---
tags:
  - cdx_index
  - credit_derivatives
  - credit_spreads
  - index_roll
  - itraxx_index
aliases:
  - CDX roll
  - iTraxx roll
key_concepts:
  - CPDO and roll
  - Credit index strategies
  - Index roll mechanics
  - Off-the-run index
  - On-the-run index
---

# 21.8 THE ROLL AND THE IMPLICATIONS  

Every 6 months, on March and September 2Oth, the iTraxx and CDX indices roll and a new series starts trading. Some credit names may have defaulted, changed sector, merged, or been downgraded. Other CDSs may have become less liquid. These are considered as no longer eligible to be part of the index. Every such name is replaced by the next most liquid name available in its class. The "old series" continue to trade as long as there are open positions, but they are off-the-run. The new roll will be the on-the-run liquid index.  

The Roll is an important characteristic of the indices from a financial engineering point of view. since its presence leads to several strategies and complications that a financial engineer must be aware of. An obvious strategy is to guess the names that will leave the index and the names that will come in. But this happens in index revisions in the equity sector as well. Credit rolls have some novel additional strategies. Note that dropping lower-rated issuers from the index and repla-. cing them with higher-rated ones normally means that the new index should start trading at a narrower spread than the old index, everything else being the same. But, surprisingly, this may not. happen, as we will see below.  

There is some empirical evidence that because the buyers of protection2o would like to stay with the new, on-the-run index due to its liquidity, right before the new series, they will close their positions. This means they will sell protection and this will lower the spreads. Of course, as the new index starts trading, the same names will buy protection and this will widen the spreads..  

There are also structured credit products that are partially based on the fact that the index will roll every 6 months. The constant proportion debt obligation (CPDO) is one good example. During a 6-month period, everything else being the same, a 5-year maturity iTraxx index will become a 4.5-year maturity index. This means that the index will roll down the curve and, if the curve is upward sloping spreads will tighten automatically. This is due to the shorter maturity and nothing else.  

Another classic technical roll is the change in the basis. This is the difference between the index spread and the intrinsic value of the underlying CDSs of the referenced names in the index. The basis exists because normally there are more clients that buy protection than sell them.21 In past. rolls, the basis between the underlying CDSs and the index has narrowed significantly. This hap-. pens because more investors are selling protection than buying protection in order to move to the. new, more liquid index. The example below summarizes the mechanics of the roll..  

# EXAMPLE  

New York (Dow Jones)-As summer draws to a close, credit derivatives investors are eye-.   
ing September's changeover in the credit default swap indexes for trading opportunities..   
This time around though, trading patterns surrounding the change in the indexes' composi-.   
tion could differ from past ones as more issuers than ever before-a total of eight-will be dropping out of the investment-grade index family..  

Credit default swaps allow investors to protect their holdings should issuers default on. their debt. Since the inception of the credit default swap indexes-liquid benchmarks that. allow investors to take positions on corporate debt issuers without having to buy or sell the. underlying, often illiquid cash instruments-there have been [nine rolls until March 2008] which take place every six months.  

At each roll date, issuers who have lost their investment-grade ranking by either Moody's Investors Service or Standard & Poor's are dropped from the Dow Jones CDX investmentgrade credit default swap index and replaced by other issuers-chosen by a poll of the dealers who belong to the index consortium. At the first index roll, six issuers were replaced, at the second five and at the last roll in March 2006, just three issuers were dropped.  

It is important to understand that at each roll the newly introduced series will have a new cou-. pon and will be trading near par initially. The traders who buy and sell index protection are in fact buying and selling this newly introduced standardized contract..  

# 21.8.1 ROLL AND DEFAULT RISK  

Default risk in the indices is somewhat different than it looks at the outset due to the existence of the roll. In fact, at each roll the credit quality of the indices improves. In general, before a company. defaults, its credit quality deteriorates. By the time the company is about to default, it is quite likely. that it was dropped from the index during some previous roll. This brings up an important distinction. A 5-year position that stays with the same index will face the default risk of the underlying. reference names, and these names will remain the same during 5 years. Some of these names will deteriorate and some may even default. This is what is meant by default risk..  

A position that always rolls to the new index faces a somewhat different default risk. The main default risk faced by such a position is when default occurs all of a sudden, without any indications. In this case a good corporation may go from a rating of AA to default, without the rating agencies having time to downgrade it, and before the roll date arrives. This is called jump to default risk. Note that its probability is significantly lower than staying with the same names during the 5 years and then seeing some of them default.  

