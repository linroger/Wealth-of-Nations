# FIXED INCOME ENGINEERING 14  

# CHAPTER OUTLINE  

4.1 Introduction . 460   
4.2 A Framework for Swaps ... . 461   
14.2.1 Equivalence of Cash Flows . 464   
14.2.2 Pricing the Swap . 464   
14.2.2.1 Interpretation of the swap rate . 466   
14.2.3 Some Applications.. 468   
14.2.3.1 Another formula .. 469   
14.2.3.2 Marking to market .... 470   
14.3 Term Structure Modeling .. . 471   
14.3.1 Determining the Forward Rates from Swaps .. 471   
14.3.2 Determining the $B(t_{0},\ t_{i})$ from Forward Rates 472   
14.3.3 Determining the Swap Rate . 472   
14.3.4 Real-World Complications . 472   
14.3.4.1 Remark... 473   
4.4 Term Structure Dynamics.. 473   
14.4.1 The Framework. 474   
14.4.2 Normalization and Forward Measure... 475   
14.4.2.1 Risk-neutral measure is inconvenient.. 475   
14.4.2.2 The forward measure. 477   
14.4.2.3 Arbitrage-free SDEs for forward rates . 478   
14.4.3 Arbitrage-Free Dynamics ... 479   
14.4.3.1 Review .. 481   
14.4.4 A Monte Carlo Implementation . 482   
4.5 Measure Change Technology .. 483   
14.5.1 The Mechanics of Measure Changes. 485   
14.5.2 Generalization.... 487   
4.6 An Application . 488   
14.6.1 Another Example of Measure Change 489   
14.6.2 Pricing CMS.. 493   
4.7 In-Arrears Swaps and Convexity ..... 494   
14.7.1 Valuation .. 495   
14.7.2 Special Case .. 497   
4.8 Cross-Currency Swaps.. . 498   
14.8.1 Pricing . 499   
14.8.2 Conventions . 500  

14.9 Differential (Quanto) Swaps 500   
14.9.1 Basis Swaps.. 501   
14.10 Conclusions... 501   
Suggested Reading .. . 502   
Exercises ... .. 502   
EXCEL Exercises . 503   
MATLAB Exercise . 505  

# 14.1 INTRODUCTION  

This chapter extends the discussion of swap-type instruments and outlines a simple framework for fixed-income security pricing. Term structure modeling is treated within this framework. The chapter also introduces the recent models that are becoming a benchmark in this sector.  

Until the late 1990s, short-rate modeling was the most common approach in pricing and riskmanaging fixed-income securities. The publication in 1992 of the Heath Jarrow Merton (HJM) approach enabled arbitrage-free modeling of multifactor-driven term structure models, but markets continued to use short-rate modeling. A few years ago the situation changed. The Forward LIBOR or Brace Gatarek Musiela (BGM) Model published in 1997 became the market standard for pricing and risk management.  

During the GFC, the LIBOR rate rose significantly and diverged from the overnight indexed swap (OIS) rate raising questions about whether LIBOR is an appropriate riskless discount. In Chapter 24, we will discuss recent models and market developments such as the use of OIS curve as a risk-free curve for discounting. The use of the OIS curve implies that more than one zero curve must be modeled for the purpose of pricing derivatives. The LIBOR curve is used to determine payoffs and the OIS zero curve is used for discounting. This chapter will discuss the Forward LIBOR Model and we will deal with more complex and recent issues such as approaches that simultaneously or separately model the LIBOR and the OIS curve in Chapter 24.  

This chapter will approach the issues from a practical point of view using swap markets and swap derivatives as a background. We are interested in providing a framework for analyzing the mechanics of swaps and swap derivatives, for decomposing them into simpler instruments, and for constructing synthetics. Recent models of fixed-income modeling can then be built on this foundation very naturally.  

It is worth reviewing the basic principles of swap engineering laid out in Chapter 4. First of all, swaps are almost always designed such that their value at initiation is zero. This is a characteristic of modern swap-type “spread instruments,” and there is no surprise here. Second, what makes the value of the swap equal to zero is a spread or an interest rate that is chosen with the purpose that the initial value of the swap vanishes. Third, swaps encompass more than one settlement date. This means that whatever the value of the swap rate or swap spread, these will in the end be some sort of “average of shorter term floating rates or spreads.” This not only imposes simple arbitrage conditions on relevant market rates but also provides an opportunity to trade the volatility associated with such averages through the use of options on swaps. Since swaps are very liquid, they form an excellent underlying for swaptions. Swaptions, in turn, are related to interest rate volatilities for the underlying subperiods, which will relate to cap/floor volatilities. This structure is conducive to  

![](f5787f5bbf4d20515b24c53782c2e3794a89d88baafb9f68cdfefcc99a607f79.jpg)  

# FIGURE 14.1  

Three-period forward swap.  

designing and understanding more complex swap products such as constant maturity swaps (CMS).   
The CMS is used as an example for showing the advantages of the Forward LIBOR Model.  

Finally, the chapter will further use the developed framework to illustrate the advantages of measure change technology. Switching between various $T_{\mathbf{\delta}}$ -forward measures, we show how convexity effects can be calculated.  

Most of the discussion will center on a three-period swap first, and then generalize the results. We begin with this simple example, because with a small number of cash flows the analysis becomes more manageable and easier to understand. Next, we lay out a somewhat more technical framework for engineering fixed-income instruments. Eventually, this is developed into the Forward LIBOR Model. Within our framework, measure changes using Girsanov-type transformations emerge as fundamental tools of financial engineering. The chapter discusses how measures can be changed sequentially during a numerical pricing exercise as was done in the simulation of the Forward LIBOR Model. These tools are then applied to CMS, which are difficult to price with traditional models.  

# 14.2 A FRAMEWORK FOR SWAPS  

We work with forward fixed payer interest rate swaps and their “spot” equivalent. These are vanilla products in the sense that contracts are predesigned and homogeneous. They are liquid, the bid ask spreads are tight, and every market player is familiar with their properties and related conventions.  

To simplify the discussion we work with a three-period forward swap, shown in Figure 14.1. It is worth repeating the relevant parameters again, given the somewhat more technical approach the chapter will adopt.  

1. The notional amount is $N$ , and the tenor of the underlying LIBOR rate is $\delta$ , which represents a proportion of a calendar year. As usual, if a year is denoted by 1, then $\delta$ will be 1/4 in the case of 3-month LIBOR.   
2. The swap maturity is three periods. The swap ends at time $T=t_{4}$ . The swap contract is signed at time $t_{0}$ but starts at time $t_{1}$ , hence the term forward swap is used.1  

![](68d1ffe91229593650aa0b9f193d8e73f9ca01f0df8427f52802c386c42ee7bc.jpg)  

# FIGURE 14.2  

Payoff diagrams for three default-free pure discount bonds.  

3. The dates $\{t_{1},t_{2},t_{3}\}$ are reset dates where the relevant LIBOR rates $L_{t_{1}}$ ; $L_{t_{2}}$ , and $L_{t_{3}}$ will be determined.2 These dates are $\delta$ time units apart.   
4. The dates $\{t_{2},t_{3},t_{4}\}$ are settlement dates where the LIBOR rates $L_{t_{1}}$ ; $L_{t_{2}}$ , and $L_{t_{3}}$ are used to exchange the floating cash flows, $\delta N L_{t_{i}}$ against the fixed $\delta\mathsf{N}\boldsymbol{s}_{t_{0}}$ at each $t_{i+1}$ . In this setup, the time that passes until the start of the swap, $t_{1}-t_{0}$ , need not equal $\delta$ . However, it may be notationally convenient to assume that it does.  

Our purpose is to provide a systematic framework in which the risk management and pricing of such swaps and the instruments that build on them can be done efficiently. That is, we discuss a technical framework that can be used for running a swap and swap derivatives book.  

Swaps are one major component of a general framework for fixed-income engineering. We need two additional tools. These we introduce using a simple example again. Consider Figure 14.2, where we show payoff diagrams for three default-free pure discount bonds. The current price, $B(t_{0},$ $T_{i})$ , of these bonds is paid at $t_{0}$ to receive 1 dollar in the same currency at maturity dates $T_{i}=t_{i}$ . Given that these bonds are default-free, the time $t_{\mathrm{i}}$ payoffs are certain and the price $\textit{B}(t_{0},\textit{T}_{i})$ can be considered as the value today of 1 dollar to be received at time $t_{i}$ . This means they are, in fact, the relevant discount factors, or in market language, simply discounts for $t_{i}$ . Note that as  

$$
\begin{array}{r}{T_{1}<T_{2}<T_{3}<T_{4}}\end{array}
$$  

![](631c34fe232dc2cd6cb35bd14b79d6bcfdbb127a84e733bcdd9000834a786049.jpg)  

# FIGURE 14.3  

Cash flow diagrams of three FRAs paid in arrears.  

bond prices must satisfy, regardless of the slope of the yield curve:3  

$$
B(t_{0},T_{1})>B(t_{0},T_{2})>B(t_{0},T_{3})>B(t_{0},T_{4})
$$  

These prices can be used as discount factors to calculate present values of various cash flows occurring at future settlement dates $t_{i}$ . They are, therefore, quite useful in successive swap settlements and form the second component in our framework.  

The third component of the fixed-income framework is shown in Figure 14.3. Here, we have the cash flow diagrams of three forward rate agreements (FRAs) paid in arrears. The FRAs are, respectively, $t_{1}\times t_{2},t_{2}\times t_{3}$ , and $t_{3}\times t_{4}$ . For each FRA, a floating (random) payment is made against a known (fixed) payment for a net cash flow of  

$$
\big[L_{t_{i}}-F(t_{0},t_{i})\big]N\delta
$$  

at time $t_{i+1}$ . Here, the $F(t_{0},\ t_{i})$ is the forward rate of a fictitious forward loan contract signed at time $t_{0}$ . The forward loan comes into effect at $t_{i}$ and will be paid back at time $t_{i+1}=t_{i}+\delta$ . We note that the fixed payments $N\delta\ F(t_{0},\ t_{i})$ are not the same across the FRAs. Although all FRA rates are  

known at time $t_{0}$ , they will, in general, not equal each other or equal the payment of the fixed swap leg, $\delta N s_{t_{0}}$ .  

We can now use this framework to develop some important results and then apply them in financial engineering.  

# 14.2.1 EQUIVALENCE OF CASH FLOWS  

The first financial engineering rule that we discuss in this chapter is associated with the perceived equivalence of cash flows. In Figure 14.3, there is a strip of floating cash flows:  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

and, given observed liquid prices, the market is willing to exchange these random cash flows against the known (fixed) cash flows:  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

According to this, if these FRAs are liquid at time $t_{0}$ , the known cash flow sequence in Eq. (14.5) is perceived by the markets as the correct exchange against the unknown, floating payments in Eq. (14.4). If we then consider the swap cash flows shown in Figure 14.1, we note that exactly the same floating cash flow sequence as in Eq. (14.4) is exchanged for the known and fixed swap leg  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

The settlement dates are the same as well. In both exchanges, neither party makes any upfront payments at time $t_{0}$ . We can therefore combine the two exchanges at time $t_{0}$ and obtain the following result.  

The market is willing to exchange the fixed and known cash flows  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

against the variable known cash flows:  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

at no additional time $t_{0}$ compensation.  

This has an important implication. It means that the time $t_{0}$ values of the two cash flow sequences are the same. Otherwise, one party would demand an initial cash payment. Given that the cash flows are known as of time $t_{0}$ , their equivalence provides an equation that can be used in pricing, as we will see next. This argument will be discussed further using the Forward LIBOR Model.  

# 14.2.2 PRICING THE SWAP  

We have determined two known cash flow sequences the market is willing to exchange at no additional cost. Using this information, we now calculate the time $t_{0}$ values of the two cash flows. To  

do this, we use the second component of our framework, namely, the discount bond prices given in Figure 14.2.  

Suppose the pure discount bonds with arbitrage-free prices $B(t_{0},t_{i}),i=1,2,3,4$ are liquid and actively traded. We can then use $\{B(t_{0},\ t_{2}),B(t_{0},\ t_{3}),B(t_{0},\ t_{4})\}$ to value cash flows settled at times $t_{2},t_{3}$ , and $t_{4}$ , respectively.4 In fact, the time $t_{0}$ value of the sequence of cash flows,  

$$
\{F(t_{0},t_{1})N\delta,F(t_{0},t_{2})N\delta,F(t_{0},t_{3})N\delta\}
$$  

is given by multiplying each cash flow by the discount factor that corresponds to that particular settlement date and then adding. We use the default-free bond prices as our discount factors and obtain the value of the fixed FRA cash flows  

$$
\begin{array}{r l r}&{}&{B(t_{0},t_{2})F(t_{0},t_{1})N\delta+B(t_{0},t_{3})F(t_{0},t_{2})N\delta+B(t_{0},t_{4})F(t_{0},t_{3})N\delta}\\ &{}&{=[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]N\delta}\end{array}
$$  

The time $t_{0}$ value of the fixed swap cash flows can be calculated similarly  

$$
B(t_{0},t_{2})s_{t_{0}}N\delta+B(t_{0},t_{3})s_{t_{0}}N\delta+B(t_{0},t_{4})s_{t_{0}}\delta N=[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]\delta N s_{t_{0}}
$$  

Now, according to the argument in the previous section, the values of the two cash flows must be the same.  

$$
\begin{array}{r l}&{[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]\delta N}\\ &{\quad=[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]\delta N s_{t_{0}}}\end{array}
$$  

This equality has at least two important implications. First, it implies that the value of the swap at time $t_{0}$ is zero. Second, note that equality can be used as an equation to determine the value of one unknown. As a matter of fact, pricing the swap means determining a value for $s_{t_{0}}$ such that the equation is satisfied. Taking $s_{t_{0}}$ as the unknown, we can rearrange Eq. (14.12), simplify, and obtain  

$$
s_{t_{0}}=\frac{B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})}{B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})}
$$  

This pricing formula can easily be generalized by moving from the three-period setting to a vanilla (forward) swap that makes $n$ payments starting at time $t_{2}$ . We obtain  

$$
s_{t_{0}}={\frac{\sum_{i=1}^{n}B(t_{0},t_{i+1})F(t_{0},t_{i})}{\sum_{i=1}^{n}B(t_{0},t_{i+1})}}
$$  

This is a compact formula that ties together the three important components of the fixed-income framework we are using in this chapter.  

# 14.2.2.1 Interpretation of the swap rate  

The formula that gives the arbitrage-free value of the (forward) swap has a nice interpretation. For simplicity, revert to the three-period case. Rewrite Eq. (14.13) as  

$$
\begin{array}{l}{{s_{t_{0}}=\displaystyle\frac{B(t_{0},t_{2})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{1})}}\\ {{\displaystyle~+\frac{B(t_{0},t_{3})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{2})}}\\ {{\displaystyle~+\frac{B(t_{0},t_{4})}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}F(t_{0},t_{3})}}\end{array}
$$  

