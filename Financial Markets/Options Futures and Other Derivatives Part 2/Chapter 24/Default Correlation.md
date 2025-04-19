---
tags:
  - '#credit_risk'
  - '#default_correlation'
  - '#factor_based_correlation'
  - '#gaussian_copula_model'
  - '#hazard_rate'
  - '#reduced_form_models'
  - '#structural_models'
  - '#time_to_default'
---
# 24.8 DEFAULT CORRELATION  

The term default correlation is used to describe the tendency for two companies to. default at about the same time. There are a number of reasons why default correlation exists. Companies in the same industry or the same geographic region tend to be. affected similarly by external events and as a result may experience financial difficulties. at the same time. Economic conditions generally cause average default rates to be. higher in some years than in other years. A default by one company may cause a default. by another-the credit contagion effect. Default correlation means that credit risk cannot be completely diversified away and is the major reason why risk-neutral default. probabilities are greater than real-world default probabilities (see Section 24.5)..  

Default correlation is important in the determination of probability distributions for default losses from a portfolio of exposures to different counterparties.13 Two types of default correlation models that have been suggested by researchers are referred to as reduced form models and structural models.  

Reduced form models assume that the hazard rates for different companies follow stochastic processes and are correlated with macroeconomic variables. When the hazard rate for company A is high there is a tendency for the hazard rate for company B to be high. This induces a default correlation between the two companies.  

Reduced form models are mathematically attractive and reflect the tendency for economic cycles to generate default correlations. Their main disadvantage is that the range of default correlations that can be achieved is limited. Even when there is a perfect correlation between the hazard rates of the two companies, the probability that they will both default during the same short period of time is usually very low. This is liable to be a problem in some circumstances. For example, when two companies operate in the same industry and the same country or when the financial health of one company is for some reason heavily dependent on the financial health of another company, a relatively high default correlation may be warranted. One approach to solving this problem is by extending the model so that the hazard rate exhibits large jumps.  

Structural models are based on a model similar to Merton's model (see Section 24.6). A company defaults if the value of its assets is below a certain level. Default correlation between companies A and B is introduced into the model by assuming that the stochastic process followed by the assets of company A is correlated with the stochastic process followed by the assets of company B. Structural models have the advantage over reduced form models that the correlation can be made as high as desired. Their main disadvantage is that they are liable to be computationally quite slow.  

# The Gaussian Copula Model for Time to Default  

A model that has become a popular practical tool is the Gaussian copula model for the. time to default. It can be shown to be similar to Merton's structural model. It assumes that all companies will default eventually and attempts to quantify the correlation between the. probability distributions of the times to default for two or more different companies..  

The model can be used in conjunction with either real-world or risk-neutral default. probabilities. The left tail of the real-world probability distribution for the time to default of a company can be estimated from data produced by rating agencies such as that in Table 24.1. The left tail of the risk-neutral probability distribution of the time to default can be estimated from bond prices using the approach in Section 24.4..  

Define $t_{1}$ as the time to default of company 1 and $t_{2}$ as the time to default of company 2. If the probability distributions of $t_{1}$ and $t_{2}$ were normal, we could assume that the joint probability distribution of $t_{1}$ and $t_{2}$ is bivariate normal. As it happens, the probability distribution of a company's time to default is not even approximately normal. This is where a Gaussian copula model comes in. We transform $t_{1}$ and $t_{2}$ into new variables $x_{1}$ and $x_{2}$ using  

$$
x_{1}=N^{-1}[Q_{1}(t_{1})],\qquadx_{2}=N^{-1}[Q_{2}(t_{2})]
$$  

where $Q_{1}$ and $Q_{2}$ are the cumulative probability distributions for $t_{1}$ and $t_{2}$ , and $N^{-1}$ is the inverse of the cumulative normal distribution $(u=N^{-1}(\nu)$ when $\nu=N(u)$ ). These are "percentile-to-percentile" transformations. The 5-percentile point in the probability distribution for $t_{1}$ is transformed to $x_{1}=-1.645$ , which is the 5-percentile point in the standard normal distribution; the 10-percentile point in the probability distribution for $t_{1}$ is transformed to $x_{1}=-1.282$ , which is the 10-percentile point in the standard normal distribution; and so on. The $t_{2}$ to $x_{2}$ transformation is similar.  

By construction, $x_{1}$ and $x_{2}$ have normal distributions with mean zero and unit standard deviation. The model assumes that the joint distribution of $x_{1}$ and $x_{2}$ is bivariate normal. This assumption is referred to as using a Gaussian copula. The assumption is convenient because it means that the joint probability distribution of $t_{1}$ and $t_{2}$ is fully defined by the cumulative default probability distributions $Q_{1}$ and $Q_{2}$ for $t_{1}$ and $t_{2}$ , together with a single correlation parameter that defines the correlation between $x_{1}$ and $x_{2}$  

