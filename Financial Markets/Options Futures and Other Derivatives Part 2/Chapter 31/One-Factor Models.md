# 31.2 ONE-FACTOR MODELS  

Equilibrium models usually start with assumptions about economic variables and derive a process for the short rate, $r.$ They then explore what the process for $r$ implies about bond prices and option prices.  

In a one-factor equilibrium model, the process for $r$ involves only one source of uncertainty. Usually the process for the short rate is assumed to be stationary in the sense that the parameters of the process are not functions of time. This means that the process we considered earlier can be written as  

$$
d r=m(r)d t+s(r)d z
$$  

The assumption of a single factor is not as restrictive as it might appear. A one-factor model implies that all rates move in the same direction over any short time interval, but not that they all move by the same amount. The shape of the zero curve can therefore change with the passage of time.  

This section considers three one-factor equilibrium models:  

$$
\begin{array}{l l}{m(r)=\mu r;s(r)=\sigma r}&{(\mathrm{RendlemanandBarttermodel})}\ {m(r)=a(b-r);s(r)=\sigma}&{(\mathrm{Vasicekmodel})}\ {m(r)=a(b-r);s(r)=\sigma\sqrt{r}}&{(\mathrm{Cox},\mathrm{Ingersoll},\mathrm{andRossmodel})}\end{array}
$$  

# The Rendleman and Bartter Model  

In Rendleman and Bartter's model, the risk-neutral process for $r$ is1  

$$
d r=\mu r d t+\sigma r d z
$$  

where $\mu$ and $\sigma$ are constants. This means that $r$ follows geometric Brownian motion. The process for $r$ is of the same type as that assumed for a stock price in Chapter 15. It can be represented using a binomial tree similar to the one used for stocks in Chapter 13.  

The assumption that the short-term interest rate behaves like a stock price is a natural starting point but is less than ideal. One important difference between interest rates and stock prices is that interest rates appear to be pulled back to some long-run average level over time. This phenomenon is known as mean reversion. When. $r$ is high, mean reversion tends to cause it to have a negative drift; when. $r$ is low, mean reversion tends. to cause it to have a positive drift. Mean reversion is illustrated in Figure 31.1. The Rendleman and Bartter model does not incorporate mean reversion..  

![](images/075aa26dcb420d9009b4b8013f16a78e2ccbdf3ba3797eb197d455ca26dbaa5c.jpg)  
Figure 31.1 Mean reversion.  

There are compelling economic arguments in favor of mean reversion. When rates are high, the economy tends to slow down and there is low demand for funds from borrowers. As a result, rates decline. When rates are low, there tends to be a high demand for funds on the part of borrowers and rates tend to rise.  

# The Vasicek Model  

In Vasicek's model, the risk-neutral process for $r$ is  

$$
d r=a(b-r)d t+\sigma d z
$$  

where $a,b$ , and $\sigma$ are nonnegative constants. This model incorporates mean reversion. The short rate is pulled to a "reversion level $^b$ at "reversion rate" $a$ . Superimposed upon this pull is a normally distributed stochastic term $\sigma d z$  

Zero-coupon bond prices in Vasicek's model are given by  

$$
P(t,T)=A(t,T)e^{-B(t,T)r(t)}
$$  

where  

$$
B(t,T)=\frac{1-e^{-a(T-t)}}{a}
$$  

and  

$$
A(t,T)=\exp\biggl[\frac{(B(t,T)-T+t)(a^{2}b-\sigma^{2}/2)}{a^{2}}-\frac{\sigma^{2}B(t,T)^{2}}{4a}\biggr]
$$  

