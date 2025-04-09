# 13.3 DERIVING THE BLACK-SCHOLES-MERTON MODEL AS AN EXPECTED VALUE

Another approach to deriving the Black-Scholes-Merton model is to treat the option as if it were valued in a world of risk-neutral investors. The Black-Scholes-Merton price is then found as the present value of the expected call price at expiration. We term this solution methodology as the expectations approach.

In such a world, investors are not concerned about risk, and the risk-free rate is an appropriate discount rate. Thus,

$$
c=e^{-r_{c}\tau}E_{t}\big(c_{T}\big)\:.
$$

The use of risk neutrality may appear to be unpalatable, but it is entirely appropriate in option pricing, as we discussed in previous chapters. We have already noted that the expected return on the asset is not a factor in the Black-Scholes-Merton model. The risk preferences of investors are reflected in an asset's expected return; thus, the BlackScholes-Merton model does not require an adjustment for investor risk preferences. We are not assuming that investors are actually risk neutral. On the contrary, virtually all investors are risk averse, but their feelings about risk are reflected in the asset price. Risk is priced in the market for the underlying asset, and the price of risk, what we call the risk premium, shows up in the price of the asset. All other things equal, the price of the asset is lower if there is more risk or if the degree of risk aversion of investors increases, but the risk aversion is embedded in the asset price, and we do not have to take it into account in pricing the option. Of course, these are points we have already made, but they must be recalled and accepted to proceed further.

The process of pricing an option via risk neutrality amounts to taking discounted expectations under an equivalent martingale probability distribution. The price of any asset that trades in a no-arbitrage world can be obtained as the discounted expectation of its future payoff, where the probabilities that determine its expectation are called equivalent martingale probabilities and the discount rate is the risk-free rate. A martingale is a stochastic process in which the expectation of an asset's future value is its current value. As has been shown elsewhere, a world of no-arbitrage is equivalent to a world in which the asset price can be obtained using the probabilities that would exist if investors were risk neutral; discounting then proceeds at the risk-free rate. In option pricing theory, we. should be confident that no arbitrage opportunities exist and we can take investors' feel-. ings about risk as given and reflected already in the asset price. No further adjustment for risk is required and indeed any further adjustment would be a double penalty. Let us state more formally that our option price is.

$$
c=e^{-r_{c}\tau}E_{t}^{Q}\left(c_{T}\right),
$$

which means that the expectation of the option payoff, $c_{T},$ is taken at time $t$ using equivalent martingale probabilities and discounted to the present at the risk-free rate. Now let us proceed to evaluate this expression.

Recall from our model that $d\mathbb{W}=\varepsilon\sqrt{d t}$ 9 The time increment over the life of the option is $\Delta t=\tau$ Now let us define the stochastic increment $\Delta W=\varepsilon^{*}\sqrt{\Delta t}=\varepsilon^{*}\sqrt{\tau}$ The term $\varepsilon$ .5 not the instantaneous increment. It represents the accumulated value of all the instantaneous increments. Recall the original stochastic process,. $d S/S=\alpha d t+\sigma d\mathrm{W}.$ Given that $\varepsilon^{*}$ is normally distributed and is the source of all the uncertainty, we should be able to. use normal probability theory to evaluate the expectation. We shall need to express the stochastic process in such a manner that the return on the asset is normally distributed. In geometric Brownian motion, the log return on the asset is normally distributed, so we will need the stochastic process for the log of the asset return..

Define $d S+S$ as the asset price at an instant, $d t_{:}$ later. Thus, we can write the stochastic process as $d S+S=S\big[1+\alpha d t+\sigma d W\big].$ Working with the term in brackets, note that we can write it in the following way:

$$
1+\alpha d t+\sigma d W=1+\left[\left(\alpha-\sigma^{2}/2\right)d t+\sigma d W+\left(\left(\alpha-\sigma^{2}/2\right)d t+\sigma d W\right)^{2}/2\right].
$$

