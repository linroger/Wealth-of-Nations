---
tags:
  - '#american_options'
  - '#black_scholes_merton'
  - '#dividend_yield_estimation'
  - '#european_index_options'
  - '#ex_dividend_dates'
  - '#forward_prices'
  - '#index_option_valuation'
  - '#put_call_parity'
  - '#stock_vs_bonds'
---
# 17.4 VALUATION OF EUROPEAN STOCK INDEX OPTIONS  

In valuing index futures in Chapter 5, we assumed that the index could be treated as an asset paying a known yield. In valuing index options, we make similar assumptions.. This means that equations (17.1) and (17.2) provide a lower bound for European index options; equation (17.3) is the put-call parity result for European index options;. equations (17.4) and (17.5) can be used to value European options on an index; and the binomial tree approach can be used for American options. In all cases, $S_{0}$ is equal to the current value of the index, $\sigma$ is equal to the volatility of the index, and $q$ is equal to the average annualized dividend yield on the index during the life of the option expressed with continuous compounding.  

# Example 17.1  

Consider a European call option on an index that is two months from maturity. The current value of the index is 930, the exercise price is 900, the risk-free interest rate is  

$8\%$ per annum, and the volatility of the index is $20\%$ per annum. Dividend yields of. $0.2\%$ and $0.3\%$ (expressed with continuous compounding) are expected in the first month and the second month, respectively. In this case $S_{0}=930,K=900$ $r=0.08$ $\sigma=0.2$ , and $T=2/12$ The total dividend yield during the option's life. is $0.2\%+0.3\%=0.5\%$ This corresponds to. $3\%$ per annum. Hence, $q=0.03$ and  

$$
d_{1}=\frac{\ln(930/900)+(0.08-0.03+0.2^{2}/2)\times2/12}{0.2\sqrt{2/12}}=0.5444
$$  

$$
d_{2}=\frac{\ln(930/900)+(0.08-0.03-0.2^{2}/2)\times2/12}{0.2\sqrt{2/12}}=0.4628
$$  

$$
N(d_{1})=0.7069,\qquadN(d_{2})=0.6782
$$  

so that the call price, $c$ , is given by equation (17.4) as  

$$
c=930\times0.7069e^{-0.03\times2/12}-900\times0.6782e^{-0.08\times2/12}=51.83
$$  

One contract, if on 100 times the index, would cost $\$5,183$  

The calculation of $q$ should include only dividends for which the ex-dividend dates. occur during the life of the option. In the United States ex-dividend dates tend to occur during the first week of February, May, August, and November. At any given time the correct value of $q$ is therefore likely to depend on the life of the option. This is even. more true for indices in other countries. In Japan, for example, all companies tend to use the same ex-dividend dates.  

If the absolute amount of the dividend that will be paid on the stocks underlying the. index (rather than the dividend yield) is assumed to be known, the basic BlackScholes-Merton formulas can be used with the initial stock price being reduced by. the present value of the dividends. This is the approach recommended in Chapter 15 for. a stock paying known dividends. However, it may be difficult to implement for a broadly based stock index because it requires a knowledge of the dividends expected on every stock underlying the index..  

It is sometimes argued that, in the long run, the return from investing a certain. amount of money in a well-diversified stock portfolio is almost certain to beat the. return from investing the same amount of money in a bond portfolio. If this were so, a long-dated put option allowing the stock portfolio to be sold for the value of the bond. portfolio should not cost very much. In fact, as indicated by Business Snapshot 17.1, it. is quite expensive.  

# Forward Prices and the Estimation of Dividend Yields  

Define $F_{0}$ as the forward price of the index for a contract with maturity $T.$ As shown by. equation (5.3), $F_{0}=S_{0}e^{\hat{(}r-q)T}.$ This means that the equations for the European call price $c$ and the European put price. $p$ in equations (17.4) and (17.5) can be written.  

