---
title: Lecture 7-Risk and Return of Bonds
tags:
  - default_free_bonds
  - fixed_income
  - treasury_bonds
  - yield_to_maturity
  - zero_coupon_bonds
aliases:
  - Lecture 7
  - Nominal Bonds
  - Risk and Return
key_concepts:
  - Default-free bonds
  - Fixed-income instruments
  - U.S. Treasury bonds
  - Yield to maturity
  - Zero-coupon bonds
---

# Lecture 7-Risk and Return of Bonds

Our goal in this session is to better understand the risk and return properties of fixedincome instruments such as U.S. Treasury bonds. ${ }^{1}$ For now,  we focus on default-free bonds,  i.e.,  we assume that the cash flows (coupons and principal) that the bonds promise to pay will be paid for sure. More precisely,  we will for now focus on nominal default-free bonds,  which are bonds that promise a fixed stream of dollar cash flows that are not adjusted for inflation. For example,  if you buy a nominal bond default-free bond today that matures 10 years from now,  you will know for sure how many dollars of principal payment you will get back at the maturity date,  but you don't know the purchasing power this dollar cash flow will have at the maturity date.

In earlier lectures,  we referred to such bonds loosely as "risk-free" and we did so because we focused on the absence of cash-flow risk in such bonds. But as will become clear,  bonds that are free of cash-flow risks are still exposed to the risks of changing interest rates and inflation. So now that we focus on bonds,  we should be more precise and use the label default-free.

For now,  we will assume that U.S. Treasury bonds qualify as default-free. We will look at the issue of sovereign default risk in the next lecture.

### [[Lecture 7-Risk and Return of Bonds#7.1 Zero-coupon yield curve|7.1 Zero-Coupon Yield Curve]]
U.S. Treasury bonds pay a stream of semi-annual coupons and a final principal payment at maturity. For the purposes of analyzing bonds,  it would be much easier to have a security with just one single cash flow,  i.e.,  a zero-coupon bond that pays only a final

[^29]principal payment and nothing else. Fortunately,  we can convert the prices and yields of regular U.S. Treasury bonds into zero-coupon bond prices and yields. We won't go into the details of how to do this,  but basically one views a Treasury bond as a portfolio of zero-coupon bonds: one for the first coupon payment,  one for the second,  …,  and one for the final principal payment. The price of the Treasury bond then must be,  based on no-arbitrage principles,  the sum of the prices of these individual zero-coupon bonds. If at every point in time one observes prices of many Treasury bonds with different maturities,  one can search for zero-coupon bond prices such that,  when they are summed up to to represent each Treasury bond as a portfolio of zero-coupon bonds,  they reproduce the observed prices of Treasury bonds.

So let's say someone has done this for us. We therefore observe at time $t$ the prices $P_{n,             t}$ of zero-coupon bonds with maturity in $n$ years and which make a single payment of $1$ at maturity. As a few lectures ago,  when we analyzed how the stock market pricedividend ratio relates to future cash flow growth and future returns,  it was convenient to work with $\log$ prices $p_{n,      t}=\log \left(P_{n,      t}\right)$. As we will see now,  doing so is actually particularly convenient for analyzing bonds. The absence of cash-flow risk makes the relationship between current log prices and future log returns particularly simple and we won't need the linearization approximation that we used for stock market valuation.

When financial market participants discuss bond prices,  they often do so not in terms of prices,  but in terms of yield,  which is just a transformation of the price. The yield-to-maturity (or often just "yield") of a zero-coupon bond is defined as

$$

\begin{equation*}

Y_{n,             t}=\left(\frac{1}{P_{n,             t}}\right)^{\frac{1}{n}}-1 \tag{7.1}

\end{equation*}

$$

So yields move in the inverse direction from prices. The $\log$ yield-to-maturity is $y_{n,             t}=$ $\log \left(1+Y_{n,             t}\right)$,  i.e.,

$$

\begin{equation*}

y_{n,             t}=-\frac{1}{n} p_{n,             t} \tag{7.2}

\end{equation*}

$$

For zero-coupon bonds,  the calculation of log returns is really simple. It's just the change in log price. For example,  the log return in year $t$ of a bond that was an $n$-year bond at the end of year $t-1$ and therefore is an $n-1$-year bond at the end of year $t$ is

$$

\begin{equation*}

r_{n,             t}=p_{n-1,             t}-p_{n,             t-1} \tag{7.3}

\end{equation*}

$$

In what follows,  to reduce clutter,  I will often just write yields,  prices,  and returns for $\log$ yields,  $\log$ prices,  and log returns of bonds.

If we plot yields $y_{n,             t}$ as a function of maturity $n$ we obtain the [[Lecture 7-Risk and Return of Bonds#7.1 Zero-coupon yield curve|zero-coupon yield curve]]. As an example,  Figure 7.1 presents two snapshots of the yield curve in April 2021

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-233.jpg?height=984&width=1199&top_left_y=294&top_left_x=474)

Figure 7.1: Zero-coupon yields extracted from U.S. Treasury bond prices

and June 2023. ${ }^{2}$ We see that the yield curve can change shape. It was upward sloping in April 2021,  with long-term bonds having higher yields than short-term bonds,  and it was downward sloping in June 2023. Much of what we do in this lecture is to figure out what we can learn from the shape of the yield curve. There is a lot of information about future economic growth,  inflation and [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] baked into the yield curve.

### 7.2 Present-value relations for bonds

But first we focus on what yields tell us about the future returns for an investor holding these bonds. Consider a zero-coupon bond that has,  at time $t,             n$ years left until maturity. Now consider the return of this bond in the last year before it matures,  i.e.,  in year $t+n$. It pays off $1$ at $t+n$ and costs $P_{1,      t+n-1}$ one year earlier,  so the return earned from holding

[^30]this bond during this last year is

$$\begin{equation*}
1+R_{1,  t+n}=1 / P_{1,  t+n-1} \tag{7.4}
\end{equation*}$$
Taking logs,

$$

\begin{equation*}

r_{1,             t+n}=-p_{1,             t+n-1} \tag{7.5}

\end{equation*}

$$

Doing a similar calculation two,  three,  and more years before maturity,

$$

\begin{align*}

& r_{2,             t+n-1}=-p_{2,             t+n-2}+p_{1,             t+n-1}  \tag{7.6}\\

& r_{3,             t+n-2}=-p_{3,             t+n-3}+p_{2,             t+n-2} \cdots \tag{7.7}

\end{align*}

$$

Summing up all these returns and rearranging,  we get

$$

\begin{equation*}

p_{n,             t}=-\sum_{i=1}^{n} r_{n-i+1,             t+i} \tag{7.8}

\end{equation*}

$$

Thus,  if the price on the left-hand side of this equation is low today,  future returns on the right-hand side of this equation must be high,  and vice versa.

Recall from our earlier discussion of the stock market price-dividend ratio that $p_{t}-d_{t}$ variation could reflect variation in future expected cash flow growth or future returns. Since we are looking at default-free bonds here,  there is no cash flow uncertainty. The single cash flow promised by a zero-coupon bond is certain. Therefore,  a change in price cannot reflect changes in cash flow growth expectations. Only the return part remains and the present-value identity is very simple: prices today are tightly linked to returns in the future.

Substituting (7.8) into (7.2) helps us to interpret the meaning of the bond yield:

$$

\begin{equation*}

y_{n,             t}=-\frac{1}{n} p_{n,             t}=\frac{1}{n} \sum_{i=1}^{n} r_{n-i+1,             t+i} \tag{7.9}

\end{equation*}

$$

The yield tells us the average return that we will be getting for sure if we hold the bond to maturity. Of course,  if the $n$-year bond is held for a time shorter than $n$ years,  the holding period return will be uncertain.

The identity (7.9) also tells us something about the time-series properties of bond returns. Period-by-period returns can be subject to random shocks,  but their mean over $n$ periods is fixed based on the price observable at $t$. Therefore,  returns must be negatively autocorrelated! For example,  consider a two-year bond. If the log return in period $t+1$ is higher than the bond's time- $t$ yield $y_{2,             t}$,  then the log return in period $t+2$ must be lower than $y_{2,             t}$ so that the mean of the two log returns still adds up to

$y_{2,             t}$. So mechanically,  it must be the case that returns in the two periods are negatively correlated.

More precisely,  (7.9) applied to a two-year zero-coupon bond tells us that

$$

y_{2,             t}=\frac{1}{2}\left(r_{2,             t+1}+r_{1,             t+2}\right)

$$

which we can solve for

$$

r_{1,             t+2}=2 y_{2,             t}-r_{2,             t+1}

$$

Therefore,  for a given yield $y_{2,             t}$ at time $t$,  we know that the future return $r_{1,             t+2}$ is perfectly negatively correlated with $r_{2,             t+1}$. For example,  if the return $r_{2,             t+1}$ in period $t+1$ is one percentage point higher,  then the return $r_{1,             t+2}$ in period $t+2$ will be one percentage point lower.

This is very important for a long-term investor. Imagine an investor with a 10-year horizon who just purchased a 10-year zero-coupon bond. It's possible that this bond falls in price tomorrow. This may seem like bad news for the investor. But there is good news at the same time: The returns of the bond will then for sure be higher going forward from tomorrow. Thus,  evaluating a bond investment in a [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] framework in which one assumes IID returns may not be a good idea. The long-run risk of long-term bonds is a lot lower than the short-run risk of long-term bonds.

### 7.3 Bond yield factors

To understand the risk and return properties of bonds,  we need to first figure out the main drivers of changes in bond yields over time. Let's first get a visual impression. Figure 7.2 shows the time-series of short- (1yr),  mid- (5yr),  and long-maturity (10yr) zero-coupon yields over the past 50 years. The two most immediate take-aways are that there is: (i) large time-variation in the level of yields,  part of it via slow trends,  up towards the 1980s and down ever since,  part via [[Week 3 Cyclical Industries (and Advanced Forecasting)|cyclical]] variation that tends to mean revert over horizons of a few years; (ii) time-variation in the slope of the yield curve,  where short-term yields are most of the time lower than long-term yields,  but sometimes they are close to,  or even a little higher than long-term yields.

In fact,  the yield curve can be quite neatly summarized by three factors that capture almost all the variation in yields over time. We form the following three linear

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-236.jpg?height=990&width=1272&top_left_y=364&top_left_x=359)

