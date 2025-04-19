---
title: The T₁ -period Binomial Model
tags:
  - binomial_model
  - derivatives
  - hull_chapter_11
  - option_pricing
  - risk_neutral_valuation
aliases:
  - T1 model
  - binomial tree model
  - multi-period binomial model
key_concepts:
  - Binomial coefficients
  - Delta hedging
  - Risk-neutral probability
  - Synthetic options
  - Two-period binomial model
---

# The T₁ -period Binomial Model

### Introduction

Once we have understood the one-period binomial model,  it is very easy to extend the model to two or more periods so that derivatives with maturity in two or more periods can be examined. We will later show that using the binomial model can produce a very good approximation when it is extended to a sufficiently great number of periods. In these notes,  we consider how to extend the binomial model to more than two periods. This is relatively straightforward but requires the use of the binomial coefficients.

Reading: Hull Chapter 11.

### The Two-Period Model

The binomial model is extended by adding new branches of the tree after each node. Proceeding in the same way as with the one-period model after each node,  the price of the underlying asset either increases by a factor of $u$ or decreases by a factor $d$. 1 Thus,  whether the value of the underlying after two periods is either $(1+u)^{2}S$ if the stock has gone up in two successive periods,  $(1+d)^{2}S$ if the stock has gone down in two successive periods,  $(1+u)(1+d) S$ if the stock first went up and then went down,  or $(1+d)(1+u) S$ if the stock went down and then went up in the second period. Since $(1+u)(1+d)=$ $(1+d)(1+u)$,  the value of the stock is the same whether it first went up and then down or down and then up. Thus,  the two branches of the tree recombine after two periods,  and there are only three possible values for the

Value of the underlying after two periods. (After $7 L$ periods,  there will be $n-1$ possible ending values for the underlying asset in such a recombinant tree).

The objective is to find the value of the option or derivative at the initial node of the tree. Let's consider an example with $u=0.75$,  $d$ = -0.25,  $S=100$,  $X=100$,  and $r=0.25$ and extend it to two periods. The ending values for the underlying asset are 306.25,  131.25,  and 56.25. To value the call option at the initial node,  we first value the call at the final nodes and then work backward. The value of the call at the final nodes is simply 206.25,  31.25,  and 0 ,  that is,  the stock value minus the strike price. The value at the intermediate node then can be computed using the methods of delta hedging,  synthetic options,  or risk-neutral valuation used in the section on the one-period model. The method of risk-neutral valuation is simple because the risk-neutral probability is the same for each period as it depends only on $u$,  $d$,  and 7 that are unchanging. Taking this risk-neutral valuation method,  the value following the first up move is

$$\frac{\frac{1}{2}(206.25+31.25)}{(1+\frac{1}{4})}=95$$

And the value of the call option following a down movement in the stock is

$$\frac{\frac 12 (31.25)}{(1+\frac 14)}=\frac{25}{2}.$$

Having found the value of the option after the firstperiod. The samemethod can be used to find the value at the initial node

$$\frac{\frac{1}{2}(95+\frac{25}{2})}{(1+\frac{1}{4})}=43.$$

### Risk Neutral Valuation and State Prices

The risk-neutral valuation method also gives a very simple method of calculating the value of the option at the initial node. The risk-neutral probabiliof

The probability of the stock is ${\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{4}}$ . The probability of the stock ending with a value of 131.25 is the risk-neutral probability of an up movement followed by a down movement plus the probability of a down movement followed by an up movement. Thus the risk-neutral probability for this event is ${\frac{1}{2}}\times{\frac{1}{2}}+{\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{2}}$ . Thus the value of the call option can also be evaluated directly as
$(1+r)^{2}=\frac{25}{16}$)+\frac{4}{25}(31.25)}=q_{du}=\frac{8}{25})^2}=43.$$ .

Likewise,  the state prices are easily calculated (by dividing the risk-neutral probabilities by $(1+r)^{2}=\frac{25}{16}$ ) to be $q_{uu}=\frac{4}{25}$：$q_{ud}=q_{du}=\frac{8}{25}$ and $q_{dd}=\frac{4}{25}$ . Thus the call value could also easily be calculated as

$$\frac{4}{25}(206.25)+\frac{8}{25}(31.25)=43.$$

### American Options

