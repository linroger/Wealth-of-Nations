---
tags:
  - black_scholes
  - derivative_pricing
  - european_option
  - pde
  - risk_neutral
aliases:
  - BS PDE
  - Black-Scholes PDE
  - Option Pricing
key_concepts:
  - Black-Scholes closed-form solutions
  - Deterministic partial differential equation
  - European option pricing
  - No-arbitrage replication portfolio
  - Risk-neutral valuation
---
# Black–Scholes PDE  

# Aims  

• To show how a no-arbitrage ‘replication portfolio’ can be constructed from stocks and options which results in a deterministic partial diferential equation (PDE) for the dynamics of an option price.   
• Solving this PDE for a European option gives the Black–Scholes closed-form solutions for call and put premia.   
• To show how European options can be priced by solving the Black–Sholes PDE numerically, using fnite diference methods.  

We show how a stochastic diferential equation (SDE) for $s$ and for the option premium $f(S,t)$ , can be ‘combined’ to give a purely deterministic partial diferential equation (PDE) for the option premium $f(S,t)$ – this is the ‘Black–Scholes PDE’. This PDE can be solved (by various methods) to give an analytic solution for European option prices – this is the famous Black–Scholes–Merton closed-form solution for call (or put) premia.  

Then we show how fnite diference methods can be used to solve the PDE numerically and provide an estimate of call and put premia. After completing this chapter, the reader should have a good basic knowledge of the continuous time approach and feel confdent in consulting more advanced texts in this area.  

# 48.1 RISK-NEUTRAL VALUATION AND BLACK–SCHOLES PDE  

In this section our aim is to show how a derivative’s price can be replicated using stocks and bonds, which eliminates any uncertainty represented by the stochastic variable, $d z=\varepsilon{\sqrt{d t}}$ .  

This results in a partial diferential equation (PDE) for the price of the derivative which is deterministic and can be interpreted in terms of risk-neutral valuation. This Black–Scholes PDE can be solved analytically for European call and put premia.  

# 48.1.1 Black–Scholes PDE  

Below we outline the steps needed to derive and solve the Black–Scholes PDE for a European option (on a non-dividend paying stock) – further details are in Appendix 48. Assume $s$ follows a GBM:  

$$
d S=\mu S d t+\sigma S d z
$$  

The price $B$ of a risk-free (zero-coupon) bond with a constant interest rate follows the process:  

$$
d B=r B d t
$$  

The price of a derivative security with underlying asset $s$ is denoted $f(S,t)$ . Ito’s lemma allows us to obtain a SDE for $f(S,t)$ which also depends on the uncertainty represented by $d z$ . From Ito’s lemma using $a=\mu S$ and $b=\sigma S$ , the dynamics of the derivative’s price is (see Chapter 47):  

$$
d f=\left[\begin{array}{c}{{\displaystyle{\frac{\partial f}{\partial t}}+\frac{\partial f}{\partial S}(\mu S)+\frac{1}{2}\frac{\partial^{2}f}{\partial S^{2}}(\sigma S)^{2}}}\end{array}\right]d t+\frac{\partial f}{\partial S}(\sigma S)d z
$$  

The SDE for the stock price and the derivatives price both depend on the same source of uncertainty, $d z$ . Over a small interval of time, portfolio-A consisting of $N_{S}=(\partial f/\partial S)=$ $\Delta$ -stocks and holdings of bonds, can be made to replicate the payof from the derivative security. The resulting equation (see Appendix 48) for the change in price of the derivative security does not depend on $d z$ and is deterministic. This equation is known as the Black–Scholes PDE:  

$$
\left[{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}(r S)+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}\right]=r f(S,t)
$$  

In Equation (48.4) the term in square brackets is similar to that in (48.3) but $\mu$ has been replaced by $r$ . Therefore the solution to (48.4) for the option price does not depend on $\mu$ – this is risk-neutral valuation (RNV), which is a consequence of no-arbitrage possibilities. When a stock pays dividends at a rate $\delta$ the Black–Scholes PDE is:  