Figure 7.2: History of zero-coupon yields extracted from U.S. Treasury bond prices

combinations of yields:

$$

\begin{align*}

\text { level }_{t} & =\frac{1}{10} \sum_{n=1}^{10} y_{n,             t} \\

\text { slope }_{t} & =y_{10,             t}-y_{1,             t} \\

\text { curvature }_{t} & =y_{5,             t}-\frac{y_{1,             t}+y_{10,             t}}{2} . \tag{7.10}

\end{align*}

$$

The labels level,  slope,  and curvature should be self-explanatory. We can now check how movements in bond yields can be reduced to movements in these three factors by running a regression of yield changes,  $\Delta y_{n,             t}=y_{n,             t}-y_{n,             t-1}$,  on contemporaneous changes in these yield factors $\Delta$ level $_{t}=$ level $_{t}-$ level $_{t-1},             \Delta$ slope $_{t}=$ slope $_{t}-$ slope $_{t-1}$,  $\Delta$ curvature $_{t}-$ curvature $_{t-1}$. The coefficients $b_{n},             c_{n},             d_{n}$ in this regression

$$

\begin{equation*}

\Delta y_{n,             t}=a+b_{n} \Delta \text { level }_{t}+c_{n} \Delta \text { slope }_{t}+d_{n} \Delta \text { curvature }_{t}+e_{t} \tag{7.11}

\end{equation*}

$$

capture how strongly the yield of a bond with time-to-maturity $n$ is exposed to movements in the three yield curve factors factors.

Table 7.1: Explanatory power of level,  slope,  and curvature factors for daily bond yield changes

 ![500](CleanShot%202024-10-24%20-003126@2x.png)
Table 7.1 shows the results from running these regressions with daily yield changes and data from the last 50 years. The first block of rows shows the intercept and slope coefficient estimates and the $R^{2}$ from the regressions on all three factors. There are three things to note. First,  the slope coefficient of the level factor is extremely close to 1.0 for bonds at all maturities. This means that when the level of the yield curve shifts,  all bonds tend to move in lockstep by the same magnitude (plus possibly some movement that may be uncorrelated with the level). Second,  short maturity bonds have negative coefficients on the slope factor while long-term bonds have positive coefficients,  which should make intuitive sense: When the slope steepens,  short-term yields decline relative to long-term yields. Third,  the $R^{2}$ is extremely close to $100/%. This means that the three factors explain almost all the day-to-day variation in yields on these 10 maturities. So for all practical purposes,        we can focus our thinking regarding the drivers of bond yields on interpreting just these three factors. Moreover,        the risks of a bond portfolio then must be driven almost entirely by these three factors. So if we want to assess the riskiness of a bond portfolio,        we can focus our attention on the portfolio's exposure to these three factors. ${ }^{3}$

The rows below show the $R^{2}$ (coefficient estimates omitted) for specifications where I only use level and slope or slope only. The contribution of the curvature factor turns out to be very small. Just level and slope alone explain $96/% or more of the variation

[^31]in daily yield changes. And just the level alone gets to around $90/% at some maturities; only at the shorter maturities it's substantially lower. So we can actually focus on just two factors: level and slope to understand most of the variation of the yield curve and its implications.

To model the risk of a bond,  or of a portfolio of bonds,  we would like to know the sensitivity of bond returns to the level,  slope,  and curvature factors. We can get these sensitivities by regressing daily bond returns on daily changes in the factors.

$$

r_{n,             t}=a+b_{n} \Delta \text { level }_{t}+c_{n} \Delta \text { slope }_{t}+d_{n} \Delta \text { curvature }_{t}+e_{t}

$$

The results we get from these regressions will be closely related to the results we obtained with yield changes as the dependent variable,  because at daily measurement frequency,  $r_{n,             t} \approx-n \Delta y_{n,             t}$. Therefore,  the regression coefficients when we have returns as dependent variable are those from earlier in Table 7.1,  but multiplied by the maturity of the bond $n$ and with flipped sign. Figure 7.3 plots the coefficients for bonds with maturities from one to 10 years.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-238.jpg?height=999&width=1359&top_left_y=1189&top_left_x=340)

Figure 7.3: Coefficients in regression of daily bond returns on daily changes in level,  slope,  and curvature factors

As the figure shows,  long-term bond returns have a much more negative $b_{n}$ coefficient. This means that they are more sensitive to movements in the level of the yield curve. For example,  they are much more negatively affected when the level of the yield curve shifts up. This is natural: If the discount rate moves up at all horizons (as it is a level shift),  then this affects an asset that pays a cash flow in the distant future more than an asset that pays a cash flow in the near-term.

The coefficient in the regressions with returns as dependent variable are like "betas" of the bond with maturity $n$ with respect to the three bond risk factors. Once we have these coefficients,  we can answer questions like: What is effect on the return of a bond if the yield curve slope increases by 10bp? ${ }^{4}$ The answer is 10 bp times the estimate of the coefficient $c_{n}$.

The coefficient $b_{n}$ in the regression estimates the (negative of the) duration of the bond. The duration of a bond measures the negative of the change in log price of a bond induced by a change in the $\log$ yield,  i.e.,  $-\partial p_{n,             t} / \partial y_{n,             t}$. For a zero-coupon bond,  duration is always equal to time until maturity,  i.e.,  $-\partial p_{n,             t} / \partial y_{n,             t}=n$. This is what Figure 7.3 shows: The $b_{n}$ coefficients are equal to the negative of maturity of the bond.

Since level,  slope,  and curvature factors explain almost all movement in yields across the maturity spectrum,  it is also natural that the most common yield curve trades used by professional investors are effectively taking positions in these three factors. Figure 7.4 illustrates these trades. An investor who anticipates that the yield curve will shift down in a parallel shift can profit from this by buying bonds across the maturity spectrum,  which means essentially buying the level factor. This is a directional bet on a shift in the entire yield curve. An investor who anticipates that the yield curve will steepen can take advantage of this with a yield curve trade known as a steepener. This trade takes a long position in short-term bonds and a short position in long-term bonds,  which is essentially a short position in the slope factor. An investor anticipating that the yield curve will become more concave will sell bonds of medium maturity and go long in bonds with short and long maturity,  which is essentially a short position in the curvature factor. This is known as a butterfly trade.

