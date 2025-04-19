---
tags:
  - '#equilibrium_swap_rate'
  - '#fixed_rate'
  - '#floating_rate'
  - '#interest_rate_swaps'
  - '#off_market_fra'
  - '#present_value'
  - '#settlement_dates'
  - '#swap_pricing'
  - '#swap_valuation'
  - '#vanilla_swap'
---
# 26.2 INTEREST RATE SWAPS

Interest rate swaps are a variation of FRAs, but they have some important distinctions. An interest rate swap is an agreement for one party to pay another a set of payments at one rate and the latter to pay the former a set of payments at another rate. Typically, one of these rates is fixed and one is variable and, thereby, floats according to a benchmark rate in the market. This standard type of swap is usually called a vanilla swap or sometimes plain vanilla swap. It is also possible to have both rates be floating, but the two rates would clearly have to be different floating rates.

Interest rate swaps are the most widely used derivative.5 The most common application is when a company has a floating-rate loan but would prefer a fixed-rate loan. Because lenders very commonly make floating-rate loans, but borrowers prefer fixed-rate loans, lenders will usually offer a swap to enable the borrower to convert the loan from floating to fixed. That is, with the loan the borrower will be making a series of interest payments to the lender at rates that adjust periodically according to a market benchmark rate. A swap can then be attached so that the borrower receives an interest payment that is floating and makes an interest payment that is fixed. The floating interest payment the borrower makes on the loan is offset by the floating interest payment it receives on the swap, leaving a net of a fixed interest payment.

# 26.2.1 Pricing Interest Rate Swaps

Let us set up the problem of pricing the swap. Our objective is to determine the fixed rate the swap buyer would agree to pay in return for receiving the floating rate. We shall assume. that the swap makes payments on the following dates, $j=1,2,\ldots,J$ Thus, at maturity, it has made the final and $\dot{J}^{t b}$ payment. The number of days to each payment is designated as $T_{j}.$ Thus, for example, a swap that makes payments in 180, 360, 540, and 720 days will have $J=4$ , and $j=1,2,3,4$ , with the number of days to each payment being $T_{1}=180$ $T_{2}=360$ $T_{3}=540$ , and $T_{4}=720$ . We refer to these dates as settlement dates, reset dates, or rate-reset dates.

We shall assume that the underlying is the rate $L_{t}(q)$ , meaning the rate on day $t$ for a $q$ -day loan. In the example here with four payments spaced 180 days apart,. $q=180$ This is the same type of underlying that we used to illustrate FRAs. One party agrees to. pay a fixed rate of $R S_{0}(J,q)$ , which means the fixed rate on a swap set at time O in which. there are $J$ payments and each payment is based on the $q$ -day rate. The standard terms of vanilla swaps call for the rate, $L_{j}(q)$ , to be set at the beginning of the settlement period, and the payment to be made at the end. This structure is different from the way FRAs are paid, but it is the way loan interest payments are made. With floating-rate loans, the rate is set at the beginning of the settlement period, the interest accrues through the period, and the interest is paid at the end of the period, at which time the rate is reset. The payoff. determined on day $j$ is, thus,6

$$
\left[L_{j}(q)-R S_{0}(J,q)\right]\left(\frac{q}{360}\right),
$$

and this amount is paid at date. $j+1$ , meaning $q$ days later. It should be apparent that the first floating rate on the first swap payment, $j=1$ , is known when the swap is initiated.. It is known as the stub rate or the current $q$ day rate, $L_{0}(q)$ . So, the first swap floating payment, which will be made at. $j=1$ , is known for certain. All remaining payments from. $j=2$ onward are unknown, because they will be determined by the $q$ -day rates on. $j=1$ $j=2,\dots,j=J-1$ Despite this uncertainty, we shall be able to value these payments, as we show here..

