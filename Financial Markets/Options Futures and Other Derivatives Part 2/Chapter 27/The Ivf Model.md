---
tags:
  - '#european_option_pricing'
  - '#exotic_option_pricing'
  - '#implied_volatility_function'
  - '#ivf_model'
  - '#local_volatility_model'
  - '#option_pricing_model'
  - '#plain_vanilla_options'
  - '#risk_neutral_process'
---
# 27.3 THE IVF MODEL  

The parameters of the models we have discussed so far can be chosen so that they provide an approximate fit to the prices of plain vanilla options on any given day. Financial institutions sometimes want to go one stage further and use a model that provides an exact fit to the prices of these options.16 In 1994 Derman and Kani, Dupire, and Rubinstein developed a model that is designed to do this. It has become known as the implied volatility function (IVF) model or the local volatility model.17 It provides an exact fit to the European option prices observed on any given day, regardless of the shape of the volatility surface.  

The risk-neutral process for the asset price in the model has the form  

$$
d S=[r(t)-q(t)]S d t+\sigma(S,t)S d z
$$  

where $r(t)$ is the instantaneous forward interest rate for a contract maturing at time $t$ and $q(t)$ is the dividend yield as a function of time. The volatility. $\sigma(S,t)$ is a function of both $S$ and $t$ and is chosen so that the model prices all European options consistently.  

with the market. It is shown both by Dupire and by Andersen and Brotherton-Ratcliffe that $\sigma(S,t)$ can be calculated analytically:18  

$$
[\sigma(K,T)]^{2}=2~\mathrm{{\frac{}{}}}~[\sigma{}\mathrm{mkt}/\partial T+q(T)c_{\mathrm{mkt}}+K[r(T)-q(T)]\partial c_{\mathrm{mkt}}/\partial K
$$  

where $c_{\mathrm{mkt}}(K,T)$ is the market price of a European call option with strike price. $K$ and maturity $T$ If a sufficiently large number of European call prices are available in the market, this equation can be used to estimate the o(S, t) function.19  

Andersen and Brotherton-Ratcliffe implement the model by using equation (27.4) together with the implicit finite difference method. An alternative approach, the implied tree methodology suggested by Derman and Kani and Rubinstein, involves constructing a tree for the asset price that is consistent with option prices in the market.  

When it is used in practice the IVF model is recalibrated daily to the prices of plain vanilla options. It is a tool to price exotic options consistently with plain vanilla. options. As discussed in Chapter 20 plain vanilla options define the risk-neutral probability distribution of the asset price at all future times. It follows that the IVF model gets the risk-neutral probability distribution of the asset price at all future times correct. This means that options providing payoffs at just one time (e.g., cash-ornothing and asset-or-nothing options) are priced correctly by the IVF model. However, the model does not necessarily get the joint distribution of the asset price at two or more times correct. This means that exotic options such as compound options and barrier options may be priced incorrectly.20  
