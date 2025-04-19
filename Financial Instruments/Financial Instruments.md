---
cssclasses: academia
title: Financial Instruments
tags:
  - binomial_model
  - delta_hedging
  - financial_instruments
  - option_pricing
  - replication
  - risk_neutral_valuation
  - synthetic_options
aliases:
  - Binomial Option Pricing
  - Delta Hedging Example
  - Financial Instruments Notes
key_concepts:
  - Call option payoff
  - Delta hedging
  - One period binomial model
  - Risk-free rate of return
  - Risk-neutral probabilities
  - Synthetic option creation
  - Underlying security price
---

# Financial Instruments

# One Period Binomial Model

These notes consider the one period binomial model to exactly price an option. We will consider three different methods of pricing an option: deltahedging,  creating a synthetic option using the underlying asset and the riskfree asset and calculating the risk-neutral probabilities or stochastic discount factors. All methods will be used again when we extend the binomial model beyond one period and when we consider continuous trading

Keywords: Delta-hedging,  synthetic options,  replication,  risk-neutral probabilities,  risk-neutral valuation.

Reading: Start of chapter 11 from Hull.

### Binomial Model

To value options exactly it is necessary to make specific assumptions about the determinants of the price of the underlying security. In practice this often means that a continuous stochastic process for the underlying is estimated or inferred from observations on past prices. However,  the essential aspects can all be embodied in a simple binomial model in which the underlying asset can be one of two possible values at the end of each period; to put in starkly the asset can either go up or go down in value. By considering more than one period a binomial tree is constructed,  where the price that an asset has branches out,  either upward or downward at each point in time. These binomial trees can provide a remarkably good approximation to a more complex stochastic process provided that the number of periods is reasonably large,  say above thirty.

In fact nearly all the basic principles of derivative pricing can be explained with a one or two period binomial model and this section develops the one period binomial model to study how options are exactly priced and the riskiness and elasticity of options.

## Delta Hedging

Buying a stock is a risky investment. Buying a call option on that stock is even riskier. Yet combining the stock with the option can produce an investment that is risk-free. That is it is possible to hedge a position in the stock by taking an opposite position in the call option. To create such a risk-free investment it is necessary to buy the stock and the option in exactly the right proportions. The number of units of the stock required per option is known as the $\Delta$ (Delta) of the stock and taking these positions to create a risk-free investment is known as Delta Hedging.

We will now illustrate how to calculate $\Delta$ in a simple binomial example Once $\Delta$ is known the option price itself can be calculated as any risk-free investment must in the absence of arbitrage opportunities earn the risk-free rate ofreturn.

Consider a simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. There is an "up” state and a"down” state. Let $u=0.75$ and $d=-0.25$ ,  SO that the value of the stock in three months in the up state is $100(1+u)=175$ and the value in the down state is $100(1+d)=75$ .The net growth rate of the value of the stock in the up state is $75\%$ ,  and the net growth in the value of the stock in the down state is $-25\%$

Since the stock can either rise by $75\%$ or fall by $25\%$ buying the stock is a risky investment. Now consider an at the money call option on this stock with a strike price of 100. If the stock goes up then in three months the call can be exercised for a profit of 175-100=75 and if the price of the stock goes down,  then the call will not be exercised. Thus the payoff to the call option is 75 in the up state and 0 in the down state. So the call is also risky. Suppose however,  that we consider buying $\Delta$ units of the stock and writing one call. The payoff from this portfolio is $175\Delta-75$ in the up state: the stock has gone up to 175 but the call option we have written will be exercised against us so we have an obligation of 75 The payoff in the down state is simply $75\Delta$ as the call option is not exercised in the down state. To make this portfolio risk-free it is necessary to choose $\Delta$ such that

$$175\Delta-75=75\Delta $$

so that the payoff is the same no matter whether we are in the up state or the down state. Solving for $\Delta$ gives $\Delta=3/4$ .Thus to completely hedge out the risk in the stock,  we should sell four call options for every three units of stock we buy. The payoff from such a portfolio is given in Table 1. The value in three months time is 225 in both states and hence the portfolio is riskfree. Since it is risk-free it can be valued using the risk-free rate of interest. Suppose the risk-free rate of interest is 1/4 or $25\%$ .The present value of this portfolio is 225/(1+1/4)=180 .The value of the portfolio now is simply the current value of the share,  $3\times100=300$ less $4c$ where $C$ is the price of the call option. If there are no arbitrage possibilities then the value of this portfolio must alsohave a value of 3180: $$300-4c=180$$ So solving for the call price gives $c=30$ .This shows that the Delta-hedge can be used to price the option.

The same procedure can be generalized. Let S be the value of the underlying stock,  so its terminal value is $S_{u}=(1+u)S$ in the up state and $S_{d}=(1+d)S$ in the down state. Let $K$ be the strike price of the option and $c_{u}=\operatorname*{max}[0,    S_{u}-K]$ be the value of the call option in the up state and

<table>
	<tbody>
		<tr>
			<th>${\mathbf{P}}$osition</th>
			<th>$\mathbf{Value}$ Now</th>
			<th>Value in down state</th>
			<th>${\mathrm{Value~in}}$ $up$ state</th>
		</tr>
		<tr>
			<td>4: Short Calls 1</td>
			<td>$-4 c$</td>
			<td>0</td>
			<td>300</td>
		</tr>
		<tr>
			<td>Long Shares 3 I</td>
			<td>300</td>
			<td>225</td>
			<td>525</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>$300-4 c$</td>
			<td>225</td>
			<td>225</td>
		</tr>
	</tbody>
</table>

Table 1: Risk-Free Portfolio - Example

$c_{d}=\operatorname*{max}[0,    S_{d}-K]$ is the value of the call option in the down state. Remember,  that the call option gives us the right to buy the underlying at a price of $K$，so for example in the up state when the stock is worth $S_{u}$ .the option gives the right to buy at $K$ and asset that can be sold for $S_{u}$ .Thus the option will be exercised for a profit of $S_{u}-K$ if $S_{u}-K>0$ and won't be exercised otherwise.

Now consider the $\Delta$ -hedgeportfolio thatwrites one call and buys $\Delta$ units of the underlying. The payoffs from this portfolio are given in Table 2. The value of $\Delta$ is chosen so that the portfolio is riskless,  $\Delta S_{d}-c_{d}=\Delta S_{u}-c_{u}$ i.e.

$$\Delta=\frac{c_u-c_d}{S_u-S_d}=\frac{c_u-c_d}{(u-d)S}.$$

The value of the risk-free portfoliois evaluated at the risk-free rate ofinterest 7 ,  so that

$$\Delta S-c=\frac{\Delta S_d-c_d}{(1+r)}.$$

Using the value of $\Delta$ just derived,  and substituting $(1+d)S$ for $S_{d}$ and solving for $C$ gives after some manipulation

$$c=\frac{pc_u+(1-p)c_d}{(1+r)}$$

where $p$ = $( rd) / ( ud)$ .Thus for any values of $S$，$K$，7，$UL$ and $d$ the value of the call option can be calculated from this formula.

