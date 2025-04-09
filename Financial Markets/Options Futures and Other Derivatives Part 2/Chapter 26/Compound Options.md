# 26.7 COMPOUND OPTIONS  

Compound options are options on options. There are four main types of compound options: a call on a call, a put on a call, a call on a put, and a put on a put. Compound options have two strike prices and two exercise dates. Consider, for example, a call on a call. On the first exercise date, $T_{1}$ , the holder of the compound option is entitled to pay the first strike price, $K_{1}$ , and receive a call option. The call option gives the holder the right to buy the underlying asset for the second strike price, $K_{2}$ , on the second exercise date, $T_{2}$ . The compound option will be exercised on the first exercise date only if the value of the option on that date is greater than the first strike price.  

When the usual geometric Brownian motion assumption is made, European-style. compound options can be valued analytically in terms of integrals of the bivariate normal distribution.2 with our usual notation, the value at time zero of a European call. option on a call option is  

$$
S_{0}e^{-q T_{2}}M(a_{1},b_{1};\sqrt{T_{1}/T_{2}})-K_{2}e^{-r T_{2}}M(a_{2},b_{2};\sqrt{T_{1}/T_{2}})-e^{-r T_{1}}K_{1}N(a_{2})
$$  

where  

$$
\begin{array}{l}{{a_{1}={\displaystyle\frac{\ln(S_{0}/S^{*})+(r-q+\sigma^{2}/2)T_{1}}{\sigma\sqrt{T_{1}}}},a_{2}=a_{1}-\sigma\sqrt{T_{1}}}}\ {{b_{1}={\displaystyle\frac{\ln(S_{0}/K_{2})+(r-q+\sigma^{2}/2)T_{2}}{\sigma\sqrt{T_{2}}}},b_{2}=b_{1}-\sigma\sqrt{T_{2}}}}\end{array}
$$  

The function $M({a},{b};{\rho})$ is the cumulative bivariate normal distribution function that the first variable will be less than $a$ and the second will be less than $^b$ when the coefficient of correlation between the two is $\rho$ 3 The variable $S^{*}$ is the asset price at time $T_{1}$ for which the option price at time $T_{1}$ equals $K_{1}$ . If the actual asset price is above $S^{*}$ at time $T_{1}$ , the first option will be exercised; if it is not above $S^{*}$ , the option expires worthless.  

With similar notation, the value of a European put on a call is  

$$
K_{2}e^{-r T_{2}}M(-a_{2},b_{2};-\sqrt{T_{1}/T_{2}})-S_{0}e^{-q T_{2}}M(-a_{1},b_{1};-\sqrt{T_{1}/T_{2}})+e^{-r T_{1}}K_{1}N(-a_{2})
$$  

The value of a European call on a put is  

$$
K_{2}e^{-r T_{2}}M(-a_{2},-b_{2};\sqrt{T_{1}/T_{2}})-S_{0}e^{-q T_{2}}M(-a_{1},-b_{1};\sqrt{T_{1}/T_{2}})-e^{-r T_{1}}K_{1}N(-a_{2})
$$  

The value of a European put on a put is  

$$
S_{0}e^{-q T_{2}}M(a_{1},-b_{1};-\sqrt{T_{1}/T_{2}})-K_{2}e^{-r T_{2}}M(a_{2},-b_{2};-\sqrt{T_{1}/T_{2}})+e^{-r T_{1}}K_{1}N(a_{2})
$$  
