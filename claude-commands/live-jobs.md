---
description: Full multi-pass scan of Wellfound, a16z and YC Work at a Startup (no date filter), compare with the sheet and a backlog ledger, keep India, worldwide, anywhere, overseas and Asia/APAC-friendly remote roles, and log the passing ones in the next free rows
argument-hint: [role family: ai|ds|fullstack|infra|all] [target count, default 15] [passes, default 3]
---

Read `CLAUDE.md` (job filter, size caps, rules), the memory note `project-hunting-sheet-state-2026-10-22.md` and the ledger `live_jobs_ledger.md` (this folder) first. This command only finds, vets and logs jobs. It never emails anyone, never creates Gmail drafts and never submits an application. On workatastartup.com it is read only: never click Apply or message anyone there.

Input: $ARGUMENTS (default: all four role families, 15 passing jobs, up to 3 passes). Any other text is an extra instruction to follow while searching.

## Operating principle (user, 2026-10-22)
**No date filter.** Do not limit to the last week. Scan the whole open job list on each source, compare it with what is already on the sheet and in the ledger, and work through what is left. Run **several passes**: every run starts by finishing the backlog from earlier runs, and every pass picks up jobs the previous pass did not get to (rate limits, unloaded pages, failed vets). A job is only "done" when it is on the sheet, or in the ledger as rejected with a reason.

## 0. Baseline: the sheet and the ledger
1. Sheet "Hunting", tab Sheet2 (gid 1578269214), logged-in browser. Read with `fetch('https://docs.google.com/spreadsheets/d/1RQilpuvQiClxvdNOaHG8yDC6Gm8UepZdAoWIi-tU6vo/gviz/tq?tqx=out:csv&gid=1578269214')` from the Sheets tab, quote-aware CSV parse (row number = index + 1). Build seen sets from column A (job URLs, Wellfound numeric ids, a16z uuids, YC job ids) and column H (company domains). Compute the last used row; the next row is last + 1 (blank rows can exist mid-sheet).
2. Ledger `live_jobs_ledger.md` in the project folder: one line per job ever seen: `source | id | company | role | status | reason/date`. Status is `ADDED row N`, `REJECTED <first failed rule>`, `PENDING <why>` (not vetted yet, page failed, rate limited, needs my answer) or `HOLD`. Read it before scanning and update it after every pass. Do not re-vet a REJECTED job unless its reason was a bug or the posting changed; always retry PENDING first.
3. Current sheet layout: A job link, B/C/D emails, E person LinkedIn, F company LinkedIn, G open source, H website, I external portal, J (spare), K follow-up count, L follow-up date, M added by, N status. Columns R:U are a dashboard: never write there.

## 1. Eligibility classes (broad on purpose)
Keep a job when the real posting says one of these; tag the class at the start of column N.
- **IN**: India named ("Hires remotely in India", India, an Indian city).
- **WW**: worldwide, anywhere, everywhere, global, "Remote - International", any country.
- **APAC**: Asia, APAC, South/Southeast Asia, or Asian-timezone overlap, or an Asia/Middle-East company hiring remotely.
- **OVERSEAS**: company outside the US hiring remote contractors across several regions (EU, UK, UAE, Singapore, Australia) with no residency rule.
Reject: US-only, US/Canada-only, LATAM-only, EU-residency, "must reside in", citizenship, clearance/ITAR, on-site or hybrid-only, local work pass required (e.g. Singapore EP/S Pass).
Flag, do not reject: timezone overlap hours, region wording that conflicts between Wellfound and the company site, pay not listed.
Small-company relaxation (CLAUDE.md 2026-10-17): under 50 people and more than 3 regions listed counts as eligible.

## 2. Other hard filters
- Size 1-200 people (Wellfound bands 1-10, 11-50, 51-200); **a16z up to 1000**. Cross-check the company site/LinkedIn; reject if clearly larger.
- Skip India-based companies (HQ and all locations in India).
- Pay >= $35k per year (top of range or midpoint). Convert currencies: INR "8L-12L" = lakh per year (about $9.5k-14k, fails), LPA the same, hourly x 2000, monthly x 12. Pay not listed: keep and flag.
- Role fits one of four resumes (AI Engineer, Data Scientist/applied ML, Full Stack incl. backend, Infra/DevOps/SRE; data/analytics engineering maps to Data Scientist).
- Experience ask not far above 5+ years (reject 10+). Match score >= 30% (must-have covered/required x 0.7 + nice-to-have x 0.3); pick the closest resume.

