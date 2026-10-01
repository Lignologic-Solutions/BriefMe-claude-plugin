---
name: delete-agenda
description: Delete a BriefMe agenda permanently, or release a saved one from the linked account, after confirming which agenda the user means.
---

# Delete a BriefMe agenda

## Confirm first

Before deleting or releasing, name the agenda (its title, and its share link if it is in the
conversation) and ask the user to confirm. Deletion is permanent: the share link and the
edit link stop working at once, the timer history goes with it, and nothing can be
recovered. A release is final too: the agenda cannot be returned to the account.

The initial request (even "delete it permanently") is not this confirmation.
Reply with a confirmation question and END YOUR TURN without calling delete_agenda
or release_agenda. Wait for a subsequent user message approving that specific action
on that specific agenda. Only then call the tool. If the user cancels, do not call it.
A tool permission setting or earlier approval for another action is not confirmation.

## Choose the tool

- `delete_agenda`: permanent removal. Takes the latest `edit_token` (create_agenda's, or rotate_edit_token's after a rotation),
  or `share_token` for an agenda saved to a linked account.
- `release_agenda` (linked account only): the agenda leaves the account for good (it cannot
  be returned to it) and expires after 7 days; its share link keeps working until
  then. It suits a user who wants to free a slot, not to destroy the agenda.

## Reply

Say what was deleted or released, and that the links no longer work (or when they stop).

## Do not

- Delete or release without an explicit confirmation in this conversation.
- Guess which agenda when several are in play; ask.
