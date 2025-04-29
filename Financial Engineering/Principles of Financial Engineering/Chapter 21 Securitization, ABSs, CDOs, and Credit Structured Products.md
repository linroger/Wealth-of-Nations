# SECURITIZATION, ABSs, CDOs, AND CREDIT STRUCTURED PRODUCTS  

# 21  

# CHAPTER OUTLINE  

21.1 Introduction . 740   
21.2 Financial Engineering of Securitization . .. 740   
21.2.1 Choosing Cash Flows . 741   
21.2.2 The Critical Step: Securing the Cash Flow . 742   
21.2.3 Some Comparisons .. 743   
21.2.3.1 Loan sales.. 743   
21.2.3.2 Secured lending . 744   
21.3 ABSs Versus CDOs... .. 745   
21.3.1 Tranches and Some Securitization History . 746   
21.3.2 A Comparison of ABSs and CDOs.. . 747   
21.3.2.1 Credit indices . 748   
21.3.2.2 Synthetic CDOs . . 748   
21.4 A Setup for Credit Indices.... . 750   
21.5 Index Arbitrage . 754   
21.5.1 Real-World Complications . 754   
21.5.2 Credit Skew Trade.. 755   
21.6 Tranches: Standard and Bespoke . . 756   
21.7 Tranche Modeling and Pricing . . 757   
21.7.1 A Mechanical View of the Tranches 758   
21.7.2 Tranche Values and the Default Distribution... . 759   
21.8 The Roll and the Implications . . 762   
21.8.1 Roll and Default Risk.. 763   
21.9 Regulation, Credit Risk Management, and Tranche Pricing . .. 764   
21.9.1 Credit Risk Management, Default Losses, and Mark-to-Market Losses . . 764   
21.9.2 Capital Requirements and CDO Activity.. . 765   
21.9.3 Lessons from the GFC, Post-GFC Capital Regulation and the Securitization Market .. 766   
21.9.4 Can Securitization Cure Cancer? 767   
21.10 New Index Markets . .. 767   
21.10.1 The ABX Index . . 768   
21.10.2 The LCDS, LCDX . 768   
21.10.2.1 Cancelability. 769   
21.10.2.2 Quoting conventions .. 769   
1 Structured Credit Products... 769   
21.11.1 Credit Options. 769   
21.11.2 Forward Start CDOs . 770   
21.11.3 The CMDS .. 770   
21.11.4 Leveraged Super Senior Notes .. 772   
21.11.5 CoCos.. 773   
21.11.5.1 Cocos versus convertible bonds .. 773   
21.11.5.2 Valuation of CoCos. 774   
21.11.5.3 The outlook for CoCos.. 775   
21.12 Conclusions.. 776   
Suggested Reading . . 776   
Exercises .. 777  

MATLAB Exercise . 780  

# 21.1 INTRODUCTION  

In this chapter, we introduce securitization, asset-backed securities (ABSs) and the modeling of collateralized debt obligations (CDOs) as well as other credit structured products. We explain the economic drivers of securitization, potential for misaligned interests, and the role of securitization in the run-up to the GFC. The securitization and CDO market has rebounded in recent years and we offer an outlook for these markets based on recent regulatory developments. The chapter also deals with credit indices, their implications in creating tranched securities.  

Tranching a basket of credit-risky instruments makes the trading and pricing of credit correlation possible. Once we learn how to strip correlation from tranched products we can price it and then trade it. The issues are discussed within credit default context, but the techniques themselves are very general and buying and selling correlation is routinely applied in creating equity and FX-based structured products as well as we saw in earlier chapters. Yet, in this chapter we focus on default correlation and discuss the issue using the credit names included in the iTraxx or, alternatively, CDX indices.  

The chapter also discusses more recent credit indices ABX and LCDX and credit structured products. Finally, we discuss one post-GFC financial innovation in the form of contingent convertibles (CoCos). CoCos are a hybrid product and we explain how valuation approaches from earlier chapters can be applied to the valuation of CoCos.  

# 21.2 FINANCIAL ENGINEERING OF SECURITIZATION  

Every business or financial institution is associated with a “credit” or, more precisely, a credit rating. If this entity issues a debt instrument to secure funding, then the resulting bonds, in general, have the same credit rating as the company. Yet, a company can also be interpreted as the receiver of future cash flows with different credit ratings. The value and the credit rating of the company will be a function of these future cash flows. Not all the receivables will have the same rating. For example, some cash flows may be owed by institutions with a dubious credit record, and these cash flows may not be received in the case of default or delinquency. Other cash flows may be liabilities of highly reputable companies, may carry a low probability of default, and may indeed be received with very high probability.  

A debt issue will be backed by an average of these credits, since it is the average receivable cash flows that determine the probability that the bonds will be repaid at maturity. If the receivables of a company carry mostly a relatively high probability of default, then the company may experience difficulties in the future and, hence, may end up defaulting on the loan. Alternatively, the credit spread on the bond will increase and the investors will be subject to mark-to-market losses. All these possibilities reflect on the debt issued by this company and are factors in the determination of the proper cost of funding.  

On the other hand, instead of issuing debt on the back of the average cash flows to be received in the future, the company can issue special types of bonds that are backed only by the higher rated portion of the receivables. Clearly, such receivables have a comparatively lower probability of default, and this makes the bonds carry a lower default probability. The funding cost will decrease significantly. The company has thus securitized a certain portion of the cash flows that are to be received in the future. In other words, securitization can be regarded as a way to issue debt and raise funds that have a higher rating than that of the company. It is also a way of repackaging various cash flows.  

What are the critical aspects of such financial engineering? Essentially, various cash flows are to be analyzed and a proper selection is made so as to obtain an optimal basket. This is then sold to investors through special types of bonds.  

Yet, besides the financial engineering aspects, securitization involves (i) legal issues, (ii) balance sheet considerations, and (iii) tax considerations. Securitization is a way of funding an operation. Instead of selling bonds or securing bank lines, the company issues ABSs. The option of securitization helps corporations and banks make decisions among the various funding alternatives.  

# 21.2.1 CHOOSING CASH FLOWS  

Consider Figure 21.1. Here, we show a bank that expects three different (random) cash flows in the future. The institutions that are supposed to pay these cash flows have different credit ratings. For example, the first series of cash flows, rated BBB, may represent credit card payments. The third could represent the random cash flows due to mortgages made in the past. Arguably, people pay better attention to the timely payment of mortgages than they do to the timely payments of unsecured credit card proceeds. Credit card defaults are much more common and plausible than mortgage delinquencies. Thus, the mortgage cash flows will be rated higher, say, with an A rating as shown in the figure.  

Now, if the company is set to receive these three cash flows only, assuming similar liabilities, the company’s average rating will perhaps be around $\mathrm{BBB^{+}}$ . A corporate bond issued by the company will carry a $\mathrm{BBB^{+}}$ credit spread.  

Consider two different ways of packaging the same cash flows. If the company “sells” cash flow 3 and backs a bond issue with this cash flow only, the probability of default will be much  

![](b9283bdfce36350bb2686886712169f1219a812779829b4c43c29d86aeb833fc.jpg)  

# FIGURE 21.1  

Cash flow characteristics of three risky cash flows.  

lower and funding can be secured at a lower rate. A bond backed by cash flows 1 and 2 will have a lower credit rating than a bond based on cash flow 3, but depending on the diversification benefits of combining different cash flows and the attractiveness of offering a bigger pool of receivables in this second option, it may make sense for a company to combine cash flows 1 and 2 instead of selling separate bonds based on them.  

Early examples of securitization can be found as far back as the eighteenth century but the first modern residential mortgage backed security (MBS) was created in 1970 by the U.S. Department of Housing and Urban Development. During the 1990s, banks moved into securitization of a wider range of assets and more complex structures. Loans from credit cards, mortgages, equity, and cars were packaged and sold to investors. A typical strategy was to (i) buy the loan from an originator, (ii) warehouse it in the bank while the cash flows stabilized and their credit quality was established, (iii) hedge the credit exposure during this warehousing period, and (iv) finally sell the loan to the investor in the form of ABS.  

# 21.2.2 THE CRITICAL STEP: SECURING THE CASH FLOW  

The idea of securitization is quite simple. Instead of borrowing against the average quality of the company’s receivables, which is what happens if the company sells a straight corporate bond, the entity decides to borrow against a higher-quality subset of the receivables. In case of default, these receivables have a higher chance of being collected (recovered) and, hence, the cost of these funds will be lower.  

But there is a critical step. How can the buyer of an ABS make sure that the receivables that are supposed to back the security are not used by the company for other purposes, and that, in the case of bankruptcy, these receivables will be there to cover losses?  

The question is relevant, since after issuing the ABS security, it is still the original company that handles the business of processing new receivables (e.g., by issuing new mortgages), as well as the receipts of cash generated by such cash flows, and then uses them in the daily business of the firm. Clearly, there must be an additional mechanism that guarantees, at least partially, that these cash flows will be there in case of default.  

A bankruptcy remote SPV (special-purpose vehicle) is one such mechanism used quite often to resolve such problems in practice. The idea is as follows. (i) The issuing company forms a SPV, which is a shell company, often independent of the parent company, and whose sole purpose is to act as a vehicle in structuring the ABS. (ii) Steps are taken to make the SPV bankruptcy remote. That is to say, the probability that the SPV itself defaults is zero (since it does not engage in any meaningful economic activity other than that of issuing the paper), and in case the original company goes bankrupt, the underlying cash flows remain in the hands of the SPV. (iii) The issuing company draws all the necessary papers so that, at least from a legal point of view, the cash flows are sold to the SPV. This is a true sale at law.  

The idea is to transfer the right to these cash flows and guarantee them under the ABS as much as possible. In fact, several SPVs with different purposes can be layered to make sure that the ABS has the desired characteristics.  

1. An SPV may be needed for tax reasons.   
2. Another SPV may be needed for balance sheet reasons.   
3. Still another SPV may be needed to comply with other regulations.  

Hence, one possible structure can be layered as shown in Figure 21.2. Note that here, the first SPV is a subsidiary of the company, so the company can “buy” the cash flows, and this is the reason for its existence. But if the SPVs keep the cash flows, these will still be on the balance sheet of the original company.  

Finally, note the role played by the investment bank. The first three layers make up the ABS structure, and the investment bank still has to handle the original sale of the ABS. The structure clearly shows that the ABS has three important purposes, namely lowering the funding cost, managing the balance sheet, and handling tax and accounting restrictions.  

# 21.2.3 SOME COMPARISONS  

The first use of securitization concerns funding costs, as already discussed. Securitization is a form of funding. But we must add that it is also an unconstrained form of funding, and an off-balancesheet form of liquidity for small and medium-sized companies. Finally, it is a diversified funding source. This way it can lower leverage. Securitization also implies less public disclosure.  

Securitization is neither secured corporate financing, nor the sale of an asset. It is a hybrid, a combination of both that uses the well-accepted legal, regulatory, tax, and accounting concepts that already exist.  

# 21.2.3.1 Loan sales  

We should also compare whole loan sales versus securitization. Securitization is on a serviceretained basis, whereas a loan sale is service released. The buyer of the loan would like to service  

![](37b9d6cc80257ff3d634debd7b3aeff67b921d916d31af7e9ccb75ac169dd595.jpg)  

# FIGURE 21.2  

Securitization structure.  

the loan himself or herself. Another point is the retention of credit and prepayment risk. In a loan sale, $100\%$ of these risks are transferred. With securitization, some of these risks may be retained. A loan sale is also often done at a premium, whereas securitization issues are often around par.  

In addition, there is a timing issue. In securitization, cash flows from assets are often invested in short-term investments and then transferred to the bond holders. Thus, the investor receives the payments later than the servicer. Finally, securitization sometimes uses credit enhancements, and this makes the paper somewhat more liquid.  

# 21.2.3.2 Secured lending  

