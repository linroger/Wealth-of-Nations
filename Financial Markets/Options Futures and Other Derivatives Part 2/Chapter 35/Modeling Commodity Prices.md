---
tags:
  - '#american_put_option'
  - '#commodity_prices'
  - '#futures_prices'
  - '#mean_reversion'
  - '#price_jumps'
  - '#risk_neutral_world'
  - '#seasonality'
  - '#stochastic_volatility'
  - '#trinomial_tree'
---
# 35.4  MODELING COMMODITY PRICES  

To value derivatives, we are often interested in modeling the spot price of a commodity in the traditional risk-neutral world. From Section 18.6, the expected future price of the commodity in this world is the futures price.  

# A Simple Process  

A simple process for a commodity price can be constructed by assuming that the expected. growth rate in the commodity price is dependent solely on time and the volatility of the. commodity price is constant. The risk-neutral process for the commodity price $S$ then has the form  

$$
\frac{d S}{S}=\mu(t)d t+\sigma d z
$$  

and  

$$
F(t)=\hat{E}[S(t)]=S(0)e^{\int_{0}^{t}\mu(\tau)d\tau}
$$  

where $F(t)$ is the futures price for a contract with maturity. $t$ and $\hat{E}$ denotes expected value in a risk-neutral world. It follows that  

$$
\ln{\cal F}(t)=\ln{S(0)}+\int_{0}^{t}\mu(\tau)d\tau
$$  

Differentiating both sides with respect to time gives  

$$
\mu(t)=\frac{\partial}{\partial t}[\ln{F(t)}]
$$  

# Example 35.1  

Suppose that the futures prices of live cattle at the end of July 2021 are (in cents per pound) as follows:  

<html><body><table><tr><td>August 2021</td><td>62.20</td></tr><tr><td>October2021</td><td>60.60</td></tr><tr><td>December2021</td><td>62.70</td></tr><tr><td>February2022</td><td>63.37</td></tr><tr><td>April2022</td><td>64.42</td></tr><tr><td>June2022</td><td>64.40</td></tr></table></body></html>  

These can be used to estimate the expected growth rate in live cattle prices in a risk-neutral world. For example, when the model in equation (35.1) is used, the  

expected growth rate in live cattle prices between October and December 2021, in a risk-neutral world is  

$$
\ln\biggl({\frac{62.70}{60.60}}\biggr)=0.034
$$  

Or $3.4\%$ per 2 months with continuous compounding. On an annualized basis, this is $20.4\%$ per annum.  

# Example 35.2  

Suppose that the futures prices of live cattle are as in Example 35.1. A certain breeding decision would involve an investment of $\$100,000$ now and expenditures of $\$20,000$ in 3 months, 6 months, and 9 months. The result is expected to be that an extra cattle will be available for sale at the end of the year. There are two major uncertainties: the number of pounds of extra cattle that will be available for sale and the price per pound. The expected number of pounds is 300,000. The expected price of cattle in 1 year in a risk-neutral world is, from Example 35.1, 64.40 cents per pound. Assuming that the risk-free rate of interest is $10\%$ per annum, the value of the investment (in thousands of dollars) is  

$$
-100-20e^{-0.1\times0.25}-20e^{-0.1\times0.50}-20e^{-0.1\times0.75}+300\times0.644e^{-0.1\times1}=17.729
$$  

This assumes that any uncertainty about the extra amount of cattle that will be available for sale has zero systematic risk and that there is no correlation between the amount of cattle that will be available for sale and the price.  

# Mean Reversion  

As already discussed, most commodity prices follow mean-reverting processes. They tend to get pulled back to a central value. A more realistic process than equation (35.1) for the risk-neutral process followed by the commodity price $S$ is  

$$
d\ln S=[\theta(t)-a\ln S]d t+\sigma d z
$$  

This incorporates mean reversion and is analogous to the lognormal process assumed for the short-term interest rate in Chapter 32. Note that this process is sometimes written  

$$
\frac{d S}{S}=[\theta^{*}(t)-a\ln S]d t+\sigma d z
$$  

From Ito's lemma, this is equivalent to the process in equation (35.2) when ${\boldsymbol{\theta}}^{*}(t)=$ $\theta(t)+{\textstyle\frac{1}{2}}\sigma^{2}$  

