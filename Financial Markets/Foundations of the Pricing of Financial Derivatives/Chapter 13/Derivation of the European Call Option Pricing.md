---
tags:
  - black_scholes
  - european_option
  - ito_lemma
  - option_pricing
  - pde
aliases:
  - BSM
  - Black-Scholes-Merton
  - Option Price
key_concepts:
  - Asset price and time
  - Black-Scholes PDE
  - European call option
  - Hedge portfolio creation
  - Ito's lemma application
  - Risk-free portfolio
---

# 13.1 DERIVATION OF THE EUROPEAN CALL OPTION PRICING FORMULA

Consider a European call option with exercise price $X$ . The option price is assumed to be a function of only two variables: the asset price and time.1 Thus, we write the option price function in its general form as $c(S_{t},t)$ and more loosely as $c_{t}$ , which denotes the option price at time $t$ and where the option price is implicitly a function of the asset price at time $t$ $S_{t}$ . The option's time to expiration is $\tau=T-t.$ At expiration, the option price is $c_{T}=\operatorname*{max}\bigl(0,S_{T}-X\bigr)$

Let us construct a hedge portfolio consisting of $b$ units of the asset and one short call. option. The value of this portfolio at time t is

$$
V_{t}=h S_{t}-c_{t}.
$$

The value $b$ could be subscripted with a. $t$ , as its value is set and known at. $t$ We hold $b_{t}$ units of the asset per one short call. As we move forward, the value of our holdings changes. due to changes in the value of the asset and the call and the increment of time. We are still holding $b_{t}$ units of the asset and one short call. As noted later, we shall have to reset $b_{t}$ according to the new market conditions, such as at time $t+d t$ to obtain $b_{t+d t}$ Thus, $b_{t}$ is set at $t$ and remains constant until we rebalance, which occurs after we determine how our portfolio has performed. Consequently, for the purpose of this derivation, we can treat. $b_{t}$ as a constant and denote it as $b$

Our objective is to make this portfolio risk free. Because the call price is a function of $S_{t}$ which follows the stochastic differential equation in (13.1), and. $t.$ we use Ito's lemma to express the call price change in terms of the changes in. $S_{t}$ and ${t,}^{2}$

$$
d c=\frac{\partial c}{\partial S}d S+\frac{\partial c}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}d S^{2}.
$$

Given Equation (13.1) and the properties of the Wiener process, $d\mathbb{W}_{t}$ we know that $d S^{2}=$ $S^{2}\sigma^{2}d t$ . Henceforth, we shall make this substitution whenever we use the result from Ito's lemma.

We know that the value of the portfolio, Equation (13.2), is a function of the asset price and the option price. Hence, using the total differential rule, we can express the change in the value of the portfolio as

$$
d V={\frac{\partial V}{\partial S}}d S+{\frac{\partial V}{\partial c}}d c.
$$

From Equation (13.2), we can determine the partial derivatives as

$$
\begin{array}{l}{\displaystyle\frac{\partial V}{\partial S}=b}\ {\displaystyle\frac{\partial V}{\partial c}=-1.}\end{array}
$$

Thus, the change in the value of the portfolio is

$$
d V=b d S-d c.
$$

Substituting from Ito's lemma, Equation (13.3), for $d c$ in (13.6) gives

$$
d V_{t}=b d S-\left(\frac{\partial c}{\partial S}d S+\frac{\partial c}{\partial t}d t+\frac12\frac{\partial^{2}c}{\partial S^{2}}S^{2}\sigma^{2}d t\right).
$$

Equation (13.7) is a stochastic partial differential equation that defines the change in the value of the portfolio in terms of several expressions. Observe that the stochastic terms are the $d S$ terms but note that they amount to the simple expression $b d S-(\partial c/\partial S)d S.$ We are free to set $b$ to whatever we want as long as its value can be determined before the asset price changes. It should be apparent that by setting $b$ to $\partial c/\partial S$ , the two $d S$ terms cancel, leaving the following expression for the change in the value of the portfolio:

$$
d V=-\left(\frac{\partial c}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}S^{2}\sigma^{2}d t\right).
$$

Notice in Equation (13.8) that there are no stochastic terms, so this portfolio is perfectly hedged. Thus, to avoid arbitrage the portfolio value,. $V.$ , must increase at the risk-free rate. This specification is made by the requirement that.

$$
d V=V r_{c}d t.
$$

We now substitute $b S-c=(\partial c/\partial S)S-c$ for $V$ in Equation (13.9) to obtain

$$
d V=\left({\frac{\partial c}{\partial S}}S-c\right)r_{c}d t.
$$

We now have two expressions for. $d V$ Equations (13.8) and (13.10). Equating these and canceling the $d t$ terms gives

$$
r_{c}S\frac{\partial c}{\partial S}+\frac{\partial c}{\partial t}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}\sigma^{2}S^{2}=r_{c}c.
$$

