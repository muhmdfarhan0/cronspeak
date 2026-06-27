# CronSpeak — Natural Language to Cron Expression Converter

> **Convert plain English schedules to production-ready cron expressions — instantly.**  
> Powered by LLaMA 3.3 70B via Groq AI. No backend. No install. Runs entirely in the browser.

🔗 **Live Demo → [muhmdfarhan0.github.io/cronspeak](https://muhmdfarhan0.github.io/cronspeak/)**

---

## What is CronSpeak?

CronSpeak is a free, open-source tool that turns natural language into cron expressions for every major platform. Type *"every weekday at 9am"* and instantly get the correct syntax for Linux crontab, GitHub Actions, AWS EventBridge, Kubernetes CronJob, and Vercel Cron — with next-run previews and platform-specific warnings.

It also works in reverse: paste any cron expression and get a plain-English explanation.

---

## Features

- **Natural Language → Cron** — describe any schedule in plain English
- **Cron → English** — decode any existing cron expression
- **5 platforms at once** — Linux/crontab, GitHub Actions, AWS EventBridge, Kubernetes, Vercel
- **Next-run preview** — see the next 5 scheduled run times
- **Platform warnings** — timezone gotchas, syntax quirks, throttle limits
- **One-click copy** — copy any expression to clipboard instantly
- **Privacy-first** — API key stored only in `localStorage`, never on any server
- **Zero dependencies** — single HTML file, no npm, no build step, works offline after first load

---

## Live Demo

**[https://muhmdfarhan0.github.io/cronspeak/](https://muhmdfarhan0.github.io/cronspeak/)**

---

## Screenshots

### English → Cron
Type a schedule in plain English and get cron expressions for all platforms:

```
Input:  "every weekday at 9am"

Linux:            0 9 * * 1-5
GitHub Actions:   0 9 * * 1-5
AWS EventBridge:  0 9 ? * MON-FRI *
Kubernetes:       0 9 * * 1-5
Vercel:           0 9 * * 1-5
```

### Cron → English
Paste a cron expression and get a human-readable explanation:

```
Input:  */15 * * * *

Output: Runs every 15 minutes, at :00, :15, :30, and :45 past every hour.
```

---

## Quick Start

### Option 1 — Use the live site
Go to **[muhmdfarhan0.github.io/cronspeak](https://muhmdfarhan0.github.io/cronspeak/)**, enter your free Groq API key, and start converting.

### Option 2 — Run locally
No install needed. Clone and open:

```bash
git clone https://github.com/muhmdfarhan0/cronspeak.git
cd cronspeak
open index.html        # macOS
start index.html       # Windows
xdg-open index.html   # Linux
```

---

## Getting a Free Groq API Key

CronSpeak uses the [Groq API](https://groq.com) for ultra-fast LLM inference. The free tier covers thousands of requests per day — more than enough for personal use.

1. Go to **[console.groq.com](https://console.groq.com)** and create a free account
2. Navigate to **API Keys** → **Create API Key**
3. Copy the key (starts with `gsk_...`)
4. Paste it into CronSpeak and click **Save**

Your key is stored only in your browser's `localStorage`. It is never sent to any server except Groq's own API.

---

## Supported Platforms

| Platform | Notes |
|---|---|
| 🐧 **Linux / Crontab** | Standard 5-field cron syntax |
| ⚙️ **GitHub Actions** | Uses UTC; supports `on.schedule` |
| ☁️ **AWS EventBridge** | Requires 6-field syntax with year; `?` for day-of-week/month conflict |
| 🎯 **Kubernetes CronJob** | Standard cron, runs in cluster timezone |
| ▲ **Vercel Cron** | Free tier minimum interval: 1 hour |

---

## Deploy Your Own

### GitHub Pages (free, 3 steps)

```bash
# 1. Fork or clone this repo
git clone https://github.com/muhmdfarhan0/cronspeak.git
cd cronspeak

# 2. Push to your own GitHub repo
gh repo create my-cronspeak --public --push --source .

# 3. Enable GitHub Pages
# Go to: Settings → Pages → Branch: main → / (root) → Save
```

Your site will be live at `https://<your-username>.github.io/my-cronspeak/` within ~60 seconds.

### Any static host
Upload `index.html` to Netlify, Vercel, Cloudflare Pages, or any CDN — it's a single file with no dependencies.

---

## Tech Stack

| Layer | Choice |
|---|---|
| Frontend | Vanilla HTML5, CSS3, JavaScript (ES2020) |
| AI Model | LLaMA 3.3 70B Versatile via [Groq API](https://groq.com) |
| Fonts | Instrument Serif + Inter (Google Fonts) |
| Hosting | GitHub Pages |
| Storage | Browser `localStorage` (API key only) |

---

## Privacy & Security

- **No backend** — there is no server, database, or data collection
- **No tracking** — no analytics, no cookies, no fingerprinting
- **API key safety** — stored in `localStorage` under `cronspeak_groq_key`, only sent to `api.groq.com`
- **Open source** — audit the entire app in `index.html` (~500 lines)

---

## Common Cron Expression Reference

| Description | Linux/K8s | GitHub Actions | AWS EventBridge |
|---|---|---|---|
| Every minute | `* * * * *` | `* * * * *` | `* * * * ? *` |
| Every hour | `0 * * * *` | `0 * * * *` | `0 * * * ? *` |
| Daily at midnight | `0 0 * * *` | `0 0 * * *` | `0 0 * * ? *` |
| Every weekday at 9am | `0 9 * * 1-5` | `0 9 * * 1-5` | `0 9 ? * MON-FRI *` |
| Every Sunday at noon | `0 12 * * 0` | `0 12 * * 0` | `0 12 ? * SUN *` |
| Every 15 minutes | `*/15 * * * *` | `*/15 * * * *` | `0/15 * * * ? *` |
| First of month midnight | `0 0 1 * *` | `0 0 1 * *` | `0 0 1 * ? *` |

---

## Contributing

Issues and pull requests welcome. Since the entire app is a single `index.html`, contributions are straightforward — edit the file and open a PR.

---

## License

MIT — free to use, modify, and distribute.

---

*Built with [Groq AI](https://groq.com) · [Live Demo](https://muhmdfarhan0.github.io/cronspeak/) · [Report an Issue](https://github.com/muhmdfarhan0/cronspeak/issues)*