$$
{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}(r-\delta)S+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}=r f(S,t)
$$  

The Black–Scholes PDE applies to any derivative security whose payof depends on one underlying asset (and time). It therefore holds for plain vanilla European calls and puts, American options, and exotic options such as standard barrier options and lookback options. Sometimes the PDE (together with the boundary conditions for the option) results in a closed-form solution for the options price but if this is not possible, the PDE can be solved using fnite diference methods.  

Complex algebra is required to obtain the closed-form solution to (48.5) for the Black–Scholes call (or put) premium on a European option. Here we simply note that the solution to (48.5) requires specifc boundary conditions. For example, for European calls and puts these are:  

$$
f(S,T)=\operatorname*{max}(S_{T}-K,0)
$$  

$$
{\mathrm{Put:~}}f(\infty,t)=0\quad{\mathrm{and}}\quad f(S,T)=\operatorname*{max}(K-S_{T},0)
$$  

These boundary conditions when used with the PDE give the Black–Scholes closed-form solutions for European option prices:  

$$
\begin{array}{l}{{C=S~N(d_{1})-K~e^{-r(T-t)}~N(d_{2})}}\\ {{P=K e^{-r(T-t)}N(-d_{2})-S~N(-d_{1})}}\\ {{d_{1}=\displaystyle\frac{\ln(S/K)+(r+\sigma^{2}/2)(T-t)}{\sigma\sqrt{(T-t)}}\qquadd_{2}=d_{1}-\sigma\sqrt{(T-t)}}}\end{array}
$$  

There are several solution methods available to solve the Black–Scholes PDE. In one method you take the Black–Scholes PDE (48.4) and transform it into a simpler PDE known (in physics) as the ‘heat equation’. (So called, because it explains the difusion of heat through a metal bar with a heat source at one end.) The solution to the heat equation then gives the Black–Scholes formulas for European call and put premia.  

Another method to solve for the option price involves integration and we outline the steps below to obtain the Black–Scholes call premium. Assume $\mathrm{lnS}_{T}\sim N(\eta,\sigma^{2}T)$ where $\eta=\ln S+$ $(r-\sigma^{2}/2)T$ and the density function for ${\bf S}_{T}$ is:  

$$
g(S_{T})={\frac{1}{S_{T}\sigma\sqrt{2\pi T}}}\exp\left[-{\frac{1}{2}}\Bigg({\frac{\ln S_{T}-\eta}{\sigma\sqrt{T}}}\Bigg)^{2}\right]
$$  

The call premium under risk-neutral pricing can written in terms of conditional expectations:  

$$
C=e^{-r T}\widehat{E}(S_{T}\mathrm{x}I n d)-K e^{-r T}~p r o b(S_{T}>K)
$$  

where is an indicator function, that takes the value 1 if $S_{T}>K$ and zero otherwise. The frst and second terms in (48.9) can be written:  

$$
\begin{array}{l}{{\displaystyle{\frac{e^{-r T}~S_{T}}{\sigma\sqrt{2\pi T}}\int_{K}^{\infty}g(S_{T})d S_{T}}}}\\ {{\displaystyle{\frac{1}{\sigma\sqrt{2\pi T}}\int_{\ln K}^{\infty}\exp\left[-{\frac{1}{2}}{\left(\frac{\ln S_{T}-\eta}{\sigma\sqrt{T}}\right)^{2}}\right]~d(\ln S_{T})}}}\end{array}
$$  

The integrals in (48.10) are not straightforward to evaluate but they result in the terms $S\ N(d_{1})$ and $K e^{-r T}N(d_{2})$ which implies $C=S\ N(d_{1})-K e^{-r T}N(d_{2})$ . The route to obtaining the Black–Scholes option pricing formula was a rather tortuous one (Finance Blog 48.1) – see Sudaram and Das (2015).  

