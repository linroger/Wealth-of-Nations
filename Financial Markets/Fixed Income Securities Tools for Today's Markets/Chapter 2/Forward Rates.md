---
tags:
  - forward_rates
  - interest_rates
  - sofr
  - spot_rates
  - term_structure
aliases:
  - Forward Rate
  - SOFR
  - Spot Rate
key_concepts:
  - Discount factors and rates
  - Forward loan agreement
  - SOFR swap market
  - Spot rates and forward rates
  - Term structure relationships
---

# 2.5 FORWARD RATES  

A forward rate is the rate on a forward loan, which is an agreement today to. lend money at some time in the future and to be repaid some time after that. The agreement today specifies the forward rate, which means that the rate on the loan is set today even though the loan itself will not be made until a later date. There are many possible forward rates: the rate on a 1.5-year loan given six months from today; the rate on a six-month loan given in five years; etc. This section, however, focuses on forward rates over sequential,. six-month periods. Let. $f(t)$ denote the forward rate on a loan from year. $t-0.5$ to year $t$ Then, investing one unit of currency from year. $t-0.5$ for six months generates proceeds, at year $t$ , of $1+f(t)/2$  

To link forward rates to spot rates, note that a spot loan from now. to year $t-0.5$ , combined with a forward loan from year. $t-0.5$ to year $t$ , covers the same investment period as a spot loan from now to year. $t$ Consistent quoting of rates, therefore, ensures that the proceeds from these two alternatives are the same. Mathematically, noting that. $t-0.5$ years is $2(t-0.5)$ or $2t-1$ semiannual periods,  

$$
\left(1+{\frac{{\hat{r}}(t)}{2}}\right)^{2t}=\left(1+{\frac{{\hat{r}}(t-0.5)}{2}}\right)^{2t-1}\left(1+{\frac{f(t)}{2}}\right)
$$  

Extending this logic to say that a spot loan to year. $t$ is equivalent to a series of six-month forward loans, spot rates and forward rates can also be  

linked as follows,  

$$
\left(1+{\frac{\hat{r}(t)}{2}}\right)^{2t}=\left(1+{\frac{f(0.5)}{2}}\right)\left(1+{\frac{f(1.0)}{2}}\right)\cdot\cdot\cdot\left(1+{\frac{f(t)}{2}}\right)
$$  

Note that $f(0.5)$ , the rate on a "forward" loan from zero years to 0.5 years, is the same as the 0.5-year spot rate,. $\hat{r}(0.5)$  

Forward rates can also be expressed in terms of discount factors.. Use Equation (2.19) to substitute discount factors for spot rates in Equation (2.20) to see that,  

$$
1+\frac{f(t)}{2}=\frac{d(t-0.5)}{d(t)}
$$  

Applying the analytics of this section to the SOFR swaps in Table 2.1 allows for the computation of implied forward rates in that market. To illustrate with just one example, substitute the. $1.5\AA-$ and 2-year discount factors in the table into Equation (2.22) to derive the 2-year forward rate,.  

$$
1+{\frac{f(2)}{2}}={\frac{0.998979}{0.997732}}
$$  

$$
f(2)=0.2500\%
$$  

# 2.6RELATIONSHIPS BETWEEN SWAP, SPOT, AND FORWARD RATES  

Table 2.1 gives the term structure of interest rates from the SOFR swap market in terms of swap, spot, and forward rates. This section describes several. relationships between these curves that highlight their individual meanings. The discussion here is intuitive, while Appendix A2.2 takes a more mathematical approach.  

The first relationship to be highlighted is that the $t$ -year spot rate approximately equals the average of all the forward rates from today through year $t$ Taking one example from the table, the two-year spot rate is approximately equal to the average of the four forward rates from term 0.5 to 2 years,  

$$
\frac{0.0348\%+0.0585\%+0.1111\%+0.2500\%}{4}\approx0.1136\%
$$  

This result makes sense because a two-year loan is equivalent to a combination of a six-month loan; a six-month loan six months forward; a six-month loan one year forward; and a six-month loan 1.5 years forward.  

The second relationship, which is evident from Table 2.1, is that spot. rates increase with term when forward rates are greater than spot rates. To take one specific example, the two-year spot,. $0.1136\%$ , is greater than the. 1.5-year spot rate, $0.0681\%$ , because the two-year forward rate, $0.2500\%$ is greater than the 1.5-year spot rate. Intuitively, it has just been established that spot rates are essentially an average of forward rates. But adding a number to an average increases that average if and only if the added number is larger than the previous average. Therefore,. $\hat{r}(t)>\hat{r}(t-0.5)$ if and only if. $f(t)>\hat{r}(t-0.5)$  

