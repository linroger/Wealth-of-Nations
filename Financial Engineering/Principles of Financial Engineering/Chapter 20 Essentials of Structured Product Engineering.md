# ESSENTIALS OF STRUCTURED 20 PRODUCT ENGINEERING  

# CHAPTER OUTLINE  

0.1 Introduction .. 696   
0.2 Purposes of Structured Products .. 697   
20.2.1 Equity Structured Products . 698   
20.2.2 The Tools .. 702   
20.2.2.1 Touch and digital options . 704   
20.2.2.2 Rainbow options... 705   
20.2.2.3 Reverse convertibles.. 705   
20.2.2.4 Cliquets.. 709   
20.2.3 Forward Volatility....... 710   
20.2.4 Prototypes . 712   
20.2.4.1 Case I: A structure with built-in cliquet. . 713   
20.2.4.2 Case II: Structures with mountain options .. 714   
20.2.4.3 Case III: The Napoleon and Vega hedging costs . 717   
20.2.5 Similar FX Structures.. 718   
0.3 Structured Fixed-Income Products... .. 718   
20.3.1 Yield Curve Strategies . 718   
20.3.2 The Tools ... 719   
20.3.3 CMS.. 719   
20.3.4 Yield Enhancement in Fixed-Income Products.. 720   
20.3.4.1 Method 1: Sell cap volatility . 721   
20.3.4.2 Method 2: Sell swaption volatility. 723   
20.4 Some Prototypes ... . 724   
20.4.1 The Components .. 724   
20.4.2 CMS-Linked Structures . . 725   
20.4.3 Engineering a CMS-Linked Note 726   
20.4.3.1 A contractual equation.. 726   
20.4.4 Engineering a CMS Spread Note .. 728   
20.4.5 The Engineering .. 729   
20.4.5.1 A contractual equation.. 733   
20.4.6 Some Other Structures. 733  

# 696 CHAPTER 20 ESSENTIALS OF STRUCTURED PRODUCT ENGINEERING  

20.5 Conclusions. 734   
Suggested Reading . 734   
Exercises . . 734  

# 20.1 INTRODUCTION  

Structured products consist of packaging basic assets such as stocks, bonds, and currencies together with some derivatives. The final product obtained this way will, depending on the product, (i) have an enhanced return or improved credit quality, (ii) lower costs of asset liability management for corporates, (iii) build in the views held by the clients, and (iv) often be principal protected.1  

Households do not like to build their own cars, computers, or refrigerators themselves. They prefer to buy them from the producers who manufacture and assemble them. Every complex product has its own specialists, and it is more cost effective to buy products manufactured by these specialists. The same is true for financial products. Investors, corporates, and institutions need solutions for problems that they face in their lives. The packaging solutions for investors’ and institutions’ needs are called structured products. “Manufacturers,” i.e., the “structurers,” put these together and sell them to clients. Clients consist of investment funds, pension funds, insurance companies, and individuals. Clients may have views on the near- or medium-term behavior of equity prices, interest rates, or commodities. Structured products can be designed so that such clients can take positions according to their views in a convenient way.  

Industrial goods such as cell phones and cars are constantly updated and improved. Again, the same is true for structured products. The views, the needs, or simply the risk appetite of clients change and the structurer needs constantly to provide new structured products that fit these new views. This chapter discusses the way financial engineering can be used to service retail clients’ particular needs.  

Financial engineering provides ways to construct any payoff structure desired by an investor. However, often these payoffs involve complex option positions, and clients may not have the knowledge, or simply the means, to handle such risks. Market practitioners can do this better. For example, many structured products offer principal protection or credit enhancements to investors. Normally, institutions that may not be allowed to invest in such positions due to regulatory reasons will be eligible to hold the structured product itself once principal protection is added to it. Providing custom-made products for clients due to differing views, risk appetite, or regulatory conditions is one way to interpret structured products and in general they are regarded this way. Hybrid securities that consist of several financial products such as a stock or bond plus a derivative are also referred to as structured notes.  

However, in this book our main interest is to study financial phenomena from the manufacturer’s point of view. This view provides a second interpretation of structured products. Investment banks deal with clients, corporates, and with each other. These activities require holding inventories, sourcing and outsourcing exposures, and maintaining books. However, due to market conditions, the instruments that banks are keeping on their books may sometimes become too costly or too risky, or sometimes better alternatives emerge. The natural thing to do is to sell these exposures to “others.” Structured products may be one convenient way of doing this. Consider the following example. A bank would like to buy volatility at a reasonable price, but suppose there are not enough sellers of such volatility in the interbank market. Then a structured product can be designed so that the bank can buy volatility at a reasonable price from the retail investor.  

In this interpretation, the structured product is regarded from the manufacturer’s angle and looks like a tool in inventory or balance sheet management. A structured product is either an indirect way to sell some existing risks to a client or an indirect way to buy some desired risks from the retail client. Given that bank balance sheets and books contain a great deal of interest rate and credit risk-related exposures, it is natural that a significant portion of the recent activity in structured products relates to managing such exposures.  

In this chapter, we consider two major classes of structured products. The first group is the new equity-, commodity- and FX-based structured products and the second is LIBOR-based fixed-income products. The latter are designed so as to benefit from expected future movements in the yield curve. We will argue that the general logic behind structured products is the same, regardless of whether they are LIBOR-based or equity-linked. Hence we try to provide a unified approach to structured products. In a later chapter, we will consider the third important class of structured products based on the occurrence of an event. This event may be a mortgage prepayment or, more importantly, a credit default. These will be discussed through structured credit products. Because credit is considered separately in a different chapter, during the discussion that follows it is best to assume that there is no credit risk.  

# 20.2 PURPOSES OF STRUCTURED PRODUCTS  

Structured products may have at least four specific objectives.  

The first objective could be yield enhancement—to offer the client a higher return than what is normally available. This of course implies that the client will be taking additional risks or foregoing some gains in other circumstances. For example, the client gets an enhanced return if a stock price increases up to $12\%$ . However, any additional gains would be forgone and the return would be capped at $12\%$ . The value of this cap is used in offering an enhanced yield.  

The second could be credit enhancement. In this case, the client will buy a predetermined set of debt securities at a lower default risk than warranted by their rating. For example, a client invests in a portfolio of 100 bonds with average rating BBB. At the same time, the client buys insurance on the first default in the portfolio. The cost of first debtor defaulting will be met by another party. This increases the credit quality of the portfolio to, say, $\mathrm{BBB^{+}}$ .  

The third objective could be to provide a desired payoff profile to the client according to the client’s views. For example, the client may think that the yield curve will become steeper. The structurer will offer an instrument that gains value if this expectation is realized.  

Finally, a fourth objective may be facilitating asset/liability management needs of the client. For example, a corporate treasurer who thinks that the cost of funds would increase in the future may decide to enter into a payer interest rate swap. The structurer will provide a modified swap structure that will protect against this eventuality at a smaller cost. In the following, we discuss these generalities using different sectors in financial markets.  

# 20.2.1 EQUITY STRUCTURED PRODUCTS  

First we take a quick glance at the history of equity structured products. This provides a perspective on the most common methodologies used in this sector. The first examples of structured products appeared in the late 1970s. One example was the stop-loss strategies. According to these, the risky asset holdings would automatically be liquidated if the prices fell through a target tolerance level. These were precursors of the CPPI techniques to be seen later in Chapter 23. They can also be regarded as precursors of barrier options.  

Then, during the late 1980s, market practitioners started to move to principal protected products. Here the original approach was offering “zero coupon bond plus a call” structures. For example, with 5-year treasury rates at $\boldsymbol{r}_{t},$ and with an initial investment of $N=100$ , the product would invest  

$$
\frac{N}{(1+r_{t})^{5}}
$$  

into a discount bond with a 5-year maturity. The rest of the principal would be invested in a properly chosen call or put option. This simple product is shown in Figure 20.1.  

At the simplest level, the guaranteed product consists of a zero-coupon bond and one or more options.2 Suppose $S_{t}$ denotes the value of an underlying security. This security can essentially be anything from stocks to credit index tranches or the value of some hedge fund investment. We can then write the following contractual equation:  

![](a9ee095d1014e20e25d31a091fc4f4c5718e96e444e4af6e04225cd624c4e16f.jpg)  

Suppose an investor invests the amount $N=100$ directly to a basket of options over a $T_{\mathbf{\delta}}$ -year maturity. Then, options being risk investments and investors having limited risk management capabilities, part of the principal may be lost if these options expire out-of-the-money. On the other hand, if the yield on a $T_{\mathbf{\delta}}$ -maturity zero-coupon bond is $r\%$ and if the same investor invests, at time $t_{0}$ , a carefully chosen amount $P V_{t_{0}}$ in this bond, the security will be worth 100 in 5 years:  

$$
P V_{t_{0}}\big(1+r_{t_{0}}\big)^{T}=N
$$  

The payoff of the zero-coupon bond is illustrated in Figure 20.1a as a function of the share, that is the underlying of the option. Thus the investor can allocate $P V_{t_{0}}$ to buy a bond and will still have $N-P V_{t_{0}}$ to invest in (a basket of) options. Depending on the level of volatility, the level of $r$ and  

(a Payoff of a zero-coupon bond as a function of the share price  

![](b1a0cbe3259365a45fb1d5e3027f471cf038d31e7217a38b584a0a05e1232ee1.jpg)  

b Payoff of a long call option position  

![](def399faf7e4daf7b0d30c7af6cb6377726808fe87d85b9d3e889dcff88f4b37.jpg)  

(c)Payoff of a long zero-coupon bond and long call option position  

![](d43b967e817e427574a56c2c694857856dc19efa1915a966d5836ff486077d5b.jpg)  

# FIGURE 20.1  

Zero-coupon bond and long call position.  

the expiration dates under consideration, this residual will provide an exposure—the growth of $S_{t}$ . In fact, let $g_{t_{i}}$ be the percentage rate of change in $S_{t}$ during the interval $[t_{i},t_{i-1}]$ ,  

$$
g_{t_{i}}=\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}
$$  

Then the investor’s exposure will be $\lambda g_{t_{i}}S_{t_{0}}$ , where $\lambda$ is the familiar participation rate. In the case of structured products, it is the bank that makes all these calculations, selects a structure with a high participation rate, and sells the principal protected security as a package to the investor.  

According to this, in the simplest case the bank will buy a $P V_{t_{0}}$ amount of the zero-coupon bond for every invested 100, and then options will be purchased with the rest of the principal, that is 100 2 PVt0 or 100 3 1 2 11rt 5.  

# EXAMPLE  

An investor has the principal $N=100$ . The observed yield on a 5-year zero-coupon treasury is $4.50\%$ . If the investor invests 80.2451 in this bond, the security will be worth 100 in 5 years:  

$$
80.2451(1+.045)^{5}=100
$$  

Thus the investor can allocate 80.2451 to buy a bond and will still have 19.7549 to invest in options.3  

In the above example, assume that the investor invests in S&P500 options. After buying the zero-coupon bond, the structurer can invest $\$19.7549$ in S&P 500 options and pay for administration, costs, and commissions. Assume that a 5-year S&P500 call option costs $\$22.19$ . We also add $\$2$ for administration and margin costs. Thus the investor will benefit from a participation rate of $80\%$ . The participation rate is calculated as $(19.7549-2)/22.19$ . Consider two scenarios. In the optimistic scenario, we assume that the S&P500 goes up by $20\%$ over the course of 5 years. In this case, the investor will achieve $16\%$ $(=80\%\times20\%)$ . The structured product would redeem at maturity at $116\%$ of the principal ( $100\%$ from the zero-coupon bond and a $16\%$ gain from the option). In the pessimistic scenario, we assume the S&P500 would fall by $40\%$ . In this case, the call option would expire worthless and the investor would receive $100\%$ of his capital back.  

