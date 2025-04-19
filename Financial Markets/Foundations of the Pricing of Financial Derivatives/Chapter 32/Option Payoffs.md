---
tags:
  - '#call_option'
  - '#domestic_currency'
  - '#exercise_price'
  - '#foreign_currency_options'
  - '#moneyness_conditions'
  - '#option_payoffs'
  - '#put_option'
  - '#reciprocal_put'
---
# 32.2 OPTION PAYOFFS

At this point in the book, you will be familiar with option payoff functions. Nonetheless, it will be useful to repeat them here. The payoff of the call at expiration is.

$$
\begin{array}{l l}{{S_{T}-X}}&{{\mathrm{if}S_{T}\geq X}}\ {{}}&{{}}\ {{0}}&{{\mathrm{if}S_{T}<X.}}\end{array}
$$

Of course, we frequently wrote this compactly as $\operatorname*{max}\bigl(0,S_{T}-X\bigr)$ . We will now show that this option is isomorphic to a put option denominated in the foreign currency to sell $X$ units of the domestic currency at an exercise price of $1/X$ Let $X_{R}=1/X$ , the reciprocal strike. We shall call this put the reciprocal put. Because the reciprocal put has an exercise price of $1/X$ and the underlying value at expiration is $1/S_{T}$ , which we designate as $R_{T},$ the put will exercise when $1/S_{T}<1/X$ . Rearranging, we have

$$
\begin{array}{c}{{1/S_{T}\leq1/X}}\ {{\Rightarrow S_{T}\geq X.}}\end{array}
$$

Thus, when the reciprocal put is in-the-money, the spot call is in-the-money. The outof-the-money put condition is obviously

$$
\begin{array}{c}{{1/S_{T}>1/X}}\ {{\Rightarrow S_{T}<X.}}\end{array}
$$

Thus, the reciprocal put out-of-the-money condition is the same as the call out-of-themoney condition. Thus, to summarize, we have

<html><body><table><tr><td>Thecondition</td><td>1/ST ≤ 1/X</td><td>1/Sr > 1/X</td></tr><tr><td>is mathematically equivalent to And, therefore, implies that</td><td>Sr ≥X</td><td>Sr <X</td></tr><tr><td>Reciprocal put</td><td>In-the-money</td><td>Out-of-the-money</td></tr><tr><td>Call</td><td>In-the-money</td><td>Out-of-the-money</td></tr></table></body></html>

Incidentally, it should also be apparent that a standard put is equivalent to a reciprocal call

Having established that the moneyness conditions of a standard call and reciprocal put are the same, we now proceed to show that the payoffs are the same, provided we adjust the quantity of the reciprocal put and translate the payoff value into the domestic currency. The payoff of the reciprocal put option is

$$
\begin{array}{l l}{{X_{R}-R_{T}=(1/X)-\left(1/S_{T}\right)}}&{{\mathrm{~if~}S_{T}\geq X}}\ {{{}}}&{{{}}}\ {{0}}&{{\mathrm{~if~}S_{T}<X.}}\end{array}
$$

If we assume there are $X$ put options, this payoff in aggregate is

$$
\begin{array}{l l}{{X(1/X)-X\big(1/S_{T}\big)=1-X/S_{T}}}&{{\mathrm{if}S_{T}\geq X}}\ {{{}}}&{{\mathrm{if}S_{T}<X.}}\end{array}
$$

This payoff is in units of the foreign currency. To convert to domestic currency, we multiply by $S_{T}$

$$
\begin{array}{l l}{S_{T}\big(1-X/S_{T}\big)=S_{T}-X}&{\mathrm{if~}S_{T}\geq X}\ {{}}&{\mathrm{if~}S_{T}<X.}\end{array}
$$

Thus, we see that the payoff of the $X$ reciprocal puts is the same as that of the spot call.

So, to repeat, a spot call on a foreign currency with an exercise price of. $X$ quoted in terms of the domestic currency is equivalent to $X$ reciprocal puts on the domestic currency with an exercise price of $1/X$ in terms of the foreign currency. As such, in the world of foreign currency options, every call is also a put. Now, just to remind you, this would. be true for any option if we were comfortable talking in terms of calls say on a stock as being puts on money in terms of stock. But we typically do not characterize other types of. options in this manner.
