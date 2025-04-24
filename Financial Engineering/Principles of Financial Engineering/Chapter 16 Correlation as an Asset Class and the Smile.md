# CORRELATION AS AN ASSET CLASS AND THE SMILE  

# 16  

# CHAPTER OUTLINE  

16.1 Introduction to Correlation as an Asset Class. 546   
16.1.1 Reasons for Trading Correlation.. 547   
16.1.2 Correlation Trading Vehicles . 547   
16.2 Volatility as Funding.... 551   
16.3 Smile ... . 551   
16.4 Dirac Delta Functions . 552   
16.5 Application to Option Payoffs .. 554   
16.5.1 An Interpretation of Dynamic Hedging.. 556   
16.6 Breeden Litzenberger Simplified... 558   
16.6.1 The Proof.. 560   
16.7 A Characterization of Option Prices as Gamma Gains... 561   
16.7.1 Relationship to Tanaka’s Formula.. 562   
16.8 Introduction to the Smile 562   
16.9 Preliminaries . 563   
16.10 A First Look at the Smile . 564   
6.11 What Is the Volatility Smile?. . 565   
16.11.1 Some Stylized Facts . 567   
16.11.2 How Can We Define Moneyness?... . 570   
16.11.3 Replicating the Smile . 572   
16.11.3.1 Contractual equations. 573   
16.12 Smile Dynamics . 574   
16.13 How to Explain the Smile.. .. 574   
16.13.1 Case 1: Nongeometric Price Processes . . 577   
16.13.2 Case 2: Possibility of Crash ... 577   
16.13.2.1 Modeling crashes 580   
16.13.3 Other Explanations 581   
16.13.3.1 Structural and regulatory explanations. 582   
16.14 The Relevance of the Smile .. 582   
16.15 Trading the Smile.. . 583   
16.16 Pricing with a Smile.. 583   
16.17 Exotic Options and the Smile . 584   
16.17.1 A Hedge for a Barrier . 584  

16.17.2 Effects of the Smile. 585  

16.17.2.1 An example of technical difficulties . 586   
16.17.2.2 Pricing exotics. 586   
16.17.3 The Case of Digital Options . 587   
16.17.4 Another Application: Risk Reversals .. 587   
16.18 Conclusions.. . 588   
Suggested Reading 588   
Exercises ... . 588   
Excel Exercise.. 589   
MATLAB Exercises.. . 590  

# 16.1 INTRODUCTION TO CORRELATION AS AN ASSET CLASS  

In the previous chapter, we saw that volatility as an asset class is firmly established. Developments in financial engineering did not stop at volatility and have continued their natural progression to correlation. Equity correlation measures how much stock prices tend to move together. Correlation links the volatility of an index to the volatilities of component stocks. As an approximation, we can write:  

Index volatility $\approx{\sqrt{\mathrm{correlation}}}\times$ average single stock volatility  

This formula shows that correlation is an important driver of index volatility. Historically, more than half of the changes in index volatility are driven by changes in correlation. This shows that correlation exposure is a fundamental component of volatility. Correlation risk is also an important driver of returns on options and other assets such as hedge funds. How can we use the principles of financial engineering applied in previous chapters to correlation? It turns out that it is quite straightforward to back out the level of forward-looking correlation being priced by the market by calculating the relative levels of implied index and implied single-stock volatilities. As with implied index volatility, this implied correlation tends to trade at a premium to that realized correlation. Figure 16.1 shows the realized and implied correlation for the S&P500.  

![](0c8c7842d69f116794efeceb807805a625fbc61209dcafeae1ffb9fa11a5eb96.jpg)  

# FIGURE 16.1  

Cash flows in a correlation swap.  

# 16.1.1 REASONS FOR TRADING CORRELATION  

The reasons for trading correlation are similar to the reasons for trading volatility:  

Since implied correlation has historically been above realized correlation, a short correlation (swap) position can be a good source of return. The hedge fund industry and several hedge fund strategies are exposed to correlation risk as Buraschi et al. (2014) show. Correlation is a major component of volatility and similar to volatility it is negatively correlated with equity index returns. Therefore, correlation trading can provide diversification benefits. Since correlation is the residual from index and single-stock volatility, correlation trading can be used to express views and take positions regarding the relative moves of index versus singlestock volatility.  

# 16.1.2 CORRELATION TRADING VEHICLES  

There are two main vehicles for trading correlation, namely variance dispersion trades and correlation swaps.1 Correlation swaps provide direct exposure to correlation. The payoff of a correlation swap is the difference between the strike of the swap and the subsequent realized average correlation of a pre-agreed basket of stocks or index. Although correlation swaps provide the purest correlation risk exposure, they are less liquid than dispersion trades.  

In recent years, the most common vehicle for trading correlation has been the dispersion trade. The trade involves taking opposing positions in the volatility of an index (or basket) and the volatility of its constitutents. Since a dispersion trade is typically implemented by means of variance swaps, it is called a variance dispersion trade. If variance swaps are used to benefit from unexpectedly higher correlations, the trade consists of a short position in an index variance swap and long positions in single stock variance swaps. Sometimes, for simplicity, options are used instead of variance swaps to generate index and stock-level exposure to volatility.  

Acceptance of correlation as an asset class is growing as the following example illustrates.  

# EXAMPLE  

Correlation trading diversifies:  

With correlation at historic highs across many indices, traders continue to see investors rush to monetise the widely-held view that correlation will fall over the next 12 months as macro-economic drivers become less prevalent in shaping investor sentiment, triggering the return of alpha strategies and increased stock dispersion. After effectively shutting down amid heightened uncertainty in the wake of Lehman Brothers’ bankruptcy, correlation trading has been gaining traction in recent months.   
“The correlation market has been re-opened for more than a year now and although the dispersion trade is a standard trade, investors are now tracking every kind of correlation, both within and between different asset classes,” said Stephane Mattatia, global head of financial engineering and advisory at SGCIB global equity flow.  

In recent months, macro hedge funds have made substantial profits by taking leveraged bets on correlation between a variety of asset classes including S&P 500 versus euro-dollar, which was highly correlated following the crisis and broke in September 2009. The strong correlation between gold and euro-dollar, which was also widely traded, broke earlier this year.  

In equity dispersion markets, traders are seeing greater diversity of client types as numerous pension funds become active players, and a greater diversity of trade types is being implemented.  

While macro hedge funds continue to favour the dispersion trade—buying volatility swaps on separate stocks while selling volatility swaps on the index—options strategies such as dispersion straddles have increased in popularity as liquidity in more traditional products declines.  

“Funds are now building dispersion books and the key is diversification,” said Mattatia. “They are trading all instrument types including straddles, variance swaps and volatility swaps, and looking across all indices.”  

(Thomson Reuters IFR 1850, ‘Correlation trading diversifies’, September 11, 2010)  

The above reading illustrates that correlation trading now extends across asset classes. Pension funds are mentioned as participants in correlation trading. They typically go long correlation swaps, which implies that they benefit when correlation unexpectedly increases. Macro hedge funds on the other hand are reported to be short correlation, by selling index and buying single stock variance swaps, thus benefiting when markets remain calm and correlations remain relatively low. To understand how correlation exposure can be created it is instructive to start with relatively simple correlation derivatives linked to one asset class, such as equities. Next we examine the replication and construction of dispersion traders and correlation swaps.  

The purest way to trade correlation is directly via a correlation swap. A correlation swap provides exposure to the average pairwise correlation of a predetermined basket of stocks. Average pairwise correlation $\rho_{A}$ is a simple equally weighted average of the correlations between all pairs of distinct stocks in an index:  

$$
\rho_{A}=\frac{2}{N(N-1)}\sum_{i<j}\rho_{i j}
$$  

where $\rho_{i j}$ is the pairwise correlation of the ith and jth stocks in a basket or index whose variance is given by $\begin{array}{r}{\sigma_{1}^{2}=\sum_{i}\omega_{i}^{2}\sigma_{i}^{2}+2\sum_{i<j}\omega_{i}\omega_{j}\sigma_{i}\sigma_{j}\rho_{i j}}\end{array}$ , where $\omega_{i}$ and $\sigma_{i}$ are respectively the weight and the volatility of the ith stock in the index.  

The swap strike is the level of (average pairwise) correlation that is bought or sold. It is typically scaled by a factor of 100 (that is a correlation of 0.5 is quoted as a strike of 50). Similar to the variance swap (discussed in the previous chapter), the payout of a correlation swap is the notional amount multiplied by the difference between the swap strike and the subsequent realized average pairwise correlation on the basket of underlyings:  

$$
\mathrm{Payout=notional\times(realized~average~pairwise~correlation-strike)}
$$  

Figure 16.1 shows the cash flows in a typical correlation swap cash flow. Let’s examine a correlation swap example.  

# EXAMPLE: CORRELATION SWAPS  

Suppose that on January 6, 2014, a hedge fund sells a 6-month correlation swap on an equally weighted basket of stocks consisting of the constituents of the Eurostoxx 50 index. The counter-party is assumed to be a pension fund. The strike price is 40 and the notional amount is h10,000. This means that the hedge fund is short the correlation swap and the pension fund is long the swap. One way to interpret the transaction is to say that, for a fee, the hedge fund sells insurance against unexpected increases of the correlation to the pension fund.  

After 6 months, on July 6, 2014, we calculate the realized 6-month average pairwise correlation of the stocks in our basket as 0.3. Then the buyer of the correlation swap, the pension fund, pays the following amount to the seller of the pension fund: Notional $\times(55-42)=\in10,000(40-30)=\in100,000$ .  

In the above example, the hedge fund received a premium for bearing the risk of unexpected increases in correlations. A good proxy for the correlation strike, also known as implied correlation, is the square of the ratio between the implied index volatility and the average of the equity component implied volatilities (as implied volatility is a good estimate of the forward-realized volatility, we could then also infer that implied correlation is a good estimate of the forward-realized correlation).  

Historically the implied correlation, the strike, has been above the realized correlation. This is illustrated in Figure 16.2 where the implied correlation is represented by the dashed line and the solid line represents the realized correlation.  

Although correlation swaps and variance swaps appear similar, the stochastic process followed by correlation and variance is different and therefore correlation and variance swaps allow the expression of different views in the form of directional trades or hedges as the following reading illustrates.  

# EXAMPLE  

Implied correlation hits multi-year lows  

Equity correlation has fallen in recent weeks alongside rising equity markets and plummeting volatility. The result has been a renewed focus on dispersion trades and other strategies that seek to profit from increased differentiation between stocks, sectors and global indices. “For investors, dispersion is a great story in the current environment and an interesting market parameter as it isn’t a directional view. It’s still very tricky to express a directional view on one market,” said Arnaud Jobert, executive director, equity derivatives structuring at JP Morgan. Despite a long-term rising trend, driven in part by a growing use of index and exchange traded products, implied correlation has dipped across global indices as well as at the sector and single stock level over the past year. And although it remains historically high, the measure is now trending back towards pre-crisis levels. Implied correlation across global indices hit multi-year lows last week as equities ramped up their January rally with the S&P 500 hitting 1500 for the first time since 2007. Over the course of just last week, two-year implied levels on a variety of index pairs including EuroStoxx 50/Nikkei 225 and S&P 500/Nikkei 225 fell by more than five points. Meanwhile, the CBOE’s S&P 500 implied correlation index (January 2014 maturity), which estimates correlation between the index constituents based on options prices of the S&P 500 index itself and its 50  

largest stocks, has fallen from 70 to 60 since the end of December, having traded in the 80s at the start of 2012.  

Macro shift  

Equity correlation pushed to record highs during the crisis as volatility spiked and investors fled equities for the safer haven of fixed income markets, leaving macro factors as the only real drivers of equity performance. But even while volatility declined to historic lows, correlation remained relatively high as abundant liquidity injected by worldwide central bank policy ensured that macro drivers outweighed other factors even as stock prices began to stage a rebound.  

However, that looks set to change as investors increasingly seek to express views on macro divergence as regions move towards different parts of their economic cycles.  

(Thomson Reuters IFR 1968, January 26, 2013)  

![](e9a6236e87fea8431459159d39600731fc6a339e3bbe8df32571233c123f4a49.jpg)  

# FIGURE 16.2  

Implied and realized correlation over time.  

# 16.2 VOLATILITY AS FUNDING  

For market professionals and hedge funds, the issue of how to fund an investment is as important as the investment itself. After all, a hedge fund would look for the “best way” to borrow funds to carry a position. The best way may sometimes carry a negative interest. In other words, the hedge fund would make money from the investment and from the funding itself.  

The normal floating LIBOR funding one is accustomed to think about is “risk-free,”2 but at the same time may not always carry the lowest funding cost. In principle, volatility could be used as a funding source. A practitioner could for example go short volatility and long another asset such as a fixed-income asset. To fund the position, why not select an appropriate volatility, sell options of value $N_{\astrosun}$ , and then delta hedge these option positions? In fact, this would fund the bond position with volatility. We analyze it below.  

First we know from Chapter 9 that delta-hedged short option positions are convex exposures that will pay the gamma. These payouts are unknown initially. As market volatility is observed, the hedge is dynamically adjusted, and depending on the market volatility the hedge fund will face a cash outflow equal to gamma. To the hedge fund this is similar to paying floating money market interest rates.  

