---
tags:
  - '#annuity_factor'
  - '#commercial_real_estate_option'
  - '#market_price_of_risk'
  - '#real_asset_valuation'
  - '#risk_neutral_growth_rate'
  - '#risk_neutral_valuation'
  - '#wiener_process'
---
# 36.2 EXTENSION OF THE RISK-NEUTRAL VALUATION FRAMEWORK  

In Section 28.1 the market price of risk for a variable $\theta$ was defined as  

$$
\lambda=\frac{\mu-r}{\sigma}
$$  

where $r$ is the risk-free rate,. $\mu$ is the return on a traded security dependent only on $\theta$  

and $\sigma$ is its volatility. As shown in Section 28.1, the market price of risk, $\lambda$ , does not depend on the particular traded security chosen.  

Suppose that a real asset depends on several variables $\theta_{i}(i=1,2,...)$ . Let $m_{i}$ and $s_{i}$ be the expected growth rate and volatility of $\theta_{i}$ so that  

$$
d\theta_{i}/\theta_{i}=m_{i}d t+s_{i}d z_{i}
$$  

where $z_{i}$ is a Wiener process. Define $\lambda_{i}$ as the market price of risk of $\theta_{i}$ . Risk-neutral valuation can be extended to show that any asset dependent on the $\theta_{i}$ can be valued byl  

1. Reducing the expected growth rate of each $\theta_{i}$ from $m_{i}$ to $m_{i}\mathrm{~-~}\lambda_{i}s_{i}$   
2. Discounting cash flows at the risk-free rate.  

# Example 36.1  

The cost of renting commercial real estate in a certain city is quoted as the amount that would be paid per square foot per year in a new 5-year rental agreement. The current cost is. $\$30$ per square foot. The expected growth rate. of the cost is. $12\%$ per annum, the volatility of the cost is. $20\%$ per annum, and its. market price of risk is 0.3. A company has the opportunity to pay $\$1$ million now. for the option to rent 100,000 square feet at. $\$35$ per square foot for a 5-year. period starting in 2 years. The risk-free rate is. $5\%$ per annum (assumed constant). Define $V$ as the quoted cost per square foot of office space in 2 years. Assume that rent is paid annually in advance. The payoff from the option is  

$$
100,000A\operatorname*{max}(V-35,0)
$$  

where $A$ is an annuity factor given by  

$$
A=1+1\times e^{-0.05\times1}+1\times e^{-0.05\times2}+1\times e^{-0.05\times3}+1\times e^{-0.05\times4}=4.5355
$$  

The expected payoff in a risk-neutral world is therefore  

$100,000\times4.5355\times{\hat{E}}[\operatorname*{max}(V-35,0)]=453,550\times{\hat{E}}[\operatorname*{max}(V-35,0)]$ where $\hat{E}$ denotes expectations in a risk-neutral world. Using the result in equation (15A.1), this is  

$$
453,550[\hat{E}(V)N(d_{1})\:-\:35N(d_{2})]
$$  

where  

$$
d_{1}={\frac{\ln[{\hat{E}}(V)/35]+0.2^{2}\times2/2}{0.2{\sqrt{2}}}}\quad{\mathrm{and}}\quad d_{2}={\frac{\ln[{\hat{E}}(V)/35]-0.2^{2}\times2/2}{0.2{\sqrt{2}}}}
$$  

The expected growth rate in the cost of commercial real estate in a risk-neutral world is $m\mathrm{~-~}\lambda s$ , where $m$ is the real-world growth rate,. $s$ is the volatility, and. $\lambda$ is the market price of risk. In this case, $m=0.12,s=0.2$ , and $\lambda=0.3$ , so that the expected risk-neutral growth rate is 0.06, or $6\%$ , per year. It follows that. ${\hat{E(V)}}=30e^{0.06\times2}=33.82.$ Substituting this in the expression above gives the expected payoff in a risk-neutral world as $\$1.5015$ million. Discounting at the.  

risk-free rate the value of the option is $1.5015e^{-0.05\times2}=\$1.3586$ million. This shows that it is worth paying $\$1$ million for the option..  
