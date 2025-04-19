---
LLM-tagged: 2025-03-10 14:13:25.958000+00:00
tags:
  - cds_spread
  - corporate_risk
  - credit_derivatives
  - credit_risk
  - merton_model
aliases:
  - Credit Derivatives
  - Lecture Notes 9
key_concepts:
  - Corporate Risk Management
  - Credit Default Swaps (CDS)
  - Credit Spread Formula
  - Investment Banking
  - Market Liquidity
  - Notional Amount
  - Protection Buyer/Seller
---

Here is a tagged summary:

**Key Points**

1. **Credit Derivatives Market**: The credit derivatives market skyrocketed in 2000-2008, driven by the proliferation of credit default swaps (CDS).
2. **Single Name CDS**: A single name CDS is an insurance contract where the investor pays interest on a notional amount to the protection seller until maturity or the default of the reference entity.
3. **CDS Spread**: The CDS spread captures important information about the likelihood of survival of individual companies, and can be used to assess credit risk.
4. **Merton's Model**: Merton's model is a mathematical framework for calculating credit spreads, but it is not commonly used in practice due to its complexity and the fact that underlying bonds are not zero-coupon.

**Key Concepts**

1. **Credit Default Swap (CDS)**: A security whose payoff depends on a "credit event", such as default or change in credit rating.
2. **Notional Amount**: The amount on which interest is paid by the protection buyer to the protection seller.
3. **Protection Buyer and Seller**: Two parties that enter into a CDS contract, with the buyer seeking protection against default and the seller selling insurance against default.
4. **Credit Spread Formula**: A formula used to calculate credit spreads, but not commonly used in practice due to its complexity.

**Key Applications**

1. **Corporate Risk Management**: Companies use CDS to manage their assets and liabilities, reducing their exposure to credit risk.
2. **Investment Banking**: Banks use CDS to assess credit risk and price securities.
3. **Market Liquidity**: The CDS market provides liquidity for investors seeking protection against default.

**Key Challenges**

1. **Model Risk**: The complexity of credit models used in the CDS market can lead to errors and biases.
2. **Liquidity Risk**: The lack of liquidity in the CDS market can make it difficult for buyers and sellers to trade.
3. **Counterparty Risk**: The risk that the protection seller will default on their obligations, causing losses for the buyer.

**Key Trends**

1. **Increased Use of CDS**: The use of CDS has increased as companies seek to manage their credit risk.
2. **Growing Importance of Credit Spreads**: Credit spreads have become an important tool for assessing credit risk and pricing securities.
3. **Regulatory Scrutiny**: Regulatory bodies have taken steps to increase oversight and transparency in the CDS market.

---

---
aliases:
- Lecture Notes 9- Corporate Securities And Credit Derivatives.md
- Lecture Notes 9- Corporate Securities And Credit Derivatives.md
- LECTURE NOTES 9 CORPORATE SECURITIES AND CREDIT DERIVATIVES
linter-yaml-title-alias: LECTURE NOTES 9 CORPORATE SECURITIES AND CREDIT DERIVATIVES
tags:
- 
title: LECTURE NOTES 9 CORPORATE SECURITIES AND CREDIT DERIVATIVES
---
# Lecture Notes 9- Corporate Securities And Credit Derivatives

[Teaching Note 8-American Options](Teaching%20Note%208-American%20Options.md)
[Lecture Notes 9ACredit Default Swaps](Lecture%20Notes%209A-%20Credit%20Default%20Swaps.md)

## FINANCIAL INSTRUMENTS TEACHING NOTE 9 CORPORATE SECURITIES AND CREDIT DERIVATIVES

The University of Chicago Booth School of Business

1. The Merton Model
	1. 1.1 Equity and Debt
	1. 1.2 Credit Spreads
	1. 1.3 Relative Pricing
	1. 1.4 Warrants
	1. 1.5 Conflict of Interests between Equity and Bond holders
1. Credit Risk Measurement: The KMV Model
1. Credit Derivatives
	1. 3.1 Credit Default Swaps
## THE MERTON MODEL

- Today is t = 0 and consider a firm with current assets V0.
- Assume the firm's return on assets (ROA) between 0 and T is log-normally distributed.
- That is,  let$\epsilon$∼ N(0,  1),  then
$$V_{T}=V_{0}\times e^{\left(\mu-\frac{1}{2}\sigma^{2}\right)T+\sigma\sqrt{T}\epsilon}$$
- Note that Black & Scholes assumes that equity returns are log-normally distributed. This is not a coincidence.
- The firm finances its operation by issuing both equity and debt. Assume first that the firm issues a zero coupon bond,  whose face value is F and maturity is T.
- There are two possible outcomes for debt holders at maturity T:
- If$V_T > F =⇒$the firm can liquidate some of its assets,  and pay the debt holders.
	- =⇒ Debt holders get F;
	- =⇒ Equity holders get the residual$V_T − F$;
