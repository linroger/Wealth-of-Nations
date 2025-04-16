---
tags:
  - '#arithmetic_brownian_motion'
  - '#asset_pricing_models'
  - '#black_scholes_merton_model'
  - '#brownian_motion'
  - '#financial_modeling'
  - '#geometric_brownian_motion'
  - '#ito_lemma'
  - '#stochastic_calculus'
  - '#wiener_process'
---
# 10.7 RECAP AND PREVIEW

In this chapter, we introduced the basic Brownian motion and Wiener process. We did this on a very intuitive level. We identified certain desirable characteristics and, one by one, we. added features that introduced those characteristics without affecting the characteristics we had already built into the model. We ultimately obtained the stochastic process that. is widely used to model assets. We showed several of its properties, and we generated a simulation so you could get a feel for what these numbers look like..

In Chapter 11, we introduce the two important concepts of Ito's lemma and. stochastic calculus, which will complete the knowledge base that we need to derive the Black-Scholes-Merton model.

# APPENDIX 10A

# Simulation of the Wiener Process and the Square of the Wiener Process for Successively Smaller Time Intervals

Suppose we run a second set of simulated values of the Wiener process for smaller and smaller time intervals. First, let us use a daily time interval $(d t=1/365)$ , then an hourly time interval $(d t=1/\left(24^{*}365\right))$ , then a minute time interval $(d t=1/\left(60^{*}24^{*}365\right))$ and then a second time interval $(d t=1/\left(60^{*}60^{*}24^{*}365\right);$ . We obtain the results in Table 10A.1 for $d\mathbb{W}_{t}$ and $d_{t}\mathbb{W}^{2}$ with values quoted to six decimal places.

Note that the average and volatility shrink for both measures when the interval is shortened. Note in particular, that the volatility of $d\mathbf{W}_{t}^{2}$ is virtually zero. Of course, in the limit, it is zero.

TABLE 10A.1 Values of $d\mathbb{W}_{t}$ and $d\mathbb{W}_{t}^{2}$ for Various dt.


<html><body><table><tr><td rowspan="2"></td><td colspan="4">dwt</td><td colspan="4">dW2</td></tr><tr><td>Daily</td><td>Hourly</td><td>Minute</td><td>Second</td><td>Daily</td><td>Hourly</td><td>Minute</td><td>Second</td></tr><tr><td>Average</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>StandardDeviation</td><td>0.053366</td><td>0.010893</td><td>0.001406</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# QUESTIONS AND PROBLEMS

1 The Wiener process is defined as $d\mathbb{W}_{t}=\varepsilon_{t}\sqrt{d t}$ Find the expected value and standard deviation of the Wiener process..
2 Geometric Brownian motion can be expressed as $d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t}$ . Explain the behavior of changes in $S_{t}$ for different values of $S_{t}$ In particular, explain why $S_{t}$ never obtains the value of zero.
3 As discussed in this chapter, an alternative framework for modeling certain financial instruments is arithmetic Brownian motion with geometric drift or $d S_{t}=\alpha S_{t}d t+$ $\sigma_{\mathbb{S}}d\boldsymbol{W}_{t}$ . Explain the behavior of changes in $S_{t}$ for different values of $S_{t}$ . In particular, explain why $S_{t}$ may obtain the value of zero or become negative.
4  The following two graphs were generated based on discretized versions of geometric Brownian motion $(d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t})$ and arithmetic Brownian motion. $\boldsymbol{(d S_{t}=}$ $\alpha S_{t}d t+\sigma_{\mathbb{S}}d\mathbb{W}_{t})$ . Identify the graphs and defend your answer..

![](092ce51f46925dbac23f0b67e2bf25066dac10f1b7f98d412c09dc992e6d57ce.jpg)

![](a2b3e03fca0d617dadb1778a57239291ca8f86e22d941d21cf3aa7a0ee833e00.jpg)

5  Identify four important characteristics that a model of asset prices should encompass.

6[Contributed by Brecklyn Groce] The following table gives five simulated values of a. standard normal random variable. Convert these values to the increments of a Wiener process and find the simulated value after five days of a stock initially priced at 80 with. an annual expected return of $10\%$ and a volatility of $48\%$ under the assumption that the time increment is one day, $1/365=0.00274.$ You may wish to create a spreadsheet to work the problem.

<html><body><table><tr><td>Day</td><td>Et</td><td>△Wt</td><td></td></tr><tr><td>0</td><td></td><td></td><td>$80.00</td></tr><tr><td>1</td><td>0.808889</td><td></td><td></td></tr><tr><td>2</td><td>0.480432</td><td></td><td></td></tr><tr><td>3</td><td>0.695581</td><td></td><td></td></tr><tr><td>4</td><td>-0.870413</td><td></td><td></td></tr><tr><td>5</td><td>0.407389</td><td></td><td></td></tr></table></body></html>

# NOTES

1. The terms Brownian motion, Wiener process, and Ito process are often used interchangeably. though there are technically some differences. Recall Robert Brown was a botanist, whereas

Wiener and Ito were mathematicians. Thus, mathematics-based authors lean toward Wiener or Ito processes, whereas physical and social scientists lean toward Brownian motion. In our context, we use standard Wiener process or just Wiener process to denote $\mathbb{W}_{t}$ alone, whereas Brownian motion denotes functions of $\mathbf{\boldsymbol{W}}_{t}$
2. Remember that $d\mathbb{W}_{t}=\varepsilon_{t}\sqrt{d t}$ Squaring the square root term gives $d t$ This term is then multiplied. by the variance of. $\varepsilon_{t},$ which is 1.0..
3. Other properties like skewness might be important but we ignore them for this model..
4. It is common but not required to express expected returns and variances on an annual basis. For. example, banks quote CD rates for a year, though the CD may have some other maturity. The Federal Reserve may have a target Fed Funds rate, which is stated on an annual basis, though most borrowings at that rate are overnight.
5. This type of process is also sometimes called a lognormal diffusion process. We explore this result in more detail in Chapter 12, Section 12.1.
6. Arithmetic (accent on third syllable) Brownian motion offers an alternative approach to several financial problems. We will cover these processes in detail starting in Chapter 12.
7. Another method is to use the Excel function $=$ normsinv(rand()), which directly gives a standard normal random variable.

# Stochastic Calculus and Ito's Lemma

lemma. Though this result was discovered about 1950, it did not get firmly established in the finance literature until 1973 when Black, Scholes, and Merton discovered that it could be used to model the price of a stock and ultimately to facilitate pricing an option. Some. excellent references with applications in finance are Baxter and Rennie (1996), Neftci (2000), and Malliaris and Brock (1982). Good sources for more advanced treatments are Karatzas and Shreve (1991) and Karlin and Taylor (1981)..
