---
title: More on Moneyness
type: docs
prev: docs/01-basics/03-moneyness-of-options
next: docs/02-option-greeks/
weight: 4
---

## General Points

### ITM & ATM

- Since, ITM options are already profitable, they have a `higher premium`.
- ATM options have a high chance of becoming ITM later, so they also have a `high premium`.

### OTM

- OTM options have less chance of becoming ITM, so they have a `lower premium`.
- Very far OTM options are often called **worthless** options, as they are unlikely to become ITM before expiry.
- So, their premium is very low.
- Bcoz, of very low premium, new traders often buy them, hoping for a big move. (like lottery tickets)
- Others, buy them to **hedge** their positions.

{{< callout type="info" >}}
  Let's say current NIFTY is at 20,000.

- We sold a CE 20,000 (ATM) for ₹100. If the price goes very up (say 25,000), we will lose a lot (might also margin call take place).
- So, we buy a CE 23,000 (OTM) for ₹5. When we start losing on the CE 20,000, we will start making money (or `cutting loses`) on the CE 23,000.
{{< /callout >}}

The above described is a classic **bear call spread** (a type of vertical spread) — it’s a **defined-risk strategy** that limits your max loss *and* caps your profit, in exchange for a smaller but safer payout.

---

### ⚙️ **Bear Call Spread Setup**

**Spot (NIFTY): 20,000**  
You do two things:

1. **Sell CE 20,000 (ATM)** at ₹100 → You receive ₹100  
2. **Buy CE 23,000 (OTM)** at ₹5 → You pay ₹5

---

### 💰 Net Credit = ₹95 (Your max profit)**

You collected ₹100 and paid ₹5. So you pocket ₹95 **if NIFTY stays below 20,000**.

---

### 🤯 Max Loss?

Let’s assume NIFTY flies to **25,000**.

- Your **sold CE 20,000** is ₹5,000 in loss (25,000 - 20,000)
- Your **bought CE 23,000** is worth ₹2,000 (25,000 - 23,000)

So:  
**Net loss = ₹5,000 - ₹2,000 = ₹3,000**  
But since you earned ₹95 upfront,  
**Final P&L = -₹2,905** (Max loss)

---

### 📏 Summary Table

| NIFTY at Expiry | 20,000 CE (sold) | 23,000 CE (bought) | Net P&L     |
|------------------|-------------------|---------------------|-------------|
| < 20,000         | ₹0 (worthless)    | ₹0 (worthless)      | +₹95        |
| 21,000           | -₹1,000           | ₹0                  | -₹905       |
| 22,000           | -₹2,000           | ₹0                  | -₹1,905     |
| 23,000           | -₹3,000           | ₹0                  | -₹2,905     |
| 24,000           | -₹4,000           | +₹1,000             | -₹2,905     |
| 25,000           | -₹5,000           | +₹2,000             | -₹2,905     |

---

### 🔒 Why Do This?

- You’re **bearish or neutral** — think market won’t go above 20k
- Want to earn premium, but **cap your worst-case scenario**
- Margin requirement is lower than naked CE sell  
  (brokers *love* this for risk control)

---

## P&L graph 📊

![Bear Call Spread P&L Graph](/assets/basics/bear-call-spread-pnl.png)

- 🟢 Left vertical line: ₹20,000 (Short CE)
- 🔴 Right vertical line: ₹23,000 (Long CE)
- 🔵 Blue curve: Net P&L at expiry

### 🧾 Interpretation

- Max profit: ₹95 (when NIFTY closes below 20,000)
- Max loss: ₹2,905 (when NIFTY closes at or above 23,000)
- Breakeven point: Around ₹20,095 (because ₹20,000 + ₹95 net credit)
