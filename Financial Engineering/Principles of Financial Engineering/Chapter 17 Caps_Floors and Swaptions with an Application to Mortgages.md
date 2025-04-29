# CAPS/FLOORS AND SWAPTIONS 17 WITH AN APPLICATION TO MORTGAGES  

# CHAPTER OUTLINE  

7.1 Introduction .. . 591   
17.2 The Mortgage Market .. 592   
17.2.1 The Life of a Typical Mortgage 593   
17.2.2 Hedging the Position . 597   
17.2.3 Assumptions Behind the Model . 597   
17.2.4 Two Risks ... 598   
17.3 Swaptions... . 599   
17.3.1 A Contractual Equation . 601   
7.4 Pricing Swaptions .. 601   
17.4.1 Swap Measure.. . 601   
17.4.2 The Forward Swap Rate as a Martingale . . 604   
17.4.3 Swaption Value . 605   
17.4.4 Real-World Complications .. . 607   
17.5 Mortgage-Based Securities. .. 607   
7.6 Caps and Floors .. 608   
17.6.1 Pricing Caps and Floors 610   
17.6.2 A Summary.. . 612   
17.6.3 Caplet Pricing and the Smile . 612   
17.7 Conclusions.. 613   
Suggested Reading . .. 613   
xercises . . 613   
EXCEL Exercises . 617  

# 17.1 INTRODUCTION  

In the previous chapters, we discussed convexity and options as well as their applications in the form of volatility trading. The US mortgage market provides us with another application of a long convexity position as a result of the prepayment option of US homeowners. We carefully explain the value of the prepayment option and its effect on mortgage agencies and discuss potential approaches to hedge this risk. As we will see the structure of the US mortgage market and the presence of a mortgage prepayment option, in particular, leads to optionality and convexity in payoffs.  

Swap markets rank among the world’s largest in notional amount and are among the most liquid. The same is true for swaption markets. Why is this so?  

There are many uses for swaps. Borrowers “arbitrage” credit spreads and borrow in currencies that yield the lowest all-in-cost. This, in general, implies borrowing in a currency other than the one the borrower needs. The proceeds, therefore, need to be swapped into the needed currency. Theoretically, this operation can be done by using a single currency swap where floating rates in different currencies are exchanged. Currency swaps discussed in Chapter 6 are not interest rate swaps, but the operation would involve vanilla interest swaps as well. Most issuers would like to pay a fixed long-term coupon. Thus, the process of swapping the proceeds into a different currency requires, first, swapping the fixed coupon payments into floating in the same currency, and then, through currency swaps, exchanging the floating rate cash flows. Once the floating rate payments in the desired currency are established, these can be further swapped into fixed payments in the same currency. Thus, a new issue requires the use of two plain vanilla interest rate swaps in different currencies coupled with a vanilla currency swap. Hence, new bond issues are one source of liquidity for vanilla interest rate swaps.  

Balance sheet management of interest exposure is another reason for the high liquidity of swaps. The asset and liability interest rate exposure of financial institutions can be adjusted using interest rate swaps and swaptions. If a loan is obtained in floating rates and on-lent in fixed rate, then an interest rate swap can be entered into and the exposures can be efficiently managed. FRAs, swaps, caps, floors and swaptions are traded on many liquid currencies and their existence in these countries is not chiefly driven by mortgage market driven.  

In some countries and cases, the uses of swap markets can be matched by the needs of mortgagebased activity. It appears that a major part of the swaption and a significant portion of plain vanilla swap trading in the US are due to the requirements of the mortgage-based financial strategies. In this chapter we focus on the US mortgage market for the purpose of illustrating the link between option markets and the market for the underlying. Mortgages have prepayment clauses and this introduces convexities in banks’ fixed-income portfolios. This convexity can be hedged using swaptions, which creates liquidity in the swaption market. On the other hand, swaptions are positions that need to be dynamically hedged. This hedging can be done with forward swaps as the underlying. This leads to further swap trading. Mortgage markets are huge and this activity can sometimes dominate the swap and swaption markets.  

In this chapter, we use the mortgage sector as an example to study the financial engineering of swaptions. We use this to introduce caps/floors and swaptions. The chapter also presents a simple discussion of the swap measure. This constitutes another example of measure change technology introduced in Chapter 12 and further discussed in Chapters 13 and 14. This chapter provides an example that puts together most of the tools used throughout the text. We start by first reviewing the essentials of the mortgage sector.  

# 17.2 THE MORTGAGE MARKET  

Lenders such as mortgage bankers and commercial banks originate mortgage loans by lending the original funds to a home buyer. This constitutes the primary mortgage market. Primary market lenders are mortgage banks, savings and loan institutions, commercial banks, and credit unions.  

These lenders then group similar mortgage loans together and sell them to Fannie Mae or Freddie Mac-type agencies. This is part of the secondary market which also includes pension funds, insurance companies, and securities dealers.  

Agencies buy mortgages in at least two ways. First, they pay “cash” for mortgages and hold them on their books.1 Second, they issue mortgage-backed securities (MBSs) in exchange for pools of mortgages that they receive from lenders. The lenders can in turn either hold these MBSs on their books, or sell them to investors. To the extent that mortgages are converted into MBSs, the purchased mortgage loans are securitized.2 Agencies guarantee the payment of the principal and interest. Hence, the “credit risk” is borne by the issuing institution.3 We now discuss the engineering of a mortgage deal and the resulting positions. As usual, we use a highly simplified setting.  

# 17.2.1 THE LIFE OF A TYPICAL MORTGAGE  

The process from home buying activity in the US to hedging swaptions is a long one, and it is best to start the discussion by explaining the mechanics of primary and secondary mortgage markets. The implied cash flow diagrams eventually lead to swaption positions. The present section is intended to clarify the sequence of cash flows generated by this activity. We will see that, at the end, the prepayment right amounts to holding a short position on a swaption. This is from the point of view of an institution that holds the mortgage and finances it with a straight fixed rate loan. Essentially, the institution sold an American-style option on buying a fixed payer swap at a predetermined rate. The option is exercised when the future mortgage rates fall below a certain limit.4  

The interrelationships between home buying, mortgage lending, and agency activity are shown in Figures 17.1 17.3. We go step by step and then put all the positions together in Figure 17.3 to obtain the consolidated position of the mortgage warehouse. We prefer to deal with a relatively simple case which can then be generalized. Some of these generalizations are straightforward, others involve considerable problems.  

We consider the following setup. A balloon mortgage is issued at time $t_{0}$ .5 The mortgage holder pays only interest and returns the principal at maturity. The mortgage principal is $N$ , the rate is $c_{t_{0}}$ , and the mortgage matures at $t_{4}$ . The $t_{i},i=1,...,4.$ , is measured in years.6 We emphasize that, with such a balloon mortgage, the periodic payments are made of interest only and no amortization takes place. This simplifies the engineering and permits the use of plain vanilla interest rate swaps.  

The home buyer makes four interest payments and then pays the $N$ at time $t_{4}$ if he or she does not prepay during the life of the mortgage. On the other hand, if the mortgage rate $c_{t}$ falls below a  

![](1ca4cfb078802f6252a9ca73dfee64ad7d271db558adfb38372230c58eb106bc.jpg)  

# FIGURE 17.1  

Mortgage agency and home buyer cash flows.  

threshold level at a future date, the home buyer refinances. We assume that the home buyer can prepay only at time $t_{2}$ . When the loan is paid at time $t_{2}$ , it is replaced by a new mortgage of two periods7 that carries a lower rate. This situation is shown in Figure 17.1.  

The bank borrows at the floating LIBOR rate, $L_{t_{i}}$ , and lends at the fixed rate, $c_{t_{0}}$ . Then the mortgage is sold to an agency such as Fannie Mae or to some other mortgage warehouse. The bank will only be an intermediary and earns a fee for servicing mortgage payments.  

