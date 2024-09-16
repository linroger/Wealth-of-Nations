---
Owner: RRoger Lin
tags:
  - Options
aliases:
  - Options
---
# OPTIONS FINANCIAL ENGINEERING
## OPTIONS AS INSTRUMENTS OF VOLATILITY

+ A call option becomes in-the-money and hence profitable if the underlying price increases, indirectly associating it with a bullish view.
+ The treatment of put options is similar. Puts are seen as appropriate for an investor who thinks the price of the underlying asset is going to decrease.
+ A market maker with a net long position in options is someone who is “expecting” the volatility to increase. A market maker who is short the option is someone who thinks that the volatility of the underlying is going to decrease.
+ From a market practitioner’s point of view, options are instruments of volatility. A retail investor who owns a call on an asset,$S_t$, may feel that a persistent upward movement in the price of this asset is “good” for him or her. But, a market maker who may be long in the same call may prefer that the underlying price$S_t$oscillate as much as possible, as often as possible. The more frequently and violently prices oscillate, the more long (short) positions in option books will gain (lose), regardless of whether calls or puts are owned.

### EXAMPLE

Wall Street firms are gearing up to recommend long single-stock vol positions on companies about to report earnings. While earnings seasons often offer opportunities for going long vol via buying Calls or Puts, this season should present plenty of opportunities to benefit from long vol positions given overall negative investor sentiment. Worse-than-expected earnings releases from one company can send shockwaves through the entire market. The big potential profit from these trades is from gamma, in other words, large moves in the underlying, rather than changes in implied vol. One promising name… announced in mid-February that manufacturing process and control issues have led to reduced sales of certain products in the United States, which it expected to influence its first quarter and full-year sales and earnings. On Friday, options maturing in August had a mid-market implied vol of around 43%, which implies a 2.75% move in the stock per trading day. Over the last month, the stock has been moving on average 3% a day, which means that by buying options on the company, you’re getting vol cheap. (Derivatives Week, now part of GlobalCapital, April 1, 2001)

This reading illustrates several important characteristics of options:

+ First, we clearly see that puts and calls are considered as similar instruments by market practitioners. The issue is not to buy puts or calls, but whether or not to buy them.
+ Second, and this is related to the first point, note that market participants are concerned with volatilities and not with the direction of prices—referring to volatility simply as vol. Market professionals are interested in the difference between actual daily volatilities of stock prices and the volatilities implied by the options. Implied volatility is calculated by taking the observed option price in the market and a pricing formula such as the Black Scholes formula that will be introduced below and backing out the volatility that is consistent with the option price given other input parameters such as the strike price of the option, for example.
+ The reading suggests that options imply a daily volatility of 2.75%, while the actual daily volatility of the stock price is 3%. According to this, options are considered “cheap,” since the actual underlying moves more than what the option price implies on a given day.
+ Finally, the reading seems to refer to two different types of gains from volatility. One, from “large movements in the underlying price,” leads to gamma gains, and the other, from implied volatility, leads to vega gains. During this particular episode, market professionals were expecting implied volatility to remain the same, while the underlying assets exhibited sizable fluctuations.

Options: Definition and Notation

+ Option contracts are generally divided into the categories of plain vanilla and exotic options, although many of the options that used to be known as exotic are vanilla instruments today.
+ American-style options can be exercised anytime until expiration and hence may be more expensive. They may carry an early exercise premium. At the expiration date, options cease to exist.

### **NOTATION**

+ We denote the strike prices by the symbol K, and the expiration date by T.
+ The price or value of the underlying instrument will be denoted by$S_t$﻿ if it is a cash product, and by$F_t$﻿ if the underlying is a forward or futures price.
+ The fair price of the call at time t will be denoted by$C(t)$﻿, and the price of the put by$P(t)$﻿. These prices depend on the variables and parameters underlying the contract.
+ We use$S_t$﻿as the underlying, and write the corresponding call option pricing function as:$C(S_t, K, T, r, \sigma)$﻿

Here,$\sigma$﻿ is the volatility of$S_t$﻿ and$r$﻿ is the spot interest rate, assumed to be constant.

## IMPERFECT HEDGING

Initial Position and the Hedge

