---
title: BINOMIAL TREES AND OPTION PRICING MBA
aliases: [BINOMIAL TREES AND OPTION PRICING MBA]
linter-yaml-title-alias: BINOMIAL TREES AND OPTION PRICING MBA
---

# BINOMIAL TREES AND OPTION PRICING MBA
## 1. BINOMIAL TREES IN PHARMACEUTICALS

### 1.1. PARAMETERS

1. Let $i$ denote a pharmaceutical company
2. Stock price at maturity $t = T$: $S_{T,i} \in \\{S_d, S_u\\}$
	 a. Decrease scenario: $S_d$
	 b. Increase scenario: $S_u$
3. Probability distribution at maturity $t = T$
	 a. Decrease scenario: $q$
	 b. Increase scenario: $1 - q$
4. Systematic risk: $\beta_i$
5. Annualized risk-free interest rate (continuously compounded): $r_f$
6. Annualized expected excess return (annually compounded): $E[R_m] - r_f$

### 1.2. CAPM

1. Let $R_i$ denote the expected return on the stock of pharmaceutical company
2. Note $R_i$ is a random variable because stock price $S_{T,i} \in \\{S_d, S_u\\}$ at maturity $t = T$ is a random variable, and so the realization of $R$ depends on the realization of $S_T$.
3. Relationship between continuously compounded and annually compounded interest rates

	 $$1 + \bar{r}_f = \exp(r_f)$$

	 $$1 + \bar{r}_f = \exp(-r_f)$$

4. CAPM formula.

	 $$E[R_i] = \bar{r}_f + \beta_i \cdot [E[R_m] - r_f]$$

5. Note $E[R_i]$ varies (linearly) with $\beta_i$.

### 1.3. STOCK VALUATION AT INCEPTION

1. The stock price $S_{0,i}$ at inception $t = 0$ is equal to the expected discounted stock price at maturity $t = T$.
2. Expected stock price at maturity $t = T$ (i.e., the mean of the random variable $S_{T,i}$).

	 $$E_q[S_{T,i}] = q \cdot S_u + (1 - q) \cdot S_d$$

3. Use expected stock price return $E[R_i]$ to compute present-value as inception. $$(1 + E[R_i]) \cdot S_{0,i} = E[S_{T,i}]$$

### 1.4. AT-THE-MONEY OPTION UNDER DYNAMIC REPLICATION

6. An **at-the-money** ("ATM") call option features a strike price $K_i$ equal to the current spot stock price $S_0$ at inception $t = 0$, i.e. $K_i = S_{0,i}$
7. Payoff from option at maturity $t = T$ depends on realized stock price $S_{T,i}$ at maturity. $$c(S_{T,i}) = \begin{cases} \max\{S_d - K_i, 0\} & \text{if } S_{T,i} = S_d \\ \max\{S_u - K_i, 0\} & \text{if } S_{T,i} = S_u \end{cases}$$
8. Value of position in stocks at inception $t = 0$. $$\Delta_{i,0} = \frac{\max\{S_u - K_i, 0\} - \max\{S_d - K_i, 0\}}{S_u - S_d}$$
9. Value of position in bonds at inception $t = 0$. $$B_0 = e^{(-r ^f)} \cdot [\max\{S_u - K_i, 0\} - \Delta_{i,0} \cdot S_u]$$
10. Value of ATM option at inception $t = 0$.

	 $$V_0^{\text{ATM}} = \Delta_{i,0} \cdot S_{0,i} + B_0$$

6. Payoff from dynamic replication portfolio at maturity $t = T$ should replicate the payoff from the option.

- $$V_{T,i}^{DR}(S_{T,i}) = \begin{cases} \Delta_{i,0} \cdot S_d + \exp(r f) \cdot B_0 & \text{if } S_{T,i} = S_d \\ \Delta_{i,0} \cdot S_u + \exp(r f) \cdot B_0 & \text{if } S_{T,i} = S_u \end{cases}$$

### 1.5. AT-THE-MONEY OPTION UNDER RISK NEUTRAL METHODOLOGY

1. Risk neutral probability: The probability such that the risky asset (stock) yields an expected (gross) return equal to that of the risk-free asset (bond). $$q^* \cdot \frac{S_u}{S_0} + (1 - q^*) \cdot \frac{S_d}{S_0} = e^{r^f}$$
2. Expected stock price at maturity $t = T$ under risk neutral probability. $$E_{q^*}[S_{T,i}] = q^* \cdot S_u + (1 - q^*) \cdot S_d$$
3. Expected stock price at maturity $t = T$ under analysts' probability. $$E_q[S_{T,i}] = q \cdot S_u + (1 - q) \cdot S_d$$
4. Question: Why may the probabilities $(q, q^*)$ differ?
5. Value of ATM option under risk neutral methodology at inception $t = 0$. $$V_0^{\text{ATM}} = \exp(-r_f) \cdot [q^* \cdot \max\\{S_u - K_i, 0\\} + (1 - q^*) \cdot \max\\{S_d - K_i, 0\\}]$$

### 1.6. OPTION VALUE COMPARATIVE STATICS

#### 1.6.1. CHANGE IN ANALYST PROBABILITIES

1. Suppose that $q$ changes.
2. All else equal, $E_q[S_{T,i}]$ changes because the probability distribution has changed.
3. In turn, the present-value of the stock price $S_0$ at inception $t = 0$ changes.
4. Furthermore, the risk neutral probability $q^*$ changes due to change in $S_0$.

#### 1.6.2. CHANGE IN MARKET EXPOSURE

1. Suppose that $\beta_i$ changes.
2. All else equal, $E[R_i]$ changes by CAPM formula.
3. In turn, the present-value of the stock price $S_0$ at inception $t = 0$ changes.
4. Furthermore, the risk neutral probability $q^*$ changes due to change in $S_0$.

---