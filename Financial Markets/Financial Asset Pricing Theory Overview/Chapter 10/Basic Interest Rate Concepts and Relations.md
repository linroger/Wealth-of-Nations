---
tags:
  - compounding
  - forward_rates
  - interest_rates
  - yield_curve
  - zero_coupon_bonds
aliases:
  - Bond Pricing
  - Discount Function
  - Interest Rate Basics
  - Spot Rates
key_concepts:
  - Coupon bond valuation
  - Discount function
  - Interest rate compounding
  - Spot and forward rates
  - Zero-coupon bond pricing
---

# 10.2 Basic interest rate concepts and relations  

As in earlier chapters we will denote by. $B_{t}^{T}$ the price at time $t$ of a zero-coupon bond paying a dividend of one at time. $T$ and no other dividends. If many zero-coupon bonds with different. maturities are traded, we can form the function. $T\mapsto B_{t}^{T}$ , which we refer to as the discount. function prevailing at time $t$ .Of course, we must have $B_{t}^{t}=1$ , and we expect the discount function to be decreasing since all individuals will presumably prefer getting the dividend sooner than later.  

Next, consider a coupon bond with payment dates $t_{1},t_{2},\ldots,t_{n}$ , where we assume without loss of generality that $t_{1}<t_{2}<\cdots<t_{n}$ . The payment at date $t_{i}$ is denoted by $Y_{i}$ . Such a coupon bond can be seen as a portfolio of zero-coupon bonds, namely a portfolio of $Y_{1}$ zero-coupon bonds maturing at $t_{1}$ $Y_{2}$ zero-coupon bonds maturing at $t_{2}$ , etc. If all these zero-coupon bonds are traded in the market, the unique no-arbitrage price of the coupon bond at any time $t$ is  

$$
B_{t}=\sum_{t_{i}>t}Y_{i}B_{t}^{t_{i}}.
$$  

where the sum is over all future payment dates of the coupon bond. If not all the relevant zerocoupon bonds are traded, we cannot justify the relation (10.1) as a result of the no-arbitrage principle. Still, it is a valuable relation. Suppose that an investor has determined (from private or macro economic information) a discount function showing the value she attributes to payments at different future points in time. Then she can value all sure cash fows in a consistent way by substituting that discount function into (10.1).  

The information incorporated in prices of the many different bonds is usually better understood. when transforming the bond prices into interest rates. Interest rates are always quoted on an annual basis, i.e. as some percentage per year. However, to apply and assess the magnitude of an interest. rate, we also need to know the compounding frequency of that rate. More frequent compounding of a given interest rate per year results in higher "effective" interest rates. Furthermore, we need. to know at which time the interest rate is set or observed and for which period of time the interest rate applies. Spot rates applies to a period beginning at the time the rate is set, whereas forward. rates applies to a future period of time. The precise definitions follow below..  

# Annual compounding  

Given the price. $B_{t}^{T^{\prime}}$ at time $t$ on a zero-coupon bond maturing at time. $T$ , the relevant discount rate between time $t$ and time $T$ is the yield on the zero-coupon bond, the so-called zero-coupon rate or spot rate for date. $T$ . That $\hat{y}_{t}^{T}$ is the annually compounded zero-coupon rate means that.  

$$
B_{t}^{T}=\big(1+\hat{y}_{t}^{T}\big)^{-(T-t)}\qquad\Leftrightarrow\qquad\hat{y}_{t}^{T}=\big(B_{t}^{T}\big)^{-1/(T-t)}-1.
$$  

The zero-coupon rates as a function of maturity is called the zero-coupon yield curve or simply the yield curve. It is one way to express the term structure of interest rates..  

While a zero-coupon or spot rate reflects the price on a loan between today and a given future date, a forward rate reflects the price on a loan between two future dates. The annually compounded relevant forward rate at time $t$ for the period between time $T$ and time $S$ is denoted by. $\hat{f}_{t}^{T,S}$ . Here, we have $t\le T<S$ . This is the rate, which is appropriate at time $t$ for discounting between time $T$ and $S$ . We can think of discounting from time $S$ back to time $t$ by first discounting from time $S$ to time $T$ and then discounting from time $T$ to time $t$ . We must therefore have that  

