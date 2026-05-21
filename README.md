# 🌿 NourishTrack

A lightweight, privacy-first nutrition and habit tracking Progressive Web App (PWA) — installable on any phone, works fully offline, no account required.

---

## Features

- **Daily Food & Drink Logging** — log meals by type (Breakfast, Lunch, Dinner, Snack) with calories, macros, and optional photos
- **Calorie Ring** — visual daily progress tracker with macro breakdown (protein, carbs, fat)
- **Water Intake Tracker** — tap-to-fill glass tracker with customizable daily goal
- **AI Nutrition Analysis** — get instant Claude-powered feedback on your daily meals
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
- Claude API (`claude-sonnet-4-20250514`) for AI nutrition analysis and reports
- LocalStorage for all data persistence

---

## Getting Started

### Option 1 — Netlify Drop (Recommended, 2 minutes)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop this entire folder onto the page
3. Copy the generated `https://` URL
4. Open it on your phone in Safari (iPhone) or Chrome (Android)
5. Tap **Share → Add to Home Screen** (iPhone) or **Menu → Install App** (Android)

Done — it's now a full PWA on your phone, works offline.

### Option 2 — GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages → Source → main branch / root**
3. GitHub will publish it at `https://yourusername.github.io/repo-name`
4. Open that URL on your phone and install as above

### Option 3 — Local Server (same WiFi only)

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

Open `http://your-computer-ip:8080` on your phone (both must be on the same WiFi). Install as PWA, then you can stop the server — the service worker keeps it running offline.

---

## File Structure

```
├── index.html      # Entire app — UI, logic, styles
├── sw.js           # Service worker for offline caching
├── manifest.json   # PWA manifest (name, icon, display mode)
└── README.md
```

---

## Installing on Your Phone

| Platform | Browser | Steps |
|----------|---------|-------|
| iPhone | Safari (required) | Share → Add to Home Screen |
| Android | Chrome | Menu (⋮) → Install App |

> ⚠️ Must be served over **HTTPS** for PWA install to work. A plain `file://` or `http://` link will only create a browser shortcut.

---

## Privacy

All data (food logs, body metrics, settings) is stored in your browser's `localStorage` — it never leaves your device. The only external call is to the Anthropic API when you request an AI analysis.

---

## License

MIT