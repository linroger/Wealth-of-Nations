---
tags:
  - bollerslev_1986
  - ewma_model
  - garch_model
  - mean_reversion
  - volatility_modeling
aliases:
  - GARCH
  - GARCH(1,1)
  - Generalized Autoregressive Conditional Heteroskedasticity
key_concepts:
  - EWMA model comparison
  - Exponentially declining weights
  - GARCH(1,1) model
  - Long-run average variance
  - Mean reversion of variance
---

# 23.3 The GARch(1,1) mODel  

We now move on to discuss what is known as the GARCH(1,1) model, proposed by Bollerslev in 1986.' The difference between the GARCH(1,1) model and the EWMA model is analogous to the difference between equation (23.4) and equation (23.5). In GARCH(1,1), $\overset{\cdot}{\sigma_{n}^{2}}$ is calculated from a long-run average variance rate, $V_{L}$ , as well as from $\sigma_{n-1}$ and $u_{n-1}$ . The equation for GARCH(1,1) is  

$$
\sigma_{n}^{2}=\gamma V_{L}+\alpha u_{n-1}^{2}+\beta\sigma_{n-1}^{2}
$$  

where $\gamma$ is the weight assigned to $V_{L},\alpha$ is the weight assigned to $u_{n-1}^{2}$ , and $\beta$ is the weight assigned to $\sigma_{n-1}^{2}$ . Since the weights must sum to unity, it follows that  

$$
\gamma+\alpha+\beta=1
$$  

The EWMA model is a particular case of GARCH(1,1) where $\gamma=0,\alpha=1-\lambda$ and $\beta=\lambda$  

The "(1,1)" in GARCH(1,1) indicates that. $\sigma_{n}^{2}$ is based on the most recent observa-. tion of $u^{2}$ and the most recent estimate of the variance rate. The more general ${\mathrm{GARCH}}(p,q)$ model calculates $\sigma_{n}^{2}$ from the most recent $p$ observations on $\overline{{u}}^{2}$ and the most recent $q$ estimates of the variance rate. GARCH(1,1) is by far the most. popular of the GARCH models..  

Setting $\omega=\gamma V_{L}$ , the GARCH(1,1) model can also be written  

$$
\sigma_{n}^{2}=\omega+\alpha u_{n-1}^{2}+\beta\sigma_{n-1}^{2}
$$  

This is the form of the model that is usually used for the purposes of estimating the parameters. Once $\omega,\alpha$ , and $\beta$ have been estimated, we can calculate $\gamma$ as $1-\alpha-\beta$ The long-term variance $V_{L}$ can then be calculated as $\omega/\gamma$ . For a stable GARCH(1,1) process we require $\alpha+\beta<1$ . Otherwise the weight applied to the long-term variance is. negative.  

# Example 23.2  

Suppose that a GARCH(1,1) model is estimated from daily data as  

$$
\sigma_{n}^{2}=0.000002+0.13u_{n-1}^{2}+0.86\sigma_{n-1}^{2}
$$  

Thiscorrespondsto $\alpha=0.13,\beta=0.86,$ and $\omega=0.000002$ .Because $\gamma=1-\alpha-\beta$ , it follows that $\gamma=0.01$ . Because $\omega=\gamma V_{L}$ , it follows that $V_{L}=0.0002$ . In other words, the long-run average variance per day implied by the model is 0.0002. This corresponds to a volatility of $\sqrt{0.0002}=0.\overset{\cdot}{0}14$ , or $1.4\%$ per day.  

Suppose that the estimate of the volatility on day $n\mathrm{~-~}1$ is $1.6\%$ per day, so that $\sigma_{n-1}^{2}\stackrel{\widehat{-}}{=}0.016^{2}=0.000256.$ and that on day $n\mathrm{~-~}1$ the market variable decreased by $1\%$ , so that $u_{n-1}^{2}=0.01^{2}=0.0001$ Then  

$$
\sigma_{n}^{2}=0.000002+0.13\times0.0001+0.86\times0.000256=0.00023516
$$  

The new estimate of the volatility is therefore $\sqrt{0.00023516}=0.0153$ , or $1.53\%$ per day.  

# The Weights  

Substituting for $\sigma_{n-1}^{2}$ in equation (23.9) gives  

$$
\sigma_{n}^{2}=\omega+\alpha u_{n-1}^{2}+\beta(\omega+\alpha u_{n-2}^{2}+\beta\sigma_{n-2}^{2})
$$  

or  

$$
\sigma_{n}^{2}=\omega+\beta\omega+\alpha u_{n-1}^{2}+\alpha\beta u_{n-2}^{2}+\beta^{2}\sigma_{n-2}^{2}
$$  

Substituting for $\sigma_{n-2}^{2}$ gives  

$$
\sigma_{n}^{2}=\omega+\beta\omega+\beta^{2}\omega+\alpha u_{n-1}^{2}+\alpha\beta u_{n-2}^{2}+\alpha\beta^{2}u_{n-3}^{2}+\beta^{3}\sigma_{n-3}^{2}
$$  

Continuing in this way, we see that the weight applied to. $u_{n-i}^{2}$ is $\alpha\beta^{i-1}$ . The weights. decline exponentially at rate. $\beta$ . The parameter $\beta$ can be interpreted as a "decay rate". It. is similar to. $\lambda$ in the EWMA model. It defines the relative importance of the observations on the $u$ 's in determining the current variance rate. For example, if $\beta=0.9$ , then $u_{n-2}^{2}$ is only $90\%$ as important as $u_{n-1}^{2};u_{n-3}^{2}$ is $81\%$ as important as $u_{n-1}^{2}$ ; and so on. The GARCH(1,1) model is similar to the EWMA model except that, in addition to assigning weights that decline exponentially to past. $u^{2}$ , it also assigns some weight to the long-run average volatility.  

# Mean Reversion  

The GARCH (1,1) model recognizes that over time the variance tends to get pulled back to a long-run average level of. $V_{L}$ . The amount of weight assigned to. $V_{L}$ is $\gamma=$ $1-\alpha-\beta$ The GARCH(1,1) is equivalent to a model where the variance $V$ follows the stochastic process  

$$
d V=a(V_{L}-V)d t+\xi V d z
$$  

where time is measured in days, $a=1-\alpha-\beta$ , and $\xi=\alpha\sqrt{2}$ (see Problem 23.14). This is a mean-reverting model. The variance has a drift that pulls it back to $V_{L}$ at rate $a$ When $V>V_{L}$ , the variance has a negative drift; when $V<V_{L}$ , it has a positive drift. Superimposed on the drift is a volatility $\xi$ . Chapter 27 discusses this type of model further.  
