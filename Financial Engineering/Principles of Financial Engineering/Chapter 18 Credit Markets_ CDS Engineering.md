# CREDIT MARKETS: CDS ENGINEERING  

# 18  

# CHAPTER OUTLINE  

# 18.1 Introduction . 620  

18.2 Terminology and Definitions.. 621   
18.2.1 Types of Credit Derivatives . 622   
18.3 Credit Default Swaps . 623   
18.3.1 Creating a CDS.. 625   
18.3.2 Decomposing a Risky Bond .. 625   
18.3.3 A Synthetic. 630   
18.3.4 Using the Contractual Equation . 630   
18.3.4.1 Creating a synthetic CDS .. 630   
18.3.4.2 Negative basis trades. 631   
18.3.5 Measuring Credit Risk of Cash Bonds . 633   
18.3.5.1 Asset swap.. 634   
18.3.5.2 The Z-spread.. 635  

# 18.4 Real-World Complications . 636  

18.4.1 CDS Standardization and 2009 “Big Bang”. 637   
18.4.1.1 Auction hardwiring . 637   
18.4.1.2 Standardization coupons and trading   
conventions. 637   
18.4.1.3 Central clearing . 638  

18.4.2 Restructuring .. 638  

18.4.3 Fixed Recovery CDS 639   
18.4.4 A Note on the Arbitrage Equality.. 640  

# 18.5 CDS Analytics . 640  

# 18.6 Default Probability Arithmetic . 641  

18.6.1 The DVO1’s. 642   
18.6.2 Unwinding a CDS 644   
18.6.3 Upfront Payments and CDS Unwinding.. 646  

# 18.7 Pricing Single-Name CDS . 646  

18.7.1 A Simplified CDS Valuation Example. 646   
18.7.2 Real-World Complications . 647   
18.7.3 Lessons from the GFC for CDS Pricing.. 648   
18.8 Comparing CDS to TRS and EDS . 648   
18.8.1 Total Return Swaps Versus Credit Default Swaps . 648   
18.8.2 EDS Versus CDS. 649   
18.9 Sovereign CDS .. .. 650   
18.10 Conclusions. . 655   
Suggested Reading . 655   
Exercises 655  

# 18.1 INTRODUCTION  

In the previous chapters, we examined the application of financial engineering to forwards, futures, swaps, and options. In this discussion, for simplicity we abstracted away from issues related to credit risk. In the present and the following chapters, we will discuss financial engineering applications related to credit risk, credit derivatives, and credit structured products.  

Credit derivatives have had a revolutionary effect on financial engineering. This is true in (at least) two respects. First, liquid credit derivatives permit stripping, pricing, and trading the last major component in financial instruments, namely the credit risk. With credit derivatives, synthetics for almost any instrument can be built.1 Second, and as important, is the special role played by credit quants and financial engineers. Major broker dealers started organizing the credit market after the development of major instruments such as options, swaps, constant maturity swaps, and swaptions was complete. New knowledge and skills were already in place. Credit markets were developed and instruments were structured using this expertise. At the end, most of the new innovations were put in place in credit markets and in structured credit. Hence, it is important to study the credit instruments, not only because they form a huge market but also because without them many of the new financial engineering techniques would not be understood properly.  

Liquid credit derivative markets extend the creation of synthetics to assets with default risk. They also permit pricing and trading default correlation. With credit default swaps (CDS) and the index products, pricing default risk and default correlation is left to the markets. In contrast, traditional approach to credit risk uses ad hoc estimates of credit curves and tries to model the spread dynamics.  

This chapter deals with three sets of instruments. The first is the fundamental building block, CDS. We will see that CDSs are a natural extension of liquid fixed-income instruments. Next, we move to index products and their tranches. Tranche trading leads to calibration of default correlation and has implications both for finance and for business cycle analysis. Finally, as the third component of credit markets we look at various structured credit products. Structured credit is one area where new innovation takes place at a brisk rate. The chapter will also briefly review credit derivatives other than CDSs.  

# 18.2 TERMINOLOGY AND DEFINITIONS  

First, we need to define some terminology. The credit sector is relatively new in modern finance, although an ad hoc treatment of it has existed as long as banking itself.2 Some of the terms used in this sector come from swap markets, but others are new and specific to the credit sector. The following list is selective.  

1. Reference name. The issuer of a debt instrument on which one is buying or selling default insurance.   
2. Reference asset. The instrument on which credit risk is traded. Note that the credit sector adopts a somewhat more liberal definition of the basis risk. A trader may be dealing in loans but may hedge the credit risk using a bond issued by the same credit.   
3. Credit event. Credit risk is directly or indirectly associated with some specific events (e.g., defaults or downgrades). These are important, discrete events, compared to market risk where events are relatively small and continuous.3 The underlying credit event needs to be defined carefully in credit derivative contracts. The industry differentiates between hard credit events such as bankruptcy versus soft credit events such as restructuring.4 We discuss this issue later in this chapter.   
4. Protection buyer, protection seller. Protection buyer is the entity that buys a credit instrument such as a CDS. This entity will make periodic payments in return for compensation in the event of default. A protection seller is the entity that sells the CDS.   
5. Recovery value. If default occurs, the payoff of the credit instrument will depend on the recovery value of the underlying asset at the moment of default. This value is rarely zero; some positive amount will be recoverable. Hence, the buyer needs to buy protection over and above the recoverable amount. Major rating agencies such as Moody’s or Standard and Poor’s have recovery rate tables for various credits which are prepared using past default data. As a result of the 2009 CDS standardization, the recovery rate is now fixed by convention at $40\%$ . This removed some earlier ambiguity related to the calculation of default probabilities and CDS mark-to-market from the quoted spread.   
6. Credit indices. This is the most liquid part of the credit sector. A credit index is put together by first selecting a pool of reference names and then taking the arithmetic average of the CDS rates for the names included in the portfolio. There are economy-wide credit indices with investment grade and speculative grade ratings, as well as indices for particular sectors. iTraxx for Europe and Asia and CDX for the United States and Emerging Markets are the most liquid credit indices.   
7. Tranches. Given a portfolio of reference names, it is not known at the outset which name will default, or for that matter whether there will be defaults at all. Under these conditions the structure may decide to sell, for example, the risks associated with the first $0-3\%$ of the defaults. In a pool of 100 names, the risk of the first three defaults would then be transferred to another investor. The investor would receive periodic payments for bearing this risk. Similarly, the structurer may sell the risk associated with $3\mathrm{-}6\%$ of the defaults, etc. We discuss credit indices and tranches in detail in Chapter 21.   
8. E-trading. Credit indices are typically traded OTC and, as a result of post-GFC regulation, centrally cleared. Most trading is electronic and certain US trades are required to be executed through an electronic platform called Swaps Execution Facility since October 2013. Exchangetraded futures on credit indices have been launched.5   
9. Standardization. In April 2009, ISDA implemented the standardization of CDS contracts. This event is also referred to as the CDS “Big Bang.” The objective of this initiative was to facilitate CDS settlement by reducing uncertainty and making credit event management more operationally efficient. The standardization had three main parts: auction hardwiring, standardizing trading conventions, and central clearing. We will discuss these in detail in Section 18.4.  

The credit sector has many other sector-specific terms that we will introduce during our discussion.  

# 18.2.1 TYPES OF CREDIT DERIVATIVES  

Crude forms of credit derivatives have existed since the beginning of banking. These were not liquid, did not trade, and, in general, did not possess the desirable properties of modern financial instruments, like swaps, that facilitate their use in financial engineering. Banking services such as a letter of credit, banker’s acceptances, and guarantees are precursors of modern credit instruments and can be found in the balance sheet of every bank around the world.  

Broadly speaking, there are three major categories of credit derivatives.  

1. Credit event-related products make payments depending on the occurrence of a mutually agreeable event. The CDS is the major building block here.   
2. Credit index products that are used in trading portfolios of credit. Obviously, such indices would come with their own derivatives such as options, futures, and forwards.6 An example would be an option written on the iTraxx Europe index.   
3. The structured credit products and the index tranches.  

The difference between the value of risky and riskless debt is typically expressed in terms of a credit spread. The spread is the difference between the (promised) yield on the risky bond and the yield on riskless bonds. Credit risk can be broadly grouped into two different categories: on one hand, credit deterioration. Widening of the underlying credit spread can indicate how credit deteriorates. On the other hand, default risk. This is a separate risk from credit deterioration, although it is certainly correlated with it. Default products trade default risk by separating it from credit deterioration risk.  

As mentioned above, banks have issued letters of credit, guarantees, and insurance. The major distinguishing characteristic of these traditional instruments is that they transfer default risk only. They do not, in particular, transfer market risk or the risk of credit deterioration. Essentially, a payment is made when default occurs. With these products, no compensation changes hands when the underlying credit deteriorates. New credit default products share some of the properties of these old instruments. Some of the new features of credit contracts are as follows:  

1. The payout is dependent on an event rather than an underlying price, similar to insurance products and unlike other derivatives. The dependence of a payoff on an event leads to new techniques and instruments.   
2. The existence of an event leads to the issue of recovery value. How to determine (model) the value of an asset in case of default is now easy. Throughout this chapter, we will use the assumption that the recovery rate is constant and known at a level $R$ .   
3. The process of settling credit contracts is more complex than in other markets. In the case of physical delivery of the underlying, this does not present a major problem. The protection seller will be the legal owner of the defaulted instrument and may take necessary legal steps for recovery. But if the contract is cash-settled, then neither party has legal recourse to the borrower unless the party owns the underlying credit directly. For this reason, the industry prefers physical delivery, and a large majority of default swaps settle this way.  

We will address the additional characteristics of default products when we study CDSs in more detail. In the following section, we will look at the most liquid credit derivatives in more detail and study the financial engineering of CDSs.  

# 18.3 CREDIT DEFAULT SWAPS  

The major building block of the credit sector is the CDS, introduced in the first chapter as an example in the swap family. It is, however, a major category. A typical default swap from the point of view of a protection seller is shown in Figure 18.1. The CDS seller of a particular credit denoted by $i$ receives a preset coupon called the CDS rate. The CDS expires at time $T.$ . The credit protection seller in a CDS is referred to as selling the CDS while the protection buyer buys the CDS. The protection buyer pays a fixed rate (called the CDS rate) periodically until the earlier of default and the fixed maturity date. The CDS spread is denoted by $\mathrm{cds}_{t_{0}}^{j}$ and is set at time $t_{0}$ . A payment of $\mathrm{cd}\mathrm{s}_{t_{0}}^{j}$ δN is made at every $t_{i}$ . The $j$ represents the reference name. If no default occurs until $T_{:}$ , the contract expires without any other payments. On the other hand, if the name $j$ defaults during $[t_{0},\ T]$ , the CDS seller has to compensate the counterparty by the insured amount, $N$ dollars. Against this payment of cash, the protection buyer has to deliver eligible debt instruments with par value $N$ dollars. These instruments will be from a deliverable basket and are clearly specified in the contract at time $t_{0}$ . Obviously, one of these instruments will, in general, be cheapest-to-deliver in the case of default, and all players may want to deliver that particular underlying.  

Note that the discussion so far is simplified since we assume that there is no upfront payment at the initiation of the CDS. This is in contrast to recent market conventions following CDS standardization which have moved from a running spread basis to an upfront basis. We will discuss these  

Credit default swap with default possibility at $t_{3}$ only  

![](353f8cec622f69147f20d4b443d216ae2a756b85ae64263da6274291d9fe6c32.jpg)  

