---
tags:
  - cds_pricing
  - corporate_bonds
  - credit_default_swaps
  - credit_risk
  - financial_markets
aliases:
  - CDS Basics
  - CDS Primer
  - Credit Derivatives
key_concepts:
  - Buying protection shorting FRN
  - CDS as leveraged bond
  - CDS counterparty risk
  - CDS structure explained
  - Selling protection long FRN
---

# A PRIMER ON CREDIT DEFAULT SWAPS (CDS)  

Thomas S. Coleman, PhD Close Mountain Advisors LLC tcoleman@closemountain.com  

21 October 2008, updated 23 March 2009,   
29 December 2009 (to include pricing)  

# INTRODUCTION  

The market for Credit Default Swaps (CDS) has grown from nothing just over ten years ago to a huge market today. But what is a CDS? How does a CDS behave in response to changes in the markets? How does one value a CDS? What is the risk? This primer aims to answer these questions for plainvanilla single-name CDS.  

Although CDS are often portrayed as complex, mysterious, even malevolent, they are really no more complex or mysterious than a corporate bond. I show how and why a CDS behaves, in almost all respects, as a leveraged or financed floating-rate corporate bond. The equivalence between a CDS. and a floating-rate bond is very useful because it means that anyone acquainted with corporate bonds, anyone who understands how and why they behave in the market as they do, how they are valued, and what their risks are, understands the most important aspects of a CDS. In essence, a CDS is no harder (and no easier) to value or understand than the underlying corporate bond. I also point out the. particular ways in which a CDS differs from a corporate bond..  

To preview the main points:  

Selling protection through a CDS is equivalent to buying a floating-rate corporate bond (a floating   
rate note or FRN) using leverage.   
-Selling protection for. $x$ years is in most respects the same as being long a corporate bond with $x$ years to maturity.. The exposure to credit spreads is the same whether one sells CDS protection or buys an FRN. In other words, when credit spreads move or upon default one can lose as much, but no more,. through selling. $\$100$ worth of CDS protection as buying $\$100$ worth of a corporate FRN with the same maturity and underlying credit.   
Conversely, buying protection through a CDS is the same as shorting a corporate FRN: the.   
exposure to credit spreads is the same and an investor can make or lose just as much from buying   
CDS protection as they can when shorting a corporate bond -- the investor loses if credit spreads   
tighten and the price of the FRN goes up.   
CDS are often spoken of as insurance contracts but a CDS more usefully can be considered a   
capital markets product: equivalent to a levered FRN. In reality, a CDS is no more (and no less)   
an insurance contract than is a corporate bond.   
A CDS entails no investment up-front (apart from margin or collateral the counterparty to the CDS   
may demand): It is equivalent to a leveraged position in an FRN. As with any leveraged position :   
CDS may generate losses greater than the original investment.   
Entering into a CDS does involve one additional risk that a corporate bond does not - the   
counterparty exposure that one party to the CDS may not live up to their side of the bargain.   
Generally this is not large, but it can be, and will be, important at times.  

# STRUCTURE OF A SINGLE-NAME CREDIT DEFAULT SWAP  

A Credit Default Swap is an agreement between two parties (say A and B) to make a payment upon the default of a bond issued by a third party (C). Let us take an example of the following five-year CDS:  

Five-year CDS on bond issued by company C  

Coupon 100bp Party A "buys protection" Party B "sells protection'  

This means that:  

As long as the bond issued by C does not default (during the next five years) Party A agrees to make regular payments of 100bp per year. Party B agrees to do nothing   
As soon as bond issued by C does default (during the next five years) Party B agrees to pay $\$100$ to party A Party A agrees to deliver the bond to party B  

The following diagram shows the payments, with the dotted line (.-.) representing periodic payments. (say once a quarter) that are made as long as the bond issued by C is not in default, and the dot-dash line $(----)$ representing payments made upon default.  

![](553e3fe07068da2f5b5d3b181da9f7f9fd6245c74581f8c5d993196d8703d980.jpg)  
Figure 1 - CDS between parties A and B, with A paying quarterly premiums and B paying loss upon default  

