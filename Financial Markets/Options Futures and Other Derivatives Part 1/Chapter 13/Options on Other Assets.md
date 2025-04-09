# 13.11 OPTIONS ON OTHER ASSETS  

We introduced options on indices, currencies, and futures contracts in Chapter 10 and will cover them in more detail in Chapters 17 and 18. It turns out that we can construct and use binomial trees for these options in exactly the same way as for options on stocks except that the equation for $p$ changes. As in the case of options on stocks, equation (13.2) applies so that the value at a node (before the possibility of early exercise is considered) is $p$ times the value if there is an up movement plus $1-p$ times the value if there is a down movement, discounted at the risk-free rate.  

# Options on Stocks Paying a Continuous Dividend Yield  

Consider a stock paying a known dividend yield at rate $q$ . The total return from dividends and capital gains in a risk-neutral world is. $r$ The dividends provide a return of $q$ . Capital gains must therefore provide a return of. $r\mathrm{~-~}q$ If the stock starts at $S_{0}$ , its expected value after one time step of length $\Delta t$ must be $S_{0}e^{(r-q)\Delta t},$ This means that.  

$$
p S_{0}u+(1-p)S_{0}d=S_{0}e^{(r-q)\Delta t}
$$  

so that  

$$
p=\frac{e^{(r-q)\Delta t}-d}{u-d}
$$  

As in the case of options on non-dividend-paying stocks, we match volatility by setting $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=1/u.$ This means that we can use equations (13.15) to (13.18), except that we set $a=e^{(r-q)\Delta t}$ instead of $a=e^{r\Delta t}$  

# Options on Stock Indices  

When calculating a futures price for a stock index in Chapter 5 we assumed that the stocks underlying the index provided a dividend yield at rate $q$ . We make a similar assumption here. The valuation of an option on a stock index is therefore very similar to the valuation of an option on a stock paying a known dividend yield.  

# Example 13.1  

A stock index is currently 810 and has a volatility of. $20\%$ and a dividend yield of. $2\%$ . The risk-free rate is $5\%$ . Figure 13.11 shows the output from DerivaGem for. valuing a European 6-month call option with a strike price of 800 using a two-step tree. In this case,  

$$
\begin{array}{r}{\Delta t=0.25,\qquadu=e^{0.20\times\sqrt{0.25}}=1.1052,\qquad}\ {d=1/u=0.9048,\qquada=e^{(0.05-0.02)\times0.25}=1.0075}\ {p=(1.0075-0.9048)/(1.1052-0.9048)=0.5126}\end{array}
$$  

The value of the option is 53.39.  

Figure 13.11 Two-step tree to value a European 6-month call option on an index when the index level is 810, strike price is 800, risk-free rate is $5\%$ volatility is $20\%$ , and dividend yield is. $2\%$ (DerivaGem output).  

At each node: Upper value $=$ Underlying Asset Price. Lower value $=$ Option Price Shading indicates where option is exercised  

Strike price $=800$   
Discount factor per ${\tt s t e p}=0.9876$   
Time step, $\mathrm{dt}=0.2500$ years, 91.25 days   
Growth factor per step, $a=1.0075$   
Probability of up move, $\mathsf{p}=0.5126$   
Up step size, $\u\mathfrak{u}=1.1052$   
Down step size, $\mathsf{d}=0.9048$  

![](images/925eb7133ad11ce5736063b5123b55b34c0f754c8ce58f9131baf0672b8fea34.jpg)  

# Options on Currencies  

As pointed out in Section 5.10, a foreign currency can be regarded as an asset providing a yield at the foreign risk-free rate of interest,. $r_{f}.$ By analogy with the stock index case. we can construct a tree for options on a currency by using equations (13.15) to (13.18) and setting a = e(r-r)4t.  

# Example 13.2  

A foreign currency is currently worth 0.6100 U.S. dollars and this exchange rate has. a volatility of $12\%$ . The foreign risk-free rate is $7\%$ and the U.S. risk-free rate. is $5\%$ . Figure 13.12 shows the output from DerivaGem for valuing a 3-month American call option with a strike price of 0.6000 using a three-step tree. In this case,  

$$
\begin{array}{c}{\Delta t=0.08333,~u=e^{0.12\times\sqrt{0.08333}}=1.0352}\ {d=1/u=0.9660,~a=e^{(0.05-0.07)\times0.08333}=0.9983}\ {p=(0.9983-0.9660)/(1.0352-0.9660)=0.4673}\end{array}
$$  

