---
aliases:
- Alias_253_Week 3-Advanced Investments.md
- Alias_256_Week 3-Advanced Investments.md
- LECTURE 3
linter-yaml-title-alias: LECTURE 3
tags:
- tag_example
title: LECTURE 3
---



# LECTURE 3

We now focus on the dynamics of returns over time. Recall from Lecture 1 the formula for the optimal risky asset share in the single risky asset case:

$$
\omega = \frac{\mathbb{E}[R] - R_f}{\gamma \operatorname{var}(R)} \tag{3.1}
$$

The inputs of this optimal allocation formula could potentially vary over time. Perhaps there are times when expected excess returns are high and times when they are low? Perhaps there are times when volatility is high and other times when volatility is low? If such time-variation in expected returns or risk exists,  can it be exploited in a market-timing strategy?

Later,  in Lecture 5,  we will look in more detail into optimal asset allocation in a multi-period setting when risk and expected return are time-varying. But for now,  let's just think about potentially applying this formula period-by-period,  with a one-period investment horizon. To do this,  we need a statistical model that gives us expectations of next-period returns and/or forecasts of next-period volatility.

With this motivation in mind,  we will now look at the data to answer questions such as:

- Are stock market index returns predictable?
- If yes,  does such predictability allow market timing?
- What sort of variables can be useful predictors of returns?
- Is volatility predictable?

## 3.1 CONDITIONAL PROBABILITY DISTRIBUTIONS

Questions about the dynamics of returns,  predictability,  and market timing all have to do with the **conditional** probability distribution of returns.

In the past two lectures,  we focused on the **unconditional** probability distribution of returns. The unconditional distribution describes how likely various outcomes are in general,  without picking a subset of specific situations. For example,  we discussed how to estimate the unconditional mean of stock returns by taking a simple average of returns.

In contrast,  the conditional distribution describes how likely various outcomes for returns are conditional on a subset of specific situations. For example,  suppose we come to the conclusion that the distribution of next period returns,  $R_{t+1}$,  is different depending on whether returns in the current period,  $R_t$,  are negative or positive. In this case,  the current period return $R_t$ is the **conditioning information** and the distribution of returns conditional on whether $R_t < 0$ or $R_t \geq 0$ is the conditional distribution of returns.

Now,  the conditional distribution differs from the unconditional distribution only if the conditioning information (lagged returns in our example) actually has some useful information about the shape and location of the probability distribution of future returns.

To describe how the shape and location of this probability distribution changes with conditioning information,  we need a statistical model.

For example,  a crude statistical model of the conditional distribution of stock market returns would be to assert that future returns may be drawn from two different distributions: one that applies when the market went up in the previous month,  the other one when it fell.

Figure 3.1 plots histograms of the two distributions: one depicts the distribution of stock market returns following a gain in the previous month; the other one depicts the distribution of stock market returns following a loss in the previous month. Interestingly,  the distributions do seem to be different! Note how the distribution following a loss is more spread out and less concentrated in the middle. This means that when the stock market has fallen in the previous month,  then,  historically,  it was followed by a more volatile month in which returns were likely to be either very high or very low.

Just as we can characterize unconditional probability distributions in terms of unconditional moments,  we can describe conditional distributions in terms of conditional moments. If $x_t$ is a variable that represents our conditioning information (in Figure 3.1,  $x_t$ would be an indicator for whether $R_t < 0$ or $R_t \geq 0$),  then we can describe the distribution of $R_{t+1}$ conditional on $x_t$ with its conditional moments such as,  e.g.,  the conditional expected return,  $\mathbb{E}[R_{t+1} \mid x_t]$,  and the conditional variance $\operatorname{var}(R_{t+1} \mid x_t)$.

To make these conditional moments useful in applications,  we need a statistical model to describe them. Here is an example: Suppose there was momentum in returns,  by which we mean that high returns in month $t$ are followed,  on average,  by predictably high returns in month $t+1$. We could capture this with a model for conditional expected returns such as:

$$
\mathbb{E}[R_{t+1} \mid R_t] = a + bR_t
$$

![Figure 3.1: Conditional Distribution of Returns](2_image_0.png)

where $a$ and $b$ are constants and $b > 0$. If we had instead $b < 0$,  this would be a model for reversals where high past returns predict low future returns. We can use regressions to estimate such models of conditional expected returns.

We often omit stating the conditioning information explicitly and just write $E_t[.]$,  e.g.,  $E_t[R_{t+1}]$. This is imprecise because this notation is not explicit about the type of information we are conditioning on,  but it reduces clutter in our notation. Typically,  this notation means that we think of the expectations conditioned on whatever is observable to an investor at time $t$.

If returns are **independently and identically** (IID) distributed,  then conditional and unconditional distributions are the same. Or,  put differently,  in this case,  conditioning information about the current state of the economy,  etc.,  does not contain information about the distribution of future returns. Our crude analysis of the returns conditional on the previous month's gain/loss in Figure 3.1 already suggests that returns are not IID,  as the two conditional distributions shown in this figure differ substantially (although we haven't yet done a formal statistical test to see whether the difference is really statistically significant).

## 3.2 LOGARITHMIC RETURNS

In this lecture and the coming ones,  we will pay more attention to the dynamics of returns over time. This means that we will have to take into account the compounding of returns.

Unfortunately,  working with compound returns is messy because compounding is multiplicative. Consider an asset that earns a sequence of returns over time: $R_{t+1}$,  $R_{t+2}$,  …,  $R_{T}$.

Calculation of the long-run return on this asset from time $t$ to $t+T$ involves compounding of returns over multiple periods:

$$
R_{t:t+T} = (1 + R_{t+1}) \times (1 + R_{t+2}) \times \ldots \times (1 + R_{t+T}) - 1 \tag{3.2}
$$

This compound return involves products of random single-period returns. Products of random variables are statistically difficult to analyze. Things quickly become intractable.

When we analyze such long-run returns,  it is often convenient to work with the natural logarithm of returns,  or short just **log returns**. We use lower-case letters to denote log returns $r_t = \log(1 + R_t)$:

$$
r_t = \log(1 + R_t) \tag{3.3}
$$

The nice property of the log transformation is that the log of a product becomes the sum of the log of the factors of the product. Hence,  for the long-run return,  we get,  after taking the log:

$$
r_{t:t+T} = \log(1 + R_{t:t+T}) = r_{t+1} + r_{t+2} + \ldots + r_{t+T} \tag{3.4}
$$

i.e.,  the long-run log return is a simple sum of the individual period log returns. Sums are much easier to analyze statistically than products of random variables.

Taking the exponential function of the log return gets us back to simple returns:

$$
R_{t:t+T} = \exp(r_{t+1} + r_{t+2} + \ldots + r_{t+T}) - 1 \tag{3.5}
$$

When we use log returns,  we always need to keep in mind that the log return is not the same as the simple return. For example,  as we will see in more detail in the next lecture,  looking for a portfolio that maximizes the expected log return of the portfolio is not the same as one that maximizes the expected simple return.

For now,  let's just note two things that we should keep in mind:

1. The expected log return is not the same as the log of one plus the expected return. The following relations hold:

   $$
   \mathbb{E}[R_t] \geq \log(\mathbb{E}[1 + R_t]) \geq \mathbb{E}[r_t] \tag{3.6}
   $$

   The first inequality on the left just reflects that $\log(1 + x) \leq x$ for any real $x$. The second inequality on the right is a special case of a mathematical law called **Jensen's inequality**. For risky returns with non-zero variance,  both inequalities are strict. We get a more precise statement about the relation between these two expectations if we impose an assumption about the statistical distribution of returns. More on this below.

1. The log of the weighted average of simple returns (i.e.,  the log of a portfolio return) is not equal to the weighted average of the log returns of the individual assets. Suppose we have $N$ assets and we collect their returns $R_1,    R_2,    \ldots,    R_N$ in the vector $r$. For a portfolio with weights $\omega$,  the (simple) return on a portfolio is simply the weighted average of individual asset (simple) returns:

   $$
   R_p = \omega^{\prime} r \tag{3.7}
   $$

   The same is not true for log returns. A weighted average of log returns is not equal to the log return on the portfolio:

   $$
   r_p = \log(\omega^{\prime} r)
   $$

Now that we have log returns in our toolbox,  we can also be more realistic in our assumptions about the distribution of returns. In the past two lectures,  we assumed in some analyses and simulations that simple returns are normally distributed. Strictly speaking,  this assumption did not really make economic sense. The support of the normal distribution is unbounded in both tails. This means that assuming normally distributed returns implies positive probability on the event that returns are less than -100%,  which is impossible for assets like equity where investors are protected by limited liability and hence can lose at most their initial investment.

At short horizons,  this issue is negligible because typical return magnitudes are so small. But it matters more over longer horizons. This is why now that we are paying more attention to long-run dynamics,  we need to address this issue.

Figure 3.2 illustrates this. It shows the empirical distribution of stock market returns from 1927–2022. The top panel shows the distribution of monthly returns,  the middle panel annual returns,  and the bottom panel 10-year returns. We see that for monthly returns the fact that returns are bounded below at -100% does not really matter. It's just extremely unlikely that a monthly return would ever get even close to a loss of this magnitude. As a consequence,  the distribution of monthly returns looks quite symmetric. The magnitudes of upside moves tend to be similar to the magnitudes of downside moves.

In contrast,  for 10-year returns,  the picture is different. Looking at the upside in the bottom panel of Figure 3.2,  we can see 10-year periods with realized returns of 400% or more. On the downside,  of course,  there are no downside moves of similar magnitude. The biggest losses over 10-year periods in this data set are returns of around -50%. As a consequence,  the empirical distribution of 10-year returns is strongly asymmetric. It basically has to be as the upside is unbounded but the downside is limited to -100%.

In contrast,  it is an economically sensible approximation for many types of assets,  although of course not always literally true,  that log returns,  $r = \log(1 + R)$,  are normally distributed.

If log returns are normally distributed,  this means that simple returns plus one,  $1 + R = \exp(r)$,  are log-normally distributed. Since $\exp(r) - 1$ is bounded below by -1 when $r$ is normally distributed,  the log-normal distribution is consistent with the theoretical lower bound on stock returns of -100%. So,  using the log-normal distribution for $1 + R$,  we can have a distribution of one plus simple returns that is realistically right-skewed and bounded below at zero,  but is still fully described by mean and variance.

Figure 3.3 presents an example where $r$ is normally distributed and hence $1 + R$ has a log-normal distribution (the plot shows the distribution of $R$,  not $1 + R$). Note the lower bound at -1 and also the right-skewness (greater upside) of $R$ compared with $r$.

Going in the reverse direction,  if log-normality is approximately a good description of the return distribution,  then,  if we apply the log transformation,  $r = \log(1 + R)$,  to empirically observed returns $R$,  we should be getting a distribution that looks closer to a normal distribution than the distribution of $R$ does.

We can see the effect of the log transformation if we redo the bottom plot from Figure 3.2 for 10-year returns,  but now with log returns. See Figure 3.4. While the distribution is not quite normal,  it is now much closer to being symmetric. The log transformation has shrunk the long upper tail and hence removed the positive skewness. Instead,  the distribution is now somewhat negatively skewed.

At short horizons,  though,  normal distribution can often be a good approximation to the log-normal distribution. The reason is that for small variance,  the log-normal distribution becomes close to symmetric. One way to see this is to note that $\exp(x) \approx 1 + x$ for very small $x$.

Empirically,  we also see that the distribution of historical returns is closer to normal when they are measured over shorter time frames. Check out,  for instance,  the top panel of Figure 3.2. Like a normal distribution,  monthly returns are close to symmetric,  unlike the longer horizon returns in the bottom panel.

But there are some important exceptions from log-normality: Occasionally,  the stock market experiences violent crashes. This makes the left tail of the distribution much fatter than in a normal distribution. Occasionally,  there are also huge upward movements in a single month. This generates the fat right tail of the distribution in the top panel of Figure 3.2.

