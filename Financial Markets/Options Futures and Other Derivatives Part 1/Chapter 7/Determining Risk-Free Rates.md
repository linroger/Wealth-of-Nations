---
tags:
  - '#fixed_rate_bond'
  - '#floating_rate_bond'
  - '#maturity'
  - '#notional_principal'
  - '#ois_rates'
  - '#overnight_indexed_swaps'
  - '#risk_free_rates'
  - '#zero_curve'
---
# 7.2 DETERMINING RISK-FREE RATES  

Overnight indexed swaps play an important role in determining the risk-free rates which are needed for valuing derivatives.  

OISs, when first entered into, into have a value of zero. (In this respect an OIS is like a forward contract.) The fixed rate that is exchanged for floating is referred to as the OIS rate. The OIS rates for a range of maturities can be observed in the market at a particular time. OIS rates with maturities one year or less, because they lead to just one exchange, have a straightforward interpretation. They provide the risk-free zero rates that are equivalent to the underlying overnight rates.  

Now consider OIS rates for maturities greater than a year. The notional principal is. not exchanged in an OIS. (This is why the principal is termed "notional.) However, if. we did exchange the notional principal at the end of the life of the swap, the cash exchanges would not change in any way because the notional principal is the same for both the fixed and floating payments. Table 7.2 is produced from Table 7.1 by adding. exchanges of principal at the end. The table shows that the swap is equivalent to the. exchange of a floating rate bond (cash flows in the third column) for a fixed rate bond (cash flows in the fourth column)..  

A key point is that the floating-rate bond in Table 7.2 is worth $\$100,000$ . This ist because it provides the payments necessary to service. $\$100$ million of borrowings at. overnight rates. (To see this, imagine that (a). $\$100$ million plus accumulated interest is borrowed at successive overnight rates during each quarter, (b) the accumulated interest is paid at the end of each quarter, and (c). $\$100$ million principal is repaid at the end of the two years.) Because an OIS is worth zero when first entered into, the fixed-rate bond (fourth column of Table 7.2) must also be worth. $\$100$ million. This shows that the OIS. rate of $3\%$ is the interest rate on a two-year fixed-rate bond that is worth par and pays interest quarterly.  

OIS rates can therefore be used in the same way as the Treasury rates in Section 4.7 to define a zero curve. The OIS rates out to one year define zero rates in a direct way. The OIS rates for longer maturities define bonds worth par. The zero curve can be assumed.  

Table 7.2 Cash flows in Table 7.1 when the notional principal is exchanged at the end.   


<html><body><table><tr><td>Date</td><td>SOFRrate (%)</td><td>Floatingcashflow received ($'000s)</td><td>Fixedcashflow paid ($:000s)</td><td>Netcashflow ($'000s)</td></tr><tr><td>June8,2022</td><td>2.20</td><td>550</td><td>750</td><td>-200</td></tr><tr><td>Sept.8,2022</td><td>2.60</td><td>650</td><td>750</td><td>-100</td></tr><tr><td>Dec.8,2022</td><td>2.80</td><td>700</td><td>750</td><td>-50</td></tr><tr><td>Mar.8,2023</td><td>3.10</td><td>775</td><td>750</td><td>+25</td></tr><tr><td>June8,2023</td><td>3.30</td><td>825</td><td>750</td><td>+75</td></tr><tr><td>Sept.8, 2023</td><td>3.40</td><td>850</td><td>750</td><td>+100</td></tr><tr><td>Dec.8,2023</td><td>3.60</td><td>900</td><td>750</td><td>+150</td></tr><tr><td>Mar.8,2024</td><td>3.80</td><td>100,950</td><td>100,750</td><td>+200</td></tr></table></body></html>

1 As mentioned in Section 4.3, overnight reference rates are considered to be better proxies for risk-free rates than Treasury rates.  

Table 7.3 OIS Rates and the calculation of the OIS zero curve.   


<html><body><table><tr><td>SIO maturity</td><td>SIO rate</td><td>Compounding frequency forOISrate</td><td>Zerorate (cont.comp.)</td></tr><tr><td>1 month</td><td>1.8%</td><td>Monthly</td><td>1.7987%</td></tr><tr><td>3months</td><td>2.0%</td><td>Quarterly</td><td>1.9950%</td></tr><tr><td>6 months</td><td>2.2%</td><td>Semiannually</td><td>2.1880%</td></tr><tr><td>12months</td><td>2.5%</td><td>Annually</td><td>2.4693%</td></tr><tr><td>2 years</td><td>3.0%</td><td>Quarterly</td><td>2.9994%</td></tr><tr><td>5 years</td><td>4.0%</td><td>Quarterly</td><td>4.0401%</td></tr></table></body></html>  

to be linear between maturities and calculations can be carried out by DerivaGem. A example of the result of the calculations is shown in Table 7.3 and Figure 7.2. In this. example, the two-year and five-year zero rates would be chosen using an iterative search. procedure (such as Solver in Excel) so that they are consistent with the following:.  

. A two-year bond making quarterly interest payments at $3\%$ per annum is worth par.   
. A five-year bond making quarterly interest payments at $4\%$ per annum is worth par.  
