---
description: Analyze a job posting against my resumes (match score, gaps, which resume to use)
argument-hint: <job posting text or URL>
---

Read `skills/job-description-analyzer/SKILL.md` and follow it. Also read `CLAUDE.md` for my background and job filters.

Job posting: $ARGUMENTS

If that is a URL, fetch it. Then read the four resume `.tex` files in this folder and produce:
1. Match score and the real technical priorities (ignore wish-list filler).
2. Gaps, stated honestly.
3. Remote/location/pay check against my filters (remote, hires from India or globally, $35k+/yr). Flag any dealbreaker first.
4. Which base resume to use and why.
5. Go / no-go recommendation and the next step.
