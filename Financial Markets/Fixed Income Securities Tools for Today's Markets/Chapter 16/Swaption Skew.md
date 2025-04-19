---
tags:
  - bsm_model
  - forward_rate
  - implied_volatility
  - swaption_skew
  - volatility_smile
aliases:
  - Swaption Volatility
  - Volatility Skew
key_concepts:
  - At-the-money options
  - BSM delta
  - BSM normal model
  - Implied volatility varies
  - Volatility skew
---

# 16.6 SWAPTION SKEW  

The BSM normal model, as applied in the previous section, has a single. and constant volatility parameter. Taking the model literally, this would. imply that all swaptions can be priced with a single basis-point volatility. Figure 16.2 illustrates, however, that this is not the case: even across swap-. tions with the same expiration and underlying tenor, like either the 2y2y. and 5y10y swaptions in the figure, implied volatilities vary significantly with. strike. As of the pricing date, the two-year swap rate, two years forward is $1.11\%$ (not shown in the figure), which is the ATM strike for 2y2y swap-. tions. The darker gray curve shows, therefore, that 2y2y implied volatilities. increase mostly linearly from 56 basis points at a strike of. $0.11\%$ , which is 100 basis points below the ATM strike, to 125 basis points at a strike of $4.11\%$ , which is 300 basis points above the ATM strike. At the same time, the 10-year swap rate, five years forward is. $2.43\%$ . The lighter gray curve of the figure shows, therefore, that implied volatilities of 5y10y swaptions are roughly 75 basis points for strikes below that ATM strike, and then increase along the curve shown to 95 basis points at a strike 300 basis points over the ATM strike. The phenomenon that basis-point volatility is not constant across strikes is known as the volatility skew. The phenomenon that basis-point volatility is higher for both in- and out-of-the-money options than for at-the-money options, as seen here for 5y10y swaptions, is known as the smile, or, to the extent this effect is not symmetric, the smirk.  

![](a1eee1f5c7f6bdfa9e5ab0967f2a404eb8e2ddea36364bb49e87e49329699e79.jpg)  
FIGURE 16.2  Implied Basis-Point Volatilities of 2y2y and 5y10y US Dollar Swaptions Across Strikes, as of May 14, 2021..  

The existence of a skew does not prevent traders from quoting swap-. tion prices in terms of normal BSM volatility or vice versa, so long as the volatilities vary with strike. But practitioners rely on BSM not just to quote a price or volatility, but also to compute delta, that is, to compute how the value of a swaption changes as its underlying forward rate changes. And the usefulness of BSM for this purpose is cast into doubt by Figure 16.2. Without getting into great detail here, the implied volatility of an option at. a given strike can be thought of as the expected gamma-weighted average of instantaneous volatilities over possible paths of the underlying forward rate as it changes from its current level to the strike. From this perspective, the implied volatility curves in Figure 16.2 mean that instantaneous volatilities vary in a complex way with the level the forward rate. In that case, however, the value of an option changes with the level of rates in two ways: a direct effect, that is, the change in the underlying forward; and an indirect effect, that is, the change in volatility as a result of the change in the level of rates.  

But the BSM delta, which is traditionally computed as the change in option value for a change in the underlying at a given volatility, captures only the direct effect.  

The search for a model that can capture the underlying dynamics of. volatility as a function of forward rates has taken two very broad paths. The first is to change the distribution of the forward rate away from normal. For example, a constant-volatility lognormal model of rates assumes that volatility is proportional to rates, which might be useful in explaining some manifestations of the skew, like parts of the 2y2y curve in Figure 16.2. In any case, along these lines, the shifted lognormal model allows for the distribution of the underlying forward rate to be between normal and lognormal. The defining dynamics of the forward rate,. $S$ , in this model are,  

$$
\begin{array}{c}{d S_{t}=\phi(S_{t})\sigma\epsilon_{t}\sqrt{d t}}\ {\epsilon_{t}\sim N(0,1)}\ {\phi(S_{t})=a+S_{t}}\end{array}
$$  

with $a\ge0$ . When $a=0$ $\phi(S_{t})=S_{t}$ , the basis-point volatility in Equation. (16.15) is just $\sigma{\cal S}_{t}$ , that is, a constant proportion of the forward rate. There-. fore, the distribution of the rate is lognormal. At the other extreme, as $a$ approaches infinity, $\phi(S_{t})$ in (16.17) approaches the constant $a$ , which means. that the volatility in (16.15) approaches a constant and, therefore, that the distribution approaches normality.  

The second approach to finding a model that captures the relationship. between rates and volatility is to allow volatility itself to be a random variable. This approach leads to stochastic volatility models, in which class the SABR model had proven particularly popular. As originally formulated,. however, the model could not handle the negative rates that recently characterized markets in Europe. An adjusted model then emerged, known as the shifted-SABR model, which assumes the following dynamics,.  

$$
\begin{array}{r l}&{d S_{t}=(S_{t}+b)^{\beta}\sigma_{t}\epsilon_{t}\sqrt{d t}}\ &{\quad\epsilon_{t}\sim N(0,1)}\ &{\quad\quad d\sigma_{t}=\alpha\sigma_{t}\nu_{t}\sqrt{d t}}\ &{\quad\quad\nu_{t}\sim N(0,1)}\ &{\quad\quad E[\epsilon_{t}\nu_{t}]=\rho}\end{array}
$$  

with $b\geq0,0<\beta<1,\alpha\geq0.$ and $0\leq\rho\leq1$ . There are several features to note about this formulation. First, the only difference between this model and the original SABR model is the shift parameter,. $b$ . With this shift, the.  

forward rate $S_{t}$ can be as negative as $-b$ with the basis-point volatility of the. model - $(S_{t}+b)^{\beta}\sigma_{t}$ - still positive. Second, the SABR model approaches the normal model as both $\alpha$ and $\beta$ approach 0, and it approaches the lognormal model as $\alpha$ approaches O and as $\beta$ approaches 1. Third, the initial volatility, $\sigma_{0}$ , is most naturally used to match ATM swaption volatility. Fourth, $\beta$ is typically less than one, because basis-point volatilities, as illustrated in Figures 16.2, do not increase as quickly for high strikes as in a lognormal model. Fifth, the parameters. $\beta$ and $\rho$ control the skew through controlling the relationship between the level of rates and volatility. From Equation (16.18), a higher $\beta$ increases the responsiveness of volatility to the level of the forward rate. And from Equation (16.22), a higher $\rho$ increases the correlation between changes in rates and changes in volatility. Sixth, the parameter $\alpha$ controls the smile, or fat tails of the rates distribution, as a higher $\alpha$ increases volatility when volatility is high, that is, $\alpha$ increases volatility when rates. are either higher or lower. Seventh, in practice, because the flexibility of the model enables many different sets of parameters to fit the observed skew, the parameters can also be constrained to fit empirical regularities. One popular choice, for example, is to constrain the parameters to match the empirical backbone, that is, the empirical relationship between ATM basis-point volatilities and forward rates. Eighth, note that, in practice, a different set of parameters are typically chosen for every swaption expiration and underlying tenor. In other words, no BSM-style model can describe the entire volatility cube.  

# Prices, Discount Factors, and Arbitrage.  

# A1.1 DERIVING REPLICATING PORTFOLIOS  

To replicate the 7.625s of 11/15/2022, Table 1.5 uses the 2.875s of 11/15/2021, the 2.125s of 05/15/2022, and the 1.625s of 11/15/2022. Number these bonds from 1 to 3, and let $F_{i}$ be the face amount of bond $i$ in the replicating portfolio. Then, the following equations express the requirement that the cash flows of the replicating portfolio equal those of the 7.625s on each of the cash flow dates. For the cash flows on November 15, 2021,  

$$
\left(100\%+{\frac{2.875\%}{2}}\right)F_{1}+{\frac{2.125\%}{2}}F_{2}+{\frac{1.625\%}{2}}F_{3}={\frac{7.625\%}{2}}
$$  

For the cash flows on May, 15, 2022,  

$$
0\times F_{1}+\left(100\%+{\frac{2.125\%}{2}}\right)F_{2}+{\frac{1.625\%}{2}}F_{3}={\frac{7.625\%}{2}}
$$  

And for the cash flows on November 15, 2022,  

$$
0\times F_{1}+0\times F_{2}+\left(100\%+{\frac{1.625\%}{2}}\right)F_{3}=100\%+{\frac{7.625\%}{2}}
$$  

Solving equations (A1.1), (A1.2), and (A1.3) for $F_{1},F_{2}$ and $F_{3}$ gives the replicating portfolio's face amounts reported in Table 1.5. Note that, because one bond matures on each date, these equations can be solved one-at-a-time instead of simultaneously.  

Replicating portfolios are easier to describe and manipulate using matrix. algebra. To illustrate, equations (A1.1) through (A1.3) can be written as follows,  

$$
\begin{array}{r}{\left[1+\frac{2.875\%}{2}\frac{2.125\%}{2}\frac{1.625\%}{2}\right]\left[F_{1}\right]=\left[\begin{array}{c}{\frac{7.625\%}{2}}\ {1+\frac{2.125\%}{2}}\ {0}\end{array}\right]\left[\begin{array}{c}{1.625\%}\ {2}\end{array}\right]\left[\begin{array}{c}{1}\ {1}\ {2}\end{array}\right]=\left[\begin{array}{c}{\frac{7.625\%}{2}}\ {\frac{7.625\%}{2}}\ {1+\frac{7.625\%}{2}}\end{array}\right]}\end{array}
$$  

Note that each column of the leftmost matrix describes the cash flows of one of the bonds in the replicating portfolio; the elements of the vector to the right of the matrix gives the face amounts of each bond for which the equation has to be solved; and the rightmost vector gives the cash flows of the bond to be replicated. Equation (A1.4) can easily be solved.  

In general, suppose that the bond to be replicated makes payments on $T$ dates. Let C be the $T\times T$ matrix of cash flows, principal plus interest, with the $T$ columns representing the $T$ bonds in the replicating portfolio and the $T$ rows the dates on which those bonds make payments. Let $\mathbf{f}$ be the $T\times1$ vector of face amounts in the replicating portfolio, and let c be the vector of cash flows, principal plus interest, of the bond to be replicated. Then, the equation to be solved is,.  

$$
\mathbf{Cf}=\mathbf{c}
$$  

with solution,  

$$
\mathbf{f}=\mathbf{C}^{-1}\mathbf{c}
$$  

The only complication in constructing replicating portfolios is to ensure that the matrix C does have an inverse. Essentially, any set of $T$ bonds will do so long as there is at least one bond in the replicating portfolio making a payment on each of the $T$ dates. All $T$ bonds maturing on the last date would work, for example, but all $T$ bonds maturing on the second-to-last date would not. In the latter case, there would be no bond in the replicating portfolio making a payment on date $T$  

# A1.2THE EQUIVALENCE OF DISCOUNTING AND ARBITRAGE PRICING  

Proposition: Pricing a bond according to either of the following methods gives the same price:  

1. Derive a set of discount factors from some set of spanning bonds and price the bond in question using those discount factors..  

2. Find the replicating portfolio of the bond in question using that same set of spanning bonds and calculate the price of the bond as the price of this portfolio.  

Proof: Continue with the notation introduced at the end of Appendix A1.1..   
In addition, let $\mathbf{d}$ be the $T\times1$ vector of discount factors for each date and.   
let p be the vector of prices of each bond in the replicating portfolio, which.   
is the same as the vector of prices used to compute the discount factors. Also note that a set of spanning bonds is such that the matrix C has an inverse.  

Generalizing the derivation of discount factors in this chapter, discount factors can be determined from the following equation,  

