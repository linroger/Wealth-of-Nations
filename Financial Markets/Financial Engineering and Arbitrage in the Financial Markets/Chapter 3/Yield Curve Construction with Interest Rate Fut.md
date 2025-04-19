---
tags:
  - eurodollar_futures
  - financing_rate
  - interest_rate_futures
  - libor_rate
  - yield_curve
aliases:
  - Eurodollar futures
  - LIBOR
  - Yield curve
key_concepts:
  - Discount factors calculation
  - Eurodollar futures role
  - Financing rate information
  - Spot LIBOR rate
  - Yield curve construction
---

# 3.5 YIELD CURVE CONSTRUCTION WITH INTEREST RATE FUTURES  

Eurodollar (-euro, -sterling) futures play a fundamental role in yield curve construction. Since. each contract locks in the financing rate for the 3 months following the contract expiry, and as the expiries of the contracts are laid out every 3 months, the financing rate information contained in each contract can be used to calculate how much $\$1$ would earn up to almost any date in the future using a reinvestment argument. Conversely, the present value of $\$1$ to be received on any future date can be computed using the spot LIBOR rate and all intervening Eurodollar futures. Once the yield curve is constructed and discount factors for any future dates.  

Table 3.23 A sample of WTI Oil futures, fair values, and convenience yields on July 23, $2003^{*}$   


<html><body><table><tr><td>Month/year</td><td>Low</td><td>High</td><td>Settle</td><td>Change</td><td>Open int.</td><td>Fair value</td><td>Conv. yield</td></tr><tr><td>Aug2003</td><td>31.25</td><td>32.10</td><td>31.78</td><td>-0.18</td><td>45,102</td><td>31.85</td><td></td></tr><tr><td>Sep2003</td><td>30.33</td><td>31.17</td><td>30.83</td><td>-0.20</td><td>190,648</td><td>31.72</td><td>17.00</td></tr><tr><td>Oct2003</td><td>29.95</td><td>30.64</td><td>30.40</td><td>-0.09</td><td>55,331</td><td>31.59</td><td>15.30</td></tr><tr><td>Nov2003</td><td>29.50</td><td>30.05</td><td>29.93</td><td>0.01</td><td>1,490</td><td>31.45</td><td>14.90</td></tr></table></body></html>

\*Data collected by hand from the WSJ for illustrative purposes only, accuracy not guaranteed. LIBOR at $1.13\%$ fo1 fair value calculation.  

are calculated, the value of any option-free fixed income security can be computed simply by discounting its cash flows up to today.  

# 3.5.1 Certainty Equivalence of Eurodollar Futures  

It is important to realize one fundamental feature of Eurodollar futures: they cost nothing to enter into (buy or sell). Any agent with funds available for lending/borrowing over the future period covered by the contract period has a choice: to lock in the financing rate implied by the futures price (for free) or not to lock it (for free), and wait for the future spot LIBOR to realize. Therefore, in yield curve construction, the implied futures rate can be taken to be the future spot rate for discounting purposes. Another way of stating this is that while the future spot 3-month rate almost certainly will not be equal to today's futures price covering the period in question, today's fair value of it is, and a. $\$100$ discount bond for that period must. be discounted using the futures rate. Let us illustrate..  

On October 25, 2012, Jane Newbie, the Treasurer of a large financial firm facing rates in. Table 3.7, overhears her CEO talking about. $\$100$ million that her firm will have to deal with. on June 19, 2013. Jane, new to her job, is unsure if the CEO said that the firm will have the $\$100$ million to invest or will have to borrow it; she is sure, however, that the CEO said the. funds would bear interest for 3 months (till September 2013).  

