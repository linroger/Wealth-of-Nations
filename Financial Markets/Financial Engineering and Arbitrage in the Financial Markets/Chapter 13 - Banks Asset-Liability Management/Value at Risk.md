---
tags:
  - market_risk
  - risk_management
  - value_at_risk
  - var_calculation
  - yield_curve
aliases:
  - Market VaR
  - VaR
key_concepts:
  - Confidence level and horizon
  - Factor change data
  - Historical bootstrap method
  - Portfolio sensitivity to factors
  - 'VaR: critical value'
---

# 13.4 VALUE AT RISK  

The objective of the Market Value-at-Risk (VaR) analysis is to factorize the present value of assets and liabilities of a financial company and compute the loss that the present value would suffer if the factors fall into a $5\%$ 0r $1\%$ probability adverse "tail' event. There are two general distributional approaches in the banking industry used to define the tail event: historical non-parametric or normal (or log-normal) with a given volatility and correlation structure of the factors. The factors can be any variables (preferably observable and tradeable) that affect the institution's portfolio of assets and liabilities: equity indexes and individual stock prices, currency rates, and commodity prices, points on the government yield curve, swap spreads, other credit spreads, implied volatilities of interest rates, and equities.  

For a bank like Zions, the market VaR method boils down to extending our duration factorization to the moves in more yield curve points (3 month, 6 month, 1 year, 2 year, 3 year, 5 year, 10 year, 30 year), credit spreads/rates (TED, Fed funds, Prime, COFI), perhaps one or two currency rates (Mexican peso, Canadian dollar). The main extension is in all the yield curve points, the TED spread (LIBOR minus TBill), and a few swap spread variables. All the other factors are much less significant to the value of assets and liabilities. And the way we will proceed is very similar to our duration analysis. We will take the line items on the balance sheet and, instead of describing them with one duration sensitivity to parallel interest rate movements, we will describe each with several finer sensitivities to the movements along the specific yield curve points and spreads. (Roughly, the sensitivities have to add up to the duration.)  

Let us first go through some VaR definitions. In general, VaR, at a confidence level $c$ , over a given horizon period. $d$ , is defined as the critical value $P V^{*}$ , such that the probability that the profit $\widetilde{P V}$ will be lower or equal to $P V^{*}$ is equal to $1-c$ . That is,.  

$$
1-c=\operatorname{Prob}\left(\widetilde{P V}\leq P V^{*}\right)
$$  

There are two givens: the confidence level $c$ , equal to $95\%$ or $99\%$ , and the time horizon $d$ in years, e.g. 1 day (1/252), 1 week (1/52), or 2 weeks (1/26). At some stage, the BIS explicitly required publishing 10-day $99\%$ VaR with minimum 6 months of data. We will use $W a R$ and $P V^{*}$ interchangeably.  

VaR is expressed in dollars and leads to statements like: "The change in the firm portfolio's $P V$ is likely to be above. $P V^{*}$ dollars with. $c$ percent probability", or "The $P V$ loss will exceed. $|P V^{*}|$ million dollars only. $1-c$ percent of the time.".  

In practice, we posit that the change in the PV of the institution's portfolio is a function of $J$ factors and we compute the dollar sensitivities $\beta_{1},\dotsc,\beta_{J}$ of the PV to those factors, just as the duration gap was sensitive to interest rate moves. We modify the VaR definition in terms of the probability region for the factors:.  

$$
1-c=\operatorname{Prob}\left[P V\left(\tilde{F}_{1},\dots,\tilde{F}_{J}\right)\leq P V^{*}\right]
$$  

This is the leanest specification for the non-parametric case. Here is the numerical procedure for the simplest VaR implementation, a historical bootstrap:  

Collect $N$ weeks' worth of factor change data; $N$ weeks, each with $J$ factor change observations Given the sensitivities of the PV to the factors, for each week compute the gain/loss to the portfolio's PV, if the factors moved by the observed amount, denoted by $P V_{n}$ $n=1,\ldots,N$ Order the gains $P V_{n}$ from the lowest (high negative) to the highest (positive) Pick the $5\%$ lowest as your critical loss $P V^{*}$ and as your $95\%$ weekly VaR.  