Securitization is similar to secured financing, with one important difference. In an ABS, the issuing company is not liable for its ABSs. It is as if the company has not really “borrowed” the funds. A separate legal entity needs to be established to do the borrowing. Securitization is structured so that this entity becomes the legal owner of the asset. If the company defaults, the cash flows will not belong to the company, but to the SPV. This way the owners of the bonds have an ownership interest in the case of securitization, whereas in the case of secured lending, they only have a security interest.  

# 21.3 ABSs VERSUS CDOs  

This chapter introduces financial engineering applications that relate to ABSs and securitization. It turns out that securitization and hybrid asset creation are similar procedures with different objectives. From the issuer’s point of view, one is a solution to balance sheet problems and it helps to reduce funding costs. From an investor’s point of view, securitization gives access to payoffs the investor had no access to before and provides opportunities for better diversification. Hybrid assets, on the other hand, can be regarded as complex, ready-made portfolios.  

A financial engineer needs to know how to construct an ABS. In fact, engineering is implicit in this asset class. The remaining tasks of pricing and risk managing are straightforward. A similar statement can be made about hybrid assets.  

This book cannot deal with the technical issues concerning ABSs and CDOs. Still, credit indices should be put in context so that they can be compared to ABSs and CDOs. This is also a good opportunity to introduce the basic definitions of and the differences between the ABS- and CDOtype securities. A CDO is a security whose value is backed or collateralized by a pool of underlying fixed-income assets. The CDO pays a return which is based on payments from the performance of this pool of assets.  

Imagine three different classes of defaultable securities. The first class is defaultable bonds. Except for U.S. Treasury bonds, all existing bonds are defaultable and fall into this category. The second class can be defined as “loans.” There are several types of loans, but for our purposes here, we consider just the secured loans extended to businesses. Finally, there are loans extended to households, the most important of which are mortgages.  

ABS securities can be defined by either using other assets such as loans, bonds, or mortgages, or more commonly using the stream of cash flows generated by various assets such as credit cards or student or equity loans. In this section, we consider the first kind. Figure 21.3 displays the way we can structure an ABS security. A basket of debt securities is divided into subclasses with different ratings, then the subclasses are placed “behind” different classes of the ABS security. This means that any cash flows or the corresponding shortfalls from the original debt instruments would be passed on to the investor who buys that particular class of ABS security. In contrast, if there are defaults, the investors receive an accordingly lower coupon or may even lose their principal. Note that according to Figure 21.3, classes of ABS securities have different ratings because they are backed by different debt instruments. Often in an ABS, the credit pool is made of loans such as credit cards, auto loans, home equity loans, and other similar consumer-related borrowing. When the underlying instrument is a mortgage, the ABS is called an MBS, which we examined in detail in Chapter 17. In each case, the rating of the ABS is determined by the rating of the loans that back it.2  

Figure 21.4 shows a “cash” CDO, also called a funded CDO. Again a pool of credit instruments are selected. But they are classified in a very different way. The CDO classes called tranches are formed, not by classifying the underlying securities, but the risk in them. In fact, all CDO tranches will be backed by the same pool of securities. What distinguishes the tranches is the subordination of the default risk. The ABS categorizes the securities themselves. A CDO categorizes the priority  

![](acc205089a4e38a937325f485247c05a1efd6bc8c4b50a967c1175890b536d29.jpg)  

# FIGURE 21.3  

ABS structure.  

![](bb6c6212998ea1f3524bcfa1b1790c844900cf6668d32e55b2aa1dc3314a5650.jpg)  

Note that these are cash bonds backing the CDO.  

# FIGURE 21.4  

Cash CDO.  

of payments during defaults. The first few defaults will be the first tranche, then if defaults continue the next tranche will suffer and so on.  

# 21.3.1 TRANCHES AND SOME SECURITIZATION HISTORY  

In the 1990s, the securitization process that started with ABS was then extended to CDOs, collateralized loan obligations (CLOs), and their variants. In packaging bonds, mortgages, loans, and ABS securities into CDO-type instruments, banks went through the following practice. The banks decided to keep the first loss piece called the equity tranche. For example, the bank took responsibility for the first, say, $3\%$ of the defaults during the CDO maturity. This introduced some subordination to the securities sold. The responsibility for the next tranche, the mezzanine took the risk of the defaults between, say, $3\%$ and $6\%$ of the defaults in the underlying portfolio. This was less risky than the equity tranche and the paper could be rated, say, BBB. Institutional investors who are prevented by law to invest in speculative grade securities could then buy the mezzanine tranche and, indirectly, the underlying loans even if the underlying debt was speculative grade. Consider the following illustrative example. Take 100 bonds all rated B. This is a fairly speculative rating and many institutions by law are not allowed to hold such bonds. Yet, suppose we sell the risk of the first $10\%$ of the defaults to some hedge fund, at which time the default risk on the remaining bonds may in fact become A. Institutional investors can then buy this risk. Hence, credit enhancement made it possible to sell paper that originally was very risky.  

Then, the very high-quality tranches, called senior and super senior, were also kept on banks’ books because their implied return was too small for many investors. As a result, the banks found themselves long equity tranche and long senior and super senior tranches. They were short the mezzanine tranche which paid a good return and was rated investment grade (IG). It turns out, as we will see in this chapter, that the equity tranche value is positively affected by the default correlation while the super senior tranche value is negatively affected. The sum of these positions formed the correlation books of the banks. Banks had to learn correlation trading, hedging, and pricing as a result.  

As discussed below, the bespoke tranches evolved later into standard tranches on the credit indices. The equity tranche was the first loss piece. A protection seller on the equity tranche bears the risk of the first $0-3\%$ of defaults in standard tranches. The mezzanine tranche bears the second highest risk. A protection seller on the tranche is responsible, by convention, for $3\%$ of the defaults. The $6\mathrm{-}9\%$ tranche is called senior mezzanine. The senior and super senior iTraxx tranches bear the default risk of $9-12\%$ and $12-22\%$ of names, respectively. In this chapter, we study the pricing and the engineering of such tranches.  

If the default risk comes from a pool of bonds, the CDO is called a collateralized bond obligation (CBO). If the underlying securities are loans, then it is called a CLO. The term CDO is more general and the securities it represents may be a mixture of all these. In fact, these underlying securities may include MBS or other ABS securities. Even tranches of other CDOs were sometimes included in a CDO before the GFC.  

# 21.3.2 A COMPARISON OF ABSs AND CDOs  

Consider an investor pays 100 in cash to buy the ABS and the CDO structures shown in Figures 21.3 and 21.4. By buying the ABS or the CDO the investor is, in a sense, buying the underlying securities as a pool. The underlying pool can be arranged so that the investor can choose among classes of ABS securities with different ratings. In the CDO, the priority of interest and principal payments determine the rating of the tranche. Thus different classes of ABS securities (at least as defined here) represent different underlying assets grouped according to their credit rating, whereas the tranches of CDOs are actually backed by the same underlying assets, while having different ratings due to how quickly they will be hit during successive defaults. Figure 21.4 shows that the cash flows in CDOs have a cascading effect between classes. This pattern is therefore often referred to as a cash flow waterfall.  

# 21.3.2.1 Credit indices  

Markets prefer to trade credit risk through standardized and transparent credit indices. We discussed the 2009 standardization of single-name credit default swap (CDS) contracts in Chapter 18. Credit indices are liquid benchmarks that are based on portfolios of reference names or singlename CDS contracts. The corresponding default risks are then repackaged by slicing the portfolio into various standard tranches bearing different risk and return characteristics.3  

The indices allow investors to take a position on the broad corporate credit market with a single trade and provide liquid hedging instruments for institutions to hedge their complex credit exposures. Within the IG corporate credit names, there exist two major CDS index categories in the world: CDX and iTraxx. During the discussion in this chapter, we focus mostly on iTraxx indices.  

The credit indices are constructed by Markit’s subsidiary International Index Company (IIC) after a dealer liquidity poll. Market makers submit a list of names to the IIC based on the following criteria.  

1. The entities have to be incorporated in Europe and have to have the highest CDS trading volume, as measured over the previous 6 months. Traded volumes for entities that fall under the same ticker, but trade separately in the CDS market, are summed to arrive at an overall volume for each ticker. The most liquid entity under the ticker qualifies for index membership.   
2. The list of entities in the index is ranked according to trading volumes. IIC removes any entities rated below BBB (by S&P) and those on negative outlook.   
3. The final portfolio is created using 125 names. It is assembled according to the following classification: 10 Autos, 30 Consumers, 20 Energy, 20 Industrials, 20 TMT, and 25 Financials. Each name is weighted equally in the overall and subindices.4  

The markets prefer to trade mostly the subinvestment grade indices called iTraxx Crossover (XO) in Europe and CDX High Yield (HY) in the United States. These indices see a large majority of the trading, they contain fewer names, and the spreads are significantly higher.5  

# 21.3.2.2 Synthetic CDOs  

A credit index and the associated tranches are a synthetic version of a CDO. The underlying assets are related to the bonds of the reference portfolio names but they are not purchased! Hence, they are unfunded. Thus, with an index and most of the tranches, there is no initial cash payment or receipt involved.6 While a cash CDO pays LIBOR plus some spread, the synthetic (unfunded) CDO pays just the spread because it involves no initial cash payments. In this sense, the relationship between an index (unfunded CDO) and a funded CDO is similar to the relationship between cash bonds versus the CDS written on that name.  

Figure 21.5 shows how the index can be interpreted as a synthetic unfunded CDO. In this figure, the tranches are selected so that they conform to the standard iTraxx tranches. Synthetic CDOs  

A credit index and the implied synthetic CDO.Note that there is no initial cash investment.  

![](fecbeb8eec05e2b76e94f863a67559ff04a76dc2ca6cd7cd6046bd64fa9b27ac.jpg)  

# FIGURE 21.5  

A credit index and the implied synthetic CDO.  

were popular in the run-up to the GFC since they were cheaper and easier to create than traditional CDOs which as we saw were mostly created from mortgages. The following example illustrates recent developments in CDS and CDO markets.  

# EXAMPLE  

The GFC led to a recession that started in December 2007 and ended in June 2009. Default rates following the recession peaked in 2010 according to S&P but subsequently declined to historical lows in 2012. As a result of the fall in defaults the demand for hedging default risk declined and the amount of single-name CDS outstanding fell. According to data from the BIS, at the end of 2012, the notional amount outstanding of single-name CDS was $\$14.3t n$ which represents a $57\%$ decline from its $\$33.4$ tn peak in the first half of 2008. It is important to bear in mind that part of the decline can be attributed to investors compressing or clearing their swaps portfolios but this does not explain the majority of the decline.  

The shrinking of the single-name CDS markets may have been welcomed by some regulators and politicians but it also means that banks and other market participants have fewer hedging tools available. As is clear from Figure 21.5, the creation for synthetic CDOs contributed to the growth of the single-name CDS market before the GFC as CDOs sold credit protection in waves. Demand for CDS protection stemmed from banks that used swaps to offset their loan exposures. At the same time hedge funds were active market participants and “correlation traders” as they arbitraged discrepancies in the prices of CDS or different CDO tranches. The synthetic CDO market is slowly recovering, as Figure 21.6 shows, but under new tougher capital rules banks no longer benefit as much from hedging their loans with CDS. Many remaining correlation traders are now involved in managing legacy synthetic CDOs. Correlation traders were some of the most active users of single-name CDS and with the decline in correlation trading liquidity in the singlename CDS market also shrank. An additional factor that depressed the single-name CDS activity was the EU’s 2012 decision to ban buying naked sovereign CDS protection. One area where activity has been robust has been in the area of CDS on indices as some market participants use them for trading and hedging purposes. Index CDS has been used as hedges against macroeconomic uncertainty and as imperfect hedges against firm specific credit risk.  

