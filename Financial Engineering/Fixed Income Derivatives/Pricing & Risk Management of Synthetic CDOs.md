---
tags:
  - credit_risk
  - default_modeling
  - risk_management
  - synthetic_cdos
  - tranche_pricing
aliases:
  - CDO Risk Analysis
  - Synthetic CDO Pricing
  - Synthetic Collateralized Debt Obligations
key_concepts:
  - Joint default distribution
  - Model parameter sensitivities
  - Reference asset correlations
  - Synthetic CDO structures
  - Tranche expected losses
---

# Pricing & Risk Management of Synthetic CDOs

# Abstract

The purpose of this paper is to analyze the risks of synthetic CDO structures and their  sensitivity to model parameters.  In order to measure these sensitivities, I also introduce  the latest techniques in the pricing and risk management of synthetic CDOs.  I show how  to model the conditional and unconditional default distributions of a typical synthetic deal  using a simple mathematical framework.  Strictly speaking, the findings of this paper are  only directly applicable to synthetic structures, however; many of the modeling and riskmanagement insights discussed apply to structures involving a waterfall.
# Introduction

The purpose of this paper is to introduce the latest techniques in the pricing and risk  management of synthetic CDOs and measure the risks and model sensitivities of a typical  synthetic deal.  Although these techniques are only directly applicable to synthetic  structures, many of the modeling and risk-management insights discussed in the paper  apply to structures involving a waterfall.

A synthetic collateralized debt obligation, synthetic CDO, is made up of a portfolio of  credit default swaps.  The arranger of a synthetic CDO distributes the credit risk of the  portfolio by creating and selling tranches to investors.  Every tranche has an attachment  and detachment point that determines the amount of loss, and correspondingly the  number of defaults, the tranche can absorb.  For example, the first tranche, known as the  equity tranche, might be responsible for portfolio credit losses between   $0\%$   and   $3\%$  , the  next tranche would then be responsible for portfolio losses that exceed   $3\%$   up to the size  of the tranche, and so on.  The least risky tranche of a CDO is known as the senior  tranche, or super-senior tranche.  Tranches between the equity tranche and the most  senior tranche are known as mezzanine tranches.

The challenge in pricing a synthetic CDO lies in the difficult task of formulating a model  for the joint default behavior of the underlying reference assets.  Understanding and  modeling the joint default dynamics of the reference assets are important in order to  compute the expected losses for each tranche.  The expected losses, in turn, determine the  fair spread of the tranche.  In fact, once the joint default distribution of the reference  assets has been specified, we can price any tranche that references these assets.

In the following section, I will present a simple approach to computing the joint default  distribution of a reference portfolio.  The approach is based on a recursive procedure and  requires no Monte Carlo simulations.  I will also compare the results of this recursive  approach with the results obtained using a Monte Carlo procedure that simulates the  default times of the reference assets and the corresponding losses in the portfolio.  The  Monte Carlo approach is computationally time-consuming as it requires a large number  of simulations in order to produce enough defaults that can impact the most senior  tranches of a CDO.

# Computing the Distribution of Default Losses

Pricing a synthetic CDO boils down to computing the joint distribution of defaults of the  reference portfolio.  Computing the default distribution, in turn, depends crucially on the  default probabilities of the reference credits and the pairwise correlation between every  pair of credits.  The correlation among the assets will drive the joint default behavior of  the assets.  The model we use here is a one-factor model whereby the defaults are driven  by one factor which we take to represent a common economic driver of credit events.   Default losses are then calculated conditional on the state of this economic factor.  This  procedure will result in computing the conditional default distribution.  The next step is  to integrate the conditional default distribution over the common factor to arrive at the  unconditional distribution of default losses.  This modeling framework has an appealing  and easy interpretation.  Conditional on the state of the common economic factor, credits  will default when their asset values fall below a pre-specified threshold.  This default  threshold usually represents the level of debt of a company.  If we further assume that the  variables driving the returns process follow a normal distribution, then this modeling  framework is also known as the Gaussian copula.
We assume that the reference portfolio contains N credits and each credit is described by  its notional amount, probability of default, and recovery rate.  For any credit “i” we then  have a notional A(i), a default probability p(i), and a recovery rate r(i).  The return  process of each credit is driven by a common factor M, and a noise factor   $\upvarepsilon(\mathrm{i})$   that is  specific to the i-th credit according to the following equation:

$$
Z(\mathrm{i})=\upbeta(\mathrm{i}).\mathbf{M}+\upvarepsilon(\mathrm{i}).\sqrt(1-\upbeta(\mathrm{i})^{2})
$$

Where the   $Z(\mathrm{i})$   represents the returns of credit i.  The market factor M, and the  idiosyncratic factor   $\upvarepsilon(\mathrm{i})$   are independent standard normals with zero means and unit  variances.  The asset returns,   $Z(\mathrm{i})$  , follow a standard normal distribution as well.  Within  this specification of the returns dynamics, the correlation between any two credits, i & j,  is simply given by the product of  β (i) and  $\upbeta(\mathrm{j})$  , where   $\upbeta{(\mathrm{i})}$   and   $\upbeta(\mathrm{j})$   are taken to represent  the betas of credits i and j respectively.  That is, they represent the sensitivities of credits i  and j to changes in the common factor.

$$
\uprho(\mathrm{Z(i)},\mathrm{Z(j)})=\upbeta(\mathrm{i}).\upbeta(\mathrm{j})
$$
 (j)

Conditional on the realization s of the common factor, defaults are only driven by the  noise factors   $\upvarepsilon(\mathrm{i})$   and are thus independent.  A credit, i, is assumed to default if its asset  return,  $Z(\mathrm{i})$  , falls below a pre-specified level or default threshold given by the  $\Phi^{\,\cdot1}(\mathrm{\textdollar{~p~}(i)})$    where   $\Phi^{\ -1}$    denotes the inverse of the cumulative standard normal distribution.  If we  denote the default threshold of credit i by D(i), then a credit i defaults when:

$$
\mathrm{{Z(i)<D(i),where~D(i)=\Phi^{-1}(\ p~(i))~}}
$$

Equivalently by re-arranging equation (1), default occurs when:

$$
\varepsilon(\mathrm{i})<\left[\mathrm{D(i)}-\upbeta(\mathrm{i}).\mathbf{M}\right]/\sqrt{(1-\upbeta(\mathrm{i})^{2})}
$$

Finally, since  $\upvarepsilon(\mathrm{i})$   are standard normals and we assume a flat correlation across all credits,  the default probability of credit i conditional on the realization s of the common factor M  is given by:

$$
\mathrm{Prob(Z(i)<D(i)\mid M)}=\Phi\left(\left[{\bf D(i)-M.\sqrt{p}}\right]/\sqrt{(1-\rho)}\right)
$$

This last equation demonstrates that only a single correlation parameter   $\uprho$   and a single  common factor  $\mathbf{M}$   are needed to calculate the joint distribution of default losses.
There are two ways to move on from here.  One approach involves a Monte Carlo  simulation of M and   $\upvarepsilon(\mathrm{i})$   in equation (1) to generate realization s of the asset returns Z(i).   Defaults will then be triggered whenever   $Z(\mathrm{i})$   falls below a threshold as described by  equation (3).  The term structure of default probabilities for each credit can be calibrated  to market spreads or implied from the credit ratings.  A second approach takes advantage  of the fact that defaults are independent, conditional on the common market factor.  It  then uses a recursive method to construct the conditional default distribution.  The details  of this recursion method are discussed in Gibson (2004), Hull & White (2003), and  Andersen, Sidenius and Basu (2003) and an alternative approach using generating  functions is discussed in Mina and Stern (2003).  We can calculate the conditional  probability that a portfolio of size i will lose exactly k credits by time t with the following  recursion:

$$
\mathrm{P^{i}(k,t\mid M)}=\mathrm{P^{i-1}(k,t\mid M)}.(1-\mathrm{P(Z(i)<D(i)\mid M)})+\mathrm{P^{i-1}(k-1,t\mid M)}.\mathrm{P(Z(i)<D(i)\mid M)}
$$

By starting with a portfolio of size 0 and successively adding credits according to the  recursion equation we can construct the conditional default distribution.  Finally, by  weighting the conditional probabilities by the probability distribution of the common  factor we arrive at the unconditional default distribution.

