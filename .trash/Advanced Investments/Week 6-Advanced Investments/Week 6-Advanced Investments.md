---
title: $\textbf{6. 1}$ $\textbf{SOURCES OF LEVERAGE}$
aliases: [$\textbf{6. 1}$ $\textbf{SOURCES OF LEVERAGE}$]
linter-yaml-title-alias: $\textbf{6. 1}$ $\textbf{SOURCES OF LEVERAGE}$
---

---
title: $\textbf{6. 1}$ Sources of leverage
aliases: Sources of leverage
Sources of leverage
---

Lecture 6

Optimal asset allocation models may sometimes recommend allocations in which risky assets account for more than $100\%$ of the total wealth invested in the portfolio. The excess over and above $100\%$ needs to be financed with debt, either explicitly so, or implicitly by taking positions in derivative securities to get the level of risk exposure that the asset allocation model prescribes.

A good example is the risk parity strategy that we looked at in lecture 2. Back then we focused on the relative weights risky assets with the risky asset portfolio. These relative weights were scaled to sum to unity. But these relative weights don't tell us about the size of the investment, relative to wealth, that an optimizing investor would put into this strategy.

Because the risk parity strategy has high weights in bonds, which have relatively low volatility, the overall volatility of the risk parity portfolio is quite low if the weights are scaled to sum up to one. Over the last 30 years, the annualized volatility was $6.92\%$ with an annualized mean excess return of $4.95\%.$ The volatility of this portfolio is much lower than the volatility of the stock index, which was $15.31\%$ over the same time period, with mean excess return of $8.02\%.$ This means that an investor who, given their level of risk aversion, would be comfortable holding a portfolio with volatility equal to the stock index volatility, would find the risk parity portfolio to be insufficiently risky and would want to take on leverage to increase the risk and return of the risk parity portfolio. Indeed, investment managers offering risk parity funds often lever up the risk parity portfolio so that it achieves a level of volatility comparable to the stock index volatility.

How much leverage do we need to get it up to $15\%$ volatility? Recall that if we take a position with weight $\omega$ in a risky asset with return $R_t$,we have portfolio variance $\operatorname{var}(R_{p,t})=\omega^2\operatorname{var}(R_t).$ So, in terms of standard deviations, and with $R_t$ now the return of the risk parity portfolio, we are looking for an $\omega$ that delivers

$$15.31\%=\omega\times6.92\%$$

asset classes in the risk parity portfolio summing up to one), funded by $1.21 of debt. Figure 6.1 shows the weights of the leveraged risk parity strategy that the investor then ends up holding once the risk parity strategy is combined with leverage. The weights now add up to 2.21, instead of to one.

