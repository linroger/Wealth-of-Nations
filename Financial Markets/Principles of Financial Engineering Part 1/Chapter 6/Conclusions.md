---
tags:
  - '#arbitrage'
  - '#commodity_futures'
  - '#commodity_swaps'
  - '#currency_swaps'
  - '#financial_engineering'
  - '#fx_forward_contracts'
  - '#fx_swaps'
  - '#hedge_funds'
  - '#interest_rate_swaps'
  - '#withholding_tax'
---
# 6.10 CONCLUSIONS  

This chapter has developed two main ideas. First we considered the engineering aspects of FX forward contracts and developed a contractual equation for them. We discussed two methodologies to FX forward replication based on money market and T-bill synthetics. Second, we applied the swap engineering methodology to FX swaps and currency swaps and highlighted differences between them. Real-life complications such as quoting conventions, clearing, and margin requirements are important for financial engineering in practice. We discussed the relative size of FX and currency. swap markets and highlighted the effect of recent regulatory exemptions of FX forward and swaps on financial engineering practice in FX markets..  

# SUGGESTED READING  

Weithers (2006) provides a good practical introduction to FX markets. Baba et al. (2008) examine the spillover of money market turbulence in 2007 to FX swap and currency swap markets. Cloyle (2000) provides an introduction to the basics of currency swaps.  

# EXERCISES  

1. Today is March 1, 2004. The day-count basis is actual/365. You have the following contracts on your FX book.  

CONTRACT A: On March 15, 2004, you will sell 1,000,000 EUR at a price $F_{t}^{1}$ dollars   
per EUR. CONTRACT B: On April 30, 2004, you will buy 1,000,000 EUR at a price $F_{t}^{2}$ dollars   
per EUR.   
a. Construct one synthetic equivalent of each contract.   
b. Suppose the spot EUR/USD is 1.1500/1.1505. The USD interest rates for loans under 1 year equal 2.25/2.27, and the German equivalents equal 2.35/2.36. Calculate the $F_{t}^{i}$ numerically.   
c. Suppose the forward points for $F_{t}^{1}$ that we observe in the markets is equal to 10/20. How can an arbitrage portfolio be formed?  

2. You are hired by a financial company in New Zealand and you have instant access to markets. You would like to lock in a 3-month borrowing cost in $\mathrm{NZ\mathbb{S}}$ for your client. You consider a $\mathrm{NZ\mathbb{S}}$ $1\times4$ FRA. But you find that it is overpriced as the market is thin.  

So you turn to Aussie. $\mathbf{A}\boldsymbol{\Phi}$ FRAs are very liquid. It turns out that the $\mathrm{A}\S$ and $\mathrm{NZ\mathbb{S}}$ forward are also easily available.  

In particular, you obtain the following data from Reuters:  

<html><body><table><tr><td>A$/NZ$</td><td>Spot the:</td><td>1.17/18</td></tr><tr><td></td><td>1-month forward:</td><td>1.18/22</td></tr><tr><td></td><td>3-month forward:</td><td>1.19/23</td></tr><tr><td></td><td>4-monthforward:</td><td>1.28/32</td></tr><tr><td>A$FRA's</td><td>1×4</td><td>8.97</td></tr></table></body></html>  

a. Show how you can create a $1\times4~\mathrm{NZ}\mathbb{S}$ from these data.  

b. Show the cash flows.   
c. What are the risks of your position (if any) compared to a direct $1\times4~\mathrm{NZ\S}$ FRA?   
d. To summarize the lessons learned from this exercise (if any), do you think there must be arbitrage relationships between the FRA markets and currency forward? Explain. Or better, provide the relevant formulas.  

3. Suppose at time $t=0$ , we are given prices for four zero-coupon bonds $(B_{1},B_{2},B_{3},B_{4})$ that mature at times $t=1,2,3$ , and 4. This forms the term structure of interest rates.  

We also have the one-period forward rates $(f_{0},f_{1},f_{2},f_{3})$ , where each $f_{i}$ is the rate contracted at time $t=0$ on a loan that begins at time $t=i$ and ends at time $t=i+1$ . In other words, if a borrower borrows $N$ GBP at time $i,$ , he or she will pay back $N(1+f_{i})$ GBP at time $t=i+1$  

