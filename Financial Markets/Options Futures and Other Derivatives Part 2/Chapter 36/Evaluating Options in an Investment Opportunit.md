---
tags:
  - '#abandonment_option'
  - '#amazon_com_valuation'
  - '#derivatives_market_losses'
  - '#expansion_option'
  - '#investment_valuation'
  - '#market_price_of_risk'
  - '#option_pricing'
  - '#real_options'
  - '#risk_neutral_valuation'
---
# 36.5 EVALUATING OPTIONS IN AN INVESTMENT OPPORTUNITY  

As already mentioned, most investment projects involve options. These options can add considerable value to the project and are often either ignored or valued incorrectly.. Examples of the options embedded in projects are:.  

I. Abandonment options. This is an option to sell or close down a project. It is an. American put option on the project's value. The strike price of the option is the  

# Business Snapshot 36.1 Valuing Amazon.com  

One of the earliest published attempts to value a company using the real options approach was Schwartz and Moon (2000), who considered Amazon.com at the end of 1999. They assumed the following stochastic processes for the company's sales revenue $R$ and its revenue growth rate $\mu$  

$$
\begin{array}{l}{{\displaystyle{\frac{d R}{R}}=\mu d t+\sigma(t)d z_{1}}}\ {{\displaystyle{d}\mu=\kappa(\overline{{{\mu}}}-\mu)d t+\eta(t)d z_{2}}}\end{array}
$$  

They assumed that the two Wiener processes $d z_{1}$ and $d z_{2}$ were uncorrelated and made reasonable assumptions about $\sigma(t),\eta(t),\kappa,$ and $\overline{{\mu}}$ based on available data.  

They assumed the cost of goods sold would be $75\%$ of sales, other variable expenses would be $19\%$ of sales, and fixed expenses would be. $\$75$ million per quarter. The initial sales level was. $\$356$ million, the initial tax loss carry forward was $\$559$ million, and the tax rate was assumed to be. $35\%$ . The market price of risk for $R$ was estimated from historical data using the approach described in the previous section. The market price of risk for $\mu$ was assumed to be zero..  

The time horizon for the analysis was 25 years and the terminal value of the company was assumed to be ten times pretax operating profit. The initial cash position was $\$906$ million and the company was assumed to go bankrupt if the cash balance became negative.  

Different future scenarios were generated in a risk-neutral world using Monte Carlo simulation. The evaluation of the scenarios involved taking account of the possible exercise of convertible bonds and the possible exercise of employee stock options. The value of the company to the share holders was calculated as the present value of the net cash flows discounted at the risk-free rate.  

Using these assumptions, Schwartz and Moon provided an estimate of the value of Amazon. com's shares at the end of 1999 equal to. $\$12.42$ . The market price at the time was $\$76.125$ (although it declined sharply in 2000). One of the key advantages of the real-options approach is that it identifies the key assumptions. Schwartz and Moon found that the estimated share value was very sensitive to $\eta(t)$ , the volatility of. the growth rate. This was an important source of optionality. A small increase in $\eta(t)$ leads to more optionality and a big increase in the value of Amazon.com shares. No doubt Amazon has benefited from this optionality.  

liquidation (or resale) value of the project less any closing-down costs. When the liquidation value is low, the strike price can be negative. Abandonment options mitigate the impact of very poor investment outcomes and increase the initial valuation of a project.  

2. Expansion options. This is the option to make further investments and increase the output if conditions are favorable. It is an American call option on the value of additional capacity. The strike price of the call option is the cost of creating this additional capacity discounted to the time of option exercise. The strike price often depends on the initial investment. If management initially choose to build capacity in excess of the expected level of output, the strike price can be relatively small.  

3. Contraction options. This is the option to reduce the scale of a project's operation. It is an American put option on the value of the lost capacity. The strike price is the present value of the future expenditures saved as seen at the time of exercise of the option.   
4. Options to defer. One of the most important options open to a manager is the option to defer a project. This is an American call option on the value of the project.   
5. Options to extend life. Sometimes it is possible to extend the life of an asset by paying a fixed amount. This is a European call option on the asset's future value.  

