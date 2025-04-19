---
tags:
  - '#credit_risk'
  - '#forward_rate_agreements'
  - '#fra_contract'
  - '#fra_strips'
  - '#hedging'
  - '#interest_rate_risk'
  - '#libor_rate'
  - '#market_value'
  - '#synthetic_fra'
---
# 3.7 FORWARD RATE AGREEMENTS  

An interest rate FRA is an interest rate forward contract, an over-the-counter contract, between parties that specifies the rate of interest to be paid or received on an obligation beginning at a future start date. The next section develops a contractual agreement for an interest rate FRA. Currency FRAs are discussed in Chapter 6.  

A forward loan contract implies not one but two obligations. First, 100 units of currency will have to be received at time $t_{1}$ , and second, interest $F_{t_{0}}$ has to be paid. One can see several draw-. backs to such a contract:  

1. The forward borrower may not necessarily want to receive cash at time $t_{1}$ . In most hedging and arbitraging activities, the players are trying to lock in an unknown interest rate and are not necessarily in need of "cash." A case in point is the convergence play described in Section 3.2, where practitioners were receiving (future) Italian rates and paying (future) Spanish rates. In these strategies, the objective of the players was to take a position on Spanish and Italian interest rates. None of the parties involved had any wish to end up with a loan in 1 or 2 years.  

2. A second drawback is that forward loan contracts involve credit risk. It is not a good idea to put a credit risk on a balance sheet if one wanted to lock in an interest rate.2.  

3. These attributes may make speculators and arbitrageurs stay away from any potential forward loan markets, and the contract may be illiquid..  

These drawbacks make the forward loan contract a less-than-perfect financial engineering. instrument. A good instrument would separate the credit risk and the interest rate commitment that coexist in the forward loan. It turns out that there is a nice way this can be done..  

# 3.7.1 ELIMINATING THE CREDIT RISK  

First, note that a player using the forward loan only as a tool to lock in the future LIBOR rate $L_{t_{1}}$ will immediately have to relend the USD100 received at time $t_{1}$ at the going market rate $L_{t_{1}}$ Figure 3.14a displays a forward loan committed at time $t_{0}$ . Figure 3.14b shows the corresponding spot deposit. The practitioner waits until time $t_{1}$ and then makes a deposit at the rate $L_{t_{1}}$ , which will be known at that time. This "swap"' cancels an obligation to receive 100 and ends up with only the fixed rate $F_{t_{0}}$ commitment.  

Thus, the joint use of a forward loan, and a spot deposit to be made in the future, is sufficient to reach the desired objective-namely, to eliminate the risk associated with the unknown LIBOR rate $L_{t_{1}}$ . These steps will lock in. $F_{t_{0}}$ We consider the result of this strategy in Figure 3.14c.. Add vertically the cash flows of the forward loan (3.14a) and the spot deposit (3.14b). Time $t_{1}$ cash flows cancel out since they are in the same currency. Time $t_{2}$ payment and receipt of the  

# FIGURE 3.14  

![](7816ab9155aaaf53a074a4dd57f42f447791037bef99270512e217b1166c65cd.jpg)  

A synthetic FRA.  

principal will also cancel. What is left is the respective interest payments. This means that the portfolio consisting of  

will lead, according to Figure 3.14c, to the following (net) cash flows:  

<html><body><table><tr><td></td><td>Cash F Paid</td><td>Cash Received</td><td>Total</td></tr><tr><td>Time t Time t2</td><td>100 100(1 1 + Ft8)</td><td>+100 100(1 + Lt, 8)</td><td>0 100(L -Ft)8</td></tr></table></body></html>  

Thus, letting the principal of the forward loan be denoted by the parameter $N$ we see that the portfolio in expression (3.37) results in a time $t_{2}$ net cash flow equaling  

$$
N(L_{t_{1}}-F_{t_{0}})\delta
$$  

where $\delta$ is the day's adjustment to interest, as usual.  

# 3.7.2 DEFINITION OF THE FRA  

This is exactly where the FRA contract comes in. If a client has the objective of locking in the future borrowing or lending costs using the portfolio in Eq. (3.37), why not offer this to him or her in a single contract? This contract will involve only the exchange of two interest payments shown in Figure 3.14c.  

In other words, we write a contract that specifies a notional amount, $N$ , the dates $t_{1}$ and $t_{2}$ , and the "price" $F_{t_{0}}$ , with payoff $N(L_{t_{1}}-F_{t_{0}})\delta$ 22 This instrument is a paid-in-arrears FRA.23 In an FRA contract, the purchaser accepts the receipt of the following sum at time $t_{2}$  

