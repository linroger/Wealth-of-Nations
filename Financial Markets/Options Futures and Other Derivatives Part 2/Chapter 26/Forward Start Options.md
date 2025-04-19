---
tags:
  - '#at_the_money_option'
  - '#employee_stock_options'
  - '#european_call_option'
  - '#forward_start_options'
  - '#non_dividend_paying_stock'
  - '#option_valuation'
  - '#risk_neutral_valuation'
---
# 26.5 FORWARD START OPTIONS  

Forward start options are options that will start at some time in the future. Sometimes. employee stock options, which were discussed in Chapter 16, can be viewed as forward start options. This is because the company commits (implicitly or explicitly) to granting. at-the-money options to employees in the future..  

Consider a forward start at-the-money European call option that will start at time $T_{1}$ and mature at time $T_{2}$ . Suppose that the asset price is $S_{0}$ at time zero and $S_{1}$ at time $T_{1}$ To value the option, we note from the European option pricing formulas in Chapters 15. and 17 that the value of an at-the-money call option on an asset is proportional to the asset price. The value of the forward start option at time $T_{1}$ is therefore $c S_{1}/S_{0}$ , where $c$ is the value at time zero of an at-the-money option that lasts for $T_{2}\mathrm{~-~}T_{1}$ . Using riskneutral valuation, the value of the forward start option at time zero is  

$$
e^{-r T_{1}}\hat{E}\Bigg[c\frac{S_{1}}{S_{0}}\Bigg]
$$  

where $\hat{E}$ denotes the expected value in a risk-neutral world. Since $c$ and $S_{0}$ are known and $\hat{E}[S_{1}]=S_{0}e^{(r-q)T_{1}}$ the value of the forward start option is $c e^{-q T_{1}}$ For a non-dividendpaying stock, $q=0$ and the value of the forward start option is exactly the same as the value of a regular at-the-money option with the same life as the forward start option.  
