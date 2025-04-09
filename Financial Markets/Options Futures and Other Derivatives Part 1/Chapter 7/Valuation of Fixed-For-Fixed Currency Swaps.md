# 7.9 VALUATION OF FIXED-FOR-FIXED CURRENCY SWAPS  

Each exchange of payments in a fixed-for-fixed currency swap is a forward contract. As shown in Section 5.7, forward foreign exchange contracts can be valued by assuming that forward exchange rates are realized. A fixed-for-fixed currency swap can therefore be. valued assuming that forward rates are realized..  

# Example 7.2  

Suppose that the term structure of risk-free interest rates is flat in both Japan and the United States. The Japanese rate is $1.5\%$ per annum and the U.S. rate is. $2.5\%$ per annum (both with continuous compounding). A financial institution has entered into a currency swap in which it receives. $3\%$ per annum in yen and pays. $4\%$ per annum in dollars once a year. The principals in the two currencies are. $\$10$ million and 1,200 million yen. The swap will last for another three years, and. the current exchange rate is 110 yen per dollar. The calculations for valuing the. swap as the sum of forward foreign exchange contracts are summarized in the following table (all amounts are in millions):  

<html><body><table><tr><td>Time (years)</td><td>Dollar</td><td>Yen</td><td>Forward cash fowcash flow exchangerate</td><td>Dollarvalueof yencashflow</td><td>Net cashflow</td><td>Present value</td></tr><tr><td>1</td><td>-0.4</td><td>+36</td><td>0.009182</td><td>0.3306</td><td>-0.0694</td><td>-0.0677</td></tr><tr><td>2</td><td>-0.4</td><td>+36</td><td>0.009275</td><td>0.3339</td><td>-0.0661</td><td>-0.0629</td></tr><tr><td>3</td><td>-10.4</td><td>+1236</td><td>0.009368</td><td>11.5786</td><td>+1.1786</td><td>+1.0934</td></tr><tr><td>Total</td><td></td><td></td><td></td><td></td><td></td><td>+0.9629</td></tr></table></body></html>  

The financial institution pays $0.04\times10=\S0.4$ million dollars and receives $1,200\times0.03=36$ million yen each year. In addition, the dollar principal of $\$10$ million is paid and the yen principal of 1,200 million is received at the end. of year 3. The current spot rate is $1/110=0.009091$ dollar per yen. In this case, $r=2.5\%$ and $r_{f}=1.5\%$ so that the one-year forward exchange rate is, from equation (5.9), $0.009091e^{(0.025-0.015)\times1}=0.{\dot{0}}09182$ The two- and three-year forward exchange rates in the table are calculated similarly. The forward contracts. underlying the swap can be valued by assuming that the forward exchange rates are realized. If the one-year forward exchange rate is realized, the value of yen. cash flow in year 1 will be $36\times0.009182=0.3306$ million dollars and the net cash flow at the end of year 1 will be $0.3306\mathrm{~-~}0.4=-0.0694$ million dollars. This has a present value of $-0.0694e^{-0.025\times1}=-0.0677$ million dollars. This is the value of the forward contract corresponding to the exchange of cash flows at the end of. year 1. The value of the other forward contracts are calculated similarly. As shown in the table, the total value of the forward contracts is $\$0.9629$ million..  

The value of a currency swap is normally zero when it is first negotiated. If the two principals are worth exactly the same using the exchange rate at the start of the swap, the value of the swap is also zero immediately after the initial exchange of principal. However, as in the case of interest rate swaps, this does not mean that each of the individual forward contracts underlying the swap has zero value. It can be shown that when interest rates in two currencies are significantly different, the payer of the highinterest-rate currency is in the position where the forward contracts corresponding to the early exchanges of cash flows have negative values, and the forward contract corresponding to final exchange of principals has a positive value. The payer of the. low-interest-rate currency is likely to be in the opposite position; that is, the early. exchanges of cash flows have positive values and the final exchange has a negative value.  

For the payer of the low-interest-rate currency, the swap will tend to have a negative. value during most of its life. The forward contracts corresponding to the early. exchanges of payments have positive values, and once these exchanges have taken. place, there is a tendency for the remaining forward contracts to have, in total, a negative value. For the payer of the high-interest-rate currency, the reverse is true. The value of the swap will tend to be positive during most of its life. Results of this sort are important when the credit risk in bilaterally cleared transactions is considered..  

# Valuation in Terms of Bond Prices  

A fixed-for-fixed currency swap can also be valued in a straightforward way as the difference between two bonds. If we define $V_{\mathrm{swap}}$ as the value in U.S. dollars of an outstanding swap where dollars are received and a foreign currency is paid, that is,  

$$
V_{\mathrm{swap}}=B_{D}-S_{0}B_{F}
$$  

where $B_{F}$ is the value, measured in the foreign currency, of the bond defined by the foreign cash flows on the swap and $B_{D}$ is the value of the bond defined by the domestic cash flows on the swap, and $S_{0}$ is the spot exchange rate (expressed as number of dollars per unit of foreign currency). The value of a swap can therefore be determined from the term structure of interest rates in the two currencies and the spot exchange. rate.  

Similarly, the value of a swap where the foreign currency is received and dollars are paid is  

$$
\ensuremath{V_{\mathrm{swap}}}=S_{0}B_{F}-B_{D}
$$  

# Example 7.3  

Consider again the situation in Example 7.2. The term structure of risk-free interest rates is flat in both Japan and the United States. The Japanese rate is $1.5\%$ per annum and the U.S. rate is $2.5\%$ per annum (both with continuous. compounding).A financial institution has entered into a currency swap in which it receives $3\%$ per annum in yen and pays $4\%$ per annum in dollars once a year. The. principals in the two currencies are $\$10$ million and 1,200 million yen. The swap will last for another three years, and the current exchange rate is. $110{\mathrm{yen}}=\$1$ The calculations for valuing the swap in terms of bonds are summarized in the. following table (all amounts are in millions):.  

<html><body><table><tr><td>Time (years)</td><td>Cashflowson dollarbond($)</td><td>Presentvalue ($)</td><td>Cashflowson yen bond (yen)</td><td>Presentvalue (yen)</td></tr><tr><td>1</td><td>0.4</td><td>0.3901</td><td>36</td><td>35.46</td></tr><tr><td>2</td><td>0.4</td><td>0.3805</td><td>36</td><td>34.94</td></tr><tr><td>3</td><td>10.4</td><td>9.6485</td><td>1,236</td><td>1,181.61</td></tr><tr><td>Total</td><td colspan="3">10.4191</td><td>1,252.01</td></tr></table></body></html>  

The cash flows from the dollar bond underlying the swap are as shown in the second column. The present value of the cash flows using the dollar discount rate of $2.5\%$ are shown in the third column. The cash flows from the yen bond. underlying the swap are shown in the fourth column. The present value of the. cash flows using the yen discount rate of. $1.5\%$ are shown in the final column of the table. The value of the dollar bond,. $B_{D}$ , is 10.4191 million dollars. The value. of the yen bond is $1{,}252{.}01$ million yen. The value of the swap in dollars is. therefore $(1,252.01/110)-10.4191=0.9629$ million. This is in agreement with the calculation in Example 7.2.  
