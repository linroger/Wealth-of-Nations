---
tags:
  - cds_spread
  - credit_default_swaps
  - credit_derivatives
  - credit_indices
  - credit_risk
aliases:
  - CDS
  - CDX
  - Credit Default Swap
  - iTraxx
key_concepts:
  - CDS spread options
  - credit default swaps (CDS)
  - credit derivative operation
  - credit indices analysis
  - hedge credit risks
---
# CREDIT DERIVATIVES  

# Credit Default Swaps (CDS)  

# Aims  

• To explain the operation, uses and pricing of credit default swaps (CDS).   
• To analyse the use of the iTraxx (Europe) and CDX (USA) credit indices.   
• To analyse forwards and options on the CDS spread.  

Credit derivatives allow companies and fnancial institutions to hedge their credit risks and allow investors to hold assets whose value depends (in part) on the creditworthiness of companies and individuals. The increased use of credit derivatives was very rapid over the 2000–7 period, slowed down after the credit crisis of 2008 but has since substantially revived.  

Banks issue loans to companies and individuals and if these default, the banks experience losses. There are two main ways banks can reduce their credit risk. First, they can ‘bundle up’ a portfolio of loans and sell bonds to investors (e.g. pension funds, insurance companies, sovereign wealth funds) who then receive the cash fows from the loans – this is securitisation, and is discussed in Chapter 43.  

The second way a bank can reduce risk arising from a specifc corporate loan is to retain the loans in its banking book but to buy protection against a default by the corporate. It can do this by purchasing a (single name) credit default swap (CDS), often from an insurance company. If the corporate defaults on its bank loan, the seller of the CDS (insurance company) will compensate the bank for any losses on the defaulting loan. There are also basket CDS where you can buy credit protection on a ‘portfolio’ of companies – this is a multi-name credit derivative.  

In this chapter we explain how CDS operate and are priced, as well as the relationship between bond yields and the CDS spread. We discuss credit indices and basket CDS. We also show how forwards and options on the CDS spread can be used to hedge or insure against future changes in CDS spreads.  

# 42.1 CREDIT RISK AND CDS  

Credit default swaps provide insurance against credit events. Suppose MegaBank owns a corporate bond (‘the reference entity’) with face value of $Q=\$100$ , maturity of 10 years and it is worried that the corporate might default over the next 5 years. MegaBank can buy a 5-year credit default swap with a fnancial institution (a swap dealer, such as Goldman Sachs). As a buyer of the CDS, MegaBank pays a fxed swap spread of say $s=80$ bps per year to the seller (Goldman) over the next 5 years, unless a ‘credit event’ occurs, when the payments cease.  

If the corporate bond does not default, (Megabank) the buyer of the CDS pays the seller $\$80,000$ $(=s Q)$ each year over the 5-year life of the swap – this is the annual cost of the insurance premium. If the bond experiences a ‘credit event’ (e.g. goes into default) the seller of the CDS (Goldman) agrees to buy the company bond from Megabank for $\$100$ (i.e. face value of the bond), even though it might only be worth $\$20$ in the ‘distressed debt market’. Alternatively, the credit default swap could be cash settled whereby MegaBank keeps the bond (e.g. worth $\$20$ ) and the swap dealer (Goldman) pays Megabank $\$80$ . After a default, the buyer of the CDS does not pay any more premiums.  

If the contract stipulates cash settlement, an independent calculations agent will poll dealers to determine the mid-market value of the cheapest deliverable corporate bond of the reference entity, for delivery on a specifc date after the credit event. There will be several bonds which are eligible for delivery – usually they will all have the same seniority and approximately the same duration/maturity as the reference bond. The CDS buyer therefore has a ‘cheapest to deliver’ option. The notional principal in the CDS does not have to equal the face value of the corporate bonds that MegaBank holds – for example, if the notional principal in the CDS is less than the face value of its corporate bond then Megabank is less than fully insured.  

