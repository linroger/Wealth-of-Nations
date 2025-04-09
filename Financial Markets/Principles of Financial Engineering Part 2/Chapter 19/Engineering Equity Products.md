# 19.6 ENGINEERING EQUITY PRODUCTS  

# 19.6.1 PURPOSE  

Companies raise capital by issuing debt or equity.12 Suppose a corporation or a bank decides to. raise funds by issuing equity. Are there more advantageous ways of doing this? Financial engineering offers several alternatives that may address the company's specific needs..  

1. Some strategies may decrease the cost of equity financing.   
2. Other strategies may result in modifying the composition of the balance sheet.   
3. There are steps directed toward better timing for issuing securities depending on the direction of interest rates, stock markets, and currencies.  

4. Finally, there are strategies directed toward broadening the investor base.  

In discussing these strategies, we consider two basic instruments that the reader is already familiar with. First, we need a straight coupon bond issued by the corporation. The second instrument is an option written on the stock. The (call) option on the stock is of European style, has expiration date $T$ and strike price $K.$ The call is sold at a premium $C\left(t_{0}\right)$ . Its payoff at time $T$ is  

$$
C\left(T\right)=\mathrm{max}\left[S_{T}-K,0\right]
$$  

These sets of instruments can be complemented by two additional products. In some equitylinked products, we may want to use a call option on the bond as well. The option will be European. In other special cases, we may want to add a credit default swap to the analysis. Many useful synthetics can be created from these building blocks. We start with the engineering of a convertible bond in a simplified setting.  

# 19.6.2 CONVERTIBLES  

In Chapter 17, we discussed callable bonds that convey an option to the issuer to redeem the bond issue early. Convertible bonds and convertible preferred stock are another example of securities with embedded options. In contrast to callable bonds they give an option to the holder of the security rather than the issuing firm. A convertible bond is a bond that incorporates an option to convert the principal into stocks. The principal can be converted to a predetermined number of stocks of the issuing company. Otherwise, the par value is received. It is clear that the convertible bond is a hybrid product that gives the bond holder exposure to the company stock in case the underlying equity appreciates significantly.  

Consider the example of a convertible bond with a conversion ratio of 20 and a par value of $\$1000$ . This allows the convertible bond holder to convert one bond of par value $\$1000$ into 20 shares of common stock. The conversion price is defined as the par value divided by the conversion ratio or. $\$10000$ , that is. $\$50$ in this example. The bond holder evaluates whether it is worth fore-. going bonds with a face value of. $\$1000$ or $\$50$ per share. When is it optimal for the holder to con-. vert the bond? This is the case when the present value of the bond's promised payments is $<20$ times the value of one share of stock. A convertible bond that is trading at $\$900$ and has a conversion ratio of 20 might be worth converting if the stocks were selling above $\$45$ since the value of 20 shares that the holder would receive for each bond is higher than $\$900$ . The bond's conversion. value is defined as the value that it would have if the holder converted it into stock.  

Can we say anything about the price of the convertible bond and how high it should be relative. to the conversion value and the value of a straight bond? On the one hand, the convertible bond should trade at least as high as its conversion value. Otherwise one could buy the convertible bond,. convert it and make an immediate profit. Such an arbitrage strategy could in reality be expected to. push up the price to the conversion value or above.  

On the other hand, the convertible bond is worth at least as much as a straight bond since the convertible consists of a straight bond plus a call option. The straight bond value provides a bond floor. Figures 19.6a illustrates the straight bond value. For bond issuers with a strong balance sheet, the straight debt value should be largely independent of the value of the stock since the default risk  

![](images/7113629a132dc6ea169092a7580ea63f5d5ab6578f75f081766cf14ff4f91fca.jpg)  

# FIGURE 19.6  

Convertible bond, conversion, and straight bond value.  

is negligible. This is represented by the horizontal bond floor. If the bond is risky then as the stock price declines the bond value can be expected to decline and even become worth close to zero as it becomes distressed. Figure 19.6b illustrates the conversion value. Figure 19.6c shows that the convertible bond value is bounded from below by the straight (risky) bond value when the stock price. makes conversion unlikely. In this case, the convertible is also referred to as being busted. It is bounded from below by the conversion value when the stock price is high enough to make conversion likely. When the stock price is significantly above the conversion price, the convertible. behaves like equity. The difference between the convertible bond value and the conversion value is. called the conversion premium. Some convertible bonds have a required conversion or redemption feature, in which case they are called mandatory convertibles.  

