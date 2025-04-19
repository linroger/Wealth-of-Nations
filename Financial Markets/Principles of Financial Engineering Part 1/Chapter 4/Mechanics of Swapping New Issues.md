---
tags:
  - '#all_in_cost'
  - '#credit_risk'
  - '#fixed_rates'
  - '#floating_rates'
  - '#interest_rate_swaps'
  - '#libor'
  - '#market_conventions'
  - '#new_bond_issues'
  - '#swap_spreads'
---
# 4.7 MECHANICS OF SWAPPING NEW ISSUES  

The swap engineering introduced in this chapter has ignored several minor technical points that. need to be taken into account in practical applications. Most of these are minor and are due to differences in market conventions in bonds, money markets, and swap markets. In this section, we provide a discussion of some of these technical issues concerning interest-rate swaps. In other swap. markets, such as in commodity swaps, further technicalities may need to be taken into account.. A more or less comprehensive list is as follows:.  

1. Real-world applications of swaps deal with new bond issues, and new bond issues imply fees, commissions, and other expenses that have to be taken into account in calculating the true cost of the funds. This leads to the notion of all-in-cost, which is different to the "interest rate"' that will be paid by the issuer.  

We will show in detail how all-in-cost is calculated, and how it is handled in swapping new issues.  

2. Interest-rate swaps deal with fixed and floating rates simultaneously. The corresponding LIBOR is often taken as the floating rate, while the swap rate, or the relevant swap spread, is taken as the fixed rate. Another real-world complication appears at this point.  

Conventions for quoting money market rates, bond rates, and swap rates usually differ. This requires converting rates defined in one basis, into another..  

In particular, money market rates such as LIBOR are quoted on an ACT/360 basis, while some bonds are quoted on an annual or semiannual 30/360 basis. In swap engineering, these cash flows are exchanged at regular times, and hence appropriate adjustments need to be made.  

<html><body><table><tr><td colspan="2">Table 4.1Details of theNewIssue</td></tr><tr><td colspan="2">Shinhan Bank</td></tr><tr><td>Amount</td><td>USD200 million</td></tr><tr><td>Maturity</td><td>3 years (due July 2009)</td></tr><tr><td>Coupon</td><td>4%</td></tr><tr><td>Reoffer price</td><td>99.659</td></tr><tr><td>Spread at reoffer</td><td>168.8bp over the 2-yearUS Treasury</td></tr><tr><td>Launch date</td><td>July 23</td></tr><tr><td>Payment</td><td>July 29</td></tr><tr><td>Fees</td><td>20 bp</td></tr><tr><td>Listing</td><td>London</td></tr><tr><td>Governing law</td><td>London</td></tr><tr><td>Negative pledge</td><td>Yes</td></tr><tr><td>Cross-default</td><td>Yes</td></tr><tr><td>Sales restrictions</td><td>US,UK, South Korea</td></tr><tr><td>Joint lead managers</td><td>ABN AMRO, BNP Paribas,UBS Warburg</td></tr><tr><td colspan="2">Source:ThomsonReutersIFR issue1444.</td></tr></table></body></html>  

3. In this chapter we mostly ignored credit risk. This greatly simplified the exposition because swap rates and corporate rates of similar maturities became equal. In financial markets, they usually are not. Issuers have different credit ratings and bonds sold by them and carry credit spreads that are different from the swap spread. This gives rise to new complications in. matching cash flows of coupon bonds and interest-rate swaps. We need to look at some examples of this as well.   
4. Finally, the mechanics of how new issues are swapped into fixed or floating rates and how this may lead to sub-LIBOR financing is an interesting topic by itself..  

The discussion will be conducted with a real-life, new issue, explained next. First we report the. "market reaction' to the bond, and second we have the details of the new issue (Table 4.1).  

# EXAMPLE  

South Korea's Shinhan Bank, rated Baal/BBB by Moody's and S&P, priced its USD200 million 3-year bond early last week (...). The deal came with a $4\%$ coupon and offered a spread of 168.8 bp over the 2-year US Treasury, equivalent to 63 bp over LIBOR.   
This was some 6 bp wide of the Korea Development Bank (KDB) curve, although it was the borrower's intention to price flat to it. Despite failing to reach this target, the borrower still managed to secure a coupon that is the lowest on an Asian bond deal since the regional crisis, thanks to falling US Treasury yields which have shrunk on a renewed flight to safe haven assets  

(Thomson Reuters IFR, issue 1444).  

Consider now the basic steps of swapping this new issue into floating USD funds.30 The issuer. has to enter into a 3-year interest-rate swap agreement. How should this be done, and what are the relevant parameters? Suppose at the time of the issue, the market makers were quoting. the swap spreads as given in Table 4.2. First we consider the calculation of all-in-cost for the. preceding deal.31  

# 4.7.1 ALL-IN-COST  

