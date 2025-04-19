---
title: Lecture 2-Asset Allocation with Multiple Risky Assets
tags:
  - asset_allocation
  - covariance_matrix
  - multiple_assets
  - portfolio_theory
  - risk_return
aliases:
  - Asset Allocation
  - Multiple Risky Assets
key_concepts:
  - CRRA preferences
  - Mean-standard deviation frontier
  - Optimal portfolio framework
  - Portfolio return variance
  - Tangency portfolio formulas
---

# Lecture 2-Asset Allocation with Multiple Risky Assets
[[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]]
We now extend our optimal [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] framework to allow for multiple risky assets. This gets us close to the type of models that are used by asset managers of large portfolios to decide how much to allocate to different asset classes.

We still stick to the IID returns assumption for now.

In your intro investments course,  you saw the graphical representation of the solution for the optimal portfolio. Recall the hyperbolic shape of the mean-standard deviation frontier,  the tangency portfolio,  and the capital market line that depicts all possible combinations of the risk-free asset with the tangency portfolio. Here we are going to use matrix algebra to get explicit formulas for the tangency portfolio and its risk-return properties.

I use bold lowercase letters for vectors and bold uppercase letters for matrices. I use $\boldsymbol{\iota}$ to denote a column vector with all elements equal to one and $\boldsymbol{I}$ for the identity matrix (which has ones on its diagonals and zeros everywhere else). Letters or symbols that are not in boldface are scalars.

### 2.1 Risk and return at the portfolio level

Consider $N$ risky assets with an $N \times 1$ vector of returns $\boldsymbol{r}$ and expected returns $\mathbb{E}[\boldsymbol{r}]$. We will often look at excess returns

$$

\begin{equation*}

\boldsymbol{z}=\boldsymbol{r}-\boldsymbol{\iota} R_{f},         \quad \boldsymbol{\mu}=\mathbb{E}[\boldsymbol{z}] \tag{2.1}

\end{equation*}

$$

Very important for our [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] analysis is the $N \times N$ covariance matrix of returns

$$

\begin{equation*}

\boldsymbol{\Sigma}=\mathbb{E}\left[(\boldsymbol{z}-\boldsymbol{\mu})(\boldsymbol{z}-\boldsymbol{\mu})^{\prime}\right] \tag{2.2}

\end{equation*}

$$

For analyzing portfolio risk and return,  we need to know a few rules on how the moments of portfolio returns,  e.g.,  mean and variance,  depend on moments of individual asset returns. Suppose we have a portfolio with $N$ assets and the weight of every asset (in terms of the proportion of the portfolio's market value accounted for by each asset) is collected in the $N \times 1$ portfolio weight vector $\boldsymbol{\omega}=\left(\omega_{1},         \omega_{2},         \ldots,         \omega_{N}\right)^{\prime}$. Then the portfolio return is

$$

\begin{equation*}

R_{p}=\boldsymbol{\omega}^{\prime} \boldsymbol{r} \tag{2.3}

\end{equation*}

$$

and the expected portfolio return

$$

\begin{equation*}

\mathbb{E}\left[R_{p}\right]=\boldsymbol{\omega}^{\prime} \mathbb{E}[\boldsymbol{r}] \tag{2.4}

\end{equation*}

$$

We can calculate the variance from the $N \times N$ covariance matrix of individual asset returns as

$$

\begin{equation*}

\operatorname{var}\left(R_{p}\right)=\boldsymbol{\omega}^{\prime} \boldsymbol{\Sigma} \boldsymbol{\omega} . \tag{2.5}

\end{equation*}

$$

This last formula shows that all $N \times N$ elements of the covariance matrix play a role in determining the portfolio return variance. This is important. The portfolio variance depends not only on how volatile individual asset returns are,  but also on how strongly they covary,  i.e.,  whether they tend to move together or not. Here is how this looks like in the $N=2$ case,  where $\rho$ denotes the correlation of the two asset returns and $\rho \sigma_{1} \sigma_{2}$ their covariance:

$$

\begin{align*}

\operatorname{var}\left(R_{p}\right) & =\binom{\omega_{1}}{\omega_{2}}^{\prime}\left(\begin{array}{cc}

\sigma_{1}^{2} & \rho \sigma_{1} \sigma_{2} \\

\rho \sigma_{1} \sigma_{2} & \sigma_{2}^{2}

\end{array}\right)\binom{\omega_{1}}{\omega_{2}}  \tag{2.6}\\

& =\omega_{1}^{2} \sigma_{1}^{2}+2 \omega_{1} \omega_{2} \rho \sigma_{1} \sigma_{2}+\omega_{2}^{2} \sigma_{2}^{2} \tag{2.7}

\end{align*}

$$

So if the portfolio has positive weight on both assets,  $\omega_{1}>0$ and $\omega_{2}>0$,  then,  due to the middle term in this expression,  the higher the correlation of the two asset returns,  the higher the portfolio return variance.

Sometimes we are interested in the covariances of returns of the individual assets that are in the portfolio with the return of the overall portfolio. We can get this vector of covariances by post-multiplying the covariance matrix with the portfolio weight vector,

$$

\left(\begin{array}{c}

\operatorname{cov}\left(R_{1},         R_{p}\right)  \tag{2.8}\\

\operatorname{cov}\left(R_{2},         R_{p}\right) \\

\ldots \\

\operatorname{cov}\left(R_{N},         R_{N}\right)

\end{array}\right)=\boldsymbol{\Sigma} \boldsymbol{\omega} .

$$

### 2.2 Optimal [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] with multiple risky assets

Let's now turn to finding the optimal portfolio weight when we have multiple risky assets. As in the last lecture,  we assume the investor has CRRA preferences and we'll use a first-order approximation of marginal utility to simplify the problem. The following analysis is pretty much analogous to our analysis in the single risky asset case in the last lecture,  but with some vectors and matrices replacing some scalars to account for the fact that we have multiple risky assets.

If the investor starts with wealth $W_{0}$ at the beginning of a period and invests proportions $\boldsymbol{\omega}$ of this initial wealth into the $N$ risky assets and the rest in the risk-free asset,  then the total investment in risky assets accounts for a proportion $\boldsymbol{\iota}^{\prime} \boldsymbol{\omega}=\sum_{i}^{N} \omega_{i}$ of initial wealth and the rest,  $1-\boldsymbol{\iota}^{\prime} \boldsymbol{\omega}$ is allocated to the risk-free asset. Hence the return on the investor's wealth portfolio is

$$

\begin{equation*}

R_{w}=\left(1-\boldsymbol{\iota}^{\prime} \boldsymbol{\omega}\right) R_{f}+\boldsymbol{r}^{\prime} \boldsymbol{\omega} \tag{2.9}

\end{equation*}

$$

or,  equivalently,

$$

\begin{equation*}

R_{w}=R_{f}+\boldsymbol{z}^{\prime} \boldsymbol{\omega} \tag{2.10}

\end{equation*}

$$

The investor's wealth at the end of the period is $W=W_{0}\left(1+R_{w}\right)$.

The investors' objective is the same as in the single risky asset case in the previous lecture

$$

\begin{equation*}

\max _{\boldsymbol{\omega}} \mathbb{E}[U(W)] \quad \text { s.t. } W=W_{0}\left(1+R_{w}\right),         \tag{2.11}

\end{equation*}

$$

but $R_{w}$ now depends on a vector of portfolio weights $\boldsymbol{\omega}$,  not just a single risky asset portfolio weight,  that the investor is trying to optimize. The first-order condition of this problem is analogous to the single risky asset case,  but now we have $N$ first order conditions instead of just one.

$$

\begin{equation*}

\mathbb{E}\left[z \frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])}\right]=0 \tag{2.12}

\end{equation*}

$$

In this vector of first-order conditions,  there is one first-order condition for each element of $\boldsymbol{z}$.

Approximating $\frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])}$ linearly,  we get,  analogous to last lecture,

$$

\begin{equation*}

\frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])} \approx 1-\gamma(\boldsymbol{r}-\mathbb{E}[\boldsymbol{r}])^{\prime} \boldsymbol{\omega} \tag{2.13}

\end{equation*}

$$

just now with a vector of returns and,  correspondingly,  a vector of portfolio weights $\boldsymbol{\omega}$. Substituting this approximation into the first-order condition (2.12),  we get

$$

\begin{equation*}

\mathbb{E}\left[\boldsymbol{z}\left\{1-\gamma(\boldsymbol{r}-\mathbb{E}[\boldsymbol{r}])^{\prime} \boldsymbol{\omega}\right\}\right]=0 \tag{2.14}

\end{equation*}

$$

With $E[\boldsymbol{z}]=\boldsymbol{\mu}$ and $\mathbb{E}\left[\boldsymbol{z}(\boldsymbol{r}-\mathbb{E}[\boldsymbol{r}])^{\prime}\right]=\boldsymbol{\Sigma}$,  we get

$$

\begin{equation*}

\boldsymbol{\mu}-\gamma \boldsymbol{\Sigma} \boldsymbol{\omega}=0 \tag{2.15}

\end{equation*}

$$

where the covariance matrix $\boldsymbol{\Sigma}$ has taken the place of the variance of risky asset return in the single risky asset case. We can solve this expression for the optimal risky asset share

$$

\begin{equation*}

\boldsymbol{\omega}=\frac{1}{\gamma} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{2.16}

\end{equation*}

$$

So instead of division by the variance of the asset return in the single risky asset case we now have the inverse of the covariance matrix. Taking the inverse of a matrix is sort of like dividing. The proportion of wealth invested in the risk-free asset is

$$

\begin{equation*}

\omega_{f}=1-\boldsymbol{\iota}^{\prime} \boldsymbol{\omega}=1-\frac{1}{\gamma} \boldsymbol{\iota}^{\prime} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{2.17}

\end{equation*}

$$

Let's look at some properties of this solution. Note that we can can further rescale the weights $\boldsymbol{\omega}$ so that they sum up to unity. This yields the weights within the risky asset portfolio:

$$

\begin{equation*}