The result of this swap of payments is that party A makes periodic payments as long as the bond issued by C does not default, while A is compensated by receiving $\$100$ , the par value of the bond, if the bond defaults. In this sense, A is protected against the default of the bond issued by C, while B is at risk to pay $\$100$ upon default. For this reason, one says that party A buys protection and party B sells protection.  

Note one important point. Party B must pay $\$100$ upon default but receives the defaulted bond in return. Defaulted bonds usually do not go to zero since there is some recovery, although less than $\$100$ . The net result is that party B does not lose $\$100$ upon default of the bond issued by C, but rather $\$100$ less the recovery value of the bond.  

The CDS described above is said to involve physical delivery, since party A actually or physically delivers the bond to party B upon default. Many CDS were in fact structured as physical delivery in the early days of the market, but generally CDS now involve cash delivery where party B pays the net amount of $\$100$ - post-default value of the bond. As long as markets are relatively well-behaved there should be no difference between physical and cash delivery, and I will ignore any differences.  

# EQUIVALENCE OF CDS AND FLOATING RATE NOTE  

When first introduced to a CDS and after reflecting on figure 1, it is natural to think that the risk or exposure of parties A and B are quite asymmetric: A has what look like fixed payments and thus what looks like a known or fixed value, while B has a large contingent liability and thus what looks like a quite uncertain value. In fact, this is far from the truth. In the example above the risk or exposure for party B is the same as the risk of owning a five-year FRN issued by C, while the exposure for A is the same as the risk of shorting a five-year FRN. Just as the FRN may go up or down due to changes in C's credit status, so the CDS may go up or down and either party A or party B may gain (or lose).  

To see why a CDS is really the same as a floating rate bond (FRN), first consider figure 2, which shows the CDS cash flows over time for party B, who sells protection, from the example above. Party B receives premiums until the maturity of the CDS or default, whichever occurs first. Since the premiums are paid only if there is no default, they are risky. If there is a default, then party B must pay 100 - Recovery.  

![](339334e3d69b66d70073417be86aeb9ac49c8e63439417c724aac84d2f8bf8a7.jpg)  
Figure 2 - Time-line of CDS Payments (Sell Protection)  

Now we can utilize an elegant trick. With any swap agreement only net cash flows are exchanged.. This means we can insert any arbitrary cash flows we wish, so long as the same amount is paid and. received and the net is zero. Let us add and subtract libor payments at each premium date, and also. 100 at CDS maturity, but only when there is no default. These libor payments are thus risky. But. since they net to zero, they have absolutely no impact on the price or risk of the CDS. The top part of figure 3 shows the original CDS plus these net-zero cash flows. The bottom part of figure 3 then rearranges these cash flows in a convenient manner:.  

Left panel produces an FRN by combining: CDS premium and $+$ libor into a risky floating coupon, paid only if there is no default. $+100$ into a risky principal repayment, paid only if there is no default. Convert the payment of -Recovery into receiving $+$ Recovery, paid only if there is default Right panel produces a libor floater by combining: libor into a risky floating coupon, paid until default or maturity, whichever occurs earlier   
100 paid at maturity if there is no default   
100 paid at default if there is default  

The lower left panel is exactly a floating rate bond (FRN): if no default occurs then party B receives coupon of (libor $+$ spread) and final principal at maturity, while if default occurs then party B receives the coupon up to default and then Recovery. The combination in the lower right panel looks awkward but is actually very simple: it is always worth 100 today. It is a libor floating bond with maturity equal to the date of default or maturity of the CDS: payments are libor $+~100$ whether there is a default or not, with the date of the 100 payment being determined by date of default (or CDS maturity). The timing of the payments may be uncertain, but that does not affect the price because any bond that pays libor $+~100$ , when discounted at libor (as is done for CDS), is worth 100 irrespective of maturity.  

![](9fb7e055b534c2665af0bbb09158d6d8076ac6d155d31384b375ba4046e78673.jpg)  
Figure 3  CDS Payments plus Offsetting Payments $=$ FRN - libor floater  