$$
(L_{t_{1}}-F_{t_{0}})\delta N
$$  

if $L_{t_{1}}>F_{t_{0}}$ at date $t_{1}$ . On the other hand, the purchaser pays  

$$
(F_{t_{0}}-L_{t_{1}})\delta N
$$  

if $L_{t_{1}}<F_{t_{0}}$ at date $t_{1}$ . Thus, the buyer of the FRA will pay fixed and receive floating.  

In the case of market-traded FRA contracts, there is one additional complication. The settlement is not done in-arrears at time. $t_{2}$ . Instead, FRAs are settled at time. $t_{1}$ and the transaction will involve the following discounted cash flows. The.  

$$
\frac{(L_{t_{1}}-F_{t_{0}})\delta N}{(1+L_{t_{1}}\delta}
$$  

will be received at time $t_{1}$ , if $L_{t_{1}}>F_{t_{0}}$ at date $t_{1}$ . On the other hand,  

$$
\frac{(F_{t_{0}}-L_{t_{1}})\delta N}{(1+L_{t_{1}}\delta}
$$  

2The $N$ represents a notional principal since the principal amount will never be exchanged. However, it needs to be specified in order to determine the amount of interest to be exchanged..   
$^{23}\mathrm{It}$ is paid-in-arrears because the unknown interest, $L_{t_{1}}$ , will be known at time. $t_{1}$ , the interest payments are exchanged at time $t_{2}$ , when the forward (fictitious) loan is due.  

will be paid at time. $t_{1}$ , if $L_{t_{1}}<F_{t_{0}}$ . Settling at. $t_{1}$ instead of $t_{2}$ has one subtle advantage for the FRA seller, which is often a bank. If during $[t_{0},t_{1}]$ the interest rate has moved in favor of the bank, time $t_{1}$ settlement will reduce the marginal credit risk associated with the payoff. The bank can then operate with a lower credit line..  

# 3.7.2.1 An interpretation  

Note one important interpretation. An FRA contract can be visualized as an exchange of two interest payments. The purchaser of the FRA will be paying the known interest $F_{t_{0}}\delta N$ and is accepting the (unknown) amount $L_{t_{1}}\delta N$ . Depending on which one is greater, the settlement will be a receipt or a payment. The sum $F_{t_{0}}\delta N$ can be considered, as of time $t_{0}$ , as the fair payment market participants are willing to make against the random and unknown $L_{t_{1}}\delta N$ . It can be regarded as the time to "market value" of $L_{t_{1}}\delta N$  

# 3.7.3 FRA CONTRACTUAL EQUATION  

We can immediately obtain a synthetic FRA using the ideas displayed in Figure 3.14. Figure 3.14 displays a swap of a fixed-rate loan of size $N$ , against a floating-rate loan of the same size. Thus, we can write the contractual equation  

![](d15330324c48d13395276204eab0d0bb5c8e586b8c5a809dca1979378943f8da.jpg)  

It is clear from the construction in Figure 3.14 that the FRA contract eliminates the credit risk associated with the principals-since the two N's will cancel out-but leaves behind the exchange. of interest rate risk. In fact, we can push this construction further by "plugging in' the contractual. equation for the fixed rate forward loan obtained in formula (3.33) and get.  

![](3dfe28c6c54f4dec98a386753feb70b4d67eaa566f903fcd6207f495b39d9093.jpg)  

This contractual equation can then be exploited to create new synthetics. One example is the use of FRA strips.  

# 3.7.3.1 Application: FRA strips  

Practitioners use portfolios of FRA contracts to form FRA strips. These in turn can be used to construct synthetic loans and deposits and help to hedge swap positions. The best way to understand. FRA strips is with an example that is based on the contractual equation for FRAs obtained earlier.  

Suppose a market practitioner wants to replicate a 9-month fixed-rate borrowing synthetically.. Then the preceding contractual equation implies that the practitioner should take a cash loan at time $t_{0}$ , pay the LIBOR rate $L_{t_{0}}$ , and buy an FRA strip made of two sequential FRA contracts, a. $(3\times6)$ FRA and a $(6\times9)$ FRA. This will give a synthetic 9-month fixed-rate loan. Here the. symbol $(3\times6)$ means $t_{2}$ is 6 months and $t_{1}$ is 3 months.  

Before we discuss interest rate futures and compare them to interest rate forwards we introduce some basic risk measures for fixed income markets. This discussion will help us to appreciate some of the difference between interest rate forwards and futures..  