# FIGURE 18.1  

Credit default swap.  

market conventions later in detail. Later in this chapter, we will consider additional properties of the default swap market that a financial engineer should be aware of. At this point, we discuss the engineering aspects of this product. This is especially important because we will show that a default swap will fall naturally as the residual from the decomposition of a typical risky bond. In fact, we will take a risky bond and decompose it into its components. The key component will be the default swap. This natural function played by default swaps partly explains their appeal and their position as the leading credit instrument.  

We discuss the creation of a default swap by using a specific example. The example deals with a special case, but illustrates almost all the major aspects of engineering credit risk. Many current practices involving index CDSs, basket default swaps, synthetic collateralized debt obligations (CDOs) and credit linked notes (CLNs), and other popular credit instruments can be traced to the discussion provided next.7  

Independently, this section can be seen as another example of engineering cash flows. We show how the static replication methods change when default risk is introduced into the picture. Essentially, the same techniques are used. But the creation of a satisfactory synthetic becomes possible only if we add CDSs to other standard instruments.  

# 18.3.1 CREATING A CDS  

The steps we intend to take can be summarized as follows. We take a bond issued by the reference name $j$ that has default risk and then show how the cash flows of this bond can be decomposed into simpler, more liquid constituents. Essentially we decompose the bond risk into two—one depending on market volatility only, the other depending on the reference home’s likelihood of default. CDSs result naturally from this decomposition.  

Our discussion leads to a new type of contractual equation that will incorporate credit risk. We then use this contractual equation to show how a CDS can be created, hedged, and priced in theory. The contractual equation also illustrates some of the inherent difficulties of the hedging and pricing process in practice. At the end of the section, we discuss some practical hedging and pricing issues.  

# 18.3.2 DECOMPOSING A RISKY BOND  

We keep the example simple in order to illustrate the fundamental issues more clearly. Consider a “risky” bond, purchased at time $t_{0}$ , subject to default risk. The bond does not contain any implicit call and put options and pays a coupon of $c_{t_{0}}$ annually over 3 years. The bond is originally sold at par.  

We make two further simplifying assumptions which can be relaxed with little additional effort. These assumptions do not change the essence of the engineering, but significantly facilitate the understanding of the credit instrument. First, we assume that, in the case of default, the recovery value equals the known constant $R$ . Second, and without much loss of generality, we assume that the default occurs only at settlement dates $t_{i}$ . Finally, to keep the graphs tractable we assume that settlement dates are annual, and that the maturity of the bond is $T=3$ years.  

Figure 18.2 shows the cash flows implied by this bond. The bond is initially purchased for 100, three coupon payments are made, and the principal of 100 is returned $i f$ there is no default. On the  

![](60ae1dc471679c0275a9341f31e1ae3e13bcc5e4df8b38e21da8b6f9d3fd1b9e.jpg)  

# FIGURE 18.2  

A defaultable par bond.  

other hand, if there is default, the bond pays nothing. The dependence on default is shown with the fork at times $t_{i}$ . At each settlement date, there are two possibilities and the claim is contingent on these.  

How do we reverse engineer these cash flows and convert them into liquid financial instruments? We answer this question in steps.  

First, we need to introduce a useful trick that will facilitate the application of static decomposition methods to defaultable instruments. We do this in Figure 18.3. Remember that our goal is to isolate the underlying default risk using a single instrument. This task will be greatly simplified if we add and subtract the amount $\left(1+c_{t_{0}}\right)N$ to the cash flows in the case of default at times $t_{i}$ . Note that this does not change the original cash flows. Yet, it is useful for isolating the inherent CDS, as we will see.  

Now we can discuss the decomposition of the defaultable bond. The bond in Figure 18.2 contains three different types of cash flows:  

1. Three coupon payments on dates $t_{1},t_{2}$ , and $t_{3}$ . We strip these fixed cash flows and place them in Figure 18.3b. Although the coupons are risky, we can still extract three default-free coupon payments from the bond cash flows due to the trick used. To get the default-free coupon payments, we simply pick the positive $\left(c_{t_{0}}\right)100$ at the default state for times $t_{i}$ of Figure 18.3a. Note that this leaves the negative $\left(c_{t_{0}}\right)1\mathrm{00}$ in place.   
2. Initial and final payment of 100 as shown in Figure 18.3c. Again, adding and subtracting 100 is used to obtain a default-free cash flow of 100 at time $t_{3}$ . These two cash flows are then carried to Figure 18.3c. As a result, the negative payment of 100 in the default state of times $t_{i}$ remains in Figure 18.3a.   
3. All remaining cash flows are shown in Figure 18.3d. These consist of the negative cash flow $\left(1+\mathbf{Co}_{t_{0}}\right)100$ that occurs in the time $t_{3}$ default state. This is detached and placed in Figure 18.3d.  

The next step is to convert the three cash flow diagrams in Figure $18.3\mathrm{b-d}$ into recognizable and, preferably, liquid contracts traded in the markets. Remember that to do this, we need to add and subtract arbitrary cash flows to those in Figure $18.3\mathrm{b-d}$ while ensuring that the following three conditions are met:  

For each cash flow added, we have to subtract the same amount (or its present value) at the same $t_{i}$ from one of the Figures 18.3b, 18.3c, or 18.3d.   
These new cash flows should be introduced to make the resulting instruments as liquid as possible.   
When added back together, the modified Figure 18.3b d should give back the original bond cash flows in Figure 18.3a. This way, we should be able to recover the cash flows of the defaultable bond.  

This process is displayed in Figure 18.4. The easiest cash flows to convert into a recognizable instrument are those in Figure 18.3b. If we add floating LIBOR-based payments, $L_{t_{i}}$ at times $t_{1},t_{2}$ , and $t_{3}$ , these cash flows will look like a fixed receiver interest rate swap (IRS). This is good because swaps are very liquid instruments. However, one additional modification is required. The fixed receiver swap rate, $s_{t_{0}}$ , is less than the coupon of a par bond issued at time $t_{0}$ , since the bond can default while the swap is subject only to a counterparty risk. Thus, we have  

$$
s_{t_{0}}\leq c_{t_{0}}
$$  

![](c8c88edfbd0db741d4fd15a14e68a60841775a12b3f3e8324f58044ae66f8172.jpg)  

# FIGURE 18.3  

Decomposition of a defaultable bond.  

![](f8eaf432a5ced413709805810cd76e97109b05b6e38e4f3bbf1478cde657cfb3.jpg)  

Remove the spread from the coupon payments...  

(b) Place the spreads on the cash flows  

![](dc301ef788ca46ae8f5c4ed85bb05c24779a0467586d3093a0aa2b8cac8b3c66.jpg)  

# FIGURE 18.4  

Synthetic credit default swap.  

The difference, denoted by $\mathrm{cds}_{t_{0}}$ ,  

$$
\mathrm{cds}_{t_{0}}=c_{t_{0}}-s_{t_{0}}
$$  

is the credit spread over the swap rate. This is how much a credit has to pay over and above the swap rate due to the default possibility. Note that we are defining the credit spread as a spread over the corresponding swap rate and not over that of the treasuries. This definition falls naturally from cash flow decompositions.9  

Thus, in order for the cash flows in Figure 18.4a to be equivalent to a receiver swap, we need to subtract $c_{t_{0}}$ from each coupon as is done in Figure 18.4a. This will make the fixed receipts equal the swap rate:  

$$
c_{t_{0}}-\mathrm{cds}_{t_{0}}=s_{t_{0}}
$$  

The resulting cash flows become a true IRS.  

The next question is where to place the counterparts of the cash flows $c_{t_{0}}$ and $L_{t_{i}}$ that we just introduced in Figure 18.4a. After all, unless the same cash flows are placed somewhere else with opposite signs, they will not cancel out, and the resulting synthetic will not reduce to a risky bond.  

A natural place to put the LIBOR-based cash flows is shown in Figure 18.5. Nicely, the addition of the LIBOR-related cash flows converts the figure into a default-free money market deposit with tenor $\delta$ . This deposit will be rolled over at the going floating LIBOR rate. Note that this is also a liquid instrument.10  

The final adjustment is how to compensate the reduction of $c_{t_{0}}$ ’s by the credit spread $\mathrm{cds}_{t_{0}}$ . Since the first two instruments are complete, there is only one place to put the compensating $\mathrm{cds}_{t_{0}}$ ’s. We add the $\mathrm{cds}_{t_{0}}$ to the cash flows shown in Figure 18.3d, and the result is shown in Figure 18.4b. This is the critical step, since we now have obtained a new instrument that has fallen  

![](cf0ea83fef7616b43aad25b042558044fbfc735788aa2dba1e70251836ca407c.jpg)  
Add LIBOR-based cash flow to figure 18.3c...   
...They become a floating rate money market deposit or a floating rate note (FRN)  

# FIGURE 18.5  

LIBOR cash flows become deposit.  

naturally from the decomposition of the risky bond. Essentially, this instrument has potentially three receipts of $\mathrm{cds}_{t_{0}}$ dollars at times $t_{1},t_{2}$ , and $t_{3}$ . But if default occurs, the instrument will make a compensating payment of 1 1 ct0 100 dollars.11  

To make sure that the decomposition is correct, we add Figures 18.4a,b and 18.5 vertically and see if the original cash flows are recovered. The vertical sum of cash flows in Figures 18.4a,b and 18.5 indeed replicates exactly the cash flows of the defaultable bond.  

The instrument we have in Figure 18.4b is equivalent to selling protection against the default risk of the bond. The contract involves collecting fees equal to $\mathrm{cds}_{t_{0}}$ at each $t_{i}$ until the default occurs. Then the protection buyer is compensated for the loss. On the other hand, if there is no default, the fees are collected until the expiration of the contract and no payment is made. We call this instrument a CDS.  

# 18.3.3 A SYNTHETIC  

The preceding discussion shows that a defaultable bond can be decomposed into a portfolio made up of (i) a fixed receiver IRS, (ii) a default-free money market deposit, and (iii) a CDS. The use of these instruments implies the following contractual equation:  

![](a03e16148484e8b94d7cce57d4fdeafcd448bb8a2950cf0f073fdce4c57f2629.jpg)  

By manipulating the elements of this equation using the standard rules of algebra, we can obtain synthetics for every instrument in the equation. In the next section, we show two applications.12  

# 18.3.4 USING THE CONTRACTUAL EQUATION  

As a first application, we show how to obtain a hedge for a long or short CDS position by manipulating the contractual equation. Second, we discuss the implied pricing and the resulting real-world difficulties.  

# 18.3.4.1 Creating a synthetic CDS  

First, we consider the way a CDS would be hedged. Suppose a market maker sells a CDS on a certain name. In other words, the market maker provides protection or sells the CDS and the credit. How would the market maker hedge this position while it is still on his or her books?  

To obtain a hedge for the CDS, all we need to do is to manipulate the contractual equation obtained above. Rearranging, we obtain the following equation for selling a CDS  

![](6dc90574bdbd5647931302c4a695b7ff99635ea2d03007339e1138e8e0a4687d.jpg)  

Remembering that a negative sign implies the opposite position in the relevant instrument, we can write the formal synthetic for buying a CDS as  

![](a9f59c65063149c4eb1c685ec1eba38c63d096e3e355d347895d984b46d5d2ea.jpg)  

