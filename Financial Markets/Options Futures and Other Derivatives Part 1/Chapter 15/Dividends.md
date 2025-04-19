---
tags:
  - black_scholes_merton_model
  - dividends
  - european_options
  - ex_dividend_date
  - option_pricing
aliases:
  - dividend impact
  - dividend payments
key_concepts:
  - Black-Scholes-Merton formula
  - European call option
  - dividends and options
  - ex-dividend date impact
  - stock price components
---

# 15.12 DIVIDENDS  

Up to now, we have assumed that the stock on which the option is written pays no. dividends. In this section, we modify the Black-Scholes-Merton model to take account. of dividends. We assume that the amount and timing of the dividends during the life of an option can be predicted with certainty. When options last for relatively short periods of time, this assumption is not too unreasonable. (For long-life options it is usual to assume that the dividend yield rather the dollar dividend payments are known. Options. can then be valued as will be described in the Chapter 17.) The date on which the dividend is paid should be assumed to be the ex-dividend date. On this date the stock price declines by the amount of the dividend.12  

# European Options  

European options can be analyzed by assuming that the stock price is the sum of two. components: a riskless component that corresponds to the known dividends during. the life of the option and a risky component. The riskless component, at any given time, is the present value of all the dividends during the life of the option discounted from the ex-dividend dates to the present at the risk-free rate. By the time the option matures, the dividends will have been paid and the riskless component will no longer exist. The Black-Scholes-Merton formula is therefore correct if. $S_{0}$ is equal to the risky component of the stock price and. $\sigma$ is the volatility of the process followed by. the risky component.13  

Operationally, this means that the Black-Scholes-Merton formulas can be used provided that the stock price is reduced by the present value of all the dividends during the life of the option, the discounting being done from the ex-dividend dates at the riskfree rate. As already mentioned, a dividend is counted as being during the life of the option only if its ex-dividend date occurs during the life of the option.  

# Example 15.9  

Consider a European call option on a stock when there are ex-dividend dates in two months and five months. The dividend on each ex-dividend date is expected to be $\$0.50$ . The current share price is $\$40$ , the exercise price is $\$40$ , the stock price volatility is $30\%$ per annum, the risk-free rate of interest is $9\%$ per annum, and the time to maturity is six months. The present value of the dividends is  

$$
0.5e^{-0.09\times2/12}+0.5e^{-0.09\times5/12}=0.9742
$$  

The option price can therefore be calculated from the Black-Scholes-Merton  

formula, with $S_{0}=40\mathrm{~-~}0.9742=39.0258$ $K=40$ $r=0.09$ $\sigma=0.3$ , and $T=0.5$  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(39.0258/40)+(0.09+0.3^{2}/2)\times0.5}{0.3\sqrt{0.5}}=0.2020}}\ {{d_{2}=\displaystyle\frac{\ln(39.0258/40)+(0.09-0.3^{2}/2)\times0.5}{0.3\sqrt{0.5}}=-0.0102}}\end{array}
$$  

Using the NORMSDIST function in Excel gives  

$$
N(d_{1})=0.5800,~N(d_{2})=0.4959
$$  

and, from equation (15.20), the call price is  

$$
39.0258\times0.5800-40e^{-0.09\times0.5}\times0.4959=3.67
$$  

or $\$3.67$  

Some researchers have criticized the approach just described for calculating the value. of a European option on a dividend-paying stock. They argue that volatility should be applied to the stock price, not to the stock price less the present value of dividends. A number of different numerical procedures have been suggested for doing this.14 when. volatility is calculated from historical data, it might make sense to use one of these procedures. However, in practice the volatility used to price an option is nearly always. implied from the prices of other options using procedures we will outline in Chapter 20.. If an analyst uses the same model for both implying and applying volatilities, the resulting prices should be accurate and not highly model dependent. Another important point is that in practice, as will be explained in Chapter 18, practitioners usually value a European option in terms of the forward price of the underlying asset. This avoids the. need to estimate explicitly the income that is expected from the asset. The volatility of the forward stock price is the same as the volatility of a variable equal to the stock price minus the present value of dividends..  

The model we have proposed where the stock price is divided into two components is. internally consistent and widely used in practice. We will use the same model when valuing American options in Chapter 21.  

# American Call Options  

