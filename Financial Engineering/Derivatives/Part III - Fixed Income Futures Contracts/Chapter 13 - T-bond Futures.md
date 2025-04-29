---
tags:
  - arbitrage
  - bond_portfolio
  - futures_contract
  - hedging
  - market_timing
  - t_bond_futures
aliases:
  - T-bond futures
  - UK Gilt futures
  - cheapest-to-deliver
key_concepts:
  - Cash-and-carry arbitrage
  - Eliminate price risk
  - Optimal futures contract
  - Speculative strategies
  - T-bond futures details
---
# T-bond Futures  

# Aims  

• To examine contract details for UK Gilt futures and US T-bond futures including the conversion factor, the cheapest-to-deliver bond and wild card play. • To determine the optimal number of T-bond futures contracts for hedging. • To determine the fair price of a T-bond futures contract using cash-and-carry arbitrage. • To analyse speculative strategies using T-bond futures. This includes spread trades and altering the e!ective duration of a bond portfolio to take advantage of market timing strategies.  

Some of the practical details of T-bond futures are quite intricate. A long T-bond futures position allows the holder to take delivery of a long maturity T-bond at expiration of the futures contract. As with all futures contracts, T-bond futures can be used for speculation, arbitrage, and hedging. Hedging allows the investor to eliminate price risk of her bond portfolio.  

For example, suppose Ms Bond holds $\$200$ in (cash market) 20-year T-bonds and she fears a rise in long-term yields over the next 6 months. Ms Bond should hedge by shorting (selling) T-bond futures. If long rates do subsequently rise, the price of her cash-market T-bonds will fall but so does the futures price. Hence, she can close out her short futures position at a proft by buying back the T-bond futures at a lower price. The proft from the futures position compensates for the loss in value of her cash market position in T-bonds.  

If Ms Bond wants to act as a speculator and she forecasts that long-term yields will fall in the future then today she would purchase T-bond futures contracts. If yields fall, then the futures price will rise and she can close out her long position in T-bond futures at a higher price – hence making a speculative proft.  

Ms Bond gains leverage by purchasing the futures contract rather than purchasing T-bonds in the cash market (with her own funds) – because she only has to provide a relatively small initial futures margin (and not the full price of the cash market bond). Transactions costs (e.g. bid–ask spreads, clearing, and brokerage fees) in the futures market might also be lower than those in the cash market.  

Naked speculative positions in T-bond futures are highly risky, therefore speculators often use spread trades. For example, they might purchase one T-bond futures contract with a long maturity date and simultaneously sell another T-bond futures with a short maturity date. This provides possible speculative profts but also reduces risk compared with an outright long or short position in T-bonds.  

# 13.1 CONTRACT SPECIFICATIONS  

T-bond futures contracts written on a number of government bonds are traded on several exchanges. The most liquid contracts are on US T-bond futures (CBOT) quoted in US dollars. There are also Euro-Bond futures – for example, on French and German bonds (‘Bunds’) which are both quoted in euros, and also UK Gilt futures (quoted in sterling) – all traded on NYSE-Euronext. Somewhat less liquid T-bond futures are those on Japanese government bonds, traded on NYSE-Euronext and in Tokyo.  

# 13.1.1 UK Long Gilt Futures Contract  

Details of the UK Long Gilt Future (on NYSE-EURONEXT) are given in Table 13.1. The bond deliverable in the contract is a ‘notional bond’ with a $4\%$ coupon (with a maturity between 8.75 and 13 years). Surprisingly, this notional $4\%$ bond does not actually exist! However, as we shall see, it provides a benchmark from which to calculate the price of possible bonds for delivery (which do exist).  

TABLE 13.1 UK Long Gilt Futures (Euronext-LIFFE)   