![](8cfce123cdb8d8e771538b753de352924bc0cee7bb81dc83558f47d6afecf4e8.jpg)  
Source: Securities Industry and Financial Markets Association (SIFMA)  

# FIGURE 21.6  

Global synthetic CDO issuance.  

As the example above illustrates the single-name CDS and synthetic CDO market have shrunk compared to pre-GFC levels, but the products continue to trade. Figure 21.6 shows that global issuance in the synthetic CDO market has rebounded slightly in 2013 although it remains at $<2\%$ of the pre-GFC annual issuance level. There are reasons to believe that securitization as well as CDO markets will continue to exist. The reason is that following a period of critical evaluation of the role of these markets in the GFC following by regulation, governments realize that securitization and CDOs play an important role in providing funding to the economy. As stricter regulation and capital requirements have seen banks reduce lending, securitization may provide one of the avenues to increase lending to businesses and stimulate the economy. The reading above also highlights the role of correlation trading based on CDOs which we will examine in further detail in the next chapter.  

# 21.4 A SETUP FOR CREDIT INDICES  

We saw in Chapter 18 that a single-name CDS is a contract that provides protection against a default event on the part of a single issuer or reference name. The protection seller pays zero and receives a constant premium if no default event occurs. The CDS premium is $\mathrm{cds}_{t_{0}}$ . If a default event does occur the protection seller pays the difference between the promised (face) value of the underlying issue (100) and the market value of the defaulted bond. The recovery rate is denoted by $R$ . Consider the single-name CDS in Figure 21.7. The maturity $T$ is assumed to be 1 year for simplicity and the notional amount $N$ is 100. The net payment by the protection seller in case of default is $(l-R)l{00}$ .  

A credit index is obtained by selecting $n$ such reference entities indexed by $j=1,...,n.$ . This pool is called the reference portfolio. The associated CDS rates at time $t$ , denoted by $\{\mathrm{cds}_{t}^{j}\}$ are assumed to be arbitrage-free. A tradeable CDS index is formed by putting these names in a single contract, where if $N$ dollars insurance is sold on the index, then this would correspond to a sale of insurance on each name by an amount ${\begin{array}{l}{{\frac{1}{n}}N}\end{array}}$ .  

Let $I_{t}$ represent the spread on the credit index for the preselected $n$ names. The “index” would then trade as a separate security from the underlying single-name CDSs. It should be regarded as a standalone security with a known maturity, coupon, and standardized documentation. Trading the index is equivalent to buying or selling protection on the reference portfolio names with equal weights.7 The spread of this portfolio, i.e., $I_{t}$ , is quoted separately from the underlying CDSs.8  

![](412ad218a5e69e6d116c94c8e15687e8f338c59785f9e843618b7da3cd7acd9d.jpg)  

# FIGURE 21.7  

A single-name CDS.  

At the outset, one may think that $I_{t}$ would (approximately) equal the simple average of the underlying CDSs. This turns out not to be the case, except in exceptional circumstances when all the CDS rates and their volatilities are the same. In general, we will have  

$$
I_{t}\leq\frac{1}{n}\sum_{j=1}\mathrm{cds}_{t}^{j}
$$  

In fact, why should a traded credit index trade as if all credits are weighted equally? It is more reasonable that the pricing of a reference portfolio would weigh the underlying names using their survival probabilities as well as the level of the corresponding CDS rates. In other words, the index spread would be DV01-weighted even though the composition of the index is weighted equally.  

# EXAMPLE  

The index has two names:  

$$
\mathrm{cds}^{1}=20\mathrm{bp}
$$  

$$
\mathrm{cds}^{2}=4500\mathrm{bp}
$$  

reminiscent of the spreads during the credit crisis. The average spread will be:  

$$
{\frac{4500+20}{2}}=2260
$$  

According to these spreads it is much less likely that the first name defaults in the near future compared to the second name. This means that if an investor sold protection with notional $N=50$ on each of the individual CDSs, the average receipt during the next five years is unlikely to be 2260. This is the case since the default of the second name appears to be imminent. Assuming that default occurs immediately after the transaction, the average return of the remaining 50 invested in the first credit would be $20~\mathrm{bp}$ for the next five years.  

On the other hand, if the index traded at $2260\mathrm{bp}$ , the index protection seller will continue to receive this spread on the remaining $\$50$ .  

According to this, the index spread will deviate more from the simple average of the underlying CDS spreads, the more dispersed the latter are. This is due to the DV01 weighing mentioned above.  

Thus, the credit indices are fundamentally different from the better-known equity indices such as S&P500 or Dow. The latter are supposed to equal some average of the price of the underlying stocks, otherwise there would be an (index) arbitrage opportunity. In the credit sector this difference is far from zero and the traders trade this difference if it deviates from a calculated fair value.  

For the sake of presentation, the discussion will continue using the iTraxx IG index as representing the $I_{t}$ . The next example will help to understand the cash flow structure of such an index.  

# EXAMPLE  

Suppose $n=3$ . The underlying names are A, B, and C. We consider a 1-year maturity with settlement in arrears at the end of the year.  

Suppose $N=3$ is invested in this index. All names are equally weighted and all probabilities of default $p^{i}$ are assumed to be the same. This makes the position similar to putting $\$1$ on each name in a reference portfolio of three single-name CDSs. However, as mentioned above, the spread on the portfolio as a whole may deviate significantly from the average of the three independent single-name CDSs.  

Essentially, there will be four possibilities or scenarios at the end of the year. There may be no defaults, one default, two defaults or three defaults at time $t_{1}$ . The structure will be as shown in Figure 21.8.  

On the other hand, if the position was for more than 1 year the default possibilities would be more complicated for the second year. This is discussed later in this chapter.  

![](83d77b03e464ed9cbb406d580dc6f0ef66c0e0d7b57b4e420d2285c7ad0756a7.jpg)  

# FIGURE 21.8  

Index with three names.  

What happens when an entity that belongs to the underlying reference names defaults? Consider the case of the iTraxx index with $n=125$ names. The resulting process for this default is similar to that for a single-name CDS. The protection seller pays to the protection buyer a compensation equal to ${\begin{array}{r}{{\frac{1}{125}}N.}\end{array}}$ In return, the protection buyer delivers deliverable bonds with the same face value.  

After the default, trading will continue in the case of a credit index, albeit with the notional amount reduced by $\textstyle{\frac{1}{n}}N.$ . The index will then have $n-1$ names and any contracts written on it will continue as if the notional amount has become:  

$$
N-{\frac{1}{n}}N={\frac{n-1}{n}}N
$$  

Further defaults would lower this notional in a similar way.  

# 21.5 INDEX ARBITRAGE  

Index arbitrage is well known in equity markets. A stock index is made of a given and known number of stocks. The Index itself can be traded in the futures markets. The carry strategy applies and by buying (short selling) the underlying stocks, one can create a synthetic futures contract which can be used to take arbitrage positions on the stock index.9  

By analogy one can define index arbitrage in credit as positioning in the index itself versus its underlying reference names using the single-name CDSs. In equity markets, this strategy is reasonable. In credit markets, it faces several complications even though theoretically it sounds similar. One issue is the liquidity of single-name CDSs. In an index consisting of 125 names, not all underlying CDSs may be liquid. The bid ask spreads for these individual CDSs may be too wide in many cases and trading the underlying against the index may become too costly.  

# 21.5.1 REAL-WORLD COMPLICATIONS  

There are two major issues that lead to different valuations in the index versus its constituents. The first is the differential treatment of restructuring. The second is a technical issue and deals with the convexity of the index versus the underlying CDSs. Credit index arbitrage is possible, but only after taking into account such divergences explicitly.  

First note that as mentioned in Chapter 18, CDX indices trade with no restructuring. Yet, the CDSs for most of the IG credits treat restructuring as a credit event.10 To correct for this valuation difference, the value of the restructuring risk must be subtracted from the individual CDSs. This value, however, is not observed separately and has to be “estimated.”  

The convexity issue is more technical. Fixed-income instruments have convexity as discussed previously, whereas equity does not. This also differentiates index arbitrage in credit from the index arbitrage in equity. Consider the 5-year CDS with a CDS rate $\mathrm{cds}_{t}^{j}$ bps for the jth name in the reference portfolio. As the underlying CDS rate changes, the market value of the future CDS coupon payments will change nonlinearly since the fixed coupons will be discounted using discount factors that will be a function of survival probabilities.11 According to this, the CDS value would be a nonlinear function of the $\mathrm{cd}\mathrm{s}_{t}^{j}$ , the CDS rate, which leads to convexity gains.  

On the other hand, an investor to the credit index receives a single coupon. The convexity of this cash flow will be different from the convexity of the portfolio of underlying CDSs, since the convexity of the average is different from the simple average of convexities. The effects of convexity and of restructuring should be taken out explicitly in order to come up with a fair value for the index.  

# 21.5.2 CREDIT SKEW TRADE  

We had seen earlier that volumes in single-name CDS trading have declined since the GFC. The following reading illustrates the interaction between regulation related to banks’ capital requirements, index arbitrage activity, and liquidity in the single-name CDS market. Following the GFC capital requirements for banks have increased and this has increased the funding costs for certain trades. The index skew in the credit markets refers to the fair value or market value of the index versus its theoretical value. The skew is the difference between the value of the index using all of the underlying credit names and where the index is actually trading. In general, a positive skew implies that the skew is trading wider than its fair value.  

# EXAMPLE  

Credit index arb trades under threat  

Dealers look to sell legacy books ahead of introduction of leverage rule Dealers are concerned that credit index arbitrage activity could be largely killed off by the coming introduction of a leverage ratio restriction on banks, further draining liquidity from the single-name CDS market as well as punishing banks with large legacy books.  

Arbitraging the difference between CDS indices and their underlying single-name components—often referred to as “skew”—is a favourite trade of market makers and hedge funds.  

But this activity becomes hugely punitive under the proposed leverage ratio rules as they currently stand. Dealers will only be able to net out long and short positions if they match precisely when executed with the same counterparty or if they face a clearing house, effectively ruling out skew trading.  

“Skew is a big problem for the banks, and it could be a big problem for liquidity. Roughly a third of liquidity in investment-grade CDS comes from skew activity. Funds are worried where the liquidity on single names comes from if that goes away,” said the head of European credit trading at a major bank.  

Single-name CDS tend to lag credit spread movements on indices, which are investors’ first port of call to hedge macro exposures. By lining up all the single-name CDS constituents in iTraxx Main versus the index itself, traders can pick up a handful of basis points for ironing out the discrepancy.  

It is a regular trade for sophisticated hedge funds, but dealers print skew packages as well to keep on their own books as a trading position, while also providing liquidity to the market. This type of activity has already become harder to carry off as liquidity in single-name CDS has dwindled since the financial crisis. These days, it is usually necessary to include multiple dealers in a package in order for a trader to line up all of the 125 single-name CDS in iTraxx Main in sufficient size, as banks’ balance sheets have come under increasing pressure.  

Legacy issues  

Many dealers have large legacy skew books sitting on their balance sheets, which look set to get clobbered by the leverage ratio. The current proposals focus on gross notional derivatives exposures and have strict rules about netting down positions. Even though a skew package is market risk neutral—buying the single names versus selling the index—such positions do not net.  

(Thomson Reuters IFR, 10 January 2014, “Credit index arb trades under threat”, by Christopher Whittall)  

The above reading illustrates the importance of index arbitrage or skew trading for single-name CDS liquidity. The liquidity in single-name CDS is driven not only by regulation and capital requirements related to CDS markets but also to CDO and securitized products. The example shows the important role that regulation plays in the application of financial engineering principles and real-world arbitrage strategies.  

# 21.6 TRANCHES: STANDARD AND BESPOKE  