By multiplying out the terms on the right-hand side, it is easy to verify that the statement is true. Now define.. $\mu=\alpha-\sigma^{2}/2$ and the statement can be written as. $1+$ $\left[\mu d t+\sigma d W+\left(\mu d t+\sigma d W\right)^{2}/2\right]\protect$ , which is equivalent to a second-order Taylor series expansion of the functiond $e^{\mu d t+\sigma d\mathbb{W}}$ : A second-order expansion is sufficient because alle terms higher than second order will involve powers of. $d t$ greater than 1.0.

Now we can write out the stochastic process as. $d S+S=S e^{\mu d t+\sigma d W}$ Dividing by $S$ we obtain $d S/S+1=e^{\mu d t+\sigma d W}$ . Taking natural logs, we have the stochastic process of the log return on the asset,.

$$
\ln\left({\frac{d S+S}{S}}\right)=\mu d t+\sigma d W.
$$

This result confirms that the log return is normally distributed with mean $\mu$ and volatility $\sigma$ . For our purposes here, we use the following version,.

$$
d S+S=S e^{\mu d t+\sigma d\mathrm{\bfW}}.
$$

Noting that the time increment until expiration is $\tau$ , we can state that the asset price. at expiration is $S_{t+\tau}=S_{T}$ and the stochastic process for. $\boldsymbol{W}$ is $\Delta W_{T}=\varepsilon^{*}\sqrt{\tau}$ . Thus,

$$
S_{T}=S_{t}e^{\mu\tau+\sigma\varepsilon^{\ast}\sqrt{\tau}},
$$

with $\Delta{{W}_{T}}$ normally distributed with mean zero and variance $\tau$ , per the central limit. theorem.10

Our objective is to evaluate the expectation of $c_{T}$ . By definition,.

$$
E_{t}^{Q}\big(c_{T}\big)=\int_{X}^{\infty}\left(S_{T}-X\right)f\big(S_{T}\big)d S_{T},
$$

where $f(S_{T})$ is the density for $S_{T}$ . Note that we need integrate only over the interval $(X,\infty)$ because $c_{T}=0$ for $0\le S_{T}\le X$ Thus,.

$$
\begin{array}{c}{{\displaystyle{E_{t}^{Q}\left(c_{T}\right)=\int_{X}^{\infty}S_{T}f\left(S_{T}\right)d S_{T}-\int_{X}^{\infty}X f\left(S_{T}\right)d S_{T}}}}\ {{\displaystyle{{X}}}}\ {{\displaystyle{{\quad=\int_{X}^{\infty}S_{T}f\left(S_{T}\right)d S_{T}-X\mathrm{Pr}^{Q}\left(S_{T}>X\right),}}}}\end{array}
$$

where $\mathrm{Pr}^{\mathrm{Q}}$ is the probability under the risk neutral or equivalent martingale measure that $S_{T}>X$ . The overall expression is the expected value of $S_{T}$ given that $S_{T}>X$ minus the expected payout of the exercise price, that is, the exercise price times the probability that the option will be exercised. That is, for the entire expression,

$$
E_{t}^{Q}\left(c_{T}\right)=E_{t}^{Q}\left(S_{T}|S_{T}>X\right)\mathrm{Pr}^{Q}\left(S_{T}>X\right)-X\mathrm{Pr}^{Q}\left(S_{T}>X\right).
$$

Starting with the simpler case, let us first evaluate the second term on the right-hand side. By definition,

$$
\mathrm{Pr}^{\mathcal{Q}}\left(S_{T}>X\right)=\mathrm{Pr}^{\mathcal{Q}}\left(S e^{\mu\tau+\sigma\varepsilon^{*}{\sqrt{\tau}}}>X\right).
$$

Note that $S e^{\mu\tau+\sigma\varepsilon^{*}{\sqrt{\tau}}}>X$ is equivalent to $\ln(S/X)+\mu\tau+\sigma\varepsilon^{*}{\sqrt{\tau}}>0$ or

$$
\varepsilon^{*}>-{\frac{\left[\ln(S/X)+\mu\tau\right]}{\sigma{\sqrt{\tau}}}}.
$$

Recall that $\alpha$ is the expected simple return on the asset and $\mu$ is the expected logarithmic return on the asset where $\mu=\alpha-\sigma^{2}/2$ . Under the equivalent martingale/risk neutrality approach, we can let $\alpha=r_{c}$ so that $\mu=r_{c}-\sigma^{2}/2$ so that

