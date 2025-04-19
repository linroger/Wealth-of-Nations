---
tags:
  - cms_linked
  - fixed_income
  - monetary_policy
  - structured_products
  - yield_curve
aliases:
  - Fixed Income Products
  - Structured Fixed Income
key_concepts:
  - CMS-linked products
  - Convexity effect
  - Level effect
  - Slope effects
  - Yield curve strategies
---

# 20.3 STRUCTURED FIXED-INCOME PRODUCTS  

Structured fixed-income products follow principles that are similar to the ones based on equity or commodity prices. But the analysis of the principles of fixed income is significantly more complex for several reasons.  

First, the main driving force behind the fixed-income structured products is the yield curve, which is a $k$ -dimensional stochastic process. Equity or commodity indices are scalar-valued stochastic processes, and elementary structured products based on them are easy to price and hedge. Equity (commodity) products that are based on baskets would have a. $k$ dimensional underlying, yet the arbitrage conditions associated with this vector would still be simpler. Second, the basis of fixed-income products is the LIBOR reference system, which leads to the LIBOR market model or swap models. In equity even when we deal with a vector process, there is no need to use similar models. Third, fixedincome markets are bigger than the equity and commodity markets combined. The very broad nature of fixed-income products' maturities and credits can make some maturities in fixed income much less liquid. Finally, the fixed-income structured products do have long maturities, whereas in equity or commodity-linked derivatives they are relatively short dated.  

# 20.3.1 YIELD CURVE STRATEGIES  

It is clear that most fixed-income structured products will deal with yield curve strategies. There aren't too many yield curve movements.  

1. The yield curve may shift parallel to itself up or down-called the level effect..   
2. The yield curve slope may change. This could be due to monetary policy changes or due to. changes in inflationary expectations. The curve can steepen if the Central Bank lowers shortterm rates or flatten if the Central Bank raises short-term rates. This is called the slope effects..   
3. The "belly" of the curve may go up and down. This is in general interpreted as a convexity effect and is related to changes in interest rate volatility.  

The next point is that many of these yield curve movements are at least partially predictable.. After all, Central Banks often announce their future policies clearly to inform the markets. Structurers. can use this information to put together constant maturity swap (CMS)-linked products that benefit. from the expected yield curve movements. One can also add callability to enhance the yield further.'  

The reading below is one example of how the structurers look at yield curve strategies.  

# EXAMPLE  

The popularity of CMS-linked structured notes derives from end users wanting to take advantage of the inverse sterling yield curve, which seems to have stabilized in the long end..  

A typical structured note might be EUR5-50 million, with a 20-year maturity. It could pay a coupon of $8\%$ for the first 5 years, and then an annual coupon based on the 10-year sterling swap rate, capped at. $8\%$ for the remainder of the note. It would be noncallable. The 10-year sterling swap rate was about $6.77\%$ last week.  

The long end of the sterling yield curve has likely stopped dropping because UK life insurers, who have been hedging guaranteed rate annuity products sold in the 1980s, have stopped scrambling for long-dated gilts. They have done so either because they no longer require further hedging, or because they have found more economical ways of doing so. If the long end fails to fall further, investors are more secure about. receiving a long-term rate in a CMS, a trader said..  

The sterling yield curve, which is flat for about three years, and then inverts, makes these products attractive for investors who believe the curve will disinvert at some point in the future, according to traders..  

(Thomson Reuters IFR, January 31, 2000)  

Hence it is clear that fixed-income structured products are heavy in terms of their involvement in LIBOR, swaption, and call/floor volatilities and their dynamics. Essentially, to handle them the. structurer needs to have, at the least, a very good command of the forward LIBOR and swap models..  

# 20.3.2 THE TOOLS  

Some of the tools involved in designing and risk-managing structured products were discussed. earlier. Digital and rainbow options and forward volatility were among these. Fixed-income struc-. tured products use additional tools. Two familiar tools are modified versions of cap/floors and swaptions and a third major tool is CMs. We review these briefly in this section..  

A digital caplet is similar to a vanilla caplet. It makes a payment if the reference LIBOR rate exceeds a cap level. The difference is the payoff. While the vanilla caplet payoff may vary according to how much the LIBOR exceeds the level, the digital caplet would make a constant payment no matter what the excess is, given that the LIBOR rate is greater than the cap level.  

