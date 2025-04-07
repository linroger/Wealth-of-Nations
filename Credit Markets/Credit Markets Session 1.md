---
aliases:
- 
- 
tags:
- 
title: Credit Markets Session 1
---
# Credit Markets Session 1
- Course objective: introduce basic concepts on pricing,  trading and portfolio risk management for credit instruments. Discuss credit market segments,  seniority ranks,  instrument types & specs,  quoting conventions,  execution venues and trading protocols
- Understand the valuation of an instrument with default risk
- Focus on:
	 - [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] and loans,
	 - foreign sovereign bonds,
	 - fixed income ETFs,
	 - Credit Default Swaps (CDS) and
	 - CDS Indices
- Good insight into the daily activity of a credit trading desk

# WHAT IS CREDIT DEFAULT RISK?

 ![500](e83ab197f445cef5c27a8c11ae5a3919.png)

# WHEN DOES A COMPANY DEFAULT?

- Issuer default triggered by non-payment of contractual obligation!
- Usually,  caused by missed coupon or principal payment
- In default,  coupon payments are stopped and all liabilities becomes due
- Assets are liquidated and used to pay the debt holders,  based on seniority rank in the capital structure
- Technical/Non-financial default: can lead to accelerated debt repayment and financial default
- See appendix on "structural" vs "reduced form" credit risk modeling approaches

# CREDIT MARKET SEGMENTS
- Investment Grade
	 - low risk of default
- Speculative Grade / High Yield
	 - higher risk of default
- Role of credit rating agencies in assessing issuer default risk
 ![500](41f1460878fe978d3c07cc92d3d99568.png)
# INSTRUMENT TYPES & CONTRACTUAL SPECS CONTRACTUAL SPECS: [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]

- Issuer name
- Issue currency,  price and amount
- Issue maturity
- Seniority rank in capital structure
- Coupon payment type: fixed rate,  floating rate (+ reset index),  variable rate,  etc
- Coupon frequency & day count convention: semi-annual,  30/360,  etc
- Call/Put schedules / embedded optionality: right to exercise call/put options at pre-specified prices
- [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] (positive vs negative,  mostly high yield)
 ![500](8adf926c7b99b2d66bd9490420329665.png)
# INSTRUMENT TYPES & CONTRACTUAL SPECS FIXED RATE IG BOND EXAMPLE: ORACLE

 ![500](d77b21350f5e4d1279ecaff6b0354fda.png)
Instrument types & contractual specs

# FIXED RATE BOND CASH-FLOWS

 ![500](73036b9191c8c1e4cea4fb10478a5299.png)
Instrument types & contractual specs

# FLOATING RATE BOND (SOFR REF INDEX): MORGAN STANLEY

 ![500](ec8418e437fcbfa6ba0afae5d9fc189a.png)
Instrument types & contractual specs

# FLOATING RATE BOND CASH-FLOWS

 ![500](545ba227fa5a360867d223eb91ab6343.png)

## FIXED RATE HY BOND EXAMPLE: AMC

 ![500](da78a73598433db6b0a4c5f587b0feab.png)

## FOREIGN SOVEREIGN BOND EXAMPLE: MEXICO

 ![500](1758a410a6e2b88bd3dabb13670a7303.png)
Instrument types & contractual specs

# FLOATING RATE LOAN EXAMPLE (FIRST LIEN): UNITED AIRLINES

 ![500](583d1159c55fec5c5632d47c450a15e1.png)
Instrument types & contractual specs

# FLOATING RATE LOAN CASH-FLOWS

 ![500](3002a15f421a7d61e0e400da0b298eb5.png)
Instrument types & contractual specs

# PREFERRED PERPETUAL EXAMPLE: MORGAN STANLEY

 ![500](98878c8a473b74952d2ed59d7715d20e.png)

Market Participants: Mostly Institutional Players

- Commercial and investment banks
- Pension funds
- Insurance companies
- Mutual funds
- Various asset managers / ETF issuers
- Hedge funds
- Sovereign funds
- Retail Clients: mostly via ETFs

