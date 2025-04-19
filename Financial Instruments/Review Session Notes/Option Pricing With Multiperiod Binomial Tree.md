---
linter-yaml-title-alias: OPTION PRICING WITH MULTIPERIOD BINOMIAL TREE
title: OPTION PRICING WITH MULTIPERIOD BINOMIAL TREE
tags:
  - binomial_tree
  - dividend_yield
  - european_option
  - option_pricing
  - stock_price
aliases:
  - BOPM
  - Binomial Option Pricing
  - Multiperiod Binomial Model
key_concepts:
  - European call option
  - Multiperiod binomial tree
  - Option pricing with dividends
  - Replicating portfolio
  - Stock price payoff tree
---

# OPTION PRICING WITH MULTIPERIOD BINOMIAL TREE

1. Multiperiod Binomial Tree 1.1. Preamble
1. Three periods: 𝑖 ∈ {0,1,2}
2. Stock price in initial period: 𝑆0
3. Stock price can either rise or fall by 10% in each subsequent period 𝑖 ∈ {1,2} 4. Discrete compounding per period interest rate: 𝑟
5. European call option has strike price: 𝐾 = 𝑆0

## 1.2. OPTION PRICING WITH MULTIPLE PERIODS

1. **Overview**: Construct a replicating portfolio of stocks and bonds that replicates the
payoff of the call option.
2. Stock price payoff tree.
	a. Period 𝑖 = 0: 𝑆0
		i. Period 𝑖 = 1
			1. 𝑆𝑢 = 𝑢 ∙ 𝑆0
			2. 𝑆𝑑 = 𝑑 ∙ 𝑆0
				1. a. Period 𝑖 = 2
					1. i. 𝑆𝑢𝑢 = 𝑢 ∙ 𝑆𝑢
					2. Ii. 𝑆𝑢𝑑 = 𝑑 ∙ 𝑆𝑢 = 𝑢 ∙ 𝑆𝑑 = 𝑆𝑑𝑢
					3. Iii. 𝑆𝑑𝑑 = 𝑑 ∙ 𝑆𝑑
3. Call option payoff tree.
	1. a. Period 𝑖 = 0: 𝑐0 (to be determined)
		1. i. Period 𝑖 = 1
			1. 𝑐𝑢 (to be determined)
			2. 𝑐𝑑 (to be determined)
				1. a. Period 𝑖 = 2
					1. i. 𝑐𝑢𝑢 = max{𝑆𝑢𝑢 − 𝐾, 0}
					2. $\begin{array}{ll}\mbox{ii.}&c_{\rm rad}=\max\{S_{\rm ud}-K\}\\ \mbox{iii.}&c_{\rm dd}=\max\{S_{\rm dd}-K\}\end{array}$
4. Work backwards from final node in the tree to determine option prices (𝑐0, 𝑐𝑢, 𝑐𝑑).
5. Period 𝑖 = 1:
	1. a. Node 𝑢.
		1. b. Position in stocks ("delta").

$$\Delta_{u}={\frac{c_{u u}-c_{u d}}{S_{u u}-S_{u d}}},$$

			c. Position in bonds (note use of discrete discounting).  

$$B_{u}=\frac{1}{1+r}\cdot(c_{u u}-\Delta_{u}\cdot S_{u u})$$

			d. Value of replicating portfolio in stocks and bonds.  

$$c_{u}:=V_{u}^{R P}=\Delta_{u}\cdot S_{u}+B_{u}$$

			e. Node 𝑑.  
				i. Position in stocks ("delta").  

$$\Delta_{d}={\frac{c_{u d}-c_{d d}}{S_{u d}-S_{d d}}}.$$

				ii. Position in bonds (note use of discrete discounting).  

$$B_{d}=\frac{1}{1+r}\cdot(c_{u d}-\Delta_{d}\cdot S_{u d})$$

				iii. Value of replicating portfolio in stocks and bonds.  

$$c_{d}:=V_{d}^{R P}=\Delta_{d}\cdot S_{d}+B_{d}$$

6. Period 𝑖 = 0.
	i. Position in stocks ("delta").

