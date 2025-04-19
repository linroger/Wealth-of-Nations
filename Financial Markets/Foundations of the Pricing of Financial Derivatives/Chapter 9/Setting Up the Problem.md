---
tags:
  - binomial_model
  - black_scholes_merton_model
  - continuous_compounding
  - put_call_parity
  - risk_neutral_probability
aliases:
  - Binomial
  - Black-Scholes
  - Call Option
  - Option Pricing
key_concepts:
  - Binomial coefficient
  - Black-Scholes-Merton formula
  - Continuous discounting
  - Put-call parity
  - Risk-neutral probability
---

# 9.1 SETTING UP THE PROBLEM

We start with our ultimate objective, the Black-Scholes-Merton model for calls and puts,

$$
\begin{array}{r l}&{c_{t}=S_{t}N(d_{1})-X e^{-r_{c}\tau}N(d_{2}),}\ &{~p=c-S+X e^{-r_{c}\tau}=X e^{-r_{c}\tau}N(-d_{2})-S N(-d_{1}),}\ &{d_{1}=\frac{\ln(S_{t}/X)+(r_{c}+\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}},\mathrm{and}}\ &{d_{2}=\frac{\ln(S_{t}/X)+(r_{c}-\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}},}\end{array}
$$

where $S_{t}$ is the current asset price at time $t,X$ is the exercise price,. $r_{c}$ is the continu-.
ously compounded risk-free rate, $\tau$ is the time to expiration, and $\bar{\sigma}^{2}$ is the variance of the.

continuously compounded return on the asset. $N(d_{i})$ is the cumulative normal probability for $i=1$ and 2 as defined.3

For now, we focus solely on calls as we can use put-call parity to arrive at the result for puts. The binomial model for the call where the option's life is divided into. $_n$ time periods is

$$
c=\frac{\displaystyle\sum_{j=0}^{n}\binom{n}{j}\phi^{n}(1-\phi)^{n-j}\mathrm{max}(0,u^{j}d^{n-j}S-X)}{(1+r)^{n}},
$$

where $\binom{n}{j}\mathrm{is}n!/[j!(n-j)!]$ is known as the binomial coefficient. The binomial coefficient represents the number of paths the asset can take to reach a certain point in a binomial tree where $j$ denotes the number of up moves, $\phi$ is the risk-neutral probability of an up move and equals $(1+r-d)/(u-d)$ $\boldsymbol{\mathscr{u}}$ and $d$ are one plus the per-period return on the asset if it goes up and down, respectively, and $r$ is the discrete risk-free interest rate per period. The numerator is the expected payout of the option at expiration under the risk-neutral. binomial probability, and the denominator discounts the risk-neutral expected payoff to. the present.

This expression can be simplified. For some outcomes, $\operatorname*{max}(0,u^{j}d^{n-j}S-X)$ is zero. Let $^{a}$ represent the minimum number of upward moves required for the call to finish in the money. That is,. $^{a}$ is the smallest integer. $(a\in n)$ such that $u^{a}d^{n-a}S>X$ 4 Then for all. $j<a$ $\operatorname*{max}(0,u^{j}d^{n-j}S-X)=0$ , and for $j>a$ $\operatorname*{max}(0,u^{j}d^{n-j}S-X)=u^{j}d^{n-j}S-X$ Now we need. count only the binomial paths from $j=a$ to $_n$ so we can write the model as

$$
c=\frac{\displaystyle\sum_{j=a}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j}(u^{j}d^{n-j}S-X)}{(1+r)^{n}}.
$$

Now let us break this up into two terms based on $S$ and $X$

$$
c=S\left[\frac{\displaystyle\sum_{j=a}^{n}\left(\displaystyle\sum_{j}^{n}\right)\phi^{j}(1-\phi)^{n-j}u^{j}d^{n-j}}{(1+r)^{n}}\right]-X(1+r)^{-n}\left[\displaystyle\sum_{j=a}^{n}\left(\displaystyle\sum_{j}^{n}\phi^{j}(1-\phi)^{n-j}\right].
$$

Let us call the two terms in the large brackets $B_{1}$ and $B_{2}$ . Specifically,

$$
\begin{array}{r l}&{B_{1}=\displaystyle\frac{\sum_{j=a}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j}u^{j}d^{n-j}}{(1+r)^{n}}\mathrm{~and}}\ &{B_{2}=\displaystyle\sum_{j=a}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j}.}\end{array}
$$

Equation (9.9) is the formula for the probability of $^{a}$ or more successes in. $_n$ trials if the probability of success on any one trial is. $\phi.B_{1}$ is similar but cannot be expressed quite.

