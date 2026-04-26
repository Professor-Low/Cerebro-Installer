<div align="center">

# 🧠 Cerebro

### A personal AI companion that remembers everything.

**Persistent memory · Agent orchestration · Browser automation · Local-first**

[![Latest Release](https://img.shields.io/github/v/release/Professor-Low/Cerebro-Installer?include_prereleases&style=for-the-badge&color=indigo)](https://github.com/Professor-Low/Cerebro-Installer/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Professor-Low/Cerebro-Installer/total?style=for-the-badge&color=emerald)](https://github.com/Professor-Low/Cerebro-Installer/releases)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](LICENSE.md)

[**⬇️ Download Latest**](https://github.com/Professor-Low/Cerebro-Installer/releases/latest) ·
[**📖 User Guide**](docs/USER_GUIDE.md) ·
[**🗺️ Roadmap**](ROADMAP.md) ·
[**💬 Report a Bug**](https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose)

</div>

---

## What is Cerebro?

Cerebro is a desktop AI companion that **remembers every conversation you've had**, learns from your corrections, and gets sharper over time. Unlike chatbots that forget the moment you close the tab, Cerebro maintains a persistent, searchable memory of every project, decision, and detail you share with it.

It can also **deploy specialized agents** to work on tasks in parallel, **drive a real Chrome browser** to fill forms and scrape pages, and **connect to your local AI models** (Ollama, LM Studio, llama.cpp) — all from one unified desktop app.

> **Why Cerebro is different:** Most AI assistants are stateless rentals. Cerebro is a teammate that remembers you.

---

## ✨ Features

| | |
|---|---|
| 🧠 **Persistent Memory** | Every conversation, learning, and correction is indexed and recallable across sessions. Powered by FAISS vector search. |
| 🤖 **Agent Orchestration** | Spawn workers, researchers, coders, analysts in parallel. Each agent has a specific role and reports back. |
| 🌐 **Browser Control** | Drive a real Chrome instance for form-filling, scraping, screenshots, and complex automations. |
| 🔌 **Bring Your Own Model** | Optional local model support via OpenAI-compatible endpoints. Plug in Ollama, LM Studio, vLLM — Cerebro speaks all of them. |
| 🖥️ **Native Desktop App** | No Docker, no terminal, no setup wizards. Download → install → launch. Tray icon. System integration. |
| 🔒 **Local-First** | Your memory and data live on your machine. No third-party telemetry on your conversations. |
| ⚡ **System Tray** | Cerebro lives in your tray and is always one click away. |
| 🎙️ **Voice Input** | Optional voice transcription for hands-free interaction. |

---

## ⬇️ Download

| Platform | Installer | Notes |
|---|---|---|
| 🪟 **Windows 10/11 (x64)** | [`Cerebro-Installer.exe`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest) | Run installer, follow prompts |
| 🐧 **Linux (x64)** | [`Cerebro-Installer.AppImage`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest) | `chmod +x` and double-click |
| 🐧 **Debian/Ubuntu** | [`Cerebro-Installer.deb`](https://github.com/Professor-Low/Cerebro-Installer/releases/latest) | `sudo dpkg -i Cerebro-Installer.deb` |
| 🍎 **macOS** | _Coming soon_ | Targeted for v6.1 |

> All installers auto-update through GitHub releases. You'll be notified inside the app when a new version drops.

---

## 🛠️ System Requirements

**Minimum**
- Windows 10/11 x64, Ubuntu 20.04+, or compatible Linux
- 8 GB RAM
- 2 GB free disk space
- Active internet connection (for cloud AI calls)

**Recommended**
- 16 GB RAM (smoother agent orchestration)
- SSD (faster memory indexing)
- Google Chrome installed (auto-detected for browser automation)

**Optional**
- Local model server (Ollama, LM Studio, llama.cpp, vLLM) — for BYO-Model mode

---

## 🚀 Quick Start

1. **Download** the installer for your platform from [Releases](https://github.com/Professor-Low/Cerebro-Installer/releases/latest)
2. **Install** — double-click and follow the prompts
3. **Launch** Cerebro from your Start Menu / Applications folder
4. **Sign in** with your Claude account when prompted
5. **Start a conversation** — Cerebro will start remembering immediately

For detailed setup, see the [**User Guide**](docs/USER_GUIDE.md).

---

## 📚 Documentation

- [**User Guide**](docs/USER_GUIDE.md) — getting started, core features, day-to-day usage
- [**FAQ**](docs/FAQ.md) — common questions
- [**Troubleshooting**](docs/TROUBLESHOOTING.md) — fixes for common issues
- [**BYO-Model Setup**](docs/BYO_MODEL.md) — connect your local LLM
- [**Privacy Policy**](docs/PRIVACY.md) — what data Cerebro stores and where
- [**Changelog**](CHANGELOG.md) — what's new in each release
- [**Roadmap**](ROADMAP.md) — what's coming next

---

## 🔐 Privacy & Security

Cerebro is **local-first by design**:
- Your conversation history and memory live on your machine in `~/Cerebro/` (or platform equivalent)
- Cloud AI calls go directly to Anthropic using your own Claude account credentials
- No third-party analytics, no telemetry beacons, no usage tracking on your conversations
- Optional crash reporting (off by default) sends only anonymized error stacks

See [SECURITY.md](SECURITY.md) for vulnerability reporting and [docs/PRIVACY.md](docs/PRIVACY.md) for the full privacy policy.

---

## 💬 Community & Support

- **Bug reports / feature requests:** [GitHub Issues](https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose)
- **Security disclosures:** see [SECURITY.md](SECURITY.md)
- **General questions:** [Discussions](https://github.com/Professor-Low/Cerebro-Installer/discussions)

---

## 📄 License

Cerebro is **proprietary commercial software**. The installer is free to download and use for personal and evaluation purposes, but the source code is **closed and not available for redistribution, modification, or reverse-engineering**.

See [LICENSE.md](LICENSE.md) for the complete End User License Agreement.

---

<div align="center">

**Built by [Professor Low](https://github.com/Professor-Low)** · © 2026 All Rights Reserved

</div>
