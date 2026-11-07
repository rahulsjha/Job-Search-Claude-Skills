---
description: LinkedIn outreach to founders, CTOs and hiring leads of companies that have a job open. Comment on their last 4-5 quiet posts, send a short connection request, and log each person in Sheet3. Never uses LinkedIn Jobs.
argument-hint: [company or linkedin.com/in/<handle> | "next" to take the next company from the Hunting sheet]
---

Read `CLAUDE.md` first (section "LinkedIn outreach, never LinkedIn Jobs"). Input: $ARGUMENTS. If it is `next`, take the next company in the Hunting sheet (Sheet2) that has a live job, people in column E, and no row yet in Sheet3.

## Hard rules
- NEVER use LinkedIn Jobs, Easy Apply, or press Next/Submit on an application. LinkedIn is only for profiles, posts, comments and connection requests.
- Only reach out to people at a company that currently has a job open (check the sheet row, the Wellfound/Arc/YC/ATS posting). Targets: CEO/founders, CTO/head of engineering, and the hiring manager or recruiter for the role. Real people only, from the sheet, the company LinkedIn People tab or the team page. Never invent a person.
- Truthful, short, human. No numbers, no savings, no India mention, no hours. Atlassian only as "most recently SDE II at Atlassian". Comments must be about the open role (see step 3).
- Pace like a person: 20+ seconds between comments, a few people per session. Stop at any LinkedIn warning, CAPTCHA or rate limit and tell the user.

## Steps for each person (one person at a time, never parallel)
1. Open `https://www.linkedin.com/in/<handle>/recent-activity/all/` and read the posts. Use only their OWN posts (skip reposts). For each post note likes and comments; qualify only if likes + comments is 30 or fewer.
2. Pick their last 4 to 5 qualifying posts. If fewer qualify, comment on those and say how many.
3. Write one comment per post, 1 to 2 sentences, specific to what the post says (quote or answer its point), no emoji, no link. JOB-RELATED: say I am interested in the open <role> and give one real fit line tied to the post; never generic congratulations. Show the text, type it in the comment box, post it, and confirm it appears under the user's name.
4. Connection request: profile top card, `More` (three dots) then `Connect` (or the Connect button), `Add a note`. The note is at most 200 characters (free account: only 5 personalised notes per month, so use notes for CEO/CTO/hiring lead first; for others send without a note). Example: "Hi <first name>, I'm a <role-family> engineer (most recently SDE II at Atlassian). Saw <Company> is hiring a <role> and enjoyed your post on <topic>. Let's connect." Check the counter shows 200 or less before Send.
5. Log in the Hunting sheet tab Sheet3 (gid 954465790): A `Linkedin Username` (handle after /in/), B `Company Name`, C `Last Reachout` (YYYY-MM-DD). Append one row per person, never delete. If the person is already there, update `Last Reachout` only.
6. Add a short note to the company row in Sheet2 column N: `LinkedIn: commented <n> posts, connection sent <date>`.

## Mode B: hiring posts found by LinkedIn content search (user, 2026-10-25)
Use when the input is `search` or a post link. Find software/AI/data/infra engineer hiring posts, then reply under the post. No connection request in this mode.
1. Open `https://www.linkedin.com/search/results/content/?keywords=<query>` (queries such as `looking for ai engineer remote`, `hiring ai engineer remote`, `hiring backend engineer remote`, `hiring devops engineer remote`, `hiring full stack engineer remote`). Sort by latest, read the result posts.
2. Qualify a post when it is a real hiring post for an engineer role that is remote or open to anywhere. Do NOT skip a post because it lists no salary or asks for more years of experience. Skip only: on-site/hybrid-only, US-only or citizen-only, not an engineering role, a post already above 30 likes plus comments (a quiet post is more likely to be read), a post that already has a comment from the user.
3. Four short comments in total (user, 2026-10-25), never several on the same post:
   - ONE comment on the main job post (max 2 sentences, about 30 words, specific to the role and stack, no contact details, no links, no numbers). Template: "Hi <first name>, this is a close fit: I'm a <role family> engineer (most recently SDE II at Atlassian) working with <2 of the post's stack words>. Happy to share more."
   - THREE comments on three DIFFERENT recent posts of the same person (open `/in/<handle>/recent-activity/all/`, their own posts only, 30 or fewer likes plus comments). Each is 1 to 2 sentences answering that post's own point, JOB-RELATED (user, 2026-10-25): each comment is how we reach them about the open role, so it names the role and one real fit line; never generic congratulations or networking.
   - Then a connection request with a note of at most 200 characters (free account: only 5 notes per month, otherwise send without a note). Template: "Hi <first name>, saw your <role> opening. I'm a <role family> engineer (most recently SDE II at Atlassian) and it looks like a close fit. Would love to connect."
   No email or phone in comments or notes unless the person asks for it. 20+ seconds between comments.