The log-normal distribution has a number of properties that we will use in the coming weeks. If $r_t \sim N(\mu,    \sigma^2)$ and $1 + R_t = \exp(r_t)$,  then:

$$
\log \mathbb{E}[1 + R_t] = \mathbb{E}[\log(1 + R_t)] + \frac{1}{2} \operatorname{var}[\log(1 + R_t)] = \mathbb{E}[r_t] + \frac{1}{2} \operatorname{var}(r_t) = \mu + \frac{1}{2} \sigma^2 \tag{3.8}
$$

and hence:

$$
1 + \mathbb{E}[R_t] = \exp\left(\mu + \frac{1}{2} \sigma^2\right) \tag{3.9}
$$

Approximately then,  at least for relatively short return measurement intervals such as monthly returns where the return magnitudes are typically not so big that the transformation by the exponential function matters much:

$$
\mathbb{E}[R_t] \approx \mu + \frac{1}{2} \sigma^2 \tag{3.10}
$$

This approximation is a useful rule of thumb to keep in mind. If you see someone presenting average log returns from some investment and the variance of log returns,  you can easily get an estimate of the implied average simple returns using this formula.

## 3.3 STOCK MARKET VALUATION MODELS

With log transformations in our toolkit,  we now turn our attention to valuation models that allow us to analyze how investor expectations and investor sentiment may affect pricing in the stock market (and other risky asset markets). This in turn provides insights about observable variables that may be useful for predicting stock market returns.

For now,  we use **investor sentiment** as a catch-all label to describe forces that affect stock prices and that do not reflect rational expectations of future cash flows of firms. This includes,  for example,  the effects of irrational investor optimism or pessimism about future cash flows. It also includes the stock price effects of time-varying risk aversion that investors may have. In the next lecture,  we'll take a more detailed look at what could explain investor sentiment changes over time.

The discounted cash flow (DCF) valuation models that you are familiar with from your introductory finance classes look somewhat like this:

$$
P_t = \frac{\mathbb{E}_t[D_{t+1}]}{1 + R} + \frac{\mathbb{E}_t[D_{t+2}]}{(1 + R)^2} + \frac{\mathbb{E}_t[D_{t+3}]}{(1 + R)^3} + \ldots \tag{3.11}
$$

where $P_t$ is the present value of cash flows,  $D_{t+1},    D_{t+2},    \ldots$ are future cash flows,  and $R$ is a (risk-adjusted) discount rate. Here we are interested in the valuation of the stock market in aggregate,  so $D$ would represent the aggregate dividends of all stocks. More precisely,  $D_t$ would comprise aggregate dividends plus aggregate share repurchases,  i.e.,  the entire flow of cash to investors. To keep it short,  I'll just refer to $D_t$ as dividends.

You may also recall that if the expected cash flows are growing at a constant rate $G$,  so that $\mathbb{E}_t[D_{t+1}] = (1 + G)D_t$,  $\mathbb{E}_t[D_{t+2}] = (1 + G)^2D_t$,  then we get the so-called Gordon growth model:

$$
\begin{aligned}
    P_t &= D_t \frac{1 + G}{R - G} \\
    \frac{P_t}{D_t} &= \frac{1 + G}{R - G}
\end{aligned}
$$

The trouble with these sorts of valuation models is that they are mixes of summations and multiplicative relationships. For our purposes,  we want something even simpler,  only with additive terms,  not ratios and powers of stuff. We're looking for such a simple valuation framework so that we can easily think through the consequences of time-varying investor sentiment on aggregate stock market prices and the implications for market-timing strategies.

As itturns out,  logs and some approximations can help us here. Consider first the case in which we are at time $t$ and an asset has just one more terminal dividend payment left at $t + 1$ (after it just paid out $D_t$ at $t$). After this terminal payment,  the asset ceases to exist. The return over this last period is:

$$
1 + R_{t+1} = \frac{D_{t+1}}{P_t} \tag{3.14}
$$

We can rewrite the right-hand side as:

$$
\frac{D_{t+1}}{P_t} = \frac{D_{t+1}}{D_t} \cdot \frac{D_t}{P_t} \tag{3.15}
$$

Taking logs of both sides of this equation,  rearranging,  and using the definitions $v_t = \log(P_t/D_t)$ and $d_{t+1} = \log(D_{t+1}/D_t)$,  we get:

$$
v_t = \Delta d_{t+1} - r_{t+1} \tag{3.16}
$$

The left-hand side of this equation is the log price-dividend ratio. Even though this is an extremely simple relationship,  it already tells us something important: If we see a high price-dividend ratio today,  then it must either be the case that future dividends will be high or returns in the future will be low,  or a combination of both. Taking logs helped us get a valuation model,  in terms of the log price-dividend ratio,  that nicely involves only additive terms.

When there is more than one period left,  we calculate returns as:

$$
1 + R_{t+1} = \frac{P_{t+1} + D_{t+1}}{P_t} \tag{3.17}
$$

Taking logs in this case does not immediately lead to a simple additive expression. However,  one can find a quite accurate linear approximation. We won't go into the details of how to do this,  but the end result makes intuitive sense in comparison with the single-period version (3.16):

The result of the approximation is:

$$
v_t = c + \Delta d_{t+1} - r_{t+1} + \rho v_{t+1} \tag{3.18}
$$

where $\rho$ is a number very close to one,  something like 0.96 if returns are measured annually,  or 0.99 if returns are measured quarterly. The constant $c$ doesn't matter much for what we will discuss so I did not write out explicitly what determines this constant.

For those who are interested in seeing the steps to get there: Rewrite (3.17) as:

$$
1 + R_{t+1} = \frac{D_{t+1}}{D_t} \cdot \frac{\frac{P_{t+1}}{D_{t+1}} + 1}{\frac{P_t}{D_t}} = \frac{D_{t+1}}{D_t} \cdot \frac{\frac{P_{t+1}}{D_{t+1}}}{\frac{P_t}{D_t}} \left(1 + \frac{D_{t+1}}{P_{t+1}}\right)
$$