The interesting position is that of the agency that ends up with the mortgage. The agency buys the mortgage and puts it on its books. This forms the asset side of its balance sheet. The issue is how these secondary market purchases are funded. In reality, there is more than one way. Some of the mortgages bought in the secondary market are kept on the books, and funded by issuing agency securities to investors. Other mortgages are packaged as MBS, and resold to end investors.  

![](0c1cd4e11844361fc7104abfcbd5eda9494bce7b3ed9a77bddd4fc06182d4c42.jpg)  

# FIGURE 17.2  

Mortgage agency asset and liability side and prepayment risk.  

Suppose in our case the agency uses a 4-year fixed coupon note to secure funding at the rate $c_{t_{0}}$ . The liabilities of the agency are shown in Figure 17.2. The asset side is shown in the lower part of this figure. The critical point is the prepayment issue. According to Figure 17.2b, the agency faces a prepayment risk only at time $t_{2}$ .8  

If the home buyer does not refinance, the agency receives four interest payments of size $c_{t_{0}}N$ each, then, at time $t_{4}$ receives the principal. We assume that the home buyer never defaults.9 If, on the other hand, the home buyer pays the “last” interest payment $c_{t_{0}}N$ and prepays the principal earlier at time $t_{2}$ , the agency places these funds in a floating rate money market account until time $t_{4}$ . The rate would be $L_{t_{i}}$ . Alternatively, the agency can get into a fixed receiver swap and receive the  

![](ffa783e5f9e03ac50176b99d4fd7e389bebbd84b8af0e9a01efc19a41a32e77a.jpg)  

# FIGURE 17.3  

Prepayment results in long fixed payer forward swap position.  

swap rate beginning at time $t_{3}$ . This swap rate is denoted by $s_{t_{2}}$ . This explains the cash flows faced by the agency in case the home buyer prepays.  

The asset and liability positions of the agency are consolidated in Figure 17.3. We see that all cash flows, except the ones for the prepayment case, cancel. Figure 17.3 shows that if the home buyer prepays, the agency will be long a fixed payer forward swap at the predetermined swap rate $c_{t_{0}}$ . If no prepayment occurs, the agency will have a flat position.  

Now assume for simplicity, and without much loss of generality, that the swap rates and mortgage rates are equal for all $t{\mathrm{.}}$ :  

$$
c_{t}=s_{t}
$$  

Then, the final position of the agency amounts to the following contract.  

The agency has sold the right to enter into a fixed receiver swap at the predetermined rate $c_{t_{0}}$ to a counterparty. The swap notional is $N.$ , the option is European,10 and the exercise date is $t_{2}$ . The underlying cash swap has a life of 2 years. The agency is short this option, and would be a fixed payer in case the option is exercised.  

This contract is a swaption. The agency has sold an option on a swap contract and is short convexity. The home buyer is the counterparty, and he or she is long convexity. The option is exercised if $s_{t_{2}}\leq c_{t_{0}}$ . The option premium is $S w_{t_{0}}$ .11 It is paid at time $t_{0}$ .12 According to this, we are ignoring any transaction costs or fees.  

# 17.2.2 HEDGING THE POSITION  

The important point of the exercise in the previous section is that, after all the dust settles, the agency faces prepayment risk and this results in a short swaption position. The short European swaption position can be hedged in several ways. One option is direct dynamic hedging. The hedger would (i) first calculate the delta of the swaption, and then, (ii) buy delta units of a 2-year forward-receiver swap with start date $t_{2}$ .13  

After following these steps, the agency will have a short convexity position, which is also a short position on volatility. If volatility increases, the agency suffers losses. In order to eliminate this risk as well, the agency has to buy convexity from the market. Another way to hedge the short swaption position is to issue callable bonds, and buy the convexity directly from the investors.  

# EXAMPLE  

Fannie Mae Callable Benchmark Notes will have a notional of at least US\$500m and a minimum reopening size of US\$100m. There will be at least one issue per month and four main structures will be used: a fiveyear, non-call two; a five-year, non-call three; a 10-year, non-call three; and a 10-year, non-call five. The volume and regular issuance pattern of the program is expected to depress volatility. Agencies have always had a natural demand for volatility and this has traditionally been provided by the banking community. But with the invention of the callable benchmark issuance program, agencies have instead started to source volatility from institutional investors.  

(Thomson Reuters IFR, Issue 1291)  

Finally, as an alternative to eliminate the short swaption position, the agency can buy a similar swaption from the market.  

# 17.2.3 ASSUMPTIONS BEHIND THE MODEL  

The discussion thus far has made some simplifying assumptions, most of which can be relaxed in a straightforward way. Some assumptions are, however, of a fundamental nature. We list these below.  

1. It was assumed that the home buyer could finance only at time $t_{2}$ . The resulting swaption was, therefore, of European style. Normally, home buyers can finance at all times at $t_{1},t_{2}$ , and $t_{3}$ . This complicates the situation significantly. The same cash flow analysis can be done, but the underlying swaption will be of Bermudan style. It will be an option that can be exercised at dates $t_{1},t_{2}$ , or $t_{3}$ , and the choice of the exercise date is left to the home buyer. This is not a trivial extension. Bermudan options have no closed-form pricing formulas, and pricing them requires more advanced techniques. The presence of an interest rate volatility smile complicates things further.  

2. The reader can, at this point, easily “add” derivatives to this setup to create mortgages seen during the credit crisis of 2007 2008. We assumed, unrealistically, that there was no credit risk. The home buyer, or the agency, had zero default probability in the model discussed. This assumption was made for simplifying the engineering. As the credit crisis of 2007 2008 shows, mortgages can have significant credit risk, especially when they are not of “vanilla” type.  

3. The mortgage was assumed to be of balloon style. Normally, mortgages amortize over a fixed period of, say, 15 or 30 years. This changes the structure of cash flows shown in Figures 17.1 17.3. The assumption can be relaxed by moving from the standard plain vanilla swaps to amortizing swaps. This may lead to some interesting financial engineering issues which are ignored in the present text.  

Finally, there are the issues of transaction costs, fees, and a more general specification of the maturities and settlement periods. These are relatively minor extensions and do not change the main points of the argument.  

# 17.2.4 TWO RISKS  

According to the preceding discussion, there are two risks associated with prepayments. One is that the bank or the issuing agency will be caught long a payer swap in the case of prepayment. If this happens, the agency would be paying a fixed rate, $c_{t_{0}}$ , for the remainder of the original mortgage maturity, and this $c_{t_{0}}$ will be more than the prevailing fixed receiver swap rate.14 The agency will face a negative carry of $s_{\tau}-c_{t_{0}}<0$ for the remaining life of the original mortgage, where $\tau$ is the random prepayment date.  

The second risk is more complicated. The agency does not know when the prepayment will happen. This means that, when mortgages are bought, the agency has to estimate the expected maturity of the mortgage. Then, based upon this expected maturity, notes with fixed maturity are sold. The liability side has, then, a more or less predictable duration,15 whereas the asset side has an average maturity that is difficult to calculate. The example below illustrates how such problems can become very serious.  

# EXAMPLE  

As rates rally, mortgage players become more vulnerable to call risk, which leads to a shortening of their asset duration, as occurred in September. “The mortgage supply into the street has been very heavy, so there has been an overall buying of volatility to hedge convexity risk from both Freddie and Fannie,” says the chief strategist of a fixed-income derivatives house. The refinancing boom has already caught out some mortgage players. A New Jersey-based arbitrage fund specializing in mortgage securities, announced losses of around \$400 million at the end of October. Analysts say the fund had not adequately hedged itself against the rate rally.  

While some speculated that criticism of Fannie Mae’s duration gap—the difference between the maturity of its assets and its liabilities—in the media would lead speculators to position themselves to benefit from the agency’s need to hedge, this was not a serious contributor to the increase in volatility.  

However, with the big increase in its mortgage portfolio, Fannie Mae, and indeed Freddie Mac, which has also been building up its mortgage portfolio, now faces the increased threat of extension risk—the risk of mortgage assets lengthening in duration as yields increase and prepayments decrease. Fannie Mae’s notional derivatives exposure stood at $\$594.5$ billion at the end of June, while Freddie reported a total derivatives exposure of $\$12$ trillion.  

