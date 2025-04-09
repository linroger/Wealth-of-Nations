# 6.7 SWAP ENGINEERING IN FX MARKETS  

So far we have discussed simple currency derivatives in the form of FX forward. Now we will. apply the more advanced financial engineering concepts related to interest rate swaps that we discussed in Chapter 4 and illustrate swap engineering in FX markets. We will encounter two different types of swaps linked to FX markets. First we will discuss FX swaps, then we will turn to currency. swaps. As we will see there are important differences in the replication and uses of FX and currency swaps respectively. In practice, in terms of turnover, the FX swap market is an order of mag-. nitude larger than the currency swap market..  

In the previous sections, we created two synthetics for forward FX contracts. We can now ask. the next question: Is there an optimal way of creating a synthetic? Or, more practically, can a trader buy a synthetic cheaply, and sell it to clients after adding a margin, and still post the smallest bid-ask spreads?  

# 6.7.1 FX SWAPS  

We can use the so-called FX swaps and pay a single bid-ask spread instead of going through two separate bid--ask spreads, as is done in contractual equation (6.8). The construction of an FX swap is shown in Figure 6.6.  

According to this figure, there are at least two ways of looking at a FX swap. The FX swap is made of a money market deposit and a money market loan in different currencies written on the same "ticket." The second interpretation is that we can look at a FX swap as if the two counterpar-. ties spot purchase and forward sell two currencies against each other, again on the same deal. ticket.  

When combined with a spot operation, FX swaps duplicate forward currency contracts easily, as shown in Figure 6.7. Because they are swaps of a deposit against a loan, interest rate differentials  

![](images/68fa8a8ef3554d93c138d0ce67a2145eeddb97d729a0b2861453470529efc852.jpg)  

# FIGURE 6.6  

A simplified FX swap.  

will play an important role in FX swaps. After all, one of the parties will be giving away a currency that can earn a higher rate of interest and, as a result, will demand compensation for this "loss."' This compensation will be returned to him or her as a proportionately higher payment at time $t_{1}$ The parties must exchange different amounts at time $t_{1}$ , as compared to the original exchange at $t_{0}$  

As the above figure shows, an FX swap is a contract in which one party borrows one currency. from, and at the same time lends another to, the second party. Each party uses the repayment obligation to its counterparty as collateral and the amount of repayment is fixed at the FX forward rate at the start of the contract. Hence, FX swaps can be interpreted as collateralized borrowing/lending,. although the collateral does not necessarily cover the entire counterparty risk..  

# 6.7.1.1 Advantages  

Why would a bank prefer to deal in FX swaps instead of outright forward? This is an important. question from the point of view of financial engineering. It illustrates the advantages of spread products.  

FX swaps have several advantages over the synthetic seen earlier. First of all, FX swaps are interbank instruments and, normally, are not available to clients. Banks deal with each other every day, and thus, compared to other counterparties, one could argue that counterparty risk is relatively lower in writing such contracts. In liquid markets, the implied bid-ask spread for synthetics  

![](images/52847ac6803c0d69d61bf316cd3acc2207e354531cb197787f9580f1a0dd2f38.jpg)  

# FIGURE 6.7  

FX swap combined with spot operation leads to forward.  

constructed using FX swaps will be smaller than the synthetic constructed from deposits and loans, or T-bills for that matter.  

The second issue is liquidity. How can a market participant borrow and lend in both currencies without moving prices? An FX swap is again a preferable way of doing this. With an FX swap, traders are not buying or selling deposits, rather they are exchanging them.  

The final advantage of FX swaps resides in their balance sheet effects, or the lack thereof. The synthetic developed in Figure 6.2 leads to increased assets and liabilities. One borrows new funds and lends them. Such transactions may lead to new credit risks and new capital requirements. FX swaps are off-balance sheet items, and the synthetic shown in Figure 6.7 will have minor balance sheet effects. FX swaps can affect a bank's capital adequacy ratio (CAR) since they change the capital requirement for market risk and credit market risk.14  

# 6.7.1.2 Uses of FX swaps  