- If$V_T < F$=⇒ the firm will be unable to pay its debt,  and therefore there is default.
	- =⇒ The debt holders take possession of the assets of the firm =⇒ their payoff is$V_T$.
	- =⇒ Equity holders get nothing.

## THE MERTON MODEL 2 DEBT HOLDERS PAYOFF AT T EQUITY HOLDERS PAYOFF AT T THE MERTON MODEL - THE VALUE OF EQUITY

- The payoff to equity holders is then the one of a call option
$$\operatorname*{max}{\big(}V_{T}-F{\big)}$$
- If we denote E0 the value of equity today,  we can apply Black and Scholes formula and obtain
$$E_{0}=\mathrm{Call}\left(V_{0},   F,   r,   T,   \sigma\right)$$
- where Call (V0,  F,  r,  T,  σ) is just Black & Scholes formula
$$\mathrm{Call}\left(V_{0},   F,   r,   T,   \sigma\right)=V_{0}\;N(d_{1})-F\;e^{-r T}\;N(d_{2})$$

$$d_{1}=\frac{\ln\left(\frac{V_{0}}{F}\right)+\left(r+\sigma^{2}/2\right)T}{\sigma\sqrt{T}};\;\;\;\;\;d_{2}=d_{1}-\sigma\sqrt{T}$$

## THE VOLATILITY OF LEVERED EQUITY

- What is the volatility of levered equity?
- We have already investigated the volatility of an option given the volatility of the underlying (see TN 5). Applying the same reasoning,  we obtain
$${\mathrm{Volatility~of~Equity~Returns}}=\sigma_{E}=\left({\frac{V N(d_{1})}{V N(d_{1})-K e^{-r T}N(d_{2})}}\right)\times\sigma$$
- The term in parenthesis is much larger than 1,  implying that equity return volatility is many times higher than the volatility of the underlying assets.
- In addition,  as V decreases,  the parenthesis increases also,  thereby increasing the volatility.
- Since equity E = Call (V,  F) is strictly increasing in V,  we have then that when EV decreases its volatility increases.
	- This is called "Leverage effect" and it was first noticed by Fisher Black.
- =⇒ The model generates time varying volatility correlated with the value of equity: When equity drop,  volatility increases.
 ![500](12cfba8371.png)
## THE MERTON MODEL - THE VALUE OF DEBT
- What is the value of defaultable debt in the model? - The payoff to debt holders is
$$\operatorname*{min}\left(V_{T},   F\right)=V_{T}-\operatorname*{max}\left(V_{T}-F\right)$$
- The value today of this payoff is then
$$D_{0}=V_{0}-E_{0}=V_{0}-C a l l(V_{0},   F,   r,   T,   \sigma)$$
- Note that this expression also comes immediately from the balance sheet identity

## ASSETS OF A FIRM = DEBT + EQUITY
- Exploiting put call parity,  we can express the value of debt alternatively,  and more intuitively,  as$$D_{0}=Fe^{-r\times T}-Put(V_{0},   F,   r,   T,   \sigma)$$The value of debt is equal to the risk free debt$Fe^{-rT}$minus a put option,  representing the (risk adjusted) expected losses due to the possibility that risky assets will not be sufficient to pay the debt at maturity.
## CREDIT SPREADS UNDER THE MERTON MODEL
- We can then use the Merton's model to compute a corporate bond credit spread.
- From the definition of yield to maturity$y$for a corporate bond,  we have the equality$$D_{0}=e^{-y\times T}\times F\quad\implies\quad Fe^{-r\times T}-Put(V_{0},   F,   r,   T,   \sigma)=e^{-y\times T}F$$
- which implies
$$e^{-r\times T}-P u t\left(\frac{V_{0}}{F},   r,   T,   \sigma\right)=e^{-y\times T}1-e^{r\times T}\times P u t\left(\frac{V_{0}}{F},   r,   T,   \sigma\right)=e^{-(y-r)\times T}$$
- and finally
$$\mathrm{Credit~Spread}=y-r=-{\frac{1}{T}}l o g\left[1-e^{r\times T}P u t\left({\frac{V_{0}}{F}},   r,   T,   \sigma\right)\right]$$

## CREDIT SPREADS UNDER THE MERTON MODEL

 ![500](09041a570db092105c83be0bc0ac774a.png)

