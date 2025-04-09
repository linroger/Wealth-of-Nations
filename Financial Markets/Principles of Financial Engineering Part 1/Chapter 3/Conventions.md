# 3.12 CONVENTIONS  

FRAs are quoted as two-way prices in bid-ask format, similar to Eurodeposit rates. A typical market contributor will quote a 3-month and a 6-month series.  

# EXAMPLE  

The 3-month series will look like this:  

<html><body><table><tr><td>1 × 4 4.87 4.91</td><td></td></tr><tr><td>2×5</td><td>4.89 4.94</td></tr><tr><td>3×6 4.90 4.95</td><td></td></tr><tr><td>etc.</td><td></td></tr></table></body></html>  

The first row implies that the interest rates are for a 3-month period that will start in 1 month. The second row gives the forward rate for a loan that begins in 2 months for a period of 3 months and so on.  

The 6-month series will look like this:  

<html><body><table><tr><td>1x7 4.87</td><td>4.91</td></tr><tr><td>2×8</td><td>4.89 4.94</td></tr><tr><td></td><td></td></tr><tr><td>3×9</td><td>4.90 4.95</td></tr></table></body></html>

etc.  

According to this table, if a client would like to lock in a fixed payer rate in 3 months for a period of 6 months and for a notional amount of UsD1 million, he or she would buy the. $3s$ against $g_{S}$ and pay the $4.95\%$ rate. For 6 months, the actual net payment of the FRA will be.  

$$
\frac{1,000,000\Big(\frac{L_{t_{3}}}{100}-0.0495\Big)\frac{1}{2}}{\Big(1+\frac{1}{2}\frac{L_{t_{3}}}{100}\Big)}
$$  

where $L_{t_{3}}$ is the 6-month LIBOR rate that will be observed in 3 months.  

Another convention is the use of LIBOR rate as a reference rate for both the sellers and the buyers of the FRA. LIBOR being an asking rate, one might think that a client who sells an FRA may receive a lower rate than LIBOR. But this is not true, as the reference rate does not change.  
