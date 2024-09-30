---
title: LECTURE NOTE 2COMPUTING COST OF CAPITAL
aliases: [LECTURE NOTE 2COMPUTING COST OF CAPITAL]
linter-yaml-title-alias: LECTURE NOTE 2COMPUTING COST OF CAPITAL
---
# LECTURE NOTE 2COMPUTING COST OF CAPITAL
## COST OF EQUITY,  COST OF PREFERRED STOCK AND COST OF DEBT

#### OBJECTIVE: INTRODUCE STUDENTS TO THE MECHANICS OF COMPUTING COST OF CAPITAL

## OUTLINE
- Define weighted average cost of capital (WACC)
- Systematic risk Vs. Idiosyncratic Risk
- Risk-return trade-off among major asset classes
- Capital Asset Pricing Model (CAPM) - Estimating cost of equity: risk-free rate,  risk premium,
And adjusted beta.
- Computing cost of debt
- Computing WACC for Smucker.
Cost of Capital

Cost of capital is also variously referred to as opportunity cost of capital,  discount rate,  hurdle rate,  expected return,  and minimum rate of return:

- Cost of debt,  rd.
- Cost of preferred stock,  rp.
- Cost of equity,  re.
- Weighted average cost of capital,  WACC,  which depends on rd,  rp,  and re in the following manner.
$$WACC=r_{e}\, \frac{E}{V}+r_{p}\, \frac{P}{V}+r_{d}\, (1-T_{c})\frac{D}{V} \tag{1a}$$where E,  P,  and D are market values of equity,  preferred stock,  and debt respectively,  V = D+P+E,  and$T_{c}$is the corporate income tax rate. When there is no preferred stock,  P =0,  equation (1 a) simplifies to the familiar:$$WACC=r_{e}\, \frac{E}{V}+r_{d}\, (1-T_{c})\frac{D}{V}\tag{1b}$$

We will discuss how to estimate each element of the WACC formula.
Systematic Risk Vs Idiosyncratic Risk

Systematic risk: Risk of a decline in the value of a stock or portfolio due to market-wide movements or general economic conditions. Example: The decline in NASDAQ and DJIA,  increase in energy prices,  economic slowdown.

Idiosyncratic Risk: Risk of a decline in the value of a stock or portfolio due to firm-specific events such as

- (a) accounting irregularities,
- (b) union problems,
- (c) product defects,  etc.

Which risk is relevant for cost of capital?

- In perfect markets,  theoretically,  only systematic risk should matter in computing cost of capital. This is because idiosyncratic risk should be diversifiable.
- Violations of perfect market assumption (E.g.: employees holding too much of their savings in own company stock and not diversifying) could lead idiosyncratic risk to be
Priced.
- High systematic risk
- High cost of capital.

## ESTIMATING COST OF EQUITY

THERE ARE THREE APPROACHES TO ESTIMATING THE COST OF EQUITY OF A FIRM

1. The Asset Pricing Approach:
	- The Asset Pricing Approach Relies on asset pricing models provided by financial theory. In particular:
		- A) Single factor model: The Capital Asset Pricing Model (CAPM). We will focus only on CAPM.
		- B) Multi-Factor models.
1. The discounted cash flow (DCF) approach: This approach estimates cost of equity as the *internal rate of return* that equates the present value of projected free cash flows to equity (FCFE) to current stock price. The cost of equity estimated from the DCF approach is referred to as the Implied cost of capital
1. An Integrated approach: This approach uses a DCF model to estimate risk premium on the market and then uses this risk premium along with CAPM to estimate cost of equity of the firm.

## WE WILL DISCUSS THE ASSET PRICING APPROACH IN DETAIL NOW

Major [Asset Classes](Asset%20Classes.md) in US: Ibbotson Associates 2012
Yearbook (market results for 1926-2011)

- (1) Large company stocks
	- S&P 500 market index.
- (2) Small company stocks
	- The bottom 20% of the stocks in NYSE by market capitalization plus AMEX and NASDAQ stocks.
- (3) Long-term corporate bonds
	- High grade AAA corporate bonds.
- (4) Long-term and intermediate term US government
	- [Bonds](Bonds.md) (maturity 15 to 30 Years)
- (5) US Treasury bills (1 Month maturity)
- (6) Inflation.

Note: Including data for 2012-2014 does not change the averages much.
 Risk-return staircase: Higher systematic risks,  higher return in the long-run.

