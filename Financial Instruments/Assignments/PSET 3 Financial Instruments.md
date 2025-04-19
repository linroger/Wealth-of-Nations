---
linter-yaml-title-alias: 1          GREECE CURRENCY SWAPS
title: PSET 3 Financial Instruments
tags:
  - bond_pricing
  - currency_swap
  - exchange_rate_risk
  - financial_instruments
  - zero_coupon_bonds
aliases:
  - Currency Swap
  - Greek Bond
  - PSET 3
  - VeroTende
key_concepts:
  - Currency swap
  - Dollar denominated note
  - Exchange rate risk
  - Semi-annual coupon rate
  - Zero coupon bonds
---

**Homework 3**
Roger Lin
Suna Bai
Due at the beginning of class 4

# PSET 3 Financial Instruments

On June 1st 2001 Greece issued a 10 year dollar denominated note for a value of USD 50 billion and a semi-annual coupon rate _c_ = 6% _Hint:_ The bond pays semiannual coupons in the amount of USD$\frac{6\%}{2}$× 50 billion = USD 1.5 billion along with the face value of USD 50 billion at maturity.

Issuing debt denominated in a foreign currency is common. There are few reasons why this happens: a country might need to make payments in a foreign currency or foreign investors’ appetites for diversification allows the country to issue at more favorable conditions. In this example we will assume that Greece has obtained more favorable conditions issuing in US dollars and the money will be used for domestic operations. At issuance Greece therefore has to convert into Euros any US dollars obtained from the note. To make the payments (semi-annual coupons and principal) to the investors that purchased the note,  Greece must to convert Euros into US dollars at coupon dates and at maturity. This exposes the country to exchange rate risk. In particular if the US dollar appreciates,  Greece will have to use more Euros to get an amount equal to the US dollar value of coupons and principal.

The Greek [Finance](Finance.md) Minister contacts VeroTende Investment Bank to ask about how to hedge the position,  and the bank suggests a currency swap. The swap will require an initial transfer of principal,  in which Greece will pay USD (US dollar) 50 billion and receive EUR (Euro) 59 billion at initiation of the contract. Every six months after that Greece will receive USD 1.5 billion in exchange for a fixed payment in EUR. _At maturity Greece will pay 59 billion EUR and receive 50 billion USD._

Table 1 reports the prices of European and American Government zero coupon bonds on June 1st 2001.

|   |   |   |
|---|---|---|
|**Maturity**|**Greek ZCB**|**US ZCB**|
|0.0|1.0000|1.0000|
|0.5|0.9786|0.9822|
|1.0|0.9588|0.9647|
|1.5|0.9388|0.9431|
|2.0|0.9191|0.9192|
|2.5|0.8989|0.8973|
|3.0|0.8788|0.8749|
|3.5|0.8583|0.8520|
|4.0|0.8379|0.8287|
|4.5|0.8177|0.8051|
|5.0|0.7977|0.7812|
|5.5|0.7780|0.7603|
|6.0|0.7583|0.7397|
|6.5|0.7370|0.7194|
|7.0|0.7155|0.6993|
|7.5|0.6953|0.6795|
|8.0|0.6751|0.6600|
|8.5|0.6559|0.6407|
|9.0|0.6369|0.6218|
|9.5|0.6208|0.6032|
|10.0|0.6050|0.5848|

**Table 1. Greek and US ZCB prices on June 1st 2001**

Hint: to use these number consider the value of the value (in dollars) of a dollar denominated bond with annualized coupon rate of _c_ and face value _N_. This value is given by:$$B_0^\$=\sum_{t=0.5}^T\frac c2\cdot N^\$\cdot Z^\$(0, t)+N^\$\cdot Z^\$(0, T)$$
(1) Using the data above,  and knowing that the USD/EUR spot exchange rate on June 1st 2001 is equal to 0.8475 USD/EUR (=50/59 USD/EUR),  compute the swap rate (i.e. the annualized coupon rate for the semi-annual payments in EUR) that sets the value of the currency swap to 0 at initiation of the contract.

