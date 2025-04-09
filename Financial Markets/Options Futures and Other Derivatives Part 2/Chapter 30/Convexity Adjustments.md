# 30.1 CONVEXITY ADJUSTMENTS  

Consider first an instrument that provides a payoff dependent on a bond yield observed at the time of the payoff.  

Usually the forward value of a variable $S$ is calculated with reference to a forward contract that pays off $S_{T}-K$ at time $T.$ It is the value of $K$ that causes the contract to  

have zero value. Forward yields are defined differently. A forward bond yield is the yield implied by the forward bond price.  

Suppose that $B_{T}$ is the price of a bond at time. $T,y_{T}$ is its yield, and the (bond pricing) relationship between $B_{T}$ and $y_{T}$ is  

$$
B_{T}=G(y_{T})
$$  

Define $B_{F}$ as the forward bond price at time zero for a transaction maturing at time $T$ and $y_{F}$ as the forward bond yield at time zero. The definition of a forward bond yield means that  

$$
B_{F}=G(y_{F})
$$  

The function $G$ is nonlinear. This means that, when the expected future bond price equals the forward bond price (so that we are in a world defined by a numeraire equal to a zero-coupon bond maturing at time $T$ ), the expected future bond yield does not equal the forward bond yield.  

This is illustrated in Figure 30.1, which shows the relationship between bond prices and bond yields at time $T.$ For simplicity, suppose that there are only three possible bond prices, $B_{1},B_{2}$ and $B_{3}$ and that they are equally likely in a world defined by numeraire $\textstyle P(t,T)$ . Assume that the bond prices are equally spaced, so that $B_{2}-B_{1}=$ $B_{3}-B_{2}$ . The forward bond price is the expected bond price $B_{2}$ . The bond prices translate into three equally likely bond yields: $y_{1},y_{2}$ , and $y_{3}$ . These are not equally spaced. The variable $y_{2}$ is the forward bond yield because it is the yield corresponding to the forward bond price. The expected bond yield is the average of $y_{1},y_{2}$ , and $y_{3}$ and is clearly greater than $y_{2}$  

Consider a derivative that provides a payoff dependent on the bond yield at time $T$ From equation (28.20), it can be valued by (a) calculating the expected payoff in a world defined by a numeraire equal to a zero-coupon bond maturing at time $T$ and (b) discounting at the current risk-free rate for maturity $T.$ We know that the expected bond price equals the forward price in the world being considered. We therefore need to know the value of the expected bond yield when the expected bond price equals the forward bond price. The analysis in the appendix at the end of this chapter shows that an approximate expression for the required expected bond yield is  

![](8f122cdeae0db04e27827e292adab733ac3c9eda09f3549871e7f9569b314bd7.jpg)  
Figure 30.1 Relationship between bond prices and bond yields at time $T$  

$$
E_{T}(y_{T})=y_{F}-{\textstyle{\frac{1}{2}}}y_{F}^{2}\sigma_{y}^{2}T\frac{G^{\prime\prime}(y_{F})}{G^{\prime}(y_{F})}
$$  

where $G^{\prime}$ and $G^{\prime\prime}$ denote the first and second partial derivatives of. $G$ $E_{T}$ denotes expectations in a world that is defined by numeraire. $\textstyle P(t,T)$ , and $\sigma_{y}$ is the forward yield. volatility. It follows that the expected payoff can be discounted at the current risk-free rate for maturity $T$ provided the expected bond yield is assumed to be.  

$$
y_{F}-{\textstyle\frac{1}{2}}y_{F}^{2}\sigma_{y}^{2}T\frac{G^{\prime\prime}(y_{F})}{G^{\prime}(y_{F})}
$$  

rather than $y_{F}$ . The difference between the expected bond yield and the forward bond yield  

$$
-{\frac{1}{2}}y_{F}^{2}\sigma_{y}^{2}T{\frac{G^{\prime\prime}(y_{F})}{G^{\prime}(y_{F})}}
$$  

is known as a convexity adjustment. It corresponds to the difference between $y_{2}$ and the expected yield in Figure 30.1. (The convexity adjustment is positive because. $G^{\prime}(y_{F})<0$ and $G^{\prime\prime}(y_{F})>0.$  

In addition to valuing a derivative dependent on a bond yield, equation (30.1) can be used to value a derivative dependent on a swap rate. We make the approximation that the $N\cdot$ -year swap rate at time $T$ equals the yield at that time on an. $N$ -year bond with a coupon equal to today's forward swap rate..  

# Example 30.1  

Consider an instrument that provides a payoff in 3 years equal to the 3-year swap rate at that time multiplied by $\$100$ . Suppose that payments are made annually on the swap, the swap rate for all maturities is. $6\%$ per annum with annual compounding, the volatility for the forward swap rate (implied from swap option prices) is $22\%$ . The 3-year risk-free zero rate is. $5\%$ with annual compounding. When the swap rate is approximated as the yield on a. $6\%$ bond, the relevant function $G(y)$ is  

$$
{\begin{array}{l}{G(y)={\frac{0.06}{1+y}}+{\frac{0.06}{\left(1+y\right)^{2}}}+{\frac{1.06}{\left(1+y\right)^{3}}}}\ {G^{\prime}(y)=-{\frac{0.06}{\left(1+y\right)^{2}}}-{\frac{0.12}{\left(1+y\right)^{3}}}-{\frac{3.18}{\left(1+y\right)^{4}}}}\ {G^{\prime\prime}(y)={\frac{0.12}{\left(1+y\right)^{3}}}+{\frac{0.36}{\left(1+y\right)^{4}}}+{\frac{12.72}{\left(1+y\right)^{5}}}}\end{array}}
$$  

In this case the forward yield $y_{F}$ is 0.06, so that $G^{\prime}(y_{F})=-2.6730$ and $G^{\prime\prime}(y_{F})=9.8910$ From equation (30.1),  

$$
E_{T}(y_{T})=0.06+{\textstyle{\frac{1}{2}}}\times0.06^{2}\times0.22^{2}\times3\times{\frac{9.8910}{2.6730}}=0.06097
$$  

A forward swap rate of. $6.097\%$ rather than $6\%$ should therefore be assumed when valuing the instrument. The instrument is worth  

$$
\frac{100\times0.06097}{1.05^{3}}=5.27
$$  

or $\$5.27$ . (This compares with a price of $\$5.18$ obtained without any convexity adjustment.)  
