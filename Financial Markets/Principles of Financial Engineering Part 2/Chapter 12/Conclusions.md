---
tags:
  - asset_pricing
  - fundamental_theorem
  - option_markets
  - option_pricing
  - risk_management
aliases:
  - conclusions
  - findings
  - results
  - summary
key_concepts:
  - arbitrage-free dynamics
  - elementary insurance contracts
  - risk management pricing
  - state prices
  - static portfolio options
---

# 12.8 CONCLUSIONS  

We obtained some important results in this chapter. First, we showed that the notion of state prices can be made practical in environments with liquid option prices at different strikes. From here we showed how to obtain risk-neutral and forward measures and the corresponding arbitrage-free dynamics.  

Finally, as long as liquid option prices with different strikes exist, we showed how to replicate an asset using a static portfolio of options. This is true for the following reasons:.  

1. Given the option prices, we can get the prices of elementary insurance contracts. 2. But we know that every asset can be synthetically created as a portfolio of elementary insurance contracts. 3. This means that every asset can be created as a portfolio of liquid options..  

Hence, option markets not only provide close relatives of elementary insurance contracts, but also show us how to obtain generalized static synthetics for all assets in principle. Of course, the practical application depends on the availability of liquid options.  

Finally, we must emphasize that risk management and pricing are never as straightforward in. real life, since given the day, the number, and the type of liquid option, contracts change.  

# SUGGESTED READING  

The treatment of the fundamental theorem of finance in this chapter has been heuristic and introductory, although all important aspects of the theorem have been covered. The reader can get more insight into the theorem by looking at Duffie (2001), which offers an excellent treatment of asset pricing. The article by Brace et al. (1997) is an important milestone in the use of Martingale theory, and places the right emphasis on pricing and the measure of change that fits this chapter. Clewlow and Strickland (1998) provide several examples.  

# APPENDIX 12.1: SIMPLE ECONOMICS OF THE FUNDAMENTAL THEOREM  

This appendix provides a justification for the fundamental theorem from standard microeconomic.   
theory. Consider the following setup. An investor faces a decision that involves two time periods;   
the time of decision, and $T_{:}$ the relevant future date. At $T_{:}$ there are only two possible states of the.   
world $\omega^{i}$ $i=1$ , 2. The investor's subjective probabilities for these are $p^{1}$ and $p^{2}$ , respectively.  

This investor's preferences are described by a utility function $U\left(X_{t}\right)$ , where $X_{t}$ is total (real) consumption at time $t.$ Essentially, this investor is better off the higher his or her consumption:  

$$
0<{\frac{\mathrm{d}U}{\mathrm{d}X_{t}}}
$$  

But, additional consumption would incrementally have less and less positive effect:  

$$
\frac{\mathrm{d}^{2}U}{\mathrm{d}X_{t}^{2}}<0
$$  

This investor would like to maximize the expected utility associated with his or her current and future consumption:  

$$
E_{t}^{P}[U(X_{t})+\beta U(X_{T})]=U(X_{t})+\beta(p^{1}U(X_{T}^{1})+p^{2}U(X_{T}^{2}))
$$  

where $\beta$ is a constant subjective discount factor, $P$ is the subjective personal probability, and $X_{T}^{1}$ and $X_{T}^{2}$ are the consumption levels in states 1 and 2 during period $T_{:}$ respectively. The maximization of this function is subject to the investor's budget constraint at time $t$ and on the two states of the world at time. $T.$  

$$
\begin{array}{c}{q_{t}X_{t}+S_{t}h_{t}=I}\ {q_{T}^{1}X_{T}^{1}=I+h_{t}S_{T}^{1}}\ {q_{T}^{2}X_{T}^{2}=I+h_{t}S_{T}^{2}}\end{array}
$$  

