---
description: HN job flow. Start from the newest "Ask HN: Who is hiring?" thread, diff every post against the Hunting sheet, vet only the NEW ones on the company's own page, then apply there, log the sheet row (A-S), make ONE Gmail draft, and do LinkedIn outreach to CEO, CTO, HM, HR and TL. One company at a time, no stopping until the list is done.
argument-hint: [optional: max new companies this run, default all] [month thread, default newest]
---

Read `CLAUDE.md` first (it holds every rule; this skill only sequences them). Input: $ARGUMENTS. Same shape as `/yc-jobs`; only the source differs.

## Start page (always)
https://news.ycombinator.com/submitted?id=whoishiring (newest "Who is hiring?", never "Who wants to be hired?"). READ ONLY on HN: never reply or post from the user's account unless asked.

## 1. Collect the list
1. Find the thread id: in a tab on `hn.algolia.com`, fetch `/api/v1/search_by_date?tags=story,author_whoishiring&hitsPerPage=4`.
2. Fetch `/api/v1/items/<thread id>` (all live top-level comments). Strip HTML. Keep posts that say "remote". Drop at once: `REMOTE (US)`, US/Canada-only, EU/UK/LATAM-only, on-site/hybrid, agencies, commission-only, non-engineering (GTM, sales, PM, design, marketing).
3. Tool note: the JS tool blocks output with URLs/query strings and truncates near 600 chars. Replace URLs with `[url]`, print 8-12 lines at a time, and pull contact emails with a regex.
4. Record per post: company, role, pay, region wording, contact (email/ATS link), HN comment id, author.

## 2. Diff against the Hunting sheet
Read Sheet2 as gviz CSV (`gid=1578269214`, fetch from the Sheets tab) and match company names/domains. Buckets: already in sheet (finish incomplete rows; Applied rows are skipped), new. State counts first: posts, remote, passing the geo filter, in sheet, new.

## 3. Vet each new company (one at a time)
Open the company's own careers page / ATS posting in a NEW tab. Pass if: remote and worldwide/India/APAC, or 3+ countries; no India office; not an agency; engineering role (all levels allowed for HN); pay top at or above about $35k or not stated (no pay is NOT a drop); size cap lifted (log size). Verify the role is still OPEN (apply page loads, not "applications closed", not 404). Hard stops (log `Skipped: <reason>`): city-bound/office/hybrid, US citizen/work authorization, India office, agency, closed, non-engineering. Not stops: US/Berlin hours, size, pay unknown, Rust/Go/PHP gaps (say "ramping up"), 10+ years asked. AI-titled roles go to the backlog while that rule stands. A skipped row still gets founder names, emails, website (CLAUDE.md "Skipped companies still get emails and people").

## 3b. Hunting sheet: every column defined (never blank, never "n/a")
Read the header row first and write by header name. Next free row: read `&range=A<n>:A<n+3>` of the gviz CSV for the last filled row (a line count is unreliable); paste a TSV via pbcopy, navigate to `...gid=<gid>&range=A<row>`, wait 6 s, cmd+v, then read the rows back to verify.

**Sheet2 (gid 1578269214), columns A to S**
| Col | Header | What goes in it |
|---|---|---|
| A | Links | The job link: the company ATS/apply URL, else the HN comment `https://news.ycombinator.com/item?id=<id>` |
| B | Email 1 | Primary email: the post's published address first, else `first@<real domain>` marked `(guessed)` / `(published)` |
| C | Email 2 | Next person's email, same marking |
| D | Email 3 and more | All other emails, ` | ` separated; if none: `not found (checked: post, site)` |
| E | Linkedin Profiles | `Name (role): <linkedin.com/in/handle>` for every persona, ` | ` separated, in the same order as B/C/D; missing roles written `CEO: not found (checked: <sources>)` |
| F | Company Linkedin | `https://www.linkedin.com/company/<slug>/`; `not found (checked: ...)` if absent |
| G | Open Source | `none found (GitHub search paused)` while paused |
| H | Companies Website | Real domain from the company's own site |
| I | External Carier Portal to Apply | The real ATS/careers apply URL, or `none found (checked: site, post email)` |
| J | Linkedin | Outreach status in one line: company followed, who got a plain request, who was Blocked, comments posted or the skip reason, date |
| K | Response Recived | `none yet` until a human reply |
| L | Followup Count | `0` |
| M | Followup Date | Plain `YYYY-MM-DD`, application date +5 days (re-check date +30 for skipped rows); the column rejects text |
| N | Added By | `hn-hiring` |
| O | Application Status | One of: `Found`, `Drafted <date>`, `Applied <date> (<ATS>)` (+ ` + drafted`), `Emailed <date>`, `Waiting on user: <what> at <url>`, `Hold: <reason>`, `Skipped: <reason>`, then free-text detail (role, region, pay, gaps) |
| P | Email Sent | `not sent`, or `Sent <date> <time>` |
| Q | Email Failed | Checkbox: paste `FALSE` |
| R | Stage | `Not sent`, `Applied`, `Sent`, `Skipped`, `Replied: ...`, `Interview` ... (CLAUDE.md stage list) |
| S | Stage date | Plain date of the stage |

**Sheet3 (gid 954465790), one row per person, columns A to F**: A LinkedIn handle (after `/in/`), B `<Company> - <Name> (<role>)`, C date, D comments (`1 comment (<post>)`, `none (no posts)`, `none (posts above reaction cap)`, `none (not requested)`), E connection result (`Sent plain`, `Sent with note`, `Pending`, `Blocked: email required`, `Skipped: India`), F notes (`followed profile`, `out of free notes`). Next free row found the same way as Sheet2.