The information given in the details of the new issue implies that the coupon is $4\%$ . But, this is not the true costs of funds from the point of view of the issuer. There are at least three additional factors that need to be taken into account. (1) The reoffer price is not 100, but 99.659. This means that for each bond, the issuer will receive less cash than the par. (2) Fees have to be paid. (3) Although not mentioned in the information in Table 4.1, the issuer has legal and documentation expenses. We assume that these were USD75,000.  

To calculate the fixed all-in-cost (30/360 basis), we have to calculate the proceeds first. Proceeds is the net cash received by the issuer after the sale of the bonds. In our case, using the terminology of Table 4.1,  

$$
{\mathrm{Proceeds}}={\mathrm{Amount}}\times\left({\frac{\mathrm{Price}}{100}}-{\mathrm{Fees}}\right)-{\mathrm{Expenses}}
$$  

Plugging in the relevant amounts,  

$$
\begin{array}{c}{{\mathrm{Procesds}=200,000,000(0.99659-0.0020)-75,000}}\ {{\mathrm{}=198,843,000}}\end{array}
$$  

<html><body><table><tr><td colspan="4">Table 4.2 USD Swap Index Versus 12 month LIBOR, Semi, 30/360</td></tr><tr><td>Maturity</td><td>Bid Spread</td><td>Ask Spread</td><td>TheBid-Ask SwapRate</td></tr><tr><td>2 years</td><td>42</td><td>46</td><td>2.706-2.750</td></tr><tr><td>3 years</td><td>65</td><td>69</td><td>3.341-3.384</td></tr><tr><td>4 years</td><td>70</td><td>74</td><td>3.796-3.838</td></tr><tr><td>5 years</td><td>65</td><td>69</td><td>4.147-4.187</td></tr><tr><td>7 years</td><td>75</td><td>79</td><td>4.653-4.694</td></tr><tr><td>10 years</td><td>61</td><td>65</td><td>5.115-5.159</td></tr><tr><td>12 years</td><td>82</td><td>86</td><td>5.325-5.369</td></tr><tr><td>15 years</td><td>104</td><td>108</td><td>5.545-5.589</td></tr><tr><td>20 years</td><td>126</td><td>130</td><td>5.765-5.809</td></tr><tr><td>30 years</td><td>50</td><td>54</td><td>5.834-5.885</td></tr></table></body></html>  

Next, we see that the bond will make three coupon payments of 8 million each. Finally, the principal is returned in 3 years. The cash flows associated with this issue are summarized in Figure 4.12. What is the internal rate of return of this cash flow? This is given by the formula  

$$
198,843,000={\frac{8,000,000}{\left(1+y\right)}}+{\frac{8,000,000}{\left(1+y\right)^{2}}}+{\frac{8,000,000+200,000,000}{\left(1+y\right)^{3}}}
$$  

The $y$ that solves this equation is the internal rate of return. It can be interpreted as the true cost of the deal, and it is the fixed all-in-cost under the (30/360) day-count basis. The calculation gives  

$$
y=0.04209
$$  

This is the fixed all-in-cost.  

The next step is to swap this issue into floating and obtain the floating all-in-cost. Suppose we have the same notional amount of $\$200$ million and consider a fixed to floating 3-year interest-rate swap. Table 4.2 gives the 3-year receiver swap rate as $3.341\%$ . This is, by definition, a 30/360, semiannual rate.  

![](0da8d84e7c9b36d964d93bfb6be4ccef8842eeabd780f43065d9b7a0ad5424a1.jpg)  

# FIGURE 4.12  

New issue and interest-rate swap cash flows.  

This requires converting the semiannual swap rate into an annual 30/360 rate, denoted by $r.$ This is done as follows:  

$$
(1+r)=\left(1+0.03341{\frac{1}{2}}\right)^{2}
$$  

which gives  

$$
r=3.369\%
$$  

With a $\$200$ million notional, this is translated into three fixed receipts of  

$$
200,000,000(0.03369)=6,738,000
$$  

each. The cash flows are shown in Figure 4.12.  

Clearly, the fixed swap receipts are not equal to the fixed annual coupon payments, which are $\$8$ million each. Apparently, the issuer pays a higher rate than the swap rate due to higher credit risk. To make these two equal, we need to increase the fixed receipts by  

$$
8,000,000-6,738,000=1,262,000
$$  

This can be accomplished by increasing both the floating rate paid and the fixed rate received. by equivalent amounts. This can be accomplished if the issuer accepts paying LIBOR plus a spread equivalent to the 66 bp. Yet, here the 66 bp is p.a. 30/360, whereas the LIBOR convention is p.a. ACT/360. So the basis point difference of 66 bp may need to be adjusted further.32 The final. figure will be the floating all-in-cost and will be around. $60~\mathrm{bp}$  
