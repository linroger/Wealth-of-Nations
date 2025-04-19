---
tags:
  - ad_hoc_synthetics
  - duration
  - fixed_income
  - immunization
  - synthetic_instruments
aliases:
  - Ad Hoc Synthetics
  - Immunization Strategy
key_concepts:
  - Dynamic replication
  - First-order sensitivities
  - Immunization of portfolio
  - Matching sensitivities
  - Synthetic instrument creation
---

# 8.4 "AD HOC" SYNTHETICS  

Then how can we replicate the two-period bond? There are several answers to this question, depending on the level of accuracy a financial engineer expects from the "synthetic." An accurate synthetic requires dynamic replication which will be discussed later in this chapter. But, there are also less accurate, ad hoc, solutions. As an example, we consider a simple, yet quite popular way of creating synthetic instruments in the fixed income sector, referred to as the immunization strategy.  

In this section, we will temporarily deviate from the notation used in the previous section and let, for simplicity, $\delta=1$ ; so that $t_{i}$ represents years. We assume that there are three instruments. They depend on the same risk factors, yet they have different sensitivities due to strong nonlinearities in their respective valuation formulas. We adopt a slightly more abstract framework compared to the previous section and let the three assets $\{S_{1t},S_{2t},S_{3t}\}$ be defined by the pricing functions:  

$$
\begin{array}{r}{{S_{1}}_{t}=f(x_{t})}\ {{}}\ {{S_{2}}_{t}=g(x_{t})}\ {{}}\ {{S_{3}}_{t}=h(x_{t})}\end{array}
$$  

where the functions. $h(.),f(.)$ , and $g(.)$ are nonlinear. $x_{t}$ is the common risk factor to all prices.. $S_{1t}$   
will play the role of targeted instrument and $\{S_{2t},S_{3t}\}$ will be used to form the synthetic..  

We again begin with static strategies. It is clear that as the sensitivities are different, a static methodology such as the one used in Chapters. $_{3-7}$ cannot be implemented. As time passes,. $x_{t}$ will change randomly, and the response of. $S_{i t}$ $\mathbf{\Phi}_{t},i=1,2,3$ , to changes in $x_{t}$ will be different. However, one ad hoc way of creating a synthetic for. $S_{1t}$ by using $S_{2t}$ and $S_{3t}$ is the following.  

At time $t.$ we form a portfolio with a value equal to $S_{1t}$ and with weights. $\theta^{2}$ and $\theta^{3}$ such that the. sensitivities of the portfolio.  

$$
\theta^{2}S_{2t}+\theta^{3}S_{3t}
$$  

with respect to the risk factor $x_{t}$ are as close as possible to the corresponding sensitivities of $S_{1t}$ Using the first-order sensitivities, we obtain two equations in two unknowns, $\{\bar{\theta}^{2},\theta^{3}\}$  

$$
\begin{array}{c}{S_{1}=\theta^{2}S_{2}+\theta^{3}S_{3}}\ {\displaystyle\frac{\partial S_{1}}{\partial x}=\theta^{2}\frac{\partial S_{2}}{\partial x}+\theta^{3}\frac{\partial S_{3}}{\partial x}}\end{array}
$$  

A strategy using such a system may have some important shortcomings. It will in general. require cash injections or withdrawals over time, and this violates one of the requirements of a  

synthetic instrument. Yet, under some circumstances, it may provide a practical solution to problems faced by the financial engineer. The following section presents an example..  

# 8.4.1 IMMUNIZATION  

Suppose that, at time $t_{0}$ a bank is considering the purchase of the previously mentioned two-period discount bond at a price $B(t_{0},T_{2})$ $T_{2}=t_{0}+2$ . The bank can fund this transaction either by using 6-month floating funds or by selling short a three-period discount bond $B(t_{0},T_{3})$ $T_{3}=t_{0}+3$ or a combination of both. How should the bank proceed?  

The issue is similar to the one that we pursued earlier in this chapter-namely, how to construct a synthetic for $B(t_{0},T_{2})$ . The best way of doing this is, of course, to determine an exact synthetic. that is liquid and least expensive-using the 6-month funds and the three-period bond--and then, if a hedge is desired, sell the synthetic. This will also provide the necessary funds for buying. $B(t_{0},$ $T_{2})$ . The result will be a fully hedged position where the bank realizes the bid--ask spread. We will learn later in the chapter how to implement this "exact' approach using dynamic strategies.  