First, let us make a slight alteration to the swap payments that has no net economic effect but serves a useful purpose in facilitating valuation. Usually in an interest rate swap, the parties exchange only the interest rates based on the notional. The notionals themselves are not exchanged. For example, if party A agrees to pay party B the swap fixed rate, and party B agrees to pay party A the floating rate, with both based on the same 50 million notional, there is no exchange of 50 million between the parties, because this would serve no purpose. That is, there would be no reason for A to pay 50 million to B at the start. and for B to pay 50 million to A and for the two parties to again exchange 50 million at expiration. The parties simply exchange, that is, "swap" interest payments. But no harm will be done if, for valuation purposes, we simply add a notional to both the fixed. and floating sides. To keep things simple, we shall set this notional at 1.0. This amount will theoretically be exchanged at the start and at the end, which is why it is called the. notional, meaning to exist only in theory, not in reality. Thus, the last fixed payment will be $\left(1+R S_{0}(J,q)q/360\right)$ , and the last floating payment will be $\left(1+L_{J-1}(q)q/360\right)$ . We shall also refer to this notional as hypothetical.7

Let us now find the present value at time O of the floating payments. First, let us start with the last floating payment, at time. $J_{:}$ which as we said is $\left(1+L_{J-1}(q)q/360\right).$ Let us find its present value back to time $J-1$ . So, we are at time. $J-1$ and we are looking ahead. to time $J$ .What is the present value at. $J-1$ of the payment of $\left(1+L_{J-1}(q)q/360\right)$ that will occur at $J{\boldsymbol{?}}$ This is a simple calculation:.

$$
{\frac{1+L_{J-1}(q)\left({\frac{q}{360}}\right)}{1+L_{J-1}(q)\left({\frac{q}{360}}\right)}}=1.
$$

In other words, discounting the upcoming payment at the rate of that payment gives a present value of 1, provided the principal is added. In what follows, we shall need to remember that 1 is the present value of the remaining payment plus the hypothetical notional.8

So, now we step back to $J-2$ and value the next payment of $L_{J-2}(q)(q/360)$ plus the value of the remaining payments plus hypothetical notional beyond $J-2$ , which is 1. This valuation will equal

$$
{\frac{1+L_{J-2}(q)\left({\frac{q}{360}}\right)}{1+L_{J-2}(q)\left({\frac{q}{360}}\right)}}=1.
$$

It should now be apparent that we can continue to step back recursively to time 0, and we. shall always obtain a value of 1 at each of the settlement dates. Hence, the present value at time O of the floating payments, plus the hypothetical notional of 1 at expiration, equals 1.

By adding the hypothetical notional at expiration, we have effectively treated the series. of floating payments like a floating-rate loan whereby the principal is repaid. We see that its value is 1 at any settlement date. This result is not a magical result. It is consistent with the purpose of a floating rate loan: the reduction of interest rate risk to the lender. Remember that when a lender makes a fixed-rate loan, it assumes interest rate risk. If rates go up, the fixed rate loan is worth less. If rates go down, the fixed rate loan is worth more.. A floating-rate loan reduces this uncertainty by having the floating rate periodically reset to the current market rate. Of course, rates can adjust only periodically and not continuously, so the value of the floating-rate loan will deviate slightly from its par value, which we set here at 1. But on each settlement date, the loan rate catches up with the market rate, and the loan value returns to its par value. What we have done here is to take the floating side of the swap and make it behave like a floating-rate loan. We have also taken the fixed side of the swap and made it behave like a fixed-rate loan.

Similar to FRAs, the swap involves no net payment at the start, so it has zero value when initiated,

$$
V S_{0}(J,q)=0.
$$

Thus, we should set the present value of the floating payments, plus hypothetical notional,.
to the present value of the fixed payments, plus hypothetical notional, equal to each other.
The present value of the floating payments plus hypothetical notional is, as we just showed,.

equal to 1. Thus, we set the present value of the fixed payments, plus the hypothetical notional of 1, equal to 1,

$$
\sum_{j=1}^{J}\left[\frac{R S_{0}(J,q)\left(\frac{q}{360}\right)}{1+L_{0}\left(t_{j}\right)\left(\frac{t_{j}}{360}\right)}\right]+\frac{1}{1+L_{0}\left(t_{J}\right)\left(\frac{t_{J}}{360}\right)}=1.
$$

Solving for the fixed rate, $R S_{0}(J,q)$ gives

$$
R S_{0}\left(J,q\right)=\left\{\frac{1-\frac{1}{1+L_{0}\left(t_{J}\right)\left(\frac{t_{J}}{360}\right)}}{\displaystyle\sum_{j=1}^{J}\left[\frac{1}{1+L_{0}\left(t_{j}\right)\left(\frac{t_{j}}{360}\right)}\right]}\right\}\frac{360}{q}.
$$