\boldsymbol{\omega}^{*}=\frac{1}{\boldsymbol{\iota}^{\prime} \boldsymbol{\omega}} \boldsymbol{\omega}=\frac{1}{\boldsymbol{\iota}^{\prime} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{2.18}

\end{equation*}

$$

This tells us something important and very useful: The solution for $\boldsymbol{\omega}^{*}$ does not depend on the level of risk aversion! All investors,  irrespective of their degree of risk aversion should therefore hold a risky asset portfolio with the same composition (as long as they have the same beliefs about $\boldsymbol{\Sigma}$ and $\boldsymbol{\mu}$ ). Risk preferences should only matter for how much of their wealth they allocate to the risky asset portfolio overall and to the risk-free asset. By scaling up or down the risky asset portion of their wealth,  investors can adjust the riskiness of their wealth portfolio. This is sufficient for getting a portfolio consistent with their risk preferences.

Thus,  the decision on how to structure a portfolio can be separated into two independent steps. First,  how to split the risky asset portfolio among the different risky assets; second,  how to allocate between this risky asset portfolio and the risk-free asset. This result is called the two-fund separation theorem.

The risky asset portfolio with weights $\boldsymbol{\omega}^{*}$ is the tangency portfolio that you already encountered in your introductory investments course. Let's denote with $R^{*}$ and $Z^{*}$ the returns and excess returns of this tangency portfolio,  respectively.

To get some intuition for what the optimal portfolio solution does and how it depends on expected returns and correlations,  suppose we have $N=2$ and

$$

\boldsymbol{\mu}=\binom{\mu_{1}}{\mu_{2}},         \quad \boldsymbol{\Sigma}=\sigma^{2}\left(\begin{array}{ll}

1 & \rho  \tag{2.19}\\

\rho & 1

\end{array}\right)

$$

Then

$$

\boldsymbol{\Sigma}^{-1}=\frac{1}{\sigma^{2}\left(1-\rho^{2}\right)}\left(\begin{array}{cc}

1 & -\rho  \tag{2.20}\\

-\rho & 1

\end{array}\right)

$$

Plugging into (2.18) we get

$$

\begin{equation*}

\boldsymbol{\omega}^{*}=a\binom{\mu_{1}-\rho \mu_{2}}{\mu_{2}-\rho \mu_{1}} \tag{2.21}

\end{equation*}

$$

for some constant $a$ that collects all the scalar factors.

Now let's think about some special cases. If the two assets' returns are uncorrelated,  $\rho=0$,  then optimal portfolio weights are proportional to their expected returns. Suppose $\mu_{1}>\mu_{2}$. Then the investor puts a higher share into asset 1 than into asset 2 . This should be intuitive. It makes sense to invest more in the higher-earning asset when the two assets are otherwise identical. But why not put everything into asset 1 (or even short asset 2 and invest more than $100/% of the risky asset portfolio into asset 1)? Diversification benefits! Having some of asset 2 in the portfolio,  but not too much,  can still be useful because it lowers the risk of the portfolio.

Now consider a case where $\rho$ is very close to 1 and again $\mu_{1}>\mu_{2}$. In this case,  the assets are,  in terms of risk,  almost perfect substitutes. As a consequence,  a long-short position,  going long in asset 1 ,  short in asset 2 ,  is optimal: it earns a positive expected returns $\mu_{1}-\mu_{2}>0$,  but it has almost no risk because the returns of the two assets are almost perfectly correlated.

### 2.3 Systematic risk

How does a mean-variance optimizing investor think about a new asset that could be added to the existing portfolio? When is it attractive in terms of risk and return? When does it make sense to alter the portfolio to include more or less of this asset? As we will see now,  the mean-variance optimal portfolio strikes a perfect balance between the expected return that an asset contributes to the portfolio and the risk that it contributes. This contribution to portfolio risk is what we call systematic risk.

We can see the risk contribution of assets to the overall portfolio by examining the portfolio variance in equation (2.5). Note from (2.8) that the expression $\boldsymbol{\Sigma} \boldsymbol{\omega}$ in

$\operatorname{var}\left(R_{p}\right)=\boldsymbol{\omega}^{\prime} \boldsymbol{\Sigma} \boldsymbol{\omega}$ is a vector of covariances,  so the pre-multiplication by $\boldsymbol{\omega}^{\prime}$ forms a weighted sum of these covariances,  i.e.,
$$\operatorname{var}\left(R_{p}\right) = \omega_{1} 
\underbrace{\operatorname{cov}\left(R_{1},   R_{p}\right)}_{
\begin{array}{c}
\text{Risk} \\
\text{contribution} \\
\text{of asset 1}
\end{array}
} 
+ \omega_{2} \operatorname{cov}\left(R_{2},   R_{p}\right) + \ldots + \omega_{N} \operatorname{cov}\left(R_{N},   R_{p}\right)$$

We have now decomposed the overall portfolio variance in the pieces that come from each asset. How much risk each asset brings to the portfolio is determined by how much of this asset is in the portfolio,    i.e.,    its portfolio weight,    times the risk contribution measured by the covariance $\operatorname{cov}\left(R_{i},         R_{p}\right)$. For the same weight,    an asset that has a higher covariance with the portfolio return adds more risk to the portfolio.

Dividing by $\operatorname{var}\left(R_{p}\right)$ on both sides,    we can express the risk contributions as shares of total portfolio risk. We get

$$

\begin{equation*}

1=\omega_{1} \beta_{1}+\omega_{2} \beta_{2}+\ldots+\omega_{N} \beta_{N} \tag{2.23}

\end{equation*}

$$

The systematic risk of asset $i$ is measured by

$$

\begin{equation*}

\beta_{i}=\frac{\operatorname{cov}\left(R_{i},  R_{p}\right)}{\operatorname{var}\left(R_{p}\right)} . \tag{2.24}

\end{equation*}

$$

One important take-away at this point is that systematic risk is investor specific. How much an asset contributes in terms of risk to an existing portfolio depends on what else is in the portfolio,    which will typically differ across investors. If asset $i$ has a high return covariance with the other assets in the portfolio,    then $\beta_{i}$ will be high. If the other assets' returns don't covary much with asset $i$ 's returns,    then $\beta_{i}$ will be low.

Now let's assume the investor's portfolio is mean-variance optimal,    i.e.,    it has weights $\boldsymbol{\omega}^{*}=\boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}$ as in (2.18),    with the modification that I dropped the scalar constant that rescales the portfolio in (2.18) to have weights that add up to $100/%. Whether we scale the portfolio weights by some constant factor does not matter for any of the calculations that follow in this section,    so I just drop the scaling factor to make the expression for $\omega^{*}$ less messy.

With these optimal portfolio weights,    following (2.8),    individual assets have a vector of covariances

$$

\begin{equation*}

\boldsymbol{\Sigma} \boldsymbol{\omega}^{*}=\boldsymbol{\Sigma} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}=\boldsymbol{\mu} \tag{2.25}

\end{equation*}

$$

and,    following (2.5),    we have the portfolio variance

$$

\begin{equation*}

\operatorname{var}\left(R^{*}\right)=\boldsymbol{\omega}^{* /} \boldsymbol{\Sigma} \boldsymbol{\omega}^{*}=\boldsymbol{\omega}^{* \prime} \boldsymbol{\mu}=\mu^{*} \tag{2.26}

\end{equation*}

$$

where $\mu^{*}=\mathbb{E}\left[Z^{*}\right]$ is the expected excess return of the mean-variance optimal portfolio. Dividing the vector covariances in (2.25) by the portfolio variance in (2.26),    we then get a vector of betas:

$$

\begin{equation*}

\boldsymbol{\beta}^{*}=\frac{1}{\operatorname{var}\left(R^{*}\right)} \boldsymbol{\Sigma} \boldsymbol{\omega}^{*}=\frac{1}{\mu^{*}} \boldsymbol{\mu} . \tag{2.27}

\end{equation*}

$$

Rearranging,    we see that expected returns of individual are tightly linked to their systematic risk with respect to the mean-variance optimal portfolio

$$

\begin{equation*}

\boldsymbol{\mu}=\boldsymbol{\beta}^{*} \mu^{*} \tag{2.28}

\end{equation*}

$$

For an asset $i$,    therefore,  

$$

\begin{equation*}

\mathbb{E}\left[Z_{i}\right]=\beta_{i}^{*} \mathbb{E}\left[Z^{*}\right] \tag{2.29}

\end{equation*}

$$

which looks exactly like the relationship predicted by the Capital Asset Pricing Model (CAPM) that you encountered in your introductory investments course - just with one very important difference: in the CAPM,    $\beta_{i}^{*}$ would be the beta with respect to the market portfolio return and $\mathbb{E}\left[Z^{*}\right]$ would be the expected excess return on the market portfolio. Here they are just the beta with respect to an investor's optimal portfolio,    which need not be the same as the market portfolio,    and $\mathbb{E}\left[Z^{*}\right]$ is the expected excess return on the investor's portfolio,    not the market portfolio.

The condition (2.29) tells us that when the existing portfolio is mean-variance optimal,    then expected returns of all assets must have expected excess returns exactly proportional to their betas with respect to the portfolio return $R^{*}$. The beta of asset $i$ tells us how much risk we would add to the portfolio if we added more of this asset to the portfolio. This is what we call systematic risk. This systematic risk originates from covariance,    i.e.,    the degree to which the return of asset $i$ and the portfolio $R^{*}$ move together in the same direction.

Furthermore,    equation (2.29) tells us that if the portfolio with return $R^{*}$ is already optimal,    then there cannot be any asset out there that offers an expected return that is lower or higher than what equation (2.29) prescribes. Each asset's expected return must be exactly commensurate with the systematic risk $\beta_{i}^{*}$ that this asset brings to the portfolio so that no asset looks attractive enough to add more of it to the portfolio,    or unattractive enough to reduce its position.

Otherwise,    if we could find such an asset $i$ that violates condition (2.29),    we could improve our portfolio's Sharpe ratio by adding more of asset $i$ to the portfolio (if the expected return is higher than required) or taking some of it out,    and possibly shorting it (if the expected return is lower than required). For example,    if an asset $i$ has $\mathbb{E}\left[Z_{i}\right]>\beta_{i}^{*} \mathbb{E}\left[Z^{*}\right]$,    it would make sense for the investor to take more of asset $i$ into the portfolio,    because this would contribute to a relatively small amount of portfolio risk,    but a relatively big expected excess return.

We can decompose the total risk of an asset into systematic and idiosyncratic components. Note that $\beta_{i}^{*}=\operatorname{cov}\left(R_{i},         R^{*}\right) / \operatorname{var}\left(R^{*}\right)$ is an ordinary least squares (OLS) regression slope coefficient in a regression of $R_{i}$ on $R^{*}$. This means we can decompose $R_{i}$ as follows

$$

\begin{equation*}

R_{i}=a_{i}+\beta_{i}^{*} R^{*}+\varepsilon_{i} \tag{2.30}

\end{equation*}

$$

where $\operatorname{cov}\left(R^{*},         \varepsilon_{i}\right)=0$. This decomposition shows that movements in $R_{i}$ are partly due to movements perfectly aligned with $R^{*}$ (systematic) and partly due to movements uncorrelated with $R^{*}$ (idiosyncratic). Taking the variance of the leftand right-hand sides,  

