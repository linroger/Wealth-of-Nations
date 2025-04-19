---
tags:
  - arbitrage
  - counterparty_risk
  - credit_risk
  - cross_currency_basis
  - xva
aliases:
  - XVA
  - xccy basis
key_concepts:
  - Counterparty risk
  - Credit valuation adjustment
  - Exposure profiles
  - Multiple transactions
  - Positive and negative values
  - XVA costs
---

# Chapter 2 XVA and the Cross-Currency Basis

The financial world changed in 2oo8.' Before the crisis, there was only one 'yield curve', and markets were relatively arbitrage-free. In the post-crisis world, credit concerns cause curves to multiply, and various regulations designed to protect end up delivering unintended consequences, allowing previously impossible 'arbitrage' situations to persist.

A contributing factor to the persistence of these apparent 'arbitrages' is the XVA costs of certain deal types to those market participants who might normally take advantage of the arbitrage. In this chapter, we introduce the concepts underpinning XVA and estimate these costs to show their probable effect on the cross-currency (xccy) basis.

Finally, we drill into the mechanics of attempting to use the xccy basis as an arbitrage and show why it is simply impossible for many market participants, though for others it may at some level be profitable. These variable profit opportunities place limits and pressure on the basis, which we attempt to quantify.

# XVA -- What is It?

# A Brief Summary of Counterparty Risk

The quantities grouped under the perhaps unintuitive acronym of 'XVA' are various credit-derived costs of doing deals. The acronym XVA had its origins in Credit Valuation Adjustment (CVA), which evolved into XVA as the various valuation adjustments grew. These adjustments derive from the older-style management of loan portfolios, where companies wished to avoid excessive or concentrated exposure to individual counterparties or closely correlated counterparties. For a single loan, the traditional calculation would look something like this:

$$
\mathrm{pected}\mathrm{loss=(Exposureatdefault)\times(probabilityofdefault)\times(lossgivendefault)}
$$

Here, 'exposure' is the amount of the loan outstanding at the time of default (some may have been partially paid back). To value a loan, the bank will consider its expected income, the difference between the interest received on the loan and the cost of borrowing the money to lend on to the customer, against the expected loss. Those earnings are set against the amount of capital that the bank is required to hold for the risk. The capital requirement for a loan is a calculation depending on a variety of factors, such as the credit risk of the borrower and the maturity of the exposure.

The complexities involved in taking this concept from the simple loan to a de-. rivatives portfolio are many, but the basic building block - that of exposure to a counterparty - remains the same. They can be qualitatively outlined as follows..

Multiple transactions. Once more than one transaction is on the books, the interaction between them must be considered. Does one offset the other? Do they add. up? Are the counterparties in similar areas, meaning that they are more likely to default at the same time?

Positive and negative values. A simple loan has a tenor and a principal amount and only creates an exposure for the lender. But even a simple derivative product like a swap introduces an additional layer of complexity, as it can create exposure for either counterparty; depending upon market conditions, it can have a positive or negative value.

Probability of different exposures. A complex deal can take on a range of val-. ues and neither of the counterparties can be sure what it will be worth at different points in time. Thus, instead of a single value it has a range of values which have a. range of probabilities attached to them at different times in the future..

Exposure profiles. Different contracts have different risks throughout their life-. times. Thus, an interest rate swap has a low exposure (meaning that its overall value will not have moved far from its start value) at the beginning of its life. It will. have a low exposure near the end of its life, as there is little uncertainty left about its ultimate value. In the middle of its life, its exposure will be highest, as it has plenty of payments left to run, and rates may have moved far from the start values by that time. So its exposure profile is humped' as a function of time. A crosscurrency swap, on the other hand, has its highest exposure right at the end of its life, as at that point, it exchanges principle amounts whose values depend on exchange rates and are not fixed until the end point, so its exposure profile rises towards the final date.

Mitigation measures. To reduce exposure, many counterparties began to take mitigation measures such as netting agreements or posting collateral. In a netting agreement, two counterparties agree that in the event of a default by one of them, any payments made will be calculated by netting offsetting deals. This is designed. to avoid a situation in which the defaulting counterparty does not pay what they owe but still claims what they are owed. Collateral posting occurs when a deal accrues a positive value to one counterparty (they are owed money), and thus a negative value to the other (who owes money). The latter counterparty sends collateral in the form of high-quality assets to the former counterparty. In the event of a de. fault, this counterparty may retain the collateral, meaning that their effective exposure is much lower. Collateral has become a hugely popular mitigation measure - ISDA (2010) estimates that $63\%$ of all FX derivative trades are covered by collateral arrangements.

