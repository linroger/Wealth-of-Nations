# 7.8 RECAP AND PREVIEW

In this chapter, we covered one of the simplest but most important methods of valuing options: the binomial model. We showed how the model clearly illustrates the process by which a dynamically adjusted portfolio enables one to assign a value to an option that must hold to prevent arbitrage. We showed how this process works in one- and two-period models. We illustrated how the early exercise of American options is accommodated within the binomial model.

In Chapter 8, we continue our coverage of the binomial model by looking at the. Greeks, which are the sensitivities of the options to the various factors that affect the value of an option.

# APPENDIX 7A

# Derivation of Equation (7.9)

We start with Equation (7.7), restated here as

$$
\frac{b_{c}S u-c_{u}}{1+r}=b_{c}S-c.
$$

Now substitute for $b$ , using Equation (7.5),

$$
\frac{\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S u-c_{u}}{1+r}=\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S-c.
$$

Rearranging, we have

$$
\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S-\frac{\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S u-c_{u}}{1+r}=c.
$$

Then we multiply through by $1+r_{:}$

$$
\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S(1+r)-\left(\frac{c_{u}-c_{d}}{S u-S d}\right)S u+c_{u}=c(1+r).
$$

Then we cancel $S$

$$
\left(\frac{c_{u}-c_{d}}{u-d}\right)(1+r)-\left(\frac{c_{u}-c_{d}}{u-d}\right)u+c_{u}=c(1+r).
$$

Using the common denominator $u-d$ , we obtain

$$
\begin{array}{r l}&{\frac{c_{u}(1+r)-c_{d}(1+r)-c_{u}u-c_{d}u+c_{u}u-c_{u}d}{u-d}=c(1+r)}\ &{\qquad\frac{c_{u}(1+r-d)+c_{d}[u-(1+r)]}{u-d}=c(1+r).}\end{array}
$$

Now, let us define $\phi$ as in Equation (7.9),

$$
\phi=\frac{1+r-d}{u-d}.
$$

Then $1-\phi$ is

$$
1-\phi=\frac{u-(1+r)}{u-d}.
$$

So the solution is

$$
c=\frac{\phi c_{u}+(1-\phi)c_{c}}{1+r}.
$$

which is Equation (7.9).

# Pascal's Triangle and the Binomial Model

Pascal's triangle has an infinite number of rows. An illustration of Pascal's triangle for the first five rows is provided in Figure 7B.1..

The elements of each row can be obtained from the row above it. For example, look at the 2 in the middle of the third row. It is obtained by summing the 1 above it to the left and the 1 above it to the right. Notice either 4 in the fifth row; each is obtained by summing the 1 above it to the left (or right) and the 3 above it to the right (or left). With the exception of the 1 in the first row, every number in the table is the sum of whatever appears above it to the left and above it to the right.14

Pascal's triangle contains the coefficients of the binomial expansion of $(a+b)^{n}$ . Here we illustrate the expansion for $n=0,\ldots,4$ below, which encompasses the portion of the triangle illustrated above. To link Pascal's triangle to option pricing, let us change the variables $^{a}$ and $b$ to the up and down factors, $\boldsymbol{\mathscr{u}}$ and $d$ as illustrated in Table 7B.1.

So how does Pascal's triangle come into play in option pricing? It tells us how many ways there are to reach a point after $_n$ periods. For example, in a one-period binomial model, there is only one way to go up and one way to go down. Note the coefficients 1 and 1 for the $n=1$ case. In the two-period model, the outcomes are up up, up down, down up, and down down. There is only one way to go up twice and one way to go down twice. But if you go up and down, you end up the same place as if you had gone down and then up. That is, $S u d=S d u$ . This would put you at the middle point of the binomial tree, as in Figure 7.4. There are two ways to get to that middle point. Thus, we get a coefficient of 2 on the ud term in row 2.

For a three-period binomial tree, you can go up three times, up twice and down once, down twice and up once, and down three times. There is only one way to go up three times:

![](5b29ecef9f20979489ea6f6610255feb15696a803166c4e64b35997b4a19c4d8.jpg)

FIGURE 7B.1 Pascal's Triangle (First Five Rows)
TABLE 7B.1 Coefficients of the Binomial Expansion


<html><body><table><tr><td>n</td><td>u(p + n)</td><td>Coefficients</td></tr><tr><td>0</td><td>1</td><td>1</td></tr><tr><td>1</td><td>p+n</td><td>1, 1</td></tr><tr><td>2</td><td>u²+2ud+d2</td><td>1,2, 1</td></tr><tr><td>3</td><td>εp+pne+pne+en</td><td>1,3,3,1</td></tr><tr><td>4</td><td>+p+pn+Pn9+pn+n</td><td>1,4, 6,4, 1</td></tr></table></body></html>

