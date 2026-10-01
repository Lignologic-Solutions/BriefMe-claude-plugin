---
name: create-agenda
description: Build a timed meeting agenda in BriefMe from a plain-language description and hand back the share link and the control link.
---

# Create a BriefMe agenda

Creates a timed meeting agenda — a shareable countdown timer that walks attendees through timeboxed topics in sync. Use when the user wants a meeting timer, timeboxes, a run of show, a workshop or standup schedule, or to keep a meeting on time. Not for calendar scheduling or note-taking, and a two-item chat needs no timer.

## Collect before calling

1. The meeting length (ask if it is not stated and cannot be inferred from the meeting type).
2. The topics in order, with rough lengths where the user gives them.
3. Nothing else: no attendee names, no dates, no notes.

## Call create_agenda once

Block durations add up to the meeting length; when none is given, a standup is about 15 minutes, a 1:1 about 30, sprint planning 60 to 90. Most agendas are three to eight blocks. Titles are read off a wall-sized countdown, so six words or fewer read best; a description is useful only when the title alone is ambiguous.

Include the opening, the wrap-up and any planned break in this single call (see
`references/meeting-rules.md`), because every later change is a separate confirmation for
the user. Respect the limits in `references/limits.md`.

## Reply

Give the user both links from the result: `edit_url` (the private control page where the
meeting is started, paused, advanced and finished; it belongs with the owner) and `share_url`
(the read-only live timer, safe to post anywhere). Without a linked BriefMe account the
result also carries `edit_token`, which later calls in this conversation take until
rotate_edit_token replaces it; it does not belong in a shared channel. Block types are
internal and appear on no BriefMe page.

If the result carries `structure_suggestions`, apply them with `add_block` and
`reorder_blocks` before replying, unless the user asked for a different shape.

## Do not

- Invent topics, lengths or a meeting the user did not describe.
- Create a second agenda to fix the first; use the edit tools or the browser editor.
- Schedule anything, send anything, or take notes: BriefMe does none of these.
