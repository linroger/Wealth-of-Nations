---
tags:
  - accrued_interest
  - bond_pricing
  - clean_price
  - day_count_convention
  - dirty_price
aliases:
  - Flat Price
  - Full Price
  - Invoice Price
  - Quoted Price
key_concepts:
  - Accrued Interest Calculation
  - Actual/Actual Day-Count
  - Coupon Payment Division
  - Full vs. Flat Price
  - Present Value of Cash Flows
---

# 1.6 ACCRUED INTEREST  

This section describes the market practice of separating the full or invoice.   
price of a bond, which is the price paid by a buyer to the seller, into two.   
parts: a flat or quoted price, which appears on trading screens and is used.   
when negotiating transactions; and accrued interest. Full and flat prices are also known as dirty and clean prices, respectively..  

For concreteness, consider an investor who purchases $\$10,000$ face amount of the US Treasury 0.625s of. $08/15/2030$ , for settlement on May 17, 2021. The bond last made a coupon payment of $\$10,000$ $\$31.25$ on February 15, 2021, and makes its next coupon payment of $\$31.25$ on August 15, 2021. See the timeline in Figure 1.3..  

Assuming that the buyer holds the bond through August 15, 2021, the buyer collects the semiannual coupon on that date. But it can be argued that the buyer is not really entitled to the whole coupon because the buyer will have held the bond for only three months, that is, from May 17, 2021, to August 15, 2021. More precisely, using what is known as the actual/actual day-count convention, and referring again to Figure 1.3, the buyer should receive only 90 of the 181 days of the coupon payment, that is, $\$31.25\times90/181=\$15.539$ . The seller, on the other hand, who presumably. held the bond from the previous coupon date to the settlement date, should collect the rest of the coupon, namely, the accrued interest from February 15, 2021, to May 17, 2021, which is. $\$31.25\times91/181=\$15.711$  

![](be76cf3541902d3c63bd6b9de52f906a9396b8ab26cd60c81fff931825e1df38.jpg)  
FIGUrE 1.3 Timeline for Computing the Accrued Interest on the 0.625s of 08/15/2030 for Settlement on May 17, 2021.  

A conceivable institutional arrangement would be for the seller and the buyer to divide the coupon payment on the next payment date, but this would undesirably require additional arrangements to ensure compliance. Instead, market convention dictates that the buyer pay the seller the. $\$15.711$ of accrued interest on the settlement date, and that the buyer keep the entire. coupon of $\$31.25$ on the coupon payment date.  

The flat or quoted price of the 0.625s of. $08/15/2030$ on May 14, 2021, for settlement on May 17, is 91.78125. The full or invoice price,. which is defined as the flat or quoted price plus accrued interest, is $91.78125+0.15711=91.93836$ . For the particular trade just described, of $\$10,000$ face amount, the invoice amount is. $\$10,000$ $0.15711\%=\$178.125+515.711=\S9.193.836$ or, equivalently, $\$10,000$  

At this point, it becomes clear why earlier in the chapter it is noted that prices are full prices. With bonds paying coupons on May 15 and November 15, and with trades settling on Monday, May 17, 2021, buyers have to pay sellers two days of accrued interest.  

The full price of a bond, the amount a buyer actually pays to purchase a bond, should equal the present value of a bond's cash flows. Mathematically, denote the flat price of the bond by $p$ , accrued interest by. $A I$ , the present value of the cash flows by. $P V$ , and the full price by. $P$ . Then,  

$$
P=p+A I=P V
$$  

Equation (1.5) reveals that the particular market convention used to calculate accrued interest does not really matter. For example, the accrued. interest convention just described is conceptually too generous to the seller because, instead of being made to wait until the next coupon date,. the seller receives a share of the coupon at settlement. But the accrued interest convention changes neither the present value of all cash flows, $P V$ , in Equation (1.5), nor the full price,. $P$ , which is the amount actually. exchanged at settlement. The convention only changes the quoted market price, $\boldsymbol{p}$ , relative to the calculated amount of accrued interest. If accrued interest is in any sense too high, the market reduces. $\boldsymbol{p}$ accordingly.  

Having made this argument, why bother with the accrued interest convention in the first place; that is, why not just quote bonds using the full price? The answer is told in Figure 1.4, which draws the full and flat prices of the 0.625s of $08/15/2030$ from February 15, 2021, to September 15, 2021, under the simplifying assumption that interest rates are constant at the approximate market rate of $1.60\%$ over the entire period.7  

Figure 1.4 shows that the full price changes dramatically over time - including a sudden drop on August 15, 2021 - even though the market, in terms of interest rates, is unchanged. The flat price, by contrast, changes only gradually over time. Therefore, when trading bonds day to day, it is more intuitive to follow flat prices and negotiate transactions in those terms.  

The behavior of the prices in Figure 1.4 can be understood readily. First,. as of February 2021, the price of the bond is below 100, because its coupon rate is below the market rate for its maturity. But as the bond matures, its flat price approaches 100. (The dynamics of prices at below and above market rates are discussed further in Chapter 3.) Second, within a coupon period, the full price of a bond increases over time as its cash flows get closer to being paid, that is, as their present values increase. But from just before the coupon payment date to just after, the full price falls by the coupon payment: the coupon is included in the present value just before the payment, but not included just after. The flat price, by contrast, which equals the full price minus accrued interest, rises more gradually than the full price and does not fall precipitously just after the coupon payment. Because accrued interest just before the coupon payment nearly equals that coupon payment, subtracting accrued interest from the full price leaves the flat price essentially without that coupon - both just before and just after its payment date.  

![](eafa60056a4fb55742b35913a53ac79d3c09ac57b862553dddcf4039c285829b.jpg)  
FIGURE 1.4  Full and Flat Prices for the 0.625s of 08/15/2030, Assuming Constant Interest Rates.  