# QUOTING CONVENTIONS

- Yield: for Investment Grade bonds with maturity < 1 year
- Spread (to Treasury Benchmark Yield): for Investment Grade bonds with maturity > 1 year
- Clean price: for High Yield bonds
- Bonds are fungible and uniquely identified via ISIN/CUSIP codes (market convention),  SEDOL codes,  FIGI codes,  etc.

# SIZE OF THE US CORPORATE BOND MARKET

- USD denominated [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]
- ~100K bonds total ~10K liquid
- Outstanding notional value: ~ 10T USD
- Average daily volume: ~ 40B USD
- Trades sizes smaller than a$100,  000 are viewed as "odd lots".

# SIFMA: FIXED INCOME OUTSTANDING AND NEW ISSUES (2023) IG BONDS LIQUIDITY (SOURCE: MORGAN STANLEY 2023) HEDGING AND RELATED INSTRUMENTS

 ![500](b9678fc69c6540872f5e5a8bab084fba.png)

- US treasuries
- US treasury futures
- Credit Default Swaps
- CDX credit indices
- Fixed income ETFs
 ![500](d1feb0724ae305487f40482ff7403fdb.png)
# TRADING

- ~70% over-the-counter (with broker-dealers)
- ~30% on electronic trading venues
- Trading volume moving gradually from OTC to electronic
	 venues
- US Bond trades reported to FINRA TRACE facility (up to 15 mins delayed)

# TRANSITION FROM OTC TO ELECTRONIC TRADING VENUES

#### MARKET STRUCTURE: OTC/BILATERAL WITH BROKER-DEALERS (70%)

- Brokers provide markets to clients,  e.g. via MSG1 (principal market maker)
- Brokers also act as agents between buyers and sellers
- Negotiation over the Phone / IB Chat
- Bloomberg VCON confirmation
- Electronic connectivity to broker via API
- Bloomberg FIT,  TSOX and BOLT screens
- Single bonds vs Portfolio trading
#### MARKET STRUCTURE: ELECTRONIC VENUES (30%) ORDER EXECUTION PROTOCOLS (VIA FIX)
- RFQ: "Request For Quote" (auction based) vs LOB: "Limit Order Book" (live trading)
- RFQ venues: MarketAxess (80% of electronic volume),
	 TradeWeb,  TrueMid,  etc
- LOB venues: ICEBondPoint,  TradeWebDirect,  TheMuniCenter,  MTSBondPro,  TrueMid,  etc
- Anonymous vs Bilateral trading
- GUI click-trading vs API trading

## BOND CASH-FLOW,  PRICES AND YIELDS

Bond cash-flows,  prices and yields

- Fixed-rate bond cash-flows for maturity$T=T_n$:

$$\{c_i,  T_i\}_{i=1..n},  \quad0\leq t<T_1<…<T_n \tag{1}$$

- Quoting bonds: price to “continuously componded" yield conversion

$$B_t=B(t,  y):=\sum_{i=1}^nc_i\cdot e^{(t-T_i)\cdot y}\tag{2}$$

- Cash-flow weights:

$$w_i=w_i(t,  y):=\frac{c_i\cdot e^{(t-T_i)\cdot y}}{B_t}>0 \tag{3}$$

# BOND CASH-FLOW,  PRICES AND YIELDS BOND VALUATION FORMULAS (0 ACCRUED,  T+0 SETTLE)

Bond valuation formulas (0 accrued,  t+0 settle)

- Bullet fixed-rate bond with semi-annual coupon pct. c and$T$years to maturity:

$$B_0=B(0,  c,  T,  y)=\sum_{k=1}^{2T}\frac c2\cdot e^{-k\cdot\frac y2}+e^{-T\cdot y}\tag{4}$$

 Simple bond price (using geometric series formula):

