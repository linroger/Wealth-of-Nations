# 18.3 CREDIT DEFAULT SWAPS  

The major building block of the credit sector is the CDS, introduced in the first chapter as an example in the swap family. It is, however, a major category. A typical default swap from the point of. view of a protection seller is shown in Figure 18.1. The CDS seller of a particular credit denoted by $i$ receives a preset coupon called the CDS rate. The CDS expires at time. $T.$ The credit protection seller in a CDS is referred to as selling the CDS while the protection buyer buys the CDS. The. protection buyer pays a fixed rate (called the CDS rate) periodically until the earlier of default and. the fixed maturity date. The CDS spread is denoted by. $\mathrm{cds}_{t_{0}}^{j}$ and is set at time $t_{0}$ . A payment of $\mathrm{cds}_{t_{0}}^{j}$ 8N is made at every $t_{i}$ The $j$ represents the reference name. If no default occurs until. $T_{:}$ the contract expires without any other payments. On the other hand, if the name $j$ defaults during $[t_{0},~T]$ the CDS seller has to compensate the counterparty by the insured amount,. $N$ dollars. Against this payment of cash, the protection buyer has to deliver eligible debt instruments with par value $N$ dollars. These instruments will be from a deliverable basket and are clearly specified in. the contract at time $t_{0}$ . Obviously, one of these instruments will, in general, be cheapest-to-deliver. in the case of default, and all players may want to deliver that particular underlying..  

Note that the discussion so far is simplified since we assume that there is no upfront payment at the initiation of the CDS. This is in contrast to recent market conventions following CDS standardization which have moved from a running spread basis to an upfront basis. We will discuss these  

Credit default swap with default possibility at $t_{3}$ only  

![](images/a9f6263f8e609016bc8f6976b1829c66ef0c9f87e044140e31c7c31dd80c8141.jpg)  

# FIGURE 18.1  

Credit default swap.  

market conventions later in detail. Later in this chapter, we will consider additional properties of the default swap market that a financial engineer should be aware of. At this point, we discuss the engineering aspects of this product. This is especially important because we will show that a default swap will fall naturally as the residual from the decomposition of a typical risky bond. In fact, we will take a risky bond and decompose it into its components. The key component will be the default swap. This natural function played by default swaps partly explains their appeal and their position as the leading credit instrument.  

We discuss the creation of a default swap by using a specific example. The example deals with a special case, but illustrates almost all the major aspects of engineering credit risk. Many current. practices involving index CDSs, basket default swaps, synthetic collateralized debt obligations. (CDOs) and credit linked notes (CLNs), and other popular credit instruments can be traced to the discussion provided next.'  

Independently, this section can be seen as another example of engineering cash flows. We show how the static replication methods change when default risk is introduced into the picture.. Essentially, the same techniques are used. But the creation of a satisfactory synthetic becomes. possible only if we add CDSs to other standard instruments..  

# 18.3.1 CREATING A CDS  

The steps we intend to take can be summarized as follows. We take a bond issued by the reference.   
name $j$ that has default risk and then show how the cash flows of this bond can be decomposed into simpler, more liquid constituents. Essentially we decompose the bond risk into two-one depending.   
on market volatility only, the other depending on the reference home's likelihood of default. CDSs.   
result naturally from this decomposition..  

Our discussion leads to a new type of contractual equation that will incorporate credit risk. We then use this contractual equation to show how a CDS can be created, hedged, and priced in theory. The contractual equation also illustrates some of the inherent difficulties of the hedging and pricing process in practice. At the end of the section, we discuss some practical hedging and pricing issues.  

# 18.3.2 DECOMPOSING A RISKY BOND  

We keep the example simple in order to illustrate the fundamental issues more clearly. Consider a "risky" bond, purchased at time $t_{0}$ subject to default risk. The bond does not contain any implicit call and put options and pays a coupon of $c_{t_{0}}$ annually over 3 years. The bond is originally sold at par.  

We make two further simplifying assumptions which can be relaxed with little additional effort. These assumptions do not change the essence of the engineering, but significantly facilitate the understanding of the credit instrument. First, we assume that, in the case of default, the recovery. value equals the known constant $R$ . Second, and without much loss of generality, we assume that the default occurs only at settlement dates $t_{i}$ . Finally, to keep the graphs tractable we assume that. settlement dates are annual, and that the maturity of the bond is $T=3$ years.  

