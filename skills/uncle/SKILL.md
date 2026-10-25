---
name: uncle
description: Work with the user's UNCLE workspaces (modules such as Orders, Customers or Stock lots, their records, statuses and approvals) through the UNCLE connector. Use when the user asks about, counts, adds, updates or moves records in UNCLE, or asks what is waiting for their approval.
---

# Working with UNCLE

UNCLE is a system the user describes and it builds: each workspace has modules (Orders, Customers, Stock lots…), each module has fields and often a workflow of statuses, and records live in modules. The UNCLE tools act as the signed-in user, with that user's permissions; fields their role hides never come back.

## Find the right place first

- If the user belongs to more than one workspace and hasn't said which, call `list_workspaces` and ask, or pass `workspace` once you know it.
- Use the module names the user uses ("orders", "lots"). If unsure which module they mean, call `list_modules`.
- Before `create_record` or `update_record`, call `describe_module` to learn the field labels, required fields and allowed options. Never guess an option value.

## Answer with one card

- Some results come with a card the user sees (a record, a list, approvals). Aim for one card per answer.
- When the user names one record ("show me SO-1043"), call `get_record` with the module and title directly instead of searching first.
- For "how many…" questions use `count_records`; for lists use `search_records` with a status or text filter.
- After a card, reply in a sentence or two. Don't repeat what the card already shows.

## Changing things

- Say what you're about to change before a write, and use the record's title, not its id.
- Use `change_status` to move a record between statuses. Some moves need someone's approval: the result says `pending_approval`, and you should tell the user who it's waiting for rather than retrying.
- Use `list_my_approvals` for "what's waiting for me", and `decide_approval` to approve or reject with the user's note.
- Keep `record_id` values from earlier results for follow-up calls; never invent ids.
- Deleting records and changing modules, fields or workflows aren't available here. Point the user to the UNCLE app at https://uncleapp.co for those.