Netting set. The use of netting agreements leads to the interesting situation where the risk of a deal depends upon the portfolio or netting set it will be added to. If it is largely offsetting, its additional risk can be low or even negative. Thus, deal risk and cost can be determined and can be unique to the counterparties involved, as well as their current portfolio and legal position.

# Risk vs Cost

The risk of a deal and the cost of a deal are different but related quantities, and it is interesting to note that over the years the focus has somewhat shifted from risk to cost. All the various complexities described here serve to reduce the risk of a deal to the holder. If we assume that the cost is a function of holding capital to support the deal risk, then to an extent, reducing risk will reduce cost. But what if a particular deal turns out to reduce risk overall? Or what if, perhaps, a risky but profitable deal can only be justified if it is hedged - but the hedge is expensive?

Additionally, a decision made on risk grounds is complex. Imagine a risky deal that is profitable. The client perhaps also does a lot of other business with the bank, so there is a degree of offset. However, this deal adds risk in a currency where the bank is already highly exposed. This is a decision that would take time and would involve multiple people.

While it may be argued that some decisions are inherently complex and should not be oversimplified, it is surely the case that for most deals, if all the various complexities described here could be reduced to a simple cost, then oh, how much easier it would be! As long as the following is the case:

# Profit of deal $>$ cost of doing deal

then the deal should be done. How easy, how efficient! No need to worry about exposures, netting, correlations or collateral. The growing complexity of managing the risk of a portfolio of deals paved the way for the introduction of CVA.

# CVA - The First Horse in the XVA Stable

Credit Value Adjustment (CVA) seems like a beautifully simple solution to this set of complexities, but it has its own problems. CVA is the change in value of the deal.
due to the possibility of counterparty default. If the counterparty will never default,.
CVA is zero. It is useful and convenient to express CVA as a running annualised.
spread.

There are many methods, varying in complexity, which are used to calculate CVA. In the following section, we list the most common.

# (1) Full Calculation

For a complete and exact value, CVA is given by

$$
C V A=(1-\delta)\sum_{j=1}^{m}D F\big(t_{j}\big)E E\big(t_{j}\big)q\big(t_{j-1},t_{j}\big)
$$

Here,

$\delta$ is the recovery fraction, so $(1{-}\delta)$ is the percentage of the deal value lost in the event of a default. This is largely dependent upon legal and relationship factors.

$D F\mathbf{(}t_{j}\mathbf{)}$ is the discount factor for time $t_{j}$ . This is relatively simply determined from risk-free rates.

$E E(t_{j})$ is the expected exposure at time $t_{j}$ . This is the idiosyncratic calculation. which involves all exposure, netting and collateral considerations, and can vary. considerably from one institution to another. It will be obtained from the desk or team in charge of these calculations..

$q\left(t_{j-1},t_{j}\right)$ is the default probability from time $t_{j}$ to $t_{j-1}$ . One would usually use default probabilities implied from historical data, though there are occasions where it may be preferred to use market implied figures (though this can become a somewhat circular issue).

# (2) Cost of Hedging

However, there are other ways of looking at the CVA calculation. If CVA is just the change in value which comes from credit risk, shouldn't it simply be the cost of hedging away this credit risk? For many large institutions, one may effectively hedge away the risk of default using a Credit Default Swap (CDS), as shown in Figure 2.1.

![](224d88e3c925f76ce8894504e512dc07076fc1e5be6409b3d6132b0f35d5112e.jpg)
Figure 2.1: Credit Default Swap.

If we use this method, then we have the following:

$$
C V A=\sum_{t=1}^{T}P V_{c a s h f l o w}(C D S_{t})
$$

This is the sum of the CDS to protect each of the future cashflows of the deal.

