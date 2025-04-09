# 32.4 PROBABILITY OF EXERCISE

It is well known that the risk-neutral probability of exercise of the spot call option is $N(d_{2}^{D})$ and correspondingly the risk-neutral probability of exercise of the spot put option .5 $N\bar{(}-d_{2}^{D})$ . For spot calls, this is the risk-neutral probability that $S_{T}>X$ The corresponding probability for exercise of the reciprocal put is the probability that $1/S_{T}<1/X$ which must be the same as the probability that $S_{T}>X$ Thus, $N(d_{2}^{D})$ is the risk-neutral probability of exercise of the call, and this equals $N(-d_{1}^{F})$ , which is the probability of exercising the reciprocal put. Note that the probability of exercising the reciprocal put is not the term in the BSM put formula that is multiplied by the present value of $1/X$ or $N(-d_{2}^{F})$ . There is an important reason for that, which will become clearer when we examine the actual, as opposed to risk-neutral, probability of exercise.

Let the true stochastic process for $S$ be given as

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d\mathrm{{W}}_{t}.
$$

Here $\alpha$ and $\sigma$ are the expected return and volatility of. $d S_{t}/S_{t}$ . It is important to remember. that the stochastic process for the log return is

$$
d\ln S_{t}=\mu d t+\sigma d W_{t},
$$

with the log expected return given as

$$
\mu=\alpha-\sigma^{2}/2,
$$

which holds by definition for normal distributions.

Now we need the stochastic process of the reciprocal exchange rate. We will apply Ito's lemma for the reciprocal exchange rate, $R_{t}=1/S_{t}$ . Thus, we will need certain partial. derivatives:

$$
\frac{\partial R_{t}}{\partial S_{t}}=-\frac{1}{S_{t}^{2}}
$$

$$
\frac{\partial^{2}R_{t}}{\partial S_{t}^{2}}=\frac{2}{S_{t}^{3}}
$$

$$
\frac{\partial R_{t}}{\partial t}=0.
$$

Now, applying Ito's lemma to $R_{t}$

$$
d R_{t}=\frac{\partial R_{t}}{\partial S_{t}}d S_{t}+\frac{\partial R_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}R_{t}}{\partial S_{t}^{2}}d S_{t}^{2}.
$$

Substituting Equations (32.17) and (32.20), and using the fact that $d S_{t}^{2}=S_{t}^{2}\sigma^{2}d t$ we obtain

$$
\begin{array}{r}{d R_{t}=\displaystyle\left(\frac{1}{S_{t}}\right)\left(-\alpha d t-\sigma d W+\sigma^{2}d t\right)}\ {=\displaystyle\left(\frac{1}{S_{t}}\right)\left[\left(-\alpha+\sigma^{2}\right)d t-\sigma d W\right].}\end{array}
$$

Dividing by $R_{t}$ and multiplying by $S_{t}$ , we obtain

$$
\frac{d R_{t}}{R_{t}}=\left(-\alpha+\sigma^{2}\right)d t-\sigma d{\mathrm{W}}_{t}.
$$

Thus, the expected return on the reciprocal exchange rate is $-\alpha+\sigma^{2}$ . Note, however, the minus term on the volatility, which contributes to the reason why the probability of exercise of the put is not given by the. $N\big(-d_{2}\big)$ term in its formula, as it usually is in the BSM. model.4

The log return on $R_{t}$ is

$$
-\alpha+\sigma^{2}-\sigma^{2}/2=-\alpha+\sigma^{2}/2.
$$

Substituting for $\alpha$ , this can then be expressed as

$$
-\alpha+\sigma^{2}/2=-\left(\mu-\sigma^{2}/2\right)+\sigma^{2}/2=-\mu.
$$

This is the term that must be inserted into the formula for the normal probability.5 It is the expected log return on $R_{t}$ expressed in terms of the log return on $S_{t}$ . Making the substitution into $-d_{1}^{F}$ , and using $a^{*}$ to denote that we are dealing with the true probability distribution, not the risk-neutral distribution, we have.

$$
\begin{array}{r l}&{N\Big(-d_{1}^{F^{*}}\Big)=N\Bigg[-\frac{\ln\big(R_{0}/X_{R}\big)+\big(-\mu+\sigma^{2}/2\big)\tau}{\sigma\sqrt{\tau}}\Bigg]=N\Bigg[-\frac{\ln\big(X/S_{0}\big)+\big(-\mu+\sigma^{2}/2\big)\tau}{\sigma\sqrt{\tau}}\Bigg]}\ &{\quad\quad=N\Bigg[\frac{-\ln\big(X/S_{0}\big)+\big(\mu-\sigma^{2}/2\big)\tau}{\sigma\sqrt{\tau}}\Bigg]=N\Bigg[\frac{\ln\big(S_{0}/X\big)+\big(\mu-\sigma^{2}/2\big)\tau}{\sigma\sqrt{\tau}}\Bigg].\quad(32)}\end{array}
$$

This is, of course, $N(d_{2}^{D^{*}})$ because

$$
d_{2}^{D^{*}}=\frac{\ln\left(S_{0}/X\right)+\left(\mu-\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}.
$$

Thus, we see $N(d_{2}^{D^{*}})$ is the risk-neutral probability of exercise of the call, and this equals $N(-d_{1}^{F^{*}})$ , which is the probability of exercising the reciprocal put.
