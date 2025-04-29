---
tags:
  - forward_swaps
  - interest_rates
  - mbs
  - payer_swaption
  - swaptions
aliases:
  - Chapter 39
  - Forward Swap
  - Mortgage-Backed Securities
  - Payer Swaption
key_concepts:
  - Cash market swap rates
  - Greeks hedge fixed income
  - Long forward swap known rate
  - MBS and interest rate changes
  - Payer swaption maximum swap rate
---
# Swaptions, Forward Swaps, and MBS  

# Aims  

• To demonstrate how a payer swaption can be used to set an efective maximum swap rate that begins at expiration of the swaption but also allows the holder of the swaption to take advantage of lower (cash market) swap rates, should they occur in the future. • To show how a long position in a forward swap locks in a known swap rate which will begin at expiration of the forward swap but the holder of the forward swap cannot take advantage of lower cash-market swap rates in the future should they occur. • To analyse the use of various forms of mortgage-backed securities (MBS) and the interaction between interest rate changes, prepayment options, and the change in value of the MBS. • To show how the Greeks can be used to hedge fxed income derivatives.  

# 39.1 SWAPTIONS  

Suppose you are thinking of taking out a 3-year pay-fxed (receive-foat) vanilla interest rate swap in 2 years’ time. You are worried that swap rates in 2 years’ time will be high, implying you will pay a high fxed swap rate. If swap rates turn out to be low in 2 years’ time then you will be happy to take advantage of this outcome. But you cannot know today what cash market swap rates will be in 2 years’ time.  

However, today, you would like to be able to fx the maximum swap rate you will pay in 2 years’ time, whilst also being able to take advantage of low swap rates should they occur.  

You can achieve this desired outcome if today you buy a 3-year payer swaption which expires in $T=2$ years’ time with a strike rate $K_{s p}=10\%$ p.a., which is the agreed fxed swap rate. You have then insured that the maximum푠푝swap rate you will pay in the future is $K_{s p}$ but you can also take advantage of lower cash market swap rates should they occur, by not exercising the swaption and entering into a swap in the cash market in 2 years’ time.  

The ‘underlying asset’ in the swaption contract is a 3-year cash market swap with an agreed payment frequency (tenor) and notional principal. At expiration, the buyer of the swaption may either ‘take delivery’ and enter into a cash market swap, or the swaption can be cash settled. The strike $K_{s p}$ is the agreed swap rate in the swaption. The swaption premium will be paid up front.  

A swaption is an OTC option to enter into a cash market swap at the expiration date of the swaption, either as a fxed rate payer (at $K_{s p})$ and foating rate receiver (i.e. payer swaption) or vice versa (i.e. a receiver swaption).  

Suppose a US corporate thinks that it may need to borrow $\$100$ at a foating rate from its correspondent bank (Citibank) for 3 years, beginning in 2 years’ time. However, it wishes to swap the foating rate payments for fxed rate payments, thus transforming the loan to a fxed rate. The corporate therefore needs a $Q=\$100$ swap (from Morgan Stanley, say), to pay fxed and receive foating beginning in 2 years’ time and an agreement that the swap will last for a further 3 years (with annual payments).  

Suppose the corporate thinks that interest rates will rise over the next 2 years and hence the cost of the fxed rate payments in the swap will be higher than at present. Rather than waiting for 2 years, the corporate can insure a maximum future swap rate by today purchasing (from Morgan Stanley) a 2-year European payer swaption, on a 3-year ‘pay-fxed, receive-foating’ swap, at a strike rate of $K_{s p}=10\%$ (say). If cash market swap rates (quoted by JPMorgan, say) in 2 years’ time are $s p_{T}=11\%(>K_{s p}=10\%)$ then the corporate will exercise the swaption and take delivery of a 3-year swap with a fxed swap rate equal to $K_{s p}=10\%$ , from Morgan Stanley.1 A payer swaption therefore places a ceiling on the fxed rate payable in a swap at $K_{s p}=10\%$ . However, if swap rates turn out to be $s p_{T}=9\%$ in 2 years’ time then the corporate would not exercise its payer swaption and would enter a cash market swap (with JPMorgan) at the current (low) swap rate of $9\%$ .  

# 39.1.1 Expiration of the Swaption  

What is the payof to a swaption if the cash market swap rate at expiration $\neg T=2\setminus$ turns out to be $s p_{T}=11\%2$ The swap underlying the swaption is for delivery of a 3-year swap, with a notional principal $Q=\$100$ and a strike swap rate of $K_{s p}=10\%$ . Exercising the option allows one to enter into a swap to pay $K_{s p}=10\%$ fxed (and receive LIBOR). But at $T=2$ you could sell an otherwise identical 3-year swap in the cash market with fxed receipts at $s p_{T}=11\%$ (and pay LIBOR). The LIBOR payments in each swap cancel each other out.  

