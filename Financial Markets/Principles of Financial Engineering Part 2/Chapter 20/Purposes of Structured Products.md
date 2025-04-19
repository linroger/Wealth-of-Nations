---
tags:
  - '#cliquets'
  - '#equity_structured_products'
  - '#forward_volatility'
  - '#hedging_strategies'
  - '#mountain_options'
  - '#option_payoffs'
  - '#principal_protected_products'
  - '#reverse_convertibles'
  - '#structured_products'
  - '#volatility_gamma'
---
# 20.2 PURPOSES OF STRUCTURED PRODUCTS  

Structured products may have at least four specific objectives.  

The first objective could be yield enhancement-to offer the client a higher return than what is normally available. This of course implies that the client will be taking additional risks or foregoing. some gains in other circumstances. For example, the client gets an enhanced return if a stock price increases up to $12\%$ . However, any additional gains would be forgone and the return would be. capped at $12\%$ . The value of this cap is used in offering an enhanced yield..  

The second could be credit enhancement. In this case, the client will buy a predetermined set of debt securities at a lower default risk than warranted by their rating. For example, a client invests in a portfolio of 100 bonds with average rating BBB. At the same time, the client buys insurance on the first default in the portfolio. The cost of first debtor defaulting will be met by another party. This increases the credit quality of the portfolio to, say, ${\tt B B+}$  

The third objective could be to provide a desired payoff profile to the client according to the client's views. For example, the client may think that the yield curve will become steeper. The structurer will offer an instrument that gains value if this expectation is realized..  

Finally, a fourth objective may be facilitating asset/liability management needs of the client For example, a corporate treasurer who thinks that the cost of funds would increase in the future may decide to enter into a payer interest rate swap. The structurer will provide a modified swap structure that will protect against this eventuality at a smaller cost. In the following, we discuss these generalities using different sectors in financial markets.  

# 20.2.1EQUITY STRUCTURED PRODUCTS  

First we take a quick glance at the history of equity structured products. This provides a perspective on the most common methodologies used in this sector. The first examples of structured products appeared in the late 1970s. One example was the stop-loss strategies. According to these, the risky asset holdings would automatically be liquidated if the prices fell through a target tolerance level. These were precursors of the CPPI techniques to be seen later in Chapter 23. They can also be regarded as precursors of barrier options.  

Then, during the late 1980s, market practitioners started to move to principal protected products.. Here the original approach was offering "zero coupon bond plus a call' structures. For example, with 5-year treasury rates at $r_{t},$ and with an initial investment of. $N=100$ , the product would invest  

$$
\frac{N}{\left(1+r_{t}\right)^{5}}
$$  

into a discount bond with a 5-year maturity. The rest of the principal would be invested in a properly chosen call or put option. This simple product is shown in Figure 20.1.  

At the simplest level, the guaranteed product consists of a zero-coupon bond and one or more options.2 Suppose $S_{t}$ denotes the value of an underlying security. This security can essentially be anything from stocks to credit index tranches or the value of some hedge fund investment. We can then write the following contractual equation:  

![](837574c40d2598a173e52db3a0b78151e8c6c6ee038db59e01321dae013788c0.jpg)  

Suppose an investor invests the amount $N=100$ directly to a basket of options over a $T.$ year maturity. Then, options being risk investments and investors having limited risk management capabilities, part of the principal may be lost if these options expire out-of-the-money. On the other hand, if the yield on a. $T.$ -maturity zero-coupon bond is. $r\%$ and if the same investor invests, at time $t_{0}$ , a carefully chosen amount. $P V_{t_{0}}$ in this bond, the security will be worth 100 in 5 years:  

$$
P V_{t_{0}}\left(1+r_{t_{0}}\right)^{T}=N
$$  

The payoff of the zero-coupon bond is illustrated in Figure 20.1a as a function of the share, that is the underlying of the option. Thus the investor can allocate. $P V_{t_{0}}$ to buy a bond and will still have. $N-P V_{t_{0}}$ to invest in (a basket of) options. Depending on the level of volatility, the level of. $r$ and  

a Payoff of a zero-coupon bond as a function of the share price  

![](62f841eb24f1a6c661cd927df7a1ca6de1ba1b1363258c22eb2073c6bfe031ad.jpg)  

b) Payoff of a long call option position  

![](94bc8e4afc43f1acd07399e3f83ab4e99c0b3956ec853970ac2888dd09c660cc.jpg)  

(c)Payoff of a long zero-coupon bond and long call option position  

![](0c4fa546d5be438bf5107007522a148e552df4acf6d3a7e2b4117f33a1db1d2f.jpg)  

# FIGURE 20.1  

Zero-coupon bond and long call position.  

the expiration dates under consideration, this residual will provide an exposure-the growth of $S_{t}$ In fact, let $g_{t_{i}}$ be the percentage rate of change in $S_{t}$ during the interval $[t_{i},t_{i-1}]$  

$$
g_{t_{i}}=\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}
$$  

Then the investor's exposure will be $\lambda g_{t_{i}}S_{t_{0}}$ , where $\lambda$ is the familiar participation rate. In the case of structured products, it is the bank that makes all these calculations, selects a structure with a high participation rate, and sells the principal protected security as a package to the investor.  

According to this, in the simplest case the bank will buy a. $P V_{t_{0}}$ amount of the zero-coupon bond for every invested 100, and then options will be purchased with the rest of the principal, that is 100 - PV, or 100  (1 - a+n)  

# EXAMPLE  

An investor has the principal $N=100$ . The observed yield on a 5-year zero-coupon treasury is. $4.50\%$ . If the investor invests 80.2451 in this bond, the security will be worth 100 in 5 years:  

$$
80.2451(1+.045)^{5}=100
$$  

Thus the investor can allocate 80.2451 to buy a bond and will still have 19.7549 to invest in options.3  

