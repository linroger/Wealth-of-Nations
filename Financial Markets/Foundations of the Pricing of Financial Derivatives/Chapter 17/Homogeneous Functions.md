---
tags:
  - degree_zero
  - function_properties
  - homogeneous_functions
  - linear_homogeneity
  - mathematical_functions
  - variable_analysis
aliases:
  - Homogeneity
  - Homogeneous Function
key_concepts:
  - Degree of homogeneity
  - Homogeneity degree zero
  - Homogeneous function definition
  - Linear homogeneity example
  - Variable multiplication effect
---

# 17.2 HOMOGENEOUS FUNCTIONS

A function $f\left(x_{1},x_{2},\ldots,x_{n}\right)$ is said to be homogeneous of degree $k$ with respect to each variable,e $x_{1},x_{2},\ldots,x_{n}$ if the following condition holds

$$
f{\bigl(}\lambda x_{1},\lambda x_{2},\ldots,\lambda x_{n}{\bigr)}=\lambda^{k}f{\bigl(}x_{1},x_{2},\ldots,x_{n}{\bigr)}.
$$

An example of such a function is

$$
g(x,y,z)=2x^{2}+3y z-z^{2}.
$$

Here we see that it is homogeneous of degree two.

$$
\begin{array}{c}{{g(\lambda x,\lambda y,\lambda z)=2\lambda^{2}x^{2}+3\lambda^{2}y z-\lambda^{2}z^{2}}}\ {{{}}}\ {{{}=\lambda^{2}\bigl(2x^{2}+3y z-z^{2}\bigr).}}\end{array}
$$

What we did is multiply each variable by. $\lambda$ , and the result is the original function multiplied. by $\lambda^{2}$ . In that case, the function is homogeneous of degree two with respect to $x,y_{\mathrm{{:}}}$ and $z$

A function can be homogeneous with respect to fewer than the full number of variables in it. For example, from Equation (17.4), a function $f(x,y,z)$ is said to be homogeneous. of degree $k$ with respect to the variables. $x$ and $y$ if the following condition holds:.

$$
f(\lambda x,\lambda y,z)=\lambda^{k}f(x,y,z).
$$

In other words, if variables $x$ and $y$ are each increased by the factor $\lambda$ , and it leads to the function increasing by the factor $\lambda^{k}$ , then the function is said to be homogeneous of degree $k$ with respect to $x$ and $y$ Note that we did not increase $z$ by the factor A. Homogeneity is always expressed with respect to one or more variables.

The most fundamental case of homogeneity is degree zero. That is, if we multiply one or more variables by $\lambda^{0}$ , we naturally obtain the original function times $\lambda^{0}=1$ . In other words, the function does not change at all. Consider the simple function $f(x,y,z)=x z/y$ Then note what happens when we multiply. $x$ and $y$ by $\lambda$

$$
f(\lambda x,\lambda y,z)={\frac{\lambda x z}{\lambda y}}={\frac{x z}{y}}.
$$

This function is unaffected by changing. $x$ and $y$ by the factor $\lambda^{0}$ and is, thus, homogeneous. of degree zero with respect to. $x$ and $y$ . Note, however, that if we tried just $z_{:}$ we would get the result $x\lambda z/y$ , which is $\lambda x z/y$ , and the function is homogeneous of degree 1 with respect to $z_{\cdot}$ , but it is not homogeneous of degree 0.

For a case of linear homogeneity, or homogeneity of degree 1, consider the function

$$
f(x,y,z)=z{\sqrt{x y}}.
$$

It is homogeneous of degree one with respect to $x$ and $y$ because

$$
f(\lambda x,\lambda y,z)=z\sqrt{\lambda x\lambda y}=\lambda z\sqrt{x y}=\lambda f(x,y,z).
$$

With respect to $x,y$ and $z$ , however, it is homogeneous of degree two:

$$
f(\lambda x,\lambda y,\lambda z)=\lambda z\sqrt{\lambda x\lambda y}=\lambda^{2}z\sqrt{x y}=\lambda^{2}f(x,y,z).
$$
