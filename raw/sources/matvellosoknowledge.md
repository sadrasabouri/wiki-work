---
title: "matvelloso/knowledge"
source: "https://github.com/matvelloso/knowledge/"
author:
published:
created: 2026-05-05
description: "Contribute to matvelloso/knowledge development by creating an account on GitHub."
tags:
  - "clippings"
---
## Knowledge

Knowledge is a privacy first, knowledge builder that runs locally on your machine, leverages open source LLMs and brings a note editor (A fork of the great MarkText project) plus an email client (works with both Google and Microsoft email accounts) and a local file parser/indexer.

Essentially, once you install this project, you must:

- Configure the OAuth apps for both Google and Microsoft so you can connect your email accounts
- Write your own "MY PREFERENCES.md" where you will describe how you want your knowledge to be captured and documented
- Run the agent to analyze your emails, files and notes to build that knowledge

This is the main screen. You can see the mail folders, as well as the note taking folders and the knowledge built all in one place:

[![Main Screen](https://github.com/matvelloso/knowledge/raw/develop/screenshots/mainscreen.png)](https://github.com/matvelloso/knowledge/blob/develop/screenshots/mainscreen.png)

Here is an example of the type of preferences you can set up:

[![Preferences example](https://github.com/matvelloso/knowledge/raw/develop/screenshots/mypreferences.png)](https://github.com/matvelloso/knowledge/blob/develop/screenshots/mypreferences.png)

In this case, I am configuring it to look at all my Amazon Whole Food email receipts and consolidate a list of grocery items that I typically order. I am also asking it to build one separate.md file for to do items, grocery items, pending emails, etc.

Knowledge will also build an email personalization profile where it will learn how you write emails, and even have sections per email target with custom personalization rules for each. Once it has that, you can ask AI to help you draft emails as responses and it will try to mimic your style:

[![email personalization profile](https://github.com/matvelloso/knowledge/raw/develop/screenshots/emailpersonalization.png)](https://github.com/matvelloso/knowledge/blob/develop/screenshots/emailpersonalization.png)

Another cool effect of running the agents on your computer is that the tool will build a full semantic index of all your files, notes and emails, so you can easily search for them all in one place:

[![semantic search](https://github.com/matvelloso/knowledge/raw/develop/screenshots/search.png)](https://github.com/matvelloso/knowledge/blob/develop/screenshots/search.png)

In other words, the knowledge is captured and grouped the way it makes sense to YOU and it is all done locally on your computer.

This sample is MIT licensed and you are free to use it however you prefer.

Below there are detailed instructions for running this code.

Tip: Just point your coding agent to this readme, ask it to read this and the code and guide you step by step how to configure and run the app. Most of the documentation below was written for AI to read, not humans.

## Current status

This is a mere prototype, fully vibe coded.

---

## Table of contents

## What you'll have when you're done

- A workspace folder on disk containing markdown notes, your managed lists (`To Do.md`, `Shopping List.md`, etc.), and a `knowledge/` subfolder for agent-generated topic notes.
- A local LLM running through Ollama, used for inbox triage, document classification, knowledge synthesis, semantic search, and reply drafting.
- Connected Gmail and/or Outlook accounts that sync into a virtual `Emails` tree (Inbox, Sent, Drafts, Junk, Deleted, Archive).
- Background agents that read your mail + workspace files and turn them into structured markdown lists and linked knowledge notes — following whatever instructions you write in `MY PREFERENCES.md`.

---

## Prerequisites

- **Node.js**: any recent LTS (v18 or v20 works). The codebase still inherits Electron's older toolchain notes, but `yarn dev` and `yarn build` work on modern Node.
- **Yarn**: `npm install -g yarn` if you don't have it.
- **Python 3** + a C/C++ compiler: required by `node-gyp` for native modules.
	- macOS: `xcode-select --install`
		- Linux: `sudo apt install build-essential python3` (Debian/Ubuntu)
		- Windows: install the "Desktop development with C++" workload via Visual Studio 2019+
- **Linux extras** (Debian/Ubuntu): `sudo apt install libx11-dev libxkbfile-dev libsecret-1-dev libfontconfig-dev`
- Note (I only really tested this on Mac, so apologies to Linux users if something won't work)

You will also need:

- **Ollama** for the local LLM (the in-app wizard installs it for you on macOS/Windows).
- A **Google account** with access to [Google Cloud Console](https://console.cloud.google.com/), if you want Gmail.
- A **Microsoft account** with access to [Azure portal](https://portal.azure.com/), if you want Outlook.

---

## Clone and run

```
git clone https://github.com/<your-fork>/knowledge.git
cd knowledge
yarn install
yarn dev
```

`yarn dev` builds the main process, the renderer, and Muya (the markdown editor library), then launches Electron with hot reload. The first build takes a couple of minutes; subsequent runs are fast.

If you see `EADDRINUSE: address already in use 127.0.0.1:9091`, a previous `yarn dev` left its dev server alive. Kill it:

```
kill -9 $(lsof -ti:9091)
```

---

## First-run setup inside the app

The wizard lives inside the app — open `Preferences` (Cmd+, on macOS, Ctrl+, elsewhere) once the window appears.

### Step 1 — Pick a workspace folder

On first launch the app prompts you for a workspace root. Pick (or create) an empty folder you want to dedicate to your notes. Knowledge will seed it with:

```
<workspace>/
├── MY PREFERENCES.md      # the agent's operating manual — you edit this
├── To Do.md
├── Shopping List.md
├── Reading List.md
├── Pending Emails.md
└── knowledge/             # agent-generated topic notes go here
    ├── index.md
    └── log.md
```

### Step 2 — Install Ollama and pull a model

Open `Preferences` → `AI & Agents`. The panel walks you through three steps with auto-detection:

1. **Install Ollama**: click "Download Ollama" if it isn't found. The button opens the official installer for your OS; once you finish the install the panel re-checks automatically.
2. **Start the runtime**: click "Start Ollama" — the in-app helper runs `ollama serve` in the background. You'll see the endpoint go green at `http://127.0.0.1:11434` once it's up.
3. **Download a model**: pick from the suggested list, or paste any tag from [ollama.com/library](https://ollama.com/library) into the custom-tag input. Knowledge needs **two** models:
	- A **chat model** for synthesis and triage. Default suggestion is `gemma4` (~9.6 GB). Other strong picks shipped in the dropdown: `qwen3.5` (9B, ~6.6 GB), `llama3.2:3b` (small, ~2 GB), `qwen3.5:27b` (better quality, ~17 GB). Anything Ollama supports works.
		- An **embedding model** for semantic search. Default is `nomic-embed-text` (~270 MB); `mxbai-embed-large` (~670 MB) is a higher-quality alternative.

The panel pulls each model and confirms when it's healthy. Until both are pulled, the agents fall back to non-AI behavior (mail still syncs, but no triage / classification / semantic search).

Knowledge uses real OAuth 2.0 with PKCE; you provide your own client ID so we never ship app credentials. Roughly five minutes:

1. Go to [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project (or pick an existing one).
3. Enable the **Gmail API** and the **Google Calendar API** under `APIs & Services` → `Library`.
4. Configure the OAuth consent screen under `APIs & Services` → `OAuth consent screen`:
	- User type: **External** (or Internal if you're in a Google Workspace).
		- Add your own Gmail address as a **test user** while the app is in testing mode.
		- Add scopes: `gmail.readonly`, `gmail.send`, `gmail.modify`, `calendar.readonly`, plus the standard `openid`, `email`, `profile`. (You'll see Knowledge request these on first connect.)
		- Note this will work for you and a few test users. For real production use you would need to deal with the approval process which can take several days.
5. Create credentials under `APIs & Services` → `Credentials` → `Create credentials` → `OAuth client ID`:
	- Application type: **Desktop app**.
		- Name: anything (e.g., `Knowledge dev`).
6. Copy the **client ID** and **client secret** that Google shows you.
7. In the Knowledge app, open `Preferences` → `Accounts` and paste both into the Google fields.

> Why a client secret for a desktop app? Google's token endpoint requires it even with PKCE. It isn't truly secret in this flow, but Knowledge still stores it in the OS keychain with OAuth tokens instead of writing it to workspace config.

The redirect URI is dynamic — Knowledge spins up a loopback HTTP server on a random port (`http://localhost:<port>/oauth/callback`) for the duration of the auth flow. Google's Desktop client type accepts loopback redirects with any port, so no extra registration is needed.

Microsoft's Azure portal is fiddlier because personal accounts (hotmail.com / outlook.com) require an exact port match for the redirect URI. Roughly:

1. Go to [Azure portal](https://portal.azure.com/) → `App registrations` → `New registration`.
2. Name it (e.g., `Knowledge dev`), and pick a "Supported account types":
	- **Accounts in any organizational directory and personal Microsoft accounts** if you want to sign in with both work/school and consumer accounts.
		- Pick a more restrictive option if you only need one.
3. **Don't** set a redirect URI yet — finish registration first.
4. Open the app's `Authentication` blade → `Add a platform` → **Mobile and desktop applications**.
5. Add a custom redirect URI: `http://localhost:53682/oauth/callback` (53682 is the default port; you can change it in the app and update Azure to match).
6. Make sure **Allow public client flows** is set to **Yes** under "Advanced settings".
7. Copy the **Application (client) ID** from the `Overview` blade.
8. Add API permissions under `API permissions` → `Microsoft Graph` → `Delegated permissions`:
	- `Mail.Read`, `Mail.Send`, `Mail.ReadWrite`, `Calendars.Read`, plus the standard `openid`, `email`, `profile`, `offline_access`.
9. (Optional) Click "Grant admin consent" if you're in an organizational tenant.
10. In the Knowledge app, `Preferences` → `Accounts`:
	- Paste the client ID into the Microsoft field.
		- Tenant: leave as `common` for personal+work, or paste your tenant ID for org-only.
		- Redirect port: `53682` (or whatever you registered above — they MUST match exactly for personal accounts).

> No client secret here — Microsoft public-client flows use PKCE alone.

### Step 5 — Connect your accounts

Run the app using:

`yarn dev`

In `Preferences` → `Accounts`:

1. Click **Connect Gmail**. A browser window opens for Google's consent screen. Approve the requested scopes. The browser redirects back to your loopback server, the auth code is exchanged for tokens, and the account appears in the "Connected email providers" list.
2. Click **Connect Outlook**. Same flow with Microsoft.

You can connect multiple accounts of either provider; each is listed separately. Tokens and the Google desktop client secret are stored in your OS keychain (macOS Keychain, Windows Credential Vault, Linux libsecret), never in the workspace folder.

### Step 6 — Sync your mail

Click **Sync** in the bottom-right status bar. Knowledge fetches up to one year of history per folder per account on the first run, then incremental on every subsequent sync. After it finishes:

- The sidebar's `Emails` tree shows folder counts and unread badges.
- Click any folder to open the three-pane Gmail-style view (folder list | message list | reading pane).
- Sortable columns, multi-select, archive/junk/delete, mark-read/unread, threaded conversations all work without round-tripping to the provider — moves are local first.

Email bodies render with the email's own CSS inside a sandboxed iframe (no scripts, no remote tracking pixels by default). Click "Show images" if you want to load remote `<img>` sources for a specific message.

### Step 7 — Edit MY PREFERENCES.md to teach the agents

This is the most important file in your workspace. It's plain markdown, you edit it like any other note, and the agents re-read it on every run. Open it from the sidebar.

The seeded template includes sections for:

- Workspace goals
- Source collections (which folders are in scope)
- **Managed Files** (rename the default lists by editing this section)
- Knowledge base conventions
- Per-list policies (To Do, Shopping, Reading, Pending Emails)
- **Topic Grouping** (control how knowledge-graph topics are named, clustered, included, or excluded)
- Knowledge synthesis rules
- Review and safety policy

#### Renaming a managed list

Want a **Grocery List** instead of the default Shopping List? Edit the `## Managed Files` section:

```
## Managed Files

- tasks: To Do.md
- shopping: Grocery List.md
- reading: Reading List.md
- pending-emails: Pending Emails.md
```

Save the file. On the next agent run, Knowledge:

- Creates `Grocery List.md` (with the User-managed / Agent-managed structure) if it doesn't exist.
- Routes all "shopping" classifications into `Grocery List.md` from then on.
- Mentions `Grocery List.md` in agent prompts so the LLM uses your naming.
- Surfaces a one-time notification if the old `Shopping List.md` is still on disk so you can delete or merge it manually (Knowledge never silently deletes user files).

The parser also accepts:

- Bare filenames in the `## Managed Files` section: `- Grocery List.md` — kind is inferred from the filename keyword.
- Backtick- or quote-wrapped filenames anywhere in the document: ``use `Grocery List.md` for groceries``.
- Standalone bullets outside the section: `- Grocery List.md` on its own line.

#### Custom extraction rules — the Whole Foods example

Beyond renaming files, you can teach the agents domain-specific extraction rules. These go in the per-list **Policy** sections. Here's how I have my Shopping (Grocery) policy set up:

```
## Shopping List Policy

- Add an item only when a source clearly implies something to be purchased.
- Dedupe by meaning, not exact text — "whole milk" and "Whole Milk, 2%" are the same.
- Preserve quantity, size, or brand hints when they matter ("2 lb organic Fuji apples", "King Arthur AP flour").

### Whole Foods / Amazon receipts (special handling)

When a synced email is a Whole Foods Market or Amazon order confirmation:

- Treat each ITEM LINE in the order body as its own Grocery List entry,
  not one entry per email. A 14-item Whole Foods order should produce 14
  Grocery List rows.
- Title = the product name as it appears in the receipt.
- Detail = quantity and unit price if visible (e.g. "2 × $4.99 each").
- Keep the same \`knowledge://email/...\` source URI on every row in the
  same receipt so I can trace each item back.
- Skip non-grocery line items (delivery fees, tips, "service charge").

### Subscription auto-renewals (special handling)

When an email is a subscription renewal notice (Audible, Apple One, etc.),
do NOT create a shopping entry. Treat it as a transactional notification.
```

Knowledge passes the entire `MY PREFERENCES.md` content to the LLM as a hard-rules system prompt during inbox triage. The LLM follows your specific instructions — receipt line-item extraction, subscription filtering, brand-preserving deduplication, anything else you write — because it sees those rules verbatim every run.

The same pattern works for the other lists. Examples you can write:

- **To Do**: "Treat any email subject containing 'action required' or 'response requested' as a To Do item." / "Do not create To Do items for newsletters or marketing emails."
- **Reading**: "When a Substack or newsletter email arrives, add the article title (not the email subject) to Reading List."
- **Pending Emails**: "Mark a thread pending if I haven't replied within 48 hours and the sender directly addresses me by name."

#### Telling the agent how to group topics

The seeded `## Topic Grouping` section controls how the knowledge-graph step clusters your notes, mail, and documents into the topic pages under `knowledge/Topics/`. The agent reads this section as HARD RULES and falls back to defaults only for things you don't specify. Examples of rules that work:

```
## Topic Grouping

- Use the format \`<Project codename or domain>: <specific theme>\` for titles.
- Always include topics for: \`Investments\`, \`Family\`, \`House search\`.
- Never include topics for newsletter or marketing mail.
- Cap at 10 topics — merge weaker themes rather than creating singletons.
- Use British spelling in topic names ("organisation", not "organization").
```

The parser recognises any of these heading variants (case-insensitive): `Topic Grouping`, `Topic Policy`, `Topics Policy`, `Topics`, `Topic Rules`, `Knowledge Topics`. Anything between that heading and the next equal-or-shallower heading is treated as the topic policy and fed verbatim into the topic-clustering and per-topic-summary prompts.

If you don't have a recognised section, the agent falls back to the first ~6 KB of `MY PREFERENCES.md` — which usually doesn't reach your topic rules, so adding a dedicated section is the difference between rules being applied and rules being silently ignored.

#### Tip: tail the log

While you're tuning preferences, run the agents and watch `knowledge/log.md` after each run. Every agent run appends a line summarizing what was indexed, classified, and synthesized — it's the fastest way to see whether your rules are landing.

### Step 8 — Run the agents

Click **Run** in the bottom-right status bar. The agent run executes phases sequentially:

1. **Mail preflight**: sync all connected accounts.
2. **Workspace indexing**: walk markdown + documents in the workspace.
3. **Pending Emails**: refresh the pending list from current mail state.
4. **To Do reconcile**: review user-managed checkboxes for closure suggestions.
5. **Inbox triage**: LLM classifies recent inbox into To Do / Shopping / Reading per your preferences.
6. **Document triage**: same for PDFs, docx, xlsx, etc. in the workspace.
7. **Semantic index**: embed every note + email + document chunk for hybrid search.
8. **Knowledge graph**: cluster topics, project pages, work-in-progress detection.
9. **Email style**: every 10 runs, distill a style profile from your sent mail (used by AI reply drafts).
10. **Knowledge overview**: write/update `knowledge/index.md` with the latest topic catalog.

Click **Cancel** at any point to interrupt — the run stops at the next phase boundary, marks the job as cancelled, and saves whatever progress it had.

A run on a fresh workspace + ~5 000 emails + a couple hundred documents takes roughly 5–15 minutes depending on your machine and chosen model size.

---

## Daily usage

Once setup is done, the day-to-day flow is mostly:

- **Sync** when you want fresh mail (or set up the schedule under `Preferences` → `AI & Agents` to run automatically every N minutes).
- **Search** with the magnifying-glass tab in the sidebar — hybrid (embeddings + keyword) over notes, mail, and documents.
- **Compose / Reply with AI**: opens a draft pre-filled in your style based on the sent-mail style profile. The compose tab uses the muya markdown editor; on Send the markdown is rendered to sanitized HTML.
- **Review queue** (sidebar): if an agent wants to edit a user-owned line in `To Do.md` etc., it shows up here for you to approve or reject.
- **Edit `MY PREFERENCES.md`** whenever you want to adjust agent behavior. Re-run agents.

---

## Troubleshooting

**`yarn dev` exits with `EADDRINUSE: address already in use 127.0.0.1:9091`** A previous dev server didn't shut down. `kill -9 $(lsof -ti:9091)` and retry.

**`Encoding auto-detection disabled — native module "ced" failed to load`** Pre-existing native-rebuild quirk inherited from MarkText. The app falls back to UTF-8, which is fine for normal usage. Run `yarn rebuild` if you need it gone.

**`unable to install vue-devtools`** Dev-mode-only quirk; doesn't affect the app.

**Google says "Access blocked: this app's request is invalid"** Your OAuth client ID is set to `Web application` instead of `Desktop app`. Recreate it under `Credentials` and pick Desktop app.

**Microsoft says "AADSTS50011: redirect URI specified in the request does not match"** The port in `Preferences` → `Accounts` doesn't match the URI you registered under `Authentication` → `Mobile and desktop applications`. Make sure both say `http://localhost:53682/oauth/callback` exactly (or your chosen port).

**Sync hangs or returns "401 Unauthorized" after a while** Refresh tokens expired. Disconnect the account in `Preferences` → `Accounts` and reconnect.

**Search returns nothing for terms that are in your files** The semantic index hasn't been built yet, or the embedding model isn't pulled. Open the Search tab and click `Rebuild index`. If that fails, check that `nomic-embed-text` (or your chosen embedding model) is installed under `Preferences` → `AI & Agents`.

**`Shopping List.md` keeps getting created when you wanted `Grocery List.md`** Check your `MY PREFERENCES.md` `## Managed Files` section is in one of the recognized formats (see [Step 7](#step-7--edit-my-preferencesmd-to-teach-the-agents)). Tail the electron log — it logs the resolved binding (`shopping → Grocery List.md`) on every parse — so you can see exactly what the parser saw. The log file path is OS-dependent: on macOS it's `~/Library/Logs/Knowledge/main.log`.

**The UI feels janky during agent runs** Agent runs broadcast status updates at ~2 s cadence and rAF-coalesce them on the renderer. If you're still seeing frame drops, check `Preferences` → `AI & Agents` and switch to a smaller model — your machine may not have headroom for the chat model you picked.

**Capturing a perf trace when the UI freezes** The renderer exposes a diagnostic on `window.__perf` (always present, disabled by default). Open DevTools (`Cmd+Option+I` on macOS) and run:

```
__perf.enable()           // start tracking long tasks, Vuex commits, IPC
// reproduce the freeze: click Run, type into a note, scroll, etc.
__perf.report()           // prints a categorized summary in the console
__perf.disable()          // stop tracking
```

The report names the longest blocking tasks, which Vuex mutations fired the most often, and which IPC channels dominated. If you want tracking from the moment the renderer boots, run `localStorage.setItem('mt:perf', '1')` once — it'll auto-enable on every renderer start until you remove the flag.

**`Cannot find module 'better-sqlite3'` or build error during `yarn install`** SQLite (via [`better-sqlite3`](https://github.com/WiseLibs/better-sqlite3)) backs the semantic index. The standard install path is:

```
yarn install && yarn rebuild
```

`yarn install` downloads a prebuilt binary matching your Node version. `yarn rebuild` then re-compiles it against the Electron-bundled Node ABI (this step always builds from source — Xcode Command Line Tools are required on macOS: `xcode-select --install`).

If the install fails on the `[4/4] Building fresh packages` step with a C++20 / `requires` / `is_base_of_v` error like:

```
prebuild-install warn install No prebuilt binaries found (target=24.x.x runtime=node arch=arm64 …)
…/v8config.h: error: "C++20 or later required."
```

…you're on a Node version newer than the prebuilts shipped by your pinned `better-sqlite3` version, and the source-compile against your system Node's V8 headers requires C++20 which the legacy build config doesn't enable. Two ways to recover:

1. **Use Node 22 LTS for the install step** (recommended). Native modules almost always ship prebuilts for the active LTS. With [`nvm`](https://github.com/nvm-sh/nvm):
	```
	nvm install 22
	nvm use 22
	yarn install && yarn rebuild
	# afterwards you can switch back to whatever Node version you prefer for daily work
	```
2. **Force prebuild-install to fetch the Electron prebuild instead** (skips system Node entirely):
	```
	npm_config_runtime=electron npm_config_target=18.0.0 npm_config_dist_url=https://atom.io/download/electron yarn install
	yarn rebuild
	```

If `yarn rebuild` fails with `ModuleNotFoundError: No module named 'distutils'`, you're running Python 3.12 or newer (which removed `distutils` from the standard library) and the bundled `node-gyp` is too old to know about it. The fix is the `@electron/rebuild` bump that's already in `devDependencies` (it ships node-gyp 10.x with `gyp-next`, which works on Python 3.12+) — make sure your `node_modules` reflects the latest lockfile by deleting it and reinstalling:

```
rm -rf node_modules
yarn install && yarn rebuild
```

If you can't or don't want to upgrade, the immediate workaround is to install `setuptools` system-wide (it ships a `distutils` shim):

```
pip3 install --user setuptools
```

…or use a Python ≤ 3.11 by exporting `npm_config_python`:

```
npm_config_python=$(which python3.11) yarn rebuild
```

Either path gets you a working `better-sqlite3` for Electron 18. Once the binary is on disk in `node_modules/better-sqlite3/build/Release/better_sqlite3.node`, the app works regardless of which Node version you launch with.

**Search returns nothing but the words are clearly in my indexed files** The search engine has two admission gates: keyword (≥ 0.5 token overlap or a single-word exact match) OR semantic (≥ 0.45 cosine similarity to the embedded query). Either gate alone admits a chunk. If your query still finds nothing, run the diagnostic from DevTools:

```
await __searchDebug.run("the words you searched for")
```

It prints three tables — a SUMMARY (token count, gate pass counts, admitted vs returned), a NEAR-MISSES table (chunks containing your keyword but below both gates), and the TOP RESULTS that did surface. If `weakKeywordMissed` is high while `returned` is 0, the chunks are in the index but the gates filtered them out — share the output and we can re-tune `KEYWORD_GATE` / `SEMANTIC_GATE` in `src/main/knowledge/semanticIndexService.js`. If a result has a small ⚠ "no text" badge, the file's body couldn't be extracted (common for password-protected PDFs); try a different file format or open the file directly to confirm. The same search call also writes a one-line `[search] q=… kwGate=… semGate=… admitted=… returned=…` summary to `~/Library/Logs/Knowledge/main.log` on every search.

---

## Architecture and developer docs

- Canonical product spec: [docs/dev/KNOWLEDGE\_APP\_SPEC.md](https://github.com/matvelloso/knowledge/blob/develop/docs/dev/KNOWLEDGE_APP_SPEC.md)
- Architecture overview: [docs/dev/ARCHITECTURE.md](https://github.com/matvelloso/knowledge/blob/develop/docs/dev/ARCHITECTURE.md)
- Build / packaging: [docs/dev/BUILD.md](https://github.com/matvelloso/knowledge/blob/develop/docs/dev/BUILD.md)
- Debugging: [docs/dev/DEBUGGING.md](https://github.com/matvelloso/knowledge/blob/develop/docs/dev/DEBUGGING.md)
- Interface guide: [docs/dev/INTERFACE.md](https://github.com/matvelloso/knowledge/blob/develop/docs/dev/INTERFACE.md)

Source layout:

```
src/
├── main/                     # Electron main process
│   ├── app/                  # window, lifecycle, accessor wiring
│   ├── dataCenter/           # persistent app state (electron-store)
│   ├── preferences/          # MarkText-inherited preferences store
│   └── knowledge/            # all the new product code
│       ├── localMailService.js
│       ├── localModelProviderService.js
│       ├── connectedAccountService.js
│       ├── googleProviderAdapter.js
│       ├── microsoftProviderAdapter.js
│       ├── oauth/                       # OAuth 2.0 + PKCE flows
│       ├── agentOrchestratorService.js  # Run pipeline (the "Run" button)
│       ├── resourceIndexService.js      # workspace + external folders
│       ├── documentIngestionService.js  # PDF / docx / xlsx / etc.
│       ├── semanticIndexService.js      # embeddings + hybrid search
│       ├── knowledgeGraphService.js     # topic clustering, projects
│       ├── emailStyleService.js         # voice profile for AI reply
│       ├── workspaceBootstrapService.js
│       ├── managedFilesRegistry.js      # MY PREFERENCES.md → kind map
│       └── templates.js                 # bootstrap file content
├── common/
│   ├── managedFiles.js       # parser + defaults shared with renderer
│   └── htmlSanitizer.js      # email-body sanitizer
├── renderer/                 # Vue 2 / Vuex
│   ├── components/
│   │   ├── mail/             # Gmail-style mail UI
│   │   ├── editorWithTabs/   # muya tabs, compose
│   │   ├── sideBar/          # workspace tree + email folders
│   │   ├── statusBar/        # Sync / Run / Cancel
│   │   └── resourceView/     # legacy mail thread, document, search dispatcher
│   ├── prefComponents/       # Preferences panes (AI & Agents, Accounts…)
│   └── store/                # Vuex modules
└── muya/                     # markdown editor library (forked from MarkText)
```

---

## Safety model

Knowledge protects user-authored content by design:

- Agents may **create** new knowledge notes and **add** to managed list files in their dedicated `## Agent-managed` section.
- Agents may NOT silently rewrite or delete content in `## User-managed` sections.
- Anything an agent wants to do to user content becomes a **Suggestion** in the review queue with rationale, confidence, and source links.
- Bootstrap is idempotent — re-running it never overwrites an existing file. New default files (e.g., `Pending Emails.md` if you didn't have it before) get created; existing ones are left alone.
- OAuth tokens and the Google desktop client secret live in your OS keychain, not in the workspace.

---

This is a fork of [MarkText](https://github.com/marktext/marktext). The lineage shows up in the editor (Muya), preferences, theming, and the build system. Everything under `src/main/knowledge/`, `src/renderer/components/mail/`, and the agent orchestration is new.