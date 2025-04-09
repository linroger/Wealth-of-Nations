# 14.2 A FRAMEWORK FOR SWAPS  

We work with forward fixed payer interest rate swaps and their "spot' equivalent. These are vanilla. products in the sense that contracts are predesigned and homogeneous. They are liquid, the bid--ask spreads are tight, and every market player is familiar with their properties and related conventions.  

To simplify the discussion we work with a three-period forward swap, shown in Figure 14.1. It is worth repeating the relevant parameters again, given the somewhat more technical approach. the chapter will adopt.  

1. The notional amount is $N_{-}$ and the tenor of the underlying LIBOR rate is $\delta$ , which represents a proportion of a calendar year. As usual, if a year is denoted by 1, then $\delta$ will be 1/4 in the case of 3-month LIBOR.   
2. The swap maturity is three periods. The swap ends at time $T=t_{4}$ . The swap contract is signed at time $t_{0}$ but starts at time $t_{1}$ , hence the term forward swap is used.'  

![](images/2fbd6b922c97f4e54d9295756991a02987c168af255c50676d76c4541ac6d34d.jpg)  

# FIGURE 14.2  

Payoff diagrams for three default-free pure discount bonds.  

3. The dates $\left\{t_{1},t_{2},t_{3}\right\}$ are reset dates where the relevant LIBOR rates $L_{t_{1}}$ $L_{t_{2}}$ , and $L_{t_{3}}$ will be determined.2 These dates are $\delta$ time units apart.   
4. The dates $\left\{t_{2},t_{3},t_{4}\right\}$ are settlement dates where the LIBOR rates $L_{t_{1}}$ $L_{t_{2}}$ , and $L_{t_{3}}$ are used to exchange the floating cash flows, $\delta N L_{t_{i}}$ against the fixed $\delta\mathbf{N}s_{t_{0}}$ at each $t_{i+1}$ . In this setup, the time that passes until the start of the swap, $t_{1}-t_{0}$ , need not equal $\delta$ . However, it may be notationally convenient to assume that it does.  

Our purpose is to provide a systematic framework in which the risk management and pricing of. such swaps and the instruments that build on them can be done efficiently. That is, we discuss a technical framework that can be used for running a swap and swap derivatives book..  

Swaps are one major component of a general framework for fixed-income engineering. We. need two additional tools. These we introduce using a simple example again. Consider Figure 14.2, where we show payoff diagrams for three default-free pure discount bonds. The current price,. $B(t_{0},$ $T_{i})$ , of these bonds is paid at $t_{0}$ to receive 1 dollar in the same currency at maturity dates. $T_{i}=t_{i}$ Given that these bonds are default-free, the time. $t_{\mathrm{i}}$ payoffs are certain and the price. $B\left(t_{0},T_{i}\right)$ can be considered as the value today of 1 dollar to be received at time $t_{i}$ This means they are, in fact, the relevant discount factors, or in market language, simply discounts for $t_{i}$ Note that as  

$$
T_{1}<T_{2}<T_{3}<T_{4}
$$  

![](images/641f3c5c075b1e768310a771b8a30ed0f1924eacdef4c496c2205c9081d0c17f.jpg)  

# FIGURE 14.3  

Cash flow diagrams of three FRAs paid in arrears.  

bond prices must satisfy, regardless of the slope of the yield curve:  

$$
B(t_{0},T_{1})>B(t_{0},T_{2})>B(t_{0},T_{3})>B(t_{0},T_{4})
$$  

These prices can be used as discount factors to calculate present values of various cash flows occurring at future settlement dates. $t_{i}$ They are, therefore, quite useful in successive swap settle-. ments and form the second component in our framework..  

The third component of the fixed-income framework is shown in Figure 14.3. Here, we have the cash flow diagrams of three forward rate agreements (FRAs) paid in arrears. The FRAs are, respectively, $t_{1}\times t_{2},t_{2}\times t_{3}$ and $t_{3}\times t_{4}$ . For each FRA, a floating (random) payment is made against a known (fixed) payment for a net cash flow of  

$$
\[L_{t_{i}}-F(t_{0},t_{i})\big]N\delta
$$  

