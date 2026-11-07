---
description: Month-by-month sweep of Hacker News "Ask HN: Who is hiring?" (and other monthly hiring threads). Collect every unique listing, put it through three verification layers, add it to the Hunting sheet, then find the people (CEO, CTO, HR, HM, TL) with LinkedIn and email pattern. A month is "passed" only when every listing is done.
argument-hint: [month, e.g. "November 2026", or "next" for the oldest unpassed month]
---

Read `CLAUDE.md` first (job filter, size cap 200, contacts rules, Gmail safety, sheet columns, "HN monthly sweep rule"). Input: $ARGUMENTS.
One month at a time, one listing at a time. Never run agents or tasks in parallel. Read-only on HN; never apply, email, draft or message in this skill (those are separate steps after a listing is complete).

## Phase 0. Pick the month
1. Open the tracker (Hunting sheet, tab `Metrics`, block `HN MONTHS`, see section 7). Take the given month, or with `next` the oldest month whose Status is not `PASSED`.
2. Thread id: `https://hn.algolia.com/api/v1/search_by_date?tags=story,author_whoishiring` (title `Ask HN: Who is hiring? (<Month Year>)`, never "Who wants to be hired"). If the month's thread is not posted yet, say so and stop.

## Phase 1. Collect every unique listing
1. `https://hn.algolia.com/api/v1/items/<thread id>` gives all top-level comments. Keep every comment with text; strip HTML, keep links.
2. Unique = one row per company + role family. Merge repeat posts of the same company (same domain) into one listing and keep the newest comment id. Drop dead/flagged comments.
3. Dedupe against the sheet before any work: column A (job link or HN item id), column H (company domain), and the company name anywhere in B:N. Already-present companies are logged `already in sheet (row n)` in the month report, not re-added.
4. First cut (cheap, keyword only): the post mentions remote/worldwide/anywhere/global/Asia/APAC/India, AND names an engineering role (senior, staff, principal, full stack, backend, software engineer, SDE, devops, SRE, platform, infrastructure, data, ML/AI, founding, lead). Everything else is logged `not engineering` or `not remote`.
5. Write the counts first: posts, unique companies, cut 1 survivors.

## Phase 2. Three verification layers (every surviving listing, no skipping)
Record the result of each layer in the sheet row notes. A listing that fails a layer is logged with the layer and the first failed requirement, and is NOT added unless the failure is only a stack gap (see rule below).

**Layer 1: the post itself.** Read the whole post end to end. Extract and write down: role titles, level, region wording (worldwide / anywhere / India / APAC / time-zone limits / "select countries" / US-only / visa-only), pay, stack (every language, framework, cloud, tool), how to apply (email, subject line, form, ATS), people named, company links. Reject only on a hard stop: on-site or hybrid only, US/Canada-only, EU/UK/LATAM-only, explicit citizenship or work-authorization requirement, agency or commission-only, India-based company, non-engineering role. Flag (do not reject): time-zone limits, unlisted pay, unclear size, "select countries".

**Layer 2: the company and the live posting.** Open the company website, careers page and ATS (Ashby, Greenhouse, Lever, Workable, own page). Confirm: the role is still open on the live page (a closed, paused or 404 role is rejected; an old HN post alone is not proof), the remote policy and countries on the real page, pay, stack, company size (accept 1-200; a trusted source showing more than 200 means reject, or flag and ask when unclear; a16z exception does not apply to HN), company location (not India-based). Note any conflict between the post and the page and keep it in the notes.

**Layer 3: fit against my resumes, requirement by requirement.** List every requirement of the posting (languages, frameworks, cloud, databases, years, domain). Mark each `have` (on the resumes), `close` (nearest real experience, say which) or `gap` (not on the resumes). Compute match % = (have + 0.5 x close) / total. Pick the closest resume family (AI Engineer, Data Scientist, Full Stack, Infra). Write the one-line requirement mapping with a real example (CLAUDE.md rule 6).

## Rules that decide add or not
- **Different-stack rule (user, 2026-11-02): a stack gap never blocks a listing.** If the role needs Go, Rust, Java, .NET, Ruby, Elixir, Scala or another stack I do not have, still add it. Write the gap in the notes as `Gap: <tech> (ramping up; closest: <real experience>)`. Never claim the skill (truthfulness rule 1). Go and Java are on the resume; Rust, Ruby, .NET, Swift and Kotlin are gaps.
- **Match threshold: 50% or more is added; even below 50% add it if every hard filter passed** and mark the match % in the notes. Never drop a listing for match alone.
- All engineer levels are allowed for HN listings (CLAUDE.md 2026-10-27).
- Hard stops and size cap stay as above. Pay below about $35k top-of-range is a flag, not a reject, when the pay is unlisted; a listed pay clearly under the floor is rejected.

