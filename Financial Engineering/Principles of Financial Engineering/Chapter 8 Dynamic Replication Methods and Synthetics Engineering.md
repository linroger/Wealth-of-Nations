# DYNAMIC REPLICATION METHODS 8 AND SYNTHETICS ENGINEERING  

# CHAPTER OUTLINE  

8.1 Introduction . 238   
8.2 An Example.. 238   
8.3 A Review of Static Replication ...... . 239   
8.3.1 The Framework.. . 241   
8.3.2 Synthetics with a Missing Asset . 242   
8.3.2.1 A synthetic that uses $\mathsf{B}_{\mathrm{t}}$ only .. .243   
8.3.2.2 Synthetics that use $\mathsf{B}_{\mathrm{t}}$ and B(t, ${\sf T}_{3})$ .. .244   
8.4 “Ad Hoc” Synthetics.. 245   
8.4.1 Immunization. 246   
8.5 Principles of Dynamic Replication.. 248   
8.5.1 Dynamic Replication of Options.. 248   
8.5.2 Dynamic Replication in Discrete Time 250   
8.5.2.1 The method .. .250   
8.5.3 Binomial Trees . 250   
8.5.4 The Replication Process. 251   
8.5.4.1 The $\mathsf{B}_{\mathrm{t}},$ B(t, $\intercal_{3})$ dynamics . .251   
8.5.4.2 Mechanics of replication.. .254   
8.5.4.3 Guaranteeing self-financing . .255   
8.5.5 Two Examples 255   
8.5.5.1 Replicating the bond . .255   
8.5.6 Application to Options 258   
8.6 Some Important Conditions . 261   
8.6.1 Arbitrage-Free Initial Conditions . 261   
8.6.2 Role of Binomial Structure .. . 261   
8.7 Real-Life Complications... 262   
8.7.1 Bid Ask Spreads and Liquidity . 262   
8.7.2 Models and Jumps... 263   
8.7.3 Maintenance and Operational Costs 263   
8.7.4 Changes in Volatility . 263   
8.8 Conclusions.. 263   
Suggested Reading . . 264   
Exercises . 264  

# 8.1 INTRODUCTION  

The previous chapters have dealt with static replication of cash flows. The synthetic constructions we discussed were static in the sense that the replicating portfolio did not need any adjustments until the target instrument matured or expired. As time passed, the fair value of the synthetic and the value of the target instrument moved in an identical fashion.  

However, static replication is not always possible in financial engineering, and replicating portfolios may need constant adjustment (rebalancing) to maintain their equivalence with the targeted instrument. This is the case for many different reasons. First of all, the implementation of static replication methods depends on the existence of other assets that permit the use of what we called contractual equations. To replicate the targeted security, we need a minimum number of “righthand side” instruments in the contractual equation. If markets in the component instruments do not exist, contractual equations cannot be used directly and the synthetics cannot be created this way.  

Second, the instruments themselves may exist, but they may not be liquid. If the components of a theoretical synthetic do not trade actively, the synthetic may not really replicate the original asset satisfactorily, even though sensitivity factors with respect to the underlying risk factors are the same. For example, if constituent assets are illiquid, the price of the original asset cannot be obtained by “adding” the prices of the instruments that constitute the synthetic. These prices cannot be readily obtained from markets. Replication and marking-to-market can only be done using assets that are liquid and “similar” but not identical to the components of the synthetic. Such replicating portfolios may need periodic adjustments.  

Third, the asset to be replicated can be highly nonlinear. Using linear instruments to replicate nonlinear assets will involve various approximations. At a minimum, the replicating portfolios need to be rebalanced periodically. This would be the case with assets containing optionality. As the next two chapters will show, options are convex instruments, and their replication requires dynamic hedging and constant rebalancing.  

Finally, the parameters that play a role in the valuation of an asset may change, and this may require rebalancing of the replicating portfolio.  

In this chapter, we will see that creating synthetics by dynamic replication methods follows the same general principles as those used in static replication, except for the need to rebalance periodically. In this sense, dynamic replication may be regarded as merely a generalization of the static replication methods discussed earlier. In fact, we could have started the book with principles of dynamic replication and then shown that, under some special conditions, we would end up with static replication. Yet, most “bread-and-butter” market techniques are based on the static replication of basic instruments. Static replication is easier to understand, since it is less complex. Hence, we dealt with static replication methods first. This chapter extends them now to dynamic replication.  

# 8.2 AN EXAMPLE  

Dynamic replication is traditionally discussed within a theoretical framework. It works “exactly” only in continuous time, where continuous, infinitesimal rebalancing of the replicating portfolio is possible. This exactness in replication may quickly disappear with transaction costs, jumps in asset prices, and other complications. In discrete time, dynamic replication can be regarded as an approximation. Yet, even when it does not lead to the exact replication of assets, dynamic replication is an essential tool for the financial engineer.  

In spite of the many practical problems, discrete time dynamic hedging forms the basis of pricing and hedging of many important instruments in practice. The following reading shows how dynamic replication methods are spreading to areas quite far from their original use in financial engineering—namely, for pricing and hedging plain vanilla options.  

# EXAMPLE  

A San Francisco-based institutional asset manager is selling an investment strategy that uses synthetic bond   
options to supply a guaranteed minimum return to investors. . Though not a new concept—option replication has been around since the late 1980s. . . the bond option   
replication portfolio. . . replicates call options in that it allows investors to participate in unlimited upside   
while not participating in the downside. The replicating portfolio mimics the price behaviour of the option every day until expiration. Each day   
the model provides a hedge ratio or delta, which shows how much the option price will change as the   
underlying asset changes. “They are definitely taking a dealer’s approach, rather than an asset manager’s approach in that they   
are not buying options from the Street; they are creating them themselves,” [a dealer] said.  

(Thomson Reuters IFR, February 28, 1998)  

This reading illustrates one use of dynamic replication methods. It shows that market participants may replicate nonlinear assets in a cheaper way than buying the same security from the dealers. In the example, dynamic replication is combined with principal preservation to obtain a product that investors may find more attractive. Hence, dynamic replication is used to create synthetic options that are more expensive in the marketplace.  

# 8.3 A REVIEW OF STATIC REPLICATION  

The following briefly reviews the steps taken in static replication.  

1. First, we write down the cash flows generated by the asset to be replicated. Figure 8.1 repeats the example of replicating a deposit. The figure represents the cash flows of a $T_{\mathbf{\delta}}$ -maturity Eurodeposit. The instrument involves two cash flows at two different times, $t$ and $T_{\mathbf{\delta}}$ , in a given currency, US dollars (USD).   
2. Next, we decompose these cash flows in order to recreate some (liquid) assets such that a vertical addition of the new cash flows match those of the targeted asset. This is shown in the top part of Figure 8.1. A forward currency contract written against a currency $X$ , a foreign deposit in currency $X$ , and a spot FX operation have cash flows that duplicate the cash flows of the Eurodeposit when added vertically.  

![](4228c5adfb906222f3c97a9379568bce1fe2a52e1607fd7dc2f7271058ee2afb.jpg)  

# FIGURE 8.1  

Eurodeposit example.  

3. Finally, we have to make sure that the (credit) risks of the targeted asset and the proposed synthetic are indeed the same. The constituents of the synthetic asset form what we call the replicating portfolio.  

We have seen several examples for creating such synthetic assets. It is useful to summarize two important characteristics of these synthetics.  

First of all, a synthetic is created at time $t$ by taking positions on three other instruments. But, and this is the point that we would like to emphasize, once these positions are taken we never again have to modify or readjust the quantity of the instruments purchased or sold until the expiration of the targeted instrument. This is in spite of the fact that market risks would certainly change during the interval $(t,T)$ . The decision concerning the weights of the replicating portfolio is made at time $t$ , and it is kept until time $T.$ As a result, the synthetic does not require further cash injections or cash withdrawals, and it matches all the cash flows generated by the original instrument.  

Second, the goal is to match the expiration cash flows of the target instrument. Because the replication does not require any cash injections or withdrawals during the interval $[t,\ T]$ , the time $t$ value of the target instrument will then match the value of the synthetic.  

# 8.3.1 THE FRAMEWORK  

Let us show how nonexistence or illiquidity of markets and the convexity of some instruments change the methodology of static synthetic asset creation. We first need to illustrate the difficulties of using static methods under these circumstances. Second, we need to motivate dynamic synthetic asset creation.  

