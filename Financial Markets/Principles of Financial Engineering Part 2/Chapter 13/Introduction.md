---
tags:
  - '#arbitrage_free_pricing'
  - '#black_derman_toy_model'
  - '#calibration'
  - '#fundamental_theorem_of_asset_pricing'
  - '#martingale_methods'
  - '#monte_carlo_procedure'
  - '#quanto_assets'
  - '#risk_neutral_measures'
---
# 13.1 INTRODUCTION  

The theorem discussed in the previous chapter establishes important no-arbitrage conditions that permit pricing and risk management using Martingale methods. According to these conditions, given unique arbitrage-free state prices, we can obtain a synthetic probability measure, $\tilde{P}$ under which all asset prices normalized by a particular. $Z_{t}$ become Martingales. Letting $C(S_{t},t)$ represent a security whose price depends on an underlying risk $S_{t}.$ we can write,  

$$
\frac{C(S_{t},t)}{Z_{t}}=E_{t}^{\tilde{P}}\left[\frac{C(S_{T},T)}{Z_{T}}\right]
$$  

As long as positive state prices exist, many such probabilities can be found and each will be associated with a particular normalization. The choice of the right working probability then becomes a matter of convenience and data availability..  

The equality in Eq. (13.1) can be evaluated numerically using various methods. The arbitragefree price $S_{t}$ can be calculated by evaluating the expectation and then multiplying by $Z_{t}.$ But to evaluate the expectation, we would need the probability $\tilde{P}$ hence, this must be obtained first. A further desirable characteristic is that the future value, $Z_{T}$ be constant, as it would be in the case of a default-free bond that matures at time $T.$ Hence, $T$ maturity bonds are good candidates for normalization.  

In this chapter, we show three applications of the fundamental theorem. The first application is the Monte Carlo procedure which can be interpreted as a general method to calculate the expectation in Eq. (13.1). This method can be applied straightforwardly when instruments under consideration are of European type. The procedure uses the tools supplied by the fundamental theorem together with the law of large numbers.'  

The second application of the fundamental theorem involves calibration. Calibration is the selection of model parameters using observed arbitrage-free prices from liquid markets. The chapter discusses simple examples of how to calibrate stochastic differential equations and tree models to market data using the fundamental theorem. This is done within the context of the Black-Derman-Toy (BDT) model.  

The third application of the fundamental theorem introduced in Chapter 12 is more conceptual in nature. We use quanto assets to show how the theorem can be exploited in modeling. Quanto assets provide an excellent vehicle for this, since their pricing involves switches between domestic and foreign risk-neutral measures. Techniques for switching between measures are an integral part of financial engineering and will be discussed further in the next chapter. The application to quantos provides the first step.  

Before we discuss these issues, a note of caution is in order. The discussion in this chapter should be regarded as an overview that presents examples for when to use the fundamental theorem, instead of being a source of how to implement such numerical techniques. Calculations using Monte Carlo or calibration are complex numerical procedures, and a straightforward application may not give satisfactory results. Interested readers can consult the sources provided at the end of the chapter.  
