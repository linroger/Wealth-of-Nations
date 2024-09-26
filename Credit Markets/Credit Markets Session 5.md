---
title: CREDIT MARKETS SESSION 5 STRUCTURAL CREDIT MODELS/ CORRELATED DEFAULTS
aliases: [CREDIT MARKETS SESSION 5 STRUCTURAL CREDIT MODELS/ CORRELATED DEFAULTS]
linter-yaml-title-alias: CREDIT MARKETS SESSION 5 STRUCTURAL CREDIT MODELS/ CORRELATED DEFAULTS
---

# CREDIT MARKETS SESSION 5 STRUCTURAL CREDIT MODELS/ CORRELATED DEFAULTS

Dr. Alex Popovici
April 30 2024

1. Financial Mathematics,  University of Chicago alex.popovici@uchicago.edu
1. Senior Quant Trader,  Chicago Trading Company
1. Capital Structure
	- Structural Approach to Credit Default Risk
1. Black-Scholes Model
	1. Recap: Black-Scholes
1. Merton Model
	- Structural Credit Models
	- Fair Value of Equity
	- Fair Value of Risky Bonds
	- Volatility Smiles
1. CS Strategies
	- Capital Structure Strategies
	- Hedging bonds against defaults
1. Correlated Defaults
	- Correlated defaults
1. Cdos
	- Collateralized Debt Obligations
	- Synthetic Cdo Pricing / Base Correlations
1. Q&A

### REMINDER: E OF A CORPORATION STRUCTURAL APPROACH

![500](Z.%20Clippings/Credit%20Markets%20Session%205-20240506035225976.png)
Main idea: model interaction between components of the capital structure of a corporation

- Assets value of corporation modeled by stochastic process $$\left(A_t\right)_{t\geq0},  A_t>0 \tag{1}$$
- Corporate Liabilities are known and denoted by $$\left(K_t\right)_{t\geq0},  K_t\geq0 \tag{2}$$

### BOOK VALUE OF EQUITY AND LEVERAGE
- Leverage $L$ of the corporate capital structure defined as

$$L_t=\frac{Liabilities}{Assets}=\frac{K_t}{A_t}\tag{3}$$

- Leverage can be obtained from corporate balance sheet details
- "Book Value of Equity" defined as "AssetsLiabilities"

$$BVE_t=A_t-K_t=A_t\cdot(1-L_t)\tag{4}$$

- Time horizon for credit default event given by maturity of liabilities

Reminder: Black-Scholes '73 option pricing formulas

- Stock price process $S_t$ follows geometric Brownian motion with constant drift $r$ and volatility $\sigma$ (under risk neutral measure)

$$\frac{dS_t}{S_t}=r\cdot dt+\sigma\cdot dW_t,  S_0>0,  \tag{5}$$

$$S_t=S_0\cdot\exp\left[\left(r-\frac12\sigma^2\right)\cdot t+\sigma\cdot W_t\right].\tag{6}$$

- Stock log-price $S_t$ is normally distributed:

$$\log\left(\frac{S_t}{S_0}\right)\sim\mathcal{N}\left[\left(r-\frac12\sigma^2\right)\cdot t,  \sigma^2\cdot t\right].\tag{7}$$

# REMINDER: BLACK-SCHOLES '73 OPTION PRICING FORMULAS

### EQUATION BREAKDOWN

$$\text{Call} (S_0,   K,   T,   \sigma,   r) = e^{-rT} \cdot \mathbb{E}[(S_T - K)^+ | \mathcal{F}_0]$$

- **$S_0$**: The initial stock price at time $t = 0$.
- **$K$**: The strike price of the option,  i.e.,  the price at which the holder of the option can buy the stock at maturity.
- **$T$**: The time to maturity of the option (in years).
- **$\sigma$**: The volatility of the stock price,  a measure of the amount by which the stock price is expected to fluctuate per year.
- **$r$**: The risk-free interest rate,  representing the time value of money.
- **$\mathbb{E}[(S_T - K)^+ | \mathcal{F}_0]$**: The expected value of the payoff of the call option at maturity,  conditioned on the filtration $\mathcal{F}_0$,  which represents the information available at time $t = 0$.
### PAYOFF FUNCTION

The payoff of a European call option at maturity is given by $(S_T - K)^+$,  where $x^+ = \max(x,   0)$. This means that the holder of the option will exercise it and benefit from the payoff if $S_T > K$ (stock price at maturity exceeds the strike price),  and will let it expire worthless otherwise.

### RISK-NEUTRAL VALUATION

The factor $e^{-rT}$ is used to discount the expected payoff back to present value,  under the risk-neutral measure. In a risk-neutral world,  all investors are assumed to earn at a rate of return equal to the risk-free rate $r$,  regardless of the investment's risk. Thus,  the expected return of holding the stock is also $r$,  and the expected growth rate of the stock under this measure is adjusted accordingly.

### BLACK-SCHOLES FORMULA

The expected value $\mathbb{E}[(S_T - K)^+]$ is calculated under the assumption that the stock price follows a geometric Brownian motion under the risk-neutral measure. This leads to the stock price at time $T$,  $S_T$,  being log-normally distributed with:

$$S_T = S_0 e^{(r - \frac{1}{2} \sigma^2)T + \sigma \sqrt{T} Z}$$

where $Z$ is a standard normal random variable.
The Black-Scholes formula for a European call option can then be expressed as:

$$\text{Call}(S_0,   K,   T,   \sigma,   r) = S_0 N(d_1) - e^{-rT} K N(d_2)$$

where:

- **$N(d)$** is the cumulative distribution function of the standard normal distribution.
- **$d_1 = \frac{\log(S_0/K) + (r + \sigma^2/2)T}{\sigma \sqrt{T}}$**
- **$d_2 = d_1 - \sigma \sqrt{T}$**
This formula results from integrating the payoff function over the probability density function of $S_T$,  using the properties of the log-normal distribution and the properties of stochastic calculus.
- Fair value price of European Call option with maturity T and strike K given by
	- $$= S_0 · \Phi (d_+) - e^{-r T} · K · \Phi (d_-),  \tag{9}$$
	- $$d_\pm = \frac{\log (S_0/K) + (r \pm \frac{1}{2}\sigma^2) · T}{\sigma \cdot \sqrt{T}}\tag{10}$$
- Intuition behind option pricing formulas
	- use risk-neutral measure $$d\tilde{P}$$ and stock-forward measure $$d\tilde{P}_* = \frac{S_T}{S_0 e^{rT}} d\tilde{P}$$

 (via Girsanov transform):

+$$ \begin{align} \text{Call} (S_0,   K,   T,   \sigma,   r) &= e^{-rT} \cdot \mathbb{E} \left[(S_T - K)^+ \mid \mathcal{F}_0 \right] \tag{11} \\ &= e^{-rT} \cdot \mathbb{E} \left[ (S_T - K) \cdot \mathbb{1}_{\{S_T > K\}} \mid \mathcal{F}_0 \right] \\ &= S_0 \cdot \mathbb{E} \left[\frac{S_T}{S_0 e^{rT}} \cdot \mathbb{1}_{\{S_T > K\}} \mid \mathcal{F}_0 \right] - e^{-rT} \cdot K \cdot \mathbb{E} \left[\mathbb{1}_{\{S_T > K\}} \mid \mathcal{F}_0 \right] \\ &= S_0 \cdot \mathbb{P}(S_T > K \mid \mathcal{F}_0) - K \cdot e^{-rT} \cdot \mathbb{P}(S_T > K \mid \mathcal{F}_0) \tag{12} \\ &= S_0 \cdot \Phi (d_+) - e^{-rT} \cdot K \cdot \Phi (d_-) \tag{13} \end{align}$$

- It's all about measuring the event $\{S_T > K\}$ under $\mathbb{P}$ and $\mathbb{P}_*$

## INTUITION BEHIND OPTION DELTA HEDGING
1. **Definition of Delta**:

   $$\Delta_{\text{Call}} (S_0,   K,   T,   \sigma,   r,   t)\tag{14}$$

   $$= \frac{\partial}{\partial S_0} \left\{ e^{-rT} \cdot \mathbb{E} \left[(S_T - K)^+ \mid \mathcal{F}_0 \right] \right\}$$

1. **Interchanging Derivative and Expectation**:

   $$= e^{-rT} \cdot \mathbb{E} \left[\frac{\partial}{\partial S_0} (S_T - K)^+ \mid \mathcal{F}_0 \right]$$

1. **Differentiating the Payoff**:

   $$= e^{-rT} \cdot \mathbb{E} \left[\frac{S_T}{S_0} \cdot \mathbb{1}_{\{S_T > K\}} \mid \mathcal{F}_0 \right]$$

	 - **Explanation** This differentiation assumes $S_T$ is functionally dependent on $S_0$,  which under the Black-Scholes model,  it is. Thus,  $\frac{\partial S_T}{\partial S_0} = \frac{S_T}{S_0}$.
1. **Simplifying to Risk-Neutral Probability**:
   $$= \mathbb{P}(S_T > K \mid \mathcal{F}_0)\tag{15}$$
1. **Final Delta Expression Using Cumulative Normal Distribution**:
$$= \Phi(d_+)\tag{16}$$
   $$ d_1 = \frac{\log(S_0/K) + (r + \frac{1}{2}\sigma^2)T}{\sigma\sqrt{T}}$$
	 - $\Phi$ represents the cumulative distribution function of the standard normal distribution.
### RECOVERING THE MARKET IMPLIED DISTRIBUTION OF $S_T$
- **Implied Distribution Function**:
		- The statement about the implied distribution refers to the model-independent cumulative distribution function $\mathbb{P}(S_T \leq K \mid \mathcal{F}_0)$. This function can be derived by evaluating how market prices of options (both calls and puts) across various strike prices $K$ reflect the cumulative probabilities under the risk-neutral measure. This method involves using the Breeden-Litzenberger identity which expresses that the second derivative of option prices with respect to strike prices provides the density function under the risk-neutral measure.
