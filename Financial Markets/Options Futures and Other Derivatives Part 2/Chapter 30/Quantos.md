---
tags:
  - '#binomial_tree'
  - '#convexity_adjustment'
  - '#currency_derivatives'
  - '#forward_exchange_rate'
  - '#interest_rate_risk'
  - '#market_price_of_risk'
  - '#numeraire_analysis'
  - '#quanto_derivatives'
  - '#risk_neutral_measures'
  - '#siegel_s_paradox'
---
# 30.3 QUANTOS  

A quanto or cross-currency derivative is an instrument where two currencies are. involved. The payoff is defined in terms of a variable that is measured in one of the currencies and the payoff is made in the other currency. One example of a quanto is the CME futures contract on the Nikkei discussed in Business Snapshot 5.3. The market. variable underlying this contract is the Nikkei 225 index (which is measured in yen), but the contract is settled in U.S. dollars..  

Consider a quanto that provides a payoff in currency $X$ at time $T$ Assume that the payoff depends on the value. $V$ of a variable that is observed in currency $Y$ at time $T$  

Define:  

$P_{X}(t,T)$ : Value at time $t$ in currency $X$ of a zero-coupon bond paying off 1 unit of currency $X$ at time $T$   
$\textstyle P_{Y}(t,T)$ : Value at time $t$ in currency $Y$ of a zero-coupon bond paying off 1 unit of currency $Y$ at time $T$ $V_{T}$ : Value of $V$ at time $T$   
$E_{X}(V_{T})$ : Expected value of $V_{T}$ in a world defined by numeraire $P_{X}(t,T)$   
$E_{Y}(V_{T})$ : Expected value of $V_{T}$ in a world defined by numeraire $\textstyle P_{Y}(t,T)$  

The numeraire ratio when we move from the $\textstyle P_{Y}(t,T)$ numeraire to the $P_{X}(t,T)$ numeraire is  

$$
W(t)=\cfrac{P_{X}(t,T)}{P_{Y}(t,T)}S(t)
$$  