For the results in this article I use the Monte Carlo and the recursion methods to generate  the default loss distribution.  The Monte Carlo method, though slower, allows more  flexibility in modeling the correlation and default parameters.  When I run both models  using the same correlation and default assumptions, I get the same results.

# Pricing Synthetic CDO Tranches

Pricing a CDO tranche is a function of the tranche’s notional, spread, and expected  default losses.  The expected losses on a tranche can be estimated from the default  distribution of the reference portfolio.  Thus, for each payment date we need to estimate  the credit losses sustained by the portfolio and distribute these losses to each tranche  based on the relative position of the tranche in the capital structure: the protection leg.   Also, each tranche receives a premium that is a function of the remaining notional  amount of the tranche on the payment date: the premium leg.  Thus, both the premium leg  and the protection leg are a function of a common denominator: the portfolio credit losses  sustained by the payment date. To compute the fair spread on a tranche we need to equate  its premium leg to its protection leg, which reduces the pricing of a synthetic tranche to  the more familiar analytics of a single-name default swap.  If we denote the expected loss  of a tranche at payment date  $\mathrm{t_{i}}$   by   $\mathrm{E(L_{i})}$  , then:

Total Expected Losses on the tranche  $\begin{array}{r}{\mathrm{\Lambda_{i}}=\sum_{\mathrm{i}}\mathrm{D}_{\mathrm{i}}\cdot[\mathrm{E(L_{i})}-\mathrm{E(L_{i}}\,.\,.}\end{array}$    Total Expected Premium Payments  $=s.$  .  Σ  D  . E(N )    i i i

Where   $\mathrm{D}_{\mathrm{i}}$   is the discount factor at payment date i, s is the tranche spread,   $\mathrm{E(N_{i})}$   is the  tranche expected remaining notional by payment date i,  and the summation is taken over  all payment dates.  I should also note that the remaining notional is a function of the  expected losses on the tranche, which is driven by the portfolio credit losses.  That is:
We can then calculate the fair spread of the tranche as:

$$
\begin{array}{r l}{\mathrm{s_{fair}=}}&{{}\sum_{\mathrm{i}}D_{\mathrm{i}}\cdot\left[E(L_{\mathrm{i}})-E(L_{\mathrm{i}\;\mathrm{-}\;\mathrm{l}})\right]/\sum_{\mathrm{i}}D_{\mathrm{i}}\;.\;E(N_{\mathrm{i}})}\end{array}
$$

Once again, the pricing equations show that all one needs to compute the price of any  synthetic CDO tranche is the default distribution of the reference credits.

# Pricing & Risk Management of Synthetic CDO Tranches

To illustrate the results of the modeling approach described above, let us work with the  following transaction:   $\S1$   billion reference portfolio for a 5-year hypothetical CDO  consisting of 100 reference credits.  All credits have the same spread of 100 basis points  and an average recovery rate of   $40\%$  .  The flat asset correlation is assumed to be   $25\%$  ,  and the risk-free discount rate is a constant   $5\%$  .  In addition, all credits have the same  notional amount:   $\S10$   million.  Table 1 shows the tranches of this hypothetical CDO  along with their fair spreads as calculated using the one-factor pricing model.

Table 1  Pricing of a hypothetical CDO
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/81f2e0759d329280c2b9bd1bee82ebc051defe2b00174b38e309ed346beb07da.jpg)

As Table 1 shows, the equity and more junior tranches bear the majority of the portfolio  credit risk, although they represent a small portion of the capital structure of the CDO.  In  addition, we can use the expected losses to infer the implied rating of each tranche.  The  implied ratings show how the credit risk of a Ba2-rated reference portfolio can be  distributed as to create buckets of lower and higher quality tranches suitable for various  investors.  Figure 1 shows the unconditional default probability distribution of the  reference credits.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7ba4cbc9b4b34d078a925c90ea3aaef033132aff8ad14accc293b4f333efcad5.jpg)
Figure 1  Unconditional default probability distributions of a hypothetical CDO