4. Log the poster in Sheet3: A username (handle from the profile or post URL), B company (or "recruiter, company not named"), C date, D what was done.
5. Staffing agencies and consultancies posting for clients are included in this mode (user said do not ignore them); note "agency" in column D.

## Mode C: networking comments (user, 2026-10-26; input `network`)
Goal: build a network of founders and CTOs who may offer jobs in future. Target: 500 comments in total, 3 comments per person across 167 people. User 2026-10-26: keep going without stopping, stop ONLY at a CAPTCHA or LinkedIn warning. ONE person at a time, never parallel, a few people per session, resume from the Sheet3 count each time.
This mode is NETWORKING, not job-related: it overrides the "comments are job-related" rule for Mode C only (Modes A and B stay job-related).
1. Find people: founders, CEOs and CTOs / heads of engineering of startups (size up to about 200, product or engineering focus, preferably remote-friendly or overseas) who post on LinkedIn about building products, AI, engineering or hiring. Sources: Sheet2 people (column E), LinkedIn content search, company People tabs, people who comment on those posts. Real people only; skip recruiters-only, aggregators, spam accounts, India-based companies, anyone already in Sheet3 with 3 comments done.
2. For each person open `/in/<handle>/recent-activity/all/`, use their OWN posts only (no reposts, no job ads), recent ones, 30 or fewer likes plus comments. Comment on 3 DIFFERENT posts, never twice on the same post. If fewer than 3 qualify, do the ones that do and note it.
3. Each comment: 1 to 2 sentences, specific to that post's point (add a real thought, a short relevant experience from the resumes, or a good question), no emoji, no links, no numbers, no pitching, no contact details, no flattery filler. Truthful: never claim experience I don't have. Show the text, post it, confirm it appears under "Rahul Jha".
4. Connection request: no note by default (free account has only about 4 personalised notes left this month); use a note (200 characters or less) only for strong CEO/CTO targets.
5. Log in Sheet3 (gid 954465790): A username, B company, C date, D `networking: 3 comments` (post topics, short; whether connect sent). Keep a running total in the report: comments done of 500, people done of 167.
6. Pacing: 20+ seconds between comments, a pause between people, at most about 10 comments per session, stop at any LinkedIn warning, CAPTCHA or rate limit and tell the user. Never use LinkedIn Jobs.

## Sheet and browser method
- Sheet cell entry: focus the Name Box with JS (`document.querySelector('input.waffle-name-box').focus()` then select), type the cell (e.g. `A3`), Return, confirm the Name Box value, then type the values with Tab between cells and Return at the end. Verify afterwards. Never type before confirming the active cell.
- Dismiss the Google account popup first if it shows. Waits longer than 10 seconds must be split into several waits.
- A permission denial on a click means the user declined that action: do not retry the same click, report it.

## Report (fixed structure)
Per person: name, role, company, posts commented (count and what each said, short), connection sent (with or without note), Sheet3 row added. Then totals, invitations left this month if LinkedIn shows it, and the next person to do.

## Mode C sourcing and thresholds (user, 2026-10-26: "go ahead, stop only for CAPTCHA")
- Pool: Sheet2 column E founders/CEOs/CTOs (about 288 profiles), one at a time, then LinkedIn content search. Skip anyone who left the company, recruiters, India-based companies, and accounts with no posts in the last 6 months.
- Networking-mode threshold: likes plus comments of 100 or fewer (the 30 cap stays for Modes A and B), own posts only, preferably from the last 6 months. Never comment on posts older than a year.
- Check method: open `/in/<handle>/recent-activity/all/`, read `document.querySelector('main').innerText` through JS (compact), pick 3 own posts, comment on each with 20+ seconds between, then log in Sheet3.

## Never stop until blocked (user, 2026-10-26)
Once the user says go, run the whole pool (Mode C: about 288 profiles, target 500 comments and 167 people). Do not stop to ask, summarise or wait for approval. The only stops are a CAPTCHA, a LinkedIn warning or restriction, or a blocked account. Skip unusable people and keep going.

## HARD RULE (user, 2026-11-01): no India or Pakistan
Before ANY comment or connection request, read the profile location line. If it is in India or Pakistan, skip the person and log `Skipped: India` or `Skipped: Pakistan` in Sheet3 column D. Never comment, connect or message them. Applies to all modes.
