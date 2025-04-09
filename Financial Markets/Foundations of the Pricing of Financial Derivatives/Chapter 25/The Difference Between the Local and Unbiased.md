# 25.3 THE DIFFERENCE BETWEEN THE LOCAL AND UNBIASED EXPECTATIONS HYPOTHESES7

In this section, we will review some of the more technical aspects of term structure math as well as demonstrate that the LEH and UEH are equivalent in discrete time with continuously compounded interest rates. Further, we make no assumption here related to a risk-neutral framework. Our focus is on the actual probability measure. Although the LEH and UEH are not equivalent in discrete time with discretely compounded interest rates, the magnitude of the difference is indistinguishable when applied to empirical data. For our purposes, all bonds are assumed to be default free. Due to the technical nature of this discussion, we adopt more precise notation for this section.

We denote $r(t,t+j)$ as the continuously compounded spot rate observed at time $t$ and maturing at time $t+j$ , the $j$ period spot rate. We suppress the subscript $c$ for continuous compounding in an effort to simplify. We denote $f(t,t+j)$ as the forward rate observed at time $t$ and for maturity $t+j$ , a one-period forward rate. Thus, the spot rate spans time $t$ to $t+j$ whereas the forward rate spans only $t+j-1$ to $t+j$ . Based on this notation, the price at time $t$ of an $_n$ -period zero-coupon bond with par value of one dollar at time $t+n$ is

$$
P(t,t+n)=e^{-[r(t,t+1)+f(t,t+1)+\ldots+f(t,t+n-1)]}.
$$

The continuously compounded holding period return can be expressed as

$$
H P R(t,t+1,n)=\ln{\left[\frac{P(t+1,t+n)}{P(t,t+n)}\right]}.
$$

The UEH states that

$$
f(t,t+j)=E_{t}[r(t+j,t+j+1)];j=1,\ldots,n.
$$

The LEH states that

$$
E_{t}[H P R(t,t+1,j)]=r(t,t+1);j=1,\ldots,n.
$$

Substituting Equation (25.26) into Equation (25.27), we note

$$
\begin{array}{r}{{\begin{array}{r l}{H P R(t,t+1,n)=r(t,t+1)+[f(t,t+1)-r(t+1,t+2)]+[f(t,t+2)-r(t+1,t+3)}}&{{}}\ {\ldots+[f(t,t+n-1)-r(t+1,t+n)].}\end{array}}\ {{\begin{array}{r l}{(25.0-1)\varepsilon~.}&{{}}\ {\ldots+[f(t,t+n-1)-r(t+1,t+n)].}\end{array}}}&{{\begin{array}{r l}{(25.0-1)\varepsilon~.}&{{}}\ {\ldots+[f(t,t+1)-1.0-1]\varepsilon~.}&{{}}\end{array}}}\end{array}
$$

Based on the definition of continuously compounded holding period returns, the LEH can be expressed as

$$
\boldsymbol{r}(t,t+1)=E_{t}\{\ln[P(t+1,t+j)]\}-\ln[P(t,t+j)];j=2,\ldots,n.
$$

Again, substituting for the price from Equation (25.26) and rearranging, we have

$$
0=\sum_{i=1}^{j}\{f(t,t+i)-E_{t}[r(t+1,t+i)]\};j=2,\ldots,n.
$$

Thus, a new interpretation of LEH is related to current expectations of future spot rates over the next time period,. $t$ to $t+1$ . Note that this is not a result of arbitrage forces. leading one to a risk-neutral solution. UEH, however, addresses forecast accuracy over. longer horizons. Note that if LEH holds at time $t$ for two- through. $_n$ -period bonds, we have

$$
f(t,t+j)=E_{t}[r(t+j,t+j+1)];j=1,\ldots,n.
$$

Therefore, if LEH holds for all future time periods, then UEH also holds.

This analysis breaks down with discretely compounded interest rates. Brooks and. Livingston (1992) rigorously document that the difference is quite small. Based on empiri-. cal evidence they examine, the empirical difference between UEH and LEH is typically less than a basis point when using monthly rates..

In summary, with continuous compounding, if LEH holds for all future time periods, then UEH also holds. This is not true with discrete compounding. Thus, any empirical differences found when testing these two hypotheses relates solely to compounding issues. For completeness, we briefly review other hypotheses of the term structure of interest rates. Remember interest rates are at the very heart of almost all financial analysis, hence, a thorough understanding of the different explanations of interest rates of varying maturities is important.
