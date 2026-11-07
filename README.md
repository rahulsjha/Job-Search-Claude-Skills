# Job-Search-Claude-Skills

Claude Code skills and flow diagrams for a volume remote-job search (personal details replaced by placeholders).

## Layout
- `claude-commands/` slash commands (copy into your project's `.claude/commands/`): `yc-jobs.md`, `daily-jobs.md`, `cold.md`, `apply.md`, `tailor.md`, `jd.md` and more.
- `skills/` resume and job-search skills (`skills/<name>/SKILL.md`).
- `Flow Diagram/` HN jobs flow: `hn-jobs-flow.md`, `hn-jobs-flow.mmd`, `hn-jobs-flow.png` (skill `claude-commands/hn-hiring.md`). YC jobs flow: `yc-jobs-flow.md` (diagrams + applying rules), `yc-jobs-flow.mmd` (Mermaid source), `yc-jobs-flow.png` (rendered).
- `CLAUDE.md` the rules every run follows (fill `<PHONE>` / `<EMAIL>` with your own).

## YC jobs flow (`/yc-jobs`)
Start page: the Work at a Startup remote-engineering list, newest first (read only). Diff against your tracking sheet, vet new roles, apply on the company's own page, log the row, make one Gmail draft, then LinkedIn outreach to CEO, CTO, HM, HR, TL. See `Flow Diagram/yc-jobs-flow.png`.

## Run it
- Once: `/yc-jobs` (or `/yc-jobs 10` to cap new companies).
- Daily in one session: `/loop 24h /yc-jobs`.
- Unattended daily: `/schedule` a routine with the prompt `/yc-jobs`.
- Needs Chrome open and signed in (Gmail, LinkedIn, Google Sheets) with the Claude in Chrome extension. Day 1 does the whole list; later days only new companies, incomplete rows and items waiting on you.

## Hard limits
No CAPTCHA solving, no passwords or account creation, Gmail drafts only unless you authorize a named batch, never Apply or message on workatastartup.com, never LinkedIn Jobs.

## HN jobs flow (`/hn-hiring`)
Same shape as the YC flow, different source: the newest "Ask HN: Who is hiring?" thread (read only). Skill: `claude-commands/hn-hiring.md`. Diagram: `Flow Diagram/hn-jobs-flow.png` (source `.mmd`, readable copy `.md`).

**The flow, step by step**
1. **Collect.** Algolia API gives the thread id and every top-level post. Keep "remote" posts; drop US/EU-only, on-site, agencies and non-engineering.
2. **Diff** against the Hunting sheet (Sheet2). Applied rows are skipped; only new posts and incomplete rows get work.
3. **Vet** each new company on its own careers/ATS page (remote, worldwide or India/APAC, no India office, still open). No pay stated is not a drop. Rejects are logged `Skipped: <reason>` and still get contacts.
4. **Per open company, in order:** sheet row, people (CEO, CTO, hiring manager, HR, team lead, senior engineer), apply (ATS form, or email when the post says so), one Gmail draft, LinkedIn, log.
5. **LinkedIn:** follow the company page; plain connection request to each person (a note only while free notes remain); one 4-5 line job comment on a quiet post; email-required invites logged `Blocked`; verify in the sent list.
6. **Email:** one draft per company, everyone in To; draft only, never sent without a named authorization; check the Drafts count rose and Sent did not.
7. **Stops:** typed-phrase/CAPTCHA gates, logins and required PRs are the user's step (`Waiting on user`); the run continues.

**Hunting sheet columns (Sheet2 A-S, none blank):** A link, B/C/D emails, E people with LinkedIn, F company LinkedIn, G open source, H website, I careers link, J LinkedIn status, K response, L follow-up count, M follow-up date (plain `YYYY-MM-DD`), N added by, O status, P email sent, Q email failed (`FALSE`), R stage, S stage date. Sheet3 logs one row per person (handle, company - name (role), date, comments, connection result, notes).

- Once: `/hn-hiring` (or `/hn-hiring 3 latest <company names>` to work named leads).
- Daily: `/loop 24h /hn-hiring` or `/schedule` a routine with the prompt `/hn-hiring`.