$$
\mathbf{d}=\mathbf{C^{'}}_{\textbf{~p}}^{-1}
$$  

where the' denotes the transpose. Then, the price of the bond according to the first method is $c^{\prime}\mathbf{d}$ . The price according to the second method is $\mathbf{p^{\prime}f}$ where f is as derived in Equation (A1.6).  

Hence, the two methods give the same price if,  

$$
c^{\prime}\mathbf{d}=\mathbf{p^{\prime}}\mathbf{f}
$$  

Expanding the left-hand side of Equation (A1.8) with (A1.7) and the right-hand side with (A1.6),  

$$
\mathbf{c}^{\prime}(\mathbf{C}^{\prime})^{-1}\mathbf{p}=\mathbf{p}^{\prime}\mathbf{C}^{-1}\mathbf{c}
$$  

Finally, since both sides of (A1.9) are numbers, take the transpose of the left-hand side to show that the equation is true..  

# Swap, Spot, and Forward Rates  

# A2.1 CONTINUOUS COMPOUNDING  

Equation (2.7) gives the proceeds of investing $F$ for $N$ periods at the rate $\hat{r}$ which is compounded $_n$ times per year. By the definition of $_n$ , there are $n T$ periods over $T$ years. Therefore, with $F=1$ , (2.7) becomes,  

$$
\left(1+{\frac{\hat{r}}{n}}\right)^{n T}
$$  

Under continuous compounding, interest is paid every instant, so that the proceeds of an investment that is continuously compounded over $T$ years grows to the limit of Equation (A2.1) as $_n$ approaches infinity. Taking the logarithm of (A2.1) and rearranging terms,  

$$
n T\ln\left(1+\frac{\hat{r}}{n}\right)=\frac{T\ln(1+\frac{\hat{r}}{n})}{\frac{1}{n}}
$$  

Using l'Hopital's rule, the limit of the right-hand side of (A2.2) as $_n$ becomes large is $\hat{r}T$ . Hence, the limit of (A2.1) is $e^{\hat{r}T}$ , where $e$ is the base of the natural logarithm. Therefore, if interest is continuously compounded at the rate $\hat{\boldsymbol{r}}$ an investment of one unit of currency will grow after $T$ years to,  

$$
e^{\hat{r}T}
$$  

Equivalently, the present value of one unit of currency to be received in $T$ years is,  

$$
e^{-\hat{r}T}
$$  

This section now defines discount factors, spot rates, and forward rates under continuous compounding. Let. $\hat{\boldsymbol{r}}(t)$ be the $t$ -year continuously compounded spot rate. Let $f(t-\Delta,t)$ be the forward rate from $t-\Delta$ to $t.$ , and  

define $f(t)$ to be the continuously compounded forward rate at time $t$ , that is, the limit of $f(t-\Delta,t)$ as $\Delta$ approaches zero.  

By Equation (A2.4), spot rates and discount factors are related such that,  

$$
d(T)=e^{-\hat{r}(T)T}
$$  

Linking forward rates and spot rates is the continuously compounded analog of Equation (2.21),  

$$
\begin{array}{l}{{{e^{{\hat{r}}^{(T)T}}=e^{\int_{0}^{T}f(s)d s}}}}\ {{{\hat{r}}(T)T={\displaystyle\int_{0}^{T}}f(s)d s}}\ {{{\hat{r}}(T)={\displaystyle\frac{1}{T}}\int_{0}^{T}f(s)d s}}\end{array}
$$  

To link forward rates and discount factors, note that the continuously compounded analogue of Equation (2.20) is,  

$$
e^{\hat{r}(t-\Delta)\times(t-\Delta)}e^{f(t-\Delta,t)\Delta}=e^{\hat{r}(t)t}
$$  

Then substitute from Equation (A2.5) for each of the two spot rates and rearrange terms to get,  

$$
e^{f(t-\Delta,t)\times\Delta}=\frac{d(t-\Delta)}{d(t)}
$$  

Then take the natural logarithm of both sides and rearrange terms,  

$$
f(t-\Delta,t)=-\frac{\ln[d(t)]-\ln[d(t-\Delta)]}{\Delta}
$$  

Finally, take the limit of both sides of this equation, recognizing that the limit of the right-hand side is the derivative of $\ln[d(t)]$ , to obtain,  

$$
f(t)=-{\frac{d^{\prime}(t)}{d(t)}}
$$  

where $d^{\prime}(t)$ is the derivative of the discount function with respect to term.  

# A2.2 RELATIONSHIPS BETWEEN SWAP OR PAR, SPOT, AND FORWARD RATES  

This section will work with semiannually compounded rates, though it could easily be cast in terms of other compounding intervals..  

Approximation: The $t$ -year spot rate is approximately equal to the average of all forward rates to year. $t$  

Start from Equation (2.21), noting that, because interest rates them-. selves are small numbers, the product of two or more interest rates is particularly small. To illustrate, take the case of the one-year spot rate, though the argument generalizes easily to longer-term rates,.  

$$
\left(1+{\frac{\hat{r}(1.0)}{2}}\right)^{2}=\left(1+{\frac{f(0.5)}{2}}\right)\left(1+{\frac{f(1)}{2}}\right)
$$  

$$
1+2{\frac{\hat{r}(1.0)}{2}}+\left({\frac{\hat{r}(1.0)}{2}}\right)^{2}=1+{\frac{{\dot{f}}(0.5)}{2}}+{\frac{{\dot{f}}(1.0)}{2}}+{\frac{{\dot{f}}(0.5)}{2}}{\frac{{\dot{f}}(1.0)}{2}}
$$  

$$
\hat{r}(1.0)\approx\frac{f(0.5)+f(1.0)}{2}
$$  

where the approximation from (A2.14) to (A2.15) comes from dropping the terms that multiply two rates.  

# Proposition 1:  

$$
\sum_{t=a}^{b}z^{t}={\frac{z^{a}-z^{b+1}}{1-z}}
$$  

Proof: Define $S$ as the left-hand side of (A2.16). Then,  

$$
z S=\sum_{t=a+1}^{b+1}z^{t}
$$  

and it follows that,  

$$
S-z S=\sum_{t=a}^{b}z^{t}-\sum_{t=a+1}^{b+1}z^{t}
$$  

$$
S(1-z)=z^{a}-z^{b+1}
$$  

$$
S={\frac{z^{a}-z^{b+1}}{1-z}}
$$  

as was to be shown.  

Proposition 2: If the term structure of spot rates is flat, then the term structure of par rates is flat at that same rate.  

Proof: Denote the semiannually compounded par rate of maturity $T$ as $C(T)$ . If spot rates are flat at the rate. $\hat{r}$ , then, by definition of. $C(T)$  

$$
{\frac{{\mathrm{C}}(T)}{2}}\sum_{t=1}^{2T}{\frac{1}{\left(1+{\frac{\hat{r}}{2}}\right)^{t}}}+{\frac{1}{\left(1+{\frac{\hat{r}}{2}}\right)^{2T}}}=1
$$  

Applying Equation (A2.16) of Proposition 1 with $z=1/(1+\hat{r}/2)$  

$$
\frac{{\mathrm C}(T)}{\hat{r}}\left[1-\frac{1}{(1+\frac{\hat{r}}{2})^{2T}}\right]+\frac{1}{\left(1+\frac{\hat{r}}{2}\right)^{2T}}=1
$$  

But solving (A2.18) for. $C(T)$ shows that $C(T)=\hat{r}$ Hence, the term struc-. ture of par rates is flat at $\hat{r}$ , as was to be shown..  

Proposition 3: $f(t)>\hat{r}(t-0.5)$ if and only if $\hat{r}(t)>\hat{r}(t-0.5)$  

Proof: The condition $f(t)>\hat{r}(t-0.5)$ is equivalent to,  

$$
\begin{array}{r l r}{\lefteqn{\left(1+\frac{\hat{r}(t-0.5)}{2}\right)^{2t-1}\left(1+\frac{f(t)}{2}\right)>\left(1+\frac{\hat{r}(t-0.5)}{2}\right)^{2t-1}\left(1+\frac{\hat{r}(t-0.5)}{2}\right)}}\ &{}&{>\left(1+\frac{\hat{r}(t-0.5)}{2}\right)^{2t}(\mathrm{A}2.19)}\end{array}
$$  

But, using Equation (2.20) to rewrite the left-hand side of (A2.19),  

$$
\left(1+\frac{\hat{r}(t)}{2}\right)^{2t}>\left(1+\frac{\hat{r}(t-0.5)}{2}\right)^{2t}
$$  

$$
\hat{r}(t)>\hat{r}(t-0.5)
$$  

as was to be shown.  

Proposition 4: $f(t)<\hat{r}(t-0.5)$ if and only if $\hat{r}(t)<\hat{r}(t-0.5)$  

Proof: Reverse the inequalities in the proof of Proposition 3.  

Proposition 5: If $\hat{r}(0.5)<\hat{r}(1.0)<\cdot\cdot\cdot<\hat{r}(T).$ then $\boldsymbol{\mathrm{{C}}}(T)<\boldsymbol{\hat{r}}(T)$  

Proof: By the definition of the par rate, $C(T)$  

$$
\frac{\operatorname{C}(T)}{2}\sum_{t=1}^{2T}\frac{1}{\left(1+\frac{\hat{r}(t)}{2}\right)^{t}}+\frac{1}{\left(1+\frac{\hat{r(T)}}{2}\right)^{2T}}=1
$$  

It is easy to show from Equation (A2.16), setting $z=1/(1+C(T)/2)$ that,  

$$
\frac{\operatorname{C}(T)}{2}\sum_{t=1}^{2T}\frac{1}{\left(1+\frac{\operatorname{C}(T)}{2}\right)^{t}}+\frac{1}{\left(1+\frac{\operatorname{C}(T)}{2}\right)^{2T}}=1
$$  

And, because the term structure of spot rates is assumed to be increasing,  

$$
\begin{array}{l}{\displaystyle\frac{C(T)}{2}\sum_{t=1}^{2T}\frac{1}{(1+\frac{\hat{r}(t)}{2})^{t}}+\frac{1}{(1+\frac{\hat{r}(T)}{2})^{2T}}>}\ {\displaystyle\frac{C(T)}{2}\sum_{t=1}^{2T}\frac{1}{(1+\frac{\hat{r}(T)}{2})^{t}}+\frac{1}{(1+\frac{\hat{r}(T)}{2})^{2T}}}\end{array}
$$  

Note that the spot rates in the summation on the top line are $\hat{\boldsymbol{r}}(t)$ , while those in the summation in the bottom line are all $\hat{r}(T)$  

Now, because the left-hand sides of Equations (A2.22), (A2.23), and (A2.24) are all equal to one, the left-hand side of (A2.23) can replace the left-hand side of (A2.24), that is,  

$$
\begin{array}{l}{\displaystyle\frac{C(T)}{2}\sum_{t=1}^{2T}\frac{1}{\left(1+\frac{C(T)}{2}\right)^{t}}+\frac{1}{\left(1+\frac{C(T)}{2}\right)^{2T}}>}\ {\displaystyle\frac{C(T)}{2}\sum_{t=1}^{2T}\frac{1}{\left(1+\frac{\hat{r}(T)}{2}\right)^{t}}+\frac{1}{\left(1+\frac{\hat{r}(\hat{T})}{2}\right)^{2T}}}\end{array}
$$  

which implies that $\boldsymbol{\mathrm{C}}(\boldsymbol{T})<\hat{\boldsymbol{r}}(\boldsymbol{T})$ , which was to be proved.  

Proposition 6: If $\hat{r}(0.5)>\hat{r}(1.0)>\cdots>\hat{r}(T),\mathrm{then}~C(T)>\hat{r}(T).$  

Proof: Reverse the inequalities of Equations (A2.24) and (A2.25) in the previous proof to conclude that $C(T)>\hat{r}(T)$ , as was to be proved.  

# Returns, Yields, Spreads, and P&L Attribution  

# A3.1 YIELD TO MATURITY FOR SETTLEMENT DATES OTHER THAN COUPON PAYMENT DATES  

Equations (3.6), (3.7), and (3.8) express the relationship between price and yield to maturity when settlement is on a coupon payment date. This. appendix generalizes this relationship to other settlement dates. First, because accrued interest is zero when settlement falls on a coupon payment. date, the full price in the equations in the text do not include any accrued interest. In this section, however, because settlement can fall on other dates, $P$ is taken to include accrued interest..  

Second, the market convention for discounting cash flows that do not occur in regular six-month intervals, using a semiannually compounded rate, is as follows. Let $y$ denote the semiannually compounded yield, and let $\tau$ denote the fraction of a semiannual period until the next coupon payment. For example, if the next coupon payment is in one month, taken to mean one-sixth of a semiannual period, then $\tau=1/6$ . By convention, then, the present value of a unit of currency at that time is,  

$$
\frac{1}{\left(1+\frac{y}{2}\right)^{\tau}}
$$  

Note that, while reasonably intuitive, this convention cannot really be justified by the logic of compounding conventions. As discussed in the text,. $(1+y/2)^{N}$ represents the final proceeds of an investment of one unit of cur-. rency semiannually compounded $N$ times. There is no such interpretation. for an exponent that is not a whole number of semiannual periods. In any. case, continuing along these lines, the present value of a unit of currency to be paid after $\tau+i$ semiannual periods is,  

$$
{\frac{1}{\left(1+{\frac{y}{2}}\right)^{\tau+i}}}
$$  

Finally, then, consider a bond with $2T$ remaining coupon payments of. $c/2$ , the first of which is paid after $\tau$ semiannual periods, the second after $\tau+1$ semiannual periods, the third after $\tau+2$ semiannual periods, etc., and the last, along with a principal payment of 100, after $\tau+2T-1$ semiannual periods. Its price is given by,.  

$$
\begin{array}{l}{P=\frac{\frac{1}{2}c}{\left(1+\frac{y}{2}\right)^{\tau}}+\frac{\frac{1}{2}c}{\left(1+\frac{y}{2}\right)^{\tau+1}}+\cdots+\frac{100+\frac{1}{2}c}{\left(1+\frac{y}{2}\right)^{\tau+2T-1}}}\ {P=\frac{c}{2}\displaystyle\sum_{t=0}^{T-1}\frac{1}{\left(1+\frac{y}{2}\right)^{\tau+t}}+\frac{100}{\left(1+\frac{y}{2}\right)^{\tau+2T-1}}}\ {P=\left(1+\frac{y}{2}\right)^{1-\tau}\left(\frac{c}{y}\left(1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right)+\frac{100}{\left(1+\frac{y}{2}\right)^{2T}}\right)}\end{array}
$$  

where (A3.5) can be derived from Equation (A2.16) in Appendix A2.2.  

# A3.2 YIELD TO MATURITY AND EX-POST RETURNS  

For simplicity, this section assumes annual coupons and annual compounding.  

Proposition: A $T$ -year coupon bond priced at a yield of $y$ earns $y$ per year over $_n$ years if its coupons are all reinvested at $y$ and if the bond's yield at the end of $_n$ years is $y$  

Proof: Let $P_{0}$ and $P_{n}$ be the prices of the bond at time 0 $T$ years to maturity) and after $_n$ years $(T-n$ years to maturity) when its yield is $y$  

Starting with the definition of yield to maturity,  

$$
\begin{array}{c}{{P_{0}=\displaystyle\frac{c}{(1+y)}+\displaystyle\frac{c}{(1+y)^{2}}+\cdot\cdot\cdot+\displaystyle\frac{c}{(1+y)^{n-1}}+\displaystyle\frac{c}{(1+y)^{n}}}}\ {{+\displaystyle\frac{c}{(1+y)^{n+1}}+\displaystyle\frac{c}{(1+y)^{n+2}}+\cdot\cdot\cdot+\displaystyle\frac{100+c}{(1+y)^{T}}}}\end{array}
$$  

$$
P_{0}(1+y)^{n}=c(1+y)^{n-1}+c(1+y)^{n-2}+\cdot\cdot\cdot+c(1+y)+c
$$  

$$
+\frac{c}{(1+y)}+\frac{c}{(1+y)^{2}}+\cdot\cdot\cdot+\frac{100+c}{(1+y)^{T-n}}
$$  

$$
\begin{array}{l}{{\displaystyle P_{0}(1+y)^{n}=c(1+y)^{n-1}+\cdot\cdot\cdot+c(1+y)+c+P_{n}}}\ {{\displaystyle(1+y)^{n}-1=\frac{c(1+y)^{n-1}+\cdot\cdot\cdot+c(1+y)+c+P_{n}-P_{0}}{P_{0}}}}\end{array}
$$  

where (A3.7) simply multiplies both sides of (A3.6) by $(1+y)^{n}$ ; (A3.8) recognizes that the second line of (A3.7) is just $P_{n}$ , the price of the bond after. $_n$ years, with a remaining maturity of $T-n$ years and a yield of. $y$ ; and (A3.9) simplifies terms.  

By inspection, the right-hand side of Equation (A3.9) is the $_n$ -year return of the bond if all coupons are reinvested at $y$ and if the yield after $_n$ years is $y$ . Breaking that down, the numerator gives the reinvested coupon payments at a yield of $y$ ; plus $P_{n}$ , the price of the bond after $_n$ years if the yield is $y$ minus $P_{0}$ the initial price of the bond at the yield $y$ . Hence, the numerator divided by the initial price equals the $_n$ -year return.  

But if the right-hand side of the bond is the $_n$ -year return under the conditions stated, then, by the left-hand side, that return is equivalent to earning $y$ per year for $_n$ years.  

Note that the proposition is not an "if and only if," because it is possible - though very unlikely - to have some combination of returns on coupons and a final yield that also result in a holding-period return of $y$ per year.  

# A3.3 REALIZED FORWARD SCENARIO  

For simplicity, this section assumes annual coupons and annual compounding.  

Proposition: Under the realized forward scenario, the. $_n$ -year return of a $T$ -year coupon, with coupon income reinvested at the initial forward rates $f(1),f(2),\ldots f(n)$ , is the same as from rolling over a unit of currency at those. forward rates.  

Proof: Let $P_{0}$ and $P_{n}$ be the prices of the bond at time 0 (. $T$ years to maturity) and after $_n$ years $(T-n$ years to maturity) under the realized forward scenario.  

Starting with the definition of forward rates,  

$$
\begin{array}{l}{{P_{0}=\displaystyle\frac{c}{\left(1+f\left(1\right)\right)}+\frac{c}{\left(1+f\left(1\right)\right)\left(1+f\left(2\right)\right)}+\cdot\cdot\cdot}}\ {{\displaystyle\quad+\frac{c}{\left(1+f\left(1\right)\right)\cdot\cdot\cdot\left(1+f\left(n\right)\right)}}}\ {{\displaystyle\quad+\frac{c}{\left(1+f\left(1\right)\right)\cdot\cdot\cdot\cdot\left(1+f\left(n+1\right)\right)}+\cdot\cdot\cdot}}\ {{\displaystyle\quad+\frac{100+c}{\left(1+f\left(1\right)\right)\cdot\cdot\cdot\left(1+f\left(T\right)\right)}}}\end{array}
$$  

$$
\begin{array}{c}{{P_{0}(1+f(1))\cdot\cdot\cdot(1+f(n))=c(1+f(2))\cdot\cdot\cdot(1+f(n))+\cdot\cdot\cdot+c}}\ {{\mathrm{}}}\ {{\displaystyle+\frac{c}{(1+f(n+1))}+\cdot\cdot\cdot}}\ {{\mathrm{}}}\ {{\displaystyle+\frac{100+c}{(1+f(n+1))\cdot\cdot\cdot(1+f(T))}}}\end{array}
$$  

$$
P_{0}(1+f(1))\cdot\cdot\cdot(1+f(n))=c(1+f(2))\cdot\cdot\cdot(1+f(n))+\cdot\cdot\cdot+c+P_{n}
$$  

$$
(1+f(1))\cdot\cdot\cdot(1+f(n))-1={\frac{c(1+f(2))\cdot\cdot\cdot(1+f(n))+\cdot\cdot\cdot+c+P_{n}-P_{0}}{P_{0}}}.
$$  

where (A3.11) simply multiplies both sides of (A3.10) by $(1+f(1))\cdots\cdot\cdot(1+$ $f(n))$ ; (A3.12) recognizes that the second and third lines of (A3.11) are $P_{n}$ the price of the bond after $_n$ years, with discounting under the assumption of realized forwards; and (A3.13) simplifies terms.  

By inspection, the right-hand side of Equation (A3.13) is the $_n$ -year return of the bond if all coupons are reinvested at the short-term rate of the realized forward scenario and if, after. $_n$ years, the bond is priced under. that scenario. But if the right-hand side is the bond's $_n$ -year return under the conditions stated, then, by the left-hand side, that return is equivalent to rolling over a unit of currency at the initial forward rates for $_n$ years.  

Corollary: Under the realized forward scenario, the one-year return of any coupon bond is the short-term rate, $f(1)$  

Proof: Following the proof of the previous proposition with $n=1$ Equation (A3.13) becomes,  

$$
f(1)=\frac{c+P_{1}-P_{0}}{P_{0}}
$$  

which was to be proved.  

# DV01, Duration, and Convexity  

# A4.1 DVO1, DURATION, AND CONVEXITY OF PORTFOLIOS  

Let $P^{i}$ denote the price of asset. $i$ and $P$ the price of a portfolio of those assets. By definition,  

$$
P=\sum P^{i}
$$  

Let $y$ be the single factor generating changes in rates. Then, taking the derivative of both sides of (A4.1) with respect to $y$  

$$
{\frac{d P}{d y}}=\sum{\frac{d P^{i}}{d y}}
$$  

Then, divide both sides of (A4.2) by -10,000 and apply Equation (4.5) of the text to see that,  

$$
D V01=\sum D V01^{i}
$$  

Or, in words, the Dv01 of a portfolio equals the sum of the individual asset DV01s.  

To derive the duration of a portfolio, start from Equation (A4.2), dividing both sides by $-{\cal P}$  

$$
{\begin{array}{r l}&{-{\frac{1}{P}}{\frac{d P}{d y}}=\sum{-{\frac{1}{P}}{\frac{d P^{i}}{d y}}}}\ &{-{\frac{1}{P}}{\frac{d P}{d y}}=\sum{-{\frac{P^{i}}{P}}{\frac{1}{P^{i}}}{\frac{d P^{i}}{d y}}}}\ &{\qquadD=\sum{\frac{P^{i}}{P}}D^{i}}\end{array}}
$$  

Equation (A4.5) multiplies each term in the summation by one, in the form of $\overset{}{P^{i}}/\overset{}{P^{i}}$ . Equation (A4.6) follows from the definition of duration in the text,.   
Equation (4.11). In words, Equation (A4.6) says that the duration of a port-.   
folio equals the weighted average of the durations of the individual assets,.   
where the weights are the fraction of value of each asset in the portfolio..  

The proof for the convexity of a portfolio can be derived along the same lines as the duration of a portfolio. The result, given here without proof, is,  

$$
C=\sum{\frac{P^{i}}{P}}C^{i}
$$  

# A4.2 ESTIMATING PRICE CHANGE WITH DURATION AND CONVEXITY  

Let $P(y)$ be the price of an asset as a function of the single factor that describes changes in rates. Then, a second-order Taylor approximation of the price rate function is given by,  

$$
P(y+\Delta y)\approx P(y)+\frac{d P}{d y}\Delta y+\frac{1}{2}\frac{d^{2}P}{d y^{2}}\Delta y^{2}
$$  

Subtracting $P(y)$ from both sides of (A4.8) and denoting the change in price, $P(y+\Delta y)-P$ , by $\Delta P$  

$$
\Delta P\approx{\frac{d P}{d y}}\Delta y+{\frac{1}{2}}{\frac{d^{2}P}{d y^{2}}}\Delta y^{2}
$$  

$$
\begin{array}{l}{\displaystyle{\frac{\Delta P}{P}\approx\frac{1}{P}\frac{d P}{d y}\Delta y+\frac{1}{2}\frac{1}{P}\frac{d^{2}P}{d y^{2}}\Delta y^{2}}}\ {~}\ {\displaystyle{\frac{\Delta P}{P}\approx-D\Delta y+\frac{1}{2}C\Delta y^{2}}}\end{array}
$$  

where (A4.11) - which is Equation (4.16) - follows from the definitions of. duration and convexity, that is, from Equation (4.10) and a discrete version of Equation (4.14).  

# Regression Hedging and Principal Component Analysis  

# A6.1 REGRESSION HEDGES AND P&L VARIANCE  

This section proves that i) the regression hedge minimizes the variance of the. P&L of the hedged portfolio; and ii) the volatility of the regression-hedged. portfolio equals the Dv01 of the position being hedged times the standard deviation of the regression residuals..  

Begin with least-squares estimation, which finds the parameters $\hat{\alpha}$ and $\hat{\beta}$ to minimize,  

$$
\sum_{t}(\Delta y_{t}-\hat{\alpha}-\hat{\beta}\Delta x_{t})^{2}
$$  

To solve this minimization, differentiate (A6.1) with respect to each of the parameters, set each result to zero, and obtain the following two equations,  

$$
\begin{array}{c}{-2\displaystyle\sum_{t}(\Delta y_{t}-\hat{\alpha}-\hat{\beta}\Delta x_{t})=0}\ {-2\displaystyle\sum_{t}(\Delta y_{t}-\hat{\alpha}-\hat{\beta}\Delta x_{t})\Delta x_{t}=0}\end{array}
$$  

These equations can be solved to show that,  

$$
\begin{array}{r}{\hat{\alpha}=\overline{{\Delta y}}-\hat{\beta}\overline{{\Delta x}}}\ {\hat{\beta}=\overline{{\frac{\sigma_{x y}}{\sigma_{x}^{2}}}}=\overline{{\frac{\rho\sigma_{y}}{\sigma_{x}}}}}\end{array}
$$  

where $\overline{{\Delta x}}$ and $\overline{{\Delta y}}$ are the sample averages; $\sigma_{x}$ and $\sigma_{y}$ the standard deviations; $\sigma_{x y}$ the covariance; and $\rho$ the correlation. The solutions (A6.4) and (A6.5)  

are not derived step-by-step here, but are easily found by noting that, with $N$ observations, the summary statistics needed are defined as follows,  

$$
\begin{array}{r l}&{\overline{{\Delta x}}=\frac{\sum_{t}\Delta x_{t}}{N}}\ &{\overline{{\Delta y}}=\frac{\sum_{t}\Delta y_{t}}{N}}\ &{\sigma_{x}^{2}=\frac{\sum_{t}\Delta x_{t}^{2}}{N}-\left(\frac{\sum_{t}\Delta x_{t}}{N}\right)^{2}}\ &{\sigma_{y}^{2}=\frac{\sum_{t}\Delta y_{t}^{2}}{N}-\left(\frac{\sum_{t}\Delta y_{t}}{N}\right)^{2}}\ &{\sigma_{x}=\frac{\sum_{t}\Delta y_{t}\Delta x_{t}}{N}-\frac{\sum_{t}\Delta y_{t}\sum_{t}\Delta x_{t}}{N}}\ &{\rho=\frac{\sigma_{x}y}{\sigma_{x}\sigma_{y}}}\end{array}
$$  

The discussion now turns to minimizing the $\mathrm{P}\&\mathrm{L}$ of the hedged position. That $\mathrm{P}\&\mathrm{L}$ , given in Equation (6.11), is repeated here for convenience,  

$$
P\&L=-F^{J N J}\frac{D V01^{J N J}}{100}\Delta y_{t}^{J N J}-F^{30}\frac{D V01^{30}}{100}\Delta y_{t}^{30}
$$  

To simplify notation, write the Dv01s of the bond positions as,  

$$
\begin{array}{l}{{\overline{{D V01}}^{J N J}\equiv\frac{F^{J N J}D V01^{J N J}}{100}}}\ {{\overline{{D V01}}^{30}\equiv\frac{F^{30}D V01^{30}}{100}}}\end{array}
$$  

Then, with the obvious notations for variance and covariance, the variance of the $\mathrm{P}\&\mathrm{L}$ in (A6.12), denoted P&L is, 1  

