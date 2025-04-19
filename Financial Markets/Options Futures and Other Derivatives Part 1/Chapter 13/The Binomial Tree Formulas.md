---
tags:
  - american_option
  - binomial_tree
  - option_pricing
  - risk_free_rate
  - volatility
aliases:
  - Binomial Model Formulas
  - Binomial Tree Method
  - CRR Model
key_concepts:
  - American put option
  - Binomial tree
  - Risk-free rate
  - Stock price
  - Time step
---

# 13.8 THE BINOMIAL TREE FORMULAS  

The analysis in the previous section shows that, when the length of the time step on a binomial tree is $\Delta t$ we should match volatility by setting  

$$
u=e^{\sigma{\sqrt{\Delta t}}}
$$  

and  

$$
d=e^{-\sigma{\sqrt{\Delta t}}}
$$  

Also, from equation (13.6),  

$$
p={\frac{a-d}{u-d}}
$$  

where  

$$
a=e^{r\Delta t}
$$  

Equations (13.15) to (13.18) define the tree.  

Consider again the American put option in Figure 13.8, where the stock price is $\$50$ the strike price is $\$52$ , the risk-free rate is $5\%$ , the life of the option is 2 years, and there. are two time steps. In this case,. $\Delta t=1$ . Suppose that the volatility $\sigma$ is $30\%$ . Then, from equations (13.15) to (13.18), we have.  

$$
u=e^{0.3\times1}=1.3499,~d=\frac{1}{1.3499}=0.7408,~a=e^{0.05\times1}=1.0513
$$  

and  

$$
p={\frac{1.0513-0.7408}{1.3499-0.7408}}=0.5097
$$  

The tree is shown in Figure 13.10. The value of the put option is 7.43. (This is different from the value obtained in Figure 13.8 by assuming. $u=1.2$ and $d=0.8.$ Note that the option is exercised at the end of the first time step if the lower node is reached.  
