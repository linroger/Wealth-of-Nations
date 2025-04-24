# DEFAULT CORRELATION PRICING AND TRADING  

# 22  

# CHAPTER OUTLINE  

22.1 Introduction . 782   
22.2 Two Simple Examples... . 782   
22.2.1 Portfolio with three credit names ... . 786   
22.2.1.1 Case 1: Independence... 783   
22.2.1.2 Case 2: Perfect correlation. 785   
22.2.2 Sensitivity of Tranche Spreads and Basket Default Swaps to Default Correlation .. . 786   
22.2.3 Recent Quotation Convention for CDO Tranches and Evolution of Tranche Spreads ..... 787   
22.3 Standard Tranche Valuation Model.. .. 789   
22.3.1 The Gaussian Copula Model . 789   
22.3.2 Implied Correlations 791   
22.3.3 The Central Limit Effect.. 794   
22.4 Default Correlation and Trading.. . 795   
22.5 Delta Hedging and Correlation Trading ... . 796   
22.5.1 How to Calculate Deltas .. 797   
22.5.2 Gamma Sensitivity.. 798   
22.5.3 Correlation Trade and Gamma Gains.. . 798   
22.6 Real-World Complications . 799   
22.6.1 Base Correlations . . 800   
22.6.2 The Dispersion Effect . . 800   
22.6.3 The Time Effect.. 801   
22.6.4 Do Deltas Add Up to One?. . 801   
22.7 Default Correlation Case Study: May 2005.. . 801   
22.8 Conclusions.. . 804   
Suggested Reading . 804   
Appendix 22.1: Some Basic Statistical Concepts .. . 805   
Exercises . 806   
MATLAB Exercises..... 808  

# 22.1 INTRODUCTION  

There are three major issues with the credit sector. First there is the understanding and engineering of the credit risk itself. In other words, how does one strip the default risk component of a bond or a loan and trade it separately? The engineering of a CDS serves this purpose and was done in Chapter 18.  

The second dimension in studying credit risk is the modeling aspect. Without modeling one cannot implement pricing, hedging, and risk management problems. Modeling helps to go from descriptive or graphical discussion to numbers. In credit risk, the modeling has a “novel” component. The risk in question is an event, the default. They are zero-one type random variables and are different than risk factors such as interest rates and stock prices which can be approximated by continuous state stochastic processes.1 Credit risk, being a zero-one event, introduces a new dimensions in modeling.  

The third major dimension of the credit sector has to do with the tranching of default risks. The main point of Chapter 21 was that tranching credit risk can eventually lead to stripping the default correlation. In this chapter, we talk about modeling default correlation and the resulting financial engineering of default correlation. We learn how to strip, hedge, and trade it. The recent correlation market provides the real-world background.  

As we discussed in the previous chapter, banks extended the securitization process to CDOs, CLOs, and other products. The intermediate or mezzanine tranches were sold to investors. The very high-quality tranches, called senior and super senior, were also kept on banks’ books because their implied return was too small for many investors. As a result, the banks found themselves long equity tranche and long senior and super senior tranches. They were short the mezzanine tranche which paid a good return and was rated investment grade. It turns out, as we will see in this chapter, that the equity tranche value is positively affected by the default correlation while the super senior tranche value is negatively affected. The sum of these positions formed the correlation books of the banks. Banks had to learn correlation trading, hedging, and pricing as a result.  

The connection between default correlation and tranche values is a complex one and needs to be clarified step by step. We discuss market examples of how this idea can be exploited in setting up correlation trades and can be exploited in setting up new structured products. The first issue that we need to introduce is the dependence of the tranche pricing on the default correlation.  

# 22.2 TWO SIMPLE EXAMPLES  

We first discuss two simple cases to illustrate the logic of how default correlation movements affect tranche prices. It is through this logic that observed tranche trading can be used to back out the default correlation. This quantity will be called implied correlation.  

# 22.2.1 PORTFOLIO WITH THREE CREDIT NAMES  

Let $n=3$ so that there are only three credit names in the portfolio. With such a portfolio, we can consider only three tranches: equity, mezzanine, and senior. In this simple example, the equity tranche bears the risk of the first default $(0-33\%)$ , the mezzanine tranche bears the risk of the second name defaulting $(33-66\%)$ , and the senior tranche investors bear the default risk of the third default $(66-100\%)$ .  

In general, we follow the same notation as in the previous chapter. As a new parameter, we let $\rho_{t}^{i,j}$ be the default correlation between ith and $j$ th names in the portfolio at time t. $p_{t}^{i}$ is the probability of default and $\mathrm{cds}_{t}^{i}$ is the liquid CDS spread for the ith name, respectively. We make the following assumptions without any loss of generality. The default probabilities for the period $[t_{0},T]$ are the same for all names, and they are constant  

$$
p_{t}^{1}=p_{t}^{2}=p_{t}^{3}=p\quad\mathrm{for~all~}t\in[t_{0},T]
$$  

We also let the recovery rate be constant and be given by $R$ .  

We consider two extreme settings. In the first, default correlation is zero  

$$
\rho^{i,j}=0
$$  

The second is perfect correlation,  

$$
\rho^{i,j}=1
$$  

for all $t\in[t_{0},\ T],\ i,\ j.$ . These two extreme cases will convey the basic idea involved in correlation trading. We study a number of important concepts under these two assumptions. In particular, we obtain (i) default loss distributions, (ii) default correlations, and (iii) tranche pricing in this context.  

Start with the independence case. In general, with $n$ credit names, the probability distribution of $D$ will be given by the binomial probability distribution. Letting $p$ denote the constant probability of default for each name and assuming that defaults are independent, the number of defaults during a period $[t_{0},T]$ will be distributed as  

$$
P(D=k)={\frac{n!}{k!(n-k)!}}p^{k}(1-p)^{n-k}
$$  

Note that there is no $\rho$ parameter in this distribution since the correlation is zero. Now consider the first numerical example.  

# 22.2.1.1 Case 1: Independence  

With $n=3$ there are only four possibilities, $D=\{O,I,2,3\}$ . For zero default, $D={\cal O}$ we have  

$$
P(D=0)=\left(1-p\right)^{3}
$$  

For the remaining probabilities we obtain  

$$
P(D=1)=p(1-p)^{2}+(1-p)p(1-p)+(1-p)^{2}p
$$  

$$
P(D=2)=p^{2}(1-p)+p(1-p)p+(1-p)p^{2}
$$  

$$
P(D=3)=p^{3}
$$  

Suppose $\mathfrak{p}=0.05$ . Plugging in the formulas above we obtain first the probability that no default occurs  

$$
P(D=0)=(1-0.05)^{3}=0.857375
$$  

One default can occur in three different ways:  

$$
\begin{array}{l}{{P(D=1)=(0.05)(1-0.05)(1-0.05)+(1-0.05)(0.05)(1-0.05)+(1-0.05)(1-0.05)(1-0.05)+(1-0.05)(1-0.05)(1-0.05)+}}\\ {{\nonumber}}\\ {{=0.135375~}}\end{array}
$$  

Two defaults can occur again in three ways:  

$$
\begin{array}{l}{{P(D=2)=(0.05)(0.05)(1-0.05)+(0.05)(1-0.05)(0.05)+(1-0.05)(0.05)(0.05)}}\\ {{\nonumber}}\\ {{=0.007125}}\end{array}
$$  

For three defaults there is only one possibility and the probability is  

$$
P(D=3)=(0.05)(0.05)(0.05)=0.000125
$$  

As required, these probabilities sum to one.  

The spreads associated with each tranche can be obtained easily from these numbers. Assume for simplicity that defaults occur only at the end of the year. In order to calculate the tranche spreads we first calculate the expected loss for each tranche under a proper working probability. Then the spread is set so that expected cash inflows equal this expected loss. The expected loss for the three tranches is given by  

$$
\mathrm{Equity}=0[P(D=0)]+1[P(D=1)+P(D=2)+P(D=3)]=0.142625
$$  

$$
\mathbf{Mez}=0[P(D=0)+P(D=1)]+1[P(D=2)+P(D=3)]=0.00725
$$  

$$
\mathrm{Sen}=0[P(D=0)+P(D=1)+P(D=2)]+1[P(D=3)]=0.000125
$$  

