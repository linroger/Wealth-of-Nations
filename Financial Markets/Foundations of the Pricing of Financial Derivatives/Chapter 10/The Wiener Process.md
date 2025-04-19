---
tags:
  - '#asset_pricing_model'
  - '#brownian_motion'
  - '#expected_value'
  - '#ito_calculus'
  - '#option_pricing'
  - '#stochastic_integral'
  - '#variance'
  - '#wiener_process'
---
# 10.2 THE WIENER PROCESS

The process we have been working with is often called a standard Brownian motion or just Brownian motion. Now let us take the difference between $\mathbf{\boldsymbol{W}}_{t+\Delta t}$ and $\mathbf{}\mathbf{}{W}_{t}$ and denote it as $d\mathbb{W}_{t}$ , which will be defined as

$$
d\mathbb{W}_{t}=\varepsilon_{t}{\sqrt{d t}}.
$$

This process, the increment to the standard Brownian motion, is called a Wiener process, named after the American mathematician, Norbert Wiener (1894-1964), who did important work in this area. In option pricing, we are more interested in the process $d\mathbb{W}_{t}$ than in the process $\mathbf{}\mathbf{}{W}_{t}$ . We shall transform $d\mathbb{W}_{t}$ into something more useful for modeling asset prices at a later point.1

It is important to note that the mathematics necessary to define the expected value. and variance require the mathematical technique of integration. The ordinary rules of integration, however, do not automatically apply when the terms are stochastic. Fortunately, work by the Japanese mathematician Kiyoshi Ito (1915-2008), who did most of his work at the University of Kyoto, proved that the integral, defined as a stochastic integral, does exist though with a slightly different definition. This branch of mathematics is often called Ito calculus. Consequently, many of the rules of ordinary integration apply in similar or. slightly different forms. We cover this material in Chapter 11..

First, let us look at some simple characteristics of the Wiener process. For starters, let us take the expected value,

$$
E\big(d W_{t}\big)=E\Big(\varepsilon_{t}\sqrt{d t}\Big)=\sqrt{d t}E\big(\varepsilon_{t}\big)=0.
$$

Now we take the variance,

$$
\mathop{\mathrm{var}}\left(d W_{t}\right)=E\Bigl(\varepsilon_{t}\sqrt{d t}\Bigr)^{2}-\left[E\Bigl(\varepsilon_{t}\sqrt{d t}\Bigr)\right]^{2}=d t E\bigl(\varepsilon_{t}^{2}\bigr)-0=d t.
$$

Note that $E\big(\varepsilon_{t}^{2}\big)=1$ because $\mathrm{var}\bigl(\varepsilon_{t}\bigr)=1=E\bigl(\varepsilon_{t}^{2}\bigr)-E\bigl(\varepsilon_{t}\bigr)^{2}$ and $E\big(\varepsilon_{t}\big)=0$

One interesting property of the Wiener process is that when you square it, it becomes. perfectly predictable. This point seems very enigmatic. How can you generate random numbers, square them, and find them perfectly predictable? Let us see..

Suppose we draw a standard normal random variable, $\varepsilon_{t}$ . Then we multiply it by the square root of the time interval $d t.$ We know that this transformed value is unpredictable, but we know its expected value and its variance. The expected value is obviously zero. Using the rule that the variance of a constant times a random variable is the constant squared times the variance of the random variable, we see that its variance is dt.2

If, however, we define the variable of interest as. $\boldsymbol{d}\boldsymbol{\mathbb{W}}_{t}^{2}$ , we get an important result. To determine $\boldsymbol{d}\boldsymbol{\mathbb{W}}_{t}^{2}$ we simply draw the value of $\varepsilon_{t}$ , multiply it by the square root of $d t$ and square the entire expression to obtain. $\varepsilon_{t}^{2}d t$ . The variance of this expression is found by squaring $d t$ and multiplying by the variance of. $\varepsilon_{t}^{2}$ . By definition, however, all values of. $d t^{k}$ where $k>1$ are zero. In other words, the length of the time interval is so short that raising it to a power more than one makes it shorter and effectively zero. The expected value of $d\mathbb{W}_{t}^{2}$ is the expected value of $\varepsilon_{t}^{2}d t$ which will be dt times the expected value of $\varepsilon_{t}^{2}$ . So now we must evaluate $E\big(\varepsilon_{t}^{2}\big)$ . We did that to get Equation (10.4). Thus, $E\Big(d W_{t}^{2}\Big)=1^{*}d t=$ dt. Because $d t^{2}=0$ then var $\left(d\mathbf{W}_{t}^{2}\right)=0$ and $E\Big(d W_{t}^{2}\Big)=d W_{t}^{2}=d t$ In other words, any variable that has zero variance can be expressed as its expected value. We see that our intuitively unusual result is that although $d\mathbb{W}_{t}$ is random, its square is not. So, remember this important result:

$$
{d W_{t}}^{2}=d t.
$$

We shall see it again.

Why do these things matter? They are the foundations of the most fundamental model used to price options. Let us look at how this process can be used to model movements in the price of an asset. For convenience, this asset could be a stock, currency, or commodity.