# lustration  

As an example of the evaluation of an investment with embedded options, consider a company that has to decide whether to invest $\$15$ million to extract 6 million units of a commodity from a certain source at the rate of 2 million units per year for 3 years. The fixed costs of operating the equipment are $\$6$ million per year and the variable costs are $\$17$ per unit of the commodity extracted. We assume that the risk-free interest rate is $10\%$ per annum for all maturities, that the spot price of the commodity is $\$20$ , and that the 1-, 2-, and 3-year futures prices are $\$22$ $\$23$ , and $\$24$ , respectively.  

# Evaluation with No Embedded Options  

First consider the case where the project has no embedded options. The expected prices of the commodity in 1, 2, and 3 years' time in a risk-neutral world are. $\$22$ $\$23$ , and $\$24$ respectively. The expected payoff from the project (in millions of dollars) in a risk-neutral world can be calculated from the cost data as 4.0, 6.0, and 8.0 in years 1, 2, and 3, respectively. The value of the project is therefore.  

$$
-15.0+4.0e^{-0.1\times1}+6.0e^{-0.1\times2}+8.0e^{-0.1\times3}=-0.54
$$  

This analysis indicates that the project should not be undertaken because it would reduce shareholder wealth by 0.54 million.  

# Use of a Tree  

We now assume that the spot price of the commodity follows the process  

$$
d\ln S=[\theta(t)-a\ln S]d t+\sigma d z
$$  

where $a=0.1$ and $\sigma=0.2$ In Section 35.4, we showed how a tree can be constructed for commodity prices using the same example as the one considered here. The tree is shown in Figure 36.1 (which is the same as Figure 35.2). The process represented by the tree is consistent with the process assumed for $S$ , the assumed values of $a$ and $\sigma$ , and the assumed 1-, 2-, and 3-year futures prices.  

We do not need to use a tree to value the project when there are no embedded.   
options. (We have already shown that the base value of the project without options is.   
$-0.54.)$ However, before we move on to consider options, it will be instructive, as well.   
as useful for future calculations, for us to use the tree to value the project in the absence   
of embedded options and verify that we get the same answer as that obtained earlier.  

![](609789b75cf886098ff96fab81178470fd54042155f5167f0ce4b7ac1fefac81.jpg)  
Figure 36.1 Tree for spot price of a commodity: $p_{u},p_{m}$ , and $p_{d}$ are the probabilities of "up", "middle", and "down' movements from a node.  

Figure 36.2 shows the value of the project at each node of Figure 36.1. Consider, for example, node H. There is a 0.2217 probability that the commodity price at the end of the third year is 22.85, so that the third-year profit is $2\times22.85-2\times17-6=5.70$ Similarly, there is a 0.6566 probability that the commodity price at the end of the third year is 16.16, so that the profit is $-7.68$ and there is a 0.1217 probability that the commodity price at the end of the third year is 11.43, so that the profit is $-17.14$ . The value of the project at node $_\mathrm{H}$ in Figure 36.2 is therefore  

$$
[0.2217\times5.70+0.6566\times(-7.68)+0.1217\times(-17.14)]e^{-0.1\times1}=-5.31
$$  

As another example, consider node C. There is a 0.1667 chance of moving to node $\mathrm{F}$ where the commodity price is 31.37. The second year cash flow is then.  

$$
2\times31.37-2\times17-6=22.74
$$  

The value of subsequent cash flows at node $\mathrm{F}$ is 21.42. The total value of the project if we move to node $\mathrm{F}$ is therefore $21.42+22.74=44.16.$ Similarly the total value of the project if we move to nodes $\mathrm{G}$ and $\mathrm{H}$ are 10.35 and $-13.93$ , respectively. The value of the project at node $\mathrm{C}$ is therefore  

$$
[0.1667\times44.16+0.6666\times10.35+0.1667\times(-13.93)]e^{-0.1\times1}=10.80
$$  