In the case of 1-year maturity contracts it is easy to generalize these tranche spread calculations. Let $B(t,T)$ denote the appropriate time- $\cdot t$ discount factor for $\$1$ to be received at time $T.$ . The recovery rate is given by $R$ . Assuming that $N=1$ and that defaults can occur only on date $T_{\mathrm{{:}}}$ the tranche spreads at time $t_{0}$ denoted by $\mathrm{cds}_{t_{0}}^{j},j=e$ , m, $s$ are then given by the following equation,  

$$
0=B(t_{0},T)\big[\mathrm{cds}_{t_{0}}^{e}P(D=0)-\big[(1-R)-\mathrm{cds}_{t_{0}}^{e}\big]P(D\geq1)\big]
$$  

for the equity tranche which is hit with the first default. This can be written as  

$$
{\mathrm{cds}}_{t_{0}}^{e}=(1-R)\times P(D\geq1)
$$  

For the mezzanine tranche we have  

$$
0=B(t_{0},T)\big[\mathrm{cd}s_{t_{0}}^{m}(P(D=0)+P(D=1))-\big[(1-R)-\mathrm{cd}s_{t_{0}}^{m}\big](P(D=2)+P(D=3))\big]
$$  

which gives  

$$
\mathrm{cds}_{t_{0}}^{m}=(1-R)\times\left(P(D=2)+P(D=3)\right)
$$  

Finally, for the senior tranche  

$$
\begin{array}{r}{0=B(t_{0},T)\big[\mathrm{cd}s_{t_{0}}^{m}(P(D=0)+P(D=1)+P(D=2))-\big[(1-R)-\mathrm{cd}s_{t_{0}}^{m}\big]\times P(D=3)\big]}\end{array}
$$  

And we obtain  

$$
\mathrm{cds}_{t_{0}}^{s}=(1-R)\times P(D=3)
$$  

Note that, in general, with $n>3$ and the number of tranches being less than $n$ , there will be more than one possible value for $R$ . One can obtain numerical values for these spreads by plugging in $p=0.05$ and the recovery value $R=40\%$ .  

If we plug in the above values, we obtain the following credit spreads for the different tranches: $\mathrm{cds}_{t_{0}}^{e}=0.085575$ , $\mathrm{cds}_{t_{0}}^{m}=0.00435$ , and $\mathrm{cds}_{t_{0}}^{s}=0.000075$ . As expected the equity tranche is the riskiest and is compensated for this with the highest spread.  

It is interesting to note that for each tranche, the relationship between spreads and probabilities of making floating payments is similar to the relation between cds and $p$ we obtained for a singlename CDS in Chapter 18  

$$
\displaystyle\mathrm{cds}=(1-R)\times p.
$$  

# 22.2.1.2 Case 2: Perfect correlation  

If default correlation increases and $\rho\to I$ then all credit names become essentially the same, restricting default probability to be identical. So let  

$$
p_{t}^{i}=0.05
$$  

for all names and all times $\mathfrak{t}\in\left[\mathfrak{t}_{0}\right.$ , T]. Under these conditions, the probability distribution for D will be trivially given by the distribution.  

$$
\begin{array}{c}{P(D=0)=(1-0.05)=0.95}\\ {P(D=1)\to0}\\ {P(D=2)\to0}\\ {P(D=3)=0.05}\end{array}
$$  

The corresponding expected losses on each tranche can be calculated trivially. The loss is the same for all tranches and is equal to 0.05 if we assume same values for p and R as in Case 1. For the equity trance obtain the following credit spread:  

$$
0=c_{t_{0}}^{e}P(D=0)-\big[(1-R)-c_{t_{0}}^{e}\big](D\geq1)
$$  

$$
\mathbf{cds}_{t_{0}}^{e}=(1-R)\times P(D\geq1)=(1-0.4)(0.05)=0.03
$$  

The mezzanine tranche spread will be  

$$
\mathsf{c d s}_{t_{0}}^{m}=(1-R)\times[P(D=2)+P(D=3)]=(1-0.4)(0.05)=0.03,
$$  

Finally for the senior tranche we have  

$$
\mathsf{c d s}_{t_{0}}^{s}=(1-R)\times[P(D=3)]=(1-0.4)(0.05)=0.03
$$  

We can extract some general conclusions from the examples in cases 1 and 2 above. First of all, as $\rho\to1$ , all three tranche spreads become similar. This is to be expected since under these conditions all names start looking more and more alike. At the limit $\rho=1$ there are only two possibilities, either nobody defaults or everybody defaults. There is no risk to “tranche” and sell separately. There is only one risk.  

Second, we see that as correlation goes from zero to one, the expected loss of equity tranche decreases and the credit spread decreases. The expected loss of the senior tranche and the resulting credit spread, on the other hand, goes up. The mezzanine tranche is somewhere in between: the expected loss and credit spread goes up as correlation increases, but not as much as the senior tranche. In general, the sensitivity of the mezzanine tranche to correlation is dependent on its attachment points and size as well as the current credit spreads.  

![](a57fcbeea63c5f8c4c232e15adfd02f91b6b0158551cb0af9f469ac46f0dcfa6.jpg)  

# FIGURE 22.1  

Tranche premiums as a function of default correlation.  

Fourth, the expected loss of the portfolio is independent of the correlation. The loss is 0.15 in both cases if we add up the losses across the three tranches. However, the correlation determines how the expected losses are allocated across the different parts of the capital structure.  

# 22.2.2 SENSITIVITY OF TRANCHE SPREADS AND BASKET DEFAULT SWAPS TO DEFAULT CORRELATION  

Finally, note that as default correlation went up the distribution became more skewed with the “two” tails becoming heavier at both ends. In Chapter 21, we saw how the default distribution and portfolio loss distribution depend on the default correlation. Figure 22.1 is based on a hypothetical portfolio and illustrates that the tranche premium is a function of correlation and tranche subordination. The tranche premium is highest for the equity tranche for all levels of correlation. This reflects the fact that the equity tranche has no subordination and is the first to suffer losses. The senior tranche is protected by the subordination of the equity and mezzanine tranches and therefore it has the lowest risk. The line representing the equity tranche shows that as default correlation increases the equity tranche premium falls. The opposite is true if default correlation increases. For the senior tranche, the premium increases as the default correlation increases. For the mezzanine tranche, the relationship between default correlation and tranche premium is generally sensitivity to several parameters but in this illustrative example we assume that it decreases with default correlation. This is also what a comparison of cases 1 and 2 in the numerical example above revealed.  

Note that the above example can also be interpreted as a basket default swap instead of an application of tranche pricing. A basket default swap differs from a single-name default swap in that the underlying is a basket of entities rather than one single entity. Examples of popular basket default swaps are first-to-default, n-th-to-default, n-out-of-m-to-default, and all-to-default swaps. In a single-name credit default swap, a credit event is usually a default of the entity. In the example there were three assets or names, and we calculated the spreads on the first-to-default, second-todefault, and third-to-default swaps. Thus the price of synthetic CDO tranches depends on default correlations in a similar way as a basket default swap. In a synthetic CDO, the underlying assets are CDS while in a cash CDO the underlying assets are bonds. As the CDO market evolved, single-tranche trading was developed. This refers to the trading of CDO tranches without the underlying portfolio of short CDS positions being created.  

# 22.2.3 RECENT QUOTATION CONVENTION FOR CDO TRANCHES AND EVOLUTION OF TRANCHE SPREADS  

The simplified example illustrated how the spreads of different tranches depend on the default correlation. Figure 22.1 illustrated this point using a hypothetical portfolio. Before we look at a real-world example of how (iTraxx Europe) tranche spreads have moved recently, we need to note that after the CDS Big Bang in 2009 CDS contracts were standardized and the quotation of the tranches changed. Until April 2009, all iTraxx tranches except for the equity tranche $(0-3\%)$ quoted in basis points with no fixed running spread. In other words, no money was exchanged upfront. The equity tranche, however, consisted of an upfront fee with a fixed 500 bps spread and was quoted in terms of percentage of notional. After April 2009, the quotation of tranches changed and since then the equity $(0-3\%)$ and mezzanine tranches $(3-6\%,6-9\%)$ consist of upfront fees with a fixed 500 bps spread and are quoted in terms of percentage of notional. The $9-12\%$ and the senior $12-22\%$ tranche continue to be quoted in basis points with no fixed running spread.  