Consider a CDS starting on 20 June 2019, with a quoted CDS spread of $\dot{\boldsymbol{s}}=80$ bps annually, on a 5-year swap with a notional principal of $\$100$ on a ‘reference asset’ (Figure 42.1). Payments are usually made in arrears either each quarter, each half year or, as in our example, at the end of each year. If there is no credit event, the buyer of the CDS will pay $\$80,000$ on 20 June in each of the years 2021 to 2025. However, if there is a credit event on 20 September 2024, the annual payments by the buyer of protection will cease. But because payments are made in arrears, a fnal payment by the buyer is usually required. In our case, on 15 September the buyer of protection would have to pay approximately one quarter of the annual payment $(=$ $\$20,000$ for protection cover between 20 June and 20 September 2024.  

![](be8f0b8ed745a86e797f86385d1a270a347100e6efac2f42b90249cdbc40731e.jpg)  
FIGURE 42.1 Credit default swap (CDS)  

Large universal banks and insurance companies are market makers in the CDS market and, for example, might quote a CDS spread at a bid of 260 bps and ofer at 270 bps, on a new 5-year CDS. This means the swap dealer is prepared either to buy protection by paying 260 bps per year (i.e. $2.6\%$ of the notional principal per year) or to sell protection and hence receive 270 bps per year. The swap dealer therefore makes 10 bps on a round trip transaction of buying and selling a 5-year CDS to two diferent counterparties (on the same notional principal).  

Credit default swaps are used by banks when they issue loans to corporates and do not wish to increase their credit risk exposure. Suppose Bank-A already holds $\$1000$ of debt (i.e. bank loans and bonds) of corporate-Z and does not wish to increase its credit exposure any further but corporate-Z requires a further $\$100$ loan. The bank can issue a further loan (or purchase a bond issued by corporate-Z) and immediately enter into a CDS with another counterparty (say Bank-B who possibly has little credit exposure to corporate-A). Here the CDS is being used to ‘spread’ the credit risk of corporate-Z amongst a wider set of fnancial institutions, than just Bank-A. Of course for Bank-A, protection from the credit event of company-Z defaulting, depends on the solvency of Bank-B, who sold the CDS contract to Bank-A.  

# 42.2 SPECULATION WITH CDS  

In contrast to CDS providing insurance, CDS can be bought or sold without owning the underlying bonds. Hence, traders such as hedge funds can speculate on credit events using CDS. The CDS spread widens as the perceived risk of default on the reference entity increases. Therefore a hedge fund can make a speculative proft if it correctly forecasts that a reference entity will become more or less risky.  

For example, suppose today a hedge fund BigBucks thinks company-X will become more risky over the coming year. The hedge fund buys (from JPMorgan) a 5-year CDS (on a bond issued by company-X, the reference entity) with a notional principal of $\$100$ at a spread of 200 bps.  

If BigBucks’ forecast of an increase in credit risk turns out to be correct then the CDS spread might widen to 300 bps by the end of the year. The hedge fund might then sell a (new) CDS at 300 bps to another counterparty (e.g. pension fund). If there is no credit event over the remaining 4 years then the hedge fund will have locked in a net infow of $\$100,000$ p.a. for the next 4 years. This is the diference between the premium it receives of $\$300,000$ p.a. $(3\%)$ from the pension fund and what it pays (to JPMorgan), namely $\$200,000$ p.a. $(2\%)$ . If there is a credit event, the hedge fund will have to pay out the notional principal to one side of the swap deal (pension fund), but will receive the same amount from the counterparty from which it initially purchased the CDS (JPMorgan). So from the end of the frst year, the hedge fund is hedged against default but has secured a potential $\$100,000$ p.a. proft for the next 4 years.  

Note that the above speculative transaction (i.e. buy followed by sell) could take place over a very short horizon (e.g. 1 week) – as long as the CDS spread widens, the hedge fund can close out its long-short CDS positions at a proft. During the year, hedge funds will usually repeat these long-short trades many times, if they forecast that the credit risk of the reference entities will increase over short horizons.  

If the hedge fund believes the reference entity will become less risky in the future then it will set up a potential speculative proft by undertaking the reverse trade (to that described above). For example, Megabucks selling a CDS today at 300 bps and buying a CDS at 200 bps in 1 year’s time after a fall in the perceived riskiness of the reference entity ensues. Finance Blog 42.1 elaborates on the above points (which led to the collapse of Lehman Brothers in September 2008).  

# Finance Blog 42.1 Speculation Using CDS  

Betting that a company (TrashUS) will go bust (i.e. insolvent or bankrupt) or simply become more risky in the future can be illustrated using a stylised and simplifed example.  

Suppose on 1 January 2017 a hedge fund (MegaBucks) thinks TrashUS will become ‘more risky’ in 1 month’s time. The hedge fund (HF) today buys from Goldman a $\$1000$ , 5-year CDS for 100 bps with TrashUS as the reference entity. For ease of exposition, assume the payment of $\$10$ p.a. to Goldman takes place today $\left(t=0\right)$ and at the beginning of each year for the following 4 years $(t=1,2,3,4)$ ), but only if TrashUS does not default. Note that in this example, MegaBucks never holds the bonds of TrashUS, it only deals in CDS contracts, with TrashUS as the reference entity. Assume the HF is correct and in 1 month’s time the CDS spread on TrashUS has increased to 120 bp.  

# After 1 month: 1 February 2017  

On 1 February 2017, the HF sells a 5-year CDS (on $\$1000$ notional principal) at 120 bp to Legal and General (L&G), a pension fund. The HF now has a long-short position in CDS contracts.  

Assume two cases: (a) TrashUS does not go into default; (b) TrashUS declares bankruptcy at $t=4.5$ years.  

# Case (a) No default by TrashUS  

pays out ${\begin{array}{r l r l}{{5}\operatorname{yrs}\times\S1\mathrm{m}}&{=\S5\mathrm{m}}&{(100\mathrm{bps}\mathrm{toGoldman})}\\ {5\operatorname{yrs}\times\S1.2\mathrm{m}}&{=\S6\mathrm{m}}&{(120\mathrm{bps}\operatorname{from}\mathrm{L}\&\mathrm{G})}\\ &{=\S1\mathrm{m}}&{{\mathrm{(over~approximately~5~years)}}}\end{array}}$   
receives   
Proft  

