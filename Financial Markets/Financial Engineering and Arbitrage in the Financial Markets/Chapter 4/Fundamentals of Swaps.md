---
tags:
  - fixed_floating_swaps
  - interest_rate_swaps
  - notional_principal
  - swap_fundamentals
  - swap_valuation
aliases:
  - Cross-Currency Swaps
  - Interest Rate Swap
  - Swap Agreements
  - Swap Basics
key_concepts:
  - Dual nature of swaps
  - Exchange cash flows
  - FRA settlement formula
  - Fictitious bonds exchange
  - Fixed vs floating
  - Notional principal
  - String of forwards
  - Swap legs
---

# 4.1 FUNDAMENTALS OF SWAPS  

A swap is a private agreement between two counterparties to exchange two streams of cash flows. Each stream of cash flows, called a swap leg, resembles a coupon and principal flow. on a bond. The swap agreement specifies the principals and coupon formulas for each stream, the exact dates of the cash flow exchanges and the final maturity. Coupon flows can be fixed, floating based on an interest rate reference such as LIBOR, T-Bill or gilt, or floating based on an equity index or a commodity price. The face value or the principal of a swap is referred to. as a notional principal, as it is not necessarily the face value of any real bond, but a reference with which to easily define the coupon formula. The principals for the two sides of the swap. may be unequal or defined in different currencies. In most cases, they are identical. In interest rate swaps, the notional principal for both sides is the same, therefore it is not even exchanged, and the cash flow exchange is simply fixed for floating. In cross-currency swaps, the notional principals are in two different currencies, but have the same value at the original exchange rate. Since their value is usually mismatched by the final maturity of the swap, they are exchanged to preserve the fairness of the swap agreement. Many swaps have deliberately mismatched coupon dates. The fixed side on an interest rate swap commonly pays every 6 or 12 months,. while the floating side is commonly indexed off the 3-month LIBOR and pays quarterly.  

# 4.1.1 The Dual Nature of Swaps  

The fundamental property of the swaps is their dual nature. On one hand, a swap can be viewed as an exchange of two fictitious bonds. In an interest rate swap, one side - one fictitious bond -- is the floating rate leg plus the notional principal, which taken together are identical to a floating rate bond. The other side -- the other fictitious bond  is the fixed leg plus the notional principal, which taken together are identical to a fixed coupon bond. The cash flow formulas for each side are typically set in such a way that neither party owes anything to the other at the outset of the swap. If the fixed coupon is high, then the margin spread added to the floating LIBOR is high, so that the two legs are of equal economic value. If the floating leg is LIBOR flat (no margin), then the fixed rate is computed to ensure that the two sides have the same present value. Such a swap is called a market swap or an on-market swap. The majority of swaps originate that way, but as interest rates or currency rates change over the life of the swap, the swap legs may not have offsetting PVs, or the PVs may be mismatched from the outset. Such swaps are called off-market swaps. Any time the swap is unwound (cancelled) by mutual agreement of the two counterparties, a payment of the mark-to-market is exchanged to cover the off-market value of the swap. The mark-to-market value of the swap reflects the difference in the values of the two fictitious bonds exchanged through the swap.  

The second nature of the swap is as a string of forwards. Instead of analyzing the swap one leg at a time, let us dissect the swap "horizontally,' one cash flow exchange at a time. In an interest rate swap, on each date we exchange a fixed coupon for a floating one times the correct day-count fractions times the face value. Each exchange is identical to the settlement formula of a Forward Rate Agreement (FRA), and can be synthesized with a FRA or almost identically synthesized with a Eurodollar futures contract. In a cross-currency swap, we may, on each. date, exchange a fixed flow in dollars for a fixed flow in euros, computed using the respective side's face value, coupon rate, and day-count fraction. Each exchange is identical to a currency forward, as it simply fixes known amounts in two different currencies, thus fixing the exchange. rate between the two currencies. Viewed this way, an on-market swap is one where the coupon rates on both sides are set relative to each other to make the sum of the present values for all the forwards strung together in a swap equal to zero (some may be positive, some negative). An off-market swap's sum of the PVs will be non-zero, and one counterparty will have to pay the other, depending on the sign of the total PV, in order to enter into a new swap or cancel an existing swap.  

# 4.1.2 Implication for Pricing and Hedging  

The dual nature of swaps profoundly simplifies the valuation and hedging analysis of swaps. We use whichever is easier and more intuitive. If a cross-currency swap is an exchange of two fixed bonds, each denominated in a different currency, we use yield curves in each currency to value each bond, and then use the spot exchange rate to find the difference in value (offmarket or mark-to-market PV), or we solve for one coupon rate in order for that difference to be zero. If we know how to hedge each bond separately, then we know how to hedge the swap, since the swap is equivalent to a long position in one bond and a short position in another. Alternatively, we can value each cash flow exchange as the mark-to-market on a currency forward, and add them to find a total. The hedging then boils down to synthesizing the opposite of each forward to offset exposure. We end up in the same spot. Often we end up with an insight into alternative, economically equivalent, hedging schemes. We can hedge an interest rate swap with one duration-equivalent bond or a strip of Eurodollar futures. We can hedge a cross-currency swap with bonds or Eurocurrency positions in each currency combined. with spot FX trades, or directly in spot and forward FX markets..  

For larger dealers, swap hedging is done on a net basis for entire books of swaps. The cash flows of many swaps in the book may offset each other literally or in economic exposure (e.g. a 5-year bond and 4-year bond with mismatched dates are economically similar). Armed with computed net value sensitivities for the entire book to a variety of liquid hedge instruments, the dealer is in a position to choose the best overall hedge, one that is liquid, easy to alter when a new deal arrives, and easy to undo when unwinds occur. Instead of choosing exact static offsets that once and for all eliminate the risks of the swap, the dealer can save money by hedging dynamically daily changes in the net value of the portfolio, as the portfolio itself changes due to the arrival of unwinds and new deals. The dynamic approach often results in a dramatically smaller overall hedge.  
