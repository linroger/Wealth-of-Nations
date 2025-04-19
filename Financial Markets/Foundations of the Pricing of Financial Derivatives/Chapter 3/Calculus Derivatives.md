---
tags:
  - '#black_scholes_merton'
  - '#bond_valuation'
  - '#calculus_derivatives'
  - '#chain_rule'
  - '#first_derivative'
  - '#partial_derivatives'
  - '#risk_management'
  - '#taylor_series_expansion'
  - '#total_differential'
---
# 3.5 CALCULUS DERIVATIVES

The derivative of a function describes the rate at which the function changes.2 The derivative is a function that is obtained (hence derived) from the original function. Given a function, $y=f(x)$ , the first derivative is denoted as $d y/d x$ Or $f^{\prime}(x)$ and is formally defined as

$$
{\frac{d y}{d x}}=\operatorname*{lim}_{\Delta x\to0}{\frac{\Delta y}{\Delta x}}=\operatorname*{lim}_{\Delta x\to0}{\frac{f(x+\Delta x)-f(x)}{\Delta x}}.
$$

An alternative notation for the first derivative is. $y_{x}$ , but we do not use this notation much in finance because we tend to use subscripts for other purposes, such as an indication of a point in time. Thus, an expression such as. $y_{t}$ , which in math might mean. $d y/d t$ , in finance often means the value of. $y$ at time $t$

In words, the first derivative is the limit of the slope of the line tangent to a function. at a specific point. It is the rate of change of the function at that point. The terms $\Delta y$ and $\Delta x$ are called differentials and the ratio of differentials when. $\Delta x\to0$ is the derivative.3. For some functions, however, the derivative does not exist at a certain point, such as a derivative that contains division by $x$ when $x=0$

The first derivative is a function itself. There are various rules for determining the derivative of a function. The most commonly used ones are summarized in the following subsections.

# 3.5.1 Derivatives of Common Algebraic Functions

We highlight several algebraic functions that are useful in various finance applications:

$$
\begin{array}{l}{{\displaystyle y=c(c a c o n s t a n t),}}\ {{\displaystyle\underline{{{d y}}}=0(x\mathrm{isnoteveninthefunction}),}}\end{array}
$$

$$
{\begin{array}{r l}&{y=c b{\mathrm{~where~}}b=f(x),}\ &{{\frac{d y}{d x}}=c{\frac{d b}{d x}},}\end{array}}
$$

$$
{\frac{d y}{d x}}={\frac{d b}{d x}}+{\frac{d\nu}{d x}},
$$

$$
\frac{d y}{d x}=b\frac{d\nu}{d x}+\nu\frac{d b}{d x}\mathrm{(the~product~rule)},
$$

$$
\begin{array}{l}{\displaystyle\frac{d y}{d x}=\frac{\nu\frac{d b}{d x}-b\frac{d\nu}{d x}}{\nu^{2}}\mathrm{(the~quotient~rule)},}\ {\displaystyle y=a^{x},}\ {\displaystyle\frac{d y}{d x}=a^{x}\ln a,\mathrm{and}}\end{array}
$$

$y=b^{n}$ where $b=f(x)$ and $_n$ is independent of $x$

$$
{\frac{d y}{d x}}=n b^{n-1}{\frac{d b}{d x}}.
$$

Note in the last example the simple case of $y=b^{n}$ where $b=x$ gives

$$
d y/d x=n b^{n-1}(d x/d x)=n x^{n-1}.
$$

To illustrate several of these results, recall the value of a simple bond can be expressed as

$$
V_{B}=\frac{C}{y}\left[1-\frac{1}{(1+y)^{N}}\right]+\frac{P a r}{(1+y)^{N}},
$$

where C denotes the coupon amount,. $y$ denotes the periodic yield to maturity,. $N$ denotes the number of remaining payments, and Par denotes the bond's par value. The first derivative of the bond value with respect to yield to maturity is.

