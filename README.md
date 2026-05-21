# 🌿 NourishTrack

A lightweight, privacy-first nutrition and habit tracking Progressive Web App (PWA) — installable on any phone, works fully offline, no account required.

---

## Features

- **Daily Food & Drink Logging** — log meals by type (Breakfast, Lunch, Dinner, Snack) with calories, macros, and optional photos
- **Calorie Ring** — visual daily progress tracker with macro breakdown (protein, carbs, fat)
- **Water Intake Tracker** — tap-to-fill glass tracker with customizable daily goal
- **AI Nutrition Analysis** — powered by Google Gemini 1.5 Flash (free, no credit card needed)
- **Body Metrics** — log weight and waist measurements weekly or bi-weekly with a live trend chart
- **Weekly & Monthly Reports** — summary tables, AI-generated nutritionist reports, and CSV export
- **Streak Counter** — tracks consecutive days logged to keep you motivated
- **Customizable Goals** — set your own calorie, macro, water, and body targets
- **Offline-ready** — service worker caches the app; works without internet after first load
- **No backend, no account** — all data stored locally on your device

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript — zero dependencies, zero build step
- PWA (Web App Manifest + Service Worker) for installability and offline support
- Google Gemini 1.5 Flash API for AI nutrition analysis and reports (free tier)
- LocalStorage for all data persistence
- Fonts: Playfair Display + Plus Jakarta Sans

---

## AI Setup (Free)

NourishTrack uses **Google Gemini 1.5 Flash** for nutrition analysis — completely free, no credit card required.

1. Go to **[aistudio.google.com](https://aistudio.google.com)**
2. Sign in with your Google account
3. Click **Get API Key** → **Create API key**
4. Copy the key (starts with `AIza...`)
5. Open the app → **Settings → AI Features** → paste your key

Free tier limits: **1,500 requests/day** and **15 per minute** — more than enough for daily use.

---

## Getting Started

### Option 1 — GitHub Pages (Recommended)

1. Fork or clone this repo
2. Go to **Settings → Pages → Source → main branch / root**
3. GitHub publishes it at `https://yourusername.github.io/nourishtrack-pwa`
4. Open that URL on your phone and install as a PWA

### Option 2 — Netlify Drop (2 minutes, no account needed)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop this entire folder onto the page
3. Copy the generated `https://` URL
4. Open on your phone and install

### Option 3 — Local Server (same WiFi only)

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

Open `http://your-computer-ip:8080` on your phone (both must be on same WiFi). Install as PWA, then stop the server — the service worker keeps it running offline.

---

## Installing on Your Phone

| Platform | Browser | Steps |
|----------|---------|-------|
| iPhone | Safari (required) | Share → Add to Home Screen |
| Android | Chrome | Menu (⋮) → Install App |

> ⚠️ Must be served over **HTTPS** for PWA install to work. A `file://` or plain `http://` link only creates a browser shortcut, not a real installed PWA.

---

## File Structure

```
├── index.html        # Entire app — UI, logic, styles
├── sw.js             # Service worker for offline caching
├── manifest.json     # PWA manifest (name, icons, display mode)
├── favicon.ico       # Browser favicon
├── icon-16.png       # Favicon small
├── icon-32.png       # Favicon standard
├── icon-180.png      # Apple touch icon
├── icon-192.png      # PWA icon (Android)
├── icon-512.png      # PWA icon (splash screen)
└── README.md
```

---

## Privacy

All data (food logs, body metrics, settings, API key) is stored in your browser's `localStorage` — it never leaves your device. The only external call is to the Google Gemini API when you request an AI analysis, and only the nutrition data you've logged that day is sent.

---

## Live App

🔗 [nlagdhir.github.io/nourishtrack-pwa](https://nlagdhir.github.io/nourishtrack-pwa)

---

## License

MIT