---
title: DetailedLectureNotes_Week2_1-10
aliases: [LECTURE 2]
linter-yaml-title-alias: LECTURE 2
---

# DetailedLectureNotes_Week2_1-10

We now extend our optimal portfolio choice framework to allow for multiple risky assets.

This gets us close to the type of models that are used by asset managers of large portfolios to decide how much to allocate to different asset classes.

We still stick to the IID returns assumption for now.

In your intro investments course,  you saw the graphical representation of the solution for the optimal portfolio. Recall the hyperbolic shape of the mean-standard deviation frontier,  the tangency portfolio,  and the capital market line that depicts all possible combinations of the risk-free asset with the tangency portfolio. Here we are going to use matrix algebra to get explicit formulas for the tangency portfolio and its risk-return properties.

I use bold lowercase letters for vectors and bold uppercase letters for matrices. I use
 to denote a column vector with all elements equal to one and I for the identity matrix (which has ones on its diagonals and zeros everywhere else). Letters or symbols that are not in boldface are scalars.

## 2.1 RISK AND RETURN AT THE PORTFOLIO LEVEL

Consider N risky assets with an N ⇥ 1 vector of returns r and expected returns E[r].

We will often look at excess returns

$$z=r-\iota R_{f},      \qquad\mu=\mathbb{E}[z]$$

Very important for our portfolio choice analysis is the N⇥N covariance matrix of returns

$$\Sigma=\mathbb{E}[(z-\mu)(z-\mu)^{\prime}]$$
0] (2.2)
$$(2.1)$$
$$(2.2)$$

For analyzing portfolio risk and return,  we need to know a few rules on how the moments of portfolio returns,  e.g.,  mean and variance,  depend on moments of individual asset returns. Suppose we have a portfolio with N assets and the weight of every asset
(in terms of the proportion of the portfolio's market value accounted for by each asset) is collected in the N ⇥ 1 portfolio weight vector! = (!1,  !2*,  …,  *!N)0. Then the portfolio return is Rp =!0r,  (2.3)
and the expected portfolio return

$$R_{p}=\omega^{\prime}r,      $$
$$(2.3)$$

$$\mathbb{E}[R_{p}]=\omega^{\prime}\mathbb{E}[\mathbf{r}].$$
$$(2.4)$$
$$\operatorname{var}(R_{p})=\omega^{\prime}\Sigma\omega.$$
E[Rp] =!0E[r]. (2.4)
We can calculate the variance from the N ⇥ N covariance matrix of individual asset returns as var(Rp) =!0⌃!. (2.5)
This last formula shows that all N ⇥ N elements of the covariance matrix play a role in determining the portfolio return variance. This is important. The portfolio variance depends not only on how volatile individual asset returns are,  but also on how strongly they covary,  i.e.,  whether they tend to move together or not. Here is how this looks like in the N = 2 case,  where ⇢ denotes the correlation of the two asset returns and ⇢12 their covariance:

$$\mathrm{var}(R_{p})=\begin{pmatrix}\omega_{1}\\ \omega_{2}\end{pmatrix}^{\prime}\begin{pmatrix}\sigma_{1}^{2}&\rho\sigma_{1}\sigma_{2}\\ \rho\sigma_{1}\sigma_{2}&\sigma_{2}^{2}\end{pmatrix}\begin{pmatrix}\omega_{1}\\ \omega_{2}\end{pmatrix}\tag{2.6}$$ $$=\omega_{1}^{2}\sigma_{1}^{2}+2\omega_{1}\omega_{2}\rho\sigma_{1}\sigma_{2}+\omega_{2}^{2}\sigma_{2}^{2}.\tag{2.7}$$

$$(2.5)$$

So if the portfolio has positive weight on both assets,  !1 > 0 and!2 > 0,  then,  due to the middle term in this expression,  the higher the correlation of the two asset returns,  the higher the portfolio return variance.

Sometimes we are interested in the covariances of returns of the individual assets that are in the portfolio with the return of the overall portfolio. We can get this vector of covariances by post-multiplying the covariance matrix with the portfolio weight vector,

$$\left(\begin{array}{c}{{\operatorname{cov}(R_{1},      R_{p})}}\\ {{\operatorname{cov}(R_{2},      R_{p})}}\\ {{\ldots}}\\ {{\operatorname{cov}(R_{N},      R_{N})}}\end{array}\right)=\Sigma\boldsymbol{\omega}.$$
$$(2.8)$$
.

## 2.2 OPTIMAL PORTFOLIO CHOICE WITH MULTIPLE RISKY ASSETS

Let's now turn to finding the optimal portfolio weight when we have multiple risky assets. As in the last lecture,  we assume the investor has CRRA preferences and we'll use a first-order approximation of marginal utility to simplify the problem. The following analysis is pretty much analogous to our analysis in the single risky asset case in the last lecture,  but with some vectors and matrices replacing some scalars to account for the fact that we have multiple risky assets.

If the investor starts with wealth W0 at the beginning of a period and invests proportions! of this initial wealth into the N risky assets and the rest in the risk-free asset,  then the total investment in risky assets accounts for a proportion 0! = PNi!i of initial wealth and the rest,  10! is allocated to the risk-free asset. Hence the return on the investor's wealth portfolio is

$$(2.9)$$
$$R_{w}=(1-\iota^{\prime}\omega)R_{f}+r^{\prime}\omega,      $$
$$R_{w}=R_{f}+z^{\prime}\omega.$$
$$(2.10)$$
$$+\,      R_{w}).$$
or,  equivalently,
Rw = Rf + z0!. (2.10)
The investor's wealth at the end of the period is W = W0(1 + Rw).

The investors' objective is the same as in the single risky asset case in the previous
lecture
$$\operatorname*{max}_{\omega}\mathbb{E}[U(W)]\quad\mathrm{s.t.}W=W_{0}(1+R_{w}),      $$
but Rw now depends on a vector of portfolio weights!,  not just a single risky asset
portfolio weight,  that the investor is trying to optimize. The first-order condition of
this problem is analogous to the single risky asset case,  but now we have N first order conditions instead of just one.
$$(2.11)$$
$$\mathbb{E}\left[z{\frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])}}\right]=0.$$
$$(2.12)$$
In this vector of first-order conditions,  there is one first-order condition for each element of z.

Approximating U0(W)
U0(E[W]) linearly,  we get,  analogous to last lecture,

$${\frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])}}\approx1-\gamma(\mathbf{r}-\mathbb{E}[\mathbf{r}])^{\prime}\mathbf{\omega}$$
$$(2.13)$$

just now with a vector of returns and,  correspondingly,  a vector of portfolio weights!. Substituting this approximation into the first-order condition (2.12),  we get

$$\mathbb{E}[\mathbf{z}\left\{1-\gamma(\mathbf{r}-\mathbb{E}[\mathbf{r}])^{\prime}\mathbf{\omega}\right\}]=0.$$ With $E[\mathbf{z}]=\mathbf{\mu}$ and $\mathbb{E}[\mathbf{z}(\mathbf{r}-\mathbb{E}[\mathbf{r}])^{\prime}]=\mathbf{\Sigma}$,  we get
$$(2.14)$$
$$\mu-\gamma\Sigma\omega=0$$
$$(2.15)$$

$$(2.16)$$
µ ⌃! = 0 (2.15)
where the covariance matrix ⌃ has taken the place of the variance of risky asset return in the single risky asset case. We can solve this expression for the optimal risky asset share

$$\omega=\frac{1}{\gamma}\Sigma^{-1}\mu.$$

So instead of division by the variance of the asset return in the single risky asset case we now have the inverse of the covariance matrix. Taking the inverse of a matrix is sort of like dividing. The proportion of wealth invested in the risk-free asset is

$$\omega_{f}=1-\iota^{\prime}\omega=1-\frac{1}{\gamma}\iota^{\prime}\Sigma^{-1}\mu.$$
$$(2.17)$$

Let's look at some properties of this solution. Note that we can can further rescale the weights! so that they sum up to unity. This yields the weights within the risky asset portfolio:

$$\omega^{*}=\frac{1}{\nu^{\prime}\omega}\omega=\frac{1}{\nu^{\prime}\Sigma^{-1}\mu}\Sigma^{-1}\mu.$$
$$(2.18)$$

This tells us something important and very useful: The solution for!⇤ does not depend on the level of risk aversion! All investors,  irrespective of their degree of risk aversion should therefore hold a risky asset portfolio with the same composition (as long as they have the same beliefs about ⌃ and µ). Risk preferences should only matter for how much of their wealth they allocate to the risky asset portfolio overall and to the risk-free asset. By scaling up or down the risky asset portion of their wealth,  investors can adjust the riskiness of their wealth portfolio. This is sucient for getting a portfolio consistent with their risk preferences.

Thus,  the decision on how to structure a portfolio can be separated into two independent steps. First,  how to split the risky asset portfolio among the different risky assets; second,  how to allocate between this risky asset portfolio and the risk-free asset. This result is called the two-fund separation theorem.

The risky asset portfolio with weights!⇤ is the tangency portfolio that you already encountered in your introductory investments course. Let's denote with R⇤ and Z⇤ the returns and excess returns of this tangency portfolio,  respectively.

To get some intuition for what the optimal portfolio solution does and how it depends on expected returns and correlations,  suppose we have N = 2 and

$$\mu=\begin{pmatrix}\mu_{1}\\ \mu_{2}\end{pmatrix},      \qquad\Sigma=\sigma^{2}\begin{pmatrix}1&\rho\\ \rho&1\end{pmatrix}$$
$$\mathrm{Then}$$
$$\Sigma^{-1}=\frac{1}{\sigma^{2}(1-\rho^{2})}\begin{pmatrix}1&-\rho\\ -\rho&1\end{pmatrix}$$
Plugging into $\left(2.18\right)$ we get.
$$(2.19)$$
$$(2.20)$$
$$\mathbf{\omega}^{*}=a\begin{pmatrix}\mu_{1}-\rho\mu_{2}\\ \mu_{2}-\rho\mu_{1}\end{pmatrix}$$
$$(2.21)$$
$$\operatorname{act{tors.}}$$