The popularity of the indices is mostly due to the existence of standard index tranches that permit trading credit risk at different levels of subordination. At the present time, default correlation can be traded only by using index tranches. The index itself is used to hedge the sensitivity of tranches to changes in the probability of default.12 We discuss the formal aspects of pricing default correlation in the next chapter. In this section, we introduce standard index tranches and then introduce their relationship to default correlation.  

The equity tranche is the first loss piece. By convention equity tranche bears the highest default risk.13 A protection seller on the standard equity tranche bears the risk of the first $0-3\%$ of defaults on the reference portfolio. The equity tranche spread is quoted in two components. The first, which is quoted by the market maker, is paid upfront. It is for the investor to “keep.” The second is the 500 bps running fee which is paid depending on how much time passes between relevant events.14  

The mezzanine tranche bears the second highest risk. A protection seller on the tranche is responsible, by convention, for $3\mathrm{-}6\%$ of the defaults.15 This tranche is also upfront with a 500 bps spread.  

The senior and super senior iTraxx tranches bear the default risk of $6\mathrm{-}9\%$ and $9-12\%$ of names respectively. The $6\mathrm{-}9\%$ tranche also has a 300 bps fixed spread.  

The numbers such as $0-3\%$ are called the lower and upper attachment points. The ones introduced above are the attachment points for standard tranches. If attachment points are different from those and negotiated individually with the market maker they become bespoke tranches.16 A bespoke trance will not naturally have the same liquidity as a standard tranche.  

The value of the tranches depends on two important factors: The first is the risk of a change in the average probability of default; the second is the change in default correlation. This is a complex and important idea and leads to the market known as correlation trading. It turns out that from a typical bank’s point of view, one of the biggest risks that may lead to bankruptcy is the event of defaults of its clients at the same time. Banks normally make provisions for “expected” defaults. It is part of the business. If individual defaults occur now, then it will not be very harmful. Yet, joint defaults of the borrowers can be fatal. This explains the importance of default correlation for the banking sector. Although most financial crises are characterized by, to most participants, surprising increases in correlations associated with declines in risky assets, it was the unprecedented increase in correlations in many of the underlyings in ABS and CDOs that led to outsized losses in this sector during the GFC. Investor and structures did not consider scenarios with historically unseen correlations.  

In fact, the reference names in a credit index are affected by the same macroeconomic and financial conditions that prevail in an economy (sector) and hence are likely to be quite highly correlated at times, and the level of the correlation would change depending on the prevailing conditions. In an environment where credit conditions are benign and liquidity is ample, default correlation is likely to be low and any defaults occur mostly due to idiosnycratic reasons, that is to say, effects that relate to the defaulting company only, rather than the overall negative economic and financial conditions. During periods of stress this changes, and defaults occur in bunches due to the underlying adverse macroeconomic conditions.  

Thus default correlation is a stochastic process itself. During the last few years, market professionals have learned how to strip, price, hedge, and trade the default correlation. We will study this more formally in the next chapter. Here we note that the value of the equity tranche depends positively on the level of default correlation. The higher the default correlation in the reference portfolio, the higher the value of an investment in the equity tranche, which means that the spread associated with it will be lower.17 On the other hand, the value of the senior and super senior tranches depends negatively on the default correlation. As default correlation increases, the investment in a super senior tranche will become less valuable and its spread will increase. This is called the correlation smile and is discussed in the next chapter.  

# 21.7 TRANCHE MODELING AND PRICING  

Markets trade the indices and the index tranches actively. As a result, the spreads associated with these instruments should be considered to be arbitrage-free. Still, we would like to understand the price formation, and this requires a modeling effort. The market has over the past few years developed a market standard for this purpose. The specifics of this market standard model are discussed in the next chapter. Here we discuss the heuristics of CDO tranche valuation.  

What determines the tranche values is of course the receipts due to spreads and the potential payoffs due to defaults. The general idea is the same as in any swap. The expected value of the properly discounted cash inflows should equal the expected value of the properly discounted cash outflows. The arbitrage-free spread is that number which makes the expected value of the two streams equal. Clearly, in order to accomplish this we need to find a proper probability distribution to work with. We discuss this issue using tranche pricing. Tranche values depend on the probabilities that are associated with the payoffs the tranche protection seller will have to make. These probabilities are the ones associated with the number of defaulting companies during a particular time period and their correlation.  

We limit ourselves to one period tranche contracts on an index with $n=3$ names.  

# 21.7.1 A MECHANICAL VIEW OF THE TRANCHES  

Consider a reference portfolio of $n=3$ names. Call them $A,B,C,$ respectively. Limit the time frame to 1-year maturities. Let $D$ represent, as usual, the total number of defaults in a year. The first step in discussing tranche valuation is to obtain the distribution of $D$ . How many possible values can $D$ have? It is clear that with $n=3$ , there are only four scenarios as shown in Figure 21.9.  

At this moment ignore how such probabilities can be obtained and take them as given. Assume that the probability of default is the same for each name and that the recovery is $R$ . Thus,  

$$
p^{A}=p^{B}=p^{C}=p
$$  

We now show how tranche values depend on this probability and on the correlation between the defaults of the three names. We now assume $p$ to be $5\%$ . According to the figure the probability is quite high that there will be no defaults at all, i.e., $D=0$ . The probability associated with more defaults $D$ then gets smaller.  

Now, consider the equity tranche. We have three names, and the equity tranche is bearing the risk of any first name to default. Mezzanine is the protection for the second name, and senior tranche sells protection on the third name. Hence for a protection seller on the senior tranche to pay, all three names need to default. Suppose a market maker now sells protection on the equity tranche. In other words, the market maker will compensate the counterparty as soon as any one of $A,B,$ , or $C$ defaults. What is the probability of this event? Let $D$ denote the random variable representing the number of defaults. Then the probability that there will be at least one default is given by  

$$
P(D=1)+P(D=2)+P(D=3)=1-P(D=0)
$$  

Going back to Figure 21.9, we see that this probability is $1-0.857375=14.2625\%$ in that particular case. This is much higher than the assumed $5\%$ probability that any name defaults individually. Thus writing insurance on a first-to-default contract is much riskier than writing insurance on a particular name in the reference portfolio.18 This is the risk associated with the equity tranche— the tranche that will get hit first in case of a default.  

An investor may not be willing to take such a risk. He or she may want to write insurance only on the second default. This is the investment in the mezzanine tranche. The tranche has subordination, in the sense that there is a cushion between the defaults and the protection seller’s loss. The first default will hit the equity tranche.  

We can calculate the probability that the mezzanine tranche will lose money as,  

![](61c120096357490ac6009e4d959a73521c0f7c79fe401529cab9371e5046a4d8.jpg)  

# FIGURE 21.9  

Default probability with three names.  

$$
P(D=2)+P(D=3)=0.007125+0.000125=0.725\%
$$  

One can also write protection for the third default. Here there is even more subordination. Before the insurer suffers any losses, three names must default. In this case, the investment will represent a senior tranche. The probability of making a payoff is simply  

$$
P(D=3)=p\times p\times p=0.05^{3}=0.000125=0.0125\%
$$  

This simple case can be generalized easily to iTraxx indices.  

# 21.7.2 TRANCHE VALUES AND THE DEFAULT DISTRIBUTION  

We use Figure 21.10 to discuss the important relation between the area under the loss density function and the tranche values. First, note that the iTraxx attachment points slice the distribution of $D$ into five separate pieces. Each tranche is associated with a different area under the density.  

Consider the $3\%$ mezzanine tranche as an example. The tranche has two attachment points, the lower attachment point is $3\%$ and the upper attachment point is $6\%$ . In heuristic terms, the lower attachment point represents the subordination, i.e., the cushion the investor has. Defaults up  

![](e58466e404db8a390a83c9949c6a2fe45738608ad1dae22622b7d15a11320ab4.jpg)  

# FIGURE 21.10  

Loss distribution.  

to this point do not result in payments of default insurance.19 The upper attachment point represents a threshold of defaults after which the mezzanine protection seller has exhausted all the notional amount invested. Any defaults beyond this point do not hurt the mezzanine investor, simply because the investment does not exist anymore. Thus the area to the right of the upper attachment point is the probability of losing all the investment for that particular tranche.  

Once this point about attachment points is understood, we can now show the relationship between default correlation and tranche values.  

Consider Figure 21.11, giving the distribution of $D$ , the total number of defaults. Note the difference between Figure 21.11 and Figure 21.10. Figure 21.11 shows the default density function while Figure 21.10 shows a loss distribution for a portfolio. Both distributions depend on the average probability of default $p$ and on the default correlation $\rho$ . Suppose in Figure 21.11 the correlation originally was low at $\rho=0.1$ . This leads to the default distribution 1. Then, keep the $p$ the same and move the correlation up to, say, $\rho=90\%$ . This leads to loss distribution 2. The distribution will shift from 1 to 2 as shown in Figure 21.11. Consider the implications.  

The first implication is that as correlation goes up, the distribution is being pressed downward from the middle. However, the area needs to equal one. So, as the middle is compressed, the weight goes to the two endpoints. Note that the figure does not plot parts of the distribution in the middle and somewhat exaggerates the right tail for illustration.  

Second, in terms of defaults this means that as correlation increases the probability of no defaults increases compared to the low correlation case. This is because the probability of credits  

![](be791697bb73662f7e2fa77dd915ec010b5bdbfc7b7e560555076cb183cc3669.jpg)  

# FIGURE 21.11  

Default distribution.  

surviving together increases. Second, the probability of a very large number of defaults also increases compared to the low correlation case. At the extreme as $\rho\to1$ the distribution that is approximately bell-shaped starts looking more like a binomial distribution. As correlation goes to one, the default probabilities of the different assets start to behave more and more similarly and at the end, they become the same random variable. Hence the value assumed by the random variable $D$ will be either $n$ or 0, i.e., either every name will default or no name will default.  

How do we translate the implications from Figure 21.11 to portfolio losses and tranche values? First consider another distribution, the default loss distribution. Consider a portfolio of defaultable assets issued by $n$ different debtors. For simplicity, assume that the recovery rates are the same and are known at $R$ . Also, the exposure to each name is $\$1$ , meaning that the total investment in the portfolio is $\$1$ . Then, if one name defaults, the investor loses $(1-R)$ dollars. The total default loss during a horizon of length $T$ will depend on how many names default during this time interval. In other words, default loss depends on the distribution of the random variable $D$ defined earlier. Figure 21.11 showed the distribution of defaults $D$ .  

We won’t discuss here how, but let’s assume it is possible to choose a corresponding distribution for portfolio losses and plot the probability of losses as in Figure 21.10. Let’s assume that the loss distribution 1 in Figure 21.10 corresponds to a default correlation $\rho=40$ , while the loss distribution 2 in Figure 21.10 corresponds to a default correlation $\rho=90\%$ . Thus we have again a lowand high-correlation scenario as in Figure 21.11 but with slightly different values which reflect the approximate shapes of the distributions. It turns out that the effect of an increase of default correlation has important insights for tranche valuation. First, note that the probability of the area near $0-3\%$ goes up. The same is true for the probability associated with the other tail. The area near the $12-22\%$ tranche also goes up.  

But this has a second implication. The area on the right of the equity upper attachment point gets smaller. Implying the probability that the equity investor will lose all his investment has gone down. The equity tranche investor will benefit from this change in the distribution function. The equity tranche spread will go down and the investor who sold protection earlier at the higher rate will have mark-to-market gains. Hence the equity tranche protection seller is long default correlation. In other words, the equity tranche investor will benefit if the correlation increases.  

Third, the probability associated with the cushion of the super senior tranche is also getting smaller. This implies that the probability is higher and the super senior protection writer will suffer some losses. The spread on the super senior tranche will go up and the investor who sold protection at a lower spread will have mark-to-market losses. Hence the super senior protection seller is short the default correlation. In other words, the super senior tranche investor will lose if default correlation decreases.  