### RECOVERING THE MARKET IMPLIED DISTRIBUTION OF $S_T$
1. **Intuition behind option delta hedging:**$$\Delta \text{Call} (S_0,   K,   T,   \sigma,   r) = \frac{\partial}{\partial S_0} \left\{ e^{-rT} \mathbb{E}[(S_T - K)^+ \mid \mathcal{F}_0] \right\}$$$$ = e^{-rT} \mathbb{E} \left[\frac{\partial}{\partial S_0} (S_T - K)^+ \mid \mathcal{F}_0 \right]$$$$= e^{-rT} \mathbb{E} \left[\frac{S_T}{S_0} \mathbf{1}_{\{S_T > K\}} \mid \mathcal{F}_0 \right] = \mathbb{P}^* [S_T > K \mid \mathcal{F}_0] = \Phi(d_+)$$
1. **Recovering the market implied distribution of $S_T$:**
   $$\text{Call}(S_0,   K + \Delta K,   \ldots) - \text{Call}(S_0,   K,   \ldots) \approx \frac{\partial}{\partial K} \text{Call}(S_0,   K,   \ldots)$$
   $$= \frac{\partial}{\partial K} \left\{ e^{-rT} \mathbb{E}[(S_T - K)^+ \mid \mathcal{F}_0] \right\} = e^{-rT} \mathbb{E}[\mathbf{1}_{\{S_T \leq K\}} \mid \mathcal{F}_0] = e^{-rT} \mathbb{P}[S_T \leq K \mid \mathcal{F}_0]$$
1. **Credit default event:**
   $$\frac{dA_t}{A_t} = r \,   dt + \sigma_A \,   dW_t,   \quad A_0 > 0$$
   $$A_t = A_0 \exp \left(\left(r - \frac{1}{2} \sigma_A^2 \right) t + \sigma_A W_t \right)$$
$$ \tau = \begin{cases}
   T,   & \text{if } A_T \leq K \\
   \infty,   & \text{if } A_T > K
   \end{cases}$$
4. **Equity Fair Value:**$$E_0 = e^{-rT} \mathbb{E}[(A_T - K)^+ \mid \mathcal{F}_0] = \text{Call}(A_0,   K,   T,   \sigma_A,   r)$$$$= A_0 \Phi(d_+) - e^{-rT} K \Phi(d_-),   \quad d_{\pm} = \frac{\log(A_0/K) + (r \pm \frac{1}{2} \sigma_A^2) T}{\sigma_A \sqrt{T}}$$
+ Is the market implied distribution of $S_T$ log-normal with constant volatility σ? Not really …
### STRUCTURAL CREDIT DEFAULT MODEL: MERTON '74 EXTENSION
+ At time horizon $T$,   the firm has the contractual obligation to liquidate the assets and repay the fixed liabilities $K_T = K$
+ No refinancing of debt is allowed!
+ Credit default triggered if value of assets $A_T$ is below liabilities $K$ (Book Value of Equity < 0) at time horizon $T$
+ Equity investors have limited liability,   so their payout at T is
	+ $$EquityPayout = (BVE_T)^+ = (A_T - K)^+\tag{18}$$
+ Bond investors take over the assets in case of default,   their payout at T is
	+ $$BondPayout = \min (K,   A_T) = A_T - (A_T - K)^+\tag{19}$$
### POSSIBLE PATHS OF ASSET VALUES RELATIVE TO LIABILITIES

![500](Z.%20Clippings/Credit%20Markets%20Session%205-20240506035320204.png)

## CREDIT DEFAULT EVENT
+ Constant interest rates $r$
+ Constant asset volatility $σ_A$
+ Asset value process $A_t$ follows a geometric Brownian motion with drift (under risk neutral measure)
	+ $$\frac{dA_t}{A_t} = r \cdot dt + σ_A \cdot dW_t,   A_0 > 0\tag{20}$$
	+ $$A_t = A_0 \cdot \exp \left[\left(r - \frac{1}{2} \sigma_A^2 \right) \cdot t + σ_A \cdot W_t \right]\tag{21}$$
+ Default time τ is discrete and given by
	+ $$τ = \begin{cases}
        T,   & A_T < K \_T ≥ K
      \end{cases}\tag{22}$$### EQUITY VALUE AS A FUNCTION OF ASSETS AND LIABILITIES

![500](Z.%20Clippings/Credit%20Markets%20Session%205-20240506035424495.png)

### EQUITY FAIR VALUE
+ Fair Value of equity computed from the equity payout function
+ … via Black-Scholes-Merton risk-neutral valuation formula$$
\begin{aligned}
&E_0=e^{-r\cdot T}\cdot\mathrm{E}\left[\left(A_T-K\right)^+\left|\mathcal{F}_0\right]\right.&& (23)  \\
&=Call\left(A_0,  K,  T,  \sigma_A,  r,  \right) \\
&=A_0\cdot\Phi\left(d_+\right)-e^{-r\cdot T}\cdot K\cdot\Phi\left(d_-\right),   \\
&d_{\pm}=\frac{-\log\left(L_{0}\right)+\left(r\pm\frac{1}{2}\sigma_{A}^{2}\right)\cdot T}{\sigma_{A}\cdot\sqrt{T}}&& \text{(24)}
\end{aligned}
$$

![500](Z.%20Clippings/%20Session%205-20240506035532128.png)

# FAIR VALUE OF RISKY BOND / RISKY LIABILITIES
- Computed from risky bond payoff function:
	+$$ \begin{aligned}
B_0=e^{-r\cdot T}\cdot\mathbb{E}\left[\min\left(K,  A_T\right)|\mathcal{F}_0\right]&& \text{(25)}  \\
=e^{-r\cdot T}\cdot\mathbb{E}\left[A_T-\left(A_T-K\right)^+|\mathcal{F}_0\right] \\
=A_0-\left[A_0\cdot\Phi\left(d_+\right)-e^{-r\cdot T}\cdot K\cdot\Phi\left(d_-\right)\right] \\
=A_0\cdot\Phi\left(-d_+\right)+e^{-r\cdot T}\cdot K\cdot\Phi\left(d_-\right).
\end{aligned}$$
- Arbitrage relationship holds (Modigliani-Miller theorem):
	- $$A_0 = B_0 + E_0\tag{26}$$