There is a natural interpretation for $\Delta$ .It is the difference in the value of the call at maturity $c_{u}-c_{d}$ in the up state rather than the down state

<table>
	<tbody>
		<tr>
			<th>$\mathbf{P}_{\mathrm{osition}}$</th>
			<th>$\mathbf{Value}$ Now</th>
			<th>Value in down state</th>
			<th>Value in $up$ $\mathbf{state}$ T</th>
		</tr>
		<tr>
			<td>Short 上 Call</td>
			<td>$-c$</td>
			<td>$-c_d$</td>
			<td>$-c_u$</td>
		</tr>
		<tr>
			<td>Long Shares $\Delta$</td>
			<td>$\Delta S$</td>
			<td>$\Delta S_d$</td>
			<td>$\Delta uS_{u}$</td>
		</tr>
		<tr>
			<td>$0_{\mathrm{verall}}$</td>
			<td>$\Delta S-c$</td>
			<td>$\Delta S_{d}-c_{d}$</td>
			<td>$\Delta S_{u}-c_{u}$</td>
		</tr>
	</tbody>
</table>

Table 2: Risk-Free Portfolio

relative to the difference in the value of the stock $S_{u}-S_{d}$ .It tells us the change in the value of the call relative to the change in the value of the stock or how much the value of the call changes when the stock changes by a given amount. Thus $\Delta$ tells us how responsive is the call value to changes in the value of the stock. We will return to this interpretation when we consider the elasticity of an option later on.

## Synthetic Options

The idea underlying $\Delta$ -Hedging is to create a risk-free asset using a combination of the stock and the option that can be valued at the risk-free rate of interest. The risk-free asset and the underlying asset can themselves be combined to replicate the payoffs of the option itself. Such a combination is called a synthetic option.

Consider again our simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. Now consider how an at the money call option on this stock with a strike price of 100 can be synthesized. The payoff to the call option in the up state is 75 and the payoff in the down state is 0 as the option will not be exercised. Consider buying $\Delta$ units of the stock and investing $B$ units of funds at the risk-free interest rate of 1/4 .The payoff from this portfolio in the up state is $175\Delta+(1+1/4)B$ and the payoff in the down state is $75\Delta+(1+1/4)B$ .To synthesize the option we must match these payoffs to

<table>
	<tbody>
		<tr>
			<th>$\mathbf{P}$osition</th>
			<th>Value Now</th>
			<th>Value in down state</th>
			<th>${\mathrm{Value~in}}$ $up$ $\mathbf{state}$</th>
		</tr>
		<tr>
			<td>Borrow $B$</td>
			<td>-45</td>
			<td>225/4</td>
			<td>225/4</td>
		</tr>
		<tr>
			<td>Buy shares $\Delta$</td>
			<td>75</td>
			<td>225/4</td>
			<td>525/4</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>30</td>
			<td>0</td>
			<td>75</td>
		</tr>
	</tbody>
</table>

Table 3: Synthetic Option

the payoffs from the option. That is we must find $\Delta$ and $B$ to solve

$$175\Delta+(1+1/4)B=75$$

$$75\Delta+(1+1/4)B=0.$$

Solving these two equations simultaneously gives $\Delta=3/4$ and $B$ = -45 Thus the option can be replicated by borrowing 45 and buying $\frac{3}{4}$ units of the stock. Since the stock costs 100 the the cost of buying 3/4 of a unit of stock is 75. Thus the net cost of synthesizing the option is the price we pay minus the amount borrowed,  75-45=30 .Again the portfolio that replicates or synthesizes the call must have the same price as the call itself. Hence $c=30$ and we reach exactly the same conclusion as before. The payoffs are summarized in Table 3.

Again it is simple to generalize this procedure. To find the number of shares to be bought $\Delta$ and the amount to invest $B$ to synthesize the option it is only necessary to solve simultaneously the following two equations:

$$\begin{array}{c}\Delta S_u+(1+r)B=c_u\\\\\Delta S_d+(1+r)B=c_d.\end{array}$$

Solving these two equations gives

$$\Delta=\frac{c_u-c_d}{S_u-S_d}$$

And

$$B=\frac{1}{1+r}(c_d-\Delta S_d)=\frac{1}{1+r}\left(c_d-\frac{(1+d)S(c_u-c_d)}{(S_u-S_d)}\right).$$

This is illustrated graphically in Figure 1. The payoff at maturity to the call option is illustrated by the thick line. The two possible end values for the stock $S_{u}$ and $S_{d}$ are drawn on the horizontal axis. The strike price $K$ has been chosen between the two values $S_{u}$ and $S_{d}$ so that in the down state the call option expires valueless and $c_{u}=0$ .The value of the call in the up state is $c_{u}=S_{u}-k$ and this is illustrated on the vertical axis. Also drawn is the line connected the two points $(S_{d},    c_{d})$ and $(S_{u},    c_{u})$ .The slope of this line is $\Delta$ and the intercept with the vertical axis is $-\Delta S_{d}=-(1+r)B$ .It can be seen that the line is never downward sloping,  so $\Delta\geq0$ and the slope is always less than $45^{o}$ ,  so $\Delta\leq1$ 0.\1 The intercept with the vertical axis is zero or negative indicating that the portfolio that synthesizes the call option involves borrowing (selling rather than buying the risk-free asset)

The cost of synthesizing the option is the cost of the portfolio of $\Delta$ units of the shares and investing $B$ in bonds

$$c=\Delta S+B=\frac{pc_u+(1-p)c_d}{(1+r)}$$

where $p=(r-d)/(u-d)$ exactly as before

EXERCISE: Repeat for a put option.

### Risk Neutral Pricing

The previous two subsections have derived a simple expression for the price of the call option

$$c=\frac{pc_u+(1-p)c_d}{(1+r)}.$$