We discuss the engineering of such a convertible bond under simplified assumptions. In the first case, we discuss a bond that has no default risk. This is illustrative, but unrealistic. All corporate bonds have some default risk. Sometimes this risk is significant. Hence, we redo the engineering,. after adding a default risk in the second example..  

# 19.6.3 SYNTHETIC CONVERTIBLE BONDS AND CASH FLOW ENGINEERING  

From the above discussion, we can see that a convertible bond can be viewed as a portfolio of a straight bond plus a call option. This leads us to the following contractual equation..  

![](images/7eb5fede3df593f74f230afafa01c7a952b09abb803f51f879561fb9cea9b537.jpg)  

Figure 19.7 shows the composition of a convertible bond's cash flows into a defaultable bond and a call option.13 There are four potential scenarios depending on whether the bond defaults or not and whether the option is exercised or not.  

As the issuer sells an embedded option to convert its shares, the issuer expects to pay a lower fee or coupon. The buyer of the convertible is rewarded by the potential to participate in the upside of the company.  

For a risky bond, we can also build on the discussion from the previous chapter on CDS which showed that a defaultable can be replicated by a portfolio consisting of a receiver interest rate swap, a default-free deposit and selling a CDS. Thus if we replace the straight bond in Eq. (19.31) by a portfolio we obtain the following contractual equation:.  

![](images/e1b3e51ffb86512ca001506820facaa71cf878a786a4ae27a3e5d8620f434314.jpg)  

This contractual equation provides an interesting insight since it shows that the convertible bond contains default risk that can be hedged by buying a CDS..  

![](images/cfb1e06b2ac030f32263261532f4413f1dd5d3907ea2193e0aee3b046af02637.jpg)  

# FIGURE 19.7  

Convertible bond decomposition.  

<html><body><table><tr><td colspan="2">Table 19.2 Intel Corporation 2.95% Convertible Bonds Due in 2035</td></tr><tr><td>Issuer</td><td>INTEL CORP</td></tr><tr><td>Par amount Conversion ratio</td><td>$1000 34.9501</td></tr><tr><td>Conversion price Conversion value Coupon (fixed) (Conversion) Parity Conversion premium (over conversion value)</td><td>28.6122 1000 2.95% 110.547 15.703</td></tr><tr><td>Price of one Intel Share Yield to maturity</td><td>31.63 1.51</td></tr><tr><td>Coupon Frequency Price of the convertible bond Call provision</td><td>Semiannual 126.25 None</td></tr><tr><td>Implied volatility Delta</td><td>62.194 0.560</td></tr><tr><td>Vega Theta</td><td>0.268 0.004</td></tr><tr><td>Psi Credit sensitivity</td><td>-2.092 -3.539</td></tr><tr><td>Aggregate amount issued</td><td>1,600,000 (M)</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td>Announcement date</td><td>03/30/2006</td></tr><tr><td>1st coupon date</td><td>06/14/2035</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td>Convertible until</td><td>12/14/2035</td></tr><tr><td>Maturity date</td><td>12/15/2035</td></tr><tr><td></td><td></td></tr><tr><td>Book Runner</td><td>JPM</td></tr><tr><td></td><td></td></tr><tr><td>Source:Bloomberg,July15,2014.</td><td></td></tr></table></body></html>  

# 19.6.4 REAL-WORLD EXAMPLE  