<html><body><table><tr><td>Contract size</td><td>100,000 nominal, notional Gilt with 4% coupon</td></tr><tr><td>Delivery months</td><td>March / June / September / December</td></tr><tr><td>Quotation</td><td>Per 100 nominal</td></tr><tr><td>Tick size (value)</td><td>0.01 (10)</td></tr><tr><td>Last trading day</td><td>11 a.m., 2 business days prior to the last business day in the month</td></tr><tr><td>Delivery day</td><td>Any business day in the delivery month (seller's choice)</td></tr><tr><td>Settlement</td><td>List of deliverable Gilts published by the exchange with maturities between 8.75-13 years</td></tr><tr><td>Margin requirements</td><td>Initial margin 2,oo0, spread margin 250 (determined by the exchange)</td></tr></table></body></html>  

The seller of the futures contract can decide the exact delivery date (within the delivery month) and exactly which bond she will deliver (from a limited set, designated by the exchange). In fact, the seller will select a bond which is known as the ‘cheapest-to-deliver’ (CTD). The CTD bond can be shown to depend on the ‘conversion factor’ (CF) for each possible deliverable bond. (These concepts are explained below.)  

The futures contract size is for delivery of $z=\pm100,000$ (face value) T-bonds and futures price quotes are expressed per £100 nominal (of deliverable T-bonds). The tick size is £0.01 per £100 nominal (e.g. 1-tick is a move from £95 to £95.01) – hence the tick value is £10 per contract $(=\pm0.01\times\mathrm{{\&100,000/\mathrm{{f100}}}})$ .  

# EXAMPLE 13.1  

# Face Value of Futures Contract  

On 27 July the September-futures has a closing (settlement) price quote of $F_{0}=£103.19$ per £100 nominal. Hence the ‘face value’1 of one futures contract is:  

$$
V_{F}=(\mathbb{\S}100,000)(F_{0}/100)=\mathbb{\P}103,190.
$$  

13.1.2 US ‘Classic’ and ‘Ultra’ T-bond Futures Contracts  

The principles underlying these futures contracts (traded on the CBOT) are very similar to those for the UK gilt-futures contract, except price quotes are in $1/32\mathrm{nd}$ of $1\%$ (see Table 13.2). Expiration months are March, June, September, and December. The last trading day is the business day prior to the last 7 days of the expiry month. The frst delivery day is the 1st business day of the delivery month but delivery can take place on any business day in the delivery month.  

Note that the notional bond deliverable in the futures contract is assumed to be a $6\%$ -coupon bond. However, in practice the person with a ‘short’ futures position can choose from around 30 di!erent eligible bonds to deliver (which have coupons di!erent from $6\%$ and the CF adjusts the delivery price to refect the type of bonds actually delivered).  

For the ‘classic’ futures contract the T-bonds delivered must have at least 15 years to maturity2 and less than 25 years to maturity (from the frst day of the delivery month).3 There are also futures on 2, 5 and 10-year T-notes, which only di!er from the T-bond futures contract in the maturity of the T-notes which can be delivered in the contract. As with most futures contracts, delivery rarely takes place but it is the possibility of delivery and hence arbitrage profts which keeps the T-bond futures price in line with the spot/cash market price of T-bonds.  

TABLE 13.2 US ‘classic’ T-bond futures (CBOT)   


<html><body><table><tr><td>Contract size</td><td>100,0oo nominal, notional Us Treasury Bond with 6% coupon</td></tr><tr><td>Delivery months</td><td>March / June /September/December</td></tr><tr><td>Quotation</td><td>Per $100 nominal</td></tr><tr><td>Tick size (value)</td><td>1/32 ($31.25)</td></tr><tr><td>Last trading day</td><td>7 working days prior to last business day in expiry months</td></tr><tr><td>Delivery day</td><td>Any business day in the delivery month (seller's choice)</td></tr><tr><td>Settlement</td><td>Any Us Treasury bond maturing at least 15 years from the contract month</td></tr><tr><td></td><td>(or not callable for 15 years) and with less than 25 years to maturity.</td></tr><tr><td>Margins</td><td>$5,000 initial, $4,ooo maintenance (decided by the exchange)</td></tr><tr><td>Trading hours</td><td>8 a.m. to 2 p.m.- Central Time</td></tr><tr><td>Daily price limits</td><td>96 points ($3,000)</td></tr></table></body></html>  

# EXAMPLE 13.2  

# Tick Value of Futures Contract  

On 7 July, the US T-bond futures settlement price quote (CBOT) for September delivery is ‘98-14’ $(=98+14/32)$ which corresponds to a price of $F_{0}=\$98.4375$ per $\$100$ nominal. With a contract size of $\$100,000$ , the face value of one contract (‘invoice’ or ‘contract’ price) is $V_{F}=\mathbb{5}100,000(F_{0}/100)=\mathbb{5}98,437.50.$ The tick size is $1/32$ of $1\%$ $(=0.0003125)$ which on a contract size of $\$100,000$ nominal, implies a tick value of $\$31.25$ per contract.  

# 13.2 CONVERSION FACTOR AND CHEAPEST-TO-DELIVER  

Before discussing hedging strategies we need to be clear about the use of the conversion factor (CF) and the concept of the cheapest-to-deliver (CTD) bond. We do so with respect to the US T-bond futures contract but similar principles apply to UK Gilt futures. There are a wide variety of bonds with over 15 years to maturity which can be delivered by the investor who is short T-bond futures. These will have di!erent maturities and coupon payments and hence di!erent values for CF and the CTD.  

TABLE 13.3 The CTD bond   


<html><body><table><tr><td>Deliverable bonds (maturity)</td><td>Spot price ($)</td><td>Conversion factor (CF)</td><td>Raw basis (=S-FCF)</td></tr><tr><td>1. Bond-A (2039)</td><td>112-4 (112.125)</td><td>1.044</td><td>0.156</td></tr><tr><td>2. Bond-B (2041)</td><td>112-8 (112.25)</td><td>1.033</td><td>1.461</td></tr><tr><td>3. Bond-C (2044)</td><td>114-8 (114.25)</td><td>1.065</td><td>0.029</td></tr></table></body></html>

Notes: F(September-futures) $\mathbf{\sigma}=\mathbf{\sigma}$ 107-8 (107.25)  

# 13.2.1 Conversion Factor (CF)  

This section assumes the reader is largely familiar with the pricing of bonds in the spot market and the conventions used in calculating accrued interest (see Cuthbertson and Nitzsche 2008). The CF adjusts the price of the actual bond to be delivered, by assuming it has a $6\%$ yield, which makes it equivalent to the notional $6\%$ bond in the futures contract.  

When computing the CF the maturity of the underlying bond is defned as the maturity on the frst day of the delivery month. For example, if we assume the actual delivery date is 11 September 2018 and the underlying bond matures on 15 February 2038, then the maturity period used in the calculation of CF is 1 September (i.e. not 11 September) to 15 February 2038.  

The CF is best understood using a specifc example. To simplify matters we assume the counterparty who is short the futures contract does not yet hold a bond for delivery, so we are going to calculate the CF and CTD bond at the maturity date of the futures contract $(=T)$ .  

Consider an actual 20-year US T-bond, paying semi-annual coupons of $8\%$ (i.e. $\$4$ per 6 months), with $n=40$ (6-month) periods to maturity (see Example 13.3). If the yield to maturity on this $8\%$ -coupon bond is assumed to be $6\%$ p.a. then its ‘fair’ or ‘theoretical’ price would be $\$123.1$ (per $\$100$ nominal) which gives a conversion factor $C F_{T}=\mathfrak{H}1.231$ . In essence the deliverable bond (with an $8\%$ coupon) is worth 1.231 times as much as the notional $6\%$ coupon bond (trading at par and hence with $Y T M=6\%$ ).  

# EXAMPLE 13.3  

# Calculation of Conversion Factor  

Bond for delivery is an $8\%$ -coupon T-bond with remaining maturity of 20 years (semi-annual coupons). What is the conversion factor of the bond?  

(continued)  

(continued)  

The theoretical price of an $8\%$ -coupon bond, with $\$100$ face value, if the YTM is assumed to be $6\%$ (i.e. the same as the notional bond in the futures contract) is:  

$$
{\widehat{P}}={\frac{\S4}{(1.03)}}+{\frac{\S4}{(1.03)^{2}}}+\cdot\cdot\cdot+{\frac{\S4}{(1.03)^{40}}}+{\frac{\S100}{(1.03)^{40}}}
$$  

Using the annuity formula for the present value of the coupons:  

$$
\widehat{P}=23.11(\S4)+0.3066(\S100)=\S123.1
$$  

The theoretical price of the actual $8\%$ -coupon bond to be delivered is $\widehat{P}=123.1$ and hence the conversion factor $C F=1.231$ (per $\$100$ nominal).  

The conversion factor adjusts the price of the actual bond to be delivered, relative to the notional $6\%$ coupon bond in the futures contract:  

If coupon on the bond actually delivered $>6\%$ then $\mathrm{:}\Rightarrow C F>1$  

If coupon on the bond actually delivered $<6\%$ then $\iota\Rightarrow C F<1$  

The conversion factor will di!er for bonds with di!erent coupon payments and di!erent maturities. The CF for any specifc deliverable bond will change over time simply because the maturity date of the deliverable bond gets closer (although it will always exceed 15 years, otherwise it will cease to be an eligible bond). In calculating the CF the CBOT assumes the yield curve is fat at $6\%$ . But in practice this is rarely (if ever) the case. This means that the ‘true price’ of the deliverable bond, which should be priced using spot rates (see Cuthbertson and Nitzsche 2008) will not equal that used in the calculation of the CF. Hence, there will usually be eligible bonds for delivery that are actually cheaper than the ‘cheapest-todeliver’ bond.  

Let us now consider the cash amount received by a trader (Ms Short) who is short T-bond futures, when she delivers the underlying bond at maturity $T$ . Let $F_{T}$ be the futures settlement price (on the ‘position day’ – see below). When Ms Short delivers the $8\%$ -coupon, 20 year bond she will receive:  

Ms Short’s receipts at settlement  

Note that $F_{T}$ is the ‘settlement price’ at $T$ (and not the price initially agreed at the outset of the futures contract). ${A I}_{T}$ is the accrued interest at $T$ and is a fraction of the next coupon payment on the bond delivered against the futures contract. For example, if the maturity date $T$ of the futures is 11 September 2017 and the deliverable bond matures on 15 February 2038, then the deliverable bond has semi-annual coupons each year on 15 February and 15 August. Assume there are 184 days between 15 August and 15 February. The short therefore delivers a bond at $T=11$ September 2017, which already has 27 days of accrued interest. Hence the long must pay the short for this loss of accrued interest of $A I_{T}=\S0.73[=(27/184)\times10/2]$ .  

# 13.2.2 Cheapest-to-Deliver  

Suppose it is now $T$ ${\bf\tau}=11$ September 2017) and there are three bonds designated by CBOT for actual delivery in September whose CF are 1.044, 1.033, and 1.065. In practice, the calculation of the CTD bond is quite complex but a rough idea of the CTD bond can be obtained by choosing that bond with the smallest raw basis:  

$$
R a w b a s i s=B_{T}-F_{T}C F_{T}
$$  

where $B_{T}$ is the spot (‘clean’) price an eligible bond for delivery, $F_{T}$ is the settlement futures price and ${C F}_{T}$ is the conversion factor of a deliverable bond.  

Table 13.3 shows the calculation of the raw basis for three deliverable bonds. The fnal column indicates that Bond-C is the CTD. Although it is often the case that the bond actually delivered by the short is the CTD, nevertheless this is not always so since the seller may wish to preserve the duration of her own bond portfolio or provide a bond, other than the CTD, in order to minimise her tax bill. We now examine how Equation (13.1) for the raw basis arises. At settlement the short receives:  

$$
C a s h r e c e i v e d b y s h o r t\left(p e r\:\mathcal{S}100\:n o m i n a l\right)=F_{T}C F_{T}+A I_{T}
$$  

where $A I_{T}$ is the accrued interest. The conversion factor adjusts the T-bond futures price for the fact that the deliverable bond has a coupon di!erent from the notional $6\%$ bond (stated in the T-bond futures contract). The $8\%$ -coupon bond actually delivered would have a higher price when its coupons are discounted at the notional $6\%$ . To purchase the actual deliverable bond in the cash market, the short will pay:  

$$
C a s h p a i d b y s h o r t={"C l e a n P r i c e^{\prime}}+A c c r u e d I n t e r e s t=B_{T}+A I_{T}
$$  

Hence, the net cost to the short of providing the deliverable $8\%$ -coupon bond is just the raw basis defned above:  

$$
N e t c o s t=(B_{T}+A I_{T})-(F_{T}C F_{T}+A I_{T})=B_{T}-F_{T}C F_{T}
$$  

# 13.3 HEDGING USING T-BONDS  

Today, if Ms Bond is (net) long in US T-bonds $(V_{s}>0)$ with a positive portfolio duration $(D_{s}>$ 0 and fears a fall in bond prices, then to hedge she will short T-bond futures. Conversely, if she wishes to purchase bonds in the future and is worried that cash market T-bond prices will rise (i.e. yields will fall) then today she should buy T-bond futures. The optimal number of futures contracts $N_{F}$ is given by the duration-based hedge ratio (see Appendix 13.A):  

$$
\begin{array}{c}{{N_{F}=-\left({\frac{V_{s}}{V_{F}}}\right)\left({\frac{D_{s}}{D_{f}}}\right)\beta_{y}~C F}}\\ {{d y_{s}=\alpha+\beta_{y}d y_{f}+\varepsilon}}\end{array}
$$  

$V_{s}=$ total market value of portfolio of bonds to hedged  

$F=$ price $\$100$ nominal of the bond in the futures contract $z=$ contract size $(=\$100,000$ for the ‘classic’ -bond futures contract $V_{F}=z(F/100)$ is the value of bond futures contract ‘contract price’ $C F=$ conversion factor of the bond eligible for delivery in the futures contract $D_{s}=$ portfolio duration the expiration of the hedge of the cash-market bonds $D_{f}=$ duration maturity of the futures of the notional bond in the futures contract $y_{s}=$ yield to maturity of the bonds to hedged $y_{f}=\mathrm{YTM}$ of the deliverable bond in the futures contract  

Equation (13.5) assumes $D_{s}$ is defned using continuously compounded rates for $y_{s}$ and $y_{f}$ . But if $y_{s}$ and $y_{f}$ are quoted yields to maturity (e.g. using discrete semi-annual compounding) then we use modifed duration $M D_{i}=D_{i}/(1+y_{i})$ , in place of $D_{i}$ in the above equations for $i=s$ $f$ .  

# 13.3.1 Portfolio Duration  

For illustrative purposes assume a fund manager has two T-bonds in her portfolio, with market values $V_{1}=\$200$ in Bond-1 and $V_{2}=\$800$ in Bond-2, so that $V_{s}\equiv V_{1}+V_{2}=\S100\mathrm{m}$ . The portfolio duration $D_{S}$ of her cash-market position is:  

$$
D_{S}\equiv w_{1}D_{1}+w_{2}D_{2}
$$  

where $w_{1}=V_{1}/V_{s}=0.20~(=\S20\mathrm{m/\Phi}\mathrm{5100\mathrm{m})}$ , $w_{2}=V_{2}/V_{s}=0.80(=\mathbb{880m/\mathbb{8100m}})$ and $D_{i}$ is the duration of bond- $i$ , for $i=1,2$ . Using portfolio duration to calculate $N_{F}$ assumes a parallel shift in the yield curve and small changes in yields (e.g. 25 bps) – otherwise the hedging error could be large.  

# 13.3.2 Hedging a T-bond Portfolio  

Consider a US pension fund manager (Ms Bond) on 1 May who wishes to hedge her portfolio of Corporate bonds (or T-bonds) with market value $V_{s}=\mathfrak{H}1,010,000^{4}$ and portfolio duration $D_{s}=6.9$ . Ms Bond fears a rise in interest rates over the next 3 months (i.e. 1 May to 1 August) and if this occurs the value of her cash-market bond portfolio will fall. The $C F$ of the CTD bond is 1.12 (Table 13.4A). For a portfolio of corporate bonds this would be a cross-hedge, as the corporate bonds are hedged using $T$ -bond futures.  

Ms Bond, on 1 May, sells September T-bond futures contracts and assuming a parallel shift in the yield curve $(d y_{s}=d y_{f})$ ) and no complications of accrued interest:  

$$
N_{F}=-\left({\frac{\mathfrak{H}1.1\mathrm{m}}{\mathfrak{H}103,500}}\right)\left({\frac{20}{18}}\right)1.12=-13.2\ {\mathrm{(short~}}13{\mathrm{contracts)}}
$$  

Suppose interest rates rise between 1 May and 1 August (Table 13.4B). Her cash-market bond portfolio falls by $5\%$ to $\$1,045,000$ capital loss of $\$55,000$ . But the futures price falls by 4 points from $F_{0}=103–16$ to $F_{1}=99–16$ and the gain on the short futures position is $\$52,000$ $\stackrel{\cdot}{=}13$ contracts $\times128$ ticks $\times\$31.25$ . The hedge shows a small loss of $\$3,000$ on an initial cash-market value of about $\$10$ (i.e. about $0.3\%$ ). The unhedged portfolio would have lost $\$55,000$ (i.e. about $5.5\%$ ).  

# 13.4 HEDGING: FURTHER ISSUES  

# 13.4.1 Cross Hedge: Corporate Bond Portfolio  

Suppose company-XYZ is going to raise funds by issuing corporate bonds in 6 months’ time, after the legal details of the bond issue are completed. The treasurer of company-XYZ may be worried by the possibility of a rise in long-term interest rates over the next 6 months, which will raise the cost of issuing corporate bonds. Company-XYZ therefore hedges by shorting T-bond futures.  

TABLE 13.4A Hedging a US bond portfolio   


<html><body><table><tr><td>Cash market - 1 May</td><td>Futures (September delivery) - 1 May</td></tr><tr><td>Marketvalue of bond</td><td>CF of CTD bond = 1.12</td></tr><tr><td>portfolio, Vs = $1.1m</td><td>Size of one contract, z = $100,000 Futures Price, Fg = 103-16 ($103.5)</td></tr><tr><td></td><td>VF= z(F/100)= $103,500</td></tr><tr><td>Duration, Ds = 20</td><td>Duration (futures), Df= 18</td></tr><tr><td></td><td></td></tr><tr><td></td><td>Tick value 1/32 equals $31.25</td></tr></table></body></html>  

TABLE 13.4B Hedge outcome   


<html><body><table><tr><td>Cash market - 1 August</td><td>Futures (September delivery) - 1 August</td></tr><tr><td>Loss on bond portfolio</td><td>September futures: F = 99-16 ($99.50 per $100)</td></tr><tr><td>= $1,100,000 - $1,045,000</td><td>Gain on 13 short futures = N z(Fg-F)/100</td></tr><tr><td>= $55,000</td><td>= 13($100,000)(4)/100 = $52,000</td></tr><tr><td></td><td>= 13 × 128 ticks × $31.25 = $52,000</td></tr></table></body></html>  

When hedging corporate bonds, it is important to estimate the relationship between $d y_{s}$ (the change in the corporate bond yield) and $d y_{f}$ (the yield on the deliverable bond in the T-bond future contract), since these may change by di!erent amounts over the hedge period.  

Regression techniques can be used but results may be subject to error, as changes in corporate ‘specifc risk’ (e.g. IT failures, results of patent applications, environmental issues, default) will a!ect changes in the corporate bond yield $d y_{s}$ – whereas changes in $d y_{f}$ (government T-bond yields) should be largely una!ected by these ‘corporate risks’.  

# 13.4.2 PVBP, Convexity, and Perturbation Analysis  

Instead of using the duration-based hedge ratio we could obtain the same result using the ‘price value of a basis point’ (PVBP). This requires the calculation of the PVBP for the cash-market bond portfolio to be hedged and the PVBP for the US T-bond futures contract. This method usually uses the duration approximation for the change in T-bond prices and therefore assumes a parallel shift in the yield curve and small changes in interest rates.  

Alternatively, we can calculate the PVBP of the cash-market (spot) bond portfolio using the ‘duration $+$ convexity’ approximation (for a parallel shift in the spot yield curve of 1 bp):  

$$
d V_{s}=-V_{s}[(D_{s}d y_{s})+(1/2)\chi_{s}(d y_{s})^{2}]
$$  

where $\begin{array}{r}{\chi_{s}=\sum_{i=1}^{n}w_{i}\chi_{i}}\end{array}$ is the cash-market convexity, $w_{i}=V_{i}/V_{s}$ proportion of the total bond portfolio held in bond- $i$ and $\chi_{i}=$ convexity of bond- $i$ .  

Alternatively, we can use the ‘full’ (present value) pricing formula when considering the e!ect of a large change in interest rates on the ‘total’ change in the cash-market value of a T-bond portfolio – this will implicitly incorporate the convexity of the bonds. The ‘full valuation’ method can be done for either parallel or non-parallel shifts in spot yields – as spot rates might change by di!erent amounts.  

# 13.4.2.1 Non-parallel Shifts  

We can also calculate the change in dollar value of one futures contract, ${\bf d V}_{F}={\bf V}_{F}(d F/F)$ using $F_{t}=S_{t}e^{r(T-t)}-F V C_{T}$ where the change is calculated with respect to changes in the spot  

yields which determine (a) the price of the deliverable bond $S_{t}$ and (b) the (future) value of any coupon payments $F V C_{T}$ . The number of futures in the hedge is then:  

$$
N_{F}=-\left(\frac{^{\ast}T o t a l^{\ast}c h a n g e i n\nu a l u e o f c a s h m a r k e t,b o n d p o r t f o l i o}{C h a n g e i n\nu a l u e o f o n e T\cdot b o n d,f u t u r e s c o n t r a c t}\right)
$$  

This is a form of perturbation analysis because we choose the size of the change in each spot interest rate along the yield curve and then calculate the impact on the numerator and denominator in Equation (13.9).  

# 13.4.3 Hedging the Market Risk of an Underpriced Corporate Bond  

In Chapter 6 we discussed how a hedge fund that buys underpriced stocks can hedge the market risk of the stocks by shorting stock index futures. Consider a similar situation where Ms Bond today, buys what she believes are underpriced corporate bonds (of several companies). She might believe the corporate bonds are underpriced because the rating agencies (and the average bond trader) have given the bond an A-rating but her assessment of their default risk would suggest a higher AA-rating.  

She therefore expects a rise in the market price of the bond (even if risk-free government bond yields stay constant), as ‘market participants’ come to realise that the corporate bond is actually less risky than they frst thought. Then she can close out her long corporate bond position at a proft.  

However, Ms Bond is exposed to changes in long-term (risk-free) T-bond yields. If long-term risk-free yields increase, this will cause a fall in the cash market price of her corporate bonds, which may more than o!set the gains she makes when the ‘credit risk underpricing’ is corrected. To hedge against future changes in T-bond yields, Ms Bond should short $N_{F}$ , T-bond futures, today:  

$$
N_{F}=-\left({\frac{V_{p}}{V_{F}}}\right)\left({\frac{D_{s}}{D_{f}}}\right)\beta_{y}C F
$$  

where $V_{p}$ is the total dollar amount held in her portfolio of underpriced cash-market corporate bonds which have a portfolio duration of $D_{s}$ . If the risk-free T-bond rate increases, then the T-bond futures price will fall and the proft after closing out the futures will just compensate for any loss in value of the cash-market bond position – solely due to changes in risk-free T-bond yields.  

Ms Bond can then capture any future rise in corporate bond prices due to the correction of the ‘credit risk’ mispricing. However, her portfolio of underpriced corporate bonds is still subject to any (residual) ‘specifc risk’ (e.g. bankruptcy, regulatory changes, IT failures, reputational damage, etc.) of the bond issuers. The hedge using T-bond futures does not protect the ‘mispriced’ corporate bond portfolio from specifc risks – but overall, specifc risk may be small in a well-diversifed corporate bond portfolio.  

# 13.4.3.1 Long-Short Bond Portfolio  

As in the case of underpriced and overpriced stocks, a bond trader might take a long position in ‘underpriced’ corporate bonds and short-sell ‘overpriced’ corporate bonds.5 The dollar amount of cash-market bonds held long $V_{L}>0$ or short $(V_{S}<0)$ , determine the portfolio durations $D_{L},D_{S}$ and hence the number of T-bond futures to go long and short, using Equation (13.10). The net position in futures contracts depends on the sign of $N_{L}-N_{S}$ , but this ensures the long-short bond speculator is then hedged against parallel shifts in the yield curve, while she waits for the mispricing of the cash-market bonds to be corrected.  

# 13.4.4 Risks in the Hedge  

A hedged bond portfolio will not provide a perfect hedge because:  

• the hedge period (e.g. 3 months from May to August) may not match the maturity date of the futures contract (e.g. September contract) – this gives rise to basis risk.   
• calculating price changes in futures markets are subject to error, in part because it is di\$cult to ascertain the CTD bond (and hence its duration).   
• shifts in the yield curve may not be parallel (there may be twists in the yield curve), so we cannot always assume duration or duration plus convexity provides a good approximation to changes in T-bond cash-market prices.   
• If we are hedging a corporate bond portfolio then the change in the value of the corporate bonds due to changes in risk-free T-bond yields can be hedged using T-bond futures but changes in corporate bond prices due to any change in (residual) specifc/credit risk will not be hedged.  

However, academic studies fnd that hedging using T-bond futures can reduce price risk, with the duration based hedge ratio performing particularly well. Hedging cash-market positions in corporate bonds using T-bond futures is also found to be e!ective, even though this is a cross-hedge and involves possible changes in credit risk.  

# 13.5 MARKET TIMING  

Suppose a trader Ms Bond currently holds a bond portfolio and over the next month she expects interest rates to fall sharply. Today, to take advantage of this interest rate forecast she might move out of low duration bonds and into high duration bonds, because the latter will rise in price more than the former. However, this is likely to be costly because it involves ‘high’ transaction costs of selling low duration bonds and buying high duration bonds – and then reversing these trades in one month’s time (when she returns to her ‘normal long-run’ position in bonds).  

A less costly strategy is to continue to hold the original cash market bond portfolio and alter the e!ective duration of the portfolio using T-bond futures. Suppose, $D_{S}=$ portfolio duration of Ms Bond’s cash-market T-bonds, $D_{f}=$ duration of the T-bond deliverable in the futures contract and $D_{d}=\operatorname{Ms}$ Bond’s target (desired) duration. The number of futures contracts required to achieve a desired duration $D_{d}$ is (see Appendix 13.A):  

$$
N_{F}=\left(\frac{D_{d}-D_{s}}{D_{f}}\right)\left(\frac{V_{s}}{V_{F}}\right)\beta_{y}
$$  

where we usually assume that $d y_{s}=d y_{f}$ and hence $\beta_{y}=1$ .6 The formula for $N_{F}$ can be used in a market timing strategy. Suppose you are long a cash-market bond portfolio (so $V_{s}$ and $D_{s}$ are positive) then:  

• If you expect a rise in yields (i.e. fall in bond prices) and therefore require a lower desired duration $D_{d}<D_{s}$ , then today, sell $N_{F}$ T-bond futures.   
• If you expect a fall in yields (i.e. rise in bond prices) and therefore require a higher desired duration $D_{d}>D_{s}$ , then today, buy $N_{F}$ T-bond futures.  

# 13.6 WILD CARD PLAY  

There is another practical issue to discuss as regards the US T-bond futures contracts and that is the strategy known as Wild Card Play. On the CBOT, trading in T-bond futures ceases at 3 p.m. (EST) while actual T-bonds are traded until 5 p.m. (EST) and the ‘short’ in the futures contract has until early evening to issue the clearing house with notice of intention to deliver. If the notice is issued, the invoice price of the T-bond futures is calculated on the basis of the settlement price (i.e. average of quoted prices just before the close of trading). However, the short can wait and see if she can purchase an eligible bond for delivery, at a lower price in the cash market. To see how this is possible we have to closely examine the delivery process for T-bond futures. Delivery is a 3-day process and involves:  

(i) Position Day: The short notifes the clearing house of intention to deliver, two business days later.   
(ii) Notice of Intention Day: The clearing house assigns a trader who is long, to accept delivery. The short is now obligated to deliver the next business day.  

(iii) Delivery Day:  

Bonds are delivered (with the last possible delivery day being the business day prior to the last 7 days in the delivery month).  

This delivery process can give rise to a Wild Card Play by the short on any ‘position day’. If the cash-market price of bonds falls between $3\ \mathrm{p.m}$ . and ${\mathsf{s p.m}}.$ ., the short buys the ‘low price’ CTD bond in the cash market and issues a notice of intention to deliver, knowing that on delivery she will receive the ‘high’ futures settlement price determined as of $3\ \mathrm{p.m}$ . that day. However, if the bond price does not decline, she can wait until the next day and repeat this strategy (until the fnal business day before the fnal delivery day in the month). In essence, the short has an implicit option that can be exercised during the delivery month, while the long has increased risk because she does not know the exact bond that will be delivered.  

There is also a quality or switching option for the short, since she can deliver a variety of eligible bonds. Even if she holds a specifc bond against delivery on her short futures position, nevertheless if the yield curve shifts she may choose to deliver another yet cheaper bond. The timing option applies when the bond held for delivery by the short pays a coupon (rate) that exceeds the cost of fnancing her cash-market bond position (i.e. the repo rate). Then it is better if the short delays delivery. There is also an end of the month option held by the short, since the last trading day for the T-bond futures contract is the eighth-to-last business day. The futures settlement price is fxed in over this period, but the short still has the option to announce her intention to deliver on any day up to the penultimate business day. She can therefore wait to see if cash-market bond prices fall over this period and deliver a ‘low’ price bond if one becomes available.  

All of these embedded options available to the person holding a short T-bond futures position should lead to a lower futures price – in order to compensate the long, for the increased risk. But it is thought that most of the time these options do not distort the cash-and-carry arbitrage relationship. However, these embedded options for the short do make it more diffcult to accurately calculate both the optimal hedge ratio and the futures price based on the cash-and-carry approach.  

# 13.7 PRICING T-BOND FUTURES  

# 13.7.1 Futures Price on Deliverable Zero-coupon Bond  

Suppose today is time $t$ and the futures contract matures at $T$ , so the time to maturity is $T-t$ . The underlying asset to be delivered at maturity $T$ is a single zero-coupon bond. Today, we can borrow at $r$ and purchase the underlying bond for a price $s$ in the cash market and later deliver it against the short futures position. The usual risk free arbitrage argument ensures that:  

$$
F=S[1+r_{s}(T-t)]\qquad\mathrm{(simple~interest)}
$$  

$$
\begin{array}{l}{F=S(1+r)^{T-t}}\\ {F=S e^{r(T-t)}}\end{array}
$$  

The implied repo rate $(\widehat{r})$ is the return from selling the futures at $t=0$ for $F$ and simultaneously buying the underlying bond at $S$ , so that $\widehat{r}=(F/S)^{1/T}-1$ (compound rate). In this case, risk-free arbitrage is possible if $\widehat{r}$ does not equal $r$ , the cost of fnancing the arbitrage strategy using the actual repo market.  

# 13.7.2 Futures Price on Deliverable Coupon Paying Bond  

In practice there is not a futures contract on a zero-coupon bond. As we saw in Chapter 3 if we ignore some important practical issues, the fair price (at $t$ ) of a T-bond futures contract using cash-and-carry arbitrage is:  

$$
F_{t}=[S_{t}-P V(C)]e^{r(T-t)},
$$  

where $s$ is the invoice price of the cash-market bond (i.e. the ‘clean price’ plus accrued interest), $P V(C)$ is the present value of any coupon payments (on the deliverable bond) between today and the maturity date $T$ of the futures contract and $r$ is the (continuously compounded) spot yield (for maturity $T-t)$ . Note that the T-bond futures price can also be written $F_{t}=\bar{S}_{t}e^{r(T-t)}-F V C_{T}$ , where the future value at $T$ of the coupon payments is $F V C_{T}=\sum_{i=1}^{N}C_{i}e^{r_{i}(T-t_{i})}.$ .  

Unfor=tunately, in practice it is di\$cult to accurately calculate the fair T-bond futures price. This is because of the fexibility of the short’s decision over the delivery date $T$ and the precise choice of the CTD bond and hence its invoice price $s$ .  

First, note that the cost of creating a synthetic futures contract is the cost of buying the underlying cash-market bond at $S_{t}$ using borrowed funds, which accrues to a debt of $S_{t}e^{r(T-t)}$ at maturity $T$ (of the futures contract). The cost-of-carry is o!set by the $N$ coupons $C_{i}$ received from the cash-market bond at times $t_{i}$ from today. When these coupons are reinvested at the (expected) risk-free rates $r_{i}$ (between $t_{i}$ and $T$ ) they have a future value at $T$ of:  

$$
F V C_{T}=\sum_{i=1}^{N}C_{i}e^{r_{i}(T-t_{i})}
$$  

The no-arbitrage futures price is then:  

$$
F_{t}=S_{t}e^{r(T-t)}-F V C_{T}
$$  

where $r$ is the interest rate over the period $(t,T)$ . Considering the additional complexities of the conversion factor, accrued interest etc., the futures price for a contract which matures at $T$  

![](87203bda2f76897c8e52b1d96258a445c37fd30796dbad6b04a542b80b5b9db9.jpg)  
Deliverable bond has a $10\%$ coupon and matures 15 February 2038 Deliverable bond pays semi-annual coupons of $\$5$ on 15 February and 15 August   
FIGURE 13.1 Pricing a T-bond futures contract  

(and has time $T-t$ to maturity) is:  

$$
F_{t}=(1/C F_{t})(S_{t}e^{r(T-t)}-F V C_{T}-A I_{T})
$$  

Let’s examine this from a more practical point of view, which requires some additional points to be made. Suppose it is 1 July 2017. The yield curve is fat and $r=0.03$ $3\%$ p.a., continuously compounded). You are deciding whether cash-and-carry arbitrage is possible with the September T-bond futures contract, which has a known maturity date $T=11$ September (Figure 13.1).  

By buying a cash-market T-bond on 1 July and carrying it forward to 11 September, you create a synthetic T- bond future, since the T-bond can be delivered against the futures contract. Assume the CTD bond is a $10\%$ -coupon T-bond which pays semi-annual coupons of $\$5$ each year, on 15 August and 15 February and matures on 15 February 2038. It has a CF of 1.22.  

Today at $t=1$ July to the maturity of the futures, the deliverable bond pays one coupon of $C=\$5$ on 15 August, which when invested over 27 days is expected to accrue to a future value at time $T$ of:  

$$
F V C_{T}=5e^{0.03(27/184)}=\S5.022.
$$  

On 1 July, borrowing at the risk-free (repo rate) $r$ and purchasing the bond in the cash market for an invoice price $S_{t}$ , leads to an amount owing at $T=11$ September, of $S_{t}e^{r(T-t)}$ (i.e. purchase cost plus the repo interest cost). Therefore at $T$ , the net cost-of-carry in the cash market is:  

But the above strategy creates a synthetic T-bond future since it ensures that the bond purchased in the cash market on 1 July is available for delivery against the futures contract at  

$T=11$ September. At maturity of the futures $T$ , the invoice price the long pays the short for delivery of the underlying T-bond is the quoted price of $F_{t}$ plus accrued interest7:  

$A I_{T}=\$0.73$ is the accrued interest (between 15 August and $T=11$ September) on the CTD bond delivered at $T$ (see Figure 13.1). $A I_{T}$ is a proportion of the next coupon which accrues on 15 February 2018.  

Since the actual futures contract and the synthetic futures both deliver one bond at $T$ then the cost today must be equal, otherwise risk-free arbitrage profts would be possible. Hence equating (13.15) and (13.16):  

$$
F_{t}(C F)+A I_{T}=S_{t}e^{r(T-t)}-F V C_{T}
$$  

The no-arbitrage (fair) futures price is:  

$$
F_{t}=(1/C F)(S_{t}e^{r(T-t)}-F V C_{T}-A I_{T})
$$  

where $S_{t}$ is the cash-market bond price (i.e. clean price $B_{t}$ plus accrued interest $A I_{t}$ payable when initially purchased at time $t_{-}$ ). If there are no coupon payments over the arbitrage period (i.e. $F V C_{T}=0.$ ), no accrued interest $\langle A I_{T}=0\rangle$ ) and the deliverable bond is the one specifed in the futures contract $\cdot C F=1{\dot{}}, $ ), then not surprisingly the above formula for $F_{t}$ reduces to that for the futures price on a zero-coupon bond, namely $F_{t}=S_{t}e^{r(T-t)}$ .  

