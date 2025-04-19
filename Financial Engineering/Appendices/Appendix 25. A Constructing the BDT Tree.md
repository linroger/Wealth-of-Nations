---
title: Appendix 25. A Constructing the BDT Tree
tags:
  - bdt_tree
  - black_derman_toy
  - bond_pricing
  - yield_volatility
  - zero_coupon_bond
aliases:
  - BDT Tree Construction
  - Constructing BDT Tree
  - Verifying Yields
key_concepts:
  - 1-year yield calculation
  - 2-year bond price
  - BDT tree verification
  - Building tree outward
  - Yield volatility matching
---

# Appendix 25. A Constructing the BDT Tree

In this appendix we verify that the tree in Figure 25.5 matches the price information in Table 25.1. We also see how to construct the tree. For reference,  Figure 25.12 depicts the one-yean zero coupon bond prices at each node of the BDT tree.

## Verifying Yields

The rate at the first node is $10\%$ ,  which corresponds to the current 1-year yield We can compute the price (and thus yield) of the 2-year zero-coupon bond by starting

In year 2 and working backward. In year 1,  the 2-year bond will be worth either 1/(1+ 0.1322)=80.8832 or $1/(1+0.1082)=\$0.9023$ Thus,  the discounted expected price at time 0 is

$$\$0.9091\times (0.5\times\$0.8832+0.5\times\$0.9023)=\$0.8116$$

Figure 25.13 illustrates the tree corresponding to this calculation The price of the 3-year zero-coupon bond is computed in a similar way. Working backward from the year-3 nodes,  we have

$$\begin{aligned}\text{S 0.9091}&\times[0.5\times\$0.8832\times (0.5\times\$0.8321+0.5\times\$0.8798)\\&+0.5\times\$0.9023\times (0.5\times\$0.8798+0.5\times\$0.9153)]=\$0.7118\end{aligned}$$

###### FIGURE 25.12
The 1-year zero coupon bond prices at each node of the BDT tree.

 ![500](https://storage.simpletex.cn/view/f1eZBGyS3yANWH9xGS4yHKl8ecGClmDbs)

###### FIGURE 25.13
Tree illustrating the evolution of the 2-year zero-coupon bond,  based upon the prices in Figure 25.12.

 ![500](https://storage.simpletex.cn/view/fHlSF90LE993ACccSrKFMwSgfG5ggnUpu)

###### FIGURE 25.14
Tree illustrating the evolution of the 3-year zero-coupon bond,  based upon the prices in Figure 25.12.

 ![500](https://storage.simpletex.cn/view/fx0KG0Gzg1GuKgyzIflOozMEYPiQzyybp)

Figure 25.14 is the tree showing the evolution of the 3-year bond. Problem 25.8 asks you to verify that the tree in Figure 25.5 generates the correct 4-year zero-coupon bond price.

## Verifying Volatilities

The volatilities in Table 25.1 are yield volatilities. Thus,  to verify the volatilities implied by the tree,  we have to compute implied bond yields in year 1 and then compute the volatility For the 2-year bond (i.e.,  the 1-year bond in year 1),  the yield volatility using equation (25.45) is

$$0.5\times\ln\left (\frac{0.8832^{-1}-1}{0.9023^{-1}-1}\right)=0.1$$

From Figure 25.14,  the 3-year bond in year 1 (which will be a 2-year bond) will be worth either $\$0.7560$ ,        with a yield of $0.7560^{-1/2}-$ l=0.1501 or $0.8099^{-1/2}-1=0.1112$ The yield volatility is then

$$0.5\times\ln\left (\frac{0.1501}{0.1112}\right)=0.15$$

Both vield volatilities match the inputs in Table 25.1.

Problem 25.9 asks you to verify that the tree generates the correct 4-year yield volatility

## Constructing a Black-Derman-Toy Tree

We have verified that the tree inFigure 25.5 is consistent with the data in Table 25.1. Now we turn the question around: Given the data,  how did we generate the tree in the first place? The answer is that we started at early nodes and worked to the later nodes,  building the tree outward

The first node is given by the prevailing 1-year rate. Therefore,  the 1-year bond price is

$$\$0.9091=\frac{1}{1+R_0}$$

Thus,  $R_{0}=0.10$

For the second node,  the year-1 price of a 1-year bond is $P (1,        2,        r_{u})$ or $P (1,        2,        r_{d})$ We require that two conditions be satisfied

$$\begin{aligned}
\$0.8116& =\frac{1}{1+0.10}\left[0.5\times P (1,        2,        r_{u})+0.5\times P (1,        2,        r_{d})\right] \\
&=\frac{1}{1+0.10}\left (0.5\times\frac{1}{1+R_{1}e^{2\sigma_{1}}}+0.5\times\frac{1}{1+R_{1}}\right) s \\
\text{0.10}& =0.5\times\ln ([P (1,        2,        r_{u})^{-1}-1]/[P (1,        2,        r_{d})^{-1}-1]) \\
&=0.5\times\ln (R_{1}e^{2\sigma}/R_{1})
\end{aligned}$$

The second equation gives us $\sigma=0.1$ ,        and this value enables us to solve the first equation to obtain $R_{\mathrm{l}}=0.1082$

It is a bit messier to solve for the next set of conditions,        but conceptually we are still fitting two parameters ( $R_{2}$ and $\sigma_{2}$ ) to match two inputs (the 3-year yield and the 2-year yield volatility 1 year hence). The possible prices of a 2-year bond at the two nodes in year 1 arc $P (1,        3,        r_{u})$ and $P (1,        3,        r_{d}).$ Thus,        we have the two conditions

$$\begin{aligned}
\$0.7118& =\frac{1}{1+0.10}\left[0.5\times P (1,        3,        r_{u})+0.5\times P (1,        3,        r_{d})\right] \\
&=\frac{1}{1+0.10}\left[0.5\times\frac{1}{1.1322}\left (0.5\times\frac{1}{1+R_{2}e^{4\sigma_{2}}}+0.5\times\frac{1}{1+R_{2}e^{2\sigma_{2}}}\right)\right] \\
&+0.5\times\frac{1}{1.1082}\left (0.5\times\frac{1}{1+R_{2}e^{2\sigma_{2}}}+0.5\times\frac{1}{1+R_{2}}\right) \\
\text{0.15}& =0.5\times\ln ([P (1,        3,        r_{u})^{-1/2}-1]/[P (1,        3,        r_{d})^{-1/2}-1]) 
\end{aligned}$$

By iterating,        it is possible to solve $R_{2}$ and $\sigma_{2}$ . In the same way,        it is possible to solve for the parameters for each subsequent period.
