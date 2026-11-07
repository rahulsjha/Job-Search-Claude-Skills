---
description: Research founders and recruiters, then write cold emails (A early-team intro, B applied, C small idea, D follow-up) as Gmail drafts. Never sends
argument-hint: <A|B|C|D> <company> <job posting or company URL> [--no-gmail]
---

Also read `CLAUDE.md` for my background and rules. Everything needed to write the email is below; do not look for any other skill.

Input: $ARGUMENTS

If the first word is not A, B, C or D, choose with the "Choosing a Template" table and say which one. Research the company first (fetch the URL, or use the browser for Wellfound pages). Find the recipient's real first name per Hard Rule 8. By default also create the Gmail drafts using the Gmail Draft Workflow at the end of this file (skip Gmail only if I pass --no-gmail). Follow the Output Format and Final Check exactly.

# Cold Email Writer (Final Version)

## When to Use This Skill

Use when the user wants to:
- Email a founder, hiring manager, or recruiter directly
- Reach out after applying, or ask about early-team openings with no posted role
- Follow up on an unanswered email
- Mentions: "cold email", "cold apply", "reach out", "intro email", "outreach", "follow up"

## Style

Personal, direct and human, like a builder writing to another builder. Every email (A, B, C) opens with a short **TL;DR** line, then "Hi [First name],", then a specific hook, then what Rahul has built, then a warm close. Never salesy, never a pasted resume.

## Hard Rules (apply to every email)

1. Use ONLY the four templates below. Pick one, fill it, keep the wording close. No extra sections.
2. **No cost reductions and no specific numbers.** No percentages, RPS, latency, event or user counts, dollar amounts, or "5+ years". Describe Atlassian work qualitatively: what was built, owned and shipped. Resumes keep their metrics; outreach does not (`CLAUDE.md` rule 7).
3. **Always fill the requirement and the one-line example yourself** (`CLAUDE.md` rule 6). Map the posting's key requirement to a real example from the resumes. If the posting text is unavailable, infer from title, company page and product, and say in one short line that it was inferred.
4. **Be specific, never generic.** The hook and the TL;DR must reference something real from the company's own materials (launch, post, product, hiring page) and show general understanding of what the company does. No "I love what you're building" on its own.
5. **Facts only from the resumes in this folder.** Do not invent employers, tools, projects, links, hobbies or personal traits. Never copy claims from other people's sample emails. Use only these links: https://context.dev, https://lokuma.ai/design-agent, https://kipps.ai, github.com/rahul-jha98 and its projects, linkedin.com/in/rahul-jha98.
6. Do not say Rahul is leaving Atlassian. Say "open to new opportunities" only if needed.
7. If the role is outside India, mention being based in India casually and early. Never imply US residency. If sources conflict on eligibility (for example Wellfound says remote everywhere but the company page says the Americas), do not stop: say so in one honest line in the email (ask whether India-based candidates are eligible), flag it in the report, and continue drafting and logging. Do not submit the company's application form; that stays with me.
8. **Always find and fill the recipient's first name.** Look in this order: the job post itself (poster, "hiring manager", recruiter, contact line, apply email), the Wellfound company People tab and "recruiter recently active" info, the company's team/about/careers page, the founder or hiring-manager LinkedIn, then a web search for the company's founder or head of the relevant team. Pick the person most likely to read it (founder or CTO at a small startup, the hiring manager for a posted role). Never invent a name and never guess one from an email address. Only if no real person can be verified, leave `[First name]`, say what was checked, and say who to look for.
9. "Resume attached" only if a resume is actually attached.
10. Length: A up to about 220 words; B and C up to about 170; D is two lines.

## Research Before Writing

1. Company: website, JD, launch posts, product. Find one specific, real thing.
2. Recipient: find the real first name and role using Hard Rule 8 (job post, Wellfound People tab, team page, LinkedIn, web search). Do this before drafting, and state in the output who it is and where the name came from.
3. Closest base resume, and the 1-2 most relevant projects.
4. For Template C, actually try the product first. No real observation, no Template C.

## Templates

### A: Early-team intro (no posted role)

