---
title: Lecture 5Dynamic [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]
tags:
  - dynamic_portfolio_choice
  - iid_assumption
  - long_term_investor
  - portfolio_weights
  - risk_return
aliases:
  - Dynamic Portfolio Selection
  - Long-Term Investing
key_concepts:
  - Dynamic portfolio problem
  - IID setting
  - Long-term investment horizons
  - Optimal portfolio formulas
  - Predictable stock market returns
---

# Lecture 5-Dynamic Portfolio Choice
[[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]

When we derived mean-variance optimal portfolio weights in earlier lectures,  we assumed an IID setting. Moreover,  when we derived the optimal portfolio formulas,  we assumed that the investor maximizes expected utility of wealth at a one-period horizon. Based on the IID assumption,  we plugged estimates of unconditional means and covariances into the resulting optimal portfolio formula. This brings up two issues.

First,  in practice,  the horizons of some investors could be very long. Pension funds and retirement investors may have investment horizons stretching to several decades. And they don't have to buy-and-hold over this long horizon. They can reshuffle their portfolio along the way. For this reason,  we cannot necessarily just treat their multidecade horizon as one period and assume they choose a portfolio today to maximize the expected utility of wealth at the end of this long period and they then just buy and hold this portfolio. Moreover,  the mean-variance solution for the [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] that we developed in earlier lectures was based on an approximation that,  as we discussed,  was only reasonably accurate for relatively short time-horizons. Just plugging expected values and variances of long-term returns into this formula would not work well.

Second,  in the past two lectures we discussed evidence that stock market returns and volatility are predictable. This means that conditional expected returns in excess of risk-free rates and conditional volatility appear to be varying over time. If a long-term investor is aware of this,  and therefore anticipates that risky asset returns will not be IID over the investment horizon,  does this change the portfolio weights that investor should choose initially?

In this lecture,  we therefore consider the dynamic [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] problem: how should a long-term investor optimally choose a portfolio in each period along the way until the end of the investment horizon? As it turns out,  the question of how to choose a dynamically optimal portfolio for a long-term investor is actually an enormously challenging problem that defies exact calculation with nice formulas - even if one used advanced mathematical tools far beyond what's feasible in this course. It is difficult because

there are so many moving parts that could possibly be interdependent in complicated ways. The portfolio return at $t+1$ depends on the portfolio weight $\omega_{t}$ we choose at $t$; the return at $t+2$ depends on the weight we choose at $t+1$,  etc.,  so there are lots of choices to be made. And if market conditions (expected returns and risk) are changing over time,  presumably these weights should change with these conditions? And if we anticipate that these conditions and our portfolio weights could change at next period,  or in periods in the more distant future,  shouldn't this already influence how we position the portfolio today?

We will approach this problem by first looking properties of risk and return over the long-run. Then we turn to the general dynamic [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] problem to understand better why it is so difficult. Then we consider a number of simplified approaches. These simplified approaches will allow discover some principles that should guide long-term [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]. To keep the analysis sufficiently tractable so that we can still get to some insights,  we will focus on the case where we choose between a single risky asset (think a stock index) and a risk-free asset. This way we can focus on the dynamic aspects of how risk,  return,  and [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]s intermingle and compound over time,  with fewer complications from the question of how to choose among risky assets.

For most of the analyses below,  we also make some statistical assumptions. These assumptions need to be both empirically plausible and,  at the same time,  also give us tractability. We assume that the risky asset returns are conditionally log-normal,  with log returns generated as

$$

\begin{equation*}

r_{t+1}=r_{f}+\mu_{t}+\sigma \varepsilon_{t+1},    \quad \varepsilon_{t+1} \sim \mathcal{N}(0,   1) \tag{5.1}

\end{equation*}

$$

For simplicity,  we assume that the risk-free rate is constant and conditional variance is constant as well. So we focus on deviations from the IID setting that arise because $\mu_{t}=\mathbb{E}_{t}\left[r_{t+1}\right]-r_{f}$ can be time-varying. Time-variation in $\mu_{t}$ is motivated by the evidence we discussed in the last couple of lectures that stock index expected returns appear to be varying over time in a predictable way,  e.g.,  as captured by valuation ratios such as the price-dividend ratio. Then,  the conditionally expected one-period simple return is

$$

\begin{equation*}

\mathbb{E}_{t}\left[R_{t+1}\right]=\exp \left(r_{f}+\mu_{t}+\frac{1}{2} \sigma^{2}\right)-1 \tag{5.2}

\end{equation*}

$$

This expression is similar to the expected value of log-normally distributed returns that we discussed in Lecture 3,  just here with a time-varying conditional mean (while in Lecture 3 we discussed IID returns).

We further assume that unexpected shocks to $\mu_{t}$ are drawn from a joint normal distribution with the $\varepsilon_{t}$ shocks ( $\mu_{t}$ will typically be persistent over time,  e.g.,  an $\operatorname{AR}(1)$ process). This means that $r_{t+1}$ is not only normally distributed conditional on $\mu_{t}$,  but also unconditionally.

### 5.1 Properties of long-run risky asset returns

The properties of the [[Lecture 1- Probability Distributions of Returns|probability distribution]] of long-term investor's final wealth depend on the portfolio weights and the [[Lecture 1- Probability Distributions of Returns|probability distribution]] of long-term returns. As a first step,  it is therefore useful to get a better understanding of the properties of long-run returns and how they relate to the properties of short-run returns.

### 5.1.1 Long-run return

The long-run growth of wealth,  or the long-run return,  from investing in a risky asset from the end of period $t$ until $t+h$ is

$$

\begin{align*}

R_{t: t+h} & =\left(1+R_{t+1}\right)\left(1+R_{t+2}\right) \times \ldots \times\left(1+R_{t+h}\right)-1 \\

& =\exp \left(\sum_{s=t+1}^{t+h} r_{s}\right)-1 \tag{5.3}

\end{align*}

$$

At long horizons,  the effects coming from compounding of returns can be substantial and they make the effects of a change in the rate of return nonlinear,  especially at high rates of return. For example,  earning an annual return of $20 \%$ for 10 years yields a 10-year return of about $500 \%$,  but doubling the return to $40 \%$ per year leads to a much more than doubling of the 10-year return to about 2,  800%.

This bring up the question how we could estimate the expected long-run return. One approach we could consider is to simply measure $R_{t: t+h}$ in the past data and compute the average $R_{t: t+h}$ and use this as our estimate of $\mathbb{E}\left[R_{t: t+h}\right]$. But since long-term returns have skewed distributions (recall our discussion in lecture 3 that downside in the long-run is limited at $-100 \%$ while the upside is unlimited),  taking means of long-run returns may produce somewhat unreliable estimates of expected long-run returns. Compounding some estimate of a mean short-run return may deliver a more precise estimate of the expected long-run return.

There may also be many situations in which it is simply not feasible to estimate average long-run returns on historical data. For example,  you may not have access to the historical data itself,  but just summary measures of mean short-term returns that someone else has calculated. Is there a way to compound these short-term mean returns to get an estimate of long-run expected return?

Given the powerful effects of compounding at long-horizons,  it may seem natural

then to rely on the geometric mean,

$$

\begin{equation*}

\left[\left(1+R_{1}\right) \times\left(1+R_{2}\right) \times \ldots \times\left(1+R_{T}\right)\right]^{\frac{1}{T}}-1=\exp \left(\frac{1}{T} \sum_{t=1}^{T} r_{t}\right)-1 \tag{5.4}

\end{equation*}

$$

and then compound this geometric mean to get an estimate of the long-term expected return. Unlike the arithmetic mean

$$

\begin{equation*}

\frac{1}{T} \sum_{t=1}^{T} R_{t} \tag{5.5}

\end{equation*}

$$

the geometric mean takes into account the effects of compounding. There is an active debate among investment practitioners whether the geometric or the arithmetic is more appropriate for estimating the expected long-run return of various asset classes.

The geometric mean is always weakly smaller than the arithmetic mean. In the case where all returns in all periods are equal,  the arithmetic mean and geometric mean are equal,  too. Otherwise,  the geometric mean is smaller. One quick way of getting the intuition which of the two means is lower is to think of the case in which the return in the last period is $-100 \%$,  i.e.,  a total loss. In this case,  the geometric mean is always $-100 \%$,  irrespective of what the returns are in the other periods before the last. In contrast,  the arithmetic mean can be well above $-100 \%$.

Many people intuitively think that,  therefore,  compounding the geometric mean should be the appropriate way to estimate the long-run expected returns because this approach "properly" reflects the effects of compounding on the long-run return. Their reasoning typically goes as follows: When an asset goes first up and then back down to the same price,  with a compounded two-period return of zero,  the percentage increase is bigger than the percentage decrease. But the arithmetic mean averages the increase and decrease and hence comes to a misleading result. For example,  with a sequence of two returns of $+50 %,   -33.33 \%$,  these two returns have arithmetic mean of $8.34 \%$,  i.e.,  greater than zero,  but obviously this sequence leaves you with unchanged wealth at the end as $(1+0.50) \times(1-0.3333)-1 \approx 0$. So the arithmetic mean seems to overstate the expected long-run return?

This thinking is a fallacy! Suppose that $+50 %,   -33.33 \%$ are the two only possible returns,  each with equal probability. There are two periods. So the "long-run" here is two periods,  and the "short-run" is one period. What are the possible outcomes for the factor by which wealth grows (or falls) over these two periods? There are four,  each with probability $\frac{1}{4}$ :

$(1+0.50) \times(1+0.50)=2.25$

$(1+0.50) \times(1-0.3333)=1$

$(1-0.3333) \times(1+0.50)=1$

$\cdot$ $(1-0.3333) \times(1-0.3333)=0.4445$

Averaging across these four possible outcomes (as each has equal probability) we get an average of about 1.174 . This means the expected long-run return is $17.4 \%$. What would one get if one takes an arithmetic mean or geometric mean from a long sample of returns in this world and then compounds this mean return?

The arithmetic mean of a long sample of equally likely ${} +50 \%,   -33.33 \%$ returns is $8.34 \%$. Compounding this arithmetic mean of $8.34 \%$ delivers $(1+0.0834)^{2}-1 \approx 0.174$,  which is the correct expected long-run return! In contrast,  the geometric mean is too pessimistic. The geometric mean of a long sample of equally likely ${} +50 \%,   -33.33 \%$ returns is $0 \%$. Compounding it yields $0 \%$,  which is obviously not the correct answer.

In some sense,  the geometric mean pays too much attention to the downside and not enough to the upside. More precisely,  it does not give enough consideration to the fact that going up twice in a row by $50 \%$ produces a long-term return that leads to an overall gain in percentage terms ( $125 \%$ ) that far exceeds the loss of going down twice by $33 \%$ ${} (-55 \%)$.

Similarly,  someone who focuses just on sequences in which the two possible realizations alternate,  as in the "typical reasoning" above,  i.e.,  ${} +50 \%,   -33.33 \%$,  or $-33.33 \%$ followed by $+50 \%$ gets a geometric mean of

$$

\begin{equation*}

\exp \left[\frac{1}{2} \log (1+0.50)+\frac{1}{2} \log (1-0.3333)\right]-1 \approx 0 \tag{5.6}

\end{equation*}

$$

Compounding this number again leads to an expected long-run return estimate that is too low. The two sequences of returns considered in this reasoning are the two out of four possible price sequences in which prices happen to be,  by chance,  strongly mean reverting. Each return is followed by a return of the opposite sign. But focusing only on these ignores that there can also be continuation sequences where returns are positive (or negative) twice in a row. And one of these continuation sequences has,  due to compounding,  a huge upside of $+125 \%$ return.

We can see this more generally if we assume IID log-normally distributed returns.

The expected long-run return under log-normal distribution is

$$

\begin{align*}

\mathbb{E}\left[R_{t: t+h}\right] & =\exp \left[\log \left(1+\mathbb{E} R_{t: t+h}\right)\right]-1  \tag{5.7}\\

& =\exp \left[\mathbb{E} r_{t: t+h}+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}\right)\right]-1  \tag{5.8}\\

