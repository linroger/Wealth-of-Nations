---
tags:
  - '#accrued_interest'
  - '#actual_actual_in_period'
  - '#bond_valuation'
  - '#corporate_bonds'
  - '#day_count_conventions'
  - '#interest_calculation'
  - '#money_market_instruments'
  - '#price_quotations'
  - '#thirty_360'
  - '#treasury_bonds'
---
# 6.1 DAY COUNT AND QUOTATION CONVENTIONS  

As a preliminary to the material in this chapter, we consider the day count and quotation conventions that apply to bonds and other instruments dependent on interest rates.  

# Day Counts  

The day count defines the way in which interest accrues over time. Generally, we know the interest earned over some reference period (e.g., the time between coupon payments on a bond), and we are interested in calculating the interest earned over some other period.  

The day count convention is usually expressed as $X/Y$ When we are calculating the interest earned between two dates, $X$ defines the way in which the number of days between the two dates is calculated, and $Y$ defines the way in which the total number of days in the reference period is measured. The interest earned between the two dates is  

Number of days between dates. $\times$ Interest earned in reference period Number of days in reference period  

Three day count conventions that are commonly used in the United States are:  

1. Actual/actual (in period)   
2. 30/360   
3. Actual/360  

# Business Snapshot 6.1 Day Counts Can Be Deceptive  

Between February 28, 2018, and March 1, 2018, you have a choice between owning a. U.S. government bond and a U.S. corporate bond. They pay the same coupon and. have the same quoted price. Assuming no risk of default, which would you prefer?  

It sounds as though you should be indifferent, but in fact you should have a marked preference for the corporate bond. Under the 30/360 day count convention used for corporate bonds, there are 3 days between February 28, 2018, and March 1, 2018. Under the actual/actual (in period) day count convention used for government bonds, there is only 1 day. You would earn approximately three times as much interest by holding the corporate bond!  

The actual/actual (in period) day count is used for Treasury bonds in the United States. This means that the interest earned between two dates is based on the ratio of the actual days elapsed to the actual number of days in the period between coupon payments. Assume that the bond principal is $\$100$ , coupon payment dates are March 1 and September 1, and the coupon rate is $8\%$ per annum. (This means that $\$4$ of interest is paid on each of March 1 and September 1.) Suppose that we wish to calculate the interest earned between March 1 and July 3. The reference period is from March 1 to September 1. There are 184 (actual) days in the reference period, and interest of $\$4$ is earned during the period. There are 124 (actual) days between March 1 and July 3. The. interest earned between March 1 and July 3 is therefore  

$$
\frac{124}{184}\times4=2.6957
$$  

The $30/360$ day count is used for corporate and municipal bonds in the United States. This means that we assume 30 days per month and 360 days per year when carrying out calculations. With the $30/360$ day count, the total number of days between March 1 and. September 1 is 180. The total number of days between March 1 and July 3 is $(4\times30)+2=122.$ In a corporate bond with the same terms as the Treasury bond. just considered, the interest earned between March 1 and July 3 would therefore be  

$$
\frac{122}{180}\times4=2.7111
$$  

As shown in Business Snapshot 6.1, sometimes the 30/360 day count convention has surprising consequences.  

The actual/360 day count is used for money market instruments in the United States. This indicates that the reference period is 360 days. The interest earned during part of a year is calculated by dividing the actual number of elapsed days by 360 and multiplying by the rate. The interest earned in 90 days is therefore exactly one-fourth of the quoted rate, and the interest earned in a whole year of 365 days is 365/360 times the quoted rate.  

Conventions vary from country to country and from instrument to instrument. For. example, money market instruments are quoted on an actual/365 basis in Australia, Canada, and New Zealand. LIBOR is quoted on an actual/360 for all currencies except. sterling, for which it is quoted on an actual/365 basis. Euro-denominated and sterling. bonds are usually quoted on an actual/actual basis..  

# Price Quotations of U.S. Treasury Bills  

The prices of money market instruments are sometimes quoted using a discount rate. This is the interest earned as a percentage of the final face value rather than as a percentage of the initial price paid for the instrument. An example is Treasury bills in. the United States. If the price of a 91-day Treasury bill is quoted as 8, this means that the rate of interest earned is $8\%$ of the face value per 360 days. Suppose that the face. value is $\$100$ Interest of. $\$02322(=$ is earned over the 91-day life. This corresponds to a true rate of interest of. $2.0222/(100-2.0222)=2.064\%$ for the 91-day period. In general, the relationship between the cash price per $\$100$ of face value and the quoted price of a Treasury bill in the United States is.  

$$
P={\frac{360}{n}}(100-Y)
$$  

where $P$ is the quoted price,. $Y$ is the cash price, and. $n$ is the remaining life of the. Treasury bill measured in calendar days. For example, when the cash price of a 90-day Treasury bill is 99, the quoted price is 4..  

# Price Quotations of U.s. Treasury Bonds  

Treasury bond prices in the United States are quoted in dollars and thirty-seconds of a dollar. The quoted price is for a bond with a face value of $\$100$ . Thus, a quote of 120-05 or $12\dot{0}\frac{5}{32}$ indicates that the quoted price for a bond with a face value of $\$100,000$ is $\$120,156.25$  

The quoted price, which traders refer to as the clean price, is not the same as the cash price paid by the purchaser of the bond, which is referred to by traders as the dirty price. In general,  

Cash price $=$ Quoted price $^+$ Accrued interest since last coupon date  

To illustrate this formula, suppose that it is March 5, 2018, and the bond under consideration is an $11\%$ coupon bond maturing on July 10, 2038, with a quoted price of 155-16 or $\$155.50$ Because coupons are paid semiannually on government bonds (and the final coupon is at maturity), the most recent coupon date is January 10, 2018, and the next coupon date is July 10, 2018. The (actual) number of days between January 10, 2018, and March 5, 2018, is 54, whereas the (actual) number of days between January 10, 2018, and July 10, 2018, is 181. On a bond with $\$100$ face value, the coupon payment is $\$5.50$ on January 10 and July 10. The accrued interest on March 5, 2018, is the share of the July 10 coupon accruing to the bondholder on March 5, 2018. Because actual/actual in period is used for Treasury bonds in the United States, this is  

$$
{\frac{54}{181}}\times\$5.50=\$1.64
$$  

The cash price per $\$100$ face value for the bond is therefore  

$$
\$155.50+\S1.64=\S157.14
$$  

Thus, the cash price of a $\$100,000$ bond is $\$157,140$  
