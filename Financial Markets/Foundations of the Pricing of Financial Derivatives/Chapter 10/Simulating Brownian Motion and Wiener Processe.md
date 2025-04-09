# 10.5 SIMULATING BROWNIAN MOTION AND WIENER PROCESSES

To get a better understanding of the Brownian motion and Wiener processes, let us run some simulations in Excel. Recall that the Brownian motion process is Equation (10.11), and the Wiener process is Equation (10.2). Of course, in the model, time is continuous, so the time increments are close to zero. They are not, however, precisely equal to zero. Let us start by making them very short, say one hour. In a year, there are 365 days and 24 hours per day. Thus, each time increment is set at $1/\big(24^{*}365\big)=0.000114$ . Let us assume a stock with an expected return of 0.12, a volatility of 0.50, and a starting stock price of 50.

The random component of the process is the Wiener process. The. $\varepsilon_{t}.$ which is a standard normal, is converted into the Wiener process. First, we need to simulate a standard normal. One reasonable way to do so is to use Excel's =rand() function. This function produces a uniformly distributed random number between zero and one.. A uniform distribution is a distribution of continuous random variables between two endpoints $^{a}$ and $b$ in which each outcome is equally likely. If $a=0$ and $b=1$ , the distribution is called unit uniform, because the range of outcomes will be between 0 and 1. It is known that the expected value of the uniform distribution is. $\left(1/2\right)\left(a+b\right),$ which is $1/2=(0+1)=0.5$ for the unit uniform. The variance is $\left(1/12\right)\left(b-a\right)^{2}$ . For the unit uniform, the variance is $(1/12)(1-0)^{2}=1/12$ . So, if we generate 12 unit uniform random variables and add them up, we obtain. $u_{1}+u_{2}+\ldots+u_{12}$ .Taking the expectation, we obtain $E\left(u_{1}\right)+E\left(u_{2}\right)+\ldots+E\left(u_{12}\right)=0.5\overline{{+}}0.5+\ldots\overline{{+}}0.5=6.$ We can then subtract 6, leaving an expected value of zero with no effect on the variance, which is easily obtained. These random drawings are independent so there is no covariance between them, and we can, therefore, simply add their variances to obtain the variance of the sum of the 12 unit uniform random variables. Thus, we have var $\left(u_{1}\right)+\operatorname{var}\left(u_{2}\right)+\ldots+\operatorname{var}\left(u_{12}\right)=1/12+1/12+\ldots+1/12=1$ Thus, the sum of the 12 unit uniform random numbers minus 6 has expected value of zero and variance of 1, just like a standard normal. Recall that the central limit theorem tells us that the sum of a series of independent random variables from any distribution is normally distributed in the limit. We have used only 12 so the limiting condition is not likely to occur just yet, but we should be reasonably close to a normal distribution.7

Thus, the sum of 12 unit uniform random variables minus 6.0 will serve as our randomly generated value of $\varepsilon_{t}$ . The rest is simple. We use Equation (10.2) to generate the. Wiener process value and insert that value into Equation (10.11) to obtain the stock return. We then apply the return to the current stock price and obtain the next stock price..

Recall that the time increment is one hour. To avoid some complications, let us assume that prices are generated every hour, every day, for a full year so there is no market closing and no holidays. This assumption would mean $24^{*}365=8.760$ prices in a year. Let us cut. it down to a month, which would be. $8{,}760/12=730$ prices. Then $d t=1/8,760$ , and we simulate 730 sequential prices or one month.

Table 10.1 shows the first five prices generated from the simulation.

Each row represents one hour. The column labeled $\varepsilon_{t}$ is the sum of 12 unit uniform random variables minus 6.0. The column labeled $d\mathbb{W}_{t}$ is a transformation of the unit uniform to the Wiener process, Equation (10.2). The column labeled $R_{t}$ is from Equation (10.11). In the first row, time 0, we simply set the starting price as 50. The first increment occurs at increment 1 where the Brownian motion value is -0.314189. The remainder of the information for time increment 1 is found as follows. First find the Wiener process value,.