The attraction of the Gaussian copula model is that it can be extended to many companies. Suppose that we are considering $n$ companies and that $t_{i}$ is the time to default of the ith company. We transform each. $t_{i}$ into a new variable,. $x_{i},$ that has a standard normal distribution. The transformation is the percentile-to-percentile transformation  

$$
x_{i}=N^{-1}[Q_{i}(t_{i})]
$$  

where $Q_{i}$ is the cumulative probability distribution for $t_{i}$ It is then assumed that the $x_{i}$ are multivariate normal. The default correlation between $t_{i}$ and $t_{j}$ is measured as the correlation between x, and x /. Thi is referred to as the copula correlation.14  

The Gaussian copula is a useful way of representing the correlation structure between variables that are not normally distributed. It allows the correlation structure of the variables to be estimated separately from their marginal (unconditional) distributions. Although the variables themselves are not multivariate normal, the approach assumes that after a transformation is applied to each variable they are multivariate normal.  

# Example 24.7  

Suppose that we wish to simulate defaults during the next 5 years in 10 companies. The copula default correlations between each pair of companies is 0.2. For each company the cumulative probability of a default during the next 1, 2, 3, 4, 5 years is $1\%$ $3\%$ $6\%$ $10\%$ $15\%$ , respectively. When a Gaussian copula is used. we sample from a multivariate normal distribution to obtain the $x_{i}$ $1\leq i\leq10$ with the pairwise correlation between the. $x_{i}$ being 0.2. We then convert the. $x_{i}$ to $t_{i}$ a time to default. When the sample from the normal distribution is less than $N^{-1}(0.01)=-2.33$ , a default takes place within the first year; when the sample is between $-2.33$ and $N^{-1}(0.03)=-\bar{1}.88$ , a default takes place during the second. year; when the sample is between $-1.88$ and $N^{-1}(0.06)\overset{^{\circ}}{=}-1.55$ , a default takes place during the third year; when the sample is between $-1.55$ and $N^{-1}(0.10)=$ $-1.28$ , a default takes place during the fourth year; when the sample is between $-1.28$ and $N^{-1}(0.15)\stackrel{_}{=}-1.04$ , a default takes place during the fifth year. When. the sample is greater than. $-1.04$ , there is no default during the 5 years.  

# A Factor-Based Correlation Structure  

To avoid defining a different correlation between $x_{i}$ and $x_{j}$ for each pair of companies $i$ and $j$ in the Gaussian copula model, a one-factor model is often used. The assumption is that  

$$
x_{i}=a_{i}F+\sqrt{1-a_{i}^{2}}Z_{i}
$$  

In this equation, $F$ is a common factor affecting defaults for all companies and $Z_{i}$ is a factor affecting only company $i.$ The variable $F$ and the variables $Z_{i}$ have independent standard normal distributions. The $a_{i}$ are constant parameters between $-1$ and $+1$ . The correlation between $x_{i}$ and $x_{j}$ .5 $a_{i}a_{j}.$  

Suppose that the probability that company $i$ will default by a particular time. $T$ is $Q_{i}(T)$ . Under the Gaussian copula model, a default happens by time $T$ when $N(x_{i})<Q_{i}(T)$ or $x_{i}<N^{-1}[Q_{i}(T)]$ . From equation (24.7), this condition is.  

or  

$$
\begin{array}{c}{{a_{i}F+\sqrt{1-a_{i}^{2}}Z_{i}<N^{1}[Q_{i}(T)]}}\ {{{}}}\ {{Z_{i}<\displaystyle\frac{N^{-1}[Q_{i}(T)]-a_{i}F}{\sqrt{1-a_{i}^{2}}}}}\end{array}
$$  

Conditional on the value of the factor $F$ , the probability of default is therefore  

$$
Q_{i}(T\mid F)=N\left({\frac{N^{-1}[Q_{i}(T)]-a_{i}F}{\sqrt{1-a_{i}^{2}}}}\right)
$$  

A particular case of the one-factor Gaussian copula model is where the probability distributions of default are the same for all $i$ and the correlation between $x_{i}$ and $x_{j}$ is the same for all $i$ and $j$ . Suppose that $Q_{i}(T)=Q(T)$ for all $i$ and that the common correlation is $\rho$ , so that $a_{i}=\sqrt{\rho}$ for all $i$ Equation (24.8) becomes  

$$
Q(T\mid F)=N\Biggl({\frac{N^{-1}[Q(T)]-\sqrt{\rho}F}{\sqrt{1-\rho}}}\Biggr)
$$  