It is perhaps worth a quick aside on the relationship of CDS to credit spreads. In theory, they arise from exactly the same source -- the perceived default risk of a com-. pany and its effect on the cost it must pay to borrow. Thus, the total value of the spread between the company bond yields and the risk-free rate should mirror the value of the CDS payments. However, in reality these two prices can diverge substantially and create a basis' between CDS and bonds (defined as the difference between the CDS' and the bond's spread). Credit-specific factors such as documentation can be important, and generally, supply-demand dynamics in the bond market are an important factor behind this basis. In practice, however, the CDS-bond basis is domi-. nated by diverging liquidity dynamics and segmentation between markets. Before the financial crisis, the creation of synthetic CDO products meant that CDS-bond basis. contracted significantly. In Europe, since 2015, the ECB's  QE program has created a force in the opposite direction, causing the basis to become wider. Last but not least, the rise of CVA desks during the last decade has introduced another important factor as they tend to be buyers of protection.

While all of these factors have contributed to a structurally wider CDS-bond basis since the crisis, it is interesting to note that the CDS-bond basis is correlated with the xccy basis - although no direct relationship exists between the two (see Figure 2.2 for an example from Italy). It is possible that this underscores that relative scarcity conditions are exerting similar influences on both bases and that regulatory XVA costs are also inhibiting arbitrage opportunities in similar ways on both instruments.

![](49991e50c20048efd4ad4fa6f67ab862cb15a0517504b41eed6c5de5a09057a0.jpg)
Figure 2.2: 5y cash-CDS and cross EURUSD currency bases, in bp. Source: Commerzbank, Bloomberg

# (3) Discounted Cashflow Approach

In this case, the CVA is assumed to be the difference between the future cashflows discounted by the risk-free rate and the future cashflows discounted by the creditadjusted rate.

$$
C V A=F V_{r i s k f r e e}-F V_{c r e d i t a d j u s t e d}
$$

While in theory this ought to come out with very similar results to the other calcula-. tions, it has a degree of flexibility in that the credit adjustment spread can be credit spread of either counterparty, depending on which way round the exposure is.

# (4) Duration Approach

This is perhaps the crudest method, but is very quick and easy to use. In this case,

$$
C V A=M T M\times C r e d i t{\cal S}p r e a d\times D u r a t i o n
$$

This uses the duration to measure how much the fair value of the deal changes by applying the credit spread to the risk-free valuation. It's certainly the 'quick and dirty' method of the bunch, but is fairly well correlated to the other methods.

# DVA - The Next Calculation

CVA was the first universally recognised attempt to apply a simple cost to cut through the various problems of counterparty credit risk and exposure. But it was very soon realised that it was not the whole story. For every transaction, each counterparty will calculate CVA with respect to the other(s). Debit value adjustment (DVA) is the CVA from the perspective of a company's counterparty looking back at the company. When this was first introduced, it was controversial. Why should a company include its own credit risk in a calculation? When the credit quality of a company goes down, its DVA goes up, meaning that deals may be 'cheaper' to do.

However, there are some strong arguments for DVA calculations to be included in the 'cost' of a deal to a trading desk. The main ones are listed as follows.

DVA is needed to arrive at a mid-market value of the deal from both counterparties' points of view (although this must be tempered by the realisation that the DVA that one counterparty calculates is probably not exactly the same as the CVA calculated by the other).
In one way, DVA has always been included when valuing transactions like bonds - lower-credit issuers have to pay a higher credit spread when selling bonds (i.e. make them more valuable).

Finally, in case of a default, a lower credit counterparty would repay only the recovery amount, which is lower for lower credits, so it can be viewed as a benefit to the issuer.

Bilateral valuation adjustment (BVA) is sometimes used to refer to CVA+DVA.

# FVA - Funding Impact

Funding valuation adjustment (FVA) attempts to capture the cost or benefit to the funding situation, though this calculation does tend to overlap with DVA and there is variability in its calculation method among different institutions. It is strongly dependent upon documentation and is generally a function of the nature of the business relationship between the two counterparties. It may in some cases be thought of as the expected loss that the funding company would incur if the counterparty. were to default.

Finally, collateral valuation adjustment (COLVA) attempts to calculate the impact of any posted collateral. This impact is sometimes included in the CVA/DVA calculation.

As these different adjustment quantities arose and were incorporated into valu-. ation frameworks, the catch-all 'acronym' which became used to refer to them as a group was XVA. The X, it must be supposed, just stands for 'anything'. For a useful. discussion of the calculation methods behind the XVA suite, see Ruiz (2015), Greg-. ory (2011) and Ernst and Young (2014).

# How XVA Costs Could Affect the Cross-Currency Basis

