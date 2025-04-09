# 26.1 INTEREST RATE FORWARDS

As noted, we referred to interest rate forwards as forward rate agreements, or FRAs. They are forward contracts that pay off based on what the interest rate is on the expiration date of the contract. To understand them, we shall need to add some additional specifications. There are two forms of FRAs: advanced set, settled in arrears, and advanced set, advanced settled. Advanced set, settled in arrears, assumes that the FRA cash settlement is made at the end of the embedded interest rate period ( $q$ in Figure 26.1), whereas advanced set, advanced settled, assumes that the FRA cash settlement is made at the beginning of the embedded interest rate period. When first learning the mechanics of FRAs, it is easier to focus on advanced set, settled in arrears. For credit risk reasons, FRAs are typically advanced set, advanced settled. Recall FRAs are unlike loans so there is no repayment of principal. Thus, once the floating rate is set, the settlement amount can be computed. For example, an advanced set, settled in arrears, that mimics a typical loan may require settlement in three months of say 2,000,o00 (e.g., receive floating FRA and rates rose). The counterparty due the 2,000,o00 would prefer to receive the present value of the settlement amount now so as not to incur the risk that the counterparty owing the money defaults in three months (e.g., due to a credit crisis).

Let us assume that the forward contract expires in m days. On day m, the payoff of the forward contract will be based on the $q$ -day interest rate. Figure 26.1 illustrates our notation. Rather than maturity time being measured in years, with FRAs, it is typically measured in days. Note here $T$ is simply $m+q$ In the next section, we will value FRAs at some future time $t$ (prior to expiration). For example, suppose the underlying is a 90-day loan rate. Then $q=90$ . If the forward contract expires in 30 days, then $m=30$ . We shall need notation for the rate on a 90-day loan on day 30 relative to the initiation date of the contract, day 0. This would be $L_{30}(90)$ In general, we shall write this rate as $L_{m}(q)$ , the $q$ -day rate on day $^m$ . Thus, $T=m+q=$ $30+90=120$ In addition, the figure shows a date $t_{z}$ referred to as an evaluation date. We will later value the FRA at that point in time. For now, we focus on the initiation date, 0.

![](images/c2045b9684801cc97a00f8c1fbd99b2326fe6fb2b433aad9cba63ac529a0b2e9.jpg)
FIGURE 26.1 Interest Rate FRA Maturity Time Notation

We assume that on day 0, an FRA maturing on day m is created. We assume that the rate that the parties agree will be paid by the long to the short on day $^m$ is $R_{0}(m,q)$ This rate can be thought of as the forward price, in much the same manner that we think of a forward price in a standard forward contract on an asset, as described in Chapter 22.

On day m, the payoff to the long is the value of the contract at expiration, and is given as follows:

$$
V F R A_{m}(m,q)=\frac{\left[L_{m}(q)-R_{0}(m,q)\right]\left(\frac{q}{360}\right)}{1+L_{m}(q)\left(\frac{q}{360}\right)},
$$

where we will use the term $V F R A_{m}(m,q)$ as the value of an FRA expiring on day m where the underlying is a. $q$ -day loan rate. This amount is paid from the short to the long and represents the payment per 1.0 notional.2 First, note the numerator, which is partly composed of the difference between the rate realized on day $^m$ $L_{m}(q)$ , and the rate the long agreed to pay, $R_{0}(m,q)$ . This payment can be positive, in which case the short pays the long, or negative, in which case the long pays the short. These rates, however, are quoted as annual rates so they must be adjusted to reflect the fact that they apply to a $q$ -day transaction in. precisely the same manner that the rate on the loan is adjusted for the number of days, as in Equation (26.1). That is, we multiply by $q/360$

Now, take a look at the denominator. It might be surprising that there even is a denominator. Notice that the denominator results in discounting the payoff over $q$ days. And yet, the payment occurs on day m. Why do we do this discounting? The answer lies in the fact that the rate on which the payment is made, $L_{m}(q)$ , is the $q$ -day interest rate on day m as. determined in the money market. It is the rate that a bank would expect to pay or receive if it made a loan on day m and the loan were paid back on day $m+q$ . Because the FRA pays off on day $^m$ , the buyer is receiving the money before it technically should. Hence, it is appropriate to discount it. Note that if the FRA buyer were to hold on to the money and accrue interest at the rate $L_{m}(q)$ for $q$ days, they would have the amount. $L_{m}(q)$ . Thus, it does not really matter if the FRA pays off on day $^m$ or day $m+q$ . If it paid off on day. $m+q$ , it would pay $L_{m}(q)$ . By paying off on day $^m$ , it pays $L_{m}(q)/\bigl(1+L_{m}(q)\bigr).$ These are effectively the same amounts of money.

Finally, let us again note that in Equation (26.2), the payoff amount can be positive or negative. So, if $R_{0}(m,q)>(<)L_{m}(q)$ , the payoff will be negative (positive), and the buyer. (seller) must pay the seller (buyer)..

So, we know how the payoff of an FRA is determined. In keeping with our previous. coverage of forward contracts, there are two things we need to derive: the forward price, which is the rate $R_{0}(m,q)$ that is established at the start, and the value of the FRA..