```
Subject: Engineer for your early team – [Company]

TL;DR: I love what [Company] is doing with [one specific thing]. Building is what I do best, and I want to be part of taking something from 0 to 1 or 1 to 100. I just want to be heads down chasing that goal.

Hi [First name],

Really loved what you're building at [Company], especially [one specific thing: a feature, launch, or post]. I wanted to reach out to see if there are any openings for engineers on the early team.

I've spent my career building production, data-driven backend and full-stack systems. I'm currently an SDE II at Atlassian (joined as an intern and grew into the role), and alongside that I've worked as an AI engineer on the early teams at Context.dev (https://context.dev), Lokuma (https://lokuma.ai/design-agent) and Kipps.AI (https://kipps.ai), where I helped ship web-to-LLM and RAG pipelines, MCP integrations for AI coding agents, and voice and WhatsApp agents used by real customers.

Being part of lean teams, one of my strongest suits is working across the stack: scalable, robust backend systems and high-throughput data pipelines (Python, FastAPI, Node and Go on AWS and GCP over Kubernetes) through to production-grade frontends in React and TypeScript. I care about event-driven design, observability and testing, so things hold up in production.

I would love to be part of the early team at [Company] and help define its work and culture. Happy to hop on a quick call whenever suits you. Resume attached.

Best,
Rahul Jha
linkedin.com/in/rahul-jha98 | github.com/rahul-jha98
```

Adapt the stack sentence to the role family: Full Stack (React, TypeScript, Node), Infra (Kubernetes, Terraform, GitOps), Data Scientist (ML pipelines and the CIKM paper), AI Engineer (agents, RAG, MCP).

### B: Just applied, reaching out directly

```
Subject: [Job title] application – Atlassian engineer, [role-relevant focus]

TL;DR: I just applied for the [Job title] role at [Company]. I build production backends at Atlassian and [role-relevant work] on the side, and I'd love to be heads down building [what the company builds].

Hi [First name],

I just applied for the [Job title] role (ID [number if listed]) and wanted to reach you directly. [One plain sentence showing general understanding of what the company does.]

I'm an SDE II at Atlassian (joined as an intern and grew into the role), where I build and own production backend services and data pipelines that other teams rely on. Alongside that I work as an AI engineer on early teams, building [role-relevant work, e.g. conversational AI agents, LLM tooling and MCP integrations].

The role mentions [requirement from the posting]; I've done exactly that with [one-line example, no numbers].

A few quick links, if useful:
- [Project 1]: [link]
- [Project 2]: [link]
- GitHub: github.com/rahul-jha98

Would you be open to a short chat about the team? Happy to work around your schedule.

Best,
Rahul Jha
linkedin.com/in/rahul-jha98
```

Only send after the application is actually submitted. Drop "(ID ...)" if none is listed. Pick 1-2 projects from the allowed links that fit the role.

### C: Small idea / unsolicited improvement

```
Subject: Small idea for [Company]'s [feature]

TL;DR: I tried [product/feature] and put together a quick [prototype / write-up / fix] for [what it improves]. I'd love to build this kind of thing with you full-time.

Hi [First name],

I tried [product/feature] and noticed [specific observation, e.g. the agent fails on JS-heavy pages / responses feel slow].

I put together a quick [prototype / write-up / fix] showing one way to [improve it]: [link]

I'm an SDE II at Atlassian who builds LLM agents and production backends on the side for early teams (Context.dev, Lokuma, Kipps.AI), and I'd love to do this kind of work at [Company]. Open to a quick chat?

Best,
Rahul Jha
linkedin.com/in/rahul-jha98 | github.com/rahul-jha98
```

Requires a real observation and a real link. If either is missing, do not use this template.

### D: Follow-up (standard, user-approved 2026-10-31; replaces the old one-liner)

Subject: `Re: <original subject>` (so it threads under the first email). To: only the addresses from the first email that were delivered (published first; never bounced ones; never Cc). One email per company.