The main burden is in identifying all the factors that affect the portfolio's PV and computing the PV's sensitivities to those factors. That is, the main burden is in defining completely the first (or higher) order Taylor expansion of the PV function. If the factorization is linear, then the simplest form of the PV change function is:  

$$
P V\left(\tilde{F}_{1},\dots,\tilde{F}_{J}\right)=\beta_{1}\times\tilde{F}_{1}+\beta_{2}\times\tilde{F}_{2}+\cdots+\beta_{J}\times\tilde{F}_{J}
$$  

A historical simulation is a scrambled bootstrap where we randomly choose with replacement (simulate) factor histories from the observed $N$ weeks of data in order to increase the sample size. In either case bootstrap or simulation, we do not know the form of the joint distribution function of all the factors.  

Many industry implementations of VaR are parametric. In this case, we observe $N$ weeks of factor data and compute the volatilities of the factors and the correlation structure of the factors. We then assume the multivariate distribution $\Phi\left(\cdot\right)$ and density function $\varphi(\cdot)$ of the continuous factors (or their logs) to be Gaussian (normal). VaR is then the cutoff PV change $P V^{*}$ corresponding to the $1-c$ tail of the multivariate normal:  

$$
1-c=\int\ldots\int_{P V(\tilde{F}_{1},\ldots,\tilde{F}_{J})\leq P V^{*}}\varphi\left(\tilde{F}_{1},\ldots,\tilde{F}_{J}\right)d\tilde{F}_{1}\ldots d\tilde{F}_{J}
$$  

This form is the general specification for the Monte Carlo simulation:  

Collect $N$ weeks' worth of factor change data.   
Compute the variance-covariance matrix $\Sigma$ of the factor changes where the diagonals and individual factor volatilities squared, or volatilities and correlations which define $\Sigma$ Generate $\eta\ge10,000$ vectors of factor samples $\tilde{F}_{1},\ldots,\tilde{F}_{J}$ Given the sensitivities of the PV to the factors, for each sample compute the gain/loss to. the portfolio's PV if the factors moved by the amount observed in the sample, denoted by $P V_{n},n=1,\dots,\eta$   
Order the gains $P V_{n}$ from the lowest (high negative) to the highest (positive)..   
.Pick the $5\%$ lowest as your critical loss. $P V^{*}$ and as your $95\%$ weekly VaR.  

The main feature of the VaR definition is its local focus and one-sidedness. Even though we reconstruct the entire distribution of PV changes, the VaR statistic is taken from its extreme left tail and ignores the rest of the information. For the complete discussion of the VaR methods' evolution, theoretical and implementation issues, see Dubil (2009) or Jorion (2009).  

Let us get back to Zions' portfolio. Again, we use balance sheet numbers as market values and make up intermediate sensitivity numbers. Suppose instead of simple durations, we identify four points on the US Treasury yield curve - 3-month, 1-year, 5-year and 10-year -- the TED spread (Libor minus TBill) and the 10-year swap spread as the main factors affecting the value of the portfolio. We characterize each asset and liability item on the balance sheet by the dollar exposure to those six factors. That is, we specify the dollar change in the PV of the bank's portfolio as a result of a 1 basis point change in the underlying rate. (Recall the definition of the PVBP in Chapter 2.) This step alone is difficult for any bank to implement. The bank would have to recompute the value of each loan or security on its books with the blipped rates. (Recall the understandable resistance of many European banks to the original EU-wide 2006 VaR Directives 2006/48/EC and 2006/49/EC, subsequently enhanced with 2010/76/EU.) Even more complicated might be computations of the exposure to convexity or to volatility for derivatives.  

Table 13.11 shows the six factor sensitivities for Zions expressed in dollars per basis. point move up. The minuses in front of the numbers for assets come from the fixed rate. nature of most assets. We show the totals for interest rates for each balance sheet category. We also show totals for each factor for the entire bank. Given these sensitivities $\beta_{1}=-731,672$ ..., $\beta_{6}=-575,815$ , the rest of the $\mathrm{VaR}$ analysis relies on using a relatively simple stand-alone procedure of using simulated samples for the factor changes, multiplying them out to compute the PV changes $P V_{n}$ $n=1,\dots,\eta$ , and picking off the lower 99- or 95-percentile PV number.  

(eonnnnne)   
  
  