Figure 36.2 shows that the value of the project at the initial node A is 14.46. When the initial investment is taken into account the value of the project is therefore. $-0.54.$ This is in agreement with our earlier calculations..  

Figure 36.2 Valuation of base project with no embedded options:. $p_{u},p_{m}$ , and $p_{d}$ are the probabilities of "up", "middle", and "down' movements from a node.  

![](cacb68d2f66ec2cc49e3e24553605d8f1fcf24f3b195e41c728f920f6ab18c36.jpg)  

# Option to Abandon  

Suppose now that the company has the option to abandon the project at any time. We suppose that there is no salvage value and no further payments are required once the project has been abandoned. Abandonment is an American put option with a strike price of zero and is valued in Figure 36.3. The put option should not be exercised at nodes E, F, and G because the value of the project is positive at these nodes. It should be exercised at nodes H and I. The value of the put option is 5.31 and 13.49 at nodes H and I, respectively. Rolling back through the tree, the value of the abandonment put option at node $\mathrm{\bfD}$ if it is not exercised is  

$$
(0.1217\times13.49+0.6566\times5.31+0.2217\times0)e^{-0.1\times1}=4.64
$$  

The value of exercising the put option at node. $\mathrm{\bfD}$ is 9.65. This is greater than 4.64, and. so the put should be exercised at node D. The value of the put option at node $\mathrm{C}$ is  

$$
[0.1667\times0+0.6666\times0+0.1667\times5.31]e^{-0.1\times1}=0.80
$$  

and the value at node A is  

$$
(0.1667\times0+0.6666\times0.80+0.1667\times9.65)e^{-0.1\times1}=1.94
$$  

The abandonment option is therefore worth $\$1.94$ million. It increases the value of the project from $-\$0.54$ million to $+\$1.40$ million. A project that was previously unattractive now has a positive value to shareholders.  

![](d5f6f02bd6e0259677d9eec2d0bd52c26b3811d1b81ea55323ef7ab5f50934d9.jpg)  
Figure 36.3  Valuation of option to abandon the project:. $p_{u},p_{m}$ and $p_{d}$ are the probabilities of "up", "middle", and "down" movements from a node.  

# Option to Expand  

Suppose next that the company has no abandonment option. Instead it has the option at any time to increase the scale of the project by $20\%$ . The cost of doing this is. $\$2$ million. Production increases from 2.0 to 2.4 million units per year. Variable costs remain. $\$17$ per unit and fixed costs increase by $20\%$ from $\$6.0$ million to $\$7.2$ million. This is an. American call option to buy. $20\%$ of the base project in Figure 36.2 for. $\$2$ million. The option is valued in Figure 36.4. At node E, the option should be exercised. The payoff is $0.2\times42.24-2=6.45.$ At node F, it should also be exercised for a payoff of. $0.2\times21.42-2=2.28.$ At nodes G, H, and I, the option should not be exercised. At. node B, exercising is worth more than waiting and the option is worth. $0.2\times38.32\mathrm{~-~}2=$ 5.66. At node C, if the option is not exercised, it is worth.  

$$
(0.1667\times2.28+0.6666\times0.00+0.1667\times0.00)e^{-0.1\times1}=0.34
$$  

If the option is exercised, it is worth. $0.2\times10.80-2=0.16.$ The option should therefore not be exercised at node C. At node A, if not exercised, the option is worth  

$$
(0.1667\times5.66+0.6666\times0.34+0.1667\times0.00)e^{-0.1\times1}=1.06
$$  

If the option is exercised it is worth $0.2\times14.46-2=0.89.$ Early exercise is therefore not optimal at node A. In this case, the option increases the value of the project from $-0.54$ to $+0.52$ Again we find that a project that previously had a negative value now has a positive value.  

Figure 36.4  Valuation of option to expand the project:. $p_{u},p_{m}$ and $p_{d}$ are the probabilities of "up", "middle", and "down' movements from a node.  