Therefore we will examine the years from 2007 until 2009 in Figure 22.2a and b first before discussing the years 2010 2013 which are reported in Figure 22.2c and d. As we see in Figure 22.2a and b, all tranche spreads increased significantly during the GFC from 2007 until 2009. The mezzanine $6\mathrm{-}9\%$ tranche spread rose from 11.95 bps on January 31, 2007 to 606.69 bps on January 30, 2009. This represents a more than 60-fold increase. All other tranches also increased significantly. There are many factors that can explain these changes, but two of them are related to the default probability and the default correlation. As market participants revised upwards their view of the default probability all tranche spreads should increase. In crisis times, correlations also increase which, however, as we saw in the examples in the previous section have a different impact on different tranches. As we would expect there is some evidence that proportionately spreads on mezzanine and senior tranches have gone up more than the spread on the equity tranche.  

Some commentators have laid partial blame for the severity of the GFC on the Gaussian copula model use in the pricing of CDO backed by MBS. However, it is important to note that the limitations of the model were pointed out by practitioners and academics before the crisis. Moreover, laying blame on the model for mispricing the tranches and CDOs is akin to a trader laying blame for option losses that he or she suffered after using historical implied volatilities to price options before being surprised by an unexpected increase in implied volatility. Option prices and tranche prices  

![](ef838956da8de1a70341035e373a7fdd7b148558344dd8f6626673dff94156ec.jpg)  
(a) Equity $(0-3\%)$ tranche in 2007–2009 (in %)  

![](11d7b0f7244bbbe6a871e36e77614fe852d874ee90010e9b1228fa3186aea3d5.jpg)  
(c) Equity and mezzaine tranches in 2010–2013 (in %)  

![](5ca301396377296cba2d5792f33aaadd4b7a7d82d89adec4e3282bd31e6cfc8b.jpg)  
(b) Mezzanine and senior tranches in 2007–2009 (in bps)  

![](9595074f34116e4e6f7a0bba37e016e205757e5aaacddbaff6c0b1481ff670ad.jpg)  
(d) Mezzanine and senior tranches in 2010–2013 (in bps)  

# FIGURE 22.2  

Tranche spreads during 2007 2013.  

can move unexpectedly as market participants revise their expectations. The cause of the losses can be found with the users of the models. Even the brief discussion here highlights the limitations of the models. More refined models are constantly being developed but as we pointed out repeatedly in the book, models are just an approximation of reality and often serve as a communication tool or benchmark, but reality is significantly more complex than the models’ assumptions make it out to be. Buyers and sellers of derivatives must understand the products that they trade and structurers of products must take care to explain products to clients and make sure that the products are suitable for their clients. This applies to all products and services and not just derivatives or structured products.  

Figure $22.2\mathrm{c}$ and d shows that tranche spread volatility decreased in the years 2010 2013. Figure 22.2c reports the new quotation conventions.2 For the $0-3\%$ equity tranche, the quotation on January 29, 2010, was $28.81\%$ (in terms of percentage of notional). Since the tranche has a fixed coupon of $500\mathrm{{bps}}$ , there is an upfront payment at initiation. The amount paid upfront is equal to the present value of the difference between the current market spread and the fixed coupon. Since the contract has a fixed coupon of 500 bps but is trading at 2881 bps $(28.81\%)$ , the protection buyer would make an upfront payment equal to the present value of the difference between 2881 and 500 bps. The figure shows that for some of the spread the market spread is lower than the fixed coupon in which case the protection seller would have to pay the difference between the two spreads upfront. In 20102013, tranche spreads have increased somewhat but the relative magnitude of the increase was smallest for the equity tranche and most pronounced for the senior and mezzanine $9-12\%$ tranches. If we ignore technical factors and changes in liquidity, then we could interpret the movements in tranche prices over this period as being consistent with an increase in the perception of the default probability and the default correlation. The comovement of the different tranches suggests that there is some reversion to the mean. If a trader observed a divergence in tranche spreads, he or she could set up a position that bets on convergence due to the observed comovement of tranches over longer periods of time.  

Our discussion related to Figure 22.2 here is heuristic and does not represent a rigorous analysis of tranche spread drivers since the main goal is to illustrate the dependence of tranches on default correlation.  

# 22.3 STANDARD TRANCHE VALUATION MODEL  

We now show how the distribution of $D$ can be calculated under correlations different than 0 and 1. We discuss the standard market model for pricing standard tranches for a portfolio of $n$ names.  

# 22.3.1 THE GAUSSIAN COPULA MODEL  

This model is equivalent to the so-called Gaussian copula model, in a one factor setting. Let  

$$
\{S^{j}\},\quad j=1,...,n
$$  

be a sequence of latent variables. Their role is to generate statistically dependent zero-one variables.3 There is no model of a random variable that can generate dependent zero-one random variables with a closed-form density or distribution function. $\{\boldsymbol{S}^{j}\}$ are used in a Monte Carlo approach to do this.  

It is assumed that $S^{j}$ follows a normal distribution and that the default of the ith name occurs the first time $S^{j}$ falls below a threshold denoted by $L_{\alpha}$ , where $a$ is the jth name’s default probability. The important step is the way $S^{j}$ is structured. Consider the following one factor case,  

$$
S^{j}=\rho^{j}F+\sqrt{1-(\rho^{j})^{2}}\in^{j}
$$  

where $F$ is a common latent variable independent of $\in^{j},\rho^{j}$ is a constant parameter, and $\in^{j}$ is the idiosyncratic component. The random variables in this setup have some special characteristics. $F$ has no superscript, so it is common to all $\begin{array}{r}{S^{j},j=1}\end{array}$ , . . ., $n$ and it has a standard normal distribution. $\in^{j}$ are specific to each $i$ and are also distributed as standard normal,  

$$
\begin{array}{l}{\epsilon^{j}\sim N(0,1)}\\ {F\sim N(0,1)}\end{array}
$$  

Finally, the common factor and the idiosyncratic components are uncorrelated.  

$$
E[\in^{j}F]=0
$$  

It turns out that $\in^{j}$ and $F$ may have any desired distribution.4 If this distribution is assumed to be normal, then the model described becomes similar to a Gaussian copula model. Note this case is in fact a one factor latent variable model.  

We obtain the mean and variance of a typical $S^{j}$ as follows  

$$
\begin{array}{r l}&{E[S^{j}]=\rho E[F]+E\bigg[\sqrt{1-(\rho^{2}}\in^{j}\bigg]}\\ &{~=0}\end{array}
$$  

and  

$$
\begin{array}{c}{{E[(S^{j})^{2}]=\rho^{2}E[F^{2}]+E[(1-\rho^{2})(\in^{j})^{2}]}}\\ {{=1+\rho^{2}-\rho^{2}=1}}\end{array}
$$  

since both random variables on the right side have zero mean and unit second moment by assumption and since $F$ is uncorrelated with $\in^{j}.$ . The model above has an important characteristic that we will use in stripping default correlation. It turns out that the correlation between defaults can be conveniently modeled using the common factor variable and the associated $\rho^{i}$ . Calculate the correlation  

$$
\begin{array}{r l}&{E[S^{j}S^{k}]=E\Big[\rho F+\sqrt{1-\rho^{2}}\epsilon^{j}\Big]\Big[\rho F+\sqrt{1-\rho^{2}}\epsilon^{k}\Big]}\\ &{\qquad=\rho^{2}E[F^{2}]+E[2(1-\rho^{2})\epsilon^{j}\epsilon^{i}]+E\Big[\rho\sqrt{(1-\rho^{2})}\epsilon^{j}F\Big]+E\Big[\rho\sqrt{(1-\rho^{2})}\epsilon^{i}F\Big]}\end{array}
$$  

This gives  

$$
\mathrm{Corr}[S^{i}S^{j}]=\rho^{i}\rho^{j}
$$  

The case where  

$$
\rho^{i}\rho^{j}
$$  

for all $i,j$ , is called the compound correlation and is the market convention. The compound default correlation coefficients is then given by $\rho^{2}$ . The ith name default probability is defined as  

$$
p^{i}=P\Big(\Big(\rho F+\sqrt{1-\rho^{2}\in^{i}}\Big)\leq L_{\alpha}\Big)
$$  

The probability is that the value of $S^{i}$ will fall below the level $L_{\alpha}$ . Remember that in Chapter 19 we introduced Merton’s (1974) structural model of default where the default occurs when the value of the firm falls below the debt issued by the firm. Hence, at first glance, it appears that the market convention here is similar to Merton’s model. This is somewhat misleading, however, since $S^{i}$ has no structural interpretation here. It will be mainly used to generate correlated binomial variables.  

This above setup provides an agenda one can follow to price and hedge the tranches. It will also help us to back out an implied default correlation once we observe liquid tranche spreads in the market.  

The agenda is as follows: First, observe the CDS rate $\mathrm{cds}_{t}^{i}$ for each name in the markets. Using this, calculate the risk-neutral default probability $p^{i}$ . Using this find the corresponding $L_{\alpha}^{i}$ . Generate pseudo-random numbers for $F$ and $\in^{i}$ . Next, assume a value for $\rho$ and calculate the implied $S^{i}$ . Check to see if the value of $S^{i}$ obtained this way is less than $L_{\alpha}^{i}$ . This way, obtain a simulated default process:  

$$
d^{i}={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S^{i}<L_{\alpha}}\\ {0}&{{\mathrm{otherwise}}}\end{array}\right.}
$$  

