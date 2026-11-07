# HN Jobs Flow (skill: `/hn-hiring`)

Source skill: `.claude/commands/hn-hiring.md` (same layout as `/yc-jobs`). This file is the readable copy plus the flow diagram.

Start page (read only): https://news.ycombinator.com/submitted?id=whoishiring

## Diagram v2: end-to-end flow

```mermaid
flowchart TD
    START([/hn-hiring]) --> L1

    subgraph COLLECT["1. Collect (read only on HN)"]
        L1[Algolia: newest Who is hiring thread] --> L2[Fetch all top-level posts<br/>strip HTML, keep remote<br/>drop US-only, EU-only, on-site, agency, non-eng]
    end

    subgraph DIFF["2. Diff against Hunting sheet"]
        L2 --> D1[Read Sheet2 CSV, match company and domain]
        D1 --> D2{Company in sheet?}
        D2 -- Applied --> SKIP([Skip])
        D2 -- Incomplete --> ROW
        D2 -- New --> V1
    end

    subgraph VET["3. Vet on company's own page"]
        V1[Open careers/ATS page in new tab] --> V2{Pass filters?<br/>remote, worldwide or India/APAC<br/>no India office, not agency<br/>engineering, pay ok or unstated}
        V2 -- No --> REJ[Sheet2: Skipped reason<br/>still fill founders, emails, site] --> SKIP
        V2 -- Yes --> V3{Role still open?<br/>not closed, not 404}
        V3 -- Closed --> REJ
        V3 -- Open --> ROW
    end

    subgraph WORK["4. Per open company (HARD GATE order)"]
        ROW[a. Sheet2 row A-S] --> PPL[b. People: CEO, CTO, HM, HR, TL, senior eng<br/>handle, location, email]
        PPL --> CH{How does the post say to apply?}
        CH -- ATS or careers form --> FILL[Upload role PDF, standard answers<br/>How heard: HN Who is hiring]
        CH -- Email --> EM[Application as Gmail draft to the post address<br/>follow its subject and asks]
        FILL --> GATE{Video-only, CAPTCHA,<br/>login, required PR?}
        GATE -- Yes --> WAIT[Waiting on user<br/>link + step]
        GATE -- No --> SUB[Submit, close tab]
        SUB --> DR
        WAIT --> DR
        EM --> DR
        DR[d. ONE Gmail draft<br/>all people in To, subject-click save] --> LI
        LI{India/Pakistan or Tax Pilot?}
        LI -- Yes --> LSK[Log Skipped]
        LI -- No --> LR[Plain connection request<br/>verify name in dialog]
        LR --> LB{Email required?}
        LB -- Yes --> BL[Log Blocked]
        LB -- No --> OK[Sent / Pending]
        LSK --> LOG
        BL --> LOG
        OK --> LOG
        LOG[f. Log Sheet2 status, Sheet3 per person]
    end

    LOG --> MORE{More new posts?}
    MORE -- Yes --> D2
    MORE -- No --> REP([Final report + My opinion])
```

## Rules in one place
- Diff every post against Sheet2 first; only new posts and incomplete rows get work.
- Vet on the company's own page; no pay stated is not a drop; closed, city-bound, India office, agency, non-engineering are.
- Apply by the channel the post names: ATS form, or email (draft to the post's address). Stops: video-only, CAPTCHA, login, required PR.
- One Gmail draft, plain LinkedIn requests, Sheet2 A-S and Sheet3 rows. One company at a time.

## Columns, LinkedIn and email (v3)
- **Sheet2 A to S** each have a defined meaning in the skill (section 3b): A link, B/C/D emails, E people with LinkedIn, F company LinkedIn, G open source, H website, I careers link, J LinkedIn status, K response, L follow-up count, M follow-up date, N added by, O status, P email sent, Q email failed, R stage, S stage date. Sheet3 has A to F per person.
- **LinkedIn (4c):** follow the company page, request CEO/CTO/hiring manager/team lead/senior engineer plainly (note only if LinkedIn still offers one), comment on a quiet post, mark email-required invites `Blocked`, verify in the sent list.
- **Email (4d):** one draft per company, everyone in To; open compose by navigation, screenshot first, check Drafts rose and Sent did not.
- **Bot-check gates (4e):** typed-phrase and CAPTCHA steps are the user's; log Applied only after the confirmation page.

## Change log
- v3 (2026-11-08): all Hunting sheet columns defined, LinkedIn outreach steps, email safety rules, bot-check gates.
- v1 (2026-11-07): flow for leads with no pay stated.
- v2 (2026-11-08): restructured like yc-jobs (collect, diff, vet, per-company gate, daily refresh); added the closed-role check and the email-apply branch.