Note one difference between loan cash flows and volatility cash flows. In volatility funding, there is no payback of the principal $N$ at the end of the contract. In this sense, $N$ is borrowed and then paid back gradually over time as gamma gains. One example is provided below from the year 2005.  

# EXAMPLE  

Merrill notes “one of the most overcrowded trades in the market has been to take advantage of the long term trading range,” by selling volatility and “earning carry via mortgage-backed securities.”  

Market professionals use options as funding vehicles for their positions. The main problem with this is that in many cases option markets may not have the depth needed in order to sell large chunks of options. If such selling depresses prices (i.e., volatility), then this idea may be hard to implement no matter how attractive it looks at the outset.  

# 16.3 SMILE  

Options were introduced as volatility instruments in Chapter 9. This is very much in line with the way traders think about options. We showed that when we deal with options as volatility instruments mathematically we arrived at the same formula, in this case the same partial differential equation (PDE) as the Black Scholes PDE. Mathematically the approach was identical to the standard textbook treatment that considers options as directional instruments.3 Yet, although the interpretation in Chapter 9 is more in line with the way traders and option markets think, in that discussion there was still a major missing component.  

It turns out that everything else being the same, an out-of-the-money put or call has a higher implied volatility than an ATM call or put. This effect, alluded to several times up to this point, is called the volatility smile. However, in order to discuss the smile in this chapter we adopt still another interpretation of options as instruments.  

The discussion in Chapter 9 showed that the option price (after some adjustments for interest receipts and payments) is actually related to the expected gamma gains due to volatility in the underlying. The interpretation we use in this chapter will show that these expected gains will depend on the option’s strike. One cost to pay for this interesting result is the need for a different mathematical approach. The advantage is that the smile will be the natural outcome. A side advantage is that we will discuss a dynamic hedging strategy other than the well-known delta-hedging. In fact, we start the chapter with a discussion of options from a more “recent” point of view which uses the so-called dirac delta functions. It is perhaps the best way of bringing the smile explicitly in option pricing.  

# 16.4 DIRAC DELTA FUNCTIONS  

Consider the integral of the Gaussian density with mean $K$ given below  

$$
\int\limits_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi{\beta}^{2}}}e^{-(1/2)(x-K)^{2}/{\beta}^{2}}\mathrm{d}x=1
$$  

where $\beta^{2}$ is the “variance” parameter. Let $f(x)$ denote the density:  

$$
f(x)=\frac{1}{\sqrt{2\pi{\beta}^{2}}}e^{-(1/2)(x-K)^{2}/{\beta}^{2}}
$$  

We will use $f(x)$ as a mathematical tool instead of representing a probability density associated with a financial variable. To see how this is done, suppose we consider the values of $\beta$ that sequentially go from 1 toward 0. The densities will be as shown in Figure 16.3. Clearly, if $\beta$ is very small, the “density” will essentially be a spike at $K.$ , but still will have an area under it that adds up to 1.  

Now consider the “expectations” calculated with such an $f(x)$ . Let $C(x_{t})$ be a random value that depends on the random variable $x_{t}$ , indexed by the time $t$ . Then we can write  

$$
E[C(x_{t})]=\ \int_{-\infty}^{\infty}C(x_{t})f(x_{t})\mathrm{d}x_{t}
$$  

![](18d0f37340062e313d14ea357d9a62ed5ef5604870ac541d0a5011ce4354ea29.jpg)  

# FIGURE 16.3  

Density as $\beta$ goes to zero.  

Now we push $\beta$ toward zero. The density $f(x_{t})$ will become a spike at $K.$ This means that all values of $C(x_{t})$ will be multiplied by a probability of almost zero, except the ones around $x_{t}=K$ . After all, at the limit $f(.)$ is nonzero only around $x_{t}=K$ . Thus at the limit we obtain  

$$
\operatorname*{lim}_{\beta\rightarrow0}\int C(x_{t})f(x_{t})\mathrm{d}x_{t}=C(K)
$$  

The integral of the product of a function $C(x_{t})$ and of $f(x_{t})$ as $\beta$ goes to zero picks up the value of the function at $x_{t}=K$ .  

Hence we define the Dirac delta function as  

$$
\delta_{K}(x)=\operatorname*{lim}_{\beta\to0}f(x,K,\beta)
$$  

Remember that $\beta$ determines how close $f(x)$ is to a spike at $K$ . The integral can then be rewritten as  

$$
\begin{array}{l}{\displaystyle\int_{-\infty}^{\infty}C(K)\delta_{K}(x)\mathrm{d}x_{t}=C(K)}\\ {\displaystyle-\infty}\end{array}
$$  

This integral shows the most useful property of dirac delta function for our purposes. Essentially, the dirac delta picks up the value of $C(x_{t})$ at the point $x_{t}=K$ . We now apply this property to option payoffs at expiration.  

# 16.5 APPLICATION TO OPTION PAYOFFS  

The major advantage of the dirac delta functions, interpreted as the limits of distributions, is in differentiating functions that have points that cannot be differentiated in the usual sense. There are many such points in option trading. The payoff at the strike $K$ is one example. Knock-in, knock-out barriers is another example. Dirac delta will be useful for discussing derivatives at those points.  

Before we proceed, for simplicity we will assume in this section that interest rates are equal to zero:  

$$
r_{t}=0
$$  

We also assume that the underlying $S_{T}$ follows the risk-neutral SDE, which in this case will be given by  

$$
\mathrm{d}S_{T}=\sigma(S_{t})S_{t}\mathrm{d}W_{t}
$$  

Note that with interest rates being zero, the drift is eliminated and that the volatility is not of the Black Scholes form. It depends on the random variable $S_{t}$ . Let  

$$
\begin{array}{r l}{f(S_{T})}&{{}=\operatorname*{max}[S_{T}-K,0]}\\ {\ }&{{}=\left(S_{t}-K\right)^{+}}\end{array}
$$  

be the vanilla call option payoff shown in Figure 16.4. The function is not differentiable at $S_{T}=K$ , yet its first-order derivative is like a step function. More interestingly, the second-order derivative can be interpreted as a dirac delta function. These derivatives are shown in Figures 16.4 and 16.5.  

![](1a870bc65f8509f9b593efafaa54db9b4dd4ca4a1c4c08846eea664bcf4566bc.jpg)  

# FIGURE 16.4  

Call option payoff and first derivative.  

![](c46a3964e45828f43baf98639400b7fe80ef3f6b309764fafd983377fa144630.jpg)  

# FIGURE 16.5  

Second derivative and dirac delta function.  

Now write the equivalent of Ito’s Lemma in a setting where functions have kinks as in the option payoff case. This is called Tanaka’s formula and essentially extends Ito’s Lemma to functions that cannot be differentiated at all points. We can write  

$$
\mathrm{d}(S_{t}-K)^{+}=\frac{\hat{\sigma}(S_{t}-K)^{+}}{\hat{\sigma}S_{t}}\mathrm{d}S_{t}+\frac{1}{2}\frac{\hat{\sigma}^{2}(S_{t}-K)^{+}}{\hat{\sigma}S_{t}^{2}}\sigma(S_{t})^{2}\mathrm{d}t
$$  

where we define  

$$
\frac{\partial(S_{t}-K)^{+}}{\partial S_{t}}=1_{s_{t}>K}
$$  

$$
\frac{\hat{\sigma}^{2}(S_{t}-K)^{+}}{\hat{\sigma}S_{t}^{2}}=\delta_{K}(S_{t})
$$  

Taking integrals from $t_{0}$ to $T$ we get:  

$$
\left(S_{T}-K\right)^{+}=\left(S_{t_{0}}-K\right)^{+}+\prod_{t_{0}}^{T}1_{s_{t}>K}\mathrm{d}S_{t}+\frac{1}{2}\int\frac{\hat{\sigma}^{2}\left(S_{t}-K\right)^{+}}{\hat{\sigma}S_{t}^{2}}\sigma(s_{t})^{2}\mathrm{d}t
$$  

where the first term on the right-hand side is the time value of the option at time $t_{0}$ and is known with certainty. We also know that with zero interest rates, the option price $C\left({{S}_{t_{0}}}\right)$ will be given by  

$$
C\left(s_{t_{0}}\right)=E_{t_{0}}^{\tilde{P}}(S_{T}-K)^{+}
$$  

Now, using the risk-adjusted probability $\tilde{P}$ , (i) apply the expectation operator to both sides of Eq. (16.13), (ii) change the order of integration and expectation, and (iii) use the property of dirac delta functions in eliminating the terms valued at points other than $S_{t}=K$ . We obtain the characterization of the option price as:  

$$
\begin{array}{r l}{E_{t}^{P}[(S_{T}-K)^{+}]}&{=\left(S_{t_{0}}-K\right)^{+}+\displaystyle\int_{t_{0}}^{T}\sigma(K)^{2}\phi_{t}(K)\mathrm{d}t}\\ &{=C\big(S_{t_{0}}\big)}\end{array}
$$  

where $\phi_{t}(.)$ is the continuous density function that corresponds to the risk-adjusted probability of $S_{t}$ .4 This means that the time value of the option depends (i) on the intrinsic value of the option,  

(ii) on the time spent around $K$ during the life of the option, and (iii) on the volatility at that strike, $\sigma(K)$ .  

The main point for us is that this expression shows that the option price depends not on the overal volatility, but on the volatility of $S_{t}$ around $K$ . This is exactly what the notion of volatility smile is.  

# 16.5.1 AN INTERPRETATION OF DYNAMIC HEDGING  

There are many dynamic strategies that replicate an option’s final payoff. The best known is delta hedging. In delta hedging, the financial engineer will buy or sell the delta $\mathbf{\Psi}=D_{t}\mathbf{\Psi}$ units of the underlying, borrow any necessary funds, and adjust $D_{t}$ as the underlying $S_{t}$ moves over time. As $t\rightarrow T,$ the expiration date, this will duplicate the option’s payoff. This is the case because, as the time value goes to zero the option price merges with $\left(S_{T}-K\right)^{+}$ .  

However, there is an alternative dynamic hedging procedure that is similar to the approach adopted in the previous section. The dynamic hedging technique, called stop-loss strategy, is as follows.  

In order to replicate the payoff of the long call, hold one unit of $S_{t}$ if $K<S_{t}$ . Otherwise hold no $S_{t}$ . This strategy requires that as $S_{t}$ crosses level $K$ , we keep adjusting the position as soon as possible. Either buy one unit of $S_{t}$ or sell the $S_{t}$ immediately as $S_{t}$ crosses the $K$ from left to right or from right to left, respectively. The $\mathrm{{P/L}}$ of this position is given by the term  

$$
\frac{1}{2}\int_{t_{0}}^{T}\frac{\partial^{2}\left(S_{t_{0}}-K\right)^{+}}{\partial S_{t}^{2}}\sigma(S_{t})^{2}\mathrm{d}t
$$  

Clearly the switches at $S_{t}=K$ cannot be done instantaneously at zero cost. The trader is moving with time $\Delta$ while the underlying Wiener process is moving at a faster rate $\sqrt{\Delta}$ . These adjustments are shown in Figures 16.6 and 16.7. The resulting hedging cost is the options value.  

![](edbbeea520fbc9f7773c1c62cb23172a1267d40d480af20d25bb1ae143471e26.jpg)  

# FIGURE 16.6  

Hedging strategy adjustment—call option.  

![](1d022481d2f83bdaba923cf694843e51708defffeac987cf48c345f48bca26a3.jpg)  

# FIGURE 16.7  

Hedging strategy adjustment and positions.  

# 16.6 BREEDEN LITZENBERGER SIMPLIFIED  

The so-called Breeden Litzenberger Theorem is an important result that shows how one can back out risk-adjusted probabilities from liquid arbitrage-free option prices. In this section, we discuss a trader’s approach to Breeden Litzenberger. This approach will show the theoretical relevance of some popular option strategies used in practice. Below, we use a simplified framework which could be generalized in a straightforward way. However, we will not generalize these results, but instead in the following section use the dirac delta approach to prove the Breeden Litzenberger theorem.  

Consider a simple setting where we observe prices of four liquid European call options, denoted by $\{C_{t}^{1},...,C_{t}^{4}\}$ . The options all expire at time $T$ with $t<T.$ The options have strike prices denoted by $\{\dot{K^{1}}<...\dot{<}K^{4}\}$ with  

$$
K^{i}-K^{i-1}=\Delta K
$$  

Hence, the strike prices are equally spaced. Apart from the assumption that these options are written on the same underlying $S_{t}$ which does not pay dividends, we make no distributional assumption about $S_{t}$ . In fact the volatility of $S_{t}$ can be stochastic and the distribution is not necessarily log normal.  

Finally we use the LIBOR rate $L_{t}$ to discount cash flows to be received at time $T.$ . The discount factor will then be given by  

$$
\frac{1}{(1+L_{t}\delta)}
$$  

Next we define a simple probability space. We assume that the strike prices define the four states of the world where $S_{T}$ can end up. Hence the state space is discrete and is assumed to be made of only four states $\{\omega^{1},...,\omega^{4}\}$ .5  

$$
\omega^{i}=K^{i}
$$  

We then have four risk-adjusted probabilities associated with these states defined as follows:  

$$
\begin{array}{l}{p^{1}=P(S_{T}=K^{1})}\\ {p^{2}=P(S_{T}=K^{2})}\\ {p^{3}=P(S_{T}=K^{3})}\\ {p^{4}=P(S_{T}=K^{4})}\end{array}
$$  

