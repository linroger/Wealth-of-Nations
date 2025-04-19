---
tags:
  - arbitrage
  - financial_mathematics
  - interest_rates
  - options
  - probability_theory
aliases:
  - FinMath
  - Financial Math
  - Intro to FinMath
key_concepts:
  - Assets, portfolios, arbitrage
  - Binomial tree pricing
  - Black-Scholes model
  - Compound interest, discounting
  - European/American options
  - Forward contracts definition
  - Forward rates and Libor
  - Futures contracts
  - Interest rate swaps
  - Sample space, events, variables
---

# Introduction to Financial Mathematics



# Contents  

# 1 Probability Theory: Basics 6  

1.1 Sample Space, Events, Random Variables 6   
1.2 Probability Measure . 7   
1.3 Discrete Random Variables 9   
1.4 Expectation 10  

# 2 Assets, Portfolios, and Arbitrage 13  

2.1 Assets 13   
2.2 Portfolios 14   
2.3 Arbitrage 15   
2.4 Monotonicity and Replication 16  

# 3. Compound Interest, Discounting, and Basic Assets 18  

3.1 Interest Rates and Compounding. 18   
3.2 Time Value of Money, Zero Coupon Bonds, and Discounting 22   
3.3 Annuities 24   
3.4 Bonds 28   
3.5 Stocks 29   
3.6 Foreign Exchange Rates 29  

# 4. Forward Contracts 30  

4.1 Derivative Contracts 30   
4.2 Forward Contract Definition 30  
4.3 Value of Forward. 31   
4.4 Payoff 31   
4.5 Forward Price 33   
4.6 Value of Forward and Forward Price for Asset Paying No Income. 33   
4.7 Value of Forward and Forward Price for Asset Paying Known Income 36   
4.8 Value of Forward and Forward Price for Stock Paying Known Dividend Yield 37   
4.9 Forward Price for Currency 39   
4.10 Relationship Between Value of Forward and Forward Price. 40  

# 5. Forward Rates and Libor 41  
5.1 Forward Interest Rates. 41   
5.2 Forward Zero Coupon Bond Prices 45   
5.3 Libor 48   
5.4 Fixed and Floating Payments 49   
5.5 Forward Rate Agreements 50   
5.6 Forward Libor Rate 51   
5.7 Forward Rates Unified 53  

# 6. Interest Rate Swaps 56  

6.1 Swap Definition 56   
6.2 Value of Swap . 57   
6.3 Forward Swap Rate 59   
6.4 Value of Swap in Terms of Forward Swap Rate 60   
6.5 Swaps as Difference Between Bonds . 60   
6.6 Par or Spot-Starting Swaps . 61  

# 7 Futures Contracts 63  

7.1 Physical and Cash Settlement 63   
7.2 Futures Definition 63   
7.3 Futures Prices When Rates Are Constant: Result and Examples . . 65   
7.4 Futures Prices When Rates Are Constant: Proof 66   
7.5 Futures Convexity Correction . 68  

# 8. Options 69  

8.1 European Option Definitions 69   
8.2 American Option Definitions 70   
8.3 More Definitions 70   
8.4 Option Prices 71   
8.5 Put-Call Parity 72   
8.6 European Call Prices for Assets Paying No Income. 74   
8.7 Equality of American and European Call Prices for Assets Paying No Income 75   
8.8 No Early Exercise for American Calls on Assets Paying No Income  .. 76   
8.9 Put Prices for Assets Paying No Income 76   
8.10 Call and Put Prices for Stocks Paying Known Dividend Yield .. 78   
8.11 Call and Put Spreads 79   
8.12 Butterflies and Convexity of Option Price 81   
8.13 Digital Options 83  

# 9. Probability Theory: Conditioning and Independence 86  

9.1 Conditional Probability 86   
9.2 Independence 87   
9.3 Conditional Expectation 88  

# 10. The Binomial Tree 91  

10.1 One-Step Binomial Tree 91   
10.2 Replication on the One-Step Binomial Tree 92   
10.3 Risk-Neutral Pricing: Introduction 93   
10.4 Risk-Neutral Pricing: One-Step Binomial Tree 94   
10.5 Multi-Step Binomial Tree . 96   
10.6 Derivative Pricing for the Binomial Tree: Part 1 99  

10.7 Derivative Pricing for the Binomial Tree: Part 2 101  

# 11. Risk-Neutral Pricing and The General Fundamental Theorem  

106  

11.1 Equivalent Probability Measures. 106   
11.2 The Fundamental Theorem of Asset Pricing 107  

# 12 Probability Theory: Normal Distribution and Central Limit Theorem 111  

12.1 Normal Distribution . 111   
12.2 Standard Normal Distribution . 112   
12.3 Central Limit Theorem 112  

# 13 Continuous-Time Limit and Black-Scholes 113  

13.1 Binomial Tree to Black-Scholes 113   
13.2 Black-Scholes Model 115   
13.3 Black-Scholes Formula 116   
13.4 Properties of Black-Scholes Formula 118   
13.5 The Greeks: Delta and Vega 120   
13.6 Volatility 127  

# Preface  

The most important concept in this course is the concept of arbitrage. Informally, arbitrage is profit without risk.  

These notes are designed around the following learning objectives:  

1. Learn how to price assets so that no arbitrage opportunities appear for competitors.   
2. Learn how to recognize and exploit arbitrage opportunities.  

The course is divided into two parts.  

In Part 1, we study the basic theory of mathematical finance.  

Part 1 consists of Chapters 1 to 8. In Chapter 1, we present the basic probability theory we. will need. In Chapter 2, we introduce the fundamental concepts of portfolio, replication, and arbitrage. In Chapter 3, we discuss compound interest, zero coupon bonds, and the time value of money. In Chapter 4, we introduce derivative contracts and the study the simplest type: forward contracts. In Chapter 5, we study forward interest rates and forward rate agreements, including on Libor. In Chapter 6, we study swap contracts. In Chapter 7, we give a brief introduction to futures contracts. In Chapter 8, we introduce options and. study some basic properties of option prices; however, we leave the non-trivial problem of actually calculating the price of options to Part 2 of these notes..  

In Part 2, we study the problem of option pricing.  

Part 2 consists of Chapters 9 to 13. In Chapter 9, we present some more advanced probability theory needed to tackle the option pricing problem. In Chapter 10, we introduce the. discrete-time binomial tree model, and we learn how to price options and other derivatives in this model using replication and the new idea of risk-neutral pricing. In Chapter 11,. we briefly discuss risk-neutral pricing and the fundamental mental theorem of asset pricing. in a general setting. In Chapter 12, we present the probability theory needed to introduce the Black-Scholes model, namely the normal distribution and the central limit theorem. In Chapter 13, we introduce the Black-Scholes model as the continuous-time limit of the binomial tree model and derive the famous Black-Scholes formula of option pricing.  

# Chapter 1  

# Probability Theory: Basics  

The future values of financial assets are uncertain. Financial mathematics is built on probability theory, the mathematical theory of modeling uncertainty. We will give a brief introduction to probability theory (without measure-theoretic subtleties and with minimal set theory). The purpose is not to be completely rigorous, but to build the correct intuition..  

# 1.1 Sample Space, Events, Random Variables  

Consider an uncertain outcome that we wish to model, such as a die roll, the result of an experiment, or the state of the world an hour from now.  

Definition 1.1.1. The set of all possible outcomes is called the sample space. It is typically denoted by $\Omega$ . Individual outcomes, i.e. elements of $\Omega$ , are typically denoted by $\omega$ $\triangle$  

Definition 1.1.2. A subset of possible outcomes is called an event.  

Example 1.1.1. Flip a fair coin three times.  

Sample space: $\Omega=\{H H H,H H T,H T H,T H H,H T T,T H T,T T H,T T T\}$ The set $A=\{H H H,H H T,H T H,H T T\}$ is the event that the first flip is heads. The set. $B=$ $\{H T H,H T T,T T H,T T T\}$ is the event that the second flip is tails..  

Definition 1.1.3. A random variable $X$ is a function from the sample space $\Omega$ to the set of real numbers $\mathbb{R}$ . In other words, $X$ assigns to each outcome $\omega\in\Omega$ a real number $X(\omega)$ (The symbol "\* $\in^{\cdot}$ ' means "in'). $\triangle$  

Example 1.1.2. Flip a fair coin twice. Sample space: $\Omega=\{H H,T T,H T,T H\}$ .A random variable: $X=$ number of heads. If the outcome is $\omega=H T$ , then $X(\omega)=1$ . If the outcome is $\omega=T T$ , then $X(\omega)=0$ . Etc.  

If the outcome is $\omega=H H$ , what is $X(\omega)$ C  

Events can be written in terms of random variables.  

Example 1.1.3. Flip a fair coin twice. Sample space: $\Omega=\{H H,T T,H T,T H\}$ $X=$ number of heads. The event that number of heads is at least one is  

$\begin{array}{r l}&{\left\{X\geq1\right\}=\left\{\omega\in\Omega:X(\omega)\geq1\right\}}\ &{\qquad=\mathrm{~set~of~all~outcomes~}\omega\mathrm{~i}}\ &{\qquad=\left\{H H,H T,T H\right\}.}\end{array}$ n the sample space $\Omega$ such that $X(\omega)\geq1$  

# 1.2 Probability Measure  

Definition 1.2.1. A probability measure $P$ on a sample space $\Omega$ is a function that assigns. to each event $A$ a real number $P(A)$ such that $0\leq P(A)\leq1$ $P(\Omega)=1$ and $P$ is countably additive (as defined below). The number $P(A)$ is called the probability of the. event $A$ $\triangle$  

Interpretation. The probability $P(A)$ encodes our knowledge or belief about how likely event $A$ is. $P(A)=0$ means the event cannot occur. $P(A)=1$ means the event is certain to occur.  

To define countably additive, we need some other definitions first.  

# Definition 1.2.2.  

The event $\varnothing=\{\}$ is the called the empty event. It is the event that nothing happens.   
The intersection of events $A$ and $B$ is the event $A\cap B=\{\omega:\omega\in A$ and $\omega\in B\}$ It is the event that both $A$ and $B$ occur.   
The events $A$ and $B$ are called disjoint if. $A\cap B=\emptyset$ . This means that there is no outcome $\omega$ where both $A$ and $B$ occur.   
The union of events $A$ and $B$ is the event $A\cup B=\{\omega:\omega\in A{\mathrm{~or~}}$ $\omega\in B\}$ . It is the event that $A$ or $B$ (or both) occur. $=$   
The union of an infinite sequence of events $A_{1},A_{2},A_{3},...$ is the event $\textstyle\bigcup_{i=1}^{\infty}A_{i}=$ $\{\omega:\omega\in A_{i}$ for at least one $i=1,2,\ldots\}$ . It is the event that at least one of $A_{1},A_{2},A_{3},...$ occurs.  

Definition 1.2.3. $P$ is countably additive means that for every infinite sequence of events $A_{1},A_{2},A_{3},...$ such that $A_{i}$ and $A_{j}$ are disjoint for all $i\neq j$ , we have  

$$
P\left(\bigcup_{i=1}^{\infty}A_{i}\right)=\sum_{i=1}^{\infty}P(A_{i}).
$$  

We won't need to work with the countable additive property of probability measures in this course. The follow intuitive properties will be enough.  

Theorem 1.2.1. If $P$ is a probability measure, then  

$\begin{array}{r}{P(\{\omega_{1},\omega_{2},...,\omega_{n}\})=\sum_{i=1}^{n}P(\{\omega_{i}\})}\end{array}$ for any set of outcomes $\{\omega_{1},\ldots,\omega_{n}\}$ . $P(X\leq a)=1-P(X>a)$ for all random variables $X$ and all real numbers $a$  

Example 1.2.2. Roll two fair six-sided dice. The possible outcomes $\omega$ are pairs $(i,j)$ where $i$ is the number shown on the first die and $j$ is the number shown on the second die. The sample space is $\Omega=\{(1,1),(1,2),(1,3),\ldots,(6,6)\}$ . The dice are fair, so all outcomes are equally likely, i.e., the probability measure $P$ satisfies  

$$
P(\{\omega\})=\frac{1}{36}\mathrm{forall}\omega\in\Omega.
$$  

Consider random variables $X_{1}=$ number on first die, $X_{2}=$ number on second die, $Y=$ sum of the dice.  

For the outcome $\omega=(2,5)$  

$$
\begin{array}{r}{\begin{array}{r l}&{X_{1}(\omega)=X_{1}((2,5))=2}\ &{X_{2}(\omega)=X_{2}((2,5))=5}\ &{Y(\omega)=Y((2,5))=2+5=7}\end{array}}\end{array}
$$  

Sum of the dice is at least 11 Event: $\{Y\ge11\}=\{(5,6),(6,5),(6,6)\}$ Probabiliy: $\begin{array}{r}{P(Y\geq11)=\frac{3}{36}=\frac{1}{12}}\end{array}$  

Sum of the dice is less than 11 Event: $\{Y<11\}$ Probabiliy: $\begin{array}{r}{P(Y<11)=1-P(Y\geq11)=1-\frac{1}{12}=\frac{11}{12}}\end{array}$  

Both dice show same number   
Event: $\{X_{1}=X_{2}\}=\{(1,1),(2,2),(3,3),(4,4),(5,5),(6,6)\}$   
Probability: P(X = X2) = 36 =  

Remark 1.2.3. If the sample space is finite, the probability measure $P$ can be defined by defining $P(\{\omega\})$ for every outcome $\omega$ . If the sample space is infinite, it may not be possible. to define the probability measure. $P$ just by defining $P(\{\omega\})$ for every outcome $\omega$ . The next example illustrates this. Except for Chapters 13 and 14, we can assume the sample spaces we work with are finite and. $P(\{\omega\})>0$ for every outcome $\omega$ in the sample space. $\triangle$  

Example 1.2.4. Pick a point uniformly at random from the interval. $[0,1]$ . Sample space:   
$\Omega=[0,1]$ . The word "uniformly' here means that the probability that the point belongs to   
a given subinterval $[a,b]$ in $[0,1]$ is proportional to the length of the interval:   
$P([a,b])=b-a$ for $0\leq a\leq b\leq1$   
In particular, $P(\{c\})=P([c,c])=0\mathrm{forany}0\leq c\leq1.$  

Exercise 1.2.1. Flip a fair coin 5 times. Let $X=$ totals number of heads.  

(a) Write down three possible outcomes $\omega$ from the sample space $\Omega$ (b) How many outcomes are in the sample space?   
(c) Compute $P(\{\omega\})$ for each outcome $\omega$ you wrote down in part (a). (d) Compute $X(\omega)$ for each outcome $\omega$ you wrote down in part (a). (e) Find $P(X\leq3)$ . Hint: Find $P(X>3)$ first.  

Exercise 1.2.2. Consider a coin where the probability of heads is $0<p<1$ .Do not assume $p=1/2$ . Flip it until the first tails occurs. Let. $X=$ number of flips needed to see the first tails.  

(a) How many outcomes are in the sample space?   
(b) Find $P(X=1)$ $P(X=2)$ , and $P(X=3)$   
(c) Write down a formula for. $P(X=k)$ , where $k$ is a positive integer.  

Exercise 1.2.3. Prove Theorem 1.2.1.  

# 1.3 Discrete Random Variables  

Let $X$ be a random variable on a sample space $\Omega$  

Definition 1.3.1. A countable set is a set that can be listed as either a finite sequence $a_{1},a_{2},\ldots,a_{n}$ or an infinite sequence $a_{1},a_{2},a_{3},\dots$ $\triangle$  

Example 1.3.1. The sets $\{-1,0,1\}$ $\{1,1/2,\dots,1/10\}$ $\mathbb{N}=\{1,2,3,...\}$ , and $\mathbb{Z}~=$ $\{\cdot\cdot\cdot,-2,-1,0,1,2,...\}$ are countable sets. $\mathbb{R}$ is an uncountable set.. $\triangle$  

Definition 1.3.2. Let $X$ be a random variable on a sample space $\Omega$ . The range of $X$ is  

$X$ is called a discrete random variable if $R(X)$ is a countable set..  

Example 1.3.2. Flip a fair coin until the first tails occurs. $X=$ number of heads in the first two flips and. $Y=$ total number of heads.. $R(X)=\{0,1,2\}$ and $R(Y)=\{0,1,2,...\}.X$ and $Y$ are discrete. $\triangle$  

Remark. The sample space in Example 1.3.2 can be taken to be the set of all possible infinite sequences of heads and tails, like.  

# HTHTTTTTTH HTTTHTHTHTH H HTH H H HTTTHTT .  

In particular, the sample space is an infinite set.  

Remark. Except in Chapter 13, all the random variables we work with are discrete.  

Exercise 1.3.1. Show that $\mathbb{R}$ (the set of all real numbers) is uncountable. Show that $\mathbb{Q}$ (the set of all rational numbers) is countable.  

# 1.4 Expectation  

Definition 1.4.1. Let $\Omega$ be a sample space, let $P$ be probability measure on $\Omega$ , and let $X$ be a discrete random variable on $\Omega$ . The expectation of $X$ (with respect to $P$ ) is  

$$
\operatorname{\mathbb{E}}(X)=\sum_{k\in R(X)}k P(X=k).
$$  

The expectation of. $X$ is a weighted average of the possible outputs of $X$ , with the weights.   
being the probability of each output..  

Terminology: expectation $=$ expected value $=$ average $=$ mean $=$ first moment  

Example 1.4.1. Roll a fair six-sided die. The sample space is $\Omega=\{1,2,3,4,5,6\}$ . Since the die is fair, the probability measure. $P$ is $\begin{array}{r}{P(\{\omega\})=\frac{1}{6}}\end{array}$ for all $\omega\in\Omega$ $X=$ the number shown. $R(X)=\left\{1,2,3,4,5,6\right\}$ . The expectation of $X$ is  

$$
\operatorname{\mathbb{E}}(X)=\sum_{k\in R(X)}k P(X=k)=(1)(1/6)+(2)(1/6)+...+(5)(1/6)+(6)(1/6)=21/6
$$  

Theorem 1.4.2 (Linearity of Expectation). Let $X$ and $Y$ be discrete random variables, and let $a,b,c$ be real numbers (constants). Then  

$$
\mathbb{E}(a X+b Y+c)=a\mathbb{E}(X)+b\mathbb{E}(Y)+c.
$$  

Example 1.4.3. Roll three fair six-sided dice. Let $Z$ be the sum of the dice. Find $\mathbb{E}(Z)$  

The easiest way is to use linearity of expectation and something we already know. Define $X_{i}=$ number on $i$ -th die. Then $Z=X_{1}+X_{2}+X_{3}.$ $\mathbb{E}X_{i}=3.5$ , and  

$$
\operatorname{\mathbb{E}}(Z)=\operatorname{\mathbb{E}}(X_{1})+\operatorname{\mathbb{E}}(X_{2})+\operatorname{\mathbb{E}}(X_{3})=3.5+3.5+3.5=10.5.
$$  

We could instead compute $\mathbb{E}(Z)$ from the definition. First note that $\begin{array}{r}{P(\{\omega\})=\frac{1}{6^{3}}=\frac{1}{216}}\end{array}$ for each $\omega=(i,j,k)$ in the sample space $\Omega=\{(i,j,k):1\leq i,j,k\leq6\}=\{(1,1,1),(1,1,2),\ldots,(6,6,6)\}.$ Then calculate $P(Z=n)=P(\{(i,j,k):i+j+k=n\}$ ) for $n=3,\ldots,18$ . Finally compute  

$$
\mathbb{E}(Z)=\sum_{n\in R(Z)}n P(Z=n)=3\cdot P(Z=3)+4\cdot P(Z=4)+\cdot\cdot\cdot+18\cdot P(Z=18)
$$  

We leave it as a challenge for the reader to check that we get the same result.  

Theorem 1.4.4 (Change of Variable or Law of the Unconscious Statistician). Let $X$ be a discrete random variable and let $g:\mathbb{R}\rightarrow\mathbb{R}$ be a function. The expectation of the random variable $g(X)$ is  

$$
\mathbb{E}(g(X))=\sum_{k\in R(g(X))}k P(g(X)=k)=\sum_{k\in R(X)}g(k)P(X=k).
$$  

Remark 1.4.5. The first sum in (1.4.1) is just the definition of the expectation of $g(X)$ The two sums are equal, but the second is often easier to compute.. $\triangle$  

Example 1.4.6. Let $X$ be a random variable with $\textstyle P(X=k)={\frac{1}{3}}$ for $k=-1,0,1$ . Find $\mathbb{E}(X^{2})$  

We take $g(x)=x^{2}$  

Using the second sum in (1.4.1),  

$$
\mathbb{E}(X^{2})=\sum_{k\in{\cal R}(X)}k^{2}P(X=k)=(-1)^{2}\left(\frac{1}{3}\right)+(0)^{2}\left(\frac{1}{3}\right)+(1)^{2}\left(\frac{1}{3}\right)=\frac{2}{3}
$$  

To use the first sum in (1.4.1), we first note that $R(X^{2})=\{0,1\}$ $P(X^{2}=0)=P(X=$ $\begin{array}{r}{0)=\frac{1}{3}}\end{array}$ , and $\begin{array}{r}{P(X^{2}=1)=P(X=-1\mathrm{or}X=1)=P(X=-1)+P(X=1)=\frac{2}{3}}\end{array}$ Then  

$$
\mathbb{E}(X^{2})=\sum_{k\in R(X^{2})}k P(X^{2}=k)=(0)\left({\frac{1}{3}}\right)+(1)\left({\frac{2}{3}}\right).
$$  

It was slightly easier to use the second sum in (1.4.1) because we didn't need to work out $R(X^{2})$ and $P(X^{2}=k)$ . We leave it as a challenge for the reader to come up with more. complicated examples that increase or reverse the difference in difficulty. $\triangle$  

Exercise 1.4.1. Use Definition 1.4.1 (not Theorem 1.4.2 or Theorem 1.4.4) to prove that $\mathbb{E}(c X)=c\mathbb{E}(X)$ for every discrete random variable $X$ and real constant $c$  

Exercise 1.4.2. Consider a class of 50 students. For each student, a fair six-sided die will be rolled to determine the student's final grade. If the die shows 6, the grade is 90. If the die shows any other number, the grade is 40. Let $X_{i}$ be the grade of the $i$ -th student.  

(a) Let $X_{i}$ be the grade of the $i$ -th student. Find $\mathbb{E}(X_{i})$   
(b) Let $Z$ be the class average. Write down the formula for $Z$ in terms of $X_{1},\ldots,X_{50}$   
(c) If only 7 students roll a 6, what is the class average?   
(d) What is the expectation of the class average? Exercise 1.4.3. Consider a coin where the probability of heads is $p$ . Flip the coin $n$ times. $X_{i}=1$ $i$ th flip is heads, 0 if $i$ th flip is tails. Define $\textstyle Y=\sum_{i=1}^{n}X_{i}$   
(a) Express the event that there are exactly $k$ heads in terms of $Y$   
(b) Find $\mathbb{E}(Y)$  

Exercise 1.4.4. The variance of a random variable $X$ is  

$$
\operatorname{Var}(X)=\mathbb{E}((X-\mathbb{E}(X))^{2}).
$$  

It is the average squared-distance between $X$ and its average $\mathbb{E}(X)$  

(a) Use the properties of expectation to prove $\operatorname{Var}(X)=\mathbb{E}(X^{2})-(\mathbb{E}(X))^{2}$ (b) Let $X$ be the number shown after rolling of a fair six-sided die. Find $\mathbb{E}(X^{2})$ and $\operatorname{Var}(X)$  

# Chapter 2  

# Assets, Portfolios, and Arbitrage  

In this chapter, we explain our mathematical model of the financial market, introduce basic definitions, and (most) importantly introduce the concept of arbitrage.  

# 2.1 Assets  

Definition 2.1.1. An asset (or security or instrument) is a valuable thing that can be owned and traded.  

Examples of assets are stocks (shares) , bonds, cash (domestic or foreign currency), real estate, and resource rights. (Don't worry if you don't know what these are yet.).  

Definition 2.1.2. The value or price of an asset is the amount of cash it can be traded for. We measure the amount of cash in units of a fixed but typically unspecified currency.. Unless we are dealing with multiple currencies, we omit writing words like "dollar' or. currency symbols like $\$1$  

We model the prices of assets over time. The times we consider are real numbers $T\geq0$ We will always measure time in units of years.  

All information (asset prices, interest rates, etc.) in the past and present is assumed to be known. Future information is assumed to be unknown, i.e., random.  

Let $S_{T}$ denote the price at time $T$ of a certain asset. Let $t$ denote the present time. If. $T<t$ (the past) or $T=t$ (the present), then we assume. $S_{T}$ is a known constant. If $T>t$ (the future), then we assume. $S_{T}$ is a random variable. This reflects the idea that asset prices in the past and present are known, while future asset prices are unknown. We sometimes use "current"' instead of "present.".  

The prices at futures times of all assets are assumed to be random variables defined on some fixed sample space $\Omega$ . We can think of the sample space as all possible states of the  

world.  

We assume there is a probability measure $P$ defined on $\Omega$ . If $S_{T}$ is the price of an asset at some future time $T$ $P(S_{T}=10)$ is the probability that the price of the asset will be 10 at time $T$ $P$ represents the objective or real-world probabilities, which in practice are determined a priori from observations on the market or on the basis of historical stock data. In other words, $P$ is estimated by looking at the real world.  

# 2.2 Portfolios  

Definition 2.2.1. A portfolio (or trading strategy) is a collection of assets along with a sequence of trades of those assets at specified times. Only certain types are trades are allowed: Trades cannot spontaneously create or destroy value and trades cannot be based on future information.  

Example 2.2.1. Letd $S_{T}^{(F)}$ denote the price of FB stock at time $T$ Let $S_{T}^{(G)}$ denote the pricee of GOOGL stock at time $T$  

Here is an example portfolio: At the present time $T=0$ , the portfolio consists of 3 shares of FB, 5 shares of GOOGL, and 10, 000 cash. At time $T=1$ , sell 5 shares of GOOGL for $5S_{1}^{(G)}$ cash. At time $T=2$ buy 10 shares of FB stock for $10S_{2}^{(F)}$ cash.  

We often consider portfolios that just hold assets and makes no trades. For example: At present time $T=t$ , the portfolio is 8 shares of FB stock..  

Trades cannot spontaneously create or destroy value. For example, trades like the following are not allowed.  

At time $T=1$ , your mom and dad give you 1, 000, 000 dollars.   
At time $T=2$ you throw all your AAPL stocks into the fires of Mount Doom.  

You may think of this as a law of conservation of value for portfolios or as portfolios as. being closed systems. Note that specifying what the portfolio contains at the present time does not count as a trade, so it doesn't violate this rule..  

Trades cannot be based on future information. For example, a trade like the following. is not allowed: At the time AAPL stock reaches its maximum value for the time period between now and 10 years from now, sell all shares of AAPL stock. However, a trade like the following is allowed: If at anytime during the next 10 years AAPL stock price is more than 500, sell all shares of AAPL stock..  

Remark 2.2.2. A portfolio can hold any amount of an asset, including fractional and negative amounts. A holding of. $-1$ asset is a debt of 1 asset. For example, if you have no apples. and you owe Johnny 3 apples, you have. $-3$ apples.  

Definition 2.2.2. The value of a portfolio at time $T$ is the sum of the values of the assets. in the portfolio at time. $T$ $V^{A}(T)$ denotes the value of a portfolio. $A$ at time $T$ . If $t$ is the current time and $T>t$ , then $V^{A}(t)$ is a constant and $V^{A}(T)$ is a random variable.. $\triangle$  

Example 2.2.3. Let $A$ be the first portfolio from Example 2.2.1: At the present time $T=0$ $A$ consists of 3 shares of FB, 5 shares of GOOGL, and 10, 000 cash. At time $T=1$ , sell 5 shares of GOOGL for $5S_{1}^{(G)}$ Cash. At time $T=2$ buy 10 shares of FB stock for $10S_{2}^{(F)}$ cash.  

Remember $S_{T}^{(F)}$ is the price of FB stock a ime $T$ and $S_{T}^{(G)}$ is the price of GOOGL stok at time $T$ . We assume (for now) that the cash does not accrue interest. Then  

$$
\begin{array}{r l}&{V^{A}(0)=3S_{0}^{(F)}+5S_{0}^{(G)}+10,000}\ &{V^{A}(1)=3S_{1}^{(F)}+(10,000+5S_{1}^{(G)})=3S_{1}^{(F)}+5S_{1}^{(G)}+10,000}\ &{V^{A}(2)=13S_{2}^{(F)}+(10,000+5S_{1}^{(G)}-10S_{2}^{(F)})=3S_{2}^{(F)}+5S_{1}^{(G)}+10,000.}\end{array}
$$  

# 2.3 Arbitrage  

Definition 2.3.1. A portfolio $A$ is called an arbitrage portfolio if the following conditions hold:  

(i) At current time $t$  

$$
V^{A}(t)\leq0.
$$  

(ii) At some future time $T>t$  

$V^{A}(T)\geq0$ with probability one and $V^{A}(T)>0$ with positive probability.  

In symbols, the second condition is: At some future time $T>t$ $P(V^{A}(T)\geq0)=1$ and $P(V^{A}(T)>0)>0$ $\triangle$  

An arbitrage portfolio represents "free lunch' or "getting something for nothing." (It is more accurate (but less snappy) to say an arbitrage portfolio represents "free lunch without risk" or "getting something for nothing without risk.")  

We have two basic goals in these notes. We will learn how to:  

1. Price assets so that no arbitrage opportunities appear for competitors.  

2. Recognize and exploit arbitrage opportunities.  

For the first goal, we will use the  

No-Arbitrage Principle. There are no arbitrage portfolios.  

The idea is that if, under the assumption of the no-arbitrage principle, we can deduce what the price of an asset must be, then we are guaranteed that no arbitrage portfolios can be constructed with the asset at that price.  

Unless otherwise indicated, we will always assume the no-arbitrage principle.  

You may have heard the phrase "'there is no such thing as a free lunch.' This phrase is an informal expression of the no-arbitrage principle. (Again, it is more accurate to say "'there is no such thing as a free lunch without risk"'.)  

For the second goal, there is a general rule: If the price of an asset does not match the no-arbitrage price (i.e., the price implied by the no-arbitrage assumption), then we can construct an arbitrage portfolio. We will get lots of practice constructing arbitrage portfolios in specific examples and in proofs. In fact, the construction of an arbitrage portfolio is contained in a proof in the next section.  

Remark 2.3.1. It may help to consider a finite sample $\Omega=\{\omega_{1},\ldots,\omega_{n}\}$ and a probability measure $P$ with $P(\{\omega_{i}\})>0$ for all $i$ . Then $A$ is an arbitrage portfolio if  

At current time $t$ $,V^{A}(t)\leq0$  

At some future time $T>t,V^{A}(T)(\omega_{i})\geq0$ for all $i$ and $V^{A}(T)(\omega_{j})>0$ for some $j$  

# 2.4 Monotonicity and Replication  

The replication principle and monotonicity principle are important consequences of the. no-arbitrage principle. We will use them frequently to find the price of assets under the assumption of no-arbitrage.  

Monotonicity Principle Let $A$ and $B$ be portfolios and let. $T>t$ , where $t$ is the current time. If $V^{A}(T)\geq V^{B}(T)$ with probability one, then. $V^{A}(t)\geq V^{B}(t)$  

We will prove the the no-arbitrage principle implies the monotonicity principle. Remember that the no-arbitrage principle is always assumed, unless indicated otherwise.  

Proof. Assume $V^{A}(T)\geq V^{B}(T)$ with probability one.  

We want to conclude $V^{A}(t)~\geq~V^{B}(t)$ .We will use an argument called proof by contradiction where we assume the desired conclusion is false and show that this leads to a contradiction.  

Assume $V^{A}(t)<V^{B}(t)$ . Define $\epsilon=V^{B}(t)-V^{A}(t)$ . Consider the portfolio $C$ consisting of $A$ minus $B$ plus $\epsilon$ of cash. (For example, if. $A$ consists of 5 shares of AAPL and $B$ consists of 3 shares of GOOGL, then $C$ consists of 5 shares of AAPL, $-3$ shares of GOOGL, and. $\epsilon$ of cash.) Then.  

$$
\bullet V^{C}(t)=V^{A}(t)-V^{B}(t)+\epsilon=0,
$$  

$\bullet V^{C}(T)=V^{A}(T)-V^{B}(T)+\epsilon\geq\epsilon>0$ with probability one.  

Therefore $C$ is an arbitrage portfolio. This contradicts the no-arbitrage principle.  

Remark 2.4.1. Note that we may view the portfolio $C$ in the previous proof as starting empty. At time $t$ , we borrow the portfolio $B$ , sell it for $V^{B}({\cal T})$ cash, use $V^{A}(T)$ of the cash to buy portfolio $A$ , leaving $\epsilon=V^{B}(t)-V^{A}(t)$ cash left over. Thus at time $t$ we have portfolio $A,\epsilon$ cash, and a debt of portfolio $B$ . At time $T$ , the debt of portfolio $B$ is worth $V^{B}({\cal T})$ $\triangle$  

Replication Principle. Let $A$ and $B$ be portfolios and let $T>t$ where $t$ is the current time. If $V^{A}(T)=V^{B}(T)$ with probability one, then $V^{A}(t)=V^{B}(t)$ $\triangle$  

We will show that the monotonicity principle, hence also the no-arbitrage principle, implies the replication principle.  

Proof. $V^{A}(T)=V^{B}(T)$ means $V^{A}(T)\geq V^{B}(T)$ and $V^{A}(T)\leq V^{B}(T)$ . The monotonicity theorem implies $V^{A}(t)\geq V^{B}(t)$ and $V^{A}(t)\leq V^{B}(t)$ , which means $V^{A}(t)~=$ $V^{B}(t)$  