# ?1.9 REGULATION, CREDIT RISK MANAGEMENT, AND TRANCHE PRICING  

This section discusses the relationship between tranche pricing and credit risk management. Basel III is the framework associated with current credit risk management practices and indirectly it has a close relationship with tranche pricing.22  

# 21.9.1 CREDIT RISK MANAGEMENT, DEFAULT LOSSES, AND MARK-TO-MARKET LOSSES  

Suppose we would like to adapt a Value at Risk (VaR)-type (or Expected Shortfall) risk management approach to portfolios with credit risk.23 This means that we would like to set enough capital to cover losses $0<\alpha$ percent of the time. It turns out that there are two quite different empirical loss distributions that determine the calculation of possible losses.  

In this setting, in order to calculate possible losses due to default, one first needs to obtain a distribution for this random variable. $L$ This is the default loss distribution and is illustrated again in. Figure 21.10. Using this distribution one can calculate the expected default loss and the threshold $L_{\alpha}$ which determines the extreme losses that occur with a probability of (at most) $\alpha$ , during the interval with length $T.$  

The bank would then put aside enough capital to cover default losses up to the point $L_{\alpha}$ .These have a probability $1-\alpha$ of occurring. Default losses may be greater than $L_{\alpha}$ only in $\alpha$ percent of the time. The bank is not obligated to cover these more extreme losses with additional capital.  

But this is only one way of looking at credit risk. It involves the risk associated with the default. events only. This way of managing risks is perhaps appropriate if the instruments under consideration are held until maturity and if the mark-to-market is not relevant..  

On the other hand, if the portfolio under consideration is a trading portfolio where marking-tomarket is important or if the instruments may not be held until maturity, then the bank or the hedge fund faces another risk.24 This risk comes from credit quality changes, which incidentally also.  

involves defaults. If credit deteriorates and needs to be sold or marked-to-market, then the bank or the hedge fund will still suffer credit losses although no default has occurred. The default loss dis-. tribution cannot take such potential losses into account, because it is only directed toward measur-. ing loss due to default. The loss due to credit quality changes requires an additional effort. The. change in the market value of the portfolio due to credit quality changes can be calculated in a way similar to that of market risk.  

The calculation of the default loss distribution requires the default probabilities for each name. and the default correlations. The calculation of the credit return distribution on the other hand requires, in addition, the conditional transition probabilities concerning the rating migrations of. each name in the portfolio as well as their correlations. Hence the calculation of this second distri-. bution is much more involved. Note that default is only one of the states where credits can migrate.. Hence default risk is included in the credit loss distributions due to credit deterioration..  

# 21.9.2 CAPITAL REQUIREMENTS AND CDO ACTIVITY  

As we saw at the beginning of this chapter, securitization activity has dropped significantly since pre-GFC levels. One of the reasons why securitization and CDO activity was so high before the. GFC was that it represented a way for banks to reduce regulatory capital. As with many previous. booms, this led to excesses and abuses. However, securitization activity continues and even under. the current more stringent capital requirements banks find it possible to reduce capital requirements as the following example indicates:  

# EXAMPLE  

In one example Chenavari provides to investors, a $\$1$ billion portfolio of small business loans has a risk-. weighting of $75\%$ under Basel III's standardised approach, generating a risk-weighted asset (RWA) total of $\$750$ million. That implies a bank would need around. $\$75$ million of equity capital to support it. Securitising. the pool and transferring the $I.5{-}8\%$ second-loss tranche-representing $\$65$ million of exposure-to a third party, while retaining the first loss and senior tranches, could bring a bank's capital requirement down to around $\$30$ million, a $60\%$ saving. The bank also gets to keep the loans on its balance sheet and maintain its client relationships.  

Fery refuses to mention counterparty names, but describes some deals he says are representative of the business the fund engages in. One involves a 1 billion portfolio of around 1,500 loans to German small and medium-sized enterprises (SMEs). The pool had a weighted average credit rating of $B B+$ and an average duration of two-and-a-half years. More than half the loans were investment-grade. Chenavari had a positive view of Germany's Mittelstand sector-the legion of mostly family-owned small businesses that power the country's export machine--so agreed to absorb the second loss on the pool via a 65 million note referencing the $I.5{-}8\%$ tranche of the loan portfolio, paying. $13.5\%$ over three-month Euribor per annum. The bank retained the first loss exposure and the entire senior tranche.  