# 26.1.1Pricing FRAs

In order to determine the fixed rate, or price, there is an important concept in valuation that we must know. First, let us establish the notation for valuation. Let $V F R A_{t}(m,q)$ be the value at time $t$ of an FRA that expires at time m in which the underlying is a $q$ day rate. It should not be surprising that when $t=0$ , the date of initiation of the contract, the value is zero. This result is consistent with the fact that no money changes hands when the contract is initiated. What we want to know is how to set the price of the contract at time 0. In this context, price is the fixed rate we agree to pay in exchange for receiving the floating rate. Let us first establish that the payoff at $^m$ , as given in Equation (26.2), is. equivalent to the following value at $m+q$

$$
\left[L_{m}(q)-R_{0}(m,q)\right]\left(\frac{q}{360}\right),
$$

as we simply compounded the payoff at $^m$ to the point $m+q$ at the rate $L_{m}(q)$ .3 Thus, the value of an FRA is the present value of this expression. Now, let us do one simple trick that will facilitate our derivation: We add and subtract a 1 in the above equation:

$$
\left[1+L_{m}(q)\left(\frac{q}{360}\right)\right]-\left[1+R_{0}(m,q)\left(\frac{q}{360}\right)\right].
$$

That is, we add 1 to the floating payment and fixed payments and thus they offset. We can easily find the value of the fixed component,. $1+R_{0}(m,q)(q/360)$ , by discounting it to the present at the $m+q$ -day rate.

$$
\frac{1+R_{0}(m,q)\left(\frac{q}{360}\right)}{1+L_{0}(m+q)\left(\frac{m+q}{360}\right)}.
$$

Now we wish to value the floating component, $1+L_{m}(q)(q/360)$ . Remember that this value is positioned at time $m+q$ and we want to discount it back to time m. So we discount for $q$ days at the rate $L_{m}(q)$ . Its value at time $^m$ is easily found as

$$
\frac{1+L_{m}(q)\left(\frac{q}{360}\right)}{1+L_{m}(q)\left(\frac{q}{360}\right)}=1.
$$

So the discounted value back to time $^m$ is 1. Therefore, the discounted value back to time 0 is

$$
{\frac{1}{1+L_{0}(m)\left({\frac{m}{360}}\right)}}.
$$

So now discounting the fixed and floating payments as indicated previously, the value of the FRA at time 0 is

$$
V F R A_{0}(m,q)=\frac{1}{1+L_{0}(m)\left(\frac{m}{360}\right)}-\frac{1+R_{0}(m,q)\left(\frac{q}{360}\right)}{1+L_{0}(m+q)\left(\frac{m+q}{360}\right)}.
$$

Because the FRA must have a value of zero at time 0, we set this equation to zero,

$$
V F R A_{0}(m,q)=\frac{1}{1+L_{0}(m)\left(\frac{m}{360}\right)}-\frac{1+R_{0}(m,q)\left(\frac{q}{360}\right)}{1+L_{0}(m+q)\left(\frac{m+q}{360}\right)}=0.
$$

Solving for the fixed rate gives us our desired result,

$$
R_{0}(m,q)=\left[\frac{1+L_{0}(m+q)\left(\frac{m+q}{360}\right)}{1+L_{0}(m)\left(\frac{m}{360}\right)}-1\right]\frac{360}{q}.
$$

This result is simply the forward rate for a $q$ -day transaction to start at time m. It is the rate that the long agrees to pay the short on day $^m$ in return for receiving the floating rate This rate guarantees that neither party can earn an arbitrage profit against the other.

For example, suppose the 270-day loan rate is $3\%$ and the 360-day loan rate is $4\%$ Calculate the fixed rate on an FRA expiring in 270 days for a 90-day deposit. In this case, the FRA fixed rate is found by solving

$$
\begin{array}{c}{{R_{0}(m,q)=\left[\displaystyle\frac{1+L_{0}(m+q)\left(\frac{m+q}{360}\right)}{1+L_{0}(m)\left(\frac{m}{360}\right)}-1\right]\displaystyle\frac{360}{q}}}\ {{=\left[\displaystyle\frac{1+0.04\left(\frac{360}{360}\right)}{1+0.03\left(\frac{270}{360}\right)}-1\right]\displaystyle\frac{360}{90}=\left(\displaystyle\frac{1+0.04}{1+0.0225}-1\right)4=0.06846.}}\end{array}
$$

Thus, the fixed rate is $6.846\%$

There is a useful approximation when estimating forward rates that market participants find helpful, especially when making decisions in chaotic markets. Suppose you view the longer rate as simply a weighted arithmetic average of the shorter rate with weights based on time to maturity. In this case, we have. $3\%$ for three 90-day periods and. $4\%$ for four 90-day periods. Thus, to achieve a. $4\%$ average the missing fourth number would be. 7 or $3+3+3+\_=4(4)$ Note that $7\%$ is higher than the correct answer of $6.846\%$ Thus, the arithmetic average is a useful starting point although slightly high. With today's computer technologies, this approximation is not as useful..

# 26.1.2 Valuing FRAs

