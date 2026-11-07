---
description: Daily refresh across every target website. 3 finder agents per site hunt in parallel, one writer adds vetted jobs to the Hunting sheet, applies on Wellfound inside the platform, finds all people (CEO, CTO, HM, HR, TL), makes ONE Gmail draft per company plus LinkedIn outreach text, and ends with a per-website progress report.
argument-hint: [sites: all | arc | wwr | remoteok | remotive | wellfound | hn | a16z | company] [target new jobs per site, default 15]
---

Read `CLAUDE.md` first (filters, Gmail safety, sheet columns, Target websites table, India-office rule, HARD GATE). Input: $ARGUMENTS (default: all sites, 15 new jobs each).
Three finder agents per site (user, 2026-11-04), run back to back, one at a time. Everything that writes or sends stays single-threaded. The whole sheet history is audited every run (section 1b), not just today's jobs.

## 0. Roles (who may do what)
- **Finder agents (3 per site, run together):** read-only. Open the site in the browser, apply the site filter, scan, vet each job on its real page, return a structured list. They never write to the sheet, apply, email, draft, message on LinkedIn or click Send.
- **Writer (main session, one at a time):** dedupes, writes sheet rows, applies, finds people, makes drafts, writes LinkedIn text, writes the report.
- Browser rule: browser only, no scripts, no CSV/JSON job files, no curl/RSS/API pulls for boards. Mac Chrome only (never the Silo work profile). Each finder uses its OWN tab and closes it when done.

## Never stop in between (user, 2026-11-04)
Once `/daily-jobs` starts, do NOT stop, pause, ask or hand back a status report until ALL of these are true: (1) every site in the standing set has been swept; (2) every passing job is on the sheet with people, emails and company details; (3) every application the site allows has been submitted; (4) every company has its single Gmail draft; (5) `Sheet5` is updated; and (6) each site has been CLEARED by a completeness audit in which 3 independent auditor agents (keyword, depth/recency and company-first lenses) all find no relevant job left. If an auditor finds anything, the audit restarts. The only reasons to stop early are the hard limits: CAPTCHA/bot check, login/password wall, 429/403/security check, LinkedIn warning, or a tool that cannot be approved. State which one and which site, park that site as HOLD, and keep going on the rest.

## 1. Start of day (writer, before any finder)
1. Read Sheet2 header row (columns shifted on 2026-11-04) and the whole sheet through gviz CSV. Build the seen sets: job URLs, ids, company domains, company names.
2. Reconcile Gmail Sent and `from:mailer-daemon` into Stage / Application Status (Sent, Bounced).
3. HARD GATE / finish-before-start: list rows that are Applied or Found but missing people, emails, company LinkedIn, website or a draft. Finish those first (or list them as carried over in the report).
4. Read `remote_boards_ledger.md` and `live_jobs_ledger.md` so finders skip known rejects.
5. Write the seen sets into a short brief and hand it to every finder in its prompt.

## 1b. Backlog audit: ALL previous records, not just today (user, 2026-11-04)
Before new finding, and again at the end of the day, classify EVERY row ever added to Sheet2 (all dates, all Added By values) by reading the whole sheet through gviz CSV:
| Bucket | Test (columns by header name) | Action |
|---|---|---|
| A. Never applied | Application Status empty / `Found` / `Pending` / no `Applied` text, job still open, passes filters | Re-verify the real page; if open, apply (section 4) and draft. If closed: `Dead`. If it fails a filter: `Skipped: <reason>`. |
| B. Applied, no email | `Applied ...` but Stage `Not sent` and no draft in Gmail | Create the single company draft (section 5). |
| C. Drafted, not sent | Draft exists in Gmail Drafts, not in Sent | List for the sending queue (standing authorization limits). |
| D. Sent, no reply | In Sent, 5+ days old, no reply | Follow-up due (Template D), unless role closed or company declined. |
| E. Incomplete HARD GATE | Missing people, emails, company LinkedIn, website or job link | Fill first. |
| F. Hold / waiting on user | `Hold:` or `Waiting on user:` | Re-list with exactly what the user must do. |
| G. Terminal | Applied+Sent, Replied, Interview, Offer, Rejected, Dead, Skipped, Bounced | No action except reporting. |
Truth sources: applications from the sheet status AND the platform itself (Wellfound Applications tab, Arc "Applied" tab, ATS confirmation emails in Gmail); emails from Gmail Sent and Drafts (`view=pt`, account u/1). When the sheet and the platform disagree, trust the platform and fix the sheet. Work bucket A and E first, oldest rows first, at the same pacing limits (Wellfound 10 a day, etc.); anything not reachable today is carried over by name in the report, never silently dropped. Write the bucket counts to the report and the tracker (section 7).