# 13.7.3 Arbitrage  

Proftable risk-free arbitrage would ensue if the invoice price of the futures ${I P F}_{T}$ received at $T$ , exceeds the cost of the synthetic futures $(S_{t}e^{r(T-t)}-F V C_{T})$ at $T$ .8 Today at $t$ , the arbitrageur borrows an amount $S_{t}$ at a cost of $r$ (the repo rate), purchases the bond and simultaneously sells T-bond futures. The amount owed at $T$ , the expiry of the futures contract is:  

$\c=$ Loan plus interest $S_{t}e^{r(T-t)}$ less the value $T$ of reinvested coupons $F V C_{T}$  

Hence the net (cash-market) cost at $T$ is $S_{t}e^{r(T-t)}-F V C_{T}$ , but the arbitrageur receives a larger amount $I P F_{T}$ . This arbitrage creates additional demand for cash-market bonds so $S_{t}$ increases and sales of bond futures will reduce $F_{t}$ until the equality in (13.17) is restored and the equilibrium futures price is given by Equation (13.18).  

However, the arbitrage strategy is not completely risk-free because the coupon payments received from the cash market T-bond have to be re-invested at interest rates which are unknown at $t=0$ (1 July). At $t$ , the best guess of the reinvestment rate for any coupon receipts would be the implied forward rate – and to lock in this rate would require a strip of FRAs. Hence cash-and-carry arbitrage only provides an approximate formula for the T-bond futures price.  