The value of the option is 0.019.  

Figure 13.12 Three-step tree to value an American 3-month call option on a currency when the value of the currency is 0.6100, strike price is 0.6000, risk-free rate is $5\%$ , volatility is $12\%$ , and foreign risk-free rate is $7\%$ (DerivaGem output).  

At each node: Upper value $=$ Underlying Asset Price. Lower value $=$ Option Price Shading indicates where option is exercised  

![](images/2b0d285c57695c7e3b902d74f3effee544a3063e1dbd87a1de1888a986d68d59.jpg)  

# Options on Futures  

It costs nothing to take a long or a short position in a futures contract. It follows that in a risk-neutral world a futures price should have an expected growth rate of zero. (We. discuss this point in more detail in Section 18.6.) As above, we define. $p$ as the probability of an up movement in the futures price,. $u$ as the percentage up movement, and $d$ as the percentage down movement. If $F_{0}$ is the initial futures price, the expected futures price at the end of one time step of length. $\Delta t$ should also be $F_{0}$ . This means that  

$$
p F_{0}u+(1-p)F_{0}d=F_{0}
$$  

so that  

$$
p={\frac{1-d}{u-d}}
$$  

and we can use equations (13.15) to (13.18) with $a=1$  

# Example 13.3  

A futures price is currently 31 and has a volatility of $30\%$ . The risk-free rate is $5\%$ Figure 13.13 shows the output from DerivaGem for valuing a 9-month American  

Figure 13.13 Three-step tree to value an American 9-month put option on a. futures contract when the futures price is 31, strike price is 30, risk-free rate is $5\%$ and volatility is $30\%$ (DerivaGem output).  

At each node: Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised  

![](images/fe56d9c3a096078f67e1752227879fcc83ff2c966b2c549856c47accbdf99a73.jpg)  

put option with a strike price of 30 using a three-step tree. In this case,  

$$
\begin{array}{c}{{\Delta t=0.25,~u=e^{0.3\sqrt{0.25}}=1.1618}}\ {{d=1/u=1/1.1618=0.8607,~a=1,}}\ {{p=(1-0.8607)/(1.1618-0.8607)=0.4626}}\end{array}
$$  

The value of the option is 2.84.  

# SUMMARY  

This chapter has provided a first look at the valuation of options on stocks and other assets using trees. In the simple situation where movements in the price of a stock during the life of an option are governed by a one-step binomial tree, it is possible to set up a riskless portfolio consisting of a position in the stock option and a position in the stock. In a world with no arbitrage opportunities, riskless portfolios must earn the riskfree interest. This enables the stock option to be priced in terms of the stock. It is interesting to note that no assumptions are required about the actual (real-world) probabilities of up and down movements in the stock price.  

When stock price movements are governed by a multistep binomial tree, we can treat. each binomial step separately and work back from the end of the life of the option to the beginning to obtain the current value of the option. Again only no-arbitrage arguments are used, and no assumptions are required about the actual (real-world). probabilities of up and down movements in the stock price..  

A very important principle states that we can assume the world is risk-neutral when valuing an option. This chapter has shown, through both numerical examples and algebra, that no-arbitrage arguments and risk-neutral valuation are equivalent and lead to the same option prices.  

The delta of a stock option, $\Delta$ , considers the effect of a small change in the underlying stock price on the change in the option price. It is the ratio of the change in the option price to the change in the stock price. For a riskless position, an investor should buy $\Delta$ shares for each option sold. An inspection of a typical binomial tree shows that delta changes during the life of an option. This means that to hedge a particular option position, we must change our holding in the underlying stock periodically.  

Constructing binomial trees for valuing options on stock indices, currencies, and futures contracts is very similar to doing so for valuing options on stocks. In Chapter 21,. we will return to binomial trees and provide more details on how they are used in practice.  

# FURTHER READING  

Coval, J. D. and T. Shumway. "Expected Option Returns, Journal of Finance, 56, 3 (2001): 983-1009.   
Cox, J. C., S. A. Ross, and M. Rubinstein. "Option Pricing: A Simplified Approach, Journal of Financial Economics 7 (October 1979): 229-64.   
Rendleman, R., and B. Bartter. "Two State Option Pricing,' Journal of Finance 34 (1979): 1092-1110.   
Shreve, S. E. Stochastic Calculus for Finance I: The Binomial Asset Pricing Model. New York: Springer, 2005.  

# Short Concept Questions  