Definition 2.4.1. Let $A$ and $B$ be portfolios and let $T>t$ , where $t$ is the current time. If $V^{A}(T)=V^{B}(T)$ with probability one, we say that $A$ replicates $B$ (and $B$ replicates $A$ :  

Exercise 2.4.1. This exercise is to practice "proof by contradiction.' Prove:  

(a) Let $a\geq0$ . If $a\leq\epsilon$ for every $\epsilon>0$ , then $a=0$ (b) $\sqrt{2}$ is irrational.  

Exercise 2.4.2. We showed above that the no-arbitrage principle implies the monotonicity principle. Consider the  

Strong Monotonicity Principle. Let $A$ and $B$ be portfolios and let. $T>t$ , where $t$ is the current time. If $V^{A}(T)\geq V^{B}(T)$ with probability one, and $V^{A}(T)>V^{B}(T)$ with positive probability, then $V^{A}(t)>V^{B}(t)$ $\triangle$ (a) Show that the no-arbitrage principle implies the strong monotonicity principle. (b) Show that the strong monotonicity principle implies the monotonicity principle. (c) Show that the strong monotonicity principle implies the no-arbitrage principle. Hint: If $A$ is an arbitrage portfolio, apply the monotonicity principle to $A$ and an empty portfolio $B$ to deduce a contradiction.  

# Chapter 3  

# Compound Interest, Discounting, and Basic Assets  

# 3.1 Interest Rates and Compounding  

Definition 3.1.1. If we invest (lend, deposit) $N$ dollars at interest rate $r$ compounded annually, then:.  

After one year the value of the investment is $N(1+r)$   
After two years: $N(1+r)^{2}$   
After $T$ years: $N(1+r)^{T}$  

The time $T$ is measured in years and can be any non-negative real number. $N$ is called the notional or principle.  

If we owe a debt of $N$ at interest rate $r$ compounded annually, then after $T$ years we owe $N(1+r)^{T}$ . In other words, after $T$ years we have $-N(1+r)^{T}$ . A debt of $N$ is like investing $-N$ $\triangle$  

Definition 3.1.2. If we invest $N$ at interest rate $r$ compounded $m$ times per year, then:.  

After $1/m$ years the value of the investment is $N(1+r/m)$ After $2/m$ years: $N(1+r/m)^{2}$ After $T$ years (i.e., $m T/m$ years): $N(1+r/m)^{m T}$  

The time $T$ is measured in years and can be any non-negative real number. $m$ is called the compounding frequency.  

Remember from calculus that $\operatorname*{lim}_{m\to\infty}(1+r/m)^{m T}=e^{r T}.$  

Definition 3.1.3. If we invest. $N$ at interest rate $r$ compounded continuously, then:  

After $T$ years we have $N e^{r T}$  

The time $T$ is measured in years and can be any non-negative real number.  

Example 3.1.1. If we invest 500 at rate. $4\%=0.04$ with compounding frequency 4 (quar-) terly compounding), the value after 3 years is  

$$
500(1+0.04/4)^{4\cdot3}=563.4125\cdot...
$$  

Example 3.1.2. If we borrow 500 at two-month compounded interest rate $4\%=0.04$ (this means compounding 6 times per year), the value after 3 years is  

$$
500(1+0.04/6)^{6\cdot3}=563.5239\cdot..
$$  

Example 3.1.3. If we invest 500 at rate $4\%=0.04$ with daily compounding (assuming 365 days per year), the value after 3 years is  

$$
500(1+0.04/365)^{365\cdot3}=563.7447\cdot..
$$  

Example 3.1.4. If we invest 500 at rate $4\%=0.04$ with continuous compounding, the value after 3 years is  

$$
500e^{0.04\cdot3}=563.7484....
$$  

We will always deal with so-called per-year interest rates. This means time is measured. in units of years. The only exception is the next example, where we consider per-month interest rates.  

Example 3.1.5. If we borrow 500 at rate $1.2\%=0.012$ per month with monthly compounding, then after $T$ months we owe  

$$
500(1+0.012)^{T}.
$$  

Notice $T$ is measured in months.  

If we borrow 500 at rate $1.2\%=0.012$ per month with compounding twice a month, then after $T$ months we owe  

$$
500(1+0.012/2)^{2T}.
$$  

If we borrow 500 at rate $1.2\%=0.012$ per month with daily compounding (assuming each month has 30 days), then after. $T$ months we owe  

$$
500(1+0.012/30)^{30T}.
$$  

Result 3.1.6. If the interest rate with compounding frequency $m$ is $r_{m}$ and the interest rate with continuous compounding is $r_{\infty}$ , then  

(a) $\left(1+{\frac{r_{m}}{m}}\right)^{m T}=e^{r_{\infty}T}{\mathrm{~for~all~}}T>0$ (b) $r_{\infty}=m\ln\left(1+{\frac{r_{m}}{m}}\right)$ (c) $r_{m}=m\left(e^{r_{\infty}/m}-1\right)$  

Proof. First, note that if we have any one of (a),(b),(c), then we get the other two by rearranging. So we only prove (a). The idea is proof by contradiction: If (a) does not hold, then we can build an arbitrage portfolio..  

$\left(1+\frac{r_{m}}{m}\right)^{m T}>e^{r_{\infty}T}$ for some $T>0$ , we consider the portfolio  

A: At time 0, invest 1 at rate $r_{m}$ with compounding frequency $m$ and borrow 1 at rate $r$ with continuous compounding.  

Then $V^{A}(0)=0$ and $V^{A}(T)=\Big(1+{\frac{r_{m}}{m}}\Big)^{m T}-e^{r_{\infty}T}>0$ with probability one. So $A$ is an arbitrage portfolio. This contradicts the no-arbitrage principle.   
$\left(1+\frac{r_{m}}{m}\right)^{m T}<e^{r_{\infty}T}$ for some $T>0$ , then a similar arguments also leads to a contradiction.  

Note that we may view the portfolio in the previous proof as starting empty.  

A proof based on the replication principle is also possible:  

Proof. Consider portfolios  

A: At time 0, invest amount $M={\left(1+{\frac{r_{m}}{m}}\right)}^{-m T}$ at rate $r_{m}$ with compounding frequency $m$ B: At time 0, invest amount $N=e^{-r_{\infty}T}$ at rate $r_{\infty}$ with continuous compounding.  

Note $V^{A}(T)=M\left(1+\frac{r_{m}}{m}\right)^{m T}=\left(1+\frac{r_{m}}{m}\right)^{-m T}\left(1+\frac{r_{m}}{m}\right)^{m T}=1$ Likewise $V^{B}(T)=$ $N e^{r_{\infty}T}=e^{-r_{\infty}T}e^{r_{\infty}T}=1$ Thus $V^{A}(T)\:=\:V^{B}(T)\:=\:1$ with probability 1. By the replication principle, $V^{A}(0)=V^{B}(0)$ . But $V^{A}(0)=\left(1+{\frac{r_{m}}{m}}\right)^{-m T}$ and $V^{B}(0)=e^{-r_{\infty}T}$ Thus $\left(1+\frac{r_{m}}{m}\right)^{m T}=e^{r_{\infty}T}.$  

Definition 3.1.4. If we invest $N$ at simple interest rate $r$ , then:  

After $T$ years we have $N(1+T r)$  

'he time $T$ is measured in years and can be any non-negative real number.  

Example 3.1.7. If we borrow 500 at simple interest rate $4\%=0.04$ , the value after 3 years is  

$$
500(1+(3)(0.04))=560.
$$  

Result 3.1.8. If the simple interest rate is $r_{0}$ and the interest rate with continuous compounding is $r_{\infty}$ , then  

$$
\left(1+T r_{0}\right)=e^{r_{\infty}T}\mathrm{forall}T>0.
$$  

The proof is an exercise.  

Remark. We will always assume we can lend and borrow at non-negative interest rates. It is possible to consider negative interest rates, but we will not do so for simplicity. As we move through the course, the reader should think about how results would change if interest rates were negative.  

Remark. We have implicitly assumed above that interest rates are constant in time. This is typically not the case. They depend on the period over which we lend/borrow. We will consider this generalization later.  

Exercise 3.1.1. Show that if the interest rate with compounding frequency $m_{1}$ is $r_{1}$ and the interest rate with compounding frequency $m_{2}$ is $r_{2}$ , then  

$$
\begin{array}{l}{{\displaystyle\left(1+\frac{r_{1}}{m_{1}}\right)^{m_{1}T}=\left(1+\frac{r_{2}}{m_{2}}\right)^{m_{2}T}\mathrm{for}\mathrm{all}T>0}}\ {{\displaystyle r_{1}=m_{1}\left[\left(1+\frac{r_{2}}{m_{2}}\right)^{m_{2}/m_{1}}-1\right]}}\end{array}
$$  

Exercise 3.1.2. Show that if the simple interest rate is $r_{0}$ and the interest rate with continuous compounding is $r_{\infty}$ , then  

$$
\left(1+T r_{0}\right)=e^{r_{\infty}T}\mathrm{forall}T>0.
$$  

Exercise 3.1.3. If the six-month compounded interest rate is $4.3\%=0.043$ , find the annually compounded rate $r_{A}$ and the continuously compounded rate $r_{\infty}$ . Hint: The six-month compounded interest rate is the interest rate with compounding twice per year.  

Exercise 3.1.4. (a) Show that if the interest rate with compounding frequency $m$ is $r_{m}$ and the simple interest rate is $r_{0}$ , then $\left(1+{\frac{r}{m}}\right)^{m T}=\left(1+T r_{0}\right)$ for all $T>0$ (b) If the simple interest rate is $2.1\%$ from 0 to 3 is, find the annually compounded rate. $r_{A}$ and the continuously compounded rate $r_{\infty}$  

Exercise 3.1.5. Suppose the definition of annual compounding was slightly different in that interest is only accrued annually. That is, if you invest. $N$ at annual rate $r$ , then  

After 1 years the value of the investment is $N(1+r)$   
After 1.1 years: $N(1+r)$   
After 1.9 years: $N(1+r)$   
After 2 years: $N(1+r)^{2}$   
After $T$ years: $N(1+r)^{\lfloor T\rfloor}$  

Here $\lfloor T\rfloor$ is the largest integer less than or equal to $T$ Construct an arbitrage portfolio.  

# 3.2 Time Value of Money, Zero Coupon Bonds, and Discounting  

Would you rather have a dollar today or a dollar tomorrow? The dollar today, because you. can invest it to receive interest, so you'll have more than a dollar tomorrow. This idea is called the time value of money. We will see more quantitative versions below..  

Definition 3.2.1. A zero coupon bond (ZCB) with maturity $T$ is an asset that pays 1 at. time $T$ (and nothing else). Its value at time $t\leq T$ is denoted $Z(t,T)$ .By definition,. $Z(T,T)=1$ $\triangle$  

What is the value of a ZCB at time. $t\leq T?$ In other words, what is the value today of the promise of a dollar tomorrow?.  

Result 3.2.1. If the continuously compounded interest rate from time $t$ to time $T$ has constant value $r$ , then  

$$
Z(t,T)=e^{-r(T-t)}.
$$  

Proof. Consider two portfolios.  

A: At time $t$ , a ZCB with maturity $T$   
B: At time $t$ , investment of $N=e^{-r(T-t)}$ with continuously compounded interest rate $r$ Then $V^{A}(T)=1$ and $V^{B}(T)=N e^{r(T-t)}=e^{-r(T-t)}e^{r(T-t)}=1.$   
Therefore $V^{A}(T)=V^{B}(T)$ with probability one.   
By the replication principle,. $V^{A}(t)=V^{B}(t)$   
In other words, $Z(t,T)=e^{-r(T-t)}$ Remark 3.2.2. This is the first of many proofs where we use the replication principle.   
Make sure you understand it..  

Remark 3.2.3. In principle, anybody can write and sell a ZCB. Just write on a piece of paper $^{\circ\circ}\mathrm{I}$ promise to pay the holder of this paper of paper 1 dollar at time. $T$ "Then sell that piece of paper. That peice of paper is a ZCB. Of course, the buyer must trust that the promise of the ZCB will be honored.. $\triangle$  

$Z(t,T)$ is also called a discount factor. It depends on the interest rate and compounding frequency over the period from $t$ to $T$  

Determining the value of an asset at time $t$ based on its value at some future time $T>t$ is called discounting or present valuing. The value at time $t$ is called the discounted value or present value.  

Example 3.2.4. Consider an asset that pays 500 and matures 3 years from now. If the continuously compounded interest rate is $2.1\%$ , what is its present value?  

If the present time is $t$ , the asset is is equivalent to 500 ZCBs with maturity $T=3+t$ , and the present value is  

$$
500Z(t,T)=500e^{-r(T-t)}=500e^{-0.021(3)}.
$$  

Result 3.2.5. If the interest rate with compounding frequency $m$ from time $t$ to time $T$ has constant value $r$ , then  

$$
Z(t,T)=(1+r/m)^{-m(T-t)}.
$$  

The proof is an exercise.  

Result 3.2.6. If the simple interest rate from time $t$ to time $T$ has constant value $r$ , then  

$$
Z(t,T)=(1+r T)^{-1}.
$$  

The proof is an exercise.  

Definition 3.2.2. Because of the Results 3.2.1, 3.2.5, and 3.2.6, we call an interest rate which is constant for a period $t$ to $T$ a zero rate. For example, if the continuous interest rate for the period $t$ to $T$ is has constant value $r=3\%=0.03$ , we would say the continuous zero rate for $t$ to $T$ is $r=3\%=0.03$  

Exercise 3.2.1. Consider an asset that pays $N$ at maturity 3 years from now. Suppose the annually compounded interest rate is $3\%$ and the present value is 300. Find $N$  

Exercise 3.2.2. Show that if the interest rate with compounding frequency $m$ from time $t$ to time $T$ has constant value $r$ , then  

$$
Z(t,T)=(1+r/m)^{-m(T-t)}.
$$  

(a) Do this by combining Result 3.1.6 and Result 3.2.1.   
(b) Do this by a no-arbitrage argument as in the proof of Result 3.2.1.  

Exercise 3.2.3. Show that if the simple interest rate from time $t$ to time $T$ has constant value $r$ , then  

$$
Z(t,T)=(1+r T)^{-1}.
$$  

(a) Do this by combining Result 3.1.8 and Result 3.2.1.   
(b) Do this by a no-arbitrage argument as in the proof of Result 3.2.1.  

# 3.3 Annuities  

Definition 3.3.1. An annuity is a series of fixed payments $C$ at times $T_{1},\dots,T_{n}$ .It is equivalent to the following collection of ZCBs:.  

$C$ ZCBs with maturity $T_{1}$ $C$ ZCBs with maturity $T_{2}$ $C$ ZCBs with maturity $T_{n}$  

Its value at time $t\leq T_{1}$ is  

$$
V_{t}=C\sum_{i=1}^{n}Z(t,T_{i}).
$$  

Its value at time $T_{1}<t\leq T_{2}$ is  

$$
V_{t}=C\sum_{i=2}^{n}Z(t,T_{i}).
$$  

because the 1st payment has already been made.  

Result 3.3.1. Consider an annuity starting at time $t$ that pays $C$ each year for $M$ years. Assume the annually compounded zero rate is $r_{A}$ for all maturities $T=t+1,\dots,t+M$ The value at its starting time $t$ is  

$$
V_{t}=C\cdot\frac{1-(1+r_{A})^{-M}}{r_{A}}.
$$  

Proof. For simplicity, we assume. $C=1$ and $t=0$ As an exercise, adjust the proof for. general $C$ and $t$ . Consider an annuity starting at time O that pays 1 each year for $M$ years. Assume the annually compounded zero rate is. $r_{A}$ for all maturities $T=1,\dots,M$ . This means that  

$$
Z(0,T)=(1+r_{A})^{-T}\quad\mathrm{for}T\in\{1,\ldots,M\}
$$  

The value of the annuity at time $t=0$ is  

$$
V_{0}=\sum_{T=1}^{M}Z(0,T)=\sum_{T=1}^{M}\frac{1}{(1+r_{A})^{T}}.
$$  

We simplify this geometric sum by a standard trick. Observe that  

$$
{\frac{1}{1+r_{A}}}V_{0}-V_{0}=\sum_{T=2}^{M+1}{\frac{1}{(1+r_{A})^{T}}}-\sum_{T=1}^{M}{\frac{1}{(1+r_{A})^{T}}}={\frac{1}{(1+r_{A})^{M+1}}}-{\frac{1}{1+r_{A}}}
$$  

and solve for $V$ to obtain  

$$
V_{0}=\frac{1-(1+r_{A})^{-M}}{r_{A}}.
$$  

Example 3.3.2. In the US, a $\$100$ million Powerball lottery jackpot is typically structured as an annuity paying. $\$4$ million per year for 25 years. With an annually compounded interest rate of $3\%$ , the value of the jackpot at time $t=0$ is  

$$
4\cdot10^{6}\sum_{T=1}^{25}Z(0,T)=4\cdot10^{6}\sum_{T=1}^{25}{\frac{1}{(1+0.03)^{T}}}=4\cdot10^{6}{\frac{1-(1+0.03)^{-25}}{0.03}}\approx69.65~\mathrm{m}
$$  

Example 3.3.3. A loan of 1000 is to be paid back in 5 equal installments due yearly. Interest of $15\%$ of the balance is applied each year, before the installment is paid. This type of loan is called an amoritized loan.  

Find the amount $C$ of each installment.  

For the lender, the loan is equivalent to an annuity. Assume it starts at $t=0$ . So it pays $C$ at times $T=1,2,3,4,5$  

The $15\%$ yearly interest on the balance is equivalent to a $15\%$ annually compounded interest rate.  

By Result 3.3.1, the value at time 0 is  

$$
V_{0}=C\frac{1-(1+(0.15))^{-5}}{0.15}
$$  

On the other hand, we know $V_{0}=1000$ Therefore  

$$
C=1000\cdot{\frac{0.15}{1-(1+(0.15))^{-5}}}\approx298.32.
$$  

Example 3.3.4. Consider an amortized loan with initial value $V$ due in $M$ years with equal annual installments $C$ and annually compounded interest rate $r$ . As in Example 3.3.3, each installment is  

$$
C=V\frac{r}{1-(1+r)^{-M}}.
$$  

The balance after the 1st installment is  

$$
B_{1}=V(1+r)-C.
$$  

The balance after the 2nd installment is  

$$
B_{2}=(V(1+r)-C)(1+r)-C=V(1+r)^{2}-C(1+r)-C.
$$  

The balance after the $k$ -th installment is  

$$
B_{k}=V(1+r)^{k}-C\sum_{i=0}^{k-1}(1+r)^{i}.
$$  

We can rewrite this expression by substituting  

$$
C=V{\frac{r}{1-(1+r)^{-M}}}\quad{\mathrm{~and~}}\quad\sum_{i=0}^{k-1}(1+r)^{i}={\frac{1-(1+r)^{k}}{1-(1+r)}}
$$  

and doing some algebra. We find the balance after the $\mathbf{k}$ -th installment is  

$$
B_{k}=V\frac{(1+r)^{M}-(1+r)^{k}}{(1+r)^{M}-1}.
$$  

$B_{0}=V$ is the initial balance.  

The interest at the 1st installment is  

$$
B_{0}r=V r.
$$  

The interest at the 2nd installment is  

$$
B_{1}r=(V(1+r)-C)r
$$  

The interest at the $k$ -th installment is  

$$
B_{k-1}r.
$$  

The amount of the initial loan repaid in the. $k$ -th installment (that is, the amount of the. $k$ th installment that does not go towards interest) is  

$$
C-B_{k-1}r
$$  

The geometric sum trick we used the proof of Result 3.3.1 can be used to prove the following result. You may prefer to remember this result, rather than the trick.  

Result 3.3.5. $1.\sum_{k=0}^{N}R^{k}=1+R+R^{2}+...+R^{k}={\frac{1-R^{N+1}}{1-R}}$  

$2.\sum_{k=1}^{N}R^{k}=R(1+R+R^{2}+...+R^{k-1})={\frac{R(1-R^{N})}{1-R}}$ $3.\sum_{k=1}^{N}\frac{1}{(1+R)^{k}}=\frac{1-(1+R)^{-N}}{R}$  

Exercise 3.3.1. Prove Result 3.3.1 for general $C$  

Exercise 3.3.2. Consider the loan in Example 3.3.3.  

(a) What is the amount of interest included in each installment? (b) How much of the initial loan is repaid in each installment? (c) What is the outstanding balance after each installment is paid'  

Exercise 3.3.3. Consider an annuity starting at time 0 that pays 1 each year for $M$ years. Assume the annually compounded zero rate is $r_{A}$ for all maturities $T=1,\dots,M$ . By Result 3.3.1, the value of this annuity at its starting time 0 is.  

$$
V_{0}=\sum_{i=1}^{M}Z(0,i)=\frac{1-(1+r_{A})^{-M}}{r_{A}}.
$$  

Find the value of the annuity at time $t^{\prime}$ , where $0<t^{\prime}<1$  

Exercise 3.3.4. Consider an annuity starting at time $t$ that pays 1 each year for $M$ years. Assume the annually compounded zero rate is $r_{A}$ for all maturities $T=t+1,\dots,t+M$ According to Result 3.3.1, the value of this annuity at its starting time $t$ is  

$$
V_{t}=\sum_{i=1}^{M}Z(t,t+i)=\frac{1-(1+r_{A})^{-M}}{r_{A}}.
$$  

Find the value of the annuity at time $t^{\prime}$ , where $t<t^{\prime}<t+1$  

Exercise 3.3.5. Consider an annuity that pays 1 every quarter for $M$ years. In other words, the payment imes are $T=t+{\textstyle{\frac{1}{4}}},t+{\textstyle{\frac{2}{4}}},\ldots,t+{\textstyle{\frac{4M}{4}}}$ Show that the value at present time $t$ is  

$$
V_{t}=\frac{1-(1+r_{4}/4)^{-4M}}{r_{4}/4},
$$  

assuming the quarterly compounded interest rate has constant value $r_{4}$  

Exercise 3.3.6. Consider an annuity that pays 1 every quarter for $M$ years. In other words, the payment times are $T=t+{\textstyle{\frac{1}{4}}},t+{\textstyle{\frac{2}{4}}},\ldots,t+{\textstyle{\frac{4M}{4}}}$ . Show that the value at present time $t$ is  

$$
V_{t}={\frac{1-(1+r_{8}/8)^{-8M}}{(1+r_{8}/8)^{2}-1}},
$$  

assuming the interest rate with compounding 8 times per year has constant value $r_{8}$  

# 3.4 Bonds  

Definition 3.4.1. A fixed rate bond with notional $N$ , coupon $c$ , start date $T_{0}$ , maturity $T_{n}$ and term length $\alpha$ is an asset that pays $N$ at time $T_{n}$ and coupon payments $\alpha N c$ at times $T_{i}$ for $i=1,\ldots,n$ , where $T_{i+1}=T_{i}+\alpha$ $\triangle$  

Result 3.4.1. Consider a fixed rate bond with coupon $c$ , notional $N$ , maturity $M$ years from now, and annual coupon payments. Assume the annually compounded interest rate has constant value $r_{A}$ . The value of the bond at present time $t$ is  

$$
V_{t}=c N\frac{1-(1+r_{A})^{-M}}{r_{A}}+N(1+r_{A})^{-M}.
$$  

Proof. The bond is equivalent to an annuity paying $c N$ each year for $M$ years plus $N$ ZCBs with maturity $M$ . Use Result 3.3.1 and Result 3.2.5.  

Exercise 3.4.1. (a) Consider an annuity that pays 1 every quarter for $M$ years. In other words, the payment times are $T=t+\textstyle{\frac{1}{4}},t+\textstyle{\frac{2}{4}},\ldots,t+\textstyle{\frac{4M}{4}}$ . Show that the value at present time $t$ is  

$$
V_{t}=\frac{1-(1+r_{4}/4)^{-4M}}{r_{4}/4},
$$  

assuming the quarterly compounded interest rate has constant value $r_{4}$  

(b) Consider a fixed rate bond with notional $N$ and coupon $c$ that starts now, matures $M$ years from now, and has quarterly coupon payments. Show that the value at present time $t$ is  

$$
V_{t}=\frac{c N}{4}\cdot\frac{1-(1+r_{4}/4)^{-4M}}{r_{4}/4}+N(1+r_{4}/4)^{-4M},
$$  

assuming the quarterly compounded interest rate has constant value $r_{4}$  

Exercise 3.4.2. (a) Consider an annuity that pays 1 every quarter for $M$ years. In other words, the payment times are $T=t+\textstyle{\frac{1}{4}},t+\textstyle{\frac{2}{4}},\ldots,t+\textstyle{\frac{4M}{4}}$ . Show that the value at present time $t$ is  

$$
V_{t}={\frac{1-(1+r_{8}/8)^{-8M}}{(1+r_{8}/8)^{2}-1}},
$$  

assuming the interest rate with compounding 8 times per year has constant value $r_{8}$  

(b) Consider a fixed rate bond with notional $N$ and coupon $c$ that starts now, matures $M$ years from now, and has quarterly coupon payments. Show that the value at present time $t$ is  

$$
V_{t}=\frac{c N}{4}\cdot\frac{1-(1+r_{8}/8)^{-8M}}{(1+r_{8}/8)^{2}-1}+N(1+r_{8}/8)^{-8M},
$$  

assuming the interest rate with compounding 8 times per year has constant value $r_{8}$  

# 3.5 Stocks  

Definition 3.5.1. A stock or share is an asset giving ownership of a fraction of a company. The price of a stock at time $T$ is denoted by $S_{T}$ . If $t$ is the current time, then the known price $S_{t}$ is called the spot price, and $S_{T}$ is a random variable for $T>t$ . A stock may sometimes pay a dividend, which is a cash payment usually expressed as a percentage of the stock price.  

# 3.6 Foreign Exchange Rates  

Example 3.6.1. The current euro (EUR) to US dollar (USD) exchange rate is  

Therefore the USD to EUR exchange rate is  

$$
{\frac{1}{0.89\mathrm{EUR/USD}}}\approx1.12\mathrm{USD/EUR}.
$$  

Then  

$$
150\mathrm{USD}=\left(\mathrm{150USD}\right)\left(0.89{\frac{\mathrm{EUR}}{\mathrm{USD}}}\right)=150(0.89)\mathrm{EUR}=133.50\mathrm{EUR}.
$$  

Exercise 3.6.1. The current US Dollar (USD) to Japense Yen (JPY) exchange rate is 0.0098USD/JPY.  

(a) Find the JPY to USD exchange rate. (b) Find the value in USD of 300,000 JPY  

# Chapter 4  

# Forward Contracts  

# 4.1 Derivative Contracts  

Definition 4.1.1. A derivative contract or derivative is a financial contract between two entities whose value is a function of (derives from) the value of another variable. The two entities in the contract are called counterparties. The variable could be the price of a stock, a foreign exchange rate, an interest rate, or even the weather.  

Example 4.1.1 (A Weather Derivative). A contract where one counterparty pays either 100 or O to the other counterparty one year from now depending on whether the total snowfall in Boston over the year is greater than 50 inches.  

We will only consider derivatives of financial variables.  

# 4.2 Forward Contract Definition  

Our first derivative is the forward contract.  

Definition 4.2.1. In a forward contract or forward, two counterparties agree to trade a specific asset (like a stock) at a certain future time $T$ and a certain price $K$  

One counterparty agrees to buy the asset at time $T$ and price $K$ , and the other counterparty agrees to sell the asset at time $T$ and price $K$  

We say the buyer is long the forward contract, and the seller is short the forward contract.  

$K$ is the called the delivery price.. $T$ is called the maturity or delivery date.  

# 4.3 Value of Forward  

Fix an asset. Consider a forward on the asset with delivery price $K$ and maturity $T$  

Definition 4.3.1. $V_{K}(t,T)$ denotes the value (price) of the forward to the long counterparty at time $t\leq T$  

Then $-V_{K}(t,T)$ is the value (price) of the forward to the short counterparty at time $t\leq T$ The value at maturity $\triangle$  

Note that $K$ and $T$ are fixed at the time the forward contract is agreed to, but the value of the forward contract may change over time..  

To take at time $t$ the long position in a forward contract with maturity. $T$ and delivery price $K$ , we must pay $V_{K}(t,T)$ at time $t$ to the counterparty party taking the short position. Note that we must also pay. $K$ at time $T$ to buy the asset.  

