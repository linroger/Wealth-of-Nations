---
tags:
  - cliquet_options
  - forward_start_option
  - monte_carlo_simulation
  - option_pricing
  - strike_reset_option
aliases:
  - cliquets
  - ratchet option
  - strike reset option
key_concepts:
  - Cliquet option definition
  - Monte Carlo valuation approach
  - Regular and forward options
  - Reset dates and strikes
  - Upper and lower payoff limits
---

# 26.6  CLIQUET OPTIONS  

A cliquet option (which is also called a ratchet or strike reset option) is a series of call or put options with rules for determining the strike price. Suppose that the reset dates are at times $t_{1},t_{2},\ldots,t_{n-1}$ with $t_{n}$ being the end of the cliquet's life. A simple structure would be as follows. The first option has a strike price $K$ equal to the initial asset price. and lasts between times 0 and $t_{1}$ ; the second option provides a payoff at time. $t_{2}$ with a strike price equal to the value of the asset at time $t_{1}$ ; the third option provides a payoff. at time $t_{3}$ with a strike price equal to the value of the asset at time $t_{2}$ ; and so on. This is a regular option plus $n\mathrm{~-~}1$ forward start options. The latter can be valued as described in Section 26.5.  

Some cliquet options are much more complicated than the one described here. For example, sometimes there are upper and lower limits on the total payoff over the whole. period; sometimes cliquets terminate at the end of a period if the asset price is in a certain range. When analytic results are not available, Monte Carlo simulation is often the best approach for valuation.  
