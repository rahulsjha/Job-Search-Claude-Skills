---
description: Find leads from Hacker News "Ask HN: Who is hiring?" (last 3 weeks by default), show details, then reach the posters by email first, HN reply second, ATS form third, LinkedIn last. Gmail drafts only.
argument-hint: [weeks back, default 3] [month thread, default latest] [company names to take through the full flow]
---

Read `CLAUDE.md` first (job filter, size cap 200, contacts rules, Gmail safety, sheet columns). Input: $ARGUMENTS.

## 1. Find the posts (read only)
1. Thread list: https://news.ycombinator.com/submitted?id=whoishiring (take the newest "Who is hiring?", not "Who wants to be hired?"). Also scan the previous month when the window crosses a month.
2. Data: in an HN tab run `fetch('https://hn.algolia.com/api/v1/items/<thread id>')` (Algolia has every live top-level comment; the Firebase API returns the same posts, dead ones 404). Keep top-level comments with `created_at` inside the window (default 3 weeks), strip HTML.
3. Filter: contains "remote"; drop US-only, US/Canada-only, EU/UK/LATAM-only, on-site/hybrid-only, India-based companies, agencies, commission-only, non-engineering (GTM, sales, iOS-only). Keep worldwide/anywhere/global/India/APAC/APJ and Asian-friendly time zones; flag time-zone-limited (AMER/EMEA) and "select countries" for a check.
4. Apply the sheet rules: all engineer levels for HN leads (CLAUDE.md 2026-10-27; the 2026-10-24 senior-only rule does not apply here), size 1-200 (flag if unclear), pay floor (flag if unlisted), match >= 30%. Dedupe by company domain (column H) and job link (column A).
5. Show me a table per lead: company, role, posted date, region wording, pay, contact (email, ATS link, HN author, named people with LinkedIn), why it fits, flags. Posts just outside the window go in a short separate list.

## 2. Where to reach them (order of preference, user 2026-10-26)
1. **Email the contact in the post.** HN posters expect applications by email. Use the address and subject line the post asks for (for example "HN - Applied ML"). If there is no email, find the founder or hiring lead through the company site, GitHub org, HN profile "about", and LinkedIn; real verified name + real domain -> `firstname@domain` marked "(guessed)". One combined email per company, all people in To, never Cc. Gmail is DRAFT-ONLY: follow the Gmail safety rules (compose URL, screenshot to verify To/Subject/body, Escape only, verify in Drafts; never click or type in the compose window).
2. **Reply under their HN comment** (two short lines: applied by email and one specific fit line). Only from the user's own HN account; ask once whether they want it.
3. **Company ATS or careers form** if the post links one (Ashby, Greenhouse, Lever). Fill and submit only through the normal UI after vetting; hold for phone, visa, salary history, essays, CAPTCHAs (see External company applications rule).
4. **LinkedIn last**: a connection request (no note by default) plus comments on the founder's recent own posts, only after the daily comment limit has reset and after verifying earlier comments posted. Never LinkedIn Jobs.

## 3. Message style
Human /cold v2 style from CLAUDE.md: `TL;DR:` line, `Hi <first name or team>,`, three short paragraphs (applying + where I saw it on Hacker News "Who is hiring?", who I am: most recently SDE II at Atlassian plus AI engineer on early teams, why I fit using the post's own stack words), quick links (2 project links, ONE matching resume link, GitHub), one-line ask, Best / Rahul Jha / LinkedIn. No numbers, no India mention, no admiring-the-company lines. A stack gap is stated as "ramping up on <X>". Subject: `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`. If the post asks for specifics (GitHub, a project, a subject line), follow it exactly.

## 4. Log and finish
Per company, in this order: vet, find people, fill the Hunting sheet row (all columns A-N per the HARD GATE: people with LinkedIn, emails, company LinkedIn, website, job link `https://news.ycombinator.com/item?id=<comment id>`, follow-up +5 days, Added By `hn-hiring`, status), then the single Gmail draft, then update column N (`Drafted <date>`). One company at a time, never in parallel. Do not apply or draft before the row is complete.

## 5. Report
Counts (posts in window, remote, passing, skipped by reason), the lead table, which channel was used per lead, drafts created, what is on hold and why, next steps.

## 3. Target and definition of done (user, 2026-10-27)
- **Target: at least 50 qualifying HN postings** (distinct companies) worked through, not just found. Tracked in `hn_leads_ledger.md` (one line per post: `thread | comment id | company | role | status | reason`).
- **Qualifying posting** = passes section 1 filters (remote, India/worldwide/APAC-open, senior-level, size <= 200, not India-based, not an agency) and is still open (company page or ATS confirms it; a stale or paused hiring page is REJECTED).
- **Worked through** = one of: `APPLIED` (form submitted or email sent with the user's authorization), `DRAFTED` (email text ready in `hn_drafts.md` or Gmail), `REJECTED <first failed rule>`, `HOLD <what the user must answer>`. The 50 counts QUALIFYING posts with status APPLIED, DRAFTED or HOLD; rejected ones do not count.
- **Scope to reach 50:** newest thread first, then walk back month by month (Sep, Aug, Jul, Jun, May 2026 ... until 50 qualify). The 2026-10-26 scan of May-Oct (1,626 posts -> 133 remote+geo+role -> 48 senior-level companies) is the starting pool; re-vet them against the live page, since many are old.
- Each qualifying lead gets the full flow one at a time: vet, sheet row with people/emails (HARD GATE), contact channel in order of section 2, status written to the ledger and column N. Progress line in every report: `HN qualifying: n/50 (applied a, drafted d, hold h; rejected r)`.
- Emails are sent only when the user authorizes a named batch; until then status is DRAFTED.
