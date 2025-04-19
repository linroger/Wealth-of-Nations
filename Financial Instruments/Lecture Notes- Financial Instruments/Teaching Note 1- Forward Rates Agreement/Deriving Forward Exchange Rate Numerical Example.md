---
title: Deriving Forward Exchange Rate Numerical Example
tags:
  - currency_depreciation
  - forward_exchange_rate
  - futures_contracts
  - hedging_strategy
  - mark_to_market
aliases:
  - FX Forward Example
  - Forward Rate Derivation
key_concepts:
  - European bank hedging
  - Forward exchange rate
  - Futures contract payoff
  - Hedging currency risk
  - Mark to market
---

# Deriving Forward Exchange Rate Numerical Example

[Carry Trade](Carry%20Trade.md)
[Currency Forward](Currency%20Forward.md)

- [[Ch1 Introduction to Derivative Markets]]
- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]
- [[Deriving Forward Exchange Rate Numerical Example]]
- [[Primary vs. Secondary Commodities]]
- [[Foreign Exchange Quoting Conventions]]
- [[Forward Contracts on Exchange Rates]]
- [[Forwards and Futures Notes]]
- [[Hedging Strategies with Forwards]]
- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,  Carry Trades,  and Exchange Rate Movements]]
- [[Teaching Note 1 Forward Rates Agreement]]

| Exchange Rate | USD/EUR |
| ---- | ---- |
| Current Exchange Rate |$M_{0}=1.2673$|
| Forward Exchange Rate |$F=1.28$|
| US interest rate |$r_{USD} = 0.05$|
| EUR interest rate |$r_{EUR}=0.03$|

1. A US firm has sold a piece of equipment to a German client. German firm will pay EUR 5 million in T = 6 months
	- US Firm wants to hedge this receivable against EUR depreciation,  which will lessen the dollar amount of the receivable it is due to collect.
	- US firm can implement a hedge to pay EUR and receive USD at maturity,  at a forward exchange rate determined today.
		- Hedging Strategy
			- US Firm will pay EUR 5 million and receive
			- EUR 5 million and receive$$\text{EUR } 5, 000, 000 * 1.28=  \$6, 400, 000$$
		- Total Payoff to US Firm$$5, 000, 000*M_{T}+5, 000, 000(F-M_{T})$$

$$(5, 000, 000*1.2673)+[5, 000, 000(1.28-1.2673)]= \$6, 400, 000  ⚡$$

1. European Bank hedges its commitment to receive EUR in exchange for USD
	1. Borrow PV of EUR 5 million at$r_{e}=0.03$$$\text{EUR }5000000e^{\left(-0.03\times 0.5\right)}= \text{EUR }4925559.698$$
	1. Exchange EUR 4925559.698 into USD today at spot exchange rate$$\text{EUR }4925559.698 * 1.2673 \frac{\text{USD}}{\text{EUR}}= \text{USD } 6242161.81$$
	1. Invest this amount in dollar deposits at$r_{USD}=0.05$$$\text{USD } 6242161.81e^{0.05*\frac{1}{2}}=6400182.88$$
		1. Today,  the bank nets 0
1. At time T,  the bank:
	1. Receives 5 mil euros from the US firm (from fwd contract).
	1. Uses this money to close the 5 mil euro loan.
	1. Cashes in the dollar investment:$$\text{USD } 6242161.81e^{0.05*\frac{1}{2}}=6400182.88$$
	1. Gives this money to the client

		- Effective exchange rate:$$F=\frac{\text{USD 6400182.88}}{\text{EUR } 5000000}= 1.28004$$

1. Assume that at time t = 3 months the Euro appreciated from$M_{0}$= 1.2673 to$M_{t}$= 1.29
	- If the US firm wants to cancel the contract with the bank,  how much does it have to pay?
	- The US firm can enter into the reverse forward contract with the bank,  with payoff$$\text{Dollar payoff at$T$of reverse forward contract} = 5, 000, 000 × (M_{T} − F_{t,  T})$$Now:$$F_{t, T} = M_t × e^{(r_USD−r_EUR)×(T −t)} = 1.29 × e^{(0.05−0.03)×0.25} = 1.296 \$/EUR$$
	- The reverse contract neutralizes the former one.
- Payoff at$T$from forward + reverse forward$$= 5000000\times (F_{0, T}-S_T)+5000000 \times(M_T-F_{t, T})$$$$=$5000000\times(F_{0, T}- F_{t,  T})$$$$=$5000000$\times (1.281.296) = - \$80, 000$$
- The US firm will have to pay the bank$80, 000 at$T$
	- The Present Value of$-\$80, 000$is the value of the original forward contract to the US firm