The market maker who sold such a CDS provided protection needs to take the opposite position of the left-hand side of Eq. (18.1). This hedge corresponds to the right-hand side of Eq. (18.6). That is to say, the credit derivatives dealer who sold a CDS will hedge the CDS position by creating a synthetic opposite CDS position. This is achieved by first shorting the risky bond, depositing the received 100 in a default-free deposit account, and contracting a payer swap. This and the sale of the CDS will then “cancel” out. The market maker will make money on the bid ask spread.  

# 18.3.4.2 Negative basis trades  

The second application of the contractual equation is referred to as negative basis trades. Negative basis trades are an important position frequently taken by the traders in credit markets. A discussion of the trade provides a good example of how the contractual equation defining the CDS contracts changes in the real world.  

The contractual equation that leads to the creation of a CDS can be used to construct a synthetic CDS that can be used against the actual one. As we saw in Chapter 7, the basis typically refers to the difference between the spot (cash) price of an asset and its future’s price (derivative). In the credit derivatives market, traders refer to the basis as the difference between the CDS premium of a given bond $\left(\mathrm{cds}_{t_{0}}\right)$ and the bond spread $\left(c_{t_{0}}-s_{t_{0}}\right)$ for the same debt issuer and with similar, if not exactly equal, maturities. Since CDS are derivatives, market participants in credit markets refer to the CDS leg of a negative basis trade as synthetic, and the bond leg as cash.13  

Essentially, with a negative basis trade one would take out a floating rate loan to buy a bond that pays the par-yield $c_{t_{0}}$ while at the same time, buying insurance on the same bond and entering a fixed payer IRS. Clearly such a position has no default risk and makes sense if the coupon minus the bond risk premium $\left(c_{t_{0}}-s_{t_{0}}\right)$ is greater than the CDS premium payments $\left(\mathrm{cds}_{t_{0}}\right)$  

$$
s_{t_{0}}+{\mathrm{cds}}_{t_{0}}<c_{t_{0}}
$$  

This is in fact the case of negative basis. Here, as in the derivation of the contractual equation above, we assume that the rate on the floating rate loan is the same as the LIBOR rate in the IRS. The above interpretation of the negative basis trade follows straight from the contractual equations (18.5) and (18.6).  

In practice, there is sometimes an alternative interpretation of the negative basis trade, since the bond spread can also be measured as the yield on the defaultable bond minus the yield of a Treasury security with a similar maturity. In other words, $s_{t_{0}}$ is taken to be the yield on a Treasury security and not the fixed rate from an IRS. The negative basis trade in that case can be interpreted as shorting the Treasury security and using the cash from this short position to buy a defaultable bond while at the same time taking out insurance purchasing a CDS on the same bond. Since the short finances the long, there is no need for a loan.  

Normally, the insurance on a default risky bond should be “slightly” higher than the credit risk spread one would obtain from the bond. This basis is in general positive. Otherwise, if the bond spread is larger than the CDS premium, then one would buy the bond and buy insurance on it. This would be a perfect arbitrage. This is exactly what a negative basis is. The reading below suggests when and how this may occur.  

# EXAMPLE  

A surge of corporate bond and structured finance issuance this past month has pushed risk premiums on credit default swaps down and those on investment-grade corporate bonds up, nearly erasing the difference between the two asset classes. If this trend continues, it has the potential to create new trading opportunities for investors who can take positions in both bonds and derivatives. Analysts are expecting to see more socalled “negative basis trades” as a result.  

January has been a particularly active month in the US primary corporate bond market, with over \$60 billion issued in investment-grade debt alone. This supply helps to widen risk premiums on corporate bonds. At the same time, there has been no shortage of synthetic collateralized debt obligations (CDOs), which has helped narrow CDS spreads. A corporate credit default swap contract features a seller of protection and a buyer of protection. The seller is effectively long that company’s debt while the buyer is short. When a synthetic CDO is created, dealers sell a certain amount of credit protection, which helps compress CDS risk premiums.  

Typically, credit default swap risk premiums trade at wider levels than comparable bond risk premiums. This is partly because it is easier to take a short position via a CDS rather than a bond. Another reason that CDS risk premiums trade wider is the cheapest-to-deliver option. In the event of a bankruptcy, the seller of protection in a CDS contract will make a cash payment to the buyer in exchange for the bonds of the bankrupt company. However, the seller of protection will receive the cheapest-to-deliver bond from the protection buyer.  

Once the basis between a CDS risk premium and cash bond reverses and becomes negative, it can become advantageous to buy the bond and buy protection through a credit default swap. In such a trade, known as a negative basis trade, the investor has hedged out their credit risk, but is earning more on their bond position than they are paying out on their CDS position.  

(Thomson Reuters IFR, January 2006)  

The above reading also illustrates the terminology used in CDS trades. In the context of IRSs and volatility swaps, we defined the counterparty that was long the swap as the party that paid the first interest rate or volatility. In the contexts of CDS, one can describe the buyer (seller) of a CDS as being short (long) the underlying bond or credit.14 To the extent one refers to the buyer of the CDS as being short, this can be counterintuitive. To avoid any confusion we refer to the buyer (seller) of a CDS as the protection buyer (seller). We will deal with CDOs and their construction and pricing in detail in Chapter 21.  

Negative basis trades become a possibility due to leveraged buyout (LBO) activity as well. During an LBO the buyer of the company issues large amounts of debt, which increases the debt to equity ratio on the balance sheet. Often, rating agencies downgrade such LBO targets several notches which makes LBO candidates risky for the original bond holder. Bond holders, hearing that a company is becoming an LBO target, may sell before the likely LBO; bond prices may drop suddenly and the yields may spike. On the other hand, the CDS rates may move less since LBO is not necessarily going to increase the default probability. As a result, the basis may momentarily turn negative.  

# 18.3.5 MEASURING CREDIT RISK OF CASH BONDS  

Many credit and fixed-income strategies involve arbitraging between cash and synthetic instruments. CDS is the synthetic way of taking an exposure to the default of a single name credit. It is a clean way of trading default. But, cash bonds contain default risk as well as interest rate and curve risk. How would we strip from a defaultable bond yield the component that is being paid due to default risk? In other words, how do we obtain the equivalent of the CDS rate from a defaultable bond in reality?  

This question needs to be answered if we are to take arbitrage positions between cash and derivatives; for example, when we have to make a decision whether cash bonds are too expensive or not relative to the CDS of the same name.  

At the outset the question seems unnecessary, since we just developed a contractual equation for the CDS. We showed that if we combined the cash bond and a vanilla IRS accordingly, then we would obtain a synthetic FRN that paid LIBOR plus a spread. The spread would equal the CDS rate. In other words, take the par yield of a par bond, subtract from this the comparable IRS rate, and get the equivalent of the CDS rate included in the bonds yield.  

This is indeed true, except for one major problem. The formula is a good approximation only if all simplifying assumptions are satisfied and if the cash bonds are selling at par. It is only then that we can straightforwardly put together an asset swap and strip the credit spread.15 If the bond is not selling for par, we would need further adjustments.  

There are two major methods used to obtain a measure of the default risk contained in a bond that does not trade at par. The first is to calculate the asset swap spread and the second is to calculate the so-called Z-spread. We discuss these two practical concepts next and give examples.  

# 18.3.5.1 Asset swap  

An asset swap spread is one way of calculating the credit spread associated with a default risky bond. Essentially it converts the risky yield into a LIBOR plus credit spread, using an IRS.  

In order to create a position equivalent to selling protection, we must buy the defaultable bond and get in a payer IRS. Note that the IRS will be a par swap here, while the bond might be selling for a discount or premium.16 So adjustments are needed in reality since the bond sells either at a discount or premium.17  

In the asset swap, the bond cash flows are discounted using the corresponding zero-coupon swap rates. A spread (called the asset swap spread) is added to (subtracted from) the bond cash flows so that the resulting bond price equals the market price.  

The formula for calculating the asset swap spread is as follows: first use the zero-coupon swap curve to calculate the discount factors. By definition, zero-coupon swap curve discounts are obtained using the corresponding forward rates $f_{t_{j}}$ , and the equation,  

$$
\left(1+s_{t_{0}}^{i}\delta\right)^{i}=\prod_{j=0}^{i-1}\left(1+f_{t_{j}}\delta\right)
$$  

Then calculate the discount factors  

$$
B(t_{0},t_{i})=\frac{1}{\left(1+s_{t_{0}}^{i}\delta\right)^{i}}
$$  

Once this is done, form the annuity factor, $A$ .  

$$
A=\sum_{i=1}^{n}B(t_{0},t_{i})\delta
$$  

Next, calculate the value of the bond cash flows using these factors:  

$$
\tilde{P}_{t_{0}}=\sum_{i=1}^{n}\frac{c_{t_{i}}}{\left(1+s_{t_{0}}^{i}\delta\right)^{i}}
$$  

The asset swap spread is $\tilde{a}_{t_{0}}$ that solves the equation:  

$$
\tilde{P}_{t_{0}}-P_{t_{0}}=\tilde{a}_{t_{0}}\sum_{i=1}^{n}B(t_{0},t_{i})\delta
$$  

Thus, $\tilde{a}_{t_{0}}$ is how much one needs to be paid extra in order to compensate for the difference between the market price and the theoretical price implied by the default-free swap curve. This is the case, since if there were no default risk the value of the bond would be $\tilde{P}_{t_{0}}$ which is greater than the market price $P_{t_{0}}.~\tilde{a}_{t_{0}}$ is a measure that converts this price differential into an additional spread.  

We can show how asset swaps are structured using this last equation. A par bond paying the swap rate $s_{t_{0}}$ satisfies the equation:  

$$
100=\sum_{i=1}^{n}B(t_{0},t_{i})s_{t_{0}}\delta+B(t_{0},t_{n})100
$$  

Thus after adding 100 to both sides, the previous equation can be written as:  

$$
\tilde{P}_{t_{0}}-\left(P_{t_{0}}-100\right)=\left(s_{t_{0}}+\tilde{a}_{t_{0}}\right)\sum_{i=1}^{n}B(t_{0},t_{i})\delta+B(t_{0},t_{n})100
$$  

where the second term on the left-hand side is the upfront payment (receipt) $\mathrm{upf}_{t_{0}}$  

$$
\mathrm{upf}_{t_{0}}=\left(P_{t_{0}}-100\right)
$$  

The latter is negative if the bond is selling at a discount and positive if the bond is at a premium.  

We interpret this equation as follows. Suppose the bond is trading at a discount, then an upfront payment of $\mathrm{upf}_{t_{0}}$ plus an IRS contracted at a rate $s_{t_{0}}+\tilde{a}_{t_{0}}$ is equivalent to the present value of the coupon payments of the bond. In other words, a par swap rate has to be augmented by $\tilde{a}_{t_{0}}$ in order to compensate for the bond’s default risk. Note that during this exercise we worked with risk-free discount factors. This will change with the next notion.  

# 18.3.5.2 The Z-spread  

The so-called Z-spread is another way of calculating the credit spread. It gives a result similar to the asset swap spread but is not necessarily the same.  

In order to calculate the $Z$ -spread, the cash flows generated by a default risk bond will be discounted by the zero-coupon swap rate $s_{t_{0}}$ augmented by a spread $z_{t_{0}}$ , so that the sum equals the market price of the bond. That is to say we have  

$$
P_{t_{0}}=\sum_{i=1}^{n}{\frac{\mathrm{cf}_{i}}{\left(1+\left(s_{t_{0}}^{i}+z_{t_{0}}\right)\delta\right)^{i}}}
$$  

We solve this equation for the unknown $z_{t_{0}}$ . Here $\mathrm{cf}_{t_{i}}$ are the cash flows received at time $t_{i}$ and are made of coupon payments $c_{t_{i}}$ and possibly of the principal.  