The spot rates are denoted by $r_{i}$ . By definition, we have  

$$
r=f_{0}
$$  

The $\left\{B_{i}\right\}$ and all forward loans are default-free, so that there is no credit risk. You are given the following live quotes:  

$$
B_{1}=0.92/0.94,B_{2}=0.85/0.88,B_{3}=0.82/0.85
$$  

and  

$$
f_{0}=8.10/8.12,f_{1}=9.01/9.03,f_{2}=10.12/10.16,f_{3}=18.04/18.10
$$  

a. Given the data on forward rates, obtain arbitrage-free prices for the zero-coupon bonds, $B_{1}$ and $B_{2}$   
b. What is the three-period swap rate under these conditions?  

4. Going back to the previous exercise, suppose you are given, in addition, data on FRAs both for USD and for EUR. Also suppose you are looking for arbitrage opportunities. Would these additional data be relevant for you? Discuss briefly.  

5. Foreigners buying Australian dollar instruments issued in Australia have to pay withholding. taxes on interest earnings. This withholding tax can be exploited in tax-arbitrage portfolios. using swaps and bonds. First let us consider an episode from the markets related to this issue.  

Under Australia's withholding tax regime, resident issuers have been relegated to second. cousin status compared with nonresident issuers in both the domestic and international markets. Something has to change..  

In the domestic market, bond offerings from resident issuers incur the. $10\%$ withholding tax. Domestic offerings from nonresident issuers, commonly known as Kangaroo bonds, do. not incur withholding tax because the income is sourced from overseas. This raises the spectre of international issuers crowding out local issuers from their own markets.  

In the international arena, punitive tax rules restricting coupon washing have reduced. foreign investor interest in Commonwealth government securities and semigovernment bonds. This has facilitated the growth of global Australian dollar offerings by Triple A-rated issuers such as Fannie Mae, which offer foreign investors an attractive tax-free alternative..  

The impact of the tax regime is aptly demonstrated in the secondary market. Exchangeable issues in the international markets from both Queensland Treasury Corporation and Treasury Corporation of Nsw are presently trading through comparable domestic issues. These exchangeable issues are exempt from withholding tax.  

If Australia wishes to develop into an international financial center, domestic borrowers must have unfettered access to the international capital markets-which means compliance costs and uncertainty over tax treatment must be minimized. Moreover, for the Australian domestic debt markets to continue to develop, the inequitable tax treatment between domestic and foreign issues must be corrected (Thomson Reuters IFR, Issue 1206).  

We now consider a series of questions dealing with this problem. First, take a 4-year. straight coupon bond issued by a local government that pays interest annually. We let the coupon rate be denoted by $c\%$  

Next, consider an Aussie $\$1$ Eurobond issued at the same time by a Spanish company. The Eurobond has a coupon rate. $d\%$ . The Spanish company will use the funds domestically in Spain.  

Finally, you know that interest rate swaps or FRAs in Aussie $\$1$ are not subject to any tax.   
a. Would a foreign investor have to pay the withholding tax on the Eurobond? Why or why not?.   
b. Suppose the Aussie. $\mathbb{S}$ IRSs are trading at a swap rate of $d+10$ bp. Design a 4-year interest rate swap that will benefit from tax arbitrage. Display the relevant cash flows.   
c. If the swap notional is denoted by $N.$ how much would the tax-arbitrage yield?   
d. Can you benefit from the same tax arbitrage using a strip of FRAs in Aussie $\$1$   
e. Which arbitrage portfolio would you prefer, swaps or FRAs? For what reasons?   
f. Where do you think it is more profitable for the Spanish company to issue bonds under. these conditions, in Australian domestic markets or in Euromarkets? Explain.  

6. Consider a 2-year currency swap between USD and EUR involving floating rates only. The EUR benchmark is selected as 6-month Euro LIBOR, the dollar benchmark is 6-month BBA LIBOR. You also have the following information:  

$$
\mathrm{onal~amount}=\mathrm{USD}10,000,0
$$  