According to this expression, we see that the “correct” (forward) swap rate is a weighted average of the FRA paid-in-arrears rates during the life of the swap:  

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

It is important to realize that the weights $\{\omega_{i}\}$ are obtained from pure discount bond prices, which, as shown in Chapters 3 and 13, are themselves functions of forward rates:  

$$
B(t_{0},t_{i})=\frac{1}{\prod_{j=0}^{i-1}(1+\delta F(t_{0},t_{j}))}
$$  

According to these formulas, three important components of our pricing framework—the swap market, the FRA market, and the bond market—are interlinked through nonlinear functions of forward rates. The important role played by the forward rates in these formulas suggests that obtaining arbitrage-free dynamics of the latter is required for the pricing of all swap and swap-related derivatives. The Forward LIBOR Model does exactly this. Because this model is set up in a way as to fit market conventions, it is also practical.  

However, before we discuss these more advanced concepts, it is best to look at an example. In practice, swap and FRA markets are liquid and market makers readily quote the relevant rates. The real-world equivalents of the pure discount bonds $\{B(t_{0},t_{i})\}$ , on the other hand, are not that liquid, even when they exist.6 In the following example, we sidestep this point and assume that such quotes are available at all desired maturities. Even then, some important technical issues emerge, as the example illustrates.  

# EXAMPLE  

Suppose we observe the following paid-in-arrears FRA quotes:  

<html><body><table><tr><td>Term</td><td>Bid-Ask</td></tr><tr><td>0X6 4.05-4.07</td><td></td></tr><tr><td>6X12</td><td>4.15-4.17</td></tr><tr><td>12X18</td><td>4.32-4.34</td></tr><tr><td>18 ×24 4.50-4.54</td><td></td></tr></table></body></html>  

Also, suppose the following treasury strip prices are observed:  

<html><body><table><tr><td>Maturity</td><td>Bid-Ask</td></tr><tr><td>12 months</td><td>96.00-96.02</td></tr><tr><td>18 months</td><td>93.96-93.99</td></tr><tr><td>24 months</td><td>91.88-91.92</td></tr></table></body></html>  

We can ask two questions. First, are these data arbitrage-free so that they can be used in obtaining an arbitrage-free swap rate? Second, if they are, what is the implied forward swap rate for the period that starts in 6 months and ends in 24 months?  

The answer to the first question can be checked by using the following arbitrage equality, written for discount bonds with par value $\$100$ , as market convention suggests:  

$$
B(t_{0},t_{i})=\frac{100}{\prod_{j-0}^{i-1}(1+\delta F(t_{0},t_{j}))}
$$  

where the value of $\delta$ will be $1/2$ in this example. Substituting the relevant forward rates from the preceding table, we indeed find that the given discount bond prices satisfy this equality. For example, for $B(0,2)^{\mathrm{ask}}$ we have  

$$
B(0,2)^{\mathrm{ask}}={\frac{100}{(1+0.5(0.0405))(1+0.5(0.0415))}}=96.02\
$$  

The relevant equalities hold for other discount bond prices as well. This means that the data are arbitrage free and can be used in finding an arbitrage-free swap rate for the abovementioned forward start swap.  

Replacing straightforwardly in  

$$
\begin{array}{r}{s_{t_{0}}^{\mathrm{ask}}=\omega_{1}^{\mathrm{ask}}F(t_{0},t_{1})^{\mathrm{ask}}+\omega_{2}^{\mathrm{ask}}F(t_{0},t_{2})^{\mathrm{ask}}+\omega_{3}^{\mathrm{ask}}F(t_{0},t_{3})^{\mathrm{ask}}}\end{array}
$$  

$$
\omega_{i}^{\mathrm{ask}}=\frac{B(t_{0},t_{i}+1)^{\mathrm{ask}}}{[B(t_{0},t_{2})^{\mathrm{ask}}+B(t_{0},t_{3})^{\mathrm{ask}}+B(t_{0},t_{4})^{\mathrm{ask}}]}
$$  

we find  

$$
\begin{array}{l}{\omega_{1}^{\mathrm{ask}}=\frac{96.02}{[96.02+93.99+91.92]}=0.341}\\ {\omega_{2}^{\mathrm{ask}}=\frac{93.99}{[96.02+93.99+91.92]}=0.333}\\ {\omega_{3}^{\mathrm{ask}}=\frac{91.92}{[96.02+93.99+91.92]}=0.326}\end{array}
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

The first step is to consider the synthetic creation of swaps within our new framework. Our purpose is to obtain an alternative synthetic for swaps by manipulating the formulas derived in the previous section. In Chapter 4, we discussed one way of replicating swaps. We showed that a potential synthetic is the simultaneous shorting of a particular coupon bond and buying of a proper floating rate bond. This embodies the classical approach to synthetic swap creation, and it will be the starting point of the following discussion.  

# 14.2.3.1 Another formula  

We have already derived a formula for the (forward) swap rate, $s_{t_{0}}$ , that gives an arbitrage-free swap value:  

$$
s_{t_{0}}=\frac{[B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})+B(t_{0},t_{4})F(t_{0},t_{3})]}{[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}
$$  

Or, in the general form,  

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
\begin{array}{c}{{s_{t_{0}}=\displaystyle\frac{1}{\delta[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]}\Bigg\{B(t_{0},t_{2})\Bigg[\displaystyle\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}-1\Bigg]}}\\ {{+B(t_{0},t_{3})\Bigg[\displaystyle\frac{B(t_{0},t_{2})}{B(t_{0},t_{3})}-1\Bigg]+B(t_{0},t_{4})\Bigg[\displaystyle\frac{B(t_{0},t_{3})}{B(t_{0},t_{4})}-1\Bigg]\Bigg\}}}\end{array}
$$  

Simplifying the common $B(t_{0},t_{i})$ terms on the right-hand side, we get  

$$
\begin{array}{l}{{s_{t_{0}}=\displaystyle\frac{1}{\delta\sum_{i=1}^{3}B(t_{0},t_{i+1})}([B(t_{0},t_{1})-B(t_{0},t_{2})]}}\\ {{\mathrm{}+[B(t_{0},t_{2})-B(t_{0},t_{3})]+[B(t_{0},t_{3})-B(t_{0},t_{4})]}}\\ {{\mathrm{}=\displaystyle\frac{1}{\delta\sum_{i=1}^{3}B(t_{0},t_{i+1})}[B(t_{0},t_{1})-B(t_{0},t_{4})]}}\end{array}
$$  

We can try to recognize what this formula means by first rearranging,  

$$
\delta s_{t_{0}}[B(t_{0},t_{2})+B(t_{0},t_{3})+B(t_{0},t_{4})]=[B(t_{0},t_{1})-B(t_{0},t_{4})]
$$  

and then regrouping:  

$$
B(t_{0},t_{1})-\big[s_{t_{0}}\delta B(t_{0},t_{2})+s_{t_{0}}\delta B(t_{0},t_{3})+B(t_{0},t_{4})\big(1+\delta s_{t_{0}}\big)\big]=0
$$  

The equation equates two cash flows. $B(t_{0},t_{1})$ is the value of 1 dollar to be received at time $t_{1}$ . Thus, the position needs to be long a $t_{1}$ -maturity discount bond. Second, there appear to be coupon payments of constant size, $\delta s_{t_{0}}$ at times $t_{2}$ , $t_{3}$ , $t_{4}$ and then a payment of 1 dollar at time $t_{4}$ .7 Thus, this seems to be a short (forward) position in a $t_{4}$ -maturity coupon bond with coupon rate $s_{t_{0}}$ .  

To summarize, this particular forward fixed receiver interest rate swap is equivalent to  

Fixed-payer forward sw $\mathrm{{ap}=\{B u y\ }}t_{1}$ discount bond; forward sell $t_{4}$ -maturity coupon bond  

This synthetic will replicate the value of the forward swap. Note that the floating cash flows do not have to be replicated. This is because, in a forward swap, the floating cash flows are related to deposits (loans) that will be made in the future, at interest rates to be determined then.  

# 14.2.3.2 Marking to market  

We can use the same framework for discussing mark-to-market practices. Start at time $t_{0}$ . As discussed earlier, the market is willing to pay the known cash flows  

$$
\left\{s_{t_{0}}N\delta,s_{t_{0}}N\delta,s_{t_{0}}N\delta\right\}
$$  

against the random cash flows  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

Now, let a short but noninfinitesimal time, $\Delta$ , pass. There will be a new swap rate $s_{t_{0}}+\Delta$ , which, in all probability, will be different than $s_{t_{0}}.$ This means that the market is now willing to pay the new known cash flows  

$$
\left\{s_{t_{0}+\Delta}N\delta,s_{t_{0}+\Delta}N\delta,s_{t_{0}+\Delta}N\delta\right\}
$$  

against the same random cash flows:  

$$
\left\{L_{t_{1}}N\delta,L_{t_{2}}N\delta,L_{t_{3}}N\delta\right\}
$$  

This implies that the value of the original swap, written at time $t_{0}$ , is nonzero and is given by the difference:  

$$
\begin{array}{r}{\Big[s_{t_{0}+\Delta}N\delta-s_{t_{0}}N\delta\Big][B(t_{0}+\Delta,t_{2})+B(t_{0}+\Delta,t_{3})+B(t_{0}+\Delta,t_{4})]}\end{array}
$$  

This can be regarded as the profit and loss for the fixed payer. At time $t_{0}+\Delta$ , the floating payment to be received has a value given by Eq. (14.47), and the actual floating payments would cancel out.8 We can apply the same reasoning using the FRA rates and calculate the mark-to-market value of the original swap from the difference:  

$$
\left(N\delta\left[\sum_{i=1}^{n}\omega_{i0}F(t_{0},t_{i})\right]-N\delta\left[\sum_{i=1}^{n}\omega_{i(t_{0}+\Delta)}F(t_{0}+\Delta,t_{i})\right]\right)\sum_{i=1}^{n}B(t_{0}+\Delta,t_{i+1})
$$  

This way of writing the expression shows the profit and loss from the point of view of a fixed receiver. It should be noted that here the weights $\omega_{i}$ have time subscripts, since they will change as time passes. Thus, managing a swap book will depend nonlinearly on the forward rate dynamics.9  

# 14.3 TERM STRUCTURE MODELING  

The framework outlined in this chapter demonstrates the links between swap, bond, and FRA markets. We will now discuss the term structure implications of the derived formulas. The set of formulas we studied implies that, given the necessary information from two of these markets, we can, in principle, obtain arbitrage-free prices for the remaining market.10 We discuss this briefly, after noting the following small, but significant, modification. Term structure models concern forward rates as well as spot rates. As a matter of fact, traditional yield curve construction is done by first obtaining the spot yields and then moving to forward rates.  

Following this tradition, and noting that spot swaps are more liquid than forward swaps, in this section we let $s_{t_{0}}^{n}$ denote the spot swap rate with maturity $n$ years. Without loss of generality, we can assume that swap maturities are across years $n=1,...,30$ , so that the longest dated swap is for 30 years.11 The discussion will be conducted in terms of spot swap rates.  

# 14.3.1 DETERMINING THE FORWARD RATES FROM SWAPS  

Given a sufficient number of arbitrage-free values of observed spot swap rates $\left\{s_{t_{0}}^{n}\right\}$ and using the equalities  

$$
s_{t_{0}}^{n}=\frac{\sum_{i=0}^{n-1}B(t_{0},t_{i+1})F(t_{0},t_{i})}{\sum_{i=0}^{n-1}B(t_{0},t_{i+1})}
$$  

and  

$$
\frac{B(t_{0},t_{i})}{B(t_{0},t_{i+1})}=(1+\delta F(t_{0},t_{i}))
$$  

We can obtain all forward rates, for the case $\delta=1$ . By substituting the $B(t_{0},t_{i})$ out from the first set of equations, we obtain $n$ equations in $n$ forward rates.12 In the case of $\delta=1/4$ or $\delta=1/2$ , there are more unknown $F(t_{0},t_{i})$ than equations, if traded swap maturities are in years. Under these conditions, the $t_{i}$ would run over quarters whereas the superscript in $s_{t_{0}}^{n}$ , $n=1$ , 2, . . . will be in years. This is due to the fact that swap rates are quoted for annual intervals, whereas the settlement dates would be quarterly or semiannual. Some type of interpolation of swap rates or modeling will be required, which is common even in traditional yield curve calculations.  

# 14.3.2 DETERMINING THE $B(t_{0},\ t_{i})$ FROM FORWARD RATES  

Now, if the forward rates $\{F(t_{0},t_{i})\}$ and the current LIBOR curve are provided by markets or are obtained from $\{s_{t_{0}}^{n}\}$ as in our case, we can use the formula  

$$
B(t_{0},t_{i+1})=\frac{1}{\prod_{j=0}^{i}(1+\delta F(t_{0},t_{j}))}
$$  

to calculate the arbitrage-free values of the relevant pure discount bond prices. In each case, we can derive the values of $B(t_{0},t_{i})$ from the observed $\{F(t_{0},t_{\mathrm{i}})\}$ and $\{s_{t_{0}}^{n}\}$ . This procedure would price the FRAs and bonds off the swap markets. It is called the curve algorithm.  

# 14.3.3 DETERMINING THE SWAP RATE  

We can proceed in the opposite direction as well. Given arbitrage-free values of forward rates, we can, in principle, use the same formulas to determine the swap rates. All we need to do is (i) calculate the discount bond prices from the forward rates and (ii) substitute these bond prices and the appropriate forward rates in our formula:  

$$
s_{t_{0}}^{n}=\frac{\sum_{i=0}^{n-1}B(t_{0},t_{i+1})F(t_{0},t_{i})}{\sum_{i=0}^{n-1}B(t_{0},t_{i+1})}
$$  

Repeating this for all available $s_{t_{0}}^{n}$ $,n=1,...,30$ , we obtain the arbitrage-free swap curve and discounts. In this case, we would be going from the spot and forward LIBOR curve to the (spot) swap curve.  

# 14.3.4 REAL-WORLD COMPLICATIONS  

There are, of course, several real-world complications to going back and forth between the forward rates, discount bond prices, and swap rates. Let us mention three of these. First, as mentioned in the previous section, in reality swaps are traded for yearly intervals and the FRAs or Eurodollar contracts are traded for 3-month or 6-month tenors. This means that if we desired to go from swap quotes to quotes on forward rates using these formulas, there will be the need to interpolate the swap rates for portions of a year.  

Second, observed quotes on forward rates do not necessarily come from paid-in-arrears FRAs. Market-traded FRAs settle at the time the LIBOR rate is observed, not at the end of the relevant period. The FRA rates generated by these markets will be consistent with the formulas introduced earlier. On the other hand, some traders use interest rate futures, and, specifically, Eurocurrency futures, in hedging their swap books. Futures markets are more transparent than the FRA markets and have a great deal of liquidity. But the forward rates determined in futures markets require convexity adjustments before they can be used in the swap formulas discussed in this chapter.  

Third, the liquidity of FRA and swap rates depends on the maturity under consideration. As mentioned earlier, FRAs are more liquid for the shorter end of the curve, whereas swaps are more liquid at the longer end. This means that it may not be possible to go from FRA rates to swap rates for maturities over 5 years. Similarly, for very short maturities there will be no observed quotes for swaps.  

# 14.3.4.1 Remark  

Another important point needs to be mentioned here. In this chapter, for simplicity, our treatment has followed the pre-GFC convention in academic work of using the term “LIBOR” as if it relates to a default-free loan. In practice, LIBOR rates $L_{t_{i}}$ are not risk free. Admittedly, this was implicit in the fixing process of the LIBOR rate. The banks that contributed to the rate had, in general, ratings of AA or $\mathrm{\AA-}$ , and the interest rate that they paid reflected this level of credit risk. However, the probability of such highly rated banks defaulting was considered small and therefore market participants and academics considered LIBOR a reasonable proxy for the risk-free rate. Before the GFC, LIBOR was a key indicator of what banks were willing to lend to each other, and 3-month LIBOR in particular emerged as a key benchmark in the interest rate swaps market. As discussed in Chapter 3 during the GFC, the LIBOR rate rose dramatically and diverged from the OIS as fears of counter-party risk became acute. This led to the realization that LIBOR could not be used as a measure of the risk-free rate. Following the GFC, market participants started using the OIS as the discount rate for the pricing of (collateralized) interest rate swaps. In June 2010, LCH.Clearnet announced that it would use the OIS instead of LIBOR to discount its $\$218$ trillion interest rate swap portfolio. The intuition is that in fully collateralized swaps, financial counterparties are exposed to overnight risk to other financial counterparties only and not the risk of the full term of a particular loan or instrument. Academic models have been developed to incorporate credit and counter-party risk more explicitly into derivatives pricing models. Such models and recent market practice are discussed in detail in Chapter 24.  

Thus, if a financial engineer follows the procedures described here, the resulting curve will be the swap curve and not the treasury or sovereign curve. This swap curve will be “above” the sovereign or treasury curve, and the difference will be the curve for the swap spreads.  

# 14.4 TERM STRUCTURE DYNAMICS  

In the remainder of this chapter, we will see that the Forward LIBOR Model is the correct way to approach term structure dynamics. The model is based on the idea of converting the dynamics of each forward rate into a Martingale using some properly chosen forward measure. According to the linkages between sectors shown in this chapter, once such dynamics are obtained, we can use them to generate dynamics for other fixed-income instruments.  

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

1. A default-free zero-coupon bond $B(t_{0},t_{2})$ that matures at time $t_{2}$ .   
2. A default-free zero-coupon bond that matures one period later, at time $t_{3}$ . Its current price is expressed as $B(t_{0},t_{3})$ .   
3. A savings account that pays (in-arrears) the discrete-time simple rate $L_{t_{i}}$ observed at time $t_{i}$ . Therefore, the savings account payoff at $t_{2}$ will be  

$$
R_{t_{2}}=\left(1+\delta L_{t_{0}}\right)\left(1+\delta L_{t_{1}}\right)
$$  

Note that the $L_{t_{1}}$ observed from the initial time $t_{0}$ will be a random variable.  

4. An FRA contracted at time $t_{0}$ and settled at time $t_{2}$ , where the buyer receives/pays the differential between the fixed rate $F(t_{0},t_{1})$ and the floating rate $L_{t_{1}}$ at time $t_{2}$ . We let the notional amount of this instrument equal 1 and abbreviate the forward rate to $F_{t_{0}}$ . The final payoff can be written as  

$$
\left(L_{t_{1}}-F_{t_{0}}\right)\delta
$$  

These assets can be organized in the following payoff matrix $D$ for time $t_{2}$ as in Chapter 12, assuming that at every $t_{i}$ , from every node there are only two possible movements for the underlying random process. Denoting these movements by u, d, we can write13  

$$
D=\left[\begin{array}{c c c c c}{{R_{t_{2}}^{u u}}}&{{R_{t_{2}}^{u d}}}&{{R_{t_{2}}^{d u}}}&{{R_{t_{2}}^{d d}}}\\ {{1}}&{{1}}&{{1}}&{{1}}\\ {{B_{t_{2}}^{u u}}}&{{B_{t_{2}}^{u d}}}&{{B_{t_{2}}^{d u}}}&{{B_{t_{2}}^{d d}}}\\ {{\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)}}&{{\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)}}&{{\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)}}&{{\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)}}\end{array}\right]
$$  

