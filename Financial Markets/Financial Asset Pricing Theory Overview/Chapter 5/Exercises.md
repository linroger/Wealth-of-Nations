---
tags:
  - exercises
  - expected_utility
  - insurance
  - probability_distributions
  - risk_aversion
aliases:
  - consumption plans
  - exercise problems
key_concepts:
  - actuarially fair insurance
  - expected utility maximization
  - one-period choice problem
  - probability distributions
  - risk averse consumer
---

# 5.8 Exercises  

EXERCISE 5.1 Give a proof of Theorem 5.3.  

EXERCISE 5.2 (Adapted from Problem 3.3 in Kreps (1990).) Consider the following two probability distributions of consumption. $\pi_{1}$ gives 5, 15, and 30 (dollars) with probabilities $1/3$ $5/9$ , and $1/9$ , respectively. $\pi_{2}$ gives 10 and 20 with probabilities $2/3$ and $1/3$ , respectively.  

(a) Show that we can think of. $\pi_{1}$ as a two-step gamble, where the first gamble is identical to. $\pi_{2}$ . If the outcome of the first gamble is 10, then the second gamble gives you an additional 5 (total 15) with probability $1/2$ and an additional. $^{-5}$ (total 5) also with probability $1/2$ If the outcome of the first gamble is 20, then the second gamble gives you an additional 10 (total 30) with probability $1/3$ and an additional $^{-5}$ (total 15) with probability $2/3$  

(b) Observe that the second gamble has mean zero and that. $\pi_{1}$ is equal to $\pi_{2}$ plus mean-zero noise. Conclude that any risk-averse expected utility maximizer will prefer $\pi_{2}$ to $\pi_{1}$  

EXERCISE 5.3 (Adapted from Chapter 3 in Kreps (1990).) Imagine a greedy, risk-averse, expected utility maximizing consumer whose end-of-period income level is subject to some uncertainty. The income will be. $Y$ with probability $p$ and $Y^{\prime}<Y$ with probability $1-\bar{p}$ . Think of $\Delta=Y-Y^{\prime}$ as some loss the consumer might incur due an accident. An insurance company is willing to insure against this loss by paying $\Delta$ to the consumer if she sustains the loss. In return, the company wants an upfront premium of $\delta$ . The consumer may choose partial coverage in the sense that if she pays a premium of. $a\delta$ , she will receive $a\Delta$ if she sustains the loss. Let. $u$ denote the von Neumann-Morgenstern utility function of the consumer. Assume for simplicity that the premium is paid at the end of the period.  

(a) Show that the first order condition for the choice of $a$ is  

$$
\bar{p}\delta u^{\prime}(Y-a\delta)=(1-\bar{p})(\Delta-\delta)u^{\prime}(Y-(1-a)\Delta-a\delta).
$$  

(b) Show that if the insurance is actuarially fair in the sense that the expected payout $(1-\bar{p})\Delta$ equals the premium $\delta$ , then the consumer will purchase full insurance, i.e. $a=1$ is optimal.  

(c) Show that if the insurance is actuarially unfair, meaning $(1-\bar{p})\Delta<\delta$ , then the consumer will purchase partial insurance, i.e. the optimal $a$ is less than 1.  

EXERCISE 5.4  Consider a one-period choice problem with four equally likely states of the world at the end of the period. The consumer maximizes expected utility of end-of-period wealth. The current wealth must be invested in a single financial asset today. The consumer has three assets to choose from. All three assets have a current price equal to the current wealth of the consumer. The assets have the following end-of-period values:  

<html><body><table><tr><td>state</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>probability</td><td>0.25</td><td>0.25</td><td>0.25</td><td>0.25</td></tr><tr><td>asset 1</td><td>100</td><td>100</td><td>100</td><td>100</td></tr><tr><td>asset 2</td><td>81</td><td>100</td><td>100</td><td>144</td></tr><tr><td>asset 3</td><td>36</td><td>100</td><td>100</td><td>225</td></tr></table></body></html>  

(a) What asset would a risk-neutral individual choose?   
(b) What asset would a power utility investor, $\begin{array}{r}{u(W)=\frac{1}{1-\gamma}W^{1-\gamma}}\end{array}$ choose if $\gamma=0.5\colon$ If $\gamma=2$ If $\gamma=5$ \~.  

Now assume a power utility with $\gamma=0.5$  

(c) Suppose the individual could obtain a perfect signal about the future state before she makes her asset choice. There are thus four possible signals, which we can represent by $s_{1}=\{1\}$ $s_{2}=\{2\}$ $s_{3}=\{3\}$ , and $s_{4}=\{4\}$ .What is the optimal asset choice for each signal? What is her expected utility before she receives the signal, assuming that the signals have equal probability?   
(d) Now suppose that the individual can receive a less-than-perfect signal telling her whether the state is in $s_{1}=\lbrace1,4\rbrace$ or in $s_{2}=\{2,3\}$ . The two possible signals are equally likely. What. is the expected utility of the investor before she receives the signal?.  

EXERCISE 5.5 Consider an individual with log utility, $u(c)=\ln{c}$ .What is her certainty equivalent and risk premium for the consumption plan which with probability 0.5 gives her $(1-\alpha)\bar{c}$ and with probability 0.5 gives her $(1+\alpha)\bar{c}$ ? Confirm that your results are consistent with numbers for $\gamma=1$ shown in Table 5.5.  

EXERCISE 5.6 Use Equation (5.5) to compute approximate relative risk premia for the consumption gamble underlying Table 5.5 and compare with the exact numbers given in the table.  
