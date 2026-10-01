---
name: edit-agenda
description: Change an existing BriefMe agenda by renaming it, or by adding, changing, removing and reordering single blocks by id.
---

# Edit a BriefMe agenda

Use this when the user wants to change an agenda that already exists.

## Identify the agenda

- The latest `edit_token` (create_agenda's, or rotate_edit_token's after a rotation) authorizes a call on its own.
- With a linked BriefMe account, an agenda saved to it is addressed by `share_token` (from
  create_agenda or list_agendas).
- Neither in the conversation: the user can open their edit link in the browser and change
  the agenda there.

Without a linked account, an agenda whose edit token is lost cannot be recovered; create_agenda makes a new one. A share link does not grant edit access.

## Change one thing per call

Every tool that changes an agenda returns the full updated agenda, so `get_agenda` is needed only when block ids
are unknown. Address blocks by their `id`, never by position. `references/tools.md` lists
each tool. Change only what the user named; leave every other block untouched.

## When to send the user to the browser instead

The edit page also adds, changes, removes and reorders blocks in the browser, so small fixes need no tool call. It suits several small changes at once, or a user who is already on
the control page.

## Do not

- Re-create the agenda to change it.
- Change durations the user did not mention to "make it fit"; say what does not fit instead.
