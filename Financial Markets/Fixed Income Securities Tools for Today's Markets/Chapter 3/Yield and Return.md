---
tags:
  - bond_valuation
  - coupon_reinvestment
  - holding_period_return
  - realized_return
  - yield_to_maturity
aliases:
  - Bond Return
  - IRR
key_concepts:
  - Bond's Internal Rate
  - Holding Period Return
  - Initial Yield
  - Reinvested Coupons
  - Yield vs. Return
---

# 3.3 YIELD AND RETURN  

As mentioned earlier, yield to maturity is a convenient way to express price.   
in terms of a single rate of interest. And the definition of yield as the single.   
rate that equates the present value of a bond's cash flows to its price means.   
that yield is a bond's internal rate of return. But how does yield relate to a bond's realized return?.  

As it turns out, yield is only weakly related to realized returns. Appendix A3.2 shows that a bond's ex-post return is equal to its initial yield if i) all of the coupons are reinvested at the initial yield, and ii) if the yield at the end of the investment horizon is the same as the initial yield. These very restrictive conditions significantly weaken the interpretation of yield as a predictor of holding period return.  

To demonstrate this point with a concrete example, consider the return. on the 7.625s of 11/15/2022 from mid-May 2021 to mid-May 2022. Begin with Equation (3.5), which gives that bond's yield as of the start of that period, and multiply both sides by. $(1+y/2)^{2}$  

$$
111.3969\bigg(1+\frac{y}{2}\bigg)^{2}=3.8125\bigg(1+\frac{y}{2}\bigg)+3.8125+\frac{103.8125}{\bigg(1+\frac{y}{2}\bigg)}
$$  

The left-hand side is the proceeds from an investment of the price of the bond, 111.3969, for one year - or two semiannual periods - at the semiannually compounded rate $y$ . The right-hand side is the value of the bond position at the end of the one-year horizon, which is the sum of three parts: the proceeds from the first coupon, received on November 15, 2021, and invested for six months to May 15, 2022; the coupon received on May 15, 2022; and the price of the bond on May 15, 2022, if its yield is. $y$ . In words. then, Equation (3.9) says that the one-year return on the initial investment will be. $y$ if the first coupon is reinvested at. $y$ and if the bond, at the end of. the year, is priced at a yield of. $y$ . If $y$ in every term of (3.9) is the initial yield. of the bond, that is,. $0.0252\%$ , then the bond earns that initial yield over the year. But if the coupon reinvestment rate or the yield of the bond at the end of year have changed over time, and are not equal to. $0.0252\%$ , then the bond likely does not earn that rate over the one-year horizon..  

To see that a bond may not earn its initial yield even if held to maturity, multiply both sides of Equation (3.5) by $(1+y/2)^{3}$ to get,  

$$
111.3969\bigg(1+\frac{y}{2}\bigg)^{3}=3.8125\bigg(1+\frac{y}{2}\bigg)^{2}+3.8125\bigg(1+\frac{y}{2}\bigg)+103.8125
$$  

Now, the left-hand side is the proceeds from an investment of 111.3969 for 1.5 years. The right-hand side is the value of the bond position at maturity, that is, November 15, 2022, which is, again, the sum of reinvested coupons and the final coupon and principal payments. If. $y$ in every term of (3.10) is the initial yield, then the bond earns that initial yield to maturity. But if coupons are invested at a different rate, the bond does not earn its initial yield over its life..  

The 7.625s of 11/15/2022 are useful in making the point that yield does not coincide with horizon return, but its short maturity, along with its low yield, may give a misleading impression of orders of magnitude. Consider, therefore, buying the US Treasury 2.375s of $5/15/2051$ in mid-May 2021, at a price of 100.6875 or yield of $2.343\%$ , and holding it to maturity. Along the lines of the previous paragraphs, if all coupons are reinvested at $2.343\%$ , then the return on the initial investment over the 30 years is $2.343\%$ per year. But if rates were to fall suddenly and remain low, so that all coupons are invested at $0\%$ , or if the investor holds all coupon payments. in a non-interest-bearing account, the return on the bond to maturity falls to $1.778\%$ per year. If, on the other hand, rates were to rise suddenly and. remain high, so that all coupons were reinvested at. $5\%$ , then the bond return rises to $3.207\%$ per year. Reproducing these results is left as an exercise to. the reader.  
