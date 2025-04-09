# 16.5 APPLICATION TO OPTION PAYOFFS  

The major advantage of the dirac delta functions, interpreted as the limits of distributions, is in differentiating functions that have points that cannot be differentiated in the usual sense. There are many such points in option trading. The payoff at the strike $K$ is one example. Knock-in, knock-out barriers is another example. Dirac delta will be useful for discussing derivatives at those points.  

Before we proceed, for simplicity we will assume in this section that interest rates are equal to zero:  

$$
r_{t}=0
$$  

We also assume that the underlying. $S_{T}$ follows the risk-neutral SDE, which in this case will be given by  

$$
\mathrm{d}S_{T}=\sigma(S_{t})S_{t}\mathrm{d}W_{t}
$$  

Note that with interest rates being zero, the drift is eliminated and that the volatility is not of the Black-Scholes form. It depends on the random variable. $S_{t}$ Let  

$$
\begin{array}{r l}{f(S_{T})}&{{}=\operatorname*{max}[S_{T}-K,0]}\ {}&{{}={(S_{t}-K)}^{+}}\end{array}
$$  

be the vanilla call option payoff shown in Figure 16.4. The function is not differentiable at. $S_{T}=K$   
yet its first-order derivative is like a step function. More interestingly, the second-order derivative.   
can be interpreted as a dirac delta function. These derivatives are shown in Figures 16.4 and 16.5.  

![](images/84af7d7cca5683f0004509b7f80b494242a00c1ad87c9aab070852487d1aa80a.jpg)  

# FIGURE 16.4  

Call option payoff and first derivative.  

![](images/10903b1facec339c139272a2950b19a0a2c6b3acb094ab332f18fd6a5cbf3504.jpg)  

# FIGURE 16.5  

Second derivative and dirac delta function.  

Now write the equivalent of Ito's Lemma in a setting where functions have kinks as in the. option payoff case. This is called Tanaka's formula and essentially extends Ito's Lemma to functions that cannot be differentiated at all points. We can write.  

where we define  

$$
\mathrm{d}(S_{t}-K)^{+}=\frac{\partial(S_{t}-K)^{+}}{\partial S_{t}}\mathrm{d}S_{t}+\frac{1}{2}\frac{\partial^{2}(S_{t}-K)^{+}}{\partial S_{t}^{2}}\sigma(S_{t})^{2}\mathrm{d}t
$$  

$$
\frac{\partial(S_{t}-K)^{+}}{\partial S_{t}}=1_{s_{t}>K}
$$  

$$
\frac{\hat{\sigma}^{2}(S_{t}-K)^{+}}{\hat{\sigma}S_{t}^{2}}=\delta_{K}(S_{t})
$$  

Taking integrals from $t_{0}$ to $T$ we get:  

$$
\left(S_{T}-K\right)^{+}=\left(S_{t_{0}}-K\right)^{+}+\intop_{t_{0}}^{T}1_{s_{t}>K}\mathrm{d}S_{t}+\frac{1}{2}\intop_{t_{0}}^{T}\frac{\partial^{2}\left(S_{t}-K\right)^{+}}{\partial S_{t}^{2}}\sigma(s_{t})^{2}\mathrm{d}t
$$  

where the first term on the right-hand side is the time value of the option at time $t_{0}$ and is known with certainty. We also know that with zero interest rates, the option price. $C\left({{S}_{t_{0}}}\right)$ will be given by  

$$
C\left({{s}_{t}}_{0}\right)={{E}_{t_{0}}^{\tilde{P}}}{{({S}_{T}}-K)^{+}}
$$  

Now, using the risk-adjusted probability $\tilde{P}$ , (i) apply the expectation operator to both sides of Eq. (16.13), (ii) change the order of integration and expectation, and (iii) use the property of dirac delta functions in eliminating the terms valued at points other than $S_{t}=K$ We obtain the characterization of the option price as:  

$$
\begin{array}{r l}{E_{t}^{P}[(S_{T}{-}K)^{+}]}&{=\big(S_{t_{0}}{-}K\big)^{+}+\displaystyle\int_{t_{0}}^{T}(K)^{2}\phi_{t}(K)\mathrm{d}t}\ &{=C\big(S_{t_{0}}\big)}\end{array}
$$  

where $\phi_{t}(.)$ is the continuous density function that corresponds to the risk-adjusted probability of $S_{t}$ 4 This means that the time value of the option depends (i) on the intrinsic value of the option  

(ii) on the time spent around $K$ during the life of the option, and (iii) on the volatility at that strike, $\sigma(K)$  

The main point for us is that this expression shows that the option price depends not on the overal volatility, but on the volatility of $S_{t}$ around $K$ This is exactly what the notion of volatility smile is.  

# 16.5.1 AN INTERPRETATION OF DYNAMIC HEDGING  

There are many dynamic strategies that replicate an option's final payoff. The best known is delta hedging. In delta hedging, the financial engineer will buy or sell the delta $=D_{t}$ units of the underlying, borrow any necessary funds, and adjust $D_{t}$ as the underlying $S_{t}$ moves over time. As $t\rightarrow T,$ the expiration date, this will duplicate the option's payoff. This is the case because, as the time value goes to zero the option price merges with $\left(S_{T}-K\right)^{+}$  

However, there is an alternative dynamic hedging procedure that is similar to the approach adopted in the previous section. The dynamic hedging technique, called stop-loss strategy, is as follows.  

In order to replicate the payoff of the long call, hold one unit of $S_{t}$ if $K<S_{t}$ . Otherwise hold no $S_{t}$ . This strategy requires that as $S_{t}$ crosses level $K$ , we keep adjusting the position as soon as possible. Either buy one unit of $S_{t}$ or sell the $S_{t}$ immediately as $S_{t}$ crosses the $K$ from left to right or from right to left, respectively. The $\mathrm{P}/\mathrm{L}$ of this position is given by the term  

$$
\frac{1}{2}\int_{t_{0}}^{T}\frac{\partial^{2}\left(S_{t_{0}}-K\right)^{+}}{\partial S_{t}^{2}}\sigma(S_{t})^{2}\mathrm{d}t
$$  

Clearly the switches at $S_{t}=K$ cannot be done instantaneously at zero cost. The trader is moving. with time $\Delta$ while the underlying Wiener process is moving at a faster rate. $\sqrt{\Delta}$ These adjustments are shown in Figures 16.6 and 16.7. The resulting hedging cost is the options value.  

![](images/fc79b648a0283bef9558132d185e002210afe21ea9b88b61b5ce4b2e8e4abf2e.jpg)  

# FIGURE 16.6  

Hedging strategy adjustment--call option.  

![](images/67a1b301769657a03f957248e8ae125ac9c42d91ac4057d18fef0d9a185ca9bc.jpg)  

# FIGURE 16.7  

Hedging strategy adjustment and positions.  
