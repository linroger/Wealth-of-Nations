---
tags:
  - differential_equations
  - indefinite_integration
  - initial_conditions
  - ordinary_derivatives
  - partial_derivatives
aliases:
  - ODE
  - PDEs
key_concepts:
  - equation with derivative
  - indefinite integration method
  - initial/boundary conditions
  - ordinary differential equations
  - partial differential equations
  - solve differential equation
---

# 3.7 DIFFERENTIAL EQUATIONS

A differential equation is an equation that contains a derivative. The objective of solving a differential equation is to determine the original function whose derivative is given by the differential equation. Differential equations that contain only ordinary derivatives are called ordinary differential equations. Differential equations that contain partial derivatives are called partial differential equations.

Taking a derivative creates a differential equation. For example, the expression

$$
{\frac{d y}{d x}}=3q x^{4}
$$

is a differential equation. Oftentimes it is written as

$$
d y=3q x^{4}d x.
$$

The objective is to "solve" the differential equation, meaning to find the original function whose derivative is the differential equation. Solving differential equations can be very difficult. The one just shown is quite simple: We can use indefinite integration to obtain. the following:

$$
\begin{array}{c}{{\displaystyle\int d y=\int3q x^{4}d x=3q\int x^{4}d x}}\ {{\displaystyle y=\left(\frac{3q}{5}\right)x^{5}+a.}}\end{array}
$$

Note, however, that without knowing the value of. $a$ we cannot be very specific about the solution, which can vary widely depending on the value of $^{a}$ . To determine a more precise solution, we often impose one or more conditions on the value of $q$ , which are called initial conditions or boundary conditions and represent values we know. For example, if we know that at $x=0$ , the function value is 50, then we can substitute zero for. $x$ and obtain $50=(3q/5)0^{2}+a$ so $a=50$ . Or if we know that at $x=100$ $y=5{,}200$ , then we know that $5,200=(3q/5)100^{2}+a$ giving us a value for $a$ in terms of. $q$

Differential equations that contain partial derivatives are naturally called partial differential equations or PDEs. They are usually much harder to solve than are ordinary differential equations. Much of the process of solving differential equations involves classifying the equation into a given category of differential equations and then following known rules, hints, and suggestions for solutions of equations in that category. We will also sometimes exploit the fact that we have an idea of what the solution might look like. One approach to pricing options relies on solving a PDE.
