# 24.9 CHOICE OF THE DISCOUNT RATE AND MULTIPLE CURVES  

Throughout the book, we took the standard approach of pricing derivatives under the risk-neutral measure and using a risk-free discount rate. This was based on the fundamental financial engineering principle that a derivative can be valued by means of a replicating portfolio that leads to a riskfree portfolio. However, as will see below, one of the most common proxies for the risk-free rate. before the GFC embeds a significant amount of counterparty risk which makes it an unsatisfactory. proxy for the risk-free rate. We introduced LIBOR and the OIS rate in Chapter 3. Figure 24.8 shows the LIBOR-OIS spread over the December 2003-July 2014 period based on Bloomberg data. The solid line and the dashed line show the 1-month and 3-month LIBOR-OIS spreads,. respectively. As the figure shows there were several episodes where the LIBOR and OIS rates. diverged by several percentage points including the years during the GFC. The divergence between the two rates reflects counterparty risk and changes in the perception of creditworthiness of banks. and their willingness to lend to each other.  

Before the GFC, LIBOR was the most commonly used proxy for the riskless rate but after the GFC, market practice has moved to the usage of OIS rates as a discount rate in collateralized transactions. This is partly due to the fact that LIBOR rates were significantly higher than OIS rates as a result of the counterparty risk that was priced into LIBOR rates.  

The following example illustrates that the move to OIS discounting affects hundreds of billions of dollars of derivatives transactions:  

# EXAMPLE  

With an increasing proportion of interest rate swap trades now being valued using the overnight swap index. (OIS) rather than Libor, LCH.Clearnet plans to begin using the measure to discount its US\$218trn interest rate swap portfolio to ensure a more accurate valuation for risk management purposes. The move signals an ongoing trend that began during the financial crisis, and the shift could help to boost liquidity across the OIS curve. Even prior to the crisis, many market participants argued that OIS was the most appropriate measure given. that it represents an accurate measure of expectations of the federal funds rate over the term of the swap. With. the Libor-OIS spread historically stuck around 10 bp, there was little impetus for change. But after peaking at more than 300 bp in late 2008, market participants were forced into reconsidering their valuation methods. Traders believe that the ongoing shift towards OIS discounting has already improved liquidity in longer. maturities and more exotic currencies, and the shift by LCH.Clearnet should further boost liquidity..  

(Thomson Reuters IFR 1838, June 19 to June 25, 2010, "LCH adopts OIS discounting")  

![](250888d8f586a09f9415abd0d15ab69c7c96be1a36a073cf2a0e8410f0dc973c.jpg)  

# FIGURE 24.8  

LIBOR-OIS spread.  

The move to OIS rates has three fundamental implications for derivatives pricing. First, it is not. possible anymore to use the same LIBOR/swap zero curves to price certain derivatives such as. IRSs that we discussed in Chapter 4. Payoffs continue to depend on LIBOR rates, but discount rates will be based on OIS rates. Second, multiple curves need to be modeled to price fixed-income derivatives such as IRSs as well as caps and swaptions discussed in Chapter 17. The reason is not just due to the fact that OIS and LIBOR rates differ, but also because practitioners now use multiple. LIBOR curves which reflect different levels of counterparty risk. Third, if one assumes that banks. can risklessly borrow and lend at LIBOR and OIS rates then an implicit arbitrage arises..  

The move to the OiS rate as the riskless rate also has implications for fixed-income financial engineering discussed in Chapter 14. We saw that one of the widely used models was the so-called Forward LIBOR or BGM (Brace Gatarek Musiela) Model. In principle, this model can be modified. easily by replacing the LIBOR rate with the OIS rate, which would lead to a Forward OIS model. For some fixed-income derivatives, it is necessary to model the LIBOR and OIS curves simulta-. neously. In practice, many banks continue to use several models such as the 3-factor HJM and the Forward LIBOR model. One of the first-order effects in fixed-income modeling is stochastic volatility. It is important to incorporate stochastic volatility but the Forward LIBOR model is not very. suitable for this purpose when large trading books are concerned since most Monte Carlo methods. that would allow this tend to be too time consuming..  

OIS discounting also brings with it some practical computational challenges as the following reading illustrates.  

# EXAMPLE  

Some buy-side firms have also taken steps to mitigate the problem of collateral-adjusted valuation by. limiting the assets that can be posted under their CSAs, and therefore removing the collateral switch option.. "The appropriate discount curve for valuing trades is more clearly defined under a clean CSA, leaving less room for ambiguity and additional margins both at inception and in the future," says LGIM's Walsh. "If clients move to clean CSAs, then it is no longer sensible to discount with Libor-so you need to be able to discount using the OIS rate...  

$I...J$ says buy-side firms may be able to approximate OIS discounting using simpler methods, but matching the accuracy of dealers is considerably more challenging--as is performing the calculations in a manageable time frame. "Speed of calculation becomes important when you want to do accurate risk management," says Douglas. OIS discounting can be orders of magnitude more computationally demanding than Libor discounting because of the number of curve calculations and calibrations it entails, he says. And if a firm also wants to calculate the CVA, debit valuation adjustment and funding valuation adjustment on a deal, then this is far beyond the reach of conventional position-keeping systems.  

(Risk Magazine, February 22, 2013, "OIS discounting dilemma for the buy-side", by Clive Davidson, www.risk.net/2244927)  

Finally there is an ongoing debate among practioners and among academics about the correct discount rate to use and this discussion is also related to a debate about the rationale for FVA.  
