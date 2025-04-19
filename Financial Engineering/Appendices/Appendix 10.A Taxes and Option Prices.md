---
title: Appendix 10. A Taxes and Option Prices
tags:
  - binomial_pricing
  - capital_gains
  - dealers
  - marked_to_market
  - option_prices
  - tax_rates
  - taxes
aliases:
  - Appendix 10
  - Taxes and Options
key_concepts:
  - After-tax return equality
  - Binomial price with taxes
  - Dealer marked-to-market
  - Option pricing formula
  - Tax rates on income
---

# Appendix 10. A Taxes and Option Prices

It is possible to solve for a binomial price when there are taxes. Suppose that each form of income is taxed at a different rate: interest at the rate $\tau_{i}$ ,  capital gains on a stock at the rate $l_{g}$ ,  capital gains on options at the rate $l0$ ,  and dividends at the rate $\tau_{d}$ We assume that taxes on all forms of income are paid on an accrual basis,  and that there is no limit on the ability to deduct losses or to offset losses on one form of income against gains on another form of income.

We then choose $\Delta_{t}$ and $B_{r}$ by requiring that the after-tax return on the stock/bond portfolio equal the after-tax return on the option in both the up and down states. Thus we require that

$$\begin{aligned}\begin{bmatrix}S_{t+h}&-\tau_{g}(S_{t+h}-S_{t})+\delta S_{t}(1-\tau_{d})\end{bmatrix}\Delta_{t}+\begin{bmatrix}1+r_{h}(1-\tau_{i})\end{bmatrix}B_{t}\\&=\phi_{t+h}(S_{t+h})-\tau_{O}\left[\phi_{t+h}(S_{t+h})-\phi_{t}(S_{t})\right]\end{aligned}$$

The solutions for $\Delta$ and $B$ arethen
$$\begin{aligned}&\Delta=\frac{1-\tau_{O}}{1-\tau_{g}}\frac{\phi_{1}(S_{1}^{+})-\phi_{1}(S_{1}^{-})}{S_{1}^{+}-S_{1}^{-}}\\&B=\frac{1}{1+r_{h}\frac{1-\tau_{l}}{1-\tau_{O}}}\left(\frac{u\phi_{1}(S_{1}^{-})-d\phi_{1}(S_{1}^{+})}{u-d}-\frac{\Delta}{1-\tau_{O}}S_{0}\left[\frac{\tau_{g}-\tau_{O}}{1-\tau_{g}}+\delta(1-\tau_{d})\right]\right)\end{aligned}$$

This gives an option price of

$$\phi_{t}=\frac{1}{1+r_{h}\frac{1-\tau_{i}}{1-\tau_{O}}}\left[p^{*}\phi_{t+h}(S_{t+h}^{+})+(1-p^{*})\phi_{t+h}(S_{t+h}^{-})\right]$$

Where

$$p^*=\frac{1+r_h\frac{1-\tau_i}{1-\tau_g}-\delta\frac{1-\tau_d}{1-\tau_O}-d}{u-d}$$

In practice,  dealers are marked-to-market for tax purposes and face the same tax rate on all forms of income. In this case taxes drop out of all the option-pricing expressions. When dealers are the effective price-setters in a market,  taxes should not affect prices