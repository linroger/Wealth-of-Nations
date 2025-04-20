---
tags:
  - cds_pricing
  - credit_derivatives
  - default_correlation
  - gaussian_copula
  - poisson_model
aliases:
  - CDS Modeling
  - Copulas
  - Default Correlation
  - Gaussian Copula Example
key_concepts:
  - CDS pricing
  - Copula functions
  - Default correlation modeling
  - Gaussian copula
  - Marginal probability distributions
  - Poisson default model
---

# 10.3  COPULAS AND THE MODELING OF DEFAULT CORRELATION  

Since the bulk of the credit derivatives business is in individual name CDSs, and for each name multiple maturity CDSs trade at the same time, calibrating marginal default probability distributions and simple univariate default models - like those in Chapter 7 - is quite easy. However, the individual CDSs contain no information about the default correlation structure. among different names. These have to be extracted from basket structures or CDOs. The main problem in modeling default correlation is the simple fact that, in mathematical statistics, very few distributions generalize easily from univariate to multivariate functions. While the multivariate normal distribution consists of correlated marginal univariate normals, the same.  

![](76618f315002d5374a776c57dafcffc8c17fb15af352a8342f6bb527e1fbf0b0.jpg)  
Figure 10.6 Hedging a long position in the first-to-default basket  

is not generally true of other distributions with non-independent marginals or transforms of known distributions. Defaults are binary events that are most naturally handled with Poisson or Gamma processes, not continuous normals. The main way of dealing with the problem of generalizing univariates to correlated multivariates is through the use of copula functions.  

The essence of the copula method is to start with known marginal probability distributions. and, since they may not generalize easily to a tractable multivariate distribution, to map them one-by-one into new marginal probability distributions, on which to impose a correlation structure and a tractable multivariate distribution. The transformation mappings are called. copula functions. Thus we do not model directly the correlation of defaults; instead we define. correlations for random variables that are one-for-one transforms of individual defaults, and then fit the model to observed prices. We start with a numerical example of a Gaussian copula and then discuss extensions and calibration issues..  

# 10.3.1 A Gaussian Copula  

Recall from Chapter 7 the Poisson model of the default probability of an individual credit. It takes as input a "failure" intensity parameter $\lambda$ observed over a period $\omega$ . A credit may default with a probability of. $\lambda=0.005$ over the period of $\omega=10$ years. These two parameters define the mean $\mu=\lambda\omega=0.05$ of the Poisson probability density function $f(x)$ of a discrete random variable $x$ , which is the number of '"failures" (defaults) over the interval. $\omega$ . In the pricing of CDSs, we are not interested in more than one default for the same issuer. We are. mostly interested in the probability of survival $f(0)$ , i.e. the probability of no failure. This univariate set-up easily extends to the case of $\lambda$ changing over time deterministically and we can calibrate the vector of input parameters $\mu$ if we observe sequential CDS prices for longer maturities.  

Suppose, by observing CDS spread levels, we have fitted constant. $\mu\mathrm{s}$ for two credits.. ABC is a C-rated company with $\lambda=0.03$ $\omega=10$ , and $\mu=\lambda\omega=0.3.$ SAF is a DD-rated company with $\lambda=0.05$ $\omega=10$ , and $\mu=\lambda\omega=0.5$ We let $x_{1}$ denote the number of ABC defaults and $x_{2}$ denote the number of SAF defaults. We transform the variables. $x_{1}$ and $x_{2}$ into two new standard normal variables $y_{1}$ and $y_{2}$ . We do this by computing the cumulative. Poisson distribution values for $x_{1}$ and $x_{2}$ and finding the standard normal values $y_{1}$ and $y_{2}$ that correspond to the same cumulative probabilities. Because the new variables are normal or Gaussian, we call this mapping a Gaussian copula. Table 10.1 shows the Poisson density and. cumulative probability values for $x_{1}$ and $x_{2}$ and the corresponding standard normals $y_{1}$ and $y_{2}$  

We then postulate that the correlation between the two new random variables $y_{1}$ and $y_{2}$ is equal to $\rho=0.5$ .With the copula correspondences $x_{1}\leftrightarrow y_{1}$ and $x_{2}\leftrightarrow y_{2}$ established, it is easy to construct a two-dimensional table of the cumulative probability density values of the default variables $x_{1}$ and $x_{2}$ . Table 10.2 shows these numbers for $x_{1}$ and $x_{2}$ running from 0 to 3.  

Table 10.1  A Gaussian copula of two Poisson variables   