### [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|7.4 Expectations Hypothesis]]
We can get some understanding of how bond prices are determined in market equilibrium,  and how the shape of the yield curve arises,  by considering a bond investment problem. Since most yield curve movements are driven by level and slope movements,  we can

[^32] ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-240.jpg?height=1007&width=1465&top_left_y=315&top_left_x=295)

Figure 7.4: Yield curve trades

simplify things by assuming there are just two types of bonds: a short term bond,  let's say with one period to maturity,  and a long-term bond,  let's say with two periods to maturity. Investors have a choice whether to invest in one or the other,  or a combination of them.

More specifically,  suppose investors are considering an investment with a two-year horizon. They face the following alternatives.

First,  invest in the two-year bond,  which delivers a two-year annualized log return from $t$ to $t+2$ equal to the bond's yield $y_{t,             2}$. Since $y_{t,             2}$ is known at time $t$,  the return is known for sure,  there is no uncertainty.

Second,  invest in the one-year bond and roll over the investment into a new one-year bond once the first one matures. This yields the annualized log return

$$

\begin{equation*}

\frac{1}{2}\left(y_{1,             t}+y_{1,             t+1}\right) \tag{7.12}

\end{equation*}

$$

The short-term bond yield $y_{1,             t+1}$ is not known yet at $t$ and hence uncertain.

For the bond market to be in equilibrium,  bond prices must adjust such that neither one of this strategy is more attractive to investors than the other (otherwise the bond market would not be in equilibrium.) Investors should be indifferent between the two strategies. But one strategy has a certain payoff,  the other one has an uncertain payoff. How can we compare them? We need a few more assumptions. Let's allow for the possibility that investors demand a risk premium $\lambda_{2}$ (not necessarily positive) for holding two-year bonds and assume that this risk premium is constant. This means that the expected return on the long-term bond that investors require in equilibrium should equal to the expected return from rolling over the short-term bond plus $\lambda_{2}$. As an approximation,  let's ignore the differences between expected simple and expected log returns and let's set equal the expected log returns of the strategies,  with an adjustment for the risk premium $\lambda_{2}$ :

$$

\begin{equation*}

y_{2,             t}=\lambda_{2}+\frac{1}{2}\left(y_{1,             t}+\mathbb{E}_{t}\left[y_{1,             t+1}\right]\right) \tag{7.13}

\end{equation*}

$$

If this holds,  investors are indifferent between the two strategies. ${ }^{5}$

So now we have a theory of the yield curve! To see this,  subtract $y_{1,             t}$ on both sides of (7.13). We get

$$

\begin{equation*}

y_{2,             t}-y_{1,             t}=\lambda_{2}+\frac{1}{2}\left(\mathbb{E}_{t}\left[y_{1,             t+1}\right]-y_{1,             t}\right) \tag{7.14}

\end{equation*}

$$

This tells us that if the slope of the yield curve is high (left-hand side) it must be the case (on the right-hand side) that either the risk premium $\lambda_{2}$ is high,  or that investors expect future short-term yields to be higher than current short-term yields. Moreover,  if $\lambda_{2}$ is truly constant,  then all movements over time in the slope are linked to movements in expected future short-term yields relative to current short-term yields. This theory is known as the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] of the yield curve.

More generally,  for a bond maturing in $n$ periods from now,  the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] says that its yield reflects expectations of short-term yields over the next $n$ periods,

$$

\begin{equation*}

y_{n,             t}=\lambda_{n}+\frac{1}{n} \sum_{i=1}^{n} \mathbb{E}_{t}\left[y_{1,             t+i-1}\right] \tag{7.15}

\end{equation*}

$$

[^33]where $\lambda_{n}$ is a maturity-specific risk premium. The yield curve slope then is
$$

\begin{equation*}

y_{n,      t}-y_{1,      t}=\lambda_{n}+\frac{1}{n} \sum_{i=1}^{n}\left(\mathbb{E}_{t}\left[y_{1,      t+i-1}\right]-y_{1,      t}\right) \tag{7.16}

\end{equation*}

$$
So according to the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  the slope of the yield curve should tell us where short-term yields are expected to go. A more strongly upward sloping curve should forecast future short-term yields going up relative to the current short-term yield. Eyeballing Figure 7.2 we see that at least roughly,  there is some truth to this prediction.

For example,  in the early 1990s and early 2000s the yield curve was steep and this was followed by rises in short-term yields. One exception are the years following the financial crisis from 2009 onwards when the yield curve was strongly upward sloping,  but short-term yields stayed low.

Around 1980,  1990,  2000,  2008 the yield curve was flat,  or even a bit inverted (by which we mean short-term yields > long-term yields) and each of these episodes was followed by a sharp fall in short-term yields.

We also see in Figure 7.2 that inversions are rare. Most of the time,  the yield curve is upward sloping. By taking unconditional expectations of (7.16) we get

$$

\begin{equation*}

\mathbb{E}\left[y_{n,             t}-y_{1,             t}\right]=\lambda_{n} \tag{7.17}

\end{equation*}

$$

and so the on average positive slope (left-hand side) indicates a positive risk premium for long-term bonds $\lambda_{n}>0$ (right-hand side).

For now,  we'll use the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] as guidance on how to interpret yield curve movements. Later,  we'll look at empirical violations of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] and what they may mean for investment policy.

### 7.5 Movements in the level of short-term interest rates

The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] tells us that long-term bond yields move because expectations of future short-term bond yields ( $=$ short-term interest rates) move. This means that we can think of the risks that long-term bond investors face as a risk of changing expectations of future short-term interest rates. To understand this risk,  we therefore need to get an understanding of why expectations of future short-term interest rates change. And this brings us to [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] and central banks.

In the U.S.,  the Federal Reserve ("Fed") normally conducts [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] by setting a target for the federal funds rate. The federal funds market is an interbank market in which banks lend to each other. Basically,  banks all have accounts at the Fed and they can move deposits in these accounts (called reserves) from one bank to another to settle interbank flows that arise from their daily deposit,  lending,  and trading activity. To manage their daily inand outflows due to receiving deposits from customers,  deposit withdrawals,  lending flows,  etc.,  banks want to keep a certain minimum level of reserves in their account to make sure they have enough liquidity to settle all of these flows. If a bank finds itself short of liquidity,  they will be active in the federal funds market to borrow reserves from other banks; if they anticipate having a surplus of liquidity,  they will be active looking to lend in the federal funds market. Loans in the federal funds market are overnight,  i.e.,  they have one-day maturity. The interest rate that clears the market (so that supply of reserves by banks willing to lend reserves equals the demand for borrowing reserves) is called federal funds rate.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-243.jpg?height=945&width=1351&top_left_y=1048&top_left_x=406)

Figure 7.5: Time-series of the federal funds rate

Figure 7.5 shows the time-series of the daily federal funds rate. Absence of arbitrage then enforces that other short-term (or money-market) interest rates,  such as overnight repo rates,  offshore dollar borrowing and lending rates,  high-grade [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] rates,  stay close to the federal funds rate.

How can the Federal Reserve influence the level of the federal funds rate? For several decades prior to the Global Financial Crisis (GFC) in 2008-09,  the Fed did this via openmarket operations in which the Fed would purchases Treasury bills from banks or sell them to banks. If the Fed buys T-bills from a bank,  then to pay for these T-bills,  it simply credits the bank's reserve account at the Fed with more reserves (which is sometimes described as creating money,  in the form of reserves,  out of "thin air"). As a consequence,  new reserves are created out of thin air. If the Fed sells T-bills,  the same thing happens in reverse and reserves are destroyed. By creating or destroying reserves in this way,  the Fed can therefore control the supply of reserves held by banks in aggregate. By lowering the supply of reserves,  the Fed can make banks more "desperate" for getting enough reserves to satisfy their liquidity needs. As a consequence,  they will try to borrow more,  and are willing to do so at higher rates. Hence,  the [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]]  rises. By raising supply,  the Fed can make banks flush with liquidity,  with little need to borrow in the federal funds market,  and hence the federal funds rate falls. Using this mechanism,  the Fed could get the federal funds rate to stay close to the federal funds rate target set by the Federal Open Market Committee (FOMC),  the monetary-policy committee at the Fed (which meets about every six weeks).