All of these various costs mean that some deals, with some counterparties, are more expensive to do than they used to be. Cross-currency swaps are of particular interest. We also examined the post-crisis dislocations in the xccy basis in Chapter 1. Due to their large notional exchange at expiry, they tend to have high risk and therefore XVA costs. However, these are the exact trades which would be used to quickly take advantage of and monetise the arbitrage that is the cross-currency. basis. While there are many other factors driving its generation, the XVA costs are likely to be a large part of the reason it persists in the market..

In Figures 2.3 and 2.4, we show the 5y cross-currency basis for EURUsD and USDJPy. Recall that in the days before the crisis when there was only one valuation curve and no XVA, this would have been seen as a pure arbitrage to be quickly traded on. At current levels, there are about 30 basis points per year available for the 10y trade - something substantial must be in the way of doing these deals.

![](d08308482876daa06655a7bd8373ee697d0dcd8d4791ea08f1e9eed2896c607c.jpg)
Figure 2.3: 5y xccy basis for EURUSD in bp.. Source: Bloomberg, Commerzbank Research

![](dfd0492547d11d21fdc465ed38867ad879a16270ea172df19b8027605223f8f1.jpg)
Figure 2.4: 5y xccy basis for USDJPY in bp. Source: Bloomberg, Commerzbank Research

# Sample XvA Calculation Using Market Standard Calculation Approach

In Table 2.1, we give a set of sample calculations for the cost of doing EURUsD cross-. currency deals from the point of view of a standard market maker, taken from 20 November 2017. The calculations are done assuming a 'standard' counterparty of A(collateralised), BBB(collateralised) and BBB(uncollateralised) credit quality with no. particular degree of offset to other parts of the trading book. The costs are all annualised in basis points. Note that the total deal cost is calculated as max(A,. $\mathrm{B+C})+\mathrm{D+E},$ where $\mathrm{A}=$ Net CVA, $\mathrm{B}=$ Rating CVA, $\mathrm{C}=\mathrm{Cost}$ of Capital, $\mathrm{D}=\mathrm{FVA}$ $\mathrm{E}=$ EU Bank Levy.

Table 2.1: Sample XVA calculations from 20 November 2017, in bp annually.


<html><body><table><tr><td>EURUSDXCCy XVA charges</td><td>A(c) 10y</td><td>A(c) 5y</td><td>A(c) 2y</td><td>BBB(c) 10y</td><td>BBB(C) 5y</td><td>BBB(c) 2y</td><td>BBB(u) 10y</td><td>BBB(u) 5y</td><td>BBB(u) 2y</td></tr><tr><td>Net CVA</td><td>0.4</td><td>0.2</td><td>0.1</td><td>1.3</td><td>1.3</td><td>0.9</td><td>17.0</td><td>6.6</td><td>1.1</td></tr><tr><td>Rating CVA</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.3</td><td>0.3</td><td>0.3</td><td>3.1</td><td>2.0</td><td>1.1</td></tr><tr><td>FVA</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.1</td><td>0.1</td><td>4.1</td><td>2.4</td><td>1.1</td></tr><tr><td>CostofCapital</td><td>1.2</td><td>1.0</td><td>0.8</td><td>1.2</td><td>1.6</td><td>2.0</td><td>7.8</td><td>6.2</td><td>3.3</td></tr><tr><td>EUBankLevy</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.1</td><td>0.1</td><td>0.0</td></tr><tr><td>TotalDealCost</td><td>1.3</td><td>1.1</td><td>0.8</td><td>1.5</td><td>1.9</td><td>2.5</td><td>21.1</td><td>10.7</td><td>5.5</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

What can we take from this table?

CVA is higher for longer-term deals.
CVA and FVA are higher for lower-credit counterparties.
Collateral makes a large difference - the total cost of uncollateralised deals is many times that of the same deal with posted collateral.

Let us take the 10y xccy swap as a benchmark. The table tells us that the XVA cost. of doing this deal with an AA, BBB(c) or BBB(c) counterparty would be 1.3, 1.5 or 21 bp. On that day (20 February 2017), the EURUSD 10y basis swap traded at $^{-38}$ bp. Thus, on the surface, Commerzbank would be delighted to do this deal! Even most conservatively, there would have been about 20 bp of profit to be made - and it is likely that our counterparties to this trade would be better credits than BBB, and that we would use collateral, so 30 bp is a more realistic figure..

