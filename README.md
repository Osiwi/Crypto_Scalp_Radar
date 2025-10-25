# Crypto Scalp Radar

Crypto Scalp Radar is a live scanner that watches multiple centralized exchanges (Binance, Bybit, OKX, KuCoin, Kraken, etc.) and scores trading pairs for short-term scalping quality.

## What it does
- Pulls recent OHLCV candles and ticker data (price, bid/ask, volume) via `ccxt`.
- Calculates:
  - Realized volatility (RV%)
  - ATR% (range vs price)
  - Choppiness (is it trending or just noise?)
  - Bid/ask spread %
  - 24h quote volume (liquidity)
- Ranks markets with a `ScalpScore` so you can instantly see which pairs are both active and liquid right now.
- Prints a clean table of the top candidates, and can optionally save the results to CSV/JSON.

## How to run
```bash
python scalp_radar.py \
  --timeframe 5m \
  --hours 24 \
  --min-quote-vol 3000000 \
  --top 25