This relationship between spot and forward rates can also be seen from Figures 2.3 and 2.4. Figure 2.3 displays forward, spot, and swap curves in the SOFR market, and Figure 2.4 displays curves from the SARON market, which, as mentioned earlier, is a rate in Swiss Franc. The curves in both figures are based on market rates, as of May 14, 2021. SOFR rates are uniformly above SARON rates, which are actually negative over a significant range of terms.  

The forward SOFR curve in Figure 2.3 increases to about the 12-year term and then declines, but it is always above the spot rate curve. Consistent with the previous paragraphs, the spot rate curve has to increase over the entire range of terms shown because forward rates are above spot rates. But the spot rate curve increases very mildly when forward rates are declining. True, spot rates have to continue to increase, but with forward rates exceeding spot rates by less and less, spot rates increase relatively slowly.  

The forward SARON curve illustrates this relationship more dramatically. Until the 22-year term, forward rates exceed spot rates and, as expected, spot rates are increasing. From then on, however, forward rates are below spot rates and, although it is somewhat hard to see from the. figure, spot rates begin to decline with term.  

![](17cd6a34d21e1ce689ec41fa0d7968ea826f0dbcd7309af3310670ddfb86a325.jpg)  
FIGURE 2.3 SOFR Rate Curves, as of May 14, 2021.  

![](5016d8a32053b43fc6537fcccc603ce5a868b91d36a77e2134c232f7b3ccbdd8.jpg)  
FIGURE 2.4  SARON Rate Curves, as of May 14, 2021.  

The third and final relationship between rates to be highlighted in this section is the following: when spot rates are increasing with term, swap or par rates are slightly below spot rates. This effect can be seen in both Figures 2.3 and 2.4, though the effect is more noticeable for the SOFR than for the SARON curves. To understand the intuition here, recall that the. $t$ -year spot rate is the return on an investment from today to year $t$ , while the swap. or par rate is the rate on an investment that pays every period from today to year $t$ . The fair market swap rate, therefore, must reflect all of the spot rates from today to year $t$ , though the. $t$ -year spot rate must be weighted most heavily as it is used to discount the by-far-and-away largest cash flow, that. is, the fictional notional amount. When the term structure of spot rates is. upward-sloping, then, all of the shorter-term spot rates are lower than the. $t$ -year spot rate, and the $t$ -year par rate -- which reflects all those spot rates -- must be less than the $t$ -year spot rate. But with the $t$ -year spot rate weighted particularly heavily, the par rate is not very much below that spot rate.  

# Returns, Yields, Spreads, and P&L Attribution  

like the Treasury bond market or the interest rate swap market. While these rates are derived from the prices of individual financial instruments, they are intended to describe the time value of money in a market as a whole. This chapter, by contrast, focuses on rates that are specific to individual bonds and then uses both market-wide and security-specific rates for P@L (profit and loss) attribution.  

The first section of the chapter defines the realized return on a bond over a given horizon. Ex-post bond returns have to account for interim coupon payments and the reinvestment of those payments and are often computed on both a gross basis and net of financing, but are otherwise calculated like the returns on any other asset.  

The next sections present yield to maturity. Bonds are often quoted and traded in terms of yield rather than price; yields are widely thought of as indicative of ex-post returns; and differences in bond yields are commonly regarded as indicative of differences in value. The discussion reveals, however, that yields can be misleading with respect to both ex-post returns and relative values.  

The chapter continues with bond spreads. Because there are so many. related but distinct fixed income products, spreads are used to quote,. trade, and value one instrument relative to another. This part of the chapter describes various ways to compute spreads, explains their uses and limitations, and presents a detailed example of using spreads to assess the. relative value of high-coupon US Treasury bonds..  

The last sections of the chapter are devoted to attribution. In order. to understand the performance of their trades and investments, traders. and asset managers often divide their ex-post P&L or return into various components, for example, the passage of time; changing interest rates; and changing spreads. The text describes how to define the "passage of time,". holding rates or spreads constant, and then illustrates P&L attribution with a detailed example of breaking into components the return on a particular US Treasury bond.  
