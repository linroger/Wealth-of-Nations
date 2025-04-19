---
linter-yaml-title-alias: PSET 4 Solution Financial instruments
title: PSET 4 Solution Financial instruments
tags:
  - financial_instruments
  - itm_straddle
  - nikkei_options
  - short_straddle
  - volatility
aliases:
  - Barings Leeson
  - Homework 4
  - PSET 4
  - Short Straddle
key_concepts:
  - ITM straddle
  - Leeson's position
  - Profit diagram
  - Short straddle strategy
  - Volatility selling
---

---

title: PSET 4 Solution

# PSET 4 Solution Financial instruments

Financial Instruments Winter 2024 John Heaton
Solution to Homework 4

# Part 1. Barings / Leeson position on Nikkei options

(1) The strategy is called a short (almost in-the-money) straddle. Note that simply mentioning a straddle is not sufficient,  since the bet is exactly the opposite. With a short straddle,  we are betting that the price of the underlying,  at maturity,  will be close to the straddle strike price (same strike for both options),  while with a long straddle (buy 1 call and 1 put with the same strike and same maturity),  we are betting that the price of the underlying will be far from the strike price of the options. When we consider in-the-money (ITM) straddles,  we can say that we take a position on volatility. With a long ITM straddle,  we are long volatility (we benefit if the underlying price moves away - and remains away at maturity -from the strike),  while with a short ITM straddle,  we are selling volatility,  since we are betting that the price will not move much.
(2) As mentioned above,  a short ITM straddle is profitable if the price of the underlying at maturity is close to the straddle strike price; in particular,  the payoff is maximum and equal to exactly 0 when $S_{T}=K^{1}$. This means that the profit of the strategy,  if $S_{T}=K$,  is equal to the premium collected from shorting the options. The risk of such a strategy is that the writer has a virtually unlimited downside potential. Even though the maximum loss is bounded if the stock price falls a lot (the most you can lose on the short put is $-max(K-S_{T},  0)=-K$ if $S_{T}=0$),  the short call has unbounded losses if the stock price rises.
(3) Figure 1 shows the profit diagram of 1 a short straddle.
 ![500](https://storage.simpletex.cn/view/fuglkGdGVBPBzBLeqtkY54BNGYSBheHhK)
Figure 1: Profit diagram at time $T$ of the short straddle
The two points in which the profit from the straddle is equal to 0 are denoted by $S_{A}$ and $S_{B}$,  and are equal to $S_{A}=17,  780$ and $S_{B}=21,  720$ respectively.
(4) Figure 2 shows the profit diagram of 35,  000 short straddles.
As you can see,  the sole (but very relevant) difference is the unit of measure of the chart. Indeed,  the two points in which the profit from the straddle is equal to 0,  denoted by $S_{C}$ and $S_{D}$,  are equal to $S_{A}$ and $S_{B}$ of figure 1: $S_{C}=S_{A}=17,  780$ and $S_{D}=S_{B}=21,  720$. This happens because the overall strategy is just the sum of
 ![500](https://storage.simpletex.cn/view/f2wH5brOdNMwc0KIWuoRDoDkgldAtGv3i)
Figure 2: Profit diagram at time $T$ of the overall position
35,  000 single short straddles. Since at $S_{A}$ and $S_{B}$ one straddle makes no profit,  then 35,  000 straddles make $35,  000\cdot0=0$ profit.
(5) As discussed in part (1),  a short straddle is a sale of the volatility of the underlying. When we sell something (for example,  sell a stock short),  we bet that the price of the underlying goes down. In the same way,  with a short straddle (since we sell volatility),  we hope that the volatility of the underlying remains low (that is,  that the price of the underlying remains close to the straddle strike). If volatility increases,  then the chances of the underlying price being far from the strike are greater; this means that the chance of a big loss is greater as well.
When Leeson wrote the options,  the market was pricing using a lower level of volatility. Given such market implied (term to be defined soon) volatility,  the premium required to insure options’ buyers were $C$ and $P$ for a call and a put,  respectively. With an increase in volatility,  to insure the same position,  an option writer would have asked instead $c^{\prime}>c$ and $p^{\prime}>p$. To get out of his position,  Leeson would have to pay more than he originally paid. Hence,  his position would have fallen in value.
(6) The profit of a short straddle is
$$-\pi^{straddle}(S_T)=-\left[\pi^{call}(S_T)+\pi^{put}(S_T)\right]=-\pi^{call}(S_T)-\pi^{put}(S_T)$$
We know that
$$-\pi^{call}(S_T)=-\left[max\left(S_T-K,  0\right)\cdot s-c\right]=c-max\left(S_T-K,  0\right)\cdot s$$
While
$$-\pi^{put}(S_T)=-\left[max\left(K-S_T,  0\right)\cdot s-p\right]=p-max\left(K-S_T,  0\right)\cdot s$$
Where S represents the contract size. The profit of a short straddle can then be rewritten as
$$-\pi^{straddle}(S_T)=c+p-s\cdot[max\left(S_T-K,  0\right)+max\left(K-S_T,  0\right)]$$
Depending on the value of $S_{T}$,  we have
$$-\pi^{straddle}(S_T)=\left\{\begin{array}{ccc}c+p+s\cdot K-s\cdot S_T&\quad if&S_T>K\\c+p&\quad if&S_T=K\\c+p-s\cdot K+s\cdot S_T&\quad if&S_T<K\end{array}\right.$$
On February 24 th,  1995,  the Nikkei 225 was $S_{T}=17,  473$. Since $K=19,  750$,  then $S_{T}<K$,  so using formula (1),  we have a profit per straddle equal tc
$$\begin{aligned}(S_{T})&=\quad c+p-s\cdot K+s\cdot S_{T}=\\&=\quad9,  900,  000+9,  800,  000-10,  000\cdot(19,  750-17,  473)=-3,  070,  000\end{aligned}$$
Given that the total number of straddles is equal to $N=35,  000$,  the total loss on Leeson’s position amounted to JPY $3,  070,  000\cdot35,  000=107.45$ billion of Yen

## Part 2. Binomial Trees - The case of FDA drug approval

(1）According to CAPM,  the expected return on an asset $I$ is $$E(R_i)=r^f+\beta_i\cdot\begin{bmatrix}E(R_m)-r^f\end{bmatrix}$$
where $r^{f}$ is the risk-free rate,  $\beta_{I}$ is the beta of the asset,  and $\left\lfloor E(R_{m})-r^{f}\right\rfloor$ is the expected market risk premium. To apply formula (2),  we first need to compute the annually compounded risk-free rate. We know that $r_{1}\:=\:e^{r}-1$,  so we get $r_{1}^{f}=$ $e^{0.05}-1=0.0513$. The expected return of Vanda stock will therefore be $18.01\%$.
$$E(R_V)=0.0513+2\cdot0.0644=0.1801$$
(2) The value of the stock is the present value of the expected stock price at time $t=1$,  where the present value is computed using the expected return calculated in point (2.1) above and the expectation is taken using the risk-neutral probability (the probability assumed by the analysts). In formulas,  we get:
$$S_0=\frac{E^q\left[S_1\right]}{1+E[R_V]}=\frac{0.7\cdot21+0.3\cdot10}{1.1801}\approx15$$
(3) An ATM option has the strike price equal to the current spot price. In our case,  that is $K=15$.

- (a) To price the option using the replicating portfolio,  we first need to compute the option payoffs at time $t=1$. We have $c_{u}\:=\:max(S_{u}\:-\:K,  0)$ and $c_{d}=$ $max(S_{d}-K,  0)$. Using the numbers given in the directions,  we get $c_{u}=6$ and $c_{d}=0$.
	- (i) We can now compute the delta as $$\triangle_0=\frac{c_u-c_d}{S_u-S_d}=\frac{6}{11}=0.5455$$ and the amount of money borrowed as $$B_0=e^{-r}\cdot(c_u-\triangle_0\cdot S_u)=0.9512\cdot(6-0.5545\cdot21)=-5.1893$$So we can replicate the option by buying 0.5545 stocks and borrowing 5.1893 dollars at time $t=0$.
	- (ii). The time $t=0$ value of such portfolio is $V_{0}^{RP}=\triangle_{0}\cdot S_{0}+B_{0}=0.5545\cdot15-$ 5.1893=2.9933
	- (iii). The time $t=1$ payoff of the replicating portfolio are $$V_{u}^{RP}=\triangle_{0}\cdot S_{u}+B_{0}\cdot e^{r}=0.5545\cdot21-5.1893\cdot1.0513=6\\V_{d}^{RP}=\triangle_{0}\cdot S_{d}+B_{0}\cdot e^{r}=0.5545\cdot10-5.1893\cdot1.0513=0$$Which are equal to the payoffs of the option
- (b). To price the call using risk-neutral probabilities.
	- (i) We first need to compute such probability $q^*$ as $$q^*=\frac{e^r-d}{u-d}=\frac{S_0\cdot e^r-S_d}{S_u-S_d}=\frac{15\cdot1.0513-10}{21-10}=0.5244$$
	- (ii) The expected time $t=1$ price,  under the risk-neutral probability $q^*$,  will be $$E^{q^*}\left[S_1\right]=21\cdot0.5244+10\cdot\left(1-0.5244\right)=15.7681$$
	- (iii) The expected time $t=1$ price,  under the analysts’ probability 4,  is $$E^q\left[S_1\right]=21\cdot0.7+10\cdot\left(1-0.7\right)=17.70$$and is much greater than $E^{q^{*}}\left[S_{1}\right]$. Under the risk-neutral probability $q^*$ the expected return on $S$ is just the risk-free rate,  while under $q$ the expected return includes a risk premium,  thus leading to a greater expected price
Note that when we compute the expected price under the risk-neutral probability we are not assuming that agents are risk-neutral. We instead compute
The risk-neutral probability is a simplifying tool for pricing the securities. Indeed,  once we have $q^{*}$,  we have only to compute the expected value under $q^{*}$ and discount it at the risk-free rate; this is much easier than computing the beta of the security and then the expected return under the CAPM. (iv) The value of the option is given by
$$c_0=e^{-r}\cdot E^{q^*}\left[c_1\right]=0.9512\cdot[6\cdot0.5244+0\cdot(1-0.5244)]=2.9933$$
Which is the same as the one computed using the replicating portfolio.
(4). The option has the same strike price $K=15$.
- (a) If the risk-neutral probability (the one assumed by analysts) changes to $q^{‘}$ $q^{‘}=0.8$ and the beta remains equal to $\beta_{V}=2$,  the expected time $t=1$ price of the stock becomes $E^{q^{‘}}\left[S_{1}\right]=0.8\cdot21+0.2\cdot10=18.8$ and the time $t=0$ stock price becomes $$S_0’=\frac{E^{q’}\left[S_1\right]}{1+E\left[R_V\right]}=\frac{18.8}{1.1801}=15.9312$$ The risk-neutral probability,  therefore,  changes to $$q^{*^{\prime}}=\frac{S_{0}^{\prime}\cdot e^{r}-S_{d}}{S_{u}-S_{d}}=\frac{15.9312\cdot1.0513-10}{21-10}=0.6135$$ The option value will therefore be $$c_0’=e^{-r}\cdot E^{q^{*’}}[c_1]=0.9512\cdot[6\cdot0.6135]=3.5018$$ Which is greater than the value computed above in point (2.3)? The reason is that when $q$ increases,  the expected time $t=1$ price increases. With $S_0$ equal to 15,  the expected return on the stock will be greater than $18.01\%$,  therefore investors will buy the stock until,  pushing its price up,  until $E\left[R_{V}\right]=18.01\%$. As the stock price increases,  the option’s chances of ending up in the money increase as well,  which leads to an increase in the value of the option.
- (b) With the new beta,  the expected return on the stock will change to $E\left[R_{V}^{\prime}\right]=$ $0.0513+3.14\cdot0.0644=0.2535$. Given this expected (required) return on the stock,  the time $t=0$ price of the stock will therefore be $$S_0’’=\frac{E^{q’}\left[S_1\right]}{1+E\left[R_V’\right]}=\frac{18.8}{1.2535}\approx15$$ The risk-neutral probability will therefore be $$q^{*^{\prime\prime}}=\frac{S_0^{\prime\prime}\cdot e^r-S_d}{S_u-S_d}=\frac{15\cdot1.0513-10}{21-10}=0.5244=q^*$$That is equal to $q^{*}$ computed in point (2.3. B) above. This implies that the value of the option is again equal to $c_{0}$ = 2.9933. The reason why this happens is that the increase in the stock’s undiversifiable risk increases the expected return required by the investors. This leaves the price of the stock unchanged at 15 dollars. So the risk-neutral chance that the option will end up being in the money is not changed,  and the price of the option does not change. Another way of looking at it is that,  even though the expected chance that the option will be in the money has increased (which pushes the option value up),  investors now require a larger risk premium to hold the replicating portfolio (remember that one position in the replicating portfolio is $\Delta$ units of the stock),  which pushes down the value of the option.
(5) The time $t=1$ payoffs of an ATM put option are $p_{u}=max(K-S_{u},  0)$ and $p_d=$ $max(K-S_{d},  0)$. In our case,  we have $p_{u}=max(15-21,  0)=0$ and $p_{d}=max(15-$ 10,  0)=5. Using the risk-neutral probability approach,  we get
$$p_0=e^{-r}\cdot E^{q^*}\left[p_1\right]=0.9512\cdot\left[0\cdot0.5244+5\cdot(1-0.5244)\right]=2.2617$$
(6) The time $t=1$ payoffs of an ATM forward contract (that is,  with $F_{0,  T}=S_{0}$) are $f_{u}=S_{u}-F_{0,  T}=S_{u}-S_{0}$ and $f_{d}=S_{d}-S_{0}$. In our case,  we have $f_{u}=21-15=6$ and $f_{d}=15-10=5. Using the risk-neutral probability approach,   we get
$$f_0=e^{-r}\cdot E^{q^*}\left[f_1\right]=0.9512\cdot[6\cdot0.5244+5\cdot(1-0.5244)]=0.7315$$
Of course,   a much more elegant way to compute it would have required us to use the put-call parity. We know that we can replicate a payoff of a long forward contract with a delivery price equal to $K$ with a portfolio of a long call and a short put,   both having the same maturity and the same strike price as the forward contract. Indeed,
$$c-p=S_0-K\cdot e^{-r\cdot T}$$
and we know that $f_{0}=S_{0}-K\cdot e^{-r\cdot T^{\prime}}$. Therefore,   $f_{0}=c-p=2.9933-2.2617=0.7315$.