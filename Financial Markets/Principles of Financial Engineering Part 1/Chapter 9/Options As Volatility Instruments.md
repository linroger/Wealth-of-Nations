---
tags:
  - '#black_scholes_pde'
  - '#cash_flows'
  - '#delta_hedging'
  - '#european_call_option'
  - '#implied_volatility'
  - '#market_maker'
  - '#options_volatility'
  - '#time_value'
  - '#vega_risk'
---
# 9.4 OPTIONS AS VOLATILITY INSTRUMENTS  

In this section we see how convexity is translated into cash earnings, as. $S_{t}$ oscillates and creates time value. The discussion is conducted in a highly simplified environment to facilitate under-. standing of the relationship between volatility and cash gains (losses) of long (short) option positions.  

Consider a market maker who quotes two-way prices for a European vanilla call option. $C(t)$ with strike $K$ , and expiration $T.$ written on a nondividend paying asset, denoted by. $S_{t}$ 7 Let the riskfree interest rate $r$ be constant. For simplicity, consider an ATM option,. $K=S_{t}$ . In the following, we first show the initial steps taken by the market maker who buys an option. Then, we show how the market maker hedges this position dynamically and earns some cash due to. $S_{t}$ oscillations.  

# 9.4.1 INITIAL POSITION AND THE HEDGE  

Suppose this market maker buys a call option from a client. The initial position of the market.   
maker is shown in the top portion of Figure 9.4. It is a standard long call position. The market.   
maker is not an investor or speculator, and this option is bought with the purpose of keeping it on the books and then selling it to another client. Hence, some mechanical procedures should be fol-..   
lowed. First, the market maker needs to fund this position. Second, he or she should hedge the asso-.   
ciated risks.  

![](4be6206a37b55ffa1e3ea26352bd21ae99975b9ae33141832707cf54b4258e4e.jpg)  

# FIGURE 9.4  

Funding a long call position with borrowing.  

We start with the first requirement. Unlike the end investor, market makers never have "money" of their own. The trade needs to be funded. There are at least two ways of doing this. One is to short an appropriate asset in order to generate the needed funds, while the other is to borrow these funds directly from the money market desk.' Suppose the second possibility is selected and the market maker borrows $C(t)$ dollars from the money market desk at an interest rate. $r_{t}=r$ .The net position that puts together the option and the borrowed funds is shown in the bottom part of Figure 9.4.  

Now, consider the risks of the position. It is clear from Figure 9.4 that the long call position funded by a money market loan is similar to going long the. $S_{t}$ If $S_{t}$ decreases, the position's value will decrease, and a market maker who takes such positions many times on a given day cannot. afford this. The market maker must hedge this risk by taking another position that will offset these possible gains or losses. When $S_{t}$ declines, a short position in $S_{t}$ gains. As $S_{t}$ changes by $\Delta S_{t}$ a short position will change by. $-\Delta S_{t}$ . Thus, we might think of using this short position as a hedge..  

But there is a potential problem. The long call position is described by a curve, whereas the short position in $S_{t}$ is represented by a line. This means that the responses of $C(t)$ and $S_{t}.$ to a change in $S_{t}$ , are not going to be identical. Everything else being the same, if the underlying. changes by $\Delta S_{t}$ , the change in the option price will be approximately!.  

$$
\Delta C(t)\cong C_{s}\Delta S_{t}
$$  

The change in the short position on the other hand will equal $-\Delta S_{t}$ In fact, the net response of the portfolio  

$$
V_{t}=\{\log C(t),\mathrm{short}S_{t}\}
$$  

to a small change in. $S_{t}$ will be given by the first-order approximation,  

$$
\begin{array}{r}{\Delta V_{t}\cong C_{s}\Delta S_{t}-\Delta S_{t}}\ {}\ {=(C_{s}-1)\Delta S_{t}<0}\end{array}
$$  

due to the condition $0<C_{s}<1$ . This position is shown in Figure 9.5. It is still a risky position and, interestingly, the risks are reversed. The market maker will now lose money if $S_{t}$ increases. In fact, this position amounts to a long put financed by a money market loan.  