Hence the value (payof) to the swaption at expiration is the present value of an annuity of $\$10m(s p_{T}-K_{s p})$ , over 3 years (Figure 39.1):  

$$
\begin{array}{r l}&{V_{s p}(T=2)=\S10\mathrm{m}\left(\mathrm{max}[s p_{T}-K_{s p},0]\right)A N}\\ &{A N=d_{1}+d_{2}+d_{3}}\end{array}
$$  

$A N=$ present value of an annuity of $\$1$ paid at times $t_{i}$ $(i=1,2,3)$ where $d_{i}=1/(1+r_{i}t_{i})$ using simple interest (or $d_{i}=e^{-r_{i}t_{i}}$ , continuously compounded rates). $r_{i}$ is the out-turn spot rate at $T$ (the maturity date of the swaption (and ending $i=1$ , 2 or 3 years later).  

If the payer swaption is in-the-money, $s p_{T}>K_{s p}$ and is cash settled then at expiration $V_{s p}$ is received by the holder of the swaption. Alternatively, if at expiration the underlying swap rate is $s p_{T}=9\%(<K_{s p}=10\%)$ then the swaption would not be exercised but the corporate could then enter into a ‘new’ 3-year cash market swap at $T=2$ , at the ‘low’ cash market swap rate of $s p_{T}=9\%$ . Hence a payer swaption is an interest rate call where the payof is the annuity value of $Q\operatorname*{max}(s p_{\mathit{T}}-K_{s p},0)$ , rather than simply a one-of payment of $Q\operatorname*{max}(s p_{_T}-K_{s p},0)$ .  

It should be obvious from the above that swaptions (either European or American) can also be used for speculation on the future value of the swap rate. You would buy a payer (receiver) swaption if you thought swap rates would rise (fall) in the future, relative to $K_{s p}$ .  

![](0b9328d9c3554848134f8d9e3ad2bb2a8aba5178075b6d39fbb205367426dac8.jpg)  
FIGURE 39.1 Payof to European 3-year payer swaption  

# 39.2 FORWARD SWAPS  

A forward swap is a contract to enter into a swap at some future date, at a (forward) swap rate agreed today. Suppose you go long a 3-year forward swap with maturity $T=2$ years, notional principal $Q=\$100$ , annual tenor and a forward swap rate $s p^{f}$ . Then you have entered a contract today to ‘pay-fxed at ${\boldsymbol{s p}}^{f}$ and receive-foating’, on a swap beginning in 2 years and lasting for a further 3 years.  

A long forward swap is a ‘pay-fxed, receive-foating’ swap that will commence in the future but at a forward swap rate $s p^{f}$ agreed today.  

How do we price the forward swap at time $t=0?$ (Figure 39.2).  

# 39.2.1 Pricing a Forward Swap  

The forward swap rate at $t=0$ is the fxed rate ${\boldsymbol{s p}}^{f}$ that makes the swap have zero expected value at $T=2$ (and therefore also at $t=0$ ). The foating leg of the swap (i.e. the FRN) is worth $Q$ at $T=2$ . The fxed leg of the underlying swap has an annual coupon $C_{X}=s p^{f}Q$ . The swap must have zero expected value at $T$ :  

Expected value of $T=E.$ xpected Value of fxed payments $T$  

$$
\begin{array}{r c l}{{}}&{{}}&{{Q=C_{X}(d_{23}^{f}+d_{24}^{f}+d_{25}^{f})+Q~d_{25}^{f}}}\\ {{}}&{{}}&{{=s p^{f}Q(d_{23}^{f}+d_{24}^{f}+d_{25}^{f})+Q~d_{25}^{f}}}\end{array}
$$  

![](8ab1710983e07f12119b61d53e93af4da921da83be4a807bf96110c3c7d385f8.jpg)  
FIGURE 39.2 Two-year forward contract on a 3-year swap  

where $d_{2i}^{f}=1/(1+f_{2i}t_{2i})$ and $f_{2i}\left(i=3,4,5\right)$ are the (simple) forward rates quoted at $t=0$ which apply to periods from $t=2$ to $t=t_{2i}$ . Hence the forward swap rate quoted today, for a swap with a maturity of $n=3$ years, beginning in $T=2$ years’ time is:  

$$
s p^{f}=\frac{(1-d_{25}^{f})}{\displaystyle\sum_{i=3}^{5}d_{2i}^{f}}
$$  

The forward swap rate depends only on the individual forward rates (from year-2 onwards). The above formula is of the same form as that used earlier to determine today’s cash market swap rate, $s p_{0}$ , except that for the forward swap we use forward rates beginning at $T=2$ rather than spot interest rates beginning at $t=0$ .  

# 39.2.2 Value of Forward Swap at Maturity  

Assume $s p^{f}=10\%$ for a 2-year forward swap on an underlying 3-year swap. Consider what happens at maturity $\cdot T=2)$ of the forward swap, if the forward swap is cash settled. Assume that at $T=2$ the cash-market swap rate $s p_{T}=12\%$ . The value at expiration $V_{f s}$ to the fxed rate payer (i.e. long forward swap) is the 3-year annuity value of the cash fow $Q(s p_{T}-s p^{f})$ :  