# Finance Blog 48.1 Particle Finance, PDE (Pretty Damn Easy?)  

The mathematics used to explain option prices has led to the subject area being dubbed ‘particle fnance’ because much of the continuous time mathematics was initially used to explain physical phenomena. It all started in 1828 when Mr Robert Brown published a paper on his observations of pollen grains suspended in water. He noticed that the pollen grains were in continuous random motion. The puzzle was that the individual random molecules in the water seemed too small, to move ‘the large’ grains of pollen. The explanation lay in the mathematics of what later became known as Brownian motion.  

In a Brownian motion, the speed of ‘molecules’ is normally distributed and hence symmetric. One might expect the pollen grains to remain in the same position as they are ‘hit’ with equal probability from the right then the left. However, if a set of unusually high velocity molecules (i.e. from the tail of the normal distribution) hit the particle, the pollen will move in one direction. Since the motion of the molecules is normally distributed, the next few ‘hits’ are likely to be small and random so the pollen stays around its new position.  

Around 1900, it was a PhD student of the French mathematician Poincaré called Louis Bachelier, who frst used Brownian motion to explain random movements in stock prices. Mathematically, the difculty with Brownian motion is that the path of the pollen grains is described by a zigzag path which is discontinuous (even as $d t\rightarrow0\mathrm{\dot{\Omega}}$ ). In contrast, normal calculus assumes the function to be diferentiated, is everywhere continuous.  

It was Einstein in 1905 who eventually unravelled the mathematics of the problem of why the pollen grains move randomly. This ‘difusion process’ as it became known, can also explain why smoke particles from a cigarette gradually fan out in all directions (i.e. positive drift). Hence it provides an explanation of why ‘smoke gets in your eyes’ even if you are standing at the other end of a long room from a smoker.  

It was Kiyoshi Ito in 1951 who took the mathematics of difusion processes further, since he established the ‘rules of diferentiation’ for stochastic variables. This enabled Black, Scholes, and Merton in the early 1970s to derive the SDE for an option, given the underlying asset (e.g. stock price) followed a Brownian motion. It was then possible to combine the SDE for the option and the SDE for the underlying asset, to create a risk-free portfolio which resulted in a deterministic PDE for the option premium. Given the PDE for the option price, there was a set of standard solution methods already in use in the physical sciences (i.e. ‘heat equation’), to provide a closed-form solution for European option premia.  

Early studies of the behaviour of ‘particles’ by physicists considerably helped in solving the option pricing problem. Other mathematical theorems from the physical sciences have also been used in continuous time fnance. For example, the Feynman-Kac formula, due in part to the Nobel prize winning physicist Richard Feynman, and also the mathematical theorem of Girsanov, are both used in solving option pricing problems.  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

Although Black–Scholes was a major breakthrough, it is not always the case that a closed-form solution for the PDE is possible. What happens then? First, it is often possible to obtain a numerical solution to the Black–Scholes PDE (e.g. using fnite diference methods). Alternatively we can use other numerical methods such as Monte Carlo simulation or the BOPM (under RNV) to price an option.  

48.1.2 Does a Forward Contract Obey the Black–Scholes PDE?  

The price of any derivative security $f(S,t)$ should satisfy the Black–Scholes PDE. We can illustrate this by considering a forward contract on a (non-dividend paying) stock. Using a no-arbitrage approach, we established that the value of a forward contract $f$ at time $t$ is:  

$$
f=S-K e^{-r(T-t)}
$$  

where $K=$ delivery price $\l=$ price $F_{0}$ established at $t=0$ ) and $T-t=$ time to maturity. Does the above expression satisfy the Black–Scholes PDE? We have:  

$$
\frac{\partial f}{\partial t}=-r K e^{-r(T-t)}\qquad\frac{\partial f}{\partial S}=1\qquad\frac{\partial^{2}f}{\partial S^{2}}=0
$$  

Substituting the above equations in the PDE (48.4):  