This seems odd. Much has been made of the impact of regulatory capital and. XVA on the cross-currency basis. But our own, fairly conservative calculations indi-. cate that these charges are not nearly large enough to cause the substantial basis. we see in the market. We are not alone in our calculations of these costs - in EBA (2014), we see that the European Banking Authority has made similar estimates of. CVA and regulatory costs.

Can we gain an indication of whether 20 November 2017 is an outlier? Although there is nothing very precise available, we can 'scale' the CVA part of the trade costs,. assuming that the other costs stay approximately constant. A reasonable index to use. when scaling CVA might be the Markit ITraxx Europe Senior Financial Index (SNRFIN 5Y on Bloomberg), which comprises 30 equally weighted CDS spreads on investment. grade European financial entities. If we look back at all the equations for the CVA calculations, it's clear that it should roughly scale with CDS spreads in all cases. Thus, we take the value of this index on 20 November, and scale other CVA values in the time series by the ratio of the index value on that date to the value on other dates.

The following chart in Figure 2.5 perhaps raises more questions than it answers. We have used the BBB uncollateralised credit 10y CVA charge as a benchmark..

![](2cde15024a7f734145322fa35cbc8484619c2486ae6dd33275ec6e06c6cd096f.jpg)
Figure 2.5: 10y BBB xccy basis and uncollateralised trade cost, in bp. Source: Bloomberg, Commerzbank Research

Xccy basis is plotted as positive number, though usually it would be negative.

Prior to 2014, we could have made a case that XVA charges and the xccy basis were strongly related, and that the basis was to some extent limited by the charges.. We would expect the conservative uncollateralised BBB costs to provide a safe upper. bound, which does indeed seem to be the case. The two were highly correlated and the basis did not seem to move too far away. But from 2014 to 2019, this useful relationship breaks down, with the basis rising sharply while the XVA costs are low and fairly stable. After that point, the two series maintain similar lower levels but with little apparent correlation. It is difficult to believe, from this evidence, that XVA costs. and the basis are strongly connected.

# Funding Constraints

To finally understand what stops market participants from taking advantage of the cross-currency basis, we turned to the trading desk and the mechanics of doing such a deal. Let us assume that a rookie trader decides that he or she is going to trade the xccy basis and make some money on it.

The following data is taken from trading screens on 6 July 2017, for deals with start date 10 July 2017 and end date 10 July 2018 (interest rates are 1y IRS/3M).

EUR interest rate -0.30%
USD interest rate $1.48\%$
Spot FX Rate 1.1423
Market FX Forward Rate 1.1660 (forward points are 237)
Implied FX Forward 1.1626 (implied from interest rates)

The implied forward is calculated using the expression

$$
{\frac{F X2}{F X1}}={\frac{1+r_{2}}{1+r_{1}}}
$$

where

$\mathrm{FX}1=$ Spot FX rate $\mathrm{FX}2=$ 1y implied forward FX rate $\mathbf{r}_{2}=\mathrm{USD}$ 1y interest rate ${\bf r}_{1}=\mathrm{EUR}$ 1y interest rate

This expression is famously broken' by the existence of the xccy basis - prior to 2008, the implied forward rate was always very close to the actual market rate. The. xccy basis here is often quoted as a spread to the implied forward, so in this case it. would be 33 forward pips'. This translates back to an interest rate spread of $^{-28}$ basis points - so one could also imply a USD 1y interest rate of $1.48\%+0.28\%=1.76\%.$ The negative sign attached to the basis is due to the fact that the xccy basis is quoted as a. spread to the non-USD interest rate. Thus, if one applied the 'correction' to the EUR. interest rate, it would come out as. $-0.58\%$

What does our hypothetical rookie trader think? This is what might be going through his or her head: The difference between the interest rate derived FX forward and the actual traded forward is 33 forward pips, or $^{-28}$ basis points. So, I will do the two interest rate contracts, and the actual traded forward, to lock in the basis.'

But now, reality begins to bite. These interest rates are NOT depo rates. They are 1y swap rates vs 3m Libor. The USD depo rate is about 28 basis points higher, at $1.77\%$ . This is one way of appreciating that the basis (expressed like this) is due to credit. With a swap, the principal is never at risk, only the differences between fixed and floating rates. With a deposit, the principal is at risk, and the rate is higher. So our hopeful trader cannot borrow and lend at these rates at all. This is part of the 'multiplication of curves' which we mentioned right at the start - the yield curve for swaps (less credit risk) and for deposits (more credit risk) are not the same, whereas before the crisis, they were almost the same.?

