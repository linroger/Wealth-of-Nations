
# **Introduction**

In modern financial theory, **no-arbitrage pricing** and **risk-neutral valuation** form the cornerstone for valuing derivative instruments. _No-arbitrage_ means there are no opportunities to make a riskless profit with zero net investment – put simply, markets adjust so that no “free lunch” is possible . Under this principle, the price of any financial instrument is constrained by the _law of one price_: two portfolios with identical future payoffs must have the same current price. The **fundamental theorem of asset pricing** formalizes this: a market is arbitrage-free if and only if there exists at least one **risk-neutral probability measure** (also called an equivalent martingale measure) under which discounted asset prices follow a martingale (have _fair game_ expected changes) . Intuitively, a _risk-neutral measure_ is a set of probabilities such that all assets earn the risk-free rate __MASK_3_1__ – investors are “indifferent to risk” under this measure, so expected returns in the pricing model equal __MASK_3_2__. Pricing derivatives in an arbitrage-free market can thus be done by taking _expected payoffs under the risk-neutral probabilities and discounting at the risk-free rate_. This is the essence of **risk-neutral pricing** .

  

**Risk-Neutral Valuation:** If __MASK_3_3__ is a payoff at future time __MASK_3_4__, and __MASK_3_5__ is the discount factor (for constant __MASK_3_6__), then the no-arbitrage price at time 0 is given by the discounted risk-neutral expectation: __MASK_2_0__ where __MASK_3_7__ denotes expectation under the risk-neutral measure __MASK_3_8__. For example, the no-arbitrage forward price __MASK_3_9__ of an asset for delivery at time __MASK_3_10__ must equal __MASK_3_11__ grown at __MASK_3_12__, so __MASK_3_13__ (we will derive this shortly). Similarly, the no-arbitrage price of a call option is __MASK_3_14__ . These results hold _regardless of investors’ risk aversion_, relying only on arbitrage arguments and replication. In a **complete market** (one where every payoff can be replicated by trading underlying securities), the risk-neutral measure is unique, and thus derivative prices are uniquely determined by no-arbitrage.

  

**Replication and Pricing:** No-arbitrage pricing can be approached via two dual perspectives: (1) constructing a **replicating portfolio** that perfectly replicates the derivative’s payoff and equating its cost to the derivative’s price (the classic approach used in the Black–Scholes derivation), or (2) directly computing the **risk-neutral expected payoff** and discounting. Both approaches yield the same result when markets are arbitrage-free. In continuous time, replication leads to a **pricing PDE** (e.g. the Black–Scholes equation), while risk-neutral valuation uses probabilistic tools (e.g. martingales and expectation under __MASK_3_15__). In practice, risk-neutral pricing is often more convenient for complex derivatives: one assumes the underlying asset’s **drift** under __MASK_3_16__ is the risk-free rate __MASK_3_17__, simulates or analytically evaluates the payoff’s expectation, then discounts. Below, we will apply these principles to price a range of instruments: forwards, futures, bonds, swaps, swaptions, caps, floors, and related derivatives. We develop formal pricing formulas with **step-by-step derivations**, using consistent notation and an academic tone. Key results from foundational texts (Hull, Shreve, Duffie, etc.) and seminal papers (Black–Scholes 1973, Black 1976) are highlighted along the way.

  

**Notation:** We let __MASK_3_18__ denote the spot price of an underlying asset (stock, commodity, etc.) at time __MASK_3_19__. __MASK_3_20__ denotes the price at time __MASK_3_21__ of a zero-coupon bond paying __MASK_3_22__T__MASK_3_23__P(0,T)=e^{-rT}__MASK_3_24__r__MASK_3_25__B(t)__MASK_3_26__B(t)=e^{rt}__MASK_3_27__P(t,T)=e^{-\int_t^T f(t,u),du}__MASK_3_28__r__MASK_3_29__\mathbb{E}^Q[\cdot]__MASK_3_30__Q__MASK_3_31__(x)^+ = \max{x,0}__MASK_3_32__\Phi(\cdot)$ for the standard normal CDF, and will present formulas in **LaTeX** for precision. Each section ends with a summary of key results, and a final section provides further reading from classic references for deeper study.

  

**No-Arbitrage and Risk-Neutral Foundations**

  

Before diving into specific instruments, we review the theoretical foundation that underpins all pricing results: **no-arbitrage arguments** and **risk-neutral pricing**. In an arbitrage-free market, every derivative’s price can be derived by assuming the existence of a risk-neutral measure __MASK_3_2__ under which all asset prices (when discounted) are martingales. Formally, if __MASK_3_3__ is the price process of any tradable asset, then __MASK_2_1__ for all __MASK_3_4__. This implies __MASK_3_5__, meaning the expected growth of __MASK_3_6__ is the risk-free rate. In particular, for any **forward price** __MASK_3_7__ (the price at time __MASK_3_8__ for future delivery at __MASK_3_9__), we must have __MASK_3_10__ (because entering a forward requires no initial outlay, so its discounted value is a martingale). And since __MASK_3_11__ under __MASK_3_12__ when __MASK_3_13__ is constant, we get the classic forward pricing formula __MASK_3_14__ . More generally, the _First Fundamental Theorem of Asset Pricing_ guarantees that _no arbitrage __MASK_3_15__ existence of a risk-neutral measure_ , so we can confidently use risk-neutral expectations for pricing as long as we rule out arbitrage.

  

