<div align="center">
  <a href="https://cerebro.life">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="./assets/logo-on-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="./assets/logo-on-light.png">
      <img alt="Cerebro" src="./assets/logo-on-light.png" width="38%">
    </picture>
  </a>

  <h3>The AI operations platform that never forgets.</h3>
  <sub>Persistent memory · Autonomous agents · Browser automation · Runs on your machine</sub>

  <br><br>

  <a href="https://github.com/Professor-Low/Cerebro-Installer/releases/latest"><img src="https://img.shields.io/github/v/release/Professor-Low/Cerebro-Installer?include_prereleases&style=for-the-badge&label=Release&color=6366F1" /></a>
  <a href="https://cerebro.life"><img src="https://img.shields.io/badge/cerebro.life-000000?style=for-the-badge" /></a>
  <a href="https://discord.gg/pTHdCFnXfz"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" /></a>

  <p>
    <a href="https://github.com/Professor-Low/Cerebro-Installer/releases/latest"><b>Download</b></a> ·
    <a href="docs/USER_GUIDE.md">User Guide</a> ·
    <a href="CHANGELOG.md">Changelog</a> ·
    <a href="ROADMAP.md">Roadmap</a> ·
    <a href="https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose">Report a bug</a>
  </p>
</div>

---

## What is Cerebro?

Cerebro is a desktop AI platform that **remembers every conversation**, learns from your corrections, and gets sharper over time. Your projects, decisions and preferences persist across sessions and are shared by every agent it runs.

It **deploys specialized agents** that work in parallel, **drives a real Chrome browser** to fill forms, read pages and take screenshots, and runs on **Claude, Codex or your own local models**, all from one app. It uses the Claude or ChatGPT subscription you already pay for. No API keys.

## Features

| | |
|---|---|
| **Persistent memory** | Conversations, learnings and corrections are indexed with FAISS vector search and recalled across sessions. |
| **Agent orchestration** | Spawn workers, researchers, coders and analysts in parallel. Each has a defined role and reports back. |
| **Browser control** | Drives a real Chrome instance for forms, scraping, screenshots and multi-step automations. |
| **Claude, Codex or local** | Runs on Claude Code or Codex through your own subscription login, or on local models through any OpenAI-compatible server (Ollama, LM Studio, llama.cpp, vLLM). |
| **Native desktop app** | No Docker and no terminal. Download, install, launch. A setup wizard installs the prerequisites for you. |
| **Runs on your machine** | Memory and data live locally in `~/.cerebro/`. No telemetry on your conversations. |
| **Auto-updates** | Windows, Linux and macOS update in place when a new release ships. |
| **Voice input** | Optional voice transcription for hands-free use. |

## Download

| Platform | File | Install |
|---|---|---|
| **Windows 10/11** (x64) | [`Cerebro-Installer.exe`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest/download/Cerebro-Installer.exe) | Run it and follow the prompts |
| **macOS** (Apple Silicon) | [`Cerebro-Installer.dmg`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest/download/Cerebro-Installer.dmg) | Drag Cerebro to Applications. First launch needs one approval, see [macOS setup](docs/USER_GUIDE.md#macos-apple-silicon) |
| **Linux** (x64) | [`Cerebro-Installer.AppImage`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest/download/Cerebro-Installer.AppImage) | `chmod +x`, then run |
| **Debian / Ubuntu** | [`Cerebro-Installer.deb`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest/download/Cerebro-Installer.deb) | `sudo apt install ./Cerebro-Installer.deb` |

Optional connectors (WhatsApp, Phone Link) are attached to each [release](https://github.com/Professor-Low/Cerebro-Installer/releases/latest).

## Requirements

- Windows 10/11 x64, macOS on Apple Silicon, or Ubuntu 20.04+ / compatible Linux
- 8 GB RAM minimum, 16 GB recommended
- 2 GB free disk space, SSD recommended
- A Claude subscription (for Claude Code) or a ChatGPT subscription (for Codex), or a local model server
- Google Chrome for browser automation (auto-detected)
- A Cerebro license key or access code, from [cerebro.life](https://cerebro.life)

## Quick start

1. **Download** the installer for your platform above.
2. **Install** and launch Cerebro.
3. **Activate** with your license key or access code.
4. **Let the setup wizard** install prerequisites and sign you in to Claude Code.
5. **Start a conversation.** Cerebro starts remembering immediately.

Full walkthrough in the [User Guide](docs/USER_GUIDE.md).

## Documentation

- [User Guide](docs/USER_GUIDE.md): setup, core features, day-to-day use
- [FAQ](docs/FAQ.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Local models](docs/BYO_MODEL.md): connect Ollama, LM Studio and other servers
- [Privacy](docs/PRIVACY.md): what Cerebro stores and where
- [Changelog](CHANGELOG.md) · [Roadmap](ROADMAP.md)

## Privacy and security

- Memory, conversation history and settings live on your machine in `~/.cerebro/`.
- AI requests go straight from your machine to the provider you choose, using your own login: Anthropic for Claude, OpenAI for Codex, or your local model server.
- Cerebro contacts cerebro.life to validate your license, and GitHub to check for updates.
- No third-party analytics and no tracking of your conversations.

Report vulnerabilities through [SECURITY.md](SECURITY.md). Full policy: [docs/PRIVACY.md](docs/PRIVACY.md).

## Community and support

- **Discord:** [discord.gg/pTHdCFnXfz](https://discord.gg/pTHdCFnXfz)
- **Bugs and feature requests:** [GitHub Issues](https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose)
- **Security:** [SECURITY.md](SECURITY.md)

## License

Cerebro is proprietary software. The source code is closed and may not be redistributed, modified or reverse-engineered. See [LICENSE.md](LICENSE.md) for the full End User License Agreement.

<div align="center">
  <sub>© 2026 Cerebro · <a href="https://cerebro.life">cerebro.life</a></sub>
</div>