$$
\mathrm{ExchangerateEUR/USD}=0.84
$$  

a. Show the cash flow diagrams of this currency swap. Make sure to quantify every cash flow exactly (i.e., use a graph as well as the corresponding number).   
b. Show that this currency swap is equivalent to two floating rate loans..   
c. Suppose a company is trying to borrow USD10,000,000 from money markets. The company has the following information concerning available rates on 6-month loans:   
EUR LIBOR $=5.7\%$ , USD LIBOR $=6.7\%$   
EUR-USD currency swap spread: 1 year-75, 2 years-90.   
Should this company borrow USD directly? Would the company benefit if it borrowed EUR.   
first and then swapped them into USD?.  

7. A treasurer in Europe would like to borrow USD for 3 months. But instead of an outright loan, the treasurer decides to use the repo market. The company has holdings of EUR40 million bonds. The treasurer uses a cross-currency repo. The details of the transaction are as follows:  

Clean price of the bonds: 97.00   
Term: September 1 to December 1   
Last coupon date on the bond: August 12   
Bond coupon $4\%$ item EUR/USD exchange rate: 1.1150  

3-month USD repo rate: $3\%$ Haircut: $3\%$ a. What is the invoice price (dirty price) of the bond in question? b. Should the repo be done on the dirty price or the clean price? c. How much in dollars is received on September 1? d. How much repo interest is paid on December 1?  

8. Suppose the quoted swap rate is 5.06/5.10. Calculate the amount of fixed payments for a fixed payer swap for the currencies below in a 100 million swap.. :USD. EUR.  

Now calculate the amount of fixed payments for a fixed receiver swap for the currencies below in a 100 million swap.  

JPY.   
GBP.  

# CASH FLOW ENGINEERING AND ALTERNATIVE CLASSES (COMMODITIES AND HEDGE FUNDS)  

#  

# CHAPTER OUTLINe  

7.1 Introduction. 212   
7.2 Parameters of a Futures Contract . 212   
'.3 The Term Structure of Commodity Futures Prices . 215   
7.3.1 Backwardation and Contango.e .215   
7.3.2 Contractual Equation and Synthetic Commodities . 216   
7.3.3 Convenience Yield . 219   
7.3.4 Cash and Carry Arbitrage.. 219   
7.3.5 Another Interpretation of Spot--Futures Parity.. 221   
1.4 Swap Engineering for Commodities .. 221   
7.4.1 Swap Cash Flow Engineering in Commodity Markets. 222   
7.4.2 Pricing and Valuation of Commodity Swaps. 222   
7.4.2.1 Calculating swap prices from the futures curve . 224   
7.4.3 Real-World Complications ... 227   
7.4.4 Other Commodity Swaps 228   
5 The Hedge Fund Industry .. .228   
7.5.1 Alternative Investment Funds . 229   
7.5.2 Hedge Fund Regulation. 229   
7.5.3 Hedge Fund Investment Mandate and Techniques. 230   
7.5.4 Hedge Funds' Legal Structure. 230   
7.5.5 Incentives.. 231   
7.5.6 Strategies 232   
7.5.7 Prime Brokers .. 233   
7.6 Conclusions. 233   
Suggested Reading 234   
Exercises . 234  

# 7.1 INTRODUCTION  

We have so far applied our cash flow engineering methodology to fixed income and currency instruments. Unlike these asset classes, commodities incur significant storage costs and this real-. world complication needs to be taken into account in commodities cash flow engineering. For example, in contrast to currencies which are a homogeneous asset, commodities differ in their quality or grade. We provide more examples of the replication of forwards, futures, and swaps, and examine cash flow engineering in commodities. In contrast to interest rates and equities, commodi-. ties are tangible assets. This makes them useful for illustrating some of the abstract derivatives market-related concepts such as the term structure of futures prices as well as open interest and volume. Three practical reasons motivate a careful look at financial engineering applications. in commodity markets. As interest in commodities investing and hedging has increased, this has also led to what has been described as the financialization of commodities. Institutional investors. are increasingly investing in commodities through commodity futures and swaps. ETFs linked to various commodity indices and commodities have been launched, thus allowing retail investors to invest in commodities as well.  
