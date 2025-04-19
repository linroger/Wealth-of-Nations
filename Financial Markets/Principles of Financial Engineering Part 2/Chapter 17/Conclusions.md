---
tags:
  - '#arbitrage'
  - '#callable_bonds'
  - '#corridor_structures'
  - '#danish_mortgage_bonds'
  - '#hedge_funds'
  - '#interest_rate_volatility'
  - '#libor'
  - '#mortgage_backed_securities'
  - '#prepayment_risk'
  - '#swaptions'
---
# 17.7 CONCLUSIONS  

Swaptions play a fundamental role in economic activity and in world financial markets. This chapter has shown a simple example that was, however, illustrative of how swap measures can be defined and used in pricing swaptions.  

# SUGGESTED READING  

Rebonato (2002) as well as Brigo and Mercurio (2006) are two extensive sources that the reader can consult after reading this chapter. Further references can also be found in these sources. There is a growing academic and practical literature on this topic. Two technical articles that contain references are Andersen and Andreasen (2000) and Pedersen (1999).  

# EXERCISES  

1. Consider the following statement:  

One prop trader noted that cap/floor volatility should be slightly higher than swaptions. Corporates buy caps and investors sell swaptions through callable bonds, said one Londonbased prop trader. The market is structurally short caps and long swaptions.  

a. Swaptions are options to get into swaps in a predetermined data, at a predetermined rate. Explain why, according to this reading, cap/floor volatility should be higher than swaption volatility.   
b. What are some plausible reasons for the market to be structurally short of caps and long on swaptions?   
c. What would this statement mean in terms of hedging and risk management?  

2. The reading below deals with some typical swaption strategies and the factors that originate them. First, read it carefully.  

Lehman Brothers and Credit Suisse First Boston are recommending clients to buy long-dated. swaption vol ahead of the upcoming US Federal Open Markets Committee meeting. In the. trade, the banks are recommending clients to buy long-dated swaption straddles, whose value increases if long-dated swaption vol rises..  

Mortgage servicers and investors are keen to hedge refinancing risk with swaptions as. interest rates fall, meaning that long-dated swaption vol should rise over the next several months, said an official at CSFB in New York..  

The traditional supply of swaption vol has been steadily decreasing over the last year, said (a trader) in New York. Agencies supply vol to dealers mainly via entering swaps with embedded options on the back of issuing callable notes. Over the past year, demand for callable notes has been decreasing due to high interest rate volatility, and lower demand from banks, one of the larger investors in callables. This decreased supply in vol for dealers would point to intermediate- and longer-dated swaption vol rising.  

Lehman is recommending a relative value trade in which investors sell short-dated. swaption volatility, such as options, to enter 10-year swaps in one year, and buy long-dated swaption vol, such as the option to enter a 10-year swap in five years. The trade is. constructed with at-the-money swaption straddles, weighted in such a way as to make this a play on the slope of the vol curve, which at current levels is more inverted compared to historical levels, noted (the trader). Short-dated swaption vol should fall as the Fed's plans become clearer in the next several months, and the market is assuaged concerning the. direction of interest rates. If the Fed cuts interest rates 50 basis points when it meets this week, the market should breathe a sigh of relief, and short-dated vol should fall more than longer-dated vol, he added..  

CSFB recommends buying long-dated vol. The option to enter a five-year swap in five years had a premium of about 570 basis points at press time. At its peak this month, this level was 670 bps, said the official at CSFB. During a similar turning point in the US economy in. 1994--1995, vol for a similar swap was nearly 700 bps. This week's meeting might provide an instant lift to the position. If the Fed cuts rates by more or less than the expected 50 bps, longdated swaption vol could rise in reaction, he added. Even if the Fed cuts by 50 basis points, swaption vol could rise as mortgage players hedge. An offsetting factor here is the fact that following a Fed meeting, short-dated vol typically falls, sometimes dragging longer-dated vol down with it. (Derivatives Week (now part of GlobalCapital) November 2001).  

First, some comments on the mechanics mentioned in the reading. The term Agencies is used for semiofficial institutions such as Fannie Mae that provide mortgage funds to the. banking sector. These agencies sell bonds that contain imbedded call options. For example, the agency has the right to call the bond at par at a particular time. The owners of these bonds are thus option writers. The agency is an option buyer. To hedge these positions they. also need to be option sellers..  

a. Using cash flow diagrams, show the positions that agencies would take due to issuing. callable bonds.   
b. Why would the short-term vol decrease according to the market? Why would long-term vol increase?   
c. What do you think an at-the-money swaption straddle is? Show the implied cash flow diagrams.   
d. If the expectations concerning the volatilities are realized, how would the gains be cashed in   
e. What are the differences between the risks associated with the positions recommended b. CSFB versus the ones recommended by Lehman?  