$$
\frac{d V_{B}}{d y}=\frac{d}{d y}\left\{\frac{C}{y}\left[1-\frac{1}{(1+y)^{N}}\right]+\frac{P a r}{(1+y)^{N}}\right\}.
$$

Based on the following definitions,

$$
\begin{array}{l}{{f(y)=\displaystyle\frac{C}{y}=C y^{-1},}}\ {{\mathrm{}}}\ {{g(y)=1-\displaystyle\frac{1}{(1+y)^{N}}=1-(1+y)^{-N},\mathrm{and}}}\ {{\mathrm{}}}\ {{b(y)=\displaystyle\frac{P a r}{(1+y)^{N}}=P a r(1+y)^{-N}.}}\end{array}
$$

Thus, based on the product rule [Equation (3.41)] and Equation (3.45), we have

$$
\frac{d V_{B}}{d y}=\frac{d}{d y}[f(y)g(y)+b(y)]=f\frac{d g}{d y}+g\frac{d f}{d y}+\frac{d b}{d y}.
$$

Based on Equations (3.39) and (3.45), we have

$$
\frac{d f}{d y}=-C y^{-2}=-\frac{C}{y^{2}}.
$$

Based on Equations (3.35) and (3.45), we have

$$
\frac{d g}{d y}=N(1+y)^{-(N+1)}.
$$

Based on Equations (3.44) and (3.45), we have

$$
\frac{d b}{d y}=-N P a r(1+y)^{-(N+1)}.
$$

Substituting we have

$$
\begin{array}{c}{{\displaystyle\frac{d V_{B}}{d y}=f\frac{d g}{d y}+g\frac{d f}{d y}+\frac{d b}{d y}=\frac{C}{y}N(1+y)^{-(N+1)}+\left[1-\frac{1}{(1+y)^{N}}\right]\left(-\frac{C}{y^{2}}\right)}}\ {{+\left[-N P a r(1+y)^{-(N+1)}\right].}}\end{array}
$$

Rearranging we have the following well-known result,

$$
\frac{d V_{B}}{d y}=\frac{C}{y}\left\{\frac{N}{(1+y)^{N+1}}-\frac{1}{y}\left[1-\frac{1}{(1+y)^{N}}\right]\right\}-\frac{N P a r}{(1+y)^{N+1}}.
$$

Sensitivities such as these have proven very useful in various risk management tasks, particularly related to managing bond portfolios. We leave one specific application related to bond duration and convexity to an end-of-chapter problem.

# 3.5.2 Derivatives of Logarithmic Functions

We review selected logarithmic functions that are useful in various finance applications:

$$
\frac{d y}{d x}=\frac{\log_{a}e}{b}\frac{d b}{d x},
$$

$$
y=\ln b,
$$

$$
{\frac{d y}{d x}}={\frac{1}{b}}{\frac{d b}{d x}},{\mathrm{and}}
$$

$$
y=\ln x,
$$

$$
{\frac{d y}{d x}}={\frac{1}{x}}.
$$

Several of these results are particularly useful when deriving various risk measures related to option valuation models.

# 3.5.3 Derivatives of Exponential Functions

We review selected exponential functions that are useful in various finance applications:

$$
{\frac{d y}{d x}}=a^{b}\ln a{\frac{d b}{d x}},
$$

$$
{\frac{d y}{d x}}=e^{b}{\frac{d b}{d x}},{\mathrm{and}}
$$

$$
{\frac{d y}{d x}}=\nu b^{\nu-1}{\frac{d b}{d x}}+b^{\nu}\ln b{\frac{d\nu}{d x}}.
$$

Again, several of these results are particularly useful when deriving various risk measures related to option valuation models. We illustrate here an application related to coupon-bearing bonds. Based on continuously compounded discount rates, the value of a bond can be expressed as

$$
V_{B}=C\sum_{i=1}^{N}e^{-y(i)}+P a r\left(e^{-y(N)}\right).
$$

Thus, the first derivative of bond value with respect to the continuously compounded yield to maturity is

