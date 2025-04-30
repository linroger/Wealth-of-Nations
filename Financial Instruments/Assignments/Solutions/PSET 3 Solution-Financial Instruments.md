---
title: PSET 3 Solution-Financial Instruments
tags:
  - coupon_bond
  - currency_swap
  - exchange_rate
  - greece_bond
  - usd_eur
aliases:
  - Currency Swap
  - Greece
  - Homework 3
  - PSET 3
key_concepts:
  - Currency swap components
  - EUR coupon bond
  - Exchange rate risk
  - Principal exchange
  - Swap value calculation
  - USD coupon bond
---

---

title: PSET 3 Solution

# PSET 3 Solution-Financial Instruments

Solution to Homework 3
For illustrative purposes,  this solution set is much longer than is required for full credit.

## Part 1. Greece Currency Swap

(1) To understand how we can compute the swap rate $K$ that sets the value of the currency swap equal to $U$,  it is helpful to break down the currency swap into simpler components. We know that Greece will have:

1. A position in USD:
(a) Pay USD 50 billion on June 1 st,  2001 (from now on: $t=0$) (b) Receive USD $50\cdot{\frac{0.06}{2}}=1.5$ billion every six months for the next 10 years (c) Receive USD 50 billion on June 1 st,  2011 (from now on: $t=T$
1. A position in EUR
$$\frac{USD\:50}{0.8475\:USD\:/\:EUR}=EUR\:59\:\mathrm{billon~at}\:t=0$$
(b) Pay EUR $59\cdot\frac{K}{2}$ billion every six months for the next 10 years (c) Pay EUR 59 billion at $t=T$
Now it’s easy to see that (1. B) and (1. C) are the cash flows of a long position in (i.e. we buy) a coupon bond with principal equal to USD 50 billion,  maturing in 10 years and with a semiannual coupon rate equal to $c=6\%$. In the same way (2. B) and (2. C) are the cash flows of a short position in (i.e. we sell) a coupon bond with principal equal to EUR 59 bn,  maturing in 10 years and with a semiannual coupon rate equal to $K$. Finally (1. A) and (2. A) represent the exchange of principal. This principal is exchanged to hedge the exchange rate risk on the principal that will be paid at $T$.
In particular,  Greece will receive USD 50 billion and will pay EUR 59 billion at $t=T$. If the dollar depreciates,  the USD 50 bn (which are exactly equivalent to EUR 59 bn at $t=0$) will be worth less than EUR 59 bn.
To hedge against this risk,  Greece exchanges the principal at time $t=0$ and agrees that,  at $t=T$,  the principal will be exchanged at the same exchange rate used for the principal exchange at time $t=0$.
We can write the swap as a sum of three components:
$$SWAP=BOND^{8}-BOND^{e}+EoP_{0}$$
Where EoP is the exchange of principal. The value of the swap will therefore be
$$V^{Swap}=B^{8}-B^{e}+V^{EoP_{0}}$$
where $B^{\$}$ and $B^{e}$ denote,   as in Teaching Notes 2,   the value of two coupon bonds (with different coupon rates) in USD and EUR,   respectively. We know that their semiannual coupon rates are $c=6\%$ (I will keep writing $U$ to get a more general result) and $K$ respectively.
The initial exchange of principal is typically done in a way that $V^{EoP}=0$,   that is,   the principal in USD is equal to the principal in EUR times the current USD / EUR exchange rate. So the value of the swap becomes $V^{Swap}=B^{\$}-B^{e}$. Now we know that the value at $t=0$ (in USD) of the USD coupon bond is
$$B_0^8=\sum\limits_{t=0.5}^T\frac{c}{2}\cdot N^8\cdot Z^8(0,  t)+N^8\cdot Z^8(0,  T)$$
That is,   the sum of all discounted (using the US zero coupon curve $Z^{\$}(0,  t)$) coupons (i.e. $\frac{c}{2}\cdot N$) plus the discounted value of the principal at maturity. Similarly,   the value at $t=0$ (in EUR) of the EUR coupon bond is
$$B_0^e=\sum\limits_{t=0.5}^T\frac{K}{2}\cdot N^e\cdot Z^e(0,  t)+N^e\cdot Z^e(0,  T)$$
Before computing $K$,   remember that when we compute the value of the swap,   we express it in a determined currency. Since each bond has its own currency,   we have to convert all values to the same currency. So,   if we want to compute the value of the currency swap in dollars,   we will convert the value of the EUR bond into USD,   by multiplying it by the spot USD / EUR exchange rate. In formulas,   the time $t$ value of the currency swap in USD is:
$$V_t^{Swap,  s}=B_t^s-M_t\cdot B_t^e$$
Similarly,   the time $t$ value in EUR is:
$$V_t^{Swap,  \:e}=\frac{B_t^s}{M_t}-B_t^e$$
We can now compute $K$. Our goal is to have $V_{0}^{Swap}=0$. Let’s take the value of the swap in USD
$$V_0^{Swap,  8}=B_0^8-M_0\cdot B_0^e=0$$
This implies that $B_{0}^{\$}=M_{0}\cdot B_{0}^{e}$,   which is the same as
$$B_0^8=M_0\cdot\left[\sum_{t=0.5}^T\frac{K}{2}\cdot N^e\cdot Z^e(0,  t)+N^e\cdot Z^e(0,  T)\right]$$
Rearranging,   we get:
$$\begin{aligned}\frac{B_0^8}{M_0}-N^e\cdot Z^e(0,  T)=\frac{K}{2}\cdot N^e\cdot\sum_{t=0.5}^TZ^e(0,  t)\end{aligned}$$
Solving for $K$,   we get:
$$K=2\cdot\frac{\frac{B_0^s}{M_0}-N^e\cdot Z^e(0,  T)}{N^e\cdot\sum_{t=0.5}^TZ^e(0,  t)}$$
But we don't know yet $B_{0}^{\mathrm{\$}}$. Using the US ZCB prices (also known as Zero Coupon curve or discount function),   we can compute its value as
$$\begin{aligned}B_{0}^{8}&=\quad\sum_{t=0.5}^T\frac{0.06}{2}\cdot50\cdot Z^8(0,  t)+50\cdot0.5848=\\&=\quad\frac{0.06}{2}\cdot50\cdot15.5573+50\cdot0.5848=52.5778\end{aligned}$$
Plugging it into equation (2),   we get $K=0.0566$ or $5.66\%$
(2) Under Goldman Sachs terms,   there are two major differences,   namely $K=7\%$ rather than $5.66\%$ and $V^{EoP_{0}}\neq0$,   since principal is exchanged using an exchange rate which is different from the spot exchange rate. We can use formula (1) to compute the currency swap. We already know $B^{\$}=52.5778$ billion of dollars. We need to compute the new value for $B^{e}$ since the coupon has changed to $K=7\%$ and the value of the time $t=0$ exchange of principal $V_{0}^{EoP_{0}}$. Using the same approach used for $B^{\$}$,   we get $B^{e}=68.244$ billion of EUR
For computing $VEoP_{0}$,   we need first to specify a currency. Let's consider USD,   and let's denote by $M_{0}$ the spot exchange rate and by $M^{GS}$ the fictitious exchange rate set in Goldman conditions. First,   let's define the cash flows in USD. Greece will pay to Goldman $N^{8}=50$ billion of dollars and will receive a cash flow in EUR determined using the fictitious state $M^{GS}$,   that is,   $N^{e}=\frac{N^{\mathrm{S}}}{M^{GS}}=\frac{50}{0.8148}=61.3648$ billion of euros. Then we can compute the value of the exchange of principal,   $V_{0}^{EoP_{0},  \:\$}$. To compute this,   we need to use the current exchange rate,   as the fictitious rate $M^{GS}$ was just used to determine the cash flow. We get (in billion of dollars)
$$V_{0}^{EoP_{0},  \:\$}=N^{e}\cdot M_{0}-N^{\$}=61.3648\cdot0.8475-50=2.0040$$
Alternatively,   if we wanted to compute the value of the exchange of principal in EUR,   we would have simply done
$$V_0^{EoP_0,  \:e}=N^e-\frac{N^8}{M_0}=61.3648-\frac{50}{0.08475}=2.3648$$
So Greece will receive a positive cash inflow at $t=0$ under Goldman conditions. The value of the currency swap will be
$$V^{Swap,  \:8}=B^{8}-B^{e}\cdot M_{0}+V^{EoP_{0},  \:8}=52.5778-68.2444\cdot0.8475+2.0066=-3.2548$$
Another interpretation of the question could have been to assume that the notional of the Euro bond was also changed to $N^{e}=61.3648$ using the fictitious exchange.
rate. Such interpretation would have led to the same directional result,  but with larger numbers,  therefore does not affect the grade. In this case,  we would have had $B^{e}=70.9796$ and $V^{Swap,  \$}=-5.5730$.
Wait a second,  the value of the swap is negative! Why would Greece accept something like this? One possible reason might be that the mark-to-market of the currency swap is not recognized as sovereign debt. Thus,  with the cash received at inception,  Greece could have paid a portion of its outstanding debt. In theory,  we expect that the value of the outstanding debt does not change (as we have a swap with a negative market value); however,  since the swap value did not account for as debt according to EUROSTAT (the institution that takes care of collecting all Euro countries’ data on debt,  deficit,  GDP,  etc.),  Greece could have reduced its reported debt in year 2001. Of course,  with the invented data provided,  this trick would have costed Greece a lot of money (3.25 billion of dollars).
# Part 2. Hedging with Options: Southwest Jet Fuel Hedging Program

(1. A) First,  assuming that all fuel is consumed on March 31 st,  2008,  allows us to match the cash flows of the options with the cash flows required by purchasing the fuel,  so we will not have any issues related to the time value of money. Second,  with the assumptions that 1 barrel of oil is sufficient to produce 1 barrel of jet fuel and that a 1 USD price change of crude oil per barrel causes always a 1 USD price change of jet fuel per barrel,  we can easily determine the number of options. The reasoning is as follows.
Let's assume that the CFO wants to hedge $75\%$ of its fuel consumption for Q 1 2008. We know that the expected fuel consumption for 2008 is 1,  511 million of gallons,  thus the expected Q 1 consumption is $\frac{1,  511}4=377.75$ million of gallons. With a $75\%$ hedge,  the quantity to be hedged is $377.75\cdot0.75=283.3125$ million of gallons,  or,  in barrels.
$\frac{283.3125}{42}=6.7455$ million. If fuel price per barrel rises by 1 USD between Dec 31 st 2007 and March 31 st 2008,  we will lose 6.7455 million of dollars (i.e. 1 USD for each barrel of consumption). To hedge this exposure,  we want to buy a number of options such that if oil price raises by 1 USD,  we will gain exactly (remember that our gain and losses are all computed at time $t=T$,  that is,  on March 31 st 2008) USD 6.7455 million. Now,  if the oil price is below the option strike,  we will not get anything from the option,  but if,  for example,  crude oil price per barrel increases from 105 USD to 106 USD,  we will gain 1.000 USD for each option (remember that each option trades on a lot of 1,  000 barrels). By assumption,  we expect oil and jet prices to move exactly by the same dollar amount,  so if oil price per barrel increases by 1 USD,  fuel price per barrel will increase by 1 USD. If we define by $\triangle P^{Oil}$ the change in oil price per barrel,  by $Payoff^{fuel}(\triangle P^{Oil})$ the payoff on our fuel position that we experience from a change in oil price (per barrel) equal to USD $\Delta P^{Oil}$,  and by $Payoff^{option}(\triangle P^{Oil})$ the option payoff arising from a change in oil price (per barrel) equal to USD $\Delta P^{Oil}$,  we can compute the number of options to be bought as
$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}$$
Let's assume $\triangle P^{Oil}=1$ dollar,  we then get $Payoff^{fuel}(\triangle P^{Oil})=-6.7455$ million of dollars (i.e. for each dollar price change of oil per barrel,  since by assumption fuel price per barrel will also change by 1 USD per barrel,  we lose 6.7455 million of dollars) and $Payoff^{option}(\triangle P^{Oil})=1,  000$ dollars. Putting all together,  we have
$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=-\frac{-6,  745,  500}{1,  000}=6,  745.5$$
Which we will round up to 6,  746.
If we instead assume a $100\%$ hedge of expected fuel consumption,  we would have had,  $FC^{hedged}=E[FC^{Q1}]=\frac{377.75}{42}=8.9940$ million of barrels,  and using the same reasoning as above,
$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=-\frac{-8,  994,  000}{1,  000}=8,  994$$
(1. B) From now on,  let's keep the $100\%$ hedge for simplicity. Using equation (3),  simply note that
$$Payoff^{fuel}(\triangle P^{Oil})=Payoff^{fuel}(\triangle P^{fuel}=1)\cdot\triangle P^{fuel}(\triangle P^{Oil})$$
so the payoff on our fuel position from a change in oil price per barrel equal to $\Delta P^{Oil}$ USD is equal to the payoff on fuel position arising from a 1 USD change in fuel price (per barrel) times the fuel price (per barrel) change due to a change in oil price (per barrel) equal to $\Delta P^{Oil}$. Moreover,  we can write $\triangle P^{fuel}(\triangle P^{Oil})=\triangle P^{fuel}(\triangle P^{Oil}=$ $1)\cdot\triangle P^{Oil}$. Plugging numbers,  we get:
$$\begin{aligned}
\text{Payoff}^{\text{fuel}}(\Delta P^{\text{Oil}}) 
&= \text{Payoff}^{\text{fuel}}(\Delta P^{\text{fuel}} = 1) \cdot \frac{\Delta P^{\text{fuel}}}{\Delta P^{\text{Oil}}} \cdot \Delta P^{\text{Oil}} \\
&= -8,\!944,\!000 \cdot 1.1964 \cdot \Delta P^{\text{Oil}}
\end{aligned}$$
And therefore
$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=-\frac{-8,  944,  000\cdot1.1964\cdot\triangle P^{Oil}}{1,  000\cdot\triangle P^{Oil}}=10,  760$$
(1. C) Let's compare the case for $100\%$ hedging. From point (1. A),  we would have bought 8.994 options,  while from point (1. B),  we would have bought 10,  760 options. Now we would have paid less in point (1. A),  but we would have had a lower payoff.
Indeed,  under (1. A) assumptions,  the expected payoff from 1 dollar change in fuel price per barrel was USD - 8,  994,  000,  and this was matched by the expected options payoff calculated at point (1. A). Under (1. B) assumptions,  the expected payoff from 1 dollar change in fuel price per barrel was USD - 10,  760,  000,  and this was matched by the expected options’ payoff calculated at point (1. B); this expected payoff,  however,  is greater,  in absolute value,  than the payoff we could get from the options bought in point (1. A). Therefore,  with the options bought in point (1. A),  we are not fully covering the expected (negative) payoff from the implicit short position in fuel. With such an amount of options,  $N^{opt}=8,  994$,  we are therefore under-hedged if the assumptions in (1. B) are true.
(1. D) The answer does not change. Just note that if we need 1.1964 barrels of oil to produce 1 barrel of fuel,  when the price of oil changes by 1 dollar,  the fuel price will change by 1.1964 dollars. The reason is that to produce 1 barrel of fuel,  refiners will need to buy 1.1964 barrels. They will pay an extra difference of 1 dollar per barrel of oil bought. Since they will buy 1 barrel plus 0.1964 barrels,  they will pay 1 extra dollar on the first barrel and 0.1964 extra dollars on the 0.1964 barrels. Therefore,  this would lead to the same results computed in point (1. B).
(1. E) Just a little note here before showing the graph. The payoff diagram (in contrast with the profit diagram) does not take into account the cost of the position. For example,  for a short position in fuel,  we do not consider $S_{0}$ but only $-S_{T}$. So at time $T$,  we will have necessarily a non-positive (i.e. $\pi(S)\leq0$ - note that I have randomly chosen to use 7 T as a synonymous of “payoff") payoff.
The payoff diagram of the implicit short position will thus be:
 ![500](https://storage.simpletex.cn/view/fGr8oQ3oKG4nZreK1yvxyok0zt9e3CyNG)
Figure 1: Payoff at $T=3$ months of the implicit short position in jet fuel
Note that the payoff is computed on the total exposure,  which is,  under the assumption in point (1. A),  8,  994.000 barrels of jet fuel (and oil). Further,  consider that if we accept assumptions (1. A),  then the oil price and jet fuel price can be assumed to be the same.
(1. F) The payoff diagram of the straight insurance is:
 ![500](https://storage.simpletex.cn/view/fnGXOEafa2ZQAkQhuqRIyltbhzlSiCykW)
Figure 2: Payoff at $T=3$ months of the straight insurance
And the one of the overall position,  combining the implicit short position with the straight insurance,  is:
 ![500](https://storage.simpletex.cn/view/fVHMFnAWlNA1yb7kVLwWn5G7AVQagpGGo)
Figure 3: Payoff at $T=3$ months of overall position using straight insurance
(2. A) We look for $P$ such that ${\mathcal{L}}={\mathcal{P}}$. Since $c\left(K_{c}=105\right)=2,  541$,  we find in the table that $K_{p}$,  such that $p\left(K_{p}\right)=2,  541$. This is for $K_{p}=88.61$
(2. B) The payoff of the collar strategy is:
 ![500](https://storage.simpletex.cn/view/fVa4kQwOabQC3e2BLDdmpGGvPuNbUX8lG)
Figure 4: Payoff at $T=3$ months of the collar using the $K_{1}=88.61$ puts
And the one of the overall position,  combining the implicit short position with the collar,  is:
 ![500](https://storage.simpletex.cn/view/fUE45dC68bzCwB7tUyBffUKaPsQixNo09)
Figure 5: Payoff at $T=3$ months of overall position using the $K_{1}=88.61$ puts
(3. A) Since the collar strategy has to be zero cost,  we look for a number of put options $N^{p}$ such that
$$N^p\cdot p=-N^c\cdot c$$
Or
$$N^p=-\frac{N^c\cdot c}{p}$$
We find $N^{p(K_{2}=80)}=-32,  742$. So we have to short 32.742 put options with strike equal to $K_{2}=80$
(3. B) We find $N^{p(K_{3}=90)}=-7,  596$. So we have to short 7,  596 put options with strike equal to $K_{3}=90$. The payoff of the collar with the $K_{2}=80$ puts is reported in the next figure.
 ![500](https://storage.simpletex.cn/view/fyW5mL123XwsCqXKWygodv0gwNKNng4dk)
Figure 6: Payoff at $T=3$ months of the collar using the $K_{2}=80$ puts
While the payoff of the collar with the $K_{3}=90$ puts is shown below.
 ![500](https://storage.simpletex.cn/view/fonmf5W9v8GpIBbfghvC8ov2K8ookXNl4)
Figure 7: Payoff at $T=3$ months of the collar using the $K_{3}=90$ puts The payoffs of the two overall positions are then shown.
 ![500](https://storage.simpletex.cn/view/f2ZMcm3TcTobr2uuYtslxWy4AToKfpzQt)
Figure 8: Payoff at $T=3$ months of overall position using the $K_{2}=80$ puts
 ![500](https://storage.simpletex.cn/view/fnxLE56e4v13gxAlBqUf7GpGgvF7s1fb2)
Figure 9: Payoff at $T=3$ months of overall position using the $K_{3}=90$ puts
Finally,  it is worth comparing the payoffs of the three collars in one chart.
 ![500](https://storage.simpletex.cn/view/fHYeraSe6R3nRkyeUDf5gH92gODto46SC)
Figure 10: Payoff at $T=3$ of the three collars
(3. C) Southwest Airlines payoff displayed in figure 5 has the general same pattern as a standard bull spread,  except that the payoff is always negative. The bull spread must have a positive premium,  while the premium for the net payoff displayed in figure 5 must be negative.
(3. D) You (should… Sorry,  MUST) know the put-call parity:
$$c-p=S_0-K\cdot e^{-r\cdot T}$$
Thus,  if we are interested in knowing 7,  we can actually derive it from equation (4). We have to follow very simple steps. We can rewrite (4) as
$$K\cdot e^{-r\cdot T}=S_0-c+p$$
Dividing by $K$
$$e^{-r\cdot T}=\frac{S_0-c+p}{K}$$
Taking (natural) logs
$$-r\cdot T=ln\left(\frac{S_0-c+p}{K}\right)$$
It follows that
$$r=-\frac{ln\left(\frac{S_0-c+p}{K}\right)}{T}$$
If we apply formula (5) to any pair of options,  provided we get (with some small rounding errors due to option prices approximation) that $r=4.5\%$.