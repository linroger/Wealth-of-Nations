---
title: Appendix 17. A Calculation of Optimal Time to Drill an Oil Well
tags:
  - investment_decision
  - investment_trigger
  - oil_well_drilling
  - optimal_solution
  - shutdown_restart
aliases:
  - Oil Well Drilling
  - Optimal Drilling Time
key_concepts:
  - Investment trigger value
  - L'Hospital's rule application
  - Maximize expression
  - Optimal investment deferral
  - Single shutdown restart
---

# Appendix 17. A Calculation of Optimal Time to Drill an Oil Well
## Single-Barrel Solution

It is optimal to defer investing as long as
$$\left (\frac{1}{1+r}\right)^h\left[S\left (\frac{1+r}{1+\delta}\right)^h-X\right]>S-X$$
Which can be rewritten as
$$\frac{S}{X}<\frac{1-\left (\frac{1}{1+r}\right)^h}{1-\left (\frac{1}{1+\delta}\right)^h}$$
The optimal solution entails taking the limit as $h\to 0$ Using L'Hospital’s rule,  we can show that $\lim_{h\to\infty}\frac{1-(1+r)^{-k}}{h}=\ln (1+r)$ Hence
$$\frac{1-\left (\frac{1}{1+r}\right)^h}{1-\left (\frac{1}{1+\delta}\right)^h}\to\frac{\ln (1+r)}{\ln (1+\delta)}$$
Thus,  we defer investing as long as
$$\frac{S}{X}<\frac{\ln (1+r)}{\ln (1+\delta)}$$
In the text example this calculation gives $\$16.918$

### THE SOLUTION WITH SHUTTING DOWN AND RESTARTING

In this appendix we explain the solution of two problems: investing and operating (1) when it is possible to shut down once and restart once,  permanently,  and (2) when it is possible tc shut down and restart an infinite number of times. The solutions here can be implemented numerically First,  we develop some notation. Let $V_{U}(S,      m,      n;*)$ represent the value of an undeveloped reserve and $V_{O}(S,      m,      n;*)$ and $V_{C}(S,      m,      n;*)$ the value of developed operating and developed closed reserves,  where it is possible to shut down m times and restart n times The 祚 denotes a dependence on the prices at which shutting and restarting is optimal. We will be using the formulas given by equations (12.22) and (12.23) for the value of $\$1$ when $S$ reaches a barrier.

#### Single Shutdown and Restart

Prior to the final permanent restart at $S^{*}$ ,  we have

$$V_C (S,      0,      1; S^*)=\left (\frac{S^*}{\delta}-\frac{c}{r}-k_r\right)\left (\frac{S}{S^*}\right)^{h_1}$$

We choose $S^{*}$ to maximize this expression.

While operating,  prior to the shutdown at $S_{*}<S$ ,  we have

(17.16)
$$V_O (S,      1,      1; S_*,      S^*)=\frac{S}{\delta}-\frac{c}{r}+\left[\frac{c}{r}-k_s-\frac{S_*}{\delta}+V_C (S_*,      0,      1; S^*)\right]\left (\frac{S}{S_*}\right)^{h_2}$$

We choose $S_{*}$ to maximize this expression,  taking $S^{*}$ as determined by equation (17.15) Finally,  prior to the original investment decision,  which occurs at $\bar{S}>S$ ,  the value of

The well is

$$V_U (S,      1,      1; S_*,      S^*)=\begin{bmatrix}V_0 (\bar{S},      1,      1,      S_*,      S^*)-I\end{bmatrix}\left (\frac{S}{\bar{S}}\right)^{h_1}$$

We find the $\bar{S}$ that maximizes this equation,  taking $S_{*}$ and $S^{*}$ as given,  determined by maximizing equations (17.15) and (17.16)

#### Infinite Shutdown and Restart

The solution here is conceptually like that in the single shutdown and restart case,  except that when we restart,  we receive the option to shut down. Thus,  when the well is shut,  we have
$$V_C (S,      \infty,      \infty; S_*,      S^*)=\begin{bmatrix}-k_r+V_O (S^*,      \infty,      \infty; S_*,      S^*)\end{bmatrix}\left (\frac{S}{S^*}\right)^{h_1}$$

While operating,  prior to the shutdown at $S>S_{*}$ ,  we have
$$\begin{aligned}
V_{O}(S,      \infty,      \infty; S_{*},      S^{*})& =\frac{S}{\delta}-\frac{c}{r} \\
&+\left[\frac{c}{r}-k_{s}-\frac{S_{*}}{\delta}+V_{C}(S_{*},      \infty,      \infty; S_{*},      S^{*})\right]\left (\frac{S}{S_{*}}\right)^{h_{2}}
\end{aligned}$$
Note that $V_{C}$ and $V_{0}$ are defined in terms of each other. We can substitute equation (17.17) into equation (17.18) and set $S=S_{*}$ . This gives
$$V_O (S^*,      \infty,      \infty; S_*,      S^*)=\frac{S^*/\delta-c/r-k_r (S_*/S^*)^{h_1}+(c/r-S_*/\delta-k_s)\times (S^*/S_*)^{h_2}}{1-(S_*/S^*)^{h_1}\times (S^*/S_*)^{h_2}}$$
Given starting values of $S^{*}$ and $S_{*}$ ,      we can evaluate equation (17.19),      substituting the answer into equation (17.17) to obtain an estimate of $V_{C}(S,      \infty,      \infty; S_{*},      S^{*})$ .Then we can maximize equation (17.17) with respect to $S^{*}$ and equation (17.18) with respect to $S_{*}$ . This gives us new estimates of $V_{C}(S_{*})$ and $V_{0}(S^{*})$ Iterate until convergence
Once we have computed $S^{*},      S_{*}$ ,      and $V_{C}(S_{*})$ ,      the value of the well is
$$V_{U}(S,      \infty,      \infty; S_{*},      S^{*})=\left[\frac{\overline{S}}{\delta}-\frac{c}{r}-I+V_{C}(S_{*},      \infty,      \infty; S_{*},      S^{*})\left (\frac{\overline{S}}{S_{*}}\right)^{h_{2}}\right]\left (\frac{S}{\overline{S}}\right)^{h_{1}}$$
We maximize this with respect to $\overline{S}$ to find the investment trigger and value of the well