The firm cut a similar deal with a UK bank that was seeking regulatory capital relief on a 1 billion. portfolio of residential mortgage loans. The pool comprised nearly 8,000 loans originated before 2007, and included a large portion of interest-only and buy-to-let mortgages. This time, Chenavari acquired an eightyear note referencing the $2-8.5\%$ second-loss tranche, paying a coupon of. $12.5\%$ over three-month LIBOR. Fery and his team have structured a host of similar deals involving different types of underlying assets-. everything from emerging market corporate loans and European mortgages to asset-backed securities, trade. finance assets and derivatives counterparty risk. The average deal size is around \$80 million, with estimated returns in the $10{-}20\%$ range, he says.  

# 21.9.3 LESSONS FROM THE GFC, POST-GFC CAPITAL REGULATION AND THE SECURITIZATION MARKET  

Securitization and the issuance of CDOs was so actively pursued by banks since it allowed banks to remove loans from their balance sheets and thus improve their capital ratio. Commercial banks must have sufficient capital to cover potential depositors' withdrawals. The ability to lend is affected by capital requirements and if a bank does not have enough capital it cannot lend further unless it finds a way to remove the assets from its balance sheet. As we saw, CDOs are a form of securitization. Many of the junior CDO tranches issued by banks were backed by risky (subprime) loans. Investigations following the GFC revealed malpractice in the loan origination process which saw loans approved without proper vetting of borrowers and the violation of proper procedures. As a result many of the CDOs that were sold to investors were very risky but this did not become apparent to most investors until the US housing market boom slowed in 2006. It is estimated that of the $\$500$ billion worth of CDOs outstanding at that point, about $50\%$ were based on MBSs and around $75\%$ of these contained subprime loans. Driven by the prospect of commissions, risky loan origination and CDO issuance continued nevertheless. As selling these increasingly risky assets became more difficult traders found ways to make the banks hold some of the riskier tranches of the CDOs in order to facilitate sales, achieve favorable credit ratings for the securities, and pay traders commissions. One of the factors that exacerbated the GFC was the prevalence of ratings arbitrage which involved pooling low-rated tranches to create CDOs. All these factors not only perpetuated the excesses but also made the eventual correction more painful as banks themselves were saddled with large losses and the financial system was crippled until banks were bailed out, wound down, or recapitalized. Housing bubbles occur regularly around the world, but the one preceding the GFC was exacerbated by abuses of securitization and misaligned interests.  

In December 2013, the Basel Committee on Banking Supervision issued a second consultative document regarding revisions to the existing securitization framework which was found to be deficient. According to the Basle Committee, the GFC revealed a number of shortcomings in the current securitization framework which it seeks to address with the latest changes. First, practices in the run-up to the GFC showed an almost mechanistic reliance on external credit ratings. Second, there was a tendency to assign too low risk weights for highly rated securitization exposures. The reason for this was that the calibration assumptions typically used turned out to be questionable and there was a lack of sufficient risk drivers across approaches in determining risk weights. Third, risk weights for low-rated senior securization positions were found to be too high. Fourth, the securitization framework leads to undesirably procyclical economic dynamics or cliff effects.  

Vis-a-vis initial post-GFC proposals by the committee the document suggests lower capital requirements but these are still more stringent than existing capital requirements. Thus, if the future Basel Committee securitization framework was based on the latest proposal this leaves the possibility. that the securitization and CDO market would continue to be an important part of financial markets..  

# 21.9.4 CAN SECURITIZATION CURE CANCER?  

In this chapter, we discussed the economic rationale for securitization. We have seen that securitization and financial engineering can play a useful economic role if correctly implemented. As in all areas of economic activity regulation exists and is required to ensure that all market participants act legally and responsibly. Financial engineering concepts have, however, also applications outside finance and may provide not just economic benefits but other social welfare improvements. In recent work, Fagnan et al. (2013) pose the question of whether financial engineering can cure. cancer, a leading cause of death in many industrialized countries. The authors observe that investment in the pharmaceutical industry has declined in recent years and make proposals on how securitization can help increase investment including key important cancer research. The authors hypothesize that one of the reasons for low private sector investment is the skewed distribution of drug trials. The authors provide a stylized example that assumes a hypothetical drug-development programme that requires $\$200$ million development costs in present value terms, a 10-year development period during which no revenues are generated and which has a $5\%$ chance of successful drug approval at the end of 10 years. If one assumes that such a programme generates $\$2$ billion in annual revenues in the subsequent 10 years (i.e. years 11-20), many investors could be expected to. be scared off by the return standard deviation of. $423\%$  

