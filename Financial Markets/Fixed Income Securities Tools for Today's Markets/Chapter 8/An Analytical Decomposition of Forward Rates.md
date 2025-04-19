---
tags:
  - bond_pricing
  - convexity
  - duration
  - forward_rates
  - risk_premium
aliases:
  - Bond Return Decomposition
  - Forward Rate Decomposition
key_concepts:
  - Bond price and rate
  - Duration and convexity
  - Expected bond returns
  - Forward rate decomposition
  - Risk-neutral investors
---

# 8.3 AN ANALYTICAL DECOMPOSITION OF FORWARD RATES  

This section derives a general decomposition of forward rates in terms of. expectations, convexity, and risk premium. The level of mathematics here is higher than used in most of the book, but the discussion still aims at intuition.  

Assume that all bond prices are determined by the instantaneous rate, $r$ which takes on the value of. $r_{t}$ at time $t$ . Let $P_{t}(r_{t},T)$ be the price of a $T$ year zero coupon bond at time. $t$ . By Ito's lemma, a discussion of which is beyond. the scope of this book,  

$$
d P={\frac{\partial P}{\partial r}}d r+{\frac{\partial P}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}P}{\partial r^{2}}}\sigma^{2}d t
$$  

where $d P,d r$ and $d t$ are the changes in price, rate, and time over the next instant, respectively, and $\sigma$ is the volatility of changes in $r$ . The two first-order. partial derivatives in Equation (8.9) denote the instantaneous change in the bond price for a unit change in the rate (with time unchanged) and for a unit change in time (with rate unchanged), respectively. Finally, the second order partial derivative in the equation gives the instantaneous change in $\partial P/\partial r$ (with time unchanged). Dividing both sides of (8.9) by price,  

$$
{\frac{d P}{P}}={\frac{1}{P}}{\frac{\partial P}{\partial r}}d r+{\frac{1}{P}}{\frac{\partial P}{\partial t}}d t+{\frac{1}{2}}{\frac{1}{P}}{\frac{\partial^{2}P}{\partial r^{2}}}\sigma^{2}d t
$$  

Equation (8.10) breaks down the instantaneous return on the zero. coupon bond into three components, but this decomposition can be written more intuitively by invoking several ideas from earlier chapters..  

First, in terms of instantaneous compounded forward rates, $f(t)$ , the price of a $T$ -year zero coupon bond is (from Section A2.1),  

$$
P=e^{-\int_{0}^{T}f(s)d s}
$$  

Then, differentiating both sides of (8.11) with respect to $t$ , recognizing that increasing $t$ decreases $T$ one-for-one,  

$$
{\frac{\partial P}{\partial t}}=-{\frac{\partial P}{\partial T}}=f(T)P
$$  

Second, by the definitions of duration, $D$ , and convexity, C,  

$$
\begin{array}{l}{{\displaystyle{\cal D}\equiv-\frac{1}{{\cal P}}\frac{\partial{\cal P}}{\partial r}}~}\ {{\displaystyle~C\equiv\frac{1}{{\cal P}}\frac{\partial^{2}{\cal P}}{\partial r^{2}}}}\end{array}
$$  

Now, substituting Equations (8.12) through (8.14) into the return decomposition (8.10),  

$$
\frac{\partial P}{P}=f(T)d t-D d r+\frac{1}{2}C\sigma^{2}d t
$$  

Equation (8.15) gives the return decomposition in terms of the following three components. The first is the return due to the passage of time, which, in this case, is the forward rate, $f(T)$ .1 The second and third components are returns due to changes in the rate. The second term says that increases in rate. reduce bond return in proportion to duration. The third term says that the volatility of rates - movement of rates either up or down - increases return in proportion to convexity. To appreciate this term, recall from Chapter 4 that,. across portfolios with the same duration, more convex portfolios increase. more in value as rates change (at a fixed moment in time), whether rates rise. or fall.  

To draw conclusions about expected returns, take the expectation of both sides of (8.15),  

$$
E\left[\frac{\partial P}{P}\right]=f(T)d t-D E[d r]+\frac{1}{2}C\sigma^{2}d t
$$  

The intuition of this decomposition is the same as for Equation (8.15), but with the duration component depending not on the change in rate but on the expected change in rate.  

The next step in the analysis introduces the concept of a risk premium. Risk-neutral investors, who do not require a risk premium, demand that each bond offer an expected return equal to the short-term rate of interest. Mathematically,  

$$
E\left[{\frac{d P}{P}}\right]=r_{0}d t
$$  

Risk averse investors, however, demand higher expected returns for bonds with greater interest rate risk. The appendix to this chapter shows that the interest rate risk of a bond over the next instant may be measured by its duration with respect to the interest rate factor, and that risk-averse investors demand a risk premium proportional to duration. This risk premium may depend on time and on the level of rates, but not on the characteristics of any individual bond. The discussion proceeds here, however, as if the risk premium were constant and denoted by $\lambda$ . In that case, the expected return equation for risk-averse investors is,  