Consider next American call options. Chapter 11 showed that in the absence of dividends American options should never be exercised early. An extension to the argument shows that, when there are dividends, it can only be optimal to exercise at a time immediately before the stock goes ex-dividend. We assume that $n$ ex-dividend dates are anticipated and that they are at times $t_{1},t_{2},\ldots,t_{n}$ with $t_{1}<t_{2}<...<t_{n}$ The dividends corresponding to these times will be denoted by $D_{1},D_{2},\ldots,D_{n}$ respectively.  

We start by considering the possibility of early exercise just prior to the final ex-dividend date (i.e., at time. $t_{n}$ ). If the option is exercised at time. $t_{n}$ ,the investor receives  

$$
S(t_{n})\mathrm{~-~}K
$$  

where $S(t)$ denotes the stock price at time $t$ If the option is not exercised, the stock price drops to $S(t_{n})~-~D_{n}$ As shown by equation (11.4), the value of the option is then greater than  

$$
S(t_{n})\mathrm{~-~}D_{n}\mathrm{~-~}K e^{-r(T-t_{n})}
$$  

It follows that, if  

$$
S(t_{n})-D_{n}-K e^{-r(T-t_{n})}\geq S(t_{n})-K
$$  

that is,  

$$
D_{n}\leq K[1-e^{-r(T-t_{n})}]
$$  

it cannot be optimal to exercise at time $t_{n}$ . On the other hand, if.  

$$
D_{n}>K[1-e^{-r(T-t_{n})}]
$$  

for any reasonable assumption about the stochastic process followed by the stock price, it can be shown that it is always optimal to exercise at time $t_{n}$ for a sufficiently high. value of $S(t_{n})$ . The inequality in (15.24) will tend to be satisfied when the final exdividend date is fairly close to the maturity of the option (i.e., $T-t_{n}$ is small) and the dividend is large.  

Consider next time $t_{n-1}$ , the penultimate ex-dividend date. If the option is exercised immediately prior to time $t_{n-1}$ , the investor receives $S(t_{n-1})\textrm{--}K$ If the option is not exercised at time $t_{n-1.}$ the stock price drops to. $S(t_{n-1})~-~D_{n-1}$ and the earliest subsequent time at which exercise could take place is $t_{n}$ . Hence, from equation (11.4), a lower bound to the option price if it is not exercised at time $t_{n-1}$ is  

$$
S(t_{n-1})\:-\:D_{n-1}-K e^{-r(t_{n}-t_{n-1})}
$$  

It follows that if  

$$
S(t_{n-1})-D_{n-1}-K e^{-r(t_{n}-t_{n-1})}\geq S(t_{n-1})-K
$$  

or  

$$
D_{n-1}\leq K[1-e^{-r(t_{n}-t_{n-1})}]
$$  

it is not optimal to exercise immediately prior to time $t_{n-1}$ . Similarly, for any $i<n$ , if  

$$
D_{i}\leq K[1-e^{-r(t_{i+1}-t_{i})}]
$$  

it is not optimal to exercise immediately prior to time $t_{i}$  

The inequality in (15.25) is approximately equivalent to  

$$
D_{i}\leq K r(t_{i+1}-t_{i})
$$  

Assuming that $K$ is fairly close to the current stock price, this inequality is satisfied. when the dividend yield on the stock is less than the risk-free rate of interest. This is often not true in low interest environments..  

We can conclude from this analysis that, in many circumstances, the most likely time for the early exercise of an American call is immediately before the final ex dividend date, $t_{n}$ Furthermore, if inequality (15.25) holds for $i=1,2,\dots,n-1$ and inequality (15.23) holds, we can be certain that early exercise is never optimal, and the American option can be treated as a European option.  

# Black's Approximation  

Black suggests an approximate procedure for taking account of early exercise in call options.15 This involves calculating, as described earlier in this section, the prices of European options that mature at times $T$ and $t_{n}$ , and then setting the American price equal to the greater of the two.16 This is an approximation because it in effect assumes the option. holder has to decide at time zero whether the option will be exercised at time $T$ or $t_{n}$  

# SUMMARY  

We started this chapter by examining the properties of the process for stock prices introduced in Chapter 14. The process implies that the price of a stock at some future time, given its price today, is lognormal. It also implies that the continuously compounded return from the stock in a period of time is normally distributed. Our uncertainty about future stock prices increases as we look further ahead. The standard deviation of the logarithm of the stock price is proportional to the square root of how far ahead we are looking.  