$$
\begin{array}{l}{{V_{f s}(T=2)=Q(s p_{T}-s p^{f})\left[A N\right]}}\\ {{A N=\left[d_{1}+d_{2}+d_{3}\right]}}\end{array}
$$  

where (using simple rates) the discount factors are $d_{i}=1/(1+r_{i}t_{i})$ and $r_{i}(i=1,2,3)$ are the 1-year, 2-year and 3-year out-turn spot rates beginning at $T=2$ . Note that $r_{i}$ are the actual spot rates (ex-post) known at $\scriptstyle{T=2}$ , which is now ‘the present’. If the out-turn cash market swap rate $s p_{T}=12\%>s p^{f}=10\%$ then the long receives cash of $V_{f s}$ at $T=2$ , from the swap dealer. If the out-turn swap rate $s p_{T}=8\%<s p^{f}=10\%$ then the holder of the long forward swap pays out $V_{f s}$ to the swap dealer at $T=2$ .  

The diference between a forward swap and a swaption is that the latter allows the holder to beneft from any fall in swap rates, while also putting a known ceiling on the swap rate payable in the future. For this privilege you pay the swaption premium. In contrast, the forward swap ‘locks in’ a swap rate $s p^{f}$ payable in the future and this implies you cannot take advantage of low swap rates should they occur – but by way of ‘compensation’, the forward swap does not require an up-front payment (we ignore margin payments).  

# 39.3 MORTGAGE-BACKED SECURITIES (MBS)  

US fnancial institutions – primarily banks, savings and loan associations (S&Ls) and mortgage companies – issue fxed-rate mortgages with initial terms of between 15 and 30 years. However, these mortgages can be bundled up into a portfolio and sold to investors in the form of mortgaged-backed securities (MBS). This is securitisation – in the US and UK the MBS primary and secondary market is very large. The principal and interest payments of a MBS are often guaranteed by a government agency (e.g. in the US, the Government National Mortgage Association GNMA or ‘Ginnie Mae’). Securitisation can also be based on future receipts from other ‘assets’ such as car loans, credit cards, recording royalties, telephone charges, or many other types of loan repayments – as we see in Chapter 43.  

# 39.3.1 Mortgage Pass-throughs and Strips  

There are a wide variety of ways that MBS can be structured and then sold on to investors (i.e. mutual funds, pension funds, hedge funds, sovereign wealth funds, and wealthy endowment funds – like those held by Harvard and Yale Universities).  

The simplest MBS are mortgage pass-throughs. Here, the investor (periodically) receives a proportion of the interest and principal payments on the underlying mortgages. In a ‘mortgage pass-through’, the initial value of the underlying mortgages $V_{0}$ held by an investor is equal to the present value of the fxed (coupon) mortgage payments of $\$0$ (per period) plus the present value of any repayments of principal. The discount rates used to calculate the present value are often risk-free yields, since many mortgage payments are guaranteed by institutions such as GNMA. Otherwise the discount rate is a risk-free rate plus a spread, to refect the credit risk of the mortgagees.  

The pass-throughs are subject to considerable interest rate risk. Firstly, they are long maturity (high duration) ‘bonds’ and hence their (present) value (PV) rises (falls) when interest rates fall (rise) – this is a ‘pure interest rate efect’.  

Secondly, the pass-throughs are subject to prepayment risk. If interest rates fall, then some home owners will want to pay of their existing fxed-rate mortgages and refnance at new lower rates. Hence, the holder of a pass-through may fnd prepayments increasing but she loses some of the future interest payments on the mortgages, which no longer need to be paid (as the mortgage has been paid of early). The change in value of a mortgage pass-through to investors is therefore complex depending on the interaction of the pure interest rate efect and prepayments. Conversely, if market interest rates rise, the pure interest rate efect will reduce the PV of the mortgage pass-through but mortgagees may extend the life of the mortgage.  

