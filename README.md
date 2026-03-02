# 🌐 Open WebUI + Crazyrouter

> Deploy Open WebUI with 300+ AI models through Crazyrouter — One API key, 45% cheaper.

[Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community?ref=github) — AI API gateway for all major models.

## 💰 Price Comparison

| Model | Official Price | Crazyrouter | Savings |
|-------|---------------|-------------|---------|
| Claude Opus 4 | $15 / $75 | $8.25 / $41.25 | **45%** |
| GPT-4o | $2.50 / $10 | $1.38 / $5.50 | **45%** |
| Gemini 2.5 Pro | $1.25 / $10 | $0.69 / $5.50 | **45%** |

## ⚡ Quick Start with Docker

```bash
docker run -d \
  --name open-webui \
  -p 3000:8080 \
  -e OPENAI_API_BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1 \
  -e OPENAI_API_KEY=sk-your-crazyrouter-key \
  -v open-webui:/app/backend/data \
  ghcr.io/open-webui/open-webui:main
```

Then visit `http://localhost:3000`.

## 🐳 Docker Compose

```yaml
version: '3.8'
services:
  open-webui:
    image: ghcr.io/open-webui/open-webui:main
    ports:
      - "3000:8080"
    environment:
      - OPENAI_API_BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1
      - OPENAI_API_KEY=sk-your-crazyrouter-key
    volumes:
      - open-webui-data:/app/backend/data
    restart: unless-stopped

volumes:
  open-webui-data:
```

```bash
docker compose up -d
```

## ⚙️ Configuration

### Add Models in UI
1. Go to **Admin** → **Settings** → **Connections**
2. OpenAI API is pre-configured via environment variables
3. Models auto-populate from Crazyrouter

### Environment Variables

| Variable | Value | Description |
|----------|-------|-------------|
| `OPENAI_API_BASE_URL` | `https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1` | Crazyrouter endpoint |
| `OPENAI_API_KEY` | `sk-your-key` | Your Crazyrouter key |

## ❓ FAQ

**Q: Models not showing up?**
A: Check API key is valid. Go to Admin → Connections and click refresh.

**Q: Can I use Claude models?**
A: Yes! Crazyrouter provides Claude, GPT, Gemini, and 300+ models through one API.

**Q: How to update?**
A: `docker pull ghcr.io/open-webui/open-webui:main && docker compose up -d`

## 🔗 Links
- 🌐 [Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community?ref=github) | 🌐 [Open WebUI](https://github.com/open-webui/open-webui) | 💬 [Telegram](https://t.me/crzrouter)

## 📄 License
MIT
