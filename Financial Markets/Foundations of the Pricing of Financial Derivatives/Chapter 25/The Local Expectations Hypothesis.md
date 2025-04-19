---
tags:
  - arbitrage
  - bond_market
  - leh
  - local_expectations_hypothesis
  - term_structure
aliases:
  - LEH
key_concepts:
  - Absence of arbitrage
  - Expected holding period return
  - Forward price and spot price
  - Local expectations hypothesis (LEH)
  - Risk-free rate
---

# 25.2 THE LOCAL EXPECTATIONS HYPOTHESIS

A similar sounding but more valid hypothesis for our purposes is the local expectations hypothesis (LEH). In its most general form, the LEH states that all bonds have the same. expected holding period return over the next period. Based on our notation, we have.

$$
\mathrm{LEH}\colon E_{t}[H P R(t,t+1,j)]=r(t,t+1);j=1,\ldots,n,
$$

where $H P R(t,t+1,j)$ denotes the continuously compounded holding period return over the period $t$ to $t+1$ for a $j$ maturity bond and $r(t,t+1)$ denotes the continuously compounded single-period spot rate over the period $t$ to $t+1$ . See Cox, Ingersoll, and Ross (1981, 1985a, 1985b) and Ingersoll (1987), where they compare the different versions of the expectations hypothesis, arguing that they are different in continuous and discrete time.

The LEH originates from a bond market in which the term structure does not permit investors to trade bonds to create arbitrage profits. In fact, the LEH is equivalent to the absence of arbitrage in the bond market. More formally, the LEH states that in the absence of arbitrage opportunities, the forward price of a zero-coupon bond will equal the expected. spot price if the expected spot price is taken under the equivalent martingale probabilities,. which are the artificial probabilities whose existence is guaranteed if there are no arbitrage. opportunities. The equivalence of the forward price and expected spot price is, however,. true only for one-period-ahead forward prices. In other words, the forward price of an $_n$ -period bond equals the expected spot price looking only one period ahead but no further. The expected returns, taken using the martingale probabilities, of any strategies involving. any bonds of any maturity, are equivalent and equal to the one-period spot rate, that is, the shortest interest rate in the market.

The reason the LEH holds only for one period ahead is that a true risk-free rate exists. only for the shortest holding period. One might think that a long-term zero-coupon bond. rate is risk-free, but interest rates change during the life of the bond, causing its value to fluctuate. The only true risk-free rate is over the shortest holding period. When we study. interest rates in a continuous time world, we shall see that this shortest holding period is an instant.

We shall demonstrate the LEH in a simple binomial world. The extension to a more complex continuous time model is feasible but a bit more difficult. We shall use continuously compounded rates, but the proof can be easily restructured for simple rates. For our. notation, let. $B(a,b)$ be the price at time $^{a}$ of a zero-coupon bond maturing at time $b$ . Let $r_{c}(a,b)$ be the rate observed on a bond at time $^{a}$ that matures at time $b$ . When $a=0$ , this. is a spot bond and a spot rate. For example, consider a one-period bond, whose price is given as

Price at time 0 of bond maturing at time 1

$$
B(0,1)=e^{-r_{c}(0,1)}.
$$

The value of this bond one period later is

Value at time 1 of bond maturing at time 1

$$
B(1,1)=1.
$$

Consider a two-period bond whose price is given as

Price at time 0 of bond maturing at time 2

$$
B(0,2)=e^{-2r_{c}(0,2)}.
$$

Its value one period later is

Price at time 1 of bond maturing at time 2

$$
B(1,2)=e^{-r_{c}(1,2)}.
$$

Now, let us introduce some uncertainty into the market. We assume that the one-period rate, $r_{c}(0,1)$ can go up to $r_{c}(1,2)^{+}$ or down to $r_{c}(1,2)^{-}$ . Thus, one period later, the original. two-period bond becomes a one-period bond with a price of.

$$
B(1,2)^{+}=e^{-r_{c}(1,2)^{+}}
$$

$$
B(1,2)^{-}=e^{-r_{c}(1,2)^{-}}.
$$

That is, we are now introducing uncertainty into the model in the form of two possible one-period future interest rates. The market moves one step forward, which produces a new interest rate, and, therefore, a new bond price, which can be either of the two previous Outcomes.

Now, let us consider how we could hold a bond for one period, without investing any. money of our own. That is, we want a self-financing strategy. One way is that we could buy. a one-period bond, financing it by selling an equivalent dollar amount of two-period bonds. When the one-period bond matures, we would pay off the two-period bonds. Alternatively,. we could buy a two-period bond, financing it by selling an equivalent dollar amount of. one-period bonds, and then sell the bond after one period..

For the first strategy, an arbitrage profit would be ensured if the rate of return $r_{c}(0,1)$ on the bond purchased is guaranteed to exceed the cost of financing it. Remember that the bond is financed by borrowing a two-period bond and buying it back one period later. This means that the financing strategy has an uncertain cost. That cost will be determined based on what the new one-period interest rate is. But if it were the case that the cost, in the worst-case scenario, is still less than the rate of return on the bond we buy, then we have earned an arbitrage profit. The worst-case scenario would be for the one-period rate to go down. This would drive up the price of the two-period bond that we sold to finance the position. Thus, the two-period bond, which then becomes a one-period bond, has a new price of $B(1,2)^{-}$ . The cost of the transaction expressed as one plus the percentage cost would be

