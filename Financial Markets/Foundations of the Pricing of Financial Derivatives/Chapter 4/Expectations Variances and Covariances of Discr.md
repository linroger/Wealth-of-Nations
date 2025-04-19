---
tags:
  - covariance
  - discrete_random_variable
  - dispersion
  - expectation
  - expected_value
  - probability_distribution
  - rates_of_return
  - variance
aliases:
  - Discrete Random Variables
  - Expectations, Variances, Covariances
key_concepts:
  - Discrete random variable
  - Expected value
  - Probability-weighted average
  - Random variable
  - Variance of distribution
---

# 4.2 EXPECTATIONS, VARIANCES, AND COVARIANCES OF DISCRETE RANDOM VARIABLES

A random variable is a variable that can take on many possible values representing uncer-.
tain outcomes whose frequencies of occurrence are governed by a probability distribution..
A discrete random variable can take on only a finite number of values. For example, the number of people who respond yes to a survey or the number of laboratory mice who died following an experiment are examples of a discrete random variable. By contrast, a con-.
tinuous random variable can take on an infinite number of values. For example, the height.
of a person selected randomly or the amount of time following an event can always be.
expressed with decimal places. For however many decimal places chosen, one can always.
add one more. Let us look at the expectations, variances, and covariances of both of these.
types of variables. We address discrete random variables first.

For a discrete random variable there are a finite number of outcomes that we often. call states or states of the world. For example, if the event is the selection of a person and we are interested in whether that person is male or female, we would have two states. Let $\boldsymbol{x}=\boldsymbol{x}_{m}$ if that person is male and $x=x_{f}$ if that person is female. In general, we specify $_n$ states and $_n$ possible values of $x\colon x_{1},x_{2},\ldots,x_{n}$ We often need to characterize the properties. of this random variable $x$ . We let $p_{i}$ be the probability that state or outcome $i$ occurs. Note that by definition $\sum_{i=1}^{n}{p_{i}}=1$ It may well be the case that $p_{i}$ is given by some mathematical function that might more appropriately be written as $f(x)$ , but here we shall just leave the. probability specification in the form $p_{i}$

# 4.2.1 The Expectation of a Discrete Random Variable

The expected value, sometimes called the mean, is the probability-weighted average value of $x$ .9 The expected value for a discrete distribution is the following specification:

$$
E(x)=\sum_{i=1}^{n}x_{i}p_{i}.
$$

Occasionally we shall have to work with a constant such as $a$ in the following operations:

$$
E(a)=\sum_{i=1}^{n}a p_{i}=a\sum_{i=1}^{n}p_{i}=a.
$$

The expected value of a constant is simply the constant. Next, we multiply the constant times the random variable and are able to pull the constant out of the expectation sign,.

$$
E(a x)=a\sum_{i=1}^{n}x_{i}p_{i}=a E(x).
$$

The Greek letter $\mu$ is often used for the expected value, but other Greek letters and many.
other symbols are also sometimes used as the expected value.

For example, Table 4.1 provides an analyst's forecast of potential rates of return from holding a particular tech company stock over the next year.

TABLE 4.1 Potential Rates of Return


<html><body><table><tr><td>Probability (%)</td><td>Rate of Return (%)</td></tr><tr><td>10</td><td>-25</td></tr><tr><td>20</td><td>-5</td></tr><tr><td>40</td><td>10</td></tr><tr><td>20</td><td>20</td></tr><tr><td>10</td><td>55</td></tr></table></body></html>

Based on Equation (4.1), we have

$$
E(R)=\sum_{i=1}^{n}R_{i}\dot{p}_{i}=-25(0.1)-5(0.2)+10(0.4)+20(0.2)+55(0.1)=10,
$$

or an expected rate of return of $10\%$

# 4.2.2 The Variance of a Discrete Random Variable

The variance is a measure of the dispersion of the distribution. It is defined as the probability-weighted squared deviation of each possible value from the expected value. Using that construction, we see that the variance can be converted to another useful specification:

$$
{\begin{array}{r l}&{\operatorname{var}(x)=\displaystyle\sum_{i=1}^{n}\left[x_{i}-E(x)\right]^{2}p_{i}=\displaystyle\sum_{i=1}^{n}\left[x_{i}-E(x)\right]\left[x_{i}-E(x)\right]p_{i}}\ &{\qquad=\displaystyle\sum_{i=1}^{n}\left\{x_{i}^{2}-2E(x)x_{i}+[E(x)]^{2}\right\}p_{i}=\displaystyle\sum_{i=1}^{n}x_{i}^{2}p_{i}-2E(x)\displaystyle\sum_{i=1}^{n}x_{i}p_{i}+[E(x)]^{2}\sum_{i=1}^{n}p_{i}}\ &{\qquad=E{\bigl(}x^{2}{\bigr)}-2[E(x)]^{2}+[E(x)]^{2}=E{\bigl(}x^{2}{\bigr)}-[E(x)]^{2}.}\end{array}}
$$

