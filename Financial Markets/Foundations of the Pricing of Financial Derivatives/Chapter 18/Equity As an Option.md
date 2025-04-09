# 18.1 EQUITY AS AN OPTION

Let us start by assuming the existence of a corporation that has a single issue of zero-coupon debt due at time $T_{2}$ . We define the following terms:

$\mathbf{}V_{t}$ : value of the firm's assets at time $t_{\perp}$
$M=X_{U}$ : face value of zero-coupon debt issued by the firm and maturing at time $T_{2}$ $S_{t}$ : market value of the stock of the firm at time $t$ and
$\sigma_{V}=\sigma$ : volatility of the log return of the assets of the firm.

Again, we continue to use $r_{c}$ as the risk-free rate and the maturity of the debt in years is $\tau_{2}$ . As Black and Scholes demonstrated, the equity is an option on the assets with payoff at $T_{2}$ of $\mathrm{max}\left(0,{{V}_{{{T}_{2}}}}-M\right)$ . That is, at time $T_{2}$ , if the stockholders pay off the creditors in the amount of their claim, $M$ they retain their own claim on the assets worth $V_{T_{2}}$ Thus, when the debt matures and the value of the firm is large enough to avert default, the stock is worth $V_{T_{2}}-M$ . When the value of the assets is below the value of the debt, the stockholders will default, and their claim is worth nothing. Hence, the stock is like a call option with a payoff of max $\left(0,V_{T_{2}}-M\right)$ . If the return on the assets can be expressed with the lognormal diffusion,

$$
\frac{d V_{t}}{V_{t}}=\alpha_{V}d t+\sigma_{V}d\mathrm{W}_{t},
$$

and the usual Black-Scholes-Merton assumptions are met, the equity can be valued as

$$
\begin{array}{l}{{S_{t}=V_{t}N\left(d_{1}\right)-M e^{-r_{c}\tau_{2}}N\left(d_{2}\right)}}\ {{\mathrm{}}}\ {{d_{1}=\displaystyle\frac{\ln{\left(V_{t}/M\right)}+\left(r_{c}+\sigma_{V}^{2}/2\right)\tau_{2}}{\sigma_{V}\sqrt{\tau_{2}}}}}\ {{d_{2}=d_{1}-\sigma_{V}\sqrt{\tau_{2}}.}}\end{array}
$$

This result is straightforward. We simply view the equity through the lens of an ordinary option in which the underlying is represented by the assets of the firm. But what if there is an option on the equity? Until now, we would value this option using the Black-Scholes-Merton model, but now we see that the option should be valued in a more meaningful way, one in which the volatility is not constant as would be the case if the firm had leverage.

Also, recall from Chapter 13 that $N\left(d_{2}\right)$ is the probability of the call option expiring in-the-money under the risk-neutral measure. Thus, the value of viewing equity as an option is immediately transparent as $N\left(d_{2}\right)$ is the probability of the firm paying off its debts when they mature under the risk-neutral measure. Alternatively, $1-N\left(d_{2}\right)$ is the probability of the firm not being able to pay off its debts when they mature under the risk-neutral measure. There have been many applications of this perspective, including appraising credit risk. See, for example, the widely popular KMV model.2
