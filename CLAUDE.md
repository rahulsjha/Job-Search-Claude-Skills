# CLAUDE.md — Rahul Jha job search

## Goal
Land a **first offer** from a **US-based remote company or an overseas company** (remote), at **$35k+ USD/year**. Targeting several role families at once and applying in volume with tailored resumes.

## Who I am (from the resumes in this folder)
- **Rahul Jha**, India (+91). <EMAIL> · linkedin.com/in/rahul-jha98 · github.com/rahul-jha98
- **SDE II at Atlassian** (remote), Jan 2021 – present: Intern → SDE (Jul 2021) → SDE II (Mar 2023). 5+ years.
- Flipkart SWE intern (Apr–Jun 2020), PySpark on 350+ GB/day clickstream.
- **Part-time/contract AI work:** Lokuma (MCP servers for coding agents), Context.dev (LLM web extraction, Playwright), Kipps.AI (voice agents, LangGraph).
- **Publication:** "Large Language Models as Zero-Shot Conversational Recommenders", ACM CIKM 2023 (co-author).
- **Education:** B.Tech IT, IIIT Allahabad, 2017–2021 (2nd rank sophomore year, 3rd rank freshman year).
- **Certs:** AWS Data Engineer Assoc. (2025), GCP Professional Data Engineer (2024), Azure DP-203 (2023), AWS Developer Assoc. (2023), GCP Cloud Developer (2024), DeepLearning.AI Deep Learning + Coursera ML (2022).
- **Open source:** PasswordKeeper (54+ stars), sheets-database (76+ stars), Artistify.ai (55+ stars), RestaurantTrends.stats.

## Core skills
Python, TypeScript/JS, Go, Java, SQL · FastAPI, Node, React/Next.js · Kafka, Spark, PostgreSQL, Redis · AWS/GCP/Azure, Docker, Kubernetes, Terraform, ArgoCD, GitHub Actions · LLMs, RAG, MCP, LangGraph/LangChain, voice AI, PyTorch · OpenTelemetry/Datadog.

## Files in this folder
Each role family has a LaTeX source (pdfLaTeX, Overleaf, A4, 2 pages, ATS-friendly, single column) and a compiled PDF:

| Role | Source | PDF |
|---|---|---|
| AI Engineer | `AI Engineer.tex` (`(1)` = alt copy) | `AI Engineer.pdf` |
| Data Scientist / Applied ML | `Data Scientist.tex` | `Data Scientist.pdf` |
| Full Stack | `full stack.tex` (`(1)` = alt copy) | `full stack.pdf` |
| Infra / DevOps / SRE | `infra.tex` (`(1)` = alt copy) | `Infra.pdf` |

All four share the same macros (`\entry`, `\company`, `\role`, `\cert`, `\projectitem`, `\paperitem`) and accent color. Keep the preamble untouched when editing content, and keep each resume at exactly 2 pages.

## Skills in `skills/` (23 resume/job-search skills)
Each is `skills/<name>/SKILL.md`. Most useful for this search:
- **Targeting:** `job-description-analyzer` (match score, gaps, strategy), `resume-tailor`, `resume-ats-optimizer`, `tech-resume-optimizer`
- **Writing:** `resume-bullet-writer`, `resume-quantifier`, `resume-section-builder`, `resume-formatter`, `resume-version-manager`
- **Outreach:** `cold-email-writer`, `cover-letter-generator`, `linkedin-profile-optimizer`, `application-form-filler`
- **Late stage:** `interview-prep-generator`, `salary-negotiation-prep`, `offer-comparison-analyzer`, `reference-list-builder`
- **Less relevant (academic/exec/creative/career-change):** `academic-cv-builder`, `executive-resume-writer`, `creative-portfolio-resume`, `career-changer-translator`, `portfolio-case-study-writer`

## Working rules
1. **Truthfulness first.** Never invent employers, titles, metrics, or tools. Tailor emphasis and wording only. Ask me before adding any new claim.
2. **Pick the closest resume** for a posting, then tailor a copy. Name it `<Role> - <Company>.tex`. Never overwrite the base files.
3. **Keep numbers consistent across versions.** The same facts appear in all four resumes (3M+ events/day, 450+ RPS, p95 <65ms, 35% cost cut, 88% cache hit, 60→90% coverage, 12,000+ pages/day, 3,500+ leads/month). Some metrics differ by version (e.g. RPS 450 vs 650, MTTD 35 vs 40 min, p95 65ms vs 50ms, Infra says "$85k saved" and "99.95% uptime", Full Stack says Jira/Go/Node work). Flag these for me to reconcile before sending, since interviewers may ask.
4. **Job filter:** remote only, open to hiring from India or global/overseas, ~$35k+/yr. Skip roles that require US work authorization or US residency, or that are on-site or hybrid. Prefer startups and remote-first companies that already hire in India or Asia (global payroll via Deel, Remote, Oyster). **Conflicts do not block:** if Wellfound and the company's own page disagree on where they hire (for example Wellfound says "Everywhere" but the careers page says "the Americas"), flag the conflict in the report, mention it politely in the email by asking whether India-based candidates are eligible, and still create the drafts and log the row. Hard stops remain only for roles that are clearly on-site or hybrid-only.
5. **Per posting, output:** match score, gaps, which resume to use, 3–5 bullets to adjust, and a short cold-email or cover-letter draft.
6. **Always fill the requirement mapping and one-line example.** In every cold email, cover letter and form answer, pick the posting's key requirement and pair it with a one-line example from my real work (resumes and projects in this folder). Never leave `[requirement]` / `[one-line example]` as brackets and never hand them back to me to fill. If I did not provide the posting text, infer the requirement from the job title, company page and product, fill the line, and note in one short line that it was inferred. Keep adding new mappings as I give new postings.
7. **No cost reductions or numbers in outreach.** In cold emails, cover letters and form answers, never mention cost reduction/savings or specific numeric figures (percentages, RPS, latency, event volumes, user counts, dollar amounts). Describe Atlassian achievements qualitatively (what I built, owned and shipped, and the kind of impact), and show a general understanding of what the company does. This applies to outreach only; resumes keep their metrics. It overrides the wording of any template or example that contains numbers.
8. **Find and fill the recipient's first name.** For every cold email, identify the real founder or hiring manager from the job post, the Wellfound People tab, the company's team page, LinkedIn or a web search, and fill `[First name]` yourself. State who it is and the source. Never invent or guess a name; only if none can be verified, leave the bracket and say what was checked.
9. **Log every apply/outreach message in the tracking sheet.** Whenever I create a cold email or apply message (draft or otherwise), add one row for it to the Google Sheet "Hunting", tab Sheet2 (gid 1578269214): https://docs.google.com/spreadsheets/d/1RQilpuvQiClxvdNOaHG8yDC6Gm8UepZdAoWIi-tU6vo/edit?gid=1578269214#gid=1578269214. Columns: A Links (job post URL), B Email 1, C Email 2 (the recipient emails, mark guessed ones "(guessed)"), D Companies Website, E Linkedin (the emailed people's LinkedIn URLs as "Name: URL | Name: URL"; read them from links in the job post's About and Meet-your-team sections, the Wellfound People tab and the company site before ever writing "Not found"), F Followup Count (number of follow-ups sent so far; 0 for a new row), G Followup Date (the date the next follow-up is due, e.g. 5 days after the email is sent; today's date plus 5 days for a new draft). H Added By (who created the row: `/cold` for rows from outreach, `find-jobs agent` for rows from the `/find-jobs` job-finding command; `/find-jobs` leaves B, C and G blank and `/cold` later fills them in the same row). Append to the first empty row, never overwrite or delete existing rows, and skip if the same job link is already in column A. Use my logged-in browser and verify the row afterwards. If the sheet cannot be edited, say so and give me the row text instead.
10. **Trusted sources only for finding companies, people and emails.** Use only: (a) Wellfound (jobs, company and People pages); (b) Y Combinator (ycombinator.com company directory and founder profiles, Work at a Startup); (c) LinkedIn **posts and profiles only, never LinkedIn Jobs**; (d) a16z (portfolio and jobs pages); (e) other websites only when they give a verifiable founder name, company domain or email: the company's own site (about, team, careers, contact, press), its GitHub org, Product Hunt and similar public pages. Goal order: first a verified email; if no email exists, get the founder's real name and the company's real website domain, and build `firstname@domain` marked "(guessed)". Record the source for every name, domain and email. Never use paid or scraped email lists, leaked data, or sources that cannot be cited.
11. **Company size cap: never add or contact companies with more than 200 people.** Applies to `/find-jobs` (do not add the row), `/cold` (do not draft or log) and every manual request. Use the size band on Wellfound (accept only 1-10, 11-50, 51-200) and cross-check the company's own site, LinkedIn or press page; if any trusted source shows more than 200 employees (for example a headcount, a Series C or later round, or a unicorn valuation), exclude it even if Wellfound says 51-200, or if the size is unclear say so and ask me before adding. Reject bands 201-500, 501-1000 and larger. Skipped companies are listed in the report as dropped with the size reason.
12. Compile check: `.tex` must build under pdfLaTeX with no overfull page. Overleaf is my compile path.

## Decisions made
- Applying across **all four role families in parallel** (AI Engineer, Data Scientist/ML, Full Stack, Infra/DevOps). No single priority; match each posting to the closest resume.
- Moving on from Atlassian for better opportunities. **$35k/yr is the floor, not the target**; favor higher-paying roles and negotiate up.

## Open questions to settle
- Whether the contractor gigs are disclosed in applications.
- Preferred geography/time zone overlap and contract vs. full-time (contractor, B2B invoicing is common for $35k+ overseas remote).

## Profile links and resume PDFs (use these in every outreach and application)
- LinkedIn: https://www.linkedin.com/in/rahul-jha98/
- GitHub: https://github.com/rahul-jha98
- Resume, Full Stack: https://drive.google.com/file/d/1ex-64uOAGC3OOcXh9_ncEvvrBlwoVzHm/view?usp=sharing
- Resume, Infra / DevOps / SRE: https://drive.google.com/file/d/1aWAN1tO-XvVNiW27zKm401kwt3_4NkPe/view?usp=sharing
- Resume, Data Scientist / Applied ML: https://drive.google.com/file/d/1eVOpKV_JIp6_QHQ3Q8bhF0jM0kwPIfyf/view?usp=sharing
- Resume, AI Engineer: https://drive.google.com/file/d/1YFRIvyYaNJ1Ytg-16mAWXdYXqX5VMhO8/view?usp=sharing

## Outreach message format (Wellfound notes/messages, cold emails, form answers)
Style: the human /cold style. Warm, direct, builder-to-builder. NOT bullet-heavy, NOT a resume dump. Short paragraphs, plain words.
Rules:
- Exactly ONE resume link, the one matching the role family (never several). Put it in the quick links.
- Atlassian is "most recently" (for example "Most recently I was an SDE II at Atlassian"); never "day job", never "leaving".
- No numbers, savings or percentages (rule 7). Facts only from the resumes. Mention being based in India casually when the company is overseas.
Order:
1. `TL;DR:` one sentence: the role, one line on what I build, and that I want to be heads down building their thing.
2. `Hi <first name>,`
3. Paragraph 1 (2-3 sentences): I applied / am applying for <role>, why I am writing to this person directly, and one specific thing the company does and why it is a good place for the work (shows I understood the product).
4. Paragraph 2 (2-3 sentences): who I am. Most recently SDE II at Atlassian (joined as an intern, grew into the role), owning production backend services and data pipelines other teams rely on; alongside that I work as an AI engineer on early teams.
5. Paragraph 3 (2-3 sentences, the "why I fit"): take the posting's key requirements (2-3) and answer them in plain sentences with real examples from my work, in the company's own words where possible. Skip any skill not on the resumes.
6. `Quick links:` one per line: 2 relevant project links, the single matching resume link (labelled, for example "Resume (AI Engineer): <url>"), GitHub.
7. One-line ask ("Would you be open to a short chat about the team?"), then `Best,` / Rahul Jha / LinkedIn.
Project picks by role family:
- AI Engineer: Context.dev https://context.dev (web-to-LLM extraction with Playwright), Kipps.AI https://kipps.ai (RAG voice agents on LangGraph), Lokuma https://lokuma.ai/design-agent (MCP servers for coding agents), CIKM 2023 paper.
- Full Stack: PasswordKeeper, sheets-database, Artistify.ai, RestaurantTrends.stats (github.com/rahul-jha98).
- Infra / DevOps / SRE: Kubernetes, Terraform, ArgoCD, OpenTelemetry/Datadog work at Atlassian; Kafka pipelines.
- Data Scientist: CIKM 2023 paper; data and ML platform work at Atlassian.

## Wellfound apply rule (authorized: send without asking)
- For every live Wellfound role that passes the job filter (remote, hires from India, size 1-200, pay at or above the floor, experience ask of 7+ years or more is skipped), apply on Wellfound and fill the "What interests you" note using the human /cold style above (TL;DR, Hi <first name>, three short paragraphs, quick links, ask). One matching resume link only.
- The note must name one specific thing the company does and answer the posting's own key requirements with real examples. No numbers, no invented skills.
- Skip: frontend-only, QA, US-only, size over 200 or unclear, pay unknown or below the floor, agency or third-party postings where the employer is unclear (flag them), and roles needing skills not on the resumes.
- Leave the "Share my AI interview" step unsaved (press Escape). Log each application in the Hunting sheet: column G = follow-up date (today + 5), and note "Applied on Wellfound" in the report.
- Never send Gmail drafts; Gmail stays draft-only.