$$
r\ [-K e^{-r(T-t)}+S]=r f
$$  

And using (48.11) in (48.13) we see that forward price satisfes the Black–Scholes PDE.1  

# 48.2 FINITE DIFFERENCE METHODS  

Finite diference methods provide an approximation to the continuous time PDE for the derivatives price, which can then be solved numerically. Consider the premium $f(S,t)$ on a European put option on a (dividend paying) stock. The Black–Scholes PDE is:  

$$
\frac{\partial f}{\partial t}+(r-\delta)S\ \frac{\partial f}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}f}{\partial S^{2}}-r\ f=0
$$  

The explicit fnite diference method approximates the above PDE and gives a set of equations that can be solved numerically for the option premium $f$ . To solve (48.14) we require some initial known values on the edges of the grid and these are given by the boundary conditions for the value of the put (e.g. the payof at maturity, or when the stock price is zero). To illustrate the method consider the grid in Figure 48.1 which has time diferences of $\Delta t$ along the horizontal axis and stock price changes of $\Delta S$ on the vertical axis.  

Each node on the grid will come to represent the option premium $f(S,t)=f_{i,j}$ where the index- $i$ represents a particular time (x-axis) and the index- $j$ represents the value of $s$ (y-axis), hence:  

$$
f_{i,j}=f[i(\Delta t),\quad j(\Delta S)]
$$  

The life of the option is $T$ years. The time axis is divided into $N$ equally spaced intervals of length $\Delta t=T/N$ , so there are $N+1$ time periods:  

$$
\mathbf{\Phi}_{0,}\quad\Delta t,\quad2\Delta t,\quad3\Delta t,\quad\quad\dots\quad T
$$  

![](040072f9a4a82aa5a2486a6825ec15f216dae8186a4d8e01c3962dc36382b68b.jpg)  
FIGURE 48.1 Finite diference  

We now set the maximum value for $s$ on the grid so that the put (with a strike of $K$ ) will have virtually zero value (this is an upper boundary for $s$ ) – for example, if $K=50$ then an upper boundary might be $S_{\mathrm{max}}=100\$ . Now consider $M$ equally spaced time intervals for $s$ so that $\Delta S=S_{\mathrm{max}}/M$ so the $M+1$ stock prices in the grid are:  

One of the nodes on the (left) vertical axis of Figure 48.1 will coincide with the current stock price $S_{0}=50$ (say) and the solved value for $f_{i,j}$ at this same node will be the option premium using the fnite diference method. Now we are in a position to provide an approximation to the (diferential) terms in the PDE (48.14). In the middle of the lattice the derivative $\partial f/\partial S$ can be approximated in three diferent ways (see Figure 48.2).  

$$
\begin{array}{r l}&{\frac{\partial f}{\partial S}=\frac{f_{i,j+1}-f_{i,j}}{\Delta S}\quad\mathrm{forward~difference}}\\ &{\frac{\partial f}{\partial S}=\frac{f_{i,j}-f_{i,j-1}}{\Delta S}\quad\mathrm{backward~difference}}\\ &{\frac{\partial f}{\partial S}=\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta S}\quad\mathrm{central~difference}}\end{array}
$$  

The other derivatives are (Figure 48.3):  

![](8526d7b830a3da5cfc8fe3a604acb36ebf8aeedd2702bac94aad87ee0a0c755d.jpg)  
FIGURE 48.2 Use of grid points  

![](0375197ef70de8d7796450c108a98feb06586aa49607b42b1bdb73f272fdf2bd.jpg)  
FIGURE 48.3 Approximations for $\partial f/\partial\mathrm{S}$  

It is only the derivative $\partial f/\partial t$ that involves time. The explicit fnite diference method simplifes the solution method by assuming that $\partial f/\partial S$ and $\partial^{2}f/\partial S^{2}$ at the point $(i,j)$ on the grid are the same as at point $(i+1,j)$ so the central diference equation [16c] and equation [17a] become:  