Financial institutions and their clients, such as exporters and importers as well as investors, use FX swaps to hedge their positions. FX swaps can also be used for speculation, typically by combining two offsetting FX swap positions with different maturity dates. Financial institutions with a need for foreign currency can either (a) borrow directly in the uncollateralized money. market for the foreign currency or (b) borrow in another (normally the domestic) currency's uncollateralized money market, and then convert the proceeds into a foreign currency obligation. through an FX swap. When a bank, for example, raises dollars by means of an FX swap using. the euro as a funding currency, it exchanges euros for dollars at the FX spot rate. The borrowing cost in dollars implied by the EUR/USD FX swap is called the FX swap-implied dollar rate $r_{t_{0}}^{\mathrm{d}}$ . It is defined as  

$$
r_{t_{0}}^{\mathrm{d}}=\frac{F_{t_{0}}}{e_{t_{0}}}\times\left(1+r_{t_{0}}^{\mathrm{f}}\right)
$$  

where $r_{t_{0}}^{\mathrm{d}}$ and $r_{t_{0}}^{\mathrm{f}}$ are the relevant interest rates in domestic and foreign currencies, respectively, and $F_{t_{0}}$ and $e_{t_{0}}$ are the forward and spot rates between the euro and the dollar. The choice of whether. the bank should raise dollars using (a) or (b) above should be a function of the relative cost. If the. costs associated with (a) and (b) are the same, i.e., the FX swap-implied dollar rate is equal to the dollar LIBOR rate in our example, then CIRP holds. Deviations from CIRP occurred during the GFC and other turbulent financial market episodes in the past, but arbitrageurs must be careful. when interpreting any test of CIRP deviations since these must carefully take into account real-life. complications such as bid-ask spreads, differences between the costs of secured and unsecured borrowing as well as whether rates such as LIBOR reflect actual interbank borrowing costs in periods of stress.  

# 6.7.1.3 Quotation conventions  

There is an important advantage to quoting swap points over the outright forward quotes. This indicates a subtle aspect of market activity. A quote in terms of forward points will essentially be independent of spot exchange rate movements and will depend only on interest rate differentials. An outright forward quote, on the other hand, will depend on the spot exchange rate movements as. well. Thus, by quoting forward points, market professionals are essentially separating the risks associated with interest rate differentials and spot exchange rate movements respectively. The. exchange rate risk will be left to the spot trader. The forward FX trader will be trading the risk associated with interest rate differentials only.  

To see this better, we now look at the details of the argument.  

Taking partial derivatives of Eq. (6.21) gives  

$$
\begin{array}{r l r}&{}&{\partial{\big(}F_{t_{0}}-e_{t_{0}}{\big)}\cong\left(r_{t_{0}}^{\mathrm{d}}-r_{t_{0}}^{\mathrm{f}}\right)\left(\frac{t_{1}-t_{0}}{360}\right)\partial e_{t_{0}}}\ &{}&{\cong0\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\end{array}
$$  

If the daily movement of the spot rate $e_{t_{0}}$ is small, the right-hand side will be negligible. In other words, the forward swap quotes would not change for normal daily exchange rate movements, if interest rates remain the same and as long as exchange rates are quoted to four decimal places. The following example illustrates what this means.  

# EXAMPLE  

Suppose the relevant domestic and foreign interest rates are given by  

$$
\begin{array}{r}{r_{t_{0}}^{\mathrm{d}}=0.03440}\ {\qquad\quad}\ {r_{t_{0}}^{\mathrm{f}}=0.02110}\end{array}
$$  

where the domestic currency is euro and the foreign currency is USD. If the EUR/USD. exchange rate has a daily volatility of, say,. $0.0l\%$ a day, which is a rather significant move,. then, for FX swaps with 3-month maturity, we have the following change in forward points:  

$$
\begin{array}{c}{\displaystyle{\partial\big(F_{t_{0}}-e_{t_{0}}\big)=0.01330\bigg(\frac{90}{360}\bigg)0.0100}}\ {\displaystyle{=0.00003325}}\end{array}
$$  

which, in a market that quotes only four decimal points, will be negligible.  

Hence, forward points depend essentially on the interest rate differentials. This "separates" exchange rate and interest rate risk and simplifies the work of the trader. It also shows that forward FX contracts can be interpreted as if they are "hidden"' interest rate contracts.  
