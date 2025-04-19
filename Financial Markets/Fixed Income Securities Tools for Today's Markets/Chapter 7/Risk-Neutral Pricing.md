---
tags:
  - arbitrage
  - contingent_claim
  - interest_rate_process
  - option_pricing
  - risk_neutral_pricing
aliases:
  - Risk-Neutral Method
  - Risk-Neutral Valuation
key_concepts:
  - Arbitrage pricing
  - Contingent claim valuation
  - Drift in interest rates
  - Expected discounted value
  - Risk-neutral probabilities
---

# 7.3 RISK-NEUTRAL PRICING  

Risk-neutral pricing is a technique that modifies an assumed interest rate. process, like the one assumed at the start of this chapter, so that any contingent claim can be priced without having to construct and price its replicating. portfolio. Because the technique requires that the original interest rate pro-. cess be modified only once, and because this modification requires no more effort than pricing a single contingent claim by arbitrage, risk-neutral pric-. ing is an extremely efficient way to price many contingent claims under the same assumed rate process.  

In the example of this chapter, the price of a one-year zero does not. equal its expected discounted value: its price is. $\$978.842$ , computed from the given one-year spot rate of. $2.15\%$ , while its expected discounted value is. $\$980.302$ , as derived in Equation (7.2). The probabilities of 0.5 for the up-. and down-states are the assumed true or real-world probabilities. But there are other probabilities, called risk-neutral probabilities, which do cause the. expected discounted value to equal the market price. To find these probabilities, let the risk-neutral probabilities in the up- and down-states be. $\boldsymbol{p}$ and $(1-p)$ , respectively. Then, solve the following equation,  

$$
{\frac{{\frac{{\S987.654\phi+\S992.556(1-\phi)}{\left({\bf1}+{\frac{.02}{2}}\right)}}}={\S978.842}}{{\left({\bf1}+{\frac{.02}{2}}\right)}}}
$$  

to find that $p=.8009$ . Hence, under the risk-neutral probabilities of .8009 and .1991, the expected discounted value does equal the market price.  

Risk-neutral probabilities can also be described in terms of the drift in interest rates. Under the true probabilities, there is a $50\%$ chance that the six-month rate rises from $2\%$ to $2.50\%$ , and a $50\%$ chance that it falls from $2\%$ to $1.50\%$ . Hence, the expected change in the six-month rate, or the drift of the six-month rate, is zero. Under the risk-neutral probabilities, there is an $80.09\%$ chance of a 50-basis point increase and a $19.91\%$ chance of a 50-basis point decrease, for an expected change of 30.09 basis points. Hence, the drift of the six-month rate under these probabilities is 30.09 basis points.  

As pointed out in the previous section, the expected discounted value of the option payoff is $\$1.2653$ , while the arbitrage price is $\$0.504$ . But if expected discounted value were computed using the risk-neutral probabilities, the resulting option value would equal its arbitrage price,  

$$
\frac{.8009\times\S0+.1991\times\S2.555831}{\left(1+\frac{.02}{2}\right)}=\S0.504
$$  

The fact that the arbitrage price of the option equals its expected. discounted value under the risk-neutral probabilities is not a coincidence. In general, to value contingent claims by risk-neutral pricing, proceed as follows. First, find the risk-neutral probabilities that equate the prices of the underlying securities to their expected discounted values. (In the simple. example here, the only risky, underlying security is the one-year zero.) Second, price the contingent claim by expected discounted value under these risk-neutral probabilities. The remainder of this section describes intuitively why risk-neutral pricing works. Since the argument is a bit complex, it is broken up into four steps:.  

1. Given trees for the underlying securities, the price of a security that is. priced by arbitrage does not depend on investors' risk preferences. The reasoning is as follows..  

A security is priced by arbitrage if its cash flows can be replicated by some portfolio of underlying securities. Under the assumed process for interest rates in this chapter, the bond option is priced by arbitrage. By contrast, it is unlikely that a specific common stock can be priced by arbitrage, because no portfolio of underlying securities can mimic the idiosyncratic fluctuations of a single common stock's market value.  

If a security is priced by arbitrage, and if everyone agrees on the price. evolution of the underlying securities, then everyone agrees on the repli-. cating portfolio. In the option example, both an extremely risk-averse, retired investor and a professional gambler agree that a portfolio of $\$521.4375$ face of one-year zeros and -. $\$515.0000$ face of six-month zeros replicates the option. And because they agree both on the com-. position of the replicating portfolio and on the prices of the underlying. securities, they must also agree on the price of the option..  

