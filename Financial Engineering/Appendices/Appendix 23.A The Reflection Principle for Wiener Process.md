---
title: Appendix 23. A The Reflection Principle for Wiener Process
tags:
  - barrier_probability
  - brownian_motion
  - knockout_call
  - reflection_principle
  - wiener_process
aliases:
  - Brownian Path
  - Reflection Principle
key_concepts:
  - Barrier probability calculation
  - Brownian path reflection
  - Down-and-in cash call
  - Hitting barrier level
  - Standard normal calculation
---

# Appendix 23. A The Reflection Principle for Wiener Process

For every standard Brownian path there is an equally likely path that can be constructed by reflecting the path,  or a portion of the path,  with respect to a horizontal line. Figure 23.5 shows a Brownian path,  $X_{r}$ ,  denoted by ABC,  that is reflected beginning at the poin where the path reaches $X_{t}=70$ .Notice that the path BD is a mirror image,  reflected vertically around the line $X=70$ ,  of the original path BC. We will see that by considering the reflected path,  it is possible to transform barrier probability calculations into standard normal probability calculations

Suppose we have a Brownian motion that starts at $X_{0}$ and follows the process

$$dX_{t}=\sigma dZ_{t}$$

Thus,  $X_{I}$ is normally distributed with mean $X_{0}$ and variance $\sigma^{2}T$ .We want to know the joint probability that at time $T,      X_{T}$ will have hit the barrier $H<X_{0}$ and will also be above the level $K\geq H$ . If we let $\underline{X}_{\mathrm{r}}$ denote the lowest value of $X$ between O and $I$ ,  we wish to compute the joint probability

$$\Pr (X_{T}>K,      \underline{X}_{T}\leq H)$$

## FIGURE 23.5

Illustration of refection principle. Original path is ABC. Path reflected about a barrier of 70 is ABD

 ![500](https://storage.simpletex.cn/view/fccZYAwqiloApgLsGN23M6KRUUEMxlngK)

The probability here is analogous to that in equation (23.6). If $X$ were the price of an asset this probability discounted at the risk-free rate would be the price of a down-and-in cash call. Suppose that $X_0=80$ $H=70$ ,  and $K=100$ Consider the actual Brownian path in

Figure 23.5 depicted by the letters ABC. This path starts at “A,  ” hits the barrier level of 70 at about time 1.25 (designated by the letter “B"),  and then ends at 104.66 ("C). ABC is an example of the path that satisfies our conditions. (A probability calculation for a Brownian motion essentially consists of asking what fraction of the possible paths satisfy specific conditions.) Now consider the path ABD. This path also starts at A and hits the barrier at B,  but

After point B it is the mirror image of ABC,  reflected about the barrier level of 70. The reflection principle in this context says that for any path that starts at 80,  hits 70 and ends up above 100,  there is an equally likely path that starts at 80,  hits 70,  and ends up below 40. Because they occur with the same probability,  it does not matter whether we count paths like ABC or paths like ABD. But paths like ABD are easier to count The fraction of paths that start at 80,  hit 70,  and end up above 100 equals the fraction

Of paths that start at 80,  hit 70,  and end up below 40. But for this second set of paths,  hitting 70 is a redundant condition: Any path ending below 40 will have hit 70 along the way. The hitting condition does not matter in computing the probability using the reflected path

The level 40 in this example can be expressed as
$$\begin{array}{c}70-(100-70)=H-(K-H)\\=2 H-K\end{array}$$
Thus,  the fraction of Brownian paths which satisfy our conditions is
$$\Pr (X_{t}>K\:,      \underline{X}_{t}\leq H)=\Pr (X_{T}<2 H-K)$$
This is a standard normal probability calculation:
$$\begin{aligned}
\operatorname*{Pr}(X_{T}<2 H-K)& =\mathrm{Pr}\left (\frac{X_{T}-X_{0}}{\sigma\sqrt{T}}\leq\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right) \\
&=N\left (\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right)
\end{aligned}$$
Because of the reflection principle,      the calculation with the hitting boundary involves only a standard normal calculation.

Example 23.1 Suppose $X_{0}=80,      \sigma=10$ ,      $H=70$ $K=100$ ,      and $T=5$ years. We have
$$\begin{aligned}
\Pr (X_{T}>100,      \underline{X}_{T}\leq 70|X_{0}=80)& =N\left ({\frac{2\times 70-100-80}{10{\sqrt{5}}}}\right) \\
&=N (-1.7889)=0.0368\:\equiv 
\end{aligned}$$
If we wish to calculate $\Pr (X_{T}>100,      \underline{X}_{T}>70)$ (the probability that a knockout call will pay off),      we can use the fact that hitting and not hitting are mutually exclusive events. Thus,      
$$\begin{aligned}
\mathrm{Pr}(X_{T}>K,      \underline{X}_{T}>H)& =\mathrm{Pr}(X_{T}>K)-\mathrm{Pr}(X_{T}>K,      \underline{X}_{T}\leq H) \\
&=N\left (\frac{X_{0}-K}{\sigma\sqrt{T}}\right)-N\left (\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right)
\end{aligned}$$

The actual barrier formulas differ in two respects from equations (23.48) and (23.49) First,      with geometric Brownian motion,      $\ln (X_{t})$ is normally distributed rather than $X_{t}$ .This results in $X_{0}$ ,      $K$ ,      $H$ ,      being replaced with $\ln (X_{0})$ ,      etc.

More importantly,      we assumed that $X$ was a Brownian motion with no drift. The construction of the reflection depends crucially on this assumption. By rewriting equatior 23.6,      however,      you can see that it reduces to equation (23.48) when $r-\delta-0.5\sigma^{2}=0$ (the logarithmic drift is zero):

$$\exp\left (2\frac{r-\delta-0.5\sigma^2}{\sigma^2}\ln (H/S)\right) N\left[\frac{2\ln (H)-\ln (S)-\ln (K)+(r-\delta-0.5\sigma^2) T}{\sigma\sqrt{T}}\right]$$

The incorporation of drift into barrier problems is discussed in Harrison (1985) and Steele (2010).

## References

Harrison,      J. M.,      1985,      Brownian Motion and Stochastic Flow Systems,      John Wiley & Sons,      New York