![](e9594e7ca3e1e69e9b4f4c1a9c2d19557e11c529c26ba68907600cac1de0e94d.jpg)  

The expansion option in Figure 36.4 is relatively easy to value because, once the. option has been exercised, all subsequent cash inflows and outflows increase by. $20\%$ . In the case where fixed costs remain the same or increase by less than. $20\%$ , it is necessary to keep track of more information at the nodes of Figure 36.4. Specifically, we need to record the following in order to calculate the payoff from exercising the option:  

1. The present value of subsequent fixed costs   
2. The present value of subsequent revenues net of variable costs.  

# Multiple Options  

When a project has two or more options, they are typically not independent. The value of having both option A and option B, for example, is generally not the sum of the values of the two options. To illustrate this, suppose that the company we have been considering has both abandonment and expansion options. The project cannot be expanded if it has already been abandoned. Moreover, the value of the put option to abandon depends on whether the project has been expanded.3  

These interactions between the options in our example can be handled by defining four states at each node:  

1. Not already abandoned; not already expanded   
2. Not already abandoned; already expanded   
3. Already abandoned; not already expanded   
4. Already abandoned; already expanded.  

When we roll back through the tree we calculate the combined value of the options at. each node for all four alternatives. This approach to valuing path-dependent options is discussed in more detail in Section 27.5..  

# Several Stochastic Variables  

When there are several stochastic variables, the value of the base project is usually determined by Monte Carlo simulation. The valuation of the project's embedded options is then more difficult because a Monte Carlo simulation works from the beginning to the end of a project. When we reach a certain point, we do not have information on the present value of the project's future cash flows. However, the techniques mentioned in Section 27.8 for valuing American options using Monte Carlo simulation can sometimes be used.  

As an illustration of this point, Schwartz and Moon (2ooo) explain how their Amazon.com analysis outlined in Business Snapshot 36.1 could be extended to take account of the option to abandon (i.e. the option to declare bankruptcy) when the value of future cash flows is negative." At each time step, a polynomial relationship between the. value of not abandoning and variables such as the current revenue, revenue growth rate,. volatilities, cash balances, and loss carry forwards is assumed. Each simulation trial provides an observation for obtaining a least-squares estimate of the relationship at each. time. This is the Longstaff and Schwartz approach of Section 27.8.5  

# SUMMARY  

This chapter has investigated how the ideas developed earlier in the book can be applied to the valuation of real assets and options on real assets. It has shown how. the risk-neutral valuation principle can be used to value a project dependent on any set. of variables. The expected growth rate of each variable is adjusted to reflect its market price of risk. The value of the asset is then the present value of its expected cash flows discounted at the risk-free rate.  

Risk-neutral valuation provides an internally consistent approach to capital investment appraisal. It also makes it possible to value the options that are embedded in many of the projects that are encountered in practice. This chapter has illustrated the approach by applying it to the valuation of Amazon.com at the end of 1999 and the valuation of a project involving the extraction of a commodity.  

# FURTHER READING  

Amran, M., and N. Kulatilaka, Real Options, Boston, MA: Harvard Business School Press, 1999.  

Copeland, T., and V. Antikarov, Real Options: A Practitioners Guide, New York: Texere, 2003.   
Koller, T., M. Goedhart, and D. Wessels, Valuation: Measuring and Managing the Value of Companies, 5th edn. New York: Wiley, 2010.   
Mun, J., Real Options Analysis, Hoboken, NJ: Wiley, 2006.   
Schwartz, E. S., and M. Moon, "Rational Pricing of Internet Companies, Financial Analysts Journal, May/June (2000): 62-75.   
Trigeorgis, L., Real Options: Managerial Flexibility and Strategy in Resource Allocation, Cambridge, MA: MIT Press, 1996.  

# Practice Questions  

