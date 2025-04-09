# 3.6 A CONTRACTUAL EQUATION  

Once an instrument is replicated with a portfolio of other (liquid) assets, we can write a contractual equation and create new synthetics. In this section, we will obtain a contractual equation. In the next section, we will show several applications. This section provides a basic approach to constructing static replicating portfolios and hence is central to what will follow.  

# 3.6.1 FORWARD LOAN  

A forward loan is engineered like any forward contract, except that what is being bought or sold is not a currency or commodity, but instead, a loan. At time $t_{0}$ , we write a contract that will settle at a future date $t_{1}$ . At settlement, the trader receives (delivers) a loan that matures at $t_{2}$ $t_{1}<t_{2}$ . The contract will specify the interest rate that will apply to this loan. This interest rate is called the forward rate and will be denoted by $F\left(t_{0},t_{1},t_{2}\right)$ . The forward rate is determined at $t_{0},t_{1}$ is the start date of the future loan, and $t_{2}$ is the date at which the loan matures.  

The situation is depicted in Figure 3.10. We write a contract at $t_{0}$ such that at a future date, $t_{1}$ USD100 are received; the principal and interest are paid at $t_{2}$ . The interest is. $F_{t_{0}}\delta$ , where $\delta$ is the day-count adjustment, ACT/360:  

$$
\delta=\frac{t_{2}-t_{1}}{360}
$$  

To simplify the notation, we abbreviate the. $F\left(t_{0},t_{1},t_{2}\right)$ as $F_{t_{0}}$ . The day-count convention needs to be adjusted if a year is defined as having 365 days.  

Forward loans permit a great deal of flexibility in balance sheet, tax, and risk management. The need for forward loans arises under the following conditions:.  

A business would like to lock in the "current' low borrowing rates from money markets. A bank would like to lock in the "current' high lending rates.   
A business may face a floating-rate liability at time $t_{1}$ . The business may want to hedge this liability by securing a future loan with a known cost.  

It is straightforward to see how forward loans help to accomplish these goals. With the forward loan of Figure 3.10, the party has agreed to receive 100 dollars at. $t_{1}$ and to pay them back at $t_{2}$ with interest. The key point is that the interest rate on this forward loan is fixed at time. $t_{0}$ . The forward rate $F\left(t_{0},t_{1},t_{2}\right)$ "locks in"' an unknown future variable at time. $t_{0}$ and thus eliminates the risk associated with the unknown rate. The $L_{t_{1}}$ is the LIBOR interest rate for a $(t_{2}-t_{1})$ period loan and can be observed only at the future date $t_{1}$ . Fixing $F\left(t_{0},t_{1},t_{2}\right)$ will eliminate the risk associated with $L_{t_{1}}$  

The chapter discusses several examples involving the use of forward loans and their more recent counterparts, FRAs.  

![](1901b368784648301b7845ed0541ef9881df0656f20e7ce28e315656ac40e6be.jpg)  

# FIGURE 3.10  

A forward loan.  

# 3.6.2 REPLICATION OF A FORWARD LOAN  

In this section, we apply the financial engineering outlined in Chapter 1 to forward loans and.   
thereby obtain synthetics for this instrument. More than the synthetic itself, we are concerned with the methodology used in creating it. Although forward loans are not liquid and rarely traded in the.   
markets, the synthetic will generate a contractual equation that will be useful for developing con-.   
tractual equations for FRAs, and the latter are liquid instruments..  

We begin the engineering of a synthetic forward loan by following the same strategy described in Chapter 1. We first decompose the forward loan cash flows into separate diagrams and then try to convert these into known liquid instruments by adding and subtracting appropriate new cash flows. This is done so that, when added together, the extra cash flows cancel each other out and the original instrument is recovered. Figure 3.11 displays the following steps:  

1. We begin with the cash flow diagram for the forward loan shown in Figure 3.11a. We detach the two cash flows into separate diagrams. Note that at this stage, these cash flows cannot.  

![](cf42c5240cf9d8a4d96abc26abd7ab40ef8372893ac8801d40071774989b3be6.jpg)  

# FIGURE 3.11  

form tradeable contracts. Nobody would want to buy 3.11c, and everybody would want to have 3.11b.  

2. We need to transform these cash flows into tradeable contracts by adding compensating cash flows in each case. In Figure 3.11b, we add a negative cash flow, preferably at time $t_{0}$ 15 This is shown in Figure 3.11d. Denote the size of the cash flow by $-C_{t_{0}}$  

