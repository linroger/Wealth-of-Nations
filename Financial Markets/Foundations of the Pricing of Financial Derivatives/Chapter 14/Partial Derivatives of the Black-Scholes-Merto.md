# 14.6 PARTIAL DERIVATIVES OF THE BLACK-SCHOLES-MERTON EUROPEAN PUT OPTION PRICING MODEL

The Black-Scholes-Merton European put option pricing model is repeated here as

$$
\begin{array}{r}{p=X e^{-r_{c}\tau}N\mathopen{}\mathclose\bgroup\left(-d_{2}\aftergroup\egroup\right)-S N\mathopen{}\mathclose\bgroup\left(-d_{1}\aftergroup\egroup\right).}\end{array}
$$

Recall that put-call parity expresses the relationship between the put and call prices. To be consistent with the continuous time framework of Black-Scholes-Merton, we restate put-call parity using continuous discounting:

$$
\begin{array}{r}{p=c-S+X e^{-r_{c}\tau}.}\end{array}
$$

We can obtain the derivatives of the put model by differentiating Equation (14.38) as follows:

$$
\begin{array}{r l}&{\frac{\partial p}{\partial S}=\frac{\partial c}{\partial S}-1}\ &{\frac{\partial^{2}p}{\partial S^{2}}=\frac{\partial^{2}c}{\partial S^{2}}}\ &{\frac{\partial p}{\partial\tau}=\frac{\partial c}{\partial\tau}-r_{c}X e^{-r_{c}\tau}}\ &{\frac{\partial p}{\partial\sigma}=\frac{\partial c}{\partial\sigma}}\ &{\frac{\partial p}{\partial r_{c}}=\frac{\partial c}{\partial r_{c}}-\tau X e^{-r_{c}\tau}.}\end{array}
$$

Substituting the partial derivatives of the call and simplifying, we obtain the put delta as

$$
\Delta_{p}=\frac{\partial p}{\partial S}=N(d_{1})-1=-N(-d_{1}).
$$

Thus, the put delta is clearly negative, as it should be. The gamma is

$$
\Gamma_{p}=\frac{\partial^{2}p}{\partial S^{2}}=\frac{1}{S\sigma\sqrt{\tau}}n(d_{1})=\Gamma_{c}.
$$

The put gamma, which is the same as the call gamma, is clearly positive. The theta is obtained as

$$
\begin{array}{l}{\displaystyle\frac{\partial\boldsymbol{p}}{\partial\tau}=\frac{S\sigma}{2\sqrt{\tau}}n(\boldsymbol{d}_{1})-\boldsymbol{r}_{c}X e^{-\boldsymbol{r}_{c}\tau}N(-\boldsymbol{d}_{2})}\ {\displaystyle\Theta_{p}=\frac{\partial\boldsymbol{p}}{\partial t}=-\frac{S\sigma}{2\sqrt{\tau}}n(\boldsymbol{d}_{1})+\boldsymbol{r}_{c}X e^{-\boldsymbol{r}_{c}\tau}N(-\boldsymbol{d}_{2}).}\end{array}
$$

The put theta cannot be definitively signed. Indeed, it is well known that a European put can have a negative or positive theta. That is, the European put can have a lower or higher value with longer expiration. The negative relationship of put value to time to expiration occurs when the put is deep in-the-money. The upper limit of the put value, which exists by the fact that the put cannot achieve a higher value than the exercise price, can make a long-term put less valuable than a short-term put, the latter being closer to the time of expiration and the payoff from exercise. Because exercise of a put pays the exercise price, waiting a long time for that payoff penalizes the put holder. This unsigned theta on a European put is precisely the reason why if the put were American, there is a possibility that it would be optimal to exercise it early.

The vega is

$$
\nu_{p}=\frac{\partial p}{\partial\sigma}=S\sqrt{\tau}n\big(d_{1}\big).
$$

The put vega is the same as the call vega and is clearly positive. Finally, the rho is

$$
\rho_{\dot{p}}={\frac{\partial\dot{p}}{\partial r}}=-\tau X e^{-r_{c}\tau}N\bigl(-d_{2}\bigr).
$$

The put rho is negative, because a higher interest rate reflects the loss of greater interest from waiting to exercise the option..