& =\exp \left(h \mathbb{E} r_{t+1}+\frac{1}{2} h \sigma^{2}\right)-1  \tag{5.9}\\

& =\exp \left(h \log \mathbb{E}\left[1+R_{t+1}\right]\right)-1  \tag{5.10}\\

& =\left(\mathbb{E}\left[1+R_{t+1}\right]\right)^{h}-1 \tag{5.11}

\end{align*}

$$

So this tells us explicitly that if we want to forecast the long-term return,  we should compound the short-run expected return. And the standard way of estimating the short-run expected return $\mathbb{E}\left[R_{t+1}\right]$ is to take the arithmetic mean of short-term returns. Statistical theory tells us that the arithmetic mean of simple returns converges to $\mathbb{E}\left[R_{t+1}\right]$ in a large sample. Therefore,  to estimate the long-term expected return,  we should compound the arithmetic mean of short-term returns.

In the case of log-normally distributed returns,  we can also calculate the wedge between the geometric and arithmetic mean. In a large sample,  as the sample size $T \rightarrow \infty$,  the arithmetic mean converges to $\mathbb{E}\left[R_{t}\right]$,  and,  using the IID special case of (5.2),  this expected simple return is

$$

\begin{equation*}

\mathbb{E}\left[R_{t}\right]=\exp \left[\mathbb{E}\left[r_{t}\right]+\frac{1}{2} \operatorname{var}\left(r_{t}\right)\right]-1 \tag{5.12}

\end{equation*}

$$

In contrast,  the geometric mean in (5.4) converges to

$$

\begin{equation*}

\exp \left(\mathbb{E}\left[r_{t}\right]\right)-1 \tag{5.13}

\end{equation*}

$$

Comparing the two,  we see that

$$

\begin{equation*}

(1+\text { arithmetic mean })=(1+\text { geometric mean }) \times \exp \left[\frac{1}{2} \operatorname{var}\left(r_{t}\right)\right] \tag{5.14}

\end{equation*}

$$

Since $\exp \left[\frac{1}{2} \operatorname{var}\left(r_{t}\right)\right] \geq 1$,  the arithmetic mean is always weakly greater than the geometric mean,  and they are equal only in the case of zero variance.

If the return measurement periods are relatively short (daily,  monthly,  quarterly),  then the arithmetic mean is approximately equal to $\mathbb{E}\left[r_{t}\right]+\frac{1}{2} \operatorname{var}\left(r_{t}\right)$ and the geometric mean is approximately equal to $\mathbb{E}\left[r_{t}\right]$,  and so

$$

\begin{equation*}

\text { arithmetic mean } \approx \text { geometric mean }+\frac{1}{2} \operatorname{var}\left(r_{t}\right) \tag{5.15}

\end{equation*}

$$

What if returns are not IID? For example,  what if the asset price is mean-reverting so that following a high return in period $t$,  the expected return for period $t+1$ is lower than following a low return in period $t$ ? In this case,  returns are negatively autocorrelated. We won't develop explicit general formulas for this case,  but we can get some intuition from our simple example above. Let's take the extreme case where prices are completely mean-reverting so that the two sequences with ${} +50 \%,   -33.33 \%$ or ${} -33.33 \%,   +50 \%$ are in fact the only possibilities,  each now with probability $\frac{1}{2}$. Wealth growth is zero over the two periods in each case. Hence,  the long-run expected return is now zero. The arithmetic mean of a long series of returns is still $8.34 \%$ in this case,  so compounding the arithmetic mean now overstates the expected long-run returns. The geometric mean is zero and compounding it delivers the correct result of expected long-run return of zero.

In summary,  only in this extreme case of complete mean reversion where the price level does not change in the long run,  and prices always bounce up and down around the same long-run price level,  compounding the geometric mean delivers the correct estimate of the expected long-run return. In contrast,  in the IID case,  without any autocorrelation in returns,  compounding the arithmetic mean delivers the correct estimate.

The extreme case of complete mean reversion is clearly not empirically realistic. But stock returns are not necessarily IID either. The evidence we discussed in the previous two lectures suggests that stock prices go through valuation cycles where stock price booms are followed,  at least to some extent predictably,  by low returns. So there is a certain degree of mean-reversion in stock price levels. How do the arithmetic and geometric mean perform as estimators of the long-run expected return in intermediate cases where prices have some tendency to mean-revert,  but not as strongly as in the extreme example we considered above?

We can examine the effects of mean-reversion in the simulations of the sentiment model from Lecture 3. Recall that in this model sentiment followed an $\operatorname{AR}(1)$ process with autocorrelation coefficient of $\phi$. This parameter $\phi$ controls the persistence of sentiment. If $\phi$ is low,  then sentiment is quickly mean reverting. This means that the asset price is then also quickly mean-reverting. In other words,  with low $\phi$,  the asset price goes through short-lived cycles of overand undervaluation and returns are strongly negatively autocorrelated. If $\phi$ is high,  then sentiment is highly persistent,  the overand undervaluation cycles are much longer,  price mean-reversion is weaker,  and negative autocorrelation of returns is weaker,  too. Let's see how these different degrees of mean-reversion affect the wedges between expected long-run returns and compounded arithmetic and geometric means.

As in Table 3.1 in Lecture 3,  I generate 1,  000 simulated series of returns and sentiment,  each with length 400 quarters. I repeat this for different values of $\phi$. For each

value of $\phi$ I choose the volatility of sentiment shocks such that sentiment always has a standard deviation of 0.20 . I also do one set of simulations in which I set sentiment to zero (no-sentiment case).

Table 5.1: Estimation of expected long-run returns in the sentiment model

|   | $\phi=0.15$ | $\phi=0.55$ | $\phi=0.95$ | No sentiment |

| --- | --- | --- | --- | --- |

| $\mathbb{E}\left[R_{t: t+40}\right]$ |   |   |   |   |

| $(1+\text { arithm. mean })^{40}-1$ | 8.57 | 1.57 | 1.57 | 1.47 |

| $(1+\text { geom. mean })^{40}-1$ | 1.24 | 4.02 | 1.67 | 1.47 |

|   |   |   | 1.24 | 1.24 |

Table 5.1 shows the result. Let's focus first on the last column. It shows the results from the simulation for the case where sentiment is always zero. In this case,  there is no mean-reversion in prices and returns are IID. The expected return over a 10-year (40quarter) horizon in this case is $147 \%$. As our analysis above suggested,  compounding the arithmetic mean of the simulated returns delivers exactly the same result: $147 \%$. In contrast,  compounding the geometric mean of the simulated results yields an estimate of $124 \%$ that is too low relative to the true expected 10-year return.

To see the effects of extremely strong mean-reversion,  consider the first column where $\phi=0.15$ and hence sentiment has low persistence. In this (unrealistic) case,  compounding the arithmetic mean yields a wildly inaccurate estimate of $842 \%$ compared with a true expected 10-year return of $157 \%$. The compounded geometric mean in this case is again $124 \%$ and so too low relative to the true expected 10 -year return,  but it's much closer than the compounded arithmetic mean.

In the more realistic case of $\phi=0.95$ (which,  as we discussed in Lecture 3 produces a log price-dividend ratio that is roughly as persistent as the log price-dividend in empirical data),  the situation is very different. Now the compounded arithmetic mean of $167 \%$ is closer to the true expected 10-year return of $157 \%$ than the compounded geometric mean,  which is again $124 \% .^{1}$

Table 5.2 shows how this looks like in empirical data. I use quarterly returns on the CRSP value-weighted stock index from 1927 to 2022. The first row in the table

[^20]Table 5.2: Estimation of expected long-run returns for the CRSP value-weighted stock market index,  1927-2022

| $\frac{1}{T} \sum_{t=1}^{T-40} R_{t: t+40}$ | 2.01 |

| --- | --- |

| $(1+\text { arithm. mean })^{40}-1$ | 2.14 |

| $(1+\text { geom. mean })^{40}-1$ | 1.51 |

shows the average of 10-year (40-quarter) returns as an estimate of the expected 10-year return. The rows below show what we get if we use the compounded arithmetic or the compounded geometric mean as estimates of the 10 -year expected return. The results look remarkably similar to the ones from the simulations with $\phi=0.95$ : Compounding the arithmetic mean delivers an estimate that is a bit too high,  but it's closer to the average 10-year return than the estimate based on compounding the geometric mean.

The bottom line is that,  for realistic return distributions,  compounding the arithmetic mean delivers a better estimate of the expected long-run return than compounding the geometric mean. Therefore,  despite the intuitive appeal of the geometric mean,  one should not rely on the geometric mean for this purpose unless one has reason to believe that mean-reversion in prices is extremely strong. There also exist formulas for long-run expected return estimation that compound a weighted average of the arithmetic and geometric mean. These formulas require an estimate of the autocorrelation of returns,  which then determines the relative weights of the arithmetic and geometric means.