Finally calculate the number of defaults for the trial as  

$$
D=\sum_{i=1}^{n}d^{i}
$$  

Repeating this procedure $m$ times will yield $m$ replicas of the random variable $D$ . If $m$ is large, we can use the resulting histogram as the default loss distribution on the $n$ reference names and then calculate the spreads for each tranche.  

# 22.3.2 IMPLIED CORRELATIONS  

The valuation of synthetic CDO tranches follows similar principles as the valuation of CDS described in Chapter 18. The break-even spread on a tranche is defined as the spread that sets the present value of the payments equals the present value of the payoffs of the tranche. The present value depends on the cash flows, the probability of receiving the cash flows and a discount factor. This is again analogous to the valuation of the single-name CDS. What is different in CDO tranche valuation is that now we have multiple underlying assets and the probability of cash flows must take into account the correlation structure between cash flows. This is what the standard market model described above achieves by using a Gaussian copula model specification. The standard Gaussian copula market model can be used in a similar way as the Black Scholes model which is the standard market model in option markets. We used the Black Scholes model to either calculate theoretical option prices based on given input parameters or to back out implied volatilities given observed market option prices. In the standard (Gaussian copula) market model, we can use default probabilities as input parameters and determine tranche spreads or we can start with market observed tranche spreads and calculate the implied probabilities.5 Since we are using the standard market model, the default loss distribution will depend on a certain level of default correlation due to the choice of $\rho_{\mathrm{-}}$ . The implied correlation is that level of $\rho$ which yields a calculated tranche spread that equals the observed spread in the markets. The coefficient $\rho$ is the only unknown variable if we observe tranche spreads.  

![](bf9212c19d603afadff1f685f966bc001f8849d0ee1135776ebed243e290946b.jpg)  
Compound correlation  

# FIGURE 22.3  

Compound correlation.  

The reason why market participants prefer to quote implied correlation instead of the market spread directly is that correlation is independent of the overall spread level of the underlyings. This is similar to the market practice in option markets where implied volatilities instead of option prices are quoted.  

It is common in the market to imply a correlation from market quotes for tranches. The correlation that if plugged into the standard model results in the spreads observed in the market is called the compound correlation or tranche correlation. In other words, the compound correlation is the correlation found by calibrating the Gaussian copula model to the price of a CDO tranche. The implied default correlation $\rho$ is the correlation that, given the observed market spread, sets the present value of the two legs of a CDO tranche equal to zero. Figure 22.3 shows a typical compound correlation plot. It shows the compound correlation for different tranches. Similar to equity markets, where the Black Scholes model leads to implied volatility skews, smiles, or frowns, the Gaussian copula approach to model the expected loss in a given tranche leads to different correlations. The compound correlations exhibit a typical correlation skew or correlation smile. With increasing tranche seniority, the implied correlation first decreases and then increases.  

We observe that the implied compound correlation for the mezzanine tranche is lower than for the senior and equity tranches. This dip in correlations reflects the fact that the market assigns a higher price to the risk of losses in senior tranches than predicted by the Gaussian copula model compared to the equity tranche. In other words, the market view is that defaults tend to cluster as they become more frequent.  

One of the limitations of compound correlations is that for some (mezzanine) tranches, the tranche correlation is not uniquely defined and may not even exist. These computation issues imply that the implied correlation is conceptually different from implied volatility. We will see in Section 22.6 how so-called base correlations address this issue.  

Below we have a simple example that shows this process.  

# EXAMPLE  

Let $n=3$ . Assume that the default probability is $1\%$ ; and let the default correlation be $\rho^{2}=0.36$ . We generate 10,000 replicas for each $\{\boldsymbol{S}^{1},\boldsymbol{S}^{2},\boldsymbol{S}^{3}\}$ using  

$$
\begin{array}{c}{{S^{1}=0.25F+\sqrt{64}\in^{1}}}\\ {{{}}}\\ {{S^{2}=0.25F+\sqrt{64}\in^{2}}}\\ {{{}}}\\ {{S^{3}=0.25F+\sqrt{64}\in^{3}}}\end{array}
$$  

For example, we select four standard pseudo-random variables  

$$
\begin{array}{l}{F=-1.12615}\\ {\ }\\ {\in^{1}=-2.17236}\\ {\ }\\ {\in^{2}=0.64374}\\ {\ }\\ {\in^{3}=-0.326163}\end{array}
$$  

Using these we obtain $S^{i}$ as  

$$
\begin{array}{l}{S^{1}=-2.41358}\\ {S^{2}=-0.160698}\\ {S^{3}=-0.936621}\end{array}
$$  

We then calculate the corresponding $S^{j}$ and see if they are less than $L_{\cdot01}=-2.32$ , where the latter is the threshold that gives a $1\%$ tail probability in a standard normal distribution.  

If $S^{1}<-2.32$ , $S^{2}<-2.32$ , $\boldsymbol{S}^{3}<-2.32$ , then we let the corresponding $d^{i}=1$ . Otherwis they are zero. We then add the three $\boldsymbol{d}^{i}$ to get the $D$ for that Monte Carlo run.  

In this particular case, $d^{1}=1$ , $d^{2}=0$ , $d^{\bar{3}}=0$ . So the first Monte Carlo run gives $D=1$ .  

Next we would like to show an example dealing with implied correlation calculations. The example again starts with a Monte Carlo sample on the $D$ , obtains the tranche spreads, then extends this to three functions, calculated numerically, that show the mapping between tranche spreads and correlation.  

# EXAMPLE: IMPLIED CORRELATION  

Suppose we are given a Monte Carlo sample of correlated defaults from a reference portfolio,  

$$
\mathrm{Sample}=\{D_{1},...,D_{m}\}
$$  

Then, we can obtain the histogram of the number of defaults.  

Assume $\rho=0.3$ , $n=100$ , and $m=1000$ . Running the procedure above we obtain 1000 replicas of $D_{i}$ . We can do at least two analyses with the distribution of $D$ . First we can calculate the fair value of the tranches of interest. For example, with recovery $40\%$ and zero interest rates, we can compute the value of the equity tranche in this case as  

$$
\boldsymbol{\mathrm{s}}^{e}=[0.05(0)+0.12(33.33)0.6+0.15(66)0.6+(1-0.05-0.12-0.15)]0.6=0.68
$$  

This 1-year spread is based on the fact that the party that sells protection with nominal $N=100$ on the first three defaults will lose nothing if there are no defaults, will lose a third of the investment if there is one default, will lose two-thirds if there are two defaults, and finally will lose all investments if there are three defaults.  

Repeating this for all values of $\rho^{2}\in[0,1]$ we can get three surfaces. These graphs plot the value of the equity, mezzanine, and senior tranches against the fair value of the tranche.  

Note that the value of the equity tranche goes up as correlation increases. The value of the mezzanine tranche is a $U.$ -shaped curve, whereas the value of the senior tranche is again monotonic. The end of chapter exercises provide another numerical example.  