The arbitrage-free pricing of Chapter 11 can be applied to these vanilla options:  

$$
C_{t}^{i}=\frac{1}{(1+L_{t}\delta)}E_{t}^{\tilde{P}}\big[(S_{T}-K,0)^{+}\big]
$$  

The straightforward application of this formula using the probabilities $p^{i}$ gives the following pricing equations, where possible payoffs are weighed by the corresponding probabilities (Figure 16.8).  

![](8caa9d17809f63ac08973ac1e982d72bcefc4e6543c20c164288eb6544c4bd51.jpg)  

# FIGURE 16.8  

Payoff diagrams for puts and calls with different moneyness.  

$$
C_{t}^{1}=\frac{1}{(1+L_{t}\delta)}\left[p^{2}\Delta K+p^{3}(2\Delta K)+p^{4}(3\Delta K)\right]
$$  

$$
C_{t}^{2}=\frac{1}{(1+L_{t}\delta)}\left[p^{3}(\Delta K)+p^{4}(2\Delta K)\right]
$$  

$$
C_{t}^{3}=\frac{1}{(1+L_{t}\delta)}\big[p^{4}(\Delta K)\big]
$$  

Next we calculate the first differences of these option prices.  

$$
C_{t}^{1}-C_{t}^{2}=\frac{1}{(1+L_{t}\delta)}\left[p^{2}\Delta K+p^{3}(\Delta K)+p^{4}(\Delta K)\right]
$$  

$$
C_{t}^{2}-C_{t}^{3}=\frac{1}{(1+L_{t}\delta)}\big[p^{3}(\Delta K)+p^{4}(\Delta K)\big]
$$  

Finally, we calculate the second difference and obtain the following interesting result:  

$$
(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})=\frac{1}{(1+L_{t}\delta)}p^{2}\Delta K
$$  

Divide by $\Delta K$ twice to obtain  

$$
\frac{\Delta^{2}C}{\Delta K^{2}}=\frac{1}{(1+L_{t}\delta)\Delta K}p^{2}
$$  

where  

$$
\Delta^{2}C=(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})
$$  

This is the well-known Breeden Litzenberger result in this very simple environment. It has interesting implications for the options trader.  

Note that  

$$
(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})=(C_{t}^{1}-C_{t}^{3})-2C_{t}^{2}
$$  

In other words, this is an option position that is long two wings and short the center twice. In fact this is a butterfly centered at $K_{2}$ . It turns out that the arbitrage-free market value of this butterfly multiplied by the $(1+L_{t}\delta)\Delta K$ gives the risk-adjusted probability that the underlying $S_{t}$ will end up at state $K_{2}$ . Letting $\Delta K{\rightarrow}0$ we get  

$$
\frac{\hat{\sigma}^{2}C}{\hat{\sigma}K^{2}}=\frac{1}{(1+L_{t}\delta)}\phi(S_{T}=K)
$$  

where $\phi(S_{T}=K)$ is the (conditional) risk-adjusted density of the underlying at time $T$ .6  

This discussion illustrates one reason why butterflies are traded as vanilla instruments in option markets. They yield the probability associated with their center. Below we prove the Breeden Litzenberger result using the dirac delta function.  

# 16.6.1 THE PROOF  

The idea behind the Breeden Litzenberger result has been discussed before. It rests on the fact that by using liquid and arbitrage-free options prices we can back out the risk-adjusted probabilities associated with various states of the world in the future. The probabilities will relate to the future values of the underlying price, $S_{T}$ .  

The theorem asserts that (i) if a continuum of European vanilla option prices exists for all $0\le K$ and (ii) if the function giving $C(S_{t},K)$ is twice differentiable with respect to $K$ , then we have  

$$
\frac{\hat{\sigma}^{2}C}{\hat{\sigma}K^{2}}=\frac{1}{(1+L_{t}\delta)}\phi(S_{T}=K)
$$  

where $\phi\big(S_{T}=K|S_{t_{0}}\big)$ is the conditional risk-adjusted density of $S_{T}$ In other words, if we had a continuum of vanilla option prices, we could obtain the risk-adjusted density with a straightforward differentiation. We now prove this using the dirac delta function $\delta_{K}(S_{T})$ .  

Apply the twice differential operator to the definition of both sides of the arbitrage-free price $C(S_{t},K)$ . By definition, this means  

$$
\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}\intop_{0}^{\infty}{(S_{T}-K)^{+}\phi(S_{T})\mathrm{d}S_{T}}
$$  

Assuming that we can interchange the operators and realizing that $\phi(S_{T})$ does not depend on $K$ we obtain  

$$
\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\intop_{0}^{\infty}\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}(S_{T}-K)^{+}\phi(S_{T})\mathrm{d}S_{T}
$$  

But  

$$
\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}(S_{T}-K)^{+}=\delta_{K}(S_{T})
$$  

is a dirac delta, which means that  