- Issues:
	- (A) They are small;
	- (B) They converge to zero at T → 0

## THE MERTON MODEL - EXTENSIONS

- Many extensions of this basic model exist,  including
- Coupon bonds: The debt is not zero-coupon; - Stochastic interest rates: Interest rates follow one of the processes we have seen.
- Early Bankruptcy: There is a lower bound Vb to assets so that if V (t) < Vb the firm is
bankrupt.
- Unobservable V (t): Investors may only rely on accounting measures to estimate V (t): The
default barrier could be closer than you think.
- The Merton's model can be used also for relative pricing across different bond classes of the
same issuer.
- For example,  suppose that a firm issues two bonds: one senior and one junior debt,  with face
value FJ and FS.
- At maturity,  we have the following payoff
$$
\begin{array}{c|c|c|c}&0<V_T<F_S&F_S<V_T<F_S+F_J&F_S+F_J<V_T\\\hline\text{Senior}&V_T&F_S&F_S\\\text{Junior}&0&V_T-F_S&F_J\\\text{Equity}&0&0&V_T-(F_S+F_J)\\\hline\end{array}
$$

- That is,  senior and junior debt and equity must satisfy
	- Payoff of Senior Debt =$V − max (V − F_S,    0)$
	- Payoff of Junior Debt =$max (V − F_S,    0) − max (V − (F_S + F-J),    0)$
	- Payoff of Equity =$max (V − (F_S + F_J),    0)$
- We have then have
$$\begin{aligned}D_{S}~&=~V-BSC\left(V,   F_S,   r,   T,   \sigma\right)\\D_{J}~&=~BSC\left(V,   F_S,   r,   T,   \sigma\right)-BSC\left(V,   F_S+F_J,   r,   T,   \sigma\right)\\E_0~&=~BSC\left(V,   F_S+F_J,   r,   T,   \sigma\right)\end{aligned}$$
- Next Figure plots$D_{J}\mathrm{~and~}D_{S}\mathrm{~when~}F_S=F_J=100.$

## RELATIVE PRICING OF JUNIOR AND SENIOR DEBT

 ![500](7935c5954a066958614775deb9b08ecb.png)

- Given these relationships,  we can also look at the relationship between$D_J$and$D_S$
-  ![500](30a7c497b3d3ab02dc13c8491d0c237a.png)
- This gives a measure of how Senior and Junior debt should be related.
- It could help spotting misallignments of the two debt values.

## WARRANTS

- Warrants are options issued by the firm on its own stock
- The holder of the warrant has the right,  but not the obligation,  to purchase a given number$m$of shares from the firm at the given strike price K at maturity T.
- The firm may issue new shares to make whole to the warrant holder,  which generates a dilution effect on the total value of equity,  as the firm is selling shares at a lower value than they are worth.
- Example: Consider a whole equity firm with n shares outstanding,  and total value of assetsequal to V.
	- If the warrant-holders exercise the warrant,  they pay K per share and receive m shares.
	- After the exercise of the warrant,  the firm's assets are VT + m × K.
	- Therefore,  the exercised warrants are worth
$$\text{Value of 1 Share{\it  after }Exercise}-K=\frac{V_{T}+m\times K}{n+m}-K=\frac{n}{n+m}\left(\frac{V_{T}}{n}-K\right)$$
- The term$V_{T}/n$is the value of one share without the warrants. The term$n/(n+m)$is called "dilution adjustment".
- Thus:$$\text{Value of warrants}=\frac{n}{n+m}BSC\left(\frac{V_{0}}{n},   K,   r,   \sigma,   T\right)$$

## BOND AND EQUITY HOLDERS' CONFLICTS OF INTEREST

- The Merton's model is at the basis of the agency theory of the firm,  in which there is a natural
conflict between equity holders and debt holders.
#### 1. VOLATILITY
- Equity holders are long a call option =⇒ They like volatility and thus risky projects.
- Bond holders are short the call option =⇒ They dislike volatility.
#### 2. DIVIDENDS
- Equity holders are long a call option =⇒ They like dividend payments
	- The decrease in value of equity is less than the dollar amount received in dividends.
	- Intuition: The Delta of equity is less than 1,  ∆ = N(d1) < 1,  =⇒$1 dollar decrease in assets V implies less than$1 decrease in equity.
- Example: A firm has V =$10bil,    F =$10bil,  T = 5,  r = 2%,  σ = 10%. Then$E_0$=$1.4066 bil.
	- If the firm makes a cash dividend payment of$1 bil =⇒ V = 9 =⇒ E0 = 0.7794 =⇒ Equity lost 0.6272 bil in equity value,  but got the 1 bil cash.
	- Where is this money coming from?