2. Imagine an economy that has the same current bond prices and possible future values of the six-month rate as the true economy. The imaginary economy is different, however, in that its investors are risk neutral. Unlike investors in the true economy, then, investors in the imaginary economy do not penalize securities for risk: they price securities by expected discounted value. In particular, under the prob-. abilities in the imaginary economy, the expected discounted value of the one-year zero equals its market price. But, by Equation (7.7), the expected discounted value of the one-year zero does equal its market.  

price under the risk-neutral probabilities of .8009 and .1991. Hence, these risk-neutral probabilities are the probabilities in the imaginary economy.  

3. The price of the option in the imaginary economy, like any other security in that economy, is computed by expected discounted value. Since the probability of the upstate in that economy is .8009, the price of the option in that economy is given by Equation (7.8) and is $\$0.504$  

4. Step 1 implies that, given the prices of the six-month and one-year zeros, as well as possible values of the six-month rate, the price of an option does not depend on investor risk preferences. Therefore, because the real and imaginary economies have the same bond prices and the same possible values for the six-month rate, the option price must be the same in both economies. In particular, the option price in the real economy must also equal $\$0.504$ . More generally, the price of a derivative in the. real economy may be computed by expected discounted value under the risk-neutral probabilities.  

# 7.4ARBITRAGE PRICING IN A MULTI-PERIOD SETTING  

Maintaining the binomial assumption, Figure 7.3 extends the tree from the previous section for another six months. This tree is called a recombining tree, because an up-move followed by a down-move, to the up-down state, lands in the same place as a down-move followed by an up-move, to the down-up. state. Trees for which this is not the case are said to be nonrecombining. While nonrecombining trees might represent economically reasonable dynamics,. they tend to be avoided as difficult or even impossible to implement. After six months there are two possible states, after one year there are four, and after $N$ semiannual periods there are $2^{N}$ possibilities. A tree with enough semiannual steps to price 10-year securities has, in its rightmost column alone, over 500,000 nodes, and to price 20-year securities, over 500 billion. Furthermore, as discussed later in the chapter, it is often desirable to reduce the time interval between dates substantially. In short, even with modern computers, trees that grow this quickly are computationally unwieldy. This does not mean that the effects that seem to give rise to nonrecombining trees - like volatilities that change across states - cannot be modeled. It does mean, however, that such effects have to be implemented in more efficient ways..  

Returning to the recombining format, as trees grow it becomes convenient to develop a notation with which to refer to particular nodes. One convention is as follows. The dates, represented by columns of the tree, are numbered from left to right starting with 0. The states, represented by rows of the tree, are numbered from bottom to top, also starting from 0. For example, in Figure 7.3, the six-month rate on date 2, state 0 is $1\%$ . The six-month rate on state 1 of date 1 is. $2.50\%$  

![](366d0bab2488b1d41d21c870b2d8c673d6a51b186618010eab8da96b50218dd4.jpg)  
FIGURE 7.3 A Recombining Binomial Rate Tree.  

Continuing where the option example left off, having derived the. risk-neutral tree for pricing a one-year zero, the goal is to extend the tree. to price a 1.5-year zero assuming that the 1.5-year spot rate is $2.25\%$ Ignoring the probabilities for a moment, several nodes of the 1.5-year zero price tree can be written down immediately, as shown in Figure 7.4. On date 3, the zero with an original term of 1.5 years matures and is worth its. face value of $\$1,000$ . On date 2, the value of the then six-month zero equals its face value discounted for six months at the then-prevailing spot rates of $3\%,2\%$ , and $1\%$ , in states 2, 1, and 0, respectively,  

$$
{\frac{\$1,000}{1+{\frac{.03}{2}}}}=\$985.22
$$  

$$
{\frac{\$1,000}{1+{\frac{.02}{2}}}}=\$990.10
$$  

$$
{\frac{\$1,000}{1+{\frac{.01}{2}}}}=\$995.02
$$  

![](1275de64ba63c060ff957811db51ee299b033575e48724a21d58a2455349a82b.jpg)  
FIGURE 7.4 Price Tree for a 1.5-Year Zero Coupon Bond.  

Finally, on date 0, the 1.5-year zero equals its face value discounted at the given, 1.5-year spot rate,  

