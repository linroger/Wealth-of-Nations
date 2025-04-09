# 29.3 NUMERICAL EXAMPLE

Let there be four states and four complex assets. The payoffs of these assets are shown in the columns of the matrix $\mathbf{H}$ here, where the rows are the states and the columns are the assets:

$$
\mathbf{H}=\left|\begin{array}{c c c c}{100}&{75}&{20}&{85}\ {100}&{100}&{65}&{72}\ {100}&{125}&{90}&{135}\ {100}&{150}&{118}&{110}\end{array}\right|.
$$

It is also apparent that the first complex asset is the risk-free asset, whose payoffs are in the first column. The A matrix will, of course, be

$$
\begin{array}{r}{\mathbf{A}=\left|\begin{array}{l l l l}{\alpha_{11}}&{\alpha_{12}}&{\alpha_{13}}&{\alpha_{14}}\ {\alpha_{21}}&{\alpha_{22}}&{\alpha_{23}}&{\alpha_{24}}\ {\alpha_{31}}&{\alpha_{32}}&{\alpha_{33}}&{\alpha_{34}}\ {\alpha_{41}}&{\alpha_{42}}&{\alpha_{43}}&{\alpha_{44}}\end{array}\right|.}\end{array}
$$

We can solve for A by obtaining $\mathbf{A}=(\mathbf{H}^{-1})^{\prime}$ .4 The solution is.

$$
\mathbf{A}=\left|\begin{array}{c c c}{-0.0236}&{0.0624-0.0574-0.0020}\ {0.0564-0.0822}&{0.0653-0.0091}\ {0.0181-0.0626}&{0.0418}&{0.0242}\ {-0.0409}&{0.0825-0.0496-0.0131}\end{array}\right|.
$$

Let us assume we observe the prices of the complex assets in the market as:

$$
{\mathsf{S}}={\left|\begin{array}{l}{92.00}\ {118.00}\ {85.86}\ {99.36}\end{array}\right|}.
$$

Then we can find the prices of the pure assets as $\boldsymbol{\Psi}=(\mathbf{H}^{\prime})^{-1}\boldsymbol{\mathsf{S}}$ The solution is.

$$
\Psi=\left|\begin{array}{c}{{0.06}}\ {{0.18}}\ {{0.26}}\ {{0.42}}\end{array}\right|.
$$

In scalar notation, this would be found by solving the equations:

$$
\begin{array}{c}{92=100\psi_{1}+100\psi_{2}+100\psi_{3}+100\psi_{4}}\ {118=75\psi_{1}+100\psi_{2}+125\psi_{3}+150\psi_{4}}\ {85.86=20\psi_{1}+65\psi_{2}+90\psi_{3}+118\psi_{4}}\ {99.36=85\psi_{1}+72\psi_{2}+135\psi_{3}+110\nu_{4}.}\end{array}
$$

Alternatively, if we had the prices of the pure assets, we could obtain the prices of the complex assets as ${\pmb S}={\bf H}^{\prime}{\pmb\Psi}$ or in the previous scalar equations, inserting values for each. $\psi$ and leaving the left-hand sides as the unknowns..

The risk-free rate is then $(1/\Psi)-1$ or simply

$$
r={\frac{1}{0.06+0.18+0.26+0.42}}-1=0.086957.
$$