The general idea is simple. The problems arise in implementation and in developing more refined ways of doing this. In practice, several problems can occur.  

First, zero-coupon interest rates for a maturity of $T$ may be too low. Then the zero-coupon bond may be too expensive and not enough “excess” may be left over to invest in options. For example, during the years 2011 2013, 5-year USD Treasury rates were around $1.25\%$ . This leaves only:  

$$
100-{\frac{100}{\left(1+0.02\right)^{5}}}=6.02
$$  

to invest in the option basket. Once we factor out the fees paid for such products, which could be several percentage points, the amount that can be invested in the option goes down even more.4 Depending on the level of volatility, such an investment may not be able to secure any meaningful participation rate.  

Second, options on the underlying where exposure is desired may not exist. For example, considering hedge funds, there are few options traded on these risks. Yet, an investor may want exposure to hedge fund activity, or, say, to credit tranches without risking (part of) his or her principal.  

Third, even if options on the underlying risk exist, the set of available maturities is limited and longer-term maturities are often illiquid. To address this, hedgers may have to resort to rolling a sequence of short maturity options which can result in a highly path-dependent strategy since the cost of the rolling strategy will depend on changing market conditions.  

Fourth, irrespective of the level of interest rates, the options may be too expensive, depending on the level of volatility. This may, again, not secure a meaningful participation rate.  

The following reading illustrates how the behavior of various market participants that buy and sell volatility affects implied volatility levels and thus the cost of options.  

# EXAMPLE  

A resurgence in close-out activity has been triggered by a sharp rise in long-dated implied volatility during the first five months of 1998. Having declined significantly throughout November and December last year, three-year index volatility levels have risen steadily since January.  

The trend closely mirrors changes in implied volatility experienced last year. Implied volatility levels first took off in 1997, driven by a surge in the market for guaranteed equity funds. Arrangers of the funds bought longer-dated options from banks to hedge the guarantee embedded in retail products. No natural sellers of long-dated volatility were available, and a short squeeze in volatility quickly developed, pushing up rates.  

Market professionals asserted last week that the short squeeze was the result of a vicious circle. Banks closing-out their short option positions had pushed volatility even higher, which in turn has prompted other houses to close out their positions. “It’s something of a chain reaction. I think most professionals are fairly concerned,” said one head of equity derivatives trading in London.  

Although in agreement over the severity of the volatility squeeze, market professionals were divided on its cause or solution. Some professionals alleged that bank risk controllers had exacerbated the volatility squeeze by setting too tight risk limits. “This is a typical example of accountants sticking to their guns, whatever happens. It’s a unique situation which will not last and they should take account of that,” said one.  

# History is Bunk?  

Professionals also pointed to factors that they felt would eventually alleviate the demand/supply imbalance. Several market participants said they thought high volatility was a temporary phenomenon; they argued that volatility is mean-reverting and that implied volatility rates would soon descend towards (much lower) historical levels.   
The discrepancy between the two views of volatility lies at the heart of conflicting views over the market’s development. Implied volatility rates are calculated by feeding current option prices into an option model, and so are a function of the supply and demand in volatility. In contrast, historical volatility rates are calculated from previous equity market movements. Three-year FTSE 100 historical volatility levels are around $1I\%$ . The yawning gap between historical and implied volatility rates has already created trading   
opportunities for unconventional suppliers of volatility. While dealers remain naturally short volatility, other trading firms have a more flexible approach to volatility rates. Hedge funds had already been seeking to sell long-dated volatility, with the view that implied levels would descend to historical rates.  

Equity derivatives professionals asserted that lower participation rates were the direct result of the rise in implied volatility. Guaranteed products are a mixture of a long position in equities—usually achieved through one or more futures contracts—and an option used to provide a floor on possible losses. If the floor is more expensive, the upside offered to the buyer of the guaranteed product will be reduced to lower the overall cost of the product. According to several market professionals, the new lower participation rates are a function of the volatility squeeze and are thus here to stay. “I think participation rates will decline and so reduce demand for volatility. It’s simply the market finding an equilibrium,” said one equity derivatives marketer.  

(Thomson Reuters IFR, June 1998)  

The reading shows that high implied volatility levels increase the price of call options which are one of the building blocks in capital guaranteed products. The higher costs means that the participation rates offered by such products necessarily decline.  

The capital guaranteed products described above were followed in the early 1990s with structures that essentially complicated the long option position. Some products started to “cap” the upside. The structure would consist of a discount bond, a long call with strike $K_{L}$ and a short call with strike $K_{U},$ , with $K_{L}<K_{U}.$ This way, the premium obtained from selling the second call would be used to increase the participation rate, since more could be invested in the long option. This is shown in Figure 20.2. Figure 20.2a shows the zero-coupon bond payoff. Figure 20.2b and c shows the payoffs of a long call position with strike price $K_{L}$ , a short call position with strike price $K_{U}$ . Figure 20.2d shows the payoff of the portfolio consisting of the zero-coupon bond and the two call options. Other products started using Asian options. The gains of the index to be paid to the investor would be calculated as an average of the gains during the life of the contract.  

Late 1990s started seeing correlation products. A worst of structure would pay at maturity, for example, $170\%$ of the initial investment plus the return of a worst performing asset in a basket of say 10 stocks or commodities. Note that this performance could be negative, thus the investor could receive ${<}170\%$ return. However, such products were also principal protected and the investor would still recover the invested 100 in the worst case.  

In the best of case, the investor would receive the return of the best performing stock or commodity given a basket of stocks or commodities. The observation period could be over the entire maturity or could be annual. In the latter case, the product would lock in the annual gains of the best-performing stock, which can be different every year. Mid-2000s brought several new versions of these equity-linked structured instruments including reverse convertibles which we discuss in more detail below, but first we consider the main tools underlying the products.  

# 20.2.2 THE TOOLS  

Equity structured products are manufactured using a relatively small set of tools that we will review in this section. We will concentrate on the main concepts and instruments: basically five main types of instruments and a major conceptual issue that will recur in dealing with equity structured products.  

a)Payoff of a zero-coupon bond with face value 100  

![](5e1e0473024923f868a3b5c12387e37737f29b89b1d716b369fa2e144e4a9d71.jpg)  

# FIGURE 20.2  

Zero-coupon bond, long call and short call.  

First there are vanilla call or put options. These were discussed in Chapters 9 and 11 and are not handled here. The second tool is touch or digital options, discussed in a later chapter, but we’ll provide a brief summary below.  

Touch or digital options are essentially used to provide payoffs (of cash or an asset) if some levels are crossed. Most equity structured products incorporate such levels. The third tool is reverse convertibles, which are conceptually related to convertible bonds with the important difference that they embed an option that is conveyed to the issuer and not the holder of the option.  

The fourth tool is new; it is the so-called rainbow options. These are options written on the maximum or minimum of a basket of stocks. They are useful since almost all equity structured products involve payoffs that depend on more than one stock. The fifth tool is the cliquet. These options are important prototypes and are used in buying and selling forward starting options. Note that an equity structured product would naturally span over several years. Often the investor is offered returns of an index during a future year, but the initial index value during these future years  

![](1ec505aa43800dfd5872758e2f2787f0abcdebfe29e53d2df886f87c5ecc9178.jpg)  

# FIGURE 20.3  

Payoff of a one-touch option.  

would not be known. Hence, such options would have forward-setting strikes and would depend on forward volatility. Forward volatility plays a crucial role in pricing and hedging structured products, both in equity and in fixed-income sectors.5  

# 20.2.2.1 Touch and digital options  

Touch options are similar to the digital options introduced in Chapter 11. European digital options have payoffs that are step functions. Digital or binary options are contracts that pay out a fixed amount or nothing at expiration, depending on the settle price of the underlying asset. If, at the maturity date, a long digital option ends in-the-money, the option holder will receive a predetermined amount of cash, or, alternatively, a predetermined asset. As discussed in Chapter 11, under the standard Black Scholes assumptions the digital option value will be given by the risk-adjusted probability that the option will end up in-the-money. In particular, suppose the digital is written on an underlying $S_{t}$ and is of European style with expiration $T$ and strike $K$ . The payoff is $\$1$ and riskfree rates are constant at $r_{\mathrm{.}}$ , as shown in Figure 20.3. Then the digital call price will be given by  

$$
C_{t}=e^{-r(T-t)}\tilde{P}(S_{T}>K)~R
$$  

where $\tilde{P}$ denotes the proper risk-adjusted probability. Digital options are standard components of structured equity products and will be used below.  

A one-touch option is a slightly modified version of the vanilla digital. A one-touch call is shown in Figure 20.3. The underlying with original price $S_{t_{0}}<K$ will give the payoff $R=\$1$ if (i) at expiration time $T_{\mathrm{{:}}}$ , the price of the underlying is above the strike price $(K<S_{T})$ and (ii) if the level $K$ is breached only once.  

Otherwise the payoff will be zero. A previous chapter discussed a double-no-touch (DNT) option which is often used to structure wedding cake structures for FX markets.6  

One advantage of digital options from the seller’s point of view is that the maximum possible downside is known in advance. From the point of view of a bank or structure this implies that selling digital options is much more risk controlled and less negatively skewed as a strategy than a typical short volatility position. On the other hand, touch and digital options are less liquid than vanilla options since it is more difficult for market makers to hedge the digital options near the strike price around expiry. Some digital options are now exchange traded while they were previously OTC instruments. In 2008, the American Stock Exchange (Amex) and the CBOE launched exchange-traded European cash-or-nothing binary options. The more complicated tools are the rainbow options and the concept of forward volatility. We will discuss them in turn before we start discussing recent equity structured products.  

# 20.2.2.2 Rainbow options  

The term rainbow options is reserved for options whose payoffs depend on the trajectories of more than one asset price. Obviously, they are very relevant for equity products that have a basket of stocks as the underlying. The major class of such options is those that pay the worst-of or best-of the $n$ underlying assets. Suppose $n=2$ ; two examples are  

$$
\mathrm{Min}[S_{T}^{1}-K^{1},S_{T}^{2}-K^{2}]
$$  

where the option pays the smaller of the two price changes on two stocks and  

$$
\mathrm{Max}[0,S_{T}^{1}-K^{1},S_{T}^{2}-K^{2}]
$$  

where the payoff is the larger one and it is floored at zero. Needless to say the number of underlying assets $n$ can be larger than 2, although calibration and numerical burdens make a very large $n$ impractical.  

# 20.2.2.3 Reverse convertibles  

In the previous chapter, we saw that convertible bonds can be viewed as a portfolio of straight debt and an embedded call option. This typically implies that the issuer can issue the debt at a lower coupon than would be the case with straight debt alone. For a bond investor who is seeking to participate in the upside of the underlying equity or who is exploiting potentially undervalued volatility a convertible bond can be the right investment. However, for an investor who is seeking a high yield and is not concerned with participating in the upside a convertible bond is less attractive than the straight debt. How could a financial engineer create a product that pays a coupon that is higher than that of straight debt? The answer is that if the product embedded a short put position instead of a long call position, the buyer issuer of the instrument would receive a long put option from the buyer of the product and the issuer could in return compensate the buyer of the product with a higher coupon. In other words, the embedded put is financing the higher coupon. Such securities are called reverse convertibles. The put option is written on an underlying stock (or basket of stocks) $S_{t}$ and the conversion is not optional, but occurs automatically if $S_{t}$ falls below a certain level $K$ , which can be viewed as the strike price of the put option. The underlying stock or basket of stocks is referred to as reference shares.  

Reverse convertibles have been mainly sold as structured products to retail investors. Reverse convertibles embed a put option that depends on the underlying stock volatility in a similar way that the embedded call option in a convertible bond depends on implied volatility. The fundamental difference between convertible bonds and reverse convertibles is, however, that convertible bonds offer participation in the upside of the underlying, while reverse convertibles offer participation in the downside of the underlying. Moreover, the conversion option is conveyed to the issuer, not the holder of the reverse convertible since the holder implicitly writes a put option on the underlying to the issuer. While the coupon payments in a reverse convertible may be considerably higher than the yields available in the bond market, reverse convertibles carry a higher risk than bonds because repayment of the principal amount is not guaranteed.  