$$
\frac{\hat{\sigma}^{2}}{\hat{\sigma}K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\int_{0}^{\infty}\delta_{K}(S_{T})\phi(S_{T})\mathrm{d}S_{T}
$$  

The previous discussion and Eq. (16.4) tells us that in this integral $\phi(S_{T})$ is being multiplied by zero everywhere except for $S_{T}{=}K$ . Thus,  

$$
\frac{\partial^{2}}{\partial K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\phi(S_{T}=K)
$$  

To recover the risk-adjusted density just take the second partial of the European vanilla option prices with respect to $K$ . This is the Breeden Litzenberger result.  

# 16.7 A CHARACTERIZATION OF OPTION PRICES AS GAMMA GAINS  

The question then is, how does a trader “characterize” an option using these hedging gains? First of all, in liquid option markets the order flow determines the price and the trader does not have to go through a pricing exercise. But still, can we use these trading gains to represent the frame of mind of an options trader?  

The discussion in the previous section provides a hint about this issue. The trader buys or sells an option with strike price $K$ . The cash needed for this transaction is either borrowed or lent. Then the trader delta hedges the option. Finally, this hedge is adjusted as the underlying price fluctuates around the initial $S_{t_{0}}$ .  

According to this, the trader could add the (discounted) future gains (payouts) from these hedge adjustments and this would be the true time-value of the option, besides interest or other expenses. The critical point is that these future gains need to be calculated at the initial gamma, evaluated at the initial $s_{t_{0}}$ , and adjusted for passing time.  

We can explain this statement. First, for simplicity assume interest rates are equal to zero. We then let the price of the vanilla call be denoted by $C(S_{t},t)$ . Then by definition we have  

$$
C\left(S_{t_{0}},T\right)=\mathbf{Max}[S_{t_{0}}-K,0]
$$  

This will be the future value of the option if the underlying ended up at $S_{t_{0}}$ at time $T.$ . Now, this value is equal to the initial price plus how much the time value has changed between $t_{0}$ and $T_{\mathbf{\delta}}$ ,  

$$
C\left(S_{t_{0}},T\right)=C\left(S_{t_{0}},t_{0}\right)+\int_{t_{0}}^{T}\frac{\partial C}{\partial t}\left|_{S_{t}=S_{t_{0}}}\mathrm{d}t\right.
$$  

Now, we know from the Black Scholes PDE that  

$$
\frac{\partial C}{\partial t}=\frac{1}{2}\frac{\partial^{2}C}{\partial S_{t}^{2}}\sigma_{t}^{2}(S_{t},t)
$$  

Substituting and reorganizing Eq. (16.42) above becomes  

$$
C\big(S_{t_{0}},t_{0}\big)=\mathbf{M}\mathbf{a}\mathbf{x}\big[S_{t_{0}}-K,0\big]+\int_{0}^{T}\frac{1}{1}\frac{\hat{\sigma}^{2}C\big(S_{t_{0}},t\big)}{\hat{\sigma}S_{t}^{2}}\sigma_{t}^{2}\big(S_{t_{0}},t\big)\mathrm{d}t
$$  

Note that on the right-hand side, the integral is evaluated at the constant $S_{t_{0}}$ so we don’t need to take expectations.  

According to this, the trader is valuing the option at time $t_{0}$ by adding the intrinsic value and the gamma gains evaluated with a gamma at $S_{t_{0}}$ and a volatility centered at $S_{t_{0}}$ . Still, the time $t$ changes and this will change the gamma over time. Thus, it is important to realize that the trader is not valuing the option by looking at the expected value of the future gamma gains evaluated at random future $S_{t}$ . The gamma is evaluated at the initial $S_{t_{0}}$ .  

# 16.7.1 RELATIONSHIP TO TANAKA’S FORMULA  

The discussion above is also consistent with the option interpretation obtained using Tanaka’s formula. Consider the value of the option as shown above, again  

$$
C\big(S_{t_{0}},t_{0}\big)=\mathbf{M}\mathrm{ax}\big[S_{t_{0}}-K,0\big]+\int_{t_{0}}^{T}\frac{1}{2}\frac{\hat{\sigma}^{2}C\big(S_{t_{0}},t\big)}{\hat{\sigma}S_{t}^{2}}\sigma_{t}^{2}\big(S_{t_{0}},t\big)\mathrm{d}t
$$  

Now we know from Breeden Litzenberger that  

$$
\frac{\partial^{2}C\big(S_{t_{0}},t\big)}{\partial S_{t}^{2}}\sigma_{t}^{2}\big(S_{t_{0}},t\big)=\varPhi\big(S_{t_{0}},t|S_{t_{0}}\big)
$$  

where $\varPhi\bigl(S_{t_{0}},t\vert S_{t_{0}}\bigr)$ is the risk-adjusted density of $S_{t}$ at time $t$ . Substituting this in the option value  

$$
C\left(S_{t_{0}},t_{0}\right)=\mathbf{Max}\left[S_{t_{0}}-K,0\right]+\int_{t_{0}}^{T}\frac{1}{2}\sigma_{t}^{2}\left(S_{t_{0}},t\right)\varPhi\left(S_{t_{0}},t\vert S_{t_{0}}\right)\mathrm{d}t
$$  

This is the same equation we obtained by using dirac delta functions along with the Tanaka formula. The second term on the right-hand side was called local time. In this case, the local time is evaluated for the ATM option with strike $K=S_{t_{0}}$ .  

# 16.8 INTRODUCTION TO THE SMILE  

Markets trade many options with the same underlying, but different strike prices and different expirations. Does the difference in strike price between options that are identical in every other aspect have any important implications?  

At first, the answer to this question seems to be no. After all, vanilla options are written on an underlying, with say, price $S_{t},$ and this price will have only one volatility at any time t, regardless of the strike price $K_{i}.$ Hence, it appears that, regardless of the differences in the strike price, the implied volatility of options written on the same underlying, with the same expiration, should be the same.  

Yet, this first impression is wrong. In reality, options that are identical in every respect, except for their strike, in general, have different implied volatilities. Overall, the more out-of-the-money a call (put) option is, the higher is the corresponding implied volatility. This well-established empirical fact is known as the volatility smile, or volatility skew, and has major implications for hedging, pricing, and marking-to-market of many important instruments. In the remainder of this chapter, we discuss the volatility smile and skews using caps and floors as vehicles for conveying the main ideas. This will indirectly give us an opportunity to discuss the engineering of this special class of convex instruments.  

From this point and on, in this chapter we will use the term smile only. This will be the case even when the smile is, in fact, a one-sided skew. However, whenever relevant, we will point out the differences.  

# 16.9 PRELIMINARIES  

The volatility smile has important implications for trading, hedging, and pricing financial instruments. To illustrate how far things have come in this area, we look at a position taken with the objective of benefiting from abnormal conditions regarding the volatility smile.  

We can trade stocks, bonds, or, as we have seen before, the slope of the yield curve. We may, for example, expect that the long-term yields will decline relative to the short-term yields. This is called a flattening of the yield curve and it invites curve-flattening strategies that (short) sell short maturities, and buy long maturities. This can be done using cash instruments (i.e., bonds) or swaps.  

In any case, such trades have become routine in financial markets. A more recent relative value trade relates to the volatility smile. Consider the following episode.  

# EXAMPLE  

Over the last month, European equity options traders have seen interest by contrarian investors, namely hedge funds, in buying at-the-money volatility and selling out-of-the-money volatility to take advantage of a skew in volatility levels in certain markets.  

. . . the skew trade involves an investor buying at-the-money vol and selling out-of-the-money vol. Due to supply/demand pressures, the level of out-of-the-money vol sometimes rises higher than normal. In other words, the spread between out, and at-the-money volatility increases, causing a so-called skew. Investors put on the trade in anticipation of the skew dissipating. [A trader] explained that along with the bull run of US and European equity markets has come a sense of unease among some investors regarding a downturn. Many have thus sought protection via over-the-counter put contracts. Because out-of-the-money puts are usually cheaper than at-the-money puts, many investors have opted for the former. The heavy volume has caused out-of-the-money vol levels to rise. Many investors want crash protection but today puts are too expensive. So, instead of buying today at 100 they buy puts at 80.  

(Based on an article in Derivatives Week (now part of GlobalCapital))  

According to this example, equity investors that had heavily invested during the “stock market bubble” of the 1990s were looking for crash protection. They were long equities and would have suffered significant losses if markets crashed. Instead of selling the stocks that they owned, they bought put options. With a put an investor has the right to sell the underlying stocks at a predetermined price, say, $K$ . If market price declines below $K$ , the investor would have some protection.  

According to the reading, the large number of investors who were willing to buy puts increased, first, the at-the-money (ATM) volatility.7 The ATM options became expensive. To lower the cost of insurance sought, investors instead bought options that were, according to the reading, $20\%$ out-of-the-money. These options were cheaper. But as more and more investors bought them, the out-of-the-money volatility started to increase relative to ATM volatility of the same option series. This led to an abnormally steep skew.8  

The reading suggests that this “abnormal” skew may have attracted some hedge funds who expected the abnormality to disappear in the longer run. According to one theory, these funds sold out-of-the-money volatility and bought ATM volatility. This position will make money if the skew flattens and out-of-the-money volatility decreases relative to the ATM volatility.9 As this example shows, the skew, or smile, should be considered as an integral part of financial markets activity. However, as we see in this section, its existence causes several complications and difficulties in financial modeling and in risk management.  

# 16.10 A FIRST LOOK AT THE SMILE  

The volatility smile can be a confusing notion, and we need to discuss some preliminary ideas before getting into the mechanics of pricing and market applications. It is well known that the Black Scholes assumptions are not very realistic. And yet, the Black Scholes formula is routinely used by options traders, although these traders know better than anybody else that the assumptions behind the model are problematic. One of the major Black Scholes assumptions, for example, is that volatility is constant during the life of an option. How can a trader still use the Black Scholes formula if the realized volatility is known to fluctuate significantly during the life of the option?  

If this BlackScholes assumption is violated, wouldn’t the price given by the BlackScholes formula be “wrong,” and, hence, the volatility implied by the formula be erroneous? This question needs to be carefully considered. In the end, we will see that there are really no inconsistencies in traders’ behavior. We can explain this as follows.  

1. First, note that the Black Scholes formula is simple and depends on a small number of parameters. In fact, the only major parameter that it depends on is the volatility, $\sigma.$ . A simple formula has some advantages. It is easy to understand and remember. But, more importantly, it is also easy to realize where or when it may go wrong. A simple formula permits developing ways to correct for any inaccuracies informally by making subjective adjustments during trading. The BlackScholes formula has one parameter, and it may be easier to remember how to “adjust” this parameter to cover for the imperfections of the formula.10  

2. An important aspect of the Black Scholes formula is that it has become a convention. In other words, it has become a standard among professionals and also in computer platforms. The formula provides a way to connect a volatility quote to a dollar value attached to this quote. This way traders use the same formula to put a dollar value on a volatility number quoted by the market. This helps in developing common platforms for hedging, risk managing, and trading volatility.  

3. Thus, once we accept that the use of the Black Scholes formula amounts to a convention, and that traders differ in their selection of the value of the parameter $\sigma$ , then the critical process is no longer the option price, but the volatility. This is one reason why in many markets, such as caps, floors, and swaptions markets, the volatility is quoted directly.  

One way to account for the imperfections of the Black Scholes assumptions would be for traders to adjust the volatility parameter.  

4. However, the convention creates new risks. Once the underlying is the volatility process, another issue emerges. For example, traders could add a risk premium to quoted volatilities. Just like the risk premium contained in asset prices, the quotes on volatility may incorporate a risk premium.  

The volatility smile and its generalization, the volatility surface, could then contain a great deal of information concerning the implied volatilities and any arbitrage relations between them. Trading, pricing, hedging, and arbitraging of the smile thus become important.  

# 16.11 WHAT IS THE VOLATILITY SMILE?  

Consider the Black Scholes world with vanilla European call and put options written on the equity price (index), $S_{t},$ that expire on the same date $T.$ Let $K_{i}$ denote the ith strike of the option series and $\sigma_{i}$ the constant Black Scholes instantaneous (implied) volatility coefficient for the strike $K_{i}$ . Finally, let $r$ be the constant risk-free rate.  

The Black Scholes setting makes many assumptions beyond that of constant volatility. In particular, the underlying equity does not make any dividend payments, and there are no transaction costs, tax issues, or regulatory costs. Finally, $S_{t}$ is assumed to follow the geometric stochastic differential equation (SDE)  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty]
$$  

where $W_{t}$ is a Wiener process defined under the probability $P$ . Here, the parameter $\mu$ may also depend on $S_{t}.$ The crucial assumption is that the diffusion component is given by $\sigma S_{t}$ . This is the assumption that we are concerned with in this chapter. The Black Scholes setting assumes that the absolute volatility during an infinitesimally small interval $\mathrm{d}t$ is given (heuristically) by11  

$$
\sqrt{E_{t}^{P}[(\mathrm{d}S_{t}-\mu S_{t}\mathrm{~d}t)^{2}]}=\sigma S_{t}\sqrt{\mathrm{d}t}
$$  

Thus, for a small interval, $\Delta$ , we can write the percentage volatility approximately as  

$$
\frac{\sqrt{E_{t}^{p}[(\Delta S_{t}-\mu S_{t}\Delta)^{2}]}}{S_{t}}\cong\sigma\sqrt{\Delta}
$$  

According to this, as $S_{t}$ changes, the percentage volatility during intervals of length $\Delta$ remains approximately constant.  

In this environment, a typical put option’s price is given by the Black Scholes formula:  

$$
P(S_{t},K,\sigma,r,T)=-S_{t}N(-d_{1})+K e^{-r(T-t)}N(-d_{2})
$$  

with  

$$
d_{1}=\frac{\log(S_{t}/K)+\left((1/2)\sigma^{2}+r\right)(T-t)}{\sigma\sqrt{T-t}}
$$  

$$
d_{2}=d_{1}-\sigma\sqrt{(T-t)}
$$  

Suppose the markets quote implied volatility, $\sigma$ . To get the monetary value of an option with strike $K_{i}$ , the trader will put the current values of $S_{t},t.$ , and $r$ and the quoted value of the implied volatility $\sigma_{i}$ at which the trade went through, in this formula. According to this interpretation, the BlackScholes formula is used to assign a dollar value to a quoted volatility. Conversely, given the correct option price $P(.)$ , the implied volatility, $\sigma_{i}$ , for the $K_{i}$ put could be extracted.  

We can now define the volatility smile within this context. Consider a series of $T_{\mathbf{\delta}}$ -expiration, liquid, and arbitrage-free out-of-the-money put option prices indexed by the strike prices $K_{i}$ , denoted respectively by $P_{K_{i}}$ :  

$$
P_{K_{1}},...,P_{K_{n}}
$$  

for  

$$
K_{n}<\ldots<K_{1}<K_{0}=S_{t}
$$  

According to this, the $K_{0}$ put is ATM and, as $K_{i}$ decreases, the puts go deeper out-of-the-money, see Figure 16.9.  

Then, given the (bid or ask) option prices, we can use the Black Scholes formula backward and extract $\sigma_{i}$ that the trader used to conclude the deal on $P_{K_{i}}$ . If the assumptions of the Black Scholes world are correct, all the implied volatilities would turn out to be the same  

$$
\sigma_{K_{0}}=\sigma_{K_{1}}=\dots=\sigma_{K_{n}}=\sigma
$$  

![](a3c97d7d099c13ce396d587e768ab1db6132520815eda27496b20d60bb2ab198.jpg)  

# FIGURE 16.9  

Volatility smile: implied volatility against strike price.  

since the put options would be identical except for their strike price. Thus, in a market that conforms to the Black Scholes world, the traders would use the same $\sigma$ in the Black Scholes put formula to obtain each $P_{K_{i}},i=0,...,n.$ . Going backward, we would then recover the same constant $\sigma$ from the prices.12  

Yet, if we conducted this exercise in reality with observed option prices, we would find that the implied volatilities would satisfy  

$$
\sigma_{K_{0}}<\sigma_{K_{1}}<\cdots<\sigma_{K_{n}}
$$  

In other words, the more out-of-the-money the put option is, the higher the corresponding implied volatility. As a result, we would obtain a “smiley” curve.  

We can also use the implied vols from progressively out-of-the-money call options and obtain, depending on the underlying instrument, the second half of the smile, as shown in Figure 16.10.  

# 16.11.1 SOME STYLIZED FACTS  

Volatility smiles observed in reality seem to have the following characteristics,  

1. Options written on equity indices yield, in general, a nonsymmetric one-sided “smile” as shown in Figure 16.10a. For this reason, they are often called skews.  

![](58081c544f13f0079f843049c4329b50c31dbd050857f39e3b5afffd9a8ca22d.jpg)  

# FIGURE 16.10  

Skew for equity indices and typical symmetric FX smile.  

2. The FX markets are quite different in this respect. They yield a more or less symmetric smile, as in Figure 16.10b. However, the smile will rarely be exactly symmetric and it is routine practice in foreign exchange markets to trade this asymmetry using risk reversals.   
3. Options on various interest rates yield a more monotonous one-sided smile than the equity indices. The fact that “smile” patterns vary from market to market would suggest, on the surface, that there are different explanations involved.  

It is also natural to think that the dynamics of the smile vary depending on the sector. This point is relevant for risk management, running swaption, cap/floor books, and volatility trading. But, before we discuss it, we consider an example.  

# EXAMPLE  

Table 16.1 displays all the options written on the S&P100 index with a very short expiration. These data were obtained from live quotes early in the morning, so few trades had passed. However, the option bid ask quotes were live, in the sense that reasonably sized trades could be conducted on them.  

When the data were gathered, the underlying was trading at 589.14. We use 12 out-of-themoney puts and 9 out-of-the-money calls to obtain the Black Scholes implied volatilities.  

The interest rate is taken to be $1.98\%$ , and the time to expiration was 8/365. Using these values and the bid prices for the options given in the table, the equations  

$$
\begin{array}{c}{C(S_{t},K_{i},r,T,\sigma_{i})=C_{i}}\\ {P(S_{t},K_{j},r,T,\sigma_{j})=P_{j}}\end{array}
$$  

were solved for the implied vols of calls $\{\sigma_{i}\}$ and the implied vols of puts $\{\sigma_{i}\}$ , $C_{i}$ and $P_{j}$ being observed option prices.  

<html><body><table><tr><td colspan="8">Table 16.1 OEX Options with January 18, 2002, Expiration</td></tr><tr><td>Calls</td><td>Bid</td><td>Ask</td><td>Vol</td><td> Puts</td><td> Bid</td><td>Ask</td><td>Vol</td></tr><tr><td>Jan 550</td><td>39.5</td><td>41.5</td><td>0</td><td> Jan 550</td><td>0.45</td><td>0.75</td><td>0</td></tr><tr><td>Jan 555</td><td>34.8</td><td>36.3</td><td>0</td><td>Jan 555</td><td>0.65</td><td>0.95</td><td>0</td></tr><tr><td>Jan 560</td><td>30</td><td>31.5</td><td>0</td><td>Jan 560</td><td>0.9</td><td>1.2</td><td>0</td></tr><tr><td>Jan 565</td><td>25.2</td><td>26.7</td><td>0</td><td>Jan 565</td><td>1.25</td><td>1.55</td><td>0</td></tr><tr><td>Jan 570</td><td>20.6</td><td>22.1</td><td>0</td><td>Jan 570</td><td>1.8</td><td>2.1</td><td>0</td></tr><tr><td>Jan 575</td><td>16.3</td><td>17.8</td><td>0</td><td>Jan 575</td><td>2.3</td><td>3</td><td>0</td></tr><tr><td>Jan 580</td><td>13</td><td>13.5</td><td>0</td><td>Jan 580</td><td>3.4</td><td>4.1</td><td>2</td></tr><tr><td>Jan 585</td><td>9.1</td><td>9.8</td><td>0</td><td>Jan 585</td><td>5</td><td>5.7</td><td>5</td></tr><tr><td>Jan 590</td><td>6.1</td><td>6.8</td><td>50</td><td>Jan 590</td><td>7.6</td><td>7.9</td><td>5</td></tr><tr><td>Jan 595</td><td>4.1</td><td>4.5</td><td>12</td><td>Jan 595</td><td>10.1</td><td>10.8</td><td>25</td></tr><tr><td>Jan 600</td><td>2.5</td><td>2.8</td><td>3</td><td>Jan 600</td><td>13.1</td><td>14.5</td><td>0</td></tr><tr><td>Jan 605</td><td>1.2</td><td>1.5</td><td>0</td><td>Jan 605</td><td>17.2</td><td>18.7</td><td>0</td></tr><tr><td>Jan 610</td><td>0.55</td><td>0.85</td><td>1</td><td>Jan 610</td><td>21.7</td><td>23.2</td><td>0</td></tr><tr><td>Jan 615</td><td>0.25</td><td>0.55</td><td>0</td><td>Jan 615</td><td>26.6</td><td>28.1</td><td>0</td></tr><tr><td>Jan 620</td><td>0.2</td><td>0.35</td><td>1</td><td>Jan 620</td><td>31.4</td><td>32.9</td><td>0</td></tr><tr><td>Jan 625</td><td>0.05</td><td>0.2</td><td>0</td><td>Jan 625</td><td>36.3</td><td>37.8</td><td>0</td></tr><tr><td>Jan 630</td><td>0</td><td>0.15</td><td>0</td><td>Jan 630</td><td>41</td><td>43</td><td>0</td></tr><tr><td>Jan 635</td><td>0</td><td>0.1</td><td>0</td><td>Jan 635</td><td>46</td><td>48</td><td>0</td></tr><tr><td>Jan 640</td><td>0</td><td>0.1</td><td>0</td><td>Jan 640</td><td>51</td><td>53</td><td>0</td></tr><tr><td>Jan 645</td><td>0</td><td>0.1</td><td>0</td><td>Jan 645</td><td>56.5</td><td>57.5</td><td>0</td></tr><tr><td>Jan 650</td><td>0</td><td>0.1</td><td>0</td><td> Jan 650</td><td>60.5</td><td>63.5</td><td>0</td></tr><tr><td>Jan 660</td><td>0</td><td>0.05</td><td>0</td><td>Jan 660</td><td>70.5</td><td>73.5</td><td>0</td></tr><tr><td>Jan 680</td><td>0</td><td>0.05</td><td>0</td><td>Jan 680</td><td>90.5</td><td>93.5</td><td>0</td></tr></table></body></html>  

![](11bafb19d5927d9cd0b0880a7ca5dea33795e1c335f5a4b5e8da7f93dbe52bca.jpg)  

# FIGURE 16.11  

Implied volatility of short-dated OEX options against moneyness.  

The resulting vols were plotted against $K_{i}/S_{t}$ in Figure 16.11. We see a pronounced smile. For example, the January 400 put, which traded at about $32\%$ out-of-the-money, had a volatility of about $26\%$ , while the ATM option traded at an implied volatility of $18.5\%$ .  

OEX options are of American style and this issue was ignored in the example above. This would introduce an upward bias in the calculated volatilities. This bias is secondary for our purpose, but in real trading should be corrected. One correction has been suggested by Barone-Adesi and Whaley (1987).  

# 16.11.2 HOW CAN WE DEFINE MONEYNESS?  

The way a smile is plotted varies from one market to another. The implied volatility, denoted by $\sigma_{i:}$ , always appears on the $y$ -axis. Unless stated otherwise, we extract this volatility from the Black Scholes formula in equity or FX markets, and from the Black formula in the case of interest rates. The implied volatilities are then treated as if they were random and time varying.  

What to put on the horizontal axis is a more delicate question and eventually depends on how we define “moneyness” of an option. Sometimes the smile is plotted against moneyness measured by the ratio of the strike price to the current market price, $K_{i}/S_{t}.$ . If the smile is a function of how much the option is out-of-the-money only, then this normalization will stabilize the smile in the sense that as $S_{t}$ changes, the smile for that particular option series may be more or less invariant. But there are almost always factors other than moneyness that affect the smile, and some practitioners define moneyness differently.  

For example, sometimes the smile is plotted against $K_{i}e^{-r(T-t)}/S_{t}$ . For short-dated options, this makes little difference, since $r(T-t)$ will be a small number. For longer-dated options, the difference is more relevant. By including this discount factor, market practitioners hope to eliminate the effect of the changes in the remaining life of the option.  

Sometimes the horizontal axis represents the option’s delta. FX traders take the size of delta as a measure of moneyness. This practice can be challenged on the grounds that an option’s delta depends on more variables than just moneyness. It also depends, for example, on the instantaneous implied volatility. Yet, as we will see later, there are some deltas at which volatility trading is particularly liquid in FX markets.  

The reader should note that the smile in Figure 16.9 is a plot of the implied volatility against the strike only. Figures 16.12 and 16.13 are plots of the implied volatility against the delta. These curves  

![](fed3cdc57f2e51511aa4cb598900e6d5f8f8ac45b72e747148bbeccfb949735c.jpg)  

# FIGURE 16.12  

![](175dfd538ad8b1cb8c5e49e7602679e28dfbe160ea69e6c1bbe0fda770d3fcee.jpg)  

# FIGURE 16.13  

Risk reversals and curvature of smile.  

relate to a particular time $t$ and expiration date $T.$ As the latter change, the smile will, in general, shift. It is quite important to know how changes in time $t$ and expiration date $T$ affect the smile.  

# 16.11.3 REPLICATING THE SMILE  

The volatility smile is a plot of the implied volatility of options that are alike in all respects except for their moneyness. The basic shape of the volatility smile has two major characteristics. The first relates to the extent of symmetry in the smile. The second is about how “pronounced” the curvature is. There are good approximations for measuring both characteristics.  

First, consider the issue of symmetry. Figure 16.12 shows three smiles for FX markets. One is symmetric, the other two are asymmetric with different biases. If the smile is symmetric, the volatilities across similarly out-of-the-money puts and calls will be the same. This means that if a trader buys a call and sells a put with the same moneyness, the structure will have zero value. Such positions were called risk reversals in Chapter 11. A symmetric smile implies that a zero cost risk reversal can be achieved by buying and selling similarly out-of-the-money options. In the case of asymmetric smiles, puts and calls with similar moneyness are sold at different implied volatilities, and this is labeled a bias. Thus, a risk reversal is one way of measuring the bias in a volatility smile.  

The way risk reversals measure the symmetry of the volatility smile is shown in Figure 16.13. We use the delta of the option as a measure of its moneyness on the $x$ -axis. ATM options would have a delta of around 50 and would be in the “middle” of the $x$ -axis. The volatility of the 25-delta risk reversal gives the difference between the volatilities of a 25-delta put and a 25-delta call as indicated in the graph. We can write this as  

$$
\sigma(25-d e l t a R R\mathrm{spread})=\sigma(25-d e l t a\mathrm{put})-\sigma(25-d e l t a\mathrm{call})
$$  

where $\sigma(25\$ -delta $R R$ spread), $\sigma(25$ -delta put), and $\sigma$ (25-delta call) indicate, respectively, the implied volatilities of a risk reversal, a 25-delta put, and a 25-delta call.  

![](edac6da314d45b279e1995a62648841a6c10745bbe141a3dd3ac36b8041f3332.jpg)  

# FIGURE 16.14  

Butterfly measures curvature of smile.  

The curvature of the smile can be measured using a butterfly. Consider the sale of an ATM put and an ATM call along with the purchase of one 25-delta out-of-the-money put and a 25-delta outof-the-money call. This butterfly has a payoff diagram that should be familiar from Chapter 11. The position consists of buying two symmetric out-of-the-money volatilities and selling two ATM volatilities. If there were no smile effects, these volatilities would all be the same and the net volatility position would be zero. On the other hand, the more pronounced the smile becomes, the higher the out-of-the-money volatilities would be relative to the ATM volatilities, and the net volatility position would become more and more positive. Figure 16.14 shows how a butterfly measures the magnitude of the curvature in a smile. The following equality holds:  

$$
\sigma(25-d e l t a\mathrm{butterflyspread})=\sigma(25-d e l t a\mathrm{put})+\sigma(25-d e l t a\mathrm{call})-2\sigma(\mathrm{ATM})
$$  

where the $\sigma(25\$ -delta butterfly spread) and $\sigma(\operatorname{ATM})$ are the butterfly and the ATM implied volatilities, respectively.  

# 16.11.3.1 Contractual equations  

Chapter 3 dealt with contractual equations for simple assets. The equalities discussed in the preceding paragraphs now permit considering quite different types of contractual equations. In fact, we can rearrange equalities shown in Eqs. (16.60) and (16.61) to generate some contractual equations for out-of-the-money implied volatilities:  

![](215656c0e942499516b574f6bf59f1bedaf40935f6ef5322ad356371fdf62907.jpg)  

These equalities can be used to determine out-of-the-money volatilities in the case of vanilla options. For example, if ATM, RR, and butterfly volatilities are liquid, we can use these equations to “calculate” 25-delta call and put volatilities. However, it has to be noted that for exotic options, adjusting the volatility parameter this way will not work. This issue will be discussed at the end of the chapter.  

# 16.12 SMILE DYNAMICS  

There are at least two types of smile “dynamics.” In the first, we would fix the time parameter $t$ and consider options with longer and longer expirations, $T.$ . In the second case, we would keep $T$ constant, but let time $t$ pass and study how changes in various factors affect the volatility smile. In particular, we can observe if changes in $S_{t}$ affect the smile when the moneyness $K_{i}/S_{t}$ is kept constant.  

We first keep $t$ fixed and increase $T.$ . We consider two series of options that trade at the same time t. Both series have comparable strikes, but one series has a relatively longer maturity. How would the smiles implied by the two series of options with expirations, say, $T_{1}$ , $T_{2}$ , compare with each other?  

The second question of interest is how the smile of the same option series moves over time as $S_{t}$ changes. In particular, would the smile be a function of the ratio $K_{i}/S_{t}$ only, or would it also depend on the level of $S_{t}$ over and above the moneyness?  

The answers to these questions change depending on which underlying asset is considered. This is because there is more than one explanation for the existence of the smile, and for different sectors, different explanations seem to prevail. Thus, before we analyze the smile dynamics and its properties any further, we need to discuss the major explanations advanced for the existence of the volatility smile.  

# 16.13 HOW TO EXPLAIN THE SMILE  

The volatility smile is an empirical phenomenon that violates the assumptions of the Black Scholes world. At the same time, the volatility smile is related to the implied volatilities obtained from the Black Scholes formula. This may give rise to confusion. The smile suggests that the Black Scholes formula is not valid, while at the same time, the trader obtains the smile using the very same Black Scholes formula. Is there an internal inconsistency?  

The answer is no. To clarify the point, we use an analogy that is unrelated to the present discussion, but illustrates what market conventions are. Consider the 3-month LIBOR rate $L_{t}$ . What is the present value of, say, $\$100$ that will be received in 3 months’ time? We saw in Chapter 3 that all we need to do is calculate the ratio:  

$$
\frac{100}{(1+L_{t}\frac{1}{4})}
$$  

An economist who is used to a different decompounding may disagree and use the following present value formula:  

$$
\frac{100}{(1+L_{t}){\frac{1}{4}}}
$$  

Who is right? The answer depends on the market convention. If $L_{t}$ is quoted under the condition that formula (16.64) be used, then formula (16.65) would be wrong if used with the same $L_{t}$ . However, we can always calculate a new $L_{t}^{*}$ using the equivalence:  

$$
\frac{100}{(1+L_{t}\frac{1}{4})}=\frac{100}{(1+L_{t}^{*})\frac{1}{4}}
$$  

Then, the formula  

$$
\frac{100}{(1+L_{t}^{*}){\frac{1}{4}}}
$$  

used with $L_{t}^{*}$ would also yield the correct present value. The point is, the market is quoting an interest rate $L_{t}$ with the condition that it is used with formula (16.64). If for some odd reason a client wants to use formula (16.65), then the market would quote $L_{t}^{*}$ instead of $L_{t}$ . The result would be the same since, whether we use formula (16.64) with $L_{t}$ , as the market does, or formula (16.65) with $L_{t}^{*}$ , we would obtain the same present value. In other words, the question of which formula is correct depends on how the market quotes the variable of interest.  

This goes for options also. The Black Scholes formula may be the wrong formula if we substitute one particular volatility, but may give the right answer if we use another volatility. And the latter may be different than the real-world volatility at that instant. But traders can still use a particular volatility to obtain the right option price from this “wrong” formula, just as in the earlier present value example. This particular volatility, when associated with the Black Scholes formula, may give the correct value for the option even though the assumptions leading to the formula are not satisfied.  

Thus, suppose the arbitrage-free option price obtained under the “correct” assumptions is given by  

$$
C(S_{t},t,T,K,\sigma_{t}^{*},\theta_{t})
$$  

where $K$ is the strike price, $T$ is the expiration date, and $S_{t}$ is the underlying asset price. The (vector) variable $\theta_{t}$ represents all the other parameters that enter the “correct” formula and that may not be taken into account by the Black Scholes world. For example, the volatility may be stochastic, and some parameters that influence the volatility dynamics may indirectly enter the formula and be part of $\theta_{t}$ .13 The critical point here is the meaning that is attached to $\boldsymbol{\sigma}_{t}^{*}$ . We assume for now that it is the correct instantaneous volatility as of time $t.$ .  

The (correct) pricing function in Eq. (16.68) may be more complex and may not even have a closed-form solution in contrast to the Black Scholes formula, $F(S_{t},\ t,\ \sigma)$ . Suppose traders ignore Eq. (16.68) but prefer to use the formula $F(S_{t},\ t,\ \sigma)$ , even though the latter is “wrong.” Does this mean traders will calculate the wrong price?  

Not necessarily. The “wrong” formula $F(S_{t},t,\sigma)$ can very well yield the same option price as $C$ $(S_{t},t,K,\sigma_{t}^{*},\theta_{t})$ if the trader uses in $F(S_{t},t,\sigma)$ , another volatility, $\sigma$ , such that the two formulas give the same correct price:  

$$
C(S_{t},t,K,\sigma_{t}^{*},\theta_{t})=F(S_{t},t,\sigma)
$$  

Thus, we may be able to get the correct option price from the “unrealistic” Black Scholes formula if we proceed as follows:  

1. We quote the $K_{i}$ -strike option volatilities $\sigma_{i}$ directly at every instant $t$ , under the condition that the Black Scholes formula be used to obtain the option value. Then, liquid and arbitrage-free markets will supply “correct” observations of the ATM volatility $\sigma_{0}$ .14   
2. For out-of-the-money options, we use the BlackScholes formula with a new volatility denoted by $\sigma((S/K_{i}),S)$ , and  

$$
\sigma\biggl({\frac{S}{K_{i}}},S\biggr)=\sigma_{0}+f\biggl({\frac{S}{K_{i}}},S\biggr)
$$  

where $f(.)$ is, in general, positive and implies a smile effect. The adjustment made to the ATM volatility, $\sigma_{0}.$ , is such that when $\sigma((S/K_{i}),S)$ is used in the Black Scholes formula, it gives the correct value for $K_{i}$ strike option:  

$$
F{\Bigg(}S_{t},t,K_{i},\sigma_{0}+f{\Bigg(}{\frac{S}{K_{i}}},S{\Bigg)}{\Bigg)}=C(S_{t},t,K_{i},\sigma_{t}^{*},\theta_{t})
$$  

The adjustment factor $f((S/K_{i}),S)$ is determined by the trader’s experience, knowledge, and the trading environment at that instant. The relationships between risk reversal, butterfly, and ATM volatilities discussed in the previous section can also be used here.15  

The trader, thus, adjusts the volatility of the non-ATM options so that the wrong formula gives the correct answer, even though what is used in the Black Scholes formula may not be the “correct” instantaneous realized volatility of the $S_{t}$ process.  

The $f((S/K_{i}),S)$ is, therefore, an adjustment required by the imperfections of the Black Scholes formula in adequately representing the real-world environment. The upshot is that when we plot $\sigma((S/K_{i}),S)$ against $K_{i}/S$ or $K_{i}$ we get a smile, or a skew curve, depending on the time and the sector we are working with.  

For what types of situations should the volatilities be adjusted? At least three inconsistencies of the Black Scholes assumptions with the real world can be corrected for by adjusting the volatilities across the strike $K_{i}$ . The first is the lognormal process assumption. The second is the fact that if asset prices fall dramatically during a relatively short period of time, this could increase the “fear factor” and volatility would increase. The third involves the organizational and regulatory assumptions concerning financial markets. We discuss these in more detail next.  

# 16.13.1 CASE 1: NONGEOMETRIC PRICE PROCESSES  

Suppose the underlying obeys the true risk-neutral dynamics described by the SDE:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t+\sigma S_{t}^{\alpha}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

With $\alpha=1,\ S_{t}$ would be lognormal. Everything else being conformable to the Black Scholes world, there would be no smile in the implied volatilities.  

The case of $\alpha<1$ would require an adjustment to the volatility coefficient used in the Black Scholes formula as the strike changes. This is true, since, unlike in the case of $\alpha=1$ , now the percentage volatility is dependent on the level of $S_{t}$ . We divide by $S_{t}$ to obtain  

$$
{\frac{\mathrm{d}S_{t}}{S_{t}}}=r\mathrm{d}t+\sigma S_{t}^{\alpha-1}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

The percentage volatility is given by the term $\sigma S_{t}^{\alpha-1}$ . This percentage volatility will be a decreasing function of $S_{t}$ if $\alpha<1$ . As $S_{t}$ declines, the percentage volatility increases. Thus, the trader needs to use higher implied volatility parameters in the Black Scholes formula for put options with lower and lower strike prices. This means that the more out-of-the-money the put option is, the higher the volatility used in the Black Scholes formula must be.  

This illustrates the idea that although the trader knows that the Black Scholes world is far from reality, the volatility is adjusted so that the original Black Scholes framework is preserved and that a “wrong” formula can still give the correct option value.  

# 16.13.2 CASE 2: POSSIBILITY OF CRASH  

Suppose a put option series has an expiration of 2 months. All options are identical except for their strike. They run from ATM to deep out-of-the-money. Suppose also that the current level of $S_{t}$ is 100. The liquid put options have strikes 90, 80, 70, and 60.  

Here is what the 90-strike option implies. If the option expires in-the-money, then the market would have fallen by at least $10\%$ in 2 months. This is a big fall, perhaps, but not a disaster. In contrast, if the 60-strike put expires in-the-money, this would imply a $40\%$ drop in 2 months. This is clearly an unusual event, and unusual events lead to sudden spikes in volatility. Thus, the 60-strike option is relatively more associated with events that are labeled as crises and, everything else the same, this option would, in all likelihood, be in-the-money when the volatility is very high. But when this option becomes in-the-money, its gamma, which originally is close to zero, will also be higher. Thus, the trader who sells this option would have higher cash payouts due to delta hedge adjustments. So, to compensate for these potentially higher cash payments, the trader would use higher and higher vol parameters in put options that are more and more out-of-the-money, and, hence, are more and more likely to be associated with a crisis situation.  

This explanation is consistent with the smiley shapes observed in reality. Note that in FX markets, sudden drops and sudden increases would mean higher volatility because in each case one of the observed currencies could be falling dramatically. So the smile will be more or less symmetric. But in the case of equity markets, a sudden increase in equity prices may be an important event, but not a crisis at all. For traders (excluding the shorts) this is a “happy” outcome, and the volatility may not increase much. In contrast, when asset prices suddenly crash, this increases the fear factor and the volatilities may spike. Thus, in equity markets the smile is expected to be mostly one-sided if this explanation is correct. It turns out that empirical data support this contention. Out-of-the-money equity puts have a smile, but out-of-the-money equity calls exhibit almost no smile.  

# EXAMPLE  

Consider Table 16.2 which displays the prices of options with June 2002 expiry, on January 10, 2002, and ignore issues related to Americanness or any possible payouts. These data are collected at the same time as those discussed in the earlier example. In this case, the options are longer dated and expire in about 6 months. First, we obtain the volatility smile for these data.  

The data are collected at the same instant, and since the current value of the underlying index is the same in each case, the division by $S_{t_{0}}$ is not a major issue, but we still prefer to graph the volatility smile against the $K/S$ .  

We extract ask prices for the 8 out-of-the-money puts and consider the 600-put as being in-the-money. This way we can calculate nine implied vols. The price data that we use are shown in Table 16.2. We consider first the out-of-the-money put asking prices listed in the sixth column of this table. This will give nine prices.  

<html><body><table><tr><td colspan="6">Table 16.2 OEX Options with June 21, 2002, Expiry (Collected 9:46 CBOT on January 10, 2002)</td></tr><tr><td>Calls</td><td>Bid</td><td>Ask</td><td> Puts</td><td>Bid</td><td>Ask</td></tr><tr><td>Jun 440</td><td>153.4</td><td>156.4</td><td>Jun 440 Jun 460</td><td>4.2 5.6</td><td>4.8</td></tr><tr><td>Jun 460</td><td>134.8</td><td>137.8</td><td> Jun 480</td><td></td><td>6.3</td></tr><tr><td>Jun 480</td><td>116.7 99.2</td><td>119.7 102.2</td><td> Jun 500</td><td>7.4 9.9</td><td>8.1 10.6</td></tr><tr><td>Jun 500</td><td>82.6</td><td>85.6</td><td> Jun 520</td><td>12.9</td><td>14.4</td></tr><tr><td>Jun 520 Jun 540</td><td>67.2</td><td>69.7</td><td> Jun 540</td><td>17.2</td><td>18.7</td></tr><tr><td>Jun 560</td><td>52.7</td><td>55.2</td><td> Jun 560</td><td>22.7</td><td></td></tr><tr><td>Jun 580</td><td>39.8</td><td>41.8</td><td>Jun 580</td><td></td><td>24.2</td></tr><tr><td>Jun 600</td><td>28.6</td><td></td><td> Jun 600</td><td>29.3</td><td>31.3</td></tr><tr><td></td><td>19.9</td><td>30.6 21.4</td><td>Jun 620</td><td>38.3</td><td>40.3</td></tr><tr><td>Jun 620</td><td>12.8</td><td>14.3</td><td> Jun 640</td><td>49.5</td><td>51.5</td></tr><tr><td>Jun 640</td><td>8</td><td>8.7</td><td> Jun 660</td><td>62.2</td><td>64.7</td></tr><tr><td>Jun 660</td><td>4.7</td><td>5.4</td><td> Jun 680</td><td>76.9</td><td>79.9</td></tr><tr><td>Jun 680</td><td></td><td></td><td></td><td>93.7</td><td>96.7</td></tr><tr><td>Jun 700</td><td>2.55</td><td>3.2</td><td> Jun 700</td><td>111.6</td><td>114.6</td></tr></table></body></html>  

Ignoring other complications that may exist in reality, we use the Black Scholes formula straightforwardly with  

$$
S_{t_{0}}=589.15,r=1.90\%,t=\frac{152}{365}=0.416
$$  

We solve the equations  

$$
P(589.15,K_{i},1.90,\sigma_{K_{i}},0.416)=P_{K_{i}}\quad i=1,...,9
$$  

and obtain the nine implied volatilities $\sigma_{K_{i}}$ . Using Mathematica, we obtain the following result, which shows the value of $K_{i}/S$ and the corresponding implied vols for out-of-the-money puts:  

<html><body><table><tr><td>K-S</td><td>Vol</td></tr><tr><td>0.74</td><td>0.26</td></tr><tr><td>0.78</td><td>0.26</td></tr><tr><td>0.81</td><td>0.26</td></tr><tr><td>0.84</td><td>0.25</td></tr><tr><td>0.88</td><td>0.25</td></tr><tr><td>0.91</td><td>0.24</td></tr><tr><td>0.95</td><td>0.23</td></tr><tr><td>0.98</td><td>0.22</td></tr><tr><td>1.01</td><td>0.21</td></tr></table></body></html>  

This is shown in Figure 16.15. Clearly, as the moneyness of the puts decreases, the volatility increases. Option market makers will conclude that, if in 6 months, US equity markets  

![](a6647095e146f87e6cda22953fd174d085bfbd7dc74b871e27151ad3a6616418.jpg)  

# FIGURE 16.15  

Implied volatility of OEX options against moneyness.  

were to drop by $25\%$ , then the fear factor would increase volatility from $21\%$ to $26\%$ . By selecting the seven out-of-the-money call prices, we get the implied vols for out-of-themoney calls.  

<html><body><table><tr><td>K-S</td><td>Vol</td></tr><tr><td>0.98</td><td>0.23</td></tr><tr><td>1.01</td><td>0.22</td></tr><tr><td>1.05</td><td>0.21</td></tr><tr><td>1.08</td><td>0.20</td></tr><tr><td>1.12</td><td>0.19</td></tr><tr><td>1.15</td><td>0.19</td></tr><tr><td>118</td><td>0.18</td></tr></table></body></html>  

Here, the situation is different. We see that as moneyness of the calls decreases, the volatility also decreases.  

Option market makers may now think that if, in 6 months, US equity markets were to increase by $20\%$ , then the fear factor would decrease and so would volatility.  

The fear of a crash that leads to a smile phenomenon can, under some conditions, be represented analytically using the so-called jump processes. We discuss this modeling approach next.  

# 16.13.2.1 Modeling crashes  

Consider again the standard geometric Brownian motion case:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}\quad t\in[0,\infty)
$$  

