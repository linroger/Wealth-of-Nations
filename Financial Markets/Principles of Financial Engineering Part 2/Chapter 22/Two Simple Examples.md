---
tags:
  - '#basket_default_swap'
  - '#cdo_tranches'
  - '#credit_default_swap'
  - '#default_correlation'
  - '#equity_tranche'
  - '#gfc_2007_2009'
  - '#mezzanine_tranche'
  - '#senior_tranche'
  - '#tranche_pricing'
  - '#tranche_spreads'
---
# 22.2 TWO SIMPLE EXAMPLES  

We first discuss two simple cases to illustrate the logic of how default correlation movements affect. tranche prices. It is through this logic that observed tranche trading can be used to back out the default correlation. This quantity will be called implied correlation..  

# 22.2.1 PORTFOLIO WITH THREE CREDIT NAMES  

Let $n=3$ so that there are only three credit names in the portfolio. With such a portfolio, we can consider only three tranches: equity, mezzanine, and senior. In this simple example, the equity tranche bears the risk of the first default $(0-33\%)$ , the mezzanine tranche bears the risk of the second name defaulting $(33-66\%)$ , and the senior tranche investors bear the default risk of the third default $(66-100\%)$  

In general, we follow the same notation as in the previous chapter. As a new parameter, we let $\rho_{t}^{i,j}$ be the default correlation between ith and. $j$ th names in the portfolio at time t. $p_{t}^{i}$ is the probability of default and. $\mathrm{cds}_{t}^{i}$ is the liquid CDS spread for the ith name, respectively. We make the following assumptions without any loss of generality. The default probabilities for the period $[t_{0},T]$ are the same for all names, and they are constant  

$$
p_{t}^{1}=p_{t}^{2}=p_{t}^{3}=p\quad\mathrm{for~all}~t\in[t_{0},T]
$$  

We also let the recovery rate be constant and be given by $R$  

We consider two extreme settings. In the first, default correlation is zerc  

$$
\rho^{i,j}=0
$$  

The second is perfect correlation,  

$$
\rho^{i,j}=1
$$  

for all $t\in[t_{0},T],i,j.$ These two extreme cases will convey the basic idea involved in correlation. trading. We study a number of important concepts under these two assumptions. In particular, we obtain (i) default loss distributions, (ii) default correlations, and (iii) tranche pricing in this. context.  

Start with the independence case. In general, with $n$ credit names, the probability distribution of $D$ will be given by the binomial probability distribution. Letting. $p$ denote the constant probability of default for each name and assuming that defaults are independent, the number of defaults during a period $[t_{0},T]$ will be distributed as  

$$
P(D=k)=\frac{n!}{k!(n-k)!}p^{k}(1-p)^{n-k}
$$  

Note that there is no. $\rho$ parameter in this distribution since the correlation is zero. Now consider the first numerical example.  

# 22.2.1.1 Case 1: Independence  

With $n=3$ there are only four possibilities, $D=\{0,l,2,3\}$ . For zero default, $D=0$ we have  

$$
P(D=0)=(1-p)^{3}
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

Suppose $\ensuremath{\mathbf{p}}=0.05$ Plugging in the formulas above we obtain first the probability that no default occurs  

$$
P(D=0)=(1-0.05)^{3}=0.857375
$$  

One default can occur in three different ways:  

$$
\begin{array}{r l}&{P(D=1)=(0.05)(1-0.05)(1-0.05)+(1-0.05)(0.05)(1-0.05)+(1-0.05)(1-0.05)(0.05)(1-0.05)}\ &{\qquad=0.135375}\end{array}
$$  

Two defaults can occur again in three ways:  

$$
\begin{array}{l}{P(D=2)=(0.05)(0.05)(1-0.05)+(0.05)(1-0.05)(0.05)+(1-0.05)(0.05)(0.05)}\ {=0.007125}\end{array}
$$  

For three defaults there is only one possibility and the probability is  

$$
P(D=3)=(0.05)(0.05)(0.05)=0.000125
$$  

As required, these probabilities sum to one.  

The spreads associated with each tranche can be obtained easily from these numbers. Assume. for simplicity that defaults occur only at the end of the year. In order to calculate the tranche spreads we first calculate the expected loss for each tranche under a proper working probability. Then the spread is set so that expected cash inflows equal this expected loss. The expected loss for the three tranches is given by.  