## Location, availability and application scope (updated 2026-10-13)
- Location: Maharashtra, India. Use "Maharashtra, India" whenever a form asks for city/location. Do not give a phone number unless I supply one.
- Availability: my working window is 8 PM to 1 AM IST (UTC+5:30), but NEVER write "IST" or my India hours in any message. Always convert the window into the company's own time zone and state only that, e.g. "I'm available 10:30 AM to 3:30 PM Eastern" (daylight-time conversions: US Eastern 10:30 AM to 3:30 PM, Central 9:30 AM to 2:30 PM, Mountain 8:30 AM to 1:30 PM, Pacific 7:30 AM to 12:30 PM, UK 3:30 PM to 8:30 PM, Central Europe 4:30 PM to 9:30 PM, Dubai 6:30 PM to 11:30 PM, Singapore 10:30 PM to 3:30 AM, Brazil 11:30 AM to 4:30 PM, UTC 2:30 PM to 7:30 PM). Use the company's location or its "preferred timezones" to pick the zone. If the zone is unknown, say "I'm happy to work in your time zone and adjust to whatever overlap you need" with no IST. Recompute after clocks change (US daylight time ends 2026-11-01).
- Apply even when the tech match is only about 30-40%; apply even when the role asks 7+ years; do not drop a remote role only because the company is outside India or lists another location or timezone. Still skip: on-site only, roles that explicitly require US citizenship or work authorization, and company size over 200.
- Wellfound applications are authorized to be sent without asking (see the Wellfound apply rule). Gmail stays draft-only.

## Keep the tracking sheet current (rule)
- After EVERY Wellfound application or skip decision, update the Hunting sheet (Sheet2) in the same pass: column G = follow-up date (application date + 5 days, written 2026-MM-DD) and column I "Application Status" = "Applied YYYY-MM-DD", "Skipped: <reason>" (closed, US-only, large/unicorn, same company already applied, pay far below floor, not an engineering role, hires only certain countries) or "Pending". New jobs found later get a new row first (columns A-H as before), then the status.
- Never overwrite an existing follow-up date or status; only fill blanks or change "Pending" to the real outcome.

## Target overseas companies only (rule)
- Do NOT target companies based in India (company location or all listed locations in India, e.g. Bengaluru, Mumbai, Delhi, Pune, Hyderabad, Gurugram). Do NOT browse Wellfound's "jobs in India" pages for sourcing. Target overseas companies (US, UK, EU, Middle East, SEA, etc.) whose posting allows Indian/remote-worldwide candidates ("Hires remotely: India / Everywhere"), remote, 1-200 people, pay at or above the floor.
- When sourcing, use Wellfound's general remote role pages (wellfound.com/role/r/<role>) and the company's own location, then screen for "Hires remotely" including India or Everywhere.

## Sheet completeness and pacing rules (added 2026-10-13)
- Every row in the Hunting sheet must have ALL columns filled: A link, B Email 1, C Email 2 (real if verified, otherwise predicted `firstname@domain` / `hello@domain` marked "(guessed)"), D company website, E LinkedIn ("Name: URL | Name: URL"; if none found after checking, "Not found (checked: <sources>)"), F follow-up count (0), G follow-up date (+5 days), H Added By, I Application Status. No blank cells.
- If a Wellfound job page is blocked (429), still add the row: predict the email from the company's real domain and a verified founder name (web search, company site, LinkedIn), mark "(guessed)", and set status "Pending (Wellfound blocked)" until applied.
- 7+ years of experience asked: still apply. Pay ranges count if the top of the range or the midpoint is at or above ~$35k (e.g. $30k-45k qualifies).
- Go slow on Wellfound: small batches (about 20-25 pages), pauses between them, stop at the first 429 and never bypass the security check.

## Role- and stack-specific messages (rule, added 2026-10-13)
- Every application message must be specific to that job's role title and tech stack, not a generic family template. Read the posting's stack (languages, frameworks, cloud, tools) and name those exact technologies and the role in the TL;DR and the "why I fit" paragraph.
- If the job needs a different stack from my main one (for example Go, Rust, Java, .NET, Ruby, a different cloud or database), say so directly: name that stack and role, connect it to the closest real experience from the resumes (for example Go and Java are on the resume, Kafka/Spark/PostgreSQL/Kubernetes, etc.), and state plainly that I pick up new stacks quickly. Never claim a skill that is not on the resumes (truthfulness rule 1); for a gap, say I am ramping up on it rather than claiming experience.
- The auto-apply macro (`AJ`) must be given the posting's stack and role before sending; do not send its default family note when the stack differs.

## India-based only is the skip rule (clarified 2026-10-13)
- Skip ONLY companies located in India (HQ or all listed locations in India). Every overseas company that passes the job filter (remote, hires India or everywhere, pay upper bound above ~$35k, not US-only, not on-site) gets BOTH the Wellfound application and a Gmail cold-email draft. Do not skip an overseas company because its product, status or founder name is unclear: write the draft ("Hi team," if no verified founder name), say what could not be verified in the report, and log the row.
- The company-size cap (rule 11) still applies only when a trusted source clearly shows more than 200 people; unclear size is flagged in the report but the draft is still written.

## Wellfound pause (set 2026-10-13)
- Do NOT submit any more Wellfound applications until the user says to resume. Jobs whose pages return HTTP 422 or 404 (job hidden/unpublished or stale link) are retried on or after 2026-10-14 (about a day later), then screened and applied to only if the user has resumed applying.
- In the meantime, create Gmail cold-email drafts (never send) for jobs that are open and for existing sheet rows that have no draft yet (overseas companies only, per the India-only skip rule). Not-yet-applied rows use a Template A style intro that names the role.
- Rows whose job page cannot be read keep: G = 2026-10-14 and I = "Retry after 2026-10-14: job page unavailable (HTTP 422/404)".

## Gmail safety rule (added 2026-10-13 after an accidental send)
- NEVER use the Tab key to move between Gmail compose fields beyond the single Tab that turns the To address into a chip, and never type text while focus could be on the Send button. A space typed while Send is focused SENDS the message (this happened once: an empty no-subject email went to ayush@answerthis.io at 11:01 PM on 2026-10-13).
- Move between To, Subject and Body only by clicking the field after a screenshot confirms its position, and always screenshot-verify the Subject/To before typing the body. Gmail is draft-only: never press Enter/Space on a focused Send control.

## Staff/Senior/Founding-level roles only (user, 2026-10-24)
- For now, apply to and keep in the Hunting sheet ONLY Staff, Principal, Senior, Lead, Founding and VP/leadership-level engineering roles. Do not add, apply to or draft for junior, mid-level ("Software Engineer", "Backend Developer") or other-level roles. Rows already Applied or Emailed are kept for follow-up tracking.
- On 2026-10-24 the user asked to delete the non-matching rows 300-364 from Sheet2. Kept: EkTech (302), Surventrix (310), Ihsan (324), Fintricity (330, applied), Hyatus (332), Terrabase (336), Clever Craft (340, applied), ITIS (347, emailed), Invert (351), Gather (355), Attack Capital (360). Gmail drafts for deleted companies were not removed.

## LinkedIn outreach, never LinkedIn Jobs (user, 2026-10-25)
- Do NOT apply through LinkedIn Jobs / Easy Apply (Arc "Apply now" links go there too). For Arc.dev leads and any other lead, reach out on LinkedIn to founders, CTOs and the people who are hiring: (1) comment on their last 3 posts and (2) send a connection request with a short note. Short and concise, same human style, no numbers, no India mention, one specific line on the role.
- Only engage with posts that have 30 or fewer likes plus comments (a founder is more likely to notice a comment on a quiet post). Skip posts above that.
- Comment only when the company has a job posting open (the person is hiring); then also send a connection request with a quick note. Invitation notes are limited to 200 characters, and this free account has only 5 personalised invitations per month: use them on the CEO/founder and CTO/hiring lead first, send others without a note or save them for next month.
- Log every person in the Hunting sheet tab Sheet3 (gid 954465790): A `Linkedin Username` (the handle after /in/), B `Company Name`, C `Last Reachout` (date, YYYY-MM-DD). Append one row per person, update `Last Reachout` when you act again, never delete rows. Row 2 = rhariprasad / Zenara Health / 2026-10-25.
- Hiring-post mode (user, 2026-10-25): search LinkedIn content (`/search/results/content/?keywords=looking for ai engineer remote`) for engineer hiring posts, reply with 3 comments (about me, skills, what I am looking for), NO connection request, and do not skip posts with no salary or with higher experience asks. Details in `.claude/commands/linkedin-reach.md` (Mode B). Sheet3 now has a fourth column D `Comments` for what was done.
- Mode B format (user, 2026-10-25): ONE short comment on the job post, THREE short comments on three different recent posts of the same person, plus a connection request with a note of at most 200 characters. Never several comments on one post. No email or phone in comments. Overrides the earlier 3-comment and contact-line rules.
- Comments are job-related (user, 2026-10-25): every comment on a founder/hiring lead post must mention the open role and one real fit line, tied briefly to that post. No generic congratulations or networking comments; comments are our main channel because invitations are limited.
- Keep it human-paced: a few actions per session, 20+ seconds between comments, stop at any LinkedIn warning or CAPTCHA. Never click the Easy Apply or Next/Submit buttons on LinkedIn Jobs.

## Second accidental send (2026-10-24)
- The "click body, cmd+End, type a space" step to force-save a draft SENT the ITIS Pro Group email to prathap@itisprogroup.com at 08:15 when the window layout differed (Undo came too late). From now on NEVER click or type in a Gmail compose window to save it. Load the compose URL, wait 10 s, take a screenshot to confirm To/Subject/body, then press Escape only (Gmail saves the draft on close), and verify the draft in Drafts. If a "Message sent" toast ever appears, say so to the user immediately.
- The Chrome session may be signed in to two Google accounts: Gmail drafts must be on u/1 (<EMAIL>); the Sheet may open under <EMAIL2> (fine for editing). Check the account in the tab title before any Gmail action.

## Short messages (added 2026-10-14, user request)
- Keep every cold email and application note SHORT and concise: each section (TL;DR, intro, who I am, why I fit) at most 3-4 short lines, whole body roughly 90-120 words. Keep the format order, quick links and ask, but cut detail.
- Standard draft format (2026-10-14): see "NEW STANDARD TEMPLATE" at the end of `.claude/commands/cold.md` (TL;DR, Why <Company>, Who I am, Why I fit bullets, Quick links, ask). All existing Gmail drafts are being rewritten to it.

## Human-style drafts (updated 2026-10-14, overrides earlier format/location rules)
- Follow the user's reference email (Happenstance): `TL;DR:` line, `Hi <name>,`, then 2-3 short plain paragraphs of 3-4 lines each, one `Quick links` block (one resume link), a short ask, `Best, Rahul Jha`, LinkedIn. Sounds like a person wrote it: contractions, plain words, no section headings, no bullet lists, no corporate filler.
- NEVER say I'm based in India, and never give time-zone/working hours, unless the posting or the person asks for it or it is required (overrides "always say based in India casually" and the time-zone conversion rule).
- NEVER describe what I like or admire about the company/product ("I love what you're building", "Why <Company>" praise). Say only the role I'm writing about and the tech the role needs. (Overrides the "one specific thing the company does" rule.)
- Keep all factual claims from the existing drafts (applied status, resume-based stack claims); only tighten the wording. Gaps stay as "ramping up".
- Location/availability rule (2026-10-14): never mention being from India or my availability in outreach. Only if the posting or the person ASKS about location/availability/overlap, answer that I'm available to follow their specific time zone overlap, naming their zone (e.g. PST, EST, CET) without any India hours or "IST".

## Sending, spacing and tracking (added 2026-10-14)
- Claude only creates drafts. The user sends them. Claude never sends (no Send, no Schedule send) unless the user explicitly authorizes sending for a named batch.
- Sending rule: at least 3 minutes between two sent emails. Remind the user of this when handing over a batch; never recommend bulk sending.
- Keep the Hunting sheet in sync with the Gmail Sent folder: when an email is sent, set column I = "Sent YYYY-MM-DD HH:MM" and column G = send date + 5 days. Check Sent folder at the start of every session and after every batch.
- Track failures: search Gmail for mailer-daemon bounces (`from:mailer-daemon`), mark the row "Bounced: <address>" in column I, find a verified address (published email, careers page, another founder) and make a new draft; never resend the same guessed address.
- Stability: after creating a draft, verify subject, To and body in the saved draft; re-check before handing over.

## Human-pace and account-safety rules (added 2026-10-14)
Goal: avoid Gmail spam flags and Wellfound blocks. This is throttling only; never bypass CAPTCHAs, security checks or rate limits.

Email (the user sends; Claude drafts and tracks):
- Spacing: at least 3 minutes between sends, randomised 3-6 minutes; never two sends in the same minute.
- Daily cap: at most 25 cold emails per day (start at 15 on a new batch day), only in the recipient's local working hours (morning to early afternoon), at most 2 per company domain per day.
- Order: send published/verified addresses first, "(guessed)" addresses last and only a few per day. Stop the batch if 2 bounces or any "message blocked" appears; wait a day.
- Bounce hygiene: keep bounce rate under 5% (the first batch hit about 14%). Never resend to a bounced address; find a verified one or drop.
- Every email must differ (specific role and stack lines); no copy-paste blasts. No attachments or tracking links; plain text with the one resume link.
- Do not send between midnight and 6 AM recipient time.

Wellfound:
- Applying stays paused until the user says resume. When resumed: at most 10 applications per day, a pause of 30-90 seconds (random) between actions, no parallel tabs, sessions of 20-30 minutes with breaks.
- Do not run fetch bursts. Screening scans must be small (at most 10 pages per run, 1.5-3 s apart), stop at the first 429, 403 or security check and wait at least a day.
- Prefer doing apply steps through the normal UI, never via injected scripts that submit forms.

Tracking: after each batch update the Hunting sheet (Sent time, follow-up +5 days, Bounced/Blocked status) and review the Sent folder and mailer-daemon replies.

