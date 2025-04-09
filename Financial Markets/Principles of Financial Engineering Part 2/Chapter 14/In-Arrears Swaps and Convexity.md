# 14.7 IN-ARREARS SWAPS AND CONVEXITY  

Although an overwhelming proportion of swap transactions involve the vanilla swap, in some cases parties transact the so-called LIBOR-in-arrears swap. In this section, we study this instrument because it is a good example of how Forward LIBOR volatilities enter pricing directly through convexity adjustments..  

But first we need to clarify the terminology. In a vanilla swap, the LIBOR rates $L_{t_{i}}$ are assumed to "set" at time $t_{i}$ whereas the floating payments are made in arrears at times $t_{i+1}$ 29 In the case of an  

1. Interest rate swap  

Receive floating $L_{t_{j-1}}\delta N$  

![](47f21fa2ba5a7ce6909e7220892ba325ee2886d8134478484f2a3eb24d33bb9a.jpg)  

2. LIBOR-in-arrears swap  

![](fcf00aac26894f00f5a19ec0d422bd3183acd662fbd57e458f10ed54ba01a936.jpg)  

# FIGURE 14.6  

Interest rate swap versus LIBOR-in-arrears swap.  

in-arrears swap, the payment days are kept the same, but the time $t_{i+1}$ settlement will use the LIBOR rate $L_{t_{i+1}}$ that has just been observed at time ${t_{i+1}}^{30}$ to determine the floating payment. Thus, in a sense. the setting of the LIBOR rate is in arrears, hence the name of the in-arrears swap.31 The difference. between LIBOR resets is illustrated in and the difference between vanilla interest rate swaps and LIBOR-in-arrears swaps is shown in Figure 14.6. LIBOR-in-arrears swaps set the LIBOR rates in arrears.  

The simple modification of paying the $L_{t_{i+1}}$ observed at time $t_{i+1}$ rather than the previously observed $L_{t_{i}}$ makes a significant difference in pricing. We will work with a simple case of a twoperiod (forward) swap first, and then give the generalized formulas.  

# 14.7.1 VALUATION  

The valuation of the fixed leg of the in-arrears swap is the same as that of the vanilla swap, except of course the swap coupons are different. Let the $s_{t_{0}}$ be the vanilla swap rate fixed at time $t_{0},N$ and $\delta$ be the notional amount and accrual parameters, respectively. Then the fixed leg payments are easy to value:  

$$
\begin{array}{r l}&{\mathrm{Fixed-Leg}_{t_{0}}=B(t_{0},t_{2})s_{t_{0}}\delta N+B(t_{0,t_{3}})s_{t_{0}}\delta N}\ &{\qquad=[B(t_{0},t_{2})+B(t_{0},t_{3})]s_{t_{0}}\delta N}\end{array}
$$  

It is clear that in case of the in-arrears swap, we will have a similar expression:  

$$
\mathrm{Fixed-Leg}_{t_{0}}=[B(t_{0},t_{2})+B(t_{0},t_{3})]i s_{t_{0}}\delta N
$$  

where the $i s_{t_{0}}$ is the swap rate of the in-arrears swap.  

The difference in valuations emerge in the floating leg. Note that in the case of the in-arrears swap, the expected value under the $P^{t_{2}}$ forward measure of the floating rate payments would be  

$$
\mathrm{Floating-Leg}_{t_{0}}={E}_{t_{0}}^{P^{t_{2}}}[B(t_{0},t_{2})L_{t_{2}}]\delta N+{E}_{t_{0}}^{P^{t_{2}}}[B(t_{0},t_{3}]\delta N
$$  

Multiply and divide by $(1+L_{t_{2}}\delta)$ and $(1+L_{t_{3}}\delta)$ , respectively, we obtain  

$$
\mathrm{Floating-Leg}=E_{t_{0}}^{p_{t_{2}}}\left[B(t_{0},t_{2})L_{t_{2}}{\frac{\left(1+L_{t_{2}}\delta\right)}{\left(1+L_{t_{2}}\delta\right)}}\right]\delta N+E_{t_{0}}^{p_{t_{2}}}\left[B(t_{0},t_{3})L_{t_{3}}{\frac{\left(1+L_{t_{3}}\delta\right)}{\left(1+L_{t_{3}}\delta\right)}}\right]\delta N
$$  

But in the case of finite-state random quantities, we have the usual correspondence between the $t_{3}$ and $t_{2}$ forward measures:  

$$
p_{i}^{t_{2}}\frac{B(t_{2},t_{3})^{i}}{B(t_{0},t_{3})}B(t_{0},t_{2})=p_{i}^{t_{3}}
$$  

Also, by definition  

$$
B(t_{2},t_{3})^{i}=\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}
$$  

This means that after regrouping, changing measures from $P^{t_{2}}$ to $P^{t_{3}}$  

$$
E_{t_{0}}^{P^{t_{2}}}\left[B(t_{0},t_{2})L_{t_{2}}\frac{\left(1+L_{t_{2}}\delta\right)}{\left(1+L_{t_{2}}\delta\right)}\right]\delta N=E_{t_{0}}^{P^{t_{3}}}\left[B(t_{0},t_{3})L_{t_{2}}\left(1+L_{t_{2}}\delta\right)\right]\delta N
$$  

Changing the measure from $P^{t_{3}}$ to $P^{t_{4}}$ , a similar set of equations gives  