$$

\begin{equation*}

\operatorname{var}\left(R_{i}\right)=\left(\beta_{i}^{*}\right)^{2} \operatorname{var}\left(R^{*}\right)+\operatorname{var}\left(\varepsilon_{i}\right),  \tag{2.31}

\end{equation*}

$$

we have now broken the total risk of asset $i,         \operatorname{var}\left(R_{i}\right)$,    into two components: Systematic risk,    $\left(\beta_{i}^{*}\right)^{2} \operatorname{var}\left(R^{*}\right)$,    and idiosyncratic risk,    $\operatorname{var}\left(\varepsilon_{i}\right)$.

Since systematic risk determines an assets (un)attractiveness,    not the idiosyncratic risk,    Sharpe Ratios are not good measures of the reward to risk ratio for individual assets,    because the Sharpe Ratio uses total volatility as a risk measure,    not just the systematic risk component.

Of course,    this reasoning based on (2.29) applies only to small changes to the portfolio at the margin. The change in portfolio risk from a small addition of asset $i$ to the portfolio depends approximately only on the asset's systematic risk because the idiosyncratic risk diversifies away in the portfolio. Yet,    if the investor were to add a lot of asset $i$ to the portfolio,    portfolio return variance and the covariance of portfolio return and asset $i$ 's return changes. Moreover,    some of the risk that was idiosyncratic now becomes systematic: The higher the allocation to asset $i$,    the higher becomes the correlation of $R_{i}$ and $R_{w}$. In the extreme case,    where there is so much of asset $i$ in the portfolio that $R^{*} \approx R_{i}$,    the $\varepsilon_{i}$ component vanishes.

This illustrates that what an investor considers as systematic or idiosyncratic risk depends on her existing portfolio. Since $\beta_{i}^{*}$ depends on what's in the investor's existing portfolio,    $\beta_{i}^{*}$ will typically be different for different investors. Hence,    how investors perceive systematic risk of assets will also differ.

### 2.4 Maximum Sharpe ratio

We can also show that when the condition (2.29) holds,    and hence $R^{*}$ is truly the return on an optimal portfolio that cannot be improved any further,    then this optimal portfolio achieves the highest possible Sharpe Ratio of any portfolio that can be constructed from the available assets.

To see this,    start from (2.29),  

$$

\begin{equation*}

\mathbb{E}\left[Z_{i}\right]=\frac{\operatorname{cov}\left(Z_{i},  R^{*}\right)}{\operatorname{var}\left(R^{*}\right)} \mathbb{E}\left[Z^{*}\right] \tag{2.32}

\end{equation*}

$$

and let $\sigma_{i}=\operatorname{var}\left(Z_{i}\right)^{1 / 2},         \sigma=\operatorname{var}\left(R^{*}\right)^{1 / 2}$ and let $\rho_{i}$ denote the correlation of $Z_{i}$ and $R^{*}$. Since $\left|\rho_{i}\right| \leq 1$,    it is true that

$$

\begin{equation*}

\left|\operatorname{cov}\left(Z_{i},  R^{*}\right)\right|=\left|\rho_{i}\right| \sigma_{i} \sigma \leq \sigma_{i} \sigma \tag{2.33}

\end{equation*}

$$

Substituting this inequality into (2.32) and rearranging,    we get

$$

\begin{equation*}

\frac{\left|\mathbb{E}\left[Z_{i}\right]\right|}{\sigma_{i}} \leq \frac{\mathbb{E}\left[Z^{*}\right]}{\sigma} \tag{2.34}

\end{equation*}

$$

This tells us that the Sharpe ratio of any asset $i$ (or any combination of assets) cannot exceed the Sharpe ratio of the optimal portfolio. In other words,    the portfolio with weights $\boldsymbol{\omega}^{*}$ that we constructed in (2.18) has the highest possible Sharpe ratio of any portfolio combining the same assets.

### 2.5 Market equilibrium

As we did in the previous lecture for a single risky asset,    we can again ask how the [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] of an individual investor fits together with the choices of other investors in equilibrium where supply equals demand. Our market equilibrium analysis in the previous lecture can be interpreted as dealing with the demand and supply of risky assets as a whole class. Here we are now asking about the composition of risky asset portfolios: what sort of composition investors would like to have,    and how the market gets these desired portfolio weights in line with the supply of securities actually available. Because we are interested in this compositional question,    we now focus on the relative quantities of risky assets,    expressed as a proportion of the total market capitalization of risky assets that investors demand or that is available as supply.

Supply is then given by the weights of the market portfolio of risky assets. This is the portfolio in which the weight of each asset is equal to ratio of the asset's market capitalization (price times shares outstanding),    mcap $_{i}$,    to the aggregate market capitalization of all risky assets:

$$

\begin{equation*}

\omega_{m,  i}=\frac{m_{c a p}}{\sum_{j=1}^{N} m_{c a p}^{j}} \tag{2.35}

\end{equation*}

$$

To see how equilibrium plays out,    in a first simple thought experiment,    suppose all investors want to hold the same portfolio,    i.e,    they all want to have the same proportions

of risky assets in their portfolios. In this case it is very easy to see which portfolio they must necessarily end up with in equilibrium: the market portfolio. Holding the market portfolio is the only way in which all investors can hold the same portfolio. Then the weight of each asset in the market overall,    aggregated across all investors is the same as the weight the asset has in each investor's portfolio. For example,    suppose each investor wants to hold $3/% of their portfolio,    in terms of market value,    in Apple stock. The only way this is possible is if the aggregate market capitalization of Apple is $3/% of the aggregate market capitalization of all risky assets.

How would the market get to such an equilibrium in which the market clears? Prices need to adjust so that investors' desired portfolio weights end up being identical to market portfolio weights. Suppose for example that the market for Apple stock does not clear (yet): there is excess demand,    i.e. investors want to hold more shares of Apple than there are outstanding shares of Apple. This means that investors will bid up the price. This has two effects. First,    a rise in the price (with expectations of future fundamentals unchanged) lowers the expected return of Apple. This makes Apple stock less attractive. Hence investors' desired portfolio share of Apple,    and hence demand,    goes down. At the same time,    the rise in the price raises Apple's weight in the market portfolio and in each investor's portfolio. So both of these effects of the price change work to get investors' desired portfolio weights closer to market portfolio weights. If the price rise is big enough,    desired portfolio weights and market portfolio become equal,    supply equals demand,    and the market therefore clears.

Now let's analyze what happens when investors not only want to hold identical portfolios,    but their demands come from mean-variance optimization: they all want to hold portfolios with weights according to our optimal risky asset portfolio formula (2.18) and they have the same beliefs about expected returns,    variances,    and covariances. Then prices of risky assets must adjust such that the optimal portfolio ends up being equal to the market portfolio. And the return $R^{*}$ is then equal to the market portfolio return $R_{m}$. This means that the relationship in (2.29) now becomes

$$

\begin{equation*}

\mathbb{E}\left[Z_{i}\right]=\frac{\operatorname{cov}\left(Z_{i},  R_{m}\right)}{\operatorname{var}\left(R_{m}\right)} \mathbb{E}\left[Z_{m}\right]=\beta_{i} \mathbb{E}\left[Z_{m}\right] \tag{2.36}

\end{equation*}

$$

which is the Capital Asset Pricing Model (CAPM)! So the CAPM results from combining the assumption that investors have identical beliefs about risk and return and seek to hold mean-variance optimal portfolios with the market equilibrium condition that demand equals supply.

For the applications we focus on in this course,    the assumption that all investors want the same portfolio is not realistic. But,    still,    the market portfolio is an important reference point.

If we take a position different from the market portfolio,    there must be,    for the market to clear,    someone willing to take the other side in the sense of also deviating from market portfolio weights,    but in the opposite direction. If we overweight an asset in our portfolio,    then,    collectively,    the rest of the investors in the market have to underweight this asset. Therefore,    if we are entertaining such a deviation,    it is always important to ask: Why would anyone be willing to take the other side? Can we have confidence that we are right and the party taking the other side is not,    or that we have special circumstances (e.g.,    a better ability to bear certain types of risk than others) that make an asset more attractive to us than it is to others?

The market portfolio is a very special portfolio. Aside from new issues of stocks,    delistings,    and needs to reinvest dividends,    holding the market portfolio does not require any trading. For example,    if we hold the market portfolio and the price of asset $i$ goes up from yesterday to today more than the market overall,    its weight in our portfolio goes up. However,    its weight goes up exactly the same in the market portfolio. Hence,    we don't have to trade to keep holding the market portfolio. This is why index funds typically follow value-weighted indices where asset weights depend on stocks' market capitalization relative to the aggregate market capitalization of all stocks in the index,    just like in the market portfolio.

 ![500](CleanShot%202024-10-24%20-003106@2x.png)

Figure 2.1: Turnover rate of Vanguard Total Stock Market Index Fund (VITNX)

Because trading needs are so minimal,    holding the market portfolio,    or more generally a value-weighted portfolio,    is very cheap in terms of trading cost. As an example,    Figure (2.1) shows some portfolio statistics for the Vanguard Total Stock Market Index Fund. This is a fund that aims to replicate the performance of the entire market portfolio of U.S. stocks as represented by the CRSP value-weighted index. As the figure shows,    the turnover rate of this fund is less than $5/% per year. This means that only $5/% of the portfolio's total value is traded each year. Most of this is accounted for by dividends,    proceeds from mergers that must be reinvested,    and investment in initial or seasoned public offerings that come to the market. But other than this,    there is basically no need to trade.

> [!Figure 2.2: From Pershing Square Capital Management Annual Letter 2015]
> popular indexes are market-cap weighted. This means that the larger the market cap of the company,    the larger its representation in the index. In other words,    as the stock price rises,    its weighting in the index increases,    and the index fund is required to buy more of the company. While value investors typically buy more as stock prices decline (assuming intrinsic value has also not declined),    market-cap weighted index funds do the opposite. They are inherently momentum investors,    forced to buy more as stock prices rise,    magnifying the risk of overvaluation of the index components.
There is also a lot of misconception out there about the mechanics of running a market-capitalization weighted portfolio like the Vanguard Total Stock Market Index Fund or any other market-capitalization weighted fund. One popular misconception is that market-cap weighting implies that the fund has to purchase more shares when prices go up. This fuels the concern that the presence of market-cap weighted funds in the market may lead to asset price bubbles where price increases cause further mechanical buying,    which leads to further price increases not justified by fundamentals,    etc. Figure 2.2 shows an example from Bill Ackman's (Pershing Square Capital Management) 2015 letter to shareholders. This sort of argument is mistaken,    however. If the price of an asset in a market-cap weighted portfolio rises by $x/%,    then,    everything else equal,    the weight of the asset in a market-capitalization weighted index rises by $x/%. At the same time,    the weight of the asset in a market-capitalization weighted portfolio also rises by $x/%-without any trading. Therefore,    after this price change,    the asset's weight in the portfolio is still exactly equal to the share that a market-capitalization weighted index fund wants it to be. There is zero need to trade.