$$
\begin{array}{l}{{\sigma_{P\&L}^{2}=\left(\overline{{{D V01}}}^{J N J}\right)^{2}\sigma_{J N J}^{2}+\left(\overline{{{D V01}}}^{30}\right)^{2}\sigma_{30}^{2}}}\ {{\qquad+2\overline{{{D V01}}}^{J N J}\overline{{{D V01}}}^{30}\sigma_{J N J,30}}}\end{array}
$$  

To minimize this variance by choosing the Dv01 in the hedging bonds, differentiate (A6.15) with respect to $\overline{{D V01}}^{30}$ , set the result to zero, and solve. for $\overline{{D V01}}^{30}$  

$$
\begin{array}{c}{{2\overline{{{D V01}}}^{30}\sigma_{30}^{2}+2\overline{{{D V01}}}^{J N J}\sigma_{J N J,30}=0}}\ {{\overline{{{D V01}}}^{30}=-\overline{{{D V01}}}^{J N J}\frac{\sigma_{J N J,30}}{\sigma_{30}^{2}}}}\end{array}
$$  

But, by inspection of Equation (A6.5), the fraction in (A6.16) is just the estimated slope coefficient in a regression of JNJ yields on 30-year Treasury yields. Hence, the regression hedge given in Equations (6.8) or (6.10) minimizes the variance of the $\mathrm{P}\&\mathrm{L}$ of the hedged position.  

The minimized P&L variance of the hedged portfolio can be written. explicitly by substituting Equation (A6.16) into Equation (A6.15) and rearranging terms,  

$$
\begin{array}{r l}&{\sigma_{P\mathrm{R}L}^{2}=\left(\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\right)^{2}\sigma_{_{J N J}^{2}}^{2}+\left(\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\right)^{2}\frac{\sigma_{_{J N J,30}^{2}}^{2}}{\sigma_{_{30}^{2}}^{2}}}\ &{\qquad-2\left(\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\right)\left[\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\frac{\mathcal{N}Y}{\sigma_{_{J N,30}^{2}}^{2}}\right]\sigma_{_{J N J,30}}}\ &{\qquad=\left(\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\right)^{2}\sigma_{_{J N,7}^{2}}^{2}\left[1-\frac{\sigma_{_{J N,30}^{2}}^{2}}{\sigma_{_{30}^{2}}^{2}\sigma_{_{J N}^{2}}^{2}}\right]}\ &{\qquad=\left(\overline{{D V01}}^{\mathcal{N}\mathcal{I}}\right)^{2}\sigma_{_{J N}^{2}}^{2}[1-\rho^{2}]}\end{array}
$$  

where $\rho$ denotes the correlation between changes in the JNJ and Treasury bond yields.  

The last step for this section is to show that the variance of the hedged P&L, now given in (A6.19), is equal to the squared Dv01 of the bonds. being hedged times the variance of the regression residuals. Starting with the definition of the regression residuals in the general regression context of (A6.1), their variance, denoted. $\sigma_{\epsilon}^{2}$ , can be expressed as follows,.  

$$
\begin{array}{r l}&{\epsilon_{t}=\Delta y_{t}-\alpha-\beta\Delta x_{t}}\ &{\sigma_{\epsilon}^{2}=\sigma_{y}^{2}+\beta^{2}\sigma_{x}^{2}-2\beta\sigma_{x y}}\ &{\quad\quad=\sigma_{y}^{2}+\bigg(\frac{\rho\sigma_{y}}{\sigma_{x}}\bigg)^{2}\sigma_{x}^{2}-2\left(\frac{\rho\sigma_{y}}{\sigma_{x}}\right)\sigma_{x y}}\ &{\quad\quad=\sigma_{y}^{2}(1-\rho^{2})}\end{array}
$$  

But applying Equation (A6.23) to the regression of the JNJ bonds on the. 30-year Treasury bonds, and multiplying by the DV01 of the JNJ bonds,. gives exactly the right-hand side of Equation (A6.19), which was to be proved.  

# A6.2 CONSTRUCTION OF PRINCIPAL COMPONENTS  

The goal of this section is to illustrate how PCs are constructed with a minimum of mathematics. A slightly more rigorous mathematical treatment is given in Section A6.3. For illustration, this section uses the data from the text on daily, basis-point changes in the five-, 10-, and 30-year swap rates only. The covariance matrix, or the variance-covariance matrix of these rate changes is,  

$$
\mathbf{V}={\left(\begin{array}{l l l}{6.46}&{7.71}&{7.10}\ {7.71}&{11.89}&{12.95}\ {7.10}&{12.95}&{16.19}\end{array}\right)}
$$  

The diagonal of the matrix in (A6.24) gives the variances of the three rates, or, taking square roots, the standard deviations. The off-diagonals give the pairwise covariances of rates, from which the correlations can be derived. For example, the volatilities of the five- and 10-year rates are the square roots of 6.46 and 11.89, or 2.54 and 3.45 basis points per day, respectively, and the correlation between them is. $7.71/(2.54\times3.45)=88.0\%$ . Note, in passing, that the sum of the variances is. $6.46+11.89+16.19=34.54$ a number that appears again below.  

Now consider portfolio weights or loadings of $-0.5,1.0$ and $-0.6$ on the five-, 10-, and 30-year rates, respectively. By the properties of variance and covariance, and with the specific covariance matrix (A6.24), the variance of this portfolio, denoted ${\sigma}_{p}^{2}$ , is,  

$$
\begin{array}{r l}&{\sigma_{\boldsymbol{p}}^{2}=(-0.5)^{2}\times6.46+1.0^{2}\times11.89+(-0.6)^{2}\times16.19}\ &{\qquad+2\times(-0.5)\times(1.0)\times7.71}\ &{\qquad+2\times(-0.5)\times(-0.6)\times7.10}\ &{\qquad+2\times(1.0)\times(-0.6)\times12.95}\ &{\qquad+2\times3860^{2}}\end{array}
$$  

Computations like this are more conveniently written with matrix notation. Let the vector of portfolio weights be w, which, in the present example,  

.5 $\mathbf{w}^{\prime}=(-0.5,1.0,-0.6)$ , where the apostrophe denotes the transpose. Then,. the same variance as computed in Equation (A6.25) can be written as,  

$$
\mathbf{w}^{\prime}\mathbf{Vw}=(-0.51.0-0.6)\left({\begin{array}{c c c}{6.46}&{7.71}&{7.10}\ {7.71}&{11.89}&{12.95}\ {7.10}&{12.95}&{16.19}\end{array}}\right)\left({\begin{array}{c}{-0.5}\ {1.0}\ {-0.6}\end{array}}\right)
$$  

Turning to the creation of the PCs, denote the first principal component by the vector of weights $\mathbf{a}=(a_{1},a_{2},a_{3})^{\prime}$ . Then, solve for the elements of a. by maximizing the variance of this PC, a'Va, such that $\mathbf{a}^{\flat}\mathbf{a}=1$ . Maximization ensures that, among all the PCs, the first explains the largest fraction of the sum or total variance across all rates. But there has to be some limit on the vector a, or the maximization would find portfolios with arbitrarily large variances. Enter the constraint a'a. $=1$ , which - along with similar constraints on other PCs - limits the risks of the PCs in a way that equates the sum of the variances of all PCs to the total variance. (See Section A6.3 for more details.) The maximization just described can be solved with the solver in Excel or some other tool to obtain that. $\mathbf{a}=(0.3846,0.6090,0.6937)^{\prime}$ . The variance of this PC is. $\mathbf{a}^{\prime}\mathbf{V}\mathbf{a}=31.4977$ , which is $91.2\%$ of the total variance of 34.54 given above.  

The second principal component, denoted by ${\mathbf{b}}=(b_{1},b_{2},b_{3})^{\prime}$ , maximizes b'Vb such that ${\bf b}^{\mathfrak{N}}{\bf b}=1$ and $\mathbf{b}^{\flat}\mathbf{a}=0$ . This last constraint ensures that the portfolio represented by the second PC is uncorrelated with the portfolio represented by the first. (Again, see Section A6.3 for more details.) Solving this maximization, $\mathbf{b}=(-0.7851,-0.1793,0.5928)^{\prime}$ . The variance of this PC is ${\bf b}^{\prime}{\bf V}{\bf b}=2.8626$ , which is. $8.3\%$ of the total variance of 34.54.  

Finally, the third PC, denoted by. ${\bf c}=(c_{1},c_{2},c_{3})^{\prime}$ , satisfies $c'c=1$ $\mathbf{c}^{\bullet}\mathbf{a}=0$ , and $\mathbf{c}{\mathbf{\'}}\mathbf{b}=0$ . Solving, $\mathbf{c}=(0.4854,-0.7726,0.4092)^{\prime}$ . No maximization is needed here because, by construction, this third PC explains all of the remaining total variance. The variance of this PC is. $\mathbf{c}^{\prime}\mathbf{V}\mathbf{c}=0.1797.$ which is the remaining. $0.5\%$ of the total variance of 34.54.  

The maximizations just described constrain the sum of squares of the elements of each PC to equal one. But a different scaling turns out to be. convenient for interpreting the PCs: multiply each element of a PC by the volatility of that PC. In that case, the sum of squares of the elements of a PC equals its variance. In addition, after this scaling, the elements of each. PC can be interpreted as the number of basis points corresponding to a one standard deviation shift in that PC. (Section A6.3 gives a more pre-. cise explanation of this point.) In the current example, the volatilities of the three PCs, from their variances computed above, are. ${\sqrt{31.4977}}=5.6123$ ${\sqrt{2.8626}}=1.6919$ and ${\sqrt{0.1797}}=0.4239$ , respectively. Multiplying the. elements of the respective raw PCs by these numbers gives the scaled PCs in.  

IABLE A6.1 Principal Components of USD LIBOR Swap Rates, from June 1, 2020, to July 16, 2021, Using Only. Five-, 10-, and 30-Year Rates. Entries Are in Basis Points.   


<html><body><table><tr><td>Term</td><td>Level</td><td>Slope</td><td>Curvature</td></tr><tr><td>5-Year</td><td>2.158</td><td>-1.328</td><td>0.206</td></tr><tr><td>10-Year</td><td>3.418</td><td>-0.303</td><td>-0.328</td></tr><tr><td>30-Year</td><td>3.893</td><td>1.003</td><td>0.173</td></tr></table></body></html>  

Table A6.1. It can then be said that a one standard deviation shock of the level PC is a 2.158-basis-point shift in the five-year rate, a 3.418-basis-point shift in the 10-year rate, and a 3.893-basis-point shift in the 30-year rate. The scaled slope and curvature PCs can be interpreted analogously.  

# A6.3CONSTRUCTION OF PCs: MATHEMATICAL DETAILS  

This section is more precise on a few claims made in the previous section at the cost of some extra mathematics. Let $\mathbf{V}$ denote the $3\times3$ variancecovariance matrix of rates with elements $V_{i j}$ ; let $\mathbf{P}$ denote the $3\times3$ matrix of principal components, with elements $p_{i j}$ , or, alternatively, with three $3\times1$ column vectors ${\bf p_{i}}$ corresponding to PC $i$ ; let $\mathbf{D}$ denote the $3\times3$ diagonal matrix with diagonal elements $\sigma_{i}^{2}$ , each equal to the variance of $\mathrm{PC}i;$ and let I denote the $3\times3$ identity matrix. Then, though not proved here, the construction of the PCs in the previous section guarantees that,  

$$
\mathbf{V}=\mathbf{P}\mathbf{D}\mathbf{P}^{\prime}
$$  

$$
\mathbf{P}^{\prime}\mathbf{P}=\mathbf{P}\mathbf{P}^{\prime}=\mathbf{I}
$$  

$$
\mathbf{P}^{\prime}\mathbf{V}\mathbf{P}=\mathbf{P}^{\prime}\mathbf{P}\mathbf{D}\mathbf{P}^{\prime}\mathbf{P}=\mathbf{D}
$$  

where (A6.29) follows from (A6.27) and (A6.28).  

Lemma 1: The PCs are uncorrelated.  

Proof: In terms of its columns, ${\bf P}=({\bf p}_{1},{\bf p}_{2},{\bf p}_{3})$ . With this, rewrite Equ-. ation (A6.29) as,  

$$
\mathbf{P}^{\prime}\mathbf{V}\mathbf{P}={\left(\begin{array}{l l l}{\mathbf{p}_{1}^{\prime}\mathbf{V}\mathbf{p}_{1}}&{\mathbf{p}_{1}^{\prime}\mathbf{V}\mathbf{p}_{2}}&{\mathbf{p}_{1}^{\prime}\mathbf{V}\mathbf{p}_{3}}\ {\mathbf{p}_{2}^{\prime}\mathbf{V}\mathbf{p}_{1}}&{\mathbf{p}_{2}^{\prime}\mathbf{V}\mathbf{p}_{2}}&{\mathbf{p}_{2}^{\prime}\mathbf{V}\mathbf{p}_{3}}\ {\mathbf{p}_{3}^{\prime}\mathbf{V}\mathbf{p}_{1}}&{\mathbf{p}_{3}^{\prime}\mathbf{V}\mathbf{p}_{2}}&{\mathbf{p}_{3}^{\prime}\mathbf{V}\mathbf{p}_{3}}\end{array}\right)}=\mathbf{D}
$$  

Because $D$ is diagonal, the numbers $\mathbf{p}_{1}^{\prime}\mathbf{Vp}_{2},\mathbf{p}_{1}^{\prime}\mathbf{Vp}_{3},\mathbf{p}_{2}^{\prime}\mathbf{Vp}_{3}$ are all zero. This means that the pairwise covariances of the PCs are zero, or, equivalently, that the PCs are uncorrelated with each other.  

Lemma 2: The variance of rate $j$ equals the sum of the variance of each PC times the square of its jth component. Mathematically,  

$$
V_{j j}={p_{1j}^{2}\sigma_{1}^{2}}+{p_{2j}^{2}\sigma_{2}^{2}}+{p_{3j}^{2}\sigma_{3}^{2}}
$$  

Proof: For $i=1$ , pre-multiply each side of Equation (A6.27) by the $1\times3$ vector $(1,0,0)$ and post-multiply by the $3\times1$ vector $(1,0,0)^{\prime}$ . Then,  

$$
\left(1~0~0\right){\bf V}\left(\begin{array}{l}{{1}}\ {{0}}\ {{0}}\end{array}\right)=\left(1~0~0\right){\bf P}{\bf D}{\bf P}^{\prime}\left(\begin{array}{l}{{1}}\ {{0}}\ {{0}}\end{array}\right)
$$  

Equation (A6.31) then follows by algebra. For $i=2$ , the proof is the same but with the vector (0,1, 0) and its transpose, and for $i=3$ with (0,0, 1).  

Lemma 3: The sum of the variances of the PCs equals the sum of the variances of the rates.  

Proof: Adding together Equations (A6.31) for each $j$ and rearranging terms,  

$$
\begin{array}{r l}&{V_{11}+V_{22}+V_{33}=p_{11}^{2}\sigma_{1}^{2}+p_{21}^{2}\sigma_{2}^{2}+p_{31}^{2}\sigma_{3}^{2}}\ &{\qquad+p_{12}^{2}\sigma_{1}^{2}+p_{22}^{2}\sigma_{2}^{2}+p_{32}^{2}\sigma_{3}^{2}}\ &{\qquad+p_{13}^{2}\sigma_{1}^{2}+p_{23}^{2}\sigma_{2}^{2}+p_{33}^{2}\sigma_{3}^{2}}\ &{\qquad=\sigma_{1}^{2}(p_{11}^{2}+p_{12}^{2}+p_{13}^{2})}\ &{\qquad+\sigma_{2}^{2}(p_{21}^{2}+p_{22}^{2}+p_{23}^{2})}\ &{\qquad+\sigma_{3}^{2}(p_{31}^{2}+p_{32}^{2}+p_{33}^{2})}\end{array}
$$  

But by Equation (A6.28), the sum of squares of the elements of each PC in the brackets, $\bf{p}_{i}^{\prime}\bf{p}_{i}$ , equals 1, thus proving the lemma..  

Lemma 4: Defined a scaled principal component matrix, $\tilde{\mathbf{P}}$ , with elements $\tilde{p}_{i j}=\sigma_{i}p_{i j}$ . Then,  

$$
\sqrt{V_{j j}}=\sqrt{\tilde{p}_{1j}^{2}+\tilde{p}_{2j}^{2}+\tilde{p}_{3j}^{2}}
$$  

Proof: This lemma follows directly from the definition of the $\tilde{p}_{i j}$ and Equation (A6.31).  

To understand the significance of Lemma 4, interpret the element $\tilde{p}_{i j}$ as the standard deviation of changes in the jth rate, in basis points, due to the scaled ith PC. Then, because the PCs are uncorrelated, the standard deviation of the jth rate, with contributions from all three scaled PCs, equals the right-hand side of Equation (A6.35). But the left-hand side of the equation is exactly the volatility of the jth rate. Hence, taken as a whole, Equation (A6.35) supports the interpretation of the elements of each scaled PCs as one standard deviation shifts in the three rates.  

# Expectations, Risk Premium, Convexity and the Shape of the Term Structure  

This appendix proves Equation (8.18) along the lines of Ingersoll (1987).1 Assume that $r$ , the single, instantaneous rate factor, follows the process,  

$$
d r=\mu d t+\sigma d w
$$  

Let $P$ be the full price of some security that depends on $r$ and time. Then, by Ito's lemma,  

$$
d P=P_{r}d r+P_{t}d t+{\frac{1}{2}}P_{r r}\sigma^{2}d t
$$  

where $P_{r},P_{t}$ , and $P_{r r}$ denote the partial first derivatives with respect to $r$ and $t$ and the second partial derivative with respect to $r$ . Dividing both sides of (A8.2) by $P$ , taking expectations, and defining $\alpha_{P}$ to be the expected return of the security,  

$$
\alpha_{P}d t\equiv E\left[\frac{d P}{P}\right]=\frac{P_{r}}{P}\mu d t+\frac{P_{t}}{P}d t+\frac{1}{2}\frac{P_{r r}}{P}\sigma^{2}d t
$$  

Combining (A8.1), (A8.2), and (A8.3),  

$$
\frac{d P}{P}-\alpha_{P}d t=\frac{P_{r}}{P}\sigma d w
$$  

Because Equation (A8.4) applies to any security, it also applies to some other security $\mathcal{Q}$  

$$
\frac{d Q}{Q}-\alpha_{Q}d t=\frac{Q_{r}}{Q}\sigma d w
$$  

Now consider the strategy of investing one unit of currency in security $P$ and $-P_{r}\mathcal{Q}/P\mathcal{Q}_{r}$ in security Q. From Equations (A8.4) and (A8.5), the return on this portfolio is,.  

$$
\frac{d P}{P}-\frac{P_{r}Q}{P Q_{r}}\frac{d Q}{Q}=\alpha_{P}d t-\frac{P_{r}Q}{P Q_{r}}\alpha_{Q}d t
$$  

Note that terms with the random variable dw have fallen out of Equation (A8.6). This particular portfolio is chosen, in fact, so as to hedge completely the risk of $P$ with $\mathcal{Q}$ . In any case, because the portfolio has no risk, it must earn the instantaneous rate, $r_{0}$  

$$
\alpha_{P}d t-\frac{P_{r}Q}{P Q_{r}}\alpha_{Q}d t=\left(1-\frac{P_{r}Q}{P Q_{r}}\right)r_{0}d t
$$  

Rearranging terms,  

$$
\frac{\alpha_{P}-r_{0}}{-P_{r}/P}=\frac{\alpha_{Q}-r_{0}}{-Q_{r}/Q}\equiv\lambda(r_{0},t)
$$  

Equation (A8.8) says that the expected return of any security above the. instantaneous rate divided by its duration with respect to that rate must equal some function $\uplambda$ . This function cannot depend on any characteristic of the security, because (A8.8) is true for all securities. The function may depend, however, on the interest rate factor and time. Rewriting Equation (A8.8), for any security $P$  

$$
E\left[{\frac{d P}{P}}\right]\equiv\alpha_{P}d t=r_{0}d t+\lambda D d t
$$  

# The Vasicek and Gauss+ Models  