Figure 18.2 shows the cash flows implied by this bond. The bond is initially purchased for 100, three coupon payments are made, and the principal of 100 is returned. $i f$ there is no default. On the  

![](images/c61f3646b921c90a766c9d30a64112e9b6fa0ede021d8f0398c4f18e0d36e85a.jpg)  

# FIGURE 18.2  

A defaultable par bond.  

other hand, if there is default, the bond pays nothing. The dependence on default is shown with the fork at times $t_{i}$ At each settlement date, there are two possibilities and the claim is contingent on these.  

How do we reverse engineer these cash flows and convert them into liquid financial instruments? We answer this question in steps.  

First, we need to introduce a useful trick that will facilitate the application of static decomposition. methods to defaultable instruments. We do this in Figure 18.3. Remember that our goal is to isolate the underlying default risk using a single instrument. This task will be greatly simplified if we add and subtract the amount $\left(1+c_{t_{0}}\right)N$ to the cash flows in the case of default at times. $t_{i}$ Note that this does not change the original cash flows. Yet, it is useful for isolating the inherent CDS, as we will see.  

Now we can discuss the decomposition of the defaultable bond. The bond in Figure 18. contains three different types of cash flows:  

1. Three coupon payments on dates $t_{1},t_{2}$ , and $t_{3}$ . We strip these fixed cash flows and place them in Figure 18.3b. Although the coupons are risky, we can still extract three default-free coupon payments from the bond cash flows due to the trick used. To get the default-free coupon. payments, we simply pick the positive $\left(c_{t_{0}}\right)100$ at the default state for times $t_{i}$ of Figure 18.3a.. Note that this leaves the negative $\left(c_{t_{0}}\right)100$ in place.   
2. Initial and final payment of 100 as shown in Figure 18.3c. Again, adding and subtracting 100 is used to obtain a default-free cash flow of 100 at time. $t_{3}$ . These two cash flows are then carried to Figure 18.3c. As a result, the negative payment of 100 in the default state of times. $t_{i}$ remains in Figure 18.3a..   
3. All remaining cash flows are shown in Figure 18.3d. These consist of the negative cash flow. $\left(1+\mathbf{Co}_{t_{0}}\right)100$ that occurs in the time $t_{3}$ default state. This is detached and placed in Figure 18.3.  

The next step is to convert the three cash flow diagrams in Figure $18.3\mathrm{b-d}$ into recognizable and, preferably, liquid contracts traded in the markets. Remember that to do this, we need to add and subtract arbitrary cash flows to those in Figure $18.3\mathrm{b-d}$ while ensuring that the following three conditions are met:  

For each cash flow added, we have to subtract the same amount (or its present value) at the same $t_{i}$ from one of the Figures 18.3b, 18.3c, or 18.3d.   
These new cash flows should be introduced to make the resulting instruments as liquid as possible.   
When added back together, the modified Figure 18.3b-d should give back the original bond cash flows in Figure 18.3a. This way, we should be able to recover the cash flows of the defaultable bond.  

This process is displayed in Figure 18.4. The easiest cash flows to convert into a recognizable instrument are those in Figure 18.3b. If we add floating LIBOR-based payments, $L_{t_{i}}$ at times $t_{1},t_{2}$ and $t_{3}$ , these cash flows will look like a fixed receiver interest rate swap (IRs). This is good because swaps are very liquid instruments. However, one additional modification is required. The fixed receiver swap rate, $s_{t_{0}}$ , is less than the coupon of a par bond issued at time $t_{0}$ since the bond can default while the swap is subject only to a counterparty risk. Thus, we have  

$$
s_{t_{0}}\leq c_{t_{0}}
$$  

![](images/c9ea9f2dc93620145312920c28cb184cf9d05fac81bd366fac575947653f4ef8.jpg)  

# FIGURE 18.3  

Decomposition of a defaultable bond.  

![](images/bb92244008b622b835d8c3d14f1e688d89edd92ce49b7c7a316016c2e8651df4.jpg)  

