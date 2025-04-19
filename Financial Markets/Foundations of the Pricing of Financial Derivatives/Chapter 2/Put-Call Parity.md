---
tags:
  - arbitrage
  - european_options
  - option_pricing
  - put_call_parity
  - risk_free_bonds
aliases:
  - Option Parity
  - PCP
  - Put-Call Relationship
key_concepts:
  - European option relationship
  - Long asset and put
  - Long call and bonds
  - Portfolio O and P
  - Put-call parity explained
---

# 2.9 PUT-CALL PARITY

The connection between the prices of puts and calls with the same exercise price and expiration is referred to as put-call parity, and it is one of the most important relationships in all of option pricing. We first begin with European options.

# 2.9.1 Put-Call Parity for European Options

We construct two portfolios called O and P. Portfolio O consists of one unit of the asset and one European put and Portfolio $\mathrm{P}$ consists of one European call and a zero-coupon

bond with face value of. $X$ and current value of. $X e^{-r_{c}\tau}$ . We assume no dividends on the.
underlying. Table 2.11 shows the outcomes at expiration.

Notice that Portfolio $\mathrm{o}$ and Portfolio $\mathrm{P}$ produce the same results at expiration. Thus, they must have the same value today. We, therefore, can state put-call parity as

$$
S_{t}+p_{t}=c_{t}+X e^{-r_{c}\tau}.
$$

This equation indicates that a long position in the asset and the put is equivalent to a long position in the call and risk-free bonds. In other words, we note that each of the four symbols $\boldsymbol{\cdot}\boldsymbol{S}_{t},\boldsymbol{p}_{t},\boldsymbol{c}_{t},$ and $X e^{-r_{c}\tau}.$ represents a financial instrument, respectively, the asset, a put, a call, and a zero-coupon bond. The sign, positive (implied) or negative, represents whether one is long or short. Now, let us use simple algebra to reveal some other relationships. First, let us isolate the put price,

$$
\begin{array}{r}{p_{t}=c_{t}-S_{t}+X e^{-r_{c}\tau},}\end{array}
$$

which indicates that a put is equivalent to a long call, short asset, and long bonds. Likewise, a call is indicated as

$$
c_{t}=p_{t}+S_{t}-X e^{-r_{c}\tau},
$$

which means that a call is equivalent to a long put, long asset, and short bonds. The asset itself can be decomposed as follows,.

$$
S_{t}=c_{t}-p_{t}+X e^{-r_{c}\tau},
$$

which indicates that the asset can be replicated by a long call, short put, and long bonds. Finally, the risk-free asset can be expressed as

$$
X e^{-r_{c}\tau}=S_{t}+p_{t}-c_{t},
$$

meaning that the zero-coupon bond is equivalent to the asset, a long put, and a short call. You can also take each of these equations, multiply by. $-1$ and make similar statements about short positions in the put, call, asset, and zero-coupon bond..

TABLE 2.11 Put-Call Parity for European Options on Assets Making No Cash Payments


<html><body><table><tr><td></td><td></td><td colspan="2">Value at Expiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td>Xs</td><td>ST</td></tr><tr><td>Portfolio O</td><td></td><td></td><td></td></tr><tr><td>Asset</td><td>'s</td><td>ST</td><td>ST</td></tr><tr><td>European put</td><td>pt</td><td>X-ST</td><td>0</td></tr><tr><td>Total</td><td>St+Pt</td><td>X</td><td>ST</td></tr><tr><td>Portfolio P</td><td></td><td></td><td></td></tr><tr><td>Call</td><td>Ct</td><td>0</td><td>Sr -X</td></tr><tr><td>Zero-coupon bond</td><td>Xe-rct</td><td>X</td><td>X</td></tr><tr><td>Total</td><td>²X+</td><td>X</td><td>ST</td></tr></table></body></html>

If there are dividends on the asset, put-call parity is easily established by simply. modifying the zero-coupon bond in Portfolio. $\mathrm{P}$ such that its current value is $X e^{-r_{c}\tau}+D_{t}$ At expiration Portfolio $\mathrm{P}$ will, therefore, pay off $X+D_{t}e^{r_{c}\tau}$ . Portfolio O's payoff in each. state will be augmented by the reinvested value of the dividends,. $D_{t}e^{r_{c}\tau}$ . The final results will be the same in that the payoffs of the two portfolios are still equivalent, but put-call parity is now stated as

$$
S_{t}-D_{t}+p_{t}=c_{t}+X e^{-r_{c}\tau}.
$$

In other words, the asset price is simply reduced by the present value of the dividends. This process of reducing the asset price by the present value of the dividends will arise often in derivative pricing.

