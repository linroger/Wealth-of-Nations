---
aliases:
- Alias_271_Swaps Complete.md
- SWAPS LECTURE NOTES
- Alias_268_Swaps Complete.md
linter-yaml-title-alias: SWAPS LECTURE NOTES
tags:
- tag_example
title: SWAPS LECTURE NOTES
---



[Interest Rate Derivatives](Teaching%20Notes%2010-%20Interest%20Rate%20Derivatives.md)# SWAPS COMPLETE

# SWAPS LECTURE NOTES

## **THE SWAP LOGIC**

- A swap involves adding a contract to an existing asset to form a basket,  such that the market risk or volatility of the basket is identical to the original asset.
- This added contract is like a "zero" in finance - when added to a portfolio,  it does not change the risk characteristics.
- The equivalent of "zero" in finance is a LIBOR-based forward contract. It has zero value at all times before expiration.
- Adding this "zero" contract can change other characteristics of the asset:
	 - Move it off balance sheet
	 - Change registration,  regulatory,  tax treatment
	 - Require no upfront cash
	 - Increase liquidity

## **APPLICATIONS OF THE SWAP LOGIC**

- The swap logic can be applied to different asset classes to create swaps:
	 - **Equity swaps**: Add a LIBOR-based "zero" contract to a stock portfolio
	 - **Currency swaps**: Add to a foreign currency portfolio
	 - **Commodity swaps**: Add to a commodity portfolio
	 - **Credit default swaps**: Add to a defaultable bond portfolio
- These lead to some of the largest derivatives markets.

## **FEATURES OF A GENERIC SWAP**

- A swap exchanges two sequences of cash flows without initial net payment.
- A spread is adjusted so parties are willing to exchange the cash flows.
- Time t0 value of the swap is zero.
- As time passes,  the swap may gain positive or negative value.
- In practice,  only the net amount is exchanged if cash flows are in same currency.

## **TYPES OF SWAPS**

- **Non-interest rate swaps**:
	 - **Equity swaps**: Exchange equity returns for LIBOR
	 - **Commodity swaps**: Exchange commodity price returns for LIBOR
	 - **Currency swaps**: Exchange foreign currency returns for LIBOR
- **Interest rate swaps**:
	 - Exchange fixed rate cash flows for floating LIBOR-based cash flows
	 - Largest derivatives market
- **Credit default swaps**:
	 - Exchange default risky bond cash flows for LIBOR
	 - Protect against credit risks

## **EQUITY SWAPS**

An equity swap allows an investor to gain exposure to an equity portfolio without directly purchasing the underlying stocks. It involves exchanging floating rate payments against the total return of an equity portfolio.

![[Untitled 4 10.png|Untitled 4 10.png]]

### **CONSTRUCTION OF AN EQUITY SWAP**

Consider a portfolio of stocks with value S_{t_{0}} at time t_{0}. We construct an equity swap on this portfolio over a period $[t_{0},   T]$ as follows:

- Divide the period into equal intervals of length$δ$﻿ (e.g. 3 months) with settlement dates$t_{1},   t_{2},   …,   t_{n} = T.$﻿
- At each t_{i}:
	 - Investor pays:
		  - LIBOR rate$L_{t_{i}} * δN$﻿
		  - Plus a spread s_{i} to compensate for dividends
	 - Investor receives:
		  - Total return on equity portfolio =$δS_{t_{i}}$﻿
- This results in exchanging:
	 - $(L_{t_{i}} + s_{i} - d_{i})δN$﻿

	 Against

	 - $δS_{t_{i}}$﻿
- No upfront payment is required. The spread s_{i} is set to make the initial value zero.
- The investor gets equity exposure without purchasing the underlying stocks.

### **EQUITY SWAP VALUATION**

- The market expects the portfolio value S_{t_{i}} to change by (L_{t_{i}} - d_{t_{i}}) each period.
- In other words:
	 - E[δS_{t_{i}}] = (L_{t_{i}} - d_{t_{i}})
- This can be derived using the fundamental theorem of asset pricing.

Equity swaps allow gaining equity exposure without direct cash investments,  changing the regulatory and accounting treatment of the position.

---

---

$\begin{align*} \text{Party A} & \quad \xrightarrow[\text{Discount Rate}]{\text{LIBOR Rate}} \quad \text{BASIS SWAP} \quad \xrightarrow[\text{LIBOR Rate}]{\text{Discount Rate}} \quad \text{Party B} \\ \end{align*}$

$A \xrightarrow{\text{LIBOR}} B \xleftarrow{\text{Discount Rate}} A$

---

## **SWAP CONTRACTS**

A swap contract involves exchanging cash flows between two parties at settlement dates {t_{i}}.

### **STRUCTURE OF A BASIC SWAP**

- There are two cash flows exchanged in a basic swap contract:
	 - C(S_{t_{0}}; x_{t_{i}}): Cash flows based on a reference asset S selected at time t_{0} and variable x at settlement dates {t_{i}}
	 - B(y_{t_{i}}): Fixed cash flows based on parameter y at settlement dates {t_{i}}
- The two parties agree to exchange these cash flows without any initial cash payment.
- One party pays the C(S_{t_{0}}; x_{t_{i}}) flows and receives the B(y_{t_{i}}) flows.
- The counterparty does the reverse - pays the B(y_{t_{i}}) flows and receives the C(S_{t_{0}}; x_{t_{i}}) flows.

### **NET CASH FLOWS**

- If the cash flows are in the same currency,  there is no need for two separate payments at each t_{i}.
- One party can pay the counterparty the **net** cash flow amount.
- The net cash flow at each t_{i} is:
	 - Party 1 pays: C(S_{t_{0}}; x_{t_{i}}) - B(y_{t_{i}})
	 - Party 2 pays: B(y_{t_{i}}) - C(S_{t_{0}}; x_{t_{i}})
- What one party receives is equal to what the counterparty pays.

---

FUTURES: EUROCURRENCY CONTRACTS

---

### FRA CONTRACTS AND EUROCURRENCY FUTURES CONTRACTS

- **FRA Contracts**: Involves exchanges of interest payments associated with a floating and a fixed-rate loan.
- **Eurocurrency Futures Contracts**: Trade future loans indirectly and result only in an exchange of interest rate payments,  but with some differences from FRA contracts.
	 - **Trading Homogenized Contracts**: Eurocurrency futures trade the forward loans (deposits) as homogenized contracts.
	 - **Deposit Lock**: The buyer locks in a future deposit rate but does not deliver the deposit itself.
	 - **Cash Settlement**: At expiration date$t_{1}$,  the contract is cash settled.
	 - **Price Denotation**: The price of the futures contract quoted in the market is denoted by Qt0Q_{t_{0}}Qt0.