This rather complex looking equation is actually quite simple. Inside the large parentheses is a numerator and a denominator. The numerator is simply one minus the. present value of 1.0 paid at the last payment date. The denominator is the sum of the present values of 1.0 at each payment date. In other words, the denominator is. simply the present value of a 1.0 annuity. The ratio of numerator to denominator is then annualized by the factor $360/q$ . The result is the fixed rate on the swap that equates the. present value of the fixed payments to the present value of the floating payments at the. start. Hence, it is the arbitrage-free fixed rate on the swap..

To facilitate finding the present value of something, as we have seen before we sometimes use the term structure of spot rates to calculate the price of a zero-coupon bond and multiply that price by the item we are discounting. Suppose the spot rates for all maturities are all $3\%$ . The example given in Table 26.1 illustrates this process in calculating a swap rate.

With a $3\%$ spot rate, the 1.0 par zero-coupon bond price can be found based on

$$
{\frac{1}{1+L_{0}\left(t_{j}\right)\left({\frac{t_{j}}{360}}\right)}}.
$$

TABLE 26.1 Spot Rates, Zero-Coupon Bond Prices, and Equilibrium Swap Rate


<html><body><table><tr><td>Days</td><td>Spot Rate (%)</td><td>Zero-Coupon Bond Price</td></tr><tr><td>90</td><td>3.0</td><td>0.992556</td></tr><tr><td>180</td><td>3.0</td><td>0.985222</td></tr><tr><td>270</td><td>3.0</td><td>0.977995</td></tr><tr><td>360</td><td>3.0</td><td>0.970874</td></tr><tr><td></td><td>Sum</td><td>3.926646</td></tr><tr><td></td><td>Quarterly Swap Rate</td><td>0.741758%</td></tr><tr><td></td><td>AnnualSwapRate</td><td>2.967032%</td></tr></table></body></html>

For example, 1.0 received on day 180 is worth

$$
{\frac{1}{1+L_{0}\left(t_{j}\right)\left({\frac{t_{j}}{360}}\right)}}={\frac{1}{1+0.03\left({\frac{180}{360}}\right)}}=0.985222.
$$

The quarterly swap rate is

$$
\left({\frac{1-0.970844}{0.992556+0.985222+0.977995+0.970874}}\right)=0.00741758,
$$

and the annualized swap rate, based on Equation (26.8), is simply

$$
\begin{array}{c}{{R S_{0}(360,90)=\left(\frac{1-0.970844}{0.992556+0.985222+0.977995+0.970874}\right)\frac{360}{90}}}\ {{=(0.00741758)4=0.02967.}}\end{array}
$$

An alternative approach to pricing an interest rate swap is based on a portfolio of off-market FRAs. With this approach, we evaluate each periodic cash flow related to the swap. The risk related to each floating cash flow is offset with an off-market FRA. Recall each cash flow determined at time $j-1$ and paid $q$ days later based on 1.0 notional for a receive-floating swap is expressed as

$$
\left[L_{j-1}(q)-R S_{0}(J,q)\right]\left(\frac{q}{360}\right).
$$

By entering a receive-fixed FRA, the combined cash flow occurring at $t_{j-1}+q$ can be expressed as

$$
\begin{array}{l}{{\displaystyle\left[L_{j-1}(q)-R S_{0}(J,q)\right]\left(\frac{q}{360}\right)+\left[R_{0}\left(t_{j-1},q\right)-L_{j-1}(q)\right]\left(\frac{q}{360}\right)}}\ {{\displaystyle\quad=\left[R_{0}\left(t_{j-1},q\right)-R S_{0}(J,q)\right]\left(\frac{q}{360}\right).}}\end{array}
$$

We seek the fixed swap rate such that the current swap value is zero or

$$
\sum_{j=1}^{J}\left\{\frac{\left[R_{0}\left(t_{j-1},q\right)-R S_{0}\left(J,q\right)\right]\left(\frac{q}{360}\right)}{1+L_{0}\left(t_{j-1}+q\right)\left(\frac{t_{j-1}+q}{360}\right)}\right\}=0.
$$