Similar graphs can also be produced for each tranche.  To illustrate this analysis further, I  take the  $\mathit{\bar{3}7^{\mathrm{th}}}$  ,  $50^{\mathrm{th}}$  , and  $63^{\mathrm{rd}}$   percentiles of the common factor realization s and calculate the  portfolio expected losses at these points.  The   $37^{\mathrm{th}}$   percentile corresponds to a value of - 1.3 for the common factor and represents a market downturn, the   $\bar{5}0^{\mathrm{th}}$   corresponds to a  value of 0 for the common factor and represents a stable market, and the   $63^{\mathrm{rd}}$   percentile  corresponds to a value of 1.3 for the common factor and represents an expanding market.   Table 2 shows the results of this scenario analysis.  For the sake of completion, figure 3  and table 3 show the conditional expected losses for the equity tranche, class A tranche,  and the senior tranche.

Figure 3 clearly shows that the most senior tranche is not totally immune to losses, while  the equity tranche bears a substantial risk of default losses even under relatively positive  market conditions.  In interpreting these results, the reader should bear in mind that we  are starting with a Ba2-rated reference portfolio.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2619dceded7d5e1d2d76ced40849368921705ea9ff33d8950a9587914bceb0d8.jpg)
Figure 2  Conditional distribution of expected losses for the reference credits over 5 years

Table 2  Scenario analysis of conditional expected losses over 5 years
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6f3df1af79b620325724252774f74b0a937bd27061ad469dd49b349314aa97ee.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a472e2701767f4ff54ad9ba83508faf97a60718d9621d1be63237a47555ca21a.jpg)
Figure 3  Conditional expected losses for selected tranches over 5 years
Table 3  Scenario analysis of conditional expected losses for selected tranches over 5 years
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e28dc8fe39b403e462e3c758aa7856781964947db9d38941d05c539920abb609.jpg)

As discussed in Gibson (2004), table 3 illustrates how the mezzanine tranches can be  thought of as leveraged bets on business cycle risk. Investors in mezzanine tranches  receive spreads ranging from 923 to 86 bps according to table 1; however, they have to  absorb the majority of credit risk in difficult and recession ary market conditions.

# Parameter Sensitivities of Synthetic CDO Tranches

In addition to calculating the conditional and unconditional expected losses of the  tranches, we can also extend the risk analysis of a synthetic CDO tranche to include:

•   Computing the tranche sensitivity to changes in correlation.  •   Computing the tranche sensitivity to broad changes in credit spreads.  •   Computing the change in subordination necessary to maintain the base value of a  tranche as a function of the average credit quality of the reference portfolio.  •   Computing the standard deviation of losses.

# A.   Correlation Sensitivity

Figure 4 shows the correlation sensitivity of the equity and mezzanine tranches.  The  graph shows the fair spread of each tranche at different correlation assumptions as a  multiple of the base spread at   $25\%$   correlation.  The equity tranche is clearly long  correlation as its value increases with higher correlations: the spread falls as correlation  increases.  This is typical for an equity tranche because higher correlation increases the  probability of fewer defaults as well as the probability of more defaults.  Since equity  investors are sensitive to any default it makes sense that they would prefer higher  probabilities of fewer defaults - hence higher correlation.  In contrast, Class A investors,   $12–22\%$   tranche, are short correlation.  For Class A investors, higher correlation reduces  the value of the tranche and increases its spread.

Tranches in the middle of the capital structure share similar behavior with either the  equity tranche or the more senior tranches, but with much less sensitivity to correlation  assumptions.  For example, Class C,   $6.9\%$   tranche, shows very little sensitivity to  changes in correlations far beyond the initial assumption of   $25\%$   correlation.  Figure 5  completes the picture by showing the high sensitivity of the most senior tranche to  changes in correlation.  More senior tranches of a CDO transaction are only susceptible  to extreme market shocks that cause higher market correlations and multiple defaults to  occur.
These observations are consist with the scenario analysis shown in table 3 and figure 3  which illustrate the conditional impact of wide economic downturns on the value of  senior tranches.  In fact, although not shown table 3, at the   $24^{\mathrm{th}}$   percentile value of the  common default driver, Class A is expected to lose all its notional and the most senior  tranche is expected to suffer a   $7\%$   loss.  Economic shocks of such a magnitude are not  unheard of.

The correlation sensitivity analysis illustrates two important features of CDO investing:

•   Investors with different correlation assumptions will attach different values to the  same tranche.  This creates both model risk and an opportunity for correlation  and/or model arbitrage.  Correlation is a very difficult parameter to measure and  estimates of correlation are susceptible to estimation errors, personal judgments,  and correlation breakdowns among many others.  •   Mezzanine tranches are the least sensitive to changes in the correlation  parameter.  Therefore, these tranches are also the least sensitive to modeling  errors.  For example, Class C investors will notice very little change to the value  of their tranche even if correlation doubles.  Investors who wish to minimize  parameter risk will therefore prefer the middle tranches of a CDO transaction.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/27647292baccce995449adb69dbd4c24e9c4434e3cc666023c8ed60a29734c1b.jpg)
Figure 4  Correlation sensitivity of CDO tranches: base spread is calculated at  $25\%$   correlation
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/be6f301afbd45d7e4dc6e108dd8eb74eafe1686bf6ff24f193ede9af98537e21.jpg)
Figure 5  Correlation sensitivity of CDO tranches: base spread is calculated at  $25\%$   correlation

# B.   Sensitivity to Broad Spread Changes

To see the effect of broad economic changes in credit spreads on CDO tranches, I  calculate the tranche fair spreads after increasing the credit spreads by 10 bps for all  credits.  I also calculate the decrease in each tranche’s mark-to-market value and report  the results in dollar terms and as a percentage of tranche notional.  Table 4 reports these  results.  The spread on the equity tranche is the least sensitive to a broad increase in credit  spreads.  However, the change in the mark-to-market as a percentage of tranche notional  is greatest for the equity tranche.  In contrast, the spread on the most senior tranche has  the greatest sensitivity to broad changes in market spreads, though its MtM is least  impacted.  These results are expected since the increase in credit spreads will increase the  likelihood for a higher number of credit defaults to which the senior tranches are more  sensitive.  That is, in a market environment where credit quality is deteriorating, the  probability that we will see multiple credit defaults will increase, which will lower the  credit subordination available to the senior tranches, and increase the probability of credit  losses reaching the senior tranches.  It should be noted here that the effect of a broad  increase in default probabilities across credits is indistinguishable from the effect of an  increase in the default correlation among credits.
Table 4  Tranche sensitivity to a 10-bps increase in spreads of all credits.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/49acb07f51e1e89a2de77545901356bd2b8800a17367a1432cda838cf6ee9723.jpg)

# C.   The Subordination Effect

The expected loss of a tranche is driven not only by the credit spreads of the reference  assets but also by the credit enhancement available to the tranche.  To illustrate the effect  of subordination, or location of a tranche within the capital structure, I run the following  analysis: the original reference portfolio is divided into two equal groups.  In the first  group, the reference credits retain their initial spreads of 100 bps, while the second  group’s credit spreads are varied to 120, 130, 140, 150, and 160 bps.  Starting with the  base case of a 100 bps for all credits, I calculate the expected loss on Class D, the   $3–6\%$    tranche.  Then I change the reference portfolio so that half the credits have a spread of  120 bps, and I back out the subordination necessary to bring about a similar expected loss  for Class D.  I repeat the same analysis with 130, 140, 150, 160, and 180 bps to obtain the  levels of subordination that will maintain the expected loss of Class D at the same base  level in each case.

The graph in figure 6 shows how the subordination varies with the average spread on the  reference portfolio.  As we progressively decrease the quality of the reference portfolio,  we need higher levels of subordination to maintain the expected loss of Class D at a level  similar to its base level of   $34.27\%$  .  This analysis illustrates another subtly in CDO  structuring: practically any desirable rating can be attained for a tranche provided the  right amount of credit enhancement can be provided to that tranche.  The lower the credit  quality of the reference portfolio, the more subordination the tranche will require to  achieve the same rating.  Figure 6 also shows the effect of higher subordination on  tranche leverage.  Leverage is defined as the expected loss of the tranche divided by the  expected loss of the reference portfolio.  As figure 6 shows, higher subordination leads to  lower leverage.  In other words, the lower the credit quality of the reference portfolio, the  lower the leverage a tranche will require to achieve a particular rating.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/574529ff82c1d6205a8e5a188906bc889227144666af49547b7e40f8d7e454a4.jpg)
Figure 6  Subordination effect on expected losses and leverage

