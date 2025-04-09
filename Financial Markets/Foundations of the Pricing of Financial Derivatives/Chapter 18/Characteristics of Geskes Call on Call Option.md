# 18.5 CHARACTERISTICS OF GESKE'S CALL ON CALL OPTION

Geske also provides the derivatives of the compound call price with respect to the underlying variables $V,M,\tau_{2},r_{c},\sigma_{V},X_{:}$ and $\tau_{1}$ .9 These illustrate some interesting results. For example, $\partial c/\partial M<0$ , meaning that increasing the firm's leverage, which raises the variance of the equity, then increases the value of the call; however, the larger debt value combined with a fixed value of the assets lowers the value of the equity, which is the dominant effect. This lowers the call price.

Another interesting result is that the volatility of the stock is not constant. Define

$$
V=B+S.
$$

Then the total differential of Equation (18.41) is

$$
d V=\left({\frac{\partial V}{\partial B}}\right)d B+\left({\frac{\partial V}{\partial S}}\right)d S.
$$

Holding $d B$ to zero, we have. $d V=(\partial V/\partial S)d S$ Then write the equation as

$$
\begin{array}{l}{\displaystyle\frac{d V}{V}=\frac{\left(\frac{\partial V}{\partial S}\right)\left(\frac{d S}{V}\right)}{S/S}}\ {\displaystyle~=\left(\frac{\partial V}{\partial S}\right)\left(\frac{S}{V}\right)\left(\frac{d S}{S}\right).}\end{array}
$$

The volatility of the asset return, $\sigma_{V}$ , is, therefore,

$$
\sigma_{V}=\left({\frac{\partial V}{\partial S}}\right){\frac{S}{V}}\sigma_{S},
$$

where $\sigma_{S}$ is the volatility of $d S/S$ Turning this around, we have

$$
\sigma_{S}=\sigma_{V}\left({\frac{\partial S}{\partial V}}\right){\frac{V}{S}}.
$$

The stock volatility is, thus, seen as a function of the asset volatility and the firm's leverage, which is picked up in the elasticity factor, $(\partial S/\partial V)(V/S)$ .10 The significance of this result is that the volatility of the stock, which is what we would usually insert into the Black-Scholes-Merton model to obtain the call price, is definitely not constant as the. Black-Scholes-Merton model assumes. The volatility of the assets may well be constant, but the firm's leverage changes with any change in the market value of the equity relative to the market value of the assets.

The formulas for selected Greeks are provided in the appendix.

# 18.6 GESKE'S CALL ON CALL OPTION MODEL AND LINEAR HOMOGENEITY

Geske goes on to show that the compound option is linearly homogeneous with respect to the value of the firm, the face value of the debt, and the exercise price and that the compound option value is convex in the value of the firm. He also shows that if there is no debt, meaning that $M=0$ , the model will converge to the Black-Scholes-Merton formula. This will also occur if the bond is a perpetuity or if the option expiration coincides with. the bond maturity. In the latter case, the two exercise prices merge to $M+X$