How can the risks associated with the movements in. $S_{t}$ be eliminated? In fact, consider Figure 9.5. We can approximate the option value by using the tangent at point. $S_{t}=K.$ This would. also be a line. We can then adjust the short position accordingly. According to Eq. (9.14), short selling one unit of. $S_{t}$ overdid the hedge. Figure 9.5 suggests that the market maker should short. $h_{t}$ units of $S_{t}.$ selecting the $h_{t}$ according to  

$$
h_{t}=\frac{\partial C(S_{t},t)}{\partial S_{t}}=C_{s}
$$  

To see why this might work, consider the new portfolio, $V_{t}$  

If $S_{t}$ changes by $\Delta S_{t},$ everything else being the same, the change in this portfolio's value will be approximately  

$$
\Delta V_{t}\cong[C(S_{t}+\Delta S_{t},t)-C(S_{t},t)]-C_{s}\Delta S_{t}
$$  

![](e35be0d6d9c9a240d92f377f3aa77d9baa4d55ae34a6da3890c678da3610fe2d.jpg)  

# FIGURE 9.5  

Long call and short futures position.  

We can use a first-order Taylor series approximation of $C(S_{t}+\Delta S_{t},t)$ , around point $S_{t},$ to sim plify this relationship:11  

$$
C(S_{t}+\Delta S_{t},t)=C(S_{t},t)+\frac{\partial C(S_{t},t)}{\partial S_{t}}\Delta S_{t}+R
$$  

Here, $R$ is the remainder. The right-hand side of this formula can be substituted in Eq. (9.17) to obtain  

$$
\Delta V_{t}\cong\left[\frac{\partial C(S_{t},t)}{\partial S_{t}}\Delta S_{t}+R\right]-C_{s}\Delta S_{t}
$$  

After using the definition  

$$
\frac{\partial C(S_{t},t)}{\partial S_{t}}=C_{s}
$$  

and simplifying, this becomes  

$$
\Delta V_{t}\cong R
$$  

That is to say, this portfolio's sensitivity toward changes in. $S_{t}$ will be the remainder term, $R$ . It is related to Ito's Lemma, shown in Appendix 9.2. The biggest term in the remainder is given by  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S_{t})^{2}
$$  

Since the second partial derivative of $C(t)$ is always positive, the portfolio's value will always. be positively affected by small changes in $S_{t}$ This is shown in the bottom part of Figure 9.6. A portfolio such as this one is said to be delta neutral. That is to say, the delta exposure, represented by the first-order sensitivity of the position to changes in. $S_{t}$ , is zero. Note that during this discussion the time variable, $t.$ was treated as a constant.  

This way of constructing a hedge for options is called delta hedging and $h_{t}$ is called the hedge ratio. It is important to realize that the procedure will need constant updating of the hedge ratio, $h_{t}$ as time passes and $S_{t}$ changes. After all, the idea depends on a first-order Taylor series approximation of a nonlinear instrument using a linear instrument. Yet, Taylor series approximations are local and they are satisfactory only for a reasonable neighborhood around the initial $S_{t}$ As $S_{t}$ changes, the approximation needs to be adjusted. Consider Figure 9.7. When $S_{t}$ moves from point $A$ to point $B$ , the approximation at $A$ deteriorates and a new approximation is needed. This new approximation will be the tangent at point $B$  

# 9.4.2 ADJUSTING THE HEDGE OVER TIME  

We now consider what happens to the delta-hedged position as $S_{t}$ oscillates. According to our discussion in the previous chapter, as time passes, the replicating portfolio needs to be rebalanced. This rebalancing will generate cash gains.  

We discuss these portfolio adjustments in a highly simplified environment. Considering a sequence of simple oscillations in $S_{t}$ around an initial point $S_{t_{0}}=S^{0}$ , let  

$$
t_{0}<t_{1}<\cdots<t_{n}
$$  

