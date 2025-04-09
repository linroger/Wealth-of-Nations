# 4.5 ENGINEERING INTEREST-RATE SWAPS  

We now study the financial engineering of swaps. We focus on plain vanilla interest-rate swaps. Engineering of other swaps is similar in many ways and is left to the reader. For simplicity, we deal with a case of only three settlement dates. Figure 4.8 shows a fixed-payer, three-period  

(a) An interest rate swap (with annual settlements)..  

![](d0dfd89f9744f51d713eb50ad76144d199dbe0d272bbda10f3f9b1cbc4bf5cb7.jpg)  

(b) Add and subtract $N=1.00$ at the start and end dates...  

![](d4e6de4da70cc211a245c402c60af4525260fd3b44409bfdf0623713ebda8006.jpg)  

(c) Then detach the two cash flows...  

![](62989eb0d2fa12cdd2287624aa1a1073f71cc0a60cb8f0e926317b053eaf8ce9.jpg)  

# FIGURE 4.8  

Decomposition of an interest-rate swap.  

interest-rate swap, with start date $t_{0}$ . The swap is initiated at date $t_{0}$ . The party will make three fixed payments and receive three floating payments at dates $t_{1}$ $t_{2}$ , and $t_{3}$ in the same currency. The dates $t_{1},t_{2}$ , and $t_{3}$ are the settlement dates. The $t_{0},t_{1}$ , and $t_{2}$ are also the reset dates, dates on which the relevant LIBOR rate is determined.  

We select the notional amount $N$ as unity and let $\delta=1$ , assuming that the floating rate is 12-month LIBOR:15  

$$
N=\$1
$$  

Under these simplified conditions, the fixed payments equal $s_{t_{0}}$ , and the LIBOR-linked payments equal $L_{t_{0}}$ $L_{t_{1}}$ , and $L_{t_{2}}$ , respectively. The swap spread will be the difference between $s_{t_{0}}$ and the treasury rate on the bond with the same maturity, denoted by $y_{t_{0}}$ o Thus, we have  

$$
\mathrm{Swapspread}=s_{t_{0}}-y_{t_{0}}
$$  

We will study the engineering of this interest-rate swap. More precisely, we will discuss the. way we can replicate this swap. More than the exact synthetic, what is of interest is the way(s) one can approach this problem.  

A swap can be reverse-engineered in at least two ways:  

1. We can first decompose the swap horizontally, into two streams of cash flows, one representing. a floating stream of payments (receipts), the other a fixed stream. If this is done, then each stream can be interpreted as being linked to a certain type of bond..  

2. Second, we can decompose the swap vertically, slicing it into $n$ cash exchanges during $n$ time periods. If this is done, then each cash exchange can be interpreted similarly (but not identically) to an FRA paid-in-arrears, with the property that the fixed rate is constant across various settlement dates.  

We now study each method in detail.  

# 4.5.1 A HORIZONTAL DECOMPOSITION  

First we simplify the notation and the parameters used in this section. To concentrate on the engineering aspects only, we prefer to eliminate some variables from the discussion. For example, we assume that the swap will make payments every year so that the day-count parameter is $\delta=1$ unless assumed otherwise. Next, we discuss a forward swap that is signed at time $t_{0}$ but starts at time $t_{1}$ with $t_{0}<t_{1}$ . During this discussion, we may occasionally omit the use of the term "forward" and refer to the forward swap simply as a swap.17.  

The traditional way to decompose an interest-rate swap is to do this horizontally. The original swap cash flows are shown in Figure 4.8a. Before we start, we need to use a trick. We add and subtract the same notional amount $N$ at the start, and end dates, for both sequences of cash flows. Since these involve identical currencies and identical amounts, they cancel out and we recover the standard exchanges of floating versus fixed-rate payments. With the addition and subtraction of the initial principals, the swap will look as shown in Figure 4.8b.  

Next, "detach' the cash flows in Figure 4.8b horizontally, so as to obtain two separate cash. flows as shown in Figure 4.8c and d. Note that each sequence of cash flows is already in the form of a meaningful financial contract.  

In fact, Figure 4.8c can immediately be recognized as representing a long forward position in an FRN that pays LIBOR flat. At time $t_{1}$ , the initial amount $N$ is paid and $L_{t_{1}}$ is set. At $t_{2}$ , the first interest payment is received, and this will continue until time $t_{4}$ where the last interest is received along with the principal.  

Figure 4.8d can be recognized as a short forward position on a par coupon bond that pays a coupon equal to $s_{t_{0}}$ . We (short) sell the bond to receive $N_{-}$ . At every payment date, the fixed coupon is paid and then, at $t_{4}$ , we pay the last coupon and the principal $N$  

