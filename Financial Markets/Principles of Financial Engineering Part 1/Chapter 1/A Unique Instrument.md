---
tags:
  - '#commodity_swap'
  - '#credit_default_swap_cds'
  - '#default_risk'
  - '#equity_swap'
  - '#financial_engineering'
  - '#forward_contracts'
  - '#interest_rate_swap_irs'
  - '#libor_loan'
  - '#market_risk'
  - '#synthetic_instruments'
---
# 1.1 A UNIQUE INSTRUMENT  

First, we would like to introduce the equivalent of the integer zero, in finance. Remember the property of zero in algebra. Adding (subtracting) zero to any other real number leaves this number the same. There is a unique financial instrument that has the same property with respect to market and credit risk. Consider the cash flow diagram in Figure 1.1. Here, the time is continuous and the. $t_{0}$ $t_{1}$ $t_{2}$ represent some specific dates. Initially we place ourselves at time $t_{0}$ . The following deal is. struck with a bank. At time $t_{1}$ we borrow 100 US dollars (UsD100), at the going interest rate of time $t_{1}$ , called the LIBOR and denoted by the symbol $\boldsymbol{L}_{t_{1}}.^{1}$ We pay the interest and the principal back at time $t_{2}$ . The loan has no default risk and is for a period of $\delta$ units of time.? Note that the contract is written at time $t_{0}$ , but starts at the future date $t_{1}$ . Hence this is an example of forward contracts. The actual value of $L_{t_{1}}$ will also be determined at the future date $t_{1}$  

Now, consider the time interval from $t_{0}$ to $t_{1}$ ,  expressed as $t\in[t_{0},t_{1}]$ . At any time during this interval, what can we say about the value of this forward contract initiated at $t_{0}$  

It turns out that this contract will have a value identically equal to zero for all $t\in[t_{0},t_{1}]$ regardless of what happens in world financial markets. Perceptions of future interest rate movements may go from zero to infinity, but the value of the contract will still remain zero. In order to prove this assertion, we calculate the value of the contract at time $t_{0}$ . Actually, the value is obvious in one. sense. Look at Figure 1.1. No cash changes hands at time $t_{0}$ . So, the value of the contract at time. $t_{0}$ must be zero. This may be obvious but let us show it formally.  

To value the cash flows in Figure 1.1, we will calculate the time $t_{1}$ value of the cash flows tha1 will be exchanged at time $t_{2}$ . This can be done by discounting them with the proper discount factor.  

![](images/e435c11193d33831ee0d1d4e1c609d931395eb9d69fa8bf4234e570aa2ae3a12.jpg)  

# FIGURE 1.1  

A forward loan.  

The best discounting is done using the $L_{t_{1}}$ itself, although at time. $t_{0}$ the value of this LIBOR rate is. not known. Still, the time. $t_{1}$ value of the future cash flows are  

$$
P V_{t_{1}}=\frac{L_{t_{1}}\delta100}{\left(1+L_{t_{1}}\delta\right)}+\frac{100}{\left(1+L_{t_{1}}\delta\right)}
$$  

At first sight, it seems we would need an estimate of the random variable $L_{t_{1}}$ to obtain a numerical answer from this formula. In fact, some market practitioners may suggest using the corresponding forward rate that is observed at time $t_{0}$ in lieu of $L_{t_{1}}$ , for example. But a closer look suggests a much better alternative. Collecting the terms in the numerator  

$$
P V_{t_{1}}=\frac{(1+L_{t_{1}}\delta)100}{(1+L_{t_{1}}\delta)}
$$  

the unknown terms cancel out and we obtain:  

$$
P V_{t_{1}}=100
$$  

This looks like a trivial result, but consider what it means. In order to calculate the value of the cash flows shown in Figure 1.1, we don't need to know $L_{t_{1}}$ . Regardless of what happens to interest rate expectations and regardless of market volatility, the value of these cash flows, and hence the value of this contract, is always equal to zero for any $t\in[t_{0},t_{1}]$ . In other words, the price volatility of this instrument is identically equal to zero.  

This means that given any instrument at time $t$ we can add (or subtract) the LIBOR loan to it, and the value of the original instrument will not change for all $t\in[t_{0},t_{1}]$ . We now apply this simple idea to a number of basic operations in financial markets.  

# 1.1.1 BUYING A DEFAULT-FREE BOND  

For many of the operations they need, market practitioners do not "buy" or "sell" bonds. There is a much more convenient way of doing business.  

The cash flows of buying a default-free coupon bond with par value 100 forward are shown in Figure 1.2. The coupon rate, set at time $t_{0}$ is $r_{t_{0}}$ . The price is USD100, hence this is a par bond and the maturity date is $t_{2}$ . Note that this implies the following equality:  