### UNDERSTANDING THE EURODOLLAR CONTRACT

The buyer of a 3-month Eurodollar contract “promises” to deposit 100(1−Ft~0+14)100(1 - F\\tilde{t}_{0} + \\frac{1}{4})100(1−Ft~0+41) dollars at expiration date $t_{1}$ and receive 100 in 3 months. The implied annual interest rate on this loan is then calculated by a specific formula.

- **Price Quotations and Forward Rates**: The price quotations are related to forward rates through a specific formula.
- **Interest Rate Convention**: The interest rate convention for forward loans is equivalent to a money market yield.
- **Futures Contracts**: Use a convention similar to discount rates to calculate the time$t_{1}$value of the forward loan.

### EXAMPLE: INTERBANK MONEY MARKET LOAN

Consider the interbank money market loan as shown in Figure 4.1.

- **Loan Principal**: 100,  paid at time$t_{1}$.
- **Interest and Principal Reception**: At$t_{2}$.
- **Interest Rate**: LIBOR rate$L_{t_{1}}$,  observed at time$t_{1}$.
- **Forward Contract**: 100 is borrowed at$t_{1}$,  and the prevailing interest rate is paid at that time.

Mathematically,

- The$t_{2}$cash flows are given by: 100+100Lt1δ100 + 100 L_{t_{1}} \\delta100+100Lt1δ (4.1)
- Discounting this value to time$t_{1}$: 100(1+Lt1δ)1+Lt1δ\=100\\frac{100\\left(1+L_{t_{1}} \\delta\\right)}{1+L_{t_{1}} \\delta} = 1001+Lt1δ100(1+Lt1δ)\=100
- Total value of the cash flows generated by the forward loan contract: Exactly zero for all times ttt during the interval$t0,  t1$.

### SPECIAL PROPERTIES OF LIBOR CONTRACTS

- **Value Denotation**: Denoting the value of this forward contract by VtV_{t}Vt.
- **Volatility**: Volatility(Vt)\=0\\text{Volatility}(V_{t}) = 0Volatility(Vt)\=0 for all t∈{t0;t1}t \\in \\{t_{0}; t_{1}\\}t∈{t0;t1}. Adding this contract to any portfolio doesn't change its risk characteristics.
- **Equivalence to Zero**: The asset VtV_{t}Vt is equivalent to zero as it doesn't change the market risk characteristics of a portfolio.
- **Changes in the Original Asset**: The addition of VtV_{t}Vt may change the original asset in important ways,  such as:
	 - **Off-Balance Sheet Movement**: Essentially,  nothing is purchased for cash.
	 - **Change in Registration Properties**: No basic security is purchased.
	 - **Change in Regulatory and Tax Treatment**: Makes the modified asset much more liquid.
	 - **No Up-front Cash**: Needed to take the position.

### ADVANTAGES OF SWAPS

Swaps have several important advantages including:

1. **Geographical Flexibility**: Swaps can be done anywhere,  not limited to specific regions like buying US Treasury bonds.
1. **Natural Extension**: Swapping cash in trade funding aligns with daily work of market practitioners.
1. **No Default Risk**: No loan is extended by any party in a swap.
1. **Favorable Treatment**: Accounting,  tax,  and regulatory treatment of the new basket may be more advantageous.

### EQUITY SWAPS

### EXAMPLE: PORTFOLIO OF STOCKS

Consider a portfolio of stocks whose fair market value at time $t_{0}$ is denoted by $S_{t_0}$