where the $B_{t_{2}}^{i j}$ is the (random) value of the $t_{3}$ maturity discount bond at time $t_{2}$ . This value will be state dependent at $t_{2}$ because the bond matures one period later, at time $t_{3}$ . Looked at from time $t_{0}$ , this value will be random. Clearly, with this $D$ matrix we have simplified the notation significantly. We are using only four states of the world, expressing the forward rate $F(t_{0},t_{2})$ simply as $F_{t_{0}}$ , and the $B(t_{2},t_{3})^{i j}$ simply as $B_{t_{2}}^{i j}$ .  

If the FRA, the savings account, and the two bonds do not admit any arbitrage opportunities, the fundamental theorem of asset pricing permits the following linear representation:  

$$
\left[{\begin{array}{c}{1}\\ {B(t_{0},t_{2})}\\ {B(t_{0},t_{3})}\\ {0}\end{array}}\right]=\left[{\begin{array}{c c c c}{R_{t_{2}}^{u u}}&{R_{t_{2}}^{u d}}&{R_{t_{2}}^{d u}}&{R_{t_{2}}^{d d}}\\ {1}&{1}&{1}&{1}\\ {B_{t_{2}}^{u u}}&{B_{t_{2}}^{u d}}&{B_{t_{2}}^{d u}}&{B_{t_{2}}^{d d}}\\ {\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{u}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}&{\delta\big(F_{t_{0}}-L_{t_{1}}^{d}\big)}\end{array}}\right]\left[{\begin{array}{c}{Q^{u u}}\\ {Q^{u d}}\\ {Q^{d u}}\\ {Q^{d d}}\end{array}}\right]
$$  

where $\{Q^{i j},i,j=u,d\}$ are the four state prices for period $t_{2}$ . Under the no-arbitrage condition, the latter exist and are positive  

$$
Q^{i j}>0
$$  

for all states $i,j$ .14  

This matrix equation incorporates the ideas that (i) the fair market value of an FRA is zero at initiation, (ii) 1 dollar is to be invested in the savings account originally, and (iii) the bonds are default free. They mature at times $t_{2}$ and $t_{3}$ . $R_{t_{2}}^{i,j}$ , finally, represents the gross returns to the savings account as of time $t_{2}$ . Because the interest rate that applies to time $t_{i}$ is paid in arrears, at time $t_{i}+\delta$ , we can express these gross returns as functions of the underlying LIBOR rates in the following way:  

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
\begin{array}{r l}&{\Tilde{p}_{u u}=R_{t_{2}}^{u u}Q^{u u}}\\ &{\Tilde{p}_{u d}=R_{t_{2}}^{u d}Q^{u d}}\\ &{\Tilde{p}_{d u}=R_{t_{2}}^{d u}Q^{d u}}\\ &{\Tilde{p}_{d d}=R_{t_{2}}^{d u}Q^{d u}}\\ &{\Tilde{p}_{d d}=R_{t_{2}}^{d d}Q^{d d}}\end{array}
$$  

The $\{\tilde{p}_{i j}\}$ then have the characteristics of a probability distribution, and they can be exploited with the associated Martingale equality.  

We know from Chapter 12 that, under the condition that every asset’s price is arbitrage free, $\{Q^{i j},i,j=u,d\}$ exist and are all positive, and $\tilde{p}_{i j}$ will be the risk-neutral probabilities. Then, by using the last row of the system in Eq. (14.58) we can write the following equality:  

$$
\begin{array}{l}{{\displaystyle0=\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)\frac1{R_{t_{2}}^{u u}}\right]\tilde{p}_{u u}+\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{u}\right)\frac1{R_{t_{2}}^{u d}}\right]\tilde{p}_{u d}+\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)\frac1{R_{t_{2}}^{d u}}\right]\tilde{p}_{d u}}}\\ {{\displaystyle~+\left[\delta\left(F_{t_{0}}-L_{t_{1}}^{d}\right)\frac1{R_{t_{2}}^{d d}}\right]\tilde{p}_{d d}}}\end{array}
$$  

Here, $\big(F_{t_{0}}-L_{t_{1}}^{i}\big),i=u,d$ are “normalized” so that $Q^{i j}$ can be replaced by the respective $\tilde{p}_{i j}$ . Note that in this equation, $F_{t_{0}}$ is determined at time $t_{0}$ , and can be factored out. Grouping and rearranging, we get  

$$
F_{t_{0}}=\frac{\left(\left[L_{t_{1}}^{u}\left(1/R_{t_{2}}^{u u}\right)\right]\tilde{p}_{u u}+\left[L_{t_{1}}^{u}\left(1/R_{t_{2}}^{u d}\right)\right]\tilde{p}_{u d}+\left[L_{t_{1}}^{d}\left(1/R_{t_{2}}^{d u}\right)\right]\tilde{p}_{d u}+\left[L_{t_{1}}^{d}\left(1/R_{t_{2}}^{d d}\right)\right]\tilde{p}_{d d}\right)}{\left(\left(1/R_{t_{2}}^{u u}\right)\tilde{p}_{u u}+\left(1/R_{t_{2}}^{u d}\right)\tilde{p}_{u d}+\left(1/R_{t_{2}}^{d u}\right)\tilde{p}_{d u}+\left(1/R_{t_{2}}^{d d}\right)\tilde{p}_{d d}\right)}
$$  

This can be written using the expectation operator  

$$
F_{t_{0}}=\frac{1}{E_{t_{0}}^{\tilde{P}}\big[1/R_{t_{2}}\big]}E_{t_{0}}^{\tilde{P}}\bigg[\frac{L_{t_{1}}}{R_{t_{2}}}\bigg]
$$  

According to this last equality, if $R_{t_{2}}$ is a random variable and is not independent of $L_{t_{1}}$ ,15 it cannot be moved outside the expectation operator. In other words, for general $i$ ,  

$$
\begin{array}{r}{F(t,t_{i})\neq E_{t}^{\tilde{P}}[L_{t_{i}}]\quad t<t_{i}}\end{array}
$$  

That is to say, under the risk-neutral measure, $\tilde{P}$ , the forward rate for time $t_{i}$ is a biased “forecast” of the future LIBOR rate $L_{t_{i}}$ . In fact, it is not very difficult to see that the $E_{t}^{\tilde{p}}[L_{t_{i}}]$ is the futures rate that will be determined by, say, a Eurodollar contract at time $i$ . The “bias” in the forward rate, therefore, is associated with the convexity adjustment.  

Another way of putting it is that $F_{t}$ is not a Martingale with respect to the risk-neutral probability $\tilde{P}$ , and that a discretized stochastic difference equation that represents the dynamics of $F_{t}$ will, in general, have a trend:  

$$
F_{t+\Delta}-F_{t}=a(F_{t},t)F_{t}\Delta+\sigma(F_{t},t)F_{t}[W_{t+\Delta}-W_{t}]
$$  

where $\boldsymbol{a}(\boldsymbol{F}_{t},t)$ is the non-zero expected rate of change of the forward rate under the probability $\Tilde{P}_{-}$  

The fact that $F_{t}$ is not a Martingale with respect to probability $\tilde{P}$ makes the risk-neutral measure an inconvenient working tool for pricing and risk management in the fixed-income sector. Before we can use Eq. (14.71), we need to calibrate the drift factor $a(.)$ . This requires first obtaining a functional form for the drift under the probability $\tilde{P}$ . The original HJM article does develop a functional form for such drifts using continuously compounded instantaneous forward rates. But, this creates an environment quite different from LIBOR-driven markets and the associated actuarial rates Lti used here.16  

On the other hand, we will see that in the interest rate sector, arbitrage-free drifts become much easier to calculate if we use the Forward LIBOR Model and switch to appropriate forward measures.  

# 14.4.2.2 The forward measure  

Consider defining a new set of probabilities for the states under consideration by using the defaultfree zero-coupon bond that matures at time $t_{2}$ . First, we present the simple case. Use the second row of the system in Eq. (14.58):  

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

It is important to index the forward measure with the superscript, $t_{2}$ , in these fixed-income models, as other forward measures would be needed for other forward rates. The superscript is a nice way of keeping track of the measure being used. For some instruments, these measures have to be switched sequentially.  

As discussed in Chapter 12, using the $t_{2}$ -forward measure we can price any asset $C_{t},$ with time $t_{2}$ payoffs $C_{t_{2}}^{i j}$  

$$
\begin{array}{r}{C_{t_{0}}=\left[B(t_{0},t_{2})C_{t_{2}}^{u u}\right]\tilde{p}_{u u}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{u d}\right]\tilde{p}_{u d}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{d u}\right]\tilde{p}_{d u}^{t_{2}}+\left[B(t_{0},t_{2})C_{t_{2}}^{d d}\right]\tilde{p}_{d d}^{t_{2}}}\end{array}
$$  

This implies that, for an asset that settles at time $T$ and has no other payouts, the general pricing equation is given by  

$$
C_{t}=B(t,T)E_{t}^{\tilde{P}T}[C_{T}]
$$  

where $\Tilde{P}^{T}$ is the associated $T$ -forward measure and where $C_{T}$ is the time $T$ payoff. According to this equality, it is the ratio  

$$
Z_{t}=\frac{C_{t}}{B(t,T)}
$$  

which is a Martingale with respect to the measure $\Tilde{P}^{T}$ . In fact, $B(t,T)$ being the discount factor for time $T.$ , and, hence, being $^{<1}$ , $Z_{t}$ is nothing more than the $T_{\mathbf{\delta}}$ -forward value of the $C_{t}$ . This means that the forward measure $\Tilde{P}^{T}$ operates in terms of Martingales that are measured in time $T$ dollars. The advantage of the forward $\Bar{P}^{T}$ measure becomes clear if we apply the same transformation to price the FRA as was done earlier for the case of the risk-neutral measure.  

# 14.4.2.3 Arbitrage-free SDEs for forward rates  

To get arbitrage-free dynamics for forward rates, we now go back to the simple model in Eq. (14.58). Divide the fourth row of the system by $B(t_{0},t_{2})$ and rearrange,  

$$
\begin{array}{r l r}{\lefteqn{\frac{F_{t_{0}}}{B(t_{0},t_{2})}\big[Q^{u u}+Q^{u d}+Q^{d u}+Q^{d d}\big]=\frac{L_{t_{1}}^{u}}{B(t_{0},t_{2})}Q^{u u}+\frac{L_{t_{1}}^{u}}{B(t_{0},t_{2})}Q^{u d}}}\\ &{}&{+\ \frac{L_{t_{1}}^{d}}{B(t_{0},t_{2})}Q^{d u}+\frac{L_{t_{1}}^{d}}{B(t_{0},t_{2})}Q^{d d}}\end{array}
$$  