<html><body><table><tr><td rowspan="9">Total 10-yr PVBPs FOR YIELD CURVE POINTS AND SPREADS Balance (Balance in millions,</td><td rowspan="9">Yld Curve Swp Sp TED 10-yr 5-yr -26,612 1-yr 3-mo</td><td>-114,246 -810,966 -39,058</td><td>41,580</td><td></td><td>-1,034,220 -1,984,207 412,188</td><td>-2,155,010 -166,089 2,761,152 40,992</td><td>20,088</td><td rowspan="9">-1,456 -946,450 -201,771</td><td rowspan="9">37,675</td></tr><tr><td>-1,270,134</td><td>-5,233</td><td>-23,774</td><td>-22,845</td><td>-322,192</td><td rowspan="2">275,412</td></tr><tr><td>-26,395</td><td>-1,433</td><td>-124,199 -143,840</td><td>-112,322 -143,228 -21,010</td><td>-6,219 -3,227 -1,456</td></tr><tr><td>-810,966 -131,826 -24,336</td><td>-2,000</td><td>-23,774</td><td>-117,396 -2,041,117</td><td>-928,411</td><td></td></tr><tr><td>-795,433 -14,722</td><td>-17,475</td><td>-153,817 -932,746</td><td>-1,024,193 478,193</td><td>-18,039</td><td>121,191</td></tr><tr><td>-342,875</td><td>-20,672 -592,110</td><td>-725,239 -125,922</td><td>-714,278 -72,622 -241,842 -18,641 -3,870</td><td></td><td>154,221 -2,730,462 -1,398,709</td></tr><tr><td>87,634</td><td>-1,433</td><td>-288,293 -302,448 286,266</td><td>-299,143 93,467 22,351</td><td>-16,218 -1,456</td><td></td></tr><tr><td>Sept 10 $5,193 843</td><td>59 4,185 189</td><td>9,402 8,741 4,206</td><td>7,535 2,157 3,504 366</td><td>558 56 36,525 1,150 FDIC-supported loans</td><td>47,241 1,063 (1,556) 5,029 Allowance for loan losses Goodwill, Core, other </td></tr><tr><td>Money market investments PVBPs in dollars) Held-to-maturity Securities: ASSETS</td><td>Commercial Loans: Trading account Loans held for sale</td><td>Construction & Land Development Owner Occupied & Leasing Commercialreal estate loans: Commercial & Industrial</td><td>Home equity credit line 1-4 Family Residential Consumer loans:</td><td>Bankcard, Revolving, Other Net loans/leases excl. FDIC Construction & other RE Foreign loans:</td><td>Total interest-earning assets Cash and duefrombanks Total loans and leases</td></tr></table></body></html>  

(eonninee)   


<html><body><table><tr><td rowspan="4">Total 10-yr PVBPs FOR YIELD CURVE POINTS AND SPREADS Balance</td><td rowspan="7">Yld Curve Swp'Sp TED 10-yr 5-yr 1-yr (Balance in millions, PVBPs in dollars)</td><td>408,342 794,784 227,124 236,352 181,308</td><td>12,236 15,732 15,470 1,029,018 1,133 2,001 655,988</td><td rowspan="10">13,787 一 13,787 Otherliabilities</td><td rowspan="10">2,934,153 745,744 655,988 342,870 1,268,258 667,037 Total liabilities</td><td rowspan="10">6,421 Total shareholders’ equity</td><td rowspan="3"></td><td rowspan="3">8,588,271 -575,815 162,415 -3,423,838 -2,970,557 -1,462,204</td></tr><tr><td>148,933 266,119 36,229 102,337 188,992</td></tr><tr><td></td></tr><tr><td>29,883 11,002 14,774</td><td>9,882 277,329</td></tr><tr><td>165,059 482,792 176,335 169,337</td><td>166,534 2,354 3,118 7,028 95,701</td></tr><tr><td>243,283 311,992 3-mo</td><td>20,906 56,013 12,614 8,442 2,103 2,462 1,563 27,900 38 874</td></tr><tr><td>Sept 10 $6,187 15,584</td><td>238 1,927 3,068 30,969 13,787 601 $45,357</td></tr><tr><td>LIABILITIES AND EQUITY Interest-bearing deposits: Time $100,000 and over</td><td>FHLB advances and other borrow: Total interest-bearing liabilities Non-interest-bearing deposits Total borrowed funds</td></tr></table></body></html>  

