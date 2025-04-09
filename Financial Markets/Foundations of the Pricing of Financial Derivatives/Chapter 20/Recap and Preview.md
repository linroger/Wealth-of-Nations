# 20.3 RECAP AND PREVIEW

In this chapter, we showed how the American put can be viewed as a combination of an infinite number of compound options. As such, the solution has an infinite number of terms, but it does provide insights into the pricing of American puts, and it does lead to. approximation formulas.

In Chapter 21, we look at min-max options, which are options with more than. one underlying. The payoff will depend on either the better or worse performing of the underlyings.

# QUESTIONS AND PROBLEMS

1 Derive the partial differential equation for an American put option based on geometric. Brownian motion when we assume that dividends are paid in the form of a continuously compounded dividend yield.

2 The American put option model presented here is based on $S_{t}^{*}$ . Explain this variable.

3  Based on the Geske-Johnson model, one of the bivariate terms is $N_{2}\Big[d_{1}\Big(S_{d t}^{*}d t\Big),-d_{1}\Big(S_{2d t}^{*}2d t\Big);-\rho_{12}\Big]$ . Explain why the correlation coefficient is. negative.

4 Based on the Geske-Johnson model, one of the trivariate terms is $N_{3}\Big[d_{1}\Big(S_{d t}^{*}d t\Big),d_{1}\Big(\bar{S_{2d t}^{*}}2d t\Big),-d_{1}\Big({S_{3d t}^{*}}3d t\Big);\rho_{12},-\rho_{13},-\rho_{23}\Big]$ Explain the pattern of $d_{1}$ terms as well as the pattern of correlation coefficient terms.

5[Contributed by Dennel McKenzie] Explain why dividends on a stock reduce the likelihood that a put option on the stock will be exercised early..

6(Contributed by Dennel McKenzie] Provide a verbal (non-quantitative) interpretation of the following representation:

$$
\mathrm{cov}\left(\int_{0}^{t_{1}}d W_{t},\intop_{0}^{t_{2}}d W_{t}\right).
$$

# NOTES

1. See Chapter 10, Section 10.6, Selected Time Series Properties.
2. The derivation of this correlation is not provided in the Geske-Johnson paper. It is added here for clarification.

# Min-Max Option Pricing

here are a number of variations of options in which there is more than one underlying. asset. These options have a variety of interesting names. Nearly all of them are based.
on the maximum or minimum performer of two or more underlying assets or rates. The.
first paper to examine this type of option was Stulz (1982), who derived formulas for calls.
and puts that pay off based on which of two assets has the maximum or minimum value.
We focus on the Stulz model initially and then show how it establishes a framework for
variations of this type of option..