$W_{t}$ is a Wiener process under the risk-neutral probability $\tilde{P}_{\l}$ . Now, keep the volatility parameterization the same, but instead, add a jump component as discussed in Lipton (2002). For example, let  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t-\sigma S_{t}\mathrm{d}W_{t}+S_{t}[(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}t]\quad t\in[0,\infty)
$$  

Some definitions are needed regarding the term $(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}$ t. The $j$ is the size of a random logarithmic jump. The size of the jump is not related to the occurrence of the jump, which is represented by the term $\mathrm{d}J_{t}$ . If the jump is of size zero, then $(e^{j}-1)=0$ and the jump term does not matter.  

The term $\mathrm{d}J_{t}$ is a Poisson-type process. In general, at time $t$ , it equals zero. But, with “small” probability, it can equal one. The probability of this happening depends on the length of the interval we are looking at, and on the size of the intensity coefficient $\lambda$ . The jump can heuristically be modeled as follows:  

$$
\mathrm{d}J_{t}={\left\{\begin{array}{l l}{0}&{{\mathrm{with~probability}}(1-\lambda\mathrm{~d}t)}\\ {1}&{{\mathrm{with~probability}}\lambda\mathrm{~d}t}\end{array}\right.}
$$  

where $0<\mathrm{d}t$ is an infinitesimally short interval. Finally, $m$ is the expected value of $(e^{j}-1)$ :  

$$
E_{t}^{\tilde{P}}[(e^{j}-1)]=m
$$  

Thus, we see that, for an infinitesimal interval we can heuristically write  

$$
\begin{array}{r l}&{E_{t}^{\tilde{P}}[(e^{j}-1)\mathrm{d}J_{t}]=E_{t}^{\tilde{P}}[(e^{j}-1)]E_{t}^{\tilde{P}}[\mathrm{d}J_{t}]}\\ &{\qquad=m[0.(1-\uplambda\mathrm{d}t)+1.\uplambda\mathrm{d}t]}\\ &{\qquad=m\uplambda\mathrm{d}t}\end{array}
$$  

According to this, the expected value of the term $(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}t$ is zero.  

This jump-diffusion model captures some crash phenomena. Stock market crashes, major defaults, 9/11-type events, and currency devaluations can be modeled as rare but discrete events that lead to jumps in prices.  

The way these types of jumps create a smile can be heuristically explained as follows. In a world where the Black Scholes assumptions hold, with a geometric $S_{t}$ process, a constant volatility parameter $\tilde{\sigma}$ , and no jumps, the volatility trade yields the arbitrage relation:  

$$
\frac{1}{2}C_{s s}\tilde{\sigma}^{2}S^{2}+C_{t}+r C_{s}S-r C=0
$$  

With a jump term added to the geometric process as in Eq. (16.77), the corresponding arbitrage relation becomes  

$$
\frac{1}{2}C_{s s}^{*}\sigma^{2}S^{2}+C_{t}^{*}+(r-\lambda m)C_{s}^{*}S-r C^{*}+\lambda E_{t}^{\tilde{P}}\left[C^{*}(S e^{j},t)-C^{*}(S,t)\right]=0
$$  

where $\Tilde{P}$ is the risk-neutral probability. Suppose we decide to use, as a convention, the Black Scholes formula, but believe that the true PDE is the one in Eq. (16.83). Then, we would select $\tilde{\sigma}$ such that the Black Scholes formula yields the same option value as the other PDE would yield.  

For example, out-of-the-money options will have much smaller gammas, $C_{s s}$ . If the expected jump is negative, then $\tilde{\sigma}$ will be bigger, and the more out-of-the-money the options are. As the expiration date $T$ increases, $C_{s s}$ will increase and the smile will be less pronounced.  

# 16.13.3 OTHER EXPLANATIONS  

Many other effects can cause a volatility smile. One is stochastic volatility. Consider a local volatility specification using  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}^{\alpha}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

