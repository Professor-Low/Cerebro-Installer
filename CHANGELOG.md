# Changelog

All notable changes to Cerebro are documented in this file.
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [6.0.0-alpha.1] — Unreleased

> 🚧 **First v6 alpha — coming soon.** This will be the first release distributed through the new public installer repository (`Professor-Low/Cerebro-Installer`).

### Major Changes
- **No more Docker.** The Python backend now ships as a native PyInstaller binary bundled inside the Electron app. Install size cut by ~10x, idle RAM cut by ~5x.
- **Persistent memory system fully ported** — FAISS vector search, conversation memory, learnings, and corrections work end-to-end across sessions.
- **Split chat/agent authentication** — chat and agents can now use separate Claude accounts. JIT credential preflight prevents stale-token failures.
- **BYO-Model support (early)** — point Cerebro at any OpenAI-compatible endpoint (Ollama, LM Studio, vLLM, llama.cpp) for embeddings or generation.
- **Strict proprietary licensing** — source code is now private; only signed installers are distributed.

### Added
- New `/api/memory/*` endpoints for memory CRUD and search
- New `/api/claude-accounts/*` endpoints for per-purpose account routing
- Memory viewer panel in the Mind tab
- Dual-account picker UI in the chat header
- Settings → BYO-Model section for local endpoint configuration

### Changed
- Backend runtime: Docker → native PyInstaller binary
- Distribution: source-available → proprietary closed-source
- Release pipeline: tagged builds now publish to `Cerebro-Installer` (public) instead of the source repo

### Removed
- Docker Desktop dependency
- Docker Compose stack
- All trading / IBKR references (private-only feature)
- Money page (private-only feature)

---

## [5.4.2] — 2026-03-29

Last release in the v5 (Docker-based) line. Available for download from the legacy releases page until the v6 alpha is published.

### Notes
- v5 used Docker for the backend; v6 ships a native binary
- v5 source was available under the "Cerebro Source Available License"; v6 source is closed
- Existing v5 users will be prompted to migrate when v6 is published

For the v5.x changelog history, see the [legacy release notes](https://github.com/Professor-Low/Cerebro-life-desktop/releases).

---

[6.0.0-alpha.1]: https://github.com/Professor-Low/Cerebro-Installer/releases/tag/v6.0.0-alpha.1
[5.4.2]: https://github.com/Professor-Low/Cerebro-life-desktop/releases/tag/v5.4.2