> [!ANSWER] Part 1. Greece Currency Swap
> (1) To understand how we can compute the swap rate K that sets the value of the
> currency swap equal to 0,  it is helpful to break down the currency swap into simpler components. We know that Greece will have:
> - 1. A position in USD:
> 	- (a) Pay USD 50 billion on June 1st 2001 (from now on:$t=0)$
> 	- (b) Receive USD$50\cdot\frac{0.06}{2}=1.5$billion every six months for the next 10 years
> 	- (c) Receive USD 50 billion n on June lst 2011 (from now on:$t=T)$
> - 2. A position in EUR:
> 	- (a) Receive$\frac{USD50}{0.8475USD/EUR}=EUR59$billion at$t=0$
> 	- (b) Pay EUR$59\cdot\frac K2$billion every six months for the next 10 years
> 	- (c) Pay EUR 59 billion at$t=T$
> Now it's easy to see that (1.b) and (1.c) are the cash flows of a long position in (i.e. we buy) a coupon bond with principal equal to USD 50 billion,  maturing in 10 years and with a semiannual coupon rate equal to c = 6%. In the same way (2.b) and (2.c)
> are the cash flows of a short position in (i.e. we sell) a coupon bond with principal equal to EUR 59 bn,  maturing in 10 years and with a semiannual coupon rate equal to K. Finally (1.a) and (2.a) represent the exchange of principal. This principal is exchanged to hedge the exchange rate risk on the principal that will be paid at T.
>
> In particular Greece will receive USD 50 billion and will pay EUR 59 billion at t = T.
>
> If dollar depreciates the USD 50 bn (which are exactly equivalent to EUR 59 bn at t = 0) will be worth less than EUR 59 bn. To hedge against this risk Greece exchanges the principals at time t = 0 and agrees that,  at t = T,  the principals will be exchanged at the same exchange rate used for the principals exchange at time t = 0.
>
> We can write the swap as a sum of three components:
>
> $$S W A P=B O N D^{USD}-B O N D^{e}+E o P_{0}$$
> where _EoP_ is the exchange of principal. The value of the swap will therefore be
>
> $$V^{Swap}=B^{\$}-B^{e}+V^{EoP_{0}}\tag{1}$$
> where B$ and Be denote,  as in Teaching Notes 2,  the value of two coupon bonds (with different coupon rates) in USD and EUR respectively. We know that their semiannual coupon rates are c = 6% (I will keep writing c to get a more general result) and K
> respectively.
>
> The initial exchange of principal is typically done in a way that V EoP = 0,  that is the principal in USD is equal to the principal in EUR times the current USD / EUR
> exchange rate. So the value of the swap becomes V _Swap_ = B$− Be. Now we know that the value at t = 0 (in USD) of the USD coupon bond is
>
> $$B_{0}^{\$$}=\sum_{t=0.5}^{T}\frac{c}{2}\cdot N^{\$$}\cdot Z^{\$$}(0, t)+N^{\$$}\cdot Z^{\$$}(0, T)$$
>
> that is,  the sum of all discounted (using the US zero coupon curve$Z^{\$}(0, t))$ coupons
> (i.e. $c/2 ·N$) plus the discounted value of the principal at maturity. Similarly the value at t = 0 (in EUR) of the EUR coupon bond is$$B_{0}^{e}=\sum_{t=0.5}^{T}\frac{K}{2}\cdot N^{e}\cdot Z^{e}(0, t)+N^{e}\cdot Z^{e}(0, T)$$
> Before computing K,  remember that when we compute the value of the swap we express it in a determined currency. Since each bond has its own currency,  we have to convert all values to the same currency. So,  if we want to compute the value of the currency swap in dollars we will convert the value of the EUR bond into USD,  by multiplying it for the spot USD / EUR exchange rate. In formulas,  the time t value of the currency swap in USD is:$$V_{t}^{S w a p, \, \$$}=B_{t}^{\$$}-M_{t}\cdot B_{t}^{e}$$similarly,  the time t value in EUR is:$$V_{t}^{S w a p, \, e}=\frac{B_{t}^{\$$}}{M_{t}}-B_{t}^{e}$$
> We can now compute K. Our goal is to have$V^{Swap}_{0}$= 0.
> Let's take the value of the swap in USD.$$V_{0}^{Swap, \, \$}=B_{0}^{\$}-M_{0}\cdot B_{0}^{e}=0$$This implies that$B_{0}^{\$}=M_{0}\cdot B_{0}^{e}$,  which is the same as$$B_{0}^{\$}=M_{0}\cdot\left[\sum_{t=0.5}^{T}\frac{K}{2}\cdot N^{e}\cdot Z^{e}(0, t)+N^{e}\cdot Z^{e}(0, T)\right]$$Rearranging we get:$${\frac{B_{0}^{\$$}}{M_{0}}}-N^{e}\cdot Z^{e}(0, T)={\frac{K}{2}}\cdot N^{e}\cdot\sum_{t=0.5}^{T}Z^{e}(0, t)$$
> solving for K,  we get:
>
> $$K=2\cdot\frac{\frac{B_{0}^{8}}{I_{0}}-N^{e}\cdot Z^{e}(0, T)}{N^{e}\cdot\sum_{t=0.5}^{T}Z^{e}(0, t)}\tag{2}$$
>
> But we don't know yet$B_{0}^{8}$. Using the US ZCB prices (also know as Zero Coupon
> curve or discount function) we can compute its value as
>
> $$B_{0}^{\$}=\sum_{t=0.5}^{T}\frac{0.06}{2}\cdot50\cdot Z^{\$}(0, t)+50\cdot0.5848=$$$$=\frac{0.06}{2}\cdot50\cdot15.5573+50\cdot0.5848=52.5778$$
> Plugging it into equation (2) we get K = 0.0566 or 5.66%.