36.1. Explain the difference between the net present value approach and the risk-neutral valuation approach for valuing a new capital investment opportunity. What are the. advantages of the risk-neutral valuation approach for valuing real options?   
36.2. The market price of risk for copper is 0.5, the volatility of copper prices is $20\%$ per annum, the spot price is 80 cents per pound, and the 6-month futures price is 75 cents per pound. What is the expected percentage growth rate in copper prices over the next 6 months?   
36.3. Show that if $y$ is a commodity's convenience yield and $u$ is its storage cost, the. commodity's growth rate in the traditional risk-neutral world is $r-y+u$ , where $r$ is the risk-free rate. Deduce the relationship between the market price of risk of the commodity, its real-world growth rate, its volatility, $y$ , and $u$   
36.4. The correlation between a company's gross revenue and the market index is 0.2. The. excess return of the market over the risk-free rate is $6\%$ and the volatility of the market index is $18\%$ . What is the market price of risk for the company's revenue?.   
36.5. A company can buy an option for the delivery of 1 million units of a commodity in 3 years at $\$25$ per unit. The 3-year futures price is $\$24.$ The risk-free interest rate is. $5\%$ per annum with continuous compounding and the volatility of the futures price is $20\%$ per annum. How much is the option worth?   
36.6. A driver entering into a car lease agreement can obtain the right to buy the car in 4 years for $\$10,000$ The current value of the car is $\$30,000$ The value of the car, $S$ is expected to follow the process $d S=\mu S d t+\sigma S d z$ , where $\mu=-0.25,\sigma=0.15$ , and $d z$ is a Wiener process. The market price of risk for the car price is estimated to be $-0.1$ . What is the value of the option? Assume that the risk-free rate for all maturities is $6\%$   
36.7. Suppose that the spot price, 6-month futures price, and 12-month futures price for wheat are 250, 260, and 270 cents per bushel, respectively. Suppose that the price of wheat. follows the process in equation (36.3) with. $a=0.05$ and $\sigma=0.15.$ Construct a two-timestep tree for the price of wheat in a risk-neutral world. A farmer has a project that involves an expenditure of $\$10,000$ and a further expenditure of $\$90,000$ in 6 months. It will increase wheat that is harvested and sold by 40,000 bushels in 1 year. What is the value of the project? Suppose that the farmer can. abandon the project in 6 months and avoid paying the $\$90,000$ cost at that time. What is the value of the abandonment option? Assume a risk-free rate of $5\%$ with continuous  

compounding.  

![](096e27502f707fa0dfa34619876afb7d726919f0450cb6eb8d1c25b9f1ee6f74.jpg)  

# Derivatives Mishapsd s and what We Can Learn from Them  

Since the mid-1980s there have been some spectacular losses in derivatives markets. The biggest losses have come from the trading of products created from subprime residential mortgages in the United States and were discussed in Chapter 8. Some of the other losses made by financial institutions are listed in Business Snapshot 37.1, and some of those made by nonfinancial organizations in Business Snapshot 37.2. What is remarkable about these lists is the number of situations where huge losses arose from the activities of a single employee. In 1995, Nick Leeson's trading brought a 200-year-old British bank, Barings, to its knees; in 1994, Robert Citron's trading led to Orange County, a municipality in California, losing about $\$2$ billion. Joseph Jett's trading for Kidder Peabody lost $\$350$ million. John Rusnak's losses of $\$700$ million for Allied Irish Bank came to light in 2002. In 2006 the hedge fund Amaranth lost $\$6$ billion because of trading risks taken by Brian Hunter. In 2008, Jerome Kerviel lost over $\$7$ billion trading equity index futures for Societe Generale. The huge losses at UBs, Shell, and Sumitomo were also each the result of the activities of a single individual.  

The losses should not be viewed as an indictment of the whole derivatives industry.. The derivatives market is a vast multitrillion dollar market that by most measures has. been outstandingly successful and has served the needs of its users well. The events listed in Business Snapshots 37.1 and 37.2 represent a tiny proportion of the total trades. (both in number and value). Nevertheless, it is worth considering carefully the lessons that can be learned from them.  
