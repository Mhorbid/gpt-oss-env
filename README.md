
## 📦 <b>What is this?</b>

A shit-simple `docker‑compose.yaml` that brings the power of GPT‑OSS-20B right to your doorstep.<br>
Kick it up with just a couple of commands and you’ll be chatting with an AI in no time!

---

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/Mhorbid/gpt-oss-env.git
cd gpt-oss-env

# Launch the stack
docker compose up -d
# This will take a while...
# vLLM has to download the model!

# Open the UI when the download is done
start http://localhost:8080
# Use any email to register an admin account
# It doesn't matter, it's a local account

# Stop the stack
# docker compose down
```

## 🐛 Features

**GPU Support** –       This compose setup will use all available gpus (NVIDIA recommended).<br>
**Presistent Data** -   Data (including chats) are saved to a postgresql database.<br>
**Local AI** -          Corpo-overlords will not be able to harvest your data.<br>
**Point-Click** –       No setup required, just compose and go!

---

## 📁 Project Layout

```text
├── docker-compose.yaml
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE/
├── README.md
└── LICENSE
```

All heavy lifting is done inside `docker‑compose.yml`; no build steps are required.

---

## 🌐 Services Overview

| Service   | Image                                            | Ports | Purpose |
|-----------|--------------------------------------------------|-------|-------|
| `vllm`    | `vllm/vllm-openai:latest`         | 8000  | Fast inference engine powered by NVIDIA’s LLM framework |
| `openwebui` | `ghcr.io/open-webui/open-webui:cuda`           | 8080  | Browser‑friendly UI for chatting, API calls, and metrics |
| `postgres` | `pgvector/pgvector:pg17`                        | 5432  | Persistent data store for OpenWeb UI (conversation history, users, etc.) |

The compose file mounts a Docker volume for PostgreSQL data (`ai_database`) so your data survives container restarts.

---

## 📜 License

MIT © Mhorbid.  
See the [LICENSE](LICENSE) file for details.

---

Happy deploying! 🚀