Finally, note that the effect of these movements is mixed on the mezzanine tranche. The area on the right of the upper attachment point has not changed that much. Hence the probabilities associated with mezzanine tranche losses are approximately the same and the mezzanine investor is more or less neutral toward the correlation changes. In the next chapter, we will discuss the sensitivity of tranche values to default correlation in further detail and explain how default correlation can be traded.  

# 21.8 THE ROLL AND THE IMPLICATIONS  

Every 6 months, on March and September 20th, the iTraxx and CDX indices roll and a new series starts trading. Some credit names may have defaulted, changed sector, merged, or been downgraded. Other CDSs may have become less liquid. These are considered as no longer eligible to be part of the index. Every such name is replaced by the next most liquid name available in its class. The “old series” continue to trade as long as there are open positions, but they are off-the-run. The new roll will be the on-the-run liquid index.  

The Roll is an important characteristic of the indices from a financial engineering point of view since its presence leads to several strategies and complications that a financial engineer must be aware of. An obvious strategy is to guess the names that will leave the index and the names that will come in. But this happens in index revisions in the equity sector as well. Credit rolls have some novel additional strategies. Note that dropping lower-rated issuers from the index and replacing them with higher-rated ones normally means that the new index should start trading at a narrower spread than the old index, everything else being the same. But, surprisingly, this may not happen, as we will see below.  

There is some empirical evidence that because the buyers of protection20 would like to stay with the new, on-the-run index due to its liquidity, right before the new series, they will close their positions. This means they will sell protection and this will lower the spreads. Of course, as the new index starts trading, the same names will buy protection and this will widen the spreads.  

There are also structured credit products that are partially based on the fact that the index will roll every 6 months. The constant proportion debt obligation (CPDO) is one good example. During a 6-month period, everything else being the same, a 5-year maturity iTraxx index will become a 4.5-year maturity index. This means that the index will roll down the curve and, if the curve is upward sloping, spreads will tighten automatically. This is due to the shorter maturity and nothing else.  

Another classic technical roll is the change in the basis. This is the difference between the index spread and the intrinsic value of the underlying CDSs of the referenced names in the index. The basis exists because normally there are more clients that buy protection than sell them.21 In past rolls, the basis between the underlying CDSs and the index has narrowed significantly. This happens because more investors are selling protection than buying protection in order to move to the new, more liquid index. The example below summarizes the mechanics of the roll.  

# EXAMPLE  

New York (Dow Jones)—As summer draws to a close, credit derivatives investors are eyeing September’s changeover in the credit default swap indexes for trading opportunities. This time around though, trading patterns surrounding the change in the indexes’ composition could differ from past ones as more issuers than ever before—a total of eight—will be dropping out of the investment-grade index family.  

Credit default swaps allow investors to protect their holdings should issuers default on their debt. Since the inception of the credit default swap indexes—liquid benchmarks that allow investors to take positions on corporate debt issuers without having to buy or sell the underlying, often illiquid cash instruments—there have been [nine rolls until March 2008] which take place every six months.  

At each roll date, issuers who have lost their investment-grade ranking by either Moody’s Investors Service or Standard & Poor’s are dropped from the Dow Jones CDX investmentgrade credit default swap index and replaced by other issuers—chosen by a poll of the dealers who belong to the index consortium. At the first index roll, six issuers were replaced, at the second five and at the last roll in March 2006, just three issuers were dropped.  

It is important to understand that at each roll the newly introduced series will have a new coupon and will be trading near par initially. The traders who buy and sell index protection are in fact buying and selling this newly introduced standardized contract.  

# 21.8.1 ROLL AND DEFAULT RISK  

Default risk in the indices is somewhat different than it looks at the outset due to the existence of the roll. In fact, at each roll the credit quality of the indices improves. In general, before a company defaults, its credit quality deteriorates. By the time the company is about to default, it is quite likely that it was dropped from the index during some previous roll. This brings up an important distinction. A 5-year position that stays with the same index will face the default risk of the underlying reference names, and these names will remain the same during 5 years. Some of these names will deteriorate and some may even default. This is what is meant by default risk.  

A position that always rolls to the new index faces a somewhat different default risk. The main default risk faced by such a position is when default occurs all of a sudden, without any indications. In this case a good corporation may go from a rating of AA to default, without the rating agencies having time to downgrade it, and before the roll date arrives. This is called jump to default risk. Note that its probability is significantly lower than staying with the same names during the 5 years and then seeing some of them default.  

# 21.9 REGULATION, CREDIT RISK MANAGEMENT, AND TRANCHE PRICING  

This section discusses the relationship between tranche pricing and credit risk management. Basel III is the framework associated with current credit risk management practices and indirectly it has a close relationship with tranche pricing.22  

# 21.9.1 CREDIT RISK MANAGEMENT, DEFAULT LOSSES, AND MARK-TO-MARKET LOSSES  

Suppose we would like to adapt a Value at Risk (VaR)-type (or Expected Shortfall) risk management approach to portfolios with credit risk.23 This means that we would like to set enough capital to cover losses $0<\alpha$ percent of the time. It turns out that there are two quite different empirical loss distributions that determine the calculation of possible losses.  

In this setting, in order to calculate possible losses due to default, one first needs to obtain a distribution for this random variable $L$ . This is the default loss distribution and is illustrated again in Figure 21.10. Using this distribution one can calculate the expected default loss and the threshold $L_{\alpha}$ which determines the extreme losses that occur with a probability of (at most) $\alpha$ , during the interval with length $T_{\cdot}$ .  

The bank would then put aside enough capital to cover default losses up to the point $L_{\alpha}$ . These have a probability $1-\alpha$ of occurring. Default losses may be greater than $L_{\alpha}$ only in $\alpha$ percent of the time. The bank is not obligated to cover these more extreme losses with additional capital.  

But this is only one way of looking at credit risk. It involves the risk associated with the default events only. This way of managing risks is perhaps appropriate if the instruments under consideration are held until maturity and if the mark-to-market is not relevant.  

On the other hand, if the portfolio under consideration is a trading portfolio where marking-tomarket is important or if the instruments may not be held until maturity, then the bank or the hedge fund faces another risk.24 This risk comes from credit quality changes, which incidentally also involves defaults. If credit deteriorates and needs to be sold or marked-to-market, then the bank or the hedge fund will still suffer credit losses although no default has occurred. The default loss distribution cannot take such potential losses into account, because it is only directed toward measuring loss due to default. The loss due to credit quality changes requires an additional effort. The change in the market value of the portfolio due to credit quality changes can be calculated in a way similar to that of market risk.  

The calculation of the default loss distribution requires the default probabilities for each name and the default correlations. The calculation of the credit return distribution on the other hand requires, in addition, the conditional transition probabilities concerning the rating migrations of each name in the portfolio as well as their correlations. Hence the calculation of this second distribution is much more involved. Note that default is only one of the states where credits can migrate. Hence default risk is included in the credit loss distributions due to credit deterioration.  

# 21.9.2 CAPITAL REQUIREMENTS AND CDO ACTIVITY  

As we saw at the beginning of this chapter, securitization activity has dropped significantly since pre-GFC levels. One of the reasons why securitization and CDO activity was so high before the GFC was that it represented a way for banks to reduce regulatory capital. As with many previous booms, this led to excesses and abuses. However, securitization activity continues and even under the current more stringent capital requirements banks find it possible to reduce capital requirements as the following example indicates:  

# EXAMPLE  

In one example Chenavari provides to investors, a $\$1$ billion portfolio of small business loans has a riskweighting of $75\%$ under Basel III’s standardised approach, generating a risk-weighted asset (RWA) total of $\$750$ million. That implies a bank would need around $\$75$ million of equity capital to support it. Securitising the pool and transferring the $I.5\mathrm{-}8\%$ second-loss tranche—representing $\$65$ million of exposure—to a third party, while retaining the first loss and senior tranches, could bring a bank’s capital requirement down to around $\$30$ million, a $60\%$ saving. The bank also gets to keep the loans on its balance sheet and maintain its client relationships.  

Fery refuses to mention counterparty names, but describes some deals he says are representative of the business the fund engages in. One involves a h1 billion portfolio of around 1,500 loans to German small and medium-sized enterprises (SMEs). The pool had a weighted average credit rating of $B B+$ and an average duration of two-and-a-half years. More than half the loans were investment-grade. Chenavari had a positive view of Germany’s Mittelstand sector—the legion of mostly family-owned small businesses that power the country’s export machine—so agreed to absorb the second loss on the pool via a h65 million note referencing the $I.5\mathrm{-}8\%$ tranche of the loan portfolio, paying $I3.5\%$ over three-month Euribor per annum. The bank retained the first loss exposure and the entire senior tranche.  

The firm cut a similar deal with a UK bank that was seeking regulatory capital relief on a d1 billion portfolio of residential mortgage loans. The pool comprised nearly 8,000 loans originated before 2007, and included a large portion of interest-only and buy-to-let mortgages. This time, Chenavari acquired an eightyear note referencing the $2-8.5\%$ second-loss tranche, paying a coupon of $I2.5\%$ over three-month LIBOR. Fery and his team have structured a host of similar deals involving different types of underlying assets— everything from emerging market corporate loans and European mortgages to asset-backed securities, trade finance assets and derivatives counterparty risk. The average deal size is around \$80 million, with estimated returns in the $10\mathrm{-}20\%$ range, he says.  

One of the difficulties for rivals seeking to replicate the strategy is that deals happen infrequently and often require months of work. That means building relationships with a large number of banks, and having a solid grasp of credit analysis and structuring—on both counts, it helps that Fery used to run the global credit trading business at Calyon.  

(Risk magazine, 13 January 2014, “Hedge fund of the year: Chenavari Investment Managers”, www.risk.net/2317763)  

# 21.9.3 LESSONS FROM THE GFC, POST-GFC CAPITAL REGULATION AND THE SECURITIZATION MARKET  

Securitization and the issuance of CDOs was so actively pursued by banks since it allowed banks to remove loans from their balance sheets and thus improve their capital ratio. Commercial banks must have sufficient capital to cover potential depositors’ withdrawals. The ability to lend is affected by capital requirements and if a bank does not have enough capital it cannot lend further unless it finds a way to remove the assets from its balance sheet. As we saw, CDOs are a form of securitization. Many of the junior CDO tranches issued by banks were backed by risky (subprime) loans. Investigations following the GFC revealed malpractice in the loan origination process which saw loans approved without proper vetting of borrowers and the violation of proper procedures. As a result many of the CDOs that were sold to investors were very risky but this did not become apparent to most investors until the US housing market boom slowed in 2006. It is estimated that of the $\$500$ billion worth of CDOs outstanding at that point, about $50\%$ were based on MBSs and around $75\%$ of these contained subprime loans. Driven by the prospect of commissions, risky loan origination and CDO issuance continued nevertheless. As selling these increasingly risky assets became more difficult traders found ways to make the banks hold some of the riskier tranches of the CDOs in order to facilitate sales, achieve favorable credit ratings for the securities, and pay traders commissions. One of the factors that exacerbated the GFC was the prevalence of ratings arbitrage which involved pooling low-rated tranches to create CDOs. All these factors not only perpetuated the excesses but also made the eventual correction more painful as banks themselves were saddled with large losses and the financial system was crippled until banks were bailed out, wound down, or recapitalized. Housing bubbles occur regularly around the world, but the one preceding the GFC was exacerbated by abuses of securitization and misaligned interests.  

In December 2013, the Basel Committee on Banking Supervision issued a second consultative document regarding revisions to the existing securitization framework which was found to be deficient. According to the Basle Committee, the GFC revealed a number of shortcomings in the current securitization framework which it seeks to address with the latest changes. First, practices in the run-up to the GFC showed an almost mechanistic reliance on external credit ratings. Second, there was a tendency to assign too low risk weights for highly rated securitization exposures. The reason for this was that the calibration assumptions typically used turned out to be questionable and there was a lack of sufficient risk drivers across approaches in determining risk weights. Third, risk weights for low-rated senior securization positions were found to be too high. Fourth, the securitization framework leads to undesirably procyclical economic dynamics or cliff effects.  