# EXAMPLE 13.4  

# Pricing T-Bond Futures  

Assume on 1 July, $C F=1.05$ , the yield curve is fat and the risk-free rate $r=3\%$ p.a. Note that on 1 July the invoice price $S_{t}$ of the cash market bond will be the ‘clean’ or quoted price $B_{t}$ plus any accrued interest on the bond (i.e. from 15 February 2017 to 1 July 2017 – see Figure 13.1). Assume the clean price of the deliverable bond on 1 July is $B_{t}=101$ . The accrued interest from 15 February 2017 to 1 July 2017 (Figure 13.1) is $A I_{t}=(136~\mathrm{days}/181~\mathrm{days})\&5={\&}3.76.$ The cash-market bond price is:  

$$
S_{t}=B_{t}+A I_{t}=\S101+\S3.76=\S134.76
$$  

Compounding $S_{t}$ forward to the delivery date of 11 September (i.e. over 72 days) $F V C_{T}=5.022$ . The net cost-of-carry in the cash market at $T$ is:  

$$
S_{t}e^{r(T-t)}-F V C_{T}=\S104.76e^{0.03(72/365)}-\S5.022=105.38-5.022=\S100.36
$$  

Accrued interest payable to the short-futures is $A I_{T}=(27\mathrm{days}/184\mathrm{days})\&5=\S0.73,$ hence:  