- **Equity-Swap Contract**: Divided into equally spaced intervals of length δ\\deltaδ,  with settlement dates$T=t_{1},   t_{2},   t_{3},  \ldots,   t_{n}$
- **Investment Process**:
	 1. N = 100 is invested at time$t_{1}$.
	 1. Total dividends amounting to$d$are collected at every (

---

### THE INSTRUMENT: SWAPS (CONTINUED)

### STRUCTURE OF SWAPS

Swaps can be structured to exchange various cash flows depending on different factors. Continuing with our analysis:

### FIGURE 4.4B - CASH FLOWS IN SWAPS

In Figure 4.4b,  we represent another strip of cash flows:

- fB(y_{t_{0}}); B(y_{t_{1}}); B(y_{t_{2}}); \\ldots; B(y_{t_{k}})
- These cash flows depend on a vector of interest rates denoted by ytiy_{t_{i}}yti.
- A swap can be devised where these two cash flow sequences are exchanged.

### PRINCIPLES OF SWAPS DESIGN

1. **Initial Value of Swap Contract**: A swap is arranged as a pure exchange of cash flows and should not require any additional net cash payments at initiation. The initial value of the swap contract should be zero.
1. **Swap Spread Specification**: The contract specifies a swap spread. This variable is adjusted to make the two counterparties willing to exchange the cash flows.

---

### FUTURES: EUROCURRENCY CONTRACTS

### INTRODUCTION

- Futures and FRA contracts have similarities and differences.
- Both involve exchanges of interest payments.
- However,  the Eurodollar futures contracts trade future loans indirectly.
- The settlement will be in cash.
- Eurocurrency futures contracts do not deliver the deposit itself.

### EUROCURRENCY FUTURES CONTRACTS

- These contracts deal with loans and deposits in Euromarkets.
- The buyer of the Eurodollar futures contract is a potential depositor of 3-month Eurodollars and will lock in a future deposit rate.
- At expiration date$t_{1}$,  the contract is cash settled.

### MATHEMATICAL DERIVATION

- Suppose we denote the price of the futures contract quoted in the market by Qt0Q_{t_{0}}Qt0.
- The buyer of a 3-month Eurodollar contract “promises” to deposit 100(1−F t0+14)100(1 - F~t_{0} + \\frac{1}{4})100(1−F t0+41) dollars at expiration date$t_{1}$and receive 100 in 3 months.
- The implied annual interest rate on this loan is then calculated by a specific formula.

### INTEREST RATE CONVENTIONS

- For forward loans: equivalent to a money market yield.
- For futures contracts: use a convention similar to discount rates.

---

### CONSIDERATIONS FOR INTERBANK MONEY MARKET LOAN

### OVERVIEW

- **Loan Principal**: 100 and is paid at time$t_{1}$.
- **Interest and Principal**: Received at$t_{2}$,  hence this is a default-free loan to be made in the future.
- **Interest Rate**: LIBOR rate Lt1L_{t_{1}}Lt1 to be observed at time$t_{1}$.
- **Forward Contract**: Written on this loan.

### VALUE OF FORWARD LOAN CONTRACT

- The$t_{2}$cash flows are 100+100⋅Lt1⋅δ100+100 \\cdot L_{t_{1}} \\cdot \\delta100+100⋅Lt1⋅δ (4.1)
- Discounting this value to time$t_1$﻿_,  we get_

$\frac{+\left(1+L_{t_{1}} \delta\right) 100}{1+L_{t_{1}} \delta}=100$

- Total value of cash flows is exactly zero for all times ttt during the interva lt0,  t1,  no matter what the market thinks about the future level of Lt1L_{t_{1}}Lt1.
- Special property of LIBOR contracts: Volatility$V_t = 0$﻿ _for all t∈{t0;t1}_,  not changing the risk characteristics of a portfolio.

### EFFECTS OF ADDING FORWARD LOAN CONTRACT TO PORTFOLIO

1. **Off-Balance Sheet Movement**: The asset may move the StS_{t}St off-balance sheet.
1. **Registration Changes**: No basic security is purchased.
1. **Regulatory and Tax Treatment Changes**.
1. **Liquidity Enhancement**: No up-front cash needed to take the position.

---

### **DETERMINING THE FAIR FIXED RATE**

- To achieve a fair swap where both legs have equal value at initiation,  the fixed cash flow B(y_{t_{i}}) must be chosen properly.
- Define:
	 - V_{b} = Present value of the fixed B cash flows
	 - V_{f} = Present value of the floating C cash flows
- By put-call parity,  there exists a fixed rate B* such that:
	 - V_{b}* = V_{f}
- B* is the **fair fixed rate** that equalizes the values of the two swap legs.
- If the agreed fixed rate B ≠ B*:
	 - **Seller value** = V_{b} - V_{f}
	 - **Buyer value** = V_{f} - V_{b}
- The buyer has positive value if B < B*.
- The seller has positive value if B > B*.
- **Seller value + Buyer value = 0** at initiation.

---

These valuations illustrate that the floating-rate payer (swap buyer) would prefer as low a fixed rate as possible,  while the fixed-rate receiver (swap seller) would want as high a fixed rate as possible. The fair fixed rate B* is the rate at which both parties are willing to enter into the swap contract without any upfront payment from one party to the other.

- The buyer wants the lowest possible fixed rate B.
- The seller wants the highest possible fixed rate B.
- B* is the rate where both parties will enter the swap without any upfront payment.

---

Another aspect of swap contracts is the spread usually applied to the floating index to determine the actual floating-rate cash flows. For example,  the floating payments might be specified as:

$$C(S_{t_0}; L_{t_i} + z)$$

where z > 0 is some quoted spread or markup over the floating index L_{t_i}. This spread compensates the floating-rate payer for the index basis risk between S_{t_0} and L_{t_i}. The analysis above still applies. In particular,  the existence of some fair fixed rate B* that equates the swap’s legs must still hold,  accounting for the spread over L_{t_i}.]

### **SPREAD ON THE FLOATING RATE**

- In practice,  a **spread z** is added to the floating index L_{t_{i}}:
	 - C(S_{t_{0}}; L_{t_{i}} + z)
- Where z > 0.
- This compensates the floating rate payer for the basis risk between S_{t_{0}} and L_{t_{i}}.
- The analysis for determining the fair fixed rate B* still applies,  accounting for the spread z.

---

## LECTURE NOTES: UNDERSTANDING PLAIN VANILLA INTEREST-RATE SWAPS

### INTRODUCTION TO INTEREST-RATE SWAPS

A plain vanilla interest-rate swap is a fundamental financial instrument used to exchange interest payments. Here’s a detailed breakdown of its components:

- **Initiation Time**: t_0
- **Notional Amount**: N
- **Settlement Dates**:${t_1,   t_2,  …,  t_n}$﻿
- **Fixed Payments**:$s_{t_0}N\delta$﻿
- **Floating Payments**:$L_{t_i}N\delta$﻿
- **LIBOR Rate**: Determined at${t_0,   t_1,  …,   t_{n-1}}$﻿
- **Maturity**: m years
- **Swap Rate**:$s_{t_0}$﻿

Under these conditions,  the fixed payments equal$s_{t_0}$﻿,  and the LIBOR-linked payments equal$L_{t_0},   L_{t_1},  $﻿ and$L_{t_2}$﻿,  respectively.

### SWAP SPREAD

The swap spread is the difference between the swap rate and the treasury rate on the bond with the same maturity,  denoted by$y_{t_0}$﻿

$\text{Swap spread} = s_{t_0} - y_{t_0}$

### ENGINEERING OF INTEREST-RATE SWAP

We will explore the engineering of this interest-rate swap,  focusing on the ways one can approach this problem.

### REVERSE ENGINEERING A SWAP

A swap can be reverse-engineered in at least two ways:

1. **Horizontal Decomposition**:
	 - Decompose the swap into two streams of cash flows.
	 - One stream represents a floating stream of payments (receipts),  the other a fixed stream.
	 - Each stream can be linked to a certain type of bond.
1. **Vertical Decomposition**:
	 - Slice the swap into n cash exchanges during n time periods.
	 - Each cash exchange can be interpreted similarly to an FRA paid-in-arrears.
	 - The fixed rate is constant across various settlement dates.

### REPRESENTATION AND DECOMPOSITION

- **Long Forward Position**: Figure 4.8c represents a long forward position in an FRN that pays LIBOR flat.
- **Addition and Subtraction of Notional Amount**: This leads to the standard exchanges of floating versus fixed-rate payments.
- **Detaching Cash Flows**: This results in two separate cash flows,  each in the form of a meaningful financial contract.
- **Short Forward Position**: Figure 4.8d represents a short forward position on a par coupon bond that pays a coupon equal to$s_{t_0}$﻿

The immediate decomposition suggests the following synthetic:

$\text{Interest rate swap} = \text{Long FRN with LIBOR coupon; short par coupon bond}$

### SYNTHETIC COUPON BOND

- **Scenario**: A client wants to buy a coupon bond from a AAA-rated entity,  but no such bonds are issued.
- **Solution**: Synthetically create the bond using the representation above.

### PRICING

- **Contractual Equation**: Permits pricing the swap off the debt markets.
- **Special Case**: A 3-year spot swap that makes fixed payments.
- **Fixed Payments**: Three annual coupon payments,  each equaling$s_{t_0}N$﻿.
- **Floating Payments**: Three floating rate payments,  each with the value$L_{t_i}N$﻿,  where the relevant LIBOR$L_{t_i}$﻿is set at$t_{i−1}$﻿but is paid at$t_i$﻿