13.1. What is meant by risk-neutral valuation?   
13.2. Explain the no-arbitrage argument used to value an option when there is a one-step binomial tree.   
13.3. What are $u$ and $d?$ What are the formulas used to calculate them?   
13.4. How is $p$ defined? What is the formula for calclulating $p$ C.   
13.5. Explain the difficulty in calculating the discount rate that should be applied to an option's payoff in the real world.   
13.6. What is the delta of a stock option?   
13.7. What is Girsanov's theorem?   
13.8. How is the valuation of an option using a binomial tree changed when the stock is assumed to provide a continuous dividend yield?   
13.9. A stock price is currently $\$40$ It is known that at the end of 1 month it will be either $\$42$ or $\$38$ . The risk-free interest rate is $8\%$ per annum with continuous compounding. What is the value of a 1-month European call option with a strike price of $\$39$   
13.10. A stock price is currently. $\$50$ It is known that at the end of 6 months it will be either $\$45$ or $\$55$ . The risk-free interest rate is $10\%$ per annum with continuous compounding. What is the value of a 6-month European put option with a strike price of $\$50?$  

# Practice Questions  

13.11. A stock price is currently $\$100$ . Over each of the next two 6-month periods it is expected to go up by $10\%$ or down by $10\%$ . The risk-free interest rate is $8\%$ per annum with. continuous compounding. What is the value of a 1-year European call option with a strike price of $\$100$   
13.12. For the situation considered in Problem 13.11, what is the value of a 1-year European. put option with a strike price of $\$100?$ Verify that the European call and European put prices satisfy put-call parity.   
13.13. Consider a situation where stock price movements during the life of a European option are governed by a two-step binomial tree. Explain why it is not possible to set up a position in. the stock and the option that remains riskless for the whole of the life of the option.   
13.14. A stock price is currently $\$50$ It is known that at the end of 2 months it will be either $\$53$ or $\$48$ . The risk-free interest rate is $10\%$ per annum with continuous compounding. What is the value of a 2-month European call option with a strike price of $\$49?$ Use noarbitrage arguments.   
13.15. A stock price is currently $\$80$ It is known that at the end of 4 months it will be either. $\$75$ or $\$85$ . The risk-free interest rate is $5\%$ per annum with continuous compounding. What is the value of a 4-month European put option with a strike price of $\$80?$ Use noarbitrage arguments.   
13.16. A stock price is currently $\$40$ It is known that at the end of 3 months it will be either $\$45$ or $\$35$ . The risk-free rate of interest with quarterly compounding is $8\%$ per annum. Calculate the value of a 3-month European put option on the stock with an exercise  

price of $\$40$ Verify that no-arbitrage arguments and risk-neutral valuation arguments  

give the same answers.   
13.17. A stock price is currently $\$50$ Over each of the next two 3-month periods it is expected. to go up by $6\%$ or down by $5\%$ . The risk-free interest rate is $5\%$ per annum with continuous compounding. What is the value of a 6-month European call option with a strike price of $\$512$   
13.18. For the situation considered in Problem 13.17, what is the value of a 6-month European put option with a strike price of $\$51?$ Verify that the European call and European put prices satisfy put-call parity. If the put option were American, would it ever be optimal. to exercise it early at any of the nodes on the tree?.   
13.19. A stock price is currently $\$25$ . It is known that at the end of 2 months it will be either. $\$23$ or $\$27$ . The risk-free interest rate is $10\%$ per annum with continuous compounding. Suppose $S_{T}$ is the stock price at the end of 2 months. What is the value of a derivative that pays off $S_{T}^{2}$ at this time?   
13.20. Calculate $u,d.$ and $p$ when a binomial tree is constructed to value an option on a foreign. currency. The tree step size is 1 month, the domestic interest rate is $5\%$ per annum, the. foreign interest rate is $8\%$ per annum, and the volatility is $12\%$ per annum.   
13.21. The volatility of a non-dividend-paying stock whose price is. $\$78$ , is $30\%$ . The risk-free rate is $3\%$ per annum (continuously compounded) for all maturities. Calculate values for u, $d$ , and $p$ when a 2-month time step is used. What is the value a 4-month European call option with a strike price of $\$80$ given by a two-step binomial tree. Suppose a trader sells 1,000 options (10 contracts). What position in the stock is necessary to hedge the trader's position at the time of the trade?   
13.22. A stock index is currently 1,500. Its volatility is. $18\%$ . The risk-free rate is. $4\%$ per annum (continuously compounded) for all maturities and the dividend yield on the index is $2.5\%$ . Calculate values for $u,d,$ and $p$ when a 6-month time step is used. What is the value a 12-month American put option with a strike price of 1,480 given by a two-step binomial tree.   
13.23. The futures price of a commodity is $\$90$ . Use a three-step tree to value (a) a 9-month American call option with strike price $\$93$ and (b) a 9-month American put option with strike price $\$93$ . The volatility is $28\%$ and the risk-free rate (all maturities) is $3\%$ with continuous compounding.   
13.24. The current price of a non-dividend-paying biotech stock is $\$140$ with a volatility of. $25\%$ The risk-free rate is $4\%$ . For a 3-month time step: (a) What is the percentage up movement?  

