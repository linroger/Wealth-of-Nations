---
tags:
  - gauss_jordan
  - inverse_matrices
  - linear_systems
  - matrix_algebra
  - nonsingular_matrix
aliases:
  - Linear Systems Solutions
  - Matrix Inverses
  - Solving Equations
key_concepts:
  - Gauss-Jordan method inverse
  - Inverse matrix definition
  - Linear equation solution
  - Matrix equation representation
  - Nonsingular matrix property
---

# Chapter 1 Additional Readings  

# Inverse Matrices and Solving Linear Systems of Equations:  

We know from algebra that the (multiplicative) inverse of any nonzero number exists; that is, if $a\neq0$ then $\boldsymbol{a}^{-I}=\stackrel{-}{I}/\boldsymbol{a}$ exists and has the property $\begin{array}{r}{a(\boldsymbol{a}^{-I})=(\boldsymbol{a}^{-I^{*}})\boldsymbol{a}=\boldsymbol{I}.}\end{array}$ Furthermore, the linear equation $a x{=}b$ has a unique solution for $x$ as long as $a$ is nonzero and the solution is $x=$ $a^{-l}b=b/a$ .We will study the analogous results for matrices. Suppose. $\mathbf{A}$ is a $n x n$ (square) matrix. The matrix $\mathbf{A}$ is said to be nonsingular if either its rows form a set of. $n$ linearly independent $1x n$ row vectors or its columns form a set of. $n$ linearly independent $n\times l$ column vectors. It is a theorem in linear algebra that these two conditions are equivalent. Thus, it is sufficient to check the condition for either just the rows or just the columns. A nonsingular matrix is the matrix equivalent to a nonzero number. In fact, every nonsingular matrix has an inverse that can be found by the Gauss Jordan method we covered in chapter 1 in the text. By definition, the inverse of a square $n\times n$ matrix $\mathbf{A}$ is a square $n{\times}n$ matrix $\mathbf{A}^{-1}$ such that:  

$$
\pmb{A}\pmb{A}^{-1}=\pmb{A}^{-1}\pmb{A}=\pmb{I}
$$  

where I is the $n{\times}n$ identity matrix. If the matrix A is singular, which means that either the rows or the columns form a linearly dependent set of vectors, then the inverse of A will not exist. If. one were to attempt to use the Gauss Jordan method on a singular matrix in order to find its inverse, one would run into the following problem. In the Gauss Jordan method, recall that one needs to obtain the identity on the left side of the augmented matrix and one would then be able. to read off the inverse of matrix A on the right side of the augmented matrix. If A is singular, one would find that the left side of the augmented matrix would eventually result in a row of zeros. It would then be impossible to continue the process to get the identity on the left side.  

Illustration 1: Find the inverse of $A={\left[{\begin{array}{l l}{2}&{4}\ {-6}&{-12}\end{array}}\right]}$ if it exists.  

Let's attempt to find the inverse of $\mathbf{A}$ by the Gauss-Jordan method.  

$$
\begin{array}{r l}{\left[{\begin{array}{r r r r}{2}&{4}&{:1}&{0}\ {-6}&{-12:0}&{1}\end{array}}\right]\stackrel{(r o w1)}{\rightarrow}}&{{}\sum}&{\left[{\begin{array}{r r r r}{1}&{2}&{:.5}&{0}\ {-6}&{-12:0}&{1}\end{array}}\right]\stackrel{(r o w1)}{\rightarrow}\emptyset+r o w2\left[{\begin{array}{r r}{1}&{2:.5}\ {0}&{0:3}\end{array}}\right]\stackrel{(r o w2)}{\rightarrow}\emptyset}\end{array}
$$  

Notice that the second row on the left side of the augmented matrix is a row of zeros. It is not possible to continue the Gauss-Jordan process, because there is no way to obtain a 1 in the. second row second column entry. This is due to the fact that the row vectors of the matrix A are linearly dependent since:  

$$
3[24]+[-6-12]=[00].
$$  

We conclude that the inverse of matrix A does not exist in this case.  

As we covered in chapter 1, we can often use inverse matrices to solve systems of linear equations. If we have a system of $n$ linear equations in $n$ unknown variables, we know that we can represent this system by a matrix equation of the form:  

