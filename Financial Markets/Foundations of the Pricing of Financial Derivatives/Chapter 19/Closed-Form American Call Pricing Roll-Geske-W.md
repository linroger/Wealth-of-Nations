# 19.1 CLOSED-FORM AMERICAN CALL PRICING: ROLL-GESKE-WHALEY

The Roll-Geske-Whaley (RGW) model requires that there be only one known cash payment made over the life of the option, such as a stock that pays quarterly dividends but with only one dividend to be paid before the option expires..

The amount of the payment is assumed to be known with certainty and is the amount $D$ , and again the time in years until the payment date is. $\tau_{1}$ .2 We assume that as the payment is made, the asset price falls by the amount of the payment, although this assumption can be relaxed such that it falls by a proportion of the payment. We are also given the asset volatility, $\sigma$ , and the continuously compounded risk-free rate,. $r_{c}$ . Let us first define the following value $S-D e^{-r_{c}\tau_{1}}$ , which is simply the asset price minus the present value of the. cash payment. We assume that this adjusted asset price follows the standard lognormal diffusion that is typically used in modeling asset price dynamics.3 We denote the price of a European call on this asset as $c$ and the price of an American call on this asset as C..

We can replicate the American call with three option positions, denoted OP1, OP2, and OP3. Thus, consider the following combination of option positions:

(OP1) A long position in a European call where the underlying is the stock that pays the known dividend with time to expiration $\tau_{A}$ and exercise price X. So this option expires at the expiration of the American option we are pricing.
(OP2) A short position in a European compound call option where the underlying option is the European call in (OP1). This compound option has a time to expiration of $\tau_{1}$ , meaning that it expires when the dividend payment is made, and it has an exercise price of $S_{1}^{*}+D-X$ where $S_{1}^{*}$ is defined next..
(OP3) A long position in a European call option where the underlying is the stock that pays the known dividend with time to expiration of $\tau_{1}$ and exercise price of $S_{1}^{*}$ where $S_{1}^{*}$ will be defined next.

The value $S_{1}^{*}$ is the critical ex-dividend asset price above which the compound option will be exercised. The corresponding underlying call pricee $(c^{*})$ is also found such that

$$
{c^{*}}={S_{1}}^{*}+D-X.
$$

In other words,. $S_{1}^{*}$ is the ex-dividend asset price that triggers early exercise.

To understand how these options combine to replicate the American call, let us assume that we are now positioned an instant before the cash payment is to be made at time $T_{1}$ The asset price is. $S_{1}^{+}$ . As soon as the payment is made, it will fall to $S_{1}^{-}$ . Thus, to make. the exercise decision, one would compare $S_{1}^{-}$ to $S_{1}^{*}$ . This critical price will be found by iteration, as we will shortly cover. Now, let us look at the payoffs of the three options: (OP1), (OP2), and (OP3).

$S_{1}^{-}\leq S_{1}^{*}$ (post-payment price is less than or equal to the critical price):

<html><body><table><tr><td>(OP1)</td><td>Regardless of the post-payment price, this is a European call and cannot be exercised until its expiration TA. It is simply worth its standard</td></tr></table></body></html>

<html><body><table><tr><td>(OP2)</td><td>This compound option will be exercised or not depending on whether the value of (OP1) exceeds the exercise price of the compound option, S* + D - X. The critical ex-dividend asset price is the one at which the option in (OP1) is precisely equal in value to S* + D - X. Because the asset price S is less than S*, as assumed in this case, then the value of the corresponding call (c) c < c*, but by definition c* = S* + D - X. Thus</td></tr><tr><td>(OP3)</td><td>and is not exercised. This is an expiring European call. Its exercise price S* exceeds the ex-dividend price, so it expires worthless.</td></tr></table></body></html>

Thus if $S_{1}^{-}<S_{1}^{*}$ , this combination of options produces no cash flow at this point and leaves us holding a European call with remaining expiration $\tau_{1A}$ . Note that this is similar to an. American call. If it does not get exercised early at the ex-dividend date, we are left holding a European call. Now consider the other possibility.. $S_{1}^{-}>S_{1}^{*}$ (ex-dividend price is greater than critical price):

<html><body><table><tr><td>(OP1)</td><td>This call will be worth c1 when the stock goes ex-dividend. It has an exercise price of X and a remaining time of T1A·</td></tr><tr><td>(OP2)</td><td>The compound option is expiring. Using the presented arguments, this option is now in-the-money and is exercised. Because we are short this option, we</td></tr><tr><td>(OP3)</td><td>deliver the option in (OP1) and receive the exercise price S* + D - X. This option is a European call expiring right now. Its exercise price S* is less than the current asset price S1 so it expires in-the-money. We own this option sowepay S*</td></tr></table></body></html>