To estimate the volatility $\sigma$ of a stock price empirically, the stock price is observed at fixed intervals of time (e.g., every day, every week, or every month). For each time period, the natural logarithm of the ratio of the stock price at the end of the time period to the stock price at the beginning of the time period is calculated. The volatility is estimated as the standard deviation of these numbers divided by the square root of the length of the time period in years. Usually, days when the exchanges are closed are ignored in measuring time for the purposes of volatility calculations.  

The differential equation for the price of any derivative dependent on a stock can be. obtained by creating a riskless portfolio of the derivative and the stock. Because the. derivative's price and the stock price both depend on the same underlying source of. uncertainty, this can always be done. The portfolio that is created remains riskless for only a very short period of time. However, the return on a riskless porfolio must always. be the risk-free interest rate if there are to be no arbitrage opportunities..  

The expected return on the stock does not enter into the Black-Scholes-Merton differential equation. This leads to an extremely useful result known as risk-neutral valuation. This result states that when valuing a derivative dependent on a stock price, we can assume that the world is risk neutral. This means that we can assume that the expected return from the stock is the risk-free interest rate, and then discount expected payoffs at the risk-free interest rate. The Black-Scholes-Merton equations for European call and put options can be derived by either solving their differential equation or by using risk-neutral valuation.  

An implied volatility is the volatility that, when used in conjunction with the Black-- Scholes-Merton option pricing formula, gives the market price of the option. Traders.  

monitor implied volatilities. They often quote the implied volatility of an option rather than its price. They have developed procedures for using the volatilities implied by the prices of actively traded options to estimate volatilities for other options on the same asset.  

The Black-Scholes-Merton results can be extended to cover European call and put. options on dividend-paying stocks. The procedure is to use the Black-Scholes-Merton. formula with the stock price reduced by the present value of the dividends anticipated during the life of the option, and the volatility equal to the volatility of the stock price net of the present value of these dividends..  

It can be optimal to exercise American call options immediately before any exdividend date, but in practice early exercise is most likely on the final ex-dividend date. Fischer Black has suggested an approximation. This involves setting the American call option price equal to the greater of two European call option prices. The first European call option expires at the same time as the American call option; the second expires immediately prior to the final ex-dividend date.  

# FURTHER READING  

# On the Distribution of Stock Price Changes  

Blattberg, R., and N. Gonedes, "A Comparison of the Stable and Student Distributions as Statistical Models for Stock Prices,' Journal of Business, 47 (April 1974): 244-80.   
Fama, E. F., "The Behavior of Stock Market Prices, Journal of Business, 38 (January 1965): 34-105.   
Kon, S. J., "Models of Stock Returns-A Comparison, Journal of Finance, 39 (March 1984): 147-65.   
Richardson, M., and T. Smith, "A Test for Multivariate Normality in Stock Returns, Journal of Business, 66 (1993): 295-321.   
On the Black-Scholes-Merton Analysis   
Black, F. "Fact and Fantasy in the Use of Options and Corporate Liabilities, Financial Analysts Journal, 31 (July/August 1975): 36-41, 61-72.   
Black, F. "How We Came Up with the Option Pricing Formula, Journal of Portfolio Management, 15, 2 (1989): 4-8.   
Black, F., and M. Scholes, "The Pricing of Options and Corporate Liabilities,' Journal of. Political Economy, 81 (May/June 1973): 637-59.   
Merton, R. C., "Theory of Rational Option Pricing,' Bell Journal of Economics and Management Science, 4 (Spring 1973): 141-83.   
On Risk-Neutral Valuation   
Cox, J. C., and S. A. Ross, "The Valuation of Options for Alternative Stochastic Processes, Journal of Financial Economics, 3 (1976): 145-66.   
Smith, C. W., "Option Pricing: A Review, Journal of Financial Economics, 3 (1976): 3-54.   
On the Causes of Volatility   
Fama, E. F. " The Behavior of Stock Market Prices.' Journal of Business, 38 (January 1965): 34-105.   
French, K. R. "Stock Returns and the Weekend Effect.' Journal of Financial Economics, 8 (March 1980): 55-69.   
French, K. R., and R. Roll "Stock Return Variances: The Arrival of Information and the Reaction of Traders.' Journal of Financial Economics, 17 (September 1986): 5-26.   
Roll R. "Orange Juice and Weather,' American Economic Review, 74, 5 (December 1984): 861-80..  

