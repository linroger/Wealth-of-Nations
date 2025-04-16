---
tags:
  - '#cds_duration'
  - '#cds_index_payments'
  - '#cds_pricing'
  - '#default_payoff'
  - '#fixed_coupon_cds'
  - '#hazard_rate'
  - '#itraxx_europe_index'
  - '#recovery_rate'
---
# 25.4  THE USE OF FIXED COUPONS  

The precise way in which CDS and CDS index transactions work is a little more complicated than has been described up to now. For each underlying and each maturity, a coupon and a recovery rate are specified. A price is calculated from the quoted spread using the following procedure:  

1. Assume four payments per year, made in arrears.   
2. Imply a hazard rate from the quoted spread. This involves calculations similar to those in Section 25.2. An iterative search is used to determine the hazard rate that leads to the quoted spread.   
3. Calculate a "duration" $D$ for the CDS payments. This is the number that the spread is multiplied by to get the present value of the spread payments. (In the example in Section 25.2, it is 4.1150.)'   
4. The price $P$ is given by $P=100-100\times D\times(s-c)$ , where $s$ is the spread and $c$ is the coupon expressed in decimal form.  

When a trader buys protection the trader pays $100-P$ per $\$100$ of the total remaining notional and the seller of protection receives this amount. (If. $100~-~P$ is negative, the buyer ofprotectionreceives money andthe seller ofprotection paysmoney.) The buyer of protection then pays the coupon times the remaining notional on each payment date. (On a CDS, the remaining notional is the original notional until default and zero thereafter.. For a CDS index, the remaining notional is the number of names in the index that have not yet defaulted multiplied by the principal per name.) The payoff when there is a default is calculated in the usual way. This arrangement facilitates trading because the instruments trade like bonds. The regular quarterly payments made by the buyer of. protection are independent of the spread at the time the buyer enters into the contract.  

# Example 25.1  

Suppose that the iTraxx Europe index quote is 34 basis points and the coupon is 40 basis points for a contract lasting exactly 5 years, with both quotes being expressed using an actual/360 day count. (This is the usual day count convention in CDS and CDS index markets.) The equivalent actual/actual quotes are $0.345\%$ for the index and $0.406\%$ for the coupon. Suppose that the yield curve is flat at. $4\%$ per year (actual/actual, continuously compounded). The specified recovery rate is $40\%$ . With four payments per year in arrears, the implied hazard rate is $0.5717\%$ . The duration is 4.447 years. The price is therefore.  

$$
100-100\times4.447\times(0.00345-0.00406)=100.27
$$  

Consider a contract where protection is $\$1$ million per name. Initially, the seller of.   
protection would pay the buyer $\$1,000,000$ Thereafter, the buyer.   
of protection would make quarterly payments in arrears at an annual rate of.   
$\$1,000,000$ , where $n$ is the number of companies that have not.   
defaulted. When a company defaults, the payoff is calculated in the usual way.   
and there is an accrual payment from the buyer to the seller calculated at the rate of $0.406\%$ per year on. $\$1$ million.  
