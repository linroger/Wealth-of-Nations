---
tags:
  - '#black_scholes_merton'
  - '#cev_model'
  - '#european_options'
  - '#jump_diffusion'
  - '#levy_processes'
  - '#merton_jump_diffusion_model'
  - '#monte_carlo_simulation'
  - '#option_pricing_models'
  - '#variance_gamma_model'
  - '#volatility_smile'
---
# 27.1 ALTERNATIVES TO BLACK-SCHOLES-MERTON  

The Black-Scholes-Merton model assumes that an asset's price changes continously in a way that produces a lognormal distribution for the price at any future time. There are. many alternative processes that can be assumed. One possibility is to retain the property. that the asset price changes continuously, but assume a process other than geometric Brownian motion. Another alternative is to overlay continuous asset price changes with jumps. Yet another alternative is to assume a process where all the asset price changes that take place are jumps. We will consider examples of all three types of processes in this section. In particular, we will consider the constant elasticity of variance model, Merton's mixed jump-diffusion model, and the variance-gamma model. All three models are implemented in DerivaGem. The types of processes we consider in this section are known collectively as Levy processes.1.  

# The Constant Elasticity of Variance Model  

One alternative to Black-Scholes-Merton is the constant elasticity of variance (CEV) model. This is a diffusion model where the risk-neutral process for a stock price. $S$ is  

$$
d S=(r-q)S d t+\sigma S^{\beta}d z
$$  

where $r$ is the risk-free rate, $q$ is the dividend yield,. $d z$ is a Wiener process, $\sigma$ is a volatility parameter, and $\beta$ is a positive constant.? The parameter. $\sigma$ is roughly equivalent to the volatility in the usual lognormal model multiplied by $S^{1-\beta}$  

When $\beta=1$ , the CEV model is the geometric Brownian motion model we have been. using up to now. When. $\beta<1$ , the volatility increases as the stock price decreases. This creates a probability distribution similar to that observed for equities with a heavy left tail and less heavy right tail (see Figure 20.4).3 When. $\beta>1$ , the volatility increases as the stock price increases. This creates a probability distribution with a heavy right tail. and a less heavy left tail. This corresponds to a volatility smile where the implied volatility is an increasing function of the strike price. This type of volatility smile is. sometimes observed for options on futures..  

The valuation formulas for European call and put options under the CEV model are  

when $0<\beta<1$ , and  

$$
\begin{array}{r}{c=S_{0}e^{-q T}[1-\chi^{2}(a,b+2,c)]-K e^{-r T}\chi^{2}(c,b,a)}\ {p=K e^{-r T}[1-\chi^{2}(c,b,a)]-S_{0}e^{-q T}\chi^{2}(a,b+2,c)}\end{array}
$$  

$$
\begin{array}{r}{c=S_{0}e^{-q T}[1-\chi^{2}(c,-b,a)]-K e^{-r T}\chi^{2}(a,2-b,c)}\ {p=K e^{-r T}[1-\chi^{2}(a,2-b,c)]-S_{0}e^{-q T}\chi^{2}(c,-b,a)}\end{array}
$$  

when $\beta>1$ , with  

$$
a=\frac{[K e^{-(r-q)T}]^{2(1-\beta)}}{(1-\beta)^{2}\nu},b=\frac{1}{1-\beta},c=\frac{S^{2(1-\beta)}}{(1-\beta)^{2}\nu}
$$  

where  

$$
\nu=\frac{\sigma^{2}}{2(r-q)(\beta-1)}[e^{2(r-q)(\beta-1)T}-1]
$$  

and $\chi^{2}(z,k,\nu)$ is the cumulative probability that a variable with a noncentral $\chi^{2}$ distribution with noncentrality parameter $\nu$ and $k$ degrees of freedom is less than $z$ A procedure for computing $\chi^{\bar{2}}(\bar{z},k,\nu)$ is provided in Technical Note 12 on the author's website: www-2.rotman.utoronto.ca/\~hull/TechnicalNotes.  

The CEV model is useful for valuing exotic equity options. The parameters of the. model can be chosen to fit the prices of plain vanilla options as closely as possible by. minimizing the sum of the squared differences between model prices and market prices.  

# Merton's Mixed Jump-Diffusion Model  

Merton has suggested a model where jumps are combined with continuous changes.4 Define:  

A: Average number of jumps per year. $k$ : Average jump size, measured as a percentage of the asset price  

The percentage jump size is assumed to be drawn from a probability distribution in the model.  

The probability of a jump in time $\Delta t$ is $\lambda\Delta t$ . The average growth rate in the asset price from the jumps is therefore $\lambda k$ . The risk-neutral process for the asset price is  

$$
\frac{d S}{S}=\left(r-q-\lambda k\right)d t+\sigma d z+d p
$$  

where $d z$ is a Wiener process, $d p$ is the Poisson process generating the jumps, and $\sigma$ is the volatility of the non-jump component of $S$ . The processes. $d z$ and $d p$ are assumed to be independent.  