Suppose that Scenario No. 233 is a parallel yield curve shift up of 75 basis points, i.e. the factor realizations for that sample are:.  

$$
F_{1}=F_{2}=F_{3}=F_{4}=75,\quad F_{5}=F_{6}=0
$$  

Then the PV change for that sample is:  

$$
\begin{array}{r l}&{P V_{233}=-731,672\times75-1,462,204\times75-2,970,557\times75-3,423,838\times75}\ &{P V_{233}=-644,120,325}\end{array}
$$  

The bank would lose $\$644.1$ million in that scenario. Of course, a parallel move of 75 bp in 1 week is most unlikely, so that scenario would have to be an extreme left-tail event. We would more likely have samples like the yield curve steepening Scenario 7256.  

$$
F_{1}=7,F_{2}=9,F_{3}=12,F_{4}=15,F_{5}=2,F_{6}=4
$$  

Then the PV change for that sample is:  

$$
\begin{array}{r l}&{P V_{7256}=-731,672\times7-1,462,204\times9}\ &{\phantom{2}-2,970,557\times12-3,423,838\times15}\ &{\phantom{2}+162,415\times2-575,815\times4}\ &{P V_{7256}=-107,264,224}\end{array}
$$  

If we have 10,000 samples, we arrange the sampled PV changes from the lowest to the highest and pick the $500\mathrm{th}$ one to obtain the 95-percentile weekly VaR.  

The VaR analysis makes more sense for a global bank like J.P. Morgan. The large derivative portfolio would have to be described in terms of sensitivities to swap spreads, cap and swaption volatilities, detailed equity indexes and perhaps individual stocks, their volatilities, currencies, and their volatilities. We might even have esoteric variables like volatility skews, credit default swap rates, etc. During the author's tenure in the corporate risk management of Merrill Lynch, the bank collected data from 3,000 trading units for hundreds of factors, excluding individual equities. What may make sense for both Zions and J.P. Morgan is the enhancement of the market VaR with credit VaR. In credit VaR, the banks would attempt to factorize the credit exposure of their securities and loan portfolios. Again, the guiding mathematical principle would be a Taylor series expansion with first-order derivatives. The factors might be key credit indexes or spreads, like average sovereign spread, spread for top investment grade, bottom investment grade, and a few junk categories, etc. The methodological difficulty might come from trying to adequately parameterize these variables with their volatilities and correlations. And as the 2008 crisis showed, all of these methods may fail if they do not account for liquidity factors or as correlations dramatically increase in times of severe market dislocations.  

# 12  

# Hedge Funds: Alpha, Beta, and Strategy Indexes.  

Hedge funds are investment funds that are lightly regulated, open only to institutional or qualified (satisfying minimum wealth requirements) investors, with limited liquidity (quarterly or annual redemptions), and charging performance fees. The fee structure is typically. $2\%$ plus $20\%$ , meaning $2\%$ of assets under management plus $20\%$ of profits. Both numbers can be higher or lower. The $20\%$ performance incentive fee may be subject to high water marking,. i.e. requiring the fund to make up losses first. As of 2010, the hedge fund industry is estimated to have over $\$1.5$ trillion in assets under management with perhaps as many as 8,000 funds. in operation. The largest operators of hedge funds include J.P. Morgan Chase, Bridgewater Associates, Paulson & Co., Soros Fund Management, and D.E. Shaw Group, each in the $\$23-55$ billion range.  

Hedge funds are said to be a type of alternative investment. The definition of what constitutes an alternative investment asset class is unclear and combines some legal, access, and strategy aspects of investing. Retail mutual funds are regulated. They must satisfy strict disclosure,. redemption, and investment rules; and their behavior is largely constrained to long investments in stocks, bonds, and ETFs. Hedge funds can easily pursue short or neutral strategies, can use derivatives extensively to express their value views, can change strategies over time, and have limited redemption privileges. Institutions, rather than individuals, are the natural. investors in hedge funds. Other alternative investments share these characteristics. Figure 12.1. shows a recent approximate breakdown of alternative investments out of the total investment dollars.  

