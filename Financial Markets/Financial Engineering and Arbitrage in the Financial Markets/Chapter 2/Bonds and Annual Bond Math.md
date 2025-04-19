---
tags:
  - annual_interest_rate
  - bond_math
  - bond_valuation
  - coupon_bond
  - floating_rate_bond
  - zero_coupon_bond
aliases:
  - Bond Analysis
  - Bond Pricing
  - Loans and Bonds
key_concepts:
  - Bond characteristics
  - Cash flow valuation
  - Coupon bonds valuation
  - Discount bonds
  - Floating rate bonds
  - Interest rate reset
  - Par value bonds
  - Yield to maturity
  - Zero-coupon bonds
---

# 2.1 BONDS AND ANNUAL BOND MATH  

In this book, we use the term "loan' and "bond' interchangeably. A loan is a private credit. arrangement between a borrower and a lender in which the lender acquires rights to future. cash flows from the borrower. A lender, subsequently, can privately resell the loan to another willing lender. A bond is a publicly traded credit arrangement. The issuer borrows money by. selling the bond to a distributed group of creditors who can then resell their portion of the issued bonds to other willing creditors.  

Bonds that do not contain options are easy to analyze and value. They typically come in one of four forms: zero-coupon (discount) bonds, coupon bonds, amortizing bonds, and floating rate bonds.  

# 2.1.1 Zero-Coupon Bond  

Jack lends money to the ABC Company by buying a 4-year. $\$1,000$ face value zero-coupon bond. Let us suppose the interest rate (called the yield-to-maturity) Jack is going to earn is  

![](a40e9f6a293d21c6832128ed6543aab42757126308043fc1806448cf32aa02ee.jpg)  
Figure 2.1 A 4-year zero-coupon bond  

$5\%$ . Figure 2.1 illustrates how we can value the bond by discounting the cash flow back through time.  

$$
P_{0}=822.70={\frac{51,000}{(1.05)^{4}}}={\frac{1}{(1.05)}}\times{\frac{1}{(1.05)}}\times{\frac{1}{(1.05)}}\times{\frac{1}{(1.05)}}\times{\frac{1}{(1.05)}}\times{\frac{91,000}{(1.05)}}
$$  

In Figure 2.1 Jack is lending. $\$823.70$ to ABC today (the price he pays) and acquires a claim to receive $\$1,000$ in 4 years' time. Jack can resell this claim later for an amount that will depend on the interest rate at the time. The buyer will perform a backward discounting. calculation similar to that shown in the figure, but only using the remaining number of years to maturity. Only if the interest rate does not change and stays at. $5\%$ throughout the life of the. loan will the amounts shown in the dashed boxes represent the actual future prices of the bond.  

Zero-coupon bonds are typically issued with face values (par values) that are round numbers like $\$1,000$ $\$5,000$ , or $\$100,000$ . They are bought at a discount from par and the interest is imputed in the difference between the price paid (usually not a round number) and the face value received at maturity or the price received at the time of the resale. The price is typically quoted as the percent of par. In our example, the price would be quoted as 82.27. Note that the percent price converted to a fraction 0.8227 represents the value today of $\$1$ received 4 years from now. The number 0.8227 is called the discount factor..  

In general, bond and loan repayment values do not have to be round numbers. Suppose Jack was willing to lend $\$1,035.46$ to ABC. How much should he expect 4 years from now if he earns $5\%2$ Figure 2.2 illustrates the answer. This time we sweep forward starting with the known amount of the loan, i.e., the purchase price of the bond.  

In general, the price of the zero-coupon bond, expressed as a percentage of par, is equal to:  

$$
P_{0}=\frac{100}{(1+r)^{n}}
$$  

![](b446ca79284327ba9c2c9f46ef248753365765d663d75f02e887c4f3944d5e9a.jpg)  
Figure 2.2 A $\$1,035,46$ zero-coupon loan earning $5\%$  

where $r$ is the interest rate and. $n$ is the number of years. The spot discount factor (df) is defined as:  