with, say, $\alpha<1$ . In this specification, percentage volatility will be stochastic since it depends on the random variable $S_{t}$ . But often this specification does not express what is meant by models of stochastic volatility. What is captured by stochastic volatility is a situation where an additional Wiener process $\mathrm{d}B_{t}$ , possibly correlated with $\mathrm{d}W_{t}$ , affects the dynamics of percentage volatility. For example, we can write  

$$
\begin{array}{r l}&{\mathrm{d}S_{t}=\mu S_{t}\mathrm{~d}t+\sigma_{t}S_{t}\mathrm{~d}W_{t}\quad t\in[0,\infty)}\\ &{\mathrm{d}\sigma_{t}=a(\sigma_{t},S_{t})\mathrm{d}t+\kappa\sigma_{t}\mathrm{~d}B_{t}\quad t\in[0,\infty)}\end{array}
$$  

where $\kappa$ is the parameter representing the (constant) percentage volatility of the volatility of $S_{t}$ . In this model, the volatility itself is driven by some random increments that originate in the volatility market only. These shocks are only partially correlated with the innovation terms $\mathrm{d}W_{t}$ affecting the price data.  

It can be shown that stochastic volatility generates a volatility smile. In fact, with stochastic volatility, we can perform an analysis similar to the PDE with a jump process (Lipton, 2002). The result will essentially be similar. However, it is important to emphasize that, everything else being the same, this model may be incomplete in the sense that there may not be enough instruments to hedge the risks associated with $\mathrm{d}W_{t}$ and $\mathrm{d}B_{t}$ completely, and form a risk-free, self-financing portfolio. The jump-diffusion model discussed in the previous section may entail the same problem. To the extent that the jump part and the diffusion part are affected by different processes, the model may not be complete.  

