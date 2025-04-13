---
title: When to do what?
type: docs
prev: docs/01-basics/01-terminologies
next: docs/01-basics/03-moneyness-of-options
weight: 1
---

## Buy & Sell: CALL & PUT

![buy vs sell](/assets/basics/options-trading-call-and-put.webp)

### You're bullish 🐂

#### bull: `less money, less risk appetite`

- Buy a **Call Option (CE)**, by paying a premium
- You start to profit if the price goes **above** `strike + premium` (breakeven point).
- Risk is limited (just the premium you paid). If the price doesn't go above `strike + premium` at expiration, you lose the premium paid.
- Reward potential is theoretically unlimited as the price rises: Profit = `Underlying Price at Expiry - (Strike Price + Premium Paid)` (for Price > Breakeven).
- `max_loss: premium paid`, `max_profit: unlimited` (theoretically). *Note: Buying options generally has a lower probability of success than selling.*

#### bull: `more money, more risk appetite`

- Sell a **Put Option (PE)**, by receiving a premium
- You profit if the price stays **above** `strike - premium` (breakeven point) at expiration. Maximum profit (keeping the full premium) is achieved if the price expires **at or above the strike price**.
- Risk is **substantial** if the price goes down significantly. If the price goes below `strike - premium` at expiration, you **start incurring a loss**, which increases as the price falls further (Loss = `(Strike Price - Underlying Price at Expiry) - Premium Received`).
- Reward is limited to the premium received.
- You need to deposit a margin with the exchange (or broker) to cover the potential obligation.
- `max_loss: substantial` (Technically capped at `Strike Price - Premium Received`, occurring if the underlying price goes to zero), `max_profit: premium received`. *Note: Selling options generally has a higher probability of profit but exposes the seller to large potential losses relative to the premium received.*

---

### You're bearish 🐻

#### bear: `less money, less risk appetite`

- Buy a **Put Option (PE)**, by paying a premium
- You start to profit if the price goes **below** `strike - premium` (breakeven point).
- Risk is limited (just the premium you paid). If the price doesn't go below `strike - premium` at expiration, you lose the premium paid.
- Reward potential is substantial as the price falls: Profit = `(Strike Price - Premium Paid) - Underlying Price at Expiry` (for Price < Breakeven).
- `max_loss: premium paid`, `max_profit: substantial` (Technically capped at `Strike Price - Premium Paid`, occurring if the underlying price goes to zero). *Note: Buying options generally has a lower probability of success than selling.*

#### bear: `more money, more risk appetite`

- Sell a **Call Option (CE)**, and receive a premium
- You profit if the price stays **below** `strike + premium` (breakeven point) at expiration. Maximum profit (keeping the full premium) is achieved if the price expires **at or below the strike price**.
- Risk is **unlimited** (theoretically) if the price goes up significantly. If the price rises above `strike + premium` at expiration, you **start incurring a loss**, which increases as the price rises further (Loss = `(Underlying Price at Expiry - Strike Price) - Premium Received`).
- Reward is limited to the premium received.
- You need to deposit a margin with the exchange (or broker) to cover the potential obligation.
- `max_loss: unlimited` (theoretically), `max_profit: premium received`. *Note: Selling options generally has a higher probability of profit but exposes the seller to large potential losses relative to the premium received.*