$$
F_{t}=(1/C F_{t})(S_{t}e^{r(T-t)}-F V C_{T}-A I_{T})=(1/1.05)(\mathbb{{\mathbb{S}}}100.36-\mathbb{{S}}0.73)=\mathbb{{S}}94.88-\mathbb{{S}}0.75)(5.05)
$$  

Note that this fgure, for the no-arbitrage price $F_{t}$ is an estimate, since we do not know the precise delivery date, the precise bond that will be delivered and the reinvestment rate of any coupons received on the underlying bond (since this may di!er from the current repo rate, if the yield curve shifts).  

# 13.8 T-BOND FUTURES SPREADS  

A spread is a long position in one asset and a short position in another (similar) asset. A T-bond futures spread can be used to speculate on twists or parallel shifts in the yield curve. For example, a trader Ms Bond could undertake a spread trade by buying a T-bond futures (which delivers a bond with at least 15 years to maturity) and simultaneously selling a 10-year T-bond in the cash market (i.e. which has a di!erent maturity/duration to the CTD bond in the futures). She might then proft after a change in interest rates as the futures price and cash-market prices change by di!erent amounts (because their underlying durations are di!erent). For example, if all interest rates fall by $1\%$ she would gain more on the long futures than she loses on the short bond position, because the duration of the futures is higher than the duration of the cash-market bond.  