# 22.3.3 THE CENTRAL LIMIT EFFECT  

Why does the default loss distribution change as a function of the correlation? This is an important technical problem that has to do with the central limit theorem and the assumptions behind it. Now define the correlated zero-one stochastic process $z_{i}$ :  

$$
z_{j}={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S^{j}\leq L_{\alpha}}\\ {0}&{{\mathrm{otherwise}}}\end{array}\right.}
$$  

Next calculate a sum of these random variables as  

$$
Z^{n}=\sum_{j=1}^{n}z^{j}
$$  

According to the central limit theorem, even if $z^{j}$ are individually very far from being normally distributed and are correlated, then the distribution of the sum will approach a normal distribution if the underlying processes have finite means and variances as in $n\to\infty$ .  

$$
\frac{\sum_{i}^{n}z_{i}-\sum_{i}^{n}\mu_{i}}{\sqrt{\sum_{i}^{n}\sigma_{i}^{2}}}\rightarrow N(\mu^{d},\sigma^{d})
$$  

Thus if we had a very high number of names in the reference portfolio, the distribution of $D$ will look like normal. On the other hand, with finite $n$ and highly correlated $z^{j}$ , this convergence effect will be slow. The higher the “correlation” $\rho$ , the slower will the convergence be. In particular, with $n$ around 100, the distribution of the $D$ will be heavily dependent on the size of $\rho$ and will be far from normal. This is where the relationship between Index tranches and correlation comes in. In the extreme case when correlation is perfect, the sum will involve the same $z^{j}$ .  

# 22.4 DEFAULT CORRELATION AND TRADING  

Correlation impacts risk assessment and valuation of CDO tranches. Each tranche value reflects correlation in a different way. Perhaps the most interesting correlation relationship is shown in the equity $(0-3\%)$ tranche. This may first appear counterintuitive. It turns out that the higher the correlation, the lower the equity tranche risk, and the higher the value of the tranche. The reasoning behind this is as follows. Higher correlation makes extreme cases of very few defaults more likely. Everything else being the same, the more correlation, the lower the risk the investor takes on and the lower premium the investor is going to receive over the lifetime of the tranche.6  

The influence of default correlation on the mezzanine tranche is not as clear. In fact, the value of the mezzanine tranche is less sensitive to default correlation. For the senior tranches, higher correlation of default implies a higher probability that losses will wipe out the equity and mezzanine tranches and inflict losses on the senior tranche as well. Thus, as default correlation rises, the value of the senior tranche falls. A similar reasoning applies to the super senior tranche.  

Correlation trading is based on this different dependence of the tranche spreads on default correlation. One of the most popular trades of 2004 and the first half of 2005 was to sell the equity tranche and hedge the default probability movements (i.e., the market risk) by going long the mezzanine index.  

This is a long correlation trade and it had significant positive carry.7 The trade also had significant (positive) convexity exposure. In fact, as the position holder adjusts the delta hedge, the hedging gains would lead to a gain directly tied to index volatility. Finally, if the carry and convexity are higher, the position’s exposure to correlation changes will be higher.  

A long correlation position has two major risks that are in fact related. First, if a single-name credit event occurs, long correlation positions would realize a loss. This loss will depend on the way the position is structured and will be around $5-15\%$ . The recovery value of the defaulted bonds will also affect this number.  

Second, a change in correlation will lead to mark-to-market gains and losses. In fact, the change in correlation is equivalent to markets changing their view on an idiosyncratic event happening. A rule of thumb that can be used is that a 100 basis point drop in correlation will lead to a change in the value of a delta-hedged equity tranche by around $1\%$ . For short equity tranche protection, long mezzanine tranche protection position this loss would be even larger. This means that the position may suffer significant mark-to-market losses if expected correlation declines. Sometimes these positions need to be liquidated.  

A market participant can go  

long correlation by going either long the equity tranche or short the senior tranche. short correlation by going either short the equity tranche or long the senior tranche.  

Note that the sensitivity to correlation can change through time since it depends on several variables, underlying spreads, number of defaults, and time decay.  

# 22.5 DELTA HEDGING AND CORRELATION TRADING  

The delta is the sensitivity of the individual tranche spreads toward movements in the underlying index, $I_{t}$ .8  

Let the tranche spreads at time $t$ be denoted by $\operatorname{cds}_{t}^{j}$ , $j=e$ , m, s, sup. The superscript represents the equity, mezzanine, senior, and super senior tranches, respectively. There will then be (at least) two variables affecting the tranche spread: the probability of default and the default correlation. Let the average probability of default be denoted by $p_{t}$ and the compound default correlation be $\rho_{t}.$ . We can write the index spread as a function of these two variables.  

$$
\mathrm{cds}^{i}=f^{i}(p_{t},\rho_{t})
$$  

It is important to remember that with changes in $p_{t}$ the sign of the sensitivity is the same for all tranches. As probability of default goes up, the tranche spreads will all go up, albeit in different degrees. The sensitivities with respect to the index (or probability of default) will be given by  

$$
\Delta^{i}=\frac{\hat{\partial}\mathrm{c}\mathrm{ds}_{t}^{i}}{\hat{\partial}I_{t}}>0
$$  

for all $i.$ . These constitute the tranche deltas with respect to the index itself. It is natural, given the evel of subordination in higher seniority tranches, to find that  

$$
\Delta^{e}>\Delta^{m}>\Delta^{s}>\Delta^{\mathrm{sup}}
$$  

Yet, the correlation sensitivity of the tranches is very different. As discussed earlier, even the sign changes.  

$$
\frac{\hat{\sigma}\mathrm{cds}^{e}}{\hat{\sigma}\rho}<0
$$  

$$
\frac{\hat{\sigma}\mathrm{cds}^{m}}{\hat{\sigma}\rho}\cong0
$$  

$$
\frac{\hat{\sigma}\mathrm{cds}^{s}}{\hat{\sigma}\rho}>0
$$  

$$
\frac{\partial{\mathrm{cds}^{\mathrm{sup}}}}{\partial\rho}>0
$$  

According to this, the equity protection seller benefits if the compound default correlation goes up. The super senior protection seller loses under these circumstances. The middle tranches are more or less neutral.  

Suppose the market participant desires to take a position positively responsive to $\rho_{t}$ but more or less neutral toward changes in $p_{t}$ . This is clearly a long correlation exposure discussed earlier. How would one put such a correlation trade on in practice? To do this the market practitioner would use the delta of the tranches with respect to the index. The position will consist of two hedging efforts.  

First, the right amounts of the equity and mezzanine tranches have to be purchased so that the portfolio is immune to changes in the default correlation. Second, each tranche should be hedged separately with respect to the changes in the index, as time passes.  

Let $N^{e}$ and $N^{m}$ be the two notional amounts. $N^{e}$ is exposure on equity, while $N^{m}$ is the exposure on the mezzanine tranche. What we want is a change in the index to not lead to a change in the total value of the position on these two tranches.  

Thus the portfolio $\boldsymbol{P}_{t}$ will consist of selling default protection by the new amount  

$$
P_{t}=N^{e}-N^{m}
$$  

we let  

$$
N^{m}=\lambda N^{e}
$$  

where $\lambda$ is the hedge ratio to be selected. Substituting we obtain  

$$
P_{t}=N^{e}-\lambda_{t}N^{e}
$$  

$\textstyle\bigwedge_{t}$ is the hedge ratio selected as  

$$
\lambda_{t}=\frac{\Delta_{t}^{e}}{\Delta_{t}^{m}}
$$  

With this selection, the portfolio value will be immune to changes in the index value at time $t.$ :  

$$
\frac{\partial}{\partial I_{t}}P_{t}=\frac{\partial}{\partial I_{t}}N^{e}-\frac{\partial}{\partial I_{t}}N^{m}
$$  

Replacing from Eq. (22.67)  

$$
\frac{\hat{\sigma}}{\hat{\sigma}I_{t}}P_{t}=\Delta^{e}-\frac{\Delta^{e}}{\Delta^{m}}\Delta^{m}=0.
$$  