As we have seen,  a European call option will have a positive time value as the lower bound for the European call is $S_{t}-X/(1+r)\geq S_{t}-X$ with inequality if $r>0$. Since American options can’t be worth less than equivalent European options,  it follows that American call options on non-dividend-paying stock will not be exercised early because selling the option will always dominate exercising it. Intuitively,  an early exercise will involve paying the strike price earlier,  and this is undesirable. However,  American put options can be exercised early because this will involve receiving the strike price earlier. The two-period binomial model can be used to illustrate this possibility.

Consider a put option in our example with a strike price $X=100$. The value of this put option at the final nodes is 0,  0,  and 43.75. Thus,  the value of the put option following an up movement in the first period is 0 as the option can never get back in the money. However,  following a down movement in the first period,  the value of the option is using the state prices

${\frac{2}{5}}(41.75)=17.5$. But early exercise of the option would give 25. Thus,  early exercise is the better alternative,  and the option must have a value of 25 if it is of the American type. At the initial node,  the option is thus worth 10 if it is an American option and 7 if it is a European option that cannot be exercised early at the end of the first period.

## Extending the model to $n>2$ periods

### Pascal's Triangle

In the one-period binomial model,  there are two possible end values,  and in the two-period binomial model,  there are three possible end values. Extrapolating,  we have that in the $n$ -period binomial model,  there are $n+1$ possible end values. The number of ways that each value is reached is determined by Pascal's triangle. Pascal's triangle is shown in Table 1 for $n=5$. Period 0 corresponds to the initial node of the binomial tree. Period 1 corresponds to the possible values after the first period,  and so on. In period 2,  there is one way to reach the two outer sides of the triangle corresponding to either two up or two down returns. There are two ways to reach the middle node. Either an up followed by a down or a down followed by an up. The numbers in Pascal's triangle are easy to calculate. Simply put,  1 is along the edges of the triangle,  and to find the other numbers,  take the two numbers above and add them together.

### Binomial Coefficients

The numbers in Pascal’s triangle are called the binomial coefficients,  and the binomial coefficients are usually written $\binom nk$ for $n,    k\geq 0$ where

$$\begin{pmatrix}n\\k\end{pmatrix}=\frac{n!}{k! (n-k)!}$$

<table>
	<tbody>
		<tr>
			<th>Period 0 1</th>
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
			<td>Period 1</td>
			<td> </td>
			<td> </td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>$\mathbf{Period}$ 2</td>
			<td> </td>
			<td>1 1</td>
			<td>1</td>
			<td> </td>
			<td>2</td>
			<td>2</td>
			<td>1</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>Period 3</td>
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
			<td>Period 5 1 T</td>
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

Is the $(k+1)$ -th number in the $(n+1)$ -th row of the triangle. Here $k!=$ $k\times k-1\times k-2\times\ldots\times 2\times 1$ and by convention 0!=1. Thus,  if $n=4$ and $k=2$ ,  then
$$\begin{pmatrix}4\\2\end{pmatrix}=\frac{4!}{2!\times 2!}=\frac{4\times 3\times 2\times 1}{(2\times 1)(2\times 1)}=\frac{24}{4}=6.$$

The binomial coefficients show us the number of ways the returns can be generated by $k$ down returns and $n-k$ up returns.

### Binomial Variable

In our binomial model,  there are two outcomes for the stock price: “up"or "down". We can treat this as a random variable and associate with each event a probability. Let $\pi~=~{\mathrm{Prob}}[$ "up-state] and probability $1-\pi=$ Prob[down-state]. The probability of having $k$ up states after $7 L$ periods is given by
$$\pi (k)=\begin{pmatrix}n\\k\end{pmatrix}\pi^k (1-\pi)^{n-k}.$$

We say this is a binomial random variable with parameter 71. For example,  say $n=4$ and there are $k=2$ “up"-states. There are ${\binom 42}=6$ ways in which this can occur. Thus,  the probability of ‘up"-states in four periods is $6\pi^{2}(1-\pi)^{2}$. We shall need to know the probability of having more than a certain number of “up"-states. Let $B_{\pi}(x)$ denote the probability that the binomial random variable with parameter 7 T is greater than $JL$ after 772 periods. That is,  the

Probability that we have $JL$ or more than $iL$ “up"-states in $TL$ periods. This is given by
$$B_\pi (x)=\sum_{k=x}^n\binom{n}{k}a^k (1-a)^{n-k}.$$