with  

$$
t_{i}-t_{i-1}=\Delta
$$  

![](27a763ef01e0a74a43bea19494edf05e5a824b739faef13954b4cdb28de2509a.jpg)  

# FIGURE 9.6  

Delta neutral portfolio example.  

denote successive time periods that are apart $\Delta$ units of time. We assume that $S_{t}$ oscillates at an annual percentage rate of one standard deviation, $\sigma$ , around the initial point $S_{t_{0}}=S^{0}$ . For example, one possible round turn may be  

$$
S^{0}\to(S^{0}+\Delta S)\to S^{0}
$$  

With $\Delta S=\sigma S^{0}\sqrt{\Delta}$ the percentage oscillations will be proportional to $\sqrt{\Delta}$ The mechanics of maintaining the delta-hedged long call position will be discussed in this simplified setting.  

![](a5501bccf3146691afa5e6a7f1d183c83e5a804370ad1c0e5ebf76f4614b6a9d.jpg)  

# FIGURE 9.7  

Oscillations in underlying and changes in hedge ratio.  

Since $S_{t_{i}}$ moves between three possible values only, we simplify the notation and denote the possible values of S, by S, so, and S+, wherel2  

$$
\begin{array}{l}{S^{+}=S^{0}+\Delta S}\ {~}\ {S^{-}=S^{0}-\Delta S}\end{array}
$$  

We now show how these oscillations generate cash gains. According to Figure 9.7, as $S_{t}$ fluctuates, the slope, $C_{s}$ of the $C(S_{t},t)$ also changes. Ignoring the effect of time, the slope will change,e say, between $C_{s}^{+},C_{s}^{0}$ , and $C_{s}^{-}$ , as shown in Figure 9.7.13 We note that  

$$
C_{s}^{-}<C_{s}^{0}<C_{s}^{+}
$$  

12 We can represent this trajectory by a thre-tate Markov chain that has the fllwing probabilities:  

$$
P(S^{0}\mid S^{+})=1\quad P(S^{-}\mid S^{0})=\frac{1}{2}\quad P(S^{+}\mid S^{0})=\frac{1}{2}\quad P(S^{0}\mid S^{-})=1
$$  

where $S^{0}$ is the sorting value. If prices are at $S^{+}$ or $S^{-}$ they always go back to $S_{\mathbf{0}}$ From $S_{\mathbf{0}}$ they can either go up or down.   
$^{13}\mathrm{{It}}$ is importan torelize that these slopes also depend on time $t$ although, to simplify the notation, we are omtting the time index here.  

for all $t_{i}$ .This means that as $S_{t}$ moves, $h_{t}$ , the hedge ratio will change in a particular way. In order. to keep the portfolio delta-hedged, the market maker needs to adjust the number of the underlying $S_{t}$ that was shorted.  

Second, and unexpectedly, the hedge adjustments have a "nice" effect. When $S_{t}$ moves from $S^{+}$ to $S^{0}$ or from $S^{0}$ to $S^{-}$ , the market maker has to decrease the size of the short position in $S_{t}$ . To do this, the market maker needs to "buy"' back a portion of the underlying asset that was originally shorted at a higher price $S^{0}$ or $S^{+}$  

Accordingly, the market maker sells short when prices are high and covers part of the position when prices decline. This leads to cash gains.  

Consider now what happens when the move is from $S^{0}$ to $S^{+}$ . The new slope, $C_{s}^{+}$ , is steeper than the old, $C_{s}^{0}$ . This means that the market maker needs to short more of the $S_{t}$ asset at the new price. When $S_{t}$ moves back to $\overline{{S}}^{0}$ , these shorts are covered at $\overline{{S}}^{0}$ , which is lower than $\overline{{S^{+}}}$  

Thus, as $S_{t}$ oscillates around $S^{0}$ , the portfolio is adjusted accordingly, and the market maker would automatically sell high and buy low. At every round turn, say, $\{\bar{S}^{0},\bar{S}^{+},\bar{S}^{0}\}$ , which takes two periods, the hedge adjustments will generate a cash gain equal to  