According to this, the zero-coupon swap curve is adjusted in a parallel fashion so that the present value of the cash flows equals the bond price. The $Z.$ -spread is the amount of parallel movement in the zero-coupon swap curve needed to do this.  

Note that during the calculation of the $Z$ -spread we worked with a measure of risky discount factors.18 The major difference between the $Z\cdot$ -spread and the asset swap spread arises from the discount rates used. Asset swaps use zero-coupon swap rates whereas $Z\cdot$ -spread uses zero-coupon swap rates plus the Z-spread.  

In this sense, the $Z$ -spread method uses a stream of risky discounts from the whole risky curve to adjust the future cash flows of the bond. The asset swap spread uses a single maturity swap rate to measure the credit risk. Although the $Z$ -spread is better suited to risky discount factors, markets prefer to use the asset swaps as a measure of credit risk. The reason is that the markets do not quote the credit spread as a spread to zero-coupon swap rates. The credit spread is quoted as a spread to a par swap rate because the par swaps are much more liquid than the zero-coupon swaps.  

# 18.4 REAL-WORLD COMPLICATIONS  

Credit markets and credit derivatives trading are inherently more complicated and heterogeneous than most other markets, and one faces an unusual number of real-life complications that theoretical models may not account for. In this section, we look at some of the real-life aspects of CDS contracts.  

Contractual equation (18.6) provides a natural hedge for the CDS and shows one way of pricing it. Similar contractual equations may provide usable hedges and pricing methods for some bread-and-butter instruments with negligible credit risk, but for CDSs these equations are essentially theoretical. The simplified approach discussed above may sometimes misprice the CDS and the hedge obtained earlier may not hold. There may be several reasons why the benchmark spreads on this credit may deviate significantly from the CDS rates. We briefly discuss some of these reasons.  

1. In the preceding example, the CDS had a maturity of 3 years. What if the particular credit had no outstanding 3-year bonds at the time the CDS was issued? Then the pricing would be more complicated and the benchmark spread could very well deviate from the CDS rate.   
2. Even if similar maturity bonds exist, these may not be very liquid, especially during times of high market volatility. Then, it would be natural to see discrepancies between the CDS rates and the benchmark spreads.   
3. The tax treatment of corporate bonds and CDSs is different, and this introduces a wedge between the corresponding spread and the CDS rate.   
4. As mentioned earlier, CDSs result in physical delivery in the case of default. But this delivery is from a basket of deliverable bonds. This means that the CDS contains a delivery option, which was not built into the contractual equation presented earlier.  

In reality, another important issue arises. The construction of the synthetic shown above used a money market account that was assumed to be risk free. In general, such money market accounts are almost never risk free and the deposit-accepting institution will have a default risk. This introduces another wedge between the theoretical construction and actual pricing. This additional credit risk that creeps into the construction can, in principle, be eliminated by buying a new CDS for the deposit-accepting institution.  

The following reading illustrates some of the real-world complications, such as liquidity issues, in the context of credit curve strategies. Standard fixed-income strategy can also be applied in the credit sector.  

Just as in the case of standard fixed-income products, the credit curve allows for curve flattener and curve steepener trades. The idea is self explanatory and follows the fixed-income swap positions applied to the iTraxx curve.  

# EXAMPLE  

Consider Hutchison Whampoa credit-curve flattener via bond-basis play, exploiting value in long end while protecting against any general market deterioration. Buy Hutch 2027 bonds (cheapest on curve), buy 5-year CDS protection. Spread now 82 bps (asset-swap bond spread 131 bps versus CDS at 49 bps). Target compression to 65 bps in coming months. Exit if spread widens to 90 bps.  

Trade primarily a play on long-end bonds: buying protection at shorter end offers hedge in case of bad news on Hutch or general bond downturn. CDS cheaper alternative to selling short-end bond given lack of repo liquidity; using asset swap avoids fixed-rate risk at short end. Spread should slowly grind tighter as more investors switch out of shorter Hutch bonds (2010, 2011, 2014 maturities) where value has already been squeezed out into undervalued longer end.  

This trade can be interpreted as primarily a play on long-end bonds. The reason why the protection is bought at the shorter maturity end is that it offers a hedge in case of bad news on Hutch or general bond downturn in the near term. The reason why a CDS was chosen over shorting a bond is that the CDS is cheaper than the alternative of selling a short-end bond given the relative lack of repo liquidity in the corporate bond market. The use of an asset swap avoids fixed-rate risk at the short end. Spread should slowly grind tighter as more investors switch out of shorter Hutch bonds (2010, 2011, 2014 maturities) where value has already been squeezed out into undervalued longer end.  

# 18.4.1 CDS STANDARDIZATION AND 2009 “BIG BANG”  

On April 8, 2009, a “Big Bang” occurred in the market for CDS contracts and the way in which they are traded. The changes affected both contracts and conventions. The standardization had three main parts: auction hardwiring, standardizing trading conventions, and central clearing. We discuss the main elements of these below.19  

# 18.4.1.1 Auction hardwiring  

ISDA released a supplement and a protocol for credit and succession events in 2009. This led to the creation of regional Determination Committees of dealers and investors to arbitrate when a credit event arises. The committee’s decisions are binding. If a committee decides on a specific credit event an automatic and mandatory CDS auction settlement process takes place.  

# 18.4.1.2 Standardization coupons and trading conventions  

The standardization of North American Corporate CDS saw the introduction of fixed coupons of 100 500 bp. For more than a decade after they were first introduced most single-name CDS contracts traded with coupons in all-running format, that is single-name CDS traded on a running spread or par spread basis which meant that the protection buyer pays for protection by making premium (or spread) payments to the protection seller. Consider a 5-year CDS with a $\$10$ million notional, for example. If we assume that the running spread was $200\mathrm{bp}$ , the protection buyer paid $\$200,000$ a year (typically in quarterly installments).  

Under the running spread convention, no money was exchanged upfront which implied that CDS positions were implicitly leveraged. Following the April 2009 “Big Bang” in the CDS market, the market moved to an points upfront basis. Nowadays contracts have fixed coupons of either $100{\mathrm{bp}}$ or 500 bp. The upfront payments are made at initiation and are equal to the present value of the difference between the current market credit spread and the fixed coupon. As an example, if a contract with a fixed coupon of $100\mathrm{bp}$ is trading at $200\mathrm{bp}$ , the protection buyer will make an upfront payment equal to the present value of the difference between 200 bp and 100 bp. The payment made in the opposite direction of the market spread is below the coupon. Note that the most liquid indices such as CDX and iTraxx have traded on such a points upfront basis for a long time. These market conventions do not require a major modification of CDS pricing approaches since a running spread contract can be viewed as a special case of an upfront and fixed-coupon contract where the upfront is zero and the fixed coupon is equal to the par spread.  

How is the fixed coupon set for CDS indices? When the new series of the index is launched, the fixed coupon, which is also known as a deal spread, since it is expressed as a spread, is determined.  

The move to the points upfront basis for single-name CDS has three advantages. First, it will make netting between single name and index positions easier. Such positions are common as we will see below in the context of index arbitrage trades. Second, the more convenient netting also facilitates the recent move of CDS contracts to central clearing. Third, it also reduces market participant’s exposures to sudden market movements or jump risk which we discuss in more detail in the context of CDS unwinding later.  

# 18.4.1.3 Central clearing  

The changes above facilitated the introduction of central clearing for CDS. As discussed below in the context of unwinding of CDS, central clearing helps reduce counterparty risk in the CDS market. Central clearing for CDS in the United States and Europe began in 2009.  

# 18.4.2 RESTRUCTURING  

Another real-life complication deals with the definition of default itself. Credit events are normally failure to pay and bankruptcy. Any nonpayments of interest or principal would count as the former and any type of formal bankruptcy would count as the latter. In our theoretical engineering, we used this second definition of defaults. Yet, in reality, most single-name CDSs also consider restructuring as an additional default event. Further complicating the picture is the type restructuring, summarized below.  

There are four types of restructuring clauses in the CDS contracts.20 The first is simply norestructuring, No R. In this case, any structuring would not constitute a credit event. It is important to note that credits have come to trade based on market-defined conventions. Normally, high-yield CDS typically trade No R. This is especially true of the CDX indexes in the United States. Markit iTraxx indices trade with Modified-Modified Restructuring except for the Sub-Financials which trade with Restructuring.  

The second type is modified restructuring, Mod $R$ . This creates new conditions for a credit event.21 North American investment grade names trade with a “Modified” restructuring convention. Mod $R$ clauses arose historically for these North American investment-grade credits because of the needs of hedgers of bank loan portfolios.  

The third is the modified modified restructuring, Mod Mod R. In this case, the maturity limits on the deliverable bonds or loans are somewhat different. There is an exception that the bonds (loans) with a maturity of more than 30 months but no more than 60 months can be delivered. European CDS contracts typically traded with a Mod-Mod R convention. The Mod-Mod R convention in Europe stems from the fact that in Europe bankruptcy laws make it difficult for borrows to file in many jurisdictions.  

The fourth type is Old $R$ or Old Restructuring. Old R clauses imply that there is no limit on the maturity of the deliverable obligation and no tranching in the auction postcredit event. Western European sovereign CDS typically contain the clause Old R.  

Obviously CDS contracts with restructuring will have higher CDS spreads than the contracts of the same name, without restructuring. Note the key difference: in a bankruptcy or failure-to-paytype credit event the price differences of deliverable bonds will be relatively small. In a restructuring, the deliverable bonds could have very different values depending on the maturity. The protection buyer has the option to deliver the cheapest bond and hence this option could be very expensive.  

# 18.4.3 FIXED RECOVERY CDS  

CDSs with fixed recovery rates are called Fixed Recovery CDS and are also known as Digital CDS or Binary CDS. In contrast to standard CDSs which require a valuation following a credit event (such as default), digital CDS simply specify payment of a fixed dollar payoff. At inception of the CDS, the payoff amount is agreed based on the severity of the default event. Remember that in a standard CDS the payoff is equal to the notional amount of the CDS minus the postdefault value of the insured assets.  

Digital CDSs have several advantages. They have lower costs, more precise focus on the credit risk, and greater transparency. They will not be subject to difficulties associated with the auctioning process after a default event.  

Essentially, the digital CDSs eliminate the random recovery rates associated with the conventional CDS. In fact, recent events suggest the possibility that the recovery rates associated with CDSs and synthetic CDOs have higher volatility than do recovery rates implied by corporate bond defaults. This led credit derivatives arrangers to offer a range of structural features to lessen this variability. One approach is a fixed recovery rate that is applied to all credit events, as in a digital CDS.  

However, CDS can also have disadvantages. There is a potential moral hazard associated with digital CDS since, in a digital CDS, dealers may have an incentive to more often call soft credit events, events that fall within the ISDA definition of default, but outside that of the rating agencies.  

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

Under these conditions instead of buying credit protection on the issuer, the client would simply short the bond and get in a receiver swap. This will provide the same protection against default, and, at the same time, cost less. So why would clients buy CDS instead? In fact, such inequalities can be caused by many different factors, briefly listed below.  

1. CDS protection is “easy” to buy. On the other hand, it is “costly” to short bonds. One has to first go to the repo market to find such bonds, and repo has the mark-to-market property. With CDS protection, there is no such inconvenience.   
2. Shorting a bond is risky because of the possibility of a short squeeze. If too many players are short the bond, the position may have to be covered at a much higher price.   
3. Some bonds may be very hard to find when a sudden need for protection arises.   
4. Also, as discussed earlier, a delivery option premium is included in the CDS rate.  