(b) What is the percentage down movement? (c) What is the probability of an up movement in a risk-neutral world? (d) What is the probability of a down movement in a risk-neutral world?  

Use a two-step tree to value a 6-month European call option and a 6-month European put option. In both cases the strike price is. $\$150$  

13.25. In Problem 13.24, suppose a trader sells 10,000 European call options and the two-step tree describes the behavior of the stock. How many shares of the stock are needed to hedge the 6-month European call for the first and second 3-month period? For the second time period, consider both the case where the stock price moves up during the first period and the case where it moves down during the first period.  

13.26. A stock price is currently. $\$50$ It is known that at the end of 6 months it will be either $\$60$ or $\$42$ . The risk-free rate of interest with continuous compounding is $12\%$ per annum. Calculate the value of a 6-month European call option on the stock with an exercise price of $\$48$ . Verify that no-arbitrage arguments and risk-neutral valuation arguments give the same answers.  

13.27. A stock price is currently $\$40$ . Over each of the next two 3-month periods it is expected. to go up by $10\%$ or down by $10\%$ . The risk-free interest rate is $12\%$ per annum with continuous compounding. (a) What is the value of a 6-month European put option with a strike price of $\$42?$ (b) What is the value of a 6-month American put option with a. strike price of $\$42?$  

13.28. Using a "trial-and-error" approach, estimate how high the strike price has to be in Problem 13.27 for it to be optimal to exercise the option immediately.  

13.29. Consider a European call option on a non-dividend-paying stock where the stock price is $\$40$ , the strike price is $\$40$ , the risk-free rate is $4\%$ per annum, the volatility is. $30\%$ per annum, and the time to maturity is 6 months..  

(a) Calculate $u,d,$ and $p$ for a two-step tree.   
(b) Value the option using a two-step tree..   
(c) Verify that DerivaGem gives the same answer..   
(d) Use DerivaGem to value the option with 5, 50, 100, and 500 time steps.  

13.30. Repeat Problem 13.29 for an American put option on a futures contract. The strike price and the futures price are $\$50$ , the risk-free rate is $10\%$ , the time to maturity is 6 months,. and the volatility is $40\%$ per annum.  

13.31. Footnote 1 of this chapter shows that the correct discount rate to use for the real-world expected payoff in the case of the call option considered in Figure 13.1 is. $55.96\%$ . Show that if the option is a put rather than a call the discount rate is. $-70.4\%$ . Explain why the two real-world discount rates are so different..  

# APPENDIX DERIVATION OF THE BLACK-SCHOLES-MERTON OPTION-PRICING FORMULA FROM A BINOMIAL TREE  

One way of deriving the famous Black-Scholes-Merton result for valuing a European option on a non-dividend-paying stock is by allowing the number of time steps in a binomial tree to approach infinity.  

Suppose that a tree with. $n$ time steps is used to value a European call option with strike price $K$ and life $T.$ Each step is of length. $T/n$ . If there have been. $j$ upward movements and $n-j$ downward movements on the tree, the final stock price is $S_{0}u^{j}d^{n-j}$ , where $u$ is the proportional up movement, $d$ is the proportional down. movement, and $S_{0}$ is the initial stock price. The payoff from a European call option is then  

$$
\operatorname*{max}(S_{0}u^{j}d^{n-j}-K,0)
$$  

From the properties of the binomial distribution, the probability of exactly $j$ upward and $n-j$ downward movements is given by  

$$
{\frac{n!}{(n-j)!j!}}p^{j}(1-p)^{n-j}
$$  

It follows that the expected payoff from the call option is  

