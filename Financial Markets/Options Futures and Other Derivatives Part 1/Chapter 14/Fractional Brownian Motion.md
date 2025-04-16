---
tags:
  - '#black_scholes_merton_model'
  - '#fractional_brownian_motion'
  - '#geometric_brownian_motion'
  - '#hurst_exponent'
  - '#ito_lemma'
  - '#ito_process'
  - '#monte_carlo_simulation'
  - '#stochastic_process'
  - '#wiener_process'
---
# 14.8 FRACTIONAL BROWNIAN MOTION  

Fractional Brownian motion (also known as fractal Brownian motion) provides a generalization of Brownian motion and the models involving Wiener processes that we have discussed so far in this chapter. It is used in rough volatility models for valuing derivatives, which are discussed later in the book.  

First, let us quickly review the properties of Wiener processes. Suppose $d z$ is a Wiener process, $\sigma$ is a constant, and  

$$
X=\sigma d z
$$  

with $X(0)=0$ Then, for $t>s>0$  

$$
E[X(t)-X(s)]=0\quad\mathrm{and}\quad E[(X(t)-X(s))^{2}]=\sigma^{2}(t-s)
$$  

In particular, $E[(X(t))^{2}]=\sigma^{2}t$ and $E[(X(s))^{2}]=\sigma^{2}s.$ The variance of the change in $X$ between times $s$ and $t$ is  

$$
E[(X(t)-X(s))^{2}]-(E[X(t)-X(s)])^{2}=\sigma^{2}(t-s)
$$  

The variance per unit time is therefore constant and equal to $\sigma^{2}$ . Because a Wiener process is Markov, $X(t)\mathrm{~-~}X(s)$ is uncorrelated with $X(s)$ . Hence,  

$$
\begin{array}{r l}&{E[X(s)X(t)]=E[X(s)(X(s)+X(t)-X(s))]}\ &{\quad\quad=E[(X(s))^{2}]+E[X(s)(X(t)-X(s))]}\ &{\quad\quad=E[(X(s))^{2}]=\sigma^{2}s}\end{array}
$$  

In fractional Brownian motion we assume  

$$
E[(X(t)-X(s))^{2}]=\sigma^{2}(t-s)^{2H}
$$  

where $H$ is referred to as the Hurst exponent. Continuing with the assumption that  

