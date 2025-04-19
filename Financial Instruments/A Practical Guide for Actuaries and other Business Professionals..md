---
tags:
  - annuities
  - bond_valuation
  - duration_convexity
  - financial_instruments
  - financial_mathematics
  - interest_rates
  - term_structure
aliases:
  - Actuarial Guide
  - Business Professionals
  - Financial Math
key_concepts:
  - Bond valuation
  - Duration, convexity, immunization
  - Financial instruments
  - Interest rates and factors
  - Level annuities
  - Project appraisal and loans
  - Varying annuities
---

# FINANCIAL MATHEMATICS

# A Practical Guide for Actuaries and other Business Professionals.

### Contents

Table of Contents
Interest Rates and Factors
1.1 Interest
1.2 Simple Interest
1.3 Compound Interest
1.4 Accumulated Value
1.5 Present Value
1.6 Rate of Discount
1.7 Constant Force of Interest
1.8 Varying Force of Interest
1.9 Discrete Changes in Interest Rates
Exercises and Solutions
Level Annuities
2.1 Annuity-Immediate
2.2 Annuity-Due
2.3 Deferred Annuities
2.4 Continuously Payable Annuities
2.5 Perpetuities
2.6 Equations of Value
Exercises and Solutions
Varying Annuities
3.1 Increasing Annuity-Immediate
3.2 Increasing Annuity-Due
3.3 Decreasing Annuity-Immediate
3.4 Decreasing Annuity-Due
3.5 Continuously Payable Varying Annuities
3.6 Compound Increasing Annuities
3.7 Continuously Varying Payment Streams
3.8 Continuously Increasing Annuities
3.9 Continuously Decreasing Annuities
Exercises and Solutions
Non-Annual Interest Rate and Annuities
4.1 Non-Annual Interest and Discount Rates
4.2 Nominal $p^{thly}$ Interest Rates: $I^{(p)}$
4.3 Nominal $p^{thly}$ Discount Rates: $d^{(p)}$
4.4 Annuities-Immediate Payable $p^{thly}$
4.5 Annuities-Due Payable $p^{thly}$
Exercises and Solutions
Project Appraisal and Loans
5.1 Discounted Cash Flow Analysis
5.2 Nominal vs. Real Interest Rates
5.3 Investment Funds
5.4 Allocating Investment Income
5.5 Loans: The Amortization Method
5.6 Loans: The Sinking Fund Method
Financial Instruments
6.1 Types of Financial Instruments
6.1.1 Money Market Instruments
6.1.2 Bonds
6.1.3 Common Stock
6.1.4 Preferred Stock
6.1.5 Mutual Funds
6.1.6 Guaranteed Investment Contracts (GIC)
6.1.7 Derivative Securities
6.2 Bond Valuation
6.3 Stock Valuation
Exercises and Solutions
Duration, Convexity, and Immunization
7.1 Price as a Function of Yield
7.2 Modified Duration
7.3 Macaulay Duration
7.4 Effective Duration
7.5 Convexity
7.5.1 Macaulay Convexity
7.5.2 Effective Convexity
7.6 Duration, Convexity, and Prices: Putting It All Together
7.6.1 Revisiting the Percentage Change in Price
7.6.2 The Passage of Time and Duration
7.6.3 Portfolio Duration and Convexity
7.7 Immunization
7.8 Full Immunization
Exercises and Solutions
The Term Structure of Interest Rates
8.1 Yield-to-Maturity
8.2 Spot Rates

## 1 Interest Rates and Factors

## Overview