$$
{\frac{B(1,2)^{-}}{B(0,2)}}.
$$

Hence, an arbitrage profit would be earned if

$$
e^{r_{c}(0,1)}>{\frac{B(1,2)^{-}}{B(0,2)}}.
$$

The left-hand side (LHs) is one plus the return from buying the one-period bond. The right-hand side (RHs) is the highest possible cost of financing the bond.

In the second strategy, we are buying a two-period bond, financing it with a one-period bond. Therefore, the financing cost is $r_{c}(0,1)$ for sure, but the return on the bond purchased is unknown. The worst-case scenario is for the one-period rate to go up, driving down the price of the two-period bond to its worst value, $B(1,2)^{+}$ . Therefore, one plus the worst one-period return on a two-period bond would be

$$
{\frac{B(1,2)^{+}}{B(0,2)}}.
$$

Therefore, an arbitrage profit would occur if

$$
e^{r_{c}(0,1)}<\frac{B(1,2)^{+}}{B(0,2)}.
$$

Thus, to prevent arbitrage, neither of these conditions must occur. Therefore, we must have

$$
\frac{B(1,2)^{+}}{B(0,2)}<e^{r_{c}(0,1)}<\frac{B(1,2)^{-}}{B(0,2)}.
$$

This statement implies that there is a set of weights, which we shall call $\phi$ and $1-\phi$ such that

$$
\phi\frac{B(1,2)^{+}}{B(0,2)}+(1-\phi)\frac{B(1,2)^{-}}{B(0,2)}=e^{r_{c}(0,1)}.
$$

The LHS can be viewed as a type of expected return on a two-period bond held for one period, which is then set equal to the RHS, which is the one-period rate. To interpret. the LHS as an expected value, however, we must recognize these weights as risk neutral or equivalent martingale weights. We call them risk neutral because the expression is the expected return that a risk-neutral investor would have. These are, therefore, the probabilities that would be used if current market prices held and investors were risk neutral. They. are also called equivalent martingale probabilities because they convert the discounted bond price into a martingale, which is a stochastic process with zero expected return. You. should recall that we studied this concept extensively when developing the procedures for. pricing options.

Of course, a martingale is a process with an expected return of zero. Equation (25.22) does not on the surface appear to be a martingale, because it shows that the expected return is the risk-free rate. Because the risk-free rate is known and constant, it is a simple matter to convert (25.22) to a martingale by dividing bye $e^{r_{c}(0,1)}$ , which is the same thing as multiplying by $B(0,1)$ . Hence, any process that has an expected return equal to the. risk-free rate can be viewed as a martingale..

To generalize this result, we could let the two-period bond be a bond of any maturity, say n. Then repeat the previous exercise, and we would easily see that the same result is obtained. A more formal proof can demonstrate that there is no bond trading strategy that permits arbitrage.

The result that the expected return, under the martingale probability, equals the one-period rate does not, however, apply to a strategy that spans more than one period. As noted, the reason for this result is that arbitrage is a risk-free strategy and there is no true risk-free rate beyond one period. Although buying a zero-coupon bond of maturity $n>1$ and holding it to maturity indeed leads to a risk-free return, arbitrage strategies require a rebalancing of the positions to properly offset the changing risk of the component instruments. This rebalancing requires trading in intermediate periods.

We have now demonstrated that the expected return, using the martingale probabil-. ities, equals the one-period rate. Next we demonstrate the other implication of the LEH, that the expected price of the two-period bond at time 1 is the forward rate. Let us express. Equation (25.22) as follows:

$$
\phi\frac{B(1,2)^{+}}{B(0,2)}+(1-\phi)\frac{B(1,2)^{-}}{B(0,2)}=\frac{1}{B(0,1)},
$$

noting thate $1/B(0,1)$ is $e^{r_{c}(0,1)}$ . Multiplying both sides by $B(0,2)$ , we obtain

$$
\phi B(1,2)^{+}+(1-\phi)B(1,2)^{-}=\frac{B(0,2)}{B(0,1)}.
$$

By definition, the RHS is the forward price. The LHS is the expected spot price under the martingale probabilities. So, the forward price is the expected spot price under the

martingale probabilities. In addition, this result generalizes to bonds of any maturity, but again, it applies over the next period, not beyond that horizon..

Finally, let us show that the equivalence of the forward price to the expected spot price does not imply equivalence of the forward rate to the expected spot rate. The RHS of Equation (25.24) can be written as follows:

$$
\frac{B(0,2)}{B(0,1)}=\frac{e^{-r_{c}(0,2)}}{e^{-r_{c}(0,1)}}=e^{-\left[r_{c}(0,2)-r_{c}(0,1)\right]}.
$$

Suppose we take the log of the RHS of Equation (25.24). So we must also take the log of the LHS, but it does not reduce to. $\phi r_{c}(1,2)^{+}+(1-\phi)r_{c}(1,2)^{-}$ , the expected spot rate. It is simply $\ln[\phi B(1,2)^{+}+(1-\phi)B(1,2)^{-}]$ . Although this value will be close to the expected. spot rate, it is not equivalent..
