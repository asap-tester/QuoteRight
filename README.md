# QuoteRight
> Stop quoting from gut. Quote from data.

## The Problem
Freelancers consistently undercharge — not from lack of confidence, but from lack of calibration data. Every new quote is an optimistic guess. There is no tool that uses your own project history to tell you what to charge next.

## Who It's For
- Freelancer who has done 5+ projects and still sets rates by feel
- Independent consultant underselling because they underestimate hours
- CA in practice quoting engagements without historical benchmarks

## What It Does
- Logs your project history (estimated hours, actual hours, amount earned)
- Computes your real hourly rate and personal optimism bias automatically
- Generates a calibrated quote range for your next project, adjusted for how you actually work

## How to Use
1. Download `index.html` or copy the raw file
2. Open in any browser — no install, no login, no internet required after first load
3. Log 3+ past projects → quote generator becomes fully calibrated to your history

## Deploy to GitHub Pages
1. Create a new GitHub repo (e.g. `quoteright`)
2. Upload `index.html` as the only file to the `main` branch
3. Go to Settings → Pages → Source: `main` branch → `/root`
4. Your app is live at `https://[username].github.io/quoteright`

## Wrap for Play Store (WebView)
1. Use [PWABuilder](https://www.pwabuilder.com) — paste your GitHub Pages URL
2. Generate the Android APK package
3. Submit to Play Store via Google Play Console
4. Zero code required — WebView wrapper handles everything

## Tech
- Vanilla HTML/CSS/JS — zero dependencies
- Google Fonts CDN (Playfair Display + IBM Plex Sans)
- localStorage for full persistence
- Fully offline after first load

## Calibration Logic
| Input | Computation |
|---|---|
| Actual hourly rate | Total earned ÷ total actual hours |
| Optimism bias | Avg of ((actual − estimated) / estimated × 100) |
| Per-type rate | Earned ÷ actual hours, grouped by project type |
| Corrected hours | Estimated × (1 + bias%) when 3+ projects logged |
| Quote range | Base × 0.9 (floor) / Base / Base × 1.2 (ceiling) |

## Roadmap
- [ ] Project type benchmarking against market rates
- [ ] Quote PDF export
- [ ] CSV import from past invoices

## License
MIT — use freely, no attribution required.