Thus, the immediate decomposition suggests the following synthetic:  

Here the bond in question needs to have the same credit risk as in a flat LIBOR-based loan. Using this representation, it is straightforward to write the contractual equation:.  

![](28199b306d5a548c86b80d7a0f709ede246296524d8b1f8897657c8201d92d00.jpg)  

Using this relationship, one can follow the methodology introduced earlier and immediately generate some interesting synthetics.  

# 4.5.1.1 A synthetic coupon bond  

Suppose a AAA-rated entity with negligible default risk issues only 3-year FRNs that pay. LIBOR-10 bp every 12 months.18 A client would like to buy a coupon bond from this entity, but. it turns out that no such bonds are issued. We can help our client by synthetically creating the. bond. To do this, we manipulate the contractual equation so that we have a long coupon bond on the right-hand side:  

![](f68492febfda6676d6cd8f190b1eb9ffeb2bbd8309bb7bd62d88ce183e791149.jpg)  

The geometry of this engineering is shown in Figure 4.9. The synthetic results in a coupon bond issued by the same entity and paying a coupon of $s_{t_{0}}-10$ bp. The $10\mathrm{bp}$ included in the coupon accounts for the fact that the security is issued by a AAA-rated entity.  

# 4.5.1.2 Pricing  

The contractual equation obtained in Eq. (4.35) permits pricing the swap off the debt markets, using observed prices of fixed and floating coupon bonds.19 To see this, we write the present value of the. cash streams generated by the fixed and floating rate bonds using appropriate discount factors.. Throughout this section, we will work with a special case of a 3-year spot swap that makes fixed  

![](d0cf824db0d39e69d4ca325543a6b2f795b532d948120bad0f18c0321f82a665.jpg)  

# FIGURE 4.9  

Creation of a synthetic bond.  

payments against 12-month LIBOR. This simplifies the discussion. It is also straightforward to generalize the ensuing formulas to an $n$ year swap.  

Suppose the swap makes three annual coupon payments, each equaling $s_{t_{0}}N$ . We also have three. floating rate payments, each with the value $L_{t_{i-1}}N$ , where the relevant LIBOR $L_{t_{i-1}}$ is set at $t_{i}-1$ but is paid at $t_{i}$  

# 4.5.1.3 Valuing fixed cash flows  

To obtain the present value of the fixed cash flows, we discount them by the relevant floating rates. Note that, $i f$ we knew the floating rates $\{L_{t_{0}},L_{t_{1}},L_{t_{2}}\}$ , we could write  

$$
\mathrm{PV-fixed}=\frac{s_{t_{0}}N}{(1+L_{t_{0}})}+\frac{s_{t_{0}}N}{(1+L_{t_{0}})(1+L_{t_{1}})}+\frac{s_{t_{0}}N+N}{(1+L_{t_{0}})(1+L_{t_{1}})(1+L_{t_{2}})}
$$  

where we added $N$ to date $t_{3}$ cash flows. But at. $t=0$ , the LIBOR rates $L_{t_{i}},i=1,2$ , are unknown. Yet, we know that against each $L_{t_{i}}$ $i=1,2$ , the market is willing to pay the known forward, (FRA) rate, $\boldsymbol{F}(t_{0},t_{i})$ . Thus, using the FRA rates as $i f$ they are the time $t_{0}$ market values of the. unknown LIBOR rates, we get  

$$
+\frac{s_{t_{0}}N+N}{(1+F(t_{0},t_{0}))(1+F(t_{0},t_{1}))(1+F(t_{0},t_{2}))}
$$  

All the right-hand side quantities are known, and the present value can be calculated exactly, given the Sto.  

# 4.5.1.4 Valuing floating cash flows  

For the floating rate cash flows, we have2  

Here, to get a numerical answer, we don't even need to use the forward rates. This present value can be written in a much simpler fashion, once we realize the following transformation:.  

$$
\begin{array}{c}{{\displaystyle\frac{L_{t_{2}}N+N}{(1+L_{t_{0}})(1+L_{t_{1}})(1+L_{t_{2}})}=\frac{(1+L_{t_{2}})N}{(1+L_{t_{0}})(1+L_{t_{1}})(1+L_{t_{2}})}}}\ {{=\displaystyle\frac{N}{(1+L_{t_{0}})(1+L_{t_{1}})}}}\end{array}
$$  

Then, add this to the second term on the right-hand side of the present value in Eq. (4.33) and use the same simplification,  