Now, as done in Chapter 12, substitute the $t_{2}$ -forward measure into this equation using the equality:  

$$
\tilde{p}_{i j}^{t_{2}}=\frac{1}{B(t_{0},t_{2})}Q^{i j}
$$  

The equation becomes  

$$
\boldsymbol{F}_{t_{0}}=[L_{t_{1}}^{u}]\tilde{p}_{u u}^{t_{2}}+[L_{t_{1}}^{u}]\tilde{p}_{u d}^{t_{2}}+[L_{t_{1}}^{d}]\tilde{p}_{d u}^{t_{2}}+[L_{t_{1}}^{d}]\tilde{p}_{d d}^{t_{2}}
$$  

Extending this to the general case of $m$ discrete states  

$$
F_{t_{0}}=\sum_{i=1}^{m}L_{t_{1}}^{i}{\tilde{p}}_{i}^{t_{2}}
$$  

This is clearly the expectation  

$$
F_{t_{0}}=E_{t_{0}}^{\tilde{P}^{t_{2}}}[L_{t_{1}}]
$$  

This means that, under the measure $\tilde{P}^{t_{2}}$ , the forward rate for the period $[t_{1},~t_{2}]$ will be an unbiased estimate of the corresponding LIBOR rate.  

Consequently, switching to the general notation of $(t,T)$ , the process  

$$
F_{t}=F(t,T,T+\delta)
$$  

will be a Martingale under the $(T+\delta)$ -forward measure $\Tilde{P}^{T+\delta}$ . Assuming that the errors due to discretization are small, its dynamics can be described by a (discretized) SDE over small intervals of length $\Delta^{17}$  

$$
F_{t+\Delta}-F_{t}=\sigma_{t}F_{t}\Delta W_{t}
$$  

where $W_{t}$ is a Wiener process under the measure $\tilde{P}^{T+\delta}.\Delta W_{t}$ is the Wiener process increment:  

$$
\Delta W_{t}=W_{t+\Delta}-W_{t}
$$  

This (approximate) equation has no drift component since, by arbitrage arguments, and writing for the general $t,T,$ we have  

$$
1+\delta F(t,T)=\frac{B(t,T)}{B(t,T+\delta)}
$$  

It is clear from the normalization arguments of Chapter 12 that, under the measure $\tilde{P}^{T+\delta}$ and rneosrpmecatl tzoa $\Tilde{P}^{T^{+\delta}}$ .y $B(t,T+\delta)$ the croartrieospoonntdhiengr fgohrt-wharndd astiedea ofMtahrtiisngeaqluea, ison ihsata hMeairtminplgiaelde SwDitEh will have no drift.  

However, note that the forward rate for the period $[T-\delta,T]$ given by  

$$
1+\delta F(t,T-\delta)=\frac{B(t,T-\delta)}{B(t,T)}
$$  

is not a Martingale under the same forward measure $\tilde{P}^{T^{+\delta}}$ . Instead, this forward rate is a Martingale under its own measure $\Tilde{P}^{T}$ which requires normalization by $B(t,T)$ . Thus, we get a critical result for the Forward LIBOR Model:  

Each forward rate F(t, Ti) admits a Martingale representation under its own forward measure P\~Ti1δ.  

This means that each forward rate dynamics can be approximated individually by a difference equation with no drift given the proper normalization. The only parameter that would be needed to characterize such dynamics is the corresponding forward rate volatility.  

# 14.4.3 ARBITRAGE-FREE DYNAMICS  

The previous section discussed the dynamics of forward rates under their own forward measure. We now show what happens when we use one forward measure for two forward rates that apply to two consecutive periods. Then, one of the forward rates has to be evaluated under a measure different from its own, and the Martingale dynamics will be broken. Yet, we will be able to obtain the new drift.  

To keep the issue as simple as possible, we continue with the basic model in Eq. (14.58), except we add one more time period so that we can work with two nontrivial forward rates and their respective forward measures. This is the simplest setup within which we can show how measure change technology can be implemented. Using the forward measures introduced earlier and shown in Figure 14.4, we can now define the following forward rate dynamics for the two forward LIBOR processes $\{F(t_{0},t_{1}),F(t_{0},t_{2})\}$ under consideration. The first will be a Martingale under the normalization with $B(t_{0},\ t_{2})$ , whereas the second will be a Martingale under the normalization with $B(t_{0},\ t_{3})$ . This means that $\tilde{P}^{t_{2}}$ and $\tilde{P}^{t_{3}}$ are the forward LIBOR processes’ “own” measures.  

Altogether, it is important to realize that during the following discussion we are working with a very simple example involving only four time periods, $t_{0},t_{1},t_{2}$ , and $t_{3}$ . We start with the arbitrage-free  

![](c3d400d2955741c4928a34fab802372b72e74bea6ec5519ac55390efb8d36308.jpg)  

# FIGURE 14.4  

Spot and forward LIBOR process.  

“dynamics” of the forward rate $F(t_{0},t_{2})$ . In our simplified setup, we will observe only two future values of this forward rate at times $t_{1}$ and $t_{2}$ . These are given by  

$$
\begin{array}{r}{F(t_{1},t_{2})-F(t_{0},t_{2})=\sigma_{2}F(t_{0},t_{2})\Delta W_{t_{1}}^{t_{3}}}\\ {F(t_{2},t_{2})-F(t_{1},t_{2})=\sigma_{2}F(t_{1},t_{2})\Delta W_{t_{2}}^{t_{3}}}\end{array}
$$  

The superscript in $\triangle_{\ast t.}W_{t_{i}}^{t_{3}},~i=1,2$ , indicates that the Wiener process increments have zero mean under the probability $\tilde{P}^{t_{3}}$ . These equations show how the “current” value of the forward rate $F(t_{0},t_{2})$ first changes to become $F(t_{1},t_{2})$ and then ends up as $F(t_{2},t_{2})$ . The latter is also $L_{t_{2}}$ .  

For the “nearer” forward rate $F(t_{0},t_{1})$ , we need only one equation18 defined under the normalization with the bond $B(t_{0},t_{2})$ (i.e., the $\tilde{P}^{t_{2}}$ measure) and the associated zero drift:  

$$
F(t_{1},t_{1})-F(t_{0},t_{1})=\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{2}}
$$  

Similarly, the superscript in $\Delta W_{t_{1}}^{t_{2}}$ indicates that this Wiener process increment has zero mean under the probability $\tilde{P}^{t_{2}}$ . Here, the $F(t_{1},t_{1})$ is also the LIBOR rate $L_{t_{1}}$ . We reemphasize that each dynamic is defined under a different probability measure. Under these different forward measures, each forward LIBOR process behaves like a Martingale.19 Consequently, there are no drift terms in either equation.  

Fortunately, as long as we can work with these equations separately, no arbitrage-free drift terms need to be estimated or calibrated. The only parameters we need to determine are the volatilities of the two forward rates: $\sigma_{2}$ for the forward rate $F(t_{0},t_{2})$ and $\sigma_{1}$ for the forward rate $F(t_{0},t_{1})$ .20  

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
E_{t_{0}}^{\tilde{P}^{t_{2}}}\left[\Delta W_{t_{1}}^{t_{3}}\right]=\lambda_{t_{0}}^{t_{2}}\Delta\neq0
$$  

Here, $\lambda_{t_{0}}^{t_{2}}$ is a mean correction that needs to be made because we are evaluating the Wiener increment under a measure different from its own forward measure $\tilde{P}^{t_{3}}$ . This, in turn, means that the dynamics for $F(t_{0},t_{2})$ lose their Martingale characteristic.  

We will now comment on the second moments, variances, and covariances. Each Wiener increment is assumed to have the same variance under the two measures. The Girsanov theorem ensures that this is true in continuous time. In discrete time, this holds as an approximation. Finally, we are operating in an environment where there is only one factor.21 So, the Wiener process increments defined under the two forward measures will be exactly correlated if they belong to the same time period. In other words, although their means are different, we can assume that, approximately, their covariance would be $\Delta$ :  

$$
E^{\tilde{P}^{t_{3}}}\left[\Delta W_{t}^{t_{3}}\Delta W_{t}^{t_{2}}\right]=E^{\tilde{P}^{t_{2}}}\left[\Delta W_{t}^{t_{3}}\Delta W_{t}^{t_{2}}\right]=\Delta
$$  

Similar equalities will hold for the variances as well.22  

# 14.4.3.1 Review  

The results thus far indicate that for the pricing and risk managing of equity-linked assets, the riskneutral measure $\tilde{P}$ may be quite convenient since it is easily adaptable to lognormal models where the arbitrage-free drifts are simple and known functions of the risk-free interest rate. As far as equity products are concerned, the assumption that short rates are constant is a reasonable approximation, especially for short maturities. Yet, for contracts written on future values of interest rates (rather than on asset prices), the use of the $\tilde{P}$ leads to complex arbitrage-free dynamics that cannot be captured easily by Martingales and, hence, the corresponding arbitrage-free drift terms may be difficult to calibrate.  

Appropriate forward measures, on the other hand, result in Martingale equalities and lead to dynamics convenient for the calculation of arbitrage-free drifts, even when they are not zero. Forward (and swap) measures are the proper working probabilities for fixed-income environments.  

# 14.4.4 A MONTE CARLO IMPLEMENTATION  

Suppose we want to generate Monte Carlo “paths” from the two discretized SDEs for two forward rates, $F(t_{i},t_{1})$ and $F(t_{i},t_{2})$ ,  

$$
\begin{array}{r l}&{F(t_{i},t_{1})-F(t_{i-1},t_{1})=\sigma_{1}F(t_{i-1},t_{1})\Delta W_{t_{i}}^{t_{2}}}\\ &{F(t_{i},t_{2})-F(t_{i-1},t_{2})=\sigma_{2}F(t_{i-1},t_{2})\Delta W_{t_{i}}^{t_{3}}}\end{array}
$$  

where $i=1$ , 2 for the second equation and $i=1$ for the first.  

It is easy to generate individual paths for the two forward rates separately by using these Martingale equations defined under their own forward measures. Consider the following approach.  

Suppose volatilities $\sigma_{1}$ and $\sigma_{2}$ can be observed in the market. We select two random variables $\{\Delta W_{1}^{3},\Delta W_{2}^{3}\}$ from the distribution  

$$
\Delta W_{i}^{3}\sim N(0,\Delta)
$$  

with a pseudo-random number generator, and then calculate, sequentially, the randomly generated forward rates in the following order, starting with the observed $F(t_{0},t_{2})$  

$$
\begin{array}{c}{F(t_{1},t_{2})^{1}=F(t_{0},t_{2})+\sigma_{2}F(t_{0},t_{2})\Delta W_{1}^{3}}\\ {F(t_{2},t_{2})^{1}=F(t_{1},t_{2})^{1}+\sigma_{2}F(t_{1},t_{2})^{1}\Delta W_{2}^{3}}\end{array}
$$  

where the superscript on the left-hand side indicates that these values are for the first Monte Carlo trajectory. Proceeding sequentially, all the terms on the right-hand side will be known. This gives the first simulated “path” $\{F(t_{0},\dot{t_{2}}),F(t_{1},t_{2})^{1},F(t_{2},t_{2})^{1}\}$ . We can repeat this algorithm to obtain $M$ such paths for potential use in pricing.  

What does this imply for the other forward LIBOR process $F$ $\textit{F}(t_{0},t_{1})?$ Can we use the same randomly generated random variable $\Delta W_{1}^{3}$ in the Martingale equation for $F(t,\ t_{1})$ , and obtain the first “path” $\{F(t_{0},t_{1}),\mathbb{F}(t_{1},t_{1})^{1}\}$ from  

$$
F(t_{1},t_{1})=F(t_{0},t_{1})+\sigma_{1}F(t_{0},t_{1})\Delta W_{1}^{3}
$$  

The answer is no. As mentioned earlier, the Wiener increments $\left\{\Delta W_{t_{1}}^{t_{2}}\right\}$ have zero mean only under the probability $\tilde{P}^{t_{2}}$ . But, the first set of random variables was selected using the measure $\tilde{P}^{t_{3}}$ . Under $\tilde{P}^{t_{2}}$ , these random variables do not have zero mean, but are distributed as  

$$
N\big(\lambda_{t_{0}}^{t_{2}}\Delta,\Delta\big)
$$  

Thus, if we use the same $\Delta W_{1}^{3}$ in Eq. (14.99), then we need to correct for the term $\lambda_{t_{0}}^{t_{2}}\Delta$ . To do this, we need to calculate the numerical value of $\lambda_{t_{0}}^{t_{2}}$ .  

Once this is done, the dynamics for $F(t_{0},t_{1})$ can be written as  

$$
F(t_{1},t_{1})=F(t_{0},t_{1})-\sigma_{1}F(t_{0},t_{1})\big(\lambda_{t_{0}}^{t_{2}}\Delta\big)+\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{3}}
$$  

To see why this is so, take the expectation under $\tilde{P}^{t_{2}}$ on the right-hand side and use the information in Eq. (14.100):  

$$
\begin{array}{r}{E_{t_{1}}^{\tilde{P}^{t_{2}}}\big[F(t_{0},t_{1})-\sigma_{1}F(t_{0},t_{1})\big(\lambda_{t_{0}}^{t_{2}}\Delta\big)+\sigma_{1}F(t_{0},t_{1})\Delta W_{t_{1}}^{t_{3}}\big]=F(t_{0},t_{1})}\end{array}
$$  

Thus, we get the correct result under the $\tilde{P}^{t_{2}}$ , after the mean correction. It is obvious that we need to determine these correction factors before the randomly generated Brownian motion increments can be used in all equations.  

Yet, note the following simple case. If the instrument under consideration has additive cash flows where each cash flow depends on a single forward rate, then individual zero-drift equations can be used separately to generate paths. This applies for several liquid instruments. For example, FRAs and especially swaps have payment legs that depend on one LIBOR rate only. Individual zero-drift equations can be used for valuing each leg separately, and then these values can be added using observed zero-coupon bond prices, $B(t,\ T_{i})$ . However, this cannot be done in the case of CMSs, for example, because each settlement leg will depend nonlinearly on more than one forward rate.  

We now discuss further how mean corrections can be conducted so that all forward rates are projected using a single forward measure. This will permit pricing instruments where individual cash flows depend on more than one forward rate.  

# 14.5 MEASURE CHANGE TECHNOLOGY  

We introduce a relatively general framework and then apply the results to the simple example shown previously. Basically, we need three previously developed relationships. We let $t_{i}$ obey  

$$
t_{0}<t_{1}<\cdots<t_{n}=T
$$  

with  

$$
t_{i}-t_{i-1}=\delta
$$  