Remove the spread from the coupon payments...  

(b) Place the spreads on the cash flows  

![](images/fcacd38814bd0fd59a102bc94c6fb70814406a312a4a0d4bad5da485b900fea3.jpg)  

# FIGURE 18.4  

Synthetic credit default swap.  

The difference, denoted by $\mathrm{cds}_{t_{0}}$  

$$
\mathrm{cds}_{t_{0}}=c_{t_{0}}-s_{t_{0}}
$$  

is the credit spread over the swap rate. This is how much a credit has to pay over and above the swap rate due to the default possibility. Note that we are defining the credit spread as a spread over the corresponding swap rate and not over that of the treasuries. This definition falls naturally from cash flow decompositions.  

Thus, in order for the cash flows in Figure 18.4a to be equivalent to a receiver swap, we need to subtract $c_{t_{0}}$ from each coupon as is done in Figure 18.4a. This will make the fixed receipts equal. the swap rate:  

$$
c_{t_{0}}-\mathrm{cds}_{t_{0}}=s_{t_{0}}
$$  

The resulting cash flows become a true IRS.  

The next question is where to place the counterparts of the cash flows. $c_{t_{0}}$ and $L_{t_{i}}$ that we just introduced in Figure 18.4a. After all, unless the same cash flows are placed somewhere else with opposite signs, they will not cancel out, and the resulting synthetic will not reduce to a risky bond..  

A natural place to put the LIBOR-based cash flows is shown in Figure 18.5. Nicely, the addition of the LIBOR-related cash flows converts the figure into a default-free money market deposit with. tenor $\delta$ . This deposit will be rolled over at the going floating LIBOR rate. Note that this is also a. liquid instrument. 10  

The final adjustment is how to compensate the reduction of. $c_{t_{0}}$ 's by the credit spread. $\mathrm{cds}_{t_{0}}$ Since the first two instruments are complete, there is only one place to put the compensating $\mathrm{cds}_{t_{0}}$ 's.We add the $\mathrm{cds}_{t_{0}}$ to the cash flows shown in Figure 18.3d, and the result is shown in. Figure 18.4b. This is the critical step, since we now have obtained a new instrument that has fallen  

![](images/a259da7af644008a3a1882cd9ae999c6dc2296aa26401ce9ff02ad5c67e6fc8a.jpg)  
Add LIBOR-based cash flow to figure 18.3c..   
...They become a floating rate money market deposit or a floating rate note (FRN)  

# FIGURE 18.5  

LIBOR cash flows become deposit.  

naturally from the decomposition of the risky bond. Essentially, this instrument has potentially three receipts of $\mathrm{cds}_{t_{0}}$ dollars at times $t_{1},t_{2}$ and $t_{3}$ . But if default occurs, the instrument will make a compensating payment of (1 + c) 100 dollars.11  

To make sure that the decomposition is correct, we add Figures 18.4a,b and 18.5 vertically and see if the original cash flows are recovered. The vertical sum of cash flows in Figures 18.4a,b and 18.5 indeed replicates exactly the cash flows of the defaultable bond.  

The instrument we have in Figure 18.4b is equivalent to selling protection against the default risk of the bond. The contract involves collecting fees equal to. $\mathrm{cds}_{t_{0}}$ at each $t_{i}$ until the default occurs. Then the protection buyer is compensated for the loss. On the other hand, if there is no default, the fees are collected until the expiration of the contract and no payment is made. We call this instrument a CDS.  

# 18.3.3 A SYNTHETIC  

The preceding discussion shows that a defaultable bond can be decomposed into a portfolio made up of (i) a fixed receiver IRS, (ii) a default-free money market deposit, and (iii) a CDS. The use of these instruments implies the following contractual equation:  

![](images/cbcbc893e6e5098b09d776fc3b548579e1b2524aa3ef1740cfcf94ce0ede668e.jpg)  

By manipulating the elements of this equation using the standard rules of algebra, we can obtain synthetics for every instrument in the equation. In the next section, we show two applications.12.  

# 18.3.4 USING THE CONTRACTUAL EQUATION  

As a first application, we show how to obtain a hedge for a long or short CDS position by manipulating the contractual equation. Second, we discuss the implied pricing and the resulting real-world difficulties.  