| Time | ZEU | ZUS | Dollar CF | Euro CF | PV Dollar CF | PV Euro CF |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 0 | 1 | 1 | -$50, 000, 000, 000.00 | € 59, 000, 000, 000.00 | -$50, 000, 000, 000.00 | € 59, 000, 000, 000.00 |
| 0.5 | 0.9786 | 0.9822 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 467, 900, 000.00 | € 1, 738, 494, 000.00 |
| 1 | 0.9588 | 0.9647 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 438, 200, 000.00 | € 1, 707, 519, 000.00 |
| 1.5 | 0.9388 | 0.9431 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 408, 200, 000.00 | € 1, 669, 287, 000.00 |
| 2 | 0.9191 | 0.9192 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 378, 650, 000.00 | € 1, 626, 984, 000.00 |
| 2.5 | 0.8989 | 0.8973 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 348, 350, 000.00 | € 1, 588, 221, 000.00 |
| 3 | 0.8788 | 0.8749 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 318, 200, 000.00 | € 1, 548, 573, 000.00 |
| 3.5 | 0.8583 | 0.852 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 287, 450, 000.00 | € 1, 508, 040, 000.00 |
| 4 | 0.8379 | 0.8287 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 256, 850, 000.00 | € 1, 466, 799, 000.00 |
| 4.5 | 0.8177 | 0.8051 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 226, 550, 000.00 | € 1, 425, 027, 000.00 |
| 5 | 0.7977 | 0.7812 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 196, 550, 000.00 | € 1, 382, 724, 000.00 |
| 5.5 | 0.778 | 0.7603 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 167, 000, 000.00 | € 1, 345, 731, 000.00 |
| 6 | 0.7583 | 0.7397 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 137, 450, 000.00 | € 1, 309, 269, 000.00 |
| 6.5 | 0.737 | 0.7194 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 105, 500, 000.00 | € 1, 273, 338, 000.00 |
| 7 | 0.7155 | 0.6993 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 073, 250, 000.00 | € 1, 237, 761, 000.00 |
| 7.5 | 0.6953 | 0.6795 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 042, 950, 000.00 | € 1, 202, 715, 000.00 |
| 8 | 0.6751 | 0.66 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$1, 012, 650, 000.00 | € 1, 168, 200, 000.00 |
| 8.5 | 0.6559 | 0.6407 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$983, 850, 000.00 | € 1, 134, 039, 000.00 |
| 9 | 0.6369 | 0.6218 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$955, 350, 000.00 | € 1, 100, 586, 000.00 |
| 9.5 | 0.6208 | 0.6032 |$1, 500, 000, 000.00 | € 1, 770, 000, 000.00 |$931, 200, 000.00 | € 1, 067, 664, 000.00 |
| 10 | 0.605 | 0.5848 |$51, 500, 000, 000.00 | € 60, 770, 000, 000.00 |$31, 157, 500, 000.00 | € 35, 538, 296, 000.00 |

|  |  |
| ---- | ---- |
| Value of Dollar Denominated Bond |$53, 893, 600, 000.00 |
| Value of Euro Denominated Bond | € 62, 039, 267, 000.00 |
| Dollar Value of Euro Denominated Bond -> |$52, 575, 650, 000.00 |
| Swap Rate | 0.975545334 |

$$V_t^{swap}=M_t\times B^e(t, T)-K\times B^\$(t, T)$$
$$0=$52, 575, 650, 000.00K*$53, 893, 600,  0000.000$$
$$K= \frac{$52, 575, 650, 000.00}{$53, 893 K, 600, 000.00}= 0.97575545334$$

The VeroTende Bank executives meet Greek officials,  describe the currency swap and quote the rate calculated in point (1). To their surprise,  the Greek Finance Minister explains that they have decided to be advised by another bank. They shake hands and the finance Minister leaves.

Some rumors say that Goldman Sachs has set up a currency swap with structured as above,  but with two minor differences:[[Lecture 1- Probability Distributions of Returns]](#_ftn1)

- a. For the exchange of principal at time t = 0 the exchange rate utilized is not the market spot rate (i.e. 0.8475 USD / EUR),  but rather the historical average of the spot exchange rate between March 12th 2001 and June 1st 2001,  that is 0.8148 USD / EUR;
- b)  The rate quoted for the payments in euro is 7.00%

|  |  |  |  |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Time | ZEU | ZUS | Dollar CF | Euro CF | PV Dollar CF | PV Euro CF |
| 0 | 1 | 1 | -$50, 000, 000, 000.00 | € 59, 000, 000, 000.00 | -$50, 000, 000, 000.00 | € 59, 000, 000, 000.00 |
| 0.5 | 0.9786 | 0.9822 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 467, 900, 000.00 | € 2, 028, 243, 000.00 |
| 1 | 0.9588 | 0.9647 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 438, 200, 000.00 | € 1, 992, 105, 500.00 |
| 1.5 | 0.9388 | 0.9431 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 408, 200, 000.00 | € 1, 947, 501, 500.00 |
| 2 | 0.9191 | 0.9192 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 378, 650, 000.00 | € 1, 898, 148, 000.00 |
| 2.5 | 0.8989 | 0.8973 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 348, 350, 000.00 | € 1, 852, 924, 500.00 |
| 3 | 0.8788 | 0.8749 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 318, 200, 000.00 | € 1, 806, 668, 500.00 |
| 3.5 | 0.8583 | 0.852 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 287, 450, 000.00 | € 1, 759, 380, 000.00 |
| 4 | 0.8379 | 0.8287 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 256, 850, 000.00 | € 1, 711, 265, 500.00 |
| 4.5 | 0.8177 | 0.8051 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 226, 550, 000.00 | € 1, 662, 531, 500.00 |
| 5 | 0.7977 | 0.7812 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 196, 550, 000.00 | € 1, 613, 178, 000.00 |
| 5.5 | 0.778 | 0.7603 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 167, 000, 000.00 | € 1, 570, 019, 500.00 |
| 6 | 0.7583 | 0.7397 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 137, 450, 000.00 | € 1, 527, 480, 500.00 |
| 6.5 | 0.737 | 0.7194 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 105, 500, 000.00 | € 1, 485, 561, 000.00 |
| 7 | 0.7155 | 0.6993 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 073, 250, 000.00 | € 1, 444, 054, 500.00 |
| 7.5 | 0.6953 | 0.6795 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 042, 950, 000.00 | € 1, 403, 167, 500.00 |
| 8 | 0.6751 | 0.66 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$1, 012, 650, 000.00 | € 1, 362, 900, 000.00 |
| 8.5 | 0.6559 | 0.6407 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$983, 850, 000.00 | € 1, 323, 045, 500.00 |
| 9 | 0.6369 | 0.6218 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$955, 350, 000.00 | € 1, 284, 017, 000.00 |
| 9.5 | 0.6208 | 0.6032 |$1, 500, 000, 000.00 | € 2, 065, 000, 000.00 |$931, 200, 000.00 | € 1, 245, 608, 000.00 |
| 10 | 0.605 | 0.5848 |$51, 500, 000, 000.00 | € 61, 065, 000, 000.00 |$31, 157, 500, 000.00 | € 35, 710, 812, 000.00 |