1. Buy a Call Option (Long Call Position): The market maker buys a call option$C(t)$﻿ with the intention of keeping it on the books and selling it to another client later.
2. Funding the Position: The market maker borrows$C(t)$﻿ on money market at interest rate$r$﻿.
3. Short One Unit of Stock: To hedge the risk associated with the long call position, the market maker shorts one unit of stock valued at$S_t$﻿

Mathematical Representation

+ The portfolio value, V, can be represented as:$V_{t} = C(t) - S_{t}$﻿

Impact of a Small Change in$S_t$﻿

Change in Stock Price: A small change in the stock price is represented by$ΔS_t$﻿

Change in Option Price: Using the first partial derivative of the call price with respect to the stock price (Delta), the change in the option price is approximately:$\Delta C(t)≈ \frac{\partial C}{\partial S_t} \Delta S_t$
Change in Portfolio Value: The change in the portfolio value is given by:

$ΔV=ΔC(t)−ΔS$
$ΔV=\frac{\partial C}{\partial S_t} \Delta S_t−ΔS$﻿

Approximation Using First Order Taylor Series
Approximating the Residual: We can use the first-order Taylor series to approximate the residual:

$ΔV=\frac{\partial C}{\partial S_t} \Delta S_t−ΔS$﻿

Conclusion

+ The impact of a small change in$S_t$﻿ on this portfolio depends on the values of$ΔS_t$﻿ and the partial derivatives.
+ If the underlying stock price decreases$(ΔS_t<0)$﻿, the short position gains, partially offsetting the loss in the call option.
+ The residual, approximated using the first-order Taylor series, captures the difference between the changes in the call option and the short stock position.

---

Proper Hedge

### STEP 1: INITIAL PORTFOLIO

+ **Equation**:$V_t=C(t)−St$﻿
+ The market maker starts with a long position in a call option _$C(t)$_﻿ and a short position in the stock _$S_t$_﻿.

### STEP 2: FIRST-ORDER APPROXIMATION OF PORTFOLIO CHANGE

1. The change in the portfolio value$ΔV_t$﻿ due to a small change$ΔS_t$﻿ in the stock price is given by:$ΔV_t=C_sΔS_t−ΔS_t$
$ΔV_t=(C_s−1)ΔSt$﻿

---

### **ADJUSTING THE HEDGE**

### STEP 3: ADJUSTING THE SHORT POSITION

3. **Adjusting the Short Position:** To eliminate the risks, the market maker should short$h_{t}$﻿ units of$S_{t}$﻿, where$h_{t}$﻿ is given by:$h_t = \frac{\partial C(S_t, t)}{\partial S_t}$﻿

### STEP 4: NEW PORTFOLIO

1. **New Portfolio:** The new portfolio V_{t} becomes:

$V_{t} = \text{long 1 unit of } C(t); \text{ borrow } C(t) \text{ dollars; short } C_{s} \text{ units of } S_{t}$﻿

---

### **FIRST-ORDER TAYLOR SERIES APPROXIMATION**

### STEP 5: TAYLOR SERIES APPROXIMATION

6. **Taylor Series Approximation:** We approximate$C(S_t+ΔS_t,t)$﻿ using a first-order Taylor series around point S_{t}:

$C(S_t + \Delta S_t, t) = C(S_t, t) + \frac{\partial C(S_t, t)}{\partial S_t} \Delta S_t + R$

### STEP 6: SUBSTITUTE INTO PORTFOLIO CHANGE

$\Delta V_{t} = \left[\frac{\partial C(S_{t}, t)}{\partial S_{t}} \Delta S_{t} + R \right] - \frac{\partial C(S_{t}, t)}{\partial S_{t}} \Delta S_{t}$

$⁍$

---

### **ITO'S LEMMA AND DELTA HEDGING**

### STEP 8: ITO'S LEMMA

1. **Explanation**: The remainder term _R_ is related to Ito's Lemma, and this equation represents the largest term in _R_.

$\frac{1}{2} \frac{\partial^{2} C(S_{t}, t)}{\partial S_{t}^{2}} (\Delta S_{t})^{2}$

---

## 9.4.2 ADJUSTING THE HEDGE OVER TIME

