---
linter-yaml-title-alias: PRICING AMERICAN OPTIONS
title: PRICING AMERICAN OPTIONS
tags:
  - american_option
  - binomial_tree
  - call_option
  - dividends
  - option_pricing
  - risk_neutral
aliases:
  - American Call Option
  - American Option Pricing
  - Early Exercise
  - Pricing American Options
key_concepts:
  - Accounting for dividends
  - American option payoff
  - Binomial tree for pricing
  - Risk neutral probability
  - Value of exercising option
---

[Teaching Note 8 American Options](Teaching%20Note%208%20American%20Options.md)
[PSET 7- Financial Instruments](PSET%207-%20Financial%20Instruments.md)
[PSET 7 Solutions](PSET%207%20Solutions.md)

# PRICING AMERICAN OPTIONS
## 1.1. PREAMBLE
3. Initial stock price:$𝑆_0$
4. Three period binomial tree
- a. Price increase 𝑢 with probability$𝑞$
- b. Price decrease 𝑑 with probability$(1 − 𝑞)$
5. No dividends
6. Interest rate on risk-free asset (continuously compounded): 𝑟

## 1.2. COMPUTING PRICE OF AN AMERICAN OPTION

1. Binomial tree for stock price evolution.
- $t=1$
	1. $S_u=S_0\cdot u$
	2. $S_d=S_0\cdot d$
		- ${} t=2 {}$
			1. $S_{uu}=S_{0}\cdot u\cdot u$
			2. $S_{ud}=S_{du}=S_0\cdot u\cdot d$
			3. $S_{dd}=S_0\cdot d\cdot d$
				- $t=3$
					1. $S_{\text{uuu}} = S _ { 0 }\cdot u\cdot u\cdot u$
					2. $S_{uud}=S_{udu}=S_{0}\cdot u\cdot u\cdot d$
					3. $S_{dud}=S_{ddu}=S_0\cdot d\cdot d\cdot u$
					4. $S_{ddd} =S_0\cdot d\cdot d\cdot d$
2. **Property of American option**: At maturity 𝑇, the payoff of an American option is equal to the payoff of a European option.
3. **Strategy for pricing American option**: For each node in the binomial tree, compute
	1. (i) the value of waiting until next period and
	2. (ii) the value of exercising the option in the current period.
4. Consider an American call option. 5. American call option payoff at maturity 𝑡 = 𝑇 = 3:
	1. $$\begin{gathered}

\bullet\quad\mathcal{C}_\text{uuu} =\max\{S_{uuu}-K\} \\
\bullet\quad\mathcal{C}_{uud} =\max\{S_{uud}-K\} \\
\bullet\quad\mathcal{C}_{dud} =\max\{S_{dud}-K\} \\
\bullet\quad\mathcal{C}_{ddd} =\max\{S_{ddd}-K\}

\end{gathered}$$
6. Risk neutral probability 𝑞∗ equates gross return on stock to gross return on risk-free asset
with interest rate 𝑟.

$$
q^{*}\cdot u+(1-q^{*})\cdot d=\exp(r)$$  
7. American call option (i) value of waiting, (ii) value of exercising, and (ii) value of option at 𝑡 = 𝑇 − 1 = 2:  
	+ Case 1: uu  
		+ $c_{\text{wait}}^{uu} = \exp(-r) \cdot [q^* \cdot c_{uuu} + (1 - q^*) \cdot c_{uud}]$  
		+ $c_{\text{exercise}}^{uu} = \max\{S_{uu} - K, 0\}$  
		+ ${} c_{uu} = \max\{c_{\text{wait}}^{uu}, c_{\text{exercise}}^{uu}\}$

	+ Case 2: ud = du  
		-  $c_{\text{wait}}^{ud} = \exp(-r) \cdot [q^* \cdot c_{udu} + (1 - q^*) \cdot c_{udd}]$ 
		- $c_{\text{exercise}}^{ud} = \max\{S_{ud} - K, 0\}$ 
		- $c_{ud} = \max\{c_{\text{wait}}^{ud}, c_{\text{exercise}}^{ud}\}$  
	
	+ Case 3: dd  
		-  $c_{\text{wait}}^{dd} = \exp(-r) \cdot [q^* \cdot c_{ddu} + (1 - q^*) \cdot c_{ddd}]$ 
		- $c_{\text{exercise}}^{dd} = \max\{S_{dd} - K, 0\}$
		- $c_{dd} = \max\{c_{\text{wait}}^{dd}, c_{\text{exercise}}^{dd}\}$ 

8. American call option (i) value of waiting, (ii) value of exercising, and (ii) value of option at 𝑡 = 𝑇 − 2 = 1:  
	+ Case 1: u  
		+ $c_{\text{wait}}^{u} = \exp(-r) \cdot [q^* \cdot c_{uu} + (1 - q^*) \cdot c_{ud}]$  
		+ $c_{\text{exercise}}^{u} = \max\{S_{u} - K, 0\}$  
		+ ${} c_{u} = \max\{c_{\text{wait}}^{u}, c_{\text{exercise}}^{u}\}$

	- Case 2: d  
		- $c_{\text{wait}}^{d} = \exp(-r) \cdot [q^* \cdot c_{du} + (1 - q^*) \cdot c_{dd}]$ 
		- $c_{\text{exercise}}^{d} = \max\{S_{d} - K, 0\}$
		- ${} c_{d} = \max\{c_{\text{wait}}^{d}, c_{\text{exercise}}^{d}\}$
	
9. American call option (i) value of waiting, (ii) value of exercising, and (ii) value of option at 𝑡 = 0:  
		- $c_{\text{wait}}^{0} = \exp(-r) \cdot [q^* \cdot c_{u} + (1 - q^*) \cdot c_{d}]$  
		- $c_{\text{exercise}}^{0} = \max\{S_{0} - K, 0\}$  
		- $c_{0} = \max\{c_{\text{wait}}^{0}, c_{\text{exercise}}^{0}\}$
## 1.2.1. EXERCISING AMERICAN OPTION PRIOR TO MATURITY

1. Exercise American option early at time 𝑡 and node 𝑗 if and only if$$C_j^{exercise}(t)>C_j^{wait}(t)$$

## 1.2.2. ACCOUNTING FOR DIVIDENDS IN PRICING AMERICAN OPTIONS

1. Dividends complicate matters because stock prices drop as a byproduct of dividends.
2. Consider a dividend yield 𝑦.
3. Construct the binomial tree for the pre-dividend stock price.
4. Construct the binomial tree for the post-dividend stock price.  

$$𝑆_{𝑝𝑜𝑠𝑡} = 𝑆_{𝑝𝑟𝑒} ⋅ (1 − 𝑦)$$

5. Note pre-dividend price one period ahead depends on post-dividend price this period.
	1. a. For example:$𝑆_{𝑢𝑢,𝑝𝑟𝑒}(2) = 𝑆_{𝑢,𝑝𝑜𝑠𝑡}(1) ⋅ 𝑢$
6. For call payoff, use pre-dividend stock price.
7. For put payoff, use post-dividend stock price.
8. **Intuition**: Put option is more valuable as the stock price falls.