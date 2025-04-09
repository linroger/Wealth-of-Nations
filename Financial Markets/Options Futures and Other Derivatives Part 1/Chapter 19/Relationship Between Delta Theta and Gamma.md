# 19.7 RELATIONSHIP BETWEEN DELTA, THETA, AND GAMMA  

The price of a single derivative dependent on a non-dividend-paying stock that follows a geometric Brownian motion process must satisfy the differential equation (15.16). It follows that the value of $\Pi$ of a portfolio of such derivatives also satisfies the differential equation  

$$
\frac{\partial\Pi}{\partial t}+r S\frac{\partial\Pi}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}\Pi}{\partial S^{2}}=r\Pi
$$  

Since  

$$
\Theta=\frac{\partial\Pi}{\partial t},\qquad\Delta=\frac{\partial\Pi}{\partial S},\qquad\Gamma=\frac{\partial^{2}\Pi}{\partial S^{2}}
$$  

it follows that  

$$
\Theta+r S\Delta+{\textstyle{\frac{1}{2}}}\sigma^{2}S^{2}\Gamma=r\Pi
$$  

Similar results can be produced for other underlying assets (see Problem 19.25).  

For a delta-neutral portfolio, $\Delta=0$ and  

$$
\Theta+{\textstyle\frac{1}{2}}\sigma^{2}S^{2}\Gamma=r\Pi
$$  

This shows that, when $\Theta$ is large and positive, gamma of a portfolio tends to be large and negative, and vice versa. This is consistent with the way in which Figure 19.8 has been drawn and explains why theta can to some extent be regarded as a proxy for gamma in a delta-neutral portfolio.  