### 2.6 Estimation of return moments in the multiple risky asset case

Last lecture we discussed empirical estimation of mean and variance of returns. To implement the optimal portfolio according to our formula (2.18),    we now also need an estimate of the covariance matrix $\boldsymbol{\Sigma}$. We can estimate it from historical returns as

$$

\begin{equation*}

\widehat{\boldsymbol{\Sigma}}=\frac{1}{T-1} \sum_{t=1}^{T}\left(\boldsymbol{R}*{t}-\hat{\boldsymbol{\mu}}\right)\left(\boldsymbol{R}*{t}-\hat{\boldsymbol{\mu}}\right)^{\prime} \tag{2.37}

\end{equation*}

$$

where

$$

\begin{equation*}

\hat{\boldsymbol{\mu}}=\frac{1}{T} \sum_{t=1}^{T} \boldsymbol{R}_{t} \tag{2.38}

\end{equation*}

$$

Table 2.1: Annualized mean,    standard deviations,    and correlations for various asset classes 1980-2022

 ![500](CleanShot%202024-10-24%20-003108@2x.png)
Table 2.1 shows an example from the same data of several asset classes that we already looked at last lecture. I broke the covariances into standard deviations (shown in the second row) and correlations (matrix below the second row). The underlying data are monthly returns,    but I annualized the mean returns and standard deviations by multiplying with 12 and $\sqrt{12}$,    respectively.

Note that we are now considering Treasury bonds,    and also the other bond asset classes,    as risky assets. In Lecture 1,    we did a crude calculation of the average investor's risky asset share where we lumped Treasury bonds and other bonds into a broad riskfree asset class. Here we are now taking a more refined approach where only short-term Treasury bills are viewed as risk-free while bonds with maturities beyond one year are viewed as risky. And,    indeed,    the table above shows that the return standard deviations of the bond asset classes are substantial.

For the estimates of mean returns,    we discussed in the last lecture how to estimate standard errors that give us an idea about the statistical uncertainty we have about expected returns.

It would be useful to also get a sense for the statistical uncertainty about covariances. However,    the covariance matrix is a high-dimensional object. For our purposes it's not necessary to now write down and study the formula for the standard error of the whole covariance matrix estimate. But to get a sense of the magnitudes,    let's focus on the

standard error of the variance estimates (i.e.,    the entries on the diagonal of the covariance matrix). In the special case of normally distributed returns,    the estimate of the variance of asset $i$ on the diagonal of the covariance matrix has standard error

$$

\begin{equation*}

\text { s.e. }\left(\hat{\sigma}*{i}^{2}\right)=\frac{\sqrt{2}}{\sqrt{T}} \sigma*{i}^{2} \tag{2.39}

\end{equation*}

$$

A back-of-the-envelope calculation: Let's say we estimate the variance of an aggregate stock market index. Suppose the estimated standard deviation of annual returns on the aggregate stock market index is roughly $20/% and so the variance is about $4/%. Then with 10 years of data,    s.e. $\left(\hat{\sigma}^{2}\right) \approx 0.018$. So,    using again a Bayesian interpretation,    as when we looked at the standard error of the mean last lecture,    we would conclude that with $95/% probability,    the true variance is in the interval $0.04 \pm 2 \times 0.018$. This is quite wide,    but not quite as wide as in the case of the estimate of $\mu$. With 100 years s.e. $\left(\hat{\sigma}^{2}\right) \approx 0.006$,    which is quite precise. Of course,    one can ask the same question about variance estimation that one can ask about estimation of the expected return: Is data from so long ago relevant for assessing the likely values of variance going forward?

However,    as we will see shortly,    there may be an opportunity to get much more precise estimates of variances and covariances by measuring returns over higher frequencies. Unfortunately,    the same trick is not going to work for getting more precise estimates of expected returns.

### 2.6.1 Effect of measurement frequency on statistical precision

Since we can often choose the frequency at which we measure returns,    we may wonder what is the best frequency? One way in which we might evaluate what's "best" is to focus on the effects on our statistical uncertainty about the true values of expected returns and variances. Having less statistical uncertainty is better. As it turns out,    there is a drastic difference in how the standard error of estimates of expected return relates to measurement frequency and how the standard error of variances (and covariances) relates to measurement frequency.

Consider first the expected return. Suppose we have returns measured over $T$ periods,    say,    annual. The average return over these $T$ periods gives us the expected return estimate $\hat{\mu}$. As we noted last lecture,    the standard error is

$$

\begin{equation*}

\text { s.e. }(\hat{\mu})=\frac{1}{\sqrt{T}} \sigma \text {. } \tag{2.40}

\end{equation*}

$$

But now we wonder whether we should perhaps chop each of these periods into $n$ smaller subperiods and measure returns at this higher frequency. We then have a total number

of periods of $T \times n$. Based on our annualization formulas from last lecture,    the expected returns at this higher measurement frequency would be approximately $1 / n$ times the annual average return,    i.e.,    $\mu / n$. The standard deviation would be $1 / \sqrt{n}$ times the standard deviation of annual returns,    i.e.,    $\sigma / \sqrt{n}$. Therefore,    the standard error of the higher-frequency estimate $\hat{\mu}(n)$ would be

$$

\begin{equation*}

\text { s.e. }(\hat{\mu}(n))=\frac{1}{\sqrt{n T}} \frac{\sigma}{\sqrt{n}}=\frac{1}{\sqrt{T} n} \sigma \tag{2.41}

\end{equation*}

$$

This is $1 / n$ times the standard error of annual returns. However,    as we discussed,    the magnitude of expected returns is also smaller by factor $1 / n$. Hence,    the ratio of true expected return to standard error remains unchanged. It is invariant to the measurement frequency! So chopping the return measurement intervals into smaller pieces is not going to help us at all to get more precise estimates of expected returns. If we make the measurement intervals smaller,    the signal (true expected return) shrinks at the same rate as the standard error.

As a consequence,    if we annualize the higher-frequency estimate in order to get an apples-to-applies comparison,    i.e.,    we look at $n \hat{\mu}(n)$,    then the standard error for this annualized estimate is simply $n \times$ s.e. $(\hat{\mu}(n))=\frac{1}{\sqrt{T}} \sigma$,    i.e.,    exactly the same as the standard error when we use annual returns!

This is a very important lesson. If we are trying to improve the precision of our expected return estimates,    it's of no use to go to higher return measurement frequency! Say we have 30 years of data at most on an asset and we use the average return as an estimate of the expected return. Then the total length of this sample period,    30 years,    effectively pins down the standard error of the expected return estimates. It does not matter for the statistical precision of our estimate whether we measure the returns annually,    monthly,    daily,    or at some other frequency.

Now,    interestingly,    the situation is very different for variances and covariances. Recall that for the variance estimate,    the standard error is

$$

\begin{equation*}

\text { s.e. }\left(\hat{\sigma}^{2}\right)=\frac{\sqrt{2}}{\sqrt{T}} \sigma^{2} \tag{2.42}

\end{equation*}

$$

The key is that this standard error depends on the variance,    while the standard error of the mean in (2.40) depends on the standard deviation. If we divide the return measurement periods into $n$ subperiods,    then this variance falls by a factor of $1 / n$. The standard error of the higher-frequency estimate $\hat{\sigma}(n)^{2}$ becomes

$$

\begin{equation*}

\text { s.e. }\left(\hat{\sigma}(n)^{2}\right)=\frac{\sqrt{2}}{\sqrt{n T}} \frac{\sigma^{2}}{n}=\frac{1}{n^{3 / 2}} \frac{\sqrt{2}}{\sqrt{T}} \sigma^{2} \tag{2.43}

\end{equation*}

$$

If we look at the ratio of the true variance,    which falls by factor of $1 / n$ and the standard error,    which falls by a factor of $\frac{1}{n^{3 / 2}}$,    we see that the ratio rises by $(1 / n) / n^{3 / 2}=\sqrt{n}$. In other words,    the standard error falls relative to the true variance. This means we gain in precision!

If we annualize the higher-frequency variance estimate,    i.e.,    we look at $n \hat{\sigma}(n)^{2}$,    then the standard error for this annualized estimate is

$$

\begin{equation*}

n \text { s.e. }\left(\hat{\sigma}(n)^{2}\right)=\frac{1}{\sqrt{n}} \frac{\sqrt{2}}{\sqrt{T}} \sigma^{2} \tag{2.44}

\end{equation*}

$$

which is smaller,    by factor $1 / \sqrt{n}$,    than the standard error when we use annual returns. The same factor applies to covariances as well,    but we are not going to show this explicitly.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-048.jpg?height=798&width=985&top_left_y=1048&top_left_x=532)

Figure 2.3: Distribution of annualized mean estimates when returns are measured at different measurement frequencies

Figures 2.3 and 2.4 illustrate this with simulations. I simulate $T=10,        000$ daily returns by drawing from a normal distribution such that the annualized returns (assuming 250 trading days per year) have mean 0.05 and standard deviation 0.20 . I calculate the mean and standard deviation of these daily returns. Then I aggregate the returns to annual returns by summing the daily returns within 250 -day windows (if I do it by

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-049.jpg?height=789&width=987&top_left_y=351&top_left_x=577)

Figure 2.4: Distribution of annualized standard deviation estimates when returns are measured at different measurement frequencies

properly compounding the daily returns,    the results are very similar). I calculate the mean and standard deviation of these annual returns. Then I repeat this 1,    000 times each with a new random draw of a daily return series of length $T=10,        000$.

Figures 2.3 shows that the distribution of the mean of annual returns and distribution of the annualized mean estimated from daily returns (i.e.g,    daily return mean times 250) is basically identical,    as expected based on our earlier standard error calculations. In contrast,    Figure 2.4 shows that the distribution of annualized standard deviations estimated from daily returns (i.e.,    daily return standard deviation times $\sqrt{250}$ ) is far smaller than the standard deviation of annual returns. The annualized standard deviations estimated from daily returns are much closer to the true standard deviation of 0.20. In other words,    these estimates are much more precise.