# A9.1 THE VASICEK MODEL IN A BINOMIAL TREE  

This section illustrates the implementation of the Vasicek model in a binomial tree. The parameters are $r_{0}=2\%$ $\theta=11\%$ $k=0.0165$ ; and $\sigma=$ $0.95\%$ . The step size is one year. The first stages of construction are shown in Figure A9.1. The starting short-term rate, by definition is $2\%$ . By a discrete time approximation to the dynamics of the risk-neutral process in Equation (9.1) of the text, the expected short-term rate after one year is,  

$$
r_{0}+k(\theta-r_{0})d t=2\%+0.0165(11\%-2\%)\times1=2.1485\%
$$  

Note that, if the time step were one month, instead of one year, the dt factor would be $1/12$ instead of 1. In any case, adding a volatility of. $0.95\%$ up and down around the expectation from (A9.1) gives the date-1 up- and down-. states in Figure A9.1.  

Because of the mean reversion in the Vasicek model, computing the evolution of the short-term rate over the next date is more complicated than the examples in Chapter 7. More specifically, because the drifts from the two states on date 1 are different from the drift from date 0, the tree does not necessarily recombine. One methodology for constructing a recombining tree is the following, though a full analysis of numerical issues is beyond the scope of this treatment.  

Given that the expected short-term rate on date 1 is $2.1485\%$ as calculated in (A9.1), the expected short-term rate on date 2 is,  

$$
2.1485\%+0.0165(11\%-2.1485\%)\times1=2.2945\%
$$  

which is the short-term rate assigned to the date-2, state 1 node of Figure A9.1.  

![](62486b2d32838b659f63617cee941608f04ccc7008e7f1f3e186fc81c94cfefe.jpg)  
FIGURE A9.1  Binomial Tree Setup for Three Dates of the Vasicek Model.  

The next stages of the construction are to find the missing rates and probabilities in Figure A9.1. From the date-1 up-state, the unknowns, $r^{u u}$ and $p$ , must result in the drift and volatility specified by the model. Mathematically, the drift condition is,  

$$
\begin{array}{r}{3.0985\%+0.0165(11\%-3.0985\%)=3.2289\%\qquad}\ {=p\times r^{u u}+(1-p)\times2.2945\%\qquad}\end{array}
$$  

and the volatility condition is,  

$$
0.95\%={\sqrt{p(r^{u u}-3.2289\%)^{2}+(1-p)(3.2289\%-2.2945\%)^{2}}}
$$  

Solving Equations (A9.3) and (A9.4) simultaneously shows that $p=$ .4917 and $r_{u u}=4.1949\%$ . These values are given in Figure A9.2 along with solutions to the analogous equations for $q$ and $r_{d d}$  

![](d48af9d873ed039decf28fe4f47c3090a96280176e624855cc7f526cf2c258c2.jpg)  
FIGUrE A9.2 Binomial Tree Solution for Three Dates of the Vasicek Model.  

# A9.2 THE GAUSS+ MODEL  

# A9.2.1 Model Solution  

Recall the dynamics of the short rate in cascade form presented in the text, where the cascade form means that each factor mean reverts to another fac-. tor, which mean reverts to another factor, in order of persistence. In order to solve the model (where "solving" means solving for the mapping from factors to forward rates), it will be convenient to work with the factors written. in reduced form (where "reduced form" means that each factor mean reverts. to a constant). After we have solved the model, we will write it back in cas-. cade form in order to proceed to the estimation of its parameters. It will. be convenient to partition the parameter vector $P=(\alpha_{s},\alpha_{m},\alpha_{l},\sigma_{l},\sigma_{m},\rho,\mu)$ in three blocks as $\alpha=(\alpha_{s},\alpha_{m},\alpha_{l})$ and $\sigma=(\sigma_{l},\sigma_{m},\rho)$ and $\mu$ . In the reduced form, we have $r_{t}=\mu+1^{\prime}X_{t}$ and the relationship between the reduced form expression and cascade form expression of the factors is,.  

$$
x_{t}=A(\alpha)X_{t}+\mu
$$  

where,  

$$
A(\alpha)=\left[{\begin{array}{c c c}{1}&{1}&{1}\ {0}&{{\frac{\alpha_{r}-\alpha_{m}}{\alpha_{r}}}}&{{\frac{\alpha_{r}-\alpha_{l}}{\alpha_{r}}}}\ {0}&{0}&{{\frac{(\alpha_{r}-\alpha_{l})(\alpha_{m}-\alpha_{l})}{\alpha_{r}}}}\end{array}}\right]
$$  

The dynamics of the reduced form factors are then given by,  

$$
d X_{t}=-d i a g(\alpha)X_{t}d t+A(\alpha)^{-1}\Omega d W_{t}
$$  

where for convenience we have appended a zero to the two-dimensional random process $d\mathbb{W}_{t}$ and,  

$$
\Omega(\sigma)=\left[\begin{array}{c c c}{{0}}&{{0}}&{{0}}\ {{\rho\sigma_{m}~\sqrt{1-\rho^{2}}\sigma_{m}~0}}&{{}}&{{}}\ {{\sigma_{l}}}&{{0}}&{{0}}\end{array}\right]
$$  

Let $P_{t}(\tau)$ denote the zero coupon bond price at time $t$ with time-to-expiry $\tau$ Taking the usual expectation of exponential of future short rate path conditional on the factors expressed in reduced form, one can show that,  

$$
P_{t}(\tau)=E^{Q}\left(e^{-\int_{0}^{\tau}r_{s}d s}\right)=e x p(-y_{t}(\tau)\tau)
$$  

where the yield of a zero coupon bond with maturity $\tau$ at time $t$ is given by,  

$$
y_{t}(\tau)=\mu-C(\tau,\alpha,\sigma)+B(\tau,\alpha)X_{t}
$$  

where $B(\tau,\alpha)$ is a three-dimensional vector with $B_{i}(\tau)=(1-e x p(-\alpha_{i}\tau))/\alpha_{i}\tau$ for $i={1,2,3}$ , and the term $\mathrm{C}(\tau,\alpha,\sigma)$ can be written as,  

$$
C(\tau,\alpha,\sigma)=\sum_{i=1}^{3}\sum_{j=1}^{3}\frac{\sigma_{i j}}{2\alpha_{i}\alpha_{j}}\left(1-B_{i}(\tau)-B_{j}(\tau)-\frac{1-e x p(-(\alpha_{i}+\alpha_{j})\tau)}{(\alpha_{i}+\alpha_{j})\tau}\right)
$$  

where $\sigma_{i j}$ stands for the ith row and jth column of matrix, $A(\alpha)^{-1}\Omega(\sigma)\Omega(\sigma)^{\prime}$ $A(\alpha)^{-1}$ with,  

$$
\begin{array}{r}{A(\alpha)^{-1}=\left[\begin{array}{c c}{1-\frac{\alpha_{r}}{\alpha_{r}-\alpha_{m}}}&{\frac{\alpha_{r}\alpha_{m}}{(\alpha_{r}-\alpha_{m})(\alpha_{r}-\alpha_{l})}}\ {0}&{\frac{\alpha_{r}}{\alpha_{r}-\alpha_{m}}}&{\frac{\alpha_{r}\alpha_{m}}{(\alpha_{r}-\alpha_{m})(\alpha_{m}-\alpha_{l})}}\ {0}&{0}&{\frac{\alpha_{r}\alpha_{m}}{(\alpha_{r}-\alpha_{l})(\alpha_{m}-\alpha_{l})}}\end{array}\right]}\end{array}
$$  

Mapping reduced form factors in (A9.10) to factors in cascade form, we finally have,  

$$
\boldsymbol{y}_{t}(\tau)=\mu(1-\Upsilon(\tau,\boldsymbol{\alpha})\mathbf{1})-\boldsymbol{\mathrm{C}}(\tau,\boldsymbol{\alpha},\boldsymbol{\sigma})+\Upsilon(\tau,\boldsymbol{\alpha})\boldsymbol{x}_{t}
$$  

where 1 is a three-dimensional column vector of ones and we have defined,  

$$
\Upsilon(\tau,\alpha)=B(\tau,\alpha)A(\alpha)^{-1}
$$  

where $\Upsilon(\tau,\alpha)=(\Upsilon_{s}(\tau,\alpha),\Upsilon_{m}(\tau,\alpha),\Upsilon_{l}(\tau,\alpha),)$ where $\Upsilon_{s},\Upsilon_{m}$ and $\Upsilon_{l}$ represent the partial derivatives (a.k.a. loadings) of the changes of the zero coupon. yield of maturity $\tau$ on the short, medium and long rate factors. A similar rep-. resentation for the (continuously compounded) forward rate of tenor. $\tau^{\prime}$ as an affine function of the factors in cascade form can be obtained as follows,  

$$
f_{t}(\tau)=\mu(1-\Upsilon^{\prime}(\tau,\alpha,\tau^{\prime})\mathbf{1})+\Upsilon^{\prime}(\tau,\alpha,\tau^{\prime})x_{t}-C^{\prime}(\tau,\alpha,\sigma,\tau^{\prime})
$$  

where,  

$$
\begin{array}{r}{\Upsilon^{\prime}(\tau,\alpha,\tau^{\prime})=(B(\tau+\tau^{\prime},\alpha)-B(\tau,\alpha))A(\alpha)^{-1}/\tau^{\prime}}\ {\hfill}\ {\mathrm{C}^{\prime}(\tau,\alpha,\sigma,\tau^{\prime})=(C(\tau+\tau^{\prime},\alpha,\sigma)-C(\tau,\alpha,\sigma,\tau^{\prime}))/\tau^{\prime}}\end{array}
$$  

Expression (A9.15) can be interpreted as follows: The time $t$ forward rate with maturity $\tau$ and tenor $\tau^{\prime}$ can be decomposed into a component that. represents the risk-neutral expectation of the $\tau^{\prime}$ maturity yield prevailing at.  

time $t+\tau$ (first two terms of the right-hand side) minus a component that represents the convexity advantage of receiving (i.e., being long) rates (third term of the right-hand side). The first on the right-hand side component can be shown to be null for $\tau=0$ and converges to $\mu$ as $\tau$ grows toward infinity. For maturities between zero and infinity, the risk-neutral expectation of the zero yield prevailing at that maturity will depend on the value that the factors take at time $t$ , namely, $\boldsymbol{x}_{t}=(\boldsymbol{r}_{t},m_{t},l_{t})$ , and this is what the second term on the right-hand side captures. We can also think of the sum of the first two components on the right-hand side as the fair futures rate at time $t$ for a mark-to-market futures contract on the zero coupon yield that will prevail at time $t+\tau$ . The shape of the slopes $\Upsilon^{\prime}(\tau,\alpha,\tau^{\prime})$ , evaluated at estimated parameter values, are displayed in Figure 9.7.  

The last term on the right-hand side of (A9.15) is null for. $\tau=0$ and grows at speed equal to the square of maturity. $\tau$ . This convexity term drives. a wedge between the futures rate and the forward rate. Imagine that an investor can bet on the yield that will prevail at time. $t+\tau$ in two different contracts: the first is a daily-settled futures contract. Any increase (decrease) in the market expected future rate will be paid (received) today by the long. (short) investor. The second is a standard forward contract. Any increase (decrease) in the market expected future rate will be paid (received) by the long (short) investor not today, but at time $t+\tau$ . Now, if the futures rate and. the forward rate were equal, the long investor would be at an advantage in transacting via the forward contract rather than the futures contract: when. the market future rate expectation increases (decreases) their future losses (gains) will be discounted to today at a relatively higher (lower) rate, hence yielding a relatively smaller (larger) present value loss (gain). Therefore, to prevent an arbitrage between forward and futures rates, today's forward rate should be somewhat lower than today's futures rate. The difference between the two is what we call the convexity correction or convexity advantage term, that is, the last term on the right hand side.  

# A9.2.2 A Practical Estimation Method  

There exists a large literature on estimating gaussian term structure models, of which the Gauss+ model is a particular case. The methods typically rely on maximum-likelihood estimation procedures which are not easy to implement in general. In the next section we discuss a procedure that is fast and intuitive for the purpose of finding reasonable values for the Gauss $^{\ast+}$ parameter vector $P=(\alpha,\sigma,\mu)$ . Given this parameter vector, and for any time $t$ , we will then extract the factors $\boldsymbol{x}_{t}=(\boldsymbol{r}_{t},m_{t},l_{t})$ in order to have the model zero yields be close to the market zero yields. The short rate $r_{t}$ will not need to be filtered because it will be set equal to the observed short policy rate..  

In order to estimate parameters $\alpha,\sigma,\mu$ , we first obtain a time series of zero coupon bond prices (discount factors) at different maturities. These can be obtained by using an external curve construction bootstrap method using.  

bonds or par swap rates. For the purpose of fitting the Gauss+ model, it does. not matter whether these discount factors come from a swap curve (index. or discount curves) or from a bond curve. Here we will use the time series of zero coupon bonds published by the New York Fed, which is based on. applying the well-known Nelson-Siegel-Svensson smooth curve construction procedure to US Treasury notes and bonds.2.  

There is always a trade-off when it comes to selecting the sample for the estimation of the model. Longer samples will lead to more robust estimates. in a statistical sense but will also reflect different market conditions from the ones in which we intend to use the model. We have found that, in practice, a good compromise is to use a sample size of eight years and a decay factor of. 0.8. (This means that in the loss-functions associated with the optimization problems that follow we will give a weight of 1 to the last observation, a weight of 0.8 to an observation that is one year old relative to the last observation, a weight of 0.64 to an observation that is two years old relative to. the last observation, and so forth.) Our sample thus begins on January 5,. 2014, and ends on January 21, 2022.  

While the $\mathrm{Gauss+}$ model involves three factors, only two are genuine. factors as we will equal the short rate to a given observed short rate, which tends to change at predictable dates. For this reason, we will take the short rate $r_{t}$ to be the fed funds target. While taking the general collateral repo rate would be closer to the actual overnight funding rate for US Treasury bonds, this series also exhibits spikes that reflect circumstantial funding conditions and are generally unrelated to monetary policy, and hence unrelated to expectations of future paths of the short rate..  

In what follows we will denote by $Y$ the $T\times N$ matrix of observed zero coupon yields for $T$ periods and $N$ maturities, and by $Y_{t}$ the vector of $N$ maturity yields observed at time $t$ . Similarly, we will denote by $y$ the vector of model implied zero coupon yields for $T$ periods and $N$ maturities. $y$ is a function of $x$ , the $T\times3$ vector of factors in cascade form. In addition, let and $y_{t}$ , as described in (A9.13), stand for the vector of yields for the $N$ maturities as a function of the cascade form factors at time $t$ , namely, $\boldsymbol{x}_{t}=(\boldsymbol{r}_{t},m_{t},l_{t})$ Finally, let $y_{t}(\tau)$ stand for the yield of maturity $\tau$ at time $t$ , as a function of the factors and the parameter vector $P$  

Estimation involves one step for data preparation, and three steps for parameter optimization. Data preparation consists of netting the effect of the (observed) short rate factor from the observed zero coupon yields. This works as follows. Take a candidate parameter value for $\alpha_{r}$ . Then, given the structure of $\Upsilon(\tau,\alpha)$ , subtract $\Upsilon_{s}(\tau,\alpha)\times r_{t}$ from both sides of (A9.13). With an abuse of notation, we will denominate $y_{t}(\tau)$ the zero coupon yield netted out of the short rate, and we will drop the short rate $r_{t}$ from the vector of factors in cascade form, so from now on we have $\boldsymbol{x}_{t}=(m_{t},l_{t})$ . Incidentally, one could show that $\Upsilon_{s}(\tau,\alpha)$ depends only on parameter $\alpha_{r}$  

The next step consists of inverting (A9.13) and expressing the factors $x_{t}$ as a linear function of the observed two- and 10-year yields (henceforth 2y and 10y). We will assume that the yields of these two maturities are priced exactly by the model, unlike other maturities. Denote these benchmark yields at time $t$ as $y b_{t}=(y_{t}(2),y_{t}(10))$ . We can then invert (A9.13) for the 2y and 10y maturity and express the factors in cascade form as linear functions of the vector of benchmark yields. Then we replace the resulting expression for the factors in (A9.13). Finally, write the resulting expression of benchmark yields as a function of factors, in changes,  

$$
\Delta y b_{t}(\tau)=\Upsilon_{b}(\alpha)\Delta x_{t}
$$  

where $\Upsilon_{b}(\alpha)$ stands for a matrix formed by the vectors (A9.14) corresponding to maturities $\tau=2{,}10$ , and dropping the column. Now, solving for $\Delta x_{t}$ and plugging the resulting expression into equation (A9.13) written in changes, we obtain a linear expression relating the yield changes at any maturity to the yield changes of the two benchmark maturities, where the slopes are a nonlinear function of just the parameter $\alpha$  

$$
\Delta y(\tau)=\Upsilon(\alpha)\Upsilon_{b}(\alpha)^{-1}\Delta y b_{t}(\tau)
$$  

we can then compute an estimate for $\alpha$ by solving,  

$$
m i n_{\alpha}\parallel\Upsilon(\alpha)\Upsilon_{b}(\alpha)^{-1}-\hat{\beta}\parallel
$$  

where $\Vert\Vert$ stands for the L2 norm and $\hat{\beta}$ is the ordinary least square estimate of regressing $\Delta y(\tau)$ onto $\Delta y b_{t}(\tau)$ , namely,  

$$
\hat{\beta}=(\Delta y b^{\prime}\Delta y b)^{-1}\Delta y b^{\prime}\Delta y
$$  

Figure 9.5 in the text shows the estimated OLS parameters of regressing yield changes at different maturities on the changes in the two- and 10-year yield. It also shows the values of the model slopes $\Upsilon(\alpha)\Upsilon_{b}(\alpha)^{-1}$ evaluated at the optimal solution of (A9.20). The parameter $\alpha$ allows one to examine the impact of a change in the factors $r_{t},m_{t},l_{t}$ on the instantaneous forward rates and yields. This allows a clear interpretation of each of the factors: the medium rate $m_{t}$ has maximum impact around the 2y to 3y maturities; hence it can be interpreted as a monetary policy factor (as has been argued in the text). On the other hand, the long factor exhibits maximum impact around the 7y forward maturity (and 15y for zero yield maturity).  

Armed with the estimated parameter $\hat{\alpha}$ that solves (A9.20), we proceed to estimate the vector $\sigma$ that minimizes the distance between model implied. yield volatilities and realized volatilities of constant maturity yields by solving,  

$$
m i n_{\sigma}\parallel\Upsilon_{b}(\hat{\alpha})\Omega(\sigma)\Omega(\sigma)^{\prime}\Upsilon_{b}(\hat{\alpha})^{\prime}-d i a g(\Delta y^{\prime}\Delta y)252/T\parallel
$$  

where $\Delta y$ is a $T\times N$ vector of yield changes for all maturities. Figure 9.6 in. the text shows the fitted zero yield volatilities, versus the volatilities computed directly from observed, constant maturity yield changes..  

Finally, using. $\hat{\alpha}$ that solves (A9.20) and $\hat{\sigma}$ that solves (A9.22), we determine the parameter $\mu$ by minimizing the sum of squares of yield fitting errors, namely,  

$$
m i n_{\mu}\sum_{t=1}^{T}\|Y_{t}-y_{t}\|
$$  

where $y_{t}$ is the vector of model yields for all maturities, at time $t$ . The estimated parameters are shown in Table 9.1 in the text.  

Once the parameter vector $P$ has been estimated, we can solve for the. factors $(m_{t},l_{t})$ to ensure that the model fits exactly the two- and 10-year. forward rates (with tenor one year) on each date. (Filtering methods such as least-squares or Kalman filtering could be employed to extract fitted factors, but we find exact fitting of two points in the curve is preferable in practical trading applications.) We show the fitted factors in Figure 9.8 in the text, along with the 2y forward rate.3.  