at time $t_{i+1}$ . Here, the $\boldsymbol{F}(t_{0},t_{i})$ is the forward rate of a fictitious forward loan contract signed at. time $t_{0}$ . The forward loan comes into effect at. $t_{i}$ and will be paid back at time $t_{i+1}=t_{i}+\delta$ . We note that the fixed payments $N\delta~F(t_{0},~t_{i})$ are not the same across the FRAs. Although all FRA rates are  

known at time $t_{0}$ , they will, in general, not equal each other or equal the payment of the fixed swap leg, $\delta N s_{t_{0}}$  

We can now use this framework to develop some important results and then apply them in financial engineering.  

# 14.2.1 EQUIVALENCE OF CASH FLOWS  

The first financial engineering rule that we discuss in this chapter is associated with the perceived equivalence of cash flows. In Figure 14.3, there is a strip of floating cash flows:.  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

and, given observed liquid prices, the market is willing to exchange these random cash flows against the known (fixed) cash flows:.  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

According to this, if these FRAs are liquid at time $t_{0}$ the known cash flow sequence in Eq. (14.5) is perceived by the markets as the correct exchange against the unknown, floating payments in Eq. (14.4). If we then consider the swap cash flows shown in Figure 14.1, we note that exactly the same floating cash flow sequence as in Eq. (14.4) is exchanged for the known and fixed s wap leg  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

The settlement dates are the same as well. In both exchanges, neither party makes any upfront payments at time $t_{0}$ We can therefore combine the two exchanges at time. $t_{0}$ and obtain the following result.  

The market is willing to exchange the fixed and known cash flows  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

against the variable known cash flows:  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

at no additional time $t_{0}$ compensation.  

This has an important implication. It means that the time $t_{0}$ values of the two cash flow sequences are the same. Otherwise, one party would demand an initial cash payment. Given that the cash flows are known as of time $t_{0}$ their equivalence provides an equation that can be used in pricing, as we will see next. This argument will be discussed further using the Forward LIBOR Model.  

# 14.2.2 PRICING THE SWAP  

We have determined two known cash flow sequences the market is willing to exchange at no additional cost. Using this information, we now calculate the time. $t_{0}$ values of the two cash flows. To.  

do this, we use the second component of our framework, namely, the discount bond prices given in Figure 14.2.  

Suppose the pure discount bonds with arbitrage-free prices $B(t_{0},t_{i}),i=1,2,3,4$ are liquid and actively traded. We can then use $\{B(t_{0},t_{2}),B(t_{0},t_{3}),B(t_{0},t_{4})\}$ to value cash flows settled at times $t_{2},t_{3}$ , and $t_{4}$ , respectively.4 In fact, the time $t_{0}$ value of the sequence of cash flows,  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

is given by multiplying each cash flow by the discount factor that corresponds to that particular settlement date and then adding. We use the default-free bond prices as our discount factors and obtain the value of the fixed FRA cash flows  

$$
\begin{array}{r}{B(t_{0},t_{2})F(t_{0},t_{1})N\delta+B(t_{0},t_{3})F(t_{0},t_{2})N\delta+B(t_{0},t_{4})F(t_{0},t_{3})N\delta}\ {=[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]N\delta}\end{array}
$$  

The time $t_{0}$ value of the fixed swap cash flows can be calculated similarly  

$$
B(t_{0},t_{2})s_{t_{0}}N\delta+B(t_{0},t_{3})s_{t_{0}}N\delta+B(t_{0},t_{4})s_{t_{0}}\delta N=[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]\delta N s_{t_{0}}
$$  

Now, according to the argument in the previous section, the values of the two cash flows must be the same.  

$$
\begin{array}{r l}&{[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]\delta N}\ &{\quad=[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]\delta N s_{t_{0}}}\end{array}
$$  

This equality has at least two important implications. First, it implies that the value of the swap at time $t_{0}$ is zero. Second, note that equality can be used as an equation to determine the value of one unknown. As a matter of fact, pricing the swap means determining a value for. $s_{t_{0}}$ such that the equation is satisfied. Taking. $s_{t_{0}}$ as the unknown, we can rearrange Eq. (14.12), simplify, and obtain.  

$$
s_{t_{0}}=\frac{B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})}{B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})}
$$  

This pricing formula can easily be generalized by moving from the three-period setting to a vanilla (forward) swap that makes $n$ payments starting at time $t_{2}$ .We obtain  

$$
s_{t_{0}}={\frac{\sum_{i=1}^{n}B(t_{0},t_{i+1})F(t_{0},t_{i})}{\sum_{i=1}^{n}B(t_{0},t_{i+1})}}
$$  