Mortgage pass-throughs can be split into interest-only (IO) and principal only (PO) strips. The investor can buy a share of either the IO or the PO strip, or both.  

An interest only (IO) strip entitles the investor to receive only interest payments from the portfolio of mortgages. $A$ principal only $(P O)$ strip entitles the investor to receive only the payments of principal.  

To illustrate what might happen to the change in value of a pass-through (PT) we consider the separate efects on the present value (PV) of IO and PO strips, and use the relationship $P V_{P T}=P V_{I O}+P V_{P O}$ .  

When interest rates fall, the PV of any set of fxed interest payments will increase but any increase in prepayments will reduce the PV of an IO strip, as the prepayments imply that many future interest payments are now not required to be paid. The net efect is usually a fall in the value of IO strips, after a fall in interest rates, because of a high level of prepayments by mortgagees.  

If interest rates rise, the PV of an IO strip will fall due to the pure interest rate efect but this may be ofset by a lengthening of the life of the mortgage and hence the interest payments, so the overall efect may be an increase in value of the IO strip.  

We can illustrate the efect of changes in interest rates on IO and PO strips and pass-throughs, by considering the following ‘stylised’ portfolio of mortgages.  

Value of initial mortgage $P_{0}=\mathbb{\S}100,000$ Life of initial mortgage $n=10$ years Fixed rate agreed for mortgage repayments $r=10\%$ p.a.  

The fxed amount paid by the mortgagees $\$0$ p.a., must ensure that the present value of all the payments $\$0$ equals the current value of the mortgage advance, $P_{0}$ . Hence, the required fxed annual mortgage payment $\$0$ is the solution to:  

$$
C\times[A_{n,r}]=P_{0}\quad\mathrm{where}A_{n,r}={\frac{1}{r}}\left[1-{\frac{1}{(1+r)^{n}}}\right]
$$  

$A_{n,r}$ is the PV of an annuity (of $\$1$ payable) over $n$ -years, given the current ( $\dot{n}$ -year) interest rate (yield), $r$ . Solving the above equation gives $C=\$16,275$ p.a. In the frst year, the interest accruing on the loan is $I O_{1}=\S10{,}000=r P_{0}$ which implies that $(C-r P_{0})$ is $\$6,275$ can be used to reduce the initial principal, leaving an outstanding balance at the end of year-1, $P_{1}=$ $\$100,000-\$86,275$ . For each succeeding year:  

$\boldsymbol{P}_{t}$ is calculated recursively:  

$$
P_{t}=P_{t-1}-P O_{t}=P_{t-1}-(C-r P_{t-1})=(1+r)P_{t-1}-C
$$  

An investor (Mr Strip) who purchases an IO strip today, will be willing to pay the present value of the future mortgage interest payments. Suppose $y=8\%$ p.a. is the current annual yield2 and we also (somewhat arbitrarily) assume that with $y=8\%(<10\%)$ , the average life of the mortgages in the securitised mortgage pool is 7 years because of early prepayments by some homeowners. The $P V$ of these interest payments (Table 39.1, column 4) is:  

$$
P V_{I O}(8\%,75\mathrm{r})=d_{1}~I O_{1}+d_{2}~I O_{2}+\ldots~\ldots+d_{7}~I O_{7}=\S41,733\
$$  

where using compound rates, $d_{i}=1/(1+y)^{i}$ . Similarly, an investor (Mr Principal) who purchases the principal only strip will be willing to pay the present value of the repayments of principal (Table 39.1, column 5) up to the end of year-7, plus the remaining principal $P_{7}=\$40,472$ after early redemption by some mortgagees, hence:  

$$
{\bf\Pi}_{_{P O}}^{\prime}(8\mathcal{U},75\mathrm{r})=d_{1}\ P O_{1}+d_{2}\ P O_{2}+\ldots+d_{6}\ P O_{6}+d_{7}\ (P O_{7}+P_{7})=\S66,614
$$  

The value of a ‘pass-through’ is simply the sum of the IO and PO strips, which is:  

$$
P V_{P T}(8\%,7\mathrm{yr})=P V_{I O}+P V_{P O}=\S108,347
$$  

