---
linter-yaml-title-alias: Binomial Option Pricing
title: Binomial Option Pricing
tags:
  - american_option
  - binomial_model
  - european_option
  - option_pricing
  - stock_option
aliases:
  - Binomial Pricing
  - CRR model
key_concepts:
  - Binomial option pricing model
  - European and American options
  - Market maker synthetic options
  - No-arbitrage option price
  - Underlying asset price movement
---

- **[[Teaching Note 4-Multiperiod Binomial Trees]]**
	- [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing]]
	- [[Binomial Tree Steps]]
	- [[Calculate Stock Prices at Different Nodes]]
	- [[Options Strategies Construction]]
	- [[Teaching Note 4-Multiperiod Binomial Trees]]
	- [[Financial Instruments/Lecture Notes/Teaching Note 4-Multiperiod Binomial Trees/The Pricing of Options and Corporate Liabilities]]

# [[Financial Instruments/Binomial Option Pricing Model|Binomial Option Pricing]]
## BINOMIAL OPTION PRICING: BASIC CONCEPTS I

In this chapter we discuss the binomial option pricing model,  with which we can compute the price of an option,  given the characteristics of the stock or other underlying asset.

The binomial option pricing model assumes that,  over a period of time,  the price of the underlying asset can move up or down only by a specified amount—that is,  the asset price follows a binomial distribution. Given this assumption,  it is possible to determine a no-arbitrage price for the option. Surprisingly,  this approach,  which appears at first glance to be overly simplistic,  can be used to price options,  and it conveys much of the intuition underlying more complex (and seemingly more realistic) option pricing models. It is hard to overstate the value of thoroughly understanding the binomial approach to pricing options.

Because of its usefulness,  we devote this chapter to binomial option pricing. In this chapter,  we will see how the binomial model works and use it to price both European and American call and put options on stocks,  currencies,  and futures contracts. As part of the pricing analysis,  we will also see how market-makers can create options synthetically using the underlying asset and risk-free bonds.

## 1. A ONE-PERIOD BINOMIAL TREE

Binomial pricing achieves its simplicity by making a very strong assumption about the stock price: At any point in time,  the stock price can change to either an up value or a down value. In-between,  greater or lesser values are not permitted. The restriction to two possible prices is why the method is called "binomial." The appeal of binomial pricing is that it displays the logic of option pricing in a simple setting,  using only algebra to price options.

The binomial approach to pricing was first used by Sharpe (1978) as an intuitive way to explain option pricing. Binomial pricing was developed more formally by Cox et al. (1979) and Rendleman and Bartter (1979),  who showed how to implement the model,  demonstrated the link between the binomial model and the Black-Scholes model,  and showed that the method provides a tractable way to price options for which early exercise may be optimal. The binomial model is often referred to as the "Cox-Ross-Rubinstein pricing model."

Binomial tree depicting the movement of XYZ stock over 1 year. The current stock price is$41.

We begin with a simple example. Consider a European call option on the stock of XYZ,  with a$40 strike and 1 year to expiration. XYZ does not pay dividends and its current price is$41. The continuously compounded risk-free interest rate is 8%. We wish to determine the option price.

Since the stock's return over the next year is uncertain,  the option could expire either in-the-money or out-of-the-money,  depending upon whether the stock price is more or less than$40. Intuitively,  the valuation for the option should take into account both possibilities and assign values in each case. If the option expires out-of-the-money,  its value is zero. If the option expires in-the-money,  its value will depend upon how far in-the-money it is. To price the option,  then,  we need to characterize the uncertainty about the stock price at expiration.

Figure 1 represents the evolution of the stock price: Today the price is$41,  and in 1 year the price can be either$60 or$30. This depiction of possible stock prices is called a binomial tree. We will see shortly how to construct a binomial tree like that in Figure 1.

For now,  you should take the tree as given as we work through an option pricing example. Be aware that if we had started with a different tree,  the numbers that follow,  including the price,  would all be different.

---
## 1. A ONE-PERIOD BINOMIAL TREE

Binomial pricing achieves its simplicity by making a very strong assumption about the stock price: At any point in time,  the stock price can change to either an up value or a down value. In-between,  greater or lesser values are not permitted. The restriction to two possible prices is why the method is called "binomial." The appeal of binomial pricing is that it displays the logic of option pricing in a simple setting,  using only algebra to price options.

The binomial approach to pricing was first used by Sharpe (1978) as an intuitive way to explain option pricing. Binomial pricing was developed more formally by Cox et al. (1979) and Rendleman and Bartter (1979),  who showed how to implement the model,  demonstrated the link between the binomial model and the Black-Scholes model,  and showed that the method provides a tractable way to price options for which early exercise may be optimal. The binomial model is often referred to as the "Cox-Ross-Rubinstein pricing model."

Binomial tree depicting the movement of XYZ stock over 1 year. The current stock price is$S_{0}$.

We begin with a simple example. Consider an **in the money European call option** on the stock of XYZ,  with a$K$strike and 1 year to expiration. XYZ does not pay dividends ($\delta=0$) and its current price is$S_{0}$>$K$. The continuously compounded risk-free interest rate is$r$%. We wish to determine the option price.

Since the stock's return over the next year is uncertain,  the option could expire either in-the-money or out-of-the-money,  depending upon whether the stock price is more or less than$K$. Intuitively,  the valuation for the option should take into account both possibilities and assign values in each case. If the option expires out-of-the-money,  its value is zero. If the option expires in-the-money,  its value will depend upon how far in-the-money it is. To price the option,  then,  we need to characterize the uncertainty about the stock price at expiration.

Figure 1 represents the evolution of the stock price: Today the price is$S_0$,  and in 1 year the price can be either$S_u$or$S_d$. This depiction of possible stock prices is called a binomial tree.

## COMPUTING THE OPTION PRICE

Now we compute the price of our K-strike 1-year call. Consider two portfolios:

Portfolio A. Buy one call option. The cost of this is the call premium,  which is what we are trying to determine.
Portfolio B. Buy$\Delta$of a share of XYZ and borrow$B$at the risk-free rate

This position costs$\Delta *S_{0} +B$

Now we compare the payoffs to the two portfolios 1 year from now. Since the stock can take on only two values,  we can easily compute the value of each portfolio at each possible stock price.

For Portfolio A,  the time 1 payoff is$max[0,  S_1 − K]$:

**Stock Price in 1 Year ($S_1$)**

|                       |$S_d$        |$S_u$          |
|-----------------------|-------------|--------------|
| **Payoff**  |0         |$max[0,  S_1 − K]$          |

**Stock Price in 1 Year ($S_1$)**

|                       |$S_D$        |$S_U$          |
|-----------------------|-------------|--------------|
| Written call          |$0          |${} K-S_{U}<0 {}$        |
|$\Delta$Purchased shares  |$\Delta*S_D$        |$\Delta*S_U$          |
| Repay loan of$B$|$-Be^{rT}$        |$-Be^{rT}$        |
| **Total payoff**      | **$0**      | **$0**       |

In computing the payoff for Portfolio B,  we assume that we sell the shares at the market price and that we repay the borrowed amount,  plus interest ($-Be^{rT}$). Thus we have

**Stock Price in 1 Year$(S_1$)**

|  |$S_D$|$S_U$|
| ---- | ---- | ---- |
| Purchased call |$0 |${} S_U-K>0 {}$|
|$\Delta$Short-sold shares | -$\Delta*S_D$| -$\Delta*S_U$|
| Sell T-bill |$+Be^{rT}$|$+Be^{rT}$|
| **Total payoff** | **$0** | **$0** |

---

## COMPUTING THE OPTION PRICE

Now we compute the price of our 40-strike 1-year call. Consider two portfolios:

Portfolio A. Buy one call option. The cost of this is the call premium,  which is what we are trying to determine.
Portfolio B. Buy 2/3 of a share of XYZ and borrow$18.462 at the risk-free rate.

This position costs$2/3 x \$41 - \$18.462 = \$8.87⚡

Now we compare the payoffs to the two portfolios 1 year from now. Since the stock can take on only two values,  we can easily compute the value of each portfolio at each possible stock price.

For Portfolio A,  the time 1 payoff is$max[0,  S_1 − \$40]$$:

**Stock Price in 1 Year ($S_1$)**

|                       |$30         |$60          |
|-----------------------|-------------|--------------|
| **Payoff**  |$0         |$20          |

**Stock Price in 1 Year (S_1)**

|                       |$30         |$60          |
|-----------------------|-------------|--------------|
| Written call          |$0          | -$20         |
| 2/3 Purchased shares  |$20         |$40          |
| Repay loan of$18.462 | -$20        | -$20         |
| **Total payoff**      | **$0**      | **$0**       |

In computing the payoff for Portfolio B,  we assume that we sell the shares at the market price and that we repay the borrowed amount,  plus interest ($18.462 × e0.08 =$20). Thus we have

**Stock Price in 1 Year$(S_1$)**

|                       |$30         |$60          |
|-----------------------|-------------|--------------|
| Purchased call        |$0          |$20          |
| 2/3 Short-sold shares | -$20        | -$40         |
| Sell T-bill           |$20         |$20          |
| **Total payoff**      | **$0**      | **$0**       |

---

Note that Portfolios A and B have the same payoff: Zero if the stock price goes down,  in which case the option is out-of-the-money,  and \$20 if the stock price goes up. Therefore,  both portfolios should have the same cost. 

- Since Portfolio B costs \$8.871,  then given our assumptions,  *the price of one option must be$8.871*. 
- Portfolio B is a synthetic call,  mimicking the payoff to a call by buying shares and borrowing.