Note that in the text we plot the affine function of $l_{t}$ $L(l_{t})$ below rather than $l_{t}$ itself, so that we can interpret the derived long factor as an approximation of the expectation of what the short rate will be in 10 years' time. This is necessary because the extreme persistence (or large half-life, or low mean-reversion parameter) of the factor $l_{t}$ makes the interpretation of the fit-. ted level of $l_{t}$ less intuitive. As you can see, the long factor closely tracks the 10y forward rate from before (the difference between the two is explained by the convexity correction adjustment),  

$$
L(l_{t})=\mu(1-e^{-10\alpha_{l}})+l_{t}e^{-10\alpha_{l}}
$$  

The time series properties of the model can be described by graphing its fitted factors over time. As mentioned already, the short-term rate is set each day to the fed funds target rate, and the medium- and long-term factors  

are set so as to match the model and market two and 10 years forward. Figure 9.8 in the text graphs these empirically recovered market factors from January 2007 to January 2022.4  

# A9.2.3 Implied Risk Premia Calculation  

Denote by $P(t,\tau)$ the price at time $t$ of a zero coupon bond that matures at time $\tau$ and let $p(t,\tau)=l o g(P(t,\tau))$ . Note that here $\tau$ stands for a fixed date in the future, and not a date interval.  

We will assume henceforth that only the risk of the long factor is priced. This is reasonable for the application we have in mind, which will involve extracting expectations about the 10-year maturity and, at that maturity, the loadings of the forward relative to the short and medium rate are negligible.. Now, applying Ito's lemma to the zero coupon bond price as an exponential. affine function of the cascade form factors (A9.9) using (A9.13), and passing. to the true measure, we can write the dynamics of the instantaneous return of a zero coupon bond as follows,.  

$$
\frac{d P(t,\tau)}{P(t,\tau)}=(r_{t}+\lambda_{t}(\tau-t)\Upsilon_{3}(\tau-t,\alpha)\sigma_{l})d t-(\tau-t)\Upsilon(\tau-t,\alpha)\Omega d W_{t}^{*}
$$  

where the loadings vector $\Upsilon(\tau,\alpha)$ was defined in (A9.14), and $\Upsilon_{3}(\tau,\alpha)$ stands for its last element, i.e., the loading of a zero coupon yield with maturity $\tau-t$ on the long rate factor. Also, $\Omega$ was defined in (A9.8) and $\mathbb{W}_{t}^{*}$ stands for the Wiener process under the true measure.  

The term multiplying dt on the right-hand side of (A9.25) has a clear. interpretation: the expected return at time. $t$ of holding $\tau$ maturity zero coupon bond from time $t$ to time $t+d t$ is equal to the riskless rate prevailing at time $t$ , plus a risk-premium term that is equal to the duration of the zero coupon bond (its maturity) times the loading of the yield of a zero coupon bond with maturity $\tau-t$ , times the volatility of the long rate, times the. price of risk prevailing at time t, namely,. $\lambda_{t}$ . We will assume that the price of risk does change over time. We will not specify its dynamics, but we will assume that $\lambda_{t}$ is a very persistent process, so that $E_{t}(\lambda_{t+\Delta t})\approx\lambda_{t}$ for $\Delta t=1$ i.e. one price of risk next-year is expected to be equal to this year's. If we changed measure to the risk-neutral measure, this term would disappear from the right-hand side of (A9.25), that is, the expected instantaneous return of our zero coupon bond would equal the riskless rate.  

Recall as well the definition of the forward rate at time $t$ with maturity $\tau$ and tenor $\Delta\tau:f_{t}(\tau)=(p(t,\tau)-p(t,\tau+\Delta\tau))/\Delta\tau-\mathrm{we}$ will omit the tenor as. an explicitly argument of $f_{t}()$ . Now, consider the following strategy: At time $t$ , buy one zero coupon bond with maturity $\tau+\Delta\tau$ , and simultaneously sell. one zero coupon bond with maturity $\tau$ . First, we claim that the return of this strategy is equal to the forward rate with tenor $\Delta\tau$ prevailing at time $t$ minus the $\Delta\tau$ maturity yield prevailing at time $\tau$ . To see this, denote by. $R_{t}^{\tau}$ the cumulative realized return between time $t$ and time $\tau$ . We then have,  

$$
\begin{array}{r l}&{R_{t}^{\tau}=(\dot{p}(\tau,\tau+\Delta\tau)-\dot{p}(t,\tau+\Delta\tau))-(\dot{p}(\tau,\tau)-\dot{p}(t,\tau))}\ &{\mathrm{~~}=(\dot{p}(t,\tau)-\dot{p}(t,\tau+\Delta\tau))-(0-\dot{p}(t,\tau))}\ &{\mathrm{~~}=(\dot{f}_{t}(\tau)-\dot{f}_{\tau}(\tau))\Delta\tau}\end{array}
$$  

where $f_{\tau}(\tau)$ is equal to the zero coupon yield with maturity $\Delta\tau$ prevailing at time $\tau$ which, for a sufficiently small $\Delta\tau$ , approximately equals the spot rate prevailing at time $\tau$ . Hence, the expected return (under the true measure) of this strategy at time $t$ is equal to the forward rate at time $t$ , minus the. expected short rate at time $\tau$ . Let's keep this result aside for a moment.  

We will now compute the expected return of this strategy (again, under the true measure). Note that the expected return of the long and short side cancel out for entire the holding period except for the segment $(t,t+\Delta\tau)$ and $(\tau-\Delta\tau,\tau)$ , because in the model the risk premia depends on time to maturity only. Applying Ito's lemma to (A9.25), canceling the short rate, integrating and taking expectations, and dismissing the contribution of the segments $(\tau-\Delta\tau,\tau)$ because only the long factor is priced, we get,.  

$$
\begin{array}{l}{{\displaystyle{E_{t}(R_{t}^{\tau})=\int_{0}^{\Delta\tau}\lambda_{t}(\tau+\Delta\tau-t-s)\Upsilon_{3}(\tau+\Delta\tau-t-s,\alpha)\sigma_{l}}~}}\ {{\displaystyle~-\frac{1}{2}(\tau+\Delta\tau-t-s)^{2}\Upsilon(\tau+\Delta\tau-t-s,\alpha)\Omega\Omega^{\prime}\Upsilon(\tau+\Delta\tau-t-s,\alpha)^{\prime}d s~}}\ {{\displaystyle~=\lambda_{t}R P(t,\tau,\Delta\tau)~}}\end{array}
$$  

Note that the expected risk premium (A9.27) is the product of the yet. unknown $\lambda_{t}$ and an amount of risk term. $R P(t,\tau,\Delta\tau)$ that can be easily computed. As we mention in the text, in order to imply $\lambda_{t}$ from the observed forward rates and the parameters of the model, we will assume that there is a maturity $\tau$ such that the (true) expectation of what the short rate will be. at maturity $\tau$ is equal to the (true) expectation of the short rate will be at. any maturity $\tau^{\prime}>\tau$ . With this assumption, we can specialize this reasoning. to two long maturities $\tau^{\prime}>\tau$ , subtract the resulting equations and solve for. the price of risk $\lambda_{t}$ as follows,  

$$
\lambda_{t}=\frac{f_{t}(\tau^{\prime})-f_{t}(\tau)}{R P(t,\tau^{\prime},\Delta\tau)/\Delta\tau-R P(t,\tau,\Delta\tau)/\Delta\tau}
$$  

Armed with an estimate for. $\lambda_{t}$ , we can then take expectations on both. sides of the equation (A9.26) at maturity $\tau-\Delta\tau$ and use (A9.27) to solve for the expected rate for a long enough maturity $\tau-\Delta\tau$ . We finally get,.  

$$
E_{t}(r_{\tau})=f_{t}(\tau)-\lambda_{t}R P(t,\tau,\Delta\tau)
$$  

To get an intuition for (A9.29), say that the price of risk $\lambda_{t}$ that we solved before is 0.09. The loading of the 10-year zero coupon bond yield on the long factor is 0.7, and the volatility of the long factor is about 100 basis points, then the 10-year risk premium would be approximately $0.09\times0.01\times10\times$ $0.7=63\mathrm{bps}$ . The convexity advantage term for the 10-year rate is about 24bps. These numbers are very close to the ones obtained by evaluating the model at estimated parameters, and 0.09 is the average price of risk in the sample.5 If we assume that the 10-year forward rate is $3\%$ , the implied expected one-year rate, nine years rate under the true measure would then be $0.03+0.0024-0.0063=2.61\%$  

We computed the price of risk in the manner described already for using the 14- and 15-year forwards to extract $\uplambda$ for every day in our sample, and then using this estimate to imply the expectation of the 10-year rate using the 10-year forward rate. Results are not sensitive to using other, longer maturities.  

The implied 10-year rate expectation computed in this manner is plotted in the text against an estimate of the long run expected short rate obtained. outside the model, just by just adding the real rate forecast produced by the Cleveland Fed, to a measure of long run inflation, which we took as the average of the 10-year inflation rate forecast produced by the Cleveland Fed, the 10-year forecast produced by the ATsIX model of the Philadelphia Fed,. and an estimate of trend inflation obtained with a simple exponential moving. average rule with a decay parameter of 0.987, a value used elsewhere in the. literature.6 Other procedures to assess long rate expectations are possible. (for example, the Survey of Market Participants conducted by the New York Fed several times a year, or the long-standing Bluechip Financial Forecast survey).  

# A11.1 FORWARD DROP APPROXIMATELY EQUALS CASH CARRY  

Define the following notation, all for 100 face amount of a bond:  

$p_{0}$ : flat price for spot settlement : $c$ : annual coupon payment : $d_{1}$ : number of days from spot settlement to the coupon payment date $d_{2}$ : number of days from the coupon payment date to forward settlement. $d=d_{1}+d_{2}$ : number of days from spot to forward settlement. $A I_{0},A I_{d}$ : accrued interest as of spot and forward settlements,. respectively : $r{:}$ repo rate from spot to forward settlement. : $p_{0}(d)$ : flat price for forward settlement  

With this notation, the forward price of the bond, based on the discussion in the text, can be written as,.  

$$
\begin{array}{c}{{\displaystyle{p_{0}(d)=\left[(p_{0}+A I_{0})\left(1+\frac{r d_{1}}{360}\right)-\frac{c}{2}\right]\left(1+\frac{r d_{2}}{360}\right)-A I_{d}}}}\ {{\displaystyle{p_{0}-p_{0}(d)\approx\frac{c}{2}+A I_{d}-A I_{0}-(p_{0}+A I_{0})\frac{r d}{360}}}}\end{array}
$$  

Equation (A11.2) follows from Equation (A11.1) by dropping terms that are small, because they represent interest-on-interest. In particular, the following approximations are made: $(1+r d_{1}/360)(1+r d_{2}/360)\approx(1+r d/360)$ and $(c/2)(1+r d_{2}/360)\approx c/2$  

# A11.2 FORWARD VERSUS FUTURES PRICES IN A TERM STRUCTURE MODEL  

This section highlights the differences between pricing forward and futures contracts in a term structure model. To focus on this difference, it is assumed here that the futures contract has one delivery date and one deliverable bond and that its conversion factor is one. Section A11.4 discusses the pricing of. delivery options in a term structure model. Also, for simplicity, it is assumed. here that there are no intermediate coupon dates between the spot and forward settlement dates.  

Using the methodology of Chapter 7, begin with a recombining, bi-. nomial tree with three dates, labeled 0, 1, and 2, where the forward and futures contracts expire on date 2. Set the following notation:.  

$r_{0},r_{1}^{u}$ , and $r_{1}^{d}$ : the initial one-period rate, and the one-period rates on date 1, in the up and down states, respectively.   
$\textbf{\em P}_{0},P_{2}^{u u},P_{2}^{u d}$ and $P_{2}^{d d}$ : the initial full price of the underlying bond, and the date-2 full prices in the "up-up," "up-down," and "down-down" states, respectively..   
$\mathbf{\Phi}^{\overline{{\mathbf{\alpha}}}}\mu_{0},p_{2}^{u u},p_{2}^{u d}$ and $\dot{p}_{2}^{d d}$ : fat pries at the indicated dates and states..   
: $P_{0}(2)$ : the initial full forward price..   
: $p_{0}(2)$ : the initial flat forward price.. $F_{0},F_{1}^{u}, $ $F_{1}^{d}$ : the initial futures price, and the date-1 futures prices in the up and down states, respectively..   
$\equiv q,1-q$ : the risk-neutral transition probabilities on all dates to move up and down from the current state, respectively.  

By the definition of a risk-neutral tree, the initial price of the bond can be computed as,  

$$
P_{0}=\frac{1}{1+r_{0}}\left[q\times\frac{q P_{2}^{u u}+(1-q)P_{2}^{u d}}{1+r_{1}^{u}}+(1-q)\times\frac{q P_{2}^{u d}+(1-q)P_{2}^{d d}}{1+r_{1}^{d}}\right]
$$  

or, rearranging terms,  

$$
\begin{array}{l}{{P_{0}=q^{2}{\displaystyle{\frac{P_{2}^{u d}}{(1+r_{0})(1+r_{1}^{u})}}}+q(1-q){\displaystyle{\frac{P_{2}^{u d}}{(1+r_{0})(1+r_{1}^{u})}}}}}\ {{\displaystyle{\quad+q(1-q){\displaystyle{\frac{P_{2}^{u d}}{(1+r_{0})(1+r_{1}^{d})}}}}+(1-q)^{2}{\displaystyle{\frac{P_{2}^{d d}}{(1+r_{0})(1+r_{1}^{d})}}}}}\end{array}
$$  

Each term of Equation (A11.4) is the probability of a particular path through the tree times the discounted value of the bond price at the end of that path, where discounting is done using the short-term rates along. the path. Taking all terms together, therefore, $P_{0}$ is the expected discounted bond price. More generally, then, letting $_n$ be the number of periods, $P_{n}$ the random full price of the bond at period $_n$ , and $r_{i}$ the random short-term rate over period $i$ to $i+1$  

$$
P_{0}=E\left[\frac{P_{n}}{\prod_{i=0}^{n-1}(1+r_{i})}\right]
$$  

The discount factor to period. $n,d(n)$ , is just a special case of (A11.5) when the terminal price equals one in all states. Hence,  

$$
d(n)=E\left[\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}\right]
$$  

Following the discussion in the text, the forward full price of the bond is just the future value, to the forward delivery date, of the full spot price of the bond. Therefore, using Equations (A11.5) and (A11.6),  

$$
P_{0}^{f w d}=\frac{P_{0}}{d(n)}
$$  

Turning to the futures price, start again with the recombining, risk-. neutral binomial tree. At expiration on date 2, the futures price equals the flat bond price. (At contract expiration, the bond is delivered at the futures. price plus accrued interest.) In the up state of date 1, the futures price is $F_{1}^{u}$ , which means that the daily settlement payment for a long position of one contract on date 2 is ${p}_{2}^{u u}-F_{1}^{u}$ in the up-up state and $p_{2}^{u d}-F_{1}^{u}$ in the up-down state. But because the value of a futures contract initiated at any. date is zero, the expected discounted value of the daily settlement payments. from the date 1 up state must be zero. Hence,  

$$
\frac{q(p_{2}^{u u}-F_{1}^{u})+(1-q)(p_{2}^{u d}-F_{1}^{u})}{1+r_{1}^{u}}=0
$$  

And, solving for the futures price,  

$$
F_{1}^{u}=q{p}_{2}^{u u}+(1-q)p_{2}^{u d}
$$  

Analogously, the futures price in the date 1 down state is,  

$$
F_{1}^{d}=q{p}_{2}^{u d}+(1-q)p_{2}^{d d}
$$  

On date 0, the futures price is $F_{0}$ , and the expected discounted value of. the date 1 settlement payment must be zero. Hence,  

$$
\frac{q(F_{1}^{u}-F_{0})+(1-q)(F_{1}^{d}-F_{0})}{1+r_{0}}=0
$$  

Or,  

$$
F_{0}=q F_{1}^{u}+(1-q)F_{1}^{d}
$$  

Finally, substituting Equations (A11.9) and (A11.10) into (A11.12),  

$$
F_{0}=q^{2}p_{2}^{u u}+2q(1-q)p_{2}^{u d}+(1-q)^{2}p_{2}^{d d}
$$  

Hence, in a risk-neutral tree, the futures price is the expected value of the bond price on the contract expiration date. More generally,.  

$$
F_{0}=E[\phi_{n}]
$$  

This result is proved more formally in Section A16.5.  

# A11.3 THE FUTURES-FORWARD DIFFERENCE  

Recall that for any two random variables, $X$ and $Y$ , their covariance can be written as,  

$$
\operatorname{Co}\nu(X,Y)=E[X Y]-E[X]E[Y]
$$  

Applying this to two random variables from the previous section, namely, $P_{n}$ and $\bar{\Pi}_{i=0}^{n-1}(1+r_{i})$  

$$
\begin{array}{r}{\begin{array}{c}{C o\nu\left(P_{n},\displaystyle{\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}}\right)=E\left[\displaystyle{\frac{P_{n}}{\prod_{i=0}^{n-1}(1+r_{i})}}\right]}\ {-E[P_{n}]E\left[\displaystyle{\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}}\right]}\end{array}}\end{array}
$$  

Let $A I_{n}$ be the accrued interest on the bond as of date $_n$ . Because accrued interest is not a random variable, $E[P_{n}]=E[\Tilde{P}_{n}]+A I_{n}$ . Next, substitute the definitions of. $P_{0},d(n)$ , and $F_{0}$ from Equations (A11.5), (A11.6), and. (A11.14) into Equation (A11.16) to see that,.  

$$
\mathrm{Co}\nu\left(P_{n},\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}\right)=P_{0}-(F_{0}+A I_{n})d(n)
$$  

Rearranging terms, substituting in the forward price from Equation (A11.7), and recognizing that phwd $P_{0}^{f w d}=\bar{p}_{0}^{\bar{f}w d}+A I_{n}$  

$$
\begin{array}{r l r}{\displaystyle{F_{0}+A I_{n}=\frac{P_{0}}{d(n)}-\frac{1}{d(n)}C o\nu\left(P_{n},\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}\right)}}\ {\displaystyle{=P_{0}^{f w d}-\frac{1}{d(n)}C o\nu\left(P_{n},\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}\right)}}\ {\displaystyle{F_{0}=\hat{p}_{0}^{f w d}-\frac{1}{d(n)}C o\nu\left(P_{n},\frac{1}{\prod_{i=0}^{n-1}(1+r_{i})}\right)}}\end{array}
$$  

Finally, because bond prices are negatively correlated with interest rates, the covariance term in Equation (A11.18) is negative and, therefore,  

$$
F_{0}<p_{0}^{f w d}
$$  

The futures price is less than the forward price.  

# A11.4  FUTURES DELIVERY OPTIONS IN A TERM STRUCTURE MODEL  

Having set up a term structure model in the form of a tree, the quality option. can be priced as follows. Start at the delivery date. At each node, compute the ratio of the price to conversion factor for each deliverable bond. Find the. bond with the minimum ratio and set the futures price equal to that ratio.. Then, given these terminal values of the futures price, prices on earlier dates can be computed along the lines described in Section A11.2. In the case of the timing, end-of-month, and wild-card options, which are American-style options exercisable by the short, the futures price at each node in the tree. is the minimum of the futures price with the option exercised and with the. option not exercised.  

The previous paragraph assumes that the prices of the bonds are avail-. able on the tree as of the last delivery date. These bond prices can be computed in one of two ways. If a model with a closed-form solution for spot rates is being used, then these rates can be used to compute the bond prices as needed. Otherwise, the tree has to be extended to the maturity date of the longest bond in the basket and bond prices have to be computed using. the usual tree methodology. The first solution is faster and less subject to numerical error, but a model with a closed-form solution may or may not be suitable for the problem at hand..  

