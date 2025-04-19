---
tags:
  - '#equity_for_floating_swap'
  - '#equity_index'
  - '#equity_swaps'
  - '#forward_rate'
  - '#notional_principal'
  - '#s_and_p_500'
  - '#sofr'
  - '#total_return_index'
---
# 34.4  EQUITY SWAPS  

In an equity swap, one party promises to pay the return on an equity index on a. notional principal, while the other promises to pay a fixed or floating return on a. notional principal. Equity swaps enable a fund managers to increase or reduce their. exposure to an index without buying and selling stock. An equity swap is a convenient way of packaging a series of forward contracts on an index to meet the needs of the market participants.  

The equity index is usually a total return index where dividends are reinvested in the stocks comprising the index. An example of an equity swap is in Business Snapshot 34.3. In this, the 3-month return on the S&P 500 is exchanged for 3-month SOFR. The principal on either side of the swap is $\$100$ million and payments are made every 3 months.  

<html><body><table><tr><td colspan="2">Business Snapshot 34.3 Hypothetical Confirmation for an Equity Swap</td></tr><tr><td colspan="2">Trade date:</td></tr><tr><td rowspan="3">Effective date: Business day convention (all dates): Holiday calendar: Termination date:</td><td>4-January, 2021 11-January, 2021</td></tr><tr><td>Following business day</td></tr><tr><td>U.S. 11-January, 2026</td></tr><tr><td colspan="2">Equity amounts Equity payer:</td></tr><tr><td rowspan="3">Equity principal Equity index: Equity payment:</td><td>Microsoft USD 100 million</td></tr><tr><td>Total Return S&P 500 index 100(I - Io) /Io, where I is the index level on the payment date and Io is the</td></tr><tr><td>index level on the immediately preceding payment date. In the case of the first payment date, Io is the index level on 11-January, 2021 Each 11-April, 11-July, 11-October,</td></tr><tr><td colspan="2">Equity payment dates: and 11-January commencing 11-April 2021 up to and including 11-January 2026</td></tr><tr><td colspan="2">Floating amounts Floating-rate payer: Goldman Sachs</td></tr><tr><td colspan="2">Floating-rate notional principal: Floating rate: Floating-rate day count convention: Floating-rate payment dates:</td></tr></table></body></html>  

For an equity-for-floating swap such as that in Business Snapshot 34.3, the value at the start of its life is zero. This is because a financial institution can in theory arrange to costlessly replicate the cash flows to one side by borrowing the principal on each payment date and investing it in the index until the next payment date with any dividends being reinvested. A similar argument shows that the swap is always worth zero immediately after a payment date.  

Between payment dates the equity cash flow and the floating cash flow at the next payment date must be valued. The next floating cash flow can be valued from the overnight rates already observed and a forward rate for the remaining time until the next payment calculated from the SOFR zero curve. The value of the next equity cash flow is $L(E-E_{0})/E_{0}$ where $L$ is the principal,. $E$ is the current value of the equity index, and $E_{0}$ is its value at the last payment date.  