$$
\sum_{j=0}^{n}\frac{n!}{(n-j)!j!}p^{j}(1-p)^{n-j}\operatorname*{max}(S_{0}u^{j}d^{n-j}-K,0)
$$  

As the tree represents movements in a risk-neutral world, we can discount this at the risk-free rate $r$ to obtain the option price:  

$$
c=e^{-r T}\sum_{j=0}^{n}\frac{n!}{(n-j)!j!}p^{j}(1-p)^{n-j}\operatorname*{max}(S_{0}u^{j}d^{n-j}-K,0)
$$  

The terms in equation (13A.1) are nonzero when the final stock price is greater than the strike price, that is, when  

$$
S_{0}u^{j}d^{n-j}>K
$$  

or  

$$
\ln(S_{0}/K)>-j\ln(u)-(n-j)\ln(d)
$$  

Since $u=e^{\sigma{\sqrt{T/n}}}$ and $d=e^{-\sigma{\sqrt{T/n}}}$ , this condition becomes  

$$
\ln(S_{0}/K)>n\sigma{\sqrt{T/n}}-2j\sigma{\sqrt{T/n}}
$$  

or  

$$
j>{\frac{n}{2}}-{\frac{\ln(S_{0}/K)}{2\sigma{\sqrt{T/n}}}}
$$  

Equation (13A.1) can therefore be written  

$$
c=e^{-r T}{\sum_{j>\alpha}}\frac{n!}{(n-j)!j!}p^{j}(1-p)^{n-j}(S_{0}u^{j}d^{n-j}-K)
$$  

where  

$$
\alpha=\frac{n}{2}-\frac{\ln(S_{0}/K)}{2\sigma\sqrt{T/n}}
$$  

For convenience, we define  

$$
U_{1}=\sum_{j>\alpha}\frac{n!}{(n-j)!j!}p^{j}(1-p)^{n-j}u^{j}d^{n-j}
$$  

and  

$$
U_{2}=\sum_{j>\alpha}{\frac{n!}{(n-j)!j!}}p^{j}(1-p)^{n-j}
$$  

so that  

$$
c=e^{-r T}(S_{0}U_{1}-K U_{2})
$$  

Consider first $U_{2}$ . As is well known, the binomial distribution approaches a normal distribution as the number of trials approaches infinity. Specifically, when there are $n$ trials and $p$ is the probability of success, the probability distribution of the number of successes is approximately normal with mean $n p$ and standard deviation $\sqrt{n p(1-p)}$ The variable $U_{2}$ in equation (13A.3) is the probability of the number of successes being more than $\alpha$ . From the properties of the normal distribution, it follows that, for large $n$  

$$
U_{2}=N\bigg({\frac{n p-\alpha}{\sqrt{n p(1-p)}}}\bigg)
$$  

where $N$ is the cumulative probability distribution function for a standard normal variable. Substituting for $\alpha$ , we obtain  

$$
U_{2}=N{\Bigg(}{\frac{\ln(S_{0}/K)}{2\sigma{\sqrt{T}}{\sqrt{p(1-p)}}}}+{\frac{{\sqrt{n}}(p-{\frac{1}{2}})}{\sqrt{p(1-p)}}}{\Bigg)}
$$  

From equations (13.15) to (13.18), we have  

$$
p={\frac{e^{r T/n}-e^{-\sigma{\sqrt{T/n}}}}{e^{\sigma{\sqrt{T/n}}}-e^{-\sigma{\sqrt{T/n}}}}}
$$  

By expanding the exponential functions in a series, we see that, as $n$ tends to infinity, $p(1-p)$ tends to $\textstyle{\frac{1}{4}}$ and $\textstyle{\sqrt{n}}(p-{\frac{1}{2}})$ tends to  

$$
\frac{(r-\sigma^{2}/2)\sqrt{T}}{2\sigma}
$$  

so that in the limit, as. $n$ tends to infinity, equation (13A.6) becomes  

$$
U_{2}=N\bigg(\frac{\ln(S_{0}/K)+(r-\sigma^{2}/2)T}{\sigma\sqrt{T}}\bigg)
$$  

We now move on to evaluate $U_{1}$ . From equation (13A.2), we have  

$$
U_{1}=\sum_{j>\alpha}\frac{n!}{(n-j)!j!}(p u)^{j}[(1-p)d]^{n-j}
$$  

Define  

$$
p^{*}=\frac{p u}{p u+(1-p)d}
$$  

It then follows that  

$$
1-p^{*}=\frac{(1-p)d}{p u+(1-p)d}
$$  

