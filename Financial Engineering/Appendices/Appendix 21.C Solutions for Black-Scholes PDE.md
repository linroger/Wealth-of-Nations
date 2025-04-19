---
cssclasses: academia
title: Appendix 21. C Solutions for Black-Scholes PDE
tags:
  - backward_equation
  - black_scholes
  - geometric_brownian_motion
  - option_pricing
  - pde
aliases:
  - BS equation solutions
  - Black-Scholes PDE solutions
key_concepts:
  - Asset-or-nothing option
  - Backward equation
  - Black-Scholes equation
  - Boundary conditions
  - General solution
---

# Appendix 21. C Solutions for Black-Scholes PDE

The Black-Scholes partial differential equation has the form

$$V_t+\frac{1}{2}\sigma^2 S^2 V_{SS}+\eta SV_S=\beta V$$

In equation (21.11),  we have $\eta=r-\delta$ and $\beta=r$ .When $\beta=0$ ,  equation (21.47) is the backward equation,  equation (21.33)

Suppose we guess the following general solution to equation (21.47):

$$\begin{aligned}V (S, t)&=Ae^{\gamma t}S^{a}N (x)^{y}\\&x=\frac{\ln[S (t)]+f+g (T-t)}{\sigma\sqrt{T-t}}\end{aligned}$$

Where $A, a, f, g$ ,  and $\gamma$ are constants to be determined,  and 0 and $y$ are parameters. $N (x)$ is the cumulative standard normal distribution. We will consider the cases $y=\{0, 1\}$ Note that sums of solutions are also solutions.

Computing the various derivatives of this guessed solution,  substituting them into equation (21.47),  and simplifying gives

$$\begin{aligned}&0=\left[\frac{1}{2}\sigma^{2}a^{2}+a\left (\eta-\frac{1}{2}\sigma^{2}\right)+\gamma-\beta\right]\\&+yN (x)^{-1}N^{\prime}(x)\left[\frac{\sigma^{2}\left (a-\frac{1}{2}\right)+\eta-g}{\sigma\sqrt{T-t}}\right]\end{aligned}$$

The parameters $A$ and $f$ are not in any way determined by this equation; hence,  they are solely determined by boundary conditions. Equation (21.49) is satisfied for

$$a=\left (\frac{1}{2}-\frac{\eta}{\sigma^2}\right)\pm\sqrt{\left (\frac{\eta}{\sigma^2}-\frac{1}{2}\right)^2+2\frac{\beta-\gamma}{\sigma^2}}$$

And

$$g=\sigma^2\left (a-\frac{1}{2}\right)+\eta $$

The first term in square brackets stems from differentiating $Ae^{\gamma r}S^{a}$ ,  while the second brack eted term stems from differentiating $N (x)$ We will examine only a few of the commonly occurring solutions. Since $Ae^{-\gamma (T-t)}S^{a}N (x)$ and $Ae^{-\gamma (I-t)}S^{a}$ both solve the PDE,  and since sums of solutions are also solutions,  then

$$Ae^{-\gamma (T-t)}S^a\left[N (x)-1\right]=Ae^{-\gamma (T-t)}S^aN (-x)$$

Is also a solution.

## Solutions to the Black-Scholes Equation

The parameters 711 and $\beta$ are determined by the PDE that arises in solving a particulan problem. In the standard Black-Scholes equation,  $\eta=r-\delta$ and $\beta=r$ ; this is the case we will consider. Let $a^{+}$ denote the positive root in equation (21.50),  and $a^{-}$ the negative root. Since $g$ is defined in terms of $d$ ,  for any given $\gamma$ ,  there are two matched $\{a, g\}$ pairs

If we pick $\gamma$ ,  the rest of the solution is determined by equations (21.50) and (21.51) in conjunction with boundary conditions. Two obvious choices are $\gamma=r$ and $\gamma=\delta$ If $\gamma=r$ ,  then $\{a^{+}, g^{+}\}=\{0, r-\delta-\frac{1}{2}\sigma^{2}\}$ and $\{a^{-}, g^{-}\}=\left\{1-2\frac{r-\delta}{\sigma^{2}}, -\left (r-\delta-\frac{1}{2}\sigma^{2}\right)\right\}$ The positive roots here,  together with appropriate boundary conditions,  generate the price of a cash-or-nothing option,  equation (21.16). If $\gamma=\beta-\eta=\delta$ ,  then $\{a^{+}, g^{+}\}=\{1, r-\delta+$ $\frac{1}{2}\sigma^{2}\}$ and $\{a^{-}, g^{-}\}=\left\{-2\frac{r-\delta}{\sigma^{2}}, -\left (r-\delta+\frac{1}{2}\sigma^{2}\right)\right\}$ .The positive roots here,  together with boundary conditions,  generate the price of an asset-or-nothing option,  equation (21.15) The following expressions all satisfy the Black-Scholes PDE

