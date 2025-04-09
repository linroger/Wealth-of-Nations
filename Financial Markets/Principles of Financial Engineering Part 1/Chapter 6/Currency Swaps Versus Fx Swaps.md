# 6.8 CURRENCY SWAPS VERSUS FX SWAPS  

Although they have similar names, currency swaps and FX swaps are different instruments. First we introduce currency swaps and apply the swap engineering methodology from Chapter 4 to their replication. Then we will highlight differences between currency swaps and FX swaps..  

# 6.8.1 CURRENCY SWAPS  

Currency swaps15 are similar to interest rate swaps, but there are some differences. First, the exchanged cash flows are in different currencies. This means that two different yield curves are involved in swap pricing instead of just one. Second, in the large majority of cases, a floating rate is exchanged against another floating rate. A third difference lies in the exchange of principals at initiation and a re-exchange at maturity. In the case of interest rate swaps, this question does not arise since the notional amounts are in the same currency. Yet, currency swaps can be engineered almost the same way as interest rate swaps.  

Formally, a currency swap will have the following components. There will be two currencies, say USD $(\$)$ and euro (). The swap is initiated at time $t_{0}$ and involves (1) an exchange of a principal amount $N^{\mathbb{S}}$ against the principal $\overset{\cdot}{M}^{\epsilon}$ and (2) a series of floating interest payments associated with the principalse $N^{\mathbb{S}}$ and $M^{\epsilon}$ respectively. They are settled at settlement dates, $\{t_{1},t_{2},...,t_{n}\}$ . One party will. pay the floating payments $L_{t_{i}}^{\mathbb{S}}N^{\mathbb{S}}\delta$ and receive floating payments of size $L_{t_{i}}M\delta$ . The two LIBOR rates $L_{t_{i}}^{\mathbb{S}}$ and $L_{t_{i}}$ will be determined at set dates $\{t_{0},t_{1},...,t_{n-1}\}$ . The maturity of swap will be $m$ years.  

A small spread $s_{t_{0}}$ can be added to one of the interest rates to make both parties willing tc. exchange the cash flows. The market maker will quote bid/ask rates for this spread.  

# EXAMPLE  

Figure 6.8 shows a currency swap. The USD notional amount is 1 million. The current USD/ EUR exchange rate is at 0.95. The agreed spread is 6 bp. The initial 3-month LIBOR rates are  

$$
L_{t_{i}}^{\S}=3\%
$$  

$$
L_{t_{i}}^{\S}=3.5\%
$$  

![](a7749bd2bf2645f28c379bc15177066aaa50d474b146ee1cf72554315abc818a.jpg)  
Pay EUR-LIBOR based floating cash flows plus some small spread. Note that the principals are swapped at the same exchange rate USD/EUR...  

# FIGURE 6.8  

Three-period currency swap.  

This means that at the first settlement date  

$$
(1,000,000)(0.03+0.0006)\frac{1}{4}=\mathbb{5}7650
$$  

will be exchanged against  

$$
0.95(1,000,000)(0.035)\frac{1}{4}=8312.5
$$  

All other interest payments would be unknown. Note that the euro principal amount is related to the USD principal amount according to  

$$
e_{t_{0}}N^{\S}=M
$$  

where $e_{t_{0}}$ is the spot exchange rate at $t_{0}$ Also, note that we added the swap spread to the USD LIBOR.  

Pricing currency swaps will follow the same principles as interest rate swaps. A currency swap involves well-defined cash flows and consequently we can calculate an arbitrage-free value for each sequence of cash flows. Then these cash flows are traded. An appropriate spread is added to either floating rate.  

By adjusting this spread, a swap dealer can again make the two parties willing to exchange the two cash flows.  

# 6.8.2 DIFFERENCES BETWEEN CURRENCY SWAPS AND FX SWAPS  

We will now compare currency swaps with FX swaps introduced earlier. To recap, a currency swap has the following characteristics:  

1. Two principals in different currencies and of equal value are exchanged at the start date $t_{0}$ 2. At settlement dates, interest will be paid and received in different currencies and according to the agreed interest rates. 3. At the end date, the principals are re-exchanged at the same exchange rate.  

A simple example is the following. 100,o0o,o00 euros are received and against these $100,000,000e_{t_{0}}$ dollars are paid, where the. $e_{t_{0}}$ is the "current"' EUR/USD exchange rate. Then, 6-month LIBOR-based interest payments are exchanged twice. Finally, the principal amounts are exchanged at the end date at the same exchange rate $e_{t_{0}}$ , even though the actual exchange rate $e_{t_{2}}$ at time $t_{2}$ may indeed be different than. $e_{t_{0}}$ . See Figure 6.9.  

![](fa601e5bf4f143df9c3aa72651bc9eb7a0e2ca81bf5b413df78eaaa6f0b50038.jpg)  

# FIGURE 6.9  

Simple currency swap.  

![](e02a0a8011b96e249879f3205b409e70569803cedda8157afe54c5bf70daa755.jpg)  

# FIGURE 6.10  

FX swap.  

The FX swap for the same period is shown in Figure 6.10. Here, we have no interim interest payments, but instead the principals are re-exchanged at a different exchange rate equal to  

$$
f_{t_{0}}=e_{t_{0}}\frac{1+L_{t_{0}}^{\mathrm{USA}}\delta}{1+L_{t_{0}}^{\mathrm{EUR}}\delta}
$$  