A spread trade is less risky than holding just a naked futures position – although potential profts are also less. However, such a strategy would have to take account of margin requirements and any ‘haircuts’ on short-sales of bonds in the cash market. A spread trade may be less costly if two futures contracts are used, with di!erent maturities.  

# 13.8.1 Turtle Trade: Arbitrage Profits  

# 13.8.1.1 Buying the Spread  

First, let us examine how an arbitrage ‘June-September’ T-bond futures spread position can be used to exploit any mispricing along the yield curve (Figure 13.2). Suppose at $t=0$ (1 April 2017) we:  

(a) buy a T-bond futures which matures at $T_{1}$ (1 June 2017)   
(b) sell a T-bond futures which matures at $T_{2}$ (1 September 2017) and   
(c) you borrow money at the forward repo rate $f=4.16\%$ (applicable between June and September) by selling the June-Eurodollar futures on 1 April.  

![](1325ecf90fcdf883d242fc4c0dbfd987236dae1105a1902608e785b547b6047d.jpg)  

1 April: Futures spread $\mathbf{\Sigma}=\mathbf{\Sigma}$ long June-contract at ${{F}_{T1}}$ and short September-contract at $F_{T2}$  

We are buying the spread (i.e. we buy the nearby T-bond futures contract). When the nearby T-bond futures contract matures we take delivery of the eligible bond (which matures on 1 August 2038, say) and pay $F_{T_{1}}$ (plus any accrued interest, $A I_{T_{1}}$ ) with fnance raised by borrowing at the (forward) repo rate.  