![500](Z.%20Clippings/Credit%20Markets%20Session%205-20240506035543887.png)

### SURVIVAL AND DEFAULT PROBABILITIES FOR TIME HORIZON $T$
- Survival Probability computed as $$SP(0,  T)=\mathbb{P}\left[\tau>T|\mathcal{F}_0\right]\\=\mathbb{P}\left[A_T>K|\mathcal{F}_0\right]\\=\Phi\left(d_-\right).\tag{27}$$
- Default Probability computed as
$$DP(0,  T)=1-SP(0,  T)=1-\Phi\left(d_-\right)\\=\Phi\left(-d_-\right).\tag{28}$$
### HAZARD RATES AND“DISTANCE TO DEFAULT"
- Flat Hazard Rate computed as

$$h=-\frac1T\cdot\log\left(SP(0,  T)\right)=-\frac1T\cdot\log\left(\Phi\left(d_-\right)\right)\tag{29}$$

- Using KMV "Distance to Default"/DD notation:
$$

\begin{align} DD &= d_{-} \tag{30} \\ DP(0,  T) &= \Phi(-DD) \tag{31} \\ SP(0,  T) &= \Phi(DD) \tag{32} \end{align}

$$
### RISKY BOND YIELD AND CREDIT SPREAD
- Yield of risky bond is given by
$$y_0=-\frac{\log\left(B_0/K\right)}T\tag{33}$$
$$=-\frac1T\cdot\log\left(L_0^{-1}\cdot\Phi\left(-d_+\right)+e^{-r\cdot T}\cdot\Phi\left(d_-\right)\right)$$
- Credit spread of risky bond ("yield-risk free rate")
$$s_0=y_0-r=-\frac1T\cdot\log{(B_0/K)}-r$$
$$=-\frac1T\cdot\log\left(e^{r\cdot T}\cdot L_0^{-1}\cdot\Phi\left(-d_+\right)+\Phi\left(d_-\right)\right)\tag{34}$$

![500](Credit%20Markets%20Session%205-20240508035225840.png)

### EXPECTED RECOVERY RATE GIVEN DEFAULT R
$$

\begin{aligned}
&R=\mathbb{E}\left[\frac{A_T}K|A_T<K,  \mathcal{F}_0\right]&   \\
&=\frac{\mathrm{E}\left[\frac{A_T}K\cdot\mathrm{I}_{\{A_T<K\}}|\mathcal{F}_0\right]}{\mathbb{P}\left[A_T<K|\mathcal{F}_0\right]} \\
&=\frac{A_0}K\cdot\frac{\Phi\left(-d_+\right)}{\Phi\left(-d_-\right)}
\end{aligned}\tag{35}

$$

![500](Credit%20Markets%20Session%205-20240508035457245.png)

## EXPECTED RECOVERY ON DEFAULT EQUITY VS. ASSETS VOLATILITIES
- We apply Ito's lemma to the equity price:
$$\frac{dE_{\rm t}}{E_{\rm t}}=\frac{1}{E_{\rm t}}\cdot\frac{\partial E}{\partial A}\left(A_{\rm t},  K\right)\cdot dA_{\rm t}+…\tag{36}$$
$$=\frac{A_{\rm t}}{E_{\rm t}}\cdot DeltaCall\left(A_{\rm t},  K\right)\cdot\sigma_{A}\cdot dW_{\rm t}+…$$
$$=\frac{A_{\rm t}}{E_{\rm t}}\cdot\Phi\left(d_{+}\right)\cdot\sigma_{A}\cdot dW_{\rm t}+…$$
- Connection between equity vol $\sigma_{E}$ and assets vol $\sigma_{A}$ ($t$ =0):
$$\sigma_{E}=\frac{A_{0}}{E_{0}}\cdot\Phi\left(d_{+}\right)\cdot\sigma_{A}.\tag{37}$$
- Equity volatility $σ_E$ is stochastic,  and inversely correlated to equity price changes!
- ![500](Credit%20Markets%20Session%205-20240508035755242.png)
## EQUITY VOLATILITY SURFACE LEVERAGE EFFECT FOR EQUITY VOLATILITIES

Intuitive explanation: when asset prices change,  equity price and equity volatility move in opposite directions $$\frac{\partial E}{\partial A}=DeltaCall>0\tag{38}$$,
$$\frac{\partial\sigma_{E}}{\partial A}\approx-\frac{L\cdot A}{E^{2}}\cdot DeltaCall\cdot\sigma_{A}<0\tag{39}$$
Correlation between equity price and equity vol changes is negative and dependent on company leverage parameter $L$
Zero-correlation case obtain only for un-leveraged companies only (when Assets = Equity)

## EQUITY OPTION VALUATION

![500](Credit%20Markets%20Session%205-20240508035907209.png)

#### FAIR VALUE OF EQUITY CALL OPTION (STRIKE K AND MATURITY T < T) FAIR VALUE OF EQUITY