The payoff of a basic reverse convertible at maturity depends on two scenarios:  

Scenario 1: $:S_{T}>K.$ . The underlying stock at maturity is above the strike price. In this case, the holder receives the coupon and $100\%$ of the original investment.   
Scenario 2: $S_{T}{<}K$ . The underlying stock at maturity is below the strike price. The holder receives a predetermined number of stocks.  

For example, consider the buyer of a reverse convertible linked to the share price of ABC. If the stock price of ABC was initially d100, and in 1 year the stock price was d120 then scenario 1 obtains. The holder of a d1000 note would receive d100 for the $10\%$ coupon, and the d1000 principal. Scenario 2 would occur if the stock price was d80 at the end of 1 year. Then the holder of the note would receive d100 for the coupon and d800 worth of stock. In other words, this would lead to a capital loss. Figure 20.4 illustrates the payoff profile of a typical reverse convertible. Figure 20.4a shows the payoff of a zero-coupon bond. Figure 20.4b shows the profit and loss from a short put option position with a strike price $K$ . The write of the put option receives the put option premium if the underlying $S_{t}$ remains above the strike price $K$ . If we combine the zero-coupon bond with the short put position we obtain the profit and loss diagram for the reverse convertible which shows that the gain is higher than for a zero-coupon bond since the put option premium enhances the coupon.  

Often the embedded option is not a simple option, but a knock-in option. This implies that the scenarios above are different in the sense that the condition is that the stock price $S_{t}$ remains above the strike price at any point in time until maturity. The knock-in level is often set at $70\mathrm{-}80\%$ of the initial reference price.  

When are reverse convertibles typically bought by investors? In a low interest rate and high market volatility environment reverse convertibles are popular since they provide a way for investors to receive an enhanced yield. However, the products’ popularity does not mean that investors fully understand the price of the embedded put option that they are writing to the issuer of the product. If market volatility is high it is possible that the embedded put is very valuable and that the structure does not pass all of its value onto the buyer in the form of a coupon. In this case, the buyer takes on a large downside risk and may be surprised that in an equity market downturn the product leads to losses. Thus, investors should carefully compare the yield offered by the  

![](1afe9349759e4a353e2bb892b9f06019575e77b278bff0914a762d6486bcbced.jpg)  

# FIGURE 20.4  

Reverse convertible.  

reverse convertible to money market rates, since if the two diverge significantly it may mean that the reverse convertible embeds significant risk.  

In the 1990s, reverse convertibles were often issued with embedded short at-the-money put options. The downside of such products was that investors would suffer losses if the underlying was below the initial level. As investor demand waned in response to the market downturn following the bursting of the tech bubble, a new generation of products was developed that embedded a short atthe-money down-and-in put option. The barrier feature provided investors with additional protection since the put option would not be triggered unless the (down) barrier was reached. Such barrier reverse convertibles are popular structured products in Europe and in the United States. For the structurer, the barrier feature poses new challenges in practice, however, since the structure requires hedging long-dated equity barrier risks (with maturities between 3 and 5 years) and the Greeks of the products near the barrier tended to be unstable as discussed in the context of digital options above. Moreover, the large number of structured products and the relative illiquidity of the underlying equity market made hedging such products more difficult than is the case for FX products, for example.  

Some structured products including reverse convertibles have embedded call features. Thus, such products have call and conversion features. Banks that issue structured products refer to these products with call features as autocallable, which is the abbreviation of automatically callable. This feature is often found in structured products with longer maturities. Such products are callable by the issuer if the reference asset is at or above its initial level on a specified observation date.  

This is effectively an option for the issuer to redeem the product early. In this case, the investor receives the principal amount of their investment plus a predetermined premium. Similar to callable bonds, this call option conveyed to the issuer makes the product less attractive to the holder and therefore the yield on autocallables can be higher than for alternatives without this feature. Autocallable features are often found in capital guaranteed notes and barrier reverse convertibles.  

Structured products do not just contain hedging risks from the perspective of the structurer or issuer, but also legal risks. There are many examples in the United States, Europe, and Asia/Pacific when buyers of structured products suffered losses and then went to court against the issuers of the products. Therefore, it is not just in the interest of the buyers but also in the interest of the structurers to understand the consequences of any embedded downside in the products. In some instances, banks settle law suits in order not to jeopardize future client relationships even if the products were properly marketed and sold. In 2013, IOSCO (the International Organization of Securities Commissions) published a report on the Regulation of Retail Structured Products. The objective of the report is to enhance investor protection. It outlines a range of regulatory options that securities regulators can use to regulate retail structured products. The following reading provides one example of regulatory issues and risks associated with structured products. The example is based on reverse convertibles discussed in the section.  

# EXAMPLE: REVERSE CONVERTIBLES IN LIMBO  

Issuance of lira-denominated reverse convertibles ground to a halt in response to growing uncertainty over their tax status under Italian law. The Italian authorities are concerned that investors may buy the instruments in the belief that they are capital-protected fixed income instruments, when, in fact, they would be exposed to equity downside risk.  

According to warrant market participants, about a month ago the Bank of Italy warned potential issuers of lira-denominated reverse convertibles that they might be classified as “abnormal securities.” If classified as such, the coupon on the securities would be taxed at $27\%$ instead of $I2.5\%$ —the rate for normal fixed income and derivative structures. Since then, lira reverse convertible issuance has dwindled as structurers await a decision on their status.  

Market commentators said the Bank of Italy was concerned about the lack of principal protection in the structure. Reverse convertibles generate a yield considerably higher than that of vanilla bonds by embodying a short equity put position.  

The investor receives a high coupon and normal bond redemption as long as a specific equity price is above a particular level at maturity. However, if the equity falls below the specified mark, then the investor is forced to receive the physical equity instead of the normal bond principal.  

As a result, the buyer of the reverse convertible could end up with a long stock position at a low level, which would mean an erosion of initial principal. In contrast, the buyer of vanilla bond paper is assured of getting back the initial principal investment.  

(Thomson Reuters IFR, May 1998)  

The above reading illustrates the embedded downside risk in reverse convertible products. The issuer of the products will typically exercise the put option if the stock price is less than the strike price. As a result the bond holders or buyers of the reverse convertibles receive the stock under adverse conditions. The concern is that not all investors understand that even if the issuer does not default, the holders may suffer from substantial losses.  

# 20.2.2.4 Cliquets  

Cliquet options are frequently used in engineering equity and FX-structured products. They are also quite useful in understanding the deeper complexities of structured products. Cliquets are also known as ratchet options due to the resetting strikes in the structure.  

A cliquet is a series of prepurchased options with forward setting strikes. The first option’s strike price is known but the following options have unknown strike prices. The strike price of future options will be set according to where the underlying closes at the end of each future subperiod. The easiest case is at-the-money options. At the beginning of each observation period, the strike price will be the price observed for $S_{t_{i}}$ . The number of reset periods is determined by the buyer in advance. The payout on each option is generally paid at the end of each reset period.  

At reset dates, the option locks in the difference between the old and new strikes and pays it out as a profit. If the stock has moved in such a way during the preceding period that one of the component options expires out-of-the-money there will be no profit, and the investor will lose the premium corresponding to that period.  

# EXAMPLE  

A five-year cliquet call on the S&P with annual resets is shown in Figure 20.5. Essentially the cliquet is a basket of five annual at-the-money spot calls.  

The initial strike is set at, say, 1419, the observed value of the underlying at the purchase date. If at the end of the first year, the S&P closes at 1450, the first call matures in-themoney and the payout is paid to the buyer. Next, the call strike for the second year is reset at 1450 and so on.  

![](61affda5fc069129731d72b42e408aebb28a2a76f0b1dbfa3ceec694e141a669.jpg)  

# FIGURE 20.5  

Cliquet.  

To see the significance of a 5-year cliquet, consider two alternatives. In the first case, one buys a 1-year at-the-money call, then continues to buy new at-the-money calls at the beginning of future years four times. In the second case, one buys a 5-year cliquet. The difference between these is that the cost of the cliquet will be known in advance, while the premium of the future calls will be unknown at $t_{0}$ . Thus a structurer will know at $t_{0}$ what the costs of the structured product will be only if he uses a cliquet.  

Consider a 5-year maturity again. The chance that the market will close lower for 5 consecutive years is, in general, lower than the probability that the market will be down after 5 years. If the market is down after 5 years, chances are it will close higher in (at least) one of these 5 years. It is thus clear that a cliquet call will be more expensive than a vanilla at-the-money call with the same final maturity.  

One of the selling points that sellers of cliquet options point to is that when volatility is expected to rise investors can lock in profits periodically rather than risk losing gains that have accumulated. An investor that takes the view that the underlying risky asset will go up or down over time, but does not have a view about the precise timing may see a cliquet structure as a better way of locking in profits. One recent example of a cliquet structure is market-linked certificates of deposit (CDs) in the US structured product market.  

The important point is that cliquet needs to be priced using the implied forward volatility surface. Once this is done the cliquet premium will equal the present value of the premiums for the future options.  

# 20.2.3 FORWARD VOLATILITY  

Forward volatility is an important concept in structured product pricing and hedging. This is a complicated technical topic and can only be dealt with briefly here. Consider a vanilla European call written at time $t_{0}$ . The call expires at T, $t_{0}<T$ and has a strike price $K$ . To calculate the value of this call we find an implied volatility and plug this into the Black Scholes formula. This is called the Black Scholes implied volatility.  

Now consider a vanilla call that will start at a later date at $t_{1}$ , $t_{0}<t_{1}$ . Yet, we have to price the option at time $t_{0}$ . The expiration is at $t_{2}$ . More important, the strike price of the option denoted by $K_{t_{1}}$ is unknown at $t_{0}$ and is given by  

$$
K_{t_{1}}=\alpha S_{t_{1}}
$$  

where $0<\alpha\leq1$ is a parameter. It represents the moneyness of the forward starting call and hence is an important determinant of the option’s cost. The forward call will be an ATM option at $t_{1}$ if $\alpha=1$ . Assuming deterministic short rates $r$ , we can write the forward start option value at $t_{0}$ as  

$$
C\big(S_{t_{0}},K_{t_{1}},\sigma(t_{0},\ t_{1},\ t_{2})\big)=e^{r(t_{2}-t_{0})}E_{t_{0}}^{\tilde{P}}\big[(S_{t_{2}}-\alpha S_{t_{1}})^{+}\big]
$$  

where $C(.)$ denotes the Black Scholes formula and $\sigma(t_{0},t_{1},t_{2})$ is the forward Black Scholes volatility. The volatility is calculated at $t_{0}$ and applies to the period $\left[t_{1},\ t_{2}\right]$ . We can replace the (unknown) $K_{t_{1}}$ , using Eq. (20.10) and see that the cliquet option price would depend only on the current $S_{t_{0}}$ and on forward volatility.  

Thus the pricing issue reduces to calculating the value of the forward volatility given liquid vanilla option markets on the underlying $S_{t}$ . This task turns out to be quite complex once we go beyond very simple characterizations of the instantaneous volatility for the underlying process. We consider two special cases that represent the main ideas involved in this section. For a comprehensive treatment we recommend that the reader consult Gatheral (2006).  

# EXAMPLE: DETERMINISTIC INSTANTANEOUS VOLATILITY  

Suppose the volatility parameter that drives the $S_{t}$ process is time dependent, but is deterministic in the sense that the only factor that drives the instantaneous volatility $\sigma_{t}$ is the time $t$ . In other words we have the risk-neutral dynamics,  

