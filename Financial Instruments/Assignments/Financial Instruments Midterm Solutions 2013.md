---
cssclasses: academia
aliases: [FINANCIAL INSTRUMENTS EXAMPLE MIDTERM SOLUTIONS,  Alias_147_Financial Instruments Midterm Solutions 2013.md,  Alias_148_Financial Instruments Midterm Solutions 2013.md]
linter-yaml-title-alias: FINANCIAL INSTRUMENTS EXAMPLE MIDTERM SOLUTIONS
tags: tag_example
title: Financial Instruments Midterm Solutions 2013
---

---

title: FINANCIAL INSTRUMENTS EXAMPLE MIDTERM SOLUTIONS

aliases: [FINANCIAL INSTRUMENTS EXAMPLE MIDTERM SOLUTIONS]

linter-yaml-title-alias: FINANCIAL INSTRUMENTS EXAMPLE MIDTERM SOLUTIONS

# Financial Instruments Midterm Solutions 2013

##Problem 1. (20 Points)

 True-False Questions (There Are 4 Of Them). Grade Depends On Completeness Of Answer.

(a) (5 points) Let's suppose you write a European call option on a stock. To hedge your exposure to the stock you could buy an equivalent number of shares of the stock.

> [!ANSWER]
> Solution: False. You need to match the Delta of the option.
(b) XYZ airlines is committed to buying one million barrels of jet fuel next quarter. XYZ can hedge this position by going long futures contracts for one million barrels of oil.
> [!ANSWER]
> Solution: False in general. The hedge ratio depends on the relationship between the futures price and the price of jet fuel. This should be checked empirically.
(c) Some options contracts may increase in value as they approach maturity.
> [!ANSWER]
> Solution: True. A call option with a large dividend yield and a put option that is significantly out of the money both increase in value as they approach maturity.
(d) The current price of a security is given by the expected future price of that security discounted using the risk-adjusted required rate of return. A forward contract to buy that same security locks in the price to buy the security at maturity. Since risk is eliminated,  the forward price should reflect discounting using the risk-free return. The forward price must therefore be lower than the expected future price of the security.
> [!ANSWER]
> Solution: False in general. This depends on the sign of the risk-premium.
## PROBLEM 2. (20 POINTS) BINOMIAL TREES

Suppose that stock JCH,  whose current price is$100,      can either increase by u = 1.05 or decrease by d = 1/(1.05) per year for the next 2 years.

The continuously-compounded interest rate is 2% per year.

(a) (15 points) Suppose you are *long* a call option that gives you the option to buy,      in two years,      *100* shares of JCH stock at a strike price of$95 per share. How would you hedge your exposure to the price of JCH stock over the life of the option? What is the current price of your option position?

> [!ANSWER]
> Solution: The stock price dynamics are given by:
> ![|500](IMG-20240913171226888.png)
To do the hedging and pricing we need all of the Delta's and bond positions. These are:
$$\Delta_{u}=\frac{15.25-5}{110.25-100}=1$$
$$B_{u}=e^{-0.02}\times(15.25-1\times110.25)=-93.12$$
so that$c_{u}=1\times105-93.12=11.88$
$$\Delta_{d}=\frac{5-0}{100-90.70}=0.54$$
$$B_{u}=e^{-0.02}\times(5-0.54\times100)=-47.81$$
so that$c_{d}=0.54\times95.24-47.81=3.40$.
$$\Delta=\frac{11.88-3.4}{105-95.24}=0.87$$
$$B=e^{-0.02}\times(11.88-0.87\times105)=-77.72$$so that c = 0.87 × 100 − 77.72 = 9.11.
The current price of the option is 9.11 and the positions in the stock and bond are given by the Delta's and "B's" above.
(b) (5 points) Consider a *binary* option on JCH stock. Under this option contract the holder of the option receives one share of JCH stock if in two years (the maturity of the option) the stock is trading between$85 and$95. According to your assumptions,  what is an appropriate price for this option? (Hint: notice that I only asked you to price the option. No hedging required!)
 > [!ANSWER]
> Solution: The payoffs and values of the option are given by:$$\begin{array}{ccccc}&&V_{uu}=0\\ &&\nearrow&&\\ &&V_u&&\\ &&\nearrow&&\searrow&&\\ V&&&&&V_{ud}=0\\ &&\searrow&&\nearrow&&\\ &&V_d&&\\ &&\searrow&&\\ &&V_{dd}=90.70\end{array}$$
The risk neutral probability of an "up" move is:$$q^{*}={\frac{e x p(0.02)-d}{u-d}}=0.69$$
The price of the option is therefore:$$V=e^{-0.02\times2}\times(1-0.69)^{2}\times90.70=8.38$$
## PROBLEM 3. (**30 POINTS**)

A few years ago your company issued a bond denominated in Euros. The bond has a face value of 1 million Euros and pays semi-annual coupons at an annual rate of 6%. You just made a coupon payment and the bond has one year left to maturity. In other words you owe a coupon payment in 6 months,  and payments of coupon and principal in 1 year.