3. In Figure 3.11c, add a positive cash flow at time $t_{0}$ , to obtain Figure 3.11e. The cash flow has. $\mathrm{size}+C_{t_{0}}$  

4. Make sure that the vertical addition of Figure 3.11d and e will replicate what we started with in Figure 3.11a. For this to be the case, the two newly added cash flows have to be identical in absolute value but different in sign. A vertical addition of Figure 3.11d and e will cancel any. cash exchange at time $t_{0}$ , and this is exactly what is needed to duplicate Figure 3.11a.16  

At this point, the cash flows of Figure 3.11d and e need to be interpreted as specific financial contracts so that the components of the synthetic can be identified. There are many ways to do this. Depending on the interpretation, the synthetic will be constructed using different assets.  

# 3.6.2.1 Bond market replication  

As usual, we assume credit risk away.. $\mathbf{A}$ first synthetic can be obtained using bond and T-bill mar-. kets. Although this is not the way preferred by practitioners, we will see that the logic is fundamental to financial engineering. Suppose default-free pure discount bonds of specific maturities denoted by $\{B(t_{0},t_{i}),i=1,...,n\}$ trade actively.17 They have par value of 100.  

Then, within the context of a pure discount bond market, we can interpret the cash flows in Figure 3.11d as a long position in the $t_{1}$ -maturity discount bond. The trader is paying $C_{t_{0}}$ at time $t_{0}$ and receiving 100 at $t_{1}$ . This means that  

$$
B(t_{0},t_{1})=C_{t_{0}}
$$  

Hence, the value of $C_{t_{0}}$ can be determined if the bond price is known.  

The synthetic for the forward loan will be fully described once we put a label on the cash flows in Figure 3.11e. What do these cash flows represent? These cash flows look like an appropriate short position in a $t_{2}$ -maturity discount bond.  

Does this mean we need to short one unit of the $B(t_{0},t_{2})^{\ast}$ ? The answer is no, since the time $t_{0}$ cash flow in Figure 3.11e has to equal $C_{t_{0}}.^{18}$ However, we know that a $t_{2}$ -maturity bond will necessarily be cheaper than a $t_{1}$ -maturity discount bond.  

$$
B(t_{0},t_{1})<B(t_{0},t_{1})=C_{t_{0}}
$$  

Thus, shorting one $t_{2}$ -maturity discount bond will not generate sufficient time $t_{0}$ funding for the position in Figure 3.11d. The problem can easily be resolved, however, by shorting not one but $\lambda$ bonds such that  

$$
\lambda B(t_{0},t_{2})=C_{t_{0}}
$$  

But we already know that $B(t_{0},t_{1})=C_{t_{0}}$ . So the $\lambda$ can be determined easily:  

$$
\lambda=\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}
$$  

According to Eq. (3.3) $\lambda$ will be greater than one. This particular short position will generate enough cash for the long position in the $t_{1}$ -maturity bond. Thus, we finalized the first synthetic for the forward loan:  

$$
\left\{\mathrm{Buy~one~}t_{1}\mathrm{-discount~bond,~short~}\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}\mathrm{~units~of~the~}t_{2}\mathrm{-discount~bond}\right\}
$$  

To double-check this result, we add Figure 3.11d and e vertically and recover the original cash flow for the forward loan in Figure 3.11a.  

# 3.6.2.2 Pricing  

If markets are liquid and there are no other transaction costs, arbitrage activity will make sure that the cash flows from the forward loan and from the replicating portfolio (synthetic) are the same.. In other words, the sizes of the time. $t_{2}$ cash flows in Figure 3.11a and e should be equal. This. implies that  

$$
1+F(t_{0},t_{1},t_{2})\delta=\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}
$$  

where the $\delta$ is, as usual, the day-count adjustment.  

This arbitrage relationship is of fundamental importance in financial engineering. Given liquid. bond prices $\{B(t_{0},t_{1}),B(t_{0},t_{1})\}$ , we can price the forward loan off the bond markets using this. equation. More important, equality (3.23) shows that there is a crucial relationship between forward rates at different maturities and discount bond prices. But discount bond prices are discounts which can be used in obtaining the present values of future cash flows. This means that forward rates are of primary importance in pricing and risk managing financial securities..  

Before we consider a second synthetic for the forward loan, we prefer to discuss how all this relates to the notion of arbitrage.  

