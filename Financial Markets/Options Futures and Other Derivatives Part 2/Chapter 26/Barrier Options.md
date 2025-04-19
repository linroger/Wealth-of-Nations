---
tags:
  - '#barrier_options'
  - '#down_and_in_put'
  - '#down_and_out_call'
  - '#knock_in_options'
  - '#knock_out_options'
  - '#option_valuation'
  - '#parisian_options'
  - '#up_and_in_put'
  - '#up_and_out_call'
  - '#vega'
---
# 26.9 BARRIER OPTIONS  

Barrier options are options where the payoff depends on whether the underlying asset's price reaches a certain level during a certain period of time..  

A number of different types of barrier options regularly trade in the over-the-counter. market. They are attractive to some market participants because they are less expensive than the corresponding regular options. These barrier options can be classified as either knock-out options or knock-in options. A knock-out option ceases to exist when the underlying asset price reaches a certain barrier; a knock-in option comes into existence only when the underlying asset price reaches a barrier..  

Equations (17.4) and (17.5) show that the values at time zero of a regular call and put option are  

$$
\begin{array}{l}{{c=S_{0}e^{-q T}N(d_{1})-K e^{-r T}N(d_{2})}}\ {{p=K e^{-r T}N(-d_{2})-S_{0}e^{-q T}N(-d_{1})}}\end{array}
$$  