### OBJECTIVE

The objective of this section is to understand how a delta-hedged position needs to be adjusted over time, particularly when the underlying asset$S_t$﻿ oscillates. We aim to explore how these adjustments generate cash gains for the market maker.

### NOTATION AND ASSUMPTIONS

We consider a sequence of time periods$t_0,t_1,…,t_n$﻿ such that$t_i - t_{i-1} = \Delta$﻿. One possible round turn may be$S^{0} \rightarrow\left(S^{0}+\Delta S\right) \rightarrow S^{0} (9.25)$﻿ The underlying asset$S_t$﻿ _oscillates at an annual percentage rate of one standard deviation_ _$\sigma$_﻿ _around an initial point_

$\Delta S = \sigma S^0 \sqrt{\Delta}$

### MECHANICS OF DELTA-HEDGED POSITION

The asset$S_t$﻿can take three possible values:$S^+, S^0, S^−$﻿, where$S^+ = S^0 + \Delta S$﻿ and$S^- = S^0 - \Delta S$﻿

### CASH GAINS FROM OSCILLATIONS

As$S_t$﻿fluctuates, the slope$C_s$﻿of the option price$C(S_t, t)$﻿ also changes. The hedge ratio$h_t$﻿ will change accordingly. When$S_t$﻿ moves, the market maker needs to adjust the short position in$S_t$﻿to keep the portfolio delta-hedged. These adjustments generate cash gains.

$ \left(C_{s}^{+}-C_{s}^{0}\right)\left[\left(S^{0}+\Delta S\right)-S^{0}\right]=\left(C_{s}^{+}-C_{s}^{0}\right) \Delta S$

$\text{Cash Gain} = (C_s^+ - C_s^0) \Delta S$

### 9.4.2.1 LIMITING FORM

As$\Delta S$﻿ approaches zero, the cash gains can be approximated as:

$h_t = \frac{\partial C(S_t, t)}{\partial S_t} = C_s$

$\Delta h_t = h_t' - h_t$

