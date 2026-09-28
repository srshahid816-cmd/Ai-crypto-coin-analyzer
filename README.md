# Crypto Multi-Factor Scanner

This project intentionally keeps the application in **one Python file** (`app.py`) and all Python dependencies in **one `requirements.txt`**.

## Run
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Data architecture
- Binance public Spot market data is tried first.
- `data-api.binance.vision` and Binance API mirrors are used to reduce HTTP 451 deployment failures.
- Bybit public Spot/Linear data is used as a fallback when Binance is inaccessible from the deployment region.
- CoinGecko tokenomics is optional; missing data is shown as unavailable rather than fabricated.
- Google News RSS is used for headline context.

No private API keys are required for the Binance/Bybit public market-data paths. A CoinGecko Demo API key can optionally be supplied as `COINGECKO_API_KEY`.