Hence the portfolio of selling $N^{E}$ units of equity protection and buying simultaneously ${\bf\nabla}\backslash{N^{E}}$ units of the mezzanine protection is delta hedged. As the underlying index moves, the portfolio would be neutral to the first order of approximation. Also, as the market moves, the hedge ratio $\textstyle\bigwedge_{t}$ would change and the delta hedge would need to be adjusted. This means that there will be gamma gains (losses).  

# 22.5.1 HOW TO CALCULATE DELTAS  

In the Black Scholes world, deltas and other sensitivity factors are calculated by taking the appropriate derivatives of a function. This is often not possible in the credit analysis. In the case of tranche deltas, the approach is one of numerical calculation of sensitivity factors or of obtaining closed-form solutions by approximations.  

One way is to use the Monte Carlo approach and one factor latent variable model to generate a sample $\{S_{i}^{j}\}$ and then determine the tranche spread. These results would depend on an initially assumed index spread or default probability. To obtain delta one would divide the original value of the index by an amount $\Delta I$ and then repeat the valuation exercise. The difference in tranche spread divided by $\Delta I$ will provide a numerical estimate for delta.  

# 22.5.2 GAMMA SENSITIVITY  

Volatility in the spread movements is an important factor. Actively managing delta positions suggest that there may be gamma gains. The gamma effect seems to be most pronounced in the equity and senior tranches. There exist differences in gamma exposures depending on the particular tranche.  

Unlike options, one can distinguish three different types of gamma in the credit sector.  

• Gamma is defined as the portfolio convexity corresponding to a uniform relative shift in all the underlying CDS spreads. iGamma is the individual gamma defined as the portfolio convexity resulting from one CDS spread moving independently of the others; i.e., one spread moves and the others remain constant. nGamma is the negative gamma defined as the portfolio convexity corresponding to a uniform relative shift in underlying CDS spreads, with half of the credits widening and half of the credits tightening by a uniform amount.  

Delta-hedged investors who are long correlation, benefiting if the correlation increases, will be long gamma while being short iGamma and nGamma.  

# 22.5.3 CORRELATION TRADE AND GAMMA GAINS  

Suppose one expects the compound default correlation to go up. This would be advantageous to the equity tranche protection seller and more or less neutral toward the mezzanine protection seller.10 Thus, one would take a long correlation exposure by selling $N^{e}$ units of equity protection while simultaneously buying $N^{m}$ units of mezzanine exposure. The latter notional amount is determined according to  

$$
N^{m}=\lambda N^{e}
$$  

What would be the gains from such a position? What would be the risks? First, consider the gains.  

It turns out that such long correlation positions have positive carry, meaning that, even if the anticipated change in correlation does not materialize and the status quo continues, the position holder will make money. In fact, historically this positive carry was significant at around 200 350 bp depending on the prevailing levels of the index $I_{t}$ and of the correlation $\rho_{t}.$  

The position will also have positive gamma gains. As the delta hedge is adjusted, the hedge adjustments will monetize the $I_{t}$ volatility because the long correlation position has, in fact, positive convexity with respect to $I_{t}$ . In addition, the position will gain if the correlation goes up as expected.  

The risks are related to iGamma effects and to the declining correlation. In both cases the position will suffer some losses, although these may not be big enough to make the overall return negative.  

Below we see an example of the gamma gains and dynamic delta hedging.  

# EXAMPLE: DELTA HEDGING AND GAMMA GAINS  

We are given the following information concerning iTraxx Index quotes $(I_{t})$ and the deltas of the equity and mezzanine tranches at various levels of $I.$ For example if the index is at 30 bps, the equity tranche delta is 18.5, whereas the mezzanine tranche delta is 8.9.  

$I_{t}$ Delta of 0 3 Tranche Delta of 0 6 Tranche   


<html><body><table><tr><td>18.5</td><td></td></tr><tr><td>30 bps</td><td>8.9</td></tr><tr><td>35 bps 17.6</td><td>9.4</td></tr><tr><td>40 bps 15.1</td><td>10.1</td></tr></table></body></html>  

Now we use these to generate a dynamically adjusted series of delta hedges. Suppose we observe the following index movements across 3 days  

$$
I_{1}=30,I_{2}=40,I_{3}=30
$$  

And suppose our notional is $N=100$ . Then a long correlation position will sell 100 units of equity protection and hedge this with $18.5/8.9\times100=207.865$ units of mezzanine protection.  

The resulting position will be delta neutral with respect to changes in $I$ .  

During day 2, initially the position is not delta neutral since $I_{t}$ has moved to $40\mathrm{bps}$ . The correct hedge ratio is smaller at $15.1/10.1=4.6.$ The investor needs to reduce the long protection position on $I_{t}$ by $[(18.5-8.9)-(15.1-10.1)]\times100\$ .  

During day 3, this position reverts back to the original position on the index.  

Look what happened as a result of dynamic delta hedging of the tranche portfolio using the index. The investor sold protection when $I_{t}$ widened and bought it back when $I_{t}$ tightened. Clearly, these will lead to convexity gains similar to the case of options or long bonds.  

# 22.6 REAL-WORLD COMPLICATIONS  

The discussion of how to model and value tranche spreads has been a very simplified one. Realworld trading has several complications and also requires further modeling effort. Several additional questions also need to be addressed. We briefly discuss them below.  

![](5a974500cec1416750fee9872ce215caf16c84f4bcc0b4efe9b4f4b5602138bf.jpg)  

# FIGURE 22.4  

Base correlation.  

# 22.6.1 BASE CORRELATIONS  

The calculation of the implied compound correlation leads to the correlation smile in Figure 22.3. One of the issues is that the implied (compound) correlations can sometimes not be unique or may not even exist in mezzanine tranches. To address the issue of the nonmonotonicity of the mezzanine tranche, it became market practice to quote in another correlation, the base correlation, in addition to the compound correlation.  

The intuition behind the base correlation approach is relatively simple. The approach consists of transforming tranche quotes into quotes for equity tranches with increasing attachment points.11 The procedure to calculate base correlations in this way is referred to as a bootstrapping process and is outlined by McGinty et al. (2004). Base correlation will also give a skew, but this skew will always exist and be unique (see Figure 22.4). One of the additional advantages of base correlations is that one can interpolate correlations to detachment points for which no market tranches exist. For these reasons, Bloomberg quotes iTraxx tranches in terms of base correlations and tranche spreads and not compound correlations.  

# 22.6.2 THE DISPERSION EFFECT  

The dispersion effect refers to how different individual spreads are from the index spread. For example, if individual CDS spreads are more or less the same as the overall index spread, then we say that there is low dispersion.  

The dispersion of individual CDS spreads in the portfolio versus the spread of the portfolio itself is an important factor influencing the tranche valuation. The effect varies with individual tranches. For the equity tranche, the higher the dispersion of spreads the higher the number of basis points. This is due to the increased riskiness of the tranche. In the mezzanine tranche, the lower the dispersion, the higher the number of bps indicating increased risk. The results of senior and super senior tranches are similar to the mezzanine.  

# 22.6.3 THE TIME EFFECT  

Time is also a variable affecting the tranche spreads. As the time to maturity gets shorter, tranche values tend to decline. In other words, the tranche spread curves are, in general, upward sloping.  

# 22.6.4 DO DELTAS ADD UP TO ONE?  

Suppose there are two tranches and only two names in the reference portfolio. We can define two tranches: the equity tranche and, say, the senior tranche. Can we say that the deltas of the entire reference portfolio weighted by tranche size should sum to one?  

Suppose one default occurs. If we sold protection on the index itself, the index spread we would receive in the future would stay the same. However, a weighted average of tranche spreads would be significantly affected, since with the first default equity protection the seller would receive no further premiums. And, it turns out that the equity tranche spreads would be the highest.  

This effect is due to the fact that tranche spreads are unevenly distributed whereas the index has a single spread. With the first default, the high spread tranche is triggered and the average spread of the remaining tranche portfolio decreases significantly. Clearly, if all tranches and the index traded on an upfront basis this effect would disappear.  

# 22.7 DEFAULT CORRELATION CASE STUDY: MAY 2005  

During May 2005, credit markets witnessed an intriguing event which looked like a puzzle and created a significant amount of discussion as to the correctness of the credit markets’ standard models. The events are worth reviewing briefly since they are a good example of the way cash derivatives markets influence each other in the newly developing credit markets.  