# 16.13.3.1 Structural and regulatory explanations  

Tax effects (Merton, 1976) and the capital requirements associated with carrying out-of-the-money options in options books may also lead to a smile in implied volatility. We briefly touch on the second point.  

The argument involves the concept of gamma. A negative gamma position is considered to be more risky, the more out-of-the-money the option is. Essentially, negative gamma means that the market maker has sold options and delta hedged them, and that he or she is paying the gamma through the rebalancing of this hedge. If the option is deep out-of-the-money, gamma would be close to zero. Yet, if the option suddenly becomes in-the-money, the gamma could spike, especially if the option is about to expire. This may cause significant losses. Out-of-the-money options, therefore, involve substantial risk and require more capital. Due to such costs, the market maker may want to sell the out-of-the-money option at a higher price than warranted by the ATM volatility.  

# 16.14 THE RELEVANCE OF THE SMILE  

The volatility smile is important in financial engineering for at least three reasons.  

First, if we associate a volatility smile with all the risk factors, and if this smile shifts randomly over time, then we may be able to trade it, take spread positions, and arbitrage it. The smile dynamics, thus, imply new opportunities for a market professional.  

The second reason for the relevance of the volatility smile is that it may contain important information about the dynamics of the underlying realized volatility processes. With a volatility smile, pricing and hedging may become much more complicated, especially if the instrument has characteristics of an exotic option. Is volatility constant or a stochastic process? If the latter is the case, then what type of stochastic process is it? Are there jumps or is a process with Wiener-type increments a sufficiently good approximation? These questions are important for risk management and pricing.  

Third, the creation of new products and synthetics must pay attention to the causes of the smile. If the smile is the result of conventions and practices adopted by market professionals rather than resulting from the underlying volatility processes, we must take these conventions into account. We now discuss these issues in more detail and provide some examples to the uses of the volatility smile.  

# 16.15 TRADING THE SMILE  

The volatility smile is actively traded to a different extent in different sectors. The smile is an integral part of daily trading in the FX sector. Here, market practitioners routinely quote risk reversals, which relate to the symmetry in exchange rate volatility and butterflies related to the curvature of the smile. Traders trade and arbitrage these effects. The volatility smile is also traded in the equity sector. Traders arbitrage volatility across stock market indices, and in doing this, sometimes trade the smile indirectly. At other times, this trade is direct. The smile relating to a risk may be too steep and is expected to flatten. The trader then sells the deep out-of-the-money options and buys those that are closer to being ATM. In the interest rate sector, volatility smile is mainly traded due to its risk management and hedging implications for cap/floor positions and swaption books.  

Smiles can be of interest to investors who may want to take positions on the slope and the curvature of the volatility smile, thinking that the market has under- or overemphasized one of the underlying parameters. In the following example, traders are putting together skew swaps that will trade realized skews against implied skews.  

# EXAMPLE  

As the skew in volatility between out-of-the-money puts and calls on Standard & Poor’s 500 index has grown, street traders are looking to capture discrepancies between the realized and implied skews of the options. One trader in New York noted interest in a skew swap on the S&P500 from hedge funds trading volatility. The swaps—which traders believe would be a first—would offer the realized skew of puts and calls in return for the implied skew.   
Currently, the S&P skew is above 30—if strikes on puts and calls are moved by $10\%$ , the volatility would [increase by] $3\%$ , explained one structurer. This compares with a level of 15 at the beginning of October, which is in line with the historical levels of 15 20.   
One structurer who had tried to put together a skew swap noted that there is no mathematical formula that can capture implied skews for any period of time. He also admitted to being stumped by hedging the product. “To hedge this, we would have to close every night with a vol swap on the deal and that can’t always be done,” he said. A rival noted that one popular trade to capture flattening skews is selling out-ofthe-money puts and calls and buying ATM puts and calls.  

(Derivatives Week (now part of GlobalCapital), November 1998)  

One interesting point in this reading is that, at least in this particular case, the observed smile (skew) is characterized by multiplying a linear relationship with a slope of 3. According to the traders, if moneyness decreases by $10\%$ , volatility increases by $3\%$ . Traders expect this relationship to be around 15 during normal times. Hence, the smile is expected to flatten.  

# 16.16 PRICING WITH A SMILE  

Pricing and hedging are fairly closely related activities, at least in abstract settings. Once an asset is replicated with liquid securities, the price of the asset is the cost of the replicating portfolio plus some profit margin. At several points in the previous chapters, we saw that assets can be replicated using a series of options with different strike prices. This was the method applied for finding a hedge for a volatility swap in Chapter 15, for example. The replicating portfolio was made of a weighted sum of relevant options with the same characteristics except for their strikes. In Chapter 12, we saw that option portfolios could replicate statically almost any future payoff function. Again, these options were similar except for their strike prices.  

The potential use of options with different strikes makes the volatility smile a crucial parameter in forming hedging portfolios and in pricing complex instruments. In fact, if implied volatilities depend on the moneyness of the option, then the volatility parameters used in formulas for replicating portfolios would automatically change as the markets move and the moneyness of the replicating options changes. The critical point is that this will be true even if the underlying realized volatility remains the same. This section presents two examples of this phenomenon.  

The first involves the class of interest rate derivatives known as caps and floors. These are among the most widely traded instruments. Their hedging and pricing are influenced in a crucial way if there is a volatility smile. The second involves the pricing and hedging of exotic options. Here also, the methodology and market practices crucially depend on the existence of the volatility smile.  

# 16.17 EXOTIC OPTIONS AND THE SMILE  

The second major category of instruments where the existence of the volatility smile can change pricing and hedging practices significantly is exotic options. In this section, we consider a simple knock-out call that is representative of the main ideas we want to convey. Due to the contractual equation between vanilla options, knock-out calls, and knock-in calls, our discussion immediately extends to knock-in calls as well. At the end of this section, we briefly discuss digital options and how the existence of the volatility smile affects them.  

# 16.17.1 A HEDGE FOR A BARRIER  

Knock-out calls were discussed in Chapters 9 and 11. As a reminder, a simple knock-out call is similar to a European vanilla call with strike $K$ and expiration $T_{\mathrm{{:}}}$ written on the underlying $S_{t},$ , except that the option will cease to exist if, during the life of the option, $S_{t}$ falls below barrier $H$ :  

$$
S_{t}<H\quad t\in[t_{0},T]
$$  

The price of a knock-out barrier approaches the price of a vanilla call as the option becomes more in-the-money. However, as the underlying approaches the barrier, the value of the knock-out will approach zero.  

There are several ways of hedging knock-out options used by practitioners. Here, we explain a hedge that (i) has nice financial engineering implications and (ii) shows clearly the important role played by the smile.  

Suppose we bought the corresponding vanilla call and sold a carefully chosen out-of-the money vanilla put with strike $K^{*}$ , $K^{*}<K.$ , with a very precise objective. We want the put and the call to be such that, as $S_{t}$ approaches the barrier $H$ , the portfolio’s value becomes zero. This portfolio, which is, in fact, a type of risk reversal, approximately replicates the knock-out option. If $S_{t}$ moves away from $H_{;}$ , the put becomes more out-of-the-money, and its value will decline. Then the portfolio looks more and more like a vanilla call. This is what the knock-out option accomplishes anyway. On the other hand, as $S_{t}$ approaches $H$ , the put becomes more valuable. If it is carefully chosen, at $H$ the value of the put position can equal the value of the vanilla call and the portfolio would have zero value. This is, again, what the knock-out option accomplishes near $H.$ . As $S_{t}$ falls below $H.$ , the portfolio has to be liquidated. Thus, the portfolio of  

$$
K^{*}\mathrm{-Put,Longone}K\mathrm{-}\mathrm{Call}\}
$$  

replicates the knock-out call if $x$ and $K^{*}$ are appropriately selected. One way to do this is to use the “symmetry” principle.  

Suppose there is no smile effect and that all options with different strikes that belong to a series have the same volatility. Then we can choose $x$ and $K^{*}$ as follows. We want the value of $x$ units of the $K^{*}$ put to equal the value of the vanilla call when $H{\gets}S_{t}$ . This can be achieved by choosing $K^{*}$ such that  

$$
K^{*}\cdot K=H^{2}
$$  

The prices of these options are assumed to satisfy  

$$
\frac{K^{*}\ \mathrm{put}}{K\mathrm{call}}=\sqrt{\frac{K^{*}}{K}}
$$  

This means that if $x$ is chosen so that  

$$
x=\frac{K}{K^{*}}
$$  

then the value of $x$ units of these $K^{*}$ puts would equal the value of the $K$ call as $S_{t}$ approaches $H$ . As a result, the portfolio would replicate the knock-out call, except that once the barrier is hit, the portfolio needs to be liquidated.  

# 16.17.2 EFFECTS OF THE SMILE  

Consider first the effect of a stable volatility smile on this procedure. If the smile does not shift over time, then it is easy to incorporate the effect into the previous replicating portfolio. Suppose the smile is downward sloping over $[K^{*},K]$ . Then, one could plug different volatility parameters in Black Scholes formulas for each vanilla option. The same $K^{*}$ put selected earlier would be relatively more valuable than in the case of a flat smile. This means that the knockout option could be sold at a cheaper price. If the smile was upward sloping over the range, then the reverse would be true and the knockout would be more expensive. Hence, the smile has a direct effect that needs to be taken into account in the pricing and hedging of the knockout.  

There is a second effect of the smile as well. Suppose the smile is not stable during the life of the option, and that it shifts as time passes. Then the logic of replication would fall apart since a smile that shifts over time would make the relative values of the call and the put differ from the originally intended ratio as $S_{t}$ approaches $H.$ . Given that in most markets the smile is unstable over time, the hedging technique by this replication is questionable. The pricing of the knock-out would also be unreliable.  

# 16.17.2.1 An example of technical difficulties  

We can look at the complications introduced by the volatility smile using knock-out pricing formulas in case all standard assumptions are satisfied. The pricing formula for knock-outs was given in Chapter 9. In particular, the price of a down-and-out call written on a stock $S_{t},$ , satisfying all standard assumptions, and paying no dividends, was given by  

$$
C^{b}(t)=C(t)-J(t)
$$  

where $C(t)$ is the value of a vanilla call, given by the standard Black Scholes formula, and where $J(t)$ is the “discount” that needs to be applied because the option may die if $S_{t}$ falls below $H$ during the life of the contract. The formula for $J(t)$ was  

$$
J(t)=S_{t}\left(\frac{H}{S_{t}}\right)^{(2(r-(1/2)\sigma^{2})/\sigma^{2})+2}N(c_{1})-K e^{-r(T-t)}\left(\frac{H}{S_{t}}\right)^{2(r-(1/2)\sigma^{2})/\sigma^{2}}N(c_{2})
$$  