$$
\pmb{C x}=\pmb{s},
$$  

where C is a known $n\times n$ matrix, $x$ is an unknown. $n{\times}I$ column vector, and $\pmb{S}$ is a known. $n{\times}I$ column vector. If the inverse of matrix $\mathbf{C}$ exists, then there is a unique solution for $x$ If the  

inverse of matrix C does not exist, then there is either no solution for $x$ or an infinite number of possible solutions for $x$  

Illustration 2: Solve the following system for $x_{I}$ and $x_{2}$  

$$
\begin{array}{c c c}{{2x_{1}}}&{{+4x_{2}=}}&{{5}}\ {{-6x_{1}}}&{{-12x_{2}=}}&{{-15}}\end{array}.
$$  

This system can be expressed as the matrix equation:  

$$
\begin{array}{r}{\bigl[\ensuremath{{\vphantom{\bigl[}2}\begin{array}{c c}{2}&{4}\ {-6}&{-12}\end{array}\bigr]}\bigl[\ensuremath{{\vphantom{\bigl[}x}_{2}\bigr]}=\bigl[\ensuremath{{\vphantom{\bigl[}5}\begin{array}{c}{5}\ {-15}\end{array}\bigr]}.}\end{array}
$$  

We saw in illustration 1 that the matrix C has no inverse. This means that there is no unique solution for the vector $x$ and thus no unique solution for the values of. $x_{I}$ and $x_{2}$ Observe that if one multiplies both sides of the equation $2x_{I}+4x_{2}=5$ by $^{-3}$ , one obtains the equation $-6x_{I}-I2x_{2}$ $=-{\cal I}5.$ Thus, the two equations are equivalent, and there are infinite number of solutions for $x_{I}$ and $x_{2}$ consisting of all values of $x_{I}$ and $x_{2}$ that satisfy the equation $2x_{I}+4x_{2}=5$ Graphically, these solutions consist of all points. $(x_{I},x_{2})$ that lie on the line with equation. $2x_{I}+4x_{2}=5$  

Illustration 3: Solve the following system for $x_{I}$ and $x_{2}$  

$$
\begin{array}{c c c}{{2x_{1}}}&{{+4x_{2}=}}&{{5}}\ {{-6x_{1}}}&{{-12x_{2}=}}&{{-12}}\end{array}.
$$  

This system can be expressed as the matrix equation:  

$$
\left[{2\atop c}{\frac{4}{c^{12}}}\right]\left[{\chi_{1}\atop x_{2}}\right]={\stackrel{\lceil}{\left[{5\atop-12}\right]}}.
$$  

This matrix equation has the same matrix $\mathbf{C}$ as in illustration 2, and we know C has no inverse. This means that there is no unique solution for the vector $x$ and thus no unique solution for the values of $x_{I}$ and $x_{2}$ . Again, if one multiplies both sides of the equation $2x_{I}+4x_{2}=5$ by $^{-3}$ one obtains the equation $\cdot6x_{I}-I2x_{2}=-I5$ But, it is impossible for $-6x_{I}-I2x_{2}=-I5$ and at the same time $\cdot6x_{I}-I2x_{2}=-I2.$ This would imply $-15=-12$ . Thus, this system has no solution. Illustration 4: Solve the following system for $x_{I}$ and $x_{2}$  

$$
\begin{array}{c c c}{{2x_{1}}}&{{+4x_{2}=}}&{{5}}\ {{-6x_{1}}}&{{-10x_{2}=}}&{{7}}\end{array}.
$$  

This system can be expressed as the matrix equation:  

$$
\begin{array}{c}{{\left[2\right.\qquad4\left.\right]\left[_{x_{2}}^{x_{1}}\right]=\left[5\right].}}\ {{\left.c\qquad\times\left.x\quad=\left.s\right.}}\end{array}
$$  

Using the Gauss-Jordan method, it is easy to check that the inverse of the matrix $\mathbf{C}$ is:  

# Chapter 1 Additional Readings  

$$
c^{-1}={\binom{-2.5}{1.5}}\quad.5\neqq.
$$  

Since the inverse of matrix $c$ exists, the solution for $x$ is unique and equals:  

$$
\pmb{x}=C^{-1}\pmb{s}=\left[{\begin{array}{c c}{-2.5}&{-1}\ {1.5}&{.5}\end{array}}\right]\left[{\begin{array}{c}{5}\ {7}\end{array}}\right]=\left[{\begin{array}{c}{-19.5}\ {11}\end{array}}\right],
$$  

and so $x_{I}=-I9.5$ and $x_{2}=I I$  

# II. Proving the Fundamental Theorem of Calculus:  

In Chapter 1, we stated the fundamental theorem of calculus as follows:  

$I f f(x)$ is a continuous function on the interval [a,b] then  

$$
\intop_{a}^{b}f(x)d x=F(b)-F(a).
$$  

where $F(x)$ is any particular antiderivative of $f(x)$  

To prove this theorem, we first review the definition of the definite integral on the left side of the equality above. We split the interval $[a,b]$ into $n$ subintervals of equal width $\Delta x=(b-a)/n$ For the $i\cdot$ -th subinterval $[x_{i-I},x_{i}]$ , the value $x_{i}^{*}$ can be any $x\cdot$ -value in the $i\cdot$ -th subinterval, $x_{i-1}\leq x_{i}^{*}\leq$ $x_{i}$ . Note that $\Delta x{\rightarrow}0$ is equivalent to $n{\rightarrow}\infty$  

By definition,  

$$
\int_{a}^{b}f(x)d x=\operatorname*{\it{lim}}_{n\rightarrow\infty}\sum_{i=1}^{n}f(x_{i}^{*})\Delta x.
$$  

Thus, to prove the theorem, we need to show:  

$$
l i m\sum_{n\to\infty}^{n}f(x_{i}^{*})\Delta x=F(b)-F(a)
$$  

where $F(x)$ is any particular antiderivative of $f(x)$  

This proof is of special interest as it has direct connections to our presentation of stochastic calculus later in the book. Since the function $f(x)$ is continuous, then $f(x_{i}^{*})\approx f(x_{i})$ when $\Delta x$ is small. In fact the error in this approximation is negligible. We will not prove this fact as it is beyond the level of this text. So, we can replace. $x_{i}^{\phantom{\dagger}}$ with $x_{i}$ and need to prove that:.  

# Chapter 1 Additional Readings  

$$
l i m\sum_{n\to\infty}^{n}f(x_{i})\Delta x=F(b)-F(a).
$$  

Suppose that $F(x)$ is any particular antiderivative of $f(x)$ : that is, $F^{\prime}(x){=}f(x)$ . We saw earlier that $F(x_{\mathrm{i}}+\Delta x)-F(x_{\mathrm{i}})=f(x_{\mathrm{i}})\Delta x+\epsilon(x_{i},\Delta x)\Delta x$ with $\epsilon(x_{i},\Delta x){\rightarrow}0$ as $\Delta x{\rightarrow}0$ . Since the function $f(x)$ is continuous, the error terms $\epsilon(x_{i},\Delta x)\Delta x$ are negligible. We won't prove this fact, since this is also beyond the level of this book. Thus, we can approximate $f(x_{\mathrm{i}})\Delta x$ by:  

$$
f(x_{i})\Delta x\approx F(x_{i}+\Delta x)-F(x_{i})=F(x_{i+1})-F(x_{i}).
$$  

Using this equation, we get:  

$$
\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}f(x_{i})\Delta x=\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}[F(x_{i+1})-F(x_{i})]
$$  

${\begin{array}{r l}{}&{=\operatorname*{lim}_{n\to\infty}\left\{\left[F(x_{n+1})-F(x_{n})\right]+\left[F(x_{n})-F(x_{n-1})\right]+\cdots+\left[F(x_{3})-F(x_{2})\right]+\left[F(x_{3})-F(x_{4})\right]\right\}}\ &{=\operatorname*{lim}_{n\to\infty}\left\{F(x_{n+1})-F(x_{1})\right\}=\operatorname*{lim}_{n\to\infty}\left\{F(b+\Delta x)-F(a+\Delta x)\right\}=F(b)-F(a)}\end{array}}$ (1)l} The last equality above follows from the observation that $\Delta x=(b-a)/n\rightarrow0$ as $n\to\infty$ , which means $b+\Delta x\rightarrow b$ and $a+\Delta x\to a$ as $n\to\infty$  