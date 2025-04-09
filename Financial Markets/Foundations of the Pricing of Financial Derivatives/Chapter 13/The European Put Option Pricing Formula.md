# 13.2 THE EUROPEAN PUT OPTION PRICING FORMULA

The model for pricing a European put is easily derived from put-call parity. We know that

$$
\begin{array}{r}{p=c-S+X e^{-r_{c}\tau}.}\end{array}
$$

We can then substitute into Equation (13.15) for $c$ from the Black-Scholes-Merton formula, Equation (13.12) to obtain

$$
\begin{array}{r}{\dot{P}=X e^{-r_{c}\tau}N\big(-d_{2}\big)-S N\big(-d_{1}\big).}\end{array}
$$

Alternatively, the put option pricing model can be derived by setting up a risk-free. hedge involving the holding of $b$ units of the asset while being long one put. The deriva-. tion would proceed exactly as in the call option pricing model derivation, except that the boundary condition would be $\begin{array}{r}{p_{T}=\operatorname*{max}\bigl(0,X-\bar{S_{T}}\bigr)}\end{array}$ , and the hedge ratio $b$ would be found to be $\partial p/\partial S$ . From put-call parity, Equation (13.15), we can see that. $\partial p/\partial S=\partial c/\partial S-1$

Interestingly, Rubinstein (1991b) has shown that the Black-Scholes-Merton call and put models can be written compactly as

$$
\nu=\imath S N(\imath d)-\imath X e^{-r_{c}\tau}N\Big[\imath\Big(d-\sigma\sqrt{\tau}\Big)\Big]
$$

where

$$
\begin{array}{c}{d=\frac{\ln{\left(\frac{S}{X}\right)}+\left(r_{c}+\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}}\ {\iota=\left\{+1\mathrm{for}\mathrm{call}}\ {-1\mathrm{for}\mathrm{put},}\end{array}\right.}\end{array}
$$

where $\nu$ is the value of the option, whether a call or a put.

Once the Black-Scholes-Merton equation is found, one can determine the partial. derivatives, which can then be substituted back into the partial differential equation to verify that the solution is correct. In Chapter 14, we examine the comparative statics of the Black-Scholes-Merton option pricing model and use these derivatives to verify the. solution.
