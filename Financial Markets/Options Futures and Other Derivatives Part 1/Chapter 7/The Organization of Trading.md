# 7.4 THE ORGANIZATION OF TRADING  

Financial institutions such as Citigroup act as market makers and provide bid and ask. quotes for the fixed rates that they are prepared to exchange in swaps. Table 7.4 shows. the full set of quotes that might be made at the time of the trades considered in Figures 7.3 to 7.6. The bid quote is the fixed rate that applies when the financial.  

![](images/b66153b39056401dc665083c4d065473a6bca231cb9164b6986da6c4c59a6ed1.jpg)  
Figure 7.6 Intel uses the swap in Figure 7.3 to convert a floating-rate investment into a fixed-rate investment..  

Table 7.4  Example of bid and ask fixed rates in the swap market for a swap where payments are exchanged quarterly (percent per annum).   


<html><body><table><tr><td>Maturity (years)</td><td>Bid</td><td>Ask</td><td>Swaprate</td></tr><tr><td>2</td><td>2.97</td><td>3.00</td><td>2.985</td></tr><tr><td>3</td><td>3.05</td><td>3.08</td><td>3.065</td></tr><tr><td>4</td><td>3.15</td><td>3.19</td><td>3.170</td></tr><tr><td>5</td><td>3.26</td><td>3.30</td><td>3.280</td></tr><tr><td>7</td><td>3.40</td><td>3.44</td><td>3.420</td></tr><tr><td>10</td><td>3.48</td><td>3.52</td><td>3.500</td></tr></table></body></html>  

institution is paying the fixed rate and receiving floating. The ask quote is the fixed rate that applies when it is receiving the fixed rate and paying floating. The average of the bid and ask rates is known as the swap rate and is shown in the final column. The spread between the bid and the ask (three to four basis points in the table) compensates the market maker for its costs.  

Occasionally a market maker may be lucky enough to enter into offsetting trades with two different nonfinancial companies. Usually, however, when it enters into a trade with a nonfinancial company, it must enter into the opposite trade with another. financial institution to hedge its risk. This is less profitable. Also, as explained in earlier chapters, the financial crisis of 2008 led to an international agreement that standard swaps between financial institutions be traded on electronic platforms and cleared though central counterparties (CCPs). This agreement would not apply to the swap. in Figures 7.4 and 7.6 because Intel is a nonfinancial company, but it would apply to Citigroup's hedging trade with another financial institution. Whereas the trade with. Intel might require no collateral to be posted, the hedging trade with another financial institution would require both initial and variation margin because it would be cleared through a CCP. This point is discussed further in Chapter 9..  

# Day Count Issues  

We discussed day count conventions in Section 6.1. The day count conventions affect payments on a swap and mean that some of the numbers calculated in the examples we have given earlier in this chapter are only approximately correct. Floating reference rates such as SOFR and U.S. LIBOR are quoted on an actual/360 basis. The first floating payment in Table 7.1 is based on a rate of $2.2\%$ . Because there are 92 days between March 8, 2022, and June 8, 2022, the floating payment that reflects an actual/ 360 day count is  

$$
\S100{,}000{,}000\times0{.}022\times\frac{92}{360}=\S562{,}222
$$  

In general, it is $L R n/360$ where $L$ is the principal, $R$ is the floating rate, and $n$ is the number of days in the accrual period.  

The fixed rate in a swap is also quoted with a day count convention. Popular fixed-. rate day counts are actual/365 and 30/360. This means that the fixed and floating rates are often not directly comparable because one applies to 360 days while the other applies to a full year. Also, in the case of actual/365, the fixed-rate cash flows in a swap. will vary slightly according to the number of days in the applicable period..  

<html><body><table><tr><td colspan="2">Business Snapshot 7.1J Extract from Hypothetical Swap Confirmation</td></tr><tr><td>Trade date Effective date Business day convention (all dates) Holiday calendar Termination date Fixed amounts</td><td>1-March-2022 8-March-2022 Following business day U.S. 8-March-2024</td></tr><tr><td>Fixed-rate payer Fixed-rate notional principal Fixed rate Fixed-rate day count convention</td><td>Apple Inc. USD 100 million 3.0% per annum Actual/365</td></tr><tr><td>Fixed-rate payment dates Floating amounts</td><td>Each 8-March, 8-June, 8-September, and 8-December commencing 8-June, 2022,up to and including 8-March, 2024</td></tr><tr><td>Floating-rate payer Floating-rate notional principal Floating rate Floating-rate day count convention Floating-rate payment dates</td><td>Citigroup Inc. USD 100 million 3-month SOFR reference rate</td></tr></table></body></html>  

For ease of exposition, we will ignore day count issues in our valuations in this chapter.  

# Confirmations  

When swaps are traded bilaterally a legal agreement, known as a confirmation, is signed by representatives of the two parties. The drafting of confirmations has been facilitated. by the work of the International Swaps and Derivatives Association (ISDA) in New York. This organization has produced a number of Master Agreements that are designed to cover all over-the-counter derivative transactions between two parties and define what happens in the event of default by either side, collateral requirements (if any), and so on. Business Snapshot 7.1 shows a possible extract from the confirmation. for the swap between Apple and the Citigroup in Figure 7.1. Almost certainly, the full confirmation would state that the provisions of an ISDA Master Agreement apply to. the contract.  

The confirmation specifies that the following business day convention is to be used and that the U.S. calendar determines which days are business days and which days are holidays. This means that, if a payment date falls on a weekend or a U.S. holiday, the payment is made on the next business day.2  