For example,  if we want to know the probability that we have two or more up states in four periods,  we have to calculate

$$\begin{pmatrix}4\\2\end{pmatrix}\pi^2 (1-\pi)^2+\begin{pmatrix}4\\3\end{pmatrix}\pi^3 (1-\pi)^1+\begin{pmatrix}4\\4\end{pmatrix}\pi^4 (1-\pi)^0=6\pi^2 (1-\pi)^2+4\pi^3 (1-\pi)+\pi^4.$$

### The distribution of the end values

Let $U$ = $( 1+ u)$,  $D$ = $( 1+ d)$ and $R$ = (1 + $r$). If there are $k$ down returns and $n - k$ up returns,  then the end value of the asset after 772 periods is $S_{n}=S_{0}U^{n - k}D^{k}$. The number of ways of attaining this ending value is given by the binomial coefficient $\binom nk$. Suppose that the probability of an "up”return is $p$ and the probability of a down return is $(1 - p)$. Then the probability of reaching the end value of $S_{n}=S_{0}U^{n - k}D^{k}$ by any one route is $p^{n - k}(1 - p)^{k}$ . Thus the probability of reaching this end value is the number of ways of reaching it $\binom nk$ times the probability $p^{n - k}(1 - p)^{k}$ of reaching it by any given route. The information is summarized in Table 2.

The expected value of the asset after $T$ periods is given by the equation

$$\sum\limits_{k=0}^n\binom{n}{k}\pi^k (1 - p)^{n - k}S_0 U^kD^{n - k}.$$

Although complicated in form,  this is a very routine computation that can be made in a spreadsheet or other software.

<table>
	<tbody>
		<tr>
			<th>$; S_n$ End Value</th>
			<th>Returns</th>
			<th>${\mathrm{Probability}}$</th>
		</tr>
		<tr>
			<td>$S_0 U^{n}D^{0}$ $n$</td>
			<td>$n$ ups and 0 downs</td>
			<td>$\pi^n (1 - p)^0$</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-1}$ ${}^{1}D^{1}$ $r 2$</td>
			<td>$n - 1$ ups and 1 downs</td>
			<td>- (1 ,  一 - $\pi )$ T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-2}D^{2}$ $r\boldsymbol{l}$</td>
			<td>$l - 2$ ups and 2 downs $\boldsymbol{r}2$ </td>
			<td>(1) $\pi$ -</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-3}D^{3}$ $m$</td>
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

Table 2: End Asset Values and Probabilities in $7 l$ -period Binomial Mode

### Pricing the Call Option

Using risk-neutral valuation,  the price of the call which matures in $T$ periods is calculated as

Where $\frac{1}{R^n}\left (\sum_{k=0}^n\binom{n}{k}\rho= (R-D)^{n-k}\max[S_0 U^kD^{n-k}-X,  0]\right)$$

Thus,  given the strike price $\rho=(R-D)/(U-D)$,  the time to maturity $7 t$,  and the risk-free interest rate Thus,  are the call value. Let $JL$ denote the time to be taken for the terminal value $7 t$,  and the risk-free interest rate $ 7$,  it is possible to be greater than the call value.

Then,  the minimum number of up branches that need to be taken for the terminal value $S_{0}U^{x}D^{n-x}$ to be greater than the strike price $X$. Then,  the above formula can be rewritten as

$$c_0=S_0\sum_{k=x}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k (1-\rho)^{n-k}\frac{U^k}{R^k}\frac{D^{n-k}}{R^{n-k}}-\frac{X}{R^n}\sum_{k=0}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k (1-\rho)^{n-k}.$$

Remember that $B_{\pi}(x)$ denotes the probability that the binomial random variable with parameter 71 has at least $2 L$ up-states after $Tl$ periods. Letting

$iL$ be the number of “up-states"such that the end value of the stock is at least the strike price $X$,  the call option price can be written more simply as

$$c_0=S_0 B_s (x)-\frac{X}{R^n}B_\rho (x)$$

Where $s=\rho U/R$. This follows since

$$\begin{aligned}
(1-s)& =\left (1-\frac{\rho U}{R}\right)=\left (1-\frac{(R-D) U}{(U-D) R}\right) \\
&=\frac{(U-D) R-(R-D) U}{(U-D) R}=\frac{D}{R}\frac{(U-R)}{(U-D)}=\frac{D}{R}\rho.
\end{aligned}$$

