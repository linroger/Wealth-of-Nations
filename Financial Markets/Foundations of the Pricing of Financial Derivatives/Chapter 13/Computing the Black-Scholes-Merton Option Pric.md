---
tags:
  - '#at_the_money_option'
  - '#black_scholes_merton_model'
  - '#call_options'
  - '#cumulative_distribution_table'
  - '#dividend_yield'
  - '#manual_calculation'
  - '#option_pricing'
  - '#put_call_parity'
  - '#put_options'
---
# 13.8 COMPUTING THE BLACK-SCHOLES-MERTON OPTION PRICING MODEL VALUES

We provide a few illustrations of the manual option value computation. The key to man-. ually calculating option values is the standard normal cumulative distribution table given in Chapter 5 (Table 5.1). We will refer back to Table 5.1 during these illustrations.

The dividend-adjusted Black-Scholes-Merton option pricing model for calls and puts can be expressed as

$$
\begin{array}{r l}&{c=S e^{-\delta\tau}N(d_{1})-X e^{-r_{c}\tau}N(d_{2}),}\ &{}\ &{p=X e^{-r_{c}\tau}N(-d_{2})-S e^{-\delta\tau}N(-d_{1}),}\end{array}
$$

where

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S/X)+\left(r_{c}-\delta+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}}}\ {{\quad}}\ {{d_{2}=d_{1}-\sigma\sqrt{\tau}.}}\end{array}
$$

We start with a non-dividend example with an at-the-money call option where the stock price is 50, the volatility is. $40\%$ , the interest rate is $2\%$ , and the time to maturity

is 0.25. The first step in the calculations requires the computation of $d_{1}$ and $d_{2}$ . Recall at-the-money implies $S=X$ , thus we have

$$
{\begin{array}{r l}&{d_{1}={\cfrac{\ln(S/X)+\left(r_{c}-\delta+\sigma^{2}/2\right)\tau}{\sigma{\sqrt{\tau}}}}}\ &{~={\cfrac{\ln(S0/50)+\left(0.02-0.0+0.4^{2}/2\right)0.25}{0.4{\sqrt{0.25}}}}={\cfrac{0.025}{0.2}}=0.125}\ &{d_{2}=d_{1}-\sigma{\sqrt{\tau}}=0.125-0.4{\sqrt{0.25}}=-0.075.}\end{array}}
$$

The second step is to look up the values of $N(d_{1})$ and $N(d_{2})$ from Table 5.1. Recall the values are given such that the first column provides the value of the first decimal and the first row provides the values of the second and third decimals incrementing by 0.005. Thus, the value for $N(d_{1})$ is found by locating the row starting with 0.1. From that row locate the column with a heading of 0.025. At the intersection of this row and column is the value 0.549738 and therefore $N\left(d_{1}\right)=0.549738.$ The value for $N(d_{2})$ is found by locating the row starting with $-0.0$ . From that row locate the column with a heading of 0.075. At the intersection of this row and column is the value 0.470107 and therefore $N\left(d_{2}\right)=0.470107$

The final step is to substitute these values into the call equation or

$$
{\begin{array}{r l}&{c=S e^{-\delta\tau}N{\bigl(}d_{1}{\bigr)}-X e^{-r_{c}\tau}N{\bigl(}d_{2}{\bigr)}}\ &{\quad=50e^{-0(0.25)}0.549738-50e^{-0.02(0.25)}0.470107}\ &{\quad=27.4869-23.3881=4.0988.}\end{array}}
$$

There are several ways to compute the put value. We first note the put-call parity approach. From the symmetry of the standard normal cumulative distribution function, we know that $N(-d)=1-N(d)$ Thus, the put equation can be rearranged to one expression of put-call parity or

$$
\begin{array}{r l}&{\indent{\cal P}=X e^{-r_{c}\tau}\big(1-N(d_{2})\big)-S e^{-\delta\tau}\big(1-N(d_{1})\big)}\ &{\indent=X e^{-r_{c}\tau}-S e^{-\delta\tau}+\Big[S e^{-\delta\tau}N(d_{1})-X e^{-r_{c}\tau}N(d_{2})\Big]}\ &{\indent=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c.}\end{array}
$$

With call value calculated, we can quickly compute the put value as