$$
\big(1+\hat{y}_{t}^{S}\big)^{-(S-t)}=\big(1+\hat{y}_{t}^{T}\big)^{-(T-t)}\Big(1+\hat{f}_{t}^{T,S}\Big)^{-(S-T)},
$$  

from which we find that  

$$
\hat{f}_{t}^{T,S}=\frac{(1+\hat{y}_{t}^{T})^{-(T-t)/(S-T)}}{(1+\hat{y}_{t}^{S})^{-(S-t)/(S-T)}}-1.
$$  

We can also link forward rates to bond prices:  

$$
B_{t}^{S}=B_{t}^{T}\left(1+\hat{f}_{t}^{T,S}\right)^{-(S-T)}\qquad\Leftrightarrow\qquad\hat{f}_{t}^{T,S}=\left(\frac{B_{t}^{T}}{B_{t}^{S}}\right)^{1/(S-T)}-1.
$$  

Note that since $B_{t}^{t}=1$ , we have.  

$$
\hat{f}_{t}^{t,S}=\left(\frac{B_{t}^{t}}{B_{t}^{S}}\right)^{1/(S-t)}-1=\left(B_{t}^{S}\right)^{-1/(S-t)}-1=\hat{y}_{t}^{S},
$$  

i.e. the forward rate for a period starting today equals the zero-coupon rate or spot rate for the same period.  

# Compounding over other discrete periods - LIBOR rates  

In practice, many interest rates are quoted using semi-annually, quarterly, or monthly compounding. An interest rate of $R$ per year compounded $m$ times a year, corresponds to a discount factor of $(1+R/m)^{-m}$ over a year. The annually compounded interest rate that corresponds to an interest rate of $R$ compounded $m$ times a year is $(1+R/m)^{m}-1$ . This is sometimes called the "effective" interest rate corresponding to the nominal interest rate $R$ . Interest rates are set for loans with various maturities and currencies at the international money markets, the most commonly used being the LIBOR rates that are fixed in London. Traditionally, these rates are quoted using a compounding period equal to the maturity of the interest rate. If, for example, the three-month interest rate is $l_{t}^{t+0.25}$ per year, it means that  

$$
B_{t}^{t+0.25}=\frac{1}{1+0.25l_{t}^{t+0.25}}\qquad\Leftrightarrow\qquadl_{t}^{t+0.25}=\frac{1}{0.25}\left(\frac{1}{B_{t}^{t+0.25}}-1\right).
$$  

More generally, the relations are  

$$
B_{t}^{T}=\frac{1}{1+l_{t}^{T}(T-t)}\qquad\Leftrightarrow\qquadl_{t}^{T}=\frac{1}{T-t}\left(\frac{1}{B_{t}^{T}}-1\right).
$$  

Similarly, discretely compounded forward rates can be computed as  

$$
L_{t}^{T,S}=\frac{1}{S-T}\left(\frac{B_{t}^{T}}{B_{t}^{S}}-1\right).
$$  

# Continuous compounding  

Increasing the compounding frequency $m$ , the effective annual return on one dollar invested at the interest rate $R$ per year increases to $e^{R}$ , due to the mathematical result saying that  

$$
\operatorname*{lim}_{m\rightarrow\infty}\left(1+\frac{R}{m}\right)^{m}=e^{R}.
$$  

A continuously compounded interest rate $R$ is equivalent to an annually compounded interest rate of $e^{R}-1$ (which is bigger than. $R$ ). Similarly, the zero-coupon bond price. $B_{t}^{T^{\prime}}$ is related to the. continuously compounded zero-coupon rate $y_{t}^{T}$ by  

$$
B_{t}^{T}=e^{-y_{t}^{T}(T-t)}\qquad\Leftrightarrow\qquady_{t}^{T}=-\frac{1}{T-t}\ln B_{t}^{T}.
$$  

