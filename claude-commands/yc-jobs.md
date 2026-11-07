---
description: YC job flow. Start from the Work at a Startup remote-engineering list (newest first), diff every company/role against the Hunting sheet, vet only the NEW ones, then apply on the company's own page, log the sheet row, make ONE Gmail draft, and do LinkedIn outreach to CEO, CTO, HM, HR and TL. One company at a time, no stopping until the list is done.
argument-hint: [optional: max new companies this run, default all]
---

Read `CLAUDE.md` first (it holds every rule; this skill only sequences them). Input: $ARGUMENTS.

## Start page (always)
https://www.workatastartup.com/companies?demographic=any&hasEquity=any&hasSalary=any&industry=any&interviewProcess=any&layout=list-compact&remote=only&role=eng&sortBy=created_desc&tab=any&usVisaNotRequired=any
(remote only, engineering, newest first, compact list). READ ONLY: never click Apply or message on workatastartup.com.

## 1. Collect the list
1. Open the start page in the Claude tab group. Scroll until the list stops growing (or the first page of companies that are already all in the sheet). Record per company: name, YC batch, size, location line, role titles, pay if shown, company page URL.
2. Do not trust the `remote=only` filter: every card is vetted on its job page.

## 2. Diff against the Hunting sheet (before and new)
1. Read Sheet2 as gviz CSV (`.../gviz/tq?tqx=out:csv&gid=1578269214`) and Sheet3 (`gid=954465790`). Match by company name and domain (column A job link, H/I website).
2. Buckets: **already in sheet** (check its status: Applied/Drafted/Found/Skipped/Hold; finish incomplete ones per the HARD GATE and "Finish before you start"), **new** (not in sheet). Only NEW companies and incomplete rows get work; Applied rows are skipped.
3. State the counts first: seen, in sheet, new, incomplete.

## 3. Vet each new company (one at a time)
Open the company page and each role in a NEW tab. Pass if: remote, open to India/worldwide/Asia, or 3+ countries (India need not be listed), US-hours OK; no India office; not an agency; engineering role (Staff/Senior/Lead/Founding/MTS first; other levels at 30%+ match); pay top at or above about $35k; size cap is lifted (log the size). Ignore AI-engineer-titled roles until the user lifts that. Reject: US-only residency, on-site/hybrid, US-citizen/work-authorization, India-based. Record the reject reason in the sheet row as `Skipped: <reason>` so it is not re-vetted. A skipped row is NOT left as "n/a": it still gets the founder/CEO names in E (from the YC page `rawCompany.founders`, LinkedIn if found), emails in B/C/D (published first, else `first@domain` "(guessed)") and the website in H, so the contacts are ready if the skip reverses. No outreach goes to skipped companies.
Then verify the role is still OPEN: company careers/ATS page, and LinkedIn company posts (never LinkedIn Jobs). Verdict OPEN / CLOSED / UNCLEAR with the apply URL.

## 4. Per OPEN company, in this order (HARD GATE)
a. **Sheet2 row** (next free row, read the header first; Added By `yc-jobs`, status `Found`): A job link, B/C/D emails (published first, else `first@domain` "(guessed)"), E people with LinkedIn, F company LinkedIn, H website, I careers/ATS link, K/L follow-up count 0 and date +5 days (use the current column layout), proof-of-skill not needed.
b. **People, all roles that exist:** CEO/founders, CTO, hiring manager, HR/recruiter, team lead. Find via YC company page, company site, LinkedIn people search (profiles only). Record name, role, handle, live title, location.
c. **Apply on the company's own page** (golden rule) using `skills/application-form-filler`, ATS format, matching role-family resume, standard answers (phone only if required, $60,000 USD, notice "available to start soon", location Maharashtra, India; city fields: Mumbai). Write every free-text and "built in production" answer myself, truthfully, no numbers, no India/country talk. Stop only for CAPTCHA/login/account creation: mark `Waiting on user: <what> at <site>` and move on. Close the tab once applied.
d. **ONE Gmail draft** with every found person in To (never Cc), v2 human style, role- and stack-specific, saved by the approved method: compose URL, wait 8 s, click the SUBJECT line (about x=1000, y=85), type ONE space, wait 20 s, navigate same tab away. Never near Send. Draft only; sending needs a named authorization.
e. **LinkedIn for CEO, CTO, HM, HR, TL** (skip India/Pakistan profiles, Tax Pilot; follower cap does not apply to job outreach):
   - Connection request with a note (max 200 chars) when LinkedIn offers it; otherwise plain via `https://www.linkedin.com/preload/custom-invite/?vanityName=<handle>`, verify the dialog names the right person, then click "Send without a note" (its position moves when the name wraps: use a name-verified click, then confirm in `/mynetwork/invitation-manager/sent/`).
   - Plain request also gets up to 3 job comments (4-5 lines: who I am, the exact role applied for, one real fit line) on recent quiet posts (30 or fewer reactions+comments; if none, use the quietest). No numbers, no India, no contact details. Comment budget: CEO and CTO get all 3; HM, HR, TL get 1 each when they post. Skip with a logged reason when there are no posts or comments are off.
