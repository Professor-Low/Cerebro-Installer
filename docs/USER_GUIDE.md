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
   - **macOS (Apple Silicon):** See [macOS (Apple Silicon)](#macos-apple-silicon) below.
3. Launch Cerebro from your Start Menu or Applications folder.
4. The first launch will create your local data directory at `~/Cerebro/` (or platform equivalent).

### macOS (Apple Silicon)

Cerebro for macOS is distributed as an unsigned `.dmg`. macOS will block the first launch — this is expected. Follow these steps:

1. Open the downloaded `Cerebro-Installer.dmg`.
2. Drag **Cerebro** into your **Applications** folder, then eject the disk image.
3. Open **Cerebro** from Applications or Launchpad.
4. macOS will show a dialog along the lines of *"Apple could not verify 'Cerebro' is free of malware that may harm your Mac or compromise your privacy."* Click **Done** (or **Cancel**) to dismiss it — do not click Move to Trash.
5. Open **System Settings → Privacy & Security** and scroll down to the **Security** section. You will see a message about Cerebro with an **Open Anyway** button. Click it.
6. Confirm with your password or Touch ID when prompted.
7. Launch Cerebro again from Applications — it will open normally.

> **macOS 15 Sequoia and macOS 26 Tahoe:** the old shortcut of Control-clicking the app icon and choosing **Open** no longer bypasses Gatekeeper on these versions. Privacy & Security → Open Anyway is the only GUI route.

**Terminal alternative:** If you prefer the command line, run this once after dragging the app in:
```bash
xattr -dr com.apple.quarantine /Applications/Cerebro.app
```
Then launch normally.

This is a one-time step per install. If you download and install a newer `.dmg`, repeat it for the updated app.

**Updates on macOS:** Auto-update is not available on macOS yet. When a new version is released, download the latest `.dmg` from the [Releases page](https://github.com/Professor-Low/Cerebro-Installer/releases/latest), drag the new app into Applications to replace the old one, and run the Gatekeeper step again.

**Prerequisites:**
- macOS 12 Monterey or later (Apple Silicon only; Intel Mac not supported yet)
- 8 GB RAM minimum, 16 GB recommended
- Google Chrome installed in `/Applications` (required for browser automation)
- An active Claude Pro or Claude Max subscription

The first-launch wizard will install Tailscale, Node.js, and Claude Code — it will ask for your password during this step, which is expected.

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
