# Bring Your Own Model (BYO-Model) Setup

Cerebro can use a **local AI model** instead of (or in addition to) the cloud Claude API. Any OpenAI-compatible HTTP endpoint will work.

---

## Why BYO-Model?

- **Privacy:** Conversations never leave your machine
- **Cost:** No per-token API charges
- **Latency:** Often faster on capable hardware
- **Offline:** Keep working when the internet is out
- **Hardware utilization:** Make use of that GPU you bought

---

## Supported Servers

Any server that implements the OpenAI Chat Completions API works. Tested with:

| Tool | Default endpoint | Notes |
|---|---|---|
| **Ollama** | `http://localhost:11434/v1` | Easiest setup. `ollama pull llama3.2` then `ollama serve`. |
| **LM Studio** | `http://localhost:1234/v1` | GUI for browsing and downloading models. Click "Start Server" in the Local Server tab. |
| **vLLM** | `http://localhost:8000/v1` | High-performance, GPU-only. `python -m vllm.entrypoints.openai.api_server --model <model-id>` |
| **llama.cpp server** | `http://localhost:8080/v1` | Lightweight C++ server. `./server -m <model.gguf> -c 4096` |
| **text-generation-webui** | `http://localhost:5000/v1` | Enable the OpenAI extension. |
| **Open WebUI** | varies | Use the underlying Ollama or other backend directly |

---

## Setup (Ollama example)

1. **Install Ollama** from [ollama.com](https://ollama.com/)
2. **Pull a model:**
   ```bash
   ollama pull llama3.2:3b
   # or for a more capable model:
   ollama pull qwen2.5:14b
   ```
3. **Start the server** (Ollama runs as a background service automatically on most platforms; if not):
   ```bash
   ollama serve
   ```
4. **In Cerebro:**
   - Open **Settings → BYO-Model**
   - **Endpoint URL:** `http://localhost:11434/v1`
   - **API Key:** `ollama` (or any non-empty string — Ollama doesn't check)
   - **Model:** `llama3.2:3b` (or whatever you pulled)
   - **Routes:** pick which surfaces use this endpoint:
     - `chat` — main chat interface
     - `agents` — spawned agent workloads
     - `embeddings` — memory vector indexing (only enable if your server has an embeddings endpoint)
     - `all` — everything
   - **Save**

5. Send a test message in chat. Watch the model picker indicator — it should show your local model is active.

---

## Routing — When to use which model

You can mix and match per surface:

- **Chat → local, Agents → cloud:** Privacy for conversations, full power for heavy workloads
- **Chat → cloud, Agents → local:** Best for fast chat responses, batch agent work locally
- **Embeddings → cloud:** Recommended unless your local server has a strong embedding model. Cloud embeddings are cheap and high-quality.

---

## Troubleshooting

### "Connection refused" or "Endpoint not reachable"
- Confirm the server is running: `curl <endpoint>/models`
- Check firewalls / Windows Defender / VPN routing
- For WSL or Docker-based local models, you may need `host.docker.internal` instead of `localhost`

### Cerebro keeps falling back to cloud
- This is automatic when the local endpoint health check fails
- Check **Settings → BYO-Model → Status** for the last error
- Toggle **Strict mode** in BYO-Model settings to disable fallback (Cerebro will error instead of using cloud)

### Embeddings don't work locally
- Most local servers don't ship a great embedding model out of the box
- Recommendation: keep embeddings on cloud (`voyage-ai` or Anthropic), generation on local

### Performance is slow
- Most likely your model is too large for available RAM/VRAM. Try a smaller model.
- For Ollama: `ollama ps` shows what's loaded. `ollama rm <model>` to free space.

---

## Recommendations by Hardware

| Hardware | Recommended local model |
|---|---|
| **8 GB RAM, no GPU** | Cloud only. Local will be too slow. |
| **16 GB RAM, no GPU** | `llama3.2:3b` for chat. Embeddings on cloud. |
| **16 GB RAM + 8GB VRAM GPU** | `qwen2.5:7b` or `llama3.1:8b` |
| **32 GB RAM + 12+GB VRAM GPU** | `qwen2.5:14b` or `llama3.1:14b` |
| **64 GB RAM + 24+GB VRAM GPU** | `qwen2.5:32b` or `llama3.1:70b` (quantized) |

For the very best local quality, look into **DeepSeek**, **Qwen 2.5/3**, and the latest Llama generations on the [Ollama library](https://ollama.com/library).