Moving the federal funds rate usually required adjustments to the level of reserves that were quite small (say,  relative to the total size of the daily transaction flows that go through banks' accounts at the Fed). The reason is that deposits at the Fed earned zero interest before the GFC. So banks were trying to avoid holding more reserves than needed for their liquidity needs and a few tens of billions of dollars for the banking sector as a whole was sufficient as a liquidity cushion. If the Fed then pulled out a few billion of reserves via open-market operations,  this had a big effect on the federal funds rate.

But in the GFC,  methods of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] implementation changed. As Figure 7.5 shows,  the federal funds rate basically hit zero during this time and stayed there for years. Further economic stimulus through lowering the federal funds rate was not possible. The Fed therefore looked for alternative approaches that could affect long-term bond yields (that had not yet hit zero). While in normal open market operations the Fed would only transact in T-bills (which have short maturities up to a year),  in the GFC the Fed started a program called quantitative easing in which the Fed purchased longer-dated Treasury bonds and also mortgage-backed securities in order bring down long-term bond yields. While normal market operations would be done in tiny quantities,  and the total supply of reserves that banks held was small,  quantitative easing was done in massive quantities which lead to a huge expansion in the reserve balances that banks held at the Fed.

Figure 7.6 shows the reserve balances. They reached a peak of close to $3$ trillion around 2015,  and then an all-time high (so far) in 2020 due to a further round of

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-245.jpg?height=936&width=1349&top_left_y=302&top_left_x=407)

Figure 7.6: Total reserves of depository institutions

quantitative easing during the COVID pandemic.

Very recently,  the Fed went back to targeting a federal funds rate substantially above zero. Pre-GFC,  the Fed could have achieved a federal funds rate in line with this target by removing a few billion dollars of reserves from the system (when the total supply of reserves was only a few tens of billions). This would have been enough to make banks scramble for reserves by attempting to borrow more,  leading to upward pressure on the federal funds rate. But now,  banks sitting on trillions of dollars in reserves are basically completely saturated with reserves. They have way more reserves than they could ever need for a liquidity cushion for their daily transaction flows due to their deposit and lending flows. So even if the Fed pulled hundreds of billions of dollars of reserves out from the system by selling an equivalent amount of Treasury securities,  this would do little to get the federal funds rate above zero.

For this reason,  the Fed needed a new tool: Interest on reserve balances (IORB). The Fed started paying IORB on banks' reserve deposits. By raising the level of IORB,  the Fed can put a floor under the federal funds rate. For example,  if the Fed pays banks $2/% interest on reserve deposits,        no bank would have an incentive to lend reserves to another bank at less than $2/%. Moreover,  since banks are sitting on plenty of reserves,

there is no reason why the federal funds rate should rise above $2/% in this case. So the federal funds rate should be equal to $2/%.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-246.jpg?height=933&width=1331&top_left_y=444&top_left_x=359)

Figure 7.7: Interest on reserve balances,  overnight repurchase agreement rate,  and effective federal funds rate

Figure 7.7 shows IORB (red line) and the effective federal funds rate (green line) during the recent rate-hiking cycle that started in early 2022. Surprisingly,  the federal funds rate is always a bit below the IORB. How is this possible? The reason is that there are some institutions (such as money-market mutual funds and government-sponsored enterprises such as the mortgage giants Fannie Mae and Freddie Mac) that participate in the federal funds market,  but do not have access to deposits at the Fed that earn IORB. As a consequence,  the floor that IORB puts on the federal funds rate is leaky.

For this reason,  the Fed added another facility called the Overnight Reverse Repo Facility (ON RRP). The details of how this works don't matter for our purposes. The essence is that the facility serves as a way for federal funds market participants that do not have reserve accounts at the Fed to effectively deposit funds at the Fed. These deposits are remunerated at the ON RRP rate which the Fed sets slightly below the IORB. And the ON RRP rate then serves as a floor for the federal funds rate that is not leaky. As Figure 7.7 shows,  the Fed was able to raise the [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]]  without breaching this floor by simultaneously raising the IORB and ON RRP rates in lockstep.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-247.jpg?height=1042&width=1489&top_left_y=306&top_left_x=340)

Figure 7.8: 3-month Treasury bill yields and the federal funds rate target

So now that we understand the mechanics of how the Fed influences short-term interest rates,  we can turn back to the question of how and when expectations of future short-term interest rates change (which should then in turn change the prices of longterm bonds). Figure 7.8 shows an example that nicely visualizes the important role of expectations about future [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] decisions for yields of three-month T-bills and two-year Treasury securities. During the period shown in the plot,  the Fed raised the federal funds rate target several times in steps ranging from 25 bp to 75 bp .

Now imagine you are managing a money-market portfolio for a financial institution and you are contemplating an investment in 3-month T-Bills a few weeks before an upcoming FOMC meeting. Based on speeches of Fed officials and the latest economic data,  you are convinced that at this upcoming meeting,  the FOMC will raise the [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]]  target by 50 bp . You are wondering whether you are better off putting money into the Fed's ON RRP facility where it will earn a few bp less than the federal funds rate or in a 3-month T-bill. If you are confident that the ON RRP rate will be raised at the upcoming FOMC meeting,  this makes the ON RRP alternative more attractive in comparison with the T-bill. If you buy a T-bill today,  its yield will be fixed for the next

three months,  but if you deposit money in the ON RRP facility,  you anticipate that the interest rate you earn will go up in a few weeks,  before the T-bill matures.

In equilibrium,  the current yield of the T-bill should have already risen (and hence the price of the T-bill fallen) sufficiently so that you are indifferent between the two alternatives. According to the logic of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  any time a piece of news comes out that makes it more likely that the Fed will raise the federal funds rate target during the next three months,  the yield of the 3 -month T-bill should rise in anticipation of the Fed's rate hikes.

The T-bill yield series in Figure 7.8 shows clear signs of such anticipation. For many FOMC meeting dates at which rates were raised,  T-bill yields already anticipated the rise in rates weeks before the FOMC meeting took place. By the time the FOMC's decision was announced and the [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]]  target raised,  the decision was already largely fully priced into T-bill yields and there is very little remaining reaction of T-bill yields on these FOMC meeting dates. In one case,  the June 14-15,  2022 FOMC meeting,  the rise in T-bill yields was concentrated a few days before the FOMC meeting. News reports from the days before this meeting suggest that investors became increasingly convinced that the Fed would raise rates by 75 bp in the upcoming meeting rather than the previously expected 50bp hike.

A similar mechanism is at work for longer-term Treasury securities. While the threemonth T-bill reflects expectations of the federal funds rate over the next three months,  the price of,  say,  a 2-year bond reflects expectations of the federal funds rate over the next two years. The plot of two-year yields in Figure 7.8 illustrates this nicely. For example,  2-year yields were already rising in late 2021 when investors started pricing in expectations of interest-rate hikes by the Fed during the coming two years. But these interest rate hikes were expected to start only after the first quarter of 2022,  which is why 3 -month T-bill yields at the end of 2021 did not react yet.

The fact that two-year yields in February 2024 are substantially lower than the federal funds rate suggests that the market expects several rate cuts by the Fed during the two years ahead.

The important role of the expected short-term interest rate path for bond pricing is why financial market participants devote a lot of effort into predicting the next [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] moves of the FOMC,  not only at the next meeting,  but also at many future meetings of the FOMC.

The fact that 3-month T-bill and 2-year Treasury yield movements in Figure 7.8 anticipate future federal funds rate rises is also a good illustration why a certain type of somewhat common bond market commentary is not good advice. Commentators occasionally express the view that if the Fed is likely to raise interest rates in the future,

long-term bonds are not a good investment because when the rate rises get implemented in the future,  long-term bond prices will fall at that point. But the market doesn't work in this way. If bond market investors are already aware that rate rises are likely coming,  bond prices already reflect these expectations of future interest rate hikes. At that time it is therefore already too late to sell long-term bonds.

To get a more precise statement of this,  start with the return definition $r_{n,             t+1}=$ $p_{n-1,             t+1}-p_{n,             t}$ and then substitute $p_{n,             t}=-n y_{n,             t}$ and the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] (7.15). We get

$$

\begin{equation*}

r_{n,             t+1}=y_{1,             t}+n \lambda_{n}-(n-1) \lambda_{n-1}-\left(\mathbb{E}_{t+1}-\mathbb{E}_{t}\right) \sum_{i=1}^{n-1} y_{1,             t+i} \tag{7.18}

\end{equation*}

$$