Finally,  estimation error can be a reason,  even in the IID case,  to put weight on the geometric mean when estimating long-run expected returns. In the analysis so far,  we implicitly considered a situation where the sample used to estimate arithmetic and geometric means are substantially longer (let's use $T$ to denote the length) than the horizon ( $h$ ) over which we are estimating long-run expected returns. But when $T$ is not much larger than $h$,  then compounding magnifies estimation error that generates an upward bias in the compounded arithmetic mean as estimate of long-run expected return,  while the downward bias in the compounded geometric mean shrinks. In this case,  it is optimal to use a weighted average of compounded geometric and arithmetic

mean to estimate long-run expected return. ${ }^{2}$

### 5.1.2 Long-run risk

Now let's turn to the risk properties of long-run returns,  and more specifically,  the volatility of long-run returns.

With regards to the riskiness of long-run stock market investments,  there is an important debate among investment practitioners that has been going on for decades: Are stocks less risky for a long-term investor than for a short-term investor? The notion that they are less risky for a long-term investor because of mean reversion in stock prices has been popularized by the book Stocks for the Long-Run by Wharton finance professor Jeremy Siegel.

Others have suggested that even with IID returns,  i.e.,  without mean-reversion,  stocks are less risky in the long-run due to time-diversification. The argument is that because of the law of large numbers,  the average return of a stock portfolio converges to its expected return in the long-run,  hence it's safer in the long-run than in the short-run. This argument turns out to be a fallacy. The variance of the average return does indeed decline due to the law of large numbers as we lengthen the horizon. However,  a longterm investor investor cares about the variance of return per period,  not the variance of the average return.

Note first that the long-run return in (5.3) depends on the sum of log returns,  or,  equivalently,  the long-run log return:

$$

\begin{align*}

r_{t: t+h} & =\log \left(1+R_{t: t+h}\right) \\

& =r_{t}+r_{t+1}+\ldots .+r_{t+h} \tag{5.17}

\end{align*}

$$

In general,  the variance of a sum of random variables depends on the correlation of the random variables in the sum. In the IID case the autocorrelation is zero and so

$$

\begin{equation*}

\operatorname{var}\left(r_{t: t+h}\right)=h \sigma^{2},    \quad \sigma^{2}=\operatorname{var}\left(r_{t}\right) \tag{5.18}

\end{equation*}

$$

[^21]i.e.,  the variance of log long-run returns simply scales proportionally with the horizon $h$.

This calculation shows that there is no disappearance of risk in the long run for a longterm investor,  i.e.,  there is no time-diversification effect with IID returns. The per-period variance that an investor is exposed to,  $\operatorname{var}\left(r_{t: t+h}\right) / h=\sigma^{2}$,  is therefore independent of the holding horizon of the investor.

The fallacy of the time-diversification argument lies in the focus on the standard deviation of the average return over long periods. It is true that the variance of the average per-period $\log$ return $\frac{1}{h} r_{t: t+h}$ shrinks with increasing horizon $h$. But a longterm investor does not care about the variance of the average per-period return. For a long-term investor risk is represented by the average per-period variance of returns from $t$ to $t+h$ (we will see this explicitly later when we look at a solution for a longrun investor's portfolio problem). And as we just figured out,  this average per period variance,  $\operatorname{var}\left(r_{t: t+h}\right) / h$,  is independent of the investment horizon $h$.

But when returns are not IID,  $\operatorname{var}\left(r_{t: t+h}\right) / h$,  can depend on the horizon $h$. For example,  with mean-reversion in prices,  risk can indeed disappear to some extent in the long run because short-term movements in asset prices partly offset each other over time.

We can see this if we go back to our simulated valuation model with [[Lecture 4- Investor Sentiment|investor sentiment]] from lecture 3. When $\phi$ is close to one in this model,  sentiment is very persistent and sentiment-induced mispricing takes a very long time to correct. When $\phi$ is close to zero,  sentiment quickly changes and mispricing rapidly corrects,  which makes prices strongly mean-reverting and returns strongly negatively autocorrelated. We can use these simulations to study the effect of mean reversion on long-run return volatility.

Using the same simulated data as in Table 5.1,  I calculate calculate the variance of quarterly $\log$ returns and $(1 / 40) \times$ the variance of 10 -year log returns. ${ }^{3}$ Table 5.3 shows the result.

Focusing first on the no-sentiment case in the right-most column,  returns in this case are IID. As expected,  in this case $(1 / 40) \times$ the variance of 10 -year log returns is exactly equal to the variance of quarterly log returns

[^22]Table 5.3: Risk at short and long horizons in the sentiment model

|   | $\phi=0.15$ | $\phi=0.55$ | $\phi=0.95$ | No sentiment |

| --- | --- | --- | --- | --- |

| Var. Quarterly Log Return | 0.072 | 0.040 | 0.009 | 0.005 |

| $(1 / 40) \times$ Var. 10-year Log Return | 0.007 | 0.007 | 0.007 | 0.005 |

In the case where mean reversion is extremely strong,  in the first column for $\phi=0.15$,  the per-period long-run log return variance is far lower than in the IID case. The strong mean reversion eliminates a lot of the risk in the long-run. As a consequence,  $(1 / 40) \times$ the variance of 10 -year log returns is far lower than the variance of quarterly log returns. Of course,  the extreme mean reversion implied by $\phi=0.15$ is far too strong to be empirically realistic. With the more realistic $\phi=0.95$,  the difference is much less dramatic. But even in this case,  stocks are still substantially less risky in the long run than in the short run in the simulated model.

Table 5.4: Risk at short and long horizons for the CRSP value-weighted stock market index,  1927-2022

Var. Quarterly Log Return 0.0110

$(1 / 40) \times$ Var. 10-year Log Return 0.0066

What about empirical data? Table 5.4 shows a similar exercise using empirical data from the CRSP value-weighted stock market index. The situation looks very similar to the sentiment model with $\phi=0.95$. The variance of quarterly log returns is substantially higher than $(1 / 40) \times$ the variance of 10 -year log returns. Thus,  there is evidence that mean-reversion annihilates some risk in the long run. Stocks are a little safer in the long run than in the short run.

### 5.2 The general dynamic portfolio problem

Let's now turn to optimal [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] for a long-term investor. Consider an investor who maximizes expected utility over final wealth after $h$ periods. Assume this investor has CRRA (constant relative risk aversion) preferences,  i.e.,  utility is

$$

\begin{equation*}

U\left(W_{t+h}\right)=\frac{W_{t+h}^{1-\gamma}-1}{1-\gamma} \tag{5.19}

\end{equation*}

$$

if $\gamma \neq 1$ and

$$

\begin{equation*}

U\left(W_{t+h}\right)=\log \left(W_{t+h}\right) \tag{5.20}

\end{equation*}

$$

if $\gamma=1$. The investor's problem is,  at $t$,  to find portfolio weights $\omega_{t}$,  that satisfy the criterion

$$

\begin{equation*}

\max _{\omega_{t}} \mathbb{E}_{t}\left[U\left(W_{t+h}\right)\right] \tag{5.21}

\end{equation*}

$$

The wealth level at the end of the investment horizon is

$$

\begin{equation*}

W_{t+h}=W_{t}\left(1+R_{p,    t: t+h}\right),    \tag{5.22}

\end{equation*}

$$

where $R_{p,    t: t+h}$ is the return on the wealth portfolio from $t$ to $t+h$,  which can be written as

$$

\begin{equation*}

R_{p,    t: t+h}=\left(1+R_{p,    t+1}\right) \times\left(1+R_{p,    t+2}\right) \times \ldots \times\left(1+R_{p,    t+h}\right)-1 \tag{5.23}

\end{equation*}

$$

or with $\log$ returns as

$$

\begin{equation*}

R_{p,    t: t+h}=\exp \left(r_{p,    t: t+h}\right)-1,    \quad \text { where } \quad r_{p,    t: t+h}=r_{p,    t+1}+r_{p,    t+2}+\ldots+r_{p,    t+h} \tag{5.24}

\end{equation*}

$$

To analyze long-run dynamics of risk and return,  log returns are much more convenient to work with than simple returns because they convert multiplicative compounding into simple summation. But the problem with using log returns to analyze portfolios is that the log portfolio return does not have a simple relationship to the log returns of the assets in the portfolio. To see this,  consider the return on a portfolio that puts weight $\omega_{t}$ on a risky asset with return $R_{t+1}$ and the rest in the risk-free asset with return $R_{f}$ :

$$

\begin{equation*}

R_{p,    t+1}=R_{f}+\omega_{t}\left(R_{t+1}-R_{f}\right) \tag{5.25}

\end{equation*}

$$

Taking logs of this,  with

$$

\begin{equation*}

\log \left(1+R_{p,    t+1}\right)=\log \left[1+R_{f}+\omega_{t}\left(R_{t+1}-R_{f}\right)\right] \tag{5.26}

\end{equation*}

$$

the right-hand side is a rather intractable nonlinear function. Unlike for simple returns,  the log return on the portfolio is not a simple weighted average of the log returns of the assets in the portfolio. But for long-run analyses we want to work with log returns to exploit the convenience of the additive (rather than multiplicative) nature of long-run $\log$ returns.

### 5.2.1 Approximation of the log portfolio return

To break this intractability,  we use a second-order Taylor approximation of the log portfolio return. We don't need to go into the details of how to do this,  but what we obtain,  for $r_{p,    t+1}=\log \left(1+R_{p,    t+1}\right)$,  is the following:

$$

\begin{equation*}

r_{p,    t+1} \approx r_{f}+\omega_{t}\left(r_{t+1}-r_{f}\right)+\frac{1}{2} \omega_{t}\left(1-\omega_{t}\right) \sigma^{2} \tag{5.27}

\end{equation*}

$$

where $\sigma^{2}=\operatorname{var}\left(r_{t+1}\right)$ and $r_{f}=\log \left(1+R_{f}\right){ }^{4}$ With this approximation,  the calculation of the portfolio log return is not quite as straightforward as the calculation of the simple portfolio return,  because we not only have the weighted average of $r_{t+1}$ and $r_{f}$,  but also the term $\omega_{t}\left(1-\omega_{t}\right)$. But still,  it's a lot more tractable than the nonlinear function we approximated.

As for any approximation,  it is useful to understand when the approximation works well and when it does not. To illustrate,  suppose we want to measure the log portfolio return $r_{p,    t+1}$ over a one-quarter horizon after we picked a portfolio weight $\omega_{t}$ at the beginning of the quarter.

The approximation in (5.27) is exact if returns are log-normal even over infinitesimally small return measurement periods (which means there are never any discrete jumps in the stock price),  and the portfolio is continuously rebalanced within the quarter back to the portfolio weight $\omega_{t}$ that we chose at the start of the quarter,  with infinitesimally small time intervals between rebalancing points.

The further reality deviates from these conditions,  the bigger will be the approximation error. When returns are not extreme (e.g.,  no extremely large stock market crashes) and time-interval of between rebalancing points not too long (e.g.,  daily rather than multi-year intervals),  the approximation is quite accurate. But we do need to keep in mind what the conditions are under which the approximation could work poorly.

Perhaps most important to keep in mind is that approximation errors in (5.27) can become particularly troublesome for levered portfolios. If one chooses a debt-financed levered portfolio,  with $\omega_{t}>1$,  and portfolio rebalancing is only possible at discrete time intervals (say,  once per month),  not continuously,  then there is a possibility that wealth could fall to zero (and without limited liability it would be negative). For example,  if an investor with 1 $\mathrm{~m}$ wealth has 10 $\mathrm{~m}$ invested in stocks financed with 9 $\mathrm{~m}$ of debt,  a return equal to or worse than $-10 \%$ percent return would completely wipe out all wealth. The probability of this happening may be tiny,  but it is not zero. So what about the log return on our portfolio in this case of total wipeout where the simple return on the portfolio is $-100 \%$ ? Well,  the log return does not even exist! In this case the log return would be $\log (1-1)=\log (0)$,  but $\log$ of zero is not defined,  nor is $\log$ of a negative number. So it's not even possible to calculate a log return when we have a total loss on the portfolio,  or when our wealth becomes negative.

Yet,  if we look at the approximation formula (5.27),  for $\omega_{t}=10$,

$$

\begin{equation*}

r_{p,    t+1} \approx r_{f}+10 \times\left(r_{t+1}-r_{f}\right)-45 \times \sigma^{2} \tag{5.28}

\end{equation*}

$$

[^23]we see that for a very low $r_{t+1}$ with a huge negative value,  the portfolio $\log$ return $r_{p,    t+1}$ can be very deep in negative territory. But,  no matter how deep in negative territory it is,  $\exp \left(r_{p,    t+1}\right)$ always greater than zero and hence the implied simple portfolio return $R_{p,    t+1}=\exp \left(r_{p,    t+1}\right)-1$ is always greater than $-100 \%$. So,  based on the approximation formula,  one could falsely conclude that wealth can never fall to zero,  no matter how high leverage is and no matter how bad the return on our assets. But this an artifact of approximation error. The actual value of a leveraged portfolio can fall to zero (or below - at this point it is then a question whether limited liability protects the leveraged borrower).

Of course,  if the investor rebalanced at extremely high frequency,  say every minute in this example,  then even in a month with $-10 \%$ return,  the investor's wealth would not be wiped out unless this $-10 \%$ return takes place in a single minute (which is extremely unlikely). If the negative return is instead due to many smaller increments of negative returns,  then frequent rebalancing would have already de-risked the portfolio after the first small loss before the second small loss hits,  and again it would have been rebalanced before the third small loss hits,  etc. So when we use this approximation formula for the log portfolio return,  we are implicitly assuming that the investor will be rebalancing the portfolio to always get back to $\omega_{t}$ at extremely high frequency.

### 5.2.2 Intractability of the dynamic portfolio problem

Equipped with the portfolio return approximation,  let's now have a look at how optimal portfolios should be chosen when returns are not IID. In lecture 1,  we used a linear approximation of marginal utility to solve the portfolio problem. We don't need this approximation here. Instead,  in the multi-period,  non-IID case here,  we can get a simplification of the problem by assuming,  along the lines laid out at the beginning of this chapter,  that returns are conditionally and unconditionally log-normally distributed. In addition,  we use the log portfolio return approximation (5.27).

However,  even under these assumptions that help make the problem more tractable,  the general problem (5.21) is difficult to solve. But we will be able to get simple formulas in a few useful special cases.

But before we look at these special cases,  let's first have a look at why the general problem is so difficult. The key difficulty is that to figure out the best portfolio weight,  $\omega_{t}$,  in period $t$,  we need to assess the riskiness of the long-term portfolio log return

$$

\begin{equation*}

r_{p,    t: t+h}=r_{p,    t+1}+r_{p,    t+2}+\ldots+r_{p,    t+h} \tag{5.29}

\end{equation*}

$$

More precisely,  we would need to be able to assess how the long-run riskiness changes when we consider a change in $\omega_{t}$. This is very difficult. The difficulty arises from two sources.

To see the first difficulty,  note first that the riskiness of the long-term returns will depend on the degree of mean-reversion in risky asset prices. For example,  the evidence we discussed in the previous section suggests that stocks may be somewhat less risky in the long-run than in the short run. But if there is mean-reversion,  how much risk reduction there will be depends not only on the properties of stock market returns,  but also on how much weight we will will have in stocks in future periods,  i.e.,  it depends on future portfolio weights $\omega_{t+1},    \omega_{t+2},    \ldots$.

To illustrate,  consider an example with a two-period horizon,  $h=2$ where mean reversion is extremely strong and the previous period's log return completely reverts with no new random shock in the second period $r_{t+2}=-r_{t+1}$ without a new random shock in $t+2$. In this case,  an investor holding the asset until $t+1$ faces risk,  but and investor holding it for two periods does not because $r_{t: t+2}=r_{t+1}+r_{t+2}=0$. But what if the investor finds it optimal to not hold the risky asset at all in the second period? If,  for example,  $\omega_{t}=1$ is optimal,  but in the next period the investor finds $\omega_{t+1}=0$ to be optimal,  then the portfolio return from the first period,  $\left(r_{p,    t+1}=r_{t+1}\right)$ will not cancel out with the portfolio return in the second period $\left(r_{p,    t+1}=r_{f}\right)$. So whether the portfolio return is mean-reverting depends on the future portfolio weights that we don't know yet at time $t$.

The second problem is that the uncertain future portfolio weights $\omega_{t+1},    \omega_{t+2},    \ldots$ introduce additional sources of randomness in future portfolio returns that make the longterm portfolio return non-log-normal,  even if the risky asset returns are log-normally distributed.

But in certain special cases,  the problem gets much simpler.

### 5.3 Growth-optimal portfolio

Recall from lecture 1 that for CRRA preferences with $\gamma=1$,  utility takes the simple form $U\left(W_{t}\right)=\log \left(W_{t}\right)$,  which is why we refer to this special case as the log utility case. In this case,  the dynamic portfolio problem is to maximize

$$

\begin{align*}

\mathbb{E}_{t}\left[U\left(W_{T}\right)\right] & =\mathbb{E}_{t}\left[\log \left(W_{t+h}\right)\right] \\

& =\log \left(W_{t}\right)+\mathbb{E}_{t}\left[\log \left(r_{p,    t: t+h}\right)\right] \\

& =\log \left(W_{t}\right)+r_{p,    t+1}+r_{p,    t+2}+\ldots+r_{p,    t+h} \tag{5.30}

\end{align*}

$$

Maximizing this expected utility for $\gamma=1$ is equivalent to maximizing the expected log long-run return on the portfolio. Since the portfolio return is a sum of individual period $\log$ returns,  and the portfolio weight $\omega_{t}$ only affects the period $t+1$ portfolio return,  and not the other returns in the more distant future,  this objective calls simply for choosing $\omega_{t}$ to maximize $\mathbb{E}_{t}\left[r_{p,    t+1}\right]$. In other words,  the dynamic multi-period problem reduces to a simple one-period problem that calls for maximizing the expected log portfolio return over the next period! The problem simplifies nicely in this special case.

As we will see now,  this solution in the $\gamma=1$ case is closely connected to an approach to dynamic [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] that has a devoted following among some investment practitioners. The approach is sometimes advertised as a universally preferable approach that is suitable for any investor irrespective of their risk preferences. As we will see,  this claim does not make sense. But let's first look at the approach.

The idea is to look for portfolio weights that maximize the long-run growth rate of wealth,  or,  equivalently,  the geometric mean return. This portfolio is known as the growth-optimal portfolio,  or a portfolio selected according to the Kelly Criterion.

The geometric mean of the portfolio return $R_{p,    t}$ over the next $h$ periods is

$$

\begin{equation*}

\exp \left(\frac{1}{h} \sum_{s=t+1}^{t+h} r_{p,    s}\right)-1 \tag{5.31}

\end{equation*}

$$

As we take the horizon $h$ to infinity,

$$

\begin{equation*}

\lim _{h \rightarrow \infty} \exp \left(\frac{1}{h} \sum_{s=t+1}^{t+h} r_{p,    s}\right)-1=\exp \left(\mathbb{E}\left[r_{p,    s}\right]\right)-1 \tag{5.32}

\end{equation*}

$$

As this expression shows,  to maximize the geometric mean at very long horizons,  we should maximize $\mathbb{E}\left[r_{p,    s}\right]$,  i.e.,  we should maximize the expected $\log$ return of the portfolio. And to maximize $\mathbb{E}\left[r_{p,    s}\right]$ for all the periods $s$ from $t+1$ to $t+h$ within our investment horizon,  we want to maximize the conditional expected log return,  $\mathbb{E}_{t}\left[r_{p,    t+1}\right]$,  every period - so this is exactly the same approach as the solution in the $\gamma=1$ case above.

It is very important to keep in mind that when we maximize the long-run growth rate of wealth,  or the geometric mean,  or the expected log return,  we do not maximize the expected long-run growth rate of wealth,  or the expected long-run return. From our discussion of geometric vs. arithmetic mean we now know that maximizing the geometric mean is not the same thing as maximizing the expected long-run return of the portfolio. (Recall that in the IID log-normal returns case,  we obtain the long-run return by compounding the arithmetic,  not the geometric mean.)

Now suppose we want to follow the growth-optimal portfolio strategy. This requires that every period we choose a portfolio that maximizes the expected log return of the portfolio next period. Which combination of the risk-free and risky asset achieves this goal? Using our approximated portfolio log return from (5.27),  maximizing $\mathbb{E}_{t}\left[r_{p,    t+1}\right]$ means

$$

\begin{equation*}

\max _{\omega_{t}} \mathbb{E}_{t}\left[r_{f}+\omega_{t}\left(r_{t+1}-r_{f}\right)\right]+\frac{1}{2} \omega_{t}\left(1-\omega_{t}\right) \sigma_{t}^{2} \tag{5.33}

\end{equation*}

$$

This yields the first-order condition

$$

\begin{equation*}

\mathbb{E}_{t}\left[r_{t+1}-r_{f}\right]+\frac{1}{2} \sigma_{t}^{2}-\sigma_{t}^{2} \omega_{t}=0 \tag{5.34}

\end{equation*}

$$

which we can solve for

$$

\begin{equation*}

\omega_{t}=\frac{\mathbb{E}_{t}\left[r_{t+1}\right]-r_{f}+\frac{1}{2} \sigma_{t}^{2}}{\sigma_{t}^{2}} \tag{5.35}

\end{equation*}

$$

One property of this portfolio that may be the reason for its almost mystical appeal among some investors is that it is guaranteed (almost surely in mathematicians' terminology) to outgrow any other portfolio (i.e.,  a portfolio formed using any other rule how to choose the weights $\omega_{t}$ ) at some point in the future. At first look,  this seems amazing: Why would we want to consider any other portfolio if the growth-optimal portfolio is sure to outgrow all the other candidates? Even better: it seems that we have a universal rule here that we can apply without having to figure out our preferences regarding risk and return (i.e.,  our risk aversion)! The growth-optimal portfolio is the same for everyone,  irrespective of the degree of risk aversion,  as long as they agree on expected log return and volatility.

Actually,  that this could be a portfolio that is universally best for everyone seems too good to be true. Not surprisingly,  it is,  indeed,  too good to be true.

The trouble - and the source of much confusion among many devoted fans of the growth-optimal portfolio strategy - lies in the qualifier at some point. It is indeed true that maximizing the expected log return yields a portfolio that outgrows all the other possible ones at some point and will from there onwards stay ahead forever. But the point in time when this happens is uncertain. It could take 100 years,  or 10,  000 years,  or more. All we know is that it will eventually outgrow all others. But this is of little relevance for an investor (e.g.,  someone saving for retirement) who cares about wealth at a finite horizon $h$. For any finite horizon $h$,  there is always a possibility that the growth-optimal portfolio will underperform portfolios formed based on other rules. And this risk of underperformance can be unacceptably large if the investor is sufficiently risk averse.

To illustrate,  I simulate the evolution of wealth under different portfolio rules by choosing different levels of $\gamma$ in the following expression:

$$

\begin{equation*}

\omega_{t}=\frac{\mathbb{E}_{t}\left[r_{t+1}\right]-r_{f}+\frac{1}{2} \sigma_{t}^{2}}{\gamma \sigma_{t}^{2}} \tag{5.36}

\end{equation*}

$$

By comparing with (5.35) we can see that $\gamma=1$ corresponds to the growth-optimal portfolio. I simulate seven different portfolios with $\gamma$ taking values from $\gamma=0.5$ to $\gamma=2$. I rebalance portfolios daily (recall that for the log-linear approximation (5.27) to work well,  we want to keep short the time between rebalancing points). I simulate log stock index returns as

$$

\begin{equation*}

r_{t}=r_{f}+\mu+\sigma \varepsilon_{t},    \quad \varepsilon_{t} \sim \mathcal{N}(0,   1) \tag{5.37}

\end{equation*}

$$

with the $\log$ risk-free rate set to a constant $r_{f}=0.02 / 250 ; \sigma=0.20 / \sqrt{250}$,  i.e.,  an annualized $\log$ stock index return volatility of $20 \%$; and $\mu=0.02 / 250$,  i.e.,  an annualized equity premium over the risk-free rate of about $250 \times\left[\exp \left(\mu+\sigma^{2} / 2\right)-1\right]=4 \%$.

We then start the simulation with wealth $W_{0}=1$ invested into the stock index and risk-free asset according to the rule (5.36) for a given $\gamma$,  which gives us the same optimal share $\omega$ each period (since expected return and volatility are constant in these simulations). Then the portfolio earns a log return in the first period according to our log-linear approximation (5.27)

$$

\begin{equation*}

r_{p,    1} \approx r_{f}+\omega\left(r_{1}-r_{f}\right)+\frac{1}{2} \omega(1-\omega) \sigma^{2} \tag{5.38}

\end{equation*}

$$

After earning this return,  wealth at the end of the first period is

$$

\begin{equation*}

W_{1}=W_{0} \exp \left(r_{p,    1}\right) \tag{5.39}

\end{equation*}

$$

Then we rebalance the portfolio back to the optimal portfolio share $\omega$. And repeat the procedure for every day in the simulation.

Figure 5.1a shows the resulting paths of $\log$ wealth for the different values of $\gamma$ for the first 10,  000 days (with 250 trading days per year this amounts to 40 calendar years). The log wealth achieved by growth-optimal portfolio is shown by the solid red line. From this plot it looks like the growth-optimal portfolio started outgrowing all others by the end of the 10,  000 day period. Is this the point from where it remains ahead of all the other portfolios forever?

Figure 5.1b shows that the answer is no. This figure shows wealth for the first 100,  000 trading days in the simulation (400 years). While the growth-optimal portfolio

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-172.jpg?height=595&width=771&top_left_y=296&top_left_x=539)

(a) Simulated up to 10,  000 days ( $\approx 40$ years)

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-172.jpg?height=624&width=768&top_left_y=992&top_left_x=543)

(b) Simulated up to 100,  000 days ( $\approx 400$ years)

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-172.jpg?height=613&width=768&top_left_y=1710&top_left_x=543)