Ok, says the still-hopeful trader. Let's do the two interest rate components of this set of deals with two fixed-floating IRS. Fine, we can now access these interest rates.

But because the trader is not doing the deposit contracts, he or she will have to fund the cashflows, so he or she will need to hold the principal amount on the books until the deal expiry. This needs to be funded. Oh no! That means accessing the deposit market once more - and the deposit rates include the basis. There is no escape -- the poor trader will have to borrow at an effective rate close to that available in the deposit market. Even though a trading desk usually funds by rolling overnight or short-term, the implied forward cost of the accumulated overnight funding will still add up not to the 1y swap rate, but to something like the 1y depo rate.' So, though there is uncertainty, as the overnight rate may of course change over the course of the deal, it is not possible to lock in a profit, and the implied $\mathrm{P/L}$ is flat.

Before the crisis, the trader would have funded at Libor, and the depo and swap rates would have been very little different, so if a basis had existed, it would have been a good opportunity for arbitrage.

In Figure 2.6, we show the 1y US swap rate and deposit rate since 2000, and the spread between them together with the xccy basis is shown in Figure 2.7. It's clear that they are closely connected though not identical, as the basis also responds to pressure from the EUR side.

![](d0a5f2933f0e8a23a424b8d8854eecb1118aa9877f807013c56ae6c7b92965b1.jpg)
Figure 2.6: 1y USD swap rate and deposit rate. Source: Bloomberg, Commerzbank Research

![](ca424602691eb485e6b682533ea2d0aafca8021de44ff877bf5e7ca4b3db74fb.jpg)
Figure 2.7: 1y USD swap-deposit spread, with 1y xccy EURUSD basis. Source: Bloomberg, Commerzbank Research

Now, as our young trader, now a little older and wiser, sadly abandons plans to make money on the basis, is there anyone who can do the trade? Yes! Under some circumstances, bank Treasuries can borrow at close to the swap rates from the central banks. This is one way that central banks inject liquidity. So these desks can make a profit from this situation. Similarly, some high-quality credits can do it or can come close. Our previous paper shows in detail how some entities (for example, large investors or insurance companies) can at times lock in at least part of the basis when hedging fixed income investments.' There is an excellent analysis in Rime, Schrimpf and Syrstad (2017), which shows that the very top-tier banks in some markets have, at some points in the past, been able to fund at levels that allow them to treat the xccy basis as at least a partial arbitrage. The current situa-. tion is such that the arbitrage may still be available, though it is narrower than it has been at other times. Thus, there is pressure on the basis not to widen too far, but not the kind of old-style risk-free arbitrage pressure..

Would it ever make sense for our trader to do this trade? Yes, indeed. If the. basis widened too far, he or she might put on the trade believing that the actual funding (as opposed to the implied) would not stay at these elevated levels. But it would be a trade with risk attached, and not a traditional arbitrage..

Thus, pressure on the basis not to widen has no hard' level at which it comes in. Those who can make risk-free money on the basis do so only because they can access cheap UsD funding. Those who make money on the basis with a risk-based trade do so because they correctly judge when it is too extended. The basis is a natural consequence of greater sensitivity to credit risk, and demand for and access to USD. For a useful discussion of forces operating on the basis, see Rime, Schrimpf and Syrstad (2017) and Borio et al. (2016), and for an excellent explanation of multiple curve discounting, see Hull (2014).

# Detail on Daily Funding/Rollover Process

In the previous section, we described how a trader might 'attempt' to capture the xccy basis - and fail. In fact, though this broad-brush description is correct, it may be of interest to go into some detail about how the actuality of the daily rolling and funding occurs. A detailed diagram of the process may be found in the online appendix of Rime, Schrimpf and Syrstad (2017), but it may be useful to add some numbers in.

Rather than funding the future cashflow for the whole tenor of the deal, the desk operates on a shorter-term basis. They will fund the future cashflow for short periods, often overnight (O/N). It is important to realise that the funding of the cashflow is like a miniature of the larger deal; both an interest rate component and a forward FX com-. ponent are involved. Thus the $\mathrm{{0/N}}$ funding cost is usually measured in forward points,. which are the overnight levels for the FX forward. These are usually not annualised.