(When $a=0$ , these equations become $B(t,T)=T-t$ and $A(t,T)=\exp[\sigma^{2}(T-t)^{3}/6].$  

To see this, note that $m=a(b-r)$ and $s=\sigma$ in differential equation (31.5), so that  

$$
{\frac{\partial P(t,T)}{\partial t}}+a(b-r){\frac{\partial P(t,T)}{\partial r}}+{\frac{1}{2}}{\sigma}^{2}{\frac{\partial^{2}P(t,T)}{\partial r^{2}}}=r P(t,T)
$$  

By substitution, we see that $P(t,T)=A(t,T)e^{-B(t,T)r}$ satisfies this differential equation when  

and  

$$
\begin{array}{c}{{B_{t}-a B+1=0}}\ {{{}}}\ {{A_{t}-a b A B+\frac{1}{2}\sigma^{2}A B^{2}=0}}\end{array}
$$  

where subscripts denote derivatives. The expressions for $A(t,T)$ and $B(t,T)$ in equations (31.7) and (31.8) are solutions to these equations. What is more, because $A(T,T)=1$ and $B(T,T)=0$ , the boundary condition $P(T,T)=1$ is satisfied.  

# The Cox, Ingersoll, and Ross Model  

Cox, Ingersoll, and Ross (CIR) have proposed the following alternative model:3  

$$
\begin{array}{r}{d r}{=a(b-r)d t+\sigma\sqrt{r}d z}\end{array}
$$  

where $a,b$ , and $\sigma$ are nonnegative constants. This has the same mean-reverting drift as Vasicek, but the standard deviation of the change in the short rate in a short period of time is proportional to $\sqrt{r}$ This means that, as the short-term interest rate increases, the. standard deviation increases.  

Bond prices in the CIR model have the same general form as those in Vasicek's model,  

$$
P(t,T)=A(t,T)e^{-B(t,T)r(t)}
$$  

but the functions $B(t,T)$ and $A(t,T)$ are different:  

$$
B(t,T)=\frac{2(e^{\gamma(T-t)}-1)}{(\gamma+a)(e^{\gamma(T-t)}-1)+2\gamma}
$$  

and  

$$
A(t,T)=\Biggl[{\frac{2\gamma e^{(a+\gamma)(T-t)/2}}{(\gamma+a)(e^{\gamma(T-t)}-1)+2\gamma}}\Biggr]^{2a b/\sigma^{2}}
$$  

with $\gamma=\sqrt{a^{2}+2\sigma^{2}}$  

To see this result, substitute. $m=a(b-r)$ and $s=\sigma\sqrt{r}$ into differential equation (31.5) to get  

$$
{\frac{\partial P(t,T)}{\partial t}}+a(b-r){\frac{\partial P(t,T)}{\partial r}}+{\textstyle{\frac{1}{2}}}\sigma^{2}r{\frac{\partial^{2}P(t,T)}{\partial r^{2}}}=r P(t,T)
$$  

As in the case of Vasicek's model, we can prove the bond-pricing result by substituting $P(t,T)=A(t,T)e^{-B(t,T)r}$ into the differential equation. In this case, $A(t,T)$ and $B(t,T)$ are solutions of  

$$
\begin{array}{r}{B_{t}-a B-\frac{1}{2}\pmb{\sigma}^{2}B^{2}+1=0,A_{t}-a b A B=0}\end{array}
$$  

Furthermore, the boundary condition $P(T,T)=1$ is satisfied.  

# Properties of Vasicek and CIR  

The $A(t,T)$ and $B(t,T)$ functions are different for Vasicek and CIR, but for both models  

$$
P(t,T)=A(t,T)e^{-B(t,T)r(t)}
$$  

so that  

$$
\frac{\partial P(t,T)}{\partial r(t)}=-B(t,T)P(t,T)
$$  

From equation (31.3), the zero rate at time $t$ for a period of $T-t$ is  

$$
R(t,T)=-\frac{1}{T-t}\ln A(t,T)+\frac{1}{T-t}B(t,T)r(t)
$$  

This shows that the entire term structure at time. $t$ can be determined as a function of. $r(t)$ once $a,b$ , and $\sigma$ have been chosen. The rate $R(t,T)$ is linearly dependent on $r(t)$ This means that the value of. $r(t)$ determines the level of the term structure at time. $t.$ As shown in Figure 31.2, the shape at a particular time can be upward sloping, downward sloping, or slightly "humped.".  

One difference between Vasicek and CIR is that in Vasicek the short rate, $r(t)$ , can become negative whereas in CIR this is not possible. If $2a b\geq\sigma^{2}$ in CIR, $r(t)$ is never zero; otherwise it occasionally touches zero.  

![](images/3c2cc49245da07a840be43aa45a0842b7672533c004482d5f243627f611ab7f3.jpg)  
Figure 31.2 Possible shapes of term structure in the Vasicek and CIR models.  

From Chapter 4, the duration $D$ of a bond that has a price of $Q$ is given by  

$$
D=-{\frac{1}{Q}}{\frac{\partial Q}{\partial y}}\quad{\mathrm{so~that}}{\frac{\Delta Q}{Q}}=-D\Delta y
$$  

where $y$ is the continuously compounded bond yield. An alternative duration measure $\hat{D}$ , which can be used in conjunction with Vasicek or CIR, is defined as follows:  

$$
\hat{D}=-\frac{1}{Q}\frac{\partial Q}{\partial r}\mathrm{sothat}\frac{\Delta Q}{Q}=-\hat{D}\Delta r
$$  

Here we are measuring the sensitivity of the bond price to the short rate rather than to its yield. Equation (31.9) shows that when we consider a $T$ -maturity zero-coupon bond so. that $Q=P(t,T)$ , the alternative duration measure,. $\hat{D}$ , is equal to $B(t,T)$  

# Example 31.1  

Consider a zero-coupon bond lasting 4 years. In this case, $D=4$ , so that a 10-basispoint ( $0.1\%$ or 0.001) increase in the bond's yield leads to a decrease of approximately $0.4\%$ in the bond price. If Vasicek's model is used with. $a=0.1$  

$$
\hat{D}=B(0,4)=\frac{(1-e^{-0.1\times4})}{0.1}=3.30
$$  

This means that a 10-basis-point increase in the short rate leads to a decrease in the bond price that is approximately $0.33\%$ . The change in the bond price from a certain movement in the short rate is less than that from the same movement in its yield because of the impact of mean reversion.  

When $Q$ is the price of a coupon-bearing bond that provides a cash flow $c_{i}$ at time $T_{i},$  

$$
{\hat{D}}=-{\frac{1}{Q}}{\frac{\partial Q}{\partial r}}=-{\frac{1}{Q}}\sum_{i=1}^{n}c_{i}{\frac{\partial P(t,T_{i})}{\partial r}}=\sum_{i=1}^{n}{\frac{c_{i}P(t,T_{i})}{Q}}{\hat{D}}_{i}
$$  

where $\hat{D}_{i}=B(t,T_{i})$ is the $\hat{D}$ for $\textstyle P(t,T_{i})$ . This shows that the $\hat{D}$ for a coupon-bearing bond can be calculated as a weighted average of the $\hat{D}$ 's for the underlying zero-coupon bonds, similarly to the way the usual duration measure $D$ is calculated (see Table 4.6). This analysis can be extended to cover convexity measures (see Problem 31.11).  

# The Bond Price Process  

The expected growth rate of $\textstyle P(t,T)$ in the traditional risk-neutral world at time $t$ is $r(t)$ because $\textstyle P(t,T)$ is the price of a traded security that provides no income. Since $\textstyle P(t,T)$ is a function of $r(t)$ , the coefficient of $d z(t)$ in the process for $\textstyle P(t,T)$ can be calculated from Ito's lemma as $\sigma\partial P(t,T)/\partial r(t)$ for Vasicek and $\sigma\sqrt{r(t)}\partial P(t,T)/\partial r(t)$ for CIR. Substituting from equation (31.9), the processes for $\textstyle P(t,T)$ in a risk-neutral world are therefore  

$$
\mathrm{asicek:}\quad d P(t,T)=r(t)P(t,T)d t-\sigma B_{\mathrm{vas}}(t,T)P(t,T)d z(t)
$$  

$$
\begin{array}{r l}{{3}\colon}&{{}d P(t,T)=r(t)P(t,T)d t-\sigma\sqrt{r(t)}B_{\mathrm{cir}}(t,T)P(t,T)d z(t)}\end{array}
$$  

where the subscripts to $B$ indicate the model it applies to.  

To compare the term structure of interest rates given by Vasicek and CIR for a particular value of $r$ , it makes sense to use the same $a$ and $^b$ . However, the Vasicek $\sigma$ should be chosen to be approximately equal to the CIR $\sigma$ times $\sqrt{r(t)}$ . For example, if $r$ is $4\%$ and $\sigma$ is 0.01 in Vasicek, an appropriate value for $\sigma$ in CIR would be $0.01/\sqrt{0.04}=0.05$ . Software for experimenting with the models can be found at www-2.rotman.utoronto.ca/\~hull/VasicekCIR.  