In other words, the variance is also the expected value of the squared value of $x$ minus the square of the expected value of $x$

When we work with constants, the variance is affected in the following manner:

$$
\begin{array}{l}{\displaystyle\operatorname{var}(a x)=\sum_{i=1}^{n}\left[a x_{i}-E(a x)\right]^{2}p_{i}=E\left[(a x)^{2}\right]-\left[E(a x)\right]^{2}=E\left(a^{2}x^{2}\right)-a^{2}[E(x)]^{2}}\ {\displaystyle\qquad=a^{2}E\big(x^{2}\big)-a^{2}[E(x)]^{2}=a^{2}\left\{E\big(x^{2}\big)-[E(x)]^{2}\right\}=a^{2}V a r(x).}\end{array}
$$

In other words, the variance of a constant times a random variable is the constant squared times the variance of the random variable. The variance of a constant is zero as shown by the following:

$$
\operatorname{var}(a)=\sum_{i=1}^{n}\left[a-E(a)\right]^{2}{p_{i}}=\sum_{i=1}^{n}\left(a-a\right)^{2}{p_{i}}=0.
$$

Finally, we also show that the variance of a constant plus a random variable is the variance of the random variable. In other words, adding a constant does nothing to change the variance of the random variable..

$$
{\begin{array}{r l}&{\operatorname{var}(a+x)=\displaystyle\sum_{i=1}^{n}\left[a+x_{i}-E(a+x)\right]^{2}p_{i}}\ &{\qquad=\displaystyle\sum_{i=1}^{n}\left[a-E(a)+x_{i}-E(x)\right]^{2}p_{i}=\displaystyle\sum_{i=1}^{n}\left[a-a+x_{i}-E(x)\right]^{2}p_{i}}\ &{\qquad=\displaystyle\sum_{i=1}^{n}\left[x_{i}-E(x)\right]^{2}p_{i}}\ &{\qquad=V a r(x).}\end{array}}
$$

The square root of the variance is the standard deviation. Using $\sigma$ as its symbol, we have $\sigma(a x)=a(\sigma(x))$

Based on the same data in the last example, Table 4.2 provides supplemental information to assist in the calculation of the standard deviation. Based on Equation (4.4), we have

$$
\mathrm{var}(R)=E\big(R^{2}\big)-[E(R)]^{2}=490-10^{2}=390,
$$

or a standard deviation of $19.748\%\left(=\sqrt{390}\right)$

# 4.2.3 The Covariance of Discrete Random Variables

An important concept somewhat similar to the variance is the covariance. It measures the extent to which two random variables move together. Now we need another random variable, which we shall refer to as $y$ . The covariance between $x$ and $y$ is given as

$$
\begin{array}{l}{{\mathrm{cov}(x,y)=\displaystyle\sum_{i=1}^{n}\left[x_{i}-E(x)\right]\left[y_{i}-E(y)\right]{\psi}_{i}=\displaystyle\sum_{i=1}^{n}\left[x_{i}y_{i}-E(x)y_{i}-x_{i}E(y)+E(x)E(y)\right]{\psi}_{i}}}\ {{~=\displaystyle\sum_{i=1}^{n}x_{i}y_{i}{\rlap/b_{i}}-E(x)\displaystyle\sum_{i=1}^{n}y_{i}{\rlap/b_{i}}-E(y)\displaystyle\sum_{i=1}^{n}x_{i}{\rlap/b_{i}}+E(x)E(y)\displaystyle\sum_{i=1}^{n}{\rlap/b_{i}}}}\ {{~=E(x y)-E(x)E(y)-E(y)E(x)+E(x)E(y)}}\ {{~=E(x y)-E(x)E(y).}}\end{array}~(4)
$$

TABLE 4.2 Illustration of Supplemental Information to Compute Standard Deviation


<html><body><table><tr><td>Probability(%)</td><td>Rate of Return (%)</td><td>RateofReturn</td></tr><tr><td>10</td><td>-25</td><td>625</td></tr><tr><td>20</td><td>-5</td><td>25</td></tr><tr><td>40</td><td>10</td><td>100</td></tr><tr><td>20</td><td>20</td><td>400</td></tr><tr><td>10</td><td>55</td><td>3,025</td></tr><tr><td>Sum=100%</td><td>E(R)=10%</td><td>E(R²) = 490</td></tr></table></body></html>

