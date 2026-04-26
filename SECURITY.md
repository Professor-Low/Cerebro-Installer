# Security Policy

## Reporting a Vulnerability

If you believe you have found a security vulnerability in Cerebro, **please do not open a public GitHub issue**. Instead, report it privately so we can address it before disclosure.

### How to Report

**Preferred:** Use GitHub's [Private Vulnerability Reporting](https://github.com/Professor-Low/Cerebro-Installer/security/advisories/new) form on this repository.

**Alternative:** Open a GitHub issue with the title `[SECURITY — Private Contact Request]` (no details in the body), and we will reach out via email to coordinate a private channel.

### What to Include

When reporting, please include as much of the following as possible:

- The version of Cerebro affected (e.g. `v6.0.0-alpha.1`)
- Your operating system and version
- A clear description of the vulnerability
- Steps to reproduce
- The potential impact (data exposure, code execution, privilege escalation, etc.)
- Any suggested fix or mitigation, if known

### Our Commitment

We will:
- **Acknowledge** your report within 72 hours
- **Triage** and assess severity within 7 days
- **Patch** critical vulnerabilities in the next release (typically within 14 days)
- **Credit** you in the release notes if you wish (or keep your report anonymous if you prefer)

### Coordinated Disclosure

We follow a **90-day coordinated disclosure** policy. Please give us a reasonable window to ship a fix before publicly disclosing the vulnerability. We will work with you on the timing.

---

## Supported Versions

Only the **latest released version** of Cerebro receives security updates. Pre-release alpha and beta versions receive critical fixes only.

| Version | Supported |
|---------|-----------|
| 6.x (latest) | ✅ Active support |
| 6.x (alpha/beta) | ⚠️ Critical fixes only |
| 5.x | ❌ End of life |
| < 5.x | ❌ End of life |

---

## Scope

This security policy covers:
- The Cerebro desktop application installer and bundled binaries
- Auto-update mechanisms
- Local data storage and encryption
- Inter-process communication between the Electron shell and bundled backend

**Out of scope:**
- Vulnerabilities in third-party services Cerebro connects to (Anthropic API, GitHub, etc.) — please report those to the respective vendor
- Vulnerabilities that require physical access to an unlocked device
- Social engineering attacks against end users

---

Thank you for helping keep Cerebro and its users safe.