## 2. Finder step: standing site set, TWO passes per site (user, 2026-11-04)
The site list below is the PERMANENT target set. For now every site gets exactly TWO passes, ONE finder agent per pass (11 sites x 2 = 22 passes), run back to back, each agent covering ALL of the site's sub-areas from the table in 2a:
- **Pass 1, breadth:** cover every sub-area from the top (main listing and filters, newest first).
- **Pass 2, depth and clearance:** auditor with different keywords, synonyms, stack terms, filters, deeper pages and a company-first check; returns only jobs not yet found, or an empty list.
A blocked site (429/403/CAPTCHA/login wall/security check) stops at the block and is marked HOLD. Remotive is paused. Between sites the writer adds the site's jobs to the sheet (section 3). Re-run the whole set on every later run or `/loop` tick to catch new postings. The workflow script (`workflows/scripts/daily-jobs-finders-*.js`) implements this (the earlier 3-pass, 3-agent clearance is retired for now).

### 2a. Sub-areas per site (one agent covers all three columns)
Split each site so the three agents never overlap:
| Site | Agent A | Agent B | Agent C |
|---|---|---|---|
| arc.dev (Location = India) | AI / ML / data roles | Backend / full stack | DevOps / SRE / platform / cloud |
| weworkremotely.com (user's 4-category URL) | page 1 | page 2 | page 3+ (older than last run stops) |
| remoteok.com (`remote-dev+engineer-jobs?location=IN,region_AS,Worldwide`) | first third of listing | second third | last third (last ~30 days only) |
| wellfound.com (general remote role pages) | ai-engineer, machine-learning-engineer, data-scientist | full-stack-engineer, backend-engineer, software-engineer | devops-engineer, site-reliability-engineer, platform-engineer, cloud-engineer |
| news.ycombinator.com Who is hiring? (newest thread) | comments 1-1/3 | middle third | last third |
| jobs.a16z.com (remote filter, open each company) | role: software engineer | role: data / ML | role: devops / infra |
| workatastartup.com + ycombinator.com/companies (YC, READ ONLY: no Apply, no messages; always start from https://www.workatastartup.com/companies?demographic=any&hasEquity=any&hasSalary=any&industry=any&interviewProcess=any&layout=list-compact&remote=only&role=eng&sortBy=created_desc&tab=any&usVisaNotRequired=any and open each company in a new tab) | software / backend / full-stack | AI / ML / data | devops / infra / platform + YC directory (hiring + remote) |
| Greenhouse boards (job-boards.greenhouse.io, boards.greenhouse.io) via web search `site:` queries, then open each company board (read only) | AI / ML / data | backend / full-stack / software | devops / SRE / platform |
| Ashby boards (jobs.ashbyhq.com) via `site:` queries | AI / ML / data | backend / full-stack / software | devops / SRE / platform |
| Lever boards (jobs.lever.co) via `site:` queries | AI / ML / data | backend / full-stack / software | devops / SRE / platform |
| Company career pages / ATS (Greenhouse, Ashby, Lever) for companies already on the sheet or found by web search | companies A-H | I-P | Q-Z |

Rules for every finder (copy into its prompt):
- Apply the filter set: remote; India/worldwide/APAC/overseas-open; size cap LIFTED for now (user, 2026-11-07: apply even to companies over 200, log the size); not India-based and NO India office; not agency/marketplace; pay top/midpoint about $35k+ (unlisted = flag); Staff/Senior/Lead/Founding (HN: all levels); match 30%+; gaps = "ramping up"; never reject for years asked.
- Vet the real posting and the company's own page, never the listing card alone. 404 = closed. 422/429/403/CAPTCHA/login = stop that site, report it, never bypass.
- Skip anything in the seen sets or the ledgers. Return at most the target count of NEW passing jobs.
- Return JSON-like text (not a file): company, role, job URL, company website, company LinkedIn page, location wording, size evidence, India-office check result, pay, stack, requirements have/close/gap, match %, resume family, flags, external ATS/careers link, people already visible (name, role, LinkedIn URL), and for rejects: company, role, first failed rule.
- Wellfound finders: at most 10 listing pages per burst, 1.5-3 s apart, no parallel fetch bursts, one tab each; on the first 429/403/security check ALL three Wellfound agents stop and the site is paused for the day.
- Never touch Apply, Send, Easy Apply, LinkedIn Jobs or workatastartup.com.

## 3. Writer step: merge, dedupe, add (one company at a time)
1. Merge the three lists, drop duplicates (same domain + same/near role, or same URL), keep one row per job. Two roles at one company = two rows but ONE email.
2. For each company in turn, in this order (HARD GATE order):
   a. Re-verify on the real page that the job is open and passes the filters.
   b. **People:** company LinkedIn page -> People tab (logged in, profiles only) for CEO/founder, CTO/head of engineering, hiring manager (HM), HR/recruiter/talent, team lead (TL), plus one senior dev if found; then the company site team/about, press, GitHub org, web search. For each: name, role, LinkedIn URL, live title ("Past:" = left, skip). Skip LinkedIn actions for people in India/Pakistan and people with more than 5,000 followers (emailing is separate).
   c. **Emails:** published first; else the company's visible pattern (`first@`, `first.last@`) marked "(guessed)". Never reuse an address that bounced. Minimum 3 people or `Hold: contacts not found (checked: ...)`.
   d. **Sheet row** at the first empty row, one cell write per row via the Name Box, fields by header name: A job URL, B/C/D emails, E people with LinkedIn, F company LinkedIn, H website, I external careers/ATS link, L follow-up count 0, N Added By `daily-jobs`, O status, R Stage, plus notes: layers (post, live page, fit), match %, `Gap: <tech> (ramping up; closest: ...)`, flags. Read back 2-3 rows through gviz to verify; never write into dashboard columns.
   e. **Apply** (section 4) if the site allows it.
   f. **ONE Gmail draft** (section 5).
   g. Set O/R to the real status and L/M follow-up date (+5 days when applied or drafted).
3. Log every job (added and rejected, with reason) in the sheet row notes and tab `Sheet5` (trace tab); read the existing ledgers (`remote_boards_ledger.md`, `live_jobs_ledger.md`) but do not create new files.

## 4. Applying
**GOLDEN RULE (user, 2026-11-07): if the post links to, or a web search finds, the company's own page or ATS posting, apply there. Never drop such a job.** Board-side paywalls, hidden Apply buttons and "company hidden" are NOT drop reasons: extract or search for the real link and apply on the company's form. Only the hard stops (on-site, US-auth, size, India office, agency, closed, CAPTCHA/login/password) end it; a CAPTCHA/login stop is parked as `Waiting on user` with the link, never deleted.
- **Wellfound (inside the platform, authorized 2026-11-04):** use the normal UI only, no injected scripts, one tab. Fill "What interests you" in the human v2 style: TL;DR line naming the role and the posting's exact stack, `Hi <first name or team>,`, three short paragraphs, quick links with ONE matching resume link, a short ask. No numbers, no India or hours, no admiring the company; stack gaps as "ramping up". Leave "Share my AI interview" unsaved (Escape). 180-240 s between submissions, at most 10 a day, stop at the first CAPTCHA/429 and mark `Waiting on user`. Status `Applied <date> (Wellfound)`. Skip frontend-only, QA, US-only, size over 200, India-based or India-office, agencies.
- **Arc.dev:** Fast apply with a role- and stack-specific note, matching resume family, notice "available to start soon". Skip product/design/sales, Exclusive roles whose company cannot be identified only if size/India office cannot be checked (flag it). Status `Applied <date> (Arc)`.
- **Company ATS / career page** found for any job: fill every field myself (school "Other" if not listed; phone only where required, per CLAUDE.md standard answers; salary $60,000 USD; remote from India, no sponsorship needed). Hold only for CAPTCHA, login/password, bot-check phrases, visa conflicts. Status `Applied <date> (<ATS>)` or `Waiting on user: <what>`.
- **WWR, RemoteOK:** their Apply buttons are paywalled; never use them or unmask hidden fields. Use the company's own posting by web search, else email only.
- **YC (Work at a Startup):** read only. Never click Apply or message there. Reach the company by email to the founders and the company's own site/ATS form; use the WaaS and YC company pages only to read the role, location, pay and founder names (log Added By `yc-tabs`).
- **HN:** email the contact in the post (follow its subject line); ATS form if linked.
- Never apply on workatastartup.com or LinkedIn Jobs/Easy Apply.

## 5. ONE email per company (all people in To)
- One Gmail draft per company on account u/1 (<EMAIL>): every person found (CEO/founder, CTO, HM, HR, TL, senior dev) in the **To** field, comma separated, never Cc/Bcc. Greeting names them or `Hi team,`.
- Subject: `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`. Body: v2 human style from CLAUDE.md (TL;DR, 3 short paragraphs, quick links with ONE resume link, ask, Best / Rahul Jha / LinkedIn), 90-120 words, role- and stack-specific, no numbers, no cost claims, no India/hours unless the post asks (then the company's time zone only), gaps = "ramping up". If the company already has a draft or sent mail, follow the partly-covered/follow-up variants in CLAUDE.md instead.
- Create the draft via the compose URL (`?fs=1&tf=cm&to=...&su=...&body=...`), screenshot-verify To/Subject/body, then leave it for autosave by the SAFE method only. **Never click the body and type a space, never press Tab beyond the To chip, never touch Send, Schedule send or Cmd+Enter** (three accidental sends so far). If a "Message sent" toast ever appears, tell the user immediately.
- Verify the draft exists in Drafts. Sending is a separate step under the standing authorization only: 25 a day, 3+ minutes apart, verified each time, published addresses first, guessed addresses few and last, none on a fresh mailbox.

## 6. Outreach map: who gets what (one clear rule per channel)
**Rule (user, 2026-11-07): every application on any platform also gets the Gmail draft AND LinkedIn outreach in the same pass.** If a connection-request note cannot be sent (no free notes left or no note field), send the request plain and leave a 4-5 line comment on a recent quiet post of that person: who I am (most recently SDE II at Atlassian; AI engineer on early teams) plus the exact job I applied for / am looking for with one real fit line. No recent suitable post: put the 4-5 lines in the email draft and log `no post`. An application is not done until draft + LinkedIn step are logged or HOLD.

| Target | Email | LinkedIn |
|---|---|---|
| The company (one email, everyone in To: CEO/founder, CTO, hiring manager, HR/recruiter, team lead, senior dev) | YES, exactly ONE email per company, never one per person, never Cc | none |
| Company LinkedIn page (linkedin.com/company/<slug>) | none | Follow the page; comment (as Rahul) on up to 2 recent company posts, preferably the job or hiring post or a quiet post (30 or fewer reactions+comments): role + one real fit line tied to that post. No Easy Apply, no Jobs tab. |
| CEO / founder (individual) | included in the company email | Connection request (plain by default; a note of at most 200 characters only when free notes remain, CEO and CTO first) + up to 3 short job-related comments, each on a DIFFERENT recent post of theirs. |
| CTO / head of engineering (individual) | included in the company email | Same as the CEO. |
| HM, HR, TL, senior dev | included in the company email | Email only. A plain connection request only if the user asks for it. |
Rules for every LinkedIn action:
- Check first on the profile card: location is not India or Pakistan, followers 5,000 or fewer (else log `Skipped: India` / `Skipped: over 5k followers (<n>)`). Person must still hold the title ("Past:" = left, skip). Never message Tax Pilot.
- Comments are short, specific to the post, truthful, job-related (the open role + one fit line), no numbers, no email or phone, never several on one post. Connection requests: verify the dialog names the right person, then confirm in the sent-invitations list.
- Human pace: a few actions per session, 20+ seconds apart, stop at any LinkedIn warning or CAPTCHA. Never LinkedIn Jobs/Easy Apply, no purchased Premium, never withdraw and resend.
- Log every person and page action in the Hunting sheet tab Sheet3 (A handle or `company/<slug>`, B company, C date, D comments done, E connection status, F notes). Update, never delete rows.
- The wording (notes and comments) is written in the chat for the user to see before posting a batch; posting follows `/linkedin-reach` and `/linkedin-connect` and happens only for the batch the user names.

## No new files without approval (user, 2026-11-04)
Do NOT create any `.md`, `.csv` or `.json` file (ledgers, daily reports, progress files, outreach files) unless the user approves it in chat first. Keep progress, ledgers and reports in the chat reply and in the Hunting sheet (tab `Sheet5` (trace tab) and the row notes); keep outreach wording in the chat. Editing the existing skill and CLAUDE.md when asked is fine.

## 7b. Trace tab in the sheet (Sheet5, gid 399625528): append-only
Every action is traced in the sheet, not in files. Log table A:M (header row 1, append at the first empty row, never overwrite): Date | Time | Site | Agent (A/B/C/Cover/Writer) | Company | Role | Job URL | Action (Found, Rejected, Applied, Drafted, Sent, Follow-up, Bounced, Reply, LinkedIn follow/comment/connect, Hold) | Channel (Wellfound, Arc, ATS, Gmail, LinkedIn) | People | Result / Status | Sheet2 Row | Notes. Right side: O1 DAILY SUMMARY BY SITE (row 2 headers: Date, Site, Agent A, Agent B, Agent C, Cover pass, Found, Added, Applied, Drafted, Sent, Hold), O4 BACKLOG (all dates) (A-G bucket counts), O7 EMAILS (from Gmail) (sent today, drafted unsent, follow-ups due, bounced, replies, interviews). Add one summary line per site per day and one line per block per day below the headers. Paste with the clipboard method (Name Box, cmd+v) and read back through gviz to verify.

## 7a. Live progress tracker (update after every company and every round)
Keep the progress tracker current in the chat and the Hunting sheet tab `Sheet5` (gid 399625528, trace tab) and show it to the user at the end of each site and on request. Fixed layout:
```
DAY <date>  | emails: sent today S | drafted D | follow-ups due F | bounced B | replies R
SITE            | Agent A | Agent B | Agent C | Cover | found | added | applied | drafted | sent | HOLD
arc.dev         |  done   |  done   | running |   -   |  ..   |  ..   |   ..    |   ..    |  ..  | ..
wellfound       | ...
(one line per site, status: not started / A / B / C / cover / done / paused)
BACKLOG (all dates): A never applied n | B applied no email n | C drafted not sent n | D follow-up due n | E incomplete n | F hold n | G terminal n
CUMULATIVE: rows total n | applied ever n | emails sent ever n | replies ever n | interviews n
```
Counts come from the sheet and Gmail (Sent, Drafts, mailer-daemon), never from memory. "Sent today" counts only messages in Gmail Sent dated today; "drafted" counts companies with a draft and no sent message.

## 7. End-of-day progress report (per website)
Post it in the chat and copy the totals to the Hunting sheet tab `Sheet5` (gid 399625528, trace tab) (no new file). One block per website:
`Site | finder agents (A/B/C counts) | pages/listings scanned | candidates | duplicates | dropped by reason (US-only, size, India office, agency, closed, pay, level, match) | passing | rows added (sheet row numbers) | applied | drafts created | LinkedIn text ready | HOLD (CAPTCHA/login/no contacts) | blocked/paused (429, login) | retry queue`.
Then: the section 7a tracker with the backlog buckets before and after the run (how many previously unapplied rows were applied or resolved today); totals across sites; table of added companies (Company | Role | Site | Match | Resume | People found | To count | Applied | Draft | Sheet row); carried-over incomplete rows; bounce/sent reconciliation; tomorrow's follow-ups due; and `My opinion:` with the main risk and next step.
A site is "DONE for the day" only when its rows, people, applications and drafts all exist, or each leftover is listed as HOLD or retry with the reason. Never leave work "for later" without writing it in the report and the ledger.

## 8. Pacing and safety limits (override any wish to go faster)
- Finders run back to back, one at a time (section 2); never two agents in the browser together. One writer, one Gmail compose at a time, one Wellfound tab, 180-240 s between Wellfound submissions, 20+ s between LinkedIn actions, stop at any CAPTCHA, warning, 429 or login wall and say which site and tab.
- Never solve or bypass CAPTCHAs/bot checks, enter passwords, create accounts, buy memberships, or unmask paywalled or blurred data.
- Truthfulness: facts only from the resumes and the real projects (Context.dev, Kipps.AI, Lokuma, CIKM 2023, open-source repos); no invented skills, employers or metrics.
- Atlassian is "most recently", never "leaving".