- The value of bonds must have gone down by the same amount =⇒ Bondholders dislike dividend payments.
- =⇒ If there are monitoring costs to check what equity holders do,  bondholders require a higher premium because they take into account the incentive of equity holders to maximize their value.
- Unusual dividend payments can be taken care through bond covenants. But the choice of risky/safe projects is harder.

## LEVERAGED FIRMS AND DEBT OVERHANG

- During crisis periods,  such at the 2007/08 crisis,  it is hard for firms to raise new equity capital.
- Why?
	- For highly levered firms,  injecting capital into the firm implies a direct transfer of value from equity holders to debt holders.
	- This effect is called "debt overhang"
- Example: A firm has V = 9 bil,  F = 10 bil,  T = 5 years,  σ =,  r =.
	- =⇒ E0 =$0.7793 and D0 = 8.2206.
- Suppose the firm issue shares and raises$1 bil in cash.
	- The value of assets is now V = 10 bil. Given that the face value of debt did not change,  what is the value of equity and debt?
		- =⇒ E0 = 1.4066 and D0 = 8.59337.
		- Equity increased by only$0.6272 billion but they put$1 billion.
		- The value of bonds increased by$0.3728
	- Of course,  the intuition is the same as for dividend cash payments: The Delta of the option is less than 1.
- How can we compute the probability of default of a particular bond or entity?
- Credit rating agencies provide credit rating to bonds,  which provide (their) assessment of their probability of default.
- For instance,  the following table is from Standard and Poor. This is called the transition matrix
	-  ![500](97d8406b7652c7fe3d3c5b719077d097.png)
- For instance,  a BBB rated company has a probability % to move to AAA,  % to AA,  6.5% to A,  84.27% to remain at BBB,  6% to move to BB,  etc.

## CREDIT RISK MEASUREMENT: KMV
- KMV argues that credit ratings did not tell the whole story (they said so way before the crisis).
	- e.g. Bonds in the same credit rating class show different probabilities of default
- They use Merton’s model to compute the probabilities of default:
 ![500](c399d2f24f626a4be0e259a5964c585c.png)

- More specifically,  they obtain
	- Expected Default Frequency (EDF)$=$$p_{T}=\Pr\left[V_{T}<F|V_{0}\right]=N\left(-d_{2}\right)$

Distance to Default (DD)$=$$d_{2}=\dfrac{\ln\left(\dfrac{V_{0}}{F}\right)+\left(\mu-\sigma^{2}/2\right)T}{\sigma\sqrt{T}}$

- What are the unknowns?
	1. $V_0$: as book values of assets are unreliable;
	1. σ: the volatility of assets
	1. F: The default point.
- They find empirically that F = Short Term Debt + 1/2 Long Term Debt works well.
- The last two items are V0 and σ.
- What can we observe about a firm?
	- The market value of equity;
	- The volatility of equity.
- From the Black Scholes formula for equity we obtained earlier
$$E_{0}=\mathrm{Call}(V_{0},   K,   T,   r,   \delta,   \sigma)=N\left(d_{1}\right)V_{0}-K e^{-r(T-t)}N\left(d_{2}\right)$$
- Note that here we may use a different K,  as the horizon is different
- From here,  we can also compute the volatility of equity$$\sigma_{E}\ =\ N\left(d_{1}\right)\left(\frac{V_{0}}{E_{0}}\right)\sigma$$
- Therefore,  we set
$$E_{0}~=~\mathrm{Market~Value~of~Equity};~~~~\sigma_{E}=\mathrm{Volatility~of~Equity}$$
- We solve two equations in the two unknown$V_0$and σ.
- Simple Example (KMV model is much more elaborate):
	- Enron market capitalization on May 30 1989 was 2.260 bil (from CRSP).
	- The book value of debt = 3.249 bil (prospectus).
	- Volatility of equity return = 20%.
	- The nominal one year interest rate was 8.6% (continuously compounded).
	- Assume T = 8 years (long term debt).
- Next two figures plot the value of equity and volatility of equity implied by the Merton model for various levels of current assets V0 and volatility σ

## CREDIT RISK MEASUREMENT: KMV

 ![500](e6964bd1fc5825a9c507639f437ad4f8.png)

