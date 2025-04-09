# 26.11 LOOKBACK OPTIONS  

The payoffs from lookback options depend on the maximum or minimum asset price reached during the life of the option. The payoff from a floating lookback call is the amount that the final asset price exceeds the minimum asset price achieved during the life of the option. The payoff from a floating lookback put is the amount by which the maximum asset price achieved during the life of the option exceeds the final asset price.  

Valuation formulas have been produced for floating lookbacks.' The value of a floating lookback call at time zero is.  

$$
\cdot_{\mathrm{fl}}=S_{0}e^{-q T}N(a_{1})-S_{0}e^{-q T}\frac{\sigma^{2}}{2(r-q)}N(-a_{1})-S_{\mathrm{min}}e^{-r T}\biggl[N(a_{2})-\frac{\sigma^{2}}{2(r-q)}e^{Y_{1}}N(-a_{3})-\frac{\sigma^{2}}{2(r-q)}e^{Y_{2}}\biggl]
$$  

where  

$$
\begin{array}{r l}&{a_{1}=\cfrac{\ln(S_{0}/S_{\mathrm{min}})+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ &{a_{2}=a_{1}-\sigma\sqrt{T},}\ &{a_{3}=\cfrac{\ln(S_{0}/S_{\mathrm{min}})+(-r+q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ &{Y_{1}=-\cfrac{2(r-q-\sigma^{2}/2)\ln(S_{0}/S_{\mathrm{min}})}{\sigma^{2}}}\end{array}
$$  

and $S_{\mathrm{min}}$ is the minimum asset price achieved to date. (If the lookback has just been originated, $S_{\mathrm{min}}=S_{\mathrm{0}}.$ ) See Problem 26.23 for the $r=q$ case.  

The value of a floating lookback put is  

$$
p_{\mathrm{fl}}=S_{\mathrm{max}}e^{-r T}\bigg[N(b_{1})-\frac{\sigma^{2}}{2(r-q)}e^{Y_{2}}N(-b_{3})\bigg]+S_{0}e^{-q T}\frac{\sigma^{2}}{2(r-q)}N(-b_{2})-S_{0}e^{-q T}N(b_{2})
$$  

$$
\begin{array}{l}{b_{1}=\displaystyle\frac{\ln(S_{\mathrm{max}}/S_{0})+(-r+q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ {b_{2}=b_{1}-\sigma\sqrt{T}}\ {b_{3}=\displaystyle\frac{\ln(S_{\mathrm{max}}/S_{0})+(r-q-\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ {Y_{2}=\displaystyle\frac{2(r-q-\sigma^{2}/2)\ln(S_{\mathrm{max}}/S_{0})}{\sigma^{2}}}\end{array}
$$  

and $S_{\mathrm{max}}$ is the maximum asset price achieved to date. (If the lookback has just been originated, then $S_{\mathrm{max}}=S_{\mathrm{0}}$  

A floating lookback call is a way that the holder can buy the underlying asset at the. lowest price achieved during the life of the option. Similarly, a floating lookback put is a way that the holder can sell the underlying asset at the highest price achieved during the life of the option.  

# Example 26.2  

Consider a newly issued floating lookback put on a non-dividend-paying stock. where the stock price is 50, the stock price volatility is. $40\%$ per annum, the risk-free rate is $10\%$ per annum, and the time to maturity is 3 months. In this. case, $S_{\mathrm{max}}=50$ $S_{0}=50$ $r=0.1$ $q=0$ $\sigma=0.4$ , and $T=0.25$ $b_{1}=-0.025$ $b_{2}=-0.225$ $b_{3}=0.025$ and $Y_{2}=0$ , so that the value of the lookback put. is 7.79. A newly issued floating lookback call on the same stock is worth 8.04.  

In a fixed lookback option, a strike price is specified. For a fixed lookback call option, the payoff is the same as a regular European call option except that the final asset price is replaced by the maximum asset price achieved during the life of the option. For a fixed lookback put option, the payoff is the same as a regular European put option except that the the final asset price is replaced by the minimum asset price achieved during the life of the option. Define. $S_{\mathrm{max}}^{*}=\operatorname*{max}(S_{\mathrm{max}},K)$ , where as before $S_{\mathrm{max}}$ is the maximum asset price achieved to date and $K$ is the strike price. Also, define. $p_{\mathrm{fl}}^{*}$ as the value of a floating lookback put which lasts for the same period as the fixed lookback call when the actual maximum asset price so far, $S_{\mathrm{max}}$ , is replaced by $S_{\mathrm{max}}^{*}$ . A put-call parity type of argument shows that the value of the fixed lookback call option, $c_{\mathrm{fix}}$ is given by8  

$$
c_{\mathrm{fix}}=p_{\mathrm{fl}}^{\ast}+S_{0}e^{-q T}-K e^{-r T}
$$  

Similarly, if $S_{\mathrm{min}}^{*}=\operatorname*{min}(S_{\mathrm{min}},K)$ , then the value of a fixed lookback put option, $p_{\mathrm{fix}}$ is given by  

$$
p_{\mathrm{fix}}=c_{\mathrm{fl}}^{\ast}+K e^{-r T}-S_{0}e^{-q T}
$$  

where $c_{\mathrm{fl}}^{*}$ is the value of a floating lookback call that lasts for the same period as the fixed lookback put when the actual minimum asset price so far,. $S_{\mathrm{min}}$ , is replaced by $S_{\mathrm{min}}^{*}$ . This shows that the equations given above for floating lookbacks can be modified. to price fixed lookbacks.  

Lookbacks are appealing to investors, but very expensive when compared with. regular options. As with barrier options, the value of a lookback option is liable to. be sensitive to the frequency with which the asset price is observed for the purposes of computing the maximum or minimum. The formulas above assume that the asset price is observed continuously. Broadie, Glasserman, and Kou provide a way of adjusting the formulas we have just given for the situation where the asset price is observed. discretely.  