denote settlement dates of some basic interest rate swap structure and limit our attention to forward rates for successive forward loans contracted to begin at $t_{i}.$ , and paid at $t_{i+1}$ . An example is shown in Figure 14.4.  

Result 1  

The forward rate at time $t$ , for a LIBOR-based forward loan that starts at time $t_{i}$ and ends at time $t_{i}+\delta$ , denoted by $F(t,t_{i})$ , admits the following arbitrage relationship:  

$$
1+F(t,t_{i})\delta=\frac{B(t,t_{i})}{B(t,t_{i+1})}\quad t<t_{i}
$$  

where, as usual, $B(t,\ t_{i})$ and $B(t,~t_{i+1})$ are the time $t$ prices of default-free zero-coupon bonds that mature at times $t_{\mathrm{i}}$ and $t_{i+1}$ , respectively.  

The left side of this equality is a gross forward return. The right side, on the other hand, is a traded asset price, $B(t,t_{i})$ , normalized by another asset price, $B(t,{t_{i+1}})$ . Hence, the ratio will be a Martingale under a proper measure—here, the forward measure denoted by $\tilde{P}^{t_{i+1}}$ .  

Result 2  

In a discrete state setting with $k$ states of the world, assuming that all asset prices are arbitrage free, and that the time $t_{i}$ state prices $Q^{j},j=1,...,k.$ , with $0<Q^{j}$ exist, the time $t_{i}$ values of the forward measure $\tilde{P}^{t_{i}}$ are given by23  

$$
\tilde{p}_{1}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{1},\tilde{p}_{2}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{2},\cdots,\tilde{p}_{k}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{k}
$$  

These probabilities satisfy:  

$$
\tilde{p}_{1}^{t_{i}}+\tilde{p}_{2}^{t_{i}}+\cdots+\tilde{p}_{k}^{t_{i}}=1
$$  

and  

$$
0<\tilde{p}_{j}^{t_{i}}\forall j
$$  

Note that the proportionality factors used to convert $Q^{j}$ into $\tilde{p}_{j}^{t_{i}}$ are equal across $j$ .  

Result 3  

In the same setting, the time $t_{i}$ -probabilities associated with the $t_{i+1}$ forward measure $\tilde{P}^{t_{i+1}}$ are given by  

$$
\tilde{p}_{1}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{1}}{B(t,t_{i+1})}Q^{1},\tilde{p}_{2}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{2}}{B(t,t_{i+1})}Q^{2},...,\tilde{p}_{k}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{k}}{B(t,t_{i+1})}Q^{k}
$$  

where the $B(t_{i},~t_{i+1})^{j}$ are the state-dependent values of the $t_{i+1}$ -maturity bond at time $t_{i}$ . Here, the bond that matures at time $t_{i+1}$ is used to normalize the cash flows for time $t_{i}$ . Since the maturity date is $t_{i+1}$ , the $B(t_{i},~t_{i+1})^{j}$ are not constant at $t_{i}$ . The factors used to convert $\{Q^{j}\}$ into P\~ti11 cease to be constant as well.  

We use these results in discussing the mechanics of measure changes. Suppose we need to price an instrument whose value depends on two forward LIBOR processes, $F(t,\ t_{i})$ and $F(t,\ t_{i+1})$ , simultaneously. We know that each process is a Martingale and obeys an SDE with zero drift under its own forward measure.  

Consider a one-factor setting, where a single Wiener process causes fluctuations in the two forward rates. Suppose that in this setting, starting from time $t$ , with $t<t_{i},i=1,...,n,a$ small time interval denoted by $h$ passes with $t+h<t_{i}$ . By imposing a Gaussian volatility structure, we can write down the individual discretized arbitrage-free dynamics for two successive forward rates $F\left(t,t_{i}\right)$ and $F(t,t_{i+1})$ as  

$$
F(t+h,t_{i})-F(t,t_{i})=\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{1}
$$  

and  

$$
F(t+h,t_{i+1})-F(t,t_{i+1})=\sigma^{i+1}F(t,t_{i+1})\Delta W_{t+h}^{2}
$$  

Changes in these forward rates have zero mean under their own forward measure and, hence, are written with zero drift. This means that the unique real-world Wiener process $W_{t+h}$ is now denoted by $\Delta W_{t+h}^{1}$ and $\Delta W_{t+h}^{2}$ in the two equations. These are normally distributed, with mean zero and variance $h$ only under their own forward measures, $\tilde{P}^{t_{i+1}}$ and $\tilde{P}^{t_{i+2}}$ .  

The superscript in $\boldsymbol{W}_{t+h}^{1}$ and $W_{t+h}^{2}$ expresses the $t_{i+1}$ and $t_{i+2}$ forward probability measures, respectively.24 Finally, note how we simplify the characterization of volatilities and assume that they are constant over time.  

The individual Martingale dynamics are very convenient from a financial engineering point of view. The respective drift components are zero and, hence, they need not be modeled during pricing. The only major task of the market practitioner is to get the respective volatilities $\sigma^{i}$ and $\bar{\sigma}^{i+1}$ .  

However, some securities’ prices may depend on more than one forward rate in a nonlinear fashion and their value may have to be calculated as an expectation under one single measure. For example, suppose a security’s price, $S_{t}$ , depends on $F(t,t_{i})$ and $F(t,t_{i+1})$ through a pricing relation such as:  

$$
S_{t}=E_{t}^{\tilde{P}}[g(F(t,t_{i}),F(t,t_{i+1}))]
$$  

where $g(.)$ is a known nonlinear function. Then, the expectation has to be calculated under one measure only. This probability can be either the time $t_{i+1}$ or the time $t_{i+2}$ forward measure. We then have to choose a forward rate equation with Martingale dynamics and carry out a mean correction to get the correct arbitrage-free dynamics for the other. The forward measure of one of the Martingale relationships is set as the working probability distribution, and the other equation(s) is obtained in terms of this unique probability by going through successive measure changes. We discuss this in detail below.  

# 14.5.1 THE MECHANICS OF MEASURE CHANGES  

We have the following expectations concerning $\Delta W_{t+h}^{1}$ and $\Delta W_{t+h}^{2}$ , defined in Eqs. (14.109) and (14.110)  

$$
\begin{array}{r}{E_{t}^{\tilde{P}^{t_{i+1}}}[\Delta W_{t+h}^{1}]=0}\\ {E_{t}^{\tilde{P}^{t_{i+2}}}[\Delta W_{t+h}^{2}]=0}\end{array}
$$  

Under their own forward measure, each Wiener increment has zero expectation. If we select $\tilde{P}^{t_{i+2}}$ as our working measure, one of these equalities has to change. We would have25  

$$
\begin{array}{c}{E_{t}^{\tilde{P}_{t+2}^{t_{i+2}}}[\Delta W_{t+h}^{1}]=\lambda_{t}h}\\ {E_{t}^{\tilde{P}_{t+2}^{t_{i+2}}}[\Delta W_{t+h}^{2}]=0}\end{array}
$$  

The value of $\lambda_{t}$ gives the correction factor that we need to use in order to obtain the correct arbitrage-free dynamics, if the working measure is $\tilde{P}^{t_{i+2}}$ . Calculating this factor implies that we can change measures in the dynamics of $F(t,t_{i})$ .  

We start with the original expectation:  

$$
E_{t}^{\tilde{P}_{t+1}^{t_{i+1}}}[\Delta W_{t+h}^{1}]=\sum_{j=1}^{k}\Delta W_{t+h}^{1j}\tilde{p}_{j}^{t_{i+1}}=0
$$  

where $\tilde{p}_{j}^{t_{i}+1}$ are the probabilities associated with the individual states $j=1,...,k$ . Now, using the identity,  

$$
\frac{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}\equiv1
$$  

we rewrite the expectation as  

$$
E_{t}^{\tilde{{p}}_{t+1}^{t_{i+1}}}\left[\Delta W_{t+h}^{1}\right]=\sum_{j=1}^{k}\Delta W_{t+h}^{1j}\frac{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}\equiv\tilde{p}_{j}^{t_{i+1}}
$$  

We regroup and use the definition of the $t_{\mathrm{i+1}}$ and $t_{\mathrm{i}+2}$ forward measures as implied by Result 3  

$$
\tilde{p}_{j}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{j}}{B(t,t_{i+1})}Q^{j}
$$  

and  

$$
\tilde{p}_{j}^{t_{i+2}}=\frac{B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})}Q^{j}
$$  

Rescaling the $Q^{j}$ using appropriate factors, Eq. (14.118) becomes  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})\left[\frac{B(t,t_{i+2})B(t_{i},t_{i+1})^{j}}{B(t,t_{i+1})B(t_{i},t_{i+2})^{j}}\right]\Tilde{p}_{j}^{t_{i+2}}=0
$$  

Note that the probabilities switch as the factors that were applied to the $Q^{j}$ changed. The superscript in $\boldsymbol{W}_{t+h}^{1}$ does not change.  

The next step in the derivation is to try to “recognize” the elements in this expectation. Using Result 1, we recognize the equality  

$$
1+\delta F(t_{i},t_{i+1})^{j}=\frac{B(t_{i},t_{i+1})^{j}}{B(t_{i},t_{i+2})^{j}}
$$  

Replacing, eliminating the $j\cdot$ -independent terms, and rearranging gives  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})(1+\delta F(t_{i},t_{i+1})^{j})\tilde{p}_{j}^{t_{i+2}}=0
$$  

Now, multiplying through, this leads to  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})\tilde{p}_{j}^{t_{i+2}}=-\left(\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})F(t_{i},t_{i+1})^{j}\tilde{p}_{j}^{t_{i+2}}\right)\delta
$$  

We can write this using the conditional expectation operator,  

$$
E_{t}^{\tilde{p}^{t_{1}+2}}[\Delta W_{t+h}^{1}]=-E_{t}^{\tilde{p}^{t_{1}+2}}[\Delta W_{t+h}^{1}F(t_{i},t_{i+1})]\delta.
$$  

In the last expression, the left-hand side is the desired expectation of the $\triangle W_{t+h}^{1}$ under the new probability $\tilde{P}^{t_{i+2}}$ . This expectation will not equal zero if the right-hand-side random variables are correlated. This correlation is nonzero as long as forward rates are correlated. To evaluate the mean of $\Delta W_{t+h}^{1}$ under the new probability $\tilde{P}^{t_{i+2}}$ , we then have to calculate the covariance.  

Let the covariance be given by $-\lambda_{t}h$ . We have,  

$$
\delta E_{t}^{\tilde{p}^{t_{i+2}}}[\Delta W_{t+h}^{1}F(t_{i},t_{i+1})]=-\lambda_{t}h
$$  

Using $\lambda_{t}.$ , we can switch probabilities in the $F(t,\ t_{i})$ dynamics. We start with the original Martingale dynamics:  

$$
F(t+h,t_{i})=F(t,t_{i})+\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{1}
$$  

Switch by adding and subtracting $\sigma^{i}F(t,t_{i})\lambda_{t}h$ to the right-hand side and regroup:  

$$
F(t+h,t_{i})=F(t,t_{i})-\sigma^{i}F(t,t_{i})\lambda_{t}h+\sigma^{i}F(t,t_{i})[\lambda_{t}h+\Delta W_{t+h}^{1}]
$$  

Let  

$$
\Delta W_{t+h}^{2}=[\lambda_{t}h+\Delta W_{t+h}^{1}]
$$  

We have just shown that the expectation of the right-hand side of this expression equals zero under $\tilde{P}^{t_{i+2}}$ . So, under the $\tilde{P}^{t_{i+2}}$ we can write the new dynamics of the $F(t,t_{i})$ as  

$$
F(t+h,t_{i})=F(t,t_{i})-\sigma^{i}F(t,t_{i})\lambda_{t}h+\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{2}
$$  

As can be seen from this expression, the new dynamics have a non-zero drift and $F(t,\ t_{i})$ is not a Martingale under the new measure. Yet, this process is arbitrage free and easy to exploit in Monte Carlo type approaches. Since both dynamics are expressed under the same measure, the set of equations that describe the dynamics of the two forward rates can be used in pricing instruments that depend on these forward rates. The same pseudo-random numbers can be used in the two SDEs. Finally, the reader should remember that the discussion in this section depends on the discrete approximation of the SDEs.  

# 14.5.2 GENERALIZATION  

A generalization of the previous heuristic discussion leads to the Forward LIBOR Model. Suppose the setting involves $n$ forward rates, $F(t_{0},t_{i}),i=0,...,n-1$ , that apply to loans which begin at time $t_{i\cdot}$ , and end at $t_{i+1}=t_{i}+\delta$ . The $F(t_{0},t_{0})$ is the trivial forward rate and is the spot LIBOR with tenor $\delta$ . The terminal date is $t_{n}$ .  

Similar to the discussion in the previous section, assume that there is a single factor.26 Using the $t_{i+1}$ forward measure we obtain arbitrage-free Martingale dynamics for each forward rate $F(t,t_{i})$ :  

$$
\mathrm{d}F(t,t_{i})=\sigma^{i}F(t,t_{i})W_{t}^{i+1}\quad t\in[0,\infty)
$$  

The superscript in $W_{t}^{i+1}$ implies that27  

$$
E_{t}^{\tilde{P}^{t+1}}[d W_{t}^{i+1}]=0
$$  

These arbitrage-free dynamics are very useful since they do not involve any interest rate modeling and are dependent only on the correct specification of the respective volatilities. However, when  

more than one forward rate determines a security’s payoff in a nonlinear fashion, the process may have to be written under a unique working measure.  

Suppose we chose $\tilde{P}^{t_{n}}$ as the working measure.28 The heuristic approach discussed in the previous section can be generalized to obtain the following arbitrage-free system of SDEs that involve recursive drift corrections in a one-factor case:  