up up up. There are three ways to go up twice and down once: up up down or up down up or down up up. Thus, we get a coefficient of 3 on the $u^{2}d$ term in the table for $n=3$ There are three ways to go down twice and then up: down down up, down up down, and up down down. Hence, we get a coefficient of 3 applied to $u d^{2}$ . Finally, there is only one way to go down three times, down down down; hence, the coefficient is 1 on $d^{3}$

These coefficients enable us to fill out the details of the binomial model. We could even use them to skip some computational steps. For example, we previously explained how to derive the binomial value by starting at the expiration and working backward to the present. We showed the special case of a two-period model in which we skip the intermediate steps between the expiration and the present, Equation (7.22). Now, consider the four-period case. Using the $n=4$ row in the binomial expansion, we can derive the time 0 value from the possible time 4 values as follows:

$$
c=\frac{\phi^{4}c_{u^{4}}+4\phi^{3}(1-\phi)c_{u^{3}d}+6\phi^{2}(1-\phi)^{2}c_{u^{2}d^{2}}+4\phi(1-\phi)^{3}c_{u d^{3}}+(1-\phi)^{4}c_{d^{4}}}{(1+r)^{4}}.
$$

This calculation works for the path-independence case, such as for European options.. For path-dependent cases, such as for American options and some complex options, one. would have to start at the expiration and roll backwards to the present. We cannot skip or consolidate any paths.

For example, suppose you have the following parameters for a four-period binomial model for European options, $S=40$ $X=40$ $r=2.0\%$ per annum, $u=1.25$ $d=0.8$ and $\tau=4$ years. Thus, we once again have. $\phi=(1+r-d)/(u-d)=(1+0.02-0.8)/(1.25-\$ $0.8)=0.4889$ . The terminal payoffs for a call option are given as follows:.

$$
\begin{array}{r l}&{c_{u^{4}}=\operatorname*{max}\left(0,S u^{4}-X\right)=\operatorname*{max}\left[0,40\left(1.25^{4}\right)-40\right]=23.616}\ &{c_{u^{3}d}=\operatorname*{max}\left(0,S u^{3}d-X\right)=\operatorname*{max}\left[0,40\left(1.25^{3}0.8\right)-40\right]=14.4}\ &{c_{u^{2}d^{2}}=\operatorname*{max}\left(0,S u^{2}d^{2}-X\right)=\operatorname*{max}\left[0,40\left(1.25^{2}0.8^{2}\right)-40\right]=0}\ &{c_{u d^{3}}=\operatorname*{max}\left(0,S u d^{3}-X\right)=\operatorname*{max}\left\{0,40\left[(1.25)0.8^{3}\right]-40\right\}=0}\ &{c_{d^{4}}=\operatorname*{max}\left(0,S d^{4}-X\right)=\operatorname*{max}\left[0,40\left(0.8^{4}\right)-40\right]=0.}\end{array}
$$

The call value is