$$
E\left[{\frac{d P}{P}}\right]=r_{0}d t+\lambda D d t
$$  

Say, for example, that the short-term rate is $1\%$ , that the duration of a bond is five, and that the risk premium is 10 basis points per year of duration risk. Then, according to Equation (8.18), the bond's expected return is $1\%+$ $5\times0.1\%=1.5\%$ per year.  

Another useful way to think of the risk premium is in terms of the Sharpe ratio (SR) of a security, defined as its expected excess return (over the short-term rate) divided by the standard deviation of its return. Because the random part of a bond's return comes from its duration times the change in rate, as in Equation (8.15), the standard deviation of the return equals the duration times the standard deviation of rates. Therefore, the SR of a bond may be written as,  

$$
S R={\frac{E[d P/P]-r_{0}d t}{\sigma D d t}}={\frac{\lambda}{\sigma}}
$$  

where the second equality follows from Equation (8.18). For example, if the risk premium is 10 basis points per year, and if the standard deviation of. rates is 100 basis points per year, then the Sharpe ratio of bond investments is $10\%$  

The decomposition of returns can now be combined with the economics. of the risk premium to draw conclusions about the shape of the term structure of forward rates. Equating the expressions for expected returns in the right-hand sides of Equations (8.16) and (8.18),.  

$$
f(T)=\left\{r_{0}+E\left[\frac{d r}{d t}\right]D\right\}+\lambda D-\frac{1}{2}C\sigma^{2}
$$  

Equation (8.20) mathematically describes the determinants of forward rates. The three terms represent the impacts of expectations, risk premium,. and convexity, respectively. The first term says that the forward rate is composed of the instantaneous interest rate plus the expected change in that rate times the duration of the zero coupon bond corresponding to the term of the forward rate. In other words, the higher the instantaneous rate, the higher the forward rate; the more rates are expected to increase, the higher the forward rate; and the greater the corresponding duration, the greater the effect of expected rate changes on the forward rate..  

The second term on the right-hand side of (8.20) says that the forward. rate increases with the risk premium in proportion to the corresponding duration. In other words, the greater the corresponding interest rate risk and the greater the risk premium, the greater the forward rate.  

Chapter 7 noted that a drift in the short-term rate of a certain number. of basis points has the same effect on bond pricing as a risk premium of that number of basis points per year of duration risk. Equation (8.20) formal-. izes this statement. Increasing the risk premium or increasing the expected short-term rate by the same amount are indistinguishable from the observation of forward rates. This means that the term structure of interest rates. cannot, on its own, be used to separate expectations of rate changes from risk premium. From a modeling perspective, this means that only the risk-neutral process is relevant for pricing. Dividing the risk-neutral drift into expecta-. tions and risk premium might be very useful for economic perspectives and. for macro-style trading (see Chapter 9), but this division is not observable from a cross section of bond prices alone..  

The first two terms of Equation (8.20) can also be cast in terms of theories of the term structure of interest rates. (Put aside the convexity term for the moment.) Under the pure expectations hypothesis, the risk premium, $\lambda$ , is zero, and the term structure of forward rates is determined by expectations, $E[d r/d t]$ . In this view of the world, the most natural "no-change" scenario,. in the terms of Chapter 3, is that short-term rates evolve as expected and that forward rates are realized. At the opposite extreme, under the pure risk premium hypothesis, the market has no expectations about rates, that is, $E[d r/d t]=0$ , and the term structure of forward rates is determined by the risk premium. In this view of the world, the most natural "no-change" scenario is that short-term rates stay the same, as expected, which, in terms of Chapter 3 is an unchanged term structure. The reality, of course, can be between the two extremes, such the the term structure is determined by a mix of expectations and risk premium..  

To conclude the discussion of Equation (8.20), the third term shows that the forward rate is reduced because of volatility and the convexity of. the zero corresponding to the term of the forward rate by. $0.5C\sigma^{2}$ . Using this to reinterpret Equation (8.16), the indirect reduction in return through the forward rate, because of convexity, is exactly offset by the direct increase in return, because of convexity. Put another way, the expected return condition of Equation (8.18) ensures that there is no net advantage of convexity. The significance of this reasoning for investment and hedging decisions is intro-. duced in Chapter 4 in the context of establishing long- and short-convexity. positions.  

# The Vasicek and Gauss+ Models  

well-known Vasicek and Gauss+ models. The Vasicek model started the literature on short-term rate models;' remains an extremely good starting point for learning about these models; and can still be used in some applied contexts. The $\mathrm{Gauss+}$ model has proven very popular for proprietary trading, for both relative value and macro-style trading. The presentation of this model here is directed toward determined readers who would like to implement a term structure model for their own trading purposes.  
