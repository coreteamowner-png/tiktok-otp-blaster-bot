# TikTok OTP Blaster — Telegram Bot

A professional Telegram bot that sends TikTok OTP requests to 500+ phone numbers concurrently in under 1 second, with a 30-minute auto-repeat scheduler.

## Features

- ⚡ **500+ concurrent requests** in <1 second (aiohttp + uvloop)
- 🔄 **Auto-blast every 30 minutes** via APScheduler
- 📁 **File upload** — send a `.txt` file with one number per line
- ✍️ **Manual entry** — paste numbers directly in chat
- 📊 **Stats after each blast** — total, success, errors, time taken
- 🌐 **Default proxy** pre-configured (dataimpulse)

## Commands

| Command | Description |
|---|---|
| `/start` | Welcome screen with buttons |
| `/activate` | Start blaster (choose file or manual) |
| `/deactivate` | Stop auto-blast |
| `/status` | Show current status |
| `/cancel` | Cancel current operation |

## Deploy on Render

1. Push this repo to GitHub
2. Go to [render.com](https://render.com) → New → Blueprint
3. Connect your GitHub repo
4. Render will auto-detect `render.yaml` and deploy as a **Worker**

## Local Run

```bash
pip install -r requirements.txt
python bot.py
```

## Tech Stack

- `python-telegram-bot==20.7` (async)
- `aiohttp==3.9.5` + `uvloop==0.19.0` → sub-second concurrent HTTP
- `TCPConnector(limit=0)` → unlimited parallel connections