## 3. Source recipes (proven)
**Wellfound** (logged-in tab; same-origin `fetch` works; 2 to 2.5 s apart; about 10 listing pages per burst, pause, then next burst; stop at the first 429/403/CAPTCHA and report; never bypass).
1. Listings, no date filter: `fetch('/role/r/<role>?page=N')` for `software-engineer`, `machine-learning-engineer`, `devops-engineer`, `full-stack-engineer`, `backend-engineer`, `data-scientist`, `data-engineer`, `site-reliability-engineer`, `cloud-engineer`, `platform-engineer`, `python-developer`, `node-js-developer`, `ai-engineer` (also `?remote=true` style variants if the page offers them). Walk pages until a page adds no unseen ids. Pull ids with `/jobs/(\d{7})-slug`. Keep every id not in the seen set and not REJECTED in the ledger. (Ids are roughly chronological: low ids are old and often closed, so vet newer ids first but do not exclude old ones.)
2. Detail: `fetch('/jobs/<id>-<slug>')`, strip scripts/tags. Read title/company/location from `<title>`, `Hires remotely in X` (the decisive eligibility line; "Everywhere" = WW), `Remote work policy`, `Company Location`, `NN-NN Employees`, pay (watch INR lakh and currency), "Posted N days ago", and sentences with "reside", "authorized", "visa", "time zone", "only accept". A 404/410 means closed.
3. Company: `fetch('/company/<slug>')` for Website, size, markets; `/company/<slug>/people` for names.
**a16z** (jobs.a16z.com, a Getro board; open in the tab).
1. No date filter. Use `https://jobs.a16z.com/jobs?workArrangement=remote&jobTypes=<slug>` for each role slug (software-engineer is confirmed; pick the others through the Roles box and copy the slug from the URL), and also remove `workArrangement` for "remote or hybrid" companies. Scroll to load; a page only loads part of the list (about 134), so repeat with more role filters and sort orders, and diff against the ledger each pass.
2. Card links are `/jobs/<company>/<uuid>--<slug>`; same-origin `fetch` returns the posting. Read LOCATION, WORK ARRANGEMENT, pay, and the card's stage and employee band. Many "remote" roles are US-only or on-site.
**YC Work at a Startup** (read only).
1. Navigate the tab to `https://www.workatastartup.com/jobs?remote=only&jobType=fulltime` (add `role=`/`sortBy=` variants), scroll to load all cards, read company, batch, title, location text ("Remote (US)", "Remote (CA)" fail), salary. Direct `fetch` of job pages returns 406: open a job in the tab only if the card is not enough. Founders from the YC company page.
Optional extras: LinkedIn posts (never LinkedIn Jobs), company career pages, Product Hunt.

## 4. Multi-pass loop
Pass 1: backlog (PENDING/HOLD in the ledger) first, then a fresh full scan of each source. Pass 2: retry everything that failed or was rate limited, scan role pages and filters not yet covered, and re-check ledger PENDING. Pass 3: widen roles/queries and re-diff. Stop when the target count is reached, or a pass adds no new passing job and nothing is PENDING. Write the ledger after each pass, and say in the report which jobs are still PENDING and why.

## 5. Duplicate check
Skip and list: same URL or id; same domain with the same or near-identical role; same company and role title with another URL. A different role at a company already on the sheet is "same company, new role": list it for me, do not add automatically.

## 6. Log passing jobs
Paste one row per job into the next free rows with the synthetic paste method: select the target cell with the Name Box (e.g. `A279`), then dispatch a `ClipboardEvent('paste')` with a tab-separated `DataTransfer` on `.cell-input`, one line per row, 14 columns A to N:
- A real job URL; B, C, D blank (emails later); E people `Name (role): url | ...` or `LinkedIn not found`; F company LinkedIn or `Not found (checked: ...)`; G blank; H company website; I company careers/ATS link if known; K `0`; L blank; M `find-jobs agent`;
- N: `Found <date>; <IN|WW|APAC|OVERSEAS>; <Source>; <role>; <company location>, <size>; hires: <region wording>; pay <USD/yr> (<original>); match <n>% (covered: ...; gaps: ...); resume: <family>; flags: ...`.
Verify by re-reading through gviz and comparing. Never overwrite or delete rows; skip if column A already has the link.

## 7. Report (fixed structure)
1. **Diff since last run**: ledger size before and after, newly seen jobs, newly added, newly rejected, still PENDING (and why).
2. Counts: sources scanned, pages walked, candidates seen, duplicates, dropped by reason, passing, retry queue.
3. **Added** table: # | Company | Role | Class | Size | Pay (USD/yr) | Match | Resume | Source | Sheet row.
4. **Duplicates** and **same company, new role**; **Dropped** with the first failed rule; **Flags**.
5. **Next step**: `/cold B <link>` on the leads I pick (one combined Gmail draft with every person in To).
Update `live_jobs_ledger.md` and the memory note (last used row, counts).

## Pacing and safety
- Never apply, send, draft, create accounts or answer forms. YC is read only.
- Wellfound: bursts of about 10 listing pages, 2 s between fetches, stop on 429/403/CAPTCHA and report; a 404/422 job goes to PENDING for retry.
- Print tool output in chunks under about 1000 characters and strip `?`, `=`, `&`, `#` from anything shown (output with query strings is blocked). Run long loops in the background inside the page and poll.
- Be thorough per CLAUDE.md "Never skip": vet every candidate on its real job page, not the listing card.