# 18.3.4.1 Creating a synthetic CDS  

First, we consider the way a CDS would be hedged. Suppose a market maker sells a CDS on a certain name. In other words, the market maker provides protection or sells the CDS and the credit. How would the market maker hedge this position while it is still on his or her books?  

To obtain a hedge for the CDS, all we need to do is to manipulate the contractual equation obtained above. Rearranging, we obtain the following equation for selling a CDS  

![](images/78a21cdfb0144ce9d720c81118a2baf8af1ed8ddebaec33b468885434f0ab596.jpg)  

Remembering that a negative sign implies the opposite position in the relevant instrument, we can write the formal synthetic for buying a CDS as  

![](images/37235dd6f172f42ea692d5ed635e48c941adb85cf3fcc7887a8c000a76e00272.jpg)  

The market maker who sold such a CDS provided protection needs to take the opposite position of the left-hand side of Eq. (18.1). This hedge corresponds to the right-hand side of Eq. (18.6). That is to say, the credit derivatives dealer who sold a CDS will hedge the CDS position by creating a synthetic opposite CDS position. This is achieved by first shorting the risky bond, depositing the received 100 in a default-free deposit account, and contracting a payer swap. This and the sale of the CDS will then "cancel" out. The market maker will make money on the bid--ask spread.  

# 18.3.4.2 Negative basis trades  

The second application of the contractual equation is referred to as negative basis trades. Negative. basis trades are an important position frequently taken by the traders in credit markets. A discussion of the trade provides a good example of how the contractual equation defining the CDS contracts changes in the real world..  

The contractual equation that leads to the creation of a CDS can be used to construct a synthetic. CDS that can be used against the actual one. As we saw in Chapter 7, the basis typically refers to the difference between the spot (cash) price of an asset and its future's price (derivative). In the credit derivatives market, traders refer to the basis as the difference between the CDS premium of a given bond $\left(\mathrm{cds}_{t_{0}}\right)$ and the bond spread $\left(c_{t_{0}}-s_{t_{0}}\right)$ for the same debt issuer and with similar, if not. exactly equal, maturities. Since CDS are derivatives, market participants in credit markets refer to the CDS leg of a negative basis trade as synthetic, and the bond leg as cash.13.  

Essentially, with a negative basis trade one would take out a floating rate loan to buy a bond that pays the par-yield $c_{t_{0}}$ while at the same time, buying insurance on the same bond and entering a fixed payer IRS. Clearly such a position has no default risk and makes sense if the coupon minus the bond risk premium $\left(c_{t_{0}}-s_{t_{0}}\right)$ is greater than the CDS premium payments $\left(\mathrm{cds}_{t_{0}}\right)$  

$$
s_{t_{0}}+\mathrm{cds}_{t_{0}}<c_{t_{0}}
$$  

This is in fact the case of negative basis. Here, as in the derivation of the contractual equation. above, we assume that the rate on the floating rate loan is the same as the LIBOR rate in the IRS. The above interpretation of the negative basis trade follows straight from the contractual equations (18.5) and (18.6).  

In practice, there is sometimes an alternative interpretation of the negative basis trade, since the bond spread can also be measured as the yield on the defaultable bond minus the yield of a Treasury security with a similar maturity. In other words,. $s_{t_{0}}$ is taken to be the yield on a Treasury. security and not the fixed rate from an IRS. The negative basis trade in that case can be interpreted as shorting the Treasury security and using the cash from this short position to buy a defaultable bond while at the same time taking out insurance purchasing a CDS on the same bond. Since the short finances the long, there is no need for a loan..  

Normally, the insurance on a default risky bond should be "slightly' higher than the credit risk spread one would obtain from the bond. This basis is in general positive. Otherwise, if the bond spread is larger than the CDS premium, then one would buy the bond and buy insurance on it. This would be a perfect arbitrage. This is exactly what a negative basis is. The reading below suggests when and how this may occur.  

# EXAMPLE  

A surge of corporate bond and structured finance issuance this past month has pushed risk premiums on credit default swaps down and those on investment-grade corporate bonds up, nearly erasing the difference between the two asset classes. If this trend continues, it has the potential to create new trading opportunities for investors who can take positions in both bonds and derivatives. Analysts are expecting to see more socalled "negative basis trades" as a result.  

