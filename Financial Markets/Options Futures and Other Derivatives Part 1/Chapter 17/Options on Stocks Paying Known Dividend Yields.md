---
tags:
  - black_scholes_merton
  - dividend_yield
  - european_options
  - put_call_parity
  - stock_pricing
aliases:
  - Dividend Paying Stocks
  - European Option Pricing
  - Options Valuation
key_concepts:
  - Black-Scholes-Merton formulas
  - Dividend yield impact
  - European option valuation
  - Lower bounds for options
  - Put-call parity formula
---

# 17.3 OPTIONS ON STOCKS PAYING KNOWN DIVIDEND YIELDS  

In this section we produce a simple rule that enables valuation results for European options on a non-dividend-paying stock to be extended so that they apply to European options on a stock paying a known dividend yield. Later we show how this enables us to value options on stock indices and currencies..  

Suppose that the dividend yield per year (measured with continuous compounding) is $q$ Dividends cause stock prices to reduce on the ex-dividend date by the amount of the dividend payment. The payment of a dividend yield at rate $q$ therefore causes the growth rate in the stock price to be less than it would otherwise be by an amount $q$ . If, with a dividend yield of $q$ , the stock price grows from $S_{0}$ today to $S_{T}$ at time $T$ then in the absence of dividends it would grow from $S_{0}$ today to $S_{T}e^{q T}$ at time $T.$ Alternatively, in the absence of dividends it would grow from $S_{0}e^{-q T}$ today to $S_{T}$ at time $T$  

This argument shows that we get the same probability distribution for the stock price at time $T$ in each of the following two cases:  

1. The stock starts at price. $S_{0}$ and provides a dividend yield at rate $q$   
2. The stock starts at price. $S_{0}e^{-q T}$ and pays no dividends..  

This leads to a simple rule. When valuing a European option lasting for time $T$ On a stock paying a known dividend yield at rate. $q$ , we reduce the current stock price from. $S_{0}$ to $S_{0}e^{-q T}$ and then value the option as though the stock pays no dividends.2.  

# Lower Bounds for Option Prices  

As a first application of this rule, consider the problem of determining bounds for the price of a European option on a stock paying a dividend yield at rate $q$ . Substituting $\bar{S}_{0}e^{-q T}$ for $S_{0}$ in equation (11.4), we see that a lower bound for the European call option. price, $c$ , is given by  

$$
c\ge\operatorname*{max}(S_{0}e^{-q T}-K e^{-r T},0)
$$  

We can also prove this directly by considering the following two portfolios:  

Portfolio $A$ : one European call option plus an amount of cash equal to $K e^{-r T}$ Portfolio $B$ $e^{-q T}$ shares with dividends being reinvested in additional shares.  

To obtain a lower bound for a European put option, we can similarly replace $S_{0}$ by $S_{0}e^{-q T}$ in equation (11.5) to get  

$$
p\ge\operatorname*{max}(K e^{-r T}-S_{0}e^{-q T},0)
$$  

This result can also be proved directly by considering the following portfolios:  

Portfolio $C$ : one European put option plus. $e^{-q T}$ shares with dividends on the shares. being reinvested in additional shares   
Portfolio $D$ : an amount of cash equal to $K e^{-r T}$  

# Put-Call Parity  

Replacing $S_{0}$ by $S_{0}e^{-q T}$ in equation (11.6) we obtain put-call parity for an option on a stock paying a dividend yield at rate $q$  

$$
c+K e^{-r T}=p+S_{0}e^{-q T}
$$  

This result can also be proved directly by considering the following two portfolios:  

Portfolio $A$ : one European call option plus an amount of cash equal to $K e^{-r T}$ Portfolio $C$ : one European put option plus $e^{-q T}$ shares with dividends on the shares being reinvested in additional shares.  

Both portfolios are both worth $\operatorname*{max}(S_{T},K)$ at time $T.$ They must therefore be worth the same today, and the put-call parity result in equation (17.3) follows. For American options, the put-call parity relationship is (see Problem 17.16).  

$$
S_{0}e^{-q T}-K\le C-P\le S_{0}-K e^{-r T}
$$  

# Pricing Formulas  

By replacing $S_{0}$ by $S_{0}e^{-q T}$ in the Black-Scholes-Merton formulas, equations (15.20) and (15.21), we obtain the price, $c$ , of a European call and the price, $p$ , of a European put on a stock paying a dividend yield at rate $q$ as  

$$
\begin{array}{l}{{c=S_{0}e^{-q T}N(d_{1})-K e^{-r T}N(d_{2})}}\ {{p=K e^{-r T}N(-d_{2})-S_{0}e^{-q T}N(-d_{1})}}\end{array}
$$  

Since  

$$
\mathrm{ln}{\frac{S_{0}e^{-q T}}{K}}=\mathrm{ln}{\frac{S_{0}}{K}}-q T
$$  

it follows that $d_{1}$ and $d_{2}$ are given by  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{0}/K)+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\ {{d_{2}=\displaystyle\frac{\ln(S_{0}/K)+(r-q-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

These results were first derived by Merton. As discussed in Chapter 15, the word dividend should, for the purposes of option valuation, be defined as the reduction in the stock price on the ex-dividend date arising from any dividends declared. If the dividend yield rate is known but not constant during the life of the option, equations (17.4)  

and (17.5) are still true, with. $q$ equal to the average annualized dividend yield during the option's life.  

# Differential Equation and Risk-Neutral Valuation  

To prove the results in equations (17.4) and (17.5) more formally, we can either solve the differential equation that the option price must satisfy or use risk-neutral valuation..  

When we include a dividend yield of $q$ in the analysis in Section 15.6, the differential equation (15.16) becomes4  

$$
\frac{\partial f}{\partial t}+(r-q)S\frac{\partial f}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}f}{\partial S^{2}}=r f
$$  

Like equation (15.16), this does not involve any variable affected by risk preferences.   
Therefore the risk-neutral valuation procedure described in Section 15.7 can be used.  

In a risk-neutral world, the total return from the stock must be $r$ The dividends provide a return of $q$ . The expected growth rate in the stock price must therefore be. $r\mathrm{~-~}q$ . It follows that the risk-neutral process for the stock price is.  

$$
d S=(r-q)S d t+\sigma S d z
$$  

To value a derivative dependent on a stock that provides a dividend yield equal to $q$ , we set the expected growth rate of the stock equal to. $r\mathrm{~-~}q$ and discount the expected payoff at rate $r.$ When the expected growth rate in the stock price is. $r\mathrm{~-~}q$ , the expected stock price at time $T$ $S_{0}e^{(r^{-}q)T}.$ A similar analysis to that in the appendix to Chapter 15 gives the expected payoff for a call option in a risk-neutral world as.  

$$
e^{(r-q)T}S_{0}N(d_{1})-K N(d_{2})
$$  

where $d_{1}$ and $d_{2}$ are defined as above. Discounting at rate $r$ for time $T$ leads to equation (17.4).  
