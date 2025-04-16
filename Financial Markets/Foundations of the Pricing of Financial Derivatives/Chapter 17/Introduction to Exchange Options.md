---
tags:
  - '#euler_s_rule'
  - '#european_call_option'
  - '#exchange_options'
  - '#homogeneous_functions'
  - '#linear_homogeneity'
  - '#margrabe_model'
  - '#put_call_parity'
  - '#stochastic_exercise_price'
---
# 17.1 INTRODUCTION TO EXCHANGE OPTIONS

We will use the concept of linear homogeneity to price exchange options but we first have to define an exchange option. The exchange option, first covered by Margrabe (1978), has proven to be an extremely powerful generalization of the Black-Scholes-Merton model. In addition, the intuitive insights in the derivation of the exchange option model are very useful in other applications in option pricing.

Consider a European call option in which at expiration the holder can exchange one unit of asset 2 and receive one unit of asset 1. Let. $\bar{c}_{t}\big(S_{1},S_{2}\big)$ denote the price of this call option. Its payoff at expiration is.

$$
c_{T}(S_{1},S_{2})=\operatorname*{max}(0,S_{1T}-S_{2T}).
$$

With this option, asset 2 plays the role of the exercise price, but the difference from the standard case is that the value of asset 2 is stochastic. Thus, an exchange option is an option with a stochastic exercise price. Alternatively, one can view this option as a put in which asset 2 can be exchanged for asset 1. In the context of a put, asset 1 plays the role of the exercise price. Let this option price be denoted as $\boldsymbol{p}_{t}(S_{2},\bar{S}_{1})$ and the payoff at expiration be

$$
\begin{array}{r}{p_{T}\mathopen{}\mathclose\bgroup\left(S_{2},S_{1}\aftergroup\egroup\right)=\operatorname*{max}\mathopen{}\mathclose\bgroup\left(0,S_{1T}-S_{2T}\aftergroup\egroup\right).}\end{array}
$$

Thus, the current prices of the options are equal, $\boldsymbol{p}_{t}(S_{2},S_{1})=c_{t}(S_{1},S_{2})$

TABLE 17.1 Put-Call Parity of Exchange Options


<html><body><table><tr><td></td><td></td><td></td><td colspan="2">Value at Expiration</td></tr><tr><td></td><td>Instrument</td><td>CurrentValue</td><td>S1r ≤ S2T</td><td>S1r > S2T</td></tr><tr><td>Portfolio A</td><td>Long exch. call to exchange asset 2 for asset 1</td><td>c(S,S2)</td><td>0</td><td>S1T - S2T</td></tr><tr><td></td><td>Short exch. put to exchange asset 1 for asset 2</td><td>-p(S,S2)</td><td>-(S2T - S1r)</td><td>0</td></tr><tr><td></td><td>Total</td><td>c,(S1,S2)</td><td>S1T - S2T</td><td>S1T - S2T</td></tr><tr><td>Portfolio B</td><td>Long asset 1</td><td>-pt(S1,S2) S1t</td><td>+S1T</td><td>+S1T</td></tr><tr><td></td><td>Short asset 2</td><td>-S2t</td><td>-S2T</td><td>-S2T</td></tr><tr><td></td><td>Total</td><td>S1t - S2t</td><td>S1T - S2T</td><td>S1T - S2T</td></tr></table></body></html>

First let us establish put-call parity between exchange options. In the previous example, we argued that $\boldsymbol{p}_{t}(S_{2},\bar{S_{1}})=c_{t}\big(\bar{S}_{1},\bar{S_{2}}\big)$ . But what about the relationship of $c_{t}(S_{2},S_{1})$ to $\boldsymbol{p}_{t}(S_{2},S_{1})$ ? Keep in mind that in options notation, the first term in parentheses is the underlying, and the second is the strike. Table 17.1 illustrates equivalent portfolios A and B, with. the former being long the call and short the put and the latter being long asset 1 and short asset 2. We see that the payoffs of the two portfolios are equivalent.

Because the portfolios have the same payoff, their current values must be equal. Therefore,

$$
c(S_{1},S_{2})-p\big(S_{1},S_{2}\big)=S_{1}-S_{2}.
$$

In short, the difference in the value of a call option to exchange asset 2 for asset 1 and the value of a put option to exchange asset 1 for asset 2 is the difference in the values of asset 2 and asset 1. This difference will be negative when asset 2 is priced higher than asset 1.

With this introduction to exchange options, we turn to explaining homogeneous functions, linear homogeneity, and Euler's rule, all useful concepts related to valuing exchange options.
