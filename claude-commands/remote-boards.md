---
description: Fetch jobs from Remotive, We Work Remotely and Arc.dev, dedupe against the Hunting sheet, vet each job against the filters, and log passing ones in Sheet2 (Added By `remote-boards`). Read-only on Remotive and We Work Remotely; applies on Arc.dev's own dashboard only (user rule 2026-11-04); never emails inside this skill.
argument-hint: [board: remotive | wwr | arc | all] [optional keyword]
---

Read `CLAUDE.md` first (job filter, size cap 200, India-office rule 2026-11-04, contacts rules, sheet columns, Gmail rules). Input: $ARGUMENTS (default `all`).
One board at a time, one job at a time. No parallel agents. Human pace: a few seconds between pages. Apply only on Arc.dev's own dashboard (see Phase 0); never email, draft or message inside this skill.

## Phase 0. Sources (use the cheapest reliable one)
- **Remotive (browser only):** open the user's filtered listing page in Chrome, read the visible cards (title, level, salary, location) by scrolling. Company name and apply link are members-only and blurred: do not unmask or extract them from responses, and do not pay or sign up for the user. If the user buys a membership and logs in himself, read the unlocked cards in his tab at human pace. No scripts, no API calls, no CSV files.
- **We Work Remotely (browser only):** open the user's listing URL in the Chrome tab (`https://weworkremotely.com/?categories%5B%5D=2&categories%5B%5D=17&categories%5B%5D=18&categories%5B%5D=6`), scroll the cards, and read company, title, region and pay. Open each job page for the posting link, description and pay. Free account only. No scripts, no RSS/curl pulls, no CSV files.
- **Arc.dev (user, 2026-11-04):** open `https://arc.dev/dashboard/d/full-time-jobs/browse` in the logged-in Chrome tab, click Filters, set Location = India (type "India", pick the flag option), click Apply (an "India" chip shows). Then go through the list and APPLY on Arc for every job that passes Phase 1/3 (engineering roles only; skip product/design/sales roles, US-only, on-site, over-200 or India-office companies). Use Arc's own "Fast apply"/Apply flow inside the dashboard with the matching resume family and a role- and stack-specific note (human style, no numbers, no India/hours mention, "available to start soon" for notice). Check the "Applied" tab afterwards and log each application. If Arc's Apply opens LinkedIn Jobs or an external form that needs a CAPTCHA/password, do not use it: HOLD for the user. If a login, CAPTCHA or bot check appears, stop and mark HOLD (hand-off rules in CLAUDE.md).

## Phase 1. Cut 1 (cheap, keyword only)
Keep a job only if the title/level fits (Senior, Staff, Principal, Lead, Founding, or Full-stack/Backend/DevOps/SRE/Platform/Data/ML/AI engineer) AND the location text says worldwide / anywhere / global / Asia / APAC / India / "all timezones", or lists many countries. Drop US-only, US/Canada-only, EU/UK-only, LATAM-only, "must be authorized to work in the US", on-site/hybrid, non-engineering roles.
Level rule: default is Staff/Senior/Lead/Founding only (CLAUDE.md 2026-10-24). If the user lifts it for these boards, say so in the report.

## Phase 2. Dedupe
Against Sheet2 by job URL (column A), company domain (column H) and company name anywhere in B:N, and against `remote_boards_ledger.md`. Already present: log `already in sheet (row n)`.

## Phase 3. Vet each survivor (real page, never the card alone)
1. Open the job page and the company's own site/careers/ATS posting: still open, fully remote, countries allow India or worldwide, pay (top of range or midpoint at or above about 35k USD, else flag), no citizenship/work-authorization requirement.
2. Company: size 1-200 (LinkedIn company page band + site), not India-based, **no office in India** (careers page, LinkedIn company locations, web search; hold with `Hold: India office (<city>, source)` if found), not an agency/staffing firm.
3. Fit vs resumes: requirement list, have/close/gap, match %, closest resume family. Stack gaps never block (note `Gap: <tech> (ramping up; closest: ...)`). 10+ years asked: still add.
Write layers 1-3 in the row notes.

## Phase 4. Log in Sheet2 (one row per job, Added By `remote-boards`)
Columns per CLAUDE.md: A job link (the board URL), B/C/D emails, E people with LinkedIn, F company LinkedIn, H website, I company careers/ATS link, K 0, L +5 days once an email is sent, M `remote-boards`, N status `Found <date> (<board>); L1 ok; L2 ok (<evidence>); L3 match <n>%; Gap: ...; Flags: ...`, Q Stage `Not sent`. People/emails: CEO/founder, CTO, HR, hiring manager, team lead (HARD GATE, minimum 3 or `Hold: contacts not found (checked: ...)`). Append to the first empty row with the clipboard method and verify via gviz CSV read-back.

## Phase 5. Draft (separate step, only after the row is complete)
One Gmail draft per company, all people in To, v2 human style, role- and stack-specific, one resume link. Sending follows the standing send authorization (3+ minutes apart, 25 per day, verify each).