$X(0)=0$ $E[(X(t)^{2}]=\sigma^{2}t^{2H},$ and $E[(X(s)^{2}]=\sigma^{2}s^{2H},$ When $H=0.5$ fractional Brownian motion becomes regular Brownian motion.  

Since  

$$
E[(X(t)-X(s))^{2}]=E[(X(t))^{2}]+E[(X(s))^{2}]-2E[X(t)X(s)]
$$  

it follows that  

$$
\begin{array}{c}{{E[X(t)X(s)]=0.5\{E[(X(t))^{2}]+E[(X(s))^{2}]-E[(X(t)-X(s))^{2}]\}}}\ {{{}}}\ {{=0.5\sigma^{2}[t^{2H}+s^{2H}-(t-s)^{2H}]}}\end{array}
$$  

When $H=0.5$ , this reduces to our earlier result for Wiener processes: $E[X(s)X(t)]=\sigma^{2}s$ The correlation between $X(t)$ and $X(s)$ is  

$$
\frac{0.5[t^{2H}+s^{2H}-(t-s)^{2H}]}{s^{H}t^{H}}
$$  

Fractional Brownian motion is non-Markov. If $t>s>u$ , then  

$$
\begin{array}{r l}&{E[(X(t)-X(s))(X(s)-X(u))]=E[X(t)X(s)]-E[(X(s))^{2}]}\ &{\qquad-E[X(t)X(u)]+E[X(s)X(u)]=0.5\sigma^{2}[(t-u)^{2H}-(t-s)^{2H}-(s-u)^{2H}]}\end{array}
$$  

This is zero (as we expect) when $H=0.5$ .When $H>0.5$ , it is positive (so that the. correlation between changes in $X$ in successive periods of time is positive). When $H<0.5$ it is negative (so that the correlation between changes in $X$ in successive periods of time is negative)..  

Simulating fractional Brownian motion involves dividing the time period being considered into a number of small time steps of length $\Delta t.$ A sample from a standard normal distribution, $\epsilon$ , determines the change over one time step using equation (14.8). In regular Brownian motion the $\epsilon$ 's used for different time steps are uncorrelated. In fractional Brownian motion we must build in the correlations so that equation (14.20) is satisfied. The. $\epsilon$ for the first step is chosen randomly; the $\epsilon$ for the second step must be. chosen so thate $X(2\Delta t)$ has the right correlation with. $X(\Delta t)$ ; the $\epsilon$ for the third time step must be chosen so that. $X(3\Delta t)$ has the right correlation with both $x(2\Delta t)$ and the. $X(\Delta t)$ ; and so on. The Cholesky decomposition procedure explained in Chapter 21, can be used to accomplish this..  

Figure 14.3 shows the simulation of fractional Brownian motion over one year for values of $H$ equal to 0.9, 0.5, and 0.1 when the time step is 0.01 years. As. $H$ decreases, the process becomes more noisy. This would become even more marked if we decreased the length of the time step further..  

# SUMMARY  

Stochastic processes describe the probabilistic evolution of the value of a variable. through time. A Markov process is one where only the present value of the variable. is relevant for predicting the future. The past history of the variable and the way in which the present has emerged from the past is irrelevant..  

![](images/61dee99f4e0f38956793c73111665f4d9d5d94b64ec8ad111eb2e8bc14c2911f.jpg)  
Figure 14.3 Simulation of fractional Brownian motion for different values of the Hurst exponent.  

A Wiener process. $d z$ is a Markov process describing the evolution of a normally. distributed variable. The drift of the process is zero and the variance rate is 1.0 per unit time. This means that, if the value of the variable is. $x_{0}$ at time 0, then at time $T$ it is normally distributed with mean $x_{0}$ and standard deviation $\sqrt{T}$  

A generalized Wiener process describes the evolution of a normally distributed variable with a drift of. $a$ per unit time and a variance rate of. $b^{2}$ per unit time, where $a$ and $^b$ are constants. This means that if, as before, the value of the variable is. $x_{0}$ at time 0, it is normally distributed with a mean of. $x_{0}+a T$ and a standard deviation of. $b\sqrt{T}$ at time $T$  

An Ito process is a process where the drift and variance rate of $x$ can be a function of both $x$ itself and time. The change in. $x$ in a very short period of time is, to a good. approximation, normally distributed, but its change over longer periods of time is liable to be nonnormal.  

One way of gaining an intuitive understanding of a stochastic process for a variable is to use Monte Carlo simulation. This involves dividing a time interval into many small time steps and randomly sampling possible paths for the variable. The future probability distribution for the variable can then be calculated. Monte Carlo simulation is discussed further in Chapter 21.  

Ito's lemma is a way of calculating the stochastic process followed by a function of a variable from the stochastic process followed by the variable itself. As we shall see in Chapter 15, Ito's lemma plays a very important part in the pricing of derivatives. A key point is that the Wiener process $d z$ underlying the stochastic process for the variable is exactly the same as the Wiener process underlying the stochastic process for the function of the variable. Both are subject to the same underlying source of uncertainty.  

The stochastic process usually assumed for a stock price is geometric Brownian motion. Under this process the return to the holder of the stock in a small period of time is normally distributed and the returns in two nonoverlapping periods are independent. The value of the stock price at a future time has a lognormal distribution. The Black-Scholes-Merton model, which we cover in the next chapter, is based on the geometric Brownian motion assumption.  

# FURTHER READING  

On Efficient Markets and the Markov Property of Stock Prices  

Brealey, R. A. An Introduction to Risk and Return from Common Stock, 2nd edn. Cambridge, MA: MIT Press, 1986.   
Cootner, P. H. (ed.) The Random Character of Stock Market Prices. Cambridge, MA: MIT Press, 1964.   
On Stochastic Processes   
Cox, D. R., and H. D. Miller. The Theory of Stochastic Processes. London: Chapman & Hall, 1977.   
Feller, W. Introduction to Probability Theory and Its Applications. New York: Wiley, 1968.   
Karlin, S., and H. M. Taylor. A First Course in Stochastic Processes, 2nd edn. New York: Academic Press, 1975.   
Mandelbrot, B. "Fractional Brownian Motions, Fractional Noises, and Applications,' SIAM Review, 10, 4 (1968): 422-437.   
Shreve, S. E. Stochastic Calculus for Finance II: Continuous-Time Models. New York: Springer, 2008.  

# Short Concept Questions  

14.1. What is a Markov model?  

14.2. What are the properties of a Wiener process?  

14.3. What is the difference between a generalized Wiener process and a Wiener process?  

14.4. How can a Wiener process be simulated?  

14.5. What are the properties of geometric Brownian motion?  

14.6.  What problem does Ito's lemma solve?  

14.7. If a stock price follows geometric Brownian motion, what is the process followed by the logarithm of the stock price?  

14.8. Suppose that $X_{1}$ is the change in the value of a variable during one time period and $X_{2}$ is the change in its value during the next time period. What is the correlation between $X_{1}$ and $X_{2}$ when the variable follows fractional Brownian motion with (a) $H>0.5$ (b) $H=0.5$ , and (c) $H<0.5$ , where $H$ is the Hurst exponent?  

14.9. What would it mean to assert that the temperature at a certain place follows a Markov process? Do you think that temperatures do, in fact, follow a Markov process?.  

14.10. Explain the role of the Hurst exponent in fractional Brownian motion.  

# Practice Questions  

14.11. Can a trading rule based on the past history of a stock's price ever produce returns that are consistently above average? Discuss.   
14.12. A company's cash position, measured in millions of dollars, follows a generalized Wiener process with a drift rate of 0.5 per quarter and a variance rate of 4.0 per quarter. How high does the company's initial cash position have to be for the company to have a. less than $5\%$ chance of a negative cash position by the end of 1 year?.   
14.13. Variables $X_{1}$ and $X_{2}$ follow generalized Wiener processes, with drift rates $\mu_{1}$ and $\mu_{2}$ and variances $\sigma_{1}^{2}$ and $\sigma_{2}^{2}$ . What process does $X_{1}+X_{2}$ follow if: (a) The changes in. $X_{1}$ and $X_{2}$ in any short interval of time are uncorrelated? (b) There is a correlation. $\rho$ between the changes in. $X_{1}$ and $X_{2}$ in any short time interval?.  

14.14. Consider a variable $S$ that follows the process.  

$$
d S=\mu d t+\sigma d z
$$  

For the first three years, $\mu=2$ and $\sigma=3$ ; for the next three years, $\mu=3$ and $\sigma=4$ If the initial value of the variable is 5, what is the probability distribution of the value of the variable at the end of year 6?  

14.15. Suppose that $G$ is a function of a stock price $S$ and time. Suppose that $\sigma_{S}$ and $\sigma_{G}$ are the volatilities of $S$ and $G$ . Show that, when the expected return of $S$ increases by $\lambda\sigma_{S}$ , the growth rate of. $G$ increases by. $\lambda\sigma_{G}$ , where $\lambda$ is a constant.  

14.16. Stock A and stock B both follow geometric Brownian motion. Changes in any short interval of time are uncorrelated with each other. Does the value of a portfolio consisting. of one of stock A and one of stock B follow geometric Brownian motion? Explain your. answer.  

14.17. The process for the stock price in equation (14.8) is  

$$
\Delta S=\mu S\Delta t+\sigma S\epsilon\sqrt{\Delta t}
$$  

where $\mu$ and $\sigma$ are constant. Explain carefully the difference between this model and each of the following:  

$$
\begin{array}{r l}&{\Delta S=\mu\Delta t+\sigma\epsilon\sqrt{\Delta t}}\ &{\Delta S=\mu S\Delta t+\sigma\epsilon\sqrt{\Delta t}}\ &{\Delta S=\mu\Delta t+\sigma S\epsilon\sqrt{\Delta t}}\end{array}
$$  

Why is the model in equation (14.8) a more appropriate model of stock price behavior than any of these three alternatives?  

14.18. It has been suggested that the short-term interest rate $r$ follows the stochastic process  

$$
d r=a(b-r)d t+r c d z
$$  

where $a$ , b, $c$ are positive constants and $d z$ is a Wiener process. Describe the nature of this process.  

14.19. Suppose that a stock price $S$ follows geometric Brownian motion with expected return $\mu$ and volatility $\sigma$  

$$
d S=\mu S d t+\sigma S d z
$$  

What is the process followed by the variable $S^{n_{\cdot}}{}$ Show that $S^{n}$ also follows geometric Brownian motion.  

14.20. Suppose that $x$ is the yield to maturity with continuous compounding on a zero-coupon bond that pays off $\$1$ at time $T.$ Assume that $x$ follows the process  

$$
d x=a(x_{0}-x)d t+s x d z
$$  

where $a,x_{0}$ , and $s$ are positive constants and $d z$ is a Wiener process. What is the process followed by the bond price?.  

14.21. A stock whose price is $\$30$ has an expected return of $9\%$ and a volatility of $20\%$ . In Excel, simulate the stock price path over 5 years using monthly time steps and random samples from a normal distribution. Chart the simulated stock price path. By hitting F9, observe how the path changes as the random samples change.  

4.22. Suppose that a stock price has an expected return of $16\%$ per annum and a volatility $30\%$ per annum. When the stock price at the end of a certain day is $\$50$ , calculate t following:  

(a) The expected stock price at the end of the next day (b) The standard deviation of the stock price at the end of the next day (c) The $95\%$ confidence limits for the stock price at the end of the next day.  

14.23. Suppose that $x$ is the yield on a perpetual government bond that pays interest at the rate of $\$1$ per annum. Assume that $x$ is expressed with continuous compounding, that interest is paid continuously on the bond, and that $x$ follows the process  

$$
d x=a(x_{0}-x)d t+s x d z
$$  

where $a,x_{0}$ , and $s$ are positive constants, and $d z$ is a Wiener process. What is the process followed by the bond price? What is the expected instantaneous return (including interest and capital gains) to the holder of the bond?  

14.24. Stock A, whose price is $\$30$ , has an expected return of $11\%$ and a volatility of $25\%$ Stock B, whose price is $\$40$ , has an expected return of $15\%$ and a volatility of $30\%$ . The processes driving the returns are correlated with correlation parameter $\rho$ . In Excel, simulate the two stock price paths over 3 months using daily time steps and random samples from normal distributions. Chart the results and by hitting F9 observe how the paths change as the random samples change. Consider values for $\rho$ equal to 0.25, 0.75, and 0.95.  

14.25. Consider whether markets are efficient in each of the following two cases: (a) a stock price follows fractional Brownian motion and (b) a stock price volatility follows fractional Brownian motion.  

# APPENDIX A NONRIGOROUS DERIVATION OF ITO'S LEMMA  

In this appendix, we show how Ito's lemma can be regarded as a natural extension of other, simpler results. Consider a continuous and differentiable function $G$ of a variable $x$ If $\Delta x$ is a small change in $x$ and $\Delta G$ is the resulting small change in $G$ a well-known result from ordinary calculus is.  

$$
\Delta G\approx{\frac{d G}{d x}}\Delta x
$$  

In other words,. $\Delta G$ is approximately equal to the rate of change of $G$ with respect to $x$ multiplied by. $\Delta x$ The error involves terms of order $\Delta x^{2}$ . If more precision is required, a Taylor series expansion of. $\Delta G$ can be used:  

$$
\Delta G={\frac{d G}{d x}}\Delta x+{\textstyle{\frac{1}{2}}}{\frac{d^{2}G}{d x^{2}}}\Delta x^{2}+{\textstyle{\frac{1}{6}}}{\frac{d^{3}G}{d x^{3}}}\Delta x^{3}+\cdot\cdot\cdot
$$  

For a continuous and differentiable function $G$ of two variables $x$ and $y$ , the result analogous to equation (14A.1) is  

$$
\Delta G\approx{\frac{\partial G}{\partial x}}\Delta x+{\frac{\partial G}{\partial y}}\Delta y
$$  

and the Taylor series expansion of $\Delta G$ is  

$$
\begin{array}{l}{\displaystyle{\Delta G=\frac{\partial G}{\partial x}\Delta x+\frac{\partial G}{\partial y}\Delta y+\frac{1}{2}\frac{\partial^{2}G}{\partial x^{2}}\Delta x^{2}+\frac{\partial^{2}G}{\partial x\partial y}\Delta x\Delta y+\frac{1}{2}\frac{\partial^{2}G}{\partial y^{2}}\Delta y^{2}+\cdot\cdot\cdot}}\end{array}
$$  

In the limit, as $\Delta x$ and $\Delta y$ tend to zero, equation (14A.3) becomes  

$$
d G={\frac{\partial G}{\partial x}}d x+{\frac{\partial G}{\partial y}}d y
$$  

We now extend equation (14A.4) to cover functions of variables following Ito processes. Suppose that a variable $x$ follows the Ito process  

$$
d x=a(x,t)d t+b(x,t)d z
$$  

and that $G$ is some function of. $x$ and of time $t$ By analogy with equation (14A.3), we can write  

$$
\Delta G={\frac{\partial G}{\partial x}}\Delta x+{\frac{\partial G}{\partial t}}\Delta t+{\frac{1}{2}}{\frac{\partial^{2}G}{\partial x^{2}}}\Delta x^{2}+{\frac{\partial^{2}G}{\partial x\partial t}}\Delta x\Delta t+{\frac{1}{2}}{\frac{\partial^{2}G}{\partial t^{2}}}\Delta t^{2}+\cdot\cdot\cdot
$$  

Equation (14A.5) can be discretized to  

$$
\Delta x=a(x,t)\Delta t+b(x,t)\epsilon\sqrt{\Delta t}
$$  

or, if arguments are dropped,  

$$
\Delta x=a\Delta t+b\epsilon\sqrt{\Delta t}
$$  

This equation reveals an important difference between the situation in equation (14A.6) and the situation in equation (14A.3). When limiting arguments were used to move from equation (14A.3) to equation (14A.4), terms in $\Delta x^{\bar{2}}$ were ignored because they were second-order terms. From equation (14A.7), we have  

$$
\Delta x^{2}=b^{2}\epsilon^{2}\Delta t+\mathrm{termsofhigherorderin}\Delta t
$$  

This shows that the term involving. $\Delta x^{2}$ in equation (14A.6) has a component that is of order $\Delta t$ and cannot be ignored..  

The variance of a standard normal distribution is 1.0. This means that  

$$
E(\epsilon^{2})\:-\:[E(\epsilon)]^{2}\:=\:1
$$  

where $E$ denotes expected value. Since $E(\epsilon)=0$ it follows that $E(\epsilon^{2})=1.$ The expected value of $\epsilon^{2}\Delta t$ , therefore, is $\Delta t$ The variance of $\epsilon^{2}\Delta t$ is, from the properties of the. standard normal distribution, $2\Delta t^{2}$ . We know that the variance of the change in a stochastic variable in time. $\Delta t$ is proportional to $\Delta t$ , not $\Delta t^{2}$ . The variance of $\overline{{\epsilon^{2}\Delta t}}$ is therefore too small for it to have a stochastic component. As a result, we can treat $\epsilon^{2}\Delta t$ as nonstochastic and equal to its expected value, $\Delta t$ , as $\Delta t$ tends to zero. It follows from. equation (14A.8) that $\bar{\Delta}x^{2}$ becomes nonstochastic and equal to. $b^{2}d t$ as $\Delta t$ tends to zero. Taking limits as $\Delta x$ and $\Delta t$ tend to zero in equation (14A.6), and using this last result, we obtain  

$$
d G={\frac{\partial G}{\partial x}}d x+{\frac{\partial G}{\partial t}}d t+{\textstyle{\frac{1}{2}}}{\frac{\partial^{2}G}{\partial x^{2}}}b^{2}d t
$$  

This is Ito's lemma. If we substitute for $d x$ from equation (14A.5), equation (14A.9) becomes  

$$
d G=\left({\frac{\partial G}{\partial x}}a+{\frac{\partial G}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}G}{\partial x^{2}}}b^{2}\right)d t+{\frac{\partial G}{\partial x}}b d z.
$$  

