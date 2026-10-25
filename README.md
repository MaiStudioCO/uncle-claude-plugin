# UNCLE for Claude

Work with your [UNCLE](https://uncleapp.co) workspaces from Claude. UNCLE is the system you describe and it builds: modules, fields, workflows and approvals for whatever you run, from a fabric wholesaler's stock to a clinic's appointments.

With this plugin, ask Claude things like:

- "What's waiting for my approval in UNCLE?"
- "Which orders are due this week?"
- "Show me the low-stock lots"
- "Add a customer: Marlow Garment Co., 30-day terms"
- "Move SO-1043 to Shipped"

Claude finds the records, counts them and opens them as cards. It can also add and update records, move them along their workflow and approve or reject requests. It works as you, with the permissions your role has in each workspace; fields your role hides stay hidden, and a status change that needs approval waits for it, as in the app. Claude can't delete records or change how a workspace is set up.

## What's inside

- **Connector:** UNCLE's remote MCP server at `https://mcp.uncleapp.co/mcp` (declared in `.mcp.json`). You sign in with your UNCLE account through OAuth the first time Claude uses it.
- **Skill:** `skills/uncle/SKILL.md` teaches Claude how to use the UNCLE tools well: pick the workspace, learn a module's fields before writing, answer with one card, and handle approvals.

Nothing runs on your machine, and the plugin sends nothing anywhere except UNCLE's MCP server, which receives only what Claude asks it for while answering you.

## Tools

| Tool | What it does |
|---|---|
| `list_workspaces`, `get_profile` | Your UNCLE workspaces and who is connected |
| `list_modules`, `describe_module` | A workspace's modules and their fields, statuses and options |
| `search_records`, `get_record`, `count_records` | Find, open and count records |
| `list_my_approvals` | Requests waiting for your decision |
| `create_record`, `update_record` | Add or change records |
| `change_status`, `decide_approval` | Move a record along its workflow; approve or reject |

## Requirements

An UNCLE account with at least one workspace: create one free at [uncleapp.co](https://uncleapp.co).

## Privacy and support

What is shared and kept is described in section 12 of the [UNCLE Privacy Policy](https://uncleapp.co/privacy). The full guide is at [uncleapp.co/claude](https://uncleapp.co/claude). For help, email [uncle@maistudio.co](mailto:uncle@maistudio.co).

Published by Mai Studio OÜ, Tallinn, Estonia.
