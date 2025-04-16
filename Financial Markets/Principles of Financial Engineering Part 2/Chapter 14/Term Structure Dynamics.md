---
tags:
  - '#arbitrage_free_dynamics'
  - '#fixed_income_instruments'
  - '#forward_libor_model'
  - '#forward_measure'
  - '#girsanov_theorem'
  - '#libor_rates'
  - '#monte_carlo_simulation'
  - '#term_structure_dynamics'
---
# 14.4 TERM STRUCTURE DYNAMICS  

In the remainder of this chapter, we will see that the Forward LIBOR Model is the correct way to.   
approach term structure dynamics. The model is based on the idea of converting the dynamics of.   
each forward rate into a Martingale using some properly chosen forward measure. According to the.   
linkages between sectors shown in this chapter, once such dynamics are obtained, we can use them to generate dynamics for other fixed-income instruments.  

Most of the derivation associated with the Forward LIBOR Model is an application of the fundamental theorem of asset pricing discussed in Chapter 12. Thus, we continue to use the same finite-state world discussed in Chapter 12. The approach is mostly straightforward. There is only one aspect of Forward LIBOR or swap models that makes them potentially difficult to follow. Depending on the instruments, arbitrage-free dynamics of different forward rates may have to be expressed under the same forward measure. The methodology then becomes more complicated. It requires a judicious sequence of Girsanov-style measure changes to be applied to forward rate dynamics in some recursive fashion. Otherwise, arbitrage-free dynamics of individual forward rates would not be correctly represented.  

The Girsanov theorem is a powerful tool, but it is not easy to conceive such successive measure changes. Doing this within a discrete framework, in a discrete setting, provides a great deal of motivation and facilitates understanding of arbitrage-free dynamics. This is the purpose behind the second part of this chapter.  

# 14.4.1 THE FRAMEWORK  

We adopt a simple discrete framework and then extend it to general formulas. Consider a market where instruments can be priced and risk managed in discrete times that are $\delta$ apart:  

$$
t_{0}<t_{1}<\cdots<t_{n}=T
$$  

with  

$$
t_{i}-t_{i-1}=\delta
$$  

Initially, we concentrate on the first three times, $t_{0},t_{1}$ , and $t_{2}$ that are $\delta$ apart. In this framework, we consider four simple fixed-income securities:  

1. A default-free zero-coupon bond $B(t_{0},t_{2})$ that matures at time $t_{2}$   
2. A default-free zero-coupon bond that matures one period later, at time $t_{3}$ Its current price is expressed as $B(t_{0},t_{3})$   
3. A savings account that pays (in-arrears) the discrete-time simple rate $L_{t_{i}}$ observed at time $t_{i}$ Therefore, the savings account payoff at. $t_{2}$ will be  

$$
R_{t_{2}}=\left(1+\delta L_{t_{0}}\right)\left(1+\delta L_{t_{1}}\right)
$$  

Note that the $L_{t_{1}}$ observed from the initial time $t_{0}$ will be a random variable.  

4. An FRA contracted at time $t_{0}$ and settled at time. $t_{2}$ , where the buyer receives/pays the differential between the fixed rate $\boldsymbol{F}(t_{0},t_{1})$ and the floating rate. $L_{t_{1}}$ at time $t_{2}$ We let the. notional amount of this instrument equal 1 and abbreviate the forward rate to $F_{t_{0}}$ The final. payoff can be written as  

$$
\left(\boldsymbol{L}_{t_{1}}-\boldsymbol{F}_{t_{0}}\right)\delta
$$  

These assets can be organized in the following payoff matrix. $D$ for time $t_{2}$ as in Chapter 12, assuming that at every $t_{i}$ , from every node there are only two possible movements for the underlying random process. Denoting these movements by u, d, we can write13.  

