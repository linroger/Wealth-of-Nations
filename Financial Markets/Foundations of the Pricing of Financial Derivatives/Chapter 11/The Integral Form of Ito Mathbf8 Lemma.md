# 11.4 THE INTEGRAL FORM OF ITO $\mathbf{8}$ LEMMA

Now let us develop Ito's lemma in integral form. Using stochastic integration applied to Equation (11.14), we have

$$
\int_{0}^{t}d F=\int_{0}^{t}{\frac{\partial F}{\partial j}}d j+\int_{0}^{t}{\frac{\partial F}{\partial x_{j}}}d x_{j}+\int_{0}^{t}{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x_{j}^{2}}}d x_{j}^{2}.
$$

This equation looks like it is going to be a problem because of the term $d x_{j}^{2}$ . In standard integration, we would see the term $d x_{j}$ but not $d x_{j}^{2}$ . So how do we handle this? We have previously noted that $d x_{t}^{2}=\sigma(x,t)^{2}d t$ . Using that result and combining terms gives

$$
F_{t}-F_{0}=\int_{0}^{t}\left[\frac{\partial F}{\partial j}+\frac{1}{2}\frac{\partial^{2}F}{\partial x_{j}^{2}}\sigma^{2}(x_{j},j)\right]d j+\int_{0}^{t}\frac{\partial F}{\partial x_{j}}d x_{j},
$$

which is Ito's lemma in integral formula and is sometimes called Ito's stochastic integral. Remember that either the differential or integral version of Ito's lemma automatically implies that the other exists, so either can be used, and in some cases, one is preferred over the other.

In Appendix 11A, we review several generalized stochastic integration results. Many of these results are useful when solving various financial problems with stochastic calculus. We turn now to additional applications of Ito's lemma..