## REAL T-BILL RETURN
- The real T-bill return is the nominal T-bill return minus the inflation rate. The arithmetic average real T-bill return over the 1926-2011 sample period is 0.5% per annum. T-bills are good inflation hedge in the long-run!

## MATURITY (TERM) RISK PREMIUM
- (a) Long-term bond prices are more sensitive to interest rate fluctuations than short-term T-bills. This makes long-term bonds more risky for lenders. How?
- (b) The term risk premium is the average return on long-term government bonds minus the average return on 1-month US treasury bills. For the 1926-2011 sample period,  the term risk premium (arithmetic mean) is 2.5% per annum.

## DEFAULT RISK PREMIUM
- (a) Investors in long-term corporate bonds are subject to default risk.
- (b) The default risk premium is the average return on longterm corporate bonds minus the average return on longterm government bonds. For the 1926-2011 sample period,  the default risk premium (arithmetic mean) is 0.3% per annum. Why so low?

## EQUITY RISK PREMIUM

- (a) The equity risk premium is the average return on large company stocks minus the average return on short-term treasury bills,  or long-term government bonds.
- (b) For the 1926-2011 sample period,  the equity risk premium (arithmetic mean) with respect to shortterm treasury bills is 8.2% per annum. The equity risk premium (arithmetic mean) with respect to long-term government bonds is 5.7% per annum.
- (c) Is 6% to 8% range appropriate now?

## SMALL STOCK PREMIUM
- (a) The small stock premium is the average return on small company stocks minus the average return on large company stocks.
- (b) For the 1926-2011 sample period,  the small stock premium (arithmetic mean) is 4.7% per annum.

Arithmetic Mean Vs Geometric Mean Suppose we want to compute the average of annual returns over the last T years.

Arithmetic Mean$$r_{A}=\sum_{t=1}^{T}\frac{r_{t}}{T}\tag{3}$$*Geometric Mean*$$r_{G}=\left[(1+r_{1})\times\left(1+r_{2}\right)\times\cdots\times\left(1+r_{T}\right)\right]^{1/\, T}-1.0\tag{4}$$*Relation between geometric mean and arithmetic mean*$$r_{G}\ \leq\ r_{A}r_{G}\ \approx r_{A}-\frac{{1}}{{2}}\sigma^{2}\tag{5}$$
where$\sigma$is the standard deviation of returns.

- Geometric mean is a better measure of past performance.
- Arithmetic mean is a better guide to expected future performance.

### CAPITAL ASSET PRICING MODEL (CAPM) APPROACH

The cost of capital/expected return of an asset ‘i’ is:
$$E(r_i) = r_f+  \text{"Risk Premium"}$$
$r_f$is the risk-free rate and “Risk Premium” is an appropriate risk premium. CAPM computes the risk premium for the stock/asset as a linear function of the market risk premium:

$$
r_e=r_f+\beta_e\lfloor E(r_m){-r_f}\rfloor 
$$

$r_f =$The risk-free rate of interest.
$E(r_m)-r_f =$The risk-premium on the market index,
$\beta_e =$The beta measures systematic risk. It measures co-movements between the market and the stock.

$\beta_\mathrm{e}>1$,  riskier than the market portfolio.
$\beta_\mathrm{e} < 1, $less risky than the market portfolio.
$\beta_{\mathrm{e} }= 1, $as risky as the market portfolio.
$\beta_{\mathrm{e} }= 0,  \mathrm{riskfree~asset.}$

 Be consistent in choosing risk-free rates and risk premia.
 T-bill yield$\Leftrightarrow$Risk premium based on T-bill returns.
 T-bond yield$\Leftrightarrow$Risk premium based on T-bond returns.

## ESTIMATING THE RISK-FREE RATE

|  | Geometric Mean | Arithmetic Mean |
| ---- | ---- | ---- |
| Risk premium with respect to 1-month T-bills | 6.2% | 8.2% |
| Risk premium with respect to long-term govt. bonds | 4.1% | 5.7% |

Long-term govt. Bonds Estimates based on historical data range from 4.1% to 8.2%.

## FORWARD-LOOKING RISK PREMIUM FROM A THREE-STAGE VALUATION MODEL

![](CleanShot%202024-02-11%20-000347@2x.png)
The monthly risk premium is estimated by first computing an implied cost of capital from a threestage discounted cash flow model and then subtracting the long-term treasury yield. We will discuss the three-stage valuation model used in this paper in the next Lecture.