If the firm has $\$100$ million to invest, then Jane can wait till June and invest at the then. prevailing LIBOR rate, bearing the risk the rate might go down, or she can lock in a rate by buying 100 Eurodollar futures. It costs her nothing to buy the futures and the firm has a margin account in which to settle mark-to-market amounts. If, instead, the firm has to borrow $\$100$ million, then Jane can wait till June and borrow at the then prevailing LIBOR rate, bearing the risk that the rate might go up, or she can lock in a rate by selling 100 Eurodollar futures. Unsure of what to do, Jane calls Smart Bank and asks for a two-way rate quote on a forward 3-month deposit and loan starting on June 19..  

Smart Bank has to quote $2.52\%$ (June futures trade at 97.48) to avoid being arbitraged.  

If Smart Bank were to quote $2.64\%$ , Jane would agree to deposit $\$100$ million at Smart Bank in June and would short 100 Eurodollar futures. On June 19, she would borrow $\$100$ million in the spot deposit market at the then prevailing LIBOR and deposit that $\$100$ million at Smart. Bank at a rate of. $2.64\%$ . We have shown before that no matter what LIBOR is on June 19,. her cost of borrowing cum variation market settlement is guaranteed to be. $2.52\%$ . If LIBOR is $2.00\%$ , she would lose $\$130,000$ $(100\times52\times25)$ on futures and pay $\$500,000$ in interest, making it a total of. $\$630,000$ . If LIBOR is $3.00\%$ , she would gain $\$120,000$ on futures, but pay $\$750,000$ in interest, again making it a total of. $\$630,000$ , which is equivalent to $2.52\%$ At the same time, Smart Bank guaranteed to pay her. $100,000,000\times0.0264\times(90/360)=$ 660,000 in interest, ensuring a $\$30,000$ profit.  

If Smart Bank were to quote $2.40\%$ , Jane would buy 100 Eurodollar contracts and agree. to borrow $\$100$ million in June from Smart Bank. In this arbitrage, she would use the $\$100$ million borrowed from Smart Bank to lend at the future spot LIBOR rate. Including the variation margin settlement, she would be guaranteed to earn. $2.52\%$  

If Smart Bank quotes any rate different from $2.52\%$ , between the mark-to-market on futures and the interest settlement with the bank, Jane can guarantee for her firm a positive cash flow equal to $\$100$ million times the interest rate deviation from $2.52\%$ times the day-count $(\approx^{1}/4)$ So, Smart Bank will be smart to quote $2.52\%$ ; it can then transact in futures to completely eliminate the risk of lending to or borrowing from Jane's firm.  

We see that Jane and the bank have to be indifferent between the uncertain future spot rate or today's known implied futures rate, the latter's level being determined (as the balance of demand and supply of forward deposits) so that it costs nothing to convert one into the other. This observation is essential for valuing floating rate bonds, forward rate agreements, and swap contracts whose one (floating) leg contains a string of LIBOR-dependent cash flows. Although the future LIBORs are unknown today, the present value of these cash flows is computed by replacing the unknown future LIBORs with today's forward rates or implied futures rates.  

# 3.5.2 Forward Rate Agreements  

The over-the-counter forward markets trade the equivalent of the Eurocurrency futures, called Forward Rate Agreements (FRAs). FRAs are more flexible than futures as they can be entered into for any future dates and for any notional principal amount. The disadvantage is that there is no credit risk mitigation by a clearinghouse; they are private contracts between two private parties. In order to unwind the contracts, the two original parties have to agree on the mark-to-market value. Some of these issues are standardized by master agreements of an international industry association. These provide for credit exposure netting (cash inflows and outflows for all contracts with the same counterparty are netted in case of default, and only the net amount is exposed to default) and for using reference dealers in case the two parties cannot agree on the mark-to-market value for unwinds. While FRAs can be arranged for any future dates, standard maturities are quoted continuously by the largest dealers. These are listed for different start and end date combinations, relative to today, using the convention of "start month $\times$ end month.' For example, in the quotes:  

$$
\begin{array}{r l}{1\times4}&{{}2.75/2.76}\ {2\times5}&{{}2.82/2.83}\ {3\times6}&{{}2.84/2.85}\end{array}
$$  