$$
\mathrm{d}F(t,t_{i})=\mathbf{\Omega}-\left[\sigma^{i}F(t,t_{i})\sum_{j=i}^{n-1}\frac{\delta\sigma^{j}F(t,t_{j})}{1+F(t,t_{j})\delta}\right]\mathrm{d}t+\sigma^{i}F\big[(t,t_{i})\mathrm{d}W_{t}^{t_{n}}\quad t\in[0,\infty)\
$$  

where superscript in $\mathrm{d}W_{t}^{t_{n}}$ indicates that the working measure is $\tilde{P}^{t_{n}}$ . The equations in this system are expressed under this forward measure for $i=1$ , . . ., $n$ . Yet, only the last equation has Martingale dynamics  

$$
\mathrm{d}F(t,t_{n-1})=\sigma^{n-1}F(t,t_{n-1})\mathrm{d}W_{t}^{t_{n}}\quad t\in[0,\infty)
$$  

All other SDEs involve successive correction factors given by the first term on the right side. It is important to realize that all terms in these factors can be observed at time $t.$ The dynamics do not need a modeling of actual drifts.  

# 14.6 AN APPLICATION  

The forward measure and measure change technology are relevant for the pricing of many instruments. But there is one instrument class that has recently become quite popular with market participants and that can be priced with this technology. These are CMSs. They have properties that would illustrate some subtleties of the methods used thus far. In order to price them, forward rates need to be projected jointly.  

First, we present a reading that illustrates some of the recent interest in this instrument class.  

# EXAMPLE  

European institutional investors mindful of rising interest rates have been turning to constant maturity swap products to hedge their long-dated liabilities over the past few months. Whereas mainstream interest rate swaps tend to reference LIBOR, CMS pay-out structures are linked to the 10-year swap rate instead—a useful hedge for investors with long-dated liabilities such as insurance companies.  

As the 10-year euro swap cratered from a peak of $3.77\%$ in April 2011 to a low of $I.44\%$ in early May this year, these firms piled into CMS structures to shield themselves against falling interest rates. The spectre of the US Federal Reserve scaling back its asset purchases was enough to put paid to this trend. By the end of June, the 10-year swap rate had rocketed to above $2\%$ and CMS products are now gaining traction as a hedge against further rises.  

“Buying of CMS caps has picked up in the first half of the year because of the change of sentiment in the market, which has put rising rates to the forefront of investors’ minds,” said Ivan Jossang, head of EMEA rates structuring at Morgan Stanley.  

Caps have traditionally been popular with investors due to the relative simplicity of the structure. Take the example of an investor buying a cap with a $3\%$ strike. If rates rise to $4\%$ by the time the cap expires, the investor will be paid 100 bp on the notional it originally agreed. “CMS is the main light exotic product that  

survived the crisis, and is the most important building block for pay-offs in rates,” said Adrian Bracher,   
European head of rates structuring at Credit Suisse. As with many exotic products, CMS flourished in the run-up to the financial crisis and the market has   
since shrunk. There is no longer any CMS market to speak of in Swiss francs and sterling, with dollars and   
euros remaining the most liquid currencies. [. . .] French insurance companies are without doubt the most prolific CMS users, and not just because of the   
proximity of the euro swaps curve to sovereign yields, against which many of their liabilities are   
benchmarked. They also offer savings products to policyholders comparable to bank deposits, which need   
hedging if rates go up or down. [. . .] Bank hedging of CMS trades has seriously impacted on the swaptions market, making the 10-year euro   
swaption trade at a premium to options on the longer end of the curve. This has led some of the more   
dynamic Dutch and Danish pension funds—which use swaptions to hedge their liabilities—to move into the   
comparatively cheaper 20-year and 30-year contracts, according to Jossang. CMS has also come into play on the asset side of the balance sheet. As 10-year swap rates are higher   
that 3-month Euribor, CMS can act as a useful yield enhancement tool, often overlaid on government bonds   
or even private placements from corporates if their treasurers can be persuaded to come on board. (Thomson Reuters IFR Issue 1996, CMS makes comeback to hedge rate rises by Christopher Whittall, August 14, 2013)  

CMSs are instruments that build on the plain vanilla swaps in an interesting way. In a vanilla swap, a fixed swap rate is exchanged against a floating LIBOR that is an interest rate relevant for that particular settlement period only. In a CMS, this will be generalized. The fixed leg is exchanged against a floating leg, but the floating leg is not a “one-period” rate. It is itself a multiperiod swap rate that will be determined in the future.  

There are many versions of such exchanges, but as an example we consider the following. Suppose one party decides to pay $4\%$ during the next 3 years against receiving a 2-year swap rate that will be determined at the beginning of each one of those years. The future swap rates are unknown at time $t_{0}$ and can be considered as floating payments, except they are not floating payments that depend on the perceived volatility for that particular year only. They are themselves averages of 1-year rates. Clearly, such swaps have significant nonlinearities and we cannot do the same engineering as in the case of a plain vanilla swap.  

An example of CMS is shown in Figure 14.5. The reader can see that what is being exchanged at each settlement date against a fixed payment is a floating rate that is a function of more than one forward rate. Under these conditions it is impossible to project individual forward rates using individual zero-drift stochastic differential equations defined under different forward measures. Each leg of the CMS depends on more than one forward rate and these need to be projected jointly, under a single measure.  

# 14.6.1 ANOTHER EXAMPLE OF MEASURE CHANGE  

This section provides another example to measure change technology from the FRA markets. Paidin-arrears FRAs make time $t_{i+1}$ payoffs:  

$$
N\delta[F(t_{0},t_{i})-L_{t_{i}}]
$$  

![](dd83c9ea6e0f4d30e9028313688f959cef9b10d6ef4c83f28f2cbf8752109d42.jpg)  

# FIGURE 14.5  

Example of a CMS.  

The market-traded FRAs, on the other hand, settle at time $t_{i}$ according to:  

$$
\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}
$$  

Finally, we have LIBOR-in-arrears FRAs that settle according to  

$$
N\delta[F(t_{0},t_{i})-L_{t_{i}}]
$$  

at time $t_{i}$ . As we saw in Chapter 10, the LIBOR-in-arrears FRA payoffs settle in a “nonnatural” way, since $L_{t_{i}}$ -related payments would normally be received or paid at time $t_{i+1}$ .  

We now show that the paid-in-arrears FRA and market-traded FRAs lead to the same forward rate. First, remember that under the $\tilde{P}^{t_{i+1}}$ forward measure for paid-in-arrears FRAs, we have:  

$$
F(t_{0},t_{i})=E_{t_{0}}^{\tilde{P}^{t_{i+1}}}[L_{t_{i}}]
$$  

That is to say, the FRA rate $F\left(t_{0},t_{i}\right)$ is the average of possible values the LIBOR rate might take:  

$$
F(t_{0},t_{i})=\sum_{j=1}^{k}L_{t_{i}}^{j}\tilde{p}_{j}^{t_{i+1}}
$$  

where $j$ represents possible states of the world, which are assumed to be discrete and countable. Now, consider the settlement amount of market-traded FRAs:  

$$
\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}
$$  

Would the forward rate implied by this contract be the same as the paid-in-arrears FRAs?  

The answer is yes. Using the measure change technology, we discuss how this can be shown. The idea is to begin with the expectation of this settlement amount under the $\tilde{P}^{t_{i}}$ measure and show that it leads to the same forward rate. Thus, begin with  

$$
E_{t_{0}}^{\tilde{P}^{t_{i}}}\left[\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}\right]
$$  

Setting this equal to zero, and rearranging, leads to the pricing equation  

$$
F(t_{0},t_{i})=\frac{E_{t_{0}}^{\tilde{P}^{t_{i}}}[N\delta L_{t_{i}}/(1+\delta L_{t_{i}})]}{E_{t_{0}}^{\tilde{P}^{t_{i}}}[N\delta/(1+\delta L_{t_{i}})]}
$$  

Now we switch measures on the right-hand side of Eq. (14.142). We have two expectations and we will switch measures in both of them. But first, let $N=1$ and, similarly, $\delta=1$ .  

Consider the numerator:  

$$
E_{t_{0}}^{\tilde{P}_{i}^{t_{i}}}\left[\frac{L_{t_{i}}}{(1+L_{t_{i}})}\right]=\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\tilde{p}_{j}^{t_{i}}
$$  

We know that for time $t_{i}$  

$$
\tilde{p}_{j}^{t_{i}}=\frac{1}{B(t_{0},t_{i})}Q^{j}
$$  

$$
\tilde{p}_{j}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{j}}{B(t_{0},t_{i+1})}Q^{j}
$$  

Thus:  

$$
\tilde{p}_{j}^{t_{i}}=\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

Replacing the right-hand side in Eq. (14.143), we get  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

In this expression, we recognize  

$$
\frac{B(t_{0},t_{i+1})}{B(t_{0},t_{i})}=\frac{1}{1+F(t_{0},t_{i})}
$$  

and  

$$
\frac{1}{B(t_{i},t_{i+1})^{j}}=1+L_{t_{i}}^{j}
$$  

Using these we get the equivalence:  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}=\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{\left(1+F(t_{0},t_{i})\right)}\left(1+L_{t_{i}}^{j}\right)\tilde{p}_{j}^{t_{i+1}}
$$  

Simplifying the common terms on the right-hand side reduces to  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{1+F(t_{0},t_{i})}\tilde{p}_{j}^{t_{i+1}}
$$  

This we immediately recognize as the expectation:  

$$
E_{t_{0}}^{\tilde{P}_{t+1}^{t_{i+1}}}\left[\frac{L_{t_{i}}^{j}}{1+F(t_{0},t_{i})}\right]
$$  

Now, consider the denominator in Eq. (14.142)  

$$
E_{t_{0}}^{\tilde{P}_{t}^{t_{i}}}\left[\frac{1}{(1+L_{t_{i}})}\right]=\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\tilde{p}_{j}^{t_{i}}
$$  

Using Eq. (14.144), we switch to the $\tilde{P}^{t_{i+1}}$ measure:  

$$
\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\tilde{p}_{j}^{t_{i}}=\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

Use the equivalences in Eq. (14.144), substitute:  

$$
\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}=\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{\left(1+F(t_{0},t_{i})\right)}\left(1+L_{t_{i}}^{j}\right)\tilde{p}_{j}^{t_{i+1}}
$$  

Note that, again, the random $(1+L_{t_{i}}^{j})$ terms conveniently cancel, and on the right-hand side we obtain:  

$$
\begin{array}{l}{\displaystyle=\sum_{j=1}^{k}\frac{1}{1+F(t_{0},t_{i})}\tilde{p}_{j}^{t_{i+1}}}\\ {\displaystyle=\frac{1}{(1+F(t_{0},t_{i}))}}\end{array}
$$  

Putting the numerator and denominator together for general $N$ and $\delta$ gives  

$$
F(t_{0},t_{i})=\frac{E_{t_{0}}^{\tilde{p}^{t_{i}}}\left[N\delta L_{t_{i}}/\left(1+\delta L_{t_{i}}\right)\right]}{E_{t_{0}}^{\tilde{p}^{t_{i}}}\left[N\delta/\left(1+\delta L_{t_{i}}\right)\right]}=\frac{E_{t_{0}}^{\tilde{p}^{t_{i+1}}}\left[N\delta\left(N_{t_{i}}^{j}/(1+F(t_{0},t_{i})\delta)\right)\right]}{(N\delta/(1+F(t_{0},t_{i})\delta))}
$$  

We simplify the common terms to get  

$$
F(t_{0},t_{i})=E_{t_{0}}^{\tilde{P}^{t_{i+1}}}\left[L_{t_{i}}^{j}\right]
$$  

Hence, we obtained the desired result. The FRA rate of paid-in-arrears FRAs is identical to the FRA rate of market-traded FRAs and is an unbiased predictor of the LIBOR rate $L_{t_{i}}$ , under the right forward measure.  

We conclude this section with another simple example.  

# EXAMPLE  

We can apply the forward measure technology to mark-to-market practices as well. The paid-in-arrears FRA will settle at time $t_{i+1}$ according to  

$$
\big[L_{t_{i}}-F(t_{0},t_{i})\big]N\delta
$$  

What is the value of this contract at time $t_{1}$ , with $t_{0}<t_{1}<t_{i}^{\:c}$  

It is market convention to replace the random variable $L_{t_{i}}$ with the corresponding forward rate of time $t_{1}$ . We get  

$$
[F(t_{1},t_{i})-F(t_{0},t_{i})]N\delta
$$  

which, in general, will be nonzero. How do we know that this is the correct way to mark the contract to market? We simply take the time $t_{1}$ expectation of:  

$$
\big[L_{t_{i}}-F(t_{0},t_{i})\big]N\delta
$$  

with respect to the natural forward measure of $t_{i+1}$  

$$
E_{t_{1}}^{\tilde{P}_{t_{1}}^{t_{i+1}}}\left[L_{t_{i}}-F(t_{0},t_{i})\right]N\delta=[F(t_{1},t_{i})-F(t_{0},t_{i})]N\delta
$$  

where we use the fact that under the $\tilde{P}^{t_{i+1}}$ , the $F(t_{1},t_{i})$ is an unbiased estimate of $L_{t_{i}}$ .  

# 14.6.2 PRICING CMS  

Pricing CMS is known to involve convexity adjustments. Staying within the context of the simple framework used in this chapter, the industry first obtains the $t_{1}\times t_{2}$ and $t_{2}\times t_{3}$ swaption volatilities. Then, knowing that the swap is a Martingale under the “annuity” measure treated in Chapter 17, various transformations under specific assumptions are performed and then the convexity correction to the forward swap rate is estimated. In other words, the industry calculates the $\in{\mathfrak{_{t}}}$ in the equation  

$$
{\mathrm{cms}}_{t}=s_{t}^{f}+\in{}_{t}
$$  

where $c m s_{t}$ is the CMS rate, $s_{t}^{f}$ is the relevant forward swap rate, and $\in{\mathfrak{\Gamma}}_{t}$ is the convexity correction.  

It is straightforward to price CMS using the forward LIBOR dynamics discussed earlier and then use successive measure changes for the required mean corrections. Because CMS offer a good example for such an application, we show a simple case.  

Consider a two-period forward CMS where a fixed CMS rate $x_{t_{0}}$ is paid at times $t_{2}$ and $t_{3}$ against the floating two-period cash swap rate at these times. The present value of the cash flows under the $\tilde{P}^{t_{3}}$ forward probability is given by  

$$
\begin{array}{c}{{0=E_{t_{0}}^{\tilde{p}_{0}^{t_{3}}}\Bigg[\left(x_{t_{0}}-s_{t_{1}}\right)\displaystyle\frac{1}{\left(1+L_{t_{0}}\delta\right)\left(1+L_{t_{1}}\delta\right)}+\left(x_{t_{0}}-s_{t_{2}}\right)}}\\ {{\displaystyle\frac{1}{\left(1+L_{t_{0}}\delta\right)\left(1+L_{t_{1}}\delta\right)\left(1+L_{t_{2}}\delta\right)}\Bigg]N}}\end{array}
$$  

where the settlement interval is assumed to be one and $N$ is the notional swap amount. The $s_{t_{1}}$ and $s_{t_{2}}$ are the two 2-period swap rates unknown at time $t_{0}$ . They are given by the usual spot swap formula shown in Eq. (14.49).  

Setting $\delta=1$ , and rearranging this equation, we obtain  

$$
x_{t_{0}}=\frac{E_{t_{0}}^{\tilde{p}^{i_{3}}}\left[s_{t_{1}}\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\right)+s_{t_{2}}\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right)\right]}{E_{t_{0}}^{\tilde{p}^{i_{3}}}\left[\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\right)+\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right)\right]}
$$  

Hence, to find the value of the CMS rate $x_{t_{0}}$ , all we need to do is write down the dynamics of the forward LIBOR processes, $\textit{F}(t_{0},t_{1})$ and $F\left(t_{0},t_{2}\right)$ , under the same forward measure $\mathbf{\bar{\boldsymbol{P}}}^{t_{3}}$ as done earlier, and then select Monte Carlo paths.  