# D.   Measuring Standard Deviation and Unexpected Losses

The one-factor Gaussian model allows an easy and straightforward calculation of the  standard deviation of tranche losses.  Given the expected loss of a tranche at time   $\mathrm{T}$  , its  loss distribution, and its default probabilities, we can calculate the standard deviation of  losses at time T with this formula:

$$
\mathbf{\tau}_{\mathsf{l}}=[\sum_{\mathbf{k}}\left(\mathbf{x}-\mathbf{EL}\right)^{2}.\mathbf{P}(\mathbf{k},\mathrm{T})]^{0.5}
$$

Where x is the tranche loss given the number of defaults in the reference portfolio and the  summation is taken over 0 defaults to   $\mathbf{k}=100$   defaults.  Using equation 11, I calculate the  standard deviation of losses for each tranche.  The results are shown in table 5.  We can  then use the standard deviation to define measures for unexpected losses and required  economic capital to hedge against extreme losses.  Here I define the unexpected losses of  a tranche to be the loss level at one standard deviation above the expected loss of the  tranche

Table5  Measures of tranche risk and unexpected losses
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/16170cdd681c884ab51a57ec8c61619bfe3762be0b49e554eacac641f70e5895.jpg)
# Monte Carlo Simulation of Losses

The Monte Carlo approach, described in Li (2000), generates the loss distribution by  simulating the default times of the reference credits using the Gaussian copula.  This  approach is flexible in that it allows for stochastic modeling of the recovery and default  parameters.  The Monte Carlo approach can easily incorporate more than one economic  factor, it allows for sampling losses from fat-tailed distributions, and it is capable of  capturing a more complex correlation structure.  However, the Monte Carlo approach is  time-consuming as it requires a large number of simulations in order to reduce estimation  error and capture extreme losses that will only affect the most senior tranches.  The  recursive approach, on the other hand, is simpler and faster, but lacks the flexibility of the  Monte Carlo approach.

Using the same modeling assumptions, the Monte Carlo approach should produce similar  results to those obtained from the recursion method.  That is, if we set the recovery rates,  credit spreads, and correlation parameter in the Monte Carlo model to those used for the  recursion method, the results of both approaches aught to be similar.  Table 6 shows the  Monte Carlo results using one million simulations.  As evident from table 6, the recursion  approach provides a robust and accurate estimation of expected losses and standard  deviations.

Table 6:  Expected losses and standard deviations with one million Monte Carlo simulations
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8c9b079eae1a614f797f758879c7859a8e291536b42220c5ac5b48bd3e201036.jpg)

# Conclusion

In this article, I have demonstrated a simple, yet powerful technique to calculate the  default distribution of a credit portfolio.  Using this technique, I have shown how the fair  spreads and risk parameters of synthetic CDO tranches can be calculated.  The important  highlights of this article can be summarized as follows:

•   The equity and most junior tranches of a synthetic CDO bear the majority of  credit risk of the reference portfolio.  •   The most senior tranche is not completely immune to credit losses.    •   The value of the equity and most junior tranches increases as correlation across  the credits rises. On the other hand, the value of the senior tranches decreases  with higher correlation.  •   The mezzanine tranche is the least sensitivity to the correlation parameter and  to correlation model risk.  •   The senior tranches are more sensitive to broad changes in credit spreads.  •   There is a trade-off between the quality of the reference credits and the  subordination required to attain a particular rating for a tranche.  The lower the  quality of the reference credits, the higher the required subordination.
# References

Andersen, L., Sidenius, J., and Basu, S. (2003).  All your hedges in one basket.   Risk ,      November: 67-72                                      Gibson, M. (2004).  Understanding the risk of synthetic CDOs.  Trading Risk Analysis      Section, Division of Research and Statistics, Federal Reserve Board.  Hull, J., and White, A. (2004).  Valuation of a CDO and an  ${\boldsymbol{\mathrm{n}}}^{\mathrm{th}}$   to default CDS without      Monte Carlo simulation.  Working paper, University of Toronto.  Li, D. (2000).  On default correlation: a copula function approach.  Working paper,      Risk Metrics Group.  Mina, J. and Stern, E. (2003).  Examples and applications of closed-form CDO pricing.       Risk Metrics Journal , Fall 2003: 5-24