The idea that positions that have the same payoff should have the same cost is called the **law of one price**. This example uses the law of one price to determine the option price.

We will see shortly that there is an arbitrage opportunity if the law of one price is violated.

The call option in the example is replicated by holding 2/3 shares,  which implies that one option has the risk of 2/3 shares. The value 2/3 is the *delta* () of the option: the number of shares that replicates the option payoff. Delta is a key concept,  and we will say much more about it later.

Finally,  we can say something about the expected return on the option. Suppose XYZ has a positive risk premium (i.e.,  the expected return on XYZ is greater than the risk-free rate). Since we create the synthetic call by borrowing to buy the stock,  the call is equivalent to a leveraged position in the stock,  and therefore the call will have an expected return greater than that on the stock. The option elasticity measures the amount of leverage implicit in the option.

## THE BINOMIAL SOLUTION

In the preceding example,  how did we know that buying 2/3 of a share of stock and borrowing$18.462 would replicate a call option?

We have two instruments to use in replicating a call option: shares of stock and a position in bonds (i.e.,  borrowing or lending). To find the replicating portfolio,  we need to find a combination of stock and bonds such that the portfolio mimics the option.

To be specific,  we wish to find a portfolio consisting of  shares of stock and a dollar amount B in lending,  such that the portfolio imitates the option whether the stock rises or falls. We will suppose that the stock has a continuous dividend yield of δ,  which we reinvest in the stock. Thus,  if you buy one share at time t,  at time t + h you will have eδh shares.

The up and down movements of the stock price reflect the *ex-dividend* price.

Let S be the stock price today. We can write the stock price as uS when the stock goes up and as dS when the price goes down. The stock price tree is then:

```tikz
\usepackage{tikz-cd}
\usetikzlibrary{positioning}
\begin{document}
\begin{tikzpicture}[>=stealth,  node distance=2cm]
    \node (S) at (0, 0) {$S$};
    \node (uS) [above right=of S] {$uS$};
    \node (dS) [below right=of S] {$dS$};
    \draw[->] (S) -- (uS) node [midway,  above left] {};
    \draw[->] (S) -- (dS) node [midway,  below left] {};
\end{tikzpicture}
\end{document}
```

In this tree$u$is interpreted as one plus the rate of capital gain on the stock if it goes up,  and$d$is one plus the rate of capital loss if it goes down. (If there are dividends,  the total return is the capital gain or loss,  plus the dividend.)
Let${}  C_u$and${} C_d$represent the value of the option when the stock goes up or down,  respectively. The tree for the stock implies a corresponding tree for the value of the option:

```tikz
\usepackage{tikz-cd}
\usetikzlibrary{positioning}
\begin{document}
\begin{tikzpicture}[>=stealth,  node distance=2cm]
    \node (C) at (0, 0) {$C$};
    \node (Cu) [above right=of C] {$C_u$};
    \node (Cd) [below right=of C] {$C_d$};
    \draw[->] (C) -- (Cu) node [midway,  above left] {};
    \draw[->] (C) -- (Cd) node [midway,  below left] {};
\end{tikzpicture}
\end{document}
```

If the length of a period is$h$,  the interest factor per period is$e^{rh}$. The problem is to solve for$\Delta$and$B$such that our portfolio of$\Delta$shares and$B$in lending duplicates the option payoff. The value of the replicating portfolio at time$h$,  with stock price$S_h$,  is$$\Delta S_h e^{rh} + e^{rh} B$$

At the prices$S_h = dS$and$S_h = uS$,  a successful replicating portfolio will satisfy^2

$$
(\Delta \times dS \times e^{rh}) + (B \times e^{rh}) = C_d
$$

$$
(\Delta \times uS \times e^{rh}) + (B \times e^{rh}) = C_u
$$

This is two equations in the two unknowns$\Delta$and$B$. Solving for$\Delta$and$B$gives$$\Delta = \frac{e^{-rh} C_u - C_d}{S(u - d)} \tag{1}$$

$$B = \frac{e^{-rh} uC_d - dC_u}{u - d} \tag{2}$$

Note that when there are dividends,  the formula adjusts the number of shares in the replicating portfolio, $\Delta$,  to offset the dividend income.
Given the expressions for$\Delta$and$B$,  we can derive a simple formula for the value of the option. The cost of creating the option is the net cash required to buy the shares and bonds. Thus,  the cost of the option is$\Delta S + B$. Using equations (1) and (2),  we have

 $$
 \Delta S + B = \frac { C _ { u } - C _ { d } } { e ^ { \delta h } ( u - d ) } + \frac { uC_ { d } - d C_ { u } } { e ^ { r h } ( u - d ) }
 $$

1. To simplify the equation,  factor out common terms in both fractions:$$\Delta S + B = \frac{1}{e^{\delta h}(u-d)}(C_u-C_d) + \frac{1}{e^{rh}(u-d)}(uC_d-dC_u)$$
2. To simplify the equation,  factor out common terms in both fractions:
3. Recognize that$e^{\delta h}$and$e^{rh}$can be combined as follows since they appear in denominators:
4. To simplify the equation,  factor out common terms in both fractions:$$\Delta S + B = \frac{1}{e^{\delta h}(u-d)}(C_u-C_d) + \frac{1}{e^{rh}(u-d)}(uC_d-dC_u)$$
5. To simplify the equation,  factor out common terms in both fractions:
6. Recognize that$e^{\delta h}$and$e^{rh}$can be combined as follows since they appear in denominators:
7. Combine exponents of$e$using properties of exponents ($a^m a^n = a^{m+n}$):
8. Notice that$e^{-r h} e^{\delta h}=e^{-(r-\delta)h}$,  then insert it back into the equation:$$

$$
1. Finally,  recognize this is equivalent to the desired form by observing that each term involving \( C_{u} \) and \( C_{d} \) has been properly placed within its respective fraction,  giving us: 
2. Finally,  recognize this is equivalent to the desired form by observing that each term involving \( C_{u} \) and \( C_{d} \) has been properly placed within its respective fraction,  giving us: $$\boxed{\Delta S+B=e^{-rh}\left(C_u\frac{e^{(r-\delta)h}-d}{u-d}+C_d\frac{u-e^{(r-\delta)h}}{u-d}\right)}.$$
3. Finally,  recognize this is equivalent to the desired form by observing that each term involving $C_{u}$  and $C_{d}$ has been properly placed within its respective fraction,  giving us: $$\Delta S + B = e^{-rh} \left(\frac{e^{(r- \delta) h}S - d}{u - d} C_u + \frac{u - e^{(r- \delta) h}S}{u - d} C_d \right) \tag{3}$$

The assumed stock price movements,  u and d,  should not give rise to arbitrage opportunities. In particular,  we require that$u>e^{(r-\delta)h}>d\tag{4}$

To see why this condition must hold,  suppose δ = 0. If the condition were violated,  we would sho $r_{t}$ the stock to hold bonds (if $e^{rh} ≥ u$),  or we would borrow to buy the stock (if $d ≥ e^{rh}$). Either way,  we would earn an arbitrage profit. Therefore the assumed process could not be consistent with any possible equilibrium. Problem 23 asks you to verify that equation (4) must hold when *δ >* 0.

Note that because  is the number of shares in the replicating portfolio,  it can also be interpreted as the sensitivity of the option to a change in the stock price. If the stock price changes by$1,  then the option price,  S + B,  changes by. This interpretation will be quite important later.

---

Regarding your question about why certain trades would necessarily follow from the equations given:
The condition $u > e^{(r−δ)h} > d$ ensures there are no arbitrage opportunities because if this inequality did not hold,  one could guarantee profit without risk through simple trading strategies—either shorting stock and buying bonds or borrowing money to buy stock depending on how the inequality is violated.

This concept hinges on what's known as "no-arbitrage" condition in financial markets which posits that you shouldn't be able to make a risk-free profit with zero investment. If \(erh ≥ u\) (assuming δ=0 for simplification),  you would short sell the stock expecting it to fall below its current growth trend and invest in bonds earning at rate \(r\) which is more than what you expect from stock growth (\(erh < u)\). Conversely,  if \(d ≥ erh\) meaning stock's downside movement is less than what bond interest could earn you; borrowing money at rate \(r\) to buy stocks would yield an arbitrage profit since stocks are expected to lose less value than cost of borrowing.

The presence of \Delta as part of replicating portfolio emphasizes how closely option pricing models align with actual market movements;! represents sensitivity or delta (∆),  indicating how much an option's price will move for every \$1 change in underlying asset price.

  ---

##### EXAMPLE 1

Here is the solution for,  B,  and the option price using the stock price tree depicted in Figure 1.
There we have$u = \$60/\$41 = 1.4634$, $d = \$30/\$41 = 0.7317$,  and$δ = 0$.
In addition,  the call option had a strike price of \$40 and 1 year to expiration—hence,  h = 1.
Thus$C_u = \$60 − \$40 = \$20$,  and$C_d = 0$.
Using equations (1) and (2),  we have$\Lambda=\frac{\$20-0}{\$41\times(1.4634-0.7317)}=2/3$
$B=e^{-0.08}\frac{1.4634\times\$0-0.7317\times\$20}{1.4634-0.7317}=-\$18.462$
Hence,  the option price is given by$\Delta S + B = 2/3 \times \$41-\$18.462 = \$8.871$
- Note that if we are interested only in the option price,  it is not necessary to solve for *and* B; that is just an intermediate step.
- If we want to know only the option price,  we can use equation (3) directly:$$\Delta S+B=e^{-0.08}\left(\$20\times\frac{e^{0.08}-0.7317}{1.4634-0.7317}+\$0\times\frac{1.4634-e^{0.08}}{1.4634-0.7317}\right)=\$8.871$$