for some constant a that collects all the scalar factors.

Now let's think about some special cases. If the two assets' returns are uncorrelated,
⇢ = 0,  then optimal portfolio weights are proportional to their expected returns. Suppose µ1 > µ2. Then the investor puts a higher share into asset 1 than into asset 2. This should be intuitive. It makes sense to invest more in the higher-earning asset when the two assets are otherwise identical. But why not put everything into asset 1 (or even short asset 2 and invest more than 100% of the risky asset portfolio into asset 1)? Diversification benefits! Having some of asset 2 in the portfolio,  but not too much,  can still be useful because it lowers the risk of the portfolio.

Now consider a case where ⇢ is very close to 1 and again µ1 > µ2. In this case,  the assets are,  in terms of risk,  almost perfect substitutes. As a consequence,  a long-short position,  going long in asset 1,  short in asset 2,  is optimal: it earns a positive expected returns µ1 µ2 > 0,  but it has almost no risk because the returns of the two assets are almost perfectly correlated.

## 2.3 SYSTEMATIC RISK

How does a mean-variance optimizing investor think about a new asset that could be added to the existing portfolio? When is it attractive in terms of risk and return? When does it make sense to alter the portfolio to include more or less of this asset? As we will see now,  the mean-variance optimal portfolio strikes a perfect balance between the expected return that an asset contributes to the portfolio and the risk that it contributes.

This contribution to portfolio risk is what we call systematic risk.

We can see the risk contribution of assets to the overall portfolio by examining the portfolio variance in equation (2.5). Note from (2.8) that the expression ⌃! in

var(Rp) =!0⌃! is a vector of covariances,  so the pre-multiplication by!0 forms a weighted sum of these covariances,  i.e.,

$$\operatorname{var}(R_{p})=\omega_{1}\underbrace{\operatorname{cov}(R_{1},      R_{p})}_{\begin{subarray}{c}\operatorname{Risk}\\ \operatorname{condition}\\ \operatorname{of~asset~1}\end{subarray}}+\omega_{2}\operatorname{cov}(R_{2},      R_{p})+\ldots+\omega_{N}\operatorname{cov}(R_{N},      R_{p})$$
$$(2.22)$$

We have now decomposed the overall portfolio variance in the pieces that come from each asset. How much risk each asset brings to the portfolio is determined by how much of this asset is in the portfolio,  i.e.,  its portfolio weight,  times the risk contribution measured by the covariance cov(Ri,  Rp). For the same weight,  an asset that has a higher covariance with the portfolio return adds more risk to the portfolio.

Dividing by var(Rp) on both sides,  we can express the risk contributions as shares of total portfolio risk. We get

$$1=\omega_{1}\beta_{1}+\omega_{2}\beta_{2}+\ldots+\omega_{N}\beta_{N}.$$
1 =!11 +!22 + … +!N N. (2.23)
The systematic risk of asset i is measured by

$$(2.23)$$

$$\beta_{i}={\frac{\mathrm{cov}(R_{i},      R_{p})}{\mathrm{var}(R_{p})}}.$$
$$(2.24)$$
var(Rp). (2.24)
One important take-away at this point is that systematic risk is investor specific.

How much an asset contributes in terms of risk to an existing portfolio depends on what else is in the portfolio,  which will typically differ across investors. If asset i has a high return covariance with the other assets in the portfolio,  then i will be high. If the other assets' returns don't covary much with asset i's returns,  then i will be low.

Now let's assume the investor's portfolio is mean-variance optimal,  i.e.,  it has weights
!⇤ = ⌃1µ as in (2.18),  with the modification that I dropped the scalar constant that rescales the portfolio in (2.18) to have weights that add up to 100%. Whether we scale the portfolio weights by some constant factor does not matter for any of the calculations that follow in this section,  so I just drop the scaling factor to make the expression for!⇤ less messy.

With these optimal portfolio weights,  following (2.8),  individual assets have a vector of covariances

$$\Sigma\omega^{*}=\Sigma\Sigma^{-1}\mu=\mu,      $$

and,  following (2.5),  we have the portfolio variance

$$\operatorname{var}(R^{*})=\omega^{*\prime}\Sigma\omega^{*}=\omega^{*\prime}\mu=\mu^{*},      $$
var(R⇤) =!⇤0⌃!⇤ =!⇤0µ = µ⇤,  (2.26)
$$(2.25)$$
$$(2.26)$$
$(\mathbb{C})\mathbb{S}$.

where µ⇤ = E[Z⇤] is the expected excess return of the mean-variance optimal portfolio.
Dividing the vector covariances in (2.25) by the portfolio variance in (2.26),  we then get
a vector of betas:
$$\beta^{*}=\frac{1}{\operatorname{var}(R^{*})}\Sigma\omega^{*}=\frac{1}{\mu^{*}}\mu.$$
Rearranging,  we see that expected returns of individual are tightly linked to their systematic risk with respect to the mean-variance optimal portfolio
$$(2.27)$$
$$(2.28)$$
$$\mu=\beta^{*}\mu^{*}.$$
$\frac{3}{4}$ 4.
$$\mathbb{E}[Z_{i}]=\beta_{i}^{*}\,      \mathbb{E}[Z^{*}],      $$
$\left(2.29\right)^{\frac{1}{2}}$
µ = ⇤µ⇤. (2.28)
For an asset $i$,  therefore,  .
E[Zi] = ⇤i E[Z⇤],  (2.29)
which looks exactly like the relationship predicted by the Capital Asset Pricing Model
(CAPM) that you encountered in your introductory investments course—just with one very important difference: in the CAPM,  ⇤i would be the beta with respect to the market portfolio return and E[Z⇤] would be the expected excess return on the market portfolio. Here they are just the beta with respect to an investor's optimal portfolio,  which need not be the same as the market portfolio,  and E[Z⇤] is the expected excess return on the investor's portfolio,  not the market portfolio.

The condition (2.29) tells us that when the existing portfolio is mean-variance optimal,  then expected returns of all assets must have expected excess returns exactly proportional to their betas with respect to the portfolio return R⇤. The beta of asset i tells us how much risk we would add to the portfolio if we added more of this asset to the portfolio. This is what we call *systematic* risk. This systematic risk originates from covariance,  i.e.,  the degree to which the return of asset i and the portfolio R⇤ move together in the same direction.

Furthermore,  equation (2.29) tells us that if the portfolio with return R⇤ is already optimal,  then there cannot be any asset out there that offers an expected return that is lower or higher than what equation (2.29) prescribes. Each asset's expected return must be exactly commensurate with the systematic risk ⇤i that this asset brings to the portfolio so that no asset looks attractive enough to add more of it to the portfolio,  or unattractive enough to reduce its position.

Otherwise,  if we could find such an asset i that violates condition (2.29),  we could improve our portfolio's Sharpe ratio by adding more of asset i to the portfolio (if the expected return is higher than required) or taking some of it out,  and possibly shorting it (if the expected return is lower than required). For example,  if an asset i has E[Zi] > ⇤i E[Z⇤],  it would make sense for the investor to take more of asset i into the portfolio,  because this would contribute to a relatively small amount of portfolio risk,  but a relatively big expected excess return.

$$\mathrm{agel}\,      \$$

##

We can decompose the total risk of an asset into *systematic* and *idiosyncratic* components. Note that ⇤i = cov(Ri,  R⇤)/ var(R⇤) is an ordinary least squares (OLS) regression slope coecient in a regression of Ri on R⇤. This means we can decompose Ri as follows