An important particular case of Merton's model is where the logarithm of one plus the size of the percentage jump is normal. Assume that the standard deviation of the. normal distribution is $s$ Merton shows that a European option price can then be written.  

$$
\sum_{n=0}^{\infty}{\frac{e^{-\lambda^{\prime}T}(\lambda^{\prime}T)^{n}}{n!}}f_{n}
$$  

where $\lambda^{\prime}=\lambda(1+k)$ . The variable $f_{n}$ is the Black-Scholes-Merton option price when the dividend yield is $q$ , the variance rate is  

$$
\sigma^{2}+{\frac{n s^{2}}{T}}
$$  

and the risk-free rate is  

$$
r-\lambda k+\frac{n\gamma}{T}
$$  

where $\gamma=\ln(1+k)$  

This model gives rise to heavier left and heavier right tails than Black-ScholesMerton. It can be used for pricing currency options. As in the case of the CEV model, the model parameters are chosen by minimizing the sum of the squared differences between model prices and market prices.  

# Simulating Jumps  

Models that involve jumps can be implemented with Monte Carlo simulation. When jumps are generated by a Poisson process, the probability of exactly. $m$ jumps in time $t$ is  

$$
\frac{e^{-\lambda t}(\lambda t)^{m}}{m!}
$$  

where $\lambda$ is the average number of jumps per year. Equivalently, $\lambda t$ is the average number of jumps in time $t$  

Suppose that on average 0.5 jumps happen per year. The probability of $m$ jumps in 2 years is  

$$
\frac{e^{-0.5\times2}(0.5\times2)^{m}}{m!}
$$  

Table 27.1 gives the probability and cumulative probability of. $0,1,2,3,4,5,6,7$ , and 8 jumps in 2 years. (The numbers in a table such as this can be calculated using the POISSON function in Excel.)  

To simulate a process following jumps over 2 years, it is necessary to determine on each simulation trial:  

1. The number of jumps   
2. The size of each jump.  

To determine the number of jumps, on each simulation trial we sample a random. number between 0 and 1 and use Table 27.1 as a look-up table. If the random number. is between 0 and 0.3679, no jumps occur; if the random number is between 0.3679 and  

Table 27.1 Probabilities for number of jumps in 2 years.   


<html><body><table><tr><td>Numberof jumps,m</td><td>Probabilityof exactlymjumps</td><td>Probabilityof m jumps orless</td></tr><tr><td>0</td><td>0.3679</td><td>0.3679</td></tr><tr><td>1</td><td>0.3679</td><td>0.7358</td></tr><tr><td>2</td><td>0.1839</td><td>0.9197</td></tr><tr><td>3</td><td>0.0613</td><td>0.9810</td></tr><tr><td>4</td><td>0.0153</td><td>0.9963</td></tr><tr><td>5</td><td>0.0031</td><td>0.9994</td></tr><tr><td>6</td><td>0.0005</td><td>0.9999</td></tr><tr><td>7</td><td>0.0001</td><td>1.0000</td></tr><tr><td>8</td><td>0.0000</td><td>1.0000</td></tr></table></body></html>  

0.7358, one jump occurs; if the random number is between 0.7358 and 0.9197, two jumps occur; and so on. To determine the size of each jump, it is necessary on each simulation trial to sample from the probability distribution for the jump size once for each jump. that occurs. Once the number of jumps and the jump sizes have been determined, the. final value of the variable being simulated is known for the simulation trial..  

In a mixed jump-diffusion model, jumps are superimposed upon the usual lognormal diffusion process that is assumed for stock prices. The process then has two components (the usual diffusion component and the jump component) and each must be sampled separately. The diffusion component is sampled as described in Sections 21.6 and 21.7 while the jump component is sampled as just described. When derivatives are valued, it is important to ensure that the overall expected return from the asset (from both components) is the risk-free rate.  

# The Variance-Gamma Model  

An example of a pure jump model that is proving quite popular is the variance-gamma model. Define a variable $g$ as the change over time $T$ in a variable that follows a gamma process with mean rate of 1 and variance rate of. $\nu$ . A gamma process is a pure jump process where small jumps occur very frequently and large jumps occur only occasionally. The probability density for $g$ is  

$$
\frac{g^{T/\nu-1}e^{-g/\nu}}{\nu^{T/\nu}\Gamma(T/\nu)}
$$  

where $\Gamma(\cdot)$ denotes the gamma function. This probability density can be computed in. Excelusingthe GAMMADIST $(\cdot,\cdot,\cdot,\cdot)$ function. The first argument ofthe functionis $g$ , the second is $T/\nu$ , the third is $\nu$ , and the fourth is TRUE or FALSE, where TRUE. returns the cumulative probability distribution function and FALSE returns the probability density function we have just given..  

