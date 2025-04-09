# 22.5 DELTA HEDGING AND CORRELATION TRADING  

The delta is the sensitivity of the individual tranche spreads toward movements in the underlying index, $I_{t}$  

Let the tranche spreads at time $t$ be denoted by $\mathrm{cds}_{t}^{j}$ $j=e$ , m, s, sup. The superscript represents the equity, mezzanine, senior, and super senior tranches, respectively. There will then be (at least) two variables affecting the tranche spread: the probability of default and the default correlation. Let the average probability of default be denoted by. $p_{t}$ and the compound default correlation be $\rho_{t}$ We can write the index spread as a function of these two variables..  

$$
\mathrm{cds}^{i}=f^{i}(p_{t},\rho_{t})
$$  

It is important to remember that with changes in. $p_{t}$ the sign of the sensitivity is the same for all. tranches. As probability of default goes up, the tranche spreads will all go up, albeit in different degrees. The sensitivities with respect to the index (or probability of default) will be given by.  

$$
\Delta^{i}=\frac{\partial\mathrm{cds}_{t}^{i}}{\partial I_{t}}>0
$$  

or all $i.$ These constitute the tranche deltas with respect to the index itself. It is natural, given the evel of subordination in higher seniority tranches, to find that.  

$$
\Delta^{e}>\Delta^{m}>\Delta^{s}>\Delta^{\operatorname*{sup}}
$$  

Yet, the correlation sensitivity of the tranches is very different. As discussed earlier, even the sign changes.  

$$
\frac{\partial{\sf c d s}^{e}}{\partial\rho}<0
$$  

$$
\frac{\partial{\sf c d s}^{m}}{\partial\rho}\cong0
$$  

$$
\frac{\partial{\sf c d s}^{s}}{\partial\rho}>0
$$  

$$
\frac{\partial\mathrm{cds}^{\mathrm{sup}}}{\partial\rho}>0
$$  

According to this, the equity protection seller benefits if the compound default correlation goes. up. The super senior protection seller loses under these circumstances. The middle tranches are more or less neutral.  

Suppose the market participant desires to take a position positively responsive to $\rho_{t}$ but more or less neutral toward changes in $p_{t}$ . This is clearly a long correlation exposure discussed earlier. How would one put such a correlation trade on in practice? To do this the market practitioner would use the delta of the tranches with respect to the index. The position will consist of two hedging efforts.  

First, the right amounts of the equity and mezzanine tranches have to be purchased so that the portfolio is immune to changes in the default correlation. Second, each tranche should be hedged separately with respect to the changes in the index, as time passes.  

Let $N^{e}$ and $N^{m}$ be the two notional amounts.. $N^{e}$ is exposure on equity, while. $N^{m}$ is the exposure on the mezzanine tranche. What we want is a change in the index to not lead to a change in the total value of the position on these two tranches.  

Thus the portfolio $P_{t}$ will consist of selling default protection by the new amount  

$$
\begin{array}{r}{P_{t}=N^{e}-N^{m}}\end{array}
$$  

we let  

$$
N^{m}=\lambda N^{e}
$$  

where $\lambda$ is the hedge ratio to be selected. Substituting we obtain  

$$
P_{t}=N^{e}-\lambda_{t}N^{e}
$$  

$\lambda_{t}$ is the hedge ratio selected as  

$$
\uplambda_{t}=\frac{\Delta_{t}^{e}}{\Delta_{t}^{m}}
$$  

With this selection, the portfolio value will be immune to changes in the index value at time $t.$  

$$
\frac{\partial}{{\partial{I_{t}}}}{P_{t}}=\frac{\partial}{{\partial{I_{t}}}}{N^{e}}-\frac{\partial}{{\partial{I_{t}}}}{N^{m}}
$$  

Replacing from Eq. (22.67)  

$$
\frac{\partial}{\partial I_{t}}P_{t}=\Delta^{e}-\frac{\Delta^{e}}{\Delta^{m}}\Delta^{m}=0.
$$  

Hence the portfolio of selling $N^{E}$ units of equity protection and buying simultaneously $\setminus N^{E}$ units of the mezzanine protection is delta hedged. As the underlying index moves, the portfolio would be neutral to the first order of approximation. Also, as the market moves, the hedge ratio $\lambda_{t}$ would change and the delta hedge would need to be adjusted. This means that there will be gamma gains (losses).  

# 22.5.1 HOW TO CALCULATE DELTAS  

