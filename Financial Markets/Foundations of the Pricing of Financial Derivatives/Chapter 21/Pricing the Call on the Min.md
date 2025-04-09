# 21.2 PRICING THE CALL ON THE MIN

Suppose the terminal payout on the call on the min is as given in Equation (21.1). Now suppose our two assets follow the standard lognormal diffusions,

$$
\begin{array}{l}{\displaystyle\frac{d S_{1}}{S_{1}}=\alpha_{1}d t+\sigma_{1}d W_{1}}\ {~}\ {\displaystyle\frac{d S_{2}}{S_{2}}=\alpha_{2}d t+\sigma_{2}d W_{2},}\end{array}
$$

where $\alpha_{i}$ and $\sigma_{i}$ are the drift and volatility of asset $i_{\cdot}$ and $d\mathbb{W}_{i}$ is the Wiener process driving. asset $i_{\cdot}$ with $i=1,2$ The correlation between assets 1 and 2 is $\rho_{12}$ . Note that $c_{m i n}$ is a function of. $S_{1},S_{2}$ , and $t.$ . Thus, based on Ito's lemma, we know

$$
\begin{array}{r l}&{d c_{\operatorname*{min}}=\left[\frac{\partial c_{\operatorname*{min}}}{\partial t}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}\alpha_{1}S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}\alpha_{2}S_{2}}\right.}\ &{\left.+\frac{1}{2}\left(\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}^{2}}\sigma_{1}^{2}S_{1}^{2}+\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{2}^{2}}\sigma_{2}^{2}S_{2}^{2}+2\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}\partial S_{2}}\sigma_{1}S_{1}\sigma_{2}S_{2}\rho_{12}\right)\right]d t}\ &{\quad+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}\sigma_{1}S_{1}d W_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}\sigma_{2}S_{2}d W_{2}.}\end{array}
$$

Consider a hedged portfolio where we are short one call on the minimum and long $(\partial c_{\mathrm{min}}/\partial S_{1})$ shares of $S_{1}$ and also long $(\partial c_{\operatorname*{min}}/\partial S_{2})$ shares of $S_{2}$ . Thus, the current value of the portfolio,. $V$ , is

$$
V=-c_{\operatorname*{min}}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}S_{2}.
$$

Now let us assume constant dividend yields and denote them. $\delta_{1}$ and $\delta_{2}$ . Recall the dividend is assumed to be paid continuously based on the current asset price. Thus, the change in portfolio value is

$$
d V=-d c_{\operatorname*{min}}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}d S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}d S_{2}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}\delta_{1}S_{1}d t+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}\delta_{2}S_{2}d t.
$$

Substituting, we have

$$
\begin{array}{r}{d V=-\left\{\left[\begin{array}{l}{\frac{\partial c_{\mathrm{min}}}{\partial t}+\frac{\partial c_{\mathrm{min}}}{\partial S_{1}}\alpha_{1}S_{1}+\frac{\partial c_{\mathrm{min}}}{\partial S_{2}}\alpha_{2}S_{2}}\ {+\frac{1}{2}\left(\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{1}^{2}}\sigma_{1}^{2}S_{1}^{2}+\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{2}^{2}}\sigma_{2}^{2}S_{2}^{2}+2\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{1}\partial S_{2}}\sigma_{1}S_{1}\sigma_{2}S_{2}\rho_{12}\right)}\ {+\frac{\partial c_{\mathrm{min}}}{\partial S_{1}}\delta_{1}S_{1}+\frac{\partial c_{\mathrm{min}}}{\partial S_{2}}\delta_{2}S_{2}}\ {+\frac{\partial c_{\mathrm{min}}}{\partial S_{1}}\sigma_{1}S_{1}d W_{1}+\frac{\partial c_{\mathrm{min}}}{\partial S_{2}}\sigma_{2}S_{2}d W_{2}}\ {+\frac{\partial c_{\mathrm{min}}}{\partial S_{1}}(\alpha_{1}S_{1}d t+\sigma_{1}S_{1}d W_{1})+\frac{\partial c_{\mathrm{min}}}{\partial S_{2}}\left(\alpha_{2}S_{2}d t+\sigma_{2}S_{2}d W_{2}\right).}\end{array}\right]d t\right\}}\end{array}
$$

Similar to many other derivations, many terms cancel and we have

$$
\begin{array}{r}{d V=-\left[\frac{\partial c_{\mathrm{min}}}{\partial t}+\frac{1}{2}\left(\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{1}^{2}}\sigma_{1}^{2}S_{1}^{2}+\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{2}^{2}}\sigma_{2}^{2}S_{2}^{2}+2\frac{\partial^{2}c_{\mathrm{min}}}{\partial S_{1}\partial S_{2}}\sigma_{1}S_{1}\sigma_{2}S_{2}\rho_{12}\right)\right]d t.}\ {\left.+\frac{\partial c_{\mathrm{min}}}{\partial S_{1}}\delta_{1}S_{1}+\frac{\partial c_{\mathrm{min}}}{\partial S_{2}}\delta_{2}S_{2}\right.}\end{array}
$$

