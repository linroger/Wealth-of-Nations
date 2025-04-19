---
tags:
  - '#abm_model'
  - '#arithmetic_brownian_motion'
  - '#black_scholes_merton_formula'
  - '#boundary_conditions'
  - '#geometric_drift'
  - '#model_validation'
  - '#nonnegativity_constraints'
  - '#partial_differential_equation'
---
# 14.4 VERIFYING THE SOLUTION OF THE PARTIAL DIFFERENTIAL EQUATION

Now that we have the three necessary partial derivatives--Equations (14.18), (14.19), and (14.23)-we can substitute them into Equation (14.2):

$$
r_{c}S N\left(d_{1}\right)-\frac{\sigma S n\left(d_{1}\right)}{2\sqrt{\tau}}-r_{c}X e^{-r_{c}\tau}N(d_{2})+\frac{1}{2}n(d_{1})\frac{1}{S\sigma\sqrt{\tau}}\sigma^{2}S^{2}=r_{c}c
$$

$$
\begin{array}{l}{{r_{c}c=r_{c}S N\left(d_{1}\right)-r_{c}X e^{-r_{c}\tau}N(d_{2})-\displaystyle\frac{\sigma S}{2\sqrt\tau}n(d_{1})+\frac{\sigma S}{2\sqrt\tau}n(d_{1})}}\ {{\mathrm{}~}}\ {{\quad c=S N\left(d_{1}\right)-X e^{-r_{c}\tau}N(d_{2}).}}\end{array}
$$

And the end result is the Black-Scholes-Merton formula.

Recall for arithmetic Brownian motion with geometric drift, the PDE can be expressed as

$$
r_{c}S{\frac{\partial c}{\partial S}}+{\frac{\partial c}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}c}{\partial S^{2}}}\sigma^{2}=r_{c}c.
$$

Further, recall that the resultant call value is

$$
c_{t}=(S_{t}-X e^{-r_{c}(T-t)})N\big(d_{n}\big)+\sigma\sqrt{\frac{1-e^{-2r_{c}(T-t)}}{2r_{c}}}n\big(d_{n}\big),
$$

where

$$
d_{n}=\frac{S_{0}-X e^{-r_{c}(T-t)}}{\sigma\sqrt{\frac{1-e^{-2r_{c}(T-t)}}{2r_{c}}}}.
$$

It can be shown, based on the ABM model, that

$$
\begin{array}{r l}&{\frac{\partial c}{\partial S}=N(d_{n})\mathrm{(delta)}}\ &{\frac{\partial^{2}c}{\partial S^{2}}=\frac{n(d_{n})}{\sigma\sqrt{\frac{1-e^{-2r_{c}(T-t)}}{2r_{c}}}}\mathrm{(gamma)}}\ &{\frac{\partial C}{\partial t}=-r_{c}X e^{-r_{c}(T-t)}N(d_{n})-\frac{\sigma e^{-2r_{c}(T-t)}}{2\sqrt{\frac{1-e^{-2r_{c}(T-t)}}{2r_{c}}}}n(d_{n})\mathrm{(theta)}.}\end{array}
$$

Substituting delta, gamma, and theta into the ABM PDE will result in Equation (14.26), and we have

$$
\begin{array}{r l}&{r_{c^{\star}t}=-r_{c}X e^{-r(T-t)}\mathrm{N}(d_{n})-\frac{\sigma e^{-2r_{c}(T-t)}}{2\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r_{c}}}}n(d_{n})+r_{c}\left[\mathrm{N}(d_{n})\right]S+\frac{1}{2}\sigma^{2}\Bigg[\frac{n(d_{n})}{\sigma\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r_{c}}}}n(d_{n})}\ &{\qquad=r_{c}S(d_{n})-r_{c}X e^{-r(T-t)}\mathrm{N}(d_{n})-\frac{\sigma e^{-2r_{c}(T-t)}n(d_{n})}{2\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r}}}+\frac{\sigma n(d_{n})}{2\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r_{c}}}}}\ &{\qquad=r_{c}(S-X e^{-r_{c}(T-t)})\mathrm{N}(d_{n})+\frac{\sigma n(d_{n})}{\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r_{c}}}}\frac{(1-e^{-r_{c}(T-t)})}{2}}\ &{\qquad=r_{c}\left(S-X e^{-r_{c}(T-t)}\right)\mathrm{N}(d_{n})+r_{c}\sigma\sqrt{\frac{1-e^{-r_{c}(T-t)}}{2r_{c}}}n(d_{n}).\qquad}&{\qquad(14.}\end{array}
$$

Therefore, we have verified that both the Black-Scholes-Merton and ABM models satisfy their respective partial differential equations. To further validate these models, one must confirm that boundary conditions and nonnegativity constraints are satisfied. See Chapter 13, Section 7, for the limiting argument for the Black-Scholes-Merton model.