$$
\begin{array}{r l}&{\cfrac{\partial f}{\partial S}=\cfrac{f_{i+1,j+1}-f_{i+1,j-1}}{2\Delta S}}\\ &{\cfrac{\partial^{2}f}{\partial S^{2}}=\cfrac{f_{i+1,j+1}-2f_{i+1,j-1}+f_{i+1,j}}{(\Delta S)^{2}}}\end{array}
$$  

Substituting (48.17b), (48.18a), and (48.18b) in the Black–Scholes PDE (48.14) and rearranging:  

$$
f_{i,j}=A_{j}f_{i+1,j-1}+B_{j}f_{i+1,j}+C_{j}f_{i+1,j+1}
$$  

$$
\begin{array}{l}{{A_{j}=\displaystyle\frac{1}{(1+r\Delta t)}[-(1/2)(r-\delta)j\Delta t+(1/2)\sigma^{2}j^{2}\Delta t],}}\\ {{B_{j}=\displaystyle\frac{1}{(1+r\Delta t)}[1-\sigma^{2}j^{2}\Delta t],}}\\ {{C_{j}=\displaystyle\frac{1}{(1+r\Delta t)}[(1/2)(r-\delta)j\Delta t+(1/2)\sigma^{2}j^{2}\Delta t]}}\end{array}
$$  

From (48.19) we can calculate the value of $f_{i,j}$ once we know the values of $f$ for the three nodes at time $(i+1)$ – Figure 48.2. Hence once we have the terminal conditions for the option, we solve for $f_{i,j}$ by working backwards through the grid (i.e. similar to solving the BOPM recursively). This is known as the explicit fnite diference method. We know the value of the put for all nodes along the right boundary is max $(K-S_{\mathrm{T}},0)$ , the value along the bottom boundary $\begin{array}{r}{\mathbf{\nabla}S=0,}\end{array}$ is $K$ and along the top boundary (i.e. $S_{\mathrm{max}}=100\AA$ ) the value of the put is zero.  

Value of put at time $_{T}$  

$$
f_{N,j}=\operatorname*{max}(K-j\Delta S,0)\quad j=0,1,2,\dots,M
$$  

Value of put when $S=0$  

$$
f_{i,0}=K\qquadi=0,1,2,\ldots,N
$$  

Value of put when $S\to\infty(S=S_{\mathrm{max}})$  

$$
f_{i,M}=0\qquadi=0,1,2,\ldots,N
$$  

Equation (48.19) can then be used to determine the option premium $f_{i,j}=f(i\Delta t,j\Delta S)$ at all points along the left hand edge of the grid, by working backwards from $T$ . The value of $f_{i,j}$ which corresponds to the same node as the current stock price is the solution for the option premium.  

The main problem with the explicit fnite diference method is that it may not converge. There are a wide variety of other numerical methods available (e.g. implicit fnite diference method, Crank-Nicholson, Hopscotch etc.) which can overcome such problems (see Hull 2018).  