3. Answer the questions related to the following case study.  

# CASE STUDY: DANISH MORTGAGE BONDS  

Danish mortgage bonds (DMBs) are liquid, volatile, and complex instruments. They are traded in fundamentally sound legal and institutional environments and attract some of the best hedge funds. Here, we look at them only as an example that teaches us something about swaps, swaptions, options, and the risks associated with modeling household behavior.  

# Background Material  

To answer the questions that follow, you need to have a good understanding of these notions and instruments:  

1. Plain vanilla interest-rate swaps   
2. Swaptions   
3. Prepayment risk of an MBS   
4. The relationship between volatility and options   
5. LIBOR and simple LIBOR instruments   
6. Government bond markets versus high-yield bonds.  

# Questions  

Part I  

a. Define the following concepts: MBS, prepayment risk, implicit option, and negative convexity..   
b. Show how you can hedge your DMB positions in the swap and swaption markets and then earn a generous arbitrage. Why would this add liquidity to the Danish markets?.   
c. Show how you can do this using Bermudan options..   
d. Explain carefully if this is true arbitrage. Are there any risks?.  

Part II  

Now consider the second reading.  

e.What is a corridor structure?. f. What does the reading mean by "dislocations"'? g. What are "balance-protected swaps'? h. Explain the purpose of the dislocation trades.  

# Reading 1  

Arbitrageurs Swoop on Danish Mortgage Market  

Yield-starved banks and hedge funds have been scooping up long-dated Danish mortgage bonds, hedging parts of the exposure in the swap and swaption markets, and earning a generous arbitrage (1). But the strategy is not without risk. The structures involved are heavily dependent on complex statistical modelling techniques.  

The Danish mortgage bond market has been undergoing something of a revolution. Securities traditionally bought by Danish pension funds or investment managers are now being snapped up by sophisticated foreign banks and hedge funds. The international players are trying to arbitrage between mortgage, credit- and other interest-rate markets. This activity has also generated significant added volume in the Danish krone and Deutsche mark swap and swaption markets. (1)  

The exact size and nature of the international activity is unknown, but it is believed to be large and growing. "Foreign involvement has gone through the roof," said one structurer at a London-based bank. Banks believed to be at the forefront of activity include Barclays Capital, Bankers Trust, and Merrill Lynch International.  

Outside interest, said market professionals, had been stoked by a decreasing number of profit opportunities in both Europe and the US European investors have seen Southern European bond yields plummet ahead of EMU and have had to look for new sources of return. US hedge funds have turned to Denmark as US mortgage market arbitrage opportunities have started to run dry.  

The European activity has focused on Denmark's mortgage bonds because they are seen as the only real arbitrage alternative (2) to US securities. Seven dedicated private companies, Nykredit, Real Kredit, BRF Kredit, Danske Kredit, Unikredit, Totalkredit, and DLR, continue to issue into a market now worth DKr900bn. Mortgage-backed markets are developing in other sectors of Europe--though slowly. Deutsche Bank last week launched the first German mortgage securitization, Haus I, and ABN AMRO have twice securitized Dutch mortgages (see Asset-Backed Securities).  

# Arbing MBS  

Foreign activity in the Danish mortgage bond market (2) concentrates on the valuation of embedded prepayment clauses-- options that enable the borrower to buy back the bonds at par in order to take out the pre-payment risks associated with the. underlying collateral pool. Derivative professionals analyze pre-payment options in terms of traditional non-mortgage backed swaptions and realize any relative value by trading swaptions against mortgage bonds. (2)  

In one version of the trade, the speculator buys the mortgage bonds and transacts a Bermudan receivers swaption, either in Danish kroner or in (closely correlated) Deutsche marks. This cancels out the prepayment risk and leaves relatively pure interest rate and credit exposure (3).  

Some players go even further and transact both a swap and a swaption against the mortgage bonds, thus creating a true arbitrage (3). They pay fixed on the swap to eliminate the interest rate risk and buy receivers swaptions to offset the inbuilt optionality. They are left with simple LIBOR plus returns and a locked-in profit, subject to credit risk.  

Very similar activity forms the backbone of the US mortgage bond market. Sophisticated US houses such as Goldman Sachs, Morgan Stanley, and Salomon Brothers have for years generated favorable arbitrage profits by examining mortgage bonds in terms of other instruments (3).  

