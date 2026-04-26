# Cerebro Roadmap

A high-level view of what's coming. Order is intent, not commitment — priorities shift based on user feedback and feasibility.

---

## ✅ Done — v6.0 Foundation
- Native PyInstaller backend (no Docker)
- Persistent FAISS-backed memory
- Split chat/agent authentication
- Bring-Your-Own-Model endpoint configuration
- Strict proprietary licensing & private source repo

---

## 🚧 In Progress — v6.0 → v6.1
- 🍎 **macOS installer** — Universal binary (Intel + Apple Silicon)
- 🛡️ **Code signing** — Eliminate SmartScreen and Gatekeeper warnings on first install
- 🔄 **Auto-update polish** — Smoother in-app upgrade flow with delta patches
- 📊 **Memory analytics** — Visualize what Cerebro remembers about you
- 🎙️ **Voice mode improvements** — Streaming transcription, lower latency

---

## 🔭 Planned — v6.2
- 🪟 **Windows ARM64** — Native build for Snapdragon Copilot+ PCs
- 🤖 **Agent marketplace** — Share and install community-built agent recipes
- 🧩 **Capability pack browser** — Discover and install new capabilities from a curated catalog
- 📱 **Mobile companion app** — iOS / Android app to chat with your desktop Cerebro remotely
- 🔐 **Memory encryption at rest** — Optional local password protection for the memory store

---

## 💭 Exploring — Future
- 🌐 **Multi-device sync** — Optional encrypted memory sync between your devices
- 🎨 **Custom themes** — Community-built UI themes
- 🔌 **Plugin SDK** — Build your own capability packs without forking
- 🧪 **Local model auto-config** — Detect installed Ollama/LM Studio and auto-suggest endpoints
- 🤝 **Team mode** — Shared memory pools for small teams (with strong access controls)

---

## ❌ Not Planned
- ❌ Web version (Cerebro is local-first by design)
- ❌ Open-sourcing the backend (it's proprietary; that's intentional)
- ❌ Bundling AI models in the installer (BYO-Model is the right pattern)
- ❌ Cloud-only mode without local memory
- ❌ Mandatory account linking with third-party social logins

---

## How to Influence the Roadmap

Open a [feature request](https://github.com/Professor-Low/Cerebro-Installer/issues/new?template=feature_request.yml) — the issues with the most reactions get prioritized for review.