This is potentially extremely useful. The covariance matrix $\boldsymbol{\Sigma}$ is an important input into the mean-variance optimal portfolio formula. If it is estimated with too much error,    the error may render the estimated portfolio weights useless. This is,    in fact,    one of the major problems that practical applications of portfolio optimization struggle with and where clever improvements can make a difference. One first step is to do what our analysis above suggests: Make the estimate of $\boldsymbol{\Sigma}$ more precise by using higher-frequency

data (say,    daily or weekly rather than annual data). In Table 2.1 I have used monthly data,    which is not as good as daily or weekly,    but better than annual.

That said,    while higher-frequency data is useful for covariance matrix estimation,    we also need to keep in mind some limitations.

First,    by going to higher measurement frequencies,    we can only get more precise estimates of variances if random shocks to returns over longer periods are always composed of smaller random shocks over shorter subperiods. This means that,    for example,    for variances of daily returns to give us more precise estimates than variances of monthly returns,    the monthly returns should be composed of a steady series of random shocks,    as opposed to just occasional jumps in prices on a few days with little price movement inbetween these infrequent jumps. ${ }^{1}$ To illustrate: Suppose once every ten years,    the stock market experiences a day in which the market crashes with a huge negative return on a single day (say,    $-20/% ). Let's also stick to the notion that returns are serially independent. Hence a crash is not followed by a predictable reversal of stock prices afterwards. If we have data that spans ten years and includes one of those crashes,    the variance estimate will capture the existence of such crashes. While variance as a risk measure might not do enough to properly characterize the severity of the crash,    if the data includes the crash,    the variance estimate will be substantially increased by the crash data point. However,    dividing return measurement intervals into shorter periods is not going to help us to get a more precise estimate of the frequency and magnitude of such crashes because most return measurement periods do not include a crash.

Market microstructure can also interfere if we try to measure returns from transaction prices at very high frequency,    especially for assets that are relatively illiquid. At high time resolution,    returns can be distorted by the bid-ask spread,    for example. If a buy order comes in,    it gets executed at the (high) ask price,    if a sell order comes in,    it gets executed at the (low) bid price. As a flow of orders comes in,    randomly switching between buys and sells,    the prices at which transactions occur tends to bounce around between the lower bid and higher ask prices. If we measure returns at such high frequency that we capture a lot of this bouncing around between bid and ask,    but this bouncing between bid and ask is not really reflecting any variation in the value of the asset. This means a variance estimate based on very high-frequency return data may overstate the true variance because it contains the bid-ask bounce effects in addition to variance in the value of the asset.

[^6]Non-synchronicity effects are another microstructure phenomenon that will distort covariance estimates constructed from transaction prices at very high frequency. Suppose you have two assets: Asset $A$ which is very liquid and usually trades every microsecond,    and asset $B$ which is very illiquid and trades only about once per hour. If we go to very high frequency - say,    5 minute returns - to estimate covariances,    it will happen very often that there is a piece of news that affects the true value of both assets,    but only the price of liquid asset $A$ responds immediately,    while it may often take another hour or so until the price of asset $B$ adjusts. But this stale price of asset $B$ that is recorded in a returns data file is not a true price. If someone actually tried to trade,    the price would adjust. It just didn't because it happened to be the case that nobody wanted to trade. With such non-synchronicity of prices,    it may seem,    based on 5 minute return data that the covariance of the returns of asset $A$ and $B$ is really low,    when in fact it is much higher. In contrast,    covariances estimated from daily returns in this example would have virtually no distortion from non-synchronicity and would reveal a higher covariance.

Similar problems can appear when assets are traded in different time zones. A returns data set may record daily prices for assets on the same day,    but if one asset traded in Tokyo and the other in New York,    they are clearly not measured at the same point in time. Hence,    a covariance estimate based on these daily returns would underestimate the true covariance.

An extreme form of this latter problem shows up with highly illiquid assets like private equity,    private-market debt securities,    and infrastructure assets. These assets rarely trade. And if we don't observe market prices regularly,    it's difficult to estimate covariances,    and,    as a consequence,    it's difficult to figure out how much risk such assets bring to a portfolio. More on this in lecture 9.

### 2.7 Optimal portfolio weights based on empirical estimates of return moments

Now let's use the estimates of means and covariances in Table 2.1 to construct the mean-variance optimal risky asset portfolio according to our formula (2.18) which I repeat here:

$$

\begin{equation*}

\boldsymbol{\omega}^{*}=\frac{1}{\boldsymbol{\iota}^{\prime} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}} \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{2.45}

\end{equation*}

$$

I now use a plug-in approach where we simply replace the vector $\boldsymbol{\mu}$ with the mean excess returns estimates from Table 2.1,    which I label $\overline{\boldsymbol{z}}$,    and the covariance matrix $\boldsymbol{\Sigma}$ with the

estimated covariance matrix from Table 2.1 (recall that a covariance is the product of the two standard deviations of the pair of asset returns and their correlation),    which I label $\widehat{\boldsymbol{\Sigma}}$. I then calculate

$$

\begin{equation*}

\hat{\omega}^{*}=\frac{1}{\iota^{\prime} \widehat{\boldsymbol{\Sigma}}^{-1} \overline{\boldsymbol{z}}} \widehat{\boldsymbol{\Sigma}}^{-1} \overline{\boldsymbol{z}} \tag{2.46}

\end{equation*}

$$

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-052.jpg?height=1012&width=1201&top_left_y=594&top_left_x=424)

Figure 2.5: Optimal allocation of risky asset portfolio based on estimated return moments

Figure 2.5 presents the result. The bars in this figure show the elements of the portfolio weight vector $\hat{\boldsymbol{\omega}}^{*}$. This result may be somewhat surprising. The portfolio is mostly a combination of long positions in government bonds (U.S. Treasury and international) and domestic value stocks,    as well as a short position in international stocks. Other asset classes only play a minor role.

These results are quite sensitive to the inputs,    though. So our work is not done yet.

A first step to understand a bit better the potential fragility of the plug-in solution to the optimal portfolio problem is to conduct a sensitivity analysis. In general,    it's quite difficult to predict how changes in a small number of inputs affects the optimal portfolio weights. The covariance matrix is a big object. It's difficult to tease out simple

relationships between inputs to the formula and the optimal weights that are the outputs when the formula involves an inverse of a relatively big covariance matrix. All of the elements of the covariance matrix and the mean return vector can interact in ways that are difficult to isolate. But we can sometimes get a rough idea by seeing what happens when we change some of the input numbers.

The perhaps most striking fact of the portfolio in Figure 2.5 is the high allocation to bonds. One may be concerned that,    at least in part,    this is a consequence of the fact that bond returns have been fantastic during the past 40 years that our data covers in this exercise. At the beginning of this four-decade period,    interest rates were very high and they have trended down throughout these four decades. This long downward trend was certainly not fully anticipated in the early 1980s when interest rates were high. As a consequence,    part of the high returns that bonds realized over the past 40 years was an unexpected positive surprise. So our estimates of expected excess returns based on historical returns from the past four decades may overstate the returns that can be expected going forward. We will look into all this in much greater detail when we discuss bonds and interest rates in a future session. But for now let's just do a simple sensitivity check: How do the results change if we reduce our estimate of the expected excess returns of the three bond categories by one (annualized) percentage point?

One percentage point is not much. Recall that in the last lecture we estimated the standard error of the mean returns in the three bond categories and the standard error was roughly one percent for each of them. So in this sensitivity check we are just considering a relatively mild deviation of one standard error.

Subtracting one percentage point from the mean returns of the three bond categories and then recalculating the optimal portfolio yields weights of shown in Figure 2.6a. Comparing with the weights before this modification,    we see a reduction in the allocation to international and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]],    but,    surprisingly,    an increase in the U.S. Treasury bond allocation. This illustrates how difficult it is to anticipate the change in the optimal portfolio weights that results from changing some of the inputs of the portfolio formula. The overall allocation to bonds of all three categories combined does not seem very sensitive to the potentially too optimistic bond return expectations.

Another useful sensitivity check can help us understand the conditions that lead to short positions in international stocks in the optimized portfolio. Looking back at Table 2.1 and focusing on the stock asset classes,    we see that the three stocks asset classes - domestic,    international,    and value stocks-have high correlations above 0.60. At the same time,    the mean excess returns are quite different,    with value stocks having about four percentage points higher mean excess returns than international stocks,    and domestic stocks somewhere inbetween. From a portfolio optimization viewpoint,    this looks like an opportunity to construct a position that earns high expected return with

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-054.jpg?height=1410&width=966&top_left_y=290&top_left_x=536)

(b) Mean excess return of international stocks raised to be the same as domestic stocks

Figure 2.6: Sensitivity analysis

little risk: go long value stocks and short international stocks. This position earns the spread in mean returns between the two asset classes. At the same time,    due to the high correlation,    much of the unexpected movements in returns cancel out. High correlation means that the returns tend to move together in the same direction; so then going long in one asset and short the other means that the returns offset to a large extent,    leaving very little residual risk relative to the size of the spread in mean returns that the position earns.

We can see this mechanism at work when we change the mean return inputs. I set the mean excess return of international stocks to be the same as domestic stocks,    i.e.,    1.9 percentage points higher relative to the estimate from historical data. Recalculating the optimal portfolio weights we get the allocations shown in Figure 2.6b. Now the short position in international stocks is gone. But bond allocations change,    too,    even though we made no change to bond expected return or covariance estimates,    which illustrates again how difficult it is to predict what happens to optimal allocations when one changes a few of the inputs.

Another way of checking sensitivity is to examine how the optimal weights change if we use inputs from different time periods. For this exercise,    I estimate mean excess returns and the covariance matrix over 10-year periods. I start at the beginning of 1990 and use data from 1980 to 1989 to calculate the optimal weights. Then I move the data window forward by one month and recalculate the weights; then I repeat until the end 10 -year data window reaches the end of the data set at the end of 2022.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-055.jpg?height=941&width=1185&top_left_y=1058&top_left_x=486)

Figure 2.7: Weights of estimated mean-variance efficient portfolio without shrinkage (10 years of data to estimate means and covariances)

Figure 2.7 shows the results. In the latest decade,    the weights are somewhat stable and not too extreme. But in the first decade,    they take extreme values: In the early years we see weights of more than $400/% in [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] and a roughly similarly sized

short position in Treasury bonds. This is effectively an extremely highly levered bet on corporate credit. Based on 10-year lagged data on returns,    and taking these data as the true expected excess returns and covariances,    this looked like an attractive position back then.