But such potential profits, whether in the US or in Denmark, are subject to considerable risks. First, there are problems involved in pricing long-dated Bermudan swaptions. The product, according to swaption professionals, is sensitive to the tilt and shape of the yield curve-features not captured by simple one-factor swaption pricing models.  

Second, there are also difficulties involved with analyzing the exact size of the prepayment risks. "Prepayment. concerns have consumed mortgage desks in the US for the last few years. And many operations have blown up because they made the wrong assumptions," said one structurer at a prominent Wall Street investment bank..  

"There's always a rumor that one house or another has got their risk modelling wrong," said another New York-. based mortgage derivative professional. The problem for banks and hedge funds is that the size of prepayment is. governed by the size of individual Danish property owners' refinancing activity. And this is a function of both current interest rate conditions and the statistical properties of individual house-owners..  

As a result, the science of valuing mortgage bonds revolves partly on building statistical models that analyze factors other than interest rate market conditions. If rates fall in Denmark, it is likely that some mortgage holders will choose to redeem their high-rate mortgages and take out a new lower-rate loan. This will lead to the borrower prepaying some of its mortgage bonds. But not every homeowner reacts in such a way. Some may never refinance; some have a greater inclination to refinance at certain times of the year; some refinance more in certain parts of the country, and so on.  

Looking to the future, mortgage bond arbitrage activity may soon be spreading to the rest of Europe. The Danish. government is considering cooling the economy by restricting the flow of 30-year issues. (5) This will depress liquidity in the market and make arbitrage more difficult. Meanwhile, investment banks are talking to authorities in Sweden,. Germany, the Netherlands, and the UK about changes to make their own mortgage bond markets more efficient.. (Thomson Reuters IFR May 1998)  

# Reading 2  

This reading refers to Part II of the case study.  

DynaHc I unus Lye disiuLauun Uppui lunlts   
With short-term yields continuing to fall across Europe, money market funds are increasingly targeting higher yields through structured products. Generally, they are lifting returns by selling volatility through corridor structures. (1) More specifically, they are taking advantage of hedge fund-induced market dislocations in Danish mortgage markets and sterling swap spread markets. "In the last few weeks funds have substituted a little credit risk for a bit more market risk," said one market professional at a major European bank. He added that funds saw the increasing confidence in financial markets as an opportunity to generate higher yields from market dislocations.  

In particular, dealers said funds were looking to buy Danish mortgage bonds together with balance-protected swaps (2). The balance-protected swap guarantees the bond buyer the coupons but still leaves the holder with duration risk-- the risk that the instrument will have a shorter duration if prepayment increases. With unswapped Danish mortgage bonds, the holder is exposed to the risk that prepayment rates increase and that coupons levels are reduced..  

In addition to specific dislocation-related trades (3), market professionals said there was a general trend for funds to move away from standard commercial paper and asset-swap investments towards higher-returning, more structured products. Whereas traditional funds buy floating-rate instruments and are only exposed to the credit risk of the. instrument, dynamic money market funds buy instruments that are exposed to interest rate and volatility risks. One structurer last week said the dynamic fund sector had been growing for some time, and added that some European funds had more funds under management in dynamic instruments than traditional instruments. "There's lots of excitement surrounding money market funds and their attempts to churn yield," he said. Typical dynamic money market fund trades are corridors, (4) with popular recent trades being based on two LIBOR rates remaining within the band. One bank structurer said he had recently traded a note that offered higher coupons, provided both US dollar LIBOR and French franc LIBOR remained within set limits. Capital repayment was. guaranteed, but coupon payments were contingent. By buying structures such as these, funds are in effect going short. LIBOR volatility and using the earned premium to enhance their received coupon levels. (5) The size of the enhanced coupon typically depends on the width of the corridor, with extra yields of up to 200 bp generated by a tight corridor and additional yields of around 50 bp delivered by a wider corridor. Dealers said funds preferred to be more cautious. and favored the wider corridor, lower yield products..  

# EXCEL EXERCISES  

4. (Interest Rate Cap Pricing). Write a VBA program to determine the price of an interest rate cap which makes payments if the floating USD LIBOR rate is above the fixed level of $5.00\%$ . Use the data given in the "Cap Pricing Input" worksheet on the chapter webpage for the calculation.   
5. (Interest Rate Floor Pricing). Write a VBA program to determine the price of interest rate floor which makes the payment if the floating USD LIBOR rate is below the fixed level of $4.60\%$ . Use the data given in the \*Floor Pricing Input' worksheet on the chapter webpage for the calculation.  

This page intentionally left blank  

# CREDIT MARKETS: CDS ENGINEERING  

# 18  

# CHAPTER OUTLINE  