$$E_{t}=EquityValue(\,  T)=e^{-r\cdot(\,  T-t)}\cdot\mathbb{E}\left[\left(A_{T}-K\right)^{+}\,  |\mathcal{F}_{t}\right]\tag{40}$$ $$=Call\left(A_{t},  K,  \,  T-t,  \sigma_{A},  r\right).$$
Fair Value of Equity Call derived from payoff function:
$$EquityCall\left(E_{0},  k,  t\right)=e^{-r\cdot t}\cdot\mathbb{E}\left[\left(E_{t}-k\right)^{+}\,  |\mathcal{F}_{0}\right]\tag{41}$$
$$=e^{-r\cdot t}\cdot\mathbb{E}\left[\left(\,  Call\left(A_{t},  K,  \,  T-t,  \sigma_{A},  r,  \,  \right)-k\right)^{+}\,  |\mathcal{F}_{0}\right].$$
Value obtained by 1-dimensional integration of the call function vs the log-normal density of $A_{t}$.

## IMPLIED VOLATILITY SURFACES
- Classic Black-Scholes model assumes constant stock price volatility (flat across strikes and maturities) Implied Volatility Surfaces observed in the market are not flat,  they dexhibit "vol skew" + "vol smile"
- Equity volatilities in the Capital Structure model are stochastic and generate implied vol surfaces similar tones observed in the market
- This is due to:
	- the equity volatility leverage effect (equity down ⇒ vol up) and
	- the "fat tails" of the equity price distribution (caused by non-zero company leverage)
## EQUITY VOLATILITY SURFACE IN STRUCTURAL CREDIT MODEL

![500](Credit%20Markets%20Session%205-20240508040030505.png)

### MODERN CAPITAL STRUCTURE ARBITRAGE MODELS

Inputs

- Term structure of risk-free interest rates
- Detailed assets and (term structure of) liabilities information from the balance sheet of a company
- Equity market prices
- Equity volatility surface

Outputs

- Implied Asset value levels and volatilities (via leverage)
- Model implied probabilities of default tvarious maturities / "Distance tDefault" metrics
- Implied prices for CDS and risky corporate bonds (hazard rate curve)
- Implied prices for convertible bonds
## INVERSE CAPITAL STRUCTURE ARBITRAGE MODELS

Inputs

- Term structure of risk-free interest rates
- Detailed assets and (term structure of) liabilities information from the balance sheet of a company
- Equity market prices
- Market prices for CDS and risky corporate bonds (hazard rate curve)

Outputs

- Implied Asset value levels and volatilities (via leverage)
- Credit Implied equity volatility surface / model implied prices for all equity options
## CAPITAL STRUCTURE ARBITRAGE STRATEGY: MAIN IDEA
- Identify dislocations across the capital structure of a company
- Monetize dislocations via credit vs equity vs options "Capital Structure Arbitrage" trades
- Trade examples
	- Risky bonds & CDS vs equity
	- Risky bond & CDS vs equity options
	- Convertible bonds vs equity & equity options
## HOW CAN WE HEDGE THE AMC 2025 BOND AGAINST DEFAULT?

![500](Credit%20Markets%20Session%205-20240508040339873.png)

# AMC 2025 BOND: IMPLIED VOLATILITY SURFACE

![500](Credit%20Markets%20Session%205-20240508040356751.png)

## AMC 2025 BOND: RECOVERING FROM DISTRESSED LEVELS

![500](Credit%20Markets%20Session%205-20240508040415900.png)

### CAPITAL STRUCTURE ARBITRAGE STRATEGY EXAMPLE
- Buy short-dated AMC 2025 bond with maturity T
- Buy AMC out of the money Put option with strike k and maturity t close to T
- Positive/No Default Scenario PnL analysis
	- bond price increases to 100
	- bond coupons collected until T
	- option price decreases to 0
- Negative/Default Scenario PnL analysis
	- bond price drops to recovery value R
	- option price increases to k
- If equity and vol markets are dislocated from credit markets: we can construct an arbitrage portfolio,  with positive PnL outcomes in both scenarios!
## IDIOSYNCRATIC VS. SYSTEMATIC/MARKET RISKS
- Main idea: decompose the Gaussian risk factors W i driving the company assets Ai into
	- idiosyncratic risk $Z_i$ (specific for company $i$) and
	- systematic/market risk X (common tall companies)
- The portion of systematic/market factor risk in $W^i_t$ (and $A^i_t$) controlled via Gaussian correlation coefficient $ρ^i$:
$$Corr\left(W_{T}^{i},  X\right)=\rho_{i}\in[-1,  1]\tag{42}$$
$$W_{T}^{i}=\sqrt{T}\cdot\left(\sqrt{1-\rho_{i}}\cdot Z^{i}+\rho_{i}\cdot X\right)\tag{43}$$
$$X,  Z_{i}\sim\mathcal{N}\left(0,  1\right),  \ \ X\perp Z_{j},  \ \ Z_{i}\perp Z_{j},  i\neq j\tag{44}$$

#### ASSETS CROSS-CORRELATIONS: VIA COMMON MARKET FACTOR
- Assets become explicitly dependent on the level of the common market factor $X$:
$$A^i_T = A^i_0 \cdot \exp \left(\left(r - \frac{1}{2} \sigma^2_i \right) T + \sigma_i \cdot W^i_T \right)\tag{45}$$
$$= A^i_0 \cdot \exp \left(\left(r - \frac{1}{2} \sigma^2_i \right) T + \sigma_i \cdot \sqrt{T} \cdot (\sqrt{1-\rho_i} \cdot Z^i + \rho_i \cdot X) \right)\tag{46}$$
	- **Cross-correlations between assets $A^i_T$ and $A^j_T$ given by**
$$\text{Corr}(A^i_T,   A^j_T) = \rho_i \cdot \rho_j,   \quad i \neq j\tag{47}$$
	- $A^i_T$ and $A^j_T$ are independent,  conditional on $X$