$$
\varepsilon^{*}>-\frac{\left[\ln(S/X)+\left(r_{c}-\sigma^{2}/2\right)\tau\right]}{\sigma\sqrt{\tau}}.
$$

You should recognize this as $\varepsilon^{*}>-d_{2}$ or $\varepsilon^{*}<d_{2}$ . So our second term in (13.25) is

$$
\varepsilon^{*}>-\frac{\left[\ln(S/X)+\left(r_{c}-\sigma^{2}/2\right)\tau\right]}{\sigma\sqrt{\tau}}\Rightarrow N\left(d_{2}\right).
$$

Now we look at the first term on the right-hand side of (13.25). It can be written as

$$
\begin{array}{r l r}{\lefteqn{\int_{X}^{\infty}}S_{T}f(S_{T})d S_{T}=\int_{X}^{\infty}S e^{\mu\tau+\sigma\varepsilon^{*}\sqrt{\tau}}f(S_{T})d S_{T}}}\ &{X}&\ &{}&{\quad=S e^{\mu\tau}\displaystyle\int_{X}^{\infty}e^{\sigma\varepsilon^{*}\sqrt{\tau}}f(S_{T})d S_{T}.}\end{array}
$$

We showed that $S_{T}>X$ implies that $\varepsilon^{*}>d_{2}$ and $\varepsilon^{*}>-d_{2}$ so we can change the variable of integration giving us the equivalent statement,

$$
S e^{\mu\tau}\int_{-d_{2}}^{\infty}e^{\sigma\varepsilon^{*}{\sqrt{\tau}}}f(\varepsilon^{*})d\varepsilon^{*}.
$$

Because $\varepsilon^{*}$ is normally distributed, we can substitute the density for the normal distribution,

$$
\begin{array}{r l}&{S e^{\mu\tau}\displaystyle\int_{-d_{2}}^{\infty}e^{\sigma\varepsilon^{*}\sqrt{\tau}}\left(e^{-{\varepsilon^{*}}^{2}/2}/\sqrt{2\pi}\right)d\varepsilon^{*}}\ &{\quad\quad\quad=S e^{\mu\tau}\displaystyle\int_{-d_{2}}^{\infty}\left(e^{-{\varepsilon^{*}}^{2}/2+\sigma\varepsilon^{*}\sqrt{\tau}}/\sqrt{2\pi}\right)d\varepsilon^{*}.}\end{array}
$$

By completing the square in the exponent, we obtain

$$
S e^{\mu\tau}\int_{-d_{2}}^{\infty}\left(e^{-\left(\varepsilon^{*}-\sigma\sqrt{\tau}\right)^{2}/2+\sigma^{2}\tau/2}/\sqrt{2\pi}\right)d\varepsilon^{*}.
$$

Now we make a change of variables. Let. $y=\varepsilon^{*}-\sigma{\sqrt{\tau}}$ so that $\varepsilon^{*}=\sigma\sqrt{\tau}+y$ This changes the lower limit of integration. Formerly, we were interested in the value of $\varepsilon^{*}$ over the range $(-d_{2},\infty)$ . Because $d_{2}=d_{1}-\sigma{\sqrt{\tau}}$ , this means that $\varepsilon^{*}>-\left(d_{1}-\sigma{\sqrt{\tau}}\right)$ or $\varepsilon^{*}>\sigma\sqrt{\tau}-d_{1}$ Substituting $y+\sigma{\sqrt{\tau}}$ for $\varepsilon^{*}$ means that $y+\sigma{\sqrt{\tau}}>\sigma{\sqrt{\tau}}-d_{1}$ ; thus, $y<d_{1}$ . Now our expression can be written as.

$$
S e^{\mu\tau+\sigma^{2}\tau/2}\int_{-\infty}^{d_{1}}\left(e^{-y^{2}/2}/\sqrt{2\pi}\right)d y.
$$

The integral is simply the value $N(d_{1})$ . Because $\mu+\sigma^{2}/2=r_{c}$ , our first term can be written as $S e^{r_{c}\tau}\bar{N}(d_{1}).$ Thus,