the $^{\star}2\times5^{\prime}$ contract is bid at 2.82 and offer at 2.83. In this case, ' $^{\circ}2\times5^{\circ}$ means a contract with a start date of exactly 2 months from today and an end date of exactly 5 months from today. Just like Eurodollar futures, FRAs lock in a borrowing/lending rate for future 3-month periods. As the dates are defined relative to today's date, they roll every day by 1 day. In. the futures markets, these are fixed in terms of actual calendar dates. Some standard 1, 6-, and 12-month forward periods are also quoted in the market, e.g.. $^{\cdot62}\times3^{\cdot}{}^{;}$ or $^{\leftarrow}1\times7$ " The language convention for FRAs is different from the futures. Parties do not go long (buy) or. short (sell), but "receive"' or "pay,' or "pay fixed' and "receive fixed,' similar to the swap. market conventions.  

The main economic difference between a FRA and a Eurodollar futures contract is that the settlement of the mark-to-market takes place once at expiry, rather than daily up to the expiry. date, and that the settlement amount is present-valued rather than a simple rate differential. times a multiplier. To see this, let us describe the mechanics of a FRA contract..  

A FRA is equivalent to a cash-settled fixed-for-floating swaplet (see Chapter 4). One party agrees to pay, and the other agrees to receive, a fixed rate of interest applied to a notional principal amount over a 3-month period in exchange for receiving (the other party paying) a floating rate equal to the spot 3-month LIBOR rate on the forward start date, applied to the same principal amount. The pay and receive amounts are netted, present-valued by the spot LIBOR on the forward start date, and settled in cash on that date. Suppose on March 19, 2013, we enter into a $3\times6$ FRA to pay $2.52\%$ On $\$20$ million. The start date of the forward is. June 19 and the end date is September 19. The amount the \*FRA payer" will pay to the "FRA receiver" is defined as:  

$$
20,000,000\times[(2.52-L)/100]\times(\mathrm{Act}/360)\times[1/(1+L\times\mathrm{Act}/360)]
$$  

The payment has the difference between the agreed-upon rate and future LIBOR applied. to the notional principal, scaled by the appropriate day-count fraction, and multiplied by the. present-value factor for 3 months. The payment is computed on June 19, when the LIBOR rate,. $L$ is revealed, and remitted 2 business days later, on June 21. The cash flow can be positive or negative depending on the LIBOR rate on June 19 relative to the upfront forward rate..  

Suppose that, on June 19, the 3-month LIBOR is $2.00\%$ . The FRA payer will have to send a check to the FRA receiver for the amount of:  

$$
{\begin{array}{r l}&{20,000,000\times[(2.52-2.00)/100]\times(92/360)\times[1/(1+0.02\times92/360)]}\ &{\qquad=\S26,442.63}\end{array}}
$$  

which is close to the $\$26,000$ the buyer of 20 Eurodollar futures contracts would receive in the form of net variation margin by June 19.  

Suppose that, on June 19, the 3-month LIBOR is $3.00\%$ . The settlement cash flow is then computed as:  

$$
{\begin{array}{r l}&{20,000,000\times[(2.52-3.00)/100]\times(92/360)\times[1/(1+0.03\times92/360)]}\ &{\qquad=\S-24,346.68}\end{array}}
$$  

This time the FRA payer would receive a check for $\$24,346.68$ from the FRA receiver. This is almost the same as the $\$24,000$ that the seller of 20 Eurodollar futures contracts would receive in the form of net variation margin by June 19. The difference is that the FRA cash flow is computed for 92 days, and not for 90 days (which forces the. $1,000,000\times90/360\times0.0001=$ $\$25$ multiplier), it is present-valued by 3 months from the end date to the start date (the futures. omit that), and it is received all at once on June 19, instead of over time in the form of daily variation margin checks. For short forward start dates, the difference between forwards and futures is negligible. For longer forward start dates, 2 years and above, the difference grows. and the two zero-cost rates start to diverge. The difference between the quoted FRA and futures rates for the same dates is referred to as futures convexity. It is largely due to the timing and PV mismatch of the settlement flows causing futures to be price-yield convex instruments relative to forwards. (This is analogous to viewing bonds as having a convex price-yield relationship and forwards as having a straight-line relationship to forward yields.) The futures convexity. charge can be quite large (in the order of several tens of basis points for 5- to 7-year futures) if the interest rate volatility between now and the expiry date is high (high interest rate volatility increases the mismatch between daily and one-time settlement).  