$$
D=\left[\begin{array}{c c c c}{{R_{t_{2}}^{u u}}}&{{R_{t_{2}}^{u d}}}&{{R_{t_{2}}^{d u}}}&{{R_{t_{2}}^{d d}}}\ {{1}}&{{1}}&{{1}}&{{1}}\ {{B_{t_{2}}^{u u}}}&{{B_{t_{2}}^{u d}}}&{{B_{t_{2}}^{d u}}}&{{B_{t_{2}}^{d d}}}\ {{\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}}&{{\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}}&{{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}}&{{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}}\end{array}\right]
$$  

where the $B_{t_{2}}^{i j}$ is the (random) value of the $t_{3}$ maturity discount bond at time $t_{2}$ . This value will be state dependent at $t_{2}$ because the bond matures one period later, at time $t_{3}$ Looked at from time $t_{0}$ this value will be random. Clearly, with this. $D$ matrix we have simplified the notation significantly.. We are using only four states of the world, expressing the forward rate $F(t_{0},t_{2})$ simply as $F_{t_{0}}$ , and the $B(t_{2},t_{3})^{i j}$ simply as $B_{t_{2}}^{i j}$  

If the FRA, the savings account, and the two bonds do not admit any arbitrage opportunities, the fundamental theorem of asset pricing permits the following linear representation:.  

$$
\left[{\begin{array}{c}{1}\ {B(t_{0},t_{2})}\ {B(t_{0},t_{3})}\ {0}\end{array}}\right]=\left[{\begin{array}{c c c c}{R_{t_{2}}^{u u}}&{R_{t_{2}}^{u d}}&{R_{t_{2}}^{d u}}&{R_{t_{2}}^{d d}}\ {1}&{1}&{1}&{1}\ {B_{t_{2}}^{u u}}&{B_{t_{2}}^{u d}}&{B_{t_{2}}^{d u}}&{B_{t_{2}}^{d d}}\ {\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}\end{array}}\right]\left[{\begin{array}{c}{Q^{u u}}\ {Q^{u d}}\ {Q^{d u}}\ {Q^{d d}}\end{array}}\right]
$$  

where $\{Q^{i j},i,j=u,d\}$ are the four state prices for period $t_{2}$ . Under the no-arbitrage condition, the latter exist and are positive  

$$
Q^{i j}>0
$$  

for all states $i,j$ 14  

This matrix equation incorporates the ideas that (i) the fair market value of an FRA is zero at initiation, (ii) 1 dollar is to be invested in the savings account originally, and (ili) the bonds are default free. They mature at times $t_{2}$ and $t_{3}$ $R_{t_{2}}^{i,j}$ ,finally, represents the gross returns to the savings account as of time $t_{2}$ . Because the interest rate that applies to time $t_{i}$ is paid in arrears, at time $t_{i}+\delta$ , we can express these gross returns as functions of the underlying LIBOR rates in the following way:  

$$
R_{t_{2}}^{u u}=R_{t_{2}}^{u d}=\left(1+\delta L_{t_{0}}\right)\left(1+\delta L_{t_{1}}^{u}\right)
$$  

and  

$$
R_{t_{2}}^{d d}=R_{t_{2}}^{d u}=\left(1+\delta L_{t_{0}}\right)\left(1+\delta L_{t_{1}}^{d}\right)
$$  

We now present the LIBOR market model and the associated measure change methodology within this simple framework. The framework can be used to conveniently display most of the important tools and concepts that we need for fixed-income engineering. The first important concept that we need is the forward measure introduced in Chapter 12.  

# 14.4.2 NORMALIZATION AND FORWARD MEASURE  

To obtain the $t_{2}$ and $t_{3}$ forward measures, it is best to begin with a risk-neutral probability, and show why it is not a good working measure in the fixed-income environment described earlier. We can then show how to convert the risk-neutral probability to a desired forward measure explicitly.  

# 14.4.2.1 Risk-neutral measure is inconvenient  

As usual, define the risk-neutral measure $\{\tilde{p}_{i j}\}$ using the first row of the matrix equation:  

$$
1=R_{t_{2}}^{u u}Q^{u u}+R_{t_{2}}^{u d}Q^{u d}+R_{t_{2}}^{d u}Q^{d u}+R_{t_{2}}^{d d}Q^{d d}
$$  