as easily without redefining the probability. Note the following:

$$
\frac{\phi^{j}(1-\phi)^{n-j}u^{j}d^{n-j}}{(1+r)^{n}}=\left[\left(\frac{u}{1+r}\right)\phi\right]^{j}~\left[\left(\frac{d}{1+r}\right)(1-\phi)\right]^{n-j}.
$$

Now, it will be useful to define a modified version of the binomial probability, call it $\phi^{*}=[u/(1+r)]\phi$ and $1-\phi^{*}=[d/(1+r)](1-\phi)$ . Thus, we can write Equation (9.10) as $\phi^{*j}(1-\phi^{*})^{n-j}$ . Thus, $B_{1}$ is a binomial probability as stated but with the probability of each. trial being $\phi^{*}$ . Now, we can write the binomial model in compact form as

$$
c=S B_{1}-X(1+r)^{-n}B_{2},
$$

where

$$
\begin{array}{l}{{{\cal B}_{1}=\displaystyle\sum_{j=a}^{n}\left({n\atop j}\right)\phi^{*j}(1-\phi^{*})^{n-j}~\mathrm{and~as~before}}}\ {{{\cal B}_{2}=\displaystyle\sum_{j=a}^{n}\left({n\atop j}\right)\phi^{j}(1-\phi)^{n-j}.}}\end{array}
$$

Based on put-call parity, we note that the put price is

$$
\begin{array}{l c r}{{\displaystyle p=c-S+X(1+r)^{-n}=S B_{1}-X(1+r)^{-n}B_{2}-S+X(1+r)^{-n}}}\ {{}}\ {{}}\ {{}}\ {{}=X(1+r)^{-n}(1-B_{2})-S(1-B_{1}).}}\end{array}
$$

Thus, we can easily move from the results for calls to arrive at the results for puts. Our objective is to get this formula to converge to the Black-Scholes-Merton formula. Obviously, we shall have to get. $B_{1}$ and $B_{2}$ to converge to $N(d_{1})$ and $N(d_{2})$ , respectively.

Let us do the simple part first, the risk-free rate. Recall that $(1+r)^{-n}$ is the present value factor for $_n$ periods where the per-period rate is. $r.$ The per-period rate can be related to an annual rate applied for $\tau$ years by the relationship $(1\dot{+}r)\dot{=}(1+r_{a})^{1/n_{y}}$ where $n_{y}$ is the number of periods per year. Then,.

$$
\begin{array}{c}{{(1+r)=(1+r_{a})^{1/n_{y}}}}\ {{{}}}\ {{(1+r)^{n}=(1+r_{a})^{(1/n_{y})n}}}\ {{{}}}\ {{(1+r)^{n}=(1+r_{a})^{\tau}\mathrm{because}\tau=n/n_{y}.}}\end{array}
$$

Thus, the present value factor for. $\tau$ years is $(1+r_{a})^{-\tau}$ . Now we can convert discrete dis-. counting to continuous discounting as follows:

$$
\begin{array}{r l}&{\ln{(1+r_{a})^{-\tau}}=-\tau\ln(1+r_{a})}\ &{~e^{\ln{P V}}=e^{-\tau\ln(1+r_{a})}}\ &{~{P V}=e^{-r_{c}\tau}\mathrm{where}r_{c}=\ln(1+r_{a}).}\end{array}
$$

Thus, our present value factor is equivalent to $\exp(-r_{c}\tau)$ with the interest rate continuously compounded. So the binomial formula is equivalent to

$$
c=S B_{1}-X e^{-r_{c}\tau}B_{2}.
$$

Now let us proceed to turn this binomial formula into the Black-Scholes-Merton formula.

Because we require $S u^{a}d^{n-a}>X$ for the option to exercise, it follows that

$$
\begin{array}{r}{\ln S+a\ln u+(n-a)\ln d>\ln X}\ {\ln S+a\ln u+n\ln d-a\ln d>\ln X}\ {a(\ln u-\ln d)>\ln X-\ln S-n\ln d}\ {a>\displaystyle\frac{\ln(X/S d^{n})}{\ln(u/d)}=\frac{\ln(X/S)-n\ln d}{\ln(u/d)}.}\end{array}
$$

By the nature of its definition as the minimum number of steps for the option to expire in-the-money, $^{a}$ has to be an integer, but Equation (9.18) will not likely produce an inte-. ger. For example, with $S=100$ $X=100$ $u=1.10$ $d=0.95$ , and $n=10$ , we have $a>$ 3.4988. This means that it would take at least four upward moves for the option to finish in-the-money. We shall handle this complication by introducing a filler variable,. $\iota$ , which is a Greek lowercase iota, such that.