$$
\mathrm{d}S_{t}=r S_{t}+\sigma_{t}S_{t}\mathrm{d}W_{t}
$$  

Then the implied Black Scholes volatility for the period $[t_{0},T_{1}]$ is defined as  

$$
\sigma_{B S}^{T_{1}}=\sqrt{\frac{1}{T_{1}-t_{0}}\int_{t_{0}}^{T_{1}}\sigma_{t}^{2}\mathrm{d}t}
$$  

In other words, $\sigma_{B S}^{T_{1}}$ is the average volatility during period $[t_{0},T_{1}]$ . Note that under these conditions the variance of $S_{t}$ during this period will be  

$$
\Big(\sigma_{B S}^{T_{1}}\Big)^{2}\big(T_{1}-t_{0}\big)
$$  

Now consider a longer time period defined as $[t_{0},T_{2}]$ with $T_{1}<T_{2}$ and the corresponding implied volatility  

$$
\sigma_{B S}^{T_{2}}=\sqrt{\frac{1}{T_{2}-t_{0}}\int_{t_{0}}^{T_{2}}\sigma_{t}^{2}\mathrm{d}t}
$$  

We can then define the forward Black Scholes variance as  

$$
\big(\sigma_{B S}^{T_{2}}\big)^{2}(T_{2}-t_{0})-\big(\sigma_{B S}^{T_{1}}\big)^{2}(T_{1}-t_{0})
$$  

Plug in the integrals and take the square root to get the forward implied Black Scholes volatility from time $T_{1}$ to time $T_{2},\sigma_{B S}^{f}\stackrel{.}{(}T_{1},T_{2})$  

$$
\sigma_{B S}^{f}(T_{1},T_{2})=\sqrt{\frac{1}{T_{2}-T_{1}}\int_{T_{1}}^{T_{2}}\sigma_{t}^{2}\mathrm{{d}}t}
$$  

The important point of this example is the following: In case the volatility changes deterministically as a function of time $t.$ , the forward Black Scholes volatility is simply the forward volatility. Hence it can be calculated in a straightforward way given a (deterministic) volatility surface. What intuition suggests is correct in this case. We now see a more realistic case with stochastic volatility where this straightforward relation between forward Black Scholes volatility and forward volatility disappears.  

# EXAMPLE: STOCHASTIC VOLATILITY  

Suppose $S_{t}$ obeys  

$$
\mathrm{d}S_{t}=r S_{t}+\sigma I_{t}S_{t}\mathrm{d}W_{t}
$$  

where $I_{t}$ is a zero-one process given by  

$$
I_{t}={\left\{\begin{array}{l l}{0.30{\mathrm{~with~probability~}}0.5}\\ {0.1{\mathrm{~with~probability~}}0.5}\end{array}\right.}
$$  

Thus, we have a stochastic volatility that fluctuates randomly (and independently of $S_{t}^{\phantom{\dagger}}$ ) between high and low volatility periods. Then, the average variances for the periods $[t_{0},T_{1}]$ and $[t_{0},T_{2}]$ will be given respectively as  

$$
\begin{array}{c}{(\sigma^{T_{1}})^{2}(T_{1}-t_{0})=\displaystyle\int_{t_{0}}^{T_{1}}E[(\sigma(I_{t}){\bf d}W_{t})^{2}]}\\ {=(T_{1}-t_{0}){\bf\sigma}(0.3)^{2}}\end{array}
$$  

which implies that forward volatility will be 0.2.  

Yet, the forward implied Black Scholes volatility will not equal 0.2.  

According to this, whenever instantaneous volatility is stochastic, calculating the Black Scholes forward volatility will not be straightforward. Essentially, we would need to model this stochastic volatility and then, using Monte Carlo, price the vanilla options. From there we would back out the implied Black Scholes forward volatility. The following section deals with our first example of equity structured products where forward volatility plays an important role.  

# 20.2.4 PROTOTYPES  

The examples of major equity structured products below are selected so that we can show the major methods used in this sector. Obviously, these examples cannot be comprehensive.  

We first begin with a structure that imbeds a cliquet. The idea here is to benefit from fluctuations in forward equity prices. Forward volatility becomes the main issue. Next we move to structures that contain rainbow options. Here the issue is to benefit from the maxima or minima of stocks in a basket. The structures will have exposure to correlation between these stocks and the investor will be long or short correlation. Third, we consider Napoleon-type products where the main issue becomes hedging the forward volatility movements. With these structures, the volatility exposure will be convex and there will be a volatility gamma. If these dynamic hedging costs involving volatility purchases and sales are not taken into account at the time of initiation, the structure will be mispriced. Such dynamic hedging costs involving volatility exposures is another important dimension in equity structured products.  

![](5cdaf60903bd73a3d50e403186fea56d817d1a7fee75e91910b89e19af0777c0.jpg)  

# FIGURE 20.6  

Structured product consisting of T-note and cliquet on iTraxx.  

# 20.2.4.1 Case I: A structure with built-in cliquet  

Cliquets are convenient instruments to structure products. Let $S_{t}$ be an underlying like stock indices or commodities or FX. Let $g_{t_{i}}$ be the annual rate of change in this underlying calculated at the end of year.  

$$
g_{t_{i}}=\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}
$$  

where $t_{i},i=1,2,...,n$ are settlement dates. There is no loss of generality in assuming that $t_{i}$ is denoted in years.  

Suppose you want to promise a client the following: Buying a 5-year note, the client will receive the future annual returns $\lambda g_{t_{i}}N$ at the end of every year $t_{i}$ . The $0<\lambda$ is a parameter to be determined by the structurer. The annual returns are floored at zero. In other words, the annual payoffs will be  

$$
P_{t_{i}}=\mathbf{Max}[\lambda g_{t_{i}}N,\ 0]
$$  

$\lambda$ is called the participation rate.  

It turns out that this structure is less straightforward than appears at the outset. Note that the structurer is promising unknown annual returns, with a known coefficient $\lambda$ at time $t_{0}$ . In fact, this is a cliquet made of one vanilla option and four forward starting options. The forward starting options depend on forward volatility. The pricing should be done at the initial point $t_{0}$ after calculating the forward volatility for the intervals $t_{i}-t_{i-1}$ . Figure 20.6 shows how one can use cliquets to structure this product. In this structured note, the structurer will take the principal $N_{:}$ , deposit part of it in a 5-year Treasury note, and with the remainder buy a 5-year cliquet. The underlying risky assets in the example are assumed to be the iTraxx index, but it could also be an equity index such as the S&P500 or the MSCI World. As the figure shows the cliquet consists of five forward start options. The strike price of the first option is $K_{0}$ and since the price of the underlying is $S_{t1}>K_{0}$ at date $t_{1}$ , the first option is exercised and pays out. The second option has a strike price of $K_{1}=S_{t1}$ and at date $t_{2}$ it is out-of-the-money. The third option does not pay out either. The fourth and fifth options pay out. We would like to discuss this structure in more detail.  

First let us incorporate the simple principal protection feature. Suppose 5-year risk-free interest rates are denoted by $r\%$ . Then the value at time $t_{0}$ of a 5-year default-free Treasury bond will be given by  

$$
P V_{t_{0}}={\frac{100}{(1+r)^{5}}}
$$  

Clearly this is less than 100. Then define the cushion $C u_{t_{0}}$  

$$
C u_{t_{0}}=100-P V_{t_{0}}
$$  

Note that  

$$
0<C u_{t_{0}}
$$  

and that these funds can be used to buy options. However, note that we cannot buy any option; instead we buy a cliquet since $\lambda$ times the unknown annual returns are promised to the investor. The issue is how to price the options on these unknown forward returns at time $t_{0}$ . To do this, forward volatility needs to be calibrated and substituted in the option pricing formula which, in general, will be Black Scholes.  

With this product, if the annual returns are positive the investor will receive $\lambda$ times these returns. If the returns are negative, then the investor receives nothing. Note that even in a market where the long-run trend is downward, some years the investor may end up getting a positive return.  

# 20.2.4.2 Case II: Structures with mountain options  

Structures with payoffs depending on the maximum and minimum of a basket of stocks are generally denoted as mountain options. This type of exotic option combines features of basket options and range options and Soci´ete´ G´en´erale was one of the first sellers of such options in the late 1990s. There are several examples. We consider a simple case for each important category.  

# 20.2.4.2.1 Altiplano  

Consider a basket of stocks with prices $\{S_{t}^{1},~\ldots,~S_{t}^{n}\}$ . A level $K$ is set. For example, $70\%$ of the initial price. The simplest version of an Altiplano structure entitles the investor to a “large” coupon if none of the $S_{t}^{i}$ hits the level $K$ during a given time period $[t_{i},~t_{i-1}]$ . Otherwise, the investor will receive lower coupons as more and more stocks hit the barrier. Typically, once three to four stocks hit the barrier the coupon becomes zero. The following is an example.  

# EXAMPLE: AN ALTIPLANO  

Currency: Eur; Capital guarantee: $100\%$ ; Issue price: 100.   
Issue date: 01-01-2014; Maturity date: 01-01-2019   
Underlying basket: {Pepsico, JP Morgan Chase, General Motors, Time Warner, Seven-Eleven} Annual coupons: Coupon $=15\%$ if no stocks settle below $70\%$ of its reference price on coupon payment dates.   
Coupon $=7\%$ if one stock settles below the $70\%$ limit.   
$\mathrm{Coupon}=0.5\%$ if more than one stock settles below the limit.  

Figure 20.7 shows how we can engineer such a product. Essentially, the investor has purchased a zero-coupon bond and then sold five digital puts. The coupons are a function of the premia for the digitals. Figure 20.7a shows the zero-coupon bond and Figure 20.7b shows the payoff and profit of the short digital put position. The put option premium can be used to enhance the coupon. Clearly this product can offer higher coupons if the components of the reference portfolio have higher volatility.  

![](57fdcf95e5f9119a23d095271c3eacf55f80e40b7c4a2b05610089896ab81b4e.jpg)  

# FIGURE 20.7  

Components of Altiplano.  

This product has an important property that may not be visible at the outset. In fact, the Altiplano investor will be long equity correlation, whereas the issuer will be short. This property is similar to the pricing of CDO equity tranches and will be discussed in detail later. Here we consider two extreme cases.  

Suppose we have a basket of $k$ stocks $S_{t}^{i},i=1,2,...,k.$ . For simplicity suppose all volatilities are equal to $\sigma$ . For all stocks under consideration, we define the annual probability of not crossing the level $K S_{t_{0}}$ ,  

$$
P\big(S_{t}^{i},t\in[t_{0},t_{1}]>K S_{t_{0}}^{i}\big)=(1-p^{i})
$$  

for all $i$ and $t\in[t_{0},T]$ . Here the $(1-p^{i})$ measure the probability that the ith stock never falls below the level $K S_{t_{0}}$ . For simplicity let all $p^{i}$ be the same at $p$ . Then i $\mathit{\bar{s}}_{t}^{i},i=1,2,\ldots$ are independent, we can calculate the probability of receiving the high coupon at the end of the first year as $(1-p)^{k}$ . Note that as $k$ increases, this probability goes down.  

Now go to the other extreme case and assume that the correlation between $S_{t}^{i}$ becomes one. This means that all stocks are the same. The probability of receiving a high coupon becomes simply $1-p$ . This is the case since all of these stocks act identically; if one does not cross the limit, none will. Since $0<p<1$ with $k>1$ we have  

$$
(1-p)^{k}<(1-p)
$$  

Thus, the investor in this product will benefit if correlation increases, since the investor’s probability of receiving higher coupons will increase.  

# 20.2.4.2.2 Himalaya  

The Himalaya is a call on the average performance of the best stocks within the basket. In one version, throughout the life of the option, there are preset observation dates, say $t_{1},t_{2},...,t_{n},$ at which the best performer within the basket is sequentially removed and the realized return of the removed stock is recorded. The payoff at maturity is then the sum of all best returns over the life of the product.  

