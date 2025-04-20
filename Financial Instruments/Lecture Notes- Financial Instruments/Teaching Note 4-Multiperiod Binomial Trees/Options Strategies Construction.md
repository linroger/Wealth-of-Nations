---
linter-yaml-title-alias: OPTIONS STRATEGIES CONSTRUCTION
title: OPTIONS STRATEGIES CONSTRUCTION
tags:
  - butterfly_spread
  - option_expiration
  - options_strategies
  - protective_put
  - stock_price
aliases:
  - Protective Put Strategy
key_concepts:
  - Limited risk
  - Minimal stock movement
  - Protective put portfolio
  - Stock near expiration
  - Stock price movement
---

- **[[Teaching Note 4-Multiperiod Binomial Trees]]**
	- [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing]]
	- [[Binomial Tree Steps]]
	- [[Calculate Stock Prices at Different Nodes]]
	- [[Options Strategies Construction]]
	- [[Teaching Note 4-Multiperiod Binomial Trees]]
	- [[Financial Instruments/Lecture Notes/Teaching Note 4-Multiperiod Binomial Trees/The Pricing of Options and Corporate Liabilities]]

# Options Strategies Construction

Value of a protective put portfolio at option expiration

|          |$S_T \leq X$|$S_T - X$|
|----------|------------------|---------------|
| Stock    |$S_T$        |$S_T$    |
| + Put    |$X - S_T$    |$0$      |
| Total    |$X$          |$S_T$    |

Value of a covered call position at option expiration

|                   |$S_T$      |$S_T$      |
|-------------------|----------------|----------------|
| Payoff of stock   |$S_T$      |$S_T$      |
| + Payoff of written call |$-0$      |$-(S_T - X)$|
| Total             |$S_T$      |$X$        |

Value of a straddle position at option expiration

|               |$S_T < X$|$S_T \geq X$|
|---------------|---------------|------------------|
| Payoff of call|$0$      |$S_T - X$    |
| + Payoff of put |$X - S_T$|$0$          |
| Total         |$X - S_T$|$S_T - X$    |

Value of a bullish spread position at expiration

|                                    |$S_T = X_1$|$S_T - X_1$|$S_T = X_2$|
|------------------------------------|-----------------|-----------------|-----------------|
| Payoff of purchased call, exercise price =$X_1$|$0$          |$S_T - X_1$|$S_T - X_1$|
| + Payoff of written call, exercise price =$X_2$|$-0$        |$-0$        |$-(S_T - X_2)$|
| Total                                |$0$          |$S_T - X_1$|$X_2 - X_1$|

### PROTECTIVE PUT

[Protective Put Option Strategy - Fidelity](0.%20Finance%20Notes/1.%20Financial%20Instruments/Derivatives/0/Protective%20Put%20Option%20Strategy%20-%20Fidelity.md)
**Construction:**

- Buy a stock.
- Buy a put option at strike price ($K$).

| Strategy Component | Type | Strike ($(K)$) | Position |  |
| ---- | ---- | ---- | ---- | ---- |
| Call Option | Call |$(K_0 = 80)$| Long |  |
| Call Option | Call |$(K_1 = 100)$| Short (2) |  |
| Call Option | Call |$(K_2 = 120)$| Long |  |

**Features:**

- A protective put is used to protect against a decline in the value of the stock owned.
- It sets a floor on the potential loss from holding the stock but allows for unlimited upside potential.
**When Beneficial:**
- When expecting the stock to rise but want insurance against a significant drop.
**When Disadvantageous:**
- The cost of the put option can eat into profits if the stock price rises.

### COVERED CALL

[Long Call Cash Backed Options Strategy - Fidelity](Long%20Call%20Cash%20Backed%20Options%20Strategy%20-%20Fidelity.md)
Features:

- A covered call generates income via the premium received for selling the call.
- Limits upside potential above the strike price of the call option.
**When Beneficial:**
- When expecting the stock to rise modestly or remain flat.
**When Disadvantageous:**
- If the stock rises significantly beyond the strike price, potential gains are capped.

### COLLAR

**Construction:**

- Buy a stock.
- Buy a put option at strike price ($K_0$).
- Sell a call option at strike price$(K_2)$.