The HF pays out $\$10$ each January and receives $\$1.2m$ each February. This is a return of $20\%$ over 1 month on its ‘own funds’ of $\$50$ – for each of the 5 years.1 The above proft is very dependent on when TrashUS becomes more risky (or defaults). If the CDS spread does not move to 120 bp until February 2020 (say) then the HF could sell a 2-year CDS and receive $2\times\$1.2m$ but it would have paid out $\$50$ in total (assuming no default of TrashUS).  

# Case (b) Default by TrashUS at 4.5 years  

The cash fows up to the 4th year are as above – and the HF has made a proft of $\$10$ by February of year-4. The HF sold a CDS contract in February 2017 to L&G, so on default of TrashUS the HF pays $\$1000$ to L&G and receives a TrashUS bond from L&G. But the HF in January 2017 bought a CDS contract from Goldman, so the HF passes the TrashUS bond (received from L&G) to Goldman and receives $\$1000$ in exchange. The net cash fow to the HF when TrashUS defaults is zero because the HF has a long-short position in the CDS contract.  

John Paulson’s hedge fund earned profts in the region of $\$1$ 5bn in the crash of 2008, in part due to large bets using CDS contracts. These CDS paid of when Lehman’s and other corporates went into liquidation around September 2008. (By comparison note that George Soros made ‘only’ $\$100$ in 1992 by betting that sterling would depreciate against the Deutsche mark.)  

# 42.3 CONTRACT DETAILS  

CDS are OTC instruments which frst appeared around the end of the 1990s. By the end of 2007 there were around $\$50$ trn notional outstanding in CDS contracts worldwide. However, since on average only around 0.2 per cent of investment grade companies default in any one year, most cash fows consist of the ‘spread’ payments from buyer to seller, which are much smaller than the notional outstanding. The most popular CDS contracts have maturities of 5 years but other maturities between 1 and 10 years are also available. Many US contracts mature on one of the following standard dates: 20 March, 20 June, 20 September, and 20 December.  

Initially there was no centralised clearing house for CDS transactions but after the credit crunch of 2007–8 revealed a lack of transparency in the CDS market, many commentators and regulators advocated a centralised clearing process with collateral being posted – and this is now being implemented in many developed countries.  

The reference entity in a CDS contract is usually a corporate or a sovereign entity (e.g. bonds issued by the Italian government) and the type of bond is often an unsubordinated (senior secured) corporate or government bond. If the ‘reference entity’ defaults, holders of these bonds are paid before ‘junior creditors’. The range of possible credit events is set out in the CDS contract and if there is any dispute it ultimately has to be settled in court. Credit events include bankruptcy of the reference entity or a failure to pay coupons on a bond or interest payments on a loan.  

For European CDS on reference entities comprising Investment Grade bonds, a credit event generally also includes debt restructuring. A ratings downgrade (by Standard & Poor’s, Moody’s, or Fitch) is not classifed as a credit event – because this might be open to manipulation. The deliverable in the CDS contract also has to be defned and may, for example, be limited to bonds or loans with a maximum maturity of 25 years and that the debt must not be ‘subordinated’ or ‘callable’.  

When a credit event occurs an auction may be held to fx the cash settlement price – this is a credit-fxing event. At the auction, large investment banks submit prices at which they would buy and sell the debt of the company which has sufered the credit event and is the reference entity in the CDS contract. For example, in 2008 Lehman’s debt was valued at around $9\%$ of face value – that is a ‘haircut’ of $91\%$ . Washington Mutual’s debt was at $57\%$ of face value while Fannie Mae and Freddy Mac’s debt was valued at the high rate of $95\%$ of par (maturity) value – because Fannie and Freddie’s debt is (efectively) underwritten by the US government.  

# 42.4 PRICING AND VALUATION  

The mid-market CDS spread (i.e. an average of bid and ask quotes) on individual reference entities can be calculated from estimates of survival and default probabilities. To illustrate CDS pricing, we initially assume default always occurs on a payment date (so there are no accruals issues), CDS payments are annual and occur at the end of each year. We use the following notation:  

$$
\begin{array}{r l}&{p=\mathrm{hazard~rate}\left(\mathrm{assumed~constant~over~life~of~the~CDS}\right)}\\ &{\pi_{i}=\mathrm{probability~of~default~}d u r i n g\mathrm{~the~year}}\\ &{\nu_{i}=\mathrm{unconditional~probability~of~survival~to~end~of~year-}i}\end{array}
$$  

$d_{i}=\mathrm{discountrate}=1/(1+r_{i})^{i}$ or $d_{i}=\exp(-r_{i}t_{i})$ continuously compounded $\textbf{\em n}=$ remaining life of the $s_{n}=$ spread decimal an $n$ -year $R=$ recovery rate $R=0.6$ ) $Q=$ notional principal in the contract  