Technical Note 29 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes provides proofs of extensions to Ito's lemma. When. $G$ is a function of variables $x_{1},x_{2},\ldots,x_{n}$ and  

$$
d x_{i}=a_{i}d t+b_{i}d z_{i}
$$  

we have  

$$
d G=\left(\sum_{i=1}^{n}{\frac{\partial G}{\partial x_{1}}}a_{i}+{\frac{\partial G}{\partial t}}+{\frac{1}{2}}\sum_{i=1}^{n}\sum_{j=1}^{n}{\frac{\partial^{2}G}{\partial x_{i}\partial x_{j}}}b_{i}b_{j}\rho_{i j}\right)d t+\sum_{i=1}^{n}{\frac{\partial G}{\partial x_{i}}}b_{i}d z_{i}
$$  

Also, when. $G$ is a function of a variable. $x$ with several sources of uncertainty so that  

$$
d x=a d t+\sum_{i=1}^{m}b_{i}d z_{i}
$$  

we have  

$$
d G=\left({\frac{\partial G}{\partial x}}a+{\frac{\partial G}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}G}{\partial x^{2}}}\sum_{i=1}^{m}\sum_{j=1}^{m}b_{i}b_{j}\rho_{i j}\right)d t+{\frac{\partial G}{\partial x}}\sum_{i=1}^{m}b_{i}d z_{i}
$$  

