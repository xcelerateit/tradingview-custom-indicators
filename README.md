# TradingView Custom Indicators

Public Pine Script® indicators you can copy into [TradingView](https://www.tradingview.com/) and use on your charts. Each script is a single `.pine` file in this repository.

## How to use

1. Open [TradingView](https://www.tradingview.com/) → **Pine Editor** (bottom panel).
2. Open the `.pine` file from this repo and copy its full contents into the editor (or paste from GitHub’s raw view).
3. Click **Save** / **Add to chart**.

Requirements are noted per script; all scripts here target **Pine Script v6** unless stated otherwise.

## Indicators

### `volusd.pine` — VolumeUSD

**What it does:** Plots **volume expressed in quote currency (USD terms)** as `volume × close`, as a histogram. That matches dollar/notional volume when price is in USD (e.g. many crypto and FX pairs).

**Extras:**

- Two **EMAs** of that USD volume (defaults: 60 and 240) with a **semi-transparent fill** between them — blue when the faster EMA is above the slower one, pink (`#e91e63`) otherwise.
- **Outlier detection:** Compares current USD volume to a smoothed baseline (**NAMA** — custom adaptive MA with φ-related smoothing) over a configurable length. When volume is at or above **baseline × multiplier**, the bar is treated as an outlier: **thicker black bar**, optional **highlighter** ring (default yellow, width/color/toggle configurable).
- **Outlier threshold** shown as a grey reference line on the pane.

**Main settings:**

| Input | Default | Role |
| --- | --- | --- |
| EMA 1 length | 60 | Faster EMA of USD volume |
| EMA 2 length | 240 | Slower EMA of USD volume |
| MA length (outlier baseline) | 60 | Length for baseline smoothing |
| Outlier threshold multiplier | 5.0 | Bar is outlier when USD volume ≥ baseline × this |
| Show outlier highlight | On | Toggle the colored halo behind outlier bars |
| Outlier highlight color | Yellow (semi-transparent) | Highlighter color (any color/opacity in the picker) |

**License:** This script is published under the **Mozilla Public License 2.0** (see file header in `volusd.pine`).

---

More indicators will be listed here as they are added.

## Contributing / Copying

You may use these scripts on TradingView and share them; respect the license in each file. If you fork or republish, keep license and attribution as required by that license.