-  ![500](c2f02f6519e277b3f01ebe8463b5f7c6.png)
- The plot shows a combination of$V_0$and σ that equates the model equity value to the market equity capitalization of 2.26 bil.
-  ![500](f4fe746eb4ef8aa3fef7ddffcb156422.png)
- We therefore find$V_0$= 3.84 bil and σ = 12%.
- We finally use these quantities to compute the distance to default and the expected frequency of default.
	- We need one more input: the growth rate of assets µ.
	- This must be forecasted from fundamentals. Assume µ = 15%. We find:
$$d_{2}=2.69\quad\mathrm{~and~}\quad p_{T}=36\mathrm{bp}$$
- According to the transition table at the end of the case,  a BBB company has 45 bp chance of defaulting.
	- KMV argues that the normal distribution is imperfect,  especially because of the thin tails.
	- So,  they define a new map from distance to default and expected default frequency,  which is estimated from data.
	-  ![500](6d3e1a0868c56050cc916995d8e68255.png)
	- For$d_2 = 2.69$it looks on target.
## THE CREDIT DERIVATIVES MARKET

- Credit derivatives are securities whose payoff depend on a "credit event"
- The credit event could be "default,  " change in the credit rating of the issuer,  or change in credit spreads.
- The credit derivatives market skyrocketed in the 2000 - 2008 period.
 ![500](593a5e60298e50f161ea6a9ef817db3f.png)

 ![500](03e894c42fb4dfe8b25ca5b815cdb84d.png)

d highly esoream market nk loan mand its base of companies,  credit derivavey. This surend of 2002,  showed that 40.1% of all reference entities

## CREDIT DERIVATIVES

- Definition of Default: Any non-compliance with the exact specification of a contract.
- The contracts generally involve three parties:
	1. The issuer of the underlying risky security (bond)
	1. The investor who bought the security and wants protection (protection buyer)
	1. A counterparty who is willing to sell protection (protection seller)
- The credit derivative exchange only involves the protection buyer and seller.
- The original issuer is just "the reference entity" over which the credit derivative contract is determined.

## SINGLE NAME CREDIT DEFAULT SWAP

 ![500](5df13b2d7b16aa00bbef78b12c162fd9.png)

- Investor pays interest on a notional amount N to Bank until maturity T or the default of the issuer (reference entity);
- In case of default,  Bank pays Investor the notional amount N in exchange of the physical delivery of the underlying asset.
	- If cash settled,  bank pays investor the net loss (=notional minus value of defaulted bond).
- This is by far the most popular credit derivative. It is essentially an insurance contract.

## SINGLE NAME CREDIT DEFAULT SWAP
- EXAMPLE
	- It is 2008 and an investor holds$10 mm of 5-year bonds from Lehman Brothers.
	- Given recent events,  the investor is now worried about Lehman defaulting on its obligations.
	- Two strategies:
		1. Sell out the position
			1. Problem: Low liquidity and high transaction costs.
		1. Enter into a CDS with,  say,  AIG Financial Products,  to obtain insurance against Lehman defaulting.
			1. This solution is cheaper,  and easier to perform.
			1. It is the equivalent for credit markets to the now standard interest rate swaps that corporations use to manage assets and liabilities.
	1. Assume CDS spread is 400bp,  then investor pays AIG$10 ×  ×  =$100,  000 each quarter until default
	1. If default occurs,  AIG FP pays$10 mm in exchange of the defaulted bond (physicaldelivery).
	1. If it is cash settled,  dealer quotes for recovery rate are obtained,  and Lehman pays"notional minus recovery."

## CDS SPREAD: LEHMAN AND BEAR STEARNS

- The CDS spread capture important information about the likelihood of survival of individual companies.
 ![500](4b7ec0fa1ed7089fe9e5506a0ecc5050.png)

## CDS SPREAD: ITALY,  GREECE,  AND USA THE CREDIT DEFAULT SWAP SPREAD

 ![500](bd018ef58c733a40505bddde176053ca.png)

- In principle,  the credit default swap spread should coincide with the credit spread of the underlying bond.
	- For instance,  with the credit spread formula in Merton's model discussed earlier:

$$\mathrm{Credit~Spread}=y-r=-{\frac{1}{T}}l o g\left[1-e^{r\times T}P u t\left({\frac{V_{0}}{F}},   r,   T,   \sigma\right)\right]$$

- However,  traders do not use this formula,  for a number of reasons:
	- The bonds underlying CDS are not zero coupon,  and so we have to adjust for coupon payments of the underlying bonds.
	- The default could occur earlier than maturity T,  and therefore
		- A. The insurance buyer stops making quarterly payments to insurance seller.
		- $B$. We have to compute the probability of getting the notional back whenever default occurs.
- These items generate some additional complications,  that more complicated models take into account.