January has been a particularly active month in the US primary corporate bond market, with over \$60 billion issued in investment-grade debt alone. This supply helps to widen risk premiums on corporate bonds. At the same time, there has been no shortage of synthetic collateralized debt obligations (CDOs), which has helped narrow CDS spreads. A corporate credit default swap contract features a seller of protection and a buyer of protection. The seller is effectively long that company's debt while the buyer is short. When a synthetic CDO is created, dealers sell a certain amount of credit protection, which helps compress CDS risk premiums.  

Typically, credit default swap risk premiums trade at wider levels than comparable bond risk premiums. This is partly because it is easier to take a short position via a CDS rather than a bond. Another reason that CDS risk premiums trade wider is the cheapest-to-deliver option. In the event of a bankruptcy, the seller of protection in a CDS contract will make a cash payment to the buyer in exchange for the bonds of the bankrupt company. However, the seller of protection will receive the cheapest-to-deliver bond from the protection buyer.  

Once the basis between a CDS risk premium and cash bond reverses and becomes negative, it can become advantageous to buy the bond and buy protection through a credit default swap. In such a trade, known as a negative basis trade, the investor has hedged out their credit risk, but is earning more on their bond position than they are paying out on their CDS position.  

(Thomson Reuters IFR, January 2006)  

The above reading also illustrates the terminology used in CDS trades. In the context of IRSs and volatility swaps, we defined the counterparty that was long the swap as the party that paid the first interest rate or volatility. In the contexts of CDS, one can describe the buyer (seller) of a CDS as being short (long) the underlying bond or credit.14 To the extent one refers to the buyer of the CDS as being short, this can be counterintuitive. To avoid any confusion we refer to the buyer. (seller) of a CDS as the protection buyer (seller). We will deal with CDOs and their construction and pricing in detail in Chapter 21..  

Negative basis trades become a possibility due to leveraged buyout (LBO) activity as well. During an LBO the buyer of the company issues large amounts of debt, which increases the debt to equity ratio on the balance sheet. Often, rating agencies downgrade such LBO targets several notches which makes LBO candidates risky for the original bond holder. Bond holders, hearing. that a company is becoming an LBO target, may sell before the likely LBO; bond prices may drop. suddenly and the yields may spike. On the other hand, the CDS rates may move less since LBO is not necessarily going to increase the default probability. As a result, the basis may momentarily. turn negative.  

# 18.3.5 MEASURING CREDIT RISK OF CASH BONDS  

Many credit and fixed-income strategies involve arbitraging between cash and synthetic instru-. ments. CDS is the synthetic way of taking an exposure to the default of a single name credit. It is a. clean way of trading default. But, cash bonds contain default risk as well as interest rate and curve risk. How would we strip from a defaultable bond yield the component that is being paid due to. default risk? In other words, how do we obtain the equivalent of the CDS rate from a. defaultable bond in reality?  

This question needs to be answered if we are to take arbitrage positions between cash and deri-. vatives; for example, when we have to make a decision whether cash bonds are too expensive or not relative to the CDS of the same name.  

At the outset the question seems unnecessary, since we just developed a contractual equation for the CDS. We showed that if we combined the cash bond and a vanilla IRS accordingly, then we would obtain a synthetic FRN that paid LIBOR plus a spread. The spread would equal the CDS rate. In other words, take the par yield of a par bond, subtract from this the comparable IRS rate, and get the equivalent of the CDS rate included in the bonds yield.  

This is indeed true, except for one major problem. The formula is a good approximation only if all simplifying assumptions are satisfied and if the cash bonds are selling at par. It is only then that we can straightforwardly put together an asset swap and strip the credit spread.15 If the bond is not selling for par, we would need further adjustments.  

There are two major methods used to obtain a measure of the default risk contained in a bond that does not trade at par. The first is to calculate the asset swap spread and the second is to calculate the so-called Z-spread. We discuss these two practical concepts next and give examples..  

# 18.3.5.1 Asset swap  

An asset swap spread is one way of calculating the credit spread associated with a default risky bond. Essentially it converts the risky yield into a LIBOR plus credit spread, using an IRS.  

