---
Owner: RRoger Lin
linter-yaml-title-alias: THE PRICING OF OPTIONS AND CORPORATE LIABILITIES
title: THE PRICING OF OPTIONS AND CORPORATE LIABILITIES
tags:
  - american_option
  - black_scholes_model
  - corporate_liabilities
  - european_option
  - option_pricing
aliases:
  - Black-Scholes
  - Corporate Debt
  - Option Pricing
key_concepts:
  - American vs European options
  - Call option definition
  - Exercise price and expiration
  - Option valuation formula
  - Option volatility analysis
---

# The Pricing of Options and Corporate Liabilities
- **[[Teaching Note 4-Multiperiod Binomial Trees]]**
	- [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing]]
	- [[Binomial Tree Steps]]
	- [[Calculate Stock Prices at Different Nodes]]
	- [[Options Strategies Construction]]
	- [[Teaching Note 4-Multiperiod Binomial Trees]]
	- [[Financial Instruments/Lecture Notes/Teaching Note 4-Multiperiod Binomial Trees/The Pricing of Options and Corporate Liabilities]]
[[Options]]
Fischer Black

> University of Chicago

Myron Scholes

> Massachusetts Institute of Technology

If options are correctly priced in the market, it should not be possible to make sure profits by creating portfolios of long and short positions in options and their underlying stocks. Using this principle, a theoretical valuation formula for options is derived. Since almost all corporate liabilities can be viewed as combinations of options, the formula and the analysis that led to it are also applicable to corporate liabilities such as common stock, [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]], and warrants. In particular, the formula can be used to derive the discount that should be applied to a corporate bond because of the possibility of default.

## INTRODUCTION

An option is a security giving the right to buy or sell an asset, subject to certain conditions, within a specified period of time. An "American option" is one that can be exercised at any time up to the date the option expires. A "European option" is one that can be exercised only on a specified future date. The price that is paid for the asset when the option is exercised is called the "exercise price" or "striking price." The last day on which the option may be exercised is called the "expiration date" or "maturity date."

The simplest kind of option is one that gives the right to buy a single share of common stock. Throughout most of the paper, we will be discussing this kind of option, which is often referred to as a "call option."

On the other hand, if the price of the stock is much less than the exercise price, the option is almost sure to expire without being exercised, so its value will be near zero.

If the expiration date of the option is very far in the future, then the price of a bond that pays the exercise price on the maturity date will be very low, and the value of the option will be approximately equal to the price of the stock.

On the other hand, if the expiration date is very near, the value of the option will be approximately equal to the stock price minus the exercise price, or zero, if the stock price is less than the exercise price. Normally, the value of an option declines as its maturity date approaches, if the value of the stock does not change.

These general properties of the relation between the option value and the stock price are often illustrated in a diagram like figure 1. Line A represents the maximum value of the option, since it cannot be worth more than the stock. Line B represents the minimum value of the option, since its value cannot be negative and cannot be less than the stock price minus the exercise price. Lines T1, 112, and 113 represent the value of the option for successively shorter maturities.

 ![500](Pasted%20image%2020240916034719.png)

Normally, the curve representing the value of an option will be concave upward. Since it also lies below the 45 line, A, we can see that the option will be more volatile than the stock. A given percentage change in the stock price, holding maturity constant, will result in a larger percentage change in the option value. The relative volatility of the option is not constant, however. It depends on both the stock price and maturity.

Most of the previous work on the valuation of options has been expressed in terms of warrants. For example, Sprenkle (1961), Ayres (1963), Boness (1964), Samuelson (1965), Baumol, Malkiel, and Quandt (1966), and Chen (1970) all produced valuation formulas of the same general form. Their formulas, however, were not complete, since they all involved one or more arbitrary parameters.

For example, Snrenkle's formula for the value of an option can be written as follows:

$\begin{matrix} & \text{kxN}\left(b_{1} \right) - k^{}\text{cN}\left(b_{2} \right) \\ & b_{1} = \frac{ln\text{kx}/c + \frac{1}{2}v^{2}\left(t^{} - t \right)}{v\sqrt{\left(t^{} - t \right)}} \\ & b_{2} = \frac{ln\text{kx}/c - \frac{1}{2}v^{2}\left(t^{} - t \right)}{v\sqrt{\left(t^{*} - t \right)}}\end{matrix}$

