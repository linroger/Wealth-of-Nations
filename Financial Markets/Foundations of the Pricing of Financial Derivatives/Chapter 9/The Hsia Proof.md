---
tags:
  - binomial_distribution
  - black_scholes_merton
  - hsia_proof
  - lognormal_distribution
  - option_pricing
aliases:
  - B-S-M
  - Black-Scholes
  - DeMoivre-LaPlace
  - Hsia's proof
key_concepts:
  - Asset price
  - Binomial distribution
  - Black-Scholes-Merton model
  - DeMoivre-LaPlace theorem
  - Hsia's proof
  - Lognormal process
  - Normal distribution
  - Option exercise
---

# 9.2 THE HSIA PROOF

Now we proceed to work through Hsia's elegant and straightforward proof. We appeal to the famous DeMoivre-LaPlace limit theorem, which says that a binomial distribution converges to the normal distribution if $n p\rightarrow\infty$ aS $n\to\infty$ . For $B_{1}$ we need

$$
B_{1}\to\int_{a}^{\infty}f(j)d j,
$$

where $f(j)$ is the density for a normal distribution. Because $j$ is not a standard normal.
distribution, however, let us convert. $j$ to a standard normal variable by defining. $z=(j-$
$E(j))/\sigma_{j}$ . Then we would have.

$$
\int_{a}^{\infty}f(j)d j=\int_{d}^{\infty}f(z)d z,{\mathrm{where}}z={\frac{j-E(j)}{\sigma_{j}}}.
$$

Following Hsia, however, we define

$$
d=-\frac{a-E(j)}{\sigma_{j}},
$$

which allows us to write the above, due to the symmetry of the normal distribution, as

$$
\int_{-\infty}^{d}f(z)d z.
$$

Thus,

$$
B_{1}\to\int_{a}^{\infty}f(j)d_{j}=\int_{-\infty}^{d}f(z)d z=N(d),
$$

where $j$ has been converted to. $z$ , a standard normal. What is happening here is that the. $N(d_{1})$ term in the Black-Scholes-Merton model is a cumulative normal probability. There-. fore, it reflects the probability of the variable ranging from. $-\infty$ to $d_{1}$ , yet it must capture a probability related to the option being exercised, which is a probability of the asset price being greater, not less, than the exercise price. This transformation solves the problem.. Furthermore, an identical procedure would be applied to $B_{2}$

Now let $S_{T}$ be the asset price at expiration. Of course, this value is not known but we can describe its stochastic properties. After $_n$ periods and $j$ up moves, $S_{T}/S=u^{j}d^{n-j}.$ Thus, the log (continuously compounded) return on the asset over the life of the option is

$$
\ln\left({\frac{S_{T}}{S}}\right)=j\ln u+(n-j)\ln d=j\ln\left({\frac{u}{d}}\right)+n\ln d.
$$

Now take the expectation of (9.25),

$$
E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=E(j)\ln\left({\frac{u}{d}}\right)+n\ln d.
$$

Rearranging to isolate $j_{:}$ we have

$$
E(j)=\frac{E\left[\ln\left(\frac{S_{T}}{S}\right)\right]-n\ln d}{\ln\left(\frac{u}{d}\right)}.
$$

The variance of the log return on the asset over the life of the option is

$$
\operatorname{var}\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=\operatorname{var}(j){\Big[}\ln\left({\frac{u}{d}}\right){\Big]}^{2}.
$$

Thus,

$$
\operatorname{var}(j)={\frac{\operatorname{var}\left[\ln\left({\frac{S_{T}}{S}}\right)\right]}{\left[\ln\left({\frac{u}{d}}\right)\right]^{2}}}.
$$