## MARKET RISK PREMIUM - BOTTOM LINE

- An estimate of between 5 and 6% relative to 30-year bonds seems reasonable.
- For small stocks (less than$1 billion in market cap),  we can add an additional risk premium of up to 3% to the CAPM risk premium.
- Risk premium for small stocks = CAPM risk premium + (a risk premium up to 3%).

## ESTIMATING BETA FROM MONTHLY RETURNS

Beta estimates can be obtained from Yahoo Finance. Yahoo uses 24 to 60 months of data to estimate betas.
http://finance.yahoo.com/q/ks?s=SJM+Key+Statistics

The beta-estimation regression is:$$\text{R}_{\text{it}}=\text{a}+\beta_{\text{raw}}\text{R}_{\text{mt}}+\text{e}_{\text{t}}$$

- R${}_{\text{it}}$is a stock's monthly stock return,
- R${}_{\text{mt}}$is the monthly return on S&P 500 index,  and
- e${}_{\text{t}}$is the idiosyncratic error.
Beta adjustment formula
$$\beta_{\text{adjusted}}=(1/3)\ +(2/3)\ \text{*}\ \beta_{\text{raw}}\tag{6}$$

- This adjustment takes into account mean-reversion in individual stock betas and the noise in estimating them.
- Raw beta is the historical beta. Adjusted beta is the predicted future beta.
- Equation (6) is the forecasting equation estimated from past data. Make sure to do the adjustment when using individual stock betas.
- An alternative is to average the betas of similar firms in the industry. If you have more than 10 stocks,  no need for the adjustment since portfolio betas are less noisy.

## A CHECKLIST FOR USING BETA FROM ONLINE DATA SOURCES

- Is the Beta computed from monthly returns?
	- Use betas computed from daily returns only as a last resort.
	- How does one estimate betas using daily or weekly returns? We use Dimson beta.
	- If it is based on monthly returns,  how many months of data were used? At least 24 months of data is preferable.
- Finally,  has the Beta been adjusted using the adjustment formula given in equation (6)? If not perform the adjustment.

## BETA SOURCES

- Yahoo Finance,  Thomson-Reuters,  Compustat,  Valueline,  Bloomberg all provide betas computed with at least 24 months of data. All these sources use S&P 500 as the market index. Valueline and Bloomberg also provide adjusted betas.

> [!EXAMPLE]
> ### Computing Cost of Equity for Smucker using CAPM
> ## Computing Cost of Equity for Smucker using CAPM
>
> Smucker is in the Processed & Packaged Goods Industry within the Consumer Goods Sector. The unadjusted beta for SMUCKER is (as of July 8,  2022):
>

> Source | Beta
> ---|---
> Yahoo [Finance](Finance.md) | 1.21

>
> Adjusted beta:$\frac{1}{3} + \frac{2}{3} \times 1.21 = 1.14$
> Market Risk Premium = 6%
> Yield on 30-Year T-bond = 2.9%
> Using CAPM: Cost of Equity =$2.9 + 1.14 \times 6 = 9.74\%$.
>
> The market cap for Smucker is$12.98 billion. It is at the higher end of the mid-cap range and lower-end of the large-cap range. It is not a small company. No need to add a small firm premium.

## COST OF DEBT

The cost of debt depends on:

- The current level of interest rates.
- The default risk of the company.
- The seniority and maturity of the particular debt issue.

Long-term debt is usually in the form of coupon bonds. For traded coupon bonds,  the cost of debt is computed as the yield to maturity (IRR) given the current market price.

$$P_{B0} = \sum_{t=1}^{T} \frac{C_t}{(1 + ytm)^t} + \frac{FV}{(1 + ytm)^T} \tag{7}$$

where$C_t$is annual or semi-annual coupon payments. If the coupon payments are semi-annual,  then$T$is 2 times the maturity in years of the bond and$ytm$is the semi-annual yield to maturity.

An easier way to obtain yield to maturity for coupon bonds is to use the yield on a portfolio of bonds with the same bond rating (and same maturity) as the issue under consideration. What is yield to worst?

## COST OF DEBT BASED ON RATINGS