Thus if $S_{1}^{-}\geq S_{1}^{*}$ the overall cash flow is $S_{1}^{-}-S_{1}^{*}+S_{1}^{*}+D-X=S_{1}^{-}+D-X.$ Thus, we paid out $X$ and received an asset worth $S_{1}^{\mathbf{\alpha-}}$ and its cash payment, $D$ . We see that this combination of two standard European options, one long and one short with different exercise prices and expirations, and one compound option produce the same results as an American option. That is, if the ex-dividend asset price is below the critical price for justification of early exercise, the American call option holder is left holding an option with exercise price $X$ and time to expiration $\tau_{1A}$ . If the ex-dividend asset price is above the critical price for justification of early exercise, the American call option holder exercises the option, paying out $X$ and receiving the dividend $D$ and is left holding an asset worth $S_{1}^{-}$ . These same results are obtained with the combination of options (OP1), (OP2), and (OP3).

The critical asset price for justification of exercise is the one such that it produces a Black-Scholes-Merton value of. $S_{1}^{*}+D-X$ for a European call with exercise price of. $X$ and a time to expiration of. $\tau_{1A}$ . This value must be derived iteratively by plugging in. values into the Black-Scholes-Merton model with time to expiration of $\tau_{1A}$ until the option value equals $S_{1}^{*}+D-X$ A good starting point estimate of $S_{1}^{*}$ is $X-D$ because the option would have to give a positive payoff to justify exercise, but the actual value of $S_{1}^{*}$ will be much higher. Standard iterative equation-solving techniques such as Newton-Raphson can speed up the search. If early exercise is not justified at any price, due to too small of a cash payment relative to the other values in the model, $S_{1}^{*}$ will be infinite. In that case, our final solution will converge to Black-Scholes-Merton.

Because our combination of the three options replicates the American call, we can. easily find the value of the American call by adding the values of options (OP1) and (OP3), which are given by the Black-Scholes-Merton model, and subtracting the value of option (OP2), which as a compound option is given by Geske's compound option formula. The. values of these three options can be written as.

$$
\begin{array}{r l r}&{\mathrm{O}P1=\left(S-D e^{-r_{c}\tau_{1}}\right)N_{1}(a)-X e^{-r_{c}\tau_{4}}N_{1}\left(a_{2}\right)}&\ &{\mathrm{O}P2=\left(S-D e^{-r_{c}\tau_{1}}\right)N_{2}\left(b_{1},a_{1},\rho\right)-X e^{-r_{c}\tau_{4}}N_{2}\left(b_{2},a_{2},\rho\right)-\left(S_{t}^{\ast}+D-X\right)e^{-r_{c}\tau_{1}}N_{1}\left(b_{2},a_{1},\rho\right)}&\ &{\mathrm{O}P3=\left(S-D e^{-r_{c}\tau_{1}}\right)N_{1}\left(b_{1}\right)-S_{t}^{\ast}e^{-r_{c}\tau_{1}}N_{1}\left(b_{2}\right),}&{(19)^{\ast}}&\end{array}
$$

where

$$
\begin{array}{r l}&{a_{1}=\cfrac{\ln\big[(S-D e^{-r_{c}\tau_{1}})/X\big]+(r_{c}+\sigma^{2}/2)\tau_{A}}{\sigma\sqrt{\tau_{A}}}}\ &{a_{2}=a_{1}-\sigma\sqrt{\tau_{A}}}\ &{b_{1}=\cfrac{\ln\big[(S-D e^{-r_{c}\tau_{1}})/S_{1}^{*}\big]+(r_{c}+\sigma^{2}/2)\tau_{1A}}{\sigma\sqrt{\tau_{1A}}}}\ &{b_{2}=b_{1}-\sigma\sqrt{\tau_{1A}}}\ &{\rho=\sqrt{\tau_{1}/\tau_{A}},}\end{array}
$$

where $N_{1}(.)$ is the univariate normal probability and $N_{2}(.)$ is the bivariate normal probability. These formulas can be consolidated to equal

$$
\begin{array}{r l}&{C={\cal O P1}-{\cal O P2}+{\cal O P3}}\ &{\quad=(S-D e^{-r_{c}\tau_{1}})N_{1}(a_{1})-(X-D)e^{-r_{c}\tau_{1}}N_{1}(b_{2})}\ &{\quad\quad+\left(S-D e^{-r_{c}\tau_{1}}\right)\left[N_{1}(b_{1})-N_{2}(b_{1},a_{1};\rho)\right]-X e^{-r_{c}\tau_{A}}\left[N_{1}(a_{2})-N_{2}(b_{2},a_{2};\rho)\right].}\end{array}
$$

The following relationships are known to exist between the univariate and the bivariate normal distributions:

$$
\begin{array}{c}{{N_{1}(x)-N_{2}(x,y;\rho)=N_{2}(x,-y;-\rho)}}\ {{{}}}\ {{N_{2}(x,y;\rho)=N_{2}(y,x;\rho).}}\end{array}
$$

Therefore, the third expression in Equation (19.4) can be written as

$$
(S-D e^{-r_{c}\tau_{1}})N_{2}(b_{1},-a_{1};-\rho),
$$