Recall from Equation (9.19) that $^{a}$ is defined as the lowest integer $j$ such that the call. option is in-the-money where $\imath$ is an adjustment factor forcing $^{a}$ to be the next integer or. a = In(x/%-nind + 1. Therefore, based on the mean and variance results above, the upper bound defined in Equation (9.22) can be expressed as

$$
d=-\frac{a-E(j)}{\sigma_{j}}=-\frac{\frac{\operatorname*{lin}\left(\displaystyle\frac{X}{S}\right)-n\ln d}{\operatorname*{lin}\left(\displaystyle\frac{u}{d}\right)}+\imath-\frac{E\left[\ln\left(\displaystyle\frac{S_{T}}{S}\right)\right]-n\ln d}{\ln\left(\displaystyle\frac{u}{d}\right)}}{\left\{\frac{\operatorname*{var}\left[\ln\left(\displaystyle\frac{S_{T}}{S}\right)\right]}{\left[\ln\left(\displaystyle\frac{U}{\cal S}\right)\right]^{2}}\right\}^{1/2}}=\frac{\frac{\ln\left(\displaystyle\frac{S}{X}\right)+E\left[\ln\left(\displaystyle\frac{S_{T}}{S}\right)\right]}{\ln\left(\displaystyle\frac{u}{d}\right)}-\imath}{\frac{\operatorname*{var}\left[\operatorname*{lin}\left(\displaystyle\frac{S_{T}}{S}\right)\right]}{\ln\left[\displaystyle\frac{\ln\left(\displaystyle\frac{U}{d}\right)}{S}\right]}}.
$$

From the properties of the binomial distribution, it is known that $\operatorname{var}(j)=n\phi(1-\phi)$ where $\phi$ is the probability per outcome. So, after some rearranging and substituting this variance result only in the second term below, we have

$$
d=\frac{\ln\left(\frac{S}{X}\right)+E\left[\ln\left(\frac{S_{T}}{S}\right)\right]}{\sqrt{\operatorname{var}\left[\ln\left(\frac{S_{T}}{S}\right)\right]}}-\frac{\ln\left(\frac{u}{d}\right)}{\sqrt{\phi(1-\phi)}}\frac{\imath}{\sqrt{n}}.
$$

As $_n$ goes to infinity, the second term disappears. Our discrete binomial process is ther. starting to converge to a continuous lognormal process, for which it is known tha1 var $[\ln(S_{T}/S)]=\sigma^{2}\tau.$ Thus, we have

$$
d={\frac{\ln\left({\frac{S}{X}}\right)+E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]}{\sigma{\sqrt{\tau}}}}.
$$

We need this expression to equal $d_{1}$ and $d_{2}$ as defined in the Black-Scholes-Merton formula when the probabilities are $\phi^{*}$ and $\phi$ , respectively, as defined previously. This means that we need

$$
E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=\left(r_{c}-{\frac{\sigma^{2}}{2}}\right)\tau{\mathrm{~if~the~probability~is~}}\phi.
$$

Now let us work on the first case. First recall that $\phi^{*}=[u/(1+r)][(1+r-d)/(u-d)]$ After some careful rearranging, we solve for $1+r$

$$
1+r=\frac{1}{\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right)}.
$$

Recall that $(1+r)^{n}=(1+r_{a})^{\tau}~\mathrm{so}^{5}$

$$
(1+r)^{n}=(1+r_{a})^{\tau}=\frac{1}{\left[\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right)\right]^{n}}.
$$

Now note that. $S/S_{T}$ can be expressed as follows:6

$$
{\frac{S}{S_{T}}}=\left({\frac{S_{0}}{S_{1}}}\right)\left({\frac{S_{1}}{S_{2}}}\right)\ldots\left({\frac{S_{n-1}}{S_{n}}}\right)=\prod_{i=1}^{n}\left({\frac{S_{i-1}}{S_{i}}}\right).
$$

where $S=S_{0}$ and $S_{T}=S_{n}$ . The expectation of this expression would be