# EXAMPLE: A HIMALAYA  

Currency: Eur; Issue price: 100.   
Issue date: 01-01-2013; Maturity date: 01-01-2019.   
Underlying basket: 20 stocks possibly from the United States and Europe.   
Redemption at Maturity:   
If the basket rose, the investor receives the maximum of the basket of remaining securities observed on one of the evaluation dates.   
If the basket declined, the investor receives the return of the basket of remaining securities observed on the last evaluation date.  

In this case, the return is related to the maximum or minimum of a certain basket over some evaluation periods. Clearly, this requires writing rainbow options, including them in a structure, and then selling them to investors.  

# 20.2.4.3 Case III: The Napoleon and Vega hedging costs  

A Napoleon is a capital-guaranteed structured product which gives the investor the opportunity to earn a high fixed coupon each year, say, $c_{t_{0}}=10\%$ , plus the worst monthly performance in an underlying basket of $k$ underlying stocks $S_{t}^{i}$ . If $k$ is large there will be a high probability that the worst performance is negative. In this case, the actual return could potentially be much less than the coupon $c_{t_{0}}$ .  

The importance of Napoleon for us is the implication of dynamic hedging that needs to accompany such products. The key issue is that Napoleon-type products cannot be hedged statically and require dynamic hedging. But the main point is that the dynamic hedging under question here is different than the one in plain vanilla options. In plain vanilla options, the practitioner buys and sells the underlying $S_{t}^{i}$ to hedge the directional movements in the option price. This dynamic hedging results in gamma gains (losses). What is being hedged in Napoleon-type products is the volatility exposure. The practitioner has to buy and sell volatility dynamically.  

These products have exposure to the so-called volatility gamma. The structurer needs to buy option volatility when volatility increases and sell it when volatility decreases. This is similar to the gamma gains of a vanilla option discussed in Chapter 9, except that now it is being applied to the volatility itself rather than the underlying price; hence the term volatility gamma. By buying volatility when vol is expensive and selling it when it is cheap, the structurer will suffer hedging costs. The expected value of these costs needs to be factored in the initial selling price, otherwise the product will be mispriced.  

# EXAMPLE: NAPOLEON HEDGING COSTS  

Suppose there is a basket of 10 stocks $\big\{S_{t}^{1},~{...}~,S_{t}^{10}\big\}$ whose prices are monitored monthly.   
The investor is paid a return of $10\%$ plus the worst monthly return among these stocks.  

Suppose now volatility is very high with monthly moves of, say, $50\%$ . Then a 1 percentage point change in volatility does not matter much to the seller since, chances are, one of the stocks will have a negative monthly return which will lower the coupon paid. Thus the seller has relatively little volatility exposure during high volatility periods.  

If, on the other hand, volatility is very low, say, $9\%$ , then the situation changes. A $1\%$ move in the volatility will matter, leading to a high volatility exposure.  

This implies that with low volatility the seller is long volatility, and with high volatility, the volatility exposure tends to zero. Hence the structurer needs to sell volatility when volatility decreases and buy it back when volatility increases in order to neutralize the vol of the position.  

This is an important example that shows the need to carefully calculate future hedging costs. If volatility is volatile, Napoleon-type structured products will have volatility gamma costs to hedging costs that need to be incorporated in the initial price.  

# 20.2.5 SIMILAR FX STRUCTURES  

It turns out that cliquets, mountain options, Napoleons, or other structured equity instruments can all be applied to FX or commodity sectors by considering baskets of currencies of commodities instead of stocks. Because of this close similarity, we will not discuss FX and commodity structures in detail. Wystub (2006) is a very good source for this.  

# 20.3 STRUCTURED FIXED-INCOME PRODUCTS  

Structured fixed-income products follow principles that are similar to the ones based on equity or commodity prices. But the analysis of the principles of fixed income is significantly more complex for several reasons.  

First, the main driving force behind the fixed-income structured products is the yield curve, which is a $k$ -dimensional stochastic process. Equity or commodity indices are scalar-valued stochastic processes, and elementary structured products based on them are easy to price and hedge. Equity (commodity) products that are based on baskets would have a $k$ -dimensional underlying, yet the arbitrage conditions associated with this vector would still be simpler. Second, the basis of fixed-income products is the LIBOR reference system, which leads to the LIBOR market model or swap models. In equity even when we deal with a vector process, there is no need to use similar models. Third, fixedincome markets are bigger than the equity and commodity markets combined. The very broad nature of fixed-income products’ maturities and credits can make some maturities in fixed income much less liquid. Finally, the fixed-income structured products do have long maturities, whereas in equity or commodity-linked derivatives they are relatively short dated.  

# 20.3.1 YIELD CURVE STRATEGIES  

It is clear that most fixed-income structured products will deal with yield curve strategies. There aren’t too many yield curve movements.  

1. The yield curve may shift parallel to itself up or down—called the level effect.   
2. The yield curve slope may change. This could be due to monetary policy changes or due to changes in inflationary expectations. The curve can steepen if the Central Bank lowers shortterm rates or flatten if the Central Bank raises short-term rates. This is called the slope effects.   
3. The “belly” of the curve may go up and down. This is in general interpreted as a convexity effect and is related to changes in interest rate volatility.  

The next point is that many of these yield curve movements are at least partially predictable. After all, Central Banks often announce their future policies clearly to inform the markets. Structurers can use this information to put together constant maturity swap (CMS)-linked products that benefit from the expected yield curve movements. One can also add callability to enhance the yield further.  

The reading below is one example of how the structurers look at yield curve strategies.  

# EXAMPLE  

The popularity of CMS-linked structured notes derives from end users wanting to take advantage of the inverse sterling yield curve, which seems to have stabilized in the long end.  

A typical structured note might be EUR5-50 million, with a 20-year maturity. It could pay a coupon of $8\%$ for the first 5 years, and then an annual coupon based on the 10-year sterling swap rate, capped at $8\%$ for the remainder of the note. It would be noncallable. The 10-year sterling swap rate was about $6.77\%$ last week.  

The long end of the sterling yield curve has likely stopped dropping because UK life insurers, who have been hedging guaranteed rate annuity products sold in the 1980s, have stopped scrambling for long-dated gilts. They have done so either because they no longer require further hedging, or because they have found more economical ways of doing so. If the long end fails to fall further, investors are more secure about receiving a long-term rate in a CMS, a trader said.  

The sterling yield curve, which is flat for about three years, and then inverts, makes these products attractive for investors who believe the curve will disinvert at some point in the future, according to traders.  

(Thomson Reuters IFR, January 31, 2000)  

Hence it is clear that fixed-income structured products are heavy in terms of their involvement in LIBOR, swaption, and call/floor volatilities and their dynamics. Essentially, to handle them the structurer needs to have, at the least, a very good command of the forward LIBOR and swap models.  

# 20.3.2 THE TOOLS  

Some of the tools involved in designing and risk-managing structured products were discussed earlier. Digital and rainbow options and forward volatility were among these. Fixed-income structured products use additional tools. Two familiar tools are modified versions of cap/floors and swaptions and a third major tool is CMS. We review these briefly in this section.  

A digital caplet is similar to a vanilla caplet. It makes a payment if the reference LIBOR rate exceeds a cap level. The difference is the payoff. While the vanilla caplet payoff may vary according to how much the LIBOR exceeds the level, the digital caplet would make a constant payment no matter what the excess is, given that the LIBOR rate is greater than the cap level.  

A Bermudan swaption can be defined as an option on a swap rate $s_{t}$ . The option can be exercised only at some specific dates $t_{1}$ , $t_{2}$ , ... When the option is exercised, the option buyer has the right to get in a payer (receiver) swap at a predetermined swap rate $\kappa$ . The option seller has the obligation of taking the other side of the deal. Clearly with this product the option buyer receives swaps of different maturity as the exercise date changes.  

CMS are fundamental elements of fixed-income structured products; hence, we review them separately.  

# 20.3.3 CMS  

A constant maturity swap is similar to a plain vanilla swap except for the definition of the floating rate. They were discussed in Chapter 14. There is a fixed payer or receiver, but the floating payments would no longer be LIBOR-referenced. LIBOR is a short-term rate with tenors of 1, 2, 3, 6, 9, or 12 months. It can only capture views concerning increasing or decreasing short-term rates. In a CMS, the floating rate will be another vanilla swap rate. This swap rate could have a maturity of 2 years, 3 years, or even 30 years. This way, instruments that benefit from increasing or decreasing long-term rates can also be put together. A 10-year CMS with a maturity of 2 years was shown in Figure 14.5. Note that there are variations on the CMS and it is possible that in a CMS, one party periodically pays a swap rate of a specific tenor (or the spread between swap rates of different specified tenors), known as the CMS rate, and in exchange receives a specified fixed or floating rate from the counterparty.  

A special property of CMS should be repeated at this point. Note that at every reset date, the contract requires obtaining, say, a 10-year swap rate from some formal fixing process. This 10-year swap rate is normally valid for the next 10 years. Yet, in a CMS that settles semiannually, this rate will be used for the next 6 months only. At the next reset date, the new fixing will be used. Thus, the floating rate that we are using is not the “natural rate” for the payment period. In other words, denoting the 10-year floating swap rate by $s_{t_{i}}^{10}$ we have:  

$$
\frac{\left(1+s_{t_{i}}^{10}\delta\right)}{\left(1+L_{t_{i}}\delta\right)}\neq1
$$  

even though both rates are “floating.” As long as the yield curve is upward sloping, the ratio will in fact be greater than one. But, in the case of a vanilla swap, each floating rate $L_{t_{i}}$ is the natural rate for the payment period and we have:  

$$
\frac{\big(1+L_{t_{i}}\delta\big)}{\big(1+L_{t_{i}}\delta\big)}=1
$$  

This is true regardless of whether we have observed $L_{t_{i}}$ or not. For this reason, the CMS require a convexity adjustment. This means, heuristically speaking, that the future unknown floating rates cannot simply be replaced by their forward equivalents. For example, if in 3 years we receive a 10-year floating swap rate $s_{t}$ , during pricing we cannot replace this by the corresponding forward swap rate $s_{t}^{f}$ . Instead we replace it with a forward swap rate adjusted for convexity.  

# 20.3.4 YIELD ENHANCEMENT IN FIXED-INCOME PRODUCTS  

Suppose an investor desires an enhanced return or a corporation wants a hedging solution at a lower cost. The general principle behind putting together such structured products is similar to equity products and is illustrated in the following contractual equation:  

![](5fd9bc0cbf6ba576ee427d678343c4c585cfab1c5203824cb5248e552da3879a.jpg)  

As in equity structured products, in order to offer a return higher than the one offered by straight bonds, make the client sell one or more options. In fact, as long as the client properly understands the risks and is willing to bear them, the more expensive and more numerous the options are, the higher will be the return. If the client is a corporation and is looking for a cheaper hedge, selling an option would again lower the associated costs.  

In structured fixed income products, there are at least two standard ways one can enhance yields.  

![](b3724f7c4b21e7d52bb430e072b6010176c19ec45edbd238a9331ae977d5733f.jpg)  

# FIGURE 20.8  

Digital caplet.  

# 20.3.4.1 Method 1: Sell cap volatility  

The first method to enhance yields is conceived so as to make the client sell cap/floor volatility. We saw in Chapter 17 that a caplet (floorlet) was an insurance written on a particular LIBOR rate that made a payment to the buyer of the option if the observed LIBOR rate went above (below) the cap level (floor level). A structurer could offer an investor a product that pays a higher coupon than would be available with the same credit risk and maturity if the product implicitly involves the investor writing a call option to the structurer. If interest rates are low and the yield curve is steep, investors may obtain above-market yields by betting against the market. Steep yield curves normally imply that interest rates are expected to rise. If an investor believes that interest rates will not rise as far as the market predicts and the investor is proven right, then the investor may be able to obtain an enhanced return. Of course, there is a price in the market for such views and the structurer could price the product based on the cost of a short caplet in the market plus a profit market. To specify a precise range of interest rates and payments associated with the option, the structurer can use digital caplets. Figure 20.8 shows the payoff of a long position in a digital caplet.  