An investor in a mortgage pass-through has a claim on a set of coupon and principal payments. The reason MBS are derivative securities is that an investor in a MBS has implicitly written (sold) an American put option because the mortgagee has the right to redeem the mortgage. The strike price in the embedded put option is equal to the outstanding principal of the mortgage. Conversely, householders paying the mortgage have a long put which they will be more likely to exercise (i.e. remortgage), the lower are market interest rates in the future.  

Let us consider what happens to the value of the IO and PO strips when interest rates change. We shall see that changes in value for the IO and PO strips depends crucially on how interest rates afect whether the prepayment option is exercised.  

# 39.3.2 Interest Only Strips  

If $y$ falls to $7\%$ and the prepayment date remains at the end of year-7 then $P V_{I O}$ increases from $\$41,733$ to $\$43,041$ (i.e. pure interest rate efect). But if $y$ falls to $7\%$ and this moves the average prepayment date to the end of year-2,3 then today the IO strip is only worth:  

$$
P V_{I O}(7\%,2\mathrm{yr})={\frac{I O_{1}}{(1.07)}}+{\frac{I O_{2}}{(1.07)^{2}}}=\S17,532
$$  

TABLE 39.1 Mortgage-backed securities (MBS)   


<html><body><table><tr><td rowspan="2">Years</td><td rowspan="2">Loan outstanding</td><td rowspan="2">Fixed payments</td><td rowspan="2">Interest accrual</td><td rowspan="2">Repayment of principal</td><td rowspan="2">Loan outstanding after payments</td><td rowspan="2"></td><td colspan="2"></td></tr><tr><td>NPV 10</td><td>PO</td></tr><tr><td>1</td><td>100,000</td><td>16,274.54</td><td>10,000</td><td>6,274.54</td><td>93,725.46</td><td></td><td></td><td></td></tr><tr><td>2</td><td>93,725.46</td><td>16,274.54</td><td>9,372.55</td><td>6,901.99</td><td>86,823.47</td><td>NPV(7%, 2 years)</td><td>17,532.14</td><td>87,727.50</td></tr><tr><td>3</td><td>86,823.47</td><td>16,274.54</td><td>8,682.35</td><td>7,592.19</td><td>79,231.27</td><td></td><td></td><td></td></tr><tr><td>4</td><td>79,231.27</td><td>16,274.54</td><td>7,923.13</td><td>8,351.41</td><td>70,879.86</td><td></td><td></td><td></td></tr><tr><td>5</td><td>70,879.86</td><td>16,274.54</td><td>7,087.99</td><td>9,186.55</td><td>61,693.31</td><td></td><td></td><td></td></tr><tr><td>6</td><td>61,693.31</td><td>16,274.54</td><td>6,169.33</td><td>10,105.21</td><td>51,588.10</td><td></td><td></td><td></td></tr><tr><td>7</td><td>51,588.10</td><td>16,274.54</td><td>5,158.81</td><td>11,115.73</td><td>40,472.37</td><td>NPV(7%, 7 years) NPV(8%,</td><td>43,041.21 41,732.57 40,487.63</td><td>69,871.16 66,613.94 63,561.14</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>7 years) NPV(9%, 7 years)</td><td></td><td></td></tr><tr><td>8</td><td>40,472.37</td><td>16,274.54</td><td>4,047.24</td><td>12,227.30</td><td>28,245.07</td><td></td><td></td><td></td></tr><tr><td>9</td><td>28,245.07</td><td>16,274.54</td><td>2,824.51</td><td>13,450.03</td><td>14,795.04</td><td></td><td></td><td></td></tr><tr><td>10</td><td>14,795.04</td><td>16,274.54</td><td>1,479.50</td><td>14,795.04</td><td>0</td><td>NPV(9%, 10 years)</td><td>44,444.24</td><td>60,000.19</td></tr></table></body></html>  

So although the fall in $y$ from $8\%$ to $7\%$ raises the PV of each interest receipt, the number of interest payments has dropped from seven to two. Hence there is a substantial fall in $P V_{I O}$ from $\$41,733$ to $\$17,532$ , a fall of $60\%$ .  

Now suppose that $y$ increases from $8\%$ to $9\%$ . If the average life of the mortgages remains at 7 years, then $P V_{I O}$ will fall from $\$41,733$ to $\$40,488$ . However, if the life of the average (fxed interest) mortgage is extended to 10 years, then there is an increase in $P V_{I O}$ from $\$41,733$ to $\$44,444$ , because of the increased number of interest payments (even though these are discounted at a higher rate). Hence, the change in value of $P V_{I O}$ depends crucially on the interaction between the change in $y$ (‘pure interest rate efect’) and the change in the average prepayment period (i.e. whether the prepayment option is exercised by the homeowner).  