Like Eurodollar futures contracts, FRAs allow one to lock in a net borrowing/lending rate. for future periods. In a sense they do it in a more precise way. Their mark-to-market formula. reflects exactly the interest exchange (LIBOR vs the lock rate) using the actual day-count and present-valuing the settlement amount to correct for an up-front (start of the interest period) cash flow instead of an arrears cash flow (end of the interest period). The FRA payer locks in a borrowing rate, while the FRA receiver locks in the lending or deposit rate. The easiest way to. remember which side is which is to think of (future) borrowing as issuing a (forward) bond and paying a fixed rate on it, hence to lock in a borrowing rate one pays on a FRA, or sells futures.  

The latter can be thought of as selling a forward discount bond. One can think of lending as buying a bond and receiving a fixed rate on it, hence to lock in a lending rate one receives on a FRA, or buys futures. The latter can be thought of as buying a forward discount bond.  

We used the term certainty equivalence to mean that the market determines today a fixed rate. at which agents are indifferent to exchange (at no charge) future known cash flows for future unknown cash flows based on future spot deposit rates. The certainty equivalence of FRAs is. even more obvious than that of the Eurodollar futures. The settlement formula contains in it the exchange of the forward rate (which is known today) for a future LIBOR rate (which is. not known until the start of the forward interest accrual period), applied to the desired notional. principal and scaled by the appropriate day-count fraction. The present-valuing by 3 months. corrects for the fact that interest is normally computed at the beginning of the accrual period. but paid at the end, but the FRA settles at the beginning of the period..  

# 3.5.3 Bootstrap Revisit: Building Spot Zeros  

In Chapter 2 we showed how quotes for coupon bonds can be used sequentially to compute.   
discount rates for present value calculations through a process called a zero curve bootstrap..   
We revisit the construction of the zero curve, this time with the use of futures and forwards..   
As previously, we will use the observed quotes in a chronological order in order to create a set of rates and discount factors that are appropriate for computing the present values of cash.   
flows at future dates. This is a fundamental task in any valuation process..  

The insight of Chapter 2 is that coupon securities are packages of zeroes (discount bonds). Assuming semi-annual coupons, the yield on a 6-month coupon bond is automatically set to the 6-month zero rate. Then, a 12-month coupon is a package of a 6-month zero with a face value equal to the 6-month coupon flow and a 12-month zero with a face value equal to the 12-month coupon flow plus the principal. If we know the blended' yield on the coupon. security and the yield on the first (6-month) zero in the package, then we can back out the yield on the second (12-month) zero, since the price of the package (in dollars) has to equal the sum of the parts. The next step involves the price and the yield of a 18-month coupon. security as package of the previously computed yields of the 6- and 12-month zeros and the to-be-determined yield on the 18-month zero. The next step is the 24-month coupon bond, etc. We continue in this way using the quoted prices on all the coupon bonds up to the longest maturity, computing along the way a set of zero-coupon yields with increasing maturities. The zero yields then allow us to discount cash flows on any future dates, and consequently allow us to value any (option-free) fixed income security..  