In other words, we have just proven, rather simply and without any complex mathematics, that a CDS(sell protection) is just a combination of long an FRN and short a libor floater (worth $\$100$  

$$
\mathrm{CDS(sell~protection)}\iff+\mathrm{FRN-libor~floater}=+\mathrm{FRN-}100.
$$  

By reversing the signs, we also have  

$$
\mathrm{CDS(buy~protection)}\Leftrightarrow-\mathrm{FRN}+\mathrm{libor}\mathrm{floater}=-\mathrm{FRN}+100.
$$  

This is extraordinarily useful as it tells us virtually everything we want to know about the broad how and why of a CDS:1  

CDS - Sell Protection  

The value of a CDS with coupon. $c$ is the value of an FRN with coupon. $l i b o r+c$ , less 100.   
The risk is that of being long an FRN. The risk goes up with maturity in exactly the same.   
way as it does for an FRN.   
As credit spreads go up the value of CDS goes down since the value of the FRN goes down.  

CDS - Buy Protection  

The value of a CDS with coupon $c$ is the value of 100 minus an FRN with coupon libor $+c$ The risk of a CDS is the risk of being short an FRN.   
As credit spreads go up the value of CDS goes up since the value of the FRN goes down and a buy-protection CDS is short the FRN.  

One can just as easily lose buying protection as selling protection, because one can lose by shorting an FRN just as easily as by buying an FRN..  

Note that everything we have covered is for a CDS exactly on a premium payment date. There are some modifications for being off a coupon date, but these are not substantial and do not change the basics of what I have shown. Also, remember that the CDS is equivalent to a leveraged position in the FRN, as discussed more below.  

# EQUIVALENCE OF CDS AND FIXED RATE BOND  

The equivalence demonstrated above is between a CDS and a floating rate note or FRN. Fixed rate. corporate bonds are more common than floating-rate, and one can show that there is an equivalence of the following form:  

CDS(sell protection) $\Leftrightarrow+$ Fixed rate corporate -- Amortizing riskless bond .  

A fixed rate corporate bond will have risk to both interest rates (the riskless rate) and credit spreads, while the CDS essentially has risk to just credit spreads. The amortizing riskless bond removes the interest rate risk, and the combination of "Fixed rate corporate bond less Amortizing riskless bond will have only credit spread risk.  

Note, however, that the CDS is equivalent to a par fixed rate bond, with coupon roughly equal to the riskless interest rate plus the CDS spread. It will not be true that a standard (zero-PV) CDS will be equivalent to a fixed rate bond that is trading at a significant discount or premium. A fixed rate (or floating rate) bond trading at a discount will be equivalent to a CDS with a below-market coupon.  

# CDS AS CAPITAL MARKETS vs. INSURANCE PRODUCT  

CDS are often talked about as "insurance" and the terminology in the market (buying or selling protection) reinforces this notion. Thinking of a CDS solely as an insurance contract, however, may lead one to think of a CDS as a contingent liability that cannot be easily valued, and even that the value of a CDS does not change over time. As the equivalence discussed above shows, however, a CDS can be thought of as a capital markets product (a levered FRN) with a price determined by investors' assessment of the firm's credit-worthiness and likelihood of default. In general this will be a more fruitful approach than considering CDS as an insurance product valued on an actuarial basis.2  

In reality, a CDS is no more (and no less) an insurance product than is a corporate bond. In fact, a corporate bond can be thought of as an insurance contract, even if a somewhat unusual one. When an investor buys a corporate bond from company C they give the company $\$100$ in return for the promise to pay regular coupons and then principal upon maturity. Obviously the promise is not iron-clad, because the company may go into default. It is most common to simply consider that the principal is at risk and there is a possibility that the investor will receive back less than $\$100$ . But one could equally think of the promise to repay principal as iron-clad with no risk to the principal, by the simple expedient of having the investor provide an additional insurance contract to company C. The insurance contract would have the investor cover any shortfall on principal if there were to be a "default' and company C were unable to repay the full principal. The net result would be the same -- the investor receives less than $\$100$ in the event of default - but it is now through the combination of a non-risky $\$100$ principal combined with an insurance contract that guarantees the principal.  

If one insists on talking about CDS as insurance then the following analogy may prove useful. Say that an insurance company provides fire insurance to all homeowners in a town, and that the contract is set for five years. Say the town is Bellingham Washington. The climate of coastal Washington is rather wet so there is little risk that widespread forest or brush fires would threaten the town. The overall rate of house fires is low, house fires in Bellingham tend to be individual random events, the insurer is well-diversified, and the overall premium would be low. Now say the impossible happens: climate change arrives overnight and Bellingham is surrounded by tinder-dry forest, or Bellingham is miraculously transported to the fire-prone areas of Australia. (I know that this is not realistic but it simply reinforces that thinking of CDS as insurance is not very useful.) The premium for fire insurance would shoot up, even before any homes burned, simply because it is likely that more houses will burn and not impossible that the whole town could burn.  

Or consider another insurance story, where a company insures homes in a city against flooding, again. for five years. The company believes that the city it is insuring is Cedar City, UT. Flooding is not. common on the northeastern edge of the Mojave Desert, and what there is tends to be random localized events, so premiums would be low. But now say the company finds out that it was mistaken and the city it has insured is not Cedar City UT but Cedar Rapids, IA, which is subject to frequent and. severe flooding. (Remember 2008, when 100 city blocks were submerged and 10,000 people. evacuated.) The premium for flood insurance would now be hugely higher, even before any homes were flooded, because there is a higher probability any single home will be flooded and a reasonable. chance the whole city will flood, leading to catastrophic losses on the part of the insurer..  

In both cases the premium would jump from before to after, even prior to actual losses from fires or floods. The insurer's future liabilities would increase hugely, and if the company marked-to-market or held reserves against possible future losses it would properly recognize those losses immediately,. prior to actual losses. If the insurer tried to sell its policies to another insurer or buy out its policy-. holders (i.e. unwind the insurance) during the five years of the contract then it would have to pay a large fee representing the new, higher cost of the insurance. Such payments would not be payment in. full to cover an actual loss on any policy but simply the higher premium reflecting the new higher. probability of fire or flood..  

The problem with calling CDS "insurance"' is that it falsely leads to comparisons with things such as standard fire insurance. For fire insurance the probability of fire does not change dramatically with time (for insurance across many houses), while for products "insured"' by CDS contracts the.  

probability of default can change dramatically over time. In the end, one can either think of both a CDS and an FRN as insurance products, or both as capital markets products, but it is inconsistent to consider one (the CDS) as insurance and the other (the FRN) as a capital markets product.  

# CDS VALUATION USING CREDIT SPREADS  

Financial markets continually assess and re-assess the credit-worthiness of firms and their likelihood of default. The equivalence between a CDS and corporate bonds demonstrated above shows how one can access the financial markets' assessment of a firm's credit to value the CDS. The credit spread. (say from FRN or fixed rate bonds) is the simple way to measure the markets' assessment of credit-. worthiness. One can obtain the credit spread from a traded FRN or fixed rate bond, then apply that. spread to value the FRN that is equivalent to the CDS.  

An example will suffice to show how the credit spread can be used to provide a ballpark price for a CDS. In mid-September 2007 the credit spread on a seven-year Lehman bond was about 120bp. A seven-year CDS would be equivalent to a seven-year par FRN. Since an FRN with spread of 120bp would be trading at par, a CDS with premium of 120bp would be at par (NPV zero). By earlySeptember 2008, Lehman credit spreads had widened to around $450\mathrm{bp}$ , reflecting markets' assessment. of the higher likelihood that Lehman would default. (As it happened, Lehman did file for bankruptcy over the weekend of September 13-14. By September $12^{\mathrm{th}}$ spreads had widened to about 660bp.) The. original FRN paying a spread of 120bp, now with six years to maturity and trading in a market that valued Lehman's credit at 450bp spread, would be worth about $\$84$ 3 This means that a sell-. protection CDS (equivalent to long FRN less $\$100$ ) would have fallen to about -\$16..  

As a general rule, default by a company is not a surprise event and does not come entirely out-of-theblue -- financial distress usually shows up well before the event of default and markets factor this in, revising over time the likelihood of default and the value of a firm's bonds. This can be seen in the changes in credit spreads for a firm's bonds. Credit spreads generally increase well before the actual event of default, and allow an investor to both ascertain markets' assessment of likelihood of default and track the changes in the value of a CDS.  

# CDS VALUATION BY MARTINGALE MODELING (constant hazard rate)  

A model for valuing a CDS is relatively straight-forward. The cash flows for a CDS (sell protection) are:  

Receive Fixed coupon $c$ as long as there is no default.   
Pay When (and if) default occurs, 100 less any recovery  

These cash flows are as shown in figure 2, repeated here:  

![](bad9d41ca68e86b021c312fb4a2abd2d59b1f6f63bb5291daaefd932f5ca0c76.jpg)  
Figure 2 - Time-line of CDS Payments (Sell Protection)  

Under the martingale modeling approach the default is assumed to occur at some random time, t. This is a reduced form model in the sense that the process governing default (the random time. $\vec{\tau_{,}}$ is assumed rather than default being modeled as a result of underlying financial or economic processes. The benefit of the approach is the substantial flexibility in the stochastic process governing default,. and the simplicity of the relative pricing (risk-free or equivalent martingale) framework.(See, for example, McNeil, Frey, Embrechts 2005, section 9.3.3.)  

For now we assume the random default time $\tau$ is a constant-hazard process. This means the probability of default in the next instant of time, conditional on not yet having defaulted, is constant. In other words under the risk-neutral measure the default time $\tau$ is exponentially-distributed with constant hazard $\alpha$  

$$
\mathrm{P}(\tau<t+\mathrm{d}t\mid\tau>t)=\alpha\mathrm{d}t\qquad\mathrm{P}(\tau>t\mid\tau>0)=\exp(-\alpha t).
$$  

If we assume that the risk-free rate is constant at $r$ , then the present value of receiving the coupons $c$ is:  

$$
\begin{array}{r}{\operatorname{PV}(\operatorname{receive}\operatorname{coupons}c\mathrm{at}\operatorname{times}t_{\mathrm{k}})=\sum_{\mathrm{k}}\exp(-r t_{\mathrm{k}})\cdot c\cdot\operatorname{P}_{\mathrm{Q}}(\mathit{\ v}\mathit{\hat{r}}_{\mathrm{k}})=\sum_{\mathrm{k}}\exp(-r t_{\mathrm{k}})\cdot c\cdot\exp(-\alpha t_{\mathrm{k}}).}\end{array}
$$  

(This assumes that coupons occur annually, or that $c$ includes the day-count adjustment. If not then we would have $c$ df where $d f=$ day fraction $=$ (days between payment) / 360 or / 365 depending on the currency and appropriate money-market convention.)  

The PV of paying the loss upon default is the expectation over the random default time of the loss (net of recovery). Say the loss is 100 and the recovery is fixed at $\delta.$ Then the loss net of recovery is 100(1-d) and the expected value is:  

$\mathrm{PV}(\mathrm{loss})=-$ Integral[Loss amount, discounted at $r$ , times density]  

$$
=-100\cdot(1-\delta)\cdot{\int}\alpha\cdot e^{-r s}\cdot e^{-\alpha s}d s=-100\cdot(1-\delta)\cdot(\alpha/(\alpha+r))\cdot[1-\exp(-(r+\alpha)T)]
$$  

The total value of the CDS is  

PV of CDS (Sell Protection: Rec premium $c$ , Pay pay-back of bond loss)  

$$
\begin{array}{r l}&{=\mathrm{PV}(\mathrm{receive~coupons})-\mathrm{PV}(\mathrm{loss})}\ &{}\ &{=\sum_{\mathrm{k}}\exp(-r t_{\mathrm{k}})\cdot c\cdot\exp(-\alpha t_{\mathrm{k}})-100\cdot(1-\delta)\cdot(\alpha/(\alpha+r))\cdot[1-\exp(-(r+\alpha)T)]}\end{array}
$$  

$$
=\sum c\cdot d f\cdot e^{-t(r+\alpha)}-100\cdot(1-\delta)\cdot\big(1-e^{-(r+\alpha)T}\big)\frac{\alpha}{\alpha+r}
$$  

Where $d f=$ dayfraction (e.g.) $\approx92.5/360$ for quarterly USD, A/360)  

This is a very simple formula, in fact one that can be evaluated in a spread-sheet without difficulty.  

This assumes that when default occurs between coupon payment dates no partial coupon is paid. For most traded CDS there is actually an accrued coupon payment. In this case the expected PV for a coupon to be paid at $t$ (with accrued paid if default occurs before $t_{,}$ should be:  

$$
c\cdot d f\cdot[\mathrm{e}^{-r t}\cdot\mathrm{P}[\mathrm{default}>\mathrm{t}]+c\cdot d f\cdot\int\alpha\cdot e^{-a u}\cdot e^{-r u}\cdot\frac{u-\left(t-b\right)}{b}\mathrm{d}u]
$$  

where $b=1$ /coupon frequency (e.g. $=0.25$ for quarterly payments)  

$$
=c\cdot d f\cdot\mathrm{e}^{-(r+\alpha)t}\cdot\left[1+\alpha\cdot\frac{e^{b(r+\alpha)}-1-b(r+\alpha)}{b\cdot(r+\alpha)^{2}}\right]
$$  

The first term is. $c{\cdot}d f{\cdot}\mathrm{e}^{-r t}\cdot\mathrm{P}[\mathrm{default}>t]$ . The second term is the accrued payment $(c{\cdot}d f{\cdot}[u{-}(t{-}b)]/b)$ times probability of default. $(\alpha\cdot\mathrm{e}^{-\alpha u})$ , discounted by $\{\mathrm{e}^{-r u}$  

Because of the equivalence between the CDS and FRN this also provides a model for valuing an FRN. In fact, this provides the obvious way to calculate the parameter $\alpha$ from the market. We can get the risk-free rate from the government bond market or swap market, and then we can back out the value for $\alpha$ necessary to give the correct market price of the FRN.4.  

# LEVERAGE AND COUNTERPARTY EXPOSURE - The difference between CDS and FRN The CDS is a leveraged position:  

CDS(sell protection) $\Leftrightarrow$ long an FRN, short a libor floater or libor deposit  

Recognizing this leverage is important. An outright (fully-funded) purchase of an FRN can never lose more than the purchase price: the up-front investment caps the total loss. An investor who finances the purchase of an FRN, whether through the repo market or synthetically through a CDS, takes on leverage. Such a leveraged position can lose up to the notional, which will generally be more than the original investment. An investor who fails to recognize either the leverage inherent in a CDS or the risk characteristics of a CDS (that selling protection is equivalent to long an FRN and buying protection is equivalent to short an FRN) may take tactical or strategic decisions leading to unexpected losses.  

There is one important difference between a CDS and an FRN: the additional counterparty credit. exposure. A CDS is a private transaction between parties A and B. Continue with our example of party B selling protection. Party B expects to receive the periodic payments until C defaults, but is dependent on party A to make those payments, not on party C as would be the case for an FRN. Thus, party B is now at risk not just to C (as for the FRN) but also to A. In most cases the credit standing of A is substantially higher than C, and furthermore the credit exposure is for the net value of the CDS which is generally close to zero. When either or both of these does not hold (the credit. standing of A is poor relative to C or the value of the CDS has moved far from zero) then the credit exposure to A can become quite important and must be considered..  

One must not, however, exaggerate the practical impact of counterparty exposure across the financial system. Two factors mean that the actual counterparty exposure is less, in fact substantially less, than the notional outstanding. First is the simple fact that the exposure at a point in time is only the PV of the CDS and not the notional. A new CDS generally is written with zero PV and so the exposure for both parties is zero. As the underlying credit improves or deteriorates the CDS will rise or fall in value. Say the credit has deteriorated and the value for party B of the CDS (sell protection) has fallen from $\$0$ to $-\$10$ . The counterparty exposure for A is now. $\$10$ (if B defaults, A loses an asset worth $\$10$ , but this is substantially less than the full notional of $\$100$ . Second, market participants have. developed mechanisms that substantially mitigate what exposure does exist. The most wide-spread are collateral arrangements. Most counterparty agreements require posting of collateral as the CDS changes in value. Continuing with the example above where party B sold the protection so that the CDS is worth $+10$ to party A. Generally, party B would transfer collateral to party A to cover some or all the $\$10$ . This collateral would be available to A to cover the value of the CDS were party B to default, bringing the effective counterparty exposure close to zero. Additional collateral would be transferred if the value of the CDS moved from - $\$10$ to - $\$20$ , keeping the counterparty exposure close to zero. The net effect is that counterparty exposure at a point in time will be closer to zero than to the. notional outstanding.  

# APPENDIX EXAMPLE  

I will work with the following example, with all instruments assumed to pay semi-annually and all.   
rates and coupons quoted on a semi-bond basis. Most CDS and most FRNs pay quarterly and are.   
quoted on an actual/360 or actual/365 basis, but I will use semi-annual bond basis here to better.   
highlight the close relationship between a CDS, FRN, and corporate bond. The underlying model is a Poisson default-process model such as that outlined above, which allows valuation of CDS, FRNs,.   
and fixed-coupon risky or defaultable bonds in the same model.5.   
5 year CDS (buy protection, accrued): Premium $=295.76\mathfrak{p}$ $\mathrm{PV}=0$   
5 year CDS (buy protection, no accr): Premium = 292.2bp $\mathrm{PV}=0$   
5 year floating-rate note: Price $=\$100$ Promised spread $=300{\mathrm{bp}}$ semi-annually Credit spread $=300\mathrm{bp}$ sab   
5 year fixed-rate corporate bond: Price $=\$100$ Coupon $=6.50\%$ semi-annually Yield $=6.50\%$ sab Credit spread $=300\mathrm{bp}$ sab   
5 year riskless bond: Price $=\$100$ Yield (interest rate) $=3.5\%$ Coupon $=3.5\%$ semi-annually  

Spreads, premiums, coupons are chosen so that instruments are at par. The differences in coupon or premium are due to differences in the way premiums or coupons are paid if default occurs between payment dates. The first rows in the table below summarize the base case..  

Now let's say the credit market moves and the probability of default rises but with no change in interest rates. Say the market moves enough so that the FRN credit spreads rise by 100bp to $400\mathrm{bp}$ The next rows in the table summarize this case. The CDS, FRN, and corporate bond all fall in value, and by essentially the same amount. The changes for the CDS with and without accrued differ by $4.8\not\C$ , while the CDS without accrued and the FRN differ by $5.8\not\C$ , out of a total change of about $\$4.00$ This demonstrates how one can use the FRN to understand how to value the CDS and to understand how the CDS moves as the market moves.  

The same result holds if credit improves and the probability of default goes down. The next rows of the table shows what happens when the probability of default goes down enough so that the FRN credit spreads fall by 100bp to 200bp. Once again, the CDS, the FRN, and the fixed-rate bond all rise by almost the same amount.  

<html><body><table><tr><td rowspan="2"></td><td colspan="2">CDS</td><td rowspan="2">FRN</td><td rowspan="2">Fixed Bond</td><td rowspan="2">Riskless Bond</td></tr><tr><td>yes accr</td><td>no accr</td></tr><tr><td>Base Case Promised Spread / Coupon PV</td><td>295.7bp 0.000</td><td>292.2bp 0.000</td><td>300.0bp 100.000</td><td>6.50% 100.000</td><td>3.50% 100.000</td></tr><tr><td>Credit Spreads Credit spreads increase 100bp PV Change from base Credit Spreads</td><td>-4.000 -4.000</td><td>-4.048 -4.048</td><td>300bp 95.894 -4.106</td><td>300bp 95.894 -4.106</td><td>100.000 0.000</td></tr><tr><td>Credit spreads decrease 100bp PV Change from base Credit Spreads</td><td>4.207 4.207</td><td>4.259 4.259</td><td>400bp 104.320 4.320 200bp</td><td>400bp 104.320 4.320 200bp</td><td>100.000 0.000</td></tr><tr><td>Spreads and Rates up 100bp PV Change from base Credit Spreads</td><td>-4.162 -4.162</td><td>-4.212 -4.212</td><td>95.665 -4.335 400bp</td><td>91.931 -8.070 401.5bp</td><td>95.567 -4.433</td></tr></table></body></html>  

When both credit conditions and economic conditions changed, so that both credit spreads and interest rates change, the fixed-coupon bond no longer mimics the CDS. The final rows of the table show results when probability of default rises and interest rates rise. The CDS and the FRN both fall by almost the same amount, but the fixed-coupon bond responds to both changes in credit and interest rates. A riskless amortizing bond would exactly cancel out the effect of the change in interest rates, but even a plain-vanilla riskless bond does a reasonable job. The net of the change in the corporate bond (-8.070) and the riskless bond (4.433) is -3.637, not wildly different from the actual change in the CDS.  

A.J. McNeil, R. Frey, P. Embrechts (2005), Quantitative Risk Management, Princeton University Press  