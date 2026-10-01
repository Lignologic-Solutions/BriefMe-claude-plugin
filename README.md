# BriefMe

BriefMe turns a meeting plan into a shared countdown timer. Describe the meeting, and Claude
builds a timed agenda in BriefMe where every topic gets its own timebox. Use it for standups,
retros, workshops or any meeting that has to finish on time. Later, ask for changes in plain
language, and only the topics you mention change.

## Install

**Claude on the web, the desktop app and Cowork**

1. Open **Customize > Plugins**. Add BriefMe from **Discover** once it is listed, or choose
   **Add > Add marketplace** and enter `Lignologic-Solutions/BriefMe-claude-plugin`.
2. Open the plugin's **Connectors** tab, then add and connect the BriefMe connector. Adding a
   plugin does not connect its connector. On Team and Enterprise plans, an Owner adds the
   connector for the organization first, and members then connect.

Skills in chat need **Code execution and file creation** on, under **Settings > Capabilities**.

**Claude Code**

In a session (version 2.1.275 or later):

```text
/plugin install briefme --marketplace Lignologic-Solutions/BriefMe-claude-plugin
```

Or from your shell:

```bash
claude plugin marketplace add Lignologic-Solutions/BriefMe-claude-plugin
claude plugin install briefme@briefme
```

A plugin you add on claude.ai also reaches Claude Code as a synced plugin.

## Use it

- "Make a 15-minute standup agenda for my team"
- "Plan a 60-minute sprint planning meeting with a demo, estimation and a wrap-up"
- "Build a 45-minute retro agenda: what went well, what didn't, action items"

Claude replies with two links. The share link (`share_url`) is a read-only live timer that stays
in sync on every screen. It is safe for a calendar invite. The edit link (`edit_url`) is the
private control page where you start, pause and advance the meeting. Keep it with the organizer.

## What the plugin contains

Three skills (`create-agenda`, `edit-agenda`, `delete-agenda`), which are instructions only, and
one connector URL, `https://briefme.us/mcp/claude`. There are no scripts, hooks, binaries or local
servers.

## Data

Claude sends BriefMe, at `https://briefme.us/mcp/claude`, the meeting and topic titles, durations
and descriptions you ask for, and the agenda's share and edit tokens. If you connect a BriefMe
account, requests also carry an OAuth access token. Like any website, BriefMe sees standard
request details such as the network address.

Agendas created without an account expire after 7 days. Saved agendas do not expire. BriefMe
calls no language model of its own. Beyond the processors named in the privacy policy, it
shares your data with no one.

## Accounts

An account is optional. Creating and running agendas needs none. On Claude on the web, the
desktop app and Cowork, when you ask for something that needs your account, such as your saved
agendas, Claude shows a Connect button. Select it to sign in to BriefMe with Google or
Microsoft. In Claude Code, Claude tells you to sign in instead: run `/mcp`, choose the briefme
server and sign in from there. You can also sign in on briefme.us to save agendas.

## Links

- Website: https://briefme.us
- Setup: https://briefme.us/docs/mcp
- Privacy: https://briefme.us/privacy
- Terms: https://briefme.us/terms
- Support: https://briefme.us/support