---

### VALUING FIXED CASH FLOWS

To obtain the present value of the fixed cash flows,  we discount them by the relevant floating rates. If we knew the floating rates$L_{t_0},   L_{t_1},  $﻿ and$L_{t_2}$﻿,  we could write the present value of the fixed cash flows as:

$\text{PV}{\text{fixed}} = \frac{S{t_{0}} N}{\left(1+L_{t_{0}}\right)} + \frac{S_{t_{1}} N}{\left(1+L_{t_{1}}\right)\left(1+L_{t_{1}}\right)} + \frac{S_{t_{2}} N+N}{\left(1+L_{t_{2}}\right)\left(1+t_{t_{1}}\right)\left(1+L_{t_{2}}\right)}$﻿

### A VERTICAL DECOMPOSITION

We now study the second way of decomposing the swap,  considering an annual FRA where the δ=1\delta = 1δ=1,  and the FRA is paid-in-arrear. Then,  at some time ti+δt_i + \deltati+δ,  the FRA parties will exchange the cash flow:$\left(L_{t_{i}}-F\left(t_{0},   t_{i}\right)\right) \delta N$﻿

where N is the notional amount,  $\delta = 1$﻿,  and the$F(t_0,   t_i)$﻿ is the FRA rate determined at time$t_0$﻿

### DECOMPOSING A SWAP INTO FRAS

- **Question**: Is it possible to decompose a swap into nnn FRAs,  each with an FRA rate F(t0,  ti)F(t_0,  t_i)F(t0,  ti),  i=1,  …,  ni = 1,  …,  ni=1,  …,  n?
- **Analysis**: The swap cash flows are split by slicing the swap vertically at each payment date. A fixed payment is made against an unknown floating LIBOR rate,  in each case.
- **Result**: The cash exchanges are not valid contracts individually. The FRA rate F(t0,  ti)F(t_0,  t_i)F(t0,  ti) is determined by supply and demand or by pricing through money markets,  and in general,  F(t0,  ti)≠st0F(t_0,  t_i) \neq s_{t_0}F(t0,  ti)=st0.
- **Implication**: Slicing the swap contract vertically into separate FRA-like cash exchanges does not result in tradeable financial contracts. The time t2t_2t2 exchange has a missing time t0t_0t0 cash flow of size
- $B(t0,  t2)[F(t0,  t1)−St0]δNB\left(t_{0},   t_{2}\right)\left[F\left(t_{0},   t_{1}\right)-S_{t_{0}}\right] \delta NB(t0,  t2)[F(t0,  t1)−St0]δN.$﻿

### PRICING

We have seen that it is not possible to interpret the individual swap settlements as FRA contracts directly. However,  the previous analysis is still useful for pricing the swap since it gives us an important relationship. The time$t_2$﻿ element of the swap has the present value$B(t0,  t2)[F(t0,  t1)−st0]δNB(t_0,   t_2)[F(t_0,   t_1) - s_{t_0}] \delta NB(t0,  t2)[F(t0,  t1)−st0]δN$﻿,  which is not normally zero.

This leads to the following important pricing relation:

$B\left(t_{0},   t_{1}\right)\left[F\left(t_{0},   t_{0}\right)-S_{t_{0}}\right] \delta N + B\left(t_{0},   t_{2}\right)\left[F\left(t_{0},   t_{1}\right)-S_{t_{0}}\right] \delta N + B\left(t_{0},   t_{3}\right)\left[F\left(t_{0},   t_{2}\right)-S_{t_{0}}\right] \delta N = 0$

$PV_{\text{fixed}} \text{ as of } t_0 = \frac{s_{t_{0}}N}{(1+F(t_0,  t_0))} + \frac{s_{t_{0}}N}{(1+F(t_0,  t_0))(1+F(t_0,  t_1))} + \frac{s_{t_{0}}N+N}{(1+F(t_0,  t_0))(1+F(t_0,  t_1))(1+F(t_0,  t_2))}$

$PV_{\text{floating}} \text{ as of } t_0 = \frac{L_{t_{0}}N}{(1+L_{t_0})} + \frac{L_{t_{0}}N}{(1+L_{t_0})(1+L_{t_1})} + \frac{L_{t_{0}}N+N}{(1+L_{t_0})(1+L_{t_1})(1+L_{t_2})}= N$

![[Untitled 5 7.png|Untitled 5 7.png]]

- FUTURES: EUROCURRENCY CONTRACTS
- FRA contracts involve exchanges of interest payments associated with a floating and a fixedrate loan. The Eurodollar futures contracts trade future loans indirectly. The settlement will be in cash and the futures contract will again result only in an exchange of interest rate payments. However,  there are some differences with the FRA contracts. Eurocurrency futures trade the forward loans (deposits) shown in Figure 3.10 as homogenized contracts. These contracts deal with loans and deposits in Euromarkets,  as suggested by their name. The buyer of the Eurodollar futures contract is a potential depositor of 3-month Eurodollars and will lock in a future deposit rate. Eurocurrency futures contracts do not deliver the deposit itself. At expiration date t_{1},  the contract is cash settled. Suppose we denote the price of the futures contract quoted in the market by Qt_{0}. Then the buyer of a 3-month Eurodollar contract “promises” to deposit 100ð1 2 F~t_{0} 1 4) dollars at expiration date t_{1} and receive 100 in 3 months. The implied annual interest rate on this loan is then calculated by the formula
- This means that the price quotations are related to forward rates through the formula
- However,  there are important differences with forward loans. The interest rate convention used for forward loans is equivalent to a money market yield. For example,  to calculate the time t_{1} present value at time t_{0} we let
- Futures contracts,  on the other hand,  use a convention similar to discount rates to calculate the time t_{1} value of the forward loan
- Consider the interbank money market loan as shown in Figure 4.1. The loan principal is 100 and is paid at time t_{1}. Interest and principal is received at t_{2}. Hence this is a default-free loan to be made in the future. The associated interest rate is the LIBOR rate Lt_{1} to be observed at time t_{1}. We write a forward contract on this loan. According to this,  100 is borrowed at t_{1} and for this the prevailing interest rate is paid at that time.
- the value of this forward loan contract for all t ∈{t_{0}; t_{1}}
- The t_{2} cash flows are 100+100 L_{t_{1}} \delta (4.1) Discounting this value to time t_{1},  we get

$\frac{+\left(1+L_{t_{1}} \delta\right) 100}{1+L_{t_{1}} \delta}=100$

