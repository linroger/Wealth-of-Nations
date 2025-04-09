# 18.7 GENERALIZED COMPOUND OPTION PRICING MODEL

Rubinstein (1991) generalizes the Geske result to accommodate the other possible compound options: a call on a put, a put on a call, and a put on a put, as well as the case of a continuous payout on the assets of $\delta$ . Brooks (2019) extends this generalized result to include a continuous payout on the underlying option of $\widehat{q}$ , which is not simply a trivial adjustment.

The generalized compound option pricing model, denoted $^{c o}$ , is observed at time $t$ under geometric Brownian motion based on an underlying instrument, denoted $S_{t}$ . When compared to Geske's call on call model,. $S_{t}$ represents the firm value per share. The under-. lying option exercise price is denoted. $X_{U}$ and expires at time 2, denoted. $T_{2}$ . By comparison, the compound option exercise price is denoted. $X_{\mathrm{{C}}}$ and expires at time 1 $(T_{2}>T_{1})$ Mathematically, the generalized model can be expressed as

$$
\begin{array}{r l}&{c o\left(S,t,T_{1},T_{2},\iota_{C},\iota_{U}\right)=\iota_{C}\iota_{U}S_{t}e^{-\delta\tau_{2}}e^{\widehat{q}\tau_{12}}N_{2}\left(\iota_{C}\iota_{U}d_{11},\iota_{U}d_{12};\iota_{C}\rho\right)}\ &{\qquad-\iota_{C}\iota_{U}X_{U}e^{-r_{c}\tau_{2}}e^{\widehat{q}\tau_{12}}N_{2}\left(\iota_{C}\iota_{U}d_{21},\iota_{U}d_{22};\iota_{C}\rho\right)}\ &{\qquad-\iota_{C}X_{C}e^{-r_{c}\tau_{1}}N\left(\iota_{C}\iota_{U}d_{21}\right),}\end{array}
$$

where indicator functions denote

$$
\begin{array}{r l}&{\imath_{C}=\left\{+1\mathrm{{if}c o m p o u n d c a l l o p t i o n}\right.}\ &{\left.\qquad-1\mathrm{{if}c o m p o u n d p u t o p t i o n}\right.}\ &{\imath_{U}=\left\{+1\mathrm{{if}u n d e r l y i n g c a l l o p t i o n}\right.}\ &{\left.\qquad-1\mathrm{{if}u n d e r l y i n g p u t o p t i o n}\right.\quad.}\end{array}
$$

The bivariate cumulative standard normal distribution is denoted

$$
N_{2}\left(a,b;\rho\right)\equiv\int_{-\infty-\infty}^{a}\int_{-\infty}^{b}\frac{\exp\left\{-\frac{z_{1}^{2}-2\rho z_{1}z_{2}+z_{2}^{2}}{2\left(1-\rho^{2}\right)}\right\}}{2\pi\sqrt{1-\rho^{2}}}d z_{1}d z_{2}.
$$

The correlation coefficient used in the bivariate distribution is

$$
\rho={\sqrt{\frac{\tau_{1}}{\tau_{2}}}}.
$$

Let $S_{T_{1}}^{*}$ be defined such that the underlying option is at-the-money or

$$
\iota_{U}S_{T_{1}}^{*}e^{-\delta\tau_{12}}N_{1}\left(\iota_{U}d_{1,T_{1},T_{2}}^{*}\right)-\iota_{U}X_{U}e^{-r_{c}\tau_{12}}N_{1}\left(\iota_{U}d_{2,T_{1},T_{2}}^{*}\right)-X_{C}=0,
$$

where

$$
d_{2,T_{1},T_{2}}^{*}=\frac{\ln\left(\frac{S_{1}^{*}}{X_{U}}\right)+\left(r_{c}-\delta-\frac{\sigma^{2}}{2}\right)\tau_{12}}{\sigma\sqrt{\tau_{12}}},
$$

$$
\begin{array}{r l}&{d_{1,T_{1},T_{2}}^{*}=\frac{\displaystyle\ln\left(\frac{S_{1}^{*}}{X_{U}}\right)+\left(r_{c}-\delta+\frac{\sigma^{2}}{2}\right)\tau_{12}}{\sigma\sqrt{\tau_{12}}}=d_{2,T_{1},T_{2}}^{*}+\sigma\sqrt{\tau_{12}},~\mathrm{and}}\ &{N_{1}\left(d\right)=\displaystyle\int_{-\infty}^{d}\frac{e^{-\frac{x^{2}}{2}}}{\sqrt{2\pi}}d x.}\end{array}
$$

Let $d_{i j}$ denote the upper limits used in the bivariate normal cumulative distribution function given in Equation (18.49), where. $i=1{,}2$ denotes whether the volatility term is added $(i=1)$ or subtracted $(i=2)$ and $j=1\AA,2$ denotes whether the evaluation is $S^{*}$ at $T_{1}$ $(j=1)$ or $X_{U}$ at $T_{2}(j=2)$ . We define

$$
\begin{array}{r l}&{d_{21}=\frac{\ln\left(\frac{\ S_{t}}{S_{1}^{\prime}}\right)+\left(r_{c}-\delta-\frac{\sigma^{2}}{2}\right)\tau_{1}}{\sigma\sqrt{\tau_{1}}},}\ &{d_{11}=\frac{\ln\left(\frac{S_{t}}{S_{1}^{\prime}}\right)+\left(r_{c}-\delta+\frac{\sigma^{2}}{2}\right)\tau_{1}}{\sigma\sqrt{\tau_{1}}}=d_{21}+\sigma\sqrt{\tau_{1}},}\ &{d_{22}\equiv\frac{\ln\left(\frac{S_{t}}{X_{0}}\right)+\left(r_{c}-\delta-\frac{\sigma^{2}}{2}\right)\tau_{2}}{\sigma\sqrt{\tau_{2}}},\mathrm{and}}\ &{d_{12}\equiv\frac{\ln\left(\frac{S_{t}}{X_{0}}\right)+\left(r_{c}-\delta+\frac{\sigma^{2}}{2}\right)\tau_{2}}{\sigma\sqrt{\tau_{2}}}=d_{22}+\sigma\sqrt{\tau_{2}}.}\end{array}
$$

Extending Merton (1974), Geske (1977, 1984) has adapted his compound option pricing model to the case of coupon paying corporate bonds. Most important, however, Roll (1977) and Whaley (1981) have used the compound option model to obtain a closed-form solution for the price of an American call, and we cover this topic in Chapter 19.