This is really exactly the same as in the one-period model. To see,    suppose for simplicity that the call has a positive value in the up state so $x=1$ and $n=1$. Then we have seen that the value of the call in the one-period model is
$$c_0=\frac{1}{R}\rho (US_0-X)=S_0\rho\frac{U}{R}-\frac{X}{R}\rho=sS_0-\rho\frac{X}{R}.$$

Likewise,    using the formula for replicating the call,    we have

$$\Delta=\frac{US_0-X}{(U-D) S_0}\quad\text{and}\quad B=-\frac{D}{R}\frac{US_0-X}{(U-D)}.$$

Therefore,    the value of the replicating portfolio is

$$\Delta S_0+B=\frac{US_0-X}{(U-D)}-\frac{D}{R}\frac{US_0-X}{(U-D)}$$

Which can be rewritten as

$$\Delta S_{0}+B=\frac{1}{R}\left (\frac{US_{0}(R-D)}{(U-D)}-X\frac{(R-D)}{(U-D)}\right)=\rho S_{0}\frac{U}{R}-\rho\frac{X}{R}=sS_{0}-\rho\frac{X}{R}.$$

## Example

A four-period example is illustrated in Figure 1. The example is the same as before with $u=0.75$,    $d=-0.25$,    $S=100$,    $X=100$,    and $r=0.25$ but

extended over four periods. The upper diagram shows the stock price in all possible cases,    the middle diagram the call price,    and the lower diagram the replicating portfolio of $\Delta$ units of the stock and borrowing a certain amount of the risk-free asset.

As can be seen,    the amount of stock required and the amount borrowed in order to replicate the call change over time. Thus,    the replicating portfolio is dynamic,    and it is necessary to reoptimise the portfolio every period. It is,    however,    true that the change in the portfolio required is self-financing. That is,    the proceeds from the sale of the old portfolio are just that required to buy the new portfolio at every node of the tree.

Exercise: Check that the replicating portfolio is self-financing.

## Arithmetic and geometric rates of return

This section shows an important difference between the arithmetic and the geometric mean rate of return. It is shown that the geometric mean is always less than the arithmetic mean and that the difference between the two is approximately half the variance of the return. This is an important distinction because it implies that if the rate of return is symmetrically distributed,    then the final asset value will be asymmetrically distributed. In particular,    the median of the distribution will fall below the mean of the distribution. Thus,    one should conclude that one should "expect less than the expected". An important lesson to learn in finance.

Suppose we have an asset worth 100 and for two successive periods it increases by $20\%$. Then the value at the end of the first period is 120,    and the value at the end of the second period is 144.

Now suppose that instead the asset increases in the first period by $30\%$ and in the second period by $10\%$. The average or arithmetic mean of the

Return is $20\%$. However,    the value of the asset is 130 at the end of the first period and 143 at the end of the second period. The variability of the return has meant that the asset is worth less after two periods even though the average return is the same. We can calculate the equivalent per-period return that would give the same value of 143 after two periods if there were no variance in the returns. That is the value $V$ that satisfies

$$143=100 (1+\nu)^2.$$

This value is known as the geometric mean. It is another measure of the average return over the two periods. Solving this equation gives the geometric mean as $\nu=0.195826$ or 19.58% per period? Which is less than the arithmetic rate of return per period.

There is a simple relationship between the arithmetic mean return,    the geometric mean return,    and the variance of the return. Let $\mu_{1}=\mu+\sigma$ be the rate of return in the first period and let $\mu_{2}=\mu-\sigma$ be the rate of return in the second period. Here,    the average rate of return is $=\frac{1}{2}(\mu_{1}+\mu_{2})=\mu$ and the variance of the two rates is $\sigma^{2}$. The geometric rate of return $\mu$ satisfies $(1+\nu)^{2}=(1+\mu_{1})(1+\mu_{2})$. Substituting and expanding this gives

$$1+2\nu+\nu^2=(1+\mu+\sigma)(1+\mu-\sigma)=(1+\mu)^2-\sigma^2=1+2\mu+\mu^2-\sigma^2$$

Or

$$\nu=\mu-\frac{1}{2}\sigma^{2}+\frac{1}{2}(\mu^{2}-\nu^{2}).$$