and the fourth expression can be written as

$$
X e^{-r_{c}\tau_{A}}\left[N_{1}(a_{2})-N_{2}(a_{2},b_{2};\rho)\right]=X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho).
$$

Thus, our formula now becomes

$$
\begin{array}{c}{{C=(S-D e^{-r_{c}\tau_{1}})N_{1}(a_{1})+(S-D e^{-r_{c}\tau_{1}})N_{2}(b_{1},-a_{1};-\rho)}}\ {{{}}}\ {{-X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho)-(X-D)e^{-r_{c}\tau_{1}}N_{1}(b_{2}).}}\end{array}
$$

Now we can use the following relationship:

$$
N_{1}(a_{1})+N_{2}(b_{1},-a_{1};-\rho)=N_{1}(b_{1})+N_{2}(a_{1},-b_{1};-\rho).
$$

Substituting we obtain the overall solution as

$$
\begin{array}{r l}&{C=(S-D e^{-r_{c}\tau_{1}})N_{1}(b_{1})+(S-D e^{-r_{c}\tau_{1}})N_{2}(a_{1},-b_{1};-\rho)}\ &{\qquad-X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho)-(X-D)e^{-r_{c}\tau_{1}}N_{1}(b_{2})\mathrm{or}}\ &{C=(S-D e^{-r_{c}\tau_{1}})N_{1}(b_{1})-(X-D)e^{-r_{c}\tau_{1}}N_{1}(b_{2})}\ &{\qquad+(S-D e^{-r_{c}\tau_{1}})N_{2}(a_{1},-b_{1};-\rho)-X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho).}\end{array}
$$

Let us examine each of these four terms, using the interpretation based on the assumption of risk neutrality. The first term, $(S-D e^{-r_{c}\tau_{1}})N_{1}(b_{1})$ is the discounted expected value. of the asset price at the payment day, conditional on the asset price exceeding the critical price. This term reflects the expected receipt of the asset on exercise of the option immediately before the dividend payment day. The term $(X-D)e^{-r_{c}\tau_{1}}N_{1}(b_{2})$ is the discounted expected payout at the payment day from exercise of the option. The probability term is the univariate probability of early exercise. The term,. $(S-D e^{-r_{c}\tau_{1}})N_{2}(a_{1},-b_{1};-\rho)$ is the discounted expected value of the asset price at the expiration, given that the option was. not exercised early and ends up in-the-money. The other term,. $X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho).$ is the discounted expected payout of the exercise price at expiration, conditional on the option not having been exercised early and ends up in-the-money at expiration. Each of these interpretations is based on risk neutrality, which as we know is not an assumption about investor preferences but permits correct pricing of options. Thus, when we say one of these probabilities is the probability of something occurring, we mean the probability. if investors were risk neutral..

Now let us observe how the formula converges to the Black-Scholes-Merton formula for the case of zero dividends. Letting. $D=0$ , we have

$$
\begin{array}{l}{{C=S N_{1}(b_{1})+S N_{2}(a_{1},-b_{1};-\rho)}}\ {{\qquad-X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho)-X e^{-r_{c}\tau_{1}}N_{1}(b_{1}),}}\end{array}
$$

with $D=0,S_{t}^{*}\to\infty$ . Then $b_{1}\to-\infty$ and $b_{2}\to-\infty$ . Then $N(b_{1})=N(b_{2})=0$ . So this leaves us with

$$
C=S N_{2}(a_{1},-b_{1};-\rho)-X e^{-r_{c}\tau_{A}}N_{2}(a_{2},-b_{2};-\rho).
$$

The first probability in Equation (19.12) is defined as

$$
N_{2}(a_{1},-b_{1};-\rho)=N_{1}(a_{1})\int_{-\infty}^{-b_{1}}\frac{1}{\sqrt{2\pi(1-\rho^{2})}}\exp\left(-\frac12\frac{x^{2}-2\rho x y+y^{2}}{1-\rho^{2}}\right)d y.
$$

With $-b_{1}\rightarrow\infty$ , then $N_{2}\big(a_{1},-b_{1};-\rho\big)=N_{2}\big(a_{1},\infty;-\rho\big)$ is the joint probability that. $x\leq a_{1}$ and $b\leq\infty$ . This is simply $N_{1}\big(a_{1}\big)$ . Similarly, $N_{2}\big(a_{2},-b_{2};-\rho\big)=N_{2}\big(a_{2},\infty;-\rho\big)=N_{1}\big(a_{2}\big)$ This reduces the overall expression to

$$
S N_{1}\left(a_{1}\right)-X e^{-r_{c}\tau_{A}}N_{1}\left(a_{2}\right),
$$

which is the Black-Scholes-Merton formula, where $^{a}$ takes the place of $d$ in the normal probability.

A numerical example of the one-dividend case is presented in Appendix 19A. Let us now take a look at the two-dividend case.