A Bermudan swaption can be defined as an option on a swap rate. $s_{t}$ The option can be exercised only at some specific dates $t_{1}$ $t_{2}$ , ... When the option is exercised, the option buyer has the. right to get in a payer (receiver) swap at a predetermined swap rate. $\kappa$ . The option seller has the. obligation of taking the other side of the deal. Clearly with this product the option buyer receives swaps of different maturity as the exercise date changes.  

CMS are fundamental elements of fixed-income structured products; hence, we review them separately.  

# 20.3.3 CMS  

A constant maturity swap is similar to a plain vanilla swap except for the definition of the floating rate.   
They were discussed in Chapter 14. There is a fixed payer or receiver, but the floating payments would.   
no longer be LIBOR-referenced. LIBOR is a short-term rate with tenors of 1, 2, 3, 6, 9, or 12 months..   
It can only capture views concerning increasing or decreasing short-term rates. In a CMS, the floating.  

rate will be another vanilla swap rate. This swap rate could have a maturity of 2 years, 3 years, or even 30 years. This way, instruments that benefit from increasing or decreasing long-term rates can also be put together. A 10-year CMS with a maturity of 2 years was shown in Figure 14.5. Note that there are variations on the CMS and it is possible that in a CMS, one party periodically pays a swap rate of a specific tenor (or the spread between swap rates of different specified tenors), known as the CMS rate, and in exchange receives a specified fixed or floating rate from the counterparty.  

A special property of CMS should be repeated at this point. Note that at every reset date, the contract requires obtaining, say, a 10-year swap rate from some formal fixing process. This 10-year swap rate is normally valid for the next 10 years. Yet, in a CMS that settles semiannually, this rate will be used for the next 6 months only. At the next reset date, the new fixing will be used. Thus, the floating rate that we are using is not the "natural rate' for the payment period. In other words, denoting the 10-year floating swap rate by $s_{t_{i}}^{10}$ we have:  

$$
\frac{\left(1+s_{t_{i}}^{10}\delta\right)}{\left(1+L_{t_{i}}\delta\right)}\ne1
$$  

even though both rates are "floating." As long as the yield curve is upward sloping, the ratio will in fact be greater than one. But, in the case of a vanilla swap, each floating rate. $L_{t_{i}}$ is the natural rate for the payment period and we have:  

$$
{\frac{\left(1+L_{t_{i}}\delta\right)}{\left(1+L_{t_{i}}\delta\right)}}=1
$$  

This is true regardless of whether we have observed. $L_{t_{i}}$ or not. For this reason, the CMS require. a convexity adjustment. This means, heuristically speaking, that the future unknown floating rates cannot simply be replaced by their forward equivalents. For example, if in 3 years we receive a 10-year floating swap rate $s_{t}$ during pricing we cannot replace this by the corresponding forward swap rate $s_{t}^{f}$ . Instead we replace it with a forward swap rate adjusted for convexity..  

# 20.3.4 YIELD ENHANCEMENT IN FIXED-INCOME PRODUCTS  

Suppose an investor desires an enhanced return or a corporation wants a hedging solution at a lower cost. The general principle behind putting together such structured products is similar to equity pro-. ducts and is illustrated in the following contractual equation:  

![](c225240350f664115871d3beb2ccf505610c0e9807739154ee5be173a3f25eb3.jpg)  

As in equity structured products, in order to offer a return higher than the one offered by straight bonds, make the client sell one or more options. In fact, as long as the client properly understands the risks and is willing to bear them, the more expensive and more numerous the options are, the higher will be the return. If the client is a corporation and is looking for a cheaper hedge, selling an option would again lower the associated costs.  

In structured fixed income products, there are at least two standard ways one can enhance yields.  

![](2a989429d0691d07072a4590a054ca57e8828a359c988e6f761b5a480e55e8cc.jpg)  

# FIGURE 20.8  

Digital caplet.  

# 20.3.4.1 Method 1: Sell cap volatility  