The bond return has three components: (i) the short-term yield; (ii) a risk premium; (iii) unexpected changes in expectations of future short-term yields,  calculated as the expectation at time $t+1$ of future short-term rates minus the expectation at time $t$. If short-term interest rates follow exactly the path that was expected at $t$ and so the same path is still expected at $t+1$,  then term (iii) is zero and a long-term bond investment earns the short-term yield $y_{1,             t}$ plus the risk premium $n \lambda_{n}-(n-1) \lambda_{n-1}$. Now let's take expectations 7.18 to calculate the expected return and subtract $y_{1,             t}$ on both sides:

$$

\begin{equation*}

\mathbb{E}_{t}\left[r_{n,             t+1}\right]-y_{1,             t}=n \lambda_{n}-(n-1) \lambda_{n-1} \tag{7.19}

\end{equation*}

$$

Whether rates are expected to increase or decrease in the future has no effect on the expected bond return. The reason is that bond prices at time $t$ already reflect this expected path of future short-term interest rate. So if everyone knows that the Fed will raise rates,  it's already too late to exit long-term bonds! Such an exit can be profitable only if we can figure out that the Fed will likely raise rates before other investors figure this out and before this information is priced into bond prices.

### 7.6 Asset price reactions to [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] surprises

By changing expectations about the path of future short-term interest rates,  [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] can affect the prices of a wide variety of assets. Through the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] channel,  a change in expected future short-term interest rates translates into changes in long-term bond yields. ${ }^{6}$ And when bond yields change,  investors also change

[^34]the discount rate they apply to the expected future cash flows of other assets. For example,  when news arrives that the Federal Reserve is more likely to raise short-term interest rates in the future,  bond prices should fall and the prices of many other assets should fall as well.

One could try to tease out this effect of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] on asset prices by looking at the time series of short-term interest rates and asset prices and their correlation. But this sort of exercise would not really be informative. There are too many other distorting factors that also influence short-term interest rates and asset prices that have nothing to do with [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]]. For example,  if we looked at quarterly changes in interest rates and quarterly returns on the stock index,  it could be that sometimes stock prices fell early in the quarter which induced the Fed to lower interest rates later in the quarter. In other words,  this would be a reverse causality channel. Rather than the effect of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] on stock prices,  the correlation in this case would capture the effect of stock prices on [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]].

To truly isolate the effect of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] on asset markets,  we can look at very short time windows around the public announcements following FOMC meetings. Since 1994,  the Federal Reserve issues a press release after each FOMC meeting that states the FOMC's target for the federal funds rate and outlines the FOMC's view of the macroeconomic situation (from which market participants often draw conclusions about what the FOMC may decide to do in future meetings). When the announced federal funds rate deviates from what investors expected prior to the announcements,  asset prices respond almost instantaneously. Within a short window of a few minutes around the announcement,  it is very likely that the announcement of the [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] decision is the main piece of news that moved asset prices. Other distortionary factors are unlikely to be of comparable importance during this very short time window.

Figure 7.9 shows the average asset price reactions within 30 minutes around the FOMC announcements (starting 10 minutes before and ending 20 minutes after the press release). Which way the reaction goes and how strong it is of course depends on what was decided in the meeting relative to what the market expected before the announcement: Sometimes [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] turns out to be tighter (higher rates) than the market expected,  sometimes is is easier (lower rates),  sometimes the market perfectly anticipated the FOMC's decision so that asset prices do not react at all; sometimes the market is very surprised and asset prices move violently.

To account for all this,  one can first measure the magnitude of the surprise by looking at the change in yield of a one-year bond for each FOMC announcement. Then look

bond yields,  but not necessarily the only one. For example,  bond risk premia could vary over time which would also affect long-term bond yields in addition to the effects of expectations of future short rates.

at the returns of other assets,  e.g.,  of a stock index,  in response to the same FOMC announcements. Then regress the assets' returns on the changes in one-year yields. The slope coefficient in this regression then tells us the return that an asset experiences on average if the one-year yield rises by 1 percentage point during the 30 -minute window. These slope coefficients are shown in Figure 7.9.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-251.jpg?height=733&width=879&top_left_y=590&top_left_x=642)

Figure 7.9: Returns of bonds and stocks during 30 minutes around FOMC announcements

Bond returns are calculated from yield changes implied by Treasury futures and converted into returns by multiplying with approximate duration. Returns are expressed as a multiple of the change in the 1-year Treasury yield during the 30-minute announcement window. Source: Bauer,  M.D. and Swanson,  E.T.,  2022. A reassessment of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] surprises and high-frequency identification,  working paper,  National Bureau of Economic Research.

Focusing first on the bond returns,  we see that longer maturity bonds respond more strongly. For example,  when the one-year yield rises (falls) by one percentage point,  the two-year bond price falls (rises) by about $1.3/% while the 30 -year bond price falls (rises) by about $4.8/% percent. This indicates that investors perceive the change in [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] to be persistent. It affects not only the current short-term interest rate,  but the level of expected interest rates many quarters ahead. As a consequence,  bonds with longer maturity have stronger price reactions.

The right-most bar in Figure 7.9 shows the slope coefficient of the S&P500 stock market index. When the one-year yield rises (falls) by one percentage point,  the stock market falls (rises) by about $5.4/%. Hence,  not only bond prices are affected by [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] surprises,  but prices of stocks,  too. This makes sense,  given the discount-rate mechanism we discussed. This highlights that [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]]-and the underlying factors that give rise to changes in [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] - are major risk factors for the stock

market. Moreover,  since the discount rate mechanism affects basically all assets across asset classes,  this is a risk factor with very pervasive effects in a portfolio.

### 7.7 Monetary policy rules

Why does the Fed change its federal funds rate target over time? The Fed has a legal mandate to pursue the dual objectives of achieving stable prices and maximum employment. Therefore,  the Fed's target rate choice is closely related to the current inflation rate,  $\pi_{t}$,  and employment,  where the deviation from maximum employment (which is not directly observable) is estimated by measures of the so-called output gap ( $x_{t}-x^{*}$ ). In the output gap,  $x^{*}$ is meant to measure the level of employment or level of overall output that the economy can achieve without generating inflationary pressures. The higher actual employment or output $x_{t}$ relative to $x^{*}$,  the greater the inflationary pressure.

Stanford economist John Taylor documented in the early 1990s that the Fed's federal funds rate target policy choices are well explained by a simple rule that came to be known as the Taylor rule. There are various versions of the Taylor rule that differ in exactly which type of inflation or output measure is used,  and they may also have small differences in the coefficients that appear in the rule,  but broadly a Taylor rule always looks something like this:

$$

\begin{equation*}

i_{t}=r^{*}+\pi_{t}+0.5 \times\left(\pi_{t}-\pi^{*}\right)+1.0 \times\left(x_{t}-x^{*}\right) \tag{7.20}

\end{equation*}

$$

In this rule,  $\pi^{*}$ is the Fed's inflation target,  which has been $2/% explicitly since 2012,        but even before that,        Fed behavior seems quite well described by assuming an inflation target of $2/% annually. The rate $r^{*}$ is an estimate of the equilibrium real interest rate (i.e.,  inflation-adjusted) that would prevail in a world in which the Fed achieved its inflation and employment goals. This rate is difficult to estimate,  but assuming $r^{*}=2/% does a good job of explaining the Fed's interest rate choices.

The interpretation is as follows. Nominal interest rates should roughly be the real interest rate $\pi^{*}$ plus compensation for inflation $\pi_{t}$. In addition,  if there are deviations from the Fed's targets $\pi^{*}$ and $x^{*}$,  the Fed should react by raising interest rates above $r^{*}+\pi_{t}$ if $\pi_{t}>\pi^{*}$ or $x_{t}>x^{*}$. The idea is that raising interest rates should cool down the economy which will help bring inflation down and bring economic activity inline with the economy's capacity.

As an example,  Figure 7.10 shows the time-series of the interest rate implied by the rule in (7.20) as well as the actual federal funds rate. As one can see,  the series are extremely close most of the time. The exception is the post-GFC period when the federal

## Figure 2: Predictions of a Modified Taylor Rule

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-253.jpg?height=752&width=1489&top_left_y=361&top_left_x=340)

Figure 7.10: Taylor rule

Source: Ben Bernanke,

https://www.brookings.edu/blog/ben-bernanke/2015/04/28/the-taylor-rule-a-benchmark-for-monetary-policy/

funds rate hit zero and could not fall any further. This constraint by the zero lower bound (ZLB) was the motivation for the Federal Reserve to engage in unconventional [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] measures such as quantitative easing.

