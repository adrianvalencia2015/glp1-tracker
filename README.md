# Vital · GLP-1 Tracker

A private, browser-based GLP-1 injection, weight, and peptide tracker. No server, no accounts, no ads. All data lives in your browser's localStorage.

## Features

- **Dashboard** — Next shot countdown, active drug level ring, weight snapshot
- **Drug Level Forecast** — Clinically accurate PK model (first-order absorption/elimination)
- **Shot Log** — Dose, injection site rotation, mood, optional weight
- **Weight Tracker** — Trend chart, goal progress, projected goal date
- **Peptides** — Protocol tracker for short-acting peptides (Nuform); daily check-off, dose logging, injection site, timing, and weekly adherence grid
- **Settings** — Export/import JSON backup, theme switcher (Cream / Graphite)
- **PWA** — Add to Home Screen on iPhone/Android for a native app feel

## Supported GLP-1 Medications

| Medication | Half-life | Tmax | Source |
|---|---|---|---|
| Tirzepatide | 5 days | 48 hr | FDA Mounjaro label |
| Semaglutide | 7 days | 48 hr | FDA Ozempic/Wegovy label |
| Retatrutide | 6 days | 48 hr | NEJM Phase 2 trial |
| Liraglutide | 13 hours | 12 hr | FDA Victoza label |

## Peptide Protocol (Nuform)

| Peptide | Conversion | Default Dose | Schedule |
|---|---|---|---|
| Tesamorelin | 10 units = 1 mg | 10 units | 5x/week · Night fasted |
| IGF-1 LR3 | 7.5 units = 25 mcg · 15 units = 50 mcg | 7.5 units | 5x/week · Pre or post workout |
| CJC-1295 / Ipamorelin | 6 units = 200 mcg · 9 units = 300 mcg | 6 units | 5x/week · Morning or night fasted |

Peptide data is stored separately under `vital_peptides_v1` in localStorage.

## Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages → Source: GitHub Actions**
3. Push to `main` — the workflow deploys automatically
4. Your app will be live at `https://YOUR-USERNAME.github.io/glp1-tracker`

## Add to iPhone Home Screen

1. Open the app URL in Safari
2. Tap the **Share** button (square with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add**

The app will launch full-screen, like a native app.

## Tech Stack

- React 18 (via CDN, no build step)
- Babel Standalone (JSX in browser)
- PWA Service Worker (offline support)
- localStorage (all data private, device-local)

## Disclaimer

This is not a medical device. Drug level values are estimates based on population pharmacokinetic data. Always consult your prescribing physician regarding dose changes or side effects.

---

Built by Adrian Valencia · June 2026
