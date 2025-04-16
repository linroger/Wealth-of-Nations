---
tags:
  - '#european_options'
  - '#notional_principal'
  - '#option_valuation'
  - '#realized_variance'
  - '#realized_volatility'
  - '#swap_valuation'
  - '#variance_swap'
  - '#vix_index'
  - '#volatility_swap'
---
# 26.16 VOLATILITY AND VARIANCE SWAPS  

A volatility swap is an agreement to exchange the realized volatility of an asset between time 0 and time $T$ for a prespecifed fixed volatility. The realized volatility is usually calculated as described in Section 15.4 but with the assumption that the mean daily return is zero. Suppose that there are $n$ daily observations on the asset price during the period between time 0 and time $T$ The realized volatility is  

$$
\overline{{\sigma}}=\sqrt{\frac{252}{n-2}\sum_{i=1}^{n-1}\biggl[\ln\biggl(\frac{S_{i+1}}{S_{i}}\biggr)\biggr]^{2}}
$$  

where $S_{i}$ is the ith observation on the asset price. (Sometimes $n\mathrm{~-~}1$ might replace $n-2$ in this formula.)  

The payoff from the volatility swap at time. $T$ to the payer of the fixed volatility is. $L_{\mathrm{vol}}(\overline{{\sigma}}\mathrm{~-~}\sigma_{K})$ , where $L_{\mathrm{vol}}$ is the notional principal and. $\sigma_{K}$ is the fixed volatility. Whereas. an option provides a complex exposure to the asset price and volatility, a volatility swap is simpler in that it has exposure only to volatility.  

A variance swap is an agreement to exchange the realized variance rate $\overline{V}$ between time 0 and time $T$ for a prespecified variance rate. The variance rate is the square of the volatility $(\overline{{V}}=\overline{{\sigma}}^{2}$ ). Variance swaps are easier to value than volatility swaps. This is because the variance rate between time O and time $T$ can be replicated using a portfolio of put and call options. The payoff from a variance swap at time $T$ to the payer of the fixed variance rate is ${\cal L}_{\mathrm{var}}(\overline{{V}}-V_{K})$ , where $L_{\mathrm{var}}$ is the notional principal and $V_{K}$ is the fixed variance rate. Often the notional principal for a variance swap is expressed in terms of the corresponding notional principal for a volatility swap using $L_{\mathrm{var}}=L_{\mathrm{vol}}/(2\sigma_{K})$  

# Valuation of Variance Swap  

Technical Note 22 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes shows that, for any value $S^{*}$ of the asset price, the expected average variance between times 0.  

and $T$ is  

$$
\hat{E}(\overline{{V}})=\frac{2}{T}\ln\frac{F_{0}}{S^{*}}-\frac{2}{T}\biggl[\frac{F_{0}}{S^{*}}-1\biggr]+\frac{2}{T}\biggl[\int_{K=0}^{S^{*}}\frac{1}{K^{2}}e^{r T}p(K)d K+\int_{K=S^{*}}^{\infty}\frac{1}{K^{2}}e^{r T}c(K)d K\biggr]
$$  

where $F_{0}$ is the forward price of the asset for a contract maturing at time $T,c(K)$ is the price of a European call option with strike price. $K$ and time to maturity $T$ , and $p(K)$ is the price of a European put option with strike price. $K$ and time to maturity $T$  

This provides a way of valuing a variance swap.14 The value of an agreement to receive the realized variance between time 0 and time $T$ and pay a variance rate of $V_{K}$ with both being applied to a principal of $L_{\mathrm{var}}$ is  

$$
L_{\mathrm{var}}[\hat{E}(\overline{{V}})-V_{K}]e^{-r T}
$$  

Suppose that the prices of European options with strike prices $K_{i}(1\leq i\leq n)$ are known, where $K_{1}<K_{2}<\cdots<K_{n}.$ A standard approach for implementing equation (26.6) is to set $S^{*}$ equal to the first strike price below. $F_{0}$ and then approximate the integrals as.  

$$
\int_{K=0}^{S^{*}}{\frac{1}{K^{2}}}e^{r T}p(K)d K+\int_{K=S^{*}}^{\infty}{\frac{1}{K^{2}}}e^{r T}c(K)d K=\sum_{i=1}^{n}{\frac{\Delta K_{i}}{K_{i}^{2}}}e^{r T}Q(K_{i})
$$  

where $\Delta K_{i}=0.5(K_{i+1}-K_{i-1})$ for $2\leq i\leq n-1$ $\Delta K_{1}=K_{2}-K_{1}$ $\Delta K_{n}=K_{n}-K_{n-1}$ The function $Q(K_{i})$ is the price of a European put option with strike price $K_{i}$ $K_{i}<S^{*}$ and the price of a European call option with strike price $K_{i}$ if $K_{i}>S^{*}$ . When $\boldsymbol{K}_{i}=\boldsymbol{S}^{*}$ the function $Q(K_{i})$ is equal to the average of the prices of a European call and a European put with strike price $K_{i}$  

# Example 26.4  