In the Black-Scholes world, deltas and other sensitivity factors are calculated by taking the appro-. priate derivatives of a function. This is often not possible in the credit analysis. In the case of tranche deltas, the approach is one of numerical calculation of sensitivity factors or of obtaining. closed-form solutions by approximations.  

One way is to use the Monte Carlo approach and one factor latent variable model to generate a sample $\{\boldsymbol{S}_{i}^{j}\}$ and then determine the tranche spread. These results would depend on an initially assumed index spread or default probability. To obtain delta one would divide the original value of the index by an amount $\Delta I$ and then repeat the valuation exercise. The difference in tranche spread. divided by $\Delta I$ will provide a numerical estimate for delta.  

# 22.5.2 GAMMA SENSITIVITY  

Volatility in the spread movements is an important factor. Actively managing delta positions sug-. gest that there may be gamma gains. The gamma effect seems to be most pronounced in the equity and senior tranches. There exist differences in gamma exposures depending on the particular tranche.  

Unlike options, one can distinguish three different types of gamma in the credit sector.  

. Gamma is defined as the portfolio convexity corresponding to a uniform relative shift in all the. underlying CDS spreads. iGamma is the individual gamma defined as the portfolio convexity resulting from one CDS spread moving independently of the others; i.e., one spread moves and the others remain constant. nGamma is the negative gamma defined as the portfolio convexity corresponding to a uniform relative shift in underlying CDS spreads, with half of the credits widening and half of the credits tightening by a uniform amount.  

Delta-hedged investors who are long correlation, benefiting if the correlation increases, will be long gamma while being short iGamma and nGamma.  

# 22.5.3 CORRELATION TRADE AND GAMMA GAINS  

Suppose one expects the compound default correlation to go up. This would be advantageous to the equity tranche protection seller and more or less neutral toward the mezzanine protection seller.10 Thus, one would take a long correlation exposure by selling. $N^{e}$ units of equity protection while simultaneously buying $N^{m}$ units of mezzanine exposure. The latter notional amount is determined according to  

$$
N^{m}=\lambda N^{e}
$$  

What would be the gains from such a position? What would be the risks? First, consider the gains.  

It turns out that such long correlation positions have positive carry, meaning that, even if the anticipated change in correlation does not materialize and the status quo continues, the position holder will make money. In fact, historically this positive carry was significant at around 200350 bp depending on the prevailing levels of the index $I_{t}$ and of the correlation $\rho_{t}$  

The position will also have positive gamma gains. As the delta hedge is adjusted, the hedge adjustments will monetize the. $I_{t}$ volatility because the long correlation position has, in fact, positive. convexity with respect to $I_{t}.$ In addition, the position will gain if the correlation goes up as. expected.  

The risks are related to iGamma effects and to the declining correlation. In both cases the position will suffer some losses, although these may not be big enough to make the overall return negative.  

Below we see an example of the gamma gains and dynamic delta hedging.  

# EXAMPLE: DELTA HEDGING AND GAMMA GAINS  

We are given the following information concerning iTraxx Index quotes. $(I_{t})$ and the deltas of the equity and mezzanine tranches at various levels of. $I.$ For example if the index is at. 30 bps, the equity tranche delta is 18.5, whereas the mezzanine tranche delta is 8.9.  

$I_{t}$ Delta of 0-3 Tranche Delta of 0-6 Tranche   


<html><body><table><tr><td></td><td></td></tr><tr><td>30 bps 18.5</td><td>8.9</td></tr><tr><td>35 bps 17.6</td><td>9.4</td></tr><tr><td>40 bps 15.1</td><td>10.1</td></tr></table></body></html>  

Now we use these to generate a dynamically adjusted series of delta hedges. Suppose we observe the following index movements across 3 days.  

$$
I_{1}=30,I_{2}=40,I_{3}=30
$$  

And suppose our notional is $N=100$ . Then a long correlation position will sell 100 units of equity protection and hedge this with $18.5/8.9\times100=207.865$ units of mezzanine protection.  

The resulting position will be delta neutral with respect to changes in $I,$  

During day 2, initially the position is not delta neutral since $I_{t}$ has moved to $40\mathrm{bps}$ . The correct hedge ratio is smaller at $15.1/10.1=4.6.$ The investor needs to reduce the long protection position on $I_{t}$ by $[(18.5{-}8.9){-}(15.1{-}10.1)]\times100$  

During day 3, this position reverts back to the original position on the index.  

Look what happened as a result of dynamic delta hedging of the tranche portfolio using the index. The investor sold protection when $I_{t}$ widened and bought it back when $I_{t}$ tightened. Clearly, these will lead to convexity gains similar to the case of options or long bonds.  
