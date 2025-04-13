---
title: Moneyness of Options
type: docs
prev: docs/01-basics/02-when-to-do-what
next: docs/01-basics/04-more-on-moneyness
weight: 3
---

## Moneyness of Options

![moneyness](/assets/basics/moneyness.png)

## ✅ **Definition:**

**Moneyness** describes the relationship between the **strike price** of an option and the **current market price** (spot price) of the underlying asset.  
It helps classify whether exercising the option **right now** would be profitable or not (ignoring premium paid).

---

## 🔄 **Types of Moneyness:**

| Type             | Call Option Condition         | Put Option Condition          | Intrinsic Value > 0? |
|------------------|-------------------------------|-------------------------------|-----------------------|
| **In the Money** | Spot price > Strike price     | Spot price < Strike price     | ✅ Yes                |
| **At the Money** | Spot price ≈ Strike price     | Spot price ≈ Strike price     | ❌ No                 |
| **Out of the Money** | Spot price < Strike price     | Spot price > Strike price     | ❌ No                 |

---

## 🧠 **Key Concepts:**

- **Intrinsic Value** (real value if expired now):  
  - Call: `max(Spot - Strike, 0)`  
  - Put: `max(Strike - Spot, 0)`
  
- **Extrinsic Value** (aka time value):  
  The portion of option price that’s **not** intrinsic value — comes from time to expiry, volatility, etc.

- **Total Premium** = Intrinsic Value + Extrinsic Value

---

## 📊 **Moneyness Ratio** (Quantitative Expression)

- **For Call Options**: `Spot Price / Strike Price`  
- **For Put Options**: `Strike Price / Spot Price`

Higher than 1 → ITM  
Exactly 1 → ATM  
Lower than 1 → OTM

---

## 🧪 **Examples (Nifty at 20,000):**

- **Call Option:**
  - CE 20,000 → ATM (zero intrinsic value)
  - CE 19,000 → ITM (₹1,000 intrinsic value)
  - CE 21,000 → OTM (worthless if expired now)

- **Put Option:**
  - PE 20,000 → ATM
  - PE 21,000 → ITM (₹1,000 intrinsic value)
  - PE 19,000 → OTM

---

## 📈 **Advanced Note (Relative Moneyness):**

Used in pricing models like Black-Scholes:

- Depends on spot, strike, **volatility**, and **time to expiry**
- Expressed via:
  - **Delta**: Options with delta ~0.5 are typically ATM  
  - **Log-moneyness**: `ln(Spot / Strike)`

This probabilistic view helps calculate **likelihood of option expiring ITM**, not just its status right now.

---

## 🗣️ **Intuitive Interpretation:**

> "Moneyness tells you if the option buyer would make money if the option expired **right now**."

- In the Money → Profitable if exercised now  
- At the Money → Breakeven  
- Out of the Money → Worthless if expired now

---

## 💡 **Quick Table (Spot Price = 20,000)**

| Option Type | Strike Price | Moneyness | Explanation                              |
|-------------|--------------|-----------|------------------------------------------|
| Call (CE)   | 19,000       | ✅ ITM    | Buy at 19k, sell at 20k → ₹1,000 gain    |
| Call (CE)   | 20,000       | 🟡 ATM    | No gain/loss                             |
| Call (CE)   | 21,000       | ❌ OTM    | Buy at 21k, sell at 20k → loss           |
| Put (PE)    | 21,000       | ✅ ITM    | Sell at 21k, buy at 20k → ₹1,000 gain    |
| Put (PE)    | 20,000       | 🟡 ATM    | No gain/loss                             |
| Put (PE)    | 19,000       | ❌ OTM    | Sell at 19k, buy at 20k → loss           |