Throughout this chapter we will continue to repo$r_{t}$and B,  since we are interested not only in the price but also in the replicating portfolio.
## ARBITRAGING A MISPRICED OPTION
- What if the observed option price differs from the theoretical price? Because we have a way to replicate the option using the stock,  it is possible to take advantage of the mispricing and fulfill the dream of every trader—namely,  to buy low and sell high.
- The following examples illustrate that if the option price is anything other than the theoretical price,  arbitrage is possible.
### THE OPTION IS OVERPRICED
Suppose that the market price for the option is$9.00,  instead of$8.871. We can sell the option,  but this leaves us with the risk that the stock price at expiration will be$60 and we will be required to deliver the stock.
We can address this risk by buying a synthetic option at the same time we sell the actual option. 
- We have already seen how to create the synthetic option by buying 2/3 shares and borrowing$18.462. 
- If we simultaneously sell the actual option and buy the synthetic,  the initial cash flow is
- $$\underbrace{\$9.00}*{\text{Receive option premium}}-\underbrace{2/3\times\$41}*{\text{Cost of shares}}+\underbrace{\$18.462}_{\text{Borrowing}}=\$0.129.$$
- If we simultaneously sell the actual option and buy the synthetic,  the initial cash flow is

We earn$0.129,  the amount by which the option is misprised.
Now we verify that there is no risk at expiration. We have 

|                       |$30         |$60          |
|-----------------------|-------------|--------------|
| Written call          |$0          | -$20         |
| 2/3 Purchased shares  |$20         |$40          |
| Repay loan of$18.462 | -$20        | -$20         |
| **Total payoff**      | **$0**      | **$0**       |

By hedging the written option,  we eliminate risk.

### THE OPTION IS UNDERPRICED
Now suppose that the market price of the option is$8.25.
We wish to buy the underpriced option. Of course,  if we are unhedged and the stock price falls at expiration,  we lose our investment.
We can hedge by selling a synthetic option. We accomplish this by reversing the position for a synthetic purchased call: 
- We short 2/3 shares and invest \$18.462 of the proceeds in Treasury bills. 
- The cash flow is$\underbrace{-\$8.25}*{\text{Option premium}}+\underbrace{2/3\times\$41}*{\text{Short-safe proceeds}}-\underbrace{\$18.462}_{\text{Invest in T-bills}}=\$0.621$

At expiration we have
**Stock Price in 1 Year (S_1)**

|                       |$30         |$60          |
|-----------------------|-------------|--------------|
| Purchased call        |$0          |$20          |
| 2/3 Short-sold shares | -$20        | -$40         |
| Sell T-bill           |$20         |$20          |
| **Total payoff**      | **$0**      | **$0**       |

---

We have earned the amount by which the option was mispriced and hedged the risk associated with buying the option.

## A GRAPHICAL INTERPRETATION OF THE BINOMIAL FORMULA

The binomial solution for  and B,  equations (1) and (2),  is obtained by solving two equations in two unknowns. Letting Ch and Sh be the option and stock value after one binomial period,  and supposing δ = 0,  the equations for the portfolio describe a line with and by construction goes through both points E and calculated as Rise Run between points E and D,  which gives the formula for the formula$$
 C_h = \Delta × S_h + e^{rh}B$$

 ![500](IMG-20240913171226944.png)

This is graphed as line *AED* in Figure 2,  which shows the option payoff as a function of the stock price at expiration.

We choose  and B to yield a portfolio that pays$C_d$when$S_h = dS$and$C_u$when$S_h = uS$. Hence,  by construction this line runs through points E and D. We can control the slope of a payoff diagram by varying the number of shares, ,  and its height by varying the number of bonds,  B. It is apparent that a line that runs through both E and D must have slope $= \frac{Cu − Cd}{(uS − *dS)}$. Also,  the point A is the value of the portfolio when Sh = 0,  which is the time-h value of the bond position,  erhB. Hence,  erhB is the y-axis intercept of the line.

You can see by looking at Figure 2 that *any* line replicating a call will have a positive slope (> 0) and a negative intercept (B < 0). As an exercise,  you can verify graphically that a portfolio replicating a put would have negative slope (< 0) and positive intercept(B > 0).

## [[Financial Instruments/Financial Derivatives and Quantitative Methods/Risk Neutral Pricing of Options|RISK-NEUTRAL PRICING]]

In the preceding option price calculations,  we did not make use of (nor did we discuss) the probability that the stock price would move up or down. The strategy of holding  shares and B bonds replicates the option payoff whichever way the stock moves,  so the probability of an up or down movement is irrelevant for computing S + B,  which is the option price.

Although we do not need probabilities to price the option,  there is a very important probabilistic interpretation of equation (3). Define$$p^{*}=\frac{e^{(r-\delta)h}-d}{u-d}\tag{5}$$
- We call$p^{*}$the **risk-neutral probability** of an increase in the stock price. 
- You can verify that 0 *< p*∗ < 1 (this follows from inequality 4),  so that$p^{*}$looks like a probability. 
- Using equation (5),  and the fact that C = S + B,  we can rewrite equation (3) as$$C=e^{-rh}[p^{*}C_{u}+(1-p^{*})C_{d}]\tag{6}$$
- Because$p^∗$and$1 − p^∗$are both positive and sum to one,  the term$p^{*}C_u + ($1 − p^∗$)C_d$looks like an expected cash flow computed using the risk-neutral probability. 
- This expected cash flow is then discounted using the risk-free rate. 
- The pricing procedure illustrated in equation (6),  in which a risk-neutral expected value is discounted at the risk-free rate,  is called **risk-neutral valuation**.

We can also use equation (6) to compute forward and prepaid forward prices. If we substitute next period's possible stock prices in place of the option prices in equation (6),  after some algebra we obtain$$e^{-r\hbar}\left[p^{*}uS+(1-p^{*})dS\right]=Se^{-\delta h}\tag{7}$$

This is the prepaid forward price. If we do not discount the expected payoff,  we obtain the forward price,  which is a value dominated in time$h$dollars.$$p^{*}uS+(1-p^{*})dS=Se^{(r-\delta)h}=F_{t, \, t+h}\tag{8}$$
You can think about$p^{*}$as the probability for which the expected stock price is the forward price.

When you first encounter risk-neutral valuation,  it appears peculiar. The risk-neutral probability is generally not the actual probability of the stock price going up,  and the expected cash flow in equation (6) is discounted at the risk-free rate even though the option has the risk of a levered investment in the stock. Nevertheless,  risk-neutral valuation is one of the most important ideas in the derivatives markets.

## 2. CONSTRUCTING A BINOMIAL TREE

In this section we explain the construction of the binomial tree. We will model the stock returns u and d using the equations$$u=e^{(r-\delta)h+\sigma\sqrt{h}}\tag{9} d=e^{(r-\delta)h-\sigma\sqrt{h}}$$
where$r$is the continuously compounded annual interest rate, $\delta$is the continuous dividend yield, $\sigma$is the annual volatility,  and$h$is the length of a binomial period in years.

In all likelihood you do not find equation (9) to be immediately intuitive. Thus,  in this section we explain a number of the concepts underlying equation (9). We first review some properties of continuously compounded returns and define volatility. We then explain the construction of$u$and$d$,  and then discuss the estimation of historical volatility.

## CONTINUOUSLY COMPOUNDED RETURNS

What follows in this section relies on calculations based on continuously compounded returns. Returns can be expressed in a variety of ways. Continuously compounded returns are mathematically convenient and widely used in practice,  both in pricing models and when computing volatility. Here we briefly summarize the important properties of continuously compounded returns.

The logarithmic function computes continuously compounded returns from prices.

- Let$S_{t}$and$S_{t+h}$be stock prices at times t and$t + h$. 
- The continuously compounded return between$t$and$t + h$, $r_t$, $t+h$is then$$r_{t, t+h}=\ln(S_{t+h}/S_{t})\tag{10}$$
- The exponential function computes prices from continuously compounded returns.

If we know the continuously compounded return, $r_{t}$, $t+h$,  we can obtain$S_{t+h}$by exponentiating both sides of equation (10). 
- This gives$$S_{t+h}=S_{t}e^{r_{t}, t+h}\tag{11}$$
#### CONTINUOUSLY COMPOUNDED RETURNS ARE ADDITIVE

- Suppose we have continuously compounded returns over consecutive periods—for example, $r_{t}$, t+h, $r_{t+h}$, t+2h,  etc.
- The continuously compounded return over a long period is the *sum* of continuously. compounded returns over the shorter periods,  i.e., $$F_{t, t+nh}=\sum_{i=1}^{n}F_{t+(i-1)h, t+ih}\tag{12}$$
- Here are some examples illustrating these statements.

## VOLATILITY

The **volatility** of an asset,  defined as the standard deviation of continuously compounded returns,  is a key input for any option pricing calculation. We can express volatility over different periods. For example,  we could compute monthly volatility (the standard deviation of the monthly return) or annual volatility (the standard deviation of the annual return). How are these related?

Suppose that the continuously compounded return over month i is$r_{monthly, i}$. From equation (12),  we can sum continuously compounded returns. Thus,  the annual continuously compounded return is
$$

r_{\mathrm{annual}}=\sum_{i=1}^{12}r_{\mathrm{monthly}, i}

$$

The variance of the annual continuously compounded return is therefore
$$

\text{Var}(r_{\text{annual}})=\text{Var}\left(\sum_{i=1}^{12}r_{\text{monthly}, i}\right)\tag{13}