Essentially, the May 2005 events were triggered by General Motors and Ford being downgraded by rating agencies. These credits that had massive amounts of debt were investment grade and were downgraded to speculative grade, which meant that many institutional players would be prevented from holding them in their portfolios. The ensuing sales led to significant credit volatility in credit markets.  

The biggest volatility happened in CDX and iTraxx tranche markets, since several players anticipating these events had put long correlation trades in place. The following IFR report shows the series of events as they happened in May 2005.  

# EXAMPLE: MAY 2005 EVENTS  

Speculation about losses in the hedge fund industry sent a shudder through credit markets earlier this month. Fund managers were wrong-footed by going long on the equity piece of synthetic CDOs, while funding that position by shorting the mezzanine tranche on the view that spreads would move in the way predicted by their correlation assumptions.  

This positive carry trade was popular with banks and hedge funds because the trade made money if spreads of the related pieces moved in a parallel fashion, as well as creating a hedge against large losses.  

The risk was exposure to unexpected default in the portfolio, but with default rates at historic lows, investors were happy to assume this risk.  

The ratings downgrade on GM and Ford, which are often included in these CDO structures because they are such large issuers of debt, made the banks change their outlook on default rates and prompted them to begin unwinding massive correlation books.  

While equity spreads jumped higher, those on the mezzanine tranches headed in the other direction, ensuring these trades significantly underperformed. As a result, investors suffered on both legs of the trade.  

Initially, the underperformance was most acutely felt in the United States, however, during the last couple of weeks the European market has been hit by hedge fund unwinding of iTraxx CDO tranche trades. It is estimated that between 20 and 30 hedge funds executed correlation trades in Europe.  

“Selling is a result of the negative returns that these types of trades have generated in the US recently,” said a European credit strategist.  

The iTraxx spreads should not be affected by the sell-off in correlation positions. “Fundamentally, a risk re-distribution between different tranches, as reflected by a change in correlation, should have a very limited effect on the underlying market,” said a credit strategist. However, from a sentimental point of view the impact was much more significant and the rush to unwind the same trade caused massive volatility in the DJ iTraxx crossover index last week.  

The index ballooned to $475\mathrm{bp}$ in 5 years from 330 bp the previous week.  

However, hedge funds putting on large shorts in a widening market coupled with a rally in US treasuries caused a violent snap back in the index to 380 bp towards the end of the week.  

Attention also turned last week to the banking sector and the size of potential losses. Most of the fall-out will be felt in London and the United States where the majority of international banks keep their correlation books, whereas Asia is less exposed.  

That is partly because synthetic tranching of purely Asian credit has not really taken off. Facilitating the interest in structured credit products in Europe and the United States has been the development and liquidity of the credit default swap indices; they have given transparency to implied correlation in those markets. Not so in Asia, where the regional indices have not proved hugely popular, there has been even less take-up of index tranching.  

The end of June is critical for the high-yield market because most funds have quarterly liquidity, and there is the threat of huge redemptions. Many are unwinding positions in expectation that clients will redeem their cash.  

We can now study this case in more detail. According to the series of events, the status quo before the volatility was as follows.  

Several hedge funds and bank proprietary trading desks were long correlation, meaning that they had sold protection on the equity tranche by a notional amount $N^{E}$ and bought protection on the mezzanine tranche by a notional amount $N^{M}$ . These two notional amounts were related to each other according to  

$$
\begin{array}{r}{N_{t}^{M}=\lambda_{t}N^{E}}\end{array}
$$  

where $\textstyle\bigwedge_{t}$ is the hedge ratio selected so that the sensitivity of the portfolio to movements in the underlying index, or, in average default probability $\boldsymbol{P}_{t}$ is approximately zero. Letting $\boldsymbol{V}^{E}$ and $V^{M}$ represent the value of the $\$1$ invested in the equity and mezzanine tranches, respectively, we can write the value  

$$
\frac{\partial}{\partial p_{t}}\left[N^{E}V_{t}^{E}-\lambda N^{E}V_{t}^{M}\right]=0
$$  

These positions were taken with the view that the compound default correlation coefficient denoted by $\rho_{t}$ would go up. Since we had  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{E}>0
$$  

and  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{M}\cong0
$$  

The position would benefit as correlation increased,  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{E}-\frac{\partial}{\partial\rho_{t}}V_{t}^{M}>0
$$  

in fact, as the reading above indicates, with the GM and Ford downgrades the reverse happened. One possible explanation of the May 2005 events is as follows.12 As GM and Ford were downgraded, the equity spreads increased and $V_{t}^{E}$ decreased, which led to a sudden collapse of the default correlation. Meanwhile, the mezzanine spreads decreased and $V_{t}^{M}$ increased. This meant severe mark-to-market losses of the long correlation trades  

$$
\frac{\partial}{\partial\rho_{t}}V_{t}^{E}-\frac{\partial}{\partial\rho_{t}}V_{t}^{M}<0
$$  

since both legs of the trades started to have severe mark-to-market losses.  

The dynamics of the tranche spreads observed during May 2005 contradicted what the theoretical models implied. The observed real-world relationships had the opposite sign of what the market standard models would imply. What was the reason behind this puzzle?  

One explanation is, of course, the models themselves. If the market convention used the “wrong” model then it is natural that sometimes the real-world development would contradict the model predictions. This is possible, but we know of no satisfactory new theoretical model that would explain the observed discrepancy at that time.  

There is, on the other hand, a plausible structural explanation of the puzzle and it relates to the cash CDO market. Over the years, starting from the mid-1990s, banks had sold mezzanine tranches of cash CDOs (the banks were paying mezzanine spreads). Some of these positions could have been unhedged. As GM and Ford were downgraded, and as these names were heavily used in cash CDOs, the banks who were short the mezzanine tranche tried to cover these positions in the index market. This means that they had to sell protection on the mezzanine index tranche.13 It is plausible that this dynamic created a downward spiral where the attempt to hedge the cash mezzanine position via selling mezzanine protection in the index market resulted in even further mezzanine spread tightening.  

At the same time, since the correlation trade had gone in the opposite direction, hedge funds tried to close their position in the equity tranche. They were selling equity protection before, but closing the position meant buying equity protection and such a rush by institutions would create exactly the type of dynamic observed at that time. The equity spreads increased and the mezzanine spreads declined and, at the end, correlation declined. The downgrade by GM and Ford had created the opposite effect.  

# 22.8 CONCLUSIONS  

In this chapter, we have discussed the dependence of tranche spreads on default correlation in detail and explained how default correlation can be traded. We have applied the standard market model in the form of the Gaussian copula model and highlighted real-world complications. Similar to other model-based trading strategies that we discussed in previous chapters, we explained how correlation trading positions can be delta hedged and how gamma gains arise for such strategies.  

# SUGGESTED READING  

The best references to continue with the discussion given in this chapter are handbooks and reports prepared by broker-dealers themselves. We recommend the JP Morgan’s Credit Derivatives Handbook (2007), the two-volume Merrill Lynch set published in 2006 and the Credit Suisse (2007) Handbook on Credit Risk Modeling. Francis et al. (2003) is a good reference for correlation trading. The 2004 JP Morgan credit correlation guide is a good introduction to correlation, the difference between compound and base correlations and their relative merits. Brigo et al. (2010) provide a good account of credit models and CDOs during and after the GFC while Schonbucher (2004) and Duffie and Singleton (2002) are earlier academic approaches.  

# APPENDIX 22.1: SOME BASIC STATISTICAL CONCEPTS  

Consider again the table discussed in the text, shown below, which gives the joint distribution of two random variables.  

This simple table is an example of marginal and joint distribution functions associated with the two random variables $d^{\boldsymbol{A}}$ , $d^{B}$ representing the default possibilities for the two references named $A$ , $B$ , respectively.  

It is best to start the discussion with a small credit portfolio, then generalize to the, say, iTraxx index. Suppose we have an equally weighted CDS portfolio of $n=2$ names denoted by $j=A$ , $B$ . We are interested in a horizon (i.e., maturity) of 1 year. According to this, there are two random variables $d^{\boldsymbol{A}}$ and ${\bf d}^{\bf B}$ , each representing the credits $j=A$ and $j=B$ . The $\dot{d^{\prime}}$ assumes the value of 1 if the $j$ th name defaults, otherwise it is equal to 0.  

