---
title: Appendix 9.B Algebraic Proofs of Strike-Price Relations
---

# Appendix 9.B Algebraic Proofs of Strike-Price Relations

In Chapter 9 we demonstrated severalpropositions about how option prices change when the strike price changes. To prove these propositions we will consider strike prices $K_{1},    K_{2}$ and $K_{3}$ ,  where $K_{1}<K_{2}<K_{3}$. Define $\lambda$ so that
$$\lambda=\frac{K_3-K_2}{K_3-K_1}$$ or
$$K_2=\lambda K_1+(1-\lambda)K_3$$
Since we are considering options that differ only with respect to the strike price. We can write $C(K)$ and $P(K)$ to denote the option premium for a particular strike. $K$

### The Call Premium Decreases as the Strike Price Increases
Suppose that $C(K_{\mathrm{l}})<$ $C(K_{2})$ ; i.e.,  a lower strike call had a lower premium. To effect arbitrage,  we would buy the low-strike call and sell the high-strike call (this is a bull spread). Table 9.10 shows the result. We will consider each entry in the “Total”row separately Time 0. We earn net premium from selling the more expensive option. The cash flow is positive.

###### Expiration or Exercise,  $S_{T}<K_{1}$
- Neither option is exercised,  so the cash flow is zero.

###### Expiration or Exercise,  $\kappa_{1}\leq S_{T}\leq\kappa_{2}$
- We exercise the option we bought,  earning $S_{T}-K_{\mathrm{l}}$

###### Expiration or Exercise,  $S_{T}>K_{2}$
- We exercise the option we bought,  earning $S_{T}-$ $K_{1}$ ,  and the option we sold is exercised,  costing us $K_{2}-S_{T}$ .
- The net is $K_{2}-K_{1}$ which is positive.

What about the fact that the options are American? We then have to account for the possibility that the written option is exercised. If that happens,  we can simply exercise the purchased option,  earning the payoffs in the table. If it is not optimal to exercise the purchased option,  we can sell it,  earning even higher payoffs

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
			<td>$C (K,  )-C (K_{1})$</td>
			<td>0</td>
			<td>$S_{T}-K_{\perp}$</td>
			<td>$K_{2}$ $,  -K.$ I</td>
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
			<td>$\operatorname{Lend}K,  -K_{\mathrm{I}}$</td>
			<td>$-(K,  -K_{1})$</td>
			<td>$(K,  -K_{1})$</td>
			<td>$(K,  -K_{1})$</td>
			<td>$(K,  -K_{1})$</td>
		</tr>
		<tr>
			<td>Total</td>
			<td>$C (K_{1})-C (K_{2})-$ $(K,  -K_{1})$</td>
			<td>${\overline{e^{rT}(K_{2}-K_{1})}}$</td>
			<td>$\overline{e^{rT}(K_{2}-K_{1})-}$ $(S_{T}-K_{\mathrm{l}})$</td>
			<td>${\overline{e^{rT}(K_{2}-K_{1})}}$ $(K_{2}-K_{\mathrm{l}})$</td>
		</tr>
		<tr>
			<td> </td>
			<td>$(K,  -K_{1})$</td>
			<td> </td>
			<td>$(S_{T}-K_{1})$</td>
			<td>$(K,  -K_{1})$</td>
		</tr>
	</tbody>
</table>

### The Call Premium Changes by Less Than the Change in the Strike Price
Suppose that $C(K_{1})-C(K_{2})\geq K_{2}-K_{1}$ We can make money initially by selling the $K_{1}$ strike call buying the $K_{2}$ -strike call,  and lending $K_{2}-K_{\mathrm{l}}$ Table 9.11 summarizes the results

Time 0. We earn net premium since the initial assumption is that $C(K_{\mathrm{l}})-C(K_{2})\geq$ $K_{2}-K_{1}$ Expiration or Exercise,  $S_{T}<K_{1}$ . Neither option is exercised,  so we keep the future value of the difference between the strikes. Expiration or Exercise,  $K_{1}\leq S_{T}\leq K_{2}$ . The written option is exercised,  so we have to sell the stock for $K_{1}$ . However,  the net loss is less than the difference between the strike prices Expiration or Exercise,  $S_{T}>K_{2}$ .We keep the interest on the difference between the strike prices

What adjustments do we have to make if the options are American? If the written $K_{\mathrm{l}}$ option is exercised,  we can duplicate the payoffs in the table by throwing our option away (if $K_{1}\leq S_{T}\leq K_{2})$ or exercising it (if $S_{T}\geq K_{2}$ ). Since it never makes sense to discard an unexpired option,  and since exercise may not be optimal,  we can do at least as well as the payoff in the table if the options are American. You may have noticed that if the options are European,  we can put a tighter restriction on the difference incall premiums—namely,  $C(K_{1})-C(K_{2})<PV(K_{2}-K_{1})$ We would show this by lending $PV(K_{2}-K_{1})$ instead of $K_{2}-K_{1}$ . This strategy does not work if the options are American,  since we do not know how long it will be before the options are exercised,  and,  hence,  we do not know what time to use in computing the present value.

```latex

\usepackage{tikz}
\begin{document}
  \begin{tikzpicture}[domain=0:4]
    \draw[very thin,   color=gray] (-0.1,   -1.1) grid (3.9,   3.9);
    \draw[->] (-0.2,   0) -- (4.2,   0) node[right] {$x$};
    \draw[->] (0,   -1.2) -- (0,   4.2) node[above] {$f(x)$};
    \draw[color=red]    plot (\x,   \x)  node[right] {$f(x) =x$};
    \draw[color=blue]   plot (\x,   {sin(\x r)})    node[right] {$f(x) = \sin x$};
    \draw[color=orange] plot (\x,   {0.05*exp(\x)}) node[right] {$f(x) = \frac{1}{20} \mathrm e^x$};
  \end{tikzpicture}
\end{document}

```

### The Call Premium Is a Convex Function of the Strike Price
This proposition says that as the option moves more into the money,  its premium increases at a faster rate. To prove it,  suppose that $C(K_{2})\geq\lambda C(K_{1})+(1-\lambda)C(K_{3})$ We can make money initially by selling the $K_{2}$ -strike call,  buying $\lambda$ $K_{\mathrm{l}}$ -strike calls,  and buying $1-\lambda$ $K_{3}$ -strike calls. Table 9.12 summarizes the results.

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

###### Expiration or Exercise,  $S_T<K_1$
- No options are exercised

###### Expiration or Exercise,  $K_{1}\leq S_{T}\leq K_{2}$
- The purchased $K_{\mathrm{l}}$ calls are exercised.
###### Expiration or Exercise,  $K_{2}<S_{T}\leq K_{3}$
- We exercise our 入 $K_{1}$ calls,  and the written $K_{2}$ call is exercised against us.
- Recall that $K_{2}=\lambda K_{1}+(1-\lambda)K_{3}$ ; substituting this expression for $K_{2}$ explains how we obtain the total in this column.
###### Expiration or Exercise,  $S_{T}>K_{3}$
- All options are exercised and the payoffs cancel.

## Puts
Here are the counterpart propositions for puts,  stated more formally

1. The put premium is increasing in the strike price: $P(K_{1})\leq P(K_{2})$ 2. The put premium changes by less than the change in the strike price: $P(K_{2})-$ $P(K_{1})<K_{2}-K_{1}$ 3. The put premium is a convex function of the strike price: $P(K_{2})<\lambda P(K_{1})+($ l- $\lambda)P(K_{3})$ .

The proofs are identical to the propositions for calls.