(c) Simulated up to $1,   000,   000$ days ( $\approx 4,   000$ years) 170

(C)Stefan Nagel 2024

Figure 5.1: Log wealth evolution for portfolios of different riskiness. Growth-optimal portfolio has $\gamma=1$.

stayed ahead of the others most of the time until around day 40,  000,  it subsequently falls substantially behind the more conservative portfolios with $\gamma>1$ that have a lower share allocated to equities. In the simulation,  this happens to be a prolonged period of poor stock market performance,  and hence portfolios with more conservative allocation do better. Only after about 100,  000 days,  at the very end of the chart,  the growth-optimal portfolio gets ahead of the others again.

Figure 5.1c shows that up to 1 million trading days ( 4,  000 years) the growth-optimal portfolio stays ahead of the others. Does this mean that we have found the point where it outperforms the others forever? Not clear. That it is ahead for so long is not a mathematical proof that we have found the point in time from which onwards it dominates forever. But even if it did,  what relevance does this have for a practical [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] problem that it outperformed all the others,  finally,  after 400 years? And in other circumstances,  if the path of random shocks that generated the stock index returns is different,  it could take more longer,  say 1,  000 years? Or 10,  000?

To get to an analysis that is more relevant for a typical real-world long-term investor,  let's see what happens with a fixed horizon. Consider an investor with a fixed horizon who cares about wealth after 10,  000 days (approx. 40 years),  which is roughly in the ballpark of the typical horizon of a young retirement investor or a pension fund. We can use these simulations to evaluate the distribution of wealth that results from different values of $\gamma$ in our [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] rule. We always start with 1$ of wealth and then simulate 1,   000 return series with length of 10,   000 and the evolution of wealth that results from applying a portfolio rule for a given $\gamma$.