|   |   |
|---|---|
|Value of Dollar Denominated Bond|$53, 893, 600, 000.00|
|Value of Euro Denominated Bond|€ 66, 628, 611, 500.00|
|Dollar Value of Euro Denominated Bond ->|$54, 288, 992, 650.20|
|Swap Rate|1.007336542|

(2) Compute the value of the Goldman swap. Why do you think Greece has decided to accept Goldman proposal rather than the one suggested by VeroTende Bank? In answering the question give particular thought to the cash flows of the swap and their timing.

```python
- Because Greece was paying a higher interest rate on the notional,  it would likely earn a higher upfront payment to compensate and make the two sides of the swap even. If Greece needed money upfront urgently,  it would likely take the Goldman deal because it gave them a higher upfront payment in exchange for higher coupon payments throughout the life of the swap. This may be why Greece decided to pursue the deal where they would have to pay a higher coupon on the FX swap.
```

> [ANSWERS]
> 2) Under Goldman Sachs terms,  there are two major differences,  namely K = 7% rather > than 5.66% and V EoP0 ̸= 0,  since principal is exchanged using an exchange rate > which is different from the spot exchange rate. We can use formula (1) to compute > the currency swap. We already know B$= 52.5778 billion of dollars. We need to > compute the new value for Be since the coupon has changed to K = 7% and the value > of the time t = 0 exchange of principal$V^{EoP0}$
> . Using the same approach used for$B^{USD}$> we get Be = 68.2444 billion of EUR. > For computing V EoP0 we need first to specify a currency. Let's consider USD,  and let's denote by M 0 the spot exchange rate and by MGS the fictitious exchange rate set in Goldman conditions. First let's define the cash flows in USD. Greece will pay to Goldman N$= 50 billion of dollars and will receive a cash flow in EUR determined using the fictitious rate$M^{GS}$,  that is$N^e=\frac{N^{\$}}{M^{GS}}=\frac{50}{0.8148}=61.3648$billion of euros Then we can compute the value of the exchange of principal, $V_{0}^{EoP_{0}, \$}.$To compute this we need to use the current exchange rate,  as the fictitious rate$M^{GS}$was just used to determine the cash flow. We get (in billion of dollars)$$V_0^{EoP_0, S}=N^e\cdot M_0-N^3=61.3648\cdot0.8475-50=2.0040$$Alternatively if we wanted to compute the value of the exchange of principal in EUR we would have simply done$$V_0^{EoP_0, e}=N^e-\frac{N^8}{M_0}=61.3648-\frac{50}{0.08475}=2.3648$$
> So Greece will receive a positive cash inflow at$t=0$under Goldman conditions.
> The value of the currency swap will be
> $$V^{Swap, \$}=B^{\$}-B^{e}\cdot M_{0}+V^{EoP_{0}, USD}=52.5778-68.2444\cdot0.8475+2.0066=-3.25484 {}$$Another interpretation of the question could have been to assume that the notional of the Euro bond was also changed to$N^e=61.3648$using the fictitious exchange$${} V_0^{EoP_0, USD}=N^e\cdot M_0-N^{USD} =61.3648\cdot0.8475-50=2.0040$$Alternatively if we wanted to compute the value of the exchange of principal in EUR we would have simply done
$$V_{0}^{E o P_{0}, \, e}=N^{e}-\frac{N^{8}}{M_{0}}=61.3648-\frac{50}{0.08475}=2.3648$$
> So Greece will receive a positive cash inflow at t = 0 under Goldman conditions. The value of the currency swap will be$${} V^{Swap, USD}=B^{\$}-B^{e}\cdot M_{0}+V^{EoP_{0}, \, \$}=52.5778-68.2444\cdot0.8475+2.0066=-3.2548$$
> Another interpretation of the question could have been to assume that the notional of the Euro bond was also changed to$N^e = 61.3648$using the fictitious exchange rate. Such interpretation would have led to the same directional result,  but with larger numbers,  therefore does not affect the grade. In this case we would have had$B^e = 70.9796$and$V^{*Swap, *USD} = −5.5730$.
>
> Wait a second,  the value of the swap is negative! Why would Greece accept something like this? One possible reason1 might be that the mark to market of the currency swap is not recognized as sovereign debt. Thus with the cash received at inception Greece could have paid a portion of its outstanding debt. In theory we expect that the value of the outstanding debt does not change (as we have a swap with negative market value); however,  since the swap value did not account for as debt according to EUROSTAT (the institutions who takes care of collecting all Euro countries data on debt,  deficit,  GDP,  etc..),  Greece could have reduced its reported debt on year 2001. Of course,  with the invented data provided,  this trick would have costed Greece a lot of money (3.25 billion of dollars).