```
Hi [first names or "team"],

[Opener naming the exact role: "I wanted to bump my earlier email about the <role> role." / "Circling back on the <role> role I wrote about last week." / "Quick follow-up on my note about the <role> role." / "Just checking whether the <role> role is still open and my earlier note reached you."]

[ONE real fact from my work for the role family, no numbers:
 AI: MCP servers for coding agents and RAG voice agents on LangGraph (Context.dev, Kipps.AI, Lokuma).
 Infra: Kubernetes, Terraform, ArgoCD, GitHub Actions, OpenTelemetry and Datadog at Atlassian.
 Data: Kafka and Spark pipelines at Atlassian, CIKM 2023 paper.
 Full stack/backend: backend services and data pipelines at Atlassian, Python/TypeScript/Go/React, FastAPI/Node/PostgreSQL/Redis.]

[Short ask, one of: "Would you be open to a short chat about the team?" / "Happy to jump on a short call whenever suits you. Would that be possible?" / "Is there a good person to talk to about this role, or a time for a short chat?"]

Resume (<family>): <the ONE matching resume link>

Best,
Rahul Jha
https://www.linkedin.com/in/rahul-jha98/
```

Rules: 4 short blocks, about 60-80 words; no numbers, no India or hours, no praise of the company; vary the opener and ask across companies; companies with several roles say so in the opener. Send one follow-up about 5-7 days after the first email, only if there is no reply and the role is verified open; at most one last short note about 10 days later. Skip rows marked Skipped, Closed, Replied or Rejected. The user sends; Claude only drafts.

## Choosing a Template

| Situation | Template |
|---|---|
| No posted role, want to ask about early-team openings | A |
| Already applied through the form or Wellfound | B |
| You can show something concrete about their product | C |
| No reply after about 5 days | D |

## Output Format

1. One line: which template and why.
2. The email in a plain code block, plus 2 alternative subject lines.
3. One line noting anything inferred (for example, requirement mapping when no posting text was available).
4. The recipient line: "To: [Full name], [role], source: [where found]". Only brackets that truly cannot be known may remain (a verified name that could not be found, links not in the resumes, job ID).
5. The day-5 follow-up (Template D) filled in.

## Final Check Before Output

- TL;DR present (A, B, C), specific and in Rahul's voice.
- No numbers, no cost or savings claims, no "5+ years".
- Hook is real and specific. Requirement and one-line example are filled.
- Every fact and link comes from the resumes. No invented hobbies or traits.
- Location disclosed if needed. No hint of leaving Atlassian.

## Company Size Cap

Never draft, send to, or log a company with more than 200 people (`CLAUDE.md` rule 11). Check the size band on Wellfound (accept only 1-10, 11-50, 51-200) and cross-check the company's site, LinkedIn or press; if any trusted source shows more than 200, or the size is unclear, stop for that company, say why, and ask me before drafting. Do not add it to the tracking sheet.

## Trusted Sources (only these)

Find companies, founders, domains and emails only from:
1. **Wellfound**: job post, company page, People tab, "Meet your team".
2. **Y Combinator**: ycombinator.com company directory and founder profiles, Work at a Startup.
3. **LinkedIn posts and profiles only. Never LinkedIn Jobs.** Hiring posts by founders or recruiters are useful; job listings are not a source.
4. **a16z**: portfolio and jobs pages.
5. **Other websites**, only if they give a verifiable founder name, company domain or email: the company's own site (about, team, careers, contact, press), its GitHub org, Product Hunt and similar public pages.

Goal order: (1) a verified email from one of these sources; (2) if no email exists, the founder's real name plus the company's real website domain, then `firstname@domain` marked "(guessed)". Record the source for every name, domain and email in the Final Report. Do not use paid or scraped email lists, leaked data, or anything that cannot be cited.

## Recipients (founders and recruiters)

For every run, build the recipient list, not just one person:
- **All founders and C-level** listed for the company (at 1-200 person startups, founders come first).
- **3 to 4 recruiters, talent or hiring-manager contacts** most relevant to the role family. Skip people marked former and duplicates.
- For each: full name, role, source, and whether the listing looks current (Wellfound People data can be stale). Never invent a person; if fewer exist, use fewer and say so.
- Founders get a builder-to-builder hook; recruiters get a role-focused hook (Template B once I have applied, otherwise A).

## Email Addresses

