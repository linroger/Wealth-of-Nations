---
tags:
  - '#american_call_options'
  - '#american_put_options'
  - '#asset_price_redefinition'
  - '#continuous_yield'
  - '#discrete_dividends'
  - '#dividends_and_early_exercise'
  - '#option_exercise_value'
---
# 24.5 DIVIDENDS AND EARLY EXERCISE

If the asset is a stock and there are dividends, the procedure is slightly more complex. If we assume a continuous, constant yield of $\delta_{c}$ , the first term in the partial differential equation is changed slightly with $r_{c}-\delta_{c}$ replacing $r_{c}$ . Then S is redefined as $S e^{-\delta_{c}\tau}$ . If we assume discrete dividends, the partial differential equation is the same as the no-dividend case,. but the asset price is redefined as the asset price less the present value of the dividends..

If the options are American calls, then the possibility of early exercise must be con-. sidered. At each node we must determine if the asset is worth more exercised early. We simply calculate the value of the option the ordinary way and then calculate the exercise value, $\mathrm{max}(0,S+P V(D)-X)$ , where $P V(D)$ is the present value of all remaining dividends. during the life of the option. If the call is worth more exercised, then replace the calculated value of the option with the exercise value. This condition will occur with high dividends, low time to expiration, low time value, low volatility, and/or a low interest rate..

If the options are American puts, dividends are not required to justify early exercise. The same procedure as described for calls is followed, with appropriate substitution of the put boundary conditions in the topmost and bottommost rows and rightmost columns.