Why this difference? Why would the same exchange rate be used to exchange the principals at. start and end dates of a currency swap while different exchange rates are used for an FX swap?  

We can look at this question from the following angle. The two parties are exchanging currencies for a period of 1 year. At the end of the year, they are getting back their original currency  

But during the year, the interest rates in the two currencies would normally be different. This difference is explicitly paid out in the case of currency swaps during the life of the swap as interim interest payments. As a result, the counterparties are ready to receive the exact original amounts back. The interim interest payments would compensate them for any interest rate differentials.  

In the case of FX swaps, there are no interim interest payments. Hence, the compensation must. take place at the end date. Thus, the interest payments are bundled together with the exchange of principals at the end date.  

# 6.8.3 ANOTHER DIFFERENCE  

Looked at from a financial engineering perspective, the currency swap is like an exchange of two FRNs with different currencies and no credit risk. The FX swap, on the other hand, is like an exchange of two zero-coupon bonds in different currencies.  

Because the LIBOR rates at time $t_{1}$ are unknown as of time $t_{0}$ , the currency swap is subject to slightly different risks than FX swaps of the same maturity. Note that FX and currency swaps are in principle subject to significantly more exposure to counterparty risk than are interest rate swaps, due to the exchange of notional amounts in FX and currency swaps..  

# 6.8.4 USES OF CURRENCY SWAPS  

Although there are structural differences between FX and currency swaps, the former basically serve the same economic purpose as the latter, except for the exchange of (floating) interest rates during the contract term. Financial institutions and their clients, including multinational corporations involved in foreign direct investment, use currency swaps to fund foreign currency investments. Other uses involve converting currencies of liabilities, particularly by issuers of bonds denominated in foreign currencies, as we will see in an example at the end of the chapter.  

# 6.8.5 RELATIVE SIZE AND LIQUIDITY OF FX SWAP AND CURRENCY SWAPMARKETS  

We discussed similarities and differences between FX and currency swaps above. Which instrument is more widely used and more important in practice? FX swaps account for a much larger proportion of FX market turnover than currency swaps. In 2013, the FX swap market was about 40 times larger than the currency swap market. According to the BIS Triennial Central Bank Survey 2013, FX swaps remained the most actively traded FX instrument in 2013 and their daily volume of 2.2 trillion accounted for $42\%$ of all FX-related transactions. Spot FX transactions and outright forward transactions made up $37\%$ and $12\%$ , respectively, of FX market turnover. In comparison, currency swaps contribute only a small share of FX turnover. Currency swap turnover stood at $\$54$ billion per day, or. around $1\%$ of the total. FX swaps remain most liquid at maturities below 1 year, but FX swap turnover has recently been growing for transactions with longer maturities. In contrast to FX swaps, most currency swaps are long term with maturities ranging from 1 to 30 years. The reason for this is that the currency swap maturity reflects the maturity of the transactions that they are funding.  

# 6.8.6 THE EFFECT OF THE GFC ON THE FX MARKET, MARGINS, AND CLEARING  

As we saw above, the advantages of FX forward and swaps are linked to their relatively high liquidity and low cost. During the GFC, there were significant deviations from CIRP, i.e., the FX swap-implied USD rates and the LIBOR rates for major currencies such as the euro and pound sterling diverged. This has been partly attributed to European financial institutions that required USD but faced increasing concerns about their creditworthiness and counterparty risk in dollar interbank markets. As a result, these institutions used the FX swap market to raise dollars using both euro and pound sterling as funding currencies, causing a shift toward one-sided order flow in the FX swap market.  

The GFC took a toll on volumes in FX derivatives, but the regulatory overhaul of the financial system that followed the crisis has left the FX derivatives market largely unchanged due to exemptions that were granted. On November 16, 2012, the US Department of the Treasury issued its final determination that exempts FX swaps and forwards from mandatory derivative requirements, including central clearing and exchange trading. Following the footsteps of the BIS and the US Treasury, on April 14, 2014, European supervisory authorities proposed to exempt uncleared FX swaps and forwards from initial margin requirements. The EU proposals envisage that users of the FX swaps and forward market will only have to post variation margin on these trades, rather than putting up hefty initial margins as well, leaving these instruments less capital-intensive than other asset classes and boding well for liquidity and financial engineering applications in this market.  

# EXAMPLE  

While participants to an interest rate swap might be paying variation margin on a trade for one or two decades, trade duration in FX is typically much shorter. Of the current gross notional amount of FX swaps and forward in the EU, E5.7 trillion has a maturity of less than 6 months, and only 1.2 trillion stretches out over 6 months. The consultation paper estimates that only. $I\delta\%$ of all OTC FX trades will be processed. through central counterparties. The figure for rates trades is expected to be $55\%$ , and for credit $62\%$ Forex market-makers have already begun offering replication products to clients, which mimic the effect of rates or credit hedges but at a fraction of the cost..  

FX week (April 16, 2014).  

As the above reading illustrates the cost advantages implied by lower margin requirements for FX forwards and swaps have already had an impact on financial engineering practice. They have. led market makers at major dealers to explore cross-hedges in the form of FX products. Clients, such as investors or banks, that have an incentive to hedge interest rate or credit risk may face higher capital charges and costs on such hedges. If FX products can be devised by dealers that mimic interest rate or credit hedges due to higher correlations with these markets, this can be a more cost-efficient hedge solution for clients and a new revenue stream for dealers. The example also illustrates the continuing trends toward financial engineering solutions involving multiple asset classes and asset class correlations.  