The treatment will naturally be more technical than the simple approach adopted prior to this chapter. It is clear that as soon as we move into the realm of portfolio rebalancing and dynamic replication, we will need a more analytical underlying framework. In particular, we need to be more careful about the timing of adjustments, and especially how they can be made without any cash injections or withdrawals.  

We adopt a simple environment of dynamic synthetic asset creation using a basic example—we use discount bonds and assume that risk-free borrowing and lending is the only other asset that exists. We assume that there are no markets in FX, interest rate forwards, and Eurodeposit accounts beyond the very short maturity. We will try to create synthetics for discount bonds in this simple environment. Later in the chapter, we move into equity instruments and options and show how the same techniques can be implemented there.  

We consider a sequence of intervals of length $\delta$ :  

$$
t_{0}<\ldots<t_{i}<\ldots<T
$$  

with  

$$
t_{i+1}-t_{i}=\delta
$$  

Suppose the market practitioner faces only two liquid markets. The first is the market for oneperiod lending/borrowing, denoted by the symbol $B_{t}$ .1 The $B_{t}$ is the time $t$ value of $\$1$ invested at time $t_{0}$ . Growing at the annual floating interest rate $L_{t_{i}}$ with tenor $\delta$ , the value of $B_{t}$ at time $t_{n}$ can be expressed as  

$$
B_{t_{n}}=\left(1+L_{t_{0}}\delta\right)\left(1+L_{t_{1}}\delta\right)\cdots\left(1+L_{t_{n-1}}\delta\right)
$$  

The second liquid market is for a default-free pure discount bond whose time $t$ price is denoted by $B(t,\ T)$ . The bond pays 100 at time $T$ and sells for the price $B(t,\ T)$ at time $t$ . The practitioner can use only these two liquid instruments, $\{B_{t},B(t,\ T)\}$ , to construct synthetics. No other liquid instrument is available for this purpose.  

It is clear that these are not very realistic assumptions except maybe for some emerging markets where there is a liquid overnight borrowing lending facility and one other liquid, on-the-run discount bond. In mature markets, not only is there a whole set of maturities for borrowing and lending and for the discount bond, but rich interest rate and FX derivative markets also exist. These facilitate the construction of complex synthetics as seen in earlier chapters. However, for discussing dynamic synthetic asset creation, the simple framework selected here will be very useful. Once the methodology is understood, it will be straightforward to add new markets and instruments to the picture.  

# 8.3.2 SYNTHETICS WITH A MISSING ASSET  

