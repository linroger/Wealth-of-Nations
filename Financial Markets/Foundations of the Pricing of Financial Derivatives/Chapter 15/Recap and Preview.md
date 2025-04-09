# 15.7 RECAP AND PREVIEW

Girsanov's theorem shows that a martingale can often be represented by another martingale with a change in the location or drift of the process. This result is a pure mathematical concept, but it has great relevance to finance in that it shows that the stochastic process for an asset can be changed into another stochastic process with the expected return equal to the risk-free rate. This result, which we called the change of measure, plays a subtle but important role in derivatives pricing. In this chapter, we showed how this result is derived, and we applied it to the return on an asset on which we would be interested in valuing a derivative.

In Chapter 16, we illustrate how the discrete and continuous stochastic processes we have been working with are related. In doing so, we will show how the discrete change of measure relates to the continuous change of measure.

# QUESTIONS AND PROBLEMS

1 Assume a given stock price follows geometric Brownian motion with geometric drift. along with known constant mean and known constant standard deviation. Find the equivalent measure with a known risk-free rate and known constant standard deviation.

2 Assume an underlying instrument follows arithmetic Brownian motion with arithmetic drift with a known constant mean and known constant standard deviation. Find the equivalent measure with a known risk-free rate having geometric drift and known constant standard deviation.

3Suppose $x$ is distributed independent, multivariate normal with each variable's standard deviation of 1, $N(\mu_{i},1)$ . Then the PDF is

$$
f_{\mathbf{x}}^{\parallel,1}(x_{1},\ldots,x_{n}:\pmb{\upmu},\Sigma=\mathbf{I})=\frac{1}{\sqrt{(2\pi)^{n}}}e^{-\frac{1}{2}\sum_{i=1}^{n}(x_{i}-\upmu_{i})^{2}}.
$$

Suppose we want $x$ to be distributed independent, multivariate normal with each variable having mean O and standard deviation 1, $N(0,1)$ . Then the PDF is

$$
f_{\mathbf{x}}^{0,1}(x_{1},\ldots,x_{n}:\mathfrak{\pmb{\upmu}}=\mathbf{0},\Sigma=\mathbf{I})=\frac{1}{\sqrt{(2\pi)^{n}}}e^{-\frac{1}{2}\sum_{i=1}^{n}x_{i}^{2}}.
$$

Find the appropriate Radon-Nikodym derivative to make this transformation.

4  Based on Girsanov's theorem, is it possible to convert arithmetic Brownian motion with geometric drift to geometric Brownian motion with geometric drift? Evaluate whether the following statement related to the martingale representation. theorem is true: Given any two martingales, $x_{t}$ and $y_{t}$ , the relationship between them can simply be stated as

$$
y_{t}=y_{0}+\int_{0}^{t}\lambda_{j}d x_{j}.
$$

# NOTES

1. In addition, a martingale must be finite, and each realization must be independent of the previous One.

2. Of course, the exercise price also determines the option payoff, but it is not random, so it causes. us no problems.
3. Mathematicians call this property previsibility.
4. Recall that specifically, $d\mathbb{W}_{t}=\varepsilon_{t}\sqrt{d t}$ where $\varepsilon_{t}$ is a standard normal random variable.
5. The following specification is because $\mathbf{\boldsymbol{W}}_{t}$ has expected value of zero, as it starts off at. $\mathrm{W}_{0}=0$ and has a variance of $t$ The term in parentheses is the value of the random variable minus its. expected value divided by its variance.
6. As we shall ultimately see, $\gamma_{u}$ will be a very simple constraint that in any rational financial market the variation is finite.
7. The result on the third line is obtained from the result on the second line by differentiating the stochastic integral at the end point.
8. If this were not the case, we would see that our method would not work later on.
9. It is even more natural that instead of defining y as $-(\alpha-r_{c})/\sigma$ we define it as $(\alpha-r_{c})/\sigma$ anc then change the sign such that instead of adding y to $\alpha$ , we are subtracting it. In that way, we appear to be subtracting a risk premium, a more sensible way to describe what is happening.
10. In the study of general market equilibrium, such as the capital asset pricing model, the appropriate measure of risk is not the standard deviation, but the systematic risk, also known as $\beta$ The derivatives pricing framework, however, takes the general equilibrium as given and as fully reflected in the price of the underlying asset. Risk is measured in isolation and. $\sigma$ is the only measure of risk recognized within option pricing theory. You may also recognize that this return/risk ratio is the Sharpe ratio, which is widely used in investment performance evaluation.
11. Let us emphasize that this is not a new definition for $\gamma$ . It simply expresses $\gamma$ in terms of the log return.

# Connecting Discrete and Continuous Brownian Motions.

e have now almost fully developed the binomial and Black-Scholes-Merton models. In this chapter, however, we will circle back and tie their stochastic processes. together. Some of this material is repetitive, but it will be helpful in cleaning up some of. the loose ends.

To model an asset price, we must start with a framework that reflects the noise produced by random information generated in such a manner that its expectation and volatility are the same through time. As we have described, the model is typically called a Brownian motion, named for the Scottish scientist, Robert Brown, who supposedly. observed it about 1827 in pollen suspended in water. Much of the scientific work for this model was done by Einstein and Norbert Wiener, the latter for whom a form of Brownian motion, the Wiener process, was named. This process is also called a random walk, though technically a random walk is slightly different.1.