$$

It is common to assume that returns are uncorrelated over time; i.e.,  the realization of the return in one period does not affect the expected returns in subsequent periods. With this assumption,  the variance of a sum is the sum of the variances. Also suppose that each month has the same variance of returns. If we let$σ^2$denote the annual variance,  then from equation (13) we have
$$

\sigma^{2}=12\times\sigma_{\mathrm{monthly}}^{2}

$$

Taking the square root of both sides and rearranging,  we can express the monthly standard deviation in terms of the annual standard deviation,  σ:
$$

\sigma_{\mathrm{monthly}}={\frac{\sigma}{\sqrt{12}}}

$$

To generalize this formula,  if we split the year into n periods of length h (so that h = 1/n),  the standard deviation over the period of length h,  σh,  is
$$

\sigma_{h}=\sigma\sqrt{h}\tag{14}

$$

The standard deviation thus scales with the square root of time. If we know σh,  equation (14) implies that
$$

\sigma=\frac{\sigma_{h}}{\sqrt{h}}\tag{15}

$$

## CONSTRUCTING U AND D

As a starting point in constructing u and d,  we can ask: What if there were no uncertainty about the future stock price? With certainty,  the stock price next period must equal the forward price. The formula for the forward price is
$$

F_{t, \, t+h}=S_{t}e^{(r-\delta)h}\tag{16}

$$

Thus,  without uncertainty we must have$S_{t+h}=F_{t, \, t+h}$; the rate of return on the stock must be the risk-free rate.[5]

We incorporate uncertainty into the stock return using volatility,  which measures how sure we are that the stock rate of return will be close to the expected rate of return. Stocks with a larger σ will have a greater chance of a return far from the expected return. We model the stock price evolution by adding uncertainty to the forward price:
$$u\, S_{t}=F_{t, \, t+h}e^{+\sigma\sqrt{h}}\tag{17} dS_{t}=F_{t, \, t+h}e^{-\sigma\sqrt{h}}$$

Using equation (16),  we can rewrite equation (17) to obtain equation (9). This is the formula we will use to construct binomial trees. Note that if we set volatility equal to zero (i.e., $\sigma=0$),  we will have$u\, S_{t}=dS_{t}=F_{t, \, t+h}$. Thus,  with zero volatility,  the price will still rise over time,  just as with a Treasury bill. Zero volatility does not mean that prices are *fixed*; it means that prices are *known in advance*.

We will refer to a tree constructed using equation (9) as a "forward tree."

## ESTIMATING HISTORICAL VOLATILITY

In selecting the parameters to use in the binomial model,  the most difficult decision usually is choosing the value for σ,  which we cannot observe directly. One possibility is to measure σ by computing the standard deviation of continuously compounded historical returns.

Volatility computed from historical stock returns is **historical volatility**.

Table 1 lists 10 weeks of Wednesday closing prices for the S&P 500 composite index and for IBM,  along with the standard deviation of the continuously compounded returns,  computed using the StDev function in Excel0.\1 Based on the historical returns in Table 1,  the weekly standard deviation of returns was 0.02800 and 0.02486 for the S&P 500 index and IBM,  respectively. These standard deviations measure the variability in weekly returns. We compute annualized standard deviations by using equation (15): Multiply the weekly increase,  which is at the rate r − δ,  plus the dividend yield,  δ.

