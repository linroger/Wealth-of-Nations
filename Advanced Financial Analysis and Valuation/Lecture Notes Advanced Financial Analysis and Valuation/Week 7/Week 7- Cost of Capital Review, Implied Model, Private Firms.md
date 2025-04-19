---
tags:
  - capm
  - cost_of_capital
  - equity_valuation
  - fama_french
  - implied_cost
  - private_firms
aliases:
  - Advanced Financial Analysis
  - Cost of Equity
  - Fama French Model
key_concepts:
  - CAPM model
  - Estimate cost of equity
  - Fama French 3-factor
  - Implied cost of capital
  - Private firm valuation
---

## ADVANCED FINANCIAL ANALYSIS AND VALUATION OF GLOBAL FIRMS

## GAME PLAN
 - Illustration for commonly used approaches to estimate the cost of equity:
	 - CAPM
	 - 3‐Factor Fama French Model
	 - Implied Cost of Capital
 - Two accompanying spreadsheets: Check out Canvas
	 - CAPM and Fama French Model
	 - Implied cost of capital
 - Cost of capital for private firms
	 - Cost of equity
	 - Cost of debt
 - Further reading: Koller et al., Chapter 15
## CAPM FOR MICROSOFT (AT THE END OF 2006)
 - Beta = 0.957 (Estimated using 60‐month history)
	‒ See spreadsheet on Canvas for data and estimation output
##### INPUTS
 - $R_f = 4.7\%$ (10‐yr treasury yield)
 - $(R_m  - R_f) = 6\%$ (based on past history – we will come back to the premium)
 - $E(R) = R_f + \beta*(R_m‐R_f) = 4.7\% + 0.957 \times 6\%$
##### OUTPUT
 - Can compute confidence interval for cost of equity
	 - = $10.44\% +/- 2.33*\sigma*(R_m  - R_f)$
	 - = $10.44\% +/- 2 \times 0.194 \times 6\%$
	 - = $10.44\% +/- 2.33\%   (95\%$ confidence)
See regression output for the standard error of beta estimate
## DOES THE CAPM WORK?

 - CAPM is based on solid theory about the tradeoff between risk and return
	‒ It accounts for the notion of diversification
	‒ Realized returns are extremely noisy and so tests of the CAPM have low power
	‒ Evidence that "conditioning" on current info is part of the issue
		- Betas conditioned on current macro information or time‐varying betas
 - Fama and French evidence:
	‒ Several other factors appear to explain future returns (beyond beta)
 - Potential reason (among many others):
	‒ Other sources of risk beyond single risk factor?
	‒ Maybe small stocks have risk premium? Illiquidity premium?
	‒ Do firms that are near financial distress have higher risk?
	‒ But remember that the "betas" measure exposure to factors (and not the firm
characteristics per se)
 - Extensions of CAPM are largely empirical
	‒ We lack a convincing and accepted new theory

## THE FAMA‐FRENCH 3‐FACTOR MODEL

 - Fama and French, "Common Risk Factors in the Returns on Stocks and Bonds,"
Journal of Financial Economics 1993
 - An empirical "extension" of the CAPM:
	 - $$R_{stock}=R_f+\beta^*(R_m-R_f)+\beta_{SIZE}^*R_{SMB})+\beta^{*}_{BM}(R_{HML})$$
	 - Every stock has different market $\beta,~\beta_{SIZE},~\beta_{BM}$
 - Where do we get $(R_m-R_f),~R_{SMB},~R_{HML}?$
	‒ From WRDS or homepage of Prof. Ken French:
	‒ http://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html

 ![500](8dc839f7c15531100a9525b01c4278bb.png)

## EXAMPLE: 3‐FACTOR COST OF CAPITAL
 - Follow same procedure as CAPM estimates, but include Size and BM in regression:
$$(R_{\mathrm{stock}}-R_{\mathrm{f}})=\alpha+\beta^{*}(R_{\mathrm{m}}-R_{\mathrm{f}})+\beta_{\mathrm{SIZE}}*(R_{\mathrm{SMB}})+\beta_{\mathrm{BM}}*(R_{\mathrm{HML}})$$
 - Microsoft (estimated for 60 months from Dec 2002 to Dec 2006)
	- Market Beta = 0.87 (notice that the beta estimate is different in 3‐factor model)
	- Size Beta = ‐0.24 (Does this make sense?)
	- BM Beta = ‐0.95 (Does this make sense?)
	- Again, see coefficients in spreadsheet on Canvas
 - Calculations using arithmetic averages from previous page:$$R_{\rm stock}=R_{\rm f}+\beta^{*}(R_{\rm m}-R_{\rm f})+\beta_{SIZE}{}^{*}(R_{\rm SMB})+\beta_{\rm BM}{}^{*}(R_{\rm HML})$$$$\begin{aligned}\mathrm{R_{stock}}&=\mathrm{R_f+\beta^*(R_m-R_f)+\beta_{SIZE}}^*(\mathrm{R_{SMB}})+\mathrm{\beta_{BM}}^*(\mathrm{R_{HML}})\\&=4.7\%+0.87^*8.25\%-0.24^*3.79\%-0.95^*5.07\%\\&=6.15\%\end{aligned}$$