-interest is the payment made by a borrower (i.e. the cost of doing business) for using a lender’s capital assets (usually money); an example is a loan transaction —interest rate is the percentage of interest to the capital asset in question interest takes into account the risk of default (risk that the borrower can't pay back the loan the risk of default can be reduced if the borrower promises to release an asset of theirs in the event of their default (the asset is called collateral

# 1.1 Interest

### Interest on Savings Accounts

 A bank borrows a depositor's money and pays them interest for the use of their money the greater the need for money, the greater the interest rate offered

Interest Earned During the Period $t$ to $t+s$ ： $AV_{t+s}-AV_{t}$

-the Accumulated Value at time TL is denoted as AV, — interest earned during a period of time is the diference between the Accumulated Value at the end of the period and the Accumulated Value at the beginning of the period

### The Effective Rate of Interest

— $i$ is the amount of interest earned over a one-year period when 1 is invested - $i$ is also defined as the ratio of the amount of Interest Earned during the period to the Accumulated Value at the beginning of the period

$$i=\frac{AV_{t+1}-AV_{t}}{AV_{t}}$$

### Interest on Loans

- Compensation a borrower of capital pays to a lender of capital lender has to be compensated since they have temporarily lost use of their capital interest and capital are almost always expressed in terms of money
## 1.2 Simple Interest

let the interest amount earned each year on an investment of $X$ be constant where the annua rate of interest is $\dot{i}$
$$AV_t=X(1+ti),$$

where $(1+ti)$ is a linear function

simple interest has the property that interest is NOT reinvested to earn additional interest amount of Interest Earned to time $t$ is

$$I=AV_t-AV_0=X(1+it)-X=X\cdot it$$

## 1.3 Compound Interest

— let the interest amount earned each year on an investment of $X$ also allow the interest earned to earn interest where the annual rate of interest is 2

$$AV_t=X(1+i)^t,$$

where $(1+i)^{l}$ is an exponential function

 compound interest produces larger accumulations than simple interest when $t>1$

Note that a constant rate of compound interest implies a constant effective rate of interest

## 1.4 Accumulated Value

Accumulated Value Factor: $AVF_{t}$

- assume that $AV_{t}$ is continuously increasing

-let $X$ be the initial Principal invested ( $X>0$ ) where $AV_{0}=X$

— $AV_{t}$ defines the Accumulated Value that amount $X$ grows to in $t$ years

the Accumulated Value at time $t$ is the product of the initial capital investment of $X$ (Prin cipal) made at time zero and the Accumulation Value Factor:

$$AV_t=X\cdot AVF_t,$$

where $AVF_{t}=(1+it)$ if simple interest is being applied and $AVF_{t}=(1+i)^{t}$ if compouno interest is being applied
### 1.5 Present Value

### Discounting

Accumulated Value is a future value pertaining to payment (s) made in the past Discounted Value is a present value pertaining to payment (s) to be made in the future discounting determines how much must be invested initially Z $Z$ $(Z)$ so that $X$ will be accumu lated after $t$ years
$$Z\cdot(1+i)^t=X\to\:Z=\frac{X}{(1+i)^t}=X(1+i)^{-t}$$

一 $Z$ represents the present value of $X$ to be paid in $t$ years

let $v={\frac{1}{1+i}}$ $U$ is called a discoumt factor or present value faetor

$$Z=X\cdot v^{t}$$

### Discount Function (Present Value Factor) $PVF_{t}$

- simpl interest $PVF_{t}=\frac{1}{1+it}$

- compound interest: $PVF_{t}={\frac{1}{\left(1+i\right)^{t}}}=v^{t}$

compound interest produces smaller Discount Values than simple interest when $t>1$
## 1.6 Rate of Discount: $d$

### Definition

 An effective rate of interest is taken as a percentage of the balance at the beginning of the year, while an effective rate of discount is at the end of the year.

-eg. If 1 is invested and $6\%$ interest is paid at the end of the year, then the Accumulatec Value is 1.06

-eg. If 0.94 is invested after a $6\%$ discount is paid at the beginning of the year, then the Accumulated Value at the end of the year is 1.00

- $d$ is also defined as the ratio of the amount of interest (amount of discount) earned during the period to the amount invested at the end of the period

$$d=\frac{AV_{t+1}-AV_{t}}{AV_{t+1}}$$

-if interest is constant. Then discount is constanf

the amount of discount earned from time $t$ to $t+s$ is $AV_{t+s}-AV_{t}$

## Relationships Between $i$ and $d$

if 1 is borrowed and interest is paid at the beginning of the year, then $1-d$ remains

-the accumulated value of $1-d$ at the end of the year is 1：

$$(1-d)(1+i)=1$$

Interest rate is the ratio of the discount paid to the amount at the beginning of the period

$$i=\frac{d}{1-d}$$

Discount rate is the ratio of the interest paid to the amount at the end of the period：

$$d=\frac{i}{1+i}$$

 The present value of end-of-year interest is the discount paid at the beginning of the yea 1

$$iv=d$$

- the present value of 1 to be paid at the end of the year is the same as borrowing $1-d$ and repaying 1 at the end of the year (if both have the same value at the end of the year, ther they have to have the same value at the beginning of the year

$$1\cdot v=1-d$$

 the difference between end-of-year, $i$ , and beginning-of-year interest, $d$ , depends on the differ ence that is borrowed at the beginning of the year and the interest earned on that difference

$$i-d=i[1-(1-d)]=i\cdot d\geq0$$
## Discount Factors: $PVF_{t}$ and $AVF_{t}$

-under the simple discount model the Discount Present Value Factor is

$$PVF_{t}=1-dt\quad\mathrm{for}\:0\leq t<1/d$$

-under the simple discount model the Discount Accumulated Value Factor is:

$$AVF_t=(1-dt)^{-1}\quad\mathrm{for}\:0\leq t<1/d$$

Under the compound discount model, the Discount Present Value Factor is:

$$PVF_t=\left(1-d\right)^t=v^t\quad\mathrm{for}\:t\geq0$$

-under the compound discount model, the Discount Accumulated Value Factor is:

$$AVF_t=\left(1-d\right)^{-t}\quad\mathrm{for}\:t\geq0$$

A constant rate of simple discount implies an increasing effective rate of discounf a constant rate of compound discount implies a constant effective rate of discount
## 1.7 Constant Force of Interest:

### Definitions

Annual effective rate of interest is applied over a one-year period

-a constant annual force of interest can be applied over the smallest sub-period imaginable (at a moment in time) and is denoted as $\delta$

-an instantaneous change at time $t$ due to interest rate $\delta$ ,where the accumulated value at time $t$ is $X$ ,can be defined as follows

$$\begin{aligned}
&\text{6} =\frac{\frac{d}{dt}AV_{t}}{AV_{t}}  \\
&=\frac{d}{dt}ln(AV_{t}) \\
&=\frac{\frac{d}{dt}X(1+i)^{t}}{X(1+i)^{t}} \\
&=\frac{(1+i)^{t}\cdot ln(1+i)}{(1+i)^{t}} \\
&\text{.} \delta=ln(1+i)
\end{aligned}$$

-taking the exponential function of $\delta$ results in

$$e^\delta=1+i$$

Taking the inverse of the above formula results in

$$e^{-\delta}=\frac{1}{1+i}=v$$

Accumulated Value Factor ( $AVF_{t}$ using constant force of interest is

$$AVF_t=e^{\delta t}$$

Present Value Factor $\langle PVF_{t}\rangle$ using constant force of interest is

$$PVF_t=e^{-\delta t}$$
### 1.8 Varying Force of Interest

let the constant force of interest $\delta$ now vary at each infitesimal point in time and be denoted as $\delta_{t}$

- a change from time $t_{1}$ to $t_{2}$ , due to interest rate $\delta_{t}$ , where the accumulated value at time $t_{1}$ is $X$ ,can be defined as follows:

$$\begin{aligned}
&##### \\
&&& \delta_{t}=\frac{\frac{d}{dt}AV_{t}}{AV_{t}} \\
&&&=\frac{d}{dt}ln(AV_{t}) \\
&\int_{t_{1}}^{t_{2}}\delta_{t}\cdot dt=&& \int_{t_{1}}^{t_{2}}\frac{d}{dt}ln(AV_{t})\cdot dt \\
&&&=ln(AV_{t_{2}})-ln(AV_{t_{1}}) \\
&\int_{t_{1}}^{t_{2}}\delta_{t}\cdot dt=&& ln\left({\frac{AV_{t_{2}}}{AV_{t_{1}}}}\right) \\
&e^{\int_{t_{1}}^{t_{2}}\delta_{t}\cdot dt}=&& \frac{AV_{t_{2}}}{AV_{t_{1}}}
\end{aligned}$$

Varying Force of Interest Accumulation Factor - $AVF_{t_{1},t_{2}}$

-let

$$AVF_{t_1,t_2}=e^{\int_{t_1}^{t_2}\delta_t\cdot dt}$$

represent an accumulation factor over the period $t_{1}$ to $t_{2}$ , where the force of interest is varying

-i $t_{1}=0$ I theath otatoasinpife roe $AVF_{0,t_{2}}$ to $AVF_{t}$ i.e. $AVF_{t}=e^{\int_{0}^{t}\delta_{t}\cdot dt}$ -if $\delta_{t}$ is readily integrable, then $AVF_{t_{1},t_{2}}$ can be derived easily -if $\delta_{t}$ is not readily integrable, then approximate methods of integration are required

### Varying Force of Interest Present Value Factor - $PVF_{t_{1},t_{2}}$

-let

$$PVF_{t_{1},t_{2}}=\frac{1}{AVF_{t_{1},t_{2}}}=\frac{1}{e^{\int_{t_{1}}^{t_{2}}\delta_{t}\cdot dt}}=\frac{AV_{t_{1}}}{AV_{t_{2}}}=e^{-\int_{t_{1}}^{t_{2}}\delta_{t}\cdot dt}$$

represent a present value factor over the period $t_{1}$ to $t_{2}$ ,where the force of interest is varying -证 $t_{1}=0$ te le oato sieie fore $PVF_{0,t_{2}}$ to $PVF_{t}$ ie. $PVF_{t}=e^{-\int_{0}^{t}\delta_{t}\cdot dt}$
## 1.9 Discrete Changes in Interest Rates

the most common application of the accumulation and present value factors over a period of $t$ years is
$$AVF_t=\prod_{k=1}^t(1+i_k)$$

And

$$PFV_t=\prod\limits_{k=1}^t\frac{1}{(1+i_k)}$$

where $l_k$ is the constant rate of interest between time $k-1$ and time $k$
### Exercises and Solutions

### 1.2 Simple Interest

### Exercise (a)

At what rate of simple interest will 500 accumulate to 615 in 2.5 years?

Solution (a)

$$\begin{gathered}
500[1+i(2.5)]=615 \\
i={\frac{\frac{615}{500}-1}{2.5}}=9.2\%
\end{gathered}$$

Exercise (b)

In how many years will 500 accumulate to 630 at $7.8\%$ simple interest?

Solution (b)

$$500[1+0.1(n)]=630$$

$$i=\frac{\frac{630}{500}-1}{0.1}=3.33\mathrm{~years}$$

Exercise (c)

At a certain rate of simple interest 1,000 will accumulate to 1,100 after a certain period of time. Find the accumulated value of 500 at a rate of simple interest three fourths as great over twice as long a period of time.

Solution (c)

$$1,000[1+i\cdot n]=1,100\to i\cdot n=0.1$$

$$500[1+\frac{3}{4}i\cdot2n]=500[1+(1.5)(0.1)]=582.50$$

### Exercise (d)

Simple interest of $i=4\%$ is being credited to a fund. In which period is this equivalent to an effective rate of $2.5\%$

Solution (d)

$$i_n=\frac{i}{1+i(n-1)}$$

$$0.25=\frac{0.1}{1+0.1(n-1)}\to n=16$$
## Exercise (a)

Fund $A$ is invested at an effective annual interest rate of $3\%$ .Fund $B$ is invested at an effective annual interest rate of $2.5\%$ .At the end of 20 years, the total in the two funds is 10,000. At the end of 31 years, the amount in Fund $A$ is twice the amount in Fund $B$ Calculate the total in the two funds at the end of 10 years.

# Solution (a)

Let the initial funds be $A$ and $B$ Therefore, we have two equations and two unknowns

$$A(1.03)^{20}+B(1.025)^{20}=10,000$$

$$A(1.03)^{31}=2B(1.025)^{31}$$

Solving for $B$ in the second equation and plugging it into the first equation gives us $A=$ 3,624.73 and $B=2,107.46$ .We seek $A(1.03)^{10}+B(1.025)^{10}$ which equals

$$3,624.73(1.03)^{10}+2,107.46(1.025)^{10}=7,569.07$$

## Exercise (b)

Carl puts 10,000 into a bank account that pays an annual effective interest rate of $4\%$ for ten years. If a withdrawal is made during the first five and one-half years, a penalty of $5\%$ of the withdrawal amount is made. Carl withdrawals $K$ at the end of each of years 4, 5, 6, 7. The balance in the account at the end of year 10 is 10,000. Calculate $K$

## Solution (b)

$$10,000(1.04)^{10}-1.05K(1.04)^6-1.05K(1.04)^5-K(1.04)^4-K(1.04)^3=10,000$$

$$14,802-K[(1.05)(1.04)^6+(1.05)(1.04)^5+(1.04)^4+(1.04)^3]=10,000$$

$$4,802=K\cdot4.9\to K=980$$
## 1.4 Accumulated Value

### Exercise (a)

100 is deposited into an account at the beginning of every 4-year period for 40 years

The account credits interest at an annual effective rate of $\dot{i}$

The accumulated value in the account at the end of 40 years is $X$ ，which is 5 times the accumulated amount at the end of 20 years. Calculate $X$

## Solution (a)

$$100(1+i)^4+100(1+i)^8+...+100(1+i)^{40}=X=5[100(1+i)^4+100(1+i)^8+...+100(1+i)^{20}]$$

$$100(1+i)^4[1+100(1+i)^4+...+100(1+i)^{36}]=5\cdot100(1+i)^4[1+100(1+i)^4+...+100(1+i)^{16}]$$

$$100(1+i)^4\left[\frac{1-[(1+i)^4]^{10}}{1-(1+i)^4}\right]=5\cdot100(1+i)^4\left[\frac{1-[(1+i)^4]^5}{1-(1+i)^4}\right]$$

$$1-(1+i)^{40}=5[1-(1+i)^{20}]$$

$$(1+i)^{40}-5(1+i)^{20}+4=0\to[(1+i)^{20}-1][(1+i)^{20}-4]=0\to(1+i)^{20}=1$$

$(1+i)^{20}=1\to i=0\%\to AV_{40}=1000$ and $AV_{20}=500$ , impossible since $AV_{40}=5AV_{20}$ therefore, $(1+i)^{20}=4$

$$X=100(1+i)^4\left[\frac{1-(1+i)^{40}}{1-(1+i)^4}\right]=100(4^{\frac{1}{5}})\left[\frac{1-4^2}{1-4^{\frac{1}{5}}}\right]=100(61.9472)=6194.72$$
### Exercise (a)

Annual payments are made at the end of each year, forever. The payments at time TL is defined as $n^{3}$ for the first $7t$ years. After year $TL$ ，the payments remain constant at $n^{2}$ .The present value of these payments at time 0 is $20n^{2}$ when the annual effective rate of interest is $0\%$ for thefirst $7t$ years and $25\%$ thereafter. Calculate 72

### Solution (a)

$$[(1^3)v_{0\%}+(2^3)v_{0\%}^2+(3^3)v_{0\%}^3+...+(n^3)v_{0\%}^n]+v_{0\%}^n[(n^2)v_{25\%}^1+(n^2)v_{25\%}^2+(n^2)v_{25\%}^3+...]=20n^2$$

$$[(1^3)+(2^3)+(3^3)+...+(n^3)]+(n^2)v_{25\%}[1+v_{25\%}^1+v_{25\%}^2+...]=20n^2$$

$$\left[\frac{n^2(n+1)^2}{4}\right]+(n^2)v_{25\%}\left[\frac{1}{1-v_{25\%}}\right]=20n^2$$

$$\left[\frac{(n+1)^2}{4}\right]+(0.1)\left[\frac{1}{1-0.1}\right]=20$$

$$\begin{bmatrix}\frac{(n+1)^2}{4}\end{bmatrix}+4=20\to\frac{(n+1)^2}{4}=16\to\frac{(n+1)}{2}=4\to n=7$$

Exercise (b)

At an effective annual interest rate of $\dot{\boldsymbol{z}}$ $i>0$ , each of the following two sets of payments has present value $K$

(i) A payment of 121 immediately and another payment of 121 at the end of one year.

(ii) A payment of 144 at the end of two years and another payment of 144 at the end of three years.

Calculate $K$

### Solution (b)

$$121+121v=144v^2+144v^3=K$$

$$121(1+v)=144v^2(1+v)\to v=\frac{11}{12}$$

$$K=121(1+\frac{11}{12})\to K=231.92$$
### Exercise (c)

The present value of a series of payments of 2 at the end of every eight years, forever, is equal to 5. Calculate the effective rate of interest.

Solution (c)

$$2v^8+2v^{16}+2v^{24}+...=5$$

$$2v^8[1+v^8+v^{16}+...=5$$

$$2v^8\left[\frac{1}{1-v^8}\right]=5$$

$$2v^8=5-5v^8$$

$$7v^{8}=5$$

$$v^8=\frac{5}{7}$$

$$(1+i)^8=\frac{7}{5}$$

$$1+i=\left(\frac{7}{5}\right)^{\frac{1}{8}}\to i=0.1$$

### 1.6 Rate of Discount

Exercise (a)

A business permits its customers to pay with a credit card or to receive a percentage discount of 7 for paying cash.

For credit card purchases, the business receives $97\%$ of the purchase price one-half month later.

At an annual effective rate of discount of $22\%$ ,the two payments are equivalent. Find 7

### Solution (a)

$$\$1(1-r)=\$0.97v^{\frac{1}{12}*\frac{1}{2}}=\$0.97v^{\frac{1}{24}}$$

$$(1-r)=0.1(1-d)^{\frac{1}{24}}=0.1(1-0.1)^{\frac{1}{24}}=0.1$$

$$r=0.1=4\%$$
### Exercise (b）

You deposit 1,000 today and another 2,000 in five years into a fund that pays simple discounting at $5\%$ per year.

Your friend makes the same deposits into another fund, but at time 72 and $2n$ , respectively. This fund credits interest at an annual effective rate of $10\%$

At the end of 10 years, the accumulated value of your deposits is exactly the same as the accumulated value of your friend’s deposits

Calculate $7t$

Solution (b)

$$1,000[1-5\%(10)]^{-1}+2,000[1-5\%(5)]^{-1}=1,000(1.10)^{10-n}+2,000(1.10)^{10-2n}$$

$$\frac{1,000}{0.1}+\frac{2,000}{0.1}=1,000(1.10)^{10}v^n+2,000(1.10)^{10}v^{2n}$$

$$4,666.67=2,593.74v^n+5,187.48v^{2n}\to\underbrace{5,187.48}_{a}v^{2n}+\underbrace{2,593.74}_{b}v^n\underbrace{-4,666.67}_{c}=0$$

$$v^n=\frac{-2,593.74+\sqrt{2,593.74^2-4(5,187.48)(-4,666.67)}}{2(5,187.48)}=0.1$$

$$(1.10)^n=\frac{1}{0.1}=1.36824\to n=\frac{ln(1.36824)}{ln(1.10)}=3.29$$

### Exercise (c)

A deposit of X is made into a fund which pays an annual effective interest rate of $6\%$ for 10 years.

At the same time , $X/2$ is deposited into another fund which pays an annual effective rate of discount of $d$ for 10 years

The amounts of interest earned over the 10 years are equal for both funds.

Calculate d.

## Solution (c)

$$X(1.06)^{10}-X=\frac{X}{2}(1-d)^{-10}-\frac{X}{2}$$

$$d=0.0905$$
### Exercise (a)

You are given that $AV_{t}=Kt^{2}+Lt+M$ ，for $0\leq t\leq2$ and that $AV_{0}=100$ ， $AV_{1}=110$ and $AV_{2}=136$ .Determine the force of interest at time $t={\frac{1}{2}}$

### Solution (a)

$$AV_0=M=100$$

$$AV_1=K+L+M=110\to K+L=10$$

$$AV_2=4K+2L+M=136\to4K+2L=36$$

These equations solve for $K=8$ $L=2$ ， $M=100$

We know that

$$\delta_{t}=\frac{\frac{d}{dt}AV_{t}}{AV_{t}}=\frac{2Kt+L}{Kt^{2}+Lt+M}$$

$$\delta_{\frac{1}{2}}=\frac{(2)(8)(\frac{1}{2})+2}{(8)(\frac{1}{2})^{2}+(2)(\frac{1}{2})+100}=\frac{10}{103}=0.09709$$

Exercise (b)

Fund $A$ accumulates at a simple interest rate of $10\%$ .Fund $B$ accumulates ata simple discount rate of $5\%$ .Find the point in time at which the forces of interest on the two funds are equal.

### Solution (b)

$$AVF_t^A=1+0.1t\text{and}AVF_t^B=(1+0.1t)^{-1}$$

$$\delta_t^A=\frac{\frac{d}{dt}AVF_t^A}{AVF_t^A}=\frac{0.1}{1+0.1t}$$

$$\delta_t^B=\frac{\frac{d}{dt}AVF_t^B}{AVF_t^B}=\frac{0.1(1-0.1t)^{-2}}{1-0.1t)^{-1}}=0.1(1-0.1t)^{-1}$$

Equating and solve for $t$

$$\frac{0.1}{1+0.1t}=\frac{0.1}{1-0.1t}\to0.1-0.1t=0.1+0.1t\to t=5$$
### Exercise (a)

On 15 March 2003. A student deposits $X$ into a bank account. The account is credited with simple interest where $i=7.5\%$

On the same date, the student's professor deposits $X$ into a different bank account where interest is credited at a force of interest

$$\delta_{t}=\frac{2t}{t^{2}+k},t\geq0.$$

From the end of the fourth year until the end of the eighth year, both accounts earn the same dollar amount of interest

Calculate $k$

## Solution (a)

$$\mathrm{t~Earned}=AV_{8}-AV_{4}=X[1+0.1(8)]-X[1+0.1(4)]=X(0.075)(4)=X(0.1)$$

$$\text{Compound Interest Earned}=AV_8-AV_4=Xe^{\int_0^8\delta_t\cdot dt}-Xe^{\int_0^4\delta_t\cdot dt}$$

$$Xe^{\int_{0}^{8}{\frac{2t}{t^{2}+k}}\cdot dt}-Xe^{\int_{0}^{4}{\frac{2t}{t^{2}+k}}\cdot dt}=Xe^{\int_{0}^{8}{\frac{f^{\prime}(t)}{f(t)}}\cdot dt}-Xe^{\int_{0}^{4}{\frac{f^{\prime}(t)}{f(t)}}\cdot dt}=X{\frac{f(8)}{f(0)}}-X{\frac{f(4)}{f(0)}}$$

$$X\frac{(8)^2+k}{(0)^2+k}-X\frac{(4)^2+k}{(0)^2+k}=X\frac{48}{k},\text{compound interest}$$

$$X(0.1)=X\frac{48}{k}\to0.1=\frac{48}{k}\to0.1k=48\to k=160$$
### Exercise (b）

Payments are made to an account at a continuous rate of , $k^{2}+8tk^{2}+(tk)^{2}$ ,where $0\leq t\leq10$ and $k>0$

Interest is credited at a force of interest where

$$\delta_t=\frac{8+2t}{1+8t+t^2}$$

After 10 years, the account is worth 88,690

Calculate $k$

### Solution (b)

$$\int_0^{10}[k^2+8tk^2+(tk)^2](1+i)^{10-t}dt=88,690$$

$$\left(1+i\right)^{10-t}=e^{\int_t^{10}\delta_s\cdot ds}=e^{\int_t^{10}\frac{8+2s}{1+8s+s^2}\cdot ds}=e^{\int_t^{10}\frac{f'(s)}{f(s)}\cdot ds}=\frac{f(10)}{f(t)}$$

$$=\frac{1+8(10)+(10)^2}{1+8t+t^2}=\frac{181}{1+8t+t^2}$$

$$\int_0^{10}[k^2+8tk^2+(tk)^2]\frac{181}{1+8t+t^2}dt=88,690$$

$$k^2\int_0^{10}[1+8t+t^2]\frac{181}{1+8t+t^2}dt=88,690\to k^2(181)(10)=88,690\to k^2=49\to k=7$$
Fund $A$ accumulates at a constant force of interest of $\delta_{t}^{A}=\frac{0.1}{1+0.1t}$ at time $t$ for $t\geq0$ and Fund $B$ accumulates at a constant force of interest of $\delta^{B}=5\%$ You aregiven

(i) The amount in Fund $A$ at time zero is 1,000 (i) The amount in Fund $B$ at time zero is 500 (ii) The amount in Fund $C$ at any time $t$ $t\geq0$ is equal to the sum of the amounts in Fund $A$ and Fund $B$ .Fund $C$ accumulates at a force ofinterest of $\delta_{l}^{C}$ ，for $tu$

Calculate $\delta_{2}^{C}$

Solution (c)

$$AV_t^C=AV_t^A+AV_t^B=1,000e^{\int_0^t\delta_sdt}+500e^{0.1t}$$

$$AV_t^C=1,000e^{\displaystyle\int_0^t\frac{0.1}{1+0.1s}\cdot ds}+500e^{0.1t}=1,000\left[\frac{f(t)}{f(0)}\right]+500e^{0.1t}$$

$$AV_t^C=1,000\left[\frac{1+0.1(t)}{1+0.1(0)}\right]+500(0.1)e^{0.1t}=1000[1+0.1t]+500e^{0.1t}$$

$$\frac{d}{dt}AV_t^C=1,000(0.1)+500(0.1)e^{0.1t}=50+25^{0.1t}$$

$$\delta_t=\frac{\frac{d}{dt}AV_t^C}{AV_t^C}=\frac{50+25e^{0.1t}}{1000[1+0.1t]+500e^{0.1t}}$$

$$\delta_2=\frac{50+25e^{0.1(2)}}{1,000[1+0.1(2)]+500e^{0.1(2)}}=4.697\%$$
Fund $F$ accumulates at the rate $\delta_{t}=\frac{1}{1+t}$ . Fund $G$ accumulates at the rate $\delta_{t}=\frac{4t}{1+2t^{2}}$ F (t) is the amount in Fund $F$ at time t, and $G(t)$ is the amount in fund $G$ at time t, witl $F(0)=G(0)$ .Let $H( t)$ = $F( t) - G( t)$ .Calculate $I$ ,the value of time $t$ when $H(t)$ is& maximum.

### Solution (d)

Since $F(0)=G(0)$ , we can assume an initial deposit of 1. Then we have

$$F(t)=e^{\displaystyle\int_0^t\frac{1}{1+r}\cdot dr}=e^{ln(1+t)-ln(1)}=1+t$$

$$G(t)=e^{\displaystyle\int_0^t\frac{4r}{1+2r^2}dr}=e^{ln(1+2t^2)-ln(1)}=1+2t^2$$

$$H(t)=t-2t^2\text{and}\frac{d}{dt}H(t)=1-4t=0\rightarrow t=\frac{1}{4}$$
## 2 Level Annuities

### Overview Definition of An Annuity

A series of payments made at equal intervals of time (annually or otherwise) -payments made for certain over a fixed period of time are called an annuity-certain payments made for an uncertain period of time are called a contingent annuity the payment frequency and the interest conversion period are equal -the payments are level

### 2.1 Annuity-Immediate

### Definition

Payments of 1 are made at the end of every year for 77 years

 ![500](https://storage.simpletex.cn/view/fQOLvhAuW2GUGg1Twh67vmzoIn1KSSoqm)

### Annuity-Immediate Present Value Factor

-the present value (at $t=0$ ) of an annuity-immediate, where the annual effective rate of interest is $i$ , shall be denoted as $U_{\mathrm{TT}_{\mathrm{f}}}$ and is calculated as follows:

$$\begin{aligned}
a_{n}& =(1)v+(1)v^{2}+\cdots+(1)v^{n-1}+(1)v^{n}  \\
&=v(1+v+v^{2}+\cdots+v^{n-2}+v^{n-1}) \\
&=\left(\frac{1}{1+i}\right)\left(\frac{1-v^{n}}{1-v}\right) \\
&=\left(\frac{1}{1+i}\right)\left(\frac{1-v^{n}}{d}\right) \\
&=\left(\frac{1}{1+i}\right)\left(\frac{1-v^{n}}{\frac{i}{1+i}}\right) \\
&=\frac{1-v^{n}}{i}
\end{aligned}$$
### Annuity-Immediate Accumulated Value Factor

-the accumulated value (at $t=7$ ) of an annuity-immediate, where the annual effective rate of interest is $\dot{\boldsymbol{z}}$ ,shall be denoted as s and is calculated as follows:

$$\begin{aligned}
s_{n}& =1+(1)(1+i)+\cdots+(1)(1+i)^{n-2}+(1)(1+i)^{n-1} \\
&=\frac{1-(1+i)^n}{1-(1+i)} \\
&=\frac{1-(1+i)^n}{-i} \\
&=\frac{(1+i)^{n}-1}{i}
\end{aligned}$$

Basic Relationship $1:1=i\cdot a_{\text{ п}}+v^{n}$

Consider an 72. -vear investment where 1 is invested at time 0

The present value of this single payment income stream at $t=0$ is 1

Alternatively, consider a 72 -year investment where 1 is invested at time 0 and produces annual interest payments of $(1)\cdot i$ at the end of each year and then the 1 is refunded at $t=7$

1
 ![500](https://storage.simpletex.cn/view/fTWp1wnTL4GNT1KplL58bGDdx7US9zNcc)

The present value of this multiple payment income stream at $t=0$ is $i\cdot a_{\overline{n}}+(1)v^{n}$

Therefore, the present value of both investment opportunities are equal

Also note that $a_{\:\overline{n}}={\frac{1-v^{n}}{i}}\to1=i\cdot a_{\:\overline{n}}+v^{n}$
### Basic Relationship $2:PV(1+i)^{n}=FV$ and $PV=FV\cdot v^{n}$

if the future value at time $7t$ . $STT$ ,is discounted back to time $U$ then you willhave its present value, $a_{\mathrm{п}}$

$$\begin{aligned}
s_{\overline{n}}\cdot v^{n}& =\left[{\frac{(1+i)^{n}-1}{i}}\right]\cdot v^{n} \\
&=\frac{(1+i)^n\cdot v^n-v^n}{i} \\
&=\frac{1-v^{n}}{i} \\
&=a_{n}
\end{aligned}$$

if the present value at time 0 ， $a\pi$ ,is accumulated forward to time 77 ,then you will have its future value, $y77$

$$\begin{aligned}
a_{n}\cdot(1+i)^{n}& =\left[\frac{1-v^{n}}{i}\right](1+i)^{n}  \\
&=\frac{(1+i)^n-v^n(1+i)^n}{i} \\
&=\frac{(1+i)^{n}-1}{i} \\
&=s_{n}
\end{aligned}$$
### Basic Relationship 3
$$3:\frac{1}{a_{\overline{n}}}=\frac{1}{s_{\overline{n}}}+i$$

Consider a loan of 1, to be paid back over $7t$ years with equal annual payments of $P$ made at the end of each year. An annual effective rate of interest, $\dot{i}$ , is used. The present value of this single payment loan must be equal to the present value of the multiple payment income stream.

$$P\cdot a_{n_{k}}=1$$

$$P=\frac{1}{a_{n_{i}}}$$

Alternatively, consider a loan of 1, where the annual interest due on the loan, $(1)i$ , is paid at the end of each year for $7t$ years and the loan amount is paid back at time $7t$

In order to produce the loan amount at time 77 ,annual payments at the end of each year for TL years, will be made into an account that credits interest at an annual effective rate of interest $i$

The future value of the multiple deposit income stream must equal the future value of the single payment, which is the loan of 1

$$D\cdot s_{n_{k}}=1$$

$$D=\frac{1}{s_{\overline{n}_{k}}}$$

The total annual payment will be the interest payment and account payment:

$$i+\frac1{s_{\overline{n}_i}}$$

Therefore, a level annual annuity payment on a loan is the same as making an annual interest payment each year plus making annual deposits in order to save for the loan repayment

Also note that

$$\begin{aligned}
\frac{1}{a_{n_{i}}}& =\frac{i}{1-v^{n}}\times\frac{(1+i)^{n}}{(1+i)^{n}}=\frac{i(1+i)^{n}}{(1+i)^{n}-1}  \\
&=\frac{i(1+i)^{n}+i-i}{(1+i)^{n}-1}=\frac{i[(1+i)^{n}-1]+i}{(1+i)^{n}-1} \\
&=i+\frac{i}{(1+i)^{n}-1}=i+\frac{1}{s_{\overline{n}}}
\end{aligned}$$
# 2.2 Annuity-Due

## Definition

Payments of 1 are made at the beginning of every year for 77 years

 ![500](https://storage.simpletex.cn/view/fb0uh9Q0W2NVGKtHhZ784a1NDD5HZFsZr)

Annuity-Due Present Value Factor

-the present value (at $t=0$ ) of an annuitydue, where the annual effective rate of interest is $i$ ,shall be denoted as $\ddot{a}_{\overline{n}_i}$ and is calculated as follows

$$\begin{aligned}
\ddot{a}_{n}& =1+(1)v+(1)v^{2}+\cdots+(1)v^{n-2}+(1)v^{n-1} \\
&=\frac{1-v^{n}}{1-v} \\
&=\frac{1-v^{n}}d
\end{aligned}$$

### Annuity-Due Accumulated Value Factor

the accumulated value (at $t=n$ ) of an annuity-due, where the annual effective rate of interesf is 2 , shall be denoted as $\ddot{S}\pi_{i}$ and is calculated as follows

$$\begin{aligned}
s_{n}& =(1)(1+i)+(1)(1+i)^{2}+\cdots+(1)(1+i)^{n-1}+(1)(1+i)^{n}  \\
&=(1+i)[1+(1+i)+\cdots+(1+i)^{n-2}+(1+i)^{n-1}] \\
&=(1+i)\left[\frac{1-(1+i)^{n}}{1-(1+i)}\right] \\
&=(1+i)\left[\frac{1-(1+i)^{n}}{-i}\right] \\
&=(1+i)\left[\frac{(1+i)^{n}-1}{i}\right] \\
&=\frac{(1+i)^{n}-1}{d}
\end{aligned}$$
### Basic Relationship $1:1=d\cdot\ddot{a}_{\overline{n}}+v^{\underline{n}}$

Consider an 72. Year investment where 1 is invested at time 0.

The present value of this single payment income stream at $t=0$ is 1.

Alternatively, consider a 72. Year investment where 1 is invested at time 0 and produces annua interest payments of (1) $d$ at the beginning of each year and then have the 1 refunded at $t=7$

1

 ![500](https://storage.simpletex.cn/view/feDDlnl3igLOuoZqTgz711PqmX63y60hg)

The present value of this multiple payment income stream at $t=0$ is $d\cdot\ddot{a}_{n}+(1)v^{n}$

Therefore, the present value of both investment opportunities are equal

Also note hat $\ddot{a}\:_{\pi_{\Pi}}=\frac{1-v^{n}}{d}\rightarrow1=d\cdot\ddot{a}\:_{\pi_{\Pi}}+v^{n}.$

### Basic Relationship $2:PV(1+i)^{n}=FV$ and $PV=FV\cdot v^{\mathrm{n}}$

- if the future value at time 72. ， $\ddot{8}_{n}$ , is discounted back to time $U$ , then you will have its present value, $\ddot{a}_{\text{п}}$

$$\ddot{s}_{\overline{n}|}\cdot v^n=\left[\frac{(1+i)^n-1}{d}\right]\cdot v^n=\frac{(1+i)^n\cdot v^n-v^n}{d}=\frac{1-v^n}{d}=\ddot{a}_{\overline{n}|}$$

-if the present value at time 0 ， $\ddot{a}_{\overline{n}}$ , is accumulated forward to time $7t$ , then you will have its future value, $\ddot{S}\pi$

$$\ddot{a}_{m}\cdot(1+i)^{n}=\left[\frac{1-v^{n}}{d}\right](1+i)^{n}=\frac{(1+i)^{n}-v^{n}(1+i)^{n}}{d}=\frac{(1+i)^{n}-1}{d}=\ddot{s}_{m}$$
### Basic Relationship 3
$$3:\frac{1}{\ddot{a}_{\overline{n}}}=\frac{1}{\ddot{s}_{\overline{n}}}+d$$

Consider a loan of 1, to be paid back over $7t$ years with equal annual payments of $P$ made at the beginning of each year. An annual effective rate of interest, $\dot{\tau}$ ,is used. The presenf value of the single payment loan must be equal to the present value of the multiple payment stream.

$$P\cdot\ddot{a}_{n_{\mathbf{l}}}=1$$

$$P=\frac{1}{\ddot{a}_{n_{i}}}$$

Alternatively, consider a loan of l, where the annual interest due on the loan, $(1)\cdot d$ , is paid at the beginning of each year for 72 years and the loan amount is paid back at time 77

In order to produce the loan amount at time TL ，annual pavments at the beginning of each year, for 74 years, will be made into an account that credits interest at an annual effective rate of interest 2

The future value of the multiple deposit income stream must equal the future value of the single payment, which is the loan of 1.

$$D\cdot\ddot{s}_{n_{k}}=1$$

$$D=\frac{1}{\ddot{s}_{n_{k}}}$$

The total annual payment will be the interest payment and account payment:

$$d+\frac{1}{\ddot{s}_{\overline{n}_{\mathbf{l}}}}$$

Therefore, a level annual annuity payment is the same as making an annual interest payment each year and making annual deposits in order to save for the loan repayment.

Also note that

$$\begin{aligned}
\frac{1}{\ddot{a}\pi_{i}}& =\frac{d}{1-v^{n}}\times\frac{(1+i)^{n}}{(1+i)^{n}}=\frac{d(1+i)^{n}}{(1+i)^{n}-1} \\
&=\frac{d(1+i)^{n}+d-d}{(1+i)^{n}-1}=\frac{d[(1+i)^{n}-1]+d}{(1+i)^{n}-1} \\
&=d+\frac{d}{(1+i)^{n}-1}=d+\frac{1}{\ddot{s}_{\overline{n}}}
\end{aligned}$$

## Basic Relationship 4: Annuity Due= Annuity Immediate $\times(1+i)$

$$\ddot{a}_{\overline{n}}=\frac{1-v^n}{d}=\frac{1-v^n}{i}\cdot(1+i)=a_{\overline{n}_1}\cdot(1+i)$$

$$\ddot{s}_{\overline{n}}=\frac{(1+i)^n-1}{d}=\left[\frac{(1+i)^n-1}{i}\right]\cdot(1+i)=s_{\overline{n}}\cdot(1+i)$$

An annuity-due starts one period earlier than an annuity-immediate and as a result, earns one more period of interest, hence it will be larger
Basic Relationship $5:\ddot{a}_{\boldsymbol{\pi}}=1+a\overline{n-1}$

$$\begin{aligned}
\ddot{a}_{n}& =1+[v+v^{2}+\cdots+v^{n-2}+v^{n-1}] \\
&=1+v[1+v+\cdots+v^{n-3}+v^{n-2}] \\
&=1+v\left(\frac{1-v^{n-1}}{1-v}\right) \\
&=1+\left(\frac{1}{1+i}\right)\left(\frac{1-v^{n-1}}{d}\right) \\
&=1+\left(\frac{1}{1+i}\right)\left(\frac{1-v^{n-1}}{i/1+i}\right) \\
&=1+\frac{1-v^{n-1}}{i} \\
&=1+a_{n-1}
\end{aligned}$$

This relationship can be visualized with a time line diagram

 ![500](https://storage.simpletex.cn/view/f00282KboCZQRnbuCokZe4MvfefE76cvx)

An additional payment of 1 at time O results in $a{\frac{n-1}{n-1}}$ becoming 72. Payments that now com mence at the beginning of each year which is $\ddot{a}_{n}$
## Basic Relationship $6:s_{\boldsymbol{\pi}}=1+\ddot{s}_{\boldsymbol{n}-1}$

$$\begin{aligned}
s_{n}& =1+[(1+i)+(1+i)^{2}+\cdots+(1+i)^{n-2}+(1+i)^{n-1}] \\
&=1+(1+i)[1+(1+i)+\cdots+(1+i)^{n-3}+(1+i)^{n-2}] \\
&=1+(1+i)\left[\frac{1-(1+i)^{n-1}}{1-(1+i)}\right] \\
&=1+(1+i)\left[\frac{1-(1+i)^{n-1}}{-i}\right] \\
&=1+(1+i)\left[\frac{(1+i)^{n-1}-1}{i}\right] \\
&=1+\frac{(1+i)^{n-1}-1}{d} \\
&=1+\ddot{s}_{\overline{n-1}}
\end{aligned}$$

This relationship can also the visualized with a time line diagram.

 ![500](https://storage.simpletex.cn/view/fmQNtQk3kGZE0rBlgHbUwWcf3iXb6g3ep)

An additional payment of 1 at time 72. Results in $\ddot{s}{\frac{n-1}{n-1}}$ becoming 72 payments that now commerce at the end of each year which is 577
### 2.3 Deferred Annuities

There are three alternative dates to valuing annuities rather than at the beginning of the term ( $t=0$ ) or at the end of the term ( $t=n$

(i) present values more than one period before the first payment date (ii) accumulated values more than one period after the last payment date (i) current value between the first and last payment dates

 The following example will be used to illustrate the above cases. Consider a series of payments of 1 that are made at time $t=3$ to $t=9$ , inclusive

 ![500](https://storage.simpletex.cn/view/fXdI7LOGetIgAi2f3eFT0eHbzBiAlN6pU)

Present Values More than One Period Before The First Payment Date At $t=2$ , there exists 7 future end-of-year payments whose present value is represented by

$u$ 7 .If this value is discounted back to time $t=0$ , then the value of this series of payments (2 periods before the first end-of-year payment) is

$$_{2|}a_{7|}=v^{2}\cdot a_{7|}.$$

The general form is

$$_{m|}a_{\overline{n}|_{i}}=v^{m}\cdot a_{\overline{n}_{\mathbf{k}}}.$$

Alternatively, at $t=3$ ,there exists 7 future beginning-of-year payments whose present value is represented by $\ddot{a}_{71}$ If this value is discounted back to time $t=0$ , then the value of this series of payments (3 periods before the first beginning-of-year payment) is

$$_{3|}\ddot{a}_{7|}=v^{3}\cdot\ddot{a}_{7|}.$$

The general form is

$$_{m|}\ddot{a}_{\overline{n}|}=v^{m}\cdot\ddot{a}_{\overline{n}\mathbf{l}_{i}}.$$

Another way to examine this situation is to pretend that there are 9 end-of-year payments This can be done by adding 2 more payments to the existing 7. In this case, let the 2 addi tional payments be made at $t=1$ and 2 and be denoted as 1
 ![500](https://storage.simpletex.cn/view/fTwBVBbO2erUki8of5cActymQbnKIzaBx)

At $\mathbf{t}=0$ , there now exists 9 end-of-year payments whose present value is $u_{9}$ .This present value of 9 payments would then be reduced by the present value of the two imaginary pay ments, represented by $a\boldsymbol{T}.$ Therefore, the present value at $t=0$ is

$$a_{\overline{9}\rceil}-a_{\overline{2}\rceil},$$

And this results in

$$v^2\cdot a_{71}=a_{91}-a_{21}.$$

The general form is

$$v^m\cdot a_{\overline{n}\rceil}=a_{\overline{m+n}\rceil}-a_{\overline{m}\rceil}.$$
With the annuitydue version, one can pretend that there are 10 payments being made This can be done by adding 3 payments to the existing 7 payments. In this case, let the 3 additional payments be made at $t=0$ ， 1 and 2 and be denoted as 1

 ![500](https://storage.simpletex.cn/view/f3ygK1eNVtvwHNm7Hgc4zMMO5eFq6qCe1)

At t=0 , there now exists 10 beginning-of-year payments whose present value is $\ddot{a}_{10}$ This present value of 10 payments would then be reduced by the present value of the three imag inary payments, represented by $\ddot{a}_{37}.$ Therefore, the present value at $t=0$ is

$$\ddot{a}_{\overline{10}\rceil}-\ddot{a}_{\overline{3}\rceil},$$

And this results in

$$v^3\cdot\ddot{a}_{71}=\ddot{a}_{101}-\ddot{a}_{31}.$$

The general form is

$$v^{m}\cdot\ddot{a}_{\overline{n}\rceil}=\ddot{a}_{\overline{m+n}\rceil}-\ddot{a}_{\overline{m}\rceil}.$$

Accumulated Values More Than One Period After The Last Payment Date

At $t=9$ there exists 7 past end-of-year payments whose accumulated value is represented by 577 . If this value is accumulated forward to time $t=12$ , then the value of this series of payments (3 periods after the last end-of-year payment) is

$$s_{71}\cdot(1+i)^{3}.$$

Alternatively, at $t=10$ , there exists 7 past beginning-of-year payments whose accumulated value is represented by $\ddot{s}71.$ If this value is accumulated forward to time $t=12$ ,then the value of this series of payments (2 periods after the last beginning-of-year payment) is

$$\ddot{s}_{71}\cdot(1+i)^{2}.$$

Another way to examine this situation is to pretend that there are 10 end-of-year payments This can be done by adding 3 more payments to the existing 7. In this case, let the 3 addi tional payments be made at $t=10$ ,11 and 12 and be denoted as
 ![500](https://storage.simpletex.cn/view/fFDsGqIgkTgG4wgFCNz9IfzihdR1Q2agv)

At $\mathbf{t}=12$ , there now exists 10 end-of-year payments whose present value is 5101 .This future value of 10 payments would then be reduced by the future value of the three imaginary payments, represented by 531 .Therefore, the accumulated value at $t=12$ is

$$s_{\overline{10}}-s_{\overline{3}},$$

And this results in

$$s_{71}\cdot(1+i)^3=s_{101}-s_{31}.$$

The general form is

$$s_{\overline{n}}\cdot(1+i)^{m}=s_{\overline{m+n}}-s_{\overline{m}}.$$

With the annuity-due version, one can pretend that there are 9 payments being made. This can be done by adding 2 payments to the existing 7 payments. In this case, let the 2 additional payments be made at $t=10$ and 1 l and bedenoted as
 ![500](https://storage.simpletex.cn/view/fznGVG0kYqV205QzUQ9Ca37RsAfqEIcTG)

At $\mathbf{t}=12$ , there now exists 9 beginning-of-year payments whose accumulated value is $\ddot{\text{S क़}}$ This future value of 9 payments would then be reduced by the future value of the two imaginary payments, represented by $\ddot{S}\boldsymbol{\daleth}$ Therefore, the accumulated value at $t=12$ is

$$\ddot{s}_{\overline{9}\rceil}-\ddot{s}_{\overline{2}\rceil},$$

And this results in

$$\ddot{s}_{71}\cdot(1+i)^{2}=\ddot{s}_{91}-\ddot{s}_{21}.$$

The general form is

$$\ddot{s}_{\overline{n}}\cdot(1+i)^{m}=\ddot{s}_{\overline{m+n}}-\ddot{s}_{\overline{m}}.$$
## Current Values Between The First And Last Payment Dates

The 7 payments can be represented by an annuity-immediate or by an annuity-due depending on the time that they are evaluated at.

For example, at $t=2$ ,， the present value of the 7 end-of-year payments is $u_{71}$ At $t=9$ the future value of those saime payments is $S7T$ There is a point between time 2 and 9 where the present value and the future value can be accumulated to and discounted back, respec tively. At $t=6$ ，for example, the present value would need to be accumulated forward 4 years, while the accumulated value would need to be discounted back 3 years.

$$a_{77}\cdot(1+i)^4=v^3\cdot s_{77}$$

The general form is

$$a_{\overline{n}\rceil}\cdot(1+i)^m=v^{(n-m)}\cdot s_{\overline{n}\rceil}$$

Alternatively, at $t=3$ one can view the 7 payments as being paid at the beginning of the year where the present value of the payments is $\ddot{a}_{71}$ The future value at $t=10$ would then be $\ddot{S}77$ .At $t=6$ , for example, the present value would need to be accumulated forward 3 years, while the accumulated value would need to be discounted back 4 years.

$$\ddot{a}_{77}\cdot(1+i)^{3}=v^{4}\cdot\ddot{s}_{77}.$$

The general form is

$$\ddot{a}_{\overline{n}\rceil}\cdot(1+i)^{m}=v^{(n-m)}\cdot\ddot{s}_{\overline{n}\rceil}.$$

At any time during the payments, there will exists a series of past payments and a series of future payments.

For example, at $t=6$ ,one can define the past payments as 4 end-of-year payments whose accumulated value is $s71$ The 3 end-of-year future payments at $t=6$ would then have a present value (at $t=6$ ) equal to $u_{31}$ Therefore, the current value as at $t=6$ of the 7 payments is

$$s_{41}+a_{31}.$$

Alternatively, if the payments are viewed as beginning-of-year payments at $t=6$ then there are 3 past payments and 4 future payments whose accumulated value and present value are respectively, d $S37$ and $a\boldsymbol{\daleth}$ Therefore, the current value as at $t=6$ of the 7 payments can also be calculated as

$$\ddot{s}_{31}+\ddot{a}_{41}.$$

This results in

$$s_{\overline{4}}+a_{\overline{3}}=\ddot{s}_{\overline{3}}+\ddot{a}_{\overline{4}}.$$

The general form is

$$s_{\overline{m}}+a_{\overline{n}}=\ddot{s}_{\overline{n}}+\ddot{a}_{\overline{m}}.$$
## 2.4 Continuously Payable Annuities

payments are made continuously every year for the next 77 years (i.e. $m=0$

### Continuously Payable Annuity Present Value Factor

the present value (at $t=0$ ) of a continuous annuity, where the annual effective rate of interest is 2 , shall be denoted as $\bar{a}_{\boldsymbol{\pi}i}$ and is calculated as follows

$$\begin{aligned}
\bar{a}_{n}& =\int_{0}^{n}v^{t}dt \\
&=\int_{0}^{n}e^{-\delta t}dt \\
&=-\left.\frac{1}{\delta}e^{-\delta t}\right]_{0}^{n} \\
&=-\:\frac{1}{\delta}\left[e^{-\delta n}-e^{-\delta0}\right] \\
&\text{=} \frac{1}{\delta}\left[1-e^{-\delta n}\right] \\
&\text{=} \frac{1-v_{i}^{n}}{\delta}
\end{aligned}$$

## Continuously Payable Annuity Accumulated Value Factor

the accumulated value (at $t=7$ ) of a continuous annuity, where the annual effective rate of interest is 2. , shall be denoted as $\bar{s}\pi\Pi_i$ and is calculated as follows

$$\begin{aligned}
\overline{s}_{n}& =\int_{0}^{n}(1+i)^{n-t}dt  \\
&=\int_0^n(1+i)^tdt \\
&=\int_{0}^{n}e^{\delta t}dt \\
&\text{=} \frac{1}{\delta}e^{\delta t}dt\biggr]_{0}^{n}  \\
&\text{=} \frac{1}{\delta}\left[e^{\delta n}-e^{\delta0}\right]  \\
&= \frac{(1+i)^{n}-1}{\delta}
\end{aligned}$$
Basic Relationship $1:1=\delta\cdot\bar{a}_{\boldsymbol{\daleth}}+v^{\boldsymbol{\tau}}$

Basic Relationship $2:PV(1+i)^{n}=FV$ and $PV=FV\cdot v^{\mathrm{n}}$

if the future value at time 77 ” $\bar{s}\varpi$ , is discounted back to time $U$ ,then you will have its present value, $\bar{a}_{\text{п}}$

$$\begin{aligned}
{\overline{s}}_{n}\cdot v^{n}& =\left[{\frac{(1+i)^{n}-1}{\delta}}\right]\cdot v^{n} \\
&\text{=} \frac{(1+i)^{n}\cdot v^{n}-v^{n}}{\delta} \\
&\text{=} \frac{1-v^{n}}{\delta} \\
&\text{=} \bar{a}_{n}
\end{aligned}$$

if the presentvalue at time 0 。$\bar{a}_{\overline{n}}$ is accumulated forwardto time 77 ,then you willhave its future value, $\bar{s}\varpi$

$$\begin{aligned}
\bar{a}_{n1}\cdot(1+i)^{n}& =\left[{\frac{1-v^{n}}{\delta}}\right](1+i)^{n}  \\
&\text{一} \frac{(1+i)^{n}-v^{n}(1+i)^{n}}{\delta}  \\
&\text{=} \frac{(1+i)^{n}-1}{\delta}  \\
&\text{=} \text{sn}
\end{aligned}$$
# Basic Relat ionship $3:{\frac{1}{\bar{a}_{n}}}={\frac{1}{\bar{s}_{n}}}+\delta$

Consider a loan of 1, to be paid back over 72 years with annual payments of $P$ that are paid continuously each year, for the next 72. Years. An annual effective rate of interest $\dot{\boldsymbol{\tau}}$ ,and annual force of interest, $\delta$ ,is used. The present value of this single payment loan must be equal to the present value of the multiple payment income stream

$$\begin{array}{c}P\cdot\bar{a}\mathbf{n}_i=1\\\\P=\frac{1}{\bar{a}\mathbf{n}_{\mathbf{k}}}\end{array}$$

Alternatively, consider a loan of 1, where the annual interest due on the loan, $(1)\times\delta$ is paid continuously during the year for 72. Years and the loan amount is paid back at time $TL$

In order to produce the loan amount at time 77 ,annual payments of $D$ are paid continu ously each year, for the next 72 years, into an account that credits interest at an annual force of interest, $\delta$

The future value of the multiple deposit income stream must equal the future value of the single payment, which is the loan of 1.

$$D\cdot\bar{s}_{\overline{n}_{i}}=1$$

$$D=\frac{1}{\bar{s}_{n_{i}}}$$

The total annual payment will be the interest payment and account payment

$$\delta+\frac{1}{\bar{s}_{n_{k}}}$$

-Note that

$$\begin{aligned}
\frac{1}{\bar{a},\pi_{i}}& =\frac{\delta}{1-v^{n}}\times\frac{(1+i)^{n}}{(1+i)^{n}}=\frac{\delta(1+i)^{n}}{(1+i)^{n}-1} \\
&=\frac{\delta(1+i)^{n}+\delta-\delta}{(1+i)^{n}-1}=\frac{\delta[(1+i)^{n}-1]+\delta}{(1+i)^{n}-1} \\
&=\delta+\frac{\delta}{(1+i)^{n}-1}=\delta+\frac{1}{\bar{s}_{n}}
\end{aligned}$$

Therefore, a level continuous annual annuity payment on a loan is the same as making an annual continuous interest payment each year plus making level annual continuous deposits in order to save for the loan repayment.
Basic Relationship $4: \bar{a} _{\overline {n}}= \frac i\delta \cdot a_{\overline {n}}$, $\bar{s} _{\overline {n}}= \frac i\delta \cdot s_{\overline {n}}$

-Consider annual payments of 1 made continuously each year for the next TL years. Over a one-year period, the continuous payments will accumulate at the end of the year to a lump sum of $\bar{s}\daleth$ If this end-of-year lump sum exists for each year of the 77 -yea 1 annuity-immediate, then the present value (at $t=0$ ) of these end-of-year lump sums is the same as $\bar{a}$ п

$$\begin{aligned}\bar{a}_{\overline{n}}=&\bar{s}_{\overline{n}}\cdot a_{\overline{n}}\\=&\frac{i}{\delta}\cdot a_{\overline{n}}\end{aligned}$$

Therefore, the accumulated value (at $t=7$ ) of these end-of-year lump sums is the same as $\bar{S}\pi$

$$\begin{aligned}\bar{s}_{m}=&\bar{s}_{\Pi}\cdot s_{m}\\=&\frac{i}{\delta}\cdot s_{m}\end{aligned}$$

Basic Relationship $5: \bar{a} _{\text{ п }}= \frac d\delta \cdot \ddot{a} _{\text{ п }}$, $\bar{s} _{\text{ п }}= \frac d\delta \cdot \ddot{s} _{\text{ п }}$

The mathematical development of this relationship is derived as follows

$$\ddot{a}_{\overline{n}}\cdot\frac{d}{\delta}=\frac{1-v^{n}}{d}\cdot\frac{d}{\delta}=\frac{1-v^{n}}{\delta}=\bar{a}_{\overline{n}}$$

$$\ddot{s}_{\overline{n}}\cdot\frac{d}{\delta}=\frac{(1+i)^n-1}{d}\cdot\frac{d}{\delta}=\frac{(1+i)^n-1}{\delta}=\bar{s}_{\overline{n}}$$
### 2.5 Perpetuities

Definition Of A Perpetuity-Immediate

 payments of 1 are made at the end of every year forever i.e. $n=\mathbf{x}$

 ![500](https://storage.simpletex.cn/view/fWLncbq3G2w2lfuuE3nw7zAic5Fts6kTb)

Perpetuity-Immediate Present Value Factor

-the present value (at $t=0$ ) of a perpetuity-immediate, where the annual effective rate of interest is $i$ , shall be denoted as $u_{\mathrm{x}}\daleth_{i}$ and is calculated as follows:

$$\begin{aligned}
a_{\infty}& =(1)v+(1)v^{2}+(1)v^{3}+\cdots \\
&=v(1+v+v^{2}+\cdots) \\
&=\left(\frac{1}{1+i}\right)\left(\frac{1-v^{\infty}}{1-v}\right) \\
&=\left({\frac{1}{1+i}}\right)\left({\frac{1-0}{d}}\right) \\
&=\left(\frac{1}{1+i}\right)\left(\frac{1}{\frac{i}{1+i}}\right) \\
&=\frac{1}{i}
\end{aligned}$$

-one could also derive the above formula by simply substituting $Tl=\mathbb{X}$ into the original present value formula:

$$a_{\infty_{i}}=\frac{1-v^{\infty}}{i}=\frac{1-0}{i}=\frac{1}{i}$$

Note that $\frac{1}{i}$ repreens an itil amount that can be invested at $t=0$ . The anual interest paynents able at the end of the er, produed by tis investmen is $\left({\frac{1}{i}}\right)\cdot i=1$ 一 $S\varpi$ is not defined since it would equal $CX$
### Basic Relationship $1:a_{\boldsymbol{\daleth}}=a_{\boldsymbol{\varpi}\boldsymbol{\daleth}}-v_{n}\cdot a_{\boldsymbol{\varpi}\boldsymbol{\Pi}}$

The present value formula for an annuity-immediate can be expressed as the difference be tween two perpetuity-immediates

$$a_{n_{1}}=\frac{1-v^{n}}{i}=\frac{1}{i}-\frac{v^{n}}{i}=\frac{1}{i}-v^{n}\cdot\frac{1}{i}=a_{\infty_{1}}-v^{n}\cdot a_{\infty_{1}}$$

In this case, a perpetuity-immediate that is payable forever is reduced by perpetuity-immediate payments that start after $7t$ years. The present value of both of these income streams, at $t$ =0 , results in end-of-year payments remaining only for the first 72 years
### Definition Of A Perpetuity-Due

payments of 1 are made at the beginning of every year forever i.e. $Tb=00$

 ![500](https://storage.simpletex.cn/view/foPG090paefDV2tgpOrUFy1rl2fhqzwde)

### Perpetuity-Due Present Value Factor

- the present value (at $t=0$ ) of a perpetuity-due, where the annual effective rate of interest is $\dot{i}$ , shall be denoted as $\ddot{a}_{\infty}$ and is calculated as follows:

$$\begin{aligned}
\ddot{a}_{\infty}& =(1)+(1)v^1+(1)v^2+\cdots \\
&=\left(\frac{1-v^{\infty}}{1-v}\right) \\
&=\left(\frac{1-0}{d}\right) \\
&=\frac1d
\end{aligned}$$

one could also derive the above formula by simply substituting $Tl=\mathbb{X}$ into the original present value formula:

$$\ddot{a}_{\overline{\infty}_{d}}=\frac{1-v^{\infty}}{d}=\frac{1-0}{d}=\frac{1}{d}$$

Note that ${\frac{1}{d}}$ represents an itil amount that can be ivested at $t=0$ . The anual interest paynents, able t the begiaming o the ear, rodued b this ivesinen s $\left({\frac{1}{d}}\right)\cdot d=1$ - $\ddot{S}\varpi$ is not defined since it would equal $CX$
## Basic Relationship $1:\ddot{a}_{\boldsymbol{\daleth}}=\ddot{a}_{\boldsymbol{\varpi}\boldsymbol{\daleth}}-v_{n}\cdot\ddot{a}_{\boldsymbol{\varpi}\boldsymbol{\Pi}}$

The present value formula for an annuity-due can be expressed as the difference between two perpetuity-dues:

$$\ddot{a}_{\overline{n}|}=\frac{1-v^{n}}{d}=\frac{1}{d}-\frac{v^{n}}{d}=\frac{1}{d}-v^{n}\cdot\frac{1}{d}=\ddot{a}_{\overline{\infty}|}-v^{n}\cdot\ddot{a}_{\overline{\infty}|}.$$

In this case, a perpetuity-due that is payable forever is reduced by perpetuity-due payments that start after 72. Years. The present value of both of these income streams, at $t=0$ , results in beginning-of-year payments remaining only for the first 77 years

## Definition Of A Continuously Payable Perpetuity Present Value Factol

Payments of 1 are made continuously every year forever

-the present value (at t=O) of a continuously payable perpetuity, where the annual effective rate of interest is $\dot{i}$ ,shall be denoted as $\bar{a}_{\varpi_{i}}$ and is calculated as follows

$$\begin{aligned}
\bar{a}_{\infty}& =\int_{0}^{\infty}v^{t}dt  \\
&=\int_{0}^{\infty}e^{-\delta t}dt \\
&=-\left.\frac{1}{\delta}e^{-\delta t}\right]_{0}^{\infty} \\
&=\frac{1}{\delta}&
\end{aligned}$$

Basic Relationships: $\bar{a}_{\infty}=\frac{i}{\delta}a_{\infty}$ and $\bar{a}_{\varpi_{k}}=\frac{d}{\delta}\ddot{a}_{\varpi}$

The mathematical development of these relationships are derived as follows

$$a_{\overline{\infty}}\cdot\frac{i}{\delta}=\frac{1}{i}\cdot\frac{i}{\delta}=\frac{1}{\delta}=\bar{a}_{\overline{\infty}}\\\ddot{a}_{\overline{\infty}}\cdot\frac{d}{\delta}=\frac{1}{d}\cdot\frac{d}{\delta}=\frac{1}{\delta}=\bar{a}_{\overline{\infty}}$$
## 2.6 Equations of Value

-the value at any given point in time, t, will be either a present value or a future value (sometimes referred to as the time value of money)

-the time value of money depends on the calculation date from which payment (s) are eithel accumulated or discounted to

### Time Line Diagrams

It helps to draw out a time line and plot the payments and withdrawals accordingl

 ![500](https://storage.simpletex.cn/view/f7gZt9d4Wi1LzOGQKsQ0A3PEGkygsYDTG)
### Example

-a payment of 600 is due in 8 years: the alternative is to receive 100 now, 200 in 5 years and $X$ in 10 years. If $i=8\%$ ，find $\$X$ , such that the value of both options is equal.

 ![500](https://storage.simpletex.cn/view/fQcGoT48vY8sHoNXFqN93m8lFkhDeNOBQ)

-compare the values at $t=0$

 ![500](https://storage.simpletex.cn/view/f3KdtNvY15HTLBlrDsPmdMInEUzc2aMDQ)

$$\begin{aligned}
600v_{8\%}^{8}& =100+200v_{8\%}^{5}+Xv_{8\%}^{10}  \\
\text{X}& =\frac{600v_{8\%}^{8}-100-200v_{8\%}^{5}}{v_{8\%}^{10}}=190.08
\end{aligned}$$
-compare the values at $t=5$

 ![500](https://storage.simpletex.cn/view/fMTu53uHQK7X0rwMVLE2xq8db3og9hMMH)

$$\begin{aligned}600v^{3}&=100(1+i)^{5}+200+Xv^{5}\\X&=\frac{600v^{3}-100(1+i)^{5}-200}{v^{5}}=190.08\end{aligned}$$

-compare the values at $t=10$

 ![500](https://storage.simpletex.cn/view/fzRuUwEDwdDZ8r6U0w6Tbigx1gXZHcdBt)

$$\begin{aligned}600(1+i)^2&=100(1+i)^{10}+200(1+i)^5+X\\X&=600(1+i)^2-100(1+i)^{10}-200(1+i)^5=190.08\end{aligned}$$

All 3 equations gave the same answer because all 3 equations treated the value of the payments consistently at a given point of time.
### Unknown Rate of Interest

Assuming that you do not have a financial calculator

Linear Interpolation need to find the value of $u$ п at two different interest rates where $a_{\overline{n}i_{1}}=P_{1}<P$ and $a_{\text{ п}i_{2}}=P_{2}>P$

$$\left.\begin{matrix}a_{\text{п}i_1}=P_1\\a_{\text{п}i}=P\\a_{\text{п}i_2}=P_2\end{matrix}\right\}\:i\approx i_1+\frac{P_1-P}{P_1-P_2}(i_2-i_1)$$
### 2.1 Annuity-Immediate

### Exercise a

Fence posts set in soil last 9 years and cost $Y$ each while fence posts set in concrete last 15 vears and cost $Y+X$ .The posts will be needed for 35 vears. What is the value of $X$ such that a fence builder would be indifferent between the two types of posts?

### Solution (a)

The soil posts must be set 4 times (at t=0,9,18,27). The PV of the cost per post is $PV=$ $Y\cdot{\frac{a_{\overline{36}}}{\alpha_{\overline{9}}}}$

The concrete posts must be set 3 times (at t=0. L 5.30). The PVof the cost per post is $PV=(Y+X)\cdot{\frac{a}{45}{a}}$

The breakeven value of X is the value for which $PV_{s}=PV_{c}$ .Thus

$$Y\cdot\frac{a_{\overline{36}}}{a_{\overline{9}}}=(Y+X)\cdot\frac{a_{\overline{45}}}{a_{\overline{15}}}\:\mathrm{or}$$

$$X\cdot\frac{a_{\overline{45}}}{a_{\overline{15}}}=Y\left[\frac{a_{\overline{36}}}{a_{\overline{9}}}-\frac{a_{\overline{45}}}{a_{\overline{15}}}\right]$$

$$X=Y\left[\frac{a_{36}\cdot a_{15}}{a_{45}\cdot a_{97}}-1\right]$$

Exercise (b)

You are given $\delta_{t}={\frac{4+t}{1+8t+t^{2}}}$ for $t\geq0$

Calculate $s74$

### Solution (b)

$$\begin{aligned}
s_{4}& =1+(1+i)^{4-3}+(1+i)^{4-2}+(1+i)^{4-1}  \\
&=1+e^{\int_{3}^{4}\delta_{s}\cdot ds}+e^{\int_{2}^{4}\delta_{s}\cdot ds}+e^{\int_{1}^{4}\delta_{s}\cdot ds} \\
&=1+e^{\int_{3}^{4}\frac{4+s}{1+8s+s^{2}}\cdot ds}+e^{\int_{2}^{4}\frac{4+s}{1+8s+s^{2}}\cdot ds}+e^{\int_{1}^{4}\frac{4+s}{1+8s+s^{2}}} \\
&=1+e^{\frac{1}{2}}\int_{3}^{4}\frac{f^{\prime}(s)}{f(s)}\cdot ds\quad\frac{1}{2}\int_{2}^{4}\frac{f^{\prime}(s)}{f(s)}\cdot ds\quad\frac{1}{2}\int_{1}^{4}\frac{f^{\prime}(s)}{f(s)}\cdot ds \\
&=1+\left[\frac{f(4)}{f(3)}\right]^{\frac12}+\left[\frac{f(4)}{f(2)}\right]^{\frac12}+\left[\frac{f(4)}{f(1)}\right]^{\frac12} \\
&=1+\left[\frac{1+8(4)+(4)^2}{1+8(3)+(3)^2}\right]^{\frac{1}{2}}+\left[\frac{1+8(4)+(4)^2}{1+8(2)+(2)^2}\right]^{\frac{1}{2}}+\left[\frac{1+8(4)+(4)^2}{1+8(1)+(1)^2}\right]^{\frac{1}{2}} \\
&=1+1.2005+1.5275+1.4878=5.2158
\end{aligned}$$
(More pages, please download the Markdown source code file to view)