# 3.6.2.3 Arbitrage  

What happens when the equality in formula (3.23) breaks down? We analyze two cases assuming that there are no bid-ask spreads. First, suppose market quotes at time. $t_{0}$ are such that  

$$
(1+F_{t_{0}}\delta)>\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}
$$  

where the forward rate $F(t_{0},t_{1},t_{2})$ is again abbreviated as $F_{t_{0}}$ . Under these conditions, a market participant can secure a synthetic forward loan in bond markets at a cost below the return that could be obtained from lending in forward loan markets. This will guarantee positive arbitrage gains.. This is the case since the "synthetic" funding cost, denoted by F%,  

$$
F_{t_{0}}^{*}=\frac{B(t_{0},t_{1})}{\delta B(t_{0},t_{2})}-\frac{1}{\delta}
$$  

will be less than the forward rate, $F_{t_{0}}$ . The position will be riskless if it is held until maturity date $t_{2}$  

These arbitrage gains can be secured by (i) shorting $B(t_{0},t_{1})/B(t_{0},t_{2})$ units of the $t_{2}$ -bond, which generates $B(t_{0},t_{1})$ dollars at time $t_{0}$ , then (ii) using these funds buying one $t_{1}$ -maturity bond, and. (iii) at time $t_{1}$ lending, at rate. $F_{t_{0}}$ , the 100 received from the maturing bond. As a result of these operations, at time. $t_{2}$ , the trader would owe. $(B(t_{0},t_{1})/B(t_{0},t_{2}))100$ and would receive. $(1+F_{t_{0}}\delta)100$  

The latter amount is greater, given the condition (3.24).  

Now consider the second case. Suppose time $t_{0}$ markets quote:  

$$
(1+F_{t_{0}}\delta)<\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}
$$  

Then, one can take the reverse position. Buy. $B(t_{0},t_{1})/B(t_{0},t_{2})$ units of the. $t_{2}$ bond at time $t_{0}$ To fund this, short a $B(t_{0},t_{1})$ bond and borrow 100 forward. When time. $t_{2}$ arrives, receive the $(B(t_{0},t_{1})/B(t_{0},t_{2}))100$ and pay off the forward loan. This strategy can yield arbitrage profits since the funding cost during $[t_{1},t_{2}]$ is lower than the return..  

# 3.6.2.4 Money market replication  

Now assume that all maturities of deposits up to 1 year are quoted actively in the interbank money market. Also assume there are no arbitrage opportunities. Figure 3.12 shows how an alternative. synthetic can be created. The cash flows of a forward loan are replicated in Figure 3.12a. Figure 3.12c shows a Euromarket loan. $C_{t_{0}}$ is borrowed at the interbank rate $L_{t_{0}}^{2}$ 19 The time $t_{2}$ cash flow in Figure 3.12c needs to be discounted using this rate. This gives.  

$$
C_{t_{0}}=\frac{100(1+F_{t_{0}}\delta)}{(1+L_{t_{0}}^{2}\delta^{2})}
$$  

where $\delta^{2}=(t_{2}-t_{0})/360$  

Then, $C_{t_{0}}$ is immediately redeposited at the rate $L_{t_{0}}^{1}$ at the shorter maturity. To obtain.  

$$
C_{t_{0}}(1+L_{t_{0}}^{1}\delta^{1})=100
$$  

with $\delta^{1}=(t_{1}-t_{0})/360$ . This is shown in Figure 3.12b.  

Adding Figure 3.12b and c vertically, we again recover the cash flows of the forward loan. Thus, the two Eurodeposits form a second synthetic for the forward loan.  

# 3.6.2.5 Pricing  

We can obtain another pricing equation using the money market replication. In Figure 3.12, if the credit risks are the same, the cash flows at time $t_{2}$ would be equal, as implied by Eq. (3.27). This can be written as  

$$
(1+F_{t_{0}}\delta)100=C_{t_{0}}(1+L_{t_{0}}^{2}\delta^{2})
$$  

where $\delta=(t_{2}-t_{1})/360$ We can substitute further from formula (3.28) to get the final pricing formula:  

$$
(1+F_{t_{0}}\delta)100=\frac{100(1+L_{t_{0}}^{2}\delta^{2})}{(1+L_{t_{0}}^{1}\delta^{1})}
$$  

![](a2032e24693d6cfede863c47d7b5a570216e32ada2481eca8899b1fa8b1bd70e.jpg)  

