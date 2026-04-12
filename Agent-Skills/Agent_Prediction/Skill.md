
# 🧠 pCLAW AI Prediction Market API

An intelligent API that provides **AI-powered 24-hour price predictions** for tokens on Binance Smart Chain (BSC).

---

## 📌 Overview

The **AI Prediction Market API** analyzes historical price data and market sentiment to generate a clear, data-driven prediction for the next 24 hours.

It combines:

* 📊 Technical analysis (candlestick data)
* 💸 Market flow indicators

To deliver actionable insights such as:

* Support & resistance levels
* Trend direction
* Natural language summary

This API is designed to enhance:

* Token analysis tools
* Trading interfaces
* DeFi dashboards

---

## 🌐 Endpoint

```
GET https://pokebookai.com/api/ai_prediction?address={token_address}
```

---

## 🔍 Query Parameters

| Parameter | Type   | Required | Description                                       |
| --------- | ------ | -------- | ------------------------------------------------- |
| address   | string | ✅ Yes    | Valid BSC token contract address (starts with 0x) |

---

## 🧪 Example Request

```bash
curl --location "https://pokebookai.com/api/ai_prediction?address=0x55d398326f99059ff775485246999027b3197955"
```

---

## ✅ Success Response

```json
{
  "success": true,
  "prediction": {
    "support": "0.002453",
    "resistance": "0.004454",
    "direction": "Bullish",
    "priceChange": "+6.52%",
    "summary": "Price is likely to move upward toward resistance at $0.004454. Positive netflow and increasing volume support bullish momentum.",
    "volume24h": 17869.02,
    "netflow": 5662.9,
    "smartMoneyHolders": 3,
    "smartMoneyPercent": "0.000"
  }
}
```

---

## ❌ Error Response

```json
{
  "success": false,
  "message": "Invalid address. Please provide a valid BSC token contract address."
}
```

---

## 📊 Response Fields

| Field             | Type   | Description                              |
| ----------------- | ------ | ---------------------------------------- |
| support           | string | Support level (7-day lowest low)         |
| resistance        | string | Resistance level (7-day highest high)    |
| direction         | string | Market bias: Bullish / Bearish / Neutral |
| priceChange       | string | 24h price change (percentage)            |
| summary           | string | AI-generated explanation                 |
| volume24h         | number | 24h trading volume                       |
| netflow           | number | Buy volume - sell volume                 |
| smartMoneyHolders | int    | Number of smart money wallets            |
| smartMoneyPercent | string | % of supply held by smart money          |

---

## ⚙️ How It Works

### 1. 📈 Candlestick Analysis

* Fetches **7 days of 1-hour candles**
* Calculates:

  * Support → lowest low
  * Resistance → highest high

### 2. 📉 Momentum Calculation

* Measures **24h price change**
* Determines trend:

  * Bullish
  * Bearish
  * Neutral

### 3. 💰 Market Flow Insights

* Analyzes:

  * 24h volume
  * Netflow (buy vs sell pressure)
  * Smart money activity

### 4. 🤖 AI Summary Generation

* Converts all signals into a **human-readable explanation**

---

## 💻 Frontend Integration Example

```javascript
async function getPrediction(tokenAddress) {
    try {
        const response = await fetch(
            `https://pokebookai.com/api/ai_prediction?address=${encodeURIComponent(tokenAddress)}`
        );

        const result = await response.json();

        if (result.success) {
            console.log("24H Prediction:", result.prediction);
        } else {
            console.error(result.message);
        }
    } catch (error) {
        console.error("Failed to fetch prediction:", error);
    }
}
```

---

## 🚀 Key Features

* ⚡ Fast & lightweight
* 📊 Based on real candlestick data (7d / 1h)
* 🧠 AI-style readable insights
* 💸 Includes volume & netflow
* 🐋 Smart money tracking
* 🔌 Easy frontend integration
* 🌍 Public API endpoint

---

## 🎯 Use Cases

* Token scanners
* Trading dashboards
* DeFi analytics tools
* Prediction widgets
* Educational trading platforms

---

## ⚠️ Disclaimer

> This is **not financial advice**.

The information and predictions provided by this API are for **educational and informational purposes only**.

Cryptocurrency markets are highly volatile and involve significant risk.

* Always **DYOR (Do Your Own Research)**
* Never rely solely on automated predictions
* Consult a financial advisor if needed