$$R_{i}=a_{i}+\beta_{i}^{*}R^{*}+\varepsilon_{i}$$
$$(2.30)$$
$$(2.31)$$
Ri = ai + ⇤i R⇤ + "i (2.30)
where cov(R⇤,  "i) = 0. This decomposition shows that movements in Ri are partly
due to movements perfectly aligned with R⇤ (systematic) and partly due to movements uncorrelated with R⇤ (idiosyncratic). Taking the variance of the leftand right-hand sides,
$$\operatorname{var}(R_{i})=(\beta_{i}^{*})^{2}\operatorname{var}(R^{*})+\operatorname{var}(\varepsilon_{i}),      $$
2 var(R⇤) + var("i),  (2.31)
we have now broken the total risk of asset i,  var(Ri),  into two components: Systematic risk,  (⇤i)2 var(R⇤),  and idiosyncratic risk,  var("i).

Since systematic risk determines an assets (un)attractiveness,  not the idiosyncratic risk,  Sharpe Ratios are not good measures of the reward to risk ratio for individual assets,  because the Sharpe Ratio uses total volatility as a risk measure,  not just the systematic risk component.

Of course,  this reasoning based on (2.29) applies only to small changes to the portfolio at the margin. The change in portfolio risk from a small addition of asset i to the portfolio depends approximately only on the asset's systematic risk because the idiosyncratic risk diversifies away in the portfolio. Yet,  if the investor were to add a lot of asset i to the portfolio,  portfolio return variance and the covariance of portfolio return and asset i's return changes. Moreover,  some of the risk that was idiosyncratic now becomes systematic: The higher the allocation to asset i,  the higher becomes the correlation of Ri and Rw. In the extreme case,  where there is so much of asset i in the portfolio that R⇤ ⇡ Ri,  the "i component vanishes.

This illustrates that what an investor considers as systematic or idiosyncratic risk depends on her existing portfolio. Since ⇤i depends on what's in the investor's existing portfolio,  ⇤i will typically be different for different investors. Hence,  how investors perceive systematic risk of assets will also differ.

## 2.4 MAXIMUM SHARPE RATIO

We can also show that when the condition (2.29) holds,  and hence R⇤ is truly the return on an optimal portfolio that cannot be improved any further,  then this optimal portfolio achieves the highest possible Sharpe Ratio of any portfolio that can be constructed from the available assets.

To see this,  start from (2.29),

$$\mathbb{E}[Z_{i}]={\frac{\operatorname{cov}(Z_{i},      R^{*})}{\operatorname{var}(R^{*})}}\,      \mathbb{E}[Z^{*}]$$
$$(2.32)$$

and let i = var(Zi)1/2,  = var(R⇤)1/2 and let ⇢i denote the correlation of Zi and R⇤.

Since |⇢i| 1,  it is true that

$$|\operatorname{cov}(Z_{i},      R^{*})|=|\rho_{i}|\sigma_{i}\sigma\leq\sigma_{i}\sigma$$
 $\diamond$ (2.32) and rearranging,  we get.
| cov(Zi,  R⇤)| = |⇢i|i i (2.33)
$\text{Uniting}\cup\text{I}$
Substituting this inequality into (2.32) and rearranging,  we get

$$(2.33)$$

$${\frac{|\mathbb{E}[Z_{i}]|}{\sigma_{i}}}\leq{\frac{\mathbb{E}[Z^{*}]}{\sigma}}.$$

$$(2.34)$$
. (2.34)
This tells us that the Sharpe ratio of any asset i (or any combination of assets) cannot exceed the Sharpe ratio of the optimal portfolio. In other words,  the portfolio with weights!⇤ that we constructed in (2.18) has the highest possible Sharpe ratio of any portfolio combining the same assets.

## 2.5 MARKET EQUILIBRIUM

As we did in the previous lecture for a single risky asset,  we can again ask how the portfolio choice of an individual investor fits together with the choices of other investors in equilibrium where supply equals demand. Our market equilibrium analysis in the previous lecture can be interpreted as dealing with the demand and supply of risky assets as a whole class. Here we are now asking about the composition of risky asset portfolios: what sort of composition investors would like to have,  and how the market gets these desired portfolio weights in line with the supply of securities actually available.

Because we are interested in this compositional question,  we now focus on the *relative* quantities of risky assets,  expressed as a proportion of the total market capitalization of risky assets that investors demand or that is available as supply.

Supply is then given by the weights of the *market portfolio* of risky assets. This is the portfolio in which the weight of each asset is equal to ratio of the asset's market capitalization (price times shares outstanding),  *mcap*i,  to the aggregate market capitalization of all risky assets:

$$\omega_{m,      i}={\frac{m c a p_{i}}{\sum_{j=1}^{N}m c a p_{j}}}.$$

To see how equilibrium plays out,  in a first simple thought experiment,  suppose all investors want to hold the same portfolio,  i.e,  they all want to have the same proportions

$$(2.35)$$

of risky assets in their portfolios. In this case it is very easy to see which portfolio they must necessarily end up with in equilibrium: the market portfolio. Holding the market portfolio is the only way in which all investors can hold the same portfolio. Then the weight of each asset in the market overall,  aggregated across all investors is the same as the weight the asset has in each investor's portfolio. For example,  suppose each investor wants to hold 3% of their portfolio,  in terms of market value,  in Apple stock. The only way this is possible is if the aggregate market capitalization of Apple is 3% of the aggregate market capitalization of all risky assets.

How would the market get to such an equilibrium in which the market clears? Prices need to adjust so that investors' desired portfolio weights end up being identical to market portfolio weights. Suppose for example that the market for Apple stock does not clear (yet): there is excess demand,  i.e. investors want to hold more shares of Apple than there are outstanding shares of Apple. This means that investors will bid up the price. This has two effects. First,  a rise in the price (with expectations of future fundamentals unchanged) lowers the expected return of Apple. This makes Apple stock less attractive. Hence investors' desired portfolio share of Apple,  and hence demand,  goes down. At the same time,  the rise in the price raises Apple's weight in the market portfolio and in each investor's portfolio. So both of these effects of the price change work to get investors' desired portfolio weights closer to market portfolio weights. If the price rise is big enough,  desired portfolio weights and market portfolio become equal,  supply equals demand,  and the market therefore clears.

Now let's analyze what happens when investors not only want to hold identical portfolios,  but their demands come from mean-variance optimization: they all want to hold portfolios with weights according to our optimal risky asset portfolio formula (2.18)
and they have the same beliefs about expected returns,  variances,  and covariances. Then prices of risky assets must adjust such that the optimal portfolio ends up being equal to the market portfolio. And the return R⇤ is then equal to the market portfolio return Rm. This means that the relationship in (2.29) now becomes

$$\mathbb{E}[Z_{i}]={\frac{\operatorname{cov}(Z_{i},      R_{m})}{\operatorname{var}(R_{m})}}\,      \mathbb{E}[Z_{m}]=\beta_{i}\,      \mathbb{E}[Z_{m}]$$

which is the Capital Asset Pricing Model (CAPM)! So the CAPM results from combining the assumption that investors have identical beliefs about risk and return and seek to hold mean-variance optimal portfolios with the market equilibrium condition that demand equals supply.

For the applications we focus on in this course,  the assumption that all investors want the same portfolio is not realistic. But,  still,  the market portfolio is an important reference point.
If we take a position different from the market portfolio,  there must be,  for the market to clear,  someone willing to take the other side in the sense of also deviating from market portfolio weights,  but in the opposite direction. If we overweight an asset in our portfolio,  then,  collectively,  the rest of the investors in the market have to underweight this asset.

Therefore,  if we are entertaining such a deviation,  it is always important to ask: Why would anyone be willing to take the other side? Can we have confidence that we are right and the party taking the other side is not,  or that we have special circumstances
(e.g.,  a better ability to bear certain types of risk than others) that make an asset more attractive to us than it is to others?

The market portfolio is a very special portfolio. Aside from new issues of stocks,  delistings,  and needs to reinvest dividends,  holding the market portfolio does not require any trading. For example,  if we hold the market portfolio and the price of asset i goes up from yesterday to today more than the market overall,  its weight in our portfolio goes up. However,  its weight goes up exactly the same in the market portfolio. Hence,  we don't have to trade to keep holding the market portfolio. This is why index funds typically follow *value-weighted* indices where asset weights depend on stocks' market capitalization relative to the aggregate market capitalization of all stocks in the index,  just like in the market portfolio.

Because trading needs are so minimal,  holding the market portfolio,  or more generally a value-weighted portfolio,  is very cheap in terms of trading cost. As an example,  Figure
(2.1) shows some portfolio statistics for the Vanguard Total Stock Market Index Fund.

This is a fund that aims to replicate the performance of the entire market portfolio of U.S. stocks as represented by the CRSP value-weighted index. As the figure shows,  the turnover rate of this fund is less than 5% per year. This means that only 5% of the portfolio's total value is traded each year. Most of this is accounted for by dividends,  proceeds from mergers that must be reinvested,  and investment in initial or seasoned

public offerings that come to the market. But other than this,  there is basically no need to trade.

Fortunately,  there are important long-term economic incentives for index fund managers to take governance more seriously. The greatest threat to index fund asset accumulation is deteriorating absolute returns and underperformance versus actively managed funds. Index funds have had the proverbial winds at their backs as large and continuous asset flows support their performance.

The problem of asset flows without regard to valuation is compounded by the fact that the most popular indexes are market-cap weighted. This means that the larger the market cap of the company,  the larger its representation in the index. In other words,  as the stock price rises,  its weighting in the index increases,  and the index fund is required to buy more of the company.

While value investors typically buy more as stock prices decline (assuming intrinsic value has also not declined),  market-cap weighted index funds do the opposite. They are inherently momentum investors,  forced to buy more as stock prices rise,  magnifying the risk of overvaluation of the index components.

Figure 2.2: From Pershing Square Capital Management Annual Letter 2015 Is There an **Index Fund Bubble?** We believe that it is axiomatic that while capital flows will drive market values in the short term,  valuations will drive market values over the long term. As a result,  large and growing inflows to index funds,  coupled with their market-cap driven allocation policies,  drive index component valuations upwards and reduce their potential long-term rates of return. As the most popular index funds' constituent companies become overvalued,  these funds long-term rates of returns will likely decline,  reducing investor appeal and increasing capital outflows. When capital flows reverse,  index fund returns will likely decline,  reducing investor interest,  further increasing capital outflows,  and so on. While we would not yet describe the current phenomenon as an index fund bubble,  it shares similar characteristics with other market bubbles There is also a lot of misconception out there about the mechanics of running a market-capitalization weighted portfolio like the Vanguard Total Stock Market Index Fund or any other market-capitalization weighted fund. One popular misconception is that market-cap weighting implies that the fund has to purchase more shares when prices go up. This fuels the concern that the presence of market-cap weighted funds in the market may lead to asset price bubbles where price increases cause further mechanical buying,  which leads to further price increases not justified by fundamentals,  etc. Figure 2.2 shows an example from Bill Ackman's (Pershing Square Capital Management) 2015 letter to shareholders. This sort of argument is mistaken,  however. If the price of an asset in a market-cap weighted portfolio rises by x%,  then,  everything else equal,  the weight of the asset in a market-capitalization weighted index rises by x%. At the same time,  the weight of the asset in a market-capitalization weighted portfolio also rises by x%—without any trading. Therefore,  after this price change,  the asset's weight in the portfolio is still exactly equal to the share that a market-capitalization weighted index fund wants it to be. There is zero need to trade.

Consider by analogy the period leading up to the technology stock market collapse in early 2000.

During that period,  Berkshire Hathaway and other leading value investing practitioners' portfolios dramatically underperformed technology stock managers. This caused investors to withdraw capital from value managers and allocate capital to growth and technology investors until valuations reached bubble proportions. The tech market subsequently collapsed,  with value investing dramatically outperforming so-called growth investing in the ensuing years. Last year,  a similar phenomenon occurred as Berkshire Hathaway underperformed the S&P 500 index by more than 1,  300 basis points despite the benefit of the market support provided from it being one of the index's largest components.

 The Fact That Most Of The Investments That We Have Identified In Recent Years Have Been Found Outside Of The S&P 500 Perhaps Is Suggestive Of The Major Index Components' Relative Unattractiveness From A Valuation Perspective. It Also Explains Why The Shareholder Bases Of These Non-Index Companies Is Comprised Mostly Of Hedge Funds And Other Active Managers Who,  Like Pershing Square,  Use Discount To Intrinsic Value As A Primary Investment Consideration.
 2. As Many Of These Index Managers Are U.S. Corporations,  Other Interesting Governance Question Arise About Their Corporate Control And Influence In Foreign Jurisdictions Where Activism Is Less Prevalent.
 3. The Recent Underperformance Of Non-Heavily Indexed Companies Creates An Opportunity For Savvy Index Fund Operators And A Good Long-Term Hedge For Their Businesses. Index Fund Managers Should Create Index Funds Of Under-Indexed Stocks. 2.6 Estimation Of Return Moments In The Multiple Risky Asset Case

Last lecture we discussed empirical estimation of mean and variance of returns. To implement the optimal portfolio according to our formula (2.18),  we now also need an estimate of the covariance matrix ⌃. We can estimate it from historical returns as 7

term investors to evaluate,  as active oversight of Corporate America and global corporations is
essential to the country's long-term business performance
$${\hat{\boldsymbol{\Sigma}}}={\frac{1}{T-1}}\sum_{t=1}^{T}({\boldsymbol{R_{t}-\hat{\boldsymbol{\mu}}}})({\boldsymbol{R_{t}-\hat{\boldsymbol{\mu}}}})^{\prime}$$
0 (2.37)
$$(2.37)$$

$${\hat{\boldsymbol{\mu}}}={\frac{1}{T}}\sum_{t=1}^{T}{\boldsymbol{R}}_{t}$$
$${\hat{H}}$$

![2_image_0.png](2_image_0.png)

$$(2.38)$$
Rt (2.38)

Stocks I-Stocks Value Small T-Bonds I-Bonds C-Bonds REITS Gold

Mean 0.079 0.060 0.102 0.091 0.030 0.041 0.037 0.074 0.007

Std.dev. 0.157 0.172 0.177 0.209 0.064 0.087 0.068 0.170 0.175 Stocks 1.000 0.711 0.877 0.851 0.056 0.243 0.349 0.652 0.086

I-Stocks 0.711 1.000 0.647 0.599 0.048 0.545 0.308 0.520 0.173

Value 0.877 0.647 1.000 0.823 -0.025 0.192 0.281 0.689 0.028

Small 0.851 0.599 0.823 1.000 -0.079 0.166 0.222 0.632 0.069

T-Bonds 0.056 0.048 -0.025 -0.079 1.000 0.435 0.816 0.120 0.117 I-Bonds 0.243 0.545 0.192 0.166 0.435 1.000 0.478 0.308 0.349

C-Bonds 0.349 0.308 0.281 0.222 0.816 0.478 1.000 0.393 0.157

REITS 0.652 0.520 0.689 0.632 0.120 0.308 0.393 1.000 0.128

Gold 0.086 0.173 0.028 0.069 0.117 0.349 0.157 0.128 1.000

Table 2.1 shows an example from the same data of several asset classes that we already looked at last lecture. I broke the covariances into standard deviations (shown in the second row) and correlations (matrix below the second row). The underlying data are monthly returns,  but I annualized the mean returns and standard deviations by multiplying with 12 and 12,  respectively.

Note that we are now considering Treasury bonds,  and also the other bond asset classes,  as risky assets. In Lecture 1,  we did a crude calculation of the average investor's risky asset share where we lumped Treasury bonds and other bonds into a broad riskfree asset class. Here we are now taking a more refined approach where only short-term Treasury bills are viewed as risk-free while bonds with maturities beyond one year are viewed as risky. And,  indeed,  the table above shows that the return standard deviations of the bond asset classes are substantial.

For the estimates of mean returns,  we discussed in the last lecture how to estimate standard errors that give us an idea about the statistical uncertainty we have about expected returns.

It would be useful to also get a sense for the statistical uncertainty about covariances.

However,  the covariance matrix is a high-dimensional object. For our purposes it's not necessary to now write down and study the formula for the standard error of the whole covariance matrix estimate. But to get a sense of the magnitudes,  let's focus on the

$$1\ 202$$

standard error of the variance estimates (i.e.,  the entries on the diagonal of the covariance matrix). In the special case of normally distributed returns,  the estimate of the variance of asset i on the diagonal of the covariance matrix has standard error

$$\mathrm{s.e.}(\hat{\sigma}_{i}^{2})=\frac{\sqrt{2}}{\sqrt{T}}\sigma_{i}^{2}.$$
$$(2.39)$$

A back-of-the-envelope calculation: Let's say we estimate the variance of an aggregate stock market index. Suppose the estimated standard deviation of annual returns on the aggregate stock market index is roughly 20% and so the variance is about 4%. Then with 10 years of data,  s.e.(ˆ!2) ⇡ 0.018. So,  using again a Bayesian interpretation,  as when we looked at the standard error of the mean last lecture,  we would conclude that with 95% probability,  the true variance is in the interval 0.04 ± 2 0.018. This is quite wide,  but not quite as wide as in the case of the estimate of µ. With 100 years s.e.(ˆ!2) ⇡ 0.006,  which is quite precise. Of course,  one can ask the same question about variance estimation that one can ask about estimation of the expected return: Is data from so long ago relevant for assessing the likely values of variance going forward?

However,  as we will see shortly,  there may be an opportunity to get much more precise estimates of variances and covariances by measuring returns over higher frequencies.

Unfortunately,  the same trick is not going to work for getting more precise estimates of expected returns.

## 2.6.1 EFFECT OF MEASUREMENT FREQUENCY ON STATISTICAL PRECISION

Since we can often choose the frequency at which we measure returns,  we may wonder what is the best frequency? One way in which we might evaluate what's "best" is to focus on the effects on our statistical uncertainty about the true values of expected returns and variances. Having less statistical uncertainty is better. As it turns out,  there is a drastic difference in how the standard error of estimates of expected return relates to measurement frequency and how the standard error of variances (and covariances)
relates to measurement frequency.

Consider first the expected return. Suppose we have returns measured over T periods,  say,  annual. The average return over these T periods gives us the expected return estimate ˆµ. As we noted last lecture,  the standard error is

s.e.($\hat{\mu}$) = $\frac{1}{\sqrt{T}}\sigma$. (2.40)
But now we wonder whether we should perhaps chop each of these periods into n smaller subperiods and measure returns at this higher frequency. We then have a total number

$${\mathrm{(\mathbb{C})}}{\mathrm{Stefan~Nagel~2024~}}$$

of periods of T n. Based on our annualization formulas from last lecture,  the expected returns at this higher measurement frequency would be approximately 1/n times the annual average return,  i.e.,  µ/n. The standard deviation would be 1/
n times the standard deviation of annual returns,  i.e.,  !/
n. Therefore,  the standard error of the higher-frequency estimate ˆµ(n) would be

s.e.$(\hat{\mu}(n))=\frac{1}{\sqrt{nT}}\frac{\sigma}{\sqrt{n}}=\frac{1}{\sqrt{Tn}}\sigma$. (2.41)
This is 1/n times the standard error of annual returns. However,  as we discussed,  the magnitude of expected returns is also smaller by factor 1/n. Hence,  the ratio of true expected return to standard error remains unchanged. It is invariant to the measurement frequency! So chopping the return measurement intervals into smaller pieces is not going to help us at all to get more precise estimates of expected returns. If we make the measurement intervals smaller,  the signal (true expected return) shrinks at the same rate as the standard error.

As a consequence,  if we annualize the higher-frequency estimate in order to get an apples-to-applies comparison,  i.e.,  we look at nµˆ(n),  then the standard error for this annualized estimate is simply ns.e.(ˆµ(n)) =
1 T!,  i.e.,  exactly the same as the standard error when we use annual returns!

This is a very important lesson. If we are trying to improve the precision of our expected return estimates,  it's of no use to go to higher return measurement frequency!

Say we have 30 years of data at most on an asset and we use the average return as an estimate of the expected return. Then the total length of this sample period,  30 years,  effectively pins down the standard error of the expected return estimates. It does not matter for the statistical precision of our estimate whether we measure the returns annually,  monthly,  daily,  or at some other frequency.

Now,  interestingly,  the situation is very different for variances and covariances. Recall that for the variance estimate,  the standard error is

$${\mathrm{s.e.}}({\hat{\sigma}}^{2})={\frac{\sqrt{2}}{\sqrt{T}}}\sigma^{2}$$
$$(2.42)$$

The key is that this standard error depends on the variance,  while the standard error of the mean in (2.40) depends on the standard deviation. If we divide the return measurement periods into n subperiods,  then this variance falls by a factor of 1/n. The standard error of the higher-frequency estimate ˆ!(n)2 becomes

$${\mathrm{s.e.}}({\hat{\sigma}}(n)^{2})={\frac{\sqrt{2}}{\sqrt{n T}}}{\frac{\sigma^{2}}{n}}={\frac{1}{n^{3/2}}}{\frac{\sqrt{2}}{\sqrt{T}}}\sigma^{2}$$
$$(2.43)$$
$$45$$
$\text{(}\!\!\text{C)}\!\!\text{Stefan Nagel}\,      \\,      \text{!}$

If we look at the ratio of the true variance,  which falls by factor of 1/n and the standard error,  which falls by a factor of 1 n3/2,  we see that the ratio rises by (1/n)/n3/2 = n. In other words,  the standard error falls relative to the true variance. This means we gain in precision!

If we annualize the higher-frequency variance estimate,  i.e.,  we look at n!ˆ(n)2,  then the standard error for this annualized estimate is

$$n{\rm s.e.}(\hat{\sigma}(n)^{2})=\frac{1}{\sqrt{n}}\frac{\sqrt{2}}{\sqrt{T}}\sigma^{2}\tag{2.44}$$

which is smaller,  by factor 1/
n,  than the standard error when we use annual returns.

The same factor applies to covariances as well,  but we are not going to show this explicitly.

![5_image_0.png](5_image_0.png)

Figures 2.3 and 2.4 illustrate this with simulations. I simulate T = 10,  000 daily returns by drawing from a normal distribution such that the annualized returns (assuming 250 trading days per year) have mean 0.05 and standard deviation 0.20. I calculate the mean and standard deviation of these daily returns. Then I aggregate the returns to annual returns by summing the daily returns within 250-day windows (if I do it by

.

![6_image_0.png](6_image_0.png)

properly compounding the daily returns,  the results are very similar). I calculate the mean and standard deviation of these annual returns. Then I repeat this 1,  000 times each with a new random draw of a daily return series of length T = 10,  000.

Figures 2.3 shows that the distribution of the mean of annual returns and distribution of the annualized mean estimated from daily returns (i.e.g,  daily return mean times 250) is basically identical,  as expected based on our earlier standard error calculations.

In contrast,  Figure 2.4 shows that the distribution of annualized standard deviations estimated from daily returns (i.e.,  daily return standard deviation times 250) is far smaller than the standard deviation of annual returns. The annualized standard deviations estimated from daily returns are much closer to the true standard deviation of 0.20. In other words,  these estimates are much more precise.

This is potentially extremely useful. The covariance matrix ⌃ is an important input into the mean-variance optimal portfolio formula. If it is estimated with too much error,  the error may render the estimated portfolio weights useless. This is,  in fact,  one of the major problems that practical applications of portfolio optimization struggle with and where clever improvements can make a difference. One first step is to do what our analysis above suggests: Make the estimate of ⌃ more precise by using higher-frequency

data (say,  daily or weekly rather than annual data). In Table 2.1 I have used monthly data,  which is not as good as daily or weekly,  but better than annual.

That said,  while higher-frequency data is useful for covariance matrix estimation,  we also need to keep in mind some limitations.

First,  by going to higher measurement frequencies,  we can only get more precise estimates of variances if random shocks to returns over longer periods are always composed of smaller random shocks over shorter subperiods. This means that,  for example,  for variances of daily returns to give us more precise estimates than variances of monthly returns,  the monthly returns should be composed of a steady series of random shocks,  as opposed to just occasional jumps in prices on a few days with little price movement inbetween these infrequent jumps To illustrate: Suppose once every ten years,  the stock market experiences a day in which the market crashes with a huge negative return on a single day (say,  -20%). Let's also stick to the notion that returns are serially independent. Hence a crash is not followed by a predictable reversal of stock prices afterwards. If we have data that spans ten years and includes one of those crashes,  the variance estimate will capture the existence of such crashes. While variance as a risk measure might not do enough to properly characterize the severity of the crash,  if the data includes the crash,  the variance estimate will be substantially increased by the crash data point. However,  dividing return measurement intervals into shorter periods is not going to help us to get a more precise estimate of the frequency and magnitude of such crashes because most return measurement periods do not include a crash.

Market microstructure can also interfere if we try to measure returns from transaction prices at very high frequency,  especially for assets that are relatively illiquid. At high time resolution,  returns can be distorted by the bid-ask spread,  for example. If a buy order comes in,  it gets executed at the (high) ask price,  if a sell order comes in,  it gets executed at the (low) bid price. As a flow of orders comes in,  randomly switching between buys and sells,  the prices at which transactions occur tends to bounce around between the lower bid and higher ask prices. If we measure returns at such high frequency that we capture a lot of this bouncing around between bid and ask,  but this bouncing between bid and ask is not really reflecting any variation in the value of the asset. This means a variance estimate based on very high-frequency return data may overstate the true variance because it contains the bid-ask bounce effects in addition to variance in the value of the asset.

1For those interested in some more (optional) detail: Using high-frequency data to estimate variances works perfectly,  in the sense that we could get infinitely precise estimates in the limit of infinitesimally small return measurement periods,  when returns are generated as a continuous-time diffusion (a continuous-time diffusion does not have any discrete jumps,  no matter how small we make the return measurement interval). This point was shown in Merton,  Robert C.,  1980,  On estimating the expected return on the market,  Journal of Financial Economics 8,  323–361.

Non-synchronicity effects are another microstructure phenomenon that will distort covariance estimates constructed from transaction prices at very high frequency. Suppose you have two assets: Asset A which is very liquid and usually trades every microsecond,  and asset B which is very illiquid and trades only about once per hour. If we go to very high frequency—say,  5 minute returns—to estimate covariances,  it will happen very often that there is a piece of news that affects the true value of both assets,  but only the price of liquid asset A responds immediately,  while it may often take another hour or so until the price of asset B adjusts. But this stale price of asset B
that is recorded in a returns data file is not a true price. If someone actually tried to trade,  the price would adjust. It just didn't because it happened to be the case that nobody wanted to trade. With such non-synchronicity of prices,  it may seem,  based on 5 minute return data that the covariance of the returns of asset A and B is really low,  when in fact it is much higher. In contrast,  covariances estimated from daily returns in this example would have virtually no distortion from non-synchronicity and would reveal a higher covariance.

Similar problems can appear when assets are traded in different time zones. A returns data set may record daily prices for assets on the same day,  but if one asset traded in Tokyo and the other in New York,  they are clearly not measured at the same point in time. Hence,  a covariance estimate based on these daily returns would underestimate the true covariance.

An extreme form of this latter problem shows up with highly illiquid assets like private equity,  private-market debt securities,  and infrastructure assets. These assets rarely trade. And if we don't observe market prices regularly,  it's dicult to estimate covariances,  and,  as a consequence,  it's dicult to figure out how much risk such assets bring to a portfolio. More on this in lecture 9.

## 2.7 OPTIMAL PORTFOLIO WEIGHTS BASED ON EMPIRICAL ESTIMATES OF RETURN MOMENTS

Now let's use the estimates of means and covariances in Table 2.1 to construct the mean-variance optimal risky asset portfolio according to our formula (2.18) which I
repeat here:

 $ \omega^*=\frac{1}{\iota'\Sigma^{-1}\mu}\Sigma^{-1}\mu$ so we simply replace the vector $ \upsilon$ with the me.
I now use a *plug-in* approach where we simply replace the vector µ with the mean excess returns estimates from Table 2.1,  which I label z¯,  and the covariance matrix ⌃ with the

$$(2.45)$$
$20\Omega$
estimated covariance matrix from Table 2.1 (recall that a covariance is the product of the two standard deviations of the pair of asset returns and their correlation),  which I
label ⌃✓. I then calculate
ˆ ⇤ = 1
!0⌃✓ p1z¯
⌃✓ p1z¯ (2.46)

$$(2.46)$$
$\boxed{\frac{1}{1}}$

![9_image_0.png](9_image_0.png)

Figure 2.5 presents the result. The bars in this figure show the elements of the portfolio weight vector ˆ ⇤. This result may be somewhat surprising. The portfolio is mostly a combination of long positions in government bonds (U.S. Treasury and international) and domestic value stocks,  as well as a short position in international stocks. Other asset classes only play a minor role.

These results are quite sensitive to the inputs,  though. So our work is not done yet.

A first step to understand a bit better the potential fragility of the plug-in solution to the optimal portfolio problem is to conduct a sensitivity analysis. In general,  it's quite dicult to predict how changes in a small number of inputs affects the optimal portfolio weights. The covariance matrix is a big object. It's dicult to tease out simple relationships between inputs to the formula and the optimal weights that are the outputs when the formula involves an inverse of a relatively big covariance matrix. All of the elements of the covariance matrix and the mean return vector can interact in ways that are difficult to isolate. But we can sometimes get a rough idea by seeing what happens when we change some of the input numbers.

The perhaps most striking fact of the portfolio in Figure 2.5 is the high allocation to bonds. One may be concerned that,  at least in part,  this is a consequence of the fact that bond returns have been fantastic during the past 40 years that our data covers in this exercise. At the beginning of this four-decade period,  interest rates were very high and they have trended down throughout these four decades. This long downward trend was certainly not fully anticipated in the early 1980s when interest rates were high. As a consequence,  part of the high returns that bonds realized over the past 40 years was an unexpected positive surprise. So our estimates of expected excess returns based on historical returns from the past four decades may overstate the returns that can be expected going forward. We will look into all this in much greater detail when we discuss bonds and interest rates in a future session. But for now let's just do a simple sensitivity check: How do the results change if we reduce our estimate of the expected excess returns of the three bond categories by one (annualized) percentage point?

One percentage point is not much. Recall that in the last lecture we estimated the standard error of the mean returns in the three bond categories and the standard error was roughly one percent for each of them. So in this sensitivity check we are just considering a relatively mild deviation of one standard error.

Subtracting one percentage point from the mean returns of the three bond categories and then recalculating the optimal portfolio yields weights of shown in Figure 2.6a.

Comparing with the weights before this modification,  we see a reduction in the allocation to international and corporate bonds,  but,  surprisingly,  an increase in the U.S. Treasury bond allocation. This illustrates how difficult it is to anticipate the change in the optimal portfolio weights that results from changing some of the inputs of the portfolio formula.

The overall allocation to bonds of all three categories combined does not seem very sensitive to the potentially too optimistic bond return expectations.

Another useful sensitivity check can help us understand the conditions that lead to short positions in international stocks in the optimized portfolio. Looking back at Table 2.1 and focusing on the stock asset classes,  we see that the three stocks asset classes—domestic,  international,  and value stocks—have high correlations above 0.60.

At the same time,  the mean excess returns are quite dierent,  with value stocks having about four percentage points higher mean excess returns than international stocks,  and domestic stocks somewhere inbetween. From a portfolio optimization viewpoint,  this looks like an opportunity to construct a position that earns high expected return with

##

![1_image_0.png](1_image_0.png)

![1_image_1.png](1_image_1.png)

little risk: go long value stocks and short international stocks. This position earns the spread in mean returns between the two asset classes. At the same time,  due to the high correlation,  much of the unexpected movements in returns cancel out. High correlation means that the returns tend to move together in the same direction; so then going long in one asset and short the other means that the returns oset to a large extent,  leaving very little residual risk relative to the size of the spread in mean returns that the position earns.

We can see this mechanism at work when we change the mean return inputs. I set the mean excess return of international stocks to be the same as domestic stocks,  i.e.,
1.9 percentage points higher relative to the estimate from historical data. Recalculating the optimal portfolio weights we get the allocations shown in Figure 2.6b. Now the short position in international stocks is gone. But bond allocations change,  too,  even though we made no change to bond expected return or covariance estimates,  which illustrates again how difficult it is to predict what happens to optimal allocations when one changes a few of the inputs.

Another way of checking sensitivity is to examine how the optimal weights change if we use inputs from dierent time periods. For this exercise,  I estimate mean excess returns and the covariance matrix over 10-year periods. I start at the beginning of 1990 and use data from 1980 to 1989 to calculate the optimal weights. Then I move the data window forward by one month and recalculate the weights; then I repeat until the end 10-year data window reaches the end of the data set at the end of 2022.

![2_image_0.png](2_image_0.png)

Figure 2.7 shows the results. In the latest decade,  the weights are somewhat stable and not too extreme. But in the first decade,  they take extreme values: In the early years we see weights of more than 400% in corporate bonds and a roughly similarly sized

##

short position in Treasury bonds. This is eectively an extremely highly levered bet on corporate credit. Based on 10-year lagged data on returns,  and taking these data as the true expected excess returns and covariances,  this looked like an attractive position back then.

But we should be skeptical about such extreme weights coming out of a portfolio optimization formula. After all,  if such an extreme long-short bet was so attractive in the 1990s,  how come other investors didn't exploit it? If they had tried to exploit it,  prices of corporate and treasury bonds would have adjusted to make the trade less attractive.

And there is good statistical reason to be skeptical. With 10-year data windows,  the estimates of mean excess returns are very imprecise. With 10-years of data,  the standard error of the mean is about 2% for Treasury and corporate bond returns,  which is substantial relative to the estimated mean excess returns for these two asset classes.

Therefore,  it is quite likely that the extreme long corporate,  short Treasury bond position that the optimal portfolio formula recommends is just an artifact of estimation error in the mean excess returns (which would also explain why it disappeared subsequently in Figure 2.7).

That such extreme weights can occur as output of the portfolio optimization formula is quite typical for plug-in implementations of the mean-variance efficient portfolio weights. Especially if one feeds in estimates of mean excess returns that were obtained from a relatively short time window of only a decade or two.

Now there are good reasons why sometimes we may want to use data windows that are relatively short. We may be worried that markets and the global economy have changed so much over time that data from several decades ago may no longer be very relevant for forecasting returns and covariances in the future. For this reason,  we now look at statistical methods that can help us increase the precision of the inputs to our portfolio optimization formula.

## 2.8 SHRINKAGE ESTIMATION

The estimation approach we have discussed so far starts from a viewpoint of complete ignorance about µ and ⌃. We proceeded as if,  before looking at historical data,  we basically have no idea whatsoever what the values of expected returns,  variances,  and covariances are likely to be. And then we just set µ and ⌃ to whatever the data tells us the estimates are.

This doesn't seem quite right. Surely we would think that an expected excess return of,  say,  the domestic stock market in the vicinity of,  say,  5% annually in excess of the risk-free rate is more likely than the expected return exceeding 100%? It would not make economic sense that expected returns are so high,  as people would have to have crazily high levels of risk aversion for stocks to oer such high rates of expected return.

Based on *a priori* considerations,  before looking at any data,  we would say that such high expected returns are totally implausible. Yet,  if we take the sample average return as the only piece of information about the expected return,  we are not making any use of such *prior* knowledge that we may have. This prior knowledge may be vague,  but as we will see,  it can still be useful to obtain better estimates of return moments.

The Bayesian branch of statistics oers tools that allow use to describe mathematically how *prior* knowledge expressed as a probability distribution,  the *prior distribution*,
can be combined with evidence from data to obtain a *posterior* distribution that reflects the combined information from the prior and the data. For our purposes here,  we don't have to work through all that math required for working with the full prior and posterior probability distributions. For practical purposes,  we can get quite far by just using a heuristic approach that captures the essence of the Bayesian method for the purpose of choosing portfolios.

Let's start with the prior beliefs. Suppose we think,  a priori,  that a reasonable number for expected excess returns of the risky assets under consideration is 5%. Then,  our prior mean vector (the mean of the prior probability distribution) µ0 is a vector in which all elements are equal to 0.05. This does not mean at all that we are certain about this number,  but we see it as a reasonable starting point. Bayesian statistics (under the assumption that both the prior distribution and the deviations of realized excess returns from µ are normally distributed) then tells us that our posterior mean is

$$\hat{\mu}=\phi\bar{z}+(1-\phi)\mu_{0},      $$
$$(2.47)$$
µˆ =!z¯ + (1 ⇥!)µ0,  (2.47)
i.e.,  it's a weighted average of sample average excess returns of the assets and the prior mean. How much weight! we would optimally put on the information coming from the observed data,  z¯ vs. the weight 1⇥! on the prior mean depends on: (i) how informative the data is (higher! if the sample is larger and returns are less volatile); (ii) the precision of our prior beliefs that µ is in the vicinity of µ0 (lower! if our prior beliefs are more precise).

But how do we come up with µ0? We could put in a number that seems reasonable.

But is there perhaps a better approach,  one in which we could still let data influence our view?

We can exploit that we have multiple risky assets. It is not only implausible that expected excess returns on any individual asset class are extremely large,  it is also implausible that they dier from each other by huge amounts. So if it happens to be the case that the sample averages of returns of asset classes dier a lot,  it's likely at least partly due to estimation error. To express this view that expected excess returns can't be too dierent in a prior belief we could say that the N elements of µ are drawn from a distribution that is centered around the same mean µ0 for all N assets,  with some variance around this mean. In other words,  we can write the prior mean vector as µ0 = µ0.

Our posterior mean now becomes

$$(2.48)$$
$$\hat{\mu}=\phi\bar{z}+(1-\phi)\iota\mu_{0}.$$

µˆ =!z¯ + (1 ⇥!)µ0. (2.48)
The posterior mean of the asset returns is now pulled towards the common prior mean µ0. We call this *shrinking* towards µ0 and µˆ is a *shrinkage* estimator.

Now to the final step: What would be a good way to find a plausible value for this common mean? Rather than specifying µ0 purely based on a priori reasoning,  as a truly Bayesian approach demands,  we will use an approach that backs it out from observable data. This approach is known as an *empirical Bayes* approach.

Given that all assets share the same prior mean,  and realizations of returns are basically all random deviations from this prior mean (with two components,  first,  the deviation of individual µi from µ0 and then deviations of realized excess returns from the individual asset specific mean µi),  a natural approach is to simply average,  across assets,  the time series averages of returns,  i.e.,  use

$$\bar{\bar{z}}=\frac{1}{N}\bar{\imath}^{\prime}\bar{z}$$

$$(2.49)$$

$$\hat{\mathbf{\mu}}=\phi\bar{\mathbf{z}}+(1-\phi)\mathbf{\iota}\bar{\bar{z}}$$
$$(2.50)$$
0z¯ (2.49)
as an estimator of µ0. And then we plug it into the posterior mean equation in place of µ0:
µˆ =!z¯ + (1 ⇥!)z¯¯ (2.50)
Now the posterior mean is pulling the estimates away from the individual-asset timeseries averages in z¯ toward the the cross-asset average of these time-series averages,  z¯¯.

Now let's refine this a little. For many assets,  it might not be all that plausible that the true elements of µ are drawn from distributions with a common mean µ0 because the assets dier substantially in their levels of risk. For example,  think of a portfolio of long-term U.S. Treasury bonds and a broad stock market portfolio. It does not seem plausible,  *a priori*,  that the lower-risk Treasury bond portfolio would earn the same expected return as a broad stock portfolio. For this reason,  it may be better to work with risk-adjusted measures of expected returns,  such as the Sharpe Ratio

$\text{(}\!\!\text{C)}\!\!\text{Stefan Nagel}\,      \$.

For the kind of application we have in mind in this course,  where we are trying to form a portfolio that invests in a number of broad asset classes,  a reasonable prior view,  before seeing data on this,  might be that each of these asset classes have a tendency to deliver similar Sharpe ratios,  i.e.,  that the true ratios

$$s_{i}={\frac{\mu_{i}}{\sigma_{i}}}$$

$$(2.52)$$
$$(2.51)$$

can't stray too far from each other. In other words,  they are drawn from a distribution that is centered around the same mean s0 for all N assets,  with some random variation around s0 for each asset. Following this view,  we then shrink estimated asset class Sharpe ratios ¯zi/⇢ˆi toward their common mean rather than shrinking the mean returns.

If we have a value for this s0,  we can then get posterior Sharpe Ratios for the individual assets as

$$\hat{s}_{i}=\phi\frac{\bar{\hat{z}}_{i}}{\hat{\sigma}_{i}}+(1-\phi)\iota s_{0}.$$

And as we discussed above for shrinking means,  we can use an empirical Bayes approach by replacing s0 with the cross-sectional mean of the assets' estimated Sharpe ratios,  s¯¯:

$$\hat{s}_{i}=\phi\frac{\bar{z}_{i}}{\hat{\sigma}_{i}}+(1-\phi)\mathbf{\iota}\bar{\hat{s}}.$$
$$(2.53)$$
$${\hat{\mu}}_{i}={\hat{s}}_{i}{\hat{\sigma}}_{i},      $$
$$(2.54)$$

$${\mathrm{e~formula}}.$$

Based on this posterior Sharpe ratio,  we can then calculate the implied posterior mean as µˆi = ˆsi⇢ˆi,  (2.54)
which we can plug into the optimal portfolio choice formula.

So far so good,  but how can all this be useful if we don't know!? We could be pick some value for! and hope that it is somewhat plausible. We would want shrinkage to be weak enough to allow Sharpe ratios to vary across asset classes in ranges that seem plausible,  but strong enough to make it very unlikely that we get ˆsi that take extreme values like,  say,  ˆsi > 5. We will get to this soon.

But before we get there,  let's first look at covariance matrix estimation. We can employ similar shrinkage ideas in covariance matrix estimation. If we are trying to find an optimal portfolio with many assets,  it is crucial to bring in prior information to discipline the covariance matrix. With N assets,  the covariance matrix has N N
elements. The covariance matrix is symmetric,  where each covariance shows up twice above and below the diagonal,  but this still leaves N(N + 1)/2 parameters to estimate.

For example,  with just 10 assets,  we already have 10 (10 + 1)/2 = 55 parameters to estimate. The more parameters there are in the covariance matrix,  the more likely it is that estimation error generates problems.

The fact that we have to invert the covariance matrix in the optimal portfolio formula can hugely magnify estimation errors. We can get an idea of where the problem comes from by looking first at the case of only one asset. Here ⌃✓ is just the estimated variance of a single asset return ⇢2. If estimation error pushes ˆ⇢2 close to zero,  the inverse,  which is here just 1/⇢ˆ2,  explodes toward infinity. Non-invertibility of a covariance matrix is sort of like this. The dierence to the single asset case is that with multiple assets,  the existence of any portfolio of assets (which is a linear combination of individual asset returns) with close to zero variance makes the covariance matrix blow up. The more assets there are,  the easier it is to find such portfolios where,  by chance,  a combination of estimation errors results in a portfolio that seemingly has close to zero variance in the sample that we are using to estimate the covariance matrix.

If the covariance matrix is not invertible,  statistical software packages will tell us.

But sometimes it may just be close to non-invertible,  even though technically it is still invertible. It's useful to know how this sort of problem then manifests in the optimal portfolio weight output of the optimal portfolio formula: A typical symptom of this problem is that the optimal portfolio weights imply some huge long and short positions,  i.e.,  some weights are huge and positive,  others are huge and negative.

Intuitively,  when estimation errors in covariances make it look like as if some combination of assets delivers close to zero risk,  but earns a substantial spread in excess returns,  this looks like a great investment opportunity to the portfolio optimization formula. For example,  suppose two assets happen to have dierent expected return estimates and similar variance estimates,  and their estimated correlation is far too high
(relative to their true correlation) because returns of these two assets in our sample just happened to be highly positively correlated by chance even though they are not truly highly correlated. This looks like an opportunity to go long in the high expected return asset and short in the low expected return asset. This position earns the spread in expected returns with very little risk. The optimal portfolio formula will tell us to take a huge long-short bet. But of course taking this position would very likely lead to a big disappointment out-of-sample because the assets aren't truly highly correlated.

Estimation error just made it look like they were.

A large number of assets magnifies this problem because the more assets there are,  the more likely it is that,  just by chance,  some linear combination of assets seemingly has zero risk.

If high-frequency data is available for covariance matrix estimation,  this can help avoid these problems because it reduces the magnitude of estimation errors in covariances,  along the lines we discussed earlier. But shrinkage can be useful,  too.

Heuristically,  we can again give this a Bayesian interpretation where we combine
information in the sample covariance matrix obtained from returns data with prior knowledge about the likely values of variances and covariances.

We can decompose the covariance matrix into standard deviations and correlations:

$$\Sigma=$$
$${\begin{pmatrix}\sigma_{1}&0&\dots&0\\ 0&\sigma_{2}&\dots&0\\ \dots&&&\\ 0&0&\dots&\sigma_{N}\end{pmatrix}}\left({\begin{array}{l l l l}{1}&{\rho_{12}}&{\dots}&{\rho_{1N}}\\ {\rho_{21}}&{1}&{\dots}&{\rho_{2N}}\\ {\dots&&&\\ \rho_{N1}}&{\rho_{N2}}&{\dots}&{1}\end{array}}\right)\left({\begin{array}{l l l l}{\sigma_{1}}&{0}&{\dots}&{0}\\ {0}&{\sigma_{2}}&{\dots}&{0}\\ {\dots}&{\dots}&{\\ 0&{0}&{\dots}&{\sigma_{N}}\end{array}}\right)$$
$$(2.55)$$
$$(2.56)$$

11C(2.55)
where ij denotes the correlation between returns of asset i and j.

Let's denote the diagonal matrix with standard deviations on the diagonal with S
and the correlation matrix with C. Then we can write ⌃ as

$$\Sigma={\bf S C S}.$$
⌃ = SCS. (2.56)
Imprecisely estimated correlations are often the source of trouble in portfolio optimization. To see why,  recall the two-asset example we just discussed earlier where two assets have dierent estimated expected returns and the estimate of their correlation is close to one,  even though their true correlation is far from one. If the estimated high correlation is indeed just a statistical fluke,  then the portfolio takes an extreme position in a strategy that in reality does not deliver a great ratio of reward to risk. It just looked like it might based on erroneous estimates. This can mess up the performance of the whole portfolio. And if we have many assets,  we need to estimate many correlations
(e.g.,  if we have 10 assets,  we must estimate (1010⇥10)/2 = 45 correlations). Among so many estimates,  it's likely that a few will be way o from the true correlation due to estimation error. Hence,  it's generally a well-known problem that with a large number of assets,  just plugging the sample covariance matrix (and hence,  implicitly,  all these sample estimates of correlations) into a portfolio optimizer yields poor results.

For this reason,  we may want to express that we know that correlations are probably all positive (risky assets generally tend to move together),  but teasing out from the data which ones are higher and which ones are lower may be difficult. We express this prior belief by shrinking our correlation estimates towards an equicorrelation matrix

$$\mathbf{C}_{0}={\begin{pmatrix}1&\rho_{0}&\dots&\rho_{0}\\ \rho_{0}&1&\dots&\rho_{0}\\ \rho_{0}&\rho_{0}&\dots&1\end{pmatrix}}$$
$$(2.57)$$

$$(2.58)$$

where all the correlations take the same value 0. Using C to denote the matrix of correlations estimated from the data,  our posterior estimate of the correlation matrix becomes C✓ =!C + (1 ⇥!)C0. (2.58)

$$\widehat{\mathbf{C}}=\phi\overline{{{\mathbf{C}}}}+(1-\phi)\mathbf{C}_{0}.$$

Then our estimate of the covariance matrix becomes

$${\widehat{\Sigma}}={\widehat{\mathbf{S}}}{\widehat{C}}{\widehat{\mathbf{S}}},      $$
$\left(2.59\right)^{\circ}$
⌃✓ = S✓C✓S✓,  (2.59)
where S✓ is the estimated version of S,  i.e.,  with estimated standard deviations on its diagonal.

How can we come up with a number for 0? In the same empirical Bayes spirit as above when we looked at expected returns and Sharpe Ratios,  we can plug in an estimate of the average pairwise correlation of all assets. This means that we use the observed returns data,  we form all possible pairs of asset return series i and i where i ⇡= j,  and we estimate their correlation ˆij. Then we construct their average,

$$\bar{\rho}=\frac{1}{N(N-1)}\sum_{i=1}^{N}\sum_{j\neq i}\hat{\rho}_{i j}$$
$$(2.60)$$

We then replace 0 in the prior correlation matrix C0 with this estimate ¯.

Now we have to tackle the remaining problem of how to estimate!. We can use an approach known as *cross-validation*. Cross-validation is a powerful idea that appears in lots of places in applied statistics and data science,  including many machine learning applications. The idea is that we can use historical data on returns to evaluate which value of! would have led us to construct the best portfolios in the past,  where with
"best" we mean that this value leads to the best out-of-sample portfolio performance.

In this approach,  we basically imagine that we had constructed Sharpe Ratio estimates as in (2.53),  and portfolios based on these estimates,  in the past and we look for the value of! that would have given us the best out-of-sample performance in the past.

To implement this cross-validation approach,  I use returns data for our nine asset classes from the beginning of 1980 to the end of 2022. I then pick an estimation window size,  e.g.,  240 months,  or 20 years. Then I implement the following steps:

1. Estimate µˆ as in (2.54) and ⌃✓ as in (2.59) using data from beginning of 1980 to end of 1999 and for dierent values from! = 0 (total shrinkage) to! = 1 (no shrinkage).
1. For each of these µˆ and ⌃✓ combinations for a value of!,  I calculate the optimal risky asset portfolio weights as in (2.18).
1. I then apply these weights to returns on the nine asset classes in January 2000 to calculate the out-of-sample portfolio return in January 2000,  i.e.,  in the month following the end of the estimation window. Again I do this for every value of!.
1. Then I move the estimation window in step 1 forward by one month to beginning of February 1980 to end of January 2000. Then I repeat steps 1 to 3 and I get an out-of-sample portfolio return in February 2020 for each value of!. I keep repeating until I have reached the portfolio return in December 2022.
1. Now I have several time-series of portfolio excess returns,  one for each!. I calculate the Sharpe ratio from these portfolio excess returns.

![0_image_0.png](0_image_0.png)

I then redo the whole procedure with a different estimation window sizes of 10 years and 5 years in addition to the 20-year window. Figure 2.8 shows the results. For each of the estimation window lengths,  it shows how the Sharpe ratio of the portfolio changes with!. There are a few things to note.

First,  when we use 20 years of data,  shrinkage doesn't have much of an effect. The Sharpe ratio is more or less insensitive to the value of!. Shrinkage is apparently not really needed to get better estimates,  but imposing lots of shrinkage also doesn't hurt.

(Just to be clear,  this is obviously not a general conclusion that is always valid everywhere. It could well be the case that with a different set of asset classes,  or with estimates from different time periods,  there is substantial sensitivity of the out-of-sample Sharpe ratio to! with 20-year estimation windows).

Second,  if we wish to use shorter estimation windows (perhaps because we think that expected returns and covariances may have changed too much over long periods of time),  shrinkage is important. With 5-year estimation windows and no shrinkage at all (i.e.,  ! = 1 at the right-hand side of the plot) the Sharpe ratio is around zero. In other words,  the portfolio optimization has become useless. In contrast,  with! = 0,  and hence extreme shrinkage,  the 5-year estimation window approach produces Sharpe ratios that are close to the highest possible Sharpe ratios for the 10-year and 20-year estimation windows.

As it turns out,  this extreme shrinkage approach with! = 0 actually leads to an asset allocation strategy that has become quite popular in the past decade or two.

## 2.9 EXTREME FORMS OF SHRINKAGE: RISK PARITY AND 1/N

Let's examine in more detail the extreme shrinkage portfolio that results when we set
! = 0 in estimating µˆ as in (2.54),  i.e.,  with shrinkage towards a equal Sharpe ratios,  and ⌃✓ as in (2.59).

In this case,  the covariance matrix estimate uses the empirically estimated standard deviations,  while the correlations are all shrunk completely to the equicorrelation matrix C0:
⌃✓ = SC✓ 0S✓ (2.61)
Before we plug this into the optimal portfolio formula,  it's useful to note that ⌃✓ 01= S✓ 01C01 0 S✓ 01.

With! = 0,  the Sharpe ratios of all asset classes are completely shrunk to their common mean s¯¯ and so the expected excess return estimates implied by these identical Sharpe ratios are µˆ = S✓s. ¯ (2.62)
The optimal portfolio weight formula (2.18) tells us that portfolio weights are proportional to ⌃✓ 01µˆ. In this case here,

$${\widehat{\Sigma}}={\widehat{S}}C_{0}{\widehat{S}}$$
$$(2.61)$$
$${\hat{\mu}}={\widehat{S}}\iota{\bar{s}}.$$
$$\begin{array}{c}{{\widehat{\Sigma}^{-1}\hat{\mu}=\widehat{S}^{-1}C_{0}^{-1}\widehat{S}^{-1}\widehat{S}\iota\bar{s}}}\\ {{=\widehat{S}^{-1}C_{0}^{-1}\iota\bar{s}}}\\ {{\propto\widehat{S}^{-1}\iota}}\end{array}$$
⇥ S✓ 01 (2.63)

$$(2.62)$$
$$(2.63)$$

(The last equality holds because the inverse of the equicorrelation matrix has the property,  just like the equicorrelation matrix does,  that the sum of the elements in each row or column is the same. This means that when we multiply C01 0 with we get,  as a result,  a vector with equal elements that is proportional to.) So,  optimal portfolio weights will be proportional to S✓ 01. And since S01 is diagonal,  we get

$$\hat{\boldsymbol{\omega}}^{*}\propto\left(\begin{array}{c}\overline{\hat{\sigma}_{1}}\\ \frac{1}{\hat{\sigma}_{2}}\\ \ldots\\ \frac{1}{\hat{\sigma}_{N}}\end{array}\right)$$

1

![2_image_0.png](2_image_0.png)

$$(2.64)$$
11C(2.64)

![2_image_1.png](2_image_1.png)

Let's examine the weights in (2.64). They only depend on individual asset class risk as measured by standard deviations. Estimates of mean returns or correlations have completely disappeared from the optimal portfolio weight formula. This is a consequence of the extreme shrinkage we have imposed. These are the weights underlying the portfolios at the very left side of Figure 2.8 for! = 0. Basically,  this strategy expresses extreme distrust in empirical estimates of correlations and mean returns,  but considers standard deviation estimates as reliable.

Among investment practitioners,  the approach to portfolio allocation embodied in the weights in (2.64) is known as *risk parity*. It was pioneered by the hedge fund firm Bridgewater Associates in their All Weather Fund in the mid-1990s. The high Sharpe ratios for! = 0 in Figure 2.8 tells us that this approach has done well in the past few decades,  which may explain why it became popular.

The motivation investment practitioners give for this approach is typically a bit different from the way we arrived at it here. Risk parity is often presented as the idea that each asset class should be held with a weight that has each asset class make the same risk contribution to the portfolio,  or,  in other words,  it gets the same "risk budget."
Recall our decomposition of the portfolio variance in (2.22):

$$\mathrm{var}(R_{p})=\omega_{1}\underbrace{\mathrm{cov}(R_{1},      R_{p})}_{\begin{subarray}{c}\mathrm{Risk}\\ \mathrm{contribution}\\ \mathrm{of\ asset\ 1}\end{subarray}}+\omega_{2}\,      \mathrm{cov}(R_{2},      R_{p})+\ldots+\omega_{N}\,      \mathrm{cov}(R_{N},      R_{p})\tag{2.65}$$

The risk contributions of each asset class per unit of weight are represented by the covariances cov(Ri,  Rp),  and their total risk contribution to the portfolio by this covariance times the portfolio weight. With risk-parity weights proportional to 1/i and the assumption that the correlation matrix of the asset classes is an equicorrelation matrix,  one can show that ⇢i cov(Ri,  Rp) is then the same for each asset class—i.e.,  each asset

class accounts for the same share of total portfolio risk This is what people mean when they say that a risk parity strategy then gives each asset class an equal *risk budget* for its contribution to portfolio risk (and keep in mind that this statement is true only if the equicorrelation assumption holds).

Now,  conceptually,  it's not clear why equal risk budgets for each asset class would be desirable. In contrast,  our shrinkage approach gives a clear motivation: if we strongly distrust mean return and correlation estimates due to estimation error,  then meanvariance optimization implies a risk parity strategy.

![3_image_0.png](3_image_0.png)

Figure 2.9 shows how risk parity portfolio weights looked like if we implemented this approach in the past few decades,  using 10 years of backward looking data to estimate the asset class return standard deviations. Notice the different scale of the y-axis compared with Figure 2.7.

Also,  note that I am plotting the risky portfolio weights in (2.18) that are scaled to sum up to one. We will leave aside for now the question of how to allocate between short-term risk-free assets (proxied for by T-bills) and the risky asset portfolio.

In several ways,  these portfolio weights have desirable attributes. There are no huge outliers asking for huge amounts of leverage (portfolio weights in excess of 1.0) or short positions (portfolio weights < 0) that portfolio managers are often reluctant to take. As we saw in Figure 2.7,  this can be very different for optimal weights without shrinkage when a relatively short estimation window of 10 years is used to estimate the inputs for the optimal portfolio weight formula (that make the calculation of the optimal weights far more cumbersome). One way to fix this problem (for a manager who is reluctant to take on leverage and short positions) is to impose additional constraints on the meanvariance optimization problem. But the risk parity strategy delivers moderate weights without having to impose such constraints.

Figure 2.9 also highlights one property that has generated criticism of the risk parity approach: its heavy loading on bonds. As the figure shows,  the three bond asset classes,  U.S. Treasury bonds,  international bonds,  and corporate bonds account for a large share of the total portfolio. The concern is that the strategy has benefitted from the secular decline in interest rates (which lead to high returns for holders of long-term bonds) that took place during the past decades. The performance of a strategy with a high bond exposure in the future may look much less appealing.

Another problem that is useful to keep in mind concerns the initial menu of asset classes. The mean-variance optimization approach that takes into account correlations is not as sensitive to the selection of the asset class menu than the risky parity approach.

For example,  if we add another asset class to the menu that is very similar in terms of mean return and highly correlated with an asset class that we already have in the menu,  the mean-variance optimal portfolio will tend to reduce the share of the one we already have in the menu and give some of this share to the new asset class,  leaving other asset classes largely unaffected.

In contrast,  the risk parity approach reduces the weight on all other asset classes equally when we bring in a new asset class,  even if the new asset class is very similar to one we already have in the menu,  and not to the others.

The bottom line from this is that the equicorrelation prior should be somewhat plausible for the selected menu of asset classes for the risky parity approach to make sense. Having two asset classes in there that are clearly much more highly correlated than others could lead to excessive weight for these two asset classes.

##

Now consider an even more extreme form of distrust in the data. Suppose we don't believe that historical data on standard deviations are useful for forecasting future volatility. We therefore feel that we can't distinguish between asset risk levels and we impose extreme shrinkage not only on mean returns and correlations,  but also standard deviations: we assume they are the same 1 = 2 = … = N. Then the portfolio weights for all asset classes are exactly equal and the risky asset portfolio weights are

$$\hat{\omega}^{*}=\begin{pmatrix}\frac{1}{N}\\ \frac{1}{N}\\ \dots\\ \frac{1}{N}\end{pmatrix}$$

1

$$(2.66)$$
11C(2.66)
where N is the number of asset classes. This portfolio formation strategy is called,  sensibly,  a 1/N strategy. It uses no inputs about expected returns and risks whatsoever.

![5_image_0.png](5_image_0.png)

This may seem like an extremely unsophisticated asset allocation strategy. And in some sense it is. But look at Figure 2.10! The Figure shows the out-of-sample Sharpe ratios of four strategies: (i) no shrinkage at all—this is the portfolio of the 10-year line

 $\text{(C)Stet}$.
.

for! = 1 in Figure 2.8; (ii) optimal shrinkage of! = 0.05 based on the maximum of the line for 10-year estimation windows in Figure 2.8; (iii) risk parity; (iv) 1/N.

Surprisingly,  1/N does quite well! Not as good as optimal shrinkage and risk parity,  but still much better than in the no-shrinkage case. There is actually a fairly large body of research at this point showing that the 1/N strategy of forming a diversified portfolio does quite well in a number of settings.

As for the risk parity approach,  the selection of the menu of assets is very important.

By adding lots of very similar,  highly correlated asset classes,  a 1/N portfolio would become poorly diversified and its Sharpe ratio would suffer. Part of the success of 1/N
in our analysis here comes from the fact that we started with a good selection of asset classes that span a lot of different types of risks.

But one conclusion that we can tentatively draw from the success of 1/N in this exercise is that our inputs to the optimal portfolio weight formula are perhaps not good enough yet. For example,  just plugging in historical estimates of mean excess returns from the past 10 years may be a poor way of forecasting future excess returns.

Much of the rest of the course will be devoted to getting a better understanding of how to forecast risk and return.