Figure 5.2a shows the result. We can see that the growth-optimal portfolio with $\gamma=1$ does not clearly dominate other portfolios. It has less downside risk than the portfolio with $\gamma=0.5$. The latter portfolio is so risky that it frequently leads to large losses that bring the wealth at the end of our evaluation period close to zero. However,  as Figure 5.2 b shows,  which zooms in on the right tail of the distribution that is cut off in Figure 5.2 a ,  the riskiness of the $\gamma=0.5$ portfolio also brings substantially higher chances than the growth-optimal portfolio of an extremely large wealth gain. And it delivers a higher return on average,  as shown in the table below: on average,  wealth grows by $4695 \%$ with $\gamma=0.5$ and only $1001 \%$ with the growth-optimal portfolio strategy.

Table 5.5: Simulations of portfolio risk and return over 40-year horizon

|      | $\gamma=0.5$ | $\gamma=0.75$ | $\gamma=1$ | $\gamma=1.25$ | $\gamma=1.5$ | $\gamma=1.75$ | $\gamma=2$ |
| ---- | ------------ | ------------- | ---------- | ------------- | ------------ | ------------- | ---------- |
| Mean | 46.95        | 17.53         | 10.01      | 7.02          | 5.49         | 4.57          | 3.97       |
| S.D. | 348.37       | 57.38         | 20.18      | 10.35         | 6.47         | 4.55          | 3.44       |

Which of these portfolio allocation policies,  and the [[Lecture 1- Probability Distributions of Returns|probability distribution]] of wealth

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-174.jpg?height=640&width=795&top_left_y=474&top_left_x=622)

(a) Distribution excluding right tail

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-174.jpg?height=668&width=790&top_left_y=1273&top_left_x=624)

(b) Right tail of the distribution

Figure 5.2: Simulated distribution of wealth after 40 years for portfolios of different riskiness. Growth-optimal portfolio has $\gamma=1$.

they generate,  are more attractive to an investor depends on the investors risk preferences. The growth-optimal portfolio is not a universally preferable portfolio. Whether an investor prefers the growth-optimal portfolio,  or a more conservative portfolio with lower risky asset exposure,  or a riskier portfolio,  depends on risk preferences. An expected utility maximizing investor would choose it only if they have relative risk aversion equal to 1 . If they have higher risk aversion,  they prefer a less risky,  lower expected return strategy. If they have lower risk aversion,  they prefer a strategy with higher risk and higher expected return than the growth-optimal strategy.

### 5.4 Fixed-weight solution

We next look at a portfolio formation approach that,  unlike the growth-optimal portfolio approach,  takes into account the investor's risk preferences. The approach also allows for the possibility that long-term risk could be different from short-term risks when returns are not IID. But the approach is simplified in that it does not try to take advantage of market conditions through market timing. Instead,  it chooses the same weight every period,  i.e.,  it is a fixed-weight solution.

Since we are aiming for a fixed-weight solution that does not try to exploit timevariation in expected returns,  and therefore will have portfolio weights that do not vary with changes in conditional expected returns,  we can do the optimization in terms of unconditional moments.

Since constants in utility don't matter for the location of the maximum,  we can write the maximization problem in (5.21),  with the utility function (5.19),  as

$$

\begin{align*}

\mathbb{E}\left[U\left(W_{t+h}\right)\right] & =(1-\gamma) \mathbb{E}\left[\exp \left\{(1-\gamma) w_{t+h}\right\}\right] \\

& =(1-\gamma) W_{t} \mathbb{E}\left[\exp \left\{(1-\gamma) r_{p,    t: t+h}\right\}\right] \tag{5.40}

\end{align*}

$$

where we work with unconditional expectations for the reasons just discussed,  and the long-term portfolio return follows

$$

\begin{equation*}

r_{p,    t: t+h} \approx h r_{f}+\omega\left(r_{t: t+h}-h r_{f}\right)+\frac{h}{2} \omega(1-\omega) \sigma^{2} \tag{5.41}

\end{equation*}

$$

where $\omega$ is a weight that is fixed over time. Because we are working with weights that are fixed over time now,  we get around the problem we discussed in the beginning that with uncertain future portfolio weights,  the long-term portfolio return is not log-normal,  even if risky asset returns are log-normal. Here,  with fixed weights and assuming that risky asset returns are log-normal,  the long-term portfolio return,  $\exp \left(r_{p,    t: t+h}\right)$,  is log-normal.

Wealth at the end of the investment horizon,  $W_{t+h}$,  is then log-normally distributed as well. In this case it is convenient to maximize the log of expected utility (which produces the same result as maximizing expected utility),  which is

$$

\begin{equation*}

\log \mathbb{E}\left[U\left(W_{t+h}\right)\right]=\log (1-\gamma)+w_{0}+(1-\gamma) \mathbb{E}\left[r_{p,    t: t+h}\right]+\frac{1}{2}(1-\gamma)^{2} \operatorname{var}\left(r_{p,    t: t+h}\right) \tag{5.42}

\end{equation*}

$$

Once again,  constants don't matter,  and we can divide the whole expression by $1-\gamma$,  which means we can write the investor's problem as

$$

\begin{equation*}

\max _{\omega} \mathbb{E}\left[r_{p,    t: t+h}\right]+\frac{1}{2}(1-\gamma) \operatorname{var}\left(r_{p,    t: t+h}\right) \tag{5.43}

\end{equation*}

$$

Focusing on a fixed-weight solution drastically simplifies things here,  because with these fixed weights,  and the resulting long-term portfolio return approximation (5.41),  we get

$$

\begin{align*}

\mathbb{E}\left[r_{p,    t: t+h}\right] & =h r_{f}+\omega\left(\mathbb{E}\left[r_{t: t+h}\right]-h r_{f}\right)  \tag{5.44}\\

\operatorname{var}\left(r_{p,    t: t+h}\right) & =\omega^{2} \operatorname{var}\left(r_{t: t+h}\right) . \tag{5.45}

\end{align*}

$$

Substituting into (5.43),  ignoring terms that don't depend on $\omega$,  we get

$$

\max _{\omega} \omega \mathbb{E}\left[r_{t: t+h}-h r_{f}\right]+\frac{1}{2} \omega(1-\omega) \operatorname{var}\left(r_{t: t+h}\right)+\frac{1}{2}(1-\gamma) \omega^{2} \operatorname{var}\left(r_{t: t+h}\right)

$$

or,  simplified,

$$

\begin{equation*}

\max _{\omega} \omega \mathbb{E}\left[r_{t: t+h}-h r_{f}\right]+\frac{1}{2} \omega \operatorname{var}\left(r_{t: t+h}\right)-\frac{1}{2} \gamma \omega^{2} \operatorname{var}\left(r_{t: t+h}\right) \tag{5.46}

