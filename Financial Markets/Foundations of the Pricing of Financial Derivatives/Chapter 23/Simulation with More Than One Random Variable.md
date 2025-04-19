---
tags:
  - asset_pricing
  - correlation
  - interest_rates
  - random_variables
  - simulation
aliases:
  - correlated variables
  - multiple random variables
key_concepts:
  - expected values, variances
  - generate normal values
  - independent variables
  - linear correlation
  - simulate random variables
---

# 23.3 SIMULATION WITH MORE THAN ONE RANDOM VARIABLE

In some cases, we wish to simulate more than one random variable. In certain situations, these variables are independent; in others, the two variables are related. Independent random variables are similar to rolling a pair of dice. What happens on one die is unrelated to what happens on another die. If the random variables of interest have that characteristic,. it is a simple matter to run two parallel simulations, each generating random variables that are completely unrelated to each other. In some cases, however, the random variables are related, most often in a linear manner. The linear relationship between random variables is captured by the correlation.5

Suppose we wish to generate two normal random values that have correlation of $\rho$ which could be two asset prices or interest rates. First, we generate two independent, standard normal random values $x_{1}$ and $x_{2}$ . We set $\varepsilon_{1}$ equal to $x_{1}$ and obtain $\varepsilon_{2}$ in the following manner:

$$
\varepsilon_{2}=\rho x_{1}+x_{2}{\sqrt{1-\rho^{2}}}.
$$

The reason this formula works is simple.

$$
\begin{array}{r l}&{E(\varepsilon_{1})=E(x_{1})=0}\ &{E(\varepsilon_{2})=E\left(\rho x_{1}+x_{2}\sqrt{1-\rho^{2}}\right)=p E\left(x_{1}\right)+\sqrt{1-\rho^{2}}E\left(x_{2}\right)=0}\end{array}
$$

var $\left(\varepsilon_{1}\right)=\mathrm{var}\left(x_{1}\right)=1$

$$
\begin{array}{r l}&{\mathrm{var}\left(\varepsilon_{2}\right)=\mathrm{var}\left(\rho\mathrm{x}_{1}+x_{2}\sqrt{1-\rho^{2}}\right)}\ &{\qquad=\rho^{\mathrm{var}}\left(x_{1}\right)+\left(1-\rho^{2}\right)\mathrm{var}\left(x_{2}\right)+2\rho\sqrt{1-\rho^{2}}\mathrm{cov}\left(x_{1},x_{2}\right)}\ &{\qquad=\rho^{2}+1-\rho^{2}+0=1}\ &{\qquad=\rho^{2}+1-\rho^{2}+0=1}\ &{\qquad\quad}\ &{\varepsilon\left(\varepsilon_{1},\varepsilon_{2}\right)=\mathrm{corr}\left(x_{1},\rho x_{1}+x_{2}\sqrt{1-\rho^{2}}\right)}\ &{\qquad=\frac{\mathrm{cov}\left(x_{1},\rho x_{1}+x_{2}\sqrt{1-\rho^{2}}\right)}{\mathrm{var}\left(\varepsilon_{1},\varepsilon_{2}\right)}=\mathrm{cov}\left(x_{1},\rho x_{1}+x_{2}\sqrt{1-\rho^{2}}\right)}\ &{\qquad=\mathrm{cov}\left(x_{1},\rho x_{1}\right)+\mathrm{cov}\left(x_{1},x_{2}\sqrt{1-\rho^{2}}\right)=\rho\mathrm{cov}\left(x_{1},x_{1}\right)+\sqrt{1-\rho^{2}}\mathrm{cov}\left(x_{1},x_{2}\right)}\ &{\qquad=\rho\mathrm{sar}\left(x_{1}\right)+0=\rho\mathrm{sar}\left(x_{1}\right)}\ &{\qquad=\rho,}\end{array}
$$

These proofs show that the two independent random variables have expected values of 0, variances of 1, and a correlation of. $\rho$ . Thus, they meet our requirements. Now, armed with. values of $\varepsilon_{1}$ and $\varepsilon_{2}$ , we can proceed by inserting into the analog of Equation (23.5) for each of the two assets, using the respective values of the expected change and volatility of each asset we are simulating.