Suppose the probabilities of default by $A$ and $B$ are given as in the table below.  

<html><body><table><tr><td></td><td>A Defaults (dA = 1)</td><td>A Survives (dA = 0)</td><td>Sum of Rows</td></tr><tr><td>B Defaults (dβ = 1)</td><td>0.02</td><td>0.03</td><td>0.05</td></tr><tr><td>B Survives (dB = 0)</td><td>0.01</td><td>0.94</td><td>0.95</td></tr><tr><td>Sum of columns</td><td>0.03</td><td>0.97</td><td>1</td></tr></table></body></html>  

Now we can discuss the most relevant point concerning this table. If the default-related random variables $d^{\boldsymbol{A}}$ and $d^{B}$ were independent, then we would have  

$$
\begin{array}{c}{{p^{11}=(1-p^{A})(1-p^{B})}}\\ {{{}}}\\ {{p^{22}=(p^{A})(p^{B})}}\\ {{{}}}\\ {{p^{12}=(1-p^{A})(p^{B})}}\\ {{{}}}\\ {{p^{21}=(p^{A})(1-p^{B})}}\end{array}
$$  

Otherwise, if any of these conditions were not satisfied, then the default random variables would be correlated. In this particular case, a quick calculation would reveal that none of these conditions are satisfied. For example for $\boldsymbol{p}^{11}$ we have  

$$
p^{11}=0.02\neq p^{A}p^{B}=0.0015
$$  

As a matter of fact, the joint probability of default is more than 10 times greater than the simple-minded (and in this case, wrong) calculation by simple multiplication of individual default probabilities.  

Let us calculate the expected values, variances, and covariances of the two random variables $d^{\boldsymbol{A}}$ and $d^{B}$ . For the expected values  

$$
\begin{array}{l}{{E[d^{A}]=1p^{A}+0(1-p^{A})=p^{A}}}\\ {{\ =0.03}}\end{array}
$$  

$$
\begin{array}{l c r}{{E[d^{B}]=1p^{B}+0(1-p^{A})=p^{B}}}\\ {{\ }}\\ {{\qquad=0.05}}\end{array}
$$  

For the variances, we have  

$$
\begin{array}{r}{E[(d^{A}-E[d^{A}])^{2}]=(1-p^{A})^{2}p^{A}+(0-p^{A})^{2}(1-p^{A})=(1-p^{A})p^{A}}\\ {=(0.03)(0.97}\end{array}
$$  

$$
\begin{array}{r}{E[(d^{B}-E[d^{B}])^{2}]=(1-p^{B})^{2}p^{B}+(0-p^{B})^{2}(1-p^{B})=(1-p^{B})p^{B}}\\ {=(0.05)(0.95\lvert}\end{array}
$$  

Finally, the more important moment, the covariance between $d^{\boldsymbol{A}}$ and $d^{B}$ is given by  

$$
\begin{array}{c}{{E[(d^{B}-E[d^{B}])(d^{A}-E[d^{A}])]=(1-p^{B})(1-p^{A})p^{11}+(0-p^{B})(0-p^{A})p^{22}}}\\ {{+(1-p^{B})(0-p^{A})p^{12}+(1-p^{A})(0-p^{B})p^{21}}}\end{array}
$$  

where $p^{i k}$ is the joint probability that the corresponding events happen jointly. Remember that we must have  

$$
p^{11}+p^{12}+p^{21}+p^{22}=1
$$  

To convert this into a correlation, we need to divide this by the square root of the variances of $d^{\boldsymbol{A}}$ and $d^{B}$ .  

# EXERCISES  

1. Explain the difference between a cash CDO and a synthetic CDO?   
2. What is the difference between compound correlation and base correlation?   
3. We consider a reference portfolio of three investment grade names with the following 1-year CDS rates: $c(1)=116$ $c(2)=193$ $c(3)=140$ The recovery rate is the same for all names at $R=40$ . The notional amount invested in every CDO tranche is $\$1.50$ . Consider the questions: a. What are the corresponding default probabilities? b. How would you use this information in predicting actual defaults? c. Suppose the defaults are uncorrelated. What is the distribution of the number of defaults during 1 year? d. How much would a $0\mathrm{-}66\%$ tranche lose under these conditions? e. Suppose there are two tranches: $0\mathrm{-}50\%$ and $50{\mathrm{-}}100\%$ . How much would each tranche pay over a year if you sell protection? f. Suppose all CDS rates are now equal and that we have $c(1)=c(2)=c(3)=100$ . Also, all defaults are correlated with a correlation of one. What is the loss distribution? What is the spread of the $0\mathrm{-}50\%$ tranche?  

4. We consider a reference portfolio of four investment grade names with the following 1-year CDS rates:  

$\begin{array}{l}{c(1)=14}\\ {c(2)=7}\\ {\operatorname{c}(3)=895}\\ {c(4)=33}\end{array}$   
The recovery rate is the same for all names at $R=30\%$ .   
The notional amount invested in every CDO tranche is $\$1.00$ . Consider the questions:  

a. What are the corresponding annual default probabilities?  

b. Suppose the defaults are uncorrelated, what is the distribution of the number of defaults during 1 year?   
c. Suppose there are three tranches: $0{-}50\%$ $50-75\%$ $75-100\%$ How much would each tranche pay over a year?  

d. Suppose the default correlation becomes 1, and all CDS rates are equal at $60~\mathrm{bp}$ , answer questions (a)(c) again. e. How do you hedge the risk that the probability of default will go up in the equity tranche?  

5. We consider a reference portfolio of three investment grade names with the following 1-year CDS rates: $c(1)=15$ $c(2)=11$ $c(3)=330$ The recovery rate is the same for all names at $R=40$ . The notional amount invested in every CDO tranche is $\$1.50$ . Consider the questions: a. What are the corresponding default probabilities? b. How would you use this information in predicting actual defaults? c. Suppose the defaults are uncorrelated. What is the distribution of the number of defaults during 1 year? d. How much would a $0\mathrm{-}66\%$ tranche lose under these conditions? e. Suppose there are two tranches: $0\mathrm{-}50\%$ and $50-100\%$ . How much would each tranche pay over a year if you sell protection? f. Suppose all CDS rates are now equal and that we have $c(1)=c(2)=c(3)=100$ . Also, all defaults are correlated with a correlation of one. What is the loss distribution? What is th spread of the $0\mathrm{-}50\%$ tranche?  

6. Explain the following position using appropriate graphs. In particular, make sure that you define a barbell in credit sector. Finally, in what sense is this a convexity position?  

1008 GMT [Dow Jones] LONDON—SG recommends selling 7-year $0-3\%$ tranche protection versus 5-year and 10-year $0-3\%$ protection. 7-year equity correlation tightened versus 5-year and 10-year last year.  

SG’s barbell plays a steepening of the 7-year bucket, as well as offering positive roll down, time decay, and jump to default.  

7. (May 2005 Crisis) What was the effect of the 2005 downgrade of General Motors and Ford on the credit market. What was the effect on default correlations and correlation trading positions?  

# MATLAB EXERCISES  

8. (Default Loss Distribution) Building on the tranche valuation model outlined in the text, write a MATLAB program to model the sensitivity of the default loss distribution of a portfolio consisting of 100 names/underlyings to changes in default correlation (ρ). Assume that the default probability (p) of each of the portfolio constituents is the same and equal to $5\%$ . Take 100 numbers of latent variables to carry out the simulations and interpret the results.   
9. (Correlation swaps and equity option implied correlation) In this chapter, we drew an analogy between tranche implied default correlations and implied volatilities and implied correlations in equity option markets. Equity correlation trading was discussed in Chapter 16. One approach to trading correlations is by means of a correlation swap. a. Explain how a synthetic equity correlation swap on the S&P500 or S&P100, for example, can be created. What are the similarities and differences between trading default correlation and equity option implied correlation? b. Download stock return and option data and calculate the implied and realized correlation for the index over the 2004 2013 period. c. Comment on the evolution of the so-called correlation risk premium, that is the difference between the implied and realized correlation. d. Are correlation swaps an attractive investment? What are the caveats?  