$$
E_{T}^{Q}\left(c_{T}\right)=S e^{r_{c}\tau}N(d_{1})-X N(d_{2}).
$$

And the value of the call today is the present value of $E_{T}^{Q}\left[c_{T}\right]$ obtained using the factor $e^{-r_{c}\tau}$ . Thus, we obtain the model,

$$
\begin{array}{r}{c=S N\big(d_{1}\big)-X e^{-r_{c}\tau}N\big(d_{2}\big),}\end{array}
$$

which is the Black-Scholes-Merton formula.

This derivation makes it somewhat easier to see the proper interpretation of the normal probabilities, $N(d_{1})$ and $N(d_{2}).N(d_{2})$ is the probability that the call will be exercised.

provided one assumes that the asset expected return is the risk-free rate. Of course, any risky asset will command a risk premium so the actual drift is $\alpha$ , which is higher than $r$ by the risk premium. Consequently, the actual probability of exercise is higher than $N(d_{2}).N(d_{1})$ , however, does not lend itself to a simple probability interpretation. $S N(d_{1})$ is interpreted as the expected asset price at expiration conditional on the asset price exceeding the exercise price, times the probability that the asset price exceeds the exercise price, discounted at the risk-free rate.

# 13.4DERIVING THE BLACK-SCHOLES-MERTON MODEL AS THE SOLUTION OF A PARTIAL DIFFERENTIAL EQUATIONS

The mathematical details that lead from the partial differential equation (PDE),.
Equation (13.11), to the Black-Scholes-Merton formula, Equation (13.12), are seldom seen.
in print. One exception is Kutner (1988). This section is adapted from that article. There.
are a few other sources of derivations, which are listed in the references, that take a slightly different approach. We refer to this general solution methodology as the PDE.
approach.

Solving a differential equation frequently involves guessing at the form of the solution.. Some clues as to the correct form were provided in the research on options that preceded Black, Scholes, and Merton. Assuming we do not yet know the solution, let us propose. that it can be written as $c_{t}=e^{-r_{c}\tau}y$ where $y=f(u,q)$ . You can see here that $y$ seems to play the role of the payoff, which is a function of two variables. The variables. $\boldsymbol{\mathscr{u}}$ and $q$ are proposed to be of the form,11

$$
\begin{array}{l}{{u=\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)\left[\ln(S/X)-\left(r_{c}-\sigma^{2}/2\right)(-\tau)\right]}}\ {{{}}}\ {{q=-\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)^{2}(-\tau).}}\end{array}
$$

The partials of $c_{t}=e^{-r_{c}\tau}y(u,q)$ are found as

$$
\begin{array}{l}{\displaystyle\frac{\partial c}{\partial S}=e^{-r_{c}\tau}y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)/S}\ {\displaystyle}\ {\displaystyle\frac{\partial c}{\partial t}=e^{-r_{c}\tau}\left[-y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)^{2}-y_{q}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)^{2}+r_{c}y\right]}\ {\displaystyle\frac{\partial^{2}c}{\partial S^{2}}=e^{-r_{c}\tau}\left[y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)\left(1/S^{2}\right)-y_{q}\left(2/\sigma^{2}\right)^{2}\left(r_{c}-\sigma^{2}/2\right)^{2}\left(1/S^{2}\right)y_{u u}\right],}\end{array}
$$

where $y_{u},y_{q}$ , and $y_{u u}$ are shorthand notation for $\partial y/\partial u,\partial y/\partial t$ and $\partial^{2}y/\partial u^{2}$ . Note that $\partial t=-\partial\tau$ . Substituting into the Black-Scholes-Merton PDE gives

$$
\begin{array}{r l}&{r S e^{-r\tau}y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)/S_{t}-r_{c}c_{t}}\ &{+e^{-r\tau}\Big[y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)^{2}-y_{q}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)^{2}+r_{c}y\Big]}\ &{+\displaystyle\frac12e^{-r\tau}\Big[y_{u}\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)\left(1/S^{2}\right)+\left(2/\sigma^{2}\right)^{2}\left(r_{c}-\sigma^{2}/2\right)^{2}\left(1/S^{2}\right)y_{u u}\Big]=0,}\end{array}
$$

