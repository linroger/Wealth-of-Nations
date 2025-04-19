---
tags:
  - black_scholes_model
  - employee_stock_options
  - option_pricing
  - valuation
  - volatility
aliases:
  - Option Valuation
  - Valuation of Options
key_concepts:
  - Black-Scholes-Merton model
  - Employee stock option valuation
  - Expected option life
  - Historical data volatility
  - Income statement expense
---

# 16.4 VALUATION  

Accounting standards give companies quite a bit of latitude in choosing a method for valuing employee stock options. In this section we review some of the alternatives.  

# Using the Black-Scholes-Merton Model  

A frequently used approach is based on what is known as the option's expected life. This is the average time for which employees hold the option before it is exercised or expires. The expected life can be approximately estimated from historical data on the early. exercise behavior of employees and reflects the vesting period, the impact of employees. leaving the company, and the tendency we mentioned in Section 16.1 for employee stock options to be exercised earlier than regular options. The Black-Scholes-Merton model is used with the life of the option,. $T$ set equal to the expected life. The volatility is usually. estimated from several years of historical data as described in Section 15.4..  

It should be emphasized that using the Black-Scholes-Merton formula in this way has no theoretical validity. There is no reason why the value of a European stock option with the time to maturity, $T$ set equal to the expected life should be approximately the same as the value of the American-style employee stock option that we are interested in. However, the results given by the model are not unreasonable in many situations. Companies, when reporting their employee stock option expense, will frequently mention the volatility and expected life used in their Black-Scholes-Merton computations.  

# Example 16.1  

A company grants 1,000,000 options to its executives on November 1, 2021. The stock price on that date is. $\$30$ and the strike price of the options is also. $\$30$ The options last for 10 years and vest after three years. The company has issued similar at-the-money options for the last 10 years. The average time to exercise. or expiry of these options is 4.5 years. The company therefore decides to use an "expected life"' of 4.5 years. It estimates the long-term volatility of the stock. price, using 5 years of historical data, to be. $25\%$ . The present value of dividends during the next 4.5 years is estimated to be $\$4.$ The 4.5-year zero-coupon risk-free interest rate is $5\%$ . The option is therefore valued using the Black-ScholesMerton model (adjusted for dividends in the way described in Section 15.12). with $S_{0}=30-4=26,K=30,r=5\%,\sigma=25$ , and $T=4.5$ . The BlackScholes-Merton formula gives the value of one option as. $\$6.31$ . Hence, the income statement expense is $1,000,000\times6.31$ , or $\$6,310,000$  

# Binomial Tree Approach  

A more sophisticated approach to valuing employee stock options involves building a binomial tree as outlined in Chapter 13 and adjusting the rules used when rolling back through the tree to reflect (a) whether the option has vested, (b) the probability of the employee leaving the company, and (c) the probability of the employee choosing to exercise the option. The terms of the option define whether the option has vested at different nodes of the tree. Historical data on turnover rates for employees can be used to estimate the probability of the option being either prematurely exercised or forfeited at a node because the employee leaves the company. The probability of an employee choosing to exercise the option at different nodes of the tree is more difficult to quantify. Clearly this probability increases as the ratio of the stock price to the strike price increases and as the time to the option's maturity declines. If enough historical data is available, the probability of exercise as a function of these two variables can be estimated-- at least approximately.  

# Example 16.2  

Suppose a company grants stock options that last 8 years and vest after 3 years. The stock price and strike price are both $\$40.$ The stock price volatility is. $30\%$ , the risk-free rate is. $5\%$ , and the company pays no dividends. Figure 16.1 shows how a. four-step tree could be used to value the option. (This is for illustration; in practice more time steps would be used.) In this case,. $\sigma=0.3$ $\Delta t=2$ , and $r_{-}=0.05$ , so that, with the notation of Chapter $13,a=e^{0.05\times2}=1.1052$ $u=e^{0.3\surd2}=1.5285$ $d=1/u=0.6543$ , and $p=(a-d)/(u-d)=0.5158$ . The probability on the "up branches" is 0.5158 and the probability on the "down branches" is 0.4842. There. are three nodes where early exercise could be desirable: D, G, and H. (The option has not vested at node B and is not in the money at the other nodes prior to maturity.) We assume that the probabilities that the holder will choose to exercise at nodes D, G, and H (conditional on no earlier exercise) have been estimated as $40\%,80\%$ , and $30\%$ , respectively. We suppose that the probability of an employee. leaving the company during each time step is $5\%$ . (This corresponds to an employee turnover rate of approximately. $2.5\%$ per year.) For the purposes of the. calculation, it is assumed that employees always leave at the end of a time period. If an employee leaves the company before an option has vested or when the option is out of the money, the option is forfeited. In other cases the option must be exercised immediately.  

At each node: Upper value $=$ Underlying asset price. Lower value $=$ Option price Values in bold are a result of early exercise.  

![](e6a8a1feb194e72d05ca58d3aa727a62c4e78403753b98010c5ca0518670b33e.jpg)  
Figure 16.1 Valuation of employee stock option in Example 16.2.  