## Phase 6. Report
Counts per board: fetched, cut-1 survivors, already in sheet, dropped by reason (US-only, size, India office, closed, agency), added (with match % and gaps), HOLD list (login/CAPTCHA, no contacts). Append every job seen to `remote_boards_ledger.md` (date, board, company, role, URL, outcome). End with `My opinion:`.

## Cadence
Run `all` once a day (Remotive and WWR via API/RSS take minutes), Arc.dev when the user is logged in. Only jobs published since the last run need vetting; older ones stay in the ledger.


## WWR flow (user, 2026-11-04): one job at a time, in this order
1. **List:** open the listing URL above (and `page=2`, `page=3` until posts are older than the last run). Collect for each post: WWR URL, company name, role title, region/countries, posted date. Cut 1 as in Phase 1 (engineering roles; worldwide/anywhere/Asia/India-friendly; not US-only).
2. **Find the external hiring link (web search, not the WWR Apply button):** search `"<company>" "<role title>" careers`, `"<company>" jobs`, and the company's ATS (Ashby, Greenhouse, Lever, Workable, BambooHR, company /careers). Record the company's real website (domain), the external posting URL and whether it is still open. No posting found: log `no external posting found (checked: web search, ATS, site)` and keep the WWR link as the source; the job is still processed for people and email.
3. **Company vetting:** website (what they do, size 1-200, location not India-based, no India office per CLAUDE.md), company LinkedIn page (confirm headcount and locations), and any LinkedIn post about this opening (profiles and posts only, never LinkedIn Jobs). Layers 1-3 from Phase 3 (post, live posting, fit and match %) are written in the row notes.
4. **If an external application form is found:** fill it with the matching resume family and a role/stack-specific answer per the external-application rule (CLAUDE.md 2026-10-16/27/30: write every answer myself, available to start soon, no numbers, no India/hours mention); hold only for CAPTCHA/login/password/visa conflicts. Log `Applied <date> (<ATS>)` or the HOLD reason.
5. **People (all of them):** CEO/founder, CTO, hiring manager (head of the team), HR/recruiter/talent, team lead, plus a senior engineer if found, from the company LinkedIn People tab, the site team page, GitHub org and web search. For each: name, role, LinkedIn URL, email (published first, else `firstname@domain` marked guessed using the company's visible email pattern). Minimum 3 people or `Hold: contacts not found (checked: ...)`. Prefer verified addresses; do not use addresses that bounced before.
6. **Sheet row:** one Sheet2 row per job (Added By `remote-boards`, A = the WWR URL, I = the external posting/careers link) with B/C/D emails, E people with LinkedIn, F company LinkedIn, H website, N notes (layers, match %, gaps, flags, WWR categories), Q Stage.
7. **ONE draft per company:** a single Gmail draft (account u/1) with ALL people in To (never Cc), greeting names them or "Hi team,", v2 human style, role- and stack-specific, one resume link, no numbers, no India/hours. Subject `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`. Verify To/Subject/body in Drafts. Set N to `Drafted <date> (To: n people)`.
8. **Report and ledger:** per run, counts (posts seen, cut-1, external posting found, applied, drafted, held, dropped by reason) and every job in `remote_boards_ledger.md`. Sending is a separate step under the standing send authorization (3+ minutes apart, 25 a day, verify each).

## RemoteOK (user, 2026-11-04, browser only)
- Listing: `https://remoteok.com/remote-dev+engineer-jobs?location=IN,region_AS,Worldwide` (473 results on 2026-11-04, newest first; the free page shows company, title, tags, region tag and age; salary is shown only on some rows, the rest say "Upgrade to Premium to see salary": never try to unmask it). Read the cards by scrolling in the Chrome tab, open each job, find the company's own hiring page by web search, then apply on the company form, add the Sheet2 row, and make one draft per company.
- The filter is noisy (many VERIFIED non-engineering and 3-4 month old posts). Keep only engineering roles from the last ~30 days; skip LATAM/region-limited, large (>200) companies, agencies and anything with an India office.

## Method rule (user, 2026-11-04): browser only
Work through the Chrome browser by hand (open pages, read, click, type). Do NOT write or run scripts for job listings, do NOT create CSV/JSON files of jobs, do NOT use curl/RSS/API pulls for these boards. Keep notes only in `remote_boards_ledger.md` and the Hunting sheet.

## The two flows (browser only)
- **We Work Remotely:** read the listing cards and each job page (company, title, location, pay, posting link) -> web-search the posting to find the company's own hiring page, size, India office, people -> apply on the company form, add the Sheet2 row, one draft per company.
- **Arc.dev:** Filters > Location = India on the full-time browse page -> open each engineering job -> Fast apply with a role-specific note -> log in Sheet2 and the ledger. Sheet2 columns shifted on 2026-11-04 (new column K): read the header row before writing.

## Target websites
The current target-site table (what to do on each site and what is barred) is in CLAUDE.md, section "Target websites (user, 2026-11-04)". Follow it before touching any board.
