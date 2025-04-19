---
tags:
  - bond_pricing
  - credit_migration
  - credit_risk
  - default_probability
  - deterministic_model
aliases:
  - Credit Quality Model
  - Deterministic Credit Model
key_concepts:
  - Conditional probabilities
  - Credit migration model
  - Deterministic default probability
  - Non-constant default probability
  - Transitional probabilities
---

# 7.3 A DETERMINISTIC CREDIT MIGRATION MODEL  

The constant default probability model can incorporate a deterministic scenario of changing credit quality. Suppose we believe that the probability of default for year 1 is $0.11\%$ , but $6\%$ in year 2 and $8\%$ in year 3. Table 7.4 shows that all we need to do is recompute the cumulative survival probabilities; the rest proceeds as before.  

The corporate credit spread on the bond is now $4.979\%$  

Perhaps a better, or at least a richer, way of dealing with a deterministically changing default rate is a credit migration model. The term "credit migration' refers in general to the path dependence of the probability of default. More narrowly, it refers to the possibility that the probability of default for a future period depends on the default risk of the bond during the previous period.  

If a bond is currently rated single A and we assign some probability to the possibility that the bond will be upgraded from A to AA and also some probabilities that the bond will remain A-rated or be downgraded from A to BBB over the next year, then the unconditional. probability of default for the following year will depend on the current rating of the bond, the conditional probabilities in the up, down, and any middle states, and on the transitional probabilities of migrating from the current state to a different default rating category. In this. approach, we consider the probabilities not only of default, but of more gradual changes to. the bond's credit rating, and the path of those changes. We can also take into account the. changing nature of the subsequent probabilities of upgrades and downgrades. The model can be made as rich as necessary, as long as there are enough observable bonds of the same issuer with different maturities to calibrate it (here we may need more than one bond per maturity). Effectively, we are replacing the assumption of temporal independence with a model of conditional probabilities.  

Table 7.4 The ABC bond with a deterministic non-constant default probability   


<html><body><table><tr><td>Year</td><td>CF</td><td>Prob/Year</td><td>Cumulative survival prob.</td><td>Risk-free zerorate</td><td>Risk-free DF</td><td>PV</td></tr><tr><td>1</td><td>5</td><td>0.11%</td><td>0.99890</td><td>2.5000%</td><td>0.975610</td><td>4.8727</td></tr><tr><td>2</td><td>5</td><td>6.00%</td><td>0.93897</td><td>2.6249%</td><td>0.949499</td><td>4.4577</td></tr><tr><td>3</td><td>105</td><td>8.00%</td><td>0.86385</td><td>2.7498%</td><td>0.921843</td><td>83.6150</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>SumPV=</td><td>92.9454</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>Yield =</td><td>7.7238%</td></tr></table></body></html>  

![](3d5a60eb045d99475171181ccb4a56c0a493af7d56acf15350a0737096371b62.jpg)  
Figure 7.6 One node of a credit migration model  

Let us examine the following scenario. ABC has the probability of default over the next year of $0.20\%$ . We postulate that the annual default probability for year 2 will change to. $0.10\%$ with the probability of $30\%$ , or to $0.70\%$ with the probability of $70\%$ . The 30-70 probabilities of period-to-period changes in the issuer's credit rating are referred to as transitional probabilities. Now, depending on where we end up in year 2, we will assume different transition probabilities for years 2-3 and different default probabilities for year 3. If we end up at. $0.10\%$ for year 2, then we postulate that the annual default probability for year 2 will change to $0.05\%$ with the probability of $25\%$ , or to $0.30\%$ with the probability of $75\%$ . If we end up at $0.70\%$ for year 2, then we postulate that the annual default probability for year 2 will change to $0.30\%$ with the probability of $30\%$ , or to $3.00\%$ with the probability of $70\%$ . This way we can model a non-linear path toward credit trouble and a migration from one credit category to the next over time.  

We use a decision tree similar to the binomial tree for options to depict our scenario (our tree is recombinant, but that is not essential). On each node, we mark the probability of default for the year starting at that node and ending next year. We show transitional probabilities of going up or down. We also show the scheduled cash flow for the next period. The present value displayed at each node is the discounted expected value of the cash flow to be received next period, cumulated with the expected value of the subsequent period's cash flow which is probability-weighted and discounted. Graphically each node $n$ is represented as in Figure 7.6.  

To compute the present value of future cash flows, we cannot ignore the down nodes as we did in Figure 7.5. We also have to "disassemble" the discounting into one-step forward rates.. At each, the probability-weighted discounted value of future cash flows is equal to.  

$$
\begin{array}{r}{P V_{n}=(1-D e f P r o b_{n})}\ {\times[C F_{n+1}+(T r a n s P r o b_{U p}\cdot P V_{U p}+T r a n s P r o b_{D n}\cdot P V_{D n})]/(1+r_{n,n+1})}\end{array}
$$  

To value the $5\%$ 3-year bond issued by ABC, we sweep backwards through the tree, taking. into account our transitional and survival assumptions. Today's price of the ABC bond turns out to be 104.14 and the yield-to-maturity is. $3.5217\%$ . The result is shown in Figure 7.7..  

Note that our tree does not rely on a hedging argument. It is a convenient graphical tool for computing probability-weighted averages given the conditional default and transition probabilities. It only coincidentally resembles option-pricing trees which are risk-neutral discretized price dynamics. Also note the large number of inputs into the model. Observing 1-, 2-, and 3-year bonds issued by ABC would not be enough to calibrate the model. A reasonable simplification might involve fixing the default probabilities at each note (e.g. set them equal to historic default rates for different rating categories) and calibrating only on the transition probabilities.  

![](9365043c861865f4d67b679f8c90789091b2f966d93f2d818b4fb4a72c88d410.jpg)  
Figure 7.7 A binomial credit migration model with deterministic conditional default and transition probabilities  
