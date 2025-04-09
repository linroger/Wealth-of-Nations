# 3.6 INTEGRATION

Integration is closely related to differentiation, but people usually find it to be a much. more difficult concept to grasp. There are two general ways to classify an integral. One, called the indefinite integral, is the opposite of differentiation and is sometimes called the. antiderivative. Given a derivative, indefinite integration attempts to find the function that when differentiated obtains the given derivative. For example, suppose we were given the. expression $12x$ . The indefinite integral is $6x^{2}+a$ where $a$ is an unknown constant. This specification is written as

$$
\int12x=6x^{2}+a,
$$

which is true because if $y=6x^{2}$ , then ${d y}/{d x}=12x$ . But what if $y=6x^{2}$ plus some constant $c$ Then again, ${d y}/{d x}=12x$ , so in finding the integral, we must allow for an indefinite constant, which is why it is called the indefinite integral. It is not precise.

The other interpretation of integration is as the definite integral, which is the area under a curve between two points on the $x$ -axis. For example, suppose we have a function $f(x)$ and wish to know the area under the curve between the points where $x=j$ and $x=k$ We write this as

$$
\int_{j}^{k}f(x)d x=F\left(k\right)-F(j),
$$

where the $F$ function is obtained upon integration, which we shall demonstrate next. The. definite integral is defined specifically as the limit of the sum of an infinite series of rectangles drawn under the curve as follows,

$$
\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}f{\big(}x_{i}{\big)}\Delta x_{i}=\int_{j}^{k}f(x)d x,
$$

where the curve between $x=j$ and $x=k$ has been partitioned into $_n$ rectangles.4 Note that the expression $f(x_{i})\Delta x_{i}$ is the area of a rectangle with a base of length $\Delta x_{i}$ such that $\Delta x_{i}=x_{i}-x_{i-1}$ and height of $f(x_{i})$ . The expression $f(x_{i})$ is simply the $y$ value associated with a value of $x$ of $x_{i}$ . The value $x_{1}$ is $x_{1}=j$ and the value $x_{n}$ is $x_{n}=k$ and the range of $x$ from $x_{1}=j$ to $x_{n}=k$ has been partitioned into an infinite number of subranges. This definition is called a Riemann integral (pronounced Ree-mahn).

The actual process of finding the area under the curve involves determining the integral and evaluating it at the end points. We shall do that later. First let us review the major formulas and rules for integration. For indefinite integrals, the major ones are

$$
\begin{array}{c}{{\displaystyle\int x^{\alpha}d x=\frac{1}{n+1}x^{\alpha+1}+a,}}\ {{\displaystyle\int e^{\alpha}c^{\alpha}d x=e^{x}+a~(\mathrm{Note}~;\mathrm{Because}d e^{x}/d x=e^{x}),}}\ {{\displaystyle\int\frac{1}{n}x^{\alpha}c=\mathrm{sin}x+a,}}\ {{\displaystyle\int[f(x)+g(x)]d x=\int f(x)d x+\int g(x)d x,}}\ {{\displaystyle\int d(f(x)d x=a)\int f(x)d x,}}\ {{\displaystyle\int f(b)\frac{d b}{d x}d x=\int f(b)d b,\mathrm{and}}}\ {{\displaystyle\int e^{\alpha\beta}\left({b}-b^{*}-\int b d v\cdot\mathrm{(inegation~by~parts)},\right.}}\end{array}
$$

Tables have been constructed to provide the integrals for thousands of functions, though not all functions can be integrated..

Definite integration uses these same rules to determine the integrals but without. the addition of the constant. In addition, the following rules are useful tricks in definite integration:

$$
\begin{array}{l}{{\displaystyle\int_{j}^{k}f(x)d x=-\int_{k}^{j}f(x)d x},}\ {{\displaystyle\int_{j}^{j}f(x)d x=0},}\ {{\displaystyle\int_{i}^{k}f(x)d x=\int_{i}^{j}f(x)d x+\int_{j}^{k}f(x)d x},\quad i\le j\le k,}\end{array}
$$

$$
\int_{i}^{j}-f(x)d x=-\int_{i}^{j}f(x)d x,
$$

$$
\int_{i}^{j}{\big[}f(x)+g(x){\big]}d x=\int_{i}^{j}f(x)d x+\int_{i}^{j}g(x)d x.
$$

Now let us illustrate an example of finding the area under the curve. Suppose we have the following problem:

$$
\int_{i}^{j}12x d x.
$$

The value is computed by determining the function that represents the integral of $12x$ This would be $F(\bar{x})=6x^{2}$ . Then we determine $F(b)-F(a)$ . The process is written in the following manner:

$$
\int_{i}^{j}12x d x=\left.6x^{2}\right|_{a}^{b}=6b^{2}-6a^{2}.
$$

Hence, given whatever choices we make of $j$ and i (here. $j=b$ and $i=a$ , the area under.
the curve is easily computed in this manner..