$S_{t}$ is a risky asset that can be purchased at time $t.$ It has possible values $S_{T}^{1}$ and $S_{T}^{2}$ at time $T.$ Here $I$ is a known and constant income earned at times. $t$ and $T,q_{t},q_{T}^{1}$ and $q_{T}^{2}$ are the corresponding prices of the consumption good. Note that, at time $T$ there are two prices, one for each state. Finally,. $h_{t}$ is the number of $S_{t}$ purchased by the investor at time $t.$  

According to this, we are dealing with an investor who receives a constant income that needs to be split between saving and consumption in a two-period setting. The investment can be made only. by buying a desired amount of the. $S_{t}$ asset. The price of this asset is a random variable in the. model.  

The investor is risk averse and maximizes the expected utility function. There are several ways. one can solve this maximization. Our intention is to show a simple example to motivate the fundamental theorem of finance. Hence, we are not concerned with the optimal consumption itself.. Rather, we would like to obtain a relationship between "current' asset price. $S_{t}$ and the two possible values $S_{T}^{1}$ and $S_{T}^{2}$ at time $T.$ The fundamental theorem of asset pricing is about these two sets of prices. Thus, we should be able to find out how the present framework can generate the state prices. $Q^{i}$ of the fundamental theorem.  

Keeping these objectives in mind, we proceed by first substituting out $X_{t},X_{T}^{1},X_{T}^{2}$ from the equations in (12.112), and then differentiating the resulting expression with respect to the only remaining choice variable $h_{t}$ . The substitution gives  

$$
\begin{array}{r l}{\langle X_{t}\rangle+\beta(p^{1}U(X_{T}^{1})+p^{2}U(X_{T}^{2}))=}&{{}U\left(\frac{I-S_{t}h_{t}}{q_{t}}\right)+\beta\left(p^{1}U\left(\frac{I+h_{t}S_{T}^{1}}{q_{T}^{1}}\right)+p^{2}U\left(\frac{I+h_{t}S_{T}^{2}}{q_{T}^{2}}\right)\right)}\end{array}
$$  

Differentiating the right side with respect to $h_{t}$ equating to zero, and then rearranging,.  

$$
\begin{array}{r l}{U^{\prime}\left(\frac{I-S_{t}h_{t}}{q_{t}}\right)\left(\frac{S_{t}}{q_{t}}\right)=}&{\beta\left(p^{1}U^{\prime}\left(\frac{I+h_{t}S_{T}^{1}}{q_{T}^{1}}\right)\left(\frac{S_{T}^{1}}{q_{T}^{1}}\right)+p^{2}U^{\prime}\left(\frac{I+h_{t}S_{T}^{2}}{q_{T}^{2}}\right)\left(\frac{S_{T}^{2}}{q_{T}^{2}}\right)\right)}\end{array}
$$  

where $U^{\prime}(.)$ is the derivative of $U\left(x\right)$ with respect to. $^{\leftarrow}x$  

Now comes the critical point. We can rearrange the first-order condition in Eq. (12.114) to obtain  

$$
S_{t}=\beta\bigg(p^{1}\frac{U^{\prime}((I+h_{t}S_{T}^{1})/q_{T}^{1})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{1}}S_{T}^{1}+p^{2}\frac{U^{\prime}((I+h_{t}S_{T}^{2})/q_{T}^{2})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{2}}S_{T}^{2}\bigg)
$$  

Now relabel as follows:  

$$
Q^{1}=\beta p^{1}\frac{U^{\prime}((I+h_{t}S_{T}^{1})/q_{T}^{1})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{1}}
$$  

and  

$$
Q^{2}=\beta p^{2}\frac{U^{\prime}((I+h_{t}S_{T}^{2})/q_{T}^{2})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{2}}
$$  

It is clear that all elements of the right-side expressions are positive and, as a result, $Q^{i},i=1,$ 2, are positive. Substituting these $Q^{i}$ back in Eq. (12.115), we get  

$$
S_{t}=S_{T}^{1}Q^{1}+S_{T}^{2}Q^{2}
$$  

In other words, there is a linear relationship between current asset price $S_{t}$ and the future possible values $S_{T}^{1}$ and $S_{T}^{2}$ , and $\{Q^{i}\}$ is the determining factor.  