Since rates of return are typically less than one,    the square of the return is even smaller and hence the difference between two squared percentage terms is smaller still. Hence we have the approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ or

$$\mathrm{geometric~mean}\approx\mathrm{arithmetic~mean}-\frac{1}{2}\mathrm{variance}.$$

This approximation will be better the smaller the interest rates are and the smaller the variance is. In the example $\mu=0.2$ and $\sigma=0.1$ so $\frac{1}{2}\sigma^{2}=0.005$ and $\mu-\frac{1}{2}\sigma^{2}=0.1950$ which is close to the actual geometric mean of 0.1958.

## Expecting less than the expected

We can see the same difference between arithmetic and geometric rates of return in our binomial model to show that the end values for the underlying asset will be asymmetrically distributed. Consider a binomial model where the $up$ and down factors are $U=1.3$ and $D=1.1$. Thus the asset either increases by $30\%$ or by $10\%$. Suppose that each is equally likely so that the average return is $20\%$. Let the initial value of the asset be 100. Then after one period the ending values are 130 or 110 each with probability $\frac{1}{2}$ . This is a symmetric distribution centered around the average value of 120. After two periods the ending value is either 169 if there are two successive ups,    143 if there is either one up and one down or one down and one up,    or 121 if there are two downs. The probability of these three outcomes,    169,    143 and 121 are $\frac{1}{4}$,    $\frac{1}{2}$ and $\frac{1}{4}$ respectively. Thus the expected value after two periods is

$$\frac{1}{4}\times 69+\frac{1}{2}\times 143+\frac{1}{4}\times 121=144.$$

However the return is less than 144 in three of the four possible ending values. Thus after two periods the distribution of the end values is asymmetric with most of the distribution below the average value. We say that the distribution of the ending values is skewed to the right. The most likely out,    the mode,    is 143 and it is also in this case equal to the median as the ending value is equally likely to be above or below 143.

Consider the two-period model where the up and down factors are $1+\mu+\sigma$ and $1+\mu-\sigma$. The initial value of the asset is $S_0$ and both up and down

movements are equally likely. Then the expected value after two periods is

$$S_0\left (\frac{1}{4}(1+\mu+\sigma)^2+\frac{1}{2}(1+\mu+\sigma)(1+\mu-\sigma)+\frac{1}{4}(1+\mu-\sigma)^2\right)=S_0 (1+\mu)^2.$$

The median value,    however,    is

$$S_0 (1+\mu+\sigma)(1+\mu-\sigma)=S_0\left ((1+\mu)^2-\sigma^2\right)$$

So that the median is below the mean by an amount equal to the variance. Since we have already shown that $(1+\nu)^{2}=(1+\mu)^{2}-\sigma^{2}$,    the median of the end value is just $S_{0}(1+\nu)^{2}$.

The binomial model is easily extended from two to 77 periods. We have in each period the return changes by the factor $U$ or $D$. Thus ,    the returns in each period are identically and independently distributed. Let $U=1+\mu+\sigma$ and $D=1+\mu-\sigma$ as before and suppose that the probability of either return is equally likely. Then the median return (if $Tl$ is large and even) is

$$S_0\left ((1+\mu+\sigma)^{\frac{n}{2}}\right)\left ((1+\mu-\sigma)^{\frac{n}{2}}\right)=((1+\mu+\sigma)(1+\mu-\sigma))^{\frac{n}{2}}$$

As there will be roughly an equal number of up returns and down returns,    the geometric return that produces the same outcome after $Tl$ periods is $(1+g)^{n}$. Thus ,   
$$(1+\nu)^n=((1+\mu+\sigma)(1+\mu-\sigma))^\frac{n}{2}$$

Or $(1+\nu)^{2}=(1+\mu+\sigma)(1+\mu-\sigma)$,    which is exactly as before. Thus,    the same approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ applies in the $7 t.$ -period model as well. Since the geometric return gives the median value for the underlying asset,    and the arithmetic mean gives the average value,    the median is always below the average. Thus,    one should always expect to have less than the average value more than half the time.

Example:u=0.75,    $d=-0.25$,    $r=0.25$,    $x=100$

 ![500](./images/fnaAhnGefU3qDKBgLiUkRuOTfKUeeicVz.png)

Figure 1: FOUR-PERIOD BINOMIAL EXAMPLE