One important detail in the construction of the plot in Figure 7.10 is that the inflation and output gap measures are based on real-time data as it was available at the time the FOMC made decisions. Macroeconomic data such as inflation rates and GDP often gets substantially revised during the quarters following the initial announcement of an estimate. But if the FOMC makes a decision based on the most recently observed inflation rates and output gaps,  these revised data are not available yet. So if one wants to understand how macroeconomic data drives [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] decisions,  it's important to look at data that was actually available at the time when the FOMC decided on [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]].

Let's circle back to assessing risks of long-term bonds. We figured out earlier that long-term bond price changes reflect changing expectations of future short-term interest rates. Now we know,  through the Taylor rule,  that these expectations of future changes in short-term interest rates must ultimately boil down to expectations about future inflation and future output gaps.

### 7.8 Yield curve and the business cycle

That bond market investors' short-term interest rate expectations should be closely related to their expectations of future inflation and output gaps implies that the shape of the yield curve may be informative about the future state of the business cycle.

For example,  consider a situation where the economy is in a boom. Inflation may be a little elevated and the output is high. As a consequence,  short-term interest rates are relatively high. But bond market investors anticipate a downturn that will set in soon. As a consequence,  they expect the Federal Reserve to lower the fed fund rate target in the coming quarters. So long-term bond yields should be relatively low,  perhaps even lower than short-term interest rates if the long-term bond risk premium is not too big. In other words,  the yield curve should be inverted,  or close to inversion,  if bond market investors think that a recession is approaching.

The data suggests that bond market investors are doing pretty well in this regard. Go back to Figure 7.1 and note the periods in which the yield curve was inverted or close to inverted: Around 1980,  1990,  2000,  2008. Each of these inversion periods was followed by a recession,  as indicated in the figure by the shaded areas. The shaded areas are the months in which the U.S. economy was in recession according to the official designation by the National Bureau of Economic Research (NBER). Thus,  the yield curve slope seems to be a pretty good short-term forecaster of the business cycle.

### 7.9 Bond risk premia

In the formulation of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] in (7.15) we allowed for a constant risk premium. Whether such risk premia exist,  and what their sign is,  and whether they depend on the maturity of the bond are important questions if we want to gather inputs for a portfolio optimization including bonds.

Let's go back to our earlier expression (7.18) that relates bond returns to surprises in future short-term yields:

$$

\begin{equation*}

r_{n,             t+1}=y_{1,             t}+n \lambda_{n}-(n-1) \lambda_{n-1}-\left(\mathbb{E}_{t+1}-\mathbb{E}_{t}\right) \sum_{i=1}^{n-1} y_{1,             t+i} \tag{7.21}

\end{equation*}

$$

The longer the maturity $n$ of the bond,  the more terms of future expected short-term rates are there in the summation in the last term of this equation,  and hence the bigger are typically the changes in the expectations of this sum,  and hence the more volatile is the bond return.

So if long-term bonds have more volatile returns,  does this mean that long-term bonds should also earn a higher risk premium than short-term bonds? While this may seem plausible,  it's not obvious. Note that we are looking at the volatility of short-term returns here. But recall that for a long-term investor,  a long-term bond is actually a risk-free investment - at least it's risk-free if the long-term investor cares about nominal payoffs,  without adjusting for inflation. So if this kind of long-term view dominates among investors,  it's also possible that long-term bond earn a smaller risk premium than short-term bonds. Let's see what the data says.

In our analysis of bond returns,  we have so far focused on log returns,  due to the convenience of working with logs. But investors' care about simple,  not log returns. So in the data,  we will look at simple returns in excess of short-term bond returns. However,  the differences are quite small. For example,  if $R_{n,             t+1}$ is log-normal,  $\mathbb{E}\left[r_{n,             t+1}\right]$ $=0.02$ and $\operatorname{var}\left(r_{n,             t+1}\right)=0.05^{2}$ (which is empirically realistic,  as we will see shortly),  then $\mathbb{E}\left[R_{n,             t+1}\right] \approx \exp \left(0.02+0.05^{2} / 2\right)-1 \approx 0.0215$.

Table 7.2: Risk and return of U.S. Treasury bonds,  annualized estimates
![300](Keep%20It%202024-10-24%2010.47.46.png)

Table 7.2 takes a first look at this by showing the annualized average returns of portfolios of U.S. Treasury bonds of various maturities in excess of the average 1-year bond return,  along with the standard deviation of these returns and the Sharpe ratio. The estimates are based on data spanning five decades from 1971 to 2023.

The table shows that mean returns and standard deviations increase with maturity. The standard deviation result is sensible. As we discussed,  bonds are exposed to the risk of changing expectations of future short-term interest rates. And for a long-term bond,  with its final cash flow far into the future,  this discount rate effect is bigger. This is consistent with our discussion above following equation (7.21). The fact that the mean return is increasing in maturity suggests that the long-term bond risk premium is increasing in maturity.

The last row of Table 7.2 shows Sharpe ratios. They are almost the same for all three maturities and they are quite high! For comparison,  the CRSP value-weighted stock market index earned a Sharpe ratio of about 0.43 during the same time period. We still have to investigate more the correlation of bond returns with other assets to figure out how much bonds contribute to portfolio risks,  but these high Sharpe ratios seem suggestive that bonds could be good for portfolio risk and return performance.

As we discussed in lecture 2,  risk parity strategies,  which weight asset classes by weights proportional the inverse of return volatility have high weights of bonds. The results in Table 7.2 show why risk parity strategies have done so well in the past few decades (which may explain why they have become popular): Bonds have done very well.

But at least some of this must be luck. The decades since the start of the 1980s have been a bond investor's dream come true. in the early 1980s,  bond yields were high because inflation was high and short-term interest rates were high. Given their experience from the 1970s,  investors at the time did not have much confidence that inflation and interest rates would come down persistently any time soon. But then inflation fell,  interest rates fell,  and after they had fallen and it seemed like they could not possibly fall further,  they fell further,  all the way to almost zero in the years after the great financial crisis.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-256.jpg?height=1044&width=1351&top_left_y=1039&top_left_x=344)

Figure 7.11: 5-year moving average of 10-year bond excess returns

Figure 7.11 illustrates the consequences of this unanticipated fall in interest rates for the return of long-term bonds. The figure shows five-year moving averages of annualized monthly returns of 10-year bonds in excess of 1-year bond returns. Until the mid-1980s,  these five-year moving average excess returns were negative,  as bond investors suffered from rising interest rates. But then,  during the decades that followed,  none of the five-year moving averages was ever negative. This was surely luck for long-term bond investors. Even if long-term bonds earn a higher risk premium than short-term bonds,  we would expect that sometimes long-term bonds underperform short-term bonds for an extended period of time. But during these usual decades since the early 1980s,  bonds benefited again and again from further falls in interest rates. Almost surely nobody could have seen this coming in the early 1980s. For this reason,  the high Sharpe ratios of bonds that we see in Table 7.2 must have a substantial luck component that we should not expect to show up again in the coming years.

This also suggests some skepticism about the historically good performance of riskparity strategies. This historical performance seems unlikely to be repeated in the future.

### 7.10 Time-varying bond risk premia?

Under the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  the expected returns of investing in bonds of different maturities are equal,  up to differences due to a constant risk premium. Hence,  an upward-sloping yield curve does not necessarily mean that long-term bonds have higher expected returns than short-term bonds. At least part of the upward slope could also reflect expectations that short-term yields are going to rise in the future.

The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] gave us a theory of the yield curve that at least roughly seems to be true,  based on eyeballing the yield curve history. The way the slope of the yield curve forecasts the future path of short-term interest rates and the business cycle seems roughly in line with the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]. But this does not mean the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] holds exactly.

One way in which we can check for deviations from the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is by checking whether we can predict the excess return of long-term bonds over short-term bonds. The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] says that we should not be able to do this. To see this,  subtract the short-term yield from both sides of (7.21) and take conditional expectations. This yields

$$

\begin{equation*}

\mathbb{E}_{t}\left[r_{n,             t+1}\right]-y_{1,             t}=n \lambda_{n}-(n-1) \lambda_{n-1} \tag{7.22}

\end{equation*}

$$