The function $T\mapsto y_{t}^{T}$ is also a zero-coupon yield curve that contains exactly the same information as the discount function $T\mapsto B_{t}^{T}$ and also the same information as the annually compounded yield curve $T\mapsto\hat{y}_{t}^{\prime}$ . The relation is $y_{t}^{T^{\prime}}=\ln(1+\hat{y}_{t}^{T^{\prime}})$  

If $f_{t}^{T,S}$ denotes the continuously compounded forward rate prevailing at time $t$ for the periode between $T$ and $S$ , we must have thate $B_{t}^{S}=B_{t}^{T}e^{-\boldsymbol{f}_{t}^{T,S}(S-T)}$ , in analogy with (10.4). Consequently,  

$$
f_{t}^{T,S}=-\frac{\ln B_{t}^{S}-\ln B_{t}^{T}}{S-T}
$$  

and hence  

$$
f_{t}^{T,S}=\frac{y_{t}^{S}(S-t)-y_{t}^{T}(T-t)}{S-T}.
$$  

Analytical studies of the term structure of interest rates often focus on forward rates for future periods of infinitesimal length. The forward rate for an infinitesimal period starting at time. $T$ is simply referred to as the forward rate for time $T$ and is defined as $f_{t}^{T}=\operatorname*{lim}_{S\rightarrow T}f_{t}^{T,S}$ . The function $T\mapsto f_{t}^{T}$ is called the term structure of forward rates. Assuming differentiability of. the discount function, we get  

$$
f_{t}^{T}=-\frac{\partial\ln B_{t}^{T}}{\partial T}=-\frac{\partial B_{t}^{T}/\partial T}{B_{t}^{T}}\qquad\Leftrightarrow\qquadB_{t}^{T}=e^{-\int_{t}^{T}f_{t}^{u}d u}.
$$  

Applying (10.9), the relation between the infinitesimal forward rate and the spot rates can be written ac  

$$
f_{t}^{T}=\frac{\partial[y_{t}^{T}(T-t)]}{\partial T}=y_{t}^{T}+\frac{\partial y_{t}^{T}}{\partial T}(T-t)
$$  

under the assumption of a differentiable term structure of spot rates $T\mapsto y_{t}^{T}$ . The forward rate reflects the slope of the zero-coupon yield curve. In particular, the forward rate $f_{t}^{T}$ and the zerocoupon rate $y_{t}^{T}$ will coincide if and only if the zero-coupon yield curve has a horizontal tangent at $T$ . Conversely,  

$$
y_{t}^{T}=\frac{1}{T-t}\int_{t}^{T}f_{t}^{u}d u,
$$  

i.e. the zero-coupon rate is an average of the forward rates.  

It is important to realize that discount factors, spot rates, and forward rates (with any compounding frequency) are perfectly equivalent ways of expressing the same information. If a complete yield curve of, say, quarterly compounded spot rates is given, we can compute the discount function and spot rates and forward rates for any given period and with any given compounding frequency. If a complete term structure of forward rates is known, we can compute discount functions and spot rates, etc. Academics frequently apply continuous compounding since the mathematics involved in many relevant computations is more elegant when exponentials are used.  

There are even more ways of representing the term structure of interest rates. Since most bonds are bullet bonds, many traders and analysts are used to thinking in terms of yields of bullet bonds rather than in terms of discount factors or zero-coupon rates. The par yield for a given maturity is the coupon rate that causes a bullet bond of the given maturity to have a price equal to its face value. Again we have to fix the coupon period of the bond. U.S. treasury bonds typically have semi-annual coupons which are therefore often used when computing par yields. Given a discount function $T\mapsto B_{t}^{T}$ , the $n$ -year par yield is the value of $c$ satisfying  

$$
\sum_{i=1}^{2n}\left(\frac{c}{2}\right)B_{t}^{t+0.5i}+B_{t}^{t+n}=1\Rightarrow\quad c=\frac{2\left(1-B_{t}^{t+n}\right)}{\sum_{i=1}^{2n}B_{t}^{t+0.5i}}.
$$  

It reflects the current market interest rate for an $n$ -year bullet bond. The par yield is closely related to the so-called swap rate, which is a key concept in the swap markets.  