Pricing an American put option is easily incorporated into the explicit fnite diference method. Each time we calculate the grid value $f_{i,j}$ we check to see if $f_{i,j}<K-S=K-j\Delta$ [S. If $f_{i,j}<K-S$ , then we replace $f_{i,j}$ at that node with $K-S$ . We then repeat this procedure for all the nodes.  

We could also use fnite diference methods based on an approximation to the diferential equation for $d(\ln S)$ (rather than for $d S$ ) and this turns out to be slightly easier computationally. Although fnite diference methods can be used for valuing American and European options they are more difcult to use when handling path-dependent options (e.g. where the payof from the option depends on the past history of the underlying asset price). We then have to move to a ‘higher order’ problem since we have another state variable (e.g. the average value of the underlying for an Asian option). We therefore have to index the option value $f_{i,j}^{k}$ where $k=\mathrm{new}$ state variable. It is also the case that some fnite diference methods are unstable and sensitive to rounding errors in the computational procedure. Because of these difculties it is worth noting that analytic approximations for some options’ prices are often available (e.g. for American options, Asian average price options).  

# 48.3 SUMMARY  

• The stochastic process for the underlying stock $s$ and for the option premium $f(S,t)$ have a common stochastic term $d z$ , which can be eliminated by using delta hedging. This results in the deterministic Black–Scholes PDE for the option premium. The PDE depends on the risk-free rate but is independent of the actual growth rate of the stock price, $\mu$ – this is risk-neutral valuation.   
• In some cases the Black–Scholes PDE can be solved to give a closed-form solution for the option premium (e.g. for several types of European calls and puts).   
• The Black–Scholes PDE can often be solved using numerical methods (e.g. fnite diference methods). The procedure is similar to that used in the BOPM in that the PDE is initially ‘anchored’ by the boundary conditions implicit in the option contract and then the PDE is solved recursively.   
• Generally speaking, numerical techniques to solve the Black–Scholes PDE for many European options is usually accurate and speedy, even if the model involves more than three variables or ‘dimensions’ (e.g. time and two underlying stochastic variables $S_{1}$ and $S_{2}\mathrm{\backslash}$ ). When the dimension of the problem is greater than three, then MCS tends to be a more efcient method of pricing a European option.  

# APPENDIX 48: DERIVATION OF BLACK–SCHOLES PDE  

We derive the Black–Scholes PDE for the derivative security $f(S,t)$ (on a stock which pays no dividends), using two alternative replication portfolios, over short intervals of time. The analysis closely follows that used in earlier chapters to price options using the BOPM. Here we simply repeat that analysis in a continuous time framework.  

Case A: Replication using stocks and (zero coupon) bonds  

We replicate the price dynamics of the derivative security (e.g. call or put) using stocks and zero-coupon bonds (risk-free asset). Assume the stock price follows a GBM and the bond price is deterministic:  

$$
\begin{array}{c}{d S=\mu S d t+\sigma S d z}\\ {}\\ {d B=r B d t}\end{array}
$$  

From Ito’s lemma, the price of the derivative security $f(S,t)$ follows the SDE:  

$$
d f=\left[{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}(\mu S)+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}\right]d t+{\frac{\partial f}{\partial S}}(\sigma S)d z
$$  

In our replication portfolio we hold $N_{S}$ stocks and $N_{B}$ bonds. The value of the replication portfolio $V$ is set equal to the value of the derivative security (at any time $t$ ):  

$$
V=N_{S}S+N_{B}B=f(S,t)
$$  

Hence the number of bonds held is:  

$$
N_{B}={\frac{1}{B}}\left[f(S,t)-N_{S}S\right]
$$  

The instantaneous change in the value of the replication portfolio is:  

$$
d V=N_{S}d S+N_{B}d B
$$  

Substituting from (48.A.1) and (48.A.2) in (48.A.6) gives:  

$$
d V=N_{S}(\mu S d t+\sigma S d z)+N_{B}r\textit{B}d t
$$  

We require the change in value of the replication portfolio to equal the change in value of the derivative itself:  

$$
d V=d f
$$  

Equating the coefcients on $d z$ in Equation (48.A.7) and (48.A.3) implies:  

$$
N_{S}=\partial f/\partial S\equiv\Delta
$$  

Thus the number of stocks to hold at time $t$ equals the option’s delta, $\Delta=\partial f/\partial S$ . From Equations (48.A.5) and (48.A.9):  

$$
N_{B}=\frac{1}{B}\left[f(S,t)-\frac{\partial f}{\partial S}S\right]
$$  

It remains to equate the coefcients on . Substituting for $N_{B}$ in (48.A.7), using $N_{S}=\partial f/\partial S$ and then equating with (48.A.3) for terms in $d t$ gives:  

$$
{\frac{\partial f}{\partial S}}\mu\ S+\left[{\frac{1}{B}}f(S,t)-{\frac{\partial f}{\partial S}}S\right]r B=\left[{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}\mu\ S+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}\right]
$$  