Like a plain vanilla interest rate swap, when a CDS is initiated it must have zero present value to both parties – otherwise they would not enter the swap. Hence, the CDS spread on (an $n$ -year) swap is that value $s_{n}$ that makes the expected present value of future payments in the swap equal to the expected present value of future receipts. For the buyer of the CDS, the expected payments at time $t_{i}$ are $\nu_{i}s_{n}Q$ and the expected receipts, given default, are $\pi_{i}Q(1-R)$ . Equating the present value of expected receipts and payments gives the $n$ -period swap rate as the solution to:  

$$
s_{n}Q\sum_{i=1}^{n}\nu_{i}d_{i}=Q(1-R)\sum_{i=1}^{n}\pi_{i}d_{i}
$$  

Hence the $n$ -period CDS spread is:  

$$
s_{n}=(1-R)\frac{\sum_{i=1}^{n}\pi_{i}d_{i}}{\sum_{i=1}^{n}\nu_{i}d_{i}}
$$  

Suppose a 5-year CDS has the following characteristics:  

Conditional probability of default $p$ 0.03 $3\%$ p.a.)   
Recovery rate $R=$ 0.40 $40\%$ p.a.)   
Notional principal $Q=$ $\$100$   
Current LIBOR rate $r$ 0.04 $4\%$ continuously compounded  

Assume that the yield curve is fat and if a default occurs it does so half-way through any particular year, which implies that accrual payments in the CDS (given default) are $(1/2)Q$ . To determine the unknown swap rate $s_{n}$ we have to equate the expected cash payments by the protection buyer with the expected cash payments by the protection seller.  

# 42.4.1 Probability of Survival and Default  

The hazard rate is the probability of default between time $t$ and a small interval of time later $t+d t$ , conditional on no earlier default. If viewed from today, suppose companies with bonds rated BB historically have a $1\%$ , $3\%$ , and $5\%$ probability of defaulting at the end of year-1, year-2, and year-3 respectively. The probability of defaulting during the third year is $5\%-3\%=2\%$ . This is the unconditional probability of default during the third year, as seen from today. The probability that the company will survive to the end of year-2 is $100-3=97\%$ . Hence the probability that it will default during the third year conditional on no earlier default is $0.02/0.97=0.0206$ $(2.06\%)$ – this conditional probability over 1 year is the hazard rate (also called the default intensity).  

Assume a constant hazard rate of $\boldsymbol{p=3\%}$ p.a., so the probability of survival2 to the end of any year $t_{i}$ is $\nu_{i}=e^{-p.t_{i}}$ . For example, the probability of survival to the end of year-4 is $\nu_{i}=$ $e^{-0.03(4)}=0.8869$ . The probability of default during year-4 equals the probability of survival to year-3 minus the probability of survival to year-4, which is 0.027 ( 0.9139-0.8869, Table 42.1).  

TABLE 42.1 Unconditional default probabilities   


<html><body><table><tr><td>Time (years) t</td><td>Unconditional default probability π = pxv(t-1)</td><td>Survival probability V</td></tr><tr><td>１</td><td>0.0296</td><td>0.9704</td></tr><tr><td>２</td><td>0.0287</td><td>0.9418</td></tr><tr><td>3</td><td>0.0278</td><td>0.9139</td></tr><tr><td>4</td><td>0.0270</td><td>0.8869</td></tr><tr><td>５</td><td>0.0262</td><td>0.8607</td></tr></table></body></html>  

# 42.4.2 Cash Flows in the CDS  

Given the survival probabilities $\nu_{i}$ (Table 42.2, column 2), the expected payments for the protection buyer (given no default) are $\nu_{i}s_{n}Q$ (column 3) with present values $d_{i}\nu_{i}s_{n}Q$ (column 5), where $d_{i}=e^{-r t_{i}}$ and $t_{i}=1,2$ 5. The total present value of all of these payments is $\$40.7281s_{n}$ .  

Probability of default $\mathbf{\varepsilon}=0.03$   
TABLE 42.2 PV of expected CDS spread payments (no default)   


<html><body><table><tr><td>Time (years)</td><td>Survival probability</td><td>Expected payment</td><td>Discount factor</td><td>PV of expected payment</td></tr><tr><td>t </td><td>V</td><td>E(Payment) = Q ×v× s</td><td>d</td><td>d × E(Payment)</td></tr><tr><td>１</td><td>0.9704</td><td>9.7045s</td><td>0.9608</td><td>9.3239s</td></tr><tr><td>2</td><td>0.9418</td><td>9.4176s</td><td>0.9231</td><td>8.6936s</td></tr><tr><td>3</td><td>0.9139</td><td>9.1393s</td><td>0.8869</td><td>8.1058s</td></tr><tr><td>4</td><td>0.8869</td><td>8.8692s</td><td>0.8521</td><td>7.5578s</td></tr><tr><td>5</td><td>0.8607</td><td>8.6071s</td><td>0.8187</td><td>7.0469s</td></tr><tr><td>Sum of PV of payoffs (no default)</td><td></td><td></td><td></td><td>40.7281s</td></tr></table></body></html>  

Conditional probability of default $=0.03$ Risk-free LIBOR rate (continuously compounded) $=0.04$ Notional principal, $Q=\$10m$  

# $\pi_{i}=$ probability of default during the year  

