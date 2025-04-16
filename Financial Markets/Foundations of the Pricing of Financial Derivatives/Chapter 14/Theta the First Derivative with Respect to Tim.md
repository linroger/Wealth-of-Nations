---
tags:
  - '#call_option'
  - '#mathematical_formula'
  - '#option_pricing'
  - '#partial_derivative'
  - '#theta_derivative'
  - '#time_to_expiration'
---
# 14.3 THETA: THE FIRST DERIVATIVE WITH RESPECT TO TIME

Now we need the derivative with respect to time to expiration.

$$
\begin{array}{l}{{\displaystyle\frac{\partial c}{\partial\tau}=S\frac{\partial N\left(d_{1}\right)}{\partial d_{1}}\frac{\partial d_{1}}{\partial\tau}-X e^{-r_{c}\tau}\frac{\partial N\left(d_{2}\right)}{\partial d_{2}}\frac{\partial d_{2}}{\partial\tau}+r_{c}N(d_{2})X e^{-r_{c}\tau}}}\ {{\mathrm{}=S n\left(d_{1}\right)\frac{\partial d_{1}}{\partial\tau}-X e^{-r_{c}\tau}n(d_{2})\frac{\left(\partial d_{1}-\sigma\sqrt{\tau}\right)}{\partial\tau}+r_{c}N(d_{2})X e^{-r_{c}\tau}}}\ {{\mathrm{}=S n\left(d_{1}\right)\frac{\partial d_{1}}{\partial\tau}-X e^{-r_{c}\tau}n(d_{2})\frac{\partial d_{1}}{\partial\tau}+X e^{-r_{c}\tau}n(d_{2})\frac{\sigma}{2\sqrt{\tau}}+r_{c}N(d_{2})X e^{-r_{c}\tau}.}}\end{array}
$$

Based on Equation (14.6), we know the first two terms cancel and we obtain

$$
\frac{\partial c}{\partial\tau}=\frac{\sigma X e^{-r_{c}\tau}}{2\sqrt{\tau}}n(d_{2})+r_{c}X e^{-r_{c}\tau}N(d_{2}).
$$

Based again on Equation (14.6), we can express this result as

$$
\frac{\partial c}{\partial\tau}=\frac{\sigma S}{2\sqrt{\tau}}n(d_{1})+r_{c}X e^{-r_{c}\tau}N(d_{2}).
$$

Thus, the derivative with respect to time to expiration is clearly positive, which is intu-. itively consistent. A call option with a longer time to expiration is worth more. Generally speaking, however, we define theta as the derivative with respect to the point in time, that. is, $\partial c/\partial t$ Recall that we defined the time to expiration as $\tau=T-t.$ What we shall need in order to check the solution to the partial differential equation is. $\partial c/\partial t$ , but it is easy to see that $\partial c/\partial t=-\partial c/\partial\tau$ Hence,

$$
\Theta_{c}=\frac{\partial c}{\partial t}=-\frac{\sigma S}{2\sqrt{\tau}}n(d_{1})-r_{c}X e^{-r_{c}\tau}N(d_{2}).
$$

This formula is one way to express theta. Alternatively, one could compute the partial with respect to time to expiration.