| Strategy Component | Type | Strike ($(K)$) | Position |
|---------------------|-----------|----------------|-----------|
| Stock | --- | --- | Long |
| Put Option | Put |$(K_0 = 80)$| Long |
| Call Option | Call |$(K_2 = 120)$| Short |

**Features:**

- A collar is used to protect against large losses but also caps the upside.
- It is a cost-effective strategy to protect the downside, as the premium received from the call option helps pay for the put option.
**When Beneficial:**
- When you own the stock and want to protect against a decline with minimal cost.
**When Disadvantageous:**
- Limits the upside potential if the stock price increases significantly.

### BEAR SPREAD

**Construction:**

- Buy a put option at higher strike price$(K_2)$.
- Sell a put option at lower strike price$(K_1)$.

| Strategy Component | Type | Strike ($(K)$) | Position |
|--------------------|------|----------------|----------|
| Put Option | Put |$(K_2 = 120)$| Long |
| Put Option | Put |$(K_1 = 100)$| Short |

**Features:**

- A bear spread profits from a decline in the underlying stock price but has limited risk and reward.
- The maximum profit and loss are known at the outset.
**When Beneficial:**
- When expecting a moderate decline in the stock price.
**When Disadvantageous:**
- If the stock price increases or decreases significantly beyond the strikes.

### BULL SPREAD

**Construction:**

- Buy a call option at lower strike price$(K_0)$.
- Sell a call option at higher strike price$(K_1)$.

| Strategy Component | Type | Strike ($(K)$) | Position |
|--------------------|------|----------------|----------|
| Call Option | Call |$(K_0 = 80)$| Long |
| Call Option | Call |$(K_1 = 100)$| Short |

**Features:**

- A bull spread profits from a moderate increase in the stock price.
- Risk and potential reward are limited.
**When Beneficial:**
- When expecting a moderate increase in the stock price.
**When Disadvantageous:**
- If the stock price falls significantly or rises well beyond the sold call strike.

### BULL SPREAD USING PUTS

**Construction:**

- Buy a put option at higher strike price$(K_1)$.
- Sell a put option at lower strike price$(K_0)$.

| Strategy Component | Type | Strike ($(K)$) | Position |
|--------------------|------|----------------|----------|
| Put Option | Put |$(K_1 = 100)$| Long |
| Put Option | Put |$(K_0 = 80)$| Short |

**Features:**

- Similar to a bull spread with calls but uses puts.
- It profits from a moderate increase in the underlying stock price, with limited risk and reward.
**When Beneficial:**
- When slightly bullish on the stock but want to limit risk.
**When Disadvantageous:**
- If the stock price significantly declines or significantly exceeds$(K_1)$.

### BUTTERFLY SPREAD

**Construction (Long 1 call with strike$(K_0)$):**

- Buy 1 call option at lower strike price$(K_0)$.
- Sell 2 call options at medium strike price$(K_1)$.
- Buy 1 call option at higher strike price$(K_2)$.

| Strategy Component | Type | Strike ((K)) | Position |
|--------------------|------|----------------|-----------|
| Call Option | Call |$(K_0 = 80)$| Long |
| Call Option | Call |$(K_1 = 100)$| Short (2) |
| Call Option | Call |$(K_2 = 120)$| Long |

**Features:**

- A butterfly spread profits from minimal movement in the underlying stock price.
- It has limited risk and is designed for a market view forecasting little volatility.
**When Beneficial:**
- When expecting the stock to remain near$(K_1)$at expiration.
**When Disadvantageous:**
- If the stock moves significantly away from$(K_1)$.

### BUTTERFLY SPREAD - 2

**Construction:(Long 1 put with strike$(K_0)$)**

- Buy 1 put option at lower strike price$(K_0)$.
- Sell 2 put options at medium strike price$(K_1).$
- Buy 1 put option at higher strike price$(K_2)$.

| Strategy Component | Type | Strike ((K)) | Position |
|--------------------|------|----------------|-----------|
| Put Option | Put |$(K_0 = 80)$| Long |
| Put Option | Put |$(K_1 = 100)$| Short (2) |
| Put Option | Put |$(K_2 = 120)$| Long |

**Features:**

- Similar to the previous butterfly spread but uses puts.
- Profits from minimal movement in the underlying stock price, with limited risk.
**When Beneficial:**
- When expecting the stock to remain near$(K_1)$at expiration.
**When Disadvantageous:**
- If the stock moves significantly away from$(K_1)$.