TABLE 10.1 Simulation of Geometric Brownian Motion


<html><body><table><tr><td>Time</td><td>Et</td><td>dw.</td><td>Rt</td><td>'S</td><td>dw2 t</td></tr><tr><td>0</td><td></td><td></td><td></td><td>50.00</td><td></td></tr><tr><td>1</td><td>-0.314189</td><td>-0.003357</td><td>-0.001665</td><td>49.92</td><td>0.000011</td></tr><tr><td>2</td><td>1.712835</td><td>0.018301</td><td>0.009164</td><td>50.37</td><td>0.000335</td></tr><tr><td>3</td><td>0.058170</td><td>0.000622</td><td>0.000324</td><td>50.39</td><td>0.000000</td></tr><tr><td>4</td><td>-0.697400</td><td>-0.007451</td><td>-0.003712</td><td>50.20</td><td>0.000056</td></tr><tr><td>5</td><td>-1.340360</td><td>-0.014321</td><td>-0.007147</td><td>49.84</td><td>0.000205</td></tr></table></body></html>

$$
d W_{t}=\varepsilon_{t}\sqrt{d t}=-0.314189\sqrt{1/8,760}=-0.003357.
$$

Then convert this value to the stock return:

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d W_{t}=0.12(1/8,760)+0.5(0.003357)=-0.001665.
$$

Then the next stock price is

$$
\$50(1-0.001665)=\$49.92.
$$

We should also compute $d\mathbf{W}_{t}^{2}$ , because we shall show later that this value is essentially constant:

$$
d\mathrm{W}_{t}^{2}=(-0.003357)^{2}=0.000011.
$$

Figure 10.3 shows the simulation of the normal random variable, $\varepsilon_{t,}$ with each dot representing one of the randomly drawn values. Recall that we created this variable by adding 12 unit uniform random variables and subtracting 6.0. The average value is 0.010416 and the standard deviation is 0.968623. These are close to but not exactly equal to their desired values, but that result would only hold with a lot more values.

Figure 10.4 shows the simulated values of $d\mathbb{W}_{t}$ and $\boldsymbol{d}\boldsymbol{\mathrm{W}}_{t}^{2}$ . The volatile and dots is $d\mathbb{W}_{t}$ , and the nearly straight line is $\boldsymbol{d}\boldsymbol{\mathrm{W}}_{t}^{2}$ . We noted that $d\mathbf{W}_{t}^{2}$ should be constant, but that result occurs only in the limit, meaning with an extremely short time interval. Our time interval of one hour seems short, but as you probably know, there are many stock prices that generate within an hour under normal trading. If we increasingly shorten the time interval, then the process would become more stable. See Appendix 10A for details.

Figure 10.5 is the stock price simulated from the given results. It should be noted that the average return does not need to be anywhere near the expected return. Indeed, it is not, as the average return is 0.000069 per hour, which annualizes to almost $60\%$ . The volatility, however, is likely to be close to the annual specified volatility of 0.50. Here it is 0.484312.

We turn now to summarize key characteristics and important properties of the Wiener process. These properties will prove useful in later chapters.

![](e0ae371b3a14016f859acc813afb1caacf87df3c7a8ed5d15525f4a49e042e7e.jpg)
FIGURE 10.3  Simulation of Normal Distribution from Unit Uniform Distribution

![](fb4694d6ad3dada15ae41f4a882a46c6283f88b9d236da60e35b5d0e2c6e43fa.jpg)
FIGURE 10.4Simulation of $d\mathbb{W}_{t}$ and $d\mathbb{W}_{t}^{2}$

![](9102e9523c35781eaae98dda174ef7c16b5768a94897c2dbf102abf2315a8f4e.jpg)