Rearranging (48.A.11) we have the Black–Scholes PDE for the derivative security $f(S,t)$ (on a stock which pays no dividends):  

$$
{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}r S+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}=r f(S,t)
$$  

The PDE equation (48.A.12a) is deterministic and independent of $\mu$ the growth rate of the stock price, so the option price does not depend on $\mu$ . For a stock which pays dividends, the growth of the stock price (in a risk-neutral world) is not equal to $r$ but to $r-\delta$ , where $\delta$ is the growth rate of dividends, hence the PDE becomes:  

$$
{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}(r-\delta)S+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}=r f(S,t)
$$  

# Case B: Risk-free Portfolio-B (Stock Pays No Dividends)  

The Black–Scholes PDE can be derived in a simpler fashion if we assume we already know how to construct a risk-free portfolio. Assume the risk-free Portfolio-B consists of a long position in $N_{S}$ stocks (where $N_{S}=\partial f/\partial S=\Delta)$ and a short position in the derivative security $(N_{f}=-1)$ ) with current price $f$ . The value of portfolio-B is:  

$$
\begin{array}{c}{{V=-f+\displaystyle\left(\frac{\partial f}{\partial S}\right)S}}\\ {{{}}}\\ {{d V=-d f+\displaystyle\frac{\partial f}{\partial S}d S}}\end{array}
$$  

Substitute in (48.A.14) for $d S$ from Equation (48.A.1) and for $d f$ from Ito’s equation (48.A.3). Crucially, the term in $d z$ cancels out and we are left with:  

$$
d V=\left[-{\frac{\partial f}{\partial t}}-{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}\right]d t
$$  

The change in value of portfolio-B is deterministic so risk-free arbitrage profts are possible unless portfolio-B earns the risk-free rate:  

$$
d V=V r d t
$$  

Substituting from Equation (48.A.15) and (48.A.13) in (48.A.16):  

$$
\left[-\ \frac{\partial f}{\partial t}-\frac{1}{2}\ \frac{\partial^{2}f}{\partial S^{2}}\ (\sigma S)^{2}\right]d t=\left[-f+\frac{\partial f}{\partial S}S\right]r d t
$$  

A simple rearrangement of (48.A.17) gives the Black–Scholes PDE, Equation (48.A.12).  

# Dividend Paying Stock  

If we hold $N_{s}=\partial f/\partial S$ stocks which pay a continuous dividend at the (proportionate) rate $\delta$ , then the (dollar) dividend paid out over time interval $d t$ is $\delta(\partial f/\partial S)S d t$ , which needs to  

be added to the right hand side of (48.A.15). The rest of the analysis is unchanged and the Black–Scholes PDE for an option on a dividend paying stock is:  

$$
{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial S}}(r-\delta)S+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}(\sigma S)^{2}=r f(S,t)
$$  

# EXERCISES  

# Question 1  

Use Ito’s lemma to shown that if $d S/S$ follows a GBM with drift rate $\mu$ and variance, $\sigma$ then the futures price $F=f(S,t)=S e^{r(T-t)}$ ∫fo≡llows a GBM with drift rate $\mu-r$ (where $r$ is th(e risk-free rate) and variance, $\sigma^{2}$ .  

# Question 2  

If the change in the stock price follows a GBM, $d S=\mu S d t+\sigma S d z$ , use Ito’s lemma to show that $f=S^{2}$ follows $d f=(2\mu+\sigma^{2})f~d t+2\sigma f~d z$ .  

# Question 3  

What assumptions are made in moving from an SDE for the option price to the Black– Scholes PDE?  

# Question 4  

What is a partial diferential equation (PDE)? What is the key diference between a SDE and a PDE?  

# Question 5  

What are the key strengths and weaknesses in calculating European option premia using fnite diference methods? What role is played by boundary conditions?  