These factors may cause the theoretical hedge to be different from the CDS sold to clients. Finally, it should be noted that when the probability of default becomes significant CDS dealers may suddenly move their prices out and stop trading. In more precise terms, the market moves from trading default toward trading the recovery. This is done by quoting the implied upfronts (UPF) instead of spreads.  

# 18.5 CDS ANALYTICS  

We will discuss the main quantitative tools used in CDS pricing and hedging using a 3-year, single-name CDS. The idea is to illustrate the way (risk-adjusted) probability of default is obtained and used. Also, we would like to determine the so-called risky DV01 and risky annuity factors. These factors are used in obtaining hedge ratios during the CDS pricing.  

Let $c d s_{t}$ be rate of a single-name CDS at time $t.$ . Let $R$ denote the fixed recovery rate, and $N$ be the notional amount. As usual $B(t_{0},\ t_{i})$ with $t_{0}<t_{i}$ represents the default-risk free pure discount bond prices at time $t_{0}$ . The bonds mature at times $t_{i}$ and have par value of $\$1$ . First we develop the notion of the default probability ${{p}_{t}}$ at time $t$ .  

# 18.6 DEFAULT PROBABILITY ARITHMETIC  

Modeling the occurrence and the timing of default events can be quite complex. The market, however, gravitates to some simple and tradable notions as we have seen before with options and implied volatility. In this section, we discuss the arithmetic behind the trading of default probability.  

Imagine default as an event that happens at a random time $\tau$ , starting from some time $t_{0}$ . How should we model the probabilities associated with such events?  

We consider the exponential distribution, which can be described as a probability distribution describing the waiting time between events. In this case the event is the default and the waiting time is time until default. Thus we are dealing with modeling the random times until some events occur.  

Let $\tau$ be the occurrence time of a default. The density function of an exponentially distributed random variable, $f(\tau)$ , is given by  

$$
\begin{array}{r}{d(\tau)=\lambda e^{-\lambda\tau}}\end{array}
$$  

This is one way to model default occurrence and timing.  

We see that as the parameter $\lambda$ gets bigger, the probability that the event will occur earlier goes up. Hence this parameter governs when the default event is likely to occur. It is called the intensity associated with the random event.  

The market does not like to use the exponential distribution. Taking the second-order Taylor series approximation of the $f(\tau)$ around the point $\tau_{t_{0}}=0$ we get  

$$
f(\tau)\cong\lambda-\lambda^{2}\tau+\frac{\lambda^{2}\tau^{2}}{2}+o(\tau)^{3}
$$  

Thus the probability that default will occur in a small interval $\Delta$ immediately following $\tau_{t_{0}}$ is approximately given by  

$$
f\left(\tau_{t_{0}}\right)\Delta\cong\lambda\Delta
$$  

Integrating the density $f(\tau)$ from 0 to some $T$ we get the corresponding probability distribution function (PDF)  

$$
\begin{array}{c}{{P(\tau<T)=\displaystyle\int_{0}^{T}\lambda e^{-\lambda\tau}\mathsf{d}\tau}}\\ {{=1-e^{-\lambda T}}}\end{array}
$$  

The first-order Taylor series approximation of the PDF is then given by  

$$
1-e^{\lambda\tau}\cong\lambda\tau
$$  

According to this, the probability that default occurs during a period $\Delta$ is approximately proportional to $\lambda.$ The probability that the event will occur within 1 year is obtained by replacing $T$ in the PDF by 1. We obtain  

$$
P(\tau\leq1)\ \cong\lambda
$$  

Hence the parameter $\lambda$ can be looked at as the approximate constant rate of default probability. The market likes to trade annual default probabilities, assuming that the corresponding probability is constant over various trading maturities. Obviously as time passes and quotes change, the  

corresponding default probability will also change. Hence it is best to use the subscript $t_{0}$ to denote a probability that is written in an instrument at time $t_{0}$ , and use $p_{t_{0}}\cong\lambda_{t_{0}}$ as the default probability written in a contract at inception time $t_{0}$ .  

Looking at this from a different way: suppose $0<\Delta$ is a small time interval. The default event is represented by a random variable $d_{t}$ that assumes the values of 0 or 1, depending on whether during $[t,t+\Delta]$ the credit defaults or not.  

