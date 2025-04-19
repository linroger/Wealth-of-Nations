---
tags:
  - at_the_money
  - call_option
  - option_greeks
  - option_sensitivity
  - put_option
aliases:
  - Greeks Sensitivity
  - Option Sensitivities
key_concepts:
  - Call and put parity
  - Delta, Gamma, Vega
  - Lognormal distribution assumption
  - Option values and Greeks
  - Time to expiration impact
  - Volatility impact on Greeks
---

# 14.8 GREEK SENSITIVITIES

We now consider the sensitivities of option values and Greeks to changes in the underlying. For this illustration we start with options that have the following parameters,. $X=100$ $r_{c}=5.0\%$ $\sigma=30\%$ $T-t=1.0$ year, and $\delta=0.0\%$ . Figure 14.1 illustrates option values and Greeks over the stock price range from O to 200.

Several observations can be made from Figure 14.1. First, the call delta moves toward zero as the asset price falls and the call delta moves to one as the asset price rises (with the dividend yield assumed zero). Second, both gamma and vega directly reflect the lognormal distribution assumption with its positive skewness. Third, the difference between call and put deltas, thetas, and rhos are constants and relatively close to one based on the put-call parity relationship.

We now consider the sensitivities of option values and Greeks to changes in volatility. For this illustration, we again start with options that are at-the-money with $S=X=100$ $r_{c}=5.0\%$ $T-t=1.0$ year, and $\delta=0.0\%$ . Figure 14.2 illustrates option values and Greeks over the volatility range from $0.0\%$ to $60\%$

Several observations can be made from Figure 14.2. First, based on the value graph, we observe that the difference between the call and the put is simply. $S-X e^{-r_{c}\tau}$ . Second, both gamma and vega are very sensitive as volatility approaches zero. Third, the difference between call and put thetas and rhos are constant across volatilities..

![](dc6aed5fa414f64782e1a7fd8464a9304220a378b81a05570b49996be9250385.jpg)
FIGURE 14.1 Sensitivity of Option Values and Greeks to Changes in Stock Price

We now consider the sensitivities of option values and Greeks to changes in time to expiration. For this illustration, we again start with options that are at-the-money with $S=X=100$ $r_{c}=5.0\%$ $\sigma=30\%$ and $\delta=0.0\%$ . Figure 14.3 illustrates option values and Greeks over the time to expiration range from zero to two years.

![](6fe6fa7d1224048a0eaf6b5b403a971355385f26c1cdb137158ee8e6bf7199cc.jpg)
FIGURE 14.2 Sensitivity of Option Values and Greeks to Changes in Volatility

Several observations can be made from Figure 14.3. First, based on the value graph,. we observe that the at-the-money call is worth more than the at-the-money put, where the value difference reflects the magnitude of. $S-X e^{-r_{c}\tau}$ . Second, both gamma and vega are. very sensitive as time to expiration approaches zero. Third, the difference between call and put thetas shrinks as the time to expiration shortens. Finally, the rhos have opposite signs and increase in absolute value as time to expiration increases..

![](3ff646bf5b431cccaef78667c89dca8bff5976bd2e260c1f83ceac434e87ad06.jpg)
FIGURE 14.3 Sensitivity of Option Values and Greeks to Changes in Time to Expiration