![](https://img.simpletex.net/pdf/BzBdZhAg/fnkQ0QPdSoV5AO3cI779VVpwIhRLS2E5C.png)

Figure 6.1: Weights of risk parity portfolio (10 years of data to estimate standard deviations)

The weights of the risk parity portfolio are all positive. In this case, the ratio of assets held by the portfolio as long positions $(\$2.21)$ divided by the wealth invested by the investor $(\$1)$ measures the leverage of the portfolio:

average$= \frac {\text{value ol onlg posı lı ons}}{\mathrm{NAV}}=$Sum of portfolio weights that are greater than zero $\begin{aligned}(6.1)&(6.1)\\\text{where NAV is the net asset value of the portfolio after subtracting the debt, i.e., this is}\\\text{the investor's own wealth invested in the portfol}\end{aligned}$ leverage.

What if there are short positions in the portfolio? The leverage ratio above simply ignores the short positions. An alternative is the net leverage ratio that subtracts the Vet leverage $$=\frac{\text{Value of longshort positions}}{\mathrm{NAV}}= \text{Sum of portfolio weights}\tag{6.2}$$

Which of these two is a better measure depends on the purpose for which we use the measure and on the nature of the short positions.

If we are interested in understanding the funding requirements of a portfolio, the leverage ratio in (6.1) may be more informative than the net leverage ratio. In an ideal frictionless world, an investor could use the proceeds from a short sale as financing to enter a long position. For example, the investor could sell short $100 worth of stock and use the proceeds to buy $100 of stock and thereby construct a long-short portfolio with zero NAV investment. But this is not how this works in practice. In practice, the investor would have to leave the short sale proceeds of $100 as collateral deposit with the broker because the broker wants to make sure that the investor has sufficient funds to repurchase the stock when the short position is closed at some point. In fact, since there is the risk that the stock price could rise subsequent to the execution of the short sale, the broker will require more than $100 of collateral deposit. For stocks this could be something like $150 (called initial margin), and this required amount will rise (called variation margin) if the price of the stock rises subsequently. In this way, the broker tries to ensure that the investor has sufficient funds to eventually repurchase the stock even if the stock price has gone up. So short sales don't generate funding, they consume funding. The leverage ratio then provides a better characterization of the funding needs of the portfolio. By ignoring short positions, it does not account for the fact that short positions consume funding, but at least it does not assume that short positions generate funding. It treats a $100 short sale as generating a margin requirement of $100. In contrast, by subtracting short positions from the long position, using the net leverage ratio in (6.3) to assess funding requirements would assume that a $\$100$ short sale requires no margin whatsoever and therefore generates $100 of funding that can be used to finance long positions.

Here is an example. Suppose we want to invest $1m of wealth to buy $1.5m of asset $A$ and short $0.5m of asset $B.$ Suppose for now that our broker requires only to keep the $\$0.5$m short-sale proceeds as collateral for the short sale of asset $B$, not more. Then we can use our $1m of wealth combined with $0.5 of debt financing to fnance the long position. The difference between the leverage ratio in (6.1) and unity correctly gives us the amount of debt financing required: 1.5-1=0.5 in this case. In contrast, the net leverage ratio is 1.0 in this case, which doesn't reveal the debt funding needs.

In practice, our broker will ask some excess collateral for the short position—-i.e., more than the proceeds from the short sale—which is called $margin.$ So the calculation

If we want to use versions of a leverage ratio to gauge how risky a portfolio is, then whether the leverage ratio or the net leverage ratio is better depends on the nature of short positions. Consider first the case that short positions are hedges of long positions, which means that the assets held long have strong positive correlation with the assets that are sold short. In this case, the overall the long minus short position has reduced risk compared to a long-only position and the net leverage ratio may be a better measure. For example, if we invest $1m of wealth to buy $1.5m of asset $A$ and short $0.5m of asset $B$, and the returns of asset $B$ have a correlation of one with the returns of asset $A$, then we are really just exposed to $\$1$m worth of asset $A$ risk, because part of our $\log$ position in $A$ is perfectly hedged by the short position in asset $B.$ So subtracting short positions from the long positions as in the net leverage ratio (6.3) is the right thing to do in this case. By netting long and short positions, this formulation accounts for the risk-reducing effect of short positions. In contrast, if a substantial part of the short positions are not hedges and actually add to the risk of the portfolio because the correlation is much lower than one, the leverage ratio (6.1) may be better. If most short positions are not hedges and are adding risk to the portfolio, the gross leverage ratio

Gross leverage $=\frac{\text{Value of long + short positions}}{\mathrm{NAV}}=$
Sum of absolute value of portfolio weights

may be an even better proxy for the risk of a levered portfolio

# $\textbf{6. 1}$ $\textbf{SOURCES OF LEVERAGE}$

Before we look at risk and return consequences, it's useful to first look in more detail at the mechanisms used by investors in practice to obtain leverage. Some of them involve actual borrowing of money, but others are structured as derivative contracts in which borrowing is implicit, not explicit.

# $\textbf{6. 1. 1}$ $\textbf{MARGIN LOANS AND REPO}$

Suppose you want to buy $$2m of stocks, but fnanced with borrowed money, to the extent possible. The most direct way of doing this is to obtain a margin loan from a broker. The broker takes the assets in the account, including the stocks bought with the margin loan, as collateral with a $50\% \textit{ initial margin requirement, the broker will require a }50\%$ equity contribution from you. In this example, if you want a initiate a position of $2m worth of stocks as the total assets in your account, you will need to make an equity contribution of $2m $\times0.50=\$1$m. Hence, the broker will provide provide at most $2m~- $1m = $1m of margin loans for this portfolio of \$ 2m worth of stocks. 

After the leveraged position is initiated, the broker will require a maintenance margin that is lower than the initial margin requirement. A typical value is $25\%$ or slightly above. Let's stick to $25\%.$ This means that when the value of the stock portfolio falls a lot, you will have to deposit additional cash into your account (this is a $margin\textit{ call}).$ For example, if the value falls from $\$2$m initially to S1.2m, then, given the margin debt of $\$1$m, your equity position has fallen to $\$1.2$m- $$\$1$m = $0.2m, which is less than the required maintenance margin of $1.2m ×0.25=$0.3m.

If you do not respond promptly to the margin call (typically until the next business day) and deposit additional funds, the lender will take the collateral and liquidate it. Thus, the collateral gets replenished with additional funds daily. From the broker's viewpoint, the loan is therefore very safe. The broker is only exposed to the risk of loss if a price move between the last collateral replenishment until the time of liquidation is so big that it burns through all the maintenance margin. For this reason, for professional investors like hedge funds, the interest rates on margin loans are very close to the risk-free rate.

Suppose you enter this leveraged position in stocks $(\$2$m in stocks, financed with margin loan of $1m, with initial margin $50\%)$ for one year. During this one year period, the stock portfolio earns a random return of $R.$ At the end of the year you sell the stock portfolio and pay back the margin loan. The interest rate on the margin loan is the risk-free rate, which happens to be $5\%.$ The cash flows from your leveraged position are then as shown in the table below (with one simplification: the table only shows the cash flow for the initial margin. It does not show the cash flows that arise if the asset price changes during the margin loan's lifetime and maintenance margin requirements trigger margin calls).

<table>

<tbody>

<tr>

<td> </td>

<td> </td>

<td>$\mathbf{t}=1$</td>

<td>$\mathbf{t}=1$</td>

</tr>

<tr>

<td> </td>

<td>Stock position $\mathbf{M}$argin loan</td>

<td>$\$2$m $\times(1+R)$ $-\$1$m $\times(1+0.05)$</td>

<td>$\$2$m $\times(1+R)$ $-\$1$m $\times(1+0.05)$</td>

</tr>

<tr>

<td> </td>

<td> Net</td>

<td>$\$0.95$m$+\$2$m$\times R$</td>

<td>30.95m$+\$2$m$\times R$</td>

</tr>

</tbody>

</table>

For bonds, but sometimes for stocks, too, it is very common to structure collateralized borrowing in the form of sale and repurchase agreement (repo). Legally, the

and this repurchase price is already fixed on the initiation date of the repo. For example, the numbers corresponding to our margin loan example above would be that the borrower commits to repurchase the collateral at a price of $2 ×(1+0.05). The interest implied by the repurchase price $(5\%$ in our example) is known as the $\textit{repo rate. Re- }$ pos are economically still like a loan, but structuring the loan as a sale and subsequent repurchase of a security makes the loan even safer for the lender, because it makes it legally easier for the lender to liquidate the collateral in the event the borrower defaults on the loan. Repo rates are therefore basically risk-free rates.

# $\textbf{6. 1. 2}$ $\textbf{SWAPS AND FORWARDS}$

Derivatives contracts are frequently used as an alternative way of obtaining leverage. One very common type of contract is a $total\textit{ return swap (TRS). In a TRS, one coun- }$ terparty pays the other the total return that an underlying asset earned over the life of the contract, while the other party makes a fixed payment that was agreed upon at the initiation date of the contract.

In our example, suppose that the counterparties (investor and broker) agree to a TRS with notional amount of $2m. In the TRS, the broker promises to pay the investor the total return of a specified stock portfolio (e.g., a stock index) during the coming year times the notional amount. This means if the stock portfolio earns the return $R$ (which is uncertain at the time of contract initiation), the broker pays the investor $2m ×R (if $R$ happens to be negative, the investor pays the broker). In turn, the investor promises the broker to pay the notional amount times a fixed interest rate $R_swap.$ So the net cash flow to the investor is $2m(R-R_\textit{swap}).$

What would that fıxed interest rate $R_{swap}$ have to be? We can see this easily if we compare the swap cash flows to the cash flows from a margin loan:
$\bullet$ The investor buys stock portfolio worth $2m
$\bullet$ The investor gets margin loan of $2m with zero margin requirement
Then one year later,
| | | $\bullet$ The stock portfolio is worth $2m $\times(1+R)$ | | |
| | | $\bullet$ The investor pays back margin loan $2m $\times(1+R_f)$ | | |

same as those in the swap case, and the risk of cash flows in the second period are the same (risky return $R$ minus a fıxed number) the cash flows to the investor in the second period also have to be the same—otherwise there would be an arbitrage opportunity between margin loans and swap markets. Hence, $R_swap=R_f$ must hold.$^1$

In addition, a typical swap contract would also require the investor to post margin. In the table below, I calculate the net cash flows to the investor if the risk-free rate is $R_f=0.05$ and the required initial margin is $50\%$ of the notional amount of the swap.

![](https://img.simpletex.net/pdf/BzBdZhAg/fteMoCkYZtCWzHGRe6xcXU4I8Id3KUqg1.png)

Comparing the cash flows of the TRS with the margin loan above, we see that they are exactly the same. Hence, a TRS achieves the same purpose as a margin loan. But some of the terms could be different. For example, TRS could have lower margin requirements than a margin loan.

In this one period case, the TRS is equivalent to another type of derivative, a forward $contract.^2$ The forward contract version of our example would be an agreement at $t=0$ to purchase the stock portfolio at $t=1$ at a price of $2m $\times(1+0.05)$, where this price, the $\textit{forward price is already contractually fı xed at }t= 0.$ The resulting cash flows for the investor from the forward contract are then the same as in the swap: The investor receives an asset with value $\$2$m $\times(1+R)$ and pays $\$2$m $\times(1+0.05)$ for it, which leaves a net cash flow (before margin payments) of $\$2$m $\times (R0. 05).$ But unlike forward contracts, a swap can involve a whole stream of payments. For example, a TRS could specify that each quarter, the swap pays the $2m times the return earned by the stock portfolio $R$ in that quarter minus the three-month risk-free interest rate.

$^{1}$If two investment strategies deliver cash flows in two periods and the cash flows of the two strategies are identical in one period, they must also be equal in the other period, otherwise an investor could make riskless profits by going long in one strategy and short in the other strategy. Absence of such arbitrages is a fundamental pricing principle in finance.

$^2$And in turn, futures contracts are almost equivalent to forward contracts, with some differences about the way margining is handled. Moreover, futures contracts are traded on exchanges, while forward contracts and swaps are arranged over-the-counter bilaterally between counterparties.

Table 6.2 shows typical margin requirements (ranges that include initial and maintenance margins) for margin loans for various types of assets and for derivatives contracts. The table also shows the maximum leverage ratio that an investor can achieve given these margin requirements.

Margin requirements by security type.

The table lists the margin requirements and their implied level of leverage in various security markets. The data are obtained by collating information from prime brokers and derivatives exchanges as of $\textbf{March 2010. }$

<table>

<tbody>

<tr>

<th> </th>

<th>$\textbf{Margin}$ $(\mathbf{haircut})$</th>

<th>$\mathbf{Implied}$ $\textbf{leverage}$</th>

</tr>

<tr>

<td>Treasuries</td>

<td>$\mathbf{0.1-3\%}$</td>

<td>33-100</td>

</tr>

<tr>

<td>Investment grade corp bonds</td>

<td>$5-10\%$</td>

<td>$\mathbf{10-20}$</td>

</tr>

<tr>

<td>High yield bonds</td>

<td>$10-15\%$</td>

<td>6.6-10</td>

</tr>

<tr>

<td>Convertible bonds</td>

<td>$15-20\%$</td>

<td>5-6.6</td>

</tr>

<tr>

<td>$\mathbf{Equities}$</td>

<td>5-50%</td>

<td>2-20</td>

</tr>

<tr>

<td>Commoditv $\textbf{futures}$</td>

<td>$10\%$</td>

<td>10</td>

</tr>

<tr>

<td>Financial futures</td>

<td>$3\%$</td>

<td>33</td>

</tr>

<tr>

<td>Foreign e $\mathbf{exchange}$ 1 futures</td>

<td>$2\%$</td>

<td>50</td>

</tr>

<tr>

<td>$\mathbf{Options}$ s (equity)</td>

<td>$75\%$</td>

<td>1.3</td>

</tr>

<tr>

<td>Interest rate swaps</td>

<td>$1\%$</td>

<td>100</td>

</tr>

<tr>

<td>Foreign exchange swaps</td>

<td>$1\%$</td>

<td>100</td>

</tr>

<tr>

<td>Total return swaps</td>

<td>$10\%$</td>

<td>10</td>

</tr>

</tbody>

</table>

Figure $6.2{:\text{ Typical margin requirements}}$

Source: Ang, A., Gorovyy, S. and Van Inwegen, G.B., 2011. Hedge fund leverage.

Journal of Financial Economics, 102(1), pp.102-126.

6.2 Risk and return from dvnamic leverage strate

$\textbf{gies}$

Leveraging a portfolio can produce some counterintuitive results in the long-run. To illustrate, consider the product shown in Figure 6.3. It presents information about the

three times the return of the S&P500 index—and it's therefore commonly referred to as a 3x levered ETF. It does so with a mix of direct investments in the stocks comprising the S&P500 and total return swaps with fnancial institutions. As the scatter plot in the middle of the figure shows, the fund achieves this objective to a high degree. On every day, the UPRO return is pretty much exactly 3x the S&P500 index return.

The long-run returns shown in the table at the bottom of the fgure may seem puzzling, though, in comparison to the total returns of the S&P500 index that are reported in the bottom row of the table. For example, in 2023Q3, when the S&P500 lost 3. 27$\%$, UPRO lost 13. 00$\%$, which far more than 3x the loss of the S$\&$P500. Over longer horizons, from year-to-date all the way back to fund inception in 2009, both the S&P500 and UPRO earned positive returns, but UPRO earned far less than 3x the return of the S&P500. Of the the past 5 years, UPRO's return was even less than 1x the S'esp500. How is it possible that UPRO delivers almost exactly three times the return of the S&P500 on every given day, but much, much lower returns than three times the S&P500 during the longer holding period returns?

This seemingly strange behavior of long-run returns is the reason why discussions of levered ETFs often come with statements such as that these ETFs are “only suitable for investors with a short horizon" and “not suitable for a long-term buy-and-hold investor.” Further, these discussions often mention “volatility decay" as the source of long-run value destruction for a buyandhold investor, usually with examples such as the following one: 

Suppose a 3x levered ETF tracks an index that has a value of 100 and the ETF has a NAV of $100 at the end of day $t=0.$ The index then falls by $10\%$ on day $t=1$, then rises by $10\%$ on day $t=2.$ Thus, over this two-day period, the market fell by $1\%.$ What's the levered ETF's performance? It falls by $30\%$ on day $t=1$, to a NAV of $70, then it rises by $30\%$ to NAV of $\$91.$ So while the index fell by $1\%$ over the two-day period, the 3x levered ETF fell by $9\%$ (not $3\%$ as one naively may have expected). Now if you repeat this example with bigger price moves (say $15\%$ instead of $10\%$ daily moves for the index), you'll get an even bigger discrepancy of the two-day ETF return from three times the index return. Hence the name volatility decay.

So this looks bad. Are we exposing ourselves to inevitable wealth destruction if we buy-and-hold a levered ETF for the long-term? How is this possible? We are just taking a position in the index. It's levered, but still, wealth can't just evaporate just because we take a levered position. Leverage can increase the risk of a disastrous return, but it should at the same time also increase the chances of a very large gain. It should not have the effect of leading to certain wealth destruction.

UPRO

UltraPro S&P500

# INVESTMENT OBJECTIVE

ProShares UltraPro S&P500 seeks daily investment results, before fees and expenses, that correspond to three times (3x) the daily performance of the S&P 500®.
Daily performance of UPRO vs. index during 3Q 2023
$\mathrm{Correlation~}^3=0.99$
$\mathrm{Beta~}^4=3.01$
The scatter graph charts the daily NAV-to-NAV $3\%$ results of the fund against its underlying index return on a daily basis.

![](https://img.simpletex.net/pdf/BzBdZhAg/fQpwpPDd5o09lRF9SMkDmXvrXKm5hoiF1.png)

Daily change in index return

![](https://img.simpletex.net/pdf/BzBdZhAg/fg2ZlFwfxR1lFrNgqGvIfGybD5Y4Iq0C2.png)

Figure $6.3{:\text{ Levered exchange-traded product UPRO}}$ return of a leveraged position in the index, with leverage ratio $\omega>1$, is $R_t=\omega R_m,t.$
Now consider frst the expected two-period compound return on the index

$$\begin{aligned}\mathbb{E}[R_{m,1:2}]&=\mathbb{E}[(1+R_{m,1})(1+R_{m,2})]-1\\&=\mu+\mu+\mathbb{E}[R_{m,1}R_{m,2}]\\&=2\mu+\mu^2.\end{aligned}$$

(6.4)

Next, consider the expected two-period compound return for a portfolio with constant leverage $\omega>1$,

$$\begin{aligned}\mathbb{E}[R_{1:2}]&=\mathbb{E}[(1+\omega R_{m,1})(1+\omega R_{m,2})]-1\\&=2\omega\mu+\omega^2\mu^2\\&=2\omega\mu+\omega\mu^2+(\omega^2-\omega)\mu^2\\&=\omega\operatorname{E}[R_{m,1:2}]+(\omega^2-\omega)\mu^2.\end{aligned}$$

(6.5)

The first term on the bottom line is the expected two-period return of a static leveraged strategy that takes leverage $\omega$ at $t=0$ but then does not rebalance back to a leverage ratio of $\omega$ at the end of $t=1.$ The expected return of this static leveraged strategy is simply $\omega$ times the expected two-period return of the index. But the frequentlyrebalanced strategy that always keeps leverage at $\omega$ has higher expected returns. With leverage, i.e., $\omega>1$, the second term $(\omega^2-\omega)\mu^2$ is greater than zero! This means that the expected return of the constant-leverage strategy is is actually greater than $\omega$ times the expected return of the index over the same period! And volatility doesn't even show up anywhere in the expected return formula above. So where is the “volatility decay”?

One could do the same calculation for more periods than two. The result would be qualitatively the same. In terms of expected return, there is no hint whatsoever that a constant-leverage strategy leads to wealth destruction in terms of expected return! Its expected long-run compound return is even higher than the expected return of a static leveraged strategy that takes leverage initially but then does not rebalance subsequently.

To understand what's going on, let's have a look at simulations. I simulate log-normal daily index returns over 3 years with 250 trading days in each year. The $\log$ risk-free rate is $r_f=0.02/250$, index $\log$ excess returns are distributed $r_m,t-r_f\sim\mathcal{N}(\mu,\sigma^2)$ with $\mu=0.02/250$ and $\sigma=0.20/\sqrt{250}.$ I then calculate, every day, the return on a leveraged strategy that takes constant leverage $\omega$, rebalanced every day, with daily return

$$R_t=R_f+\omega(R_{m,t}-R_f).$$

(6.6)

I then compound these returns for 750 days, and I simulate many such paths.

![](https://img.simpletex.net/pdf/BzBdZhAg/f0ya9GPek0f27pHAxGgRFsfKEdigUZ7TV.png)

Day

Figure 6.4: Simulated compound returns over 3 years in a 3x leveraged strategy

Figure 6.4 shows 100 such paths. A closer look at the fgure shows that a large number of these paths end at 3-year returns lower than zero. On these paths, the wealth destruction story seems to play out. But note that there are some paths on which the wealth gain is enormous. On the path with the maximum wealth gain among these 100 paths, the 3x leveraged strategy earns more than 2,000% over the 3-year period. $\bar{\text{Also, because the strategy is rebalancing back to 3x leverage every period, wealth never}}$ falls to zero. Whenever there is a loss, leverage goes up above 3x (as the equity in our position falls), but we rebalance back to 3x, which reduces the risk of a big loss that could wipe out all wealth. In contrast, a strategy that takes 3x leverage in the beginning and then does not rebalance every period faces a high risk that a sequence of bad returns completely wipe out all wealth.

Thus, returns are extremely skewed. Very often, the leveraged strategy loses in the long-term, but in some cases it earns a spectacular return. And in some cases, it suffers huge losses, but losses that are still smaller than the losses one would get from a levered strategy without rebalancing.

We can see this more clearly in the histogram shown in Figure 6.5. The blue bars

$3\times Leveraged$

|Index

0.8

0.6

0.4

0.2

0

0

5

Figure 6.5: Histogram of simulated compound returns over 3 years in 3x leveraged and

$\underset{\text{unleveraged strategy}}{\operatorname*{\text{unleveraged strategy}}}$

show the histogram of 3x levered 3-year returns from 1,000 simulations. It shows that in the majority of simulation runs, the 3-year return is negative, but there is also a very $\log$ right-tail of rare, but extremely large positive returns. In comparison, the orange bars show the histogram of the index returns without leverage. For index returns the vast majority of 3-year returns are positive, and the right tail of positive returns is much less pronounced.

This resolves our puzzle: An investor in a 3x levered strategy experiences extremely skewed returns. Most of the time, the strategy yields negative long-run returns. On commonly occurring paths, there is wealth destruction. But with a small probability, the strategy achieves an extremely large positive return. As a consequence, in terms of expected returns, or expected wealth, in the long-run, the strategy looks just fine. There is no mysterious wealth destruction. As we calculated earlier, the leveraged strategy's expected long-run return is more than 3x higher than the expected long-run return of the index.

Therefore, it is not true that a long-run buy-and-hold investor would necessarily find

the 3x leveraged strategy unattractive. Whether this is so depends on the level of risk

Now what about our earlier numerical example that seemed to provide a nice intuition that volatility of the index return seemingly inevitably leads to poor returns of the leveraged strategy? The problem with this example is that it tells only part of the story. The path of the index return that we considered in this example (index down $10\%$, then up $10\%)$ was one in which there happened to be lots of mean reversion: the return on day $t=1$ is followed by a return on day $t=2$ with the opposite sign and the same magnitude. But this is not typical. If returns are IID, then it is as likely that the (unexpected) return the next day is a continuation in the same direction as the (unexpected) return on the day before.

So how does the numerical example play out if there is return continuation? Suppose the market goes up by $10\%$ two days in a row. Then the index goes up by 21% over two days. What happens to the 3x levered ETF? It goes up by $30\%$, and then once more by $30\%$, which yields a two-day return of $69\%$, which is higher than three times the return of the index over these two days! Next, consider continuation on the way down, with -$10\%$ on the index followed by -$10\%$, which yields a two-day index return of -$19\%.$ The 3x levered ETF return is -$30\%$ and -$30\%$, which yields a two-day return of -$51\%$, which is again higher than three times the two-day return of the index!

Therefore, in terms of the expected long-run returns, the poor performance of the leveraged strategies (worse than 3x the long-run return of the index) on paths on which there happens to be mean-reversion is balanced by the good performance (better than 3x the long-run return of the index) on those paths on which there happens to be continuation. That's why the expected long-run return of the leveraged strategy is not worse than 3x the long-run return of the index.

Here is another way to think about the performance deterioration of a leveraged strategy performance due to mean reversion. Recall from our discussion in the last lecture that rebalancing to a fıxed risky asset weight was a contrarian strategy. If you start with $\omega=0.5$ and the value of stocks doubles, the portfolio weight of stocks goes to $\omega=0.66$ and so to rebalance back to $\omega=0.5$ you need to sell stocks. However, that discussion back then focused on a strategy without leverage and hence $\omega<1.$ When a strategy is leveraged, and hence $\omega>1$, it is actually the opposite: Rebalancing is now a $positive\textit{ feedback strategy, not a contrarian one. For example, if you start with }\omega = 2$ and the value of stocks doubles, then the value of your equity position triples, hence leverage falls to $\omega=4/3\approx1.33$, so to rebalance back to $\omega=2$ you need to buy stocks! And following a positive-feedback strategy when returns are mean-reverting is a money loser.

lot of return continuation on these paths. Hence, a positive feedback strategy did well on these paths. In contrast, on paths on which the market largely moved sideways overall, we have that price movements up are largely offset by price movements down in other periods which hurts the performance of a positive-feedback strategy.

Overall, this analysis shows how a simple leveraged strategy with regular rebalancing to a constant leverage ratio can result in surprisingly complex and not-easy-tounderstand risk and return properties. It is not the long-term wealth destroyer that it is $\textbf{sometimes labeled as, but it does generate a highly skewed distribution of longterm re- }$ turns that may indeed be unattractive to some investors unless they have sufficiently low risk aversion. Moreover, a strategy of rebalancing to a constant high leverage ratio can be a destroyer of wealth when the asset we are investing in has strongly mean-reverting returns.

6.3 $\textbf{Optionlike payoffs from dynamic rebalancing}$

We can get further insights into the risk-return profile of leveraged strategies by examining in more detail how long-term returns of leveraged strategies relate to the long-term returns on the underlying index. Figure 6.6 shows scatter plots of several leveraged strategies' simulated 3-year returns against the 3-year market index returns.

The blue circles show the 3-year returns of a strategy where we initially pick a leverage ratio of 3.0 and then refrain from rebalancing during the 3-year period (with 750 trading days). As one would expect, the long-term return of this strategy, $R_t:t+750$, is linear in the long-term return on the index, $R_m,t:t+750.$ More precisely,

$$\begin{aligned}R_{t:t+750}&=(1+R_f)^{750}(1-\omega)+\omega(1+R_{m,t:t+750})-1\\&=(1+R_f)^{750}+\omega\left[1+R_{m,t:t+750})-(1+R_f)^{750}\right]-1\end{aligned}$$

(6.7)

Note that when the index performs very poorly, the initial 3x leverage strategy can lose more than the entire amount of initial investment. With 3x initial leverage, a -33% loss on the index is sufficient to extinguish the entire wealth invested in the strategy. Losses bigger than this generate additional liabilities. This is an issue we will revisit shortly.

![](https://img.simpletex.net/pdf/BzBdZhAg/f0gHaDoGVt7upl4rWVyOc4znYYUSXNmr5.png)

Long-run index return

Figure $6.6{:\text{ Simulated 3-year returns of various leveraged strategies as function of 3-year}}$

index returns

In contrast, as the scatter plot of red circles shows, the constant-leverage strategy's loss is bounded by -100%. This is due to the frequent rebalancing. Every time the index declines and the leveraged strategy experiences a daily loss— which would lead to rising leverage in the absence of rebalancing—the strategy sells some index investment to reduce leverage back to the target leverage of $\omega=3.$ This quick de-risking following losses ensures that the strategy never experiences a loss big enough to wipe out all wealth invested in it.

To be more precise, the constant-leverage strategy would perfectly achieve this avoidance of losses in excess of -$100\%$ if it was possible to continuously rebalance at infinitesimally small time intervals and if the price process of the underlying index was a diffusion, which means that the price path is continuous even as we examine smaller and smaller time intervals (in other words, there are no discrete price jumps). This is obviously not exactly true in reality. And in the simulations we're looking at here, I simulated daily returns, not returns over infinitesimally small time intervals and rebalancing takes place only once per day, not continuously. Over these daily intervals, it is theoretically $\begin{aligned}\text{possible that a randomly drawn return could be sufficiently negative that it wipes out all}\\\text{possible that a randomly drawn return could be sufficiently ne}\end{aligned}$ wealth in the strategy, and possibly more—it is just so unlikely that it never happened in the 1,000 simulation runs of 750 trading days that I used to construct Figure 6.6.

in the index return.

A convex payoff of this sort should remind you of a fnancial instrument that you

encountered in your introductory investments course: A call option.

For example, let the index level at the start of the three-year period be $S_t$ and the index level at the end of the three-year period $S_T$ and consider options with the index as the underlying asset. A three-year at-the-money European call option with a strike or exercise price $K$ offers a payoff of $\max(0,S_T-K)$ at the end of the three-year period. Hence, this is a kinked, convex payoff.

What's the connection to our constant-leverage strategy? Recall that the payoff of a European call option can be replicated by a dynamically rebalanced leveraged position $\bar{\text{in the index financed by borrowing at the risk-free rate. The positions in this replicating}}$ can be obtained from the Black-Scholes formula. The Black-Scholes formula expresses the price of a European call option (on a non-dividend paying underlying asset) that gives the right, but not the obligation to obtain one share of the underlying asset as

$$C_t=\Delta_tS_t-B_t,$$

(6.8)

where $\Delta_t$, with $0<\Delta_t<1$, is the number of shares of the underlying asset in the replicating portfolio and $B_t$ is the amount borrowed at the risk-free rate. Hence, the right-hand side is the amount of wealth that must be invested in the replicating portfolio to exactly replicate the payoff of the call option. By absence of arbitrage then, the price of the call option must be equal to the cost of this replicating portfolio. The Black Scholes formula further provides expressions

$$\Delta_t=N(d_1),\quad d_1=\frac{\log S_t-\log K+\left(r_f+\frac{\sigma^2}2\right)(T-t)}{\sigma\sqrt{T-t}}$$

(6.9)

and

$$B_t=N(d_2)K\exp[-r_f(T-t)],\quad d_2=d_1-\sigma\sqrt{T-t}$$

(6.10)

where $N(.)$ denotes the normal cumulative distribution function that maps numbers

from $-\infty$ to $+\infty$ into -1 to +1.

Thus, the Black-Scholes model tells us that a call option is equivalent to a levered

position in the index. The leverage ratio of the replicating portfolio is

$$\text{Call leverage}=\frac{\text{Holding of underlying asset}}{\text{Total portfolio value}}=\frac{\Delta_tS_t}{\Delta_tS_t-B_t}$$

(6.11)

makes this leverage ratio smaller (close to one) for high $S_t$ and higher for lower $S_t.$ Nevertheless, there is a substantial similarity of the nature of rebalancing trades in the replicating portfolio and in the constant-leverage strategy.

Consider frst the call option replicating portfolio. From (6.9) one can see that $d_1$ is increasing in $S_t.$ Since $N(d_1)$ is monotonically increasing in $d_1$, this then makes $\Delta$ increasing in $S_t.$ Hence, when the index goes up, the option-replicating strategy calls for purchasing more shares in the index, financed by borrowing. The opposite happens when the index falls.

Now consider the constant-leverage strategy. As we already discussed earlier, when the index declines and the leveraged strategy experiences a daily loss, the strategy sells some index investment and repays debt to reduce leverage back to the target leverage of $\omega=3.$ The opposite happens when the index rises. Hence, directionally, the trading of involved in the constant-leverage strategy is similar to that in the call-option replicating strategy! There are some differences in how the amount of trading depends on the change in the index, but directionally, both strategies call for similar positive-feedback trading. In other words, the constant-leverage strategy is, implicitly, quite similar to a call-option replicating strategy.

To see this explicitly, the yellow circles in Figure 6.6 show the long-term returns from investing in the call option replicating portfolio of an at-the-money three-year European at-the-money (i.e., $K=S_t)$ call option on the index that I described above. To be precise, this is not the exact replicating portfolio. To get it exactly right, one would need to rebalance the replicating portfolio continuously, with infnitesimally small time windows between the rebalancing points. Here I do it once per day, which introduces a small amount of approximation error. Nevertheless, as Figure 6.6 shows, we are getting very close to the kinked payoff of a call option

This now gives us further insight into the risk-return properties of a constant-leverage strategy. Since the constant-leverage strategy is similar to the replicating position of a call-option payoff, its risk and return are similar to the risk and return of a call option. More precisely, an at-the-money call option has a

$\bullet$ highly positively skewed long-term return

$\bullet$ with most price paths ending with losses on the call option positior

$\bullet$ but with a small probability of huge gains

$\bullet$ which leads to an overall high expected return

6.4 $\textbf{Using options to implement leveraged strategies}$

Now that we have seen that a constant-leverage strategy is effectively synthesizing an option-like payoff, we can also turn this around and synthesize a leveraged strategy using options.

![](https://img.simpletex.net/pdf/BzBdZhAg/ffKmQaLoRcKGs4txLyRZkxnHXbDRy2I1D.png)

Long-run index return

Figure 6.7{:} Simulated 3-year returns of constant-leverage strategy and a strategy that

combines investment in index with options on the index

Figure 6.7 provides an example of how this can be done. It shows the 3-year returns from a strategy that invests in the index combined with buying and selling call options. To understand the construction of this strategy, it's easiest here to think of the index investment as purchase of one share of an index ETF. Let $S_0$ be the price of one ETF share at the start of the 3-year period. For simplicity, let's also assume that one option has one share of the ETF as underlying asset. The options are European. The combined position involves, at the start of the 3-year period

$\bullet$ purchase of one share of the index ETF

$\bullet$ sale of 2 call options with strike price $K=1.3\times S_0$ (hence these are out-of-the-

money (OTM) options) and 3-year maturity

The long position in ATM call options generates the convexity in the relationship between the combined position's returns and the index returns. The short position in the OTM call options cancels some of the convexity. Without this short position in OTM calls, the convexity would be too strong in the region of high index returns on the right-hand side of the plot.

For comparison, Figure 6.7 also shows the 3-year returns from the constant-leverage strategy. The returns are remarkably close. ($One could try to get even closer. I did$ not spend a lot of effort fine-tuning the size of the options position.) Like constantleverage strategy, the options strategy avoids losses more than -100%. This means that the returns of a constant-leverage strategy can be effectively synthesized by taking a combined index and options position.

An options implementation of the constant-leverage strategy has potential benefits. Direct implementation of the constant-leverage strategy requires regular trading, e.g., at daily frequency, throughout the 3-year period. In contrast, with the options strategy we can establish the index and options position once at the start of the 3-year period and then sit back and do nothing for three years. Using options we can therefore turn a dynamic strategy (direct implementation) into a static strategy (using options).

The static version may be especially attractive for investors who are not set up to trade a lot and at relatively high frequency. We can actually think of the options strategy as letting someone else do the dynamic trading who may be better equipped to do this trading efficiently. The likely counterparty of an options trade is an options market maker (e.g. Citadel Securities). For any options that they purchase or sell, option market makers typically try to hedge their position, either entering into offsetting options positions with other counterparties or by constructing a hedging portfolio using the options' underlying assets. For example, if you buy a call option, the market maker's hedging position would be a leveraged investment in the underlying asset that needs to be regularly rebalanced at high frequency. So in this sense, the market maker is doing the trading in the underlying asset for you. And doing this sort of dynamic trading at high-frequency is a core part of a market maker's business. Hence, it could make sense for many investors, even relatively sophisticated institutional investors to effectively “outsource” such trading to a market maker by entering into an options position.

Taking on leverage is risky. That's in a way the point, as the purpose of leverage is to take higher exposure to risky assets than would be possible without borrowing. But some risks are special and require special attention. Without leverage, an investor can at most lose all their wealth. And since -$100\%$ returns are extremely unlikely on most risky assets, such an event is extremely unlikely. In contrast, with leverage, it can be much more likely that an investor ends up losing their entire wealth.

Moreover, a leveraged investor may be forced to abandon a position pre-maturely. Even if the investor is in a trade that would pay off in the long-run when prices eventually move in the direction the investor hoped for, if prices move the wrong way in the interim, the investor may not be able to hold on to the position long enough to benefit from the eventual payoff.

For example, with a static strategy that fixes a leverage ratio initially at 2:1 and then refrains from trading, a $50\%$ loss on the portfolio is sufficient to wipe out the investors" wealth. Buying $2m of risky assets with $1m borrowed money and $1m equity capital means that a loss of $1m on the risky asset position is enough to wipe out the investor's entire equity.

Suppose the amount of margin debt outstanding is $D$ and assume there is a maintenance margin requirement of $25\%$ of the value of securities in the portfolio. Let $V$ the value of the risky asset position. The investors equity then is $E=V-D.$ The maintenance margin requirement demands

(6.12)

$$V-D\geq0.25\times V$$

which we can solve for

$$V\geq\frac43D$$

(6.13)

so if $V$ initially twice as high as $D$, a loss greater than $-33.3\%$ on the risky asset position triggers a margin call. If the investor is unable or unwilling to provide an equity infusion, their broker will liquidate the position.

With a strategy that rebalances to constant 2:1 leverage at high frequency, things look a bit different. In the idealized case of continuous rebalancing at infinitesimally small time intervals, the strategy would always maintain a 2:1 leverage ratio. This means that it would always maintain a ratio of equity to risky asset position of $50\%$, while the margin requirement calls for $25\%.$ So it would always stay comfortably above the margin requirement. Hence no margin calls and no equity infusion or liquidation.

| Risky asset position $\iota\left(S\right)$               | 2.0 | 1.9   | 1.8  |
| -------------------------------------------------------- | --- | ----- | ---- |
| $(D)$ $\textbf{Margin loan}$                             | 1.0 | 1.0   | 0.9  |
| $\mathbf{Equity}$ $(S-D)$                                | 1.0 | 0.9   | 0.9  |
| $\mathbf{Required}$ $(0.25\times S)$ $\textbf{l margin}$ | 0.5 | 0.475 | 0.45 |
| $\operatorname{Equitv/Required}$ margin                  | 2   | 1.89  | 2    |

In practice, investors can't rebalance continuously, but only at discrete time intervals (e.g., daily). But with high probability, this can still work out to avoid margin calls if the rebalancing frequency is high enough. Table 6.1 presents an example. The frst column shows the initially entered position. At that point, as shown in the last row, the investors’ equity is double the amount of required margin. The second column shows what happens if the initial risky asset position suffers a loss of -5% before the first rebalancing point. Before rebalancing, equity has now fallen by more (-10%) than the required margin falls (-5%), hence the buffer between the investors' equity and the required margin has shrunk. As shown in the last row, the ratio of equity to required margin fell from 2 to 1.89. The last column shows the situation after rebalancing. To get back to 2{:}1 leverage, the investor sells 0.1 worth of the risky asset and uses it to pay back part of the margin loan. Now the ratio of equity to required margin is back up to 2.

Of course, if the loss before the first rebalancing was -$50\%$ instead of -$5\%$, it would be too late to prevent a margin call. In this case, all equity would be wiped out and the broker would ask for an equity infusion or would liquidate the position. But if the volatility of the risky asset position's return is not too high, and if rebalancing is done at sufficiently high frequency, the probability of a margin call can be kept very small.

Real-world market imperfections can bring in some additional complications, however. One problem could arise when there is insufficient $market\textit{liquidity in the risky}$ asset market. Recall that rebalancing in the case of a loss, as in the example in Table 6.1 requires selling some of the risky asset position. In an illiquid market, this selling could further drive down the price of the risky assets, which then raised leverage and hence requires further selling, which could further drive down the price, and so on. In an extreme case, this could lead to a collapse in the risky asset prices and ruin of the leveraged investors trying to follow a constant-leverage strategy. Thus, a constant-leverage strategy will only work in practice if the risky assets trade in sufficiently liquid markets and if the leveraged investor is sufficiently small so that their rebalancing trades won't move prices much. We should also keep in mind that multiple investors may follow similar strategies and they will all try to rebalance in the same direction at the same time.

Another potential problem is a deterioration in $funding\textit{liquidity. Margin require- }$ ments can change. If an investor has only a small buffer left between equity in the account and the required margin, then if the broker demands an increase in margin, this can lead to a margin call. This can be extremely inconvenient because margin requirements tend to go up precisely in times when risky asset prices fall, which usually coincides with increases in risky asset volatility and sometimes also market illiquidity. This then exacerbate rebalancing needs in unpleasant circumstances.

These market imperfections are another reason why implementing a leveraged strategy via options can be beneficial. Implementation of a risky asset plus options strategy like in Figure 6.7 can be done without borrowing and without any rebalancing trading

# $\textbf{6. 6}$ $\textbf{HEDGING TAIL RISKS}$

As the previous discussion made clear, leveraged strategies can be exposed to the risk of total ruin when margin constraints are hit and the position gets liquidated (in the absence of a new equity infusion by the investor). The risk of large losses that can have such consequences are also known as $tail\textit{ risk because these are realizations far in the}$ (left) tail of the return distribution.

Obtaining leverage through call options instead of debt financing is one way to rule out such a ruinous outcome. A constant-leverage approach with regular rebalancing also can get close to ruling out ruin, if rebalancing is done often enough and volatility is sufficiently small that very large moves in the portfolio value between rebalancing points are extremely unlikely.

In contrast, a strategy that initially sets a certain level of leverage but then does not rebalance for a long period of time is exposed a large risk of ruin. But if we want to stick to not rebalancing for longer periods, and we want to lever up directly by borrowing, not with call options, then buying protection against extreme downside moves through out-of-the money (OTM) put options is an alternative to avoid the tail risk of such ruinous outcomes.

Recall that a European put option gives a right, but not the obligation, to sell the underlying asset at the strike price of the put option on the expiration date of the option. By purchasing the right amount of put options we can therefore put a floor under the value of our portfolio.

![](https://img.simpletex.net/pdf/BzBdZhAg/fpdQtacM1D3f4ADPFy5nG9Fq4zgUuGHhm.png)

Long-run index return

Figure 6.8: Simulated 3-year returns of strategies with initially fixed 3.1 leverage and

with or without put protection

Figure 6.8 shows a scatter plot of simulated 3-year returns of a strategy with initial 3x leverage and no rebalancing (blue circles) against the 3-year market index returns, as earlier in Figure 6.6. For this strategy, doing the same calculation as in (6.13), with a $25\%$ margin requirement, a decline of -11.1% in the risky asset position would be enough trigger a margin call.

This is quite a small tolerance for losses. Why is it so small? In our earlier calculation with 2:1 leverage, we could sustain a -$33.3\%$ decline in the risky asset value without a margin call and here with 3{:}1 leverage it is only -$11.1\%?$ The reason is that 3{:}1 leverage is already quite close to the maximum leverage of 4:1 that is possible with a margin constraint of $25\%.$ With 4:1 leverage, any loss, no matter how small, would trigger a margin call. Obviously, no investor in their right mind would try to take 4: 1 leverage if the margin requirement is $25\%.$

The figure also shows the returns of a strategy that combines the 3x initial leverage strategy with a position in put options. For each share of the index (think share of an index ETF), the protection strategy adds one put option with threeyear maturity and strike price $10\%$ below the index value at the time the position is established. Thus, this put option position establishes a floor on the portfolio value $10\%$ below the initial

1 he combined rısky asset

value. Then, taking into account the debt financing for the 3:1 leveraging, the maximum loss on the investors' equity is then is slightly bigger than 30%. (It's slightly bigger than rather than equal to $30\%$ because there is also the initial investment into the put that the investor must pay for. This lowers the returns.)

By limiting the losses on the combined position, the put protection ensures that a margin call will not be triggered at the end of the 3-year period. At the end of the 3-year period, the investors’ equity is guaranteed to be higher than $25\%$ of the risky asset position.

Example: Start with a risky asset position worth $V_0=3$ and debt $D=2$, plus $\begin{array}{l}\text{one put for each share of the risky asset. If initiating the puts position costs }P_0,\mathrm{~then}\\\text{initial equity is }E=V_0-D+P_0=1+P_0.\mathrm{~Then~the~combined~}\end{array}$ and puts suffers its maximum loss and is worth $0.9\times V_0.$ Then the remaining equity is $0.9\times V_0-D=0.7$ which is higher than the required margin of $0.9\times V_0\times0.25\approx0.67.$

This protection from losses of course does not come for free. We can see this in Figure 6.6 in that the when the index return isn't terrible, the put-protected strategy has lower returns than the strategy without put protection. This reflects the fact that the put options have a cost and unless the index suffers substantial losses, they expire worthless. The return an investor can expect to earn from the put-protected strategy will be lower than for the unprotected strategy. While the strategy with initially 3x leverage mechanically earns 3 times the excess return of the index, the addition of put protection (which is effectively a short position in the index of a size that varies over time) reduces these returns on average. Effectively, the puts provide insurance, and this insurance is not for free. Some expected return has to be given up for it.

Now back to the effectiveness of protection against margin calls. What about dates before the 3-year period is over and the options expire? What if there is a big loss before this end date? Is the investor also protected from losses that trigger a margin call in the interim until the 3-year period is over?

As it turns out, the answer is yes. The reason is that when the index is at level $S_T<K$ at maturity, the payoff of the put is $K-S_T.$ But when the index is at the same level $S_t=S_T$ some time before maturity, the value of the put option is typically $P_t>K-S_t.$ Therefore, the put option actually provides more protection prior to expiration than at expiration (for exceptions to this see the footnote). The reason is that at that point in time, there is still a chance that the index could fall a lot more in the future, triggering a large payout at expiration (the index could also rise, of course,

![](https://img.simpletex.net/pdf/BzBdZhAg/fx1yDFedXFITGCSP06ylCzw9V8dsTEzob.png)

Figure $6.9{:\text{ Simulated }1.5\text{-year return on the 3x initial leverage }+\text{OTM puts strategy}}$

as function of 1.5-year index returns

Figure 6.9 illustrates this. It shows the returns after 1.5 years (i.e., 1.5 years before the options expire) on the put-protected strategy as a function of the index return over the same period. As one can see, the losses on the put-protected strategy are limited to around -40% at the very extreme end of index declines on the left-hand side, slightly bigger losses than after 3 years in Figure 6.6 (the reason why the losses are slightly bigger is explained in the last footnote). In the more likely ranges of moderate declines of the index, the return on the put-protected strategy are higher than after 3 years in Figure 6.6. This is, as we discussed, a consequence that the put options after 1.5

$\overline{^3\text{For the European put options that }}$we are considering here, it can happen that $P_t<K-S_t$ in extreme situations where it is virtually certain that the option will end up in the money and will be exercised at maturity, e.g., if the current index level is so far below the strike price, that it's virtually impossible that the option expires out of the money. To see why, suppose $S_{t}$ is far below $K.$ As owner of a put option, you basically know for sure that a combined position of the index and the put will be worth $K$ $\begin{aligned}\text{after you exercise the option at maturity. The present value of this combined payoff is }\dot{Kexp}[-r_f(T-t)]],\end{aligned}$ so it must be true that $S_t+P_t=Kexp[-r_f(T-t)]]$, and hence $P_t=Kexp[-r_f(T-t)]]-S_t$, which is smaller than $K-S_t.$ But unless interest rates are very high, even in this extreme scenario here, $P_t$ can be just a very small amount below $K-S_t.$

to summarize, long-term put options are also effective at providing protection in the

$\operatorname{in\text{terim, before expiration}}.$

In practice, investors may face the problem, though, that long-term options are quite illiquid. The most heavily traded options are short-term with, say, one month to expiration. Purchasing large positions in long-term options may involve substantial transaction costs due to illiquidity.

This brings up the question whether one could also achieve similar long-term protection against large losses by rolling over a position in short-term put options, say ones with one month to expiration. Unfortunately, the protection they offer is not the same. Short-term puts offer effective protection against steep, sudden crashes. For example, suppose you purchase put options with a strike price $5\%$ below the current index value and you renew this position once a month when the previous options expire. If the index falls by $20\%$ in a single day, and stays low until the one-month option expires, the put option will make a large payout that provides the protection you were seeking. But if instead of a steep crash there is a long drawn-out decline in the index, with the index falling many months in a row, but never more than $5\%$, the put options always expire worthless even though you suffer a big accumulated loss. In this case, the short-term options fail to provide effective protection.

Protection can be improved if we combine short-term put options with regular rebalancing back to a target leverage ratio—not necessarily daily, as in our constant-leverage examples above, but perhaps once per month. Following a monthly loss on the risky asset position, rebalancing to a target leverage ratio would mean selling risky assets and de-risking the position. This helps prevent large losses going forward. And one-month put options then help protect against big losses between rebalancing time points.

An alternative to hedging tail risk with options is to look for assets that tend to perform well during times when tail risk materializes on the assets that we want to hedge. If we add such assets to the portfolio, it can provide some offsetting gains in times when other assets in the portfolio perform very poorly. Unlike with put options, this is not guaranteed. It's just likely, in a statistical sense, judging by historical experience.

Figure 6.10 presents some examples. The fırst block of rows at the top shows the performance of two U.S. and two international stock market indices in three episodes in the past 25 years when stock markets dropped by large percentages (burst of the technology bubble, fnancial crisis, COVID crisis). Many investors have large stock market exposures in their portfolio, so assets that do well when stock markets drop a lot would be potentially suitable tail-risk hedges.

|                              | Side  | Technology Bubble Aug 2000 Mar 2003 | Global Financial Crisis May 2008 Feb2009 | covid-19 Dec2019 Mar 2020 | Crisis Average | Historical Annual Return Jan 1995 Mar 2020 |
| ---------------------------- | ----- | ----------------------------------- | ---------------------------------------- | ------------------------- | -------------- | ------------------------------------------ |
| S&P500                       | Long  | -4696                               | $-47\%$                                  | $\%$                      | $-38\%$        | $6.8\%$                                    |
| Russell 2000                 | Long  | $-37\%$                             | $-48\%$                                  | $-31\%$                   | $-39\%$        | $4.3\%$                                    |
| MSCIEAFE                     | Long  | $-48\%$                             | $-53\%$                                  | $\cdot23\%$               | -4296          | $2.0\%$                                    |
| MSCI Emerging                | Long  | $-37\%$                             | $-58\%$                                  | $-24\%$                   | $-40\%$        | $5.8\%$                                    |
| US Mid-Term Treasury         | Long  | $15\%$                              | 6%                                       | 596                       | $99\%$         | $2.2\%$                                    |
| US Long-Term Treasu          | Long  | 2196                                | 1196                                     | 20%                       | 17%            | $5.7\%$                                    |
| USSYIGCDS                    | Short | 0%                                  | 596                                      | 496                       | 396            | -1.2%                                      |
| US 10Y IG CDS                | Short | 0%                                  | 6%                                       | 596                       | 496            | -1.2%                                      |
| US SY HY CDS                 | Short | 30%                                 | 28%                                      | 1196                      | 23%            | -3.196                                     |
| Emerging FX                  | Short |                                     | 18%                                      | 9%                        | 14%            | -2.6%                                      |
| AUDUSD                       | Short | -1096                               | 3196                                     | 1396                      | 1196           | $-1.2\%$                                   |
| JPYUSD                       | Long  | $-16\%$                             | 796                                      | 196                       | -396           | $-2.8\%$                                   |
| CHFEUR                       | Long  | 0%                                  | 8%                                       | 296                       | 396            | $0.6\%$                                    |
| Gold Futures                 | Long  | 1296                                | 496                                      | 496                       | 796            | 3.496                                      |
| Crude Oil Futures            | Short | -696                                | $76\%$                                   | 67%                       | $46\%$         | $6.6\%$                                    |
| Copper Futures               | Short | 2796                                | $57\%$                                   | $20\%$                    | $35\%$         | $-3.3\%$                                   |
| GSCI Commodity Index Futures | Short | 896                                 | 65%                                      | $43\%$                    | $38\%$         | $4.2\%$                                    |
| VIX Futures                  | Long  |                                     | 23296                                    | $209\%$                   | $221\%$        | -50.9%                                     |
| Tail Risk Hedge Funds        | Long  |                                     | 1296                                     | $56\%$                    | \34% $         | $ -3.4\%$                                  |
| Trend Following              | Long  | 51%                                 | 10%                                      | 296                       | 21%            | $3.2\%$                                    |

Figure 6.10 Payoff of Tail Risk Hedging Strategies during Severe Market Downturns

Source: CAIA Association, “"Tail Risk Hedging,”, August 25,2021.

The remaining rows show assets that are often considered as candidate tail-risk hedges: U. S Treasury bonds, buying credit protection via creditdefault swaps (CDS) (which pays out well if many companies default on their debts),various exchange rates, commodities, and a few assets in the bottom group that we will discus in more detail. To be a suitable tail-risk hedge, we would want to see that the asset reliably performs well when stocks do extremely poorly.

U.S. Treasury bonds seem to fit this requirement. They did well in all three crisis episodes. In the next lecture, we will look more closely at the relationship between stock and bond markets to understand why bond prices behave this way, and whether this good performance in crises is actually a reliable relationship over longer periods than the past 25 years considered here. For now, I'll just note that as a tail risk hedge we might want an asset that has a more skewed payoff, with payoffs that are very high in crisis, but otherwise not necessarily strongly negatively correlated with stock markets in “normal times.” Treasury bonds don't ft this requirement.

rates are a mixed bag. The Swiss Franc (CHF) is perhaps the most reliable “safe haven” currency that tends to appreciate in times of crises when investors seek safety, but the magnitudes of appreciation seem rather small, so not a great tail risk hedge.

Among commodities, gold is a popular among some investors as a tail risk hedge. For gold, too, the price rise during crisis episodes seems rather small. Not clear that it's a great tail risk hedge.

Finally, the last block of rows includes one product that we will shortly examine more closely: VIX futures. The returns of a VIX futures investment look consistent with tail risk insurance properties. VIX futures produced extremely high returns during the three crisis episodes (insurance pays out) and strongly negative average returns overall (insurance premium to be paid). Adding VIX futures to a portfolio can have somewhat similar effects as adding put protection. We will explore in more detail why this is so.

But first a few final remarks on tail risk hedging.

Our discussion focused on tail risk hedging for the purpose of avoiding margin calls in leveraged strategies. But tail risk hedging can be applied more broadly. For example, an unlevered investor may want to put a floor on how much their portfolio can decline in value. Put options, or other forms of tail risk hedging can be used to accomplish this.

But it's important to keep in mind that that the insurance against tail risk events does not come for free. In fact, it could be quite expensive. A substantial part of the equity risk premium earned by stocks over risk-free assets is likely a compensation for the risk of extreme declines of stock prices in times of economic crises. Insuring against these extreme declines may also remove much of the risk premium that the portfolio earns. This may be fne for a risk averse investor, or an investor who wants to take more risk via leverage, but must ensure that there is zero risk of margin calls. But it may be counterproductive for a relatively risk-tolerant investor who is investing to earn substantial risk premia.

There is also an organizational challenge of how to sustain a tail risk hedging program in the long-term if such a program is deemed useful. There seems to be a tendency of investors setting up tail risk hedging programs after an experiencing a severe crash. But then, as years pass by without a crisis event, and the tail risk hedging program only produces costs and no payouts, the program is abandoned (before, eventually, another crisis hits). $^4$ This is misguided. Whether the benefts of tail risk hedging justify the costs benefits

$\overline{^4\text{A recent example that may fall in th}}$ is category was the pension fund Calpers. Calpers unwound a tail risk hedging program just before the COVID crisis in early 2020. See “The Inside Story of CalPERS"
Untimely Tail-Hedge Unwind," Institutional investor, April 14,2020.

# $\mathbf{6. 7}$ $\textbf{VOLATILITY PRODUCTS}$

Let's examine in more detail now the VIX futures that showed up in Figure 6.10 with large returns during crisis episodes. The underlying “asset" of these futures is the VIX index of the Chicago Board Options Exchange (CBOE). In fact, the VIX index is not an asset that one can directly invest in. Instead, the VIX index represents a weighted average of the prices of put and call options on the S&P500 index with close to 30 days to expiration. This means that every day the VIX is really the value of a portfolio of different assets, because every day the calculation is based on options with different expiration dates. So the change of VIX from one day to the next is not a change in the price of an asset, or a collection of assets, because there is also partly a switch to different assets (options with different expiration dates) going on.

This weighted average of option prices in the VIX calculation is constructed such that the level of the VIX represents a generalized version of implied volatility that you encountered in the Black-Scholes model. Recall that implied volatility is the level of volatility that, when you stick it into the Black-Scholes model along with other parameters, yields the current market price of an option. If the assumptions of the Black-Scholes model were correct in reality (which would require, among other things, that volatility is constant over the life of the option and that stock index returns are log-normally distributed) then the level of VIX would be equal to implied volatility according to the Black-Scholes model. But in reality the Black-Scholes model assumptions don't hold and VIX provides an implied volatility measure that does not rely on the Black-Scholes model assumptions.

Under these more general assumptions the VIX calculation is based on, if investors were risk-neutral, the level of the VIX would provide the expected volatility of the S&P500 index over the next 30 days. On average, then, if we observe a level of $VIX_t$ on day $t$, the level of volatility that is realized subsequently over days $t+1$ to $t+30$ should be equal to $VIX_t.$ In reality, of course, investors are risk averse and it's possible that they view unexpected changes in volatility as a systematic risk that commands a risk premium. If so, the level of VIX may be expected volatility plus or minus a risk premium.

![](https://img.simpletex.net/pdf/BzBdZhAg/fDwMdASf4u1qG2D1vu6MMXZX0ygnXyIvr.png)

Figure $6.11{:\text{ VIX index and annualized realized volatility over following }30\text{ days}}$

Figure 6.11 shows the data on this. The blue line shows the time series of daily $\tilde{\text{observations on the VIX. Very clearly visible are the massive spikes in the VIX during}}$ the onset of the financial crisis in fall of 2008 and during the COVID crisis in early 2020. Consistent with the strong time-variation in the level of the VIX, the realized volatility (calculated from daily returns over 30-day windows, then annualized) shown by the red line also shows huge time-variation that is highly correlated with the VIX. Volatility is clearly not constant. And after burst of volatility such as in 2008 and 2020, it takes quite a while for volatility to revert back to the mean.

Interestingly, the VIX is almost always higher than the level of realized volatility during the subsequent days. This means that investors price a $volatility\textit{ risk premium}$ into the put and call options that comprise the VIX index. To understand the source of the risk premium, consider an investor who holds a long position in the weighted combination of these options that replicates the VIX. If in the next instant, after the investor established this position, option market participants' expectations of future volatility go up, the investor's position would gain. Therefore, the investor's position provides insurance against unexpected rises in volatility. Apparently, investors are willing to pay a premium for insurance against such a risk of rising volatility. A risk-neutral investor would only pay a price for options that would make the VIX equal to expected future volatility, but real-world risk averse investors are willing to pay a higher price for these

$11150011vc110$

U Say UIIat UIIIN

$UIIUY\perp ION$

1009 w00

wuuud

makes assets with returns that are positively correlated with unexpected changes in volatility (e.g., the options underlying VIX) command a higher price and to have lower future returns. (In contrast, based on this signing convention, the equity risk premium is $\textit{positive because it makes assets that are positively correlated with unexpected stock}$ market returns, e.g., positive-beta stocks, command a lower price and to have higher future returns.)

Now that we understand VIX, let's turn to VIX futures, whose tail-risk hedging properties were shown in Figure 6.10. VIX futures are like a forward contract on VIX. If we enter a long position in VIX futures on day $t$ at futures price $F_t$ and the futures expire on day $T>t$ (where $T$ could, for example, be in the middle of next month, or in one of the following months) and the level of the VIX index on the futures expiration date is $VIX_T$, then we get a payoff $VIX_T-F_T.$

| SYMBOL  | EXPIRATION | LAST                    | CHANGE | HIGH  | LOW   | SETTLEMENT | VOLUME |
| ------- | ---------- | ----------------------- | ------ | ----- | ----- | ---------- | ------ |
| $VIX$   |            | 22.20 -0.62 23.13 23.13 |        |       |       |            |        |
| VX35/Q2 | 08/31/2022 | 0                       |        | 0     | 0     | 23.675     | 0      |
| VX36/U2 | 09/07/2022 | 0                       |        | 0     | 0     | 24.325     | 0      |
| VX37/U2 | 09/14/2022 | 0                       |        | 0     | 0     | 24.325     | 0      |
| $VX/U2$ | 09/21/2022 | 23.85                   | -0.50  | 24.45 | 23.65 | 24.35      | 22,024 |
| VX39/U2 | 09/28/2022 | 0                       |        | 0     | 0     | 24.35      | 0      |
| VX40/V2 | 10/05/2022 | 0                       |        | 0     | 0     |            | 0      |
| $vXVV2$ | 10/19/2022 | 25.50                   | -0.467 | 26.02 | 25.37 | 25.967     | 11,576 |
| $vx/X2$ | 11/16/2022 | 26.32                   | -0.382 | 26.76 | 26.20 | 26.702     | 4,430  |
| $VX/Z2$ | 12/21/2022 | 26.57                   | -0.33  | 26.95 | 26.50 | 26.90      | 1,859  |
| $VX/F3$ | 01/18/2023 | 27.72                   | -0.31  | 28.05 | 27.65 | 28.03      | 913    |
| $VX/G3$ | 02/15/2023 | 27.82                   | -0.326 | 28.15 | 27.80 | 28.146     | 636    |
| VXIH3   | 03/22/2023 | 28.04                   | -0.31  | 28.32 | 28.00 | 28.35      | 469    |
| $vx/j3$ | 04/19/2023 | 28.12                   | -0.28  | 28.35 | 28.00 | 28.40      | 241    |
| VX/K3   | 05/17/2023 | 27.95                   | -0.325 | 28.10 | 27.95 | 28.275     | 34     |

Figure 6.12{:} CBOE VIX Futures Prices on August 25,2022

For example, consider the VIX futures prices from August 25,2022 shown in Figure 6.12. The price for futures expiring on October 10/19/2022 was \$ 25. 50. And so the payoff on October 19,2022 of a long position entered on August 22,2022 would be the level of the VIX on October 19 minus $\$25.50$ (x1000 since each futures contract is for a notional value of 1000 times the index). If there were no margin requirements, no money would change hands at all at the initiation of the contract on August 25. But position makes losses until the day of expiration

Hence, VIX futures are essentially a beton where the level of VIX will be on the futures expiration date. This has several implications.

First, the price of VIX futures is not necessarily closely tied to the current, or $spot$, value of the VIX index. In particular, the options underlying the current VIX may have already expired by the time the futures expire. The value of the futures depends on expectations about the value that the options that will be used in the calculation of the VIX on the futures' expiration date.

Second, there can be an additional risk premium in the sense that the futures price is not necessarily equal to the expected future VIX level. Empirical evidence indicates that futures prices are on average higher than the future level of VIX that will be realized on the expiration date.$^5$ This means that investors are willing to pay a premium for VIX futures relative to what risk-neutral investors would be willing to pay. This further means that VIX futures must have some insurance properties that are valuable to investors. This makes sense given what we have seen for the VIX. Just like the options underlying the VIX are expensive due to a negative volatility risk premium, futures on VIX are expensive due to a negative volatility risk premium. Both the VIX and VIX futures tend to rise in price strongly in times of crisis, hence they are valuable to investors as a hedge.

![](https://img.simpletex.net/pdf/BzBdZhAg/fGq67uKdHLaYyOkbdTXLwqctfl6SBKcyy.png)

Figure 6.13{:} VXX ETN

We can look at some exchange-traded products as an easy way to track the returns from a strategy that rolls over long positions in near-term VIX futures. Figure 6.13 shows the holdings of one popular product with the ticker VXX on August $22,2022.^6$

$^{5}$See Eraker, B. and Wu, Y., 2017. Explaining the negative returns to volatility claims: An equilib-

rium approach. Journal of Financial Economics, 125(1), pp.72-98.

$^6$To me more precise, holdings is not quite the correct description. VXX is an exchange traded note,

futures with exactly one month to expiration. This means we can use the return series of VXX to track the return on such a strategy of maintaining a VIX futures position with approximately one month to expiration.

Figure 6.14 shows a time series of the price of VXX. More precisely, it's the splitadjusted price of VXX. During the time period shown in this plot, VXX has undergone 1{:}4 reverse splits where 4 shares were converted into 1. Without adjusting for these splits, it would look like VXX maintained its value over the entire period, when in fact its value almost completely evaporated. To show in more detailed what happened in the later part of this period, Figure 6.15 focuses just on the 2014 to 2021 subperiod.

Looking at both figures, we see two key properties that are consistent with the notion that this product provides investors with insurance against tail events: The price rises strongly during crisis episodes when the stock market crashes like in March 2020 where the VXX price rose by several hundred percent (effectively, insurance pays out), but in absence of such crashes, the price falls, leading the holder to experience losses (effectively, the insurance premium that must be paid for the insurance).

Figure 6.16 shows these hedging properties in a scatterplot of daily VXX return against daily CRSP value-weighted stock index return. In addition to the scatterplot, the fgure also shows a curve that smoothes the scatter observations locally in order to visualize the underlying nonlinear relationship between the two variables. It shows that there is a particularly strong negative relationship between stock index returns and VXX returns in the domain of losses on the stock index.

Table 6.2{:} Annualized risk-return properties of a strategy that combines stock index

with VXX

<table>

<tbody>

<tr>

<th> </th>

<th>$100\%$ stocks</th>

<th>$90\%$ stocks$+10\%$ $5\textbf{VXX}$</th>

</tr>

<tr>

<td> Mean</td>

<td>15.59</td>

<td>8.90</td>

</tr>

<tr>

<td>Std. dev. </td>

<td>17.89</td>

<td>11.81</td>

</tr>

<tr>

<td> Sharpe Ratio</td>

<td>0.87</td>

<td>0.75</td>

</tr>

<tr>

<td>1st pctile</td>

<td>-3.28</td>

<td>-1.98</td>

</tr>

<tr>

<td>99th pctile</td>

<td>3.05</td>

<td>2.19</td>

</tr>

</tbody>

</table>

not an exchange traded fund. So an investor in this product does not own a share of a fund that holds these futures. Instead, the note represents a debt obligation of the issuer. The holdings shown in this table represent the position to which the issuer (Barclays) promises to tie the value of the notes. For a large investor, it is better to invest in VIX futures directly rather than to rely on the promises of a financial institution in honoring the debt obligations implied by this product. But for our purposes here, the product is an easy way to see the returns obtained from a futures position.

![](https://img.simpletex.net/pdf/BzBdZhAg/fEV7t29vk6SXExoyMzgZ1kshLYxGmAbgU.png)

Figure $6.14{:\text{ Split-adjusted VXX ETN price}}$

Adding VXX to a stock portfolio should therefore substantially reduce the downside risk of the portfolio. How would this have played out in the period that my VXX return data sample spans, February 2009 to December 2021? Table 6.2 shows the mean returns, standard deviations, and Sharpe ratio (all annualized) from a strategy that invests $100\%$ in the CRSP valueweighted stock index and one that rebalances every day to 90$\%$ in the stock index and $10\%$ in VXX. Not surprisingly, the combined strategy has substantially lower standard deviation of returns. The mean returns are lower, too, consistent with the fact that investing in VXX means paying an insurance premium. In fact, the mean returns are sufficiently low so that the Sharpe ratio of the combined strategy of 0.75 is somewhat lower than the Sharpe ratio of the stock index of 0.87. (Even so, a sufficiently risk averse investor might prefer the combined strategy).

The 1st percentiles of the daily return distribution (second-to-last row, in percent) $\hat{\text{show that the tail-risk hedging beneft is modest. The }1\text{st percentile of the mixed strategy}}$ is pulled toward zero a little more strongly than the 99th percentile on the upside. But $\bar{\text{it's not a huge difference. So if one is really interested in a targeted tail-risk hedge,}}$ directly going for the tailrisk hedge with outofthe money options rather than adding VXX (or VIX futures) to the portfolio may be a more reliable strategy.

Let me close our discussion with a warning. Earlier I pointed out that the price of

![](https://img.simpletex.net/pdf/BzBdZhAg/fHDF8LV0czDvow41BscX6sO1tLgl7C8Rt.png)

2015 2016 2017 2018 2019 2020 2021 2022

Figure $6.15{:\text{ Split-adjusted VXX ETN price since }2014}$

VIX futures depends on the investors' expectations of VIX at the futures' expiration in the future. Therefore, VIX futures prices will not move one-for-one with VIX. In some cases, although this will be very rare, it could even happen that VIX rises, e.g., before an event that involves lots of uncertainty, like an election, but at the same time expectations of VIX in the future falls. To see why, recall that the current VIX index will reflect expectations about volatility over the next 30 days, so if we approach an uncertainty event, the VIX will start capturing it once it's less than 30 days away. However, VIX futures capture expectations of future VIX, and as we get closer to the uncertainty event, VIX futures may no longer capture the uncertainty associated with this event because it is too near term. So as we approach the uncertainty event, VIX and VIX futures could even move in opposite direction.

Moreover, market imperfections can induce a disconnect between the prices of VIX futures and exchange-traded notes like VXX. If this happens, the price of VXX could move in ways that distorts its hedging properties. Two recent events have underscored these concerns.

The first is that Barclays, the issuer of VXX had made a regulatory paperwork blunder and had issued billions more in structured notes (including VXX) that it had permission for. For this reason, it stopped issuing VXX in March 2022. This is a problem

![](https://img.simpletex.net/pdf/BzBdZhAg/fZgR4O9pEIdCEgxgwQ2yIFfI4PGi4PYMz.png)

Stock index return 2018 to December 2021.
Figure 6.16: Scatterplot of daily VXX return against daily stock index return, January

for the pricing mechanism. Normally, if there is a lot of demand for VXX that pushes the price above the value it should have, based on the futures position that VXX is meant to track, Barclays would issue more shares of VXX to keep the price where it should be. Barclays’halt of issuance means that this mechanism was no longer operational and, as a consequence, the price of VXX was substantially elevated above its correct value (apparently due to uninformed investor demand). For example, on August 15,2022 it traded $33\%$ above its correct value.

Another problem with volatility-linked products occurred in February 2018 in an episode that came to be known as $`$Volmageddon'. This concerned not VXX, but inverse VIX products that are constructed to move inverse to VIX futures, e.g. with returns always -1x the VIX futures return. On February 5,2018 the VIX rose by $102\%$ in a single day, leading some inverse VIX products to fall by $97\%.$ To stay hedged, the issuers of these products had to purchase VIX futures following the strong upward movements in the VIX which may have further exacerbated the rise VIX futures and VIX. The next day, Credit Suisse, the issuer of one popular product with ticker XIV announced that they would trigger a provision in the contract of XIV that allowed them to redeem the notes for a fınal payment in the event that the price of XIV should fall more than $80\%$ in a day. This attracted criticism because of the possibility that the price impact of the that problems can arise when the futures markets underlying these products is not liquid enoughto absorb large rebalancing flows without price distortions.