standard deviations by$\sqrt{52}$(because$h = 1/\sqrt{52}$,  giving annualized historical standard deviations of 20.19% for the S&P 500 index and 17.93% for IBM. We can use the estimated annualized standard deviation as σ in constructing a binomial tree.

 Once we annualize the estimate we can then multiply the result by √h (as in equation (9)) to obtain the appropriate standard deviation for any size binomial step.

You might be wondering about how dividends affect the standard deviation calculation. The returns in Table 1 are based on ex-dividend prices,  in particular ignoring IBM's payment of$0.65 with an ex-dividend date of August 6,  2010. Including the dividend in the return calculation in this example changes the estimated annual standard deviation to

0.1778. Most of the time dividends are infrequent and small; the standard deviation will be similar whether you compute a standard deviation accounting for dividends or ignoring them.

The more important question is whether the standard deviation calculation should be based on returns that include dividends (the total return volatility). For option pricing it is generally the volatility of the price *excluding dividends* that matters. For a European option,  the payoff clearly depends on the ex-dividend price,  so the volatility calculation should exclude dividends. The same is true for American options: If an American call is not exercised before expiration,  the payoff depends on the ex-dividend price. If it is exercised before expiration,  the option holder exercises prior to a dividend. American puts are exercised ex-dividend. Thus,  for standard options,  the volatility that matters excludes dividends. For an option protected against dividends,  it would be appropriate to base pricing upon the total return volatility,  which includes dividends.

Binomial tree for pricing a European call option; assumes S =$41.00,  K =$40.00,  σ = 0.30,  r =
0.08,  T = 1.00 years,  δ = 0.00,  and h = 1.000. At each node the stock price,  option price, ,  and B
are given. Option price in *bold italic* signifies that exercise is optimal at that node.

## ONE-PERIOD EXAMPLE WITH A FORWARD TREE

We began this section by assuming that the stock price followed the binomial tree in Figure 1. The up and down stock prices of$30 and$60 were selected to make the example easy to follow. Now we present an example where everything is the same except that we use equation (9) to construct the up and down moves.

Suppose volatility is 30%. Since the period is 1 year,  we have h = 1,  so that σ√h = 0.30. We also have $S_0  =\$41,  r = 0.08,  \ and \ δ = 0.$ {}$ Using equation (9),  we get $$dS =$41e(0.08−0)×1−0.3× √ 1 =$32.903 (18)$$

Because the binomial tree is different than in Figure 1,  the option price will be different as well.
Using the stock prices given in equation (18),  we have $u = \$\frac{59.954}{\$41} = 1.4623$ and d =$32.903/$41= 0.8025. With K =$40,  we have Cu =$59.954 −$40 =$19.954,  and Cd = 0. Using equations (1) and (2),  we obtain
 =$19.954 − 0$41× (1.4623 − 0.8025) = 0.7376 B = e−0.081.4623 ×$0 − 0.8025 ×$19.954 1.4623 − 0.8025 = −$22.405

Hence,  the option price is given by

$\Delta$S +$B=0.7376\times$$41-$$22.405=$$7.839$

This example is summarized in Figure 3.

We have covered a great deal of ground in this section,  but there are still many issues remaining. The simple binomial tree seems too simple to provide an accurate option price. Unanswered questions include how to handle more than one binomial period,  how to price put options,  and how to price American options. With the basic binomial formula in hand,  we can now turn to those questions.

Binomial tree for pricing a European call option; assumes S =$41.00,  K =$40.00,  σ = 0.30,  r = 0.08,  T = 2.00 years,  δ = 0.00,  and h = 1.000. At each node the stock price,  option price,  and B are given. Option prices in *bold italic* signify that exercise is optimal at that node.

## 3. TWO OR MORE BINOMIAL PERIODS

We now see how to extend the binomial tree to more than one period. We begin by pricing a 2-year option using a two-period binomial model. Then we will see how to accommodate many periods of arbitrary length.

## A TWO-PERIOD EUROPEAN CALL

We begin first by adding a single period to the tree in Figure 3; the result is displayed in Figure 4. We can use that tree to price a 2-year option with a$40 strike when the current stock price is$41,  assuming all inputs are the same as before.

Since we are increasing the time to maturity for a call option on a non-dividend-paying stock,  we expect the option premium to increase. In this example the two-period tree will give us a price of $10.737,  compared to $7.839 in Figure 3.

Constructing the Tree.

To see how to construct the tree,  suppose that we move up in year 1,  to Su = \$59.954. If we reach this price,  then we can move further up or down according to equation (17). We get$$\mathbb{S}_{\mu\nu}=\$59.954e^{0.08+0.3}=\$87.669$$
and
$$

S_{ud}=\$59.954e^{0.08-0.3}=\$48.114

$$

The subscript$uu$means that the stock has gone up twice in a row and the subscript$ud$means that the stock has gone up once and then down.

Similarly,  if the price in 1 year is$S_{d}=\$32.903$, we have$S_{du}=\$32.903e^{0.08+0.3}=\$48.114$and

$$

S_{d d}=\$32.903e^{0.08-0.3}=\$26.405

$$
Note that an up move followed by a down move (Sud) generates the same stock price as a down move followed by an up move (Sdu). This is called a **recombining tree**. If an up move followed by a down move led to a different price than a down move followed by an up move,  we would have a **nonrecombining tree**0.\1 A recombining tree has fewer nodes,  which means less computation is required to compute an option price.

We also could have used equation (9) directly to compute the year-2 stock prices.
Recall that $u = e^{0.08}+0.3 = 1.462$ and ${} d = e^{0.08}−0.3 = 0.803$. We have $$S_{uu}=u^{2}\times\$41=e^{2\times(0.08+0.3)}\times\$41=\$87.669$$

$$S_{ud}=S_{du}=u\times d\times\$41=e^{(0.08+0.3)}\times e^{(0.08-0.3)}\times\$41=\$48.114$$
$$S_{dd}=d^{2}\times\$41=e^{2\times(0.08-0.3)}\times\$41=\$26.405$$

**Pricing the Call Option.** How do we price the option when we have two binomial periods? The key insight is that we work *backward* through the binomial tree. In order to use equation (3),  we need to know the option prices resulting from up and down moves in the subsequent period. At the outset,  the only period where we know the option price is at expiration.

Knowing the price at expiration,  we can determine the price in period 1. Having determined that price,  we can work back to period 0.

Frigerted exhibits the option price at each node as well as the details of the replicating portfolio at each node. Remember,  however,  when we use equation (3),  it is not necessary to compute$\Delta$and$B$in order to derive the option price.${}^{8}$Here are details of the solution:

Year 2,  Stock Price = **$87.669.** Since we are at expiration,  the option value is max(0,  S − K) =$47.669.
Year 2,  Stock Price = **$48.114.** Again we are at expiration,  so the option value is$8.114.
Year 2,  Stock Price = **$26.405.** Since the option is out of the money,  the value is 0.
Year 1,  Stock Price = **$59.954.** At this node we use equation (3) to compute the option value. (Note that once we are at this node,  the "up" stock price,  uS,  is  $87.669,  and the "down" stock price,  dS,  is{} 48.114.) $$e^{-0.08}\left(\$47.669\times\frac{e^{0.08}-0.803}{1.462-0.803}+\$8.114\times\frac{1.462-e^{0.08}}{1.462-0.803}\right)=\$23.029$$
Year 1,  Stock Price = ** \$32.903**.Again we use equation(3)to compute the option value: $$e^{-0.08}\left(\$8.114\times\frac{e^{0.08}-0.803}{1.462-0.803}+\$0\times\frac{1.462-e^{0.08}}{1.462-0.803}\right)=\$3.187$$
Year 0,  Stock Price = **\$41.** Again using equation(3):
$e^{-0.08}$$e^{-0.08}\left(\$23.029\times\frac{e^{0.08}-0.803}{1.462-0.803}+\$3.187\times\frac{1.462-e^{0.08}}{1.462-0.803}\right)=\$10.737$

Notice the following:
- The option price is greater for the 2-year than for the 1-year option,  as we would expect.
- We priced the option by working backward through the tree,  starting at the end and working back to the first period.
- The option's  and B are different at different nodes. In particular,  at a given point in time,   increases to 1 as we go further into the money.
- We priced a European option,  so early exercise was not permitted. However,  permitting early exercise would have made no difference. At every node prior to expiration,  the option price is greater than S − K; hence we would not have exercised even if the option had been American.
- Once we understand the two-period option,  it is straightforward to value an option using more than two binomial periods. The important principle is to work backward through the tree.

## MANY BINOMIAL PERIODS

An obvious objection to the binomial calculations thus far is that the stock can only have two or three different values at expiration. It seems plausible that to increase accuracy we would want to divide the time to expiration into more periods,  generating a more realistic tree. Fortunately,  the generalization to many binomial periods is straightforward.

To illustrate using more binomial periods,  we re-examine the 1-year European call option in Figure 3,  which has a \$40 strike and initial stock price of$41. We use equation (9) to generate the up and down moves. Suppose there are three binomial periods. With a 1-

year call,  the length of a period is h = 1

3. We will assume that other inputs stay the same,  so r = 0.08 and σ = 0.3. Equation (9) then automatically generates a per-period interest rate of$r_{}h = 0.027$and volatility of$σ\sqrt{h} = 0.1732$.

Figure 5 depicts the stock price and option price tree for this option. The option price is$7.074,  as opposed to$7.839 in Figure 3. The difference occurs because the numerical approximation is different; it is quite common to see large changes in a binomial price when the number of periods,  n,  is changed,  particularly when n is small.

Since the length of the binomial period is shorter,  u and d are closer to 1 than before

(1.2212 and 0.8637 as opposed to 1.462 and 0.803 with h = 1). Just to be clear about the procedure,  here is how the second-period nodes are computed:

$$

S_{u}=\$41e^{0.08\times1/3+0.3\sqrt{1/3}}=\$50.071

$$

$$S_{d}=\$41e^{0.08\times1/3-0.3\sqrt{1/3}}=\$35.411$$
The remaining nodes are computed similarly.
The option price is computed by working backward. The risk-neutral probability of the stock price going up in a period is

----

price sooner rather than later. The disadvantages are the dividends lost by giving up the stock,  and the loss of insurance against the stock price exceeding the strike price.
Figures 1 and 2 also show that,  other things equal,  early-exercise criteria become less stringent closer to expiration. This occurs because the value of insurance diminishes as the options approach expiration.
While these pictures are constructed for the special case where δ = r,  the overall conclusion holds generally.
## 2. UNDERSTANDING RISK-NEUTRAL PRICING
The binomial option pricing formula can be written
$$

C=e^{-rh}[p^{*}C_{u}+(1-p^{*})C_{d}]\tag{1}

$$
where
$$

p^{*}=\frac{e^{(r-\delta)h}-d}{u-d}\tag{2}

$$
We labeled$p^{*}$the *risk-neutral probability* that the stock will go up. Equation (1) has the appearance of a discounted expected value,  where the expected value calculation uses
and discounting is done at the risk-free rate.
In this section we explain why p∗ is called the risk-neutral probability and show that option valuation is consistent with standard discounted cash flow calculations.
## THE RISK-NEUTRAL PROBABILITY
The idea that an option price is the result of a present value calculation is reassuring,  but at the same time equation (1) is puzzling. A standard discounted cash flow calculation would require computing an expected value using the true probability that the stock price would go up. Discounting would then be done using the expected return on an asset of equivalent risk,  not the risk-free rate.
It is common in finance to emphasize that investors are risk averse. To see what risk aversion means,  suppose you are offered either (a)$1000,  or (b)$2000 with probability
0.5,  and$0 with probability 0.5. A **risk-averse** investor prefers (a),  since alternative (b) is risky and has the same expected value as (a). This kind of investor will require a premium to bear risk when expected values are equal.
A **risk-neutral** investor is indifferent between a sure thing and a risky bet with an expected payoff equal to the value of the sure thing. A risk-neutral investor,  for example,  will be equally happy with alternative (a) or (b).
Let's consider what an imaginary world populated by risk-neutral investors would be like. In such a world,  investors care only about expected returns and not about riskiness. Assets would have no risk premium since investors would be willing to hold assets with an expected return equal to the risk-free rate.
In this hypothetical risk-neutral world,  we can solve for the probability of the stock going up,  p∗,  such that the stock is expected to earn the risk-free rate. In the binomial model,  the probability that the stock will go up,  p∗,  must satisfy p∗uSeδh + (1− p∗)dSeδh = erhS
Solving for p∗ gives us equation (2),  which is why we refer to p∗ as the risk-neutral probability that the stock price will go up. It is the probability that the stock price would increase in a risk-neutral world.
Not only would the risk-neutral probability,  equation (2),  be used in a risk-neutral world,  but also all discounting would take place at the risk-free rate. Thus,  the option pricing formula,  equation (1),  can be said to price options *as if* investors are risk-neutral.
ous,  It is important to note that we are not assuming that investors are actually risk-neutral,  and we are not assuming that risky assets are actually expected to earn the risk-free rate of return. Rather,  *risk-neutral pricing is an* interpretation *of the formulas above*. Those formulas in turn arise from finding the cost of the portfolio that replicates the option payoff.
This interpretation of the option-pricing procedure has great practical importance;
risk-neutral pricing can sometimes be used where other pricing methods are too difficult. Risk-neutral pricing is the basis for Monte Carlo valuation,  in which asset prices are simulated under the assumption that assets earn the risk-free rate,  and these simulated prices are used to value the option.
## PRICING AN OPTION USING REAL PROBABILITIES
We are left with this question: Is option pricing consistent with standard discounted cash flow calculations? The answer is yes. We can use the true distribution for the future stock price in computing the expected payoff to the option. This expected payoff can then be discounted with a rate based on the stock's required return.
Discounted cash flow is not used in practice to price options because there is no reason to do so: However,  we present two examples of valuing an option using real probabilities to see the difficulty in using real probabilities,  and also to understand how to determine the risk of an option.
Suppose that the continuously compounded expected return on the stock is α and that the stock does not pay dividends. Then if p is the true probability of the stock going up,  p must be consistent with u,  d,  and α:
$puS+(1-p)dS=e^{\alpha h}S$(3)
Solving for p gives us
$$

p=\frac{e^{\alpha h}-d}{u-d}\tag{4}

$$
For probabilities to be between 0 and 1,  we must have$u>e^{\alpha h}>d$. Using$p$,  the actual expected payoff to the option one period hence is
$$

pC_{u}+(1-p)C_{d}=\frac{e^{\alpha h}-d}{u-d}C_{u}+\frac{u-e^{\alpha h}}{u-d}C_{d}\tag{5}

$$
Now we face the problem with using real as opposed to risk-neutral probabilities: At what rate do we discount this expected payoff? It is not correct to discount the option at the expected return on the stock,  α,  because the option is equivalent to a leveraged investment in the stock and,  hence,  is riskier than the stock.
Denote the appropriate per-period discount rate for the option as γ. To compute γ,  we can use the fact that the required return on any portfolio is the weighted average of the returns on the assets in the portfolio0.\1 An option is equivalent to holding a portfolio consisting of ${} \Delta$ shares of stock and B bonds. The expected return on this portfolio is
$$

e^{\gamma h}=\frac{S\Delta}{S\Delta+B}\, e^{\alpha h}+\frac{B}{S\Delta+B}\, e^{\gamma h}\tag{6}

$$
We can now compute the option price as the expected option payoff,  equation (5),  discounted at the appropriate discount rate,  given by equation (6). This gives
$$

e^{-\gamma h}\left[\frac{e^{\alpha h}-d}{u-d}\, C_{u}+\frac{u-e^{\alpha h}}{u-d}\, C_{d}\right]\tag{7}

$$
It turns out that *this gives us the same option price as performing the risk-neutral calculation*. Appendix A demonstrates algebraically that equation (7) is equivalent to the risk-neutral calculation,  equation (1).
The calculations leading to equation (7) started with the assumption that the expected return on the stock is$\alpha$. We then derived a consistent probability, $p$,  and discount rate for the option, $\gamma$. You may be wondering if it matters whether we have the "correct" value of$\alpha$to start with. The answer is that it does not matter: *Any* consistent pair of$\alpha$and$\gamma$will give the same option price. Risk-neutral pricing is valuable because setting$\alpha=r$results in the *simplest* pricing procedure.
A One-Period Example.
To see how to value an option using true probabilities,  we will compute two examples. First,  consider the one-period binomial example in Figure 3.
Suppose that the continuously compounded expected return on XYZ is α = 15%. Then the true probability of the stock going up,  from equation (4),  is
$$

p=\frac{e^{0.15}-0.8025}{1.4623-0.8025}=0.5446

$$
The expected payoff to the option in one period,  from equation (5),  is
$$

0.5446\times\$19.954+(1-0.5446)\times\$0=\$10.867

$$
The replicating portfolio, $\Delta$and$B$,  does not depend on$p$or$\alpha$. In this example, $\Delta=0.738$and$B=-\$22.405$. The discount rate, \gamma$,  from equation (6) is given by
$$

e^{\gamma h}=\frac{0.738\times\$41}{0.738\times\$41-\$22.405}e^{0.15}+\frac{-\$22.405}{0.738\times\$41-\$22.405}e^{0.08}=1.386

$$
$59.954$19.954
$41.000
Binomial tree for pricing a European call option;
assumes$S=\$41.00$, $K=\$40.00$, $\sigma=0.30$, $r=0.08$, 
$T=1.00$years, $\delta=0.00$, 
and$h=1.000$.  Thus, $\gamma=\ln(1.386)=32.64\%$. The option price is then given by equation (7):
$$e^{-0.3264}\times\$10.867=\$7.839$$
This is exactly the price we obtained before.
Notice that in order to compute the discount rate,  we first had to compute ${} \Delta$ and B.
But once we have computed ${} \Delta$ and B,  we can simply compute the option price as ${} \Delta$S + B.
There is no need for further computations. It can be helpful to know the actual expected return on an option,  but for valuation it is pointless.

#### A MULTI-PERIOD EXAMPLE.
To demonstrate that this method of valuation works over multiple periods,  Figure 4 presents a binomial tree illustrating that the true discount rate for the option,  γ,  is reported at each node. Given the 15% continuously compounded discount rate,  the true probability of an up move in Figure 4 is
$$\frac{e^{0.15\times1/3}-0.8637}{1.2212-0.8637}=0.5247$$
To compute the price at the node where the stock price is$61.149, we discount the expected option price the next period at26.9%.This gives
$$e^{-0.269\times1/3}\left[0.5247\times\$34.678+(1-0.5247)\times\$12.814\right]=\$22.202$$
When the stock price is$\$43.246, the discount rate is$49.5\%, and the option price is
$$e^{-0.495\times1/3}\left[0.5247\times\$12.814+(1-0.5247)\times\$0\right]=\$5.700$$
$74.678
$34.678
γ = N/A
$\$61.149$
$\$22.202$
$\gamma=0.269$
$\$50.071$
$\$12.889$
$\gamma=0.323$
$\$41.000$
$\$43.246$
$\$5.700$
$\gamma=0.357$
$\gamma=0.495$
$\$35.411$
$\$2.535$
$\gamma=0.495$
$37.351
$0.000
γ = N/A
Binomial tree for pricing an American call option;
assumes S =$41.00,  K
=$40.00,  σ = 0.30,  r =
0.08,  T = 1.00 years,  δ =
0.00,  and h = 0.333. The continuously compounded true expected return on the stock,  α,  is 15%. At each node the stock price,  option price,  and continuously compounded true discount rate for the option,  γ,  are given. Option price in bold italic signify that exercise is optimal at that node.
$30.585
$0.000
γ = N/A
$26.416
$0.000
γ = N/A
We work back through the tree. To compute the price at the node where the stock price is$50.071,  we discount the expected option price the next period at 32.3%. Thus, 
$$e^{-0.323\times1/3}\left[0.5247\times\$22.202+(1-0.5247)\times\$5.700\right]=\$12.889$$
The actual discount rate for the option changes as we move down the tree at a point in time and also over time. The required return on the option is less when the stock price is$61.149(26.9\%)$than when it is$43.246(49.5\%)$. The discount rate increases as the stock price decreases because the option is equivalent to a leveraged position in the stock,  and the degree of leverage increases as the option moves out of the money.
These examples illustrate that it is possible to obtain option prices using standard discounted-cash-flow techniques. Generally,  however,  there is no reason to do so. Moreover,  the fact that risk-neutral pricing works means that it is not necessary to estimate$\alpha$,  the expected return on the stock,  when pricing an option. Since expected returns are hard to estimate precisely,  this makes option pricing a great deal easier.
Appendix B goes into more detail about risk-neutral pricing.
## 3. THE BINOMIAL TREE AND [[Advanced Investments/Lecture 1- Probability Distributions of Returns|LOGNORMALITY]]
The usefulness of the binomial pricing model hinges on the binomial tree providing a reasonable representation of the stock price distribution. In this section we discuss the motivation for and plausibility of the binomial tree. We will define a lognormal distribution and see that the binomial tree approximates this distribution.
## THE RANDOM WALK MODEL
It is sometimes said that stock prices follow a random walk. More precisely,  a random walk provides a foundation for modeling the prices of stocks and other assets. In this section,  we will explain what a random walk is. In the next section,  we use the random walk model to build a model of stock prices.
To understand a random walk,  imagine that we flip a coin repeatedly. Let the random variable Y denote the outcome of the flip. If the coin lands displaying a head,  Y = 1. If the coin lands displaying a tail,  Y = −1. If the probability of a head is 50%,  we say the coin is fair. After n flips,  with the ith flip denoted Yi,  the cumulative total,  Zn,  is
$$

Z_{n}=\sum_{l=1}^{n}Y_{l}\tag{8}

$$
It turns out that the more times we flip,  on average,  the farther we will move from where we start. We can understand intuitively why with more flips the average distance from the starting point increases. Think about the first flip and imagine you get a head. You move to
+1,  and as far as the remaining flips are concerned,  *this is your new starting point*. After the second flip,  you will either be at 0 or +2. If you are at zero,  it is as if you started over;
however,  if you are at +2,  you are starting at +2. Continuing in this way,  your average distance from the starting point increases with the number of flips0.\1
Another way to represent the process followed by Zn is in terms of the *change* in Zn:
$$

Z_{n}-Z_{n-1}=Y_{n}

$$
We can rewrite this more explicitly as
$$

\begin{array}{ll}\mbox{Heads:}&Z_{n}-Z_{n-1}=+1\\ \mbox{Tails:}&Z_{n}-Z_{n-1}=-1\end{array}\tag{9}

$$
With heads,  the *change* in$Z$is 1,  and with tails,  the change in$Z$is$-1$. This random walk is illustrated in Figure 5.
The idea that asset prices should follow a random walk was articulated in Samuelson (1965). In efficient markets,  an asset price should reflect all available information. By definition,  new information is a surprise. In response to new information the price is equally likely to move up or down,  as with the coin flip. The price after a period of time is the initial price plus the cumulative up and down movements due to informational surprises.
## MODELING STOCK PRICES AS A RANDOM WALK
The idea that stock prices move up or down randomly makes sense; however,  the description of a random walk in the previous section is not a satisfactory description of stock price movements. Suppose we take the random walk model in Figure 5 literally. Assume the beginning stock price is$100,  and the stock price will move up or down$1 each time we flip the coin. There are at least three problems with this model:
1. If by chance we get enough cumulative down movements,  the stock price will become
	 negative. Because stockholders have limited liability (they can walk away from a bankrupt firm),  a stock price will never be negative.
1. The magnitude of the move ($1) should depend upon how quickly the coin flips occur
	 and the level of the stock price. If we flip coins once a second, $1 moves are excessive; in real life,  a$100 stock will not typically have 60$1 up or down movements in 1 minute. Also,  if a$1 move is appropriate for a$100 stock,  it likely isn't appropriate for a$5 stock.
1. The stock on average should have a positive return. The random walk model taken
	 literally does not permit this.
$D_{n}^{2}=0.5\times(D_{n-1}+1)^{2}+0.5\times(D_{n-1}-1)^{2}=D_{n-1}^{2}+1$
	 It turns out that the binomial model is a variant of the random walk model that solves all of these problems at once. The binomial model assumes that continuously compounded returns are a random walk with drift.
## THE BINOMIAL MODEL
The binomial stock price is
$$

S_{t+h}=S_{t}e^{(r-\delta)h\pm\sigma{\sqrt{h}}}

$$
Taking logs,  we obtain
$$

\ln(S_{t+h}/S_{t})=(r-\delta)h\pm\sigma\sqrt{h}\tag{11}

$$
Since ln(St+h/St) is the continuously compounded return from t to t + h,  rt, t+h,  the binomial model is simply a particular way to model the continuously compounded return.
That return has two parts,  one of which is certain [(r − *δ)h*],  and the other of which is uncertain and generates the up and down stock price moves (±σ
√
h).
Let's see how equation (11) solves the three problems in the random walk discussed earlier:
1. The stock price cannot become negative. Even if we move down the binomial tree
	 many times in a row,  the resulting large,  negative,  continuously compounded return will give us a positive price.
1. As stock price moves occur more frequently,  h gets smaller,  therefore up and down
	 moves get smaller. By construction,  annual volatility is the same no matter how many binomial periods there are. Since returns follow a random walk,  the percentage price change is the same whether the stock price is$100 or$5.
1. There is a (r − *δ)h* term,  and we can choose the probability of an up move,  so we can
	 guarantee that the expected change in the stock price is positive.
	 The bottom panel of Figure 5 illustrates the stock price that results when the continuously compounded return follows equation (11). The figure is one particular path through a 10, 000-step binomial tree,  with the path generated by the same sequence of coin flips as in the top panel of Figure 5.
## LOGNORMALITY AND THE BINOMIAL MODEL
The binomial tree approximates a lognormal distribution,  which is commonly used to model stock prices. The lognormal distribution is the [[Lecture 1- Probability Distributions of Returns|probability distribution]] that arises from the assumption that *continuously compounded returns on the stock are normally distributed*.
When we traverse the binomial tree,  we are implicitly adding up binomial random return components of (r − δ)h ± σ
√
h. In the limit (as n → ∞ or,  the same thing,  h → 0),  the sum of binomial random variables is normally distributed. Thus,  continuously compounded returns in a binomial tree are (approximately) normally distributed,  which means that the stock is lognormally distributed. We can see with an example how it works.
The binomial model implicitly assigns probabilities to the various nodes. Figure 6
depicts the construction of a tree for three binomial periods,  along with the risk-neutral probability of reaching each final period node. There is only one path—sequence of up and down moves—reaching the top or bottom node (uuu or *ddd*),  but there are three paths reaching each intermediate node. For example,  the first node below the top (S0u2d) can be reached by the sequences uud,  *udu*,  or *duu*. Thus,  there are more paths that reach the intermediate nodes than the extreme nodes.
We can take the probabilities and outcomes from the binomial tree and plot them against a lognormal distribution with the same parameters. Figure 7 compares a three-period binomial approximation with a lognormal distribution assuming that the initial stock price is$100,  volatility is 30%,  the expected return on the stock is 10%,  and the time horizon is 1 year. Because we need different scales for the discrete and continuous distributions,  lognormal probabilities are graphed on the left vertical axis and binomial probabilities on the right vertical axis.
Suppose that a binomial tree has n periods and the risk-neutral probability of an up move is p∗. To reach the top node,  we must go up n times in a row,  which occurs with a probability of (p∗)n. The price at the top node is Sun. There is only one path through the tree by which we can reach the top node. To reach the first node below the top node,  we must go up n − 1 times and down once,  for a probability of (p∗)n−1 × (1 − p∗). The price at that node is Sun−1d. Since the single down move can occur in any of the n periods,  there are n ways this can happen. The probability of reaching the ith node below the top is
(p∗)n−i × (1− p∗)i. The price at this node is Sun−idi. The number of ways to reach this node is
Number of ways to reach$i$th node$=\dfrac{n!}{(n-i)!\, i!}=\binom{n}{i}$
where n! = n × (n − 1) × … × 1.3
We can construct the implied [[Lecture 1- Probability Distributions of Returns|probability distribution]] in the binomial tree by plotting the stock price at each final period node,  Sun−idi,  against the probability of reaching that node. The probability of reaching any given node is the probability of one path reaching that node times the number of paths reaching that node:
Figure 8 compares the [[Lecture 1- Probability Distributions of Returns|probability distribution]] for a 25-period binomial tree with the corresponding lognormal distribution. The two distributions appear close; as a practical matter,  a 25-period approximation works fairly well for an option expiring in a few months.
Figures 7 and 8 show you what the lognormal distribution for the stock price looks like. The stock price is positive,  and the distribution is skewed to the right; that is,  there is a chance that extremely high stock prices will occur.
## ALTERNATIVE BINOMIAL TREES
There are other ways besides equation (11) to construct a binomial tree that approximates a lognormal distribution. An acceptable tree must match the standard deviation of the continuously compounded return on the asset and must generate an appropriate distribution as the length of the binomial period,  h,  goes to 0. Different methods of constructing the binomial tree will result in different u and d stock movements.
The Cox-Ross-Rubinstein Binomial Tree.
The best-known way to construct a binomial tree is that in Cox et al. (1979),  in which the tree is constructed as
$$

u=e^{\sigma\sqrt{h}}\tag{13}

$$$$
$$ 

$$
u=e^{\sigma\sqrt{h}}\tag{13}
$$

$$
u=e^{\sigma\sqrt{h}}\tag{13} d=e^{-\sigma\sqrt{h}}
$$
$$u=e^{\sigma\sqrt{h}}\tag{13}$$
The Cox-Ross-Rubinstein approach is often used in practice. A problem with this approach,  however,  is that if$h$is large or$\sigma$is small,  it is possible that$e^{rh}>e^{\sigma\sqrt{h}}$. In real applications
h. In real applications h would be small,  so this problem does not occur.
The Lognormal Tree.
Another alternative is to construct the tree using
$$u=e^{(r-\delta-0.5\sigma^{2})h+\sigma\sqrt{h}}\tag{14}$$

This procedure for generating a tree was proposed by Jarrow and Rudd (1983) and is sometimes called the Jarrow-Rudd binomial model.
All three methods of constructing a binomial tree yield different option prices for finite n,  but they approach the same price as n → ∞. Also,  while the different binomial trees all have different up and down movements,  all have the same ratio of u to d:
$$
{\frac{u}{d}}=e^{2\sigma{\sqrt{h}}}\quad{\mathrm{or}}\quad\ln(u/d)=2\sigma{\sqrt{h}}
$$
This is the sense in which,  however the tree is constructed,  the proportional distance between u and d measures volatility.
## IS THE BINOMIAL MODEL REALISTIC?
Any option pricing model relies on an assumption about the behavior of stock prices. As we have seen in this section,  the binomial model is a form of the random walk model,  adapted to modeling stock prices. The lognormal random walk model in this section assumes,  among other things,  that volatility is constant,  that "large" stock price movements do not occur,  and that returns are independent over time. All of these assumptions appear to be violated in the data.
There is ample evidence that volatility changes over time (see Bollerslev et al.,  1994).
It also appears that on occasion stocks move by a large amount. The binomial model has the property that stock price movements become smaller as the period length,  h,  becomes smaller. Occasional large price movements—"jumps"—are therefore a feature of the data inconsistent with the binomial model. Finally,  there is some evidence that stock returns are correlated across time,  with positive correlations at the short to medium term and negative correlation at long horizons (see Campbell et al.,  1997,  ch. 2).
The random walk model is a useful starting point for thinking about stock price behavior,  and it is widely used because of its elegant simplicity. However,  it is not sacrosanct.
## 4. STOCKS PAYING DISCRETE DIVIDENDS
Although it may be reasonable to assume that a stock index pays dividends continuously,  individual stocks pay dividends in discrete lumps,  quarterly or annually. In addition,  over short horizons it is frequently possible to predict the amount of the dividend. How should we price an option when the stock will pay a known dollar dividend during the life of the option? The procedure we have already developed for creating a binomial tree can accommodate this case. However,  we will also discuss a preferable alternative due to Schroder (1988).
## MODELING DISCRETE DIVIDENDS
When no dividend will be paid between time$t$and$t+h$,  we create the binomial tree. Suppose that a dividend will be paid between times$t$and$t+h$and that its future value at time$t+h$is$D$. The time$t$forward price for delivery at$t+h$is then
$$
F_{t, \, t+h}=S_{t}e^{rh}-D
$$
Since the stock price at time$t+h$will be ex-dividend,  we create the up and down moves based on the ex-dividend stock price:
$$
S_{t}^{a}=\left(S_{t}e^{rh}-D\right)e^{\sigma\sqrt{h}}\tag{15} S_{t}^{d}=\left(S_{t}e^{rh}-D\right)e^{-\sigma\sqrt{h}}
$$

How does option replication work when a dividend is prominent? When a dividend is paid,  we have to account for the fact that the stock earns the dividend. Thus,  we have
$$
 \left(S_{t}^{d}+D\right)\Delta+e^{rh}B=C_{d}
$$
The solution is
$$
\Delta=\frac{C_{u}-C_{d}}{S_{t}^{u}-S_{d}^{d}}
$$
$$
B=e^{-rh}\left[\frac{S_{t}^{u}C_{d}-S_{t}^{d}C_{u}}{S_{t}^{u}-S_{d}^{d}}\right]-\Delta De^{-rh}
$$
Because the dividend is known,  we decrease the bond position by the present value of the certain dividend. (When the dividend is proportional to the stock price,  as with a stock index,  we reduce the stock position.) The expression for the option price is given by
$$
C=e^{-rh}\left(p^{*}C_{u}+(1-p^{*})C_{d}\right)
$$
Problems with the Discrete Dividend Tree
The practical problem with this procedure is that the tree does not completely recombine after a discrete dividend. In all previous cases we have examined,  we reached the same price after a given number of up and down movements,  regardless of the order of the movements.
Figure 9,  in which a dividend with a period-2 value of$5 is paid between periods
1 and 2,  demonstrates that with a discrete dividend,  the order of up and down movements affects the price. In the third binomial period there are six rather than four possible stock prices.
To see how the tree is constructed,  period-1 prices are
$\$41e^{0.08\times1/3+0.3\times\sqrt{1/3}}=\$50.071$
$\$41e^{0.08\times1/3-0.3\times\sqrt{1/3}}=\$35.411$
first and second binomial periods. There are eight discrete terminal nodes (six of them distinct) rather than four. Assumes S =$41,  σ =
0.3,  r = 0.08,  t = 1 year,  and h = 0.333.
The period-2 prices from the$50.071 node are
($50.071e^{0.08\times1/3}-5)\times e^{0.3\times\sqrt{1/3}}=\$55.203$
($50.071e^{0.08\times1/3}-5)\times e^{-0.3\times\sqrt{1/3}}=\$39.041$
Repeating this procedure for the node S =$35.411 gives prices of$37.300 and$26.380.
You can see that there are now four prices instead of three after two binomial steps: The ud and du nodes do not recombine. There are six distinct prices in the final period as each set of ex-dividend prices generates a distinct tree (three prices arise from the top two prices in period 2 and three prices arise from the bottom two prices in period 2). Each discrete dividend causes the tree to bifurcate.
There is also a conceptual problem with equation (15). Since the amount of the dividend is fixed,  the stock price could in principle become negative if there have been large downward moves in the stock prior to the dividend.
This example demonstrates that handling fixed dividends requires care. We now turn to a method that is computationally easier than constructing a tree using equation (15) and that will not generate negative stock prices.
## A BINOMIAL TREE USING THE PREPAID FORWARD
Schroder (1988) presents an elegant method of constructing a tree for a dividend-paying stock that solves both problems encountered with the method in Figure 9. The key insight is that if we know for certain that a stock will pay a fixed dividend,  then we can view the stock price as being the sum of two components: the dividend and the present value of the exdividend value of the stock—in other words,  the prepaid forward price. With the dividend known,  all volatility is attributed to the prepaid forward component of the stock price.
Suppose we know that a stock will pay a dividend D at time TD *< T*,  where T is the expiration date of the option. For *t < T*D,  the stock price is the sum of the prepaid forward price and the present value of the dividend:
$$
S_{t}=F_{t, T}^{P}+De^{-r(T_{D}-t)}\tag{16}
$$
where F P
t, T = St − De−r(TD−t). We construct the binomial tree by attributing all uncertainty to the prepaid forward price. As before,  we have up and down movements of
$$
u=e^{r h+\sigma{\sqrt{h}}}\qquad d=e^{r h-\sigma{\sqrt{h}}}
$$
The observed stock price at time t + *h < T*D is then
$$
S_{t+h}=F_{t}^{P}e^{r h\pm\sigma{\sqrt{h}}}+D e^{-r(T_{D}-(t+h))}
$$
We measure σ by observing movements in St,  but σ is used in this equation to characterize movements in F P
t. We want the total dollar volatility of the prepaid forward to equal that of the stock,  so we assign a volatility to the prepaid forward using the *ad hoc* adjustment
$$
\sigma_{F}=\sigma_{s}\times{\frac{S}{F^{P}}}
$$
Figure 10 shows the construction of the binomial tree for a specific example,  using the same initial inputs as Figure 9. Both the observed stock price and the stock price less the present value of dividends (the prepaid forward price) are included in the figure. Assuming that the dividend is paid just before the second period,  the initial prepaid forward price is F P
0 = 41− 5e−0.08×2/3 = 36.26. The volatility for the prepaid forward is therefore
0.3 ×
$41
$36.26 = 0.3392.
To understand Figure 10,  note first that u = 1.2492. Look at the node where the stock price is$61.584. This is a *cum-dividend* price,  just before the dividend is paid. The nodes in the last period are constructed based on the *ex-dividend* price,  for example, 
($61.584-$55)$\times$1.2492 =$70.686
As a final point,  we obtain risk-neutral probabilities for the tree in the same way as in the absence of dividends. Because up and down movements are based on the prepaid forward,  which pays no dividends,  the risk-neutral probability of an up move in the prepaid forward price is given by p∗ = e(r−δ)h−d u−d
,  as for a non-dividend paying stock.
Binomial tree for pricing an American call option on a stock paying a discrete dividend of$5 in 8 months;
assumes S =$41.00,  K =
$40.00,  σ = 0.3392,  r =
0.08,  T = 1.00 years,  δ =
0.00,  and h = 0.333. At each node the stock price,  prepaid forward price,  and option price are given. Option prices in *bold italic* signify that exercise is optimal at that node.
## CHAPTER SUMMARY
Both call and put options may be rationally exercised prior to expiration. The early-exercise decision weighs three considerations: dividends on the underlying asset,  interest on the strike price,  and the insurance value of keeping the option alive. Calls will be early-exercised in order to capture dividends on the underlying stock; interest and insurance weigh against early exercise. Puts will be early-exercised in order to capture interest on the strike price; dividends and insurance weigh against early exercise. For both calls and puts,  the earlyexercise criterion becomes less stringent as the option has less time to maturity.
Risk-neutral option valuation is consistent with valuation using more traditional discounted cash flow methods. With risk-neutral pricing it is not necessary to estimate the expected return on the stock in order to price an option. With traditional discounted cash flow methods,  the correct discount rate for the option varies along the binomial tree; thus,  valuation is considerably more complicated than with risk-neutral pricing.
The binomial model,  which approximates the lognormal distribution,  is a random walk model adapted to modeling stock prices. The model assumes that the continuously compounded return on the stock is normally distributed,  which implies that the stock price is lognormally distributed.
The binomial model can be adapted to price options on a stock that pays discrete dividends. Discrete dividends can lead to a nonrecombining binomial tree. If we assume that the prepaid forward price follows a binomial process instead of the stock price,  the tree becomes recombining.

---

# BINOMIAL OPTION PRICING SELECTED TOPICS

## 2. UNDERSTANDING RISK-NEUTRAL PRICING

The binomial option pricing formula can be written$$C = e ^ { - r h } [p ^ { * } C _ { u} + (1 - p ^ { * }) C_d] \tag{1}$$
The binomial option pricing formula can be written where$$C = e ^ { - r h } [p ^ { * } C _ { u} + (1 - p ^ { * }) C_d] \tag{1}$$where$$C = e ^ { - r h } [p ^ { * } C _ { u} + (1 - p ^ { * }) C_d] \tag{1}$$where$$p ^ { * } = \frac {e ^ { (r - d) h } - d } { u - d } \tag{2}$$
- We labeled p* the risk-neutral probability that the stock will go up. Equation (1) has the appearance of a discounted expected value,  where the expected value calculation uses p and discounting is done at the risk-free rate.
- A risk-neutral investor is indifferent between a sure thing and a risky bet with an expected payoff equal to the value of the sure thing
- In such a world,  investors care only about expected returns and not about riskiness. Assets would have no risk premium since investors would be willing to hold assets with an expected return equal to the risk-free rate.
- In this hypothetical risk-neutral world,  we can solve for the probability of the stock going up,  p, such that the stock is expected to earn the risk-free rate. In the binomial model,  ∗ the probability that the stock will go up,  p,  must satisfy
- In this hypothetical risk-neutral world,  we can solve for the probability of the stock going up,  p, such that the stock is expected to earn the risk-free rate. In the binomial model,  ∗ the probability that the stock will go up,  p,  must satisfy $$p ^ { * }uSe ^ {\delta h } + (1 - p ^ { * }) d S e ^ { \delta h } = S e ^ { r h }$$
- Solving for p* gives us equation (2),  which is why we refer to p as the risk-neutral probability that the stock price will go up. It is the probability that the stock price would increase in a risk-neutral world.
- Not only would the risk-neutral probability,  equation (2),  be used in a risk-neutral world,  but also all discounting would take place at the risk-free rate.
- Thus,  the option pricing formula,  equation (1),  can be said to price options as if investors are risk-neutral.

## PRICING AN OPTION USING REAL PROBABILITIES
Suppose that the continuously compounded expected return on the stock is$\alpha$and that the stock does not pay dividends. Then if$p$is the true probability of the stock going up, $p$must be consistent with$u,  d, $and$\alpha:$$puS+(1-p)dS=e^{\alpha h}\tag{3}S$$
Solving for$p$gives us
$$
p=\frac{e^{\alpha h}-d}{u-d}\tag{4}
$$
For probabilities to be between 0 and 1,  we must have$u>e^{\alpha h}>d.$Using$p$,  the actual expected payoff to the option one period hence is$$pC_u+(1-p)C_d=\frac{e^{\alpha h}-d}{u-d}C_u+\frac{u-e^{\alpha h}}{u-d}C_d\tag{5}$$

Denote the appropriate per-period discount rate for the option as γ. To compute γ,  we can use the fact that the required return on any portfolio is the weighted average of the returns on the assets in the portfolio.

An option is equivalent to holding a portfolio consisting of  Δshares of stock and B bonds. The expected return on this portfolio is consisting of  shares of stock and B bonds. The expected return on this portfolio is

An option is equivalent to holding a portfolio consisting of  Δshares of stock and B bonds. The expected return on this portfolio is consisting of  shares of stock and B bonds. The expected return on this portfolio is$$
An option is equivalent to holding a portfolio consisting of  Δshares of stock and B bonds. The expected return on this portfolio is consisting of  shares of stock and B bonds. The expected return on this portfolio is e ^ { \gamma h } = \frac { S \Delta  } { S \Delta + B } e ^ { \alpha h } + \frac { B } {S \Delta + B } e ^ { r h }\tag{6}
An option is equivalent to holding a portfolio consisting of  Δshares of stock and B bonds. The expected return on this portfolio is consisting of  shares of stock and B bonds. The expected return on this portfolio is$$
We can now compute the option price as the expected option payoff,  equation (5),  discounted at the appropriate discount rate,  given by equation (6). This gives

![[IMG-20240913171234595.svg]]