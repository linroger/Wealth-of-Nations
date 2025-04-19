---
tags:
  - '#cash_cdos'
  - '#cdo_structure'
  - '#cdo_tranches'
  - '#cdx_na_ig'
  - '#collateralized_debt_obligations'
  - '#credit_default_swaps'
  - '#financial_crisis_impact'
  - '#itraxx_europe'
  - '#single_tranche_trading'
  - '#synthetic_cdos'
---
# 25.8 COLLATERALIZED DEBT OBLIGATIONS  

We discussed asset-backed securities (ABSs) in Chapter 8. Figure 8.1 shows a simple structure. An ABS where the underlying assets are bonds is known as a collateralized debt obligation, or $C D O$ . A waterfall similar to that indicated in Figure 8.2 is defined for the interest and principal payments on the bonds. The precise rules underlying the waterfall are complicated, but they are designed to ensure that, if one tranche is more senior than another, it is more likely to receive promised interest payments and repayments of principal.  

# Synthetic CDOs  

When a CDO is created from a bond portfolio, as just described, the resulting structure is known as a cash CDO. In an important market development, it was recognized that a long position in a corporate bond has a similar risk to a short position in a CDS when the reference entity in the CDS is the company issuing the bond. This led to an alternative structure known as a synthetic $C D O$  

The originator of a synthetic CDO chooses a portfolio of companies and a maturity. (e.g., 5 years) for the structure. It sells CDS protection on each company in the portfolio. with the CDS maturities equaling the maturity of the structure. The synthetic CDO principal is the total of the notional principals underlying the CDSs. The originator has cash inflows equal to the CDS spreads and cash outflows when companies in the portfolio default. Tranches are formed and the cash inflows and outflows are distributed to tranches. The rules for determining the cash inflows and outflows of tranches are more straightforward for a synthetic CDO than for a cash CDO. Suppose that there are only three tranches: equity, mezzanine, and senior. The rules might be as follows:.  

1. The equity tranche is responsible for the payouts on the CDSs until they reach $5\%$ of the synthetic CDO principal. It earns a spread of 1,o00 basis points per year on the outstanding tranche principal..   
2. The mezzanine tranche is responsible for payouts in excess of $5\%$ up to a maximum of $20\%$ of the synthetic CDO principal. It earns a spread of 100 basis points per year on the outstanding tranche principal.   
3. The senior tranche is responsible for payouts in excess of $20\%$ . It earns a spread of 10 basis points per year on the outstanding tranche principal.  

To understand how the synthetic CDO would work, suppose that its principal is $\$100$ million. The equity, mezzanine, and senior tranche principals are. $\$5$ million, $\$15$ million, and $\$80$ million, respectively. The tranches initially earn the specified. spreads on these notional principals. Suppose that after 1 year defaults by companies in the portfolio lead to payouts of $\$2$ million on the CDSs. The equity tranche holders are responsible for these payouts. The equity tranche principal reduces to $\$3$ million and its spread (1,000 basis points) is then earned on. $\$3$ million instead of $\$5$ million. If, later during the life of the CDO, there are further payouts of. $\$4$ million on the CDSs, the cumulative of the payments required by the equity tranche is. $\$5$ million, so that its outstanding principal becomes zero. The mezzanine tranche holders have to pay $\$1$ million. This reduces their outstanding principal to $\$14$ million.  

Cash CDOs require an initial investment by the tranche holders (to finance the. underlying bonds). By contrast, the holders of synthetic CDOs do not have to make an initial investment. They just have to agree to the way cash inflows and outflows will be calculated. In practice, they are almost invariably required to post the initial tranche. principal as collateral. When the tranche becomes responsible for a payoff on a CDS,. the money is taken out of the collateral. The balance in the collateral account usually. earns interest.  

# Standard Portfolios and Single-Tranche Trading  

In the synthetic CDO we have described, CDSs on individual companies were sold to create a portfolio of instruments equivalent to a portfolio of bonds. In a further market development, it was recognized that tranches can be traded without any underlying. portfolio being created. An imaginary reference portfolio is used to define the cash flows on tranches. The buyer of protection pays the tranche spread to the seller of. protection, and the seller of protection pays amounts to the buyer that correspond to those losses on the reference portfolio of CDSs that the tranche is responsible for. This is sometimes referred to as single-tranche trading because one tranche can be traded without there being any trading in other tranches..  

In Section 25.3, we discussed CDS indices such as CDX NA IG and iTraxx Europe.. The market has used the portfolios underlying these indices to define standard synthetic CDO tranches. These trade very actively. The six standard tranches of iTraxx Europe. cover losses in the ranges $0{-}3\%$ $3{-}6\%$ $6{-}9\%$ $9-12\%$ $12-22\%$ , and $22{-}100\%$ . The six standard tranches of CDX NA IG cover losses in the ranges. $0{-}3\%$ $3\mathrm{-}7\%$ $7-10\%$ $10{-}15\%$ $15{-}30\%$ , and $30{-}100\%$  

Table 25.6 shows the effect of the 2007-8 financial crisis on iTraxx Europe quotes.. The index spread is the cost in basis points of buying protection on all the companies in the index, as described in Section 25.3. The quotes for all tranches except the $0{-}3\%$ tranche is the cost in basis point per year of buying tranche protection. (As explained earlier, this is paid on a principal that declines as the tranche experiences losses.) In the case of the $0{-}3\%$ (equity) tranche, the protection buyer makes an initial payment and. then pays 500 basis points per year on the outstanding tranche principal. The quote is for the initial payment as a percentage of the initial tranche principal..  

What a difference two years makes in the credit markets! Table 25.6 shows that the financial crisis led to a huge increase in credit spreads. The iTraxx index rose from  

Table 25.6  Mid-market quotes, from the Creditex Group, for 5-year tranches of iTraxx Europe. Quotes are in basis points except for the $0{-}3\%$ tranche where the quote equals the percent of the tranche principal that must be paid up front in addition to 500 basis points per year.   


<html><body><table><tr><td rowspan="2">Date</td><td colspan="5">Tranche</td><td rowspan="2">iTraxx index</td></tr><tr><td>0-3%</td><td>3-6%</td><td>6-9%</td><td>9-12%</td><td>12-22%</td></tr><tr><td>January 31, 2007</td><td>10.34%</td><td>41.59</td><td>11.95</td><td>5.60</td><td>2.00</td><td>23</td></tr><tr><td>January 31, 2008</td><td>30.98%</td><td>316.90</td><td>212.40</td><td>140.00</td><td>73.60</td><td>77</td></tr><tr><td>January 30, 2009</td><td>64.28%</td><td>1185.63</td><td>606.69</td><td>315.63</td><td>97.13</td><td>165</td></tr></table></body></html>  

23 basis points in January 2007 to 165 basis points in January 2009. The individual tranche quotes have also shown huge increases. One reason for the changes is that the default probabilities assessed by the market for investment-grade corporations increased. However, it is also the case that protection sellers were in many cases experiencing liquidity problems. They became more averse to risk and increased the risk premiums they required.  