In these equations, $\rho_{i j}$ is the correlation between $d z_{i}$ and $d z_{j}$ (see Section 14.5).  

![](images/2d59f63d0b51c9873cff0f038bf2eef594345bbc40ca8a34500fb17d20b5d597.jpg)  

# The BlackScholes-Merton Model  

In the early 1970s, Fischer Black, Myron Scholes, and Robert Merton achieved a major breakthrough in the pricing of European stock options.' This was the development of what has become known as the Black-Scholes-Merton (or Black-Scholes) model. The model has had a huge influence on the way that traders price and hedge derivatives. In 1997, the importance of the model was recognized when Robert Merton and Myron Scholes were awarded the Nobel prize for economics. Sadly, Fischer Black died in 1995; otherwise he too would undoubtedly have been one of the recipients of this prize.  

How did Black, Scholes, and Merton make their breakthrough? Previous researchers had made similar assumptions and had correctly calculated the expected payoff from a European option. However, as explained in Section 13.2, it is difficult to know the correct discount rate to use for this payoff. Black and Scholes used the capital asset pricing model (see the appendix to Chapter 3) to determine a relationship between the. market's required return on the option and the required return on the stock. This was not easy because the relationship depends on both the stock price and time. Merton's approach was different from that of Black and Scholes. It involved setting up a riskless. portfolio consisting of the option and the underlying stock and arguing that the return on the portfolio over a short period of time must be the risk-free return. This is similar to what we did in Section 13.1--but more complicated because the portfolio changes continuously through time. Merton's approach was more general than that of Black and Scholes because it did not rely on the assumptions of the capital asset pricing model..  

This chapter covers Merton's approach to deriving the Black-Scholes-Merton. model. It explains how volatility can be either estimated from historical data or implied from option prices using the model. It shows how the risk-neutral valuation argument introduced in Chapter 13 can be used. It also shows how the Black-Scholes-Merton model can be extended to deal with European call and put options on dividend-paying. stocks and presents some results on the pricing of American call options on dividendpaying stocks.  