Given the probability of default during the year $\pi_{i}$ , the expected cash fows by the seller of the CDS are $\pi_{i}Q(1-R)$ (Table 42.3, column 4). If defaults (only) occur half-way through each year then $d_{i}=e^{-r t_{i}}$ where $t_{i}=0.5,1.0,1.5\dots$ etc. For the CDS seller, the present value of expected cash fows (given default) are $d_{i}[\pi_{i}Q(1-R)]$ and the sum of these present values is $\$0.759$ (Table 42.3, column 6).  

TABLE 42.3 PV of cash fows given default and recovery rate   


<html><body><table><tr><td colspan="6">Conditional probability of default = 0.03 Risk-free LlBOR rate (continuously compounded) = 0.04 Notional principal, Q = $10m Recovery rate, R = 0.4</td></tr><tr><td>Time (years) t</td><td>Unconditional default probability π</td><td>Recovery rate</td><td>E(Payoff) = Q×π x(1 - R)</td><td>Discount factor d</td><td>PV of E(Payoff) = d × E(Payoff)</td></tr><tr><td>0.5</td><td>0.0296</td><td>0.4</td><td>0.1773</td><td>0.9802</td><td>0.1738</td></tr><tr><td>1.5 2.5</td><td>0.0287 0.0278</td><td>0.4 0.4</td><td>0.1721 0.1670</td><td>0.9418 0.9041</td><td>0.1621</td></tr><tr><td></td><td>0.0270</td><td>0.4</td><td>0.1621</td><td>0.8683</td><td>0.1510</td></tr><tr><td>3.5</td><td>0.0262</td><td>0.4</td><td>0.1573</td><td>0.8353</td><td>0.1407</td></tr><tr><td>4.5</td><td></td><td></td><td></td><td></td><td>0.1314</td></tr><tr><td colspan="6">Sum of PV given default (and recovery) 0.7590</td></tr></table></body></html>  

It only remains to determine the accrual payments should a default occur half-way through any of the 5 years in the life of the CDS. The accrual payment is $Q/2$ and the expected cash fows are $(Q/2)\pi_{i}s_{n}$ . The present value of the accrual payments is $\$0.6325s_{n}$ (Table 42.4, fnal column).  

TABLE 42.4 PV of accrual cash fows CDS spread given default   


<html><body><table><tr><td colspan="4">Conditional probability of default = 0.03 Risk free LlBOR rate (continuously compounded) = 0.04 Notional principal, Q = $10m Accrual payment (given default) = 0.5</td></tr><tr><td>Time (years) t 0.5</td><td>Unconditional default probability π</td><td>Expected accrual E(Accrual) = π × (Q/2)</td><td>Discount factor d</td><td>PV of expected accrual = d × E(Accrual)</td></tr><tr><td>1.5</td><td>0.0296 0.0287</td><td>0.1478s 0.1434s</td><td>0.9802</td><td>0.1448s 0.1351s</td></tr><tr><td>2.5</td><td>0.0278</td><td>0.1392s</td><td>0.9418 0.9041</td><td>0.1258s</td></tr><tr><td>3.5</td><td>0.0270</td><td>0.1351s</td><td>0.8683</td><td>0.1173s</td></tr><tr><td>4.5</td><td>0.0262</td><td>0.1311s</td><td>0.8353</td><td>0.1095s</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="5">Sum of PV of accrual cash flows given default 0.6325s</td></tr></table></body></html>  

Equating the expected cash fows with no default, to the expected cash fows given default:  

$$
\$40.7281s_{n}+\S0.6325s_{n}=\S0.759
$$  