$$
100=\frac{r_{t_{0}}\delta100}{(1+r_{t_{0}}\delta)}+\frac{100}{(1+r_{t_{0}}\delta)}
$$  

which is true, because at $t_{0}$ the buyer is paying USD100 for the cash flows shown in Figure 1.2.  

Buying (selling) such a bond is inconvenient in many respects. First, one needs cash to do this.. Practitioners call this funding, in case the bond is purchased.3 When the bond is sold short it will generate new cash and this must be managed. Hence, such outright sales and purchases require. inconvenient and costly cash management.  

![](images/9d77ef008f11e2a83effbe8652d789333ba288e188d19f45b7dbb2c1cf577286.jpg)  

# FIGURE 1.2  

Buying default-free bond.  

Second, the security in question may be a registered bond, instead of being a bearer bond, whereas the buyer may prefer to stay anonymous..  

Third, buying (selling) the bond will affect balance sheets, called books in the industry. Suppose the practitioner borrows UsD100 and buys the bond. Both the asset and the liability sides of the balance sheet are now larger. This may have regulatory implications.  

Finally, by securing the funding, the practitioner is getting a loan. Loans involve credit risk The loan counterparty may want to factor a default risk premium into the interest rate.  

Now consider the following operation. The bond in question is a contract. To this contract "add"' the forward LIBOR loan that we discussed in the previous section. This is shown in Figure 1.3a.. As we already proved, for all. $t\in[t_{0},t_{1}]$ , the value of the LIBOR loan is identically equal to zero.. Hence, this operation is similar to adding zero to a risky contract. This addition does not change the market risk characteristics of the original position in any way. On the other hand, as Figures 1.3a. and b show, the resulting cash flows are significantly more convenient than the original bond..  

The cash flows require no upfront cash, they do not involve buying a registered security, and the. balance sheet is not affected in any way.' Yet, the cash flows shown in Figure 1.3 have exactly the same market risk characteristics as the original bond.  

Since the cash flows generated by the bond and the LIBOR loan in Figure 1.3 accomplish the same market risk objectives as the original bond transaction, then why not package them as a separate instrument and market them to clients under a different name? This is an interest rate swap (IRS). The party is paying a fixed rate and receiving a floating rate. The counterparty is doing the reverse. IRSs are among the most liquid instruments in financial markets.  

![](images/44b15ccd55385600918c5abaa4e9b47722d3519c7fc6bf790f835c1e6718d02c.jpg)  

# FIGURE 1.3  

Engineering a simple IRS.  

# 1.1.2 BUYING STOCKS  

Suppose now we change the basic instrument. A market practitioner would like to buy a stock $S_{t}$ at time $t_{0}$ with a $t_{1}$ delivery date. We assume that the stock does not pay dividends. Hence, this is, again, a forward purchase. The stock position will be liquidated at time $t_{2}$ . Also, assume that the. time $t_{0}$ perception of the stock market gains or losses is such that the markets are demanding a price  

$$
S_{t_{0}}=100
$$  

for this stock as of time $t_{0}$ . This situation is shown in Figure 1.4a, where $\Delta S_{t_{2}}$ is the unknown stock price appreciation or depreciation to be observed at time $t_{2}$ . Note that the original price being 100, the time $t_{2}$ stock price can be written as  

$$
\begin{array}{r l}{S_{t_{2}}=S_{t_{1}}+\Delta S_{t_{2}}}&{{}}\ {=100+\Delta S_{t_{2}}}\end{array}
$$  

Hence the cash flows shown in Figure 1.4a.  

![](images/b385b59d1966459e7d52cc891e091f022f191988f737d148a5ce8712a8badf05.jpg)  

# FIGURE 1.4  

Engineering an equity or commodity swap.  

It turns out that whatever the purpose of buying such a stock was, this outright purchase suffers. from even more inconveniences than in the case of the bond. Just as in the case of the Treasury. bond, the purchase requires cash, is a registered transaction with significant tax implications, and immediately affects the balance sheets, which have regulatory implications. A fourth inconvenience is a very simple one. The purchaser may not be allowed to own such a stock.' Last, but not least, there are regulations preventing highly leveraged stock purchases.  

Now, apply the same technique to this transaction. Add the LIBOR loan to the cash flows. shown in Figure 1.4a and obtain the cash flows in Figure 1.4b. As before, the market risk characteristics of the portfolio are identical to those of the original stock. The resulting cash flows can be marketed jointly as a separate instrument. This is an equity swap and it has none of the inconveniences of the outright purchase. But, because we added a zero to the original cash flows, it has exactly the same market risk characteristics as a stock. In an equity swap, the party is receiving any stock market gains and paying a floating LIBOR rate plus any stock market losses.10  