Relabel  

$$
\begin{array}{r}{\tilde{p}_{u u}=R_{t_{2}}^{u u}Q^{u u}}\ {\tilde{p}_{u d}=R_{t_{2}}^{u d}Q^{u d}}\ {\tilde{p}_{d u}=R_{t_{2}}^{d u}Q^{d u}}\ {\tilde{p}_{d d}=R_{t_{2}}^{d d}Q^{d d}}\end{array}
$$  

The $\{\tilde{p}_{i j}\}$ then have the characteristics of a probability distribution, and they can be exploited with the associated Martingale equality.  

We know from Chapter 12 that, under the condition that every asset's price is arbitrage free, $\{Q^{i j},i,j=u,d\}$ exist and are all positive, and $\tilde{p}_{i j}$ will be the risk-neutral probabilities. Then, by using the last row of the system in Eq. (14.58) we can write the following equality:  

$$
\begin{array}{l}{{0=\displaystyle\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)\frac1{R_{t_{2}}^{u u}}\right]\tilde{p}_{u u}+\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)\frac1{R_{t_{2}}^{u d}}\right]\tilde{p}_{u d}+\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)\frac1{R_{t_{2}}^{d u}}\right]\tilde{p}_{d u}}}\ {{\mathrm{~}+\displaystyle\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)\frac1{R_{t_{2}}^{d d}}\right]\tilde{p}_{d d}}}\end{array}
$$  

Here, $\left(F_{t_{0}}-L_{t_{1}}^{i}\right),i=u,d$ are "normalized" so that. $Q^{i j}$ can be replaced by the respective $\tilde{p}_{i j}$ . Note that in this equation,. $F_{t_{0}}$ is determined at time. $t_{0}$ , and can be factored out. Grouping and rearranging, we get  

$$
F_{t_{0}}=\frac{\left(\left[L_{t_{1}}^{u}\left(1/R_{t_{2}}^{u u}\right)\right]\tilde{p}_{u u}+\left[L_{t_{1}}^{u}\left(1/R_{t_{2}}^{u d}\right)\right]\tilde{p}_{u d}+\left[L_{t_{1}}^{d}\left(1/R_{t_{2}}^{d u}\right)\right]\tilde{p}_{d u}+\left[L_{t_{1}}^{d}\left(1/R_{t_{2}}^{d d}\right)\right]\tilde{p}_{d d}\right)}{\left(\left(1/R_{t_{2}}^{u u}\right)\tilde{p}_{u u}+\left(1/R_{t_{2}}^{u d}\right)\tilde{p}_{u d}+\left(1/R_{t_{2}}^{d u}\right)\tilde{p}_{d u}+\left(1/R_{t_{2}}^{d d}\right)\tilde{p}_{d d}\right)}
$$  

This can be written using the expectation operator  

$$
F_{t_{0}}=\frac{1}{E_{t_{0}}^{\tilde{P}}\left[1/R_{t_{2}}\right]}E_{t_{0}}^{\tilde{P}}\left[\frac{L_{t_{1}}}{R_{t_{2}}}\right]
$$  

According to this last equality, if $R_{t_{2}}$ is a random variable and is not independent ofd $L_{t_{1}}$ 15 it cannot be moved outside the expectation operator. In other words, for general $i$  

$$
F(t,t_{i})\neq E_{t}^{\tilde{P}}[L_{t_{i}}]\quad t<t_{i}
$$  

That is to say, under the risk-neutral measure, $\tilde{P}$ , the forward rate for time $t_{i}$ is a biased "fore-. cast' of the future LIBOR rate. $L_{t_{i}}$ . In fact, it is not very difficult to see that the. $E_{t}^{\tilde{p}}[L_{t_{i}}]$ is the futures. rate that will be determined by, say, a Eurodollar contract at time $i$ The "bias' in the forward rate,. therefore, is associated with the convexity adjustment..  