- Adding this to the initial 100 that was lent,  we see that the total value of the cash flows generated by the forward loan contract is exactly zero for all times t during the interval [t_{0},  t_{1}],  no matter what the market thinks about the future level of Lt_{1}.
- Denoting the value of this forward contract by Vt,  we can immediately see that VolatilityðVt) 0 for all$t ∈{t_{0}; t_{1}}$﻿ (4.3) Hence adding this contract to any portfolio would not change the risk (volatility) characteristics of that portfolio. This is important and is a special property of such LIBOR contracts.
- Thus let V_t denote the value of a security with a sequence of cash flows so that the security has a value equal to zero identically for all t ∈{t_{0}; t_{1}},  V_1 = 0 (4.4) Let S_{t} be the value of any other security,  with 0,  VolatilityðSt) t ∈{t_{0}; t_{1}} (4.5) Suppose both assets are default-free. 3 Then,  because the loan contract has a value identically equal to zero for all t ∈{t_{0}; t_{1}},  we can write S_{t} 1 Vt = S_{t} (4.6) in the sense that VolatilityðSt 1 Vt) = VolatilityðSt)
- Hence the portfolio consisting of an S_{t} and a Vt asset has the identical volatility and correlation characteristics as the original asset St. It is in this sense that the asset Vt is equivalent to zero. By adding it to any portfolio,  we do not change the market risk characteristics of this portfolio.
- Still,  the addition of Vt may change the original asset in important ways. In fact,  with the addition of Vt: 1. The asset may move the S_{t} off-balance sheet. Essentially,  nothing is purchased for cash. 2. Registration properties may change. Again no basic security is purchased 3. Regulatory and tax treatment of the asset may change. 4. No up-front cash will be needed to take the position. This will make the modified asset much more liquid. =
- Swaps have the following important advantages among others.
- Remark 1: When you buy a US Treasury bond or a stock issued by a US company,  you can only do this in the United States. But,  when you work with the swap,  S_{t} 1 Vt,  you can do it anywhere,  since you are not buying/selling a cash bond or a “cash” stock. It will consist of only swapping cash. Remark 2: The swap operation is a natural extension of a market practitioner’s daily work. When a trader buys an asset,  the trader needs to fund this trade. “Funding” an asset with a LIBOR loan amounts to the same scheme as adding Vt to the St. In fact,  the addition of the zero asset eliminates the initial cash payments.
- Remark 3: The new portfolio will have no default risk In fact with a swap,  no loan is extended by any party. Remark 4: Finally the accounting,  tax,  and regulatory treatment of the new basket may be much more advantageous.
- Consider a portfolio of stocks whose fair market value at time t_{0} is denoted by S_{t_0}. Let t_{n} = T,  t_{0},  ?,  tn,  where T is a date that defines the expiration of an equity-swap contract. For simplicity,  think of tn 2 t_{0} as a 1-year period. We divide this period into equally spaced intervals of length δ,  with$t_{1},   t_{2},   t_{3},  …,   t_{n} = T$﻿ being the settlement dates. Let$δ= \frac{1}{4}$﻿ so that the ti’s are 3 months apart. During a 1-year interval with n = 4,  the portfolio’s value will be changed by

$S_{t_{4}}-S_{t_{0}}=\Delta S_{t_{0}}+\Delta S_{t_{1}}+\Delta S_{t_{2}}+\Delta S_{t_{3}} (4.10)$

We consider buying and marking this portfolio to market in the following manner: 1. N = 100 is invested at time t_{1}. At every t_{1},  i = 1,  2,  3,  4 total dividends amounting to d are collected