Solving for the equilibrium fixed swap rate, we have

$$
R S_{0}\left(J,q\right)=\sum_{j=1}^{J}w_{j}R_{0}\left(t_{j-1},q\right),
$$

where

$$
w_{j}=\frac{D F_{j}}{\displaystyle\sum_{j=1}^{J}D F_{j}}=\frac{\displaystyle\frac{1}{1+L_{0}\Big(t_{j-1}+q\Big)\Big(\frac{t_{j-1}+q}{360}\Big)}}{\displaystyle\sum_{j=1}^{J}\left[\frac{1}{1+L_{0}\Big(t_{j-1}+q\Big)\Big(\frac{t_{j-1}+q}{360}\Big)}\right]}.
$$

Note that the inverse of the accrual period,. $q/360$ , simply converts the periodic swap rate to an annual rate. For example, if. $q=90$ , then the summation part of Equation (26.11) is. the quarterly swap rate. Thus, we see that the fixed rate of an interest rate swap is simply a weighted average of discount factors, where each discount factor is expressed as

$$
D F_{j}=\frac{1}{1+L_{0}\left(t_{j-1}+q\right)\left(\frac{t_{j-1}+q}{360}\right)}.
$$

Again, as before, suppose the spot rates for all maturities are all. $3\%$ . Table 26.2 illustrates both methods for finding the equilibrium swap rate, which again turns out to be about $2.967\%$

The forward rates are based on Equation (26.3). For example, the 270-day forward rate is

$$
\begin{array}{r l}&{R_{0}\left(m_{3},q\right)=\left[\frac{1+L_{0}\left(t_{3}+q\right)\left(\frac{t_{3}+q}{360}\right)}{1+L_{0}\left(t_{3}\right)\left(\frac{t_{3}}{360}\right)}-1\right]\frac{360}{q}}\ &{\qquad=\left[\frac{1+0.03\left(\frac{270}{360}\right)}{1+0.03\left(\frac{180}{360}\right)}-1\right]\frac{360}{90}=0.029557.}\end{array}
$$

TABLE 26.2 Two Approaches to Solving for the Equilibrium Swap Rate


<html><body><table><tr><td>Days</td><td>Spot Rate (%)</td><td>Zero-Coupon Bond Price</td><td>Forward Rate (%)</td><td>Weight (%)</td></tr><tr><td>90</td><td>3.0</td><td>0.992556</td><td>3.0000</td><td>25.2774</td></tr><tr><td>180</td><td>3.0</td><td>0.985222</td><td>2.9777</td><td>25.0907</td></tr><tr><td>270</td><td>3.0</td><td>0.977995</td><td>2.9557</td><td>24.9066</td></tr><tr><td>360</td><td>3.0</td><td>0.970874</td><td>2.9340</td><td>24.7253</td></tr><tr><td></td><td>Sum</td><td>3.926646</td><td></td><td></td></tr><tr><td></td><td>QuarterlySwapRate</td><td>0.741758%</td><td></td><td></td></tr><tr><td></td><td>Annual Swap Rate</td><td>2.967032%</td><td></td><td>2.967032</td></tr></table></body></html>

Each discount factor is simply the zero-coupon bond price (DF) divided by the sum of several zero-coupon bond prices. For example, the 270-day discount factor is

