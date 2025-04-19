---
tags:
  - '#binomial_model'
  - '#complex_assets'
  - '#forward_rate_agreement_fra'
  - '#heath_jarrow_morton_model'
  - '#interest_rate_derivatives'
  - '#option_pricing'
  - '#pure_assets'
  - '#state_contingent_claims'
  - '#state_preference_theory'
  - '#state_pricing_theory'
---
# 28.11 RECAP AND PREVIEW

In this chapter, we showed how to use the binomial version of the one-factor Heath-. Jarrow-Morton model to price almost every type of interest rate derivative. We showed that the technique involves discounting the risk-neutral expected value at the upcoming. nodes, with discounting at the risk-free rate..

This material completes Part VI on the pricing of interest rate derivatives. Part VII is a collection of miscellaneous topics. In Chapter 29, we show how option prices are related to the prices of state contingent claims.

# QUESTIONS AND PROBLEMS

Based on material in Chapter 28 and within the discretized version of the Heath-Jarrow-Morton forward rate stochastic process, compute the appropriate forward rate tree and bond price tree at times 1, 2, and 3, based on the following inputs. The next four problems build on these results.

$$
\begin{array}{r l r}&{}&{f(0,0)=0.030\qquad\sigma(0,1)=0.02}\ &{}&{f(0,1)=0.029\mathrm{and}\sigma(0,2)=0.03}\ &{}&{f(0,2)=0.028\qquad\sigma(0,3)=0.01.}\ &{}&{f(0,3)=0.027}\end{array}
$$

2 Based on your results in Problem 1, build the coupon bond price tree assuming a $1.5\%$ stated coupon and four-year maturity. Assume 1.0 par..

3 Based on your results in Problems 1 and 2, build the call and put option on coupon bond price tree assuming a 1.0 exercise price, three-year option expiration, $1.5\%$ stated coupon, and four-year maturity. Assume 1.0 par and expiration occurs an instant before the coupon is paid.
4 Based on your results in Problem 1 and 3, build the callable coupon bond price tree assuming a $1.5\%$ stated coupon, four-year maturity, callable starting in year 1, and the call price is par (1.0).
5 Based on your results in Problem 1, compute the at-market fixed FRA rate expiring at. time 3 for a one-period spot rate. Further, illustrate the receive floating FRA value tree and thus verifv vour results.

# NOTES

1. The notation is going to get a bit messy later on when we have to put the arguments for both the characteristics of the underlying and derivative in parentheses.
2. Alternatively, we could simply multiply by the price of a one-period zero-coupon bond, and we shall do it this way later in this chapter.
3. Recall that with FRAs, the payoff is subject to discounting, because the payoff is made at expiration, but is based on a rate that represents interest that would be paid later if it were a loan.
4. Of course, that is also what we did with swaps.

# Miscellaneous Topics

# Option Prices and the Prices of State-Contingent Claims

n option is sometimes referred to as a contingent claim. A contingent claim is a special happening. An option is a contingent claim in that it provides a positive payoff under the condition that the option expires in-the-money. If the option does not expire in-the-money,. the payoff is obviously zero. In this chapter, we look at another form of a contingent claim. that happens to be an asset that pays 1.0 in a given outcome and zero otherwise. These outcomes are referred to as states or states of nature, and this particular asset is sometimes. called a state-contingent claim. Other common names for this type of security are pure asset, the term we shall use, fundamental asset, and Arrow-Debreu asset, the last arising out of the work of Nobel Laureates Kenneth Arrow (1964) and Gerard Debreu (1964) and the extension to valuation by Myers (1968).1 In this chapter, we examine some properties of pure assets and demonstrate how they relate to options in a framework called state. preference theory and occasionally state pricing theory.

State pricing theory, which is also sometimes known as time state preference theory,. provides a framework for the valuation of financial assets. It can be shown to provide a general equilibrium theory of asset pricing, consistent with a market in which assets. are risky, and investors have homogeneous beliefs and aversion to risk. State preference theory was developed around the same time as the capital asset pricing model but has not received as much attention as the capital asset pricing model. This is probably because state preference theory is a more abstract theoretical framework, relying as it does on the existence of pure assets, whose prices cannot be observed in financial newspapers, from the Bloomberg, or on the internet. It is more appropriately viewed as what one would see. if one took a microscopic look at the financial markets.

In order to understand this material, we shall have to tread carefully with the terminology. We shall make reference to assets that could be stocks, bonds, or commodities, and we shall call them complex assets, though there is nothing particularly complex about them. A share of Google stock is a complex asset, a barrel of oil is a complex asset, a bond issued by GE is a complex asset. They are complex assets in that they are made up of pure assets. In some ways, this idea is analogous to the fact that humans (and animals) are complex combinations of fundamental elements. In fact, you should think of this chapter as taking. a microscopic look at a financial market and learning about the basic building blocks that enable markets to generate prices. It so happens that pure assets play a tremendous role in the functioning of a market. As such, we can gain a better appreciation for the value that. options provide markets and society as a whole..