$$
E\left({\frac{S}{S_{T}}}\right)=E\left[\prod_{i=1}^{n}\left({\frac{S_{i-1}}{S_{i}}}\right)\right]=\prod_{i=1}^{n}E\left({\frac{S_{i-1}}{S_{i}}}\right).
$$

Note that our ability to express the expected value of a product as the product of the expected values comes from the independence of the asset prices. That is, we know that $c o\nu(x y)=E(x y)-E(x)E(y)$ If $x$ and $y$ are independent, however, then $c o\nu(x y)=0$ and $E(x y)=E(x)E(y)$

Now recall that our probability for $B_{1}$ is $\phi^{*}$ . Because $S_{i}=S_{i-1}u$ with probability $\phi^{*}$ and $S_{i}=S_{i-1}d$ with probability $1-\phi^{*}$ , then

$$
E\left(\frac{S_{i-1}}{S_{i}}\right)=\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right).
$$

Thus,

$$
E\left(\frac{S}{S_{T}}\right)=\prod_{i=1}^{n}\left[\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right)\right]=\left[\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right)\right]^{n}.
$$

Inverting Equation (9.39) gives

$$
\left[E\left(\frac{S}{S_{T}}\right)\right]^{-1}=\left[\phi^{*}\left(\frac{1}{u}\right)+(1-\phi^{*})\left(\frac{1}{d}\right)\right]^{-n}.
$$

Because $(1+r)^{\tau}=[\phi^{*}(1/u)+(1-\phi^{*})(1/d)]^{-n}$ ,then $(1+r)^{\tau}=E(S/S_{T})^{-1}$ or $(1+r)^{-\tau}$ $=E(S/S_{T})$ . Therefore,

$$
-\tau\ln(1+r_{a})=\ln\left[E\left(\frac{S}{S_{T}}\right)\right].
$$

So now we are working with $\ln[E(S/S_{T})]$ . Because $S_{T}/S$ is lognormally distributed, it will also be true that the inverse of a lognormal distribution is lognormally distributed.7 Thus, $S/S_{T}$ is lognormally distributed. For any random variable $x$ that is lognormally distributed, it will be the case that $\ln[E(x)]=E[\ln(x)]+\mathrm{{var}[\ln(}x)]/2$ This result may not look correct, but follows from a widely used result in options: The log return is defined as $S_{T}/S=e^{x}$ so $\ln(S_{T}/S)=x$ It is known that $E(x)=\exp(\mu+\sigma^{2}/2)$ 8 Thus, $\ln E(x)=\mu+\sigma^{2}/2$ , where $\mu$ is $E[\ln(x)]$ and $\sigma$ is its standard deviation.

Because $-\tau\ln(1+r_{a})=\ln[E(S/S_{T})]$ (see Equation (9.41)), then

$$
\begin{array}{r l}&{-\tau\ln(1+r_{a})=E\left[\ln\left(\frac{S}{S_{T}}\right)\right]+\frac{\mathrm{var}\left[\ln\left(\frac{S}{S_{T}}\right)\right]}{2}}\ &{=E\left[-\ln\left(\frac{S_{T}}{S}\right)\right]+\frac{\mathrm{var}\left[-\ln\left(\frac{S_{T}}{S}\right)\right]}{2}=-E\left[\ln\left(\frac{S_{T}}{S}\right)\right]+\frac{\mathrm{var}\left[\ln\left(\frac{S_{T}}{S}\right)\right]}{2}.}\end{array}
$$

Note the origin of these results,. $E[\ln(S/S_{T})]=E[-\ln(S_{T}/S)]=-E[\ln(S_{T}/S)]$ , because you can always pull a minus sign out from inside an expectations operator. Also, $\mathrm{\Delta}\mathrm{r}[\ln(S/S_{T})]=\mathrm{var}[-\ln(S_{T}/S)]=\mathrm{var}[\ln(S_{T}/S)].$ because you can pull the constant. $(-1)$ out in front of the variance operator by squaring it, thereby obtaining one times the variance.

Now what we have is