# 39.3.3 Principal Only Strips  

There will be some early prepayments of principal simply because people move house for a whole variety of reasons (e.g. arrival of children, changing jobs etc.). But here we only concentrate on the interaction between interest rates and the prepayment option.  

Suppose $y$ falls from $8\%$ to $7\%$ or rises from $8\%$ to $9\%$ , with no change in the 7-year maturity of the underlying mortgages. Clearly, after an interest rate fall (rise) $P V_{P O}$ rises (falls), ceteris paribus. However, if the fall in $y$ from $8\%$ to $7\%$ brings the average prepayment date to the end of year-2, then:  

$$
P V_{P O}(7\%,2\mathrm{yr})={\frac{P O_{1}}{(1.07)}}+{\frac{P O_{2}+P_{2}}{(1.07)^{2}}}=\S87,728
$$  

where $P_{2}=\$86,823$ (Table 39.1, column 6, row 2) is the ‘large’ prepayment of the remaining principal on the mortgages at the end of year-2. Hence $P V_{P O}$ increases substantially from $P V_{P O}((8\%,7\mathrm{yr}))=\S66,614$ to $P V_{P O}(7\%,2\mathrm{yr}){=}587,728$ , that is, an increase of $31.7\%$ .  

Alternatively, if interest rates rise immediately from $8\%$ to $9\%$ and this pushes the prepayment date out to year-10, then $P V_{P O}$ falls substantially from $P V_{P O}(8\%,7\mathrm{yr})=866,614$ to $P V_{P O}(9\%,10\mathrm{yr})=\S60,000$ , that is, a fall of $9.9\%$ .  

,F푂rom Table 39.1 we can calculate the PV of the mortgage pass-through using $P V_{P T}=$ $P V_{I O}+P V_{P O}$ for our three cases:  

$$
\begin{array}{r l}&{{P V}_{P T}(8\%,7\mathrm{yr})=\S108,347}\\ &{{P V}_{P T}(7\%,2\mathrm{yr})=\S105,260\left(2.8\%\mathrm{fall}\right)}\\ &{{P V}_{P T}(9\%,10\mathrm{yr})=\S104,444\left(3.6\%\mathrm{fall}\right)}\end{array}
$$  

Hence here, the value of the mortgage ‘pass-through’ is less sensitive to interest rate changes and consequent changes in the schedule of prepayments by homeowners, than are IO and PO strips, taken separately. The value of IO and PO strips are very sensitive to the complex interaction between changes in interest rates and any prepayments by homeowners, which also depend on the characteristics of the cohort of mortgage borrowers – such as age, marital status, number of children, geography, income, state of the (local) economy etc. Hence it is di\$cult to value and predict changes in IO and PO strips. While they (often) carry a government credit guarantee, there is no guarantee that their market value will remain unchanged and hence they are far from being ‘safe investments’ – as the events of the crash of 2008–9 illustrated.  

# 39.4 HEDGING FIXED INCOME DERIVATIVES  

The price of fxed income derivatives, such as options on T-bond futures or caps and foors, can change substantially due to non-parallel shifts in the yield curve or changes in the term structure of volatility. There is therefore not just ‘one number’ for the delta, gamma, and vega of a fxed income derivative – for example, you can have a delta for a cap with respect to the 3-month interest rate, the 6-month rate etc. Once you have calculated the type of shift in the yield curve you want to hedge against (e.g. for a parallel shift or a twist in the yield curve) then you can calculate the appropriate delta and gamma by recalculating the option price under this new interest rate scenario, using an option pricing formula such as Black’s model – this is the ‘perturbation approach’.  

Suppose we want to calculate the delta of an option on a fxed income asset (e.g. option on a T-bond or option on Eurodollar futures). The delta is defned as the change in the option price due to a (small) change in spot yields (i.e. the ‘zero curve’). Possible alternative ways of modelling and simulating changes in interest rates along the yield curve are:  

• Calculate the change in the option price due to a parallel shift in all spot yields of 1 bp – this is sometimes referred to as a PV01, DV01, or PVBP – that is, the ‘present value’ or ‘duration value’ of a 1 bp $(0.01\%)$ parallel shift.   
• Divide the zero curve (or forward curve) into a number of ‘maturity buckets’ and calculate the change in the option’s price for a 1 bp change in one of these time buckets (e.g. for 0–3 month rates), holding the rest of the yield curve unchanged. Or alternatively calculate the change in the options price for a 2 bp change in one time bucket (e.g. 0–3 month rates) and a 1 bp change in another time bucket (e.g. 4–6 month rates) – to mimic a twist in the yield curve.   
• Use a principal components analysis to decompose all spot rate changes across the yield curve into say the ‘frst 3 principal components’. Then calculate a delta for each of these three principal components (PC). The delta of the frst-PC represents an (approximate) parallel shift in the yield curve, the delta for the second-PC represents a twist in the curve and the third-PC often can be interpreted as a possible ‘bowing’ of the yield curve.   
• Calculate the change in the option’s price due to small changes in all the ‘yields’ that have been used to construct the zero curve. The easiest way to think of this is that all  