## Phase 3. Add to the Hunting sheet (Sheet2, one row per listing)
Append to the first empty row (check the last row with the gviz CSV first; never overwrite). Columns follow CLAUDE.md "Correct sheet columns": A job link (`https://news.ycombinator.com/item?id=<comment id>`), B/C/D emails, E people, F company LinkedIn, H website, I careers/ATS link, K follow-up count 0, L follow-up date (+5 days when a draft/email exists), M Added By `hn-monthly`, N status, Q Stage `Not sent`. Status format for N: `Found <date> (HN <Month Year>); L1 post ok; L2 live-page ok (<evidence>); L3 match <n>% (<have/close/gap list>); Gap: <techs>; Flags: <...>`. Paste with the clipboard method (type tab-separated rows into the sheet only through paste into column A of an empty row; verify by reading the gviz CSV). Never write into the dashboard columns.

## Phase 4. People: CEO, CTO, HR, HM, TL (every listing)
Order of work per company (CLAUDE.md "People-finding steps, LinkedIn first"):
1. Company LinkedIn page (`linkedin.com/company/<slug>`), confirmed against the company website footer or about page. Put it in column F.
2. Open the company People tab (logged-in LinkedIn, profiles only, never LinkedIn Jobs). Find, in this order: CEO/founders, CTO/head of engineering, HR/recruiter/talent, hiring manager (HM, head of the team the role sits in), team lead (TL), plus a senior engineer on that team. Record each as `Name (role): https://www.linkedin.com/in/<handle>` with the live current title; if the profile shows "Past:" the person has left, skip them. If the People tab hides profiles, use the company site team page, the post's author on HN, the GitHub org, then a profile search (`/search/results/people/?keywords=<name> <company>`, 6 s apart, a few per call; the monthly search cap applies).
3. Email pattern: first a published address (post, careers page, contact page, press page, GitHub). If none, find the company's real pattern from any published address on that domain (for example `first@`, `first.last@`, `flast@`) and build each person's address with it, marked `(guessed)`; if no pattern is visible, use `firstname@domain` marked `(guessed, pattern unknown)`. The domain must come from the company's own site. Never invent a person, never use scraped or paid lists.
4. Write B (primary, published first), C and D (the rest, " | "), E (people with LinkedIn). Minimum 3 people or the row says `Hold: contacts not found (checked: <sources>)`.
5. Skip any person whose LinkedIn location is India or Pakistan for LinkedIn outreach (CLAUDE.md 2026-11-01); emailing them is a separate decision, note their location in E.

## Phase 5. Month report and the "month passed" rule
Per month, write the counts and the table: posts, unique companies, cut-1 survivors, rejected by layer (with reasons), already in sheet, added (with match % and gaps), contact status per added row (people found / missing), and the next step. End with `My opinion:`.

A month is `PASSED` only when ALL are true:
1. Every unique listing from the month is in one of three states: added to the sheet, rejected with a written layer and reason, or already in the sheet.
2. Every added listing has passed layers 1-3 (notes written) and has the people and email set from Phase 4 (or an explicit `Hold: contacts not found` with the sources checked).
3. The counts in the month report add up (posts = rejected + already in sheet + added).
Then update the tracker (section 7) in the same pass. Never mark a month PASSED while any listing is unprocessed.

## 6. Order of months
Newest month first, then walk back month by month. The 2026-11-02 scan covered Oct to May at keyword level only (9 leads added); those months are NOT passed until this skill's layers are done for them.

## 7. Sheet tracker: tab `Metrics`, block `HN MONTHS`
Columns: Month | Thread id | Unique companies | Cut-1 survivors | Added to sheet | Rejected | Already in sheet | Contacts complete | Status (`Not started`, `In progress <date>`, `PASSED <date>`) | Notes. One row per month. Update after every listing and set Status to `PASSED <date>` only by the rule above. If the block does not exist, create it below the existing dashboard cells (never over them) after reading the tab.

## Safety
LinkedIn: no Jobs, no Easy Apply, no connection requests or comments in this skill; stop at any warning or CAPTCHA. Gmail and sending: not used here. Hacker News: read only, never post. Human pace for any browser reading (a few seconds between pages).
