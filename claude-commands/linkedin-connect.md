---
description: Send connection requests and networking comments to the people logged in Sheet3, one at a time, verify each in LinkedIn's sent list, and keep the Connection Request column current. Free-account safe; never uses LinkedIn Jobs.
argument-hint: [ceo-cto | all | <linkedin handle> | comment]  (default: ceo-cto)
---

Read `CLAUDE.md` first (sections "LinkedIn outreach, never LinkedIn Jobs", "LinkedIn networking mode", "Follow the user's instructions exactly"). Input: $ARGUMENTS.

## What this does
Sheet3 (Hunting sheet, gid 954465790) holds every person reached out to. Columns: A `Linkedin Username`, B `Company Name` (with name and role), C `Last Reachout`, D `Comments`, E `Connection Request`, F `Round 2 comments`. This skill sends connection requests to people whose E is `-`, and adds fresh networking comments where there is something new to say.

## Hard rules
- LinkedIn profiles, posts, comments and connection requests only. NEVER LinkedIn Jobs, Easy Apply, or any application button.
- Never solve or bypass a CAPTCHA, security check or restriction page. Never enter a password or log in. If LinkedIn is signed out, stop and tell the user.
- Stop immediately on any LinkedIn warning, "weekly invitation limit", or restriction notice, and report it.
- One person at a time, never parallel. Human pace: no more than about 3 seconds of batching between actions, and a pause between profiles.
- Personalised notes need the monthly free allowance. If "Add a note" shows "You're out of free custom notes", do NOT buy Premium and do NOT withdraw and resend; send plain requests only and say so. The allowance resets about the 1st of the month (3 used on 2026-10-28).
- Do not guess an email to connect. If LinkedIn asks for the person's email, close the dialog and mark the row `Not sent: needs email to connect`.
- Skip people who left the company, India-based companies, ex-titles, and non-founder or non-leader titles unless the user names them. Mark skips in the report.
- Comments are truthful, specific to the post, 1 to 2 sentences, no numbers, no links, no contact details, no job pitch (Mode C networking). Never comment on a post already commented on (check `mine()` counts and column D).

## Choosing who
1. Read Sheet3 through the gviz CSV: `/spreadsheets/d/<id>/gviz/tq?tqx=out:csv&gid=954465790`, parse with a quote-aware parser (cells contain commas and newlines).
2. `ceo-cto` (default): rows where E is `-` and B contains CEO, CTO, Chief Executive or Chief Technology Officer. Then founders. `all`: every row with E `-`. A handle: only that person.
3. Show the list and the skips, then go. Do not ask again mid-run.

## Sending a plain connection request (the flow that works)
The browser window is about 1430x838 or 1395x868 and the page layout shifts by a few pixels, so look at a screenshot before each click. Use `browser_batch` with `{name, input:{...}}` objects.
1. Navigate to `https://www.linkedin.com/in/<handle>/`, wait 6-9 seconds, screenshot at scale 0.4. Coordinates in the screenshot divide by 0.4.
2. If the top card has a direct `Connect` button, click it. If not, click the round `...` button beside Follow/Message. The menu opens either below or ABOVE the button; screenshot, then click `Connect` in the menu. Rough rule: when the menu opens above, `Connect` is about 195 px above the `...` button; when below, about 160 px below.
3. Wait 2 seconds. The dialog "Add a note to your invitation?" appears. Its `Send without a note` button is at about x 870 and y 200 (when the name fits on 2 lines) or y 223-225 (3 lines). Screenshot to see which, then click it.
4. A green toast "Invitation sent to <name>" confirms. If the page shows `Pending`, it worked. If the dialog asks for the person's email, close it (X) and skip.
5. Do not click again when the screenshot is unclear; screenshot first. A click on the wrong spot opens the cover-photo overlay.

## Verifying
After a batch, open `https://www.linkedin.com/mynetwork/invitation-manager/sent/`, scroll twice and read names with `document.querySelectorAll('main li, main [role=listitem]')`. The total `People (n)` shows pending count. A person you already follow may be missing from the list; open their profile and look for `Pending`.

## Logging (every time, in the same pass)
Update Sheet3 column E for each person: `Sent plain YYYY-MM-DD`, `Sent WITH NOTE YYYY-MM-DD`, or `Not sent: <reason>`. Write a contiguous block, never single cells in a loop:
1. Escape any open editor, focus the Name Box with JS (`input.waffle-name-box`), type the start cell (for example `E2`) plus Enter.
2. Paste with a synthetic `ClipboardEvent` on `.cell-input` carrying newline-separated values. If a stray editor opens with the pasted text, press Escape, refocus the Name Box and paste again (the second attempt commits).
3. Read the sheet back through gviz and check counts and 3 known rows. Never paste tab characters into a single cell; tabs go through one block at column A only when adding whole rows.
4. For new comments, also fill column F `Round 2 comments` and column D when it is a first-time person.

## Comment mode (`comment`)
1. Open `/in/<handle>/recent-activity/all/`, wait 5 seconds, and read their own posts with `get_page_text` or `main.innerText.split('Feed post')`. Pick a post newer than the last logged reachout, with about 100 or fewer reactions plus comments, not a repost, not a job ad outside my background.
2. Open the comment box with the saved helpers (`localStorage` key `h`: `eval(localStorage.getItem('h'))`, then `openC(i)`), type the comment with the browser type action, confirm in a screenshot, then `submitC()` and check `mine()` rose by 2.
3. 20+ seconds between comments; stop at any warning. Log in column F.

## Report format
Counts (sent, skipped with reasons, not sent), the list of names, pending total from the sent list, and the sheet read-back result. End with "My opinion:" including the main risk (LinkedIn weekly invitation limit; about 75 plain requests were sent on 2026-10-28/29 with no warning).