Consider a 3-month contract to receive the realized variance rate of an index over the 3 months and pay a variance rate of 0.045 on a principal of $\$100$ million. The. risk-free rate is. $4\%$ and the dividend yield on the index is $1\%$ . The current level of the index is 1020. Suppose that, for strike prices of 800, 850, 900, 950, 1,000, 1,050, 1,100, 1,150, 1,200, the 3-month implied volatilities of the index are $29\%$ $28\%$ $27\%$ $26\%$ $25\%$ $24\%$ $23\%$ $22\%$ $21\%$ , respectively. In this case, $n=9$ $\therefore=800,K_{2}=850,\ldots,K_{9}=1,200,F_{0}=1,020e^{(0.04-0.01)\times0.25}=1,027.68.$ and $\boldsymbol{S}^{*}=1{,}000$ DerivaGem shows that $Q(K_{1})=2.22,Q(K_{2})=5.22,Q(K_{3})=$ $Q(K_{3})=11.05$ $\begin{array}{r}{Q(K_{4})=21.27,Q(K_{5})=51.21,Q(K_{6})=38.94,Q(K_{7})=20.69,Q(K_{8})=9.44,}\end{array}$ $Q(K_{9})=3.57$ Also, $\Delta K_{i}=50$ for all $i$ . Hence,  

$$
\sum_{i=1}^{n}\frac{\Delta K_{i}}{K_{i}^{2}}e^{r T}Q(K_{i})=0.008139
$$  

From equations (26.6) and (26.8), it follows that  

$$
\hat{E}(\overline{{V}})=\frac{2}{0.25}\ln{\left(\frac{1027.68}{1.000}\right)}-\frac{2}{0.25}{\left(\frac{1027.68}{1.000}-1\right)}+\frac{2}{0.25}\times0.008139=0.0621
$$  

From equation (26.7), the value of the variance swap (in millions of dollars) is $100\times(\hat{0}.0621-0.045)e^{-0.04\times0.25}=1.69$  

# Valuation of a Volatility Swap  

To value a volatility swap, we require $\hat{E}(\overline{{\sigma}})$ , where $\overline{{\sigma}}$ is, as before, the realized volatility between time 0 and time $T$ We can write  

$$
\overline{{\sigma}}=\sqrt{\hat{E}(\overline{{V}})}\sqrt{1+\frac{\overline{{V}}-\hat{E}(\overline{{V}})}{\hat{E}(\overline{{V}})}}
$$  

Expanding the second term on the right-hand side in a series gives the approximation  

$$
\overline{{\sigma}}=\sqrt{\hat{E}(\overline{{V}})}\bigg\{1+\frac{\overline{{V}}-\hat{E}(\overline{{V}})}{2\hat{E}(\overline{{V}})}-\frac{1}{8}\bigg[\frac{\overline{{V}}-\hat{E}(\overline{{V}})}{\hat{E}(\overline{{V}})}\bigg]^{2}\bigg\}
$$  

Taking expectations,  

$$
\begin{array}{r}{\hat{E}(\overline{{\sigma}})=\sqrt{\hat{E}(\overline{{V}})}\bigg\{1-\frac{1}{8}\bigg[\frac{\mathrm{var}(\overline{{V}})}{\hat{E}(\overline{{V}})^{2}}\bigg]\bigg\}}\end{array}
$$  

where $\operatorname{var}({\overline{{V}}})$ is the variance of $\overline{V}$ The valuation of a volatility swap therefore requires an estimate of the variance of the realized variance rate during the life of the contract. The value of an agreement to receive the realized volatility between time 0 and time. $T$ and pay a volatility of $\sigma_{K}$ , with both being applied to a principal of $L_{\mathrm{vol}}$ is  

$$
L_{\mathrm{vol}}[\hat{E}(\overline{{\sigma}})-\sigma_{K}]e^{-r T}
$$  

# Example 26.5  

For the situation in Example 26.4, consider a volatility swap where the realized. volatility is received and a volatility of. $23\%$ is paid on a principal of. $\$100$ million. In this case $\hat{E}(\overline{{V}})=0.0621$ . Suppose that the standard deviation of the realized variance over 3 months has been estimated as O.01. This means that $\operatorname{var}({\overline{{V}}})=0.0001$ . Equation (26.9) gives  

$$
\begin{array}{r}{\hat{E}(\overline{{\sigma}})=\sqrt{0.0621}\bigg(1-\frac{1}{8}\times\frac{0.0001}{0.0621^{2}}\bigg)=0.2484}\end{array}
$$  

The value of the swap in (millions of dollars) is  

$$
100\times(0.2484-0.23)e^{-0.04\times0.25}=1.82
$$  

# The VIX Index  

In equation (26.6), the ln function can be approximated by the first two terms in a series expansion:  

$$
\ln\left(\frac{F_{0}}{S^{*}}\right)=\left(\frac{F_{0}}{S^{*}}-1\right)-\frac{1}{2}\biggl(\frac{F_{0}}{S^{*}}-1\biggr)^{2}
$$  

This means that the risk-neutral expected cumulative variance is calculated as  

$$
{\hat{E}}({\overline{{V}}})T=-{\bigg(}{\frac{F_{0}}{{S^{*}}}}-1{\bigg)}^{2}+2{\sum_{i=1}^{n}}{\frac{\Delta K_{i}}{K_{i}^{2}}}e^{r T}Q(K_{i})
$$  

Since 2004 the VIX volatility index (see Section 15.11) has been based on equation (26.10). The procedure used on any given day is to calculate ${\hat{E}}({\overline{{V}}})T$ for options that trade in the market and have maturitiesimmediately above and below 30 days. The 30-day risk-neutral expected cumulative variance is calculated from these two numbers using interpolation. This is then multiplied by 365/30 and the index is set equal to the square root of the result. More details on the calculation can be found on the CBOE website.  