Consider a practitioner operating in the environment just described. Suppose this practitioner would like to buy, at time $t_{0}$ , a two-period default-free pure discount bond denoted by $B(t_{0},T_{2})$ with maturity date $T_{2}=t_{2}$ . It turns out that the only bond that is liquid is a three-period bond with price $B(t_{0},$ $\begin{array}{r}{T_{3,}}\end{array}$ and maturity $T_{3}=t_{3}$ . The $B(t_{0},T_{2})$ either does not exist or is illiquid. Its current fair price is unknown. So the market practitioner decides to create the $B(t_{0},T_{2})$ synthetically.  

One immediate consideration is that a static replication would not work in this setting. To see this, consider Figures 8.2 and 8.3. Figure 8.2 shows the cash flow diagrams for $B_{t}.$ , the one-period borrowing/lending, combined with the cash flows of a two-period bond. Figure 8.3 shows the cash flows of the three-period bond. The top portion of Figure 8.2 shows that $B(t_{0},T_{2})$ is paid at time $t_{0}$  

![](8b61ceb08dcbc6298d86a02e80575df8e386911553b858a0084e488c09ecf352.jpg)  

# FIGURE 8.2  

![](05f91095ccc72773a276b7d8ffeff9eedbb2b42a3c674365a3200e56e65d441b.jpg)  

# FIGURE 8.3  

Cash flows of a three-period bond.  

to buy the bond that yields 100 at maturity $T_{2}$ . These simple cash flows cannot, unfortunately, be reconstructed using one-period borrowing/lending $B_{t}$ only, as can be seen in the second part of Figure 8.2. The two-period bond consists of two known cash flows at times $t_{0}$ and $T_{2}$ . It is impossible to duplicate, at time $t_{0}$ , the cash flow of 100 at $T_{2}$ using $B_{t}.$ , without making any cash injections and withdrawals, as the next section will show.  

# 8.3.2.1 A synthetic that uses $\beta_{t}$ only  

Suppose we adopt a rollover strategy: (i) lend money at time $t_{0}$ for one period, at the known rate $L_{t_{0}}$ , (ii) collect the proceeds from this at $t_{1}$ , and (iii) lend it again at time $t_{1}$ at a rate $L_{t_{1}}$ , so as to achieve a net cash inflow of 100 at time $t_{2}$ . There are two problems with this approach. First, the rate $L_{t_{1}}$ is not known at time $t_{0}$ , and hence we cannot decide, at $t_{0}$ , how much to lend in order to duplicate the time $t_{2}$ cash flow. The amount  

$$
\frac{100}{\left(1+L_{t_{0}}\delta\right)\left(1+L_{t_{1}}\delta\right)}
$$  

that needs to be invested to recover the USD100 needed at time $t_{2}$ is not known. This is in spite of the fact that $L_{t_{0}}$ is known.  

Of course, we could guess how much to invest and then make any necessary additional cash injections into the portfolio when time $t_{1}$ comes. We can invest $B_{t_{0}}$ at $t_{0}$ , and then once $L_{t_{1}}$ is observed at $t_{1}$ , we add or subtract an amount $\Delta B$ of cash to make sure that  

$$
\left[B_{t_{0}}\left(1+L_{t_{0}}\delta\right)+\Delta B\right]\left(1+L_{t_{1}}\delta\right)=100
$$  

But, and this is the second problem, this strategy requires injections or withdrawals $\Delta B$ of an unknown amount at $t_{1}$ . This makes our strategy useless for hedging, as the portfolio is not selffinancing and the need for additional funds is not eliminated.  

Pricing will be imperfect with this method. Potential injections or withdrawals of cash imply that the true cost of the synthetic at time $t_{0}$ is not known.2 Hence, the one-period borrowing/lending cannot be used by itself to obtain a static synthetic for $B(t_{0},T_{2})$ . As of time $t_{0}$ , the creation of the  

synthetic is not complete, and we need to make an additional decision at date $t_{1}$ to make sure that the underlying cash flows match those of the targeted instrument.  

# 8.3.2.2 Synthetics that use $\beta_{t}$ and B(t, T3)  

Bringing in the liquid longer-term bond $B(t,~T_{3})$ will not help in the creation of a static synthetic either. Figure 8.4 shows that no matter what we do at time $t_{0}$ , the three-period bond will have an extra and nonrandom cash flow of $\$100$ at maturity date $T_{3}$ . This cash flow, being “extra” (an exact duplication of the cash flows generated by $B(t,T_{2})$ as of time $t_{0}$ ), is not realized.  

Up to this point, we did not mention the use of interest rate forward contracts. It is clear that a straightforward synthetic for $B(t_{0},T_{2})$ could be created if a market for forward loans or forward rate agreements (FRAs) existed along with the “long” bond $B(t_{0},T_{3})$ . In our particular case, a $2\times3$  

![](1906cbb0bf36456354f0e4a0acef0953503f717e1232a2d9109636bff8dd0370.jpg)  

# FIGURE 8.4  

Replicating two-period loan with FRA and three-period bond.  

FRA would be convenient as shown in Figure 8.4. The synthetic consists of buying $\left(1+f_{t_{0}}\delta\right)$ units of the $B(t_{0},T_{3})$ and, at the same time, taking out a one-period forward loan at the forward rate $f_{t_{0}}$ . This way, we would successfully recreate the two-period bond in a static setting. But this approach assumes that the forward markets exist and that they are liquid. If these markets do not exist, dynamic replication is our only recourse.  

# 8.4 “AD HOC ” SYNTHETICS  

Then how can we replicate the two-period bond? There are several answers to this question, depending on the level of accuracy a financial engineer expects from the “synthetic.” An accurate synthetic requires dynamic replication which will be discussed later in this chapter. But, there are also less accurate, ad hoc, solutions. As an example, we consider a simple, yet quite popular way of creating synthetic instruments in the fixed income sector, referred to as the immunization strategy.  

In this section, we will temporarily deviate from the notation used in the previous section and let, for simplicity, $\delta=1$ ; so that $t_{i}$ represents years. We assume that there are three instruments. They depend on the same risk factors, yet they have different sensitivities due to strong nonlinearities in their respective valuation formulas. We adopt a slightly more abstract framework compared to the previous section and let the three assets $\{S_{1t},S_{2t},S_{3t}\}$ be defined by the pricing functions:  

$$
\begin{array}{c}{S_{1t}=f(x_{t})}\\ {S_{2t}=g(x_{t})}\\ {S_{3t}=h(x_{t})}\end{array}
$$  

where the functions $h(.),f(.)$ , and $g(.)$ are nonlinear. $x_{t}$ is the common risk factor to all prices. $S_{1t}$   
will play the role of targeted instrument and $\{S_{2t},S_{3t}\}$ will be used to form the synthetic.  

We again begin with static strategies. It is clear that as the sensitivities are different, a static methodology such as the one used in Chapters $_{3-7}$ cannot be implemented. As time passes, $x_{t}$ will change randomly, and the response of $S_{i t}$ $_{t},i=1,2,3$ , to changes in $x_{t}$ will be different. However, one ad hoc way of creating a synthetic for $S_{1t}$ by using $S_{2t}$ and $S_{3t}$ is the following.  

At time $t$ , we form a portfolio with a value equal to $S_{1t}$ and with weights $\theta^{2}$ and $\theta^{3}$ such that the sensitivities of the portfolio  

$$
\theta^{2}S_{2t}+\theta^{3}S_{3t}
$$  

with respect to the risk factor $x_{t}$ are as close as possible to the corresponding sensitivities of $S_{1t}$ . Using the first-order sensitivities, we obtain two equations in two unknowns, $\{\bar{\theta}^{2},\theta^{3}\}$ :  

$$
\begin{array}{c}{{S_{1}={\theta}^{2}S_{2}+{\theta}^{3}S_{3}}}\\ {{{}}}\\ {{{\displaystyle\frac{\partial S_{1}}{\partial x}={\theta}^{2}\frac{\partial S_{2}}{\partial x}+{\theta}^{3}\frac{\partial S_{3}}{\partial x}}}}\end{array}
$$  

A strategy using such a system may have some important shortcomings. It will in general require cash injections or withdrawals over time, and this violates one of the requirements of a  

synthetic instrument. Yet, under some circumstances, it may provide a practical solution to problems faced by the financial engineer. The following section presents an example.  

# 8.4.1 IMMUNIZATION  

Suppose that, at time $t_{0}$ , a bank is considering the purchase of the previously mentioned two-period discount bond at a price $B(t_{0},T_{2})$ , $T_{2}=t_{0}+2$ . The bank can fund this transaction either by using 6-month floating funds or by selling short a three-period discount bond $B(t_{0},T_{3})$ , $T_{3}=t_{0}+3$ or a combination of both. How should the bank proceed?  

The issue is similar to the one that we pursued earlier in this chapter—namely, how to construct a synthetic for $B(t_{0},T_{2})$ . The best way of doing this is, of course, to determine an exact synthetic that is liquid and least expensive—using the 6-month funds and the three-period bond—and then, if a hedge is desired, sell the synthetic. This will also provide the necessary funds for buying $B(t_{0},$ $T_{2})$ . The result will be a fully hedged position where the bank realizes the bid ask spread. We will learn later in the chapter how to implement this “exact” approach using dynamic strategies.  

An approximate way of proceeding is to match the sensitivities as described earlier. In particular, we would try to match the first-order sensitivities of the targeted instrument. The following strategy is an example for the immunization of a fixed-income portfolio. As we saw in Chapter 3, the first-order sensitivities are called duration. In order to work with a simple risk factor, we assume that the yield curve displays parallel shifts only. This assumption rarely holds, but it is still used quite frequently by some market participants as a first-order approximation. In our case, we use it to simplify the exposition.  

# EXAMPLE  

Suppose the zero-coupon yield curve is flat at $y=8\%$ and that the shifts are parallel. Then, the values of the 2-year, 3-year, and 6-month bonds in terms of the corresponding yield $y$ will be given by  

$$
\begin{array}{c}{{B(t_{0},T_{2})=\displaystyle\frac{100}{\left(1+y\right)^{2}}=85.73}}\\ {{{}}}\\ {{B(t_{0},T_{3})=\displaystyle\frac{100}{\left(1+y\right)^{3}}=79.38}}\end{array}
$$  

$$
B(t_{0},T_{0.5})=\frac{100}{\left(1+y\right)^{0.5}}=96.23
$$  

Using the “long” bond $B(t_{0},T_{3})$ and the “short” $B(t_{0},T_{0.5})$ , we need to form a portfolio with initial cost 85.73. This will equal the time $t_{0}$ value of the target instrument, $B(t_{0},T_{2})$ . We also want the sensitivities of this portfolio with respect to $y$ to be the same as the sensitivity of the original instrument. We therefore need to solve the equations  

$$
\theta^{1}B(t_{0},T_{3})+\theta^{2}B(t_{0},T_{0.5})=85.73
$$  

$$
\theta^{1}\frac{\partial B(t_{0},T_{3})}{\partial y}+\theta^{2}\frac{\partial B(t_{0},T_{0.5})}{\partial y}=\frac{\partial B(t_{0},T_{2})}{\partial y}
$$  

We can calculate the “current” values of the partials:  

$$
\begin{array}{c}{{\displaystyle{\frac{\partial B(t_{0},T_{0.5})}{\partial y}=\frac{-50}{(1+y)^{1.5}}=-44.55}}}\\ {{\mathrm{}}}\\ {{\displaystyle{\frac{\partial B(t_{0},T_{2})}{\partial y}=-158.77}}}\\ {{\mathrm{}}}\\ {{\displaystyle{\frac{\partial B(t_{0},T_{3})}{\partial y}=-220.51}}}\end{array}
$$  

Replacing these in Eqs. (8.15) and (8.16), we get  

$$
\begin{array}{c}{{\theta^{1}79.38+\theta^{2}96.23=85.73}}\\ {{\ }}\\ {{\theta^{1}(220.51)+\theta^{2}(44.55)=158.77}}\end{array}
$$  

Solving  

$$
\theta^{1}=0.65,\theta^{2}=0.36
$$  

Hence, we need to short 0.36 units of the 6-month bond and short 0.65 units of the 3-year bond to create an approximate synthetic that will fund the 2-year bond. This will generate the needed cash and has the same first-order sensitivities with respect to changes in $y$ at time $t_{0}$ . This is a simple example of immunizing a fixed-income portfolio.  

According to this, the asset being held, $B(t_{0},\ T_{2})$ , is “funded” by a portfolio of other assets, in a way to make the response of the total position insensitive to first-order changes in y. In this sense, the position is “immunized.”  

The preceding example shows an approximate way of obtaining “synthetics” using dynamic methods. In our case, portfolio weights were selected so that the response to a small change in the yield, $d y$ , was the same. But, note the following important point.  

The second- and higher-order sensitivities were not matched. Thus, the funding portfolio was not really an exact synthetic for the original bond $B(t_{0},T_{2})$ . In fact, the second partials of the “synthetic” and the target instrument would respond differently to dy. Therefore, the portfolio weights $\theta^{i}$ , $i=1$ , 2 need to be recalculated as time passes and new values of $y$ are observed.  

It is important to realize in what sense(s) the method is approximate. Even though we can adjust the weights $\theta^{i}$ as time passes, these adjustments would normally require cash injections or withdrawals. This means that the portfolio is not self-financing.  

In addition, the shifts in the yield curve are rarely parallel, and the yields for the three instruments may change by different amounts, destroying the equivalence of the first-order sensitivities as well.  

# 8.5 PRINCIPLES OF DYNAMIC REPLICATION  

We now go back to the issue of creating a satisfactory synthetic for a “short” bond $B(t_{0},T_{2})$ using the savings account $B_{t}$ and a “long” bond $B(t_{0},T_{3})$ . The best strategy for constructing a synthetic for $B(t_{0},T_{2})$ consists of a “clever” position taken in $B_{t}$ and $B(t_{0},T_{3})$ such that, at time $t_{1}$ , the extra cash generated by $B_{t}$ adjustment is sufficient for adjusting $B(t_{0},T_{3})$ .  

In other words, we give up static replication, and we decide to adjust the time $t_{0}$ positions at time $t_{1}$ , in order to match the time $T_{2}$ cash payoff of the two-period bond. However, we adjust the positions in a way that no net cash injections or withdrawals take place. Whatever cash is needed at time $t_{1}$ for the adjustment of one instrument will be provided by the adjustment of the other instrument. If this is done while at the same time it is ensured that the time $T_{2}$ value of this adjusted portfolio is 100, replication will be complete. It will not be static; it will require adjustments, but, importantly, we would know, at time $t_{0}$ , how much cash to put down in order to receive $\$100$ at $T_{2}$ .  

Such a strategy works because both $B_{t_{1}}$ and $B(t_{0},\ T_{3})$ depend on the same $L_{t_{1}}$ , the interest rate that is unknown at time $t_{0}.$ , and both have known valuation formulas. By cleverly taking offsetting positions in the two assets, we may be able to eliminate the effects of the unknown $L_{t_{1}}$ as of time $t_{0}$ .  

The strategy will combine imperfect instruments that are correlated with each other to get a synthetic at time $t_{0}$ . However, this synthetic will need constant rebalancing due to the dependence of the portfolio weights on random variables unknown as of time $t_{0}$ . Yet, if these random variables were correlated in a certain fashion, these correlations can be used against each other to eliminate the need for cash injections or withdrawals. The cost of forming the portfolio at $t_{0}$ would then equal the arbitrage-free value of the original asset.  

What are the general principles of dynamic replication according to the discussion thus far?  

1. We need to make sure that during the life of the security there are no dividends or other payouts. The replicating portfolio must match the final cash flows exactly.   
2. During the replication process, there should be no net cash injections or withdrawals. The cash deposited at the initial period should equal the true cost of the strategy.   
3. The credit risks of the proposed synthetic and the target instrument should be the same.  

As long as these principles are satisfied, any replicating portfolio whose weights change during $[t,T]$ can be used as a synthetic of the original asset. In the rest of the chapter, we apply these principles to a particular setting and learn the mechanics of dynamic replication.  

# 8.5.1 DYNAMIC REPLICATION OF OPTIONS  

For replicating options, we use the same logic as in the case of the two-period bond discussed in the previous section. We will explore options in the next chapter. However, for completeness we repeat a brief definition. A European call option entitles the holder to buy an underlying asset, $S_{t}$ , at a strike price $K_{\cdot}$ , at an expiration date $T_{\cdot}$ . Thus, at time $T,t<T_{:}$ the call option payoff is given by the broken line shown in Figure 8.5. If price at time $T$ is lower than $K$ , there is no payoff. If $S_{T}$ exceeds $K.$ , the option is worth $(S_{T}-K)$ . The value of the option before expiration involves an additional component called the time value and is given by the curve shown in Figure 8.5.  

Let the underlying asset be a stock whose price is $S_{t}$ . Then, when the stock price rises, the option price also rises, everything else being the same. Hence the stock is highly correlated with the option.  

This means that we can form at time $t_{0}$ a porfolio using $B_{t_{0}}$ and $S_{t_{0}}$ such that as time passes, the gains from adjusting one asset compensate the losses from adjusting the other. Constant rebalancing can be done without cash injections and withdrawals, and the final value of the portfolio would equal the expiration value of the option. If this can be done with reasonably close approximation,  

![](c9c23d7a8f47e7b9617a7233feafdd1874f9b3d3552107b3ad06a4848ac49298.jpg)  

# FIGURE 8.5  

the cost of forming the portfolio would equal the arbitrage-free value of the option. We will discuss this case in full detail later in this chapter, and will see an example when interest rates are assumed to be constant.  

# 8.5.2 DYNAMIC REPLICATION IN DISCRETE TIME  

In practice, dynamic replication cannot be implemented in continuous time. We do need some time to adjust the portfolio weights, and this implies that dynamic strategies need to be analyzed in discrete time. We prefer to start with bonds again, and then move to options. Suppose we want to replicate the two-period default-free discount bond $B(t_{0},T_{2})$ , $T_{2}=t_{2}$ , using $B_{t}$ ${\bf\Lambda}_{t},B(t_{0},T_{3})$ with $T_{2}<T_{3}$ , similar to the special case discussed earlier. How do we go about doing this in practice?  

# 8.5.2.1 The method  

The replication period is $[t_{0},T_{2}]$ , and rebalancing is done in discrete intervals during this period. First, we select an interval of length $\Delta$ , and divide the period $[t_{0},T_{2}]$ into $n$ such finite intervals:  

$$
n\Delta=T_{2}-t_{0}
$$  

At each $t_{i}=t_{i-1}+\Delta$ , we select new portfolio weights $\theta_{t_{i}}$ such that  

1. At $T_{2}$ , the dynamically created synthetic has exactly the same value as the $T_{2}$ -maturity bond. 2. At each step, the adjustment of the replicating portfolio requires no net cash injections or withdrawals.  

To implement such a replication strategy, we need to deviate from static replication methods and make some new assumptions. In particular, we just saw that correlations between the underlying assets play a crucial role in dynamic replication. Hence, we need a model for the way $B_{t}$ , $B(t,T_{2})$ , and $B(t,T_{3})$ move jointly over time.  

This is a delicate process, and there are at least three approaches that can be used to model these dynamics: (i) binomial-tree or trinomial-tree methods; (ii) partial differential equation (PDE) methods, which are similar to trinomial-tree models but are more general; and (iii) direct modeling of the risk factors using stochastic differential equations and Monte Carlo simulation. In this section, we select the simplest binomial tree methods to illustrate important aspects of creating synthetic assets dynamically.  

# 8.5.3 BINOMIAL TREES  

We simplify the notation significantly. We let $j=0$ , 1, 2, . . . denote the “time period” for the binomial tree. We choose $\Delta$ so that $n=3$ . The tree will consist of three periods, $j=0$ , 1, and 2. At each node there are two possible states only. This implies that at $j=1$ there will be two possible states, and at $j=2$ there will be four altogether.3  

In fact, by adjusting $\Delta$ and selecting the number of possible states at each node as two, three, or more, we obtain more and more complicated trees. With two possible states at every node, the tree is called binomial; with three possible states, the tree is called trinomial. The implied binomial  

![](2e830e94c9e6ac6bd2118a8e7d3990648a1005799cc8ecf9ef926a7c4a161b40.jpg)  

# FIGURE 8.6  

A binomial tree.  

tree is in Figure 8.6. Here, possible states at every node are denoted, as usual, by up or down. These terms do not mean that a variable necessarily goes up or down. They are just shortcut names used to represent what traders may regard as “bullish” and “bearish” movements.  

# 8.5.4 THE REPLICATION PROCESS  

In this section, we let $\Delta=1$ , for notational convenience. Consider the two binomial trees shown in Figure 8.7 that give the joint dynamics of $B_{t}$ and $B(t,\ T)$ over time. The top portion of the figure represents a binomial tree that describes an investment of $\$1$ at $j=0$ . This investment, called the savings account, is rolled over at the going spot interest rate. The bottom part of the figure describes the price of the “long bond” over time. The initial point $j=0$ is equivalent to $t_{0}$ , and $j=3$ is equivalent to $t_{3}$ when the long bond $B(t_{0},\ T_{3})$ matures. The tree is nonrecombining, implying that a fall in interest rates following an increase would not give the same value as an increase that follows a drop. Thus, the path along which we get to a time node is important.4 We now consider the dynamics implied by these binomial trees.  

# 8.5.4.1 The $\mathsf{B}_{\mathrm{t}},\mathsf{B}(\mathsf{t},\mathsf{T}_{3})$ dynamics  

First consider a tree for $B_{t},$ the savings account or risk-free borrowing and lending. The practitioner starts at time $t_{0}$ with one dollar. The observed interest rate at $j=0$ is $10\%$ , and the dollar invested initially yields 1.10 regardless of which state of the world is realized at time $j=1$ .5 There are two possibilities at $j=1$ . The up state is an environment where interest rates have fallen and bond prices, in general, have increased. Figure 8.7 shows a new spot rate of $8\%$ for the $\boldsymbol{u p}$ state in period $j=1$ . For the down state, it displays a spot rate that has increased to $15\%$ .  

Thus, looking at the tree from the initial point $t_{0}$ , we can see four possible paths for the spot rate until maturity time $t_{2}$ of the bond under consideration. Starting from the top, the spot interest rate paths are  

$$
\begin{array}{c}{{\{10\%,8\%,6\%\}}}\\ {{\{10\%,8\%,9\%\}}}\\ {{\{10\%,15\%,12\%\}}}\\ {{\{10\%,15\%,18\%\}}}\end{array}
$$  

These imply four possible paths for the value of the savings account $B_{t}$ :  

$$
\begin{array}{r l}&{\{1,1.10,1.188,1.26\}}\\ &{\{1,1.10,1.188,1.29\}}\\ &{\{1,1.10,1.26,1.42\}}\\ &{\{1,1.10,1.26,1.49\}}\end{array}
$$  

It is clear that as $\Delta$ becomes smaller, and $n$ gets larger, the number of possible paths will increase.  

The tree for the “long” bond is shown in the bottom part of Figure 8.7. Here the value of the bond is $\$100$ at $j=3$ , since the bond matures at that point. Because there is no default risk, the maturity value of the bond is the same in any state of the world. This means that one period before maturity the bond will mimic a one-period risk-free investment. In fact, no matter which one of the next two states occurs, in going from a node at time $j=2$ to a relevant node at time $j=3$ , we always invest a constant amount and receive 100. For example, at point $A$ , we pay  

$$
B(2,3)^{\mathrm{down}}=91.7
$$  

for the bond and receive 100, regardless of the spot rate move. This will change, however, as we move toward the origin. For example, at point $B$ , we have either a “good” return:  

$$
R^{\mathrm{up}}=\frac{94.3}{85.0}
$$  

or a “bad” return:  

$$
R^{\mathrm{{down}}}=\frac{91.7}{85.0}
$$  

Hence, Figure 8.7 shows the dynamics of two different default-free fixed-income instruments: the savings account $B_{t}$ , which can also be interpreted as a shorter maturity bond, and a three-period long bond $B(t,T_{3})$ . The question is how to combine these two instruments so as to form a synthetic medium-term bond $B(t,T_{2})$ .  

![](b97474eab8e46f9690ed420bf24449f791617d30b18416afd9f9e3c0d0d003c8.jpg)  

# FIGURE 8.7  

Binomial tree with lending/borrowing and three-period bond dynamics.  

# 8.5.4.2 Mechanics of replication  

We will now discuss the mechanics of replication. Consider Figure 8.8, which represents a binomial tree for the price of a two-period bond, $B(t,T_{2})$ . This tree is assumed to describe exactly the same states of the world as the ones shown in Figure 8.7. The periods beyond $j=2$ are not displayed, given that $B(t,T_{2})$ matures then. According to this tree, we know the value of the two-period bond only at $j=2$ . This value is 100, since the bond matures. Earlier values of the bond are not known and hence are left blank. The most important unknown is, of course, the time $j=0$ value $B(t_{0},T_{2})$ . This is the “current” price of the two-period bond. The problem we deal with in this section is how to “fill in” this tree.  

The idea is to use the information given in Figure 8.7 to form a portfolio with (time-varying) weights $\theta_{t}^{\mathrm{lend}}$ and $\theta_{t}^{\mathrm{bond}}$ for $B_{t}$ and $B(t,~T_{3})$ . The portfolio should mimic the value of the mediumterm bond $B(t,~T_{2})$ at all nodes at $j=0$ , 1, 2. The first condition on this portfolio is that, at $T_{2}$ , its value must equal 100.  

The second important condition to be satisfied by the portfolio weights is that the $j=0$ , 1 adjustments do not require any cash injections or withdrawals. This means that, as the portfolio weights are adjusted or rebalanced, any cash needed for increasing the weight of one asset should come from adjustment of the other asset. This way, cash flows will consist of a payment at time $t_{0}$ , and a receipt of $\$100$ at time $T_{2}$ , with no interim net payments or receipts in between—which is exactly the cash flows of a two-period discount bond.  

Then, by arbitrage arguments the value of this portfolio should track the value of the $B(t,T_{2})$ at all relevant times. This means that the $\theta_{t}^{\mathrm{lend}}$ and $\theta_{t}^{\mathrm{bond}}$ will also satisfy  

$$
\theta_{t}^{\mathrm{lend}}B_{t}+\theta_{t}^{\mathrm{bond}}B(t,T_{3})=B(t,T_{2})
$$  

for all $t$ , or $j.$  

![](417002ba91f98ed7712df4abbc9324890a5f9147eb9849cf48f01bfb06439100.jpg)  

# FIGURE 8.8  

Binomial tree for two-period bond.  

# 8.5.4.3 Guaranteeing self-financing  

How can we guarantee that the adjustments of the weights $\theta_{j}^{\mathrm{lend}}$ and $\theta_{j}^{\mathrm{bond}}$ , observed along the tree paths $j=0,1,2$ will not lead to any cash injections or withdrawals? The following additional conditions at $j=0,1$ , will be sufficient to do this:  

$$
\begin{array}{r l}&{\theta_{j}^{\mathrm{lend}}B_{j+1}^{\mathrm{up}}+\theta_{j}^{\mathrm{bond}}B(j+1,3)^{\mathrm{up}}=\theta_{j+1}^{\mathrm{lend}}B_{j+1}^{\mathrm{up}}+\theta_{j+1}^{\mathrm{bond}}B(j+1,3)^{\mathrm{up}}}\\ &{\mathcal{I}_{j}^{\mathrm{lend}}B_{j+1}^{\mathrm{down}}+\theta_{j}^{\mathrm{bond}}B(j+1,3)^{\mathrm{down}}=\theta_{j+1}^{\mathrm{lend}}B_{j+1}^{\mathrm{down}}+\theta_{j+1}^{\mathrm{bond}}B(j+1,3)^{\mathrm{down}}}\end{array}
$$  

Let us see what these conditions mean. On the left-hand side, the portfolio weights have the subscript $j$ , while the asset prices are measured as of time $j+1$ . This means that the left-hand side is the value of a portfolio chosen at time $j$ , and valued at a new up or down state at time $j+1$ . The left-hand side is, thus, a function of “new” asset prices, but “old” portfolio weights.  

On the right-hand side of these equations, we have “new” portfolio weights, $\theta_{j+1}^{\mathrm{{lend}}}$ and $\theta_{j+1}^{\mathrm{bond}}$ multiplied by the time $j+1$ prices. Thus, the right-hand side represents the cost of a new portfolio chosen at time $j+1$ , either in the up or down state. Putting these two together, the equations imply that, regardless of which state occurs, the previously chosen portfolio generates just enough cash to put together a new replicating portfolio.  

If $\theta_{j+1}^{\mathrm{{lend}}}$ and $\theta_{j+1}^{\mathrm{bond}}$ are chosen so as to satisfy Eqs. (8.36) and (8.37), there will be no need to inject or withdraw any cash during portfolio rebalancing. The replicating portfolio will be selffinancing. This is what we mean by dynamic replication. By following these steps, we can form a portfolio at time $j=0$ and rebalance at zero cost until the final cash flow of $\$100$ is reached at time $j=2$ . Given that there is no credit risk, and all the final cash flows are equal, the initial cost of the replicating portfolio must equal the value of the two-period bond at $j=0$ :  

$$
\theta_{0}^{\mathrm{lend}}B_{0}+\theta_{0}^{\mathrm{bond}}B(0,3)=B(0,2)
$$  

Hence, dynamic replication would create a true synthetic for the two-period bond.  

Finally, consider rewriting Eq. (8.37) after a slight manipulation:  

$$
(\theta_{j}^{\mathrm{lend}}-\theta_{j+1}^{\mathrm{lend}})B_{j+1}^{\mathrm{down}}=-(\theta_{j}^{\mathrm{bond}}-\theta_{j+1}^{\mathrm{bond}})B(j+1,3)^{\mathrm{down}}
$$  

This shows that the cash obtained from adjusting one weight will be just sufficient for the cash needed for the adjustment of the second weight. Hence, there will be no need for extra cash injections or withdrawals. Note that this “works” even though $B_{j+1}^{i}$ and $B(j+1,3)^{i}$ are random. The trees in Figure 8.7 implicitly assume that these random variables are perfectly correlated with each other.  

# 8.5.5 TWO EXAMPLES  

We apply these ideas to two examples. In the first, we determine the current value of the twoperiod default-free pure discount bond using the dynamically adjusted replicating portfolio from Figure 8.7. The second example deals with replication of options.  

# 8.5.5.1 Replicating the bond  

The top part of Figure 8.7 shows the behavior of savings account $B_{t}$ . The bottom part displays a tree for the two-period discount bond $B(t,~T_{3})$ . Both of these trees are considered as given exogenously, and their arbitrage-free characteristic is not questioned at this point. The objective is to fill in the future and current values in Figure 8.8 and price the two-period bond $B(t,T_{2})$ under these circumstances.  

# EXAMPLE  

To determine $\{B(j,2),j=0,1,2\}$ , we need to begin with period $j=2$ in Figure 8.8. This is the maturity date for the two-period bond, and there is no default possibility by assumption. Thus, the possible values of the two-period bond at $j=2$ , denoted by $B(2,2)^{i}$ , can immediately be determined:  

$$
B(2,2)^{\mathrm{up\mathrm{-}u p}}=B(2,2)^{\mathrm{down\mathrm{-}u p}}=B(2,2)^{\mathrm{up\mathrm{-}d o w n}}=B(2,2)^{\mathrm{down\mathrm{-}d o w n}}=100\
$$  

Once these are placed at the $j=2$ nodes in Figure 8.8, we take one step back and obtain the values of $\{B(1,2)^{i}$ , $i=\mathrm{up}$ , down}. Here, the principles that we developed earlier will be used. As “time” goes from $j=1$ to $j=2$ , the value of the portfolio put together at $j=1$ using $B_{1}$ and $B(1,3)^{i}$ should match the possible values of $B(2,2)$ at all nodes. Consider first the top node, $B(1,2)^{\mathrm{up}}$ . The following equations need to be satisfied:  

$$
\begin{array}{r l}{\theta_{1}^{\mathrm{lend,up}}B_{2}^{\mathrm{up-up}}+\theta_{1}^{\mathrm{bond,up}}B(2,3)^{\mathrm{up-up}}=B(2,2)^{\mathrm{up-up}}}&{{}}\\ {\theta_{1}^{\mathrm{lend,up}}B_{2}^{\mathrm{up-down}}+\theta_{1}^{\mathrm{bond,up}}B(2,3)^{\mathrm{up-down}}=s B(2,2)^{\mathrm{up-down}}}&{{}}\end{array}
$$  

Here, $\theta\mathrm{s}$ have $j=1$ subscript, hence the left-hand side is the value of the replicating portfolio put together at time $j=1$ , but valued as of $j=2$ . In these equations, all variables are known except portfolio weights $\theta_{1}^{\mathrm{lend,up}}$ and $\theta_{1}^{\mathrm{bond,up}}$ . Replacing from Figure 8.7  

$$
\begin{array}{l l}{\theta_{1}^{\mathrm{lend,up}}1.188+\theta_{1}^{\mathrm{bond,up}}94.3=100}\\ {\theta_{1}^{\mathrm{lend,up}}1.188+\theta_{1}^{\mathrm{bond,up}}91.7=100}\end{array}
$$  

Solving these two equations for the two unknowns, we get the replicating portfolio weights for $j=1$ , $i={\tt u p}$ . These are in units of securities, not in dollars.  

$$
\begin{array}{c}{{\theta_{1}^{\mathrm{lend,up}}=84.18}}\\ {{\theta_{1}^{\mathrm{bond,up}}=0}}\end{array}
$$  

Thus, if the market moves to $i={\tt u p}$ , 84.18 units of $B_{1}$ will be sufficient to replicate the future values of the bond at time $j=2$ . In fact, this position will have the $j=2$ value of  

$$
84.18(1.188)=100\
$$  

Note that the weight for the long bond is zero.6 The cost of the portfolio at time $j=1$ can be obtained using the just calculated $\{\theta_{1}^{\mathrm{lend,up}},\theta_{1}^{\mathrm{bond,up}}\}$ ; this cost should equal $B(1,2)^{\mathrm{up}}$ :  

$$
\theta_{1}^{\mathrm{lend,up}}(1.1)+\theta_{1}^{\mathrm{bond,up}}(85.0)=92.6
$$  

Similarly, for the state $j=1$ , $i=\mathrm{down}$ , we have the two equations:  

$$
\begin{array}{l l}{\theta_{1}^{\mathrm{lend,down}}1.265+\theta_{1}^{\mathrm{bond,down}}89.3=100}\\ {\theta_{1}^{\mathrm{lend,down}}1.265+\theta_{1}^{\mathrm{bond,down}}84.7=100}\end{array}
$$  

Solving, we get the relevant portfolio weights:  

$$
\begin{array}{c}{{\theta_{1}^{\mathrm{lend,down}}=79.05}}\\ {{{}}}\\ {{\theta_{2}^{\mathrm{bond,down}}=0}}\end{array}
$$  

We obtain the cost of the portfolio for this state:  

$$
\theta_{1}^{\mathrm{lend,down}}(1.1)+\theta_{1}^{\mathrm{bond,down}}(75)=86.9
$$  

This should equal the value of $B(1,2)^{\mathrm{down}}$ . Finally, we move to the initial period to determine the value $B(0,~2)$ . The idea is again the same. At time $j=0$ choose the portfolio weights $\theta_{0}^{\mathrm{lend}}$ and $\theta_{0}^{\mathrm{bond}}$ such that, as time passes, the value of the portfolio equals the possible future values of $B(1,2)$ :  

$$
\begin{array}{r}{\theta_{0}^{\mathrm{lend}}1.1+\theta_{0}^{\mathrm{bond}}85.00=92.6}\\ {\theta_{0}^{\mathrm{lend}}1.1+\theta_{0}^{\mathrm{bond}}75.00=86.9}\end{array}
$$  

Here, the left-hand side is the value of the portfolio put together at time $j=0$ such that its value equals those of the two-period bond at $j=1$ . Solving for the unknowns,  

$$
\begin{array}{c}{{\theta_{0}^{\mathrm{lend}}=40.1}}\\ {{\theta_{0}^{\mathrm{bond}}=0.57}}\end{array}
$$  

Thus, at time $j=0$ we need to make a deposit of 40.1 dollars and buy 0.57 units of the three-period bond with price $B(0,3)$ . This will replicate the two possible values $\{B(1,2)^{i}$ , $i=\mathrm{up,\down\}$ . The cost of this portfolio must equal the current fair value of $B(0,2)$ , if the trees for $B_{t}$ and $B(j,3)$ are arbitrage-free. This cost is given by  

$$
B(0,2)=40.1+0.57(72)=81.14
$$  

This is the fair value of the two-period bond at $j=0$ .  

The arbitrage-free market value of the two-period bond is obtained by calculating all the current and future weights for a dynamic self-financing portfolio that duplicates the final cash flows of a two-period bond. At every step, the portfolio weights are adjusted so that the rebalanced portfolio keeps matching the values of $B(j,2),j=0,1,2.$ The fact that there were only two possible moves from every node gave a system of two equations, in two unknowns.  

Note the (important) analogy to static replication strategies. By following this dynamic strategy and adjusting the portfolio weights, we guarantee to match the final cash flows generated by the two-period bond, while never really making any cash injections or withdrawals. Each time a future node is reached, the previously determined portfolio will always yield just enough cash to do necessary adjustments.7  

# 8.5.6 APPLICATION TO OPTIONS  

We can apply the replication technique to options and create appropriate synthetics. Thus, consider the same risk-free lending and borrowing $B_{t}$ dynamics shown in Figure 8.7. This time, we would like to replicate a call option $C_{t}$ written on a stock $S_{t}$ . The call has the following plain vanilla properties. It expires at time $t_{2}$ and has a strike price $K=100$ . The option is European and cannot be exercised before the expiration date. The underlying stock $S_{t}$ does not pay any dividends. Finally, there are no transaction costs such as commissions and fees in trading $S_{t}$ or $C_{t}$ .  

Suppose the stock price $S_{t}$ follows the tree shown in Figure 8.9. Note that unlike a bond, the stock never “matures” and future values of $S_{t}$ are always random. There is no terminal time period where we know the future value of $S_{t}.$ , as was the case for the bond that expired at time $T_{3}$ .  

![](514c933a02d76f89d2d38cb532df48719f273388a13fab89aa7e676eced89ebf.jpg)  

# FIGURE 8.9  

Binomial tree for stock price.  

However, the corresponding binomial tree for the call option still has known values at expiration date $j=2$ . This is the case since, at expiration, we know the possible values that the option may assume due to the formula:  

$$
C_{2}=\operatorname*{max}[S_{2}-100,0]
$$  

Given the values of $S_{2}$ , we can determine the possible values of $C_{2}$ . But, the values of the call at earlier time periods still need to be determined.  

How can this be done? The logic is essentially the same as the one utilized in the case of a twoperiod default-free bond. We need to determine the current value of the call option, denoted by $C_{0}$ , using a dynamically adjusted portfolio that consists of the savings account and of the stock $S_{t}.$ .  

# EXAMPLE  

Start with the expiration period and use the boundary condition:  

$$
C_{2}^{i}=\operatorname*{max}[S_{2}^{i}-100,0]
$$  

where the $i$ superscript represents gain in the states of the world {upup, updown, downup, down down}. Using these, we determine the four possible values of $C_{2}^{i}$ at expiration:  

$$
C_{2}^{\mathrm{up-up}}=60,C_{2}^{\mathrm{up-down}}=42,C_{2}^{\mathrm{down-up}}=0,C_{2}^{\mathrm{down-down}}=0
$$  

Next, we take one step back and consider the value $C_{1}^{\mathsf{u p}}$ . We need to replicate this with a portfolio using $B_{1},S_{1}$ , such that as “time” passes, the value of this portfolio stays identical to the value of the option $C_{2}^{i}$ . Thus, we need  

$$
\begin{array}{r l}&{\theta_{1}^{\mathrm{lend,up}}B_{2}^{\mathrm{up-up}}+\theta_{1}^{\mathrm{stock,up}}S_{2}^{\mathrm{up-up}}=C_{2}^{\mathrm{up-up}}}\\ &{\theta_{1}^{\mathrm{lend,up}}B_{2}^{\mathrm{up-down}}+\theta_{1}^{\mathrm{stock,up}}S_{2}^{\mathrm{up-down}}=C_{2}^{\mathrm{up-down}}}\end{array}
$$  

Replacing the known values from Figures 8.7 and 8.9, we have two equations and two unknowns:  

$$
\begin{array}{l l}{\theta_{1}^{\mathrm{lend,up}}(1.188)+\theta_{1}^{\mathrm{stock,up}}(160)=60}\\ {\theta_{1}^{\mathrm{lend,up}}(1.188)+\theta_{1}^{\mathrm{stock,up}}(142)=42}\end{array}
$$  

Solving for the portfolio weights $\theta_{1}^{\mathrm{lend,up}}$ and $\theta_{1}^{\mathrm{stock,up}}$ , we get  

$$
\begin{array}{c}{{\theta_{1}^{\mathrm{lend,up}}=-84.18}}\\ {{\theta_{1}^{\mathrm{stock,up}}=1}}\end{array}
$$  

Thus, at time $j=1,\ i=\mathrm{up}$ , we need to sell 84.18 units of $B_{t}$ and buy one stock. The behavior of this portfolio in the immediate future will be equal to the future values of $\{C_{2}^{i}\}$ where $i$ denotes the four possible states at $j=2$ . The cost of this portfolio is $C_{1}^{\mathsf{u p}}$ :  

$$
\begin{array}{c}{{C_{1}^{\mathrm{up}}=-84.18(1.1)+140}}\\ {{{}}}\\ {{=47.40}}\end{array}
$$  

Similarly, in order to determine $C_{1}^{\mathrm{{down}}}$ , we first form a replicating portfolio by solving the equations  

$$
\begin{array}{r l}&{\theta_{1}^{\mathrm{lend,down}}(1.26)+\theta_{1}^{\mathrm{stock,down}}(100)=0}\\ &{\theta_{1}^{\mathrm{lend,down}}(1.26)+\theta_{1}^{\mathrm{stock,down}}(84)=0}\end{array}
$$  

which gives  

$$
\begin{array}{c}{\theta_{1}^{\mathrm{lend,down}}=0}\\ {\theta_{1}^{\mathrm{stock,down}}=0}\end{array}
$$  

The cost of this portfolio is zero and hence the option is worthless if we are at $j=1$ , $i=\mathrm{down}$ :  

$$
C_{1}^{\mathrm{{down}}}=0
$$  

Finally, the fair value $C_{0}$ of the option can be determined by finding the initial portfolio weights from  

$$
\begin{array}{c}{{\theta_{0}^{\mathrm{lend}}(1.1)+\theta_{0}^{\mathrm{stock}}(140)=47.40}}\\ {{\theta_{0}^{\mathrm{lend}}(1.1)+\theta_{0}^{\mathrm{stock}}(80)=0}}\end{array}
$$  

We obtain  

$$
\begin{array}{c}{{\theta_{0}^{\mathrm{lend}}=-57.5}}\\ {{{}}}\\ {{\theta_{0}^{\mathrm{stock}}=0.79}}\end{array}
$$  

Thus, we need to borrow 57.5 dollars and then buy 0.79 units of stock at $j=0$ . The cost of this will be the current value of the option:  

$$
\begin{array}{c}{{C_{0}=-57.5+0.79(100)}}\\ {{{}}}\\ {{=21.3}}\end{array}
$$  

This will be the fair value of the option if the exogenously given trees are arbitrage-free.  

Note again the important characteristics of this dynamic strategy.  

1. To determine the current value of the option, we started from the expiration date and used the boundary condition.   
2. We kept adjusting the portfolio weights so that the replicating portfolio eventually matched the final cash flows generated by the option.   
3. Finally, there were no cash injections or cash withdrawals, so that the initial amount invested in the strategy could be taken as the cost of the synthetic.  

# 8.6 SOME IMPORTANT CONDITIONS  

In order for these methods to work, some important assumptions are needed. These are discussed in detail here.  

# 8.6.1 ARBITRAGE-FREE INITIAL CONDITIONS  

The methods discussed in this chapter will work only if we start from dynamics that originally exclude any arbitrage opportunities. Otherwise, the procedures shown will give “wrong” results. For example, some bond prices $B(j,T_{2})^{i},j=0$ , 1 or the option price may turn out to be negative.  

There are many ways the arbitrage-free nature of the original dynamics can be discussed. One obvious condition concerns the returns associated with the savings account and the other constituent asset. It is clear that, at all nodes of the binomial trees in Figure 8.7, the following condition needs to be satisfied:  

$$
R_{j}^{\mathrm{down}}<L_{j}<R_{j}^{\mathrm{up}}
$$  

where $L_{j}$ is the one-period spot rate that is observed at that node and the $R_{j}^{\mathrm{{down}}}$ and $R_{j}^{\mathrm{up}}$ are two possible returns associated with the bond at the same node.  

According to this condition, the risk-free rate should be between the two possible returns that one can obtain from holding the “risky” asset, $B(t,T)$ . For the case of bonds, before expiration we must also have, due to arbitrage,  

$$
R_{j}^{\mathrm{down}}=L_{j}=R_{j}^{\mathrm{up}}
$$  

Otherwise, we could buy or sell the bond, and use the proceeds in the risk-free investment to make unlimited gains.  

Yet, the arbitrage-free characteristic of binomial trees normally requires more than this simple condition. As Chapter 11 will show, the underlying dynamics should be conformable with proper Martingale dynamics in order to make the trees arbitrage-free.  

# 8.6.2 ROLE OF BINOMIAL STRUCTURE  

There is also a very strong assumption behind the binomial tree structure that was used during the discussion. This assumption does not change the logic of the dynamic replication strategy, but can make it numerically more complicated if it is not satisfied.  

Consider Figure 8.7. In these trees, it was assumed that when the short rate dropped, the long rate always dropped along with it. Conversely, when the short rate increased, the long rate increased with it. That is to say, the long bond return and the short rate were perfectly correlated. It is thanks to this assumption that we were able to associate a future value of $B_{t}$ with another future value of $B(t,~T_{3})$ . These “associations” were never random. A similar assumption was made concerning the binomial trees for $S_{t}$ and $C_{t}$ . The movements of these two assets were perfectly correlated.  

This is a rather strong assumption and is due to the fact that we are using the so-called onefactor model. It is assumed that there is a single random variable that determines the future value of the assets under consideration at every node. In reality, given a possible movement in the short rate $L_{t}$ , we may not know whether a bond price $B(t,T)$ will go up or down in the immediate future, since other random factors may be at play. Under such conditions, it would be impossible to obtain the same equations, since the up or down values of the two assets would not be associated with certainty.  

Yet, introducing further random factors will only increase the numerical complexity of the tree models. We can, for example, move from binomial to trinomial or more complicated trees. The general logic of the dynamic replication does not change. However, we may need further base assets to form a proper synthetic.  

# 8.7 REAL-LIFE COMPLICATIONS  

Real-life complications make dynamic replication a much more fragile exercise than static replication. The problems that are encountered in static replication are well known. There are operational problems, counterparty risk, and the theoretically exact synthetics may not be identical to the original asset. There are also liquidity problems and other transaction costs. But, all these are relatively minor and in the end, static replicating portfolios used in practice generally provide good synthetics.  

With dynamic replication, these problems are magnified because the underlying positions need to be readjusted many times. For example, the effect of transaction costs is much more serious if dynamic adjustments are required frequently. Similarly, the implications of liquidity problems will also be more serious. But more important, the real-life use of dynamic replication methods brings forth new problems that would not exist with static synthetics. We study these briefly.  

# 8.7.1 BID ASK SPREADS AND LIQUIDITY  

Consider the simple case of bid ask spreads. In static replication, the portfolio that constitutes the synthetic is put together at time $t$ and is never altered until expiration $T.$ . In such an environment, the existence of bid ask spreads may be non-negligible, but this is hardly a major aspect of the problem. After all, any bid ask spread will end up increasing (or lowering) the cost of the associated synthetic, and in the unlikely case that these are prohibitive, then the synthetic will not be put together.  

Yet, with dynamic replication, the practitioner is constantly adjusting the replicating portfolio. Such a process is much more vulnerable to widening bidask spreads or the underlying liquidity changes. At the time dynamic replication is initiated, the future movements of bid ask spreads or of liquidity will not be known exactly and cannot be factored into the initial cost of the synthetic. Such movements will constitute additional risks and increase the costs even when the synthetic is held until maturity.  

# 8.7.2 MODELS AND JUMPS  

Dynamic replication is never perfect in real life. It is done using models in discrete time. But models imply assumptions and discrete time means approximation. This leads to a model risk. Many factors and the possibility of having jumps in the underlying risks may have serious consequences if not taken into account properly during the dynamic replication process.  

# 8.7.3 MAINTENANCE AND OPERATIONAL COSTS  

It is easy to obtain a dynamic replication strategy theoretically. But in practice, this strategy needs to be implemented using appropriate position-keeping and risk-management tools. The necessary software and human skills required for these tasks may lead to significant new costs.  

# 8.7.4 CHANGES IN VOLATILITY  

Often, dynamic replication is needed because the underlying instruments are nonlinear. It turns out that, in dealing with nonlinear instruments, we will have additional exposures to new and less transparent risks such as movements in the volatility of the associated risk factors. Because risk-managing volatility exposures are much more delicate (and difficult) than the management of interest rate or exchange rate risks, dynamic replication often requires additional skills.  

In the exercises at the end of this chapter, we briefly come back to this point and provide a reading (and some questions) concerning the role of volatility changes during the dynamic hedging process.  

# 8.8 CONCLUSIONS  

We finish the chapter with an important observation. Static replication was best done using cash flow diagrams and resulted in contractual equations with constant weights.  

Creating synthetics dynamically requires constant adjustments and careful selection of portfolio weights ${\theta}_{t}^{i}$ , in order to make the synthetic self-financing. Thus, we again use contractual equations, but this time, the weights placed on each contract change as time passes. This requires the use of algebraic equations and is done with computers.  

Finally, the dynamic synthetic is nothing but the sequence of weights $\{\theta_{1}^{i},\theta_{2}^{i},...,\theta_{n}^{i}\}$ that the financial engineer will determine at time $t_{0}$ .  

# SUGGESTED READING  

Several books deal with dynamic replication. Often these are intermediate-level textbooks on derivatives and financial markets. We have two preferred sources that the reader can consult for further examples. The first is Jarrow (2002). This book deals with fixed-income examples only. The second is Jarrow and Turnbull (1999), where dynamic replication methods are discussed in much more detail with a broad range of applications. The reader can also consult the original Cox and Ross (1976a) article. It remains a very good summary of the procedure.  

# EXERCISES  

1. Consider the immunization example given in Section 8.4. Assume that the zero-coupon yield curve is flat at $y=5\%$ and not $8\%$ as in the example. The shifts in the yield curve are parallel. What positions and how many units of the 6-month bond and the 3-year bond are needed to create an approximate synthetic that will fund the 2-year bond?  

2. Suppose you are given the following data: The risk-free interest rate is $6\%$ . The stock price follows:  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}
$$  

Volatility is $12\%$ a year.   
The stock pays no dividends and the current stock price is 100.  

Using these data, you are asked to approximate the current value of a European call option on the stock. The option has a strike price of 100 and a maturity of 200 days.  

a. Determine an appropriate time interval $\Delta$ , such that an implied binomial tree has five steps.   
b. What is the implied up probability? Hint: To obtain the probability we need to discretize the stochastic differential equation.   
c. Determine the tree for the stock price $S_{t}$ .   
d. Determine the tree for the call premium $C_{t}$ .  

3. Suppose the stock discussed in Exercise 1 pays dividends. Assume all parameters are the same. Consider three forms of dividends paid by the firm:  

a. The stock pays a continuous, known stream of dividends at a rate of $4\%$ per time.   
b. The stock pays $5\%$ of the value of the stock at the third node. No other dividends are paid.   
c. The stock pays a $\$5$ dividend at the third node.  

In each case, determine the tree for the ex-dividend stock price. For the first two cases, determine the premium of the call. In what way(s) does the third type of dividend payment complicate the binomial tree?  

4. You are going to use binomial trees to value American-style options on the British pound. Assume that the British pound is currently worth $\$1.40$ . Volatility is $10\%$ . The current British risk-free rate is $5\%$ , and the US risk-free rate is $2\%$ . The put option has a strike price of $\$1.50$ . It expires in 200 days. American-style options can be exercised before expiration.  

a. The first issue to be settled is the role of US and British interest rates. This option is being purchased in the United States, so the relevant risk-free rate is $2\%$ . But British pounds can be used to earn British risk-free rates. So this variable can be treated as a continuous rate of dividends.  

Taking this into account, determine a $\Delta$ such that the binomial tree has five periods. b. Determine the relevant probabilities. Use a similar method to the one used to value the European stock call option above. c. Determine the tree for the exchange rate. d. Determine the tree for a European put with the same characteristics. e. Determine the price of an American style put with these properties.  

5. Consider the reading that follows which deals with the effects of straightforward delta hedging. Read the events described and then answer the questions that follow.  

Dynamic Hedging  

US equity option market participants were of one voice last week in refuting the notion that [dynamic hedging due to] equity options trading had exacerbated the stock market correction of late October, which saw the Dow Jones Industrial Average fall 554.26 points, or some $7\%$ .  

Dynamic hedging is a strategy in which investors buy and sell stocks to create a payout, which is the same as going long and short options. Thus, if the market takes a big drop, a writer of puts sells stock to cut their losses. Dynamic hedgers buy and sell stock to achieve the position they desire to equalize their exposure to volatility.  

The purpose of dynamic hedging, also known as delta hedging, is to remain marketneutral. The hedger’s objective is to have no directional exposure to the market. For example, the hedgers will buy puts, giving them the right to sell stock. They are thus essentially short the market. To offset this short position, the hedger will purchase the underlying stock. The investor is now long the put and long the stock, and thereby market-neutral.  

If the market falls, the investor’s put goes in-the-money, increasing the short exposure to the market. To offset this, the investor will sell the underlying. . .  

“It is my humble opinion that few investors use dynamic hedging. If somebody is selling options, i.e. selling volatility, they will have an offsetting position where they are long volatility. People don’t take big one-sided bets,” said a senior official at another U.S. derivatives exchange. (Thomson Reuters IFR, issue 832)  

a. Suppose there are a lot of put writers. How would these traders hedge their position? Show using appropriate payoff diagrams.   
b. What would these traders do when markets start falling? Show on payoff diagrams.   
c. Now suppose an option’s trader is short volatility as the last paragraph implies. Describe how this trader can be long volatility “somewhere else.”   
d. Is it possible that the overall market is a bit short volatility, yet that this amount is still very substantial for the underlying (cash) markets?  

There are many special terms in this reading, but at this point we would like to emphasize one important aspect of dynamic hedging that was left unmentioned in the chapter. As mentioned in the reading, in order to dynamically hedge a nonlinear asset, we need a delta.  

Delta is the sensitiveness of the option to underlying price changes. Now if this asset is indeed nonlinear, then the delta will depend on the volatility of underlying risks. If this volatility is itself dependent on many factors, such as the strike price, then there will be a volatility smile and delta hedging may be inaccurate.  

To this effect, suppose you have a long options’ position on FTSE-100. How would you delta hedge this position? More important, how would this delta hedge be affected by the observations in the last paragraph of the reading?  

6. How could you determine whether the trees in Figure 8.7 are arbitrage-free or not?  

7. Consider the replication of a European call option. Write a VBA program to show the dynamic hedging strategy using only stocks and a saving account to replicate a short European option. Calculate the position in both the stock and the savings account for all the intermediate time points and all possible states. Use the binomial model with the following data: • $S(0)=100\$ ; $K=110$ ; $T=3$ ; $\sigma=30\%$ ; $M=3$ • $L(0)=1$ ; $\sigma=5\%$ • Use the value of $u=\mathrm{e}^{(\sigma\sqrt{\Delta t+(r-\sigma^{2}/2)\Delta t})}$ and $d=\mathrm{e}^{(-\sigma\sqrt{\Delta t+(r-\sigma^{2}/2)\Delta t})}$ .  