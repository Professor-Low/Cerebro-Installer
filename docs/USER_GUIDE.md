# Cerebro User Guide

A walkthrough of Cerebro's core features and how to use them day-to-day.

---

## Getting Started

### Installing

1. Download the installer for your platform from the [Releases page](https://github.com/Professor-Low/Cerebro-Installer/releases/latest).
2. Run the installer:
   - **Windows:** Double-click `Cerebro-Installer.exe`. If SmartScreen warns about an unsigned publisher, click "More info" → "Run anyway" (we're working on code signing for v6.1).
   - **Linux (.AppImage):** `chmod +x Cerebro-Installer.AppImage` then double-click.
   - **Linux (.deb):** `sudo dpkg -i Cerebro-Installer.deb`
3. Launch Cerebro from your Start Menu or Applications folder.
4. The first launch will create your local data directory at `~/Cerebro/` (or platform equivalent).

### Signing In

On first launch you'll be prompted for a Claude account. Cerebro uses the Claude CLI authentication flow:

1. Click **Sign in with Claude**
2. A browser window opens to Anthropic's auth page
3. Approve the connection
4. You'll be redirected back to Cerebro

You can use the same account for chat and agents, or split them — see [BYO-Model & Account Routing](#account-routing) below.

---

## The Six Tabs

Cerebro is organized into six tabs in the left sidebar:

| Tab | Icon | What it's for |
|---|---|---|
| **Home** | 🏠 | Quick stats, recent activity, jump-back to recent conversations |
| **Chat** | 💬 | Talk to Cerebro. The main interface. |
| **Agents** | 🤖 | Spawn and monitor specialized agents working in parallel |
| **Mind** | 🧠 | Browse Cerebro's memory — what it remembers about you |
| **Auto** | ⚙️ | Schedule recurring tasks (cron-like automations) |
| **Settings** | ⚡ | Configure accounts, models, file access, audio, and more |

---

## Chat

The Chat tab is where you'll spend most of your time. Type a message and Cerebro responds, drawing on its full memory of past conversations.

**Tips:**
- **Persistent memory:** Cerebro automatically remembers important facts. You don't need to repeat yourself.
- **Voice input:** Click the microphone icon for hands-free dictation (requires Settings → Voice & Audio enabled).
- **File uploads:** Drag and drop files into the chat to share them with Cerebro.

---

## Agents

The Agents tab lets Cerebro spawn specialized workers to do things in parallel.

**Common agent types:**
- **Worker** — General-purpose task execution
- **Researcher** — Web research and fact-finding
- **Coder** — Write or modify code
- **Analyst** — Examine data and produce reports
- **Browser agent** — Drive the Chrome instance for automation

You can spawn agents directly from chat ("Cerebro, deploy three researchers to look into X") or from the Agents tab UI.

---

## Mind (Memory Browser)

The Mind tab shows you what Cerebro remembers — every conversation summary, every learning, every correction.

**You can:**
- Search memories by keyword or semantic similarity
- Manually delete memories you don't want kept
- Export your full memory archive (Settings → AI Memory → Export)
- Trigger a memory consolidation pass (compacts older memories into summaries)

**Privacy:** All memory data lives on your machine in the path shown at the top of the Mind tab. Nothing is sent to third parties.

---

## Auto (Automations)

The Auto tab lets you schedule recurring tasks. Examples:
- Daily morning brief at 7am
- Weekly summary of all your projects every Sunday
- Hourly check on a specific website

Automations run as worker agents on the schedule you set.

---

## Settings

### General
- App appearance, startup behavior, tray settings

### Connection
- Backend host/port (rarely needs changing)

### AI Memory
- Memory storage path
- Manual memory operations (consolidate, garbage-collect, rebuild index)
- Export / import memory archives

### Voice & Audio
- Microphone selection
- Voice input language
- Optional voice output (text-to-speech)

### File Access
- Folders Cerebro is allowed to read/write
- Recent file activity log

### About / Account
- Current version
- Active Claude account(s)
- Sign out / switch accounts

### Account Routing

Cerebro supports **two separate Claude accounts** — one for the chat interface, one for spawned agents. This lets you use a personal account for chat and a project/team account for heavy agent workloads.

To configure:
1. Go to **Settings → About / Account**
2. Click **Configure Account Routing**
3. Sign in to the additional account
4. Pick which account each surface uses

---

## BYO-Model (Bring Your Own Model)

Cerebro can talk to any **OpenAI-compatible** local model server. Common options:

| Tool | Default endpoint |
|---|---|
| **Ollama** | `http://localhost:11434/v1` |
| **LM Studio** | `http://localhost:1234/v1` |
| **vLLM** | `http://localhost:8000/v1` |
| **llama.cpp server** | `http://localhost:8080/v1` |
| **Text Generation WebUI** | `http://localhost:5000/v1` |

To configure:
1. Start your local model server (e.g. `ollama serve`)
2. Open Cerebro → **Settings → BYO-Model**
3. Enter the endpoint URL
4. Pick which routes use it (chat, agents, embeddings, or all)
5. Save

If your local model is unreachable, Cerebro automatically falls back to cloud (Anthropic).

For a deeper walkthrough see [BYO_MODEL.md](BYO_MODEL.md).

---

## Updating

Cerebro auto-checks for updates on launch and every 4 hours. When a new version is available, you'll see a prompt in the bottom-right corner. Updates are downloaded in the background and applied on next launch.

To check manually: **Settings → About → Check for Updates**.

---

## Data Locations

| Platform | Cerebro data |
|---|---|
| **Windows** | `%USERPROFILE%\Cerebro\` |
| **macOS** | `~/Library/Application Support/Cerebro/` |
| **Linux** | `~/.config/Cerebro/` (or `$XDG_CONFIG_HOME/Cerebro/`) |

Memory specifically lives in `<data>/memory/`. Logs are in `<data>/logs/`.

---

## Help

- [FAQ](FAQ.md)
- [Troubleshooting](TROUBLESHOOTING.md)
- [Open an issue](https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose)