#### SURVIVAL PROBABILITY FORMULAS
- **Unconditional survival probabilities $p'$:**
$$p' = \mathbb{P}[T_i \geq T] = \mathbb{P}[A^i_T > K_i]\tag{48}$$
$$= \mathbb{P} \left[\frac{W^i_T}{\sqrt{T}} < d'_i \right] = \Phi(d'_i),  \tag{49}$$
$$d'_i = \Phi^{-1}(p')\tag{50}$$
	- **Conditional survival probabilities $p'_x$:**
$$p'_x:= \mathbb{P}[T_i \geq T \mid X = x] = \mathbb{P} \left[\frac{W^i_T}{\sqrt{T}} < d'_i \mid X = x \right]\tag{51}$$
$$= \mathbb{P} \left[\sqrt{1-\rho_i} \cdot Z^i + \rho_i \cdot x < d'_i \mid X = x \right]\tag{52}$$
$$= \mathbb{P} \left[Z^i < \frac{d'_i - \rho_i \cdot x}{\sqrt{1-\rho^2_i}} \right] = \Phi \left(\frac{d'_i - \rho_i \cdot x}{\sqrt{1-\rho^2_i}} \right)\tag{53}$$
## CORRELATED DEFAULTS MEASURING JOINT CREDIT DEFAULTS
- Conditional on $X$,  default times τi are independent,  hence
$$\mathbb{P}\left[\tau_{i}>T,  \tau_{j}>T|X=x\right]=\rho_{x}^{i}\cdot p_{x}^{j}\tag{54}$$
- Joint credit survival/default probabilities ($\varphi=\Phi^{\prime}$):
$$\mathbb{P}\left[\tau_{i}>T,  \tau_{j}>T\right]\tag{55}$$
$$=\int_{-\infty}^{\infty}\mathbb{P}\left[\tau_{i}>T,  \tau_{j}>T|X=x\right]\cdot\varphi\left(x\right)dx\tag{56}$$
$$=\int_{-\infty}^{\infty}\!\!p_{x}^{i}\cdot p_{x}^{j}\cdot\varphi\left(x\right)dx\tag{57}$$
$$= \int_{-\infty}^\infty \Phi \left(\frac{d'_i - \rho_i \cdot x}{\sqrt{1-\rho^2_i}} \right) \cdot \Phi \left(\frac{d'_j - \rho_j \cdot x}{\sqrt{1-\rho^2_j}} \right) \cdot \phi(x) \,   dx\tag{58}$$

## POOLS OF HOMOGENEOUS CREDIT ISSUERS

Simple case: we assume that the underlying pool consists of n homogeneous credit issuers,  i.e. with identical:

- notionals $\frac{1}{n}$,
- "distance to default" coefficients d−,
- recovery rates R,
- market correlations ρ
The total pool loss LT at time T is given by
$$L_{T}=\frac{(1-R)}{n}\cdot\sum_{i=1}^{n}\mathbb{I}_{\{\tau_{i}\leq T\}}\tag{59}$$
## CONDITIONAL CREDIT EVENTS: "K OUT OF N" DEFAULTS
- We are interested in counting the number of defaults in the pool,  conditional on the market factor X
- Conditional default events are independent and Bernoulli distributed
$$\mathbb{I}_{\{\tau_{i}\leq T\}}|X=x\sim\text{Bernoulli}\left(1-p_{x}\right)\tag{60}$$
Therefore,  their sum follows the Binomial distribution
$$\sum_{i=1}^{n}\mathbb{1}_{\{\tau_{i}\leq T\}}|X=x\sim Binomial\left(n-p_{x}\right),  \tag{61}$$
$$\mathbb{P}\left[\sum_{i=1}^{n}\mathbb{1}_{\{\tau_{i}\leq T\}}=k|X=x\right]=\binom{n}{k}\cdot\left(1-p_{x}\right)^{k}\cdot p_{x}^{n-k}\tag{62}$$
## JOINT/CORRELATED CREDIT EVENTS: "K OUT OF N" DEFAULTS
- We are interested in counting the number of defaults in the pool,  as well as the distribution of the pool loss $L_T$ at T
$$\mathbb{P}\left[L_{T}=k\cdot\frac{(1-R)}{n}\right]=\mathbb{P}\left[\sum_{i=1}^{n}\mathbb{I}_{\{\tau_{i}\leq T\}}=k\right]\tag{63}$$
$$=\int_{-\infty}^{\infty}\mathbb{P}\left[\sum_{i=1}^{n}\mathbb{I}_{\{\tau_{i}\leq T\}}=k|X=x\right]\cdot\varphi\left(x\right)dx\tag{64}$$
$$=\int_{-\infty}^{\infty}\binom{n}{k}\cdot p_{x}^{k}\cdot\left(1-p_{x}\right)^{n-k}\cdot\varphi\left(x\right)dx\tag{65}$$
- Therefore,  in the homogeneous case,  the pool loss distribution $L_{T}$ can be computed explicitly… and depends on the Gaussian correlation coefficient ρ!
## LOSS DISTRIBUTION $L_T$ FOR GENERAL (NON-HOMOGENEOUS) POOLS
1. Calibrate "distance to default" coefficients $d^i_{-}$ from market data (from survival probabilities to maturity T)
1. Estimate the level of expected "Recovery Given Default" coefficients $R_i$,  on a 1% discretization grid
1. Estimate the correlation levels ρi of assets Ai with the systematic/market factor X
1. Discretize the distribution of the market factor X on a grid ${{(x_j)}}_{j=1..J}$ _(also works for general,  non-Gaussian X)
1. Compute the conditional distribution of $L_T|x_j$ on a 1% discretization grid,  via numerical "convolution"
1. Aggregate the distribution of LT as a weighted sum of conditional distributions: $∑_j P [X = x_j] · L_T|x_j$
## WHAT IS A COLLATERALIZED DEBT OBLIGATION/CDO?
- A derivative/"structured" credit product linked tan underlying/collateral pool of risky assets
- Example of underlying pool assets:
	- Corporate Bonds,
	- Corporate Loans,
	- Mortgage backed securities/MBS,
	- CDS,  etc
- Underlying pool notional divided into tranches,  corresponding to various level of risk (usually credit rated by rating agencies)
- CDO Tranche cash-flows defined via from underlying pool cash-flows via structural subordination waterfall
- CDO has contractual coupon c and maturity T
## CDX IG INDEX TRANCHE SUMMARY (CDX IG 5Y S41)

![500](Credit%20Markets%20Session%205-20240508042703014.png)

## MORE DETAILS ON CDO TRANCHES
- Each CDO Tranche is characterized by an interval \[a,  d]:
	- a is the attachment point of the tranche,
	- d is the detachment point of the tranche,
	- a and d are expressed in % of the underlying pool notional
- Cumulative portfolicash-flows,  both coupons and losses,  are assigned inttranche cash-flows via "waterfall" logic
- CDO fixed leg pays the contractual coupon c on the outstanding Tranche notional (adjusted for defaults)
- Tranche detachment points are adjusted for realized defaults

### SYNTHETIC CDX IG INDEX TRANCHES
- Uses CDX IG Index as underlying pool
- Each tranche "behaves" like a CDS with dynamic face notional!
	- Equity \[0%,  3%]: highest level of risk (B),  "first pool losses"
	- Mezzanine \[3%,  7%],  intermediate (BBB) risk
	- Senior \[7%,  15%],  senior (AA) level of risk
	- Super-Senior \[15%,  100%],  super-senior (AAA) level of risk
	- Equity + Mezzanine + Senior + Super-Senior = Total Pool
## CREDIT RISK DETAILS FOR UNDERLYING POOL INSTRUMENTS
- Synthetic pool: equally weighted basket of n CDS instruments,  e.g. CDX IG index basket
- Total notional of the pool normalized t1,  i.e. each CDS notional is $\frac{1}{n}$
- CDS issuer default times τi,  i = 1..n CDS issuer expected default recoveries $R_i,   i = 1..n$
- Default Loss Given Default payments are
$$L_{i}=\frac{1}{n}\cdot(1-R_{i})\,  ,  i=1..n\tag{66}$$
## CDO TRANCHES: STRUCTURAL SUBORDINATION "WATERFALL" LOGIC

![500](Credit%20Markets%20Session%205-20240508043040259.png)

### CDO "WATERFALL" LOGIC FOR TRANCHE DEFAULT LEG
- Cumulative losses in the pool at time $t\in[0,  \,  T]$ given by
- $$L_{t}=\frac{1}{n}\cdot\sum_{i=1}^{n}\left(1-R_{i}\right)\mathbb{1}_{\{\tau_{i}\leq t\}},  \,  L_{0}=0\tag{67}$$
- Cumulative losses in the \[a,  d] tranche at time t ∈ \[0,  T]
- $$L_{t}^{[a,  d]}=\left(L_{t}-a\right)^{+}-\left(L_{t}-d\right)^{+}=L_{t}^{[0,  d]}-L_{t}^{[0,  a]}\tag{68}$$
- Notice that $L_{t}^{[a,  d]}\leq t\leq T$ is a discrete jump process paying the portfolio losses within the $[a,  d]$ tranche until maturity $T$
- Maximum loss on \[a,  d] tranche is d − a (tranche "wipe-out")
## CDO "WATERFALL" LOGIC FOR TRANCHE PREMIUM LEG
- Outstanding/non-defaulted \[a,  d] tranche notional at time t
- $${\cal N}_{t}^{[a,  d]}=d-a-L_{t}^{[a,  d]}={\cal N}_{t}^{[0,  d]}-{\cal N}_{t}^{[0,  a]}\tag{69}$$
- Premium leg cash-flow payments for the \[a,  d] tranche occur on (quarterly) cash-flow times ${T_k},   k = 1..K$
- … on the outstanding tranche notional $N^{[a,  d]}_{T_k}$ at time $T_k$: $$C_{k}^{[a,  d]}=c\cdot\Delta\,  T_{k}\cdot N_{T_{k}}^{[a,  d]}=c\cdot\Delta\,  T_{k}\cdot\left(N_{T_{k}}^{[0,  d]}-N_{T_{k}}^{[0,  a]}\right)\tag{70}$$
- Maximum premium leg payment on $[a,  d]$ tranche is $c\cdot\Delta\,  T_{k}\cdot(d-a)$,  minimum payment is 0 (tranche "wipe out")
## CDO \[A,  D] TRANCHE PRICING: PREMIUM LEG

Present Value Of Premium/Fixed Leg Is Given By
$$P V_{C D O\_P L}\left(0\right)=\mathbb{E}\left[\sum_{k=1}^{K}DF(0,  \,  T_{k})\cdot c\cdot\Delta T_{k}\cdot N_{T_{k}}^{[a,  d]}\right].\tag{71}$$
$$=c\cdot\sum_{k=1}^{K}DF(0,  \,  T_{k})\cdot\Delta T_{k}\cdot\mathbb{E}\left[N_{T_{k}}^{[a,  d]}\right]\tag{72}$$ $$=c\cdot\sum_{k=1}^{K}D F(0,  \,  T_{k})\cdot\Delta\,  T_{k}\cdot\left(d-a-\mathrm{{E}}\left[L_{T_{k}}^{[a,  d]}\right]\right)\tag{73}$$

## CDO \[A,  D] TRANCHE PRICING PRESENT VALUE AND PAR SPREAD OF THE \[A,  D] TRANCHE

$$PV_{CDO}\left(0\right)=PV_{CDO\_PL}\left(0\right)-PV_{CDO\_PL}\left(0\right),  \tag{77}$$
$$ParSpread_{CDO}\left(0\right)=c\cdot\frac{PV_{CDO\_PL}\left(0\right)}{PV_{CDO\_PL}\left(0\right)}\tag{78}$$
In practice,  we need to compute the "Expected Tranche Loss" at each premium payment time $\left\{\,  T_{k}\right\}$,  $k=1..K$
$$\mathbb{E}\left[L_{T_{k-1}}^{\left[a,  d\right]}\right]=\mathbb{E}\left[\left(L_{T_{k}}-a\right)^{+}\right]-\mathbb{E}\left[\left(L_{T_{k}}-d\right)^{+}\right]\tag{79}$$
… which can be computed explicitly from the distribution of the pool loss $L_{T_{k}}$

## BASE CORRELATION MODEL FOR QUOTING CDTRANCHES
- Start with a pool of credit issuer and calibrate the "distance to default" coefficients $d^i_{-}$
- For a given Gaussian correlation coefficient ρ,  one can consistently price all CDO equity tranches
- Convert the market prices for mezzanine and senior tranches into "equity equivalent" tranches (tranche linearity)
- Calibrate the "base" tranche correlations ρi matching the prices of "equity equivalent" tranches
- The calibrated "base" correlations are used as market convention for quoting CDO tranches
- Observation: the "base" correlation model for pricing CDOs is not consistent for mezzanine and senior tranches!
## CDOS IN THE GFC (2008-2009) FINANCIAL CRISIS
- During the GFC (2008-2009) financial crisis,  various pools underlying CDO contracts experienced realized defaults In particular,  pools consisting of mortgage and asset backed securities were severely impacted in the real estate crisis
- Synthetic CDOs linked tCDX IG and HY (North America) indices alsexperienced unprecedented default rates
- In many cases,  investors in senior (AA) and super-senior (AAA) tranches were partially wiped out!
- Failures of understanding risks were amplified by the market-wide use of an inconsistent,  non-realistic CDO model:
	- Gaussian correlation models do not cover properly "fat tail" risks/"clustering" of defaults events!
## Q&A
- Assets/Liabilities of a company
- Black-Scholes model
- Capital Structure / Merton model
- Correlated Defaults
- CDO Pricing
- Appendix: First Passage/Black-Cox model
## FIRST PASSAGE TIME CREDIT MODEL: BACK & COX '76
- Model introduces a "default barrier" parameter D
- Barrier D chosen below the liabilities level K,  in order to protect bond investors from excessive losses
- Credit default triggered when assets $A_t$ fall through the liabilities level $K$ and cross the default barrier $D_t$.
- In that case,  equity investors get "wiped out" and the bond holders take over the assets of the company.
- Assets still liquidated at time T to repay the bond investors.
## POSSIBLE PATHS OF ASSET VALUES RELATIVE TO LIABILITIES

![500](Credit%20Markets%20Session%205-20240508043846006.png)

### EQUITY AND BOND INVESTOR'S PAYOUT
- We denote the running minimum of the asset process $A_{t}$ as
- $$A_{t}^{*}=min\left\{A_{s}:0<s<t\right\}\tag{80}$$
- Equity investors payout at $T$ defined as
- $$EquityPayout=\left(A_{T}-K\right)^{+}\cdot\mathbb{1}_{\left\{A_{T}^{*}\geq D\right\}}\tag{81}$$
- Bond investors payout at $T$ is
- $$\begin{array}{l}\mbox{\it BondPayout}=A_{T}-\mbox{\it EquityPayout}\\ =K-(K-A_{T})^{+}+(A_{T}-K)^{+}\cdot\mbox{\rm1}_{\{A_{T}^{*}<D\}}\end{array}\tag{82}$$
## VALUATION: DOWN-AND-OUT BARRIER OPTIONS FORMULAS

### FIRST PASSAGE TIME MODEL: PRICING FORMULAS
- Fair value of equity priced as an down-and-out Call option on the assets value with strike $K$,  barrier $D$ and maturity $T$
- $$E_{0}=e^{-r\cdot T}\cdot\mathbb{E}\left[(A_{T}-K)^{+}\cdot\mathbb{I}_{\{A_{T}^{*}\geq D\}}|\mathcal{F}_{0}\right]\tag{83}$$
- Price is known explicitly in the Black-Scholes framework ("down-an-out" barrier option)
- Fair value of risky bond derived from equity price Fair value of a risky bond higher in "first passage time model" vs. "classical structural model",  due tadditional value from the barrier option