The structure will consider daily fixings of LIBOR and make coupon payments (enhanced by the implicit digital caplet-type premium) when a day’s observation stays within a range, say $[0,7\%]$ . If the observed LIBOR exceeds that range for that day, no coupon is received.  

This way, the client is short a digital caplet and is selling digital caplet volatility and he or she will receive an enhanced yield for bearing this risk. Such products are called Range Accrual Notes (RAN).8 The client will earn interest for the proportion of the day’s LIBOR observations that remain within the range. This feature would be suitable for a client who does not expect LIBOR rates to fluctuate significantly during the maturity period.  

Let $F_{t}^{t_{i}}$ be the time- $\cdot t$ 6-month forward rate associated with the LIBOR rate $L_{t_{i}}$ . The associated settlement of the spot LIBOR is done, in-arrears, at time $t_{i+1}$ and the day-count adjustment parameter is $\delta$ as usual.  

Let the index $j=1$ , 2, ... denote days. A typical caplet starts on day $t_{i}+(j-1)$ and has an expiration 1 day later at $t_{i}+j$ . Each caplet’s payoff will depend on the selected reference rate that is followed daily. Often this would be the LIBOR rate at time $t_{i}+j,L_{t_{i}+j}$ . Depending on this daily observation the caplets will expire in- or out-of-the-money. In other words, the seller collects daily fixings on the LIBOR rate and sees if the rate stayed within the range that day. If it does, there will be a digital payoff for that day (i.e., interest accrues); otherwise, no interest is earned for that particular day.  

On the other hand, the actual amount paid will depend on another predetermined LIBOR rate. The rate applied to the payoff will be $L_{t_{i}}+$ spread, settled at $t_{i+1}$ .9 According to this the return of the structured product return is a function of the payoffs of $m$ digital options, where m is the number of calendar days in the payment period. Hence, the issue of whether interest is earned or not and the payoff depends on different LIBOR rates for each settlement period.  

Symbolically, assuming that interest paid is constant at $R$ , the $j$ th day’s payoff of the caplets can be written as  

$$
\begin{array}{r}{\mathrm{Pay}_{t_{i}+j}=\left\{\begin{array}{l l}{L_{t_{i}}\frac{1}{360}N}&{\mathrm{if}\ L_{t_{i}+j}\geq L^{\operatorname*{max}}}\\ {0}&{\mathrm{if}\ L_{t_{i}+j}\leq L^{\operatorname*{max}}}\end{array}\right.}\end{array}
$$  

where $L^{\mathrm{max}}$ is the upper limit of “range,” $N$ is the notional amount, and $\mathrm{Pay}_{t_{i}}+j$ is the daily payoff that depends on the jth observed LIBOR rate $L_{t_{i}+j}$ . The investor will be short this caplet. How would this enhance the return?  

Suppose there are $m$ days during the interest payment period;10 then the client is selling m digital caplets. For observation days these caplets are written on that day’s LIBOR rate that we denoted by $L_{t_{i}+j}$ . For weekends, the previous observation day’s LIBOR is used. So these digital caplets can be regarded as an $m$ -period digital cap, made of caplets with daily premiums $c_{t_{i}+j}$ , if settled at the end of that day. The investor receives the daily premiums and pays off that day’s payoff at every $t_{i}+j$ , instead of collecting all the cap premiums at the contract conception $t_{0}$ . The total value of these digital caplets at the payment time $t_{i+1}$ will be given by  

$$
C_{t_{0}}=\sum_{j=1}^{m}B(t_{0},t_{i}+j)c_{t_{i}+j}
$$  

where $c_{t_{i}+j}$ are the caplet premiums for the option that starts at time $t_{i}+j$ . Clearly these quantities are known at time $t_{0}$ .11 Note that this quantity is measured in time $t_{i+j}$ dollars. Then the enhanced yield of the RAN settled at time $t_{i+j}$ will be given by  

$$
L_{t_{i}}+c_{t_{i}+j}
$$  

At the time of inception $t_{0}$ of the note, the relevant LIBORs will be $\{L_{t_{i}}\}$ and these will be “equivalent” to $s_{t_{0}}$ , the swap rate observed at the time of inception. So the enhanced yield can in fact be expressed by the constant $R_{t_{0}}$ :  

$$
R_{t_{0}}=s_{t_{0}}+c_{t_{i}+j}
$$  

If at time $t_{0}$ the structurer observes the (i) swap rate $s_{t_{0}}$ , (ii) the forward volatilities of each digital cap $c_{j},$ and (iii) the discount factors $\textit{B}\left(t_{0},\ t_{i+1}\right)$ , then $R_{t_{0}}$ can be calculated. Thus the investor will receive the $R_{t_{0}}N$ and will pay the payoffs of daily caplets that expire in-the-money. Naturally, all this assumes a correct calculation of the digital cap premium $c_{j}.$ . Here there are some small technical complications. However, before we get to these we look at an example.  

# EXAMPLE: INTEREST RATE RANGE ACCRUAL/STRUCTURED DEPOSIT  

[Price quoted as of May 23, 2011] Customer View: US Dollar 3-month LIBOR will stay within the range of $0.25{-}O.60\%$ (inclusive) in the   
coming 1 year Deposit Currency: Renminbi (CNY) Deposit Period: 1 year Deposit Amount: CNY1,000,000 Interest Rate: US Dollar 3-month LIBOR (3M LIBOR) Reference Index Accrual in rate: $0.70\%$ p.a. Accrual out rate: $0.00\%$ p.a. Interest rate: Accrual in rate $\times$ (No. of days 3M LIBOR stays at or within the Accrual Range)/Total   
number of days $^+$ Accrual out rate $\times$ (No. of days 3M LIBOR stays outside the Accrual Range)/Total number   
of days Accrual range: $0.25\mathrm{-}0.60\%$ p.a. Interest period: Quarterly Interest payment: (Principal $\times$ Interest rate/4) for each interest period for each period Upon maturity: $I O O\%$ of principal customer receives (HSBC, https://www.hsbc.com.hk/1/2/hk/investments/sp/range-acc#example)  

In the above example, there are some interesting variations since the deposit currency (CNY) differs from the currency underlying the interest rate reference index. This may be convenient for customers that deposit CNY but have reviews regarding US interest rates. Note that the range is not bounded from below by zero, but is instead bounded by $L^{\mathrm{min}}=0.25\%$ and $L^{\mathrm{max}}=0.6\theta\%$ . The accrual out rate is the rate received if the interest rate falls outside the range. This implies that the investor is not just short a digital cap, but also a digital floor.  

Note that the underlying reference rate in the examples above that we use to determine the payoff of the digital caplets is 3-month or 6-month LIBOR rates, which are not the “natural rates” for the 1-day payoffs. Hence, the pricing of these digital caplets would require that a convexity adjustment is applied to the LIBOR rates, similar to CMS.  

# 20.3.4.2 Method 2: Sell swaption volatility  

Making a straight bond callable is the second way of enhancing yields. This will result in the investor being short swaption volatility.  

The difference is important. In the first case one is writing a series of options on a single cash flow, namely the caplet payoff. But in the case of callable bonds, the investor will write options on all the cash flows simultaneously and will receive his principal 100 if the bond is called. Thus a swaption involves payoffs with baskets of cash flows. These cash flows will depend on different LIBOR rates. When the swaption is Bermudan, this is similar to selling several options (although dependent on each other) at the same time. Hence the Bermudan swaption will be more expensive and there will be more yield enhancement.  

An investor that buys a callable LIBOR exotic has sold the issuer the right (but not the obligation) to redeem the notes at $100\%$ of the face value at any given call date. A note that is callable just once (European) will have a lower yield than a comparable note with multiple calls (Bermudan). The question whether a callable note will be called or not depends on the initially assumed dynamics of the forward LIBOR rates versus the behavior of these forward rates and their volatilities in the future.  

# 20.4 SOME PROTOTYPES  

In this section, we discuss some typical fixed-income structured products and their engineering in detail using the tools previously introduced. We consider three typical structured products that are representative.  

# 20.4.1 THE COMPONENTS  

In order to engineer fixed-income structured products, the market practitioner will need a small number of components. These are  

1. The relevance discount curve $B(t_{0},t_{i})$ in a certain currency. This will be used to discount future “expected” cash flows.12 2. A relevant forward curve in the same currency. This could be a forward LIBOR curve or a forward swap curve. Obviously, this can be obtained from the discount curve using relations such as13  

$$
(1+F(t_{0},t_{i},t_{k})\delta)=\frac{B(t_{0},t_{i})}{B(t_{0},t_{k})}\quad i\le k
$$  

This is equivalent to needing a market for vanilla swaps, i.e., a tradeable swap curve.  

3. A market for CMS, since the structurer may want to receive or pay a floating rate that can be any point of the yield curve. A fixed CMS rate will be paid against this.14  

4. A market for (Bermudan) swaptions if the structure is callable.  

5. A market for caps/floors if the structure is of range accrual type.  

We now show how some prototypes for fixed-income structured products can be manufactured using these components. The prototypes we discuss are exotics in the sense that the structurer cannot buy the note from some wholesale market and then sell it. The structurer has to manufacture the note. In other words, they are exotics because one side of the market does not exist and the structurer has to know how to price and hedge the product in-house.  

# 20.4.2 CMS-LINKED STRUCTURES  

There are (at least) two kinds of CMS-based products. Some link the coupon to a CMS rate. This would be similar to a floating rate note, but the floating rate would be a long-term rate this time. The second kind will be linked to a CMS spread. An investor buying CMS spread-linked structures will not be affected by parallel shifts in the yield curve. Rather, the buyer will be affected by the slope of the yield curve. Depending on whether the curve flattens or steepens, the buyer of the spread notes would benefit.  

A note linked to a CMS rate enables investors to benefit from shifts in the long or short end of the yield curve over prolonged periods of time. The note pays a fixed coupon which goes up as the short end of the yield curve shifts upward over the lifetime of the product.15 If made callable, the investor also receives enhanced returns. This is one of the most common types of structured fixedincome products. A straightforward example is shown below.  

# EXAMPLE: A CMS-LINKED NOTE  

Issuer: Bank ABC Tenor: 5 years Principal: Guaranteed at maturity at $100\%$ Coupon: Year 1: $4.00\%$ Year 2: CMS $10+2.5\%$ Year 3: CMS $10+2.5\%$ Year 4: CMS $10+2.5\%$ Year 5: CMS $10+2.5\%$ where CMS 10 refers to the 10-year constant maturity swap rate. Call: Callable on each coupon date.  

Suppose an institutional investor expects 10-year rates to rise successively during the next 5 years. This would be equivalent to five consecutive shifts in the long end of the yield curve. Then the note provides a way to take exposure to this risk. We now discuss how CMS-linked products can be engineered using standard tools in fixed-income markets.  

# 20.4.3 ENGINEERING A CMS-LINKED NOTE  

In this section, we engineer a straightforward CMS-linked note. Suppose an investor has “a view” concerning the yield curve. For example, he or she expects the long end of the yield curve to shift up gradually during the next 5 years. For such an investor, the structurer would like to put together a portfolio of elementary assets that generates the promised risk-return characteristics of the relevant CMS-linked note with maturity $T=5$ years. The example discussed above provides a good framework. For simplicity we assume annual interest payment dates. How do we engineer the CMS-linked note shown above?  

1. First we select a CMS rate. For example, let the CMS rate be the floating rate of an $m$ -period swap observed at every $t_{i}$ (in-advance) and paid at time $t_{i+1}$ (in arrears). There is no harm in thinking that $m=10$ years.   
2. Next we manufacture the high, known, first-year coupon $c_{t_{0}}$ . There is no harm in thinking that $c_{t_{0}}=5\%$ as in the above case. The question is, of course, how to manufacture such a high coupon. This value will be determined during pricing.  

3. Next, offer a “floating” coupon for the following 4 years of the form  

$$
c_{t_{t}}=\mathrm{cms}_{t_{i}}^{m}+\alpha_{t_{0}}^{t_{i}}
$$  

where $\mathrm{cms}_{t_{i}}^{m}$ is the CMS rate of period $t_{i}$ .  

4. $\alpha_{t_{i}}^{t_{i}}$ will be known constants at time $t_{0}$ and will have to be determined during the pricing. Below we consider two different formulations for this term.   
5. Make the note callable at call dates $t_{1},t_{2},t_{3}$ , and $t_{4}$ .  

First, some general observations. The first-year coupon needs to be constant, since even with floating rate instruments the first coupon is always known. The investor is taking a position on “floating” rates, but the first floating rate will be observed at the purchase date. Second, the note is made callable. The structurer is making the investor sell an option, so that the returns can be enhanced by this option’s premium. Third, the option is of Bermudan style, so it can be exercised four times at any of the four future dates. This option would naturally be more expensive than a vanilla swaption and hence the investor can be better compensated.  

# 20.4.3.1 A contractual equation  

Now we can put together a replicating portfolio, i.e., obtain a contractual equation for this note.  

First, start with the floating CMS coupons $\mathrm{cms}_{t_{i}}^{m}$ . How can the structurer pay such coupons to the investor?16 Here the answer is straightforward. The structurer gets into a 5-year receiver CMS at time $t_{0}$ . We assume that in this CMS the floating CMS rate is exchanged against a floating LIBOR rate. In this swap the first-year coupon is fixed, but at every $t_{i}.$ , $i=1$ , 2, 3, 4 the going CMS rate $\mathrm{cms}_{t_{i}}^{m}$ will be received by the structurer and that period’s LIBOR $L_{t_{i}}$ will be paid. The structurer will pass the $\mathrm{cms}_{t_{i}}^{m}$ to the investor. So part of the coupon has now been constructed. This situation is shown in Figure 20.9. The source of the LIBOR payments will be discussed later.  

What would $\alpha_{t_{i}}$ represent then? Calculate the premium of a 5-year Bermudan swaption—call it $C_{t_{0}}$ . This swaption is on the CMS rate and can be exercised four times during the period $[t_{0},\ T]$  

Premium $C_{t_{0}}$ from 5-year Bermudan option used to enhance coupon  

![](07f662174561c483cf19d6e18e4e20003c9b65810946fa02d2b1f06bca8d067c.jpg)  

# FIGURE 20.9  

CMS-linked note.  

annually at each $t_{i},$ , $i=1$ , 2, 3, 4, 5. Allocate this premium to the four future years by choosing the $\alpha_{t_{0}}^{t_{i}}$ such that,  

$$
C_{t_{0}}=B(t_{0},t_{1})~\alpha_{t_{0}}^{t_{1}}+B(t_{0},t_{2})~\alpha_{t_{0}}^{t_{2}}+B(t_{0},t_{3})~\alpha_{t_{0}}^{t_{3}}+B(t_{0},t_{4})~\alpha_{t_{0}}^{t_{4}}+B(t_{0},t_{5})~\alpha_{t_{0}}^{t_{5}}
$$  

This gives $\alpha_{t_{0}}^{t_{i}}$ .  

Finally, note that the structurer will be making LIBOR referenced payments to the CMS market maker. These payments will come from the original principal $N=100$ . The structurer will place the principal into a deposit account and receive floating LIBOR.  

The replication is complete. The structurer buys a receiver a 5-year CMS on the 10-year CMS rate and sells a 5-year Bermudan swaption on the CMS rate that can be exercised annually. The original $N$ received as principal is held in a deposit account.  

The cash flows of this portfolio are shown in Figure 20.9. These cash flows are identical to the ones promised by the note. The structurer is essentially buying the portfolio, repackaging it, and then selling it to the client as a structured CMS-linked note. We can summarize such CMS-linked structures using contractual equations. For this particular CMS-linked note we have  

![](d3643ffb9adf26323d5ad59c7cd1071648935383b77f7181fd3f299bae23e2c6.jpg)  

Note that the replicating portfolio presents further opportunities to the structurer. The structurer may be in need to sell swaption volatility to other clients. Through this CMS-linked note the structurer is buying swaption volatility from retail clients. Hence, the note may be a good way of generating a needed supply of swaption volatility at an attractive price. The structurer will naturally sell the swaption at a higher (offer) price than the price of the swaption implicitly bought from the retail client.  

A similar comment is valid for the CMS. The structurer may in fact be a CMS market maker and may be receiving fixed CMS rates and paying floating rates in a different deal. By marketing the CMS-linked note to the investor the structurer is paying a fixed CMS rate. This is like receiving the asked CMS rate and then paying the bid CMS rate.  

In other words, the instruments that need to be purchased from the market may in fact already be in the books of the structurer. The structured product is then a good way of taking these risks, repackaging them, and then selling them, to retail clients.  

# 20.4.4 ENGINEERING A CMS SPREAD NOTE  

Suppose an investor expects that the yield curve will steepen. In that case, a CMS-spread structure is appropriate. First we consider the product itself.  

This LIBOR exotic has three additional properties. First, the instrument is more complicated because the floating annual coupon will depend on more than one CMS rate, hence the “spread.” Second, this spread will be offered to the retail investor after multiplying it with a participation rate. The participation rate has the potential of significantly enhancing the yields if the expectation turns out to be correct and if the product is not called. The spread in question can become negative. To prevent investors from paying negative coupons, such spread-related coupons are often floored at zero. Third, because the product is written on more than one CMS rate, the value of the structure will explicitly depend on the correlation between these rates.  

The example below is typical of CMS spread notes.  

# EXAMPLE: A CMS SPREAD NOTE  

Issuer: Bank ABC; Tenor: 5 years   
Principal: Guaranteed at maturity at $100\%$   
Coupons:   
Year 1: $4.00\%$   
Year $2{-}5\colon17\times(\mathbf{CMS}^{10}{-}\mathbf{CMS}^{20})$ , max $22\%$ , $\mathrm{mm}0\%$ Call: Callable on each coupon date, $t_{i}$ .  

Why would an investor be interested in such a note? Suppose an institutional investor expects that the yield curve will steepen further. This can happen in two ways at least.  

First, if at constant inflation and hence at constant long rates, the short end interest rates decline. A loosening of monetary policy by the Central Bank due to moderately weakening real economy may be one example. Second, short rates and Central Bank monetary policy may stay the same, but due either to inflationary pressures or strengthening economic activity the long rates may go up. These two cases represent two possible views and the spread note will provide one way to take an exposure toward such an event.  

This product will offer higher rates if the yield curve keeps steepening gradually, as the coupon is dependent on the differential between the rates. Below we synthetically create a CMS spread note starting with more elementary instruments.  

# 20.4.5 THE ENGINEERING  

The CMS spread product has (at least) two novel financial engineering features: the product will illustrate the utilization of the participation rate and the way one has to floor the spreads. In addition, on the pricing side, we will see that correlation becomes an explicit additional risk.17 Now we engineer the CMS spread note mentioned above. The first year coupon is already discussed; it comes from the first year LIBOR rate which is known, plus part of the option premium sold by the investor. The real novelty of the structure is in the coupons for years $i=2,3,4,5.$ In fact, the coupons are of the form,  

$$
c_{t_{i}}=\operatorname*{max}\left[\lambda\big(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}\big)+\alpha_{t_{i}},0\right]
$$  

where $\mathrm{cms}_{t_{i}}^{m}$ and $\mathrm{cms}_{t_{i}}^{h}$ are two floating CMS rates observed at time $t_{i}$ , with CMS maturities of $m$ and $h$ years, respectively. As shown in the example, there is no harm in thinking that $m=10$ and $h=2$ years, respectively. According to this, the coupon gets bigger or smaller depending on the difference between the 10-year and 2-year swap rates at times $t_{i}$ in the future. At times $t_{i}.$ , we are taking snapshots of the swap curve and paying the client a coupon proportional to the slope of the curve. In this particular case, the client would get progressively higher coupons if the swap curve becomes steeper and steeper during the following 5 years. The note will benefit from progressive steepening $i f$ it is not called.  

In order to engineer the coupons, first ignore the floor, and let the $\alpha$ represent a swaption premium allocated to the five settlement dates, as before. Now consider engineering the component,  

$$
\lambda(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h})
$$  

