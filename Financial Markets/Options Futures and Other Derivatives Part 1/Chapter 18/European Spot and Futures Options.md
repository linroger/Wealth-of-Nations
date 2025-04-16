---
tags:
  - '#american_style_options'
  - '#european_call_option'
  - '#european_put_option'
  - '#futures_options'
  - '#futures_price'
  - '#option_maturity'
  - '#option_payoff'
  - '#spot_price'
---
# 18.3 EUROPEAN SPOT AND FUTURES OPTIONS  

The payoff from a European call option with strike price $K$ on the spot price of an asset is  

$$
\operatorname*{max}(S_{T}-K,0)
$$  

where $S_{T}$ is the spot price at the option's maturity. The payoff from a European call option with the same strike price on the futures price of the asset is  

$$
\operatorname*{max}(F_{T}-K,0)
$$  

where $F_{T}$ is the futures price at the option's maturity. If the futures contract matures at  

the same time as the option, then. $F_{T}=S_{T}$ and the two options are equivalent..   
Similarly, a European futures put option is worth the same as its spot put option.   
counterpart when the futures contract matures at the same time as the option.  

Most of the futures options that trade are American-style. However, as we shall see,it is useful to study European futures options because the results that are obtained can be used to value the corresponding European spot options.  
