---
tags:
  - black_scholes_model
  - cppi_dynamics
  - gap_risk
  - wiener_process
  - yield_curve
aliases:
  - CPPI Model
  - Constant Proportion Portfolio Insurance
key_concepts:
  - Black-Scholes environment
  - CPPI algorithm stability
  - Gap risk from jumps
  - Stochastic differential equation
  - Yield curve movements
---

# 23.4 MODELING THE CPPI DYNAMICS  

We now obtain the equations that give the dynamics of $V_{t}$ under the typical CPPI scheme. The equations are obtained from a relatively simple setting to highlight the important aspects of the methodol-. ogy. The two points on which we focus are the following: first, we will see that from a single portfolio. point of view, CPPI algorithms may be much more stable than they appear from the outside if there. are no jumps. However, in reality there are jumps which lead to the gap risk. Second, we show that the CPPI methodology may have a more fragile structure with respect to yield curve movements than anticipated. This may be especially the case if sharp downward jumps in $S_{t}$ are correlated with a sudden steepening of the curve-exactly what happens during periods of excessive market stress.  

Let us place ourselves in a Black-Scholes-type environment, with constant interest rates $r$ and constant volatility $\sigma$ . Further, the $S_{t}$ follows the Wiener process-driven SDE,.  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}
$$  

We know from the previous discussion that the investment in risky assets is  

$$
R_{t}=\lambda C u_{t}
$$  

and that the changes in the cushion are given by  

$$
\mathrm{d}C u_{t}=\mathrm{d}(V_{t}-F_{t})
$$  

This means  

$$
\mathrm{d}C u_{t}=(V_{t}-R_{t})\frac{\mathrm{d}B_{t}}{B_{t}}+R_{t}\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}F_{t}
$$  

where $B_{t}$ is the value of the zero-coupon bond at time $t.^{6}$ In this expression, we can replace $V_{t},R_{t}$ with their respective values to obtain  

$$
\mathrm{d}C u_{t}=(C u_{t}+F_{t}-\lambda C u_{t})\frac{\mathrm{d}B_{t}}{B_{t}}+\lambda C u_{t}\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}F_{t}
$$  

But the value of the floor increases according to  

$$
\mathrm{d}F_{t}=F_{t}\frac{\mathrm{d}B_{t}}{B_{t}}
$$  

This means  

$$
\mathrm{d}C u_{t}=(1-\lambda)C u_{t}\frac{\mathrm{d}B_{t}}{B_{t}}+\lambda C u_{t}\frac{\mathrm{d}S_{t}}{S_{t}}
$$  

Substituting further,  

$$
\mathrm{d}C u_{t}=(\lambda(\mu-r)+r)C u_{t}\mathrm{d}t+\lambda\sigma c\mathrm{d}W_{t}
$$  

This is a geometric stochastic differential equation whose solution is given by  

$$
C u_{t}=C u_{t_{0}}e^{\left(\lambda(\mu-r)+r-((\lambda^{2}\sigma^{2})/2)\right)(t-t_{0})+\lambda\sigma W_{t}}
$$  

We can combine this with $F_{t_{0}}$ to get the behavior of the portfolio net asset value for all $t\in[t_{0},T]$  

$$
V_{t}=F_{t_{0}}e^{r(t-t_{0})}+C u_{t}
$$  

Using standard results from stochastic calculus, we can calculate the expected portfolio value as of time $t$  

$$
E_{t_{0}}^{P}[V_{t}]=F_{t_{0}}+\left(100-F_{t_{0}}e^{r(T-t_{0})}\right)e^{r(t-t_{0})+\lambda(\mu-r)(t-t_{0})}
$$  

Note that the probability measure we use in this expectation is the real-world probability and not the risk-adjusted measure. This is the case since the drift of the. $S_{t}$ process was taken to be the $\mu$ and not the risk-free rate $r$  

# 23.4.1 INTERPRETATION  

There are two equations in the above derivation that are very suggestive. The first relates to the dynamics of the cushion over time,  

$$
\mathrm{d}C u_{t}=(\lambda(\mu-r)+r)C u_{t}\mathrm{d}t+\lambda C u_{t}\frac{\mathrm{d}S_{t}}{S_{t}}
$$  

Note that with such a dynamic the cushion itself can never go below zero over time. In fact, suppose $C u_{t}$ becomes very small at time $t$ The first term on the right-hand side of the equation will be positive. Also, being a Wiener-driven system, $S_{t}$ cannot exhibit jumps and over infinitesimal periods must change infinitesimally. The second term on the right-hand side then shows that the changes in $S_{t}$ affect the cushion with a coefficient of $\lambda C u_{t}$ which goes to zero as $C u_{t}$ approaches zero. Under these conditions, as the cushion $C u_{t}$ goes toward zero, the ${\mathrm{d}}C u_{t}$ will go to zero as well.  

This leads to an interesting conclusion. The CPPI method will always "work" in the sense that as the market goes against the investor, the cushion will never become negative. In the worst case, the cushion will be zero which means that the risky investment is liquidated. This leaves the investor with the zero-coupon bond which matures at a value of 100. Hence, the principal is "always' protected.  

Before we continue with the implications of this result consider the second interesting equation The expected value of the portfolio was calculated as  

$$
E_{t_{0}}^{P}[V_{t}]=F_{t_{0}}+\left(100-F_{t_{0}}e^{r(T-t_{0})}\right)e^{r(t-t_{0})+\lambda(\mu-r)(t-t_{0})}
$$  

This is also very suggestive because, as long as $r<\mu$ , which means that the risky asset expected return is higher than the risk-free rate, the expected value of the portfolio can be increased indefinitely by picking higher and higher leverage factors, $\lambda$  

Thus we have reached an unrealistic result. The CPPI strategy will always work, in the sense that the investor's initial investment is always protected, while at the same time the higher the leverage the higher the expected gains. This implies picking the highest possible leverage factor that is available to the structurer. Yet, it is clear that in the real world this is not the prudent approach. This, in turn, suggests that the model we discussed above may be missing some critical features of real-world investment.  

There are at least two possibilities, the first being the limits on borrowing. There are credit limits and the leverage cannot be increased indefinitely in the real world. The second possibility is more interesting.  

In the real world, $S_{t}$ process may not follow a geometric process and may contain jump factors. If this is the case, as $C u_{t}{\rightarrow}0$ , a downward jump in $S_{t}$ can make $C u_{t}$ negative. The portfolio value will fall below the floor and the investor's initial investment is lost,  

$$
V_{t}<F_{t}
$$  

This is the gap risk. Note that, if there are such jumps in $S_{t}$ , then the presence of the leverage factor $1<\lambda$ will magnify them. The higher the $\lambda$ the higher will be the effect of a downward jump.  

# 23.4.2 HOW T0 PICK X  

The discussion involving the gap risk suggests a methodology for selecting a numerical value for the critical leverage parameter $\lambda$ The structurer would first determine an acceptable threshold for. the gap probability using the investor's risk preferences. Then, using the observed volatility and jump parameters, the structurer would work backward and determine. $\lambda$ that makes the gap probability equal to this desired amount. This could be done with Monte Carlo or with semiparametric methods as in Cont and Tankov (2009)..  

Clearly this determination of. $\lambda$ will be model dependent. A structurer would have a number of. other ways to deal with this gap risk, some of which are discussed below.  