Another way of putting it is that. $F_{t}$ is not a Martingale with respect to the risk-neutral probabil-. ity $\tilde{P}$ and that a discretized stochastic difference equation that represents the dynamics of $F_{t}$ will, in general, have a trend:.  

$$
F_{t+\Delta}-F_{t}=a(F_{t},t)F_{t}\Delta+\sigma(F_{t},t)F_{t}[W_{t+\Delta}-W_{t}]
$$  

where $a(F_{t},t)$ is the non-zero expected rate of change of the forward rate under the probability $\tilde{P}$  

The fact that $F_{t}$ is not a Martingale with respect to probability $\tilde{P}$ makes the risk-neutral measure an inconvenient working tool for pricing and risk management in the fixed-income sector. Before we can use Eq. (14.71), we need to calibrate the drift factor $a(.)$ . This requires first obtaining a functional form for the drift under the probability. $\tilde{P}$ The original HJM article does develop a functional form for such drifts using continuously compounded instantaneous forward rates. But, this. creates an environment quite different from LIBOR-driven markets and the associated actuarial rates Ly, used here.16  

On the other hand, we will see that in the interest rate sector, arbitrage-free drifts become much easier to calculate if we use the Forward LIBOR Model and switch to appropriate forward measures.  

# 14.4.2.2 The forward measure  

Consider defining a new set of probabilities for the states under consideration by using the defaultfree zero-coupon bond that matures at time. $t_{2}$ . First, we present the simple case. Use the second. row of the system in Eq. (14.58):  

$$
B(t_{0},t_{2})=Q^{u u}+Q^{u d}+Q^{d u}+Q^{d d}
$$  

and then divide every element by $B(t_{0},t_{2})$ . Renaming, we get the forward $t_{2}$ measure $\tilde{P}^{t_{2}}$  

$$
1=\tilde{p}_{u u}^{t_{2}}+\tilde{p}_{u d}^{t_{2}}+\tilde{p}_{d u}^{t_{2}}+\tilde{p}_{d d}^{t_{2}}
$$  

where the probability of each state is obtained by scaling the corresponding $Q^{i j}$ using the time $t_{0}$ price of the corresponding bond:  

$$
\tilde{p}_{i j}^{t_{2}}=\frac{Q^{i j}}{B(t_{0},t_{2})}
$$  

It is important to index the forward measure with the superscript,. $t_{2}$ , in these fixed-income models, as other forward measures would be needed for other forward rates. The superscript is a. nice way of keeping track of the measure being used. For some instruments, these measures have to be switched sequentially.  

As discussed in Chapter 12, using the $t_{2}$ -forward measure we can price any asset $C_{t},$ with time $t_{2}$ payoff s $C_{t_{2}}^{i j}$  

$$
C_{t_{0}}=\left[B(t_{0},t_{2})C_{t_{2}}^{u u}\right]\tilde{p}_{u u}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{u d}\right]\tilde{p}_{u d}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{d u}\right]\tilde{p}_{d u}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{d d}\right]\tilde{p}_{d d}^{t_{2}}
$$  

This implies that, for an asset that settles at time $T$ and has no other payouts, the general pricing equation is given by  

$$
C_{t}=B(t,T)E_{t}^{\tilde{P}T}[C_{T}]
$$  

where $\tilde{P}^{T}$ is the associated $T$ forward measure and where $C_{T}$ is the time. $T$ payoff. According to this. equality, it is the ratio  

$$
Z_{t}=\frac{C_{t}}{B(t,T)}
$$  

which is a Martingale with respect to the measure $\tilde{P}^{T}$ . In fact, $B(t,T)$ being the discount factor for time $T.$ and, hence, being ${<}1$ $Z_{t}$ is nothing more than the. $T$ forward value of the. $C_{t}$ This means. that the forward measure. $\tilde{P}^{T}$ operates in terms of Martingales that are measured in time. $T$ dollars.e The advantage of the forward. $\mathbf{\tilde{\rho}}^{T}$ measure becomes clear if we apply the same transformation to. price the FRA as was done earlier for the case of the risk-neutral measure.  