But we should be skeptical about such extreme weights coming out of a portfolio optimization formula. After all,    if such an extreme long-short bet was so attractive in the 1990s,    how come other investors didn't exploit it? If they had tried to exploit it,    prices of corporate and treasury bonds would have adjusted to make the trade less attractive.

And there is good statistical reason to be skeptical. With 10-year data windows,    the estimates of mean excess returns are very imprecise. With 10-years of data,    the standard error of the mean is about $2/% for Treasury and corporate bond returns,    which is substantial relative to the estimated mean excess returns for these two asset classes. Therefore,    it is quite likely that the extreme long corporate,    short Treasury bond position that the optimal portfolio formula recommends is just an artifact of estimation error in the mean excess returns (which would also explain why it disappeared subsequently in Figure 2.7).

That such extreme weights can occur as output of the portfolio optimization formula is quite typical for plug-in implementations of the mean-variance efficient portfolio weights. Especially if one feeds in estimates of mean excess returns that were obtained from a relatively short time window of only a decade or two.

Now there are good reasons why sometimes we may want to use data windows that are relatively short. We may be worried that markets and the global economy have changed so much over time that data from several decades ago may no longer be very relevant for forecasting returns and covariances in the future. For this reason,    we now look at statistical methods that can help us increase the precision of the inputs to our portfolio optimization formula.

### 2.8 Shrinkage estimation

The estimation approach we have discussed so far starts from a viewpoint of complete ignorance about $\boldsymbol{\mu}$ and $\boldsymbol{\Sigma}$. We proceeded as if,    before looking at historical data,    we basically have no idea whatsoever what the values of expected returns,    variances,    and covariances are likely to be. And then we just set $\boldsymbol{\mu}$ and $\boldsymbol{\Sigma}$ to whatever the data tells us the estimates are.

This doesn't seem quite right. Surely we would think that an expected excess return of,    say,    the domestic stock market in the vicinity of,    say,    $5/% annually in excess of the risk-free rate is more likely than the expected return exceeding $100/% ? It would not make economic sense that expected returns are so high,    as people would have to have crazily high levels of risk aversion for stocks to offer such high rates of expected return. Based on a priori considerations,    before looking at any data,    we would say that such high expected returns are totally implausible. Yet,    if we take the sample average return as the only piece of information about the expected return,    we are not making any use of such prior knowledge that we may have. This prior knowledge may be vague,    but as we will see,    it can still be useful to obtain better estimates of return moments.

The Bayesian branch of statistics offers tools that allow use to describe mathematically how prior knowledge expressed as a [[Lecture 1- Probability Distributions of Returns|probability distribution]],    the prior distribution,    can be combined with evidence from data to obtain a posterior distribution that reflects the combined information from the prior and the data. For our purposes here,    we don't have to work through all that math required for working with the full prior and posterior [[Lecture 1- Probability Distributions of Returns|probability distribution]]s. For practical purposes,    we can get quite far by just using a heuristic approach that captures the essence of the Bayesian method for the purpose of choosing portfolios.

Let's start with the prior beliefs. Suppose we think,    a priori,    that a reasonable number for expected excess returns of the risky assets under consideration is $5/%. Then,    our prior mean vector (the mean of the prior [[Lecture 1- Probability Distributions of Returns|probability distribution]]) $\boldsymbol{\mu}_{0}$ is a vector in which all elements are equal to 0.05 . This does not mean at all that we are certain about this number,    but we see it as a reasonable starting point. Bayesian statistics (under the assumption that both the prior distribution and the deviations of realized excess returns from $\boldsymbol{\mu}$ are normally distributed) then tells us that our posterior mean is

$$

\begin{equation*}

\hat{\boldsymbol{\mu}}=\phi \overline{\boldsymbol{z}}+(1-\phi) \boldsymbol{\mu}_{0} \tag{2.47}

\end{equation*}

$$

i.e.,    it's a weighted average of sample average excess returns of the assets and the prior mean. How much weight $\phi$ we would optimally put on the information coming from the observed data,    $\overline{\boldsymbol{z}}$ vs. the weight $1-\phi$ on the prior mean depends on: (i) how informative the data is (higher $\phi$ if the sample is larger and returns are less volatile); (ii) the precision of our prior beliefs that $\boldsymbol{\mu}$ is in the vicinity of $\boldsymbol{\mu}_{0}$ (lower $\phi$ if our prior beliefs are more precise).

But how do we come up with $\boldsymbol{\mu}_{0}$ ? We could put in a number that seems reasonable. But is there perhaps a better approach,    one in which we could still let data influence our view?

We can exploit that we have multiple risky assets. It is not only implausible that expected excess returns on any individual asset class are extremely large,    it is also

implausible that they differ from each other by huge amounts. So if it happens to be the case that the sample averages of returns of asset classes differ a lot,    it's likely at least partly due to estimation error. To express this view that expected excess returns can't be too different in a prior belief we could say that the $N$ elements of $\boldsymbol{\mu}$ are drawn from a distribution that is centered around the same mean $\mu_{0}$ for all $N$ assets,    with some variance around this mean. In other words,    we can write the prior mean vector as $\boldsymbol{\mu}_{0}=\boldsymbol{\iota} \mu_{0}$.

Our posterior mean now becomes

$$

\begin{equation*}

\hat{\boldsymbol{\mu}}=\phi \overline{\boldsymbol{z}}+(1-\phi) \boldsymbol{\iota} \mu_{0} \tag{2.48}

\end{equation*}

$$

The posterior mean of the asset returns is now pulled towards the common prior mean $\mu_{0}$. We call this shrinking towards $\mu_{0}$ and $\hat{\boldsymbol{\mu}}$ is a shrinkage estimator.

Now to the final step: What would be a good way to find a plausible value for this common mean? Rather than specifying $\mu_{0}$ purely based on a priori reasoning,    as a truly Bayesian approach demands,    we will use an approach that backs it out from observable data. This approach is known as an empirical Bayes approach.

Given that all assets share the same prior mean,    and realizations of returns are basically all random deviations from this prior mean (with two components,    first,    the deviation of individual $\mu_{i}$ from $\mu_{0}$ and then deviations of realized excess returns from the individual asset specific mean $\mu_{i}$ ),    a natural approach is to simply average,    across assets,    the time series averages of returns,    i.e.,    use

$$

\begin{equation*}

\overline{\bar{z}}=\frac{1}{N} \iota^{\prime} \overline{\boldsymbol{z}} \tag{2.49}

\end{equation*}

$$

as an estimator of $\mu_{0}$. And then we plug it into the posterior mean equation in place of $\mu_{0}$ :

$$

\begin{equation*}

\hat{\boldsymbol{\mu}}=\phi \overline{\boldsymbol{z}}+(1-\phi) \boldsymbol{\iota} \overline{\bar{z}} \tag{2.50}

\end{equation*}

$$

Now the posterior mean is pulling the estimates away from the individual-asset timeseries averages in $\overline{\boldsymbol{z}}$ toward the the cross-asset average of these time-series averages,    $\overline{\bar{z}}$.

Now let's refine this a little. For many assets,    it might not be all that plausible that the true elements of $\boldsymbol{\mu}$ are drawn from distributions with a common mean $\mu_{0}$ because the assets differ substantially in their levels of risk. For example,    think of a portfolio of long-term U.S. Treasury bonds and a broad stock market portfolio. It does not seem plausible,    a priori,    that the lower-risk Treasury bond portfolio would earn the same expected return as a broad stock portfolio. For this reason,    it may be better to work with risk-adjusted measures of expected returns,    such as the Sharpe Ratio

For the kind of application we have in mind in this course,    where we are trying to form a portfolio that invests in a number of broad asset classes,    a reasonable prior view,    before seeing data on this,    might be that each of these asset classes have a tendency to deliver similar Sharpe ratios,    i.e.,    that the true ratios

$$

\begin{equation*}

s_{i}=\frac{\mu_{i}}{\sigma_{i}} \tag{2.51}

\end{equation*}

$$

can't stray too far from each other. In other words,    they are drawn from a distribution that is centered around the same mean $s_{0}$ for all $N$ assets,    with some random variation around $s_{0}$ for each asset. Following this view,    we then shrink estimated asset class Sharpe ratios $\bar{z}_{i} / \hat{\sigma}_{i}$ toward their common mean rather than shrinking the mean returns. If we have a value for this $s_{0}$,    we can then get posterior Sharpe Ratios for the individual assets as

$$

\begin{equation*}

\hat{s}*{i}=\phi \frac{\bar{z}*{i}}{\hat{\sigma}*{i}}+(1-\phi) \boldsymbol{\iota} s*{0} \tag{2.52}

\end{equation*}

$$

And as we discussed above for shrinking means,    we can use an empirical Bayes approach by replacing $s_{0}$ with the cross-sectional mean of the assets' estimated Sharpe ratios,    $\overline{\bar{s}}$ :

$$

\begin{equation*}

\hat{s}*{i}=\phi \frac{\bar{z}*{i}}{\hat{\sigma}_{i}}+(1-\phi) \iota \overline{\bar{s}} \tag{2.53}

\end{equation*}

$$

Based on this posterior Sharpe ratio,    we can then calculate the implied posterior mean as

$$

\begin{equation*}

\hat{\mu}*{i}=\hat{s}*{i} \hat{\sigma}_{i} \tag{2.54}

\end{equation*}

$$

which we can plug into the optimal [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] formula.

So far so good,    but how can all this be useful if we don't know $\phi$ ? We could be pick some value for $\phi$ and hope that it is somewhat plausible. We would want shrinkage to be weak enough to allow Sharpe ratios to vary across asset classes in ranges that seem plausible,    but strong enough to make it very unlikely that we get $\hat{s}_{i}$ that take extreme values like,    say,    $\hat{s}_{i}>5$. We will get to this soon.

But before we get there,    let's first look at covariance matrix estimation. We can employ similar shrinkage ideas in covariance matrix estimation. If we are trying to find an optimal portfolio with many assets,    it is crucial to bring in prior information to discipline the covariance matrix. With $N$ assets,    the covariance matrix has $N \times N$ elements. The covariance matrix is symmetric,    where each covariance shows up twice above and below the diagonal,    but this still leaves $N(N+1) / 2$ parameters to estimate. For example,    with just 10 assets,    we already have $10 \times(10+1) / 2=55$ parameters to estimate. The more parameters there are in the covariance matrix,    the more likely it is that estimation error generates problems.