gives a 5-year CDS spread of $s_{n}=0.01835$ $(1.84\%$ . Hence the ‘insurance premium’ on the reference entity for a 5-year CDS with a notional principal of $\$100$ , is $\$183,500$ each year.  

At inception, the value of the swap is zero and the swap rate is $s_{0}$ (say). If the CDS has been in existence for some time then its value could be positive or negative (to either the buyer or seller). The value of the CDS to the seller at $t>0$ is the present value of the remaining expected swap premium receipts minus the expected payout in the event of default. Ignoring accrual payments this is:  

$$
{{V}_{C D S}}(s e l l e r)_{t}=s_{0}Q\sum_{i=t}^{n}{{{\nu}_{i}}}{{d}_{i}}-Q(1-R)\sum_{i=t}^{n}{{{\pi}_{i}}}{{d}_{i}}
$$  

The summation goes from today $t>0$ to the end of the swap’s life, $n$ . At $t>0$ the default and survival probabilities as well as market interest rates used in the discount factors, will usually be diferent from those at $t=0$ (when the swap was initiated).  

# 42.4.3 Binary CDS  

A binary CDS is similar to a standard CDS except that if default occurs a fxed dollar amount is paid, which is independent of the recovery rate. For example, a binary CDS might have a cash payout of $Q=\$100$ if there is a default. The only change in the above analysis is that for the cash fows given default, $\pi_{i}Q(1-R)$ , we set $R=0$ (Table 42.5, column 4). The ‘binary’ CDS spread is the solution to:  

$$
\$40.7281s_{n}+\S0.6325s_{n}=1.2649
$$  

Hence, $s_{n}=0.0305$ $3.05\%$ , which on a notional principal of $\$100$ is an annual payment of $\$305,000$ .  

# 42.4.4 Default Probabilities from CDS Spreads  

When discussing the Black–Scholes option pricing formula we noted that by setting the quoted price of the option equal to the theoretical Black–Scholes price, we could derive the implied volatility of the underlying asset. Similarly, note that the theoretical CDS spread depends on probabilities of default $\pi_{i}-\mathsf{s e e}$ Equation (42.2). This means that if we have the term structure of quoted (mid-market) CDS spreads, then we can invert (42.2) to obtain the  

Conditional probability of default $=0.03$   
Risk-free LIBOR rate (continuously compounded) $=0.04$   
Notional principal, $Q=\$10m$   
Assume each payoff given default is $\$2$ , rather than $\${Q}(1-R),$ hence set Recovery rate $=0$  

TABLE 42.5 Binary CDS, PV of cash fows given default and recovery rate   


<html><body><table><tr><td>Time (years)</td><td>Unconditional default probability</td><td>Recovery rate</td><td>E(Payoff) = Q x π×(1 - R)</td><td>Discount factor</td><td>PV of E(Payoff) =</td></tr><tr><td>t</td><td>π</td><td></td><td></td><td>d</td><td>d × E(Payoff)</td></tr><tr><td>0.5</td><td>0.0296</td><td>0</td><td>0.2955</td><td>0.9802</td><td>0.2897</td></tr><tr><td>1.5</td><td>0.0287</td><td>0</td><td>0.2868</td><td>0.9418</td><td>0.2701</td></tr><tr><td>2.5</td><td>0.0278</td><td>0</td><td>0.2783</td><td>0.9041</td><td>0.2516</td></tr><tr><td>3.5 4.5</td><td>0.0270 0.0262</td><td>0</td><td>0.2701 0.2621</td><td>0.8683 0.8353</td><td>0.2345 0.2189</td></tr><tr><td></td><td></td><td>0</td><td></td><td></td><td>1.2649</td></tr><tr><td colspan="8">Sum of PV given default and recovery rate</td></tr></table></body></html>  

implicit conditional probability of default in each year. Today, we observe the mid-market quoted CDS swap rates $s_{1},s_{2},\ldots s_{n}$ for newly issued CDS (with diferent maturities) and using Equation (42.2), we can extract the conditional default probabilities $\pi_{1},\pi_{2},\ldots\pi_{n}$ . In fact, these are risk-neutral default probabilities, not real-world default probabilities. (Risk neutral probabilities can also be estimated from bond prices and asset swaps but we do not pursue this here.)  

# 42.5 BOND YIELDS AND THE CDS SPREAD  

If you hold a corporate bond and also purchase protection via a CDS then you efectively hold a risk-free T-bond. For example, suppose you hold portfolio-A consisting of:  

# Portfolio-A  

(a) 5-year corporate bond selling at (or near) its par (maturity) value which has a (par) yield $y_{c o r p}^{p a r}=7\%$ p.a. and (b) 5-year CDS on the corporate bond with a spread of $s=2\%$ p.a.  

Portfolio-A is free of credit risk, with a net return of $5\%$ p.a. (ignoring the default risk of the counterparty in the CDS contract). Hence to prevent arbitrage profts, the following should hold:  

Long a corporate bond and long $\mathrm{CDS}=\mathrm{Y}$ Yield on risk-free T-bond  

$$
y_{c o r p}^{p a r}-s=y_{T B}^{p a r}
$$  

Hence:  

$$
s=y_{c o r p}^{p a r}-y_{T B}^{p a r}
$$  

where $y_{c o r p}^{p a r}=p a r$ yield on a corporate bond, $y_{T B}^{p a r}=p a r$ yield on a US Treasury bond and $s$ is the CDS swap rate.  

If the corporate bond does not default, portfolio-A gives a net return of $5\%$ p.a. over 5 years consisting of receipts of $y_{c o r p}^{p a r}=7\%$ less the CDS premium paid. If the corporate bond defaults after, say, 3 years then portfolio-A still earns $5\%$ p.a. (net) over 5 years. This is made up of $5\%$ p.a. net over the frst 3 years from the corporate bond yield, minus the CDS spread payments. In year-3 after default, you receive the par value of the corporate bond from the CDS contract but you can invest this cash infow at the risk-free rate for another 2 years.  

# 42.5.1 Arbitrage Profits  

Suppose the quoted corporate bond yield is $y_{c o r p}^{p a r}=8\%$ (rather than $7\%$ above) and the CDS swap rate is $s=2\%$ , then an investor could earn a risk-free arbitrage proft. The investor borrows $\$2$ at the risk-free rate of $5\%$ , buys the corporate bond (at par) yielding $8\%$ and buys a CDS contract at a cost of $2\%$ . If there is no default, the net return to this strategy is $8\%$ from the corporate bond yield, less the cost of the CDS at $2\%$ and less the cost of borrowing of $5\%$ . This gives a known $1\%$ p.a. arbitrage proft, if and until the corporate bond defaults. But if the corporate defaults, then the receipt of the principal (from the CDS contract) can be used to pay of the borrowing of $\$2-s o$ there is no risk to this arbitrage strategy even if the bond defaults.  

Alternatively, suppose the corporate bond yield is $y_{c o r p}^{p a r}=6\%$ (rather than $7\%$ above). An arbitrageur would borrow the bond from her broker (JPMorgan), short-sell the bond, invest the cash proceeds at the risk-free rate of $5\%$ and also simultaneously sell a CDS contract, receiving the premium of $2\%$ p.a. The return to this arbitrage strategy is $5\%+2\%$ less the yield on the corporate bond of $6\%$ (which has to be paid to the broker – JPMorgan), giving a risk-free arbitrage return of $1\%$ p.a. These are not entirely riskless arbitrage opportunities but Equation (42.4) gives a reasonable frst approximation to the relationship between corporate bond yields and CDS spreads.  

# 42.6 CREDIT INDICES AND OTHER CDS CONTRACTS  

Indices have been developed to track a ‘portfolio’ of CDS spreads. Two important ones are:  

iTraxx Europe – a portfolio of 125 Investment Grade ‘names’ (corporates) in Europe CDX NA IG – a portfolio of 125 Investment Grade companies in North America.  

If some companies cease to be classifed as investment grade they are dropped from the above indices and new ‘investment grade’ companies are added – this happens in March and September each year. There is an active market in CDS ‘index protection’ particularly for maturities of 3, 5, 7, and 10 years.  

The quoted CDS index spread is (approximately) given by an average of the CDS spreads on the individual reference entities (companies), that make up the index. A quoted bid-price of 100 bps on a 5-year CDS index, implies that you can buy 5-year protection on a notional principal of $\$1$ million on each of the 125 reference entities in the index, for an annual payment of $\$1.25\mathrm{m}$ p.a. $(=0.01\times\$1m\times125$ ). Simplifying somewhat, if a reference entity defaults, the protection buyer receives the usual CDS payof and the annual payment is reduced by $\$125,456$ $\$10,000$ . (Note that the precise way the contract works is more complex than this.)  

# 42.6.1 Other CDS Contracts  

As noted above, a binary CDS is similar to a regular CDS, except the payof in default is the fxed dollar amount $Q$ rather than $Q(1-R)$ . We can price a binary CDS using (42.2) by setting the recovery rate $R=0$ .  

In a basket CDS there are a number of reference entities. A frst-to-default CDS provides a payof only when the frst default occurs. Similarly, a k -to-default CDS provides a payof only when the k default occurs. An add-up basket CDS pays of when any of the reference entities in the portfolio defaults. The add-up basket costs more than the k -to-default CDS, since the former provides greater protection (for the buyer of the CDS). These basket CDS operate much like a regular CDS, so that after the specifed default there is a settlement process and the swap is terminated – so there are no further payments by either party.  

# 42.7 DERIVATIVES ON THE CDS SPREAD  

There are forwards and options on the CDS spread. Forwards lock in a known future CDS spread, which will begin at some point in the future. An option on the CDS spread allows you to take advantage of the strike CDS spread $K_{s}$ or the market CDS spread $s_{T}$ , whichever is the most favourable ‘price’, at expiration of the option. If the company defaults before the maturity date of these derivatives contracts then they cease to exist (i.e. they ‘knock out’).  

For example, on 15 January 2017 you might purchase a forward CDS with a maturity $T=1$ year, on the 5-year CDS spread, at a forward ‘price’ of $s_{0}^{\check{f}}=300$ . You then have an obligation to buy protection at 300 bps in 1 year’s time on 15 January 2018. If the market (5-year) CDS spread on 15 January 2018 is $s_{T}=400$ then you will be happy you took out the forward CDS – but if the CDS spread turns out to be $s_{T}=200$ , then you may regret having taken out the forward contract. However, the latter is of no consequence because you initially bought the forward CDS on 15 January 2017 to ‘lock in’ a known CDS spread starting in 1 year’s time. When you hedge with forwards on 15 January 2017 you do not have the luxury of hindsight. If the reference entity defaults before the end of the year, then the forward-CDS ceases to exist.  

There are options which give you the right (but not the obligation) to enter into a credit default swap in the future, at a swap rate $K_{s}$ which is fxed today – these are credit default swaptions or CDS options. On 15 January 2017 you might purchase a call option on a 5-year CDS where the call matures in one year $(T=1)$ and has a strike of $K_{s}=240$ . If the (5-year) CDS spread on 15 January 2018, $s_{T}>K_{s}=240$ then you exercise the call and efectively obtain a CDS where you pay the CDS rate $K_{s}=240$ , which is lower than the quoted ‘cash market’ CDS spread, $s_{T}$ . If on 15 January 2018 the CDS spread $s_{T}<K_{s}=240$ , you do not exercise the call option and instead you buy a CDS in the cash market at the lower quoted swap rate, $s_{T}$ . Viewed as insurance, a 1-year call swaption on the 5-year CDS spread sets the maximum swap rate at $K_{s}=240$ you will pay in 1 year’s time, to enter a 5-year CDS swap but the swaption also allows you to take advantage of lower CDS rates should they occur.  

The price of a call (default) swaption on the CDS spread is positively related to the current ‘cash market’ CDS spread $s$ (i.e. the underlying asset in the option). Hence, you can hedge the credit risk from holding (cash market) corporate bonds by delta hedging with a credit default swaption.  

A 1-year put option on the (5-year) CDS spread gives you the right to sell fve-year protection on a corporate bond at a strike $K_{s}=250$ (say), starting in 1 year. If the 5-year CDS spread for the corporate $s_{T}<K_{s}=250$ in 1 year’s time, the put option will be exercised. If you have shorted corporate bonds, you will lose if the corporate’s perceived credit risk improves – as the bond price will rise. Today, you can ofset this credit risk by buying a CDS put option.  

For both call and put options on the CDS spread, the premiums must be paid up front and usually the option will cease to exist if the reference entity defaults before the expiration of the option. Clearly, calls and puts on the CDS spread can also be used to speculate on the future path of the CDS spread.  

# 42.8 SUMMARY  

• A (single name) credit default swap (CDS) is a marketable insurance contract, which pays out if the reference entity (e.g. a corporate bond) experiences a ‘credit event’ (e.g. bankruptcy). The buyer of a CDS is buying protection against possible default on a corporate bond – and the seller of a CDS (usually an insurance company) is the protection seller.  

• The payment of the ‘insurance premium’ is known as the CDS spread. The CDS spread is usually paid in arrears. Payment ceases if the reference entity defaults – although this will usually involves a ‘one-of’ accrual payment by the protection buyer.  

• The CDS spread $s_{n}$ on an $n$ -year CDS contract is determined by the (unconditional) probabilities of default $\pi_{i}$ , the (unconditional) probabilities of survival $\nu_{i}$ , the term structure of interest rates (as refected in discount rates $d_{i}$ ) and the recovery rate $R$ . Ignoring accrual payments the CDS spread is given by:  

$$
s_{n}=(1-R)\frac{\sum_{i=1}^{n}\pi_{i}d_{i}}{\sum_{i=1}^{n}\nu_{i}d_{i}}
$$  

• If there is a default, the buyer of the CDS either (a) receives the face (maturity/par) value of the reference entity’s bond, in return for ‘delivering’ the reference bond to the CDS counterparty or (b) the CDS is cash settled for $Q(1-R)$ , where $R$ is the recovery rate.   
• A binary CDS is like a standard CDS but the payout on default is a fxed amount of cash (e.g. the notional principal in the CDS, $\grave{Q}.$ ) which does not depend on the recovery rate.   
• There are CDS contracts on indices comprising a portfolio of 125 investment grade corporate bonds – for example, the European iTraxx index and the US, CDX NA IG indices. If any one bond in the reference portfolio defaults, there is a payof to the protection buyer equal to the notional principal of the bond in default (and the annual premium is reduced by 1/125 of the notional principal).   
• Forwards and options are available on the CDS spread. A long forward contract locks in a known future CDS spread, which will begin at some point in the future. A (long) call on the CDS spread (which is a credit default swaption) sets a maximum credit default swap spread that will be paid in the future but allows the holder to take advantage of lower cash market CDS spreads at expiration of the call option, should they occur. A (long put) on the CDS spread sets a minimum value for the CDS swap spread you receive but allows you to take advantage of selling a CDS at a higher cash market spread, should this occur at expiration of the put option.  

# EXERCISES  

# Question 1  

Explain why an investor who holds the bonds of company-Z might purchase a 5-year, CDS with a spread of 80 bps and notional principal of $\$100$ , on the ‘reference entity’. What are the possible outcomes?  

# Question 2  

Bank-A has loans outstanding with company-Z of $\$1000$ . Company-Z asks bank-A for a further $\$200$ loan. How can bank-A provide the additional loan to company-Z but use a CDS to reduce its credit exposure to company-Z? How does this ‘diversify’ the credit risk due to company-Z?  

# Question 3  

For a European CDS, is a ratings downgrade (by Standard & Poor’s, Moody’s, Fitch) classifed as a credit event?  

# Question 4  

Explain two ways that a CDS can be settled after a credit event.  

# Question 5  

Explain how and why a hedge fund might speculate on a credit event, using a 5-year CDS contract (on a bond issued by company-X) with a notional principal of $\$100$ , when the CDS spread is 200 bps.  

Consider the possible outcomes if the CDS spread widens to 300 bps after 3 months and consider two cases: (i) company-X does not default, or (ii) company-X defaults after 3 months.  

# Question 6  

Qualitatively what are the main determinants of the CDS spread?  

# Question 7  

The yield on a 5-year corporate bond-X is $7.5\%$ p.a. and it is trading at par. The yield on a 5-year risk-free bond is $4\%$ p.a. A 5-year CDS costs 400 bps per annum. How can you lock in a (risk-free) arbitrage opportunity?  