(Based on an article in Derivatives Week (now part of GlobalCapital).)  

Of the two risks associated with trading and warehousing mortgages, the first is an issue of hedging convexity positions, whereas the second involves the Americanness of the implicit prepayment options.  

# 17.3 SWAPTIONS  

Mortgages form the largest asset class that households own directly or indirectly. The total mortgage stock is of similar size as the total US Treasury debt. Most of these mortgages have prepayment clauses, and this leads to massive short swaption positions. As a result, Bermudan swaptions become a major asset class. In fact, mortgages are not the only instrument with prepayment clauses. Prepayment options exist in many other instruments. Callable and putable bonds also lead to contingent, open-forward swap positions. These create similar swaptions exposures and can be fully hedged only by taking the opposite position in the relevant swaption market. Given the important role played by swaptions in financial markets, we need to study their modeling. This section deals with technical issues associated with European swaptions.16  

A swaption can be visualized as a generalization of caplets and floorlets. The caplet selects a floating LIBOR rate, $L_{t_{i}}$ , for one settlement period, such that, if $L_{t_{i}}$ is greater than the cap rate $\kappa$ written in the contract, the caplet buyer receives compensation proportional to the difference. We can generalize this. Select a floating swap rate for $n$ periods. If the time $t_{1}$ value of this swap rate denoted by $s_{t_{1}}$ is greater than a fixed strike level, $f_{t_{0}}=\kappa$ , the buyer of the instrument receives payments proportional to the difference. Thus, in this case both the “underlying interest rate” and the strike rate cover more than one period and they are forward swap rates. A fixed payer swaption can then be regarded as a generalization of a caplet. Similarly, a fixed receiver swaption can be regarded as a generalization of a floorlet.  

Let us look at this in more detail. Consider a European-style vanilla call option with expiration date $t_{1}$ . Instead of being written on equity or foreign exchange, let this option be written on a plain vanilla interest rate swap. The option holder has the right to “buy” the underlying at a selected strike price, but this underlying is now a swap. In other words, the option holder has the right to enter into a payer swap at time $t_{1}$ , at a predetermined swap rate $\kappa$ . The strike price itself can be specified either in terms of a swap rate or in terms of the value of the underlying swap.  

Let $t_{0}$ be the trade date. We simplify the instrument and consider a two-period forward interest rate swap that starts at time $t_{1}$ , with $t_{0}<t_{1}$ , and that exchanges two fixed payments against the 12-month LIBOR rates, $L_{t_{1}}$ and $L_{t_{2}}$ Let the forward fixed payer swap rate for this period be denoted by $f_{t_{0}}$ . The spot swap rate, $s_{t_{1}}$ , will be observed at time $t_{1}$ , while the forward swap rate is known at $t_{0}$ .  

The buyer of the swaption has thus purchased the right to buy, at time $t_{1}$ , a fixed payer (spot) swap, with nominal value $N$ and payer swap rate $f_{t_{0}}$ . If the strike price, $\kappa$ , equals the ongoing forward swap rate for the time $t_{1}$ swap, this is called an ATM swaption. A forward fixed payer swap is contracted at time $t_{0}$ . The forward swap rate $f_{t_{0}}$ is set at time $t_{0}$ , and the swap will start at time $t_{1}$ . The corresponding spot swap can be contracted at time $t_{1}$ . Thus, the swap rate $s_{t_{1}}$ is unknown as of $t_{0}$ .  

The ATM swaption involves the following transactions. No cash changes hands at time $t_{1}$ . The option premium is paid at $t_{0}$ . If at time $t_{1}$ the spot swap rate, $s_{t_{1}}$ , turns out to be higher than the strike rate $f_{t_{0}}$ , the swaption holder will enter a fixed payer swap at the previously set rate $f_{t_{0}}$ . If the time $t_{1}$ spot swap rate $s_{t_{1}}$ is below $f_{t_{0}}$ , the option holder has an incentive to buy a new swap from the market since he or she will pay less. The swaption expires unexercised. Thus, ignoring the bidask spreads, suppose, at time $t_{1}$ ,  

$$
f_{t_{0}}<s_{t_{1}}
$$  

the 2-year interest rate swap that pays $s_{t_{1}}$ against 12-month LIBOR will have a zero time $t_{1}$ value. This means that at time $t_{1}$ , the swaption holder can decide to pay $f_{t_{0}}$ , and receive $s_{t_{1}}$ . The time $t_{1}$ value of the resulting cash flows can be expressed as17  

$$
\left[\frac{s_{t_{1}}-f_{t_{0}}}{\left(1+L_{t_{1}}\right)}+\frac{s_{t_{1}}-f_{t_{0}}}{\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]N
$$  

Note that at time $t_{1},L_{t_{1}}$ will be known, but $L_{t_{2}}$ would still be unknown. But, we know from earlier chapters that we can “replace” this random variable by the forward rate for the period $[t_{2},~t_{3}]$ that is known at time $t_{1}$ . The forward rate $F\left(t_{1},t_{2}\right)$ is an unbiased estimator of $L_{t_{2}}$ under the forward measure P\~t3:  

$$
F(t_{1},t_{2})=E_{t_{1}}^{\tilde{P}^{t_{3}}}\left[L_{t_{2}}\right]
$$  

Then, the time $t_{1}$ value of a swap entered into at a predetermined rate $f_{t_{0}}$ will be  

$$
\biggl[\frac{s_{t_{1}}-f_{t_{0}}}{\bigl(1+L_{t_{1}}\bigr)}+\frac{s_{t_{1}}-f_{t_{0}}}{\bigl(1+L_{t_{1}}\bigr)(1+F(t_{1},t_{2}))}\biggr]N
$$  

This is zero if the swaption expires at-the-money, at time $t_{1}$ , with  

$$
s_{t_{1}}=f_{t_{0}}
$$  

Thus, we can look at the swaption as if it is an option written on the value of the cash flows in Eq. (17.5) as well. The ATM swaption on a fixed payer swap can then either be regarded as an option on the (forward) swap rate $f_{t_{0}}$ , or as an option on the value of a forward swap with strike price $\kappa=0$ .  

# 17.3.1 A CONTRACTUAL EQUATION  

As in the case of caps and floors, we can obtain a contractual equation that ties swaptions to forward swaps.  

We interpret this contractual equation the following way. Consider a forward payer swap with rate $f_{t_{0}}$ that starts at time $t_{1}$ and ends at time $t_{n+1}$ . The forward swap settles $n$ times in between and makes (receives) the following sequence of cash payments in arrears:  

$$
\{(f_{t_{0}}-L_{t_{1}})N\delta,...,(f_{t_{0}}-L_{t_{n}})N\delta\}
$$  

This is regardless of whether $f_{t_{0}}<s_{t_{1}}$ or not.  

A payer swaption, on the other hand, makes these payments only if $f_{t_{0}}<s_{t_{1}}$ . To receive the cash flows in Eq. (17.8) when $f_{t_{0}}>s_{t_{1}}$ , one has to buy a receiver swaption.  

# 17.4 PRICING SWAPTIONS  

The pricing and risk management of swaptions can be approached from many angles using various working measures. For example, we have already seen in Chapters 4 and 14 that the time $t_{0}$ forward swap rate $f\left(t_{0},t_{1},T\right)$ for a forward swap that begins at time $t_{1}$ and ends at time $T$ will be a weighted average of the forward rates $F\left(t_{0},t_{i},t_{i+1}\right)$ . If we adopt this representation, a possible working measure would be the time $T$ forward measure. The Martingale dynamics of all forward rates under this measure could be obtained, and swaptions and various other swap derivatives could be priced with it.  

However, we adopt an alternative approach. For some pricing and risk-management problems, using the swap measure as the working probability may be more convenient. This gives us an opportunity to discuss this interesting class of working measures in a very simple context. Therefore, we will obtain the pricing functions for European swaptions using the swap measure.  

# 17.4.1 SWAP MEASURE  

The measures considered thus far were obtained using normalization by the price of a single asset. Under some conditions, we may want to use normalization by the value of a stream of payments instead of a single asset. One well-known case is the swap measure. We will discuss the swap measure in a simple, two-period model with finite states. The model has the same time and cash flow structure discussed earlier in this chapter. We start with the definition of an annuity.  

Consider a contract that pays $\delta$ dollars at every $\delta$ units of time. The payment dates are denoted by $t_{i},$  

$$
t_{i}-t_{i-1}=\delta
$$  

![](76a82b8f5ddd2c56bab5162623d056a78cdec24a16838643462d1a1d673724e7.jpg)  

# FIGURE 17.4  

Present value of annuity.  

For example, $\delta$ can be 1/2 and the payments would be made every 6 months. The payments continue for $N$ years. This would be an annuity and we could use its time $t$ value to normalize time $t$ asset prices. This procedure leads us to the swap measure.  

Suppose at time $t_{2}$ there is a finite number of states of the world indexed by $i=1$ , 2, . . ., n. In this context suppose an annuity starts at time $t_{2}$ and makes two payments of 1 dollar at times $t_{3}$ and $t_{4}$ , respectively. Hence, in this case, $\delta=1$ . This situation is shown in Figure 17.4. Obviously, for simplicity, we eliminated any associated credit risks. The annuity is assumed to be default-free. In reality, such contracts do have significant credit risk as was seen during the GFC.  

The present value of the payments at time $t_{2}$ is a random variable when considered from time $t_{0}$ and is given by the expression:18  

$$
P V_{t_{2}}^{i}=\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\Big(1+L_{t_{2}}^{i}\delta\Big)(1+F(t_{2},t_{3})^{i}\delta)}
$$  