$$
f_{t, T}=e^{-r_{\$}\times(T-t)}\times(F_{0, T}-F_{t, T})\times5\text{ mil}=-\$79, 006.2
$$

- Since it costs$\$79, 006.2$to close the position,  the value of the forward contract to the firm must equal this amount.
	- Vice-versa,  the value to the bank must be \$79, 006.20

> [!note]
> The above formula is general: The value of a forward contract to $sell$ euros at a prespecifled
>
> price $K$ is always given by $$f_{t, T}=e^{-r_{\$}\times(T-t)}\times(K-F_{t, T})$$

To summarize,  we found:

1. The Forward (Delivery) Price - the price decided at time 0 to buy / sell goods (Euros) in the future is given by$$
\begin{aligned}F_{0, T}=M_0\times e^{(r_{\$}-r_e)T}\end{aligned}

$$
2. The value of an $existing$ forward contract to deliver goods (Euros) at preset price $K$ (determined some time in the past) is equal to the cost / profit of closing the contract: $$ f_{t, T}=[K-F_{t, T}]\times e^{-r_{\$}(T-t)}$$
- This is the value of forward contract to $sell$. 

- What is the value of a forward contract to buy (i.e. a long forward contract?)

· Important Note: The value of a forward contract at inception $t=0$ is zero.
- The Forward delivery price $K=F_{0, T}$,  which makes $f_{0, T}=0.$
* When two counterparties enter into a forward contract,  they do not exchange any money 
* In fact, they agree to exchange money only in the future,  depending on $M_T$

· Finally,  an equivalent formula is obtained by substituting $F_{t, T}$
$$

f_{t, T}=Ke^{-r_{\$}(T-t)}-M_te^{-r_{e}(T-t)}

$$

· The earlier derivation was obtained for currency forwards. · Similar derivations hold for other securities,  such as stocks,  bonds,  and commodities.

# EXAMPLE: HEDGING WITH FUTURES

Consider earlier example: The US firm could hedge with futures contracts instead of forwards.
- CME Euro FX Futures have size of 125, 000 Euro and expire on Mar,  Jun,  Sep,  and Dec.
- Suppose that $T =$ Mar 2007 and $F_{0, T} = 1.28$.
- US firm can short 5 mil/125, 000 $\approx$ 40 futures contracts.
- Every day $t$,  $$P/L_t = k \times 125, 000 \times (F_{1, T} - F_{t, T}) =5, 000, 000\times (F_{1, T} - F_{t, T})$$
- At maturity $T$: Payoff at $T = (P/L)_t + (P/L)_2 + ... + (P/L)_T$
  - $=5, 000, 000\times (F_{0, T} - F_{T, T})$
  - $=5, 000, 000\times (F_{0, T} - M_T)$
  - $=$ Payoff of Forward Contract at $T$ if  $F_{0, T} = F_{T, T}$

**Caveat**: The total payoff from using a constant number of contracts $k$ every period is actually not exactly equivalent to the one of a forward contract.
- Because of mark to market,  trading profits and losses accrue **over time** to the hedger.
- The correct statement of the payoff at $T$ is in fact:
  - Payoff at $T$ = $$(P/L)_1 \times e^{-r(T-t)} + (P/L)_2 \times e^{-r(T-t2)} + ... + (P/L)_T \times e^{-r(T-T)}$$
  - where $dt = 1/365 = 1$ day (in annual units)

To obtain the forward contract's payoff,  we must **tail the hedge** and choose the number of contracts $k$ per period as $$k = 40 \times e^{-r(T-t1)}$,  
$k = 40 \times e^{-r(T-t2)}$,  ...,  $k = 40 \times e^{-r(T-t_{T-1})}$,  $k_{T-1} = 40$$
- which yields the payoff sequence at $T =5, 000, 000\times (F_{0, T} - F_{1, T}) \times e^{r(T-t1)} + 5, 000, 000\times (F_{1, T} - F_{2, T}) \times e^{r(T-t2)} + ... + 5, 000, 000\times (F_{T-1, T} - F_{T, T}) \times e^{r(T-T)}$
  - $=5, 000, 000\times (F_{0, T} - M_T)$

---

# SPECULATING WITH FUTURES

