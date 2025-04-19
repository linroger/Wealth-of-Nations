---
tags:
  - financial_modeling
  - lognormal_distribution
  - normal_distribution
  - portfolio_instruments
aliases:
  - Bivariate Lognormal
  - Bivariate Simulation
  - Lognormal Distribution
key_concepts:
  - Bivariate lognormal simulation
  - Lognormal probability distribution
  - Normal distribution property
  - Portfolio of instruments
  - Sum of lognormal variables
---

# 5.4 THE BIVARIATE LOGNORMAL PROBABILITY DISTRIBUTION

Again if $S_{t}=S_{t-1}e^{R_{t}^{c}}$ and $R_{t}^{c}$ is normally distributed, then we know $S_{t}$ is lognormally distributed. In finance, we are often interested in a portfolio of instruments such as stock holdings. Unfortunately, the sum of lognormally distributed random variables does not follow any known distribution. One important property of the normal distribution is that the sum of normally distributed random variables is itself normally distributed. Thus, in practice, it is dramatically easier to assume the underlying instrument prices are normally distributed, an issue we address in Chapter 12.

Figure 5.6 illustrates a simulation of 1,000 draws from a bivariate lognormal distribu-. tion, with normal mean 0, variance 1, and correlation 0. Note that the bivariate lognormal. lower bound is zero for both $x$ and $y$ , but it is non-inclusive. Specifically, an outcome of zero did not occur because it is not possible with the lognormal distribution. Therefore, one advantage of the lognormal distribution is that negative values are not possible. Closely related, one disadvantage of the lognormal distribution is that zero values are also not possible.

![](790401a9c4eadb71215e4f5dc64a32acb81f57fea78bfbfc4c8c16d75ca99764.jpg)
FIGURE 5.6 Bivariate Lognormal Simulation
