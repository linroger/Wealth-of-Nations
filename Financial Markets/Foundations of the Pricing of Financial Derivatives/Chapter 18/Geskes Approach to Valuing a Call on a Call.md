# 18.4 GESKE'S APPROACH TO VALUING A CALL ON A CALL

Geske uses the principle of risk-neutral valuation to price a stock option. Due to his focus solely on a call option on a stock, we follow his notation where $c$ denotes the call option, S denotes the common stock price, and $V$ denotes the firm value per share. Note we follow Geske's notation only in this section and will revert back to the more generic notation in the next section. Remember, our focus here is on valuing a call option on a stock as a compound option on the firm. Specifically, he evaluates the expression

$$
{{c}_{t}}={{e}^{-{{r}_{c}}{{\tau}_{1}}}}E\left\{\operatorname*{max}\left[0,{{S}_{1}}\left({{V}_{1}}\right)-X\right]\right\}.
$$

This expression means that we find the expected payoff of the call at its expiration, time $T_{1}$ , and discount it to the present. The expected payoff of the call is based on the stock price at $T_{1}$ , which is a function of the value of the firm at. $T_{1}$ . More formally, the expression. to be evaluated is8

$$
{{c}_{t}}={{e}^{-{{r}_{c}}{{\tau}_{1}}}}\int_{-\infty}^{\infty}{\operatorname*{max}\left[0,{{S}_{1}}\left(V{{e}^{u}}\right)-X\right]{{f}_{\left(u\right)}}d u},
$$

where

$$
\begin{array}{r}{u=\ln{\left(V_{1}/V_{t}\right)}}\ {f(u)=\frac{e^{-\frac{q^{2}}{2}}}{\sigma_{V}\sqrt{2\pi\tau_{1}}}}\ {q=\frac{u-\mu_{V}\tau_{1}}{\sigma_{V}\sqrt{\tau_{1}}}}\ {\mu_{V}=r_{c}-\sigma_{V}^{2}/2.}\end{array}
$$

These expressions arise from the fact that the value of the assets,. $V_{1}$ , is assumed to be lognormally distributed and the expected return is set to the risk-free rate.

Now the problem can be broken down into three parts that have logical interpretations. If the option expires in-the-money at. $T_{1}$ , the holder will exercise it and obtain a. position in the stock. When the bonds mature at. $T_{2}$ , the stock value behaves like an ordi-. nary call with a payoff equal to the expected value of the assets conditional on the bonds being paid off minus the expected payoff on the bonds. Thus, the value of the compound call can be expressed as the sum of three option parts:.

(OP1) The value today of the assets of the firm at. $T_{1}$
(OP2) The value today of the payment of the exercise price, $M$ , on the compound option
(OP3) The value today of the payment of the exercise price, $X$ , on the underlying,. meaning, the payoff of the bonds.

Each of these values is conditional on the compound option being exercised at $T_{1}$ . These three values are written formally as.

$$
\begin{array}{r l}{\lefteqn{V e^{-r_{c}\tau_{1}}\sum_{\mathrm{ln}(V^{*}/V)}^{\infty}e^{u}N(z)f(u)d u}}\ {\le}&{\displaystyle\operatorname*{ln}_{\mathrm{ln}(V^{*}/V)}\sum_{\mathrm{\ensuremath{\left/vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}^{\infty}\sum_{\mathrm{\ensuremath{\left/\vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}^{\infty}N\left(z-\sigma_{V}\sqrt{\tau_{12}}\right)f(u)d u}\ &{\displaystyle\operatorname*{ln}_{\mathrm{\ensuremath{\left/\vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}\sum_{\mathrm{\ensuremath{\left/\vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}^{\infty}f(u)d u}\ {\displaystyle\sum_{\mathrm{\ensuremath{\left/\vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}\sum_{\mathrm{\ensuremath{\left/\vphantom{\frac{r}{c}\tau_{1}}\right.\kern-\nulldelimiterspace}M}}^{\infty}f(u)d u}\end{array}
$$

where

$$
z=\frac{\left(\ln{(V^{*}/M)}+\left(r_{c}+\sigma_{V}^{2}/2\right)\tau_{12}\right)}{\sigma_{V}\sqrt{\tau_{12}}}.
$$

The term $\boldsymbol{V}^{*}$ is the critical value of the assets at $T_{1}$ at which the equity would be sufficiently valuable to have the call option expire at-the-money. It can be found by solving the following equation for $V^{*}$

$$
V^{\ast}N\left(z\right)-M e^{-r_{c}\tau_{12}}N\left(z-\sigma_{V}\sqrt{\tau_{12}}\right)=X.
$$

Observe that the left-hand solution of Equation (18.39) is the Black-Scholes-Merton value of the underlying option at the point at which the compound option is expiring. Note that the exercise price is the amount owed on the bond at time. $T_{2}$ , and the volatility is the volatility of the assets. The right-hand solution is the exercise price of the compound option. We are finding the value at the expiration of the compound option that forces the value of the underlying option to equal its exercise value. In other words, if the underlying. is above this level, the compound option will exercise and convert to the stock, which then proceeds as an ordinary call option on the assets that will expire at. $T_{2}$

The values of the option parts, (OP1), (OP2), and (OP3), are as follows:

$$
\begin{array}{l}{{V N_{2}\left(x,y;\rho\right)}}\ {{}}\ {{M e^{-r_{c}\tau_{2}}N_{2}\left(x-\sigma_{V}\sqrt{\tau_{1}},y-\sigma_{V}\sqrt{\tau_{2}};\rho\right)}}\ {{}}\ {{X e^{-r_{c}\tau_{1}}N_{1}\left(x-\sigma_{V}\sqrt{\tau_{1}}\right)}}\end{array}
$$

where

$$
\begin{array}{l}{x=\cfrac{\ln{(V/V^{*})}+\left(r_{c}+\sigma_{V}^{2}/2\right)\tau_{1}}{\sigma_{\nu}\sqrt{\tau_{1}}}}\ {y=\cfrac{\ln{(V/M)}+\left(r_{c}+\sigma_{V}^{2}/2\right)\tau_{2}}{\sigma_{\nu}\sqrt{\tau_{2}}}}\ {\rho=\sqrt{\tau_{1}/\tau_{2}}.}\end{array}
$$

Note that $N_{2}\left(.,.,.\right)$ is the bivariate normal probability and reflects the likelihood of both events occurring. The two events are exercise of the compound option and exercise of the underlying option. The overall price of the compound option is $(\mathrm{OP1})-(\mathrm{OP2})-(\mathrm{OP3})$