where  

$$
c_{1,2}=\frac{\log(H^{2}/S_{t}K)+(r\pm\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

Note that just like the Black Scholes formula, this pricing function contains a single volatility parameter $\sigma$ . In the plain vanilla case, this parameter could be manipulated to make the formula yield the correct answer, even when the underlying assumptions do not hold. Thus, in a smile environment with nonconstant volatilities, the trader could use one value for volatility and make the formula yield the correct answer. In fact, this was used in pricing caps and floors even though the volatilities of the individual forward rates that are relevant to these instruments were different.  

Unfortunately, this approach is not guaranteed to work for the down-and-out call pricing formula given here if a volatility smile exists and if this smile is continuously (and stochastically) shifting over time. In fact, there may not be a single well-behaved volatility value to replace in Eq. (16.94) to obtain the correct price of the down-and-out call. Even when the realized and ATM implied volatilities remain the same, if the slope of the smile changes, the price of the down-andout call may change as in the previous argument. In fact, if the smile becomes less negatively sloped, the short put component of the replicating portfolio will become relatively less expensive and the value of the down-and-out call may increase. Hence, in the case of exotic options, the relationship between volatility adjustments and the correct option price may become much more complex as smile effects become significant.  

# 16.17.2.2 Pricing exotics  

Actual trading takes place in the presence of a volatility smile, and the prices of exotic options need to be set so as to take into account the future costs and benefits of adjusting the hedge to the exotic option. With the presence of smile, as time passes, the vega hedge of an exotic option book needs to be adjusted for the reasons explained earlier. As this happens, depending on the net position of the option book, the trader may realize some net cash gains or losses. The present value of these “expected” cash gains and losses needs to be incorporated into the market price. At the end, the market price of the exotic may be higher or lower than the theoretical price indicated by Eq. (16.94).  

# 16.17.3 THE CASE OF DIGITAL OPTIONS  

Chapter 11 showed that a theoretical replication of a European digital call with strike $K$ and expiration $T$ would be to buy $1/h$ units of the vanilla call with strike $K$ and to sell $1/h$ units of the vanilla call with strike $K+h$ . In this case $h$ would be the minimum tick in a futures market.  

If there is a volatility smile, then the prices of these vanilla calls would need to be adjusted since they have different strikes and, therefore, different volatilities. Of course, if $h$ is small, this volatility difference would be small as well, but then $1/h$ would be large and the position would involve buying and selling a large number of vanilla calls. With such numbers, small variations in volatilities can make a difference to the end result.16  

# 16.17.4 ANOTHER APPLICATION: RISK REVERSALS  

One of the most liquid ways of trading the smile is using risk reversals from FX markets. Consider options written on an exchange rate $\boldsymbol{e}_{t}$ . Fix the expiration at $T_{\cdot}$ and arrange the puts and calls by their strike price $K_{i}.$ . Then calculate these options’ deltas and consider a grid of reasonable deltas. We use the options’ deltas to represent the moneyness.  

A typical smile for these exchange rate options will then look like the one shown in Figure 16.13. It is a “symmetric” curve and is plotted in a two-dimensional graph having the percentage volatility on the vertical axis and the option’s delta on the $x\cdot$ -axis. In particular, consider the 25, 50, and 75-delta options.17  

We look at the following example.  

# EXAMPLE  

Activity in the dollar/yen foreign exchange markets over the past fortnight has emphasized the severe complexities associated with pricing exotic options. More importantly, it has provided sophisticated option houses with an opportunity to test their pricing theories against each other and against their less-advanced competitors. . .  

However, it was not the decline in the spot rate itself that provided the interest for options dealers but the resulting risk-reversal position. Risk-reversal is an expression of the directional preference in the market. If spot is expected to fall, as in the case of dollar/yen, then there will be greater demand for puts relative to calls, and so the volatility trader will pay a higher price for the puts than the calls. The upshot of this, said one commentator, is that volatility is not constant, as assumed by the standard Black Scholes option-pricing model, but instead changes according to the option delta.  

One-month dollar/yen risk reversal shot up to nearly 3 last week and has continued to hover at levels not seen since the summer of 1995. This extraordinary situation enabled sophisticated traders to find value in the pricing of their so-called naive counterparts.  

“A lot of banks must have learned a lot about risk-reversal over the past few days,” said one trader. According to market insiders, the less advanced houses failed to adequately account for the effects of riskreversal in pricing and hedging exotic structures such as knock-out and path-dependent options.  

They also asserted that simple off-the-shelf option pricing software was unable to cope with pricing exotic derivatives in a risk-reversal scenario. These packages did not allow the user to enter different volatilities for different deltas and so failed to capture the nuances of exotics pricing. However, other commentators argued that this too was an over-simplification and that other “thirdorder” effects came into play when hedging certain types of options in very high risk-reversal scenarios. They added that the third-order effects meant the barrier described might not be overpriced by the Black Scholes user, merely mispriced.  

(Thomson Reuters IFR Issue 1188, June 1997)  

As this reading illustrates, risk reversals are creations of the volatility smile in FX markets and are heavily traded. But, as indicated in the reading, market practitioners involved in riskreversal trading are clearly dealing with the underlying smile dynamics. The dynamics can become very complex. Pricing and hedging such positions on exotic options may become much more difficult.  

# 16.18 CONCLUSIONS  

The volatility smile is a fascinating topic in finance. Yet, it is also a complex phenomenon and more research needs to be done on its causes and on the ways to model it. This chapter offered a simple introduction. However, it has illustrated some of the essential points associated with this topic.  

# SUGGESTED READING  

Allen and Granger (2005) provide an excellent overview of techniques for trading equity correlation. The text by Brigo and Mercurio (2006) deals with the volatility smile in the interest rate sector. For equity smiles, the reader should consult the papers by Derman et al. (1994) and (1996), at a minimum. A comprehensive treatment of the volatility smile is provided in Lipton (2002). Taleb (1996) is the source that we used to discuss most market practices. There is also a flurry of papers dealing with empirical and theoretical issues involving the volatility smile. One recent source is Johnson and Lee (2003). The cited sources contain further references on the previous research.  

# EXERCISES  

1. Consider the following table displaying the bid ask prices for all options on the OEX index passed on January 10, 2002, at 9:46. These options have February 22, 2002, expiry and at the time of data collection, the underlying was at 589.14.  

<html><body><table><tr><td>Calls</td><td>Bid</td><td>Ask</td><td>Vol </td><td> Puts</td><td>Bid</td><td>Ask</td><td>Vol</td></tr><tr><td>Feb 400</td><td>188.9</td><td>191.9</td><td>0</td><td>Feb 400</td><td>0.05</td><td>0.2</td><td>0</td></tr><tr><td>Feb 420</td><td>169</td><td>172</td><td>0</td><td>Feb 420</td><td>0.1</td><td>0.4</td><td>0</td></tr><tr><td>Feb 440</td><td>149.2</td><td>152.2</td><td>0</td><td>Feb 440</td><td>0.25</td><td>0.55</td><td>0</td></tr><tr><td>Feb 460</td><td>129.4</td><td>132.4</td><td>0</td><td>Feb 460</td><td>0.45</td><td>0.75</td><td>0</td></tr><tr><td>Feb 480</td><td>109.6</td><td>112.6</td><td>0</td><td>Feb 480</td><td>0.8</td><td>1.1</td><td>0</td></tr><tr><td>Feb 500</td><td>90.2</td><td>92.7</td><td>0</td><td>Feb 500</td><td>1.4</td><td>1.7</td><td>0</td></tr><tr><td>Feb 520</td><td>71</td><td>73.5</td><td>0</td><td>Feb 520</td><td>2.5</td><td>2.8</td><td>0</td></tr><tr><td>Feb 530</td><td>61.6</td><td>64.1</td><td>0</td><td>Feb 530</td><td>2.8</td><td>3.5</td><td>0</td></tr><tr><td>Feb 540</td><td>52.4</td><td>54.9</td><td>0</td><td>Feb 540</td><td>3.7</td><td>4.4</td><td>0</td></tr><tr><td>Feb 550</td><td>43.8</td><td>45.8</td><td>0</td><td>Feb 550</td><td>4.9</td><td>5.6</td><td>1</td></tr><tr><td>Feb 560</td><td>35.4</td><td>37.4</td><td>0</td><td>Feb 560</td><td>6.6</td><td>7.3</td><td>0</td></tr><tr><td>Feb 570</td><td>27.9</td><td>29.4</td><td>0</td><td>Feb 570</td><td>8.9</td><td>9.6</td><td>0</td></tr><tr><td>Feb 580</td><td>20.8</td><td>22</td><td>0</td><td>Feb 580</td><td>11.8</td><td>12.8</td><td>0</td></tr><tr><td>Feb 590</td><td>14.8</td><td>15.8</td><td>0</td><td>Feb 590</td><td>15.8</td><td>16.8</td><td>1</td></tr><tr><td>Feb 600</td><td>10</td><td>10.7</td><td>1</td><td>Feb 600</td><td>20.8</td><td>22</td><td>0</td></tr><tr><td>Feb 610</td><td>6.1</td><td>6.8</td><td>0</td><td>Feb 610</td><td>27.1</td><td>28.6</td><td>0</td></tr><tr><td>Feb 615</td><td>4.6</td><td>5.3</td><td>0</td><td>Feb 615</td><td>31</td><td>32</td><td>0</td></tr><tr><td>Feb 620</td><td>3.4</td><td>4.1</td><td>0</td><td>Feb 620</td><td>34.3</td><td>36.3</td><td>0</td></tr><tr><td>Feb 630</td><td>1.9</td><td>2.2</td><td>0</td><td>Feb 630</td><td>42.8</td><td>44.8</td><td>0</td></tr><tr><td>Feb 640</td><td>0.9</td><td>1.2</td><td>0</td><td>Feb 640</td><td>52</td><td>54</td><td>0</td></tr><tr><td>Feb 650</td><td>0.4</td><td>0.7</td><td>0</td><td>Feb 650</td><td>61.4</td><td>63.9</td><td>0</td></tr><tr><td>Feb 660</td><td>0.15</td><td>0.45</td><td>0</td><td>Feb 660</td><td>71.2</td><td>73.7</td><td>0</td></tr><tr><td>Feb 680</td><td>0</td><td>0.25</td><td>0</td><td>Feb 680</td><td>90.8</td><td>93.8</td><td>0</td></tr><tr><td>Feb 700</td><td>0</td><td>0.2</td><td>100</td><td>Feb 700</td><td>110.8</td><td>113.8</td><td>0</td></tr></table></body></html>  

a. Using the out-of-the-money ask prices for the puts, calculate the implied volatility for the relevant strikes. Plot the volatility smile against K/S.   
b. Using the out-of-the-money bid prices for the puts, calculate the implied volatility for the relevant strikes. Plot the volatility smile against K/S. Are the bid ask spreads for these vols constant?   
c. Using the out-of-the-money ask prices for the calls, calculate the implied vol for the relevant strikes. Plot the volatility smile against K/S. When you put this figure together with the outof-the-money put volatilities, do you obtain a smile or a skew?  

# EXCEL EXERCISE  

2. (Stop-loss hedge). Write a VBA program to show the stop-loss hedged portfolio adjustments and cash flows for 100 long calls from the dealers’ perspective with the following data:  

$$
{\cal S}(0)=100;{\cal K}=100;{\cal T}=1;\quad r=8\%;\sigma=30\%;\&\mathrm{realized\volatility}=50\%
$$  

# MATLAB EXERCISES  

3. Write a MATLAB program to observe the volatility payoff of stop loss hedged long call position and measure the performance of this strategy of replicating long call position when the frequency of adjustment is increased during the time interval until the call expires. Use the following data for the calculation  

$$
{\cal S}(0)=100;{\cal K}=100;{\cal T}=1;\quad r=8\%;\sigma=30\%;\&\mathrm{realized\volatility}=50\%
$$  

Plot the graph for the volatility payoff for 30 instances for these sets of adjustment frequency [10, 20, 50, 100, 500]. Also show the performance of the method on the graph as a plot of mean return of the hedging strategy versus frequency of adjustment.  

4. (Stochastic volatility) Write a MATLAB program to observe the implied volatility smile for the option based on the stock price having stochastic volatility. Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\%\sigma=30\%;\sigma_{\sigma}=10\%,r_{\sigma}=10\%
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option.  

5. (Nongeometric Brownian motion) Write a MATLAB program to observe the implied volatility smile for the option based on the stock price following the dynamics of nongeometric Brownian motion. Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\mathcal{H};\sigma=30\mathcal{H};\alpha=0.8
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option. 6. (Stock price crashes and jumps)  

Write a MATLAB program to observe the implied volatility smile for the option based on the stock price having jumps (particularly crashes). Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\%;\sigma=30\%;\lambda=0.3;\alpha_{J}=-2\mathcal{U};\sigma_{J}=5\mathcal{U}
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option.  

7. (VIX calculation) Using the S&P 500 option data on the chapter website (collected on July 4, 2013 for options expiring on July 25, 2013), calculate the VIX index value following the procedure discussed in the book. Take the risk-free interest rate value to be $5\%$ for the purpose of calculation. Also highlight the strike price $K_{0}$ and show the contribution by strike for all the options.  