It is instructive to examine a real-world example. Table 19.2 provides information on a convertible bond issued by Intel. The bond matures in 2035. The bond pays a $2.95\%$ semiannual coupon. The reported conversion ratio is 34.9501 and the conversion price is 26.6122. If we multiply the conversion ratio times the conversion price we obtain a conversion value of 1o00. The share price of Intel on that day was 31.63. The convertible bond is currently selling for 126.25 per $\$100$ or 1262.5 per $\$1000$ par value. The conversion parity is defined as the share price multiplied by the conversion ratio: $34.9501\times31.63=1105.47$ . The conversion premium is defined as the price of the convertible minus the conversion parity, that is $1262.5-1105.47=157.03$ per $\$1000$ or $\$15.703$ per $\$100$ as indicated in the table. The implied volatility is 62.194 and can be compared to the implied volatility of equity options on Intel shares on that day. The delta is the sensitivity of the convertible bond to changes in the share prices and it is 0.56 according to the table.  

# 19.6.5 CONVERTIBLE BOND PRICING  

# 19.6.5.1 Bond plus equity option approach  

There are several issues that complicate the decomposition in Eq. (19.31) and any valuation based on it. These complications include dividend payments by the stock, a conversion price that may increase over time and any potential call options that allow the issuer to repurchase the bond early. Moreover, convertible bonds contain an option component with a stochastic strike price equal to the bond price.  

# 19.6.5.2 Multifactor model  

A further complicating factor relates to default risk. As we saw in Figure 19.6, the share price level is a key determinant of the convertible bond value. In principle, this means that we can use the Black--Scholes approach to value the convertible with the state variable being the share price and use a dynamic hedging strategy to value to embedded option. However, as Figure 19.6c shows, the credit risk of the bond also depends on the stock price. The most recent and sophisticated convertible bond pricing models incorporate the stochastic nature of interest rates and credit spreads. References to recent papers on convertible bond pricing are provided at the end of the chapter. Bloomberg's convertible bond pricing function, for example, incorporates not only time-varying interest rates, dividends, and volatility but also allows for jumps in the stock price which can be calibrated to CDS data..  

# 19.6.6 CONVERTIBLE BOND ARBITRAGE  

Historically some of the most active buyers of convertible bonds were hedge funds.'4 However, recent estimates suggest that the proportion of hedge funds as buyers of convertible bonds has fallen from $75\%$ in 2008 to less than $40\%$ in 2013.  

Convertible arbitrage strategies are used by hedge funds in an attempt to generate risk-adjusted performance. Consider the following reading.  

# EXAMPLE  

Convertible arb hedge funds in the U.S. are piling into the credit default swaps market. The step-up in. demand is in response to the rise in investment-grade convertible bond issuance over the last month, coupled with illiquidity in the U.S. asset swaps market and the increasing credit sensitivity of convertible players' portfolios, said market officials in New York and Connecticut.   
Arb hedge funds are using credit default swaps to strip out the credit risk from convertible bonds, leaving them with only the implicit equity derivative and interest rate risk. The latter is often hedged through futures or treasuries. Depending on the price of the investment-grade convertible bond, this strategy is often cheaper than buying equity derivatives options outright, said [a trader].   
Asset swapping, which involves stripping out the equity derivative from the convertible, is the optimal. hedge for these funds, said the [trader] as it allows them to finance the position cheaply, and removes. interest rate risk and credit risk in one fell swoop. But with issuer-credit quality in the U.S. over the last 12 to 18 months declining, finding counterparties willing to take the other side of an asset swap has become. more difficult. ..  

