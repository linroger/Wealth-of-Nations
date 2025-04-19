---
tags:
  - bond_spreads
  - century_bond_hedging
  - dv01_hedging
  - market_making
  - treasury_bonds
aliases:
  - DV01
  - Hedging Century Bond
  - NSC bonds
  - Treasury hedge
key_concepts:
  - Bond spread risk
  - DV01 and hedging
  - Hedging century bonds
  - Market maker example
  - Treasury bond face amount
---

# 4.3 HEDGING A CENTURY BOND: PART I  

Say that a market maker buys from a client. $\$10,000,000$ face amount of the NSC 4.10s of 05/15/2121 at the going bid price. The market maker does not turn around and immediately sell those bonds at market, because that would likely mean selling at the same bid price, leaving no overall profit from the trades. Instead, the market maker waits until other clients appear, who are willing to pay the higher ask price. In this way, the market maker earns the bid-ask spread for providing immediacy or liquidity both to the client who originally sells the bonds and to the clients who later buy the bonds.  

This strategy, however, exposes the market maker to the risk that the. price of the corporate bond falls before it can be sold. The typical solution is to hedge that risk by selling a liquid Treasury bond when buying the corporate, and then buying back that Treasury bond when selling the corporate. Because a liquid Treasury bond, by definition, has a very narrow bid-ask spread, this strategy protects the market maker against falling prices at the cost of that narrow bid-ask spread, which leaves much of the wider, corporate bid-ask spread as profit.  

The next question, therefore, is which Treasury bond to sell. Because,. as mentioned earlier, rates of different terms can behave differently, a rea-. sonable choice is to sell a Treasury bond with about the same maturity as. the corporate bond being hedged. In the particular situation at hand, however, there is no Treasury bond with a maturity anywhere near 100 years. The best the market maker can do, therefore, is to sell one of the longest. maturity Treasuries outstanding, like the 1.625s of 11/15/2050.  

The final question, then, is what face amount of Treasury bonds to sell against the purchase of. $\$10$ million face amount of the NSC bonds. One common solution is to ensure that the net Dv01 of the combined position is zero. In other words, choose the face amount of Treasuries such that, if rates change by one basis point, the value of the net position is unchanged. Denoting the face amount of the Treasury hedge by $F$ , and using the DV01s of the two bonds computed in Table 4.2,. $F$ is determined by the following equation,  

$$
F{\frac{0.199}{100}}+\S10,000,000{\frac{0.241}{100}}=0
$$  

The first term of (4.6) gives the change in the value of. $F$ face amount of Treasury bonds if rates fall by one basis point - 19.9 cents per 100 face amount, and, therefore, $F$ times 0.199/100 for $F$ face amount. The second term, along the same lines, gives the change in the value of the. $\$10$ million face amount of NSC bonds if rates fall by one basis point. The equation. as a whole, therefore, requires that the combined, hedged position neither gains nor loses value when rates fall by one basis point. And because the. hedged profit and loss $(\mathrm{P}\&\mathrm{L})$ when rates fall by some other number of basis. points is just that number of basis points times the left-hand side of (4.6), the. equation holds for that number of basis points as well (subject, of course, to the limitation of Dv01 as a local measure of interest rate sensitivity)..  

Solving Equation (4.6) for $F$  

$$
F=-\$10,000,0000\frac{0.241}{0.199}=-\S12,110,553
$$  

Hence, the market maker can hedge its $\$10$ million face amount of the NSC bonds by selling about $\$12.1$ million face amount of the Treasury bond. Intuitively, because the price of the NSC bonds changes by 24.1 cents per  

100 face amount per basis point, while the Treasury bonds change by only 19.9 cents, the market maker has to sell a larger face amount of Treasuries than it buys of NSC bonds to achieve a DV01-neutral position.  

To elaborate on how the hedge works, say that rates rise by five basis points after the market maker established the position. The NsC bonds fall in value, losing approximately $\$10,000,00000\times(0.241/100)\times5=\S120,500$ At the same time, the Treasury bonds also fall in value, gaining - because the market maker is short - approximately $\$12,110,553\times(0.199/100)\times5=$ $\$120,500$ . Hence, as intended, the overall, hedged position does not gain or lose money.  

In general, if the Dv01s of bonds A and B are $D V01^{A}$ and $D V01^{B}$ , then $F^{A}$ face amount of bond A is hedged with $F^{B}$ face amount of bond B such that,  

$$
\begin{array}{c}{{F^{A}\displaystyle\frac{D V01^{A}}{100}+F^{B}\displaystyle\frac{D V01^{B}}{100}=0}}\ {{F^{B}=-F^{A}\displaystyle\frac{D V01^{A}}{D V01^{B}}}}\end{array}
$$  

Equation (4.8) is the generalization of Equation (4.6). The general solution, Equation (4.9), reveals two intuitive points about DV01 hedging. First, a long position in bond A is hedged by a short position in bond B. Second, the bond with the higher DV01 is traded in smaller quantity. In the market making example, a long position in the NSC bonds is hedged by a short position in Treasury bonds, and, because the DV01 of the NSC bonds is greater. than that of the Treasury bonds,. $\$10$ million of NSC bonds is hedged by. $\$12.1$ million of Treasury bonds..  

The section concludes with a reminder of the assumptions behind the. DV01 hedge constructed here. First, rate shifts across terms are assumed to be proportional to those illustrated in Figure 4.1. If it turns out that the 100-year and 29.5-year par rates move differently than as assumed, the hedge will not work as intended. To the extent that this is a concern, the hedges described in Chapters 5 and 6 might be more appropriate. Second,. the spreads of the NSC and Treasury bonds to the base curve are assumed to be constant. If it turns out that these spreads behave differently, then, again,. the hedge will not work as intended. This concern is not as easily addressed.. A safer hedge would be to sell a corporate bond, whose spread is more highly correlated with the NSC bond spread than is the Treasury bond spread. But. hedging with a relatively illiquid corporate bond instead of an extremely liquid Treasury bond is likely to wipe out any market making P&L. Therefore, bearing spread risk for short periods of time may be an integral part of corporate bond market making and, in turn, may enter into the determination of bid-ask spreads in that market..  