$$
d f_{n}={\frac{1}{(1+r)^{n}}}
$$  

The discount factor will prove to be extremely important when we come to value other securities. Each security will be treated as a claim on a stream of cash flows at different times. We will find the present value of those cash flows by multiplying them by their respective discount factors and summing the products to get the total value of the security. The zerocoupon bond is the only bond that has only one cash flow. All other bonds have multiple cash flows.  

# 2.1.2 Coupon Bond  

A coupon bond pays a periodic stream of identical cash flows (called coupon interest) and a one-time cash flow at maturity (called the par or face value). Suppose Jack buys a 4-year $6\%$ annual coupon $\$1,000$ par value bond issued by the ABC Company to earn a $5\%$ annual interest rate (yield-to-maturity) on his investment. Figure 2.3 illustrates how we can value the bond.  

$$
P_{0}=1,035.46={\frac{1}{1.05}}\left(60+{\frac{1}{1.05}}\left(60+{\frac{1}{1.05}}\left(60+{\frac{1}{1.05}}(60+1,000\right)\right)\right)
$$  

Instead of going back in time step-by-step to discount and cumulate cash flows, we can value the coupon bond as the sum of its parts. The coupon bond is a package of four zero-coupon bonds with face values of $\$60,4560,78$ and $\$1,060$ and maturities 1, 2, 3, and 4 years, respectively. We do this by multiplying each coupon cash flow (face value of the component zero-coupon bond) by its appropriate discount factor. This factorization is illustrated in Figure 2.4.  

![](db4beb28d94b7a26f77713930a7ea0defc6bd94efcbdd6be54a97764bb20534f.jpg)  
Figure 2.3 A4-year $6\%$ coupon bond yielding $5\%$ : backward sweep  

$$
P_{0}=1,035.46={\frac{{\S60}}{(1.05)}}+{\frac{{\S60}}{(1.05)^{2}}}+{\frac{{\S60}}{(1.05)^{3}}}+{\frac{{\S1},060}{(1.05)^{4}}}
$$  

Also, we can factorize by separating the $\$1,000$ par from the rest of the cash flows:o.  

$$
P_{0}=1,035.46=560\times\left({\frac{1}{(1.05)}}+{\frac{1}{(1.05)^{2}}}+{\frac{1}{(1.05)^{3}}}+{\frac{1}{(1.05)^{4}}}\right)+{\frac{{\mathfrak{H}}1.000}{(1.05)^{4}}}
$$  

The two methods in Figures 2.3 and 2.4 - the backward step-by-step discounting sweep. and the sum of the parts' present values - are equivalent and always produce the same answer. Mathematically, it makes no difference whether we multiply. $n$ times in succession by oneperiod (forward) discount factors  

$$
d f_{n-1,n}=\frac{1}{(1+r_{n-1,n})}
$$  

![](88560852533d55790ec2d4e5717538f9a2cb7353ceb7287ceb49153f3200c33c.jpg)  
Figure 2.4  A 4-year $6\%$ coupon bond yielding $5\%$ : sum of the parts.  

or all at once by today's (spot) discount factors  

$$
d f_{n}={\frac{1}{(1+r_{n})^{n}}}
$$  

as long as the rates are all equal.  

One has to be a bit more careful, but the two methods are still identical when interest rates for different periods are not the same. We deal with the more complicated case of changing interest rates in Section 2.3 where we call $r_{n-1,n}$ forward zero rates and $r_{n}$ spot zero rates. We develop further the notion of forward rates in Chapter 3.  

# 2.1.3 Amortizing Bond  

An amortizing bond is also a multicash flow bond. Unlike the coupon bond which has an equal stream of coupon interest plus a one-time cash flow representing the return of par, the amortizing bond has a stream of equal cash flows, all of which can be thought of as partly coupon interest (on the remaining balance of the loan) and partly principal repayment. This distinction is somewhat artificial since the coupon interest of the coupon bond is generally not. the same as the interest rate earned on the amount invested in the bond. The real difference between the coupon bond and the amortizing bond is the pattern of cash flows. The amortizing.  

![](59f713d45dee8bbe976bddcb48b1fb83a08abbaffed473ad5de6e130e87de7ae.jpg)  
Figure 2.5 A 4-year amortizing loan yielding $5\%$ : sum of the parts  

bond's cash flows are all identical, and there is no large "balloon" payment at maturity.  

$$
\begin{array}{l}{{P_{0}=1,035.46=\frac{{\bar{9}292.01}}{(1.05)}+\frac{{\bar{5}292.01}}{(1.05)^{2}}+\frac{{\bar{5}292.01}}{(1.05)^{3}}+\frac{{\bar{5}292.01}}{(1.05)^{4}}}}\ {{{}=\bar{9}292.01\times\left(\frac{1}{(1.05)}+\frac{1}{(1.05)^{2}}+\frac{1}{(1.05)^{3}}+\frac{1}{(1.05)^{4}}\right)}}\end{array}
$$  

Figure 2.5 illustrates a 4-year amortizing loan of $\$1,035,46$ yielding a. $5\%$ interest rate. At.   
that rate, the lender receives. $\$292.01$ each period. (Think of a refrigerator priced at. $\$1,035,46$   
financed with a 4-year installment loan at. $5\%$ .) We value it using the sum-of-the-parts method.  

# 2.1.4 Floating Rate Bond  

The last type of bond, the floating rate bond, is also a multiple-cash flow bond. Similarly to. the coupon bond, it has a stream of coupon cash flows and a large balloon cash flow equal to the par value at maturity. However, the coupon cash flows are not known up front, but are set one period in advance: next coupon payment is set today, the coupon paid 2 years from today is set 1 year from today, the coupon paid 3 years from today is set 2 years from today, etc. The. idea is to reset the interest rate, as on a revolving loan, to a new "fair' rate each year, rather than holding it constant throughout of the life of the bond..  

![](00ea206c43f976c6dc9ed8fede7472153f26e8af53ee5165c02e9b8da5614c9a.jpg)  
Figure 2.6 A 4-year floating-rate bond: always worth par  

Since the cash flows are not known in advance (we use a tilde to denote a quantity unknown today), it may appear that the floating rate bond is impossible to value. In fact, as long as the. rates set each year are flat without a margin (i.e. LIBOR plus zero), the floating rate bond is. easy to value using the backward sweep method..  

We illustrate that in Figure 2.6. Suppose Jack lends to the ABC Company on a floating rate basis for 4 years. The face value of the bond is $\$1,000$ . Each year the bond's rate is set to a 1-year rate and the coupon interest is paid a year later (in arrears). At the penultimate time 3, we expect to receive 1 year later $\$1,000$ in principal plus the new coupon rate ${\tilde{x}}_{3}$ times $\$1,000$ in coupon interest. To discount from time 4 to time 3, we will multiply the cash flow $\$1,000$ $+\tilde{x}_{3}\times\S1\mathrm{,000}$ to be received at time 4 by the one-step discount factor $d f_{3,4}=1/(1+\tilde{x}_{3})$ That simply produces $\$1,000$ . This illustrates that after each coupon payment the value of the floating rate bond reverts to par. The floating rate bond is indeed equivalent to a guaranteed. revolving loan without the hassle of finding a borrower and re-signing papers each year..  

$$
\begin{array}{c}{\displaystyle\mathrm{~\boldmath~\rho~}_{0}^{,}=1,000=\frac{1}{1+x_{0}}}\ {\displaystyle~\times\left(1,000x_{0}+\frac{1}{1+\tilde{x}_{1}}\left(1,000\tilde{x}_{1}+\frac{1}{1+\tilde{x}_{2}}\left(1,000\tilde{x}_{0}+\frac{1}{1+\tilde{x}_{3}}(1,000\tilde{x}_{3}+1,000\right)\right)\right)}\end{array}
$$  