We then ‘carry’ this cash market bond until 1 September when it is delivered against the short September-futures position and we receive $F_{T_{2}}$ (plus any accrued interest $A I_{T_{2}}$ , arising from the underlying bond’s next coupon payment on 1 February 2018). The (compound) return from this long-spread strategy9 is the implied repo rate ${\widehat{r}}\mathbf{:}$  

$$
\begin{array}{r l r}{\lefteqn{(1+\widehat{r})=\bigg(\frac{A m o u n t r e c e i\nu e d a t T_{2}}{A m o u n t p a i d a t T_{1}}\bigg)^{1/(T_{2}-T_{1})}}}\\ &{}&{=\bigg(\frac{F_{T_{2}}C F_{T_{2}}+A I_{T_{2}}+F V C_{T_{2}}}{F_{T_{1}}C F_{T_{1}}+A I_{T_{1}}}\bigg)^{1/(T_{2}-T_{1})}}\end{array}
$$  

where $F V C_{T_{2}}$ is the (future) value of any coupons paid on the ‘carried’ cash-market bond on 1 August 2017, compounded to $T=1$ September 2017. Note that the implied repo rate is a forward rate. If the implied repo rate $\widehat{r}=4.3\%$ (say) exceeds the cost of borrowing at the actual forward repo rate $f=4.16\%$ (applicable between 1 June and 1 September), then a long arbitrage spread trade undertaken on 1 April is guaranteed to be proftable.  

The actual repo borrowing rate is the forward rate $f=4.16\%$ , when viewed from $t=0$ (1 April 2017). How can we ‘lock-in’ this forward rate on 1 April? Today we sell Ju=ne-Eurodollar futures contracts at $F_{T_{1}}^{E u r o\Phi}=\mathfrak{H}99.$ . When we close out the Eurodollar futures in June, the e!ective cost (between June and September) is the implied forward rate $f=4.16\%(=100/99)^{365/90}-1)$ .10 You use the cash infow on 1 June from closing out several short Eurodollar futures contracts, to pay $F_{T_{1}}$ (plus accrued interest) for delivery of the eligible T-bond in the maturing June T-bond futures. Hence if the implied (forward) repo rate from buying the spread is $\widehat{\boldsymbol{r}}$ $(=4.5\%)$ and the cost of borrowing is $f$ $(=4.16\%$ , the actual forward repo rate), we undertake the following turtle trade on 1 April:  

# Turtle trade  

Buy the T-bond futures spread and sell June-Eurodollar futures.  

When the implied repo rate (i.e. the ‘percentage return’ on the T-bond spread trade) exceeds the actual (forward) repo cost of borrowing, an overall proft will be made on the turtle trade.  

# 13.8.1.2 Selling the Spread  

Suppose we have the reverse position on 1 April, namely the implied repo rate $\widehat{r}=4.5\%<f=$ $4.8\%$ , the actual (forward) repo rate. Then you sell the T-Bond spread, so on 1 April:  

(a) sell the June T-bond futures   
(b) buy the September T-bond futures and   
(c) you lend money at the forward repo rate $f=4.16\%$ (applicable between June and September) by buying the June Eurodollar futures on 1 April.  

Selling the June T-bond futures and buying the September T-bond futures is equivalent to borrowing at the forward rate $\widehat{r}=4.5\%$ . By buying the Eurodollar futures is equivalent to lending at $f=4.8\%$ . Hence the trade results in an arbitrage proft of $0.3\%$ .  

The above strategy is an intermarket spread since it involves two T-bond futures contracts which mature at di!erent dates but are on the same underlying asset (i.e. a cash-market T-bond). They are not risk-free trades because of the di\$culty of ascertaining the CTD bond in each contract and uncertainty surrounding the reinvestment rate of any coupons paid.  

# 13.9 SUMMARY  

• Contract details for T-bond futures are necessarily complex because of the use of the conversion factor (CF), the cheapest-to-deliver bond (CTD), and Wild Card Play.   
• Holders of cash-market T-bonds can hedge their position, using the duration based hedge ratio to determine the number of T-bond futures contracts $N_{F}$ to short. Conversely, to hedge a future purchase of cash-market T-bonds, you buy $N_{F}$ T-bond futures, today.   
• T-bond futures contracts are useful for hedging a corporate bond portfolio, even though corporate bond prices and T-bond futures prices might not be perfectly positively correlated (e.g. due to changes in credit risk of the corporate bond) – hence there will be some hedging error. This is a cross hedge.   
• Even when hedging a T-bond portfolio with T-bond futures a perfect hedge is not possible because of basis risk (i.e. the cash-market T-bond prices and futures prices do not move perfectly together). This is exacerbated by non-parallel shifts in the yield curve.   
• T-bond futures are used to increase (decrease) the e!ective duration of an existing cash-market bond portfolio, when the investor forecasts yields to fall (rise). This is a market timing strategy.   
• Speculation with T-bond futures often involves spread trading where the speculator takes a long position in nearby T-bond futures and a short position in T-bond futures with a longer maturity date (or vice versa). Spread trades can be used to speculate on parallel shifts and twists in the yield curve.  

• The fair price of a T-bond futures contract can be determined using cash-and-carry arbitrage. • Proftable arbitrage opportunities with T-bond futures are usually expressed in terms of the implied repo rate. If the implied repo rate di!ers from the actual repo rate (i.e. the cost of lending/borrowing funds), then proftable arbitrage is possible.  

# APPENDIX 13.A: HEDGING: DURATION AND MARKET TIMING  

First (for illustrative purposes), consider a cash-market (spot) position in two bonds, where $S_{i}$ $\mathbf{\Sigma}=$ (invoice) price of bond- $\cdot i$ and $N_{i}=$ number of bonds- $\mathbf{\nabla}\cdot\mathbf{\vec{l}}$ held $\mathrm{\Delta}N_{i}>0$ if held long or $N_{i}<0$ if short-sold). The dollar value and change in the cash-market T-bond portfolio is:  

Cash Market  

$$
\begin{array}{c}{{V_{s}=N_{1}S_{1}+N_{2}S_{2}}}\\ {{{}}}\\ {{d V_{s}=V_{1}(d S_{1}/S_{1})+V_{2}(d S_{2}/S_{2})=-[V_{1}(D_{1}d y_{1})+V_{2}(D_{2}d y_{2})]}}\end{array}
$$  

where we use the duration approximation, $d S_{i}/S_{i}=-D_{i}d y_{i}$ . For a parallel shift in spot yields $d y_{1}=d y_{2}=d y_{s}$ , then:  

$$
d V_{s}=-V_{s}(D_{s}d y_{s})
$$  

where $V_{s}\equiv V_{1}+V_{2}$ , $w_{i}=V_{i}/V_{s}$ for $i=1,2$ and $D_{S}\equiv w_{1}D_{1}+w_{2}D_{2}$ is the portfolio duration of the cash-market bond portfolio.  

T-bond futures  

The change in value of a portfolio consisting of ‘cash-market T-bonds $+\mathrm{T}$ -bond futures’ (ignoring accrued interest) is:  

$$
\begin{array}{r l}&{d V=d V_{s}+N_{F}\ z\ (d F/100)=V_{s}(D_{s}d y_{s})+N_{F}V_{F}(d F/F)}\\ &{\quad\quad=-[V_{s}(D_{s}d y_{s})+N_{F}V_{F}(D_{f}d y_{f})]}\end{array}
$$  

