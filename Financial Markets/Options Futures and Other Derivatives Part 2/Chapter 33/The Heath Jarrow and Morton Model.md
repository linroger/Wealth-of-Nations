# 33.1 The heath, JArROw, And morton MOdel  

In 1990 David Heath, Bob Jarrow, and Andy Morton (HJM) published an important paper describing the no-arbitrage conditions that must be satisfied by a model of the yield curve.' To describe their model, we will use the following notation:.  

$\textstyle P(t,T)$ : Price at time $t$ of a risk-free zero-coupon bond with principal. $\$1$ maturing at time $T$ $\Omega_{t}\cdot$ Vector of past and present values of interest rates and bond prices at time $t$ that are relevant for determining bond price volatilities at that time  

$\nu(t,T,\Omega_{t})$ : Volatility of $\textstyle P(t,T)$  

$f(t,T_{1},T_{2})$ : Forward rate as seen at time $t$ for the period between time $T_{1}$ and time $T_{2}$ $F(t,T)$ : Instantaneous forward rate as seen at time $t$ for a contract maturing at. time $T$ $r(t)$ : Short-term risk-free interest rate at time $t$ $d z(t)$ : Wiener process driving term structure movements.  

# Processes for Zero-Coupon Bond Prices and Forward Rates  

We start by assuming there is just one factor and will use the traditional risk-neutral world. A zero-coupon bond is a traded security providing no income. Its return in the traditional risk-neutral world must therefore be $r$ This means that its stochastic process has the form  

$$
d P(t,T)=r(t)P(t,T)d t+\nu(t,T,\Omega_{t})P(t,T)d z(t)
$$  

As the argument $\Omega_{t}$ indicates, the zero-coupon bond's volatility $\nu$ can be, in the most general form of the model, any well-behaved function of past and present interest rates and bond prices. Because a bond's price volatility declines to zero at maturity, we must have2  

$$
\nu(t,t,\Omega_{t})=0
$$  

From equation (4.5), the forward rate $f(t,T_{1},T_{2})$ can be related to zero-coupon bond prices as follows:  

$$
f(t,T_{1},T_{2})=\frac{\ln[P(t,T_{1})]-\ln[P(t,T_{2})]}{T_{2}-T_{1}}
$$  

From equation (33.1) and Ito's lemma,  

and  

$$
\begin{array}{l}{{d\ln[P(t,T_{1})]=\displaystyle\bigg[r(t)-\frac{\nu(t,T_{1},\Omega_{t})^{2}}{2}\bigg]d t+\nu(t,T_{1},\Omega_{t})d z(t)}}\ {{{}}}\ {{d\ln[P(t,T_{2})]=\displaystyle\bigg[r(t)-\frac{\nu(t,T_{2},\Omega_{t})^{2}}{2}\bigg]d t+\nu(t,T_{2},\Omega_{t})d z(t)}}\end{array}
$$  

so that from equation (33.2)  

$$
d f(t,T_{1},T_{2})=\frac{\nu(t,T_{2},\Omega_{t})^{2}-\nu(t,T_{1},\Omega_{t})^{2}}{2(T_{2}-T_{1})}d t+\frac{\nu(t,T_{1},\Omega_{t})-\nu(t,T_{2},\Omega_{t})}{T_{2}-T_{1}}d z(t)
$$  

Equation (33.3) shows that the risk-neutral process for $f$ depends solely on the. $\nu$ s. It depends on $r$ and the. $P$ s only to the extent that the $\nu$ s themselves depend on these variables.  

When we put $T_{1}=T$ and $T_{2}=T+\Delta T$ in equation (33.3) and then take limits as $\Delta T$ tends to zero, $f(t,T_{1},T_{2})$ becomes $F(t,T)$ , the coefficient of $d z(t)$ becomes $-\nu_{T}(t,T,\Omega_{t})$  

and the coefficient of $d t$ becomes  

$$
\frac{1}{2}\frac{\partial[\nu(t,T,\Omega_{t})^{2}]}{\partial T}=\nu(t,T,\Omega_{t})\nu_{T}(t,T,\Omega_{t})
$$  

where the subscript to $\nu$ denotes a partial derivative. It follows that  

$$
d F(t,T)=\nu(t,T,\Omega_{t})\nu_{T}(t,T,\Omega_{t})d t-\nu_{T}(t,T,\Omega_{t})d z(t)
$$  

Once the function. $\nu(t,T,\Omega_{t})$ has been specified, the risk-neutral processes for the $F(t,T)$ 's are known.  

Equation (33.4) shows that there is a link between the drift and standard deviation of an instantaneous forward rate. This is the key HJM result. Integrating. $\nu_{\tau}(t,\tau,\Omega_{t})$ between $\tau=t$ and $\tau=T$ leads to  

$$
\nu(t,T,\Omega_{t})-\nu(t,t,\Omega_{t})=\int_{t}^{T}\nu_{\tau}(t,\tau,\Omega_{t})d\tau
$$  

Because $\nu(t,t,\Omega_{t})=0$ , this becomes  

$$
\nu(t,T,\Omega_{t})=\int_{t}^{T}\nu_{\tau}(t,\tau,\Omega_{t})d\tau
$$  

If $m(t,T,\Omega_{t})$ and $s(t,T,\Omega_{t})$ are the instantaneous drift and standard deviation of $F(t,T)$ , so that  

$$
d F(t,T)=m(t,T,\Omega_{t})d t+s(t,T,\Omega_{t})d z
$$  

then it follows from equation (33.4) that  

$$
m(t,T,\Omega_{t})=s(t,T,\Omega_{t})\int_{t}^{T}s(t,\tau,\Omega_{t})d\tau
$$  

This is the HJM result.  

The process for the short rate $r$ in the general HJM model is non-Markov. This means that the process for $r$ at a future time. $t$ depends on the path followed by $r$ between now and time. $t$ as well as on the the value of. $r$ at time $t$ 3 This is the key problem in implementing a general HJM model. Monte Carlo simulation has to be used. It is difficult to use a tree to represent term structure movements because the tree is usually nonrecombining. Assuming the model has one factor and the tree is binomial as in Figure 33.1, there are $2^{n}$ nodes after $n$ time steps (when $n=30$ $2^{n}$ is about 1 billion).  

The HJM model in equation (33.4) is deceptively complex. A particular forward rate $F(t,T)$ is Markov in most applications of the model and can be represented by a recombining tree. However, the same tree cannot be used for all forward rates. Setting $s(t,T,\Omega_{t})$ equal to a constant, $\sigma$ , leads to the Ho-Lee model (see Problem 33.3); setting $s(t,T,\Omega_{t})=\sigma e^{-a(T-t)}$ leads to the Hull-White model (see Problem 33.4). These are particular Markov cases of HJM where the same recombining tree can be used to represent the short rate, $r$ , and all forward rates.  

Figure 33.1 A nonrecombining tree such as that arising from the general HJM model.  

![](images/ddf7ee0e4be493bb1afeb329ac89c627a8c83c39b8ab349827d2a8baf2888ab3.jpg)  

# Extension to Several Factors  

The HJM result can be extended to the situation where there are several independent factors. Suppose  

$$
d F(t,T)=m(t,T,\Omega_{t})d t+\sum_{k}s_{k}(t,T,\Omega_{t})d z_{k}
$$  

A similar analysis to that just given (see Problem 33.2) shows that  

$$
m(t,T,\Omega_{t})=\sum_{k}s_{k}(t,T,\Omega_{t})\int_{t}^{T}s_{k}(t,\tau,\Omega_{t})d\tau
$$  