We have said that the cost of funding the cashflow ends up adding to the xccy basis. This is true but is more complex for the. $\mathrm{{0/N}}$ case. Essentially, the implied. curve of the $0/\mathrm{N}$ forward rates incorporates both the OIS currency rates and the FX. forward. Figure 2.8 is the graph of the entire 1-day forward-forward implied curve,. as calculated by Commerzbank's STIRT desk, for 6 July 2017. It is derived from various averages over different number of days - from 2 to 15 - with the greater granu-. larity around points of interest like the turn of the year. Thus, we would expect it to look smoother than the actual historical forward in Figure 2.9, but otherwise should. show similar features.

![](1652060304a5eeec65a6cbf5ce03dd3b768d32e657a261fe1e00d3594c1616c9.jpg)
Figure 2.8: 1-day EURusD forward-forward curve in forward points. Source: Bloomberg, Commerzbank Research

![](bb711b9e01ceb9013dd48e5390e9c601d92a6594d18202a4a1b358c17c130fca.jpg)
Figure 2.9: 1-day historical FX forward.. Source: Bloomberg, Commerzbank Research

These two graphs are informative. On 6 July 2017, the forward points are 0.55. This is the difference between the market forward FX rate for 1 day and the spot rate. Harking back to our earlier calculation, this looks very optimistic for the arbitrage trade. If we can fund at this level for the whole deal, then. $0.55\times365=201.$ But the actual forward points for a 1-year deal are 237. To get to this number, the difference between the 1y forward (1.166) and the spot (1.142) is 0.0237; multiply this by 10,000 to get the forward points as they are quoted by the market. We can make this money. (which comes out to about $0.28\%$ of notional) if these points remain stable!.

But they don't. From the Commerzbank STIRT desk, we obtained the implied curve for that day, going out to 1 year. As seen in Figure 2.9, various spikes at times of high USD demand are priced in. This means that we need to look at the average for the year - and it comes out at 0.63 forward points, which is 230 forward points over the year, which leaves us with very nearly nothing!

But has it been correct? Well, we can also look at historical $0/\mathrm{N}$ rates - and they say the same thing. Figure 2.10 shows the actual historical levels of these over the last year. It is more active than the desk-supplied forward curve, as it includes the change in levels over each weekend, which the forward curve from the desk smooths out with averaging. But in fact, it averages out to exactly O.63 forward points as well - though this is in the past, it is certainly consistent with the idea that it has not been possible to make money.

# Historical Funding Data

We have shown that for an 'average' trading desk, it's unlikely that they will be able to lock in a profit from trading the cross-currency basis. It seems likely, however, that some institutions may have occasional situations which will enable them to lock in a profit. It is important to note that for the situation of a trading desk, with a. daily roll and funding process, profits will be made only over these short periods; a. brief arbitrage may well exist if the desk can borrow or lend for a day or two at better than market rates.

Very fortunately, we have access to the internal Commerzbank funding levels available from late 2008 to 2017. Specifically, we have access to Treasury rates made available to the internal trading desks for different currencies. This is not quite the same as the rates the desks dealt at, since they also had the option of trading outside of the bank, but it is an excellent indication of supply and demand as seen by a large German commercial bank. We use this to calculate the forward points available to the desk.

The forward points are the difference between the forward FX rate and the spot FX rate. Using the previous notation, we can say:

$$
{\mathrm{Forward~Points}}=F X2-F X1
$$

But we know:

$$
{\frac{F X2}{F X1}}={\frac{1+r_{2}}{1+r_{1}}}
$$

So, we can say:

$$
\begin{array}{r l}&{\mathrm{ForwardPoints}=F X1\left(\displaystyle\frac{1+r_{2}}{1+r_{1}}-1\right)}\ &{}\ &{\mathrm{ForwardPoints}=F X1\left(\displaystyle\frac{r_{2}-r_{1}}{1+r_{1}}\right)\times10,000}\end{array}
$$

The additional factor of 1o,ooo is usually applied to make the number easier to handle.

As we have the internal time series for $\mathfrak{r}_{1}$ and ${\bf r}_{2}$ available (in this case for EUR and UsD), plus the spot FX rate FX1, this allows us to create Figures 2.10 and 2.11, where we compare the effective forward points available to the desk with the overnight and Tom/Next forward points available in the market. We show both cases, as the tenor of the internal rate varies between them.

