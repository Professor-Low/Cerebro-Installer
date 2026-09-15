## macOS (Apple Silicon) — First Release

Download `Cerebro-Installer.dmg`, open it, drag **Cerebro** into Applications, then eject.

**First launch:** macOS will block the app because it is not yet signed. Go to **System Settings → Privacy & Security**, scroll to the Security section, and click **Open Anyway** — then confirm with your password or Touch ID. On macOS 15 Sequoia and macOS 26 Tahoe, Control-click → Open no longer works; Settings is the only GUI route. Alternatively: `xattr -dr com.apple.quarantine /Applications/Cerebro.app`.

This is a one-time step. Repeat it after each manual update — auto-update is not available on macOS yet.

See [docs/USER_GUIDE.md](docs/USER_GUIDE.md#macos-apple-silicon) for the full walkthrough and [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md#macos) for common issues.
