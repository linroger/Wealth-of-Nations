# 29.1 BOND OPTIONS  

A bond option is an option to buy or sell a particular bond by a particular date for a particular price. In addition to trading in the over-the-counter market, bond options are frequently embedded in bonds when they are issued to make them more attractive to either the issuer or potential purchasers.  

# Embedded Bond Options  

One example of a bond with an embedded bond option is a callable bond. This is a bond that contains provisions allowing the issuing firm to buy back the bond at a.  

predetermined price at certain times in the future. The holder of such a bond has sold a call option to the issuer. The strike price or call price in the option is the. predetermined price that must be paid by the issuer to the holder. Callable bonds cannot usually be called for the first few years of their life. (This is known as the lockout period.) After that, the call price is usually a decreasing function of time. For example, in a 10-year callable bond, there might be no call privileges for the first 2 years. After that, the issuer might have the right to buy the bond back at a price of 110 in years 3 and 4 of its life, at a price of 107.5 in years 5 and 6, at a price of 106 in. years 7 and 8, and at a price of 103 in years 9 and 10. The value of the call option is reflected in the quoted yields on bonds. Bonds with call features generally offer higher. yields than bonds with no call features..  

Another type of bond with an embedded option is a puttable bond. This contains provisions that allow the holder to demand early redemption at a predetermined price. at certain times in the future. The holder of such a bond has purchased a put option on. the bond as well as the bond itself. Because the put option increases the value of the bond to the holder, bonds with put features provide lower yields than bonds with no put features. A simple example of a puttable bond is a 10-year bond where the holder has the right to be repaid at the end of 5 years. (This is sometimes referred to as a retractable bond.)  

Loan and deposit instruments also often contain embedded bond options. For. example, a 5-year fixed-rate deposit with a financial institution that can be redeemed without penalty at any time contains an American put option on a bond. (The deposit. instrument is a bond that the investor has the right to put back to the financial. institution at its face value at any time.) Prepayment privileges on loans and mortgages. are similarly call options on bonds..  

Finally, a loan commitment made by a bank or other financial institution is a put option on a bond. Consider, for example, the situation where a bank quotes a 5-year. interest rate of $3\%$ per annum to a potential borrower and states that the rate is good. for the next 2 months. The client has, in effect, obtained the right to sell a 5-year bond with a $3\%$ coupon to the financial institution for its face value any time within the next 2 months. The option will be exercised if rates increase..  

# European Bond Options  

Many over-the-counter bond options and some embedded bond options are European. The assumption made in the standard market model for valuing European bond options is that the forward bond price has a volatility $\sigma_{B}$ . This allows Black's model. in Section 28.6 to be used. In equations (28.28) and (28.29), $\sigma_{F}$ is set equal to $\sigma_{B}$ and $F_{0}$ is set equal to the forward bond price. $F_{B}$ , so that  

$$
\begin{array}{l}{{c=P(0,T)[F_{B}N(d_{1})-K N(d_{2})]}}\ {{}}\ {{p=P(0,T)[K N(-d_{2})-F_{B}N(-d_{1})]}}\end{array}
$$  

where  

$$
d_{1}=\frac{\ln(F_{B}/K)+\sigma_{B}^{2}T/2}{\sigma_{B}\sqrt{T}}\quad\mathrm{and}\quad d_{2}=d_{1}-\sigma_{B}\sqrt{T}
$$  

In these equations, $K$ is the strike price of the bond option, $T$ is its time to maturity, and $P(0,T)$ is the (risk-free) discount factor for maturity $T$  

From Section 5.5, $F_{B}$ can be calculated using the formula  

$$
F_{B}=\frac{B_{0}-I}{P(0,T)}
$$  

where $B_{0}$ is the bond price at time zero and. $I$ is the present value of the coupons that. will be paid during the life of the option. In this formula, both the spot bond price and the forward bond price are cash prices rather than quoted prices. The relationship. between cash and quoted bond prices is explained in Section 6.1..  

The strike price. $K$ in equations (29.1) and (29.2) should be the cash strike price. In. choosing the correct value for. $K$ the precise terms of the option are therefore. important. If the strike price is defined as the cash amount that is exchanged for the bond when the option is exercised,. $K$ should be set equal to this strike price. If, as is more common, the strike price is the quoted price applicable when the option is. exercised, $K$ should be set equal to the strike price plus accrued interest at the expiration. date of the option. Traders refer to the quoted price of a bond as the clean price and the. cash price as the dirty price..  

# Example 29.1  