Futures are also excellent vehicles to speculate on a view about the variation in the underlying.
- Example: Let today be Friday Jan 1,  2010. The Euro/Dollar exchange rate is ${} S_T = 1.4326$.
- A speculator believes that the Euro/Dollar rate will increase over the weekend.
- Consider two strategies:
  1. Funded Speculative Position:
     - Buy 125, 000 Euros for $179, 075 = 125, 000 x 1.4326.
  2. Unfunded Speculative Position through Futures
     - Go long 1 Futures contract at the CME. E.g.,  The March 10 Futures price on Jan 1,  2010 was $F_{T, T} = 1.4334$
     - First,  initial margin $2, 995.

On Monday,  Jan 4,  2010,  $ (t)$,  the exchange rate was ${} S_T = 1.4413$ and the Mar 10 Futures was $F_{T, T} = 1.441$.
- Funded Speculative Position: The position is $180162.5 = 125, 000 x 1.441. Thus
  - Profit = $180162.5 - $179, 075 = $1087.5
  - Return on Investment ${} \frac{1087.5}{179, 075} = 0.607\%$
- Unfunded Speculative Position through Futures:
  - Profit = 125, 000 x $ (1.441 - 1.4334)$ = $950
  - Return on Investment ${} \frac{950}{2, 995} = 31.72\%$
## HEDGING WITH FUTURES:

**Objective**: To mitigate the risk of price fluctuations in a commodity or currency that a firm is either planning to buy or sell in the future.

### STEP 1: DETERMINE NUMBER OF CONTRACTS
- **Equation**: $N = \frac{V}{S}$
- **Rationale**: The firm calculates the number of futures contracts $N$ needed by dividing the total value it wants to hedge $V$ by the size of one futures contract $S$. This ensures that the hedge covers the entire value of the exposure.

### STEP 2: CALCULATE DAILY PROFIT/LOSS
- **Equation**: $P/L_t = N \times S \times (F_{1, T} - F_{t, T})$
- **Rationale**: The profit or loss on any given day $t$ is determined by the change in the futures price from the initial price $F_{1, T}$ when the contract was entered into,  against the price at the current time $F_{t, T}$. This captures the gain or loss from the hedge on that day.

### STEP 3: PAYOFF AT MATURITY
- **Equation**: $\text{Payoff at } T = \sum_{t=1}^{T} P/L_t = V \times (F_{0, T} - M_T)$
- **Rationale**: The total payoff at maturity is the sum of the daily profits and losses. If the initial futures price $F_{0, T}$ is greater than the spot price at maturity $M_T$,  the firm has a net gain on the hedge; otherwise,  it's a net loss.

### PAYOFF CONSIDERING TIME VALUE OF MONEY
- **Equation**: $\text{Payoff at } T = \sum_{i=1}^{T} (P/L_{t_i}) \times e^{-r(T-t_i)}$
- **Rationale**: The present value of future profits and losses is calculated using the risk-free interest rate $r$ to discount them. This accounts for the time value of money,  recognizing that future cash flows are worth less in present terms.

### TAIL THE HEDGE
- **Equation**: $k_{t_i} = N \times e^{-r(T-t_i)}$
- **Rationale**: To maintain the hedge over time,  the number of contracts may need to be adjusted due to the change in present value of the hedged amount. This is called "tailing the hedge."

## SPECULATING WITH FUTURES:

**Objective**: To profit from the anticipated movement in the price of an underlying commodity or currency.

### FUNDED SPECULATIVE POSITION
- **Equation**: $\text{Profit} = N \times S \times (S_{T+1} - S_T) - I$
- **Rationale**: The speculator takes a funded position by buying the underlying asset directly and profits from the price difference over time,  minus the initial investment $I$.

### UNFUNDED SPECULATIVE POSITION THROUGH FUTURES
- **Equation**: $\text{Profit} = N \times S \times (F_{T+1, T} - F_{T, T})$
- **Rationale**: Instead of purchasing the underlying asset,  the speculator enters into futures contracts,  aiming to profit solely from the price change in the futures contract,  without the need for a large initial investment.

### RETURN ON INVESTMENT
- **Equation for funded**: $R = \frac{\text{Profit}}{I}$
- **Equation for unfunded**: $R = \frac{\text{Profit}}{\text{Initial Margin}}$
- **Rationale**: Return on investment (ROI) measures the efficiency of the investment. For funded positions,  ROI is calculated against the total initial investment. For unfunded speculative positions,  ROI is calculated against the initial margin required to hold the futures position. The initial margin is usually a fraction of the total contract value,  allowing for leverage.
