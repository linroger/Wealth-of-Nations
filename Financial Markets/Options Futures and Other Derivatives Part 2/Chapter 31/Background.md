# 31.1 BACKGROUND  

The risk-free short rate, $r.$ at time $t$ is the rate that applies to an infinitesimally short period of time at time $t.$ It is sometimes referred to as the instantaneous short rate. Bond prices, option prices, and other derivative prices depend only on the process followed by $r$ in the traditional risk-neutral world. As explained in Chapter 28, the traditional riskneutral world is a world where, in a very short time period between. $t$ and $t+\Delta t$ , investors earn on average $r(t)\Delta t$ . All risk-neutral processes for $r$ that will be considered in this chapter are processes in this traditional risk-neutral world.  

From equation (28.19), the value at time $t$ of an interest rate derivative that provides a payoff of $f_{T}$ at time $T$ is  

$$
\hat{E}[e^{-\bar{r}(T-t)}f_{T}]
$$  

where $\bar{r}$ is the average value of. $r$ in the time interval between $t$ and $T$ , and $\hat{E}$ denotes expected value in the traditional risk-neutral world.  

As usual, define. $\textstyle P(t,T)$ as the price at time $t$ of a risk-free zero-coupon bond that pays off $\$1$ at time $T.$ From equation (31.1),  

$$
P(t,T)=\hat{E}[e^{-\bar{r}(T-t)}]
$$  

If $R(t,T)$ is the continuously compounded risk-free interest rate at time $t$ for a term of $T-t$ then  

$$
P(t,T)=e^{-R(t,T)(T-t)}
$$  

so that  

$$
R(t,T)=-\frac{1}{T-t}\ln P(t,T)
$$  

and, from equation (31.2),  

$$
R(t,T)=-{\frac{1}{T-t}}\ln\hat{E}[e^{-\bar{r}(T-t)}]
$$  

This equation enables the term structure of interest rates at any given time to be obtained from the risk-neutral process for. $r$ It shows that, once the process for. $r$ has been defined, everything about the initial zero curve and its evolution through time can. be determined.  

Suppose the risk-neutral process for $r$ is Markov with one factor:.  

$$
d r=m(r,t)d t+s(r,t)d z
$$  

From Ito's lemma, any derivative dependent on $r$ follows the process  

$$
d f=\left({\frac{\partial f}{\partial t}}+m{\frac{\partial f}{\partial r}}+{\frac{1}{2}}s^{2}{\frac{\partial^{2}f}{\partial r^{2}}}\right)d t+s{\frac{\partial f}{\partial r}}d z
$$  

Because we are working in the traditional risk-neutral world, if the derivative provides no income, this process must have the form.  

$$
~d f=r f d t+\cdots.
$$  

so that  

$$
{\frac{\partial f}{\partial t}}+m{\frac{\partial f}{\partial r}}+{\frac{1}{2}}s^{2}{\frac{\partial^{2}f}{\partial r^{2}}}=r f
$$  

This is the equivalent of the Black-Scholes-Merton differential equation for interest rate derivatives. One particular solution to the equation must be the zero-coupon bond price $\textstyle P(t,T)$  

Hence  

$$
{\frac{\partial P(t,T)}{\partial t}}+m{\frac{\partial P(t,T)}{\partial r}}+{\frac{1}{2}}s^{2}{\frac{\partial^{2}P(t,T)}{\partial r^{2}}}=r P(t,T)
$$  

It is tempting to suggest a simple model where the term structure is always flat. All zerocoupon interest rates are then $r$ so that $P(t,T)=e^{-r(t)(T-t)}$ at all times. However, this is not a valid stochastic model for bond prices because it cannot satisfy equation (31.5) for all $T$ unless $m$ and $s$ are both zero..  
