---
tags:
  - '#american_option'
  - '#binomial_tree'
  - '#black_scholes_merton'
  - '#european_option'
  - '#intrinsic_value'
  - '#option_valuation'
  - '#shout_option'
  - '#trinomial_tree'
---
# 26.12 SHOUT OPTIONS  

A shout option is a European option where the holder can "shout" to the writer at one time during its life. At the end of the life of the option, the option holder receives either the usual payoff from a European option or the intrinsic value at the time of the shout, whichever is greater. Suppose the strike price is. $\$50$ and the holder of a call shouts when. the price of the underlying asset is. $\$60$ . If the final asset price is less than $\$60$ , the holder. receives a payoff of. $\$10$ . If it is greater than. $\$60$ , the holder receives the excess of the. asset price over $\$50$  

A shout option has some of the same features as a lookback option, but is considerably less expensive. It can be valued by noting that if the holder shouts at a. time $\tau$ when the asset price is $S_{\tau}$ the payoff from the option is.  

$$
\mathrm{max}(0,S_{T}-S_{\tau})+(S_{\tau}-K)
$$  

where, as usual,. $K$ is the strike price and $S_{T}$ is the asset price at time. $T$ The value at time $\tau$ if the holder shouts is therefore the present value of. $S_{\tau}-K$ (received at time $T$ plus the value of a European option with strike price $S_{\tau}$ . The latter can be calculated. using Black-Scholes-Merton formulas..  

A shout option is valued by constructing a binomial or trinomial tree for the underlying asset in the usual way. Working back through the tree, the value of the option if the holder shouts and the value if the holder does not shout can be calculated at each node.  

The option's price at the node is the greater of the two. The procedure for valuing a shout option is therefore similar to the procedure for valuing a regular American option.  