The first method to enhance yields is conceived so as to make the client sell cap/floor volatility.. We saw in Chapter 17 that a caplet (floorlet) was an insurance written on a particular LIBOR rate that made a payment to the buyer of the option if the observed LIBOR rate went above (below) the cap level (floor level). A structurer could offer an investor a product that pays a higher coupon. than would be available with the same credit risk and maturity if the product implicitly involves. the investor writing a call option to the structurer. If interest rates are low and the yield curve is steep, investors may obtain above-market yields by betting against the market. Steep yield curves normally imply that interest rates are expected to rise. If an investor believes that interest rates will not rise as far as the market predicts and the investor is proven right, then the investor may be able to obtain an enhanced return. Of course, there is a price in the market for such views and the structurer could price the product based on the cost of a short caplet in the market plus a profit market. To specify a precise range of interest rates and payments associated with the option, the structurer can use digital caplets. Figure 20.8 shows the payoff of a long position in a digital caplet..  

The structure will consider daily fixings of LIBOR and make coupon payments (enhanced by. the implicit digital caplet-type premium) when a day's observation stays within a range, say $[0,7\%]$ . If the observed LIBOR exceeds that range for that day, no coupon is received..  

This way, the client is short a digital caplet and is selling digital caplet volatility and he or she will receive an enhanced yield for bearing this risk. Such products are called Range Accrual Notes (RAN). The client will earn interest for the proportion of the day's LIBOR observations that remain within the range. This feature would be suitable for a client who does not expect LIBOR rates to fluctuate significantly during the maturity period.  

Let $\boldsymbol{F}_{t}^{t_{i}}$ be the time- $t$ 6-month forward rate associated with the LIBOR rate $L_{t_{i}}$ . The associated settlement of the spot LIBOR is done, in-arrears, at time. $t_{i+1}$ and the day-count adjustment parameter is $\delta$ as usual.  

Let the index $j=1$ , 2, ... denote days. A typical caplet starts on day $t_{i}+(j-1)$ and has an expiration 1 day later at $t_{i}+j$ Each caplet's payoff will depend on the selected reference rate that is. followed daily. Often this would be the LIBOR rate at time. $t_{i}+j,L_{t_{i}+j}$ . Depending on this daily observation the caplets will expire in- or out-of-the-money. In other words, the seller collects daily fixings on the LIBOR rate and sees if the rate stayed within the range that day. If it does, there. will be a digital payoff for that day (i.e., interest accrues); otherwise, no interest is earned for that. particular day.  

On the other hand, the actual amount paid will depend on another predetermined LIBOR rate. The rate applied to the payoff will be. $L_{t_{i}}+$ spread, settled at $t_{i+1}$ 9 According to this the return of. the structured product return is a function of the payoffs of. $m$ digital options, where m is the. number of calendar days in the payment period. Hence, the issue of whether interest is earned or not and the payoff depends on different LIBOR rates for each settlement period.  

Symbolically, assuming that interest paid is constant at $R$ , the $j$ th day's payoff of the caplets can be written as  

