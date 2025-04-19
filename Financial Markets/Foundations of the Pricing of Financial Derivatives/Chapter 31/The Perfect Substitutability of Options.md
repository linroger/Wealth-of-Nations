---
tags:
  - '#black_scholes_merton_model'
  - '#deep_in_the_money_calls'
  - '#deep_out_of_the_money_puts'
  - '#implied_volatility'
  - '#option_pricing'
  - '#option_replication'
  - '#option_substitutability'
  - '#option_valuation'
  - '#risk_free_bonds'
  - '#volatility_smile'
---
# 31.4 THE PERFECT SUBSTITUTABILITY OF OPTIONS

Within the Black-Scholes-Merton framework, any option on the same underlying should be a perfect substitute for any other option. To demonstrate this claim, consider an option priced at $w_{1}$ and a second option on the same asset priced at $w_{2}$ . These options could have different exercise prices and/or times to expiration. They could differ in that one is a call and one is a put. It does not matter. They are simply two options on the same asset, which itself is priced at S.

Suppose we wished to buy the first option. Under the assumptions of the. Black-Scholes-Merton model, we could create the same result by combining the second option with risk-free bonds. The math to demonstrate this result requires essentially a derivation of the Black-Scholes-Merton model. We can avoid these technical details by. using some simple results from the Black-Scholes-Merton formula itself..

We can write a general expression for the values of these options as follows:

$$
\begin{array}{r}{w_{1}=b_{s1}S+b_{b1}X_{1}e^{-r_{c}\tau_{1}}}\ {w_{2}=b_{s2}S+b_{b2}X_{2}e^{-r_{c}\tau_{2}}.}\end{array}
$$

The quantities $b_{s1}$ and $b_{s2}$ represent the holdings of the underlying asset necessary to replicate options 1 and 2, and the quantities $b_{b1}$ and $b_{b2}$ represent the holdings of risk-free bonds necessary to replicate options 1 and 2.

If option 1 is a call, the Black-Scholes-Merton formula is, of course,

$$
\begin{array}{r}{w_{1}=S N\Big(d_{1}^{(1)}\Big)-X_{1}e^{-r_{c}\tau_{1}}N\Big(d_{2}^{(1)}\Big),}\end{array}
$$

where $N(d_{1}^{(1)})$ and $N(d_{2}^{(1)})$ are the well-known standard cumulative normal probabilities,. typically identified as $\bar{N}(d_{1})$ and $N(d_{2})$ when working with a single option. These values are computed using the appropriate exercise price $X_{1}$ and time to expiration $\tau_{1}$ in the. standard formula for $d_{1}$ and $d_{2}$ .8 Thene $b_{s1}$ .5 $N(d_{1}^{(1)})$ and $b_{b1}$ .5 $-N(d_{2}^{(1)})$

If option 1 is a put, the formula is

$$
w_{1}=X_{1}e^{-r_{c}\tau_{1}}N\left(-d_{2}^{(1)}\right)-S N\left(-d_{1}^{(1)}\right).
$$

Then $b_{s1}$ would be $-N(-d_{1.}^{(1)})$ and $b_{b1}$ would be $N(-d_{2}^{(1)})$ . If option 2 is a call, the Black-Scholes-Merton formula is

$$
w_{2}=S N\Big(d_{1}^{(2)}\Big)-X_{2}e^{-r_{c}\tau_{2}}N\Big(d_{2}^{(2)}\Big),
$$

with the $N(d_{1}^{(2)})$ and $N(d_{2}^{(2)})$ terms defined in the manner previously described. Then $b_{s2}$ would be $N(d_{1}^{(2)})$ , and $b_{b2}$ would be $-N(d_{2}^{(2)})$ If option 2 is a put, the formula is

$$
w_{2}=X_{2}e^{-r_{c}\tau_{2}}N\Big(-d_{2}^{(2)}\Big)-S N\Big(-d_{1}^{(2)}\Big),
$$

and $b_{s2}$ would be $-N\bigg(-d_{1}^{(2)}\bigg)$ and $b_{b2}$ would be $N\bigg(-d_{2}^{(2)}\bigg)$

From these general expressions, we can see how to replicate any option with any other option on the same underlying. Take the general expression for $w_{2}$ and solve for $S$ to obtain

$$
S=\frac{w_{2}-b_{b2}X_{2}e^{-r_{c}\tau_{2}}}{b_{s2}}.
$$

Then substitute this result for $S$ into the expression for. $w_{1}$

$$
w_{1}=\left(\frac{b_{s1}}{b_{s2}}\right)w_{2}-\left(\frac{b_{s1}}{b_{s2}}\right)b_{b2}X_{2}e^{-r_{c}\tau_{2}}+b_{b1}X_{1}e^{-r_{c}\tau_{1}}.
$$

We see that the first option can be replicated by holding. $({b}_{s1}/{b}_{s2})$ units of option 2,. $-(b_{s1}/b_{s2})b_{b2}$ units of a risk-free bond paying. $X_{2}$ at the expiration of option 2, and. $b_{b1}$ units of a risk-free bond paying. $X_{1}$ at the expiration of option 1.9 Of course, this position must be dynamically adjusted through time. Nonetheless, any option can be used to replicate any other option on the same underlying, regardless of exercise price, time to expiration, or whether it is a call or a put. Hence, any option is a perfect substitute for any other option on the same underlying, at least in the Black-Scholes-Merton world..

That being the case, there is no rationale within the Black-Scholes-Merton framework. for why any one option should be more expensive than any other option, after accounting. for time to expiration, exercise price, and whether it is a put or a call. But clearly the existence of multiple implied volatilities tells us that some options are more expensive. than others, and the smile tells us that there is a pattern to the relative costs of these options. Typically the most expensive options are the deep-in-the-money calls and deep out-of-the-money puts as illustrated in the previous figures..

Unfortunately, no one really knows why certain options are more expensive than others. Deep out-of-the-money puts have oftentimes been viewed as a form of insurance against large drops in the market. Fear of a crash, it is said, leads some investors to pay relatively more for the protection these options afford than for other options. Yet, the Black-Scholes-Merton theory says that any option should substitute perfectly for any other option. Yet, theory and reality diverge. Perhaps the dynamic replicating strategy is too com-. plex or too costly to implement. For whatever reason, perfect substitution does not hold in reality.

The Black-Scholes-Merton model is a wonderful theory, but it tells us nothing about why anyone would hold an option. It cannot motivate the holding of options because any. option serves as well as any other option. In reality, some options are more desirable than others. Whatever factors motivate the holding of options are simply not captured in the Black-Scholes-Merton model. Hence, these factors show up subsumed within the implied volatility.

One must then wonder why we do not simply throw out the Black-Scholes-Merton model. There are three reasons why we do not. First, the model is attractively simple. Although the mathematical details that support the derivation of the model are complex, there are a number of simple conceptual approaches to understanding the model.10 Practitioners have shown not only that they can understand the model but also that they can accept it. Second, the computational demands of the model are also quite modest. Perhaps its greatest virtue is that it requires so little information. But therein lies its vice: by requiring so little information, the model almost surely misses factors that explain why options are held and why some investors would pay more for certain options.

But the model is admired so much for its simplicity that practitioners continue to use it. The volatility smile and related surface is the price paid for oversimplification..
