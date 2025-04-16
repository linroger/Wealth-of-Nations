---
tags:
  - '#arbitrage_pricing_theory'
  - '#capital_asset_pricing_model_capm'
  - '#excess_return'
  - '#expected_return'
  - '#ito_lemma'
  - '#market_price_of_risk'
  - '#nonsystematic_risk'
  - '#stochastic_processes'
  - '#systematic_risk'
---
# 28.2  SEVERAL STATE VARIABLES  

Suppose that $n$ variables, $\theta_{1},\theta_{2},\ldots.\theta_{n}$ , follow stochastic processes of the form  

$$
\frac{d\theta_{i}}{\theta_{i}}=m_{i}d t+s_{i}d z_{i}
$$  

for $i=1,2$ ,..., n, where the $d z_{i}$ are Wiener processes. The parameters $m_{i}$ and $s_{i}$ are expected growth rates and volatilities and may be functions of the $\theta_{i}$ and time. Equation (14A.10) in the appendix to Chapter 14 provides a version of Ito's lemma that covers functions of several variables. It shows that the process for the price $f$ of a security that is dependent on the $\theta_{i}$ has $n$ stochastic components. It can be written  

$$
\frac{d f}{f}=\mu d t+\sum_{i=1}^{n}\sigma_{i}d z_{i}
$$  

In this equation, $\mu$ is the expected return from the security and $\sigma_{i}d z_{i}$ is the component of the risk of this return attributable to. $\theta_{i}$ . Both $\mu$ and the $\sigma_{i}$ are potentially dependent on the $\theta_{i}$ and time.  

Technical Note 30 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes shows that  

$$
\mu-r=\sum_{i=1}^{n}\lambda_{i}\sigma_{i}
$$  

where $\lambda_{i}$ is the market price of risk for $\theta_{i}.$ This equation relates the expected excess return that investors require on the security to the. $\lambda_{i}$ and $\sigma_{i}$ Equation (28.9) is the particular case of this equation when. $n=1$ . The term $\lambda_{i}\sigma_{i}$ on the right-hand side measures the. extent that the excess return required by investors on a security is affected by the dependence of the security on. $\theta_{i}.$ If $\lambda_{i}\sigma_{i}=0$ , there is no effect; if. $\lambda_{i}\sigma_{i}>0$ , investors require a higher return to compensate them for the risk arising from. $\theta_{i};$ if $\lambda_{i}\sigma_{i}<0$ , the dependence of the security on $\theta_{i}$ causes investors to require a lower return than would. otherwise be the case. Thee $\lambda_{i}\sigma_{i}<0$ situation occurs when the variable has the effect of reducing rather than increasing the risks in the portfolio of a typical investor..  

# Example 28.3  

A stock price depends on three underlying variables: the price of oil, the price of gold, and the performance of a stock index. Suppose that the market prices of risk for these variables are 0.2, $-0.1$ , and 0.4, respectively. Suppose also that the. $\sigma_{i}$ in  

equation (28.12) corresponding to the three variables have been estimated as 0.05, 0.1, and 0.15, respectively. The excess return on the stock over the risk-free rate is  

$$
0.2\times0.05-0.1\times0.1+0.4\times0.15=0.06
$$  

or $6.0\%$ per annum. If variables other than those considered affect the stock. price, this result is still true provided that the market price of risk for each of these other variables is zero..  

Equation (28.13) is closely related to arbitrage pricing theory, developed by Stephen. Ross in 1976.2 The continuous-time version of the capital asset pricing model (CAPM) can be regarded as a particular case of the equation. CAPM (see appendix to Chapter 3) argues that an investor requires excess returns to compensate for any risk that is correlated to the risk in the return from the stock market, but requires no excess return for other risks. Risks that are correlated with the return from the stock market are. referred to as systematic; other risks are referred to as nonsystematic. If CAPM is true,. then $\lambda_{i}$ is proportional to the correlation between changes in $\theta_{i}$ and the return from the market. When $\theta_{i}$ is uncorrelated with the return from the market, $\lambda_{i}$ is zero.  