(Based on an article in Derivatives Week (now part of GlobalCapital)  

Convertible bonds are generally issued at a discount to their theoretical value. This implies that hedge fund managers can extract the undervalued component from the convertible using appropriate techniques. One of the most basic convertible bond arbitrage strategies is to buy cheap volatil-. ity. A convertible bond consists of a bond and an option as we saw earlier. A hedge fund manager can calculate the price of the embedded option or the equity volatility implied by the current price. of the convertible. By comparing the implied volatility of the embedded option to historical volatil-. ity or the implied volatility of listed options on the same stock, it is possible to calculate whether the embedded option in the convertible bond is undervalued. The implied equity volatility is the. volatility that needs to be entered into a convertible bond pricing model together with other input parameters in order to generate the observed convertible bond price. The implied volatility for the. convertible bond issued by Intel, for example, was 62.194 according to the Bloomberg data in Table 19.2.  

If the option embedded in the convertible is cheaper than a vanilla call option on the same. stock, then a fund can go long the convertible bond in the hope that the undervalued embedded option will appreciate in value. A range of techniques can be employed to hedge against unwanted risks and isolate the desired equity, credit, event, or even currency exposure embedded in the securities.  

The basic convertible bond arbitrage strategy is long volatility. This means that the strategy ben-. efits from volatility in the underlying stock. The volatility exposure arises from two different sources. First, the embedded stock option implies that the buyer of the convertible bond is long. gamma, that is the rate of change in the delta with respect to stock prices. Second, the strategy is long vega since the call option price rises if implied volatility rises. In the case of the Intel convertible discussed above, the vega was O.268. If the implied volatility corrects and rises, this will lead to gains for the holder of the convertible bond. Convertible bonds are also exposed to more complex risk including credit risk. On the one hand, a deterioration in the creditworthiness of the issuer is likely to coincide with an increase in the volatility of the underlying stock which in turn affects the value of the embedded call option. The opposite is likely to happen if creditworthiness. improves. On the other hand, a deterioration of the credit quality of the issuer directly affects the underlying risky bonds. As credit spreads tighten, the value of a convertible bond is likely to increase. As credit spreads widen its value decreases..  

Equation 19.32 showed that a convertible bond can be decomposed into several constituents including a CDS position. Therefore, CDS can be used to hedge credit risk embedded in a long convertible bond position. The reason is that the mark-to-market value of an existing CDS position will change as the credit risk of the issuer changes. To establish the correct hedge ratio, we examine how sensitive the CDS is to changes in credit spreads relative to the sensitivity of the convertible bond. Omnicron measures the price impact of an increase in credit spreads. Typically this measure is rebased for 1 basis point increase in the level of credit spreads. Practitioners also call this sensitivity the Credit Dv01.  

The equity market risk can be hedged using short stock positions or put options. The credit market risk exposure is in principle best hedged using CDS. However, sometimes, equity market puts may be a cheaper hedging alternative than CDS. As the Merton model illustrated, equity market and credit markets are linked. One can calculate the sensitivity of put options and CDS to the underlying credit risk and use this sensitivity as a hedge ration and choose between a CDS or equity put option hedge depending on which one is cheaper.  

# 19.6.7 COMPARING THE ROLE OF VOLATILITY IN CONVERTIBLE BOND ARBITRAGE AND CAPITAL STRUCTURE ARBITRAGE  

As we saw in Section 19.5, in capital structure arbitrage we can interpret the straight bond as an equity derivative since there is a theoretical relationship between the bond and the equity. We can use a Merton-type model to calculate the equity volatility implied by the share price and the credit spread. If this implied equity volatility differs from what is viewed as the correct volatility, the market participant can buy or sell the bonds (or the CDS) and delta hedge the position. There is an important difference between the capital structure arbitrage strategy and the convertible bond arbitrage strategy since a convertible bond can be converted into equity while a straight bond cannot. This implies that there are theoretical arbitrage bounds for the convertible but no such bounds exist for straight debt based on the Merton-type models. This in addition to the restrictive assumptions of the Merton model imply that arbitrage strategies based on simple structural models of default may not predict actual movements in equity and credit markets well.  

# 19.6.8 INCORPORATING MORE COMPLEX STRUCTURES  

This section considers two variations of the basic convertible structure. First of all, the basic convertible can be modified in a way that will make the buyer operate in two different currencies. In fact, a dollar-denominated bond may be sold, but the underlying shares may be, say, French shares, denominated in Euros. This amounts, as we will see, to adding a call or put option on a foreign currency.  

The second alternative is also important. The basic convertible can be made callable. This amounts to making the underlying debt issue a callable bond. It leads to adding a call option on the bond. Before we see how these are used, we consider some of the financial engineering issues in each case.  

# 19.6.8.1 Exchange rate exposure  

Suppose the convertible bond is structured in two currencies. A Thai company secures funding by selling a euro convertible in the Eurodollar market, and the debt component of the structure is denominated in dollars. So, the bonds have a par value of, say, $\$100$ . The conversion is into the shares of the firm, which trade, say, in Bangkok. The shares are baht denominated. We assume, unrealistically, that there is no default risk.  

Because Thai shares trade in Thai exchanges and are quoted in Thai baht, the conversion price to. be included in the convertible bond needs to specify something about the value of the exchange rate to. be used during a potential conversion. Otherwise, the conversion rule will not be complete. That is to say, instead of specifying only the number of shares,. $n$ , and the conversion price, $K.$ using the equality  

$$
100\S=K n
$$  

the conversion condition now needs to be  

$$
e_{t}100\Phi=K n
$$  

where $e_{t}$ is an exchange rate denoting the price of USD1 in terms of Thai baht at date $t.$ This is needed since the original conversion price, $K$ , will be in Thai baht, yet, the face value of the bond. will be in USD. The bond structure can set a value for. $e_{t}$ and include it as a parameter in the con-. tract. Often, this. $e_{t}$ will be the current exchange rate..  

![](images/961c91e46ec267ddc53fe261ed4266354173982a6235a2af7b29c7367101f105.jpg)  

# FIGURE 19.8  

Convertible with currency conversion.  

Now, suppose a Thai issuer has sold such a Euro convertible at. $e_{t}$ the current exchange rate. Then, if Thai stocks rise and the exchange rate remains stable, the conversion will occur. Here is the important point. With this structure, at maturity, the Thai firm will meet its obligations by using. its own shares instead of returning the original. $\$100$ to bond holders. Yet, if, in the meantime, $e_{t}$ rises,15 then, in spite of higher stock prices, the value of the original principal. $\$100$ , when measured in Thai baht, may still be higher than the $n S_{T}$ and the conversion may not occur. As a result, the. Thai firm may face a significant dollar cash outflow.16  

This shows that a convertible bond, issued in major currencies but written on domestic stocks,. will carry an FX exposure. This point can be seen more clearly if we reconstruct this type of convertible and create its synthetic. This is done in Figure 19.8..  

The top part of Figure 19.8 is similar to Figure 19.7. A straight coupon bond with coupon $c$ matures at time $t_{3}$ and pays the principal $\$100$ . The difference is in the second part of the figure. Here, we have, as usual, the call option on the stock $S_{t}$ But $S_{t}$ is denominated in baht and the call will be in-the-money--that is to say, the conversion will occur only if  

$$
n S_{t_{3}}>100e_{t_{3}}
$$  

The idea in Figure 19.8 is the following. We would like to begin with a dollar bond and then convert the new call option into an option as in the case before. But, if the Thai baht collapses,17. then the $\$100$ received from the principal at maturity will be much more valuable than. $S_{t_{3}}n/e_{t_{0}}$  

# 19.6.8.2 Making the convertibles callable  

One can extend the basic convertible structure in a second way and add a call option on the underlying convertible bond. For example, if the bond maturity is. $T$ then we can add an implicit option. that gives the issuer the right to buy the bond back at time, U. $;U<T$ at the price  

$$
\operatorname*{max}\left[\$100,nS_{U}\right]
$$  

This way the company has the right to force the conversion and issue new securities at time $U$ Some corporations may find this a useful strategy.  

With this type of convertible, forcing the conversion is the main purpose. Suppose the following :wo conditions are satisfied:  

1. The share is trading at a higher price than the conversion price (i.e., the strike $K_{\cdot}$ 2. The expected future dividends to be paid on the stock are lower than the current coupon of the convertible.  

Then, if the convertible is callable, the issuer may force the conversion by calling the bond. This will convert a debt issue in the issuer's balance sheet into equity and affect some important ratios, in case these are relevant. Second, the immediate cash flow of the firm will improve..  

# 19.6.8.3 Exchangeable bond  

The basic convertible-warrant structures can be modified to meet further financial engineering needs. We can consider another example. Suppose the convertible bond, when it converts, converts into another company's security. This may be the case, for example, if company. $A$ has acquired an interest in company B. This way, the company can sell convertible bonds where the conversion. is into company B's securities.  

From a financial engineering point of view, the structure of this "exchangeable"' is the same. Yet, the pricing and risk management are different because now there are two credits that affect the price of the bond: the credit of the company that issues the bond and the credit of the company this bond may convert.  

Another difference involves the dilution of the shares of the target company. When a convertible is issued and converts at a later date, there may be dilution of the shares, yet, in an exchangeable the shares that are exchanged will come, in general, from the free float..  

# 19.6.9 USING CONVERTIBLES  

A convertible bond has some attractiveness from the point of view of end investors. For example, the investor who buys the convertible will have some exposure to the share price. If $S_{t}$ increases significantly, the bond becomes a portfolio of shares. On the other hand, if the bond fails to convert, the investor has at least some minimum cash flow to count on as income, and the principal is recovered (when there is no default)..  

But, our interest in this book is not with the investors, but rather, in the advantages of the prod uct from an issuer's point of view. For what types of purposes can we use a convertible bond?.  

The first consequence of issuing convertibles rather than a straight bond is that the convertible carries a lower coupon. Hence, it "seems' like the funds are secured at lower cost..   
More notably for a financial engineer, convertibles have interesting implications for balance. sheet management. If an equity-linked capital is regarded as equity, it may have less effect on. ratios such as debt to equity. But, in general, rating agencies would consider straight. convertibles as debt rather than equity.   
Note that with a convertible, in case conversion occurs, the shares will be sold at a higher price than the original stock price at issue time.. Finally, convertibles are bonds, and they can be sold in the Euro markets as Euro-convertibles. This way a new investor base can be reached..  

We should also point out that convertibles, when combined with other instruments, may have significant and subtle tax advantages. The best way to show this is by looking at an example from the markets.  

# EXAMPLE  

(ABC Capital) has entered into a total return swap on 154,000 shares of Cox Communications preferred stock exchangeable into shares of Sprint PCS, and a total return swap on 225,000 shares of Sprint PCS. In the Cox swap, the hedge fund pays three-month LIBOR plus 50 basis points and receives the return on the exchangeable preferred shares. In the Sprint swap, ABC pays the return on the stock and receives threemonth LIBOR less 25 bps. Both total return swaps mature in about 13 months..   
The total return swaps were entered into for tax reasons. ABC's positions are held by a Cayman Islands limited duration company. Because the Cayman Islands do not have a tax treaty with the U.S., income from these securities is withheld at the non-treaty rate of. $30\%$ . Entering the total return swaps ensures that ABC does not physically hold the securities, and, hence, is not subject to U.S. withholding.   
The underlying position was put on as part of a convertible arb play. ABC bought the exchangeable preferred stock and is using the cash equity to delta hedge the implicit equity option. The market is   
undervaluing the exchangeable preferred shares, according to a trader, who noted that although these shares recently traded at USD76.50, the fund's models indicate they should be priced around USD87. The company's. model is based in part on the volatility of the underlying stock, the credit quality of the issuer, and the features of the convertible. In this case, the market may be undervaluing the security because it is not pricing in all the features of the complicated preferreds and because of general malaise in the telecom sector.  

(Derivatives Week (now part of GlobalCapital), November 2000)  

This reading is also an example of how implicit options can be used to form arbitrage portfolios.   
However, there are many delicate points of doing this as were shown earlier..  

# 19.6.10 WARRANTS  

Warrants are detachable options linked to bonds. In this sense, they are similar to convertibles.   
But, from a financial engineering point of view, there are important differences..  

1. The warrant is detachable and can be sold separately from the bond. Of course, a financial engineer can always detach the implicit option in a convertible bond as well, but still there are differences. The fact that the warrant is detachable means that the principal will always have to be paid at maturity.  

The number of warrants will not necessarily be chosen so as to give an exercise cash inflow that equals the cash outflow due to the payment of the principal. Thus, the investor can, in principle, end up with both the debt and the equity arising from the same issue..   
2. The exchange rate used in a convertible is fixed. But, because there is no such requirement for a warrant and because the latter is detachable, this is, in general, not the case for a warrant. Hence, there is no implicit option on the exchange rate in the case of warrants. In this sense warrants are said to be relatively more attractive for strong currency borrowers, whereas convertibles are more attractive for weak currency borrowers.   
3. Finally, because warrants are detachable, the warrant cannot be forced to convert. The bond can be called, but the conversion is not required.  

We now move to another topic and look at securitizing cash flows. This can be regarded as ar example of new product structuring.  
