---
title: Appendix 5. A Taxes and the Forward Price
tags:
  - arbitrage
  - derivative_pricing
  - forward_price
  - futures_price
  - taxes
aliases:
  - Forward contract pricing
  - Futures vs. Forwards
  - Tax impact
key_concepts:
  - Broker-dealer tax treatment
  - Forward vs. futures prices
  - No-arbitrage forward price
  - Stochastic interest rates
  - Taxes on forward prices
---

# Appendix 5. A Taxes and the Forward Price

The formulas in this chapter—and in the book to this point—have ignored taxes. In this appendix we show how taxes enter into the theoretical formula for the forward price,  and explain why in practice these tax adjustments are never used. The impact of taxes on derivative prices was studied by Scholes (1976) and Cornell and French (1983),  who showed that prices depend upon taxes when capital gains,  dividends and interest are taxed at different rates. However,  a party such as a broker-dealer,  who is taxed identically on all forms of income,  will have a fair price that is independent of taxes.

Suppose that capital gains on a stock are taxed at the rate $l_{g}$ ,  gains on the forward contract at $\tau_f$ ,  dividends at the rate $\tau_{d}$ ,  and interest at the rate $\tau_{i}$ .Consider an investor who goes long $(1-\tau_{g})/(1-\tau_{f})$ forward contracts (we will see why in a moment) and hedges by selling one share today. The investor thus receives $S_{0}$ ,  which can be invested to earn the risk-free rate.

In 1 year,  the investor closes the transaction by buying a share and paying the forward price. After-tax income is
$$S_0[1+r(1-\tau_i)]-[S_1-\tau_g(S_1-S_0)]-Div(1-\tau_d)+[S_1-F_{0,      1}]\frac{1-\tau_g}{1-\tau_f}(1-\tau_f)$$
The first bracketed term is the after-tax value of invested short-sale proceeds,  the second is the after-tax cost of buying the share to close the short sale,  the third is the after-tax dividend that must be paid to the share-lender,  and the fourth is the after-tax gain on $(1-\tau_{g})/(1-\tau_{f})$ futures contracts. If the transaction is to generate no-arbitrage profits,  the forward price must be set so that equation (5.20) equals zero. Thus,  the after-tax zero-profit forward price is
$$F_{0,      1}=S_0\left(1+r\frac{1-\tau_i}{1-\tau_g}\right)-Di\nu\frac{1-\tau_d}{1-\tau_g}$$
Note that the tax on the forward contract does not enter the expression at all! The reason is that since the forward contract has a zero value,  it is possible to offset the tax by entering intc additional forward contracts—this is the reason for going long $(1-\tau_{g})/(1-\tau_{f})$ contracts against one short share. We in effect make the forward contract be taxed at the same rate as the stock.
$$F_{0,      T}=S_{0}e^{[r(1-\tau_{i})/(1-\tau_{g})-\delta(1-\tau_{d})/(1-\tau_{g})]T}$$
The important insight is that broker-dealers are marked-to-market for tax purpose and face the same tax rate on all forms of income —-i.e.,  $\tau_{i}=\tau_{g}=\tau_{d}$ . Thus,  equation (5.21 becomes
$$F_{0,      1}=S_0\left(1+r\right)-Div$$
The same as equation (5.5).

# [[Appendix 5. C Forward And Futures Prices When Interest Rates Are Random|Appendix 5. C Forward and Futures Prices When Interest Rates Are Random]]

This appendix formalizes the difference between forward and futures prices and shows the relationship between them when interest rates are stochastic. We will use the following notation:

$$\begin{aligned}
&F_{t,      T} =\mathrm{~Forward~price} \\
&f_{t,      F} \text{= Futures price} \\
&\text{s} = \text{Time }t \text{ price of the underlying asset} \\
&P_{t,      T} =\mathrm{~Time~}t\mathrm{~price~of~a~zero-coupon~bond~maturing~at~time~}T. \\
&\text{R} =\mathrm{~Time~}t\mathrm{~interest~rate~from~time~}t\mathrm{~to~time~}t+h. \\
&\text{h} =\mathrm{Length~of~a~period};h=T/n 
\end{aligned}$$

We will refer to an instrument that pays the short-term interest rate as a money-market account.

The strategy in these derivations,      which follow Cox et al. (1981),      is to find a strategy that replicates fully funded contracts

### Forward Prices

The forward price is
$$F_{t,      T}=\mathrm{PV}\left(\frac{S_T}{P_{t,      T}}\right)=\frac{S_t}{P_{t,      T}}$$
In the chapter,        we wrote this formula as $F_{t,      T}=S_{t}e^{r(T-t)}$ This is the same as equation (5.23),        where $r$ is the continuously compounded yield on the bond: $r=\ln(1/P_{t,      T})/(T-t)$

To prove equation (5.23),        buy $F_{t,      T}$ bonds paying $S1$ at maturity (this pre-funds the forward price) and go long $1/P_{t,      T}$ forward contracts. The payoff is
$$\frac{F_{t,      T}}{P_{t,      T}}+\frac{1}{P_{t,      T}}\left[F_{T,      T}-F_{t,      T}\right]=\frac{F_{t,      T}}{P_{t,      T}}=\frac{S_{T}}{P_{t,      T}}$$
This demonstrates that a portfolio costing the forward price at time $t$ pays $S_{T}/P_{t,      T}$ Thus the forward price is the present value of $S_{T}/P_{t,      T}$ ,      or $S_{t}/P_{t,      T}$

## Futures Price

We will show that the futures price is

$$f_{t,      T}=\text{PV}\left[S_T\prod_{i=t}^T(1+R_i)\right]$$

Note that if the interest rate is known,      $\prod_{i=t}^{T}(1+R_{i})=1/P_{t,      T}$ (the bond can be replicated with the money-market fund),      and the forward price equals the futures price. To prove equation (5.24),      invest the amount $f_{l,      T}$ at the short-term interest rate,      reinvesting the proceeds each period. Also,      at each time $t_{i} \equiv t+ih,      i=1,      \ldots,      n$ ,      invest in $\Pi_{j=t}^{l_{i}}(1+R_{j})$ futures contracts. At time $t_{i+1}$ ,      liquidate position and invest the proceeds in the money-market account. The net cash flow at time 7 will be
$$\begin{gathered}
f_{t,      T}\prod_{i=t}^{T}(1+R_{i}) +\sum_{i=t}^{T-h}\left(\prod_{j=t}^{i}(1+R_{j})(f_{j,      T}-f_{j-h,      T})\prod_{j=i+h}^{T-h}(1+R_{j})\right) \\
=f_{T,      T}\prod_{i=t}^{T-h}(1+R_{i})=S(T)\prod_{i=t}^{T-h}(1+R_{i}) 
\end{gathered}$$
For future reference,      note that in continuous time,      equation (5.24) becomes
$$f_{t,      T}=\mathrm{PV}\left[S_Te^{\int_t^Tr(s)ds}\right]$$
where $r(s)$ is the instantaneous continuously compounded short-term interest rate
