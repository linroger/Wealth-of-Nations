---
tags:
  - '#black_formula'
  - '#caplet_pricing'
  - '#caplets'
  - '#caps_and_floors'
  - '#floorlets'
  - '#forward_caps_and_floors'
  - '#forward_swap'
  - '#interest_rate_options'
  - '#libor_rate'
  - '#volatility_smile'
---
# 17.6 CAPS AND FLOORS  

Caps and floors are important instruments for fixed-income professionals. Our treatment of caps. and floors will be consistent with the approach adopted in this text from the beginning. First, we would like to discuss, not the more liquid spot caps and floors that start immediately, but instead the so-called forward caps and floors. These instruments have a future start date and are perhaps. less liquid, but they are more appropriate for learning purposes. Second, we will follow our stan-. dard practice and generate these instruments from instruments that have already been discussed..  

Again, we keep the framework as simple as possible and leave the generalization to the reader. Consider the two-period forward fixed payer swap shown in Figure 17.6a. In this swap, there will be two settlements  

$$
\left(f_{t_{0}}-L_{t_{1}}\right)N\delta\quad\mathrm{and}\quad\left(f_{t_{0}}-L_{t_{2}}\right)N\delta
$$  

where $L_{t_{i},f_{t_{0}}}$ , and $N$ are the relevant LIBOR rate, forward swap rate, and the forward swap notional, respectively. 8 is the reset interval. The forward swap starts at time t.2  

We now consider a particular decomposition of this forward swap. First, note that depending on whether $L_{t_{1}}>f_{t_{0}}$ or not, the swap party either receives a payment at time $t_{2}$ , or makes a payment. Thus, the first cash flow to be settled at time $t_{2}$ can be decomposed into two contingent cash flows  

![](images/edd5a6ae4336e2ead5aac277438228c2f2de01996d0a5eedbfdf4ddb42ffe7b1.jpg)  

# FIGURE 17.6  

Forward fixed payer swap.  

depending on whether $L_{t_{1}}<f_{t_{0}}$ or $L_{t_{1}}>f_{t_{0}}$ . The same can be done for the second cash flow to be settled at time $t_{3}$ . Again, the cash flow can be split into two contingent payments.  

These contingent cash flows can be interpreted as payoffs of some kind of interest rate option. Consider the cash flows of time $t_{2}$ in Figure 17.6b. Here, the client receives $\big(L_{t_{1}}-f_{t_{0}}\big)N\delta$ if $L_{t_{1}}>f_{t_{0}}$ , otherwise he or she receives nothing. Thus, this cash flow will replicate the payoff of an option with expiration date $t_{1}$ , and settlement date $t_{2}$ that is written on the LIBOR rate $L_{t_{1}}$ . The client receives the appropriate difference at time $t_{2}$ if the LIBOR observed at time $t_{1}$ exceeds a cap level $\kappa$ , which in this case is $\kappa=f_{t_{0}}$ . Thus, the top part of Figure 17.6b is like an insurance against movements of LIBOR rates above level $\kappa$ . This instrument is labeled a caplet and its time $t$ price is denoted by $C l^{t_{1}}$ . The client is long a caplet.  

The lower portion of Figure 17.6b is similar but shows insurance against a drop of the LIBOR rate below the floor level $\kappa$ . In fact, the cash flow here is a payment of. $\left(f_{t_{0}}-L_{t_{1}}\right)N\delta$ if $L_{t_{1}}<f_{t_{0}}$ Otherwise, the client pays nothing. This cash flow replicates the payoff of an option with expiration $t_{1}$ and settlement $t_{2}$ that is written on the LIBOR rate. The client pays the appropriate difference at time $t_{2}$ , if the LIBOR observed at time $t_{1}$ falls below floor. $\kappa$ , which in this case, is. $\kappa=f_{t_{0}}$ . We call this instrument a floorlet and denote its price by. $F l^{t_{1}}$ . Clearly, the client is short the floorlet in this case.  

The treatment of the time $t_{3}$ settled caplet-floorlets is similar. The cap and floor levels are again the same:  

$$
\kappa=f_{t_{0}}
$$  

but exercise times, settlement times, and the underlying LIBOR rate. $L_{t_{2}}$ are different. By putting the two caplets together, we get a two-period forward interest rate cap, which starts at time $t_{1}$ and ends at $t_{3}$  

