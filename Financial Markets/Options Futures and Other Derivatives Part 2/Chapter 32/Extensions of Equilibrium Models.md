# 32.1 EXTENSIONS OF EQUILIBRIUM MODELS  

It turns out that some equilibrium models can be converted to no-arbitrage models by.   
including a function of time in the drift of the short rate. Here, we consider the Ho-Lee,.   
Hull-White (one- and two-factor), Black-Derman-Toy, and Black-Karasinski models.  

# The Ho-Lee Model  

Ho and Lee proposed the first no-arbitrage model of the term structure in a paper in 1986.1 They presented the model in the form of a binomial tree of bond prices with two.  

![](6d4a47ffbdb629fdd519f70306568552ce97f37514bb45c41df1d918a79df8d2.jpg)  
Figure 32.1 The Ho-Lee model.  

parameters: the short-rate standard deviation and the market price of risk of the short. rate. It has since been shown that the continuous-time limit of the model in the traditional risk-neutral world is.  

$$
d r=\theta(t)d t+\sigma d z
$$  

where $\sigma$ , the instantaneous standard deviation of the short rate, is constant and $\theta(t)$ is a function of time chosen to ensure that the model fits the initial term structure. The variable $\theta(t)$ defines the average direction that $r$ moves at time. $t.$ This is independent of the level of. $r$ The market price of risk, which determines behavior in the real world, is irrelevant when the model is used to price interest rate derivatives.  

Technical Note 31 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes shows that  

$$
\theta(t)=F_{t}(0,t)+\sigma^{2}t
$$  

where $F(0,t)$ is the instantaneous forward rate for a maturity $t$ as seen at time zero and. the subscript $t$ denotes a partial derivative with respect to $t.$ As an approximation,. $\theta(t)$ equals $F_{t}(0,t)$ . This means that the average direction that the short rate will be moving in the future is approximately equal to the slope of the instantaneous forward curve. The Ho-Lee model is illustrated in Figure 32.1. Superimposed on the average movement in the short rate is the normally distributed random outcome.  

Technical Note 31 also shows that  

$$
P(t,T)=A(t,T)e^{-r(t)(T-t)}
$$  

where  

$$
\ln A(t,T)=\ln\frac{P(0,T)}{P(0,t)}+(T-t)F(0,t)-{\textstyle{\frac{1}{2}}}\sigma^{2}t(T-t)^{2}
$$  

From Section 4.8,. $F(0,t)=-\partial\ln P(0,t)/\partial t.$ The zero-coupon bond prices, $P(0,t)$ , are  

known for all $t$ from today's term structure of interest rates. Equation (32.3) therefore gives the price of a zero-coupon bond at a future time $t$ in terms of the short rate at time $t$ and the prices of bonds today.  

# The Hull-white One-Factor Model  

In a paper published in 1990, Hull and White explored extensions of the Vasicek model that provide an exact fit to the initial term structure.? One version of the extended Vasicek model that they consider is  

$$
\begin{array}{r}{d r}{\boldsymbol{\it{\/}}d\boldsymbol{\it{\/}}r=\left[\theta(t)-a r\right]d t+\sigma d\boldsymbol{\it{z}}}\end{array}
$$  

or  

$$
d r=a\Big[\frac{\theta(t)}{a}-r\Big]d t+\sigma d z
$$  

where $a$ and $\sigma$ are constants. This is known as the Hull-White model. It can be characterized as the Ho-Lee model with mean reversion at rate $a$ Alternatively, it can be characterized as the Vasicek model with a time-dependent reversion level. At time $t$ , the short rate reverts to $\theta(t)/a$ at rate $a$ The Ho-Lee model is a particular case of the Hull-White model with $a=0$  

The model has the same amount of analytic tractability as Ho-Lee. Technical Note 31 shows that  

$$
\theta(t)=F_{t}(0,t)+a F(0,t)+\frac{\sigma^{2}}{2a}(1-e^{-2a t})
$$  