Equation (13.11) is a partial differential equation of which the unique solution, $c$ , is the call option price. The unique solution is determined by the boundary conditions, which refers to the value of $c$ at the option expiration. In the case of a European call, the condition is that $c_{T}=\operatorname*{max}(0,S_{T}-X).^{3}$ Equation (13.11), or a variation of it, appears frequently in derivative pricing theory and is often termed the Black-Scholes-Merton partial differential equation.

Equation (13.11), formally a second-order parabolic partial differential equation, is. actually a variation of a famous equation in physics that models the transfer of heat. The solution procedure is well known to physicists and one version of it is presented later in this chapter. Black and Scholes (1973) first obtained the solution by taking advantage of previous research on option pricing that produced an idea of what the solution would look like. Bachelier (1900) had derived the solution under arithmetic Brownian motion.4 Several other researchers derived similar solutions under diverse assumptions, but the key complication was that none of this earlier work on option pricing used the risk-free hedge.5. As such, they all require the use of a discount rate that reflected the risk premium that an investor would demand to hold an option. Risk premia are not observable in the market, and they require that the model incorporate assumptions about the risk preferences of investors. These requirements are fairly standard in general equilibrium models, such as the capital asset pricing model and most models of macroeconomic equilibrium. These. models typically aggregate the demand and supply of assets and produce an equilibrium price, as well as the optimal holdings of assets by individuals. These models are powerful but demanding ones that impose many restrictions on their users and can be very difficult to empirically estimate and to implement in practice..

Partial equilibrium models, however, derive prices and certain other pieces of information only for sectors within a market or economy. For example, a partial equilibrium option pricing model derives the price of an option as well as the hedge ratio and the option. sensitivities to changes in its inputs. It does not, however, tell us how many, if any, options a market participant would hold. Nonetheless, partial equilibrium models are valuable for pricing and trading instruments such as options, keeping in mind, however, that they apply only to this sector of the market..

The early research on option pricing produced partial equilibrium models, but these models imposed certain general equilibrium requirements, meaning that we needed to know something about investor risk preferences and the rates at which they would discount risky future cash flows. These requirements are quite strong. Hence, these models never gained much acceptance.

The key insight provided by Black, Scholes, and Merton of the risk-free hedge was a. giant leap forward in economic and financial theory. Interestingly, there is some indica-. tion that a mathematically oriented practitioner, Ed Thorp, working with Sheen Kassouf. (1967), developed the model before Black, Scholes, and Merton did. Thorp and Kassouf, however, did the wise thing and kept it to themselves, apparently making a considerable amount of money. Black, Scholes, and Merton did credit Thorp and Kassouf for the idea of risk-free hedging.6 For a history of the development of the ideas behind the model, see. Szpiro (2011).

Despite their limitations, each of the option pricing formulas that preceded BlackScholes-Merton resembles the correct solution as found by Black, Scholes, and Merton. Black and Scholes originally derived the equation by using the capital asset pricing model,. which provides the equation for the expected return on a risky asset as a function of its risk. Though Black had a PhD in applied mathematics from Harvard, he was not aware that the differential equation was the heat transfer equation. It is rumored that someone. else noticed and showed him how to obtain the solution. At approximately the same time,. Robert Merton (1973b) wrote a paper developing the model with virtually the full mathematical solution. It is not clear whether Merton or Black and Scholes came up with the result first, but Black and Scholes have without doubt received the most credit, because the model is more often known as the Black-Scholes model.7 The model should probably be called the Black-Scholes-Merton model, and we shall do so, but Merton has never really received full credit. Black died in 1995, and in 1997, Merton and Scholes received the Nobel Prize in Economics for this work..

The solution to the equation is the Black-Scholes-Merton option pricing model,

$$
\begin{array}{r}{c=S N\big(d_{1}\big)-X e^{-r_{c}\tau}N\big(d_{2}\big),}\end{array}
$$

where

$$
\begin{array}{l}{{d_{1}={\displaystyle\frac{\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma{\sqrt{\tau}}}}}\ {{d_{2}={\displaystyle\frac{\ln(S/X)+\left(r_{c}-\sigma^{2}/2\right)\tau}{\sigma{\sqrt{\tau}}}}=d_{1}-\sigma{\sqrt{\tau}}}.}\end{array}
$$

The value $N\left(d_{i}\right),i=1,2$ , is the cumulative normal probability,

$$
N(d_{i})=\int_{-\infty}^{d_{i}}\frac{1}{\sqrt{2\pi}}e^{-x^{2}/2}d x.
$$

Note that the expected return on the asset is not a factor in pricing the option. All of the information needed to capture investor risk preferences is embedded in the price of the underlying, S. If we attempted to incorporate risk preferences by, say, using a discount rate. greater than the risk-free rate, we would be double counting, that is, penalizing the option twice for the effect of risk..

Of the five inputs into the model, four are easily observable. We know the price of the asset, S. The option contract specifies the exercise price, $X$ , and when the option expires. The time to expiration, $\tau.$ , is simply the number of remaining days divided by 365. The risk-free rate, $r_{c}$ , would be the continuously compounded rate on a risk-free security that matures at the option expiration. The only remaining factor is the volatility, and it is indeed an unobservable factor. Investors will have different opinions on the volatility, and this diversity of opinions will generate trading.8
