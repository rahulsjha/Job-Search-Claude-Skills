---
description: Find jobs that fit my requirements from trusted sources, de-duplicate against the tracking sheet, score each one, and log the passing ones (column H "Added By" = find-jobs agent)
argument-hint: [role family: ai|ds|fullstack|infra|all] [count, default 10]
---

Read `CLAUDE.md` for my background, job filter and rules. This command only finds, checks and logs jobs; it never emails anyone and never submits applications.

Input: $ARGUMENTS (default: all four role families, 10 passing jobs). If the input is not a role family or a number, treat it as an instruction to follow while searching.

## 0. Load the sheet first (duplicate baseline)
Sheet: "Hunting", tab Sheet2 (gid 1578269214): https://docs.google.com/spreadsheets/d/1RQilpuvQiClxvdNOaHG8yDC6Gm8UepZdAoWIi-tU6vo/edit?gid=1578269214#gid=1578269214

Before searching, read every existing row (columns A Links, D Companies Website, B/C emails) with my logged-in browser. Build a "seen" list of:
- job post URLs and the numeric job ID inside each Wellfound URL (for example `3143348`);
- company website domains (for example `allminds.io`, `ensemblegains.com`);
- company name plus role title.
This list is the duplicate check.

## 1. Search (trusted sources only)
Use only the trusted sources in `CLAUDE.md` rule 10: Wellfound, Y Combinator (company directory, Work at a Startup), LinkedIn **posts only, never LinkedIn Jobs**, a16z (portfolio and jobs), and the company's own site. Use my logged-in browser for Wellfound. Search by role family:
- **AI Engineer**: LLM, agents, RAG, MCP, voice AI, applied AI.
- **Data Scientist / applied ML**: ML pipelines, recommender systems, NLP, experimentation.
- **Full Stack**: React, TypeScript, Next.js, Node, Python, Go, PostgreSQL.
- **Infra / DevOps / SRE**: Kubernetes, Terraform, AWS, GCP, CI/CD, observability.
Keep searching until the requested number of jobs have passed every check below or the sources are exhausted.

## 2. Duplicate check (before any scoring)
For every candidate job, compare it with the "seen" list. Mark it **DUPLICATE** and skip it if any of these match:
1. the same job URL, or the same numeric job ID;
2. the same company domain and the same or a near-identical role title (a different role at an already-logged company is NOT a duplicate; list it as "same company, new role" and let me decide);
3. the same company name plus role title, even if the URL differs (reposts and "clone" listings).
Also de-duplicate within the current run. Never add a duplicate row. Report every duplicate skipped with the row it matched.

## 3. Requirement check (hard filters, in this order)
Check the company's own page if Wellfound disagrees; a conflict is flagged, not a rejection, per `CLAUDE.md` rule 4. A job must pass all of these:
| # | Requirement | Pass rule |
|---|---|---|
| 1 | Location | Remote, and hires from India or "everywhere". Reject on-site or hybrid only. |
| 2 | Work authorization | No required US work authorization, clearance or residency. |
| 3 | Company size | **1 to 200 people, hard cap.** Accept only Wellfound bands 1-10, 11-50, 51-200. Reject 201-500, 501-1000 and larger. Cross-check the company's own site, LinkedIn or press (headcount, Series C or later, unicorn valuation); if any trusted source shows more than 200, reject it even when Wellfound says 51-200. Unclear size: flag and do not add until I confirm (`CLAUDE.md` rule 11). |
| 4 | Pay | $35k per year or more. Hourly roles: annualise at 2,000 hours and state the assumption. Pay not listed: mark "pay unknown", do not reject, but flag. |
| 5 | Role fit | Matches one of my four resumes. |
| 6 | Experience | Within reach of my 5+ years; reject only if the ask is far above (for example 10+). |
Record the first failed requirement as the one-line drop reason.

## 4. Match scoring (structured)
For each job that passes step 3, extract the real must-have skills from the posting (ignore wish lists). Score:
- **Must-have skills**: count the posting's required skills that appear on my best-matching resume. Score = covered / total required. Weight 70 percent.
- **Nice-to-have skills**: same ratio over preferred skills. Weight 30 percent.
- **Match** = (must-have score x 0.7) + (nice-to-have score x 0.3), shown as a percentage.
Keep jobs at 30 percent or higher (user rule 2026-10-14: 30% match is enough to apply). Below 30: drop with the missing must-haves as the reason. List, for each kept job, the covered skills and the gaps, and pick the closest base resume (`AI Engineer.tex`, `Data Scientist.tex`, `full stack.tex`, `infra.tex`).

## 5. Add each passing job to the tracking sheet
Append one row per job at the first empty row, never overwrite or delete existing rows. Re-check column A for the job link right before writing (duplicate guard). Columns:
- A Links: job post URL
- B Email 1, C Email 2: leave blank (`/cold` fills these later)
- D Companies Website: the real company website
- E Linkedin: founders' LinkedIn URLs if found from the trusted sources, else blank
- F Followup Count: 0
- G Followup Date: leave blank until an email draft exists
- H Added By: `find-jobs agent`
Verify each row with a screenshot. Use the 5-try retry rule if a cell does not take the text.

## 6. Report (structured)
1. **Added** (one table): # | Company | Role | Size | Pay (annualised) | Match % | Covered skills | Gaps | Resume to use | Source | Sheet row.
2. **Duplicates skipped**: Job | matched which existing row | why.
3. **Dropped**: Job | failed requirement or missing must-haves.
4. **Flags**: source conflicts (for example Wellfound versus company page), pay unknown, hours or time zone issues.
5. **Next step**: run `/cold B <job link>` on the ones I pick (it fills the blank email columns in the same row instead of creating a new one).

## Thoroughness rule (user, 2026-10-14)
Never skip or stop early. Vet every candidate on its real job page (not the listing card), queue 422/404s for retry instead of stopping, cover every role page, page number, pre-screened list and the YC directory, and report in the fixed structure (counts, Added table, duplicates, dropped with reasons, retry queue, still undone). See CLAUDE.md "Never skip, be thorough and structured".

## Company LinkedIn (user rule, 2026-10-14)
Fill column P "Company LinkedIn" (linkedin.com/company/...) for every new row, from the company site, Wellfound/YC page, or a new-tab web search; never guess. See CLAUDE.md "Company LinkedIn rule".

## a16z size exception (user, 2026-10-15)
For a16z-sourced jobs only, the size cap is 1000 (not 200). All other sources keep 200. See CLAUDE.md.

## Sheet column rules (user, 2026-10-15)
Every logged row must have D (company website), E (founders/hiring contacts LinkedIn) and P (company LinkedIn page) filled, or "Not found (checked: ...)" plus a retry. See CLAUDE.md "Sheet column rules: website and LinkedIn".


## Standing rules (user, 2026-10-16): external applications and all contacts
- If a job has an application on the company website/ATS (Greenhouse, Lever, Ashby, careers form), apply there too as well as Wellfound and the Gmail draft. Hold and ask the user for phone, work authorization/sponsorship, CTC, notice period, relocation, legal declarations, account creation, CAPTCHAs. Log column I "Applied externally YYYY-MM-DD (<ATS>)" or "External form needs user answer: <what>". See CLAUDE.md "External company applications".
- For every company collect ALL founders, CEO/CTO and the hiring manager/recruiters (4-5 people): primary email in B, the rest in C separated by " | ", names/roles/LinkedIn in E. See CLAUDE.md "All key contacts per company".