## 4. Per OPEN company, in this order (HARD GATE)
a. Sheet2 row (status `Found`). b. People, every persona that exists: CEO/founders, CTO, hiring manager, HR/recruiter, team lead, senior engineer (LinkedIn `/company/<slug>/people/` and `/search/results/people/?keywords=<name> <company>`; skip India/Pakistan; emails published first else `first@domain` "(guessed)"). c. Apply through the channel the post names, in this order: (1) the company ATS/careers form (Ashby, Greenhouse, Lever, Personio, Recruitee, own page) with the matching role-family PDF, standard answers, truthful free text; "How did you hear": Hacker News "Who is hiring? (<month>)"; (2) if the post says apply by email, that email is the apply step: write the application as a Gmail draft to that address (follow the post's subject line and asks, e.g. GitHub link or a PR); sending needs a named authorization. d. ONE Gmail draft, everyone in To, v2 style, subject `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`, saved by the subject-click method. e. LinkedIn: plain request via `https://www.linkedin.com/preload/custom-invite/?vanityName=<handle>` (verify the name, "Send without a note"; "email required" = `Blocked`; empty dialog = already connected/pending). Comments only when asked. f. Log Sheet2 status, Sheet3 rows.
Stops: video-only question, CAPTCHA, login, a required PR/take-home, a typed-phrase gate. Mark `Waiting on user: <what> at <url>` and continue.

## 4c. LinkedIn outreach (every application, learned 2026-11-08)
Order per company: (1) open `linkedin.com/company/<slug>/` (find the slug via `/search/results/companies/?keywords=<name>`) and JS-click the first button whose text is `Follow`. (2) People: `/company/<slug>/people/` (the keyword filter in the URL does not apply; scan the list) and name searches `/search/results/people/?keywords=<name> <company>`. Pick CEO/founder, CTO or head of engineering, hiring manager (VP/Director/Head of the team), team lead, senior engineer, recruiter. Skip India/Pakistan profiles and Tax Pilot; the 5,000-follower cap does not apply to job outreach. (3) Request: `https://www.linkedin.com/preload/custom-invite/?vanityName=<handle>`; JS-check the dialog names the person; if "Add a note" works, add a note of at most 200 characters (role applied for, one real fit line); if the dialog says "You're out of free custom notes", click `Send without a note`; if it asks for the person's email, log `Blocked: email required` and click Follow on their profile instead. (4) Plain request also gets one comment (4 to 5 lines: who I am, the exact role applied for, one real fit line, no numbers, no India, no contact details) on a recent post with 30 or fewer reactions+comments, else the quietest relevant hiring post; skip with a logged reason when the person has no posts or every post is huge. Open `/in/<handle>/recent-activity/all/`, click the comment icon, click the box, type, screenshot, click the blue Comment button, confirm the comment shows under your name. (5) Verify every request in `/mynetwork/invitation-manager/sent/`. (6) Log Sheet3 and column J.

## 4d. Email (draft only)
One email per company, everyone in To, never Cc, v2 style, subject `<Exact role> - <Company> | Rahul Jha, Atlassian engineer`, plus the post's own subject line and asks when it gives them (a post that says apply by email makes the draft the application). Safety, after the fourth accidental send on 2026-11-08 (ArtCraft email went out while saving): open the compose URL by navigating the Gmail tab, never by script `location.href`; take a screenshot to confirm the tab id, To, Subject and body before any click; save with the subject-click method only when the layout matches (subject about x=1000, y=86); after saving, check that the Drafts count rose and Sent gained no row; if a Sent row appears, tell the user at once and log `Emailed <date> (sent by accident)`. If no safe method is available, hand the draft text to the user instead of saving. Sending needs a named authorization.

## 4e. Bot-check gates
A page that tells applicants to type a phrase ("I am not a robot"), a CAPTCHA or Cloudflare challenge is the user's step. Fill everything else, leave the tab open on the form, mark `Waiting on user`, continue, and log `Applied` only after the confirmation page shows.

## 5. Rules of the run
One company at a time, no parallel agents, no new .md/.csv/.json files, browser only. Never stop between companies and no status reports until the end or a hard stop. Gotchas: Recruitee phone box needs `<PHONE>` typed; file inputs use the upload tool; Personio needs native setters; Ashby needs native setters plus a real Submit click; Gmail save never near Send.

## 5b. Daily refresh
HN posts one thread a month (first business days) and posts keep arriving for ~3 weeks, so run `/hn-hiring` weekly in the first month-weeks and monthly after. The sheet diff makes each run incremental. Order: (1) reconcile Gmail Sent/bounces; (2) finish incomplete rows and `Waiting on user`; (3) sections 1-4 on the new posts; (4) final report. Repeat: `/loop 24h /hn-hiring`; unattended: `/schedule` a routine with the prompt `/hn-hiring`. Older months: `/hn-monthly <month>`.

## 6. Final report (once)
Counts: posts, remote, passing geo, in sheet, new, rejected (reasons), applied, drafted, LinkedIn requests (sent/pending/blocked), HOLD list with the exact user step. End with "My opinion:" (one or two lines).

Diagram: `Commands/Flow Diagram/hn-jobs-flow.md` (and `.mmd`, `.png`).