$$
\mathrm{Equity}=0[P(D=0)]+1[P(D=1)+P(D=2)+P(D=3)]=0.142625
$$  

$$
\mathrm{Mez}=0[P(D=0)+P(D=1)]+1[P(D=2)+P(D=3)]=0.00725
$$  

$$
\mathrm{Sen}=0[P(D=0)+P(D=1)+P(D=2)]+1[P(D=3)]=0.000125
$$  

In the case of 1-year maturity contracts it is easy to generalize these tranche spread calculations. Let $B(t,T)$ denote the appropriate time- $t$ discount factor for $\$1$ to be received at time $T.$ The recovery rate is given by $R$ Assuming that $N=1$ and that defaults can occur only on date $T_{:}$ the tranche spreads at time $t_{0}$ denoted by $\mathrm{cds}_{t_{0}}^{j},j=e$ , m, $s$ are then given by the following equation,  

$$
0=B(t_{0},T)\big[\mathrm{cds}_{t_{0}}^{e}P(D=0)-\big[(1-R)-\mathrm{cds}_{t_{0}}^{e}\big]P(D\geq1)\big]
$$  

for the equity tranche which is hit with the first default. This can be written as  

$$
\mathrm{cds}_{t_{0}}^{e}=(1-R)\times P(D\geq1)
$$  

For the mezzanine tranche we have  

$$
0=B(t_{0},T)\bigl[\mathrm{cds}_{t_{0}}^{m}(P(D=0)+P(D=1))-\bigl[(1-R)-\mathrm{cds}_{t_{0}}^{m}\bigr](P(D=2)+P(D=3))\bigr]
$$  

which gives  

$$
\mathrm{cds}_{t_{0}}^{m}=(1-R)\times(P(D=2)+P(D=3))
$$  

Finally, for the senior tranche  

$$
0=B(t_{0},T)\big[\mathrm{cds}_{t_{0}}^{m}(P(D=0)+P(D=1)+P(D=2))-\big[(1-R)-\mathrm{cds}_{t_{0}}^{m}\big]\times P(D=3)\big]
$$  

And we obtain  

$$
\mathrm{cds}_{t_{0}}^{s}=(1-R)\times P(D=3)
$$  

Note that, in general, with $n>3$ and the number of tranches being less than. $n$ , there will be. more than one possible value for $R$ One can obtain numerical values for these spreads by plugging in $p=0.05$ and the recovery value $R=40\%$  

If we plug in the above values, we obtain the following credit spreads for the different tranches: $\mathrm{cds}_{t_{0}}^{e}=0.085575$ $\mathrm{cds}_{t_{0}}^{m}=0.00435$ and $\mathrm{cds}_{t_{0}}^{s}=0.000075$ As expected the equity tranche is the riski-. est and is compensated for this with the highest spread..  

It is interesting to note that for each tranche, the relationship between spreads and probabilities of making floating payments is similar to the relation between cds and $p$ we obtained for a singlename CDS in Chapter 18  

$$
\operatorname{cds}=(1-R)\times p.
$$  

# 22.2.1.2 Case 2: Perfect correlation  

If default correlation increases and $\rho\to I$ then all credit names become essentially the same, restricting default probability to be identical. So let  

$$
p_{t}^{i}=0.05
$$  

for all names and all times. $\mathrm{t}\in\left[\mathrm{t}_{0}\right]$ T]. Under these conditions, the probability distribution for D will be trivially given by the distribution..  

$$
\begin{array}{c}{{P(D=0)=(1-0.05)=0.95}}\ {{P(D=1)\to0}}\ {{P(D=2)\to0}}\ {{P(D=3)=0.05}}\end{array}
$$  

The corresponding expected losses on each tranche can be calculated trivially. The loss is the same for all tranches and is equal to O.05 if we assume same values for p and R as in Case 1. For the equity trance obtain the following credit spread:  

$$
0=c_{t_{0}}^{e}P(D=0)-\left[(1-R)-c_{t_{0}}^{e}\right](D\geq1)
$$  

$$
\mathrm{cds}_{t_{0}}^{e}=(1-R)\times P(D\geq1)=(1-0.4)(0.05)=0.03
$$  

The mezzanine tranche spread will be  

$$
\mathrm{cds}_{t_{0}}^{m}=(1-R)\times[P(D=2)+P(D=3)]=(1-0.4)(0.05)=0.03
$$  