The coupon-based bootstrap results in observations every 6 months (for UK and Canadian bonds with annual coupons, perhaps every 12 months) and is typically used in constructing the discount curve for dates past the 2-, 3-, or 5-year point, but may be too crude for shorter maturities. A forward- or futures-based bootstrap for shorter dates dovetails nicely with the coupon bootstrap for longer terms. Eurodollar futures are liquid every 3 months for 10 years, Eurosterling and Euribor futures are liquid every 3 months for 3 or 5 years. Finer observations can be obtained from 1-month LIBOR futures and FRAs. The choice of where the two methods meet, the short bootstrap based on forwards and the long one based on coupon bonds, depends on the relative liquidity of the instruments. The abundant liquidity of the futures in the short end and of the government bonds in the long end, guarantees - via the fair value arbitrage - that coupon packages can be synthetically replicated without any difficulty and that the whole process is not just a mathematical exercise but a reality ensured by potential arbitrage.  

Table 3.24 Yield curve construction using Eurodollar futures   


<html><body><table><tr><td>Start date</td><td>End date</td><td>Days in period</td><td>Quote</td><td>Implied rate Act/360</td><td>Forward discountfactor</td><td>Spot discountfactor</td></tr><tr><td colspan="7">SpotLIBORs</td></tr><tr><td>Oct152001</td><td>Nov21 2001</td><td>37</td><td>2.05</td><td>2.05</td><td>0.997897</td><td>0.997897</td></tr><tr><td></td><td>Dec19 2001</td><td>65</td><td>2.12</td><td>2.12</td><td>0.996187</td><td>0.996187</td></tr><tr><td></td><td>Jan162002</td><td>93</td><td>2.15</td><td>2.15</td><td>0.994477</td><td>0.994477</td></tr><tr><td colspan="7">EurodollarFutures</td></tr><tr><td>Nov212001</td><td>Feb19 2002</td><td>90</td><td>97.81</td><td>2.19</td><td>0.994555</td><td>0.992464</td></tr><tr><td>Dec19 2001</td><td>Mar202002</td><td>91</td><td>97.85</td><td>2.15</td><td>0.994595</td><td>0.990802</td></tr><tr><td>Jan162002</td><td>Apr19 2002</td><td>93</td><td>97.87</td><td>2.13</td><td>0.994528</td><td>0.989034</td></tr><tr><td>Mar202002</td><td>Jun19 2002</td><td>91</td><td>97.77</td><td>2.23</td><td>0.994395</td><td>0.985248</td></tr><tr><td>Jun19 2002</td><td>Sep18 2002</td><td>91</td><td>97.48</td><td>2.52</td><td>0.993670</td><td>0.979012</td></tr><tr><td>Sep18 2002</td><td>Dec18 2002</td><td>91</td><td>97.09</td><td>2.91</td><td>0.992698</td><td>0.971863</td></tr><tr><td>Dec182002</td><td>Mar192003</td><td>91</td><td>96.60</td><td>3.40</td><td>0.991479</td><td>0.963582</td></tr></table></body></html>  

We proceed sequentially, similarly to the coupon case. We start with a spot zero rate (1-, 2-, or 3-month LIBOR) and add forwards and/or futures with ever-increasing start and end dates to construct a discount curve of zero-coupon yields and discount factors. To avoid confusion with day-counts, it is a good practice to first compute discount factors, not zero rates. Depending on the compounding convention, there can be multiple zero rates for the same date. Discount factors are unique; they are dollar costs (present values) of $\$1$ face value discount bonds maturing on a given date. From the discount factors, we can recover rates based on any compounding or day-count convention.  

We use spot and futures quotes for October 25, 2001. We have three spot zero rates (LIBORs) as starting points for the curve. The maturities of these deposit rates match the expiries of the first three futures contracts, i.e. November, December, and January. We use the November and January quotes merely to get fine detail for the next 6 months (i.e. to discount factors for November, January, and 3 months later for February and April). We use the December spot to compute the discount factors for December and all other dates of the quarterly futures expiry cycle (March, June, September, December). We assume that the LIBORs implied by the Eurodollar futures are for deposits spanning the 3-month periods from one expiry to the next, not the 90 days forced by the. $\$25$ multiplier.  