and take logs and let $v_t = \log(P_t/D_t)$:

$$
r_{t+1} = \Delta d_{t+1} + v_{t+1} - v_t + \log\left(1 + \exp(v_{t+1})\right)
$$

Use a first-order Taylor expansion to approximate the last term linearly as a function of $v_{t+1}$ around $\bar{v}$:

$$
\log\left(1 + \exp(v_{t+1})\right) \approx c - (1 - \rho)v_{t+1}
$$

where the derivative in this Taylor expansion is:

$$
(1 - \rho) = \left[\frac{1}{1 + \exp(\bar{v})}\right] \exp(\bar{v})
$$

which means $\rho = \frac{1}{1 + \exp(\bar{v})}$; the constant is $c = \log \rho - (1 - \rho) \log(1/\rho - 1)$. We can see that $\rho$ is a constant very close to one for any reasonable value of $v$. If we take $\bar{v}$ to be the long-term historical average of the price-dividend ratio with annual data,  which is around 3.2,  we have something in the ballpark of $\rho = \frac{1}{1 + \exp(3)} \approx 0.96$ for annual data (and $0.96^{1/4} \approx 0.99$ for quarterly data). Plugging the approximation into (3.17),  we get:

$$
r_{t+1} \approx c + \Delta d_{t+1} + v_{t+1} - v_t - (1 - \rho)v_{t+1}
$$

which we can solve for $v_t$ to get (3.18). This approximation was first proposed by Campbell,  J.Y. and Shiller,  R.J.,  1988. The dividend-price ratio and expectations of future dividends and discount factors. The Review of Financial Studies,  1(3),  pp-228.