# 2          HEDGING WITH OPTIONS: SOUTHWEST JET FUEL HEDGING PROGRAM

Consider again the hedging strategy of Southwest Airlines (see Homework 2). We are back on December 31st 2007. Instead of using commodity futures,  the CFO is considering buying insurance on oil prices using options. Table 2 reports the prices,  on December 31st 2007,  of a set of European call and put options on crude oil. All options expire on March 31st 2008 and can only be exercised at maturity. Each options’ underlying is one lot of 1, 000 crude oil barrels,  which equals 42, 000 gallons of crude oil.

| Call options |  | Put options |  |
| ---- | ---- | ---- | ---- |
| Strike Price | Option Price | Strike Price | Option Price |
| 60 | 35, 674 | 60 | 3 |
| 65 | 30, 744 | 65 | 17 |
| 70 | 25, 859 | 70 | 76 |
| 75 | 21, 098 | 75 | 259 |
| 80 | 16, 593 | 80 | 698 |
| 85 | 12, 513 | 85 | 1, 562 |
| 88.61 | 9, 923 | 88.61 | 2, 541 |
| 90 | 9, 016 | 90 | 3, 009 |
| 95 | 6, 195 | 95 | 5, 132 |
| 100 | 4, 060 | 100 | 7, 941 |
| 105 | 2, 541 | 105 | 11, 366 |
| 110 | 1, 522 | 110 | 15, 292 |
| 115 | 875 | 115 | 19, 589 |
| 120 | 485 | 120 | 24, 142 |
| 125 | 259 | 125 | 28, 861 |
| 130 | 135 | 130 | 33, 680 |

**Table 2. Crude oil options prices on December 31,  2007,  USD per lot**

Given the data in Table 2:

1. Assume that the CFO decides to buy the$105 strike call options on oil (we can refer to this strategy as a **straight insurance**).

(a)   How many options should be bought? In computing the number of options, make the (somewhat unreasonable) assumption that 1 barrel of oil is sufficient to produce 1 barrel of jet fuel,  that a$1 price change of crude oil per barrel barrel,  always causes a$1 price change of jet fuel per barrel,  that is the same as a$\frac{1}{42}=$0.02381 price change of jet fuel per gallon and that all fuel is consumed on March 31st 2008.

```python
- Back to Dec 2017,  we need to hedge 94,  437,  500 * 3 month = 283, 312, 500 gallon of fuels for Q1 2008.
- Barrel of oil should be hedged: 283, 312, 500/42 = 6, 745, 536 barrels
- Number of options to buy: 6, 745, 536 /1000 = 6745.536 options
```

> [!ANSWER] Part 2. Hedging With Options: Southwest Jet Fuel Hedging Program
>
> (1.a) First,  assuming that all fuel is consumed on March 31st 2008 allows us to match the > cash flows of the options with the cash flows required by purchasing the fuel,  so we will not have any issues related to time value of money. Second,  with the assumptions that 1 barrel of oil is sufficient to produce 1 barrel of jet fuel and that a 1 USD price > change of crude oil per barrel causes always a 1 USD price change of jet fuel per barrel we can easily determine the number of options. The reasoning is as follows. > Let's assume that the CFO wants to hedge 75% of its fuel consumption for Q1 2008.
>
> We know that the expected fuel consumption for 2008 is 1,  511 million of gallons,  thus > the expected Q1 consumption is$1, 511/4 = 377.75$million of gallons. With a 75% hedge,  > the quantity to be hedges is 377.75 · 0.75 = 283.3125 million of gallons,  or,  in barrels,  > 1We are not accusing any person,  but we rather are suggesting one of many possible interpretations of$283.3125/42= 6.7455$million. If fuel price per barrel rises by 1 USD between Dec 31st and March 31st 2008 we will loose 6.7455 million of dollars (i.e. 1 USD for each barrel of consumption). To hedge this exposure we want to buy a number of options such that if oil price raises by 1 USD we will gain exactly (remember that our gain and losses are all computed at time t = T,  that is on March 31st 2008) USD 6.7455 million. Now if the oil price is below the option strike we will not get anything from the option,  but if for example crude oil price per barrel increases from 105 USD to 106 USD we will gain 1, 000 USD for each option (remember that each option trades on a lot of 1, 000 barrels). By assumption we expect oil and jet prices to move exactly by the same dollar amount,  so if oil price per barrel increases by 1 USD,  fuel price per barrel will increase by 1 USD. If we define by$\triangle P^{Oil}$the change in oil price per barrel,  by$Payoff^{fuel}(\triangle P^{Oil})$the payoff on our fuel position that we experience from a change in oil price (per barrel) equal to USD$\triangle P^{Oil}$and by$Payoff^{option}(\triangle P^{Oil})$the option payoff arising from a change in oil price (per barrel) equal to USD$\triangle P^{Oil}$we can compute the number of options to be bought as$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}$$
> Let's assume$\triangle P^{Oil}=1$dollar,  we then get$Payoff^{fuel}(\triangle P^{Oil})=-6.7455$million of dollars (i.e. for each dollar price change of oil per barrel,  since by assumption fuel price per barrel will also change by 1 USD per barrel,  we loose 6.7455 million of dollars) and$Payoff^{option}(\triangle P^{Oil})=1, 000$dollars. Putting all together we have:$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=\frac{-6, 745, 500}{1, 000}=6, 745.5$$which we will round up to 6, 746. If we instead assume a 100% hedge of expected fuel consumption we would have had$FC^{hedged}= E[FC^{Q1}] = \frac {377.75}{42}= 8.9940$million of barrels and using the same reasoning as above$$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=-\frac{-8, 994, 000}{1, 000}=8, 994$$