spot rates are changed by diferent amounts based on a trader’s view of likely ‘shifts’ along the yield curve – this is like the ‘bucket’ case but with many more ‘buckets’.  

• A slightly more complex variant is to use the actual rates used to construct the yield curve. If the short end of the curve has been derived using yields based on zero-coupon bonds (bills) then these yields would be changed by a small amount. If the long end of the curve is constructed from spot yields derived from swap rates, then swap rates would be changed by a small amount.  

Once we have our new spot rates we can calculate a new price for the (fxed income) option using an appropriate pricing formula (e.g. Black’s model) and hence calculate the option’s (overall) delta.  

Calculating gamma is even more involved. Suppose there are fve diferent spot rates $r_{i}$ used to construct the zero curve and to price the option (e.g. swaption). Then there are at least fve diferent gammas with respect to changes in these fve diferent spot rates, which infuence the change in the option’s price $d f$ . (This assumes we ignore cross product terms $\partial^{2}f/\partial r_{i}\partial r_{j}$ in the Taylor series expansion of $d f$ .) But once we have made our specifc choice of a specifc shift in the yield curve (e.g. parallel shift), the calculation of specifc gammas using the perturbation method is straightforward, in principle.  

The same procedure can be used to calculate vega by changing the volatility (of interest rates) by a small amount and calculating the change in the option premium. If the option premium depends on the volatility of interest rates at diferent horizons then when calculating the option’s vega we can either assume an equal change in all volatilities or we can change volatilities by diferent amounts at diferent maturities (e.g. change the volatility of 3-month interest rates by a diferent amount than you change the volatility of 6-month rates).  

# 39.4.1 Hedging Interest Rate Options and Swaps  

Suppose a bank acts as a swap dealer and also buys and sells interest rate options such as caps and foors (to corporates and other banks). A long position in an interest rate cap increases in value as interest rates increase – it has a positive delta. So if a bank sells a cap (to a corporate) and interest rates rise, the bank loses – a short cap has a negative delta.  

A cap is a series of caplets on an agreed notional principal. For simplicity assume MegaBank on 15 June 2019 holds a cap which consists of three caplets with maturity dates of September-2019, March-2020 and September-2020. Each caplet has a known price (on 15 June 2019). If we assume a 1 bp increase in interest rates (over 1 day say) then we can work out the change in value (over 1 day) of each caplet and hence of the cap itself. The cap will also have a gamma (with respect to interest rates) and a vega (with respect to the volatility of interest rates, $\sigma$ ).4  

Assume MegaBank has positions in swaps and caps – how does the bank hedge these positions? We proceed as we did when hedging a portfolio of stock options (see Chapter 18) but here it is changes in interest rates and the volatility of interest rates that cause changes in the value of MegaBank’s caps or swaps. We can easily calculate the total gamma and vega of MegaBank’s ‘swaps plus cap’ portfolio. (The vega only arises from the caps, the vega of a swap is zero.)  

Our frst hedging method for MegaBank’s ‘swaps plus cap’ can be sequential because we choose frst to hedge with an interest rate option-X and then with a fxed income asset with a zero vega (e.g. a T-bond, which has non-zero gamma and delta but a zero vega). We frst use option-X to hedge the vega, then we hedge the gamma and fnally the delta.  

First, we use an interest rate option-X (e.g. cap with a diferent strike or expiration date) to ofset the vega of MegaBank’s current cap position – so we are now vega neutral. This will lead to a new portfolio gamma, since option-X has a non-zero gamma. We can ofset this new portfolio gamma by buying or selling T-bonds or FRAs (which have non-zero gammas). The important point is that achieving a gamma-neutral portfolio using T-bonds does not upset our newly acquired vega neutral position – as T-bonds have zero vegas.  

However, including bonds in our hedge portfolio to achieve gamma neutrality, will alter the delta of our portfolio, which we now recalculate. Finally, we ofset this remaining portfolio delta by using Eurodollar futures (which have zero gamma and vega). We are then vega, gamma, and delta neutral and we have been able to hedge sequentially – frst with option-X (vega neutral), then with bonds (gamma neutral) and fnally with Eurodollar futures (to achieve delta neutrality).  

