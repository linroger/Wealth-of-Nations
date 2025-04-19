---
tags:
  - '#common_logarithm'
  - '#continuous_compounding'
  - '#continuously_compounded_interest'
  - '#logarithms_and_exponentials'
  - '#mathematical_operations'
  - '#natural_logarithm'
  - '#rates_of_return'
  - '#terminal_value'
---
# 3.3 LOGARITHMS AND EXPONENTIALS

The logarithm of a number is an exponent to which a base raised to that power equals the number. There are two primary types of logarithms, the base $e$ , called the natural or Naperian log, and the base 10, called the common log. We write the former as. $\log_{\mathrm{e}}$ or sometimes In, and the latter as $\log_{10}$ . In financial applications we nearly always use natural. logs, which is primarily because continuously compounded interest is consistent with the natural log function.

By definition, the natural log of a value $x$ is the power to which $e=2.71828\dots$ must be raised to equal $x$ . That is, when we say that $\ln x=a$ , we mean that $e^{a}=x$

The notation we use for the natural log of. $x$ is sometimes written as $\ln x$ or $\ln(x)$ and occasionally $\log(x)$ . Working with logarithms oftentimes greatly facilitates mathematical operations. The following are typical operations performed with logarithms:

$$
\ln(x y)=\ln x+\ln y,
$$

$$
\ln\left(x^{a}\right)=a\ln x,
$$

$$
\ln(\frac{x}{y})=\ln x-\ln y,
$$

$$
\ln e=1,
$$

$$
\ln1=0.
$$

Be aware, however, that $\ln(x+y)\neq\ln x+\ln y$

The mathematical definition of $e$ is

$$
e=\operatorname*{lim}_{n\to\infty}{\left(1+{\frac{1}{n}}\right)}^{n}.
$$

The expression $e^{x}$ , which is

$$
e^{x}=\operatorname*{lim}_{n\to\infty}{\left(1+{\frac{x}{n}}\right)}^{n},
$$

and can be approximated as

$$
e^{x}=\operatorname*{lim}_{n\to\infty}\left(1+x+{\frac{1}{2!}}x^{2}+{\frac{1}{3!}}x^{3}+\cdot\cdot\cdot+{\frac{1}{n!}}x^{n}\right)=\sum_{i=0}^{\infty}x^{i}/i!.
$$

The expression $e^{x}$ is sometimes written $\exp(x)$ . Some typical operations with the exponential function are as follows:

$$
\begin{array}{c}{{e^{x}e^{y}=e^{x+y},}}\ {{{e}^{x}e^{-y}=e^{x-y},\mathrm{and}}}\ {{{\left(e^{x}\right)}^{n}=e^{n x}.}}\end{array}
$$

Rather than compute discrete rates of return, it is often much more useful to compute. continuously compounded rates of return $(R_{t}^{c})$ . Following the previous illustration, we. assume monthly continuous compounding. The monthly continuous rate of return can be expressed as

$$
R_{t}^{c}=\ln\left(\frac{V_{t}}{V_{t-1}}\right).
$$

Clearly, we once again must assume an initial positive value and no possibility of nonpositive value in the future as $\ln(0)$ is undefined. Unfortunately, many instruments have a. significant chance of being nonpositive in the future. The terminal value at time $t$ can be expressed as

$$
V_{t}=V_{t-1}e^{R_{t}^{c}}.
$$

Thus, the monthly total return with continuous compounding is

$$
T R_{t}=\frac{V_{t}}{V_{t-1}}=e^{R_{t}^{c}}.
$$

Again, consider a portfolio's performance over the past five years measured monthly with continuous compounding. Hence, we have 60 observations of the rate of return and. the five-year total return is

$$
T R_{T}=\frac{V_{T}}{V_{0}}=\prod_{t=1}^{60}T R_{t}=\prod_{t=1}^{60}e^{R_{t}^{c}}=e^{\sum_{t=1}^{60}R_{t}^{c}}.
$$

Using the previous product and summation properties, one could again easily manipu-. late total returns based on calendar months (January, February, and so forth) or further decompose monthly total returns into daily returns.