# 14.4.2.3 Arbitrage-free SDEs for forward rates  

To get arbitrage-free dynamics for forward rates, we now go back to the simple model in Eq. (14.58). Divide the fourth row of the system by. $B(t_{0},t_{2})$ and rearrange,  

$$
\begin{array}{c}{{\displaystyle\frac{F_{t_{0}}}{B(t_{0},t_{2})}\left[Q^{u u}+Q^{u d}+Q^{d u}+Q^{d d}\right]=\frac{L_{t_{1}}^{u}}{B(t_{0},t_{2})}Q^{u u}+\frac{L_{t_{1}}^{u}}{B(t_{0},t_{2})}Q^{u d}}}\ {{\displaystyle~+\frac{L_{t_{1}}^{d}}{B(t_{0},t_{2})}Q^{d u}+\frac{L_{t_{1}}^{d}}{B(t_{0},t_{2})}Q^{d d}}}\end{array}
$$  

Now, as done in Chapter 12, substitute the $t_{2}$ forward measure into this equation using the equality:  

$$
\tilde{p}_{i j}^{t_{2}}=\frac{1}{B(t_{0},t_{2})}Q^{i j}
$$  

The equation becomes  

$$
F_{t_{0}}=[L_{t_{1}}^{u}]\tilde{p}_{u u}^{t_{2}}+[L_{t_{1}}^{u}]\tilde{p}_{u d}^{t_{2}}+[L_{t_{1}}^{d}]\tilde{p}_{d u}^{t_{2}}+[L_{t_{1}}^{d}]\tilde{p}_{d d}^{t_{2}}
$$  

Extending this to the general case of $m$ discrete states  

$$
F_{t_{0}}=\sum_{i=1}^{m}L_{t_{1}}^{i}{\tilde{p}}_{i}^{t_{2}}
$$  

This is clearly the expectation  

$$
F_{t_{0}}=E_{t_{0}}^{\tilde{P}^{t_{2}}}[L_{t_{1}}]
$$  

This means that, under the measure $\tilde{P}^{t_{2}}$ , the forward rate for the period $[t_{1},t_{2}]$ will be an unbiased estimate of the corresponding LIBOR rate.  

Consequently, switching to the general notation of $(t,T)$ , the process  

$$
F_{t}=F(t,T,T+\delta)
$$  

will be a Martingale under the $(T+\delta)$ forward measure $\tilde{P}^{T+\delta}$ Assuming that the errors due to iscretization are small, its dynamics can be described by a (discretized) SDE over small intervals of length $\Delta^{17}$  

$$
F_{t+\Delta}-F_{t}=\sigma_{t}F_{t}\Delta W_{t}
$$  

where $W_{t}$ is a Wiener process under the measure $\tilde{P}^{T+\delta}\cdot\Delta W_{t}$ is the Wiener process increment:  

$$
\Delta W_{t}=W_{t+\Delta}-W_{t}
$$  

This (approximate) equation has no drift component since, by arbitrage arguments, and writing for the general $t,T,$ we have  

$$
1+\delta F(t,T)=\frac{B(t,T)}{B(t,T+\delta)}
$$  

It is clear from the normalization arguments of Chapter 12 that, under the measure $\tilde{P}^{T+\delta}$ and nosmalira $\tilde{P}^{T+\delta}$ $B(t,T+\delta)$ will have no drift.  

However, note that the forward rate for the period $[T-\delta,T]$ given by  

$$
1+\delta F(t,T-\delta)=\frac{B(t,T-\delta)}{B(t,T)}
$$  

is not a Martingale under the same forward measure $\tilde{P}^{T+\delta}$ . Instead, this forward rate is a Martingale. under its own measure. $\tilde{P}^{T}$ which requires normalization by. $B(t,T)$ . Thus, we get a critical result for the Forward LIBOR Model:  

Each forward rate F(, T) admits a Martingale representation under its own forward measure P"+  

This means that each forward rate dynamics can be approximated individually by a difference. equation with no drift given the proper normalization. The only parameter that would be needed to characterize such dynamics is the corresponding forward rate volatility..  