\end{equation*}

$$

with the first-order condition

$$

\begin{equation*}

\left.\mathbb{E}\left[r_{t: t+h}-h r_{f}\right)\right]+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}\right)-\gamma \omega \operatorname{var}\left(r_{t: t+h}\right)=0 \tag{5.47}

\end{equation*}

$$

which we can solve for

$$

\begin{equation*}

\omega=\frac{\mathbb{E}\left[r_{t: t+h}\right]-h r_{f}+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}\right)}{\gamma \operatorname{var}\left(r_{t: t+h}\right)} \tag{5.48}

\end{equation*}

$$

Now note that $\mathbb{E}\left[r_{t: t+h}\right]=h \mathbb{E}\left[r_{t+1}\right]$. Therefore,  after dividing numerator and denominator in (5.48) by $h$,  we get

$$

\begin{equation*}

\omega=\frac{\mathbb{E}\left[r_{t+1}\right]-r_{f}+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}\right) / h}{\gamma \operatorname{var}\left(r_{t: t+h}\right) / h} \tag{5.49}

\end{equation*}

$$

Compared with the optimal portfolio formula that we developed in the IID case in Lecture 1,  there are two differences. First,  the numerator is not the expected excess return,  but the log of one plus the expected risky asset return in excess of the log risk-free rate (under the assumption of a log-normal distribution). Second,  and more importantly,  the variance in the denominator is not the variance of the single-period portfolio return,  but a long-term portfolio log return variance divided by $h$.

For this long-term portfolio log return variance it matters whether returns are IID or not. If prices are mean-reverting and hence returns negatively serially correlated,  as the evidence suggests that we reviewed in Section 5.1.2,  then,  for $h>1$,

$$

\begin{equation*}

\operatorname{var}\left(r_{t: t+h}\right) / h<\sigma^{2} \tag{5.50}

\end{equation*}

$$

In this case,  the optimal fixed weight is horizon dependent. A short-horizon investor would choose a lower allocation to stocks than a long-term investor. The long-term investor in this case benefits from the long-term risk-reducing effects of mean-reversion.

By the same token,  the optimal fixed-weight solution again underscores the absence of any "time-diversification" in the IID case. With IID returns we have $\operatorname{var}\left(r_{t: t+h}\right) / h=\sigma^{2}$ and hence the optimal portfolio share is independent of the investor's horizon.

Table 5.6: Short and long-horizon optimal fixed-weight portfolios in the sentiment model

|                   | $\phi=0.15$ | $\phi=0.55$ | $\phi=0.95$ |
| ----------------- | ----------- | ----------- | ----------- |
| Quarterly Horizon | 0.156       | 0.200       | 0.558       |
| 10-year Horizon   | 0.686       | 0.686       | 0.710       |

We can examine the effects of mean reversion by going back to the simulated data from the sentiment model that we examined earlier. Table 5.6 shows the optimal weights in a fixed-weight strategy for an investor with quarterly horizon (first row) and an investor with 10-year horizon (second row). In both cases,  the investor has CRRA with $\gamma=5$. The extreme mean-reversion case $\phi=0.15$ illustrates nicely how an investor with a short-horizon would find stocks very risky and,  as a result,  invest only a small share in equities. A long-horizon investor recognizes that much of this risk cancels out in the long run and is willing to invest a much higher share in equities. In the empirically realistic case of $\phi=0.95$,  the wedge in optimal portfolio shares between shortand long-run perspectives is smaller,  but still not trivial.

An extension to multiple risky assets would not be difficult in the optimal fixedweights case. Just like single risky [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] depends on variance of long-run log returns,  the multiple risky [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] would depend on the covariance matrix of long-run log returns.

To complete the optimal fixed-weight portfolio analysis,  there is one additional issue that we need to address. What is the risk-free asset for a long-term investor? In the simulations,  the risk-free rate was fixed over time and so the risk-free asset is not only risk-free in the short-run but also risk-free in the long-run.

In reality,  our usual proxy for the short-run risk-free asset,  a Treasury bill is not riskfree in the long run. In the short-horizon analysis that we focused on in earlier lectures,  a Treasury bill with,  say,  three-month or one-year maturity was a suitable risk-free asset because it guarantees a fixed payoff at the end of the investment horizon. However,  if the horizon is multiple years,  or perhaps even multiple decades,  a short-maturity Treasury bill is no longer a risk-free asset over this long horizon because short-term interest rates will fluctuate over time. Rolling over short-maturity Treasury bills therefore delivers a risky long-term payoff.

To get a risk-free long-term payoff,  we need a bond with a long maturity. Ideally,  a zero-coupon bond that delivers only one single payment at the end of the investment horizon. But in practice,  a coupon bond can also provide a good approximation. The reinvestment of coupons at uncertain future interest rates introduces an element of risk,  but as long as bond yields are not too high,  this should be a relatively minor effect.

Ideally,  we would want to look at the price of this bond at the start of the investment period $t$ and then use its return until the end of the investment horizon $t+h$. For empirical analysis of long time series,  this approach is cumbersome because we would need to look up a different bond every period. Could one use instead the return a bond portfolio that is regularly rebalanced to hold bonds of similar maturity (i.e.,  by buying new bonds with long maturity and selling older bonds that have shorter remaining maturity)? As return series of such regularly rebalanced bond portfolios are widely available,  this would be easier to do.

Unfortunately,  the returns on such a portfolio over,  say,  a 10-year horizon are quite different from the returns on a 10-year bond held to maturity. We will discuss risks of such bond portfolios in more detail in later lectures,  but for now it suffices to say that during the past decades,  an investor with a 10-year horizon would have actually experienced slightly more volatile 10 -year log returns on a portfolio that rolls over bonds with approximately 10-year maturity than on an investment in a portfolio that rolls over short-term Treasury bills. So unless one is using the cumbersome approach of evaluating returns on buy-and-hold positions in bonds of maturities that match the investor's investment horizon,  it can be fine to stick to using Treasury bills as the riskfree asset proxy,  even though they are not truly risk-free over long investment horizons.

### 5.5 Adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]]

Many institutional investors follow variants of the fixed-weight strategy that we discussed in the previous section. Many balanced funds,  for example,  follow a strict policy of regularly rebalancing to fixed weights. Vanguard Balanced Index Fund describes its investment policy as follows:

With $60 \%$ of its assets,  the fund seeks to track the investment performance of the CRSP US Total Market Index,  which represents nearly 100\% of the investable U.S. Stock market covering large-,  mid-,  small-,  and micro-cap stocks regularly traded on the New York Stock Exchange and NASDAQ. The fund typically holds the largest 1,  200-1,  300 stocks in the CRSP US Total Market Index and a representative sample of the remainder of the index […]. With $40 \%$ of its assets,  the fund seeks to track the investment performance of the Bloomberg U.S. Aggregate Float Adjusted Bond Index …

Target date funds,  which have become ubiquitous as a retirement investment vehicle in $401(\mathrm{k})$ and other retirement accounts,  have target allocations that follow a preset glide path toward the funds target date (usually lower allocations to equity over time). These funds also regularly rebalance their portfolio weights to set them equal to the target glide path weights. These weights are not literally fixed,  but they vary only according to a deterministic schedule as a function of the investor's age. In this sense,  they also resemble the fixed-weight strategy we analyzed in this section. There is no uncertainty about future weights.

Endowments and pension funds typically set a strategic [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] policy that specifies weights for different asset classes with a range around the target. This is like approximately fixed weights with some flexibility. Figure 5.3 shows an example from CalPERS. While the "income" (fixed income) portion of their portfolio is 1.6 percentage points above the target of $28 \%$,  this deviation is still well within the range of $+/-6$ percentage points allowed by their policy. Portfolio managers can,  but don't have to rebalance yet toward the target. It becomes an active choice.

So what are we effectively doing if we rebalance frequently toward a fixed target allocation? Rebalancing requires selling assets that have appreciated (hence their portfolio weight has increased) and buying assets that have fallen in value. So we are effectively following a contrarian strategy.

It is in some sense an active investment strategy because we are buying and selling! And it's not a strategy that the average investor can follow. Buying and selling means that someone else has to take the other side of our trades. If we sell,  someone else has to buy. We can't all rebalance!

Public Employees' Retirement Fund (PERF) As of September 30,  2021

| [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]]                |                          |                        |                          |                      |                    |
| ------------------------------- | ------------------------ | ---------------------- | ------------------------ | -------------------- | ------------------ |
|                                 | Ending Asset Value (bil) | Current Allocation (%) | Policy Target Weight (%) | Policy Variance  (%) | Policy Range       |
| Public Equity ${ }^{1}$         | $ 241.1                  | 50.2\%                 | 50.0\%                   | 0.2\%                | $\pm 7 \%$         |
| Private Equity ${ }^{2}$        | $ 44.0                   | 9.2\%                  | 8.0\%                    | 1.2\%                | $\pm 4 \%$         |
| Income ${ }^{1}$                | $ 142.0                  | 29.6\%                 | 28.0\%                   | 1.6\%                | $\pm 6 \%$         |
| Real Assets ${ }^{2}$           | $ 48.5                   | 10.1\%                 | 13.0\%                   | (2.9%)               | $\pm 5 \%$         |
| Total Fund                      | $ 11.2                   | 2.3\%                  |                          |                      |                    |
| Opportunistic ${ }^{2}$         | $ 3.2                    | 0.7\%                  |                          |                      |                    |
| LLER $^{3}$                     | $ 7.8                    | 1.6\%                  |                          |                      |                    |
| Other                           | $ 0.2                    | 0.0\%                  |                          |                      |                    |
| Financing & Liquidity           | $ (7.0)                  | (1.5%)                 |                          |                      |                    |
| Trust Level Financing ${ }^{4}$ | $ (14.8)                 | (3.1%)                 |                          |                      |                    |
| Liquidity ${ }^{4}$             | $ 7.8                    | $1.6 \%$               | $1.0 \%$                 | $0.6 \%$             | $-6 \%$ to $+3 \%$ |
| Total PERF                      | $ 479.8                  | 100.0\%                | 100.0\%                  |                      |                    |

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-180.jpg?height=524&width=527&top_left_y=540&top_left_x=1189)

Figure 5.3: CalPERS [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] September 2021

To see the contrast to a passive strategy,  recall our discussion in Lecture 2 of the absence of trading needs when an investor holds the market portfolio,  or,  more generally,  when an investor replicates a value-weighted index. As a reminder,  let's quickly revisit this using the example of a value-weighted stock index. With $N$ stocks,  a price $p_{i,    t}$ of stock $i$ at time $t$,  and shares outstanding for each stock of $s_{i}$ (assumed constant),  the weight of each stock in the index at $t$ is

$$

\begin{equation*}

w_{i,    t}=\frac{p_{i,    t} s_{i}}{\sum_{i=1}^{N} p_{i,    t} s_{i}} \tag{5.51}

\end{equation*}

$$

Now suppose we own shares exactly in the right proportion so that our portfolio weights are $w_{i,    t}$ at time $t$. If we hold this portfolio until $t+1$ without trading,  our weights will be

$$

