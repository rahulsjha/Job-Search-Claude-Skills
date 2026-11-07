# Job-Search-Claude-Skills

Claude Code skills and flow diagrams for a volume remote-job search (personal details replaced by placeholders).

## Layout
- `claude-commands/` slash commands (copy into your project's `.claude/commands/`): `yc-jobs.md`, `daily-jobs.md`, `cold.md`, `apply.md`, `tailor.md`, `jd.md` and more.
- `skills/` resume and job-search skills (`skills/<name>/SKILL.md`).
- `Flow Diagram/` HN jobs flow: `hn-jobs-flow.md`, `hn-jobs-flow.mmd`, `hn-jobs-flow.png` (skill `claude-commands/hn-hiring.md`, section 6). YC jobs flow: `yc-jobs-flow.md` (diagrams + applying rules), `yc-jobs-flow.mmd` (Mermaid source), `yc-jobs-flow.png` (rendered).
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
Newest "Who is hiring?" thread via Algolia (read only). Leads with no pay stated are not dropped: vet on the company's own ATS page, apply, find every persona, one Gmail draft, plain LinkedIn requests, and a sheet row with every column filled. See `Flow Diagram/hn-jobs-flow.png`.
- Once: `/hn-hiring` (or `/hn-hiring 3 latest <company names>` to work named leads).
- Daily: `/loop 24h /hn-hiring` or `/schedule` a routine with the prompt `/hn-hiring`.