This is a compact formula that ties together the three important components of the fixed-income framework we are using in this chapter.  

# 14.2.2.1 Interpretation of the swap rate  

The formula that gives the arbitrage-free value of the (forward) swap has a nice interpretation. For simplicity, revert to the three-period case. Rewrite Eq. (14.13) as.  

$$
\begin{array}{l}{{s_{t_{0}}=\displaystyle\frac{B(t_{0},t_{2})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{1})}}\ {{\displaystyle~+\frac{B(t_{0},t_{3})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{2})}}\ {{\displaystyle~+\frac{B(t_{0},t_{4})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{3})}}\end{array}
$$  

According to this expression, we see that the "correct' (forward) swap rate is a weighted average of the FRA paid-in-arrears rates during the life of the swap:.  

$$
s_{t_{0}}=\omega_{1}F(t_{0},t_{1})+\omega_{2}F(t_{0},t_{2})+\omega_{3}F(t_{0},t_{3})
$$  

The weights are given by  

$$
\omega_{i}=\frac{B(t_{0},t_{i+1})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}
$$  

and add up to one:  

$$
\omega_{1}+\omega_{2}+\omega_{2}=1
$$  

This can again be generalized for a (forward) swap that makes $n$ payments:  

$$
s_{t_{0}}=\sum_{i=1}^{n}\omega_{i}F(t_{0},t_{i})
$$  

with  

$$
\sum_{i=1}^{n}\omega_{i}=1
$$  

Thus, the (forward) swap rate is an average paid-in-arrears FRA rate. We emphasize that this is true as long as the FRAs under consideration are paid in arrears. There are, on the other hand, so-called LIBOR-in-arrears FRAs where a convexity adjustment needs to be made for the argument to hold.5  

It is important to realize that the weights $\left\{\omega_{i}\right\}$ are obtained from pure discount bond prices. which, as shown in Chapters 3 and 13, are themselves functions of forward rates:  

$$
B(t_{0},t_{i})=\frac{1}{\prod_{j=0}^{i-1}(1+\delta F(t_{0},t_{j}))}
$$  

According to these formulas, three important components of our pricing framework-the swap market, the FRA market, and the bond market--are interlinked through nonlinear functions of forward rates. The important role played by the forward rates in these formulas suggests that obtaining arbitrage-free dynamics of the latter is required for the pricing of all swap and swap-related derivatives. The Forward LIBOR Model does exactly this. Because this model is set up in a way as to fit market conventions, it is also practical.  

However, before we discuss these more advanced concepts, it is best to look at an example. In practice, swap and FRA markets are liquid and market makers readily quote the relevant rates. The real-world equivalents of the pure discount bonds $\{B(t_{0},t_{i})\}$ , on the other hand, are not that liquid, even when they exist. In the following example, we sidestep this point and assume that such quotes are available at all desired maturities. Even then, some important technical issues emerge, as the example illustrates.  

# EXAMPLE  

Suppose we observe the following paid-in-arrears FRA quotes:  

<html><body><table><tr><td>Term Bid-Ask</td><td></td></tr><tr><td>9×0 4.05-4.07</td><td></td></tr><tr><td>6 × 12 4.15-4.17</td><td></td></tr><tr><td>12 × 18</td><td>4.32-4.34</td></tr><tr><td>18 × 24 4.50-4.54</td><td></td></tr></table></body></html>  

Also, suppose the following treasury strip prices are observed:  

<html><body><table><tr><td>Maturity</td><td>Bid-Ask</td></tr><tr><td>12 months</td><td>96.00-96.02</td></tr><tr><td>18 months</td><td>93.96-93.99</td></tr><tr><td>24 months</td><td>91.88-91.92</td></tr></table></body></html>  

We can ask two questions. First, are these data arbitrage-free so that they can be used in obtaining an arbitrage-free swap rate? Second, if they are, what is the implied forward swap rate for the period that starts in 6 months and ends in 24 months?  

The answer to the first question can be checked by using the following arbitrage equality, written for discount bonds with par value. $\$100$ , as market convention suggests:  

$$
B(t_{0},t_{i})=\frac{100}{\prod_{j-0}^{i-1}(1+\delta F(t_{0},t_{j}))}
$$  