# 14.4.3 ARBITRAGE-FREE DYNAMICS  

The previous section discussed the dynamics of forward rates under their own forward measure. We now show what happens when we use one forward measure for two forward rates that apply to two consecutive periods. Then, one of the forward rates has to be evaluated under a measure different from its own, and the Martingale dynamics will be broken. Yet, we will be able to obtain the new drift.  

To keep the issue as simple as possible, we continue with the basic model in Eq. (14.58), except we add one more time period so that we can work with two nontrivial forward rates and their respective forward measures. This is the simplest setup within which we can show how measure change technology can be implemented. Using the forward measures introduced earlier and shown in Figure 14.4, we can now define the following forward rate dynamics for the two forward LIBOR processes $\{F(t_{0},t_{1}),F(t_{0},t_{2})\}$ under consideration. The first will be a Martingale under the normalization with $B(t_{0},t_{2})$ , whereas the second will be a Martingale under the normalization with $B(t_{0},t_{3})$ This means thate $\tilde{P}^{t_{2}}$ and $\tilde{P}^{t_{3}}$ are the forward LIBOR processes' "own' measures.  

Altogether, it is important to realize that during the following discussion we are working with a very simple example involving only four time periods, $t_{0},t_{1},t_{2}$ and $t_{3}$ . We start with the arbitrage-free  

![](images/974b98282b49d5ac26647c0312c5dfdbdd29a3c8497b8e3358913fa4c0e3fc47.jpg)  

# FIGURE 14.4  

Spot and forward LIBOR process.  

"dynamics" of the forward rate $F(t_{0},t_{2})$ . In our simplified setup, we will observe only two future values of this forward rate at times $t_{1}$ and $t_{2}$ . These are given by  

$$
\begin{array}{r}{F(t_{1},t_{2})-F(t_{0},t_{2})=\sigma_{2}F(t_{0},t_{2})\Delta W_{t_{1}}^{t_{3}}}\ {F(t_{2},t_{2})-F(t_{1},t_{2})=\sigma_{2}F(t_{1},t_{2})\Delta W_{t_{2}}^{t_{3}}}\end{array}
$$  

The superscript in. $\Delta W_{t_{i}}^{t_{3}},i=1,2$ indicates that the Wiener process increments have zero mean under the probability $\tilde{P}^{t_{3}}$ . These equations show how the "current' value of the forward rate $F(t_{0},t_{2})$ first changes to become $F(t_{1},t_{2})$ and then ends up as $F(t_{2},t_{2})$ . The latter is also. $L_{t_{2}}$  

For the "nearer' forward rate. $\boldsymbol{F}(t_{0},t_{1})$ , we need only one equation18 defined under the normali. zation with the bond. $B(t_{0},t_{2})$ (i.e., the $\tilde{P}^{t_{2}}$ measure) and the associated zero drift:.  

$$
F(t_{1},t_{1})-F(t_{0},t_{1})=\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{2}}
$$  

Similarly, the superscript in $\Delta W_{t_{1}}^{t_{2}}$ indicates that this Wiener process increment has zero mean under the probability $\tilde{P}^{t_{2}}$ . Here, the $\boldsymbol{F}(t_{1},t_{1})$ is also the LIBOR rate $L_{t_{1}}$ . We reemphasize that each dynamic is defined under a different probability measure. Under these different forward measures, each forward LIBOR process behaves like a Martingale.19 Consequently, there are no drift terms in either equation.  

Fortunately, as long as we can work with these equations separately, no arbitrage-free drift terms need to be estimated or calibrated. The only parameters we need to determine are the volatilities of the two forward rates: $\sigma_{2}$ for the forward rate $F(t_{0},t_{2})$ and $\sigma_{1}$ for the forward rate $\boldsymbol{F}(t_{0},t_{1})$ 20  

In fact, each Wiener increment has a zero expectation under its own measure. For example, the Wiener increments of the two forward rates will satisfy, for time $t_{0}<t_{1}$  

