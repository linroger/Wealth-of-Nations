---
tags:
  - '#asset_payoffs'
  - '#asset_pricing'
  - '#complex_assets'
  - '#financial_modeling'
  - '#matrix_notation'
  - '#pure_assets'
  - '#risk_free_asset'
  - '#scalar_notation'
  - '#spanning_property'
  - '#state_prices'
---
# 29.2 PRICING PURE AND COMPLEX ASSETS

First, we state without proof the fact that there must always be at least as many assets as. there are states. This principle is referred to as the spanning property, which means that the pure assets must be sufficient to reproduce any complex asset. Here we shall make the number of assets equal to the number of states. Specifically let there be $_n$ states, where each state is identified as state i, $i=1,2,\ldots,n.$ and there are $_n$ complex assets, with each complex asset identified with the index j, $j=1,2,\ldots,n.$ Each complex asset has price $S_{j}$ Let $H_{i j}$ be the payoff of complex asset $j$ in state $i.$ A complex asset can be defined in terms of the number of units of each pure asset required to replicate the payoffs of the complex asset. We can alternatively define each pure asset in terms of the number of units of each complex asset required to replicate its outcomes. Define pure asset $i$ as an asset that pays 1.0 in state $i$ and zero in all other states. Then let $\alpha_{i j}$ be the number of units of asset $j$ that should be held to reproduce the payoff of pure asset i. Alternatively, we can view the payoff $H_{i j}$ as the number of units of pure asset $i$ that are implicit in complex asset $j$ . Let us now organize this information in a more meaningful way. We shall use both matrix and scalar notation, though the matrix notation is somewhat more useful in facilitating the solution of the simultaneous equations that will arise here.

As stated, a pure asset is a combination of complex assets. The payoffs of pure asset 1 in each of the possible states are as follows:

In other words, pure asset 1 is a combination of $\alpha_{11}$ units of complex asset 1, $\alpha_{12}$ units of. complex asset $2,...,$ and $\alpha_{1n}$ units of complex asset $_n$

Similarly the payoffs of pure asset 2 in each of the possible states are as follows:

Pure asset 2 is, thus, a combination of $\alpha_{21}$ units of complex asset 1, $\alpha_{22}$ units of complex asset 2, and $\alpha_{2n}$ units of complex asset $_n$

The payoffs of pure asset. $_n$ in each of the possible states are as follows:

Pure asset $_n$ is, thus, a combination of $\alpha_{n1}$ units of complex asset 1, $\alpha_{n2}$ units of complex asset 2, and $\alpha_{n n}$ units of complex asset $_n$

These conditions can be easily expressed in matrix notation as follows. The $\mathbf{H}$ matrix represents the payoffs of each asset in each state:

$$
\mathbf{H}=\left|\begin{array}{c c c c c}{H_{11}}&{H_{12}}&{\cdots}&{H_{1n}}\ {H_{21}}&{H_{22}}&{\cdots}&{H_{2n}}\ {\cdot}&{\cdot}&{\cdot\cdot}&{\cdot}\ {\cdot}&{\cdot}&{\cdot\cdot}&{\cdot}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {H_{n1}}&{H_{n2}}&{\cdots}&{H_{n n}}\end{array}\right|.
$$

The matrix of weights is

$$
\mathbf{A}={\left|\begin{array}{l l l l}{\alpha_{11}}&{\alpha_{12}}&{\cdots}&{\alpha_{1n}}\ {\alpha_{21}}&{\alpha_{22}}&{\cdots}&{\alpha_{2n}}\ {\cdot}&{\cdot}&{\cdot\cdot\cdot}&{\cdot}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {\alpha_{n1}}&{\alpha_{n2}}&{\cdot\cdot\cdot}&{\alpha_{n n}}\end{array}\right|}.
$$

As is often the case in matrix algebra, we shall need the identity matrix:

$$
{\bf I}=\left|\begin{array}{l l l l}{1}&{0}&{\cdots}&{0}\ {0}&{1}&{\cdots}&{0}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {\cdot}&{\cdot}&{\cdots}&{\cdot}\ {0}&{0}&{\cdots}&{1}\end{array}\right|.
$$

The key relationship is $\mathbf{HA}^{\prime}=\mathbf{I}.$ We can then solve for the weights using the expression2

$$
\mathbf{A}=(\mathbf{H}^{-1}\mathbf{I})^{\prime}.
$$