1. Find the company's real domain from its website, not a guess.
2. Look for a verified pattern (job post apply email, team or press page, public search). Use it if found.
3. If none is verifiable, use `firstname@domain` and mark it **UNVERIFIED (guessed)**. Real first name only, lowercase, no spaces or accents. If two people share a first name, flag it instead of guessing.
4. Guessed addresses can bounce or reach the wrong person; I review them before anything is sent.

## Message Format (professional, scannable, not text-heavy)

- One separate draft per recipient. Never put several people in To, Cc or Bcc.
- Subject on its own line, short and specific.
- Body target: about 110 to 150 words, at most 3 short paragraphs of 1 to 3 sentences each, one blank line between them. No walls of text; cut anything generic.
- **Bold** the label "TL;DR:" only. Greeting with the real first name comes after the TL;DR line.
- Links are a short bulleted list under "Quick links:", one per bullet, written as a label plus the full `https://` URL (for example `https://github.com/rahul-jha98`) so Gmail turns each into a clickable link. Never leave bare `github.com/...` text.
- Close with "Best," then name, then `LinkedIn: https://linkedin.com/in/rahul-jha98` on its own line (clickable).
- Plain clean text otherwise: no emojis, no ALL CAPS, no fancy symbols.
- Remove the line "Resume attached" unless a resume is genuinely attached. I attach the PDF myself before sending.
- Do not create local .md or log files. The report is given in chat only.

## Gmail Draft Workflow (never send)

**Never send.** Never click Send, never press Cmd/Ctrl+Enter, never schedule. Only save drafts. If a send control is ever the next step, stop and ask me.