These coupons can be replicated using the following position: pay 2-year CMS rate and receive 10-year CMS rate for 5 years during the $t_{1},t_{2},t_{3},t_{4}$ . This can be accomplished by getting in two CMS. The structurer buys $\lambda$ units of the 10-year CMS and sells $\lambda$ units of the 2-year CMS. For simplicity the cash flows for the first 2 years only are shown in Figure 20.10.  

The figure incorporates the way CMS market quotes the CMS. It turns out that the market does this as a spread to the plain vanilla swap rate. Thus,  

$$
\mathrm{cms}_{t_{i}}^{10}=s_{t_{0},t_{i}}^{5}+s p_{t_{i}}^{10,5}
$$  

and  

$$
\mathrm{cms}_{t_{i}}^{2}=s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{2,5}
$$  

![](2ea59b1a9907c3c18c4bf7e530c649c91e4cf38b0a098ec5633c23390d772f92.jpg)  

# FIGURE 20.10  

CMS spread product and two CMS.  

where $s_{t_{0},t_{t}}^{5}$ is the 5-year vanilla (forward) swap rate known at time $t_{0}$ for the case swap beginning at time ti. spt $s p_{t_{0}}^{10,5}$ is the 10-year CMS spread for an instrument of 5-year maturity. The structurer will receive this. $s p_{t_{0}}^{2,5}$ on the other hand is the 2-year CMS spread for an instrument of 5-year maturity. The structurer will pay this. Note that at time $t_{0}$ , both spreads are known for all $t_{i}$ .  

Adding together the components we have:  

$$
\begin{array}{r l}&{c_{t_{i}}=\operatorname*{max}\Big[\lambda\Big(\mathrm{cms}_{t_{i}}^{10}-\mathrm{cms}_{t_{i}}^{2}\Big)+\alpha_{t_{i}},0\Big]}\\ &{\quad=\operatorname*{max}\Big[\lambda\Big(\Big(s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{10,5}\Big)-\Big(s_{t_{0},t_{i}}^{5}+s p_{t_{0}}^{2,5}\Big)\Big)+\alpha_{t_{i}},0\Big]}\\ &{\quad=\operatorname*{max}\Big[\lambda\Big(s p_{t_{0}}^{10,5}-s p_{t_{i}}^{2,5}\Big)+\alpha_{t_{0}},0\Big]}\end{array}
$$  

This is the coupon. Note that at this point of the engineering the floating rates have dropped, and the only unknown on the right-hand side is the participation rate $\lambda$ . Next we show how $\lambda$ can be determined.  

First remember that the principal $N$ is received from the investor. This is placed in a deposit account that pays the LIBOR rates $L_{t_{i}}$ in the future. At time $t_{0}.$ , one can get in a 5-year swap and convert these floating cash flows into a strip of known swap rate cash flows at the rate $s_{t_{0}}^{5}$ . This means at every $t_{i}$ the structurer will receive the known quantity $s_{t_{0}}^{5}$ . This is shown in Figure 20.11 for a simplified 2-year maturity version of the 5-year maturity product. Consider the following:  

$$
\lambda\Bigl(s p_{t_{0}}^{10,5}-s p_{t_{0}}^{2,5}\Bigr)=s_{t_{0}}^{5}
$$  

