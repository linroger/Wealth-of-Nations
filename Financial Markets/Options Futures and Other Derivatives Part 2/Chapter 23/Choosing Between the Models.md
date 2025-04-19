---
tags:
  - ewma_model
  - garch_model
  - mean_reversion
  - model_selection
  - variance_rates
aliases:
  - Choosing Models
  - Model Comparison
key_concepts:
  - Best-fit parameters
  - EWMA model
  - GARCH(1,1) mean reversion
  - Model stability
  - Switching models
---

# 23.4 CHOOSING BETWEEN THE MODELS  

In practice, variance rates do tend to be mean reverting. The GARCH(1,1) model incorporates mean reversion, whereas the EWMA model does not. GARCH (1,1) is therefore theoretically more appealing than the EwMA model..  

In the next section, we will discuss how best-fit parameters $\omega$ $\alpha$ , and $\beta$ in GARCH(1,1) can be estimated. Whenthe parameter wiszero, the GARCH(1,1) reduces to EWMA. In circumstances where the best-fit value of $\omega$ turns out to be negative, the GARCH(1,1) model is not stable and it makes sense to switch to the EWMA model..  