where the value of $\delta$ will be $1/2$ in this example. Substituting the relevant forward rates from the preceding table, we indeed find that the given discount bond prices satisfy this equality. For example, for $B(0,2)^{\mathrm{ask}}$ we have  

$$
B(0,2)^{\mathrm{ask}}={\frac{100}{(1+0.5(0.0405))(1+0.5(0.0415))}}=96.02
$$  

The relevant equalities hold for other discount bond prices as well. This means that the data are arbitrage free and can be used in finding an arbitrage-free swap rate for the above-. mentioned forward start swap.  

Replacing straightforwardly in  

$$
s_{t_{0}}^{\mathrm{ask}}=\omega_{1}^{\mathrm{ask}}F(t_{0},t_{1})^{\mathrm{ask}}+\omega_{2}^{\mathrm{ask}}F(t_{0},t_{2})^{\mathrm{ask}}+\omega_{3}^{\mathrm{ask}}F(t_{0},t_{3})^{\mathrm{ask}}
$$  

$$
\omega_{i}^{\mathrm{ask}}=\frac{B(t_{0},t_{i}+1)^{\mathrm{ask}}}{\left[B(t_{0},t_{2})^{\mathrm{ask}}+B(t_{0},t_{3})^{\mathrm{ask}}+B(t_{0},t_{4})^{\mathrm{ask}}\right]}
$$  

we find  

$$
{\begin{array}{r l}&{\omega_{1}^{\mathrm{ask}}={\frac{96.02}{[96.02+93.99+91.92]}}=0.341}\ &{\omega_{2}^{\mathrm{ask}}={\frac{93.99}{[96.02+93.99+91.92]}}=0.333}\ &{\omega_{3}^{\mathrm{ask}}={\frac{91.92}{[96.02+93.99+91.92]}}=0.326}\end{array}}
$$  

The asking swap rate is  

$$
s_{t_{0}}^{\mathrm{ask}}=(0.341)4.17+(0.333)4.34+(0.326)4.54=4.34
$$  

Similarly, we can calculate the bid rate:  

$$
s_{t_{0}}^{\mathrm{bid}}=(0.341)4.15+(0.333)4.32+(0.326)4.50=4.32
$$  

It is worth noting that the weights have approximately the same size.  

We now consider further financial engineering applications of the fixed-income framework outlined in this section.  

# 14.2.3 SOME APPLICATIONS  

The first step is to consider the synthetic creation of swaps within our new framework. Our purpose. is to obtain an alternative synthetic for swaps by manipulating the formulas derived in the previous section. In Chapter 4, we discussed one way of replicating swaps. We showed that a potential synthetic is the simultaneous shorting of a particular coupon bond and buying of a proper floating rate bond. This embodies the classical approach to synthetic swap creation, and it will be the starting point of the following discussion.  

# 14.2.3.1 Another formula  

We have already derived a formula for the (forward) swap rate, $s_{t_{0}}$ , that gives an arbitrage-free. swap value:  

Or, in the general form,  