$$
E_{t_{0}}^{P^{t_{3}}}\left[B(t_{0},t_{3})L_{t_{3}}\frac{\left(1+L_{t_{3}}\delta\right)}{\left(1+L_{t_{3}}\delta\right)}\right]=E_{t_{0}}^{P^{t_{4}}}\left[B(t_{0},t_{4})L_{t_{3}}\left(1+L_{t_{3}}\delta\right)\right]
$$  

Thus the valuation of the floating leg becomes  

$$
\begin{array}{r}{\mathrm{Floating-Leg}_{t_{0}}=\left[E_{t_{0}}^{p_{i}}\left[B(t_{0},t_{3})L_{t_{2}}\left(1+L_{t_{2}}\delta\right)\right]+E_{t_{0}}^{p_{i}}\left[B(t_{0},t_{4})L_{t_{3}}\left(1+L_{t_{3}}\delta\right)\right]\right]\delta N}\end{array}
$$  

The right-hand side can be expanded to  

$$
\begin{array}{r l}&{\mathrm{Floating-Leg}_{t_{0}}=B(t_{0},t_{3})\left[E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}\right]+E_{t_{0}}^{P^{t_{3}}}\left[\left(L_{t_{2}}\delta\right)^{2}\right]\right]\delta N+B(t_{0},t_{4})\left[E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}\right]\right.}\ &{\qquad\left.+E_{t_{0}}^{P^{t_{4}}}\left[\left(L_{t_{3}}\delta\right)^{2}\right]\right]\delta N}\end{array}
$$  

But the forward rates are Martingales with respect to their own measures. So,  

$$
\begin{array}{r}{F_{t_{0}}^{t_{2}}=E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}\right]}\ {F_{t_{0}}^{t_{3}}=E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}\right]}\end{array}
$$  

and  

$$
\begin{array}{r}{E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}^{2}\right]=\left(F_{t_{0}}^{t_{2}}\right)^{2}e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}}\ {E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}^{2}\right]=\left(F_{t_{0}}^{t_{3}}\right)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}}\end{array}
$$  

So we get the final result as:  

$$
\begin{array}{r}{\mathrm{Floating-Leg}_{t_{0}}=B(t_{0},t_{3})\bigg[F_{t_{0}}^{P^{t_{2}}}+\delta\Big(F_{t_{0}}^{t_{2}}\Big)^{2}e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}\bigg]}\ {+B(t_{0},t_{4})\bigg[F_{t_{0}}^{t_{3}}+\delta\Big(F_{t_{0}}^{t_{3}}\Big)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{3}}^{2}\mathrm{d}u}\bigg]\delta N}\end{array}
$$  

This can be expressed as the floating leg of a vanilla swap plus an adjustment called the convexity adjustment:  

$$
\begin{array}{r}{\mathrm{Floating\mathrm{-Leg}}_{t_{0}}=\Big[B(t_{0},t_{3})F_{t_{0}}^{t_{2}}+B(t_{0},t_{4})F_{t_{0}}^{t_{3}}\Big]\delta N+\Big[B(t_{0},t_{3})\delta\big(F_{t_{0}}^{t_{2}}\big)e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{t}\mathrm{d}u}}\ {+B(t_{0},t_{4})\delta\Big(F_{t_{0}}^{t_{3}}\Big)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{3}}^{t_{2}}\mathrm{d}u}\Big]\delta N~\qquad\quad}\end{array}
$$  

For small settlement intervals,. $\Delta$ and constant volatilities the approximation becomes  

$$
\begin{array}{r}{\left[B(t_{0},t_{3})\delta\big(F_{t_{0}}^{t_{2}}\big)^{2}e^{\Delta\sigma_{t_{2}}^{2}}+B(t_{0},t_{4})\delta\big(F_{t_{0}}^{t_{3}}\big)^{2}e^{\Delta\sigma_{t_{3}}^{2}}\right]\delta N}\end{array}
$$  

Note that the second bracketed term in the convexity adjustment is positive. This makes the value of the floating rate payments in the in-arrears swap be greater than the value of the floating payments in the vanilla swap. The consequence of this is that the in-arrears fixed swap rate denoted by $\tilde{s}_{t}$ is bigger than the vanilla fixed rate  

$$
s_{t_{0}}<\tilde{s}_{t_{0}}
$$  

A number of comments can be made. First note that the volatilities can be obtained from the corresponding caplet volatilities. Second, note that the value of the in-arrears swap does not depend on the correlation between various forward rates. Third, the volatilities are likely to be different than the swaption volatilities.  

# 14.7.2 SPECIAL CASE  

A special case of this is if we look at a single period in-arrears swap. Then we get a relation between forward rates and futures rates.  

A Eurodollar contract leads to an exchange of. $f_{t_{0}}$ for $L_{t_{i}}$ at time $t_{i}$ The forward contract leads tc an exchange of $\boldsymbol{F}_{t_{0}}$ for $L_{t_{i-1}}$ at $t_{i}$ So this is the one-period replica of the comparison we just made.  

This means  

$$
f_{t_{0}}^{t-i}-F_{t_{0}}^{t-i}=\delta\big(F_{t_{0}}\big)^{2}e^{\int_{t_{0}}^{t_{i}}\sigma(u)_{t_{i}}^{2}\mathrm{d}u}
$$  

Directly from Eq. (14.177) of the previous section. The right-hand side is known as the convex-. ity adjustment that needs to be applied when going from futures to forward rates. Note that the futures price of the contract will then be smaller than the forward price.32.  