An interesting implication of the derivation shown here is the following. Even when the utility function $U(.)$ and the subjective probabilities $p^{i}$ differ among investors, general equilibrium conditions would equate the marginal rates of substitution across these differing investors and hence the $\{Q^{i}\}$ would be the same. In other words, $\{Q^{i}\}$ would be unique to all consumers even when these consumers disagree on the expected future behavior of the economy.  

# EXERCISES  

1. The following prices of the four different stocks are reported from an arbitrage-free market at time $t_{0}$  

$$
S_{t_{0}}^{1}=12.66,S_{t_{0}}^{2}=12.24,S_{t_{0}}^{3}=20.66,S_{t_{0}}^{4}=18.25
$$  

Find out the price of the 5th asset given the following possible values of these assets at time $T$  

<html><body><table><tr><td>14 3</td><td>25</td></tr><tr><td>11 10</td><td>9</td></tr><tr><td>9 23</td><td>24 22</td></tr><tr><td>8 25</td><td>10</td></tr><tr><td>6 15</td><td>25</td></tr></table></body></html>  

2. The current time is $t=1$ and our framework is the LIBOR model. We consider a situation with four states of the world. $\omega_{i}$ at time $t=3$  

Suppose $L_{i}$ is the LIBOR process with a particular tenor and $B(1,3)$ $B(1,4)$ , and $B(1,4)$ are zero-coupon bond prices with indicated maturities. The possible payoffs of these instruments in the four future states of the world are as follows:  

$$
L=6\%,6\%,4\%,4\%
$$  

$$
B(1,3)=1,1,1,1
$$  

$$
\begin{array}{c}{B(1,4)=0.9,0.92,0.95,0.96}\ {B(1,5)=0.8,0.84,0.85,0.88}\end{array}
$$  

The current prices are, respectively,  

Here the 1 is a dollar invested in LIBOR. It is like a savings account. Finally, current LIBOR is $5\%$  

a. Using Mathematica or MATLAB, determine a state price vector $q_{1},q_{2},q_{3},q_{4}$ that corresponds to $B$ (1, 3), $B(1,4)$ $B(1,5)$ $L$ as a basis.   
b. Does $q_{i}$ satisfy the required condition of positivity? Is there an arbitrage opportunity?   
c. Let $F$ be the $1\times2$ FRA rate. Can you determine its arbitrage-free value?   
d. Now let $C$ be an ATM caplet (i.e., the strike is $5\%$ ) that expires at time $t=2$ , but settlec at time $t=3$ with notional amount 1. How much is it worth?  

3. Suppose you are given the following data. The risk-free interest rate is $4\%$ . The stock price follows:  

$$
\mathrm{d}S_{t}=\mu S_{t}+\sigma S_{t}\mathrm{d}W_{t}
$$  

The percentage annual volatility is $18\%$ a year. The stock pays no dividends and the current stock price is 100.  

Using these data, you are asked to calculate the current value of a European call optior on the stock. The option has a strike price of 100 and a maturity of 200 days..  

a. Determine an appropriate time interval $\Delta$ , such that the binomial tree has five steps.. b. What would be the implied $u$ and $d$   
c.What is the implied "up' probability?   
d. Determine the binomial tree for the stock price $S_{t}$   
e. Determine the tree for the call premium. $C_{t}$  

4. Suppose the stock discussed in the previous exercise pays dividends. Assume all parameters are the same. Consider three forms of dividends paid by the firm:  

a. The stock pays a continuous, known stream of dividends at a rate of $4\%$ per time.   
b. The stock pays $5\%$ of the value of the stock at the third node. No other dividends are paid.   
c. The stock pays a $\$5$ dividend at the third node. In each case, determine the tree for the ex-dividend stock price. For the first two cases, determine the premium of the call. In what way(s) will the third type of dividend payment complicate the binomial tree?  

