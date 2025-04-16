---
tags:
  - '#atm_swaption'
  - '#bermudan_swaptions'
  - '#caplets_floorlets'
  - '#european_swaptions'
  - '#fixed_payer_swaption'
  - '#fixed_receiver_swaption'
  - '#forward_swap_rate'
  - '#mortgages'
  - '#prepayment_clauses'
  - '#swaptions'
---
# 17.3 SWAPTIONS  

Mortgages form the largest asset class that households own directly or indirectly. The total mortgage stock is of similar size as the total US Treasury debt. Most of these mortgages have prepay-. ment clauses, and this leads to massive short swaption positions. As a result, Bermudan swaptions become a major asset class. In fact, mortgages are not the only instrument with prepayment clauses.. Prepayment options exist in many other instruments. Callable and putable bonds also lead to contingent, open-forward swap positions. These create similar swaptions exposures and can be fully hedged only by taking the opposite position in the relevant swaption market. Given the important. role played by swaptions in financial markets, we need to study their modeling. This section deals with technical issues associated with European swaptions.16  

A swaption can be visualized as a generalization of caplets and floorlets. The caplet selects a floating LIBOR rate, $L_{t_{i}}$ , for one settlement period, such that, if $L_{t_{i}}$ is greater than the cap rate $\kappa$ written in the contract, the caplet buyer receives compensation proportional to the difference. We can generalize this. Select a floating swap rate for $n$ periods. If the time $t_{1}$ value of this swap rate denoted by $s_{t_{1}}$ is greater than a fixed strike level, $f_{t_{0}}=\kappa$ , the buyer of the instrument receives payments proportional to the difference. Thus, in this case both the "underlying interest rate"' and the strike rate cover more than one period and they are forward swap rates. A fixed payer swaption can then be regarded as a generalization of a caplet. Similarly, a fixed receiver swaption can be regarded as a generalization of a floorlet.  

Let us look at this in more detail. Consider a European-style vanilla call option with expiration date $t_{1}$ . Instead of being written on equity or foreign exchange, let this option be written on a plain vanilla interest rate swap. The option holder has the right to "buy" the underlying at a selected strike price, but this underlying is now a swap. In other words, the option holder has the right to enter into a payer swap at time. $t_{1}$ , at a predetermined swap rate. $\kappa$ . The strike price itself can be. specified either in terms of a swap rate or in terms of the value of the underlying swap..  

Let $t_{0}$ be the trade date. We simplify the instrument and consider a two-period forward interest rate swap that starts at time. $t_{1}$ with $t_{0}<t_{1}$ , and that exchanges two fixed payments against the 12-month LIBOR rates, $L_{t_{1}}$ and $L_{t_{2}}$ Let the forward fixed payer swap rate for this period be denoted by $f_{t_{0}}$ . The spot swap rate, $s_{t_{1}}$ , will be observed at time. $t_{1}$ , while the forward swap rate is known at. $t_{0}$  

The buyer of the swaption has thus purchased the right to buy, at time $t_{1}$ , a fixed payer (spot) swap, with nominal value $N$ and payer swap rate. $f_{t_{0}}$ . If the strike price,. $\kappa$ , equals the ongoing forward swap rate for the time $t_{1}$ swap, this is called an ATM swaption. A forward fixed payer swap is contracted at time $t_{0}$ . The forward swap rate $f_{t_{0}}$ is set at time $t_{0}$ and the swap will start at time $t_{1}$ . The corresponding spot swap can be contracted at time $t_{1}$ .Thus, the swap rate $s_{t_{1}}$ is unknown as of $t_{0}$  

The ATM swaption involves the following transactions. No cash changes hands at time $t_{1}$ . The option premium is paid at $t_{0}$ If at time $t_{1}$ the spot swap rate, $s_{t_{1}}$ , turns out to be higher than the strike rate $f_{t_{0}}$ , the swaption holder will enter a fixed payer swap at the previously set rate $f_{t_{0}}$ . If the time $t_{1}$ spot swap rate $s_{t_{1}}$ is below $f_{t_{0}}$ , the option holder has an incentive to buy a new swap from the market since he or she will pay less. The swaption expires unexercised. Thus, ignoring the bid-ask spreads, suppose, at time $t_{1}$  

$$
f_{t_{0}}<s_{t_{1}}
$$  

the 2-year interest rate swap that pays $s_{t_{1}}$ against 12-month LIBOR will have a zero time $t_{1}$ value. This means that at time $t_{1}$ , the swaption holder can decide to pay $f_{t_{0}}$ , and receive $s_{t_{1}}$ . The time $t_{1}$ value of the resulting cash flows can be expressed as17  

$$
\left[{\frac{s_{t_{1}}-f_{t_{0}}}{\left(1+L_{t_{1}}\right)}}+{\frac{s_{t_{1}}-f_{t_{0}}}{\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}}\right]N
$$  

Note that at time $t_{1},L_{t_{1}}$ will be known, but $L_{t_{2}}$ would still be unknown. But, we know from ear-. lier chapters that we can "replace' this random variable by the forward rate for the period $[t_{2},t_{3}]$ that is known at time. $t_{1}$ . The forward rate $F\left(t_{1},t_{2}\right)$ is an unbiased estimator of $L_{t_{2}}$ under the forward measure P's:  

$$
F(t_{1},t_{2})=E_{t_{1}}^{\tilde{P}^{t_{3}}}\left[L_{t_{2}}\right]
$$  

Then, the time. $t_{1}$ value of a swap entered into at a predetermined rate $f_{t_{0}}$ will be  

$$
\left[{\frac{s_{t_{1}}-f_{t_{0}}}{(1+L_{t_{1}})}}+{\frac{s_{t_{1}}-f_{t_{0}}}{(1+L_{t_{1}})(1+F(t_{1},t_{2}))}}\right]N
$$  

This is zero if the swaption expires at-the-money, at time $t_{1}$ , with  

$$
s_{t_{1}}=f_{t_{0}}
$$  

Thus, we can look at the swaption as if it is an option written on the value of the cash flows in Eq. (17.5) as well. The ATM swaption on a fixed payer swap can then either be regarded as an option on the (forward) swap rate $f_{t_{0}}$ , or as an option on the value of a forward swap with strike price $\kappa=0$  

# 17.3.1 A CONTRACTUAL EQUATION  

As in the case of caps and floors, we can obtain a contractual equation that ties swaptions to forward swaps.  

We interpret this contractual equation the following way. Consider a forward payer swap with rate $f_{t_{0}}$ that starts at time $t_{1}$ and ends at time $t_{n+1}$ . The forward swap settles. $n$ times in between and makes (receives) the following sequence of cash payments in arrears:  

$$
\left\{\left(f_{t_{0}}-L_{t_{1}}\right)N\delta,...,\left(f_{t_{0}}-L_{t_{n}}\right)N\delta\right\}
$$  

This is regardless of whether $f_{t_{0}}<s_{t_{1}}$ or not.  

A payer swaption, on the other hand, makes these payments only if $f_{t_{0}}<s_{t_{1}}$ . To receive the cash flows in Eq. (17.8) when $f_{t_{0}}>s_{t_{1}}$ , one has to buy a receiver swaption..  