$$
d_{t}={\left\{\begin{array}{l l}{0}&{{\mathrm{No~default}}}\\ {1}&{{\mathrm{Default}}}\end{array}\right.}
$$  

Now we make the assumption that the probability of default follows the equation  

$$
\mathrm{Prob}(d_{t}=1)\cong p_{t}\Delta
$$  

which says that the probability that the credit defaults during a small interval $\Delta$ depends on the length of the interval and on a parameter $p_{t}$ called the “intensity.” According to this, the probability that default occurs by time $t$ will be given by  

$$
\operatorname*{Prob}(\tau<t)=1-e^{-\int_{0}^{t}p_{s}\mathrm{~d}s}
$$  

Assuming $p_{s}$ is constant gives  

$$
\mathrm{Prob}(\tau<\Delta)=1-e^{-p\Delta}
$$  

We have the Taylor series approximation around $t=0$  

$$
e^{-p\Delta}=1-p\Delta+{\frac{1}{2}}p^{2}\Delta^{2}\cdots
$$  

or  

$$
1-e^{-p\Delta}\cong p\Delta
$$  

According to this, the probability that the credit defaults during 1 year will equal $p$ .  

# 18.6.1 THE DVO1’S  

Working with a CDS of maturity $T=3$ years, let $p_{t_{0}}$ be the risk-adjusted default probability associated with a CDS contract of maturity 3 years. We will ignore the $t_{0}$ subscript and write this parameter simply as $p$ . The CDS rate is $\mathrm{cds}_{t_{0}}$ and is observed in the markets. The $\delta_{i}$ is the time as a proportion of the year between two consecutive settlement dates.  

Using this we can write the initial value of the CDS at inception time $t_{0}$ as follows. First, if during the 3 years the name does not default, the present value of the cash flows denoted by $P V_{N D}$ will be  

$$
\mathbf{PV}_{\mathrm{ND}}=\left[B(t_{0},t_{1})(1-p)\delta_{1}\mathbf{c}\mathbf{d}s_{t_{0}}+B(t_{0},t_{2})(1-p)^{2}\delta_{2}\mathbf{c}\mathbf{d}s_{t_{0}}+B(t_{0},t_{2})(1-p)^{3}\delta_{3}\mathbf{c}\mathbf{d}s_{t_{0}}\right]N,
$$  

On the other hand, the name can default during years 1, 2, or 3. The expected present value of the accrued premium denoted by $P V_{A P}$ if a case default event occurs will be  

$$
\begin{array}{r l}&{\mathrm{PV}_{\mathrm{AP}}=[B(t_{0},t_{0}+\Delta_{1})\Delta_{1}p\times\mathrm{cd}\mathsf{s}_{t_{0}}+B(t_{0},t_{1}+\Delta_{2})\Delta_{2}(1-p)p\times\mathrm{cd}\mathsf{s}_{t_{0}}}\\ &{\qquad+B(t_{0},t_{2}+\Delta_{3})\Delta_{3}(1-p)^{2}p\times\mathrm{cd}\mathsf{s}_{t_{0}}]N}\end{array}
$$  

Three comments might help here. First, $\Delta_{i}$ are the parameters that determine the prorated spreads that will be received. If the name defaults right after the settlement date then that particular $\Delta_{i}$ will be close to 0. If the default is right before the next settlement date, $\textstyle\sum_{i}$ will be close to $\updelta_{i}.\L^{22}$ Assuming that the expected default time is the middle of the settlement period gives  

$$
\begin{array}{l}{{\mathrm{PV}_{\mathrm{AP}}}=\displaystyle\frac{1}{2}[B(t_{0},t_{0}+\Delta_{1})\delta_{1}p\times\mathrm{cd}\mathbf{s}_{t_{0}}+B(t_{0},t_{1}+\Delta_{2})\delta_{2}(1-p)p\times\mathrm{cd}\mathbf{s}_{t_{0}}}\\ {~}\\ {\displaystyle~+B(t_{0},t_{2}+\Delta_{3})\delta_{3}(1-p)^{2}p\times\mathrm{cd}\mathbf{s}_{t_{0}}]N}\end{array}
$$  

The $\frac{1}{2}$ comes from the expected default time during an interval $[t_{i},t_{i+1}]$ as given by a uniform distribution on the interval [0,1], the height of the uniform density being $\mathrm{d}t$ .  

The expected value of the compensation for the cash payouts during default will be given by  

$$
\begin{array}{l}{{\mathrm{PV}_{\mathrm{D}}}=B(t_{0},t_{0}\triangle_{1})p(1-R)N+B(t_{0},t_{1}+\triangle_{2})(1-p)p(1-R)N}\\ {\qquad+B(t_{0},t_{2}+\triangle_{3})(1-p)^{2}(1-R)N}\end{array}
$$  

The expected payments and receipts should be equal under the risk-adjusted probability and the CDS rate $\mathrm{cds}_{t_{0}}$ must satisfy the equation  

$$
\mathrm{PV_{ND}=P V_{D}-P V_{A P}}
$$  

Generalizing from the 3-year maturity to $n$ settlement dates, we can write  

$$
\begin{array}{r l}&{\left[\displaystyle\sum_{i=1}^{n}B(t_{0},t_{i})(1-p)^{i}\delta_{i}\mathsf{c}\mathsf{d}\mathsf{s}_{t_{0}}\right]N+\left[\displaystyle\frac{1}{2}\sum_{i=1}^{n}B\left(t_{0},t_{i-1}+\displaystyle\frac{1}{2}\delta_{i}\right)(1-p)^{i-1}p\delta_{i}\mathsf{c}\mathsf{d}\mathsf{s}_{t_{0}}\right]N}\\ &{\quad=\displaystyle\sum_{i=1}^{n}B\left(t_{0},t_{i-1}+\displaystyle\frac{1}{2}\delta_{i}\right)(1-p)^{i-1}p(1-R)N}\end{array}
$$  

Using Eq. (18.36), we now define two important concepts. The first is the risky annuity factor. Suppose the investor receives $\$1$ at all $t_{i}.$ . The payments will stop with a default. For that period the investor receives only a prorated premium. The risky annuity factor, denoted by $\tilde{A}$ , is the value of this defaultable annuity. It is obtained by letting $\mathrm{cds}_{t_{0}}N=1$ on the right-hand side of the expression in Eq. (18.36)  

$$
\tilde{A}=\left[\sum_{i=1}^{n}B(t_{0},t_{i})(1-p)^{i}\delta_{i}\right]+\Biggl[\frac{1}{2}\sum_{i=1}^{n}B\biggl(t_{0},t_{i-1}+\frac{1}{2}\delta_{i}\biggr)(1-p)^{i-1}P\delta_{i}\Biggr]
$$  

The second concept is the risky DV01. This is given by letting the $\mathrm{cds}_{t_{0}}$ change by one basis point.23 The CDS DV01 is also known as a credit delta or spread delta. Often the traders use the $\tilde{A}$ as the risky DV01. Yet, there is a difference between the two concepts. The risky $D V O I$ is how much the value of the CDS changes if one increases $\mathrm{cds}_{t_{0}}$ by 0.0001. In general, this is not going to equal $\tilde{A}$ , although it will be close to it depending on the shape of the curve and the change in spreads. The reason is following the relationship between the probability of default and the CDS spread cdst024  

$$
(1-R)p_{t_{0}}=\mathbf{c}\mathbf{d}\mathbf{s}_{t_{0}}.
$$  

If DV01 is the value of a stream of payments to a $\mathrm{dcds}_{t_{0}}=1$ , then note that we have  

$$
\mathrm{d}p={\frac{1}{(1-R)}}
$$  

In other words, the risky annuity factor $\tilde{A}$ will change due to two factors. Both $\mathrm{cds}_{t_{0}}$ and $p_{t_{0}}$ would change. This means that the risky DV01 is a nonlinear function of $\mathrm{cds}_{t_{0}}$ and that there will be a convexity effect. Most market participants ignore this effect and consider the annuity factor $\tilde{A}$ as a good approximation of DV01. Yet, if the CDS spreads are moving in a volatile environment then the two sensitivity measures would differ.  

# 18.6.2 UNWINDING A CDS  

There are three essential ways to unwind a CDS transaction. The first two are similar to the transactions we routinely see in futures markets. The third is a bit different.  

The most common way of unwinding a CDS position is to offset the position with another CDS or by getting in an offsetting position in the underlying assets.  

A second way to unwind a CDS position is by terminating the contract and pay (or receive from) the counterparty the present value of the remaining CDS cash flows. The trick here is to remember that in a credit event, the cash flows would terminate early, hence, the calculation of the PV should take this into account. This is a good example for the use of risky annuities and risky DV01s.  

Finally, assigning the contract to another dealer is the third way of terminating the contract. Below we discuss an example for the use of DV01 by terminating the contract before maturity. We will calculate the upfront cash payment or receipt.  

# EXAMPLE  

Theoretically, one can unwind a CDS position by getting into an offsetting position or by receiving or paying the PV of the contract. However, in practice, if the CDS in question is substantially in-the-money, then it may be difficult to find a counterparty who will be willing to pay a substantial upfront for a position that can be attained with no upfront cash. This means that the original owner of the contract may have to accept a PV significantly lower to entice the counterparty to take over the position. In other words, there will be a haircut issue. For example:  

An investor bought 3-year ABC protection on October 29, 2007 at 122 bps on $\$100$ notional. Three days later on November 1, the spread is at 140 bps. This means that the original CDS will be in-the-money by an amount.  

If there is no credit event this means an annuity of  

$$
\frac{(140-122)}{10,000}100m=\$180,000
$$  

to be paid annually at times $t_{1},t_{2},t_{3}$ . On the other hand, there may be a credit event and the coupon payments may stop. Assuming that this credit event can occur only at the end of the year there are three possible cash flow paths.  

$$
\{180,180,180\},\{180,180\},\{180\}
$$  

The payments during a default event will approximately cancel each other out assuming that the same cheapest-to-deliver bond is involved during the delivery.  

Suppose the recovery rate is $40\%$ . In order to determine the present value (PV) of these cash flows we use risk-adjusted probabilities of default $p$ obtained from the CDS spread at time $t_{0}$  

$$
p={\frac{142}{10,000(1-0.4)}}=0.023
$$  

Clearly, we also need the corresponding risky zero bond prices, $\tilde{B}(t_{0},t_{i})$ . Suppose they are given by  

$$
\begin{array}{r}{\tilde{B}(t_{0},t_{1})=0.92}\\ {\tilde{B}(t_{0},t_{2})=0.86}\\ {\tilde{B}(t_{0},t_{3})=0.79}\end{array}
$$  

Hence we can write the present value of the coupon payments if no default occurs,  

$$
\begin{array}{r l}&{\mathrm{DV}01=[((\tilde{B}(t_{0},t_{1})+\tilde{B}(t_{0},t_{2})+\tilde{B}(t_{0},t_{3}))(1-p)^{3}}\\ &{\qquad+(\tilde{B}(t_{0},t_{1})+\tilde{B}(t_{0},t_{2}))(1-p)^{2}+(\tilde{B}(t_{0},t_{1}))(1-p))]\times0.18\times(100)}\end{array}
$$  

where $p^{i},i=1,2,3$ are the probabilities associated with each annuity path. Plugging in the numbers we obtain  

$$
\mathrm{DV}01=87.4775
$$  

Note that we needed to use the default risky discounts and the corresponding DV01 because the default will change the timing of the cash flows.  

# 18.6.3 UPFRONT PAYMENTS AND CDS UNWINDING  

As we discussed earlier, in 2009 the single-name CDS also moved to upfront payments.  

# 18.7 PRICING SINGLE-NAME CDS  

The basic approach to pricing CDS is relatively simple, but there are real-world market conventions that have to be taken into account in practice. We first present a simplified CDS pricing example before reviewing market conventions and how they affect pricing.  

# 18.7.1 A SIMPLIFIED CDS VALUATION EXAMPLE  

We can use some of the tools reviewed above to value a CDS. Essentially the approach is to choose the CDS spread cds in such a way as to set the PV of the expected payments by the protection seller (the protection leg) to the PV of the payments made by the protection buyer (the premium leg). This was captured by Eq. (18.35). The two main inputs in this calculation are the survival probabilities and the discount rates. The survival probabilities should be risk-neutral probabilities and they can be obtained from bond prices or asset swaps discussed in Section 18.3. Of course, once market prices or CDS spreads are given, the survival probabilities can also be backed out from CDS markets, similar to how implied volatilities are backed out from option prices.  

Let’s consider the following example of a 5-year CDS with a notional amount $N=\$1$ . We assume that default can occur in the middle of each year. The riskless rate is assumed to be $4\%$ and the yield curve is flat. If one uses the default intensity approach outlined in Section 18.6 with a hazard rate of $\lambda=5\%$ , then one can calculate the probability of survival for each year from Eq. (18.22). The default intensity approach is also referred to as a reduced form approach to modeling default. We distinguish it from the structural approach to default modeling discussed in Chapter 19.  

For the end of the first year, the equation leads to a probability of default (PD) of $P(\tau<T)=$ $1-e^{-\lambda T}=1-e^{-5\%\times1}=0.0488$ . Therefore the probability of survival is $1-0.0488=0.9512$ . We can similarly calculate the probability of survival (PS) until the end of years 1, 2, 3, 4, and 5. This is shown in column 2 of Table 18.1. The second column shows the expected premium payment times the CDS spread cds. It is calculated as $P S\times c d s\times\mathrm{N}$ otional amount.  

The discount factor in this example is based on continuous discounting. The discount factor for year 1 is $e^{-0.04\times1}=0.9608$ . The present value of the expected premium payment at the end of the first year in Table 18.1 is $0.9512\times0.9608\times c d s\times1=0.9139\times c d s$ . Note that this present value does not take into account the accrual payments (Eq. (18.32)).  

We also need to add the accrued premiums in the event of a default. Table 18.2 shows their calculation in the first five columns. The probability of default during year $T+I$ is calculated as the probability of survival until the end of year $T$ minus the probability of survival until the end of year $T+I$ . For example of date $T=I.5$ , we calculate the probability of survival until year $T=l.5$ to be $0.9512-0.9048=0.0464$ . Since we expect to receive the CDS premium cds at date $T=I.5$ , the expected accrual payment is $0.464\times0.5\times c d s$ . If we multiply the expected accrual payments times the discount factor we obtain a present value of all expected accrual payments of $0.1006\times c d s$ .  

<html><body><table><tr><td colspan="4">Table 18.1 Simplified CDS Valuation Example (PV of Premium Leg)</td></tr><tr><td>Time (Years)</td><td>Probability of Survival (PS)</td><td>Expected Payment</td><td>Discount Factor</td><td>PV of Expected Payment</td></tr><tr><td>1</td><td>0.9512</td><td>0.9512 × cds</td><td>0.9608</td><td>0.9139 × cds</td></tr><tr><td>2</td><td>0.9048</td><td>0.9048 × cds</td><td>0.9231</td><td>0.8353 × cds</td></tr><tr><td>3</td><td>0.8607</td><td>0.8607 × cds</td><td>0.8869</td><td>0.7634 × cds</td></tr><tr><td>4</td><td>0.8187</td><td>0.8187 × cds</td><td>0.8521</td><td>0.6977 × cds</td></tr><tr><td>5</td><td>0.7788</td><td>0.7788 × cds</td><td>0.8187</td><td>0.6376 × cds</td></tr><tr><td>Total</td><td></td><td></td><td></td><td>3.8479 × cds</td></tr></table></body></html>  

Table 18.2 Simplified CDS Valuation Example (PV of Protection Leg and Accrued Payments)   


<html><body><table><tr><td>1</td><td>Probability</td><td>Expected Accrual</td><td>Discount</td><td>PV of Expected Accrual</td><td></td><td>Expected</td><td>PV of Expected</td></tr><tr><td>Time (Years)</td><td>of Default (PD)</td><td>Payment 0.0244 × cds</td><td>Factor 0.9802</td><td>Payment 0.0239 × cds</td><td>R 0.4</td><td>Payoff 0.0293</td><td>Payoff 0.0287</td></tr><tr><td>0.5 1.5</td><td>0.0488 0.0464</td><td>0.0232 × cds</td><td>0.9418</td><td>0.0218 × cds</td><td>0.4</td><td>0.0278</td><td>0.0262</td></tr><tr><td>2.5</td><td>0.0441</td><td>0.0221 × cds</td><td>0.9048</td><td>0.0200 ×cds</td><td>0.4</td><td>0.0265</td><td>0.0240</td></tr><tr><td>3.5</td><td>0.0420</td><td>0.0210 × cds</td><td>0.8694</td><td>0.0182 × cds</td><td>0.4</td><td>0.0252</td><td>0.0219</td></tr><tr><td>4.5</td><td>0.0399</td><td>0.0200 × cds</td><td>0.8353</td><td>0.0167 × cds</td><td>0.4</td><td>0.0240</td><td>0.0200</td></tr><tr><td></td><td></td><td></td><td></td><td>0.1006 X cds</td><td></td><td></td><td>0.1208</td></tr></table></body></html>  

If we add the expected accrual payments and the expected premium payments, we obtain a value of $3.8479\times{c d s}+0.1006\times{c d s}=3.9585\times{c d s}$ .  

Finally, lets consider the protection leg payments. The last three columns of Table 18.2 show the calculations. We assume a standard recovery rate of $R=40\%$ . The expected payoff for date $T=0.5$ , e.g., $(1-R)\times N\times0.0488=\bf{0.6}\times1\times0.0488\times0.9802=0.0287$ . One can use programs such as Matlab or VBA to calculate the spread cds that sets the present value of the premium leg and the protection leg equal to each other so that $3.9585\times c d s=0.1208$ . If we do that we find a value of $c d s=0.0306$ or 306 basis points. In other words, given the parameters in this example a CDS spread of 306 basis points would set the present value of the premium leg payments equal to the protection leg payments.  

# 18.7.2 REAL-WORLD COMPLICATIONS  

The above example is very much a simplified and unrealistic treatment of CDS valuation. It ignores many real-world complications such as coupon, day-count conventions, interest rate curves, and upfront payments. CDS premiums are paid typically on a quarterly basis and since the “CDS big bang”, CDS include upfront payments. The choice of the benchmark yield curve and riskless rate is important in practice. The swap yield curve or the LIBOR curve could be used as the basis for the discount factors, but as we will discuss in Chapter 24 the LIBOR curve has some issues due to counterparty risk. White (2013) provides detailed CDS pricing formulae that take into account the ISDA model and real-world conventions.25 Since the CDS market has moved from the spread convention for single-name contracts to a fixed coupon and upfront payments, following standardization it is important for market participants to be able to match the upfront payment amounts and be able to translate upfront quotations to spread quotations and vice versa in a standardized manner. Therefore, ISDA created the CDS Standard model and made the underlying source code for CDS calculations freely available at http://www.cdsmodel.com/cdsmodel/.  

# 18.7.3 LESSONS FROM THE GFC FOR CDS PRICING  

Historically financial innovation has played an important role in economic growth, funding economic activity and risk sharing, but occasionally it also turns sour. Derivatives are one example of financial innovation and derivatives debacles occur with an disturbingly high frequency.26 Such debacles have led to unexpected losses on the part of unsophisticated or misinformed counterparties such as corporates, municipalities, or banks, but sometimes they lead to systemic risk. The insurance company AIG was nearly brought down by losses on CDS positions during the GFC. AIG had a AAA credit rating and was therefore considered a safe counterparty to sell CDS protection. However, the size of its portfolio grew disproportionately large and reached around $\$500$ billion dollars in notional value in 2008. AIG also provided insurance against the default of Lehman Brothers which famously went under in September of 2008. One of the mistakes that AIG made was that, in contrast to the reserves it held for its traditional insurance business, it never correctly reserved for the CDS that it was selling. The irony was that CDS were first developed within a unit of AIG Financial Products which was started in 1987.  

# 18.8 COMPARING CDS TO TRS AND EDS  

To appreciate the nuances of CDS it is helpful to compare them to different but related products.  

# 18.8.1 TOTAL RETURN SWAPS VERSUS CREDIT DEFAULT SWAPS  

We encountered total return swap (TRS) applications in Chapter 4 and discussed equity swaps as an example of TRS principle. A TRS trades default, credit deterioration, and market risk simultaneously. Therefore, unlike CDS, TRS are not a pure credit derivative.  

It is instructive to compare them with CDSs. In the case of a CDS, a protection buyer owns a bond issued by a credit and would like to buy insurance against default. This is done by making constant periodic payments during the maturity of the contract to the protection seller. It is similar to, say, fire insurance. A constant amount is paid, and if during the life of the contract the bond issuer defaults, the protection seller compensates the protection buyer for the loss and the contract ends. The compensation is done by paying the protection buyer the face value of, say, 100, and then, in return, accepting the delivery of a deliverable bond issued by the credit. In brief, CDSs are instruments for trading defaults only.27  

A TRS has a different structure. Consider a bond or any arbitrary risky security issued by a credit. This security makes two types of payments. First, it pays a coupon interest. Second, there will be associated capital gains (appreciation in asset price) and capital losses (depreciation in asset price), which include default in the extreme case. In a TRS, the protection seller pays any depreciation in the asset price during periodic intervals to the protection buyer. Default is included in these payments, but it is not the only component. In general, assets gain or lose value for many reasons, and this does not mean the issuer has defaulted or will default. Nevertheless, the protection seller will compensate the protection buyer for these losses as well.  

However, in a TRS, the protection seller’s payments will not stop there. The protection seller will also make an additional payment linked to LIBOR plus a spread.  

The protection buyer, on the other hand, will make periodic payments associated with the appreciation and the coupon of the underlying asset. Normally, asset prices appreciate and pay coupons more often than decline, but this is compensated by the LIBOR plus any spread received.  

The TRS structure is equivalent to the following operation. A market participant buys an asset, $S_{t},$ and funds this purchase with a LIBOR-based loan. The loan carries an interest rate, $L_{t_{i}}$ , and has to be rolled over at each $t_{i}$ . The market participant is rated A and has to pay the credit spread $d_{t_{0}}$ known at time $t_{0}.\ S_{t}$ has periodic (coupon) payouts equal to $c$ . The market participant’s net receipts at time $t_{i+1}$ would, then, be the following:  

$$
(\Delta S_{t_{i+1}}+c)-(L_{t_{i}}+d_{t_{0}})S_{t_{0}}\Delta
$$  

where $\Delta S_{t_{i+1}}$ is the appreciation or depreciation of the asset price during the period, $\Delta=[t_{i},~t_{i+1}]$ .   
The $c$ is paid during $\Delta$ . The payments are in-arrears.  

A TRS swap is equivalent to this purchase of a risky asset with LIBOR funding. Except, in this particular case, instead of going ahead with this transaction, the market participant can simply sign a TRS with a proper counterparty. This will make him or her a protection seller. Banks may prefer these types of TRS contracts to lending to market practitioners.  

# 18.8.2 EDS VERSUS CDS  

Equity default swaps (EDS) are strictly speaking equity derivatives, but they have similarities with CDS. EDS have been marketed by dealers with mixed success thus far.28 The EDS emulate CDS. In a CDS, the reference asset is a bond, and the protection is provided against the default of other credit event. In an EDS, the reference asset is a company’s stock, and protection is provided against a dramatic decline in the company’s stock price.  

An EDS is “exercised” when a company’s stock price $S_{t}$ falls below a prespecified barrier $H$ . Normally this barrier will be $30\mathrm{-}40\%$ below the current stock price level. If $S_{t}{<}H$ happens, then an “equity event” similar to a credit event takes place.  

If a credit event occurs, the EDS terminates, and the protection seller makes a specified payment to the protection buyer. The payment is calculated as  

$$
\mathrm{notionalamount}(1-\mathrm{recoveryrate})
$$  

Note, however, that hitting an equity barrier $H$ , no matter how distant it is, is more likely than a credit event. After all, a company’s stock price can fall dramatically without the company going bankrupt. An EDS shares similarities with CDS and with options. An EDS is similar to a deep outof-the-money, long-dated American digital put. However, there is a difference in that the option premium is paid in installments and these stop when the option is exercised. A better analogy is between the EDS and the CDS. The reason is that typically when a CDS is triggered the stock price of the underlying typically dramatically collapses and might fall to zero at the same time as the reference asset, that is the bond, drops in value. One of the advantages of EDS over CDS is that the trigger events are less ambiguous. It is generally clear whether a stock price has fallen below a certain threshold, while in a CDS there is some ambiguity about what constitutes a credit event or default, as we will see in our discussion of sovereign CDS below, for example.  

Again, similar to CDSs, dealers can, and have tried to, put together CDOs of the EDSs. Such CDOs can get rated. Normally, however, it is difficult for dealers to get a big enough tranche of such a CDO rated higher than A.29  

It is worth adding that the EDS structure is very similar to a deep out-of-the-money put option written on the stock. In both cases there is a barrier, namely the strike price in the case of the option, such that the option buyer receives a cash payment. The major difference is perhaps the expiration date of the EDS which can be much longer.  

# 18.9 SOVEREIGN CDS  

The cash flow engineering approach that we used to create synthetic CDS in Section 18.3 applies to any reference asset. In a corporate CDS, the reference asset is a corporate bond. In a sovereign CDS, the reference asset is sovereign debt. There are some special considerations associated with sovereign CDS which we want to highlight and therefore we discuss sovereign CDS in this section. In economic terms, sovereign CDS are also becoming more important. In terms of gross notional amounts the sovereign CDS market in 2012 was $11\%$ of the whole CDS market, but the sovereign CDS market has been growing while the single-name CDS market has been declining since the GFC. We discuss reasons for the decline in the single-name CDS market in Chapters 21 and 22.  

A sovereign CDS can in principle protect investors against losses on sovereign debt if a country restructures or defaults on its debt. Sovereign CDS have four main uses: hedging, speculation, basis trading, and credit risk management.  

First, sovereign CDS are also used as proxy hedges for other types of credit risk, such as financial and nonfinancial corporate bonds. An investor that holds Italian government bonds can buy an Italian sovereign CDS to hedge the credit risk in the Italian government bond.  

Second, sovereign CDS can be used to speculate. A market participant could buy or sell sovereign CDS on a naked basis, that is without an offsetting position in the underlying reference asset. A hedge fund, for example, with a view that Japanese sovereign credit ratings will improve could buy a sovereign CDS on Japanese government debt. CDS differ from traditional insurance in that in principle a purchase of a CDS does not need to own the reference asset. Expressing a view about the evolution of a country’s credit rating could be achieved by using other financial markets such as cash bond markets or interest rate futures, but these alternatives reflect other types of risk in addition to sovereign credit risk.  

Naked CDS positions are banned in some markets. As a result of the rising influence of the sovereign CDS market, concerns have been voiced about whether speculative uses of sovereign CDS could be destabilizing. Since 2012, as part of the EU regulation “Short Selling and Certain Aspects of Credit Default Swaps” naked CDS on the debt of European Economic Area countries are banned. Liquidity in the sovereign CDS market had started to decrease ahead of the ban, but proving that the ban caused liquidity to decrease is made difficult by various other events and policy announcements at the same time. Some market participants have closed even covered CDS positions following the ban because of ambiguity in the hedge rules in the regulation. There are alternative instruments that can be used to hedge sovereign risk such as some corporate CDS contracts and bond futures but these proxy hedges are likely to be more expensive and less precise.  

Third, as we saw in Section 18.3, CDS, together with IRSs and FRNs can be used to replicate the cash flows of the underlying asset. Therefore, sovereign CDS can be used for basis trading, that is exploiting mispricing between the sovereign CDS and the underlying government bond. If the sovereign CDS spread is narrower than the credit spread of the underlying debt, that is if the basis is negative, arbitrageurs may be able to profitably buy the debt and buy CDS protection.  

Fourth, sovereign CDS are important credit risk management tools and sovereign CDS premia are widely used as market indicators of credit risk. Figure 18.6 shows an example of how CDS spreads can be used as risk and default probability indicators. The figure shows a screenshot from Bloomberg which shows the implied 1-year default probability in percent for a range of reserve currency and nonreserve currency sovereign credits on July 2, 2014. The default probabilities are derived from the CDS spreads with are reported in the columns to the right. The 5-year CDS spread for Greece is 455 bps or $4.55\%$ and the implied annual default probability for Greece on that day is $9.5\%$ . Note however that this probability is lower than the highest probability that had been reached historically, which according to the screenshot was around $27\%$ .  

Dealer banks act as market makers and dominate the sovereign CDS market on the buy and the sell side. The banks’ exposure to sovereign risk arises from their direct holdings of sovereign debt as well as counterparty credit risk associated with their derivatives trades with countries. Historically, sovereigns did not post collateral on a mark-to-market basis related to their OTC derivatives positions in interest rate and cross-currency derivatives for example. As a result dealer  

![](7a4ee08de96439b035542368b3dbea4b44d0790df10a0993f8ff0cedb5319fc0.jpg)  

# FIGURE 18.6  

Sovereign CDS and implied default probabilities.  

banks have counterparty risk exposure on these OTC contracts in which sovereigns are counterparties and sovereign CDS can be used to hedge the counterparty risk.  

Argentina is an interesting name to be associated with the CDS market because of the large size of the default and the ongoing legal proceedings regarding Argentina’s debt. The following deals with Argentina, where the CDS rate was around $40\%$ for 1 year around the default period.  

# EXAMPLE  

One-year Argentina credit default swap mid-levels hit 4,000 bp late last week, though the highest trade in   
the sovereign is thought to have been a one-year deal at 2,350 bp early in the week. Derivatives market-makers were cautiously quoting default swap prices on an extremely wide bid/offer   
spread (the two-year Argentina mid rose to around 3,900 bp), but mostly concentrated on balancing cash   
market hedges, which did not prove easy. Dealers who have sold protection also consulted their lawyers to plot tactics in the event that Argentina   
defaults, or restructures its debt. It is likely that more than US\$1bn of credit default protection on Argentina   
has traded in the last few years, which could result in the biggest default swap payout yet, if there is a  

clear-cut default or debt restructuring. There is plenty of scope for disagreement on whether or not the payout terms of swaps have been met, however, depending on how any debt restructuring is handled by the Argentine authorities.  

Pricing default swaps when a payout trigger could be hours away is an art, not a science. Late last week traders were working from the closing price on Thursday of Argentina’s FRBs of 63.5, which was the equivalent of 3,060 bp over LIBOR, then adding a $30\mathrm{-}40\%$ basis for the theoretical risk of writing a default swap, as opposed to the asset swap value of a bond trade. For much of this year, traders have been using a default against asset swap basis of around $10\%$ of the total spread for deals in Latin American sovereigns.  

(Thomson Reuters IFR, July 2001)  

Following the events described in the reading above, Argentina defaulted on a total of USD 93 billion of external debt on December 26, 2001. The following article summarizes the lengthy legal proceedings and impact on CDS markets in the subsequent years up to 2014 and provides valuable lessons.  

# EXAMPLE  

ISDA Asked If Event Clause Triggered on Argentina Debt Swaps  

The International Swaps & Derivatives Association said it was asked to rule whether a clause in creditdefault swaps on Argentina has been triggered after the government said it won’t make bond interest payments.[. . .]  

Argentina is negotiating with creditors, who refused to accept restructured debt after its default in 2001, following a U.S. Supreme Court ruling last week requiring full payment. The ruling blocks interest payments on restructured bonds until holdout creditors are paid. President Cristina Fernandez de Kirchner’s government said it’s unable to pay all claims.[. . .]  

The government owes $\$900$ million in interest on June 30 for bonds issued as part of restructurings in 2005 and 2010. The New York judge’s order requires Argentina to pay creditors, including billionaire Paul Singer’s Elliott Management Corp., $\$1.5$ billion on defaulted debt before it’s allowed to make the interest payments.  

Fernandez says the nation could owe as much as \$15 billion if forced to pay all holders of defaulted bonds on the same terms, which would deplete more than half of its foreign reserves.[. . .]  

The government defaulted on a record $\$95$ billion debt in 2001, replacing the defaulted bonds with new ones at a discount in two restructurings. Holdouts have fought for full payment on the defaulted bonds. Argentina had vowed never to pay the holdouts, calling them “vultures” and refusing to pay U.S. court judgments in their favor.  

Argentina’s debt is the world’s most expensive to insure, according to data compiled by Bloomberg. It cost $\$3.4$ million upfront and $\$500,000$ annually to protect $\$10$ million of Argentina’s debt for five years, signaling a 64 percent chance of default within that time, according to CMA.  

There were 2,602 credit-default swaps contracts covering a net \$906 million of Argentina’s debt outstanding as of June 13, according to the Depository Trust & Clearing Corp.  

(Bloomberg, June 23, 2014)  

The legal wrangling regarding the payment of creditors by Argentina in $2013-2014$ led to gyrations in the CDS spread and implied default probability. Figure 18.7 shows the annual probability of default for Argentina implied by 5-year CDS spreads and under the assumption of a $40\%$ recovery rate. In the  

![](8cda0360ed9591fc7209942340354b6d5aea287fde1e6abf731c3418bc8479a2.jpg)  

# FIGURE 18.7  

Argentina probability of default and CDS spread.  

figure, the dashed line and $y$ -axis on the right show the default probability while the solid line and y-axis on the left show the CDS spread. In August 2014, ISDA determined that Argentina’s failure to pay its sovereign bonds was a credit event, triggering a payout to holders of credit default swap.  

The sovereign debt stress in the euro area following the GFC has again raised concerns about the reliability and usefulness of sovereign CDS. Between June 2005 and April 2013, there were 103 CDS credit events but only two sovereign CDS credit events in which settlements were publicly documented. The March 2012 Greece debt exchange was an example that highlighted the potential complexity of sovereign CDS credit event triggering and settlement. About h200 million in Greek government bonds (GGBs) were exchanged against new GGBs making this the largest sovereign restructuring event in history. European governments had concerns about the effect of a Greek debt default on European banks. Therefore, governments attempted to delay the triggering of the associated credit event. These actions however undermined confidence in the CDS market and raise questions about the effectiveness of sovereign CDS. The effectiveness of CDS protection depends on two main things. The first is whether the event responsible for the losses triggers the CDS payout. The second is whether the payout offsets the losses if the CDS is triggered. The April 2013 IMF Global Financial Stability report notes that it is a fortunate coincidence that the new GGBs were trading at about $22\%$ of par going into the CDS settlement, which was the same price that the old GGBs were trading at before the exchange. This implied that the settlement resulted in sovereign CDS payouts roughly in line with losses incurred in the debt exchange. Since this result for a fortunate coincidence for debt and CDS holders, the associated uncertainty led to a rethinking of alternative settlement mechanisms such as delivering a package of new instruments in proportion to the instruments that they replace.  

# 18.10 CONCLUSIONS  

This chapter is only a very brief introduction to this important class of credit derivatives. We saw that CDS play a key role in completing the methodology of financial engineering. We developed a contractual equation for CDS and applied it to negative basis trades. We discussed real-world complications related to recovery clauses and drew lessons about the importance of credit event triggers and settlement following recent sovereign defaults and sovereign CDS triggers.  

# SUGGESTED READING  

Several recent books deal with this new sector. For a good theoretical background and some empirical work, Duffie and Singleton (2003) is very useful. Bielecki and Rutkowski (2001) is more mathematically involved, but excellent. The Barclays Capital Standard Corporate CDS Handbook 2010 provides a good summary of the main changes in the CDS market after the GFC. The monthly Risk publication, Credit, is also good reading on market activity. We only covered a simple example of CDS pricing in this chapter. For a detailed description of CDS pricing under real-world market conventions see White (2013). Hull (2014) and O’kane (2008) are also good references. The classic reading here is Merton (1974). Giesecke (2002) is a good survey on pricing. The reader should also consult the very good source, Scho¨nbucher (2003). The April 2013 IMF Global Financial Stability Report reviews recent issues in sovereign CDS markets.  

# EXERCISES  

1. This exercise deals with value-at-risk calculations for credit portfolios. Using the data on a corporate financial statement, answer the following questions: a. How would you calculate the default probabilities? b. How can one obtain the migration matrix for a credit? c. How can one obtain the joint migration probabilities for the relevant credits in a bank’s portfolio?  

2. You are given two risky bonds with the following specifications: Bond A  

a. Par: 100   
b. Currency: USD   
c. Coupon: 10   
d. Maturity: 4 years   
e. Callable after 3 years   
f. Credit: AA   
Bond B   
a. Par: 100   
b. Currency: EUR   
c. Coupon: LIBOR $^+78$ bp   
d. Maturity: 5 years   
e. Credit: AAA  

You will be asked to transform Bond A into Bond B by acquiring some proper derivative contracts. Use cash flow diagrams and be precise.  

Show how you would use a currency swap to switch into the right currency. Show how you would use an IRS to switch to the needed interest rate. Is there a need for using a swaption contract? Can the same be accomplished using forward caps and floors? Finally, show two ways of using credit derivatives to switch to the desired credit qualit  

3. Consider the CDS pricing example in Section 18.7. Assume that hazard rate is $3\%$ instead of $5\%$ but all other input parameters remain the same. Calculate the value of the CDS by finding the CDS spread cds that sets the expected present value of the protection leg payments equal to the expected present value of the premium leg payments as in the text.  

4. In the CDS pricing example in the text we assumed a hazard rate to derive the CDS spread and to price the contract. Now assume that the hazard rate is unknown, but assume that you can observe a CDS spread of 200 bp in the market for this credit. The recovery rate is still $40\%$ , the maturity is 5 years, the riskless rate is $4\%$ and the yield curve is flat. Assumptions about the timing of defaults and accrued premia are unchanged. Calculate the implied hazard rate.  

5. a. Consider the following quote from Reuters: The poor correlation between CDS and cash in Swedish utility Attentat (VTT.XE) is an anomaly and investors can benefit by setting up negative basis trades, says ING. 5-yr CDS for instance has tightened by approx. 5 bp since mid-May while the Attentat 2010 is actually approx. 1 bp wider over the same period.  

Buy the 2010 bond and CDS protection at approx midas $+27$ bp. (MO)  

i. Display this position on a graph with cash flows exactly marked.   
ii. Explain the logic of this position.   
iii. Explain the numbers involved. In particular, suppose you have 100 to invest in such a position, what would be the costs and expected returns?   
iv. What other parameters may have caused such a discrepancy?  

6. Consider the following news from Reuters: 1407 GMT [Dow Jones] LONDON—According to a large investment bank investors can boost yields using the following strategies: a. In the strategy, sell 5-yr CDS on basket of Greece $(9b p)$ , Italy $(\delta.5b p)$ , Japan (4 bp), Poland (12 bp), and Hungary (16 bp), for $34$ bp spread. Buy 5-yr protection on iTraxx Europe at 38 bp to hedge. Trade gives up 4 bp but will benefit if public debt outperforms credit. b. To achieve neutral or positive carry, adjust notional amounts—for example in the first trade, up OECD basket’s notional by $20\%$ for spread neutral position. c. Emerging market basket was $65\%$ correlated with iTraxx in 2005, hence use the latter a hedge. i. Explain the rationale in item (a). In particular, explain why the iTraxx Xover is used as a hedge.  

ii. Explain how you would obtain positive carry in (b). iii. What is the use of the information given in statement (c)?  

7. Consider the following news from Reuters: HVB Suggests Covered Bond Switches 0843 GMT [Dow Jones] LONDON—Sell DG Hyp $4.25\%$ 2008s at 6.5 bp under swaps and buy Landesbank Baden-Wuerttemberg(LBBW) $3.5\%$ 2009s at swaps-4.2 bp, HVB says. The LBBW deal is grandfathered and will continue to enjoy state guarantees; HVB expects spreads to tighten further in the near future. a. What is a German Landesbank? What are their ratings? b. What is the logic behind this credit strategy? c. Can you take the same position using CDSs? Describe how.  

8. Explain the logic behind the two following strategies using cash flow diagrams.  

a. WestLB mortgage Pfandbriefe trade too tight. Sell the WestLB $3\%$ 2009s at 5.4 bp under swaps and buy the zero risk weighted Land Berlin $2.75\%$ 2010s at 2.7 bp under. (TMA)   
b. The following quote deals with implied forward rates in the credit sector. Using proper diagrams explain what the trade is. Implied forward CDS levels look high because shorter-dated CDS are currently too cheap to 5-year, says BNP Paribas. Using the iTraxx Main curve as reference gives a theoretical 3-year forward curve that shows $\boldsymbol{\mathscr{\sigma}}$ -month and $\boldsymbol{{\mathit{1}}}$ -year CDS both at 60 bp. “In 3-years time, we find that 6-month and $\jmath$ -year CDS are very unlikely to be trading above 60 bp.” Take advantage through the 3-5-10-year barbell, buying iTraxx 3-year at 20.75 bp for EUR20M, selling iTraxx 5-year at 38 bp for EUR25M, and buying iTraxx 10-year at 61.25 bp for EUR7M. The trade has a yearly carry of EUR32,000 for a short nominal exposure of EUR2M.  

This page intentionally left blank  