We can also obtain this result using scalar notation. Letting $I_{i j}$ be the $i j^{t h}$ element of matrix I, then

$$
I_{i j}=\sum_{k=1}^{n}H_{i k}\alpha_{j k}.
$$

In other words, the rows and columns of matrix I are

$$
\begin{array}{r}{I_{11}=H_{11}\alpha_{11}+H_{12}\alpha_{12}+\ldots+H_{1n}\alpha_{1n}=1}\ {I_{12}=H_{11}\alpha_{21}+H_{12}\alpha_{22}+\ldots+H_{1n}\alpha_{2n}=0}\end{array}
$$

$$
\begin{array}{r}{I_{1n}=H_{11}\alpha_{n1}+H_{12}\alpha_{n2}+\ldots+H_{1n}\alpha_{n n}=0}\ {I_{21}=H_{21}\alpha_{11}+H_{22}\alpha_{12}+\ldots+H_{2n}\alpha_{1n}=0}\ {I_{22}=H_{21}\alpha_{21}+H_{22}\alpha_{22}+\ldots+H_{2n}\alpha_{2n}=1}\end{array}
$$

$$
I_{2n}=H_{21}\alpha_{n1}+H_{22}\alpha_{n2}+\ldots+H_{2n}\alpha_{n n}=0
$$

$$
\begin{array}{l}{I_{n1}=H_{n1}\alpha_{11}+H_{n2}\alpha_{12}+\ldots+H_{n n}\alpha_{1n}=0}\ {I_{n2}=H_{n1}\alpha_{21}+H_{n2}\alpha_{22}+\ldots+H_{n n}\alpha_{2n}=0}\ {.}\ {.}\end{array}
$$

$$
I_{n n}=H_{n1}a_{n1}+H_{n2}a_{n2}+\ldots+H_{n n}a_{n n}=1.
$$

Now let us introduce a vector $\Psi$ where the element $\psi_{i}$ is the price today of pure. asset $i;$

$$
\Psi=\left|\begin{array}{c}{{\psi_{1}}}\ {{\psi_{2}}}\ {{.}}\ {{.}}\ {{.}}\ {{\psi_{n}}}\end{array}\right|.
$$

The price of a complex asset can be obtained, in matrix notation, as

$$
\begin{array}{r}{\mathbf{S}=\mathbf{H}^{\prime}\boldsymbol{\Psi}.}\end{array}
$$

or in scalar notation as

$$
{\cal S}=H^{\prime}\Psi.
$$

The equations written out are as follows:

$$
S_{n}=H_{1n}\psi_{1}+H_{2n}\psi_{2}+\ldots+H_{n n}\psi_{n}.
$$

Here we see how the complex assets are combinations of the pure assets. Alternatively, we can obtain the state prices from the prices of the complex asset. This would be found as

$$
\boldsymbol{\Psi}=(\mathbf{H}^{\prime})^{-1}\mathsf{S}.
$$

Alternatively, one could solve for the $\psi_{i}$ values in the scalar equations for $S_{j}$ shown in Equation (29.10).

In other words, a complex asset $j$ can be priced by multiplying its payoff in each state by the price of the pure asset that pays off in that given state. In this way, we see that. the payoffs of complex assets, or what we ordinarily just call assets, can be expressed in terms of the payoffs of more fundamental assets, those whose payoffs are contingent on. the given states.

The risk-free asset is extremely easy to see in this context. Its payoffs are the same in all states. Denoting the risk-free asset with 1.0 current price as asset $S_{r}$ and its payoff as $R$ , we have

$$
S_{r}=\sum_{k=1}^{n}R\psi_{k}=R\sum_{k=1}^{n}\psi_{k}.
$$

One plus the risk-free rate is, by definition, $R/S_{r}$ . Consequently, the risk-free rate, which we write as $r$ , is given as3

$$
r=\left(\frac{1}{\displaystyle\sum_{k=1}^{n}\psi_{k}}\right)-1.
$$

We see that the risk-free rate is just the inverse of the sum of the state prices minus 1.. This result should make sense. A risk-free asset is one that pays 1.0 in each state. Thus, a portfolio of one unit of each pure asset will replicate the payoff of the risk-free asset. It follows that the sums of the values of one unit of each pure asset will give the present value of 1.0, which will be the price of the risk-free asset. Inverting the price gives one plus the rate.
