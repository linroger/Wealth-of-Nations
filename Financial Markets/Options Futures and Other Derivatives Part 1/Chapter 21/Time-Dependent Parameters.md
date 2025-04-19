---
tags:
  - '#binomial_tree'
  - '#calculating_pi'
  - '#cox_ross_rubinstein_tree'
  - '#excel_spreadsheet'
  - '#forward_interest_rate'
  - '#monte_carlo_simulation'
  - '#nonconstant_interest_rates'
  - '#time_dependent_parameters'
  - '#volatility_modeling'
---
# 21.5 TIME-DEPENDENT PARAMETERS  

Up to now we have assumed that. $r,q,r_{f}$ and $\sigma$ are constants. In practice, they are. usually assumed to be time dependent. The values of these variables between times $t$ and t + At are assumed to be equal to their forward values.10  

To make $r$ and $q$ (or $r_{f}$ ) a function of time in a Cox-Ross-Rubinstein binomial tree, we set  

$$
a=e^{[f(t)-g(t)]\Delta t}
$$  

for nodes at time. $t$ where $f\left(t\right)$ is the forward interest rate between times $t$ and $t+\Delta t$ and $g(t)$ is the forward value of. $q$ (or $r_{f}$ ) between these times. This does not change the geometry of the tree because $u$ and $d$ do not depend on. $a$ . The probabilities on the. branches emanating from nodes at time t are:11  

$$
p=\frac{e^{[f(t)-g(t)]\Delta t}-d}{u-d}
$$  

$$
1-p=\frac{u-e^{[f(t)-g(t)]\Delta t}}{u-d}
$$  

The rest of the way that we use the tree is the same as before, except that when discounting between times $t$ and $t+\Delta t$ we use $f(t)$  

Making the volatility,. $\sigma$ , a function of time in a binomial tree is more difficult. Suppose $\sigma(t)$ is the volatility used to price an option with maturity $t.$ One approach is to make the length of each time step inversely proportional to the average variance rate during the time step. The values of $u$ and $d$ are then the same everywhere and the tree recombines. Define the $V=\sigma(T)^{2}T$ where $T$ is the life of the tree, and define $t_{i}$ as the end of the ith. time step. For N time steps, we choose t; to satisfy o(t)?t, = iV/N and set u = eVv/N with $d=1/u$ . The parameter $p$ is defined in terms of $u,d,r$ , and $q$ as for a constant. volatility. This procedure can be combined with the procedure just mentioned for dealing  

# Business Snapshot 21.1 Calculating Pi with Monte Carlo Simulation  

Suppose the sides of the square in Figure 21.13 are one unit in length. Imagine that you fire darts randomly at the square and calculate the percentage that lie in the circle. What should you find? The square has an area of 1.0 and the circle has a radius of 0.5 The area of the circle is. $\pi$ times the radius squared or. $\pi/4$ . It follows that. the proportion of darts that lie in the circle should be $\pi/4$ . We can estimate $\pi$ by multiplying the proportion that lie in the circle by 4.  

We can use an Excel spreadsheet to simulate the dart throwing as illustrated in Table 21.1. We define both cell A1 and cell B1 as. $=$ RAND().A1 and B1 are random numbers between 0 and 1 and define how far to the right and how high up the dart lands in the square in Figure 21.13. We then define cell C1 as.  

$$
=\mathrm{IF}((\mathrm{A}1-0.5)^{\widehat{\circ}}2+(\mathrm{B}1-0.5)^{\widehat{\circ}}2<0.5^{\widehat{\circ}}2,4,0)
$$  

This has the effect of setting C1 equal to 4 if the dart lies in the circle and 0 otherwise.  

Define the next 99 rows of the spreadsheet similarly to the first one. (This is a "select and drag" operation in Excel.) Define $\mathrm{C102as=AVERAGE(C1:C100)}$ and ${\mathrm{C103~as~}}{=}\mathrm{STDEV}({\mathrm{C1}}{\mathrm{:}}\mathrm{C100})$ . C102 (which is 3.04 in Table 21.1) is an estimate of $\pi$ calculated from 100 random trials. C103 is the standard deviation of our results and as we will see in Example 21.7 can be used to assess the accuracy of the estimate.. Increasing the number of trials improves accuracy-but convergence to the correct value of 3.14159 is slow.  

with nonconstant interest rates so that both interest rates and volatilities are timedependent.  
