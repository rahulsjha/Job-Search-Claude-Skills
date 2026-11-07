---
description: Run the full loop for one posting: analyze, tailor, cold email
argument-hint: <company> <job posting text or URL>
---

For this posting, run in order and stop early if the analysis says no-go:
1. The `/jd` steps (follow `.claude/commands/jd.md`).
2. The `/tailor` steps with the resume chosen in step 1 (follow `.claude/commands/tailor.md`).
3. The `/cold` steps (follow `.claude/commands/cold.md`).

Input: $ARGUMENTS

End with a one-line summary: company, score, resume used, files created.