Because the portfolio is risk free, we also know that

$$
d V=r V d t=r\left(-c_{\operatorname*{min}}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}S_{2}\right)d t.
$$

Setting these two expressions equal and canceling the $d t$ term, we have

$$
\begin{array}{r l}&{r\left(-c_{\operatorname*{min}}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}S_{2}\right)}\ &{=-\left[\frac{\partial c_{\operatorname*{min}}}{\partial t}+\frac{1}{2}\left(\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}^{2}}\sigma_{1}^{2}S_{1}^{2}+\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{2}^{2}}\sigma_{2}^{2}S_{2}^{2}+2\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}\partial S_{2}}\sigma_{1}S_{1}\sigma_{2}S_{2}\rho_{12}\right)\right].}\ &{\quad\quad+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}\delta_{1}S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}\delta_{2}S_{2}}\end{array}
$$

Rearranging in a more familiar form, we have the two-asset PDE,

$$
\begin{array}{l}{{r c_{\operatorname*{min}}=\displaystyle\frac{\partial c_{\operatorname*{min}}}{\partial t}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{1}}(r-\delta_{1})S_{1}+\frac{\partial c_{\operatorname*{min}}}{\partial S_{2}}(r-\delta_{2})S_{2}}}\ {{\displaystyle~+\frac{1}{2}\left(\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}^{2}}\sigma_{1}^{2}S_{1}^{2}+\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{2}^{2}}\sigma_{2}^{2}S_{2}^{2}+2\frac{\partial^{2}c_{\operatorname*{min}}}{\partial S_{1}S_{2}}\sigma_{1}S_{1}\sigma_{2}S_{2}\rho_{12}\right).}}\end{array}
$$

Thus, we seek a solution to this PDE that satisfies the boundary conditions.2

Recall from Chapter 13 that the univariate Feynman-Kac theorem provides a link between the PDE solution and the expectations solution. There is a multivariate version that provides the same link that can be applied here. Appendix 21.A provides a formal

expression of the multivariate Feynman-Kac theorem. Thus, based on the multivariate Feynman-Kac theorem, we know

$$
S_{i T}=S_{i t}e^{\left(r_{c}-\delta_{i}-\frac{\sigma_{i}^{2}}{2}\right)\tau+\sigma_{i}\sqrt{\tau}\varepsilon_{i}};i=1,2\mathrm{~and}
$$

$$
\begin{array}{r l r}{\lefteqn{c_{\mathrm{min},t}=e^{-r_{c}\tau}E_{t}(c_{\mathrm{min},T})}}\ &{}&{=e^{-r_{c}\tau}\displaystyle\int_{0}^{\infty}\int_{0}^{\infty}\operatorname*{max}\left[0,\operatorname*{min}\left(S_{1T}S_{2T}\right)-X\right]f\left(S_{1T},S_{2T}\right)d S_{1T}d S_{2T}.}\end{array}
$$

Solving the double integral based on the bivariate normal distribution, we have the minmax option model.

The call on minimum option model can be expressed as3

$$
\begin{array}{r l}&{c_{\operatorname*{min},t}=S_{1}e^{-\delta_{1}\tau}N_{2}\left(d_{11},d_{3},\frac{\sigma_{2}\rho-\sigma_{1}}{\sigma}\right)}\ &{\hphantom{x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x}}\ &{\hphantom{x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x}+S_{2}e^{-\delta_{2}\tau}N_{2}\left(d_{21},d_{4},\frac{\sigma_{1}\rho-\sigma_{2}}{\sigma}\right)-X e^{-r_{c}\tau}N_{2}(d_{12},d_{22},\rho),}\end{array}
$$

where

$$
\begin{array}{l}{{\sigma^{2}\equiv\sigma_{1}^{2}+\sigma_{2}^{2}-2\rho_{12}\sigma_{1}\sigma_{2},}}\ {{{}}}\ {{d_{11}\equiv\displaystyle\frac{\ln\left(\frac{S_{1}}{X}\right)+\left(r_{c}-\delta_{1}+\frac{\sigma_{1}^{2}}{2}\right)\tau}{\sigma_{1}\sqrt{\tau}},}}\end{array}
$$

$$
d_{12}\equiv\frac{\ln\left(\frac{S_{1}}{X}\right)+\left(r_{c}-\delta_{1}-\frac{\sigma_{1}^{2}}{2}\right)\tau}{\sigma_{1}\sqrt{\tau}}=d_{11}-\sigma_{1}\sqrt{\tau},
$$