$$\mathcal{B}_{0}=1+\frac{\frac{\xi}{2}-\left(\mathbf{e}^{\frac{y}{2}}-1\right)}{\mathbf{e}^{\frac{y}{2}}-1}\cdot\left(1-\mathbf{e}^{-T\cdot y}\right).\tag{5}$$

Bullet fixed-rate bond with semi-annual coupon pct.$c$and$T$years to maturity:

$$B_{0}=B(0,  c,  \,  T,  y)=\sum_{k=1}^{2T}\frac{c}{2}\cdot e^{-k\cdot\frac{y}{2}}+e^{-T\cdot y}\tag{4}$$

Using "semi-annual yield":$y_{\text{sa}}=2\cdot\left(\mathbf{e}^{\frac{y}{2}}-1\right)$

$$B_0=1+\frac{c-y_{sa}}{y_{sa}}\cdot\left[1-\left(1+\frac{y_{sa}}2\right)^{-2T}\right]\tag{6}$$

### BOND VALUATION SURFACE (0 ACCRUED,  T+0 SETTLE)

 ![500](b23dd256712e6173f4c764a0110d1921.png)

 ![500](46c53c8593e13c304ca92ae1d091c29e.png)

# COMMENTS

Bond trading at 100% "par" price:$$B_{0}=1\iff c=y_{s a}\iff\left(1+{\frac{c}{2}}\right)$$

New issue pricing (primary market):
pricing "at par" ⇐⇒
"semi-annual coupon" = "semi-annual yield"

- When yield > coupon,  bond trades below par
- When yield < coupon,  bond trades above par
- Bond price is increasing in coupon,  decreasing in yield
## TIME SENSITIVITY: THETA/CARRY = "YIELD"

$$\frac{\partial B}{\partial t}\left(t,  y\right)=\frac{\partial}{\partial t}\left[\sum_{i=1}^{n}c_{i}\cdot e^{\left(t-T_{i}\right)\cdot y}\right]=\sum_{i=1}^{n}c_{i}\cdot\frac{\partial}{\partial t}\left[e^{\left(t-T_{i}\right)\cdot y}\right]\tag{8}$$

$$=\sum_{i=1}^{n}c_{i}\cdot y\cdot e^{\left(t-T_{i}\right)\cdot y}=y\cdot\left[\sum_{i=1}^{n}c_{i}\cdot e^{\left(t-T_{i}\right)\cdot y}\right]=y\cdot B_{t}.$$

$$B\left(t+\Delta t,  y\right)=B\left(t,  y\right)\approx B_{t}\cdot y\cdot\Delta t.\tag{9}$$

## YIELD SENSITIVITY: DURATION/D = "WEIGHTED SUM OF TTMS”

$$\frac{\partial B}{\partial y}=\frac{\partial}{\partial y}\left[\sum_{i=1}^{n}c_{i}\cdot e^{(t-T_{i})\cdot y}\right]=\sum_{i=1}^{n}c_{i}\cdot\frac{\partial}{\partial y}\left[e^{(t-T_{i})\cdot y}\right]\tag{10}$$

$$=\sum_{i=1}^{n}c_{i}\cdot(t-T_{i})\cdot e^{(t-T_{i})\cdot y}=-B_{t}\cdot\sum_{i=1}^{n}\left(\,  T_{i}-t\right)\cdot w_{i}=-B_{t}\cdot D.$$

$$\beta\left(t,  y+\Delta y\right)-\beta\left(t,  y\right)\approx-B_{t}\cdot D\cdot\Delta y.\tag{11}$$$$\frac{\partial B}{\partial y}=\frac{\partial}{\partial y}\left[\sum_{i=1}^{n}c_{i}\cdot e^{(t-T_{i})\cdot y}\right]=\sum_{i=1}^{n}c_{i}\cdot\frac{\partial}{\partial y}\left[e^{(t-T_{i})\cdot y}\right]\tag{10}$$