Finally for the senior tranche we have  

$$
\mathrm{cds}_{t_{0}}^{s}=(1-R)\times[P(D=3)]=(1-0.4)(0.05)=0.03
$$  

We can extract some general conclusions from the examples in cases 1 and 2 above. First of all, as $\rho\to1$ , all three tranche spreads become similar. This is to be expected since under these conditions all names start looking more and more alike. At the limit $\rho=1$ there are only two possibilities, either nobody defaults or everybody defaults. There is no risk to "tranche' and sell separately. There is only one risk.  

Second, we see that as correlation goes from zero to one, the expected loss of equity tranche decreases and the credit spread decreases. The expected loss of the senior tranche and the resulting credit spread, on the other hand, goes up. The mezzanine tranche is somewhere in between: the expected loss and credit spread goes up as correlation increases, but not as much as the senior tranche. In general, the sensitivity of the mezzanine tranche to correlation is dependent on its attachment points and size as well as the current credit spreads.  

![](images/9774c290fa655de2a5e8a44c7dc3ce13f7b27c5ccc069d9658d5cfe4cb351671.jpg)  

# FIGURE 22.1  

Tranche premiums as a function of default correlation.  

Fourth, the expected loss of the portfolio is independent of the correlation. The loss is O.15 in. both cases if we add up the losses across the three tranches. However, the correlation determines how the expected losses are allocated across the different parts of the capital structure..  

# 22.2.2 SENSITIVITY OF TRANCHE SPREADS AND BASKET DEFAULT SWAPS TO DEFAULT CORRELATION  

Finally, note that as default correlation went up the distribution became more skewed with the "two' tails becoming heavier at both ends. In Chapter 21, we saw how the default distribution and portfolio loss distribution depend on the default correlation. Figure 22.1 is based on a hypothetical portfolio and illustrates that the tranche premium is a function of correlation and tranche subordination. The tranche premium is highest for the equity tranche for all levels of correlation. This reflects the fact that the equity tranche has no subordination and is the first to suffer losses. The senior tranche is protected by the subordination of the equity and mezzanine tranches and therefore it has the lowest risk. The line representing the equity tranche shows that as default correlation increases the equity tranche premium falls. The opposite is true if default correlation increases. For the senior tranche, the premium increases as the default correlation increases. For the mezzanine tranche, the relationship between default correlation and tranche premium is generally sensitivity to several parameters but in this illustrative example we assume that it decreases with default correlation. This is also what a comparison of cases 1 and 2 in the numerical example above revealed.  

Note that the above example can also be interpreted as a basket default swap instead of an application of tranche pricing. A basket default swap differs from a single-name default swap in that the underlying is a basket of entities rather than one single entity. Examples of popular basket default swaps are first-to-default, n-th-to-default, n-out-of-m-to-default, and all-to-default swaps. In a single-name credit default swap, a credit event is usually a default of the entity. In the example there were three assets or names, and we calculated the spreads on the first-to-default, second-todefault, and third-to-default swaps. Thus the price of synthetic CDO tranches depends on default correlations in a similar way as a basket default swap. In a synthetic CDO, the underlying assets are CDS while in a cash CDO the underlying assets are bonds. As the CDO market evolved, single-tranche trading was developed. This refers to the trading of CDO tranches without the underlying portfolio of short CDS positions being created.  

# 22.2.3 RECENT QUOTATION CONVENTION FOR CDO TRANCHES AND EVOLUTION OF TRANCHE SPREADS  

The simplified example illustrated how the spreads of different tranches depend on the default correlation. Figure 22.1 illustrated this point using a hypothetical portfolio. Before we look at a real-world example of how (iTraxx Europe) tranche spreads have moved recently, we need to note that after the CDS Big Bang in 2009 CDS contracts were standardized and the quotation of the tranches changed. Until April 2009, all iTraxx tranches except for the equity tranche. $(0-3\%)$ quoted in basis points with no fixed running spread. In other words, no money was exchanged upfront. The equity tranche,. however, consisted of an upfront fee with a fixed 500 bps spread and was quoted in terms of percentage of notional. After April 2009, the quotation of tranches changed and since then the equity $(0-3\%)$ and mezzanine tranches $(3-6\%,6-9\%)$ consist of upfront fees with a fixed 500 bps spread and are quoted in terms of percentage of notional. The $9-12\%$ and the senior $12-22\%$ tranche continue to be quoted in basis points with no fixed running spread..  