$$
\begin{array}{l}{{c=F_{0}e^{-r T}N(d_{1})-K e^{-r T}N(d_{2})}}\ {{p=K e^{-r T}N(-d_{2})-F_{0}e^{-r T}N(-d_{1})}}\end{array}
$$  

where  

$$
d_{1}=\frac{\ln(F_{0}/K)+\sigma^{2}T/2}{\sigma\sqrt{T}}\mathrm{and}d_{2}=\frac{\ln(F_{0}/K)-\sigma^{2}T/2}{\sigma\sqrt{T}}
$$  

Business Snapshot 17.1 Can We Guarantee that Stocks Will Beat Bonds in the Long Run?  

It is often said that if you are a long-term investor you should buy stocks rather than bonds. Consider a U.S. fund manager who is trying to persuade investors to buy, as a long-term investment, an equity fund that is expected to mirror the S&P 500. The manager might be tempted to offer purchasers of the fund a guarantee that their return will be at least as good as the return on risk-free bonds over the next 10 years. Historically stocks have outperformed bonds in the United States over almost any 10-year period. It appears that the fund manager would not be giving much away.  

In fact, this type of guarantee is surprisingly expensive. Suppose that an equity index is 1,000 today, the dividend yield on the index is $1\%$ per annum, the volatility of the index is. $15\%$ per annum, and the 10-year risk-free rate is. $5\%$ per annum. To. outperform bonds, the stocks underlying the index must earn more than $5\%$ per annum. The dividend yield will provide. $1\%$ per annum. The capital gains on the. stocks must therefore provide $4\%$ per annum. This means that we require the index. level to be at least $1,0\hat{0}0e^{0.04\times10}=\hat{1},492$ in 10 years.  

A guarantee that the return on $\$1,000$ invested in the index will be greater than the return on $\$1,000$ invested in bonds over the next 10 years is therefore equivalent to. the right to sell the index for 1,492 in 10 years. This is a European put option on the index and can be valued from equation (17.5) with $S_{0}=1\small{,}000$ $K=1{,}492$ $r=5\%$ $\sigma=15\%$ $T=10$ , and $q=1\%$ . The value of the put option is 169.7. This shows that the guarantee contemplated by the fund manager is worth about $17\%$ of the fundhardly something that should be given away!  

The put-call parity relationship in equation (17.3) can be written  

or  

$$
\begin{array}{c}{{c+K e^{-r T}=p+F_{0}e^{-r T}}}\ {{F_{0}=K+(c-p)e^{r T}}}\end{array}
$$  

Working with forward prices and equations (17.8) and (17.9) is attractive because it avoids the need to estimate the dividend yield on the index directly. The dividend yield expected by the market is incorporated into forward prices. Futures prices for stock indices can be assumed to be the same as forward prices and so futures markets can be used to estimate forward prices for the maturities of the futures contracts that trade. If, as is not uncommon, European put and call options with the same strike price and maturity date are traded, equation (17.10) can be used to provide an estimate of the forward price of the index for that maturity date.  

Once forward prices for a number of different maturity dates have been obtained (at least approximately), a smooth function describing the forward price as a function of maturity can be estimated, and equations (17.8) and (17.9) can be used to determine the prices of European index options for a range of maturities.  

When American options on an index are valued, the average dividend yield during the life of the option must be estimated explicitly.' Because $F_{0}\bar{=}S_{0}e^{(r-q)T}$ the average dividend yield during the life of a futures contract can be estimated as  

$$
q=r-\frac{1}{T}\ln\frac{F_{0}}{S_{0}}
$$  

A European call and put option with the same strike price and maturity date can also be used to estimate $q$ . From equation (17.3),  

$$
q=-\frac{1}{T}\mathrm{ln}\frac{c-p+K e^{-r T}}{S_{0}}
$$  

For a particular strike price and time to maturity, the estimates of $q$ calculated from this equation are liable to be unreliable. But when the results from many matched pairs of calls and puts are combined, a clearer picture of the term structure of dividend yields being assumed by the market emerges.  