Here, $L_{t_{2}}^{i}$ is the time $t_{2}$ LIBOR rate in state $i$ and $F(t_{2},t_{3})^{i}$ is the forward rate at time $t_{2}$ , in state $i$ , on a loan that starts at time $t_{3}$ . The loan is paid back at time $t_{4}$ . We are using these rates in order to calculate the time $t_{2}$ present value of the payments that will be received in times $t_{3}$ and $t_{4}$ . These values are state dependent and $P V_{t_{2}}^{i}$ is therefore indexed by $i$ .  

Using the default-free discount bonds $B(t,t_{3})$ and $B(t,t_{4})$ that mature at times $t_{3}$ and $t_{4}$ , we can write the $P V_{t_{2}}^{i}$ as  

$$
P V_{t_{2}}^{i}=(\delta)B(t_{2},t_{3})^{i}+(\delta)B(t_{2},t_{4})^{i}
$$  

In this representation, the right-hand side default-free bond prices are state dependent, since they are measured at time $t_{2}$ .  

Suppose two-period interest rate swaps trade actively. A spot swap that will be initiated at time $t_{2}$ is shown in Figure 17.5. The spot swap rate $s_{t_{2}}^{i}$ for this instrument is unknown at time $t_{0}.$ , and this is implied by the $i$ superscript. As of time $t_{0}$ , markets are assumed to trade a forward swap, with a rate denoted by $f_{t_{0}}$ that corresponds to $s_{t_{2}}^{i}$ .  

![](bd38169676a601229d810cd97895a43e4a49cb21dd0003cade145c7cdd1ca544.jpg)  

# FIGURE 17.5  

Spot swap initiated at date $t_{2}$ .  

Now consider the time $t_{0}$ market value of a two-period forward swap contract that starts at time $t_{2}$ . In the context of the fundamental theorem of Chapter 12, we can write a matrix equation containing the annuity, the forward swap contract, and the European fixed payer swaption $S w_{t}$ that delivers the same two-period swap, if $s_{t_{2}}<f_{t_{0}}$ . Putting these assets together in the simplified matrix equation of Chapter 12, we obtain:  

$$
\left[\begin{array}{c c c c}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\\ {0}&{0}\\ {S w_{t_{0}}}&{\displaystyle\left[\begin{array}{c c c c c}{\cdots}&{\displaystyle\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}}&{\cdots}\\ {\cdots}&{\displaystyle\frac{1}{\left(f_{t_{0}}-S_{t_{2}}^{i}\right)\delta}}&{\cdots}\\ {\cdots}&{\displaystyle\frac{1}{S w_{t_{2}}^{i}}}&{\cdots}\end{array}\right]\left[\begin{array}{c c c c c}{\cdots}\\ {Q^{i}}\\ {\cdots}\\ {Q^{i}}\\ {\cdots}\end{array}\right]
$$  

Here $\{Q^{i},i=1,...,n\}$ are the $n$ state prices for the period $t_{2}$ . Under the no-arbitrage condition, these exist, and they are positive  

$$
Q^{i}>0
$$  

for all states $i.^{19}$ The last row of the matrix equation shows the swaption’s current value as a function of $\boldsymbol{Q}^{i}$ and the state-dependent expiration values of the swaption. In the states of the world where $f_{t_{0}}>s_{t_{2}}^{i}$ , the swaption will expire out-of-the-money and the corresponding $S w_{t_{2}}^{i}$ will be zero. Without loss of generality, let these be the first $m<n$ , values:  

$$
S w_{t_{2}}^{i}=0\quad i=1,...,m
$$  

For the remaining $n-m$ states, the expiration value of the swaption is  

$$
S w_{t_{2}}^{i}={\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}}+{\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)(1+F(t_{2},t_{3})^{i}\delta)}}\quad s_{t_{2}}^{i}<f_{t_{0}}
$$  

The first row of the matrix equation shows the value of the annuity. We obtain this row from the arbitrage-free prices of the corresponding default-free discount bonds with par value $\$1$ :  

$$
B(t_{2},t_{3})^{i}=\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}
$$  

and  

$$
B(t_{2},t_{4})^{i}=\frac{1}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}
$$  

The quantity $B(t_{0},t_{3})\delta+B(t_{0},t_{4})\ \delta$ is, therefore, the present value of the annuity payment. The same quantity was previously called PV01. In fact, the present discussion illustrates how PV01 comes to center stage as we deal with streams of fixed-income cash flows.  

The first row of the matrix equation gives:  

$$
B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta=\sum_{i=1}^{n}\left[\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]Q^{i}
$$  

Now we switch measures and obtain a new type of working probability known as the swap measure. Dividing the first row by the left-hand side we have:  

$$
1=\sum_{i=1}^{n}\frac{1}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\left[\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]Q^{i}
$$  

We define the measure $\tilde{p}_{i}^{s}$ using this expression:  

$$
\tilde{p}_{i}^{s}=\frac{1}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\left[\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})\right.^{i}\delta)}\right]Q^{i}
$$  

Note that as long as $Q^{i}>0$ is satisfied, we will have:  

$$
\tilde{p}_{i}^{s}>0\quad i=1,...,n
$$  

and  

$$
1=\sum_{i=1}^{n}\tilde{p}_{i}^{s}
$$  

Thus, $\tilde{p}_{i}^{s}$ have the properties of a well-defined discrete probability distribution. We call this the swap measure. We will show two interesting applications of this measure. First, we will see that under this measure, the corresponding forward swap rate behaves as a Martingale and has very simple dynamics. Second, we will see that by using this measure, we can price European swaptions easily.  

# 17.4.2 THE FORWARD SWAP RATE AS A MARTINGALE  

In order to see why forward swap rates behave as a Martingale under the appropriate swap measure, consider the second row of the matrix equation in Eq. (17.12). Since the forward swap has a value of zero at the time of initiation, we can write:  

$$
0=\sum_{i=1}^{n}\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta\left[\frac{1}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]Q^{i}
$$  

We can express this as:  