Therefore we will examine the years from 2007 until 2009 in Figure 22.2a and b first before discussing the years 2010-2013 which are reported in Figure 22.2c and d. As we see in Figure 22.2a and b, all tranche spreads increased significantly during the GFC from 2007 until 2009. The mezzanine $6-9\%$ tranche spread rose from 11.95 bps on January 31, 2007 to 606.69 bps on January 30, 2009. This represents a more than 60-fold increase. All other tranches also increased significantly. There are many factors that can explain these changes, but two of them are related to the default probability and the default correlation. As market participants revised upwards their view of the default probability all tranche spreads should increase. In crisis times, correlations also increase which, however, as we saw in the examples in the previous section have a different impact on different tranches. As we would expect there is some evidence that proportionately spreads on mezzanine and senior tranches have gone up more than the spread on the equity tranche.  

Some commentators have laid partial blame for the severity of the GFC on the Gaussian copula model use in the pricing of CDO backed by MBs. However, it is important to note that the limitations of the model were pointed out by practitioners and academics before the crisis. Moreover, laying blame on the model for mispricing the tranches and CDOs is akin to a trader laying blame for option losses that he or she suffered after using historical implied volatilities to price options before being surprised by an unexpected increase in implied volatility. Option prices and tranche prices  

![](images/04828f1dcbb36b53b344eb858578cfac52b6638a25b727af8bfb26c83bc2ba12.jpg)  
(a) Equity $(0-3\%)$ tranche in 2007-2009 (in %)  

![](images/c307dd8439f9683c3894846f4748eda18d44c5ff6007c3bfef26e5eb77060d06.jpg)  
(c) Equity and mezzaine tranches in 2010-2013 (in %)  

![](images/a45f9894d358c746b14d2b0ea02fbdb8d84672e8a40dd60c40b227dda09c1e1f.jpg)  
(b) Mezzanine and senior tranches in 2007-2009 (in bps)  

![](images/056ceb307380a1604a0cdd41ffe54acdfe0b4b4e5550c4105907b3c95b20b361.jpg)  
(d) Mezzanine and senior tranches in 2010-2013 (in bps)  

# FIGURE 22.2  

Tranche spreads during 2007-2013.  

can move unexpectedly as market participants revise their expectations. The cause of the losses can be found with the users of the models. Even the brief discussion here highlights the limitations of the models. More refined models are constantly being developed but as we pointed out repeatedly in the book, models are just an approximation of reality and often serve as a communication tool or benchmark, but reality is significantly more complex than the models' assumptions make it out to be. Buyers and sellers of derivatives must understand the products that they trade and structurers of products must take care to explain products to clients and make sure that the products are suitable for their clients. This applies to all products and services and not just derivatives or structured products.  

Figure $22.2\mathrm{c}$ and d shows that tranche spread volatility decreased in the years 2010-2013.. Figure 22.2c reports the new quotation conventions.? For the $0-3\%$ equity tranche, the quotation on January 29, 2010, was $28.81\%$ (in terms of percentage of notional). Since the tranche has a fixed. coupon of $500~\mathrm{bps}$ , there is an upfront payment at initiation. The amount paid upfront is equal to. the present value of the difference between the current market spread and the fixed coupon. Since the contract has a fixed coupon of 500 bps but is trading at 2881 bps. $(28.81\%)$ , the protection buyer would make an upfront payment equal to the present value of the difference between 2881 and 500 bps. The figure shows that for some of the spread the market spread is lower than the fixed coupon in which case the protection seller would have to pay the difference between the two spreads upfront. In 2010-2013, tranche spreads have increased somewhat but the relative magni-. tude of the increase was smallest for the equity tranche and most pronounced for the senior and. mezzanine $9-12\%$ tranches. If we ignore technical factors and changes in liquidity, then we could. interpret the movements in tranche prices over this period as being consistent with an increase in the perception of the default probability and the default correlation. The comovement of the differ-. ent tranches suggests that there is some reversion to the mean. If a trader observed a divergence in. tranche spreads, he or she could set up a position that bets on convergence due to the observed. comovement of tranches over longer periods of time..  

Our discussion related to Figure 22.2 here is heuristic and does not represent a rigorous analysis. of tranche spread drivers since the main goal is to illustrate the dependence of tranches on default correlation.  