Our second hedging method uses two interest rate options (e.g. a mixture of caps or bond options or bond futures options). This hedge cannot be done sequentially because the two options both have non-zero gammas and non-zero vegas. To hedge MegaBank’s ‘swaps caps position we frst use two other interest rate options X and Y (e.g. caps with diferent strikes and expiration dates) to simultaneously hedge the gamma and vega of our initial position. (This was done for stock options in Chapter 18.) MegaBank’s portfolio now consists of ‘swaps $+$ caps $^+$ options- $\cdot X+$ options- $\mathbf{\nabla\cdotY^{\eta}}$ and has a portfolio gamma and vega that are both zero. But MegaBank, by adding the two options X and Y, has changed the delta of its initial ‘swap $+$ caps’ portfolio, so it now recalculates its new portfolio delta. MegaBank then ‘neutralises’ this new portfolio delta by taking ofsetting positions in Eurodollar futures – which does not afect MegaBank’s existing vega-gamma neutral position because Eurodollar futures contracts have zero vega and gamma.  

# 39.5 SUMMARY  

• A payer swaption is an option on a swap. If you hold a payer swaption with a strike $K_{s p}$ , you have efectively placed an upper limit of $K_{s p}$ on the fxed rate payable in a swap (which will start at the expiration date of the swaption contract). However, you can  

also take advantage of low cash market swap rates in the future by not exercising the swaption at maturity, if the out-turn swap rate ${\boldsymbol{s p}}_{T}$ is below $K_{s p}$ and instead you purchase a cash market swap at the low swap rate, .   
• A forward swap can be used by a corporate to ‘lock in’ a known swap rate that will begin at a specifc time in the future. However, the corporate cannot then beneft from lower swap rates in the future should these occur.   
• One of the largest and most active fxed income markets is for various forms of mortgage-backed securities (MBS). It is the prepayment possibility in these portfolios of mortgages that give them their ‘embedded option’ characteristics. The market value of mortgage pass-throughs, interest only and principal only strips are very sensitive to the interaction between changes in interest rates and the decision to prepay the principal early (or to extend the life of the mortgage).   
• Calculating the Greeks for fxed income derivatives can be done by the perturbation method. For example, change the input (e.g. spot yields) by a small amount and recalculate the new option price (e.g. using Black’s model or the BOPM) – this gives the option’s delta for this specifc set of spot rate changes. Other Greeks can be calculated in a similar way.   
• A portfolio of options on fxed income assets (e.g. caps and foors) can be vega-hedged and gamma-hedged using other fxed income options (e.g. caps and foors with diferent strike prices and expiration dates) and fnally delta-hedged using Eurodollar futures contracts.  

# EXERCISES  

# Question 1  

A corporate treasurer has to borrow $\$100$ in 2 years’ time, at 360-day LIBOR, for a further 2 years. She decides to take out a forward swap, to receive-LIBOR and pay-fxed, with tenor 1 year. The swap will begin in 2 years.  

Current forward rates (continuously compounded) are $f_{12}=5.0\%,f_{23}=5.1\%,f_{24}=5.2\%$ , $f_{25}=5.3\%$ , $f_{13}=5.05\%$ , $f_{14}=5.15\%$ . Calculate and explain how the forward swap rate is determined.  

# Question 2  

There is a forward swap, with swap rate ${\boldsymbol{s p}}^{f}$ and a swaption with strike $K_{s p}$ . Assume both derivatives have maturity dates at $T$ and the underlying swap has the same time to maturity, tenor, and notional principal for both derivatives.  

What is the key diference between a forward swap, with swap rate $s p^{f}$ , and a swaption with strike $K_{s p}?$ Explain with reference to the payofs at maturity.  

# Question 3  

You hold a $Q=\$10\mathrm{m}$ , bank deposit on 90-day LIBOR with four further resets in 90, 180, 270, and 360 days. Explain how you could reduce interest rate risk by using either a forward swap (with swap rate $s p^{f}$ ) or an interest rate ‘foor’ (with strike rate, $K_{F L}\backslash$ ). What is the key diference in outcomes at maturity for these two derivatives?  

# Question 4  

How do mortgage pass-throughs difer from interest only (IO) and principal only (PO) strips?  

# Question 5  

Explain why a principal only (PO) mortgage strip has a mark-to-market value to an investor that may be extremely volatile, with respect to changes in interest rates. What two key factors determine the change in value of a PO mortgage strip?  