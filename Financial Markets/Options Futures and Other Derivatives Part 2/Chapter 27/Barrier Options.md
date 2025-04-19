---
tags:
  - adaptive_mesh_model
  - barrier_options
  - numerical_methods
  - option_pricing
  - trinomial_tree
aliases:
  - Barrier Option Valuation
  - Option Pricing Techniques
  - Up-and-Out Option
key_concepts:
  - Adaptive mesh model
  - Barrier option valuation
  - Binomial and trinomial trees
  - Inner and outer barriers
  - Nodes on the barrier
---

# 27.6 BARRIER OPTIONS  

Chapter 26 presented analytic results for standard barrier options. This section considers numerical procedures that can be used for barrier options when there are no analytic results.  

In principle, many barrier options can be valued using the binomial and trinomial. trees discussed in Chapter 21. Consider an up-and-out option. A simple approach is to. value this in the same way as a regular option except that, when a node above the barrier is encountered, the value of the option is set equal to zero..  

Trinomial trees work better than binomial trees, but even for them convergence is. very slow when the simple approach is used. A large number of time steps are required to obtain a reasonably accurate result. The reason for this is that the barrier being assumed by the tree is different from the true barrier.24 Define the inner barrier as the. barrier formed by nodes just on the inside of the true barrier (i.e., closer to the center of the tree) and the outer barrier as the barrier formed by nodes just outside the true barrier (i.e., farther away from the center of the tree). Figure 27.4 shows the inner and outer barrier for a trinomial tree on the assumption that the true barrier is horizontal. The usual tree calculations implicitly assume that the outer barrier is the true barrier because the barrier conditions are first used at nodes on this barrier. When the time step. is $\Delta t$ , the vertical spacing between the nodes is of order $\sqrt{\Delta t}.$ This means that errors created by the difference between the true barrier and the outer barrier also tend to be of order $\dot{\sqrt{\Delta t}}$  

One approach to overcoming this problem is to:  

1. Calculate the price of the derivative on the assumption that the inner barrier is the true barrier.   
2. Calculate the value of the derivative on the assumption that the outer barrier is the true barrier.   
3. Interpolate between the two prices.  

Another approach is to ensure that nodes lie on the barrier. Suppose that the initial stock price is $S_{0}$ and that the barrier is at $H.$ In a trinomial tree, there are three possible.  

![](16bdd77e093809f71785fbf21126df1b1130a439f018a96ee49440561e191cf8.jpg)  
Figure 27.4 Barriers assumed by trinomial trees.  

movements in the asset's price at each node: up by a proportional amount $u$ ; stay the same; and down by a proportional amount $d$ , where $d=1/u$ . We can always choose $u$ so that nodes lie on the barrier. The condition that must be satisfied by $u$ is  

$$
H=S_{0}u^{N}
$$  

or  

$$
\ln H=\ln S_{0}+N\ln u
$$  

for some positive or negative $N$  

When discussing trinomial trees in Section 21.4, the value suggested for $u$ was $e^{\sigma{\sqrt{3\Delta t}}}$ so that ln $u=\sigma\sqrt{3\Delta t}.$ In the situation considered here, a good rule is to choose ln $u$ as close as possible to this value, consistent with the condition given above. This means that  

$$
\ln u=\frac{\ln H-\ln S_{0}}{N}
$$  

where  

$$
N=\mathrm{int}\biggl[{\frac{\ln H-\ln S_{0}}{\sigma{\sqrt{3\Delta t}}}}+0.5\biggr]
$$  

and $\operatorname{int}(x)$ is the integral part of $x$  

This leads to a tree of the form shown in Figure 27.5. The probabilities $p_{u},p_{m}$ and $p_{d}$ on the upper, middle, and lower branches of the tree are chosen to match the first  

![](1d0d9ff515bea1c2547396ec70e505b52b06abf5e30d52dab9beb4949938e880.jpg)  
Figure 27.5 Tree with nodes lying on barrier.  

two moments of the return, so that  

$$
p_{d}=-\frac{(r-q-\sigma^{2}/2)\Delta t}{2\ln u}+\frac{\sigma^{2}\Delta t}{2(\ln u)^{2}},p_{m}=1-\frac{\sigma^{2}\Delta t}{(\ln u)^{2}},p_{u}=\frac{(r-q-\sigma^{2}/2)\Delta t}{2\ln u}+\frac{\sigma^{2}\Delta t}{2(\ln u)^{2}}\ln(\frac{\sigma^{2}}{u}+\frac{\sigma^{2}\Delta t}{2(\ln u)^{2}})\Delta t
$$  

The methods presented so far work reasonably well when the initial asset price is not close to the barrier. When the initial asset price is close to a barrier, the adaptive mesh model, which was introduced in Section 21.4, can be used.25 The idea behind the model. is that computational efficiency can be improved by grafting a fine tree onto a coarse tree to achieve a more detailed modeling of the asset price in the regions of the tree. where it is needed most. To value a barrier option, it is computationally efficient to have. a fine tree close to barriers with nodes on the barriers..  