$\frac{C_s' - C_s}{\Delta S} \approx \frac{\partial^2 C(S_t, t)}{\partial S_t^2}$

## 9.4.3 OTHER CASH FLOWS

### COSTS

1. Interest cost for borrowing money:$rC\Delta$﻿
2. Time decay of the option:$\frac{\partial C(S_t, t)}{\partial t} \Delta$﻿
3. Interest earned from the short position:$rS_t C_s \Delta$﻿

## 9.4.4 OPTION GAINS AND LOSSES AS A PDE

### THE BLACK-SCHOLES PDE

$h_t = \frac{\partial C(S_t, t)}{\partial S_t} = C_s$

$\frac{1}{2} C_{ss} \sigma^2 S_t \Delta + r C_s S_t \Delta - r C \Delta = -C_t \Delta$

$\frac{1}{2} C_{ss} \sigma^2 S_t^2 + r C_s S_t - r C = -C_t$

By equating the net cash gains to the daily loss of time value, we obtain the Black-Scholes PDE:

$\frac{1}{2} C_{ss} \sigma^2 S_t^2 + rC_s S_t - rC = -C_t$

With boundary conditions$C(S_T, T) = \max[S_T - K, 0]$﻿

---

The goal is to understand the cash flows from delta hedging a long call position as the underlying price$S_t$﻿ oscillates.

1. We consider a series of time points$t_0, t_1, …, t_n$﻿ separated by$Δ$﻿ time periods.
2. $S_t$﻿ oscillates by$±σS_t^0 \sqrt\Delta$﻿ at each point, where σ is the volatility.
3. As$S_t$﻿ changes, the slope$C_s$and hedge ratio$h_t$﻿ must be rebalanced to maintain delta-neutrality.
4. When$S_t$﻿ increases from$S_t^0$﻿ to$S_t^+$﻿, the hedge ratio$h_t$﻿ decreases, meaning the market maker buys back some shorted shares at the higher$S_t^+$﻿. This generates a trading gain.
5. Conversely, when$S_t$﻿ decreases from$S_t^0$﻿ to$S_t^-, h_t$﻿ increases, meaning more shares are shorted at the lower$S_t^-$﻿. When$S_t$﻿ rebounds to$S_t^0$﻿, a trading gain is generated from covering the extra shorts.
6. The trading gain per roundtrip is approximately:$(C_s^+ - C_s^0)*ΔS$﻿
7. As ΔS → 0, this approaches$$\frac{1}{2} C_{ss} \sigma^2 S_t \Delta + r C_s S_t \Delta - r C \Delta = -C_t \Delta$$

Or per time period:$$\frac{1}{2}C_ssσ^2S_t^2Δ$$

﻿

1. But there are costs to the strategy - interest on the borrowed funds, time decay of the option, and interest earned on the short stock position.
2. The total P&L per Δ is:$$\frac{1}{2}C_ssσ^2S_t^2Δ + rC_sS_tΔ - rC*Δ$$
3. For no arbitrage, this must equal the time decay of the option:$C_t*Δ$
4. Setting these equal and dividing by Δ gives the Black-Scholes PDE:$$\frac{1}{2}C_ssσ^2S_t^2 + rC_sS_t - rC + C_t = 0$$
5. This PDE can be solved with the boundary condition that$C(S_T, T) = max(S_T - K, 0)$to get the Black-Scholes formula.

In summary, the cash flows from dynamically hedging options lead directly to the Black-Scholes PDE, providing an intuitive derivation based on trading and arbitrage.

---

### CALL OPTION PRICING FUNCTION

The call option pricing function is given by:

Where:

+ $S_{t}$﻿: Stock price at time t
+ t: Time
+ r: Risk-free interest rate
+ K: Strike price
+ $\sigma$﻿: Volatility of the underlying asset
+ T: Expiration date

### PARTIAL DERIVATIVES

$\frac{\partial C}{\partial S_{t}}$

$\frac{\partial^{2} C}{\partial S_{t}^{2}}$

$\frac{\partial C}{\partial t}$

$\frac{\partial C}{\partial \sigma}$

$\frac{\partial C}{\partial r}$

### 1. FIRST PARTIAL DERIVATIVE WITH RESPECT TO STOCK PRICE

This derivative is known as Delta ($\Delta$﻿) and represents the rate of change of the option price with respect to the underlying stock price. In other words, it measures how much the option price changes for a one-unit change in the stock price.

Delta helps in hedging by indicating how many shares of the underlying asset need to be bought or sold to offset the risk of price movement.

A high Delta means the option price is highly sensitive to changes in the underlying asset, requiring more attention to hedging.

### 2. SECOND PARTIAL DERIVATIVE WITH RESPECT TO STOCK PRICE

This derivative is known as Gamma ($\Gamma$﻿) and represents the rate of change of Delta with respect to the underlying stock price. It measures the sensitivity of Delta to changes in the stock price.

High Gamma requires frequent adjustments to the Delta hedge, leading to higher transaction costs.

### 3. FIRST PARTIAL DERIVATIVE WITH RESPECT TO TIME

This derivative is known as Theta ($\Theta$﻿) and represents the rate of change of the option price with respect to time. It measures the time decay of the option, showing how the option loses value as it approaches expiration.

### 4. FIRST PARTIAL DERIVATIVE WITH RESPECT TO VOLATILITY

This derivative is known as Vega ($\nu$﻿) and represents the rate of change of the option price with respect to volatility. It measures the sensitivity of the option price to changes in the volatility of the underlying asset.

### 5. FIRST PARTIAL DERIVATIVE WITH RESPECT TO INTEREST RATE

This derivative is known as Rho ($\rho$﻿) and represents the rate of change of the option price with respect to the risk-free interest rate. It measures the sensitivity of the option price to changes in interest rates.

Rho helps in understanding and managing interest rate risk.

A market maker must consider Rho, especially in environments where interest rates are volatile, to hedge against unexpected changes that can affect the option's value.

### **1. CONVEXITY**

### DEFINITION

+ Convexity refers to the shape of the options value curve, where the curve is concave upwards.
+ It represents the second derivative of the option price with respect to the stock price, known as Gamma
+ Convexity ensures that the option's Delta changes in a nonlinear fashion with the underlying stock price.
+ In periods of high volatility, convexity can provide opportunities for profit, as the option's sensitivity to price changes (Delta) increases more rapidly.
+ Convexity allows market makers to create hedging strategies that can benefit from large price swings in the underlying asset.

### **2. TIME VALUE**

### DEFINITION

+ Time value represents the portion of the option's price that exceeds its intrinsic value.
+ It is affected by factors such as time to expiration, volatility, and interest rates.
+ Time value decays as the option approaches expiration (Theta effect), providing opportunities to profit from time decay in certain strategies.
+ The time value is higher for options that are at-the-money (ATM) and decreases for in-the-money (ITM) or out-of-the-money (OTM) options.
+ Market makers can utilize the time value to trade volatility, buying options when volatility is expected to increase and selling when it is expected to decrease.

### **3. CURVATURE**

### DEFINITION

+ Curvature refers to the rate of change of the curve's slope (Gamma) and how it varies along the x-axis (_St_).
+ It describes how the option's sensitivity to price changes (Delta) accelerates or decelerates.
+ Curvature is most pronounced for ATM options, where Gamma is typically highest.

![[WolframAlpha--black_scholes______2023_08_26_19_48.svg]]

![[WolframAlpha--black_scholes______2023_08_26_19_48_(1).svg]]

$\int_{-\infty}^ \frac{(T-t)\left(r+\frac{1}{2} \sigma^{2}\right)+\log \left(\frac{S_{t}}{k}\right)} {\sqrt{(T-t) \sigma}}\frac{1}{\sqrt{2 \pi}} e^{-\left(\frac{1}{2}\right) x^{2}} d x$

> Consider the Black-Scholes formula C(S t,t|r, σ, T, K). How much would this theoretical price change if the underlying asset price, S t, moved by an infinitesimal amount? One theoretical answer to this question can be given by using the partial derivative of the function with respect to S t. This is by definition the delta at time t: delta = ∂C(S t,t|r, σ, T, K) ∂S t

> The partial derivative in equation (79) can be taken in case the call option is European and the price is given by the Black-Scholes formula. Doing so, we obtain the delta of this important special case: ∂C(S t,t|r, σ, T, K) ∂S t = ∫ (T− t)(r + 1 2 σ2) +log(S t /K) √ (T − t)σ −∞ 1 √ 2πe− 1 2 x2 dx (80) = N (d 1)

> We can make some interesting observations: 1. The ATM calls and puts have the same price. 2. Their deltas, however, are different. 3. The calls and puts that are equally far from the ATM have slightly different deltas in absolute value.

> We now point out to some questionable assumptions used in our example. First, in calculatin the deltas for various strikes, we always used the same volatility parameter σ. This is not a trivial point. [Options](Options.md) that are identical in every other aspect, except for their strike K, may have different implied volatilities. There may be a volatility smile. Using the ATM implied

> volatility in calculating the delta of all options may not be the correct procedure. Second, we assumed a zero dividend yield, which is not realistic either. Normally, stocks have positive expected dividend yields and some correction for this should be made when option prices and the relevant Greeks are calculated. A rough way of doing it is to calculate an annual expected percentage dividend yield and subtract it from the risk-free rate r. Third, should we use St or a futures market equivalent, in case this latter exists, the delta evaluated in the futures or forward price may be more desirable.

> Gamma

> Gamma represents the rate of change of the delta as the underlying risk St changes. Changes in delta were seen to play a fundamental role in determining the price of a vanilla option. Hence, gamma is another important Greek. It is given by the second partial derivative of C(St, t) with respect to St: gamma = ∂2C(St, t|r, σ, T, K) ∂S2t

> Gamma shows how much the delta hedge should be adjusted as St changes. F

> Gamma is highest if the option is at-the-money, and approaches zero as the option becomes deep in-the-money or out-of-the-money. We can gain some intuition on the shape of the gamma curve. First, remember that gamma is, in fact, the derivative of delta with respect to St. Second, remember that delta itself had the shape of a cumulative normal distribution. This means that the shape of gamma will be similar to that of a continuous, bell-shaped probability density function,

> The puts and calls with different distance to the ATM strike have gammas that are alike but not exactly symmetric. 2. Gamma is positive if the market maker is long the option; otherwise it is negative. It is also clear from this table that gamma is highest when we are dealing with an ATM option.

> We have seen that long delta exposures can be hedged by going short using the underlying asset. But, how are gamma exposures hedged? Traders sometimes find this quite difficult. Especially in very short-dated, deep out-of-the-money options, gamma can suddenly go from zero to very high values and may cause significant losses (or gains).

> The forex option market was caught short gamma in GBP/EUR last week. The spot rate surged from GBP0.6742 to GBP0.6973 late the previous week, one-month volatilities went up from about 9.6% to roughly 13.3%. This move forced players to cover their gamma. (A typical market quote.) This example shows one way delta and gamma are used by market professionals. Especially in the [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) markets, options of varying moneyness characteristics are labeled according to their delta. For example, consider 25-delta Sterling puts. Given that an at-the-money put has a delta of around 50, these puts are out-of-the-money. Market makers had sold such options and, after hedging their delta exposure, were holding short gamma positions. This meant that as the Sterling-Euro exchange rate fluctuated, hedge adjustments led to higher than expected cash outflows

> Vega

> How much will the value of an option change if the volatility parameter, σ, moves by an infinitesimal amount? This question relates to an option’s sensitivity with respect to implied volatility movements. Vega is obtained by taking the partial derivative of the function with respect to σ:

> Note the resemblance to the gamma

> the vega is greatest when the option is at-the-money. This implies that if we use the ATM option as a vehicle to benefit from oscillations in St, we will also have maximum exposure to movements in the implied volatility.

> Vega is the sensitivity with respect to the percentage volatility parameter, σ, of the option. According to the convention, this is calculated using the Black-Scholes formula. We differentiate the formula with respect to the volatility parameter σ.

> At-the-money options have the largest values of vega. 2. As implied volatility increases, the ATM vega changes marginally, whereas the outof-the-money and in-the-money option vegas do change, and in the same direction.

> Players dumped USD/JPY vol last week in a quiet spot market, causing volatilities to go down further. One player was selling USD1 billion in six-month dollar/yen options in the market. These trades were entered to hedge vega exposure. The drop in the vols forced market makers to hedge exotic trades they had previously sold. According to this reading, some practitioners were long volatility. They had bought options when the dollar-yen exchange rate volatility was higher. They faced vega risk. If implied volatility declined, their position would lose value at a rate depending on the position’s vega. To cover these risky positions, they sold volatility and caused further declines in this latter. The size of vega is useful in determining such risks faced by such long or short volatility positions.

> Vega Hedging Vega is the response of the option value to a change in implied volatility. In a liquid market, option traders quote implied volatility and this latter continuously fluctuates. This means that the value of an existing option position also changes as implied volatility changes. Traders who would like to eliminate this exposure use vega hedging in making their portfolio vega-neutral. Vega hedging in practice involves buying and selling options, since only these instruments have convexity and hence, have vega.

```tikz
\documentclass[tikz,border=10pt]{standalone}
\usepackage{tikz}
\usetikzlibrary{trees,arrows.meta}

\begin{document}
\begin{tikzpicture}
  [grow=right, sloped, 
   level 1/.style={sibling distance=5cm,level distance=3.5cm},
   level 2/.style={sibling distance=2.5cm, level distance=3.5cm},
   level 3/.style={sibling distance=1cm, level distance=3.5cm},
   edge from parent/.style={very thick,draw=blue!40!black!60,
   shorten >=5pt, shorten <=5pt},
   edge from parent path={(\tikzparentnode.east) -- (\tikzchildnode.west)},
   every node/.style={text width=2.5cm, align=center}]

  \node {Start: 10}
    child { node {Up: 15}
      child { node {Up: 20}
        child { node {Up: 25} }
        child { node {Down: 19} }
      }
      child { node {Down: 14}
        child { node {Up: 19} }
        child { node {Down: 13} }
      }
    }
    child { node {Down: 9}
      child { node {Up: 14}
        child { node {Up: 19} }
        child { node {Down: 13} }
      }
      child { node {Down: 8}
        child { node {Up: 13} }
        child { node {Down: 7} }
      }
    };
\end{tikzpicture}
\end{document}
```