(b)   How does your answer in (1.a) change if we assume that a$1 price change of crude oil per barrel,  always causes a$1.1964 price change of jet fuel per barrel? Maintain the (still unrealistic) assumption that 1 barrel of oil is sufficient to produce 1 barrel of jet fuel.

```python
- b)	We need to hedge more for each barrel of the jet fuel with the new ratio 1.1964. 
- New barrels to hedge = barrels to hedge * hedge ratio = 8, 070, 359 barrels
- Options to buy: 8070359/1000=8, 070.359
- This change brought us a increase of 8070.359 – 6745.536 = 1, 324.8230
```

> [!ANSWER]
> (1.b) From now on let's keep the$100\%$hedge for simplicity. Using equation (3),  simply note that$$Payoff^{fuel}(\triangle P^{Oil})=Payoff^{fuel}(\triangle P^{fuel}=1)\cdot\triangle P^{fuel}(\triangle P^{Oil})$$so the payoff on our fuel position from a change in oil price per barrel equal to$\triangle P^{Oil}$USD is equal to the payoff on fuel position arising from a 1 USD change in fuel price$($per barrel$)$times the fuel price (per barrel) change due to a change in oil price (pen barrel) equal to$\triangle P^{Oil}.$Moreover we can write$\triangle P^{fuel}(\triangle P^{Oil})=\triangle P^{fuel}(\triangle P^{Oil}=$$1)\cdot\triangle P^{Oil}$. Plugging numbers we get:$$\begin{aligned}^{fuel}(\triangle P^{fuel}=1)\cdot\triangle P^{fuel}(\triangle P^{Oil}=1)\cdot\triangle P^{Oil}=\end{aligned}$$$$Payoff^{fuel}(\triangle P^{Oil})=\quad-8, 944, 000\cdot1.1964\cdot\triangle P^{Oil}$$and therefore
> $$N^{opt}=-\frac{Payoff^{fuel}(\triangle P^{Oil})}{Payoff^{option}(\triangle P^{Oil})}=-\frac{-8, 944, 000\cdot1.1964\cdot\triangle P^{Oil}}{1, 000\cdot\triangle P^{Oil}}=10, 760$$

(c)    Suppose that you have bought the number of call options determined in (1.a). If the assumptions mentioned in point (1.b) are true,  how would your (1.a) strategy perform? Would you be over-hedged or under-hedged?

```python
- c)	We would be under-hedged by approximately 1325 options. 
```

> [!ANSWER]
> (1.c) Let's compare the case for 100% hedging. From point (1.a) we would have bought 8, 994 options,  while from point (1.b) we would have bought 10, 760 options. Now we would have paid less in point (1.a) but we would have had a lower payoff. Indeed under (1.a) assumptions,  the expected payoff from 1 dollar change in fuel price per barrel was USD - 8, 994, 000,  and this was matched by the expected options' payoff calculated point (1.a). Under (1.b) assumptions,  the expected payoff from 1 dollar change in fuel price per barrel was USD - 10, 760, 000,  and this was matched by the expected options' payoff calculated point (1.b); this expected payoff,  however,  is greater,  in absolute value,  than the payoff we could get from the options bought in point (1.a). Therefore with the options bought in point (1.a) we are not fully covering the expected (negative) payoff from the implicit short position in fuel. With such an amount of options Nopt = 8,  994 we are therefore under-hedged if the assumptions in (1.b) are true.

(d)   How does your answer in point (1.b) change if we assume that to produce1 barrel of jet fuel one needs to employ 1.1964 barrels of oil? Why are the answers in point (1.b) and (1.d) different or the same? (Tip: don’t spend more than 2 minutes on this. Just think about the implication for the relationship between jet fuel price and oil price if you assume that you need 1.1964 units of oil to produce 1 unit of fuel.)

```python
- In both scenarios,  we need to buy more options but they are different.
- In (1.b),  we are hedging against a greater financial exposure per barrel (price risk),  and in (1.d),  we are hedging against a greater volume exposure (quantity risk). 
```

