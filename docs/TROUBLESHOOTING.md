# Troubleshooting

Common issues and fixes.

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