$$
(C_{s}^{+}-C_{s}^{0})[(S^{0}+\Delta S)-S^{0}]=(C_{s}^{+}-C_{s}^{0})\Delta S
$$  

Here, $(C_{s}^{+})^{-}C_{s}^{0})$ represents the number of. $S_{t}$ assets that were shorted after the price moved from $S^{0}$ to $S^{+}$ . Once the price goes back to. $\overline{{S}}^{0}$ , the same securities are purchased at a lower price. It is interesting to look at these trading gains as the time interval, $\Delta$ , becomes smaller and smaller..  

# 9.4.2.1 Limiting form  

As $\Delta S{\rightarrow}0$ , we can show an important approximation to the trading (hedging) gains  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S
$$  

The term $(C_{s}^{+}-C_{s}^{0})$ is the change in the first partial derivative of $C\left({{S}_{t}},t\right)$ , as $S_{t}$ moves from $S_{t_{0}}$ to a new level denoted by $S_{t_{0}}+\Delta S$ We can convert $(C_{s}^{+}-C_{s}^{0})$ into a rate of change after multiplying and dividing by $\Delta S$  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S=\frac{C_{s}^{+}-C_{s}^{0}}{\Delta S}(\Delta S)^{2}
$$  

As we let $\Delta S$ go to zero, we obtain the approximation  

$$
\frac{C_{s}^{+}-C_{s}^{0}}{\Delta S}\cong\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}
$$  

Thus, the round-turn gains from delta-hedge adjustments shown in Eq. (9.29) can be approximated as  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S\cong\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}(\Delta S)^{2}
$$  

Per time unit gains are then half of this,  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S)^{2}
$$  

These gains are only part of the potential cash inflows and outflows faced by the market maker. The position has further potential cash flows that need to be described. This is done in the next two sections.  

# 9.4.3 OTHER CASH FLOWS  

We just showed that oscillations in $S_{t}$ generate positive cash flows if the market maker delta hedges his or her long option position. Does this imply an arbitrage opportunity? After all, the market maker did not advance any cash yet seems to receive cash spontaneously as long as $S_{t}$ Oscillates. The answer is no. There are costs to this strategy, and the delta-hedged option position is not riskless.  

1. The market maker funded his or her position with borrowed money. This means, that, as time passes, an interest cost is incurred. For a period of length. $\Delta$ , this cost will equal  

$$
r C\Delta
$$  