The numerical value of the covariance by itself is difficult to interpret. For example, we do. not know what constitutes a large covariance, and what is a small covariance. We do know that a positive (negative) covariance means that the two variables tend to move together (opposite) in a linear fashion. A zero covariance implies that there is no linear relationship. between the two variables, but it does not rule out a nonlinear relationship.10 A more. useful measure of association is the correlation, defined as.

$$
\rho(x,y)=\frac{\mathsf{c o v}(x,y)}{\sigma(x)\sigma(y)},
$$

where $\sigma(x)$ and $\sigma(y)$ are the standard deviations of $x$ and $y$ , respectively. The correlation.
ranges between $-1$ and $+1$ . With bounds at. $-1$ and $+1$ , it is a good bit easier to interpret.
the magnitude of a correlation.

Based on the data in the last example along with a second instrument, Table 4.3 provides supplemental information to assist in the calculation of covariance. Based on Equation (4.8), we have the covariance as

$$
\operatorname{cov}(R_{1},R_{2})=E(R_{1}R_{2})-E(R_{1})E(R_{2})=535-10(10)=435.
$$

Note that interpreting 435 is difficult. Is it large or small? Also, note,

$$
\begin{array}{l l}{{\mathrm{var}(R_{1})=490-10^{2}=390~\mathrm{and}}}\ {{}}\ {{\mathrm{var}(R_{2})=1,090-10^{2}=990.}}\end{array}
$$

The correlation coefficient, however, is more intuitive as

$$
\rho(R_{1},R_{2})={\frac{\operatorname{cov}(R_{1},R_{2})}{\sigma(R_{1})\sigma(R_{2})}}={\frac{435}{{\sqrt{390}}{\sqrt{990}}}}={\frac{435}{19.748(31.464)}}=0.7.
$$

A correlation of 0.7 is a strong positive correlation.

An important result that is sometimes seen in finance is that the covariance of a variable with itself is the variance. We can easily see this by letting $y$ also be $x$ and thereby obtaining the covariance of $x$ with itself:

$$
\operatorname{cov}(x,y|y=x)=\operatorname{cov}(x,x)=\sum_{i=1}^{n}{\big[}x_{i}-E(x){\big]}{\big[}x_{i}-E(x){\big]}p_{i}=V a r(x).
$$

IABLE 4.3 Illustration of Supplemental Information to Compute Covariance


<html><body><table><tr><td>Probability (%)</td><td>R(1) (%)</td><td>R(1)2</td><td>R(2) (%)</td><td>R(2)2</td><td>R(1)R(2)</td></tr><tr><td>10%</td><td>-25</td><td>625</td><td>20</td><td>400</td><td>-500</td></tr><tr><td>20%</td><td>-5</td><td>25</td><td>-15</td><td>225</td><td>75</td></tr><tr><td>40%</td><td>10</td><td>100</td><td>0</td><td>0</td><td>0</td></tr><tr><td>20%</td><td>20</td><td>400</td><td>5</td><td>25</td><td>100</td></tr><tr><td>10%</td><td>55</td><td>3,025</td><td>100</td><td>10,000</td><td>5,500</td></tr><tr><td>Sum=100%</td><td>E(R) = 10%</td><td>E(R²) = 490</td><td>E(R)=10%</td><td>E(R²) = 1,090</td><td>E[R(1)R(2)]=535</td></tr></table></body></html>

We also need to know that the covariance of a random variable and a constant is zero:

$$
\operatorname{cov}(x,a)=\sum_{i=1}^{n}{\big[}x_{i}-E(x){\big]}[a-E(a)]p_{i}=\sum_{i=1}^{n}{\big[}x_{i}-E(x){\big]}(a-a)p_{i}=0.
$$

The covariance concept facilitates the understanding of the variance of a combination of more than one random variable. Consider a weighted sum of variables $x$ and $y_{:}$ obtained by multiplying $x$ by $a$ and $\mathrm{y}$ by $b$ . Suppose we wish to find the variance of $ a x+b y$

