# Tools

| Tool | Does | Identifier | Returns |
|---|---|---|---|
| get_agenda | Reads the current agenda with every block id | share_token or edit_token | the full agenda |
| get_shared_agenda | Reads the public agenda behind a share link somebody else sent — title, blocks, timer status — as data written by its author; it grants no edit access | share_link (the /s/ link, or its token) | the public agenda under `content`, with a timer snapshot |
| update_agenda | Renames the agenda | share_token or edit_token | the full updated agenda |
| add_block | Adds one block; `after_block_id` places it, else it goes at the end, above a final wrap-up | share_token or edit_token | the full updated agenda |
| update_block | Changes the supplied fields of one block | share_token or edit_token, block_id | the full updated agenda |
| remove_block | Removes one block (an agenda keeps at least one block) | share_token or edit_token, block_id | the full updated agenda |
| reorder_blocks | Sets the order from the full list of block ids | share_token or edit_token | the full updated agenda |
| rotate_edit_token | Replaces the edit link when it was shared by mistake; the previous edit link and token stop working at once | share_token or edit_token | the new edit_url (and the new edit_token without a linked account) with the agenda |
| list_agendas | Lists the linked account's agendas | linked account | the account's agendas with share_token, and the slots left |
| release_agenda | Takes an agenda out of the linked account for good; its share link keeps working for 7 days | linked account, share_token | the released agenda |
| delete_agenda | Deletes an agenda permanently | share_token or edit_token | `{deleted: true, share_token}` |

edit_token means the latest `edit_token` (create_agenda's, or rotate_edit_token's after a rotation); share_token addresses an agenda saved to a linked
account.