Table 3.24 contains the quote input information and the computed forward and spot discount factors. The first panel contains the LIBOR quotes; the second panel contains the Eurodollar futures quotes. For clarity, we show the periods spanned by the contracts and the number of days. Forward factors are intermediate calculations; they present-value. $\$1$ from the end date to the start date. Spot discount factors present-value. $\$1$ from the end date all the way back to. the present (October 15, 2001). The whole set of the spot factors unambiguously defines the. yield curve.  

We observe three LIBOR rates (2.05, 2.12, and 2.15) for 1-, 2-, and 3-month deposits. We also observe a string of Eurodollar futures prices. Each locks a 3-month LIBOR for the period starting on the expiry date and ending 3 months later equal to 100 minus the futures price.. Using the number of days in each period spanned by the futures expiries, we compute forward discount factors (the first three based on the spot rates are actually spot factors with the start.  

Table 3.25Recovering zero rates from discount factors   


<html><body><table><tr><td>Date</td><td>Days</td><td>SpotDF</td><td>Continuous yield</td><td>Simple yieldAct/360</td></tr><tr><td>Nov212001</td><td>37</td><td>0.997897</td><td>2.0763</td><td>2.0500</td></tr><tr><td>Dec192001</td><td>65</td><td>0.996187</td><td>2.1453</td><td>2.1200</td></tr><tr><td>Jan162002</td><td>93</td><td>0.994477</td><td>2.1738</td><td>2.1500</td></tr><tr><td>Feb192002</td><td>127</td><td>0.992464</td><td>2.1741</td><td>2.1525</td></tr><tr><td>Mar202002</td><td>156</td><td>0.990802</td><td>2.1620</td><td>2.1423</td></tr><tr><td>Apr19 2002</td><td>186</td><td>0.989034</td><td>2.1637</td><td>2.1459</td></tr><tr><td>Jun192002</td><td>247</td><td>0.985248</td><td>2.1961</td><td>2.1822</td></tr><tr><td>Sep182002</td><td>338</td><td>0.979012</td><td>2.2906</td><td>2.2833</td></tr><tr><td>Dec182002</td><td>429</td><td>0.971863</td><td>2.4283</td><td>2.4295</td></tr><tr><td>Mar192003</td><td>520</td><td>0.963582</td><td>2.6040</td><td>2.6166</td></tr></table></body></html>  

date of today) as $1/\left(1+r\times A c t/360\right)$ . These are present values as of the start date of. $\$1$ received on the end date using the futures-implied yield. The logic follows from arbitrage; a $\$1$ face value loan for the forward period can be synthesized by locking the futures implied rate and borrowing/lending at future LIBOR. From the forward discount factors, we compute spot discount factors (present values as of today, October 25, 2001, of. $\$1$ received on the end date) as products of forward discount factors spanning successive periods. For example, the spot. discount factor of 0.979012 for September 18, 2002, is the product of the factor of 0.996187 for December, the forward factor of 0.994595 for December-March, the forward factor of. 0.994395 for March-June, and the forward factor of 0.993670 for June-September. The yield curve construction could have been enriched by including liquid FRAs as substitutes for futures or used in addition for some of the in-between dates, and more spot points, or coupon instrument dates.  

Once we have computed all the discount factors, we can recover discount rates according to any convention. In Table 3.25 we show the continuously compounded yields (which have the nice property that the spot continuous yield is simply an average of the forwards) and simple interest Act/360 yields.  

The yield curve for 520 days, as of October 25, 2001, is shown in Figure 3.2.  

![](6e5d8518460cc444367db5df8e0ff1d4242a9ed5b7b5319f2d700973b7be1caa.jpg)  
Figure 3.2 The zero-coupon curve  

Since the discount factors are today's prices of future dollars, pricing fixed income securities is trivial. Suppose we are offered a structured note paying $\$3,500$ twice, 182 days from today and 365 days from today plus the principal of $\$100,000$ How much do we pay for it?  

