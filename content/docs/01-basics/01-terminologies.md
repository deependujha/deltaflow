---
title: Terminologies
type: docs
prev: docs/01-basics/
next: docs/01-basics/02-moneyness-of-options
weight: 1
---

## Options

An **option** is a contract that gives you the **right, but not the obligation**, to buy or sell something (usually a stock or an index) at a pre-agreed price (**strike price**) on or before a certain date (**expiry**).

There are two types:

- **Call Option (CE)** 🔼 – Right to **buy**
- **Put Option (PE)** 🔻 – Right to **sell**

### Strike Price 🏏

- The **strike price** is the price at which you can buy or sell the underlying asset (stock/index) when you exercise your option.

### Spot Price

- The **spot price** is the current market price of the underlying asset (stock/index).

{{< callout type="info" >}}
  NIFTY is at 20,000. And, a NIFTY CE has a strike price of 20,100.

  Meaning, you can buy NIFTY CE today, it gives you the right to buy NIFTY at 20,100 on expiry (let's say 1 month from now).

  The current price of NIFTY: 20,000 is called the **spot price**.
{{< /callout >}}

---

## Buying vs Selling Options

- **Buying** an option means you pay a **premium** to acquire the right (option) to decide later if you wish to exercise your option or not (buy/sell the underlying).
- **Selling** an option means you receive a **premium** in exchange for taking on the **obligation** to fulfill the contract if the buyer chooses to exercise it. You recieve the premium upfront, but you need to `deposit a margin` with the exchange (or broker, like Zerodha) to cover the risk of the obligation.

---

## European Options v/s American Options

- **European Options**: Can be exercised **only at expiry**  
- **American Options**: Can be exercised **anytime before or at expiry**

In India:

- All **index options (like NIFTY, BANKNIFTY)** are European-style
- **Stock options** are American-style

> For most algo systems, we don't exercise — we **`square off` (reverse our position)**. But the style still affects pricing and strategy.

---

## Square off

**Square off** means to close your position by taking the opposite trade.

For example:

- if you bought something (CE/PE), you sell the same thing to close your position
- if you sold something (CE/PE), you buy the same thing to close your position

### ⏳ When does it happen?

You can square off anytime before expiry

- If you don’t, then at expiry:
  - **It gets auto-exercised (if in-the-money)**, or
  - **It expires worthless (if out-of-the-money)**

> [!NOTE]
> [Margin Call](https://www.imdb.com/title/tt1615147/)
> If you're short and the risk increases, broker might square off your position forcibly (margin call).
> Zerodha might call/sms/email you to either add more margin or they will square off your position.

---

## Call Option (CE)

### Buying CALL Option (CE)

- You buy a **Call Option** if you expect the price of the underlying to **go up**.
- You pay a **premium** upfront
- You profit if the price rises **above strike + premium**
- Risk is **limited** (just the premium you paid)
- Reward is **unlimited**

### Selling CALL Option (CE)

- You sell a **Call Option** if you expect the price of the underlying to **go down** or **stay flat**(`theta decay will be in your favour`).
- You receive a **premium** upfront (since you sold it)
- But, you deposit the margin with the exchange (or broker, like Zerodha) to cover the risk of the obligation
- You profit if the price stays **below strike + premium**
- You lose if the price rises **above strike + premium**
- Risk is **unlimited** (if the price goes up)
- Reward is **limited** (just the premium you received)

---

## Put Option (PE)

### Buying PUT Option (PE)

- You buy a **Put Option** if you expect the price of the underlying to **go down**.
- You pay a **premium** upfront
- You profit if the price falls **below strike - premium**
- Risk is **limited** (just the premium you paid)
- Reward is **unlimited**

### Selling PUT Option (PE)

- You sell a **Put Option** if you expect the price of the underlying to **go up** or **stay flat**(`theta decay will be in your favour`).
- You receive a **premium** upfront (since you sold it)
- But, you deposit the margin with the exchange (or broker, like Zerodha) to cover the risk of the obligation
- You profit if the price stays **above strike - premium**
- You lose if the price falls **below strike - premium**
- Risk is **unlimited** (if the price goes down)
- Reward is **limited** (just the premium you received)