$$=\sum_{i=1}^{n}c_{i}\cdot(t-T_{i})\cdot e^{(t-T_{i})\cdot y}=-B_{t}\cdot\sum_{i=1}^{n}\left(\ T_{i}-t\right)\cdot w_{i}=-B_{t}\cdot D.B\left(t,  y+\Delta y\right)-B\left(t,  y\right)\approx-B_{t}\cdot D\cdot\Delta y.\tag{11}$$

## YIELD CONVEXITY: GAMMA/ Γ = "WEIGHTED SUM OF SQUARED TTMS"

$$\begin{aligned}&\frac{\partial^2B}{\partial y^2}=\frac{\partial^2}{\partial y^2}\left[\sum_{i=1}^nc_i\cdot\mathrm{e}^{(t-T_i)\cdot y}\right]=\sum_{i=1}^nc_i\cdot\frac{\partial^2}{\partial y^2}\left[\mathrm{e}^{(t-T_i)\cdot y}\right]\quad(12)\\\\&=\sum_{i=1}^nc_i\cdot(T_i-t)^2\cdot\mathrm{e}^{(t-T_i)\cdot y}=B_t\cdot\sum_{i=1}^n\left(T_i-t\right)^2\cdot\mathrm{w}_i=B_t\cdot\Gamma.\\\\&B\left(t,  y+\Delta y\right)-B\left(t,  y\right)\approx B_t\cdot\left[-D\cdot\Delta y+\frac12\cdot\Gamma\cdot\left(\Delta y\right)^2\right].\quad(13)\end{aligned}$$

## SUMMARY OF SENSITIVITIES (YIELD PARAMETRIZATION)

Theta/Carry

$$\begin{array}{l}\mbox{\it Theta}=\frac{\partial B}{\partial t}=y\cdot B_{t}\end{array}\tag{14}$$

"DV01" (-1bp change in yield) and Duration

$$DV01=-\frac{\partial B}{\partial y}=B_{t}\cdot D,  \quad D=\sum_{l=1}^{n}\left(\ T_{l}=t\right)\cdot w_{l}>0\tag{15}$$

Convexity (-1bp change in yield) and Gamma

$$\frac{\partial^{2}B}{\partial y^{2}}=B_{t}\cdot\Gamma,  \quad\Gamma=\sum_{l=1}^{n}\left(T_{l}-t\right)^{2}\cdot w_{l}>0\tag{16}$$

Simple bond price dynamics

$$\begin{align}
dB_t &= dB(t,   y_t) = \frac{\partial B}{\partial t} \cdot dt + \frac{\partial B}{\partial y} \cdot dy_t + \frac{1}{2} \frac{\partial^2 B}{\partial y^2} \cdot \sigma_y^2 \cdot dt,   & (17) \\
&= y \cdot B_t \cdot dt - B_t \cdot D \cdot dy_t + \frac{1}{2} \cdot B_t \cdot \Gamma \cdot \sigma_y^2 \cdot dt. \nonumber \\
\frac{dB_t}{B_t} &= \left( y_t + \frac{1}{2} \cdot \Gamma \cdot \sigma_y^2 \right) \cdot dt - D_t \cdot dy_t. & (18)
\end{align}$$
## BOND PRICE DYNAMICS AND DRIFT COMPONENTS 

Bond Drift Components
$$\mathbb{E}\left[{\frac{d B_{t}}{B_{t}}}\right]$$
$$=y_{t}-D\cdot{\frac{\mathbb{E}\left[d y_{t}\right]}{d t}}+{\frac{1}{2}}$$
$$

\mathbb{E} \left[\frac{dB_t}{B_t} \right] / dt \tag{19}= y_t - D \cdot \mathbb{E} \left[\frac{dy_t}{dt} \right] + \frac{1}{2} \cdot \Gamma \cdot \sigma_y^2

$$
$$\text{``yield''} + \text{``yield curve roll down''} + \text{``yield convexity''}.$$

 ![500](e6c0c03635bd4c405c38cd4fdd5454c5.png)