The trinomial tree methodology in Section 32.5 can be adapted to construct a tree. for $S$ and determine the value of $\theta(t)$ in equation (35.2) such that ${\bf\dot{\boldsymbol{F}}}(t)={\hat{E}}[S(t)]$ . We will illustrate the procedure by building a three-step tree for the situation where the current spot price is $\$20$ and the 1-year, 2-year, and 3-year futures prices are. $\$23,456$ , and $\$24$ respectively. Suppose that $a=0.1$ and $\sigma=0.2$ in equation (35.2). We first define a variable $X$ that is initially zero and follows the process  

$$
d X=-a X d t+\sigma d z
$$  

Using the procedure in Section 32.5, a trinomial tree can be constructed for $X$ .This is shown in Figure 35.1.  

Figure 35.1Tree for $X.$ Constructing this tree is the first stage in constructing a tree for the spot price of a commodity, S. Here $p_{u},p_{m}$ and $p_{d}$ are the probabilities of "up", "middle", and "down" movements from a node.  

![](images/b4fd1316c25ade3b6a42b2488adac10ba3c160026683841618161bcf025f8f30.jpg)  

The variable ln $S$ follows the same process as $X$ except for a time-dependent drift. Analogously to Section 32.5, the tree for $X$ can be converted to a tree for ln $S$ by displacing the positions of nodes. This tree is shown in Figure 35.2. The initial node corresponds to a price of 20, so the displacement for that node is ln 20. Suppose that the displacement of the nodes at 1 year is $\alpha_{1}$ . The values of the. $X$ at the three nodes at the 1-year point are. $+0.3464,0$ , and $-0.3464$ . The corresponding values of $\ln S$ are $0.3464+\alpha_{1}$ $\alpha_{1}$ and $-0.3464+\alpha_{1}$ . The values of $S$ are therefore $e^{0.3464+\alpha_{1}}$ $e^{\alpha_{1}}$ , and $e^{-0.3464+\alpha_{1}}$ respectively. We require the expected value of $S$ to equal the futures price. This means that.  

$$
0.1667e^{0.3464+\alpha_{1}}+0.6666e^{\alpha_{1}}+0.1667e^{-0.3464+\alpha_{1}}=22
$$  

The solution to this is. $\alpha_{1}=3.071$ . The values of. $S$ at the 1-year point are therefore 30.49, 21.56, and 15.25.  

At the 2-year point, we first calculate the probabilities of nodes E, F, G, H, and I being. reached from the probabilities of nodes B, C, and D being reached. The probability of reaching node F is the probability of reaching node B times the probability of moving. from B to F plus the probability of reaching node C times the probability of moving from C to F. This is  

$$
0.1667\times0.6566+0.6666\times0.1667=0.2206
$$  

Similarly the probabilities of reaching nodes E, G, H, and I are 0.0203, 0.5183, 0.2206, and 0.0203, respectively. The amount. $\alpha_{2}$ by which the nodes at time 2 years are.  

displaced must satisfy  

$$
\begin{array}{r}{1,0203e^{0.6928+\alpha_{2}}+0.2206e^{0.3464+\alpha_{2}}+0.5183e^{\alpha_{2}}\qquad}\ {+0.2206e^{-0.3464+\alpha_{2}}+0.0203e^{-0.6928+\alpha_{2}}=23.}\end{array}
$$  

The solution to this is. $\alpha_{2}=3.099$ . This means that the values of. $S$ at the 2-year point are 44.35, 31.37, 22.18, 15.69, and 11.10, respectively.  

A similar calculation can be carried out at time 3 years. Figure 35.2 shows the resulting tree for $S$  

# Example 35.3  

Suppose that the tree in Figure 35.2 is used to price a 3-year American put option on the spot price of the commodity with a strike price of 20 when the interest rate (continuously compounded) is $3\%$ per year. Rolling back through the tree in the usual way, we obtain Figure 35.3 showing that the value of the option is $\$1.48$ The option is exercised early at nodes D, H, and I. To obtain a more accurate value, a tree with many more time steps would be used. The futures prices would be interpolated to obtain futures prices for maturities corresponding to the end of every time step on this more detailed tree.  

# Interpolation and Seasonality  

When a large number of time steps are used, it is necessary to interpolate between futures prices to obtain a futures price at the end of each time step. When there is seasonality, the interpolation procedure should reflect this. Suppose there are monthly time steps. One simple way of incorporating seasonality is to collect monthly historical data on the spot price and calculate the 12-month moving average of the price.. A percentage seasonal factor can then be estimated as the average of the ratio of the spot price for the month to the 12-month moving average of spot prices that is centered. (approximately) on the month..  