We do not have the factors for 182 days or 365 days, so we interpolate the continuous yields. to obtain these two factors. Using the rates for 156 days and 186 days, we get the interpolated. yield of 2.1635 and the discount factor of 0.989270 for 182 days. Using the rates for 338 days and 429 days to get the interpolated yield of 2.3314 and the discount factor of 0.976955 for 365 days. The present value of the note's cash flows is then equal to.  

$$
3,500\times0.989270+(3,500+100,000)\times0.976955=\{104,577.33
$$  

We pay $104.5773\%$ of the face value for the note.  

# 3.5.4 Recovering the Forwards  

With the constructed yield curve, not only can we value securities with known (fixed) cash flows, but also those whose cash flows float with LIBOR rates (floating rate bonds, inverse floaters, leveraged floaters, etc.). We can recover forwards implied by the yield curve and substitute them for future unknown LIBORs using the certainty equivalence argument of costless conversion. The present value of an artificial security with today's forwards substituted for the unknown future LIBORs must be the same as that of the actual floating rate security.  

# The Valuation of a Floating Rate Bond  

On October 25, 2001 we are offered a 1-year floating rate note with a face value of $\$200,000$ whose quarterly coupon is equal to the 3-month LIBOR. The coupon payment dates are January 25, April 25, July 25 and October 25, 2002, set 3 months prior. How much are we willing to pay for it? The valuation method is summarized in Table 3.26.  

We compute the number of days from spot (today) to each rate set and interest pay date, and the number of days between the set and the pay date. We use those to interpolate the continuous discount yields and to compute discount factors to each set and pay date. From each pair of discount factors, we compute the implied forward LIBOR rate (FRA) using the arbitrage argument that discounting from the pay date to today can be synthesized by discounting from the pay date to the set date and then from the set date to today:  

$$
d f_{P a y D a t e}=d f_{S e t D a t e}\times\left(1+\frac{1}{\left(1+f_{S e t\times P a y}\times\frac{A c t}{360}\right)}\right)
$$  

For example, the Jan02 forward LIBOR, i.e. the Jar $102\times\mathrm{Apr}02$ FRA, of 2.1302, is computed from:  

$$
0.989270=0.994538\times\left(1+\frac{1}{\left(1+f_{J a n02\times A p r02}\times\frac{90}{360}\right)}\right)
$$  

Each cash flow is set on the basis of the LIBOR forward on the set date equal to $200{,}000\times$ $\begin{array}{r}{f_{S e t\times P a y}\times\frac{A c t}{360}}\end{array}$ and paid 3 months later. We compute the PV of the cash flow by multiplying it. by the discount factor to the pay date. We sum the PVs to get the price of the note which turns out to be exactly $\$200,000$ . This is no surprise given that the floating rate note is a revolving loan always worth par.  

<html><body><table><tr><td>cash flow PV of</td><td>1,092.34 1,053.65 1,152.06 196,701.94 200,000.00</td></tr><tr><td>Cash flow on pay</td><td>1,098.34 1,065.08 1,171.38 201,341.78</td></tr><tr><td>Implied LIBOR Set</td><td>Sum of PVs 2.1489 2.1302 2.3170 2.6252</td></tr><tr><td>DF to Pay</td><td>0.994538 0.989270 0.983510 0.976955</td></tr><tr><td>DF to set</td><td>1.000000 0.994538 0.989270 0.983510</td></tr><tr><td>cont yld Interp topay</td><td>2.1728 2.1635 2.2231 2.3314</td></tr><tr><td>Days in period</td><td>29092</td></tr><tr><td>Days to pay</td><td>22135</td></tr><tr><td>Days toset</td><td>2 213</td></tr><tr><td>Pay date</td><td>Jan252002 Apr252002 Jul252002 Oct252002</td></tr><tr><td>Setdate</td><td>Oct252001 Jan252002 Apr252002 Jul252002</td></tr></table></body></html>  

# 3.5.5 Including Repo Rates in the Calculation of the Forwards  

The yield curve construction process is generic to all credit markets. In one special situation, it has to be modified to take into account special repos which render forward replication. strategies more expensive. There are times when the demand and supply forces may make a bond scarce. A lender of funds through a reverse repo (buying securities today to resell tomorrow) may lend funds at a zero interest rate just to be able to own the desired bond. overnight. The resale price includes a rebate making it only minimally greater than or equal to today's purchase price. The lender earns diminished or no interest, but acquires the desired collateral (the bond). The diminished interest rate is referred to as special repo and is lower than the overnight or term rate implied by the yield curve..  

In a simplified numerical example, assume that a 1-year zero yielding $6\%$ enjoys general repo, while a 2-year zero yielding $6.5\%$ is expected to be on special for the next month. We want to replicate a 1-year by 2-year forward deposit by buying the 2-year zero and shorting the 1-year zero. If neither bond were on special, then we could lock in the forward $f_{12\times24}$ rate equal to $7.0024\%$ implied from:  

$$
{\frac{1}{1+0.06}}\times{\frac{1}{1+f_{12\times24}}}={\frac{1}{(1+0.065)^{2}}}
$$  

This no-arbitrage equation states that $\$1$ can be received 2 years from today by spending $1/(1+0.065)^{2}$ on a 2-year bond or can be synthesized by spending $1/(1+0.06)(1+f_{12\times24})$ on a 1-year bond and rolling it over into $1/(1+f_{12\times24})$ of a 1-year by 2-year forward. However, if the 2-year bond trades special, then to own it we have to surrender interest for a month. That is like paying a higher price grossed up by 1 plus the lost interest fraction. Assuming that the 1-month rate is equal to $6\%$ , we have  

$$
{\frac{1}{1+0.06}}\times{\frac{1}{1+f_{12\times24}}}=(1+0.06)^{1/12}{\frac{1}{\left(1+0.065\right)^{2}}}
$$  

The forward rate we can synthesize is $f_{12\times24}=6.484\%$ The calculations for special repos get complicated when deriving synthetic forward prices for coupon securities. The simple discount factors in the above equations have to be replaced with PVs of coupon and principal packages. However, the principle of synthetic replication with no-arbitrage must not be violated and the mathematics must include any repo rebates earned or given up. The equations are the same for forward borrowers and lenders as the "specialness" of repo cuts both ways. The forward lender locks in a lower forward rate. The borrower also does this, and uses the hotly desired security as collateral in a repo transaction.  

Publicly traded securities - stocks and bonds - are often bought as a long-term investment. Their ownership is widely distributed among thousands of investors. Short of major corporate actions, such as tender offers, buyback programs, or bankruptcy restructurings, issuers have little leeway to change the cash flow pattern of their liabilities. This is where swap markets come in. Issuers can match the cash flows they owe on their preferred stocks or bonds while agreeing to pay completely different sets of flows to financial institutions. Fixed coupon liabilities can be swapped into floating; dollar flows can be swapped into yen or euros; callable or putable flows can be swapped into straight bullet flows. Not only can issuers change the nature and maturity of their old liabilities, but they can also take advantage of relative differences in financing costs in different markets. Bonds can be issued floating and immediately swapped into fixed, or issued in one currency and immediately swapped into another to take advantage of a low interest rate, while matching the liability to the nature and currency of the revenue stream. Nestle can issue a Swiss franc fixed bond, swap it into floating dollars and euros, and be able to pay the coupons with revenues from global sales.  

The fastest growing segments of the swap markets are interest rate swaps, cross-currency.   
swaps, and credit default swaps with trillions of dollars of principal outstanding worldwide..   
We leave until later the analysis of credit default swaps which are structurally insurance.   
arrangements, exchanging premiums for one-time event-triggered payouts. In this chapter.   
we cover interest rate, cross-currency, equity, and commodity swaps which typically are not triggered single payouts, but have multiple predefined cash flows on both sides of the swap..  