As usual, we define $S_{T}$ as the asset price at time $T,S_{0}$ as the asset price today, $r$ as the risk-free interest rate, and $q$ as the dividend yield. Conditional on. $g$ , ln $S_{T}$ has a riskneutral probability distribution under the variance-gamma model that is normal. The conditional mean is  

$$
\ln S_{0}+(r-q)T+\omega+\theta g
$$  

and the conditional standard deviation is  

$$
\sigma{\sqrt{g}}
$$  

where  

$$
\omega=(T/\nu)\ln(1-\theta\nu-\sigma^{2}\nu/2)
$$  

The variance-gamma model has three parameters: $\nu,\sigma$ , and $\theta$ 6 The parameter $\nu$ is the variance rate of the gamma process, $\sigma$ is the volatility, and $\theta$ is a parameter defining skewness. When $\theta=0$ , ln $S_{T}$ is symmetric; when. $\theta<0$ , it is negatively skewed (as for equities); and when. $\theta>0$ , it is positively skewed..  

Suppose that we are interested in using Excel to obtain 10,000 random samples of the change in an asset price between time 0 and time $T$ using the variance-gamma model. As a preliminary, we could set cells E1, E2, E3, E4, E5, E6, and E7 equal to. $T,\nu,\theta,\sigma,r$ $q$ , and $S_{0}$ , respectively. We could also set E8 equal to $\omega$ by defining it as  

$$
=\S\mathrm{E}\S1*\mathrm{LN}(1-\S\mathrm{E}\S3*\S\mathrm{E}\S2-\S\mathrm{E}\S4*\S\mathrm{E}\S4*\S\mathrm{E}\S2/2)/\S\mathrm{E}\S2
$$  

We could then proceed as follows:  

1. Sample values for $g$ using the GAMMAINV function. Set the contents of cells A1, A2,..., A10000 as $\mathbf{\Sigma}=\mathbf{G}\mathbf{A}\mathbf{M}\mathbf{M}\mathbf{A}\mathbf{I}\mathbf{N}\mathbf{V}(\mathbf{R}\mathbf{A}\mathbf{N}\mathbf{D}(\mathbf{\Sigma}),\S\mathbf{E}\S1/\S\mathbf{E}\S2,\mathbf{\Sigma}\S\mathbf{E}\S2)$  

2. For each value of $g$ we sample a value $z$ for a variable that is normally distributed with mean $\theta g$ and standard deviation $\sigma{\sqrt{g}}$ . This can be done by defining cell B1 as  

$$
=A1*{\mathrm{SE}}\P3+{\mathrm{SQRT}}({\mathrm{A}}1)*{\mathrm{\SE}}\S4*{\mathrm{NORMSINV}}({\mathrm{RAND}}())
$$  

and cells $\mathbf{B}2,\mathbf{B}3,\dotsc,\mathbf{B}10000$ similarly.  

3. The stock price $S_{T}$ is given by.  

$$
S_{T}=S_{0}\exp[(r-q)T+\omega+z]
$$  

By defining $\mathrm{C}1$ as  

$$
=\S\mathrm{E}\S7*\mathrm{E}\mathrm{XP}((\S\mathrm{E}\S5-\S\mathrm{E}\S6)*\S\mathrm{E}\S1+\mathrm{B}1+\S\mathrm{E}\S8)
$$  

and $\mathrm{C}2,\mathrm{C}3,...,\mathrm{C}10000$ similarly, random samples from the distribution of $S_{T}$ are created in these cells.  

![](images/e08ab552fe7aba101023b4c27a4152d4aa983cc3dd10aa0d354743cb7fb06bf2.jpg)  
Figure 27.1 Distributions obtained with variance-gamma process and geometric Brownian motion.  

Figure 27.1 shows the probability distribution that is obtained using the variancegamma model for $S_{T}$ when $S_{0}=100,T=0.5,\nu=0.5,\theta=0.1,\sigma=($ and $r=q=0$ For comparison it also shows the distribution given by geometric Brownian motion when the volatility, $\sigma$ is 0.2 (or $20\%$ ). Although not clear in Figure 27.1, the variance-gamma distribution has heavier tails than the lognormal distribution given by geometric Brownian motion.  

One way of characterizing the variance-gamma distribution is that $g$ defines the rate at which information arrives during time $T.$ If $g$ is large, a great deal of information arrives and the sample we take from a normal distribution in step 2 above has a relatively large mean and variance. If $g$ is small, relatively little information arrives and the sample we take has a relatively small mean and variance. The parameter $T$ is the usual time measure, and. $g$ is sometimes referred to as measuring economic time or time adjusted for the flow of information.  

Semi-analytic European option valuation formulas are provided by Madan et al. (1998). The variance-gamma model tends to produce a U-shaped volatility smile. The smile is not necessarily symmetrical. It is very pronounced for short maturities and "dies away" for long maturities. The model can be fitted to either equity or foreign currency plain vanilla option prices.  