$$
\frac{L_{t_{1}}N}{(1+L_{t_{0}})(1+L_{t_{1}})}+\frac{N}{(1+L_{t_{0}})(1+L_{t_{1}})}=\frac{N}{(1+L_{t_{0}})}
$$  

Finally, apply the same trick to the first term on the right-hand side of Eq. (4.33) and obtain, somewhat surprisingly, the expression  

$$
\mathrm{PV~of~floating~payments~as~of~}t_{0}=N
$$  

According to this, the present value of an FRN equals the par value. $N$ at every settlement date. Such recursive simplifications can be applied to present values of floating rate payments at reset dates.1 We can now combine these by letting  

PV of fixed payments as of $t_{0}=\mathrm{PV}$ of floating payments as of $t_{0}$  

This gives an equation where $s_{t_{0}}$ can be considered as an unknown:  

$$
\begin{array}{r l}&{\frac{s_{t_{0}}N}{(1+F(t_{0},t_{0}))}+\frac{s_{t_{0}}N}{(1+F(t_{0},t_{0}))(1+F(t_{0},t_{1}))}}\ &{+\frac{s_{t_{0}}N+N}{(1+F(t_{0},t_{0}))(1+F(t_{0},t_{1}))(1+F(t_{0},t_{2}))}=N}\end{array}
$$  

Canceling the $N$ and rearranging, we can obtain the numerical value of $s_{t_{0}}$ given $F(t_{0},t_{0}),F(t_{0},t_{1}),$ and $F(t_{0},t_{2})$ . This would value the swap off the FRA markets.  

# 4.5.1.5 An important remark  

Note a very convenient, but very delicate operation that was used in the preceding derivation. Using the liquid FRA markets, we "replaced' the unknown $L_{t_{i}}$ by the known $\boldsymbol{F}(t_{0},t_{i})$ in the appropriate formulas. Yet, these formulas were nonlinear in. $L_{t_{i}}$ and even if the forward rate is an unbi-. ased forecast of the appropriate LIBOR,  

$$
F(t_{0},t_{i})=E_{t_{0}}^{P*}[L_{t_{i}}]
$$  

under some appropriate probability $P^{*}$ , it is not clear whether the substitution is justifiable. For example, it is known that the conditional expectation operator at time $t_{0}$ , represented by $E_{t_{0}}^{P*}[.].$ cannot be moved inside a nonlinear formula due to Jensen's inequality:  

$$
E_{t_{0}}^{P*}\left[\frac{1}{1+L_{t_{i}}\delta}\right]>\frac{1}{1+E_{t_{0}}^{P*}[L_{t_{i}}]\delta}
$$  

So, it is not clear how $L_{t_{i}}$ can be replaced by the corresponding $\boldsymbol{F}(t_{0},t_{i})$ , even when the relation in Eq. (4.48) is true. These questions will have to be discussed after the introduction of risk-neutral and forward measures in Chapters 12 and 13. Such "substitutions" are delicate and depend on many conditions. In our case, we are allowed to make the substitution, because the forward rate is what the market "pays" for the corresponding LIBOR rates at time $t_{0}$  

# 4.5.2 A VERTICAL DECOMPOSITION  

We now study the second way of decomposing the swap. We already know what FRA contracts are. Consider an annual FRA where the $\delta=1$ . Also, let the FRA be paid-in-arrear. Then, at some time $t_{i}+\delta$ , the FRA parties will exchange the cash flow:  

$$
(L_{t_{i}}-F(t_{0},t_{i}))\delta N
$$  

where $N$ is the notional amount,. $\delta=1$ , and the $\boldsymbol{F}(t_{0},t_{i})$ is the FRA rate determined at time. $t_{0}$ We also know that the FRA amounts to exchanging the fixed payment $F(t_{0},t_{i})\delta N$ against the floating payment $L_{t_{i}}\delta N$  

Is it possible to decompose a swap into $n$ FRAs, each with an FRA rate $\boldsymbol{F}(t_{0},t_{i})$ $i=1,...,n?$ The situation is shown in Figure 4.10 for the case $n=3$ . The swap cash flows are split by slicing the swap vertically at each payment date. Figure 4.10b-d represents each swap cash flow separately. A fixed payment is made against an unknown floating LIBOR rate, in each case.  

Are the cash exchanges shown in Figure 4.10-d tradeable contracts? In particular, are they. valid FRA contracts, so that the swap becomes a portfolio of three FRAs? At first glance, the cash  

![](69b25f0cf4257c70c1b81d8f8bc57b2445dd7e67c97eb06255588e7c526f5180.jpg)  

