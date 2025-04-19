---
linter-yaml-title-alias: PSET 5 Financial Instruments
title: PSET 5 Financial Instruments
tags:
  - binomial_tree
  - convexity
  - delta_hedging
  - financial_instruments
  - option_payoff
  - option_pricing
  - replicating_portfolio
  - self_financing
  - stock_price
aliases:
  - Binomial Tree
  - Homework 5
  - PSET 5
  - Replicating Portfolio
key_concepts:
  - Convex relationship
  - Multi-period binomial tree
  - Option payoff computation
  - Portfolio P&L
  - Portfolio value calculation
  - Replicating portfolio setup
  - Self-financing portfolio
  - Stock price tree
---

### Financial Instruments Winter
# PSET 5 Financial Instruments

2024 John Heaton
Solution to Homework 5

### Part 1. Multi-period binomial tree
1. The intermediary can set up a replicating portfolio using delta hedging. At each node $(i,                        j)$，(with $i$ representing the period $i=0,                        …,                        I-1$ and $j$ representing the row $j=1,                        …\dot{i}$ for a given period) the intermediary can take a position equal to $\triangle_{i,                        j}$ stocks and $B_{i,                        j}$ bonds,  where
$$\triangle_{i,                        j}=\frac{c_{i+1,                        j}-c_{i+1,                        j+1}}{S_{i+1,                        j}-S_{i+1,                        j+1}}$$
$$B_{i,                        j}=\frac{1}{1+r}\cdot(c_{i+1,                        j}-\triangle_{i,                        j}\cdot S_{i+1,                        j})=\frac{1}{1+r}\cdot(c_{ i+1j+1}-\triangle_{i,                        j}\cdot S_{i+1,                        j+1})$$ …e member that by taking the positions (1) …d (2) the institution replicates a long call,  which exactly offsets the short position in the call.
(a）We can sta rt by r epresent ing the tr ee for the st ock price,  that is shown in Fig ure (1).
 ![500](https://storage.simpletex.cn/view/fyyg666isOQVVhplkPU976LrXANnionPx)
Figure 1: Stock price tree
Given the tree in Figure (1) we can compute option payoff at period $i=2$，a 8 represented in Figure (2)

 ![500](https://storage.simpletex.cn/view/ff1S4VLcHlx0cOyDGCalKPhKElGbmD8Ge)

```latex
\usetikzlibrary{arrows.meta,                        positioning}
\begin{document}
\begin{tikzpicture}[
    node distance=1.5cm and 2cm,                       
    every node/.style={font=\footnotesize},                       
    box/.style = {draw,                        rectangle,                        align=center},                       
    arrow/.style={-{Stealth}}
  ]
  \node[box] (S0) {$S_0 = 100$ \\ $\Delta_0 = 0.7732$ \\ $B_0 = -66.9474$ \\ $c_0 = 10.3768$};
  \node[box,                        above right=of S0] (Su) {$S_u = 110$ \\ $\Delta_u = 1.0000$ \\ $B_u = -95.2381$ \\ $c_u = 14.7619$};
  \node[box,                        below right=of S0] (Sd) {$S_d = 90.9091$ \\ $\Delta_d = 0.0000$ \\ $B_d = 0.0000$ \\ $c_d = 0.0000$};
  \node[box,                        above right=of Su] (Suu) {$S_{u.u} = 121.0000$ \\ $c_{u.u} = 21.0000$};
  \node[box,                        below right=of Su] (Sud) {$S_{u.d} = 100.0000$ \\ $c_{u.d} = 0.0000$};
  \node[box,                        above right=of Sd] (Sdu) {$S_{d.u} = 100.0000$ \\ $c_{d.u} = 0.0000$};
  \node[box,                        below right=of Sd] (Sdd) {$S_{d.d} = 82.6446$ \\ $c_{d.d} = 0.0000$};
  \draw[arrow] (S0) -- (Su);
  \draw[arrow] (S0) -- (Sd);
  \draw[arrow] (Su) -- (Suu);
  \draw[arrow] (Su) -- (Sud);
  \draw[arrow] (Sd) -- (Sdu);
  \draw[arrow] (Sd) -- (Sdd);
\end{tikzpicture}
\end{document}
```

Figure 2: Option value tree
We can then work backward in the tree and determine the position tobe invstec in stock and in bonds at each node that allow to replicate the period $i=2$ payoffs of the stock. For example in node"up",  at period $i=1$，wefind
$$\triangle_{u}=\frac{c_{u\cdot u}-c_{u\cdot d}}{S_{u\cdot u}-S_{u\cdot d}}=1.000$$
$$B_{u}=\frac{1}{1+r}\cdot(c_{u\cdot u}-\triangle_{u}\cdot S_{u\cdot u})=\frac{1}{1+0.05}\cdot(21-1\cdot121)=-95.2381$$
In the same way for node "down",  at period $i=1$ we find $\triangle_{d}=0.0000$ and $B_{d}=0.00000$. Given this we can compute the value of the replicating portfolio at period $i=1$. We find $V_{u}^{RP}= \triangle_{u}\cdot S_{u}+B_{u}=14.7619$ and $V_{d}^{RP}=\triangle_{d}\cdotp S_{d}+B_{d}=0$ Since the portfolio mirrors the period $i=2$ payoffs of the option,  then the value of the option,  then the period $i=1$ value of the option will be equal to the period $i=1$ value of the replicating portfolio. Therefore we can plug $V_{u}$ and $V_{d}$ in Figure (2). We can then work backward again and compute the position in stock and bond at period $i=0$. We find $\Delta_{0}=0.7732$ and $B_{0}=-66.9474$ whichleads to a value of the replicating portfolio (and of the option) equal to $V_{0}^{RP}=c_{0}=\triangle_{0}\cdot S_{0}+B_{0}=10.3768$
A summary of all the relevant quantities are reported in Figure (3).
 ![500](https://storage.simpletex.cn /view/fXze 865 NHkKZt 4 F 7 bxFqY 3 TnsnMghqRMV)
Figure 3: Summary tree

- b）Table (1) reports the period $i=0$ value of the replicating portfolio $V_{0}^{R}$ for different values of $S_{0}$

```latex
\begin{document}
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{|c|c|c|}
\hline
\textbf{Input} & \textbf{Change in call price} & \textbf{Change in put price} \\ \hline
Stock Price    & $\uparrow$                    & $\downarrow$                 \\ \hline
Strike Price   & $\downarrow$                  & $\uparrow$                   \\ \hline
Volatility     & $\uparrow$                    & $\uparrow$                   \\ \hline
Maturity       & $\uparrow$ or $\downarrow$    & $\uparrow$ or $\downarrow$   \\ \hline
Risk-free Rate & $\uparrow$                    & $\downarrow$                 \\ \hline
\end{tabular}
\end{document}
```

Table 1: Value of the replicating portfolio as a function of $S_{0}V^{RP}\left(S_{0}\right)$

1. The change in value of the portfolio is constant for values of $S_{0}$ below 100 and again constant but at a higher value for values of $S_{0}$ above 100. As a result the relationship between the option price and the current stock prices is convex. Figure (4) reports this result.
 ![500](https://storage.simpletex.cn/view/faHg9EDG1S5Anhb6rrN3i5rv3UPIxegq2)
Figure 4: Relationship between portfolio value and stock price
1. The relationship is convex. The "second derivative" is positive..
(c) The portfolio is “self-financing". To check this consider the following. At period $i=0$,  the replicating portfolio requires buying 0.7732 stocks and to short-selling 66.9474 units of zero couponbonds paying 1 dollar at period $i=2$ (which is the same as borrowing 66.9484 dollars). At the “"up-node (1,  1) the value of such position is
$$\triangle_0\cdot S_u+B_0\cdot(1+r)=0.7732+(-66.9474)\cdot(1+0.05)=14.7619$$
If we arenow atnode (1,  1) to hedge the option payoffs at period $i=2$,  we need to take aposition in stock equaltc
$$\triangle_{u}=\frac{c_{u\cdot u}-c_{u\cdot d}}{S_{u\cdot u}-S_{u\cdot d}}=1.000$$
and a o sition in zero couponbond paying 1 dollar at period $i=2$ equal to the value of such new portfolio is $V_{u}^{RP}=\triangle_{u}\cdot S_{u}+B_{u}=1.000\cdot110+(-95.2381)=$ 14.7619 that is exactly equal to the liquidation value of the portfolio that was set up at period $i=0$.
$$B_{u}=\frac{1}{1+r}\ cdot(c_{u\cdot u}-\triangle_{u}\cdot S_{u\cdotu })=\frac{1}{1+0.05}\cdot(21-1\cdot121)=-95.2381$$
We can do the same exercise for node (2,  1) and we see that
$$\triangle_0\cdot S_d+B_0\cdot(1+r)=V_d^{RP}=\triangle_d\cdot S_{1,                        2}+B_d=0$$
(d) The P&L of the portfolio can be computed by looking at the portfolio value. At node (1,  1),  the value of the replicating portfolio is $V_{u}^{RP}=14.7619$,  so if stock price goes up between period $i=0$ and period $i=1$，then the portfolio gains 14.7619-10.3768=4.39 dollars (which is the same value we loose on the short call position). If instead the stock price goes down the value of the portfolio in node (1,  2),  that is $V_{d}^{RP}=0$ goes to 0,  so we experience a loss equal to 10.3768. In the same way,  at time 2,  if the price of the stock is $S_{u\cdot u}=121$，then the portfolio gains 21.000-14.7619=6.2381 dollars,  while if the stock prices goes from $S_{u}=110$ to $S_{u\cdot d}=100$ then the portfolio value drops to 0 loosing 14.7619 dollars. Finally for node (1,  2) in both scenarios $S_{d\cdot u}$ and $S_{d\cdot d}$ the value of the portfolio does not change as it remains equal to 0
(e) If the option pays a $5\%$ dividend yield in period 1,  after the payment of the dividend,  the stock price will decrease by an amount equal to the dividend paid (which means a proportional decrease by $5\$）at period $i=1$. Ths happens because t he gross return of the stock is either $u$ or $a$. And the gross return comprises both capital gains and dividends. For example,  considering an “upmove" and letting $y$ denote the per period dividend yield we get:
$$\begin{array}{rcl}S_0\cdot u&=&CG+D\\\\&=&S_0\cdot u\cdot(1-y)+S_ 0\cdot u\cdot y\end{array}$$
Therefore,  in case of an up-movement,  the period $i=1$ stock price $S_{u}$ (after dividend) w ill be equal to $S_{u}=S_{0}\cdot u\cdot(1-y)=100\cdot1.1\cdot(0.05)=104.5000$ In the same way,  in case of a down-movement,  nth period $i=1$ stock price (again after dividend) will be $$S_{d}=\:S_{0}\cdot d\cdot(1-y)=\:100\cdot\frac{1}{1.1}\cdot(1-0.05)=\:86.3636$$
What happens next? The stock price will still have gross return of either $u$ OI d. Figure (5) shows the new tree for thestock price.
 ![500](htps:/ /storage. Simpletex. Cn/view /fad 2 pg 019 l 9 rLKAmwRXDU 51 YeY Ab 5 K 3 cZ)
Figure 5: Stock price tree in case of a $5\%$ dividend yield paid at $i=1$
Note that at period $i=2$ the tree is r ecombining,  that is $S_{u\  cdot d}=S_{d\cdot u}=95$ Given the stock price tree shown in Figure (5),  we can compute the option payoffs at period $i=2$. We get
$$\begin{array}{rcl}c_{u\cdot u}&=&14.9500\\\\c_{u\cdot d}=c_{d\cdot u}&=&0\\\\c_{d\cdot d}&=&0\end{array}$$
We can use the replicating portfolio formula to compute the option value. At period $i=1$ we can simply apply formulas (1) and (2) to the new tree,  as between period $i=1$ and period $i=2$ the stock will not pay any more dividends. We get
$$\triangle_u^{'}=0.7494$$
$$B_u^{'}=-67.8005$$
 $$\triangle_d^{\prime}=0$$
$$\triangle_{u}^{\prime}=0$$
----------------------------- -------------------------------------
Where we have addeda single quote todistinguish such valuesfrom the ones computed in point (1. A). We obtain the following replicating portfolio values
$$V_u^{RP}=10.5091$$
And
$$V_d^{RP}=0$$
It's easy to check that $RP$ replicates the option payoff at period $i=2$. For example for the up node,  the value of the portfolio is $V_{u\cdot u}^{RP}= \triangle _{u}^{^{\prime }}\cdot S_{u\cdot u}+ B_{u}^{^{\prime }}$. $(1+r)=0.7494\cdot114.95-67.8005\cdot(1+0.05)=14.95$. To find the period $i=0$ delta,  that is $\Delta_{0}^{'}$,  we need to consider the dividend. Indeed if we buy $\triangle_{0}^{'}$ stocks tomorrow we will gain from the price appreciation and we will also get $\triangle_{0}^{'}\cdot y$ dividends. If for example the stock price increases,  as shown in equation (3) this will imply a gross return equal to $S_{0}\cdot u$. Therefore we can compute the delta as if no dividend was paid (that is using the old,  pre-dividend stock price tree)) while we can apply formula (2) - still using the stock price with no dividend - to compute the position in bonds. We get
$$\triangle_0^{'}=\frac{V_u^{RP}-V_d^{RP}}{S_u^{old}-S_d^{old}}=\frac{10.5091}{110.0000-90.9091}=0.5505$$
$$B_0'=\frac{1}{1+0.05}\cdot(10.5091-0.5505\cdot110)=-47.6602$$
The value of the option will therefore be $c_{0}^{'}=V_{0}^{RP}=\triangle{0}^{'}\cdot S_{0}+B_{0}^{'} =0.5505$ 100-47.6602=7.3873
Figure (6) shows a summary of all relevant quantities in case of a $5\%$ dividend
 ![500](https://storage.simpl etex. Cn/view/fPf 8 Gga 1 cOes 7 99 bkFFgiq 8 HscnEGe 7 V)
Figure 6: Summary tree in case of $5\%$ dividend yield paid at $i=1$
(f）To compute the option price in case of a fixed dollar dividend,  we can apply the same logic as in point (1. E). The only difference tho ugh is that the tree does not recombine at period $i=2$. Figure (7) presents a ummary tree,  which shows that the option value in this case is $c_{0}=7.6591$
 ![500](https://storage.simpletex.cn/view/faqCthGF2N720UTAANTWtwkIkF3fchDpM)
Figure 7: Summary tree in case of a 5 dollars constant dividend paid at $i=1$
------------------------------------------------------------------
### Part 2 - Black and Scholes (and Merton) Formula

(1) Simply apply the formula. For the call and for the put the prices ae given respectively by
$$c^{BS}=S_ {0}\cdot N\left(d_{1}\right)-K\cdot e^{-r\cdot T}\cdot N\left(d_{2}\right)$$
$$p^{BS}=K\cdot e^{-r\cdot T}\cdot N\left(-d_{2}\right)-S_{0}\cdot N\left(-d_{1}\right)$$
Where
$$d_1=\frac{ln\left(\frac{S_0}{K}\right)+\left(r+\frac{\sigma^2}{2}\right)\cdot T}{\sigma\cdot\sqrt{T}}$$
And
$$d_2=d_1-\sigma\cdot T\sqrt{-}$$
applying formulas (4) and (5) we get $c^{BS}=4.7594$ and $p^{BS}=0.8086$
(2) Figure (8) shows the results. The relationship between options premium and stock price is convex.
 ![500](https://storage.simpletex.cn/view/fV5qNLxfifFcxyP32nR7DGx6YGBfqBNUi)
Figure 8: Black and Scholes options prices for different stock prices
(3) The results are shown in the following Table 2.

```latex
\begin{document}
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{|c|c|c|}
\hline
\textbf{Input} & \textbf{Change in call price} & \textbf{Change in put price} \\ \hline
Stock Price    & $\uparrow$                    & $\downarrow$                 \\ \hline
Strike Price   & $\downarrow$                  & $\uparrow$                   \\ \hline
Volatility     & $\uparrow$                    & $\uparrow$                   \\ \hline
Maturity       & $\uparrow$ or $\downarrow$    & $\uparrow$ or $\downarrow$   \\ \hline
Risk-free Rate & $\uparrow$                    & $\downarrow$                 \\ \hline
\end{tabular}
\end{document}
```

Table 2: Sensitivity of Black and Scholes option prices to inputs
In addition,  the following Figures depict the relationships between options prices and the inputs
![[Finder 2024-09-19 09.36.11.png]]
Figure 9: Black and Scholes options prices for different strike prices

------------ ------------------------------------------------------

 ![500](https://storage.simpletex.cn/view/fT6GKr24xqxbcvk57LNsVukNeMVnSGvfb)
Figure 10: Black and Scholes options prices for different return volatilities
[[Attachments/PSET 5 Solution-1.png|Financial Instruments/Assignments/Solutions/PSET 5 Solution (attachments)/PSET 5 Solution-1.png]]
Figure 11: Black and Scholes options prices for different maturities
 ![500](https://storage.simpletex.cn/view/ftxNzEvVKl2ual7eAEyUeSq79A7VItZQN)
Figure 12: Black and Scholes options prices for different interest rates

- (4). In order to hedge a short position in a put,  we need to set up a portfolio that mirrors the value of a long puT. We can do that via delta hedging. Since we know that the delta for a long put is $-N\left(-d_{1}\right)=-0.2887$,  in our case we have to short 0.2887 stocks. In addition since when we wrote the put we have received the premium equal to 1.1579 the replicating portfolio requires to invest $B_{0}=p-\triangle_{0}\cdot S_{0}=1.1579+0.2887\cdot42=$ 13.2841 in zero coupon bonds. As a double check,  the value of the replicating portfolic is
$$V_0^{RP}=B_0+\triangle_0\cdot S_0=13.2841-0.2887\cdot42=1.1579$$