Assume the relationship between the change in the YTM of the cash-market T-bonds and the change in the yield (on the deliverable bond) in the T-bond futures contract is $d y_{s}=\beta_{y}d y_{f}$ , then:  

$$
d V=-[V_{s}D_{s}\beta_{y}+N_{F}V_{F}D_{f}]d y_{f}
$$  

Hedging  

To fully hedge your cash-market T-bond portfolio we set $d V=0$ , hence:  

$$
N_{F}=-\left(\frac{V_{s}}{V_{F}}\right)\left(\frac{D_{s}}{D_{f}}\right)\beta_{y}
$$  

which is sometimes referred to as the minimum variance hedge ratio.  

# Effective Duration and Market Timing  

Suppose a trader holds a cash-market (spot) T-bond portfolio and she wants to change the e!ective duration of the portfolio to some desired level $D_{d}$ , using T-bond futures contracts. The desired change $d V_{d}$ in her cash-market T-bond portfolio is:  

$$
d V_{d}=-V_{s}D_{d}d y_{s}=-V_{s}D_{d}(\beta_{y}d y_{f})
$$  

Equating (13.A.5) and (13.A.7):11  

$$
N_{F}=\left(\frac{V_{s}}{V_{F}}\right)\left(\frac{D_{d}-D_{s}}{D_{f}}\right)\beta_{y}
$$  

The cash-market T-bond position could be either net long or short – depending on the sign of $V_{s}\equiv V_{1}+V_{2}$ – and the cash-market portfolio duration could be positive or negative depending on the value of $D_{s}$ . For the moment assume $V_{s}$ and $D_{s}$ are both positive. Then (13.A.8) gives the required number of futures contracts to achieve a ‘desired duration’:  

$$
\begin{array}{r}{\begin{array}{r l}{\mathrm{If}D_{d}>D_{s}\quad\Rightarrow\quad}&{\mathrm{take~a~long~position~in~T\mathrm{-}b o n d~f u t u r e s,}}\\ {\mathrm{If}D_{d}<D_{s}\quad\Rightarrow\quad}&{\mathrm{take~a~short~position~in~T\mathrm{-}b o n d~f u t u r e s.}}\end{array}}\end{array}
$$  

Hence, to increase (decrease) the e!ective duration of an underlying (long) cash-market bond portfolio (with $D_{s}>0\}$ ), we go long (short) T-bond futures. This makes sense because if interest rates subsequently fall, then you make profts both from the cash market bond portfolio and the long T-bond futures contracts – this is equivalent to increasing the duration of the cash-market bond portfolio and is a form of ‘market timing’. If your forecasts are correct then you will make more proft by taking the long futures position rather than just holding your cash-market bond portfolio.  

Note that (13.A.6) the minimum variance hedge ratio is a special case of (13.A.8), where the desired duration, $D_{d}=0$ :  

$$
D_{d}=0\Rightarrow N_{F}=-\left({\frac{V_{s}}{V_{F}}}\right)\left({\frac{D_{s}}{D_{f}}}\right)\beta_{y}\Rightarrow\mathrm{a~short~position~in~T\mathrm{-bond~futures}}
$$  

# APPENDIX 13.B: IMPLIED REPO RATE AND ARBITRAGE  

The implied repo rate is another way of determining whether risk-free arbitrage profts are possible. The implied repo rate is the return from buying the underlying cash-market T-bond at $t=0$ for the invoice price $S_{0}=\left(B_{0}+A I_{0}\right)$ and simultaneously selling the futures for delivery at $T$ . The return or implied repo rate $\widehat{\boldsymbol{r}}$ (using discrete compounding) is:  

$$
\begin{array}{r l}&{1+\widehat{r}=\bigg(\frac{c a s h r e c e i\nu e d a t T f r o m h e d g e p o r t f o l i o}{c a s h p a i d o u t a t t=0f o r t h e u n d e r l y i n g b o n d}\bigg)^{1}\bigg/_{T}}\\ &{\qquad=\bigg(\frac{F_{0,T}C F_{0}+A I_{T}+F V C_{T}}{S_{0}}\bigg)^{1}\bigg/_{T}}\end{array}
$$  

where $F_{0,T}=$ futures price set at $t=0$ for payment at $T$ (when the underlying bond is delivered) and the conversion factor is $C F_{0}$ . The arbitrageur holds the underlying bond and receives coupon payments which can be reinvested over the period $t=0$ to $T$ to give a future value $F V C_{T}$ . The accrued interest on the deliverable bond at maturity of the futures contract is $A I_{T}$ . The cash-market bond has an invoice price of $S_{0}$ and this is fnanced by borrowing at the (actual) repo rate $r$ , at $t=0$ .  

Cash-and-carry arbitrage is proftable if the implied repo rate $\widehat{r}>$ actual repo rate r  

It is easy to see using (13.B.1) that if $\widehat{r}>r$ then:  

$$
\frac{F_{0,T}C F_{0}+A I_{T}+F V C_{T}}{S_{0}}>(1+r)^{T}
$$  

Part of the reason for using the implied repo rate to determine possible arbitrage profits is that it is straightforward to compare the implied repo rate with the quoted repo rate  

(cost of borrowing funds). Using (13.B.2), the elimination of any arbitrage profts implies the fair (no-arbitrage) T-bond futures price is:  

$$
F_{0,T}=(1/C F_{0})[S_{0}(1+r)^{T}-F V C_{T}-A I_{T}]
$$  

If we replace the discrete compound rate $(1+r)^{T}$ by the continuously compounded rate $e^{r T}$ then Equation (13.B.3) is equivalent to the formula for the ‘no-arbitrage’ or ‘fair price’ given by Equation (13.14) in the text.  

# EXERCISES  

# Question 1  

Explain whether you would undertake a long or short futures hedge if you plan to purchase a cash-market T-bond in 30 days’ time and you want to hedge against adverse outcomes.  

# Question 2  

On 1 July you hold a bond portfolio of $\$100$ with duration of 7 (years). The December US T-bond futures price is 95-12 (‘95 and 12/32’). Contract size of the T-bond futures is $\$100,000$ .  

The cheapest-to-deliver (CTD) bond has a duration of 9 years and a conversion factor of unity. On average, the change in the bond yield equals $90\%$ of the change in the futures yield.  

(a) How many T-bond futures contracts are needed to hedge your position over the next 2 months? (b) How can the duration of your bond portfolio be reduced to 3 (years)?  

# Question 3  

How does the ‘wild card play’ help the person who holds a short position in a US T-bond futures contract?  

# Question 4  

The current US, T-bond futures price is 101-12 ( 101-12/32). Which of the following three bonds is cheapest-to-deliver?  

<html><body><table><tr><td>Bond</td><td>Bond price (32nds)</td><td>Conversion factor (CF)</td></tr><tr><td>２</td><td>142-20</td><td>1.3690</td></tr><tr><td>3</td><td>120-00</td><td>1.1200</td></tr><tr><td>4</td><td>144-16</td><td>1.4100</td></tr></table></body></html>  

# Question 5  

The average duration of your $\$10$ US bond portfolio, on 15 February is 8 years. The September T-bond futures price is currently 110-16. The cheapest-to-deliver ‘Note’ against the futures contract has a duration of 7 years. How can you hedge against interest changes over the next 7 months? How many futures contracts do you require? (Ignore the complexities of the conversion factor and cheapest-to-deliver bond).  

# Question 6  

Intuitively, if you are long a bond portfolio with duration $\mathrm{D}=10$ years, how can T-bond futures be used to give a lower e!ective duration? Why might you want to lower the duration of your cash-market bond portfolio?  