**State Prices and DF:** Another useful viewpoint is via **state-price deflators** or **Arrow–Debreu prices**. Let __MASK_3_16__ be the time-__MASK_3_17__ price of a security paying __MASK_3_18__T__MASK_3_19__\xi_T__MASK_3_20__X_T__MASK_3_21__V_0 = \mathbb{E}[\xi_T X_T]__MASK_3_22__\xi_T = e^{-rT} \frac{dQ}{dP}__MASK_3_23__\mathbb{E}[\xi_T X_T]__MASK_3_24__e^{-rT}\mathbb{E}^Q[X_T]$. Thus risk-neutral pricing is effectively a change of measure that embeds the discount factor. All methods – replication, state prices, risk-neutral expectation – yield the same no-arbitrage price if applied correctly.

  

**Pricing Algorithm (Monte Carlo):** While analytical formulas will be derived for each instrument, it’s worth noting a general algorithm for pricing via simulation, to illustrate risk-neutral valuation in practice:

__MASK_0_0__

As __MASK_3_25__, __MASK_3_26__ converges to the true no-arbitrage price __MASK_3_27__. This algorithm underscores that once we specify dynamics under __MASK_3_28__, pricing is “just” an expectation – albeit one often computed via elegant math rather than brute force.

  

With these foundations in mind, we now proceed to analyze and derive pricing formulas for specific instruments, starting with forward and futures contracts.

  

**Forward and Futures Contracts**

  

**Forward Contracts:** A **forward contract** is an agreement entered at time __MASK_3_29__ to buy or sell an underlying asset for a fixed **forward price** __MASK_3_30__ at a specified future date __MASK_3_31__. For example, a gold forward might lock in the purchase of 1 oz. of gold at __MASK_3_32__ dollars, with delivery in 3 months. Importantly, no money changes hands initially for a forward (ignoring any collateral), so the contract’s initial value is set to zero by no-arbitrage. We consider a forward from the perspective of the **long** side (buyer at maturity) unless stated otherwise.

  

**Forward Price Derivation:** To find the arbitrage-free forward price __MASK_3_33__ at inception, we use a classic arbitrage argument under the assumption of constant risk-free rate __MASK_3_34__ and no carrying costs or income on the asset. Let __MASK_3_35__ be the current spot price of the underlying. Consider two strategies starting at time 0 and ending at time __MASK_3_36__:

• **Strategy A (Synthetic Forward):** Borrow __MASK_3_37__ dollars at the risk-free rate __MASK_3_38__ (so owe __MASK_3_39__ at __MASK_3_40__) and buy one unit of the asset now for __MASK_3_41__. This results in owning the asset at __MASK_3_42__ with a net outflow at maturity of __MASK_3_43__.

• **Strategy B (Forward):** Enter a long forward contract to buy one unit at time __MASK_3_44__ for the forward price __MASK_3_45__. No cash flow now, and pay __MASK_3_46__ at __MASK_3_47__ to receive the asset.

  

At time __MASK_3_3__, both strategies yield the same asset. Strategy A’s net cost at __MASK_3_4__ is __MASK_3_5__ (loan repayment), while Strategy B’s net cost is __MASK_3_6__. For no arbitrage, these total costs must be equal – otherwise one could profit by choosing the cheaper strategy and shorting the more expensive one. Thus we require: __MASK_2_0__ If __MASK_3_7__ were higher, one could short the forward (lock in selling at __MASK_3_8__), and execute Strategy A (borrow and buy asset) to deliver into the forward, pocketing a riskless profit __MASK_3_9__ . If __MASK_3_10__ were lower, one could do the opposite: short-sell the asset and invest the proceeds __MASK_3_11__ at __MASK_3_12__, and take a long forward to buy back at __MASK_3_13__, yielding arbitrage profit __MASK_3_14__ at __MASK_3_15__ . In summary, **the forward price must equal the future value of the spot price** under no-arbitrage (when the asset has no income or storage cost).

  

More generally, if the underlying asset provides cash flows or has storage costs, the forward pricing formula adjusts for the **cost of carry**. For instance, if the asset pays a continuous dividend yield __MASK_3_16__ (or foreign interest rate in the case of a currency), then the forward price is: __MASK_2_1__ which subtracts the present value of dividends from the cost . If the asset yields a known cash income of present value __MASK_3_17__ over __MASK_3_18__, then __MASK_3_19__; whereas if there are known storage costs with present value __MASK_3_20__, then __MASK_3_21__. All of these are derived by constructing arbitrage strategies that include the income or cost streams appropriately (treating dividends like a negative cost, and storage as a positive cost). As a special case, a **forward rate agreement (FRA)** – a forward contract on an interest rate – will have a forward rate determined by the difference between borrowing and lending (we discuss FRAs implicitly when covering swaps, as a swap is essentially a string of FRAs).

  

**Forward Value During the Contract:** Once a forward is entered at the fair price __MASK_3_22__, its **value** at inception is zero to both long and short. However, as the underlying price moves and time passes, the forward contract acquires a non-zero **mark-to-market value** (the amount one side would pay to exit the contract). Suppose at time __MASK_3_23__ (before maturity) the underlying spot is __MASK_3_24__ and the forward price for maturity __MASK_3_25__ (for a new contract) is now __MASK_3_26__. Consider a forward contract struck at the original price __MASK_3_27__. The **forward contract value** to the long at time __MASK_3_28__ is the difference between locking in purchase at __MASK_3_29__ and the current fair price __MASK_3_30__, appropriately discounted. Specifically, the long forward’s time-__MASK_3_31__ value __MASK_3_32__ is:

__MASK_2_2__

assuming continuous compounding. This can be derived by recognizing that a forward can be replicated by holding the underlying (__MASK_3_33__) and borrowing __MASK_3_34__ (so that __MASK_3_35__ with interest will be paid at __MASK_3_36__) . The difference __MASK_3_37__ is the net value. When __MASK_3_38__ (forward price is reset to fair), this value is zero (as expected). If __MASK_3_39__ is less than the current fair forward price, the long forward is “in the money” (positive value), since they locked in a cheaper purchase than the market forward; if __MASK_3_40__ is above market __MASK_3_41__, the forward has negative value to the long.

  

**Example:** If you entered a 6-month forward to buy a stock at __MASK_3_42__ and after 3 months the stock price is __MASK_3_43__ with 3-month remaining forward price __MASK_3_44__ (assuming some dividends or rates), then the value of your forward contract at 3 months is __MASK_3_45__. If __MASK_3_46__, that’s simply __MASK_3_47__ (you’d have a $5 gain, since you locked in at 100 while a new forward costs 105).

  

**Futures Contracts:** A **futures contract** is similar to a forward in that it obligates the purchase or sale of an asset at a future date for a set price. However, futures are exchange-traded, standardized, and **marked-to-market daily**. Mark-to-market means that gains and losses on a futures position are settled in cash each day, and the futures price is reset to a new level until delivery. Despite these differences, if interest rates are constant and there are no other frictions, the **forward price equals the futures price** for the same maturity . Intuitively, with deterministic __MASK_3_48__, the interim cash flows from marking-to-market can be reinvested at the risk-free rate, leaving no difference in present value.

  

When interest rates are **stochastic**, forward and futures prices can diverge slightly. The daily settlement feature of futures means that if asset price movements are positively correlated with interest rate changes, a long futures tends to earn gains when rates are high (which can be reinvested at a high rate) and losses when rates are low, making the futures more attractive than a forward. Conversely, negative correlation makes forwards slightly more valuable. In fact, **if __MASK_3_1__ then futures price __MASK_3_2__ forward price; if __MASK_3_3__ then futures __MASK_3_4__ forward** . These differences are second-order in many cases, and practitioners often assume forward __MASK_3_5__ futures price unless dealing with long-dated contracts or significant rate volatility. We will generally not distinguish between forward and futures prices in the formulas below (taking that assumption, or using __MASK_3_6__ for both), unless noted.

  

**Pricing via Risk-Neutral Expectation:** The forward pricing result can be alternatively obtained by risk-neutral valuation. Under the risk-neutral measure __MASK_3_7__, the **expected spot price** at time __MASK_3_8__ grows at rate __MASK_3_9__: __MASK_3_10__. Because a forward contract has zero initial cost, its forward price must satisfy __MASK_3_11__ (otherwise an arbitrage via long/short forward vs. underlying would exist). Thus __MASK_3_12__, consistent with our arbitrage derivation. In fact, we can express the _time-__MASK_3_13__ forward price_ as __MASK_2_0__ which again yields __MASK_3_14__ in the simple case. For futures, because of daily settlement, one shows __MASK_3_15__ (the expectation under __MASK_3_16__ without discounting, since each day’s gains are realized immediately). If __MASK_3_17__ is constant, this equals the forward price after accounting for discounting day by day, but if __MASK_3_18__ is random, __MASK_3_19__ in general, hence forward __MASK_3_20__ futures in that scenario.

  

**Summary (Forwards/Futures):** A forward contract’s no-arbitrage delivery **price** at inception is __MASK_3_21__ (where __MASK_3_22__ is storage cost and __MASK_3_23__ yield). The **value** of an existing forward (long position) is __MASK_3_24__, which at __MASK_3_25__ reduces to __MASK_3_26__ when __MASK_3_27__. Futures prices are generally equal to forward prices under the simple assumptions of constant interest rates and no correlations. Both forward and futures pricing illustrate that the expectation under the risk-neutral measure – adjusted for any cost-of-carry – determines the fair price. These instruments have linear payoffs and thus are easier to price; we now move to fixed income instruments where interest rates play a central role.

  

**Zero-Coupon Bonds and the Term Structure**

  

