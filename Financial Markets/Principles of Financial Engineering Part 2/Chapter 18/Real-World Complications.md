# 18.4 REAL-WORLD COMPLICATIONS  

Credit markets and credit derivatives trading are inherently more complicated and heterogeneous. than most other markets, and one faces an unusual number of real-life complications that theoretical models may not account for. In this section, we look at some of the real-life aspects of CDS contracts.  

Contractual equation (18.6) provides a natural hedge for the CDS and shows one way of. pricing it. Similar contractual equations may provide usable hedges and pricing methods for some bread-and-butter instruments with negligible credit risk, but for CDSs these equations are essen-. tially theoretical. The simplified approach discussed above may sometimes misprice the CDS and. the hedge obtained earlier may not hold. There may be several reasons why the benchmark. spreads on this credit may deviate significantly from the CDS rates. We briefly discuss some of these reasons.  

1. In the preceding example, the CDS had a maturity of 3 years. What if the particular credit had. no outstanding 3-year bonds at the time the CDS was issued? Then the pricing would be more. complicated and the benchmark spread could very well deviate from the CDS rate.   
2. Even if similar maturity bonds exist, these may not be very liquid, especially during times of. high market volatility. Then, it would be natural to see discrepancies between the CDS rates and the benchmark spreads.   
3. The tax treatment of corporate bonds and CDSs is different, and this introduces a wedge between the corresponding spread and the CDS rate.   
4. As mentioned earlier, CDSs result in physical delivery in the case of default. But this delivery is from a basket of deliverable bonds. This means that the CDS contains a delivery option, which was not built into the contractual equation presented earlier.  

In reality, another important issue arises. The construction of the synthetic shown above used a money market account that was assumed to be risk free. In general, such money market accounts are almost never risk free and the deposit-accepting institution will have a default risk. This introduces another wedge between the theoretical construction and actual pricing. This additional credit risk that creeps into the construction can, in principle, be eliminated by buying a new CDS for the deposit-accepting institution.  

The following reading illustrates some of the real-world complications, such as liquidity issues, in the context of credit curve strategies. Standard fixed-income strategy can also be applied in the credit sector.  

Just as in the case of standard fixed-income products, the credit curve allows for curve flattener and curve steepener trades. The idea is self explanatory and follows the fixed-income swap. positions applied to the iTraxx curve..  

# EXAMPLE  

Consider Hutchison Whampoa credit-curve flattener via bond-basis play, exploiting value in long end while protecting against any general market deterioration. Buy Hutch 2027 bonds (cheapest on curve), buy 5-year CDS protection. Spread now 82 bps (asset-swap bond spread 131 bps versus CDS at 49 bps). Target compression to 65 bps in coming months. Exit if spread widens to 90 bps.  

Trade primarily a play on long-end bonds: buying protection at shorter end offers hedge in case of bad news on Hutch or general bond downturn. CDS cheaper alternative to selling short-end bond given lack of repo liquidity; using asset swap avoids fixed-rate risk at short end. Spread should slowly grind tighter as more investors switch out of shorter Hutch bonds (2010, 2011, 2014 maturities) where value has already been squeezed out into undervalued longer end.  

This trade can be interpreted as primarily a play on long-end bonds. The reason why the pro-. tection is bought at the shorter maturity end is that it offers a hedge in case of bad news on Hutch or general bond downturn in the near term. The reason why a CDS was chosen over shorting a bond is that the CDS is cheaper than the alternative of selling a short-end bond given the relative lack of repo liquidity in the corporate bond market. The use of an asset swap avoids fixed-rate risk at the short end. Spread should slowly grind tighter as more investors switch out of shorter Hutch bonds (2010, 2011, 2014 maturities) where value has already been squeezed out into undervalued longer end.  

# 18.4.1 CDS STANDARDIZATION AND 2O09 "BIG BANG"  