# FIGURE 3.12  

Money market replication of a forward loan.  

Simplifying,  

$$
(1+F_{t_{0}}\delta)=\frac{1+L_{t_{0}}^{2}\delta^{2}}{1+L_{t_{0}}^{1}\delta^{1}}
$$  

This formula prices the forward loan off the money markets. The formula also shows the important role played by LIBOR interest rates in determining the forward rates..  

# 3.6.3 CONTRACTUAL EQUATIONS  

We can turn these results into analytical contractual equations. Using the bond market replication. we obtain  

![](b7de80eb4b3a97ba934ca2230228e294fce5dc072cc44ab79a5074a68ece847d.jpg)  

The expression shown in formula (3.32) is a contractual equation. The left-hand-side contract leads to the same cash flows generated jointly by the contracts on the right-hand side. This does not necessarily mean that the monetary value of the two sides is always the same. In fact, one or more of the contracts shown on the right-hand side may not even exist. in that particular economy and the markets may not even have the opportunity to put a price. on them.  

Essentially the equation says that the risk and cash flow attributes of the two sides are the same.. If there is no credit risk, no transaction costs, and if the markets in all the involved instruments are liquid, we expect that arbitrage will make the values of the two sides of the contractual. equation equal.  

If we use the money markets to construct the synthetic, the contractual equation above becomes  

![](7c179f940e610a069bc1ae74fa1c8b57242489e442aefcd7370bde6874a52397.jpg)  

These contractual equations can be exploited for finding solutions to some routine problems encountered in financial markets although they do have drawbacks. Ignoring these for the time being we give some examples.  

# 3.6.4 APPLICATIONS  

Once a contractual equation for a forward loan is obtained, it can be algebraically manipulated to create further synthetics. We discuss two such applications in this section.  

# 3.6.4.1 Application 1: creating a synthetic bond  

Suppose a trader would like to buy a. $t_{1}$ -maturity bond at time $t_{0}$ .The trader also wants this bond to. be liquid. Unfortunately, he discovers that the only bond that is liquid is an on-the-run Treasury with a longer maturity of. $t_{2}$ . All other bonds are off-the-run.? How can the trader create the liquid short-term bond synthetically assuming that all bonds are of discount type and that, contrary to real-. ity, forward loans are liquid?.  

Rearranging Eq. (3.32), we get  

![](443d4010a66146daca7be25c8f4e493411549e7cb1f1dfefdc5f6b0f0d271b6c.jpg)  

The minus sign in front of a contract implies that we need to reverse the position. Doing this. we see that a $t_{1}$ -maturity bond can be constructed synthetically by arranging a forward loan from $t_{1}$  

![](ef4e1e5e9301829010983987d70296d4082562c0892250bcc0ef944fe76d5d4f.jpg)  

# FIGURE 3.13  

Constructing a bond synthetically  

to $t_{2}$ and then by going long. $B(t_{0},t_{1})/B(t_{0},t_{2})$ units of the bond with maturity. $t_{2}$ . The resulting cash flows would be identical to those of a short bond. More important, if the forward loan and the long bond are liquid, then the synthetic will be more liquid than any existing off-the-run bonds with maturity $t_{1}$ This construction is shown in Figure 3.13.  

# 3.6.4.2 Application 2: covering a mismatch  

Consider a bank that has a maturity mismatch at time $t_{0}$ . The bank has borrowed. $t_{1}$ -maturity funds from Euromarkets and lent them at maturity $t_{2}$ . Clearly, the bank has to roll over the short-term loan that becomes due at time $t_{1}$ with a new loan covering the period $[t_{1},t_{2}]$ . This new loan carries. an (unknown) interest rate $L_{t_{1}}$ and creates a mismatch risk. The contractual equation in formula (3.33) can be used to determine a hedge for this mismatch, by creating a synthetic forward loan, and, in this fashion, locking in time $t_{1}$ funding costs.  

In fact, we know from the contractual equation in formula (3.33) that there is a relationship between short and long maturity loans:.  

![](e65f4079316a89c5d54f4627926f632eaf6695d2cff4c532b45f860884a79632.jpg)  

Changing signs, this becomes  

![](5b3e0d8559c1fe6fcdb6bc430d48a9f109548046d0ca3a69217046ca1a84e4ff.jpg)  

According to this, the forward loan converts the short loan into a longer maturity loan and in this way eliminates the mismatch..  