You can think of $V_{K}(t,T)$ as the amount the long counterparty must pay upfront (time $t$ to convince the short counterparty to agree to the forward contract. The long counterparty must still pay $K$ at time $T$ to buy the asset.  

Note that if $V_{K}(t,T)$ is negative, it is actually the short counterparty that pays upfront.   
Paying a negative amount means receiving.  

Here is one more way to understand the value of a forward contract. Suppose two counterparties have agreed (at some time in the past) to a forward contract with maturity $T$ and delivery price $K$ . At current time $t\leq T$ , we want to buy we buy the long position from the long counterparty, so that we become the long counterparty. To do so, we need to pay the current long counterparty $V_{K}(t,T)$ at time $t$ . Note that we will still need to pay pay $K$ at time $T$ to buy the asset itself.  

# 4.4 Payoff  

Definition 4.4.1. Fix an asset. Let $S_{t}$ be its price at time $t$ . Consider a forward on the asset with delivery price $K$ and maturity $T$  

At time $T$ , we know the counterparty long the forward must pay $K$ to buy the asset whose value is $S_{T}$ . Therefore the value at maturity (i.e. at time $T$ ) long the forward (i.e., for the long counterparty) is  

$$
V_{K}(T,T)=S_{T}-K.
$$  

We call  

$$
g(S_{T})=S_{T}-K
$$  

the payoff or payout long the forward. Here the function $g(x)=x-K$ is called the long forward payoff function.  

The value at maturity (i.e. at time $T$ ) short the forward (i.e., for the short counterparty) is  

$$
-V_{K}(T,T)=K-S_{T}.
$$  

The payoff payoff or payout short the forward is  

$$
h(S_{T})=K-S_{T}
$$  

where the function. $h(x)=x-K$ is the short forward payoff function.  

Example 4.4.1. Consider a forward with delivery price 100 and maturity $T=2$ years. If the underlying asset has price 95.10 at maturity, find value of the forward to the long party at maturity.  

We have $K=100$ $T=2$ $S_{T}=95.10$ . Therefore $V_{K}(T,T)=S_{T}-K=95.10-100=$ $-4.90$ $\triangle$  

Example 4.4.2. Consider a forward with delivery price 100 and maturity $T$ .Suppose underlying asset has price  

$$
S_{T}=\left\{\begin{array}{c l}{{110}}&{{\mathrm{with~probability~0.6~}}}\ {{90}}&{{\mathrm{with~probability~0.4.}}}\end{array}\right.
$$  

Find the expected payoff long the forward.  

The payoff at maturity long the forward is  

$$
g(S_{T})=S_{T}-100={\left\{\begin{array}{l l}{110-100}&{{\mathrm{with~probability~}}0.6}\ {90-100}&{{\mathrm{with~probability~}}0.4}\end{array}\right.}={\left\{\begin{array}{l l}{10}&{{\mathrm{with~probability~}}0.6}\ {-10}&{{\mathrm{with~probability~}}0.4}\end{array}\right.}
$$  

The expected payoff at maturity long the forward is  

$$
\mathbb{E}(g(S_{T}))=\sum_{k\in R(g(S_{T}))}k P(g(S_{T})=k)=(10)(0.6)+(-10)(0.4)=2
$$  

Exercise 4.4.1. Consider a forward with delivery price 200 and maturity $T$ . Suppose the underlying asset has price  

$$
S_{T}=\left\{\begin{array}{l l}{150}&{\mathrm{with~probability~0.3~}}\ {200}&{\mathrm{with~probability~0.5~}}\ {250}&{\mathrm{with~probability~0.2~}}\end{array}\right..
$$  

(a) Find the payoff long the forward.   
(b) Find the expected value at maturity long the forward.   
(c) Find the expected value of the forward to the short counterparty at maturity.  

# 4.5 Forward Price  

Pre-emptive clarification:  

$$
{\mathrm{forward~price}}\neq{\mathrm{price~of~forward}}={\mathrm{value~of~forward}}=V_{K}(t,T)
$$  

The terminology is unfortunate, but we are stuck with it.  

Definition 4.5.1. Fix an asset. The forward price of the asset at time $t\leq T$ is the number $F(t,T)$ such that the forward contract with maturity $T$ and delivery price $K=F(t,T)$ has value $V_{K}(t,T)=0$ at time $t$ . Thus  

$$
V_{K}(t,T)=0\mathrm{if~and~only~if~}K=F(t,T).
$$  

There is no cost to enter a forward contract (as either the long or short counterparty) at $t$ if the delivery price $K$ equals the forward price $F(t,T)$ $\triangle$  

Remark 4.5.1. Here is another way to describe the forward price that may be help understand it. Consider a forward contract on the asset with maturity. $T$ . Suppose the two counterparties are negotiating the delivery price $K$ before they agree to the contract. Remember that at future time $T$ the long counterparty will pay $K$ to the short counterparty in exchange for the asset. If $K$ is too small, the long counterparty must pay. $V_{K}(t,T)$ at current time $t$ to convince the short counterparty to agree to the contract. If. $K$ is too large, the short counterparty must pay $-V_{K}(t,T)$ $(V_{K}(t,T)<0$ in this situation) at current time $t$ to convince the long counterparty to agree to the contract. The delivery price $K$ where each counterparty pays zero $(V_{K}(t,T)=0)$ at $t$ to convince the other is called the forward price and is denoted $F(t,T)$ . A better name for the forward price may be the \*fair delivery price"' or the "neutral delivery price. $\triangle$  

Remark 4.5.2. Let $S_{T}$ be the price of the asset at time $T$ . Since $V_{K}(T,T)=S_{T}-K$ and since $F(T,T)$ is the value of $K$ that makes $V_{K}(T,T)=0$ , we have  

$$
F(T,T)=S_{T}.
$$  

# 4.6 Value of Forward and Forward Price for Asset Paying No Income  

Result 4.6.1. Suppose the continuous zero rate for period $t$ to $T$ is $r$ .Suppose an asset pays no income (no dividends, no coupons, no payment at maturity, no rent, etc). Then  

$$
V_{K}(t,T)=S_{t}-K Z(t,T)=S_{t}-K e^{-r(T-t)}
$$  

and  

$$
F(t,T)=\frac{S_{t}}{Z(t,T)}
$$  

where $S_{t}$ is the price of asset at time $t$  

Proof. Consider two portfolios.  

A: At time $t$ , one unit of the asset.   
B: At time $t$ , one long forward contract with maturity $T$ and delivery price $K$ plus $K$ ZCBs.   
Then $V^{A}(T)=S_{T}$ and $V^{B}(T)=(S_{T}-K)+K=S_{T}.$   
So $V^{A}(T)=V^{B}(T)$   
By replication, $V^{A}(t)=V^{B}(t)$   
This means  

$$
S_{t}=V_{K}(t,T)+K Z(t,T).
$$  

Solving $V_{K}(t,T)$ gives  

$$
V_{K}(t,T)=S_{t}-K Z(t,T).
$$  

The forward price $F(t,T)$ is the value of $K$ such that $V_{K}(t,T)=0$ Setting $K=F(t,T)$ and $V_{K}(t,T)=0$ in (4.6.1) leads to  

$$
F(t,T)=\frac{S_{t}}{Z(t,T)}.
$$  

By the definition of continuous zero rate, $Z(t,T)=e^{-r(T-t)}$  

Example 4.6.2. The current price of a certain stock paying no income is 20. Assume the continuous zero rate will be $2.1\%$ for the next 6 months. Find the forward price with maturity in 6 months.  

$T-t=6$ months $=0.5$ years.  

$$
F(t,T)={\frac{S_{t}}{Z(t,T)}}={\frac{20}{e^{-(0.021)(0.5)}}}
$$  

Example 4.6.3. The current price of a certain stock paying no income is 20. Assume the continuous zero rate will be $2.1\%$ for the next 6 months. Find the value of a forward contract on the stock if the delivery price is 25 and maturity is in 6 months.  

$T-t=6$ months $=0.5$ years , $S_{t}=20$ $K=25$ $r=0.021$ . Therefore  

$$
V_{K}(t,T)=20-25e^{-(0.021)(0.5)}
$$  

If the price of an asset does not match the no-arbitrage price (i.e., the price implied by the no-arbitrage assumption), then we can construct an arbitrage portfolio.  

Example 4.6.4. At current time $t$ , a certain stock paying no income has price 45, the. forward price with maturity. $T$ on the stock is 48, and the price of a zero coupon bond with maturity $T$ is 0.95. Determine whether there is an arbitrage opportunity. If so, construct an arbitrage portfolio.  

Given $S_{t}=45,F(t,T)=48,Z(t,T)=0.95\$ Notice  

$$
{\frac{S_{t}}{Z(t,T)}}={\frac{45}{0.95}}\approx47.37.
$$  

So $F(t,T)>\frac{S_{t}}{Z(t,T)}$ This violates the result above deduced from the no-arbitrage assumption. So there must be arbitrage portfolio..  

At current time $t$ , portfolio $A$ is  

$-S_{t}$ cash (i.e., $S_{t}$ cash debt)   
1 stock   
1 short forward contract with maturity $T$ and delivery price equal to the forward price $F(t,T)$  

$$
{\cal V}^{A}(t)=-{\cal S}_{t}+{\cal S}_{t}+{\cal V}_{F(t,T)}(t,T)=0.
$$  

At time $T$ , we must sell 1 stock at price $F(t,T)$ , and our debt has grown to $S_{t}e^{r(T-t)}=$ $S_{t}/Z(t,T)$ , where $r$ is the continuous zero rate for period $t$ to $T$  

At time $T$ , portfolio $A$ is:  

$-S_{t}e^{r(T-t)}$ r(T-t) cash$F(t,T)$ cash  

The value of $A$ is  

$$
V^{A}(T)=F(t,T)-S_{t}e^{r(T-t)}=F(t,T)-{\frac{S_{t}}{Z(t,T)}}>0.
$$  

with probability one.  

Therefore $A$ is an arbitrage portfolio.  

Exercise 4.6.1. At current time $t$ a certain stock has price 45, the forward price with. maturity $T$ on the stock is 40, and the price of a zero coupon bond with maturity $T$ is 0.95. Construct an arbitrage portfolio if possible. Verify the portfolio you construct is an arbitrage portfolio.  

Exercise 4.6.2. The current price of a certain stock paying no income is 30. Assume the annually compounded zero rate will be. $3\%$ for the next 2 years.   
(a) Find the current value of a forward contract on the stock if the delivery price is 25 and maturity is in 2 years.   
(b) If the stock has price 35 at maturity, find the value of the forward to the short counterparty at maturity.  

Exercise 4.6.3. Let $S_{t}$ be the current price of a stock that pays no income. Let. $r_{\mathrm{BID}}$ be the interest rate at which one can lend/invest money, and $r_{\mathrm{OFF}}$ be the interest rate at which. one can borrow money. Both rates are continuously compounded. Assume $r_{B I D}\leq r_{O F F}$ except in (a).  

(a) Assume $r_{B I D}>r_{O F F}$ . Find an arbitrage portfolio. Verify it is an arbitrage portfolio. (b) Use a no-arbitrage argument to prove the forward price with maturity $T$ for the stock satisfies the upper bound  

$$
F(t,T)\leq S_{t}e^{r_{O F F}(T-t)}.
$$  

(c) Use a no-arbitrage argument to prove a similar lower bound for the forward price.  

(d) Assume the stock has bid price $S_{t,B I D}$ and offer (or ask) price $S_{t,O F F}$ . The bid price is the price for which you can sell the stock. The offer price is the price for which you. can buy the stock. How do the upper and lower bounds in (a) and (b) change? Prove these bounds using no-arbitrage.  

# 4.7 Value of Forward and Forward Price for Asset Paying Known Income  

Result 4.7.1. Suppose the continuous zero rate for period $t$ to $T$ is $r$ . Suppose an asset an pays a known income stream (for example, dividends, coupons, payment at maturity, rent) during the life of the forward contract. Then.  

$$
V_{K}(t,T)=S_{t}-I_{t}-K Z(t,T)=S_{t}-I_{t}-K e^{-r(T-t)}
$$  

and  

$$
F(t,T)={\frac{S_{t}-I_{t}}{Z(t,T)}}=(S_{t}-I_{t})e^{r(T-t)},
$$  

where $S_{t}$ is the price of asset at time $t$ , and $I_{t}$ is the present value of the income stream at time $t$  

Notice the forward price for an asset paying known income is lower than it would be if the asset paid no income. Until maturity of the forward, the short counterparty holds the asset and collects any income it pays, while the long counterparty gets no income. Thus, for an. asset paying income, there is an advantage to buying it spot (i.e., buying it immediately at. time $t$ ) rather than buying it forward. So the forward price is lower to compensate..  

Proof. A: At time $t$ , one unit of the asset and $-I_{t}$ cash B: At time $t$ , one long forward contract with maturity $T$ and delivery price $K$ plus $K$ ZCBs.  

We have  

$$
V^{A}(T)=S_{T}+I_{t}e^{r(T-t)}-I_{t}e^{r(T-t)}=S_{T},
$$  

$V^{B}(T)=S_{T}-K+K=S_{T}$ So $V^{A}(T)=V^{B}(T)$ with probability 1 By replication, $V^{A}(t)=V^{B}(t)$ Therefore  

$$
S_{t}-I_{t}=V_{K}(t,T)+K Z(t,T).
$$  

Solving for $V_{K}(t,T)$ gives  

$$
V_{K}(t,T)=S_{t}-I_{t}-K Z(t,T)
$$  

The forward price $F(t,T)$ is the value of $K$ such that $V_{K}(t,T)=0$ Setting $K=F(t,T)$ and $V_{K}(t,T)=0$ in (4.7.1) leads to  

$$
F(t,T)=\frac{S_{t}-I_{t}}{Z(t,T)}.
$$  

By the definition of continuous zero rate, $Z(t,T)=e^{-r(T-t)}$  

Example 4.7.2. Assume the continuously compounded interest rate is a constant $r$ . Consider an asset that pays $d$ at times $T_{1}\leq T_{2}\leq\cdots\leq T_{n}$ . Find the forward price. $F(t,T)$ when $t\leq T_{1}$ and $T_{n}\leq T$  

$I_{t}=$ present value of the income $=$ present value of the stream of payments.  

The payment of. $d$ at $T_{i}$ is equivalent to $d$ ZCBs with maturity $T_{i}$ . Therefore  

Hence  

$$
I_{t}=d\sum_{i=1}^{n}Z(t,T_{i})=d\sum_{i=1}^{n}e^{-r(T_{i}-t)}
$$  

$$
F(t,T)={\frac{S_{t}-I_{t}}{Z(t,T)}}={\frac{S_{t}-d\sum_{i=1}^{n}e^{-r(T_{i}-t)}}{e^{-r(T-t)}}}.
$$  

Exercise 4.7.1. The income may be negative if the asset has carrying costs, such as insurance or storage costs. Suppose you have a single gold bar (400 troy ounces) in a storage unit. in Mountain View, California. Rent for the storage unit is 100 per month (with payments starting immediately, not at the end of the month). The current price of gold is 1325 per. troy ounce. Find the current forward price for the gold bar if maturity is 1 year from now, assuming the continuously compounded interest rate has constant value $3\%$ .Hint: From the point of view of the rental company, the rent is a sequence of ZCBs with maturities after 0 months, 1 month, 2 months,. .., 11 months.  

# 4.8 Value of Forward and Forward Price for Stock Paying Known Dividend Yield  

Result 4.8.1. Suppose the continuous zero rate for period $t$ to $T$ is $r$ .Suppose a stock pays dividends as a percentage $q$ of the stock price on a continuously compounded per-year  

basis. $q$ is called the dividend yield. Suppose the dividends are automatically reinvested in the stock. Then  

$$
V_{K}(t,T)=e^{-q(T-t)}S_{t}-K Z(t,T)=e^{-q(T-t)}S_{t}-K e^{-r(T-t)}
$$  

and  

$$
F(t,T)={\frac{S_{t}e^{-q(T-t)}}{Z(t,T)}}=S_{t}e^{(r-q)(T-t)}
$$  

Dividends are often assumed to be paid continuously, rather than at discrete times. This assumption is appropriate for a portfolio of many stocks paying dividends at many different times throughout the year. If you wish, replace the word "stock" in Result 4.8.1 by "portfolio of many stocks."  

Proof. Consider two portfolios at time $t$  

A: $N=e^{-q(T-t)}$ units of stock   
B: 1 forward with delivery price $K$ and maturity $T$ $K$ ZCBs with maturity $T$   
At time $T$ , the number of units of stock in $A$ is $N e^{q(T-t)}=e^{-q(T-t)}e^{q(T-t)}=1,$ Therefore   
$V^{A}(T)=S_{T}$   
$V^{B}(T)=(S_{T}-K)+K=S_{T}$   
Since $V^{A}(T)~=~V^{B}(T)$ with probability one, the replication theorem gives $V^{A}(t)~=$   
$V^{B}(t)$   
We have $V^{A}(t)=e^{-q(T-t)}S_{t}$   
$V^{B}(t)=V_{K}(t,T)+K Z(t,T)$   
Therefore  

$$
e^{-q(T-t)}S_{t}=V_{K}(t,T)+K Z(t,T).
$$  

Solving for $V_{K}(t,T)$ gives  

$$
V_{K}(t,T)=e^{-q(T-t)}S_{t}-K Z(t,T).
$$  

The forward price $F(t,T)$ is the value of $K$ such that $V_{K}(t,T)=0$ . Setting $K=F(t,T)$ gives $V_{K}(t,T)=0$ , and so (4.8.1) leads to  

$$
F(t,T)=\frac{S_{t}e^{-q(T-t)}}{Z(t,T)}.
$$  

By the definition of continuous zero rate, $Z(t,T)=e^{-r(T-t)}$  

Exercise 4.8.1. Suppose a stock pays dividends. $m$ times per year at equally spaced times with annual yield. $q$ . So each dividend payment is equal to. $q/m$ of the stock price and the. payments are made at times. $t+1/m,t+2/m,\ldots$ where $t$ is the current time. Suppose. the dividends are automatically reinvested in the stock.  

(a) If you have 1 unit of stock at time $t$ , how many will you have. $1/m$ years later when the.  

first dividend is paid?  

(b) If $T-t$ is an integer multiple of. $1/m$ , show that the forward price for the stock is  

$$
F(t,T)=\frac{S_{t}(1+q/m)^{-m(T-t)}}{Z(t,T)}.
$$  

(c) Compute the limit as $m\rightarrow\infty$  

(d) Suppose $m=1$ and $T-t=0.5$ (so $T-t$ is not an integer multiple of $m$ ). Show that if (4.8.2) holds, then you can build an arbitrage portfolio. Verify the portfolio is an arbitrage portfolio.  

Exercise 4.8.2. Fix times $t_{0}<t<T$ . Consider an asset that pays no income. Suppose that at time $t_{0}$ you go short a forward contract with maturity $T$ and delivery price equal to the forward price. $F(t_{0},T)$ . At time $t$ suppose both the price of the asset and interest rates are unchanged.  

(a) How much money have you made or lost? This is called the carry of the trade at time $t$ Hint: Compare the value of the short forward at time $t_{0}$ to its value at time $t$  

(b) How does your answer change if the asset pays dividends at constant rate. $q?$ As usual, assume the dividends are paid continuously and automatically reinvested in the stock.  

# 4.9 Forward Price for Currency  

Result 4.9.1. Suppose $X_{t}$ is the price at time $t$ in USD of one unit of foreign currency. (For. example, $1{\mathrm{CAD}}=0.77$ USD.) Let $r_{\mathbb{S}}$ be the zero rate for USD. Let $r_{f}$ be the zero rate for foreign currency, both constant and compounded continuously.  

The value of a forward contract with maturity $T$ and delivery price $K$ on one unit of foreign. currency is  

$$
V_{K}(t,T)=e^{-r_{f}(T-t)}S_{t}-K Z(t,T)=e^{-r_{f}(T-t)}S_{t}-K e^{-r_{\S}(T-t)}.
$$  

The forward price for one unit of foreign currency is  

$$
F(t,T)=X_{t}e^{(r_{\Updownarrow}-r_{f})(T-t)}.
$$  

Exercise 4.9.1. Prove Result 4.9.1. Hint: In the proof of Result 4.8.1, replace the stock by foreign currency. The foreign currency is analogous to a stock paying known dividend yield. The foreign interest rate corresponds to the dividend yield.  

# 4.10 Relationship Between Value of Forward and Forward Price  

Result 4.10.1. Suppose the continuous zero rate for period $t$ to $T$ is $r$ . For any asset,  

$$
V_{K}(t,T)=(F(t,T)-K)Z(t,T)=(F(t,T)-K)e^{-r(T-t)}.
$$  

Proof. Consider two portfolios at time $t$  

A: one long forward with maturity $T$ and delivery price $K$ , one short forward with maturity   
$T$ and delivery price $F(t,T)$   
B: $(F(t,T)-K)$ ZCBs with maturity $T$   
We have   
$V^{A}(T)=\left(S_{T}-K\right)+\left(F(t,T)-S_{T}\right)=F(t,T)-K$   
$V^{B}(T)=F(t,T)-K$   
So $V^{A}(T)=V^{B}(T)$ with probability one. By replication, $V^{A}(t)=V^{B}(t)$ . But $V^{A}(t)=$   
$V_{K}(t,T)+0=V_{K}(t,T)$   
$V^{B}(t)=(F(t,T)-K)Z(t,T)$  

Therefore  

$$
V_{K}(t,T)=(F(t,T)-K)Z(t,T).
$$  

Example 4.10.2. Assume $V_{K}(t,T)<(F(t,T)-K)Z(t,T)$ . Construct an arbitrage portfolio.   
A is $^{\circ\circ}\mathrm{A}$ from the proof"' minus $V_{K}(t,T)$ cash (or $V_{K}(t,T)/Z(t,T)$ ZCBs with maturity $T$ $V^{A}(t)=0$   
$V^{A}(T)=(S_{T}-K)+(F(t,T)-S_{T})-\frac{V_{K}(t,T)}{Z(t,T)}>0$ with probability one.  

Exercise 4.10.1. Assume $V_{K}(t,T)>(F(t,T)-K)Z(t,T)$ . Construct an arbitrage portfolio.  

Exercise 4.10.2. The current time is. $t=0$ . Suppose the present value of a forward contract on a certain asset is 10. The delivery price is $K=100$ and the maturity is. $T=5$ . Suppose the forward price on the asset is 110. Suppose the continuous interest rate is $2\%$ for time 0 to $T$ . Determine whether there is an arbitrage opportunity. If there is, find an arbitrage portfolio. Verify the portfolio you construct is an arbitrage portfolio.  

# Chapter 5  

# Forward Rates and Libor  

# 5.1 Forward Interest Rates  

Definition 5.1.1. If $t<T_{1}<T_{2}$ , an interest rate agreed at $t$ for lending/borrowing from $T_{1}$ to $T_{2}$ is called a forward rate. $\triangle$  

In contrast, an interest rate agreed at $t$ for lending/borrowing from $t$ to $T$ is a zero rate.  

Example 5.1.1. If the continuously compounded forward rate at current time $t=0$ for period $T_{1}=5$ to $T_{2}=10$ is $7\%$ , then we can agree now to invest $1,000,000$ dollars 5 years from now and receive  

$$
(1,000,000)e^{(0.07)(10-5)}=1419067.54...
$$  

10 years from now.  

For $t<T_{1}<T_{2}$ , let  

$r_{1}=\mathrm{zero}$ rate for period $t$ to $T_{1}$ $r_{2}=\mathrm{zero}$ rate for period $t$ to $T_{2}$ $f_{12}=$ forward rate at $t$ for period $T_{1}$ to $T_{2}$  

Figure 5.1 indicates two possible strategies:  

. Lend (borrow) from $t$ to $T_{2}$ at rate $r_{2}$   
. Lend (borrow) from $t$ to $T_{1}$ at rate $r_{1}$ , then at $T_{1}$ lend (borrow) the amount gained (owed) from $T_{1}$ to $T_{2}$ at rate $f_{12}$  

![](d4c780a629c59d7453dc505fdc190e436c154827245bd7dbb9b1c9bde0fe1822.jpg)  
Figure 5.1: Forward and zero rates  

The next result says they are equivalent.  

Result 5.1.2. In the notation above, if the rates are for continuous compounding, then  

$$
e^{r_{2}(T_{2}-t)}=e^{r_{1}(T_{1}-t)}e^{f_{12}(T_{2}-T_{1})}.
$$  

We give two proofs.  

Proof 1. The idea is that if the strategies return different amounts (i.e., if (5.1.1) does not hold), then we can borrow with one and lend with the other to create an arbitrage portfolio..  

Assume (5.1.1) does not hold.  

If $e^{r_{2}(T_{2}-t)}>e^{r_{1}(T_{1}-t)}e^{f_{12}(T_{2}-T_{1})}$ , we consider portfolio $C$  

. At time $t$ : Start with nothing. Borrow 1 from $t$ to $T_{1}$ at rate $r_{1}$ ; Lend 1 from $t$ to $T_{2}$ at rate $r_{2}$ ; We know that at time. $T_{1}$ we will owe a debt of. $e^{r_{1}(T_{1}-t)}$ ; To pay the debt, we arrange at $t$ to borrow $e^{r_{1}\cdot(T_{1}-t)}$ from $T_{1}$ to $T_{2}$ at rate $f_{12}$   
. At time $T_{1}$ : We owe $e^{r_{1}\cdot(T_{1}-t)}$ . As we arranged at $t$ , to pay off the debt we borrow er1(T-t) from T1 to T2 at the rate f12.   
. At time $T_{2}$ : We receive $e^{r_{2}\cdot(T_{2}-t)}$ and must pay $e^{r_{1}\cdot(T_{1}-t)}e^{f_{12}\cdot(T_{2}-T_{1})}$  

Then $V^{C}(t)=0$ and $V^{C}(T)=e^{r_{2}\cdot(T_{2}-t)}-e^{r_{1}\cdot(T_{1}-t)}e^{f_{12}\cdot(T_{2}-T_{1})}>0$ Thus $C$ is an arbitrage portfolio, which contradicts no-arbitrage.  

If $e^{r_{2}(T_{2}-t)}<e^{r_{1}(T_{1}-t)}e^{f_{12}(T_{2}-T_{1})}$ , a similar construction also gives an arbitrage portfolio.  

# Proof 2. Consider  

A: Time $t$ : Lend amount $M=e^{-r_{2}(T_{2})}$ from $t$ until $T_{2}$ at rate $r_{2}$  

B: Time $t$ : Lend $N=e^{-r_{1}(T_{1}-t)}e^{-f_{12}(T_{2}-T_{1})}$ from $t$ until $T_{1}$ at rate $r_{1}$ . Also arrange at $t$ to lend the amount that will be gained from the first loan, namely $N e^{r_{1}(T_{1}-t)}=e^{-f_{12}(T_{2}-T_{1})}$ from $T_{1}$ until $T_{2}$ at rate $f_{12}$  

Then $V^{A}(T_{2})=M e^{r_{2}(T_{2})}=1$ and $V^{B}(T_{2})=N e^{r_{1}(T_{1}-t)}e^{f_{12}(T_{2}-T_{1})}=1$ Thus $V^{A}(T_{2})=$ $V^{B}(T_{2})$ with probability one. By replication,  

$$
V^{A}(t)=V^{B}(t)
$$  

or equivalently  

$$
e^{-r_{2}(T_{2})}=e^{-r_{1}(T_{1}-t)}e^{-f_{12}(T_{2}-T_{1})}.
$$  

Take reciprocals.  

Remark 5.1.3. The portfolio $C$ in the Proof 1 above can be viewed as $C=A^{\prime}-B^{\prime}$ where  

A: Time $t$ : Lend amount 1 from $t$ until $T_{2}$ at rate $r_{2}$   
B: Time $t$ : Lend 1 from $t$ until $T_{1}$ at rate $r_{1}$ . Also arrange at $t$ to lend the amount gained   
from the first loan, namely. $e^{r_{1}(T_{1}-t)}$ , from $T_{1}$ until $T_{2}$ at rate $f_{12}$  

For compounding $m$ times per year and for simple interest, results analogous to Result 5.1.2 can be obtained by analogous arguments.  

For example,  

Result 5.1.4. In the notation above, if the rates are for compounding $m$ times per year, then  

$$
\left(1+\frac{r_{2}}{m}\right)^{m(T_{2}-t)}=\left(1+\frac{r_{1}}{m}\right)^{m(T_{1}-t)}\left(1+\frac{f_{12}}{m}\right)^{m(T_{2}-T_{1})}
$$  

Example 5.1.5. One year from now, your business plan requires a loan of 100, 000 to purchase new equipment. You plan to repay the loan one year after that. You want to arrange the interest rate of the loan today, rather than gamble on the interest rate one year from now.  

Assume all rates are for continuous compounding. The current time is $t=0$ . The interest rate for period 0 to 1 is $8\%$ . The interest rate for period 0 to 2 is $9\%$ . What must the interest rate on the loan be (assuming no-arbitrage)?.  

Have  

$t=0,T_{1}=1,T_{2}=2,$ . $r_{1}=0.08$ (rate agreed at $t=0$ to borrow from $t=0$ to $T_{1}=1$ . $r_{2}=0.09$ (rate agreed at $t=0$ to borrow from $t=0$ to $T_{2}=2$  

Want $f_{12}=$ forward rate agreed at $t=0$ to borrow from $T_{1}=1$ to $T_{2}=2$  

# DRAW DIAGRAM LIKE Figure 5.1.  

$$
e^{r_{2}(T_{2}-t)}=e^{r_{1}(T_{1}-t)}e^{f_{12}(T_{2}-T_{1})}.
$$  

Solve for $f_{12}$ ..  

$$
f_{12}={\frac{r_{2}(T_{2}-t)-r_{1}(T_{1}-t)}{T_{2}-T_{1}}}={\frac{0.09(2-0)-0.08(1-0)}{2-1}}=0.1=10\%
$$  

Definition 5.1.2. The zero rate for the period starting now and ending $M$ years later is called the $M$ -year zero rate. It is the zero rate for period $t$ to $T=t+M$  

The forward rate for the period starting $M$ years from now and and ending. $N$ years later is the $M$ -year forward $N$ -year rate. It is denoted. $f_{M N}$ . It is also called the. $M\mathbf{y}N\mathbf{y}$ rate. It is the forward rate at current time $t$ for period $T_{1}=t+M$ to $T_{2}=T_{1}+N=t+M+N$ $\triangle$  

Remark. Notice that the notation for the one-year forward two-year rate is. $f_{12}$ .This conflicts with the notation $f_{12}$ used earlier for the forward rate for period $T_{1}$ to $T_{2}$ . This is unfortunate, but both notations are used by the textbook. If you are careful, you will be able to keep things straight.  

Example 5.1.6. Assume all rates are annually compounded. The one-year and two-year zero rates are $1\%$ and $2\%$ , respectively.  

(a) What is the one-year forward one-year rate?  

# Given:  

$r_{1}=0.01=\mathrm{zero}$ rate for period starting now and ending 1 year later, $r_{2}=0.02=:$ zero rate for period starting now and ending 2 years later. Want: $f_{11}=\mathrm{1y1y}$ forward rate $=$ one-year forward one-year rate $=$ forward rate for the period starting one year from now and ending one year later.  

We can assume current time $t=0$ . Then $T_{1}=1$ $T_{2}=2$   
Given   
$r_{1}=0.01=\mathrm{z}$ ero rate for period O to 1   
$r_{2}=0.02=\mathrm{z}$ ero rate for period 0 to 2   
Want   
$f_{11}=$ forward rate for period 1 to 2  

# DRAW DIAGRAM LIKE Figure 5.1.  

Then  

$$
(1+r_{1})^{T_{1}-t}(1+f_{11})^{T_{2}-T_{1}}=(1+r_{2})^{T_{2}-t}
$$  

Solving for $f_{11}$ gives  

$$
\begin{array}{l}{{f_{11}=\displaystyle\left(\frac{(1+r_{2})^{T_{2}-t}}{(1+r_{1})^{T_{1}-t}}\right)^{1/(T_{2}-T_{1})}-1=\left(\frac{(1+0.02)^{2-0}}{(1+0.01)^{1-0}}\right)^{1/(2-1)}-1}}\ {{=0.0300990099\ldots=3.00990099\ldots\%}}\end{array}
$$  

(b) If the two-year one-year forward rate is $3\%$ , what is the three-year zero rate?.  

In class, I will draw a picture like Figure 5.1.  

We can assume current time $t=0$   
$f_{21}=0.03=2\mathrm{y}1\mathrm{y}$ forward rate $=$ two-year forward one-year rate $=$ forward rate for the   
period starting two years from now and ending one year later $=$ forward rate at $t=0$ for   
$T_{2}=2$ to $T_{3}=3$   
$r_{2}=0.02=$ zero rate for 0 to 2   
T3 = zero rate for O to 3 = ???  

Then  

$$
(1+r_{2})^{T_{2}-t}(1+f_{21})^{T_{3}-T_{2}}=(1+r_{3})^{T_{3}-t}
$$  

i.e.,  

$$
(1+0.02)^{2-0}(1+0.03)^{3-2}=(1+r_{3})^{3-0}.
$$  

Solving for $r_{3}$ gives  

$$
r_{3}=0.02332249903\ldots.
$$  

# 5.2 Forward Zero Coupon Bond Prices  

Definition 5.2.1. Let $t\leq T_{1}\leq T_{2}$ . Consider a forward contract with delivery price $K$ and maturity $T_{1}$ where the underlying asset is a ZCB with maturity $T_{2}$ . The price of the ZCB at $t$ is $S_{t}=Z(t,T_{2})$  

The value/price of the forward is denoted $V_{K}(t,T_{1},T_{2})$  

The forward price of the ZCB (or forward ZCB price) is denoted $F(t,T_{1},T_{2})$  

A forward on a ZCB is a forward on an asset paying no income. So Result 4.6.1 (with $T=T_{1}$ and $S_{t}=Z(t,T_{2}))$ implies  

Result 5.2.1. Let $t\leq T_{1}\leq T_{2}$ . Then  

$$
F(t,T_{1},T_{2})=\frac{Z(t,T_{2})}{Z(t,T_{1})}
$$  

or equivalently  

$$
Z(t,T_{2})=Z(t,T_{1})F(t,T_{1},T_{2}).
$$  

Compare this to Result 5.1.2. Compare also Figure 5.1 to Figure 5.2.  

![](df4592665eb9b4763af50a74491510895d44bda7825a1124b9dbdc2784a6155d.jpg)  

Result 5.2.2. Let $t\leq T_{1}\leq T_{2}$ . If $f_{12}$ is the forward rate at $t$ for $T_{1}$ to $T_{2}$ with continuous compounding  

$$
F(t,T_{1},T_{2})=e^{-f_{12}(T_{2}-T_{1})}
$$  

Similar results hold for compounding $m$ times per year and for simple interest.  

We give two proofs.  

Proof $I$ .If $r_{i}$ is the continuous zero rate for $t$ to $T_{i}$ , then $Z(t,T_{i})=e^{-r_{i}(T_{i}-t)}$ , so Result 5.1.2 says  

$$
Z(t,T_{2})=Z(t,T_{1})e^{-f_{12}(T_{2}-T_{1})}.
$$  

On the other hand, Result 5.2.1 says  

$$
Z(t,T_{2})=Z(t,T_{1})F(t,T_{1},T_{2}).
$$  

It follows that  

$$
F(t,T_{1},T_{2})=e^{-f_{12}(T_{2}-T_{1})}.
$$  

# Proof 2. Consider  

A: Time $t$ $M=F(t,T_{1},T_{2})$ ZCBs with maturity $T_{1}$ . Enter a long forward contract with maturity $T_{1}$ and delivery price $K=M=F(t,T_{1},T_{2})$ on a ZCB with maturity $T_{2}$ . These  

contracts have no cost to enter, by the definition of $F(t,T_{1},T_{2})$ . Note that at $T_{1}$ the $M$ ZCBs will give us $M$ cash while the long forward will give us 1 ZCB with maturity $T_{2}$ and require us to pay $M$ cash. That will leave us with 1 ZCB with maturity $T_{2}$  

B: Time $t$ $N=e^{-f_{12}(T_{2}-T_{1})}$ ZCBs with maturity $T_{1}$ . Agree at $t$ to lend $N$ (the amount that will be gained from the ZCBs) from $T_{1}$ until $T_{2}$ at rate $f_{12}$  

Then $V^{A}(T_{2})=Z(T_{2},T_{2})=1$ and $V^{B}(T_{2})=N e^{f_{12}(T_{2}-T_{1})}=1$ . Thus $V^{A}(T_{2})=V^{B}(T_{2})$ with probability one. By replication,  

$$
V^{A}(t)=V^{B}(t)
$$  

or equivalently  

$$
F(t,T_{1},T_{2})Z(t,T_{1})=e^{-f_{12}(T_{2}-T_{1})}Z(t,T_{1}).
$$  

Divide by $Z(t,T_{1})$  

Example 5.2.3. Assume $t\leq T_{1}\leq T_{2}$ , where $t=$ current time. What can you say about interest rates between $T_{1}$ and $T_{2}$ if  

(a) $Z(t,T_{1})=Z(t,T_{2})$ (b) $Z(t,T_{1})>0$ and $Z(t,T_{2})=0$  

For annual compounding:  

(a) We have  

$$
F(t,T_{1},T_{2})=\frac{Z(t,T_{2})}{Z(t,T_{1})}=(1+f_{12})^{-(T_{2}-T_{1})}.
$$  

$$
(1+f_{12})^{-(T_{2}-T_{1})}=\frac{Z(t,T_{2})}{Z(t,T_{1})}=1,
$$  

so the forward rate $f_{12}$ between $T_{1}$ and $T_{2}$ must be 0. (b) We have  

$$
(1+f_{12})^{-(T_{2}-T_{1})}=\frac{Z(t,T_{2})}{Z(t,T_{1})}=0,
$$  

so the forward rate $f_{12}$ between $T_{1}$ and $T_{2}$ must be $\infty$  

The same is true for any compounding frequency.  

For continuous compounding:  

(i) We have  

$$
F(t,T_{1},T_{2})=\frac{Z(t,T_{2})}{Z(t,T_{1})}=e^{-f_{12}(T_{2}-T_{1})}.
$$  

$$
e^{-f_{12}(T_{2}-T_{1})}={\frac{Z(t,T_{2})}{Z(t,T_{1})}}=1,
$$  

so the forward rate $f_{12}$ between $T_{1}$ and $T_{2}$ must be 0. (ii) We have  

$$
e^{-f_{12}(T_{2}-T_{1})}={\frac{Z(t,T_{2})}{Z(t,T_{1})}}=0,
$$  

so the forward rate $f_{12}$ between $T_{1}$ and $T_{2}$ must be $\infty$  

Exercise 5.2.1. Give a third proof of Result 5.2.2 by assuming $F(t,T_{1},T_{2})\neq e^{-f_{12}(T_{2}-T_{1})}$ and constructing an arbitrage portfolio..  

You might find the idea of a forward rate (where one agrees in advance to an interest rate for borrowing over a future time period) to be a bit odd.  

The next example shows how we can arrange a forward interest rate by using forwards on ZCBs.  

Example 5.2.4. A bank wishes to set at present time $t$ a continuously compounded rate at which it can lend notional. $N$ to a customer from $T_{1}$ to $T_{2}$ . Here $t<T_{1}<T_{2}$ . How can it. use forwards on ZCBs to do? What should the interest rate be?  

At time $t$ , the bank enters into ${N}/{F(t,T_{1},T_{2})}$ forward contracts with the customer. The. bank takes the long position and the customer takes the short position. The forwards are on ZCBs with maturity $T_{2}$ . The maturity of the forwards is at $T_{1}$ . The delivery price is the forward ZCB price $F(t,T_{1},T)$ , neither party must pay to enter these contracts.  

At time $T_{1}$ , the forwards mature. So the bank pays to the customer. $F(t,T_{1},T)$ cash for each of the ${N}/{F(t,T_{1},T_{2})}$ forward contracts. Thus the banks gives the customer $N=$ $F(t,T_{1},T)\cdot N/F(t,T_{1},T_{2})$ cash. The customer gives the bank. ${N}/{F(t,T_{1},T_{2})}$ ZCBs with maturity $T_{2}$ . In other words, the customer gives the bank. ${N}/{F(t,T_{1},T_{2})}$ promises that the customer will pay 1 at time. $T_{1}$  

At time time $T_{2}$ , the ZCBs must be paid out. So the customer pays 1 to the bank for each of the ${N}/{F(t,T_{1},T_{2})}$ ZCBs. In other words, the customer pays the bank ${N}/{F(t,T_{1},T_{2})}$  

The number $r$ such that $N e^{r(T_{2}-T_{1})}=N/F(t,T_{1},T_{2})$ is the forward interest rate agreed at $t$ to lend from $T_{1}$ to $T_{2}$  

Of course, it is much more natural if the bank and the customer just agree to the forward rate directly. $\triangle$  

# 5.3 Libor  

Definition 5.3.1. The simple interest rate at which banks borrow or lend money to each other is called the libor rate or libor. $\triangle$  

Libor stands for London InterBank Offered Rate. Most interest rate derivatives are libor derivatives.  

Definition 5.3.2. $L_{t}[t,t+\alpha]$ is the libor (simple interest) rate agreed at $t$ to lend/borrow from $t$ to $t+\alpha$ . Here $\alpha>0$  

In other words,. $L_{t}[t,t+\alpha]$ is the rate agreed at time $t$ such that we lend/borrow $N$ at time $T$ and receive/return  

$$
N\left(1+\alpha L_{t}[t,t+\alpha]\right)
$$  

at time $t+\alpha$  

When $\alpha=1$ , the libor $L_{t}[t,t+\alpha]$ is called the 1-year libor or twelve-month libor or $12\mathrm{mL}$  

When $\alpha=0.25$ , the libor $L_{t}[t,t+\alpha]$ is called the quarter-year libor or three-month libor or $3\mathrm{mL}$  

Example 5.3.1. The current six-month libor is $3.46\%$ . If a bank lends $2,000,000$ at this rate, how much will they receive at term?  

$$
N(1+\alpha L_{t}[t,t+\alpha])=2,000,000(1+(0.5)(0.0346))=2,034,600
$$  

Remark 5.3.2. For $t<T$ , you might guess that $L_{t}[T,T+\alpha]$ is the libor rate agreed at $t$ to lend/borrow from $T$ to $T+\alpha$ and it should be called the forward libor rate.  

To match the textbook, we will define $L_{t}[T,T+\alpha]$ in a different way (Definition 5.6.1), but it will turn out to be equivalent to the above guess (Result 5.6.4).  

Definition 5.3.3. If $t$ is the current time and $T>t$ , then $L_{T}[T,T+\alpha]$ is the libor that.   
will be available at $T$ to lend/borrow from $T$ to $T+\alpha$ . It is unknown at time $t$ , thus it is a.   
random variable and said to be floating. $\triangle$  

Remark 5.3.3. In practice, libor (London InterBank Offered Rate) is the interest rate at which a bank offers to lend money and libid (London InterBank Bid Rate) is the interest rate at which a bank is willing to borrow money. For large transactions the two rates are very close together. To keep things simple, we assume libor. $=$ libid. $\triangle$  

# 5.4 Fixed and Floating Payments  

Let $t<T<T+\alpha$ , where $t$ is the current time. If notional 1 is invested at simple interest rate $r$ from time $T$ until time $T+\alpha$ then it will grow to $1+\alpha r$ . The amount of interest accrued is $\alpha r$ .If $r$ is a fixed (known, non-random) rate $K$ , then the interest accrued is $\alpha K$ . If $r$ is the floating (unknown, random) rate $L_{T}[T,T+\alpha]$ , then the interest accrued is $\alpha L_{T}[T,T+\alpha]$  

Result 5.4.1. Fix a constant $K>0$ . The value at $t$ of an agreement to receive the fixed (i.e., known, non-random) payment $\alpha K$ at time $T+\alpha$ is  

$$
\alpha K Z(t,T+\alpha)
$$  

Proof. The agreement is equivalent to $\alpha K$ ZCBs.  

Result 5.4.2. The value at $t$ of an agreement to receive the floating (i.e., unknown, random) payment $\alpha L_{T}[T,T+\alpha]$ at time $T+\alpha$ is  

$$
Z(t,T)-Z(t,T+\alpha),
$$  

which is the same value as an agreement to receive 1 at time $T$ and pay back 1 at time $T+\alpha$  

Remark. Notice the value is non-random. It does not even depend on the distribution of the random variable $L_{T}[T,T+\alpha]$  

Proof. Consider two portfolios.  

A: An agreement to receive $\alpha L_{T}[T,T+\alpha]$ at time $T+\alpha$   
B: Time $t$ : An agreement to receive 1 at time $T$ and pay back 1 at time $T+\alpha$ . (Equivalently, $+1$ ZCB with maturity $T$ $-1$ ZCB with maturity $T+\alpha$ Time $T$ : Deposit the 1 received from the agreement at random Libor $L_{T}[T,T+\alpha]$ until time $T+\alpha$  

At time $T+\alpha$ ..  

$$
\begin{array}{r l}&{V^{A}(T+\alpha)=\alpha L_{T}[T,T+\alpha],}\ &{V^{B}(T+\alpha)=1+\alpha L_{T}[T,T+\alpha]-1=\alpha L_{T}[T,T+\alpha].}\end{array}
$$  

By replication, $V^{A}(t)=V^{B}(t)=Z(t,T)-Z(t,T+\alpha)$  

# 5.5 Forward Rate Agreements  

Definition 5.5.1. A forward rate agreement (FRA) a derivative to exchange the floating (unknown, random) amount of cash. $\alpha L_{T}[T,T+\alpha]$ for the fixed (known, non-random). amount of cash $\alpha K$  

It has three parameters: $K=$ fixed rate or delivery price; $T=$ maturity; $\alpha=$ term length or daycount fraction or accrual factor.  

The buyer (long counterparty) of the FRA agrees at time $t\leq T$ to  

$$
\left.\begin{array}{l}{{\mathrm{receive}\alpha L_{T}[T,T+\alpha]\left.\right\}}}\ {{\mathrm{pay}\alpha K}}\end{array}\right\}
$$  

The seller (short counterparty) agrees to do the opposite.  

The payout of the FRA for the buyer is  

$$
g(L_{T}[T,T+\alpha])=\alpha L_{T}[T,T+\alpha]-\alpha K
$$  

at time $T+\alpha$ . Here $g(x)=\alpha x-\alpha K$ is the payout function.  

The value of the FRA at time $t\leq T$ is denoted $V_{K}(t,T)$  

$\alpha L_{T}[T,T+\alpha]$ is the amount of simple interest that would be accrued on notional 1 at floating (unknown, random) rate. $L_{T}[T,T+\alpha]$ over period $T$ to $T+\alpha$  

$\alpha K$ is the amount of simple interest that would be accrued on notional 1 at fixed (known, non-random) rate $K$ over period $T$ to $T+\alpha$  

Forwards are derivatives of the price $S_{T}$ of an asset. FRAs are derivatives of the libor rate $L_{T}[T,T+\alpha]$  

Result 5.5.1. The value of the FRA with fixed rate $K$ , maturity $T$ , and term length. $\alpha$ at time $t\leq T$ is  

$$
V_{K}(t,T)=Z(t,T)-Z(t,T+\alpha)-\alpha K Z(t,T+\alpha).
$$  

Proof. Combine Results 5.4.1 and 5.4.2.  

Remark 5.5.2. Notice the value at present time $t$ does not depend on the distribution of the random variable $L_{T}[T,T+\alpha]$ . This is just like how the value of a forward contract on an asset does not depend on the the random variable $S_{T}$ (asset price). $\triangle$  

# 5.6 Forward Libor Rate  

Definition 5.6.1. Let $T$ and $\alpha$ be given. The forward libor rate at time. $t\leq T$ is the number $L_{t}[T,T+\alpha]$ such that the forward rate agreement with fixed rate $K=L_{t}[T,T+\alpha]$ maturity $T$ , and term length $\alpha$ is $V_{K}(t,T)=0$ at time $t$ . Thus,  

Note the similarity with the forward price. $F(t,T)$ for an asset. Just like the forward price. of an asset is the "fair delivery price' for a forward contract on the asset, the forward libor rate is the 'fair fixed rate" for an forward rate agreement (FRA) on libor..  

Result 5.6.1. Let $T$ and $\alpha$ be given. The forward libor rate at time $t\leq T$ is  

$$
L_{t}[T,T+\alpha]=\frac{Z(t,T)-Z(t,T+\alpha)}{\alpha Z(t,T+\alpha)}.
$$  

Proof. Set $K=L_{t}[T,T+\alpha]$ and $V_{K}(t,T)=0$ in (5.5.1), and solve for $L_{t}[T,T+\alpha]$  

Example 5.6.2. Suppose the one-year and two-year continuous zero rates are $1\%$ and $2\%$ respectively. What is the one-year forward one-year libor rate?.  

Assume current time $t=0$  

one-year continuous zero $=$ continuous zero rate for period O to $1=1\%$  

two-year continuous zero $=$ continuous zero rate for period O to $2=2\%$  

The $m$ year forward $n$ -year libor rate is the forward libor rate for the period starting $m$ years from now and ending. $n$ years after that.  

Want: one-year forward one-year libor rate $={\cal L}_{t}[T,T+\alpha]$ with $t=0$ $T=1$ $\alpha=1$ $T+\alpha=2$  

$$
\begin{array}{c}{{L_{t}[T,T+\alpha]=\displaystyle\frac{Z(t,T)-Z(t,T+\alpha)}{\alpha Z(t,T+\alpha)}=\displaystyle\frac{Z(0,1)-Z(0,2)}{Z(0,2)}}}\ {{=\displaystyle\frac{e^{-(0.01)(1)}-e^{-(0.02)(2)}}{e^{-(0.02)(2)}}=0.0304545...}}\end{array}
$$  

Result 5.6.3. For $t<T<T+\alpha$  

$$
Z(t,T+\alpha)=Z(t,T)\frac{1}{1+\alpha L_{t}[T,T+\alpha]}.
$$  

Proof. Rearrange (5.6.1).  

![](6d15a5b25cf65010af580f860511c8cede7647e86b77673165a5f80c0c5c6c21.jpg)  
Figure 5.2: Discounting by ZCBs and the forward libor rate  

Compare Result 5.6.3 to Results 5.1.2 and 5.1.4. Compare also Figure 5.2 to Figures 5.1 and 5.2.  

Result 5.6.4. Let $t<T$ and $\alpha>0$ . The forward libor rate $L_{t}[T,T+\alpha]$ is the libor (simple interest) rate that we can agree on at $t$ to lend/borrow $N$ at time $T$ and receive/return  

$$
N(1+\alpha L_{t}[T,T+\alpha])
$$  

at time $T+\alpha$  

This result says that $L_{t}[T,T+\alpha]$ really is a forward interest rate (as the name and the.   
notation implies), in addition to being the "fair fixed rate' for an FRA on libor.  

Proof. We consider the case of lending. The borrowing case is analogous.  

We agree at time $t$ to do the following:  

Time $t$ :We go short on. $N$ FRAs with with maturity $T$ ,term length $\alpha$ , and fixed rate. $K=L_{t}[T,T+\alpha]$ . By the definition of the forward libor rate (Definition 5.6.1), this is free to do.  

Time $T$ : Lend $N$ at the random libor rate $L_{T}[T,T+\alpha]$ until $T+\alpha$  

Time $T+\alpha$ : Receive $N(1+\alpha L_{T}[T,T+\alpha])$ because of the loan we made at $T$ . Receive $N\alpha L_{t}[T,T+\alpha]$ and pay $N\alpha L_{T}[T,T+\alpha])$ because of the short FRAs we entered at $t$ . In total, we get  

$$
N(1+\alpha L_{T}[T,T+\alpha])+N\alpha L_{t}[T,T+\alpha]-N\alpha L_{T}[T,T+\alpha])=N(1+\alpha L_{t}[T,T+\alpha])
$$  

Summary: At time $t$ we entered into an agreement at no cost that allowed us to give out $N$ at time $T$ and get back $N(1+\alpha L_{t}[T,T+\alpha])$ at time.  

# 5.7 Forward Rates Unified  

Let's write down the pieces.  

Result 5.7.1 (Restatement of Result 5.2.1). For $t\leq T_{1}\leq T_{2}$  

$$
Z(t,T_{2})=Z(t,T_{1})F(t,T_{1},T_{2})
$$  

Result 5.7.2. For $t\leq T$  

$Z(t,T)=\left\{\begin{array}{l l}{e^{-r(T-t)}}&{\mathrm{if~}r\mathrm{~is~continuous~zero~rate~at~}t\mathrm{~for~period~}t\mathrm{~to~}T}\ {\left(1+\frac{r}{m}\right)^{-m(T-t)}}&{\mathrm{if~}r\mathrm{~is~}m\mathrm{-times\mathrm{-per-year-compounding~zero~rate~}}}\ {\left(1+r(T-t)\right)^{-1}}&{\mathrm{if~}r=L_{t}[t,T]\mathrm{~is~libor~(simple)~rate~at~}t\mathrm{~for~period~}t\mathrm{~to~}T}\end{array}\right.$ at $t$ for period $t$ to $T$ $t$ to $T$  

Proof. Combine Results 3.2.1, 3.2.5, 3.2.6.  

![](068775f8dfd8e162ad10e3e842b9768bc2534a57eb8a93289d7a15d126756d24.jpg)  

Result 5.7.3. For $t\leq T_{1}\leq T_{2}$  

$\begin{array}{r}{F(t,T_{1},T_{2})=\left\{\begin{array}{l l}{e^{-f_{12}(T_{2}-T_{1})}}\ {\left(1+\frac{f_{12}}{m}\right)^{-m(T_{2}-T_{1})}}\ {\left(1+f_{12}(T_{2}-T_{1})\right)^{-1}}\end{array}\right.}\end{array}$ if $f_{12}$ is continuous forward rate at $t$ for period $T_{1}$ to $T_{2}$ if $f_{12}$ is $m$ -times-per-year-compounding forward rate at $t$ for period $T_{1}$ to $T_{2}$ if $f_{12}=L_{t}[T_{1},T_{2}]$ is forward libor (simple) rate at $t$ for period $T_{1}$ to $T_{2}$  

Proof. Mimic the proof of Result 5.2.2.  

The next example shows how the pieces fit together.  

Example 5.7.4. The two-year forward one-year libor rate is $3\%$ The price of a ZCB maturing in 3 years is 0.7. Find the continuous two-year zero rate..  

We are given  

$$
L_{t}[T_{1},T_{2}]=0.03\quad\mathrm{and}\quad Z(t,T_{2})=0.7,
$$  

where $t$ is the current time, $T_{1}=t+2$ , and $T_{2}=T_{1}+1=t+3$  

We want $r=\tt c$ ontinuous zero rate at $t$ for period $T_{1}=t+2$ and $T_{2}=t+3$  

By the results above, the quantities are related by  

$$
Z(t,T_{2})=e^{-r\cdot(T_{1}-t)}(1+(T_{2}-T_{1})L_{t}[T_{1},T_{2}])^{-1}.
$$  

![](015514239c2efd33d12040991161945a0ac3565a55b0ac4168a14155f73d8a87.jpg)  

Solving for $r$ and substituting gives  

$$
\begin{array}{l}{{r=\displaystyle\frac{1}{T_{1}-t}\ln\left((Z(t,T_{2}))^{-1}(1+(T_{2}-T_{1})L_{t}[T_{1},T_{2}])^{-1}\right)}}\ {{~=\displaystyle\frac{1}{2}\ln\left((0.7)^{-1}(1+(1)(0.03))^{-1}\right)}}\ {{~=0.163558\ldots.}}\end{array}
$$  

# Chapter 6  

# Interest Rate Swaps  

Interest rate swaps are the most widely traded and most liquid of all over-the-counter derivative contracts.  

# 6.1 Swap Definition  

Definition 6.1.1. A swap is an agreement between two counterparties to exchange a sequence of floating (unknown, random) cash flows for a sequence of fixed (known, nonrandom) cash flows.  

Parameters: $K=$ fixed rate or delivery price; $T_{0}=$ start date; $T_{n}=$ maturity; $T_{1},\dots,T_{n}=$   
payment dates.  

We assume $T_{i+1}=T_{i}+\alpha$ for every $i$ with fixed $\alpha>0$  

So knowing $n,T_{0}$ , and $T_{n}$ is enough to determine $\alpha$ and every $T_{i}$ .. $T_{n}=T_{0}+n\alpha$ and $T_{i}=T_{0}+i\alpha$  

One counterparty (called "buyer', "payer", or "long") agrees at $t$ to pay $\alpha K$ and receive $\alpha L_{T_{i}}[T_{i},T_{i}+\alpha]$ at $T_{i}+\alpha$ for each $i=0,\ldots,n-1$ The other counterparty (called "seller', "receiver", or "short') does the opposite.  

Therefore a swap is a sequence of forward rate agreements (FRAs).  

The floating leg of the swap consists of the payments $\alpha L_{T_{i}}[T_{i},T_{i}+\alpha]$ at times $T_{i+1}=T_{i}+\alpha$ for $i=0,\ldots,n-1$  

The fixed leg of the swap consists of the payments $\alpha K$ at times $T_{i+1}=T_{i}+\alpha$ for $i=$ $0,\ldots,n-1$  

The buyer receives the floating leg and pays the fixed leg. The seller does the opposite. $\triangle$  

$\alpha L_{T_{i}}[T_{i},T_{i}+\alpha]$ is the amount of simple interest that would be accrued on notional 1 at  

floating (unknown, random) rate $L_{T_{i}}[T_{i},T_{i}+\alpha]$ from $T_{i}$ to $T_{i}+\alpha$ and paid at $T_{i}+\alpha$  

$\alpha K$ is the amount of simple interest that would be accrued on notional 1 at fixed (known, non-random) rate $K$ from $T_{i}$ to $T_{i}+\alpha$ and paid at $T_{i}+\alpha$  

![](5f6b7323da54237a5576629843704e3a4c19ef6cf3d95f8502602a4d0ad7d07c.jpg)  
Figure 6.1: A swap  

Remark 6.1.1. The definition above is for a swap with notional 1. To treat a swap with notional $N$ , either consider $N$ swaps of notional 1 or make the payments $N\alpha L_{T_{i}}[T_{i},T_{i}+\alpha]$ and $N\alpha K$ $\triangle$  

Remark 6.1.2. There are more general types of swaps. For example,. $\alpha$ can be different for each period, so that $T_{i+1}=T_{i}+\alpha_{i}$ . As another example, the payment times for the floating. and fixed legs may differ. This will be explored in the exercises.  

# 6.2 Value of Swap  

Consider a swap from $T_{0}$ to $T_{n}$ with fixed rate $K$  

Definition 6.2.1. For $t\leq T_{0}$  

$$
\begin{array}{r l}&{V_{K}^{S W}(t)={\mathrm{value~of~the~swap~at~}}t}\ &{V^{F L}(t)={\mathrm{value~of~the~floating~leg~a~}}}\ &{V_{K}^{F X D}(t)={\mathrm{value~of~the~flxed~leg~}}t}\end{array}
$$  

Result 6.2.1.  

$$
V_{K}^{S W}(t)=V^{F L}(t)-V_{K}^{F X D}(t).
$$  

Note that ${V}_{K}^{S W}(t)$ is the value to the buyer. The value to the seller is the $-V_{K}^{S W}(t)$ The fixed leg is a sequence of ZCBs with maturities at $T_{1},\dots,T_{n}$ , so  

Result 6.2.2.  

$$
V_{K}^{F X D}(t)=\sum_{i=1}^{n}\alpha K Z(t,T_{i})=K P_{t}[T_{0},T_{n}],
$$  

where we define  

$$
P_{t}[T_{0},T_{n}]=\sum_{i=1}^{n}\alpha Z(t,T_{i}).
$$  

The floating leg is a sequence of floating libor payments at $T_{1},\dots,T_{n}$ , so by Result 5.4.2 we have  

# Result 6.2.3.  

$$
\begin{array}{l}{{\displaystyle V^{F L}(t)=\sum_{i=1}^{n}(\mathrm{value~at~t~of~payment}~\alpha L_{T_{i-1}}[T_{i-1},T_{i}]~\mathrm{at}~T_{i}=T_{i-1}}}\ {{\displaystyle~=\sum_{i=1}^{n}\alpha L_{t}[T_{i-1},T_{i}]Z(t,T_{i})=\sum_{i=1}^{n}[Z(t,T_{i-1})-Z(t,T_{i})]}}\ {{\displaystyle~=Z(t,T_{0})-Z(t,T_{n})}}\end{array}
$$  

This says the value of receiving a stream of libor interest payments on an investment of 1 is. equal to the value of receiving one dollar at the beginning of the stream and paying it back at the end. We simply take the dollar and repeatedly invest in a sequence of libor deposits.  

By combining Results 6.2.1, 6.2.2, and 6.2.3, we can write ${V}_{K}^{S W}(t)$ as a linear combination of ZCB prices.  

Result 6.2.4.  

$$
V_{K}^{S W}(t)=Z(t,T_{0})-Z(t,T_{n})-\alpha K\sum_{i=1}^{n}Z(t,T_{i}).
$$  

Example 6.2.5. Consider a swap starting now with fixed rate $3\%$ , quarterly payment frequency, and ending in 2 years. Suppose the quarterly compounded zero rates for all payment times are $2\%$ . Find the present value of  

(a) the floating leg (b) the swap  

(a) Given $t=T_{0}$ $T_{n}-t=2$ $\alpha=0.25$ $r_{4}=0.02$  

$$
\begin{array}{c}{{V^{F L}(t)=Z(t,T_{0})-Z(t,T_{n})=1-(1+r_{4}/4)^{-4(T_{n}-t)}}}\ {{=1-(1+0.02/4)^{-4(2)}=0.039114...}}\end{array}
$$  

(b) Since VSW(t) = VFI $V_{K}^{S W}(t)=V^{F L}(t)-V_{K}^{F X D}(t)$ , we just neede $V_{K}^{F X D}(t)$  

Have $K=0.03$ . Have $T_{i}-t=T_{i}-T_{0}=i\alpha=i0.25$ . Using $T_{n}=T_{0}+n\alpha$ (or drawing a picture), we get $n=8$ . Then  

$$
V_{K}^{F X D}(t)=\alpha K\sum_{i=1}^{n}Z(t,T_{i})=\alpha K\sum_{i=1}^{n}(1+r_{4}/4)^{-4(T_{i}-t)}=\alpha K\sum_{i=1}^{n}(1+r_{4}/4)^{-i}
$$  

The sum  

$$
\sum_{i=1}^{n}(1+r_{4}/4)^{-i}=\sum_{i=1}^{8}(1+0.02/4)^{-i}
$$  

only has 8 terms, so we could just compute it directly. Or we can use the formula  

$$
\sum_{i=1}^{n}(1+r_{4}/4)^{-i}=\frac{1-(1+r_{4}/4)^{-n}}{r_{4}/4}.
$$  

Then  

$$
{}^{\cdot D}(t)=\alpha K{\frac{1-(1+r_{4}/4)^{-n}}{r_{4}/4}}=(0.25)(0.03){\frac{1-(1+0.02/4)^{-8}}{0.02/4}}=0.05867219...
$$  

Therefore  

$$
\begin{array}{l}{{V_{K}^{S W}(t)=V^{F L}(t)-V_{K}^{F X D}(t)}}\ {{{}~=1-(1+0.02/4)^{-4(2)}-(0.25)(0.03){\frac{1-(1+0.02/4)^{-8}}{0.02/4}}}}\ {{{}~=-0.0195573\ldots}}\end{array}
$$  

# 6.3 Forward Swap Rate  

Definition 6.3.1. The forward swap rate $y_{t}[T_{0},T_{n}]$ is the special number such that the value at $t$ of the swap from $T_{0}$ to $T_{n}$ with fixed rate $K=y_{t}[T_{0},T_{n}]$ has value ${\cal V}_{K}^{S W}(t)=0$ Thus,  

$$
{\cal V}_{K}^{S W}(t)=0\quad\mathrm{~if~and~only~if~}K=y_{t}[T_{0},T_{n}].
$$  

Note the similarity to the forward price $F(t,T)$ and forward libor rate. $L_{t}[T,T+\alpha]$  

Result 6.3.1. The forward swap rate at $t\leq T_{0}$ for a swap from $T_{0}$ to $T_{n}$ is  

$$
y_{t}[T_{0},T_{n}]=\frac{Z(t,T_{0})-Z(t,T_{n})}{P_{t}[T_{0},T_{n}]}=\frac{\sum_{i=1}^{n}\alpha L_{t}[T_{i-1},T_{i}]Z(t,T_{i})}{\sum_{i=1}^{n}\alpha Z(t,T_{i})}.
$$  

Proof. We use Results 6.2.1, 6.2.2, 6.2.3. Setting $K=y_{t}[T_{0},T_{n}]$ gives  

$$
\begin{array}{r c l}{{V_{K}^{S W}(t)=0}}&{{\Leftrightarrow}}&{{\displaystyle V_{K}^{F X D}(t)=V^{F L}(t)}}\ {{}}&{{\Leftrightarrow}}&{{\displaystyle K P_{t}[T_{0},T_{n}]=Z(t,T_{0})-Z(t,T_{n})}}\ {{}}&{{\Leftrightarrow}}&{{\displaystyle K\sum_{i=1}^{n}\alpha Z(t,T_{i})=\sum_{i=1}^{n}\alpha L_{t}[T_{i-1},T_{i}]Z(t,T_{i})}}\end{array}
$$  

Solving (6.3.3) for $K$ gives the first equality in (6.3.1).  

Solving (6.3.4) for $K$ gives the second equality in (6.3.1).  

# 6.4 Value of Swap in Terms of Forward Swap Rate  

Result 6.4.1. The value at $t\leq T_{0}$ of a swap from $T_{0}$ to $T_{n}$ with fixed rate $K$ is  

$$
V_{K}^{S W}(t)=(y_{t}[T_{0},T_{n}]-K)P_{t}[T_{0},T_{n}]=\left(y_{t}[T_{0},T_{n}]-K\right)\sum_{i=1}^{n}\alpha Z(t,T_{i})
$$  

Remark. Compare this to the relationship between the value of a forward on an asset and the forward price of the asset.  

$$
V_{K}(t,T)=(F(t,T)-K)Z(t,T).
$$  

Proof. By Results 6.2.1, 6.2.2, and 6.2.3, we have  

$$
V_{K}^{S W}(t)=V^{F L}(t)-V_{K}^{F X D}(t)=Z(t,T_{0})-Z(t,T_{n})-K P_{t}[T_{0},T_{n}].
$$  

By Result 6.3.1, we have  

$$
Z(t,T_{0})-Z(t,T_{n})=y_{t}[T_{0},T_{n}]P_{t}[T_{0},T_{n}].
$$  

# 6.5 Swaps as Difference Between Bonds  

Definition 6.5.1. A fixed rate bond with notional $N$ , coupon $c$ , start date $T_{0}$ , maturity $T_{n}$ and term length. $\alpha$ is an asset that pays $N$ at time $T_{n}$ and also coupon payments. $\alpha N c$ at times $T_{i}$ for $i=1,\ldots,n$ , where $T_{i+1}=T_{i}+\alpha$  

If $N=1$ , the price at $t$ of the fixed rate bond is denoted $B_{c}^{F X D}(t)$  

Definition 6.5.2. A floating rate bond with notional $N$ , start date $T_{0}$ , maturity $T_{n}$ , and term length $\alpha$ is an asset that pays. $N$ at time $T_{n}$ and also coupon payments $\alpha N L_{T_{i-1}}[T_{i-1},T_{i}]$ at times $T_{i}$ for $i=1,\ldots,n$ , where $T_{i+1}=T_{i}+\alpha$  

If $N=1$ , the price at $t$ of the floating rate bond is denoted $B^{F L}(t)$  

Result 6.5.1. Consider a swap from $T_{0}$ to $T_{n}$ with fixed rate $K$ . For $t\leq T_{0}$  

$$
{\cal V}_{\cal K}^{S W}(t)={\cal B}^{F L}(t)-{\cal B}_{\cal K}^{F X D}(t)
$$  

Proof. The fixed rate bond with notional 1 and coupon $K$ equals the fixed leg of the swap plus a payment of 1 at $T_{n}$  

The floating rate bond with notional 1 equals the floating leg of the swap plus a payment of 1 at $T_{n}$  

Therefore  

$$
\begin{array}{r l}&{\boldsymbol{B}^{F L}(t)-\boldsymbol{B}_{K}^{F X D}(t)=(V^{F L}(t)+Z(t,T_{n}))-(V_{K}^{F X D}(t)+Z(t,T_{n}))}\ &{\qquad=V^{F L}(t)-V_{K}^{F X D}(t)}\ &{\qquad=V_{K}^{S W}(t).}\end{array}
$$  

# 6.6 Par or Spot-Starting Swaps  

Definition 6.6.1. When $t=T_{0}$ , we call $y_{T_{0}}[T_{0},T_{n}]$ a par swap rate or spot-starting swap rate.  

Remark 6.6.1. Given par swap rates $y_{T_{0}}[T_{0},T_{k}]$ for every $T_{k}$ , we can recover the ZCB price $Z(T_{0},T_{k})$ for every $T_{k}$ by using Result 6.3.1:  

$$
y_{t}[T_{0},T_{k}]=\frac{Z(t,T_{0})-Z(t,T_{k})}{P_{t}[T_{0},T_{k}]}=\frac{Z(t,T_{0})-Z(t,T_{k})}{\sum_{i=1}^{n}\alpha Z(t,T_{i})}
$$  

This process is known as bootstrapping and is used frequently in practice. It will be explored in the exercises.  

Reminder:  

Definition 6.6.2. A fixed rate bond with notional $N$ , coupon $c$ , start date $T_{0}$ , maturity $T_{n}$ and term length. $\alpha$ is an asset that pays $N$ at time $T_{n}$ and also coupon payments. $\alpha N c$ at times $T_{i}$ for $i=1,\ldots,n$ , where $T_{i+1}=T_{i}+\alpha$  

If $N=1$ , the price at $t$ of the fixed rate bond is denoted $B_{c}^{F X D}(t)$  

Result 6.6.2.  

$B_{c}^{F X D}(T_{0})=1$ if and only if $c=y_{T_{0}}[T_{0},T_{n}]=$ par swap rate  

Because of this result, the par swap rate $y_{T_{0}}[T_{0},T_{n}]$ is sometimes called the coupon rate.  

Result 6.6.2 can be rephrased as  

Result 6.6.3. The par swap rate $y_{T_{0}}[T_{0},T_{n}]$ is the fixed rate such that we can invest 1 at time $T_{0}$ , receive 1 back at time $T_{n}$ , and receive fixed payments of $\alpha y_{T_{0}}[T_{0},T_{n}]$ at times $T_{1},\dots,T_{n}$ in between. This is not true if $y_{T_{0}}[T_{0},T_{n}]$ is replaced by any other coupon rate $c$  

Proof of Result 6.6.2. By definition of the par swap rate $y_{T_{0}}[T_{0},T_{n}]$ , we have  

$$
V_{c}^{S W}(T_{0})=0\quad\mathrm{if~and~only~if}\quad c=y_{T_{0}}[T_{0},T_{n}].
$$  

But  

$$
V_{c}^{S W}(T_{0})=B^{F L}(T_{0})-B_{c}^{F X D}(T_{0})
$$  

and  

$$
B^{F L}(T_{0})=V^{F L}(T_{0})+Z(T_{0},T_{n})=Z(T_{0},T_{0})-Z(T_{0},T_{n})+Z(T_{0},T_{n})=Z(T_{0},T_{0})
$$  

Therefore  

$$
\begin{array}{r}{1-B_{c}^{F X D}(T_{0})=0\quad\mathrm{if~and~only~if}\quad c=y_{T_{0}}[T_{0},T_{n}].}\end{array}
$$  

# Chapter 7  

# Futures Contracts  

# 7.1 Physical and Cash Settlement  

We briefly recall the definition of a forward contract.  

Fix an asset. Let. $S_{t}$ be its price at time. $t$ . Fix times $t\leq T$ . A forward contract (or forward) on the asset with maturity $T$ and delivery price. $K$ is an agreement to trade the asset. At maturity $T$ , the long counterparty receives (pays if negative) value  

$$
S_{T}-K=F(T,T)-K.
$$  

The short counterparty does the opposite. There are no payments in between. If $K$ equals the forward price $F(t,T)$ , the contract has no cost to enter (the value is zero) at time. $t$  

Definition 7.1.1. In a physically settled forward, at time $T$ the long counterparty receives the asset (value $S_{T}$ ) and pays $K$ cash. In a cash settled forward, the long counterparty receives $S_{T}$ cash and pays $K$ cash.  

Previously, we have always considered physically settled rather than cash settled forwards. Both have the same value at maturity $T$ , hence at any time $t\leq T$ . However, a cash settled forward has no exposure to the asset price after $T$ , while a physically settled contract ( where one owns the asset at $T$ ) continues to have exposure to asset price movements.  

Other types of derivative contracts can be either physically-settled or cash-settled. When. we define futures contracts below, it may be helpful to cash settlement in mind, rather than physical settlement.  

# 7.2 Futures Definition  

Definition 7.2.1. Fix an asset. Let $S_{t}$ be its price at time $t$ . Fix times $t\leq T$ . A futures contract (or future) on the asset with maturity $T$ and delivery price. $K$ is an agreement to  

trade the asset. Unlike a forward contract, there are payments every day until the maturity date $T$ .We describe the payments below. If. $K$ equals the futures price. $\Phi(t,T)$ , the contract has no cost to enter (i.e., the value is zero) at time $t$  

Let $\begin{array}{r}{\Delta=\frac{1}{365}}\end{array}$ . Since we measure time in years, day 1 is time $t+\Delta$ and day $i$ is time $t+i\Delta$ We define day $n$ to be maturity $T$ , so that $T=t+n\Delta$  

On day O, the long counterparty receives (pays if negative) the amount  

$$
\Phi(t,T)-K.
$$  

On day 1, the long counterparty receives (pays if negative) the amount  

$$
\Phi(t+\Delta,T)-\Phi(t,T).
$$  

On each day $1<i<n$ , the long counterparty receives (pays if negative) the amount  

$$
\Phi(t+i\Delta,T)-\Phi(t+(i-1)\Delta,T)
$$  

On day $n$ , the long counterparty receives (pays if negative) the amount  

$$
\Phi(T,T)-\Phi(t+(n-1)\Delta,T)
$$  

The payment amount on each day is called the mark-to-market payment (or mark-tomarket change or variation margin). The mark-to-market payments are invested (or borrowed) when they are paid, so they accrue interest.  

For the short counterparty, the payments are, of course, the negatives of these amounts.  

Usually $K=\Phi(t,T)$ (i.e., the delivery price is the futures price), so that there is no markto-market change on day zero.  

$\Phi(t+i\Delta,T)$ is the future price on day. $i$ . It costs nothing to enter a futures contract at $t+i\Delta$ if the delivery price is $\Phi(t+i\Delta,T)$ and maturity is. $T$  

At current time. $t$ $\Phi(t+i\Delta,T)$ is unknown (random) for $i\geq1$  

The future price at maturity $T$ is defined to be $\Phi(T,T)=S_{T}$  

Over the life of the futures contract, the long counterparty receives mark-to-market payments that total  

$$
\begin{array}{c}{{S_{T}-K=\Phi(T,T)-K}}\ {{{}}}\ {{\mathrm{~,~}T)-\Phi(t+(n-1)\Delta,T)+\cdot\cdot\cdot+\Phi(t+i\Delta,T)-\Phi(t+(i-1)\Delta,T)+\cdot\cdot\cdot+\Phi(t,T)-K}}\end{array}
$$  

However, each payment is made at a different time and accrues interest, so the value of the payments at $T$ will not in general equal. $S_{T}-K$  

Remark. We have described the payments for cash settlement, where the final payment is $\Phi(T,T)=S_{T}$ cash minus $\Phi(t+(n-1)\Delta,T)$ cash. For physical settlement, the final payment is the asset (value) $\Phi(T,T)=S_{T})$ minus $\Phi(t+(n-1)\Delta,T)$ cash.  

Remark. In practice, at $t$ each counterparty in a futures contract makes a deposit called an initial margin or performance bond in an account at an exchange. Each day, the exchange. transfers the appropriate variation margin amount from one counterparties account to the other. The initial margin needs to be large enough to cover several days of likely variation margin transfers. A typical initial margin is. $5\%$ to $15\%$ of the value $S_{t}-K$ . If the account balance of a counterparty drops below a certain level, called the maintenance margin,. the exchange may issue a margin call to that counterparty. A margin call is a demand to replenish the account. If the account is not replenished, then the futures contract is closed and the counterparties are paid the balance of their accounts. Note that the accounts accrue interest. In other words, the initial margin and variation margin accrue interest..  

# 7.3 Futures Prices When Rates Are Constant: Result and Examples  

Result 7.3.1. If interest rates are constant, then  

$$
\Phi(t,T)=F(t,T)
$$  

for all $t\leq T$  

Before we give the proof, here are some examples.  

Example 7.3.2. If interest rates are constant, then  

$$
\Phi(t+i\Delta,T)=F(t+i\Delta,T)
$$  

for all $t\leq T,i=0,1,\dots,n$  

Example 7.3.3. If interest rates are constant and if the underlying asset is a stock paying no income, then  

$$
\Phi(t,T)=S_{t}e^{r(T-t)}.
$$  

Example 7.3.4. If interest rates are constant and if the underlying asset is a stock that pays dividends at continuous rate $q$ , then  

$$
\Phi(t,T)=S_{t}e^{(r-q)(T-t)}.
$$  

Example 7.3.5. The table below is for a future contract maturing on day 5 with delivery price equal to the futures price. The underlying asset is a stock paying no income, and the constant continuously compounded interest rate $8\%$ .The MTM column lists market-tomarket payment The interest column lists the interest on the mark-to-market payment that will be accumulated over the life of the contract. All values are rounded off.  

As an exercise, do the calculations to reproduce the last three columns in this table.  

<html><body><table><tr><td>day</td><td>+S</td><td>Φ(t, T)</td><td>MTM</td><td>interest</td></tr><tr><td>0</td><td>1000</td><td>1001.10</td><td>0</td><td>0</td></tr><tr><td>1</td><td>1020</td><td>1020.89</td><td>19.80</td><td>0.017</td></tr><tr><td>2</td><td>980</td><td>980.64</td><td>-40.25</td><td>-0.026</td></tr><tr><td>3</td><td>1020</td><td>1020.45</td><td>39.80</td><td>0.017</td></tr><tr><td>4</td><td>1050</td><td>1050.23</td><td>29.78</td><td>0.007</td></tr><tr><td>5</td><td>1030</td><td>1030</td><td>-20.23</td><td>0</td></tr><tr><td></td><td></td><td>sum:</td><td>28.90</td><td>0.015</td></tr></table></body></html>  

Note that value of the corresponding forward contract at maturity is  

$$
\begin{array}{r}{S_{T}-F(t,T)=1030-1001.10=28.90.}\end{array}
$$  

# 7.4 Futures Prices When Rates Are Constant: Proof  

Proof of Result 7.3.1. For simplicity assume $t~=~0$ .Then $T=n\Delta$ .Let the constant continuously compounded interest rate be $r$  

Note that we can make trades in a portfolio, as long as they have no cost. For example, we can't just add or subtract cash to a portfolio..  

Consider the portfolio having the following strategy.  

At time 0, go long $e^{-r(n-1)\Delta}$ futures contracts with maturity $T$ at deliver price equal to the futures price $\Phi(0,T)$ . By the definition of the futures prices, we can do this at no cost.  

At time $\Delta$ , increase position to $e^{-r(n-2)\Delta}$ futures at futures price $\Phi(\Delta,T)$ . That is, we go long on $e^{-r(n-2)\Delta}-e^{-r(n-1)\Delta}$ futures with maturity $T$ at delivery price equal to the futures price $\Phi(\Delta,T)$ . Again, by the definition of the futures prices, we can do this at no cost.  

At time $i\Delta$ (for $i=2,\dots,n-2)$ , increase position to $e^{-r(n-i-1)\Delta}$ futures at futures price $\Phi(i\Delta,T)$  

At time $(n-1)\Delta$ , increase position to 1 futures contract at futures price $\Phi((n-1)\Delta,T)$ With this strategy we receive the following amounts.  

At time $\Delta$ , we receive mark-to-market gain/loss  

$$
(\Phi(\Delta,T)-\Phi(0,T))e^{-r(n-1)\Delta}.
$$  

This will be invested at rate $r$ . So by time $T=n\Delta$ (after time $T-\Delta=(n-1)\Delta$ has passed) it becomes  

$$
(\Phi(\Delta,T)-\Phi(0,T))e^{-r(n-1)\Delta}\cdot e^{r(n-1)\Delta}=\Phi(\Delta,T)-\Phi(0,T).
$$  

At time $(i+1)\Delta$ we receive mark-to-market gain/loss  

$$
(\Phi((i+1)\Delta,T)-\Phi(i\Delta,T))e^{-r(n-i-1)\Delta}.
$$  

This will be invested at rate $r$ . So by time $T=n\Delta$ (after time $T-(i+1)\Delta=(n-i-1)\Delta$ has passed) it becomes  

$$
(\Phi((i+1)\Delta,T)-\Phi(i\Delta,T))e^{-r(n-i-1)\Delta}\cdot e^{r(n-i-1)\Delta}=\Phi((i+1)\Delta,T)-\Phi(i\Delta,T)
$$  

Therefore the value at time $T=n\Delta$ of the portfolio is  

$$
\sum_{i=0}^{n-1}\Phi\d((i+1)\Delta,T)-\Phi\d(i\Delta,T)=\Phi\d(n\Delta,T)-\Phi\d(0,T)=S_{T}-\Phi\d(0,T).
$$  

Let $A$ be the above portfolio plus $\Phi(0,T)$ ZCBs maturing at $T$ (or $e^{-r T}$ cash). Then  

$$
V^{A}(T)=S_{T}.
$$  

Let $B$ be the portfolio consisting at time O of one long forward contract on the asset with maturity $T$ and delivery price equal to the forward price. $F(0,T)$ plus $F(0,T)$ ZCBs maturing at $T$ (or $e^{-r T}$ cash). Then also  

$$
\begin{array}{r}{V^{B}(T)=S_{T}.}\end{array}
$$  

By replication,  

$$
V^{A}(t)=V^{B}(t),
$$  

which means  

$$
\Phi(0,T)Z(0,T)=F(0,T)Z(0,T).
$$  

Divide by $Z(0,T)$ to conclude.  

Result 7.4.1. Suppose that at the present time $t$ we know what the interest rate between any two days will be. IThen  

$$
\Phi(t,T)=F(t,T)
$$  

for any given $t\leq T$  

Exercise 7.4.1. Prove Result 7.4.1. You may assume $t=0$ for simplicity. Use the notation $r_{i j}$ for the continuous interest rate between day $i$ and day $j$  

# 7.5 Futures Convexity Correction  

When interest rates are not constant, we may have $\Phi(t,T)\neq F(t,T)$  

Definition 7.5.1. The difference $\Phi(t,T)-F(t,T)$ is called the futures convexity correction.  

A detailed analysis of the futures convexity correction is beyond our scope. For details, see the textbook and references therein.  

# Chapter 8  

# Options  

# 8.1 European Option Definitions  

Fix an asset. Let $S_{t}$ be its price at time $t$  

Definition 8.1.1. A European call option on the asset with strike (or exercise price) $K$ and maturity (or exercise date) $T$ is the right---but not the obligation--to buy the asset for$K$ at time $T$ . Using the right to trade the asset is called exercising the option.  

In contrast, a long forward contract is the obligation to buy the asset for $K$ at time $T$  

We would only choose to pay $K$ for an asset worth. $S_{T}$ if $S_{T}\geq K$ . Thus the payout of a.   
European call option is s.  

$$
\left\{\begin{array}{r l}{S_{T}-K}&{\mathrm{if~}S_{T}\geq K}\ {0}&{\mathrm{if~}S_{T}\leq K}\end{array}\right.=\operatorname*{max}\left\{S_{T}-K,0\right\}=(S_{T}-K)^{+}.
$$  

We can also write the payout as. $g(S_{T})$ , where $g(x)=(x-K)^{+}=\operatorname*{max}\left\{x-K,0\right\}$ is called the payout function for the European call option. $\triangle$  

Example 8.1.1. Suppose the strike is $K=100$ for an call option with maturity. $T$ .If $S_{T}=110$ , then we receive value $S_{T}-K=110-100=10$ by exercising the option. On. the other hand, if $S_{T}=90\$ , then $S_{T}-K=-10$ , so we let the option expire and receive 0.  

Definition 8.1.2. A European put option is the right to sell the asset for $K$ at time $T$  

The payout of a European put option is  

$$
\left\{\begin{array}{l l}{{K-S_{T}}}&{{\mathrm{if}~S_{T}\leq K}}\ {{0}}&{{\mathrm{if}~S_{T}\geq K}}\end{array}\right.=\operatorname*{max}~\{K-S_{T},0\}=(K-S_{T})^{+}.
$$  

Remark 8.1.2. Notice that the payout of a put is not the negative of the payout of a call. $\triangle$  

Definition 8.1.3. Suppose we buy a European call option at time $t$ .The price we pay is denoted $C_{K}(t,T)$ . The party who sold us the call is said to be short on the call (or the writer of the call). Since we are holding the call, we are said to be long on the call (or the owner of the call). As the long counterparty, we have the right to buy the asset from the short counterparty for $K$ at $T$ . If this right is exercised, the short counterparty has the obligation to immediately sell the asset to us. Note that  

$$
\mathrm{short1call\neqlong1put.}
$$  

The payout at maturity when short a call is  

$$
-\operatorname*{max}\left\{S_{T}-K,0\right\}
$$  

which is the negative of the payout when long the call. However, don't forget that the short counterparty was paid $C_{K}(t,T)$ at $t$ by the long counterparty.  

Definition 8.1.4. A European straddle option is a European call plus a European put. It has payout  

$$
|S_{T}-K|=\left\{\begin{array}{l l}{S_{T}-K}&{\mathrm{if}S_{T}\geq K}\ {K-S_{T}}&{\mathrm{if}S_{T}\leq K.}\end{array}\right.
$$  

Remark 8.1.3. Note that an option is automatically exercised at maturity if the payout is positive.  

# 8.2 American Option Definitions  

While a European option allows exercise only at maturity $T$ , an American option allows exercise at any time $t\leq T$  

Definition 8.2.1. An American call option on an asset with strike (or exercise price) $K$ and maturity (or exercise date) $T$ is the right to buy the asset for. $K$ at any time $t\leq T$ For an American put option, replace "buy" with "sell.. $\triangle$  

There are many other less common types of options (such as Bermudan, Asian, and Lookback options). We won't study them in this course.  

Remark. Note that an option is automatically exercised at maturity if the payout is positive.  

# 8.3 More Definitions  

Definition 8.3.1. At time $t\leq T$ , a call option with strike $K$ is said to be:  

in-the-money (ITM) if $S_{t}>K$ (the call option will have positive payout if the asset price remains unchanged)  

out-of-the-money (OTM) if $S_{t}<K$ (the call option will be worthless if the asset price remains unchanged)  

at-the-money (ATM) if $S_{t}=K$  

in-the-money-forward (ITMF) if $F(t,T)>K$  

out-of-the-money-forward (OTMF) if $F(t,T)<K$  

at-the-money-forward (ATMF) if $F(t,T)=K$  

As usual, $F(t,T)$ is the forward price on the asset at $t$ for maturity $T$  

For a put option, we reverse these inequalities. For example, a put option is ITM if $K>$ St. $\triangle$  

Definition 8.3.2. The intrinsic value at $t$ of a call option is max. $\{S_{t}-K,0\}$ . The intrinsic. value at $t$ of a put option is max. $\{K-S_{t},0\}$ . Thus an option is in-the-money if its intrinsic value is positive..  

The intrinsic value is the payout if we had to immediately exercise the option or let it expire.  

The intrinsic value is not the value/price of the option.  

# 8.4 Option Prices  

Fix an asset. Let $S_{t}$ be its price at time $t$ . At this point, we make no assumptions about the nature of the asset.  

Definition 8.4.1. For $t\leq T$ ..  

$C_{K}(t,T)=$ price/value at time $t$ of a European call with strike $K$ and maturity $T$  

$P_{K}(t,T)=$ price/value at time $t$ of a European put with strike $K$ and maturity $T$  

$\tilde{C}_{K}(t,T)=$ price/value at time $t$ of an American call with strike $K$ and maturity $T$  

$\tilde{P}_{K}(t,T)=$ price/value at time $t$ of an American put with strike $K$ and maturity $T$  

Because an option must either be exercised or expired at maturity, we have  

# Result 8.4.1.  

$$
\tilde{C}_{K}(T,T)=C_{K}(T,T)=\operatorname*{max}\left\{S_{T}-K,0\right\}.
$$  

and  

$$
\tilde{P}_{K}(T,T)=P_{K}(T,T)=\operatorname*{max}\left\{K-S_{T},0\right\}.
$$  

In words, the next result says: Option prices are never negative, and American options are always worth at least as much as European options (with the same strike and maturity)..  

# Result 8.4.2.  

$$
\tilde{C}_{K}(t,T)\geq C_{K}(t,T)\geq0\quad\mathrm{and}\quad\tilde{P}_{K}(t,T)\geq P_{K}(t,T)\geq0.
$$  

Proof. It is intuitively clear that  

$$
\tilde{C}_{K}(t,T)\geq C_{K}(t,T)\quad\mathrm{and}\quad\tilde{P}_{K}(t,T)\geq P_{K}(t,T)
$$  

because an American option gives the same rights as a European option, and more. (As an exercise, prove these inequalities using the no-arbitrage principle or the monotonicity theorem.)  

In light of the assertion above, we just need to prove.  

$$
C_{K}(t,T)\geq0\quad{\mathrm{and}}\quad P_{K}(t,T)\geq0.
$$  

These inequalities should also be intuitively clear because an option can never lose money for its owner. For completeness, we prove the first inequality in detail. We apply the. monotonicity theorem to the portfolios.  

$$
\mathrm{A}=1~\mathrm{call}~\mathrm{and}~\mathrm{B}=\mathrm{empty}.
$$  

We see that  

$$
V^{A}(T)=C_{K}(T,T)=\operatorname*{max}\left\{S_{T}-K,0\right\}\geq0=V^{B}(T).
$$  

So by monotonicity,  

$$
V^{A}(t)\geq V^{B}(t)
$$  

that is,  

$$
C_{K}(t,T)\geq0.
$$  

The proof of the second inequality is similar.  

# 8.5 Put-Call Parity  

Fix an asset. Let $S_{t}$ be its price at $t$ . Again, we make no assumptions about the nature of the asset.  

Recall that the value of a forward is related to the forward price and delivery price by  

$$
V_{K}(t,T)=(F(t,T)-K)Z(t,T).
$$  

The next result relates the value of a forward to the price of a European call and the price of a European put.  

Result 8.5.1 (Put-Call Parity).  

$$
V_{K}(t,T)=C_{K}(t,T)-P_{K}(t,T)
$$  

Proof. Consider two portfolios.  

A: long 1 forward with delivery price $K$ and maturity $T$  

B: long 1 European call and short 1 European put (i.e., $+1$ call and $-1$ put), both with strike $K$ and maturity $T$  

We have  

$$
\begin{array}{r l}&{V^{A}(T)=S_{T}-K}\ &{V^{B}(T)=\left\{\begin{array}{l l}{(S_{T}-K)-0}&{\mathrm{if}S_{T}\geq K}\ {0-(K-S_{T})}&{\mathrm{if}S_{T}\leq K}\end{array}\right\}=S_{T}-K.}\end{array}
$$  

By the replication theorem,  

$$
V^{A}(t)=V^{B}(t)
$$  

which means  

$$
V_{K}(t,T)=C_{K}(t,T)-P_{K}(t,T).
$$  

In words, put-call parity says:  

$$
V_{K}(t,T)=C_{K}(t,T)-P_{K}(t,T)
$$  

long 1 forward equals long 1 call and short 1 put  

$$
C_{K}(t,T)=V_{K}(t,T)+P_{K}(t,T)
$$  

long 1 call equals long 1 forward and long 1 put  

$$
P_{K}(t,T)=-V_{K}(t,T)+C_{K}(t,T)
$$  

long 1 put equals short 1 forward and long 1 call  

Here "equals"' means "has the same value as."'  

Remember the options are European.  

There is a version of put-call parity for American options, but it involves inequalities rather.   
than an equality, and it depends on the income paid by the stock. We will not study it here.  

# Result 8.5.2.  

$$
C_{K}(t,T)=P_{K}(t,T)
$$  

if and only if $K=F(t,T)$ if and only if $K=F(t,T)$ if and only if the call and put are both at-the-money-forward (ATMF) at $t$  

Proof. Use put-call parity and the definition of forward price.  

Example 8.5.3. Suppose that a stock paying no income is trading at price 30 per share. European puts on the stock with strike 35 and exercise date in six months are trading at price 10. The six-month libor rate is. $4\%$ .What is the price of a European call with the. same strike and exercise date?  

Put-call parity says $V_{K}(t,T)=C_{K}(t,T)-P_{K}(t,T)$ , so  

$$
C_{K}(t,T)=V_{K}(t,T)+P_{K}(t,T).
$$  

Since the stock pays no income, we have  

$$
\begin{array}{r}{\mathbf{\Sigma}_{K}(t,T)=\left(F(t,T)-K\right)Z(t,T)=S_{t}-K Z(t,T)=S_{t}-K(1+(T-t)L_{t}[t,T])^{2}}\end{array}
$$  

Therefore  

$$
\begin{array}{r l}&{C_{K}(t,T)=S_{t}-K(1+(T-t)L_{t}[t,T])^{-1}+P_{K}(t,T)}\ &{\qquad=30-35(1+(0.5)(0.04))^{-1}+10=5.68627\dots.}\end{array}
$$  

# 8.6 European Call Prices for Assets Paying No Income  

Result 8.6.1. For an asset paying no income, the European call price satisfies  

$$
S_{t}-K Z(t,T)\le C_{K}(t,T)\le S_{t}.
$$  

Proof. We have  

$$
C_{K}(T,T)=\operatorname*{max}\left\{S_{T}-K,0\right\}\leq S_{T}
$$  

To prove the upper bound  

$$
C_{K}(t,T)\leq S_{t},
$$  

apply the monotonicity theorem to the following portfolios.  

A: 1 call.   
B: 1 stock.  

We have  

$$
S_{T}-K\le\operatorname*{max}{\left\{S_{T}-K,0\right\}}=C_{K}(T,T).
$$  

Applying the monotonicity theorem to the portfolios  

A: 1 stock, $-K$ ZCBs with maturity $T$   
B: 1 call   
proves the lower bound  

$$
S_{t}-K Z(t,T)\le C_{K}(t,T).
$$  

Result 8.6.2. For an asset paying no income, the price of a European call is at least the intrinsic value of the call: $C_{K}(t,T)\geq\operatorname*{max}\left\{S_{t}-K,0\right\},$  

Proof. We know $C_{K}(t,T)\geq0$ . So we just need to observe that  

$$
C_{K}(t,T)\geq S_{t}-K Z(t,T)\geq S_{t}-K
$$  

by Result 8.6.1.  

# 8.7 Equality of American and European Call Prices for Assets Paying No Income.  

Result 8.7.1. For an asset paying no income, the price of an American call and the price of a European call (with the same strike and maturity) are always equal, i.e.,  

$$
\tilde{C}_{K}(t,T)=C_{K}(t,T)
$$  

for all $t\leq T$  

Proof. We already know (Result 8.4.2) that $\tilde{C}_{K}(t,T)\geq C_{K}(t,T)$  

To prove $\tilde{C}_{K}(t,T)\leq C_{K}(t,T)$ , we assume $\tilde{C}_{K}(t,T)>C_{K}(t,T)$ and deduce a contradiction. Consider the portfolio $C$ with the following strategy.  

At time $t$ , the portfolio is empty. Write and sell 1 American call. The portfolio becomes short 1 American call and $\tilde{C}_{K}(t,T)$ cash. Spend $C_{K}(t,T)$ cash to go long 1 European call. The portfolio becomes short 1 American call, long 1 European call, and. $\epsilon=\tilde{C}_{K}^{\bar{}}(t,T)-$ $C_{K}(t,T)$ cash. By our assumption, $\epsilon>0$ . It is not necessary to invest the cash, we can just hold it.  

Now the portfolio acts depending on what the buyer of the American call does with it.  

Case 1. The American call expires without being exercised. Then  

$$
V^{C}(T)=\epsilon+C_{K}(T,T)\geq\epsilon>0.
$$  

Case 2. The American call is exercised at some time $T_{0}$ with $t\le T_{0}\le T$ . At $T_{0}$ , we are obligated to give away 1 asset worth $S_{T_{0}}$ and receive $K$ cash. To meet our obligation, we  

borrow $S_{T_{0}}$ cash to buy 1 asset and give it away. We also sell the European call. Then we have $\epsilon+K-S_{T_{0}}+C_{K}(T_{0},T)$ cash. Nothing else happens until $T$ . Thus, by Result 8.6.1. and the fact $Z(T_{0},T)\le1$ , we have  

$$
\begin{array}{r l}&{V^{C}(T)\geq\epsilon+K-S_{T_{0}}+C_{K}(T_{0},T)}\ &{\qquad\geq\epsilon+K-S_{T_{0}}+S_{T_{0}}-K Z(T_{0},T)}\ &{\qquad\geq\epsilon}\ &{\qquad>0}\end{array}
$$  

Combining both cases, we have. $V^{C}(T)>0$ with probability one and. $V^{C}(t)=0$ .This contradicts the no-arbitrage assumption.  

# 8.8 No Early Exercise for American Calls on Assets Paying No Income  

Result 8.8.1. For an asset paying no income, an American call will never be exercised before maturity if interest rates are positive..  

Proof. Suppose $t<T$ . By Result 8.4.2 and Result 8.6.1, we have  

$$
\tilde{C}_{K}(t,T)\geq C_{K}(t,T)\geq S_{t}-K Z(t,T).
$$  

If the interest rates for period $t$ to $T$ are positive, then. $Z(t,T)<1$ , and so  

$$
\tilde{C}_{K}(t,T)>S_{t}-K.
$$  

We would receive value $S_{t}-K$ if we exercise an American call at $t$ . But we would receive a strictly larger value $\tilde{C}_{K}(t,T)$ if we sell the call instead. So we would never choose to exercise at $t<T$  

# 8.9 Put Prices for Assets Paying No Income  

Result 8.9.1. For an asset paying no income,  

$$
K Z(t,T)-S_{t}\leq P_{K}(t,T)\leq K Z(t,T)
$$  

Result 8.9.2. For an asset paying no income,  

$$
K-S_{t}\le\tilde{P}_{K}(t,T)\le K.
$$  

Recall that (with the same strike and maturity) American options are always worth at least as much as European options, and that, for a stock paying no income, American and Euro-. pean calls have the same value.  

However, American puts may be worth strictly more than European puts. This is because, by exercising early, we receive the strike price $K$ early and can invest this amount. The next example illustrates this.  

Example 8.9.3. The current price of a stock paying no income is $S_{t}=10$ . The one-year annually compounded interest rate is $r=16\%$  

Consider an American put expiring in one year with strike $K=80$ . Exercising now, we get  

$$
K-S_{t}=80-10=70,
$$  

which can be invested to become  

$$
70(1+0.16)=81.20
$$  

after one year.  

Consider a European put expiring in one year with strike $K=80$ . The payout at $T$ is at most  

$$
\operatorname*{max}{\{80-S_{T},0\}}\leq80<81.20
$$  

after one year.  

Since we can potentially make more money with the American put, its current price will be strictly larger than the price of a European put.  

Proof of Result 8.9.1. As with the European call bounds of Result 8.6.1, we can prove (8.9.1) directly by replication. Instead, to illustrate another method, we prove (8.9.1) using. European call bounds and put-call parity..  

We prove the upper bound. $P_{K}(t,T)\leq K Z(t,T)$ in detail. According to Result 8.6.1,  

$$
C_{K}(t,T)\leq S_{t}.
$$  

By put-call parity,  

$$
C_{K}(t,T)=V_{K}(t,T)+P_{K}(t,T)
$$  

Hence  

$$
P_{K}(t,T)\leq S_{t}-V_{K}(t,T).
$$  

But, for an asset paying no income,  

$$
V_{K}(t,T)=(F(t,T)-K)Z(t,T)=S_{t}-K Z(t,T).
$$  

Therefore  

$$
P_{K}(t,T)\leq K Z(t,T).
$$  

To prove the lower bound $K Z(t,T)-S_{t}\leq P_{K}(t,T)$ , start with  

$$
0\le C_{K}(t,T)
$$  

and argue the same way.  

Proof of Result 8.9.2. For the lower bound: If we exercise the American put at $t$ , we receive value $K-S_{t}$ , so the price $\Tilde{P}_{K}(t,T)$ must be at least this much.  

To prove the upper bound $\tilde{P}_{K}(t,T)\le K$ , we assume $\tilde{P}_{K}(t,T)>K$ and deduce a contradiction. Consider portfolio $C$ with the following strategy.  

At time $t$ , the portfolio is empty. Write and sell 1 American put. The portfolio becomes short 1 American put and $\tilde{P}_{K}\dot{(t,T)}$ cash. It is not necessary to invest the cash, we can just hold it.  

Now the portfolio acts depending what the long party of the American put does.  

Case 1. The American put expires without being exercised. Then  

$$
V^{C}(T)=\tilde{P}_{K}(t,T)\geq\tilde{P}_{K}(t,T)-K>0.
$$  

Case 2. The American put is exercised at some time. At that moment, we must pay $K$ to buy 1 asset from the holder of the put. The portfolio is then $\tilde{P}_{K}(t,T)-K$ non-invested cash and 1 asset. Nothing else happens until $T$ , SO  

$$
V^{C}(T)=\tilde{P}_{K}(t,T)-K+S_{T}>0.
$$  

Combining both cases, we have $V^{C}(T)>0$ with probability one and $V^{C}(t)=0$ . This contradicts the no-arbitrage assumption.  

# 8.10 Call and Put Prices for Stocks Paying Known Dividend Yield  

Result 8.10.1. For a stock paying dividends at continuous yield $q$ with automatic reinvestment,  

$$
\begin{array}{c}{{S_{t}e^{-q(T-t)}-K Z(t,T)\leq C_{K}(t,T)\leq S_{t}e^{-q(T-t)}}}\ {{K Z(t,T)-S_{t}e^{-q(T-t)}\leq P_{K}(t,T)\leq K Z(t,T)}}\ {{S_{t}-K\leq\tilde{C}_{K}(t,T)\leq S_{t}}}\ {{K-S_{t}\leq\tilde{P}_{K}(t,T)\leq K}}\end{array}
$$  

Recall that (with the same strike and maturity) American options are always worth at least as much as European options, and that, for a stock paying no income, American and European calls have the same value.  

However, for a stock paying dividends, an American call may be worth more than a European call. This is because, by exercising early, we may receive dividends from the stock which we would not have received otherwise. The next example illustrates this.  

Example 8.10.2. Consider a stock paying dividends at continuous yield $q=5\%$ with automatic reinvestment. The current price of the stock is $S_{t}=10$ . The one-year continuously compounded interest rate is $r=5\%$  

Consider an American call expiring in one year with strike $K=20$ . Exercising now, we get the stock and a debt of $K=20$ . If the stock price in one year is $S_{T}=30$ , then we will have gained  

$$
S_{T}e^{q(T-t)}-K e^{r(T-t)}=30e^{0.05}-20e^{0.05}\approx16.49
$$  

after one year.  

A European call expiring in one year with strike $K=20$ would payout only.  

$$
S_{T}-K=30-20=10
$$  

after one year.  

Exercise 8.10.1. Prove Result 8.10.1.  

# 8.11 Call and Put Spreads  

In this section, we consider only European options.  

Fix an asset. Let $S_{t}$ be its price at $t$  

Definition 8.11.1. Let $K_{1}<K_{2}$ . A $(K_{1},K_{2})$ call spread is a portfolio consisting of long 1 call option with strike $K_{1}$ and short 1 call option with strike $K_{2}$ , both with maturity $T$ $\triangle$  

Result 8.11.1. For a $(K_{1},K_{2})$ call spread:  

The payout at maturity $T$ is  

$$
\left\{\begin{array}{l l}{0}&{\mathrm{if~}S_{T}\leq K_{1}\mathrm{~(neither~exercised)}}\ {S_{T}-K_{1}}&{\mathrm{if~}K_{1}\leq S_{T}\leq K_{2}\mathrm{~(only~}K_{1}\mathrm{-call~exercised)}}\ {K_{2}-K_{1}}&{\mathrm{if~}S_{T}\geq K_{2}\mathrm{~(both~exercised)}}\end{array}\right.
$$  

The value at $t\leq T$ is  

$$
C_{K_{1}}(t,T)-C_{K_{2}}(t,T).
$$  

The value at $t\leq T$ satisfies  

$$
0\leq C_{K_{1}}(t,T)-C_{K_{2}}(t,T)\leq(K_{2}-K_{1})Z(t,T).
$$  

Proof. Only the last point needs justification.  

The payout at $T$ is $\geq0$ , so (by the monotonicity theorem) the value at $t$ is also $\geq0$  

The payout at $T$ is always $\le K_{2}-K_{1}$ , which is the value at $T$ of a portfolio of $K_{2}-K_{1}$ ZCBs with maturity $T$ . So (by the monotonicity theorem) the value of the spread at $t$ is $\leq(K_{2}-K_{1})Z(t,T)$  

![](68d07bd089c236bd7192caafab760d336177fb564064bc01f837646bf945a78c.jpg)  
Figure 8.1: Payout of (80, 110) call spread  

Definition 8.11.2. Let $K_{1}<K_{2}$ . A $(K_{2},K_{1})$ put spread is a portfolio consisting of short 1 put option with strike $K_{1}$ and long 1 put option with strike $K_{2}$ , both with maturity $T$ $\triangle$  

Result 8.11.2. For a $(K_{2},K_{1})$ put spread:  

The payout at maturity $T$ is  

$$
\left\{\begin{array}{l l}{K_{2}-K_{1}}&{\mathrm{if}S_{T}\leq K_{1}(\mathrm{bothex}}\ {K_{2}-S_{T}}&{\mathrm{if}K_{1}\leq S_{T}\leq K_{2}(\mathrm{o}}\ {0}&{\mathrm{if}S_{T}\geq K_{2}(\mathrm{neither}}\end{array}\right.
$$  

The value at $t\leq T$ is  

$$
P_{K_{2}}(t,T)-P_{K_{1}}(t,T).
$$  

The value at $t\leq T$ satisfies  

$$
0\le P_{K_{2}}(t,T)-P_{K_{1}}(t,T)\le(K_{2}-K_{1})Z(t,T)
$$  

Remark 8.11.3. The previous two results imply If $K_{1}\leq K_{2}$ , then  

$$
C_{K_{1}}(t,T)\geq C_{K_{2}}(t,T)\quad\mathrm{and}\quad P_{K_{1}}(t,T)\leq P_{K_{2}}(t,T)
$$  

In other words, $C_{K}(t,T)$ is a decreasing function of the strike $K$ , and $P_{K}(t,T)$ is an increasing function of the strike $K$ $\triangle$  

# 8.12 Butterflies and Convexity of Option Price  

Fix an asset. Let $S_{t}$ be its price at $t$  

Definition 8.12.1. Let $K_{1}<K^{*}<K_{2}$ . Then there is a unique $\lambda\in(0,1)$ such that  

$$
K^{*}=\lambda K_{1}+(1-\lambda)K_{2}.
$$  

The portfolio consisting of  

$+2\lambda$ calls with strike $K_{1}$ $-2$ calls with strike $K^{*}$ $+2(1-\lambda)$ calls with strike $K_{2}$  

all with the same maturity, is called a $(K_{1},K^{*},K_{2})$ call butterfly.   
If $\lambda\neq1/2$ , it is called an asymmetric call butterfly.   
If $\lambda=1/2$ , it is called an symmetric call butterfly.  

Since symmetric call butterflies are vastly more common in practice, if the shorter term call butterfly is used without further qualification, we will always assume it means symmetric call butterfly.  

For a symmetric call butterfly, the portfolio is  

$+1$ call with strike $K_{1}$  

$-2$ calls with strike $\begin{array}{r}{K^{*}=\frac{1}{2}(K_{1}+K_{2})}\end{array}$ $+1$ call with strike $K_{2}$  

Result 8.12.1. For a $(K_{1},K^{*},K_{2})$ symmetric call butterfly, at maturity $T$ the payout is  

$$
\left\{\begin{array}{l l}{0}&{\mathrm{if~}S_{T}\leq K_{1}}\ {S_{T}-K_{1}}&{\mathrm{if~}K_{1}\leq S_{T}\leq K^{*}}\ {K_{2}-S_{T}}&{\mathrm{if~}K^{*}\leq S_{T}\leq K_{2}}\ {0}&{\mathrm{if~}S_{T}\geq K_{2}}\end{array}\right.
$$  

![](58fc8e1635bb615a03aa7f9bc7bbf583fe9301f9a64754d351bb553c6ee159c0.jpg)  
Figure 8.2: Payout of a (90, 105, 120) call butterfly.  

Result 8.12.1 is a special case of  

Result 8.12.2. For a $(K_{1},K^{*},K_{2})$ (asymmetric or symmetric) call butterfly:  

The payout at maturity $T$ is  

$$
\left\{\begin{array}{l l}{0}&{\mathrm{if~}S_{T}\leq K_{1}}\ {2\lambda(S_{T}-K_{1})}&{\mathrm{if~}K_{1}\leq S_{T}\leq K^{*}}\ {2(1-\lambda)(K_{2}-S_{T})}&{\mathrm{if~}K^{*}\leq S_{T}\leq K_{2}}\ {0}&{\mathrm{if~}S_{T}\geq K_{2}}\end{array}\right.
$$  

The value at $t\leq T$ is  

$$
2\lambda C_{K_{1}}(t,T)+2(1-\lambda)C_{K_{2}}(t,T)-2C_{K^{*}}(t,T).
$$  

The payout at $T$ is $\geq0$ , so (by the monotonicity theorem) the value at $t\leq T$ satisfies  

$$
0\leq2\lambda C_{K_{1}}(t,T)+2(1-\lambda)C_{K_{2}}(t,T)-2C_{K^{*}}(t,T)
$$  

Proof. Only the first point needs justification. the cases $S_{T}\geq K_{1}$ and $K_{1}\leq S_{T}\leq K^{*}$ are clear. If $K^{*}\leq S_{T}\leq K_{2}$ , the payout is  

$$
2\lambda(S_{T}-K_{1})-2(S_{T}-K^{*})=2\lambda(S_{T}-K_{1})-2(S_{T}-\lambda K_{1}-(1-\lambda)K_{2})=2(1-\lambda)(K_{2}-K_{1})
$$  

If $S_{T}\geq K_{2}$ , the payout is  

$$
2\lambda(S_{T}-K_{1})-2(S_{T}-K^{*})+2(1-\lambda)(S_{T}-K_{1})=0
$$  

Remark 8.12.3. (8.12.1) can be rearranged to  

$$
C_{K^{*}}(t,T)\leq\lambda C_{K_{1}}(t,T)+(1-\lambda)C_{K_{2}}(t,T),
$$  

which means that. $C_{K}(t,T)$ is convex (concave up) function of $K$  

Exercise 8.12.1. Draw the payout diagram for an asymmetric call butterfly with strikes (70, 80, 110).  

Exercise 8.12.2. Consider an arbitrary $(K_{1},K^{*},K_{2})$ asymmetric or symmetric call butterfly. (a) Use put-call parity to express it as a portfolio of only puts.  

(b) Show that the value at $t\leq T$ is  

$$
2\lambda P_{K_{1}}(t,T)+2(1-\lambda)P_{K_{2}}(t,T)-2P_{K^{*}}(t,T).
$$  

(c) Show that $P_{K}(t,T)$ is a convex (concave up) function of $K$ by showing that.  

$$
P_{K^{*}}(t,T)\leq\lambda P_{K_{1}}(t,T)+(1-\lambda)P_{K_{2}}(t,T).
$$  

# 8.13 Digital Options  

Fix an asset. Let $S_{t}$ be its price at $t$  

Definition 8.13.1. A digital call option with strike $K$ , payout $\beta$ , and maturity $T$ has payout at $T$  

$$
\left\{\begin{array}{l l}{\beta}&{\mathrm{if}S_{T}\geq K}\ {0}&{\mathrm{if}S_{T}<K}\end{array}\right.
$$  

A digital put option with strike $K$ , payout $\beta$ , and maturity $T$ has payout at $T$  

$$
\left\{\begin{array}{l l}{\beta}&{\mathrm{if~}S_{T}\leq K}\ {0}&{\mathrm{if~}S_{T}>K}\end{array}\right.
$$  

Digital options are also called binary options or all-or-nothing options.  

![](1c82e13cf395e78bf74f877c222120b475577b2e86a362fdfdfcd31e18dbe407.jpg)  
Figure 8.3: Payout of a $K$ -strike 1-payout digital call  

Result 8.13.1. The price/value at time $t\leq T$ of a digital call option with strike. $K$ , payout 1, and maturity. $T$ is  

$$
-\frac{d}{d K}C_{K}(t,T),
$$  

provided $C_{K}(t,T)$ is differentiable in $K$  

The proof is Exercise 8.13.1  

Exercise 8.13.1. Fix an asset. Let $S_{t}$ be its price at $t\leq T$ . In this exercise, you will prove. Result 8.13.1 (and a bit more). Parts $(\mathrm{g})$ and (i) may be difficult if you haven't studied $\epsilon{-}\delta$ analysis. For each positive integer $n$ , define the portfolio  

Let $B$ be the portfolio consisting of a digital call option with strike $K$ , payout 1, and maturity $T$ . (a) Find $V^{A(n)}(T)$ and $V^{B}(T)$ . (b) On the same axes, draw payout diagrams for $B$ and $A(n)$ when $K=10$ and $n=1,5,10$  

(c) Show that $\operatorname*{lim}_{n\rightarrow\infty}V^{A(n)}(t)=-\frac{d}{d K}C_{K}(t,T)$ if $C_{K}(t,T)$ is differentiable in $K$ .Hint:  

$V^{A(n)}(t)=\frac{C_{K-1/n}(t,T)-C_{K}(t,T)}{1/n}.$   
(d) Find $\begin{array}{r}{\operatorname*{lim}_{n\to\infty}V^{A(n)}(T)}\end{array}$ when $S_{T}\geq K$   
(e) Find $\begin{array}{r}{\operatorname*{lim}_{n\to\infty}V^{A(n)}(T)}\end{array}$ when $S_{T}<K$ . Justify your answer.   
(f) How is $\begin{array}{r}{\operatorname*{lim}_{n\to\infty}V^{A(n)}(T)}\end{array}$ related to $V^{B}({\cal T})$   
(g) Use a no-arbitrage argument to prove that $\begin{array}{r}{\operatorname*{lim}_{n\rightarrow\infty}V^{A(n)}(t)=V^{B}(t).}\end{array}$   
(h) Conclude using parts (c) and $(\mathbf{g})$   
(i) Use Remark 8.12.3 to prove that the limit $\operatorname*{lim}_{n\to\infty}V^{A(n)}(t)$ always exists.   
(j) Without knowing whether $C_{K}(t,T)$ is differentiable in $K$ , what formula can you write down for the price/value at time $t\leq T$ of a digital call option with strike $K$ , payout 1, and. maturity $T^{\bullet}$ C.  

Exercise 8.13.2. (a) What is the price at time $t$ of a digital put option with strike $K$ , payout 1, and maturity $T\mathrm{?}$ (You may assume $P_{K}(t,T)$ is differentiable in $K$ .) (b) Prove it.  

# Chapter 9  

# Probability Theory: Conditioning and Independence  

In this chapter, we introduce the concepts of conditioning and independence in probability theory, which we will need later. As before, the purpose is not to be completely rigorous, but to build the correct intuition.  

# 9.1 Conditional Probability  

Fix a sample space $\Omega$ and probability measure $P$  

Definition 9.1.1. Let. $A$ and $B$ be events (i.e., subsets of $\Omega$ ). The conditional probability of $A$ given $B$ is  

$$
P(A|B)={\frac{P(A{\mathrm{~and~}}B)}{P(B)}}.
$$  

It is undefined if $P(B)=0$  

Intuition. $P(A|B)$ is the probability that event $A$ occurs assuming event. $B$ occurs.  

Out of the probability assigned to the outcomes in $B$ $3,P(A|B)$ is the fraction assigned to those outcomes that are in both $A$ and $B$  

![](1681943423c4cb846dde034a9bc7a81d53e0ba80e77d95ec2c44cebeafada113.jpg)  

Example 9.1.1. Experiment: Flip a fair coin three times.   
Sample space: $\Omega=\{\mathrm{HHH},\mathrm{HHT},\mathrm{HTH},\mathrm{THH},\mathrm{HTT},\mathrm{THT},\mathrm{TTH},\mathrm{TTT}\}$ Probability Measure:. $\begin{array}{r}{P(\{\omega\})=\frac{1}{8}}\end{array}$ for all $\omega\in\Omega$   
$X=$ number of heads   
$Y=1$ if 1st flip heads, O otherwise   
$Z=1$ if 2nd flip heads, 0 otherwise  

Find $P(X=2)$ $P(X=2|Y=1)$ , and $P(X=2|Y=1,Z=0)$ Notation: $\{Y=1,Z=0\}=\{Y=1$ and $Z=0\}$  

$$
P(X=2)=P(\{{\mathrm{HHT}},{\mathrm{HTH}},{\mathrm{THH}}\})={\frac{3}{8}}
$$  

$$
P(X=2|Y=1)=\frac{P(X=2,Y=1)}{P(Y=1)}.
$$  

$$
\begin{array}{l}{P(X=2|Y=1,Z=0)=\cfrac{P(X=2,Y=1,Z=0)}{P(Y=1,Z=0)}}\ {\{Y=1,Z=0\}=\{H T H,H T T\}\mathrm{~and~}\{X=2,Y=1,Z=0\}=\{H H T\}}\ {P(X=2|Y=1,Z=0)=\cfrac{P(X=2,Y=1,Z=0)}{P(Y=1,Z=0)}=\cfrac{1/8}{2/8}=\cfrac{1}{2}.}\end{array}
$$  

# 9.2 Independence  

Fix a sample space $\Omega$ and probability measure $P$  

Definition 9.2.1. Events $A$ and $B$ are called independent if  

$$
P(A{\mathrm{~and~}}B)=P(A)P(B)
$$  

If $P(B)>0$ , we can use the definition $P(A|B)=P(A{\mathrm{~and~}}B)/P(B)$ to rewrite (9.2.1) as  

$$
P(A|B)=P(A),
$$  

so, intuitively, independence of $A$ and $B$ means knowledge of. $B$ does not affect the probability of. $A$ . We get a similar statement with $P(B|A)$ if $P(A)>0$  

Definition 9.2.2. Discrete random variables $X$ and $Y$ are independent if  

$$
P(X=x,Y=y)=P(X=x)P(Y=y)\quad{\mathrm{~for~all~}}x,y
$$  

Remember: The "" here means "and"  

Intuitively, $X$ and $Y$ are independent if knowing one of them gives no information about the other.  

Example 9.2.1. Roll two fair six-sided dice. $X=\operatorname{sum}$ of the dice, $Y=$ number on first die, $Z=$ number on second die.  

$X$ and $Y$ are not independent because (for example)  

$$
P(X=2|Y=6)=0\neq{\frac{1}{36}}=P(X=2).
$$  

$Y$ and $Z$ are independent. Indeed, we can check that (exercise)  

$$
P(Y=y|Z=z)=P(Y=y)\quad{\mathrm{~for~all~}}y,z
$$  

but this should be intuitively clear.  

Definition 9.2.3. Discrete random variables $X_{1},\ldots,X_{n}$ are independent if  

$$
P(X_{1}=x_{1},\ldots,X_{n}=x_{n})=P(X_{1}=x_{1})\cdot\cdot\cdot\cdot P(X_{n}=x_{n})\quad{\mathrm{for~all~}}x_{1},\ldots,x_{n}.
$$  

An infinite sequence of discrete random variables $X_{1},X_{2},\dots$ is independent if any finite sub-collection is independent. $\triangle$  

Theorem 9.2.2.(i) If $X_{1},X_{2},\dots$ are independent, then $X_{1},X_{2},X_{3},X_{5},X_{8},X_{13}$ are independent. (ii) If $X_{1},X_{2},\dots$ are independent, then $g(X_{1}),g(X_{2}),\dots$ are independent for any function $g:\mathbb{R}\rightarrow\mathbb{R}$  

# 9.3 Conditional Expectation  

Fix a sample space $\Omega$ and probability measure $P$  

Recall that the expectation of a discrete random variable $X$ is  

$$
\operatorname{\mathbb{E}}(X)=\sum_{k\in R(X)}k P(X=k),
$$  

where $R(X)$ is the range of $X$  

Definition 9.3.1. Let $X$ and $Y$ be discrete random variables. The conditional expectation of $X$ given $Y=y$ is  

$$
\mathbb{E}(X|Y=y)=\sum_{k\in R(X)}k P(X=k|Y=y).
$$  

Interpretation. $\mathbb{E}(X|Y=y)$ is the expectation of $X$ assuming that $Y=y$ occurs.  

Example 9.3.1. Roll two fair six-sided dice. $X=$ sum of the dice, $Y=$ number on first die, $Z=$ number on second die.  

$$
\operatorname{\mathbb{E}}(X)=\operatorname{\mathbb{E}}(Y+Z)=\operatorname{\mathbb{E}}(Y)+\operatorname{\mathbb{E}}(Z)=3.5+3.5=7
$$  

$$
\operatorname{\mathbb{E}}(X|Y=6)=\operatorname{\mathbb{E}}(Y+Z|Y=6)=\operatorname{\mathbb{E}}(Y|Y=6)+\operatorname{\mathbb{E}}(Z|Y=6)=6+3.5=9.5.
$$  

Theorem 9.3.2 (Properties of Conditional Expectation $\mathbb{E}(X|Y=y),$ . Let $X$ and $Y$ be discrete random variables, let $a,b,c,y$ be real numbers (constants), and let $g:\mathbb{R}\rightarrow\mathbb{R}$ be any function. Then  

(i) If $X$ and $Y$ are independent, then $\mathbb{E}(X|Y=y)=\mathbb{E}(X)$   
(ii) When conditioning on $Y=y$ , replace $Y$ by $y$ $\mathbb{E}(X g(Y)|Y)=\mathbb{E}(X g(y)|Y)=$ $g(y)\mathbb{E}(X|Y)$   
(iii) Linearity:. $\mathbb{E}(a X+b Y+c|Y=y)=\mathbb{E}(a X+b y+c|Y=y)=a\mathbb{E}(X|Y)+b y+c.$  

Example 9.3.3. Roll two fair six-sided dice. $X=$ sum of the dice,. $Y=$ number on first die,.   
$Z=$ number on second die..  

$$
\mathbb{E}(Z|X=3)=\sum_{k\in R(Z)}k P(Z=k|X=3)
$$  

For $\begin{array}{r}{\mathopen{}\mathclose\bgroup\left\langle\sum3,P\mathopen{}\mathclose\bgroup\left(Z=k\mathopen{}\mathclose\bgroup\left|X=3\aftergroup\egroup\right.\right)=0.}\end{array}$  

$$
P(Z=1|X=3)={\frac{P(Z=1\mathrm{and}X=3)}{P(X=3)}}={\frac{P(\{(2,1)\})}{P(\{(1,2),(2,1)\})}}={\frac{1/36}{2/36}}={\frac{1}{2}}.
$$  

Similarly, $\textstyle P(Z=2|X=3)={\frac{1}{2}}$ . Therefore  

$$
\mathbb{E}(Z|X=3)=(1)\left(\frac{1}{2}\right)+(2)\left(\frac{1}{2}\right)=1.5
$$  

Intuitively, this make sense. If $X=3$ , then $Z$ must be 1 or 2, with equal probability. $\triangle$  

Theorem 9.3.4 (Change of Variable or Law of the Unconscious Statistician). Let $X$ and and $Y$ be a discrete random variable and let $g:\mathbb{R}\rightarrow\mathbb{R}$ be a function. The conditional expectation of the random variable $g(X)$ given $Y=y$ is  

$$
\mathbb{E}(g(X)|Y=y)=\sum_{k\in R(g(X))}k P(g(X)=k|Y=y)=\sum_{k\in R(X)}g(k)P(X=k|Y=y)
$$  

Definition 9.3.2. Let $X$ and $Y$ be discrete random variables, and let $R(Y)=\left\{y_{1},y_{2},y_{3},...\right\}$ The conditional expectation of $X$ given $Y$ is  

$$
E(X|Y)={\left\{\begin{array}{l l}{E(X|Y=y_{1})}&{{\mathrm{if~}}Y=y_{1}}\ {E(X|Y=y_{2})}&{{\mathrm{if~}}Y=y_{2}}\ {\vdots}&{\vdots}\ {E(X|Y=y_{i})}&{{\mathrm{if~}}Y=y_{i}}\ {\vdots}&{\vdots}\end{array}\right.}
$$  

Notice that $E(X|Y)$ is a random variable. Remember that a random variable is a function $Z:\Omega\rightarrow\mathbb{R}$ . For each $\omega\in\Omega,Z(\omega)$ is a real number. Indeed, we can define. $E(X|Y)$ more concisely as  

$$
E(X|Y)(\omega)=E(X|Y=Y(\omega))\quad{\mathrm{~for~all~}}\omega\in\Omega.
$$  

Example 9.3.5. Roll two fair six-sided dice. $X=\operatorname{sum}$ of the dice, $Y=$ number on first die, $Z=$ number on second die.  

$$
|Y\rangle=\mathbb{E}(Y+Z|Y)=\mathbb{E}(Y|Y)+\mathbb{E}(Z|Y)=Y+\mathbb{E}(Z|Y)=Y+\mathbb{E}(Z)=Y+3.5
$$  

Theorem 9.3.6 (Properties of Conditional Expectation $\mathbb{E}(X|Y))$ . Let $X$ and $Y$ be discrete random variables, let $a,b,c$ be real numbers (constants), and let. $g:\mathbb{R}\rightarrow\mathbb{R}$ be any function. Then  

(i) If $X$ and $Y$ are independent, then $\mathbb{E}(X|Y)=\mathbb{E}(X)$   
(ii) When conditioning on $Y$ , treat $Y$ as constant: $\mathbb{E}(X g(Y)|Y)=g(Y)\mathbb{E}(X|Y)$   
(iii) Linearity: $\mathbb{E}(a X+b Y+c|Y)=a\mathbb{E}(X|Y)+b Y+c$  

Example 9.3.7. Roll two fair six-sided dice. $X=\operatorname{sum}$ of the dice,. $Y=$ number on first die,.   
$Z=$ number on second die.  

$$
E(Z|X)={\left\{\begin{array}{l l}{E(Z|X=2)}&{{\mathrm{if~}}X=2}\ {E(Z|X=3)}&{{\mathrm{if~}}X=3}\ {\vdots}&{\vdots}\ {E(Z|X=12)}&{{\mathrm{if~}}X=12}\ {\vdots}&{\vdots}\end{array}\right.}
$$  

In a previous example, we found $E(Z|X=3)=1.5$ We leave it as a challenge for the reader to compute. $E(Z|X=k)$ for the other values of $k$ , and thus find. $E(Z|X)(\omega)$ for each $\omega\in\Omega=\{(1,1),(1,2),\dotsc,(6,6)\}$ $\triangle$  

# Chapter 10  

# The Binomial Tree  

Throughout this chapter, we consider a stock paying no income. We introduce a simple model for the stock price at discrete times called the binomial tree model. In this model, the exact prices of options and other derivatives can be determined..  

# 10.1 One-Step Binomial Tree  

We start with the one-step binomial tree model for a stock paying no income.  

In this model, there are only two times:. $T=0$ and $T=1$ .At time $T=0$ , the stock price $S_{0}$ is known. At time $T=1$ , there are two possible states of the world: either. $S_{1}=(1+u)S_{0}$ (state A) with probability $p$ or $S_{1}=(1+d)S_{0}$ (state B) with probability $1-p$ . The parameters $u$ and $d$ are the possible percentage changes in the stock price. They satisfy $0<1+d<1+u$ . The model assumes there is a constant annually compounded interest rate, denoted by $r$  

An example one-step binomial tree is given in Figure 10.1.  

![](6a31e66ef88795d9ee503c44fe72d3f195e0b363e4712400ae2cb215e9cef512.jpg)  
Figure 10.1: One-Step Binomial Tree with $r=0.1$ $d=-0.1$ , and $u=0.2$  

The outcome $S_{1}=(1+u)S_{0}$ is called an up movement. The outcome $S_{1}=(1+d)S_{0}$ is called a down movement..  

To put things in terms of a sample space $\Omega$ and probability measure $P$ , we have  

$$
\begin{array}{c}{\Omega=\left\{\omega_{A},\omega_{B}\right\},}\ {P(\{\omega_{A}\})=P(S_{1}=(1+u)S_{0})=p,}\ {P(\{\omega_{B}\})=P(S_{1}=(1+d)S_{0})=1-p.}\end{array}
$$  

# 10.2 Replication on the One-Step Binomial Tree  

Up to this point in the course, our standard strategy for pricing derivatives has been replication. The outline of the replication pricing strategy is as follows. We start with a derivative whose price at time $t$ we wish to determine. We put it in a portfolio $A$ . We then construct a portfolio $B$ such that $V^{A}(T)=V^{B}(T)$ with probability one at some future time $T>t$ and $V^{B}(t)$ has a simple well-understood formula. Finally, we use the replication principle to conclude that the price of the derivative at time $t$ is  

$$
D_{t}=V^{A}(t)=V^{B}(t)=\mathrm{simple~well{\mathrm{-}}u n d e r s t o o d~f o r m u l a.}
$$  

Note that portfolio. $B$ here is said to replicate the derivative.  

We used the replication pricing strategy successfully when the derivative was a forward on various types of underlying assets and when the derivative was a forward rate agreement or swap on future interest rates.  

For other types of derivatives, like options, it is not always possible in general to find a suitable replicating portfolio $B$  

However, in the one-step binomial tree model, every derivative contract can be replicated by a portfolio of stocks and ZCBs, so we can use the replication pricing strategy. We now. discuss the details.  

Consider an arbitrary derivative contract on a stock in a one-step binomial tree model. Since the only times are $T=0$ and $T=1$ , the derivative is completely described by its payout at $T=1$ is  

$$
g(S_{1})=\left\{\begin{array}{c l}{{\alpha}}&{{\mathrm{if}~S_{1}=S_{0}(1+u)~(\mathrm{state}~\mathrm{A})}}\ {{\beta}}&{{\mathrm{if}~S_{1}=S_{0}(1+d)~(\mathrm{state}~\mathrm{B})}}\end{array}\right.
$$  

where $\alpha,\beta\in\mathbb{R}$ are constants.  

Result 10.2.1. In the one-step binomial tree model, every derivative can be replicated by a portfolio of stocks and ZCBs. In particular, the derivative with payout at $T=1$ given by (10.2.1) is replicated by the portfolio consisting of  

$$
{\frac{\alpha-\beta}{S_{0}(u-d)}}\mathrm{stocks},\quad\alpha-{\frac{\alpha-\beta}{u-d}}(1+u)\mathrm{ZCBs},
$$  

and the price of the derivative at time $T=0$ is  

$$
D_{0}=\frac{\alpha-\beta}{u-d}+\left(\alpha-\frac{\alpha-\beta}{u-d}(1+u)\right)Z(0,1).
$$  

Proof. Let $A$ be the portfolio consisting of only the derivative. Let $B$ be the portfolio of. $x$ stocks and $y$ ZCBs maturing at $T=1$ . Now  

$g(S_{1})=x S_{1}+y$ with probability one (i.e., in all states of the world)  

if and only if  

$$
\left\{\begin{array}{l}{\alpha=x S_{0}(1+u)+y}\ {\beta=x S_{0}(1+d)+y}\end{array}\right.
$$  

Solving for $x$ and $y$ gives  

$$
\begin{array}{l}{\displaystyle x=\frac{\alpha-\beta}{S_{0}(u-d)}}\ {\displaystyle y=\alpha-\frac{\alpha-\beta}{u-d}(1+u)}\end{array}
$$  

Thus the portfolio $B$ of $x$ stocks and $y$ ZCBs (with $x,y$ as above) replicates the derivative at $T=1$ . By the replication theorem, the price of the derivative at $T=0$ is  

$$
D_{0}=x S_{0}+y Z(0,1)=\frac{\alpha-\beta}{u-d}+\left(\alpha-\frac{\alpha-\beta}{u-d}(1+u)\right)Z(0,1).
$$  

# 10.3 Risk-Neutral Pricing: Introduction  

In this section, we introduce an alternative to the replication pricing strategy, called riskneutral pricing.  

Risk-neutral pricing is the idea that the best guess for the future price of an asset, after discounting, should be the current price. Thus the price at current time $t$ of any portfolio $A$ should be  

$$
V^{A}(t)=Z(t,T)\mathbb{E}(V^{A}(T)).
$$  

Unfortunately, this formula is not compatible with the no-arbitrage principle, as Example 10.3.1 below illustrates. The correct formula takes the form.  

$$
V^{A}(t)=Z(t,T)\mathbb{E}^{*}(V^{A}(T)).
$$  

What's the difference? The expectation in (10.3.1) is computed with respect to the realworld probability measure $P$ , which is determined from observation and data. The expectation in (10.3.2) is computed with respect to a different probability measure $P^{*}$ , which we discuss more later.  

Here is an example that illustrates (10.3.1) can lead to violations of the no-arbitrage principle.  

Example 10.3.1. Consider a stock paying no income. The stock price at current time 0 is $S_{0}=100$ . At time $T=1$ , the stock price is  

$$
S_{1}=\left\{\begin{array}{l l}{120,}&{\mathrm{with~probability~0.75,}}\ {90=0,}&{\mathrm{with~probability~0.25~}}\end{array}\right.
$$  

The one-year annually compounded interest rate is $r=5\%$ . (This is a one-step binomial tree model with $u=0.2$ $d=-0.1$ $p=0.75$ $r=0.05$ ). Consider a European call with strike $K=92$ and maturity $T=1$ on the stock. The payout at $T=1$ of the call is  

$$
C_{K}(1,1)=(S_{1}-K)^{+}=\left\{{\begin{array}{l l}{(120-92)^{+}=28,}&{{\mathrm{with~probability~}}0.75,}\ {(90-96)^{+}=0,}&{{\mathrm{with~probability~}}0.25}\end{array}}\right.
$$  

Using formula (10.3.1) gives  

$$
C_{K}(0,1)=Z(0,1)\mathbb{E}(C_{K}(1,1)|S_{0}=100)=(1+0.05)^{-1}\left(28\cdot0.75+0\cdot0.4\right)=20
$$  

We now show that this price allows us to construct an arbitrage portfolio.  

Portfolio A:  

Time $t$ : Start empty. Write and sell one call for 20 cash, borrow an additional 80 cash, buy 1 stock for 100 cash. Then the portfolio consists of 1 short call, 1 stock, -80 cash.  

We have $V^{A}(0)=0$ and  

$$
{}^{4}(1)=S_{1}-(S_{1}-K)^{+}-80(1+0.05)^{1-0}=S_{1}-(S_{1}-K)^{+}-84\left\{120-28-84=8,\atop90-0-84=6,\atop}\right.
$$  

with probability 0.75, with probability 0.25,  

Therefore $V^{A}(T)>0$ with probability one. So $A$ is an arbitrage portfolio.  

# 10.4 Risk-Neutral Pricing: One-Step Binomial Tree  

Consider a one-step binomial tree model for a stock paying no income. With respect to the real-world probability measure $P$ , the probability of an up movement is $P(S_{1}=(1+$ $u)S_{0})=p$ , and the probability of a down movement is $P(S_{1}=(1+d)S_{0})=1-p$ The constant annually compounded interest rate is $r$  

Result 10.4.1 (Fundamental Theorem). If there are no arbitrage portfolios, then $d<r<u$ and  

$$
V^{A}(0)=Z(0,1)\mathbb{E}^{*}(V^{A}(1)|S_{0})
$$  

for any portfolio $A$ , where the expectation is computed with respect to the probability measure $P^{*}$ defined by  

$$
P^{*}(S_{1}=(1+u)S_{0})=p^{*}=\frac{r-d}{u-d}.
$$  

Before proving Result 10.4.1, we prove an auxillary result that shows there is only one possible measure $P^{*}$ that will work.  

Result 10.4.2. Let $P^{*}$ be any probability measure for the one-step binomial tree. Then  

Proof.  

$$
\begin{array}{r l}&{S_{0}=Z(0,1)\mathbb{E}^{*}(S_{1}|S_{0})}\ &{\quad=(1+r)^{-1}\cdot(p^{*}(1+u)S_{0}+(1-p^{*})(1+d)S_{0})}\ &{\quad=(1+r)^{-1}\cdot(p^{*}(1+u)+(1-p^{*})(1+d))\cdot S_{0}.}\end{array}
$$  

Divide both sides by $S_{0}$ to get  

$$
1=(1+r)^{-1}(p^{*}(1+u)+(1-p^{*})(1+d)).
$$  

Solving for $p^{*}$ gives  

$$
p^{*}=\frac{r-d}{u-d}.
$$  

Proof of Result 10.4.1. Assume there are no-arbitrage portfolios.  

Then we must have $d<r<u$ .Indeed, if either $r\geq u>d$ or $d<u\leq r$ , then we. can construct an arbitrage portfolio. In the first case we proceed as follows. At $T=0$ borrow 1 stock, sell it for $S_{0}$ cash, invest the cash at interest rate $r$ ; at $T=1$ we have $S_{0}(1+r)$ cash and a debt of one stock, which has positive probability $1-p$ of having price $S_{0}(1+d)<S_{0}(1+r)$ . The second case is similar.  

Define $\begin{array}{r}{p^{*}=\frac{r-d}{u-d}}\end{array}$ . Since $d<r<u$ we have $0<p^{*}<1$ . Remember the sample space is $\Omega=\{\omega_{A},\omega_{B}\}$ . Define the probability measure $P^{*}$ by $\begin{array}{r}{P^{*}(\{\omega_{A}\})=P^{*}(S_{1}=S_{0}(1+u))=}\end{array}$ $p^{*}$ and $P^{*}(\{\omega_{B}\})=P^{*}(S_{1}=S_{0}(1+d))=1-p^{*}$ . Note $P(E)=1$ if and only if $E=\Omega$ if and only if $P^{*}(E)=1$  

By Result 10.4.2,  

$$
Z(0,1)\mathbb{E}^{*}(S_{1}|S_{0})=S_{0}.
$$  

Now let $A$ be any portfolio. For some $\alpha,\beta>0$ , we have  

$$
V^{A}(1)=\left\{\begin{array}{c l}{{\alpha}}&{{\mathrm{if}\:S_{1}=S_{0}(1+u)}}\ {{\beta}}&{{\mathrm{if}\:S_{1}=S_{0}(1+d)}}\end{array}\right.
$$  

Since the no-arbitrage principle holds, the replication principle holds. Arguing as in the proof of Result 10.2.1, the porfolio $A^{\prime}$ % $\begin{array}{r}{x=\frac{\alpha-\beta}{S_{0}(u-d)}}\end{array}$ stocks and $\begin{array}{r}{y=\alpha-\frac{\alpha-\beta}{u-d}(1+u)}\end{array}$ ZCBs satisfies $V^{A}(1)=V^{A^{\prime}}(1)$ , and so (by the replication principle) $V^{A}(0)=V^{A^{\prime}}(0)$  

Using this and (10.4.1), we have  

$$
\begin{array}{r l}&{Z(0,1)\mathbb{E}^{*}(V^{A}(1)|S_{0})=Z(0,1)\mathbb{E}^{*}(V^{A^{\prime}}(1)|S_{0})=Z(0,1)\mathbb{E}^{*}(x S_{1}+y|S_{0})}\ &{\qquad=Z(0,1)(x\mathbb{E}^{*}(S_{1}|S_{0})+y)=x Z(0,1)\mathbb{E}^{*}(S_{1}|S_{0})+y Z(0,1)}\ &{\qquad=x S_{0}+y Z(0,1)=V^{A^{\prime}}(0)=V^{A}(0).}\end{array}
$$  

Remark 10.4.3. The probability measure $P$ represents the real-world probabilities determined from observation and data. The probability measure $P^{*}$ represents the probabilities in an arbitrage-free world.  

Exercise 10.4.1. Show that Result 10.4.1 also gives (10.2.2).  

# 10.5 Multi-Step Binomial Tree  

We now introduce the multi-step binomial tree model for a stock paying no income.  

In the multi-step binomial tree, the stock price is modeled at times $0,\Delta T,2\Delta T,\ldots,n\Delta T,\ldots$ The parameter $\Delta T>0$ is the time step.  

We assume the interest rate with compounding frequency $1/\Delta T$ is a positive constant, and we denote it by $r$  

At time 0 the stock price $S_{0}$ is known..  

At time $\Delta T$ , the stock price becomes $S_{\Delta T}~=~(1+u)S_{0}$ with probability $p$ , or $S_{\Delta T}=$ $(1+d)S_{0}$ with probability $1-p$  

At time $2\Delta T$ , the stock price becomes $S_{2\Delta T}=(1+u)S_{\Delta T}$ with probability $p$ , or $S_{2\Delta T}=$ $(1+d)S_{\Delta T}$ with probability. $1-p$  

At time $n\Delta T$ , the stock price becomes $S_{n\Delta T}=(1+u)S_{(n-1)\Delta T}$ with probability $p$ , or $S_{n\Delta T}=(1+d)S_{(n-1)\Delta T}$ with probability $(1-p)$  

A change from $S_{(n-1)\Delta T}$ to $S_{n\Delta T}=(1+u)S_{(n-1)\Delta T}$ is called a up-movement. A change from $S_{(n-1)\Delta T}$ to $S_{n\Delta T}=(1+d)S_{(n-1)\Delta T}$ is called a down-movement..  

Whether the price moves up or down at time $n\Delta$ is independent of whether the price moves up or down at any other time..  

The parameters $u$ and $d$ are the possible percentage changes in the stock price at each step. They must satisfy $0<1+d<1+u$  

![](62e8ec0f98ce95fdb1377396d75ba7959fc0f62835aa61ff9d3acde8dcffd720.jpg)  
Figure 10.2: Branch of a Binomial Tree  

![](f3845d0191d399163d54002359af0225418de36142bddf401e928a90b01139d0.jpg)  
Figure 10.3: One-Step Binomial Tree with $r=0.1$ $d=-0.1$ , and $u=0.2$  

![](629152657c8dffb5816542e7bf33498342f15329ab6e0bbb2e425b19aad58a71.jpg)  
Figure 10.4: Two-Step Binomial Tree with $d=-0.1$ and $u=0.2$  

Here is an equivalent way to define how the price changes at each time:  

$$
S_{n\Delta T}=\xi_{n}S_{(n-1)\Delta T}\quad\mathrm{for}n=1,2,\ldots,
$$  

where $\xi_{1},\xi_{2},\ldots$ is a sequence of independent random variables with  

$$
\xi_{i}={\left\{\begin{array}{l l}{(1+u)}&{{\mathrm{with~probability~}}p}\ {(1+d)}&{{\mathrm{with~probability~}}1-p}\end{array}\right.}
$$  

By applying (10.5.1) repeatedly, we see  

$$
S_{n\Delta T}=\xi_{n}S_{(n-1)\Delta T}=\xi_{n}\xi_{n-1}S_{(n-2)\Delta T}=...=\xi_{n}\cdot\cdot\cdot\xi_{1}S_{0}.
$$  

The probability $p$ of an "up" movement determines the probability measure $P$  

# Result 10.5.1.  

$\gamma^{k}(1+d)^{n-k}S_{0})=P(\mathrm{exactly~}k^{*}\mathrm{up}^{,*}\mathrm{movements~in~period~0~to~}n)={\binom{n}{k}}p^{k}(1-p)^{n-k}S_{0}.$ for $0\leq k\leq n$  

Proof. From time 0 to time $n$ , the stock price changes $n$ times. If  

$$
S_{n\Delta T}=(1+u)^{k}(1+d)^{n-k}S_{0},
$$  

it means the stock price moves "up"' exactly. $k$ times out of the $n$ possible times. For example, if $n=5$ and $k=3$ , a typical path with exactly $k$ "up" movements is  

There are ${\binom{n}{k}}$ possible paths with exactly $k$ up movements: Out of the $n$ changes, choose $k$ Of them to be "up" and the rest "down.' Each such path has probability $p^{k}(1-p)^{n-k}$ Therefore  

$$
P(S_{n\Delta T}=(1+u)^{k}(1+d)^{n-k}S_{0})={\binom{n}{k}}p^{k}(1-p)^{n-k}
$$  

for $0\leq k\leq n$  

Remark. A derivative that pays out only at a single time $T$ is called a European-style derivative. Examples are forwards, Europeans calls, European puts, European call butterflies, and any portfolio that consists of European options all maturing at the same time. American options are not examples, since they can payout at any time $t\leq T$ . By iterating the argument in the proof of 10.2.1, we can show that any European-style derivative can be replicated by a portfolio consisting of only stocks and ZCBs.  

Result 10.5.2 (Fundamental Theorem). If there are no arbitrage portfolios, then $d<r\Delta T<$ $u$ and  

$$
V^{A}(t)=Z(t,T)\mathbb{E}^{*}(V^{A}(T)|S_{t})
$$  

for any portfolio $A$ and times $T>t\geq0$ , where the expectation is computed with respect to the probability measure $P^{*}$ defined by  

$$
P^{*}(S_{n\Delta T}=(1+u)S_{(n-1)\Delta T})=p^{*}=\frac{r\Delta T-d}{u-d}.
$$  

Remark. We omit the proof, which is similar to the proof of Result 10.4.1.  

# 10.6 Derivative Pricing for the Binomial Tree: Part 1  

Consider a binomial tree (parameters $\Delta T,r,u,d,p)$ for a stock paying no income. The stock price at time $T$ is denoted $S_{T}$  

The fundamental theorem (Result 10.5.2) allows us to prove an exact formula for the price of European call options.  

Result 10.6.1 (Cox-Rubenstein Formula for European Calls). Assume there are no arbitrage portfolios. The price at 0 of a European call with maturity $T=n\Delta T$ and strike $K$ is  

$$
C_{K}(0,T)=(1+r\Delta T)^{-n}\sum_{k=0}^{n}\operatorname*{max}\left\{(1+u)^{k}(1+d)^{n-k}S_{0}-K,0\right\}\binom{n}{k}\left(p^{*}\right)^{k}(1-u)^{-n}d u.
$$  

where $p^{*}={\frac{r\Delta T-d}{u-d}}$ and $1-p^{*}=\frac{u-r\Delta T}{u-d}$  

In fact, we can prove a more general formula.  

Result 10.6.2 (General Cox-Rubenstein Formula). Assume there are no arbitrage portfolios. Consider a derivative on the stock with payout $g(S_{T})$ at $T=n\Delta T$ (and no payout otherwise). The price at time 0 is  

$$
=Z(0,T)E^{*}(g(S_{T})|S_{0})=(1+r\Delta T)^{-n}\sum_{k=0}^{n}g((1+u)^{k}(1+d)^{n-k}S_{0}){\binom{n}{k}}p^{*k}(1-p^{*})
$$  

where $p^{*}={\frac{r\Delta T-d}{u-d}}$ and $1-p^{*}=\frac{u-r\Delta T}{u-d}$  

We will prove Result 10.6.1 in case $\Delta T=1$ . It is an exercise for the reader to modify the proof to obtain Result 10.6.2.  

Proof of Result 10.6.1 in case $\Delta T=1$ .We have  

$$
C_{K}(T,T)=\operatorname*{max}{\left\{S_{T}-K,0\right\}}=\operatorname*{max}{\left\{S_{n}-K,0\right\}}=g(S_{n}).
$$  

and  

$$
Z(0,T)=Z(0,n)=(1+r)^{-n}.
$$  

By the fundamental theorem,  

$$
C_{K}(0,T)=Z(0,T)\mathbb{E}^{*}(C_{K}(T,T)|S_{0})=(1+r)^{-n}\mathbb{E}^{*}(g(S_{n})|S_{0}).
$$  

By the Law of the Unconscious Statistician,  

$$
C_{K}(0,T)=(1+r)^{-n}\sum_{s\in{\cal R}(S)}g(s)P^{*}(S_{n}=s|S_{0}).
$$  

The possible values of $S_{n}$ are  

$$
(1+u)^{k}(1+d)^{n-k}S_{0}\quad\mathrm{~for~}k=0,1,\ldots,n.
$$  

Hence  

$$
\k_{1},\l_{T})=(1+r)^{-n}\sum_{k=0}^{n}g((1+u)^{k}(1+d)^{n-k}S_{0})P^{*}(S_{n}=(1+u)^{k}(1+d)^{n-k}S_{0}|S_{0}).
$$  

By Result 10.5.2,  

$$
p^{*}={\frac{r-d}{u-d}},
$$  

is the probability of an "up" movement in the stock price with respect to the risk-neutral probability measure $P^{*}$ . Therefore, by Result 10.5.1,  

$$
P^{*}(S_{n}=(1+u)^{k}(1+d)^{n-k}S_{0}|S_{0})={\binom{n}{k}}p^{*k}(1-p^{*})^{n-k}\quad{\mathrm{~for~}}k=0,1,\ldots,n.
$$  

Hence  

$$
C_{K}(0,T)=(1+r)^{-n}\sum_{k=0}^{n}g((1+u)^{k}(1+d)^{n-k}S_{0}){\binom{n}{k}}p^{*k}(1-p^{*})^{n-k}.
$$  

Since $g(x)=\mathrm{max}\{x-K,0\}$ , we are done.  

Let's do a computation with this formula.  

Example 10.6.3. Assume no-arbitrage. The constant annually compounded interest rate is $10\%$ . The time step is $\Delta T=1$ . At current time 0, a stock paying no income has price 50. Suppose that at each time point, the stock price can go up by $30\%$ or down by $20\%$ . Find the price at 0 of a European put with strike 47 and maturity 2.  

![](901dde31ef7e23dd3c0c85b277996320e3e104c3850c0dc76aee78fdf5852618.jpg)  

Exercise 10.6.1. We proved Result 10.6.1 in the case $\Delta T=1$ . Modify the argument to prove Result 10.6.2 for arbitrary $\Delta T$  

# 10.7 Derivative Pricing for the Binomial Tree: Part 2  

Consider a binomial tree (parameters $\Delta T,r,u,d,p)$ for a stock paying no income. The stock price at time $T$ is denoted $S_{T}$  

Let's do Example 10.6.3 by a different method.  

Example 10.7.1. Assume no-arbitrage. The constant annually compounded interest rate is $10\%$ . The time step is $\Delta T=1$ . At current time 0, a stock paying no income has price 50. Suppose that at each time point, the stock price can go up by $30\%$ or down by $20\%$ . Find the price at 0 of a European put with strike 47 and maturity 2..  

![](920d5455da79a1b9331b50e24a1f2f926e09b86f6ca00c2ddc3767e8967c52ab.jpg)  

![](581f9bf7738e826cdce9f6920ceafe4fa54ad096103c831c3eb10f4bd72a1080.jpg)  

Let's do the same example again, but with an American put.  

Example 10.7.2. Assume no-arbitrage. The constant annually compounded interest rate is $10\%$ . The time step is $\Delta T=1$ . At current time 0, a stock paying no income has price 50.. Suppose that at each time point, the stock price can go up by. $30\%$ or down by $20\%$ . Find the price at 0 of a American put with strike 47 and maturity 2.  

![](95c61b259910643931fe83df261c4923385d1129c7af1bd4102f127cc262c37a.jpg)  

![](2c601f549c273f77fd16297b62a6d45d4f1fd01fc2f9db4ee404021ff3afd5df.jpg)  

![](a1a18ecb2440a702773245392e2bac5a4cdf7a447b56b47fe17574e19bc27394.jpg)  

![](3216132ed7c3e790ea87dac4afe679cbd90ec658d0e16528f3f9e36d92f6bd60.jpg)  

![](542ef9d50138931df167058f31f15f82648fde8da06333124819d4096dcd9b4e.jpg)  

Remark. The examples above show that an American put can have price strictly greater than a European put with the same strike and maturity.  

Remark. The examples in this section demonstrate an algorithm you can program into a computer.  

# Chapter 11  

# Risk-Neutral Pricing and The General Fundamental Theorem  

# 11.1 Equivalent Probability Measures  

Multiple probability measures can be defined on the same sample space.  

Example 11.1.1. Roll a six-sided die. Sample space: $\Omega=\{1,2,3,4,5,6\}$  

Consider the probability measure $P$ on $\Omega$ defined by $\begin{array}{r}{P(\{\omega\})=\frac{1}{6}}\end{array}$ for all $\omega\in\Omega$ .This would be the appropriate measure if the die is fair.  

Consider also the probability measure $P^{*}$ on $\Omega$ defined by $\begin{array}{r}{P^{*}(\{\omega\})=\frac{1}{7}}\end{array}$ for all $\omega\in$ $\{1,2,3,4,5\}$ and $\textstyle P^{*}(\{6\})={\frac{2}{7}}$ . This would be an appropriate measure if the die is unfair (weighted) in a certain way..  

Consider the random variable $X=$ the number shown on the die. $R(X)=\left\{1,2,3,4,5,6\right\}$ The expectation of $X$ with respect to $P$ is  

$$
\operatorname{\mathbb{E}}(X)=\sum_{k\in R(X)}k P(X=k)=(1)(1/6)+(2)(1/6)+...+(5)(1/6)+(6)(1/6)=21/6
$$  

The expectation of $X$ with respect to $P^{*}$ is  

$$
\operatorname{\mathbb{E}}(X)=\sum_{k\in R(X)}k P(X=k)=(1)(1/7)+(2)(1/7)+...+(5)(1/7)+(6)(2/7)=54/1
$$  

Definition 11.1.1. Two probability measures $P$ and $P^{*}$ on the same sample space are called equivalent if  

(i) the events that have probability one according to $P$ are exactly the events that have. probability one according to $P^{*}$   
(ii) the events that have probability zero according to $P$ are exactly the events that have. probability zero according to $P^{*}$   
(iii) the events that have probability non-zero according to $P$ are exactly the events that. have probability non-zero according to. $P^{*}$  

In symbols, for every event $A$ (i) $P(A)=1$ if and only if $P^{*}(A)=1$ (ii) $P(A)=0$ if and only if $P^{*}(A)=0$ (iii) $P(A)>0$ if and only if $P^{*}(A)>0$  

Remark 11.1.2. We don't need to include all the conditions (i),(ii),(ii) in the definition.   
As soon as we have one condition, we have have the other two.  

Remark 11.1.3. Recall the definition of arbitrage portfolio: A portfolio $A$ is an arbitrage portfolio if the following conditions are satisfied:.  

At current time $t$  

$$
V^{A}(t)\leq0.
$$  

At some future time $T$  

$$
P(V^{A}(T)\geq0)=1\quad\mathrm{and}\quad P(V^{A}(T)>0)>0.
$$  

Notice the definition only cares about events having probability one and probability nonzero. Therefore, if. $P$ and $P^{*}$ are equivalent probability measures, then they have the same arbitrage portfolios; in other words, the portfolios that are arbitrage portfolios with respect to $P$ are exactly the portfolios that are arbitrage portfolios with respect to $P^{*}$  

# 11.2 The Fundamental Theorem of Asset Pricing  

Result 10.4.1 and Result 10.5.2 can be viewed as special cases of  

Theorem 11.2.1 (General Fundamental Theorem). There are no arbitrage portfolios $\Leftrightarrow$ there exists a probability measure $P^{*}$ equivalent to $P$ such that  

$$
V^{A}(t)=Z(t,T)\mathbb{E}^{*}(V^{A}(T)|\mathcal{Z}_{t})\quad\mathrm{for~all~times~}t<T\mathrm{~and~all~portfolios~}A.
$$  

Notation. $\mathcal{T}_{t}$ is an abbreviation for all random variables relevant to the portfolio at time $t$ .Typically, there will only be one relevant variable. For a portfolio that depends on a stock price, $\mathcal{I}_{t}=S_{t}=$ stock price at $t$ . For a derivative that depends on an interest rate, $\mathcal{T}_{t}=$ interest rate at $t$  

The fundamental theorem can be proved in very general settings, but we will not go into details in this course. We proved the. $\Rightarrow$ half of Theorem 11.2.1 in the case of the one-step. binomial tree when we proved Result 10.4.1. Here we prove the. $\Leftarrow$ half Theorem 11.2.1.  

Proof. Assume there exists a probability measure $P^{*}$ equivalent to $P$ such that (11.2.1) holds. We will show there are no arbitrage portfolios.  

Seeking a contradiction, we assume $A$ is an arbitrage portfolio. Without loss of generality, we may assume  

$$
\begin{array}{l}{\bullet~V^{A}(0)\leq0}\ {\bullet~P(V^{A}(1)\geq0)=1}\ {\bullet~P(V^{A}(1)>0)>0}\end{array}
$$  

Since $P^{*}$ is equivalent to $P$  

$$
\begin{array}{l}{{V^{A}(0)\leq0}}\ {{{}}}\ {{P^{*}(V^{A}(1)\geq0)=1}}\ {{{}}}\ {{P^{*}(V^{A}(1)>0)>0}}\end{array}
$$  

By (ii) and (ii) and the definition of expectation, we have $\mathbb{E}\ast(V^{A}(1)|\mathcal{Z}_{0})>0$ .This contradicts (i).  

To make things more concrete, suppose we are in the one-step binomial tree model. We must have  

$$
V^{A}(1)=\left\{\begin{array}{c l}{{\alpha}}&{{\mathrm{if}\:S_{1}=S_{0}(1+u)}}\ {{\beta}}&{{\mathrm{if}\:S_{1}=S_{0}(1+d)}}\end{array}\right.
$$  

for some numbers $\alpha,\beta$ . Let $p^{*}$ be the probability of an up movement with respect to $P^{*}$ Therefore  

$$
V^{A}(1)=\left\{\begin{array}{l l}{{\alpha}}&{{\mathrm{with~probability~}p^{*}}}\ {{\beta}}&{{\mathrm{with~probability~}1-p^{*}}}\end{array}\right.
$$  

Then (ii) implies. $\alpha\geq0$ and $\beta\geq0$ , and (ili) implies at least one of $\alpha$ and $\beta$ is positive. Without loss of generality, assume $\alpha>\beta\geq0$ . Since (11.2.1) holds,  

$$
V^{A}(0)=Z(0,1)\mathbb{E}^{*}(V^{A}(1)|S_{0})=Z(0,1)(\alpha p^{*}+\beta(1-p^{*}))>0.
$$  

This contradicts (i).  

Definition 11.2.1. A probability measure $P^{*}$ equivalent to $P$ that satisfies (11.2.1) is called a risk-neutral probability measure (or an equivalent martingale probability measure).  

Remark 11.2.2. The probability measure. $P$ represents the real-world probabilities deter-. mined from observation and data. A risk-neutral probability measure $P^{*}$ represents the probabilities in an arbitrage-free world.. $\triangle$  

Theorem 11.2.3 (Restatement of The Fundamental Theorem of Asset Pricing). There are no arbitrage portfolios if and only if there exists a risk-neutral probability measure. $\triangle$  

Corollary 11.2.4 (Applications of the Fundamental Theorem). Let. $S_{t}$ be the price at $t$ of an arbitrary asset. If there are no-arbitrage portfolios, then there exists a risk neutral probability measure $P^{*}$ and:  

(i) If the asset pays no income, then  

$$
S_{t}=Z(t,T)\mathbb{E}^{*}(S_{T}|S_{t})\quad{\mathrm{for~all~times~}}t\leq T
$$  

(ii) If $D_{t}$ is the price at $t$ of a European derivative on the asset (i.e., a derivative that pays out $D_{T}=g(S_{T})$ at $T$ and nothing otherwise), then  

$$
D_{t}=Z(t,T)\mathbb{E}^{*}(D_{T}|S_{t})\quad{\mathrm{for~all~times~}}t\leq T
$$  

Proof. (i): Let portfolio. $A$ consist only of the asset. (ii): Let portfolio $A$ consist only of the.   
derivative.  

The fundamental theorem to reproduce some standard results.  

Example 11.2.5. Assume no-arbitrage. Consider a forward with delivery price $K$ and maturity $T$ on a stock paying no income. The prices of the forward and stock at time $t$ are denoted $V_{K}(t,T)$ and $S_{t}$ . Let $A$ be the portfolio consisting of only the forward. By the fundamental theorem,  

$$
\begin{array}{r l}&{V_{K}(t)=V^{A}(t)=Z(t,T)\mathbb{E}^{*}(V^{A}(T)|S_{t})}\ &{\qquad=Z(t,T)\mathbb{E}^{*}(S_{T}-K|S_{t})=Z(t,T)\mathbb{E}^{*}(S_{T}|S_{t})-Z(t,T)K}\end{array}
$$  

By Corollary 11.2.4(i), we get  

$$
V_{K}(t,T)=S_{t}-Z(t,T)K,
$$  

which is the same result we got by replication.  

Exercise 11.2.1. Assume no-arbitrage.  Consider a forward with delivery price $K$ and maturity $T$ on a stock paying dividends at continuous yield. $q$ with automatic reinvestment. The prices of the forward and stock at time. $t$ are denoted $V_{K}(t)$ and $S_{t}$ . Use the fundamental theorem (not replication) to prove $V_{K}(t)=S_{t}e^{-q(T-t)}-K Z(t,T)$ . Hint: At some point you will need to show $E(S_{T}|S_{t})=S_{t}e^{-q(T-t)}/Z(t,T)$ . To do so, consider portfolio $B$ consisting of just the stock, find $V^{B}({\cal T})$ , and apply the fundamental theorem to. $B$  

Exercise 11.2.2. Assume no-arbitrage. Consider a forward rate agreement with maturity $T$ , fixed rate $K$ , and term length $\alpha$ . Use the fundamental theorem (not replication), to prove that the value at time $t$ is $V_{K}(t,T)=Z(t,T)-Z(t,T+\alpha)-\alpha K Z(t,T+\alpha)$  

# Chapter 12  

# Probability Theory: Normal. Distribution and Central Limit Theorem  

# 12.1 Normal Distribution  

Let $X$ be a random variable. If there are constants $\mu\in\mathbb{R}$ and $\sigma>0$ such that  

$$
P(a\leq X\leq b)=\int_{a}^{b}{\frac{1}{\sqrt{2\pi\sigma^{2}}}}e^{-(x-\mu)^{2}/2\sigma^{2}}d x
$$  

for all real numbers $a\leq b$ , then we write.  

$$
X\sim{\mathcal{N}}(\mu,\sigma^{2})
$$  

and we say that $X$ has normal distribution (with respect to $P$ ). Note that $X$ is non-discrete with $R(X)=\mathbb{R}$  

Theorem 12.1.1. If $X\sim{\mathcal{N}}(\mu,\sigma^{2})$ , then:  

(i) For any function $g(x)$ , the expectation of $g(X)$ is  

$$
\mathbb{E}(g(X))=\int_{-\infty}^{\infty}{\frac{1}{\sqrt{2\pi\sigma^{2}}}}e^{-(x-\mu)^{2}/2\sigma^{2}}g(x)d x
$$  

(ii) The expectation of $X$ is  

$$
\mathbb{E}(X)=\mu.
$$  

(iii) The variance of $X$ is  

$$
\operatorname{Var}(X)=\operatorname{\mathbb{E}}((X-\mu)^{2})=\operatorname{\mathbb{E}}(X^{2})-\mu^{2}=\sigma^{2}.
$$  

# 12.2 Standard Normal Distribution  

Definition 12.2.1. If $W\sim N(0,1)$ , we say that $W$ has standard normal distribution.  

Definition 12.2.2. The function  

$$
\Phi(t)=P(X\leq t)=\int_{-\infty}^{t}{\frac{1}{\sqrt{2\pi}}}e^{-x^{2}/2}d x
$$  

is called the standard normal cumulative distribution function or standard normal cdf.  

Definition 12.2.3. The function  

$$
\phi(x)=\Phi^{\prime}(x)=\frac{1}{\sqrt{2\pi}}e^{-x^{2}/2}
$$  

is called the standard normal probability density function or standard normal pdf.  

Theorem 12.2.1. If $W\sim N(0,1)$ and if. $a$ and $b$ are real numbers, then  

$$
X=a+b W\sim N(a,b^{2}).
$$  

# 12.3 Central Limit Theorem  

The central limit theorem is the reason the normal distribution is so important. Basically,. it says that any sum of many independent random effects is approximately normally distributed.  

Theorem 12.3.1 (Central Limit Theorem). If $X_{1},X_{2},\dots$ are independent identically distributed random variables with $\mathbb{E}(X_{i})=0$ and $\operatorname{Var}(X_{i})=1$ , then  

$$
{\frac{1}{\sqrt{n}}}\sum_{i=1}^{n}X_{i}\to N(0,1)
$$  

which is an abbreviation for  

$$
\operatorname*{lim}_{n\to\infty}P\left(a\leq{\frac{1}{\sqrt{n}}}\sum_{i=1}^{n}X_{i}\leq b\right)=\int_{a}^{b}{\frac{1}{\sqrt{2\pi}}}e^{-x^{2}/2\sigma^{2}}d x
$$  

for all real numbers $^{a,b}$  

# Chapter 13  

# Continuous-Time Limit and Black-Scholes  

# 13.1 Binomial Tree to Black-Scholes  

In this section, we motivate the Black-Scholes model as a continuous-time limit of the binomial tree model.  

Consider a stock paying no income whose price at time $T$ is $S_{T}$ . We divide the time interval $[0,\infty)$ at very closely spaced time points $0,\Delta T,2\Delta T,...,(n-1)\Delta T,n\Delta T,...$ with step size  

$$
\Delta T={\frac{1}{N}},
$$  

where $N$ is a very large positive integer. We aim to let $N\rightarrow\infty$ . We suppose the stock obeys a binomial tree model with $\Delta T,r,u,d$ , and $p=1/2$ . Thus the stock price satisfies  

$$
S_{i\Delta T}=\xi_{i}^{(N)}S_{(i-1)\Delta T}\quad\mathrm{for}i=0,1,2,....
$$  

where $\xi_{1}^{(N)},\xi_{2}^{(N)},\dots$ are independent random variables with identical distributions  

$$
\xi_{i}^{(N)}=\left\{\begin{array}{l l}{{1+u}}&{{\mathrm{with~}P\mathrm{~probability~}p=1/2}}\ {{1+d}}&{{\mathrm{with~}P\mathrm{~probability~}1-p=1/2}}\end{array}\right.
$$  

Here $P$ is the real-world probability measure.  

We assume there are no arbitrage portfolios. So there is a risk-neutral probability measure $P^{*}$ . Under the risk-neutral probability measure $P^{*}$ , the probability of an up-movement is  

$$
p^{*}={\frac{r\Delta T-d}{u-d}}
$$  

and so  

$$
\xi_{i}^{(N)}=\left\{\begin{array}{l l}{{1+u}}&{{\mathrm{with~}P^{*}\mathrm{~probability~}p^{*}}}\ {{1+d}}&{{\mathrm{with~}P^{*}\mathrm{~probability~}1-p^{*}}}\end{array}\right.
$$  

The stock price at $T=n\Delta T$ is  

$$
S_{T}=S_{n\Delta T}=\xi_{N}^{(N)}S_{(N-1)\Delta T}=\xi_{N}^{(N)}\xi_{N-1}^{(N)}S_{(N-2)\Delta T}=\cdot\cdot\cdot=\xi_{N}^{(N)}\xi_{N-1}^{(N)}\cdot\cdot\cdot\xi_{1}^{(N)}S_{0},
$$  

Hence, for. $t=k\delta T<n\delta T=T$  

$$
S_{T}/S_{t}=\xi_{n}^{(N)}\xi_{n-1}^{(N)}\cdot\cdot\cdot\xi_{k+1}^{(N)}.
$$  

If $t_{1}<T_{1}\leq t_{2}<T_{2}$ (with $t_{i}=k_{i}\Delta T$ and $T_{i}=n_{i}\Delta T)$ , then the random variables  

$$
S_{T_{1}}/S_{t_{1}}=\xi_{n_{1}}^{(N)}\xi_{n_{1}-1}^{(N)}\cdot\cdot\cdot\xi_{k_{1}+1}^{(N)}\quad\mathrm{~and~}\quad S_{T_{2}}/S_{t_{2}}=\xi_{n_{2}}^{(N)}\xi_{n_{2}-1}^{(N)}\cdot\cdot\cdot\xi_{k_{2}+1}^{(N)}
$$  

are independent.  

Fix $t=k\Delta T<n\Delta T=T$ For simplicity, assume $t=0$  

Then (13.1.1) is  

$$
S_{T}/S_{0}=\xi_{n}^{(N)}\xi_{n-1}^{(N)}\cdot\cdot\cdot\xi_{1}^{(N)}.
$$  

We aim to take the limit. $N\rightarrow\infty$ $\Delta T\to0$ and use the central limit theorem. But $\xi_{n}^{(N)}\xi_{N-1}^{(N)}\cdot\cdot\cdot\xi_{1}^{(N)}$   
we take logarithms:  

$$
\ln(S_{T}/S_{0})=\sum_{i=1}^{n}\ln\xi_{i}^{(N)}.
$$  

By some algebra, we can show  

$$
\ln\xi_{i}^{(N)}=\mu\Delta T+\sigma\sqrt{\Delta T}X_{i}
$$  

where and $X_{1},X_{2},\dots$ , are independent with identical distributions  

$$
X_{i}={\left\{\begin{array}{l l}{+1}&{{\mathrm{with~}}P{\mathrm{~probability~}}1/2}\ {-1}&{{\mathrm{with~}}P{\mathrm{~probability~}}1/2}\end{array}\right.}={\left\{\begin{array}{l l}{+1}&{{\mathrm{with~}}P^{*}{\mathrm{~probability~}}1/2}\ {-1}&{{\mathrm{with~}}P^{*}{\mathrm{~probability~}}1/2}\end{array}\right.}
$$  

Note $\mathbb{E}(X_{i})=0$ and $\operatorname{Var}(X_{i})=1$ for all $i$  

Now  

$$
\begin{array}{l}{{\displaystyle\ln(S_{T}/S_{0})=\sum_{i=1}^{n}\ln\xi_{i}^{(N)}}}\ {{\displaystyle~=\mu\Delta T n+\sigma\sqrt{\Delta T}n\sum_{i=1}^{n}X_{i}}}\ {{\displaystyle~=\mu T+\sigma\sqrt{T}\frac{1}{\sqrt{n}}\sum_{i=1}^{n}X_{i}.}}\end{array}
$$  

Now we let. $N\rightarrow\infty$ . Since $T=n\Delta T=n/N$ and since $T$ is fixed, we have. $n\to\infty$ also. Thus the central limit theorem implies  

$$
\ln(S_{T}/S_{0})\to\mu T+\sigma\sqrt{T}W,\quad\mathrm{where}W\sim N(0,1)\mathrm{w.r.t}P
$$  

hence  

$$
\ln(S_{T}/S_{0})\rightarrow N(\mu T,\sigma^{2}T)
$$  

with repsect to $P$ . With some adjustments, we can show for any $t<T$ that  

$$
\ln(S_{T}/S_{t})\to N\left(\mu(T-t),\sigma^{2}(T-t)\right)
$$  

with respect to $P$  

With a more complicated argument, we can show for any $t<T$ that  

$$
\ln(S_{T}/S_{t})\to N\left(\left(r-\frac{1}{2}\sigma^{2}\right)(T-t),\sigma^{2}(T-t)\right)
$$  

with respect to $P^{*}$ . Here $r$ is the continuously compounded interest rate, which is the limit as $N\rightarrow\infty$ of the interest rate with compounding. $N$ times per year.  

# 13.2 Black-Scholes Model  

We consider a stock paying no income whose price at time $T$ is $S_{T}$  

# Black-Scholes Model  

1. There are no arbitrage portfolios, and there is a risk-neutral probability measure $P^{*}$   
2. There is a constant continuous interest rate $r$   
3. The stock price $S_{0}$ at time O is a known constant.   
4. For any times $0\leq t_{1}<T_{1}\leq t_{2}<T_{2}$ $\ln(S_{T_{1}}/S_{t_{1}})$ and $\ln(S_{T_{2}}/S_{t_{2}})$ are independent.   
5. There are constants $\mu$ (called the drift) and $\sigma>0$ (called the volatility) such that for all times $t<T$ $\ln(S_{T}/S_{t})\sim\mathcal{N}\left(\mu(T-t);\sigma^{2}(T-t)\right)$ with respect to $P$ (the real-world probability measure)..  

6. For all times $t<T$  

$$
\ln(S_{T}/S_{t})\sim{\cal N}\left(\left(r-\frac{1}{2}\sigma^{2}\right)(T-t);\sigma^{2}(T-t)\right)
$$  

with respect to the risk-neutral probability measure $P^{*}$  

Recall that $P^{*}$ being a risk-neutral probability measure means that  

$$
V^{A}(t)=Z(t,T)\mathbb{E}^{*}(V^{A}(T)|S_{t})
$$  

for all portfolios $A$ and all times $t<T$ . By combining 4. and 6. we can prove (exercise) the following result which will be extremely useful in evaluating the expectation in (13.2.1).  

Result 13.2.1. For any function $h:\mathbb{R}\rightarrow\mathbb{R}$ and any times $t<T$  

$$
\mathbb{E}^{*}(h(\ln S_{T})|S_{t})=\frac{1}{\sqrt{2\pi\sigma^{2}(T-t)}}\int_{-\infty}^{\infty}e^{-(x-\nu)^{2}/2\sigma^{2}(T-t)}h(x)d x
$$  

where  

$$
\nu=\ln S_{t}+\left(r-\frac{1}{2}\sigma^{2}\right)(T-t).
$$  

From 5., we have that for all times $t<T$  

$$
\begin{array}{r l}&{\mu=\frac{\mathbb{E}\left(\ln S_{T}-\ln S_{t}\right)}{T-t}}\ &{\sigma^{2}=\frac{\mathbf{V}\mathbf{ar}(\ln S_{T}-\ln S_{t})}{T-t},}\end{array}
$$  

which indicates $\mu$ is expected time rate of change of the logarithmic stock price, and $\sigma^{2}$ is the variance of the change of the logarithmic stock price per unit time. Compare this to the definition of $\mu$ and $\sigma$ in the previous section.  

# 13.3 Black-Scholes Formula  

Result 13.3.1 (Black-Scholes Formula). Assume the Black-Scholes model for a stock paying no income.The price at $t$ of a European call option with strike $K$ and maturity $T$ is  

$$
C_{K}(t,T)=Z(t,T)\frac{1}{\sqrt{2\pi\sigma^{2}(T-t)}}\int_{\ln K}^{\infty}e^{-(x-\nu)^{2}/2\sigma^{2}(T-t)}(e^{x}-K)d x,
$$  

or, equivalently,  

$$
C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})
$$  

or, equivalently,  

$$
C_{K}(t,T)=Z(t,T)(F(t,T)\Phi(d_{1})-K\Phi(d_{2})).
$$  

Here $F(t,T)=\frac{S_{t}}{Z(t,T)}$ is the forward price, $\Phi(t)=\int_{-\infty}^{t}\frac{1}{\sqrt{2\pi}}e^{-x^{2}/2}d x$ x2/2 dx is the standard normal cdf, and  

$$
\begin{array}{l}{{d_{1}={\displaystyle\frac{\ln(S_{t}/K)+(r+{\frac{1}{2}}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}},}}\ {{d_{2}={\displaystyle\frac{\ln(S_{t}/K)+(r-{\frac{1}{2}}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}}=d_{1}-\sigma\sqrt{T-t}}.}\end{array}
$$  

Proof. We will prove (13.3.1). We will not give the details of how to go from (13.3.1) to (13.3.2). It involves a clever change of variable and a lot of algebra. It is easy to see that (13.3.2) and (13.3) ae quivalet by usin theformula (t.T) - 2(t,.1)  

The payout of the call is  

$$
g(S_{T})=(S_{T}-K)^{+}={\left\{\begin{array}{l l}{S_{T}-K}&{{\mathrm{if~}}S_{T}\geq K}\ {0}&{{\mathrm{if~}}S_{T}\leq K}\end{array}\right.}
$$  

Since $P^{*}$ is a risk-neutral probability measure, we have  

CK $t,T)=Z(t,T)E^{*}(g(S_{T})|S_{t})=Z(t,T)E^{*}(g(e^{\ln S_{T}})|S_{t})=Z(t,T)E^{*}(h(\ln S_{T})|S_{t})$ where $h$ is defined by  

$$
h(x)=g(e^{x})=(e^{x}-K)^{+}={\left\{\begin{array}{l l}{e^{x}-K}&{{\mathrm{if~}}x\geq\ln K}\ {0}&{{\mathrm{if~}}x\leq\ln K}\end{array}\right.}
$$  

By Result 13.2.1, we have  

$$
\begin{array}{l}{{\displaystyle C_{K}(t,T)=Z(t,T)\frac{1}{\sqrt{2\pi\sigma^{2}(T-t)}}\int_{-\infty}^{\infty}e^{-(x-\nu)^{2}/2\sigma^{2}(T-t)}h(x)d x}}\ {{\displaystyle~=Z(t,T)\frac{1}{\sqrt{2\pi\sigma^{2}(T-t)}}\int_{\ln K}^{\infty}e^{-(x-\nu)^{2}/2\sigma^{2}(T-t)}(e^{x}-K)d x.}}\end{array}
$$  

This is exactly (13.3.1).  

Example 13.3.2. Use the Black-Scholes formula to find the current price of a European call on a stock paying no income with strike 40 and maturity 18 months from now. Assume the current stock price is 50, the stock volatility is $15\%$ , and the constant continuously compounded interest rate is $5\%$  

$$
\begin{array}{l}{d_{1}={\cfrac{\ln(S_{t}/K)+(r+{\frac{1}{2}}\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}}\ {={\cfrac{\ln(50/40)+(0.05+{\frac{1}{2}}(0.15)^{2})(1.5)}{0.15{\sqrt{1.5}}}}}\ {=1.7147438\ldots}\end{array}
$$  

$$
\begin{array}{l}{{d_{2}=d_{1}-\sigma\sqrt{T-t}}}\ {{\quad=(1.7147438\ldots)-(0.15)\sqrt{1.5}}}\ {{\quad=1.531032\ldots}}\end{array}
$$  

$$
\begin{array}{r l}&{C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})}\ &{\qquad=50\Phi(1.7147438\ldots)-40e^{-0.05(1.5)}\Phi(1.531032\ldots)}\ &{\qquad=13.06\ldots}\end{array}
$$  

# 13.4 Properties of Black-Scholes Formula  

Consider a stock paying no income. Assume the Black-Scholes model of the stock. The Black-Scholes formula for a European call is  

$$
C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})
$$  

where  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}~}}\ {{d_{2}=\displaystyle\frac{\ln(S_{t}/K)+(r-\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}=d_{1}-\sigma\sqrt{T-t}.}}\end{array}
$$  

Recall the bounds on a European call we obtained in Chapter 8:  

$$
\operatorname*{max}\left\{S_{t}-K Z(t,T),0\right\}\leq C_{K}(t,T)\leq S_{t}
$$  

These bounds are illustrated when we plot the price of a 1-year 80-strike call under the Black-Scholes model for various values of the volatility $\sigma$  

# Black-Scholes price of 1-year 100-strike call $(r=5\%$  

![](06e60fd069865d2e777c5c08c0a26b9e7ca33120348fc1a6f0745e7b1708a2cf.jpg)  

As the plot indicates, the bounds are achieved in limiting cases:  

# Result 13.4.1.  

(a) $C_{K}(t,T)\to\operatorname*{max}\left\{S_{t}-K Z(t,T),0\right\}\quad{\mathrm{as}}\quad\sigma\to0.$ (b) $C_{K}(t,T)\rightarrow S_{t}$ as $\sigma\to\infty$  

Proof. We prove (a) and leave (b) as an exercise. We have  

$$
\begin{array}{r l}{\lefteqn{\operatorname*{lim}_{\sigma\to0}d_{1}=\operatorname*{lim}_{\sigma\to0}\frac{\ln\left(S_{t}/K\right)+\left(r+\frac{1}{2}\sigma^{2}\right)(T-t)}{\sigma\sqrt{T-t}}}}\ &{=\operatorname*{lim}_{\sigma\to0}\frac{\ln\left(S_{t}/K\right)+r(T-t)}{\sigma\sqrt{T-t}}+\frac{1}{2}\sigma\sqrt{T-t}}\ &{=\left\{\begin{array}{l l}{+\infty}&{\mathrm{if~}\ln\left(S_{t}/K\right)+r(T-t)>0}\ {0}&{\mathrm{if~}\ln\left(S_{t}/K\right)+r(T-t)=0}\ {-\infty}&{\mathrm{if~}\ln\left(S_{t}/K\right)+r(T-t)<0}\end{array}\right.}\ &{=\left\{\begin{array}{l l}{+\infty}&{\mathrm{if~}S_{t}>K e^{-r(T-t)}}\ {0}&{\mathrm{if~}S_{t}=K e^{-r(T-t)}}\ {-\infty}&{\mathrm{if~}S_{t}<K e^{-r(T-t)}}\end{array}\right.}\end{array}
$$  

Therefore  

$$
\operatorname*{lim}_{\sigma\to0}\Phi(d_{1})=\operatorname*{lim}_{\sigma\to0}P(X\leq d_{1})={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S_{t}>K e^{-r(T-t)}}\ {{\frac{1}{2}}}&{{\mathrm{if~}}S_{t}=K e^{-r(T-t)}}\ {0}&{{\mathrm{if~}}S_{t}<K e^{-r(T-t)}.}\end{array}\right.}
$$  

where $X\sim N(0,1)$ . Since  

$$
\operatorname*{lim}_{\sigma\to0}d_{2}=\operatorname*{lim}_{\sigma\to0}(d_{1}-\sigma{\sqrt{T-t}})=\operatorname*{lim}_{\sigma\to0}d_{1},
$$  

we have  

$$
\operatorname*{lim}_{\sigma\to0}\Phi(d_{2})=\operatorname*{lim}_{\sigma\to0}\Phi(d_{1})={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S_{t}>K e^{-r(T-t)}}\ {{\frac{1}{2}}}&{{\mathrm{if~}}S_{t}=K e^{-r(T-t)}}\ {0}&{{\mathrm{if~}}S_{t}<K e^{-r(T-t)}.}\end{array}\right.}
$$  

Thus  

$$
\begin{array}{r l}&{\underset{\sigma\rightarrow0}{\mathrm{lim}}C_{K}(t,T)=\underset{\sigma\rightarrow0}{\mathrm{lim}}(S_{t}\Phi(d_{1})-K e^{-r(T-t)}\Phi(d_{2}))}\ &{\quad\quad\quad\quad\quad=\left\{\begin{array}{l l}{S_{t}-K e^{-r(T-t)}}&{\mathrm{if~}S_{t}>K e^{-r(T-t)}}\ {0}&{\mathrm{if~}S_{t}=K e^{-r(T-t)}}\ {0}&{\mathrm{if~}S_{t}<K e^{-r(T-t)}.}\end{array}\right.}\ &{\quad\quad\quad=\operatorname*{max}\left\{S_{t}-K Z(t,T),0\right\}}\end{array}
$$  

# 13.5 The Greeks: Delta and Vega  

Definition 13.5.1. The delta of an option (or other derivative contract) is the partial derivative of its price $D(t,T)$ with respect to the stock price. $S_{t}$  

$$
{\mathrm{delta}}={\frac{\partial}{\partial S_{t}}}D(t,T).
$$  

If the delta of a contract is positive, the price of the contract increases as the stock price increases, and the party long on the contract is said to have a long delta position..  

If the delta of a contract is negative, the price of the contract decreases as the stock price increases, and the party long on the contract is said to have a short delta position.  

If the delta of a contract is zero, the price of the contract is unaffected by small changes in the stock price, and both parties have a neutral delta position.  

Result 13.5.1. Assuming the Black-Scholes model for a stock paying no income, the delta of a European call is  

$$
\mathrm{{delta}}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}=\Phi(d_{1}).
$$  

Since $\Phi(d_{1})=P(X\leq d_{1})$ ,where $X\sim N(0,1)$ , Result 13.5.1 implies the delta of a European call satisfies.  

$$
0<\mathrm{delta}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}<1.
$$  

Thus a long call is a long delta position.  

The proof of Result 13.5.1 relies on the following:  

# Lemma 13.5.2.  

$$
S_{t}\Phi^{\prime}(d_{1})=K Z(t,T)\Phi^{\prime}(d_{2})
$$  

Proof of Result 13.5.1. Use the product rule and chain rule to compute  

$$
\begin{array}{l}{\displaystyle\mathrm{delta}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}=\frac{\partial}{\partial S_{t}}\left(S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})\right)}\ {\displaystyle=\Phi(d_{1})+S_{t}\frac{\partial}{\partial S_{t}}\Phi(d_{1})-K Z(t,T)\frac{\partial}{\partial S_{t}}\Phi(d_{2})}\ {\displaystyle=\Phi(d_{1})+S_{t}\Phi^{\prime}(d_{1})\frac{\partial d_{1}}{\partial S_{t}}-K Z(t,T)\Phi^{\prime}(d_{2})\frac{\partial d_{2}}{\partial S_{t}}.}\end{array}
$$  

Note that  

Therefore  

$$
\frac{\partial d_{2}}{\partial S_{t}}=\frac{\partial}{\partial S_{t}}(d_{1}-\sigma\sqrt{T-t})=\frac{\partial d_{1}}{\partial S_{t}}.
$$  

$$
\mathrm{delta}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}=\Phi(d_{1})+\frac{\partial d_{1}}{\partial S_{t}}\left(S_{t}\Phi^{\prime}(d_{1})-K Z(t,T)\Phi^{\prime}(d_{2})\right)
$$  

Lemma 13.5.2 implies the expression in parenthesis is zero, and so the proof is complete.  

Example 13.5.3. The owner (long counterparty) of a European call has a long delta position, and so will profit if the stock price increases..  

The writer (short counterparty) of a European call has a short delta position. Indeed, the delta is  

$$
\frac{\partial}{\partial S_{t}}(-C_{K}(t,T))=-\Phi(d_{1}).
$$  

![](309cedd3a7f90eeb4ea292e44792158f4b2b78edca19e56a6ed8507139d5c46d.jpg)  
Figure 13.1: Black-Scholes delta of 1-year 100-strike call (for different volatilities $\sigma$  

Example 13.5.4 (Delta Hedging). Let $\Delta(s)$ be the delta of a European call when the stock price is $S_{t}=s$  

$$
\Delta(s)=\left.\frac{\partial C_{K}(t,T)}{\partial S_{t}}\right|_{S_{t}=s}.
$$  

For example, assume $K=100,T-t=1,r=10\%$ and $\sigma=20\%$ . Thend  

$$
\begin{array}{l}{{\Delta(90)=\left.{\frac{\partial C_{K}(t,T)}{\partial S_{t}}}\right|_{S_{t}=90}=\Phi(d_{1})|_{S_{t}=90}}}\ {{\qquad=\Phi\left({\frac{\ln\left(S_{t}/K\right)+\left(r+{\frac{1}{2}}\sigma^{2}\right)\left(T-t\right)}{\sigma{\sqrt{T-t}}}}\right)=\Phi\left({\frac{\ln\left(90/100\right)+\left(0.10+{\frac{1}{2}}\left(0.20\right)\right)}{\left(0.20\right)^{2}{\sqrt{1}}}}\right)}}\ {{\qquad=\Phi(0.365987\quad)=0.649813}}\end{array}
$$  

Similarly,  

$$
\Delta(80)=0.00496022.
$$  

Fix a number $s$ .Consider the portfolio consisting of $+1$ European call and short $\Delta(s)$ stocks. The delta of the portfolio is  

$$
\frac{\partial}{\partial S_{t}}(C_{K}(t,T)-\Delta(s)S_{t})=\frac{\partial C_{K}(t,T)}{\partial S_{t}}-\Delta(s)\frac{\partial S_{t}}{\partial S_{t}}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}-\Delta(s).
$$  

Therefore when the stock price is $S_{t}=s$ , the delta is  

$$
\frac{\partial}{\partial S_{t}}(C_{K}(t,T)-\Delta(s)S_{t})\bigg\vert_{S_{t}=s}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}\bigg\vert_{S_{t}=s}-\Delta(s)=0.
$$  

So, when $S_{t}=s$ , the value of the portfolio (consisting of $+1$ European call and short $\Delta(s))$ stocks is unaffected by small changes in the stock price. The portfolio is said to be deltahedged or delta-neutral at $S_{t}=s$ because its delta is zero when $S_{t}=s$ . It has no exposure. to changes in the stock price around $S_{t}=s$  

Similarly, if $D(t,T)$ is the price at $t$ of a derivative contract with maturity $T$ on the stock, then the portfolio consisting of +1 contract and short @D(t,T)] $\left.\frac{\partial D(t,T)}{\partial S_{t}}\right|_{S_{t}=s}$ stocks is delta-hedged at $S_{t}=s$  

Definition 13.5.2. The vega of an option (or other derivative contract) is the partial derivative of its price $D(t,T)$ with respect to volatility $\sigma$  

$$
{\mathrm{vega}}={\frac{\partial}{\partial\sigma}}D(t,T).
$$  

If the vega of a contract is positive, the price of the contract increases as the volatility increases, and the party long on the contract is said to have a long vega position..  

If the vega of a contract is negative, the price of the contract increases as the volatility decreases, and the party long on the contract is said to have a short vega position..  

If the vega of a contract is zero, the price of the contract is unaffected by small changes in the stock price, and both parties have a neutral vega position.  

Result 13.5.5. Assuming the Black-Scholes model for a stock paying no income, the vega of a European call is  

$$
\mathrm{vega}=\frac{\partial C_{K}(t,T)}{\partial\sigma}=S_{t}\sqrt{T-t}\phi(d_{1})=S_{t}\sqrt{T-t}\frac{1}{\sqrt{2\pi}}e^{-d_{1}^{2}/2}.
$$  

where $\phi(x)=\Phi^{\prime}(x)=\frac{1}{2\pi}e^{-x^{2}/2}$ x2/2 is the standard normal pdf.  

The proof of Result 13.5.5 is an exercise for the reader. Since $0<\phi(x)=e^{-x^{2}/2}\leq1$ for all $x$ , Result 13.5.5 implies a European call always has vega $>0$ , so the call price increases as volatility increases.  

![](0ca9ce343545de2d3b1b6995f2e67cf5bc32647ea784e0b6f37c0bb528d05da7.jpg)  
Figure 13.2: Black-Scholes vega of 1-year 100-strike call (for different volatilities)  

The next result shows how the delta (and vega) of a call and a put are related.  

Result 13.5.6. For a stock paying no income,  

$$
\begin{array}{r}{\begin{array}{r l}{(a)\quad}&{{}\displaystyle\frac{\partial C_{K}(t,T)}{\partial S_{t}}-\frac{\partial P_{K}(t,T)}{\partial S_{t}}=1}\ {(b)\quad}&{{}\displaystyle\frac{\partial C_{K}(t,T)}{\partial\sigma}-\frac{\partial P_{K}(t,T)}{\partial\sigma}=0}\end{array}}\end{array}
$$  

Note that Result 13.5.6 does require assuming the Black-Scholes model.  

Proof. Recall that put-call parity states  

$$
C_{K}(t,T)-P_{K}(t,T)=V_{K}(t,T)=S_{t}-K Z(t,T)
$$  

Differentiating with respect to. $S_{t}$ gives (a). Differentiating with respect to $\sigma$ gives (a).  

By combining Results 13.5.1, 13.5.5, and 13.5.6, we obtain  

Result 13.5.7. In the Black-Scholes model for a stock paying no income,  

$$
\frac{\partial P_{K}(t,T)}{\partial S_{t}}=\frac{\partial C_{K}(t,T)}{\partial S_{t}}-1=\Phi(d_{1})-1
$$  

and  

$$
\frac{\partial P_{K}(t,T)}{\partial\sigma}=\frac{\partial C_{K}(t,T)}{\partial\sigma}=S_{t}\sqrt{T-t}\frac{1}{\sqrt{2\pi}}e^{-d_{1}^{2}/2}
$$  

Example 13.5.8. Suppose we are short a $(K_{2},K_{1})$ put spread, where $0~<~K_{1}~<~K_{2}$ Determine whether this position is long vega $\left(\mathrm{vega}\geq0\right)$ , short vega (. $\mathbf{\check{vega}}\leq0\mathbf{\check{,}}$ , has no. volatility exposure $\mathbf{\mathrm{(vega=0)}}$ , or the volatility exposure is indeterminate. Do the same with delta..  

Recall that a. $(K_{2},K_{1})$ put spread is $+1K_{2}$ put and $-1K_{1}$ put. Since we are short the spread, our position is: $-1K_{2}$ put and $+1K_{1}$ put.  

We will need to indicate that $d_{1}$ depends on $K$ . So we write  

$$
d_{1}=d_{1}(K)={\frac{\ln S_{t}-\ln K+(r+{\frac{1}{2}}\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}.
$$  

Let's start with delta.  

$$
\mathrm{delta}=-\frac{\partial P_{K_{2}}(t,T)}{\partial S_{t}}+\frac{\partial P_{K_{1}}(t,T)}{\partial S_{t}}.
$$  

Recall the result from lecture (or lecture notes): $\begin{array}{r}{1=\frac{\partial C_{K}(t,T)}{\partial S_{t}}-\frac{\partial P_{K}(t,T)}{\partial S_{t}}}\end{array}$ oPk(t,T). It comes from put-call parity. Applying it above gives.  

$$
\begin{array}{c}{\displaystyle\mathrm{delta}=-\frac{\partial C_{K_{2}}(t,T)}{\partial S_{t}}+\frac{\partial C_{K_{1}}(t,T)}{\partial S_{t}}}\ {=-\Phi(d_{1}(K_{2}))+\Phi(d_{1}(K_{1})).}\end{array}
$$  

Note $\Phi$ is an increasing function:  

$$
x<y\mathrm{implies}\Phi(x)=\int_{-\infty}^{x}{\frac{1}{\sqrt{2\pi}}}e^{-t^{2}/2}d t<\int_{-\infty}^{y}{\frac{1}{\sqrt{2\pi}}}e^{-t^{2}/2}d t=\Phi(y)
$$  

Since $K_{1}<K_{2}$ , the definition of $d_{1}(K)$ gives $d_{1}(K_{1})>d_{1}(K_{2})$ , hence $\Phi(d_{1}(K_{1}))>$ $\Phi(d_{1}(K_{2}))$ . This gives delta $>0$ . Thus the position is long delta.  

Now vega.  

$$
\mathrm{vega}=-\frac{\partial P_{K_{2}}(t,T)}{\partial\sigma}+\frac{\partial P_{K_{1}}(t,T)}{\partial\sigma}
$$  

Recall the result from lecture (or lecture notes): Cx(,T) $\begin{array}{r}{\frac{\partial C_{K}(t,T)}{\partial\sigma}=\frac{\partial P_{K}(t,T)}{\partial\sigma}}\end{array}$ 3Pk(t,T). It comes from put-call parity. Applying it above gives  

$$
\begin{array}{l}{{\mathrm{vega}=\displaystyle-\frac{\partial C_{K_{2}}(t,T)}{\partial\sigma}+\frac{\partial C_{K_{1}}(t,T)}{\partial\sigma}}}\ {{\mathrm{}=\displaystyle-S_{t}\sqrt{T-t}\frac{1}{\sqrt{2\pi}}e^{-(d_{1}(K_{2}))^{2}/2}+S_{t}\sqrt{T-t}\frac{1}{\sqrt{2\pi}}e^{-(d_{1}(K_{1}))^{2}/2}}}\ {{\mathrm{}=S_{t}\sqrt{T-t}\frac{1}{\sqrt{2\pi}}\left(e^{-(d_{1}(K_{1}))^{2}/2}-e^{-(d_{1}(K_{2}))^{2}/2}\right)}}\end{array}
$$  

For the second line, we used the Result from lecture that the vega of a call and put are equal (which comes immediately from put-call parity). Now we need to compare the sizes of $e^{-(d_{1}(K_{1}))^{2}/2}$ and $e^{-(d_{1}(K_{1}))^{\overline{{2}}}/2}$ . Since $e^{-x^{2}/\bar{2}}$ is decreasing, it suffices to compare $(d_{1}(K_{1}))^{2}$ and $(d_{1}(K_{2}))^{2}$  

We know that. $K_{1}<K_{2}$ , so we have $d_{1}(K_{1})>d_{1}(K_{2})$ . But that's not enough to determine which of $(d_{1}(K_{1}))^{2}$ and $(d_{1}(K_{2}))^{2}$ is largest. For example, if $K_{2}<S_{t}$ , then $d_{1}(K_{2})>0$ is positive, then. $(d_{1}(K_{1}))^{2}>(d_{1}(K_{2}))^{2}$ . On the other hand, if. $K_{2}$ is large enough, then. $d_{1}(K_{2})<-|d_{1}(K_{1})|$ , and so $(d_{1}(K_{2}))^{2}>(d_{1}(K_{1}))^{2}$  

Since we cannot decide which of $(d_{1}(K_{1}))^{2}$ and $(d_{1}(K_{2}))^{2}$ is larger, we cannot say whether vega is positive or negative. Thus the vega of the position is indeterminate. $\triangle$  

We finish this section by proving Lemma 13.5.2.  

Proof of Lemma 13.5.2. First observe that  

$$
\begin{array}{r l}&{\quad\prime(d_{2})=\phi(d_{2})=\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{1}{2}d_{2}^{2}\right)=\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{1}{2}\bigl(d_{1}-\sigma\sqrt{T-t}\bigr)^{2}\right)}\ &{\quad=\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{1}{2}d_{1}^{2}+\sigma\sqrt{T-t}d_{1}-\frac{1}{2}\sigma^{2}(T-t)\right)}\ &{\quad=\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{1}{2}d_{1}^{2}+\sigma\sqrt{T-t}\frac{\ln(S_{t}/K)+\bigl(r+\frac{1}{2}\sigma^{2}\bigr)(T-t)}{\sigma\sqrt{T-t}}-\frac{1}{2}\sigma^{2}(T-t)\right.}\ &{\quad=\left.\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{1}{2}d_{1}^{2}+\ln(S_{t}/K)+r(T-t)\right)}\ &{\quad=\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}d_{t}^{2}}\mathrm{e}^{\ln(S_{t}/K)}e^{r(T-t)}}\ &{\quad=\frac{1}{\sqrt{2\pi}}\frac{S_{t}}{K}e^{r(T-t)}}\end{array}
$$  

It follows that  

$$
K Z(t,T)\Phi^{\prime}(d_{2})=K Z(t,T)\Phi^{\prime}(d_{1})\frac{S_{t}}{K}e^{r(T-t)}=S_{t}\Phi^{\prime}(d_{1}).
$$  

# 13.6 Volatility  

For a stock paying no income, the Black-Scholes model assumes for any $t\leq T$ that  

$$
\ln(S_{T}/S_{t})\sim{\cal N}((r-\frac{1}{2}\sigma^{2})(T-t),\sigma^{2}(T-t)).
$$  

under the risk-neutral measure probability measure $P^{*}$ $r$ is the continuously compounded interest rate, which is assumed to be constant.  

$\sigma$ is a positive constant called the volatility of the stock. Roughly, it measures how much the stock price can be expected to change over time. Large volatility means large changes in the stock price are likely. Small volatility means large changes in the stock price are unlikely.  

Price History of Stock A  

<html><body><table><tr><td>Day</td><td>Stock Price</td></tr><tr><td>0</td><td>100.00</td></tr><tr><td>1</td><td>100.11</td></tr><tr><td>2</td><td>100.50</td></tr><tr><td>3</td><td>100.31</td></tr><tr><td>4</td><td>100.80</td></tr><tr><td>5</td><td>100.79</td></tr><tr><td>6</td><td>100.79</td></tr><tr><td>7</td><td>102.43</td></tr><tr><td>8</td><td>103.50</td></tr><tr><td>9</td><td>102.88</td></tr><tr><td>10</td><td>102.66</td></tr><tr><td>11</td><td>102.80</td></tr><tr><td>12</td><td>101.60</td></tr><tr><td>13</td><td>101.95</td></tr><tr><td>14</td><td>101.90</td></tr><tr><td>15</td><td>101.75</td></tr><tr><td>16</td><td>101.56</td></tr><tr><td>17</td><td>101.46</td></tr><tr><td>18</td><td>101.54</td></tr><tr><td>19</td><td>101.48</td></tr><tr><td>20</td><td>102.69</td></tr><tr><td>21</td><td>102.06</td></tr><tr><td>22</td><td>102.89</td></tr><tr><td>23</td><td>102.83</td></tr><tr><td>24</td><td>103.67</td></tr><tr><td>25</td><td>103.53</td></tr><tr><td>26</td><td>102.46</td></tr><tr><td>27</td><td>104.81</td></tr><tr><td>28</td><td>105.49</td></tr><tr><td>29</td><td>107.15</td></tr><tr><td>30</td><td>109.21</td></tr></table></body></html>  

![](9992613084455849d0ac167cc085c27aec63d7c25ef075330828479efae4973e.jpg)  

# Price History of Stock B  

<html><body><table><tr><td>Day</td><td>Stock Price</td></tr><tr><td>0</td><td>100.00</td></tr><tr><td>1</td><td>99.99</td></tr><tr><td>2</td><td>99.43</td></tr><tr><td>3</td><td>100.05</td></tr><tr><td>4</td><td>97.37</td></tr><tr><td>5</td><td>94.67</td></tr><tr><td>6</td><td>93.65</td></tr><tr><td>7</td><td>92.45</td></tr><tr><td>8</td><td>95.08</td></tr><tr><td>9</td><td>93.80</td></tr><tr><td>10</td><td>88.43</td></tr><tr><td>11</td><td>89.35</td></tr><tr><td>12</td><td>92.67</td></tr><tr><td>13</td><td>96.52</td></tr><tr><td>14</td><td>97.41</td></tr><tr><td>15</td><td>94.24</td></tr><tr><td>16</td><td>92.71</td></tr><tr><td>17</td><td>91.43</td></tr><tr><td>18</td><td>92.42</td></tr><tr><td>19</td><td>92.83</td></tr><tr><td>20</td><td>90.25</td></tr><tr><td>21</td><td>93.25</td></tr><tr><td>22</td><td>92.35</td></tr><tr><td>23</td><td>96.55</td></tr><tr><td>24</td><td>101.59</td></tr><tr><td>25</td><td>103.00</td></tr><tr><td>26</td><td>103.57</td></tr><tr><td>27</td><td>103.27</td></tr><tr><td>28</td><td>100.97</td></tr><tr><td>29</td><td>101.30</td></tr><tr><td>30</td><td>107.34</td></tr></table></body></html>  

![](665d8862ba023c4b8c4f35a367a4d15e2222eda5d85bad32c525befcb758b3a4.jpg)  

Based on the graphs, it looks like stock B has higher volatility than stock A.  

We now explain how to estimate the volatility of stocks A and B based on the data above.  

# Some Theory.  

Assuming the Black-Scholes model for the stock, we have, for any times $t<T$  

$$
\ln(S_{T}/S_{t})\sim{\cal N}\left(\left(r-\frac{1}{2}\sigma^{2}\right)(T-t),\sigma^{2}(T-t)\right).
$$  

Let $S_{i\Delta T}$ be the stock price on day $i$ , where $\Delta T=1/365$ years $=1$ day. Define  

$$
X_{i}=\ln(S_{i\Delta T}/S_{(i-1)\Delta T}).
$$  

Then  

$$
X_{i}=\ln(S_{i\Delta T}/S_{(i-1)\Delta T})=\ln(S_{i\Delta T})-\ln(S_{(i-1)\Delta T})\sim{\mathcal{N}}\left((r-{\frac{1}{2}}\sigma^{2})\Delta T,\sigma^{2}\Delta T.\right)
$$  

Therefore  

$$
\sigma^{2}\Delta T=\mathrm{Var}^{*}\left(X_{i}\right).
$$  

# Procedure to Estimate $\sigma$ From Data.  

We compute $X_{i}=\ln(S_{i\Delta T}/S_{(i-1)\Delta T})$ for day $i=1,\ldots,n=30.$  

We compute the sample variance of the data points $X_{1},\ldots,X_{n}$  

$$
s_{n}^{2}={\frac{1}{n-1}}\sum_{i=1}^{n}(X_{i}-{\overline{{X}}})^{2}\quad{\mathrm{~where~}}\quad{\overline{{X}}}={\frac{1}{n}}\sum_{i=1}^{n}X_{i}.
$$  

Then  

$$
s_{n}^{2}\approx\mathrm{Var}^{*}\left(X_{i}\right)=\sigma^{2}\Delta T.
$$  

Therefore  

$$
\sigma\approx\sqrt{\frac{1}{\Delta T}s_{n}^{2}}
$$  

Remark. We can use a spreadsheet to do the calculations. In Excel and Google Sheets, VARO computes the sample variance of a set of data points..  

Example 13.6.1 (Estimating the Volatility). We use a spreadsheet to estimate the volatility of stocks A and B according to the procedure described above. You can find a sample spreadsheet on the course website.  

Stock A   
Stock B   


<html><body><table><tr><td>Day</td><td>Stock Price</td><td>Si△T ln</td><td>S(i-1)△T</td><td>Day</td><td>Stock Price</td><td>Si△T In</td></tr><tr><td>0</td><td>100.00</td><td></td><td></td><td>0</td><td>100.00</td><td>S(i-1)△T</td></tr><tr><td>1</td><td>100.11</td><td>0.001058</td><td></td><td>1</td><td>99.99</td><td>-0.000053</td></tr><tr><td>2</td><td>100.50</td><td>0.003958</td><td></td><td>2</td><td>99.43</td><td>-0.005705</td></tr><tr><td>3</td><td>100.31</td><td>-0.001968</td><td></td><td>3</td><td>100.05</td><td>0.006300</td></tr><tr><td>4</td><td>100.80</td><td>0.004884</td><td></td><td>4</td><td>97.37</td><td>-0.027170</td></tr><tr><td>5</td><td>100.79</td><td>-0.000050</td><td></td><td>5</td><td>94.67</td><td>-0.028109</td></tr><tr><td>6</td><td>100.79</td><td>0.000027</td><td></td><td>6</td><td>93.65</td><td>-0.010864</td></tr><tr><td>7</td><td>102.43</td><td>0.016101</td><td></td><td>7</td><td>92.45</td><td>-0.012910</td></tr><tr><td>8</td><td>103.50</td><td>0.010389</td><td></td><td>8</td><td>95.08</td><td>0.028077</td></tr><tr><td>６</td><td>102.88</td><td>-0.006053</td><td></td><td>６</td><td>93.80</td><td>-0.013594</td></tr><tr><td>10</td><td>102.66</td><td>-0.002059</td><td></td><td>10</td><td>88.43</td><td>-0.058895</td></tr><tr><td>11</td><td>102.80</td><td>0.001347</td><td></td><td>11</td><td>89.35</td><td>0.010312</td></tr><tr><td>12</td><td>101.60</td><td>-0.011804</td><td></td><td>12</td><td>92.67</td><td>0.036433</td></tr><tr><td>13</td><td>101.95</td><td>0.003454</td><td></td><td>13</td><td>96.52</td><td>0.040808</td></tr><tr><td>14</td><td>101.90</td><td>-0.000480</td><td></td><td>14</td><td>97.41</td><td>0.009134</td></tr><tr><td>15</td><td>101.75</td><td>-0.001444</td><td></td><td>15</td><td>94.24</td><td>-0.033096</td></tr><tr><td>16</td><td>101.56</td><td>-0.001891</td><td></td><td>16</td><td>92.71</td><td>-0.016330</td></tr><tr><td>17</td><td>101.46</td><td>-0.000995</td><td></td><td>17</td><td>91.43</td><td>-0.013951</td></tr><tr><td>18</td><td>101.54</td><td>0.000788</td><td></td><td>18</td><td>92.42</td><td>0.010781</td></tr><tr><td>19</td><td>101.48</td><td>-0.000588</td><td></td><td>19</td><td>92.83</td><td>0.004450</td></tr><tr><td>20</td><td>102.69</td><td>0.011868</td><td></td><td>20</td><td>90.25</td><td>-0.028251</td></tr><tr><td>21</td><td>102.06</td><td>-0.006163</td><td></td><td>21</td><td>93.25</td><td>0.032770</td></tr><tr><td>22</td><td>102.89</td><td>0.008077</td><td></td><td>22</td><td>92.35</td><td>-0.009707</td></tr><tr><td>23</td><td>102.83</td><td>-0.000548</td><td></td><td>23</td><td>96.55</td><td>0.044447</td></tr><tr><td>24</td><td>103.67</td><td>0.008119</td><td></td><td>24</td><td>101.59</td><td>0.050907</td></tr><tr><td>25</td><td>103.53</td><td>-0.001372</td><td></td><td>25</td><td>103.00</td><td>0.013816</td></tr><tr><td>26</td><td>102.46</td><td>-0.010321</td><td></td><td>26</td><td>103.57</td><td>0.005456</td></tr><tr><td>27</td><td>104.81</td><td>0.022598</td><td></td><td>27</td><td>103.27</td><td>-0.002878</td></tr><tr><td>28</td><td>105.49</td><td>0.006494</td><td></td><td>28</td><td>100.97</td><td>-0.022518</td></tr><tr><td>29</td><td>107.15</td><td>0.015586</td><td></td><td>29</td><td>101.30</td><td>0.003265</td></tr><tr><td>30</td><td>109.21</td><td>0.019046</td><td></td><td>30</td><td>107.34</td><td>0.057947</td></tr><tr><td></td><td>Sample Variance =</td><td>0.000066628</td><td></td><td></td><td>Sample Variance =</td><td>0.00074733</td></tr><tr><td></td><td>Volatility = o ≈</td><td>0.1559</td><td></td><td></td><td>Volatility = o ~</td><td>0.5222</td></tr></table></body></html>  

From the data, we estimate the volatility as  

Stock A: $\sigma=15.59\%$ Stock B: $\sigma=52.22\%$  

In fact, the price data was generated with  

Stock A: $\sigma=15\%$ Stock B: $\sigma=50\%$  

Our estimates are pretty good considering we only had 30 data points.  

Example 13.6.2 (Option Pricing With Estimated Volatility). Assume the constant continuously compounded interest rate is $10\%$ . Use the volatility estimates  

Stock A: $\sigma=15.59\%$ Stock B: $\sigma=52.22\%$  

to find call prices for two-year 100-strike European calls on stocks A and B. The current time is Day 30.  

The Black-Scholes formula is  

$$
C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2}).
$$  

Stock A:  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}}}\ {{\quad=\displaystyle\frac{\ln(109.21/100)+(0.10+\frac{1}{2}(0.1559)^{2})(2)}{(0.1559)\sqrt{2}}}}\ {{\quad=1.41697\ldots}}\end{array}
$$  

$$
\begin{array}{l}{d_{2}=d_{1}-\sigma\sqrt{T-t}}\ {=(1.41697\ldots)-(0.1559)\sqrt{2}}\ {=1.19649\ldots}\end{array}
$$  

$$
Z(t,T)=e^{-0.10(2)}
$$  

Therefore  

$$
\begin{array}{r l}&{C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})}\ &{\qquad=109.21\Phi(1.41697\dots)-100e^{-0.10(2)}\Phi(1.19649\dots)}\ &{\qquad=28.26\dots}\end{array}
$$  

Stock B:  

$$
\begin{array}{l}{{d_{1}=\frac{{\ln(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}}{{\sigma\sqrt{T-t}}}}}\ {{=\frac{{\ln(107.64/100)+(0.10+\frac{1}{2}(0.5222)^{2})(2)}}{{0.5222\sqrt{2}}}}}\ {{=0.739761...}}\end{array}
$$  

$$
\begin{array}{l}{d_{2}=d_{1}-\sigma\sqrt{T-t}}\ {=(0.739761\ldots)-(0.15)\sqrt{1.5}}\ {=0.00125836\ldots}\end{array}
$$  

$$
Z(t,T)=e^{-0.10(2)}
$$  

Therefore  

$$
\begin{array}{l}{{C_{K}(t,T)=S_{t}\Phi(d_{1})-K Z(t,T)\Phi(d_{2})\nonumber}}\ {{\nonumber=107.64\Phi(0.739761\ldots)-100e^{-0.10(2)}\Phi(0.00125836\ldots)\nonumber}}\ {{\nonumber=41.93\ldots}}\end{array}
$$  

# Bibliography  

[1] S. Blyth, An Introduction to Quantitative Finance, 1 ed., 2014.   
[2] M. Capinski, T. Zastawniak, Mathematics for Finance: An Introduction to Financial Engineering, 2 ed., 2011.   
[3] D. J. Higham, An Introduction to Financial Option Evaluation: Mathematics, Stochastics and Computation, 1 ed., 2004. Kyle Hambrook   
Department of Mathematics, University of Rochester, Rochester, NY, 14627 USA khambroo@ur.rochester.edu.  