$$
\frac{d V_{B}}{d y}=C\sum_{i=1}^{N}\left(-i\right)e^{-y(i)}+\left(-N\right)P a r\left(e^{-y(N)}\right)=-C\sum_{i=1}^{N}i e^{-y(i)}-\left(N\right)P a r\left(e^{-y(N)}\right).
$$

Clearly, as the yield increases, the bond value decreases.

# 3.5.4 Derivatives of Trigonometric Functions

Although trigonometric functions rarely make their way into finance applications, it does happen occasionally, particularly when estimating functions, such as the yield curve, or when deploying econometric models. We show here selected derivatives of trigonometric. functions:

$$
\begin{array}{c}{{\displaystyle y=\sin b\mathrm{where}b=f(x),}}\ {{\displaystyle\frac{d y}{d x}=\cos b\frac{d b}{d x},}}\end{array}
$$

$$
{\frac{d y}{d x}}=-\sin b{\frac{d b}{d x}},{\mathrm{~and~}}
$$

$$
{\frac{d y}{d x}}=\sec^{2}b{\frac{d b}{d x}}.
$$

One application is modeling calendar seasonality with trigonometric functions.

# 3.5.5 Derivatives of Inverse Functions

The derivative of an inverse functions can be expressed as

$y=f(x)$ and $x=g\left(y\right)$ are inverse functions,

$$
{\frac{d y}{d x}}={\frac{1}{\frac{d x}{d y}}}.
$$

For example, based on periodic compounding, the future value $(F V)$ of some present value $(P V)$ can be expressed as a function of the annualized yield to maturity $(y)$ or

$$
F V=P V\bigg(1+\frac{y}{m}\bigg)^{N},
$$

where $^m$ denotes the number of compounding periods per year, and $N$ denotes time to maturity expressed in compounding periods. Alternatively, we can express the annualized yield to maturity as a function of the future value in the following form,

$$
y=m\left[e^{\frac{\ln\left(\frac{F V}{P V}\right)}{N}}-1\right].
$$

Thus, $y=f(F V)$ and $F V=g(y)$ . Thus, based on the previous inverse equation, we note

$$
\frac{d y}{d F V}=\frac{1}{\frac{d F V}{d y}},
$$

and

$$
\frac{d F V}{d y}=\frac{d}{d y}\left[P V\Big(1+\frac{y}{m}\Big)^{N}\right]=\frac{(N)P V}{m}\Big(1+\frac{y}{m}\Big)^{N-1}.
$$

Therefore,

$$
\frac{d y}{d F V}=\frac{1}{\frac{d F V}{d y}}=\frac{1}{\frac{(N)P V}{m}\Big(1+\frac{y}{m}\Big)^{N-1}}.
$$

At times, the derivative of an inverse is easier to obtain than the derivative directly. For example, the direct approach is a bit more tedious as shown here:.

$$
{\begin{array}{r l}{{\frac{d y}{d x}}={\frac{d}{d F V}}\left\{m\left[e^{\frac{\ln\left({\frac{F V}{P V}}\right)}{N}}-1\right]\right\}=m{\frac{d}{d F V}}\left[e^{\frac{\ln\left({\frac{F V}{P V}}\right)}{N}}\right]}&{}\ {={\frac{m}{(N)F V}}e^{\frac{\ln\left({\frac{F V}{P V}}\right)}{N}}={\frac{m}{(N)F V}}e^{\frac{N\ln\left(1+{\frac{y}{m}}\right)}{N}}}&{}\ {={\frac{m}{(N)P V\left(1+{\frac{y}{m}}\right)^{N}}}\left(1+{\frac{y}{m}}\right)={\frac{m}{(N)P V\left(1+{\frac{y}{m}}\right)^{N-1}}}.}\end{array}}
$$

# 3.5.6 The Chain Rule

If we have a function $y=f(x)$ and $x$ is also a function such as $x=f(g)$ , then we take the derivative $d y/d g$ in the following manner:

$$
{\frac{d y}{d g}}=\left({\frac{d y}{d x}}\right)\left({\frac{d x}{d g}}\right),
$$

or in other words, as the product of two derivatives. This is called the chain rule.

For example, manipulating the Black-Scholes-Merton option pricing model often. requires use of the chain rule. For example, the cumulative standard normal distribution can be expressed as

$$
y=N\left(d_{1}\right)=\int_{-\infty}^{d_{1}}{\frac{e^{-{\frac{x^{2}}{2}}}}{\sqrt{2\pi}}}d x.
$$

The value of $d_{1}$ is

$$
x=d_{1}\equiv\frac{\ln\left(\frac{S}{X}\right)+\left(r_{c}+\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}},
$$

where $S$ denotes the current stock price, $X$ denotes the strike price, $r_{c}$ denotes the annualized, continuously compounded, risk-free interest rate, $\sigma$ denotes the volatility, and $\tau$ denotes the time to expiration. Therefore, the first derivative of $N\left(d_{1}\right)$ , the normal probability based on $d_{1}$ , with respect to the stock price can be worked out based on the chain rule or

$$
\frac{d N\left(d_{1}\right)}{d S}=\left(\frac{d N\left(d_{1}\right)}{d d_{1}}\right)\left(\frac{d d_{1}}{d S}\right)=\frac{e^{-\frac{d_{1}^{2}}{2}}}{S_{t}\sigma\sqrt{2\pi\tau}}.
$$

# 3.5.7 Higher-Order Derivatives

These are examples of the first derivative, the rate of change of the function at the indicated point. There is also a second derivative, which is the rate of change of the first deriva-. tive. For example, consider $y=f(x)$ and its first derivative, $d y/d x$ . Its second derivative is written as follows:

$$
{\frac{d\left({\frac{d y}{d x}}\right)}{d x}}={\frac{d^{2}y}{d x^{2}}},
$$

and sometimes as $f^{\prime\prime}(x)$ . The second derivative provides further information, beyond that. of the first derivative, about the characteristics of the function. For example, a positive first derivative and positive second derivative describes a function that is upward sloping with the slope increasing at an increasing rate. A positive first derivative and negative. second derivative describes a function that is increasing at a decreasing rate. A negative first. derivative and positive second derivative is a function that is decreasing at a decreasing rate.. A negative first derivative and negative second derivative is a function that is decreasing at an increasing rate. A zero first derivative and positive second derivative is a function that is at a minimum, whereas a zero first derivative and negative second derivative is a. function that is at a maximum. There are also third- and higher-order derivatives, but we rarely need them in finance..

Again, manipulating the Black-Scholes-Merton option pricing model often requires. use of the higher-order derivatives. For example, the second derivative of the call option price with respect to the underlying instrument is known as gamma and, though rarely. used, the third derivative of the call option price with respect to the underlying instrument. is known as speed.

# 3.5.8Partial Derivatives

A function containing more than one variable that can be differentiated with respect to one of the variables by treating the other variables as constants is a derivative called a partial derivative. Consider $y=f(x,z)$ where both $x$ and $z$ are variables. Then the partial derivatives are written as $\partial y/\partial x$ and $\partial y/\partial z$ and they represent the change in $y$ for a change in either $x$ or $z$ , while treating the other variable as a constant.

The rules for taking partial derivatives are the same as the rules for taking ordinary derivatives. For example, consider the function $y=2x^{3}+4z^{2}+c$ where $c$ is a constant. Then

$$
\begin{array}{l}{\displaystyle\frac{\partial y}{\partial x}=6x^{2}}\ {\displaystyle\frac{\partial y}{\partial z}=8z.}\end{array}
$$

Likewise, there are second partial derivatives. Hence,