## Wellfound RESUMED (2026-10-14, user instruction in chat)
- The user lifted the Wellfound pause: "also try to apply for Wellfound ... apply on Wellfound with 3-4 mins delay between applications". Applications are authorized again, through the normal UI, vetted per job, with 180-240 s between submissions, at most 10 per day (2 done on 2026-10-14: Viso, Infrawatch). Queue: `wellfound_queue.md`. Still stop and report at any CAPTCHA / rate limit; the user solves CAPTCHAs.
- The earlier "Wellfound pause (set 2026-10-13)" section no longer applies; the human-pace rules do.
- Correct Data Scientist resume link: https://drive.google.com/file/d/1eVOpKV_JIp6_QHQ3Q8bhF0jM0kwPIfyf/view?usp=sharing (the earlier copy in this file had a typo).

## First-pass rule for every Wellfound job (user instruction, 2026-10-14)
- For EVERY Wellfound job posting that passes the job filter, do BOTH: (1) apply on Wellfound (UI, short human-style note) and (2) create a Gmail email draft in the v2 human style to the best verified/published contact, logged in the Hunting sheet. A job is "first pass complete" only when both are done and column I says so.
- Order: vet the posting, apply on Wellfound, then draft the email (or draft first if the page is likely to close). Never send the drafted emails automatically; only the sender agent sends, paced 3-20 minutes apart.
- Wellfound applications: 180-240 seconds between submissions. For this first pass the daily cap of 10 is lifted by the user ("I want at least first pass to be done"); still stop at the first CAPTCHA, rate limit or block and wait.
- India-based companies were deleted from the Hunting sheet (2026-10-14, user request: rows removed, sheet now 147 rows). Do not re-add India-based companies.
- Sheet row numbers shifted after the deletion; refer to rows by company name, not the old row numbers.

## Match threshold (2026-10-14, user instruction)
- A 30% match is enough: do not drop a job for match score at or above 30%; apply and log it. Other filters stay.

## Never skip, be thorough and structured (user rule, 2026-10-14)
- When asked to find, apply, draft or send, do the FULL job. Never stop early, skip a source or a step, or return "0 found" without a deep check. No shortcuts.
- Never drop or skip a job on a listing card alone (card region tags like "Everywhere"/"US" are unreliable). Open the job page and vet it before dropping. A drop needs a stated reason from the real page.
- A 422/404 is "retry later": queue it, retry (slower, different time), and list it in the report. Do not stop the whole run for it. Only a 429/403, CAPTCHA or security check stops the run (wait, never bypass), and then resume as soon as it clears and report what is still undone.
- Cover every angle each run: all role pages and pagination on Wellfound, pre-screened candidate lists (window.__cand/__rem), hidden "+N" regions, YC Work at a Startup filters plus the YC company directory (hiring + remote), then a16z/LinkedIn posts/company sites.
- Always follow the 30% match rule, the same filters, and dedupe against the sheet.
- Report in a fixed structure every time: counts (screened, duplicates, dropped by reason, passing, retry queue, still undone), the Added table, and next steps. Log new rows in the sheet as part of the same run, and never leave work "for later" without writing it in tasks.md.
- Applies equally to emails (full draft coverage, bounce checks) and to Wellfound applications.

## Company LinkedIn rule (user, 2026-10-14)
- For EVERY job/company we log, find the COMPANY's LinkedIn page (linkedin.com/company/<slug>) and put it in the sheet column P "Company LinkedIn" (new column; column E stays for the founders'/hiring contacts' personal LinkedIn). Do this at the moment the row is created, and backfill any row where P is blank.
- How to find it (trusted sources only): the company's own site footer/about page, the Wellfound company page, the YC company page, Product Hunt/GitHub org; if none lists it, open a NEW tab and search the web for "<company> LinkedIn company page" and take the official page (matching name, website and location). Never guess a URL. If nothing is found, write "Not found (checked: <sources>)" and keep it on the retry list.
- Also use it for the size check (rule 11): the LinkedIn company page headcount band is a trusted cross-check.
- Every new find-jobs, /cold and Wellfound/YC row must have P filled before the run is called done. (Stats block is in N:O, Email Failed is K.)

## a16z size cap exception (user, 2026-10-15)
- For jobs sourced from a16z (jobs.a16z.com / a16z portfolio companies) ONLY, the company-size cap is raised from 200 to 1000 people. Accept a16z bands 2-10, 11-50, 51-200, 201-500, 501-1000; still cross-check (headcount, funding) and reject anything clearly above 1000. Wellfound and YC keep the 200 cap (rule 11). Log the size band in the status cell for 201-1000 companies.

## Sheet column rules: website and LinkedIn (user, 2026-10-15)
Applies to EVERY row in the Hunting sheet (Sheet2), existing and new. A row is not complete until these are filled; never leave them blank.
- **D Companies Website**: the company's real website (https://domain), verified from the job post, the company's own site, the Wellfound/YC/a16z page or a search. Never leave blank and never write a made-up domain; if not found write "Not found (checked: <sources>)" and put the row on the retry list.
- **E Linkedin (people)**: the emailed founders'/hiring contacts' personal LinkedIn as "Name (role): https://www.linkedin.com/in/<handle> | ...". If a name is known but no URL, "Name (role): LinkedIn not found". Look at the job post links, the company's team/about page, the Wellfound People tab and a web search before writing "Not found (checked: ...)".
- **P Company LinkedIn**: the official company page https://www.linkedin.com/company/<slug> (see "Company LinkedIn rule"). Mark "(unverified)" when it came from a directory or search and was not matched on the company's own site.
- Also keep: A job link, F follow-up count (0), H Added By, I status with size/match/eligibility notes. Columns J (Email Sent), K (Email Failed tick-box) and N:O (stats) are not edited by the finders.
- Backfill: at the start of each session, scan for rows where D, E or P are blank or "Not found", and retry them with a deeper search (company site, Wellfound/YC/a16z page, new-tab web search). Report how many were fixed and how many remain.
- Each finder agent must return website + people LinkedIn + company LinkedIn for every job it reports; rows without them go back to the retry list instead of being called done.

## All key contacts per company, not just one (user rule, 2026-10-15)
- For EVERY company, collect the emails of ALL relevant people, not one: every founder/co-founder, the CEO, CTO/head of engineering, the hiring manager or recruiter for the role, and up to 4-5 people in total (fewer only if fewer exist; at larger a16z companies, the most relevant 4-5). Never stop at the first person found.
- Sheet layout: B = primary email (verified first); C = every other email separated by " | ", each marked "(guessed)" if unverified, or "(published)" / "(verified: <source>)"; E = the same people as "Name (role): https://www.linkedin.com/in/<handle> | ..." in the same order. Keep a generic contact (info@/hello@/careers@) only as a fallback after personal addresses.
- Sources are the trusted ones in rule 10 only; record the source per name. Never invent a name or address; never use scraped or paid lists. Max 2 sends per company domain per day still applies (the user sends), so extra addresses are for choosing the best contact and for follow-ups, not for blasting everyone.
- Backfill: go through every existing row one by one (by company name) and add the missing people/emails. Track progress in tasks.md. Drafts stay one per person only when the user asks; by default keep the existing draft to the primary contact.

## External company applications: APPLY on the company site too (user rule, updated 2026-10-16; replaces the 2026-10-15 "left out" rule)
- "External application" = an application on the company's own site or ATS (Greenhouse, Lever, Ashby, Workable, careers page form). When a job has one, apply there as well as on Wellfound (if listed there), in addition to the Gmail draft. Use the real posting URL in column A.
- Authorized by the user in chat (2026-10-16) to fill and submit external forms through the normal UI, one at a time, after vetting the job against the filters. Use the matching resume link/PDF the form asks for and a role- and stack-specific answer (no numbers, no India mention).
- Stop and hold (ask the user) for: phone number, work authorization/visa/sponsorship, CTC/salary history, notice period, relocation, demographic or legal declarations, account creation or password sign-in, CAPTCHAs/bot checks, anything paid. Never bypass a CAPTCHA or security check. Never create an account on the company's behalf.
- Log in column I: "Applied externally YYYY-MM-DD (<ATS>)" with G = +5 days, or "External form needs user answer: <what>" when held.
- Contacts: for every company collect ALL founders/CEO/CTO and the hiring manager/recruiters (4-5 people) with names, roles, LinkedIn and emails per "All key contacts per company" above; put them in B, C and E.

## Hand-off points: CAPTCHA and login (user asked to define, 2026-10-16)
- **Who does it:** the user, always, in the real Chrome tab Claude is working in. Claude never solves or bypasses a CAPTCHA, bot check, Cloudflare/"verify you are human" page or 2FA, and never types a password, creates an account or logs in on the user's behalf.
- **Where:** the exact tab where the block appears (Wellfound, workatastartup.com, a company/ATS application form, Gmail, Google Sheets). Claude leaves that tab open on the blocking page and does not navigate away or retry it.
- **What Claude does at a block:** (1) stop that task; (2) say in one line which site and tab, and what is needed ("CAPTCHA on <company> form" / "log in to Work at a Startup"); (3) mark the row in column I as "Waiting on user: <CAPTCHA|login> at <site>" with the date; (4) continue with other work that does not need that tab (other sources, drafts, sheet updates).
- **Resume:** when the user says "done"/"continue", Claude re-checks the same tab, confirms the block is gone with a screenshot, and resumes from where it stopped, then updates column I from "Waiting on user" to the real status.
- **Logins needed once per session (user keeps them signed in):** Wellfound, Work at a Startup (YC), Gmail (<EMAIL>, drafts only), Google Sheets (Hunting). If a session expires, treat it as a login block above. Same-day repeats of the same block on one site: pause that site for the rest of the day and tell the user.

## Status vocabulary for column I (user asked to define, 2026-10-16)
Use ONE of these at the start of column I, then free-text detail after a semicolon. Dates as YYYY-MM-DD.
- `Found` - passes filters, nothing sent yet (no application, no draft).
- `Drafted` - Gmail draft exists, not sent (user sends; Claude never sends).
- `Applied <date> (<where>)` - application submitted: Wellfound, company ATS/form, or email-to-apply. Add `+ drafted` when a draft also exists.
- `Emailed <date>` - cold email sent by the user (from the Gmail Sent folder). Column J = sent time, G = +5 days.
- `Followed up <n>` - follow-up sent (F = count).
- `Replied <date>: <summary>` - any human reply; `Interview <date>` once scheduled; `Offer`, `Rejected`.
- `Hold: <what the user must answer>` - needs a user decision (phone, work authorization, size, CTC, region). Mirrored in column R.
- `Bounced: <address>` - delivery failed (K ticked); needs a verified address.
- `Skipped: <reason>` - failed a filter on the real page (US-only, on-site, size, pay, agency, clearance, India-based, closed).
- `Dead` - link 404/closed.
- Sync rule: at the start of each session reconcile the Gmail Sent folder and mailer-daemon bounces into this column and J/K.

## Standard ATS form answers (user, 2026-10-18)
- Phone: <PHONE> (given by the user in chat 2026-10-18); use it only on application forms that require it, never in emails or sheet cells.
- Compensation target / expected salary: $60,000 USD per year.
- Work authorization and sponsorship: based in India working remotely; not authorized to work in the US; no visa sponsorship needed for remote work. Answer truthfully.
- Location: Maharashtra, India. Resume: the matching role-family PDF in the project folder (AI Engineer.pdf, full stack.pdf, Infra.pdf, Data Scientist.pdf).
- Never invent experience for essay or "do you have X" questions (for example Kubernetes at scale, LLM fine-tuning); hold those forms and ask. CAPTCHAs are the user's job.

## Sheet entry method and draft workflow (learned 2026-10-18)
- Typing a Tab character through the browser puts a literal tab inside ONE cell. To add rows: type each row as one tab-separated line into column A (rows ending with a newline), then select A<first>:A<last> and use Data > Split text to columns (separator auto-detects tabs). Never type tab-separated text starting from column B.
- To update a column for many rows, type all rows in one contiguous block starting at the first cell; never use the Down key with repeat to skip rows (it skips unreliably). Verify afterwards by reading the gviz CSV.
- Gmail drafts: open the compose URL (to and subject only), wait 4 s, type the body, wait 6 s for autosave before navigating to the next draft. If a "Leave site?" dialog blocks navigation, wait and check the draft before typing anything else. Verify in Drafts afterwards.
- Local copies: `yc_leads.md` holds the YC tracker and all draft texts.

