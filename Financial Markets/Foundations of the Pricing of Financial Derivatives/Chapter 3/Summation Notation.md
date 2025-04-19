---
tags:
  - '#double_summation'
  - '#financial_applications'
  - '#index_variable'
  - '#portfolio_management'
  - '#portfolio_value'
  - '#summation_notation'
  - '#value_additivity'
---
# 3.1 SUMMATION NOTATION

The summation symbol is often used in finance. For example, portfolios and stock indexes are additive combinations of their constituent securities. Consider the summation expression,

$$
\sum_{i=1}^{n}x_{i}=x_{1}+x_{2}+\cdot\cdot\cdot+x_{n}.
$$

The subscript is sometimes called the index. Any variable that appears on the RHS without the index can be brought to the LHS, as in the following examples:1

$$
\begin{array}{l}{\displaystyle\sum_{i=1}^{n}x_{i}y=y\sum_{i=1}^{n}x_{i},\mathrm{and},}\ {\displaystyle\sum_{i=1}^{n}x_{i}a_{j}=a_{j}\sum_{i=1}^{n}x_{i}.}\end{array}
$$

This step often simplifies the equation considerably. In finance, we sometimes encounter a double summation, as is the case when there are two assets. For example,.

$$
\sum_{i=1}^{n}\sum_{j=1}^{q}x_{i}a_{j},
$$

which is like a double loop in computer code. We start with the outer summation, letting $i=1$ . We then sum through the inner summation. Then we increment the index in the outer summation and sum through the inner summation again, continuing in that manner until both summations have been completely covered. Thus, the previous equation amounts to the following expression in expanded form,

$$
\begin{array}{c}{{x_{1}a_{1}+x_{1}a_{2}+\cdot\cdot\cdot+x_{1}a_{q}}}\ {{}}\ {{+x_{2}a_{1}+x_{2}a_{2}+\cdot\cdot\cdot+x_{2}a_{q}}}\ {{}}\ {{+\cdot\cdot\cdot}}\ {{+x_{n}a_{1}+x_{n}a_{2}+\cdot\cdot\cdot+x_{n}a_{q}.}}\end{array}
$$

Because we can move the $x_{i}$ outside the second summation, we could have written this equation as

$$
\sum_{i=1}^{n}x_{i}\sum_{j=1}^{q}a_{j}=\left(x_{1}+x_{2}+\cdot\cdot\cdot+x_{n}\right)\left(a_{1}+a_{2}+\cdot\cdot\cdot+a_{q}\right).
$$

Also note that the following operations are appropriate and often used in finance:

$$
\begin{array}{c}{{\displaystyle\sum_{i=1}^{n}\left(x_{i}+y_{i}\right)=\displaystyle\sum_{i=1}^{n}x_{i}+\sum_{i=1}^{n}y_{i}\mathrm{and}}}\ {{\displaystyle\sum_{i=1}^{n}a_{j}=n a_{j}.}}\end{array}
$$

For example, most portfolio managers will frequently need to know the values of their portfolios. The manager may own financial instruments in numerous categories, such. as domestic bonds, domestic stocks, international bonds, international stocks, financial derivatives, private equity, and so forth. Within each category, the manager may own vary-. ing amounts of numerous individual instruments. Based on the principle of value additivity,. the portfolio value of each category is found by summing the number of units held for each. instrument $(N_{t,j,i})$ times the estimated price of the instrument $(P_{t,j,i})$ , where $t$ denotes thee point in time,. $j$ denotes the category, and $i$ denotes the specific instrument. Thus, each. category's value. $(C_{t,j})$ can be represented as

$$
C_{t,j}=\sum_{i=1}^{N_{j}}N_{t,j,i}P_{t,j,i}.
$$

The overall portfolio value ( $\mathbf{}V_{t}$ , uppercase Greek $p i$ ) can be expressed as

$$
V_{t}=\sum_{j=1}^{N_{C}}C_{t,j}=\sum_{j=1}^{N_{C}}\sum_{i=1}^{N_{j}}N_{t,j,i}P_{t,j,i}.
$$
