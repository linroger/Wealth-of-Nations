---
title: Appendix 5.A Taxes and the Forward Price
---

# Appendix 5.A Taxes and the Forward Price

The formulas in this chapter—and in the book to this point—have ignored taxes. In this appendix we show how taxes enter into the theoretical formula for the forward price,  and explain why in practice these tax adjustments are never used. The impact of taxes on derivative prices was studied by Scholes (1976) and Cornell and French (1983),  who showed that prices depend upon taxes when capital gains,  dividends and interest are taxed at different rates. However,  a party such as a broker-dealer,  who is taxed identically on all forms of income,  will have a fair price that is independent of taxes.

Suppose that capital gains on a stock are taxed at the rate $l_{g}$ ,  gains on the forward contract at $\tau_f$ ,  dividends at the rate $\tau_{d}$ ,  and interest at the rate $\tau_{i}$ .Consider an investor who goes long $(1-\tau_{g})/(1-\tau_{f})$ forward contracts (we will see why in a moment) and hedges by selling one share today. The investor thus receives $S_{0}$ ,  which can be invested to earn the risk-free rate.

In 1 year,  the investor closes the transaction by buying a share and paying the forward price. After-tax income is
$$S_0[1+r(1-\tau_i)]-[S_1-\tau_g(S_1-S_0)]-Div(1-\tau_d)+[S_1-F_{0,   1}]\frac{1-\tau_g}{1-\tau_f}(1-\tau_f)$$
The first bracketed term is the after-tax value of invested short-sale proceeds,  the second is the after-tax cost of buying the share to close the short sale,  the third is the after-tax dividend that must be paid to the share-lender,  and the fourth is the after-tax gain on $(1-\tau_{g})/(1-\tau_{f})$ futures contracts. If the transaction is to generate no-arbitrage profits,  the forward price must be set so that equation (5.20) equals zero. Thus,  the after-tax zero-profit forward price is
$$F_{0,   1}=S_0\left(1+r\frac{1-\tau_i}{1-\tau_g}\right)-Di\nu\frac{1-\tau_d}{1-\tau_g}$$
Note that the tax on the forward contract does not enter the expression at all! The reason is that since the forward contract has a zero value,  it is possible to offset the tax by entering intc additional forward contracts—this is the reason for going long $(1-\tau_{g})/(1-\tau_{f})$ contracts against one short share. We in effect make the forward contract be taxed at the same rate as the stock.
$$F_{0,   T}=S_{0}e^{[r(1-\tau_{i})/(1-\tau_{g})-\delta(1-\tau_{d})/(1-\tau_{g})]T}$$
The important insight is that broker-dealers are marked-to-market for tax purpose and face the same tax rate on all forms of income —-i.e.,  $\tau_{i}=\tau_{g}=\tau_{d}$ . Thus,  equation (5.21 becomes
$$F_{0,   1}=S_0\left(1+r\right)-Div$$
The same as equation (5.5).

# Appendix 5.C Forward and Futures Prices When Interest Rates Are Random

This appendix formalizes the difference between forward and futures prices and shows the relationship between them when interest rates are stochastic. We will use the following notation:

$$\begin{aligned}
&F_{t,   T} =\mathrm{~Forward~price} \\
&f_{t,   F} \text{= Futures price} \\
&\text{s} = \text{Time }t \text{ price of the underlying asset} \\
&P_{t,   T} =\mathrm{~Time~}t\mathrm{~price~of~a~zero-coupon~bond~maturing~at~time~}T. \\
&\text{R} =\mathrm{~Time~}t\mathrm{~interest~rate~from~time~}t\mathrm{~to~time~}t+h. \\
&\text{h} =\mathrm{Length~of~a~period};h=T/n 
\end{aligned}$$

We will refer to an instrument that pays the short-term interest rate as a money-market account.

The strategy in these derivations,   which follow Cox et al. (1981),   is to find a strategy that replicates fully funded contracts

### Forward Prices

The forward price is
$$F_{t,   T}=\mathrm{PV}\left(\frac{S_T}{P_{t,   T}}\right)=\frac{S_t}{P_{t,   T}}$$
In the chapter,     we wrote this formula as $F_{t,   T}=S_{t}e^{r(T-t)}$ This is the same as equation (5.23),     where $r$ is the continuously compounded yield on the bond: $r=\ln(1/P_{t,   T})/(T-t)$

To prove equation (5.23),     buy $F_{t,   T}$ bonds paying $S1$ at maturity (this pre-funds the forward price) and go long $1/P_{t,   T}$ forward contracts. The payoff is
$$\frac{F_{t,   T}}{P_{t,   T}}+\frac{1}{P_{t,   T}}\left[F_{T,   T}-F_{t,   T}\right]=\frac{F_{t,   T}}{P_{t,   T}}=\frac{S_{T}}{P_{t,   T}}$$
This demonstrates that a portfolio costing the forward price at time $t$ pays $S_{T}/P_{t,   T}$ Thus the forward price is the present value of $S_{T}/P_{t,   T}$ ,   or $S_{t}/P_{t,   T}$

## Futures Price

We will show that the futures price is

$$f_{t,   T}=\text{PV}\left[S_T\prod_{i=t}^T(1+R_i)\right]$$

Note that if the interest rate is known,   $\prod_{i=t}^{T}(1+R_{i})=1/P_{t,   T}$ (the bond can be replicated with the money-market fund),   and the forward price equals the futures price. To prove equation (5.24),   invest the amount $f_{l,   T}$ at the short-term interest rate,   reinvesting the proceeds each period. Also,   at each time $t_{i} \equiv t+ih,   i=1,   \ldots,   n$ ,   invest in $\Pi_{j=t}^{l_{i}}(1+R_{j})$ futures contracts. At time $t_{i+1}$ ,   liquidate position and invest the proceeds in the money-market account. The net cash flow at time 7 will be
$$\begin{gathered}
f_{t,   T}\prod_{i=t}^{T}(1+R_{i}) +\sum_{i=t}^{T-h}\left(\prod_{j=t}^{i}(1+R_{j})(f_{j,   T}-f_{j-h,   T})\prod_{j=i+h}^{T-h}(1+R_{j})\right) \\
=f_{T,   T}\prod_{i=t}^{T-h}(1+R_{i})=S(T)\prod_{i=t}^{T-h}(1+R_{i}) 
\end{gathered}$$
For future reference,   note that in continuous time,   equation (5.24) becomes
$$f_{t,   T}=\mathrm{PV}\left[S_Te^{\int_t^Tr(s)ds}\right]$$
where $r(s)$ is the instantaneous continuously compounded short-term interest rate


# Appendix 9.B Algebraic Proofs of Strike-Price Relations

In Chapter 9 we demonstrated severalpropositions about how option prices change when the strike price changes. To prove these propositions we will consider strike prices $K_{1},   K_{2}$ and $K_{3}$ ,   where $K_{1}<K_{2}<K_{3}$. Define $\lambda$ so that
$$\lambda=\frac{K_3-K_2}{K_3-K_1}$$ or
$$K_2=\lambda K_1+(1-\lambda)K_3$$
Since we are considering options that differ only with respect to the strike price. We can write $C(K)$ and $P(K)$ to denote the option premium for a particular strike. $K$

### The Call Premium Decreases as the Strike Price Increases.
Suppose that $C(K_{\mathrm{l}})<$ $C(K_{2})$ ; i.e.,   a lower strike call had a lower premium. To effect arbitrage,   we would buy the low-strike call and sell the high-strike call (this is a bull spread). Table 9.10 shows the result. We will consider each entry in the “Total”row separately Time 0. We earn net premium from selling the more expensive option. The cash flow is positive.

###### Expiration or Exercise,   $S_{T}<K_{1}$ .
- Neither option is exercised,   so the cash flow is zero.

###### Expiration or Exercise,   $\kappa_{1}\leq S_{T}\leq\kappa_{2}$ .
- We exercise the option we bought,   earning $S_{T}-K_{\mathrm{l}}$

###### Expiration or Exercise,   $S_{T}>K_{2}$ .
- We exercise the option we bought,   earning $S_{T}-$ $K_{1}$ ,   and the option we sold is exercised,   costing us $K_{2}-S_{T}$ . 
- The net is $K_{2}-K_{1}$ which is positive.

What about the fact that the options are American? We then have to account for the possibility that the written option is exercised. If that happens,   we can simply exercise the purchased option,   earning the payoffs in the table. If it is not optimal to exercise the purchased option,   we can sell it,   earning even higher payoffs



<table>
	<tbody>
		<tr>
			<th rowspan="2">Transaction</th>
			<th rowspan="2">Time 0</th>
			<th colspan="3">Expiration or Exercise</th>
		</tr>
		<tr>
			<th>$S_T<K_1$</th>
			<th>$\mathbf{K}_{1}\leq\mathbf{S}_{\mathrm{T}}\leq\mathbf{K}_{2}$</th>
			<th>$S_{\mathrm{T}}>\mathbf{K}_{2}$</th>
		</tr>
		<tr>
			<td>Buy 1 $K_{1}$-strike call</td>
			<td>$-C (K_1)$</td>
			<td>0</td>
			<td>$S_{T}-K_{\mathrm{l}}$</td>
			<td>$S_T$ $K$ 一</td>
		</tr>
		<tr>
			<td>Sell $K_{2}$-strike call</td>
			<td>$C (K_2)$</td>
			<td>0</td>
			<td>0</td>
			<td>$\underline{K_2-S_T}$</td>
		</tr>
		<tr>
			<td>Total</td>
			<td>$C (K,   )-C (K_{1})$</td>
			<td>0</td>
			<td>$S_{T}-K_{\perp}$</td>
			<td>$K_{2}$ $,   -K.$  I</td>
		</tr>
	</tbody>
</table>


<table>
	<tbody>
		<tr>
			<th rowspan="3">TABLE 9.1 Transaction</th>
			<th>Proof tha in the str</th>
			<th colspan="3">Proof that the call premium changes by less than the change in the strike price of the option.</th>
		</tr>
		<tr>
			<th> </th>
			<th colspan="3">Expiration or Exercise</th>
		</tr>
		<tr>
			<th>Time 0</th>
			<th>$S_{\mathrm{T}}<K_{\mathrm{I}}$</th>
			<th>$\mathbf{K}_{1}\leq\mathbf{S}_{T}\leq\mathbf{K}_{2}$</th>
			<th>$S_T>K_2$</th>
		</tr>
		<tr>
			<td>Sell $K_{1}$-strike 'all</td>
			<td>$C (K_1)$</td>
			<td>0</td>
			<td>$K_{\mathrm{l}}-S_{T}$</td>
			<td>$K_{\mathrm{l}}-S_{T}$</td>
		</tr>
		<tr>
			<td>101 Buy $K_{2}$-strike $a 11$</td>
			<td>$-C (K_2)$</td>
			<td>0</td>
			<td>0</td>
			<td>$S_T-K_2$</td>
		</tr>
		<tr>
			<td>$\operatorname{Lend}K,   -K_{\mathrm{I}}$</td>
			<td>$-(K,   -K_{1})$</td>
			<td>$(K,   -K_{1})$</td>
			<td>$(K,   -K_{1})$</td>
			<td>$(K,   -K_{1})$</td>
		</tr>
		<tr>
			<td>Total</td>
			<td>$C (K_{1})-C (K_{2})-$ $(K,   -K_{1})$</td>
			<td>${\overline{e^{rT}(K_{2}-K_{1})}}$</td>
			<td>$\overline{e^{rT}(K_{2}-K_{1})-}$ $(S_{T}-K_{\mathrm{l}})$</td>
			<td>${\overline{e^{rT}(K_{2}-K_{1})}}$ $(K_{2}-K_{\mathrm{l}})$</td>
		</tr>
		<tr>
			<td> </td>
			<td>$(K,   -K_{1})$</td>
			<td> </td>
			<td>$(S_{T}-K_{1})$</td>
			<td>$(K,   -K_{1})$</td>
		</tr>
	</tbody>
</table>

### The Call Premium Changes by Less Than the Change in the Strike Price.
Suppose that $C(K_{1})-C(K_{2})\geq K_{2}-K_{1}$ We can make money initially by selling the $K_{1}$ strike call buying the $K_{2}$ -strike call,   and lending $K_{2}-K_{\mathrm{l}}$ Table 9.11 summarizes the results

Time 0. We earn net premium since the initial assumption is that $C(K_{\mathrm{l}})-C(K_{2})\geq$ $K_{2}-K_{1}$ Expiration or Exercise,   $S_{T}<K_{1}$ . Neither option is exercised,   so we keep the future value of the difference between the strikes. Expiration or Exercise,   $K_{1}\leq S_{T}\leq K_{2}$ . The written option is exercised,   so we have to sell the stock for $K_{1}$ . However,   the net loss is less than the difference between the strike prices Expiration or Exercise,   $S_{T}>K_{2}$ .We keep the interest on the difference between the strike prices

What adjustments do we have to make if the options are American? If the written $K_{\mathrm{l}}$ option is exercised,   we can duplicate the payoffs in the table by throwing our option away (if $K_{1}\leq S_{T}\leq K_{2})$ or exercising it (if $S_{T}\geq K_{2}$ ). Since it never makes sense to discard an unexpired option,   and since exercise may not be optimal,   we can do at least as well as the payoff in the table if the options are American. You may have noticed that if the options are European,   we can put a tighter restriction on the difference incall premiums—namely,   $C(K_{1})-C(K_{2})<PV(K_{2}-K_{1})$ We would show this by lending $PV(K_{2}-K_{1})$ instead of $K_{2}-K_{1}$ . This strategy does not work if the options are American,   since we do not know how long it will be before the options are exercised,   and,   hence,   we do not know what time to use in computing the present value.

```latex

\usepackage{tikz}
\begin{document}
  \begin{tikzpicture}[domain=0:4]
    \draw[very thin,  color=gray] (-0.1,  -1.1) grid (3.9,  3.9);
    \draw[->] (-0.2,  0) -- (4.2,  0) node[right] {$x$};
    \draw[->] (0,  -1.2) -- (0,  4.2) node[above] {$f(x)$};
    \draw[color=red]    plot (\x,  \x)  node[right] {$f(x) =x$};
    \draw[color=blue]   plot (\x,  {sin(\x r)})    node[right] {$f(x) = \sin x$};
    \draw[color=orange] plot (\x,  {0.05*exp(\x)}) node[right] {$f(x) = \frac{1}{20} \mathrm e^x$};
  \end{tikzpicture}
\end{document}

```


### The Call Premium Is a Convex Function of the Strike Price.
This proposition says that as the option moves more into the money,   its premium increases at a faster rate. To prove it,   suppose that $C(K_{2})\geq\lambda C(K_{1})+(1-\lambda)C(K_{3})$ We can make money initially by selling the $K_{2}$ -strike call,   buying $\lambda$ $K_{\mathrm{l}}$ -strike calls,   and buying $1-\lambda$ $K_{3}$ -strike calls. Table 9.12 summarizes the results.


<table>
	<tbody>
		<tr>
			<th rowspan="3">TABLE 9.1 Transaction</th>
			<th>2 Proo price</th>
			<th colspan="4">Proof that the call price is a convex function of the strike $price.$</th>
		</tr>
		<tr>
			<th> </th>
			<th colspan="4">Expiration or Exercise</th>
		</tr>
		<tr>
			<th>Time 0</th>
			<th>$S_{\mathbf{T}}$ $<K_{1}$</th>
			<th>$\mathbf{K}_{\mathrm{l}}\leq\mathbf{S}_{\mathrm{T}}\leq\mathbf{K}_{2}$</th>
			<th>$\mathbf{K}_{2}<\mathbf{S}_{\mathbf{T}}\leq\mathbf{K}_{3}$</th>
			<th>$S_{T}>K_{3}$</th>
		</tr>
		<tr>
			<td>$\operatorname{Buy}\lambda K_{\mathrm{l}}$ strike calls</td>
			<td>$-\lambda C (K_{\mathrm{l}})$</td>
			<td>0</td>
			<td>$\lambda\left (S_{T}-K_{1}\right)$</td>
			<td>$\lambda (S_{T}-K_{\mathrm{l}})$</td>
			<td>$\lambda (S_{T}-K_{\mathrm{l}})$</td>
		</tr>
		<tr>
			<td>Sell l $K_{2}$ strike call</td>
			<td>$C (K_2)$</td>
			<td>0</td>
			<td>0</td>
			<td>$K_{2}-S_{T}$</td>
			<td>$K_{2}-S_{T}$</td>
		</tr>
		<tr>
			<td>Buy $l- \lambda$ $K_{3}.$ strike calls</td>
			<td>$-(1-\lambda) C (K_{3})$</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
			<td>$(1-\lambda)$ $(S_T-K_3)$</td>
		</tr>
		<tr>
			<td>Total</td>
			<td>$C (K_{2})-$ $\lambda C (K_{\mathrm{l}})-$ $(1-\lambda) C (K_{3})$</td>
			<td>0</td>
			<td>$\lambda\left (S_{T}-K_{1}\right)$</td>
			<td>$(1-\lambda)/$ $(K_{3}-S_{T})$</td>
			<td>0</td>
		</tr>
	</tbody>
</table>

Time 0. We earn net premium since the initial assumption is that $C(K_{2})\geq\lambda C(K_{\mathrm{l}})+$ $(1-\lambda)C(K_{3})$

###### Expiration or Exercise,   $S_T<K_1$ .
- No options are exercised

###### Expiration or Exercise,   $K_{1}\leq S_{T}\leq K_{2}$ . 
- The purchased $K_{\mathrm{l}}$ calls are exercised. 
- 
######  Expiration or Exercise,   $K_{2}<S_{T}\leq K_{3}$ .
- We exercise our 入 $K_{1}$ calls,   and the written $K_{2}$ call is exercised against us. 
- Recall that $K_{2}=\lambda K_{1}+(1-\lambda)K_{3}$ ; substituting this expression for $K_{2}$ explains how we obtain the total in this column.
- 
###### Expiration or Exercise,   $S_{T}>K_{3}$ . 
- All options are exercised and the payoffs cancel.

## Puts. 
Here are the counterpart propositions for puts,   stated more formally

1. The put premium is increasing in the strike price: $P(K_{1})\leq P(K_{2})$ 2. The put premium changes by less than the change in the strike price: $P(K_{2})-$ $P(K_{1})<K_{2}-K_{1}$ 3. The put premium is a convex function of the strike price: $P(K_{2})<\lambda P(K_{1})+($ l- $\lambda)P(K_{3})$ .

The proofs are identical to the propositions for calls.


# TAXES AND OPTION PRICES

It is possible to solve for a binomial price when there are taxes. Suppose that each form of income is taxed at a different rate: interest at the rate $\tau_{i}$ ,   capital gains on a stock at the rate $l_{g}$ ,   capital gains on options at the rate $l0$ ,   and dividends at the rate $\tau_{d}$ We assume that taxes on all forms of income are paid on an accrual basis,   and that there is no limit on the ability to deduct losses or to offset losses on one form of income against gains on another form of income.

We then choose $\Delta_{t}$ and $B_{r}$ by requiring that the after-tax return on the stock/bond portfolio equal the after-tax return on the option in both the up and down states. Thus we require that

$$\begin{aligned}\begin{bmatrix}S_{t+h}&-\tau_{g}(S_{t+h}-S_{t})+\delta S_{t}(1-\tau_{d})\end{bmatrix}\Delta_{t}+\begin{bmatrix}1+r_{h}(1-\tau_{i})\end{bmatrix}B_{t}\\&=\phi_{t+h}(S_{t+h})-\tau_{O}\left[\phi_{t+h}(S_{t+h})-\phi_{t}(S_{t})\right]\end{aligned}$$

The solutions for $\Delta$ and $B$ arethen
$$\begin{aligned}&\Delta=\frac{1-\tau_{O}}{1-\tau_{g}}\frac{\phi_{1}(S_{1}^{+})-\phi_{1}(S_{1}^{-})}{S_{1}^{+}-S_{1}^{-}}\\&B=\frac{1}{1+r_{h}\frac{1-\tau_{l}}{1-\tau_{O}}}\left(\frac{u\phi_{1}(S_{1}^{-})-d\phi_{1}(S_{1}^{+})}{u-d}-\frac{\Delta}{1-\tau_{O}}S_{0}\left[\frac{\tau_{g}-\tau_{O}}{1-\tau_{g}}+\delta(1-\tau_{d})\right]\right)\end{aligned}$$

This gives an option price of

$$\phi_{t}=\frac{1}{1+r_{h}\frac{1-\tau_{i}}{1-\tau_{O}}}\left[p^{*}\phi_{t+h}(S_{t+h}^{+})+(1-p^{*})\phi_{t+h}(S_{t+h}^{-})\right]$$

Where

$$p^*=\frac{1+r_h\frac{1-\tau_i}{1-\tau_g}-\delta\frac{1-\tau_d}{1-\tau_O}-d}{u-d}$$

In practice,   dealers are marked-to-market for tax purposes and face the same tax rate on all forms of income. In this case taxes drop out of all the option-pricing expressions. When dealers are the effective price-setters in a market,   taxes should not affect prices





# AN ALTERNATIVE APPROACH TO EXPENSING OPTION GRANTS

How should companies account for compensation options? One approach is to fully deduct the market value of the option at exercise; this is the approach taken in taxing option grants A deduction at exercise gives an expense with a present value equal to the price at grant. However,   by waiting to deduct the expense,   the firm's reported income in earlier years will not reflect the economic value of compensation in those years. As an alternative,   Bulow and Shoven (2004) propose an option expense calculation that records an expense for each period that the option remains unexercised. Their approach neatly sidesteps many valuation difficulties and provides a correct present value of option deductions. Moreover,   the method provides insight into why a long-term option grant is costly. We will illustrate the proposal in the specific context of compensation options,   but the methodology is generally applicable to long-term contracts and contingent liabilities. Bulow and Shoven make the observation that most option contracts are exercisable after a vesting period,   and that employees or heirs are typically required to exercise their options within 90 days of resignation or death. Thus,   in practice,   a 10-year option can be viewed as a renewable 90-day option,   extendible (by the employee’s continuing to work) for 39 additional 90-day periods. Bulow and Shoven propose taking the value of this extension as the deduction in each quarter. The value of the extension is the market value of a 90-day option,   less intrinsic value. The present value of expected option expense computed in this fashion is the fair market value for an option with the same time to expiration Figure 16.10 provides a binomial example illustrating how the Bulow-Shoven proposal works for a 3-year option that vests immediately,   and for which recipients can exercise the option in year 1,   2,   or 3,   or 1 year after resignation. The binomial value of the 3-year 100-strike option is \$28.15; you can verify this by applying the binomial pricing method to the stock price tree in panel (a) Panel (d) of Figure 16.10 shows the annual expense reported under the Bulow-Shoven scheme. To see how the entries in panel (d) are calculated,   consider the \$4.88 expense in year 1 when the stock price is $\$134.99$ . From panel (c),   the price of a l-year option at that node is S 39.86. Option expense in that year is therefore fair market value less intrinsic value,   or $\$39.86-34.99=\$4.88$ Why do we deduct intrinsic value? The reason is that the deduction for the year 2 intrinsic value was,   in effect,   already taken the previous year,   when we deducted the value of a 1-year option. The price of a 1-year option is the present value of the next year's intrinsic value. Therefore,   the only new value to deduct in a given year is the value of a l-year option over and above that year's intrinsic value,   which is the present value of next year's intrinsic value. In effect,   the Bulow-Shoven scheme amortizes the value of the 3-year option,   where the amortization amount varies with the stock price. You can compute the present value of all deductions in panel (d) by using the binomial pricing method with the same parameters used to generate panel (a). As an exercise,   you can verify that the present value of deductions in panel (d) is $\$28.15$ ,   which is also the binomial value of a 3-year option


FIGURE 16.10

Option expense calculation under the Bulow-Shoven proposal. Assumes $K=$ $\$100$ $\sigma=0.30$ $r=0.05$ $\delta=0$ ,   and $T=3$ years. The risk-neutral probability of an up move is $p=0.5097$ The CRR binomial stock price process is in panel (a). Panel (b) reports the option intrinsic value,   $max[0,   S_{\mathrm{t}}-K]$ . Panel (c) reports the 1-period option value. Panel (d) reports the annual option expense.

<table>
	<tbody>
		<tr>
			<th rowspan="2">Pane</th>
			<th> </th>
			<th colspan="4">Year</th>
		</tr>
		<tr>
			<th>1</th>
			<th>0</th>
			<th>1</th>
			<th>2</th>
			<th>3</th>
		</tr>
		<tr>
			<td rowspan="5">$(\mathbf{a})\colon$</td>
			<td>Stock price process</td>
			<td>100.00</td>
			<td>134.99</td>
			<td>182.21</td>
			<td>245.96</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td>74.08</td>
			<td>100.00</td>
			<td>134.99</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>54.88</td>
			<td>74.08</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>40.66</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td rowspan="5">$(\mathbf{b})\colon$</td>
			<td>Intrinsic value</td>
			<td>0.00</td>
			<td>34.99</td>
			<td>82.21</td>
			<td>145.96</td>
		</tr>
		<tr>
			<td>$(\operatorname*{max}[0,   S_{t}-K])$</td>
			<td> </td>
			<td>0.00</td>
			<td>0.00</td>
			<td>34.99</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td rowspan="5">$(\mathbf{c})\colon$</td>
			<td>alm</td>
			<td>$1 f$ 11 $1 K$</td>
			<td>$3 C$ 24</td>
			<td>87</td>
			<td> </td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td>0.00</td>
			<td>16.96</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td rowspan="4">$(\mathbf{d}):$</td>
			<td>Reported expense</td>
			<td>16.96</td>
			<td>4.88</td>
			<td>4.88</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td>$( \mathbf{Panel}( \mathbf{c} )$ $\mathbf{less}$ $\mathbf{panel}$ $( \mathbf{b} ) )$</td>
			<td> </td>
			<td>0.00</td>
			<td>16.96</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
			<td>0.00</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td>0.00</td>
		</tr>
	</tbody>
</table>

There are several points to make about this example. First,   the full deductions with a present value of $\$28.15$ are reported by the company only if the option is held unexercised until year 3. Thus,   the proposal solves the problem of early exercise and the employee leaving the company. Second,   the actual deductions are substantially less than the maximum possible value of the option at exercise. Third,   expenses behave in what might appear to be a counterintuitive fashion,   with reported option expense greatest when the option is at the-money. In year 2,   for example,   expense is greatest when the stock price is $\$100$ .The reason is that the value of delaying exercise on a deep-in-the-money option is primarily the value of delaying the payment of the strike price. Thus,   in panel (d),   S 4.88 is the 1 year present value of interest on $\$100$ . When the option is at-the-money,   however,   put-call parity tells us that the value of the implicit put option is also important,   and this is why the at-the-money expense is greater. To say this differently,   an employee who prematurely exercises an option that is near the money loses more economic value than an employee who prematurely exercises an option that is deep in the money. The option expense calculation in Figure 16.10 reflects this. Suppose a firm must compute annual option expense and separated employees have 2 years to exercise their options. How does this change the calculation? In this case,   by working 1 more year,   the employee obtains a new 1-year option and gives up the remaining 1 year on the previous year's 2-year option. It is straightforward to calculate expense in this situation. Using the assumptions in Figure 16.10,   Problem 16.24 asks you to verify that the present value of option expense in this case again equals the fair market value of $\$28.15$ Note that if we were to apply this methodology to a grant of stock,   we would expense the entire grant initially. A share of stock is like a zero-exercise price option,   and with no dividends,   such an option is worth the share price. Price would therefore equal intrinsic value in every period,   resulting in zero expense every period after the first. Finally,   note that this expensing method is generally applicable to contingent liabili ties,   and it thus has broad applicability beyond compensation options. In general,   in order to record a current expense,   it is necessary to value the liability only over a short horizon and then to do so repeatedly

## References

Bulow,   J. and Shoven,   J. B. 2004,   “Accounting for Options,   * Working Paper,   Stanford University,   March 2004





# CALCULATION OF OPTIMAL TIME TO DRILL AN OIL WELL 
## Single-Barrel Solution

It is optimal to defer investing as long as
$$\left (\frac{1}{1+r}\right)^h\left[S\left (\frac{1+r}{1+\delta}\right)^h-X\right]>S-X$$
Which can be rewritten as
$$\frac{S}{X}<\frac{1-\left (\frac{1}{1+r}\right)^h}{1-\left (\frac{1}{1+\delta}\right)^h}$$
The optimal solution entails taking the limit as $h\to 0$ Using L'Hospital’s rule,   we can show that $\lim_{h\to\infty}\frac{1-(1+r)^{-k}}{h}=\ln (1+r)$ Hence
$$\frac{1-\left (\frac{1}{1+r}\right)^h}{1-\left (\frac{1}{1+\delta}\right)^h}\to\frac{\ln (1+r)}{\ln (1+\delta)}$$
Thus,   we defer investing as long as
$$\frac{S}{X}<\frac{\ln (1+r)}{\ln (1+\delta)}$$
In the text example this calculation gives $\$16.918$

### THE SOLUTION WITH SHUTTING DOWN AND RESTARTING

In this appendix we explain the solution of two problems: investing and operating (1) when it is possible to shut down once and restart once,   permanently,   and (2) when it is possible tc shut down and restart an infinite number of times. The solutions here can be implemented numerically First,   we develop some notation. Let $V_{U}(S,   m,   n;*)$ represent the value of an undeveloped reserve and $V_{O}(S,   m,   n;*)$ and $V_{C}(S,   m,   n;*)$ the value of developed operating and developed closed reserves,   where it is possible to shut down m times and restart n times The 祚 denotes a dependence on the prices at which shutting and restarting is optimal. We will be using the formulas given by equations (12.22) and (12.23) for the value of $\$1$ when $S$ reaches a barrier.

#### Single Shutdown and Restart

Prior to the final permanent restart at $S^{*}$ ,   we have

$$V_C (S,   0,   1; S^*)=\left (\frac{S^*}{\delta}-\frac{c}{r}-k_r\right)\left (\frac{S}{S^*}\right)^{h_1}$$

We choose $S^{*}$ to maximize this expression.

While operating,   prior to the shutdown at $S_{*}<S$ ,   we have

(17.16)
$$V_O (S,   1,   1; S_*,   S^*)=\frac{S}{\delta}-\frac{c}{r}+\left[\frac{c}{r}-k_s-\frac{S_*}{\delta}+V_C (S_*,   0,   1; S^*)\right]\left (\frac{S}{S_*}\right)^{h_2}$$

We choose $S_{*}$ to maximize this expression,   taking $S^{*}$ as determined by equation (17.15) Finally,   prior to the original investment decision,   which occurs at $\bar{S}>S$ ,   the value of

The well is

$$V_U (S,   1,   1; S_*,   S^*)=\begin{bmatrix}V_0 (\bar{S},   1,   1,   S_*,   S^*)-I\end{bmatrix}\left (\frac{S}{\bar{S}}\right)^{h_1}$$

We find the $\bar{S}$ that maximizes this equation,   taking $S_{*}$ and $S^{*}$ as given,   determined by maximizing equations (17.15) and (17.16)

#### Infinite Shutdown and Restart

The solution here is conceptually like that in the single shutdown and restart case,   except that when we restart,   we receive the option to shut down. Thus,   when the well is shut,   we have
$$V_C (S,   \infty,   \infty; S_*,   S^*)=\begin{bmatrix}-k_r+V_O (S^*,   \infty,   \infty; S_*,   S^*)\end{bmatrix}\left (\frac{S}{S^*}\right)^{h_1}$$

While operating,   prior to the shutdown at $S>S_{*}$ ,   we have
$$\begin{aligned}
V_{O}(S,   \infty,   \infty; S_{*},   S^{*})& =\frac{S}{\delta}-\frac{c}{r} \\
&+\left[\frac{c}{r}-k_{s}-\frac{S_{*}}{\delta}+V_{C}(S_{*},   \infty,   \infty; S_{*},   S^{*})\right]\left (\frac{S}{S_{*}}\right)^{h_{2}}
\end{aligned}$$
Note that $V_{C}$ and $V_{0}$ are defined in terms of each other. We can substitute equation (17.17) into equation (17.18) and set $S=S_{*}$ . This gives
$$V_O (S^*,   \infty,   \infty; S_*,   S^*)=\frac{S^*/\delta-c/r-k_r (S_*/S^*)^{h_1}+(c/r-S_*/\delta-k_s)\times (S^*/S_*)^{h_2}}{1-(S_*/S^*)^{h_1}\times (S^*/S_*)^{h_2}}$$
Given starting values of $S^{*}$ and $S_{*}$ ,   we can evaluate equation (17.19),   substituting the answer into equation (17.17) to obtain an estimate of $V_{C}(S,   \infty,   \infty; S_{*},   S^{*})$ .Then we can maximize equation (17.17) with respect to $S^{*}$ and equation (17.18) with respect to $S_{*}$ . This gives us new estimates of $V_{C}(S_{*})$ and $V_{0}(S^{*})$ Iterate until convergence
Once we have computed $S^{*},   S_{*}$ ,   and $V_{C}(S_{*})$ ,   the value of the well is
$$V_{U}(S,   \infty,   \infty; S_{*},   S^{*})=\left[\frac{\overline{S}}{\delta}-\frac{c}{r}-I+V_{C}(S_{*},   \infty,   \infty; S_{*},   S^{*})\left (\frac{\overline{S}}{S_{*}}\right)^{h_{2}}\right]\left (\frac{S}{\overline{S}}\right)^{h_{1}}$$
We maximize this with respect to $\overline{S}$ to find the investment trigger and value of the well


# Appendix 18.B CONSTRUCTING A NORMAL PROBABILITY PLOT

This appendix discusses the details of constructing the normal probability plot for the data in Example 18.9. The idea of the normal probability plot is to compare the quantiles of the data with the corresponding quantiles of the normal distribution. Because the shape of the normal distribution is the same whatever the mean and variance,   we know that the relative distance of normal quantiles will be the same for any normal distribution. For a $\mathcal{N}(0,   1)$ distribution,   the cumulative inverse distribution function tells us which $A$ value corresponds to a particular quantile. For example,   $N^{-1}(0.1)=-1.282$ and $N^{-1}(0.3)=-0.524$ . The distance between the $\lambda$ values that give rise to the data quantiles is

$$\begin{gathered}
N^{-1}(0.3)-N^{-1}(0.1) =0.757 \\
N^{-1}(0.5)-N^{-1}(0.3) =0.524 \\
N^{-1}(0.7)-N^{-1}(0.5) =0.524 \\
N^{-1}(0.9)-N^{-1}(0.7) =0.757 
\end{gathered}$$

The lesser distance between quantiles closer to the median reflects the shape of the normal distribution. If the data come from a normal distribution,   the relative distance between data points at these quantiles will have the same relative distances. The procedure in creating Figure 18.5 is to plot the data points on the X -axis against

The values from a $\mathcal{N}(0,   1)$ distribution with the same quantiles. Thus,   we plot the data point with quantile 4 against $N^{-1}(q)$ In the case of the five sample data points,   we plot the points (3,   -1.282) ,   (4,   -524) ,   (5,   0) ,   (7,   0.524) and (11,   1.282). These points are plotted in the top left panel of Figure 18.6. The $y$ -axis is labeled ‘ $^{^{\prime}}z$ -value” since these are values from a standard normal distribution. The top right panel is exactly the same,   except that the $y$ -axis is labeled with probabilities corresponding to the $z$ -values. The data do not appear normal though with only five points there is a large possibility for error





# Appendix 19 A: FORMULAS FOR GEOMETRIC AVERAGE OPTIONS

The discussion of Monte Carlo valuation of geometrically averaged Asian options enables us to understand the formulas for geometrically averaged Asian options,   described in Appendix 14.A. If we sample the stock price $N$ times from time O to 7 ,   with the distance betweer samples $h=T/N$ and the first sample occurring at time $h$ ,   the log of the geometric average i
$$\begin{aligned}
\frac{1}{N}\sum_{i=1}^{N}\ln (S_{ih})& =\frac{1}{N}\left[\sum_{i=1}^{N}\left (\ln (S_{0})+(r-\delta-0.5\sigma^{2}) ih+\sigma\sum_{j=1}^{i}Z_{j}\sqrt{h}\right)\right] \\
&=\ln (S_{0})+(r-\delta-0.5\sigma^{2})\frac{h}{N}\sum_{i=1}^{N}i+\frac{\sigma\sqrt{h}}{N}\sum_{i=1}^{N}\sum_{j=1}^{i}Z_{j}
\end{aligned}$$
Where $Z_{j}\sim\mathcal{N}(0,   1)$ and $Z_{i}$ and $Z_{j}$ are independent The last double summation can be rewritten as
$$\sum_{i=1}^N\sum_{j=1}^iZ_j=NZ_1+(N-1) Z_2+\cdots+Z_N$$
Thus,   we have
$$\begin{aligned}
\operatorname{E}\left[{\frac{1}{N}}\sum_{i=1}^{N}\ln (S_{ih})\right]& =\ln (S_{0})+(r-\delta-0.5\sigma^{2})\frac{h}{N}\frac{N (N+1)}{2} \\
&=\ln (S_{0})+(r-\delta-0.5\sigma^{2}) T\frac{N+1}{2 N}
\end{aligned}$$
Where we have used the fact that
$$\begin{aligned}\sum_{i=1}^Ni=\frac{N (N+1)}{2}\end{aligned}$$
The variance is
$$\begin{aligned}
\operatorname{Var}\left[{\frac{1}{N}}\sum_{i=1}^{N}\ln (S_{ih})\right]& =\frac{\sigma^{2}h}{N^{2}}\left (N^{2}+(N-1)^{2}+\cdots+1\right) \\
&=\sigma^{2}T\frac{N (N+1)(2 N+1)}{6 N^{3}}
\end{aligned}$$

Where we have used the fact that

$$\begin{aligned}\sum_{i=1}^Ni^2=\frac{N (N+1)(2 N+1)}{6}\end{aligned}$$

These calculations tell us that the average price,   $G (T)$ ,   can be written as a lognormal process,   

$$G (T)=S_{0}e^{\left[(r-\delta-0.5\sigma^{2})\frac{T}{2}\frac{N+1}{N}+\sigma\sqrt{T}\sqrt{\frac{(N+1)(2 N+1)}{6 N^{2}}}Z\right]}$$


Where $Z\sim\mathcal{N}(0,   1)$ . Using equation (18.13),   we have

$$\operatorname{E}\left[G (T)\right]=S_{0}e^{\left[(r-\delta-0.5\sigma^{2})\frac{N+1}{N}+\sigma^{2}\frac{(N+1)(2 N+1)}{6 N^{2}}\right]\frac{1}{2}T}$$

The prepaid forward price for the average is

$$e^{-rT}\mathrm{E}\left[G (T)\right]=S_{0}e^{-\left[r\frac{N-1}{N}+(\delta+0.5\sigma^{2})\frac{N+1}{N}-\sigma^{2}\frac{(N+1)(2 N+1)}{6 N^{2}}\right]\frac{1}{2}T}$$

Thus,   we can price an option on the geometric average by setting the dividend yield for the average,   $\delta^{*}$ ,   equal to

$$\delta^*=\frac{1}{2}\left[r\frac{N-1}{N}+(\delta+0.5\sigma^2)\frac{N+1}{N}-\sigma^2\frac{(N+1)(2 N+1)}{6 N^2}\right]$$

And the volatility of the average,   $\sigma^*$ ,   equal to

$$\sigma^*=\frac{\sigma}{N}\sqrt{\frac{(N+1)(2 N+1)}{6}}$$

If we take the limit as $N\rightarrow\infty$ ,   we have

$$\begin{aligned}&\delta^{*}=\frac{1}{2}\left (r+\delta+\frac{1}{6}\sigma^{2}\right)\\&\sigma^{*}=\sigma\sqrt{\frac{1}{3}}\end{aligned}$$

## Average Price Options
Geometric average price options,   for which the geometric average replaces the stock price are priced by substituting $\delta^{*}$ and $\sigma^*$ for $\delta$ and 0 in the Black-Scholes formula

## Average Strike Options
With geometric average strike options,   the average replaces the strike price. Thus,   we replace the risk-free rate with $\delta^{*}$ and the strike price with $S_{0}$ .However,   we also need to compute the volatility of the difference between $\ln (S_{T})$ and $\ln (A (T))$
$$\sigma^{**2}=\mathrm{Var}\left[\ln (S_T)-\ln (A_T)\right]$$
We can write
$$\ln (S_T)=\ln (S_0)+(r-\delta-0.5\sigma^2) T+\sigma\sum_{i=1}^NZ_i\sqrt{h}$$
Using equation (19.19),   the covariance between $\ln (S_T)$ and $\ln (A_T)$ is
$$\begin{aligned}
\operatorname{E}\left[\left (\sigma{\sqrt{h}}\sum_{i=1}^{N}Z_{i}\right)\left ({\frac{\sigma{\sqrt{h}}}{N}}\sum_{i=1}^{N}\sum_{j=1}^{i}Z_{j}\right)\right]& =\frac{\sigma^{2}h}{N}\left (\sum_{i=1}^{N}Z_{i}\right)\left (\sum_{i=1}^{N}\sum_{j=1}^{i}Z_{j}\right) \\
&=\frac{\sigma^{2}h}{N}\left (N+(N-1)+\cdots+1\right) \\
&=\frac{\sigma^{2}h}{2}(N+1)
\end{aligned}$$

The correlation coefficient,   $\rho$ ,   is therefore

$$\begin{aligned}\rho&=\frac{\frac{\sigma^2 h}{2}(N+1)}{\left (\sigma\sqrt{T}\right)\left (\sigma\sqrt{T}\frac{1}{N}\sqrt{\frac{(N+1)(2 N+1)}{6}}\right)}\\&=\frac{1}{2}\sqrt{\frac{6 (N+1)}{2 N+1}}\end{aligned}$$

Note that when $N=1$ ,   $\rho=1$ ,   and as $N\to\infty$ ,   $\rho={\sqrt{3}}/2$ Using this expression for $\rho$ ,   we have

$$\sigma^{**2}=\sigma^{2}T+\sigma^{2}T\frac{(N+1)(2 N+1)}{6 N^{2}}-2\rho\sigma^{2}T\frac{1}{N}\sqrt{\frac{(N+1)(2 N+1)}{6}}$$

Thus,   to value an average strike option we substitute $\sigma^{\text{ 83}*}$ for the volatility and $\delta^{*}$ fo the interest rate. The dividendyield on the underlying asset remains the same





# Appendix 20. A VALUATION USING DISCOUNTED CASH FLOW

For the special case where the stock follows geometric Brownian motion,   and where the claim has the payoff $S^{u}$ ,   we can also use discounted cash flow (DCF) to value the claim. In general,   there is no reason to use DCF when we can perform risk-neutral valuation,   bu it is instructive to see how DCF works in the case where a claim pays $S^{a}$ .We can value the claim by discounting the expected payoff under the physical measure at an appropriate discount rate. To do this we must compute the expected value of the claim and discount the expected payoff appropriately We know that the stock has a Sharpe ratio of $(\alpha-r)/\sigma$ . Equation (20.34) tells us that $S^{u}$ follows geometric Brownian motion with drift $a (\alpha-\delta)+0.5 a (a-1)\sigma^{2}$ and diffusion term $a_0 dZ$ gives us the process followed by $S^{a}$ . The requirement for equal Sharpe ratios tells that the expected return for a claim paying $S^{a},   \alpha_{a}$ must satisfy
$$\frac{\alpha_a-r}{a\sigma}=\frac{\alpha-r}{\sigma}$$
This implies that $\alpha_{a}$ is
$$\alpha_{a}=a (\alpha-r)+r$$
For the moment. Set $\delta=0.$ It is obvious that in general
$$a (\alpha-r)+r\neq a\alpha+0.5 a (a-1)\sigma^{2}$$
The economic issue is that if $\alpha$ is the equilibrium return for the stock-that is,   it is the return for which investors are willing to hold the stock —then $a\alpha+0.5 a (a-1)\sigma^{2}$ is not generally the return for which investors are willing to hold a claim with the value $S^{u}$ . This is a consequence of Jensen’s inequality: Raising the stock price to a power requires a particular change in the expected return,   which is not the same as the return generated by raising the price to a power. To make investors willing to hold a claim paying $S^{u}$ at time 7 ,   the clain must sell at a premium or discount prior to time $I$ .We have already valued the claim in Proposition 20.3,   but we will value the claim a second time,   illustrating the application of DCF valuation in this context We know that the expected value of $S (T)^a$ is
$$\mathrm{E}_{0}\left[S (T)^{a}\right]=S (0)^{a}e^{[a (\alpha-\delta)+\frac{1}{2}a (a-1)\sigma^{2}]T}$$
The expected return on this claim,   which is also the appropriate discount rate,   is given by expression (20.46). The price at time 0 of a claim paying $S (T)^{a}$ at time 1 is therefore the discounted expected payoff:
$$\begin{aligned}
F_{0,   T}^{P}(S^{a})& =e^{-[r+a (\alpha-r)]T}\mathrm{E}(S (T)^{a})  \\
&=e^{-[r+a (\alpha-r)]T}S (0)^{a}e^{[a (\alpha-\delta)+\frac{1}{2}a (a-1)\sigma^{2}]T} \\
&=S (0)^{a}e^{-rT}e^{[a (r-\delta)+\frac{1}{2}a (a-1)\sigma^{2}]T}
\end{aligned}$$
Note that the risk premium on the stock,   $\alpha-r$ drops out of the derivation. This illustrates that DCF yields the same answer as risk-neutral pricing. The use of a constant discount rate works in this case because the payoff to the claim is relatively simple. In many cases computing a price using DCF will be more difficult than computing the price using risk neutral valuation.


# Appendix 21.C SOLUTIONS FOR PRICES AND PROBABILITIES
The Black-Scholes partial differential equation has the form
$$V_t+\frac{1}{2}\sigma^2 S^2 V_{SS}+\eta SV_S=\beta V$$
In equation (21.11),   we have $\eta=r-\delta$ and $\beta=r$ .When $\beta=0$ ,   equation (21.47) is the backward equation,   equation (21.33)

Suppose we guess the following general solution to equation (21.47):
$$\begin{aligned}V (S,   t)&=Ae^{\gamma t}S^{a}N (x)^{y}\\&x=\frac{\ln[S (t)]+f+g (T-t)}{\sigma\sqrt{T-t}}\end{aligned}$$
Where $A,   a,   f,   g$ ,   and $\gamma$ are constants to be determined,   and 0 and $y$ are parameters. $N (x)$ is the cumulative standard normal distribution. We will consider the cases $y=\{0,   1\}$ Note that sums of solutions are also solutions.

Computing the various derivatives of this guessed solution,   substituting them into equation (21.47),   and simplifying gives
$$\begin{aligned}&0=\left[\frac{1}{2}\sigma^{2}a^{2}+a\left (\eta-\frac{1}{2}\sigma^{2}\right)+\gamma-\beta\right]\\&+yN (x)^{-1}N^{\prime}(x)\left[\frac{\sigma^{2}\left (a-\frac{1}{2}\right)+\eta-g}{\sigma\sqrt{T-t}}\right]\end{aligned}$$

The parameters $A$ and $f$ are not in any way determined by this equation; hence,   they are solely determined by boundary conditions. Equation (21.49) is satisfied for
$$a=\left (\frac{1}{2}-\frac{\eta}{\sigma^2}\right)\pm\sqrt{\left (\frac{\eta}{\sigma^2}-\frac{1}{2}\right)^2+2\frac{\beta-\gamma}{\sigma^2}}$$
And
$$g=\sigma^2\left (a-\frac{1}{2}\right)+\eta $$
The first term in square brackets stems from differentiating $Ae^{\gamma r}S^{a}$ ,   while the second brack eted term stems from differentiating $N (x)$ We will examine only a few of the commonly occurring solutions. Since $Ae^{-\gamma (T-t)}S^{a}N (x)$ and $Ae^{-\gamma (I-t)}S^{a}$ both solve the PDE,   and since sums of solutions are also solutions,   then
$$Ae^{-\gamma (T-t)}S^a\left[N (x)-1\right]=Ae^{-\gamma (T-t)}S^aN (-x)$$
Is also a solution.

## Solutions to the Black-Scholes Equation

The parameters 711 and $\beta$ are determined by the PDE that arises in solving a particulan problem. In the standard Black-Scholes equation,   $\eta=r-\delta$ and $\beta=r$ ; this is the case we will consider. Let $a^{+}$ denote the positive root in equation (21.50),   and $a^{-}$ the negative root. Since $g$ is defined in terms of $d$ ,   for any given $\gamma$ ,   there are two matched $\{a,   g\}$ pairs


If we pick $\gamma$ ,   the rest of the solution is determined by equations (21.50) and (21.51) in conjunction with boundary conditions. Two obvious choices are $\gamma=r$ and $\gamma=\delta$ If $\gamma=r$ ,   then $\{a^{+},   g^{+}\}=\{0,   r-\delta-\frac{1}{2}\sigma^{2}\}$ and $\{a^{-},   g^{-}\}=\left\{1-2\frac{r-\delta}{\sigma^{2}},   -\left (r-\delta-\frac{1}{2}\sigma^{2}\right)\right\}$ The positive roots here,   together with appropriate boundary conditions,   generate the price of a cash-or-nothing option,   equation (21.16). If $\gamma=\beta-\eta=\delta$ ,   then $\{a^{+},   g^{+}\}=\{1,   r-\delta+$ $\frac{1}{2}\sigma^{2}\}$ and $\{a^{-},   g^{-}\}=\left\{-2\frac{r-\delta}{\sigma^{2}},   -\left (r-\delta+\frac{1}{2}\sigma^{2}\right)\right\}$ .The positive roots here,   together with boundary conditions,   generate the price of an asset-or-nothing option,   equation (21.15) The following expressions all satisfy the Black-Scholes PDE
$$V^5[S (t),   t]=e^{-\delta (T-t)}S^{-a_3}\times N\left (\frac{\ln[S (t)]+f-[r-\delta+0.5\sigma^2][T-t]}{\sigma\sqrt{T-t}}\right)$$
$$V^{6}[S (t),   t]=e^{-r (T-t)}S^{1-a_{3}}\times N\left (\frac{\ln[S (t)]+f-[r-\delta-0.5\sigma^{2}][T-t]}{\sigma\sqrt{T-t}}\right)$$
$$V^7[S (t),   t]=AS (t)^{a_1}$$
$$V^8[S (t),   t]=AS (t)^{a_2}$$
Where
$$\begin{aligned}
&a_{1} =\left (\frac{1}{2}-\frac{r-\delta}{\sigma^{2}}\right)+\sqrt{\left (\frac{r-\delta}{\sigma^{2}}-\frac{1}{2}\right)^{2}+\frac{2 r}{\sigma^{2}}} \\
&a_{2} =\left (\frac{1}{2}-\frac{r-\delta}{\sigma^{2}}\right)-\sqrt{\left (\frac{r-\delta}{\sigma^{2}}-\frac{1}{2}\right)^{2}+\frac{2 r}{\sigma^{2}}} \\
&a_{3} =\frac{2 (r-\delta)}{\sigma^{2}} 
\end{aligned}$$

With appropriate choice of $A$ ,   equations (21.54) and (21.55) are the formulas for infinitely lived options. We will see in Chapter 22 that equations (21.52) and (21.53) play a role in pricing barrier options. The solutions to the equations in Table 21.1 are obtained by choosing the parameters listed there. These equations also satisfy specific boundary conditions.

## Solutions to the Backward Equation

For a stock following geometric Brownian motion,   the backward equation is satisfied if $\beta=0.$ It turns out that $\gamma=0$ is frequently the solution of interest. For example,   the Black Scholes term $N (d_{2})$ ,   without a discount factor,   is the risk-neutral probability that $S (T)>K$ and is a solution to the forward equation.

Consider these (undiscounted) variants of equations (21.52) and (21.53)
$$e^{r (T-t)}V^{5}[S (t),   t]=e^{(r-\delta)(T-t)}S (t)^{-a_{3}}N\\\left (\frac{\ln[S (t)]+f-[r-\delta+0.5\sigma^{2}][T-t]}{\sigma\sqrt{T-t}}\right)\\e^{r (T-t)}V^{6}[S (t),   t]=S^{1-a_{3}}N\left (\frac{\ln[S (t)]+f-[r-\delta-0.5\sigma^{2}][T-t]}{\sigma\sqrt{T-t}}\right)$$


TABLE 21.1 Parameters generating the solutions to the Black-Scholes PDE for the indicated equation.

<table>
	<tbody>
		<tr>
			<th>Equation</th>
			<th>$y$</th>
			<th>$\gamma$</th>
			<th>$a\left (\mathrm{Equation~(21.50)}\right)$ 1</th>
		</tr>
		<tr>
			<td>(21.12)</td>
			<td>0</td>
			<td>$r$</td>
			<td>$a^+=0$</td>
		</tr>
		<tr>
			<td>(21.13)</td>
			<td>0</td>
			<td>$\delta$</td>
			<td>$a^+=1$</td>
		</tr>
		<tr>
			<td>(21.15)</td>
			<td>l</td>
			<td>$\delta$</td>
			<td>$a^+=1$</td>
		</tr>
		<tr>
			<td>(21.16)</td>
			<td>l</td>
			<td>$\delta$</td>
			<td>$a^{-}=-2$</td>
		</tr>
		<tr>
			<td>(21.52)</td>
			<td>l</td>
			<td>$r$</td>
			<td>$a^+=0$</td>
		</tr>
		<tr>
			<td>(21.53)</td>
			<td>l</td>
			<td>$r$</td>
			<td>$a^{-}=1-2$</td>
		</tr>
		<tr>
			<td>(21.54)</td>
			<td>0</td>
			<td>0</td>
			<td>$\left\|\frac{1}{2}\right\|$</td>
		</tr>
		<tr>
			<td>(21.55)</td>
			<td>0</td>
			<td>0</td>
			<td>$a$ -</td>
		</tr>
	</tbody>
</table>

You can verify that equations (21.56) and (21.57) obey equation (21.34). With an appropriate scale factor and choice of $f$ ,   equation (21.56) will appear in Chapter 22 as the risk-neutral probability that the stock price hits a barrier and exceeds a terminal strike price Finally,   note that you can use Proposition 21.1 to obtain equation (21.55) from equation (21.56)

# Appendix 23. A THE REFLECTION PRINCIPLE

For every standard Brownian path there is an equally likely path that can be constructed by reflecting the path,   or a portion of the path,   with respect to a horizontal line. Figure 23.5 shows a Brownian path,   $X_{r}$ ,   denoted by ABC,   that is reflected beginning at the poin where the path reaches $X_{t}=70$ .Notice that the path BD is a mirror image,   reflected vertically around the line $X=70$ ,   of the original path BC. We will see that by considering the refected path,   it is possible to transform barrier probability calculations into standard normal probability calculations

Suppose we have a Brownian motion that starts at $X_{0}$ and follows the process

$$dX_{t}=\sigma dZ_{t}$$

Thus,   $X_{I}$ is normally distributed with mean $X_{0}$ and variance $\sigma^{2}T$ .We want to know the joint probability that at time $T,   X_{T}$ will have hit the barrier $H<X_{0}$ and will also be above the level $K\geq H$ . If we let $\underline{X}_{\mathrm{r}}$ denote the lowest value of $X$ between O and $I$ ,   we wish to compute the joint probability

$$\Pr (X_{T}>K,   \underline{X}_{T}\leq H)$$

## FIGURE 23.5

Illustration of refection principle. Original path is ABC. Path reflected about a barrier of 70 is ABD

![](https://storage.simpletex.cn/view/fccZYAwqiloApgLsGN23M6KRUUEMxlngK)


The probability here is analogous to that in equation (23.6). If $X$ were the price of an asset this probability discounted at the risk-free rate would be the price of a down-and-in cash call. Suppose that $X_0=80$ $H=70$ ,   and $K=100$ Consider the actual Brownian path in

Figure 23.5 depicted by the letters ABC. This path starts at “A,   ” hits the barrier level of 70 at about time 1.25 (designated by the letter “B"),   and then ends at 104.66 ("C). ABC is an example of the path that satisifies our conditions. (A probability calculation for a Brownian motion essentially consists of asking what fraction of the possible paths satisfy specific conditions.) Now consider the path ABD. This path also starts at A and hits the barrier at B,   but

After point B it is the mirror image of ABC,   reflected about the barrier level of 70. The reflection principle in this context says that for any path that starts at 80,   hits 70 and ends up above 100,   there is an equally likely path that starts at 80,   hits 70,   and ends up below 40. Because they occur with the same probability,   it does not matter whether we count paths like ABC or paths like ABD. But paths like ABD are easier to count The fraction of paths that start at 80,   hit 70,   and end up above 100 equals the fraction

Of paths that start at 80,   hit 70,   and end up below 40. But for this second set of paths,   hitting 70 is a redundant condition: Any path ending below 40 will have hit 70 along the way. The hitting condition does not matter in computing the probability using the reflected path

The level 40 in this example can be expressed as
$$\begin{array}{c}70-(100-70)=H-(K-H)\\=2 H-K\end{array}$$
Thus,   the fraction of Brownian paths which satisfy our conditions is
$$\Pr (X_{t}>K\:,   \underline{X}_{t}\leq H)=\Pr (X_{T}<2 H-K)$$
This is a standard normal probability calculation:
$$\begin{aligned}
\operatorname*{Pr}(X_{T}<2 H-K)& =\mathrm{Pr}\left (\frac{X_{T}-X_{0}}{\sigma\sqrt{T}}\leq\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right) \\
&=N\left (\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right)
\end{aligned}$$
Because of the reflection principle,   the calculation with the hitting boundary involves only a standard normal calculation.

Example 23.1 Suppose $X_{0}=80,   \sigma=10$ ,   $H=70$ $K=100$ ,   and $T=5$ years. We have
$$\begin{aligned}
\Pr (X_{T}>100,   \underline{X}_{T}\leq 70|X_{0}=80)& =N\left ({\frac{2\times 70-100-80}{10{\sqrt{5}}}}\right) \\
&=N (-1.7889)=0.0368\:\equiv 
\end{aligned}$$
If we wish to calculate $\Pr (X_{T}>100,   \underline{X}_{T}>70)$ (the probability that a knockout call will pay off),   we can use the fact that hitting and not hitting are mutually exclusive events. Thus,   
$$\begin{aligned}
\mathrm{Pr}(X_{T}>K,   \underline{X}_{T}>H)& =\mathrm{Pr}(X_{T}>K)-\mathrm{Pr}(X_{T}>K,   \underline{X}_{T}\leq H) \\
&=N\left (\frac{X_{0}-K}{\sigma\sqrt{T}}\right)-N\left (\frac{2 H-K-X_{0}}{\sigma\sqrt{T}}\right)
\end{aligned}$$

The actual barrier formulas differ in two respects from equations (23.48) and (23.49) First,   with geometric Brownian motion,   $\ln (X_{t})$ is normally distributed rather than $X_{t}$ .This results in $X_{0}$ ,   $K$ ,   $H$ ,   being replaced with $\ln (X_{0})$ ,   etc.

More importantly,   we assumed that $X$ was a Brownian motion with no drift. The construction of the reflection depends crucially on this assumption. By rewriting equatior 23.6,   however,   you can see that it reduces to equation (23.48) when $r-\delta-0.5\sigma^{2}=0$ (the logarithmic drift is zero):

$$\exp\left (2\frac{r-\delta-0.5\sigma^2}{\sigma^2}\ln (H/S)\right) N\left[\frac{2\ln (H)-\ln (S)-\ln (K)+(r-\delta-0.5\sigma^2) T}{\sigma\sqrt{T}}\right]$$

The incorporation of drift into barrier problems is discussed in Harrison (1985) and Steele (2010).

## References

Harrison,   J. M.,   1985,   Brownian Motion and Stochastic Flow Systems,   John Wiley & Sons,   New York





# Appendix 25. A CONSTRUCTING THE BDT TREE

In this appendix we verify that the tree in Figure 25.5 matches the price information in Table 25.1. We also see how to construct the tree. For reference,   Figure 25.12 depicts the one-yean zero coupon bond prices at each node of the BDT tree.

## Verifying Yields

The rate at the first node is $10\%$ ,   which corresponds to the current 1-year yield We can compute the price (and thus yield) of the 2-year zero-coupon bond by starting

In year 2 and working backward. In year 1,   the 2-year bond will be worth either 1/(1+ 0.1322)=80.8832 or $1/(1+0.1082)=\$0.9023$ Thus,   the discounted expected price at time 0 is

$$\$0.9091\times (0.5\times\$0.8832+0.5\times\$0.9023)=\$0.8116$$

Figure 25.13 illustrates the tree corresponding to this calculation The price of the 3-year zero-coupon bond is computed in a similar way. Working backward from the year-3 nodes,   we have

$$\begin{aligned}\text{S 0.9091}&\times[0.5\times\$0.8832\times (0.5\times\$0.8321+0.5\times\$0.8798)\\&+0.5\times\$0.9023\times (0.5\times\$0.8798+0.5\times\$0.9153)]=\$0.7118\end{aligned}$$

###### FIGURE 25.12
The 1-year zero coupon bond prices at each node of the BDT tree.

![](https://storage.simpletex.cn/view/f1eZBGyS3yANWH9xGS4yHKl8ecGClmDbs)

###### FIGURE 25.13
Tree illustrating the evolution of the 2-year zero-coupon bond,   based upon the prices in Figure 25.12.

![](https://storage.simpletex.cn/view/fHlSF90LE993ACccSrKFMwSgfG5ggnUpu)

###### FIGURE 25.14
Tree illustrating the evolution of the 3-year zero-coupon bond,   based upon the prices in Figure 25.12.

![](https://storage.simpletex.cn/view/fx0KG0Gzg1GuKgyzIflOozMEYPiQzyybp)

Figure 25.14 is the tree showing the evolution of the 3-year bond. Problem 25.8 asks you to verify that the tree in Figure 25.5 generates the correct 4-year zero-coupon bond price.

## Verifying Volatilities

The volatilities in Table 25.1 are yield volatilities. Thus,   to verify the volatilities implied by the tree,   we have to compute implied bond yields in year 1 and then compute the volatility For the 2-year bond (i.e.,   the 1-year bond in year 1),   the yield volatility using equation (25.45) is

$$0.5\times\ln\left (\frac{0.8832^{-1}-1}{0.9023^{-1}-1}\right)=0.1$$

From Figure 25.14,   the 3-year bond in year 1 (which will be a 2-year bond) will be worth either $\$0.7560$ ,   with a yield of $0.7560^{-1/2}-$l=0.1501 or $0.8099^{-1/2}-1=0.1112$ The yield volatility is then

$$0.5\times\ln\left (\frac{0.1501}{0.1112}\right)=0.15$$

Both vield volatilities match the inputs in Table 25.1.

Problem 25.9 asks you to verify that the tree generates the correct 4-year yield volatility

## Constructing a Black-Derman-Toy Tree

We have verified that the tree inFigure 25.5 is consistent with the data in Table 25.1. Now we turn the question around: Given the data,   how did we generate the tree in the first place? The answer is that we started at early nodes and worked to the later nodes,   building the tree outward

The first node is given by the prevailing 1-year rate. Therefore,   the 1-year bond price is

$$\$0.9091=\frac{1}{1+R_0}$$

Thus,   $R_{0}=0.10$

For the second node,   the year-1 price of a 1-year bond is $P (1,   2,   r_{u})$ or $P (1,   2,   r_{d})$ We require that two conditions be satisfied

$$\begin{aligned}
\$0.8116& =\frac{1}{1+0.10}\left[0.5\times P (1,   2,   r_{u})+0.5\times P (1,   2,   r_{d})\right] \\
&=\frac{1}{1+0.10}\left (0.5\times\frac{1}{1+R_{1}e^{2\sigma_{1}}}+0.5\times\frac{1}{1+R_{1}}\right) s \\
\text{0.10}& =0.5\times\ln ([P (1,   2,   r_{u})^{-1}-1]/[P (1,   2,   r_{d})^{-1}-1]) \\
&=0.5\times\ln (R_{1}e^{2\sigma}/R_{1})
\end{aligned}$$

The second equation gives us $\sigma=0.1$ ,   and this value enables us to solve the first equation to obtain $R_{\mathrm{l}}=0.1082$

It is a bit messier to solve for the next set of conditions,   but conceptually we are still fitting two parameters ( $R_{2}$ and $\sigma_{2}$ ) to match two inputs (the 3-year yield and the 2-year yield volatility 1 year hence). The possible prices of a 2-year bond at the two nodes in year 1 arc $P (1,   3,   r_{u})$ and $P (1,   3,   r_{d}).$ Thus,   we have the two conditions

$$\begin{aligned}
\$0.7118& =\frac{1}{1+0.10}\left[0.5\times P (1,   3,   r_{u})+0.5\times P (1,   3,   r_{d})\right] \\
&=\frac{1}{1+0.10}\left[0.5\times\frac{1}{1.1322}\left (0.5\times\frac{1}{1+R_{2}e^{4\sigma_{2}}}+0.5\times\frac{1}{1+R_{2}e^{2\sigma_{2}}}\right)\right] \\
&+0.5\times\frac{1}{1.1082}\left (0.5\times\frac{1}{1+R_{2}e^{2\sigma_{2}}}+0.5\times\frac{1}{1+R_{2}}\right) \\
\text{0.15}& =0.5\times\ln ([P (1,   3,   r_{u})^{-1/2}-1]/[P (1,   3,   r_{d})^{-1/2}-1]) 
\end{aligned}$$

By iterating,   it is possible to solve $R_{2}$ and $\sigma_{2}$ . In the same way,   it is possible to solve for the parameters for each subsequent period.