Note that if $S_{t}$ denoted the price of any commodity, such as oil, then the same logic would give us a commodity swap.1.  

# 1.1.3 BUYING A DEFAULTABLE BOND  

Consider the bond in Figure 1.1 again, but this time assume that at time $t_{2}$ the issuer can default. The bond pays the coupon $c_{t_{0}}$ with  

$$
r_{t_{0}}<c_{t_{0}}
$$  

where $r_{t_{0}}$ is a risk-free rate. The bond sells at par value, USD100 at time $t_{0}$ The interest and principal are received at time $t_{2}i f$ there is no default. If the bond issuer defaults the investor receives nothing. This means that we are working with a recovery rate of zero. Figure 1.5a shows this characterization.  

This transaction has, again, several inconveniences. In fact, all the inconveniences mentioned there are still valid. But, in addition, the defaultable bond may not be very liquid.'2 Also, because it is defaultable, the regulatory agencies will certainly impose a capital charge on these bonds if they are carried on the balance sheet.  

A much more convenient instrument is obtained by adding the "zero' from Figure 1.1 to the. defaultable bond and forming a new portfolio. Figures 1.5a and b visualized the cash flows of. a defaultable bond together with those of a forward LIBOR loan. The combination of the defaultable bond and the LIBOR loan is show in Figure 1.5c, in which we assume. $\delta=1$ . But we can go one step further in this case. Assume that at time $t_{0}$ there is an IRS, as shown in Figure 1.3, trading actively in the market. Then we can subtract this IRS from Figure 1.5c and obtain a much clearer pic-. ture of the final cash flows. This operation is shown in Figure 1.6. In fact, this last step eliminates the. unknown future LIBOR rates $L_{t_{i}}$ and replaces them with the known swap rate $s_{t_{0}}$  

The resulting cash flows don't have any of the inconveniences suffered by the defaultable bond purchase. Again, they can be packaged and sold separately as a new instrument. Letting $s_{t_{0}}$ denote the rate on the corresponding IRS, the instrument requires receipts of a known and constant premium $\mathrm{Sp}_{t_{0}}=c_{t_{0}}-s_{t_{0}}$ periodically. Against this a floating (contingent) cash flow is paid. In case of default, the counterparty is compensated by USD100. This is similar to buying and selling default insurance. The instrument is called a credit default swap (CDS). Since their initiation during the  

![](images/5c0c50b8961e5dfc538e65ab729c869cc1b58dacf0de93569f84e3840e5a44f3.jpg)  

# FIGURE 1.5  

A risky bond and a LIBOR loan.  

![](images/edbc3f3a680559692d5126f19d1044cdefd5b670b29ccf54b7def6dd77e2a0f3.jpg)  

# FIGURE 1.6  

A credit default swap.  

1990s CDSs have become very liquid instruments and completely changed the trading and hedging of credit risk. The insurance premium, called the $C D S$ spread, $\mathrm{cds}_{t_{0}}$ , is given by  

$$
\mathrm{cds}_{t_{0}}=\mathrm{Sp}_{t_{0}}=c_{t_{0}}-s_{t_{0}}
$$  

This rate is positive since. $c_{t_{0}}$ should incorporate a default risk premium, which the default-free bond does not have.13  

# 1.1.4 FIRST CONCLUSIONS  

This section discussed examples of the first method of financial engineering. Switching from cash.   
transactions to trading various swaps has many advantages. By combining an instrument with a.   
forward LIBOR loan contract in a specific way, and then selling the resulting cash flows as separate.   
swap contracts, the financial engineer has succeeded in accomplishing the same objectives much more efficiently and conveniently. The resulting swaps are likely to be more efficient, cost effective,.   
and liquid than the underlying instruments. They also have better regulatory and tax implications..  

Clearly, one can sell as well as buy such swaps. Also, one can reverse engineer the bond, equity, and the commodities by combining the swap with the LIBOR deposit. Chapter 4 will generalize this swap engineering. In the next section, we discuss another major financial engineering principle: the way one can build synthetic instruments.  

We now introduce some simple financial engineering strategies. We consider two examples that. require finding financial engineering solutions to a daily problem. In each case, solving the problem under consideration requires creating appropriate synthetics. In doing so, legal, institutional, and. regulatory issues need to be considered.  

The nature of the examples themselves is secondary here. Our main purpose is to bring to the forefront the way of solving problems using financial securities and their derivatives. The chapter does not go into the details of the terminology or of the tools that are used. In fact, some readers may not even be able to follow the discussion fully. There is no harm in this since these will be explained in later chapters.  
