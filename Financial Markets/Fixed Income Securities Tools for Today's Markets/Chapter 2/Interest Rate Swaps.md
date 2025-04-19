---
tags:
  - fixed_swap_rate
  - interest_rate_swaps
  - notional_amount
  - sofr_swap
  - term_structure
aliases:
  - IRS
  - SOFR
  - SONIA
  - Swap
  - TONAR
key_concepts:
  - Fixed swap rate
  - Interest rate swap
  - Notional amount
  - SOFR swap payments
  - Term structure currencies
---

# 2.2 INTEREST RATE SWAPS  

In an interest rate swap, two parties agree to exchange a series of interest. payments. Consider first the solid arrows in Figure 2.1, which are the only. contractual cash flows of the depicted swap. Counterparty A agrees to pay Counterparty B the fixed swap rate of. $0.1120\%$ annually for two years on. a notional amount of $\$100$ million. In return, Counterparty B agrees to paye to Counterparty A daily compounded SOFR annually for two years on this. same notional amount. No cash is exchanged on the trade or settlement date. Counterparty A is said to pay fixed and receive floating, while Counterparty. B is said to receive fixed and pay floating..  

As is explained in Chapter 12, SOFR on any given day is the. volume-weighted median rate at which market participants borrow and lend overnight funds secured by US Treasury collateral. Conceptually, daily SOFR represents the rate on extremely safe, overnight loans made that day.  

The $\$100$ million in the swap of Figure 2.1 is called the notional amount of the swap, rather than the face, par, or principal amount of the swap, because it is used only to compute the fixed- and floating-rate payments. The notional amount is never paid or received by either counterparty. The dashed arrows in Figure 2.1, which portray a final exchange of notional amount, will be convenient later for pricing the swap, but this exchange is fictional: it is not part of the swap contract and never actually takes place.  

![](42c488508bb271d671ff98c50b736c1eecfa3b0328e4138d8ccfb9b20a92e8c1.jpg)  
FIGURE 2.1 A SOFR Swap.  

Payments on both sides of a SOFR swap follow the actual/360 day-count convention. The annual interest payment on the fixed leg of the swap, therefore, over any 365-day year, is,  

$$
\mathbb{S}100,000,000\times0.1120\%\times\frac{365}{360}=\mathbb{S}113,556
$$  

Over 366-day years, of course, the fraction in Equation (2.9) would be $366/360$ instead.  

The annual payment on the floating side can be computed only after. every daily SOFR rate that year has been realized. To illustrate, assume a very simple scenario in which, over a 365-day year, SOFR was. $0.10\%$ for five days;. $0.50\%$ for 170 days; and $0.01\%$ for 190 days. In that scenario, an investment of. $\$100$ million compounded daily at SOFR rates would. grow to,  

$$
\begin{array}{l}{{5100,000,0000\bigg(1+{\displaystyle{\frac{0.10\%}{360}}}\bigg)^{5}\bigg(1+{\displaystyle{\frac{0.50\%}{360}}}\bigg)^{170}\bigg(1+{\displaystyle{\frac{0.01\%}{360}}}\bigg)^{190}}}\ {{~={\displaystyle\S100,243,071}}}\end{array}
$$  

Therefore, the payment on the floating leg at the end of the year, representing the interest on a daily compounded SOFR investment over that year, is,  

$$
\$100,243,071-
$$  

In this particular scenario, Counterparty A receives $\$243,071$ on the floating leg, but pays only $\$113,556$ on the fixed leg. Had realizations of SOFR over the year been lower, the reverse could have easily been true, with Counterparty A receiving less on the floating leg than it paid on the fixed leg.  

SOFR swaps that mature in an exact number of years, like the example in Figure 2.1, make annual payments. SOFR swaps that mature in less than one year make one payment at maturity. And SOFR swaps that mature in more than one year, but not in an exact number of years, typically make one stub payment followed by annual payments to maturity. A 1.5-year swap, for example, would likely make a stub payment after six months and another payment one year later.  

Figure 2.2 shows the term structure of swap rates in different currencies. as of mid-May 2021. The SOFR curve, for example, gives the fixed rates that can be exchanged for SOFR for various terms. As highlighted in Figure 2.1, in a two-year US dollar (USD) swap,. $0.1120\%$ fixed can be exchanged for floating SOFR. Figure 2.2 shows additional USD swap rates, for example,. $1.352\%$ for a 10-year swap and $1.758\%$ for 30 years.  

The other rates and currencies shown are SONIA (Sterling Overnight. Interbank Average) in British Pounds (GBP); TONAR (Tokyo Overnight  

![](6041084b4e95f086049b2131084f6d3ef51349fc7620e2bd8c80078aa9c00108.jpg)  
FIGURE 2.2 Term Structures in Different Currencies, as of May 14, 2021.  

Average Rate) in Japanese Yen (JPY); ESTER, also written as STR (Euro Short-Term Rate) in Euro (EUR); and SARON (Swiss Average Rate Overnight) in Swiss Franc (CHF). These rates, which are discussed further. in Chapter 12, are often called "risk-free" rates to distinguish them from LIBOR rates, but only SOFR and SARON are rates on loans collateralized by government bonds. SONIA, TONAR, and ESTER, by contrast, are all rates on interbank loans. In any case, Figure 2.2 illustrates that the term structures of these rates vary across currencies and, of course, though not. shown, over time as well..  