\begin{equation*}

\frac{p_{i,    t+1} s_{i}}{\sum_{i=1}^{N} p_{i,    t+1} s_{i}} \tag{5.52}

\end{equation*}

$$

based on the new prices $p_{i,    t+1}$ at time $t+1$. And these weights in (5.52) are also exactly the new index weights

$$

\begin{equation*}

w_{i,    t+1}=\frac{p_{i,    t+1} s_{i}}{\sum_{i=1}^{N} p_{i,    t} s_{i}} \tag{5.53}

\end{equation*}

$$

A value-weighted index lets each assets' weights drift as the price of these assets changes. If Apple's stock price doubles,  its weight in our portfolio almost doubles (more precisely,  it almost doubles,  but not quite,  because it will also lift the total value of our portfolio by a bit),  but its weight in the index also goes up by the same proportion. As a consequence,  maintaining a portfolio that follows such an index does not require trading (unless there are changes in shares outstanding,  e.g. via new equity issues,  or dividend payments that must be reinvested. In practice,  these changes would require a small amount of trading). Unlike a rebalancing strategy that reverts to fixed weights each period by buying and selling,  this value-weighted index replication is a strategy that all investors could follow collectively (or the average investor).

Now back to the rebalancing-to-fixed-weights strategy. Suppose we are an investor with a long-term horizon following an optimal portfolio rule like (5.49). Suppose further that we use a long-term bonds as a proxy for a long-term risk-free investment,  despite the caveats we discussed at the end of the previous section. And let's assume that the optimal portfolio weight formula produced 60/40 to stocks and bonds as the optimal allocation. In the initial period,  we set portfolio weights exactly equal to 60/40. But then subsequently,  due to price changes,  let's say the portfolio weights have drifted away from these optimal weights to 65/35.

On one hand,  if our views about future risk and return have not changed and our risk aversion has not changed,  so the previous portfolio weights of $60 / 40$ are still optimal,  then we should rebalance back to the previous portfolio weights of $60 / 40$. But the fact the average investors' weights have drifted away from the previous weights to 65/35,  and the average investor is apparently fine with this means that other investors must have changed their views and future risk and returns,  or their risk aversion must have changed,  so that they are willing to hold the asset classes at $65 / 35$. If price changes have made the aggregate market capitalization of the stock market bigger relative to the value of all bonds this must mean either that

the average investor perceives stocks as less risky or less averse to its risk than before. In this case,  the returns of stocks expected by the average investor would fall to some degree (as price goes up with unchanged future cash flow expectations),  but the investor is happy to hold a higher share of stocks in their portfolio due to the lower riskiness or lower aversion to this risk.

that the average investor became more optimistic about the future cash flows of stocks. In this case,  the price rise would be dampened a bit by the fact that investors require a higher expected rate of return from stocks if they are to command a bigger share of their portfolio. As a consequence,  the price rise would coincide with a higher expected return expected by the average investor.

If we are rebalancing back to 60/40,  we are implicitly expressing the view that we are somehow taking a different view about risk and return,  or have different changes in preferences about risk and return,  than the average investor. Is this what we want? Perhaps our views about future risk and return should have changed. If the market changed its valuation of stocks and bonds in aggregate,  perhaps there is a good reason for it? Perhaps we should just follow what the market does?

So the questions we need to ask ourselves then is how we compare relative to the average investor.

If the average investors aversion to stock market risk has gone down,  or their perception of riskiness of stocks has gone down,  do we think we are similar to the average investor,  or can trust that the average investor makes a good assessment here and we can just follow along? If yes,  we should not rebalance in response to price changes.

If the average investors optimism about future cash flows of stocks has gone up,  should we go along with this because the average investor probably knows better than we do? If yes,  we should not rebalance in response to price changes.

In other words,  if we believe that financial markets are efficient and that we are similar to the average investor in terms of how our risk aversion changes (or does not change) over time,  then we should not rebalance in response to price changes. By rebalancing frequently back to the weights recommended by a fixed-weight strategy,  we would implicitly express the view that we are different from the average investor. In some sense,  therefore,  a fixed-weight strategy is actually a form of market-timing (and a contrarian one,  as we already discussed) where we are hoping to do better than the average investor by disagreeing with the average investor's investment decisions. If we don't think we are different from the average investor,  and we would therefore like to follow a passive approach that does not involve implicit market-timing through rebalancing,  then we should let our portfolio weights drift with market prices.

So far we have ignored that there may be reasons other than rebalancing in response to price changes that may require trading: stocks earn dividends that must be reinvested,  bonds pay coupons and they mature and the obtained funds must be reinvested,  initial public offerings bring new assets to the market,  etc. The rule of letting portfolio weights drift with prices doesn't exactly tell us what to do when these complications are present.

But there is a relatively simple solution: If we want to follow the principle of avoiding deviations from what the average in investor is doing,  let's try to hold a portfolio whose weights move in lockstep with changes in the relative aggregate market values of the

asset classes in our portfolio. This portfolio will be close to what we get by just letting portfolio weights drift with price changes,  but not exactly. The amount of trading required to achieve these portfolio weights is minimal. And it will give us guidance how to reinvest dividends,  proceeds from redemptions when firms go private,  etc.

In our stocks/bonds case,  we would start out with an allocation that reflects our assessment of risk and return at that time and our risk preferences,  which leads us,  say,  to a $60 / 40$ portfolio,  so our initial equity share at time $t=0$ is

$$

\begin{equation*}

\omega_{0}=0.60 \tag{5.54}

\end{equation*}

$$

Next,  we take the view that we can agree with the average investor in the U.S. market with respect to changes in expected future cash flows of stocks; we also take the view that we would share future changes in the average investor's perceived risk and risk aversion. So if such changes lead to changes in market values of stocks and bonds,  we just want to follow along. We therefore look up the aggregate market value of equity held by U.S. investors at $t=0$,  denoted $V_{e,    0}$,  and of bonds,  $V_{b,    0}$. In the following period,  $t=1,   2,    \ldots$,  when aggregate market values have changed to $V_{e,    t}$ and $V_{b,    t}$,  our target portfolio weight is

$$

\begin{equation*}

\omega_{t}=0.60 \times \frac{V_{e,    t} / V_{e,    0}}{0.6 \times V_{e,    t} / V_{e,    0}+0.4 \times V_{b,    t} / V_{b,    0}} \tag{5.55}

\end{equation*}

$$

If the only reason why the values $V_{e}$ and $V_{b}$ changed were price changes,  then $\omega_{t}$ in (5.55) would be exactly the weight we would get if we just let portfolio weights drift with price changes. But in practice $V_{e}$ and $V_{b}$ will also change because new firms come to market,  bonds get redeemed,  and so on.

The same logic applies analogously with more than two asset classes. For example,  if we hold a portfolio of several global asset classes,  we need estimates of the total market value of all assets globally in these classes.

Nobel laureate Bill Sharpe has called this approach to (mostly avoid) portfolio rebalancing an adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] policy. ${ }^{5}$

I use the data on aggregate stock and debt holdings of U.S. investors that we looked at earlier in Figure 1.12 to calculate $V_{e,    t}$ and $V_{b,    t}$ at the end of every quarter from December 1951 to December 2022. And then,  starting with an initial portfolio of $60 / 40$ at the end of 1951,  I use these to calculate the adaptive allocation to equity following (5.55) every quarter. Figure 5.4 shows the result.

As the figure shows,  the adaptive portfolio has above-average allocations to equity following stock market booms such as in the late 1990s,  or in the years prior to the

[^24] ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-184.jpg?height=949&width=1201&top_left_y=290&top_left_x=424)

Figure 5.4: Equity share with adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] policy

COVID pandemic in 2020,  and below-average allocations following stock market downturns such as during the depth of the financial crisis in 2008-09.

Is this a good thing? The potential advantage of this adaptive approach kicks in if financial markets are efficient. Expected returns and risks could change from quarter to quarter,  but by letting our portfolio track the average investors' portfolio allocation,  we are avoiding taking a bet against the average investor. Instead,  we rely on the "wisdom of the average investor" : say,  if the average investors' allocation to equity has gone up,  there must be a good reason for it,  and so it makes sense to follow what the average investor does.

But if markets are to some degree inefficient,  following what the average investor does could become a disadvantage. What if the average investor sometimes gets it wrong? For example,  if stock market booms are times when stocks are overvalued because the average investor gets too optimistic about future growth in stocks' cash flows,  then it may not be a good idea to let our weight on equities increase along with the rise in stock prices because we would raise our stock allocation exactly when future stock market returns are likely to be poor. Given the evidence on stock return predictability we discussed in the previous lectures,  regularly rebalancing to a fixed portfolio share,  say

$60 / 40$,  may be a better approach.

Table 5.7: Risk and return of different rebalancing strategies

|   | Fixed 60/40 | Adaptive | Fixed at mean(adapt.weight) |

| --- | --- | --- | --- |

| Panel A: Quarterly returns,  annualized stats |   |   |   |

| Mean excess return | 0.052 | 0.052 |   |

| S.D. | 0.104 | 0.113 | 0.055 |

| Sharpe Ratio | 0.497 | 0.459 | 0.112 |

|   |   | 0.490 |   |

| Panel B: 10-year returns,  annualized stats |   |   |   |

| LR Mean excess return | 0.028 | 0.027 |   |

| LR S.D. | 0.079 | 0.093 | 0.030 |

| LR Sharpe Ratio | 0.355 | 0.294 | 0.087 |

|   |   | 0.350 |   |

Let's do a simple empirical calculation of the returns that we would have earned in past decades with an adaptive allocation approach and a fixed 60/40 portfolio that is rebalanced at the end of every quarter. Table 5.7 presents the results. It shows the performance of portfolios that mix U.S. stocks (CRSP value-weighted index) and a portfolio of U.S. Treasury bonds from 1952 to 2022. We treat the bond portfolio as a long-term riskless asset and look at the excess return of the combined stock-bond portfolio relative to the long-term returns of this bond portfolio.

The table looks at three strategies:

a fixed-weight strategy with $60 \%$ in stocks,  $40 \%$ in bonds,  rebalanced at the end of every quarter

an adaptive allocation strategy using the weights show in Figure 5.4

a fixed-weight strategy that uses the average of the weights shows in Figure 5.4 $(\approx 65 %)$,  rebalanced at the end of every quarter

The last one is there to have a benchmark for comparison with the adaptive strategy that has the same allocation to risky assets on average as the adaptive strategy.

Panel A looks at mean,  standard deviation,  and Sharpe ratio of quarterly returns of the three strategies,  with all statistics annualized. In this short-term returns analysis,  I use T-bill returns as the risk-free asset return proxy. As the table shows,  the differences between the three strategies' outcomes are not big. But the adaptive strategy does a little worse in terms of Sharpe ratio returns than the third strategy that has the same

average exposure to stocks. If returns were IID,  as we have assumed in our theoretical analyses so far,  this should not be the case. Part of this worse performance is due to a somewhat lower average excess return. This is consistent with the evidence we discussed that high stock market valuation levels have historically been followed by relatively poor returns on stocks. The contrarian market-timing of the fixed-weight strategy provides a little performance boost relative to the passive adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] strategy.