In this expression the value of the call optionisthepresentvalue ofaweighted average of the call at maturity,  either $Cu$ in the up state,  or $Cd$ in the down state. It is tempting to interpret $P$ in this equation as a probability. It is

 ![500](https://storage.simpletex.cn/view/fgHoIqOBAftbCMM78kC4TmVAKSq1GGfov)

Figure 1: THE $\Delta$ OF A CALL OPTION IN THE BINOMIAL MODEL

important to notice two things about this formula. First $P$ cannot be the probability of an up movement in the stock as the probabilities of stock movements were not used in the calculation of the call value. Thus the value of the call is independent of the probabilities of the up or down movements in the stock price. Second the formula for the call is based on the present value of $pc_{u}+(1-p)c_{d}$ and is therefore valued as if this payoff was risk-free. Thus the probability $P$ is a risk-adjusted probability. It is simply the future value of the state price for the up-state.

To give an interpretation to $\not P$ imagine a situation where all individuals were indifferent to risk. Such as situation is known as a risk-neutral world In such a situation all individuals would agree to value any risky prospect

simply by its expected present value. Since the formula for the value of the call is the expected present value when $p$ is interpreted as the probability of an upward movement in the stock,  $\rho$ is interpreted as a risk-neutral probability and this method of valuing the derivative is calledrisk neutral valuation. It is a simple and general principle that can be used for valuing all derivative securities.

To see how it can be used,  let's revisit our simple example again. Using the method of risk neutral valuation,  the expected value of the stock at the end of the period is $175p+75(1-p)$ ,  so the expected present value using the risk-neutral probabilities is

$$\frac{175p+75(1-p)}{(1+1/4)}.$$

This must equal the actual value of the stock which is 100. This gives one equation in one unknown,  $P$ ,  and solving gives $p=\frac{1}{2}$ .To value the call we simple use risk-neutral valuation again. The call at maturity is worth 75 in the up state and 0 in the down state,  so the expected value using the risk neutral probabilities is (1/2) 75 and the present value of this expectation is (1/2) 75/(5/4)=30

Again generalising this method,  $P$ is solved from the equation

$$S=\frac{p(1+u)S+(1-p)(1+d)S}{(1+r)}$$

to give $p=(r-d)/(u-d)$ exactly as before and this value of $P$ can then be used to compute the risk-neutral valuation for the option.

## Summary

We've considered a one period binomial model where the stock price can go either up or down by factors $(1+u)$ and $(1+d)$ .We can the use information

on the current stock price $S$ ,  the risk-free interest rate 7 and the strike price $K$ to determine the value of the option. We did this in three different ways. First by creating a riskless portfolio of the stock and the option. Second by creating a synthetic option that replicates the payoffs to the option using the underlying stock and the risk-free asset. In both cases we use an arbitrage argument that any two portfolios or assets that deliver the same payoffs must trade at the same price. Thirdly we derived the risk-neutral probability such that all assets and portfolios are valued by their expected present value. This ten allows the option to be evaluated in the same way using these riskadjusted probabilities.

The next thing to do is to allow for more than one period in the binomial model to see if the price of the option can still be calculated in a similar and similarly simple fashion.

/////////////////////////////////////////////////////////////////////////////////////////////////

# The $Tl$ -period Binomial Model

### Introduction

Once we have understood the one period binomial model it is very easy to extend the model to two or more periods so that derivatives with maturity in two or more periods can be examined. We will later show that using the binomial model can produce a very good approximation when it is extended to a sufficiently great number of periods. In these notes we consider how to extend the binomial model to more than two periods. This is relatively straightforward but requires the use of the binomial coefficients

Reading: Hull Chapter 11.

### The Two-Period Model

The binomial model is extended by adding to new branches of the tree after each node. Proceeding in the same way as with the one period model after each node the price of the underlying asset either increases by a factor of $u$ or decreases by a factor $d$ 0.\1 Thus whether the value of the underlying after two periods is either $(1+u)^{2}S$ if the stock has gone up in two successive periods. $(1+d)^{2}S$ if the stock has gone down in two successive periods,  $(1+u)(1+d)S$ if the stock first went up and then went down,  or $(1+d)(1+u)S$ if the stock went down and then went up in the second period. Since $(1+u)(1+d)=$ $(1+d)(1+u)$，the value of the stock is the same whether it frst went up and then down or down and then up. Thus the two branches of the tree recombine after two periods and there are only three possible values for the

value of the underlying after two periods. (After $7L$ periods there will be $n-1$ possible ending values for the underlying asset in such a recombinant tree)

The objective is to find the value of the option or derivative at the initial node of the tree. Let's consider an example with $u=0.75$，$d$ = -0.25 $S=100$ ,  $X=100$ and $r=0.25$ and extend it to two periods. The ending values for the underlying asset are 306.25,  131.25 and 56.25. To value the call option at the initial node we first value the call at the final nodes and then work backward. The value of the call at the final nodes is simply 206.25,  31.25 and 0，that is the stock value minus the strike price. The value at the intermediate note then can than be computed using the methods of delta hedging,  synthetic options or risk neutral valuation used in the section on the one period model. The method of risk neutral valuation is simple because the risk neutral probability is the same for each period as it depends only on $u$，$d$ and 7 that are unchanging. Taking this risk-neutral valuation method,  the value following the first up move is

$$\frac{\frac{1}{2}(206.25+31.25)}{(1+\frac{1}{4})}=95$$

And the value of the call option following a down movement in the stock is

$$\frac{\frac12(31.25)}{(1+\frac14)}=\frac{25}2.$$

Having found the value of the option after the first period,  the same method can be used to find the value at the initial node

$$\frac{\frac{1}{2}(95+\frac{25}{2})}{(1+\frac{1}{4})}=43.$$

### Risk Neutral Valuation and State Prices

The risk neutral valuation method also gives a very simple method of calculating the value of the option at the initial node. The risk neutral probability

of two up movements in the underlying stock is ${\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{4}}$ . The probability of stock ending with a value of 131.25 is the probability of an up movement followed by a down movement plus the probability of a down movement followed by an up movement. Thus the risk neutral probability for this event is ${\frac{1}{2}}\times{\frac{1}{2}}+{\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{2}}$ . Thus the value of the call option can also be evaluated directly as

$$\frac{\frac{1}{4}(206.25)+\frac{1}{2}(31.25)}{(1+\frac{1}{4})^2}=43.$$

Likewise the state prices are easily calculated (by dividing the risk neutral probabilities by $(1+r)^{2}=\frac{25}{16}$ ) to be $q_{uu}=\frac{4}{25}$：$q_{ud}=q_{du}=\frac{8}{25}$ and $q_{dd}=\frac{4}{25}$ Thus the call value could also easily be calculated as

$$\frac{4}{25}(206.25)+\frac{8}{25}(31.25)=43.$$

### American Options

As we have seen a European call option will have a positive time value as the lower bound for the European call is $S_{t}-X/(1+r)\geq S_{t}-X$ with inequality if $r>0$ .Since American options can't be worth less than equivalent European options it follows that American call options on non-dividend paying stock will not be exercised early because selling the option will always dominate exercising it. Intuitively an early exercise will involving paying the strike price earlier and this is undesirable. However,  American put options can be exercised early because this will involve receiving the strike price earlier. The two period binomial model can be used to illustrate this possibility

Consider a put option in our example with a strike price $X=100$ .The value of this put option at the final nodes is 0，0 and 43.75. Thus the value of the put option following an up movement in the first period is 0 as the option can never get back in the money. However,  following a down movement in the first period the value of the option is using the state prices

${\frac{2}{5}}(41.75)=17.5$ .But early exercise of the option would give 25. Thus early exercise is the better alternative and the option must have a value of 25 if it is of the American type. At the initial node the option is thus worth 10 if it is an American option and 7 if it is a European option that cannot be exercised early at the end of the first period.

## Extending themodel to $n>2$ periods

### Pascal's Triangle

In the one-period binomial model there are two possible end values and in the two-period binomial model there are three possible end values. Extrapolating we have that in the $7l$ -period binomial model there are $n+1$ possible end values. The number of ways that each value is reached is determined by Pascal's triangle. Pascal's triangle is shown in Table 1 for $n=5$ .Period 0 corresponds to the initialnode of the binomial tree. Period 1 corresponds to the possible values after the first period and so on. In period 2 there is one way to reach the two outer sides of the triangle corresponding to either two up or two down returns. There are two ways to reach the middle node. Either an up followed by a down or a down followed by an up. The numbers in Pascal's triangle are easy to calculate. Simply put 1 s along the edges of the triangle and to find the other numbers take the two numbers above and add them together.

### Binomial Coefficients

The numbers inPascal's triangle are called the binomial coefficients and the binomial coefficients are usually written $\binom nk$ for $n,    k\geq0$ where

$$\begin{pmatrix}n\\k\end{pmatrix}=\frac{n!}{k!(n-k)!}$$

<table>
	<tbody>
		<tr>
			<th>Period 0 11</th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th>1</th>
			<th>1</th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th> </th>
		</tr>
		<tr>
			<th>Period 1</th>
			<th> </th>
			<th> </th>
			<th>1</th>
			<th>1</th>
			<th>1</th>
			<th>1</th>
			<th>1</th>
			<th> </th>
			<th> </th>
			<th> </th>
		</tr>
		<tr>
			<th>$\mathbf{Period}$ 2</th>
			<th> </th>
			<th>1 1</th>
			<th>1</th>
			<th> </th>
			<th>2</th>
			<th>2</th>
			<th>1</th>
			<th> </th>
			<th> </th>
			<th> </th>
		</tr>
		<tr>
			<td>$\operatorname{Period}3$</td>
			<td> </td>
			<td>1</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>1</td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>Period 4</td>
			<td>1</td>
			<td>1</td>
			<td>4</td>
			<td> </td>
			<td>6</td>
			<td>6</td>
			<td>$\angle 1$</td>
			<td colspan="3">1 1</td>
		</tr>
		<tr>
			<td>Period 5 1 1</td>
			<td>1</td>
			<td>5</td>
			<td>10</td>
			<td>10</td>
			<td>0</td>
			<td>10</td>
			<td>10</td>
			<td>5</td>
			<td> </td>
			<td>1</td>
		</tr>
	</tbody>
</table>

Table 1: Pascal's Triangle

is the $(k+1)$ -th number in the $(n+1)$ -th row of the triangle. Here $k!=$ $k\times k-1\times k-2\times\ldots\times2\times1$ and by convention 0!=1 .Thus if $n=4$ and $k=2$ ,  then

$$\begin{pmatrix}4\\2\end{pmatrix}=\frac{4!}{2!\times2!}=\frac{4\times3\times2\times1}{(2\times1)(2\times1)}=\frac{24}{4}=6.$$

The binomial coefficients show us the number of ways the returns can be generated by $k$ down returns and $n-k$ up returns

### Binomial Variable

In our binomial model there are two outcomes for the stock price “up”or "down". We can treat this as a random variable and associate with each event a probability. Let $\pi~=~{\mathrm{Prob}}[$ "up-state] and probability $1-\pi=$ Prob[down-state]. The probability of having $k$ up states after $7L$ periods is given by

$$\pi(k)=\begin{pmatrix}n\\k\end{pmatrix}\pi^k(1-\pi)^{n-k}.$$

We say this is a binomial random variable with parameter 71 .For example say $n=4$ and there are $k=2$ "up"-states. The are ${\binom42}=6$ ways in which this can occur. Thus the probability of ‘up"-states in four periods is $6\pi^{2}(1-\pi)^{2}$ Weshall need toknow the probability of havingmore than a certain number of “up”-states. Let $B_{\pi}(x)$ denote the probability that the binomial random variable with parameter 7 T is greater than $X$ after 772 periods. That is the

probability that we have $JL$ or more than $iL$ “up"-states in $TL$ periods. This is given by

$$B_\pi(x)=\sum_{k=x}^n\binom{n}{k}a^k(1-a)^{n-k}.$$

For example,  if we want to know the probability that we have two or more up states in four periods we have to calculate

$$\begin{pmatrix}4\\2\end{pmatrix}\pi^2(1-\pi)^2+\begin{pmatrix}4\\3\end{pmatrix}\pi^3(1-\pi)^1+\begin{pmatrix}4\\4\end{pmatrix}\pi^4(1-\pi)^0=6\pi^2(1-\pi)^2+4\pi^3(1-\pi)+\pi^4.$$

### The distribution of the end values

Let $U$ = $( 1+ u)$，$D$ = $( 1+ d)$ and $R$ = (1 + $r)$ .If there are $k$ down returns and $n-k$ upreturns then the endvalue of the asset after 772 periods is $S_{n}=S_{0}U^{n-k}D^{k}$ .The number of ways of attaining this ending value is given by the binomial coefficient $\binom nk$ .Suppose that the probability of an "up" return is $7i$ and the probability of a down return is $(1-\pi)$ .Then the probability of reaching the end value of $S_{n}=S_{0}U^{n-k}D^{k}$ by any one route is $\pi^{n-k}(1-\pi)^{k}$ .Thus the probability of reaching this end value is the number of ways of reaching it $\binom nk$ times the probability $\pi^{n-k}(1-\pi)^{k}$ of reaching it by any given route. The information is summarized in Table 2

The expected value of the asset after $Tl$ periods is given by the equation

$$\sum\limits_{k=0}^n\binom{n}{k}\pi^k(1-\pi)^{n-k}S_0U^kD^{n-k}.$$

Although complicated in form this is very routine computation that can be madein a spreadsheet or other software

<table>
	<tbody>
		<tr>
			<th>$; S_n$ $\mathbf{End}$Value</th>
			<th>Returns</th>
			<th>$\operatorname{Probability}$</th>
		</tr>
		<tr>
			<td>$S_0 U^{n}D^{0}$ $n$</td>
			<td>$n$ ups and 0 downs</td>
			<td>$\pi^n (1-\pi)^0$</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-1}$ ${}^{1}D^{1}$ $r 2$</td>
			<td>$n-1$ ups and 1 downs</td>
			<td>- (1 ,  一 - $\pi )$ T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-2}D^{2}$ $r\boldsymbol{l}$</td>
			<td>$l-2$ ups and 2 downs $\boldsymbol{r}2$ </td>
			<td>(1) $\pi$ -</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-3}D^{3}$ $rn$</td>
			<td>$\boldsymbol{r}2$ $\imath-3$ ups and 3 downs</td>
			<td>$)\pi^{n-3}(1-\pi) 3$ 1.</td>
		</tr>
		<tr>
			<td>$S_{0}U^{3}D^{n-3}$ 3 $u$</td>
			<td>ups and $n-3$ downs 3</td>
			<td>$^{3}(1-\pi^{\prime}$ TI</td>
		</tr>
		<tr>
			<td>$S_{0}U^{2}D^{n-2}$ 2 u$_{\mathrm{I}}$</td>
			<td>2 ups and $n-2$ downs</td>
			<td>7 {:}(1 一 T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{1}D^{n-1}$ $1 u]$</td>
			<td>ups and $n-1$ downs 1</td>
			<td>7 1 (1 一 T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{0}D^{n}$ 0</td>
			<td>0 ups and $n$ downs</td>
			<td>$^{0}(1-\pi)$</td>
		</tr>
	</tbody>
</table>

Table 2: End Asset Values and Probabilities in $7l$ -period Binomial Mode

### Pricing theCall Option

Using risk-neutral valuation,  the price of the call which matures in $Tt$ periods is calculated as

$$c_0=\frac{1}{R^n}\left(\sum_{k=0}^n\binom{n}{k}\rho^k(1-\rho)^{n-k}\max[S_0U^kD^{n-k}-X,    0]\right)$$

where $\rho=(R-D)/(U-D)$ is the risk-neutral probability and $U$ and $D$ are the factors given above. Thusgiven the strike price $X$ ,  the time tomaturity $7t$ ,  the risk-free interest rate 7 ,  it is possible to calculate the callvalue

Let $JL$ denote the minimum number of up branches that need to be taken for the terminal value $S_{0}U^{x}D^{n-x}$ to be greater than the strike price $X$ .Then the above formula can bewritten as

$$c_0=S_0\sum_{k=x}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k(1-\rho)^{n-k}\frac{U^k}{R^k}\frac{D^{n-k}}{R^{n-k}}-\frac{X}{R^n}\sum_{k=0}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k(1-\rho)^{n-k}.$$

Remember that $B_{\pi}(x)$ denotes the probability that the binomial random variable with parameter 71 has at least $2L$ up-states after $Tl$ periods. Letting

$iL$ be the number of “up-states"such that the end value of the stock is at least the strike price $X$，the call option price can be written more simply as

$$c_0=S_0B_s(x)-\frac{X}{R^n}B_\rho(x)$$

where $s=\rho U/R$ .This follows since

$$\begin{aligned}
(1-s)& =\left(1-\frac{\rho U}{R}\right)=\left(1-\frac{(R-D)U}{(U-D)R}\right) \\
&=\frac{(U-D)R-(R-D)U}{(U-D)R}=\frac{D}{R}\frac{(U-R)}{(U-D)}=\frac{D}{R}\rho.
\end{aligned}$$

This is really exactly the same as in the one period model. To see Suppose for simplicity that the callhasapositive value in theup state so $x=1$ anc $n=1$ .Then we have seen that the value of the call in the one period model is
$$c_0=\frac{1}{R}\rho(US_0-X)=S_0\rho\frac{U}{R}-\frac{X}{R}\rho=sS_0-\rho\frac{X}{R}.$$

Likewise using the formula for replicating the call we have

$$\Delta=\frac{US_0-X}{(U-D)S_0}\quad\text{and}\quad B=-\frac{D}{R}\frac{US_0-X}{(U-D)}.$$

Therefore the value of the replicating portfolio is

$$\Delta S_0+B=\frac{US_0-X}{(U-D)}-\frac{D}{R}\frac{US_0-X}{(U-D)}$$

Which can be rewritten as

$$\Delta S_{0}+B=\frac{1}{R}\left(\frac{US_{0}(R-D)}{(U-D)}-X\frac{(R-D)}{(U-D)}\right)=\rho S_{0}\frac{U}{R}-\rho\frac{X}{R}=sS_{0}-\rho\frac{X}{R}.$$

## Example

Afour period example is illustrated inFigure 1. The example is the same as before with with $u=0.75$ ， $d=-0.25$ ， $S=100$ ， $X=100$ and $r=0.25$ but
extended over four periods. The upper diagrams shows the stock price in all possible cases,     the middle diagram the call price and the lower diagram the replicating portfolio of $\Delta$ units of the stock and borrowing a certain amount of the risk-free asset

As can be seen the amount of stock required and the amount borrowed in order to replicate the call change over time. Thus the replicating portfolic is dynamic and it is necessary to reoptimise the portfolio every period. It is however,     true that the change in the portfolio required is self-financing That is the proceeds from the sale of the old portfolio are just that required to buy the new portfolio at every node of the tree.

Exercise: Check that the replicating portfolio is self-financing

## Arithmetic and geometric rates of return

This section shows an important difference between the arithmetic and the geometric mean rate of return. It is shown that the geometric mean is always less than the arithmetic mean and that the difference between the two is approximately half the variance of the return. This is an important distinction because it implies that if the rate of return is symmetrically distributed then the final asset value will be asymmetrically distributed. In particular the median of the distribution willfall below the mean of the distribution. Thus one should conclude that one should "expect less than the expected". An important lesson to learn in finance

Suppose we have an asset worth 100 and for two successive periods it increases by $20\%$ .Then the value at the end of the first period is 120 and the value at the end of the second period is 144.

Now suppose that instead the asset increases in the first period by $30\%$ and in the second period by $10\%$ .The average or arithmetic mean of the
Return is $20\%$ .However the value of the asset is 130 at the end of first period and 143 at the end of the second period. The variability of the return has meant that the asset is worth less after two periods even though the average return is the same. We can calculate the equivalent per period return that would give the same value of 143 after two periods if there were no variance in the returns. That is the value $V$ that satisfies

$$143=100 (1+\nu)^2.$$

This value is known as the geometric mean. It is another measure of the averagereturn over the two periods. Solving this equation gives the geometric mean as $\nu=0.195826$ or 19.58% per period? Which is less than the arithmetic rate of return per period.

There is a simple relationship between the arithmetic mean return,     the geometric mean return and the variance of the return. Let $\mu_{1}=\mu+\sigma$ be the rate of return in the first period and let $\mu_{2}=\mu-\sigma$ be the rate of return in the second period. Here the average rate of return is $=\frac{1}{2}(\mu_{1}+\mu_{2})=\mu$ and the variance of the two rates is $\sigma^{2}$ .The geometric rate of return $\mu$ satisfies $(1+\nu)^2=(1+\mu_{1})(1+\mu_{2})$ .Substituting and expanding this gives

$$1+2\nu+\nu^2=(1+\mu+\sigma)(1+\mu-\sigma)=(1+\mu)^2-\sigma^2=1+2\mu+\mu^2-\sigma^2$$

Or

$$\nu=\mu-\frac{1}{2}\sigma^{2}+\frac{1}{2}(\mu^{2}-\nu^{2}).$$

Since rates of return are typically less than one,     the square of the return is even smaller and hence the difference between two squared percentage terms is smaller still. Hence we have the approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ or

$$\mathrm{geometric~mean}\approx\mathrm{arithmetic~mean}-\frac{1}{2}\mathrm{variance}.$$
This approximation will be better the smaller are the interest rates and the smaller is the variance. In the example $\mu=0.2$ and $\sigma=0.1$ SO $\frac{1}{2}\sigma^{2}=0.005$ and $\mu-\frac{1}{2}\sigma^{2}=0.1950$ which is close to the actual geometric mean of 0.1958.

## Expectless than the expected

We can see the same difference between arithmetic and geometric rates of return in our binomial model to show that the end values for the underlying asset will be asymmetrically distributed. Consider a binomial model where the $up$ and down factors are $U=1.3$ and $D=1.1$ .Thus the asset either increases by $30\%$ or by $10\%$ .Suppose that each is equally likely so that the average return is $20\%$ .Let the initial value of the asset be 100. Then after one period the ending values are 130 or 110 each with probability $\frac{1}{2}$ . This is a symmetric distribution centered around the average value of 120. After two periods the ending value is either 169 if there are two successive ups,     143 if there is either one up and one down or one down and one up,     or 121 if there are two downs. The probability of these three outcomes,     169,    143 and 121 are $\frac{1}{4}$ ， $\frac{1}{2}$ and $\frac{1}{4}$ respectively. Thus the expected value after two periods is

$$\frac{1}{4}\times 69+\frac{1}{2}\times 143+\frac{1}{4}\times 121=144.$$

However the return is less than 144 in three of the four possible ending values Thus after two periods the distribution of the end values is asymmetric with most of the distribution below the average value. We say that the distribution of the ending values is skewed to the right. The most likely out,     the mode,     is 143 and it is also in this case equal to the median as the ending value is equally likely to be above or below 143.

Consider the two-period model where the up and down factors are $1+\mu+\sigma$ and $1+\mu-\sigma$ ， the initial value of the asset is $S_{0}$ and both up and down
Movements are equallylikely. Then the expectedvalue after two periods is

$$S_0\left (\frac{1}{4}(1+\mu+\sigma)^2+\frac{1}{2}(1+\mu+\sigma)(1+\mu-\sigma)+\frac{1}{4}(1+\mu-\sigma)^2\right)=S_0 (1+\mu)^2.$$

The median valuehowever is

$$S_0 (1+\mu+\sigma)(1+\mu-\sigma)=S_0\left ((1+\mu)^2-\sigma^2\right)$$

So that the median is below the mean by an amount equal to the variance Since we have already shown that $(1+\nu)^{2}=(1+\mu)^{2}-\sigma^{2}$ ， the median of the end value is just $S_{0}(1+\nu)^{2}$

The binomial modelis easily extended from two to 77 periods. We have in each period the return changes by the factor $U$ or $D$ ,     thus the returns in each period are identically and independently distributed. Let $U=1+\mu+\sigma$ and $D=1+\mu-\sigma$ as before and suppose that the probability of either return is equally likely. Then the median return (if $Tl$ is large and even) is

$$S_0\left ((1+\mu+\sigma)^{\frac{n}{2}}\right)\left ((1+\mu-\sigma)^{\frac{n}{2}}\right)=((1+\mu+\sigma)(1+\mu-\sigma))^{\frac{n}{2}}$$

As there will be roughly an equal number of up returns and down returns Thegeometric return thatproduces the same outcome after $Tl$ periods is $(1+g)^{n}$ ,    thus
$$(1+\nu)^n=((1+\mu+\sigma)(1+\mu-\sigma))^\frac{n}{2}$$

Or $(1+\nu)^{2}=(1+\mu+\sigma)(1+\mu-\sigma)$ which is exactly as before. Thus the same approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ applies in the $7 t.$ -period model as well. Since the geometric return gives the median value for the underlying asset and the arithmetic mean gives the average value,     the median is always below the average. Thus one should always expect to have less than the average value more than half the time.
### Example:u=0.75,     $d=-0.25$ r=0.25,     $X=100$

 ![500](https://storage.simpletex.cn/view/fUH7qnbN24NLAVuVynt7tYKrbYxEpiV2m)

Figure 1: FOUR-PERIOD BINOMIAL EXAMPLE
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
# OPTION RISK

### Introduction

In these notes we consider the risk of an option and relate it to the standard capital asset pricing model. If we are simply interested in valuing the option,     then we can largely ignore this issue. We have seen from our notes on the oneperiod binomial model that to price an option we only need to know the price of the underlying asset. It is not necessary to know whether the underlying asset is priced fairly relative to other assets or indeed anything about other assets at all. However,     if we are interested in forming an investment portfolic that includes options or other derivatives,     then the risk and return of that portfolio will depend on the risk and return characteristics of the options. Thus we will need to know how the $\beta$ of an option relates to the $\beta$ of the underlying stock.

We can examine the issue of risk in a simple binomial model. So this is what we shall do. Most textbooks on options don’t discuss risk and therefore you will need to keep these notes for your revision.

## Risk in the binomial model

We'll use the simple example we used when discussing the one period binomial model. Suppose the price of the underlying stock is 100 and at the end of the period it has either risen to 175 or has fallen to 75. That is $u=0.75$ and $d=-0.25$ ,     so that the value of the stock after one period in the up state is $100 (1+u)=175$ and the value in the down state is $100 (1+d)=75$ .The net growth rate of the value of the stock in the up state is $75\%$ ,     and the net growth in the value of the stock in the down state is $-25\%$
We showed that in determining the price of the option,     the probability that the stock price rises of falls was irrelevant. Now however suppose that the true probability of the up state is $\pi$ = 4/5 and the probability of the down state is $(1-\pi)=1/5$ 0.\1 The expected rate of return on the stock is therefore $\mu_{S}=(4/5) 75+(1/5)(-25)=55\%$ and with an interest rate of $25\%$ the excess over the risk-free rate is $\mu_{S}-r=55-25=30\%$ .Given that the price of the call is 30,     the rate of return on the call option is (75-30)/30 or $150\%$ in the up state and $-100\%$ in the down state. Thus the expected rate of return on the call option is $\mu_{C}=100\%$ and the excess return over the risk-free rate is $\mu_{C}-r=75\%$ .Thus the excess return on the call is 2.5 times the excess return on the underlying asset. We know that this extra return will only come at the cost of extra risk.

The standard deviation of the rate of return on the stock is often simply referred to as the stock's volatility. The volatility of the stock is

$$\sigma_S=\sqrt{\frac{4}{5}(75-55)^2+\frac{1}{5}(-25-55)^2}=40\%$$

And the standard deviation of the rate of return on the call option,     or the call's volatility is

$$\sigma_C=\sqrt{\frac{4}{5}(150-100)^2+\frac{1}{5}(-100-100)^2}=100\%.$$

Thus the standard deviation of the call returns is again 2.5 times the standard deviation of the stock returns.

Now remember that $\Delta$ measures the responsiveness of the value of the call to changes in the value of the stock. In our example $\Delta=3/4$ .It is natural to measure this change in percentage terms. That is we define

$$\Omega\equiv\frac{S}{c}\Delta $$
To be the elasticity of the option,     that is the percentage change in the call value relative to a given percentage change in the stock value. In our example $S=100$ and $c=30$ ,    so that $\Omega=2.5$

This is not a coincidence. If 71 is the probability of the up state and $1-\pi$ is the probability of the down state then expected rate of return on the stock and its volatility are：

$$\mu_S=\pi u+(1-\pi) d\quad\text{and}\quad\sigma_S=\sqrt{\pi (1-\pi)}(u-d).$$

Equally the expected rate of return on the call and its volatility are

$$\mu_C=\frac{\pi c_u+(1-\pi) c_d-c}{c}\quad\mathrm{and}\quad\sigma_C=\sqrt{\pi (1-\pi)}\frac{c_u-c_d}{c}.$$

Then remembering that $\Delta$ is the change in the call price over the change in the stock price,     we have

$$\Omega\equiv\frac{S}{c}\Delta=\frac{S}{c}\frac{c_{u}-c_{d}}{(u-d) S}=\frac{c_{u}-c_{d}}{c (u-d)}.$$

It is therefore clear using the expressions above for $0 C$ and $0 S$ that

$$\sigma_C=\Omega\sigma_S.$$

Thus the ratio of the call and stock volatilities is exactly the option elasticity

Remember thatin synthesizing the calloption we used the equations

$$\Delta (1+u) S+(1+r) B=c_u$$

$$\Delta (1+d) S+(1+r) B=c_d.$$

To show that the call price is $c=\Delta S+B$ .We can therefore substitute for $B=c-\Delta S$ to write these two equations as

$$\Delta (1+u) S-c_u=(1+r)(\Delta S-c)$$

$$\Delta (1+d) S-c_{d}=(1+r)(\Delta S-c).$$
Multiplying the first equation by 71 and the second equation by $(1-\pi)$ and adding theresulting two equations gives

$$\pi (\Delta (1+u) S-c_u)+(1-\pi)(\Delta (1+d) S-c_d)=(1+r)(\Delta S-c).$$

Then dividing by $C$ ，using the definition of $\Omega$ = $\Delta ( S/ c)$ and after some rewriting gives

$$\mu_C-r=\Omega (\mu_S-r)$$

Or

$$\mu_C=r+\left (\frac{\mu_S-r}{\sigma_S}\right)\sigma_C.$$

This is of course the standard equation used to express an asset as a portfolic of the stock and the risk-free asset,     that we have seen previously in Asset Pricing and [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]. As we know the call option can be replicated by a fraction of the stock and selling the risk-free asset this should not be surprising. That is the risk and return of the call lie on somewhere on the risk-return line with intercept of 7 and slope of $(\mu_{S}-r)/\sigma_{S}$ .The elasticity $\Omega 2$ gives the position of the call along this line. Rewriting our equation on the excess return again

$$\mu_C=\Omega\mu_S+(1-\Omega)r.$$

Thus the call can be seen as the portfolio of the stock and the risk-free asset with a weight of $S 2$ attached to the stock. Since we have seen that to synthesize the call requires borrowing the risk-free asset,     we have that $\Omega>1$ and the callvolatility is always greater than the stockvolatility

This is seen in Figure 1. In the diagram the call option is always to the right of the underlying stock as it will have higher volatility and higher expected return than the underlying asset itself. It can also be seen that a call with a higher strike price will be more risky and therefore will lie further out along the risk and return line.

If the same analysis is repeated for a put option it is found that $\Delta$ is negative and $B$ is positive. This means that replicating the put option involves
 ![500](https://storage.simpletex.cn/view/f4X5qdEn8nqYtIlAagw7VHInAspIEPLf9)

Figure 1: RISK-RETURN DIAGRAM: $(\sigma,    \mu)$

Selling the underlying asset and buying the risk-free asset (investing). As the underlying asset is sold short a put option will be located on the lower arm of the risk-return diagram. The expected return is reduced because there is a future obligation from the short sale rather than a return although the obligations are still risky and therefore have a positive standard deviation. It can therefore be seen that put options are never of themselves efficient portfolios although since they will be negatively correlated with the underlying asset they can provide good hedging opportunities
We now consider the $\beta$ of a call option. The Capital AssetPricing Model shows that for any asset,     the ezcess return or risk-premium satisfies

$$\mu_S-r=\beta_S (\mu_M-r)$$

Where $\mu_{M}$ is the expected rate of return on the market portfolio and $\beta_{S}$ is the covariance of the stock's rate of return with the market divided by the variance of the rate of return on the marketportfolio

It is therefore simple to combine our excess return equation for the call and the CAPM formula to derive

$$\mu_C-r=\Omega\beta_S (\mu_M-r).$$

It can be shown that $\Omega\beta_{S}$ is the covariance of the rate of return of the call with the market divided by the variance of the rate of return of the market,     so that the beta of the call is $\beta_{C}=\Omega\beta_{S}$ .The option beta is simply the elasticity time the beta of the underlying asset. Provided that $\beta_{S}>0$ ,    since $\Omega>1$ for a call option,     it is the case that $\beta_{C}>\beta_{S}$ and the beta for the call is higher than the beta of the underlying asset. 2 This is illustrated in Figure 2 which shows the security market line which plots expected return $\mu$ against $\beta$ .The security market line intercepts the vertical axis at 7 the rate of return on the risk-free asset which is uncorrelated with the market return (as it is risk-less) and hence has a zero beta. Since $\Omega\geq 1$ the call option has a higher $\beta$ than the underlying asset and so lies to the right of the stock on the security market line. Put options on the other hand are anti-correlated with the stock,     their value goes up as the stock goes down,     so they have a negative $\beta$ and are located to the left of the risk-free asset on the security market line.
 ![500](https://storage.simpletex.cn/view/fy8nMdnXM5lnTosq8WrlOypVTIbgNSuA0)

## Figure 2: SECURITY MARKET LINE: $(\beta,    \mu)$

Let's return once again to our simple example and suppose that the expected rate of return on the market portfolio is $40\%$ .Then since the excess return on the stock is $30\%$ and the excess return on the market portfolio is $40-25=15\%$ ,    the beta of the stock is $\beta_{S}=2$ and the beta of the option is $\beta_{C}=\Omega\beta_{S}=5$ .Since $\beta>0$ and the expected rate of return on the market portfolio is greater than the risk-free rate,     the expected rate of return on the call is also greater than the risk-free rate. Remember that the expected rate of return on the call using the risk-neutral probabilities is equal to the risk-free rate. Thus the risk-neutral probability for the up state is less than the true probability,     $p<\pi$ .This simply reflects that in adjusting for the risk of the call the probability of the high rate of return is shaded downward to
Refect an aversion to risk. In our example the risk-neutral probability is 1/2 and the actual probability of the up state is 4/5

## Summary

These notes have provided a connection between option pricing and standard models of [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] and the Capital Asset Pricing Model (CAPM). The connection is provided by the option elasticity $S 2$ .We have seen previously that $\Delta$ measures how much of the stock to buy to create a riskless hedge or to replicate the option. The option elasticity,     $\leq 2$ is a proportionate measure of $\Delta$ ， $\Omega=S\Delta/c$ .The elasticity $S 2$ ：therefore measures the proportion of the portfolio placed in the underlying asset in order to replicate the option. It is therefore a portfolio weight rather a quantity of stock bought. The elasticity of the call option will be no less than one since to replicate the call option it will be necessary to borrow,     that is go short in the risk-free asset,     to fund the acquisition of the underlying asset. The elasticity also can be combined with the beta of the stock,     $\beta_{S}$ to calculate the beta of the call option $\beta_{C}=\Omega\beta_{C}$ Since $\Omega\geq 1$ the call option will be a more aggressive asset that the underlying stock.
////////////////////////////////////////////////////////////////////////////////////
#  [[Exotic Options]] 

These notes describe the payoffs to some of the so-called erotic options. There are a variety of different types of exotic options. Some of these options are path dependent so that the value of the option depends on the previous values of the underlying as well as the current price of the underlying

Keywords: Digital options,     Barrier options,     Path dependent options,     Lookback options,     Asian options.

Reading Hull Chapter 22 [Just read about the different types exotic options and their payoffs. Ignore the equations describing how they are priced for the moment.]

### Introduction

American and European puts and calls are sometimes referred to as plain vanilla options. There are however a wide variety of other types of options that are traded. These are sometimes referred to as exotic options. In the past most exotic options were traded in over the counter markets rather than exchanges,     but more recently these alternative option types can be found on exchange markets too. The variety and types of options that are available are really only limited by imagination. As long as the payoff can be well specified,     it can depend on any property of the price of the underlying asset. The following list just gives a few examples

## Digital Options

One simple type is the digital or binary option. The payoff to a digital option depends on whether the price of the underlying asset at maturity is greater
Or less than the strike price. Thus for a digital call option the payoff at maturity is:
$$c_T^b=\left\{\begin{array}{ll}0&\text{if}S_T\leq X\\1&\text{if}S_T>X\end{array}\right.$$

And the payoff at maturity to a digital put option is

$$p_T^b=\left\{\begin{array}{ll}1&\text{if}S_T\leq X\\0&\text{if}S_T>X.\end{array}\right.$$

### Range Forward Contract

A range forward contract specifies a band $[X_{2},     X_{1}]$ .If the price of the underlying at maturity is within the band then the holder is obliged to buy the asset at its current price. If the price of the underlying at maturity is below $X_{2}$ then the holder has to buy at $X_{2}$ and if the price of the underlying at maturity is above $X_{1}$ then the holder has to buy at $X_{1}$ .The range forward is designed so that the initialvalue of the contract is zero and therefore similar to a forward contract. It is equivalent to a combination of a long call option with a strike price of $X_{1}$ and a written put option with a strike price of $X_{2}$ ，where the strike prices are chosen so that the put and the call have the same prices. The payoff at maturity to a range forward contract is $\operatorname*{max}[S_{T}-X_{1},     0]-\operatorname*{max}[X_{2}-S_{T},     0]$

### Break Forward

A break forward contract specifies a delivery price $K$ and a break price $B$ at which the forward price can be broken. Thus at the maturity date,     the break price will be paid on a long forward position if $-B>S_{T}-K$ .For example if the break price is $\$10$ and the delivery price is S 100,     the payoff to the long forward position is $S_{T}-100$ .If $S_{T}<90$ ,     there will be a loss of more than S 10 and it will be worth while to pay the break price of $\$10$ .The payof
At maturity is therefore $\operatorname*{max}[S_{T}-100,    -10]=\operatorname*{max}[S_{T}-90,    0]-10$ .This then is just like a call option with a strike price of S 90 but where a payment of $\$10$ is paid at maturity. Since the break forward costs nothing when it is initiated,     it is essentially a deferred payment option,     where the payment of the initial cost of the option is deferred until maturity. Suppose that the interest rate until maturity is $\frac{1}{9}$ ,     then in our example a call option with a strike price of $\$90$ which costs $\$9$ us equivalent to a long break forward with a delivery price of $\$100$ and break price of 810 .In general letting 7 denote the interest to maturity and $C_{t}$ the current price of the call option with a strike price $X$ ,     then the call option is equivalent to a long position in a break forward contract with delivery price $X+(1+r) c_{t}$ and break price $(1+r) c_{t}$

## Rainbow Options

It is possible to write options on more than one underlying asset. Such options are called rainbow options. For example a put option may specify that you have the option to deliver one from a range of different assets. Clearly if the exercise price is the same for all assets specified,     and if you decide to exercise your option to sell,     you will choose to deliver that asset with the lowest current price. Thus if there are two assets specified and their prices are $S^{\mathrm{I}}$ and $S^{2}$ ， then the intrinsic value of the put option is

$$x\text{Intrinsic value}=\left\{\begin{array}{ll}X-\min[S^1,     S^2]&\text{if}\min[S^1,     S^2]\leq X\\0&\text{if}\min[S^1,     S^2]>X.\end{array}\right.$$

## "As-you-like-it" Options

This is an option where the holder can decide at a specific time whether the option is a put or a call option. Suppose that the where the decision must be made is $t$ . The value of the option at this time is $\max[c_{t},     p_{t}]$ .If the as-you-like-option offers the choice between a European put and a European
Call with the same strike price and same maturity date $T$ ,    then the put call parity condition can be used and

$$\max[c_t,     p_t]=\max\left[c_t,     c_t+\frac{X}{(1+r)}-S_t\right]=c_t+\max\left[0,    \frac{X}{(1+r)}-S_t\right]$$

Where 7 is the risk-free interest rate between $t$ and thematurity date $T$ .The as-you-like-it option therefore consist of aportfolio of a call option with strike price $X$ and maturity at date $T$ and a put option with strike price $\frac{X}{(1+r)}$ and maturity at date $t$

## Barrier Options

Barrier options have a payoff that depends on whether the underlying asset reaches a certain level,     the barrier,     prior to maturity. There are two main varieties of barrier option. The knock-in only pays out if the price of the underlying reaches the barrier and the knock-out only pays out if the underlying does not reach the barrier. These can be further classified by whether the barrier is set above or below the initial value of the underlying asset. If the barrier is above the initial value of the underlying,     it is said to be an up option. If the barrier is below the initial value of the underlying asset,     it is said tobe a down option. The payoff at maturity for a down-and-out call option is
$$c_T^{down-out}=\left\{\begin{array}{lll}c_T&\text{if}\:S_t>B&\text{for all}\: t\leq T\\0&\text{if}\:S_t<B&\text{for any}\: t\leq T\end{array}\right.$$

Where $B$ is the barrier and $CT$ is the value of the plain vanilla call option. Clearly if you own both a down and out call option together with a down an in call option on the same underlying with the same barrier,     strike prices and maturity,     then you have a plain vanilla call option. So for calls and puts and down and up options:

$$\mathrm{vanilla}=\mathrm{in}+\mathrm{out}.$$
Barrier option sometimes specify a double barrier with an upper and lower limit. Sometimes the barrier changes over time. Sometimes a rebate is paid if the barrier is hit. Some options become barrier options if a particulan value,     usually the strike price,     for the underlying is reached

### Lookback Options

Lookback options have a payof that depends on the maximum or minimum value that the underlying asset reaches during the lifetime of the option. The payoff to maturity of a European-style lookback call is $S_{T}-S_{min}$ where $S_{min}$ is the minimum value that the underlying achieves over the option’slifetime The payoff to maturity of a European-style lookback put is $S_{max}-S_{T}$ where $S_{max}$ is the maximum value that the underlying achieves over the option’s lifetime. Note that if you hold both a lookback put and a lookback call your payoff is $S_{max}-S_{min}$ . It is like you bought when the price was lowest and sold when the price was highest. Of course such sweet deals are likely to be costly.

## Asian Options

An Asian option has a payoff that depends on the average price of the underlying asset from its starting date. Thus the intrinsic value of an average price Asian call option is $\operatorname*{max}[0,     S_{ave}-X]$ ，where $S_{ave}$ is the average value of the asset from the start of the option to the current date. Another type of Asian option is the average strike price type,     where the strike price is the average value. In this case the intrinsic value of the call is $\operatorname*{max}[0,     S_{t}-S_{ave}]$ and the intrinsic value of the put is $\operatorname*{max}[S_{ave}-S_{t},     0]$