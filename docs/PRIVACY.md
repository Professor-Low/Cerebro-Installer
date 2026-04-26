# Privacy Policy

**Effective Date:** April 26, 2026
**Version:** 1.0

This privacy policy describes what data Cerebro collects, where it lives, and what we (Professor Low) can and cannot see.

---

## TL;DR

- **Your conversations and memory are stored locally on your device.** We do not have access to them.
- **Cloud AI requests go directly from your machine to Anthropic** using your own Claude account credentials.
- **No analytics, no tracking, no telemetry on your conversations.**
- **Optional anonymous diagnostic telemetry** (off by default) may report crashes and version usage. You control it in Settings.

---

## Data Categories

### 1. Conversation & Memory Data

**What:** Your chat history, agent outputs, memories, learnings, corrections, file uploads, and any data you generate while using Cerebro.

**Where it lives:** Locally on your device, in your data directory:
- Windows: `%USERPROFILE%\Cerebro\`
- macOS: `~/Library/Application Support/Cerebro/`
- Linux: `~/.config/Cerebro/`

**Who can see it:** Only you (and anyone who has access to your device).

**Sent to Licensor:** **Never.**

### 2. AI Model Requests

**What:** The text of your conversations and agent prompts is sent to AI model providers to generate responses.

**Where it goes:**
- **Cloud Claude:** Directly to Anthropic's API endpoints, using YOUR Claude account credentials. Subject to [Anthropic's Privacy Policy](https://www.anthropic.com/legal/privacy).
- **Local BYO-Model:** Stays on your device (sent to your local AI server only).

**Sent to Licensor:** **Never.** Cerebro does not proxy or intercept these requests.

### 3. Authentication Tokens

**What:** OAuth tokens for your Claude account, stored locally to keep you signed in.

**Where it lives:** In your OS's secure credential store (Windows Credential Manager, macOS Keychain, libsecret on Linux) and/or in your local Cerebro data directory.

**Sent to Licensor:** **Never.**

### 4. Update Checks

**What:** When checking for updates, Cerebro contacts GitHub Releases to see if a newer version is available.

**Data sent:** Standard HTTP request headers (User-Agent including Cerebro version + your platform). No personal data.

**Where it goes:** GitHub. Subject to [GitHub's Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

### 5. Optional Diagnostic Telemetry

**Off by default.** Can be enabled in **Settings → General → Send anonymous diagnostics**.

**What's included if enabled:**
- Anonymized crash reports (stack traces with no personal content)
- Cerebro version and platform
- Aggregate feature usage counters (e.g. "agents spawned: 12 today" — never the agent prompts themselves)

**What's NEVER included:**
- Conversation content
- Memory data
- File names or paths
- Account identifiers
- IP addresses (we only see country-level geo from request headers)

**Where it goes:** A diagnostics endpoint operated by Licensor. Used solely for debugging crashes and prioritizing improvements. Never sold, never shared with third parties, never used for advertising.

---

## Third-Party Services Cerebro May Contact

| Service | What for | When |
|---|---|---|
| **Anthropic API** | Cloud AI generation | Whenever you chat / spawn agents (using cloud) |
| **GitHub Releases** | Update checks | On launch + every 4 hours |
| **GitHub Issues / Security Advisories** | Bug reports you submit | Only when you click "Report bug" |
| **Local AI server** (if configured) | BYO-Model generation | When BYO-Model is enabled and routed |
| **Google Chrome** (if installed) | Browser automation features | Only when you use a browser agent |

---

## Your Rights

- **Access:** All your data is local — open the data directory and read it.
- **Export:** Use **Settings → AI Memory → Export** for a portable archive.
- **Deletion:** Delete the data directory to wipe everything. Uninstalling does NOT delete data by default (so upgrades are seamless).
- **Telemetry control:** Toggle in Settings any time. Defaults to off.
- **Account disconnection:** Sign out of your Claude account in Settings.

---

## Children

Cerebro is not directed at children under 13. We do not knowingly collect data from children.

---

## Changes to This Policy

We may update this policy. Material changes will be highlighted in the [CHANGELOG](../CHANGELOG.md) and a notice will appear in-app.

---

## Contact

Privacy questions: open an issue at [github.com/Professor-Low/Cerebro-Installer/issues](https://github.com/Professor-Low/Cerebro-Installer/issues) with the `[PRIVACY]` prefix in the title.
