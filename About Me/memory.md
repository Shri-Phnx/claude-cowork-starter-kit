# Memory: Working State

> **TEMPLATE FILE.** This file becomes Claude's persistent memory across sessions. Sections are pre-populated with universal patterns and an example structure. Replace `[TODO: ...]` and example entries with your own state. Don't delete sections you don't currently use; just leave them empty.

## How This File Works

This is the running memory file. Claude updates it whenever a session produces a meaningful state change, decision, or commitment. The protocol:

- **Append new entries** to the relevant section, most recent at the top of each subsection.
- **Update existing entries** when something changes status (e.g., a project moves from drafted to published).
- **Date every entry** in `yyyy-mm-dd` format.
- **Keep entries short.** One line of summary, then any necessary detail or links underneath.
- **Never delete an entry without checking with me first.** Mark superseded items with `~~strikethrough~~` and a note pointing to the replacement.

If Claude is unsure whether to log something, log it. Better to have a noisy memory than a sparse one.

---

## Active Projects

[TODO: List your live projects here. Use this structure for each:]

### [Project name]
- **Status:** [drafted / in progress / blocked / complete]
- **Last updated:** [yyyy-mm-dd]
- **Notes:** [anything relevant]
- **Open question:** [what's pending]

---

## Decisions Log

Decisions worth remembering, with the why.

[TODO: Append decisions here as you make them. Format: "yyyy-mm-dd: did X because Y."]

---

## Open Questions / Follow-Ups

Things waiting on me to answer or decide.

[TODO: Add open questions here as they come up.]

---

## Patterns and Preferences (Learned Over Time)

Universal lessons pre-populated below. These apply to almost everyone working with Claude. Keep them and append your own as Claude observes your preferences.

- **Don't guess factual details (UI paths, product features, menu locations, names, numbers, dates).** If not certain, either say "I'm not sure" or web-search authoritative sources first. Do not wrap a guess in a hedge ("or wherever it lives") and pass it off as an answer. This violates the Accuracy rule in CLAUDE.md.
- **Default to structured answers when explaining anything multi-part:** a mistake, a comparison, a multi-step diagnosis, a list of issues, or any reply with more than one distinct point. Use numbered or bulleted structure with clear labels. Prose-only is fine for short, single-point answers and casual chat, not for substantive explanations.
- **Cowork Global Instructions location is `Settings → Cowork → Global Instructions`**, then click Edit. (Not Settings → Capabilities, which is a separate menu item for network and tool permissions.)
- **For full visibility across all Claude data folders, mount the parent Claude folder** as the Cowork directory rather than a subfolder. Subfolders limit what scheduled tasks can see and back up.
- **Scheduled task notification protocol** (no native push notifications): every scheduled run must (1) write a status file to `backup-logs/` (or task-equivalent log folder) named `yyyy-mm-dd-task-name.md` summarising what was committed, what failed, what was skipped; (2) append a one-line entry to `memory.md` under a "Scheduled Run Log" section; (3) the run also appears as a Dispatch entry in Cowork's Dispatch panel.
- **GitHub MCP setup gotcha:** the Claude Github MCP Connector has two layers: OAuth authorisation (gives basic identity and read access to public repos), and GitHub App installation (gives per-repo write access and access to private repos). OAuth alone returns 404 on private repos. Fix: install the App at `github.com/apps/claude-github-mcp-connector` and choose **All repositories** for full coverage. Note: the App's permission set does not include creating new repos. Always create new repos manually at `github.com/new`, then push files via the MCP.

[TODO: Append your own patterns as Claude observes them.]

---

## Scheduled Run Log

One-line summaries of every scheduled task run. Most recent at the top. Format:
`yyyy-mm-dd HH:MM | task-name | status | summary | log-file-path (if any)`

- *(no runs yet)*

---

## Recent Wins / Completed Work

[TODO: Optional section. Useful for periodic retrospectives. Append completed work here as you ship things.]