In the above example, assume that the investor invests in S&P500 options. After buying the zero-coupon bond, the structurer can invest $\$19.7549$ in S&P 500 options and pay for administration, costs, and commissions. Assume that a 5-year S&P500 call option costs $\$22.19$ . We also add $\$2$ for administration and margin costs. Thus the investor will benefit from a participation rate of $80\%$ . The participation rate is calculated as $(19.7549-2)/22.19$ . Consider two scenarios. In the optimistic scenario, we assume that the S&P500 goes up by $20\%$ over the course of 5 years. In this case, the investor will achieve $16\%$ $\phantom{'}=80\%\times20\%)$ . The structured product would redeem at maturity at $116\%$ of the principal ( $100\%$ from the zero-coupon bond and a $16\%$ gain from the option). In the pessimistic scenario, we assume the S&P500 would fall by $40\%$ . In this case, the call option would expire worthless and the investor would receive $100\%$ of his capital back.  

The general idea is simple. The problems arise in implementation and in developing more refined ways of doing this. In practice, several problems can occur..  

First, zero-coupon interest rates for a maturity of. $T$ may be too low. Then the zero-coupon bond. may be too expensive and not enough "excess" may be left over to invest in options. For example, during the years 2011-2013, 5-year USD Treasury rates were around. $1.25\%$ . This leaves only:  

$$
100-{\frac{100}{\left(1+0.02\right)^{5}}}=6.02
$$  

to invest in the option basket. Once we factor out the fees paid for such products, which could be several percentage points, the amount that can be invested in the option goes down even more.4 Depending on the level of volatility, such an investment may not be able to secure any meaningful participation rate.  

Second, options on the underlying where exposure is desired may not exist. For example, considering hedge funds, there are few options traded on these risks. Yet, an investor may want exposure to hedge fund activity, or, say, to credit tranches without risking (part of) his or her principal.  

Third, even if options on the underlying risk exist, the set of available maturities is limited and longer-term maturities are often illiquid. To address this, hedgers may have to resort to rolling a sequence of short maturity options which can result in a highly path-dependent strategy since the cost of the rolling strategy will depend on changing market conditions..  

Fourth, irrespective of the level of interest rates, the options may be too expensive, depending. on the level of volatility. This may, again, not secure a meaningful participation rate.  

The following reading illustrates how the behavior of various market participants that buy anc sell volatility affects implied volatility levels and thus the cost of options..  

# EXAMPLE  

A resurgence in close-out activity has been triggered by a sharp rise in long-dated implied. volatility during the first five months of 1998. Having declined significantly throughout November and December last year, three-year index volatility levels have risen steadily. since January.  

The trend closely mirrors changes in implied volatility experienced last year. Implied volatility levels first took off in 1997, driven by a surge in the market for guaranteed equity funds. Arrangers of the funds bought longer-dated options from banks to hedge the guarantee embedded in retail products. No natural sellers of long-dated volatility were available, and a short squeeze in volatility quickly developed, pushing up rates.  

Market professionals asserted last week that the short squeeze was the result of a vicious circle. Banks closing-out their short option positions had pushed volatility even higher, which in turn has prompted other houses to close out their positions. "It's something of a chain reaction. I think most professionals are fairly concerned," said one head of equity derivatives trading in London.  

Although in agreement over the severity of the volatility squeeze, market professionals were divided on its cause or solution. Some professionals alleged that bank risk controllers had exacerbated the volatility squeeze by setting too tight risk limits. \*This is a typical example of accountants sticking to their guns, whatever happens. It's a unique situation which will not last and they should take account of that," said one.  

# History is Bunk?  

Professionals also pointed to factors that they felt would eventually alleviate the demand/supply imbalance. Several market participants said they thought high volatility was a temporary phenomenon; they argued that volatility is mean-reverting and that implied volatility rates would soon descend towards (much lower) historical levels.   
The discrepancy between the two views of volatility lies at the heart of conflicting views over the market's development. Implied volatility rates are calculated by feeding current option prices into an option model, and so are a function of the supply and demand in volatility. In contrast, historical volatility rates are calculated from previous equity market movements. Three-year FTSE 100 historical volatility levels are around. $1l\%$ The yawning gap between historical and implied volatility rates has already created trading.   
opportunities for unconventional suppliers of volatility. While dealers remain naturally short volatility, other trading firms have a more flexible approach to volatility rates. Hedge funds had already been seeking to sell long-dated volatility. with the view that imnlied levels would descend to historical rates.  

Equity derivatives professionals asserted that lower participation rates were the direct result of the rise. in implied volatility. Guaranteed products are a mixture of a long position in equities-usually achieved. through one or more futures contracts-and an option used to provide a floor on possible losses. If the floor is more expensive, the upside offered to the buyer of the guaranteed product will be reduced to lower the overall cost of the product.. According to several market professionals, the new lower participation rates are a function of the. volatility squeeze and are thus here to stay. "I think participation rates will decline and so reduce demand. for volatility. It's simply the market finding an equilibrium," said one equity derivatives marketer.  

(Thomson Reuters IFR, June 1998)  

The reading shows that high implied volatility levels increase the price of call options which are one of the building blocks in capital guaranteed products. The higher costs means that the participation rates offered by such products necessarily decline.  

The capital guaranteed products described above were followed in the early 1990s with structures that essentially complicated the long option position. Some products started to "cap"' the upside. The structure would consist of a discount bond, a long call with strike $K_{L}$ and a short call with strike $K_{U},$ with $K_{L}<K_{U}.$ This way, the premium obtained from selling the second call would be used to increase the participation rate, since more could be invested in the long option. This is shown in Figure 20.2. Figure 20.2a shows the zero-coupon bond payoff. Figure 20.2b and c shows the payoffs of a long call position with strike price $K_{L}$ , a short call position with strike price $K_{U}$ Figure 20.2d shows the payoff of the portfolio consisting of the zero-coupon bond and the two call options. Other products started using Asian options. The gains of the index to be paid to the investor would be calculated as an average of the gains during the life of the contract.  

Late 1990s started seeing correlation products. A worst of structure would pay at maturity, for. example, $170\%$ of the initial investment plus the return of a worst performing asset in a basket of say 10 stocks or commodities. Note that this performance could be negative, thus the investor could receive ${<}170\%$ return. However, such products were also principal protected and the investor. would still recover the invested 100 in the worst case..  

In the best of case, the investor would receive the return of the best performing stock or com-. modity given a basket of stocks or commodities. The observation period could be over the entire. maturity or could be annual. In the latter case, the product would lock in the annual gains of the best-performing stock, which can be different every year. Mid-2000s brought several new versions. of these equity-linked structured instruments including reverse convertibles which we discuss in. more detail below, but first we consider the main tools underlying the products..  

# 20.2.2 THE TOOLS  

Equity structured products are manufactured using a relatively small set of tools that we will review in this section. We will concentrate on the main concepts and instruments: basically five main types. of instruments and a major conceptual issue that will recur in dealing with equity structured. products.  

a Payoff of a zero-coupon bond with face value 100  

![](0e3cac5f714fc38e5030b7fff9617c4e37ac40330b8e64684a7efe8684a3f2a0.jpg)  

# FIGURE 20.2  

Zero-coupon bond, long call and short call.  

First there are vanilla call or put options. These were discussed in Chapters 9 and 11 and are. not handled here. The second tool is touch or digital options, discussed in a later chapter, but we'll provide a brief summary below.  

Touch or digital options are essentially used to provide payoffs (of cash or an asset) if some levels are crossed. Most equity structured products incorporate such levels. The third tool is reverse convertibles, which are conceptually related to convertible bonds with the important difference that they embed an option that is conveyed to the issuer and not the holder of the option.  

The fourth tool is new; it is the so-called rainbow options. These are options written on the maximum or minimum of a basket of stocks. They are useful since almost all equity structured products involve payoffs that depend on more than one stock. The fifth tool is the cliquet. These options are important prototypes and are used in buying and selling forward starting options. Note that an equity structured product would naturally span over several years. Often the investor is offered returns of an index during a future year, but the initial index value during these future years  

![](98d5179d3d89f18a180ff270d53b1e53e34ec407e6410308ae5f6e1515c8e030.jpg)  

# FIGURE 20.3  

Payoff of a one-touch option.  

would not be known. Hence, such options would have forward-setting strikes and would depend on forward volatility. Forward volatility plays a crucial role in pricing and hedging structured products,. both in equity and in fixed-income sectors.5.  

# 20.2.2.1 Touch and digital options  

Touch options are similar to the digital options introduced in Chapter 11. European digital options have payoffs that are step functions. Digital or binary options are contracts that pay out a fixed amount or nothing at expiration, depending on the settle price of the underlying asset. If, at the maturity date, a long digital option ends in-the-money, the option holder will receive a predetermined amount of cash, or, alternatively, a predetermined asset. As discussed in Chapter 11, under the standard Black-Scholes assumptions the digital option value will be given by the risk-adjusted probability that the option will end up in-the-money. In particular, suppose the digital is written on an underlying. $S_{t}$ and is of European style with expiration $T$ and strike $K$ The payoff is. $\$R$ and riskfree rates are constant at $r.$ as shown in Figure 20.3. Then the digital call price will be given by  

$$
C_{t}=e^{-r(T-t)}{\tilde{P}}(S_{T}>K)~R
$$  

where $\tilde{P}$ denotes the proper risk-adjusted probability. Digital options are standard components of structured equity products and will be used below.  

A one-touch option is a slightly modified version of the vanilla digital. A one-touch call is shown in Figure 20.3. The underlying with original price $S_{t_{0}}<K$ will give the payoff $R=\$1$ if (i) at expiration time $T_{:}$ the price of the underlying is above the strike price $(K<S_{T})$ and (ii) if the level $K$ is breached only once.  

Otherwise the payoff will be zero. A previous chapter discussed a double-no-touch (DNT) option which is often used to structure wedding cake structures for FX markets..  

One advantage of digital options from the seller's point of view is that the maximum possible. downside is known in advance. From the point of view of a bank or structure this implies that selling digital options is much more risk controlled and less negatively skewed as a strategy than a typical short volatility position. On the other hand, touch and digital options are less liquid than vanilla options since it is more difficult for market makers to hedge the digital options near the strike price around expiry. Some digital options are now exchange traded while they were previously OTC instruments. In 2008, the American Stock Exchange (Amex) and the CBOE launched exchange-traded European cash-or-nothing binary options. The more complicated tools are the rainbow options and the concept of forward volatility. We will discuss them in turn before we start discussing recent equity structured products.  

# 20.2.2.2 Rainbow options  

The term rainbow options is reserved for options whose payoffs depend on the trajectories of more than one asset price. Obviously, they are very relevant for equity products that have a basket of stocks as the underlying. The major class of such options is those that pay the worst-of or best-of the $n$ underlying assets. Suppose $n=2$ ; two examples are  

$$
\mathrm{Min}[S_{T}^{1}-K^{1},S_{T}^{2}-K^{2}]
$$  

where the option pays the smaller of the two price changes on two stocks and  

$$
\mathrm{Max}[0,S_{T}^{1}-K^{1},S_{T}^{2}-K^{2}]
$$  

where the payoff is the larger one and it is floored at zero. Needless to say the number of underlying assets $n$ can be larger than 2, although calibration and numerical burdens make a very large. $n$ impractical.  

# 20.2.2.3 Reverse convertibles  

In the previous chapter, we saw that convertible bonds can be viewed as a portfolio of straight debt and an embedded call option. This typically implies that the issuer can issue the debt at a lower coupon than would be the case with straight debt alone. For a bond investor who is seeking to participate in the upside of the underlying equity or who is exploiting potentially undervalued volatil-. ity a convertible bond can be the right investment. However, for an investor who is seeking a high yield and is not concerned with participating in the upside a convertible bond is less attractive than the straight debt. How could a financial engineer create a product that pays a coupon that is higher than that of straight debt? The answer is that if the product embedded a short put position instead of a long call position, the buyer issuer of the instrument would receive a long put option from the buyer of the product and the issuer could in return compensate the buyer of the product with a higher coupon. In other words, the embedded put is financing the higher coupon. Such securities are called reverse convertibles. The put option is written on an underlying stock (or basket of stocks) $S_{t}$ and the conversion is not optional, but occurs automatically if. $S_{t}$ falls below a certain level $K$ which can be viewed as the strike price of the put option. The underlying stock or basket of stocks is referred to as reference shares.  

Reverse convertibles have been mainly sold as structured products to retail investors. Reverse. convertibles embed a put option that depends on the underlying stock volatility in a similar way that the embedded call option in a convertible bond depends on implied volatility. The fundamental difference between convertible bonds and reverse convertibles is, however, that convertible bonds offer participation in the upside of the underlying, while reverse convertibles offer participation in the downside of the underlying. Moreover, the conversion option is conveyed to the issuer, not the holder of the reverse convertible since the holder implicitly writes a put option on the underlying to. the issuer. While the coupon payments in a reverse convertible may be considerably higher than. the yields available in the bond market, reverse convertibles carry a higher risk than bonds because repayment of the principal amount is not guaranteed.  

The payoff of a basic reverse convertible at maturity depends on two scenarios:  

Scenario 1 $:S_{T}>K$ The underlying stock at maturity is above the strike price. In this case, the holder receives the coupon and $100\%$ of the original investment.   
Scenario 2: $S_{T}{<}K$ The underlying stock at maturity is below the strike price. The holder receives a predetermined number of stocks.  

For example, consider the buyer of a reverse convertible linked to the share price of ABC. If the stock price of ABC was initially 100, and in 1 year the stock price was 120 then scenario 1 obtains. The holder of a 1000 note would receive 100 for the. $10\%$ coupon, and the 1000 principal. Scenario 2 would occur if the stock price was 80 at the end of 1 year. Then the holder of the note would receive 100 for the coupon and 800 worth of stock. In other words, this would lead to a capital loss. Figure 20.4 illustrates the payoff profile of a typical reverse convertible. Figure 20.4a shows the payoff of a zero-coupon bond. Figure 20.4b shows the profit and loss from a short put option position with a strike price $K.$ The write of the put option receives the put option. premium if the underlying. $S_{t}$ remains above the strike price. $K$ If we combine the zero-coupon. bond with the short put position we obtain the profit and loss diagram for the reverse convertible which shows that the gain is higher than for a zero-coupon bond since the put option premium enhances the coupon.  

Often the embedded option is not a simple option, but a knock-in option. This implies that the scenarios above are different in the sense that the condition is that the stock price $S_{t}$ remains above the strike price at any point in time until maturity. The knock-in level is often set at $70-80\%$ of the initial reference price.  

When are reverse convertibles typically bought by investors? In a low interest rate and high. market volatility environment reverse convertibles are popular since they provide a way for investors to receive an enhanced yield. However, the products' popularity does not mean that investors fully understand the price of the embedded put option that they are writing to the issuer of the product. If market volatility is high it is possible that the embedded put is very valuable and that the structure does not pass all of its value onto the buyer in the form of a coupon. In this case, the buyer takes on a large downside risk and may be surprised that in an equity market downturn the product leads to losses. Thus, investors should carefully compare the yield offered by the  

![](9d9324fd71b2dc13763f9819fe6d795f5b8386970b72f2d208088a4b5ca00077.jpg)  

# FIGURE 20.4  

Reverse convertible.  

reverse convertible to money market rates, since if the two diverge significantly it may mean that the reverse convertible embeds significant risk.  

In the 1990s, reverse convertibles were often issued with embedded short at-the-money put. options. The downside of such products was that investors would suffer losses if the underlying was. below the initial level. As investor demand waned in response to the market downturn following the. bursting of the tech bubble, a new generation of products was developed that embedded a short atthe-money down-and-in put option. The barrier feature provided investors with additional protection. since the put option would not be triggered unless the (down) barrier was reached. Such barrier. reverse convertibles are popular structured products in Europe and in the United States. For the structurer, the barrier feature poses new challenges in practice, however, since the structure requires hedging long-dated equity barrier risks (with maturities between 3 and 5 years) and the Greeks of the. products near the barrier tended to be unstable as discussed in the context of digital options above. Moreover, the large number of structured products and the relative illiquidity of the underlying equity market made hedging such products more difficult than is the case for FX products, for example..  

Some structured products including reverse convertibles have embedded call features. Thus, such products have call and conversion features. Banks that issue structured products refer to these products with call features as autocallable, which is the abbreviation of automatically callable. This feature is often found in structured products with longer maturities. Such products are callable by the issuer if the reference asset is at or above its initial level on a specified observation date.  

This is effectively an option for the issuer to redeem the product early. In this case, the investor.   
receives the principal amount of their investment plus a predetermined premium. Similar to callable.   
bonds, this call option conveyed to the issuer makes the product less attractive to the holder and.   
therefore the yield on autocallables can be higher than for alternatives without this feature.   
Autocallable features are often found in capital guaranteed notes and barrier reverse convertibles..  

Structured products do not just contain hedging risks from the perspective of the structurer or. issuer, but also legal risks. There are many examples in the United States, Europe, and Asia/Pacific when buyers of structured products suffered losses and then went to court against the issuers of the products. Therefore, it is not just in the interest of the buyers but also in the interest of the structurers to understand the consequences of any embedded downside in the products. In some instances, banks settle law suits in order not to jeopardize future client relationships even if the products were properly marketed and sold. In 2013, IOscO (the International Organization of. Securities Commissions) published a report on the Regulation of Retail Structured Products. The objective of the report is to enhance investor protection. It outlines a range of regulatory options. that securities regulators can use to regulate retail structured products. The following reading pro-. vides one example of regulatory issues and risks associated with structured products. The example is based on reverse convertibles discussed in the section..  

# EXAMPLE: REVERSE CONVERTIBLES IN LIMBO  

Issuance of lira-denominated reverse convertibles ground to a halt in response to growing uncertainty over their tax status under Italian law. The Italian authorities are concerned that investors may buy the instruments in the belief that they are capital-protected fixed income instruments, when, in fact, they would be exposed to equity downside risk.  

According to warrant market participants, about a month ago the Bank of Italy warned potential issuers of lira-denominated reverse convertibles that they might be classified as "abnormal securities." If classified as such, the coupon on the securities would be taxed at $27\%$ instead of $12.5\%$ the rate for normal fixed income and derivative structures. Since then, lira reverse convertible issuance has dwindled as structurers await a decision on their status.  

Market commentators said the Bank of Italy was concerned about the lack of principal protection in the structure. Reverse convertibles generate a yield considerably higher than that of vanilla bonds by embodying a short equity put position.  

The investor receives a high coupon and normal bond redemption as long as a specific equity price is above a particular level at maturity. However, if the equity falls below the specified mark, then the investor is forced to receive the physical equity instead of the normal bond principal.  

As a result, the buyer of the reverse convertible could end up with a long stock position at a low level, which would mean an erosion of initial principal. In contrast, the buyer of vanilla bond paper is assured of getting back the initial principal investment.  

(Thomson Reuters IFR, May 1998)  

The above reading illustrates the embedded downside risk in reverse convertible products. The. issuer of the products will typically exercise the put option if the stock price is less than the strike. price. As a result the bond holders or buyers of the reverse convertibles receive the stock under. adverse conditions. The concern is that not all investors understand that even if the issuer does not default, the holders may suffer from substantial losses.  

# 20.2.2.4 Cliquets  

Cliquet options are frequently used in engineering equity and FX-structured products. They are also quite useful in understanding the deeper complexities of structured products. Cliquets are also known as ratchet options due to the resetting strikes in the structure.  

A cliquet is a series of prepurchased options with forward setting strikes. The first option's strike price is known but the following options have unknown strike prices. The strike price of. future options will be set according to where the underlying closes at the end of each future subperiod. The easiest case is at-the-money options. At the beginning of each observation period, the. strike price will be the price observed for. $S_{t_{i}}$ . The number of reset periods is determined by the. buyer in advance. The payout on each option is generally paid at the end of each reset period..  

At reset dates, the option locks in the difference between the old and new strikes and pays it out as a profit. If the stock has moved in such a way during the preceding period that one of the com-. ponent options expires out-of-the-money there will be no profit, and the investor will lose the pre-. mium corresponding to that period.  

# EXAMPLE  

A five-year cliquet call on the S&P with annual resets is shown in Figure 20.5. Essentially the cliquet is a basket of five annual at-the-money spot calls.  

The initial strike is set at, say, 1419, the observed value of the underlying at the purchase date. If at the end of the first year, the S&P closes at 1450, the first call matures in-themoney and the payout is paid to the buyer. Next, the call strike for the second year is reset at 1450 and so on.  

![](c636a1350af2a8c42867b24ad3f55ffec25fb918c6b5a027cf3c68007387f6fa.jpg)  

# FIGURE 20.5  

Cliquet.  

To see the significance of a 5-year cliquet, consider two alternatives. In the first case, one buys a 1-year at-the-money call, then continues to buy new at-the-money calls at the beginning of future years four times. In the second case, one buys a 5-year cliquet. The difference between these is that the cost of the cliquet will be known in advance, while the premium of the future calls will be unknown at $t_{0}$ . Thus a structurer will know at $t_{0}$ what the costs of the structured product will be only if he uses a cliquet.  

Consider a 5-year maturity again. The chance that the market will close lower for 5 consecutive years is, in general, lower than the probability that the market will be down after 5 years. If the market is down after 5 years, chances are it will close higher in (at least) one of these 5 years. It is thus clear that a cliquet call will be more expensive than a vanilla at-the-money call with the same final maturity.  

One of the selling points that sellers of cliquet options point to is that when volatility is expected to rise investors can lock in profits periodically rather than risk losing gains that have accumulated. An investor that takes the view that the underlying risky asset will go up or down over time, but does not have a view about the precise timing may see a cliquet structure as a better way of locking in profits. One recent example of a cliquet structure is market-linked certificates of deposit (CDs) in the US structured product market.  

The important point is that cliquet needs to be priced using the implied forward volatility surface. Once this is done the cliquet premium will equal the present value of the premiums for the future options.  

# 20.2.3 FORWARD VOLATILITY  

Forward volatility is an important concept in structured product pricing and hedging. This is a complicated technical topic and can only be dealt with briefly here. Consider a vanilla European call written at time $t_{0}$ . The call expires at T, $t_{0}<T$ and has a strike price $K.$ To calculate the value of this call we find an implied volatility and plug this into the Black-Scholes formula. This is called the Black-Scholes implied volatility.  

Now consider a vanilla call that will start at a later date at $t_{1}$ $t_{0}<t_{1}$ . Yet, we have to price the option at time $t_{0}$ The expiration is at $t_{2}$ . More important, the strike price of the option denoted by $K_{t_{1}}$ is unknown at $t_{0}$ and is given by  

$$
K_{t_{1}}=\alpha S_{t_{1}}
$$  

where $0<\alpha\leq1$ is a parameter. It represents the moneyness of the forward starting call and hence. is an important determinant of the option's cost. The forward call will be an ATM option at $t_{1}$ if $\alpha=1$ . Assuming deterministic short rates $r$ we can write the forward start option value at $t_{0}$ as  

$$
C\big(S_{t_{0}},K_{t_{1}},\sigma(t_{0},~t_{1},~t_{2})\big)=e^{r(t_{2}-t_{0})}E_{t_{0}}^{\tilde{P}}\big[(S_{t_{2}}-\alpha S_{t_{1}})^{+}\big]
$$  

where $C(.)$ denotes the Black-Scholes formula and $\sigma(t_{0},t_{1},t_{2})$ is the forward Black-Scholes volatility. The volatility is calculated at. $t_{0}$ and applies to the period $[t_{1},~t_{2}]$ .We can replace the (unknown) $K_{t_{1}}$ , using Eq. (20.10) and see that the cliquet option price would depend only on the current $S_{t_{0}}$ and on forward volatility.  

Thus the pricing issue reduces to calculating the value of the forward volatility given liquid vanilla option markets on the underlying $S_{t}$ This task turns out to be quite complex once we go beyond very simple characterizations of the instantaneous volatility for the underlying process. We consider two special cases that represent the main ideas involved in this section. For a comprehensive treatment we recommend that the reader consult Gatheral (2006).  

# EXAMPLE: DETERMINISTIC INSTANTANEOUS VOLATILITY  

Suppose the volatility parameter that drives the $S_{t}$ process is time dependent, but is deterministic in the sense that the only factor that drives the instantaneous volatility $\sigma_{t}$ is the time $t$ In other words we have the risk-neutral dynamics,.  

$$
\mathrm{d}S_{t}=r S_{t}+\sigma_{t}S_{t}\mathrm{d}W_{t}
$$  

Then the implied Black-Scholes volatility for the period $[t_{0},T_{1}]$ is defined as  

$$
\sigma_{B S}^{T_{1}}=\sqrt{\frac{1}{T_{1}-t_{0}}}\int_{t_{0}}^{T_{1}}\sigma_{t}^{2}\mathrm{d}t
$$  

In other words, $\sigma_{B S}^{T_{1}}$ is the average volatility during period $[t_{0},T_{1}]$ . Note that under these conditions the variance of $S_{t}$ during this period will be  

$$
{\left(\sigma_{B S}^{T_{1}}\right)}^{2}(T_{1}-t_{0})
$$  

Now consider a longer time period defined as $[t_{0},T_{2}]$ with $T_{1}<T_{2}$ and the corresponding implied volatility  

$$
\sigma_{B S}^{T_{2}}=\sqrt{\frac{1}{T_{2}-t_{0}}}\int_{t_{0}}^{T_{2}}\sigma_{t}^{2}\mathrm{d}t
$$  

We can then define the forward Black--Scholes variance as  

$$
\big(\sigma_{B S}^{T_{2}}\big)^{2}(T_{2}-t_{0})-\big(\sigma_{B S}^{T_{1}}\big)^{2}(T_{1}-t_{0})
$$  

Plug in the integrals and take the square root to get the forward implied Black-Scholes volatility from time $T_{1}$ to time $T_{2},\sigma_{B S}^{f}~(\dot{T}_{1},T_{2})$  

$$
\sigma_{B S}^{f}(T_{1},T_{2})=\sqrt{\frac{1}{T_{2}-T_{1}}\int_{T_{1}}^{T_{2}}\sigma_{t}^{2}\mathrm{d}t}
$$  

The important point of this example is the following: In case the volatility changes deterministically as a function of time $t_{:}$ the forward Black-Scholes volatility is simply the forward volatility.. Hence it can be calculated in a straightforward way given a (deterministic) volatility surface. What intuition suggests is correct in this case. We now see a more realistic case with stochastic volatility where this straightforward relation between forward Black-Scholes volatility and forward volatility disappears.  

# EXAMPLE: STOCHASTIC VOLATILITY  

Suppose $S_{t}$ obeys  

$$
\mathrm{d}S_{t}=r S_{t}+\sigma I_{t}S_{t}\mathrm{d}W_{t}
$$  

where $I_{t}$ is a zero-one process given by  

$$
I_{t}={\left\{\begin{array}{l l}{0.30{\mathrm{with~probability~}}0.5}\ {0.1{\mathrm{with~probability~}}0.5}\end{array}\right.}
$$  

Thus, we have a stochastic volatility that fluctuates randomly (and independently of $S_{t}$ between high and low volatility periods. Then, the average variances for the periods $[t_{0},T_{1}]$ and $[t_{0},T_{2}]$ will be given respectively as  

$$
\begin{array}{c}{(\sigma^{T_{1}})^{2}(T_{1}-t_{0})=\displaystyle\int_{t_{0}}^{T_{1}}E[(\sigma(I_{t}){\bf d}W_{t})^{2}]}\ {=(T_{1}-t_{0})~(0.3)^{2}}\end{array}
$$  

which implies that forward volatility will be 0.2.  

Yet, the forward implied Black-Scholes volatility will not equal 0.2.  

According to this, whenever instantaneous volatility is stochastic, calculating the Black-Scholes.   
forward volatility will not be straightforward. Essentially, we would need to model this stochastic volatility and then, using Monte Carlo, price the vanilla options. From there we would back out the.   
implied Black-Scholes forward volatility. The following section deals with our first example of.   
equity structured products where forward volatility plays an important role..  

# 20.2.4 PROTOTYPES  

The examples of major equity structured products below are selected so that we can show the major methods used in this sector. Obviously, these examples cannot be comprehensive.  

We first begin with a structure that imbeds a cliquet. The idea here is to benefit from fluctuations in forward equity prices. Forward volatility becomes the main issue. Next we move to structures that contain rainbow options. Here the issue is to benefit from the maxima or minima of stocks in a basket. The structures will have exposure to correlation between these stocks and the investor will be long or short correlation. Third, we consider Napoleon-type products where the main issue becomes hedging the forward volatility movements. With these structures, the volatility exposure will be convex and there will be a volatility gamma. If these dynamic hedging costs involving volatility purchases and sales are not taken into account at the time of initiation, the structure will be mispriced. Such dynamic hedging costs involving volatility exposures is another important dimension in equity structured products.  

![](26ccf360d6a2541df2202982dd82951d9d68a38ae3ef3ce7185e1dcbd9ed50c4.jpg)  

# FIGURE 20.6  

Structured product consisting of T-note and cliquet on iTraxx.  

# 20.2.4.1 Case I: A structure with built-in cliquet  

Cliquets are convenient instruments to structure products. Let $S_{t}$ be an underlying like stock indices or commodities or FX. Let $g_{t_{i}}$ be the annual rate of change in this underlying calculated at the end of year.  

$$
g_{t_{i}}=\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}
$$  

where $t_{i},i=1,2,...,n$ are settlement dates. There is no loss of generality in assuming that $t_{i}$ is denoted in years.  

Suppose you want to promise a client the following: Buying a 5-year note, the client will receive the future annual returns $\lambda g_{t_{i}}N$ at the end of every year $t_{i}$ The $0<\lambda$ is a parameter to be determined by the structurer. The annual returns are floored at zero. In other words, the annual payoffs will be  

$$
P_{t_{i}}=\mathbf{Max}[\lambda g_{t_{i}}N,0]
$$  

$\lambda$ is called the participation rate.  

It turns out that this structure is less straightforward than appears at the outset. Note that the structurer is promising unknown annual returns, with a known coefficient $\lambda$ at time $t_{0}$ . In fact, this is a cliquet made of one vanilla option and four forward starting options. The forward starting options depend on forward volatility. The pricing should be done at the initial point $t_{0}$ after calculating the forward volatility for the intervals $t_{i}-t_{i-1}$ . Figure 20.6 shows how one can use cliquets.  

to structure this product. In this structured note, the structurer will take the principal. $N_{:}$ deposit part of it in a 5-year Treasury note, and with the remainder buy a 5-year cliquet. The underlying risky assets in the example are assumed to be the iTraxx index, but it could also be an equity index such as the S&P500 or the MSCI World. As the figure shows the cliquet consists of five forward start options. The strike price of the first option is. $K_{0}$ and since the price of the underlying is $S_{t1}>K_{0}$ at date $t_{1}$ , the first option is exercised and pays out. The second option has a strike price of. $K_{1}=S_{t1}$ and at date $t_{2}$ it is out-of-the-money. The third option does not pay out either. The fourth and fifth. options pay out. We would like to discuss this structure in more detail..  

First let us incorporate the simple principal protection feature. Suppose 5-year risk-free interest rates are denoted by $r\%$ . Then the value at time $t_{0}$ of a 5-year default-free Treasury bond will be. given by  

$$
P V_{t_{0}}=\frac{100}{\left(1+r\right)^{5}}
$$  

Clearly this is less than 100. Then define the cushion $C u_{t_{0}}$  

$$
C u_{t_{0}}=100-P V_{t_{0}}
$$  

Note that  

$$
0<C u_{t_{0}}
$$  

and that these funds can be used to buy options. However, note that we cannot buy any option; instead we buy a cliquet since. $\lambda$ times the unknown annual returns are promised to the investor.. The issue is how to price the options on these unknown forward returns at time. $t_{0}$ . To do this, forward volatility needs to be calibrated and substituted in the option pricing formula which, in general, will be Black-Scholes..  

With this product, if the annual returns are positive the investor will receive. $\lambda$ times these returns. If the returns are negative, then the investor receives nothing. Note that even in a market where the long-run trend is downward, some years the investor may end up getting a positive. return.  

# 20.2.4.2 Case II: Structures with mountain options  

Structures with payoffs depending on the maximum and minimum of a basket of stocks are generally denoted as mountain options. This type of exotic option combines features of basket options and range options and Societe Generale was one of the first sellers of such options in the late 1990s. There are several examples. We consider a simple case for each important category.  

# 20.2.4.2.1 Altiplano  

Consider a basket of stocks with prices. $\{S_{t}^{1},~...~,~S_{t}^{n}\}$ A level $K$ is set. For example,. $70\%$ of the. initial price. The simplest version of an Altiplano structure entitles the investor to a "large' coupon. if none of the. $S_{t}^{i}$ hits the level. $K$ during a given time period $[t_{i},t_{i-1}]$ . Otherwise, the investor will receive lower coupons as more and more stocks hit the barrier. Typically, once three to four stocks hit the barrier the coupon becomes zero. The following is an example..  

# EXAMPLE: AN ALTIPLANO  

Currency: Eur; Capital guarantee: $100\%$ ; Issue price: 100.   
Issue date: 01-01-2014; Maturity date: 01-01-2019   
Underlying basket: {Pepsico, JP Morgan Chase, General Motors, Time Warner, Seven-Eleven} Annual coupons: Coupon $=15\%$ if no stocks settle below. $70\%$ of its reference price on coupon payment dates.   
Coupon $=7\%$ if one stock settles below thes. $70\%$ limit.   
$\mathrm{Coupon}=0.5\%$ if more than one stock settles below the limit.  

Figure 20.7 shows how we can engineer such a product. Essentially, the investor has purchased a zero-coupon bond and then sold five digital puts. The coupons are a function of the premia for the digitals. Figure 20.7a shows the zero-coupon bond and Figure 20.7b shows the payoff and profit of the short digital put position. The put option premium can be used to enhance the coupon. Clearly this product can offer higher coupons if the components of the reference portfolio have higher volatility.  

![](3a99d87a85fd4ef1c8a7ebbd80f60fa72fc054ac43dfd223620298919307028f.jpg)  

# FIGURE 20.7  

Components of Altiplano.  

This product has an important property that may not be visible at the outset. In fact, the Altiplano investor will be long equity correlation, whereas the issuer will be short. This property is similar to the pricing of CDO equity tranches and will be discussed in detail later. Here we consider two extreme cases.  

Suppose we have a basket of. $k$ stocks ${S_{t}^{i},i=1,2,...,k}.$ For simplicity suppose all volatilities are equal to $\sigma$ . For all stocks under consideration, we define the annual probability of not crossing the level $K S_{t_{0}}$  

$$
P\big(S_{t}^{i},t\in[t_{0},t_{1}]>K S_{t_{0}}^{i}\big)=(1-p^{i})
$$  

for all $i$ and $t\in[t_{0},T]$ . Here the $(1-p^{i})$ measure the probability that the ith stock never falls below the level $K S_{t_{0}}$ . For simplicity let all $p^{i}$ be the same at $p$ . Then if $\cdot s_{t}^{i},i=1,2,\ldots$ are independent, we can calculate the probability of receiving the high coupon at the end of the first year as $(1-p)^{k}$ Note that as $k$ increases, this probability goes down.  

Now go to the other extreme case and assume that the correlation between $S_{t}^{i}$ becomes one. This means that all stocks are the same. The probability of receiving a high coupon becomes simply $1-p$ This is the case since all of these stocks act identically; if one does not cross the limit, none will. Since. $0<p<1$ with $k>1$ we have  

$$
(1-p)^{k}<(1-p)
$$  

Thus, the investor in this product will benefit if correlation increases, since the investor's probability of receiving higher coupons will increase..  

# 20.2.4.2.2 Himalaya  

The Himalaya is a call on the average performance of the best stocks within the basket. In one version, throughout the life of the option, there are preset observation dates, say $t_{1},t_{2},...,t_{n},$ at which the best performer within the basket is sequentially removed and the realized return of the removed stock is recorded. The payoff at maturity is then the sum of all best returns over the life of the product.  

# EXAMPLE: A HIMALAYA  

Currency: Eur; Issue price: 100.   
Issue date: 01-01-2013; Maturity date: 01-01-2019.   
Underlying basket: 20 stocks possibly from the United States and Europe.   
Redemption at Maturity:   
If the basket rose, the investor receives the maximum of the basket of remaining securities observed on one of the evaluation dates.   
If the basket declined, the investor receives the return of the basket of remaining securities observed on the last evaluation date..  

In this case, the return is related to the maximum or minimum of a certain basket over some. evaluation periods. Clearly, this requires writing rainbow options, including them in a structure, and then selling them to investors.  

# 20.2.4.3 Case III: The Napoleon and Vega hedging costs  

A Napoleon is a capital-guaranteed structured product which gives the investor the opportunity to earn a high fixed coupon each year, say, $c_{t_{0}}=10\%$ , plus the worst monthly performance in an underlying basket of. $k$ underlying stocks. $S_{t}^{i}$ . If $k$ is large there will be a high probability that the worst performance is negative. In this case, the actual return could potentially be much less than the coupon $c_{t_{0}}$  

The importance of Napoleon for us is the implication of dynamic hedging that needs to accom-. pany such products. The key issue is that Napoleon-type products cannot be hedged statically and require dynamic hedging. But the main point is that the dynamic hedging under question here is different than the one in plain vanilla options. In plain vanilla options, the practitioner buys and sells the underlying $S_{t}^{i}$ to hedge the directional movements in the option price. This dynamic hedg-. ing results in gamma gains (losses). What is being hedged in Napoleon-type products is the volatil-. ity exposure. The practitioner has to buy and sell volatility dynamically..  

These products have exposure to the so-called volatility gamma. The structurer needs to buy. option volatility when volatility increases and sell it when volatility decreases. This is similar to the gamma gains of a vanilla option discussed in Chapter 9, except that now it is being applied to the vol-. atility itself rather than the underlying price; hence the term volatility gamma. By buying volatility when vol is expensive and selling it when it is cheap, the structurer will suffer hedging costs. The. expected value of these costs needs to be factored in the initial selling price, otherwise the product. will be mispriced.  

# EXAMPLE: NAPOLEON HEDGING COSTS  

Suppose there is a basket of 10 stocksd $\left\{S_{t}^{1},\enspace\enspace\cdot\cdot\enspace,S_{t}^{10}\right\}$ whose prices are monitored monthly.e The investor is paid a return of. $10\%$ plus the worst monthly return among these stocks.  

Suppose now volatility is very high with monthly moves of, say,. $50\%$ . Then a 1 percentage point change in volatility does not matter much to the seller since, chances are, one of the stocks will have a negative monthly return which will lower the coupon paid. Thus the. seller has relatively little volatility exposure during high volatility periods..  

If, on the other hand, volatility is very low, say,. $9\%$ , then the situation changes. A. $1\%$ move in the volatility will matter, leading to a high volatility exposure.  

This implies that with low volatility the seller is long volatility, and with high volatility, the volatility exposure tends to zero. Hence the structurer needs to sell volatility when volatil-. ity decreases and buy it back when volatility increases in order to neutralize the vol of the position.  

This is an important example that shows the need to carefully calculate future hedging costs. If volatility is volatile, Napoleon-type structured products will have volatility gamma costs to hedging costs that need to be incorporated in the initial price.  

# 20.2.5 SIMILAR FX STRUCTURES  

It turns out that cliquets, mountain options, Napoleons, or other structured equity instruments can all be applied to FX or commodity sectors by considering baskets of currencies of commodities instead of stocks. Because of this close similarity, we will not discuss FX and commodity structures in detail. Wystub (2006) is a very good source for this.  