where $S(t)$ is the spot exchange rate (units of $Y$ per unit of $X$ ) at time $t$ It follows from this that the numeraire ratio $W(t)$ is the forward exchange rate (units of $Y$ per unit of $X$ for a contract maturing at time $T$ Define:  

$\sigma_{W}$ :Volatility of W $\sigma_{V}$ :Volatility of V $\rho_{V W}$ :Instantaneous correlation between $V$ and $W$  

From equation (28.35), the change of numeraire increases the growth rate of $V$ by $\alpha_{V}$ where  

$$
\alpha_{V}=\rho_{V W}\sigma_{V}\sigma_{W}
$$  

If it is assumed that the volatilities and correlation are constant, this means that  

$$
E_{X}(V_{T})=E_{Y}(V_{T})e^{\rho_{V W}\sigma_{V}\sigma_{W}T}
$$  

or as an approximation  

$$
E_{X}(V_{T})=E_{Y}(V_{T})(1+\rho_{V W}\sigma_{V}\sigma_{W}T)
$$  

These equations can be used to value diff swaps where interest in one currency is applied to a principal in another currency.  

# Example 30.3  

Suppose that the current value of the Nikkei stock index is 15,000 yen, the 1-year dollar risk-free rate is. $5\%$ , the 1-year yen risk-free rate is. $2\%$ , and the Nikkei. dividend yield is. $1\%$ . The forward price of the Nikkei for a 1-year contract. denominated in yen can be calculated in the usual way from equation (5.8) as  

$$
15,000e^{(0.02-0.01)\times1}=15,150.75
$$  

Suppose that the volatility of the index is. $20\%$ , the volatility of the 1-year forward yen per dollar exchange rate is $12\%$ , and the correlation between the two is 0.3. In. this case $E_{Y}(V_{T})=15{,}150{.}75$ $\sigma_{V}=0.20$ $\sigma_{W}=0.12$ and $\rho=0.3$ . From equation (30.5), the expected value of the Nikkei in a world defined by a numeraire equal to a dollar bond maturing in 1 year is.  

$$
15,150.75e^{0.3\times0.2\times0.12\times1}=15,260.23
$$  

This is the forward price of the Nikkei for a contract that provides a payoff in dollars rather than yen. (As an approximation, it is also the futures price of such a. contract.)  

# Using Traditional Risk-Neutral Measures  

The numeraire-based measures we have been using work well when payoffs occur at only one time. In other situations, it is often more appropriate to use the traditional riskneutral measure. Suppose the process followed by a variable $V$ in the traditional currency- $Y$ risk-neutral world is known and we wish to estimate its process in the traditional currency- $X$ risk-neutral world. Define:  

$S$ :Spot exchange rate (units of $Y$ per unit of $X$ $\sigma_{S}$ :Volatility of $S$   
$\sigma_{V}$ :Volatility of $V$   
$\rho$ :Instantaneous correlation between $S$ and $V$  

In this case, the change of numeraire is from the money market account in currency $Y$ to the money market account in currency. $X$ (with both money market accounts being denominated in currency $X$ . Define $g_{X}$ as the value of the money market account in. currency $X$ and $g_{Y}$ as the value of the money market account in currency. $Y$ Thee numeraire ratio is  

$$
g_{X}S/g_{Y}
$$  

The variables $g_{X}(t)$ and $g_{Y}(t)$ have a stochastic drift but zero volatility as explained in. Section 28.4. From Ito's lemma it follows that the volatility of the numeraire ratio is $\sigma_{S}$ The change of numeraire therefore involves increasing the expected growth rate of $V$ by  

$$
\rho\sigma_{V}\sigma_{S}
$$  

The market price of risk changes from zero to. $\rho\sigma_{S}$ This result enables what is known as.   
Siegel's paradox to be understood (see Business Snapshot 30.1).  

# Example 30.4  

A 2-year American option provides a payoff of $S\mathrm{~-~}K$ pounds sterling where $S$ is the level of the S&P 500 at the time of exercise and. $K$ is the strike price. The current level of the S&P 500 is 1,200. The risk-free interest rates in sterling and dollars are both constant at $5\%$ and $3\%$ , respectively, the correlation between the dollar/sterling exchange rate and the S&P 500 is 0.2, the volatility of the S&P 500 is $25\%$ , and the volatility of the exchange rate is $12\%$ . The dividend yield on the S&P 500 is $1.5\%$  

This option can be valued by constructing a binomial tree for the S&P 500.   
using as the numeraire the money market account in the U.K. (i.e., using the   
traditional risk-neutral world as seen from the perspective of a U.K. investor)..   
From equation (30.7), the change in numeraire from the U.S. to U.K. money.   
market account leads to an increase in the expected growth rate in the S&P 500 of.  

$$
0.2\times0.25\times0.12=0.006
$$  

or $0.6\%$ . The growth rate of the S&P 500 using a U.S. dollar numeraire is $3\%-1.5\%=1.5\%$ The growth rate using the sterling numeraire is therefore  

# Business Snapshot 30.1 Siegel's Paradox  

Consider two currencies, $X$ and $Y.$ Suppose that the interest rates in the two currencies,. $r_{X}$ and $r_{Y}$ , are constant. Define $S$ as the number of units of currency. $Y$ per unit of currency $X.$ As explained in Chapter 5, a currency is an asset that provides a yield at the foreign risk-free rate. The traditional risk-neutral process for. $S$ is therefore  

$$
d S=(r_{Y}-r_{X})S d t+\sigma_{S}S d z
$$  

From Ito's lemma, this implies that the process for $1/S$ is  

$$
d(1/S)=(r_{X}-r_{Y}+\sigma_{S}^{2})(1/S)d t-\sigma_{S}(1/S)d z
$$  

This leads to what is known as Siegel's paradox. Since the expected growth rate of $S$ is $r_{Y}-r_{X}$ in a risk-neutral world, symmetry suggests that the expected growth rate of $1/S$ should be $r_{X}-r_{Y}$ rather than $r_{X}-r_{Y}+\sigma_{S}^{2}$  

To understand Siegel's paradox it is necessary to appreciate that the process we have given for $S$ is the risk-neutral process for $S$ in a world where the numeraire is the money market account in currency $Y$ . The process for $1/S$ , because it is deduced from the process for $S$ , therefore also assumes that this is the numeraire. Because $1/S$ is the number of units of $X$ per unit of $Y$ to be symmetrical we should measure the process for $1/S$ in a world where the numeraire is the money market account in currency $X$ Equation (30.7) shows that when we change the numeraire, from the money market account in currency. $Y$ to the money market account in currency $X.$ the growth rate of. a variable $V$ increases by $\rho\sigma_{V}\sigma_{S}$ , where $\rho$ is the correlation between $S$ and $V$ In this case, $V=1/S$ , so that $\rho=-1$ and $\sigma_{V}=\sigma_{S}$ It follows that the change of numeraire causes the growth rate of $1/S$ to increase by $-\sigma_{S}^{2}$ . This neutralizes the. $+\sigma_{S}^{2}$ in the process given above for $1/S.$ The process for. $1/S$ in a world where the numeraire is the money market account in currency $X$ is therefore  

$$
d(1/S)=(r_{X}-r_{Y})(1/S)d t-\sigma_{S}(1/S)d z
$$  

This is symmetrical with the process we started with for S. The paradox is resolved!  

$2.1\%$ . The risk-free interest rate in sterling is. $5\%$ . The S&P 500 therefore behaves like an asset providing a dividend yield of. $5\%-2.1\%=2.9\%$ under the sterling numeraire. Using the parameter values of $S=1{,}200$ $K=1\mathrm{{,}}200$ $r=0.05$ $q=0.029$ $\sigma=0.25$ , and $T=2$ with 100 time steps, DerivaGem estimates the value of the option as 179.83.  

# SUMMARY  

When valuing a derivative providing a payoff at a particular future time it is natural to assume that the variables underlying the derivative equal their forward values and discount at the rate of interest applicable from the valuation date to the payoff date. This chapter has shown that this is not always the correct procedure.  

When a payoff depends on a bond yield $y$ observed at time $T$ the expected yield should be assumed to be higher than the forward yield as indicated by equation (30.1). This result can be adapted for situations where a payoff depends on a swap rate. When a variable is observed at time $T$ but the payoff occurs at a later time $T^{*}$ the forward value of the variable should be adjusted as indicated by equation (30.3). When a variable is observed in one currency but leads to a payoff in another currency the forward value of the variable should also be adjusted. In this case the adjustment is shown in equation (30.5).  

These results can be used when nonstandard swaps are valued.  

# FURTHER READING  

Brotherton-Ratcliffe, R., and B. Iben, "Yield Curve Applications of Swap Products," in Advanced Strategies in Financial Risk Management (R. Schwartz and C. Smith, eds.). New York Institute of Finance, 1993..   
Jamshidian, F., "Corralling Quantos," Risk, March (1994): 71-75..   
Reiner, E., "Quanto Mechanics," Risk, March (1992), 59-63..   
Siegel, J. J., "Risk, interest rates and the forward exchange," Quarterly Journal of Economics, 86 (1972): 303-309.  

# Practice Questions  

30.1. The payoff from a forward contract is delayed by two years. Explain how the impact of the delay on value is affected by the correlation between the price of the underlying asset and interest rates.  

30.2. Explain whether any convexity or timing adjustments are necessary when:  

(a) We wish to value a spread option that pays off every quarter the excess (if any) of the 5-year swap rate over the 3-month compounded SOFR applied to a principal of $\$100$ The payoff occurs 90 days after the rates are observed.   
(b) We wish to value a derivative that pays off every quarter the 3-month compounded SOFR minus the 3-month Treasury bill rate. The payoff occurs 90 days after the rates are observed.  

30.3. Suppose that in Example 29.3 of Section 29.2 the payoff occurs after 1 year (i.e., when the interest rate is observed) rather than in 15 months. What difference does this make to the inputs to Black's model?  

30.4. The OIS zero curve is flat at. $10\%$ per annum with annual compounding. Calculate the value of an instrument where, in 5 years' time, the 2-year OIS swap rate (with annual payments and compounding) is received and a fixed rate of. $10\%$ is paid. Both are. applied to a notional principal of. $\$100$ . Assume that the volatility of the forward swap. rate is $20\%$ . Explain why the value of the instrument is different from zero..  

30.5. What difference does it make in Problem 30.4 if the swap rate is observed in 5 years but the exchange of payments takes place in (a) 6 years, and (b) 7 years? Assume that the. volatilities of all forward rates are $20\%$ and also that the forward swap rate for the period between years 5 and 7 has a correlation of 0.8 with the forward interest rate between years. 5 and 6 and a correlation of 0.95 with the forward interest rate between years 5 and 7..  

30.6. The price of a bond at time $T$ measured in terms of its yield, is $G(y_{T})$ . Assume geometric Brownian motion for the forward bond yield $y$ in a world that is defined by a numeraire equal to a bond maturing at time $T$ Suppose that the growth rate of the forward bond yield is $\alpha$ and its volatility is $\sigma_{y}$  

(a) Use Ito's lemma to calculate the process for the forward bond price in terms of $\alpha$ $\sigma_{y},y$ , and $G(y)$   
(b) The forward bond price should follow a martingale in the world considered. Use this fact to calculate an expression for $\alpha$   
(c) Show that the expression for $\alpha$ is, to a first approximation, consistent with equation (30.1).  

30.7. The variable. $S$ is an investment asset providing income at rate $q$ measured in currency A. It follows the process.  

$$
d S=\mu_{S}S d t+\sigma_{S}S d z
$$  

in the real world. Defining new variables as necessary, give the process followed by $S$ and the corresponding market price of risk, in:.  

(a) A world that is the traditional risk-neutral world for currency A   
(b) A world that is the traditional risk-neutral world for currency B   
(c) A world that is defined by a numeraire equal to a zero-coupon currency A bond. maturing at time $T$   
(d) A world that is defined by a numeraire equal to a zero-coupon currency B bond maturing at time $T$   
30.8. A call option provides a payoff at time $T$ of $\operatorname*{max}(S_{T}-K,0)$ yen, where $S_{T}$ is the dollar price of gold at time $T$ and $K$ is the strike price. Assuming that the storage costs of gold are zero and defining other variables as necessary, calculate the value of the contract.   
30.9. A Canadian equity index is 400. The Canadian dollar is currently worth $0.70~\mathrm{U}.\mathrm{S}$ dollars. The risk-free interest rates in Canada and the U.S. are constant at $6\%$ and $4\%$ respectively. The dividend yield on the index is $3\%$ . Define $Q$ as the number of Canadian dollars per U.S. dollar and $S$ as the value of the index. The volatility of $S$ is $20\%$ , the volatility of $Q$ is $6\%$ , and the correlation between $S$ and $Q$ is 0.4. Use DerivaGem to determine the value of a 2-year American-style call option on the index if: (a) It pays off in Canadian dollars the amount by which the index exceeds 400. (b) It pays off in U.S. dollars the amount by which the index exceeds 400.  

30.10. Consider an instrument that will pay off. $S$ dollars in 2 years, where $S$ is the value of the. Nikkei index. The index is currently 20,000. The yen/dollar exchange rate is 100 (yen per dollar). The correlation between the exchange rate and the index is 0.3 and the dividend yield on the index is $1\%$ per annum. The volatility of the Nikkei index is. $20\%$ and the. volatility of the yen/dollar exchange rate is $12\%$ . The interest rates (assumed constant) in the U.S. and Japan are $4\%$ and $2\%$ , respectively.  

(a) What is the value of the instrument?   
(b) Suppose that the exchange rate at some point during the life of the instrument is. $Q$ and the level of the index is S. Show that a U.S. investor can create a portfolio that changes in value by approximately $\Delta S$ dollar when the index changes in value by $\Delta S$ yen by investing $S$ dollars in the Nikkei and shorting $S Q$ yen.   
(c) Confirm that this is correct by supposing that the index changes from 20,000 to 20,050 and the exchange rate changes from 100 to 99.7.   
(d) How would you delta hedge the instrument under consideration?.  

30.11. Suppose that the risk-free yield curve is flat at. $8\%$ (with continuous compounding). The payoff from a derivative occurs in 4 years. It is equal to the 5-year rate minus the 2-year rate at this time, applied to a principal of. $\$100$ with both rates being continuously. compounded. (The payoff can be positive or negative.) Calculate the value of the derivative. Assume that the volatility for all rates is. $25\%$ . What difference does it make. if the payoff occurs in 5 years instead of 4 years? Assume all rates are perfectly correlated.  

30.12. Suppose that the payoff from a derivative will occur in 10 years and will equal the 3-year U.S. dollar swap rate for a semiannual-pay swap observed at that time applied to a certain principal. Assume that the swap yield curve is flat at $8\%$ (semiannually compounded) per annum in dollars and. $3\%$ (semiannually compounded) in yen. The. forward swap rate volatility is $18\%$ , the volatility of the 10-year "yen per dollar". forward exchange rate is $12\%$ , and the correlation between this exchange rate and U.S. dollar interest rates is 0.25. What is the value of the derivative if the swap rate is applied to a principal of (a). $\$100$ million with a dollar payoff and (b) 100 million yen with a yen payoff? Assume that risk-free rates are $2\%$ in yen and. $6\%$ in dollars (both semiannually compounded).  

# APPENDIX PROOF OF THE CONVEXITY ADJUSTMENT FORMULA  

This appendix calculates a convexity adjustment for forward bond yields. Suppose that the payoff from a derivative at time. $T$ depends on a bond yield observed at that. time. Define:  

$y_{F}$ : Forward bond yield observed today for a forward contract with maturity $T$ $y_{T}$ : Bond yield at time $T$   
$B_{T}$ : Price of the bond at time. $T$   
$\sigma_{y}$ : Volatility of the forward bond yield..  

Suppose that the relationship between a bond price and its yield is  

$$
B_{T}=G(y_{T})
$$  

Expanding $G(y_{T})$ in a Taylor series about $y_{T}=y_{F}$ yields the following approximation:  

$$
B_{T}=G(y_{F})+(y_{T}-y_{F})G^{\prime}(y_{F})+0.5(y_{T}-y_{F})^{2}G^{\prime\prime}(y_{F})
$$  

where $G^{\prime}$ and $G^{\prime\prime}$ are the first and second partial derivatives of $G$ . Taking expectations in a world defined by a numeraire equal to a zero-coupon bond maturing at time $T$ gives  

$$
\begin{array}{r}{E_{T}(B_{T})=G(y_{F})+E_{T}(y_{T}-y_{F})G^{\prime}(y_{F})+\frac{1}{2}E_{T}[(y_{T}-y_{F})^{2}]G^{\prime\prime}(y_{F})}\end{array}
$$  

where $E_{T}$ denotes expectations in this world. The expression. $G(y_{F})$ is by definition the forward bond price. Also, because of the particular world we are working in, $E_{T}(B_{T})$ equals the forward bond price. Hence. $E_{T}(B_{T})=G(y_{F})$ , so that  

$$
{\cal E}_{T}(y_{T}-y_{F})G^{\prime}(y_{F})+{\textstyle\frac{1}{2}}{\cal E}_{T}[(y_{T}-y_{F})^{2}]G^{\prime\prime}(y_{F})=0
$$  

The expression $E_{T}[(y_{T}-y_{F})^{2}]$ is approximately $\sigma_{y}^{2}y_{F}^{2}T$ Hence it is approximately true that  

$$
E_{T}(y_{T})=y_{F}-{\textstyle\frac{1}{2}}y_{F}^{2}\sigma_{y}^{2}T\frac{G^{\prime\prime}(y_{F})}{G^{\prime}(y_{F})}
$$  

This shows that, to obtain the expected bond yield in a world defined by a numeraire equal to a zero-coupon bond maturing at time. $T$ the term  

$$
-{\textstyle{\frac{1}{2}}}y_{F}^{2}\sigma_{y}^{2}T\frac{G^{\prime\prime}(y_{F})}{G^{\prime}(y_{F})}
$$  

should be added to the forward bond yield. This is the result in equation (30.1). For an alternative proof, see Problem 30.6.  

![](1a899f4eff386f608b4d6d3495951fc0a81e4c9101047458638a536732eafd25.jpg)  

# Equilibrium Models of the Short Rate  

In this chapter, we consider how models of the term structure of risk-free interest rates can be constructed in both the real world and the risk-neutral world. We first show that when a Markov process for the short rate has been specified in the traditional riskneutral world all rates can, at least in theory, be calculated at all times as a function of the short rate. We will spend some time studying two popular one-factor Markov models of the short rate: the Vasicek model and the Cox, Ingersoll, and Ross model. These are relatively simple models which lead to analytic formulas for determining bond prices.  

The difference between the behavior of the short rate in the real world and the risk-. neutral world is determined by the market price of interest rate risk. We explained the meaning of the term "market price of risk' in Section 28.1. The market price of risk for a bond is positive. Since interest rates and bond prices are negatively related, the market price of risk for an interest rate is negative. This means that the drift of an interest rate is greater in the risk-neutral world than in the real world. The expected future value of an interest rate is therefore greater in the risk-neutral world than in the real world..  

The equilibrium models considered in this chapter can approximately match the. today's term structure of interest rates, but they do not provide an exact match. However, when Monte Carlo simulation is being carried out over a long period of. time for the purposes of scenario analysis, the models can be useful tools. For example, a pension fund or an insurance company that is interested in the performance of its investments over the next 20 years is likely to feel that an approximate fit to today's. term structure is adequate.  

In the next chapter, we extend the material in this chapter to consider short-rate models that are designed to exactly fit today's term structure of interest rates. These are used to value interest rate derivatives. In Chapter 33, we consider models of forward rates that also provide an exact fit to today's term structure.  
