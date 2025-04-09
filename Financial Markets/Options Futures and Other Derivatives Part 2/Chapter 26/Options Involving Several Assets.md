# 26.15 OPTIONS INVOLVING SEVERAL ASSETS  

Options involving two or more risky assets are sometimes referred to as rainbow options.   
One example is the bond futures contract traded on the CBOT described in Chapter 6.   
The party with the short position is allowed to choose between a large number of.   
different bonds when making delivery.  

Probably the most popular option involving several assets is a European basket option. This is an option where the payoff is dependent on the value of a portfolio (or basket) of assets. The assets are usually either individual stocks or stock indices or currencies. A European basket option can be valued with Monte Carlo simulation, by assuming that the assets follow correlated geometric Brownian motion processes. A much faster approach is to calculate the first two moments of the basket at the maturity of the option in a risk-neutral world, and then assume that value of the basket is lognormally distributed at that time. The option can then be valued using Black's model with the parameters shown in equations (26.3) and (26.4). In this case,  

$$
M_{1}=\sum_{i=1}^{n}F_{i}\quad{\mathrm{and}}\quad M_{2}=\sum_{i=1}^{n}\sum_{j=1}^{n}F_{i}F_{j}e^{\rho_{i j}\sigma_{i}\sigma_{j}T}
$$  

where $n$ is the number of assets, $T$ is the option maturity, $F_{i}$ and $\sigma_{i}$ are the forward price and volatility of the $i^{.}$ th asset, and. $\rho_{i j}$ is the correlation between the ith and jth asset.. See Technical Note 28 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes.  