$$
\mathrm{Cap}=\{C l^{t_{1}},C l^{t_{2}}\}
$$  

Similarly, the two floorlets can be grouped as a two-period forward interest rate floor:  

$$
\mathrm{Floor}=\{F l^{t_{1}},F l^{t_{2}}\}
$$  

These forward caps and floors can be extended to $n$ periods by putting together $n$ caplets and floorlets defined similarly.  

Figure 17.6 shows that we obtained a contractual equation. By adding Figures 17.6b and c vertically, we get back the original forward swap. Thus, we can write the contractual equation:  

![](images/afd10c91c72d08666b134e444f0c27b1567428071d5fe013d96c4c792673634b.jpg)  

This contractual equation shows that caps, floors, and swaps are closely related instruments.  

# 17.6.1 PRICING CAPS AND FLOORS  

This discussion will be conducted using the same two-period cap and floor discussed earlier. One obvious conclusion from the engineering shown here is that the caplets that make up the cap can be priced separately and their values added, after discounting them properly. This is how a caplet is typically priced; we take the $C l^{t_{1}}$ written on $L_{t_{1}}$  

First, let the $\boldsymbol{F}\left(t,t_{1}\right)$ $t<t_{1}$ , be the forward rate that corresponds to. $L_{t_{1}}$ , observed at $t.$ More precisely, $\boldsymbol{F}\left(t,t_{1}\right)$ is the interest rate decided on at time $t$ on a loan that will be made at time $t_{1}$ and paid back at time $t_{2}$ . Market practice assumes that the forward LIBOR rate. $\boldsymbol{F}(t,t_{1})$ can be represented as a Martingale with constant instantaneous percentage volatility $\sigma$  

$$
\mathrm{d}F(t,t_{1})=\sigma F(t,t_{1})\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

with initial point $\boldsymbol{F}(t_{0},t_{1})$  

Second, the market assumes that the arbitrage-free value of a $t_{2}$ -maturity default-free pure discount bond price, denoted by B(to, t2), can be calculated.22  

Third, it is shown that the time $t_{0}$ value of the caplet $C l^{t_{1}}$ is given by the formula  

$$
C l_{t_{0}}^{t_{1}}=B(t_{0},t_{2})E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\operatorname*{max}\left[L_{t_{1}}-\kappa,0\right]N\delta\right]
$$  

where, in this case,. $\kappa$ also equals the forward swap rate $f_{t_{0}}$ . Hence, this is an ATM cap. $N$ is the national amount. Here, the expectation is taken with respect to the forward measure $\tilde{P}^{t_{2}}$ and the normalization is done with the $t_{2}$ -maturity pure discount bond, $B(t_{0},t_{2})$  

Finally, remembering that under the measure $\tilde{P}^{t_{2}}$ , the forward LIBOR rate $\boldsymbol{F}(t_{0},t_{1})$ is an unbiased estimate of $L_{t_{1}}$  

$$
F(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}^{l_{2}}}\left[L_{t_{1}}\right]
$$  

a closed-form formula can be obtained. This is done by applying Black's formula to the $\boldsymbol{F}(t,t_{1})$ process, which has a zero drift term. Then the expectation  

$$
E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\operatorname*{max}\left[L_{t_{1}}-\kappa,0\right]N\delta\right]
$$  

can be calculated to obtain Black's formula:23  

$$
C l_{t_{0}}^{t_{1}}=B(t_{0},t_{2})[F(t_{0},t_{1})N(h_{1})-\kappa N(h_{2})]\delta N
$$  

where  

$$
h_{1}=\frac{\log(F(t_{0},t_{1})/\kappa)+(1/2)\sigma^{2}(t_{1}-t_{0})}{\sigma\sqrt{t_{1}-t_{0}}}
$$  

$$
h_{2}=\frac{\log(F(t_{0},t_{1})/\kappa)+(1/2)\sigma^{2}(t_{1}-t_{0})}{\sigma\sqrt{t_{1}-t_{0}}}-\sigma\sqrt{(t_{1}-t_{0})}
$$  

Note that both $F(t_{0},t_{1})$ and $f_{t_{0}}$ are rates that relate to amounts calculated in $t_{2}$ dollars. The discount bond price $B(t_{0},t_{2})$ is then a market-determined "expected"' discount rate for this settlement.  