$$
s_{t_{0}}=\frac{[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}
$$  

$$
s_{t_{0}}={\frac{\sum_{i=1}^{n}B(t_{0},t_{i+1})F(t_{0},t_{i})}{\sum_{i=1}^{n}B(t_{0},t_{i+1})}}
$$  

Now, we would like to obtain an alternative way of looking at the same swap rate by modifying the formula. We start the discussion with the arbitrage relation between the discount bond prices, $B(t_{0},t_{i})$ , and the forward rates, $F(t_{0},t_{i})$ , obtained earlier in Chapter 3:  

$$
1+\delta F(t_{0},t_{i})=\frac{B(t_{0},t_{i})}{B(t_{0},t_{i+1})}
$$  

Rearranging  

$$
F(t_{0},t_{i})=\frac{1}{\delta}\left[\frac{B(t_{0},t_{i})}{B(t_{0},t_{i+1})}-1\right]
$$  

We now substitute this expression in Eq. (14.32) to obtain  

$$
\begin{array}{c}{{s_{t_{0}}={\displaystyle\frac{1}{\delta[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}}\left\{B(t_{0},t_{2})\displaystyle\left[\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}-1\right]\right.}}\ {{\displaystyle\left.+B(t_{0},t_{3})\left[\frac{B(t_{0},t_{2})}{B(t_{0},t_{3})}-1\right]+B(t_{0},t_{4})\displaystyle\left[\frac{B(t_{0},t_{3})}{B(t_{0},t_{4})}-1\right]\right\}}}\end{array}
$$  

Simplifying the common $B(t_{0},t_{i})$ terms on the right-hand side, we get  

$$
\begin{array}{l}{{s_{t_{0}}=\displaystyle\frac{1}{\delta\sum_{i=1}^{3}B(t_{0},t_{i+1})}([B(t_{0},t_{1})-B(t_{0},t_{2})]}}\ {{\mathrm{~~}+[B(t_{0},t_{2})-B(t_{0},t_{3})]+[B(t_{0},t_{3})-B(t_{0},t_{4})]}}\ {{\mathrm{~~}=\displaystyle\frac{1}{\delta\sum_{i=1}^{3}B(t_{0},t_{i+1})}[B(t_{0},t_{1})-B(t_{0},t_{4})]}}\end{array}
$$  

We can try to recognize what this formula means by first rearranging,  

$$
\delta s_{t_{0}}[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]=[B(t_{0},t_{1})-B(t_{0},t_{4})]
$$  

and then regrouping:  

$$
B(t_{0},t_{1})-\left[s_{t_{0}}\delta B(t_{0},t_{2})+s_{t_{0}}\delta B(t_{0},t_{3})+B(t_{0},t_{4})\big(1+\delta s_{t_{0}}\big)\right]=0
$$  

The equation equates two cash flows.. $B(t_{0},t_{1})$ is the value of 1 dollar to be received at time $t_{1}$ Thus, the position needs to be long a. $t_{1}$ -maturity discount bond. Second, there appear to be coupon payments of constant size,. $\delta s_{t_{0}}$ at times $t_{2}$ $t_{3}$ $t_{4}$ and then a payment of 1 dollar at time $t_{4}$ ' Thus, this seems to be a short (forward) position in a. $t_{4}$ -maturity coupon bond with coupon rate. $s_{t_{0}}$  

To summarize, this particular forward fixed receiver interest rate swap is equivalent to  

Fixed-payer forward swa $\mathrm{{1p}}=\left\{\mathrm{{Buy}}t_{1}\right.$ discount bond, forward sell $t_{4}$ -maturity coupon bond}  

This synthetic will replicate the value of the forward swap. Note that the floating cash flows do not have to be replicated. This is because, in a forward swap, the floating cash flows are related to deposits (loans) that will be made in the future, at interest rates to be determined then..  

# 14.2.3.2 Marking to market  

We can use the same framework for discussing mark-to-market practices. Start at time $t_{0}$ . As discussed earlier, the market is willing to pay the known cash flows.  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

against the random cash flows  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

Now, let a short but noninfinitesimal time, $\Delta$ , pass. There will be a new swap rate $s_{t_{0}}+\Delta$ which, in all probability, will be different than $s_{t_{0}}.$ This means that the market is now willing to pay the new known cash flows  

$$
\left\{s_{t_{0}+\Delta}N\delta,s_{t_{0}+\Delta}N\delta,s_{t_{0}+\Delta}N\delta\right\}
$$  

against the same random cash flows:  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

This implies that the value of the original swap, written at time $t_{0}$ , is nonzero and is given by the. difference:  

$$
\big[s_{t_{0}+\bigtriangleup}N\delta-s_{t_{0}}N\delta\big][B(t_{0}+\Delta,t_{2})+B(t_{0}+\Delta,t_{3})+B(t_{0}+\Delta,t_{4})]
$$  

This can be regarded as the profit and loss for the fixed payer. At time. $t_{0}+\Delta$ , the floating payment to be received has a value given by Eq. (14.47), and the actual floating payments would cancel out.8 We can apply the same reasoning using the FRA rates and calculate the mark-to-market value of the original swap from the difference:  

$$
\left(N\delta\left[\sum_{i=1}^{n}\omega_{i t_{0}}F(t_{0},t_{i})\right]-N\delta\left[\sum_{i=1}^{n}\omega_{i(t_{0}+\Delta)}F(t_{0}+\Delta,t_{i})\right]\right)\sum_{i=1}^{n}B(t_{0}+\Delta,t_{i+1})
$$  

This way of writing the expression shows the profit and loss from the point of view of a fixed. receiver. It should be noted that here the weights. $\omega_{i}$ have time subscripts, since they will change as. time passes. Thus, managing a swap book will depend nonlinearly on the forward rate dynamics.'  