From Equation (26.2) we know the value of the contract at expiration, and from. Equation (26.3) we know the fixed loan rate so the value of the contract at initiation is. zero. What we need to know is the value of the contract during its life. So, let us position. ourselves at an arbitrary point, time. $t$ , which is between time O and time m. In order. to value the contract, we need to create a transaction that essentially sells the contract. In other words, we need to create an offsetting contract. Keep in mind that we do not actually have to execute this new contract. We just need to be able to execute it and to know at what price it would be executed.4.

So here at time $t_{:}$ we look into the market and determine that a new forward contract. on the $q$ -day day rate expiring at m has a rate of $R_{t}(m,q)$ . If we held a long position in the original contract, we would need to go short this contract. The payoffs of the two contracts would yield an overall payoff at time $^m$ of

$$
\left[\frac{L_{m}(q)-R_{0}(m,q)\left(\frac{q}{360}\right)}{1+L_{m}(q)\left(\frac{q}{360}\right)}\right]-\left[\frac{L_{m}(q)-R_{t}(m,q)\left(\frac{q}{360}\right)}{1+L_{m}(q)\left(\frac{q}{360}\right)}\right].
$$

The first large bracketed term is the payoff from the contract we are long, the one we actually own. The second large bracketed term is the payoff from the contract we hypothetically sell. Let us rearrange this equation as follows:.

$$
\frac{\left[R_{t}(m,q)-R_{0}(m,q)\right]\left(\frac{q}{360}\right)}{1+L_{m}(q)\left(\frac{q}{360}\right)}.
$$

And this is the guaranteed payoff at time $T$ discounted to time m. Note that the rate at time $^m$ $L_{m}(q)$ , is not in the numerator. We have resolved that uncertainty by hypo-. thetically selling the new contract. Hence, the uncertainty is gone. We can thus value the FRA by discounting this amount from day m back to day $t.$ What we see in this equation is that the amount is discounted according to the standard payoff formula for an FRA, Equation (26.2). Recall how the denominator discounts the payoff that occurs at time $^m$ but is based on a rate in which the interest is paid at time $m+q$ . As we did previously, we can simply compound that payoff forward to date $m+q$ by multiplying by $1+L_{m}(q)(q/360)$ to remove the denominator from the equation. We now simply discount this amount from time $m+q$ to the present, time $t$ by the rate at time $t$ for the period $m+q-t$ as follows:

$$
V F R A_{t}(m,q)=\frac{\left[R_{t}(m,q)-R_{0}(m,q)\right]\left(\frac{q}{360}\right)}{1+L_{t}(m+q-t)\left(\frac{m+q-t}{360}\right)},
$$

where

$$
R_{t}(m,q)=\left[\frac{1+L_{0}(m+q-t)\left(\frac{m+q-t}{360}\right)}{1+L_{0}(m-t)\left(\frac{m-t}{360}\right)}-1\right]\frac{360}{q}.
$$

And this is the value of the FRA at time $t$ In other words, the contract we created at time. zero that obligates us to pay. $R_{0}(m,q)$ at time $^m$ is worth the above at time t. Based on the results of the previous example, suppose after 90 days, the 180-day loan rate is. $2\%$ and the 270 day rate is $3\%$ . Calculate the value of the receive-floating FRA entered at time 0.. Assume 1,00o,o00 notional. We first compute the new equilibrium FRA fixed rate as

$$
\begin{array}{c}{{R_{90}(270,90)=\left[\frac{1+L_{0}(m+q-t)\left(\frac{m+q-t}{360}\right)}{1+L_{0}(m-t)\left(\frac{m-t}{360}\right)}-1\right]\frac{360}{q}}}\ {{=\left[\frac{1+0.03\left(\frac{270}{360}\right)}{1+0.02\left(\frac{180}{360}\right)}-1\right]\frac{360}{90}=0.049505.}}\end{array}
$$

Now we compute the current value from the receive-floating counterparty (paying initial fixed rate and receiving the later fixed rate) as

$$
V F R A_{90}(270,90)=51,000,00000000000000.040.03\left(\frac{0.049505-0.06846)\left(\frac{90}{360}\right)}{1+0.03\left(\frac{270}{360}\right)}=-54,634.400550.
$$

In this case, the fixed FRA rate fell from. $6.846\%$ to $4.9505\%$ . In this particular case, the.
receive-floating counterparty is now in the hole 4,634.40.

# 26.1.3 Off-Market FRAs

As we discussed with forward contracts in general in Chapter 22, it is possible to create an FRA that is not set at a zero value at the start. If the fixed rate is set according to Equation (26.3), then the contract has zero value at the start and neither party pays. anything to the other. If we set the fixed rate higher than that given in Equation (26.3), the buyer has agreed to pay an above-market fixed rate. Thus, the contract would have a negative value at the start, and the seller would have to pay the buyer the market value at the start. If we set the fixed rate lower than Equation (26.3), the buyer has agreed to pay a below-market fixed rate. Thus, the contract would have a positive value at the start, and the buyer would have to pay the seller the market value at the start. These versions of FRAs are called off-market FRAs, and although they are not common, they are implicitly embedded in interest rate swaps, as we shall see..