- At the settlement dates,  we collect (pay) the cash due to the appreciation (depreciation) of the portfolio value. 4. At time t_{n} = T,  collect the original USD100 invested
- This is exactly what an equity investor would do. The investor would take the initial investment (principal),  buy the stocks,  collect dividends,  and then sell the stocks. The final capital gains or losses will be Stn 2 S_{t_0}. In our case,  this is monetized at each settlement date
- Value of portfolio has not changed any time between t{0} and t{1},  since the forward FRN has value identically equal to zero at any time tA[t,  t_{0}]. 2. But the initial and final N’s cancel. 3. The outcome is an exchange of (L_{t_{i}}) δN (4.12) against (St_{i} - d)δN (4.13) at each t_{i}. 4. Then we can express the cash flows of an equity swap as the exchange of (L_{t_{i}}) 2 d_{i})δN (4.14) against δStiδN (4.15) at each t_{i}. The di being an unknown percentage dividend yield,  the market will trade this as a spread. The market maker will quote the “expected value of” di and any incremental supply demand imbalances as the equity-swap spread. The buyer of the equity swap will need to pay LIBOR (L_{t_{i}}) δN plus a spread while receiving the total return on the equity index,  i.e.,  (St_{i} - d)δN at each t_{i}.. The swap will involve no up-front payment. This construction proves that the market expects the portfolio St_{i} to change by (L_{t_{i}}) - dt_{i}) each period,  in other words,  we have EP t ½δSt_{i} = (L_{t_{i}}) - dt_{i}) (4.16) This result is proved normally by using the fundamental theorem of asset pricing and the implied risk-neutral probability.
- THE INSTRUMENT: SWAPS Imagine any two sequences of cash flows with different characteristics. These cash flows could be generated by any process—a financial instrument,  a productive activity,  a natural phenomenon. They will also depend on different risk factors. Then one can,  in principle,  devise a contract where these two cash flow sequences are exchanged. This contract will be called a swap. To design a swap,  we use the following principles: 1. A swap is arranged as a pure exchange of cash flows and hence should not require any additional net cash payments at initiation In other words,  the initial value of the swap contract should be zero. 2. The contract specifies a swap spread. This variable is adjusted to make the two counterparties willing to exchange the cash flows.
- A generic exchange is shown in Figure 4.4. In this figure,  the first sequence of cash flows starts at time t_{1} and continues periodically at t_{2},  t_{3},  …,  tk. There are k floating cash flows of differing sizes denoted by C(S_{t_0}; x_{t_{1}} {1});C(S_{t_0}; x_{t_{2}}); …;C(S_{t_0}; x_{t_{k}}) (4.17) These cash flows depend on a vector of market or credit risk factors denoted by x_{t_{i}}. The cash flows depend also on the S_{t_0},  a swap spread or an appropriate swap rate. By selecting the value of S_{t_0},  the initial value of the swap can be made zero. Figure 4.4b represents another strip of cash flows: fB(y_{t_{0}); B(yt_{1}); B(y_{t_{2}); …; B(y_{t_{k}) (4.18) which depend potentially on some other risk factors denoted by y_{t_{i}}.
- The swap consists of exchanging the C(S_{t_0}; x_{t_i}) against B(y_{t_{i}}) at settlement dates {ti}. The parameter S_{t_0} is selected at time t_{0} so that the two parties are willing to go through with this exchange without any initial cash payment. This is shown in Figure 4.4c. One will pay the C()’s and receive the B()’s. The counterparty will be the “other side” of the deal and will do the reverse Clearly,  if the cash flows are in the same currency,  there is no need to make two different payments in each period t_{i}. One party can simply pay the other the net amount. Then actual wire transfers will look more like the cash flows as shown in Figure 4.5. Of course,  what one party receives is equal to what the counterparty pays.

[In order for the two complementary C() and B() cash flow legs to achieve such a theoretically fair offsetting,  the fixed B() must be chosen properly so that the swap market value is zero at initiation. Of course the PV of the floating-rate cash flows is not known at the outset since it depends on the future uncertainty,  X_{t_i}. However,  there exists at least one fixed B level that will equate the values. This is just an application of put-call parity In the swap context,  call the fixed leg payer the “seller” of the swap and the floating-rate payer the “buyer” of the swap. Define:

V_{b} = PV of fixed cash flow stream (B)
V_{f} = PV of floating cash flow stream (C)

Put-call parity implies a certain value B* exists such that:

V_{b}* = V_{f}

This defines the fair fixed rate B* such that the two legs have equal value. What if the agreed fixed rate B ≠ B*? Then the value to each party at initiation is:

Seller value = V_{b} - V_{f}
Buyer value = V_{f} - V_{b}

The buyer has positive value if B<B*,  while the seller has positive value if B>B*. Of course,  the sum of values is:

Seller value + Buyer value = 0

Chapter 4 - SWAPS

[[Swaps]]
[[Swaps Lecture Notes]]

## WHAT IS A SWAP?

- Most generally,  a swap is a contract between two parties to exchange one set of cash flows for another. This is a broad definition and covers a wide variety of structures.
	 - Some examples are
		  - Fixed-floating interest rate swaps in a single currency
		  - Cross-currency swaps,  both fixed-fixed and fixed-floating.
		  - Floating-floating basis swaps such as libor versus CP.
		  - Equity and total return swaps
		  - Commodity (price) swaps
- This chapters covers fixed-floating interest rate swaps (IRS) in detail. This type of swap developed early and today is probably the most common with the largest volume in trading.
- We will focus throughout this chapter on a fixed-floating swap where a dealer receives fixed and pays floating.
- Figure 4.1 is the traditional swap diagram showing the direction of cash flows. This type of diagram is useful for laying out an overview of a structure and tracking down what goes where. It is not as useful,  however,  for a detailed understanding of the valuation and risk of a swap.

![swaps-cash-flow2.svg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7e132aca-def6-48bf-a09d-f7e09ce757f9/swaps-cash-flow2.svg)

- Figure 4.2 show a “cash flow” diagram of the swap from the dealer’s perspective. This diagram is more useful for valuation of both simple structures such as this interest rate swap and more complicated structured products. Used together,  these two types of diagrams are very useful tools for analyzing and valuing derivative products.

![swaps-cash-flow.svg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/232932bf-474e-4866-9447-9f6a753190ee/swaps-cash-flow.svg)

### HISTORY

- The swap market grew from virtually nothing less than 20 years ago to a thriving market which is central to the fixed income business
- The origin of the swaps market was in the back-to-back and parallel loan market of the 1970 s. The British government limited purchases of foreign currency,  for example US dollars. In response some British firms arranged “back-to-back” loans where the firm lent sterling to a US company and borrowed US dollars while agreeing to make future payments in US dollars in return for receiving sterling. This would now be called a cross-currency swap,  and it efficiently allowed the British firm to buy the US dollars.
	 - In a back-to-back loan,  two companies in different countries would lend to each other in their respective currencies. This was a way to obtain foreign currency without having to deal with exchange rate risk.
	 - A parallel loan is similar,  but involves four parties (two in each country) and two separate loan agreements.
		  - A British firm (Firm A) would lend a certain amount in British pounds (sterling) to a US company (Company B).
		  - In return,  Company B would lend an equivalent amount in US dollars to Firm A.
		  - Both parties would agree to repay the loans in the original currencies at a future date.
		  - This arrangement allowed the British firm to effectively "borrow" US dollars from the US company,  while the US company could "borrow" British pounds from the British firm. The key point here is that the loans were made in the respective domestic currencies of each company,  which helped them avoid the restrictions on foreign currency purchases.
		  - In a cross-currency swap,  two parties exchange a principal amount in two different currencies and then repay over time according to an agreed upon exchange rate. The principal amounts are usually exchanged at the start and end of the contract.

### ECONOMIC RATIONAL

- Swaps allow efficient repackaging and allocation of risk. They provide users with the ability to separate interest rate risk from other characteristics such as counterparty credit risk,  leading to the pricing,  management,  and trading of such risks on their own.
- For example,  a bank may make a five year fixed rate loan to a corporate customer. The bank has two primary risks embedded in the loan.
	 - First,  the customer may fail to repay the loan,  leading to a loss of the principal amount of the loan. This is counterparty credit risk and is the primary risk commercial banks have traditionally focused on.
	 - Second,  the level of interest rates may rise after the loan is made. If the bank were not already committed to the lower rate they could make a new loan at the higher rate and earn more. This risk is the interest rate risk that the level of rates will change during the life of the loan,  and is the type of risk which bond trading desks have traditionally focused on.
- An interest rate swap would allow the bank to separate the interest rate risk from the loan by executing a swap at the same time as the loan.
- The bank has shifted the rate risk to someone else while retaining the credit risk,  in which they presumably have special expertise. Such separation allows specialization and efficiency in pricing and trading and thus lower costs and increased customer choice
- ## Much of the early growth of the interest rate swap market was a result of credit arbitrage or exploiting comparative advantages in funding. Consider the following example where two companies,  A and B,  have the following funding opportunities for five year loans

	 ```latex
      |  | Fixed Rate | Floating Rate |
      | --- | --- | --- |
      | Company A | 7% (700bp) | libor+50bp |
      | Company B | 8% (800bp) | libor+125bp |
    ```

- Company B is clearly a lower rated credit than company A; it must pay a higher rate in both the fixed and floating rate market. Note,  however,  that in the fixed rate market B pays 100 bp above A while in the floating rate market it pays only 75 bp above A. If A wishes to issue floating rate while B wishes to issue fixed rate,  the differential provides the opportunity for a profitable trade between the two companies.
- Consider the swap shown in figure 4.3. Company A issues fixed rate debt and B issues floating rate debt. Since A originally wanted to issue floating rate debt and B wanted to issue fixed rate,  they enter into a swap to exchange the fixed for floating rate cash flows. Company A pays floating libor while receiving a fixed rate of 6.65%. The net cost for company A is now libor+35 bp,  15 bp better than it could obtain in the market. Company B also benefits because its net cost is 7,  90% fixed,  better by 10 bp than it could do by issuing fixed bonds directly.

![swaps-Page-2.drawio.svg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/39042210-c919-4b36-8e3e-f331805ef33e/swaps-Page-2.drawio.svg)

- It may seem strange that the spread faced by the companies (which depends on the credit-worthiness of the company) should differ simply because they choose to issue in the fixed or floating market. (In fact,  such a credit arbitrage is relatively rare today,  partly as a result of increased efficiency achieved through the swap market itself.) Nonetheless,  it sometimes does occur. Two reasons are:
	 - Sectoral differences. Supply and demand of specific types of paper may differ across sectors of the market. For example,  banks issue considerable floating rate paper because their assets are primarily floating rate. This can lead to a plentiful supply of floating rate but a scarcity of fixed rate bank paper,  with a consequent premium for fixed rate paper (relatively low fixed rate as for company A above). This is exactly the kind of market inefficiency which the swaps market has tended to erase.
	 - Apparent arbitrage resulting from differences between fixed and floating contracts. The spread on a floating rate loan can usually be reset periodically as credit conditions of the borrower change,  while the rate on a fixed rate loan cannot. The initial spread on a floating rate loan may be lower than on a fixed rate because the spread can be raised if the credit deteriorates. In the example above company B has a net cost of 7.90% for the five year life of the loan only if the spread of 125 bp over libor remains unchanged. In this case the “credit arbitrage” may be more apparent than real since company B may end up with fixed rate funding higher than the stated 7.90%,  even higher than 8%.

## BASIC SWAP TERMS AND QUOTING CONVENTIONS

- Cash Flow (each payment period) = Stated Coupon * Day Basis * Notional

	 |Notional Principal|$5-200 mm (may be much larger)|
	 |---|---|
	 |Maturity of Contract|2 - 30 years (beyond 10 years less liquid)|
	 |Notional Exchange|None|
	 |Reset (standard settle)|2 days prior (2 day settle)|

	 ||FIXED SIDE|FLOATING SIDE|
	 |---|---|---|
	 |Payment Frequency|Semi-annual|Quarterly|
	 |Payment Type|In Arrears|In Arrears|
	 |Rate Quotation|Absolute level or spread to UST|Spread to libor|
	 |Day Basis for Coupon|30/360|A/360|
	 |Business Day Convention|Modified Following|Modified Following|

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2d69b3e6-05d2-4e82-a852-0b34f04da24c/Untitled.png)

- The stated coupon is 6.5%. The Day Basis is the number of days calculated on a 30/360 ISDA day basis (assuming each month has 30 days and a year has 360 days,  and using the 30 E/360 rather than 30/360 end of month convention 2). For an indication the coupon will be quoted as a spread over US Treasuries but the coupon will generally be quoted as a fixed,  all-in rate when the deal is done. The exact dates of payment are determined by going from the settlement date (2 days forward) and adjusting for weekends and holidays by the modified following business day rule. (For a non-business day,  roll to the next following good business day unless that takes you past month end,  in which case roll backwards)
- - The fixed side coupon is 6.5% per annum which in most cases means half of that each six months.

The floating side coupon is determined by the current level of libor. The rate used (the rate set) is taken from the screens two days prior to the beginning of a period. The payment is at the end of the period (payment in arrears) and is determined in the manner of the fixed side cash flow as: Cash Flow = (Libor Rate + Spread) * Day Basis * Notional

The day basis is Actual/360 which means take the actual number of days and divided by 360. Floating payments are usually quarterly.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b1123803-ae76-4d12-ae15-e5de13f367d8/Untitled.png)

- Figure 4.6 shows a sample broker screen with quotes for USD swaps. Focusing on the first row (quotes for 2 year swaps) the indicative quotes are shown as spreads off the two year US Treasury. The two year swaps spreads are shown in the fourth column as 21/17 which means that a dealer would (ideally) expect to receive 21 bp over the 2 year UST while paying only 17 bp over the 2 year. The market is said to be 17 bid,  21 offer. (In fact the market today is so competitive that the indicated 4 bp bid/offer spread is more like 2 bp or less in most cases.) The reference UST is shown in the second column. A live feed for the current price and yield of the on-the-run two year is displayed in the second column. The mid-market yield is calculated in the third column and the spread over this yield shown in the fourth column (quoted in basis points). The all-in fixed coupon is shown in the fifth column. A customer would expect to pay the higher fixed rate and receive the lower fixed rate. The sixth column shows the semi-annual 30/360 swap quote converted to an annual money-market (A/360) rate,  although this convention is less common than semi 30/360.
- In the US market swaps are quoted as a spread to Treasuries. This is convenient because it separates the all-in swap rate into two components: a general market component represented by the level of Treasury yields and a swap-specific component represented by the swap spread. The general market level changes minute-by-minute throughout the day as supply and demand for fixed-income securities of all types changes. The swap-specific component changes more gradually (say once a day). This component captures the specific supply and demand for swaps relative to other fixed income instruments such as Treasuries and corporate bonds,  and reflects,  among other components,  the credit spread of swaps to Treasuries.

Swap Valuation Swap valuation is quite straightforward and is actually no more complex than valuing a bond. We will start with a new swap (one which is right on a reset date) and then move to the more general case. The cash flow diagram introduced earlier in this chapter (see figures 4.2 and 4.5) hold the key to valuation.

Take as an example the two year swap to receive 6.5% fixed semi-annually. Figure 4.8 shows such a swap,  but with one important addition: a phantom exchange of principal has been added to the last payment. In the market all swap payments are net so that only the net cash actually changes hands. This means that introducing offsetting $100 payments will not change the cash changing hands,  and so cannot change the valuation of the swap. Nonetheless,  introducing the exchange of principal makes the valuation more straightforward.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7d24e38b-060f-4a59-a95b-a35ee0b7b2a7/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/498217cc-813f-41e1-bcce-9b0693624bc4/Untitled.png)

---

### RATE-ANTICIPATION SWAP

A portfolio manager who has expectations about the future direction of interest rates will use bond swaps to position the portfolio to take advantage of the anticipated interest-rate move. These are known as rate-anticipation swaps. If rates are expected to fall,  for example,  bonds with a greater price volatility will be swapped for existing bonds in the portfolio with lower price volatility (to take advantage of the larger change in price that will result if interest rates do in fact decline). The opposite will be done if rates are expected to rise.

### SUBSTITUTION SWAP

In a substitution coupon,  terms of bond for another bond that is thought to be identical in maturity,  price sensitivity interest-rate changes,  and credit quality,  but to capital market imperthat a offers a higher yield. This swap depends on fection. Such situations sometimes exist in the bond market because of portfolio manager faces temporary market imbalances. The risk that the purchased may not be identical to the bond for which it is that the bond example,  For not the same,  the bond if credit quality is exchanged. Is purchased may of higher credit risk be offering a higher yield because rather than because of a market imbalance

### INTERMARKET-SPREAD SWAP

These swaps are undertaken when the portyield spread between two bonds folio manager believes that the current historical yield spread and that the with its market is out of line in the of the investment horizon. Yield yield spread will realign by the end spreads between bonds exist for the following reasons: (1) there is Treasury bonds (e.g.,  between the of a difference in credit quality maturity),  bonds and the same double-A-rated public utility bonds of or (2) there are differences in the features of corporate bonds that make them more (for example,  callable and or less attractive to investors nonputable bonds). Noncallable bonds,  and putable and nonputable bonds).