Vis-a\`-vis initial post-GFC proposals by the committee the document suggests lower capital requirements but these are still more stringent than existing capital requirements. Thus, if the future Basel Committee securitization framework was based on the latest proposal this leaves the possibility that the securitization and CDO market would continue to be an important part of financial markets.  

# 21.9.4 CAN SECURITIZATION CURE CANCER?  

In this chapter, we discussed the economic rationale for securitization. We have seen that securitization and financial engineering can play a useful economic role if correctly implemented. As in all areas of economic activity regulation exists and is required to ensure that all market participants act legally and responsibly. Financial engineering concepts have, however, also applications outside finance and may provide not just economic benefits but other social welfare improvements. In recent work, Fagnan et al. (2013) pose the question of whether financial engineering can cure cancer, a leading cause of death in many industrialized countries. The authors observe that investment in the pharmaceutical industry has declined in recent years and make proposals on how securitization can help increase investment including key important cancer research. The authors hypothesize that one of the reasons for low private sector investment is the skewed distribution of drug trials. The authors provide a stylized example that assumes a hypothetical drug-development programme that requires $\$200$ million development costs in present value terms, a 10-year development period during which no revenues are generated and which has a $5\%$ chance of successful drug approval at the end of 10 years. If one assumes that such a programme generates $\$2$ billion in annual revenues in the subsequent 10 years (i.e. years 11 20), many investors could be expected to be scared off by the return standard deviation of $423\%$ .  

One proposed solution to this problem is to create a fund that pools various drug-development programmes and securitizes the resulting revenue streams. The proposed name for the structured securities that give ownership interest to experimental drug compounds is research backed obligations or RBOs. Fagnan et al. (2013) suggest how techniques that were used in the creation of CDOs and ABSs can be used to provide guarantees and alter the capital structure of these securities in such a way that they represent an attractive investment opportunity for investors. To date no such RBO has been issued but the research shows that financial engineering techniques, if appropriately applied, may potentially have wider implications and social benefits beyond the narrowly defined domain of financial markets.  

# 21.10 NEW INDEX MARKETS  

The credit sector plays an important role in financial markets for several reasons. One of these is the methodical way new sectors are introduced by the major players. Markets are normally created endogenously with the interaction of thousands of traders, market makers, and risk managers. In the credit sector, this effort has been consciously directed by broker-dealers and has come after years of experience in new derivatives markets and trading strategies. As a result, broker-dealers have been quite successful in creating platforms for trading new risks and offering broad numbers of instruments for hedging a range of credit risk exposures. The Markit website provides an overview of a wide range of indices including iTraxx, CDX, ABX, and LCDX.  

The ABX and LCDX indices are the most prominent of the new tradeable indices that permit trading of new risks. The ABX index is a carefully constituted index that permits trading and hedging of mortgage debt exposures. A player who is short mortgage debt will hedge this position by buying the ABX index. The LCDX is similar to the iTraxx or CDX, except that the underlying securities are loans instead of being bonds. Hence, this index helps hedging loan exposures. Levx is similar. It is an index of leveraged loans.  

A player who is long will hedge the position by selling the index. These indices are traded in the form of series and offer a fixed coupon at each roll.  

# 21.10.1 THE ABX INDEX  

The ABX index is made of obligations issued by 20 issuers of residential MBSs. Altogether there are five subindices. These subindices are each made of one security from each one of these issuers. These securities and hence the subindices have ratings that range from AAA to BBB 2 . Similar to the roll in the iTraxx and CDX indices, the new series of ABX indices roll on January 19 and July 19. Each series has a new set of mortgage loans behind it. Thus, unlike the iTraxx and CDX index, the ABX indices have “vintages.”  

The securities included in the index are essentially debt securities entitling the investors to receive cash flows that depend on residential mortgages of one-to-four family residences. Hence variations in these cash flows, defaults, and delinquencies affect the value of the ABX indices. An investor in the ABX indices will receive (pay) a fixed coupon set at the roll date and will make floating payments (receipts) if there is an interest or principal shortfall in the cash flows.  

# 21.10.2 THE LCDS, LCDX  

The so-called LCDS (Loan Credit Default Swaps) contracts and their corresponding index LCDX are relatively new tools in the credit sector. Besides being important tools they provide a good opportunity to summarize the Credit indexing technology from a somewhat different angle. LCDS is similar to the single-name CDS that we saw in Chapter 18. In a CDS, the deliverable debts are bonds. With LCDS the deliverable is syndicated secured debt in the United States that was originally issued by a syndicate. LCDX is the corresponding tradeable index and it is similar to the iTraxx and CDX indices. The underlying for the LCDX is $n=100$ equally weighted single-name LCDS. The loans in question trade in the secondary leveraged loan market. The index launches with a fixed coupon, paid quarterly. The index trades on a clean price basis. If the price goes down, the corresponding spread goes up.  

The protection seller will receive a coupon fixed at the roll date and will make a compensating payment during a credit event. Also during a credit event the protection seller pays the notional amount $N$ and gains possession of the loan. Cash settlement is also permitted. The amount of this cash settlement will be determined in an auction.  

# 21.10.2.1 Cancelability  

An issuer can repay the debt and may not issue new debt afterward. If there is no deliverable obligation then the LCDS cannot continue. Thus LCDS contracts are cancelable unlike the standard CDS. An issuer may be upgraded. When this occurs, the issuer can repay the original debt and issue new debt with lower interest cost.  

A loan repayment starts a 30 business day period, and during the entity can initiate a new loan. If after 30 days no new loans are made, the name is removed from the index after a dealer vote.  

This cancelability affects the valuation. If the LCDS is cancelable upon repayment of debt, then the final maturity for a given LCDS will be unknown. The calculation of the present values should then take into account the probability that the loan will be repaid early. This is similar to the use of the credit-risky DV01.  

# 21.10.2.2 Quoting conventions  

The iTraxx and CDS index families are quoted on a spread basis, except for the equity tranche which is quoted with an upfront.25  

On the other hand, the LCDX and ABX indices are quoted on a price basis and this forms another difference.  

# 21.11 STRUCTURED CREDIT PRODUCTS  

CDS is the basic building block of the credit sector. Using CDS engineering, one can immediately create credit-market equivalents of risk-free fixed-income instruments. Some of these instruments are discussed in this section.  

# 21.11.1 CREDIT OPTIONS  

It is natural for options to be the first derivative to be written on credit indices. After all, there are liquid indices and these could serve as an attractive underlying for those who would like to hedge their credit volatility or for investors who would like to take positions in them. Yet, such options turn out to be much more complicated to structure and market than visualized at the outset. Although there is decent liquidity in the market, with daily references to iTraxx and CDX implied volatility, some difficulties remain.  

There are essentially three problems associated with options on credit indices. First, the credit sector is heavily influenced by monetary policy and has a long credit cycle. The practitioners would need long-dated options. Second, although stocks are liquid, a large majority of corporate bonds have very little liquidity; but the third and main problem is the index roll.  

Essentially these indices change every 6 months and one cannot price a long-term option against such an unstable benchmark.  

The credit option trader is then forced to operate in the shortest maturities and the exercise dates controlled by the roll dates.26 This is not sufficient for traders since their needs are really 5-year options because these could be used to arbitrage the structured credit market.27  

There is another important difference between credit index options and options from other markets. In the credit sector the longer dated an option, the more it becomes a correlation product. With longer-dated options, the underlying risk is to what extent referenced credits will move jointly. Shorter-dated options, on the other hand, are more like volatility products.  

# 21.11.2 FORWARD START CDOs  

Using forward start CDOs, one can take leveraged positions on the outlook for credit spreads in the distant future, say from 2015 to 2020. Such forward start products may be useful for some investors that want to hedge their positions on take exposure during the credit cycle.  

The product can be structured by selling CDSs maturing, say, in 10 years, and buying CDSs maturing in a shorter maturity, say, 5 years. Such forward start instruments are marketed as bespoken deals on the iTraxx or CDX default swap indexes. The most common reference is the mezzanine tranche insurance against the $3\mathrm{-}6\%$ of defaults in a credit portfolio.  

The net position of buying 5-year protection and selling 10-year protection is selling 5-year protection 5 years from now. Note that such a position will have positive carry. Due to this, such trades become popular if the iTraxx curve is relatively steep.  

# 21.11.3 THE CMDS  

The constant maturity default swap (CMDS) is an important component of the structured credit sector. A CMDS can be structured as follows.  

Fix the maturity of the CDS at, say, 5 years. Consider a series of $T$ -maturity CDSs starting at times $t,\ t+1,\ t+2,\ t+3,\ t+4$ , and $t+5$ . Note that the spread of the current CDS is known at time $t$ , whereas future CDS spreads $c_{t+i}$ will be known only in the future as time passes. Also note that these CDSs all have the same 5-year constant maturity. Let their spread be denoted by $c_{t+i}$ . Then the CMDS will be the 5-year CDS that pays the floating spreads $c_{t+i}$  

Essentially this is an extension of the CMS swaps to the case where the underlying risk incorporates default risk. There are several uses of this crucial component. A market example follows.  

# EXAMPLE  

Investors want to sell protection today with the potential to take advantage of expected future spread widening; this is exactly what the CMDS product provides. Client interest in constant maturity CDOs (CM-CDOs) also helps establish the CMDS market by drawing clients’ attention to what the product can achieve.  

Nearly all new CDOs in the pipeline today come with the option of constant maturity technology embedded in them.  

There are concerns about the possibility that profit and loss volatility may be injected into synthetic CDOs because of International Accounting Standards (IAS) 39 which requires all derivatives to be marked-to-market through the income statement. These concerns drive a lot of interest in CM-CDOs. Using CMDS to mitigate mark-to-market volatility is a legitimate reason for employing them. Market participants do not expect CMDS to outshine the market for tranched credit index products or credit options. But having standardized fixings would be useful both for closing CDO deals and for developing the market for cash-settled credit spread options and other structured credit and volatility products.  

CMDS are generally viewed as a building block for other structured credit products. The challenge is that fixings for credit derivatives are not as straightforward as they are for interest rate derivatives. “The amount of information that you need is so much greater than it is in rates. And where do you stop with fixings? The universe of names in the credit default swap market is very large. How many do you fix, and do you fix for the five-year or the whole curve for each name?” asked a trader.  

Fixings on the credit indices are relevant for CMDS contracts because if CDSs are written on indices, which most are, an independent fix is needed. Quoting an index, such as Dow Jones iTraxx, is not easier as the coupon must be linked to 125 names, but the liquidity in credit indices is greater than it is in the underlying single names.  

Standardized fixings. About 18 dealers have been working with Credited, the electronic dealer-broker, and Mark-It Partners, the OCT derivatives valuation firm, to standardize fixings for credit indices. Six weekly fixing test runs have been completed so far (Thomson Reuters IFR 1552). No runs on single-name credit default swaps have been tested yet, though.  

According to dealers, the standard resets that are being developed are essential for the continued growth of the product as opposed to relying on just dealer polls as documented in current contracts.  

“Fixings are worthwhile for the credit derivative market not just for CMDS but for all other second- and third-generation credit derivative products. For example, if fixings are done for iTraxx index tranches, this will help breed a further range of derivatives on the tranches. So, in this way, fixings are essential just like LIBOR fixes every day for the swap market,” one dealer added.  

For the CMDS market to evolve, common documentation must also be forthcoming, dealers say. In CMDS, two documentation issues to overcome are whether the coupon is quarterly or semiannual and if the fixing is $T+1$ or $T+2$ .  

The CMDS can be used to take an exposure to the movements of the credit curve. If one expects the credit curve to steepen then one could, for example, buy a 5-year protection on the CMDS that references a 10-year CDS and sell protection on the 5-year CMDS that references a 3-year CDS. The reverse could be done if the credit curve is expected to flatten. One could also put together a swap of the CDSs: e.g., paying 10-year and receiving 3-year reference spreads.  

# 21.11.4 LEVERAGED SUPER SENIOR NOTES  

The spreads on super senior tranches are very tight—say, around 10 bps. This is not very attractive to the investors. Hence, the demand for super senior tranches is relatively low. Yet, banks have issued many mezzanine tranches on CDOs and have kept the super senior and equity tranches on their books. They need a way to generate a demand for these tranches. Leveraged super senior notes is one method that was devised for selling the super senior risk to others.  

With the note investors, take the additional exposure to the mark-to-market value of the tranche, and the trigger protects the bank against the investor’s credit risk. Given the leverage, super senior investment may lose an amount greater than the original investment. With the trigger, this risk is reduced.  

In this sense, one can say that a leveraged super senior note is a modification of the super senior tranche. This modification occurs first in the leverage. $N$ is collected from the investor, but $\lambda N$ with $1<\lambda$ invested in the super senior tranche. Hence the return is also multiplied by $\lambda$ . Second, there is a trigger on the market value of the note. If this trigger is reached the issuer of the note can unwind the position and return the mark-to-market value of the note to the investors.  

# EXAMPLE  

Consider a USD1 billion portfolio. Let the senior tranche have attachment points of $12\%$ and $30\%$ . This gives a thickness of USD180 million.  

Suppose we select a leverage ratio of 10. The leveraged super senior note will consist of an issue of USD18 million. This amount is multiplied by 10 and invested as a notional amount of 180 million in the super senior tranche. Assuming that the quoted spread for this tranche is 8 bp, the note will pay $\mathrm{LIBOR}+100$ .  

The market value trigger could be defined, for instance, as $70\%$ of the issue amount of USD18 million. If the market value of the note falls below this limit, say becomes 12, then the 12 is returned to the investors instead of the original investment of 18.  

There are two general tendencies in structured credit. The first is to introduce leveraged transactions; the second is the introduction of market risk in addition to default risk. The leveraged super senior notes are examples of the first tendency. The CPPI techniques applied to credit are an example of the second and they will be discussed in Chapter 23.  

Where does risk lie in leveraged super senior notes? Owing to the substantial credit protection inherent in a super senior structure, the default risk itself is very limited. The risk borne by investors mainly lies in the behavior of the market value of the CDS tranche, which depends on spreads and correlations. Most transactions are actually structured so as to ignore correlation variations as market value parameters; they introduce instead a trigger on the portfolio average spread.  

In such a trade, the investor is long the super senior risk, while the dealer goes short that risk. To boost the return on these investments, dealers have been constructing products for their clients using borrowed funds.  

During the year 2000, dealers purchased significant amounts of mezzanine protection and, as a result, were left exposed to the senior and equity components of the capital structure. This is because they had marketed mezzanine products to clients and kept the senior and equity tranches on their books. Note that leveraged super senior trades is one way of buying protection on the senior and super senior tranches. Hence, the structured product is in fact useful to both the client and the dealer.  

If dealers did not have such long senior and super senior positions, after buying protection from a client with a leveraged super senior issuance, they would hedge themselves through the iTraxx index or other individual CDSs, although there may be a significant basis risk between the two risks.  

# 21.11.5 CoCos  

CoCos are an example of post-GFC financial innovation. The structuring and valuation of CoCos represent an interesting application of the financial engineering principles that we discussed in this book, including the modeling of credit and default events. For this reason and since CoCos are a relatively recent and untested product, we discuss CoCos in some detail. A CoCo is a hybrid product. It is a debt instrument that automatically converts into equity or suffers a write down when a certain trigger event occurs. CoCos can therefore be viewed as an example of convertible debt which we first encountered in Chapter 19. However, the contingent conversion of CoCos into equity means that they have more in common with structured products such as reverse convertibles discussed in Chapter 20 than with convertible bonds. What CoCos have in common with reverse convertibles is that they expose the holder to a limited upside but a potentially large downside. However, in contrast to reverse convertibles the trigger for CoCos recently issued by banks is an accounting trigger such as the banks’ Tier-1 capital ratios (typically $5\text{\textperthousand}$ of risk-weighted assets) and not their share price. The first CoCo was issued by Lloyds banking group in 2009 and labeled Enhanced Capital Note (ECN). The d7bn Lloyds ECNs convert into equity if the bank’s tier one capital falls below $5\%$ . The minimum level for banks to pass the European stress test is $5.5\%$ .  

There is another important difference compared to convertible bonds and reverse convertibles which is that the trigger may sometimes depend on regulatory intervention, as was the case with a CoCo launched by Credit Suisse in February 2011 under the name Buffer Capital Notes. The Swiss regulator has the right to intervene and force a conversion into shares of the Credit Suisse CoCo. Of course, such intervention that is external to the company makes modeling the risk significantly more complicated than when the trigger is just related to the share price.  

# 21.11.5.1 Cocos versus convertible bonds  

Figure 21.12 shows the difference in price behavior between a CoCo and a convertible bond. For simplicity here we assume that the underlying debt is riskless. This is reflected in the horizontal line that represents the flat bond floor. This is in contrast to Chapter 19 where convertible bond value for low stock price levels converged to zero. As the share price falls, the convertible bond value approaches the bond floor from above. The CoCo behaves differently. We assume that the  

![](c93beceb44172d2f870cdc443a12c1c7ccc57542855b31b37c74a00f504106ca.jpg)  

# FIGURE 21.12  

Contingent convertible versus convertible bond.  

$\mathbf{CoCo}$ is converted into shares when the share price $s$ falls below a market trigger $S^{*}$ . As the stock price falls, the line representing the CoCo approaches the conversion value line from below. As the stock price rises the CoCo approaches the bond floor from below while the convertible bond approaches the conversion value from above. The slope of the line representing the conversion value depends on the conversion ratio (CR), discussed in Chapter 19.  

# 21.11.5.2 Valuation of CoCos  

CoCos provide a nice application of the financial engineering principles discussed in this book. Since CoCos are a hybrid security, it is not surprising that there are different valuation methods that can be used to price a CoCo. In fact there are three different approaches: the credit derivative approach, the equity derivative approach, and the structural credit approach. From a credit derivative perspective or reduced form approach, we price the CoCo as a fixed-income instrument with an enhanced yield as compensation for potential losses upon conversion. The risk of losses can be modeled using the default intensity or reduced form approach outlined in Chapter 18. One can model the trigger event that leads to the conversion of the CoCo into shares, an event similar to the way default is modeled statistically in the valuation of corporate debt or CDS. This approach could lead to an equation that expresses the credit spread on CoCos as a function of the default, or in this case trigger, intensity $(\uplambda)$ , and the recovery rate. As a variation of Eq. (18.38) we would obtain the following relationship:  

$$
\mathrm{spread}_{\mathrm{CoCo}}=(1-R_{\mathrm{CoCo}})\times\lambda_{\mathrm{CoCo}}
$$  

From an equity derivatives perspective, we can apply the principles outlined in Chapter 20 and see the CoCo as a long position in CR shares, where CR is the conversion ratio. The knock-in feature is dependent on the trigger event and barrier option valuation approaches can be used to price it. Third, in Chapter 19 we saw structural models of default and credit valuation. CoCos are just one element of the issuer’s capital structure and therefore we can apply the principles underlying the Merton model and its extensions to value CoCos. For this purpose, we would specify a stochastic process for the firm and model the value of different continent claims, including those of CoCo holders, as a function of the value of the assets and the trigger price. From an equity derivatives one can decompose the $\mathbf{CoCo}$ into a risky bond, a knock-in forward on the underlying share and a short position in a digital down-and-in option, which reflects the fact that the coupons on the bond will only be received as long as the trigger event does not occur. This leads to the following contractual equation:  

![](eed5270f97883ef498726f094714b186a5b620cf5f98e46fabd80173c32457ed.jpg)  

The end of chapter exercises provide CoCo valuation examples using the credit reduced form approach and the equity derivatives approach. Further details are available in the references listed at the end of the chapter.  

# 21.11.5.3 The outlook for CoCos  

The rationale for CoCos arose because of banks’ desire to shore up their capital base in response to regulatory changes that led to more stringent capital requirements. The implicit hope on the part of regulators is that CoCos will help protect big banks from having to be bailed out by taxpayers again. Therefore, CoCos are also sometimes referred to as bail-in bonds. Bond holders were largely unaffected by bank losses during the GFC because taxpayers bailed out banks. The idea behind a bail-in bond is not to bail out, but to bail-in bond holders before taxpayers are asked to rescue a bank. Bail-in clauses are different from traditional bankruptcy procedures which have strict rules and court-supervised procedures. As Figure 21.12 shows, CoCos have a significant downside potential which has to be compensated by a higher yield. Thus, these instruments may be of interest to yield-hungry investors, provided that they understand the risks.  

However as the following reading illustrates there is some concern about the hidden risk and future performance of CoCos.  

# EXAMPLE  

Potential conflict of interest between regulators and investor can arise as a result of significant discretion that regulators have over the mandatory conversion feature embedded in CoCos. From an investor point of view, a CoCo is a hybrid product that is a deeply subordinated investment with uncertain income and significant capital risk. In a 2012 Financial Times article Satyajit Das warned that as a result of the dependence of conversion on regulatory decisions as well as credit risks, it is rather difficult for investors to quantify the probability of conversion. In addition to this risk, investors also face liquidity risk when they buy CoCos. The potential downside is made worse by the possibility of “death spirals”. Such negative feedback loop spirals may arise when holders of a bank’s shares try to sell shares to hedge a feared decline in the value of their holdings in the face of a mandatory conversion and potential dilution of their shares. This can potentially worsen the bank’s financial position and lead to increased fear among other banks, counterparties, investors, and depositors. The probability of such spirals is increased by the fact that hybrids such as CoCos are marketed to private investors instead of institutional investors who face restrictions regarding purchases of hybrid securities. Of course, it is possible that investors are compensated for these risks in the form of generous coupons, but the recent example of CoCos issued by Credit Suisse and UBS which paid about $8\%$ per annum suggests otherwise. Double-digit percentage coupons may be required to compensate for the missed couponsor mandatory conversion in times of distress. History contains several examples that should serve as a warning regarding the purchase of hybrids without careful due diligence. Perpetual Floating Rate Notes were a popular form of hybrid capital in the late 1980s but saddled their investors with large capital losses when they fell sharply in price. Another example is the case of some hybrid capital securities issued in the late 1990s in Australia which in 2012 were trading well below issue price. More recently, during the GFC several banks deferred coupon payments on hybrids which caused losses for investors.  

As the above example illustrates, there are serious concerns about future performance of CoCos and several design flaws are apparent in the existing offerings.  

The sensitivity of financial engineering and structured product innovation to regulatory changes was highlighted again in February 2014 when both Lloyds and Credit Suisse discussed plans to buy back their CoCos issued in 2009 after their respective regulators changed the way they viewed the debt and which instruments will count towards capital in bank stress tests. The February 2014 episode illustrates the significant uncertainty related to CoCos, their trigger events, their treatment by regulators for stress testing purposes, potential downward spirals and the wider effects on the legal protection of bond holders and the economy.  

# 21.12 CONCLUSIONS  

This chapter discussed securitization and the role that it has played before and after the GFC. We discussed one example of securitization in the form of CDOs and their tranches. We saw that CDO tranche values depend on default correlations which has led us to a discussion of correlation trading. The next chapter will provide a detailed example that shows the effect of correlation on tranche prices. This will lead us to a discussion of how to risk manage positions in CDO tranches and take views on increasing and decreasing correlations.  

This chapter also provided interesting applications of financial engineering principles including option valuation and reduced form and structural models which we encountered in earlier chapters. We discussed credit structured products include post-GFC developments such as CoCos.  

# SUGGESTED READING  

Brigo et al. (2010) provide a good account of credit models and CDOs during and after the GFC while Schonbucher (2004) and Duffie and Singleton (2002) are earlier academic approaches.  

Some of the most useful references are in handbooks published by banks. We recommend the Handbook of Credit Derivatives by Merrill Lynch and one by JP Morgan. The latter is the closest approach to the market standard in this sector. For more details on and recent developments in the credit indices, see www.markit.com. Francis et al. (2003) is a good reference for credit correlation trading. De Spiegeleer and Schoutens (2012) provide an in-depth analysis of the valuation and structuring of CoCos.  

# EXERCISES  

1. What is the difference between an ABS and a CDO?   
2. What is the effect of default probabilities on CDO tranches? What is the effect of default correlations on CDO tranches? Explain.   
3. Consider the following news from Reuters: 1008 GMT [Dow Jones] LONDON—SG recommends selling 7-year $0-3\%$ tranche protection versus buying 5-year and 10-year $0-3\%$ protection. 7-year equity correlation tightened versus 5-year and 10-year last year. SG’s barbell plays a steepening of the 7-year bucket, as well as offering positive roll down, time decay, and jump to default. SG also thinks Alstom’s (1022047.FR) 3 5-year curve is too steep, and recommends buying its $6.25\%$ March 2010 bonds versus 3-year CDS. a. What is a barbell? What is positive roll down, time decay? b. What is jump to default? c. Explain the logic behind SG’s strategy.   
4. Consider the following quote: It is only when portfolios are tranched that the relative value of default correlation becomes meaningful. So, for subordinate tranches, the risk and spreads decrease as correlation between defaults increases, while for senior tranches the risk and spreads increase as default correlation increases. a. Explain the first sentence carefully. b. Explain the second paragraph. c. Suppose you think that credit correlation would decrease in the near future. What typ trade would you put on?  

5. Consider the following quote:  

Until last year, this correlation pricing of single-tranche CDOs and first-to-default baskets was dependent on each bank or hedge fund’s assessment of correlation. However, in 2003 the banks behind iBoxx and Trac- $x$ started trading tranched versions of the indexes. This standardization in tranches has created a market where bank desks and hedge funds are assessing value and placing prices on the same products rather than on portfolios bespoke single-tranche CDOs and first-to-default baskets. Rather than the price of correlation being based on a model, it is now being set by the market.  

# 778 CHAPTER 21 SECURITIZATION, ABSs, CDOs  

a. What is the iTraxx index?   
b. What is a standard tranche?   
c. Explain the differences between trading standardized tranches and the tranches of CDOs issued in the market place.  

6. (Reduced form approach to CoCos valuation). The text mentions that CoCos can be valued from three different perspectives. One of the approaches is based on the reduced form or default intensity approach outlined in Chapter 18. Assume that a $\mathbf{CoCo}$ has a 5-year maturity. The underlying share price (S) is d100, the equity volatility is $20\%$ and there are no dividend payments. The continuously compounded interest rate is $4\%$ . Assume that the trigger event occurs then the share price (S) reaches the trigger price of $S^{*}=\pounds50$ . Calculate the credit spread using the trigger intensity model. Consult the end of chapter references for a derivation of the required probability of hitting the trigger, the trigger intensity and the recovery rate.  

Consider the following reading, which deals with collateralized debt obligations (CDOs). Despite the deluge of downgrades in the collateralized debt obligation (CDO) market, banks are not focusing on the effect of interest rate swaps on arbitrage cash flow CDOs, Fitch Ratings said in a report released last week.  

Ineffective interest rate hedging strategies inflicted the hardest blows to the performance of high-yield bond CDOs completed during 1997 1999, the report noted.  

This combination of events caused some CDOs to become significantly over-hedged and out-of-the-money on their swap positions at the same time, the report found. For its report, Fitch used a random sample of 18 cash-flow deals that recently experienced downgrades.  

While half the CDOs benefited from falling rates, half did not. All nine of the over-hedged CDOs were high-yield bond transactions that closed before 1999.  

With the benefit of hindsight, a balanced guaranteed or customized swap would have mitigated the over-hedged CDO’s risks. Plain vanilla swaps, which were economically advantageous during 1997 1999, ended up costing money in the long run because the notional balance of the swap is set at the deal’s closing date and does not change over time, the report said. CDOs tend to use a plain vanilla swap instead of a customized swap because they are cheaper. (Thomson Reuters IFR Issue 1433, May 2002)  

a. Show the cash flows generated by a simple CDO on a graph. Suppose you are short the CDO. b. What are your risks and how would you hedge them?   
c. Show the cash flows of the CDO together with a hedge obtained using a plain vanilla swap. d. As time passes, default rates increase and interest rates decline, what happens to the CDO and to the hedge?   
e. What does the reading refer to with buying a customized swap?  

# CASE STUDY: CREDIT-LINKED NOTES  

8. Read the following case study and answer the questions below. Overall, this case study deals with CDSs, synthetic corporate bonds, and, more interestingly, credit-linked notes. The case study highlights two issues. a. Cash flows and the risks associated with these instruments, and the reasons why these instruments are issued. b. The arbitrage opportunity that was created as a result of some of the recent issuance activity in credit-linked notes. Focus on these aspects when answering the questions that follow the readings.  

# Reading  

Default swap quotes in key corporates have collapsed, as a rush to offset huge synthetic credit-linked notes has coincided with a shortage of bonds in the secondary market, and with a change in sentiment about the global credit outlook. The scramble to cover short derivatives positions has resulted in windfall arbitrage opportunities for dealers who chanced to be flat, and for their favored customers.  

At least h5bn, and possibly as much as h15bn, equivalent of credit-linked note issuance has been seen in the last month. The resulting offsetting of short-credit default swap positions has caused a sharp widening in the negative basis between default swaps and the asset swap value of the underlying debt in the secondary bond market.  

Dealers with access to corporate bonds have been able to buy default swaps at levels as much as 20 bp under the asset swap value of the debt, and to create synthetic packages for their clients where, in effect, the only risk is to the counterparty on the swap. Credit derivatives dealers who chanced to be flat have been turning huge profits by proprietary dealing—and from sales of these packages to their favored insurance company customers.  

Deutsche Bank, Merrill Lynch, Bear Stearns, and Citigroup have been among the most aggressive sellers of default swaps in recent weeks, according to dealers at rival houses, and their crossing of bid/offer spreads has driven the negative default-swap basis to bonds ever wider.  

A h2.25bn credit-linked note issued by Deutsche Bank is typical of the deals that have been fuelling this movement. The deal, Deutsche Bank Repon 20012014, offered exposure to 150 separate corporate credits, $5I\%$ from the US and 49% from Europe. Because DB had the deal rated, the terms of the issue spread across trading desks in London and New York, and rival dealers pulled back their bids on default swaps in the relevant corporates.  

Other banks were selling similar unrated (and therefore, private) credit-linked notes at the same time, which led to a scramble to offset swap positions. Faced with a shortage of bonds in the secondary market, and repo rates at $0\%$ for some corporate issues, dealers were forced to hit whatever bid was available in the default swap market, pushing the negative basis for many investment grade five-year default swaps from an 8 bp 16 bp negative basis to a 12 bp 20 bp basis last week.  

This produced wild diversity between default swaps for corporates that had seen their debt used for credit-linked notes, and similar companies that had not. Lufthansa five-year default swaps were offered at 29 bp late last week, while British Airways offers in the same maturity were no lower than 50 bp, for example.  

Many default swaps were also very low on an absolute basis. Single A-rated French pharmaceuticals company Aventis was quoted at 16 bp/20 bp for a five-year default swap at the close of dealing on Friday, for example. Other corporate default swaps were also at extremely tight levels, with Rolls-Royce offered as low as 27 bp in the five-year, Volkswagen at 26 bp, BMW offered at least as low as 26b, and Unilever at 21 bp.  

# Run for the Door  

The movement was not limited to European credits. Offsetting of default swaps led to the sale of negative-basis packages in US names including Sears, Bank of America, and Philip Morris, with Bank of America trading at levels below 40 bp in the five-year, or less than half its trade point when fears about US bank credit quality were at their height earlier this year.  

General market sentiment that the worst of the current downturn in credit quality has passed has amplified the effec of the default swap selling. Investors are happy to hold corporate bonds, which has left dealers struggling to buy paper to cover their positions as an alternative to selling default swaps.  

“Everyone tried to run for the door at the same time,” said one head dealer, describing trading in recent weeks. He predicted that the wide negative basis between swaps and bonds will be a trading feature for some time. Dealers worry that the banks which are selling default swaps most aggressively are doing so because they are lining up still more synthetic credit-linked notes. As long as they can maintain a margin between the notes and the level at which they can offset their exposure, they will keep hitting swap bids.  

This collision of default swap-offset needs, a bond shortage, and improved credit sentiment is working in favor of corporate treasurers. WorldCom managed to sell the biggest deal yet from a US corporate last week, and saw spread talk on what proved to be a US\$ 11.83bn equivalent deal tighten ahead of pricing. An issue of this size would normally prompt a sharp widening in default swaps on the relevant corporate, but WorldCom saw its five-year mid quotes fall from 150 bp two weeks ago to below 140 bp last week.  

The decline in default swap quotes, and widening basis-to-asset swap levels for bonds, has been restricted to Europe and the US so far. If sentiment about the credit quality of Asian corporates improves there could be note issuance and spread movement. The dealers who have been struggling to cover their positions in the supposedly liquid US and European bond-and-swap markets may be reluctant to try the same approach in Asia, however. With the prospect of more issuance of credit-linked notes on US and European corporates, and maintenance of the wide negative swap-to-bond basis, dealers who are allowed to run proprietary positions—and their insurance company clients—should reap further windfall arbitrage profits. The traders forced to offset deals issued by their structured note departments face further weeks of anxious hedging, however. (Thomson Reuters IFR, May 12, 2001)  

# Questions  

a. What is a credit-linked note (CLN)? Why would investors buy credit-linked notes instead of, say, corporate bonds? Analyze the risks and the cash flows generated by these two instruments to see in what sense CLNs are preferable.   
b. Suppose you issue a CLN. How would you hedge your position? Mention at least two ways of doing this. By the way, why do you need to hedge your position? Be specific.   
c. As a continuation of the previous question, why is whether or not the investors sell their corporate bonds important in this situation?   
d. Now we come to the arbitrage issue. What is the basis of the arbitrage argument mentioned in this reading? Be specific and explain in detail. Show your reasoning using cash flow diagrams.   
e. What does a $0\%$ repo rate for some corporate paper mean? Why is the rate zero?   
f. Finally, why would this create an opportunity for corporate treasurers?  

# MATLAB EXERCISE  

9. (Equity derivatives approach to the valuation of $\mathbf{CoCos})$ ). Consider a $\mathbf{CoCo}$ , denominated in US dollars, with a maturity of 5 years and a face value of $\$1000$ . Assume that the current share price $s$ is $\$100$ and the equity volatility is $20\%$ . The risk-free continuously compounded interest rate is $4\%$ and there are no dividend payments. At the trigger moment a certain fraction $(\alpha)$ of the face value $(N)$ , that is $\alpha N$ is up for conversion. We assume that the conversion $(\alpha=80^{\cdot}$ ) will be triggered when the share price $s$ falls below $\$50$ . The conversion price is equal to the price when the $\mathbf{CoCo}$ is issued. Therefore the conversion ratio CR equals $\alpha^{*}1000/100=8$ . If the bank would like to issue the $\mathbf{CoCo}$ at par, what should be the coupon rate offered to the investors in order for the initial price of the CoCo to be $\$1000?$ Refer to the end of chapter references for details about the equity derivatives approach to the valuation of CoCos.  