It is clear that proceeding in this way and obtaining Monte Carlo paths from the arbitrage-free forward LIBOR dynamics requires calibrating the respective volatilities $\sigma^{i}$ . But once this is done, and once the correction factors are included in the proper equations, the Monte Carlo paths can be selected in a straightforward manner. The CMS rate can then be calculated from  

$$
x_{t_{0}}=\frac{\sum_{j=1}^{M}\left[s_{t_{1}}^{j}\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\right)+s_{t_{2}}^{j}\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\left(1+L_{t_{2}}^{j}\right)\right)\right]}{\sum_{j=1}^{M}\left[\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\right)+\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\left(1+L_{t_{2}}^{j}\right)\right)\right]}
$$  

where the swap rates $s_{t_{i}}^{j}$ themselves depend on the same forward rate trajectories and, hence, can be calculated from the selected paths.  

The same exercise can be repeated by starting from perturbed values of volatilities and initia forward rates to obtain the relevant Greeks for risk-management purposes as well.  

# 14.7 IN-ARREARS SWAPS AND CONVEXITY  

Although an overwhelming proportion of swap transactions involve the vanilla swap, in some cases parties transact the so-called LIBOR-in-arrears swap. In this section, we study this instrument because it is a good example of how Forward LIBOR volatilities enter pricing directly through convexity adjustments.  

But first we need to clarify the terminology. In a vanilla swap, the LIBOR rates $L_{t_{i}}$ are assumed to “set” at time $t_{i}$ whereas the floating payments are made in arrears at times $t_{i+1}$ .29 In the case of an  

1. Interest rate swap  

Receive floating $L_{t_{j-1}}\delta N$  

![](705c529222407f2433febfbc1d0dfa2a36ba61a10019327fb469c0958d986fe9.jpg)  

2. LIBOR-in-arrears swap  

![](2c713c13d60ebbc7788e72808818ca842c8b572c43af990aebcd7092fdd25506.jpg)  

# FIGURE 14.6  

Interest rate swap versus LIBOR-in-arrears swap.  

in-arrears swap, the payment days are kept the same, but the time $t_{i+1}$ settlement will use the LIBOR rate $L_{t_{i+1}}$ that has just been observed at time ${t_{i+1}}^{30}$ to determine the floating payment. Thus, in a sense the setting of the LIBOR rate is in arrears, hence the name of the in-arrears swap.31 The difference between LIBOR resets is illustrated in and the difference between vanilla interest rate swaps and LIBOR-in-arrears swaps is shown in Figure 14.6. LIBOR-in-arrears swaps set the LIBOR rates in arrears.  

The simple modification of paying the $L_{t_{i+1}}$ observed at time $t_{i+1}$ rather than the previously observed $L_{t_{i}}$ makes a significant difference in pricing. We will work with a simple case of a twoperiod (forward) swap first, and then give the generalized formulas.  

# 14.7.1 VALUATION  

The valuation of the fixed leg of the in-arrears swap is the same as that of the vanilla swap, except of course the swap coupons are different. Let the $s_{t_{0}}$ be the vanilla swap rate fixed at time $t_{0},N$ and $\delta$ be the notional amount and accrual parameters, respectively. Then the fixed leg payments are easy to value:  

$$
\begin{array}{r}{\mathrm{Fixed-Leg}_{t_{0}}=B(t_{0},t_{2})s_{t_{0}}\delta N+B(t_{0,t_{3}})s_{t_{0}}\delta N}\\ {=[B(t_{0},t_{2})+B(t_{0},t_{3})]s_{t_{0}}\delta N\quad}\end{array}
$$  

It is clear that in case of the in-arrears swap, we will have a similar expression:  

$$
\mathrm{Fixed-Leg}_{t_{0}}=[B(t_{0},t_{2})+B(t_{0},t_{3})]i s_{t_{0}}\delta N
$$  

where the $i s_{t_{0}}$ is the swap rate of the in-arrears swap.  

The difference in valuations emerge in the floating leg. Note that in the case of the in-arrears swap, the expected value under the $P^{t_{2}}$ forward measure of the floating rate payments would be  

$$
\mathrm{Floating-Leg}_{t_{0}}=E_{t_{0}}^{P^{t_{2}}}[B(t_{0},t_{2})L_{t_{2}}]\delta N+E_{t_{0}}^{P^{t_{2}}}[B(t_{0},t_{3}]\delta N
$$  

Multiply and divide by $(1+L_{t_{2}}\delta)$ and $(1+L_{t_{3}}\delta)$ , respectively, we obtain  

$$
\mathrm{Floating-Leg}=E_{t_{0}}^{P^{2}}\left[B(t_{0},t_{2})L_{t_{2}}\frac{\left(1+L_{t_{2}}\delta\right)}{\left(1+L_{t_{2}}\delta\right)}\right]\delta N+E_{t_{0}}^{P^{2}}\left[B(t_{0},t_{3})L_{t_{3}}\frac{\left(1+L_{t_{3}}\delta\right)}{\left(1+L_{t_{3}}\delta\right)}\right]\delta N
$$  

But in the case of finite-state random quantities, we have the usual correspondence between the $t_{3}$ and $t_{2}$ forward measures:  

$$
p_{i}^{t_{2}}\frac{B(t_{2},t_{3})^{i}}{B(t_{0},t_{3})}B(t_{0},t_{2})=p_{i}^{t_{3}}
$$  

Also, by definition  

$$
B(t_{2},t_{3})^{i}=\frac{1}{\bigg(1+L_{t_{2}}^{i}\delta\bigg)}
$$  

This means that after regrouping, changing measures from $P^{t_{2}}$ to $P^{t_{3}}$ :  

$$
E_{t_{0}}^{P^{t_{2}}}\left[B(t_{0},t_{2})L_{t_{2}}\frac{\left(1+L_{t_{2}}\delta\right)}{\left(1+L_{t_{2}}\delta\right)}\right]\delta N=E_{t_{0}}^{P^{t_{3}}}\left[B(t_{0},t_{3})L_{t_{2}}\left(1+L_{t_{2}}\delta\right)\right]\delta N
$$  

Changing the measure from $P^{t_{3}}$ to $P^{t_{4}}$ , a similar set of equations gives  

$$
{E}_{t_{0}}^{P^{t_{3}}}\left[B(t_{0},t_{3})L_{t_{3}}\frac{\left(1+L_{t_{3}}\delta\right)}{\left(1+L_{t_{3}}\delta\right)}\right]={E}_{t_{0}}^{P^{t_{4}}}\left[B(t_{0},t_{4})L_{t_{3}}\left(1+L_{t_{3}}\delta\right)\right]
$$  

Thus the valuation of the floating leg becomes  

$$
\mathrm{Floating-Leg}_{t_{0}}=\left[E_{t_{0}}^{P_{3}}\left[B(t_{0},t_{3})L_{t_{2}}\left(1+L_{t_{2}}\delta\right)\right]+E_{t_{0}}^{P_{4}}\left[B(t_{0},t_{4})L_{t_{3}}\left(1+L_{t_{3}}\delta\right)\right]\right]\delta N
$$  

The right-hand side can be expanded to  

$$
\begin{array}{r l}&{\mathrm{Floating-Leg}_{t_{0}}=B(t_{0},t_{3})\Big[E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}\right]+E_{t_{0}}^{P^{t_{3}}}\left[\left(L_{t_{2}}\delta\right)^{2}\right]\Big]\delta N+B(t_{0},t_{4})\Big[E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}\right]}\\ &{\quad\quad\quad\quad+E_{t_{0}}^{P^{t_{4}}}\left[\left(L_{t_{3}}\delta\right)^{2}\right]\Big]\delta N}\end{array}
$$  

But the forward rates are Martingales with respect to their own measures. So,  

$$
\begin{array}{r}{F_{t_{0}}^{t_{2}}=E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}\right]}\\ {F_{t_{0}}^{t_{3}}=E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}\right]}\end{array}
$$  

and  

$$
\begin{array}{r l}&{E_{t_{0}}^{P^{t_{3}}}\left[L_{t_{2}}^{2}\right]=\left(F_{t_{0}}^{t_{2}}\right)^{2}e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}}\\ &{E_{t_{0}}^{P^{t_{4}}}\left[L_{t_{3}}^{2}\right]=\left(F_{t_{0}}^{t_{3}}\right)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}}\end{array}
$$  

So we get the final result as:  

$$
\begin{array}{r l}&{\mathrm{Floating–Leg}_{t_{0}}=B(t_{0},t_{3})\Bigg[F_{t_{0}}^{P^{t_{2}}}+\delta\Big(F_{t_{0}}^{t_{2}}\Big)^{2}e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}\Bigg]}\\ &{\qquad+B(t_{0},t_{4})\Bigg[F_{t_{0}}^{t_{3}}+\delta\Big(F_{t_{0}}^{t_{3}}\Big)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{3}}^{2}\mathrm{d}u}\Bigg]\delta N}\end{array}
$$  

This can be expressed as the floating leg of a vanilla swap plus an adjustment called the convexity adjustment:  

$$
\begin{array}{r l}&{\mathrm{Floating\mathrm{-}L e g}_{t_{0}}=\Big[B(t_{0},t_{3})F_{t_{0}}^{t_{2}}+B(t_{0},t_{4})F_{t_{0}}^{t_{3}}\Big]\delta N+\Bigg[B(t_{0},t_{3})\delta\big(F_{t_{0}}^{t_{2}}\big)e^{\int_{t_{0}}^{t_{2}}\sigma(u)_{t_{2}}^{2}\mathrm{d}u}}\\ &{\quad\quad\quad\quad+B(t_{0},t_{4})\delta\Big(F_{t_{0}}^{t_{3}}\Big)^{2}e^{\int_{t_{0}}^{t_{3}}\sigma(u)_{t_{3}}^{2}\mathrm{d}u}\Bigg]\delta N}\end{array}
$$  

For small settlement intervals, $\Delta$ and constant volatilities the approximation becomes  

$$
\Big[B(t_{0},t_{3})\delta\big(F_{t_{0}}^{t_{2}}\big)^{2}e^{\Delta\sigma_{t_{2}}^{2}}+B(t_{0},t_{4})\delta\big(F_{t_{0}}^{t_{3}}\big)^{2}e^{\Delta\sigma_{t_{3}}^{2}}\Big]\delta N
$$  

Note that the second bracketed term in the convexity adjustment is positive. This makes the value of the floating rate payments in the in-arrears swap be greater than the value of the floating payments in the vanilla swap. The consequence of this is that the in-arrears fixed swap rate denoted by $\tilde{s}_{t}$ is bigger than the vanilla fixed rate  

$$
s_{t_{0}}<\tilde{s}_{t_{0}}
$$  

A number of comments can be made. First note that the volatilities can be obtained from the corresponding caplet volatilities. Second, note that the value of the in-arrears swap does not depend on the correlation between various forward rates. Third, the volatilities are likely to be different than the swaption volatilities.  

# 14.7.2 SPECIAL CASE  

A special case of this is if we look at a single period in-arrears swap. Then we get a relation between forward rates and futures rates.  

A Eurodollar contract leads to an exchange of $f_{t_{0}}$ for $L_{t_{i}}$ at time $t_{i}$ . The forward contract leads to an exchange of $\boldsymbol{F}_{t_{0}}$ for $L_{t_{i-1}}$ at $t_{i}$ . So this is the one-period replica of the comparison we just made.  

This means  

$$
f_{t_{0}}^{t-i}-F_{t_{0}}^{t-i}=\delta\big(F_{t_{0}}\big)^{2}e^{\int_{t_{0}}^{t_{i}}\sigma(u)_{t_{i}}^{2}\mathrm{d}u}
$$  

Directly from Eq. (14.177) of the previous section. The right-hand side is known as the convexity adjustment that needs to be applied when going from futures to forward rates. Note that the futures price of the contract will then be smaller than the forward price.32  

# 14.8 CROSS-CURRENCY SWAPS  

A cross-currency swap can serve different purposes. It can be used for hedging, that is to reduce the exposure to exchange rate changes. Alternatively, one can use it to exploit arbitrage opportunities between different rates.  

The following reading illustrates some of the recent issues related to cross-currency swaps.  

# EXAMPLE  

It has been a rollercoaster couple of years for the Australian cross-currency basis swap [. . .], which has ripsawed to unprecedented levels primarily as a result of large irregular capital dislocations during the global financial crisis. On October 10, 2008, a shortage of US dollars, coupled with major rehedging of Japanese power reverse dual currency (PRDC) notes, caused the five-year AUD/USD cross-currency basis swap to drop to $-50$ basis points—quite a move for a swap that has traditionally traded in a fairly predictable range of around six to 10 bp. Its 10-year equivalent suffered an equally volatile fate, hitting $-47$ bp on the same date. By September 2009, this situation had completely reversed. Kangaroo bond issuance had all but ground to a halt, while Australian banks—buoyed by AA credit ratings and government guarantees—were able to comfortably tap offshore markets to shore up their balance sheets. [. . .]  

These extreme levels of volatility have attracted the attention of a number of hedge funds. “The hedge fund community has been active in the basis swap market for some time. By nature, it is a function of opportunity,” says Anthony Robson, head of rates for Australian and New Zealand dollars at Barclays Capital in Sydney.  

Those opportunities, he says, have occurred regularly in the past two years. “In 2008 and early 2009, the yield curve was steeply negative, which reflected the sheer illiquidity at that time, severe global funding issues and bank hedging need to receive in the long-end around 30 years. For hedge funds looking for the basis swap to widen, that presented attractive opportunities to pay. For example, they could pay a five-year basis swap, starting in five years’ time and pick up 60 bp, benefiting from the negative-shaped curve and the very rapid change in levels,” he says, adding: “At the moment, and especially late last year, the basis swap is quite steeply positive, so there are certainly receivers of the forward basis spread.”  

Dealers say that since hitting its peak in late 2009, interest from hedge fund managers in the basis swap has noticeably picked up. Betting on the basis to trend back towards its historical average, they have put on a range of forward-starting basis swaps to extract value from the shape of the curve. “A fund manager could receive a five-year basis swap on a hold-to-maturity basis, yielding say, $+3I.5b p$ ,” says Ian Martin, head of global rates for Australia and New Zealand at Deutsche Bank in Sydney, who says hedge funds have been particularly involved in two- to five-year maturities. “By hedging the first year’s cash flows at $+5.5$ bp, the manager can create a forward-starting four-year swap at 39 bp. Assuming the swap tightens in line with its historical average, they would benefit from carry and capital appreciation as the trade rolls down the curve.”  

Since the fourth quarter of 2009, following a surge in kangaroo issuance, the three- to seven-year basis swap tenors have come back in substantially from their late 2009 peaks, with the five-year AUD/USD crosscurrency swap falling to $+32$ bp on February 17. Ten-year and longer tenors, however, have not fallen as  