![](53ada3c979522778c64b5238e5e8d5122391a01f1e26cafda1849e70442ab8db.jpg)  
Figure 32.2 The Hull-White model.  

The last term in this equation is usually fairly small. If we ignore it, the equation implies.   
that the drift of the process for $r$ at time $t$ is $F_{t}(0,t)+a[F(0,t)-r]$ . This shows that, on.   
average, $r$ follows the slope of the initial instantaneous forward rate curve. When it deviates from that curve, it reverts back to it at rate. $a$ . The model is illustrated in.   
Figure 32.2.  

Technical Note 31 shows that bond prices at time $t$ in the Hull-White model are. given by  

$$
P(t,T)=A(t,T)e^{-B(t,T)r(t)}
$$  

where  

$$
B(t,T)=\frac{1-e^{-a(T-t)}}{a}
$$  

and  

$$
\ln A(t,T)=\ln\frac{P(0,T)}{P(0,t)}+B(t,T)F(0,t)-\frac{1}{4a^{3}}\sigma^{2}(e^{-a T}-e^{-a t})^{2}(e^{2a t}-1)
$$  

As we show in the next section, European bond options can be valued analytically using the Ho-Lee and Hull-White models. A method for representing the models in the form of a trinomial tree is given later in this chapter. This is useful when American options and other derivatives that cannot be valued analytically are considered.  

# The Black-Derman-Toy Model  

In 1990, Black, Derman, and Toy proposed a binomial-tree model for a lognormal. short-rate process. Their procedure for building the binomial tree is explained in. Technical Note 23 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes. It can be shown that the stochastic process corresponding to the model is.  

$$
d\ln r=[\theta(t)-a(t)\ln r]d t+\sigma(t)d z
$$  

with  

$$
a(t)=-{\frac{\sigma^{\prime}(t)}{\sigma(t)}}
$$  

where $\boldsymbol{\sigma^{\prime}}(t)$ is the derivative of $\sigma$ with respect to $t.$ This model has the property that. the interest rate cannot become negative. The Wiener process $d z$ can cause $\ln(r)$ to be negative, but $r$ itself is always positive. One disadvantage of the model is that there. are no analytic properties. A more serious disadvantage is that the way the tree is constructed imposes a relationship between the volatility parameter $\sigma(t)$ and the reversion rate parameter $a(t)$ . The reversion rate is positive only if the volatility of the short rate is a decreasing function of time.  

In practice, the most useful version of the model is when. $\sigma(t)$ is constant. The parameter $a$ is then zero, so that there is no mean reversion and the model reduces to  

$$
d\ln r=\theta(t)d t+\sigma d z
$$  

This can be characterized as a lognormal version of the Ho-Lee model.  

# The Black-Karasinski Model  

In 1991, Black and Karasinski developed an extension of the Black-Derman-Toy. model where the reversion rate and volatility are determined independently of each other.4 The most general version of the model is.  

$$
d\ln r=[\theta(t)-a(t)\ln r]d t+\sigma(t)d z
$$  

The model is the same as Black-Derman-Toy model except that there is no relation between $a(t)$ and $\sigma(t)$ . In practice, $a(t)$ and $\sigma(t)$ are often assumed to be constant, so that the model becomes  

$$
\begin{array}{r}{d\ln r=[\theta(t)-a\ln r]d t+\sigma d z}\end{array}
$$  

As in the case of all the models we are considering, the $\theta(t)$ function is determined to provide an exact fit to the initial term structure of interest rates. The model has no analytic tractability, but later in this chapter we will describe a convenient way of simultaneously determining $\theta(t)$ and representing the process for $r$ in the form of a trinomial tree.  

# The Hull-white Two-Factor Model  

In Section 31.4, we presented a two-factor equilibrium model which is an extension of. Vasicek's model. Hull and White show how this model can be converted into a noarbitrage model by adding $\theta(t)$ in the drift of $r$  

This model provides a richer pattern of term structure movements and a richer. pattern of volatilities than one-factor models of. $r$ For more information on the. analytical properties of the model and the way a tree can be constructed for it, see Technical Note 14 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes..  