- Obtain the bond rating for all publicly traded bonds of your company from Moody's Bond Record or Standard & Poor's (you can obtain these from BLOOMBERG).
- The current yield to maturity for corporate bonds with a given rating and given maturity can be obtained from http://finance.yahoo.com/bonds/composite_bond_rates
- Note that the yields reported are promised yields computed based on promised cash flows. However,  if the default risk is high,  the expected cash flows from the bond will be lower than the promised cash flows. Thus,  the expected yield (cost of debt) would be lower than the promised yield for bonds with very high default risk,  i.e.,  junk bonds.
- For most high-grade bonds,  the promised yield will be close to the expected yield and,  therefore,  you can just use the promised yield.
- Note that the coupon rate is not the cost of debt. Coupon rate is a historical rate while cost of debt refers to the current yields.

### PRIVATE PLACEMENT DEBT

- The yield on privately placed debt can be based on the ratings of comparable publicly traded bonds (available on Bloomberg). Note that the yield on privately placed debt should,  in general,  be higher than comparable publicly traded debt because the privately placed debt is less liquid. Bank Debt For bank debt (which is not usually traded) we can analogously use the yield on comparable publicly traded bonds. Short-Term Debt Permanent short-term debt should be included in computing cost of debt. For short-term debt and floating-rate debt,  coupon rates are usually good proxies of yield to maturity.

Note: All permanent interest bearing debt should be included in the cost of debt calculations.

### WEIGHTED AVERAGE COST OF DEBT

If you have different kinds of debt then you can compute a weighted average cost of debt (for instance) as follows:$$r_d = \frac{\sum_{i=1}^{M} D_i \times r_{di}}{D} \tag{2}$$
where$D_i$is the market value of the `i`th debt issue, $D$is the sum of market values of all debt, $M$is the number of debt issues and$r_{di}$is the cost of debt for the `i`th issue.

Note 1: Debt should include all permanent interest-bearing debt (including long-term lease liabilities),  which may include floating rate debt and revolving credit lines.

Note 2: Non-interest bearing current liabilities (accounts payable) and non-interest bearing long-term liabilities (such as deferred taxes) should not be included.

Note 3: Capital Leases (long-term leases that are capitalized on the balance sheet) should be included.

## COST OF PREFERRED STOCK

 It is easy to estimate the cost of preferred stock. Preferred stocks have fixed dividend payments with no future growth. Therefore,  the cost of preferred stock, $r_p$,  is given by:$$r_p = \frac{D_p}{P_{p0}} \tag{3}$$where$D_p$is the annual fixed preferred dividend and$P_{p0}$is the market value of preferred stock (we can approximate this with the book value).

>

Note that preferred stock is more risky than debt but less risky than equity. Also,  note that preferred dividends are not tax-deductible.

>

The cost of finite-maturity preferred stock can be computed in the same way we compute *yield to maturity* on a coupon bond.

> [!EXAMPLE]
> ## Computing Weighted Average Cost of Debt for Smucker
>
> The different maturity debt outstanding can be obtained from the footnotes to the financial statements.
> - Market Value = Book Value$\times$Price/100.
> - Ratings are from Moody's where A3 is equivalent to Aby S&P.
> - The weighted average cost of debt is 2.84%.
> - The weighted average coupon rate is 2.79% which is a bit lower than the cost of debt.
>
> Using coupon interest rate could lead to highly erroneous estimates of cost of debt. The coupon rates reflect historical interest rates that existed at the time the debt was issued.
>
> See Worksheet 12 in Smucker-July 2015 version 7.0.xls.
>
> ![](CleanShot%202024-02-11%20-000350@2x.png)
>

> [!EXAMPLE]
> ## Weighted Average Cost of Capital for SMUCKER
> - From page (18),  the cost of equity from CAPM, $r_e = 9.74\%$.
> - Market value of equity as of July 8,  2022 is$12, 979 MM.
> - Book value of interest bearing debt as of July 28,  2014 was about \$6, 171 MM with maturities ranging from 1 year to 30 years.
> - $V = D + E = \$6, 171 + \$12, 979 = \$19, 150 MM..$
> - $D/V = 6, 171/19, 150 = 0.32$, $E/V = 0.68$.
> - Weighted average cost of debt is 2.84%
> - $WACC = 9.74\% \times 0.68 + 2.84\% \times (1-0.34) \times 0.32 = 7.2\%$.
> > (for tax rate we can use a company’s statutory tax rate inclusive of both state and federal taxes of around 38% or the effective tax rate of 34% in 2014).
> - Note: Book value of debt may not always be a good proxy for market value of debt (even for high grade bonds) since interest rates have fallen drastically in the last 5 years.
> - For Smucker,  however,  the ratio of market value of debt to book value of debt is about 1.