Let us now examine a case where put-call parity does not hold. Suppose you observe the following data: The stock price is $S_{t}=100$ , the strike price is $X=100$ , a European call is at $c_{t}=7.55$ , a European put is at $p_{t}=7.55$ , and the time to expiration is 0.5 years, a 1.0 dividend will be paid in 0.25 years $(D_{t+0.25}=1.0$ or the present value $D_{t}=0.99$ . The risk-free interest rate is $r_{c}=5.0\%$ (continuously compounded, annualized, appropriate for both dividend and expiration). How would an arbitrageur trade? The first step is to assess. whether there is a put-call parity violation. Note in this case the value of the put-call parity relation can be assessed based on the expression provided in Equation (2.32). Note that. the two sides do not equal,

$$
S_{t}-D_{t}+\mathfrak{p}_{t}=100-0.99+6.02=105.03<c_{t}+X e^{-r_{c}\tau}=7.55+97.53=105.08.
$$

The arbitrageur seeks to pocket this 0.05 difference through a series of current trades. Rearranging the expression such that a positive number is produced, we have. $c_{t}+X e^{-r_{c}\tau}-$ $S_{t}+D_{t}-p_{t}=0.05$ . To generate this cash flow, you would sell the call. $(+c_{t}=7.55)$ , short. sell the bond or borrow the present value of the exercise price . $\langle X e^{-r_{c}\tau}=100e^{-0.05(0.5)}=$ 97.53), buy the stock $(-S_{t}=-100)$ , short sell the bond or borrow the present value of the. dividend $(-D_{t}=-1e^{-0.05(0.25)}=0.99)$ , and buy the put $(-p_{t}=-6.02)$ . Table 2.12 clearly demonstrates that these transactions result in arbitrage profits today with no future cash flows at all..

TABLE 2.12  Numerical Illustration Put-Call Parity for European Options on Assets Making No Cash Payments


<html><body><table><tr><td colspan="3"></td><td colspan="2">Cash Flow at Expiration</td></tr><tr><td>Instrument</td><td>Cash Flow Today</td><td>Cash Flow at Dividend Date</td><td>Sr≤X</td><td>X<Sr</td></tr><tr><td>Sell call</td><td>+ct = +7.55</td><td></td><td>0</td><td>-(Sr - X)</td></tr><tr><td>Short sell bond</td><td>Xe-rc=+97.53</td><td></td><td>-X=-100</td><td>= 100-ST -X= -100</td></tr><tr><td>Buy stock</td><td>-S, = -100</td><td>+DtD = +1.0</td><td>+ST</td><td>+ST</td></tr><tr><td>Short sell bond</td><td>+Dt= +0.99</td><td>-DtD = -1.0</td><td></td><td></td></tr><tr><td>Buy put</td><td>-pt=-6.02</td><td></td><td>X-ST</td><td>0</td></tr><tr><td>Net</td><td>Ct + Xe-rct-S +Dt-pt=0.05</td><td>0</td><td>=100-ST 0</td><td>0</td></tr></table></body></html>

Note that buying pressure will drive the stock and put prices up and selling pressure will drive the call price down. Again, in well-functioning markets, we expect the net cash flow today to quickly move to nearly zero..

# 2.9.2  Put-Call Parity for American Options

If the options are American, put-call parity is a bit more complex, and the statements we shall be able to make a bit less precise. We first consider the case of no dividends. Portfolio. P, consisting of a long call and a zero-coupon bond, is not subject to early exercise because the long call would not be exercised due to the absence of dividends on the asset. Given the potential for early exercise, it is necessary to adjust the initial value of the bonds to $X$ instead of $X e^{-r_{c}\tau}$ . That is, we make the current value of the bonds equal to the exercise price, not the present value of the exercise price, which means we borrow a little more money. At expiration, the bonds will mature and pay off $X e^{-r_{c}\tau}$ . So, at expiration, the payoff of Portfolio P will either be $X e^{r_{c}\tau}$ $S_{T}\leq X$ or $S_{T}-X(1-e^{r_{c}\tau})$ $S_{T}>X$ Portfolio O, however, is subject to early exercise of the put. Let us choose an arbitrary time before expiration, $j,$ in which the remaining time to expiration is $\tau_{j}$ . Suppose at that point, the asset price, $S_{j}\mathrm{:}$ is sufficiently below the exercise price to justify early exercise. In that case, the holder of the put will tender the asset and receive the exercise price. We assume that. this person will reinvest the exercise price at the risk-free rate, such that it will grow to a value of $X e^{r_{c}\tau_{j}}$ at time $T.$ The final value at $T$ will be

If $S_{T}\leq X$

<html><body><table><tr><td>0</td><td>(the call) (the bonds)</td></tr></table></body></html>

