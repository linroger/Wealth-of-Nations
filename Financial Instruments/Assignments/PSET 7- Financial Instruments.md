---
linter-yaml-title-alias: FINANCIAL INSTRUMENTS
title: PSET 7Financial Instruments
cssclasses:
  - academia
tags:
  - american_options
  - binomial_tree
  - call_option
  - financial_instruments
  - put_option
aliases:
  - Homework 7
  - PSET 7
key_concepts:
  - American call option
  - American put option
  - Binomial tree model
  - Continuously compounded rate
  - Strike price
---

# PSET 7Financial Instruments

BUS 35100 Winter 2024 John Heaton

## HOMEWORK 7

Due at the beginning of class 9

## 1 PART 1: AMERICAN OPTIONS

Let$S_0 = 100$,  and consider a 3-period binomial tree model in which in every period,  1year long,  there is 60% chance of$u = 1.1$increase,  or a 40% chance of$d = 1/u$decrease.

Assume that the stock pays no dividends,  and the continuously compounded interest rate is 2%.

- (a) Compute the value of an American call and put option with strike price$K = 100$(at-the-money).

> [!ANSWER]
> The price of the American call at t=0 is$10.1457358
>  ![500](92cebeb95864bc4a296361c40c2c2e6f.png)

> [!ANSWER]
> The price of the American put is$4.654588$
>  ![500](ec83b9f05d0ec6266517f834840946f0.png)

>

- (b) Are the American options computed in point (a) exercised before maturity? Discuss the intuition.

> [!answer]
> The American call option is not exercised early,  but is instead exercised at maturity. This is because the payoffs from waiting are higher than the payoffs from exercising early at each node,  and so the holder of the American call would wait until maturity to exercise. Additionally,  in the absence of dividends,  there is no advantage to early exercise,  as obtaining the stock early would yield no benefit. Early exercise would only result in the loss of the optionality value for the call option holder. The stock price could always increase further at the next node,  making the call option more valuable if held for an additional period.
> The American put option,  on the other hand,  is exercised early at T=2. The payoffs from exercising at this node is higher than the expected payoff from waiting.

(c) Let the continuously compounded interest rate be 5%. What are the values of the two ATM American options? Compute the times of early exercise and discuss.

> [!answer] The value of the American call under 5% continuously compounded interest rate is 15.424132. The value of the American put is 1.7824366. Once again,  the call is not exercised early. The put however,  is still exercised early at T=2.
>  ![500](7fec7bdb24c17f02a6b7187d6968379c.png)
>  ![500](15e0c2b3aa6e65d382d5f7b039fd160f.png)

(d) In case (a)-(b),  with interest rate still at r = 2%,  suppose that the firm now pays a 5% proportional dividend per year. How does your answer to point(c) change? Discuss.