The equation (3.18) looks very similar to (3.16)—just with the addition of $\rho v_{t+1}$ (and the constant $c$,  but again that constant won't matter much for anything). So when $v_t$ is high,  there could now be three different ways in which the future plays out: high dividend growth,  low returns,  or a high future price-dividend ratio.

We can also take expectations of (3.18). We get:

$$
v_t = c + \mathbb{E}_t[\Delta d_{t+1}] - \mathbb{E}_t[r_{t+1}] + \rho \mathbb{E}_t[v_{t+1}] \tag{3.19}
$$

which we can solve for:

$$
\mathbb{E}_t[r_{t+1}] = c + \mathbb{E}_t[\Delta d_{t+1}] + \rho \mathbb{E}_t[v_{t+1}] - v_t
$$

So,  if we expect a high return today,  we must either expect high dividends next period,  or a high price-dividend ratio next period,  or a combination of the two.

We can take this further and iterate on (3.18). Substituting $v_{t+1} = c + \Delta d_{t+2} - r_{t+2} + \rho v_{t+2}$ into (3.18),  we get:

$$
v_t = c + \rho c + \Delta d_{t+1} + \rho \Delta d_{t+2} - r_{t+1} - \rho r_{t+2} + \rho^2 v_{t+2}
$$

Doing this $T$ times,  we get:

$$
v_t = \frac{c}{1 - \rho}(1 - \rho^{T+1}) + \sum_{j=1}^{T+1} \rho^{j-1}\left(\Delta d_{t+j} - r_{t+j}\right) + \rho^{T+1}v_{T+1} \tag{3.20}
$$

Now consider taking $T$ to infinity. The first term and the summation term are straightforward. The key question is what happens to $\rho^{T+1}v_{T+1}$. Recall that $\rho$ is a number close to but smaller than one. So $\rho^{T+1}$ goes to zero when $T$ goes to infinity. Then $\rho^{T+1}v_{T+1}$ also goes to zero,  unless the price-dividend ratio is on an explosive path on which it grows without upper bound in the long run and it grows faster than $\rho^{T+1}$ shrinks. But such an exploding dividend-price ratio doesn't really make economic sense. Therefore,  we assume that:

$$
\lim_{T \rightarrow \infty} \rho^{T+1}v_{T+1} = 0 \tag{3.23}
$$

This seems like a reasonable assumption (it's known as a **transversality condition**). Prices should not be wandering away arbitrarily far from dividends. Temporarily,  price levels might vary a lot relative to dividends,  but it would be rather weird if stock prices could diverge on a path towards an infinitely high price-dividend ratio in the long run. We will come back to think more about this assumption in the next lecture,  but for now we will assume that the condition (3.23) holds. With this assumption,  letting $T$ go to infinity yields:

$$
v_t = \frac{c}{1 - \rho} + \sum_{j=1}^{\infty} \rho^{j-1}\left(\Delta d_{t+j} - r_{t+j}\right) \tag{3.24}
$$

which we refer to as the **present-value identity**.

So now we have two possibilities left,  as earlier in (3.16),  but with many future periods: High price-dividend ratio today means that eitherfuture dividends will be high,  or returns in the future will be low. This should make intuitive sense. If you pay a high price for an asset today,  then either you'll be lucky enough that the cash flows you receive from this asset are also high,  or otherwise,  you will have to suffer from earning low returns.

At this point,  (3.24) is just a tautological identity. The relationship between the price-dividend ratio and future dividend growth and returns that we described must hold mechanically,  always. It does not depend on whether markets are efficient,  investors' risk aversion is constant or not,  or anything else. It's just mechanical. So the insights coming from it are also naturally limited. But we can use the identity to do useful things with it.

If we introduce expectations of dividends and returns,  we can turn the identity into a valuation model. We do this by taking expected values of the rightand left-hand side of (3.24) conditional on time-$t$ information. Since $v_t$ is observable at time $t$,  its expectation is just $v_t$. But on the right-hand side,  we have expectations of dividends and returns in the future:

$$
v_t = \frac{c}{1 - \rho} + \sum_{j=1}^{\infty} \rho^{j-1} \mathbb{E}_t[\Delta d_{t+j}] - \sum_{j=1}^{\infty} \rho^{j-1} \mathbb{E}_t[r_{t+j}] \tag{3.25}
$$

So the price-dividend ratio reflects expectations of future dividends and future returns.

The model in (3.25) could now be used for fundamental valuation. We would have to build a forecasting model for future dividend growth. This would give us the expectations of future dividend growth,  $\mathbb{E}_t[\Delta d_{t+j}]$. We could then also plug in the required rate of return $\mathbb{E}_t[r_{t+j}]$ that we would require from a stock market investment. This would then give us a model implied log price-dividend ratio $v_t$ that we could compare to the current actual $v_t$ to estimate the current over/undervaluation of the stock market. For example,  if the model implied $v_t$ is higher than the actual current $v_t$,  we would conclude that the stock market is currently overvalued and hence currently not an attractive investment (and possibly even an opportunity to take a short position).

In the special case that expected log dividend growth is constant,  $\mathbb{E}_t[\Delta d_{t+j}] = g$,  and investors price the stock market with a constant required rate of expected (log) return of $\mathbb{E}_t[r_{t+j}] = \theta$,  the expression in (3.25) simplifies drastically to:

$$
v_t = \frac{1}{1 - \rho}(c + g - \theta) \tag{3.26}
$$

Compare this to the Gordon growth model in (3.11). It's very similar,  showing that it's the difference between expected growth and the required rate of expected return that determines the level of the price-dividend ratio.

Substituting in this result for $v_t$ and $v_{t+1}$ from (3.26) into (3.20),  and solving for expected log returns,  we obtain:

$$
\mathbb{E}_t[r_{t+1}] = \theta \tag{3.27}
$$

which is exactly what it should be: The log return investors can expect to earn is the required rate of expected log return that they priced into the stock market valuation.

## 3.4 A VALUATION MODEL WITH INVESTOR SENTIMENT

Let's use this framework to understand how time-varying investor sentiment could affect prices,  how we could measure sentiment,  and how we could potentially exploit it in our asset allocation strategy. For the purpose of this exercise,  suppose that equation (3.26) represents how **rational** investors—who are not subject to sentiment fluctuations—would value the aggregate stock market. This means that these rational investors expect constant growth of dividends $g$ and they would require an expected return of $\theta$ to hold the outstanding value of all stocks. Let's call the $v_t$ in (3.26) the (log) fundamental value.

In contrast,  suppose that **actual** investors are subject to the influence of investor sentiment. For example,  they are sometimes more optimistic about dividend growth and sometimes more pessimistic. Their valuation of the aggregate stock market is:

$$
v_t = \frac{1}{1 - \rho}(c + g - \theta) + s_t \tag{3.28}
$$

where $s_t$ is the level of sentiment,  with $s_t > 0$ reflecting excessive optimism and $s_t < 0$ excessive pessimism.

Now imagine a rational investor looking at this market,  seeing $v_t$,  as determined by (3.28),  and wondering what rate of return to expect given that stock prices are subject to the influence of investor sentiment. We can answer this question by substituting $v_t$ and $v_{t+1}$ from (3.28) into (3.20). Lots of terms cancel,  and we are left with:

$$
\mathbb{E}_t[r_{t+1}] = \theta + \rho \mathbb{E}_t[s_{t+1}] - s_t \tag{3.29}
$$

Naturally,  if there was no sentiment effect on prices,  as in (3.27),  a rational investor could expect to earn $\theta$,  the rate of return that rational investors would price the market to earn.

But with sentiment,  there is an additional component that reflects that current high sentiment ($s_t$) makes the market overpriced,  which is bad for next-period returns,  while high future sentiment ($\rho \mathbb{E}_t[s_{t+1}]$) makes the market overpriced in the future,  which is good for next-period returns.

Also note that if sentiment and hence mispricing is constant,  $s_t = s$,  then this mispricing component becomes $\rho \mathbb{E}_t[s] - s$,  which is not zero,  so it still affects returns the rational investor can expect. For example,  with constant overpricing,  $s > 0$,  we have $\mathbb{E}_t[s] - s < 0$. This reflects the fact that with a constant level of overvaluation,  even though an investor does not have to suffer from collapses of overpricing in this case,  the investor is paying more for stocks than they are really worth,  given their expected dividends,  which hurts returns.

The relationship in (3.29) also tells us that if we could forecast $s_{t+1}$,  we could calculate expected returns and therefore forecast returns. This means that to forecast returns,  we need to have a model of the dynamics of investor sentiment.

A reasonable starting point for such a model of sentiment could be that sentiment is positively correlated over time (so when sentiment is,  e.g.,  above average today,  it will tend to be above average next quarter) and mean-reverting (so when sentiment is,  e.g.,  above average today,  we expect it to be closer to the average level next quarter). This would mean that sentiment slowly cycles through periods of optimism and pessimism.

We can capture these properties with a first-order autoregressive process,  or AR(1) process:

$$
s_{t+1} = \phi s_t + \eta_{t+1},    \quad \eta_{t+1} \sim \mathcal{N}(0,    \sigma_s^2)
$$

where $0 < \phi < 1$,  which makes sentiment mean-reverting. Thus,  every period,  sentiment is subject to an unpredictable shock $\eta_{t+1}$. In addition,  some of the previous period's sentiment carries over to the next period through the $s_t$ term. In this model,  we have:

$$
\mathbb{E}_t[s_{t+1}] = \phi s_t \tag{3.31}
$$

Therefore,  (3.29) becomes:

$$
\mathbb{E}_t[r_{t+1}] = \theta - (1 - \rho\phi)s_t \tag{3.32}
$$

Note that $(1 - \rho\phi) > 0$. So,  expected returns are low when current sentiment is high,  for two reasons. First,  as we discussed earlier,  even constant high sentiment would mean low expected returns because price is high relative to the expected stream of dividends. Second,  in addition,  expected returns are low because prices are expected to depreciate. Sentiment is mean-reverting ($\phi < 1$),  so if it's high today,  it's likely to be lower next period. So when sentiment is high today,  we can forecast that sentiment will likely go down in the future. Following (3.28),  stock prices will go down along with sentiment.

When we have a relationship between rationally expected returns and a time-varying variable like $s_t$,  we say that there is **return predictability**.

Yet,  to empirically use (3.32),  we need to measure $s_t$. How can we measure it? We'll discuss some empirical proxies for investor sentiment in the next lecture. But for now,  let's look at an indirect way of getting at it. Go back to (3.28) and solve for $s_t$:

$$
s_t = v_t - \frac{1}{1 - \rho}(c + g - \theta) \tag{3.33}
$$

Now plug this into (3.32). The result is:

$$
\mathbb{E}_t[r_{t+1}] = \text{const.} - (1 - \rho\phi)v_t \tag{3.34}
$$

where I collected all the constants in the first term. So the log price-dividend ratio,  which we can directly observe,  should capture the time-variation in expected returns induced by investor sentiment. If investors were rational,  under the assumptions we made,  the price-dividend ratio would not vary. So to the extent it varies,  it varies with the investor sentiment level $s_t$. This is why the price-dividend ratio predicts returns. Times of high price-dividend ratios,  for example,  are times when a rational investor in this model should expect low future returns.

In practice,  there can be a distortion that can prevent the price-dividend ratio from accurately capturing the sentiment level. If rationally expected dividend growth rates are not constant but time-varying,  this would introduce rational reasons for why the price-dividend ratio should vary. If so,  then not all variation in $v_t$ in our sentiment valuation model (3.28) is due to variation in $s_t$. Some of the variation would be due to time-varying $g$. Then the price-dividend ratio may be high not because the market is currently overpriced due to positive sentiment,  but rather because high rationally expected growth of dividends justifies a high current price relative to current dividends. This makes $v_t$ a less reliable predictor of future returns.

It is also possible that the risk premium that rational investors demand,  and that we have assumed to be constant at $\theta$ in (3.28),  may in fact be time-varying. Then the price-dividend ratio may be high because investors require a low risk premium. Then future returns will be low because a stock market investment will earn only this low risk premium. So this is just like the sentiment effect that we discussed in the sense that a high current price-dividend ratio forecasts low future returns. So for now we just include time-varying risk aversion as one potential manifestation of sentiment. We can just include the time-varying part of $\theta$ in $s_t$.

## 3.5 MACRO VS. MICRO MARKET INEFFICIENCY

At this point,  it's useful to reflect a bit on the possibility that the sentiment of not-so-rational investors could have some impact on the stock market valuation overall. If such sentiment reflects excessive optimism or pessimism about future cash flows and affects prices,  then there is a market inefficiency. In an efficient market,  prices are supposed to reflect a rational assessment of the information available at a point in time,  not sentiment disconnected from fundamentals.

A common argument in modern finance against the existence of such market inefficiencies is that "smart money,  " i.e.,  highly sophisticated professional investors,  would take advantage of such market inefficiencies by trading against them and thereby eliminating them. But how strong is this force against market inefficiencies? This depends on the level of aggregation that we are interested in (e.g.,  individual stock level or at an aggregate level,  say the market portfolio) and the nature of the riskiness of the assets involved.

Consider first individual stocks. Suppose there are lots of idiosyncratic mispricings. Idiosyncratic here means that whether a stock is overor undervalued is totally random and not systematically related to,  say,  the firm's industry,  its size,  or other common attributes that firms may have. In this case,  a hedge fund can run a "pairs trading" strategy,  taking long positions in undervalued stocks and pairing each long position with a short position in an overvalued stock that has highly correlated returns because it's in the same industry,  has the same size,  etc. The high correlation ensures that the pair long-short position has relatively little risk because the short position to a large extent hedges the risk of the long position. Moreover,  putting lots of such pairs together into a portfolio results in a lot of the remaining risk being diversified away. As a consequence,  very little risk is left in this portfolio. Hence,  if these kinds of market inefficiencies existed,  it would be an extremely attractive opportunity that hedge funds or other smart-money investors would aggressively exploit and thereby largely eliminate. For exactly that reason,  these sorts of inefficiencies are unlikely to be big.

Now consider the stock market as a whole. Suppose,  for instance,  that the stock market portfolio as a whole is overvalued by 50% and smart-money investors know about this overvaluation (without any uncertainty about the degree of misvaluation). Unfortunately for them,  there is no way to construct a low-risk,  high-return trade that exploits this misvaluation. Unlike in the pairs trading example,  there is no other asset class out there that has a return that is highly correlated with the stock market. In other words,  one cannot really hedge the risk of a short position in the overvalued stock market with a long position in some other asset class. As a consequence,  taking a bet against stock market overor undervaluation is necessarily risky. Recall that a typical one-standard deviation move in the stock market in a single year is a 20% return. So if an investor stays out of the market due to concerns about overvaluation,  this investor takes a substantial risk that they could experience a performance shortfall of 20% or more relative to a broad stock index. For an investor who responded to overvaluation by taking a short position in the stock market,  the performance shortfall in this case would be even bigger.

Moreover,  even if smart-money investors are correct in their judgment that the stock market is misvalued,  it could take years until the misvaluation is corrected. And since betting against the entire stock market is very risky,  substantial losses can pile up until the position finally pays off. This means smart-money investors may have to write many quarterly letters to their outside investors pleading with them to be patient and arguing that their position will win in the long run. Yet,  outside investors are rarely patient enough to see this through. As the economist John Maynard Keynes,  who was also an active speculator in markets,  once remarked: "Markets can stay irrational longer than you can stay solvent."

One well-known example is the famous value investor Julian Robertson of Tiger Management during the technology stock bubble in the late 1990s. Tech stock prices were going through the roof in 1999,  before crashing sharply in March 2000. In mid-1999,  tech stocks seemed extremely overvalued. Julian Robertson decided to exit long positions in tech stocks and to bet against further price rises of tech stocks. Unfortunately for him,  prices kept rising at a fast pace. His funds started to suffer outflows. In October 1999,  Tiger Management increased the redemption period for investors from 3 to 6 months in an attempt to curb outflows. But nevertheless,  in the last quarter of 1999,  their funds lost about 25% of their assets through withdrawals. In March 2000,  Robertson threw in the towel and announced the liquidation of his funds,  just a few days before the start of the technology stock crash.

Figure 3.5 shows the monthly flows of the Jaguar fund,  one of the funds managed by Tiger Management,  and compares them with the flows of the Quantum fund,  managed by George Soros. Soros took a very different approach. He tried to "ride the bubble" until the end,  with long positions in tech stocks until March 2000. At the start of the crash,  he quickly reduced these positions. His performance in late 1999 and early 2000,  therefore,  was much better than Julian Robertson's. As the figure shows,  this made a dramatic difference to the timing of flows. The Jaguar fund had strong outflows in the second half of 1999 before being closed down in the first quarter of 2000. The Quantum fund also suffered outflows once its long positions got hit by the crash in March 2000. But due to the prior inflows as well as the large gains it had achieved on its long positions,  the Quantum fund was able to weather those outflows. After the Quantum fund exited tech stock positions quickly in the wake of the crash,  outflows stopped a couple of months later.

To examine the relationship to flows,  we back out fund flows from data on assets under management and fund performance. Unfortunately,  our data on assets under management is incomplete. Among the funds managed by the five managers in Figure 3.5a,  we are able to calculate complete monthly histories.

The bottom line of all this is that betting against the misvaluation of the entire market,  or large sectors of the market,  is very risky. And it's not even clear that betting early on against misvaluation is necessarily the best strategy for a smart-money investor. Temporarily riding a bubble of inflating misvaluation of the stock market,  like George Soros seems to have done,  may be preferable. In the short run,  therefore,  smart money investors may even further amplify misvaluation.

Overall,  it's quite implausible that smart money would lean aggressively against misvaluation at the aggregate stock market level.

Another argument that is often made is that professional investors manage most of the money invested in the stock market and so it must be professionals,  not the likely less sophisticated individual investors that effectively determine pricing in the stock market. However,  according to the U.S. Financial Accounts,  at the end of 2021,  individual investors held about 37% of total stock market capitalization directly,  and an additional roughly 25% indirectly through mutual funds,  ETFs,  and direct-contribution retirement products. This means that a substantial share of equity investments is directly or indirectly controlled by individual investors. The investment products that individual investors purchase in the mutual funds and ETF space are often quite narrowly defined (e.g.,  a stock fund,  a bond fund,  or a stock fund focused on a specific sector,  etc.). By allocating money to these products,  it is the individual investors who are effectively making the allocation decision at the asset-class level,  not the professional managers running these funds. Professionals,  or the computer algorithms they use,  then decide on how the allocated flows are invested in individual securities within the asset class,  but the asset-class level allocation decision is left to individuals.

In contrast,  at the individual stock level,  most of the funds products that individual investors hold leave it to professional investment managers to choose the individual securities within asset class buckets. So we should expect individual investors to have much less influence on the relative pricing of individual securities within asset classes.

In summary,  at the macro level,  for asset classes,  investment flows are more likely to be driven by sentiment-prone retail investors than at the individual security level. These asset-class level flows are also more difficult to counteract for smart money investors because doing so is risky. The conclusion from all this is that we should not expect that smart money investors exert a strong influence to keep markets efficient at the macro level. Markets are likely to be quite efficient at the micro level,  but inefficiencies are more likely at the macro level.

Our next step will be to look into getting estimates of the returns we can expect from a stock market in the presence of misvaluation. We do this first by looking at simulations of the model from above,  then we'll look at actual data.

## 3.6 RETURN PREDICTION REGRESSIONS: SIMULATIONS

Recall from earlier that our valuation model with sentiment had the following equation for the log price-dividend ratio:

$$
v_t = \frac{1}{1 - \rho}(c + g - \theta) + s_t
$$

The fundamental value component of the log price-dividend price ratio is obtained as $v_t - s_t$. We then get the level of the fundamental value,  $F_t$,  by adding the log dividend and then exponentiating:

$$
F_t = \exp(v_t - s_t + d_t) \tag{3.36}
$$

The price level is:

$$
P_t = \exp(v_t + d_t) \tag{3.37}
$$

I simulate unexpected changes in log dividends as a normal random variable:

$$
d_{t+1} - d_t = g + \varepsilon_{t+1},    \quad \varepsilon_{t+1} \sim \mathcal{N}(0,    \sigma_d^2) \tag{3.38}
$$

and the level of sentiment as in (3.30):

$$
\eta_{t+1} \sim \mathcal{N}(0,    \sigma_s^2) 
$$

i.e.,  also with normally distributed shocks. Based on the simulated $d_t$ and $s_t$ series,  I then calculate a series of first $v_t$,  and then $F_t$ and $P_t$ using the above formulas. Finally,  I get a series of realized log returns by solving (3.18) for $r_{t+1}$,  which yields:

$$
r_{t+1} = c + \Delta d_{t+1} + \rho v_{t+1} - v_t \tag{3.40}
$$

Plugging the simulated $d_t$,  $v_t$ series into this formula then yields the simulated log returns series.

I pick parameters that make the series have properties close to the actual stock market index return and price-dividend ratio series at a quarterly frequency: $\rho = 0.99$ (the parameter in the log-linearization that is very close to one),  $g = 0.01$ (expected log dividend growth); $\theta = 0.02$ (unconditional expected log return). I set the volatility of dividend shocks to $\sigma_d = 0.07$.

A key question we should look into is how the persistence of sentiment affects the nature of mispricing and the return predictability that follows from it. For this reason,  I will show results for several different values of $\phi$ in (3.31). For each value of $\phi$,  I look for a value of the sentiment shocks $\sigma_s$ that makes the standard deviation of $s_t$ equal to 0.20. In other words,  I want to see the effects of changing persistence of sentiment without changing the typical magnitudes of sentiment-induced misvaluation.

Figure 3.6 shows simulated price paths of $F_t$ and $P_t$ for a total length of 400 quarters and for two different values of $\phi$: $\phi = 0.15$ in the top panel and $\phi = 0.95$ in the bottom panel. In both cases,  there is a substantial degree of misvaluation due to the time-varying investor sentiment,  often exceeding +30% or -30% of the fundamental value. But which value of $\phi$ we pick makes a big difference in how fast misvaluation corrects. In the top panel,  if investor sentiment is not very persistent,  mispricing corrects very quickly and so we get relatively high-frequency variation of the price around the fundamental value. In contrast,  with $\phi = 0.95$ in the bottom panel,  investor sentiment is highly persistent and we get long-lasting cycles of misvaluation.

Which of the two cases would make it easier for a smart investor to profit from misvaluation? Clearly the first case. In this case,  if the investor recognizes at a certain point in time that there is big misvaluation,  then,  because sentiment has low persistence,  it's very likely that this misvaluation will correct soon. A bet against misvaluation is therefore likely to pay off soon. In contrast,  in the high-persistence case in the bottom panel,  an investor could correctly diagnose that there is,  say,  undervaluation (such as around quarter 245 in the plot),  but then it can take another 5 to 10 years until the misvaluation finally gets corrected and the bet against the mispricing eventually pays off.

We can see this more clearly if we look at the scatter plots of log returns in period $t + 1$,  i.e.,  $r_{t+1}$,  on log sentiment in the previous period,  $s_t$,  shown in Figure 3.7 for these two 400-quarter simulation runs. These scatter plots show us how informative $s_t$ is about the return in the next quarter.

As the top panel shows,  with low persistence,  there is a clearly visible negative relationship between sentiment and next-quarter returns: high sentiment strongly forecasts low future returns. This reflects the relatively quick correction of mispricing in the low-persistence case.

In contrast,  the bottom panel shows that when persistence is high,  there is at best a very weak relation between sentiment and next-quarter returns. So,  even if we perfectly know the level of mispricing at $t$,  it's still very difficult to predict what returns will be next quarter! And remember that typical magnitudes of mispricing in the simulations in both panels are the same. The only difference is that mispricing in the top panel is mean-reverting quickly,  while it can be very long-lasting in the bottom panel. Long-lasting mispricing is difficult to exploit,  even if it's big!

Let's explore this more through the lens of a statistical model that an investor could then use to get estimates of conditional expected returns (which the investor could then fit into a portfolio optimization model). Let's run a regression of log returns on lagged log sentiment:

$$
r_{t+1} = a + bs_t + \varepsilon_{t+1}
$$

Basically,  we are fitting a straight line with slope $b$ and intercept $a$ through the scatter plots we just looked at. Once we have an estimate of the regression coefficients $a$,  $b$—let's label them $\hat{a}$,  $\hat{b}$—we can form an estimate of the conditional expected next-quarter log return as $\hat{a} + \hat{b}s_t$.

To see what such a regression delivers on average (or said differently,  in expectation),  I now generate 1,  000 simulated series of returns and sentiment,  each with a length of 400 quarters. I run the regression above on each of these simulated 400-quarter series. So for each simulated series,  I get one set of estimates $\hat{a}$,  $\hat{b}$.

Table 3.1 shows the average $\hat{b}$ across the 1,  000 simulations. I also calculate the average $R^2$,  which shows how much of the variance of $r_{t+1}$ is explained by the predictable component $bs_t$.

| $\phi = 0.15$ | $\phi = 0.55$ | $\phi = 0.95$ |
|---------------|---------------|---------------|
| Slope Coefficient  | -0.85         | -0.46         | -0.07         |
| $R^2$                 | 0.40           | 0.21           | 0.02           |

In line with the intuition from the scatter plots,  when $\phi$ is low,  there is a strong negative relationship between $r_{t+1}$ and $s_t$ as shown by the large negative average slope coefficient of -0.85 and the high $R^2$ of 40%. The high $R^2$ basically says the same thing as our visual impression from the scatter plot for $\phi = 0.15$ where we can see the negative relationship just by eyeballing the scatter plot.

In contrast,  when $\phi = 0.95$,  the average slope coefficient is much,  much smaller (-0.07) and the $R^2$ is much lower (2%). Again,  this lines up well with what we concluded from the scatter plot: if there is any predictive relationship,  it must be weak,  because we can't really see it in the scatter plot.

In this high persistence case,  $\phi = 0.95$,  how difficult is it,  statistically,  to pin down the slope coefficient? We can get an idea by looking at the different estimates $\hat{b}$ we get across the 1,  000 simulation runs. Figure 3.8 presents a histogram. The variation in $\hat{b}$ across the different simulation runs is substantial! It is not all that unlikely that an estimate ends up quite close to zero—which looks like returns are only very weakly predictable,  even though the magnitudes of mispricing are substantial.

Moreover,  we get this result that the slope $b$ is difficult to estimate precisely even though we are looking at really long samples here in these simulation runs. In practice,  the sample length of 400 quarters we are using here would be unusually long. And it's not only 400 quarters long here,  but we also know for sure that the underlying process of sentiment and dividend growth,  and their parameters,  are not changing over time. In practice,  using a 400-quarter sample of data to estimate these sorts of predictive relationships runs into questions about whether the predictive relationship we are trying to uncover could really be stable over such a long period of time. So,  in practice,  we would be even less certain about the predictive relationship between measures of misvaluation and future return.

All this shows how exceedingly difficult market timing can be,  even if the stock market goes through cycles of large misvaluations that we can perfectly measure!

And we haven't even gotten to the main difficulty,  which is that a real-world investor must predict out-of-sample. Here we have only examined in-sample regressions. For example,  an investor living in our simulations and trying to make an investment decision at,  say,  quarter 200 does not yet have the benefit of knowing the coefficient estimates of a regression run with data all the way until quarter 400. The investor would only be able to use data up to quarter 200 to inform themselves about the predictive relationship.

But before we get to this problem of out-of-sample prediction,  let's first look at actual data on returns and price-dividend ratios to see whether any of the cases for different $\phi$ that we considered so far could be a good approximation to reality.