$$
\frac{\S1\mathrm{,000}}{\left(1+\frac{\mathrm{.0225}}{2}\right)^{3}}=\mathbb{5}\mathbb{96}6\mathrm{.9954}
$$  

The prices of the zero on date 1 in states 1 and O are denoted in Figure 7.4 by $P_{1,1}$ and $P_{1,0}$ , respectively. These one-year zero prices are not known at this point.  

The previous section showed that the risk-neutral probability of an up-move on date 0 is 0.8009. Letting $q$ be the risk-neutral probability of an up-move on date 1, and, for the purposes of this section, making the simplifying assumption that the probability of moving up from state O is the same as the probability of moving up from state 1, the resulting tree is shown in Figure 7.5.  

By definition, the expected discounted value under risk-neutral probabilities recovers market prices. With respect to the 1.5-year zero price on. date 0, this requires that,  

$$
\frac{.8009P_{1,1}+.1991P_{1,0}}{1+\frac{.02}{2}}=\S966.995
$$  

And with respect to the prices of a then one-year zero on date 1,  

$$
\begin{array}{l}{{P_{1,1}={\displaystyle\frac{\S985.222q+\S990.099(1-q)}{1+{\displaystyle\frac{.025}{2}}}}~}}\ {{P_{1,0}={\displaystyle\frac{\S990.099q+\S995.025(1-q)}{1+{\displaystyle\frac{.015}{2}}}}~}}\end{array}
$$  

![](0a5bc6ef6f2a93662d0fdb0abacbdf5802a9aec59f42bd2cdb93893a8657697b.jpg)  
FIGURE 7.5 Price Tree for a 1.5-Year Zero Coupon Bond, with Probabilities.  

Substituting Equations (7.14) and (7.15) into Equation (7.13) results in a linear equation in the one unknown, $q$ , which can be solved to find that $q=0.6520$ . Therefore, the risk-neutral interest rate process is summarized by the tree in Figure 7.6. Furthermore, any contingent claim that depends on the six-month rate in six months and in one year may be priced by computing its discounted expected value along this tree. An example is given in the next section.  

The difference between the true and risk-neutral probabilities may once again be described in terms of drift. From dates 1 to 2, the drift under the true probabilities is zero. Under the risk-neutral probabilities, the drift is computed from a $65.20\%$ chance of a 50-basis-point increase in the six-month. rate and a $34.80\%$ chance of a 50-basis-point decline in the rate. These numbers give a drift or expected change of 15.20 basis points..  

Substituting $q=0.6520$ back into Equations (7.14) and (7.15) completes the tree for the price of the 1.5-year zero, which is shown in Figure 7.7. It follows immediately from this tree that the one-year spot rate in six months may be either $2.5754\%$ or $1.5754\%$ , because,  

$$
\begin{array}{l}{{\S974.735={\frac{\S1.000}{\left(1+{\frac{2.5754\mathcal{H}}{2}}\right)^{2}}}}}\ {{\S984.430={\frac{\S1.000}{\left(1+{\frac{1.5754\mathcal{H}}{2}}\right)^{2}}}}}\end{array}
$$  

The fact that the possible values of the one-year spot rate can be. extracted from the tree is at first surprising. The starting point of the example is the date 0 values of the. $0.5\cdot,1-$ , and 1.5-year spot rates, along. with assumptions about the evolution of the six-month rate over the next years. But because this information, in combination with arbitrage. or risk-neutral arguments, is sufficient to determine the price tree of the 1.5-year zero, it is also sufficient to determine the possible values of the one-year spot rate in six months. Put another way, having specified initial.  

![](d8d12f91c9e74acdeaeef1ec78c2ee22cb94c63f7d11bb92360d396f0a287f48.jpg)  
FIGURE 7.6 Risk-Neutral Process for the Six-Month Rate.  

![](c6ecc1837616414ffac4333e73344bc799583540762603f85041c4bd313847d0.jpg)  
FIGURE 7.7 Final Price Tree for a 1.5-Year Zero Coupon Bond, with Probabilities.  

spot rates and the evolution of the six-month rate, a modeler may not make any further assumptions about the behavior of the one-year rate.  

The six-month rate process completely determines the one-year rate process here, because the model presented has only one factor. Writing down a tree for the evolution of the six-month rate alone implicitly assumes that prices of all fixed income securities can be determined by the evolution of that rate. A multi-factor term structure model is presented in Chapter 9.  