$$
{\begin{array}{r l}&{{\frac{\partial\left({\frac{\partial y}{\partial x}}\right)}{\partial x}}={\frac{\partial^{2}y}{\partial x^{2}}}=12x}\ &{{\frac{\partial\left({\frac{\partial y}{\partial z}}\right)}{\partial z}}={\frac{\partial^{2}y}{\partial z^{2}}}=8.}\end{array}}
$$

It is common in mathematical notation that given a function $y(x,z)$ , we use an expression such as $y_{1}$ to be the partial derivative of $y$ with respect to the first variable indicated in the expression, that is,. $\partial y/\partial x$ , and $y_{2}$ to be the partial derivative with respect to the second variable, that is,. $\partial y/\partial z$ . Likewise $y_{11}$ is $\partial^{2}y/\partial x^{2}$ and $y_{22}$ is $\partial^{2}y/\partial z^{2}$ . We do not use this. notation much in finance, however, owing to the use of subscripts as other indications such as a point in time or the identity of a variable.

Consider the following function: $y=4x^{3}z^{2}$ . The partial derivatives are $\partial y/\partial x=$ $12x^{2}z^{2}$ and $\partial y/\partial z=8x^{3}z$ You can also take the partial derivative of each of these derivatives with respect to the other variable. In other words,

$$
{\begin{array}{r l}&{{\frac{\partial\left({\frac{\partial y}{\partial x}}\right)}{\partial z}}={\frac{\partial^{2}y}{\partial x\partial z}}=24x^{2}z}\ &{{\frac{\partial\left({\frac{\partial y}{\partial z}}\right)}{\partial x}}={\frac{\partial^{2}y}{\partial z\partial x}}=24x^{2}z.}\end{array}}
$$

Note that they are the same. It does not matter which order you do the differentiation.

In mathematical notation these derivatives, sometimes called cross-partial derivatives, often are indicated with such symbols as $y_{12}$ and $y_{21}$ , but as noted as shown previously we do not use this notation much in finance.

# 3.5.9 Taylor's Theorem

Taylor's theorem appears a surprising number of times in finance. Consider a function, $f(x)$ , observed at two points,. $x$ and $x+\Delta x$ . In other words, the function is. $f(x)$ at point $x$ and $f(x+\Delta x)$ at point $x+\Delta x$ . Taylor's theorem states that we can take the value of the function at $f(x)$ and add a series of terms to obtain its value at. $f(x+\Delta x)$ in the following manner:

$$
\begin{array}{c}{{f(x+\Delta x)=f(x)+\displaystyle{\frac{f^{\prime}(x)}{1!}}\Delta x+\displaystyle{\frac{f^{\prime\prime}(x)}{2!}}\Delta x^{2}+\displaystyle{\frac{f^{\prime\prime\prime}(x)}{3!}}\Delta x^{3}+\cdot\cdot\cdot}}\ {{f(x+\Delta x)-f(x)=\displaystyle{\frac{f^{\prime}(x)}{1}}\Delta x+\displaystyle{\frac{f^{\prime\prime}(x)}{2}}\Delta x^{2}+\displaystyle{\frac{f^{\prime\prime\prime}(x)}{6}}\Delta x^{3}+\cdot\cdot\cdot}}\ {{\Delta f(x)=f^{\prime}(x)\Delta x+\displaystyle{\frac{f^{\prime\prime}(x)}{2}}\Delta x^{2}+\displaystyle{\frac{f^{\prime\prime\prime}(x)}{6}}\Delta x^{3}+\cdot\cdot\cdot.}}\end{array}
$$

This operation is also called a Taylor series expansion, which is useful when we need to study the properties of the rate of change of a function, rather than its specific value at a point. Although derivatives do the same thing, they represent the change in a function when there is an infinitesimal change in a variable. Taylor series expansions are useful when the variable change is not infinitesimal, as is often the case in finance.

If the function has more than one variable, we can apply Taylor's Theorem to a given. variable at a time, holding the other variables constant. The derivatives expressed are then. partial derivatives. Alternatively, we could do a Taylor series expansion for more than one variable. For example, let. $y=f(x,z)$ . Then a Taylor series expansion for both $x$ and $z$ would be written as.

