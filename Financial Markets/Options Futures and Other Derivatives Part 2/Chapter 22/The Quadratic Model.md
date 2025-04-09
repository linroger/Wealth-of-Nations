# 22.5  THE QUADRATIC MODEL  

When a portfolio includes options, the linear model is an approximation. It does not.   
take account of the gamma of the portfolio. As discussed in Chapter 19, delta is defined.   
as the rate of change of the portfolio value with respect to an underlying market.   
variable and gamma is defined as the rate of change of the delta with respect to the.   
market variable. Gamma measures the curvature of the relationship between the portfolio value and an underlying market variable..  

Figure 22.3 shows the impact of a nonzero gamma on the probability distribution of. the value of the portfolio. When gamma is positive, the probability distribution tends to. be positively skewed; when gamma is negative, it tends to be negatively skewed. Figures 22.4 and 22.5 illustrate the reason for this result. Figure 22.4 shows the relationship between the value of a long call option and the price of the underlying asset. A long. call is an example of an option position with positive gamma. The figure shows that, when the probability distribution for the price of the underlying asset at the end of 1 day is normal, the probability distribution for the option price is positively skewed.8. Figure 22.5 shows the relationship between the value of a short call position and the price of the underlying asset. A short call position has a negative gamma. In this case, we see that a normal distribution for the price of the underlying asset at the end of 1 day gets mapped into a negatively skewed distribution for the value of the option position..  

The VaR or ES for a portfolio is critically dependent on the left tail of the probability distribution of the portfolio value. For example, when the confidence level used is. $99\%$ the $\mathrm{VaR}$ is the value in the left tail below which there is only. $1\%$ of the distribution. As. indicated in Figures 22.3a and 22.4, a positive gamma portfolio tends to have a less heavy left tail than the normal distribution. If the distribution of $\Delta P$ is normal, the calculated VaR tends to be too high. Similarly, as indicated in Figures 22.3b and 22.5, a negative gamma portfolio tends to have a heavier left tail than the normal distribution. If the distribution of $\Delta P$ is normal, the calculated VaR tends to be too low.  

![](images/297e7a22026ed74af815022c419f72460e8abd84318d0e89a524dffd0568de18.jpg)  
Figure 22.3  Probability distribution for value of portfolio: (a) positive gamma; (b) negative gamma.  

![](images/1ca6323bbc85a5a69ebd66cffacd69dd07f30290165b5c47cb8628182bc6694a.jpg)  
Figure 22.4 Translation of normal probability distribution for asset into probability distribution for value of a long call on asset..  

![](images/9fc3dc8a410e4112a5a9fbcd13c56bc745df53b4d71b4e11abdb78446fd78cfa.jpg)  
Figure 22.5 Translation of normal probability distribution for asset into probability distribution for value of a short call on asset.  

For a more accurate estimate of $\mathrm{VaR}$ than that given by the linear model, both delta. and gamma measures can be used to relate. $\Delta P$ to thee $\Delta x_{i}.$ Consider a portfolio dependent on a single asset whose price is. $S$ . Suppose $\delta$ and $\gamma$ are the delta and gamma. of the portfolio. From the appendix to Chapter 19, the equation  

$$
\begin{array}{r}{\Delta P=\delta\Delta S+\frac{1}{2}\gamma(\Delta S)^{2}}\end{array}
$$  

is an improvement over the approximation in equation (22.5).' Setting  

$$
\Delta x={\frac{\Delta S}{S}}
$$  

reduces this to  

$$
\begin{array}{r}{\Delta P=S\delta\Delta x+\frac{1}{2}S^{2}\gamma(\Delta x)^{2}}\end{array}
$$  

More generally for a portfolio with. $n$ underlying market variables, with each instrument. in the portfolio being dependent on only one of the market variables, equation (22.7) becomes  

$$
\Delta P=\sum_{i=1}^{n}S_{i}\delta_{i}\Delta x_{i}+\sum_{i=1}^{n}{\textstyle\frac{1}{2}}S_{i}^{2}\gamma_{i}(\Delta x_{i})^{2} 
$$  

where $S_{i}$ is the value of the ith market variable, and $\delta_{i}$ and $\gamma_{i}$ are the delta and gamma of the portfolio with respect to the ith market variable. When individual instruments in the portfolio may be dependent on more than one market variable, this equation takes the more general form  

$$
\Delta P=\sum_{i=1}^{n}S_{i}\delta_{i}\Delta x_{i}+\sum_{i=1}^{n}\sum_{j=1}^{n}\mathbb{\frac{1}{2}}S_{i}S_{j}\gamma_{i j}\Delta x_{i}\Delta x_{j}
$$  

where $\gamma_{i j}$ is a "cross gamma" defined as  

$$
\gamma_{i j}=\frac{\partial^{2}P}{\partial S_{i}\partial S_{j}}
$$  

Equation (22.8) is not as easy to work with as equation (22.2) because. $\Delta P$ is not normally distributed. If there are only a small number of variables, equation (22.8) can be used to calculate moments for $\Delta P$ A result in statistics known as the Cornish-Fisher expansion. can be used to estimate percentiles of the probability distribution from the moments.10.  
