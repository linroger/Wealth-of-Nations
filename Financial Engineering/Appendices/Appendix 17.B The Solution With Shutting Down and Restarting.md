---
tags:
  - appendix
  - investment_trigger
  - restart
  - shut_down
  - undeveloped_reserves
aliases:
  - Appendix 17B
  - Investment
  - Restarting
  - Shutting Down
key_concepts:
  - Developed operating reserves
  - Investment trigger
  - Shut down and restart
  - Undeveloped reserve value
  - Value of the well
---

# Appendix 17. B  the SOLUTION WITH SHUTTING DOWN and RESTARTING  

In this appendix we explain the solution of two problems: investing and operating (1) when it is possible to shut down once and restart once, permanently, and (2) when it is possible to shut down and restart an inﬁnite number of times. The solutions here can be implemented numerically.  

First, we develop some notation. Let    $V_{U}(S,m,n;*)$   represent the value of an undeveloped reserve and    $V_{O}(S,m,n;*)$   and    $V_{C}(S,m,n;*)$   the value of developed operating and developed closed reserves, where it is possible to shut down  m  times and restart  n  times. The  $^*$  denotes a dependence on the prices at which shutting and restarting is opt al. We will be using the formulas given by equations (12.22) and (12.23) for the value of \$1 when  $S$   reaches a barrier.  

# Single Shutdown and Restart  

Prior to the ﬁnal permanent restart at    $S^{*}$  , we have  

$$
V_{C}(S,0,1;S^{*})=\left(\frac{S^{*}}{\delta}-\frac{c}{r}-k_{r}\right)\left(\frac{S}{S^{*}}\right)^{h_{1}}
$$  

We choose    $S^{*}$  to maximize this expression.  

While operating, prior to the shutdown at  $S_{*}<S$  , we have  

$$
V_{O}(S,1,1;S_{*},S^{*})=\frac{S}{\delta}-\frac{c}{r}+\left[\frac{c}{r}-k_{s}-\frac{S_{*}}{\delta}+V_{C}(S_{*},0,1;S^{*})\right]\left(\frac{S}{S_{*}}\right)^{h_{2}}
$$  

We choose  $S_{*}$  to maximize this expression, taking    $S^{*}$  as determined by ion (17.15).  

Finally, prior to the original investment decision, which occurs at    $\bar{S}>S$  ¯ , the value of the well is  

$$
V_{U}(S,\,1,\,1;\,S_{*},\,S^{*})=\left[V_{0}(\bar{S},\,1,\,1,\,S_{*},\,S^{*})-I\right]\left({\frac{S}{\bar{S}}}\right)^{h_{1}}
$$  

We ﬁnd the    $\bar{S}$   that maximizes this equation, taking    $S_{*}$  and    $S^{*}$  as given, determined by maximizing equations (17.15) and (17.16).  

# Inﬁnite Shutdown and Restart  

The solution here is conceptually like that in the single shutdown and restart case, except that when we restart, we receive the option to shut down. Thus, when the well is shut, we have  

$$
V_{C}(S,\infty,\infty;S_{*},S^{*})=\left[-k_{r}+V_{O}(S^{*},\infty,\infty;S_{*},S^{*})\right]\left(\frac{S}{S^{*}}\right)^{h_{1}}
$$  

While operating, prior to the shutdown at    $S>S_{*}$  , we have  
$$
\begin{array}{l}{{V_{O}(S,\infty,\infty;S_{*},S^{*})=\displaystyle\frac{S}{\delta}-\frac{c}{r}}}\\ {{\displaystyle~~~~~~~~~~~~~~~~~~~~~+\left[\frac{c}{r}-k_{s}-\frac{S_{*}}{\delta}+V_{C}(S_{*},\infty,\infty;S_{*},S^{*})\right]\left(\frac{S}{S_{*}}\right)^{h_{2}}}}\end{array}
$$  

Note that    $V_{C}$   and  $V_{O}$   are deﬁned in terms of each other. We can substitute equation (17.17) into equation (17.18) and set    $S=S_{*}$  . This gives  

$$
V_{O}(S^{*},\infty,\infty;S_{*},S^{*})=\frac{S^{*}/\delta-c/r-k_{r}(S_{*}/S^{*})^{h_{1}}+(c/r-S_{*}/\delta-k_{s})\times(S^{*}/S_{*})^{h_{2}}}{1-(S_{*}/S^{*})^{h_{1}}\times(S^{*}/S_{*})^{h_{2}}}
$$  

Given starting values of  $S^{*}$  and    $S_{*}$  , we can evaluate equation (17.19), substituting the answer into equation (17.17) to obtain an timate of  $V_{C}(S,\infty,\infty;S_{*},S^{*})$  . Then we can maximize equation (17.17) with respect to  $S^{*}$  and equation (17.18) with respect to  $S_{*}$  . This gives us new estimates of    $V_{C}(S_{*})$   and    $V_{O}(S^{*})$  . Iterate until convergence.  

Once we have computed  $S^{*}$  ∗ ,  $S_{*}$  , and    $V_{C}(S_{*})$  , the value of the well is  

$$
V_{U}(S,\infty,\infty;S_{*},S^{*})=\left[{\frac{\overline{{S}}}{\delta}}-{\frac{c}{r}}-I+V_{C}(S_{*},\infty,\infty;S_{*},S^{*})\left({\frac{\overline{{S}}}{S_{*}}}\right)^{h_{2}}\right]\left({\frac{S}{\overline{{S}}}}\right)^{h_{1}}
$$  

We maximize this with respect to    $\overline{{S}}$   to ﬁnd the investment trigger and value of the well.  