$$
\begin{array}{l}{\displaystyle\Delta y=\frac{\partial y}{\partial x}\Delta x+\frac{\partial y}{\partial z}\Delta z}\ {\displaystyle\qquad+\frac{1}{2}\frac{\partial^{2}y}{\partial x^{2}}\Delta x^{2}+\frac{1}{2}\frac{\partial^{2}y}{\partial z^{2}}\Delta z^{2}+\frac{\partial^{2}y}{\partial x\partial z}\Delta x\Delta z}\ {\displaystyle\qquad+\cdot\cdot,}\end{array}
$$

where the additional terms would represent higher-order partial derivatives and all possible cross-partial combinations.

A Taylor series expansion is exact only in the limit, that is, where the number of terms. on the RHS is infinite. In applications we often do a Taylor series expansion to the second order, that is, where terms after the second derivative are dropped, and then change the. equals sign to the approximation sign, which is. $\approx$

The Taylor series approximation is a widely used tool in financial analysis. For. example, various risk measures related to bonds, such as duration and convexity, are derived based on this approximation.

# 3.5.10 Total Differential

Consider a function $y=f(x,z)$ . Suppose both $x$ and $z$ change. If we want to know by how much the function changes, we can obtain the answer using a function called the total differential, which is

$$
d y={\frac{\partial y}{\partial x}}d x+{\frac{\partial y}{\partial z}}d z.
$$

This expression essentially says that the change in $y$ is the change in $x$ multiplied by the rate at which $y$ changes if $x$ changes plus the change in $z$ multiplied by the rate at which. $y$ changes if $z$ changes. It is exact only if the changes in. $x$ and $z$ are very small.

Note that the total differential looks somewhat like a first-order Taylor series expansion. A first-order Taylor series expansion, however, is just an approximation. The total differential is an exact expression. The distinction lies in the fact that the Taylor series expansion applies to discrete changes in $x$ and $z$ $\Delta x$ and $\Delta z$ ) and uses partial derivatives to approximate the discrete change in $y(\Delta y)$ . If we let $\Delta x$ and $\Delta z$ be infinitesimal changes, we denote them as $d x$ and $d z$ Then we restate the Taylor series expansion for the two variables that we presented previously as

$$
{\begin{array}{l}{\displaystyle d y={\frac{\partial y}{\partial x}}d x+{\frac{\partial y}{\partial z}}d z}\ {\displaystyle~+{\frac{1}{2}}{\frac{\partial^{2}y}{\partial x^{2}}}d x^{2}+{\frac{1}{2}}{\frac{\partial^{2}y}{\partial z^{2}}}d z^{2}+{\frac{\partial^{2}y}{\partial x\partial z}}d x d z}\ {\displaystyle~+\cdot\cdot}\ {={\frac{\partial y}{\partial x}}d x+{\frac{\partial y}{\partial z}}d z,}\end{array}}
$$

which is the total differential and which holds by virtue of the fact that any product such as. $d x d x=d x^{2}$ or $d x d z$ is zero because $d x$ is a differential and is defined as an infinitesimally small value, which when squared moves it closer to zero. In general,. $d x^{k}\rightarrow0$ if $k>1$ Interestingly, this result is used a great deal in option pricing as we shall see in later chapters.

# 3.5.11 Total Derivative

As previously noted, a derivative is a ratio of differentials. Working with the total differential, we can divide by one of the variables and obtain the total derivative with respect to that variable. In other words,.

$$
\begin{array}{r}{\displaystyle{\frac{d y}{d x}}={\frac{\partial y}{\partial x}}+{\frac{\partial y}{\partial z}}{\frac{d z}{d x}}}\ {\displaystyle{\frac{d y}{d z}}={\frac{\partial y}{\partial x}}{\frac{d x}{d z}}+{\frac{\partial y}{\partial z}}.}\end{array}
$$