The value of the option at the final nodes is its intrinsic value. Consider the nodes at time 6 years. Nodes I and J are easy. Since these nodes are certain to lead to nodes where the option is worth nothing, the value of the option is zero at these nodes. At node $_\mathrm{H}$ there is a $30\%$ chance that the employee will choose to exercise the option. In cases where the employee does not choose to exercise, there is a $5\%$ chance that the employee leaves the company and has to exercise. The total probability of exercise is therefore $0.3+0.7\times0.05=0.335.$ If the option is exercised, its value is $61.14-40=21.14.$ If it is not exercised, its value is  

$$
e^{-0.05\times2}(0.5158\times53.45+0.4842\times0)=24.95
$$  

The value of the option at node $\mathrm{H}$ is therefore  

$$
0.335\times21.14+0.665\times24.95=23.67
$$  

The value at node $\mathrm{G}$ is similarly  

$$
0.81\times102.83+0.19\times106.64=103.56
$$  

We now move on to the nodes at time 4 years. At node $\mathrm{F}$ the option is clearly. worth zero. At node E there is a. $5\%$ chance that the employee will forfeit the. option because he or she leaves the company and a $95\%$ chance that the option will be retained. In the latter case the option is worth  

$$
e^{-0.05\times2}(0.5158\times23.67+0.4842\times0)=11.05
$$  

The option is therefore worth. $0.95\times11.05=10.49.$ At node $\mathrm{\bfD}$ there is a 0.43 probability that the option will be exercised and a 0.57 chance that it will be retained. The value of the option is 56.44..  

Consider next the initial node and the nodes at time 2 years. The option has not vested at these nodes. There is a $5\%$ chance that the option will be forfeited and a $95\%$ chance that it will be retained for a further 2 years. This leads to the valuations shown in Figure 16.1. The valuation of the option at the initial node is 14.97. (This compares with a valuation of 17.98 for a regular option using the same tree.)  

# Exercise Multiple Approach  

Hull and White suggest a simple model where an employee exercises as soon as the option has vested and the ratio of the stock price to the strike price is above a certain level. They refer to the ratio of stock price to strike price that triggers exercise as the. "exercise multiple". The option can be valued using a binomial or trinomial tree. As outlined in Section 27.6, it is important to construct a binomial or trinomial tree where nodes lie on the stock prices that will lead to exercise. For example, if the strike price is $\$30$ and the assumption is that employees exercise when the ratio of the stock price to. the strike price is 1.5, the tree should be constructed so that there are nodes at a stock price level of $\$45$ The tree calculations are similar to those for Example 16.2 and take. account of the probability of an employee leaving the company.' To estimate the exercise multiple, it is necessary to calculate from historical data the average ratio of stock price to strike price at the time of exercise. (Exercises at maturity and those arising from the termination of the employee's job are not included in the calculation of the. average.) This may be easier to estimate from historical data than the expected life because the latter is quite heavily dependent on the particular path that has been followed by the stock's price.  

# A Market-Based Approach  

One way of valuing an employee stock option is to see what the market would pay for it. Cisco was the first to try this in 2006. It proposed selling options with the exact terms of its employee stock options to institutional investors. This approach was rejected by the SEC on the grounds that the range of investors bidding for the options was not wide enough.  

Zions Bancorp has suggested an alternative approach. It proposed that securities providing payoffs mirroring those actually realized by its employees be sold. Suppose that the strike price for a particular grant to employees is $\$40$ and it turns out that $1\%$ of employees exercise after exactly 5 years when the stock price is $\$60,2\%$ exercise after exactly 6 years when the stock price is $\$65$ , and so on. Then $1\%$ of the securities owned by an investor will provide a $\$20$ payoff after 5 years, $2\%$ will provide a payoff of $\$25$ after 6 years, and so on.  

Zions Bancorp tested the idea using its own stock option grant to its employees. It. sold the securities using a Dutch auction process. In this individuals or companies can. submit a bid indicating the price they are prepared to pay and the number of options. they are prepared to buy. The clearing price is the highest bid such that the aggregate number of options sought at that price or a higher price equals or exceeds the number of options for sale. Buyers who have bid more than the clearing price get their orders filled at the clearing price and the buyer who bid the clearing price gets the remainder.. Zions Bancorp announced that it had received SEC approval for its market-based. approach in October 2007, but the approach has not been used to any great extent..  

# Dilution  

The fact that a company issues new stock when an employee stock option is exercised. leads to some dilution for existing stock holders because new shares are being sold to employees at below the current stock price. It is natural to assume that this dilution takes place at the time the option is exercised. However, this is not the case. As explained in Section 15.10, stock prices are diluted when the market first hears about a stock option grant. The possible exercise of options is anticipated and immediately. reflected in the stock price. This point is emphasized by the example in Business. Snapshot 15.3.  

The stock price immediately after a grant is announced to the public reflects any. dilution. Provided that this stock price is used in the valuation of the option, it is not. necessary to adjust the option price for dilution. In many instances the market expects a company to make regular stock option grants and so the market price of the stock anticipates dilution even before the announcement is made..  

If a company is contemplating a stock option grant that will surprise the market, the. cost can be calculated as described in Example 15.7. This cost can be compared with benefits such as lower regular employee remuneration and less employee turnover..  
