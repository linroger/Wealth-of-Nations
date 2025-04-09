# 30.2 EXPECTED RETURNS ON OPTIONS

Consider a hedge portfolio consisting of $b$ shares of the asset and one short call option. The portfolio value is $b S-c$ One period later the portfolio will be worth

$$
b(S+\Delta S)-\left(c+\Delta c\right),
$$

where the symbol $\Delta$ means the change in $S$ or $c$ If this portfolio is hedged, its value should grow at the risk-free rate. Hence, the following condition must hold:

$$
\big(b S-c\big)(1+r)=b(S+\Delta S)-(c+\Delta c).
$$

Gathering option terms on the left-hand side and asset terms on the right-hand side and dividing by $c$ , we obtain the following result:.

$$
{\frac{\Delta c}{c}}=r+\left({\frac{\Delta S}{S}}-r\right)b\left({\frac{S}{c}}\right).
$$

This expression says that the option return is the sum of the risk-free rate and an ex-post risk premium, $\Delta S/S-r$ , times a risk factor $b(S/c)$ . Recall that the Black-ScholesMerton model tells us that

$$
b={\frac{\partial c}{\partial S}},
$$

which should be recognized as the option's delta. Expressing the delta in discrete time, we have

$$
b=\frac{\Delta c}{\Delta S}.
$$

Then the risk factor is

$$
\frac{\Delta c}{\Delta S}\frac{S}{c}=\frac{\Delta c/c}{\Delta S/c}.
$$

Economists will recognize any term reflecting the percentage movement in one variable divided by the percentage movement in another as the concept of elasticity. Thus, we see that the return on the option is related to the return on the asset by the risk-free rate, a risk premium, and a term reflecting the option's elasticity.

Elasticity in this context measures the sensitivity of the option to the asset and, hence, is a reflection of the leverage of the option. Elasticity is closely related to the concept of the delta of the option, $\partial c/\partial S$ , which is also the hedge ratio, but delta is an absolute measure, capturing the movement of the option price relative to the movement in the asset price. Elasticity is a relative measure and, as such, is more appropriate when dealing with rates of return.

The elasticity of a standard European call is at least equal to 1.4 This means that the. absolute value of the option return will exceed the absolute value of the asset return. The elasticity of an option is often denoted with the Greek letter omega. $\varOmega$ . Thus, our equation for the return on the option is.

$$
\frac{\Delta c}{c}=r+\left(\frac{\Delta S}{S}-r\right)\Omega.
$$

Now with this result, we can examine the expected return on the option. Taking the expectation of this equation, we obtain.

$$
E\Big(\frac{\Delta c}{c}\Big)=r+\left[E\Bigg(\frac{\Delta S}{S}\Bigg)-r\right]\Omega.
$$

The left-hand side,. $E(\Delta c/c)$ , is the expected return on the call, which we denote as $E\big(R_{c}\big)$ Within the right-hand side, the term. $E(\Delta S/S)$ is the expected return on the asset, which we denote as $E\big(R_{S}\big)$ . Now we have a simple equation for the expected return on the call:

$$
\begin{array}{r}{E\big(R_{c}\big)=r+\big(E\big(R_{s}\big)-r\big)\Omega.}\end{array}
$$

We see that the expected return on the call equals the risk-free rate plus the risk premium on the underlying asset times the elasticity of the option. This functional form is very appealing and intuitive. The option's expected return at a minimum is the risk-free rate and is increased by a risk premium, which is the product of the risk premium on the asset and the risk of the option relative to the asset. We can also write this as

$$
E\big(R_{c}\big)=r+\big[E\big(R_{s}\big)-r\big]\frac{\partial c}{\partial S}\Bigg(\frac{S}{c}\Bigg).
$$

Now let us try to determine the volatility of the option.