####    CREDIT SPREADS AND TREASURY BENCHMARKS
- “Treasury benchmark” = US treasury bond with same/similar maturity as the corporate bond
- “Spread to benchmark” = corporate bond yield - treasury benchmark yield
- “G-Spread” = corporate bond yield - interpolated treasury yield
- Credit spreads quantify the risk of credit issuer defaulting to bond maturity
- Spread to benchmark = market convention for quoting IG bonds
 ![500](56def999d8659b9d747c2ad62e48475b.png)

## Z-SPREAD PARAMETRIZATION

- Interest rate curve bootstrapping & risk-free bond valuation
$$ G_t = G(t,   r) \coloneqq \sum_{i=1}^{n} c_i \cdot e^{(t-T_i)\cdot r_i} \tag{20} $$
- Bond price to z-spread conversion

$$ B_t = B(t,   r,   s) \coloneqq \sum_{i=1}^{n} c_i \cdot e^{(t-T_i) \cdot (r_i+s)} \tag{21} $$
- Cash-flow spread weights:

$$ \widetilde{\omega}_i = \widetilde{\omega}_i(t,   r,   s) \coloneqq \frac{c_i \cdot e^{(T_i - t) \cdot (r_i+s)}}{B_t} > 0 \tag{22} $$

## SUMMARY OF BOND SENSITIVITIES (SPREAD PARAMETRIZATION)
- Theta/Carry
$$ \Theta = \frac{\partial B}{\partial t} = B_t \cdot \sum_{i=1}^{n} (r_i + s) \cdot \omega_i \approx B_t \cdot y \tag{23} $$
- "CS01" (-1bp change in spread) and Spread Duration $D$
$$ CS01 = -\frac{\partial B}{\partial s} = B_t \cdot D,   \quad D = \sum_{i=1}^{n} (T_i - t) \cdot \omega_i > 0 \tag{24} $$
- Spread Convexity (-1bp change in spread) and Gamma $\Gamma$
$$ \frac{\partial^2 B}{\partial s^2} = B_t \cdot \Gamma,   \quad \Gamma = \sum_{i=1}^{n} (T_i - t)^2 \cdot \omega_i > 0 \tag{25} $$
## IR-HEDGED BOND PRICE DYNAMICS

$$ \frac{dB_t}{B_t} = \left( s_t + \frac{1}{2} \cdot \Gamma \cdot \sigma_s^2 \right) \cdot dt - D \cdot ds_t \tag{26} $$

$$ \mathbb{E}\left[ \frac{dB_t}{B_t} \right] / dt = s_t - D \cdot \mathbb{E}\left[ \frac{ds_t}{dt} \right] + \frac{1}{2} \cdot \Gamma \cdot \sigma_s^2 \tag{27} $$

$$\text{spread} + \text{spread curve roll down} + \text{spread convexity}$$.
 ![500](14f84088ac66af7dbead4cbf637c79e6.png)

 ![500](e0ccd72d68224fff194d1818e62fa391.png)
## SUMMARY
- Capital structure and credit default events
- Credit ratings
- Credit instruments & contractual spec
- Market participants
- Trading details
- [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]: valuation and risk
- Corporate credit spreads
- Interest rate hedging

# MODELLING APPROACHES: STRUCTURAL VS. REDUCED FORM CREDIT RISK MODELS

## STRUCTURAL CREDIT RISK MODELS

- Introduced by Robert C. Merton (1974),   refined by Black-Cox (1976) and others.
- Equity value represented as call option on company Assets,   using Liabilities as strike
- Issuer default triggered by Assets falling below Liabilities (predictable default time)
- Structural credit risk quantified by solving a Black-Scholes-Merton-type equation.
- Moody's KMV implementation widely used by credit analysts

## REDUCED FORM CREDIT RISK MODELS

- Introduced by Jarrow & Turnbull (1995),   Duffie & Singleton (1999) and others.
- Default driven by exogenous Default Intensity (Hazard Rate) process
- Default occurs without warning (non-predictable default time)
- Dynamics of exogenous default intensity process calibrated to market prices
- No direct connection to company's capital structure