and we can write equation (13A.8) as  

$$
U_{1}=[p u+(1-p)d]^{n}\sum_{j>\alpha}\frac{n!}{(n-j)!j!}(p^{*})^{j}(1-p^{*})^{n-j}
$$  

Since the expected rate of return in the risk-neutral world is the risk-free rate $r$ , it follows that $\hat{p}u+(1-p)d=e^{r T/n}$ and  

$$
U_{1}=e^{r T}{\sum_{j>\alpha}}{\frac{n!}{(n-j)!j!}}(p^{*})^{j}(1-p^{*})^{n-j}
$$  

This shows that. $U_{1}$ involves a binomial distribution where the probability of an up movement is $p^{*}$ rather than $p$ Approximating the binomial distribution with a normal. distribution, we obtain, similarly to equation (13A.5),.  

$$
U_{1}=e^{r T}N\bigg({\frac{n p^{*}-\alpha}{\sqrt{n p^{*}(1-p^{*})}}}\bigg)
$$  

and substituting for $\alpha$ gives, as with equation (13A.6),  

$$
U_{1}=e^{r T}N\Bigg(\frac{\ln(S_{0}/K)}{2\sigma\sqrt{T}\sqrt{p^{*}}(1-p^{*})}+\frac{\sqrt{n}(p^{*}-{\frac{1}{2}})}{\sqrt{p^{*}}(1-p^{*})}\Bigg)
$$  

Substituting for $u$ and $d$ in equation (13A.9) gives  

$$
p^{*}={\bigg(}{\frac{e^{r T/n}-e^{-\sigma{\sqrt{T/n}}}}{e^{\sigma{\sqrt{T/n}}}-e^{-\sigma{\sqrt{T/n}}}}}{\bigg)}{\bigg(}{\frac{e^{\sigma{\sqrt{T/n}}}}{e^{r T/n}}}{\bigg)}
$$  

By expanding the exponential functions in a series we see that, as $n$ tends to infinity, $p^{*}(1-p^{*})$ tends to $\frac{1}{4}$ and $\sqrt{n}(p^{*}-\frac{1}{2})$ tends to  

$$
\frac{(r+\sigma^{2}/2)\sqrt{T}}{2\sigma}
$$  

with the result that  

$$
U_{1}=e^{r T}N\bigg({\frac{\ln(S_{0}/K)+(r+\sigma^{2}/2)T}{\sigma\sqrt T}}\bigg)
$$  

From equations (13A.4), (13A.7), and (13A.10), we have  

$$
c=S_{0}N(d_{1})-K e^{-r T}N(d_{2})
$$  

where  

$$
d_{1}={\frac{\ln(S_{0}/K)+(r+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}
$$  

and  

$$
d_{2}=\frac{\ln(S_{0}/K)+(r-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}
$$  

This is the Black-Scholes-Merton formula for the valuation of a European call option. It will be discussed in Chapter 15. An alternative derivation is given in the appendix to that chapter.  

![](images/d350f62c08fc917c5ac360fc2652058c12920584688ce04a78e22d9fab9118d2.jpg)  

# Wiener Processes and Ito's Lemma  

Any variable whose value changes over time in an uncertain way is said to follow a stochastic process. Stochastic processes can be classified as discrete time or continuous time. A discrete-time stochastic process is one where the value of the variable can change. only at certain fixed points in time, whereas a continuous-time stochastic process is one where changes can take place at any time. Stochastic processes can also be classified as. continuous variable or discrete variable. In a continuous-variable process, the underlying. variable can take any value within a certain range, whereas in a discrete-variable. process, only certain discrete values are possible..  

This chapter develops a continuous-variable, continuous-time stochastic process for stock prices. A similar process is often assumed for the prices of other assets. Learning about this process is the first step to understanding the pricing of options and other more complicated derivatives. It should be noted that, in practice, we do not observe stock prices following continuous-variable, continuous-time processes. Stock prices are restricted to discrete values (e.g., multiples of a cent) and changes can be observed only when the exchange is open for trading. Nevertheless, the continuous-variable, continuous-time process proves to be a useful model for many purposes.  

Many people feel that continuous-time stochastic processes are so complicated that they should be left entirely to "rocket scientists." This is not so. The biggest hurdle to understanding these processes is the notation. Here we present a step-by-step approach aimed at getting the reader over this hurdle. We also explain an important result known as Ito's lemma that is central to the pricing of derivatives.  