Arbitrage-free pricing models usually assume that some set of securities is fairly priced. In the case of futures, the standard assumption is that the forward prices of all bonds in the deliverable basket are fair. Technically, this calibration can be accomplished by assigning a spread to each bond such that its forward price in the model matches the forward price in the market. The assumption that bond prices are fair is in the spirit of pricing the futures relative to cash. Another approach can be used to decide whether the underlying bonds are fairly priced or not.  

Term structure models commonly used for pricing futures fall into two. main categories. First are one- or two-factor short-rate models along the lines of those described in Chapters 7-9. These models are relatively easy to. implement and, for the most part, flexible enough to capture the yield curve dynamics driving futures prices. With only one or two factors, however, these. models cannot capture the idiosyncratic price movements of any deliverable bond relative to another.  

The second type of model allows for a richer set of relative price movements across bonds in the deliverable basket. These models essentially allow each bond to follow its own price or yield process. There are costs to this flexibility, however. First, ensuring that these models are arbitrage free takes some effort. Second, the user must specify the parameters that describe the stochastic behavior of all bond prices in the basket, for example, a volatility for each of the bonds in the basket along with correlations between each pair of bonds.  

Futures traders often describe their models in terms of the beta of each bond in the basket relative to a benchmark bond in the basket. The beta. of a bond represents the expected change in yield of that bond given a one-basis-point change in the yield of the benchmark. A bond with a beta of 1.02, for example, implies that the bond's yield is assumed to change $2\%$ more than the yield of the benchmark bond. The beta of a particular bond. can be thought of as the coefficient from a regression of changes in its yield on changes in the benchmark's yield. Note that in a one-factor model the. beta of a bond is simply the ratio of the volatility of that bond yield to the volatility of the benchmark's yield.  

# Short-Term Rates and Their Derivatives  

ing of forward and futures rates and the futures-forward rate difference in term structure models. All expectations here are also with respect to some risk-neutral or pricing probabilities.  

The first step in this Appendix is to show that the futures rate with respect to a term rate, like a Euribor futures rate in the text, is greater than the corresponding forward term rate.  

The $\beta$ year rate, $t$ years forward,e $r_{t}^{f w d}$ , is the rate that equate the present value at time $t$ of receiving a unit of currency at time $t+\beta$ with the price of -year zero coupon bond, -years forward, p. Usig continuously compounded rates,  

$$
p_{0}^{f w d}(t)=e^{-\beta r_{t}^{f w d}}
$$  

Furthermore, by Equation (A11.19),  

$$
p_{0}^{f w d}(t)=e^{-\beta r_{t}^{f w d}}>F_{0}
$$  

where $F_{0}$ is the futures price of that zero coupon bond.  

Let $r_{t}$ be the realized $\beta$ -year rate at time $t$ . Then, by definition, the $\beta$ -year zero coupon bond price at that time, $\mathbf{}p_{t}$ , is,  

$$
p_{t}=e^{-\beta r_{t}}
$$  

and, by Equation (A11.14),  

$$
F_{0}=E[\boldsymbol{p}_{t}]=E[e^{-\beta\boldsymbol{r}_{t}}]
$$  

Because of daily settlement payments of futures contracts, and following the same argument as in Appendix A11.2, which leads to Equation (A11.14),  

it can be hown tat the furures ate, $r_{t}^{f u t}$ coresponding to the $\beta$ ycar zero coupon bond rate, is simply today's expectation of that bond rate at time $t$  

$$
r_{t}^{f u t}=E[r_{t}]
$$  

By Jensen's inequality and Equation (A12.5),  

$$
E[e^{-\beta r_{t}}]>e^{-\beta E[r_{t}]}=e^{-\beta r_{t}^{\mathit{f u t}}}
$$  

Stringing together Equations (A12.2), (A12.4), and (A12.6),  

$$
e^{-\beta r_{t}^{f w d}}>F_{0}=E[e^{-\beta r_{t}}]>e^{-\beta r_{t}^{f u t}}
$$  

Finally, focusing on the leftmost and rightmost terms of Equation (A12.7),  

$$
r_{t}^{f u t}>r_{t}^{f w d}
$$  

as was to be proved.  

The next step in this appendix is to show that the futures rate with respect to an average rate, like a one-month SOFR (Secured Overnight Financing Rate) futures rate or a fed funds futures rate, is greater than the futures rate with respect to a term rate. This fact, combined with the result just proved, implies that futures rates with respect to average rates are also greater than the corresponding forward rates.  

Let $R(t,t+\beta)$ be the integral of the continuously compounded overnight rates from $t$ to $t+\beta$ , so that the average rate is $R(t,t+\beta)/\beta$ . Once again, because of the daily settlement of futures contracts, today's futures rate on the average rate, $A_{t}^{f u t}$ , is today' expectation of the average at time $t$  

$$
A_{t}^{f u t}=E\left[\frac{1}{\beta}R(t,t+\beta)\right]
$$  

By definition of the $\beta$ -year term rate at time $t,r_{t}$  

$$
e^{-\beta r_{t}}=E_{t}[e^{-R(t,t+\beta)}]
$$  

where $E_{t}[\cdot]$ gives the expectation as of time $t$ . Applying Jensen's inequality. to (A12.10) and rearranging terms,  

$$
\begin{array}{r l r}{\lefteqn{e^{-\beta r_{t}}>e^{-E_{t}[R(t,t+\beta)]}}}\ &{}&{r_{t}<\frac{1}{\beta}E_{t}[R(t,t+\beta)]}\ &{}&{r_{t}^{f u t}<\frac{1}{\beta}E[R(t,t+\beta)]=A_{t}^{f u t}}\end{array}
$$  

where the third equation takes expectations of the second as of today, and the last equality follows from Equation (A12.9). Equation (A12.11) says that the futures rate on the average is greater than the futures rate on the term rates, as was to be proved.  

The final step in this appendix is to show that the futures rate with. respect to a compounded rate, like a three-month SOFR futures rate, is greater than the futures rate with respect to an average rate. Once again,. because of daily settlement, today's futures rate on a compounded rate, Cfut, is the expectation of that compounded rate in the future. Mathematically, in a continuously compounded version of Equation (12.10) in the text,.  

$$
C_{t}^{f u t}=\frac{1}{\beta}(E[e^{R(t,t+\beta)}]-1)
$$  

By Jensen's inequality and the properties of the exponential function,  

$$
E[e^{R(t,t+\beta)}]-1>e^{E[R(t,t+\beta)]}-1>E[R(t,t+\beta)]
$$  

Finally, combining Equations (A12.12), (A12.13), and the definition of the futures rate on the average in (A12.9),  

$$
\displaystyle{C_{t}^{f u t}=\frac{1}{\beta}(E[e^{R(t,t+\beta)}]-1)>\frac{1}{\beta}E[R(t,t+\beta)]=A_{t}^{f u t}}
$$  

Hence, as was to be proved, the futures rate on a compounded rate is greater than the futures on an average rate.  

To summarize, the financial insight is that, because of daily settlement, the forward price on a zero coupon bond is greater than the futures price on. that bond. This result, from Chapter 11, plus a convexity effect in moving from price to rate, shows that the futures rate with respect to a term rate exceeds the corresponding forward term rate. Then, accounting for the convexity effects of moving to a futures rate with respect to an average rate or with respect to a compounded rate, these futures rates exceed the futures rate with respect to the term rate. The bottom line, then, is that all of the futures rates discussed in the chapter exceed the corresponding term forward rate..  

# Interest Rate Swaps  

# A13.1PRICING A EURIBOR SWAP AS OF FEBRUARY 24, 2022  

This section prices a two-year fixed-for-floating swap, where the floating rate is three-month Euribor. The inputs are the term structure of STR OIS given in Table A13.1, the two-year Euribor swap rate of. $0.078\%$ , and the two-year STR-Euribor basis swap spread of. $0.138\%$ . All cash flows are. assumed to follow the actual/360 convention, and all of the relevant dates are assumed to be business days..  

The OIS rates in the fourth column of the table are observed in the market. The discount factors are calculated by setting the present value of the fixed payments on each OIS (including the fictional notional amount at maturity) equal to par, which is the value of the floating legs that pay compounded daily STR. Letting $d(t)$ denote the discount factor for $t$ years, the equations determining the discount factors, along the same lines as for SOFR swaps explained in Chapter 2, are the following,.  

TABLE A13.1 STR OIS Rates as of February 24, 2022.   


<html><body><table><tr><td>Term (years)</td><td>Term (date)</td><td>Term (days)</td><td>Rate (%)</td><td>Discount Factor</td><td>FwdRate (%)</td></tr><tr><td>0.25</td><td>05/24/2022</td><td>89</td><td>-0.5695</td><td>1.0014099</td><td>-0.1408</td></tr><tr><td>0.50</td><td>08/24/2022</td><td>181</td><td>-0.5580</td><td>1.0028134</td><td>-0.1400</td></tr><tr><td>0.75</td><td>11/24/2022</td><td>273</td><td>-0.5110</td><td>1.0038902</td><td>-0.1073</td></tr><tr><td>1.00</td><td>02/24/2023</td><td>365</td><td>-0.4380</td><td>1.0044606</td><td>-0.0568</td></tr><tr><td>1.25</td><td>05/24/2023</td><td>454</td><td>-0.3380</td><td>1.0042784</td><td>0.1081</td></tr><tr><td>1.50</td><td>08/24/2023</td><td>546</td><td>-0.2330</td><td>1.0035455</td><td>0.0730</td></tr><tr><td>1.75</td><td>11/24/2023</td><td>638</td><td>-0.1400</td><td>1.0024888</td><td>0.1054</td></tr><tr><td>2.00</td><td>02/24/2024</td><td>730</td><td>-0.0600</td><td>1.0012201</td><td>0.1267</td></tr></table></body></html>  

$$
{\begin{array}{r l}&{1=(1-0.6595\times8.993736)d\Omega(2.25)}\ &{1=(1-0.5980\times18.136)\omega(1.000)(1.50)}\ &{1=(1-0.51100\times12.73)(3.60)d(1.75)}\ &{1=(1-0.4380\times36.36)(3.00)d(1.00)}\ &{1=-0.3390\times8.897360\times40.25)}\ &{1+(1-0.38095\times14.45)(1.25)}\ &{1=-0.23395\times18.1360\times40.501}\ &{1+(1-0.23309\times8.(54.6-18.1))(3.60)d(1.50)}\ &{1=-0.1400\times8.273/360\times40.75)}\ &{1+(1-0.14005\times10.3273)(8.01(1.75))}\ &{1+(1-0.14005\times(6.33-273))(3.60)d(1.75)}\ &{1=-0.06000\times36.53/360\times41.(1.00)}\ &{1+(1-0.06009\times8.05)(3.60)d(2.00)}\end{array}}
$$  

Solving this set of equations gives the discount factors in Table A13.1. The resulting forward rates are shown in the table as well but are not. needed for the remaining calculations. In any case, with these discount factors, the two-year Euribor swap rate of. $0.078\%$ and the two-year STR versus three-month Euribor basis swap spread of. $0.138\%$ are related by equating the present value of the fixed side of the Euribor swap payments (including the fictional notional amount) to one (i.e., the value of floating STR, including the fictional notional amount) plus the present value of the basis swap spread payments. Mathematically,  

$$
\begin{array}{r}{0.078\%\times365/360\times d(1.00)+(1+0.078\times(730-365)/360)\times d(2.00)}\ {=1+0.138\%\times89/360\times d(0.25)}\ {+0.138\%\times(181-89)/360\times d(0.50)+\cdot\cdot\cdot}\ {+0.138\%\times(730-638)/360\times d(2.00)}\ {(\mathrm{A}13.2)}\end{array}
$$  

Note that Equation (A13.2) is the pricing condition. Given the $0.078\%$ swap rate, it can be used to solve for the $0.138\%$ basis swap spread. Or, conversely, given the $0.138\%$ basis swap spread, it can be used to solve for the $0.078\%$ swap rate.  

# A13.2 TWO-CURVE PRICING  

For the purposes of this section, assume for simplicity that payments are annual at times $t=1,\ldots,T$ . For ease of exposition, say that the risk-free rate index is STR and that the non-risk-free rate index is Euribor. Given a set of discount factors, $d(t)$ , derived from STR OIS; a set of Euribor swap rates, $c(t)$ ; and STR versus Euribor basis swap spreads, $x(t)$ , the fair pricing conditions for the Euribor swaps, discussed in the text and the previous section are, for every $t$  

$$
c(t)\sum_{s=1}^{t}d(s)+d(t)=1+x(t)\sum_{s=1}^{t}d(s)
$$  

Now define a set of adjusted Euribor forward rates, $L^{\prime}(t)$ , such that the present values of the floating legs of the Euribor swaps equal their correct values, which are given by the right-hand side of (A13.3),  

$$
\sum_{s=1}^{t}L^{\prime}(s)d(s)+(1+L^{\prime}(t))d(t)=1+x(t)\sum_{s=1}^{t}d(s)
$$  

Given the basis swap spreads, Equation (A13.4) could be used to solve for all of the adjusted Euribor forward rates, one at a time, starting with $t=1$ and continuing through to. $t=T$ .These $L^{\prime}(t)$ could then be used to price. payments that depend on Euribor. However, noticing that the right-hand sides of Equations (A13.3) and (A13.4) are the same, these two equations. can be combined,  

$$
c(t)\sum_{s=1}^{t}d(s)+d(t)=\sum_{s=1}^{t}L^{\prime}(s)d(s)+(1+L^{\prime}(t))d(t)
$$  

But given all of the swap rates,. $c(t)$ , Equation (A13.5) can be used iteratively to solve for the $L^{\prime}(t)$ . In other words, so long as the Euribor swaps are. priced fairly relative to STR OIS, there is no need to know the basis swap spreads.  

In summary, then, the two-curve methodology for pricing Euribor swaps is as follows. First, solve for the adjusted forward rates, $L^{\prime}(t)$ , as just described. Second, project those adjusted forward rates as future Euribor floating rates to set floating-leg payments. Third, discount both fixed- and floating-leg payments using the STR discount factors.  

# Corporate Debt and Credit Default Swaps  

# A14.1 CUMULATIVE DEFAULT AND SURVIVAL RATES  

Proposition: If the hazard rate is constant at $\uplambda$ , then the cumulative survival probability to time $t$ $C S(t)$ , is $e^{-\lambda t}$ , and the cumulative default probability, CD(t), is 1 - e-t.  

Proof: The probability of no default to time $t+\Delta t$ $C S(t+\Delta t)$ , is the probability that there is no default to time $t$ and no default from then to time $t+\Delta t$ . Mathematically,  

$$
\begin{array}{c}{\mathrm{C}S(t+\Delta t)=\mathrm{C}S(t)\times(1-\lambda\Delta t)}\ {\lambda{\mathrm{C}S}(t)=-\frac{\mathrm{C}S(t+\Delta t)-\mathrm{C}S(t)}{\Delta t}}\end{array}
$$  

Taking the limit of the right-hand side of (A14.2) as $\Delta t$ approaches zero is the derivative of $C S(t)$ , denoted $C S^{\prime}(t)$ . Therefore,  

$$
\begin{array}{c}{{\lambda C S(t)=-C S^{\prime}(t)}}\ {{C S(t)=e^{-\lambda t}}}\end{array}
$$  

where Equation (A14.4) is the solution to Equation (A14.3). The cumulative default probability is just one minus the cumulative survival probability,. which gives CD(t) = 1 - e-At .  

Fixed Income Securities: Tools for Today's Markets, Fourth Edition. Bruce Tuckman and Angel 505 Serrat $\copyright$ 2022 Bruce Tuckman and Angel Serrat. Published 2022 by John Wiley & Sons, Inc..  

# A14.2 UPFRONT AMOUNTS  

Continue with the notation of the previous section, and add the following:  

$s^{C D S}$ : CDS spread cCDS: CDS coupon : $T$ : maturity of the CDS, in years. n: number of CDS premium payments per year $\overline{{\overline{{\mathbf{\alpha}}}}}t_{i}$ : time of CDS premium payment $\quad;i=1,\ldots,n T_{\cdot}$ with $t_{0}\equiv0$ : $d(t_{i})$ : discount factor at time. $t_{i}$ , at risk-free or benchmark rates $\texttt{\textbf{n}}$ : recovery rate UF: upfront amount  

Then, following the logic described in the text, with the detail that premium payments follow the actual/360 day-count convention, the expected discounted value of the fee leg, $V^{f e e}$ , is,  

$$
\begin{array}{l}{{\displaystyle V^{f e e}=s^{C D S}\sum_{i=1}^{n T}\frac{t_{i}-t_{i-1}}{360}C S(t_{i})d(t_{i})}}\ {{\displaystyle~+\frac{1}{2}s^{C D S}\sum_{i=1}^{n T}\frac{t_{i}-t_{i-1}}{360}[C S(t_{i-1})-C S(t_{i})]d(t_{i})}}\end{array}
$$  

The value of the contingent leg, $V^{c o n t}$ , again following the logic described in the text, is,.  

$$
V^{C o n t}=(1-R)\sum_{i=1}^{n T}[C S(t_{i-1})-C S(t_{i})]d(t_{i})
$$  

A CDS with a premium of $s^{C D S}$ is fair if the hazard rate is such that. the values of the fee and contingent legs, as given in Equations (A14.5) and (A14.6), are equal.  

The upfront amount, following the logic of the text, equals the expected. discount value of paying the CDS coupon as a premium payment rather than the CDS spread. Essentially, the upfront amount is computed like the fee leg, with $-(c^{\mathrm{{CDS}}}-s^{\mathrm{{CDS}}})$ or $(s^{\dot{C}\dot{D}S}-c^{\dot{C}D S})$ replacing $s^{C D S}$ . Hence,  

$$
\begin{array}{l}{{\displaystyle U F=(s^{C D S}-c^{C D S})\sum_{i=1}^{n T}\frac{t_{i}-t_{i-1}}{360}C S(t_{i})d(t_{i})}}\ {{\displaystyle~+\frac{1}{2}(s^{C D S}-c^{C D S})\sum_{i=1}^{n T}\frac{t_{i}-t_{i-1}}{360}[C S(t_{i-1})-C S(t_{i})]d(t_{i})}}\end{array}
$$  

# A14.3 AN APPROXIMATION FOR CDS SPREADS  

For the purposes of this section, assume that premium payments of the CDS are all $\Delta t$ years apart, that is, $t_{i}-t_{i-1}=\Delta t$ for all $t_{i}$ . Substituting that relationship into Equations (A14.5) and (A14.6) and setting the two equations equal, gives the following,  

$$
\begin{array}{c}{{s^{\scriptscriptstyle{C D S}}\Delta t\displaystyle\sum_{i=1}^{n T}C S(t_{i})d(t_{i})+\frac{1}{2}s^{\scriptscriptstyle{C D S}}\Delta t\displaystyle\sum_{i=1}^{n T}[C S(t_{i-1})-C S(t_{i})]d(t_{i})}}\ {{=(1-R)\displaystyle\sum_{i=1}^{n T}[C S(t_{i-1})-C S(t_{i})]d(t_{i})}}\end{array}
$$  

Substituting in from Equation (A14.4), each term of (A14.8) can be simplified as follows,  

$$
\begin{array}{l}{{0=s^{C D S}\Delta t e^{-\lambda t_{i}}}}\ {{\mathrm{~}+\displaystyle{\frac{1}{2}}s^{C D S}\Delta t[e^{-\lambda t_{i-1}}-e^{-\lambda t_{i}}]}}\ {{\mathrm{~}-(1-R)[e^{-\lambda t_{i-1}}-e^{-\lambda t_{i}}]}}\end{array}
$$  

Furthermore, because $t_{i}-t_{i-1}=\Delta t$ for all $t_{i}$ , it is easy to show that,. if Equation (A14.9) holds for. $t_{i}$ , then it also holds for $t_{i+1}$ . Hence, in this. special case, $s^{C D S}$ can be solved from any one date. Proceeding then from Equation (A14.9), multiply through by. $e^{-\lambda t_{i}}$ and simplify to see that,  