under the constant spot rate assumption. (We write $C(t)$ , as $C.$  

2. The option has time value, and as time passes, everything else being the same, the value of the option will decline at the rate  

$$
C_{t}=\frac{\partial C(S_{t},t)}{\partial t}
$$  

The option value will go down by  

$$
\frac{\partial C(S_{t},t)}{\partial t}\Delta
$$  

dollars, for each $\Delta$ that passes.  

3. Finally, the cash received from the short position generates $r S_{t}C_{s}\Delta$ dollars interest every time period $\Delta$  

The trading gains and the costs can be put together to obtain an important partial differential equation (PDE), which plays a central role in financial engineering..  

# 9.4.4 OPTION GAINS AND LOSSES AS A PDE  

We now add all gains and costs per unit of time $\Delta$ . The options' gains per time unit from hedging adjustments are  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S)^{2}
$$  

In case the process $S_{t}$ is geometric, the annual percentage variance will be constant and this can be written as (see Appendix 9.2)  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta
$$  

The rest of the argument will continue with the assumption of a constant $\sigma$  

Interest is paid daily on the funds borrowed to purchase the call. For every period of length $\Delta$ a long call holder will pay  

Another item is the interest earned from cash generated by shorting $C_{s}$ units of $S_{t}$  

$$
r C_{s}S_{t}\Delta
$$  

Adding these, we obtain the net cash gains (losses) from the hedged long call position during $\Delta$  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta+r C_{s}S_{t}\Delta-r C\Delta
$$  

Now, in order for there to be no arbitrage opportunity, this must be equal to the daily loss of time value:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta+r C_{s}S_{t}\Delta-r C\Delta=-C_{t}\Delta
$$  

We can eliminate the common $\Delta$ terms and obtain a very important relationship that some readers will recognize as the Black-Scholes PDE:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

Every PDE comes with some boundary conditions and this is no exception. The call option will expire at time $T$ , and the expiration $C(S_{T},T)$ is given by  

$$
C(S_{T},T)=\operatorname*{max}[S_{T}-K,0]
$$  

Solving this PDE gives the Black-Scholes equation. In most finance texts, the PDE derived here is obtained from some mathematical derivation. In this section, we obtained the same PDE heuristically from practical trading and arbitrage arguments.  

# 9.4.5 CASH FLOWS AT EXPIRATION  

The cash flows at expiration date have three components: (i) the market maker has to pay the original loan if it is not paid off slowly over the life of the option, (ii) there is the final option settlement, and (iii) there is the final payoff from the short $S_{t}$ position.  

Now, at an infinitesimally short time period, $\mathrm{d}t$ . before expiration, the price of the underlying will be very close to $S_{T}.$ Call it $S_{T}^{-}$ . The price curve $C(S_{t},t)$ will be very near the piecewise linear option payoff. Thus, the hedge ratio $h_{T}^{-}=C_{s}$ will be very close to either 0 or 1:  

$$
h_{T}^{-}\cong\left\{\begin{array}{l l}{{1}}&{{S_{T}^{-}>K}}\ {{0}}&{{S_{T}^{-}<K}}\end{array}\right.
$$  

This means that, at time. $T.$ any potential gains from the long call option position will be equal to losses on the short $S_{t}$ position.  

The interesting question is, how does the market maker manage to pay back the original loan. under these conditions? There is only one way. The only cash that is available is the accumulation of (net) trading gains from hedge adjustments during $[t,T]$ . As long as Eq. (9.44) is satisfied for every $t_{i}.$ the hedged long option position will generate enough cash to pay back the loan. The. option price, $C(t)$ , regarded this way is the discounted sum of all gains and losses from a delta-. hedged option position the trader will incur based on expected $S_{t}$ volatility.  

We will now consider a numerical example to our highly simplified discussion of how realized volatility is converted into cash via an option position..  

# 9.4.6 AN EXAMPLE  

Consider a stock, $S_{t}.$ trading at a price of 100. The stock pays no dividends and is known to have a Black-Scholes volatility of. $\sigma=45\%$ per annum. The risk-free interest rate is. $4\%$ and $S_{t}$ is known to follow a geometric process, so that the Black--Scholes assumptions are satisfied.  

A market maker buys 100 plain vanilla, ATM calls that expire in 5 days. The premium for one call is 2.13 dollars. This is the price found by plugging the above data into the Black-Scholes formula. Hence, the total cash outlay is. $\$213$ . There are no other fees or commissions. The market. maker borrows the $\$213$ , buys the call options, and immediately hedges the long position by short. selling an appropriate number of the underlying stock.  

# EXAMPLE  

Suppose that during these 5 days the underlying stock follows the path:  

$$
\{\mathrm{Day~1}=100,\mathrm{Day~2}=105,\mathrm{Day~3}=100,\mathrm{Day~4}=105,\mathrm{Day~5}=100\}
$$  

What are the cash flows, gains, and losses generated by this call option that remain on the market maker's books?.  

# 1. Day 1: The purchase date  

Current Delta: 51 (Found by differentiating the Black-Scholes formula with respect to $S_{t},$ plugging in the data and then multiplying by 100)   
Cash paid for the call options:. $\$213$   
Amount borrowed to pay for the calls: $\$213$   
Amount generated by short selling 51 units of the stock: $\$5100$ . This amount is depos-. ited at a rate of $4\%$  

# 2. Day 2: Price goes to 105  

Current Delta: 89 (Evaluated at $S_{t}=105,3$ days to expiration)   
Interest on amount borrowed: 213(0.04) $\left(\frac{1}{360}\right)=\$02$   
Interest earned from deposit: 5100(0.04) $\left(\frac{1}{360}\right)=\$57$ (Assuming no bid-ask difference in interest rates)   
Short selling 38 units of additional stock to reach delta neutrality which generate: 38 $(105)=\$3990$ -.  

# 3. Day 3: Price goes back to 100  

Current Delta: 51   
Interest on amount borrowed: 213(0.04) $\begin{array}{r}{\left(\frac{1}{360}\right)=\$0.02}\end{array}$   
Interest earned from deposits:. $(5100+3990)(0.04)~\textstyle{\left({\frac{1}{360}}\right)}=\mathbb{\S}1$   
Short covering 38 units of additional stock at 100 each, to reach delta neutrality generates a cash flow of:. $38(5)=\$190$ Interest on these profits is ignored to the first order of approximation.  

# 4. Day 4: Price goes to 105  

Current Delta: 98   
Interest on amount borrowed: 213(0.04) $\left(\frac{1}{360}\right)=\$0.02$   
Interest earned from deposits: 5100(0.04) $\left({\frac{1}{360}}\right)=\$0.57$   
Shorting 47 units of additional stock at 105 each, to reach delta neutrality generates:   
$47(105)=\$4935$  

# 5. Day 5: Expiration with $S_{T}=100$  

Net cash generated from covering the short position: $47(5)=\$235$ (There were 98 shorts, covered at $\$100$ each; 47 shorts were sold at. $\$105$ , 51 shorts at $\$100$   
Interest on amount borrowed: 213(0.04) $\left(\frac{1}{360}\right)=\$0.02$   
Interest earned from deposits: $(5100+4935)$ (0.04) $\textstyle\left({\frac{1}{360}}\right)=\$1.1$ . The option expires ATM and generates no extra cash.  

# 6. Totals  

Total interest paid: $4(0.02)=\$0.08$   
Total interest earned: $2(0.57)+1+1.1=\$3.24$   
Total cash earned from hedging adjustments: $\$235$   
Cash needed to repay the loan: $\$213$   
Total net profit ignoring interest on interest. $=\$215.16$   
A more exact calculation would take into account interest on interest earned and the interest earned on $\$190$ for 2 days.  

We can explain why total profit is positive. The path followed by $S_{t}$ in this example implies a daily actual volatility of $5\%$ . Yet, the option was sold at an annual implied volatility of $45\%$ , which corresponds to a "daily"' percentage implied volatility of:  

$$
0.45\sqrt{\frac{1}{365}}=2.36\%
$$  

Hence, during the life of the option,. $S_{t}$ fluctuated more than what the implied volatility sug-. gested. As a result, the long convexity position had a net profit.  

This example is, of course, highly simplified. It keeps implied volatility constant and the oscillations occur around a fixed point. If these assumptions are relaxed, the calculations will change.  

# 9.4.6.1 Some caveats  

Three assumptions simplified notation and discussion in this section.  

First, we considered oscillations around a fixed $S^{0}$ . In real life, oscillations will clearly occur around points that themselves move. As this happens, the partial derivatives, $C_{s}$ and $C_{s s}$ will change in more complicated ways.   
Second, $C_{s}$ and $C_{s s}$ are also functions of time $t.$ , and as time passes, this will be another source of change.   
The third point is more important. During the discussion, oscillations were kept constant at $\Delta S$ In real life, volatility may change over time and be random as well. This would not invalidate the essence of our argument concerning gains from hedge adjustments, but it will clearly introduce another risk that the market maker may have to hedge against. This risk is known as vega risk.   
Finally, it should be remembered that the underlying asset did not make any payouts during the life of the option. If dividends or coupons are paid, the calculation of cash gains and losses needs to be adjusted accordingly.  

These assumptions were made to emphasize the role of options as volatility instruments. Forthcoming chapters will deal with how to relax them.  