$$V^5[S (t), t]=e^{-\delta (T-t)}S^{-a_3}\times N\left (\frac{\ln[S (t)]+f-[r-\delta+0.5\sigma^2][T-t]}{\sigma\sqrt{T-t}}\right)$$

$$V^{6}[S (t), t]=e^{-r (T-t)}S^{1-a_{3}}\times N\left (\frac{\ln[S (t)]+f-[r-\delta-0.5\sigma^{2}][T-t]}{\sigma\sqrt{T-t}}\right)$$

$$V^7[S (t), t]=AS (t)^{a_1}$$

$$V^8[S (t), t]=AS (t)^{a_2}$$

Where

$$\begin{aligned}
&a_{1} =\left (\frac{1}{2}-\frac{r-\delta}{\sigma^{2}}\right)+\sqrt{\left (\frac{r-\delta}{\sigma^{2}}-\frac{1}{2}\right)^{2}+\frac{2 r}{\sigma^{2}}} \\
&a_{2} =\left (\frac{1}{2}-\frac{r-\delta}{\sigma^{2}}\right)-\sqrt{\left (\frac{r-\delta}{\sigma^{2}}-\frac{1}{2}\right)^{2}+\frac{2 r}{\sigma^{2}}} \\
&a_{3} =\frac{2 (r-\delta)}{\sigma^{2}} 
\end{aligned}$$

With appropriate choice of $A$ , equations (21.54) and (21.55) are the formulas for infinitely lived options. We will see in Chapter 22 that equations (21.52) and (21.53) play a role in pricing barrier options. The solutions to the equations in Table 21.1 are obtained by choosing the parameters listed there. These equations also satisfy specific boundary conditions.

## Solutions to the Backward Equation

For a stock following geometric Brownian motion, the backward equation is satisfied if $\beta=0.$ It turns out that $\gamma=0$ is frequently the solution of interest. For example, the Black Scholes term $N (d_{2})$ , without a discount factor, is the risk-neutral probability that $S (T)>K$ and is a solution to the forward equation.

Consider these (undiscounted) variants of equations (21.52) and (21.53)
$$
e^{r (T-t)}V^{5}[S (t), t] = e^{(r-\delta)(T-t)} S(t)^{-a_{3}} N\left( \frac{\ln[S(t)] + f - [r-\delta+0.5\sigma^{2}](T-t)}{\sigma\sqrt{T-t}} \right) 
$$

$$
e^{r (T-t)}V^{6}[S (t), t] = S^{1-a_{3}} N\left( \frac{\ln[S(t)] + f - [r-\delta-0.5\sigma^{2}](T-t)}{\sigma\sqrt{T-t}} \right)
$$

TABLE 21.1 Parameters generating the solutions to the Black-Scholes PDE for the indicated equation.

<table>
	<tbody>
		<tr>
			<th>Equation</th>
			<th>$y$</th>
			<th>$\gamma$</th>
			<th>$a\left (\mathrm{Equation~(21.50)}\right)$ 1</th>
		</tr>
		<tr>
			<td>(21.12)</td>
			<td>0</td>
			<td>$r$</td>
			<td>$a^+=0$</td>
		</tr>
		<tr>
			<td>(21.13)</td>
			<td>0</td>
			<td>$\delta$</td>
			<td>$a^+=1$</td>
		</tr>
		<tr>
			<td>(21.15)</td>
			<td>l</td>
			<td>$\delta$</td>
			<td>$a^+=1$</td>
		</tr>
		<tr>
			<td>(21.16)</td>
			<td>l</td>
			<td>$\delta$</td>
			<td>$a^{-}=-2$</td>
		</tr>
		<tr>
			<td>(21.52)</td>
			<td>l</td>
			<td>$r$</td>
			<td>$a^+=0$</td>
		</tr>
		<tr>
			<td>(21.53)</td>
			<td>l</td>
			<td>$r$</td>
			<td>$a^{-}=1-2$</td>
		</tr>
		<tr>
			<td>(21.54)</td>
			<td>0</td>
			<td>0</td>
			<td>$\left\|\frac{1}{2}\right\|$</td>
		</tr>
		<tr>
			<td>(21.55)</td>
			<td>0</td>
			<td>0</td>
			<td>$a$ -</td>
		</tr>
	</tbody>
</table>

You can verify that equations (21.56) and (21.57) obey equation (21.34). With an appropriate scale factor and choice of $f$ , equation (21.56) will appear in Chapter 22 as the risk-neutral probability that the stock price hits a barrier and exceeds a terminal strike price Finally, note that you can use Proposition 21.1 to obtain equation (21.55) from equation (21.56)