Hedge funds pursue a great variety of investment strategies. These can be classified according to the style (macro, directional, event-driven, managed futures), market (equity, fixed income, commodity, currency), industry (technology, pharma, emerging markets), instrument vehicles (long/short, options, futures, swaps), stated exposure (directional, neutral), or selection method (discretionary, quant, statistical). No matter how you slice it, none of the promised. return from a hedge fund can come without risk. The principle is always relative value with the big question of how relative. A global macro fund buying German bonds and selling British gilts may call itself non-directional market neutral. Of course, it is anything but neutral. By. comparison, a credit fund trading CDS against hedged corporate bonds to arbitrage "mispricing" has much less directional risk, or at least narrower in scope, as does a statistical arbitrage equity fund pursuing a momentum strategy or a managed futures fund..  

We will attempt our own classification of hedge funds, based on the subjective criterion of. how the relative value that the fund tries to unlock is pursued. Broadly, we can group funds into four blocks, from general bets on asset classes groups, all the way down to technical mispricing:  

Relative Asset Value (Directional) Funds - global macro, emerging markets, short bias, long/short equity, high yield convertible, managed futures.  

![](41a65a94b6f66f274d0013d6fa17a78691003ed8b3bc834f6816ac457b2c6494.jpg)  
Figure 12.1Alternative investments Sources: Compiled by the author from various public domain sources, blending 2009-2010 data. The percentage of assets in the various categories is approximate and unconfirmed.  

Relative Corporate/Credit Structure - capital structure, emerging market and corporate credit arbitrage, event-driven merger or distressed. Relative Value (Theoretical Arbitrage) - fixed income arbitrage, managed futures, convertible arbitrage.   
Relative Value (Statistical Arbitrage) - momentum, pairs, quantitative directional.  

The biggest attraction and risk of a hedge fund is an almost unlimited discretion afforded the fund manager. This engenders two negative aspects of hedge fund investing. Those are style drift and clustering. Since hedge funds are unregulated and their prospectuses are very vague, there is nothing stopping the manager from pursuing currency ideas one year and fixed income or equity ideas in the next, or to go from technical mispricing strategies to event-driven ones. This is referred to as style drift. The investor here has to truly believe in the manager's skill (alpha). Also, it has been well documented that at any given moment of time many managers pursue the same ideas and may be on the same end of a trade. This is clustering. Often they hold illiquid securities and cannot quickly get out of their strategies. In an important study by Hasanhodzic and Lo (2007), the authors find significant serial correlation in hedge fund returns. They suggest that hedge fund outperformance alphas may. not be coming from managers' investment acumen but may simply be reward for illiquidity that public market investors cannot gain exposure to. The Sharpe ratios may be artificially lowered as the reported returns are necessarily smoothed in the process of marking to market illiquid holdings, resulting in artificially low computed standard deviations. All this leads to the fundamental question of whether the oft-claimed superior hedge funds returns are due to the superior managers and strategies, or whether they are due to access and illiquidity factors. This then begs the question of whether they can be synthetically replicated by exposure to a. number of macro factors. While hedge funds claim economic and technical sophistication, or alpha, it is likely that the return on a group of similar strategy funds, or even each individual fund, can be attributed to the exposure to economic factors, preferably with investable vehicles proxying them. Because the funds do not have to disclose their holdings the way mutual funds do, perhaps we currently have no way to easily determine the complete set of factors.  

In the mutual fund industry, several studies have shown that active management does not lead to superior returns at all, and most returns can be decomposed into a set of three or four. systematic factors explaining $95\%$ of the variation of the returns. Mutual funds also exhibit. style drift (in the USA funds change their locus in the Morningstar matrix in order to earn more stars), but to a much more limited extent as their behavior is constrained by the objectives defined in the fund prospectus. More than two-thirds of the active mutual funds underperform. their benchmark when taking into account the fees they charge. What if we find that hedge fund returns can also be decomposed into a set of factors, and factor loadings for each fund. or group of funds can be easily computed? If so, are the alphas really alphas, or are they betas coming from the exposure to the factors, and can one avoid paying the. $2+20$ fee structure with the use of "indexing"? Perhaps with a little bit of empirical research, we may soon be able to. enhance the standard index models applicable to more traditional long-only investments, such as mutual funds, with additional investable factors to be able to replicate hedge fund returns. We will come back to this question when discussing strategy indexes..  