$$
\begin{array}{r l}&{c=\cfrac{\phi^{4}c_{u^{4}}+4\phi^{3}(1-\phi)c_{u^{3}d}+6\phi^{2}(1-\phi)^{2}c_{u^{2}d^{2}}+4\phi(1-\phi)^{3}c_{u d^{3}}+(1-\phi)^{4}c_{d^{4}}}{(1+r)^{4}}}\ &{=\cfrac{\left[0.4889^{4}(57.656)+4(0.4889^{3})(1-0.4889)(22.5)+6(0.4889^{2})(1-0.4889)^{2}(0)\right.}{\left.+4(0.4889)(1-0.4889)^{3}(0)+(1-0.4889)^{4}(0)\right.}}\end{array}
$$

We leave as a problem to find both the European and American put prices.

# QUESTIONS AND PROBLEMS

1 Suppose you have the following parameters related to a single-period binomial model, $S=32$ $X=30$ $r=4.0\%$ (annual, discrete compounding), $\tau=0.5$ years, $u=1.25$ , and $d=0.75$ . Suppose the call price in the market is 5.39 and the put price is 2.80. Calculate the option prices based on the binomial model and explain how any arbitrage would be captured.

2  Assume a single-period binomial model for a put option can be expressed as

$$
\begin{array}{l}{{\displaystyle p=\frac{\phi p_{u}+(1-\phi)p_{d}}{1+r}\mathrm{where}}}\ {{\displaystyle\phi=\frac{1+r-d}{u-d}.}}\end{array}
$$

Prove that the call option value can also be represented as

$$
\begin{array}{c}{{\displaystyle p=\frac{b_{_p}S u+p_{u}}{1+r}-b_{_p}S,\mathrm{where}}}\ {{\displaystyle b_{_p}=\frac{p_{d}-p_{u}}{S u-S d}.}}\end{array}
$$

3 Based on the information given in the chapter, we have the following market quotes,. $c_{Q}=11.43$ and $p_{\mathscr{Q}}=10.37$ . Recall $S=99$ $X=100$ $r=0.02$ $\delta=1$ $u=1.25$ , and $\bar{d=0.8}$ . Further, we found. $c=11.38$ and $p=10.42$ , thus the call price is too high and the put price is too low. Recall, arbitrageurs typically prefer to receive positive cash flow today with no chance of any future liability. Based on put-call parity, demonstrate. the appropriate arbitrage transaction.

4 Suppose you have the following parameters for a four-period binomial model for European options, $S=40$ $X=40$ $r=2.0\%$ per annum, $u=1.25$ $d=0.8$ and $\tau=4.0$ years. Calculate the European put value.

5 Again, suppose you have the following parameters for a four-period binomial model for European options, $S=40$ $X=40$ $r=2.0\%$ per annum,. $u=1.25$ $d=0.8$ , and $\tau=4.0$ years. Calculate the American put value. Further, compare the behavior of the hedge ratio for European and American puts.

6[Contributed by Paul Maloney] A portfolio manager takes a fairly simplified approach to stock valuation. They narrow it down to just two scenarios, a good year and a bad year. The stock is currently priced at 50. They believe there is a $34\%$ chance the stock will fall to 35. What is their estimate of the upside if the risk-free rate is $3.0\%?$ (Note: They are using risk-neutral valuation.)

# NOTES

1. An alternative approach would specify an asset priced at $S$ can go up to $S+u$ or down to $S+$ $d_{\mathrm{:}}$ an additive binomial approach.
2. There is another arbitrage opportunity based on put-call parity, but we leave that one as an end-of-chapter problem.
3. As we shall see in Chapter 9, we can also divide an option's life into a larger number of smaller periods. Thus, we can accommodate a fixed life, subdivided into smaller and smaller periods. Here, however, we simply extend the life of the option.
4. Henceforth, we shall always use $c_{u d}$ to represent both $c_{u d}$ and $c_{d u}$
5. It is important to note that recombining trees can also be produced through an additive process,. such as $S+u+d=S+d+u$ with $d<0$ The additive binomial lattice facilitates the convergence of the underlying variable to the normal distribution. Recall the multiplicative binomial lattice facilitates the convergence of the underlying variable to the lognormal distribution.
6. The general binomial expansion is $(a+b)^{n}$ . The coefficients are known as the elements of Pascal's triangle. This point is illustrated in Appendix 7B.
7. If the asset is a stock and the cash payment is a dividend, then exercise would occur immediately before the stock goes ex-dividend. Of course, early exercise is not necessarily optimal. Furthermore, the relationship can be expressed as either a continuous yield or a discrete y
9. The only time points that we have to check are those in which the option is in-the-money.
10. This number would be even larger if there were additional dividends over the life of the option You would add the present value of these dividends..
11. We have rounded the final answers to ease exposition, but all calculations are based on a spreadsheet with more precise values.
12. Specifically, the node growth rate is $2^{N}-2^{N-1}=2^{N-1}$ For example, if $N=0$ then the growth rate is $2^{10}-2^{9}=1,024-512=512$
13. Note the remainder stock price $S^{\prime}$ is simply the present value of dividends after the expiration of the option.
14. The ones on all rows except the first also follow this rule. If nothing appears above left or above right, simply treat it as zero.

# Calculating the Greeks in the Binomial Model

0ption pricing models are rimarily useful for dentifying the far value of an option, but of option portfolios. In particular, dealers that make markets in options need to be able to hedge the risk.1 Hence, they must know how sensitive their options are to changes in market conditions. Knowing these sensitivities enables them to balance that risk using other. instruments. These sensitivities are often known as the Greeks. This term arose because they are primarily identified with Greek letters, such as delta and gamma. End users, such as corporate executives, portfolio managers, and regulators, have all found these measures and other Greeks to be very useful. For example, in Chapter 18 we will see an application of option theory to gain insights on corporate default risk. Within this framework, the Greeks provide useful information regarding sensitivities of default risk to changes in market conditions. Numerous financial instruments contain option-like features where understanding the related Greeks will aid in financial decision-making.