On April 8, 2009, a "Big Bang" occurred in the market for CDS contracts and the way in which. they are traded. The changes affected both contracts and conventions. The standardization had three. main parts: auction hardwiring, standardizing trading conventions, and central clearing. We discuss the main elements of these below.19  

# 18.4.1.1 Auction hardwiring  

ISDA released a supplement and a protocol for credit and succession events in 2009. This led to the creation of regional Determination Committees of dealers and investors to arbitrate when a credit event arises. The committee's decisions are binding. If a committee decides on a specific credit event an automatic and mandatory CDS auction settlement process takes place.  

# 18.4.1.2 Standardization coupons and trading conventions  

The standardization of North American Corporate CDS saw the introduction of fixed coupons of 100-500 bp. For more than a decade after they were first introduced most single-name CDS contracts traded with coupons in all-running format, that is single-name CDS traded on a running spread or par spread basis which meant that the protection buyer pays for protection by making premium (or spread) payments to the protection seller. Consider a 5-year CDS with a $\$10$ million notional, for example. If we assume that the running spread was $200\mathrm{bp}$ , the protection buyer paid $\$200,000$ a year (typically in quarterly installments).  

Under the running spread convention, no money was exchanged upfront which implied that CDS positions were implicitly leveraged. Following the April 2009 "Big Bang" in the CDS market, the market moved to an points upfront basis. Nowadays contracts have fixed coupons of either $100\mathrm{bp}$ or 500 bp. The upfront payments are made at initiation and are equal to the present value of the difference between the current market credit spread and the fixed coupon. As an example, if a contract with a fixed coupon of. $100\mathrm{bp}$ is trading at $200\mathrm{bp}$ the protection buyer will make an. upfront payment equal to the present value of the difference between 200 bp and 100 bp. The payment made in the opposite direction of the market spread is below the coupon. Note that the most liquid indices such as CDX and iTraxx have traded on such a points upfront basis for a long time. These market conventions do not require a major modification of CDS pricing approaches since a running spread contract can be viewed as a special case of an upfront and fixed-coupon. contract where the upfront is zero and the fixed coupon is equal to the par spread.  

How is the fixed coupon set for CDS indices? When the new series of the index is launched, the fixed coupon, which is also known as a deal spread, since it is expressed as a spread, is determined.  

The move to the points upfront basis for single-name CDS has three advantages. First, it will. make netting between single name and index positions easier. Such positions are common as we will see below in the context of index arbitrage trades. Second, the more convenient netting also facilitates the recent move of CDS contracts to central clearing. Third, it also reduces market participant's exposures to sudden market movements or jump risk which we discuss in more detail in the context of CDS unwinding later.  

# 18.4.1.3 Central clearing  

The changes above facilitated the introduction of central clearing for CDS. As discussed below in the context of unwinding of CDS, central clearing helps reduce counterparty risk in the CDS mar-. ket. Central clearing for CDS in the United States and Europe began in 2009..  

# 18.4.2 RESTRUCTURING  

Another real-life complication deals with the definition of default itself. Credit events are normally failure to pay and bankruptcy. Any nonpayments of interest or principal would count as the former and any type of formal bankruptcy would count as the latter. In our theoretical engineering, we used this second definition of defaults. Yet, in reality, most single-name CDSs also consider restructuring as an additional default event. Further complicating the picture is the type restructuring, summarized below.  

There are four types of restructuring clauses in the CDS contracts.2o The first is simply norestructuring, No R. In this case, any structuring would not constitute a credit event. It is important to note that credits have come to trade based on market-defined conventions. Normally, high-yield CDS typically trade No R. This is especially true of the CDX indexes in the United States. Markit iTraxx indices trade with Modified-Modified Restructuring except for the Sub-Financials which trade with Restructuring.  

The second type is modified restructuring, Mod $R$ This creates new conditions for a credit event.2' North American investment grade names trade with a "Modified' restructuring convention. Mod $R$ clauses arose historically for these North American investment-grade credits because of the needs of hedgers of bank loan portfolios.  