Figure 35.2 Tree for spot price of a commodity:. $p_{u},p_{m}$ and $p_{d}$ are the probabilities of "up", "middle", and "down" movements from a node.  

![](images/1d0334d9442745e36930e05f66db75ecd69fad3eef0a3eedf70397097604e29b.jpg)  

![](images/5e16420dad9bcbb3afaa97e59dcb7951b0d4ff34c368621708765c6640c1cfea.jpg)  
Figure 35.3 Valuation of an American put option with a strike price of $\$20$ using the tree in Figure 35.2.  

The percentage seasonal factors are then used to deseasonalize the futures prices that are known. Monthly deseasonalized futures are then calculated using interpolation. These futures prices are then seasonalized using the percentage seasonal factors and the tree is built. Suppose, for example, that the futures prices are observed in the market for September and December as 40 and 44, respectively, and we want to calculate a futures prices for October and November. Suppose further that the percentage seasonality factors for September, October, November, and December are calculated from historical data as 0.95, 0.85, 0.8 and 1.1, respectively. The deseasonalized futures prices are $40/0.95=42.1$ for September and $44/1.1=40\$ for December. The interpolated deseasonalized futures prices are 41.4 and 40.7 for October and November, respectively. The seasonalized futures prices that would be used in tree construction for October and November are $41.4\times0.85=35.2$ and $40.7\times0.8=32.6$ respectively.  

As has been mentioned, the volatility of a commodity sometimes shows seasonality. For example, the prices of some agricultural commodities are more volatile during the. growing season because of weather uncertainty. Volatility can be monitored using the methods discussed in Chapter 23, and a percentage seasonal factor for volatility can be estimated. The parameter $\sigma$ can then be replaced by $\sigma(t)$ in equations (35.2) and (35.3). A procedure that can be used to construct a trinomial tree for the situation where the volatility is a function of time is discussed in Technical Notes 9 and 16 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes.  

# Jumps  

Some commodities, such as electricity and natural gas, exhibit price jumps because of weather-related demand shocks. Other commodities, particularly those that are agricultural, are liable to exhibit price jumps because of weather-related supply shocks. Jumps can be incorporated into equation (35.2) so that the process for the spot price becomes  

$$
d\ln S=[\theta(t)-a\ln S]d t+\sigma d z+d p
$$  

where $d p$ is the Poisson process generating the percentage jumps. This is similar to. Merton's mixed jump-diffusion model for stock prices, which is described in Section 27.1. Once the jump frequency and jump size probability distribution have been. chosen, the average increase in the commodity price at a future time. $t$ that is as a result of jumps can be calculated. To determine. $\theta(t)$ , the trinomial tree method can be used. with the futures prices for maturity. $t$ reduced by this increase. Monte Carlo simulation can be used to implement the model, as explained in Sections 21.6 and 27.1..  

# Other Models  

More-sophisticated models are sometimes used for oil prices. If $y$ is the convenience yield, then the proportional drift of the spot price is $r-y$ , where $r$ is the short-term risk-free rate and a natural process to assume for the spot price is  

$$
\frac{d S}{S}=(r-y)d t+\sigma_{1}d z_{1}
$$  

Gibson and Schwartz suggest that the convenience yield $y$ be modeled as a meanreverting process:2  

$$
~d y=k(\alpha-y)d t+\sigma_{2}d z_{2}
$$  

where $k$ and $\alpha$ are constants and $d z_{2}$ is a Wiener process, which is correlated with the Wiener process $d z_{1}$ . To provide an exact fit to futures prices,. $\alpha$ can be made a function of time.  

Eydeland and Geman propose a stochastic volatility for gas and electricity prices.3 This is  

$$
\begin{array}{l}{\displaystyle\frac{d S}{S}=a(b-\ln S)d t+\sqrt{V}d z_{1}}\ {\displaystyle d V=c(d-V)d t+e\sqrt{V}d z_{2}}\end{array}
$$  

where $a,b,c,d$ , and $e$ are constants, and $d z_{1}$ and $d z_{2}$ are correlated Wiener processes. Later Geman proposed a model for oil where the reversion level $^b$ is also stochastic.4  