In order to create a position equivalent to selling protection, we must buy the defaultable bond and get in a payer IRS. Note that the IRS will be a par swap here, while the bond might be selling for a discount or premium.16 So adjustments are needed in reality since the bond sells either at a discount or premium.17  

In the asset swap, the bond cash flows are discounted using the corresponding zero-coupon swap rates. A spread (called the asset swap spread) is added to (subtracted from) the bond cash flows so that the resulting bond price equals the market price..  

The formula for calculating the asset swap spread is as follows: first use the zero-coupon swap. curve to calculate the discount factors. By definition, zero-coupon swap curve discounts are obtained using the corresponding forward rates $f_{t_{j}}$ , and the equation,  

$$
\left(1+s_{t_{0}}^{i}\delta\right)^{i}=\prod_{j=0}^{i-1}\left(1+f_{t_{j}}\delta\right)
$$  

Then calculate the discount factors  

$$
B(t_{0},t_{i})=\frac{1}{\left(1+s_{t_{0}}^{i}\delta\right)^{i}}
$$  

Once this is done, form the annuity factor, $A$  

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

Thus, $\tilde{a}_{t_{0}}$ is how much one needs to be paid extra in order to compensate for the difference between the market price and the theoretical price implied by the default-free swap curve. This is the case, since if there were no default risk the value of the bond would be $\tilde{P}_{t_{0}}$ which is greater than the market price $P_{t_{0}}.\tilde{a}_{t_{0}}$ is a measure that converts this price differential into an additional spread.  

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

We interpret this equation as follows. Suppose the bond is trading at a discount, then an upfront payment of $\mathrm{upf}_{t_{0}}$ plus an IRS contracted at a rate $s_{t_{0}}+\tilde{a}_{t_{0}}$ is equivalent to the present value of the coupon payments of the bond. In other words, a par swap rate has to be augmented by $\tilde{a}_{t_{0}}$ in order to compensate for the bond's default risk. Note that during this exercise we worked with risk-free discount factors. This will change with the next notion..  

# 18.3.5.2 The Z-spread  

The so-called Z-spread is another way of calculating the credit spread. It gives a result similar to the asset swap spread but is not necessarily the same.  

In order to calculate the $\mathrm{\bfZ}$ -spread, the cash flows generated by a default risk bond will be discounted by the zero-coupon swap rate $s_{t_{0}}$ augmented by a spread $z_{t_{0}}$ , so that the sum equals the market price of the bond. That is to say we have  

$$
P_{t_{0}}=\sum_{i=1}^{n}\frac{\mathrm{cf}_{i}}{\left(1+\left(s_{t_{0}}^{i}+z_{t_{0}}\right)\delta\right)^{i}}
$$  

We solve this equation for the unknown $z_{t_{0}}$ . Here $\mathrm{cf}_{t_{i}}$ are the cash flows received at time $t_{i}$ and are made of coupon payments $c_{t_{i}}$ and possibly of the principal.  

According to this, the zero-coupon swap curve is adjusted in a parallel fashion so that the present value of the cash flows equals the bond price. The. $\mathrm{\bfZ}$ -spread is the amount of parallel movement. in the zero-coupon swap curve needed to do this..  

Note that during the calculation of the $\boldsymbol{Z}$ spread we worked with a measure of risky discount factors.18 The major difference between the $\mathrm{\bfZ}$ spread and the asset swap spread arises from the discount rates used. Asset swaps use zero-coupon swap rates whereas $\mathrm{\bfZ}$ -spread uses zero-coupon swap rates plus the Z-spread.  

In this sense, the $\boldsymbol{Z}$ spread method uses a stream of risky discounts from the whole risky. curve to adjust the future cash flows of the bond. The asset swap spread uses a single maturity swap rate to measure the credit risk. Although the. $\boldsymbol{Z}$ spread is better suited to risky discount.  

factors, markets prefer to use the asset swaps as a measure of credit risk. The reason is that the markets do not quote the credit spread as a spread to zero-coupon swap rates. The credit spread is quoted as a spread to a par swap rate because the par swaps are much more liquid than the zero-coupon swaps.  