# Short Concept Questions  

15.1. What does the Black-Scholes-Merton model assume about the return on a stock in a short period of time?   
15.2. What are the mean and standard deviation of the logarithm of the stock price at time $T$ in the model assumed by Black-Scholes-Merton?   
15.3. In the Black-Scholes-Merton model, what happens to the standard deviation of the continuously compounded rate of return as the length of the time period over which it is measured increases?   
15.4. How are weekends and holidays handled when volatility is estimated and used?.   
15.5. How is a riskless portfolio set up in order to derive the Black-Scholes-Merton. differential equation?   
15.6. What is the Black-Scholes-Merton price of European call and put options on an asset providing no income?   
15.7. Explain the principle of risk-neutral valuation..   
15.8. What is the difference between a warrant to purchase a stock and an exchange-traded stock option?   
15.9. How is an implied volatility calculated?   
15.10. How can the Black-Scholes-Merton formulas be adjusted to take account of known dividends?  

# Practice Questions  

15.11. What does the Black-Scholes-Merton stock option pricing model assume about the probability distribution of the stock price in one year? What does it assume about the. probability distribution of the continuously compounded rate of return on the stock. during the year?   
15.12. The volatility of a stock price is $30\%$ per annum. What is the standard deviation of the percentage price change in one trading day?   
15.13. Calculate the price of a 3-month European put option on a non-dividend-paying stock with a strike price of $\$50$ when the current stock price is $\$50$ , the risk-free interest rate is $10\%$ per annum, and the volatility is $30\%$ per annum.   
15.14. What difference does it make to your calculations in Problem 15.13 if a dividend of $\$1.50$ is expected in 2 months?   
15.15. A stock price is currently $\$40$ . Assume that the expected return from the stock is $15\%$ and that its volatility is $25\%$ . What is the probability distribution for the rate of return (with continuous compounding) earned over a 2-year period?   
15.16. A stock price follows geometric Brownian motion with an expected return of $16\%$ and a volatility of $35\%$ . The current price is $\$38$ (a) What is the probability that a European call option on the stock with an exercise price of $\$40$ and a maturity date in 6 months will be exercised? (b) What is the probability that a European put option on the stock with the same exercise price and maturity will be exercised?  

15.17. Using the notation in this chapter, prove that a $95\%$ confidence interval for $S_{T}$ is between $S_{0}e^{(\mu-\sigma^{2}/2)T-1.96\sigma\sqrt{T}}$ and $S_{0}e^{(\stackrel{\rightharpoonup}{\mu}-\sigma^{2}/2)T+1.96\sigma\sqrt{T}}$  

15.18. A portfolio manager announces that the average of the returns realized in each year of the last 10 years is $20\%$ per annum. In what respect is this statement misleading?.  

15.19. Assume that a non-dividend-paying stock has an expected return of $\mu$ and a volatility of $\sigma$ . An innovative financial institution has just announced that it will trade a security that pays off a dollar amount equal to ln $S_{T}$ at time $T$ where $S_{T}$ denotes the value of the stock price at time $T$  

(a) Use risk-neutral valuation to calculate the price of the security at time $t$ in terms of the stock price, $S$ at time $t.$ The risk-free rate is $r$ (b) Confirm that your price satisfies the differential equation (15.16).  

15.20. Consider a derivative that pays off $S_{T}^{n}$ at time $T$ where $S_{T}$ is the stock price at that time. When the stock pays no dividends and its price follows geometric Brownian motion, it can be shown that its price at time. $t$ $(t\leq T)$ has the form. $h(t,T)S^{n}$ , where $S$ is the stock. price at time $t$ and $h$ is a function only of. $t$ and $T$  

(a) By substituting into the Black-Scholes-Merton partial differential equation, derive an ordinary differential equation satisfied by $h(t,T)$   
(b) What is the boundary condition for the differential equation for $h(t,T)?$   
(c) Show that $h(t,T)={\check{e}}^{[0.5\sigma^{2}n(n-1)+r(n-1)](T-t)}$ , where $r$ is the risk-free interest rate and $\sigma$ is the stock price volatility.  

15.21. What is the price of a European call option on a non-dividend-paying stock when the stock price is $\$52$ , the strike price is $\$50$ , the risk-free interest rate is $12\%$ per annum, the volatility is $30\%$ per annum, and the time to maturity is 3 months?  

