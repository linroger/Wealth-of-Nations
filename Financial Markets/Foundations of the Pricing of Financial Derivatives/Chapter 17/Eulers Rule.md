# 17.3 EULER'S RULE

Functions that are homogeneous of degree one are referred to as linearly homogeneous, and this property is called linear homogeneity. The Swiss mathematician Leonhard Euler proved that linearly homogeneous functions have the property that.

$$
x\frac{\partial f}{\partial x}+y\frac{\partial f}{\partial y}=f(x,y),
$$

which is called Euler's rule.

In economics, this special characteristic is used to describe production functions that. have constant returns to scale. That is, if an economic output changes by a factor $\lambda$ when the inputs change by the factor $\lambda$ , then we say that the production function has constant. returns to scale. This type of production function is relatively simple and convenient to use, and so it appears often in microeconomic models. Typically the inputs are capital. $(K)$ and labor $(L)$

For example, consider the economic production function

$$
\begin{array}{r}{Q=A K^{\alpha}L^{1-\alpha};A>0;0<\alpha<1,}\end{array}
$$

where $A$ is a scalar. Clearly, this economic production function is homogeneous of degree one with respect to capital and labor because

$$
\widehat{\cal Q}=A(\lambda K)^{\alpha}(\lambda L)^{1-\alpha}=A\lambda K^{\alpha}L^{1-\alpha}.
$$

Further, note that if we define $f(K,L)\equiv A K^{\alpha}L^{1-\alpha}$ , then

$$
K\frac{\partial f}{\partial K}+L\frac{\partial f}{\partial L}=K\alpha\frac{A K^{\alpha}L^{1-\alpha}}{K}+L(1-\alpha)\frac{A K^{\alpha}L^{1-\alpha}}{L}=A K^{\alpha}L^{1-\alpha}=f(K,L).
$$

Thus, we see that this production function is linearly homogeneous and therefore satisfies Euler's rule.
