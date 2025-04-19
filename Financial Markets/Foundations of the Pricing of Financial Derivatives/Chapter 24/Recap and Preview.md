---
tags:
  - '#explicit_finite_difference'
  - '#finite_difference_methods'
  - '#forward_rate'
  - '#implicit_finite_difference'
  - '#interest_rate_derivatives'
  - '#option_pricing'
  - '#term_structure_interest_rates'
  - '#unbiased_expectations_hypothesis'
  - '#yield_curve'
---
# 24.6 RECAP AND PREVIEW

In this chapter, we showed how options can be priced by finite difference methods. The finite difference approach specifies difference equations that approximate the differential equations that must hold to obtain the option price. These difference equations are solved by deriving their values over the range of possibilities, such that the option price at the start corresponds to the condition that the current underlying price and time to expiration are in effect. We showed two methods of achieving this result: the explicit and implicit finite difference methods. The former essentially creates a trinomial, which is solved in a similar manner to the binomial model. The latter solves simultaneous equations at each combination of asset price and time to expiration.

This completes Part V. In Part VI, we introduce a new type of underlying, specifically interest rates, which shall pose a special challenge in modeling the stochastic process of the underlying.

# QUESTIONS AND PROBLEMS

1 Based on the standard Black-Scholes-Merton partial differential equation, derive the following transformed PDE:  w $\begin{array}{r}{\frac{\sigma^{2}}{2}\frac{\partial^{2}w}{\partial y^{2}}+\left(r_{c}-\frac{\sigma^{2}}{2}\right)\frac{\partial w}{\partial y}+\frac{\partial w}{\partial t}-r_{c}w=0}\end{array}$ when $y=\ln(S)$
2 In general, explain the difference between the explicit finite difference method and the implicit finite difference method.. Explain how the finite difference methodology is changed when solving for put prices. Explain the impact dividends have on finite difference methods.
5 Compare and contrast the binomial option pricing model with the explicit finite difference method.
6 [Contributed by Jeremy Vasseur] Suppose you were creating a grid for a finite difference valuation of European puts. Explain how you would fill in the rightmost column, topmost row, and bottommost row. Assume the log transform approach is used. (Base your answer on the grid structure provided in Table 24.2.)

# NOTES

1. Some methods lead to an unstable solution, meaning a negative option price for certain asset. prices and times to expiration.
2. If we do not let $S$ be less than 1, then $\ln S$ would always be positive.
3. The option delta, gamma, and theta can be estimated by using approximations for the formulas for $\partial\bar{{w}}/\partial y,\partial^{2}{w}/\partial{y^{2}}$ , and $\partial w/\partial t$ based on the finite differences in the grid..
4. Without the log transform, there will be a different set of weights for each time point or column.

# Interest Rate Derivatives

# The Term Structure of Interest Rates

he term structure of interest rates is the relationship between the interest rate on a. bond or loan and the maturity.1 The term structure is often depicted with a graph,. sometimes called a yield curve. A typical question raised by the term structure is whether long-term rates are more than short-term rates and, if so, why? Of course, the issue is a bit more complex than that. The maturities of loans and bonds span a range from very short. term, as short perhaps as a day, to very long term, such as 30 years or more. Maturities cannot simply be dichotomized into short and long term. And it is difficult to make general statements, such as longer-term rates are higher than shorter-term rates. That might be true, but there can be more complex relationships between rates and maturities. Hence, there could be low short-term rates, high intermediate-term rates, and low long-term rates,. with bumps and dips in between. And, of course, the words low and high are relative and might mean different things to different people. Figure 25.1 illustrates three potential patterns for the term structure of interest rates. The top line depicts a common upward sloping yield curve and the bottom depicts a downward sloping yield curve. The middle curve illustrates that other patterns that are not necessarily upward or downward are also possible.

In general, however, we use the term structure to think about how rates of various maturities might differ. As we discussed in Chapter 22, the rate on a loan or bond of one maturity can be related to the rate on a loan or bond of a shorter-term maturity to produce a forward rate. For example, let us say that the rate on a five-year zero-coupon bond is $7.2\%$ , annual compounding, and the rate on a two-year zero-coupon bond is $6.9\%$ . The forward rate is found as follows:

$$
F=\sqrt[3]{\frac{(1.072)^{5}}{(1.069)^{2}}}-1=0.074.
$$

Much of the study of the term structure is about understanding what that forward rate might mean. We have already seen that it means that one could today enter into a contract to borrow or lend for three years with the loan starting two years from now. The rate would be agreed on today. There are some opinions that this number might tell us something about the direction of future interest rates. We explore this issue in this chapter.2

Almost anyone who has studied the term structure of interest rates, perhaps through a course in fixed income markets, is familiar with the unbiased expectations hypothesis (UEH),3 which proposes that the forward rate is an unbiased predictor of the future spot rate. Thus, the forward rate is seen as the expected spot rate. The question of whether the

![](4096044864612219b141f771328d558d50c44eb2bc32ae1f58d1e215c16b5014.jpg)
FIGURE 25.1Term Structure of Interest Rates Illustration

UEH is true has occupied a central place in research in our body of understanding of the. term structure, in particular in empirical research. There is no clear consensus empirically, but in fact it is a simple matter to prove that the unbiased expectations hypothesis cannot. be true theoretically and almost surely cannot be true in reality.4.