f. **Log**: Sheet2 status `Applied <date> (<ATS>) + drafted`, Sheet3 row per person (A handle, B company with name/role, C date, D comments done/blocked reason, E connection `Sent plain`/`Sent with note`/`Pending`/`Skipped: India`, F notes), and a Sheet5 trace row. Update column N/O per the status vocabulary.

## 4b. External company website: applying rules
- Apply only on the company's own page/ATS (found from the role page link or a web search `"<company>" "<role>" careers`); never on workatastartup.com or LinkedIn Jobs. Golden rule: a findable own-page link means apply there.
- Hard stops (log `Skipped: <reason>`): on-site/hybrid, US-citizen/work-authorization or must-reside-in-US, India office, agency, closed role. Not stops: US hours, size, India not listed with 3+ countries, 10+ years, 30%+ match.
- Upload the role-family PDF (never .tex); use posting keywords only where the resume supports them; gaps are "ramping up".
- Standard answers: phone <PHONE> only if required, $60,000 USD, notice "available to start soon", Maharashtra, India (city field: Mumbai), no US authorization, no sponsorship needed. Never volunteer India or countries.
- Write every free-text and "built in production" answer myself, truthful, no numbers unless asked (then resume-backed): Full Stack leads with Kipps.AI, Context.dev, Lokuma then Atlassian; ML/AI leads with the CIKM 2023 paper; Infra leads with Atlassian. A technology asked: "yes" if real or adjacent, else "ramping up".
- Fill and submit without asking; leave only CAPTCHA/typed-phrase gates, login/account creation, age/first language/demographics/visa conflicts, salary history. Mark `Waiting on user: <what> at <site>` with the link and move on. Close the tab after submit and log `Applied <date> (<ATS>)`.
- Diagram: `Commands/Flow Diagram/yc-jobs-flow.md` (v2 has this flow).

## 5. Rules of the run
- One company at a time; no parallel agents, no new .md/.csv/.json files; browser only.
- Never stop between companies, never ask mid-run, no status reports until the end or a hard stop (CAPTCHA, login wall, 429/403, LinkedIn warning).
- If a step has no tool path (people not found, no Connect button, email-required invite), mark it BLOCKED with the reason and continue.
- Comment mechanics that work: open the person's `/in/<handle>/recent-activity/all/`, wait 6 s, click the post's comment icon, click into the box, type, then click the blue Comment button after a screenshot (verify the post's comment count went up). A typed comment is not posted until the button is clicked.

## 5b. Daily refresh (how to run it every day)
- The sheet diff makes every run incremental: day 1 works the whole list, later days only the companies and roles that are new since the last run (plus incomplete rows and `Waiting on user` items from earlier days). Nothing already Applied is touched.
- Order each day: (1) reconcile Gmail Sent/bounces into the sheet; (2) finish incomplete rows and `Waiting on user` items; (3) run sections 1-4 on the new list; (4) final report.
- Run by hand: type `/yc-jobs` (or `/yc-jobs 10` to cap new companies). Keep Chrome open, signed in to Gmail (u/1), LinkedIn and Google Sheets, with the YC list in the Claude tab group.
- Repeat inside one session: `/loop 24h /yc-jobs` (self-paced loop). Unattended on a schedule: `/schedule` a daily routine with the prompt `/yc-jobs`. A scheduled run needs the signed-in Chrome profile on this Mac to be open; if a login wall or CAPTCHA appears it parks the item as `Waiting on user` and continues.
- Hard limits are unchanged on every run: no CAPTCHA solving, no passwords or accounts, drafts only (never send), never Apply or message on workatastartup.com, never LinkedIn Jobs, stop LinkedIn work at any warning.

## 6. Final report (once)
Counts: seen, already in sheet, new, rejected (with reasons), applied, drafted, LinkedIn requests (sent/pending/blocked), comments (done/left), HOLD list with the exact user step. End with "My opinion:" (one or two lines).
