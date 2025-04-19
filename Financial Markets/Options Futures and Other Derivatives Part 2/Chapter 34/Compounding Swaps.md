---
tags:
  - '#compounding_swaps'
  - '#fixed_rate'
  - '#floating_rate'
  - '#forward_rate_agreements'
  - '#notional_principal'
  - '#ois_rates'
  - '#sofr'
  - '#swap_valuation'
---
# 34.2 COMPOUNDING SWAPS  

Another variation on the plain vanilla swap is a compounding swap. A hypothetical confirmation for a compounding swap is in Business Snapshot 34.2. In this example there is only one payment date for both the floating-rate payments and the fixed-rate payments. This is at the end of the life of the swap. The floating rate of interest is SOFR plus 20 basis points. Instead of being paid, the interest is compounded forward until the end of the life of the swap at a rate of SOFR. The fixed rate of interest is $2\%$ per annum. Instead of being paid this interest is compounded forward at a fixed rate of interest of $2.3\%$ per annum until the end of the swap.  

The "assume forward rates are realized" approach can be used at least approximately for valuing a compounding swap such as that in Business Snapshot 34.2. It is straightforward to deal with the fixed side of the swap because the payment that will be made at maturity is known with certainty. The "assume forward rates are realized" approach for the floating side is justifiable because there exist a series of forward rate agreements (FRAs) where the floating-rate cash flows are exchanged for the values they would have if each floating rate equaled the corresponding forward rate.1  

# Example 34.1  

A compounding swap with annual resets has a life of three years. A fixed rate is paid and a floating rate is received. The fixed interest rate is $4\%$ and the floating reference interest rate is a 12-month rate. The fixed side compounds at $3.9\%$ and the floating side compounds at the 12-month rate minus 20 basis points. All forward rates for the floating reference rate are $5\%$ . OIS rates are all $4\%$ . The notional. principal is $\$100$ million. (All rates are annually compounded.)  

On the fixed side, interest of $\$4$ million is earned at the end of the first year. This compounds to $4\times1.039=\$4.156$ million at the end of the second year.. A second interest amount of $\$4$ million is added at the end of the second year bringing the total compounded forward amount to $\$8.156$ million. This compounds to $8.156\times1.039=\$8.474$ million by the end of the third year when there is the third interest amount of. $\$4$ million. The cash flow at the end of the third year on the fixed side of the swap is therefore $\$12.474$ million.  

On the floating side we assume all future interest rates equal the corresponding forward rates. This means that all future interest rates are assumed to be. $5\%$ with annual compounding. The interest calculated at the end of the first year is $\$5$ million. Compounding this forward at $4.8\%$ (forward rate minus 20 basis points) gives $5\times1.048=\$5.24$ million at the end of the second year. Adding in the interest, the compounded forward amount is $\$10.24$ million. Compounding. forward to the end of the third year, we get $10.24\times1.048=\S10.731$ million. Adding in the final interest gives $\$15.731$ million.  

The swap can be valued by assuming that it leads to an inflow of $\$15.731$ million and an outflow of $\$12.474$ million at the end of year 3. The value of the swap is therefore  

$$
\frac{15.731-12.474}{1.04^{3}}=2.895
$$  

or $\$2.895$ million. (This analysis ignores day count issues and makes the approximation indicated in footnote 1.).  
