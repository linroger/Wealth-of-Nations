# 14.6 ITO'S LEMMA  

The price of a stock option is a function of the underlying stock's price and time. More. generally, we can say that the price of any derivative is a function of the stochastic variables underlying the derivative and time. A serious student of derivatives must,. therefore, acquire some understanding of the behavior of functions of stochastic variables. An important result in this area was discovered by the mathematician. K. Ito in 1951, and is known as Ito's lemma..  

Suppose that the value of a variable $x$ follows the Ito process  

$$
d x=a(x,t)d t+b(x,t)d z
$$  

where $d z$ is a Wiener process and $a$ and $^b$ are functions of $x$ and $t.$ The variable $x$ has a drift rate of $a$ and a variance rate of $b^{2}$ . Ito's lemma shows that a function $G$ of $x$ and $t$ follows the process  

$$
d G=\Biggl(\frac{\partial G}{\partial x}a+\frac{\partial G}{\partial t}+\frac{1}{2}\frac{\partial^{2}G}{\partial x^{2}}b^{2}\Biggr)d t+\frac{\partial G}{\partial x}b d z
$$  

where the $d z$ is the same Wiener process as in equation (14.11). Thus, $G$ also follows an Ito process, with a drift rate of  

$$
{\frac{\partial G}{\partial x}}a+{\frac{\partial G}{\partial t}}+{\textstyle{\frac{1}{2}}}{\frac{\partial^{2}G}{\partial x^{2}}}b^{2}
$$  

and a variance rate of  

$$
\left({\frac{\partial G}{\partial x}}\right)^{2}b^{2}
$$  

A completely rigorous proof of Ito's lemma is beyond the scope of this book. In the appendix to this chapter, we show that the lemma can be viewed as an extension of wellknown results in differential calculus..  

Earlier, we argued that  

$$
d S=\mu S d t+\sigma S d z
$$  

with $\mu$ and $\sigma$ constant, is a reasonable model of stock price movements. From Ito's lemma, it follows that the process followed by a function $G$ of $S$ and $t$ is  

$$
d G=\left({\frac{\partial G}{\partial S}}\mu S+{\frac{\partial G}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}G}{\partial S^{2}}}\sigma^{2}S^{2}\right)d t+{\frac{\partial G}{\partial S}}\sigma S d z
$$  

Note that both $S$ and $G$ are affected by the same underlying source of uncertainty,. $d z$   
This proves to be very important in the derivation of the Black-Scholes-Merton results.  

# Application to Forward Contracts  

To illustrate Ito's lemma, consider a forward contract on a non-dividend-paying stock. Assume that the risk-free rate of interest is constant and equal to $r$ for all maturities. From equation (5.1),  

$$
F_{0}=S_{0}e^{r T}
$$  

where $F_{0}$ is the forward price at time zero, $S_{0}$ is the spot price at time zero, and $T$ is the time to maturity of the forward contract.  

We are interested in what happens to the forward price as time passes. We define $F$ as the forward price at a general time. $t$ , and $S$ as the stock price at time $t$ with $t<T.$ The relationship between $F$ and $S$ is given by  

$$
F=S e^{r(T-t)}
$$  

Assuming that the process for. $S$ is given by equation (14.13), we can use Ito's lemma to determine the process for $F,$ From equation (14.15),  

$$
\frac{\partial F}{\partial S}=e^{r(T-t)},\frac{\partial^{2}F}{\partial S^{2}}=0,\frac{\partial F}{\partial t}=-r S e^{r(T-t)}
$$  

From equation (14.14), the process for $F$ is given by  

$$
d{\cal F}=[e^{r(T-t)}\mu S-r S e^{r(T-t)}]d t+e^{r(T-t)}\sigma S d z
$$  

Substituting $F$ for $S e^{r(T-t)}$ gives  

$$
d F=(\mu-r)F d t+\sigma F d z
$$  

Like $S$ , the forward price $F$ follows geometric Brownian motion. It has the same volatility as $S$ and an expected growth rate of $\mu\mathrm{~-~}r$ rather than $\mu$  
