# Frequently Asked Questions

### Is Cerebro free?
The installer is free to download for personal and evaluation use. The source code is proprietary and not available for redistribution. See [LICENSE.md](../LICENSE.md) for details.

### Does Cerebro work offline?
Partially. Local features (memory browser, settings, the UI) work offline. AI conversations require either:
- An internet connection (for cloud Claude calls), **or**
- A local AI model running on your machine (BYO-Model mode)

### Where is my data stored?
Locally on your machine. See the [Data Locations](USER_GUIDE.md#data-locations) section of the User Guide.

### Does Cerebro send my conversations to Professor Low or anyone else?
**No.** Conversation content is local-first. Cloud AI calls go directly from your machine to Anthropic using your Claude account. We do not see your chats.

Optional anonymous diagnostic telemetry (off by default) may be enabled in Settings — see [PRIVACY.md](PRIVACY.md).

### Why do I need a Claude account?
Cerebro uses Claude as its primary cloud model. Your conversations, your account, your billing. Cerebro does not proxy or rate-limit your usage.

### Can I use a model other than Claude?
Yes — via [BYO-Model](BYO_MODEL.md). Point Cerebro at any OpenAI-compatible local endpoint (Ollama, LM Studio, vLLM, llama.cpp, etc.) and configure which routes use it.

### Does Cerebro require Docker?
**No** (as of v6.0). v5 used Docker; v6 ships a native bundled binary. If you have v5 installed, uninstall it before installing v6.

### What happens to my v5 data when I upgrade?
v5 → v6 includes a one-time migration that imports your v5 memory and conversations into the new format. Original v5 data is preserved unless you explicitly delete it.

### Is the source code available?
**No.** Cerebro v6 is proprietary closed-source. Only signed installers are distributed. The previous v5 line was source-available; that has been retired.

### Can I run Cerebro on a server / headless?
Cerebro is designed as a desktop app. A headless / server mode is not currently supported but is on the long-term roadmap.

### Why doesn't Cerebro support [my favorite feature]?
Open a [feature request](https://github.com/Professor-Low/Cerebro-Installer/issues/new?template=feature_request.yml). Issues with the most community reactions get prioritized.

### How do I uninstall?
- **Windows:** Settings → Apps → Cerebro → Uninstall
- **macOS:** Drag `Cerebro.app` from Applications to the Trash
- **Linux (AppImage):** Just delete the `.AppImage` file
- **Linux (.deb):** `sudo apt remove cerebro`

To also remove your data, delete the data directory listed in [User Guide → Data Locations](USER_GUIDE.md#data-locations).

### Why does macOS say Cerebro can't be verified / is damaged?
Cerebro is not yet signed with an Apple Developer ID, so macOS Gatekeeper blocks the first launch. This is expected for unsigned apps downloaded from the internet. To open it:

1. Go to **System Settings → Privacy & Security** and scroll to the **Security** section.
2. Click **Open Anyway** next to the Cerebro message.
3. Confirm with your password or Touch ID.

Alternatively, run `xattr -dr com.apple.quarantine /Applications/Cerebro.app` in Terminal. This is a one-time step per install. See [User Guide → macOS (Apple Silicon)](USER_GUIDE.md#macos-apple-silicon) for the full walkthrough.

### Does Cerebro auto-update on Mac?
Not yet. Auto-update is disabled on macOS for now. When a new version is available, download the latest `.dmg` from the [Releases page](https://github.com/Professor-Low/Cerebro-Installer/releases/latest), drag the new app into Applications to replace the old one, and clear the quarantine flag again. Code signing and in-app auto-update for macOS are planned.

### Is there an Intel Mac build?
Not yet — the current macOS release is Apple Silicon (arm64) only. An Intel or universal build is not on the near-term roadmap.

### Which macOS versions are supported?
macOS 12 Monterey and later, Apple Silicon only. macOS 11 Big Sur and earlier are not supported.

### How do I report a security issue?
**Privately.** See [SECURITY.md](../SECURITY.md). Do NOT open a public issue for security reports.