An approximate way of proceeding is to match the sensitivities as described earlier. In particular, we would try to match the first-order sensitivities of the targeted instrument. The following strategy is an example for the immunization of a fixed-income portfolio. As we saw in Chapter 3, the first-order sensitivities are called duration. In order to work with a simple risk factor, we assume that the yield curve displays parallel shifts only. This assumption rarely holds, but it is still used quite frequently by some market participants as a first-order approximation. In our case, we use it to simplify the exposition.  

# EXAMPLE  

Suppose the zero-coupon yield curve is flat at. $y=8\%$ and that the shifts are parallel. Then,. the values of the 2-year, 3-year, and 6-month bonds in terms of the corresponding yield $y$ will be given by  

$$
\begin{array}{l c r}{{\displaystyle B(t_{0},T_{2})=\frac{100}{(1+y)^{2}}=85.73}}\ {{}}\ {{\displaystyle B(t_{0},T_{3})=\frac{100}{(1+y)^{3}}=79.38}}\end{array}
$$  

$$
B(t_{0},T_{0.5})=\frac{100}{\left(1+y\right)^{0.5}}=96.23
$$  

Using the "long" bond $B(t_{0},T_{3})$ and the "short" $B(t_{0},T_{0.5})$ , we need to form a portfolio with initial cost 85.73. This will equal the time $t_{0}$ value of the target instrument, $B(t_{0},T_{2})$ We also want the sensitivities of this portfolio with respect to $y$ to be the same as the sensitivity of the original instrument. We therefore need to solve the equations  

$$
\theta^{1}B(t_{0},T_{3})+\theta^{2}B(t_{0},T_{0.5})=85.73
$$  

$$
\theta^{1}\frac{\partial B(t_{0},T_{3})}{\partial y}+\theta^{2}\frac{\partial B(t_{0},T_{0.5})}{\partial y}=\frac{\partial B(t_{0},T_{2})}{\partial y}
$$  

We can calculate the "current' values of the partials:  

$$
\begin{array}{c}{\displaystyle\frac{\partial B(t_{0},T_{0.5})}{\partial y}=\frac{-50}{(1+y)^{1.5}}=-44.55}\ {\displaystyle\frac{\partial B(t_{0},T_{2})}{\partial y}=-158.77}\ {\displaystyle\frac{\partial B(t_{0},T_{3})}{\partial y}=-220.51}\end{array}
$$  

Replacing these in Eqs. (8.15) and (8.16), we get  

$$
\begin{array}{c}{{\theta^{1}79.38+\theta^{2}96.23=85.73}}\ {{{}}}\ {{\theta^{1}(220.51)+\theta^{2}(44.55)=158.77}}\end{array}
$$  

Solving  

$$
\theta^{1}=0.65,\theta^{2}=0.36
$$  

Hence, we need to short 0.36 units of the 6-month bond and short 0.65 units of the 3-year. bond to create an approximate synthetic that will fund the 2-year bond. This will generate the needed cash and has the same first-order sensitivities with respect to changes in. $y$ at time $t_{0}$ . This is a simple example of immunizing a fixed-income portfolio..  

According to this, the asset being held, $B(t_{0},T_{2})$ , is "funded" by a portfolio of other assets, in a way to make the response of the total position insensitive to first-order changes in y. In this sense, the position is "immunized."  

The preceding example shows an approximate way of obtaining "synthetics" using dynamic. methods. In our case, portfolio weights were selected so that the response to a small change in the yield, $d y$ , was the same. But, note the following important point..  

The second- and higher-order sensitivities were not matched. Thus, the funding portfolio was not really an exact synthetic for the original bond $B(t_{0},T_{2})$ . In fact, the second partials. of the "synthetic' and the target instrument would respond differently to dy. Therefore, the portfolio weights $\theta^{i}$ $i=1$ , 2 need to be recalculated as time passes and new values of $y$ are observed.  

It is important to realize in what sense(s) the method is approximate. Even though we can adjust. the weights $\theta^{i}$ as time passes, these adjustments would normally require cash injections or withdrawals. This means that the portfolio is not self-financing..  

In addition, the shifts in the yield curve are rarely parallel, and the yields for the three instruments may change by different amounts, destroying the equivalence of the first-order sensitivities. as well.  