$$
E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=\tau\ln(1+r_{a})+{\frac{\mathrm{var}\left[\ln\left({\frac{S_{T}}{S}}\right)\right]}{2}}.
$$

Recall that we know that var $[\ln(S_{T}/S)]$ is $\sigma^{2}\tau$ . Thus, we have

$$
E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=\left[\ln(1+r_{a})+{\frac{\sigma^{2}}{2}}\right]\tau.
$$

Because $\ln(1+r)=r_{c}$ , this is the result we want for $B_{1}$ to converge to $N(d_{1})$

For $B_{2}$ to converge to $N(d_{2})$ , recall the definition $\phi=(1+r-d)/(u-d)$ . Then $1+$ $r=[\phi u+(1-\phi)d]$ . Because $S_{i}=S_{i-1}u$ with probability $\phi$ and $S_{i}=S_{i-1}d$ with probability $1-\phi$ then $E(S_{i}/S_{i-1})=\phi u+(1-\phi)d=1+r.$ Because

$$
E\left(\frac{S_{T}}{S}\right)=E\left[\prod_{i=1}^{n}\left(\frac{S_{i}}{S_{i-1}}\right)\right]=\prod_{i=1}^{n}E\left(\frac{S_{i}}{S_{i-1}}\right)=[\phi u+(1-\phi)d]^{n}=(1+r)^{n}=(1+r_{a})^{1}
$$

it follows that

$$
\ln\left[E\left(\frac{S_{T}}{S}\right)\right]=\tau\ln(1+r_{a}).
$$

Again, recall

$$
\ln\left[E\left({\frac{S_{T}}{S}}\right)\right]=E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]+{\frac{\mathrm{var}\left[\ln\left({\frac{S_{T}}{S}}\right)\right]}{2}}.
$$

Substituting our previous result, and note the switch to solving for $E[\ln(S_{T}/S)]$ and recall va1 $\cdot[\ln(S_{T}/S)]=\sigma^{2}\tau$ we have

$$
E\left[\ln\left({\frac{S_{T}}{S}}\right)\right]=\left[\ln(1+r_{a})-{\frac{\sigma^{2}}{2}}\right]\tau.
$$

cause $\ln(1+r_{a})=r_{c}$ , this is the result we needed to obtain convergence of. $B_{2}$ to $N(d_{2})$ Thue we have choun that the hinomial model for a call can he evnrecced ac

$$
c=S B_{1}-X e^{-r_{c}\tau}B_{2},
$$

where

$$
\begin{array}{l}{{{\cal B}_{1}=e^{-r_{c}\tau}\displaystyle\sum_{j=a}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j}u^{j}d^{n-j}~\mathrm{and}}}\ {{{\cal B}_{2}=\displaystyle\sum_{j=a}^{n}\binom{n}{j}\phi^{j}(1-\phi)^{n-j},}}\end{array}
$$

which will converge to the Black-Scholes-Merton model in the limit as $n\to\infty$ , expressed as

$$
c_{t}=S_{t}N(d_{1})-X e^{-r_{c}\tau}N(d_{2}),
$$

![](8c4a202d24ab23978625bbce3b9f1b2b949ea4fc74d8205c77a9b12543aad015.jpg)
FIGURe 9.1  Convergence of the Binomial Model for Calls to the Black-Scholes-Merton

where

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{t}/X)+(r_{c}+\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}},\mathrm{and}}}\ {{d_{2}=\displaystyle\frac{\ln(S_{t}/X)+(r_{c}-\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}}.}}\end{array}
$$

For example, suppose $S=100,X=100,r=5.0\%,\sigma=30\%.$ and $\tau=1$ year. Figure 9.1 illustrates the call prices as the number of time steps increases. The binomial call price quickly converges to the Black-Scholes-Merton price of 14.23. The zig-zag pattern is well known. An odd number of steps produces values on the high side, and an even number of steps produces values on the low side.