> [!An of American Call with Dividends is 5.70483
>  ![500](attachment/f9ef49fd213f16fa6496f725291e2007.png)

> [!AN of American Put with Dividends is 11.0599
>  ![500](attachment/0475e63afdbf889c5d28d2ef1607dd82.png)
>

 ![500]/c9b86e20df71de92d351c1682a0dc27c.png)

## 2 PART 2: CITIGROUP'S DEFAULT PROBABILITY DURING THE CREDIT CRISIS

It is Feb 2010,  and you have been hired by the US Government to evaluate the effectiveness of the Paulson's plan to save the banks,  a plan that was announced on October 13,  2008. In particular,  you have been assigned to evaluate the impact of the Paulson's plan on Citigroup's probability of default. In this homework you must compute the (true) probability of default of Citigroup by using the KMV model. The file HW7 data.xls contains important information about Citigroup (as well as JPMorgan and Goldman Sachs,  but computing their probability of default is optional). In addition,  it contains a simple solver to compute the Implied Volatility *and* Implied Stock value to match both a call option value and its volatility (see Teaching Notes 9). As you will see,  you will need a lot of assumptions to use the KMV model,  and so make sure to write the assumptions you make in your report (see below for some tips). For instance,  how do you treat deposits and short-term debt? Please,  compute the probabilities of default at the following two dates:

10/10/2008 The day before the government announcement of the bailout program.

10/14/2008 The day after the announcement.

Proceed as follows:

|                          | Citigroup |
| ------------------------ | --------- |
| Deposits                 | 780.343   |
| Short term               | 352.274   |
| Long term                | 396.097   |
| Other                    | 395.693   |
| Total liabilities        | 1924.407  |
| Total equity             | 126.062   |
| Total assets             | 2050.469  |
| Mkt Cap on 2/13/2009     | 19.02     |
| Stock Price on 2/13/2009 | 3.49      |

| Date     | Stock Price | Market Cap | Return   | 22 day volatility. |
| -------- | ----------- | ---------- | -------- | ------------------ |
| 10/14/08 | 18.35       | 100.0049   | 0.1675   | 1.894658           |
| 10/13/08 | 15.52       | 84.58178   | 0.110241 | 1.803801           |
| 10/10/08 | 13.9        | 75.75301   | 0.087142 | 1.755075           |

| Date     | Stock Price | Market Cap | Return | 22 day volatility. |
| -------- | ----------- | ---------- | ------ | ------------------ |
| 10/14/08 | 18.35       | 100.0049   | 0.1675 | 1.894658           |

| Date     | Market yield on U.S. Treasury securities at 1-year   constant maturity,    quoted on investment basis |
| -------- | -------------------------------------------------------------------------------------------------- |
| 10/10/08 | 0.0108                                                                                             |
| 10/14/08 | 0.0122                                                                                             |

- Compute the number of shares (you will need them to compute the market capitalization in the next point.)

> [!answer]
> - On 10/14/2008,  Citi had$\frac{101,   393,   223,   246.00}{186.20}=544,   539,   330$

- Compute the value of assets and volatility of assets to match the market cap and equity volatility at the two dates above. The assets and volatility of assets will be different across dates. Please,  note the tips at the end.
- Corobability of default with one year to maturity. Note that KMV identifies the "Default Point" as short term debt + 1/2 long term debt.
 ![500](attachment/f38b8d64617760fde019fdc8e395e583.jpeg)

After you do the calculations above,  answer the following:

(a) What was the effect of the bailout announcement on the probability of default? Discuss.

- The ouncement slightly increased the probability of default from 9.122% on 10/10 to 10.132% on 10/14. This seems to be counterintuitive,  since we typically expect the announcement of a bailout to significantly bring down the expected probability of default.
-  ![500](attachment/7fe8097bf9c95a2919f0af227b856007.png)
(b) How does your answer to point (a) changes if you keep the volatility of assets σ constant to the value estimated on 10/10/2008 when you recompute the asset value at time 10/14/2008? (it is a simple change in the solver: only change assets but not volatility) Provide an intuition for the difference with (a).
- Keeping volatility constant,  (ie.$\sigma_{A}=0.72614$on 10/10 and 10/14,  ) the distance to default,  or$d_{2}=1.4686$and the expected frequency of default,  or$N(-d_{2})=7.097\%$. Thus,  the probability of default decreases with the announcement of the bailout. This makes more sense. One property of the Merton Model is the leverage effect,  in which volatility increases when the value of equity decreases. If we keep volatility constant at the lower 10/10 level of 0.72614 (as opposed to volatility increasing to 0.79557),  we expect the value of equity to be higher,  and therefore the value of the asset to be higher.
(c) What was the credit spread before and after the announcement (choose what you think is most reasonable of your answers in (a) or (b),  if you find any difference).
- The ad before the announcement (on 10/10) was 0.02898 and the credit spread after the announcement (on 10/14) is 0.03982
-  ![500](attachment/3fdac17bd64dfe392b2f8595a83ade7f.png)
(d) The Paulson's Plan promised Citigroup a cash infusion of 25 billion from the US Treasury. Consider your calculated asset and equity values on 10/10/2008,  and assume Citi suddenly gets the 25 bil cash infusion. What is the transfer to bond holders,  if any? Discuss.
- The bt increases from 321.72876 before the bailout to 324.85172 after the bailout. This difference of about 4 billion is the transfer to bondholders from the bailout package.
-  ![500](attachment/d68acb98496df7b7c8a89aac79b2d836.png)
## TIPS

This exercise is complicated by the existence of multiple type of securities. Clearly,  we need assumptions,  and no set of assumptions is particularly good (we just need a better model). Here is a set of assumptions that may be reasonable.

- To compute the value of equity,  the residual claim after all of the debt,  other liabilities,  and deposits have been paid,  you may assume:
1. All deposits and short-term debt is super short-term,  and in fact it will be paid instantly. This implies that for equity calculation purposes,  $V − D − S$is the relevant variable,  where V is the total value of the firm,  D is the total amount of deposits,  and S is the total amount of short-term debt.
1. Even after all short-term debt S and deposits D are paid out,  you can still use Black and Scholes on the residual$V − D − S$to compute the value of equity. Note that you still have long term debt L and other liabilities O to repay at T.
1. Assume that the value of assets V has percentage volatility σ both before and after you pay short-term debt and deposits. This implies that the volatility of equity today (before paying out everything) is
$${\mathrm{Volatility~of~Equity}}=N(d_{1})\times{\frac{V}{E}}\times\sigma$$
where both$d_1$and$E$use$V − D − S$instead of$V$.