$$
\begin{array}{r l}{(a x+b y)=}&{\frac{1}{\sqrt{a_{1}}}\left(a x+b y\right)^{2},~R_{1}=}\ {=}&{\frac{1}{\sqrt{a_{1}}}\left(a x_{1}+b y\right)(a x_{1}+b y),~R_{1}=\left(a\frac{1}{\sqrt{a_{1}}}x_{1}+b y\right)^{2}}\ &{=}&{\frac{1}{\sqrt{a_{1}}}\left(a x_{1}+b y\right)(a x_{1}+b y),~R_{1}=\left(a\frac{1}{\sqrt{a_{1}}}x_{1}+b\frac{1}{\sqrt{a_{1}}}y\right)^{2}}\ &{=}&{\frac{1}{\sqrt{a_{1}}}\left(a x_{1}^{2}+2a x_{1}x_{1}+b y^{2}\right),~R_{1}=\left[a(x_{1}+b y)^{2}\right]^{2}}\ &{=}&{a x_{1}^{2},~R_{1}=}\ &{=a x_{1}^{2},~R_{1}=+b y\frac{1}{\sqrt{a_{1}}}\sum_{\alpha=1/{\beta_{1}}}a^{\beta}+\frac{1}{\sqrt{a_{1}}}y^{2},}\ &{=}&{\left\{\begin{array}{l l}{a^{2}({a_{1}}\times{a_{1}})^{2}+2a{a_{1}}{b_{1}}({c_{1}}\times{a_{1}})({b_{1}}+{b_{1}})^{2}}\ {-{a_{1}}{b_{1}}({c_{1}}\times{a_{1}})+{b_{1}}({c_{1}}\times{a_{1}})}\end{array}\right.}\ &{~-\left\{\begin{array}{l l}{a^{2}({a_{1}}\times{a_{1}})^{2}+2{a_{1}}{b_{1}}({c_{1}}\times{a_{1}})({b_{1}}+{b_{1}})^{2}}\ {-{a_{1}}{b_{1}}({c_{1}}\times{a_{1}})+{b_{1}}({c_{1}}\times{a_{1}})}\end{array}\right\}}\ &{=a x_{1}^{2}({a_{1}})+a x_{1}^{2}({a_{1}})+{b_{
$$

Thus, we see that the variance of a weighted sum of random variables is a weighted aver-.
age of the variances of the individual random variables plus twice the weighted covariance.
This result is commonly used in portfolio analysis because it captures the collective volatil-.
ity of correlated variables.

Now let us find the covariance between the weighted variables, that is, $\operatorname{cov}(a x,b y)$

$$
{\begin{array}{r l}&{\operatorname{cov}(a x,b y)=\displaystyle\sum_{i=1}^{n}\left[a x_{i}-E(a x)\right]\left[b y_{i}-E(b y)\right]\phi_{i}}\ &{\qquad=\displaystyle\sum_{i=1}^{n}\left[a x_{i}-a E(x)\right]\left[b y_{i}-b E(y)\right]\phi_{i}}\ &{\qquad=\displaystyle\sum_{i=1}^{n}\left[a x_{i}b y_{i}-a x_{i}b E(y)-a E(x)b y_{i}+a b E(x)E(y)\right]\phi_{i}}\end{array}}
$$

$$
\begin{array}{l}{{=a b\displaystyle\sum_{i=1}^{n}x_{i}y_{i}{p}_{i}-a b E(y)\displaystyle\sum_{i=1}^{n}x_{i}{p}_{i}-a b E(x)\displaystyle\sum_{i=1}^{n}y_{i}{p}_{i}+a b E(x)E(y)\displaystyle\sum_{i=1}^{n}{p}_{i}}}\ {{=a b E(x y)-a b E(y)E(x)-a b E(x)E(y)+a b E(x)E(y)}}\ {{=a b(E(x y)-E(x)E(y))}}\ {{=a b\mathrm{cov}(x,y).}}\end{array}
$$

We may also wish to know what happens to the covariance if we add constants to $x$ and $y$ . Let $a$ and $b$ be constants:

$$
{\begin{array}{r l}{\operatorname{cov}(a+x,b+y)={\underset{i=1}{\overset{n}{\sum}}}\left[a+x_{i}-E(a+x)\right]\left[b+y_{i}-E(b+y)\right]p_{i}}&{}\ {={\underset{i=1}{\overset{n}{\sum}}}\left[a-E(a)+x_{i}-E(x)\right]\left[b-E(b)+y_{i}-E(y)\right]p_{i}}&{}\ {={\underset{i=1}{\overset{n}{\sum}}}\left[a-a+x_{i}-E(x)\right]\left[b-b+y_{i}-E(y)\right]p_{i}}&{}\ {={\underset{i=1}{\overset{n}{\sum}}}\left[x_{i}-E(x)\right]\left[y_{i}-E(y)\right]p_{i}=\operatorname{cov}(x,y).}&{}\end{array}}
$$

Thus, quite logically, adding constants does not change the covariance between two variables.

Finally, we might be interested in the covariance between the sum of two random variables and a third random variable. Letting the third random variable be $z_{:}$ we want to know $\operatorname{cov}(x+y,z)$

$$
{\begin{array}{r l}{\operatorname{cov}(x+y,z)={\displaystyle\sum_{i=1}^{n}\left[x_{i}+y_{i}-E(x+y)\right]\left[z_{i}-E(z)\right]{\mathit{p}}_{i}}}\ {={\displaystyle\sum_{i=1}^{n}\left\{\left[x_{i}-E(x)\right]+\left[y_{i}-E(y)\right]\right\}\left[z_{i}-E(z)\right]{\mathit{p}}_{i}}}\ {={\displaystyle\sum_{i=1}^{n}\left[x_{i}-E(x)\right]\left[z_{i}-E(z)\right]{\mathit{p}}_{i}+\sum_{i=1}^{n}\left[y_{i}-E(y)\right]\left[z_{i}-E(z)\right]{\mathit{p}}_{i}}}\ {=\operatorname{cov}(x,z)+\operatorname{cov}(y,z).}\end{array}}
$$

Based on the data in the last example along with a portfolio composed of $50\%$ of instrument 1 and $50\%$ of instrument 2, Table 4.4 provides supplemental information to. assist in the calculation of the covariance of sums. Here we let. $P$ denote the return on a portfolio of $50\%$ instrument 1 and $50\%$ instrument 2.

Based on Equation (4.4), we have the variance of the portfolio is

$$
\operatorname{var}(P)=E{\big(}P^{2}{\big)}-[E(P)]^{2}=662.5-10^{2}=562.5.
$$

TABLE 4.4 Illustration of Supplemental Information to Compute Covariance of Sums


<html><body><table><tr><td>Probability (%)</td><td>P (%)</td><td>P2</td><td>R(1)*P (%)</td><td>R(2)*P</td></tr><tr><td>10</td><td>-2.5</td><td>6.25</td><td>62.5</td><td>-50</td></tr><tr><td>20</td><td>-10</td><td>100</td><td>50</td><td>150</td></tr><tr><td>40</td><td>5</td><td>25</td><td>50</td><td>0</td></tr><tr><td>20</td><td>12.5</td><td>156.25</td><td>250</td><td>62.5</td></tr><tr><td>10</td><td>77.5</td><td>6,006.25</td><td>4,262.5</td><td>7,750</td></tr><tr><td>Sum=100%</td><td>E(P)= 10%</td><td>E(P2) = 662.5</td><td>E[R(1) * P]=512.5</td><td>E[R(2) * P] = 812.5</td></tr></table></body></html>

Based on the properties of portfolio returns, we know

$$
\begin{array}{r}{P_{i}=0.5(R_{1i})+0.5(R_{2i}).}\end{array}
$$

Thus, based on Equation (4.15), we have the covariance as

$$
\mathrm{cov}(0.5R_{1}+0.5R_{2},P)=\mathrm{cov}(0.5R_{1},P)+\mathrm{cov}(0.5R_{2},P).
$$

From Equation (4.13), we know

$$
\mathrm{cov}(0.5R_{1}+0.5R_{2},P)=0.5\mathrm{cov}(R_{1},P)+0.5\mathrm{cov}(R_{2},P),
$$

$$
\operatorname{cov}(R_{1},P)=E(R_{1}P)-E(R_{1})E(P)=512.5-10(10)=412.5,
$$

$$
\operatorname{cov}(R_{2},P)=E(R_{2}P)-E(R_{2})E(P)=812.5-10(10)=712.5.
$$

Again, interpreting variances and covariances is difficult. From the definition of covariance, we observe the identity

$$
\operatorname{var}(P)=\operatorname{cov}(0.5R_{1}+0.5R_{2},P)=0.5\operatorname{cov}(R_{1},P)+0.5\operatorname{cov}(R_{2},P).
$$

If we divide both sides by the variance of the portfolio, we observe the following percentage marginal contribution to risk (%MCTR) of each instrument in the portfolio:

$$
\begin{array}{r l}&{\%M C T R_{1}=0.5\frac{\mathrm{cov}(R_{1},P)}{\mathrm{var}(P)}=0.5\frac{412.5}{562.5}=36.67\%\mathrm{~and}}\ &{\%M C T R_{2}=0.5\frac{\mathrm{cov}(R_{2},P)}{\mathrm{var}(P)}=0.5\frac{712.5}{562.5}=63.33\%.}\end{array}
$$
