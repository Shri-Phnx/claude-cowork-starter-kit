# Claude Cowork Starter Kit

A universal, opinionated starter pack for Claude Cowork. Drop in your details, follow this README, and get a fully configured Cowork environment in under 30 minutes. Designed so a complete beginner with no coding background can set it up end-to-end.

If you've never heard of Claude Cowork, it's a feature inside the Claude Desktop app that lets Claude work on your files, run scheduled tasks, and remember context across sessions. This kit gives you a ready-made set of instructions and identity files so Claude works like a senior colleague from day one instead of a generic chatbot.

---

## Table of contents

1. [Who this is for](#who-this-is-for)
2. [What you get](#what-you-get)
3. [Recommended folder layout (and why)](#recommended-folder-layout-and-why)
4. [Prerequisites](#prerequisites)
5. [Setup on Windows](#setup-on-windows)
6. [Setup on Mac](#setup-on-mac)
7. [Customise the templates](#customise-the-templates)
8. [Verify it works](#verify-it-works)
9. [Optional: back up your setup to GitHub](#optional-back-up-your-setup-to-github)
10. [Optional: schedule a monthly auto-backup](#optional-schedule-a-monthly-auto-backup)
11. [Troubleshooting](#troubleshooting)
12. [What's in each file](#whats-in-each-file)
13. [Credits and feedback](#credits-and-feedback)

---

## Who this is for

This kit is for anyone who:

- Has just installed (or is about to install) Claude Desktop and wants Cowork mode set up properly.
- Wants Claude to write in a consistent voice, follow safety rules, and remember context across sessions.
- Is non-technical and wants every step explained.
- Wants the option to back up their personal Claude setup to a private GitHub repo, with monthly automation.

You do not need to know how to code. You do not need git or the command line. You will need a free Anthropic account and (optionally) a free GitHub account if you want backups.

---

## What you get

By the end of this guide:

1. Claude knows who you are, what work you do, and how you like to communicate.
2. Claude follows a written set of safety rules: never deletes, sends, or publishes anything without checking with you first.
3. Claude writes in plain, human-sounding prose. No "delve," no em dashes, no AI tells.
4. Claude maintains a memory file that survives across sessions, so you don't repeat yourself.
5. Optional: a private GitHub backup of your whole setup, with monthly automation.

---

## Recommended folder layout (and why)

The recommended structure mounts Cowork at a **parent** Claude folder, with `CLAUDE.md` and the `About Me/` folder at the root, and your individual projects as sub-folders alongside them.

```
C:\Users\<you>\OneDrive\Documents\Claude\        ← Cowork mount root
├── CLAUDE.md                                     ← global instructions (loaded every session)
├── About Me\
│   ├── about-me.md                               ← identity, role, business, tools, projects
│   ├── writing-rules.md                          ← anti-AI writing guide
│   └── memory.md                                 ← persistent memory across sessions
├── Cowork folder\                                ← optional: legacy or general-purpose subfolder
├── Scheduled\                                    ← scheduled task definitions (Cowork manages this)
├── backup-logs\                                  ← created by the monthly backup task
└── Project Subfolders\                           ← one per project, as many as you like
    ├── Job listing and application automation\
    ├── Content scraping and generating automation\
    ├── Creating Second brain\
    ├── AI Trend Scraper Build\
    └── Video generation automation\
```

### Why this layout

**One identity, many projects.** Your `CLAUDE.md` and About Me files at the root mean Claude loads the same identity, voice, safety rules, and memory regardless of which project sub-folder you happen to be working in. You don't have to copy-paste these files into every project.

**Projects stay organised but share context.** Each project gets its own sub-folder for its working files (drafts, exports, references). Claude can see them all because they sit inside the mounted root, but each project's working files don't leak into other projects.

**Scheduled tasks see everything.** The monthly backup, weekly memory consolidation, and any other recurring task can read every file in the tree. If you mounted only one project sub-folder, scheduled tasks would only see that one slice.

**Memory survives across projects.** Decisions you make in one project (e.g. "always use British English in CVs") get written to the shared `memory.md` and apply to every other project automatically. No more repeating yourself.

**One backup covers everything.** When you set up the optional monthly GitHub backup, it captures the entire tree in one push. Adding a new project? It's automatically included in next month's backup with no extra configuration.

### When to use a single sub-folder mount instead

Mount a single sub-folder (e.g. `Documents\Claude\Cowork folder`) only if:

- You want strict isolation between Claude work and other personal files.
- You're trying Cowork for the first time and want minimum scope.
- You have a specific project that should not share identity with the rest.

For most users, parent-mount is the better default.

---

## Prerequisites

- A computer running Windows or macOS.
- An Anthropic account. Sign up free at `https://claude.com`.
- A web browser (Chrome, Edge, Safari, Firefox, anything modern).
- Optional: a GitHub account if you want backups. Free at `https://github.com/signup`.

That's it.

---

## Setup on Windows

### Step 1: Install Claude Desktop

- **Where:** open your browser, go to `https://claude.ai/download`.
- **What:** click the **Download for Windows** button. A `.exe` installer downloads.
- **Why:** Cowork mode is a feature inside Claude Desktop. It does not work in the web app at `claude.ai`.
- **How:** double-click the downloaded `.exe`. Follow the installer's prompts (defaults are fine). When it finishes, Claude Desktop opens automatically.

### Step 2: Sign in

- **Where:** the welcome screen of Claude Desktop.
- **What:** click **Sign in**. Enter the email address tied to your Anthropic account.
- **Why:** every feature (Cowork, plugins, scheduled tasks, Global Instructions) is tied to your signed-in account.
- **How:** the app opens your browser for sign-in. Complete sign-in there. The browser hands control back to the desktop app once you're authenticated. You'll land on the main Claude window.

### Step 3: Create your parent Claude folder

- **Where:** Windows File Explorer (open it from the taskbar or press `Windows key + E`).
- **What:** create a single parent folder where all your Claude work will live. This becomes your Cowork mount root.
- **Recommended path:** `C:\Users\<your-username>\OneDrive\Documents\Claude`. Replace `<your-username>` with your actual Windows username.
- **Why this path:** putting it under OneDrive means OneDrive syncs the folder as a free secondary backup. If you don't use OneDrive, use `C:\Users\<your-username>\Documents\Claude` instead.
- **How:**
  1. In File Explorer, navigate to `C:\Users\<your-username>\OneDrive\Documents\` (or just `C:\Users\<your-username>\Documents\`).
  2. Right-click on empty space, choose **New**, then **Folder**. Name it `Claude` exactly.
  3. Open the `Claude` folder. Leave it empty for now. The next step fills it.

### Step 4: Download this starter kit into the Claude folder

You have two options. Pick the one that suits you.

**Option A: Download as ZIP (no GitHub account needed, fastest).**

1. In your browser, go to `https://github.com/Shri-Phnx/claude-cowork-starter-kit`.
2. Click the green **Code** button.
3. Click **Download ZIP** at the bottom of the dropdown.
4. The ZIP downloads to your Downloads folder. Right-click it and choose **Extract All**.
5. Inside the extracted folder you'll see `CLAUDE.md`, an `About Me` folder, and `README.md`. Move all of these into your `Claude` folder (the one you created in Step 3). They sit directly at the root, not inside any subfolder.

**Option B: Clone with GitHub Desktop (slightly more setup, easier to update later).**

1. Install GitHub Desktop from `https://desktop.github.com`. Sign in with your GitHub account.
2. In GitHub Desktop, click **File**, then **Clone repository**.
3. Click the **URL** tab.
4. **Repository URL field:** paste `https://github.com/Shri-Phnx/claude-cowork-starter-kit`.
5. **Local path field:** click **Choose** and pick your `Claude` folder (the parent one, from Step 3). Important: the local path is the parent `Claude` folder, not a subfolder inside it.
6. Click **Clone**.
7. After cloning, the cloned files might end up inside a subfolder named `claude-cowork-starter-kit`. If so, move `CLAUDE.md`, the `About Me/` folder, and `README.md` up one level so they sit directly inside `Claude`. Delete the now-empty `claude-cowork-starter-kit` subfolder.

After either option, your folder should look like this:

```
C:\Users\<your-username>\OneDrive\Documents\Claude\
  ├── CLAUDE.md
  ├── README.md
  └── About Me\
      ├── about-me.md
      ├── writing-rules.md
      └── memory.md
```

### Step 5: Point Cowork at the parent Claude folder

- **Where:** Claude Desktop, **Settings → Cowork**.
- **What:** tell Cowork to use the parent `Claude` folder as its working root.
- **Why:** with this set, Claude loads `CLAUDE.md` and the About Me files automatically in every session, and any project sub-folder you add later inherits the same identity.
- **How:**
  1. Open Claude Desktop.
  2. Click your profile icon (top of the window).
  3. Click **Settings**.
  4. In the Settings sidebar on the left, click **Cowork**.
  5. Find the option labelled **Cowork directory**, **Working folder**, or similar. Click **Browse** or **Change**.
  6. Navigate to `C:\Users\<your-username>\OneDrive\Documents\Claude` (the parent, not a subfolder) and select it.
  7. Confirm. The setting saves automatically.

### Step 6: Paste Global Instructions

- **Where:** Claude Desktop, **Settings → Cowork → Global Instructions**.
- **What:** Global Instructions are persistent rules Claude reads at the start of every Cowork session, regardless of which folder is mounted.
- **Why:** the local `CLAUDE.md` in your folder covers folder-specific instructions. Global Instructions are the universal layer that travels with you. Best practice is to keep both in sync.
- **How:**
  1. Open `Claude/CLAUDE.md` in any text editor (Notepad, VS Code, even Word in plain text mode).
  2. Select all (`Ctrl+A`), copy (`Ctrl+C`).
  3. In Claude Desktop, go to **Settings → Cowork → Global Instructions**.
  4. Click **Edit**.
  5. Paste (`Ctrl+V`) into the text box.
  6. Click **Save**.

### Step 7: Done. Skip to "Customise the templates"

You now have a working Cowork setup with universal templates at the parent root. Move on to the [Customise the templates](#customise-the-templates) section to fill in your details.

---

## Setup on Mac

### Step 1: Install Claude Desktop

- **Where:** browser, `https://claude.ai/download`.
- **What:** click **Download for Mac**. A `.dmg` file downloads.
- **How:** open the `.dmg` (double-click it). Drag the Claude icon into the **Applications** folder. Launch Claude from Launchpad or by pressing `Cmd+Space` and typing `Claude`.

### Step 2: Sign in

Same as Windows Step 2 above.

### Step 3: Create your parent Claude folder

- **Where:** Finder.
- **Recommended path:** `~/Documents/Claude` (the `~` means your home folder).
- **Why this path:** simple and consistent. If you use OneDrive on Mac, the path is longer and lives under `~/Library/CloudStorage/OneDrive-Personal/Documents/Claude`. Use that if you want OneDrive sync, otherwise stick with `~/Documents/Claude`.
- **How:**
  1. Open Finder.
  2. Navigate to `~/Documents/`.
  3. Right-click in empty space, choose **New Folder**. Name it `Claude` exactly.
  4. Leave it empty for now.

### Step 4: Download this starter kit

Same two options as Windows Step 4.

**Option A: Download ZIP.**

1. `https://github.com/Shri-Phnx/claude-cowork-starter-kit` → green **Code** button → **Download ZIP**.
2. Double-click the ZIP in Downloads to extract.
3. Move `CLAUDE.md`, the `About Me/` folder, and `README.md` into your `Claude` folder. They sit at the root.

**Option B: GitHub Desktop.**

1. Download from `https://desktop.github.com`. Drag to Applications. Sign in.
2. **File → Clone repository → URL tab.**
3. URL: `https://github.com/Shri-Phnx/claude-cowork-starter-kit`.
4. Local path: `~/Documents/Claude`.
5. Click **Clone**.
6. If files land in a subfolder, move them up one level so they sit at the root of `Claude`.

### Step 5: Point Cowork at the parent Claude folder

- Same as Windows Step 5, just using Claude on Mac. The settings menu lives at **Claude → Settings** or **Claude → Preferences** depending on version. Select `~/Documents/Claude` as the directory.

### Step 6: Paste Global Instructions

- Same as Windows Step 6. Use `Cmd+A` and `Cmd+C` for select-all and copy.

### Step 7: Done. Move on.

---

## Customise the templates

You now have a working Cowork setup, but the templates are full of `[TODO: ...]` placeholders. The fastest way to fill them in is to let Claude help you.

### Easiest path: ask Claude to walk you through it

1. Open a new Cowork chat in Claude Desktop, with your Claude folder selected.
2. Paste this message:

   > Walk me through filling in `CLAUDE.md` and `About Me/about-me.md`. Ask me one section at a time, suggest defaults where it makes sense, and update the files as we go. Once we're done, do the same for `About Me/memory.md`.

3. Answer Claude's questions as it goes. The whole pass takes 15 to 20 minutes.

### Manual path: edit the files yourself

If you'd rather edit the files directly, open them in your favourite text editor and search for `[TODO: ...]`. Each TODO has inline guidance explaining what to put there. The files are:

- `CLAUDE.md` — universal behavioural rules (keep most of this) plus your identity and standing context.
- `About Me/about-me.md` — your full identity profile.
- `About Me/memory.md` — your running memory file. Pre-populated with universal lessons. Add your active projects and follow-ups.

`About Me/writing-rules.md` does not need editing. It applies universally.

---

## Verify it works

Now check that everything is loading correctly.

1. Close any open Cowork chats.
2. Open a brand-new Cowork chat (important: must be new, not a continuation of an old one).
3. Confirm your Claude folder is selected at the top of the chat.
4. Type this probe question:

   > "What's my name, and what's the first safety rule you should follow?"

5. **Expected answer:** Claude returns your full name (the one you put in `about-me.md`) and the safety rule about never deleting anything without checking. If it does, your setup is fully loaded.

6. **If the answer is wrong or generic:** see the [Troubleshooting](#troubleshooting) section.

---

## Optional: back up your setup to GitHub

If you want a private cloud backup of your Claude folder, follow this section. Skip if you don't use GitHub.

### Why bother

- Your `CLAUDE.md` and About Me files become the most important files on your computer over time. They define how Claude works for you.
- A laptop dying or a folder getting accidentally deleted can wipe months of refinement.
- A private GitHub repo is free and gives you full version history.

### One-time setup

#### Step 1: Create a private repo for your backup

1. Go to `https://github.com/new`.
2. **Repository name:** `cowork-personal-backup` (or any name you prefer).
3. **Description (optional):** `My personal Claude Cowork backup`.
4. **Visibility:** select **Private**. Important.
5. **Initialize with:** tick **Add a README file**.
6. Click **Create repository**.

#### Step 2: Install the Claude GitHub MCP Connector

This is the bit that lets Claude push files to your repos.

1. In your browser, open `https://github.com/apps/claude-github-mcp-connector`.
2. Click **Install**.
3. Choose your account when prompted.
4. **Repository access:** select **All repositories** (recommended) or **Only select repositories** and tick your backup repo.
5. Click **Install** or **Save**.

After this, Claude can push to and read from your repos. It still cannot create new repos for you. Repo creation is always a manual step at `github.com/new`.

#### Step 3: Ask Claude to do the first push

In a Cowork chat:

> Push the contents of my Claude folder to my private GitHub repo at `<your-username>/cowork-personal-backup`. Include `CLAUDE.md`, the `About Me/` folder, and any other `.md` files at the root and in project sub-folders. Skip the `Scheduled/` folder and any `backup-logs/` folder. Write a detailed restore README first so I can recover on a new machine.

Claude will read the files, push them, and write a restore README. Verify the files appear at `https://github.com/<your-username>/cowork-personal-backup`.

---

## Optional: schedule a monthly auto-backup

To make backups automatic, schedule a Cowork task that runs once a month and pushes any changes to your private repo.

### How

In a Cowork chat:

> Create a scheduled task that runs on the 1st of every month at 11:00 AM (my local time). The task should push any changes from my parent Claude folder to my private repo at `<your-username>/cowork-personal-backup`. Use Glob to discover all `.md` files at the root and in sub-folders, but skip the `Scheduled/` and `backup-logs/` folders. After each run, write a status file to a `backup-logs/` folder at the parent root (named `yyyy-mm-dd-monthly-backup.md`) summarising what was pushed, what was skipped, and what failed. Append a one-line entry to `About Me/memory.md` under a "Scheduled Run Log" section.

Claude will configure the task using the Cowork scheduled-tasks tool. The task definition lives in your Cowork app's **Dispatch** panel, where you can also see each run's history.

### Verifying the schedule works

You can wait until the 1st of the next month, or you can ask Claude to run the same task immediately as a one-off so you see it work. The output should be:

1. New commit on your private repo.
2. New file at `Claude/backup-logs/yyyy-mm-dd-monthly-backup.md`.
3. New entry in `Claude/About Me/memory.md` under Scheduled Run Log.
4. New entry in your Cowork app's Dispatch panel.

If any of those four are missing, troubleshoot by asking Claude what failed.

---

## Troubleshooting

### Claude doesn't know my name when I ask the probe question

1. Confirm your Claude folder is selected at the top of the chat.
2. Confirm `CLAUDE.md` exists at the root of that folder, and `About Me/about-me.md` exists inside the `About Me` subfolder. They should be at the parent root, not nested inside another subfolder.
3. Confirm you actually filled in the `[TODO: Your full name]` placeholder in `about-me.md`. If it still says `[TODO: ...]`, Claude has nothing to read.
4. Confirm you clicked **Save** after pasting Global Instructions in Step 6.
5. Start a brand-new chat (not a continuation of an old one). Global Instructions only apply to chats started after they were saved.

### GitHub push returns 404

1. Confirm the repo exists by opening its URL in your browser.
2. Confirm the Claude GitHub MCP Connector App is installed at `github.com/settings/installations`. There should be a section called **Installed GitHub Apps** with **Claude Github MCP Connector** listed.
3. Click **Configure** next to it. Confirm **Repository access** is set to **All repositories** or has your specific repo selected.

### GitHub push returns 403 on `create_repository`

This is expected. The Claude GitHub MCP Connector cannot create new repos. Always create them manually at `github.com/new` first, then ask Claude to push files.

### Claude opens with "Great question!" or uses em dashes

Either Global Instructions weren't saved properly, or this is the first message in a session that started before you saved them. Open a brand-new chat and try again. If it persists, re-paste Global Instructions and click Save.

### Cowork won't let me select the parent folder

Some Cowork builds restrict folder selection to specific user directories. The parent `Documents/Claude` location should always work. If it doesn't, you can fall back to a single sub-folder mount (see [When to use a single sub-folder mount instead](#when-to-use-a-single-sub-folder-mount-instead)).

### I previously had Cowork mounted at a subfolder. How do I switch?

1. In File Explorer (Windows) or Finder (Mac), move `CLAUDE.md` and the `About Me/` folder up one level from your subfolder to the parent `Claude` folder.
2. In Claude Desktop, go to **Settings → Cowork** and change the directory selection from the subfolder to the parent `Claude` folder.
3. Start a new chat. The probe question should now work from the parent root.
4. If you have a scheduled monthly backup task, ask Claude to update the task's prompt to use the new parent-root paths.

---

## What's in each file

- **README.md** — this file. Setup walkthrough.
- **CLAUDE.md** — the project instructions Cowork loads when working in this folder. Contains identity, behavioural rules, output rules, safety rules, and what to avoid. Most of it is universal best practice. The `[TODO: ...]` sections are where you customise.
- **About Me/about-me.md** — your full identity profile. Who you are, what work you do, what tools you use, what projects are in flight. Customise everything.
- **About Me/writing-rules.md** — anti-AI writing guide built from Wikipedia's "Signs of AI writing." Universal. Don't customise.
- **About Me/memory.md** — running memory file. Pre-populated with universal lessons. Customise the project sections.

---

## Credits and feedback

Built and battle-tested by Shrinivas Ramaprasad. The behavioural rules and writing-rules content come from extensive iteration with Claude, plus Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide for the anti-AI patterns.

Found a bug, hit a confusing step, or want to suggest an improvement? Open an issue at `https://github.com/Shri-Phnx/claude-cowork-starter-kit/issues`.

---

*Last updated: 2026-05-07.*
