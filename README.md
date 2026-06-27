# CronSpeak

**AI-powered Natural Language → Cron Expression converter.**  
Describe your schedule in plain English, get production-ready cron expressions for Linux, GitHub Actions, AWS EventBridge, Kubernetes, and Vercel — instantly.

Live at: `https://<your-username>.github.io/cronspeak/`

---

## What it does

- **English → Cron** — type "every weekday at 9am", get `0 9 * * 1-5` for all five platforms
- **Cron → English** — paste `*/15 * * * *`, get a plain-English explanation + next 5 run times
- Platform-specific expressions (AWS EventBridge needs a year field; Vercel has throttle limits)
- Warnings for timezone gotchas and platform quirks
- Copy-to-clipboard on every result card
- No backend, no tracking, no cookies — your API key never leaves your browser

Powered by **LLaMA 3.3 70B** via [Groq](https://groq.com) for near-instant inference.

---

## Step 1 — Get a free Groq API key

1. Go to **[console.groq.com](https://console.groq.com)** and sign up (free, no credit card)
2. Click **API Keys** in the left sidebar → **Create API Key**
3. Copy the key (it starts with `gsk_...`)

The free tier gives you ~14,400 requests/day on LLaMA 3.3 70B — more than enough for personal use.

---

## Step 2 — Run it locally

No install required. Just open the file:

```
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or drag `index.html` into any browser.

---

## Step 3 — Deploy to GitHub Pages (3 steps)

1. **Create a new GitHub repository** (e.g. `cronspeak`) and push `index.html` to the `main` branch:

   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/cronspeak.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**: go to your repo → **Settings** → **Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → **Save**

3. **Visit your site** at `https://<your-username>.github.io/cronspeak/` — live in ~60 seconds.

---

## Files

```
index.html   ← the entire app (HTML + CSS + JS, single file)
README.md    ← this file
```

No `node_modules`, no build step, no framework. Open and it works.

---

## Tech

| Layer     | Choice                                      |
|-----------|---------------------------------------------|
| Frontend  | Vanilla HTML, CSS, JavaScript               |
| AI Model  | LLaMA 3.3 70B Versatile via Groq API        |
| Fonts     | Instrument Serif + Inter (Google Fonts)     |
| Hosting   | GitHub Pages (any static host works)        |
| Storage   | `localStorage` for API key only             |

---

## Privacy

- Your Groq API key is stored in `localStorage` under the key `cronspeak_groq_key`
- The only outbound requests are to `api.groq.com` and `fonts.googleapis.com`
- No analytics, no telemetry, no cookies

---

## License

MIT — do whatever you want with it.