$$\Delta_{0}={\frac{c_{u}-c_{d}}{S_{u}-S_{d}}}$$

	ii. Position in bonds (note use of discrete discounting).  

$$B_{0}=\frac{1}{1+r}\cdot(c_{u}-\Delta_{0}\cdot S_{u})$$

	iii. Value of replicating portfolio in stocks and bonds.  

$$c_{0}:=V_{0}^{BP}=\Delta_{0}\cdot S_{0}+B_{0}$$

## 1.3. PORTFOLIO SELF-FINANCING

1. Compute value of "inherited" portfolio and cost of "current" portfolio. 2. Consider node 𝑢 at 𝑖 = 1. 3. Value of "inherited" portfolio set up at 𝑖 = 0.

$$V_{u}^{1}=\Delta_{0}\cdot S_{u}+B_{0}\cdot(1+r)$$

4. Cost of "future" portfolio set up at 𝑖 = 1.

$$V_{u}^{2}=\Delta_{u}\cdot S_{u}+B_{u}$$

5. **Question**: What is the value of (𝑉𝑢1 − 𝑉𝑢2)?

## 1.4. OPTION PRICING WITH DIVIDENDS

1. **Takeaway**: Stock prices must fall in response to dividends. 2. Stock price payoff tree with dividend yield 𝑦 at period 𝑡 = 1
a. Period 𝑖 = 0: 𝑆0
i. Period 𝑖 = 1
1. 𝑆𝑢 = (1 − 𝑦) ∙ 𝑢 ∙ 𝑆0 2. 𝑆𝑑 = (1 − 𝑦) ∙ 𝑑 ∙ 𝑆0
a. Period 𝑖 = 2
i. 𝑆𝑢𝑢 = 𝑢 ∙ 𝑆𝑢
ii. 𝑆𝑢𝑑 = 𝑑 ∙ 𝑆𝑢 = 𝑢 ∙ 𝑆𝑑 = 𝑆𝑑𝑢
iii. 𝑆𝑑𝑑 = 𝑑 ∙ 𝑆𝑑
3. Note that the tree is recombining at period 𝑖 = 2, i.e. 𝑆𝑢𝑑 = 𝑆𝑑𝑢
4. Follow the same steps as before to compute option prices. 5. Consider node 𝑢 at period 𝑖 = 1.
a. Position in stocks.

$$\Delta_{u}={\frac{c_{u u}-c_{u d}}{S_{u u}-S_{u d}}}.$$

b. Position in bonds.

$$B_{u}=\frac{1}{1+r}\cdot(c_{u u}-\Delta_{u}\cdot S_{u u})$$

c. Value of option.
𝑐𝑢 ≔ 𝑉𝑢𝑅𝑃 = Δ𝑢 ∙ 𝑆𝑢 + 𝐵𝑢

6. Consider node 𝑑 at period 𝑖 = 1.
a. Position in stocks.

$$\Delta_{d}=\frac{c_{d u}-c_{d d}}{S_{d u}-S_{d d}}.$$

b. Position in bonds.

$$B_{d}=\frac{1}{1+r}\cdot(c_{d u}-\Delta_{d}\cdot S_{d u})$$

c. Value of option.

$$c_{d}:=V_{d}^{R P}=\Delta_{d}\cdot S_{d}+B_{d}$$

𝑁𝐷 = 𝑑 ∙ 𝑆0,

7. Use stock prices without dividend at period 𝑖 = 1, namely 𝑆𝑢𝑁𝐷 = 𝑢 ∙ 𝑆0 and 𝑆𝑑
when pricing options at the initial period 𝑖 = 0.
a. Position in stocks.

$$\Delta_{0}=\frac{c_{u}-c_{d}}{S_{u}^{N D}-S_{d}^{S D}}$$

b. Position in bonds.

$$B_{0}=\frac{1}{1+r}\cdot(c_{u}-\Delta_{0}\cdot S_{u}^{N D})$$

c. Value of option.

$$c_{0}=\Delta_{0}\cdot S_{0}+B_{0}$$

 ![500](IMG-20240913171226939.png