where  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{0}/K)+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\ {{d_{2}=\displaystyle\frac{\ln(S_{0}/K)+(r-q-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

A down-and-out call is one type of knock-out option. It is a regular call option that ceases to exist if the asset price reaches a certain barrier level $H$ . The barrier level is below the initial asset price. The corresponding knock-in option is a down-and-in call. This is a regular call that comes into existence only if the asset price reaches the barrier level.  

If $H$ is less than or equal to the strike price, $K$ , the value of a down-and-in call at time zero is  

$$
c_{\mathrm{di}}=S_{0}e^{-q T}(H/S_{0})^{2\lambda}N(y)-K e^{-r T}(H/S_{0})^{2\lambda-2}N(y-\sigma\sqrt{T})
$$  

where  

$$
\begin{array}{l}{\displaystyle{\lambda=\frac{r-q+\sigma^{2}/2}{\sigma^{2}}}}\ {\displaystyle{y=\frac{\ln[H^{2}/(S_{0}K)]}{\sigma\sqrt{T}}+\lambda\sigma\sqrt{T}}}\end{array}
$$  

Because the value of a regular call equals the value of a down-and-in call plus the value of a down-and-out call, the value of a down-and-out call is given by  

$$
c_{\mathrm{do}}=c-c_{\mathrm{di}}
$$  

If $H\geq K$ , then  

$$
\begin{array}{r l}{c_{\mathrm{do}}=S_{0}N(x_{1})e^{-q T}-K e^{-r T}N(x_{1}-\sigma\sqrt{T})}&{{}}\ {-S_{0}e^{-q T}(H/S_{0})^{2\lambda}N(y_{1})+K e^{-r T}(H/S_{0})^{2\lambda-2}N(y_{1}-\sigma\sqrt{T})}&{{}}\end{array}
$$  

and  

$$
c_{\mathrm{di}}=c-c_{\mathrm{do}}
$$  

where  

$$
x_{1}=\frac{\ln(S_{0}/H)}{\sigma\sqrt{T}}+\lambda\sigma\sqrt{T},y_{1}=\frac{\ln(H/S_{0})}{\sigma\sqrt{T}}+\lambda\sigma\sqrt{T}
$$  

An up-and-out call is a regular call option that ceases to exist if the asset price reaches a barrier level, $H.$ that is higher than the current asset price. An up-and-in call is a regular call option that comes into existence only if the barrier is reached. When $H$ is less than or equal to $K$ , the value of the up-and-out call, $c_{\mathrm{uo}}.$ is zero and the value of the up-andin call, $c_{\mathrm{ui}}$ , is $c$ . When $H$ is greater than $K$  

$$
\begin{array}{r l}{\mathrm{\ddot{\Psi}u i}=S_{0}N(x_{1})e^{-q T}-K e^{-r T}N(x_{1}-\sigma\sqrt{T})-S_{0}e^{-q T}(H/S_{0})^{2\lambda}[N(-y)-N(-y_{1})]\qquad}&{{}}\ {+K e^{-r T}(H/S_{0})^{2\lambda-2}[N(-y+\sigma\sqrt{T})-N(-y_{1}+\sigma\sqrt{T})]}&{{}}\end{array}
$$  

and  

$$
c_{\mathrm{uo}}=c-c_{\mathrm{ui}}
$$  

Put barrier options are defined similarly to call barrier options. An up-and-out put is a put option that ceases to exist when a barrier, $H$ , that is greater than the current asset. price is reached. An up-and-in put is a put that comes into existence only if the barrier is reached. When the barrier,. $H$ , is greater than or equal to the strike price, $K$ , their prices are  

$$
p_{\mathrm{ui}}=-S_{0}e^{-q T}(H/S_{0})^{2\lambda}N(-y)+K e^{-r T}(H/S_{0})^{2\lambda-2}N(-y+\sigma\sqrt{T})
$$  

and  

$$
p_{\mathrm{uo}}=p\:-\:p_{\mathrm{ui}}
$$  

When $H$ is less than or equal to $K$  

$$
\begin{array}{r}{\mathrm{\lambda}_{7\mathrm{uo}}=\mathrm{\lambda}-S_{0}N(-x_{1})e^{-q T}+K e^{-r T}N(-x_{1}+\sigma\sqrt{T})\qquad}\ {\mathrm{\lambda}+\mathrm{\lambda}S_{0}e^{-q T}(H/S_{0})^{2\lambda}\mathrm{\Lambda}N(-y_{1})-K e^{-r T}(H/S_{0})^{2\lambda-2}N(-y_{1}+\sigma\sqrt{T})\qquad}\end{array}
$$  

and  

$$
p_{\mathrm{ui}}=p\mathrm{~-~}p_{\mathrm{uo}}
$$  

A down-and-out put is a put option that ceases to exist when a barrier less than the. current asset price is reached. A down-and-in put is a put option that comes into  

existence only when the barrier is reached. When the barrier is greater than the strike price, $p_{\mathrm{do}}=0$ and $p_{\mathrm{di}}=p$ . When the barrier is less than the strike price,.  

$$
\begin{array}{r l}{p_{\mathrm{di}}=}&{-S_{0}N(-x_{1})e^{-q T}+K e^{-r T}N(-x_{1}+\sigma\sqrt{T})+S_{0}e^{-q T}(H/S_{0})^{2\lambda}[N(y)-N(y_{1})]}\ &{\qquad-K e^{-r T}(H/S_{0})^{2\lambda-2}\left[N(y-\sigma\sqrt{T})-N(y_{1}-\sigma\sqrt{T})\right.}\end{array}
$$  

and  

$$
p_{\mathrm{do}}=p-p_{\mathrm{di}}
$$  

All of these valuations make the usual assumption that the probability distribution for the asset price at a future time is lognormal. An important issue for barrier options is the frequency with which the asset price,. $S$ is observed for purposes of determining whether the barrier has been reached. The analytic formulas given in this section assume that $S$ is observed continuously and sometimes this is the case.4 Often, the terms of a contract state that $S$ is observed periodically; for example, once a day at $3\mathrm{p.m}$ . Broadie, Glasserman, and Kou provide a way of adjusting the formulas we have just given for the situation where the price of the underlying is observed discretely. The barrier level $H$ is replaced by $H e^{0.5826\sigma{\sqrt{T/m}}}$ for an up-and-in or up-and-out option and by. $H e^{-0.5826\sigma{\sqrt{T/m}}}$ for a down-and-in or down-and-out option, where $m$ is the number of times the asset. price is observed (so that. $T/m$ is the time interval between observations).  

Barrier options often have quite different properties from regular options. For. example, sometimes vega is negative. Consider an up-and-out call option when the. asset price is close to the barrier level. As volatility increases, the probability that the barrier will be hit increases. As a result, a volatility increase can cause the price of the barrier option to decrease in these circumstances.  

One disadvantage of the barrier options we have considered so far is that a "spike" in the asset price can cause the option to be knocked in or out. An alternative structure is a Parisian option, where the asset price has to be above or below the barrier for a period of time for the option to be knocked in or out. For example, a down-and-out Parisian put option with a strike price equal to. $90\%$ of the initial asset price and a barrier at. $75\%$ of the initial asset price might specify that the option is knocked out if the asset. price is below the barrier for 50 days. The confirmation might specify that the 50 days are a "continuous period of 50 days" or "any 50 days during the option's life." Parisian options are more difficult to value than regular barrier options. Monte Carlo simulation and binomial trees can be used with the enhancements discussed in Sections 27.5 and 27.6.  