This section concludes with two additional observations about multi-period settings. First, extending the tree to any number of dates requires assumptions about the future possible values of the short-term rate and the calculation of risk-neutral probabilities that recover a given set of bond prices. Second, the composition of replicating portfolios depends on date and state. For example, the replicating portfolio of a derivative as of date O is usually different from its replicating portfolio on date 1, state 0,. and different again from its replicating portfolio on date 1, state 1. From a trading perspective, this means that replicating portfolios must be adjusted as time passes and as interest rates change. These adjustments are known as dynamic replication, in contrast to the static replication strategies of earlier chapters, like replicating a coupon bond with an unchanging portfolio of two other coupon bonds of the same maturity..  

# 7.5PRICING A CONSTANT-MATURITYTREASURY SWAP  

Equipped with the tree in Figure 7.7, this section prices a $\$1,000,000$ stylized constant-maturity Treasury (CMT) swap struck at $2\%$ . This swap pays,  

$$
\Psi1,000,000\frac{y_{\mathrm{C}M T}-2\%}{2}
$$  

every six months until it matures, where $y_{C M T}$ is the semiannually compounded yield -- of a predetermined maturity -- on the payment date. This example prices a one-year CMT swap on the six-month yield, though, in practice, CMT swaps trade most commonly on the yields of the most liquid bonds, for example, on two-, five- and 10-year Treasury yields.  

Because six-month semiannually compounded yields equal six-month spot rates, rates from the tree of the previous section can be substituted into Equation (7.18) to calculate the payoffs of the CMT swap. On date 1, the state 1 and state 0 payoffs are, respectively,  

$$
\begin{array}{r l}&{\S1,000,000\frac{2.50\%-2\%}{2}=\S2,500}\ &{\S1,000,000\frac{1.50\%-2\%}{2}=-\S2,500}\end{array}
$$  

Similarly on date 2, the state 2, 1, and 0 payoffs are, respectively,  

$$
\begin{array}{l}{{\S1,000,000\frac{3\mathcal{H}_{\mathrm{~-~}}2\mathcal{H}_{\mathrm{~~}}}{2}=\S5,000}}\ {{\mathrm{~}}}\ {{\S1,000,000\frac{2\mathcal{H}_{\mathrm{~-~}}2\mathcal{H}_{\mathrm{~}}}{2}=\S0}}\ {{\mathrm{~}}}\ {{\S1,000,000\frac{1\mathcal{H}_{\mathrm{~-~}}2\mathcal{H}_{\mathrm{~}}}{2}=-\S5,000}}\end{array}
$$  

The possible values of the CMT swap at maturity, on date 2, are given. by Equations (7.21) through (7.23). The possible values on date 1 are given. by the expected discounted value of the date 2 payoffs under the risk-neutral probabilities plus the date 1 payoffs given by (7.19) and (7.20). The resulting. date 1 values in states 1 and 0 are, respectively,.  

$$
\begin{array}{r l}&{\frac{\hphantom{x x}\cdot6520\times\hphantom{0x}\S5,000+.3480\times\S0}{1+\frac{.0250}{2}}+\S2,500=\S5,719.52}\ &{\frac{\hphantom{x x}\cdot6520\times0+.3480\times(-\S5,000)}{1+\frac{.0150}{2}}-\S2,500=-\S4,227.29}\end{array}
$$  

Finally, the value of the swap on date O is the expected discounted value, under the risk-neutral probabilities, of the date-1 payoffs, given by Equations (7.24) and (7.25),  

$$
{\frac{.8009\times{\S}{5},719.52+.1991\times(-{\S}4,227.29)}{1+\frac{.0200}{2}}}=53,702.11
$$  

![](5cf803818dc6e4af9b7702fb5b88b546adb425bbd7e2c72eedd4a70e64a7bafc.jpg)  
FIGURE 7.8 Price Tree for a Stylized CMT Swap.  

The tree in Figure 7.8 summarizes the value of the stylized CMT swap. over dates and states. A value of. $\$3,702.11$ for the CMT swap might seem surprising at first. After all, the cash flows of the CMT swap are zero at. a rate of $2\%$ , and $2\%$ is, under the true probabilities, the average rate on each date. The explanation, of course, is that the risk-neutral probabilities,. not the true probabilities, determine the arbitrage price of the swap. The. expected discounted value of the swap under the true probabilities can be. computed by following the steps leading to Equations (7.24) through (7.26) but using the probability O.5 for all up- and down-moves. The result of these calculations does give a value close to zero, namely,. $-\$6.07$  
