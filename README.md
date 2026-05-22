## Aaron Peabody

**Applied analytics · intelligent systems · probabilistic decision automation**

I design and operate production decision systems — the kind that ingest noisy real-world data, turn it into well-calibrated probabilities, and act on them under risk controls. End-to-end ownership from data ingestion through automated action and post-hoc P&L attribution.

---

### Current focus — GEO · Kalshi Weather Bot

Live algorithmic trading system on Kalshi's CFTC-regulated daily-high-temperature prediction markets across 20 US cities. Real money, maker-only execution, behind a 15-minute Telegram approval gate.

- **Six-model probabilistic ensemble** — NBM, GFS, ECMWF 51-member, HRRR, NWS gridded, MOS
- **Per-(model × station) EMOS calibration** — Platt scaling fit on a 152K-row two-year backtest; +26.7% Brier reduction on holdout
- **Quarter-Kelly sizing** — disagreement-weighted multiplier, soft-drawdown derisking, asymmetric edge gates, 50¢ side-cost floor derived from P&L attribution
- **Maker-only execution** — limits at `ceil(ask × 100) − 1` for 0% fees; single-instance `fcntl` lock; fill-watch re-quoting
- **Backtest-gated promotion** — every production change validated against historical data before it goes live

→ Source: [`GEO-The-Kalshi-Weather-Bot-DEMO`](https://github.com/apeabody007/GEO-The-Kalshi-Weather-Bot-DEMO)
→ Live demo: [apeabody007.github.io/GEO-The-Kalshi-Weather-Bot-DEMO](https://apeabody007.github.io/GEO-The-Kalshi-Weather-Bot-DEMO/)

---

### Stack

Python 3.11 · SQLite · NumPy / SciPy · REST APIs (incl. RSA-PSS authenticated trading endpoints) · launchd · pytest + AST-based invariant tests · Playwright

Data feeds: NOAA GHCND · NWS api.weather.gov · Open-Meteo (ECMWF / GFS / HRRR / NBM) · METAR · NWS Climate Reports · NWS MOS

---

### Operating principles

- **Backtest before promote.** Every change to filters, sizing, or model weights gets validated on historical data before it touches live capital.
- **Brier improvement ≠ trustworthy calibration.** Always audit the shape of a fitted curve, not just its score.
- **The crowd is usually right at extremes.** 1¢ and 99¢ markets carry real information; encode the skepticism as a hard veto, not a soft filter.
- **Encode expensive lessons into filters or tests.** Memory is lossy; AST-pinned invariants and dated investigation memos aren't.

---

### Background

BA Economics — University of Wisconsin–Madison
BS Psychology — University of Central Florida

I think in systems, behavior, and incentives. Equally comfortable with the mechanics of an ensemble forecaster and the second-order effects of how a system's design changes the behavior of the people who interact with it.

---

### Contact

[apeabody@uwalumni.com](mailto:apeabody@uwalumni.com) · [LinkedIn](https://www.linkedin.com/in/aaronpeabody7/)
