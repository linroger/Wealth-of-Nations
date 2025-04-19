---
tags:
  - asset_pricing
  - constrained_optimization
  - financial_interpretations
  - lagrange_approach
  - linear_algebra
  - mathematics_economics
  - optimization
  - probability_theory
  - utility_function
  - vectors_matrices
aliases:
  - Mathematical Foundations
  - Prerequisites for Asset Pricing
key_concepts:
  - asset pricing
  - constrained optimization
  - dot product
  - formal derivations
  - identity matrix
  - lagrange approach
  - linear algebra
  - non-singular matrix
  - optimization problems
  - precise definitions
  - probability theory review
  - transpose matrix
  - utility maximization
  - vectors and matrices
---

# 1.5 Prerequisites  

We will study asset pricing with the well-established scientific approach: make precise definitions of concepts, clear statements of assumptions, and formal derivations of results. This requires extensive use of mathematics, but not very complicated mathematics. Concepts, assumptions, and results will all be accompanied by financial interpretations. Examples will be used for illustrations. The main mathematical disciplines we will apply are linear algebra, optimization, and probability. theory. Linear algebra and optimization are covered by many good textbooks on mathematics for economics as, e.g., the companion books by Sydsaeter and Hammond (2005) and Sydsaeter, Hammond, Seierstad, and Strom (2005), and of course by many more general textbooks on mathematics. Probability theory is usually treated in separate textbooks... A useful reference "manual' is Sydsaeter, Strom, and Berck (2000)..  

Probability theory  Appendix A gives a review of main concepts and definitions in probability theory. Appendix B summarizes some important results on the lognormal distribution which we shall frequently apply.  

Linear algebra, vectors, and matrices We will frequently use vectors and matrices to represent a lot of information in a compact manner. For example, we will typically use a vector to represent the prices of a number of assets and use a matrix to represent the dividends of different assets in different states of the world. Therefore some basic knowledge of how to handle vectors and matrices (so-called linear algebra) are needed..  

We will use boldface symbols like. $_{\alpha}$ to denote vectors and vectors are generally assumed to be. column vectors. Matrices will be indicate by double underlining like A. We will use the symbol $\top$ to denote the transpose of a vector or a matrix. The following is an incomplete and relatively. unstructured list of basic properties of vectors and matrices..  

Given two vectors $\pmb{x}=(x_{1},\dots,x_{n})^{\top}$ and $\pmb{y}=(y_{1},\dots,y_{n})^{\top}$ of the same dimension, the dot product of $_{x c}$ and ${\bf{y}}$ is defined as $x\cdot y=x_{1}y_{1}+\cdot\cdot\cdot+x_{n}y_{n}=\textstyle\sum_{i=1}^{n}x_{i}y_{i}$  

The identity matrix of dimension $n$ is the $n\times n$ matrix $\underline{{\underline{{I}}}}=[I_{i j}]$ with 1 along the diagonal and zeros elsewhere, i.e. $I_{i i}=1$ $i=1,\ldots,n$ , and $I_{i j}=0$ for $i,j=1,\dots,n$ with $i\neq j$  

The transpose of an $m\times n$ matrix $\underline{{\underline{{A}}}}=[A_{i j}]$ is the $n\times m$ matrix $\underline{{\underline{{A}}}}^{\top}=[A_{j i}]$ with columns and rows interchanged.  

Given an $m\times n$ matrix $\underline{{\underline{{A}}}}=[A_{i j}]$ and an $n\times p$ matrix $\underline{{\underline{{B}}}}=[B_{k l}]$ , the product $\underline{{\underline{{A}}}}\underline{{\underline{{B}}}}$ is the $m\times p$ matrix with $(i,j)$ 'th entry given by $\begin{array}{r}{(\underline{{\underline{{A}}}}\underline{{\underline{{B}}}})_{i,j}=\sum_{k=1}^{n}A_{i k}B_{k j}}\end{array}$ . In particular with $m=p=1$ , we see that for two vectors. $\pmb{x}=(x_{1},\dots,x_{n})^{\top}$ and $\pmb{y}=(y_{1},\dots,y_{n})^{\top}$ , we have $\pmb{x}^{\top}\pmb{y}=\pmb{x}\cdot\pmb{y}$ , so the matrix product generalizes the dot product for vectors.  

An $n\times n$ matrix $\underline{{\underline{{A}}}}$ is said to be non-singular if there exists a matrix $\underline{{\underline{{A}}}}^{-1}$ so that $\underline{{A A}}^{-1}=\underline{{\underline{{I}}}}$ where $\underline{{\underline{{I}}}}$ is the $n\times n$ identity matrix, and then $\underline{{\underline{{A}}}}^{-1}$ is called the inverse of $\underline{{\underline{{A}}}}$  

A $2\times2$ matrix $\left({\begin{array}{l l}{a}&{b}\ {c}&{d}\end{array}}\right)$ is non-singular if $a d-b c\neq0$ and the inverse is then given by  

$$
\left({\begin{array}{l l}{a}&{b}\ {c}&{d}\end{array}}\right)^{-1}={\frac{1}{a d-b c}}\left({\begin{array}{l l}{d}&{-b}\ {-c}&{a}\end{array}}\right).
$$  

If $\underline{{\underline{{A}}}}$ is non-singular, then $\underline{{\underline{{A}}}}^{\top}$ is non-singular and $(\underline{{\underline{{A}}}}^{\top})^{-1}=(\underline{{\underline{{A}}}}^{-1})^{\top}$ If $\underline{{\underline{{A}}}}$ and $\underline{{\underline{{B}}}}$ are non-singular matrices of appropriate dimensions,  

$$
\left(\underline{{\underline{{A}}}}\underline{{\underline{{B}}}}\right)^{-1}=\underline{{\underline{{B}}}}^{-1}\underline{{\underline{{A}}}}^{-1}.
$$  

If a and x are vectors of the same dimension, then @gT - $\begin{array}{r}{\frac{\partial\pmb{a}^{\top}\pmb{x}}{\partial\pmb{x}}=\frac{\partial\pmb{x}^{\top}\pmb{a}}{\partial\pmb{x}}=\pmb{a}}\end{array}$  

If $_{\mathbf{\nabla}}\mathbf{\phi}_{\mathbf{\phi}}$ is a vector of dimension $n$ and $\underline{{\underline{{A}}}}$ is an $n\times n$ matrix, then 0aA = (4+AT) x. In particular, if $\underline{{\underline{{A}}}}$ is symmetric, i.e. $\underline{{\underline{{A}}}}^{\top}=\underline{{\underline{{A}}}}$ , we have $\frac{\partial\pmb{x}^{\top}\underline{{\underline{{A}}}}\pmb{x}}{\partial\pmb{x}}=2\underline{{\underline{{A}}}}\pmb{x}$  

Optimization Optimization problems arise naturally in all parts of economics, also in finance. To study asset pricing theory, we will have to study how individual investors make decisions about consumption and investment. Assuming that the well-being of an individual can be represented by some sort of utility function, we will have to maximize utility subject to various constraints, e.g. a budget constraint. Therefore we have to apply results on constrained optimization. The main approach for solving constrained optimization problems is the Lagrange approach; see, e.g.,. Sydsaeter and Hammond (2005).  