If $S_{T}>X$

<html><body><table><tr><td>ST-X</td><td>(the call)</td></tr><tr><td></td><td>(the bonds)</td></tr><tr><td>ST - X + Xerct</td><td>(total for Portfolio P)</td></tr><tr><td>Xerctj</td><td>(total for Portfolio O with put exercised early)</td></tr></table></body></html>

In the first outcome,. $S_{T}\leq X$ , Portfolio $\mathrm{P}$ has the same value as Portfolio O. In the sec-. ond outcome, $S_{T}>X$ $\mathrm{P}$ beats $\mathrm{o}$ because the value $S_{T}>X$ and $X e^{r_{c}\tau_{j}}$ is positive. Hence, $\mathrm{P}$ dominates O, and we can say that. $C_{t}+X\geq P_{t}+S_{t}$ . Let us rearrange this to. $\mathrm{C}_{t}\geq P_{t}+$ $S_{t}-X$ and further arrange to have the call on the left-hand side,

$$
C_{t}\geq P_{t}+S_{t}-X.
$$

This result establishes a lower limit on the call price. We can also establish an upper limit on the call price by using European put-call parity. With the conditions $p_{t}=c_{t}-S_{t}{+}X e^{-r_{c}\tau}a$ nd $P_{t}>p_{t}$ we can say that $P_{t}\ge c_{t}-S_{t}+X e^{-r_{c}\tau}$ . With no dividends, $\mathrm{C}_{t}>c_{t}$ we have,

$$
\begin{array}{r}{C_{t}\leq P_{t}+S_{t}\mathrm{-}X e^{-r_{c}\tau}.}\end{array}
$$

Now we can combine these results to obtain put-call parity for American options on non-dividend-paying assets.

$$
P_{t}+S_{t}-X e^{-r_{c}\tau}\geq C_{t}\geq P_{t}+S_{t}-X.
$$

Unfortunately, the best we can do is place these bounds around the put price.10

If the asset pays dividends with present value. $D_{t}$ , the proof is only slightly altered. Consider the first inequality, $P_{t}+S_{t}{-}X e^{-r_{c}\tau}\geq C_{t}$ If we impose dividends, it will raise the put price and lower the call price, so this relationship will still be correct. For the other inequality, $C_{t}\geq P_{t}+S_{t}{-}D_{t}-X$ let us pretend that it is violated. That is, suppose. $\mathrm{\mathit{C}}_{t}<$ $P_{t}+S_{t}{-}D_{t}-X$ . If we believe that the left-hand side (LHS) should be greater than the. right-hand side (RHS), an arbitrage should be possible. Because the call price appears to be too low, let us buy the call. We would then sell the RHs by selling the put, shorting. the stock, and buying zero-coupon bonds with face value $D_{t}+X$ Now, suppose the put is immediately exercised on us. We now have to pay out. $X$ to buy the shares, so let us borrow $X$ We then tender $X$ to acquire the shares from the put holder, and we use the. shares to cover the short sale. At expiration, we would owe $X e^{r_{c}\tau}$ but our zero-coupon bond would mature and pay that same amount plus. $D_{t}e^{r_{c}\tau}$ . If the puts are not exercised until maturity, we will have accrued an obligation to pay all the dividends, but this amount will be covered by the value of $D_{t}e^{r_{c}\tau}$ from the maturing bonds. So, this strategy generates. a cash inflow at the start and a positive or zero outflow at maturity. Therefore, it is an arbitrage opportunity and will be exploited, which will drive up the price of the call or drive down the price of the put until the correct inequality is established. Therefore,

$$
P_{t}+S_{t}-X e^{-r_{c}\tau}\geq C_{t}\geq P_{t}+S_{t}-D_{t}-X.
$$

Note we can rearrange Equation (2.35), isolating the role of the interest rate, time. to maturity, and present value of dividends, as. $X e^{-r_{c}\tau}\leq S_{t}+P_{t}-C_{t}\leq D_{t}+X$ For nondividend-paying stocks with short maturity options in a low rate environment we have very. tight put-call parity boundaries. Figure 2.6 illustrates the normalized Equation (2.35) or

$$
1-\frac{X e^{-r_{c}\tau}-P_{t}}{S_{t}}\geq\frac{C_{t}}{S_{t}}\geq1-\frac{D_{t}+X-P_{t}}{S_{t}},
$$

where the LHS is the put-call parity upper bound, and the RHS is the put-call parity lower bound. Figure 2.6a illustrates short-dated options (44 days to maturity with. $5\%$ Sstrike range) and Figure $2.6\mathrm{b}$ illustrates long-dated options (212 days to maturity with $25\%$ strike range). Note that we use a trading day in November that contains one potential future dividend payment for the short-dated option and two potential future dividends for the long-dated option. The presence of dividends results in wider bounds.