> [!ANSWER]
> (1.d) The answer does not change. Just note that if we need 1.1964 barrels of oil to produce
> 1 barrel of fuel,  when the price of oil changes by 1 dollar,  fuel price will change by 1.1964 dollars. The reason is that to produce 1 barrel of fuel,  refiners will need to buy 1.1964 barrels. They will pay an extra difference of 1 dollar per barrel of oil bought. Since they will buy 1 barrel plus 0.1964 barrels they will pay 1 extra dollar on the first barrel and 0.1964 extra dollars on the 0.1964 barrels. Therefore this would lead to the same results computed in point (1.b).

(e)   Under no hedging,  Southwest position is _de facto_ a short position on jet fuel between December 31st 2007 and March 31st 2008. Indeed if fuel price goes up Southwest is loosing money as it has to spend more to buy the same amount of fuel; conversely if jet fuel price falls,  Southwest experiences a gain as it can buy the same quantity of fuel at a lower price. With this in mind,  draw the payoff diagram,  at maturity,  of the implicit short position that Southwest has on jet fuel.

-  ![500](22fbf52af579c7888de2c.png)

> [!ANSWER]
> (1.e) Just a little note here before showing the graph. The payoff diagram (in contrast with > the profit diagram) does not take into account the cost of the position. For example,  > for a short position in fuel,  we do not consider S0 but only −ST. So at time T,  we > will have necessarily a non positive (i.e. π(S) ≤ 0 - note that I have randomly chosen > to use π as a synonymous of "payoff") payoff. > The payoff diagram of the implicit short position will thus be: > Note that the payoff is computed on the total exposure,  which is,  under the assumption in point (1.a),  8, 994, 000 barrels of jet fuel (and oil). Further,  consider that if we accept assumptions (1.a),  then the oil price and jet fuel price can be assumed to be the same.
 ![500](2373e22ab534410d2cacfbd8e29676b4.png)

(f)     Now draw the payoff diagram,  at maturity,  of the **straight insurance** strategy determined in (1.a) and,  in another chart,  the diagram of the overall position of Southwest,  that is the implicit short position in jet fuel plus the **straight insurance**; please label the axes of the diagram,  specify the units of measure and show some values on each axis. Compare the costs and benefits of the **straight insurance** with the costs and benefits of hedging with futures.
 ![500](2baf67b653ef3159edac758f08b2931f.png)

> [!ANSWER]
> (1.f) The payoff diagram of the straight insurance is: ![500](921429ef02602abd9cbea9add66ad2c6.png)
> And the one of the overall position,  combining the implicit short position with the straight insurance,  is: ![500](7119b15cd978dff405cdf1534e4ccbca.png)

1. Assume that the CFO is a Booth alumni,  and reasons that one drawback of thestraight insurance is that it costs money upfront. Instead he decides to set up a **collar**,  that is,  sell some out-of-the-money put options to finance the purchase of out-of-the-money calls. The goal of this collar is that it must **cost nothing** (or near to nothing) to the firm at initiation. In other words,  the total amount from the puts must compensate for the calls.

(a)   Keeping the same strike for the insurance (call) as in point (1.a) above,  findthe strike of the put option that the CFO must sell to achieve the **zero-cost collar strategy**. To determine the total number of options (calls and puts),  you make the same assumptions as in point (1.a) above.

```python
-  a)	Buy 6, 746 call options with a strike price of $105 at a total cost of $17, 141, 586 (6, 746 options $2, 541 per option)
To achieve a zero-cost collar strategy,  the CFO should sell put options with a strike price of $88.61. Selling the same number of put options as the call options purchased (6, 746) would generate enough premium to offset the cost of buying the call options.
```

> [!ANSWER]
> (2.a) We look for p such that c = p. Since c (Kc = 105) = 2,  541,  we find in the table that Kp,  such that p (Kp) = 2,  541. This is for Kp = 88.61

(b)   Draw the payoff diagram,  at maturity,  of the **collar** strategy determined in (2.a) and,  in another chart,  the diagram of the overall position of Southwest: the implicit short position in jet fuel plus the **collar**; please label the axes of the diagram,  specify the units of measure and show some values on each axis. Compare the costs and benefits of the **collar** with the costs and benefits of both the straight insurance and the hedging with futures.

-  ![500](bfc119fc0c2267adcef98358eabfedc3.png)

```python
Comparison: 
Collar strategy: 
	Cost: limitation of the benefit gained from decreasing prices
	Benefit: no need to pay premium when hedge the risk,  and no upfront cost like straight insurance

Straight insurance: 
	Cost: upfront cost
	Benefit: unlimited upside protection against price increases

Hedging with futures:
	Cost: no flexibility since the contract is fixed. The firm could not get any benefit from price decreasing
	Benefit: full protection against price increasing
```

> [!ANSWER]
> (2. B) The payoff of the collar strategy is: ![500](dc8721b42f306b86f95a6d066dbd128d.png)
> and the one of the overall position,  combining the implicit short position with the collar,  is: ![500](54aa611314fd62dc1f968f99e483ff49.png)

1. Assume now that the CFO is a Booth student who is taking the Financial Instruments course and is very excited about the variety of different options strategies. Instead of selling just one put option to finance the purchase of the call option (used for insurance) as in point 2,  the CFO wants to experiment different quantities of put options,  still maintaining the constraint that the cost of the strategy must be zero.

(a)   If the CFO chooses the$80 strike put options,  how many options does he have to sell to set up the collar?