$$
E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\Delta W_{t_{1}}^{t_{2}}\right]=0
$$  

and  

$$
E_{t_{0}}^{\tilde{P}^{t_{3}}}\left[\Delta W_{t_{1}}^{t_{3}}\right]=0
$$  

Yet, when we evaluate the expectations under $\tilde{P}^{t_{2}}$ , we get  

$$
E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\Delta W_{t_{1}}^{t_{2}}\right]=0
$$  

and  

$$
E_{t_{0}}^{\tilde{P}^{l_{2}}}\left[\Delta W_{t_{1}}^{t_{3}}\right]=\lambda_{t_{0}}^{t_{2}}\Delta\neq0
$$  

Here, $\lambda_{t_{0}}^{t_{2}}$ is a mean correction that needs to be made because we are evaluating the Wiener increment under a measure different from its own forward measure. $\tilde{P}^{t_{3}}$ . This, in turn, means that the. dynamics for $F(t_{0},t_{2})$ lose their Martingale characteristic..  

We will now comment on the second moments, variances, and covariances. Each Wiener increment is assumed to have the same variance under the two measures. The Girsanov theorem ensures that this is true in continuous time. In discrete time, this holds as an approximation. Finally, we are operating in an environment where there is only one factor.21 So, the Wiener process increments defined under the two forward measures will be exactly correlated if they belong to the same time period. In other words, although their means are different, we can assume that, approximately, their covariance would be $\Delta$  

$$
E^{\tilde{P}^{I3}}\left[\Delta W_{t}^{t_{3}}\Delta W_{t}^{t_{2}}\right]=E^{\tilde{P}^{I_{2}}}\left[\Delta W_{t}^{t_{3}}\Delta W_{t}^{t_{2}}\right]=\Delta
$$  

Similar equalities will hold for the variances as well.22  

# 14.4.3.1 Review  

The results thus far indicate that for the pricing and risk managing of equity-linked assets, the riskneutral measure $\tilde{P}$ may be quite convenient since it is easily adaptable to lognormal models where the arbitrage-free drifts are simple and known functions of the risk-free interest rate. As far as equity products are concerned, the assumption that short rates are constant is a reasonable approximation, especially for short maturities. Yet, for contracts written on future values of interest rates (rather than on asset prices), the use of the $\tilde{P}$ leads to complex arbitrage-free dynamics that cannot be captured easily by Martingales and, hence, the corresponding arbitrage-free drift terms may be difficult to calibrate.  

Appropriate forward measures, on the other hand, result in Martingale equalities and lead to.   
dynamics convenient for the calculation of arbitrage-free drifts, even when they are not zero.   
Forward (and swap) measures are the proper working probabilities for fixed-income environments..  

# 14.4.4 A MONTE CARLO IMPLEMENTATION  

Suppose we want to generate Monte Carlo "paths' from the two discretized SDEs for two forward rates, $\boldsymbol{F}(t_{i},t_{1})$ and $F(t_{i},t_{2})$  

$$
\begin{array}{r}{F(t_{i},t_{1})-F(t_{i-1},t_{1})=\sigma_{1}F(t_{i-1},t_{1})\Delta W_{t_{i}}^{t_{2}}}\ {F(t_{i},t_{2})-F(t_{i-1},t_{2})=\sigma_{2}F(t_{i-1},t_{2})\Delta W_{t_{i}}^{t_{3}}}\end{array}
$$  

where $i=1$ , 2 for the second equation and $i=1$ for the first..  

It is easy to generate individual paths for the two forward rates separately by using these Martingale equations defined under their own forward measures. Consider the following approach.  

Suppose volatilities $\sigma_{1}$ and $\sigma_{2}$ can be observed in the market. We select two random variables $\{\Delta W_{1}^{3},\Delta W_{2}^{3}\}$ from the distribution  

$$
\Delta W_{i}^{3}\sim N(0,\Delta)
$$  

with a pseudo-random number generator, and then calculate, sequentially, the randomly generated forward rates in the following order, starting with the observed $F(t_{0},t_{2})$  