$$
0=\sum_{i=1}^{n}\left(f_{t_{0}}-s_{t_{2}}^{i}\right)\delta\left[\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}\right]\left[\frac{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\right]Q^{i}
$$  

Now, we use the definition of the swap measure given in Eq. (17.20) and relabel, to get:  

$$
0=\sum_{i=1}^{n}\big(f_{t_{0}}-s_{t_{2}}^{i}\big)[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]\tilde{p}_{i}^{s}
$$  

After taking the constant term outside the summation and eliminating, this becomes:  

$$
0=\sum_{i=1}^{n}{{{\left({{f}_{t_{0}}}-{{s}_{t_{2}}}^{i}\right)}{{\tilde{p}}_{i}^{s}}}}
$$  

or again:  

$$
f_{t_{0}}=\sum_{i=1}^{n}s_{t_{2}}^{i}{\tilde{p}}_{i}^{s}
$$  

which means:  

$$
f_{t_{0}}=E_{t_{0}}^{\tilde{P}^{s}}[s_{t_{2}}]
$$  

Hence, under the swap measure, the forward swap rate behaves as a Martingale. The dynamics of the forward swap rate under this measure can then be written using the SDE:  

$$
\mathrm{d}f_{t}=\sigma f_{t}\mathrm{d}W_{t}\quad t\in[t_{0},T]
$$  

where we assumed a particular diffusion structure and where $T$ is the general swap maturity. Given the forward swap rate volatility $\sigma$ , it would be straightforward to generate Monte Carlo trajectories from these dynamics.  

# 17.4.3 SWAPTION VALUE  

In order to obtain a pricing function for the European swaption, we consider the third row of the matrix equation given in Eq. (17.12). We have:  

$$
S w_{t_{0}}=\sum_{i=1}^{n}S w_{t_{2}}^{i}Q^{i}
$$  

We use the definition of the swap measure $\tilde{P}^{s}$  

$$
\tilde{p}_{i}^{s}=\frac{1}{[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]}\left[\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}\right]Q^{i}
$$  

and rewrite the equality in Eq. (17.30):  

$$
S w_{t_{0}}=\sum_{i=m+1}^{n}S w_{t_{2}}^{i}\Biggl[\frac{[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]}{\left(1\delta/\left(1+L_{t_{2}}^{i}\delta\right)\right)+\left(1\delta/\left(1+L_{t_{2}}^{i}\delta\right)(1+F(t_{2},t_{3})^{i}\delta)\right)}\Biggr]\tilde{p}_{i}^{s}
$$  

Note that we succeeded in introducing the swap measure on the right-hand side. Now, we know from Eq. (17.15) that the non-zero expiration values of the swaption are given by  

$$
S w_{t_{2}}^{i}={\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}}+{\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)(1+F(t_{2},t_{3})^{i}\delta)}}\quad s_{t_{2}}^{i}<f_{t_{0}}
$$  

Substituting these values in Eq. (17.32) gives,  

$$
S w_{t_{0}}=\sum_{i=m+1}^{n}\left[{\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}}+{\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}}\right]
$$  

$$
\left[\frac{[B(t_{0},t_{3})+B(t_{0},t_{4})]\delta}{\left(\delta/\left(1+L_{t_{2}}^{i}\delta\right)\right)+\left(\delta/\left(1+L_{t_{2}}^{i}\delta\right)(1+F(t_{2},t_{3})^{i}\delta)\right)}\tilde{p}_{i}^{s}\right]
$$  

We see the important role played by the swap measure here. On the right-hand side of this expression, the state-dependent values of the annuity will cancel out for each $i$ and we obtain the expression:  

$$
S w_{t_{0}}=[B(t_{0},t_{3})+B(t_{0},t_{4})]\sum_{i=m+1}^{n}\left[\left(f_{t_{0}}-s_{t_{2}}^{i}\right)\delta\tilde{p}_{i}^{s}\right]
$$  

This is equivalent to  

$$
S w_{t_{0}}=[B(t_{0},t_{3})+B(t_{0},t_{4})]E_{t_{0}}^{\tilde{P}^{s}}\left[\operatorname*{max}\left[\left(f_{t_{0}}-s_{t_{2}}\right)\delta,0\right]\right]
$$  

Using this pricing equation and remembering that the forward swap rate behaves as a Martingale under the proper swap measure, we can easily obtain a closed-form pricing formula for European swaptions.  

There are many ways of formulating market practice. One way to proceed is as follows. The market assumes that:  

1. The forward swap rate $f_{t}$ follows a geometric (log-normal) process  

$$
\mathrm{d}f_{t}=\mu(f_{t},t)\mathrm{d}t+\sigma f_{t}\mathrm{d}W_{t}
$$  

which can be converted into a Martingale by using the swap measure $\tilde{P}^{s}$  

$$
\mathrm{d}f_{t}=\sigma f_{t}\mathrm{d}{\tilde{W}}_{t}
$$  

2. Black’s formula can be applied to obtain the value  

$$
f_{t_{0}}N(d_{1})-\kappa N(d_{2})
$$  

with  