The third is the modified modified restructuring, Mod Mod R. In this case, the maturity limits on the deliverable bonds or loans are somewhat different. There is an exception that the bonds (loans) with a maturity of more than 30 months but no more than 60 months can be delivered. European CDS contracts typically traded with a Mod-Mod R convention. The Mod-Mod R convention in Europe stems from the fact that in Europe bankruptcy laws make it difficult for borrows to file in many jurisdictions.  

The fourth type is Old $R$ or Old Restructuring. Old R clauses imply that there is no limit on the. maturity of the deliverable obligation and no tranching in the auction postcredit event. Western European sovereign CDS typically contain the clause Old R..  

Obviously CDS contracts with restructuring will have higher CDS spreads than the contracts of the same name, without restructuring. Note the key difference: in a bankruptcy or failure-to-paytype credit event the price differences of deliverable bonds will be relatively small. In a restructuring, the deliverable bonds could have very different values depending on the maturity. The protection buyer has the option to deliver the cheapest bond and hence this option could be very expensive.  

# 18.4.3 FIXED RECOVERY CDS  

CDSs with fixed recovery rates are called Fixed Recovery CDS and are also known as Digital CDS or Binary CDS. In contrast to standard CDSs which require a valuation following a credit event (such as default), digital CDS simply specify payment of a fixed dollar payoff. At inception of the CDS, the payoff amount is agreed based on the severity of the default event. Remember that in a standard CDS the payoff is equal to the notional amount of the CDS minus the postdefault value of the insured assets.  

Digital CDSs have several advantages. They have lower costs, more precise focus on the credit risk, and greater transparency. They will not be subject to difficulties associated with the auctioning process after a default event.  

Essentially, the digital CDSs eliminate the random recovery rates associated with the conven-. tional CDS. In fact, recent events suggest the possibility that the recovery rates associated with CDSs and synthetic CDOs have higher volatility than do recovery rates implied by corporate bond defaults. This led credit derivatives arrangers to offer a range of structural features to. lessen this variability. One approach is a fixed recovery rate that is applied to all credit events, as in a digital CDS.  

However, CDS can also have disadvantages. There is a potential moral hazard associated with. digital CDS since, in a digital CDS, dealers may have an incentive to more often call soft credit events, events that fall within the ISDA definition of default, but outside that of the rating agencies..  

# 18.4.4 A NOTE ON THE ARBITRAGE EQUALITY  

The simple contractual equation derived earlier suggests that we should have  

$$
\mathrm{cds}_{t_{0}}-s_{t_{0}}=\mathrm{cds}_{t_{0}}
$$  

under ideal conditions.  

Yet, in reality, even when bonds are selling close to par, we in general observe  

$$
c_{t_{0}}-s_{t_{0}}<\mathrm{cds}_{t_{0}}
$$  

Under these conditions instead of buying credit protection on the issuer, the client would simply. short the bond and get in a receiver swap. This will provide the same protection against default,. and, at the same time, cost less. So why would clients buy CDS instead? In fact, such inequalities can be caused by many different factors, briefly listed below..  

1. CDS protection is "easy" to buy. On the other hand, it is "costly" to short bonds. One has to first go to the repo market to find such bonds, and repo has the mark-to-market property. With CDS protection, there is no such inconvenience..   
2. Shorting a bond is risky because of the possibility of a short squeeze. If too many players are. short the bond, the position may have to be covered at a much higher price.   
3. Some bonds may be very hard to find when a sudden need for protection arises..   
4. Also, as discussed earlier, a delivery option premium is included in the CDS rate..  

These factors may cause the theoretical hedge to be different from the CDS sold to clients.. Finally, it should be noted that when the probability of default becomes significant CDS dealers may suddenly move their prices out and stop trading. In more precise terms, the market moves from trading default toward trading the recovery. This is done by quoting the implied upfronts (UPF) instead of spreads.  