```python
- With $80 strike price,  the option price is 698. To cover the total cost of buying the 6, 746 call options,  we have to sell 24558 put options. 
```

> [!ANSWER]
> (3.a) Since the collar strategy has to be zero cost,  we look for a number of put options$N^p$
> such that
> $$N^{p}=-{\frac{N^{c}\cdot c}{p}}$$
> we find Np(K2=80) = −32,  742. So we have to short 32, 742 put options with strike equal to K2 = 80.
(b)   How would your answer in point (3.a) change if the CFO chooses the$90 strike put options?

```python
- If choose the $ 90 strike price,  the option price is $3009 now. We have to sell 5697 options to cover the call options we bought. 
```

Draw the payoff diagrams,  at maturity,  of these two new strategies as well as of the overall Southwest position in each case. Please label the axes of the diagrams,  specify the units of measure and show some values on each axis. Compare the costs and benefits of the two strategies with the costs and benefits of both the straight insurance and the first collar determined in point
 ![500](d838931709b0d991efc4da0d5bc74977.png)
Comparison:

```python
$80 Put Collar: 
Cost: lower floor price (higher potential losses)
Benefit: more potential gains if the price of jet fuel decreases

$90 Put Collar
	Cost: limits the potential gains compared to the $80 put collar
Benefit: higher floor price (lower potential losses)

Straight Insurance: 
Benefit: unlimited upside protection against price increases 
Cost: the option premiums.
```

> [!ANSWER]
> (3.b) We find Np(K3=90) = −7,  596. So we have to short 7, 596 put options with strike equal > to K3 = 90. The payoff of the collar with the K2 = 80 puts is reported in the next figure. ![500](caf6abb34fe52e308aea0a51266e86ad.png)
> While the payoff of the collar with the K 3 = 90 puts is shown below. ![500](dbb91e14e07f3848b5c73c0ce0d273db.png)
>  ![500](a63132683515b6a931f8785ad6c81c36.png)
>
> The payoffs of the two overall positions are then shown. ![500](70c9356ec6e31915dbdbc6449028c3b9.png)
> Finally it is worth to compare the payoffs of the three collars in one chart… ![500](b53d23e67d2e0c11a6544165b9f891d1.png)
>

(2.a).

```python
First Collar (2.a): 
Benefit: balance the cost of insurance with the protection provided,  allowing for some gains if the price decreases and capping the losses if the price increases.

Hedging with Futures: 
Benefit: full protection against price movements 
Cost: no flexibility and limited downside of options
```

(c)    If you would have set up a bear spread,  how would its payoff have comparedwith the payoff of the portfolio discussed in point (2.b) (i.e. the collar determined in point (2.a) plus the implicit short position on fuel)? Which strategy is more expensive? Why? (No need to carry out calculations; just provide an intuition. Tip: drawing payoff diagrams helps intuition with intuition.)

```python
If we set up the bear spread,  there will be an extra maximum potential loss coming from the cost,  which is the premium paid for the long put minus the premium received for the short put. So,  normally bear spread is more expensive.
```

> [!ANSWER]
> (3.c) Southwest Airlines payoff displayed in figure 5 has the general same pattern as a
> standard bull spread,  except that that the payoff is always negative. The bull spread must have a positive premium while premium for the net payoff displayed in figure 5 must be negative.

(d)   While the CFO is on a plane to Italy,  he thinks that he would like to knowwhat is the continuously compounded interest rate implied by the options markets market. As “all electronic devices have been turned off”,  he does not have access to any additional data. He just remembers that the spot price of oil on December 31,  2007 was$95 per barrel and that the maturity of the quoted options was _T_ = 0_._25 years. How can he compute the implied continuously compounded interest rate using option prices? (Tip: is there any relationship that holds between put and call prices?)

- From formula of put call parity we know:
$$P=C+e^{-r\ast T}\times K-S_0$$
thus, $$\ r=\frac{1}{T}\ln(\frac{C-P+K}{S_0})$$
apply\ the\ information\ he\ remembers, \$$r=\frac{1}{0.25}\ln(\frac{C-P+K}{\$95})$$
He can use this relationship to calculate compounded interest rate with call option price and put price and strike price.

> [!ANSWER] (3.d) You (should… sorry,  MUST) know the put call parity:
>
> $$c-p=S_{0}-K\cdot e^{-r\cdot T}\tag{4}$$
> Thus if we are interested to know r,  we can actually derive it from equation (4). We have to follow very simple steps. We can rewrite (4) as:$$K\cdot e^{-r\cdot T}=S_{0}-c+p$$dividing by$K$$$e^{-r\cdot T}={\frac{S_{0}-c+p}{K}}$$taking (natural) logs$$-r\cdot T=l n\left({\frac{S_{0}-c+p}{K}}\right)$$it follows that$$r=-\frac{ln\left(\frac{S_{0}-c+p}{K}\right)}{T}\tag{5}$$
> If we apply formula (5) to any pair of options provided we get (with some small rounding errors due to option prices approximation) that r = 4.5%.

---

[[Lecture 1- Probability Distributions of Returns]](#_ftnref1) This exercise is motivated by a real deal between Goldman Sachs and Greece. However,  **all** of the details in this exercise are fictitious,  as details of the deal are not known. For initial reference,  please visit https://www.goldmansachs.com/media-relations/in-the-news/archive/greece.html