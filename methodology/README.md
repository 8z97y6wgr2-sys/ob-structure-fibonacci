# Research methodology

Status: known-rule specification; implementation decisions pending.

Use US100 / NAS100 H1 bars and swing pivots with `pivotLength = 1`. Anchor the Fibonacci measurement from the selected order block to the latest corresponding high/low; the supplied entry band is 66.66%–61.8%, stop level is 89.60%, and target is 0.0%. Treat a break of the selected/taken block as a structure change. At most two concurrent positions may exist when zones coincide.

## Definitions to resolve before coding

1. Exact bullish/bearish order-block selection and invalidation rules: wick versus body, close versus intrabar break, and which block takes precedence.
2. The directional meaning of 0% and 100% anchors, precise entry price inside the band, and how overlapping zones are classified.
3. Pivot confirmation time. A one-bar right confirmation cannot be known until that later bar closes.
4. Pending order expiry, partial fills, SL/TP collision handling, gaps and anchor updates after signal generation.
5. Per-position risk, total risk when two positions coincide, sizing, margin and broker contract specifications.

## Backtest protocol

Record data provenance, timezone, sessions, contract specification, code version and test period. Freeze decisions before evaluation; separate development from out-of-sample periods. Include spread, commissions, slippage and realistic fill ordering. Report trade count, drawdown, exposure, net returns and sensitivity only after an actual run with auditable outputs. No backtest has been performed in this repository.