15.22. What is the price of a European put option on a non-dividend-paying stock when the stock price is $\$69$ , the strike price is $\$70$ , the risk-free interest rate is. $5\%$ per annum, the. volatility is $35\%$ per annum, and the time to maturity is 6 months?  

15.23. Consider an American call option on a stock. The stock price is $\$70$ , the time to maturity is 8 months, the risk-free rate of interest is $10\%$ per annum, the exercise price is. $\$65$ , and the volatility is. $32\%$ . A dividend of. $\$1$ is expected after 3 months and again after 6 months. Show that it can never be optimal to exercise the option on either of the two dividend dates. Use DerivaGem to calculate the price of the option.  

15.24. A call option on a non-dividend-paying stock has a market price of $\$2$ . The stock price is $\$15$ , the exercise price is $\$13$ , the time to maturity is 3 months, and the risk-free interest rate is $5\%$ per annum. What is the implied volatility?  

15.25. With the notation used in this chapter:  

(a) What is $N^{\prime}(x)$ (b) Show that $\dot{S}N^{\prime}(d_{1})=K e^{-r(T-t)}N^{\prime}(d_{2})$ , where $S$ is the stock price at time $t$ and  

$$
d_{1}={\frac{\ln(S/K)+(r+\sigma^{2}/2)(T-t)}{\sigma{\sqrt{T-t}}}},d_{2}={\frac{\ln(S/K)+(r-\sigma^{2}/2)(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

(c) Calculate $\partial d_{1}/\partial S$ and $\partial d_{2}/\partial S$ (d) Show that when $c=S\bar{N(}d_{1})-K e^{-r(T-t)}N(d_{2})$ , it follows that  

$$
\frac{\partial c}{\partial t}=-r K e^{-r(T-t)}N(d_{2})-S N^{\prime}(d_{1})\frac{\sigma}{2\sqrt{T-t}}
$$  

where $c$ is the price of a call option on a non-dividend-paying stock.  

(e) Show that $\partial c/\partial S=N(d_{1})$   
(f) Show that $c$ satisfies the Black-Scholes-Merton differential equation.   
(g) Show that $c$ satisfies the boundary condition for a European call option, i.e., that $c=\operatorname*{max}(S-K,0)$ as $t\longrightarrow T$  

15.26. Show that the Black-Scholes-Merton formulas for call and put options satisfy put-call parity.  

15.27. A stock price is currently $\$50$ and the risk-free interest rate is $5\%$ . Use the DerivaGem software to translate the following table of European call options on the stock into a. table of implied volatilities, assuming no dividends. Are the option prices consistent with the assumptions underlying Black-Scholes-Merton?.  

<html><body><table><tr><td rowspan="2">Strike price ($)</td><td colspan="2">Maturity (months)</td></tr><tr><td>3</td><td>6 12</td></tr><tr><td>45</td><td>7.0</td><td>8.3 10.5</td></tr><tr><td>50</td><td>3.7</td><td>7.5</td></tr><tr><td>55</td><td>1.6</td><td>5.1</td></tr></table></body></html>  

15.28. Explain carefully why Black's approach to evaluating an American call option on a dividend-paying stock may give an approximate answer even when only one dividend is anticipated. Does the answer given by Black's approach understate or overstate the true. option value? Explain your answer.   
15.29. Consider an American call option on a stock. The stock price is $\$50$ , the time to maturity is 15 months, the risk-free rate of interest is $8\%$ per annum, the exercise price is $\$55$ , and the volatility is $25\%$ . Dividends of. $\$1.50$ are expected in 4 months and 10 months. Show. that it can never be optimal to exercise the option on either of the two dividend dates.. Calculate the price of the option.   
15.30. Show that the probability that a European call option will be exercised in a risk-neutral world is, with the notation introduced in this chapter, $N(d_{2})$ . What is an expression for the value of a derivative that pays off $\$100$ if the price of a stock at time $T$ is greater than $K\mathord{?}$   
15.31. Use the result in equation (15.17) to determine the value of a perpetual American put option on a non-dividend-paying stock with strike price $K$ if it is exercised when the stock price equals $H$ where $H<K$ Assume that the current stock price $S$ is greater than $H.$ What is the value of $H$ that maximizes the option value? Deduce the value of a. perpetual American put with strike price $K$   
15.32. A company has an issue of executive stock options outstanding. Should dilution be. taken into account when the options are valued? Explain your answer.   
15.33. A company's stock price is $\$50$ and 10 million shares are outstanding. The company is considering giving its employees 3 million at-the-money 5-year call options. Option exercises will be handled by issuing more shares. The stock price volatility is $25\%$ , the 5-year risk-free rate is $5\%$ , and the company does not pay dividends. Estimate the cost to the company of the employee stock option issue.   
15.34. If the volatility of a stock is $18\%$ per annum, estimate the standard deviation of the. percentage price change in (a) 1 day, (b) 1 week, and (c) 1 month.   
15.35. A stock price is currently $\$50$ Assume that the expected return from the stock is $18\%$ and its volatility is $30\%$ . What is the probability distribution for the stock price in  

2 years? Calculate the mean and standard deviation of the distribution. Determine the $95\%$ confidence interval.  

15.36. Suppose that observations on a stock price (in dollars) at the end of each of 15 consecutive weeks are as follows:  

30.2, 32.0, 31.1, 30.1, 30.2, 30.3, 30.6, 33.0, 32.9, 33.0, 33.5, 33.5, 33.7, 33.5, 33.2  

Estimate the stock price volatility. What is the standard error of your estimate?  

15.37. The appendix derives the key result  

$$
E[\operatorname*{max}(V-K,0)]=E(V)N(d_{1})-K N(d_{2})
$$  

Show that  

$$
E[\operatorname*{max}(K-V,0)]=K N(-d_{2})-E(V)N(-d_{1})
$$  

and use this to derive the Black-Scholes-Merton formula for the price of a European put option on a non-dividend-paying stock..  

# APPENDIX PROOF OF THE BLACK-SCHOLES-MERTON FORMULA USING RISK-NEUTRAL VALUATION  

We will prove the Black-Scholes result by first proving another key result that will also be useful in future chapters.  

# Key Result  

If $V$ is lognormally distributed and the standard deviation of ln $V$ is $w$ , then  

$$
E[\operatorname*{max}(V-K,0)]=E(V)N(d_{1})-K N(d_{2})
$$  

where  

$$
\begin{array}{l}{displaystyle{d_{1}=\frac{\ln[E(V)/K]+w^{2}/2}{w}}}\ {{d_{2}=\frac{\ln[E(V)/K]-w^{2}/2}{w}}}\end{array}
$$  

and $E$ denotes the expected value. (See Problem 15.37 for a similar result for puts.)  

# Proof of Key Result  

Define $g(V)$ as the probability density function of $V.$ It follows that  

$$
E[\operatorname*{max}(V-K,0)]=\int_{K}^{\infty}(V-K)g(V)d V
$$  

The variable ln $V$ is normally distributed with standard deviation $w$ . From the properties of the lognormal distribution, the mean of ln $V$ .5 $m$ , where17  

$$
m=\ln[E(V)]-w^{2}/2
$$  

Define a new variable  

$$
Q={\frac{\ln V-m}{w}}
$$  

This variable is normally distributed with a mean of zero and a standard deviation of 1.0. Denote the density function for $Q$ by $h(Q)$ so that  

$$
h(Q)={\frac{1}{\sqrt{2\pi}}}e^{-Q^{2}/2}
$$  

Using equation (15A.4) to convert the expression on the right-hand side of equation (15A.2) from an integral over $V$ to an integral over $Q$ , we get  

$$
E[\operatorname*{max}(V-K,0)]=\int_{(\ln K-m)/w}^{\infty}(e^{Q w+m}-K)h(Q)d Q
$$  

or  

$$
E[\operatorname*{max}(V-K,0)]=\int_{(\ln K-m)/w}^{\infty}e^{Q w+m}h(Q)d Q-K\int_{(\ln K-m)/w}^{\infty}h(Q)d Q
$$  

Now  

$$
\begin{array}{c}{{e^{Q w+m}h(Q)=\displaystyle\frac{1}{\sqrt{2\pi}}e^{(-Q^{2}+2Q w+2m)/2}=\displaystyle\frac{1}{\sqrt{2\pi}}e^{[-(Q-w)^{2}+2m+w^{2}]/2}}}\ {{=\displaystyle\frac{e^{m+w^{2}/2}}{\sqrt{2\pi}}e^{[-(Q-w)^{2}]/2}=e^{m+w^{2}/2}h(Q-w)}}\end{array}
$$  

This means that equation (15A.5) becomes  

$$
E[\operatorname*{max}(V-K,0)]=e^{m+w^{2}/2}\int_{(\ln K-m)/w}^{\infty}h(Q-w)d Q-K\int_{(\ln K-m)/w}^{\infty}h(Q)d Q(\theta)d\theta
$$  

If we define $N(x)$ as the probability that a variable with a mean of zero and a standard deviation of 1.0 is less than $x$ , the first integral in equation (15A.6) is.  

$$
1-N[(\ln K-m)/w-w]=N[(-\ln K+m)/w+w]
$$  

Substituting for $m$ from equation (15A.3) leads to  

$$
N\bigg(\frac{\ln[E(V)/K]+w^{2}/2}{w}\bigg)=N(d_{1})
$$  

Similarly the second integral in equation (15A.6) is $N(d_{2})$ . Equation (15A.6), therefore,. becomes  

$$
E[\operatorname*{max}(V-K,0)]=e^{m+w^{2}/2}N(d_{1})-K N(d_{2})
$$  

Substituting for $m$ from equation (15A.3) gives the key result.  

# The Black-Scholes-Merton Result  

We now consider a call option on a non-dividend-paying stock maturing at time $T.$ The strike price is. $K$ , the risk-free rate is $r$ , the current stock price is $S_{0}$ , and the volatility is $\sigma$ . As shown in equation (15.22), the call price. $c$ is given by.  

$$
c=e^{-r T}\hat{E}[\operatorname*{max}(S_{T}-K,0)]
$$  

where $S_{T}$ is the stock price at time $T$ and $\hat{E}$ denotes the expectation in a risk-neutral. world. Under the stochastic process assumed by Black-Scholes-Merton, $S_{T}$ is lognormal. Also, from equations (15.3) and (15.4),. $\hat{E}(S_{T})=S_{0}e^{r T}$ and the standard deviation of ln $S_{T}$ is $\sigma\sqrt[3]{T}$  

From the key result just proved, equation (15A.7) implies  

$$
c=e^{-r T}[S_{0}e^{r T}N(d_{1})-K N(d_{2})]=S_{0}N(d_{1})-K e^{-r T}N(d_{2})
$$  

where  

$$
\begin{array}{r l}&{d_{1}=\frac{\ln[\hat{E}(S_{T})/K]+\sigma^{2}T/2}{\sigma\sqrt{T}}=\frac{\ln(S_{0}/K)+(r+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ &{d_{2}=\frac{\ln[\hat{E}(S_{T})/K]-\sigma^{2}T/2}{\sigma\sqrt{T}}=\frac{\ln(S_{0}/K)+(r-\sigma^{2}/2)T}{\sigma\sqrt{T}}}\end{array}
$$  

This is the Black-Scholes-Merton result.  

![](a504587b88552c4fd0175f60f2ec348488cfbc45bb05ab72c4db7979b5aff9e9.jpg)  

# Employee Stock Options  

Employee stock options are call options on a company's stock granted by the company to its employees. The options give the employees a stake in the fortunes of the company. If the company does well so that the company's stock price moves above the strike price, employees gain by exercising the options and then selling the stock they acquire at the market price.  

Many companies, particularly technology companies, feel that the only way they can attract and keep the best employees is to offer them attractive stock option packages. Some companies grant options only to senior management; others grant them to people at all levels in the organization. Microsoft was one of the first companies to use employee stock options. All Microsoft employees were granted options and, as the company's stock price rose, it is estimated that over 10,o00 of them became millionaires. Employee stock options have become less popular in recent years for reasons we will explain in this chapter. (Microsoft, for example, announced in 2003 that it would discontinue the use of. options and award shares of Microsoft to employees instead.) But many companies throughout the world continue to be enthusiastic users of employee stock options..  

Employee stock options are popular with start-up companies. Often these companies do not have the resources to pay key employees as much as they could earn with an. established company and they solve this problem by supplementing the salaries of the. employees with stock options. If the company does well and shares are sold to the public in an initial public offering (IPO), the options are likely to prove to be very valuable. Some newly formed companies have even granted options to students who worked for just a few months during their summer break-and in some cases this has led to windfalls of hundreds of thousands of dollars for the students..  

This chapter explains how stock option plans work and how their popularity has been influenced by their accounting treatment. It discusses whether employee stock options help to align the interests of shareholders with those of top executives running a company. It also describes how these options are valued and looks at backdating scandals.  