The fact that we have to invert the covariance matrix in the optimal portfolio formula can hugely magnify estimation errors. We can get an idea of where the problem comes from by looking first at the case of only one asset. Here $\widehat{\boldsymbol{\Sigma}}$ is just the estimated variance of a single asset return $\sigma^{2}$. If estimation error pushes $\hat{\sigma}^{2}$ close to zero,    the inverse,    which is here just $1 / \hat{\sigma}^{2}$,    explodes toward infinity. Non-invertibility of a covariance matrix is sort of like this. The difference to the single asset case is that with multiple assets,    the existence of any portfolio of assets (which is a linear combination of individual asset returns) with close to zero variance makes the covariance matrix blow up. The more assets there are,    the easier it is to find such portfolios where,    by chance,    a combination of estimation errors results in a portfolio that seemingly has close to zero variance in the sample that we are using to estimate the covariance matrix.

If the covariance matrix is not invertible,    statistical software packages will tell us. But sometimes it may just be close to non-invertible,    even though technically it is still invertible. It's useful to know how this sort of problem then manifests in the optimal portfolio weight output of the optimal portfolio formula: A typical symptom of this problem is that the optimal portfolio weights imply some huge long and short positions,    i.e.,    some weights are huge and positive,    others are huge and negative.

Intuitively,    when estimation errors in covariances make it look like as if some combination of assets delivers close to zero risk,    but earns a substantial spread in excess returns,    this looks like a great investment opportunity to the portfolio optimization formula. For example,    suppose two assets happen to have different expected return estimates and similar variance estimates,    and their estimated correlation is far too high (relative to their true correlation) because returns of these two assets in our sample just happened to be highly positively correlated by chance even though they are not truly highly correlated. This looks like an opportunity to go long in the high expected return asset and short in the low expected return asset. This position earns the spread in expected returns with very little risk. The optimal portfolio formula will tell us to take a huge long-short bet. But of course taking this position would very likely lead to a big disappointment out-of-sample because the assets aren't truly highly correlated. Estimation error just made it look like they were.

A large number of assets magnifies this problem because the more assets there are,    the more likely it is that,    just by chance,    some linear combination of assets seemingly has zero risk.

If high-frequency data is available for covariance matrix estimation,    this can help avoid these problems because it reduces the magnitude of estimation errors in covariances,    along the lines we discussed earlier. But shrinkage can be useful,    too.

Heuristically,    we can again give this a Bayesian interpretation where we combine

information in the sample covariance matrix obtained from returns data with prior knowledge about the likely values of variances and covariances.

We can decompose the covariance matrix into standard deviations and correlations:

$$

\boldsymbol{\Sigma}=\left(\begin{array}{cccc}

\sigma_{1} & 0 & \ldots & 0  \tag{2.55}\\

0 & \sigma_{2} & \ldots & 0 \\

& \ldots & & \\

0 & 0 & \ldots & \sigma_{N}

\end{array}\right)\left(\begin{array}{cccc}

1 & \rho_{12} & \ldots & \rho_{1 N} \\

\rho_{21} & 1 & \ldots & \rho_{2 N} \\

& \ldots & & \\

\rho_{N 1} & \rho_{N 2} & \ldots & 1

\end{array}\right)\left(\begin{array}{cccc}

\sigma_{1} & 0 & \ldots & 0 \\

0 & \sigma_{2} & \ldots & 0 \\

& \ldots & & \\

0 & 0 & \ldots & \sigma_{N}

\end{array}\right)

$$

where $\rho_{i j}$ denotes the correlation between returns of asset $i$ and $j$.

Let's denote the diagonal matrix with standard deviations on the diagonal with $\boldsymbol{S}$ and the correlation matrix with $\boldsymbol{C}$. Then we can write $\boldsymbol{\Sigma}$ as

$$

\begin{equation*}

\Sigma=\boldsymbol{S C S} \tag{2.56}

\end{equation*}

$$

Imprecisely estimated correlations are often the source of trouble in portfolio optimization. To see why,    recall the two-asset example we just discussed earlier where two assets have different estimated expected returns and the estimate of their correlation is close to one,    even though their true correlation is far from one. If the estimated high correlation is indeed just a statistical fluke,    then the portfolio takes an extreme position in a strategy that in reality does not deliver a great ratio of reward to risk. It just looked like it might based on erroneous estimates. This can mess up the performance of the whole portfolio. And if we have many assets,    we need to estimate many correlations (e.g.,    if we have 10 assets,    we must estimate $(10 \times 10-10) / 2=45$ correlations). Among so many estimates,    it's likely that a few will be way off from the true correlation due to estimation error. Hence,    it's generally a well-known problem that with a large number of assets,    just plugging the sample covariance matrix (and hence,    implicitly,    all these sample estimates of correlations) into a portfolio optimizer yields poor results.

For this reason,    we may want to express that we know that correlations are probably all positive (risky assets generally tend to move together),    but teasing out from the data which ones are higher and which ones are lower may be difficult. We express this prior belief by shrinking our correlation estimates towards an equicorrelation matrix

$$

\boldsymbol{C}*{0}=\left(\begin{array}{cccc}*

*1 & \rho*{0} & \ldots & \rho_{0}  \tag{2.57}\\

\rho_{0} & 1 & \ldots & \rho_{0} \\

\rho_{0} & \rho_{0} & \ldots & 1

\end{array}\right)

$$

where all the correlations take the same value $\rho_{0}$. Using $\overline{\boldsymbol{C}}$ to denote the matrix of correlations estimated from the data,    our posterior estimate of the correlation matrix becomes

$$

\begin{equation*}

\widehat{\boldsymbol{C}}=\phi \overline{\boldsymbol{C}}+(1-\phi) \boldsymbol{C}_{0} \tag{2.58}

\end{equation*}

$$

Then our estimate of the covariance matrix becomes

$$

\begin{equation*}

\widehat{\boldsymbol{\Sigma}}=\widehat{\boldsymbol{S}} \widehat{\boldsymbol{C}} \widehat{\boldsymbol{S}} \tag{2.59}

\end{equation*}

$$

where $\widehat{\boldsymbol{S}}$ is the estimated version of $\boldsymbol{S}$,    i.e.,    with estimated standard deviations on its diagonal.

How can we come up with a number for $\rho_{0}$ ? In the same empirical Bayes spirit as above when we looked at expected returns and Sharpe Ratios,    we can plug in an estimate of the average pairwise correlation of all assets. This means that we use the observed returns data,    we form all possible pairs of asset return series $i$ and $i$ where $i \neq j$,    and we estimate their correlation $\hat{\rho}_{i j}$. Then we construct their average,  

$$

\begin{equation*}

\bar{\rho}=\frac{1}{N(N-1)} \sum_{i=1}^{N} \sum_{j \neq i} \hat{\rho}_{i j} \tag{2.60}

\end{equation*}

$$

We then replace $\rho_{0}$ in the prior correlation matrix $\boldsymbol{C}_{0}$ with this estimate $\bar{\rho}$.

Now we have to tackle the remaining problem of how to estimate $\phi$. We can use an approach known as cross-validation. Cross-validation is a powerful idea that appears in lots of places in applied statistics and data science,    including many machine learning applications. The idea is that we can use historical data on returns to evaluate which value of $\phi$ would have led us to construct the best portfolios in the past,    where with "best" we mean that this value leads to the best out-of-sample portfolio performance. In this approach,    we basically imagine that we had constructed Sharpe Ratio estimates as in (2.53),    and portfolios based on these estimates,    in the past and we look for the value of $\phi$ that would have given us the best out-of-sample performance in the past.

To implement this cross-validation approach,    I use returns data for our nine asset classes from the beginning of 1980 to the end of 2022. I then pick an estimation window size,    e.g.,    240 months,    or 20 years. Then I implement the following steps:

Estimate $\hat{\boldsymbol{\mu}}$ as in (2.54) and $\widehat{\boldsymbol{\Sigma}}$ as in (2.59) using data from beginning of 1980 to end of 1999 and for different values from $\phi=0$ (total shrinkage) to $\phi=1$ (no shrinkage).

For each of these $\hat{\boldsymbol{\mu}}$ and $\widehat{\boldsymbol{\Sigma}}$ combinations for a value of $\phi$,    I calculate the optimal risky asset portfolio weights as in (2.18).

I then apply these weights to returns on the nine asset classes in January 2000 to calculate the out-of-sample portfolio return in January 2000,    i.e.,    in the month following the end of the estimation window. Again I do this for every value of $\phi$.

Then I move the estimation window in step 1 forward by one month to beginning of February 1980 to end of January 2000. Then I repeat steps 1 to 3 and I get an out-of-sample portfolio return in February 2020 for each value of $\phi$. I keep repeating until I have reached the portfolio return in December 2022.

Now I have several time-series of portfolio excess returns,    one for each $\phi$. I calculate the Sharpe ratio from these portfolio excess returns.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-063.jpg?height=887&width=1186&top_left_y=695&top_left_x=491)

Figure 2.8: Out-of-sample Sharpe Ratios for different values of the shrinkage parameter $\phi$ and different lengths of the backward-looking estimation window

I then redo the whole procedure with a different estimation window sizes of 10 years and 5 years in addition to the 20-year window. Figure 2.8 shows the results. For each of the estimation window lengths,    it shows how the Sharpe ratio of the portfolio changes with $\phi$. There are a few things to note.

First,    when we use 20 years of data,    shrinkage doesn't have much of an effect. The Sharpe ratio is more or less insensitive to the value of $\phi$. Shrinkage is apparently not really needed to get better estimates,    but imposing lots of shrinkage also doesn't hurt. (Just to be clear,    this is obviously not a general conclusion that is always valid everywhere. It could well be the case that with a different set of asset classes,    or with estimates from different time periods,    there is substantial sensitivity of the out-of-sample Sharpe ratio to $\phi$ with 20-year estimation windows).

Second,    if we wish to use shorter estimation windows (perhaps because we think that expected returns and covariances may have changed too much over long periods of time),    shrinkage is important. With 5 -year estimation windows and no shrinkage at all (i.e.,    $\phi=1$ at the right-hand side of the plot) the Sharpe ratio is around zero. In other words,    the portfolio optimization has become useless. In contrast,    with $\phi=0$,    and hence extreme shrinkage,    the 5-year estimation window approach produces Sharpe ratios that are close to the highest possible Sharpe ratios for the 10-year and 20-year estimation windows.

As it turns out,    this extreme shrinkage approach with $\phi=0$ actually leads to an [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] strategy that has become quite popular in the past decade or two.

### 2.9 Extreme forms of shrinkage: Risk parity and $1 / \mathrm{N}$

Let's examine in more detail the extreme shrinkage portfolio that results when we set $\phi=0$ in estimating $\hat{\boldsymbol{\mu}}$ as in (2.54),    i.e.,    with shrinkage towards a equal Sharpe ratios,    and $\widehat{\boldsymbol{\Sigma}}$ as in (2.59).