$$
\begin{array}{c}{{s^{C D S}\Delta t\left[1+\displaystyle\frac{1}{2}(e^{\lambda\Delta t}-1)\right]=(1-R)[e^{\lambda\Delta t}-1]}}\ {{{}~}}\ {{s^{C D S}\Delta t\displaystyle\frac{[1+e^{\lambda\Delta t}]}{2}=(1-R)[e^{\lambda\Delta t}-1]}}\ {{{}~}}\ {{s^{C D S}=(1-R)\left[\displaystyle\frac{2}{\Delta t}\displaystyle\frac{e^{\lambda\Delta t}-1}{e^{\lambda\Delta t}+1}\right]}}\end{array}
$$  

Finally, take the limit as $\Delta t$ approaches zero of the terms in the hard bracket on the right-hand side of (A14.12) to obtain,  

$$
\begin{array}{r}{s^{C D S}\approx\lambda(1-R)}\end{array}
$$  

# A14.4 CDS-EQUIVALENT BOND SPREADS  

Following the logic of the text and this appendix, the expected discounted. value of a bond's coupons can be computed along the lines of the fee leg of a CDS. Similarly, the expected discounted value of a bond's principal payment.  

can be computed along the lines of the contingent leg, except that the payment from the bond upon default is $R$ times the principal amount, while the payment due to the buyer of protection upon default is. $1-R$ times the principal amount. Therefore, using Equations (A14.5) and (A14.6) - simplified here to assume that coupon payments are exactly one-half years apart - the. price of a bond,. $P$ , with a coupon rate,. $c$ given a hazard rate, is given by,.  

$$
\begin{array}{l}{{\displaystyle{\cal P}=\frac{c}{2}\sum_{i=1}^{n T}C S(t_{i})d(t_{i})}}\ {{\displaystyle~+\frac{c}{2}\sum_{i=1}^{n T}[{\mathrm{CS}}(t_{i-1})-{\mathrm{CS}}(t_{i})]d(t_{i})}]}\ {{\displaystyle~+R\sum_{i=1}^{n T}[{\mathrm{CS}}(t_{i-1})-{\mathrm{CS}}(t_{i})]d(t_{i})}}\end{array}
$$  

To solve for the CDS-equivalent bond spread, find the hazard rate that solves Equation (A14.14). Then, using that hazard rate, find the $s^{C D S}$ that sets the fee leg in Equation (A14.5) equal to the contingent leg in Equation (A14.6).  

# A14.5 BOND SPREAD WITH MARKET RECOVERY  

From the definition of bond spread, if the bond does not default (and rates do not change), then the return on the bond equals the risk-free or benchmark rate, $r$ , plus the spread. If the bond defaults and recovers $R^{m}$ of its market price, then the return over the moment of default is $(R^{m}P-P)/P$ or $(R^{m}-1)$ Therefore, over a short time interval $d t$ years, over which the probability of no default and default are $1-\lambda d t$ and $\uplambda\mathop{d t}$ , respectively, the expected return on the bond is,  

$$
\begin{array}{r l}&{(1-\lambda d t)\times(r+s)d t+\lambda d t\times(R^{m}-1)}\ &{\approx(r+s)d t+\lambda d t(R^{m}-1)}\end{array}
$$  

where the approximation follows from ignoring the very small terms, that is, those that are multiplied by. $(d t)^{2}$  

Assuming that investors are risk neutral or that the hazard rate is a risk-neutral pricing rate, investors are indifferent between buying a corporate bond and buying a bond without default risk if the expected return of the former, given in Equation (A14.15), is equal to the risk-free rate. Mathematically, then,  

$$
\begin{array}{c}{{r d t=(r+s)d t+\lambda d t(R^{m}-1)}}\ {{s=\lambda(1-R^{m})}}\end{array}
$$  

# Mortgages and. Mortgage-Backed Securities  

# A15.1 MONTH-END BALANCES  

This section shows that, under the principal amortization schedule described in the text, the balance outstanding at any time equals the present value of the remaining payments at the original mortgage rate. Let $N$ be the term of. the mortgage, in months; let $r$ be the mortgage rate; let $X$ be the monthly payment, and let. $B(i)$ be the balance outstanding at the end of month $i$ $i=0,1,\ldots N$ By definition, as discussed in the text,  

$$
B(0)=X\frac{12}{r}\left[1-\left(1+\frac{r}{12}\right)^{-N}\right]
$$  

If the balance outstanding at the end of month $i$ does equal the present. value of the remaining payments at the rate. $r$ , then,  

$$
\begin{array}{c}{{B(i)=X\displaystyle\frac{12}{r}\left[1-\left(1+\displaystyle\frac{r}{12}\right)^{i-N}\right]}}\ {{{}}}\ {{B(i+1)=X\displaystyle\frac{12}{r}\left[1-\left(1+\displaystyle\frac{r}{12}\right)^{i+1-N}\right]}}\end{array}
$$  

According to the logic of the amortization table, the interest component. of the payment for month $i+1$ is $(r/12)B(i)$ , and the principal component. is $X-(r/12)B(i)$ . Because $B(0)$ is, by definition, the present value of the. remaining payments at the start of the mortgage, this section needs to prove that, for any $i>0$  

$$
B(i)-B(i+1)=X-\frac{r}{12}B(i)
$$  

To prove this, rearrange terms and then substitute for $B(i)$ and $B(i+1)$ from Equations (A15.2) and (A15.3), respectively,  

$$
\begin{array}{r l r}&{}&{\left(1+\displaystyle\frac{r}{12}\right)B(i)-B(i+1)\overset{?}{=}X}\ &{}&{X\displaystyle\frac{12}{r}\left[1+\displaystyle\frac{r}{12}-\left(1+\displaystyle\frac{r}{12}\right)^{i+1-N}-1+\left(1+\displaystyle\frac{r}{12}\right)^{i+1-N}\right]\overset{?}{=}X}\ &{}&{X\displaystyle\frac{12}{r}\left[\displaystyle\frac{r}{12}\right]\overset{?}{=}X}\ &{}&{X=X}\end{array}
$$  

which is clearly true for any parameters of the problem.  

# A15.2 PRICING MBS WITH TERM STRUCTURE MODELS  

This section very briefly discusses three problems that arise in the context. of pricing MBS in term structure models: path dependence, proxies for the mortgage rate, and factors apart from interest rates..  

As for path dependence, the burnout and media effects imply that the value of an MBs depends not only on the current term structure of interest rates, but also on the history of the term structure. Pricing by backward induction, however, described in earlier chapters of the book, does not naturally accommodate path dependence: at any node of a binomial tree, for example, there is no memory of how the interest rate process moved from its current state to that particular node of the tree.  

A popular solution for pricing path-dependent claims is Monte Carlo simulation. To price a security in this framework, in a one-factor setting, proceed as follows. First, generate a large number of paths of interest rates at the frequency and to the horizon desired. For this purpose, paths are generated using a particular risk-neutral process for the short-term rate. Second, calculate the cash flows of the security along each path. In the mortgage context, this would include the security's scheduled payments along with its prepayments. Burnout and the media effect can be implemented in this framework, because each path is available in its entirety as cash flows are calculated. Third, starting at the end of each path, calculate the discounted value of the security's cash flows along each path using the interest rates along that path. Fourth, compute the value of the security as the average of the discounted values across paths.  

To connect Monte Carlo simulation with the pricing approach used elsewhere in the book, recall Equation (A11.5), reproduced here for convenience,  

$$
P_{0}=E\left[\frac{P_{n}}{\prod_{i=0}^{n-1}(1+r_{i})}\right]
$$  

where $r_{i}$ is the short-term rate in period i, $P_{n}$ is the value of a claim in $_n$ periods, and $P_{0}$ is the price of the claim today. In light of the discussion. in this section, the term inside the hard brackets is analogous to the discounted value of a security along one path. The expectation is analogous to the average of those discounted values across paths.  

In the Monte Carlo framework, measures of interest rate sensitivity can be computed by shifting the initial term structure in some manner, repeating the valuation process, and calculating the difference between the initial and shifted prices. As a numerical matter, paths should not be regenerated between the initial and shifted valuations, as that would introduce noise into the sensitivity calculations.  

A general drawback of Monte Carlo simulation is that is does not naturally accommodate the valuation of American- or Bermudan-style options,. because the value of holding an option at any state typically requires pricing by backward induction. While methodological advances are now used to overcome this problem,1 the issue does not really arise when valuing the. prepayment option. As it is generally accepted that homeowner behavior is not well explained as the optimal exercise of a fixed income option, a path-dependent prepayment function, which is well-suited to Monte Carlo simulation, is the preferred approach..  

The second problem addressed in this section relates to the mortgage. rate. Valuing an MBS along a path requires both the benchmark of discounting rates as well as the mortgage rate. Discounting can be done at benchmark rates plus a spread, but the incentive of a prepayment model depends on the current mortgage rate. The difficulty is that calculating the fair mortgage rate at a single date on a single path of a Monte Carlo simulation is a problem of the same order of magnitude as the original problem of pricing a particular. MBS as of the current state! Common practice, therefore, is to build a simple model of the mortgage rate as a function of benchmark rates and, perhaps,. volatility, for example, an estimated regression model of the mortgage rate as a function of one or more benchmark rates and rate volatility. It may not be trivial to compute long-term benchmark rates along a path of short-term rates, but this difficulty can usually be overcome with a closed-form solution for long-term rates or with a numerical approximation consistent with the short-term rate process.  

The third problem is that defaults and turnover depend on variables other than interest rates, like housing prices, which are not traditionally included in the pricing of fixed income securities. Incorporating these variables, including their correlations with interest rates, is yet another challenge of pricing MBS.  

# Fixed Income Options  

# A16.1 THEORETICAL FOUNDATIONS FOR APPLYING BLACK-SCHOLES-MERTON (BSM) TO SELECTED FIXED INCOME OPTIONS  

The justification for applying BSM in each of the cases of the text takes the following form:  

1. Given the functional form of a probability distribution (e.g., normal, lognormal), there exist parameters of that distribution such that. $V_{0}$ , the arbitrage-free price of any asset today, is given by,.  

$$
{\frac{V_{0}}{N_{0}}}=E_{0}\left[{\frac{V_{t}}{N_{t}}}\right]
$$  

where $N_{t}$ is the price at time $t$ of an asset chosen as the numeraire; $\mathbf{}V_{t}$ is value at time $t$ of an asset being priced today, including reinvested cash flows; and. $E_{t}[\cdot]$ gives expectations as of time $t$ under the appropriately parameterized probability distribution. Equation (A16.1) is known as the martingale property of asset prices. This claim is proved in a special case in Section A16.2 but used more generally here.  

2. Say that the rate or security price underlying an option at time $t$ is $S_{t}$ It follows from the previous point that the value of a call option with strike $K$ and time to expiry $T$ is,  

$$
V_{0}^{C a l l}=N_{0}E_{0}\left[\frac{(S_{T}-K)^{+}}{N_{T}}\right]
$$  

while the value of a put is,  

$$
V_{0}^{P u t}=N_{0}E_{0}\left[\frac{(K-S_{T})^{+}}{N_{T}}\right]
$$  

3. In the contexts of the text, it is possible to choose the numeraire such that,  

$$
S_{0}=E_{0}[S_{T}]
$$  

and such that Equations (A16.2) and (A16.3) can be written as, res pectively,  

$$
\begin{array}{r}{V_{0}^{C a l l}=b_{0}E_{0}[(S_{T}-K)^{+}]}\ {~}\ {V_{0}^{P u t}=b_{0}E_{0}[(K-S_{T})^{+}]}\end{array}
$$  

for some $b_{0}$ that is known as of time 0. This is proven in Section A16.3. 4. If $S_{t}$ has a normal distribution with volatility parameter $\sigma$ ,then Section A16.4 shows that (A16.4) through (A16.6) become the normal BSM-style formulae,  

$$
\begin{array}{r}{V_{0}^{C a l l}=b_{0}\xi^{N}(S_{0},T,K,\sigma)}\ {~}\ {V_{0}^{P u t}=b_{0}\pi^{N}(S_{0},T,K,\sigma)}\end{array}
$$  

for the functions $\xi^{N}(\cdot)$ and $\pi^{N}(\cdot)$ defined in that section. On the other hand, if $S_{t}$ has a lognormal distribution with volatility parameter $\sigma$ Section A16.4 shows that (A16.4) through (A16.6) become the lognormal BSM-style formulae,  

$$
V_{0}^{C a l l}=b_{0}\xi^{L N}(S_{0},T,K,\sigma)
$$  

and  

$$
V_{0}^{P u t}=b_{0}\pi^{L N}(S_{0},T,K,\sigma)
$$  

for the functions. $\xi^{L N}(\cdot)$ and $\pi^{L N}(\cdot)$ defined in that section.  

# A16.2 NUMERAIRES, PRICING MEASURES,AND THE MARTINGALE PROPERTY  

Define the following:  

Gains process. The gains process of an asset at any time equals the value of that asset at that time plus the value of all its cash flows reinvested to that time. For this purpose, all cash flows are reinvested and then rolled at prevailing short-term interest rates.  

Numeraire asset. Given a particular numeraire asset, the gains process of any other asset can be expressed in terms of the numeraire asset by dividing that gains process by the gains process of the numeraire asset. The gains process of a security in terms of the numeraire asset is called the normalized gains process of that asset.  

For concreteness, Table A16.1 gives an example of these concepts. The asset under consideration is a long-term,. $4\%$ coupon bond with a face. amount of 100. The numeraire is a two-year zero coupon bond with a unit face amount. The gains process is observed today, after one year, and after two years.  

The realization of the short-term rate, which in this example is the oneyear rate, is given in row (i). The realization of the bond price over time is given in row (ii). A $4\%$ coupon on 100 is paid on dates 1 and 2 and shown in row (ii) and row (iv). The payment on date 1 is reinvested for one year at the short-term rate on date 1, that is, $2\%$ . The gains process of the bond given in row (v) is the sum of its price and reinvested cash flows, i.e., the sums of rows (ii) through (iv). The price realization of the two-year zero coupon bond, which is the chose numeraire, is given in row (vi). Finally, the normalized bond gains process, given in row (vii), is the bond gains process divided by the price of the numeraire, i.e., row (v) divided by row (vi).  

These definitions allow for the statement of the main result of this section: in the absence of arbitrage opportunities, there exists a parameter-. ization of a given probability distribution, or a pricing measure, such that the normalized gains of any asset today equals the expected value of that asset's normalized gains in the future. Technically, there exist probabilities such that the normalized gains process is a martingale. As the goal here is. intuition rather than mathematical generality, this result is proven in the context of a single-period, binomial process..  

TABLE A16.1 Example of the Calculation of a Normalized Gains Process   


<html><body><table><tr><td></td><td></td><td colspan="3">End-of-YearRealizations</td></tr><tr><td></td><td></td><td>0</td><td>1</td><td>2</td></tr><tr><td>(i)</td><td>Short-Term/1-YearRate</td><td>1%</td><td>2%</td><td>1.5%</td></tr><tr><td>(ii)</td><td>Bond Price</td><td>100</td><td>95</td><td>97.50</td></tr><tr><td>(ii)</td><td>Date 1 Reinvested Coupon</td><td></td><td>4</td><td>4(1.02)=4.08</td></tr><tr><td>(iv)</td><td>Date 2 Reinvested Coupon</td><td></td><td></td><td>4</td></tr><tr><td>(v)</td><td>Gains Process</td><td>100</td><td>99</td><td>105.58</td></tr><tr><td>(vi)</td><td>Price of 2-Year Zero/Numeraire</td><td>0.9612</td><td>0.9804</td><td>1.0</td></tr><tr><td>(vii)</td><td>Normalized Bond Gains Process</td><td>104.04</td><td>100.98</td><td>105.58</td></tr></table></body></html>  

The starting point is state 0 of date 0, after which the economy moves. to either state 0 or state 1 of date 1. Three assets will be considered, A, B, and C, with current prices $A_{0},B_{0}$ , and $C_{0}$ , and date 1, state $i$ prices of $A_{1}^{i},B_{1}^{i}$ and $C_{1}^{i}$ . Without loss of generality here, the date 1 prices include any cash flows of the securities on date 1..  

In this framework, any asset can be priced by arbitrage relative to the other two assets. The method is just as in Chapter 7. To price asset C by arbitrage, construct its replicating portfolio, in particular, a portfolio with $\alpha$ of asset A and $\beta$ of asset B such that,  

$$
\begin{array}{r}{C_{1}^{0}=\alpha A_{1}^{0}+\beta B_{1}^{0}}\ {{}}\ {C_{1}^{1}=\alpha A_{1}^{1}+\beta B_{1}^{1}}\end{array}
$$  

Then, to rule out risk-free arbitrage opportunities, it must be the case that,  

$$
C_{0}=\alpha A_{0}+\beta B_{0}
$$  

Now let asset A be the numeraire and rewrite equations (A16.11) through (A16.13) in terms of the normalized gains processes of assets B and C. To do this, simply divide each of the equations by the corresponding. value of the numeraire asset A, that is, divide (A16.11) by. $A_{1}^{0}$ ,(A16.12) by $A_{1}^{1}$ , and(A16.13) by $A_{0}$ . Furthermore, denote the normalized gains process of the assets by. $\overline{B}$ and $\overline{{C}}$ . Then, equations (A16.11) through (A16.13) become,  

$$
\begin{array}{r l}&{\overline{{C}}_{1}^{0}=\alpha+\beta\overline{{B}}_{1}^{0}}\ &{}\ &{\overline{{C}}_{1}^{1}=\alpha+\beta\overline{{B}}_{1}^{1}}\ &{}\ &{\overline{{C}}_{0}=\alpha+\beta\overline{{B}}_{0}}\end{array}
$$  

Furthermore, solving (A16.14) and (A16.15) for $\alpha$ and $\beta$  

$$
\begin{array}{l}{\displaystyle\alpha=\frac{\overline{{B}}_{1}^{1}\overline{{C}}_{1}^{0}-\overline{{B}}_{1}^{0}\overline{{C}}_{1}^{1}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}}\ {\displaystyle\beta=\frac{\overline{{C}}_{1}^{1}-\overline{{C}}_{1}^{0}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}}\end{array}
$$  

In the framework just described, it is now shown that there exists a pricing measure such that the expected normalized gains process of each security is a martingale. More specifically, there is a probability $\boldsymbol{p}$ of moving to state 1 of date 1 (and $1-p$ of moving to state 0 of date 1) such that the. expected value of the normalized gain of each security on date 1 equals its normalized gain on date 0. Mathematically, it has to be shown that there is $\boldsymbol{p}$ such that,  

$$
\begin{array}{l}{{\overline{{{C}}}_{0}=\gamma\overline{{{C}}}_{1}^{1}+(1-p)\overline{{{C}}}_{1}^{0}}}\ {{}}\ {{\overline{{{B}}}_{0}=\gamma\overline{{{B}}}_{1}^{1}+(1-p)\overline{{{B}}}_{1}^{0}}}\end{array}
$$  

Solving (A16.20) for $\boldsymbol{p}$ gives,  

$$
\dot{p}=\frac{\overline{{B}}_{0}-\overline{{B}}_{1}^{0}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}
$$  

But this value of $p$ also solves (A16.19). To see this, start by substituting $p$ from (A16.21) into the right-hand side of (A16.19),  

$$
\begin{array}{r l}{\displaystyle{\dot{p}}\overline{{C}}_{1}^{1}+(1-\gamma)\overline{{C}}_{1}^{0}=\frac{\overline{{B}}_{0}-\overline{{B}}_{1}^{0}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}\overline{{C}}_{1}^{1}-\frac{\overline{{B}}_{0}-\overline{{B}}_{1}^{1}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}\overline{{C}}_{1}^{0}}&{}\ {=\overline{{B}}_{0}\frac{\overline{{C}}_{1}^{1}-\overline{{C}}_{1}^{0}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}+\frac{\overline{{B}}_{1}^{1}\overline{{C}}_{1}^{0}-\overline{{B}}_{1}^{0}\overline{{C}}_{1}^{1}}{\overline{{B}}_{1}^{1}-\overline{{B}}_{1}^{0}}}&{}\ {=\overline{{B}}_{0}\beta+\alpha}&{}\ {=\overline{{C}}_{0}}&{=\overline{{C}}_{0}}\end{array}
$$  

