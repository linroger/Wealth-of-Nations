---
title: Credit Market Session 2
---

# Credit Market Session 2
## SOVEREIGN BONDS,  ETFS,  CDS AND CDX
1. Sovereign Bonds
	- Sovereign bonds
1. ETFs
	- Fixed Income ETFs
	- Sovereign Bond ETFs
	- Aggregated Cash-Flows method
1. Floating rate bonds
- Floating rate cash-flows
- Financed floating rate bonds
1. CDS and Hazard Rates
- Credit Default Swap specs and cash-flows
- CDS quoting and trading
- Hazard Rate Model
1. CDX Index
- CDX IG,  HY and EM indexes
- Pairs trading using CDX indexes
1. Q&A

What Is Special About Sovereigns?

- Think of a sovereign as a "corporation" … with monopoly on managing resources of an entire state/country.
- Ability to issue "common stock" at will ("printing press" in local currency)
- Legal power to enforce local economic activity & taxation be conducted in local currency (it's own "common stock")
- Central Banks manage supply and value of "common stock" of via interest rates,  QE,  QT,  swaps with other CBs,  etc

## WHY DO GOVERNMENTS ISSUE BONDS IN FOREIGN CURRENCIES?
- When sovereigns need money to fund operations,  they usually issue debt in their own currencies.
- If they struggle to pay off the bonds,  they print more money (diluting the value of the "common stock")
- This can cause inflation,  eroding investors earnings potential.
- A sovereign may issue debt in a foreign currency to calm investor fears of currency devaluation.
- Issuing debt in a foreign currency exposes a nation to exchange rate risk.
 - If the local currency drops in value,  paying down international debt becomes costlier.

## VALUATION AND RISKS OF SOVEREIGN BONDS
- Sovereign Debt Issuers Are Considered
	- Risk-free in local currency (they own the "printing press")
	- Risky for USD and other foreign currencies (cannot print foreign currencies)
- Risk factors: a country's debt-to-GDP ratios,  economic growth prospects,  political risks,  etc
- In default,  sovereigns suspend payment of contractual cash-flows
- There is no bankruptcy/liquidation procedure for sovereign entities
- Defaulted bonds trade at distressed levels,  based on likelihood of recovering the funds sometime in the future
- Sovereign bond investors can try to recover assets abroad,  but it can be tricky …

### SOVEREIGN BOND EXAMPLE: BRAZIL 8.5 2034

![](0c3be445bc5df5265288b1cbca1959da.png)

### SOVEREIGN BOND EXAMPLE: TURKEY 8 2034

![](997b3ca40608c2014fe7a1a3fd543ddc.png)

### SOVEREIGN YIELD/SPREAD CURVES: US VS BRAZIL VS TURKEY

![](9e70288f3e9fe20ea95546120aedee86.png)

### SOVEREIGN BOND EXAMPLE: SRI LANKA 6.85 2024 (DEFAULTED)

![](67d0d32af2d1a4b3f9f7328309201a4b.png)

### SOVEREIGN BOND EXAMPLE: SRI LANKA 6.85 2024 (HISTORICAL PRICES)

![](fba1c25f3bbf70b9ed04f0dc32066cc1.png)

## FIXED INCOME ETFS: 'CREDIT' TRADING AS 'EQUITY'
- Basket of bonds packaged into ETF shares
- ETF basket weights and NAVs published daily
- Major ETF issuers: BlackRock,  StateStreet,  Vanguard,  etc
- Primary Market: enables "in-kind" creation/redemption of ETF shares
- Secondary Market: electronic trading on equity exchanges (NYSE Arca,  NYSE,  NASDAQ,  BATS,  EDGE)
- Efficient way for investors to gain macro exposure to credit markets

### FIXED INCOME ETF EXAMPLE: LQD (MOST LIQUID IG CREDIT ETF)

![](9ded321bfb789c9ea0fb85e496a1adc2.png)

### LQD BASKET COMPOSITION

![](2b810adcf991cbc409cf66532776ecfd.png)

### HISTORICAL PRICES,  YIELDS AND CREDIT SPREADS FOR LQD

![](816438813e93af05e49edfbd4611fc3d.png)

### TOTAL RETURN ANALYSIS FOR LQD (PRICE DYNAMICS + DIVIDENDS)

![](d6720a949b3bf512ce48232a38c2c779.png)

### ETF BASIS (MARKET VS INTRINSIC NAV): LQD

![](c901fb400b6b90494a9de0c24b750ef9.png)

### ETF CREATIONS/REDEMPTIONS & BASIS ARBITRAGE

![](efceee973dc396be71bf138bbfe6773e.png)

## SOVEREIGN BOND ETFS
- ETFs that track a sovereign bond index (monthly re-balancing)
- Coupon payments accumulated over time and paid as monthly dividends
- Principal payments re-invested according to target index weights
- Sovereign bond exposure can be hedged with "CDX EM"

### EXAMPLES
- EMB: tracking JPM USD Emerging Market Bond index
- EMHY: tracking JPM USD Emerging Market HY Bond index

### SOVEREIGN BOND ETF EXAMPLE: EMB ("EMERGING MARKET BONDS")

![](cc842c8750f58b284711a0e1192cb5f2.png)

### EMB COMPOSITION: ~ 600 FIXED RATE SOVEREIGN BONDS

![](6b411421318eb361a5220e75b97c4a86.png)

### COUPON CASH-FLOWS DISTRIBUTED AS MONTHLY DIVIDENDS

![](35ca2592baaeb2735590c0ed8ce8d980.png)

### COMPUTING ETF YIELD AND SPREAD USING ACF METHOD
- Model ETF as "synthetic bond" by aggregating weighted constituent cash-flows
- Discount aggregated cash-flows using flat yield to match the ETF market price (ignoring yield dispersion of individual sovereign issuers)
- Use weighted average "time to maturity" of cash-flows to determine treasury benchmark
- Compute spread to benchmark (to interpolated treasury yield for g-spread)

### ACF CASH-FLOW AGGREGATION EXAMPLE

![](9db36a69fa59f57e2a944e375ce04b56.png)

### YIELD AND SPREAD/YAS CALCULATION FOR EMB ETF

![](a6f90d38491a3a417157909e72ab6f97.png)

## WHY DO CORPORATIONS (SPECIFICALLY BANKS) ISSUE FLOATING RATE BONDS?
- Commercial/other corporate loans are floating rate contracts
- Banks provide commercial loans to corporations and issue floating rate bonds to match the risk exposure
- Banks can swap their fixed rate vs floating rate exposure via interest rate swaps

### EXAMPLES
- Floating rate High Yield senior loans (monthly coupon frequency)
- Floating rate corporate bonds issued by banks/financials (quarterly coupon frequency)

## REFERENCE INTEREST RATES (APRIL 8 2024)
- Federal Funds Target Rate - Lower Bound (currently 5.25%)
- Federal Funds Target Rate - Upper Bound (currently 5.5%)
- Federal Funds Effective Rate (currently 5.33%)
- SOFR - Secured Overnight Financing Rate (currently 5.32%)
- 3M Term SOFR Rate (currently 5.28%)
- 3M US Treasury Rate (currently 5.35%)

### REFERENCE INTEREST RATES: FED FUNDS (E/U/L) AND SOFR

![](d133ba72dfaf28134855de93dfb5b1a3.png)

### HISTORICAL 3M TERM INTEREST RATES: SOFR VS US TREASURIES

![](a3f0f6cfe25568f6785a88edd3bf9f78.png)

### INTEREST RATES CURVES: SOFR VS ACTIVE TREASURY (APRIL 8 2024)

![](669156b14ac5e7a350d93ec6c2483e5a.png)

## COMPOSITION OF FLOATING RATE CASH-FLOWS
- Floating rate cash-flow payments are composed of two parts:
	 - Reference Index Rate part: usually indexed to SOFR,  FedFunds,  LIBOR,  etc
	 - Contractual Spread part: "floating" on the top of the Reference Index rate
- Reference Index Rate gets "fixed"/reset on the coupon frequency schedule
- Coupons determined "on-the-fly",  known on payment date

### FLOATING RATE BOND (SOFR REF INDEX): MORGAN STANLEY

![](e0758e1ce32b0917bb0e306b44c41537.png)

## INVESTING AT RISK-FREE REFERENCE RATES (FEDFUNDS,  SOFR,  LIBOR)

![](0276f0b574ec483e4590525f07aea9b0.png)

## RISKY BOND CASH-FLOWS INDEXED TO REFERENCE RATE

![](27c9ad08687c262d04fd7624a6d3c1df.png)

### FLOATING RATE BOND FINANCED AT REFERENCE INDEX RATE

![](ec66b51af0b7535c5382b3a4d8951fcf.png)

#### FINANCED RISKY FLOATING RATE BOND
- Long position: floating rate bond
 - Short position: finance the cash costs via Reference Index Rate contracts (FedFunds,  SOFR)
- Enables investor to "extract" the company specific credit risk
- Eliminates (most) exposure to interest rates
- Investor receives spread premium payments to maturity (or default time)
- Investor pays loss in case of default (100% - bond recovery value)

### CREDIT DEFAULT SWAP CASH-FLOWS

![](44f40b4572a95169ffdd4abc8d5e4712.png)

- What Is A CDS Contract?
	 - Synthetic swap contract "mimicking" cash-flows of financed floating rate bond
	 - "Insurance" contract linked to an issuer credit default event
	 - Mainly used for hedging long corporate bond positions against credit default risk
- Fixed/Premium Leg details: seller of protection receives spread premiums until maturity (or default)
- Default/Loss Leg details: seller of protection pays the loss in case of default before maturity

## CDS ACCOUNTING CONVENTION
- Seller Of Cds Contract: Investor sells credit default protection
	 - Corresponds to "long risk" position in (financed floating rate) bond
	 - It is a bet on no default occurring before maturity
- Buyer Of Cds Contract: Investor buys credit default protection
	 - Corresponds to "short risk" position in (financed floating rate) bond
	 - It is a bet on default occurring before maturity

## INTERNATIONAL SWAPS AND DERIVATIVES ASSOCIATION (ISDA)
- CDS market regulated by International Swaps and Derivatives Association
- ISDA agreement with PB is needed to enter into CDS contracts
- Provides Standard Model for CDS pricing and risk ("hazard rate model")
- Role of ISDA Committee
	 - Declare when default event occurs for an issuer
	 - Run defaulted bond recovery rate auction / publish CDS recovery rate
	 - Coordinate default settlement of existing CDS contracts

## CREDIT DEFAULT SWAP SPECS AND CASH-FLOWS
### CDS CONTRACT SPECS
- Credit issuer entity
- Rank/seniority: usually Senior Unsecured/SNRFOR
- Currency
- Coupon premium: 100bps for IG,  500bps for HY issuers
- Maturity date: quarterly payments (on IMM dates) to maturity
- ISDA docs: SNAC 2014 XR SR USD
- Reference proxy bond (if available)

## CDS QUOTING AND TRADING CONVENTIONS
- Quotation in spread for IG issuers
- Quotation in "points upfront" for HY issuers
- Quotes converted into "points upfront" for trade settlement (via ISDA Standard Model)
- ISDA Standard Model also provides risk and accrued calcs

### CDSW SCREEN: IBM 5Y CDS (ISDA STD MODEL)

![](b36463269447a35cfd1a317932ebb321.png)

### CDSW SCREEN: FORD MOTOR CREDIT 5Y CDS (ISDA STD MODEL)

![](73bcea226fb0398292c9ef6cce699dfd.png)

### CDS PAR SPREAD CURVES: FORD MOTOR CREDIT (5Y MOST LIQUID)

![](882d831c5336157fe28cb11180948816.png)

### FORD MOTOR CREDIT: CDS SPREADS VS CASH EQUITY (INV)

![](2ea428a01148b6875e4f244bd836d72d.png)

## ISDA CDS STANDARD MODEL

![](c44339cf371373e99b3ace316e2ef32d.png)

### HAZARD RATE MODEL INPUTS
- Contractual cash-flows to maturity
- Calibrated discount factors curve for given Reference Interest Rate (SOFR)
- Expected recover rates given default (by seniority rank)
- "Market implied" survival probability curve … calibrated to standard CDS maturities: 6M,  1Y,  2Y,  3Y,  5Y,  7Y and 10Y
- Hazard rates: local probabilities of default,  can be "computed" from survival probability curves

### SHAPE OF SURVIVAL PROBABILITY CURVES

![](2c6c212036fe6c1859a5da381a7bf48b.png)

### SIMPLE VALUATION FORMULAS (FLAT HAZARD RATE MODEL)

$$PV_{CDS}\left(c,    r,    h,    R,    T\right)=\left[\frac{c-(1-R)\cdot h}{r+h}\right]\cdot\left[1-e^{-T\cdot(r+h)}\right]. \tag{1}$$

$$PV_{Bond}\left(c,    r,    h,    R,    T\right)=1+\left[\frac{c-r-(1-R)\cdot h}{r+h}\right]\cdot\left[1-e^{-T\cdot(r+h)}\right] \tag{2}$$

See next session for details on the Hazard Rate Model

### CDS PV SURFACE (5% FLAT INTEREST RATES,  5% COUPON)

![](3e1035945224c094167ba071f74bb17e.png)

## CDX CONTRACT SPECS
- CDX is an equally weighted index of CDS contracts
- Reference issuers portfolios
	 - CDX IG: top 125 North American Investment Grade CDS issuers (100bps coupon)
	 - CDX HY: top 100 North American High Yield CDS issuers (500bps coupon)
	 - CDX EM: 20 sovereign CDS issuers (100bps coupon)
- Financials are excluded (banks not allowed to trade their own CDS)

### CDX CONTRACT SPECS
- His Markit provides the index composition
- Electronically trading on SEF,  ICE cleared
- CDX indexes roll every 6 months (March and September IMM dates)
- Individual CDS defaults settled in cash after recovery rate auctions
- ISDA docs: SNAC 2014 XR SR USD

### CDX EXAMPLE: IG 5Y SERIES 42

![](5ce116dd693d87abeec7e1c8e090840f.png)

### CDX IG SERIES 42 COMPOSITION: 125 EQUALLY WEIGHTED ISSUERS

![](05184c051d51b459f0d2bebf4f579f6c.png)

### CDX HY 42 COMPOSITION: 100 EQUALLY WEIGHTED ISSUERS

![](094657faeb3f434cd4493d10349b56a7.png)

### CDX EM 41 COMPOSITION: 20 EMERGING MARKET SOVEREIGN ISSUERS

![](9b7f505be3489317fadbb019afe9c7c0.png)

## WHAT DO CDX INDEX SPREADS REPRESENT?
- Level of credit default risk in US Markets (by credit market segment: IG vs HY)
- Level of credit default risk in Emerging Markets (CDX EM)
- CDX is most liquid macro trading/hedging instruments for credit risk!
- High leverage,  with funding advantage (synthetic swap contract)
- Very similar in nature to Options Volatility Index VIX!

### CDX IG 5Y & 10Y SPREADS VS VIX INDEX

![](c172c402493e5ae7ce686efe9d27bc93.png)

### CDX HY 5Y VS JNK AND HYG SPREADS

![](0cb728e5702a7f914aa8a5ca4c61ae85.png)

### CDX EM 5Y VS EMB SPREADS: WHAT COULD CAUSE THE LEVEL DIFFS?

![](d9b073749c285636446438c8750d58b7.png)

## SUMMARY AND Q&A
- Sovereign bonds
- Credit ETFs
- Corporate Sovereign
- Floating rate bonds
- CDS
- CDX Index IG HY EM
- Pairs trading