$$
a=\frac{\ln(X/S)-n\ln d}{\ln(u/d)}+\imath,
$$

where $\imath$ is a number added to the result from Equation (9.18) to make $a$ an integer. In the limit, this variable will not matter as it will converge to zero with an infinite number of time steps.

To illustrate the results thus far, suppose $S=25$ $X=40$ $u=1.10$ $d=0.90$ $n=10$ and $r=3.0\%$ . Based on this example, Table 9.1 illustrates the following potential outcomes along with probabilities. With the binomial tree, the total number of outcomes is $2^{\mathrm{n}}$ or $2^{10}=1,024$ here. The total probability whether modified or not is $100\%$ . Finally, based on the risk-neutral approach,. the expected terminal value of the asset is. $S(1+r)^{n}$ or $25(1+0.031)^{10}=33.93$ here. Further, we have

$$
a>\frac{\ln(X/S)-n\ln d}{\ln(u/d)}=\frac{\ln(40/25)-10\ln0.9}{\ln(1.1/0.9)}=7.5926=a^{*},
$$

$$
a={\frac{\ln(X/S)-n\ln d}{\ln(u/d)}}+\imath=a^{*}+\imath=7.5926+0.4074=8.
$$

TABLE 9.1 Illustration of 10 Period Binomial Model Outcomes and Probabilities


<html><body><table><tr><td>Counter</td><td>n choosej</td><td>B,(i)</td><td>B2(i)</td><td>S</td></tr><tr><td>0</td><td>1</td><td>0.00001</td><td>0.0000</td><td>8.72</td></tr><tr><td>1</td><td>10</td><td>0.0001</td><td>0.0005</td><td>10.65</td></tr><tr><td>2</td><td>45</td><td>0.0015</td><td>0.0039</td><td>13.02</td></tr><tr><td>3</td><td>120</td><td>0.0092</td><td>0.0196</td><td>15.92</td></tr><tr><td>4</td><td>210</td><td>0.0374</td><td>0.0652</td><td>19.45</td></tr><tr><td>5</td><td>252</td><td>0.1041</td><td>0.1485</td><td>23.77</td></tr><tr><td>6</td><td>210</td><td>0.2012</td><td>0.2349</td><td>29.06</td></tr><tr><td>7</td><td>120</td><td>0.2668</td><td>0.2549</td><td>35.52</td></tr><tr><td>8</td><td>45</td><td>0.2322</td><td>0.1815</td><td>43.41</td></tr><tr><td>9</td><td>10</td><td>0.1197</td><td>0.0766</td><td>53.05</td></tr><tr><td>10</td><td>1</td><td>0.0278</td><td>0.0145</td><td>64.84</td></tr><tr><td>Sum</td><td>1024</td><td>1.0000</td><td>1.0000</td><td>33.93*</td></tr></table></body></html>

\*Sum of the product of ${\mathrm{B}}_{2}{\mathrm{S}}$ or the expected terminal asset price.

Thus, $S>X$ only for outcomes where up has occurred eight or more times. Thus, we can compute the binomial probabilities from Equations (9.8) and (9.9) as

$$
\begin{array}{l}{\phi=\displaystyle\frac{1+r-d}{u-d}=\frac{1+0.031-0.9}{1.1-0.9}=0.6550,}\ {\displaystyle\sum_{B_{1}=\frac{j=a}{\gamma}}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j}u^{j}d^{n-j}}_{=\frac{j=8}{\gamma}}\binom{10}{j}0.6550^{j}(1-0.6550)^{10-j}1.1^{j}0.9^{10-j}}\ {(1+r)^{n}}\ {=0.2322+0.1197+0.0278=0.3797}\ {\sum_{\bf\sigma}^{n}\binom{n}{m}_{\bf\sigma....}\quad\ldots\quad\frac{10}{m}\binom{10}{10}0.6550^{j}(1-0.6550)^{10-j}1.1^{j}0.9^{10-j}}\end{array},
$$

$$
B_{2}=\sum_{j=a}^{n}{\binom{n}{j}}\phi^{j}(1-\phi)^{n-j}=\sum_{j=8}^{10}{\binom{10}{j}}0.6550^{j}(1-0.6550)^{10-j}
$$

$$
=0.1815+0.0766+0.0145=0.2726
$$

Thus, the option prices are

$$
c=S B_{1}-X e^{-r_{c}\tau}B_{2}=25(0.3797)-40(0.7369)(0.2726)=1.46
$$

$$
\begin{array}{r}{p=c-S+X e^{-r_{c}\tau}=1.46-25+40(0.7369)=5.93.}\end{array}
$$