## Small multi-region companies: apply even if India is not listed (user, 2026-10-17)
- If a company has fewer than 50 people AND its posting allows more than 3 locations/countries for remote work, treat it as eligible and apply (email to founders / company's own site; never WaaS) even when India is not in the list. In the email, ask politely whether India-based candidates are eligible. All other filters still apply (remote, pay floor, not on-site, no explicit US-citizen/work-authorization requirement, not India-based, role fits the resumes).
- 3 or fewer listed countries, or 50+ people, keeps the old rule (skip when India/worldwide is not allowed).
- Log such rows as `Found; small multi-region (<50 people, N countries, India not listed)` and keep the usual columns.

## NO applying on workatastartup.com (user, 2026-10-17; overrides the YC section below)
- Never click Apply or send a message on workatastartup.com (Work at a Startup). For YC leads, reach the company only through (1) email to founders/hiring contacts (Gmail draft, the user sends) and (2) the company's own website/careers/ATS form. Use WaaS pages only to read the role, location, pay and founders.
- Already applied on WaaS before this rule (2026-10-17): Asha Health (Staff Software Engineer, AI Agents) and SiPhox Health (Full-Stack Software Development Lead). Log them as such; do not repeat.
- Log rows for YC leads with Added By = `yc-tabs`; the "no email drafts" line below is replaced by: draft emails are fine again for YC leads.

## YC tab leads: apply + sheet only, no email drafts (user, 2026-10-17) [superseded above]
- For roles found on the YC Work at a Startup tabs (company pages and job pages the user opens or keeps in the Claude tab group): vet the real role, apply on Work at a Startup (or the company's own apply link it points to), and log the row in the Hunting sheet. Do NOT write Gmail drafts for these unless the user asks.
- Status format per the status vocabulary: `Applied <date> (YC WaaS)` or `Found` / `Skipped: <reason>`; Added By = `yc-tabs`. Fill A (job URL), D (website), E/F/G/H/I/P; B/C may say "not drafting (user rule)" when no email is needed.
- Filters unchanged: remote and open to India/worldwide or no US-only/visa-citizenship ask, company size 1-200, pay top about $35k or more, not India-based, not clearance/US-citizen only.

## Contacts for EVERY row incl. a16z, plus internal hiring post (user, 2026-10-20)
- For every job row on the sheet (a16z included), find 3-4 people with emails: CEO/founder, CTO/head of engineering, hiring manager, HR/recruiter. Sources: company website (about/team/careers/contact/press), LinkedIn profiles and posts (never LinkedIn Jobs), GitHub org, Product Hunt, a16z/YC/Wellfound people pages. Verified email first; else real name + real domain -> firstname@domain marked "(guessed)". Never invent names.
- If fewer than 3 people can be found after checking those sources, skip drafting for now: set column I to "Hold: contacts not found (checked: <sources>)" and list it in the report; do not draft to a single guessed address.
- Also find the company's own internal hiring post (careers page, ATS page, founder/recruiter post, other boards) and put that URL in the row notes (column I detail), plus any better role details (pay, regions, stack) found there.
- Record people in B (primary), C (others, " | "), E (names, roles, LinkedIn), with source per name. Respect max 2 sends per domain per day; Claude only drafts.
- Role mix per company (user, 2026-10-20): collect as many of these as exist, in this order: CEO/founder, CTO, hiring manager (head of the team the role sits in), HR/recruiter/talent, a senior or lead developer on the relevant team when relevant, and a team member (TM) in the same function. Aim for 4-6 people per company; minimum 3 or the row is Hold. Run it for every live row on the sheet, one company at a time, and write people into B/C/E with a source.
- Per-person fields (user, 2026-10-20): for EVERY person recorded, capture both the email AND the LinkedIn profile URL (linkedin.com/in/<handle>), plus name, role and source. Emails: published address first; if none, a guessed `firstname@domain` marked "(guessed)" (company's real domain, real verified name only). LinkedIn: read the profile link from the Wellfound/YC/a16z people section, company team page or a LinkedIn search result; if not findable write "LinkedIn not found". Sheet layout: B = primary email, C = all other emails " | " (each marked guessed/published), E = "Name (role): <linkedin url> | ..." in the same order as B/C. A person without email or LinkedIn is still recorded, with the missing field stated.
- Open-source / proof-of-skill check (user, 2026-10-20): for every company also look for places where I can show my skill: a public GitHub org and its repos (name the repo that matches the role, note stars, good-first-issues, contributing guide), public docs/SDKs, bounties, hackathons, public take-home or coding challenges, engineering blog, community Discord/Slack. Record the best 1-3 links in the row notes ("Proof-of-skill: <links>") or "none found (checked: GitHub, site)". Use it in outreach: contribute or reference a relevant repo before/while applying, and mention it in the draft only as a real, specific fact.
- Find ALL, not some (user, 2026-10-20): for every company record EVERY one of these that exists: all founders and co-founders, CEO, CTO, CPO, COO, head of engineering / engineering manager / technical lead, the hiring manager for the role, HR / people ops / talent / recruiter, and a senior dev on the team. Never stop at the first 1-2 names.
- Minimum search checklist per company before writing "not found" (log which were checked): (1) Wellfound job page "Meet your team" + company People tab; (2) YC / a16z / Crunchbase / PitchBook company page; (3) company site pages: /about /team /careers /contact /press /blog; (4) web search "<company> CTO", "<company> head of engineering", "<company> recruiter OR talent OR people", "<company> founder LinkedIn"; (5) LinkedIn company People tab and profile search results (profiles only); (6) GitHub org members and top committers; (7) founder posts on LinkedIn/X announcing the role; (8) ATS page (Ashby/Greenhouse/Lever/Workable) hiring contact. Only after all of these may a role be marked "not found".

## No 2-per-company cap; verify remote, avoid WFO (user, 2026-10-20)
- The "max 2 people / 2 sends per company domain per day" limit is lifted for now: draft to every relevant person found at a company. (Still draft-only; spacing of at least 3 minutes between sends stays as the user's sending practice.)
- Avoid WFO: before researching or drafting for any company, confirm from the real job page (Wellfound/YC/a16z/ATS) that the role is fully remote. Reject and mark `Skipped: WFO/on-site/hybrid` if the page says on-site, hybrid, "in office", "office-based", relocate, or lists only a city with no remote option. Record the evidence (location line, work policy) in the row notes.
- GitHub procedure (user, 2026-10-20; do not just guess org URLs): (1) search orgs: `api.github.com/search/users?q=<company>+type:org` (unauthenticated, ~10 searches/min, ~60 core calls/hour, so pace and batch); (2) verify the org belongs to the company: blog/homepage field matches the company domain, or description/repos match; never use name-only matches (example: github.com/Swivl is a different company); (3) list repos (`/orgs/<org>/repos?sort=pushed`), stars, forks vs original; (4) list public members (`/orgs/<org>/public_members`) and top contributors of the main repos (`/repos/<org>/<repo>/contributors`); (5) for each person fetch `/users/<login>` for real name, company, blog, X handle, location and use them as persona leads (CTO/engineers/hiring managers), then find email/LinkedIn via their blog or profile; (6) record under "GitHub" in the row (column T). If nothing verified, write "none found" with what was checked.
- LinkedIn live check (user, 2026-10-20): for every person, get the real linkedin.com/in/<handle> URL and the LIVE current title/employer from the logged-in LinkedIn people search (`linkedin.com/search/results/people/?keywords=<name> <company>`, profiles only, never LinkedIn Jobs; 6 s between searches, at most about 6 per call). If the profile shows "Past: <role> at <company>", the person has LEFT: mark stale, do not draft to them, and delete any draft already made. Record the live headline in column U. Also note any open-source repo or project the person personally promotes (personal GitHub, X, blog) as extra proof-of-skill hooks.

## Correct sheet columns, written structured 2026-10-20 (supersedes writing to S/T/U)
The sheet already has dedicated columns for all contact research; use them directly, never stray columns:
- B Email 1 (primary, guessed/published)
- C Email 2
- D "Email 3 and more" (every further email, " | " separated, each marked guessed/published)
- E "Linkedin Profiles" = "Name (role): <linkedin url or 'LinkedIn not found'> | ..." for every person, same order as B/C/D
- F "Company Linkedin" = https://www.linkedin.com/company/<slug>, mark "(unverified)" if not confirmed on the company's own site
- G "Open Source" = verified GitHub org/repo with stars + what's usable (good-first-issue, original vs fork), or "none found (checked: ...)"
- H "Companies Website"
- Columns R "STATS (live)", S "Count", T "Priority (not yet applied)", U "Needs your answer" are a DASHBOARD, not per-row scratch space. NEVER write research notes there. (2026-10-20 incident: rows 2-15 of S/T/U were overwritten with research notes by mistake and could not be recovered from the API; user asked to restore via Sheets Version History.)
- One cell write per row via the Name Box, not a multi-line paste starting with blank lines — a multi-line paste that starts with empty rows was observed to drop a leading blank line and shift every subsequent row up by one. If a multi-row paste must be used, verify immediately afterward by reading back 2-3 known rows before moving on.

## People-finding steps, LinkedIn first (user, 2026-10-20)
For every company, in this order: (1) find the company's LinkedIn page (column F; verify against the company site); (2) open the company page and its People tab (logged-in LinkedIn, profiles only, never Jobs); (3) pick the relevant people there (founders/CEO, CTO/head of eng, hiring manager, HR/recruiter, senior dev, team members) and record each profile URL and live title; (4) only if the company page or People tab does not show them, search the individual person's profile (linkedin.com/search/results/people/?keywords=<name> <company>). Then add emails (published, else guessed from the real domain), GitHub, and draft one email per person. Sheet row number = index in the parsed gviz CSV + 1 (gviz keeps blank middle rows); always verify by reading column A of the target row before writing.

## One combined email per company (user, 2026-10-20)
- For each company, write ONE email with the same body and put ALL the found people in the To line (comma separated), greeting "Hi <first names>," or "Hi team,". Do not make a separate draft per person. The user sends that one email to everyone at once (Claude still never sends unless a named batch is authorized). Earlier per-person drafts (Trelium 5, HUD 6, Respan 3) stay as they are unless the user asks to consolidate.
- URL method that saves: `?fs=1&tf=cm&to=a%40x.com%2Cb%40x.com&su=...&body=...`, wait 10 s, click body (700,450), cmd+End, type one space, wait 10 s, navigate with force:true, then verify with a Gmail search.

## External job portal link per company (user, 2026-10-20)
- For every company, web-search and record the company's own job portal / application link (careers page or ATS: Ashby, Greenhouse, Lever, Workable, company /careers) in sheet column I "External Carier Portal to Apply", plus any contact details found on that page (careers/jobs/hiring email, recruiter name). Use the real role URL when it exists, else the careers page. If none, write "none found (checked: site, ATS search, web search)". Do not apply on workatastartup.com (see that rule); the external link is for the user to apply or for Claude to apply on the company's own form under the external-application rule.

## GitHub / open-source search PAUSED (user, 2026-10-20)
- Drop the GitHub org / open-source (proof-of-skill) search for now: do not run GitHub API lookups and do not fill column G "Open Source" for new companies. Overrides the "GitHub procedure" and "Open-source / proof-of-skill check" bullets above until the user turns it back on. Existing column G values stay.

## ONE email per company, MANY recipients on it (user, 2026-10-21; reinforces the 2026-10-20 combined-email rule)
- For every company create exactly ONE email (one draft, one thread) and put ALL found people of that company on that single email in the To line (comma separated; use Cc only if the user asks). Never create a separate draft per person, and never send several emails to one company.
- Same subject and same body for everyone on that email; greeting names all recipients ("Hi Abhimanyu, Ritanshu and Kamran," or "Hi team,"). Role- and stack-specific content is for the company, not per person.
- The existing per-person drafts (Trelium 5, HUD 6, Respan 3) violate this rule; consolidate them into one draft per company when the user says so.
- Sending (only when the user authorizes a named batch): one send per company, so the 3-minute spacing and daily caps count companies, not people.

## Recipients go in To, never Cc (user, 2026-10-21)
- For the one email per company, put EVERY recipient (all found people) in the **To** field, comma separated. Never use Cc or Bcc. Greeting names all recipients or "Hi team,". One draft, one thread per company; drafts only, never sent without a named-batch authorization.
- Recipient addresses come from sheet columns B, C and D (guessed ones marked "(guessed)", published ones first). Use the URL method `?fs=1&tf=cm&to=a%40x.com%2Cb%40x.com&su=...&body=...`.

## Companies with no email: check the posting itself (user, 2026-10-21)
- For every company whose row has NO email in B, C or D (and any row with only a generic info@/hello@ address), open the actual job posting (Wellfound, YC, a16z, ATS or the company's careers page) and read it end to end for a contact: "apply at / email us / send your CV to" lines, recruiter or hiring-manager names, footer and company-page contacts, linked founder profiles. Also check the company site (contact, about, team, careers, press) and the company's LinkedIn page and People tab.
- Record what the posting says in column I (notes): the hiring contact, the apply method (email, form, ATS), and whether it is remote and open to India. If an email or a named person is found, add it to B/C/D (published first; otherwise `firstname@domain` marked "(guessed)") and the person to column E.
- If the posting names no contact, say so in column N as `Hold: no contact in posting (checked: posting, site, LinkedIn)` and list the company in the report. Never leave such a row silently empty.

## Draft message variants and the "not in Gmail" check (user, 2026-10-21)
- Truth source for who has been contacted is Gmail (Drafts and Sent, read via `view=pt` per thread, account u/1 = <EMAIL>), never the sheet. An address counts as covered only if it appears in a draft's To or a sent message's To.
- One email per company, all NOT-yet-covered people of that company in To (never Cc). Three variants, all in the v2 human style (no numbers, one resume link, no India or hours unless asked):
  1. **New company (no address covered):** standard v2 body, greeting names every recipient or "Hi team,".
  2. **Partly covered (some people already have a draft or were emailed):** same body, but opening line adds "I also wrote to <covered first name(s)> about the same role, so I wanted to reach you directly too." Recipients are only the uncovered people. Never re-send to a covered address.
  3. **Follow-up (5 days after a send, no reply):** 3-line nudge on the same thread: role, one new line of relevant work, ask for a short chat.
- Subject for every variant: `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`. Log each created draft in column N as `Drafted <date> (<variant>; To: <n> people)`.

## /live-jobs command (user, 2026-10-22)
- `.claude/commands/live-jobs.md` pulls the newest postings (real links and details) from Wellfound, a16z and YC Work at a Startup (read only), dedupes against the sheet, and logs passing leads in the next free row (A:N, M = `find-jobs agent`).
- Eligibility is deliberately broader than "remote India": India, worldwide/anywhere/everywhere, Asia/APAC or Asian-timezone, and overseas companies hiring across regions. Reject US-only, US/Canada-only, LATAM-only, EU-residency, work-pass-required (e.g. Singapore EP), clearance/ITAR. Convert INR lakh pay to USD before applying the $35k floor.
- It never applies, emails or drafts. Next step for chosen leads is `/cold B <link>`.

## a16z: open every company, then contacts and drafts (user, 2026-10-23; overrides "load all jobs and check them" scans)
- Use the a16z board with the filter on (remote work arrangement; role families Software Engineer, data/ML, DevOps/infra). Do not just skim the job list. **Open each company page** (jobs.a16z.com/jobs/<company>), read ALL of its open jobs, and vet each against the filters (remote, India/worldwide/APAC/overseas-friendly, size up to 1000 for a16z, pay floor, role fit). The company's own ATS board (Ashby, Greenhouse, Lever) is the source of truth for location, pay and description.
- For every company that has at least one passing job: (1) log each passing job as a row in the Hunting sheet; (2) find ALL relevant people for that role, not a sample: CEO/founders, CTO, hiring manager (head of the team the role sits in), HR/recruiter/talent, a technical lead or senior engineer on that team, plus any team member (TM) in the same function; (3) for each person capture name, role, LinkedIn profile URL and email (published first; else `firstname@domain` marked "(guessed)"), per the "Contacts for EVERY row" rules; (4) write the people into columns B/C/D (emails) and E (names, roles, LinkedIn) and company LinkedIn into F; (5) create ONE Gmail draft for the company with every recipient in To (never Cc), using the v2 human style and the role-specific stack lines. Drafts only; the user sends.
- Companies are processed one at a time and logged in the ledger (`live_jobs_ledger.md`) as DONE only when the rows, contacts and draft all exist, or as REJECTED with the first failed rule, or HOLD with what is missing.

## Every sheet row must carry the full people set (user, 2026-10-23)
When a row is added to the Hunting sheet (Sheet2), fill all of this in the same pass, never "later":
- **People, by role** (every one that exists, in this order): CEO/founder, CTO, HR/recruiter/talent, hiring manager (HM), team lead (TL), project/product lead (PL), plus other relevant people (senior dev, team member). Write them in column E as `Name (role): <linkedin.com/in/... or "LinkedIn not found">`, separated by " | ". Check Wellfound People and "Meet your team", the company site, press pages and LinkedIn profiles; never invent a person.
- **Emails** in B, C and D: published first, otherwise `firstname@<real domain>` marked "(guessed)". The domain must come from the company's own site.
- **Company LinkedIn** in F, **company website** in H, **careers/ATS link** in I, follow-up count K = 0, follow-up date L = +5 days, M = who added it, N = status.
- A role you could not find after checking the sources is written as `not found (checked: <sources>)`, never left blank.
- **Drafts only for now:** one Gmail draft per company with everyone in To. Never send unless the user names a batch.

## HARD GATE for every sheet row (user, 2026-10-23, after rows were added without people)
A job posting is NOT "added" and must NOT be applied to or reported as done until its row has ALL of the following. No placeholders like "research pending", "people not researched" or blank cells. If a field truly cannot be found, write `not found (checked: <sources>)`.
1. **People, one per role** in column E as `Name (role): <linkedin.com/in/... or "LinkedIn not found">`: CEO/founder, CTO, HR/recruiter/talent, hiring manager (HM), team lead (TL), project/product lead (PL), plus other relevant people. Look them up in this order: company LinkedIn page and its People tab (logged-in, profiles only), Wellfound People / "Meet your team", YC or a16z page, company site, web search.
2. **Emails** in B, C, D for EVERY person found: published first, otherwise `firstname@<real company domain>` marked "(guessed)".
3. **Company LinkedIn** in F, **website** in H, **careers/ATS or job link** in I, follow-up count K = 0, follow-up date L = +5 days, added-by M, status N.
4. **One Gmail draft per company** with ALL those people in To (never Cc), role- and stack-specific, v2 human style. Row N says `Drafted <date> (To: n people)`.
5. **Order of work for each posting:** (a) vet it, (b) find the people and fill the row, (c) apply, (d) make the single draft, (e) update column N. Do not apply first and "fill later".
6. Before saying a batch is done, re-read the sheet and check every new row has B, C or D, E, F, H filled. List any row that fails, and fix it in the same turn.

## Finish before you start (user, 2026-10-23)
- **Do not apply to any new job until every row I have already applied to is complete** (people by role with LinkedIn, emails for each, company LinkedIn, website, job link, follow-up date, status, and one Gmail draft with all recipients in To).
- Before each new application, scan the sheet for rows marked Applied or Found that fail the HARD GATE and finish those first. Report the list at the start of every run.
- The only exception is when the user explicitly says "apply to <named job>" in that message.

## Never run in parallel (user, 2026-10-23)
- Do NOT run agents, workflows, background tasks or research jobs in parallel. Work on ONE company or ONE task at a time, finish it (row filled, people found, draft made), then start the next.
- Do not launch sub-agents or workflows unless the user explicitly asks for one, and then only a single one at a time.
- This applies to browser work, web research, sheet writes and Gmail drafts alike.

## LinkedIn networking mode (user, 2026-10-26)
- Mode C in `.claude/commands/linkedin-reach.md` (input `network`): networking comments, NOT job-related (overrides the job-related rule for this mode only). Target 500 comments = 3 different posts per person x 167 founders/CEOs/CTOs who might offer jobs in future. One person at a time, long task, resume from the Sheet3 count.
- Comments are short, specific to the post, truthful, no pitch, no numbers, no contact details. Connection request without note by default. Log each person in Sheet3 (A username, B company, C date, D `networking: 3 comments ...`). Human pace, stop at any LinkedIn warning or CAPTCHA.

## Do not stop until blocked (user, 2026-10-26)
- When the user says "go ahead" with a list of people or companies (for example LinkedIn networking, Mode C), work through the WHOLE list without stopping, asking, or ending the turn with a status report. Stop ONLY when a CAPTCHA appears, LinkedIn shows a warning or restriction, or the account is blocked. Skipping an unusable person (left company, no posts, India-based) is not a reason to stop: log it and move to the next person.
- Do not ask for confirmation on wording, thresholds or order mid-run; use the rules already in the skill and report at the end or at a block. Human pace still applies (20+ seconds between comments, one person at a time, no parallel work).

## Hacker News "Who is hiring?" leads (user, 2026-10-26)
- Skill: `.claude/commands/hn-hiring.md` (`/hn-hiring`). Default window: last 3 weeks of the newest "Ask HN: Who is hiring?" thread (https://news.ycombinator.com/submitted?id=whoishiring), read via Algolia (`hn.algolia.com/api/v1/items/<id>`). Same job filters as everywhere else (remote, India/worldwide/APAC-friendly, staff/senior/lead/founding, size up to 200, no India-based companies, no agencies or commission-only).
- Best place to reach them, in order: (1) email the contact given in the post (follow its subject line; Gmail draft only, one combined email per company); (2) a short reply under their HN comment from the user's own account (ask first); (3) the company ATS/careers form through the normal UI; (4) LinkedIn last, after the daily comment limit resets and earlier comments are verified.
- Show the user the lead table first (company, role, date, region, pay, contact, fit, flags) before drafting; then take chosen leads through the full row + draft flow one at a time.
- HN target (user, 2026-10-27): work through at least 50 qualifying HN postings (distinct companies; see section 3 of `.claude/commands/hn-hiring.md`), walking back thread by thread until 50 qualify. Ledger: `hn_leads_ledger.md`. Report progress as `HN qualifying: n/50`.
- HN level rule (user, 2026-10-27): for Hacker News leads ONLY, all engineer levels are allowed (not just staff/senior/lead/founding). Other filters stay (remote, India/worldwide/APAC-open, size <= 200, not India-based, pay floor, not agency). Enveritas and Mastra are re-opened under this rule.

## Always give my opinion (user, 2026-10-27)
- I am the user's assistant and helper, so in every report and at every decision point I state my own opinion and a recommendation (what I would do and why, with the main risk), not only facts or options. Keep it to one or two lines, clearly labelled "My opinion:". The user decides; I still follow all rules above.
- Keep working through the whole list without stopping. Items that need a user-only answer (CAPTCHA, an opinion on a page I cannot read, phone/visa questions) are marked HOLD in the ledger and I move on to the next company.

## Summaries and project answers on forms (user, 2026-10-27)
- When a form or email asks for a summary, "projects you're proud of" or similar, I may draw on the part-time startup work: Context.dev (LLM web extraction, Playwright), Kipps.AI (RAG voice agents, LangGraph) and Lokuma (MCP servers for coding agents), tied to the company's context. No numbers, truthful, facts from the resumes only.
- Send authorization (user, 2026-10-27, "please send them now"): the Supero and Lucia emails were authorized; Supero sent 2026-10-27. Spacing of 3+ minutes between sends still applies.

## Always fill application forms myself (user, 2026-10-27)
- The user will never fill form answers. I write every field and every free-text answer myself (from the resumes, Context.dev/Kipps.AI/Lokuma, no numbers, truthful), then submit through the normal UI, without waiting for the user. This includes forms that say LLM-written answers are disqualified (Kadoa); I mention that risk once in the report, then proceed as instructed.
- Still hold only for: CAPTCHAs, passwords/accounts, visa/work-authorization conflicts, salary history, and facts I cannot verify (for example MixRank's age/first-language questions: answer only what the user has stated).

## Maximum effort on applications, but never bypass bot checks (user, 2026-10-27)
- The user wants to beat the competition: fill every application fully and strongly, with the best truthful answers, without waiting for approval or asking for fields.
- Hard limit that stays regardless of instruction: I never solve, pass or bypass CAPTCHAs, "I am not a robot" gates, or other bot-detection (including pages that ask for a phrase to be typed back), and I do not claim facts I cannot verify. When a form has such a gate, I fill everything else, leave it unsubmitted, and mark HOLD with the exact step for the user (about one minute of their time).

## Follow the user's instructions exactly (user, 2026-10-27/28)
- When the user states an instruction, I do it as stated. I do not substitute my own judgment, shrink the scope, stop early, or replace the method with my preference. My opinion goes in the "My opinion:" line only, after the work is done.
- Only the hard safety limits override this (never bypass CAPTCHAs/bot checks, never enter passwords or create accounts, never send unless authorized, truthfulness). Nothing else.
- LinkedIn networking (Mode C): keep going until the stated target is reached (60 people x 3 comments today, plus more comments on previous people). No connection-request notes (user, 2026-10-28: "you don't need to send notes"); connection requests, if sent, are plain.

## LinkedIn connect skill (user, 2026-10-29)
- Skill: `.claude/commands/linkedin-connect.md` (`/linkedin-connect`). Sends plain connection requests to Sheet3 people marked `-` in column E (CEOs/CTOs first, then founders), verifies them in the sent-invitations list, and logs `Sent plain YYYY-MM-DD` in column E; comment mode logs in column F.
- Free-note allowance is used up until about 2026-11-01 ("You're out of free custom notes"); plain requests only until then. Never buy Premium, never withdraw and resend. About 75 plain requests were sent on 2026-10-28/29 with no LinkedIn warning; stop at the first warning.

## Write story and essay answers myself, no approval (user, 2026-10-30)
- When an application form asks for stories, essays, "tell us about a time", projects or similar free text, I write the answer myself without asking the user for approval or for the story. I build it from real facts in the resumes, this CLAUDE.md and the user's projects (Atlassian work, Context.dev, Kipps.AI, Lokuma, CIKM 2023 paper, open-source repos). No invented employers, metrics, products, or personal facts; no numbers in outreach (rule 7) unless a form specifically asks for a measurable result, and then only resume-backed figures.
- Still HOLD (do not guess) only for: age, first language, demographic or legal declarations, visa/work-authorization conflicts, salary history, and CAPTCHAs/bot checks.
- Tab hygiene: after a form is submitted (or decided as skipped), close its tab.

## Never stop on application forms; fill and submit (user, 2026-10-30, stated emphatically)
- Do not treat any application form as a reason to stop, hold, ask, or hand work back. Fill every field myself (resume upload, location, availability, eligibility, essays, stories, questions), then submit, without waiting for approval. Do not lecture or over-explain; do the work and report in a few lines.
- Experience-year gaps (for example a posting asking 7+ years): still apply, answer truthfully, and lean on real strengths.
- The only fields I leave for the user are a typed-phrase gate or CAPTCHA/bot check ("type I am not a robot", "verify you are human"): I cannot pass bot checks even on request. If a form has one and it is required, I fill and submit everything else I can, and list the single gate field in one line for the user.
- Personal facts the user has never given (age, first language, pronouns) are left blank or "Prefer not to say" when optional, never invented.

## LinkedIn follower cap for outreach (user, 2026-10-31)
- For now, do NOT reach out (connection requests, comments or notes) to LinkedIn people who have MORE than 5,000 followers. Focus only on people with 5,000 followers or fewer. Check the follower count on the profile card ("<n> followers") before any request or comment.
- Applies to Sheet3 people and the Sheet2 pool alike. If the count is not shown, treat the person as 5,000 or fewer only when the profile shows a connection count like "500+ connections" with no larger follower number; otherwise skip and log `Skipped: over 5k followers`.
- Skipped people are logged in Sheet3 with `Skipped: over 5k followers (<n>)`. Already-sent requests and comments are not undone.
- Applies until the user lifts it in chat.

## US networking mode: people who are NOT hiring (user, 2026-10-31)
- Target US-based founders, CEOs and CTOs (profile location in the United States), with 5,000 or fewer followers, who are NOT posting a job. Goal: build a better network, not apply. Comment on their own recent posts (specific, truthful, no pitch, no numbers) and send a plain connection request. Skip hiring posts, recruiters and aggregators for this mode.
- LinkedIn people search is capped (monthly profile-search limit, only 3 results shown) and I do not buy Premium. Find people through content search (non-hiring founder/CTO posts), company People tabs and Sheet2, then check location and follower count on the profile before acting.
- Log each person in Sheet3 (A handle, B company with name and role, C date, D comments, E connection, F `-`). Check the dialog names the right person before sending.

## Production stories on forms: build them myself, tailored per role (user, 2026-10-31)
- When a form or email asks for a software story ("what have you built in production", "tell us about a project", "a hard bug", "a system you owned"), I write it myself without asking. Source: the resumes, the Atlassian work, and the part-time work (Context.dev, Kipps.AI, Lokuma), plus the open-source repos and the CIKM 2023 paper. I may use the web only to understand the company's product and stack so the story fits it, never to invent my experience.
- Tailor each story to the role family and the posting's stack: DevOps/SRE (Kubernetes, Terraform, ArgoCD, GitHub Actions, OpenTelemetry/Datadog, reliability), AI (LLM extraction with Playwright, RAG voice agents on LangGraph, MCP servers, evals), full stack, frontend, backend (Python, Go, Java, TypeScript, Kafka, Spark, PostgreSQL, Redis, FastAPI, Node, React/Next.js). Pick the real project that best matches, name the problem, my role, the design choices, what shipped and how it ran in production.
- Truthfulness limit: the same real work can be told with the emphasis and the language it was actually built in. Do NOT present it as built in a language or tool that is not on my resumes. For a stack I haven't used (for example Rust, Ruby, .NET, Swift), say I am ramping up on it and connect it to the closest real experience.
- No numbers in outreach (rule 7); on a form that explicitly asks for a measurable result, use only resume-backed figures. Fill the answer directly, submit, and report in a few lines.
- Bot checks, CAPTCHAs and "I am not a robot" gates are still left for the user (hard limit).

## Email conversion tracking, metrics and sending capacity (user, 2026-10-31)
- Spec file: `email_tracking_spec_2026-10-31.md`. Metrics live in the Hunting sheet: tab `Metrics` (dashboard) and Sheet2 columns `Stage` and `Stage date`. Update them at the start of every session (check Sent, mailer-daemon bounces and replies first) and after every send batch.
- **Tier 1 (conversion):** positive-reply rate = positive replies / delivered companies; reply rate = human replies / delivered companies; interview rate = interviews / delivered companies.
- **Tier 2 (sending health):** delivery rate = delivered / sent; bounce rate by address source (published vs guessed), limit under 5% of addresses; redirect rate = "apply via portal" replies / replies.
- **Tier 3 (finer signals):** follow-up lift = replies after follow-up 1 / follow-ups sent; resume views per company (Drive activity, signed-in viewers only); forwarded (inferred) = a reply or Drive viewer from a person who was not emailed.
- **Stage values (one per company row):** Not sent, Sent, Delivered, Bounced (all), Replied: auto, Replied: acknowledged, Replied: redirect, Replied: positive, Forwarded (inferred), Applied via portal, Call, Interview, Offer, Rejected, Closed (role), Skipped. "Positive" is strict: asks for a call, forwards me, shares my resume, or names a next step.
- Open rate and forward rate cannot be measured reliably (Apple Mail and the Gmail image proxy preload tracking pixels; no email system reports forwards). Do not add pixels or tracked links to outreach unless the user approves a named test group; clicks are the stronger signal than opens. Replies stay the main signal.
- **Volume target (user): 50 to 100 emails a day.** Reach it with several separately authenticated sending mailboxes, not by raising one mailbox. The per-mailbox limits in "Human-pace and account-safety rules" still apply (start at 15 a day, at most 25 a day per mailbox, 3 minutes or more between sends, bounce rate under 5%). The current single Gmail account stays at those limits until more mailboxes have finished warm-up. Never use guessed addresses in the first 7 days of a new mailbox.
- New mailbox warm-up (about 4 weeks): own domain with SPF, DKIM and DMARC set up and checked; days 1-7 only real conversations at 5 a day or fewer; weeks 2-3 add 5 a day each week; week 4 reach 15 to 25 a day. Increase only while bounce rate stays under 5% and no "message blocked" appears; pause a mailbox for a day at 2 bounces. Sender name is always Rahul Jha, real identity, truthful signature. Claude never creates mailboxes or accounts; the user does that.
- Rows marked `Skipped 2026-10-31: role closed` or `company declined by email` get no follow-up. A role is verified closed from the ATS posting (Ashby, Greenhouse or Lever API 404), a 404 job page, or Wellfound's "listing no longer available".

## Standard follow-up email (user, 2026-10-31)
- Format is defined in `.claude/commands/cold.md` Template D: subject `Re: <original subject>`, To = delivered addresses of the first email only, greeting with first names or "team", opener naming the role, one real work fact for the role family, short ask, one resume link on its own line, Best / Rahul Jha / LinkedIn. No numbers, no India or hours, no praise.
- Eligible: no reply, role verified open, not Skipped/Closed/Rejected, first email at least 5 days ago. One per company. First batch: `followup1_drafts_2026-10-31.csv` (87 companies, send plan Nov 2-6, 17-18 a day, 3+ minutes apart, published addresses first). The user sends.
- Gmail draft save for these URL-prefilled compose windows: Escape alone did NOT save a draft on 2026-10-31. The user approved making the drafts, so click a blank body area after a screenshot confirms the layout, type one space, wait for autosave, verify in Drafts. Never touch Send, Schedule send or Cmd/Ctrl+Enter.

## No LinkedIn outreach to people in India or Pakistan (user, 2026-11-01)
- Never reach out to individual founders, CEOs, CTOs or any person whose profile location is in India or Pakistan: no comments, no connection requests, no notes, no messages. Check the location line on the profile card BEFORE the first comment or request, and skip the person with `Skipped: India` or `Skipped: Pakistan` in Sheet3 column D.
- Applies to every LinkedIn mode (A, B, C, US networking, connect) and to new people found from any source. Existing rows are not undone.

## HN monthly sweep rule (user, 2026-11-02)
- Skill: `.claude/commands/hn-monthly.md` (`/hn-monthly <month|next>`). Goes month by month through "Ask HN: Who is hiring?", collects every UNIQUE listing (one per company + role family), and adds each one to the Hunting sheet (Sheet2, Added By `hn-monthly`), then opens the website and LinkedIn and finds the people (CEO, CTO, HR, hiring manager, team lead) with LinkedIn and the company email pattern.
- **Three verification layers for every listing:** (1) the post itself, (2) the company site and the live posting (still open, remote policy, size, not India-based), (3) requirement-by-requirement fit against the resumes with a match %. Each layer is written in the row notes (column N).
- **Stack gaps never block a listing:** if it needs Go, Rust, Java, .NET, Ruby or any other stack I do not have, still add it and note `Gap: <tech> (ramping up; closest: ...)`. A match of 50% or more is added; below 50% is also added when every hard filter passed. Never claim a skill that is not on the resumes.
- **A month is PASSED only when** every unique listing is added, rejected with a written layer and reason, or already in the sheet; every added row has layers 1-3 notes and its people/email set (or `Hold: contacts not found (checked: ...)`); and the counts add up. Record it in the Hunting sheet tab `Metrics`, block `HN MONTHS`, Status `PASSED <date>`.
- The 2026-11-02 keyword scan (Oct to May 2026, 9 leads added) is NOT a passed month; those months get the full three layers via this skill. Read-only on HN; no applying, emailing or LinkedIn outreach inside the skill.

## Notice period and 10+ year roles (user, 2026-11-02)
- **Availability / notice period:** when a post, form or person asks for a notice period or start date, answer "available to start soon" (immediately if they need a date). No need to ask the user each time.
- **10+ years of experience asked:** still apply and draft; never skip or drop a listing for the years ask. Answer truthfully (no invented years, no numbers in outreach), lean on the real work, and note the gap in the row notes. Some of those companies may be open to hiring regardless of the years ask.
- HN leftovers (user, 2026-11-02): every HN listing that was IGNORED, PENDING or HOLD only for lack of names, a hidden contact or a years ask now gets a Gmail draft (to the post's published address plus any verified people) and a sheet row. Hard stops stay: closed role, on-site, region-locked, size over 200, agency, India-based company, equity-only below the pay floor.

## Standing send authorization for drafts (user, 2026-11-04)
- The user said "keep sending", "send 20+ email today" and to bring Gmail Drafts down to about 100. Standing authorization: keep sending the prepared drafts (follow-up plan `followup1_drafts_2026-10-31.csv` in send_day order, then `followup2_drafts_2026-11-01.csv`, then unsent first emails) without asking again each time, until the user says stop.
- Per send: open the draft with `in:drafts to:<domain>`, screenshot-verify To, Subject and body, click Send, confirm the "Message sent" toast (or the draft vanishing from Drafts plus a Sent entry), wait 3+ minutes before the next send (background `sleep`, never rapid-fire). Never use scripted clicks on the Drafts list.
- Daily count stays at 25 sends per day unless the user names a higher number; keep reporting progress (sent count, drafts left) after every send and list new bounces from `from:mailer-daemon`. Bounce notices do not stop the run (user override), but are logged to the sheet (Z/Stage) and the ledger.
- Drafts target: about 100 left. Hold back Camu (human reply, handle by hand), Scarce Labs, CyberAtlas and Interview Resources.

## Stop reaching companies with offices in India (user, 2026-11-04)
- For now, do NOT email, follow up, apply to, or LinkedIn-reach any Indian company OR any company that has an office in India (Bengaluru, Mumbai, Delhi/Gurugram, Pune, Hyderabad, Chennai, etc.), even if it is a US/overseas company. Be specific: only companies with no India office are contacted.
- Before every send, check the company's own site (about/careers/locations), its LinkedIn company page locations and the job post for an India office. If one exists, skip the send, leave the draft in place (do not delete), and mark the sheet row `Hold: India office (<city>, source)`. If unclear, check once more with a web search; if still unclear, send only when no India location is listed anywhere.
- Applies to follow-ups, first emails, Wellfound/ATS applications and LinkedIn outreach. Already-sent emails are not undone. Overrides the earlier rule that only India-HQ companies are skipped, until the user lifts it.

## Never message Tax Pilot (user, 2026-11-04)
- NEVER send LinkedIn messages (or any DM) to anyone at Tax Pilot (thetaxpilot.com), including Will Hudson (hudsonwilliam), Nick Wallman, Jake Spear and Mike Demerjian. Skip them in every message run and log `Skipped: no messages to Tax Pilot (user rule)`. Existing comments and connection requests are not undone.

## Remote job boards: Remotive, We Work Remotely, Arc.dev (user, 2026-11-04)
- Skill: `.claude/commands/remote-boards.md` (`/remote-boards [remotive|wwr|arc|all]`). Fetch jobs from these three boards (Remotive API, We Work Remotely RSS, Arc.dev in the logged-in tab), dedupe against Sheet2, vet each on the real page (remote, India/worldwide-open, size 1-200, no India office, pay floor, not agency), log passing jobs in Sheet2 with Added By `remote-boards`, then people/emails and one draft per company.
- Read-only on the boards: never use their Apply buttons (Arc "Apply now" goes through LinkedIn Jobs/Arc forms); reach people by email or the company's own site. Remotive's terms: personal search only, link back, never republish their jobs elsewhere. Arc login/CAPTCHA is the user's job (HOLD).
- Ledger: `remote_boards_ledger.md`. Level filter stays Staff/Senior/Lead/Founding unless the user lifts it for these boards.

## Arc.dev: filter India and apply on Arc (user, 2026-11-04; supersedes the "never use Arc Apply" line above)
- URL: https://arc.dev/dashboard/d/full-time-jobs/browse (user is logged in). Filters > Location = India > Apply. Then apply on Arc's own dashboard ("Fast apply"/Apply) to every engineering job that passes the filters (remote, size <= 200, no India office, not agency, not product/design/sales). Matching resume family, role- and stack-specific note, no numbers, no India/hours mention, notice = "available to start soon".
- Still never use LinkedIn Jobs/Easy Apply: if Arc's Apply redirects to LinkedIn Jobs or a form needing a CAPTCHA/password, HOLD for the user. Log each application in Sheet2 (Added By `remote-boards`, status `Applied <date> (Arc)`) and in `remote_boards_ledger.md`; check the Arc "Applied" tab.
- Level filter for Arc: Staff/Senior/Lead/Founding unless the user lifts it. Skill: `.claude/commands/remote-boards.md`.

## We Work Remotely flow, free account (user, 2026-11-04)
- Listing URL: https://weworkremotely.com/?categories%5B%5D=2&categories%5B%5D=17&categories%5B%5D=18&categories%5B%5D=6 (read as a free user, no signup or payment). For each job: find the company's real external hiring page by web search, check the company website and LinkedIn (company page, people, any post about the role), fill the external application if one is found (per the external-application rules), find ALL people (CEO, CTO, HM, HR, TL, team members) with LinkedIn and emails, log one Sheet2 row, and create ONE Gmail draft per company with everyone in To. Full steps: "WWR flow" in `.claude/commands/remote-boards.md`. Drafts only here; sending follows the standing send authorization. India-office, size and level rules still apply.

## Sheet2 column shift (2026-11-04)
- The user inserted a new column K "Response Recived" in Sheet2. Letters from K onward moved one to the right. Current layout: J Linkedin, K Response Recived, L Followup Count, M Followup Date, N Added By, O Application Status, P Email Sent, Q Email Failed, R Stage, S Stage date, then the dashboard columns; the follow-up status column (was Z) is now AA. Always read the header row from the gviz CSV before writing, and write by header name, not by remembered letters.

## Job boards: browser only, no scripts or CSVs (user, 2026-11-04)
- For Arc.dev, We Work Remotely, RemoteOK and Remotive work only through the Chrome browser by hand. Do not create scripts, CSV or JSON job files, or use curl/RSS/API pulls for them. Remotive's blurred (members-only) company names and apply links are never unmasked or extracted; Remotive's membership is the user's own decision. Notes live in `remote_boards_ledger.md` and the Hunting sheet. Skill: `.claude/commands/remote-boards.md`.

## Third accidental send (2026-11-04): the "click body, type a space" draft-save step is unsafe
- While building outreach drafts (user said "build email, linkedin outreach msg, nothing else"), the Salesforge compose (to frank@salesforge.ai, daniel@salesforge.ai, guessed addresses) showed a "Message sent" toast after the click-body + type-space step; the Undo link had already expired. The same step saved Ritual, Toggl and garden3d correctly, so the click sometimes does not land in the editable body and the space then hits the focused Send button.
- From now on: do NOT use "click body + type space" to save a draft. Leave URL-prefilled compose windows for the user to close, or create drafts only through a method that never focuses Send (for example, let the user press the compose window's X, which autosaves). Tell the user immediately when a "Message sent" toast appears.

## Target websites (user, 2026-11-04): where we look, what we do there, what is barred
Work in the Chrome browser by hand (no scripts, no CSV/JSON job files). One site at a time.

| Site | Use now | Apply / reach out | Limits |
|---|---|---|---|
| arc.dev (full-time browse, Location = India) | PRIMARY. Check daily. | Fast apply with a role-specific note; log in Sheet2 | Company name is hidden on Arc Exclusive roles; skip "Perm - India" and India-employer roles; Staff/Senior only unless lifted |
| weworkremotely.com (user's 4-category listing URL) | Read listings and job pages | Apply Now is Pro-only: apply only on the company's own posting found by web search; email/LinkedIn outreach otherwise | Read the description for time-zone limits; skip agencies and companies over 200 |
| remoteok.com (`remote-dev+engineer-jobs?location=IN,region_AS,Worldwide`) | Read listings, last ~30 days only | Apply is a paid-plan page: same company-site route; never use the URL hidden in the paywall page | Many rows are stale or non-engineering; "Worldwide" tags are often wrong (check the company's own post) |
| remotive.com (user's filtered URL) | Read the visible rows only | None from Remotive; company names/apply links are members-only | Never unmask or extract hidden fields; membership is the user's decision |
| news.ycombinator.com "Who is hiring?" | Monthly sweep (`/hn-monthly`) | Email the post's contact, ATS form, drafts only | Read only on HN |
| wellfound.com, ycombinator.com (read only), jobs.a16z.com | Existing rules apply | Per earlier Wellfound/a16z rules; NEVER apply on workatastartup.com | Size caps (200; a16z 1000) |
| Company career pages, Greenhouse/Ashby/Lever boards | Preferred place to apply once a company is identified | Fill every field myself; school "Other" when IIIT Allahabad is not listed | CAPTCHAs and passwords are the user's |
| Gmail (u/1, <EMAIL>) | Follow-ups and cold emails | Standing send authorization (3+ min apart, 25/day, verify each) | Never use the "click body + type space" draft-save step (third accidental send 2026-11-04) |
| LinkedIn | Posts and profiles only | Connection requests and comments per the LinkedIn rules | NEVER LinkedIn Jobs/Easy Apply (also blocks Salesforge-style "careers" buttons that open LinkedIn Jobs) |
| Candidates to test next | himalayas.app, workingnomads.com, jobgether.com, dynamitejobs.com, VC portfolio boards (Getro-style) | Test once: shows company name? Apply free? India/worldwide filter? | Add to this table only after the test |
Barred or skipped: LinkedIn Jobs, workatastartup.com apply, agencies and marketplaces (Toptal, Turing, Lemon.io, Proxify, A.Team, Braintrust, Cloudary-style placement firms), paid boards (FlexJobs, Remote100k), India-based employers and companies with an India office, companies over 200 people.
Hard filters on every site: remote; open to India or worldwide (read the post for time-zone and visa limits); size 1-200; no India office; engineering roles at Staff/Senior/Lead/Founding level (HN: all levels); apply at 30% match or more and always state gaps as "ramping up".

## Daily jobs skill, 3 finder agents per site (user, 2026-11-04)
- Skill: `.claude/commands/daily-jobs.md` (`/daily-jobs [sites] [target per site]`). The user asked for 3 agents working on the same site to find as many opportunities as possible. This is the ONLY exception to "Never run in parallel": three READ-ONLY finder agents per site (split by role family or page range). One writer (main session) does every sheet write, application, Gmail draft and LinkedIn text, one company at a time.
- Applies on Wellfound inside the platform (normal UI, 180-240 s apart, at most 10 a day, stop on first CAPTCHA/429), on Arc, and on company ATS forms; ONE Gmail draft per company with CEO, CTO, HM, HR and TL all in To; LinkedIn outreach text drafted, not sent; progress report per website at the end (`daily_report_<date>.md`, ledger `daily_jobs_ledger.md`).
- Finders never write, apply, email or message; if any site returns 429/403/CAPTCHA/login, all agents on it stop for the day.
- Update (user, 2026-11-04): the 3 finder agents per site run BACK TO BACK (A, B, C, then a cover pass), each given the earlier agents' results, never two in the browser at once. Every `/daily-jobs` run first audits ALL previous Sheet2 rows (any date) into buckets (never applied, applied-no-email, drafted-not-sent, follow-up due, incomplete, hold) and applies/drafts the ones not done. Live tracker `daily_progress_<date>.md` shows emails sent vs drafted and per-site progress.

## No new .md/.csv/.json files without approval (user, 2026-11-04)
- Never create a new `.md`, `.csv` or `.json` file (ledgers, reports, progress notes, outreach drafts) unless the user approves it in chat first. Put progress, ledgers and reports in the chat reply and in the Hunting sheet (tab Metrics, row notes). Editing existing files (CLAUDE.md, skills) when the user asks is fine. Overrides every earlier instruction that says to write a ledger or report file.

## Outreach map (user, 2026-11-04)
- ONE email per company with everyone (CEO/founder, CTO, hiring manager, HR, team lead, senior dev) in To. LinkedIn is individual: follow + comment on the company page's recent posts; CEO and CTO each get a connection request and up to 3 job-related comments on 3 different posts; HM, HR, TL are email-only unless the user asks. Skip India/Pakistan profiles and people over 5,000 followers; log in Sheet3. Details in `.claude/commands/daily-jobs.md` section 6.

## Sheet5 is now the OPEN-SOURCE REPO TRACKER (user, 2026-11-07; replaces the trace tab below)
- Sheet5 (gid 399625528) holds the open-source contribution targets, re-ranked 2026-11-07 (44 companies, A1:V45): A Final Rank, B Section (1 Apply + contribute now / 2 Contribute; roles US-only or single-region / 3 Watch / Excluded: India office), C Company, D Role Family, E Repo URL, F Stars, G Eligible openings (verified live), H Eligible roles, I Role links, J US-only/single-region roles, K Combined score (0.45 openings + 0.35 contribution-to-hire + 0.20 resume fit), L/M/N the three rankers' rank/score, O Why this rank, P People, Q Published emails, R Starter issue, S Careers/ATS, T PR status (Not started / Issue picked / In progress / PR opened / Merged / Closed), U Next step, V Checked date. Sort order: section first, then combined score. User rule 2026-11-07: keep ONLY companies with live engineering roles open to his region (section 1); companies with no engineering roles, or only US-only/single-region roles, are removed (rows 17-45 cleared, 15 companies remain). Tightened same day: keep ONLY companies that hire GLOBALLY (worldwide / all regions incl. APAC; small startups fine) AND merge real outside contributors (spot-checked). Multi-country lists without APAC, single-region, or US-benefits-only roles are removed. Result: Supabase, LiveKit, Railway, PostHog, Mastra (rows 2-6).
- Do NOT write daily-jobs traces here any more; traces go in the chat report. GitHub lookups are re-enabled for this tracker (overrides the 2026-10-20 pause for this purpose). Type ratios like 2/2 as text ('2/2) so Sheets does not turn them into dates.

## Trace tab (user, 2026-11-04) [retired 2026-11-07, see above]
- Traces live in the Hunting sheet tab `Sheet5` (gid 399625528), not in files: log table A:M (Date, Time, Site, Agent, Company, Role, Job URL, Action, Channel, People, Result/Status, Sheet2 Row, Notes) plus right-side blocks O1 Daily summary by site, O4 Backlog (all dates), O7 Emails (from Gmail). Append only, never overwrite. Skill: `.claude/commands/daily-jobs.md` section 7b.
- Standing site set (user, 2026-11-04): the Target websites list is the permanent set for `/daily-jobs`, not a one-day list. Finders keep running rounds per site until 2 consecutive rounds add nothing (max 8), then sweep the full set again on every run. Workflow script: `workflows/scripts/daily-jobs-finders-wf_*.js` in the session directory.

## Never stop in between + 3-agent clearance (user, 2026-11-04)
- During `/daily-jobs` do NOT stop, pause, ask or send a status report mid-run. Continue until every site is swept, every passing job is on the sheet with people/emails, applied where allowed, drafted (one email per company), `Sheet5` is updated, AND each site is CLEARED by 3 independent auditor agents (keyword, depth/recency, company-first lenses) that all find no relevant job left; a find restarts the audit. Only hard limits stop a site (CAPTCHA/bot check, login wall, 429/403, LinkedIn warning, unapprovable tool): name it, mark HOLD, continue with the other sites.
- Three passes per site (user, 2026-11-04): every site goes through pass 1 (breadth), pass 2 (depth) and pass 3 (clearance, repeated until all three auditor agents find nothing new), each pass run by agents A, B, C back to back. Skill: `.claude/commands/daily-jobs.md` section 2.
- YC added to the standing site set for `/daily-jobs` (user, 2026-11-04): workatastartup.com plus the ycombinator.com/companies hiring directory, READ ONLY (no Apply, no messages there); reach companies by founder email and the company's own site/ATS.
- ATS boards added to the standing site set for `/daily-jobs` (user, 2026-11-04): Greenhouse (job-boards.greenhouse.io / boards.greenhouse.io), Ashby (jobs.ashbyhq.com) and Lever (jobs.lever.co), searched with `site:` web queries and then read in the browser; applying on a company ATS form follows the external-application rules.
- Remotive removed from the `/daily-jobs` site set for now (user, 2026-11-04). Re-add only when the user says so.
- Two passes per site (user, 2026-11-04; replaces the three-pass rule): each site gets exactly 2 passes with ONE finder agent per pass (11 sites x 2 = 22 passes): pass 1 breadth, pass 2 depth and clearance. The 3-agent clearance is retired for now.

## Every application triggers outreach: draft email + LinkedIn (user, 2026-11-07)
- Whenever we apply for a job on ANY platform (Wellfound, Arc, company ATS/career page, email-to-apply, HN), the same pass must also produce: (1) the single Gmail draft for the company with all found people in To (never Cc; drafts only, saved by the safe method); and (2) LinkedIn outreach to the CEO/founder and CTO (and the hiring manager when found): a connection request with a note of at most 200 characters when personalised notes remain. 
- If a note cannot be sent (free-note allowance used up, "out of free custom notes", or the dialog has no note field), send the connection request plain and instead leave a COMMENT on one of the person's recent posts (the post must have 30 or fewer reactions+comments): 4-5 lines, no more, covering (a) who I am (most recently SDE II at Atlassian, owning production backend services and data pipelines; AI engineer on early teams: LLM extraction, RAG voice agents, MCP servers) and (b) the job I am looking for / applied for (exact role and stack, one real fit line). If the person has no suitable recent post, put the same 4-5 lines in the Gmail draft only and log `no post`.
- Comment rules stay: no numbers, no contact details, truthful, one comment per post. Skip people in India/Pakistan, people over 5,000 followers, Tax Pilot; never LinkedIn Jobs/Easy Apply. Human pace (20+ s apart), stop at any LinkedIn warning or CAPTCHA.
- Show the comment/note wording in chat before posting a batch unless the user has already authorized the batch. Log each action in Sheet3 (A handle, B company, C date, D comments, E connection `Sent plain`/`Sent with note`, F notes) and Sheet5.
- An application is not "done" until the draft exists and the LinkedIn step (note, or plain request + 4-5 line comment) is logged or marked HOLD with the reason.

## GOLDEN RULE: if a job post links to the company's own page, apply there (user, 2026-11-07)
- Whenever ANY job post, listing or board (Arc, WWR, RemoteOK, Wellfound, HN, a16z, YC, Greenhouse/Ashby/Lever, LinkedIn posts, newsletters, anything) gives a link, or we can extract one by reading the page or web search, that redirects to the company's own page (company careers page, its ATS posting, or its own apply form), we MUST apply there. Such a job is NEVER dropped, never left as "Found", and never skipped because the board's own Apply is paywalled, hidden or unavailable. This is the golden rule.
- Order of work: (1) read the post and look for the company/ATS/apply link (apply button URL, "apply at", linked careers page, ATS board); (2) if none is visible, web-search `"<company>" "<role>" careers` and the company's ATS (Greenhouse, Ashby, Lever, Workable, own /careers); (3) open that real posting, confirm it is open, then fill every field myself and submit through the normal UI (external-application rules, standard answers, role- and stack-specific text, no numbers); (4) log the real URL in column I and status `Applied <date> (<ATS>)`, plus the draft and LinkedIn step from the "Every application triggers outreach" rule.
- This rule overrides drop/skip reasons EXCEPT the hard stops: on-site or hybrid-only, explicit US citizenship/work-authorization requirement, company over the size cap, India-based company or India office, agency/marketplace, closed role (404 or "no longer available"), and the hard safety limits (CAPTCHA/bot check, login/password wall, account creation, never LinkedIn Jobs, never apply on workatastartup.com). It also overrides "company hidden" and "paywalled apply" as drop reasons: find the company by search and apply on its own page.
- A hard safety stop is not a drop: park the job as `Waiting on user: <CAPTCHA|login> at <site>` with the exact link, and keep it in the backlog until done. Never delete or silently abandon such a job; list it in every report until it is applied or hard-stopped.

## "What have you built in production" answers: lead with part-time + Atlassian + paper (user, 2026-11-07)
- ALWAYS apply (golden rule stays) and, whenever a form, email or comment asks what I have built in production or about my experience, answer from the strongest REAL material, written attractively (concrete problem, what I owned, design choices, what shipped, impact), tailored to the role family:
  - **Full Stack / backend roles:** lead with the part-time full-stack work: Kipps.AI (lead-management portal on Next.js, Node.js and WebSockets for voice and WhatsApp prospects; two-way CRM webhook sync with HubSpot and Salesforce), Context.dev (web extraction services in Node.js, Playwright and Go; Redis task queues with rate limiting and proxy rotation), Lokuma (integration layer exposing design tools to coding agents through MCP servers with strictly validated JSON-schema APIs); then Atlassian (production backend services and data pipelines other teams depend on).
  - **ML core / Data Scientist / AI roles:** lead with the ACM CIKM 2023 paper "Large Language Models as Zero-Shot Conversational Recommenders" (co-author) and the applied ML work (Context.dev LLM extraction and RAG, Kipps.AI RAG voice agents on LangGraph, Lokuma MCP tools with evaluation routines), then Atlassian ML-serving and data pipelines.
  - **Infra / DevOps / SRE:** lead with Atlassian (Kubernetes, Terraform, ArgoCD, GitHub Actions, OpenTelemetry/Datadog, Kafka pipelines), then part-time services in production.
- Make it attractive but TRUTHFUL: sharper verbs and outcomes, never new employers, titles, tools or numbers. In outreach and form answers still follow rule 7 (no numbers) unless a form explicitly asks for a measurable result, then use only resume-backed figures. Gaps are stated as "ramping up". Part-time work is described as part-time/contract with early teams.
- Resumes: the Full Stack resume (`full stack.tex`) lists Kipps.AI, Context.dev and Lokuma (Lokuma added 2026-11-07, facts and figures copied from the AI Engineer resume, reframed full-stack) as full-stack part-time work; the AI Engineer and Data Scientist resumes keep the research paper and the ML framing, and the paper stays prominent for ML-core applications. Compile check in Overleaf (2 pages) is still needed after this edit; no pdflatex is installed here.

## YC jobs flow from the user's open tabs (user, 2026-11-07)
- The user opens many YC job/company tabs (workatastartup.com and ycombinator.com). They must be in the Claude tab group for me to see them (a tab outside the group is invisible). Flow, one tab at a time: (1) list every YC tab with `tabs_context_mcp` and read each (title, company, role, location, pay); (2) filter on the real page: remote and open to India/worldwide/Asia (reject `Remote (US)`, `Remote (CA)`, on-site/city-only, Europe-only), company 1-200 people, no India office, engineering role at Staff/Senior/Lead/Founding level (founding and Member of Technical Staff count), pay top at or above about $35k a year, stack match 30%+; (3) for each passing job open the company page in a NEW tab for website, size, founders, LinkedIn; (4) add one Sheet2 row (Added By `yc-tabs`, status `Found`), find people and emails, make ONE Gmail draft per company; (5) apply on the company's own site or ATS if it links one (golden rule); NEVER click Apply or message on workatastartup.com; (6) close each tab when done and log in Sheet5. The `remote=only` URL filter is unreliable: many cards are US-only or on-site, so every card is vetted on its job page.
- YC standing URL (user, 2026-11-07): ALWAYS open this company list when checking YC jobs, and use its params as the default YC filter: https://www.workatastartup.com/companies?demographic=any&hasEquity=any&hasSalary=any&industry=any&interviewProcess=any&layout=list-compact&remote=only&role=eng&sortBy=created_desc&tab=any&usVisaNotRequired=any (remote only, engineering, newest first, compact list). Open each company from it in a new tab (read only, never Apply/message there), vet it, and add passing ones per the YC flow above.

## YC-only focus + verify the role is still open (user, 2026-11-07)
- When the user says "YC jobs", work ONLY on Work at a Startup / the YC directory. Do not run liveness checks, closes or sheet changes on Ashby/Greenhouse/Lever/Wellfound rows unless asked.
- For every relevant YC role: (1) open the company's own careers page / ATS posting and see whether the role is still listed; (2) check LinkedIn (company page posts, people profiles; never LinkedIn Jobs) for signs the role was filled (someone with that title recently joined, "we hired" posts); (3) verdict OPEN / FILLED-CLOSED / UNCLEAR with evidence and the real apply URL; (4) apply on the company's own page for OPEN ones (golden rule). Read-only until the verdict is in.
- YC directory API (found 2026-11-07, user asked to check through the page): the directory asks Algolia (`WaaSPublicCompanyJob_company_<sort>_production`, filters `(role:eng) AND (remote:only)`, 10 per page) for company IDs, then `POST /companies/fetch {ids:[10]}` for details. The page stops rendering at 87 of the 158 hits: the other 71 are companies marked hiring with NO job listed on YC (PostHog, RevenueCat, LiteLLM, GrowthBook, authzed, BuildBuddy, etc.). Reach them through their OWN career pages/ATS. Never print or store the Algolia key or CSRF token; the automatic permission check blocked reading them back once.

## Size cap lifted for now (user, 2026-11-07)
- For now, companies with MORE than 200 people are NOT dropped for size: vet them and apply like any other (the user: "if already 200+ still apply for now as exception"). This temporarily overrides rule 11 and the 200 cap in the YC/ATS/Wellfound/HN flows (a16z already allowed up to 1000). Log the size in the row notes (`size <n>, cap lifted`).
- Every other filter stays: remote, open to India/worldwide (read the posting), no office in India, not an agency/marketplace, pay at or above the floor, level and match rules, never apply on workatastartup.com, never LinkedIn Jobs. Roles that are US-only, on-site or hybrid still fail regardless of size.
- Newly eligible by this change from the YC directory (to check on their own career pages): Xendit (700, Senior Software Engineer - Platform, remote), Amplitude (750), Zip (500), Athelas (1000), Flock Safety (1000), Clipboard (1000), BioRender (250), Whatnot (1500), Nabis (700), GOAT Group (1600), EquipmentShare (5400). Several of their YC roles are US-only or on-site and still fail.

## US time-zone overlap is OK (user, 2026-11-07)
- For ALL roles, a requirement to work US hours or overlap with US time zones (for example "4+ hours overlap with mainland US", "US timezone", "EST/PST hours") is NOT a reason to drop or hold a job. Apply anyway. In outreach state only the company's own time zone overlap (never India hours, never "IST").
- Still failing: explicit US citizenship/work-authorization requirement, "must be located/reside in the US", on-site/hybrid. Overrides any earlier rule treating US-hours as a filter (daily-jobs time-zone checks, "Remote (US)" screening applies only to residency, not hours).

## Multi-country remote: apply even if India is not listed (user, 2026-11-07; broadens the 2026-10-17 small multi-region rule)
- If a posting allows remote work from 3 or more countries/regions (for example "Europe + Canada + LatAm", a list of country codes), apply even when India is not listed, and regardless of company size (size cap is lifted). Do not drop it as "not eligible for India".
- In the email or note, ask politely whether India-based candidates are eligible. Log as `Found; multi-country (N countries, India not listed)`.
- Still failing: a single country or US-only residency, explicit US citizenship/work-authorization, on-site/hybrid, EU-residency-only, agencies, India office.

## Never raise India or countries in outreach (user, 2026-11-07; overrides "ask politely whether India-based candidates are eligible")
- Do NOT ask whether India is allowed and do NOT mention countries, regions or eligibility in any email, note, comment or form answer. Just apply directly. Only discuss location/eligibility if the company asks first, and then answer truthfully (based in India, available to their time zone overlap).
- Form fields that require a country/location: answer truthfully (Maharashtra, India). Nothing volunteered beyond that.

## ATS format for company career-portal applications (user, 2026-11-07)
- Skills to use: `skills/resume-ats-optimizer` (keyword match vs the posting, ATS checklist), `skills/application-form-filler` (`/apply`, free-text answers), `skills/tailor` (`/tailor`, tailored .tex copy named `<Role> - <Company>.tex`). The four base resumes already pass the ATS text check (single column, A4, 2 pages, `glyphtounicode` on, clean `pdftotext` output).
- Per portal application: (1) upload the matching role-family PDF (PDF, never .tex; for a keyword-heavy posting use a tailored copy, never overwrite the base); (2) paste the posting's exact keywords the resume truly supports into the summary and skills lines; gaps are never added, they are "ramping up" in the answer; (3) form fields in plain text: Name Rahul Jha, email, phone only if required (standard answers), location Maharashtra, India, LinkedIn, GitHub, notice "available to start soon", salary $60,000 USD; (4) free-text answers per `application-form-filler`, no numbers unless asked, no India/country talk; (5) after submit, save the confirmation and log `Applied <date> (<ATS>)`.
- Known resume items: `full stack.pdf` is stale (built before Lokuma was added to `full stack.tex`); recompile in Overleaf (2 pages) and replace the PDF and the Drive link before any Full Stack portal upload. `full stack.tex` has one `tabular` (line ~118); keep it only if the text extraction stays in reading order after recompile.

## Company-website applications: form answers and "what have you built in production" (user, 2026-11-07)
- On EVERY company-website/ATS application, use the ATS format above, the matching role-family resume PDF, and `skills/application-form-filler` for all free-text and question answers.
- "What have you worked on / built in production" answers, by role type:
  - **ML / AI research / Data Scientist roles:** lead with the ACM CIKM 2023 paper "Large Language Models as Zero-Shot Conversational Recommenders" (co-author), then the applied ML work.
  - **Full-stack roles:** use the user's full-stack projects: Lawflow, SkateYX, Right by Hand (names as dictated by the user on 2026-11-07; confirm exact spellings and one real fact each before first use), plus the part-time full-stack work (Kipps.AI portal, Context.dev services). The user says these were scaled to large usage over a period of time; state it qualitatively ("scaled to heavy real usage") and use a figure only when the user supplies the exact number and unit.
  - **AI / agentic AI / applied AI engineering (AI + full stack):** explain Context.dev (LLM web extraction, Playwright), Kipps.AI (RAG voice agents on LangGraph), Lokuma (MCP servers for coding agents) and the other part-time work as production, scalable work; then Atlassian.
- **Specific technology asked:** answer "yes" where I have real hands-on or adjacent experience (even a 40-50% match), phrased as working experience with the closest real work; where I have never used it, say I am ramping up and have shipped comparable work, never claim years of production use or invent a project in it (truthfulness rule 1 stays; the user's hype preference is applied through strong, positive framing, not false claims).

## City field on forms (user, 2026-11-07)
- A city is never a blocker. When a form needs a specific city (autocomplete that rejects "Maharashtra"), pick **Mumbai, Maharashtra, India** from the suggestions. Standard location answer stays "Maharashtra, India" where free text is accepted.
- Keep going through all applications; list blockers (CAPTCHA, login, account creation, visa conflicts) at the end, do not stop for them.

## 5,000-follower cap applies to general networking only (user, 2026-11-07; narrows the 2026-10-31 rule)
- The "skip people over 5,000 followers" rule is ONLY for general LinkedIn networking (Mode C and US networking, people who are not hiring). It does NOT apply to job outreach: for any company we applied to or are emailing about a role, reach the CEO/founder and CTO regardless of follower count (connection request, and the 4-5 line job comment when no note is possible).
- India/Pakistan location skip and the Tax Pilot ban still apply everywhere.

## Gmail draft save method that works (user approved, 2026-11-07; replaces the "click body + type space" ban for drafts only)
- Load the compose URL (`?fs=1&tf=cm&to=...&su=...&body=...`) in the Gmail tab (account u/1), wait 8 s, click the SUBJECT line at the top (about x=1000, y=85 in a 1434x840 window; far from Send), type ONE space (a net change; "x" + Backspace does NOT save), wait 20 s in that same tab, then navigate that same tab (force) to the next compose URL or to #drafts. Gmail saves the draft on that exit. Confirm in Drafts (count goes up, row is at the top).
- Never click or type near the Send button, never press Enter or Ctrl/Cmd+Enter. Drafts only unless a named batch is authorized to send. Do not switch to another tab and back while a compose is open (background-tab autosave is unreliable).
- Sending (when explicitly told): screenshot-verify To/Subject/body, click Send once, confirm in Sent.

## NEVER END THE TURN BEFORE THE LIST IS DONE (user, 2026-11-07, stated angrily after I stopped after four drafts)
- When the user starts a big job (all applications, all YC companies, all drafts), run the WHOLE list in one continuous turn: apply, draft, LinkedIn, sheet, next company. No mid-run status reports, no "should I continue?", no stopping to summarise. Report once, at the very end, or at a hard stop (CAPTCHA, login wall, 429/403, LinkedIn warning).
- "Ignore a few AI for now" (2026-11-07): skip AI-engineer-titled roles in the current run; they stay in the backlog.

## LinkedIn outreach order (user, 2026-11-07)
- For every founder/CEO/CTO of a company we apply to: (1) connection request WITH a note (max 200 chars) whenever LinkedIn offers it; (2) if the note option is gone ("You're out of free custom notes"), send the request plain AND comment on one of their recent quiet posts (30 or fewer reactions+comments) saying which role I applied for, one real fit line, and why I am reaching out (4-5 lines, no numbers, no India, no contact details).
- Fast path that works: `https://www.linkedin.com/preload/custom-invite/?vanityName=<handle>` opens the invite dialog directly (verify the name, then Send without a note at about x=874,y=226). Get the handle from the people-search result link.
- Skip profiles located in India or Pakistan. Log each person in Sheet3.