One proposed solution to this problem is to create a fund that pools various drug-development programmes and securitizes the resulting revenue streams. The proposed name for the structured securities that give ownership interest to experimental drug compounds is research backed obligations or RBOs. Fagnan et al. (2013) suggest how techniques that were used in the creation of. CDOs and ABSs can be used to provide guarantees and alter the capital structure of these securities in such a way that they represent an attractive investment opportunity for investors. To date no. such RBO has been issued but the research shows that financial engineering techniques, if appropriately applied, may potentially have wider implications and social benefits beyond the narrowly defined domain of financial markets.  

# 21.1O NEW INDEX MARKETS  

The credit sector plays an important role in financial markets for several reasons. One of these is the methodical way new sectors are introduced by the major players. Markets are normally created endogenously with the interaction of thousands of traders, market makers, and risk managers. In the credit sector, this effort has been consciously directed by broker-dealers and has come after years of experience in new derivatives markets and trading strategies. As a result, broker-dealers. have been quite successful in creating platforms for trading new risks and offering broad numbers.  

of instruments for hedging a range of credit risk exposures. The Markit website provides an overview of a wide range of indices including iTraxx, CDX, ABX, and LCDX..  

The ABX and LCDX indices are the most prominent of the new tradeable indices that permit. trading of new risks. The ABX index is a carefully constituted index that permits trading and hedg-. ing of mortgage debt exposures. A player who is short mortgage debt will hedge this position by buying the ABX index. The LCDX is similar to the iTraxx or CDX, except that the underlying. securities are loans instead of being bonds. Hence, this index helps hedging loan exposures. Levx is similar. It is an index of leveraged loans..  

A player who is long will hedge the position by selling the index. These indices are traded in the form of series and offer a fixed coupon at each roll..  

# 21.1O.1 THE ABX INDEX  

The ABX index is made of obligations issued by 20 issuers of residential MBSs. Altogether there are five subindices. These subindices are each made of one security from each one of these issuers. These securities and hence the subindices have ratings that range from AAA to BBB - . Similar to the roll in the iTraxx and CDX indices, the new series of ABX indices roll on January 19 and July 19. Each series has a new set of mortgage loans behind it. Thus, unlike the iTraxx and CDX index, the ABX indices have "vintages."  

The securities included in the index are essentially debt securities entitling the investors to. receive cash flows that depend on residential mortgages of one-to-four family residences. Hence variations in these cash flows, defaults, and delinquencies affect the value of the ABX indices. An investor in the ABX indices will receive (pay) a fixed coupon set at the roll date. and will make floating payments (receipts) if there is an interest or principal shortfall in the. cash flows.  

# 21.1O.2 THE LCDS, LCDX  

The so-called LCDS (Loan Credit Default Swaps) contracts and their corresponding index LCDX are relatively new tools in the credit sector. Besides being important tools they provide a good opportunity to summarize the Credit indexing technology from a somewhat different angle. LCDS is similar to the single-name CDS that we saw in Chapter 18. In a CDS, the deliverable debts are bonds. With LCDS the deliverable is syndicated secured debt in the United States that was originally issued by a syndicate. LCDX is the corresponding tradeable index and it is similar to the iTraxx and CDX indices. The underlying for the LCDX is $n=100$ equally weighted single-name LCDS. The loans in question trade in the secondary leveraged loan market. The index launches with a fixed coupon, paid quarterly. The index trades on a clean price basis. If the price goes down, the corresponding spread goes up.  

The protection seller will receive a coupon fixed at the roll date and will make a compensating. payment during a credit event. Also during a credit event the protection seller pays the notional amount $N$ and gains possession of the loan. Cash settlement is also permitted. The amount of this cash settlement will be determined in an auction..  

# 21.10.2.1 Cancelability  

An issuer can repay the debt and may not issue new debt afterward. If there is no deliverable obligation then the LCDS cannot continue. Thus LCDS contracts are cancelable unlike the standard CDS. An issuer may be upgraded. When this occurs, the issuer can repay the original debt and issue new debt with lower interest cost.  

A loan repayment starts a 30 business day period, and during the entity can initiate a new. loan. If after 30 days no new loans are made, the name is removed from the index after a dealer VOte.  

This cancelability affects the valuation. If the LCDS is cancelable upon repayment of debt, then the final maturity for a given LCDS will be unknown. The calculation of the present values should then take into account the probability that the loan will be repaid early. This is similar to the use of the credit-risky DV01.  

# 21.10.2.2 Quoting conventions  

The iTraxx and CDS index families are quoted on a spread basis, except for the equity tranche which is quoted with an upfront.25  

On the other hand, the LCDX and ABX indices are quoted on a price basis and this forms another difference.  
