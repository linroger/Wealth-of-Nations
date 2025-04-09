# 3.2 PRODUCT NOTATION

Product notation often occurs when linking rates of return. Consider the specification,

$$
\prod_{i=1}^{n}x_{i}=x_{1}x_{2}\cdot\cdot\cdot x_{n}.
$$

The following operations are appropriate,

$$
\prod_{i=1}^{n}x_{i}y=y^{n}\prod_{i=1}^{n}x_{i}.
$$

Here we simply factored out all the ys, because they are not indexed and can move to the left of the product sign. Note, however, we can write this as $y$ raised to the power of. $_n$ inasmuch as $y$ is multiplied $_n$ times. That is, the previous expression is $x_{1}y x_{2}y\ldots x_{n}y\mathrm{~so~}y$ appears as multiplied by itself $_n$ times.

Another permissible operation is

$$
\prod_{i=1}^{n}x_{i}a_{j}=a_{j}^{n}\prod_{i=1}^{n}x_{i}.
$$

Even though. $a$ is subscripted with. $j_{:}$ its value does not change, because there is no $j$ in the product expression. Thus,. $a_{j}$ is simply a constant, just as. $y$ was a constant in Equation (3.9).

We can also do the following:

$$
\prod_{i=1}^{n}x_{i}y_{i}=\prod_{i=1}^{n}x_{i}\prod_{i=1}^{n}y_{i}.
$$

That is, if we write out the expression on the LHS, we have $x_{1}y_{1}x_{2}y_{2}\ldots x_{n}y_{n}$ . This is clearly equal to $x_{1}x_{2}\ldots x_{n}y_{1}y_{2}\ldots y_{n}.$ the expression on the RHS.

Another simplifying operation is

$$
\prod_{i=1}^{n}a_{j}=a_{j}^{n}.
$$

Here the value of $a_{j}$ does not change, so the same term is simply being multiplied by itself $_n$ times.

The rate of return is an important metric in finance and can be measured in many different ways. For this illustration, we assume monthly discrete compounded rates of return based on the portfolio's estimated value at the start $(V_{t-1})$ and end $(V_{t})$ of the month. Thus, the monthly discrete compounded rate of return $(R_{t}^{d})$ is defined as

$$
R_{t}^{d}=\frac{V_{t}-V_{t-1}}{V_{t-1}}=\frac{V_{t}}{V_{t-1}}-1.
$$

Note that we assume the initial value is positive. Many financial derivatives have initial values of zero presenting some challenges addressed later. The monthly total return $(T R_{t})$ is based on rearranging the monthly rate of return expression or

$$
T R_{t}=\frac{V_{t}}{V_{t-1}}=1+R_{t}^{d}.
$$

For example, consider a portfolio's return performance over the past five years mea-. sured monthly. Hence, we have 60 observations of the rate of return and the five-year total return is

$$
T R_{T}=\frac{V_{T}}{V_{0}},
$$

where the subscript in this case is 60. Based on the definition of monthly total return, we observe the following relationship based on the product notation,.

$$
T R_{T}=\frac{V_{T}}{V_{0}}=\prod_{t=1}^{60}T R_{t}=\prod_{t=1}^{60}\left(1+R_{t}^{d}\right).
$$

Using the properties of products above, one could easily manipulate total returns based on calendar months (January, February, and so forth) or further decompose monthly total returns into daily returns.