$$
\begin{array}{l}{{w_{3}={\displaystyle\frac{D F_{3}}{4}}={\displaystyle\frac{\frac{1}{1+L_{0}\left(t_{2}+90\right)\left(\frac{t_{2}+90}{360}\right)}}{\displaystyle\sum_{j=1}^{4}D F_{j}\quad\sum_{j=1}^{4}\left[\frac{1}{1+L_{0}\left(t_{2}+90\right)\left(\frac{t_{2}+90}{360}\right)}\right]}}}\ {{\displaystyle={\displaystyle\frac{0.977995}{3.926646}}=0.249066.}}\end{array}
$$

Note that for flat spot rates, the weights are declining. Further, the weighting scheme is present value weights so near-maturity forward rates receive greater weights.

# 26.2.2 Valuing Interest Rate Swaps

Now we wish to determine the value of an interest rate swap at some arbitrary point in its life, denoted t. We will assume that we are between payment dates. At this point we know the next upcoming floating payment because it was set at the last payment date. Let us denote the upcoming floating payment that was set at the last date, $L_{k}(q)$ . From the results obtained in the previous section, we know that at the next settlement date the present value of the remaining floating payments plus the hypothetical notional is 1. Thus, we can value the receive-floating swap as

$$
\begin{array}{r l}&{V S_{t}(J,q)=\left[\frac{1+L_{k}(q)\left(\frac{q}{360}\right)}{1+L_{t}\left(t_{k+1}-t\right)\left(\frac{t_{k+1}-t}{360}\right)}\right]}\ &{\qquad-\left\{\sum_{j=k+1}^{J}\left[\frac{R S_{0}(q)\left(\frac{q}{360}\right)}{1+L_{t}\left(t_{j}-t\right)\left(\frac{t_{k+1}-t}{360}\right)}\right]+\frac{1}{1+L_{t}\left(t_{J}-t\right)\left(\frac{t_{J}-t}{360}\right)}\right\}.}\end{array}
$$

Note that the receive-fixed swap value is simply the negation of Equation (26.15). The first term on the right-hand side (in brackets. $[]$ ) is the current value of a floating rate bond and. the second term (in curly brackets. $\{\}$ ) is the current value of the fixed-rate bond, where the. fixed rate is based on the previously established fixed swap rate..

Let us take a closer look at each of these terms. The first term on the right-hand side is the present value of the floating payments plus hypothetical 1.0 notional discounted. back from time $k+1$ to time $t.$ that is, over $t_{k+1}-t$ days at the rate that is applicable at time $t$ for $t_{k+1}-t$ days. The second term is the present value of the fixed payments where. the discounting is from each of the upcoming payment dates at the appropriate rate for. day $t_{j}$ to day $t$ for $j=k+1$ to $J$ plus hypothetical 1.0 notional discounted from the last payment date.

Recall from Table 26.2 that the fixed swap rate was. $2.967032\%$ for a quarterly reset one-year swap. Now suppose 90 days have past and interest rates have fallen significantly. We assume the first swap payment has just been made. Table 26.3 reports the interim calcu-. lations involved in computing the current swap value. Note that all but the last row involve.

TABLE 26.3 Illustrating the Swap Value for an Existing Swap


<html><body><table><tr><td>Days</td><td>Spot Rate (%)</td><td>Zero-Coupon Bond Price</td><td>Forward Rate (%)</td><td>Weight (%)</td></tr><tr><td>90</td><td>2.0</td><td>0.995025</td><td>2.0000</td><td>33.4986</td></tr><tr><td>180</td><td>2.0</td><td>0.990099</td><td>1.9900</td><td>33.3328</td></tr><tr><td>270</td><td>2.0</td><td>0.985222</td><td>1.9802</td><td>33.1686</td></tr><tr><td></td><td>Sum</td><td>2.970346</td><td></td><td></td></tr><tr><td></td><td>Quarterly Swap Rate</td><td>0.497529%</td><td></td><td></td></tr><tr><td></td><td>Annual SwapRate</td><td>1.990115%</td><td></td><td>1.990115</td></tr><tr><td></td><td>Current SwapValue per 1.0 Notional</td><td>-0.00725445</td><td></td><td></td></tr></table></body></html>

similar calculations as previously covered. We assume a receive floating swap. Because we are at a reset date, the present value of the floating payments equals 1.0. Substituting into Equation (26.15), we have

$$
\begin{array}{c}{{V S_{t}(J,q)=\left[\frac{1+L_{k}(q)\left(\frac{q}{360}\right)}{1+L_{t}(q)\left(\frac{t_{k+1}-t}{360}\right)}\right]-\left\{\sum_{j=k+1}^{J}\left[\frac{R S_{0}(J,q)\left(\frac{q}{360}\right)}{1+L_{t}\left(t_{j}-t\right)\left(\frac{t_{j}-t}{360}\right)}\right]+\frac{1}{1+L_{t}\left(t_{J}-t\right)\left(\frac{t_{J}-t}{360}\right)}\right.}}\ {{=\left[\frac{1+0.02\left(\frac{90}{360}\right)}{1+0.02\left(\frac{90}{360}\right)}\right]-\left\{\sum_{j=1+1}^{4}\left[\frac{0.002967392\left(\frac{90}{360}\right)}{1+0.02\left(\frac{t_{j}-t}{360}\right)}\right]+\frac{1}{1+0.02\left(\frac{270}{360}\right)}\right\}}}\ {{=-0.00725445.}}\end{array}
$$

Note also in Table 26.3 that we provide the new swap rate based on the new term structure. This rate, $1.990115\%$ , would be the rate on a new swap with three payments spaced 90 days apart. As it turns out, we can also value the swap by assuming that we offset the old swap with this new swap. The floating rates cancel, leaving the swap value equal to the present value of the difference in the new fixed rate and the old fixed rate:

$$
(0.01990115-0.02967032)\left({\frac{90}{360}}\right)(2.970347)=-0.00725445.
$$

The use of a new hypothetical offsetting contract is how we valued FRAs, so this approach is broadly applicable.

In this problem we positioned ourselves an instant after the first swap payment, but we could have positioned ourselves completely between swap payment dates. The procedure would be the same.

Before leaving interest rate swaps, we dive into some important technical details related to understanding swaps as they are actually used in practice..

# 26.2.3 Technical Details Related to Actual Interest Rate Swaps

In this section, we deal with some technical aspects related to managing swaps, such as day counting and accrual periods. We elaborate further on viewing swaps as a portfolio of off-market FRAs. For example, consider a swap with payments in 90, 180, 270, and 360 days. Assume the swap is on-market, that is, it has zero value and no exchange of cash at the start, the fixed rate on this swap will come from Equation (26.8).

Now let us show how we value the swap as a series of off-market FRAs. Assume settlement dates of 90, 180, 270, and 360 days. Create an FRA expiring at each date. If. each FRA is a standard FRA, it will have a different fixed rate, but the swap will have the same fixed rate. If, however, we force an FRA to have the swap fixed rate as its fixed rate, the FRA will be off-market. That is not a problem, however, and is one reason we covered off-market FRAs. Some of these FRAs will have positive values, and some will. have negative values, but the values must add up to zero at the start. If they did not, it. would be possible to execute a swap, hedge it with a series of FRAs, and earn an arbitrage. profit.

We now examine this approach with specific notation to incorporate important practi-. cal factors. We assume 1.0 notional and the same accrual period for both legs of the swap.. Each accrual period, however, can be different. For example, one accrual period may be for 90 days and another accrual period is for 92 days. Assuming a 360-day year, these two accrual periods are 90/360 and 92/360. Because the forward rate is the current market rate to lock in funds for some future period, the value of the receive-floating swap can be expressed as

$$
V S_{0}(J,q)=\sum_{j=1}^{J}D F_{F l t,j}A P_{F l t,j}r_{F R,j-1}-r_{F i x}\sum_{j=1}^{J}D F_{F i x,j}A P_{F i x,j},
$$

where $D F_{F l t,j}~(D F_{F i x,j})$ denotes the appropriate discount factor for the. $j^{t h}$ floating (fixed) rate, $A P_{F l t,j}(A P_{F i x,j})$ denotes the appropriate accrual period for the. $j^{t b}$ floating (fixed) rate, and $r_{F R,j-1}$ denotes the equilibrium forward rate, which is equivalent to the fixed FRA rate.. We use $j-1$ to remind us that the forward rate is set in advance of the period and paid at. the end. Solving for the fixed rate that renders Equation (26.16) equal to zero is

$$
r_{F i x}=\sum_{j=1}^{J}\frac{D F_{F l t,j}A P_{F l t,j}}{\displaystyle\sum_{j=1}^{J}D F_{F i x,j}A P_{F i x,j}}r_{F R,j-1}=\sum_{j=1}^{J}w_{j}r_{F R,j-1},
$$

where

$$
w_{j}=\frac{D F_{F l t,j}A P_{F l t,j}}{\displaystyle\sum_{j=1}^{J}D F_{F i x,j}A P_{F i x,j}}.
$$

Note if the accrual periods are the same, then appropriate weights can be computed solely. with discount factors, as we have seen before. Further, notice that the numerator is based on floating payments and the denominator is based on fixed payments. Often, swap structures. have different frequencies for both legs, resulting in these weights not summing to one.. For example, the plain vanilla swap so widely used has semiannual fixed payments based on a 30/360-day year, whereas the floating payments are often quarterly based on an. actual/360 -day year.

Table 26.4 illustrates three different sets of spot rates: flat, upward, and downward.. Note that the pattern of these spot rates can be influenced by a number of factors, including expectations of future interest rates and additional premium for perceptions of riskiness. As before, we assume the same accrual periods, we observe downward sloping forward rates resulting in the equilibrium swap rate being below the $2.5\%$ spot rate by just a few basis points. In Panel B, the upward sloping spot curve results in a steeper upward sloping forward curve. As expected, the fixed swap rate of $3.9175\%$ is much higher than the average spot rate of $2.5\%$ . Panel C illustrates the downward sloping spot curve with opposite results where the fixed swap rate is $1.0025\%$ , even though the average spot rate is again $2.5\%$

All three panels demonstrate that a weighted average of forward rates yields exactly the same annual fixed rate as the solution based on zero-coupon bond prices or discount factors.

TABLE 26.4 Illustration of Equilibrium Swap Rate


<html><body><table><tr><td colspan="5">Panel A. Flat Spot Rate Curve</td></tr><tr><td>Days</td><td>Spot Rate (%)</td><td>Zero-Coupon Bond Price</td><td>Forward Rate (%)</td><td>Weight ( %)</td></tr><tr><td>90</td><td>2.5</td><td>0.993789</td><td>2.5000</td><td>25.2317</td></tr><tr><td>180</td><td>2.5</td><td>0.987654</td><td>2.4845</td><td>25.0760</td></tr><tr><td>270</td><td>2.5</td><td>0.981595</td><td>2.4691</td><td>24.9221</td></tr><tr><td>360</td><td>2.5</td><td>0.975610</td><td>2.4540</td><td>24.7702</td></tr><tr><td></td><td>Sum</td><td>3.938648 0.619254%</td><td></td><td></td></tr><tr><td colspan="5">Quarterly Swap Rate Annual Swap Rate</td></tr><tr><td>Panel B. Upward Sloping Spot Rate Curve</td><td></td><td>2.477017%</td><td></td><td>2.477017</td></tr><tr><td colspan="5"></td></tr><tr><td>Days</td><td>Spot Rate (%)</td><td>Zero-Coupon Bond Price</td><td>Forward Rate (%)</td><td>Weight (%)</td></tr><tr><td>90</td><td>1.0</td><td>0.997506</td><td>1.0000</td><td>25.4003</td></tr><tr><td>180</td><td>2.0</td><td>0.990099</td><td>2.9925</td><td>25.2117</td></tr><tr><td>270 360</td><td>3.0</td><td>0.977995</td><td>4.9505</td><td>24.9035</td></tr><tr><td></td><td>4.0</td><td>0.961538</td><td>6.8460</td><td>24.4845</td></tr><tr><td></td><td>Sum</td><td>3.927139 0.979378%</td><td></td><td></td></tr><tr><td colspan="5">Quarterly Swap Rate Annual Swap Rate</td></tr><tr><td>Panel C. Downward Sloping Spot Rate Curve</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="5">Days Spot Rate (%)</td></tr><tr><td></td><td></td><td>Zero-Coupon Bond Price</td><td>Forward Rate (%)</td><td>Weight (%)</td></tr><tr><td>90 180</td><td>4.0</td><td>0.990099 0.985222</td><td>4.0000 1.9802</td><td>25.0617</td></tr><tr><td>270</td><td>3.0</td><td>0.985222</td><td>0.0000</td><td>24.9383 24.9383</td></tr><tr><td>360</td><td>2.0</td><td>0.990099</td><td>-1.9704</td><td></td></tr><tr><td></td><td>1.0 Sum</td><td>3.950641</td><td></td><td>25.0617</td></tr><tr><td colspan="2">Quarterly Swap Rate</td><td>0.250617%</td><td></td><td></td></tr><tr><td colspan="2">Annual Swap Rate</td><td>1.002469%</td><td></td><td>1.002469</td></tr><tr><td colspan="2"></td><td></td><td></td><td></td></tr></table></body></html>