- Calculations using Koller averages from previous page: $$R_{stock}=R_{f}+\beta^{*}(R_{m}-R_{f})+\beta_{SIZE}{}^{*}(R_{\rm SMB})+\beta_{BM}{}^{*}(R_{\rm HML})$$ $$\begin{aligned}\mathrm{R_{stock}}&=\mathrm{R_f+\beta^*(R_m-R_f)+\beta_{SIZE}}^*(R_{SMB})+\beta_{BM}^*(R_{HML})\\&=4.7\%+0.87^*5.4\%-0.24^*2.8\%-0.95^*5.0\%\\&=3.98\%\end{aligned}$$

## IMPLIED COST OF CAPITAL
 - Economic (or abnormal earnings) models can be used for reverse engineering to obtain an estimate for the (implied) cost of equity capital
	‒ Could be used for other parameters as well (e.g., implied growth rate)
 - You need to assume that the market prices a firm on average correctly
 - Then, we can use analysts' forecasts about future earnings and growth as a proxy
for the market's expectations
	‒ We use these as inputs and plug them into an abnormal earnings model
	‒ Back out an estimate of cost of equity capital "implied" by the market price
$$\mathrm{P}_{0}=\sum_{t=1}^{\infty}\ \frac{\mathrm{D}_{t}}{\left(1+\mathrm{R}_{\mathrm{e}}\right)^{t}}=\sum_{t=1}^{\infty}\ \frac{\mathrm{NI}_{t}+\mathrm{BVE}_{t-1}-\mathrm{BVE}_{t}}{\left(1+\mathrm{R}_{\mathrm{e}}\right)^{t}}=\mathrm{BVE}_{0}+\sum_{t=1}^{\infty}\ \frac{\mathrm{NI}_{t}-\mathrm{R}_{\mathrm{e}}*\mathrm{BVE}_{t-1}}{\left(1+\mathrm{R}_{\mathrm{e}}\right)^{t}}$$
 - Hail and Leuz (2006) implement for four different models
	‒ Could be used to infer market risk premium (see also Koller et al., Ch. 15)

## EXAMPLE: IMPLIED COST OF CAPITAL
 - Microsoft:
	‒ Book value per share June 2006: $3.99/share
	‒ Earnings per share June 2007: $1.49/share
	‒ Earnings per share June 2008: $1.71/share
	‒ Analysts' 5‐year growth estimate (LTG) = 13.84% (known to be optimistic)
	‒ Dividend payout ratio = 28.2%
	‒ Stock Price at t=0 = $31.05/share
	‒ Different models need different additional ingredients
 - Implied cost of capital = 7.1%, 8.5%, 9.1%, 9.9%
 - Hail and Leuz (2006) show that this model produces very reasonable results for 40 countries around the world
	‒ Cost of capital is higher in countries with weaker institutions
	‒ Effects are more pronounced in less integrated markets
		- Market integration makes it easier for investors to diversify institutional "defects"

# COST OF CAPITAL FOR PRIVATE FIRMS

## COST OF EQUITY
- No Traded Equity Means That We Cannot Directly Estimate Beta
 - Alternative approaches:
	 - 1. Industry or asset betas (basically using traded comparables)
	 - 2. Accounting and fundamental betas

## APPROACH 1
- ‒ Estimate mean (median) "asset beta" (unlevered beta) for public comparables
- ‒ Then, re‐lever to reflect private firm's capital structure
- ‒ Levering betas in private companies is difficult due to the lack of market prices for debt and/or equity
	- Use book value
	- Assume private firm's future leverage ratio eventually resembles the industry average
	- Use a target debt‐to‐equity ratio
##  - **APPROACH 2:** SEE DAMODARAN READING

 ![500](ad2137d571e390994d008d0e6b922de4.png)

 - Note the similarity of asset betas
	‒ Compute median or average by industry and then re‐lever for your firm's capital structure
 - Ideally, try to find publicly traded "pure plays" for this exercise
	‒ If private firm has multiple business lines, do it for each line and compute weighted average beta

## IS BETA FROM PUBLIC FIRM A GOOD PROXY?

 - Who is the marginal investor in public firm?
	‒ Typically, a well‐diversified investor
	‒ In private company, owner has invested most of the wealth in the business
	‒ The owner is exposed to all risk in the firm, and not just the market risk
 - Use total beta for the firm: Divide market $β$ by the square root of $R^2$ (= correlation coefficient with the market): $$\text{Total Beta}=\text{Market beta/ p}_{\mathrm{jm}}$$ ‒ Ex: For a private firm $i$ with a market $β$ of 0.82(from traded comparables) and an average R-squared of 16\%:
$$\mathrm{Market~\beta_{i}~=~\frac{cov(r_{i},r_{m})}{var(r_{m})}=\frac{\sigma_{i}\times\sigma_{m}\times\rho_{im}}{\sigma_{m}^{2}}=\frac{\sigma_{i}\times\rho_{im}}{\sigma_{m}}~\to\frac{Market\beta_{i}}{\rho_{im}}=\frac{\sigma_{i}}{\sigma_{m}}}$$
$$\mathrm{tal~\beta_{i}=\frac{Market~\beta_{i}}{\rho_{im}}=\frac{Market~\beta_{i}}{\sqrt{R-Sq}}=\frac{0.82}{\sqrt{0.16}}=2.05}$$
## ILLUSTRATION: SECURE MAIL SOFTWARE

 ![500](d4e1b4b36c80f3f9775f48f7743a0c0f.png)

- Note that this formula for unlevering the beta assumes that the risk of the debt tax shields equals the risk of the firm (and debt beta is zero)

## ILLUSTRATION: SECURE MAIL SOFTWARE (CONT.)

 ![500](5c9597a04e708666f240566562f8bef9.png)

Cost Of Debt  - Private Companies Rarely Have Publicly Traded Debt

- ‒ If firm does, could use yield from its publicly traded debt or its rating
- ‒ Note that in this case firm is SEC registrant and has to file 10‐Ks
- ‒ If not, try to find yields for its bank or private debt
 - Directionally, one expects the cost of debt to be higher for private firms
	‒ Reason: Access to finance is more limited 

 - Alternative Approaches:
- ‒ Cost of debt for public comparables (plus some adjustment)
- ‒ Recent borrowing: Cost of Debt = Interest Expense/Outstanding Debt
- ‒ Synthetic rating & default spread
	- Estimate an appropriate synthetic rating based on financial ratios

## SYNTHETIC RATINGS AND COST OF DEBT

 ![500](d09ae9c4b32bf544c741ead1f71f3899.png)

 - Steps:
	‒ Compute the interest coverage ratio
	‒ Infer rating based on financial ratio
	‒ Add spread to current yield on long‐term government bond
 - Will share spreadsheet on Canvas
To illustrate:
 - Compute interest coverage ratio
	‒ EBIT (operating income): $132MM
	‒ Interest expense: $39MM
	‒ Interest coverage ratio = EBIT / interest expense = 3.38
 - This CR translates to rating of Ba2/BB and spread of 3.60%
 - With current 10‐year Treasury rate at 0.73% (May 2020), estimated cost of debt is 0.73% + 3.60% = 4.33%

## PROMISED YIELD  IS NOT THE COST OF DEBT
 - For risky debt, cost of debt does not equal the promised yield:
	‒ Is the cost of debt lower or higher?
	‒ Why?
 - Cost of debt is lower!
	‒ Cost of debt is the IRR such that bond price = PV of *expected* future interest and principal payments
	‒ In computing the yield, we use the *promised* payment in the numerator, rather  than the expected payment (which is lower)
	‒ Expected payment
		$= (1-  \text{prob default}) \times  \text{promised payment} +  \text{prob default} \times \text{ payment in default}$
 - For this reason the current (or promised) yield overstates the cost of debt
	‒ This effect increases as debt becomes riskier

## WHAT ARE THE COSTS OF FINANCIAL DISTRESS?
 - Present value of expected costs resulting from risky debt financing
	‒ Includes potential costs to firm as it approaches default and costs if it defaults
	‒ Costs of distress are a reduction in the expected cash flows
 - Examples:  
	- Legal costs after default
	- Decline in employee productivity (job hunting, low morale), turnover
- Customers/suppliers' concerns about potential interruptions/cancellations of warranties, parts, and service
	- Fire‐sale of assets
	- Potential underinvestment (shareholders' unwilling to fund new projects since benefits will accrue to bondholders)
	- Management time spent in discussions with creditors and investment bankers about refinancing and reorganization (instead of running the business)
 - Costs of financial distress likely vary across industries and over time

## HOW HIGH ARE THE COSTS OF FINANCIAL DISTRESS?
 - Upper bound on expected costs of financial distress as a fraction of levered firm value for different leverage ratios L
 - Final column shows upper bound on costs of financial distress at actual industry leverage (1994‐2004)
 - Costs higher in industries with:
	 - Risk of asset fire‐sales
	 - High reliance on human capital
	 - High importance on postsales service, warranties, and parts
-  ![500](dfe93510282e0b1c4e7aa256de597102.png)