$$
d_{1}=\frac{\log(f_{t}/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}
$$  

$$
d_{2}=d_{1}-\sigma\sqrt{t_{2}-t_{0}}
$$  

where $t_{2}$ is the expiration of the swaption contract discussed in this section.  

3. Finally, the value of the European swaption $S w_{t}$ is obtained by discounting this value using the present value of the annuity. For time $t_{0}$ , this will give:  

$$
S w_{t_{0}}=[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]\big[f_{t_{0}}N(d_{1})-\kappa N(d_{2})\big]
$$  

In other words, swaptions are priced by convention using Black’s formula and then discounting by the value of a proper annuity.  

# 17.4.4 REAL-WORLD COMPLICATIONS  

There may be several complications in the real world. First of all, the market quotes the swaption volatilities $\sigma$ directly, and the preceding formula is used to put a dollar value on a European swaption. However, most real-world applications of swaptions are of Bermudan nature and this introduces Americanness to the underlying option. There are no closed formulas for Bermudan swaptions.  

Second, just as in the case of caps and floors, the existence of the volatility smile introduces significant complications to the pricing of swaptions, especially when they are of the Bermudan type.20 If the swap curve is not flat, then relative to a single strike level, different forward swap rates have different moneyness characteristics. Pricing Bermudan swaptions would then become more complicated.  

# 17.5 MORTGAGE-BASED SECURITIES  

MBS is a very important market, especially in the United States. MBS is also called “mortgage pass-through certificates.” They essentially take the cash flows involving interest and amortization of a principal paid by home buyers, and then pass them through to an investor who buys the MBS. In MBS, a selected pool of mortgages serves as the underlying asset. An MBS investor receives a “pro-rata share of the cash flows” generated by the underlying mortgages.  

# EXAMPLE  

A typical Fannie Mae MBS will have the following characteristics.  

Each pool of mortgages has a pass-through rate, which forms the coupon passed on to the investor. This is done on the 25th day of a month following the month of the initial issue.  

The pass-through rate is lower than the interest rate on the underlying mortgages in the pool. (We assumed this away in the present chapter.)  

This interest differential covers the fee paid to Fannie Mae, and the fee paid to the servicing institution for collecting payments from homeowners and performing other servicing functions.  

The lender that delivers the mortgages for securitization can retain servicing of the loans.  

During pooling, Fannie Mae makes sure that the mortgage rates on the underlying loans fall within 250 basis points of each other.  

MBSs are sold to investors through securities dealers.  

Certificates are issued in book-entry form and are paid by wire transfer.  

Fannie Mae’s paying agent is the Federal Reserve Bank of New York. The centralized payment simplifies accounting procedures since investors receive just one monthly payment for various MBSs that they hold.  

The certificates will initially represent a minimum of $\$1000$ of the unpaid principal of the pooled mortgages. However, as time passes, this principal is paid gradually due to amortization and the remaining principal may go down.  

Such activity by Fannie Mae-type institutions has several important consequences. First of all, the MBS and the Fannie Mae agency securities are issued in large sizes and normally form a liquid asset class. Further, the MBS and some of the agency securities contain implicit call and put options, and this creates a large class of convex assets. Important hedging, arbitraging, and pricing issues emerge. Second, institutions such as Fannie Mae become huge players in derivatives markets which affect the liquidity and functioning of swap, swaption, and other interest rate option markets. Third, the issue of prepayment requires special attention from the part of market participants. Fourth, as institutions such as Fannie Mae bear the credit risk in the mortgages, they separate credit risk from market risk of mortgages. The credit crisis of 2007 2008 has shown that there is a delicate pricing issue here. It is difficult to estimate this credit risk. We will deal with the issue of credit risk in subsequent chapters. Finally, the structure of the balance sheets and the federal government connection that such institutions have may create market gyrations from time to time.  

# 17.6 CAPS AND FLOORS  

Caps and floors are important instruments for fixed-income professionals. Our treatment of caps and floors will be consistent with the approach adopted in this text from the beginning. First, we would like to discuss, not the more liquid spot caps and floors that start immediately, but instead the so-called forward caps and floors. These instruments have a future start date and are perhaps less liquid, but they are more appropriate for learning purposes. Second, we will follow our standard practice and generate these instruments from instruments that have already been discussed.  

Again, we keep the framework as simple as possible and leave the generalization to the reader. Consider the two-period forward fixed payer swap shown in Figure 17.6a. In this swap, there will be two settlements  

$$
\left(f_{t_{0}}-L_{t_{1}}\right)N\delta\quad\mathrm{and}\quad\left(f_{t_{0}}-L_{t_{2}}\right)N\delta
$$  

where $L_{t_{i}},f_{t_{0}}$ , and $N$ are the relevant LIBOR rate, forward swap rate, and the forward swap notional, respectively. δ is the reset interval. The forward swap starts at time t1.21  

We now consider a particular decomposition of this forward swap. First, note that depending on whether $L_{t_{1}}>f_{t_{0}}$ or not, the swap party either receives a payment at time $t_{2}$ , or makes a payment. Thus, the first cash flow to be settled at time $t_{2}$ can be decomposed into two contingent cash flows  

![](5e7fe7490b181fd67069ca357f9b01489b200ab174c81d118171a21c5f0c27c8.jpg)  

# FIGURE 17.6  

Forward fixed payer swap.  

depending on whether $L_{t_{1}}<f_{t_{0}}$ or $L_{t_{1}}>f_{t_{0}}$ . The same can be done for the second cash flow to be settled at time $t_{3}$ . Again, the cash flow can be split into two contingent payments.  

These contingent cash flows can be interpreted as payoffs of some kind of interest rate option. Consider the cash flows of time $t_{2}$ in Figure 17.6b. Here, the client receives $\left(L_{t_{1}}-f_{t_{0}}\right)N\delta$ if $L_{t_{1}}>f_{t_{0}}$ , otherwise he or she receives nothing. Thus, this cash flow will replicate the payoff of an option with expiration date $t_{1}$ , and settlement date $t_{2}$ that is written on the LIBOR rate $L_{t_{1}}$ . The client receives the appropriate difference at time $t_{2}$ if the LIBOR observed at time $t_{1}$ exceeds a cap level $\kappa$ , which in this case is $\kappa=f_{t_{0}}$ . Thus, the top part of Figure 17.6b is like an insurance against movements of LIBOR rates above level $\kappa$ . This instrument is labeled a caplet and its time $t$ price is denoted by $C l^{t_{1}}$ . The client is long a caplet.  

The lower portion of Figure 17.6b is similar but shows insurance against a drop of the LIBOR rate below the floor level $\kappa$ . In fact, the cash flow here is a payment of $\left(f_{t_{0}}-L_{t_{1}}\right)N\delta$ if $L_{t_{1}}<f_{t_{0}}$ . Otherwise, the client pays nothing. This cash flow replicates the payoff of an option with expiration $t_{1}$ and settlement $t_{2}$ that is written on the LIBOR rate. The client pays the appropriate difference at time $t_{2}$ , if the LIBOR observed at time $t_{1}$ falls below floor $\kappa$ , which in this case, is $\kappa=f_{t_{0}}$ . We call this instrument a floorlet and denote its price by $F l^{t_{1}}$ . Clearly, the client is short the floorlet in this case.  

The treatment of the time $t_{3}$ settled caplet-floorlets is similar. The cap and floor levels are again the same:  

$$
\kappa=f_{t_{0}}
$$  

but exercise times, settlement times, and the underlying LIBOR rate $L_{t_{2}}$ are different. By putting the two caplets together, we get a two-period forward interest rate cap, which starts at time $t_{1}$ and ends at $t_{3}$  

$$
\mathrm{Cap}=\{C l^{t_{1}},C l^{t_{2}}\}
$$  

Similarly, the two floorlets can be grouped as a two-period forward interest rate floor:  

$$
\mathrm{Floor}=\{F l^{t_{1}},F l^{t_{2}}\}
$$  

These forward caps and floors can be extended to $n$ periods by putting together $n$ caplets and floorlets defined similarly.  

Figure 17.6 shows that we obtained a contractual equation. By adding Figures 17.6b and c vertically, we get back the original forward swap. Thus, we can write the contractual equation:  

![](4afea9545caaf7258684e8305dce9c822e7ee0a8e62fdfb27ffc5d851a3faf22.jpg)  

This contractual equation shows that caps, floors, and swaps are closely related instruments.  

# 17.6.1 PRICING CAPS AND FLOORS  

This discussion will be conducted using the same two-period cap and floor discussed earlier. One obvious conclusion from the engineering shown here is that the caplets that make up the cap can be priced separately and their values added, after discounting them properly. This is how a caplet is typically priced; we take the $C l^{t_{1}}$ written on $L_{t_{1}}$ .  

First, let the $F\left(t,t_{1}\right)$ , $t<t_{1}$ , be the forward rate that corresponds to $L_{t_{1}}$ , observed at $t$ . More precisely, $\textit{F}(t,\ t_{1})$ is the interest rate decided on at time $t$ on a loan that will be made at time $t_{1}$ and paid back at time $t_{2}$ . Market practice assumes that the forward LIBOR rate $F(t,\ t_{1})$ can be represented as a Martingale with constant instantaneous percentage volatility $\sigma$ :  

$$
\mathrm{d}F(t,t_{1})=\sigma F(t,t_{1})\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

with initial point $F(t_{0},t_{1})$ .  

Second, the market assumes that the arbitrage-free value of a $t_{2}$ -maturity default-free pure discount bond price, denoted by B(t0, t2), can be calculated.22  

Third, it is shown that the time $t_{0}$ value of the caplet $C l^{t_{1}}$ is given by the formula  

$$
C l_{t_{0}}^{t_{1}}=B(t_{0},t_{2})E_{t_{0}}^{\tilde{P}_{t_{2}}^{t_{2}}}\left[\operatorname*{max}\left[L_{t_{1}}-\kappa,0\right]N\delta\right]
$$  

where, in this case, $\kappa$ also equals the forward swap rate $f_{t_{0}}$ . Hence, this is an ATM cap. $N$ is the national amount. Here, the expectation is taken with respect to the forward measure $\tilde{P}^{t_{2}}$ and the normalization is done with the $t_{2}$ -maturity pure discount bond, $B(t_{0},t_{2})$ .  

Finally, remembering that under the measure $\tilde{P}^{t_{2}}$ , the forward LIBOR rate $F(t_{0},t_{1})$ is an unbiased estimate of $L_{t_{1}}$  

$$
F(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[L_{t_{1}}\right]
$$  

a closed-form formula can be obtained. This is done by applying Black’s formula to the $F(t,\ t_{1})$ process, which has a zero drift term. Then the expectation  

$$
E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\operatorname*{max}\left[L_{t_{1}}-\kappa,0\right]N\delta\right]
$$  

can be calculated to obtain Black’s formula:23  

$$
C l_{t_{0}}^{t_{1}}=B(t_{0},t_{2})[F(t_{0},t_{1})N(h_{1})-\kappa N(h_{2})]\delta N
$$  

where  

$$
h_{1}=\frac{\log(F(t_{0},t_{1})/\kappa)+(1/2)\sigma^{2}(t_{1}-t_{0})}{\sigma\sqrt{t_{1}-t_{0}}}
$$  

$$
h_{2}=\frac{\log(F(t_{0},t_{1})/\kappa)+(1/2)\sigma^{2}(t_{1}-t_{0})}{\sigma\sqrt{t_{1}-t_{0}}}-\sigma\sqrt{(t_{1}-t_{0})}
$$  

Note that both $F(t_{0},t_{1})$ and $f_{t_{0}}$ are rates that relate to amounts calculated in $t_{2}$ dollars. The discount bond price $B(t_{0},t_{2})$ is then a market-determined “expected” discount rate for this settlement.  

The caplet that expires at time $t_{2},C l^{t_{2}}$ , will be priced similarly, except that this time the expectation has to be taken with respect to the time $t_{3}$ -forward measure $\tilde{P}^{t_{3}}$ , and the underlying forward rate will now be $\textit{F}(t_{0},t_{2})$ and not $\boldsymbol{F}\left(t_{0},t_{1}\right)$ .24 Solving the pricing formula, we get  

$$
C l_{t_{0}}^{t_{2}}=B(t_{0},t_{3})[F(t_{0},t_{2})N(g_{1})-\kappa N(q_{2})]\delta N
$$  

where  

$$
q_{1}=\frac{\log(F(t_{0},t_{2})/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}
$$  

$$
q_{2}=\frac{\log(F(t_{0},t_{2})/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}-\sigma\sqrt{(t_{2}-t_{0})}
$$  

It is important to realize that the same constant percentage volatility was used in the two caplet formulas even though the two caplets expired at different times. In fact, the first caplet has a life of $[t_{0},t_{1}]$ , whereas the second caplet, $C l_{t_{0}}^{t_{2}}$ , has a longer life of $[t_{0},t_{2}]$ . Also, note that despite the strike price being the same, the two caplets have different money.  

Finally, to get the value of the cap itself, the market professional simply adds the two caplet prices:  

$$
\mathrm{Cap}_{t_{0}}=B(t_{0},t_{2})[F(t_{0},t_{1})N(h_{1})-\kappa N(h_{2})]+B(t_{0},t_{3})[F(t_{0},t_{2})N(g_{1})-\kappa N(g_{2})]
$$  

where $h_{i}$ and $g_{i}$ are given as noted earlier. The parameters $N,\delta$ are set equal to one in this formula.   
Otherwise, the right-hand side needs to be multiplied by $N,\delta$ as well.  

# 17.6.2 A SUMMARY  

It is worth summarizing some critical steps of the cap/floor pricing convention. First, to price each caplet, the market uses normalization by means of a discount bond that matures at the settlement date of that particular caplet and obtains the forward measure that corresponds to that caplet. Second, the market uses an SDE with a zero drift since the corresponding forward LIBOR rate is a Martingale under this measure. Third, the percentage volatility for all the caplets is assumed to be constant and identical across caplets. Finally, the use of proper forward measures makes it possible to calculate the expectations for the random discount factors and the caplet payoffs, separately. Black’s formula gives the caplet prices which are added using the appropriate liquid discount bond prices.  

# 17.6.3 CAPLET PRICING AND THE SMILE  

The previous summary should make clear why the volatility smile is highly relevant for pricing and hedging caps/floors. The latter are made of several caplets and floorlets and, hence, are baskets of options written on different forward rates denoted by $F(t_{0},t_{i}),i=1,...,n.$ .  

As long as the yield curve is not flat, the forward rates $\textit{F}(t_{0},\ t_{i})$ will be different from each other. Yet, each cap or floor has only one strike price $\kappa$ . This means that, relative to this strike price, we will have  

$$
{\frac{F(t_{0},t_{1})}{\kappa}}\neq{\frac{F(t_{0},t_{2})}{\kappa}}\neq\cdots{\frac{F(t_{0},t_{n})}{\kappa}}
$$  

In other words, as long as the yield curve slopes upward or downward, the ratios  

$$
\frac{F(t_{0},t_{i})}{\kappa}
$$  

will be different, implying different moneyness for each caplet/floorlet.  

Now, suppose there is a volatility smile. If, under these conditions, each caplet and floorlet were sold separately, the option trader would substitute a different volatility parameter for each, conformable with the smile in the corresponding Black’s formula. But caplets or floorlets are bundled into caps and floors. More important, a single volatility parameter is used in Black’s formula.  

This has at least two implications. First, we see that the volatility parameter associated with a cap is some weighted average of the caplet volatilities associated with options that have different moneyness characteristics. Second, even when the realized and ATM volatilities remain the same, a movement of the yield curve would change the moneyness of the underlying caplets (floorlets) and, through the smile effect, would change the volatility parameter that needs to be used in the corresponding Black’s formulas. In other words, marking cap/floor books to the market may become a delicate task if there is a volatility smile.  

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

Lehman Brothers and Credit Suisse First Boston are recommending clients to buy long-dated swaption vol ahead of the upcoming US Federal Open Markets Committee meeting. In the trade, the banks are recommending clients to buy long-dated swaption straddles, whose value increases if long-dated swaption vol rises.  

Mortgage servicers and investors are keen to hedge refinancing risk with swaptions as interest rates fall, meaning that long-dated swaption vol should rise over the next several months, said an official at CSFB in New York.  

The traditional supply of swaption vol has been steadily decreasing over the last year, said (a trader) in New York. Agencies supply vol to dealers mainly via entering swaps with embedded options on the back of issuing callable notes. Over the past year, demand for callable notes has been decreasing due to high interest rate volatility, and lower demand from banks, one of the larger investors in callables. This decreased supply in vol for dealers would point to intermediate- and longer-dated swaption vol rising.  

Lehman is recommending a relative value trade in which investors sell short-dated swaption volatility, such as options, to enter 10-year swaps in one year, and buy long-dated swaption vol, such as the option to enter a 10-year swap in five years. The trade is constructed with at-the-money swaption straddles, weighted in such a way as to make this a play on the slope of the vol curve, which at current levels is more inverted compared to historical levels, noted (the trader). Short-dated swaption vol should fall as the Fed’s plans become clearer in the next several months, and the market is assuaged concerning the direction of interest rates. If the Fed cuts interest rates 50 basis points when it meets this week, the market should breathe a sigh of relief, and short-dated vol should fall more than longer-dated vol, he added.  

CSFB recommends buying long-dated vol. The option to enter a five-year swap in five years had a premium of about 570 basis points at press time. At its peak this month, this level was 670 bps, said the official at CSFB. During a similar turning point in the US economy in 1994 1995, vol for a similar swap was nearly 700 bps. This week’s meeting might provide an instant lift to the position. If the Fed cuts rates by more or less than the expected 50 bps, longdated swaption vol could rise in reaction, he added. Even if the Fed cuts by 50 basis points, swaption vol could rise as mortgage players hedge. An offsetting factor here is the fact that following a Fed meeting, short-dated vol typically falls, sometimes dragging longer-dated vol down with it. (Derivatives Week (now part of GlobalCapital) November 2001).  

First, some comments on the mechanics mentioned in the reading. The term Agencies is used for semiofficial institutions such as Fannie Mae that provide mortgage funds to the banking sector. These agencies sell bonds that contain imbedded call options. For example, the agency has the right to call the bond at par at a particular time. The owners of these bonds are thus option writers. The agency is an option buyer. To hedge these positions they also need to be option sellers.  

a. Using cash flow diagrams, show the positions that agencies would take due to issuing callable bonds.   
b. Why would the short-term vol decrease according to the market? Why would long-term vol increase?   
c. What do you think an at-the-money swaption straddle is? Show the implied cash flow diagrams.   
d. If the expectations concerning the volatilities are realized, how would the gains be cashed in   
e. What are the differences between the risks associated with the positions recommended b CSFB versus the ones recommended by Lehman?  

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

a. Define the following concepts: MBS, prepayment risk, implicit option, and negative convexity.   
b. Show how you can hedge your DMB positions in the swap and swaption markets and then earn a generous arbitrage. Why would this add liquidity to the Danish markets?   
c. Show how you can do this using Bermudan options.   
d. Explain carefully if this is true arbitrage. Are there any risks?  

Part II  

Now consider the second reading.  

e. What is a corridor structure? f. What does the reading mean by “dislocations”? g. What are “balance-protected swaps”? h. Explain the purpose of the dislocation trades.  

# Reading 1  

Arbitrageurs Swoop on Danish Mortgage Market  

Yield-starved banks and hedge funds have been scooping up long-dated Danish mortgage bonds, hedging parts of the exposure in the swap and swaption markets, and earning a generous arbitrage (1). But the strategy is not without risk. The structures involved are heavily dependent on complex statistical modelling techniques.  

The Danish mortgage bond market has been undergoing something of a revolution. Securities traditionally bought by Danish pension funds or investment managers are now being snapped up by sophisticated foreign banks and hedge funds. The international players are trying to arbitrage between mortgage, credit- and other interest-rate markets. This activity has also generated significant added volume in the Danish krone and Deutsche mark swap and swaption markets. (1)  

The exact size and nature of the international activity is unknown, but it is believed to be large and growing. “Foreign involvement has gone through the roof,” said one structurer at a London-based bank. Banks believed to be at the forefront of activity include Barclays Capital, Bankers Trust, and Merrill Lynch International.  

Outside interest, said market professionals, had been stoked by a decreasing number of profit opportunities in both Europe and the US European investors have seen Southern European bond yields plummet ahead of EMU and have had to look for new sources of return. US hedge funds have turned to Denmark as US mortgage market arbitrage opportunities have started to run dry.  

The European activity has focused on Denmark’s mortgage bonds because they are seen as the only real arbitrage alternative (2) to US securities. Seven dedicated private companies, Nykredit, Real Kredit, BRF Kredit, Danske Kredit, Unikredit, Totalkredit, and DLR, continue to issue into a market now worth DKr900bn. Mortgage-backed markets are developing in other sectors of Europe—though slowly. Deutsche Bank last week launched the first German mortgage securitization, Haus I, and ABN AMRO have twice securitized Dutch mortgages (see Asset-Backed Securities).  

# Arbing MBS  

Foreign activity in the Danish mortgage bond market (2) concentrates on the valuation of embedded prepayment clauses— options that enable the borrower to buy back the bonds at par in order to take out the pre-payment risks associated with the underlying collateral pool. Derivative professionals analyze pre-payment options in terms of traditional non-mortgage backed swaptions and realize any relative value by trading swaptions against mortgage bonds. (2)  

In one version of the trade, the speculator buys the mortgage bonds and transacts a Bermudan receivers swaption, either in Danish kroner or in (closely correlated) Deutsche marks. This cancels out the prepayment risk and leaves relatively pure interest rate and credit exposure (3).  

Some players go even further and transact both a swap and a swaption against the mortgage bonds, thus creating a true arbitrage (3). They pay fixed on the swap to eliminate the interest rate risk and buy receivers swaptions to offset the inbuilt optionality. They are left with simple LIBOR plus returns and a locked-in profit, subject to credit risk.  

Very similar activity forms the backbone of the US mortgage bond market. Sophisticated US houses such as Goldman Sachs, Morgan Stanley, and Salomon Brothers have for years generated favorable arbitrage profits by examining mortgage bonds in terms of other instruments (3).  

But such potential profits, whether in the US or in Denmark, are subject to considerable risks. First, there are problems involved in pricing long-dated Bermudan swaptions. The product, according to swaption professionals, is sensitive to the tilt and shape of the yield curve—features not captured by simple one-factor swaption pricing models.  

Second, there are also difficulties involved with analyzing the exact size of the prepayment risks. “Prepayment concerns have consumed mortgage desks in the US for the last few years. And many operations have blown up because they made the wrong assumptions,” said one structurer at a prominent Wall Street investment bank.  

“There’s always a rumor that one house or another has got their risk modelling wrong,” said another New Yorkbased mortgage derivative professional. The problem for banks and hedge funds is that the size of prepayment is governed by the size of individual Danish property owners’ refinancing activity. And this is a function of both current interest rate conditions and the statistical properties of individual house-owners.  

As a result, the science of valuing mortgage bonds revolves partly on building statistical models that analyze factors other than interest rate market conditions. If rates fall in Denmark, it is likely that some mortgage holders will choose to redeem their high-rate mortgages and take out a new lower-rate loan. This will lead to the borrower prepaying some of its mortgage bonds. But not every homeowner reacts in such a way. Some may never refinance; some have a greater inclination to refinance at certain times of the year; some refinance more in certain parts of the country, and so on.  

Looking to the future, mortgage bond arbitrage activity may soon be spreading to the rest of Europe. The Danish government is considering cooling the economy by restricting the flow of 30-year issues. (5) This will depress liquidity in the market and make arbitrage more difficult. Meanwhile, investment banks are talking to authorities in Sweden, Germany, the Netherlands, and the UK about changes to make their own mortgage bond markets more efficient. (Thomson Reuters IFR May 1998)  

# Reading 2  

This reading refers to Part II of the case study.  

Dynamic Funds Eye Dislocation Opportunities   
With short-term yields continuing to fall across Europe, money market funds are increasingly targeting higher yields through structured products. Generally, they are lifting returns by selling volatility through corridor structures. (1) More specifically, they are taking advantage of hedge fund-induced market dislocations in Danish mortgage markets and sterling swap spread markets. “In the last few weeks funds have substituted a little credit risk for a bit more market risk,” said one market professional at a major European bank. He added that funds saw the increasing confidence in financial markets as an opportunity to generate higher yields from market dislocations.  

In particular, dealers said funds were looking to buy Danish mortgage bonds together with balance-protected swaps (2). The balance-protected swap guarantees the bond buyer the coupons but still leaves the holder with duration risk— the risk that the instrument will have a shorter duration if prepayment increases. With unswapped Danish mortgage bonds, the holder is exposed to the risk that prepayment rates increase and that coupons levels are reduced.  

In addition to specific dislocation-related trades (3), market professionals said there was a general trend for funds to move away from standard commercial paper and asset-swap investments towards higher-returning, more structured products. Whereas traditional funds buy floating-rate instruments and are only exposed to the credit risk of the instrument, dynamic money market funds buy instruments that are exposed to interest rate and volatility risks. One structurer last week said the dynamic fund sector had been growing for some time, and added that some European funds had more funds under management in dynamic instruments than traditional instruments. “There’s lots of excitement surrounding money market funds and their attempts to churn yield,” he said. Typical dynamic money market fund trades are corridors, (4) with popular recent trades being based on two LIBOR rates remaining within the band. One bank structurer said he had recently traded a note that offered higher coupons, provided both US dollar LIBOR and French franc LIBOR remained within set limits. Capital repayment was guaranteed, but coupon payments were contingent. By buying structures such as these, funds are in effect going short LIBOR volatility and using the earned premium to enhance their received coupon levels. (5) The size of the enhanced coupon typically depends on the width of the corridor, with extra yields of up to 200 bp generated by a tight corridor and additional yields of around 50 bp delivered by a wider corridor. Dealers said funds preferred to be more cautious and favored the wider corridor, lower yield products.  

# EXCEL EXERCISES  

4. (Interest Rate Cap Pricing). Write a VBA program to determine the price of an interest rate cap which makes payments if the floating USD LIBOR rate is above the fixed level of $5.00\%$ . Use the data given in the “Cap Pricing Input” worksheet on the chapter webpage for the calculation.   
5. (Interest Rate Floor Pricing). Write a VBA program to determine the price of interest rate floor which makes the payment if the floating USD LIBOR rate is below the fixed level of $4.60\%$ . Use the data given in the “Floor Pricing Input” worksheet on the chapter webpage for the calculation.  

This page intentionally left blank  