$$
\begin{array}{c}{{F(t_{1},t_{2}){}^{1}=F(t_{0},t_{2})+\sigma_{2}F(t_{0},t_{2})\Delta W_{1}^{3}}}\ {{{}}}\ {{F(t_{2},t_{2}){}^{1}=F(t_{1},t_{2}){}^{1}+\sigma_{2}F(t_{1},t_{2}){}^{1}\Delta W_{2}^{3}}}\end{array}
$$  

where the superscript on the left-hand side indicates that these values are for the first Monte Carlo. trajectory. Proceeding sequentially, all the terms on the right-hand side will be known. This gives the first simulated "path" $\{F(t_{0},\dot{t_{2}}),F(t_{1},t_{2})^{1},F(t_{2},t_{2})^{1}\}$ We can repeat this algorithm to obtain $M$ such paths for potential use in pricing.  

What does this imply for the other forward LIBOR process $F$ $F(t_{0},t_{1})?$ Can we use the same ran-. domly generated random variable $\Delta W_{1}^{3}$ in the Martingale equation for $\boldsymbol{F}(t,t_{1})$ , and obtain the first. "path" $\{F(t_{0},t_{1}),\mathrm{F}(t_{1},t_{1})^{1}\}$ from  

$$
F(t_{1},t_{1})=F(t_{0},t_{1})+\sigma_{1}F(t_{0},t_{1})\Delta W_{1}^{3}
$$  

The answer is no. As mentioned earlier, the Wiener increments $\left\{\Delta W_{t_{1}}^{t_{2}}\right\}$ have zero mean only. under the probability $\tilde{P}^{t_{2}}$ . But, the first set of random variables was selected using the measure $\tilde{P}^{t\tilde{3}}$ Under $\tilde{P}^{t_{2}}$ , these random variables do not have zero mean, but are distributed as  

$$
N\big(\lambda_{t_{0}}^{t_{2}}\Delta,\Delta\big)
$$  

Thus, if we use the same. $\Delta W_{1}^{3}$ in Eq. (14.99), then we need to correct for the term $\lambda_{t_{0}}^{t_{2}}\Delta$ . To do this, we need to calculate the numerical value of. $\lambda_{t_{0}}^{t_{2}}$  

Once this is done, the dynamics for $\boldsymbol{F}(t_{0},t_{1})$ can be written as  

$$
F(t_{1},t_{1})=F(t_{0},t_{1})-\sigma_{1}F(t_{0},t_{1})\big(\lambda_{t_{0}}^{t_{2}}\Delta\big)+\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{3}}
$$  

To see why this is so, take the expectation under $\tilde{P}^{t_{2}}$ on the right-hand side and use the information in Eq. (14.100):  

$$
\begin{array}{r}{E_{t_{1}}^{\tilde{P}^{2}}\left[F(t_{0},t_{1})-\sigma_{1}F(t_{0},t_{1})\big(\lambda_{t_{0}}^{t_{2}}\Delta\big)+\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{3}}\right]=F(t_{0},t_{1})}\end{array}
$$  

Thus, we get the correct result under the $\tilde{P}^{t_{2}}$ , after the mean correction. It is obvious that we need to determine these correction factors before the randomly generated Brownian motion increments can be used in all equations.  

Yet, note the following simple case. If the instrument under consideration has additive cash flows where each cash flow depends on a single forward rate, then individual zero-drift equations can be used separately to generate paths. This applies for several liquid instruments. For example, FRAs and especially swaps have payment legs that depend on one LIBOR rate only. Individual zero-drift equations can be used for valuing each leg separately, and then these values can be added using observed zero-coupon bond prices,. $B(t,T_{i})$ . However, this cannot be done in the. case of CMSs, for example, because each settlement leg will depend nonlinearly on more than one forward rate.  

We now discuss further how mean corrections can be conducted so that all forward rates are. projected using a single forward measure. This will permit pricing instruments where individual cash flows depend on more than one forward rate..  
