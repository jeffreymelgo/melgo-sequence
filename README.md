# Melgo Sequence — Price Structure Classifier

**Original work by Jeff Rey Melgo | @JeffMelgo on TradingView** 
**Research: https://ssrn.com/abstract=6658238**
Independent Researcher and System Developer | Cebu, Philippines

---

## What This Is

The Melgo Sequence is a price structure classification engine built on the 
behavioral properties of three derived candle values:

| Level | Formula | Name |
|-------|---------|------|
| HL2 | (High + Low) / 2 | Neutral Anchor (NA) |
| HLC3 | (High + Low + Close) / 3 | Structural Core (SC) |
| OHLC4 | (Open + High + Low + Close) / 4 | FakeOut Threshold (FOT) |

Their relative ordering produces six mutually exclusive structural states:

| Code | State | Sequence |
|------|-------|----------|
| T | Bull Trend | SC > NA > FOT |
| B | Bear Trend | FOT > NA > SC |
| R | Bull Rejection | SC > FOT > NA |
| I | Bear Indecision | NA > SC > FOT |
| D | Distribution | FOT > SC > NA |
| A | Accumulation | NA > FOT > SC |

The classifier identifies **market condition type before signaling direction** — 
addressing one of the most consistent failure patterns in retail trading: 
entering with correct direction bias in structurally unreadable conditions.

---

## What Is Published Here

This repository contains the **public classifier release** — the conceptual 
core of the system:

- Four-timeframe state classification (Macro, Bias, Micro, Context)
- On-chart state labels with streak and spread conviction
- Dashboard showing all four timeframe states simultaneously

Sweep signals, breakout signals, zone levels, and the full entry/exit system 
are part of the proprietary implementation and are not included here.

---

## Research Basis

The Melgo Sequence has been validated across eight phases of structured 
backtesting covering four instruments — BTCUSDT, SPY, EURUSD, and NASDAQ — 
with 18,904 valid candles tested under controlled confluence conditions. 
All directional findings are tested with two-sided binomial tests and 
Bonferroni correction for multiple comparisons.

A formal research paper has been submitted to 
**Technical Analysis of Stocks & Commodities** magazine for consideration.

---

## How to Use

1. Open TradingView
2. Open Pine Editor (bottom of screen)
3. Paste the contents of `melgo_sequence.pine`
4. Click **Add to chart**

Recommended default timeframe stack: **4H / 1H / 15m / 1D**

---

## License

Published under the **Mozilla Public License 2.0**.  
Personal use only. Commercial use, white-labeling, or inclusion in paid 
products requires explicit written authorization from the author.

Contact: @JeffMelgo on TradingView

---

*The Melgo Sequence classification system — including the NA / SC / FOT naming 
convention, the six-state sequence logic, and the signal framework built upon 
it — is the original, independent intellectual work of Jeff Rey Melgo, 
developed outside of any employment relationship and not derived from any 
third-party system.*