$$
\mathbf{Pay}_{t_{i}+j}=\left\{\begin{array}{l l}{L_{t_{i}}\frac{1}{360}N}&{\mathrm{if~}L_{t_{i}+j}\geq L^{\operatorname*{max}}}\ {0}&{\mathrm{if~}L_{t_{i}+j}\leq L^{\operatorname*{max}}}\end{array}\right.
$$  

where $L^{\mathrm{max}}$ is the upper limit of "range," $N$ is the notional amount, and $\mathrm{Pay}_{t_{i}}~+j$ is the daily payoff that depends on the jth observed LIBOR rate $L_{t_{i}+j}$ .The investor will be short this caplet. How would this enhance the return?  

Suppose there are $m$ days during the interest payment period;10 then the client is selling m digi-. tal caplets. For observation days these caplets are written on that day's LIBOR rate that we denoted by $L_{t_{i}+j}$ . For weekends, the previous observation day's LIBOR is used. So these digital caplets can be regarded as an $m$ -period digital cap, made of caplets with daily premiums $c_{t_{i}+j}$ , if settled at the end of that day. The investor receives the daily premiums and pays off that day's payoff at every $t_{i}+j$ instead of collecting all the cap premiums at the contract conception $t_{0}$ The total value of these digital caplets at the payment time $t_{i+1}$ will be given by  

$$
C_{t_{0}}=\sum_{j=1}^{m}B(t_{0},t_{i}+j)c_{t_{i}+j}
$$  

where $c_{t_{i}+j}$ are the caplet premiums for the option that starts at time $t_{i}+j$ Clearly these quantities are known at time $t_{0}$ 11 Note that this quantity is measured in time. $t_{i+j}$ dollars. Then the enhanced yield of the RAN settled at time $t_{i+j}$ will be given by  

$$
L_{t_{i}}+c_{t_{i}+j}
$$  

At the time of inception $t_{0}$ of the note, the relevant LIBORs will be $\{L_{t_{i}}\}$ and these will be "equivalent" to $s_{t_{0}}$ , the swap rate observed at the time of inception. So the enhanced yield can in fact be expressed by the constant $R_{t_{0}}$  

$$
R_{t_{0}}=s_{t_{0}}+c_{t_{i}+j}
$$  

If at time $t_{0}$ the structurer observes the (i) swap rate $s_{t_{0}}$ , (ii) the forward volatilities of each digital cap $c_{j},$ and (iii) the discount factors $B(t_{0},t_{i+1})$ , then $R_{t_{0}}$ can be calculated. Thus the investor will receive the $R_{t_{0}}N$ and will pay the payoffs of daily caplets that expire in-the-money. Naturally, all this assumes a correct calculation of the digital cap premium $c_{j}.$ Here there are some small technical complications. However, before we get to these we look at an example.  

# EXAMPLE: INTEREST RATE RANGE ACCRUAL/STRUCTURED DEPOSIT  

[Price quoted as of May 23, 2011] Customer View: US Dollar 3-month LIBOR will stay within the range of $0.25\substack{-0.60\%}$ (inclusive) in the   
coming I year Deposit Currency: Renminbi (CNY) Deposit Period: 1 year. Deposit Amount: CNY1,000,000 Interest Rate: US Dollar 3-month LIBOR (3M LIBOR) Reference Index Accrual in rate: $0.70\%$ p.a. Accrual out rate:. $0.00\%$ p.a. Interest rate: Accrual in rate $\times$ (No. of days 3M LIBOR stays at or within the Accrual Range)/Total   
number of days $^+$ Accrual out rate $\times$ (No. of days 3M LIBOR stays outside the Accrual Range)/Total number   
of days Accrual range: $0.25\substack{-0.60\%}$ p.a. Interest period: Quarterly. Interest payment: (Principal) $\times$ Interest rate/4) for each interest period for each period. Upon maturity: $100\%$ of principal customer receives (HSBC, https://www.hsbc.com.hk/1/2/hk/investments/sp/range-acc#exampl  

In the above example, there are some interesting variations since the deposit currency (CNY) differs from the currency underlying the interest rate reference index. This may be convenient for customers that deposit CNY but have reviews regarding US interest rates. Note that the range is not bounded from below by zero, but is instead bounded by $L^{\mathrm{min}}=0.25\%$ and $L^{\operatorname*{max}}=0.60\%$ . The accrual out rate is the rate received if the interest rate falls outside the range. This implies that the investor is not just short a digital cap, but also a digital floor.  

Note that the underlying reference rate in the examples above that we use to determine the payoff of the digital caplets is 3-month or 6-month LIBOR rates, which are not the "natural rates' for the 1-day payoffs. Hence, the pricing of these digital caplets would require that a convexity adjustment is applied to the LIBOR rates, similar to CMS.  

# 20.3.4.2 Method 2: Sell swaption volatility  

Making a straight bond callable is the second way of enhancing yields. This will result in the investor being short swaption volatility..  

The difference is important. In the first case one is writing a series of options on a single cash flow, namely the caplet payoff. But in the case of callable bonds, the investor will write options on. all the cash flows simultaneously and will receive his principal 100 if the bond is called. Thus a swaption involves payoffs with baskets of cash flows. These cash flows will depend on different LIBOR rates. When the swaption is Bermudan, this is similar to selling several options (although. dependent on each other) at the same time. Hence the Bermudan swaption will be more expensive. and there will be more yield enhancement..  

An investor that buys a callable LIBOR exotic has sold the issuer the right (but not the obligation) to redeem the notes at $100\%$ of the face value at any given call date. A note that is callable just once (European) will have a lower yield than a comparable note with multiple calls (Bermudan). The question whether a callable note will be called or not depends on the initially assumed dynamics of the forward LIBOR rates versus the behavior of these forward rates and their volatilities in the future.  