$$
d_{21}\equiv\frac{\ln\left(\frac{S_{2}}{X}\right)+\left(r_{c}-\delta_{2}+\frac{\sigma_{2}^{2}}{2}\right)\tau}{\sigma_{2}\sqrt{\tau}},
$$

$$
d_{22}\equiv\frac{\ln\left(\frac{S_{2}}{X}\right)+\left(r_{c}-\delta_{2}-\frac{\sigma_{2}^{2}}{2}\right)\tau}{\sigma_{2}\sqrt{\tau}}=d_{21}-\sigma_{2}\sqrt{\tau},
$$

$$
d_{3}\equiv\frac{\ln\left(\frac{S_{2}}{S_{1}}\right)+\left(\delta_{1}-\delta_{2}-\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}},\mathrm{and}
$$

$$
d_{4}\equiv\frac{\ln\left(\frac{S_{1}}{S_{2}}\right)+\left(\delta_{1}-\delta_{2}-\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}=-d_{3}-\sigma\sqrt{\tau}.
$$

Note the call on maximum can be found based on Equation (21.3). Further, the put on max is found based on Equation (21.8) and the put on min is found based on Equation (21.6)..

We draw several interesting insights from the following figures generated based on the min-max option model presented here. The base parameters used in these figures are as follows: $S_{1}=100$ $S_{2}=100$ $\delta_{1}=0$ $\delta_{2}=0$ $\sigma_{1}=30\%$ $\sigma_{2}=30\%$ $\rho=0.7$ $X=100$ $r_{c}=$ $5\%$ , and $\tau=1$ year.

Figure 21.1 illustrates the sensitivity of min-max options with respect to changes in. asset price 2 $(S_{2})$ . Note that as asset price 2 declines, the call on max converges to the. Black-Scholes-Merton call value for asset 1 (14.23 with these parameters), the put on the max converges to the Black-Scholes-Merton put value for asset 1 (9.35 with these parameters), the call on the min converges to zero, and the put on the min converges to the lower boundary condition for asset 2. Further, as asset price 2 increases, the call on min con-. verges to the Black-Scholes-Merton call value for asset 1, the put on the min converges to the Black-Scholes-Merton put value, the call on the max converges to the lower boundary. condition for asset 2, and the put on the max converges to zero..

Figure 21.2 illustrates the sensitivity of min-max options with respect to changes in the correlation between asset 1 and asset 2. Note that as the correlation declines, the call on max and the put on the min increase in value as the likelihood of favorable moves in one of the two assets increases due to the lower correlation. Further, the call on the min and the put on the max decrease in value as the likelihood of an unfavorable move in one of the two assets increases. Further, note that as the correlation tends to $+1$ , the call on the min and call on the max converge to the Black-Scholes-Merton call value (14.23, same for both underlying calls) and the put on the min and put on the max converge to the Black-Scholes-Merton put value (9.35, same for both underlying puts).

![](8356555bee48f614fc675030576bd86ecb20cf2ab08fd515f924f861d52b4211.jpg)
Figure 21.3 illustrates the sensitivity of min-max options with respect to changes in the time to expiration. The familiar time value decay is evident with all four min-max options
FIGURE 21.1 Min-Max Option Value Sensitivity to Asset Price 2

![](9b484f51222b48b2aced3c381aaae67a71e0c89312e536db6d34b5fc83579e8d.jpg)
FIGURE 21.2  Min-Max Option Value Sensitivity to Correlation

![](6974ad10f4e05c6c3aa98afccdc3716c8e257e1b0ba1ca6ec4041766758b94c4.jpg)
FIGURE 21.3  Min-Max Option Value Sensitivity to Time to Expiration

converging to zero as time to expiration tends toward zero. The call on the max and the put on the min have greater time value decay because they have greater value for longer maturities.

![](ec1a6e5b62c3f8b02c87a9f3f22237ec34de01d78443b61985c4731aae46652a.jpg)
FIGURE 21.4 Min-Max Option Value Sensitivity to Asset 2 Volatility

Figure 21.4 illustrates the sensitivity of min-max options with respect to changes in asset 2 volatility. As asset 2 volatility tends toward zero, the put on the min converges to the Black-Scholes-Merton put value for asset 1 and the put on the max converges to zero. Min-max call options are less transparent. When volatility converges to zero, the Black-Scholes-Merton call value converges to the lower bound, which in this case is positive (asset price 2 less the present value of the exercise price). Based on Equation (21.3), we know the sum of min-max call options should equal the sum of the underlying calls. Thus, we observe a nonzero call on min and a call on max in excess of the BlackScholes-Merton call value (14.23).