which simplifies to

$$
y_{q}=-y_{u u}.
$$

This is the heat exchange equation of thermodynamics. The solution is well known, and Black and Scholes cite a contemporary math book. If $V$ is a function of. $x$ and $t$ and $V_{t}=$ $K V_{x x}$ for $-\infty<x<\infty$ $t>0$ and $V=f(x)$ when $t=0$ for $-\infty<x<\infty$ , the solution is of. the form

$$
V={\frac{1}{\sqrt{\pi}}}\int_{-\infty}^{\infty}f\left(x+2\eta{\sqrt{k t}}\right)e^{-\eta^{2}}d\eta.
$$

In our problem, $V$ is the option price, $x$ is $\boldsymbol{\mathscr{u}}$ $t$ is $q,k=1$ , and $f(x)$ is the boundary condition. The variable $q$ can equal zero only at expiration $\mathbf{\chi}_{\tau}^{\prime}=0$ ). We need to find the function $f(x)$ consistent with the option's expiration value:

$$
\begin{array}{r l}{y(u,0)=c\big(S_{T},0\big)=S_{T}-X}&{i f~S_{T}\geq X}\ {=0}&{i f~S_{T}<X.}\end{array}
$$

Let

$$
\begin{array}{r l r}{y(u,0)=X\Bigg(e^{u\left(\sigma^{2}/2\right)\left/\left(r-\sigma^{2}/2\right)\right.}-1\Bigg)}&{{}i f u\geq0}\ {~}&{{}i f u<0.}\end{array}
$$

At $\tau=0$ $\boldsymbol{\mathscr{u}}$ will equal $\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)\ln\left(S_{T}/X\right)$ . So at $\tau=0$

$$
\begin{array}{r l r}&{}&{y(u,0|\tau=0)=X\Big(e^{\ln\left(S_{T}/X\right)}-1\Big)=S_{T}-X}&{i f~u\geq0}\ &{}&{=0}&{i f~u<0.}\end{array}
$$

Thus,e $y(u,0)\mid\tau=0$ is consistent with $c(S_{T},0)$ . A function $f(x)$ that meets this condition is

$$
\begin{array}{r l r}{f(u)=X\Bigg(e^{u\left(\sigma^{2}/2\right)/\left(r-\sigma^{2}/2\right)}-1\Bigg)}&{{}i f u\geq0}\ {~}&{{}i f u<0.}\end{array}
$$

The solution is, thus,

$$
y={\frac{1}{\sqrt{\pi}}}\int_{-u/2\sqrt{q}}^{\infty}X\left[e^{\left(u+2\eta\sqrt{q}\right)\left(\sigma^{2}/2\right)/\left(r_{c}-\sigma^{2}/2\right)}-1\right]e^{-\eta^{2}}d\eta.
$$

The lower limit was changed from $-\infty$ to $-u/2\sqrt{q}$ , because we require the integrand to be nonnegative to get a positive value of $y$ . Thus, the first exponential function must be greater than or equal to one. So the exponent must be restricted to $\left(u+2\eta{\sqrt{q}}\right)\geq0$ , meaning that

$\eta\ge-u/2\sqrt{q}$ Now let $\eta=a\sqrt{2}/2$ . We will have $-\eta^{2}=-a^{2}/2,d\eta=d a/\sqrt{2}$ , and the lower limit of integration will change to $-u/\sqrt{2q}$ Then the equation will become

$$
y=\int\displaylimits_{-u/2\sqrt{q}}^{\infty}\frac{1}{\sqrt{\pi}}X\left[e^{\left(u+a\sqrt{2q}\right)\left(\sigma^{2}/2\right)/\left(r_{c}-\sigma^{2}/2\right)}-1\right]e^{-a^{2}/2}d a.
$$

Now note that $-u/\sqrt{2q}=(1/\sigma)\left[\ln(S/X)-\left(r_{c}-\sigma^{2}/2\right)(-\tau)\right]/\sqrt{\tau}=-d_{2}/\tau$ Next, we transform the equation back into the equation for $c_{t}$ by multiplying by. $e^{-r_{c}\tau}$ , and then we. separate the integrals:

$$
\begin{array}{l}{{\displaystyle c=\int_{-d_{2}}^{\infty}\frac{1}{\sqrt{2\pi}}X e^{-r\tau}\left[e^{(u+2a\sqrt{q})\left(\sigma^{2}/2\right)/\left(r_{c}-\sigma^{2}/2\right)}-1\right]e^{-a^{2}/2}d a}}\ {{\mathrm{}~}}\ {{\displaystyle~=\int_{-d_{2}}^{\infty}\frac{1}{\sqrt{2\pi}}X e^{-r\tau}e^{\left[{\frac{\left(u+2a\sqrt{q}\right)\left(\sigma^{2}/2\right)\left(r_{c}-\sigma^{2}/2\right)}{\sqrt{2}\pi}}\right]-a^{2}/2}d a-X e^{-r\tau}\int_{-d_{2}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-a^{2}/2}d a.}}\end{array}
$$

The first term can be simplified by using the definitions of $\boldsymbol{\mathscr{u}}$ and $q$ . After rearranging those definitions, we have

$$
\begin{array}{c}{{u\left(2/\sigma^{2}\right)\left(r_{c}-\sigma^{2}/2\right)=\left[\ln(S/X)-\left(r_{c}-\sigma^{2}/2\right)(-\tau)\right]}}\ {{{}}}\ {{a\sqrt{2q}(1/\sigma^{2})\left(r_{c}-\sigma^{2}/2\right)=-a\sigma\sqrt{\tau}.}}\end{array}
$$

Thus, the first term in our solution is

$$
\begin{array}{l}{{\displaystyle{X e^{-r_{c}\tau}e^{\ln(S/X)}\int_{-d_{2}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{r\tau}e^{-\left[a^{2}/2-a\sigma\sqrt{\tau}+\sigma^{2}\tau\right]}d a}}}\ {{\displaystyle{}}}\ {{\displaystyle{=S\int_{-d_{2}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-(1/2)\left[a^{2}-2a\sigma\sqrt{\tau}+\sigma^{2}\tau\right]}d a.}}}\end{array}
$$

The integrand is $e^{-(1/2)(a-\sigma{\sqrt{\tau}})^{2}}$ . Now define $b=a-\sigma{\sqrt{\tau}}$ so $d b=d a$ and the lower limit of integration becomes $-d_{2}-\sigma\sqrt{\tau}$ Let $d_{1}=d_{2}+\sigma{\sqrt{\tau}}$ so we have

$$
S\int_{-d_{1}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-b^{2}/2}d b,
$$

which is simply $S\big[1-N\big(-d_{1}\big)\big]=S N\big(d_{1}\big)$

The second term in the solution is simply $-X e^{-r_{c}\tau}\big[1-N\big(-d_{2}\big)\big]=-X e^{-r_{c}\tau}N\big(d_{2}\big).$ Thus,e

$$
\begin{array}{r}{c=S N\big(d_{1}\big)-X e^{-r_{c}\tau}N\big(d_{2}\big),}\end{array}
$$

which is the Black-Scholes-Merton formula.

An alternative route to the solution uses the LaPlace transform on the partial differential equation. This converts it to an ordinary differential equation, for which standard solution techniques can be applied.

Wilmott, Howison, and DeWynne (1995) have an excellent illustration of the steps in. converting the Black-Scholes-Merton PDE into the heat transfer equation of physics and then solving that equation to obtain the option pricing formula..

Thus, we have two approaches to arriving at the Black-Scholes-Merton model, the. expectations approach and the PDE approach. The Feynman-Kac theorem provides a convenient methodology for moving between these two approaches. Although we have solution methodologies for both the expectations approach as well as the PDE approach with the Black-Scholes-Merton model, there are other more complicated models where one approach may be less complicated than the other. Once, say the PDE is derived based on arbitrage arguments, we can easily transform the problem to taking an expectation via the Feynman-Kac theorem.

The generic univariate Feynman-Kac theorem is briefly introduced here. Recall the Ito. process parameters can depend on at most the underlying variable and time, represented here as $x$ and $t$ Thus, the PDE parameters have the same constraint. The PDE parameters. also depend on at most $x$ and $t.$ The three parameters associated with the PDE are expressed as $\mu(x,t),{\widehat{\mu}}(x,t)$ , and $\widehat{\sigma}(x,t)$ . Formally, the Feynman-Kac theorem can be expressed as. follows:

Assume a univariate Ito process expressed generically as

$$
d x=\mu(x,t)d t+\sigma(x,t)d z.
$$

Subject to certain technical conditions, we have the following statement:

$$
\mu(x,t)f=\frac{\partial f}{\partial t}+\widehat{\mu}(x,t)\frac{\partial f}{\partial x}+\frac{1}{2}\widehat{\sigma}^{2}(x,t)\frac{\partial^{2}f}{\partial x^{2}},
$$

subject to

$$
f(x,T)=f\left(x_{T}\right),
$$

if and only if

$$
f(x,t)=E_{\widehat{\mu},\widehat{\sigma}^{2}}\left[f\big(x_{T}\big)e^{-\int_{t}^{T}\mu\big(x_{y},y\big)d y}\right].
$$

Thus, the Feynman-Kac theorem provides a straightforward linkage between the expectations approach (Equation (13.57)) and the PDE approach (Equation (13.55) with boundary condition Equation (13.56)) to various option valuation problems, including the Black-Scholes-Merton model. The discounting $\left(e^{-\int_{t}^{T}\mu\left(x_{y},y\right)d y}\right)$ in Equation (13.57)

is based on the parameter on the left-hand side of Equation (13.55),. $\mu(x,t)$ . In the Black-Scholes-Merton model, it is simply $r_{c}$ . The expectation is taken based on the remaining two parameters from the PDF. In the Black-Scholes-Merton model, for example, ${\widehat{\mu}}(x,t)=\mu S$ and $\widehat{\sigma}(x,t)=\sigma S$

We now illustrate the application of the Feynman-Kac theorem within our context. here. Based on assuming geometric Brownian motion for the underlying asset, we have the following result. The Black-Scholes-Merton PDE of.

$$
r_{c}S\frac{\partial c}{\partial S}+\frac{\partial c}{\partial t}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}\sigma^{2}S^{2}=r_{c}c,
$$

