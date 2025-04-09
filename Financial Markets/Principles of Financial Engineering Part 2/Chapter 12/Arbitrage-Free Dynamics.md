# 12.6 ARBITRAGE-FREE DYNAMICS  

The last result that we derive from the fundamental theorem of asset pricing is a combination of all the corollaries discussed thus far. The synthetic probabilities and the Martingale property that we obtained earlier can be used to derive several arbitrage-free dynamics for an asset price. These arbitrage-free dynamics play an important role in pricing situations where an exact synthetic cannot be created, either due to differences in nonlinearities or due to a lack of liquid constituent assets. In fact, most of the pricing models will proceed along the lines of first obtaining arbitrage-free dynamics, and then either simulating paths from this or obtaining the implied binomial or trinomial trees. PDE methods also use these arbitrage-free dynamics.  

# 12.6.1 ARBITRAGE-FREE SDEs  

In this section, we briefly discuss the use of stochastic differential equations (SDEs) as a tool in financial engineering and then show how the fundamental theorem helps in specifying explicit SDEs that can be used in pricing and hedging in practice.2' Consider an asset price $S_{t}.$ Suppose we divide the time period $[t,T]$ into small intervals of equal size $\Delta$ . For each time $t+i\Delta$ $i=1,...,n$ we observe a different $S_{t+i\Delta}$ $S_{t+\Delta}-S_{t}$ is the change in asset price at time $t$ Choose a working probability from all available synthetic probabilities, and denote it by $P^{*}$  

Then, we can always calculate the expected value of this change under this probability. In the case of $P^{*}=\tilde{P}$ , we obtain the risk-neutral expected net return by.  

$$
E_{t}^{\tilde{P}}[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta
$$  

Next, note that the following statement is always true:  

Now we can use the probability switching method and exploit the Martingale property. For example, for the risk-neutral probability we have.  

$$
[S_{t+\Delta}-S_{t}]E_{t}^{\tilde{P}}[S_{t+\Delta}-S_{t}]+\in_{t}
$$  

where $\in_{t}$ represents a random variable with zero expectation under $\tilde{P}$ Replace from Eq. (12.78  

$$
[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta+\in_{t}
$$  

Now the error term $\in_{t}$ can be written in the equivalent form  

$$
\in_{t}=\sigma(S_{t})S_{t}\Delta W_{t}
$$  

here $\Delta W_{t}$ is a Wiener process increment with variance equal to $\Delta$  

Thus, the arbitrage-free dynamics under the $\tilde{P}$ measure can be written as  

$$
[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta+\sigma(S_{t})S_{t}\Delta W_{t}
$$  

Letting $\Delta\to0$ , this equation becomes an SDE, that represents the arbitrage-free dynamics under the synthetic probability, $\tilde{P}$ , during an infinitesimally short period ${\mathrm{d}}t$ Symbolically, the SDE is written as  

$$
\mathrm{d}S_{t}=r_{t}S_{t}\mathrm{d}t+\sigma(S_{t})S_{t}\mathrm{d}W_{t}
$$  

$\mathrm{d}S_{t}$ and $\mathrm{d}W_{t}$ represent changes in the relevant variables during an infinitesimal time interval. Given. the values for the (percentage) volatility parameter, $\sigma(S_{t})$ , these equations can be used to generate arbitrage-free trajectories for $S_{t}$ . We deal with these in the next chapter. Note a major advantage of using the risk-neutral probability. The drift term, that is to say the first term on the right-hand side, is known. At this point, we consider a second way of obtaining arbitrage-free paths.  

# 12.6.2 TREE MODELS  

We will see another major application of the Martingale property. We develop the notion of binomial (trinomial) trees introduced in Chapter 8 and obtain an alternative way of handling arbitragefree dynamics. Suppose the dynamics of $S_{t}$ can be described by a (geometric) SDE:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

where the volatility is assumed to be given by  

$$
\sigma(S_{t})=\sigma
$$  

This is the constant percentage volatility of $S_{t}$ . Also note that $r_{t}$ is set to a constant. It can be shown that this SDE can be "solved" for $S_{t}$ to obtain the relationship (0ksendal, 2010).  

$$
S_{t+\Delta}=S_{t}e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta+\sigma(W_{t+\Delta}-W_{t})}
$$  

Our purpose is to construct an approximation to the arbitrage-free dynamics of this. $S_{t}$ .We will do this by considering approximations to possible paths that. $S_{t}$ can follow between $t$ and some "expiration" date $T.$ This approximation will be such that $S_{t}$ will satisfy the Martingale property under a judiciously chosen probability. Finally, the approximation should be chosen so that as $\Delta\to0$ , the mean and the variance of the discrete approximation converge to those of the continuous time process under the relevant probability. It turns out that this can be done in many different ways. Each method may have its advantages and disadvantages. We discuss two different ways of building trees. As $\Delta\to0$ , the dynamics become those of continuous time.  

# 12.6.2.1 Case 1  

The method introduced by Cox-Ross-Rubinstein (CRR) selects the following approximation. First, the period $[t_{0},T]$ is divided into $N$ subintervals of equal length. Then, it is assumed that at each point of a path there are possible states. In the CRR case, $n=2$ and the paths become binomial. An alternative trinomial tree is shown in Figure 12.3.  

At every node $i$ of a possible path, there are only two possible states represented by the numbers $\{u_{i},d_{i}\}$ , with the (marginal) probabilities. $p$ and $(1-p)$ . The dynamics are selected as follows:.  

$$
\begin{array}{c}{{S_{i}^{u}=u_{i}S_{i-\Delta}}}\ {{{}}}\ {{S_{i}^{d}=d_{i}S_{i-\Delta}}}\end{array}
$$  

where $S_{i}$ is the shortcut notation for $S_{t+i\Delta}$  

![](images/71f6795f4620dc1bdee54dbad407a0dddf5edb9afe51cac2accebf169f04ab76.jpg)  

# FIGURE 12.3  

Trinomial tree.  