<html><body><table><tr><td>X1</td><td>Poisson p.d.f.</td><td>Poisson c.d.f.</td><td>y1</td><td>X2</td><td>Poisson p.d.f.</td><td>Poisson c.d.f.</td><td>y2</td></tr><tr><td>0</td><td>0.740818</td><td>0.740818</td><td>0.6459</td><td>0</td><td>0.606531</td><td>0.606531</td><td>0.2703</td></tr><tr><td>1</td><td>0.222245</td><td>0.963064</td><td>1.7874</td><td>1</td><td>0.303265</td><td>0.909796</td><td>1.3395</td></tr><tr><td>2</td><td>0.033337</td><td>0.996401</td><td>2.6875</td><td>2</td><td>0.075816</td><td>0.985612</td><td>2.1866</td></tr><tr><td>3</td><td>0.003334</td><td>0.999734</td><td>3.4643</td><td>3</td><td>0.012636</td><td>0.998248</td><td>2.9197</td></tr><tr><td>4</td><td>0.000250</td><td>0.999984</td><td>4.1618</td><td>4</td><td>0.001580</td><td>0.999828</td><td>3.5795</td></tr><tr><td>5</td><td>0.000015</td><td>0.999999</td><td>4.8025</td><td>5</td><td>0.000158</td><td>0.999986</td><td>4.1865</td></tr></table></body></html>  

Table 10.2 Cumulative joint probability of $x_{1}$ and $x_{2}$   


<html><body><table><tr><td></td><td colspan="4">X2=</td></tr><tr><td>X1</td><td>0</td><td>1</td><td>2</td><td>3</td></tr><tr><td>0</td><td>0.5163</td><td>0.7058</td><td>0.7374</td><td>0.7406</td></tr><tr><td>1</td><td>0.6000</td><td>0.8872</td><td>0.9527</td><td>0.9620</td></tr><tr><td>2</td><td>0.6062</td><td>0.9083</td><td>0.9828</td><td>0.9948</td></tr><tr><td>3</td><td>0.6065</td><td>0.9097</td><td>0.9854</td><td>0.9980</td></tr></table></body></html>  

# 10.3.2 General Copula Models  

The Gaussian copula generalizes easily to many random variables. Once the default random. variables are transformed into univariate normals, the marginal normals form a multivariate normal distribution have known properties, with the inputs limited to the correlation matrix..  

While the copula method solves the issue of generalizing marginal univariate distributions, it is not without its own problems. First, the correlation inputs are not the correlations of defaults, but the correlations of artificially created random variables with one-to-one correspondences to the default random variables. The issue is compounded by the fact that derivative valuation imposes no-arbitrage conditions which result in risk-neutral pricing. Thus the correlation structure we impose is not only not directly that of the defaults themselves, but is also the. risk-neutral correlation, making it even harder to interpret. All this necessitates another layer of model calibration with potentially irresolvable pricing inconsistencies. For any model to be useful, the inputs have to be intuitive and easily extracted from securities priced in liquid markets. In a credit derivative model, an intuitive input would be the default correlation. This could, for example, be checked against historical evidence for similar names or credit. categories. In order to use a copula model, one can start with default correlations and then try to. fit the correlation structure of the copula-transformed variables to produce the desired default. variable correlation structure, or basket derivative prices, in the market. As in calibration, the. problem may be under- or overdetermined. We may observe too few or too many basket prices to fit the model. In the first case, we may have to simplify the correlation matrix through parameterization. In the second case, we may not be able to match all the observed prices.  

The under-determined case is often treated with a factor model. Suppose we try to model the correlation structure for hundreds of credits in a portfolio. There is hardly any chance to precisely fit each pairwise correlation by observing basket structures containing those pairs. Similar to the method used in modeling the risk of equity baskets, we can impose an index structure on the default correlations. Instead of transforming. $x$ s into ys individually, we impose. a common-factor structure:  

$$
\begin{array}{c}{y_{1}=\theta_{1}I+\sqrt{1-\theta_{1}}z_{1}}\ {y_{2}=\theta_{2}I+\sqrt{1-\theta_{2}}z_{2}}\end{array}
$$  

where the common factor $I$ is of a desirable form, normal in the Gaussian case, and the $\theta\mathrm{s}$ are the correlations of each transformed default variable. $y$ with the index. This simplification.  

reduces the number of inputs from $n(n{-}I)/2$ for the entire pairwise correlation matrix to. $n$ in a diagonal form of factor-credit correlations (like betas in the equity model).  

Finally, defaults are low-probability tail events. In the example above, we deliberately used risky credits with fairly high default probabilities to generate cumulative probabilities distinguishably less than 1 in Table 10.2. When dealing with investment-grade credits, the individual default probabilities are extremely low. Therefore, credit modeling is, by definition, confined to the modeling of the tails of distributions. In the multivariate case, this is even. harder since the cumulative densities have to be computed numerically and with some error. One way to deal with it is by the use of a Student $t\cdot$ -copula instead of a Gaussian copula. The $t$ -distribution is much more fat-tailed, and the factor model still works if we assume that $I$ is Student $t$ distributed and the zs are standard normal. The other way to deal with it is to abandon the modeling of the entire distributions and focus on multivariate modeling and parameterization of the tails alone. Some successes have been reported with the use of Pareto functions as tail approximations, but multivariate tail modeling remains a challenge. The interested reader may want to look into the Extreme Value Theory research initially applied to VaR modeling.  
