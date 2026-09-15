# Troubleshooting

Common issues and fixes.

---

## macOS

### Gatekeeper blocks launch — "Apple could not verify…"

The `.dmg` is unsigned, so macOS quarantines it on first open. The fix is a one-time step:

**Settings route (required on macOS 15 Sequoia and macOS 26 Tahoe):**
1. After the Gatekeeper dialog appears, click **Done** or **Cancel** — do not click Move to Trash.
2. Open **System Settings → Privacy & Security** and scroll to the **Security** section near the bottom.
3. You will see a message about Cerebro and an **Open Anyway** button. Click it.
4. Confirm with your password or Touch ID.
5. Launch Cerebro again — it will open normally.

> On macOS 15 Sequoia and macOS 26 Tahoe, the old Control-click → Open shortcut no longer bypasses Gatekeeper. The Privacy & Security route is the only GUI option.

**Terminal route (any macOS version):**
```bash
xattr -dr com.apple.quarantine /Applications/Cerebro.app
```
Run this once after installation, then launch normally.

Repeat this step each time you install an updated `.dmg`.

---

### "Cerebro is damaged and can't be opened. You should move it to the Trash."

This is the same Gatekeeper quarantine, shown when the app was downloaded via a browser. Do **not** reinstall — the file is not damaged. Clear the quarantine attribute:

```bash
xattr -dr com.apple.quarantine /Applications/Cerebro.app
```

If you already moved the app to the Trash, drag it back to `/Applications` first, then run the command.

---

### Chrome not found on macOS

Cerebro requires Google Chrome installed at `/Applications/Google Chrome.app`. Download it from [google.com/chrome](https://www.google.com/chrome/) and install normally.

If Chrome is installed elsewhere, set the path manually: **Settings → File Access → Browser Path**.

---

### App opens but shows nothing / backend not starting

1. Wait 15 seconds — the bundled backend binary takes a moment on first launch.
2. Check **Settings → Connection** — confirm host is `127.0.0.1` and port is `59000`.
3. Check logs in two places:
   - `~/Library/Logs/Cerebro/` (macOS system logs)
   - `~/.config/Cerebro/logs/` (app logs)
4. Look for `Address already in use` in the logs — if present, a previous Cerebro process is still running. Quit it from the Dock and relaunch.

---

### First-launch wizard asks for a password when installing Tailscale, Node.js, or Claude Code

This is expected. The first-launch wizard installs these components system-wide and needs administrator access to do so. Enter your Mac login password when prompted.

---

## Installation

### Windows: "Windows protected your PC" SmartScreen warning
The installer is not yet code-signed (coming in v6.1). To proceed:
1. Click **More info**
2. Click **Run anyway**

This warning will go away once code signing is in place.

### Linux: AppImage won't launch
Make sure the file is executable:
```bash
chmod +x Cerebro-Installer.AppImage
```

If you see `FUSE` errors on Ubuntu 22.04+:
```bash
sudo apt install libfuse2
```

---

## First Launch

### Backend won't start / "Backend connection failed"
1. Wait 10 seconds — the bundled backend binary takes a few seconds to initialize on first launch
2. Check **Settings → Connection** — confirm host is `127.0.0.1` and port is `61000` (or whatever you configured)
3. Look at the backend log: `<data>/logs/backend.log`
4. If you see `Address already in use`, another Cerebro instance is running. Quit it from the system tray and relaunch.

### Claude sign-in opens browser but never returns
- Make sure no popup blocker or browser extension is interfering
- Try signing in via your default browser (Cerebro uses your default browser for OAuth)
- If repeated failures, try **Settings → About → Reset Account** and try again

---

## Memory & Performance

### Memory tab is empty after upgrade
If you upgraded from v5, the migration may not have completed. Manually trigger it:
**Settings → AI Memory → Migrate from v5**

### Cerebro feels slow / high memory usage
- Memory rebuilds rebuild the FAISS index — this is heavy. Wait for it to finish or trigger consolidation in **Settings → AI Memory → Consolidate**
- Check **Settings → AI Memory → Garbage Collect** to remove stale memories
- If you have very large memory archives (10k+ entries), consider exporting and starting fresh

### Agents are stuck "spawning"
- Open the Agents tab and check the agent status
- Most stuck agents resolve in 60 seconds; if not, click **Cancel** and respawn
- If all agents are stuck, restart Cerebro from the system tray (this just restarts the backend, not the OS)

---

## BYO-Model

### Local model endpoint not working
1. Make sure your local model server is actually running: `curl http://localhost:11434/v1/models` (or your endpoint)
2. Check Cerebro's BYO-Model settings — make sure the URL ends with `/v1` (or the OpenAI-compatible path)
3. Some servers require a dummy API key — try setting it to `not-needed` in Cerebro
4. Check Cerebro's logs for the actual error response

### Cerebro keeps falling back to cloud even though local is configured
This is expected if the local endpoint is unreachable. Check **Settings → BYO-Model → Status** for the last health check result.

---

## Updates

### Auto-update doesn't trigger
- Make sure you're online
- Force a check: **Settings → About → Check for Updates**
- Manually download from [Releases](https://github.com/Professor-Low/Cerebro-Installer/releases/latest) if needed

### Update fails to install
- Quit Cerebro completely (system tray → Quit)
- Run the installer manually
- If still failing, uninstall and reinstall — your data is preserved in the data directory

---

## Browser Automation

### Browser agent says "Chrome not found"
Cerebro uses your installed Google Chrome. Install Chrome from [google.com/chrome](https://www.google.com/chrome/) if you don't have it.

If Chrome is installed but not detected, manually set the path in **Settings → File Access → Browser Path**.

---

## Still stuck?

Open an issue with:
1. Cerebro version (Settings → About)
2. Operating system + version
3. What you tried
4. Relevant snippets from `<data>/logs/backend.log` and `<data>/logs/main.log`

[Open an issue →](https://github.com/Professor-Low/Cerebro-Installer/issues/new/choose)
