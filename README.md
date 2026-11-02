# India Day Trader (PWA starter)

## What this version does
- Installable Android-style web app when hosted over HTTPS.
- Imports user-provided 5-minute OHLCV CSV data.
- Scans imported candles for a simple Opening Range Breakout rule.
- Calculates historical entry reference, stop, target and illustrative quantity.
- Exports scan results to CSV.
- Never labels imported/delayed data as a live BUY signal.
- No broker API, no order placement.

## CSV format
Required headers: `ticker,timestamp,open,high,low,close,volume`
Optional header: `exchange` (defaults to NSE).
Timestamp should be ISO-like, e.g. `2026-11-02T09:15:00+05:30`.
Use completed 5-minute candles. Data must be legally obtained from a source whose terms permit your use.

## Install on Android
1. Host the folder on an HTTPS static host (e.g. GitHub Pages).
2. Open the deployed URL in Chrome on Android.
3. Chrome menu (⋮) > Install app / Add to Home screen.
4. Launch from the new home-screen icon.

Opening `index.html` directly as a local file may work for basic CSV scanning, but PWA installation/offline caching requires HTTPS hosting or localhost.

## Important limitations
This is a working prototype, not a production trading system. It does not fetch exchange data. A CSV can be delayed, stale, incomplete, adjusted, or malformed. The ORB rule is illustrative and has not been validated for profitability. Quantity ignores costs, slippage, liquidity, circuit limits, lot sizes and capital availability. Verify every price against a broker/exchange-approved source before any decision.
