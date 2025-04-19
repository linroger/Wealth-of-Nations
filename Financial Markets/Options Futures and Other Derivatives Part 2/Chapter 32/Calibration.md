---
tags:
  - calibrating_instruments
  - calibration
  - goodness_of_fit
  - levenberg_marquardt
  - volatility_parameters
aliases:
  - model calibration
key_concepts:
  - Bermudan swap option
  - Levenberg-Marquardt procedure
  - calibrating instruments
  - goodness-of-fit measure
  - volatility parameter determination
---

# 32.6 CALIBRATION  

Up to now, we have assumed that the volatility parameters. $a$ and $\sigma$ are known. We now discuss how they are determined. This is known as calibrating the model.  

The volatility parameters are determined from market data on actively traded options. These will be referred to as the calibrating instruments. The first stage is to choose a "goodness-of-fit" measure. Suppose there are $n$ calibrating instruments. A popular goodness-of-fit measure is $\textstyle\sum_{i=1}^{n}({\hat{U}}_{i}-V_{i})^{2}$ where $U_{i}$ is the market price of the ith calibrating instrument and $V_{i}$ is the price given by the model for this instrument. The. objective of calibration is to choose the model parameters so that this goodness-of-fit measure is minimized.  

![](6d511700fdf51e696062820799350ce695ef6325f886d8e8b40ff409deb8991b.jpg)  
Figure 32.9 Tree, produced by DerivaGem, for valuing an American bond option.  

The number of volatility parameters should not be greater than the number of calibrating instruments. If $a$ and $\sigma$ are constant, there are only two volatility parameters. The models can be extended so that. $a$ or $\sigma$ , or both, are functions of time. Step functions. can be used. Suppose, for example, that. $a$ is constant and $\sigma$ is a function of time. We might choose times. $t_{1},t_{2},\ldots,t_{n}$ and assume $\sigma(t)=\sigma_{0}$ for $t\leq t_{1}$ $\sigma(t)=\sigma_{i}$ for $t_{i}<t\leq t_{i+1}$ - $1\leq i\leq n-1$ ),and $\sigma(t)=\sigma_{n}$ for $t>t_{n}$ . There would then be a total of. $n+2$ volatility parameters: $a$ $\sigma_{0}$ $\sigma_{1}$ ,..., and $\sigma_{n}$  

The minimization of the goodness-of-fit measure can be accomplished using the Levenberg-Marquardt procedure.14 When $a$ or $\sigma$ , or both, are functions of time, a penalty function is often added to the goodness-of-fit measure so that the functions are "well behaved". In the example just mentioned, where. $\sigma$ is a step function, an appropriate objective function is  

$$
\sum_{i=1}^{n}(U_{i}-V_{i})^{2}+\sum_{i=1}^{n}w_{1,i}(\sigma_{i}-\sigma_{i-1})^{2}+\sum_{i=1}^{n-1}w_{2,i}(\sigma_{i-1}+\sigma_{i+1}-2\sigma_{i})^{2}
$$  

The second term provides a penalty for large changes in $\sigma$ between one step and the next. The third term provides a penalty for high curvature in $\sigma$ Appropriate values for $w_{1,i}$ and $w_{2,i}$ are based on experimentation and are chosen to provide a reasonable level of smoothness in the $\sigma$ function.  

The calibrating instruments chosen should be as similar as possible to the instrument. being valued. Suppose, for example, that the model is to be used to value a Bermudan-. style swap option that lasts 10 years and can be exercised on any payment date between. year 5 and year 9 into a swap maturing 10 years from today. The most relevant calibrating instruments are $5\times5,6\times4,7\times3,8\times2$ , and $9\times1$ European swap options. (An $n\times m$ European swap option is an. $n$ -year option to enter into a swap lasting for. $m$ years beyond the maturity of the option.)  

The advantage of making $a$ or $\sigma$ , or both, functions of time is that the models can be. fitted more precisely to the prices of instruments that trade actively in the market. The disadvantage is that the volatility structure becomes nonstationary. The volatility term structure given by the model in the future is liable to be quite different from that existing in the market today.15  

A somewhat different approach to calibration is to use all available calibrating instruments to calculate "global-best-fit" $a$ and $\sigma$ parameters. The parameter $a$ is held fixed at its best-fit value. The model can then be used in the same way as BlackScholes-Merton. There is a one-to-one relationship between options prices and the $\sigma$ parameter. The model can be used to calculate implied $\sigma{\mathrm{?s.}}^{16}$ These can be used to assess the $\sigma$ most appropriate for pricing the instrument under consideration.  
