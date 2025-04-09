# 29.4 STATE PRICING AND OPTIONS IN A BINOMIAL FRAMEWORK

In this section, we draw on the work of Banz and Miller (1978) and Breeden and Litzenberger (1978). Consider a one-period binomial option pricing world. Let an asset worth $V$ today be worth either $V u$ or $V d$ one period later, where $\boldsymbol{\mathscr{u}}$ and $d$ are one plus the return on the asset in each of the two outcomes. From what we have previously learned about state pricing, we know that. $V$ must be $V u\psi_{1}+V d\psi_{2}$ . Let us divide through by. $V$ and also specify the formula for the risk-free rate in terms of the state prices:

$$
\begin{array}{l}{{1=u\psi_{1}+d\psi_{2}}}\ {{{}_{r=}\left(\displaystyle\frac{1}{\psi_{1}+\psi_{2}}\right)-1.}}\end{array}
$$

Solving these equations simultaneously for $\psi_{1}$ and $\psi_{2}$ , we obtain

$$
\begin{array}{l}{\displaystyle\psi_{1}=\frac{1+r-d}{(1+r)(u-d)}}\ {\displaystyle\psi_{2}=\frac{u-(1+r)}{(1+r)(u-d)}.}\end{array}
$$

You should note the similarity of these formulas to those of the binomial probability for $\phi$ and $1-\phi$ , which is repeated here:

$$
\begin{array}{c}{\displaystyle{\phi=\frac{1+r-d}{(u-d)}}}\ {\displaystyle{1-\phi=\frac{u-(1+r)}{(u-d)},}}\end{array}
$$

Compare the formula for $\phi$ in Equation (29.17), which is the risk-neutral probability of. the asset going up, to the formula for $\psi_{1}$ , which is the price for the state in which the asset goes up. Note that. $\psi_{1}=\phi/(1+r)$ . Usually when we obtain the value of $\phi$ we determine $1-\phi$ by simple subtraction, but it can be shown that $1-\phi=(u-(1+r))/(u-d)$ . Then,. it is easily seen that. $\psi_{2}=(1-\phi)/(1+r)$ . Thus, in general, the state price is the risk-neutral probability discounted at the risk-free rate. Alternatively, if we are given the risk-free rate, we can easily solve for the state prices as

$$
\begin{array}{l}{\displaystyle\psi_{1}=\frac{p}{1+r}}\ {\displaystyle\psi_{2}=\frac{1-p}{1+r}.}\end{array}
$$

We know that we can obtain the price of a call option on this asset with an exercise price of $X$ by using the standard binomial pricing formula from Chapter 7,.

$$
c=\frac{\phi c_{u}+(1-\phi)c_{d}}{1+r},
$$

where $c_{u}=\operatorname*{max}(0,S u-X)$ and $c_{d}=\operatorname*{max}(0,S d-X)$ Let us demonstrate these results with an example. Consider the following scenario. We have an asset priced at 100 that can go up to either 140 or down to 75 in the next period. Thus, $u=140/100=1.40$ and $d=$ $75/100=0.75.$ The risk-free rate is $3\%$ . Using the standard binomial pricing approach, we first calculate the risk-neutral probability as

$$
\phi=\frac{1.03-0.75}{1.40-0.75}=0.4308.
$$

And, of course,. $1-\phi=0.5692$ . The payoffs of the call are obviously 40 and 0. The call price today is found as.

$$
c=\frac{0.4308(40)+0.5692(0)}{1.03}=16.73.
$$

Now let us look at how this problem is consistent with state pricing. Given the risk-neutral probabilities of 0.4308 and 0.5692, we can find the state prices as

$$
\begin{array}{l}{\displaystyle{\psi_{1}=\frac{0.4308}{1.03}=0.4182}}\ {\displaystyle{\psi_{2}=\frac{0.5692}{1.03}=0.5527.}}\end{array}
$$

The call price in terms of state prices is

$$
c=c_{u}\psi_{u}+c_{d}\psi_{d}.
$$

Substituting for our numerical example, we arrive at the previous value of

$$
c=40(0.4182)+0(0.5527)=16.73.
$$

We have three financial instruments: a stock, an option, and a riskless bond. To obtain the state prices from the prices of the complex assets, we need as many instruments as there are states. Thus, we need only two of the three assets at a time. Using the formulas, we previously developed, we shall re-derive the state prices, which should be 0.4182 and. 0.5527. Let us first use the stock and risk-free bond. We can set the price of the risk-free. bond to anything as long as its payoff is $3\%$ higher than its price. Let us just set it at 100, the same as the stock price. Then our $\mathbf{H}$ matrix is

$$
\begin{array}{r}{\bf{H}=\left|_{103}^{103}\right.\left.^{140}\right|.}\end{array}
$$

Our S vector, the prices of the assets, is

$$
\mathsf{S}=\left|^{100}_{100}\right|.
$$

Then performing the matrix operations $(\mathbf{H}^{\prime})^{-1}\mathbf{S}$ , we obtain

$$
\Psi=\left|\begin{array}{c c}{{-0.0112}}&{{0.0154}}\ {{0.0209}}&{{-0.0154}}\end{array}\right|\left|\begin{array}{c}{{100}}\ {{100}}\end{array}\right|=\left|\begin{array}{c}{{0.4182}}\ {{0.5527}}\end{array}\right|,
$$

which are the correct values for the state prices.

Alternatively, we could use the option and the stock. Then our $\mathbf{H}$ matrix would be

$$
{\bf H}=\left|{\begin{array}{c c}{{40}}&{{140}}\ {{0}}&{{75}}\end{array}}\right|.
$$

Our S vector would be

$$
\begin{array}{r}{\mathbf{S}=\left|\begin{array}{c}{16.73}\ {100}\end{array}\right|.}\end{array}
$$

Then we can find the prices of the pure assets as $\boldsymbol{\Psi}=(\mathbf{H}^{\prime})^{-1}\boldsymbol{\mathsf{S}}.$ The solution is

$$
\Psi=\left|\begin{array}{r r}{{0.0250}}&{{-0.0467}}\ {{0.0000}}&{{0.0133}}\end{array}\right|\left|\begin{array}{r}{{16.73}}\ {{100}}\end{array}\right|=\left|\stackrel{0.4182}{0.5527}\right|.
$$

Finally, using the option and the risk-free bond, our $\mathbf{H}$ matrix is

$$
\begin{array}{r}{\mathbf{H}=\left|\begin{array}{c c}{40}&{103}\ {0}&{103.}\end{array}\right|.}\end{array}
$$

The S vector will be

$$
\begin{array}{r}{\mathbf{S}=\left|\begin{array}{c}{16.73}\ {100}\end{array}\right|.}\end{array}
$$

Then we can find the prices of the pure assets as $\boldsymbol{\Psi}=(\mathbf{H}^{\prime})^{-1}\boldsymbol{\mathsf{S}}.$ The solution is.

$$
\Psi=\left|\begin{array}{c c}{{0.0250}}&{{-0.0000}}\ {{-0.0467}}&{{0.0133}}\end{array}\right|\left|\begin{array}{c}{{16.73}}\ {{100}}\end{array}\right|=\left|\stackrel{0.4182}{0.5527}\right|.
$$

Thus, it does not matter which assets we use, but it is good to see that the result is internally consistent.
