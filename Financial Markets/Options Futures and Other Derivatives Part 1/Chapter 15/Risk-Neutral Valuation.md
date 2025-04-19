---
tags:
  - binomial_model
  - black_scholes_merton
  - derivative_pricing
  - forward_contracts
  - risk_neutral_valuation
aliases:
  - Black-Scholes
  - Risk-Neutral Pricing
key_concepts:
  - Black-Scholes equation
  - Expected payoff
  - Forward contract valuation
  - Risk-free interest rate
  - Risk-neutral valuation
---

# 15.7 RISK-NEUTRAL VALUATION  

We introduced risk-neutral valuation in connection with the binomial model in Chapter 13. It is without doubt the single most important tool for the analysis of derivatives. It arises from one key property of the Black-Scholes-Merton differential equation (15.16). This property is that the equation does not involve any variables that are affected by the risk preferences of investors. The variables that do appear in the equation are the current stock price, time, stock price volatility, and the risk-free rate of interest. All are independent of risk preferences.  

The Black-Scholes-Merton differential equation would not be independent of risk preferences if it involved the expected return, $\mu$ , on the stock. This is because the value of $\mu$ does depend on risk preferences. The higher the level of risk aversion by investors, the higher $\mu$ will be for any given stock. It is fortunate that. $\mu$ happens to drop out in the derivation of the differential equation.  

Because the Black-Scholes-Merton differential equation is independent of risk preferences, an ingenious argument can be used. If risk preferences do not enter the equation, they cannot affect its solution. Any set of risk preferences can, therefore, be used when evaluating $f.$ In particular, the very simple assumption that all investors are risk neutral can be made.  

In a world where investors are risk neutral, the expected return on all investment assets is the risk-free rate of interest, $r.$ The reason is that risk-neutral investors do not require a premium to induce them to take risks. It is also true that the present value of any cash flow in a risk-neutral world can be obtained by discounting its expected value at the risk-free rate. The assumption that the world is risk neutral does, therefore, considerably simplify the analysis of derivatives.  

Consider a derivative that provides a payoff at one particular time. It can be valued using risk-neutral valuation by using the following procedure:.  

1. Assume that the expected return from the underlying asset is the risk-free interest rate, $r$ (i.e., assume $\mu=r$   
2. Calculate the expected payoff from the derivative.   
3. Discount the expected payoff at the risk-free interest rate.  

It is important to appreciate that risk-neutral valuation (or the assumption that all investors are risk neutral) is merely an artificial device for obtaining solutions to the Black-Scholes-Merton differential equation. The solutions that are obtained are valid in all worlds, not just those where investors are risk neutral. When we move from a riskneutral world to a risk-averse world, two things happen. The expected payoff from the derivative changes and the discount rate that must be used for this payoff changes. It happens that these two changes always offset each other exactly.  

# Application to Forward Contracts on a Stock  

We valued forward contracts on a non-dividend-paying stock in Section 5.7. In Example 15.5, we verified that the pricing formula satisfies the Black-Scholes-Merton differential equation. In this section we derive the pricing formula from risk-neutral valuation. We make the assumption that interest rates are constant and equal to $r.$ This is somewhat more restrictive than the assumption in Chapter 5.  

Consider a long forward contract that matures at time $T$ with delivery price, $K$ . As indicated in Figure 1.2, the value of the contract at maturity is  

$$
S_{T}-K
$$  

where $S_{T}$ is the stock price at time. $T.$ From the risk-neutral valuation argument, the value of the forward contract at time O is its expected value at time. $T$ in a risk-neutral. world discounted at the risk-free rate of interest. Denoting the value of the forward contract at time zero by. $f,$ this means that.  

$$
f=e^{-r T}\hat{E}(S_{T}-K)
$$  

where $\hat{E}$ denotes the expected value in a risk-neutral world. Since $K$ is a constant, this equation becomes  

$$
f=e^{-r T}\hat{E}(S_{T})-K e^{-r T}
$$  

The expected return $\mu$ on the stock becomes $r$ in a risk-neutral world. Hence, from equation (15.4), we have  

$$
\hat{E}(S_{T})=S_{0}e^{r T}
$$  

Substituting equation (15.19) into equation (15.18) gives  

$$
f=S_{0}-K e^{-r T}
$$  

This is in agreement with equation (5.5).  