With an understanding of option boundaries, we observe a rationality to the relation-. ship between the underlying, calls, and puts that is not apparent to the untrained eye.

![](cac5623faae26b73361f6fb69483941b391e2118195917705320e068e42c4a47.jpg)
FIGURE 2.6a Illustration of Put-Call Parity Bounds for Short-Dated American Options (in Percentage)

![](243c7ea55d64fe0b6c39826cd10c1c2194a1bfda1d2b6dda75e7a61a902ae71c.jpg)
FIGURE 2.6b Illustration of Put-Call Parity Bounds for Long-Dated American Options (in Percentage)

We are just beginning to partially unravel financial derivatives mysteries. Once you finish this book, there will be plenty of remaining mysteries worthy of a lifetime of research and. learning.

# 2.9.3 Put-Call Parity and the Box Spread

There is a special relationship between the prices of European puts and calls that differ by exercise price. Suppose one buys the call with exercise price $X_{L}$ , sells the call with exercise. price $X_{H}$ , buys the put with exercise price. $X_{H}$ , and sells the put with exercise price. $X_{L}$ These portfolios constitute a strategy known in the world of options trading as a box. spread. Because the call purchased will cost more than the call that is sold, there is a net cash outflow for the calls. Likewise, the put purchased will cost more than the put sold,. so there is a net cash outflow for the puts. Thus, these transactions will net out to a long. position, meaning that the investor who does this strategy will pay out money at the start. Let us look at the outcomes because they produce a somewhat surprising result..

If $S_{T}>X_{H}$ , both calls are exercised and both puts are out-of-the-money for a payoff of $S_{T}-X_{L}-(S_{T}-X_{H})=X_{H}-X_{L}$

If $X_{L}<S_{T}\leq X_{H}$ , the long $X_{L}$ call is exercised for a value of $S_{T}-X_{L}$ and the long $X_{H}$ put is exercised for a value of $X_{H}-S_{T}$ for a total value of $X_{H}-X_{L}$

If $S_{T}\leq X_{L}$ , the long $X_{H}$ put is exercised for a value of $X_{H}-S_{T}$ and the short $X_{L}$ put is exercised for a value of $-(X_{L}-S_{T})$ for a total of $X_{H}-X_{L}$ . Thus, the box spread pays off $X_{H}-X_{L}$ in every state.

With the same payoff in each case, the value of the box spread is the present value of $X_{H}-X_{L}$

$$
c_{t L}-c_{t H}+p_{t H}-p_{t L}=(X_{H}-X_{L})e^{-r_{c}\tau}.
$$

Thus, it may surprise you to know that this strategy, which combines four options, is. actually risk-free. It is also easy to see that the box spread is just a combination of two put-call parities. Let us write put-call parity for both sets of options as.

$$
\begin{array}{l}{{p_{L}+S=c_{L}+X_{L}e^{-r_{c}\tau}}}\ {{{}}}\ {{p_{H}+S=c_{H}+X_{H}e^{-r_{c}\tau}.}}\end{array}
$$

We then isolate the asset price and obtain

$$
\begin{array}{l}{S_{t}=c_{L}+X_{L}e^{-r_{c}\tau}-p_{L}}\ {\qquad}\ {S_{t}=c_{H}+X_{H}e^{-r_{c}\tau}-p_{H}.}\end{array}
$$

Setting these equations equal to each other gives the box spread, Equation (2.36).

Dividends have no effect on the box spread because none of the positions produce. dividends. If the options are American, the analysis is slightly modified. If the short call. is exercised, then the long call is even deeper in-the-money and can be exercised for a. value of $X_{H}-X_{L}$ , which is then reinvested in cash until expiration. Thus, it will grow. to $X_{H}-X_{L}$ plus the interest reflecting the time between the early exercise date and the expiration. In addition, the puts can have some value at expiration to add. At expiration, the puts will be worth zero at worst and. $X_{H}-X_{L}$ at best, provided they are not exercised early. If the puts are exercised early, they will be worth $X_{H}-X_{L}$ , which will be reinvested. until expiration. In addition, the calls can have some value at expiration to add. In short, the box spread will pay off. $X_{H}-X_{L}$ at expiration or possibly before expiration and there. can be additional payoff from the non-exercised options. Because the options are subject to immediate early exercise, in which case they could be worth. $X_{H}-X_{L}$ right now and because it is possible that at some time during the life of the options that are alive, another. payoff will be received, we can say that.

$$
C_{t L}-C_{t H}+P_{t H}-P_{t L}\geq X_{H}-X_{L}.
$$