A **zero-coupon bond** (or **discount bond**) maturing at date __MASK_3_28__ is the simplest fixed-income instrument: it pays a single unit of currency (e.g. __MASK_3_29__T__MASK_3_30__P(t,T)__MASK_3_31__t__MASK_3_32__P(T,T)=1__MASK_3_33__P(t,T)__MASK_3_34__y(t,T)__MASK_3_35__T__MASK_3_36__P(t,T)=e^{-y(t,T),(T-t)}__MASK_3_37__y(0,T)__MASK_3_38__T__MASK_3_39__T \mapsto y(0,T)$ is the initial yield curve.

  

**No-Arbitrage for Bonds:** Bonds with different maturities are linked by no-arbitrage: there should be no way to use short-term bonds to arbitrage long-term bonds and vice versa. In practice, an entire yield curve is fitted to market prices of bonds, Treasury bills, swaps, etc., to ensure consistency. A common procedure is **bootstrapping**: starting from the shortest maturities (where yields are directly observed) and solving for longer-term discount factors that match observed coupon bond prices. A **coupon bond** paying semiannual coupons, for example, can be seen as a portfolio of zero-coupon bonds (each coupon and principal is a cash flow at a known date). No-arbitrage demands that the bond’s price equals the sum of the present values of each cash flow using the appropriate zero-coupon rates for each period. If not, an arbitrageur could strip the bond into zeros or reconstitute it to exploit mispricings. Thus, _coupon bond pricing requires a consistent set of discount factors __MASK_3_40__ for all cash flow dates __MASK_3_41___.

  

In a deterministic interest rate environment, __MASK_3_2__ (with __MASK_3_3__ constant) or more generally __MASK_3_4__ for a time-varying rate __MASK_3_5__. Under stochastic interest rates, the price is given by a risk-neutral expectation:

__MASK_2_0__

which is the discounted expected value of __MASK_3_6__P(t,T)__MASK_3_7__P(0,T)$, or equivalently zero rates, as inputs.

  

**Forward Rates:** A useful derived quantity is the **forward interest rate** for borrowing between __MASK_3_8__ and __MASK_3_9__ as seen today. Denoted __MASK_3_10__, it is defined via the relation

__MASK_2_1__

so that __MASK_3_11__ is the rate that makes an investment from __MASK_3_12__ to __MASK_3_13__ equivalent to investing until __MASK_3_14__ then rolling into a loan from __MASK_3_15__ to __MASK_3_16__. Solving, __MASK_3_17__. If interest rates are continuous, this is also related to the instantaneous **forward rate** __MASK_3_18__ via __MASK_3_19__. In a no-arbitrage setting, forward rates extracted from bond prices are consistent with forward contracts on interest rates (FRAs). Indeed, the no-arbitrage price of a **forward rate agreement** that fixes the rate for __MASK_3_20__ at __MASK_3_21__ can be found by considering lending/borrowing strategies in bonds: one can show the present value of the payoff is __MASK_3_22__ (which is analogous to the forward contract value formula __MASK_3_23__, with __MASK_3_24__ replaced by forward rate and discount by __MASK_3_25__). We won’t derive FRA pricing in detail, as it will be subsumed by the discussion of swaps.

  

**Risk-Neutral Pricing for Bonds:** By treating the bond as the asset and the money-market account as numeraire, one can derive that _each __MASK_3_26__ must equal the risk-neutral expectation of its payoff 1, discounted by __MASK_3_27__._ This yields the earlier expectation formula. It also implies that trading strategies involving bonds must satisfy no-arbitrage; for instance, a **rolling over strategy** of short-term bonds cannot outgun a long-term bond if the forward rates are set properly.

  

**Summary (Bonds):** Zero-coupon bond prices __MASK_3_28__ encode the discount factors for future cash flows and determine the term structure of interest rates. Arbitrage considerations enforce that coupon bond prices equal the sum of zero-coupon bond equivalents. Forward interest rates are derived from zero prices and coincide with FRA rates under no-arbitrage. We now use these concepts as building blocks for pricing **interest rate swaps**, which are essentially exchanges of fixed and floating cash flow streams and heavily depend on the term structure.

  

**Interest Rate Swaps**

  

An **interest rate swap** is a derivative in which two parties exchange cash flows of two different types of interest payments on a notional principal amount. The most common type is a **plain vanilla interest rate swap**: one party pays a fixed interest rate __MASK_3_29__ on the notional and receives a floating rate (such as LIBOR or SOFR) from the other party (who does the opposite). These payments occur periodically (e.g. semiannually) over a term of the swap. No principal is exchanged in a vanilla swap; only the net interest difference is paid each period. Swaps allow conversion between fixed-rate and floating-rate exposures and are fundamental in interest rate risk management.

  

**Swap as Exchange of Bonds:** A useful way to conceptualize a fixed-for-floating swap is as the difference between two bond positions. Consider a **payer swap** (the party who pays fixed and receives floating): this position can be replicated by (i) **short** a fixed-rate bond (paying coupons __MASK_3_5__ and principal) and (ii) **long** a floating-rate note of the same notional and maturity. A floating-rate note (FRN) typically pays the benchmark rate (e.g. LIBOR) each period and is reset such that it always trades at par at coupon dates (assuming no credit risk). Thus, at coupon reset dates, the FRN’s value returns to the notional. If we assume the floating leg is tied to a risk-free benchmark, the present value of receiving floating over each period plus getting back notional at end is just the notional amount (because one could just hold that cash risk-free). In fact, at swap initiation (time 0), the **present value of the floating leg** (for the full swap term) equals the notional principal _by construction_ when using the current forward rates. Meanwhile, the present value of the fixed leg is the present value of a fixed coupon bond paying __MASK_3_6__ per period plus principal. For the swap to have zero initial value (a **par swap**), these two present values must be equal. Therefore, the fixed rate __MASK_3_7__ is chosen such that the _fixed leg PV = notional_ (since the floating leg PV is notional). This unique rate is called the **swap par rate** __MASK_3_8__ for the swap’s maturity __MASK_3_9__.

  

**Swap Pricing (at Initiation):** Suppose the swap pays fixed __MASK_3_10__ at times __MASK_3_11__ (with __MASK_3_12__) and floating payments of the prevailing forward rate for each period (so effectively the floating leg will realize forward rates in expectation). Let __MASK_3_13__ be year-fractions for each period. The present value of the fixed leg (per notional $1) is:

__MASK_2_0__

which is the coupon payments plus the notional returned at __MASK_3_14__. (We include __MASK_3_15__ as the PV of receiving __MASK_3_16__P(0,T_i)$ terms could be interpreted as including the principal.) The present value of the floating leg is:

__MASK_2_1__

which telescopes to __MASK_3_17__ (since __MASK_3_18__). In other words, __MASK_3_19__ for __MASK_3_20__PV_{\text{fixed}} = PV_{\text{float}}__MASK_3_21__R$:

__MASK_2_2__

Thus the **par swap fixed rate** is

__MASK_2_3__

This __MASK_3_22__ is the_ **_swap rate_** _that makes the swap’s initial value zero_ _. Each __MASK_3_23__ is readily obtained from the zero curve. For example, if __MASK_3_24__ years with semiannual payments, __MASK_3_25__ is such that the PV of five years of semiannual __MASK_3_26__ payments plus __MASK_3_27__ equals 1. If yield curve is flat at, say, 3% continuously, then __MASK_3_28__ as expected. If the yield curve is upward sloping, __MASK_3_29__ will be higher than the short rate but lower than long-term rates, roughly an average.



**Swap Valuation (After Initiation):** Once a swap is in place, its value may become positive or negative to a party as rates change. The **value of a swap** at time __MASK_3_30__ (to the fixed-rate payer) can be computed as the difference between the present value of remaining floating payments and remaining fixed payments. Let __MASK_3_31__ be the original fixed rate on the swap, and let __MASK_3_32__ be the current par swap rate for the remaining term (i.e. the swap rate one would get on a new swap from __MASK_3_33__ to __MASK_3_34__). Then the **swap value** to the fixed payer (who pays __MASK_3_35__) at __MASK_3_36__ (per $1 notional) is:

__MASK_2_4__

where __MASK_3_0__ is the last payment date passed (so payments __MASK_3_1__ to __MASK_3_2__ remain) . Here __MASK_3_3__ is the **annuity factor** (present value of \__MASK_3_4__R_{\text{fixed}} > R_{\text{new}}__MASK_3_5__R_{\text{fixed}} < R_{\text{new}}__MASK_3_6__V_t__MASK_3_7__V_t^{\text{receiver}} = (R_{\text{fixed}} - R_{\text{new}}(t)) \sum \Delta_i P(t,T_i)__MASK_3_8__R_{\text{fixed}}__MASK_3_9__R_{\text{new}}__MASK_3_10__R_{\text{fixed}}__MASK_3_11__(R_{\text{new}} - R_{\text{fixed}})__MASK_3_12__\sum \Delta_i P(t,T_i)$ .

  

Another way: one can imagine terminating (or initiating an offsetting swap) at time __MASK_3_13__. To do so, one would pay/receive the net present value difference. Thus __MASK_3_14__ can be found by computing __MASK_3_15__ (for the same floating leg), which yields the above result since __MASK_3_16__ would equal the floating leg’s PV.

  

**Example:** Suppose two years ago you entered a 7-year swap to pay fixed 3% and receive 6-month LIBOR, on __MASK_3_17__\sum_{i=1}^{10} \Delta_i P(0,T_i) = 4.8161__MASK_3_18__{} R_{\text{new}} = (1 - P(0,5))/4.8161 = 1.59\%__MASK_3_19__(0.0159 - 0.03) \times 4.8161 \times \__MASK_3_20__ . It’s negative because you are paying 3% which is high relative to the new 1.59% market rate – you’d have to pay __MASK_3_21__6.79MM position.

  

**Risk-Neutral View:** Under a no-arbitrage pricing measure, each forward LIBOR rate (the underlying for each floating payment) has an expectation equal to its forward value. A par swap initially has zero value because the fixed leg’s promised payments are set exactly equal to the sequence of implied forward floating payments. As time evolves, the realization of interest rates will make the fixed leg too high or too low relative to forward rates, creating value. One could price a swap by modeling the joint evolution of the short rate or forward rates and taking expectations of the net present value of payments, but the linearity of swap payoffs allows the simpler “deterministic PV” approach above. Indeed, a vanilla swap has _no optionality_, so its price is just the difference of two bond portfolios, and one can compute it by deterministic cashflow discounting with the current zero curve (no need for complex optionality modeling). This is why swaps are often used to infer the _risk-free zero curve itself_ from swap rates in the market.

  

**Summary (Swaps):** The fixed leg of a swap is priced as an annuity whose rate is set such that its initial PV equals the notional (the floating leg’s PV). The swap par rate __MASK_3_22__ is given by the ratio of “1 minus last discount factor” to “sum of discount factors” . The mark-to-market value of a swap during its life is proportional to the difference between the original fixed rate and current par rate, times the remaining annuity factor . Swaps are thus very convenient to price given a yield curve, and they facilitate the market’s bootstrapping of that curve. Next, we turn to **swaptions** – options on swaps – which introduce optionality and require a further step of risk-neutral valuation (often using the Black model).

  

**Swaptions (Swap Options)**

  

A **swaption** is an option granting the right, but not the obligation, to enter an interest rate swap at a specified future date. There are two types: a **payer swaption** gives the right to _pay fixed, receive floating_ (i.e. become the fixed-rate payer in a swap), while a **receiver swaption** gives the right to _receive fixed, pay floating_. For example, a 5Y5Y payer swaption is an option (exercisable in 5 years) to enter a 5-year swap as fixed payer. Swaptions are widely used to hedge or speculate on future interest rate moves and to add optionality to swap-based products.

  

**Swaption Payoff:** Consider a payer swaption expiring at time __MASK_3_4__ on a swap that would run from __MASK_3_5__ to __MASK_3_6__ (with coupon dates __MASK_3_7__, __MASK_3_8__, __MASK_3_9__). Let __MASK_3_10__ be the agreed fixed rate (swaption strike). At exercise (time __MASK_3_11__), if the swaption holder chooses to exercise and enter the swap as fixed payer, they will pay fixed __MASK_3_12__ and receive floating. The _market swap rate_ __MASK_3_13__ for that __MASK_3_14__–__MASK_3_15__ swap (par rate at __MASK_3_16__ for maturity __MASK_3_17__) will determine whether exercise is favorable. The **intrinsic value** of a payer swaption at expiry is the present value of the difference between the swap at the market rate __MASK_3_18__ and the swap at the strike __MASK_3_19__, floored at zero (since one wouldn’t exercise if it’s negative). In other words, the payoff is the **swap’s value to the payer** at __MASK_3_20__, clipped at zero:

__MASK_2_0__

times the notional. Here __MASK_3_21__ is the **annuity factor at __MASK_3_22__** (present value at __MASK_3_23__ of __MASK_3_24__= \sum_{i=1}^N \Delta_i e^{-r(T_i-T)}__MASK_3_25__S(T) > K__MASK_3_26__K__MASK_3_27__S(T)__MASK_3_28__(S(T)-K)__MASK_3_29__S(T)\le K__MASK_3_30__\Big(K - S(T)\Big)^+ \sum_{i=1}^N \Delta_i P(T,T_i)__MASK_3_31__K >$ current swap rate, since receiver would then get above-market fixed rate).

  

**Pricing Swaptions:** Swaptions are more complex to price because the payoff depends on the entire set of interest rates at __MASK_3_32__ (through __MASK_3_33__ or the collection of bond prices __MASK_3_34__). A full treatment requires an interest rate model (e.g. Black’s model, Bachelier model, or a short-rate/forward-rate model like Hull–White, LIBOR market model, etc.). However, a common market approach is to use an analog of the Black–Scholes formula known as **Black’s 1976 model** for swaptions . Black’s model assumes the **forward swap rate** __MASK_3_35__ for the underlying swap follows a lognormal process under its appropriate forward measure (with a certain volatility __MASK_3_36__). Under these assumptions, the swaption price can be expressed in closed form, similar to a call option on a forward asset.

  

In Black’s formula for a **payer swaption**, the price at time 0 is given by:

__MASK_2_1__

where:

• __MASK_3_37__ is the **forward swap rate** (today’s par rate for the swap starting at __MASK_3_38__), essentially __MASK_3_39__ for that swap starting in future;

• __MASK_3_40__ is the **annuity factor** (present value of $1 per swap period, from 0);

• __MASK_3_41__ is the standard normal CDF;

• __MASK_3_42__;

• __MASK_3_43__ is the implied **swaption volatility** (assumed constant);

• __MASK_3_44__ is the swaption expiration.

  

This formula is directly analogous to Black–Scholes: __MASK_3_45__ plays the role of a discount factor and size scaling, __MASK_3_46__ is like a forward price, and __MASK_3_47__ the strike. In fact, it can be derived by noting the swaption payoff is __MASK_3_48__ for payer, and treating __MASK_3_49__ as approximately constant (or using the annuity as numeraire, which leads to __MASK_3_50__ being martingale under the _swap measure_). Black’s 1976 paper originally presented the formula for options on futures , but it’s applied to swaptions by analogous reasoning. If we account for discrete compounding conventions, a more precise formula is:

__MASK_2_2__

where __MASK_3_51__ is payments per year (this factor __MASK_3_52__ is essentially __MASK_3_53__ in another guise) . The receiver swaption price by put-call parity is

__MASK_2_3__

or simply the payer formula with __MASK_3_54__ and __MASK_3_55__ swapped in sign inside the __MASK_3_56__ arguments.

  

**Modeling Considerations:** The risk-neutral pricing of swaptions can also be done using _Jamshidian’s trick_ in one-factor models (decomposing a swaption into a portfolio of bond options), or Monte Carlo under a LIBOR market model where each LIBOR forward rate is lognormal (the industry standard for consistent caplet and swaption volatilities). The Black swaption formula is widely used to quote swaption implied volatilities. It assumes lognormal swap rate distribution; in low-rate or negative-rate environments, sometimes a normal assumption (Bachelier model) is used instead.

  

**Cap/Floor Parity with Swaptions:** Interestingly, there is a connection between swaptions and interest rate caps/floors (described next) via parity relationships. A payer swaption (right to pay fixed) can be shown to be equivalent to a portfolio of caplets (a cap) with the same strike, and a receiver swaption equals a portfolio of floorlets (a floor), under certain assumptions. Alternatively, one can say: **Cap – Floor = Swap**, which implies by arbitrage that **Cap price – Floor price = PV of fixed-floating difference** . Indeed, if you hold a cap and short a floor (same strike __MASK_3_1__), you will receive payments whenever LIBOR __MASK_3_2__ is positive (from the cap) and pay when __MASK_3_3__ is positive (due to the short floor), which net replicates paying floating vs __MASK_3_4__. This is exactly a swap with fixed __MASK_3_5__. Thus, **Cap(K) – Floor(K) = PV(\text{receive floating – pay fixed __MASK_3_6__})**, which is the par swap value if __MASK_3_7__ equals the par rate (zero at inception) . If __MASK_3_8__ differs from par, the difference in cap and floor prices equals the market value of a payer swap with rate __MASK_3_9__. These relationships ensure consistency across the pricing of caps, floors, and swaptions.

  

**Summary (Swaptions):** Swaptions add optionality to swaps, with payoffs contingent on future swap rates. They are commonly priced via the **Black-76 model**, treating the swap’s fixed rate as the underlying instrument . The payer swaption formula resembles a call option on the forward swap rate, scaled by the annuity factor. While we provided Black’s formula (ubiquitous in practice), rigorous pricing can be done with term structure models under the risk-neutral measure. Swaption contracts allow hedging of interest rate volatility and are closely related to caps and floors, which we discuss next.

  

**Caps and Floors (Interest Rate Options)**

  

An **interest rate cap** is essentially a portfolio of call options on a short-term interest rate, often designed to limit a borrower’s floating interest payments. Conversely, an **interest rate floor** is a portfolio of put options on a rate, limiting a lender’s minimum received rate. Caps and floors are quoted in terms of their strike rate __MASK_3_10__ (the cap rate or floor rate) and typically reference a LIBOR-like index over a schedule of reset dates.

  

**Cap Definition:** A cap provides payoff in each period the reference interest rate exceeds __MASK_3_11__. For example, consider a cap on 3-month LIBOR with quarterly reset dates __MASK_3_12__. At each reset __MASK_3_13__ (when the new LIBOR __MASK_3_14__ for __MASK_3_15__ is determined), the cap will, at the next payment date __MASK_3_16__, pay the excess interest: __MASK_3_17__, where __MASK_3_18__ is the day-count fraction for that period . In other words, if LIBOR ends up higher than __MASK_3_19__, the caplet pays the difference * times the period length and notional (the additional interest cost). If LIBOR __MASK_3_20__, the caplet pays zero (the borrower’s rate is at or below the cap). The collection of these call-option-like payoffs for __MASK_3_21__ to __MASK_3_22__ constitutes the cap. Each individual option is called a **caplet**.

  

**Floor Definition:** Similarly, a floor pays __MASK_3_23__ on each period __MASK_3_24__ – paying out when LIBOR falls below __MASK_3_25__, thus guaranteeing a minimum rate __MASK_3_26__ to the investor. Each piece is a **floorlet** (put option on the rate).

  

**Caplet Pricing:** Each caplet is effectively a European call option on the interest rate __MASK_3_27__ set at time __MASK_3_28__ for payment at __MASK_3_29__. To price a caplet, one usually uses a **forward measure**: for caplet on __MASK_3_30__, it is convenient to use the __MASK_3_31__-forward measure (with numeraire __MASK_3_32__). Under this measure, the forward LIBOR for that period, __MASK_3_33__, behaves like a martingale. Black’s model assumes __MASK_3_34__ (or equivalently __MASK_3_35__) is lognormal under this forward measure with volatility __MASK_3_36__. Then the **Black formula for a caplet** (at time 0) is:

__MASK_2_0__

where __MASK_3_37__ is the current forward rate for __MASK_3_38__, and

__MASK_3_39__ (assuming caplet decision is effectively at __MASK_3_40__). We also multiplied by __MASK_3_41__ because the payoff is __MASK_3_42__ . This formula is directly analogous to an option on a forward rate agreement. The factor __MASK_3_43__ is the discount to the payment date. In practice, market quotes cap implied volatilities for different maturities and strikes, and uses Black’s formula to price each caplet accordingly (with interpolation for intermediate).

  

A key point: Because each caplet payoff occurs at __MASK_3_2__ but is determined by __MASK_3_3__ fixed at __MASK_3_4__, using __MASK_3_5__ as numeraire simplifies the payoff to something like __MASK_3_6__ times a simple difference . The standard Black formula accounts for the required convexity adjustment via the __MASK_3_7__ factor and discounting.

  

**Cap = Sum of Caplets:** The total cap price is the sum of the present values of all its caplets:

__MASK_2_0__

with appropriate __MASK_3_8__ for each caplet expiring __MASK_3_9__ . Similarly a floor price is the sum of floorlets:

__MASK_2_1__

The decomposition into caplets/floorlets is possible because LIBOR resets for different periods are independent under their respective forward measures (in a one-factor setting), and because the payoff is linear in these separate pieces. In multi-factor models, one must be careful, but by definition of a cap as a series of individual options, this additivity holds for pricing.

  

**Cap-Floor Parity:** As mentioned earlier, a long cap and long floor with the same strike __MASK_3_10__ on the same dates replicate a fixed rate guarantee: cap pays when rates above __MASK_3_11__, floor pays when below, so together they ensure you effectively always either receive or pay adjustments to achieve rate __MASK_3_12__. In fact, **Long Cap + Long Floor = Interest Rate Collar** that locks the rate at __MASK_3_13__. The cost of this collar equals the cost of a swap that would pay fixed __MASK_3_14__ (because achieving exactly __MASK_3_15__ payments is a fixed-rate bond). Thus, __MASK_3_16__ (the value of paying fixed __MASK_3_17__ vs floating) . If __MASK_3_18__ is set to the current swap par rate, __MASK_3_19__, so the cap and floor have the same price. This is an important consistency check in interest rate models.

  

**Use Cases:** A cap can protect a borrower with a floating-rate loan by capping the maximum interest rate they pay (beyond which the cap payouts compensate the extra interest). A floor can ensure a minimum interest income for a lender on a floating-rate investment. Caps and floors are often structured with notional amortization schedules to match specific loan principals. They trade actively in the derivatives market (e.g. caps on 3M LIBOR for various maturities), and their implied volatilities form the **volatility surface/skew** for interest rates.

  

**Summary (Caps/Floors):** An interest rate cap is equivalent to a series of European call options on the interest rate for each period (caplets), and a floor is analogous with put options. Under no-arbitrage, the cap’s price is the sum of caplet prices, often computed with Black’s 1976 model . The Black model formulas for caplets are akin to Black–Scholes, with forward LIBOR as underlying and discount bond as numeraire. Caps, floors, and swaps satisfy parity relationships (cap – floor = swap) that must hold to avoid arbitrage. These instruments allow market participants to trade and hedge interest rate volatility and to tailor risk profiles (e.g. a collar strategy, which is long a cap and short a floor, can set an interest rate band).

  

**Conclusion and Further Reading**

  

In these notes, we’ve systematically derived the pricing of various financial instruments – forwards, futures, bonds, swaps, swaptions, caps, and floors – using the twin principles of no arbitrage and risk-neutral valuation. We started from the foundation that in an arbitrage-free market there exists a risk-neutral measure enabling simple expected-value pricing of discounted payoffs . We applied this to determine forward and futures prices, seeing that forward prices are essentially expected future spot prices grossed-up at the risk-free rate. We then covered bond pricing and the term structure, emphasizing how discount factors ensure consistency across maturities. Building on that, we priced interest rate swaps by equating fixed and floating-leg present values , and showed how a swap’s value evolves with changes in the swap rate . Swaptions introduced optionality on swaps, and we presented Black’s formula as a convenient closed-form solution . Finally, we detailed caps and floors, breaking them into caplets/floorlets and again leveraging Black’s model for tractable pricing . Throughout, we highlighted arbitrage strategies and intuitive reasoning (e.g. constructing replicating portfolios or using parity relations) to reinforce why the pricing formulas take the form they do.

  

For further study, the following resources are recommended:

• **John C. Hull – Options, Futures, and Other Derivatives** (often updated, e.g. 10th edition, 2017): A comprehensive text covering derivatives pricing with an intuitive approach. Hull’s chapters on swaps, futures, and options provide concrete examples and additional context (e.g. day-count conventions, collateral, etc.) beyond the idealized formulas.

• **Steven Shreve – Stochastic Calculus for Finance II: Continuous-Time Models (2004)**: This graduate-level text rigorously develops the risk-neutral pricing framework with Brownian motion and martingales. It is an excellent reference for the theoretical foundations (including the Black–Scholes derivation, Girsanov’s theorem, and the fundamental theorems of asset pricing) that underlie the methods used in these notes.

• **Darrell Duffie – Dynamic Asset Pricing Theory (3rd ed., 2001)**: A more abstract and advanced treatment of arbitrage pricing in a general state-space setting. Duffie’s text is ideal for those interested in measure-theoretic foundations and the most general statements of the no-arbitrage pricing theorems, as well as advanced topics like incomplete markets.

• **Fischer Black and Myron Scholes (1973), “The Pricing of Options and Corporate Liabilities,” Journal of Political Economy**: The seminal paper introducing the Black–Scholes formula, which underpins much of risk-neutral option pricing. While focused on equity options, the methodology is foundational for understanding how no-arbitrage arguments can lead to partial differential equations and closed-form solutions.

• **Fischer Black (1976), “The Pricing of Commodity Contracts,” Journal of Financial Economics**: Black’s paper extends Black–Scholes to options on futures, which became the basis for pricing caps, floors, and swaptions (Black–76 model). It’s a short but insightful read to see how the formula we used for swaptions and caplets was originally derived for futures options.

• **Damiano Brigo and Fabio Mercurio – Interest Rate Models: Theory and Practice (2nd ed., 2006)**: A thorough text specifically on interest rate derivatives. It covers the pricing of caps, floors, and swaptions in depth, examining the Black model as well as more sophisticated models (Hull–White, LIBOR Market Model, etc.) for interest rates. This is excellent for understanding the limitations of Black’s model and how one calibrates to cap/floor volatilities and swaption volatilities in practice.

• **Leif B. G. Andersen and Vladimir Piterbarg – Interest Rate Modeling (3-volume set, 2010)**: An advanced and encyclopedic resource on interest rate models, including detailed discussions on swaption pricing, model calibration, and the mathematics of no-arbitrage term structure models. Volume I lays the foundations and vanilla models, while Volume III goes into products and risk management.

• **Harrison & Kreps (1979) and Harrison & Pliska (1981)**: These papers formally develop the concept of equivalent martingale measures and risk-neutral pricing in both discrete and continuous time. They are the classic references for the fundamental theorems of asset pricing in academic finance.

  

By consulting these materials, one can deepen their understanding of both the practical formulas and the theoretical mechanisms behind them. Each of the instruments discussed has further nuances (credit risk, collateralization, multi-curves for different interest rate benchmarks, etc.) which become important in real-world contexts. However, the no-arbitrage, risk-neutral pricing paradigm remains the unifying theme that ensures different market prices all fit into a coherent, arbitrage-free framework.