5. We use binomial trees to value American-style options on the British pound. Assume that the British pound is currently worth. $\$1.40$ . Volatility is $20\%$ . The current British risk-free rate is $6\%$ and the US risk-free rate is. $3\%$ . The put option has a strike price of $\$1.50$ . It expires in 200 days. a. The first issue to be settled is the role of US and British interest rates. This option is. being purchased in the United States, so the relevant risk-free rate is. $3\%$ . But British pounds can be used to earn the British risk-free rate. So this variable can be treated as a continuous rate of dividends. Or we can say that interest rate differentials are supposed to equal the expected appreciation of the currency. Taking this into account, determine a $\Delta$ such that the binomial tree has five periods.. b. Determine the implied $u$ and $d$ and the relevant probabilities. c. Determine the tree for the exchange rate. d. Determine the tree for a European put with the same characteristics.. e. Determine the price of an American-style put with the previously stated properties.  

6. Barrier options belong to one of four main categories. They can be up-and-out, down-and-. out, up-and-in, or down-and-in. In each case, there is a specified "barrier," and when the underlying asset price down- or up-crosses this barrier, the option either expires. automatically (the "out' case) or comes into life automatically (the "in' case)..  

Consider a European-style up-and-out call written on a stock with a current price of 100 and a volatility of $30\%$ . The stock pays no dividends and follows a geometric price process. The risk-free interest rate is $6\%$ and the option matures in 200 days. The strike price is 110. Finally, the barrier is 120. If the before-maturity stock price exceeds 120, the option automatically expires.  

a. Determine the relevant $u$ and $d$ and the corresponding probability.   
b. Value a call with the same characteristics but without the barrier property.   
c.Value the up-and-out call.   
d.Which option is cheaper?.  

# EXCEL EXERCISES  

7. (European Option)  

Write a VBA program to determine the initial price of a European Call and European Put option in a binomial model based on the following data:.  

Create a function to calculate the option price using the Black-Scholes formula and compare the two results. Now gradually increase the value of. $M$ and report the subsequent option prices. Use the value of u = eo and d = e-o  

8. (European Option Nonrecombining Binomial Tree)  

Write a VBA program to determine the initial price of a European Call and European Put option in a nonrecombining binomial tree model based on the following data:.  

$S(O)=100$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ $M=10$  

Create a function to calculate the option price using the Black-Scholes formula and compare the two results. Now gradually increase the value of. $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma\sqrt{\Delta t}+(r-\sigma^{2}/2)\Delta t}$ and $d=e^{-\sigma{\sqrt{\Delta t}}+(r-\sigma^{2}/2)\Delta t}$  

9. (American Option)  

Write a VBA program to determine the initial price of an American Call and American Put option in a binomial model based on the following data:  

Gradually increase the value of. $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

10. European option on dividend paying index  

Write a VBA program to determine the initial price of a European Call and European Put option in a binomial model based on the following data:.  

Create function to calculate the option price using the Black--Scholes formula and compare. Now gradually increase the value of $M$ and report the subsequent option prices.  

Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

11. European option on dividend paying index (nonrecombining binomial tree)  

Write a VBA program to determine the initial price of a European Call and European Put option in nonrecombining binomial model based on the following data:  

$S(O)=100$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ $\mathrm{div}=8\%$ $M=10$  

Create function to calculate the option price using the Black--Scholes formula and compare. Now gradually increase the value of. $M$ and report the subsequent option prices..  

Use the value of $u=e^{\sigma{\sqrt{\Delta t}}+(r-\mathrm{div}-\sigma^{2}/2)\Delta t}$ and $d=e^{-\sigma{\sqrt{\Delta t}}+(r-\mathrm{{div}}-\sigma^{2}/2)\Delta t}$  

12. (FX American Option)  

Write a VBA program to determine the initial price of an American-style options on the British pound in a binomial model based on the following data:.  

Gradually increase the value of. $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

13. FX European Option  

Write a VBA program to determine the initial price of European-style options on the British pound in the binomial model based on the following data:.  

Create a function to calculate the option price using the Black--Scholes formula and compare. Now gradually increase the value of. $M$ and report the subsequent option prices..  

Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  