subject to

$$
c(S,T)=\operatorname*{max}\bigl(0,S_{T}-X\bigr),
$$

if and only if

$$
c(S,t)=e^{-r_{c}(T-t)}E_{r_{c},\sigma}\left[\operatorname*{max}\bigl(0,S_{T}-X\bigr)\right].
$$

Due to the lognormal distribution assumption, we know

$$
S_{T}=S_{t}e^{\left(r_{c}-\frac{\sigma^{2}}{2}\right)\left(T-t\right)+\sigma\sqrt{T-t}\varepsilon},
$$

where $\varepsilon$ is distributed normal with mean O and standard deviation 1.

Based on the previous two sections, we know that both approaches result in the Black-Scholes-Merton model.

# 13.5DECOMPOSING THE BLACK-SCHOLES-MERTON MODEL INTO BINARY OPTIONS

Recall in Chapter 7, we introduced binary options, asset-or-nothing options and cash-or-. nothing options. We can obtain the value of an asset-or-nothing call by using the method of expectations, as covered in Section 13.4. Recall that we derived the Black-Scholes-Merton. model and found that it has two components, $S N(d_{1})$ and $X e^{-r_{c}\tau}N(d_{2})$ . The first represents the expected value of the underlying asset at expiration conditional on the value of. the underlying asset exceeding the exercise price times the probability that the value of the underlying asset exceeds the exercise price, discounted to the present at the risk-free rate.. The second equals the discounted value of a payoff of. $X$ at expiration provided that the. price of the underlying asset exceeds the exercise price. $X$ .The payoff of the first compo-. nent is precisely that of an asset-or-nothing call, and the payoff of the second is precisely the payoff of a cash-or-nothing call. Therefore, as explained in Chapter 7, a standard. European option can be viewed as a long position in an asset-or-nothing call and a short position in a cash-or-nothing call both struck at. $X$ and the latter paying X.12 Similarly, a. standard European put can be decomposed into a long position in a cash-or-nothing put. and a short position in an asset-or-nothing put..
