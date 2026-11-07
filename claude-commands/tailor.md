---
description: Tailor the closest base resume (.tex) to a job posting without fabricating
argument-hint: <resume: ai|ds|fullstack|infra> <company> <job posting text or URL>
---

Read `skills/resume-tailor/SKILL.md` and follow it. Also read `CLAUDE.md`.

Input: $ARGUMENTS

Steps:
1. Map the first word to the base file: ai = `AI Engineer.tex`, ds = `Data Scientist.tex`, fullstack = `full stack.tex`, infra = `infra.tex`. If it is missing, choose the closest and say why.
2. Copy the base file to `<Role> - <Company>.tex` in this folder. Never edit the base file.
3. In the copy, change only content: summary, skill order, bullet wording and order, keywords. Leave the preamble and macros alone. Keep it at 2 pages.
4. Do not invent employers, titles, tools or metrics. Use only facts already in the resumes or that I confirm.
5. Report a short diff summary of what changed and why. Do not compile unless I ask.