$$
\begin{array}{r l}&{\indent P=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c}\ &{\indent=50e^{-0.02(0.25)}-50e^{-0(0.25)}+4.0988}\ &{\indent=49.7506-50+4.0988=3.8494.}\end{array}
$$

Alternatively, we can work through the same three steps for computing the call option. The first step in manual calculations for a put requires the computation of $-d_{1}$ and $-d_{2}$ Thus, given we have already computed the values of $-d_{1}$ and $-d_{2}$ , we simply have

$$
\begin{array}{l}{-d_{1}=-\displaystyle\frac{\ln(S/X)+\left(r_{c}-\delta+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}=-0.125}\ {-d_{2}=0.075.}\end{array}
$$

The second step is to look up the values of $N(-d_{1})$ and $N(-d_{2})$ from Table 5.1. The value for $N(-d_{1})$ is found by locating the row starting with $-0.1$ . From that row locate the column with heading of 0.025. At the intersection of this row and column is the value 0.450262 and therefore $N{\left(-d_{1}\right)}=0.450262$ . The value for. $N(d_{2})$ is found by locating the row starting with 0.0. From that row locate the column with heading of 0.075. At the intersection of this row and column is the value 0.529893 and therefore $N\left(d_{2}\right)=0.529893$

The final step is to substitute these values into the put equation or

$$
\begin{array}{r l}&{\indent P=X e^{-r_{c}\tau}N\left(-d_{2}\right)-S e^{-\delta\tau}N\left(-d_{1}\right)}\ &{\indent=50e^{-0.02(0.25)}0.529893-50e^{-0(0.25)}0.450262}\ &{\indent=26.3625-22.5131=3.8494.}\end{array}
$$

Thus, both put values are identical. The key to successfully using Table 5.1 is knowing. where to round. The purpose of such a dense table is to avoid significant rounding error with manual calculations. With Table 5.1, we round up or down on the quarters, that is,. 0.XX25 and 0.XX75. For example, if $d_{1}=0.3224$ , then we round down to $d_{1}=0.320$ and use $N\left(d_{1}\right)=0.625516$ . Alternatively, if $d_{1}=0.3226$ , then we round up to $d_{1}=0.325$ and use $N\left(d_{1}\right)=0.627409$ . For most applications, Table 5.1 is granular enough to provide. option values without too much estimation error..

Now let us consider the influence of a $2\%$ dividend yield $\'\delta=0.02\rangle$ on our calculations given in the previous example. This will enable us to see firsthand the influence of dividends on call and put values. As before, the first step in manual calculations requires. the computation of $d_{1}$ and $d_{2}$ or

$$
{\begin{array}{r l}&{d_{1}={\frac{\ln(S/X)+(r_{c}-\delta+\sigma^{2}/Z)\tau}{\sigma{\sqrt{\tau}}}}}\ &{\quad={\frac{\ln(S0/50)+\left(0.02-0.02+0.4^{2}/2\right)0.25}{0.4{\sqrt{0.25}}}}=0.1}\ &{d_{2}=d_{1}-\sigma{\sqrt{\tau}}=0.1-0.4{\sqrt{0.25}}=-0.1.}\end{array}}
$$

The value for $N(d_{1})$ is found by locating the row starting with 0.1 and selecting the first value or $N\left(d_{1}\right)=0.539828$ . Similarly, we find the value for $N\left(d_{2}\right)=0.460172$ . The final step is to substitute these values into the call equation or

$$
{\begin{array}{r l}&{c=S e^{-\delta\tau}N(d_{1})-X e^{-r_{c}\tau}N(d_{2})}\ &{\quad=50e^{-0.02(0.25)}0.539828-50e^{-0.02(0.25)}0.460172}\ &{\quad=26.8568-22.8938=3.9630.}\end{array}}
$$

Applying put-call parity, we have

$$
\begin{array}{l}{{\displaystyle p=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c}}\ {{\displaystyle~=50e^{-0.02(0.25)}-50e^{-0.02(0.25)}+3.9630=3.9630.}}\end{array}
$$

Thus, both call and put values are identical because the underlying growth rate under. the equivalent martingale measure is zero. Clearly, we see that the call value declined and the put value increased when the dividend yield was changed from. $0\%$ to $2\%$