in which the right-hand side is constant over time,  and hence the left-hand side must be constant,  too. Therefore,  under the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  there is no scope for generating superior returns from market-timing the bond market. (As before,  the caveat about differences between expected simple and expected log returns applies here.)

In contrast,  if the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is not entirely correct because the risk premium bond investors demand from bonds is time-varying,  or because bond investors have time-varying sentiment that biases their expectations of future short-term interest rates sometimes upward,  sometimes downward,  then we should be able to predict returns of long-term bonds in excess of short-term yields. For example,  suppose investors are currently very averse to the risks of holding long-term bonds. This should,  simultaneously,  raise yields of long-term bonds and the slope of the yield curve,  and generate high returns of long-term bonds going forward. In other words,  if bond risk premia are time-varying,  the yield curve slope might be able to tell us when we can expect high or low excess returns of long-term bonds.

To check this empirically,  we'll focus on the excess return of a portfolio that averages returns of bonds with different maturities from $n=2$ to $n=10$. I run the regression

$$

\begin{equation*}

\frac{1}{9}\left(\sum_{i=2}^{10} R_{i,             t+1}\right)-R_{1,             t+1}=a+b\left(y_{10,             t}-y_{1,             t}\right)+e_{t+1} \tag{7.23}

\end{equation*}

$$

with monthly data from 1971 to 2023.

Table 7.3: Predicting monthly bond excess returns with the 10yr-1yr yield spread
![300](Keep%20It%202024-10-24%2010.48.12.png)

Table 7.3 presents the results. The first block of rows shows that the yield curve slope is a statistically significant predictor of excess returns on this bond portfolio. The $R^{2}$ is $1/%,        which is not huge,        but for monthly return prediction, this is substantial. (Running the regression with returns over the next year instead of over the next month as dependent variable yields an $R^{2}$ of about $10/% ). So this would suggest a substantial violation of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]. This regression result suggests that when the yield curve slope is strongly upward sloping,  long-term bonds tend to earn high returns in the following month relative to short-term bonds.

There is a potential problem,  though. Yield levels and the yield curve slope have undergone some very slow-moving changes during the past five decades. Basically,  before around 1981,  the yield curve tended to be quite flat,  as investors did not anticipate that short-term rates would stay high for so long,  and bond returns were poor,  as a sequence of surprise interest rate hikes pushed down bond prices. After 1981,  the opposite happened.

So it's possible that our regression picks up this low slope/low returns before 1982,  high slope/high returns after 1981 pattern in the data. Neither the rise in rates in the 1970s,  nor the decades-long fall of rates from 1981 to 2021 could have been anticipated by investors. So if the regression picks this up,  it's perhaps capturing something that is unlikely to repeat in the future - or,  at least,  something that is statistically fragile because it's driven by extremely slow moving changes,  not year-to-year variation in the yield curve slope.

To check how big this problem is,  I modify the regression

$$

\begin{equation*}

\frac{1}{9}\left(\sum_{i=2}^{10} R_{i,             t+1}\right)-R_{1,             t+1}=a+d \mathbb{1}_{82 t o 21}+b\left(y_{10,             t}-y_{1,             t}\right)+e_{t+1} \tag{7.24}

\end{equation*}

$$

by including the dummy variable $\mathbb{1}_{82 t o 21}$ that simply takes values equal to zero in months before 1981,  a value of one from 1982 to 2021 and zero in all remaining months. This basically allows the intercept of the regression to be different from 1982 to 2021 (where it is $a+d$ ) and the rest of the sample (where it is just $a$ ). This effectively removes the difference in average returns between the 1982 to 2021 period and the rest of the sample,  which,  as I have argued,  investors likely could not have anticipated.

As the second block of rows in Table 7.3 shows,  this has a big effect on the estimate of the slope coefficient $b$ : it drops to about half in magnitude and it is quite far from being statistically significant. So the earlier result that bond excess returns can be predicted with the yield curve slope is quite fragile! At least some of it seems to be due to the low slope/low returns before 1982,  high slope/high returns from 1982 to 2021 pattern.

As we did a few lectures ago when we discussed stock market excess return forecasting with the price-dividend ratio,  we can also ask here how the bond excess return predictability looks like out of sample. The predictive regressions we looked at so far in the table above using the full sample of data are not regressions that an actual investor without the luxury of hindsight could have run.

We now look at pseudo-OOS regressions. We recreate regressions that investors in the past could have run,  based on the data that was available at the time. I fix an initial burn-in period of 120 months as minimum data requirement before one can run a regression. In the first month where this minimum data requirement is satisfied,  I run the regression of long-term bond portfolio returns in excess of the one-year bond return on the yield curve slope,  I record the estimated coefficients,  and I compute predicted excess returns for the next quarter. I then use the predicted excess return as portfolio weight $\omega_{t}$. The share $\omega_{t}$ is invested in the long-term bond portfolio in quarter $t+1$ and the rest,  $1-\omega_{t}$ in the one-year bond. Then I move forward one quarter and repeat the procedure,  and so on.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-260.jpg?height=906&width=1188&top_left_y=295&top_left_x=425)

Figure 7.12: Cumulative standardized excess returns of different out-of-sample portfolio strategies

Once I have the full time-series of portfolio returns,  I cumulate them and then by divide by the full-sample standard deviation (recall that this turns the cumulated returns into a cumulated "realized Sharpe ratio"). The blue line in Figure (7.12) shows the result.

As in our earlier analysis of stock market return predictability,  I compare the results to a trading strategy that uses just the trailing mean bond excess return instead of the predictive regression forecast as the portfolio weight. Returns are again cumulated and standardized. The red line shows the result for this trailing mean strategy. The result is quite different from what we found for stock market excess return predictability where predictive regression and trailing mean strategy delivered almost exactly the same cumulative standardized returns. Here the predictive regression is clearly better.

This looks like a resounding victory for a market-timing strategy based on the yield curve slope. Unfortunately,  this conclusion is pre-mature. The trailing mean strategy in this case is just a very poorly performing strategy. This is related to the problem we discussed earlier that bond returns during much of the past five decades werestrongly influenced by a decade-long rise in yields followed by a multi-decade fall in yields,  neither of which could really be anticipated by investors. These two trends have a very unfortunate impact in the trailing mean strategy: following the rise in yields in the 1970s,  it takes a short position in bonds just when bond yields start to fall and long-term bonds start to earn high returns. It takes until the 1990s for the strategy to finally take a long position in long-term bonds. It then still benefits from this long position,  but not enough to catch up with the trailing mean strategy.

For this reason,  it's useful to examine a second benchmark strategy,  as we did in the stock market return predictability analysis,  one that is always keeping a constant portfolio weight in the bond portfolio without trying to time the bond market. Unlike in the stock market return predictability analysis,  here this constant-weight portfolio (which simply puts $100/% into the long-term bond portfolio) does much better than the predictive regression. This shows that the relative success of the predictive regression strategy relative to the trailing mean strategy is not due to successful market timing because the constant-weight strategy doesn't do any market timing!

These results from the pseudo-OOS analysis cast further doubt on the usefulness of forecasting regressions for providing expected return estimates that could inform the portfolio optimization approach.

### 7.11 [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] with bonds

To assess the risk and return consequences of allocating part of a portfolio to bonds,  we need to understand not only the expected returns and standard deviations of returns of bonds that we examined so far,  but also the correlation of returns with other assets. We focus here in particular on the correlation with a domestic stock market index.

In lecture 2 we discussed that the attractiveness of an asset as an addition to a portfolio depends on the systematic risk that the asset brings to the portfolio,  as measured by the asset's beta with respect to the portfolio's return. So consider an investor who has the risky asset portion of their portfolio fully invested in the stock market and is considering an addition of bonds to the portfolio. The stock market portfolio return is $R_{m}$ and the bond return is $R_{b}$. In line with our earlier notation when we discussed [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]],  let's denote the yield on a Treasury bill with one period to maturity with $R_{f}$. The optimality condition (2.29) in lecture 2 then becomes

$$

\begin{equation*}

\mathbb{E}\left[R_{b,             t}\right]-R_{f}=\beta\left(\mathbb{E}\left[R_{m,             t}\right]-R_{f}\right),             \quad \beta=\frac{\operatorname{cov}\left(R_{m,             t},             R_{b,             t}\right)}{\operatorname{var}\left(R_{m,             t}\right)} \tag{7.25}

\end{equation*}

$$