In this case,    the covariance matrix estimate uses the empirically estimated standard deviations,    while the correlations are all shrunk completely to the equicorrelation matrix $C_{0}$ :

$$

\begin{equation*}

\widehat{\Sigma}=\widehat{\boldsymbol{S}} C_{0} \widehat{\boldsymbol{S}} \tag{2.61}

\end{equation*}

$$

Before we plug this into the optimal portfolio formula,    it's useful to note that $\widehat{\boldsymbol{\Sigma}}^{-1}=$ $\widehat{\boldsymbol{S}}^{-1} \boldsymbol{C}_{0}^{-1} \widehat{\boldsymbol{S}}^{-1}$.

With $\phi=0$,    the Sharpe ratios of all asset classes are completely shrunk to their common mean $\overline{\bar{s}}$ and so the expected excess return estimates implied by these identical Sharpe ratios are

$$

\begin{equation*}

\hat{\boldsymbol{\mu}}=\widehat{\boldsymbol{S}} \boldsymbol{\iota} \bar{s} \tag{2.62}

\end{equation*}

$$

The optimal portfolio weight formula (2.18) tells us that portfolio weights are proportional to $\widehat{\boldsymbol{\Sigma}}^{-1} \hat{\boldsymbol{\mu}}$. In this case here,  

$$

\begin{align*}

\widehat{\boldsymbol{\Sigma}}^{-1} \hat{\boldsymbol{\mu}} & =\widehat{\boldsymbol{S}}^{-1} \boldsymbol{C}*{0}^{-1} \widehat{\boldsymbol{S}}^{-1} \widehat{\boldsymbol{S}} \boldsymbol{\iota} \bar{s} \\*

*& =\widehat{\boldsymbol{S}}^{-1} \boldsymbol{C}*{0}^{-1} \iota \bar{s} \\

& \propto \widehat{\boldsymbol{S}}^{-1} \boldsymbol{\iota} \tag{2.63}

\end{align*}

$$

(The last equality holds because the inverse of the equicorrelation matrix has the property,    just like the equicorrelation matrix does,    that the sum of the elements in each row or column is the same. This means that when we multiply $\boldsymbol{C}_{0}^{-1}$ with $\boldsymbol{\iota}$ we get,    as a result,    a vector with equal elements that is proportional to $\boldsymbol{\iota}$.) So,    optimal portfolio weights will be proportional to $\widehat{\boldsymbol{S}}^{-1} \boldsymbol{\iota}$. And since $\boldsymbol{S}^{-1}$ is diagonal,    we get

$$

\hat{\boldsymbol{\omega}}^{*} \propto\left(\begin{array}{c}

\frac{1}{\hat{\sigma}*{1}}  \tag{2.64}\\*

*\frac{1}{\hat{\sigma}*{2}} \\

\ldots \\

\frac{1}{\hat{\sigma}_{N}}

\end{array}\right)

$$

Let's examine the weights in (2.64). They only depend on individual asset class risk as measured by standard deviations. Estimates of mean returns or correlations have completely disappeared from the optimal portfolio weight formula. This is a consequence of the extreme shrinkage we have imposed. These are the weights underlying the portfolios at the very left side of Figure 2.8 for $\phi=0$. Basically,    this strategy expresses extreme distrust in empirical estimates of correlations and mean returns,    but considers standard deviation estimates as reliable.

Among investment practitioners,    the approach to portfolio allocation embodied in the weights in (2.64) is known as risk parity. It was pioneered by the hedge fund firm Bridgewater Associates in their All Weather Fund in the mid-1990s. The high Sharpe ratios for $\phi=0$ in Figure 2.8 tells us that this approach has done well in the past few decades,    which may explain why it became popular.

The motivation investment practitioners give for this approach is typically a bit different from the way we arrived at it here. Risk parity is often presented as the idea that each asset class should be held with a weight that has each asset class make the same risk contribution to the portfolio,    or,    in other words,    it gets the same "risk budget." Recall our decomposition of the portfolio variance in (2.22):

$$

\operatorname{var}\left(R_{p}\right)=\omega_{1} \underbrace{\operatorname{cov}\left(R_{1},  R_{p}\right)}*{\begin{array}{c}*

*\text { Risk }  \tag{2.65}\\*

*\text { contribution } \\*

*\text { of asset } 1*

*\end{array}}+\omega*{2} \operatorname{cov}\left(R_{2},  R_{p}\right)+\ldots+\omega_{N} \operatorname{cov}\left(R_{N},  R_{p}\right)

$$

The risk contributions of each asset class per unit of weight are represented by the covariances $\operatorname{cov}\left(R_{i},         R_{p}\right)$,    and their total risk contribution to the portfolio by this covariance times the portfolio weight. With risk-parity weights proportional to $1 / \sigma_{i}$ and the assumption that the correlation matrix of the asset classes is an equicorrelation matrix,    one can show that $\omega_{i} \operatorname{cov}\left(R_{i},         R_{p}\right)$ is then the same for each asset class-i.e.,    each asset

class accounts for the same share of total portfolio risk. ${ }^{2}$ This is what people mean when they say that a risk parity strategy then gives each asset class an equal risk budget for its contribution to portfolio risk (and keep in mind that this statement is true only if the equicorrelation assumption holds).

Now,    conceptually,    it's not clear why equal risk budgets for each asset class would be desirable. In contrast,    our shrinkage approach gives a clear motivation: if we strongly distrust mean return and correlation estimates due to estimation error,    then meanvariance optimization implies a risk parity strategy.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-066.jpg?height=926&width=1201&top_left_y=762&top_left_x=424)

Figure 2.9: Weights of risk parity portfolio (10 years of data to estimate standard deviations)

Figure 2.9 shows how risk parity portfolio weights looked like if we implemented this approach in the past few decades,    using 10 years of backward looking data to estimate the

[^7]asset class return standard deviations. Notice the different scale of the y-axis compared with Figure 2.7.

Also,    note that I am plotting the risky portfolio weights in (2.18) that are scaled to sum up to one. We will leave aside for now the question of how to allocate between short-term risk-free assets (proxied for by T-bills) and the risky asset portfolio.

In several ways,    these portfolio weights have desirable attributes. There are no huge outliers asking for huge amounts of leverage (portfolio weights in excess of 1.0) or short positions (portfolio weights $<0$ ) that portfolio managers are often reluctant to take. As we saw in Figure 2.7,    this can be very different for optimal weights without shrinkage when a relatively short estimation window of 10 years is used to estimate the inputs for the optimal portfolio weight formula (that make the calculation of the optimal weights far more cumbersome). One way to fix this problem (for a manager who is reluctant to take on leverage and short positions) is to impose additional constraints on the meanvariance optimization problem. But the risk parity strategy delivers moderate weights without having to impose such constraints.

Figure 2.9 also highlights one property that has generated criticism of the risk parity approach: its heavy loading on bonds. As the figure shows,    the three bond asset classes,    U.S. Treasury bonds,    international bonds,    and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] account for a large share of the total portfolio. The concern is that the strategy has benefitted from the secular decline in interest rates (which lead to high returns for holders of long-term bonds) that took place during the past decades. The performance of a strategy with a high bond exposure in the future may look much less appealing.

Another problem that is useful to keep in mind concerns the initial menu of asset classes. The mean-variance optimization approach that takes into account correlations is not as sensitive to the selection of the asset class menu than the risky parity approach. For example,    if we add another asset class to the menu that is very similar in terms of mean return and highly correlated with an asset class that we already have in the menu,    the mean-variance optimal portfolio will tend to reduce the share of the one we already have in the menu and give some of this share to the new asset class,    leaving other asset classes largely unaffected.

In contrast,    the risk parity approach reduces the weight on all other asset classes equally when we bring in a new asset class,    even if the new asset class is very similar to one we already have in the menu,    and not to the others.

The bottom line from this is that the equicorrelation prior should be somewhat plausible for the selected menu of asset classes for the risky parity approach to make sense. Having two asset classes in there that are clearly much more highly correlated than others could lead to excessive weight for these two asset classes.

Now consider an even more extreme form of distrust in the data. Suppose we don't believe that historical data on standard deviations are useful for forecasting future volatility. We therefore feel that we can't distinguish between asset risk levels and we impose extreme shrinkage not only on mean returns and correlations,    but also standard deviations: we assume they are the same $\sigma_{1}=\sigma_{2}=\ldots=\sigma_{N}$. Then the portfolio weights for all asset classes are exactly equal and the risky asset portfolio weights are

$$

\hat{\boldsymbol{\omega}}^{*}=\left(\begin{array}{c}

\frac{1}{N}  \tag{2.66}\\

\frac{1}{N} \\

\ldots \\

\frac{1}{N}

\end{array}\right)

$$

where $N$ is the number of asset classes. This portfolio formation strategy is called,    sensibly,    a $1 / N$ strategy. It uses no inputs about expected returns and risks whatsoever.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-068.jpg?height=955&width=1201&top_left_y=1035&top_left_x=424)

Figure 2.10: Out-of-sample Sharpe Ratios of different portfolio strategies (10 years of data to estimate return moments)

This may seem like an extremely unsophisticated [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] strategy. And in some sense it is. But look at Figure 2.10! The Figure shows the out-of-sample Sharpe ratios of four strategies: (i) no shrinkage at all - this is the portfolio of the 10-year line

for $\phi=1$ in Figure 2.8; (ii) optimal shrinkage of $\phi=0.05$ based on the maximum of the line for 10-year estimation windows in Figure 2.8; (iii) risk parity; (iv) $1 / N$.

Surprisingly,    $1 / N$ does quite well! Not as good as optimal shrinkage and risk parity,    but still much better than in the no-shrinkage case. There is actually a fairly large body of research at this point showing that the $1 / N$ strategy of forming a diversified portfolio does quite well in a number of settings.

As for the risk parity approach,    the selection of the menu of assets is very important. By adding lots of very similar,    highly correlated asset classes,    a $1 / N$ portfolio would become poorly diversified and its Sharpe ratio would suffer. Part of the success of $1 / N$ in our analysis here comes from the fact that we started with a good selection of asset classes that span a lot of different types of risks.

But one conclusion that we can tentatively draw from the success of $1 / N$ in this exercise is that our inputs to the optimal portfolio weight formula are perhaps not good enough yet. For example,    just plugging in historical estimates of mean excess returns from the past 10 years may be a poor way of forecasting future excess returns.

Much of the rest of the course will be devoted to getting a better understanding of how to forecast risk and return.