For each recipient:
1. Open `https://mail.google.com/mail/u/1/#inbox?compose=new` in my browser. Confirm it is Gmail and the signed-in account is mine; if a login or account chooser appears, stop and tell me.
2. Click To, type the email address, press Tab.
3. Click Subject and type it.
4. Click the body and type the email with real line breaks. Use Ctrl/Cmd+B around "TL;DR:", and the toolbar bullet list for the links. Type each URL in full (https://...) followed by Enter or a space so Gmail links it.
5. Screenshot to confirm To, Subject, body, that the links are blue and underlined (clickable), and that the layout is not cramped. If a step fails or lands in the wrong field, fix it (discard only a draft you just created in error) and retry up to 5 times, changing the method each time (click the field, screenshot before typing, use Tab or keyboard focus, reload compose). Only after 5 failed tries stop and tell me. Never leave a wrong draft behind.
6. Close the compose window with the X (or Esc) so Gmail saves it to Drafts. Do not click Send and do not discard.
7. Start a fresh compose window for the next recipient.
Afterwards open Drafts once and confirm the count matches.

## Tracking Sheet (log every message)

Whenever a cold email or apply message is created (Gmail draft or chat-only), add one row to the Google Sheet "Hunting", tab **Sheet2** (gid 1578269214):
https://docs.google.com/spreadsheets/d/1RQilpuvQiClxvdNOaHG8yDC6Gm8UepZdAoWIi-tU6vo/edit?gid=1578269214#gid=1578269214

Columns, in order:
- A **Links**: the job post URL.
- B **Email 1**: first recipient email (add "(guessed)" if unverified).
- C **Email 2**: second recipient email, or blank.
- D **Companies Website**: the company's real website.
- E **Linkedin**: the LinkedIn URLs of the people emailed, as "Name: URL | Name: URL". Always look for them before writing "Not found": on the job post page, names inside the "About <Company>" text and the "Meet your team" section are often links to linkedin.com/in/... (use the browser's find/read_page tool to read the link targets), plus the Wellfound People tab and the company site. Fall back to the company LinkedIn page only if no person link exists, and write "Not found" only after checking all of these.
- F **Followup Count**: how many follow-ups have been sent so far; use 0 for a new row.
- G **Followup Date**: the date the next follow-up is due (today plus 5 days for a new draft), written as a plain date like 2026-10-15.
- H **Added By**: who created the row. Use `/cold` when this command adds it. Rows added earlier by `/find-jobs` say `find-jobs agent`; leave that value as is.

Rules: append to the first empty row below the header; never overwrite or delete existing rows; if the same job link is already in column A: when that row came from the `find-jobs agent` with blank emails, fill B, C, E, G in that same row instead of adding a new one, otherwise skip; use my logged-in browser (the sheet may open under a different Google account than Gmail, which is fine) and screenshot to verify the row. Use the 5-try retry rule if a cell does not take the text. If the sheet cannot be edited, give me the row text in chat. Add the row in the Final Report too.

## Final Report (replaces Output Format step 4 when drafting)

A table: Name | Role | Email | Verified or guessed | Source | Template | Subject. Then say how many drafts were created and that none were sent, and what I must do before sending (verify guessed emails, attach resume PDF, review each draft). Flag anything skipped or uncertain. Include the row added to the tracking sheet.

---
## NEW STANDARD TEMPLATE (2026-10-14, overrides Templates A/B wording and length; use for every draft)
Short, structured, specialised. Every section is 3-4 short lines max; whole body about 100-130 words. No numbers. One resume link. Never generic: name the posting's exact role and stack and one real thing the company does.

```
Subject: <Exact role title> - <Company> | Rahul Jha, Atlassian engineer

**TL;DR:** <Role> at <Company>: I build <their stack/what they build> and want to be heads down on <their product>.

Hi <First name or "team">,

**Why <Company>**
<1-2 lines: one specific thing they build / why it fits>. I'm based in India, happy to work <company time zone window or "your time zone">.

**Who I am**
Most recently SDE II at Atlassian (joined as an intern, grew into the role), owning production backend services and data pipelines. Alongside, AI engineer on early teams (Context.dev, Lokuma, Kipps.AI).

**Why I fit** (2-3 bullets, posting requirement -> real example, exact stack words; gaps = "ramping up")
- <requirement 1>: <real example>
- <requirement 2>: <real example>
- <gap if any>: ramping up, closest is <real experience>

**Quick links**
<project 1 url>
<project 2 url>
Resume (<family>): <resume url>
GitHub: https://github.com/rahul-jha98

Open to a short chat about the team?

Best,
Rahul Jha
LinkedIn: https://www.linkedin.com/in/rahul-jha98/
```
Bold only the TL;DR label and the section labels. Applies to all existing drafts too: rewrite them into this format.

---
## STANDARD TEMPLATE v2 (2026-10-14) - overrides everything above for tone/format
```
Subject: <Exact role> - <Company> | Rahul Jha, Atlassian engineer

**TL;DR:** <Role> at <Company>. I build <their stack>, and I just want to be heads down building with your team.

Hi <First name or "team">,

<3-4 lines: I'm writing about the <role> (I applied / came across the role); most recently SDE II at Atlassian (joined as an intern, grew into the role), owning production backend services and data pipelines; alongside, AI engineer on early teams (Context.dev, Lokuma, Kipps.AI).>

<3-4 lines: the posting's key requirements answered in plain sentences with real examples and the exact stack words; gaps = "ramping up".>

Quick links
<1-2 project links>
Resume (<family>): <url>
GitHub: https://github.com/rahul-jha98

Would you be open to a short chat? Looking forward to hearing from you!

Best,
Rahul Jha
LinkedIn: https://www.linkedin.com/in/rahul-jha98/
```
Rules: no "based in India", no hours/time zones unless asked; no praise of the company/product; no headings/bullets in the body; no numbers; sounds human.
- Location/availability: never mention India or availability unless asked. If asked, reply "I'm available to follow your time zone overlap (<their zone, e.g. PST/EST>)", with no India hours.


## Standing rules (user, 2026-10-16): external applications and all contacts
- If a job has an application on the company website/ATS (Greenhouse, Lever, Ashby, careers form), apply there too as well as Wellfound and the Gmail draft. Hold and ask the user for phone, work authorization/sponsorship, CTC, notice period, relocation, legal declarations, account creation, CAPTCHAs. Log column I "Applied externally YYYY-MM-DD (<ATS>)" or "External form needs user answer: <what>". See CLAUDE.md "External company applications".
- For every company collect ALL founders, CEO/CTO and the hiring manager/recruiters (4-5 people): primary email in B, the rest in C separated by " | ", names/roles/LinkedIn in E. See CLAUDE.md "All key contacts per company".