First of all, it's clear that at some points in time some desks can lock in a short-. dated profit. There are clearly days where the internal rates differ somewhat from market rates - for a trader with the right positioning, this is good news..

This is perhaps to be expected - part of the job of a trading desk is to pick up on short-term discrepancies. But we can learn something from the overall pattern of the discrepancies, which may probably be generalised to most substantial investment banks.

Let's first summarise how a trading desk will see things.

![](9532c4db55c8f419475d285f597cbd8bbec91dbb26857c59f2c67b442bbf8e0c.jpg)
Figure 2.10: Internal forward points vs market $0/\Nu$ in $\%$ Source: Bloomberg, Commerzbank Research

![](827d34ae5a5ef7aedb0b6fbd3a45351f060db571ec04723ba575bd526e260790.jpg)
Figure 2.11: Internal forward points vs market $T/N$ in $\%$ Source: Bloomberg, Commerzbank Research

If you are LONG USD/SHORT EUR, you want the points to be higher - i.e. 55 rather than 50 (you need to lend out the USD and get the EUR in for as many pips as you can). If you are SHORT USD/LONG EUR, you want the points to be lower - i.e. 50 rather than 55. The points are currently positive, as EUR rates are below USD. in the case where EUR rates are higher, the points will be negative, but the same rationale applies - with LONG USD/SHORT EUR, you want a bigger NEGATIVE number (you want to lend out the UsD at as big a number as you can ie -45 not $-40\AA$ , and with SHORT USD/LONG EUR, you want a less negative number $\left(-40\mathrm{not}-45\right)$

What do we see in the graphs? When USD rates are higher than EUR, generally the.
internal points are less positive. When USD rates are lower than EUR, the internal.
points are less negative. This is a disadvantage to those who are overall long of USD.

This can be seen as part of an internal redistribution process, as on average, most. of the trading desks will tend to be long of USD - for example, oil and many other commodities are valued in UsD, and it is one of the most important tactical and strategic risk currencies. Conversely, the Treasury is likely to be long of EUR overall. This means that it can generate interest income when the EUR has positive interest rates, but it is costly when there are negative rates. Thus, as the Treasury needs to manage. its own position, it will offer a higher spread to the internal trading desks in positive periods (flow from desk to Treasury) and a lower spread to the desks in negative periods (flow from Treasury to desk). The desks in turn will hope to make money by short-term management of positions, often including short-dated carry..

# Trading the xccy Basis

With a last look at our trader, let's see when the risk-based trade would have been profitable over time. If the trader puts on the trade assuming that the basis is too large and will close up, then there's an easy way to approximate the. $\mathrm{P/L}$ that the trade would make - look at the average levels of the basis over the next year. Figure 2.12 is a. chart of the xccy basis vs its average level for the following year, and the difference. between them. Note that this is only an indication of the profit of the trade, as we ought to strictly look at trades whose tenor shortens towards the end of the deal, but it will be good enough to give us an indication..

![](42a8f759aa9e4372e2973528f4e6bf13a1cb3830d1967332d4e20c804f227e52.jpg)
Figure 2.12: Indication of profitability of xccy basis trade. 1y tenor, all in bp. Source: Bloomberg, Commerzbank Research

It can be seen that positioning for the transient nature of large basis spikes has been generally beneficial. In Table 2.2, we also tabulate the average profit per trade if it is entered at different levels.

Table 2.2: Average profit per trade.


<html><body><table><tr><td>Level where trade is entered (bp)</td><td>-10</td><td>-20</td><td>-30</td><td>-40</td><td>-50</td><td>-60</td><td>-70</td><td>-80</td></tr><tr><td>Average profit per trade in bp</td><td>0.97</td><td>2.20</td><td>6.51</td><td>14.54</td><td>22.48</td><td>26.40</td><td>30.21</td><td>35.00</td></tr><tr><td>Numberoftrades</td><td>1959</td><td>1612</td><td>884</td><td>491</td><td>289</td><td>182</td><td>106</td><td>56</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Though the trade has been profitable overall, this has varied with the time period. But its substantial profitability at entry levels of 40 or greater mean that we might expect trading pressure to close up the basis being strongly felt at that point..
