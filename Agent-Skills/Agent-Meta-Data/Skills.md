# 🚀 pCLAW AI Meta Data API

**pCLAW AI Meta API** is a AI token analytics.
It allows developers to fetch **real-time token metadata, smart money insights, and market activity** across multiple chains — using a single endpoint.

---

## 🌐 Supported Chains

* 🟡 **BSC (Binance Smart Chain)** → `chain=bsc`
* 🟣 **Solana** → `chain=sol` *(via Binance Web3 CT_501)*

---

## ⚡ Features

* 🔥 **Binance AI Data (Primary Source)**
* 📊 Full Market Metrics (price, liquidity, volume)
* 📈 Multi-timeframe Price Changes (5m, 1h, 4h, 24h)
* 🧠 Smart Money Tracking
* 🏦 Holder Distribution Analysis
* 🚀 Token Launch Data
* 🧩 Dual Output:

  * `raw` → full Binance response
  * `structured` → clean developer-friendly format

---

## 📡 API Endpoint

```bash
GET /api/ai_metadata
```

### Query Parameters

| Parameter | Type   | Required | Description            |
| --------- | ------ | -------- | ---------------------- |
| address   | string | ✅ yes    | Token contract address |
| chain     | string | ✅ yes    | `bsc` or `sol`         |

---

## 🔍 Example Request

### BSC

```bash
https://pokebookai.com/api/ai_metadata?chain=bsc&address=0x55d398326f99059ff775485246999027b3197955
```

### SOL

```bash
https://pokebookai.com/api/ai_metadata?chain=sol&address=So11111111111111111111111111111111111111112
```

---

## 📦 Example Response

```json
{
    "code": "000000",
    "data": {
        "price": "48.00617218672732466029",
        "nativeTokenPrice": "589.09115969567768209591",
        "volume24h": "53803143.235015073706599196363",
        "volume24hBuy": "26880240.472839229350983682189",
        "volume24hSell": "26922902.762175844355615514174",
        "volume4h": "7179919.170580971950485838372",
        "volume1h": "3181854.878039371691111933489",
        "volume5m": "84557.068962077549412188792",
        "count24h": "39869",
        "count24hBuy": "19850",
        "count24hSell": "20019",
        "percentChange5m": "0.03",
        "percentChange1h": "0.02",
        "percentChange4h": "0.03",
        "percentChange24h": "0.01",
        "marketCap": "162260777.94315716831842935701774977509483735135",
        "totalSupply": "3379998.56",
        "circulatingSupply": "3379998.249225519124584315",
        "priceHigh24h": "48.59526604943723770716",
        "priceLow24h": "47.4815509902145490401",
        "holders": "78255",
        "fdv": "162260792.8622504084644326891824",
        "liquidity": "13393863.149264026822944",
        "launchTime": 1600950241000,
        "top10HoldersPercentage": "93.2621248736909194",
        "kycHolderCount": "23579",
        "kolHolders": "17",
        "kolHoldingPercent": "0.000059",
        "proHolders": "138",
        "proHoldingPercent": "0.003357",
        "smartMoneyHolders": "1",
        "smartMoneyHoldingPercent": "0"
    },
    "success": true
}
```

---

## 🧠 Data Breakdown

### 🔥 Metrics

* Price
* Market Cap
* FDV
* Liquidity
* Volume (24h, 4h, 1h, 5m)

### 📈 Price Changes

* 5 minutes
* 1 hour
* 4 hours
* 24 hours

### 🔄 Transactions

* Total transactions
* Buy vs Sell count

### 🏦 Supply

* Total Supply
* Circulating Supply

### 👥 Holders

* Total holders
* KYC holders

### 🧠 Smart Money

* KOL wallets
* Pro traders
* Smart money wallets

---

## ⚠️ Notes

* Some fields may return `0` or `null` depending on token availability
* This API is designed as a **wrapper — not a data origin**

---



## 🚀 Roadmap

* [ ] API Key System
* [ ] Rate Limiting Engine
* [ ] AI Trading Signals (BUY / SELL / AVOID)
* [ ] Multi-chain Expansion (ETH, BASE, ARB)
* [ ] Telegram Bot Integration

---

## 🤝 Contributing

Contributions are welcome!

* Fork the repo
* Create a new branch
* Submit a pull request

---

## 📜 License

---

## 🧠 About pCLAW

pCLAW is a **data-driven AI agent platform** focused on:

* Smart money tracking
* Token analytics
* Autonomous crypto agents

---

## ⚡ Final Note

This is not just an API wrapper.
This is the foundation of a **crypto intelligence layer**.

> Build tools. Build agents. Build alpha.