Panel B takes the perspective of a long-term investor and evaluates outcomes of the three strategies at a 10-year investment horizon ( $h=40$ quarters). With long-term returns,  we should not simply take means and standard deviations of simple long-term returns to calculate a Sharpe ratio. For the Sharpe ratio to be a good summary of the risk-return profile of an asset or portfolio,  the distribution of the returns should not be too far from normal. However,  long-term simple returns are strongly positively skewed (since they have downside bounded at $-100 \%$,  but unlimited upside) and hence variance of long-term simple returns is not a good risk measure. But an examination of the optimal fixed-weight formula (5.48) gives us a hint how we could address the issue. Under the log-normal distribution,  the numerator in that formula is the log expected simple long-run excess return and the formula relates it to the variance of the long-run log return in the denominator. In the same way,  we can construct a long-run Sharpe ratio with good properties for log-normally distributed returns as follows:

$$

\begin{equation*}

L R S R=\frac{\log \left(1+\mathbb{E}\left[R_{p,    t: t+h}\right]\right) / h-r_{f,    t: t+h} / h}{\sqrt{\operatorname{var}\left(r_{p,    t: t+h}\right)} / \sqrt{h}} \tag{5.56}

\end{equation*}

$$

where $r_{f,    t: t+h}$ is an appropriate proxy for the rate of return on a long-term risk-free investment over the horizon $h$.

If returns are IID $\log$-normal,  then $\log \left(1+\mathbb{E}\left[R_{p,    t: t+h}\right]\right)$ and $\operatorname{var}\left(r_{p,    t: t+h}\right)$ grow proportionally with $h$ and hence $L R S R$ does not change with horizon-which is a sensible result for an IID environment.

Panel B shows that the long-run Sharpe ratios are all lower than the Sharpe ratios in Panel A for the fixed-weight strategies. This is a consequence of using the bond portfolio returns as risk-free asset return proxies. Long-term bonds had higher returns than T-bills during the sample period analyzed in this table,  so we are subtracting higher numbers when we construct excess returns. (If one uses T-bill returns instead,  the long-run Sharpe ratios are slightly higher than the short-run Sharpe ratios in Panel A,  consistent with a variance-reducing effect of mean reversion in stock prices). In terms of relative performance between the three strategies,  the message from the longterm Sharpe ratios in Panel B is the same as in Panel A: the adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] strategy underperforms.

So unless we are convinced that valuation cycles in the stock market reflect timevarying risk aversion or time-varying risk and that we (or our clients) share this timevariation in risk aversion or these time-varying risk perceptions,  it's not clear that an adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] strategy is preferable. The contrarian trading implied by a fixed-weight strategy may actually be preferable and worth the small transaction cost of rebalancing. It's a simple,  relatively robust way of exploiting the tendency of stock market returns to mean-revert without having to estimate a statistical return-prediction model.

### 5.6 Myopic market-timing

A practically feasible method that goes some way of taking advantage of the opportunities offered by time-varying expected returns and risk is to solve the [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] problem every period as if returns were IID. This means we use the solution we derived earlier in (5.49),  but now with conditional expected log short-horizon returns,  $\mathbb{E}_{t}\left[r_{t+1}\right]$. So far in this lecture,  we did not allow for a time-varying conditional variance,  $\sigma_{t}^{2}=\operatorname{var}_{t}\left(r_{t+1}\right)$,  but we can now allow for this,  too,  and easily incorporate a time-varying conditional variance in the portfolio formula. With this strategy,  we can also allow for a time-varying short-term risk-free rate:

$$

\begin{equation*}

\omega_{t}=\frac{\mathbb{E}_{t}\left[r_{t+1}\right]-r_{f,    t}+\frac{1}{2} \sigma_{t}^{2}}{\gamma \sigma_{t}^{2}} \tag{5.57}

\end{equation*}

$$

With this method,  we choose a portfolio every period as if future returns were generated IID. But when the next period arrives,  we recompute the solution now based on $\mathbb{E}_{t+1}\left[r_{t+2}\right],    \sigma_{t+1}^{2}=\operatorname{var}_{t+1}\left(r_{t+2}\right)$,  and $r_{f,    t+1}$ (which would not have changed if returns were truly IID). We reshuffle our portfolio accordingly.

This approach clearly takes advantage of the opportunities that arise from having information about time varying expected returns or volatilities. This can potentially be a substantial improvement over a policy that simply ignores these opportunities and sticks to a fixed portfolio. But we are not taking into account the effects that work through the long-run portfolio return variance that we discussed above. For example,  if mean-reversion makes stocks less risky in the long-run and hence a more attractive asset,  the formula in (5.57) does not take this into account because it uses only the short-run variance. So the myopic market-timing strategy is not necessarily utility-improving for a long-term investor.

To check whether there is a gain from the myopic market-timing strategy,  even though it does not take advantage of the long-run variance reduction due to mean-reversion,  I

now look again at the simulations of the sentiment model. I set $\gamma=5$ and implement three different strategies:

The myopic market-timing strategy based on (5.57)

The optimal fixed weight strategy (5.49)

An alternative fixed-weight strategy that sets the weight to the long-run average of the myopic market-timing strategy weights

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-188.jpg?height=920&width=1186&top_left_y=819&top_left_x=426)

Figure 5.5: Equity share of market-timing portfolio (first 100 observations from simulation,  $\phi=0.95$ )

Figure 5.5 illustrates how the weights of these strategies look like with a cut of 100 quarters from one simulation run with $\phi=0.95$. With $\gamma=5$,  the myopic market-timing strategy invests on average about $56 \%$ of the portfolio in the stock market. This is the fixed weight for the third strategy in the list above. The myopic market-timing strategy has weights that vary around this level from around zero to occasionally above one. Periods when the weight is low are periods when the conditional expected excess return on the stock market is low; periods when the weight is high are periods when the conditional expected excess return is high. When the weight is below zero,  this means

that the strategy takes a short position in the stock market; when it's above one,  the strategy takes a leveraged position in the stock market financed by borrowing at the risk-free rate.

The optimal fixed-weight strategy has a risky asset weight of around $68 \%$,  which is substantially higher than the average weight of the myopic market-timing strategy. This reflects the fact that the optimal fixed-weight strategy takes into account the long-term variance-reducing effect of mean-reversion. This makes a stock market investment look more attractive,  hence the higher weight.

Table 5.8 shows the expected utility from the three strategies for a long-term investor with a 10-year (40-quarter) horizon. For this investor,  expected utility is then given by

$$

\begin{equation*}

\mathbb{E}\left[U\left(W_{t+h}\right)\right] \quad \text { with } \quad U\left(W_{t+h}\right)=\frac{W_{t+h}^{1-\gamma}-1}{1-\gamma} \tag{5.58}

\end{equation*}

$$

horizon $h=40$,  and

$$

\begin{equation*}

W_{t+h}=W_{t}\left(1+R_{p,    t: t+h}\right) \tag{5.59}

\end{equation*}

$$

In the calculation of $W_{t+h}$ in the simulations,  I normalize wealth to $W_{t}=1$ at the time when the investor makes the investment. As in the previous simulation results,  I focus on three cases for $\phi$ ranging from unrealistically strong mean-reversion with $\phi=0.15$ to the empirically realistic case of $\phi=0.95$. I compute the realized $U\left(W_{t+h}\right)$ for every available 10-year period in the simulated data,  and then I average across the very large number of such simulated 10-year periods to get $\mathbb{E}\left[U\left(W_{t+h}\right)\right]$.

Table 5.8: Expected utility from different strategies for an investor with 10-year horizon in the simulated sentiment model

|   | $\phi=0.15$ | $\phi=0.55$ | $\phi=0.95$ |

| --- | --- | --- | --- |

| Myopic timing | 0.250 | 0.250 | 0.194 |

| Optimal fixed weight | 0.179 | 0.178 | 0.178 |

| Fixed weight $=$ mean(myopic timing wts.) | 0.110 | 0.119 | 0.173 |

As the table shows,  the market-timing strategy is generally outperforming the other two in terms of expected utility. Thus,  a risk-averse investor with $\gamma=5$ would clearly prefer the market-timing strategy over the two fixed-weights strategies. This makes sense. After all,  the market-timing strategy exploits time-variation in expected returns while the fixed-weights strategies ignores it. But it is not automatically true under all parameter constellations for the simulations that generate the data. The reason is that the myopic market-timing strategy looks only one period ahead in the optimization. For this reason,  it does not take into account the long-term variance-reducing effect of mean-reversion. At least in theory,  there could therefore be parameter constellations that

make the optimal fixed-weight strategy,  which takes into account this long-term variancereducing effect of mean-reversion but fails to exploit market-timing opportunities,  the better strategy.

This is also the reason why the myopic market-timing strategy does not show a utility improvement when going from $\phi=0.55$ to $\phi=0.15$. On the one hand,  lower sentiment persistence strongly amplifies the market-timing opportunities,  which benefit the myopic market-timing strategy. On the other hand,  long-term variance then falls relative to short-term variance,  but the myopic market-timing weights fail to take this into account.

We can also see that the fixed-weight strategy that sets the weight equal to the longterm average of the myopic market-timing strategy is inferior to the optimal fixed-weight strategy. This again has to do with the fact that the optimal fixed-weight strategy takes into account the long-term variance-reducing effect of mean-reversion,  while the strategy that sets fixed weights equal to the mean of myopic market-timing weights ignores this reduction in long-term variance - and this is particularly detrimental to expected utility when mean-reversion is very strong,  i.e.,  for low $\phi$.

As we discussed,  the myopic market-timing strategy is not fully optimal for the longterm investor because it allocates each period as if returns were IID going forwardwhich they are not. Since the problem is intractable,  we can't figure out exactly how much more we would need to allocate to stocks to optimally exploit the fact that stocks are less riskier in the long-run (than it may seem from a short-horizon analysis) due to mean-reversion. But we can try a heuristic approach that may go some of the way towards the fully optimal solution: Use the myopic market-timing formula (5.57),  but instead of the short-run variance $\sigma^{2}$ (which is constant in the sentiment model that we are simulating here) plug in the long-run variance $\operatorname{var}\left(r_{p,    t: t+h}\right) / h$ from the optimal fixed weight strategy formula (5.49). This produces only a slight improvement: in the $\phi=0.95$ case,  the long-term investor gets expected utility of 0.198 instead of 0.194 . This confirms that the myopic market-timing strategy is not fully optimal,  but it seems difficult to improve it in a substantial way.

The bottom line is that the myopic market-timing strategy seems like a reasonable approach,  even though it's not fully optimal. One caveat,  though,  is that in these simulations we knew exactly the value of conditional expected stock market returns at every point in time. In practice,  we would have to estimate this with the predictive regression techniques we discussed in earlier lectures. This introduces estimation noise into the portfolio weights which will lead to some degree of performance deterioration. As a consequence,  in practice,  the optimal fixed-weight strategy may be quite competitive relative to the myopic market-timing strategy. It takes into account the effects of meanreversion on the long-run variance,  but does not try to exploit predictability of excess returns for market timing.
