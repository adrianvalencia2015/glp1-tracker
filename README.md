# Vital · GLP-1 Tracker

A private, browser-based GLP-1 injection, weight, and peptide tracker. No server, no accounts, no ads. All data lives in your browser's localStorage.

## Features

- **Dashboard** — Next shot countdown, active drug level ring, weight snapshot
- **Drug Level Forecast** — Clinically accurate PK model (first-order absorption/elimination)
- **Shot Log** — Dose, injection site rotation, mood, optional weight
- **Weight Tracker** — Trend chart, goal progress, projected goal date
- **Peptides** — Three subtabs (Today · Levels · History): log any peptide on any day with date/time backdating, see per-peptide drug-level curves, and track weekly adherence
- **Water** — Daily intake with a configurable oz goal and quick-add buttons
- **Settings** — Export/import JSON backup, theme switcher (Cream / Graphite)
- **PWA** — Add to Home Screen on iPhone/Android for a native app feel

## Supported GLP-1 Medications

| Medication | Half-life | Tmax | Source |
|---|---|---|---|
| Tirzepatide | 5 days | 48 hr | FDA Mounjaro label |
| Semaglutide | 7 days | 48 hr | FDA Ozempic/Wegovy label |
| Retatrutide | 6 days | 48 hr | NEJM Phase 2 trial |
| Liraglutide | 13 hours | 12 hr | FDA Victoza label |

## Peptide Protocol

Four peptides are tracked. Doses are entered in syringe units and converted using each vial's real parameters (vial mg, BAC water mL, 100-unit syringe), so the mg/mcg shown is label-accurate. Each peptide has its own pharmacokinetics, so the Levels tab auto-scales — fast-clearing peptides show an hours-scale curve, while the longer-acting IGF-1 LR3 shows a multi-day curve that reflects accumulation.

| Peptide | Conversion | Default Dose | Schedule | Half-life |
|---|---|---|---|---|
| Tesamorelin | 10 units = 1 mg | 10 units | 5x/week · Night fasted | ~30 min |
| IGF-1 LR3 | 7.5 units = 25 mcg · 15 units = 50 mcg | 7.5 units | 5x/week · Around workout | ~20–30 hr |
| CJC-1295 / Ipamorelin (no-DAC) | 6 units = 200 mcg · 9 units = 300 mcg | 6 units | 5x/week · AM or PM fasted | ~30 min / ~2 hr |
| MOTS-C | 10 units = 2 mg · 25 units = 5 mg | 10 units | 3x/week · Morning fasted | ~1–2 hr |

Adherence is frequency-based (e.g. 5×/week), so doses can be logged on any day rather than fixed weekdays. For the short-acting peptides, the molecule clears within a few hours — the therapeutic effect (GH pulse, AMPK signaling) outlasts what the curve shows.

Peptide protocol parameters are defined in code (`DEFAULT_PEPTIDES`), so corrections propagate automatically; only your logs are persisted. Peptide logs are stored under `vital_peptides_v2` in localStorage, with automatic migration from the earlier `vital_peptides_v1` format.

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

This is not a medical device. Drug and peptide level values are estimates based on published pharmacokinetic data, not clinical measurements. Always consult your prescribing physician regarding dose changes or side effects.

---

Built by Adrian Valencia · June 2026