Equation (A16.23) just rearranges the terms of (A16.22); combining. (A16.23) with (A16.17) and (A16.18) gives (A16.24); and (A16.24) with (A16.16) gives (A16.25). Hence, as was to be shown, there is a pricing measure, in this case the probability. $p$ , such that the normalized gains processes. of B and C are martingales. And, of course, since nothing distinguishes A from the other assets, a probability with the same properties could have. been found had B or C been chosen as the numeraire instead..  

# A16.3 CHOOSING THE NUMERAIRE AND BSM PRICING  

In the contexts of this chapter, it is possible to choose a numeraire. such that the underlying is a martingale and such that the value of a call is given by $b_{0}\xi^{N}(S_{0},T,K,\sigma)$ or $b_{0}\xi^{L N}(S_{0},T,K,\sigma)$ , in the normal or lognormal cases, respectively, and the value of a put by $b_{0}\pi^{N}(S_{0},T,K,\sigma)$ or $b_{0}\bar{\pi}^{L N}(S_{0},T,K,\sigma)$ in the normal or lognormal cases, where those functions are defined in Section A16.4. This section gives the appropriate definition of the underlying, the appropriate numeraire, and the resulting quantity $b_{0}$  

# A16.3.1 Bond Options  

Start with a European-style option, expiring on date $T$ , written on a longerterm bond. The underlying of this option is a forward position in the bond for delivery on date $T$ . It is first shown that taking the zero coupon bond. maturing at time $T$ to be the numeraire makes this forward bond price a martingale. Proving this is somewhat complex, because the gains process. of a bond includes reinvested coupons. Therefore, to keep the presentation simple, the martingale result is derived in a three-date, two-period setting.. The current date is date 0, and the expiration or forward delivery date is. date 2. The bond is assumed to pay a coupon $c$ on each of dates 1 and 2, and its price at time $t$ is denoted $B_{t}$ . The numeraire is the zero coupon bond. maturing on date 2 with a price, on date. $t.$ of $d_{t}(2)$ . Lastly, let $r_{1}$ denote the current one-period rate; $r_{2}$ the one-period rate, realized one period from. now; and $f$ the current one-period rate, one-period forward..  

Under these assumptions, and the expression of the zero coupon bond price on various dates in terms of the prevailing one-period rates, the gains process of the bond on the three dates is given by the expressions,  

Date 0: $\begin{array}{r l}&{\frac{B_{0}}{d_{0}(2)}=B_{0}(1+r_{1})(1+f);}\ &{\frac{B_{1}+c}{d_{1}(2)}=(B_{1}+c)(1+r_{2});}\ &{\frac{B_{2}+c(1+r_{2})+c}{d_{2}(2)}=B_{2}+c(1+r_{2})+c}\end{array}$   
Date 1:   
Date 2:  

Therefore, the martingale property for the bond says that,  

$$
\begin{array}{r}{\displaystyle\frac{B_{0}}{d_{0}(2)}=E_{0}\left[\frac{B_{2}+c(1+r_{2})+c}{d_{2}(2)}\right]}\ {B_{0}(1+r_{1})(1+f)=E_{0}[B_{2}+c(1+r_{2})+c]}\end{array}
$$  

The term $c(1+r_{2})$ in the expectation on the right-hand side of (A16.26) requires some attention, because. $r_{2}$ is not known as of date O. The date-0 value of a payment of $c(1+r_{2})$ on date 2 is, however, by the definition of forward rates,  

$$
{\frac{c(1+f)}{(1+r_{1})(1+f)}}={\frac{c}{1+r_{1}}}
$$  

So, applying the martingale property under the numeraire to a payment of $c(1+r_{2})$ on date 2 requires that,  

$$
\frac{\frac{c}{1+r_{1}}}{d_{0}(2)}=E_{0}\left[\frac{c(1+r_{2})}{d_{2}(2)}\right]
$$  

$$
c(1+f)=E_{0}[c(1+r_{2})]
$$  

With this result, the discussion returns to the martingale property of the bond in (A16.26). Substituting (A16.28) into (A16.26),  

$$
\begin{array}{r}{B_{0}(1+r_{1})(1+f)-c(1+f)-c=E_{0}[B_{2}]}\ {\left[B_{0}-\cfrac{c}{1+r_{1}}-\cfrac{c}{(1+r_{1})(1+f)}\right](1+r_{1})(1+f)=E_{0}[B_{2}]}\ {B_{0}(2)=E_{0}[B_{2}]}\end{array}
$$  

The left-hand side of the second line of (A16.29) is the date 0 forward price of the bond for delivery on date 2. The third line, then, simply denotes this forward price by $B_{0}(2)$ . Hence, taking the zero coupon bond of maturity. $T$ as a numeraire, the forward price of a bond for delivery on date $T$ is a martingale.  

Turning now to the price of an option on the bond, consider a call with payoff $(B_{T}-K)^{+}$ . Applying the martingale property to the option price and assuming that the forward bond price is lognormal with volatility parameter $\sigma$ , the call option is priced as,  

$$
\begin{array}{l}{{\displaystyle\frac{V_{0}^{B o n d C a l l}}{d_{0}(T)}=E_{0}\left[\frac{(B_{T}-K)^{+}}{d_{T}(T)}\right]}~}\ {{\displaystyle~=E_{0}[(B_{T}-K)^{+}]}~}\ {{\displaystyle V_{0}^{B o n d C a l l}=d_{0}(T)\xi^{L N}(B_{0}(T),T,K,\sigma)}}\end{array}
$$  

An analogous argument for a put shows that,  

$$
V_{0}^{B o n d P u t}=d_{0}(T)\pi^{L N}(B_{0}(T),T,K,\sigma)
$$  

# A16.3.2 Euribor Futures Options  

The terminal payoff of a Euribor futures call option with strike $K$ and expiration time $T$ is, per unit notional,  

$$
[K-f_{T}(T,T+\tau)]^{+}
$$  

Given the daily settlement feature of Euribor futures options, the numeraire of choice is the money market account, the value of one unit of currency invested and then rolled every period, at the prevailing short-term rate. Denoting the money market account by $M(t)$ and the short-term rate from time t - 1 to t by rt,  

$$
M(0)=1
$$  

$$
M(T)=(1+r_{1})(1+r_{2})\cdot\cdot\cdot(1+r_{T})
$$  

The first point to make about the money market account is that it is the numeraire of the risk-neutral short-term rate process used in the term structure models presented earlier in the book. To see this, apply the martingale property with the numeraire to an arbitrary gains process. $V_{t}$ at time $t$  

$$
\begin{array}{r}{\lefteqn{\frac{V_{0}}{M(0)}=E_{0}\left[\frac{V_{T}}{M(T)}\right]}}\ {\phantom{\frac{V_{0}}{0}}V_{0}=E_{0}\left[\frac{V_{T}}{(1+r_{1})(1+r_{2})\cdot\cdot\cdot(1+r_{T})}\right]}\end{array}
$$  

But the second line of (A16.37) is just the condition that the value of a claim today equals its expected discounted value..  

The second point to make about the money markets as numeraire is that futures prices are martingales under this numeraire. This is proved in Section A16.5.  

Turning now to Euribor futures options, because they are subject to daily settlement and are futures contracts, their prices are also martingales with the money market account as numeraire. Furthermore, if $F_{t}$ is the underlying. futures price at time. $t$ , then at the expiration of a put option on the futures price (call on rates) at time $T$ , the option is worth. $(F_{T}-K)^{+}$ . Putting together the martingale property of the futures, (A16.38), the martingale property of futures options, (A16.39), and the final settlement price of the futures options, (A16.40), results in the price of the Euribor futures put option at time t, denoted vEBPut,  

$$
\begin{array}{c}{F_{0}=E[F_{T}]}\ {V_{0}^{E B P u t}=E_{0}[V_{T}^{E B P u t}]}\ {=E_{0}[(F_{T}-K)^{+}]}\end{array}
$$  

Assuming now that. $F_{T}$ is normally distributed, applying Section A16.4 to Equations (A16.38) and (A16.40) shows that,  

$$
V_{0}^{E B P u t}=\xi^{N}(F_{0},T,K,\sigma)
$$  

Similarly, for the Euribor futures call option (put on rates),  

$$
V_{t}^{E B C a l l}=\pi^{N}(F_{0},T,K,\sigma)
$$  

# A16.3.3 Bond Futures Options  

As shown in Section A16.5, futures prices are a martingale in the risk-neutral measure, that is, when the numeraire is the money market account, $M(t)$ Hence, with $F_{t}$ the underlying bond futures price at time. $t$  

$$
F_{0}=E[F_{T}]
$$  

By the martingale property, the price of a put option on the futures is,  

$$
\frac{V_{0}^{F u t P u t}}{M(0)}=E_{0}\left[\frac{(K-F_{T})^{+}}{M(T)}\right]
$$  

Then, by the definition of the money market account,  

$$
V_{0}^{F u t P u t}=E_{0}\left[\frac{(K-F_{T})^{+}}{(1+r_{1})(1+r_{2})\cdot\cdot\cdot(1+r_{T})}\right]
$$  

To continue, make the assumption - defended in the text -- that the discount factor is uncorrelated with the futures price. Then, Equation (A16.45). becomes,  

$$
\begin{array}{l}{{V_{0}^{F u t P u t}=E_{0}\left[\frac1{(1+r_{1})(1+r_{2})\cdot\cdot\cdot(1+r_{T})}\right]E_{0}[(K-F_{T})^{+}]}}\ {{{}~}}\ {{{}~=d_{0}(T)E_{0}[(K-F_{T})^{+}]}}\end{array}
$$  

where (A16.47) follows from the risk-neutral pricing of a zero coupon bond. Finally, applying Section A16.5 to (A16.43), (A16.47) with the assumption that the bond futures price has a lognormal distribution,.  

$$
V_{0}^{F u t P u t}=d_{0}(T)\pi^{L N}(F_{0},T,K,\sigma)
$$  

For calls, the analogous result is,  

$$
V_{0}^{F u t C a l l}=d_{0}(T)\xi^{L N}(F_{0},T,K,\sigma)
$$  

# A16.3.4 Caplets  

Caplets that mature at time $T$ are written on a forward rate from time $T$ to $T+\tau$ , whose value, at time $t$ , is denoted by $f_{t}(T,T+\tau)$ . It is first shown that taking a $T+\tau$ -year zero coupon bond as the numeraire makes this forward rate a martingale. Let $d_{t}(T)$ be the time- $\cdot t$ price of a zero coupon bond maturing at time $T$ . By the definition of a forward rate of term $\tau$  

$$
\begin{array}{c}{{f_{t}(T,T+\tau)=\displaystyle\frac{1}{\tau}\left(\displaystyle\frac{d_{t}(T)}{d_{t}(T+\tau)}-1\right)}}\ {{=\displaystyle\frac{1}{\tau}\left(\displaystyle\frac{d_{t}(T)-d_{t}(T+\tau)}{d_{t}(T+\tau)}\right)}}\end{array}
$$  

Next, consider a portfolio that is long a. $T$ -year zero and short a. $T+\tau$ -year zero. Taking the. $T+\tau$ -year zero as the numeraire, the normalized. gains process of this portfolio is a martingale. Mathematically,  

$$
\begin{array}{r l}&{\frac{1}{\tau}\left(\frac{d_{t}(T)-d_{t}(T+\tau)}{d_{t}(T+\tau)}\right)=\frac{1}{\tau}E_{t}\left[\frac{d_{T}(T)-d_{T}(T+\tau)}{d_{T}(T+\tau)}\right]}\ &{\quad\quad\quad=\frac{1}{\tau}E_{t}\left[\frac{d_{T}(T)}{d_{T}(T+\tau)}-1\right]}\ &{\quad\quad\quad=E_{t}[f_{T}(T,T+\tau)]}\end{array}
$$  

where the last line of (A16.51) just uses the definition of the forward rate. Combining (A16.50) and (A16.51) shows that the forward rate is a martingale under the chosen numeraire,  

$$
f_{t}(T,T+\tau)=E_{t}[f_{T}(T,T+\tau)]
$$  

Turning to the valuation of the caplet, its normalized gains process is. a martingale as well. Hence, taking expectations of its normalized gain as of $T+\tau$  

$$
\begin{array}{r}{\frac{V_{0}^{C a p l e t}}{d_{0}(T+\tau)}=E_{0}\left[\frac{\tau(f_{T}(T,T+\tau)-K)^{+}}{d_{T+\tau}(T+\tau)}\right]}\ {=E_{0}[\tau(f_{T}(T,T+\tau)-K)^{+}]}\end{array}
$$  

Finally, assuming that the forward rate $f_{T}(T,T+\tau)$ is normal with variance $\sigma^{2}T$ , and knowing from (A16.52) with $t=0$ that its mean is $f_{0}(T,T+\tau)$ , the results of Section A16.4 apply and,  

$$
V_{0}^{C a p l e t}=d_{0}(T+\tau)\tau\xi^{N}(f_{0}(T,T+\tau),T,K,\sigma)
$$  

# A16.3.5 Swaptions  

The underlying of a $T$ -year into $\tau$ -year swaption is the forward par swap rate from $T$ to $T+\tau$ , which, at time $t$ , is denoted by $C_{t}(T,T+\tau)$ . It is first shown that taking an annuity from $T$ to $T+\tau$ as the numeraire makes this forward par swap rate a martingale. Denote the price of this annuity by $A_{t}(T,T+\tau)$  

Consider receiving the fixed-rate $K$ on a swap from $T$ to $T+\tau$ . Its value at time $t$ is,  

$$
[K-C_{t}(T,T+\tau)]A_{t}(T,T+\tau)
$$  

Applying the martingale property with this annuity as numeraire,  

$$
\frac{[K-C_{t}(T,T+\tau)]A_{t}(T,T+\tau)}{A_{t}(T,T+\tau)}=E_{t}\left[\frac{[K-C_{T}(T,T+\tau)]A_{T}(T,T+\tau)}{A_{T}(T,T+\tau)}\right]
$$  

$$
C_{t}(T,T+\tau)=E_{t}[C_{T}(T,T+\tau)]
$$  

Hence, as claimed, the forward par swap rate is a martingale under this numeraire.  

To price a receiver swaption, note that the payoff is. $[K-C_{T}(T,T+\tau)]^{+}$ $\times A_{T}(T,T+\tau)$ . Therefore, its value can be calculated as the expectation of its normalized payoff using the same numeraire,.  

$$
\begin{array}{r l r}{\lefteqn{\frac{V_{0}^{R e c e i v e r}}{A_{0}(T,T+\tau)}=E_{0}\left[\frac{(K-C_{T}(T,T+\tau))^{+}A_{T}(T,T+\tau)}{A_{T}(T,T+\tau)}\right]}}\ &{}&{=E_{0}[(K-C_{T}(T,T+\tau))^{+}]}\ &{}&{V_{0}^{R e c e i v e r}=A_{0}(T,T+\tau)\pi^{N}(C_{0}(T,T+\tau),T,K,\sigma)}\end{array}
$$  

The last line of (A16.58) follows from (A16.57), the assumption that the forward par swap rate is normal with variance $\sigma^{2}T$ , and the appropriate result from Section A16.4.  

Similarly, a payer option under the assumption of normality has the value,  

$$
V_{0}^{P a y e r}=A_{0}(T,T+\tau)\xi^{N}(C_{0}(T,T+\tau),T,K,\sigma)
$$  

# A16.4EXPECTATIONS FOR BLACK-SCHOLES-MERTON STYLE OPTION PRICING  

As the results in this section are part of the option pricing literature, they are presented here for easy reference but without proof. Let $E^{N}[\cdot]$ and $E^{L N}[\cdot]$  

denote the expectations operators under the normal and lognormal distributions, respectively, and let $N(\cdot)$ denote the standard normal cumulative distribution.  

If $S_{T}$ is normally distributed with means $S_{0}$ and variance $\sigma^{2}T$ , then,  

$$
\begin{array}{l}{{\displaystyle\xi^{N}(S_{0},T,K,\sigma)\equiv E_{0}^{N}[(S_{T}-K)^{+}]~}}\ {{\displaystyle~=(S_{0}-K)N(d)+\frac{\sigma\sqrt{T}}{\sqrt{2\pi}}e^{-\frac{1}{2}d^{2}}}}\ {{\displaystyle\pi^{N}(S_{0},T,K,\sigma)\equiv E_{0}^{N}[(K-S_{T})^{+}]~}}\ {{\displaystyle~=(K-S_{0})N(-d)+\frac{\sigma\sqrt{T}}{\sqrt{2\pi}}e^{-\frac{1}{2}d^{2}}}}\ {{\displaystyle d=\frac{S_{0}-K}{\sigma\sqrt{T}}~}}\end{array}
$$  

$S_{T}$ is lognormally distributed with mean $S_{0}$ and variance $S_{0}^{2}(e^{\sigma^{2}T}-1)$ then,  

$$
\begin{array}{c}{{\xi^{L N}(S_{0},T,K,\sigma)\equiv E_{0}^{L N}[(S_{T}-K)^{+}]}}\ {{{}}}\ {{{}=S_{0}N(d_{1})-K N(d_{2})}}\end{array}
$$  

$$
\begin{array}{r l}&{\pi^{L N}(S_{0},T,K,\sigma)\equiv E_{0}^{L N}[(K-S_{T})^{+}]}\ &{\quad\quad\quad=K N(-d_{2})-S_{0}N(-d_{1})}\ &{\quad\quad\quad d_{1}=\frac{\ln(\frac{S_{0}}{K})+\frac{1}{2}\sigma^{2}T}{\sigma\sqrt{T}}}\ &{\quad\quad\quad\quad=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

# A16.5FUTURES PRICES ARE MARTINGALES WITH THE MONEY MARKET ACCOUNT AS A NUMERAIRE  

The initial value of a futures contract is zero; subsequent cash flows are from daily settlements; and at maturity, the futures price is determined by some final settlement rule. Consider a two-period, three-date framework for simplicity, and let the futures price on date. $t$ be $F_{t}$ . Then, the normalized. gains process is,  

$$
\begin{array}{r}{\mathbf{\mathrm{~Date~}}0\colon\frac{V_{0}}{M(0)}=0;}\end{array}
$$  

Date 1: $\begin{array}{r}{\frac{V_{1}}{M(1)}=\frac{F_{1}-F_{0}}{1+r_{1}}}\end{array}$ Date 2: V3, = (F1-Fo)(1+r2)+F2-F1  

Since the value of a futures contact on date O is zero, the martingale property implies that the expectation of the normalized gains at any future date is zero. In particular, for date 1,  

$$
0=E_{0}\left[{\frac{F_{1}-F_{0}}{1+r_{1}}}\right]
$$  

But since $r_{1}$ is known as of date 0, it follows from (A16.67) that,  

$$
F_{0}=E_{0}[F_{1}]
$$  

As of date 2, the martingale property says that  

$$
0=E_{0}\left[\frac{(F_{1}-F_{0})(1+r_{2})+F_{2}-F_{1}}{(1+r_{1})(1+r_{2})}\right]
$$  

Using the law of iterated expectations, and the fact that $r_{1}$ is known as of date 0,  

$$
0=E_{0}\left[{\frac{1}{1+r_{2}}}E_{1}[F_{2}-F_{1}]\right]
$$  

But, since $F_{1}$ is known as of date 1, (A16.70) implies that,  

$$
F_{1}=E_{1}[F_{2}]
$$  

Finally then, combine (A16.68) and (A16.71) to see that,  

$$
F_{0}=E_{0}[E_{1}[F_{2}]]=E_{0}[F_{2}]
$$  

Together with (A16.68), (A16.72) shows that the futures price is a martin-.   
gale under the money-market account or risk-neutral measure, as desired.  