# FIGURE 4.10  

Decompose a swap into FRAs.  

flows indeed look like FRAs. But when we analyze this claim more closely, we see that these cash flows are not valid contracts individually..  

To understand this, consider the time. $t_{2}$ settlement in Figure 4.10b together with the FRA cash. flows for the same settlement date, as shown in Figure 4.11. This figure displays an important phenomenon concerning cash flow analysis. Consider the FRA cash flows initiated at time $t_{0}$ and settled in arrears at time. $t_{2}$ and compare these with the corresponding swap settlement. The two.  

![](a42ffe617f90b97c2dac447297521a27f18964d6266076198723b71da75f59f4.jpg)  

# FIGURE 4.11  

Settlement differences between FRAs and swaps.  

cash flows look similar. A fixed rate is exchanged in the same fashion against LIBOR rate $L_{t_{1}}$ observed at time $t_{1}$ . But there is still an important difference..  

First of all, note that the FRA rate $F(t_{0},t_{i})$ is determined by supply and demand or by pricing through money markets. Thus, in general  

$$
F(t_{0},t_{i})\neq s_{t_{0}}
$$  

This means that if we buy the cash flow in Figure 4.11a and sell the cash flow in Figure 4.11b,. LIBOR-based cash flows will cancel out, but the fixed payments won't. As a result, the portfolio will have a known negative or positive net cash flow at time $t_{2}$ , as shown in Figure 4.11c. Since this cash flow is known exactly, the present value of this portfolio cannot be zero. But the present value of the FRA cash flow is zero, since (newly initiated) FRA contracts do not have any initial cash payments. All these imply that the time $t_{2}$ cash flow shown in Figure 4.11c will have a known present value,  

$$
B(t_{0},t_{2})[F(t_{0},t_{1})-s_{t_{0}}]\delta N
$$  

where the $B(t_{0},t_{2})$ is the time $t_{0}$ value of the default-free zero coupon bond that matures at time $t_{2}$ with par value USD 1. This present value will be positive or negative depending on whether $F(t_{0},t_{1})<s_{t_{0}}$ Or not.  

Hence, slicing the swap contract vertically into separate FRA-like cash exchanges does not result in tradeable financial contracts. In fact, the time $t_{2}$ exchange shown in Figure 4.11c has a missing time $t_{0}$ cash flow of size $B(t_{0},t_{2})[F(t_{0},t_{1})-s_{t_{0}}]\delta N$ . Only by adding this, does the exchange become a tradeable contract. The $s_{t_{0}}$ is a fair exchange for the risks associated with $L_{t_{0}},L_{t_{1}}$ , and $L_{t_{2}}$ on the average. As a result, the time $t_{2}$ cash exchange that is part of the swap contract ceases to have a zero present value when considered individually.  

# 4.5.2.1 Pricing  

We have seen that it is not possible to interpret the individual swap settlements as FRA contracts directly. The two exchanges have a nonzero present value, while the (newly initiated) FRA contracts have a price of zero. But the previous analysis is still useful for pricing the swap since it gives us an important relationship.  

In fact, we just showed that the time. $t_{2}$ element of the swap has the present value. $B(t_{0},t_{2})[F(t_{0},t_{1})-s_{t_{0}}]\delta N,$ which is not, normally, zero. This must be true for all swap settlements. individually. Yet, the swap cash flows altogether do have zero present value. This leads to the following important pricing relation:.  

$$
B(t_{0},t_{1})[F(t_{0},t_{0})-s_{t_{0}}]\delta N+B(t_{0},t_{2})[F(t_{0},t_{1})-s_{t_{0}}]\delta N+B(t_{0},t_{3})[F(t_{0},t_{2})-s_{t_{0}}]\delta N=0
$$  

Rearranging provides a formula that ties the swap rate to FRA rates:  

$$
s_{t_{0}}=\frac{B(t_{0},t_{1})[F(t_{0},t_{0})+B(t_{0},t_{2})F(t_{0},t_{1})+B(t_{0},t_{3})F(t_{0},t_{2})}{B(t_{0},t_{1})+B(t_{0},t_{2})+B(t_{0},t_{3})}
$$  

This means that we can price swaps off the FRA market as well. The general formula, where $n$ is the maturity of the swap,  

$$
s_{t_{0}}=\frac{\displaystyle\sum_{i=1}^{n}B(t_{0},t_{i})F(t_{0},t_{i-1})}{\displaystyle\sum_{i=1}^{n}B(t_{0},t_{i})}
$$  

will be used routinely in this book. It is an important arbitrage relationship between swap rates and FRA rates.  