[https://www.chathamfinancial.com/insights/what-is-an-interest-rate-swap](https://www.chathamfinancial.com/insights/what-is-an-interest-rate-swap)
[[Swaps]]
[[Swaps Part 2]]
[[Swaps Lecture Notes]]

![[what-is-an-interest-rate-swap.jpg]]

### INTEREST RATE SWAP CASH FLOW

A common swap structure in CRE finance is a pay-fixed swap,  in which the borrower pays a periodic fixed-rate (often monthly in the U.S. and quarterly in Europe) and receives SOFR in return. This structure complements the underlying payment structure of many CRE floating-rate loans and,  in conjunction with a floater,  gives a borrower a fixed-rate profile. The SOFR cashflows that the borrower receives on the swap net out the SOFR component of the loan interest and the borrower is left with a net fixed rate.

![[interest-rate-swap-diagram.png]]

### INTEREST RATE SWAP PRICING

The rate for a pay-fixed swap consists of two distinct components:

- **Mid-market rate**: This is the market rate for a given swap structure and term. While it will differ based on the swap structure (a 5-year swap and a 10-year swap will likely have different mid-market rates) and may change over time (the rate for a 5-year swap is likely different today than what it was yesterday),  in normal market conditions this rate should be an objective number. Different banks quoting the same structure at the same time should quote very similar mid-market rates (i.e. within a few tenths of a basis point of one another). This mid-market rate reflects what the market is pricing SOFR to average over a given term. A 5-year swap rate,  for instance,  is roughly the average of the [forward curve](https://www.chathamfinancial.com/insights/what-is-a-forward-curve) for SOFR for the next 5 years.

![[Untitled 20.png|Untitled 20.png]]

- **Credit charge**: For any given executed swap,  the swap provider will add a transaction-specific mark-up which is designed to compensate the swap provider bank for the credit risk they take in providing the swap,  and to provide the bank’s trading desk (which is often a different P&L than the bank’s lending group) with a return. This mark-up will differ from deal-to-deal,  and by the sponsor and the collateral securing the swap. For shorter dated swaps on low leverage mortgage debt,  this charge may only be a few basis points. For longer dated swaps,  the charge may be in the high single digits or teens,  or even higher.

With this is mind,  for a floating-rate loan that is swapped to fixed,  the fixed-rate coupon is the sum of the mid-market swap rate,  the credit charge on the swap,  and the spread on the underlying loan.

![[Untitled 1 13.png|Untitled 1 13.png]]

### SWAP CONSIDERATIONS

Interest rate swaps,  whether executed as a requirement in conjunction with a new financing or to manage risk on an existing loan,  carry risks. Chatham encourages real estate investors to consider the following factors when contemplating a swap or a financing with a swap:

- **Availability**: Swaps involve an exchange of payments between the borrower and the swap provider over time. These future obligations create credit risk for both parties. In practice,  CRE investors will find that their ability to enter into a swap is contingent upon identifying a bank willing to underwrite their credit. In some cases,  a borrower entity may have multiple banks that are willing to underwrite the borrower’s credit for a swap on an unsecured basis. This is most common with entities that have multiple unsecured lenders,  like real estate investment trusts (REITs) or open-end fund vehicles. In other cases,  the borrower entity may be required to provide some form of collateral to secure the swap. This is most common when the borrower is a single purpose entity (SPE) created to hold an asset and mortgage debt. In these cases,  the borrower will likely need to secure the swap with the underlying asset,  pari pasu to the loan. In practice,  this will limit the borrower to swapping with the lender.
- **Pricing**: As described above a swap rate is comprised of two components—the objective,  structure-specific mid-market rate and the transaction-specific credit charge (or mark-up) added to it. Borrowers entering into a financing with a swap should understand that the mid-market rate can move significantly between the signing of a term sheet and the closing of a loan. Borrowers should also negotiate the credit charge before signing a term sheet—we’ve seen many borrowers award a loan based on small differences in spread without realizing that the credit charge on the swap more than offset any loan spread benefit.
- **Documentation**: A swap will be documented with an ISDA Master and Schedule,  industry standard documentation for interest rate derivatives like swaps. While these documents may be presented to a borrower by a swap provider as boilerplate (or rarely negotiated),  they are typically heavily negotiated. Key provisions include language around termination events that can create cash events prior to loan maturity—language which can allow defaults on unrelated financings to trigger defaults on the swap,  and language which can tie non-recourse carve-out guarantors to swap obligations.
- **Mark-to-market**: Swaps may fluctuate between being an asset or a liability to a borrower over their life,  based on the contracted swap rate relative to the market replacement rate at any given time for the remaining swap term. Depending on accounting approaches,  quarter-over-quarter changes in mark-to-market value may flow through earnings if the swap does not receive appropriate accounting treatment. Investment platforms that use historical cost accounting may find that changes in swap mark-to-market impact fund returns.
- **Prepayment**: Swaps may require a breakage payment if terminated early in conjunction with an asset sale or loan refinance,  though this penalty will be less than the prepayment penalty on a similarly couponed fixed-rate loan. Swaps may also be structured with open prepay windows to limit potential prepayment costs.