If $\mathbb{E}\left[R_{b,             t}\right]-R_{f}$ is higher than $\beta\left(\mathbb{E}\left[R_{m,             t}\right]-R_{f}\right)$,  then adding bonds to the risky asset portion of the portfolio would improve the Sharpe ratio of the overall portfolio.

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-262.jpg?height=909&width=1199&top_left_y=294&top_left_x=428)

Figure 7.13: Beta of 10-year zero-coupon bonds based on daily returns in three-month moving windows

Therefore,  whether bonds are an attractive addition to the portfolio depends on the bond-stock beta. As it turns out,  this beta has undergone dramatic changes over the years. Figure 7.13 illustrates this. I take daily returns of the CRSP value-weighted stock market index and daily returns of 10-year zero coupon bonds (i.e.,  returns based on synthetic zero-coupon bond prices extracted from coupon-paying U.S. Treasury bond prices). Then I estimate the beta within three-month windows,  starting at the beginning,  with the first three months of available data. Once I have the first estimates,  I move the window forward by one day and repeat the estimation. Then I move it forward one more day,  and so on. The blue line in the figure shows the resulting time series of beta estimates. I then repeat the same procedure using the daily returns on 2-year zero coupon bonds. The resulting time series of betas is shown by the red line.

Let's focus first on the 10-year bond's beta. In the 1970s,  the beta started out close to zero. Hence,  in this environment,  adding some bonds to a stock portfolio would make sense even if the expected return on bonds is just slightly above the yield on Treasury bills. But throughout the 1970s and 1980s,  the beta went up,  eventually fluctuating around 0.5 . This means that bonds at that time brought substantial systematic risk to a stock portfolio. When the stock market fell,  bond prices would fall substantially,

too. With $\beta_{t}=0.5$,  bonds would have to offer more than half the equity premium $\mathbb{E}_{t}\left[R_{m,             t+1}\right]-R_{f,             t}$ to be an attractive asset to add to a portfolio that is fully invested in the stock market.

Then,  in the late 1990s,  the beta dropped dramatically,  often into negative territory. Now bonds were a hedge of stock market risk: a falling stock market coincided with rising bond prices during these years. Adding bonds to a stock market portfolio could be valuable even if bonds offered less expected return than Treasury bills.

In recent years,  the beta has been slowly rising again toward positive territory. We'll discuss the very recent data,  including the behavior of Treasury bond prices at the onset of the COVID pandemic in more detail in the next lecture.

The betas of 2-year bonds show the same pattern of betas over time,  just at a much smaller magnitude.

From an investment viewpoint,  a crucial question is whether expected excess returns of Treasury bonds have moved in line with the movements in the bond-stock beta in Figure 7.13. If a high bond-stock beta pushed up the risk premium for long-term bonds so that investors are enticed to hold the outstanding supply of bonds despite the higher systematic risk,  this would show up as a rise in the yields of long-term bonds. As Figure 7.13 shows,  the beta of shorter-maturity bonds also rises when the beta of long-term bonds rise,  but to a much smaller extent. Hence,  everything else equal (e.g.,  expectations about the path of future short-term yields) the yield curve should get steeper. And the steeper slope should then predict higher excess returns on long-term bonds.

But one take-away from our earlier discussion of bond excess returns predictability was that bond excess returns are difficult to predict. The yield curve slope may have some predictive power,  but the evidence on this looked quite fragile and weak. So we could take an approach were we regard the conditional expected excess returns of longterm bonds as constant (since we can't predict its time-variation) and try to exploit the changing systematic riskiness of long-term bonds (that we can capture quite reliably: it's quite persistent,  so if we estimate it to be high today,  based on data from the past three months or so,  it's also likely to be high going forward over the next quarter or next year).

Table 7.4: Annualized risk and return properties of a bond-stock beta timing strategy
![300](Keep%20It%202024-10-24%2010.47.27.png)

In Table 7.4 I show a quick back-of-the-envelope approach to this. I consider a portfolio that combines the CRSP value-weighted stock market index and 10-year bonds. To try to exploit the time-variation in the systematic risk of long-term bonds,  I use a timing strategy that varies the weight on bonds as a function of the beta of 10-year bonds:

$$

\begin{equation*}

\omega_{\text {bonds },             t}=0.40-\beta_{t},             \quad \omega_{\text {stocks },             t}=1-\omega_{\text {bonds },             t} . \tag{7.26}

\end{equation*}

$$

Every day,  I update these weights based on the beta estimate from the three-month window ending the day before. So when $\beta_{t}$ was around 0.5 in the 1980s,  the strategy has almost zero exposure to bonds. Once $\beta_{t}$ dropped into negative territory,  the strategy has $60/% or more invested in bonds.

The first column in Table 7.4 shows annualized means,  standard deviations,  and Sharpe ratio of this strategy. For comparison,  the second column shows these statistics for a strategy with fixed $60/% stocks,        $40/% bonds weight,  with daily rebalancing,  and a strategy that is fully invested in stocks. In terms of Sharpe ratio,  the beta-timing strategy does better than the two others. So this is a hint that there may be some benefits from changing bond exposures as a function of the bond-stock beta. Of course,  this is just a simple back-of-the-envelope analysis. I have not optimized the weights. Making the weights more or less sensitive to $\beta_{t}$ could potentially further improve the portfolio performance.

How would this play out in a bigger portfolio with other asset classes? We won't do a detailed analysis of this,  but it's likely that the effects would look quite similar. Many other asset classes - e.g.,  private equity,  [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]],  international stocksare positively correlated with the stock market index that we have used in our analysis above. Hence,  high beta of bonds with respect to this domestic stock index would likely also mean high beta on a portfolio that combines an investment in the domestic stock index with investments in these other asset classes.

As a final step,  we will dig into the reasons why the bond-stock beta has changed so much.

Part of the answer is that the nature of business cycles changed over the years. In the late 70s and early 1980s,  recessions were of the stagflation type - i.e.,  stagnating or falling GDP accompanied by high inflation. Oversimplifying a bit,  there were burst of high inflation and the Fed tried to bring inflation back down by raising interest rates strongly (recall our Taylor rule discussion),  which depressed economic activity,  causing a recession and falling stock prices. Therefore,  the fall in stock prices coincided with unexpectedly rising interest rates and hence falling bond prices-a positive bond-stock beta. Even later in the 1980s and early 1990s,  investors seemed to assume that future recessions would likely be of a similar flavor,  leading to falling stock and bond prices

## B. FOMC transcripts (1976-2013)

 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-265.jpg?height=806&width=1445&top_left_y=383&top_left_x=340)

Figure 7.14: Counts of stock market mentions in FOMC meeting transcripts

Source: Cieslak,  A. and Vissing-Jorgensen,  A.,  2021. The economics of the Fed put. The Review of Financial Studies,  34(9),  pp0.\1-4089.

when there were signs of slowing economic activity.

But once inflation seemed firmly under control in the late 1990s,  investors switched their views about how bonds and stock prices would comove in a recession. This shift in views was confirmed by the recessions around 2001 and 2008. In both cases,  stock markets fell strongly and the Fed strongly lowered interest rates,  leading to rising bond prices,  and a negative bond-stock beta.

Another part of the answer is that the Fed seems to have started paying more attention to the stock market. The Fed's motivation for doing this seems to have been,  in part,  that a falling stock market is an early indicator for a future decline in economic growth,  and,  in part,  that a stock market fall could also cause a decline in economic activity if stock market investors experience a loss of wealth and are less willing to consume. That stock market participation of retail investors had grown over the years,  e.g.,  through the spread of defined-benefit retirement accounts,  may have contributed to this concern gaining more relevance.

Figure 7.14 presents some evidence on the Fed's increasing attention to the stock

market. This is from a paper that analyzed the transcripts of FOMC meetings in which the members of the FOMC discuss how [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] should be set,  such as the target level for the federal funds rate. The figure shows the count of how much stockmarket related phrases appeared in the transcripts in each FOMC meeting. Strikingly,  the count goes up strongly just around the time,  in the late 1990s,  when the bond-stock beta dropped sharply.

This policy of the Fed reacting to stock market falls by lowering interest rates and thereby boosting the economy and the stock market came to be known as the "Fed put,  " the idea being that the Fed can be relied on to prevent,  or moderate,  falls in the stock market,  sort of like having a put option that hedges against stock market crashes. This in turn has given rise to concerns that this "Fed put" may encourage excessive risk-taking in financial markets.