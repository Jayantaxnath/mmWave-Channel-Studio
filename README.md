# mmWave Channel Studio

[![Deploy to GitHub Pages](https://github.com/Jayantaxnath/mmWave-Channel-Studio/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/Jayantaxnath/mmWave-Channel-Studio/actions/workflows/deploy-pages.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A lightweight, dependency-free statistical spatial channel simulator for mmWave and sub-THz wireless links, inspired by [NYUSIM](https://wireless.engineering.nyu.edu/nyusim/)-style methodology. Runs entirely in your browser as a single HTML file — no build step, no server, no install.

**Live demo:** [jayantaxnath.github.io/mmWave-Channel-Studio](https://jayantaxnath.github.io/mmWave-Channel-Studio/)

## What it does

- **Statistical spatial channel model (SSCM)** in the spirit of NYUSIM and 3GPP-style modeling: Close-In (CI) or Alpha-Beta-Gamma (ABG) path loss, Poisson-distributed time clusters and subpaths with exponential power decay, and subpaths grouped into angular "spatial lobes" for azimuth angle-of-arrival / angle-of-departure.
- **Scenarios:** Urban Microcell (UMi), Urban Macrocell (UMa), Indoor Hotspot (InH), with LOS/NLOS drawn from a distance-based probability model or forced manually.
- **Tunable link parameters:** frequency (0.5–150 GHz), T-R separation distance, TX/RX height, path loss model, and a reproducible random seed.
- **Live outputs:**
  - Path loss vs. distance
  - Power delay profile (PDP)
  - Complex channel impulse response (CIR) taps
  - Azimuth angular spectrum (AoA/AoD polar plot)
  - RMS delay spread, RMS angular spread, Rician K-factor, cluster/subpath counts
- **Export:** download any chart as a PNG, or the full parameter set and per-subpath data as JSON.
- **AI explain:** an optional "Explain this channel" button sends your current results to Google's Gemini API for a plain-language readout, using your own free API key (stored only in your browser).
- **Light / Dark / System theme**, fully responsive down to phone width.

## Using it

Visit the [live demo](https://jayantaxnath.github.io/mmWave-Channel-Studio/) — nothing to install. Set your scenario, frequency, and distance on the left, and the path loss, power delay profile, CIR, and angular spectrum charts update instantly. Use the small download icon on any chart to save it as a PNG, or "Download params (.json)" to export the full simulation data.

To use the AI explanation feature:

1. Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey).
2. Click **API key settings** in the app and paste your key.
3. Click **Explain this channel** after running a simulation.

Your key is stored only in your own browser's local storage and sent directly from your browser to Google's API — it never passes through any other server.

## Running it locally

```bash
git clone https://github.com/Jayantaxnath/mmWave-Channel-Studio.git
cd mmWave-Channel-Studio
```

Then just open `index.html` in your browser. No dependencies, no build step.

## What this is (and isn't)

This is an educational and prototyping tool. The underlying methodology — CI/ABG path loss, Poisson cluster and subpath generation, spatial-lobe angular modeling — follows the general approach used by NYUSIM and 3GPP-style statistical spatial channel models. The specific parameter values (path loss exponents, cluster statistics, angular spreads, shadow fading), however, are **illustrative defaults chosen to be physically plausible, not NYU WIRELESS's calibrated measurement tables**. Treat its outputs as approximations for learning and prototyping, not a substitute for NYUSIM or real measurement campaigns. This project is not affiliated with, endorsed by, or derived from NYU WIRELESS or the NYUSIM software.

## License

[MIT](LICENSE) — free to use, modify, and redistribute.

## Contributing

Issues and pull requests are welcome. This is a single self-contained `index.html` file with no build tooling — most changes will touch it directly. Please keep it dependency-free.
