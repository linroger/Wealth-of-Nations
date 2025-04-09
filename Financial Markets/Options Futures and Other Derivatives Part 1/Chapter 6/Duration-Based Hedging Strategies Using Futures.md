# 6.4 DURATION-BASED HEDGING STRATEGIES USING FUTURES  

We discussed duration in Section 4.10. Interest rate futures can be used to hedge the yield on a bond portfolio at a future time. Define:.  

$V_{F}$ : Contract price for one interest rate futures contract.   
$D_{F}$ : Duration of the asset underlying the futures contract at the maturity of the futures contract   
$P$ : Forward value of the portfolio being hedged at the maturity of the hedge (in. practice, this is usually assumed to be the same as the value of the portfolio today)   
$D_{P}$ : Duration of the portfolio at the maturity of the hedge..  

If we assume that the change in the forward yield, $\Delta y$ , is the same for all maturities, it is approximately true that  

$$
\Delta P=-P D_{P}\Delta y
$$  

It is also approximately true that  

$$
\Delta V_{F}=-V_{F}D_{F}\Delta y
$$  

The number of contracts required to hedge against an uncertain $\Delta y$ , therefore, is  

$$
N^{*}=\frac{P D_{P}}{V_{F}D_{F}}
$$  

This is the duration-based hedge ratio. It is sometimes also called the price sensitivity hedge ratio.  

When the hedging instrument is a Treasury bond futures contract, the hedger must base $D_{F}$ on an assumption that one particular bond will be delivered. This means that the hedger must estimate which of the available bonds is likely to be cheapest to deliver at the time the hedge is put in place. If, subsequently, the interest rate environment changes so that it looks as though a different bond will be cheapest to deliver, then the hedge has to be adjusted and as a result its performance may be worse than anticipated.  

When hedges are constructed using interest rate futures, it is important to bear in mind that interest rates and futures prices move in opposite directions. When interest rates go up, an interest rate futures price goes down. When interest rates go down, the reverse happens, and the interest rate futures price goes up. Thus, a company in a position to lose money if interest rates drop should hedge by taking a long futures position. Similarly, a company in a position to lose money if interest rates rise should hedge by taking a short futures position.  

The hedger tries to choose the futures contract so that the duration of the underlying. asset is as close as possible to the duration of the asset being hedged. Eurodollar futures tend to be used for exposures to short-term interest rates, whereas ultra T-bond, Treasury bond, and Treasury note futures contracts are used for exposures to longer-. term rates.  

# Example 6.6  

It is August 2 and a fund manager with. $\$10$ million invested in government bonds is concerned that interest rates are expected to be highly volatile over the next 3 months. The fund manager decides to use the December T-bond futures contract to hedge the value of the portfolio. The current futures price is 93-02, or 93.0625. Because each contract is for the delivery of $\$100,000$ face value of bonds, the futures. contract price is. $\$93,062.50$  

Suppose that the duration of the bond portfolio in 3 months will be 6.80 years. The cheapest-to-deliver bond in the T-bond contract is expected to be a 20-year $12\%$ per annum coupon bond. The yield on this bond is currently $8.80\%$ per annum, and the duration will be 9.20 years at maturity of the futures contract.  

# Business Snapshot 6.3 Asset-Liability Management by Banks  

The asset-liability management (ALM) committees of banks now monitor their exposure to interest rates very carefully. Matching the durations of assets and liabilities is sometimes a first step, but this does not protect a bank against nonparallel shifts in the yield curve. A popular approach is known as $G A P$ management. This involves dividing the zero-coupon yield curve into segments, known as buckets. The first bucket might be 0 to 1 month, the second 1 to 3 months, and so on. The ALM committee then investigates the effect on the value of the bank's portfolio of the zero rates corresponding to one bucket changing while those corresponding to all other buckets stay the same.  

If there is a mismatch, corrective action is usually taken. This can involve changing deposit and lending rates in the way described in Section 4.12. Alternatively, tools. such as swaps, FRAs, bond futures, Eurodollar futures, and other interest rate derivatives can be used.  

The fund manager requires a short position in T-bond futures to hedge the bond portfolio. If interest rates go up, a gain will be made on the short futures position, but a loss will be made on the bond portfolio. If interest rates decrease, a loss will be made on the short position, but there will be a gain on the bond portfolio. The number of bond futures contracts that should be shorted can be calculated from equation (6.3) as  

$$
\frac{10,000,000}{93,062.50}\times\frac{6.80}{9.20}=79.42
$$  

To the nearest whole number, the portfolio manager should short 79 contracts.  
