# OB Structure Fibonacci

Rule-based quantitative trading system implementing market structure, order blocks, Fibonacci retracement and systematic risk-management logic.

## Project Status

**Methodology stage.** The connected repository was empty. Known strategy rules are documented; no Pine Script indicator, MQL5 expert advisor, price dataset or reproducible backtest is included. No profitability, win rate or live execution result is claimed.

## Methodology

| Parameter | Known specification |
| --- | --- |
| Market | US100 / NAS100; exact broker instrument to be recorded |
| Timeframe | H1 |
| Swing pivots | `pivotLength = 1` |
| Entry zone | Fibonacci 66.66%–61.8% |
| Stop loss | Fibonacci 89.60% |
| Take profit | Fibonacci 0.0% |
| Fibonacci anchors | Order block to the latest corresponding high/low |
| Structure change | When the selected/taken order block breaks |
| Concurrent positions | Up to two when zones coincide |

These are supplied research rules, not executable instructions. [The methodology specification](methodology/README.md) records definitions that still need to be resolved, including order-block selection, pivot confirmation, anchor orientation, fill assumptions and aggregate risk.

## Repository Structure

`pine-script/` · `mql5/` · `methodology/` · `backtests/` · `results/` · `charts/`.

## Tech Stack

Planned implementation: Pine Script / TradingView and MQL5 / MetaTrader 5. Python may be used for data checks and analysis. No executable source or dependency configuration exists here yet.

## Usage

Read the methodology. There is currently no runnable indicator, expert advisor or backtest command. Add source code and instrument-specific reproducible settings before publishing implementation results.

## Limitations

Order-block and execution details are incomplete. Pivot detection must respect the information available at the signal time; using future confirmation retrospectively creates look-ahead bias. Spreads, slippage, fees, broker differences, overlapping exposure and sample selection can materially change outcomes. Research rules do not guarantee returns.
