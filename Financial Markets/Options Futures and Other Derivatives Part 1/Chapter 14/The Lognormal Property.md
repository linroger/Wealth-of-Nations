---
tags:
  - ito_lemma
  - lognormal_distribution
  - lognormal_property
  - stock_price
  - wiener_process
aliases:
  - Lognormal Distribution
  - Stock Price Behavior
key_concepts:
  - Generalized Wiener process
  - Ito's lemma application
  - Logarithm normal distribution
  - Lognormal price distribution
  - Stock price lognormal model
---

# 14.7 THE LOGNORMAL PROPERTY  

We now use Ito's lemma to derive the process followed by $\ln S$ when $S$ follows the process in equation (14.13). We define  

$$
G=\ln S
$$  

Since  

$$
\frac{\partial G}{\partial S}=\frac{1}{S},\qquad\frac{\partial^{2}G}{\partial S^{2}}=-\frac{1}{S^{2}},\qquad\frac{\partial G}{\partial t}=0
$$  

it follows from equation (14.14) that the process followed by $G$ is  

$$
d G=\left(\mu-{\frac{\sigma^{2}}{2}}\right)d t+\sigma d z
$$  

Since $\mu$ and $\sigma$ are constant, this equation indicates that $G=\ln S$ follows a generalized Wiener process. It has constant drift rate $\mu-\sigma^{2}/2$ and constant variance rate $\sigma^{2}$ . Thee  

change in ln $S$ between time 0 and some future time $T$ is therefore normally distributed,. with mean $(\mu-\sigma^{2}/2)T$ and variance $\sigma^{2}T.$ This means that  

or  

$$
\ln S_{T}-\ln S_{0}\sim\phi\biggl[\biggl(\mu-\frac{\sigma^{2}}{2}\biggr)T,\sigma^{2}T\biggr]
$$  

$$
\ln S_{T}\sim\phi\biggl[\ln S_{0}+\biggl(\mu-\frac{\sigma^{2}}{2}\biggr)T,\sigma^{2}T\biggr]
$$  

where $S_{T}$ is the stock price at time $T$ $S_{0}$ is the stock price at time $0$ , and as before $\phi(m,\nu)$ denotes a normal distribution with mean $m$ and variance $\nu$  

Equation (14.19) shows that ln $S_{T}$ is normally distributed. A variable has a lognormal distribution if the natural logarithm of the variable is normally distributed. The model of stock price behavior we have developed in this chapter therefore implies that a stock's price at time $T$ given its price today, is lognormally distributed. The standard deviation of the logarithm of the stock price is $\sigma{\sqrt{T}}.$ It is proportional to the square root of how far ahead we are looking.  