In this expression, x is the stock price, c is the exercise price, t* is the maturitv date, t is the current date, v 2 is the variance rate of the return on the stock, 1 In is the natural logarithm, and N (b) is the cumulative normal density function. But k and k* are unknown parameters. Sprenkle (1961) defines k as the ratio of the expected value of the stock price at the time the warrant matures to the current stock price, and k* as a discount factor that depends on the risk of the 'stock. He tries to estimate the values of k and k* empirically, but finds that he is unable to do so.

More typically, Samuelson (1965) has unknown parameters a and (3, where (1 is the rate of expected return on the stock, and (3 is the rate of expected return on the warrant or the discount rate to be applied to the warrant. 2 He assumes that the distribution of possible values of the stock when the warrant matures is log-normal and takes the expected value of this distribution, cutting it off at the exercise price. He then discounts this expected value to the present at the rate (3. Unfortunately, there seems to be no model of the pricing of securities under conditions of capital market equilibrium that would make this an appropriate procedure for determining the value of a warrant.

In a subsequent paper, Samuelson and Merton (1969) recognize the fact that discounting the expected value of the distribution of possible values of the warrant when it is exercised is not an appropriate procedure. They advance the theory by treating the option price as a function of the stock price. They also recognize that the discount rates are determined in part by the requirement that investors be willing to hold all of the outstanding amounts of both the stock and the option. But they do not make use of the fact that investors must hold other assets as well, so that the risk of an option or stock that affects its discount rate is only that part of the risk that cannot be diversified away. Their final formula depends on the shape of the utility function that they assume for the typical investor.

One of the concepts that we use in developing our model is expressed by Thorp and Kassouf (1967). They obtain an empirical valuation formula for warrants by fitting a curve to actual warrant prices. Then they use this formula to calculate the ratio of shares of stock to options needed to create a hedged position by going long in one security and short in the other. What they fail to pursue is the fact that in equilibrium, the expected return on such a hedged position must be equal to the return on a riskless asset. What we show below is that this equilibrium condition can be used to derive a theoretical valuation formula.

**The Valuation Formula**

In deriving our formula for the value of an option in terms of the price of the stock, we will assume "ideal conditions" in the market for the stock and for the option:

1. a) The short-term interest rate is known and is constant through time. b) The stock price follows a random walk in continuous time with a variance rate proportional to the square of the stock price. Thus the distribution of possible stock prices at the end of any finite interval is lognormal. The variance rate of the return on the stock is constant.
2. The stock pays no dividends or other distributions.
3. The option is "European," that is, it can only be exercised at maturity.
4. There are no transaction costs in buying or selling the stock or the option.
5. It is possible to borrow any fraction of the price of a security to buy it or to hold it, at the short-term interest rate.
6. There are no penalties to short selling. A seller who does not own a security will simply accept the price of the security from a buyer, and will agree to settle with the buyer on some future date by paying him an amount equal to the price of the security on that date.

Under these assumptions, the value of the option will depend only on the price of the stock and time and on variables that are taken to be known constants. Thus, it is possible to create a hedged position, consisting of a long position in the stock and a short position in the option, whose value will not depend on the price of the stock, but will depend only on time and the values of known constants. Writing w(x, t) for the value of the option as a function of the stock price x and time t, the number of options that must be sold short against one share of stock long is:

$1/W_1(x,t)$

In expression (1), the subscript refers to the partial derivative of w(x,t) with respect to its first argument.

To see that the value of such a hedged position does not depend on the price of the stock, note that the ratio of the change in the option value to the change in the stock price, when the change in the stock price is small, is WI (x,t). To a first approximation, if the stock price changes by an amount Ax, the option price will change by an amount WI (x,t) Ax, and the number of options given by expression (1) will change by an amount Ax. Thus, the change in the value of a long position in the stock will be approximately offset by the change in value of a short position in 1/WI options.

As the variables x and t change, the number of options to be sold short to create a hedged position with one share of stock changes. If the hedge is maintained continuously, then the approximations mentioned above become exact, and the return on the hedged position is completely independent of the change in the value of the stock. In fact, the return on the hedged position becomes certain. 3

To illustrate the formation of the hedged position, let us refer to the solid line (T 2) in figure 1 and assume that the price of the stock starts at 15.00, so that the value of the option starts at 5.00. Assume also that the slope of the line at that point is 1 2. This means that the hedged position is created by buying one share of stock and selling two options short. One share of stock costs 15.00, and the sale of two options brings in 10.00, so the equity in this position is 5.00.

If the hedged position is not changed as the price of the stock changes, then there is some uncertainty in the value of the equity at the end of a finite interval. Suppose that two options go from 10.00 to 15.75 when the stock goes from 15.00 to 20.00, and that they go from 10.00 to 5.75 when the stock goes from 15.00 to 10.00. Thus, the equity goes from 5.00 to 4.25 when the stock changes by 5.00 in either direction. This is a decline in the equity for a 5.00 change in the stock in either direction

1. This was pointed out to us by Robert Merton.
2. These figures are purely for illustrative purposes. They correspond roughly to the way figure 1 was drawn, but not to an option on any actual security.

In addition, the curve shifts (say from T2 to T3 in fig. 1) as the maturity of the options changes. The resulting decline in value of the options means an increase in the equity in the hedged position and tends to offset the possible losses due to a large change in the stock price.

Note that the decline in the equity value due to a large change in the stock price is small. The ratio of the decline in the equity value to the magnitude of the change in the stock price becomes smaller as the magnitude of the change in the stock price becomes smaller.

Thus the risk in the hedged position is zero if the short position in the option is adjusted continuously. If the position is not adjusted continuously, the risk is small, and consists entirely of risk that can be diversified away by forming a portfolio of a large number of such hedged positions.

In general, since the hedged position contains one share of stock long and 1/WI options short, the value of the equity in the position is:

_$x − w/w1$_﻿ (2)

The change in the value of the equity in a short interval _Δt_ is:

_$Δx − Δw/w1$_﻿.

Assuming that the short position is changed continuously, we can use stochastic calculus  5 to expand _Δw_, which is _$w(x + Δx, t + Δt) − w(x, t)$_﻿, as follows:

$\Delta w = w_{1}\Delta x + \frac{1}{2}w_{11}v^{2}x^{2}\Delta t + w_{2}\Delta t.$

In equation (4), the subscripts on _w_ refer to partial derivatives, and _v_2 is the variance rate of the return on the stock.  6 Substituting from equation (4) into expression (3), we find that the change in the value of the equity in the hedged position is:

$\left(\frac{1}{2}w_{11}v^{2}x^{2} + w_{2} \right)\Delta t/w_{1}$

Since the return on the equity in the hedged position is certain, the return must be equal to rΔt. Even if the hedged position is not changedcontinuously, its risk is small and is entirely risk that can be diversified away, so the expected return on the hedged position must be at the short term interest rate. 7 If this were not true, speculators would try to profit by borrowing large amounts of money to create such hedged positions, and would in the process force the returns down to the short term interest rate.

Thus the change in the equity (5) must equal the value of the equity (2) times _rΔt_.

$\left(\frac{1}{2}w_{11}v^{2}x^{2} + w_{2} \right)\Delta t/w_{1} = \left(x - w/w_{1} \right)r\Delta t$

Dropping the _Δt_ from both sides, and rearranging, we have a differential equation for the value of the option.

$w_{2} = \text{rw} - \text{rx}w_{1} - \frac{1}{2}v^{2}x^{2}w_{11}.$

Writing _t_* for the maturity date of the option, and _c_ for the exercise price, we know that:

$\begin{matrix} w\left(x,t^{*} \right) & \ = x - c, & & x \geqslant c \\ & \ = 0, & & x < c. \\ \end{matrix}$

There is only one formula _w_(_x_, _t_) that satisfies the differential equation (7) subject to the boundary condition (8). This formula must be the option valuation formula.

To solve this differential equation, we make the following substitution:

$w(x,t) = e^{r\left(t - t^{*} \right)}y\left\lbrack \left(2/v^{2} \right)\left(r - \frac{1}{2}v^{2} \right) \right]$

$\begin{matrix} & \left\lbrack lnx/c - \left(r - \frac{1}{2}v^{2} \right)\left(t - t^{} \right) \right\rbrack, \\ & \left. \ - \left(2/v^{2} \right)\left(r - \frac{1}{2}v^{2} \right)^{2}\left(t - t^{} \right) \right\rbrack.(9) \\ & u_{2} = \text{ru} - \text{rx}u_{1} - \frac{1}{2}v^{2}x^{2}u_{11}. \\ \end{matrix}$

With this substitution, the differential equation becomes:

$y_{22} = y_{11},$

and the boundary condition becomes:

$\begin{matrix} y(u) & \ = 0, & & u < 0 \\ & \ = c\left\lbrack e^{u\left(\frac{1}{2}v^{2} \right)/\left(r - \frac{1}{2}v^{2} \right)} - 1 \right\rbrack, & & u \geqslant 0. \\ \end{matrix}$

The differential equation (10) is the heat-transfer equation of physics, and its solution is given by Churchill (1963, p. 155). In our notation, the solution is:

$y(u,s)=1/\sqrt{2\pi}\int_{-u/\sqrt{2s}}^{\infty}$

$c\left\lbrack e^{(u + q\sqrt{2s})\left(\frac{1}{2}v^{2} \right)/\left(r - \frac{1}{2}v^{2} \right)} - 1 \right\rbrack e^{q^{2/2}}\text{dq}$

Substituting from equation (12) into equation (9), and simplifying, we find:

$\begin{matrix} w(x,t) & \ = \text{xN}\left(d_{1} \right) - ce^{r\left(t - t^{} \right)}N\left(d_{2} \right) \\ d_{1} & \ = \frac{lnx/c + \left(r + \frac{1}{2}v^{2} \right)\left(t^{} - t \right)}{v\sqrt{t^{} - t}} \\ d_{2} & \ = \frac{lnx/c + \left(r - \frac{1}{2}v^{2} \right)\left(t^{} - t \right)}{v\sqrt{t^{*} - t}} \\ \end{matrix}$

In equation (13), N (d) is the cumulative normal density function.

Note that the expected return on the stock does not appear in equation (13). The option value as a function of the stock price is independent of the expected return on the stock. The expected return on the option, however, will depend on the expected return on the stock. The faster the stock price rises, the faster the option price will rise through the functional relationship (13).

Note that the maturity (t* t) appears in the formula only multiplied by the interest rate r or the variance rate v 2. Thus, an increase in maturity has the same effect on the value of the option as an equal percentage increase in both r and v 2.

Merton (1973) has shown that the option value as given by equation (13) increases continuously as any one of$t^*, r, \text{ or } v_2$﻿ increases. In each case, it approaches a maximum value equal to the stock price.

The partial derivative WI of the valuation formula is of interest, because it determines the ratio of shares of stock to options in the hedged position as in expression (1). Taking the partial derivative of equation (13), and simplifying, we find that:

_$w1(x, t) = N(d1$_﻿) (14)

In equation (14), dl is as defined in equation (13).

From equations (13) and (14), it is clear that$xw_1/w$﻿ is always greater than one. This shows that the option is always more volatile than the stock.

**An Alternative Derivation**

It is also possible to derive the differential equation (7) using the "capital asset pricing model." This derivation is given because it gives more understanding of the way in which one can discount the value of an option to the present, using a discount rate that depends on both time and the price of the stock.

The capital asset pricing model describes the relation between risk and expected return for a capital asset under conditions of market equilibrium. The expected return on an asset gives the discount that must be applied to the end-of-period value of the asset to give its present value. Thus, the capital-asset pricing model gives a general method for discounting under uncertainty.

The capital-asset pricing model says that the expected return on an asset is a linear function of its$\beta$﻿, which is defined as the covariance of the return on the asset with the return on the market, divided by the variance of the return on the market. From equation (4) we see that the covariance of the return on the option Aw w with the return on the market is equal to w times the covariance of the return on the stock$\Delta x/x$﻿ with the return on the market. Thus, we have the following relation between the option's$\beta$﻿ and the stock's$\beta$﻿

$βw = (xw1/w)βx (15)$

The expression$xw_1/w$﻿ may also be interpreted as the "elasticity" of the option price with respect to the stock price. It is the ratio of the percentage change in the option price to the percentage change in the stock price, for small percentage changes, holding maturity constant.

To apply the capital-asset pricing model to an option and the underlying stock, let us first define a as the rate of expected return on the market minus the interest rate. 3 Then the expected return on the option and the stock are:

$\begin{matrix}E(\Delta x/x)=r\Delta t+a\beta_x\Delta t,\\ E(\Delta w/w)=r\Delta t+a\beta_w\Delta t.\end{matrix}$

Multiplying equation (17) by _w_, and substituting for _βw_ from equation (15), we find:

$E(\Delta w)=mw\Delta t+axw_1\beta_x\Delta t.$

Using stochastic calculus,  10 we can expand _Δw_, which is _$w(x + Δx, t + Δt) − w(x, t)$_﻿, as follows:

$\Delta w = w_{1}\Delta x + \frac{1}{2}w_{11}v^{2}x^{2}\Delta t + w_{2}\Delta t.$

Taking the expected value of equation (19), and substituting for _E_(_Δx_) from equation (16), we have:

$E(\Delta w) = \text{rx}w_{1}\Delta t + \text{ax}w_{1}\beta_{x}\Delta t + \frac{1}{2}v^{2}x^{2}w_{11}\Delta t + w_{2}\Delta t.$

Combining equations (18) and (20), we find that the terms involving _a_ and _βx_ cancel, giving:

$w_{2} = \text{rw} - \text{rx}w_{1} - \frac{1}{2}v^{2}x^{2}w_{11}$

Equation (21) is the same as equation (7).

**More Complicated Options**

The valuation formula (13) was derived under the assumption that the option can only be exercised at time t*. Merton (1973) has shown, however, that the value of the option is always greater than the value it would have if it were exercised immediately (x — c). Thus, a rational investor will not exercise a call option before maturity, and the value of an American call option is the same as the value of a European call option.

There is a simple modification of the formula that will make it applicable to European put options (options to sell) as well as call options (options to buy). Writing u(x,t) for the value of a put option, we see that the differential equation remains unchanged.

$u_{2} = \text{ru} - \text{rx}u_{1} - \frac{1}{2}v^{2}x^{2}u_{11}$

The boundary condition, however, becomes:

$\begin{matrix} u\left(x,t^{*} \right) & \ = 0, & & x \geqslant c \\ & \ = c - x, & & x < c. \\ \end{matrix}$

To get the solution to this equation with the new boundary condition, we can simply note that the difference between the value of a call and the value of a put on the same stock, if both can be exercised only at maturity, must obey the same differential equation, but with the following boundary condition:

$w(x,t*) − u(x,t*) = x − c.$

The solution to the differential equation with this boundary condition is:

$w(x, t) − u(x, t) = x − cer(t−*t**).$

Thus the value of the European put option is:

$u(x, t) = w(x, t) − x + cer(t−*t**).$

Putting in the value of _w_(_x_, _t_) from (13), and noting that$1 − N(d)$﻿ is equal to _$N( − d)$_﻿, we have:

$u(x, t) =  − xN(−d1) + ce − rtN(−d*2). (27)$

In equation (27), dl and d2 are defined as in equation (13).

Equation (25) also gives us a relation between the value of a European call and the value of a European put. ll We see that if an investor were to buy a call and sell a put, his returns would be exactly the same as if he bought the stock on margin, borrowing toward the price of the stock.

Merton (1973) has also shown that the value of an American put option will be greater than the value of a European put option. This is true because it is sometimes advantageous to exercise a put option before maturity, if it is possible to do so. For example, suppose the stock price falls almost to zero and that the probability that the price will exceed the exercise price before the option expires is negligible. Then it will pay to exercise the option immediately, so that the exercise price will be received sooner rather than later. The investor thus gains the interest on the exercise price for the period up to the time he would otherwise have exercised it. So far, no one has been able to obtain a formula for the value of an American put option.

11 The relation between the value of a call option and the value of a put option was first noted by Stoll (1969). He does not realize, however, that his analysis applies only to European options.

If we relax the assumption that the stock pays no dividend, we begin to get into some complicated problems. First of all, under certain conditions it will pay to exercise an American call option before maturity. Merton (1973) has shown that this can be true only just before the stock's ex-dividend date. Also, it is not clear what adjustment might be made in the terms of the option to protect the option holder against a loss due to a large dividend on the stock and to ensure that the value of the option will be the same as if the stock paid no dividend. Currently, the exercise price of a call option is generally reduced by the amount of any dividend paid on the stock. We can see that this is not adequate protection by imagining that the stock is that of a holding company and that it pays out all of its assets in the form of a dividend to its shareholders. This will reduce the price of the stock and the value of the option to zero, no matter what adjustment is made in the exercise price of the option. In fact, this example shows that there may not be any adjustment in the terms of the option that will give adequate protection against a large dividend. In this case, the option value is going to be zero after the distribution, no matter what its terms are. Merton (1973) was the first to point out that the current adjustment for dividends is not adequate.

**Warrant Valuation**

A warrant is an option that is a liability of a corporation. The holder of a warrant has the right to buy the corporation's stock (or other assets) on specified terms. The analysis of warrants is often much more complicated than the analysis of simple options, because:

1. The life of a warrant is typically measured in years, rather than months. Over a period of years, the variance rate of the return on the stock may be expected to change substantially.
2. The exercise price of the warrant is usually not adjusted at all for dividends. The possibility that dividends will be paid requires a modification of the valuation formula.
3. The exercise price of a warrant sometimes changes on specified dates. It may pay to exercise a warrant just before its exercise price changes. This too requires a modification of the valuation formula.
4. If the company is involved in a merger, the adjustment that is made in the terms of the warrant may change its value.
5. Sometimes the exercise price can be paid using bonds of the corporation at face value, even though they may at the time be selling at a discount. This complicates the analysis and means that early exercise may sometimes be desirable.
6. The exercise of a large number of warrants may sometimes result in a significant increase in the number of common shares outstanding.

In some cases, these complications can be treated as insignificant, and equation (13) can be used as an approximation to give an estimate of the warrant value. In other cases, some simple modifications of equation (13) will improve the approximation. Suppose, for example, that there are warrants outstanding, which, if exercised, would double the number of shares of the company's common stock. Let us define the "equity" of the company as the sum of the value of all of its warrants and the value of all of its common stock. If the warrants are exercised at maturity, the equity of the company will increase by the aggregate amount of money paid in by the warrant holders when they exercise. The warrant holders will then own half of the new equity of the company, which is equal to the old equity plus the exercise money.

Thus, at maturity, the warrant holders will either receive nothing, or half of the new equity, minus the exercise money. Thus, they will receive nothing or half of the difference between the old equity and half the exercise money. We can look at the warrants as options to buy shares in the equity rather than shares of common stock, at half the stated exercise price rather than at the full exercise price. The value of a share in the equity is defined as the sum of the value of the warrants and the value of the common stock, divided by twice the number of outstanding shares of common stock. If we take this point of view, then we will take v 2 in equation (13) to be the variance rate of the return on the company's equity, rather than the variance rate of the return on the company's common stock.

A similar modification in the parameters of equation (13) can be made if the number of shares of stock outstanding after exercise of the warrants will be other than twice the number of shares outstanding before exercise of the warrants.

**Common Stock and Bond Valuation**

It is not generally realized that corporate liabilities other than warrants may be viewed as options. Consider, for example, a company that has common stock and bonds outstanding and whose only asset is shares of common stock of a second company. Suppose that the bonds are "pure discount bonds" with no coupon, giving the holder the right to a fixed sum of money, if the corporation can pay it, with a maturity of 10 years. Suppose that the bonds contain no restrictions on the company except a restriction that the company cannot pay any dividends until after the bonds are paid off. Finally, suppose that the company plans to sell all the stock it holds at the end of 10 years, pay off the bond holders if possible, and pay any remaining money to the stockholders as a liquidating dividend.

Under these conditions, it is clear that the stockholders have the equivalent of an option on their company's assets. In effect, the bond holders own the company's assets, but they have given options to the stockholders to buy the assets back. The value of the common stock at the end of 10 years will be the value of the company's assets minus the face value of the bonds, or zero, whichever is greater.

Thus, the value of the common stock will be$w(x,t)$﻿, as given by equation (13), where we take v 2 to be the variance rate of the return on the shares held by the company, c to be the total face value of the outstanding bonds, and x to be the total value of the shares held by the company. The value of the bonds will simply be$x — w(x,t)$﻿.

By subtracting the value of the bonds given by this formula from the value they would have if there were no default risk, we can figure the discount that should be applied to the bonds due to the existence of default risk.

Suppose, more generally, that the corporation holds business assets rather than financial assets. Suppose that at the end of the 10 year period, it will recapitalize by selling an entirely new class of common stock, using the proceeds to pay off the bond holders, and paying any money that is left to the old stockholders to retire their stock. In the absence of taxes, it is clear that the value of the corporation can be taken to be the sum of the total value of the debt and the total value of the common stock. 12 The amount of debt outstanding will not affect the total value of the corporation, but will affect the division of that value between the bonds and the stock. The formula for w(x,t) will again describe the total value of the common stock, where x is taken to be the sum of the value of the bonds and the value of the stock. The formula for x — w(x,t) will again describe the total value of the bonds. It can be shown that, as the face value c of the bonds increases, the market value x — w(x,t) increases by a smaller percentage. An increase in the corporation's debt, keeping the total value of the corporation constant, will increase the probability of default and will thus reduce the market value of one of the corporation's bonds. If the company changes its capital structure by issuing more bonds and using the proceeds to retire common stock, it will hurt the existing bond holders, and help the existing stockholders. The bond price will fall, and the stock price will rise. In this sense, changes in the capital structure of a firm may affect the price of its common stock. 4 The price changes will occur when the change in the capital structure becomes certain, not when the actual change takes place.

Because of this possibility, the bond indenture may prohibit the sale of additional debt of the same or higher priority in the event that the firm is recapitalized. If the corporation issues new bonds that are subordinated

12 The fact that the total value of a corporation is not affected by its capital structure, in the absence of taxes and other imperfections, was first shown by Modigliani and Miller (1958).

to the existing bonds and uses the proceeds to retire common stock, the price of the existing bonds and the common stock price will be unaffected. Similarly, if the company issues new common stock and uses the proceeds to retire completely the most junior outstanding issue of bonds, neither the common stock price nor the price of any other issue of bonds will be affected.

The corporation's dividend policy will also affect the division of its total value between the bonds and the stock. 14 To take an extreme example, suppose again that the corporation's only assets are the shares of another company, and suppose that it sells all these shares and uses the proceeds to pay a dividend to its common stockholders. Then the value of the firm will go to zero, and the value of the bonds will go to zero. The common stockholders will have "stolen" the company out from under the bond holders. Even for dividends of modest size, a higher dividend always favors the stockholders at the expense of the bond holders. A liberalization of dividend policy will increase the common stock price and decrease the bond price. 5 Because of this possibility, bond indentures contain restrictions on dividend policy, and the common stockholders have an incentive to pay themselves the largest dividend allowed by the terms of the bond indenture. However, it should be noted that the size of the effect of changing dividend policy will normally be very small.

If the company has coupon bonds rather than pure discount bonds outstanding, then we can view the common stock as a "compound option." The common stock is an option on an option on an option on the firm. After making the last interest payment, the stockholders have an option

14 Miller and Modigliani (1961) show that the total value of a firm, in the absence of taxes and other imperfections, is not affected by its dividend policy. They also note that the price of the common stock and the value of the bonds will not be affected by a change in dividend policy if the funds for a higher dividend are raised by issuing common stock or if the money released by a lower dividend is used to repurchase common stock.

to buy the company from the bond holders for the face value of the bonds. Call this "option 1." After making the next-to-the-last interest payment, but before making the last interest payment, the stockholders have an option to buy option 1 by making the last interest payment. Call this ' 'option 2." Before making the next-to-the-last interest payment, the stockholders have an option to buy option 2 by making that interest payment. This is "option 3." The value of the stockholders' claim at any point in time is equal to the value of option n + 1, where n is the number of interest payments remaining in the life of the bond.

If payments to a sinking fund are required along with interest payments, then a similar analysis can be made. In this case, there is no "balloon payment" at the end of the life of the bond. The sinking fund will have a final value equal to the face value of the bond. Option 1 gives the stockholders the right to buy the company from the bond holders by making the last sinking fund and interest payment. Option 2 gives the stockholders the right to buy option 1 by making the next-to-the-last sinking fund and interest payment. And the value of the stockholders' claim at any point in time is equal to the value of option n, where n is the number of sinking fund and interest payments remaining in the life of the bond. It is clear that the value of a bond for which sinking fund payments are required is greater than the value of a bond for which they are not required.

If the company has callable bonds, then the stockholders have more than one option. They can buy the next option by making the next interest or sinking fund and interest payment, or they can exercise their option to retire the bonds before maturity at prices specified by the terms of the call feature. Under our assumption of a constant short-term interest rate, the bonds would never sell above face value, and the usual kind of call option would never be exercised. Under more general assumptions, however, the call feature would have value to the stockholders and would have to be taken into account in deciding how the value of the company is divided between the stockholders and the bond holders.

Similarly, if the bonds are convertible, we simply add another option to the package. It is an option that the bond holders have to buy part of the company from the stockholders.

Unfortunately, these more complicated options cannot be handled by using the valuation formula (13). The valuation formula assumes that the variance rate of the return on the optioned asset is constant. But the variance of the return on an option is certainly not constant: it depends on the price of the stock and the maturity of the option. Thus the formula cannot be used, even as an approximation, to give the value of an option on an option. It is possible, however, that an analysis in the same spirit as the one that led to equation (13) would allow at least a numerical solution to the valuation of certain more complicated options.