The current exchange rate is 1.3 dollars per Euro (USD/EUR). The current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rates (in continuously compounded units) are:

| Maturity   | USD   | Euro   |
|------------|-------|--------|
| 6 months   | 2%    | 2%     |
| 1 year     | 2.5%  | 3%     |

(a) (10 points) You would like to hedge your exposure to the Euro using forward contracts. How many and what maturities of forward contracts would you use? What would be the forward prices of these contracts?

 > [!ANSWER]
> Solution: The forward prices are:$$F_{0,     0.5}=1.3\times e^{(0.02-0.02)\times0.5}=1.3$$
and
$$F_{0,     1}=1.3\times e^{(0.025-0.03)\times1}=1.29$$
Hedge: buy 6%/2 × 1 milllion = 30,  000 Euros forward at the 6 month rate of 1.3 and buy 1,  030,  000 Euros forward at the 1 year rate of 1.29.
(b) (10 points) Suppose the day after you signed your forward contract in part (a) above,  the spot exchange rate between dollars and Euros is 1.29 dollars per Euro (USD/EUR). Yields (c.c.) in the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] market are now:

| Maturity              | USD   | Euro   |
|-----------------------|-------|--------|
| 6 months (less a day) | 2%    | 2%     |
| 1 year (less a day)   | 2.5%  | 3.1%   |

What would be the market values of the forward contracts you signed in part (a)?(Assume that there are 360 days in a year.)

> [!ANSWER]
> Solution:
The new forward rates for the maturities from part (a) are now:$$F_{1/360,     0.5}=1.29$$
and$${F}_{{{1}\text{/}{360}}}={1.29}\times{e}^{{{\left({0.025}-{0.031}\right)}\times{359}\text{/}{360}}}={1.28}$$
The value of the forward contracts from part(a)are now:$${V}_{{{1}\text{/}{360},     {0.5}}}={e}^{{-{0.02}\times{179}\text{/}{360}}}\times{30},     {000}\times{\left({1.29}\text{-}{1.30}\right)}=\text{-}{297.03}$$and$$V_{1/360,     1} = e^{−0.025×359/360} × 1,      030,      000 × (1.28 − 1.29) = -11,      263.69$$
(c) (10 points) Let's return to the setting of part (a) where you owe a coupon payment in six months,  and coupon and principal payments in one year. An investment bank
offers you a contract where they will pay the Euros under your bond obligation. In return,  you will owe the bank US dollar denominated payments on a bond with one year to maturity,  face value of$1.29 million,      and semiannual coupon payments at an annual rate of 6%. Would you enter into this contract to hedge your exposure to the Euro? Why or why not?
> [!ANSWER]
> Solution: The present value of what you currently owe is (in US Dollars):$$V_{Euro Bond} = 1.3 × (e−0.02×0.5 × 30,      000 + e−0.03 × 1,      030,      000) = 1,      338,      038.51$$
The semiannual coupon from the offer is:$1,  290,  000 × 0.03 = 38,  700$
 The present value of the offer is:$$V_{Offer} = e−0.02×0.5 × 38,      700 + e−0.025 × [1,      290,      000 + 38,      700] = 1,      327,      745.91$$
Since I would owe the bank less than what I would receive,  I would enter the agreement.
## PROBLEM 4. (**20 POINTS**)
- Through your investment in an index fund you are currently long 1,  000
units of the S&P500. In addition,  you are long a put option on the S&P500. The terms of this put option are:
	- Underlying index: S&P500.
	 - Current value of the S&P500:$1,  200.
	- Number of units of the underlying index: 750.
	- Strike price of the put option (per unit of underlying):$1,  000.
 - Maturity of the put option: 2 years.
(a) (5 points) Why might you be holding the put option contract along with the S&P 500 index?
 > [!ANSWER]
> Solution You would like to participate in the upside of the S&P500 but would like some down-side protection.
(b) (15 points) Make the following additional assumptions:
- Risk-free rate: 1% continuously compounded.
- Dividend yield for the S&P500: 0%.
- Volatility of the S&P500: 30%. This will be constant over the life of the option.
Under these assumptions,  what should be the value of your portfolio? What is the delta of your portfolio with respect to the S&P500?
 > [!ANSWER]
> Solution: Black-Scholes quantities:
$$d_1=\frac{\ln(1200/1000)+(0.01+0.3^2/2)\times2}{0.3\times\sqrt{2}}=0.69$$
$$d_2=0.69-0.3\times\sqrt{2}=0.26$$
$$N(-d_1)=0.25$$
$$N(-d_2)=0.4$$
The value of a put option on one unit of the index:
$$p=1,     000\times e^{-0.01\times2}\times0.4-1,     200\times0.25=93.28$$
Hence the value of your portfolio is:$$1,     000\times1,     200+750\times93.28=1,     269,     959.22$$.
The delta of your portfolio is:$$1,     000-750\times0.25=815.94$$