This is an equation where all quantities are known at $t_{0}$ except $\lambda$ . Solve for $\lambda$ and insert this number in the original coupon rate,  

$$
c_{t_{i}}=\operatorname*{max}\left[\lambda\Big(\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}\Big)+\alpha_{t_{i}},0\right]
$$  

In this expression, the unknowns are the CMS rates and this is the risk the client is assuming. To the structurer, however, the spread $\mathrm{cms}_{t_{i}}^{m}-\mathrm{cms}_{t_{i}}^{h}$ does not represent a risk since it can be hedged at a cost of $s p_{t_{0}}^{10,5}-s p_{t_{0}}^{2,5}$ . The example below shows this simple calculation.  

# EXAMPLE  

Suppose the 2-year and 10-year CMS trade at spreads of  

$$
\begin{array}{c}{{s p^{10,5}=50\mathrm{{bps}}}}\\ {{}}\\ {{s p^{2,5}=20\mathrm{{bps}}}}\end{array}
$$  

The difference is 30 bps. Suppose also that the 5-year swap rate is $4.5\%$ . Then $\lambda$ will be given by  

$$
{\frac{450}{30}}=15
$$  

This explains the high participation rates. Even if the curve steepens by a small $30~\mathrm{bp}$ , the investor can receive a coupon over $10\%$ : $\alpha_{t_{i}}$ plus the 450 bp.  

![](ffcac2d1c8632c0d3953ff451b2d1547764f74d926746f92e4eb9d1279e5f6c1.jpg)  

# FIGURE 20.11  

The structurer has determined all the unknown parameters. Essentially the structurer will buy and sell two CMS with different reference rates, buy floors and sell swaptions on CMS rates to manufacture a synthetic of the 5-year CMS note. Then the structurer will repackage these as a structured note and sell it to clients.  

# 20.4.5.1 A contractual equation  

This characterization is shown in the contractual equation below.  

![](e281d136f1584c326e9f400bf6010ef3f630afae3a13bf6d262d84ec504d5a46.jpg)  

As in the previous case, the synthetic structure can open several possibilities for the structurer. The structurer can buy swaption volatility, sell cap/floor volatility at advantageous rates from the retail client, and market them at better rates in the interbank market or to other clients. Again, as before, the structurer may in fact have some of the components of the synthetic on his books and the CMS spread note would be a good way of passing them along to other customers and removing them from the balance sheet.  

Or, the structurer can take the exposure itself. The structurer can buy/sell all the components in the right-hand side of the contractual equation except the swaption. Note that, then, if the expectation turns out to be correct, the synthetic structure will have a positive value. But, the note is callable. The structurer will call the note and close the position on the hedge side with a good profit. It is partly for this reason that when the callable notes are likely to pay very high coupons they are in fact called. The investors basically receive the high initial coupon.  

# 20.4.6 SOME OTHER STRUCTURES  

A special case of structured fixed-income products is called Target Redemption Note (TARN). This security provides a sum of coupons until a target level is reached. The note then terminates early. TARNs may be quite popular with investors when interest rates are low, or more correctly when they are heading lower. The additional risk in TARNs is the uncertainty of termination date. Although this is like a callable note, there is a difference. The termination condition is explicitly stated in a TARN and can easily be priced using the LIBOR market model. On the other hand, callable products contain embedded Bermudan swaptions. It is much more difficult to determine when the option will be exercised (i.e., called). Some investors may prefer the more transparent way the TARNs are redeemed early. Like the others, the instrument is path dependent.  

Another example is an inverse floater. As typical in such structured products, the first coupon is fixed. The subsequent coupons are set so as to depend on LIBOR inversely. When LIBOR rates decline, the coupon automatically increases. Often such coupons accumulate. If the accumulated coupons reach the target level, the note will be redeemed early. The client is paid the par value.  

We can also give examples of structured products that are useful for asset liability management. Consider a trigger swap that fixes borrowing costs for $T$ years at a level lower than the current comparable market rates. In this sense, it is an asset liability management tool. We discuss a simple variant. It is easy to complicate this simple prototype. Products such as trigger swaps belong in the category of fixed-income structured products although they are not marketed to investors. The clients are corporations and the product is useful in managing assets and liabilities. Still, the main idea is the same. The corporation has a view on the yield curve movements, or simply desires to lower hedging costs, which is the equivalent of yield enhancement.  

# 20.5 CONCLUSIONS  

We close this chapter with a comment on modeling structured products. Which model to use and how to calibrate the chosen models is clearly a crucial component of structured product trading. The structurer cannot buy these products in the wholesale market. The products need to be manufactured in-house. This requires extensive pricing and hedging efforts that will often depend on the model one is working with.  

In equity structured products, versions of the stochastic volatility model are found to be quite effective and are widely used. For fixed-income versions of the forward LIBOR model that incorporate some volatility, smile needs to be used.  

# SUGGESTED READING  

For LIBOR exotics consider Piterbarg (2005) and Andersen and Piterbarg (2010). Wystup (2006) is recommended for FX structured products. For the new equity structured products, Gatheral (2010) is required reading.  

# EXERCISES  

1. Case Study: Reverse-Convertibles and Volatility Trading  

This case study shows another example of volatility trading and reverse convertibles. Read the case study below and answer the following questions.  

a. What is a reverse-convertible bond? How would you decompose this instrument? How would a corporate treasurer use reverse-convertible bonds?   
b. How are the market professionals using reverse-convertibles? Why is there a “flood”?   
c. What is a synthetic convertible?   
d. What is the other solution mentioned in the text? What are the possible risks behind this solution?  

e. Finally, the regulators. Consider the case of French regulators and reverse-convertible bonds. Why would the regulators have an issue with these products? Do you think this is justified? Discuss briefly.  

Reverse convertibles activity soared to new heights last week, driven by sustained high stock index volatility   
levels across Europe and stock market jitters. Warrant professionals highlighted the increasing number of   
structuring banks involved in the sector and the broadening range of issuance currencies. These factors were evidence, they said, of the product’s growing acceptance throughout the industry.   
Stock index volatilities across Europe have consistently been in the high twenties of percentage points since   
the beginning of the year. Explaining the sudden surge in demand, equity derivatives professionals said reverse convertibles were an   
ideal means of taking advantage of current high volatility rates throughout Europe. Others said interest in the product was spreading across Europe, whereas it had previously been confined   
to Switzerland and Germany. “There’s been a flood. It’s all over the place,” enthused one German bank   
derivatives official. Reverse convertibles are credit products with an embedded put option referenced to a particular quoted   
company stock. The face value of the bond is discounted to the equivalent value of the option premium. If the   
stock price breaches a certain minimum value threshold, the bond investor receives equity instead of a cash   
payout. Credit Lyonnais Equity Derivatives was in the thick of the action, structuring three deals. Volkswagen was   
chosen as the underlying for an issue paying a $10\%$ coupon; Telecom Italia was selected as the reference   
stock for an issue paying an $1I\%$ coupon; and ABN AMRO was the reference for a third. If the stock price on the final date is greater than or equal to $95\%$ of the initial price, then the   
investor receives $100\%$ cash redemption. But if the price is below, then the investor receives one  

physical.  

Thomson Reuters IFR, June 1998  

2. Consider the swap and LIBOR curves available in Reuters or Bloomberg.  

a. Obtain the 3-month discount and forward curves   
b. Obtain the 2-year forward curve   
c. Find the components for the following note: maturity: 3 years Callable: each coupon payment date Payments: annual Coupons: Year $1\colon R_{1}$ Year 2: $\alpha_{1}\times(2$ -year CMS) $+$ previous coupon Year 3: $\alpha_{2}\times$ (2-year CMS) $+$ previous coupon   
Determine the unknowns $R_{1}$ $\mathbf{\Psi}_{1},\alpha_{1},\alpha_{2}$ .   
d. Find the components for the following note: Maturity: 3 years Callable: each coupon payment date Payments: annual Coupons: Year $1\colon\mathsf{R}_{1}$ Year 2: $x\times[(3\mathrm{{-y}e a r\ {C M S}})-(2\mathrm{{-y}e a r\ {C M S}})]+\beta_{1}$ Year 3: $x\times[(3\mathrm{{-y}e a r\ {C M S}})-(2\mathrm{{-y}e a r\ {C M S}})]+\beta_{2}$   
Determine the unknowns $R_{1},\alpha,\beta_{i}$ .   
e. In the latter case, when would $\beta_{1}=\beta_{2}?$  

3. What follows is the description of a rather complex swap structured by a bank. The structure is sold for the purpose of liability management and involves an exotic option (digital cap) and a CMS component.  

At time 0 the bank and the client agree to exchange cash flows semiannually for 5 years according to the following rules:  

The bank pays semiannually, 6m-LIBOR on the notional amount. This is a vanilla swap. The client pays a coupon $c_{t}$ according to the following formula:  

$$
c_{t}=c_{1t}-c_{2t}
$$  

where  

$$
\begin{array}{r}{c_{1t}=\left\{\begin{array}{l l}{\mathrm{LIBOR}+47\mathrm{bp}\%}&{\mathrm{if}\quad\mathrm{LIBOR}<4.85\%}\\ {5.23\%}&{\mathrm{if}\quad4.85\%<\mathrm{LIBOR}<6.13\%}\\ {2.98\%}&{\mathrm{if}\quad\mathrm{LIBOR}>6.13\%}\end{array}\right.}\\ {c_{2t}=\{\mathrm{cms~}(30Y)-(\mathrm{cms~}(10Y)+198\mathrm{bp})\}}\end{array}
$$  

for the first 2 years. And  

$$
c_{2t}=8\{\mathsf{c m s}(30Y)-(\mathsf{c m s}(10Y)+198\mathrm{bp})\}
$$  

for the last 3 years.  

a. Unbundle this LIBOR exotic into vanilla products the best you can. b. Why would an investor demand this product? What would be his or her expectations?  

Show how you would engineer the following Snowball Note.   
Issuer: ABC bank   
Notional: $\$10$ mio   
Tenor: 10 years; Principal: Guaranteed at maturity   
Coupon: Yr 1; Q1: $9.00\%$   
Q2: Previous Coupon $+\mathrm{CMS}104.65\%$   
Q3: Previous Coupon $+\thinspace{\bf C M S}10\ 4.85\%$   
Q4: Previous $\mathrm{Coupon+CMS105.25\%}$   
Yr 2 Q1: Previous $\mathrm{Coupon+CMS105.45\%}$   
Yr 2 Q2 Q4: Previous $\mathrm{Coupon+CMS105.65\%}$   
Yr 3: Previous $\mathrm{Coupon+CMS105.75\%}$   
Yr 4 10: Previous Coupon   
Coupon subject to a minimum of $0\%$   
Call: Callable on each coupon   
a. What is the view of the investor?   
b. What are the risks?   
c. Now forget about the call provision and calculate the coupons paid under the two following realizations of LIBOR rates:   
Realization $1=5.0$ , 6.0, 6.5, 7.0, 8.0, 9.0, 10.0   
Realization $2=\mathrm{LIBOR}$ stays at 3.5   
d. How can you characterize these coupons using a swap? What type of swap is this?   
e. Suppose you have 8 annual FRAs quoted to you. How can you price these coupon payments?   
f. How do you generate the first-year coupon?   
g. Are the coupons floored at 0?   
h. Write a contractual equation representing this instrument.  

5. Show how you would engineer the following CMS spread note. Issuer: ABC Notional: $\$100$ Tenor: 10 years Principal: Guaranteed at maturity Coupon: Yr 1: $11.50\%$ Yr 2 $10\colon16\times\mathrm{(CMS30-CMS10)}$ , max of $30\%$ , min $0\%$ Call: Callable on each coupon date by the issuer a. What is the view of the investor? b. What are the risks?  

This page intentionally left blank  