Consider a 10-month European call option on a 9.75-year bond with a face value of $\$1,000$ .(When the option matures, the bond will have 8 years and 11 months remaining.) Suppose that the current cash bond price is $\$960$ , the strike price is $\$1,000$ , the 10-month risk-free interest rate is $10\%$ per annum, and. the volatility of the forward bond price for a contract maturing in 10 months is $9\%$ per annum. The bond pays a coupon of. $10\%$ per year (with payments made semiannually). Coupon payments of $\$50$ are expected in 3 months and 9 months. (This means that the accrued interest is $\$25$ and the quoted bond price is. $\$935$ We suppose that the 3-month and 9-month risk-free interest rates are $9.0\%$ and $9.5\%$ per annum, respectively. The present value of the coupon payments is, therefore,  

$$
50e^{-0.25\times0.09}+50e^{-0.75\times0.095}=95.45
$$  

or $\$95.45$ . The bond forward price is from equation (29.3) given by  

$$
F_{B}=(960-95.45)e^{0.1\times0.8333}=939.68
$$  

(a) If the strike price is the cash price that would be paid for the bond on exercise, the parameters for equation (29.1) are $F_{B}=939.68\$ $K=1000$ $\textstyle P(0,T)=$ e-0.1(10/12) = 0.9200, oB = 0.09, and T = 10/12. The price of the call option is $\$9.49$  

(b) If the strike price is the quoted price that would be paid for the bond on exercise, 1 month's accrued interest must be added to $K$ because the maturity of the option is 1 month after a coupon date. This produces a value for $K$ of  

$$
1,000+100\times0.08333=1,008.33
$$  

The values for the other parameters in equation (29.1) are unchanged (i.e., $F_{B}=939.68,P(0,T)=0.9200,\sigma_{B}=0.09$ and $T=0.8333$ ). The price of the option is $\$7.97$  

Figure 29.1 shows how the standard deviation of the logarithm of a bond's price changes as we look further ahead. The standard deviation is zero today because there is no uncertainty about the bond's price today. It is also zero at the bond's maturity because we know that the bond's price will equal its face value at maturity. Between today and the maturity of the bond, the standard deviation first increases and then decreases.  

![](images/73484d2ec9db0a721972f24cabc8adb70560c838c1232f3d6aeaebae684558cb.jpg)  
Figure 29.1 Standard deviation of logarithm of bond price at future times.  

The volatility $\sigma_{B}$ that should be used when a European option on the bond is valued is  

Standard deviation of logarithm of bond price at maturity of option  

What happens when, for a particular underlying bond, the life of the option is increased? Figure 29.2 shows a typical pattern for $\sigma_{B}$ as a function of the life of the option, with $\sigma_{B}$ declining as the life of the option increases.  

![](images/4a37261eb1e2ac51109d345955793cfde1dfce4c1b8930c9bac911a5d0afb743.jpg)  
Figure 29.2 Variation of forward bond price volatility $\sigma_{B}$ with life of option when bond is kept fixed.  

# Yield Volatilities  

The volatilities that are quoted for bond options are often yield volatilities rather than price volatilities. The duration concept, introduced in Chapter 4, is used by the market to convert a quoted yield volatility into a price volatility. Suppose that. $D$ is the modified duration of the bond underlying the option at the option maturity, as defined in Chapter 4. The relationship between the change $\Delta F_{B}$ in the forward bond price. $F_{B}$ and the change $\Delta y_{F}$ in the forward yield. $y_{F}$ is  

$$
\frac{\Delta F_{B}}{F_{B}}\approx-D\Delta y_{F}
$$  

or  

$$
\frac{\Delta F_{B}}{F_{B}}\approx-D y_{F}\frac{\Delta y_{F}}{y_{F}}
$$  

Volatility is a measure of the standard deviation of percentage changes in the value of a variable. This equation therefore suggests that the volatility of the forward bond price $\sigma_{B}$ used in Black's model can be approximately related to the volatility of the forward bond yield $\sigma_{y}$ by  

$$
\sigma_{B}=D y_{0}\sigma_{y}
$$  

where $y_{0}$ is the initial value of $y_{F}$ . When a yield volatility is quoted for a European bond option, the implicit assumption is usually that it will be converted to a price volatility using equation (29.4), and that this volatility will then be used in conjunction with equation (29.1) or (29.2) to obtain the option's price. Suppose that the bond underlying a call option will have a modified duration of 5 years at option maturity, the forward yield is $8\%$ , and the forward yield volatility quoted by a broker is $20\%$ . This means that the market price of the option corresponding to the broker quote is the price given by equation (29.1) when the volatility variable $\sigma_{B}$ is  

$$
5\times0.08\times0.2=0.08
$$  

or $8\%$ per annum. Figure 29.2 shows that forward bond volatilities depend on the. option considered. Forward yield volatilities as we have just defined them are more constant. This is why traders prefer them..  

The Bond_Options worksheet of the software DerivaGem accompanying this book can be used to price European bond options using Black's model by selecting BlackEuropean as the Pricing Model. The user inputs a yield volatility, which is handled in. the way just described. The strike price can be the cash or quoted strike price..  

# Example 29.2  

Consider a European put option on a 10-year bond with a principal of 100. The coupon is $8\%$ per year payable semiannually. The life of the option is 2.25 years. and the strike price of the option is 115. The forward yield volatility is. $20\%$ . The zero curve is flat at $5\%$ with continuous compounding. The DerivaGem software accompanying this book shows that the quoted price of the bond is 122.82. The price of the option when the strike price is a quoted price is. $\$2.36$ When the strike price is a cash price, the price of the option is. $\$1.74$ . (See Problem 29.16 for the manual calculation.)  