The caplet that expires at time $t_{2},C l^{t_{2}}$ , will be priced similarly, except that this time the expectation has to be taken with respect to the time $t_{3}$ forward measure $\tilde{P}^{t_{3}}$ , and the underlying forward. rate will now be. $F\left(t_{0},t_{2}\right)$ and not $F\left(t_{0},t_{1}\right)$ 24 Solving the pricing formula, we get  

$$
C l_{t_{0}}^{t_{2}}=B(t_{0},t_{3})[F(t_{0},t_{2})N(g_{1})-\kappa N(q_{2})]\delta N
$$  

where  

$$
q_{1}=\frac{\log(F(t_{0},t_{2})/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}
$$  

$$
q_{2}=\frac{\log(F(t_{0},t_{2})/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}-\sigma\sqrt{(t_{2}-t_{0})}
$$  

It is important to realize that the same constant percentage volatility was used in the two caplet formulas even though the two caplets expired at different times. In fact, the first caplet has a life of $[t_{0},t_{1}]$ , whereas the second caplet, $C l_{t_{0}}^{t_{2}}$ , has a longer life of $[t_{0},t_{2}]$ . Also, note that despite the strike price being the same, the two caplets have different money.  

Finally, to get the value of the cap itself, the market professional simply adds the two caplet prices:  

$$
\mathrm{Cap}_{t_{0}}=B(t_{0},t_{2})[F(t_{0},t_{1})N(h_{1})-\kappa N(h_{2})]+B(t_{0},t_{3})[F(t_{0},t_{2})N(g_{1})-\kappa N(g_{2})]
$$  

where $h_{i}$ and $g_{i}$ are given as noted earlier. The parameters $N,\delta$ are set equal to one in this formula.   
Otherwise, the right-hand side needs to be multiplied by $N,\delta$ as well.  

# 17.6.2 A SUMMARY  

It is worth summarizing some critical steps of the cap/floor pricing convention. First, to price each. caplet, the market uses normalization by means of a discount bond that matures at the settlement date of that particular caplet and obtains the forward measure that corresponds to that caplet. Second, the. market uses an SDE with a zero drift since the corresponding forward LIBOR rate is a Martingale. under this measure. Third, the percentage volatility for all the caplets is assumed to be constant and identical across caplets. Finally, the use of proper forward measures makes it possible to calculate the expectations for the random discount factors and the caplet payoffs, separately. Black's formula gives the caplet prices which are added using the appropriate liquid discount bond prices..  

# 17.6.3 CAPLET PRICING AND THE SMILE  

The previous summary should make clear why the volatility smile is highly relevant for pricing and hedging caps/floors. The latter are made of several caplets and floorlets and, hence, are baskets of options written on different forward rates denoted by $F\left(t_{0},t_{i}\right),i=1,...,n.$  

As long as the yield curve is not flat, the forward rates $\boldsymbol{F}\left(t_{0},t_{i}\right)$ will be different from each other. Yet, each cap or floor has only one strike price $\kappa$ . This means that, relative to this strike price, we will have  

$$
\frac{F(t_{0},t_{1})}{\kappa}\neq\frac{F(t_{0},t_{2})}{\kappa}\neq\cdots\frac{F(t_{0},t_{n})}{\kappa}
$$  

In other words, as long as the yield curve slopes upward or downward, the ratios  

$$
\frac{F(t_{0},t_{i})}{\kappa}
$$  

will be different, implying different moneyness for each caplet/floorlet.  

Now, suppose there is a volatility smile. If, under these conditions, each caplet and floorlet. were sold separately, the option trader would substitute a different volatility parameter for each,. conformable with the smile in the corresponding Black's formula. But caplets or floorlets are bundled into caps and floors. More important, a single volatility parameter is used in Black's formula..  

This has at least two implications. First, we see that the volatility parameter associated with a. cap is some weighted average of the caplet volatilities associated with options that have different moneyness characteristics. Second, even when the realized and ATM volatilities remain the same, a.  

movement of the yield curve would change the moneyness of the underlying caplets (floorlets) and,. through the smile effect, would change the volatility parameter that needs to be used in the corresponding Black's formulas. In other words, marking cap/floor books to the market may become a delicate task if there is a volatility smile..  