sharply. That caused the inversion of the long-end of the basis to remain pronounced and has led Deutsche   
Bank to recommend a butterfly spread to take advantage of the inversion of the curve. “While the basis   
swap spread slope has returned to fairly normal long-run levels, the five-year/10-year/15-year butterfly is   
currently near the wides reached in February last year. We think this butterfly (receiving 10-year basis   
against paying the five-year and 15-year) is one of the better trade opportunities in basis swap spreads at   
present, and we recommend entering the trade,” the bank wrote in a research note dated February 17. (‘Betting on basis’ by Wietske Blees, Asia Risk, 19 April 2010. URL: http://www.risk.net/asia-risk/ feature/1600830/betting-basis).  

As an example of the use of a cross-currency swap for hedging, consider a European company that intends to buy US dollar bonds and would like to hedge the US dollar exchange rate risk. The European company could buy a cross-currency swap from a US-based bank. As a result of the swap, the European company would pay in euros and receive a (fixed) US dollar cash flow. These US dollar cash flows from the swap could be used to buy the US dollar bond. The valuation of a cross-currency swap is similar to that of an interest-rate swap but one difference relates to the exchange of notional. A cross-currency swap has two principal amounts, one for each currency. The initial principals can be exchanged or not. The nonexchange of the initial amounts is a minor issue. But eliminating the exchange of the final amounts changes the pricing structure significantly. The exchange rate used to determine the principals is the prevailing spot rate.  

With an interest rate swap, there is no exchange of principal at either the start or end of the transaction, as both principal amounts are the same and therefore net out. For a cross-currency swap, it is essential that the parties agree to exchange principal amounts at maturity. The exchange of principal at the start is optional.  

Like all swaps, a cross-currency swap can be replicated using on-balance sheet instruments, in this case with money market deposits or FRNs denominated in different currencies. This explains the necessity for principal exchanges at maturity as all loans and deposits also require repayment at maturity.33  

The initial exchange can be replicated by the bank by entering into a spot exchange transaction at the same rate quoted in the cross-currency swap. Actually, all foreign exchange forwards can be described as cross-currency swaps as they are agreements to exchange two streams of cash flows in different currencies. Many banks manage long-term foreign exchange forwards as part of the crosscurrency swap business, given the similarities.  

Like FX forwards, the cross-currency swap exposes the user to foreign exchange risk. The swap leg the party agrees to pay is a liability in one currency, and the swap leg they have agreed to receive is an asset in the other currency. One of the users of cross-currency swaps are debt issuers. In the Eurobond markets, issuers sell bonds in the currency with the lowest cost and swap their exposure to the desired currency using a cross-currency swap.  

# 14.8.1 PRICING  

At the inception of the swap, the present value of one leg must be equal to the present value of the other leg at the then-prevailing spot rate. Using this simple logic, it would seem natural that cash flows of LIBOR (flat) payments in one currency could be exchanged for cash flows of LIBOR (flat) payments in another currency.  

In reality this is not true, and there is a constant spread. By convention cross-currency swap spreads are quoted on the currency side against USD LIBOR: USD LIBOR versus Foreign Currency LIBOR plus a spread. The spread can be positive or negative. Before 2007 the EUR/USD crosscurrency swap spread was close to zero, but during the GFC it reached 120 bp. The reasons for the spread are twofold. First is the daily demand supply imbalances that are always possible. There may be more demand for paying a LIBOR in a particular currency and this will lead to a positive (basis) spread to be paid. Consider US companies, for example, that issue a loan in euros. The companies will exchange principal and coupons payments in EUR for principal and coupons payments in USD. If the cross-currency basis is negative, the companies will have to pay LIBOR but will receive Euribor minus the basis. Such corporate supply and hedging activity can be a potential driver crosscurrency swap basis. If the corporate issuance in EUR is high and most of it is swapped into USD, there could be a positive or spread to exchange EUR payments in USD payments. Such corporate activity, however, cannot explain the huge swings in the spread during the GFC.  

The second effect that leads to positive spreads is credit risk. Counterparties may not have the same credit risk and the currency swap spread may then reflect this. For example, if one party is paying the Philippine peso equivalent of the LIBOR rate against USD LIBOR, then this party is likely to have a higher credit risk. So the party will pay a higher spread. During the GFC, an excess demand of USD by non-US banks drove the EUR/USD cross-currency swap down dramatically in 2008. In 2011, US Money-Market funds withdrew funding to European banks which also led to a decline in the spread. These examples illustrate that the spread reflects the relative creditworthiness of banks across different countries.34  

# 14.8.2 CONVENTIONS  

The usual convention for quoting the currency swap spread, also called the basis, is to quote it relative to the USD LIBOR.  

# 14.9 DIFFERENTIAL (QUANTO) SWAPS  

Financial Accounting Standard (FAS) 133 and the International Accounting Standard (IAS) 39 set the accounting rules for derivatives for the United States and for European companies, respectively. According to these rules, a derivative position will have to be marked-to-market and included in income statements unless it qualifies for hedge accounting.35  

A quanto (differential) swap is a special type of cross-currency swap. It is an agreement where one party makes payments in, say, USD LIBOR and receives payments, say, in Euro LIBOR. However, the important point is that both parties make payments in the same currency. In other words, the quanto swap value is an exposure on pure play of international interest rate differentials and has no foreign exchange risk.  

Quanto swap popularity depends on the relative shapes of the forward curves in the two underlying money markets. Quanto swaps become “cheap” if one of the two forward curves is lower at the short end and higher at the long end.  

# 14.9.1 BASIS SWAPS  

This discussion is limited to US dollar markets. The particular interest rates discussed below will change if other currencies are considered, since basis swaps are directly related to the business environment in an economy. A basis swap is a floating floating interest rate swap in which cash flows based on one floating reference rate are exchanged against the cash flows based on a different floating reference rate.  

In a basis swap, one party will often pay USD LIBOR and will receive another money-market rate. Most bank liabilities are in fact LIBOR based, but assets are not. A corporation that deals mainly in the domestic US economy may be exposed to commercial paper (CP) rates; a bank may be exposed to T-bill rates, and another to the prime rate. Basis swaps could then be used to protect the party with respect to changes in these different money market rates.  

The most common types of basis swaps are Fed Funds against LIBOR,36 T-bill rates against LIBOR, CP rates against LIBOR, and the prime rate against LIBOR.37 Which basis swap a client picks depends on his or her business. For example, a party that has concerns about credit squeezes can use Fed Funds-LIBOR basis swaps or the T-bill-LIBOR basis swaps. During a credit squeeze, a flight to safety will make the basis swap spread increase. On the other hand, the Prime-LIBOR basis swap can hedge the exposures of those players involved in credit card, auto, or consumer loans.  

# 14.10 CONCLUSIONS  

This chapter was devoted to the connections between the swap, FRA, and bond markets. Our discussion led us to the issue of constructing a satisfactory yield curve, which is the fundamental task of a financial engineer. Two main tools were introduced in the chapter. The first was the $T.$ -forward measures and the second was the related measure change technology. This permitted setting up convenient arbitrage-free dynamics for a sequence of forward rates. These dynamics were then used as a tool for calculating the desired quantities using the formulas that connect swap rates, forward rates, and their derivatives.  

The next topic was the Forward LIBOR Model. Here, the essential idea was to obtain sequential correction factors to express the dynamics of various forward rates under a single forward measure.  

# SUGGESTED READING  

The standard readings for this chapter will make interesting reading for a financial engineer. Brace et al. (1997) and Jamshidian (1997) are the fundamental readings. Miltersen et al. (1997) is another important reference. Glasserman and Zhao (2000) is a good source on the discretization of BGM models. Finally, the text by Brigo and Mercurio (2006) provides a comprehensive treatment of all this material. Rebonato (2002) is a good introduction.  

# EXERCISES  

1. You are given the following quotes for liquid FRAs paid in arrears. Assume that all time intervals are measured in months of 30 days.  

<html><body><table><tr><td>Term Bid/Ask</td></tr><tr><td>3X6 4.5-4.6</td></tr><tr><td>6X9 4.7-4.8</td></tr><tr><td>9×12 5.0-5.1</td></tr><tr><td>12X15 5.5-5.7</td></tr><tr><td>15 X18 6.1-6.3</td></tr></table></body></html>  

You also know that the current 3-month LIBOR rate is $4\%$ . a. Calculate the discount bond prices $B(t_{0},t_{i})$ , where $t_{i}=6$ , 9, 12, 15, and 18 months. b. Calculate the yield curve for maturities 0 18 months. c. Calculate the swap curve for the same maturities. d. Are the two curves different? e. Calculate the par yield curve. f. Calculate the zero-coupon yield curve.  

2. You are given the following quotes for liquid swap rates. Assume that all time intervals are measured in years.  

<html><body><table><tr><td>Term Bid/Ask</td></tr><tr><td>２ 6.2-6.5</td></tr><tr><td>3 6.4-6.7</td></tr><tr><td>4 7.0-7.3</td></tr><tr><td>5 7.5-7.8</td></tr><tr><td>６ 8.1-8.4</td></tr></table></body></html>  

You know that the current 12-month LIBOR rate is $5\%$ .  

a. Calculate the FRA rates for the next 5 years, starting with a $1\times2$ FRA.   
b. Calculate the discount bond prices $B(t_{0},t_{i})$ , where $t_{i}=1,...,6$ years.   
c. Calculate the yield curve for maturities of 0 18 months.   
d. Calculate the par yield curve.  

3. Going back to the data given in Exercise 2, calculate the following:  

a. The bid ask on a forward swap that starts in 2 years with maturity in 3 years. The swap is against 12-month LIBOR.   
b. The forward price of a coupon bond that will be delivered at time 2. The bond pays coupon $7\%$ and matures in 2 years.  

# EXCEL EXERCISES  

4. Write a VBA program to determine the bond price and swap rates from the set of forward rates given below and plot the yield curves along with the swap curve. Comment on their characteristics.  

<html><body><table><tr><td>Term (Month)</td><td>Forward Rate</td></tr><tr><td>0</td><td>4.00%</td></tr><tr><td>3</td><td>4.50%</td></tr><tr><td>6</td><td>4.70%</td></tr><tr><td>9</td><td>5.00%</td></tr><tr><td>12</td><td>5.50%</td></tr><tr><td>15</td><td>6.10%</td></tr><tr><td>18</td><td>6.40%</td></tr><tr><td>21</td><td>6.46%</td></tr><tr><td>24</td><td>7.00%</td></tr></table></body></html>  

5. Write a VBA program to determine the bond price and forward rates from the set of swap rates below with the term of 1 year as the input. Assume that the current LIBOR rate is $5.00\%$ . Plot the yield curves along with swap curve to observe their characteristic.  

<html><body><table><tr><td>Term (Years)</td><td>Swap Rate</td></tr><tr><td>2</td><td>6.20%</td></tr><tr><td>3</td><td>6.40%</td></tr><tr><td>4</td><td>7.00%</td></tr><tr><td>5</td><td>7.50%</td></tr><tr><td>6</td><td>8.10%</td></tr><tr><td>7</td><td>8.70%</td></tr></table></body></html>  

6. Write a VBA program to determine the FRA rates and swap rates from the set of bond prices below as the input and plot the yield curves along with swap curve. Comment on their characteristics.  

<html><body><table><tr><td>Time (Month)</td><td>Bond Price</td></tr><tr><td>0</td><td>100.00</td></tr><tr><td>3</td><td>99.01</td></tr><tr><td>6</td><td>97.91</td></tr><tr><td>9</td><td>96.77</td></tr><tr><td>12</td><td>95.58</td></tr><tr><td>15</td><td>94.28</td></tr><tr><td>18</td><td>92.86</td></tr><tr><td>21</td><td>91.40</td></tr><tr><td>24</td><td>89.95</td></tr><tr><td>27</td><td>88.40</td></tr></table></body></html>  

7. Write a VBA program to determine the price of an interest rate swap which makes a floating payment every 6 months at the rate equal to USD LIBOR rate against a fixed rate of $5.10\%$ for the notional amount of $\$10,000$ . Use the data given in the “Input” worksheet for carrying out the calculation.  

<html><body><table><tr><td>Time (Years)</td><td>Forward Rate</td></tr><tr><td>0.00</td><td>5.70%</td></tr><tr><td>0.50</td><td>5.18%</td></tr><tr><td>1.00</td><td>5.83%</td></tr><tr><td>1.50</td><td>5.10%</td></tr><tr><td>2.00</td><td>5.75%</td></tr><tr><td>2.50</td><td>5.74%</td></tr><tr><td>3.00</td><td>5.28%</td></tr><tr><td>3.50</td><td>5.65%</td></tr><tr><td>4.00</td><td>5.53%</td></tr></table></body></html>  

8. (Cross-Currency Swap) Write a VBA program to determine the cross-currency swap rate based on the information below. The fixed payment is made in USD in the exchange for the floating payment (in USD) rate equal to the GBP LIBOR at every 3 months. Also include the exchange of notional amount d10,000 against payment in dollars at their corresponding exchange spot rate during initiation and maturity of the swap in the swap rate calculation.  

Notional amount $(\mathbf{GBP})=\pounds10,000$ , notional amount $(\mathrm{USD})=\$20,000$  

<html><body><table><tr><td>Time (Month)</td><td>Forward Rate (USD)</td><td>Exchange Rate (USD/GBP)</td><td>LIBOR Rate (GBP)</td></tr><tr><td>0</td><td>4.00%</td><td>2.0000</td><td>5.70%</td></tr><tr><td>3</td><td>4.50%</td><td>2.0225</td><td>5.18%</td></tr><tr><td>6</td><td>4.70%</td><td>2.0150</td><td>5.83%</td></tr><tr><td>9</td><td>5.00%</td><td>1.9875</td><td>5.10%</td></tr><tr><td>12</td><td>5.50%</td><td>1.9750</td><td>5.75%</td></tr><tr><td>15</td><td>6.10%</td><td>1.9685</td><td>5.74%</td></tr><tr><td>18</td><td>6.30%</td><td>1.9480</td><td>5.28%</td></tr><tr><td>21</td><td>6.36%</td><td>1.9325</td><td>5.65%</td></tr><tr><td>24</td><td>6.40%</td><td>1.9300</td><td>5.53%</td></tr></table></body></html>  

# MATLAB EXERCISE  

9. a. Write a MATLAB program to determine the bond price and swap rate from the given set of FRA rates and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the “Forward” worksheet of the “Data.xlsx” file on the chapter webpage. Now plot all the curves simultaneously and comment on their characteristics. b. Write a MATLAB program to determine the bond price and FRA rate from the given set of forward swap rates and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the “Swap” worksheet of “Data.xlsx” file. Now plot all the curves simultaneously and comment on their characteristics. c. Write a MATLAB program to determine the FRA price and swap rate from the given set of bond prices and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the “Bond” worksheet of “Data.xlsx” file. Now plot all the curves simultaneously and comment on their characteristics.  

This page intentionally left blank  