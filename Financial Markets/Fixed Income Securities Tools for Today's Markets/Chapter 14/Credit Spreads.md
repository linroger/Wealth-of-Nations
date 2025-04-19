---
tags:
  - asset_swap
  - bond_spread
  - credit_spreads
  - oas
  - yield_spread
aliases:
  - Bond Spread
  - Credit Spreads
  - OAS
key_concepts:
  - asset swap spreads
  - bond cash flows
  - credit risk
  - embedded options
  - yield spread
---

# 14.3 CREDIT SPREADS  

Credit spreads are the differences between the relatively high rates earned on fixed income instruments that are subject to credit risk and the relatively low rates on instruments with little or no credit risk. The simplest measure of credit spread is the yield spread, which is the difference between the yield on a bond and the rate or yield on a similar maturity interest rate swap or highly creditworthy government bond. Yield spreads, however, suffer from a number of drawbacks. First, a sufficiently liquid government bond or swap with a similar maturity might not exist. Second, yields reflect not only credit risk, but also the structure of a bond's cash flows. (See the discussion of the "coupon effect" in Chapter 3.) Third, yields reflect the value of embedded options, like the fixed-price call provisions discussed earlier, which have nothing to do with credit risk.  

A better measure of credit spread is referred to in this chapter as the bond spread. This term includes the spread defined in Chapter 3 and the more general option-adjusted spread (OAs) defined in Chapter 7. In the credit context, a bond spread is computed by assuming no default and finding the spread over a benchmark curve that prices a bond as it is priced in the. market. Because the market price incorporates the risk of default while this. pricing methodology does not, the bond spread is a metric of credit risk. Unlike yield spreads, bond spreads properly account for maturity and the. structure of cash flows. This approach, therefore, is suitable for bonds without embedded options. For bonds with embedded options, OAS is more. appropriate: by design, its computation of price accounts for the value of embedded options and, therefore, any remaining spread to the benchmark curve can be reasonably attributed to credit risk. Furthermore, as explained. in Chapters 3 and 7, the bond spread and OAS can be interpreted as the extra. spread earned by a bond if interest rates are unchanged or hedged against; if the spread is unchanged; and if the bond does not default.  

The measures of credit spread in this section are illustrated with the Gen-. worth 4.90s of 08/15/2023, a speculative-grade bond issued by an insurance company. Table 14.7 gives various measures of credit spread for this bond, as of August 15, 2021, when the 4.90s of 08/15/2023 have exactly two years to maturity. Given the market yield of $5.596\%$ and the two-year LIBOR swap rate of $0.288\%$ , the yield spread is the difference between those two rates, or 530.8 basis points. The bond spread, given the bond's market price of 98.70 and the term structure of forward swap rates as of the pricing date, is 531.1 basis points.5 Then, in the sense of the previous paragraph, the Genworth bond earns an annual rate of LIBOR plus 531.1 basis points.  

TABLE 14.7 Selected Credit Spreads for the Genworth 4.90s of 08/15/2023, as of August 15, 2021. The Price of the Bond is 98.70; Its Yield is. $5.596\%$ ; and the Par Swap Rate Is $0.288\%$ . Spreads Are in Basis Points..   


<html><body><table><tr><td>Spread Type</td><td>Spread</td></tr><tr><td>Yield Spread</td><td>530.8</td></tr><tr><td>Bond Spread</td><td>531.1</td></tr><tr><td>Par-Par Asset Swap Spread</td><td>526.4</td></tr><tr><td>Market Value Asset Swap Spread</td><td>533.3</td></tr></table></body></html>  

Other popular measures of spread are asset swap spreads. The point of an asset swap is to transform a fixed-rate, coupon bond into an asset that earns a spread over a short-term rate, like LIBOR. In the context of this chapter, asset swaps enable investors to earn credit spreads without having to bear the interest rate risk of long-term, fixed-rate bonds.  

Figure 14.2 illustrates one type of asset swap, the par-par asset swap,. or, more simply, the par asset swap. Thin lines indicate cash flows at the initiation of the asset swap; heavy lines indicate intermediate cash flows; and. dashed lines indicate cash flows at the maturity of the swap. At initiation, the. asset swapper buys the bond for $P$ per 100 face amount, earning a periodic. coupon payment of. $c$ . The purchase price is financed with 100 from the. repo desk and $P-100$ from the swap desk.6 Finally, through an interest rate. swap to the maturity of the bond, in addition to the up-front payment just. mentioned, the asset swapper periodically pays $c$ in exchange for receiving. LIBOR plus the spread, $s^{p a r}$ , on 100. Note that this trade requires no cash at initiation; earns LIBOR plus. $s^{p a r}$ minus the repo rate over the life of the. bond, so long as the bond does not default; and requires no cash at maturity, again, so long as the bond does not default. Hence, as desired, the investor has converted the fixed coupon payments of a bond into floating payments of LIBOR plus $s^{p a r}$ . Of course, there are losses if the bond defaults: in that. case, the asset swapper has to make coupon payments to the swap desk and,. at maturity, pay 100 to the repo desk, even though these payments will not be fully realized from the defaulted bond.  

The par asset swap spread, $s^{p a r}$ , can be determined by the condition that the interest rate swap with the swap desk is fair, that is, that the initial payment plus the present value of the floating leg equals the present value of the fixed leg, where discounting is at market swap rates.7 Mathematically, let $A^{\mathit{f x e d}}$ and $A^{f l o a t i n g}$ be the factors such that $c A^{\mathit{f i x e d}}$ gives the present value of the payments of $c$ on the fixed side of the swap and such that $s^{p a r}A^{\textit{t l}}$ oating gives the present value of the payments of $s^{p a r}$ on the floating side. Let $d$ be the discount factor for cash flows at maturity. Also, along the lines of Chapter 13, include a fictional notional amount of 100 at maturity on both legs of the swap, and note that the present value of receiving LIBOR and the final notional amount is par. Then, the fair pricing condition for the swap is,  

![](6fd9612f462c035a511866e01eb0ef41e2a11f778378e29aa8df804b8dd1fb4a.jpg)  
FIGURE 14.2 A Par-Par Asset Swap with Financing.  

$$
\begin{array}{c}{{(P-100)+100+100s^{p a r}A^{f l o a t}=c A^{f i x e d}+100d}}\ {{s^{p a r}=\frac{c A^{f x e d}+100d-P}{100A^{f l o a t}}}}\end{array}
$$  

From Equation (14.1), for a given swap rate curve, as the credit risk of the bond increases, $P$ decreases, which, in turn, increases the asset swap spread, $s^{p a r}$ . Table 14.7 reports that, as of August 15, 2021, the par asset swap spread of the Genworth 4.90s of $08/15/2023$ is 526.4 basis points.  

A second flavor of asset swaps, namely, a market value asset swap, is illustrated in Figure 14.3. The market value asset swap differs from the par asset swap in that. $P$ is borrowed from the repo desk, rather than 100;. $P-100$ is paid by the swap desk at the maturity rather than the initiation of the swap; and, as a result, LIBOR plus the spread,. $s^{m k t}$ , is earned on $P$ rather than 100. Following the same notation and logic as in the case of the par asset swap, the fair market value asset swap spread is given by,  

$$
\begin{array}{c}{{P+s^{m k t}P A^{q o a t}+(P-100)d=c A^{f x e d}+P d}}\ {{s^{m k t}=\displaystyle\frac{c A^{f x e d}+100d-P}{P A^{f l o a t}}}}\ {{=\displaystyle\frac{100s^{p a r}}{P}}}\end{array}
$$  

![](08a16533c6bf15a5e94377d219bc655ca2703274a1bbb0c9bc7300e373f22adc.jpg)  
FIGURE 14.3 A Market Value Asset Swap with Financing.  

where the final equality uses Equation (14.1). According to Table 14.7, the market value asset swap spread of the Genworth 4.90s of 08/15/2023, as of August 15, 2021, is 533.3 basis points. The relationship between the two asset swap spreads is quite intuitive: an investor can earn $s^{p a r}$ on 100 or $s^{m k t}$ on $P$ , which, from Equation (14.2), gives the same result. The choice between the two asset swap trades, therefore, depends not on earnings, but on collateral and counterparty risk considerations.9  

The final measure of credit spread considered in this section is an effec-. tive spread for corporate FRNs no longer priced at par. When an FRN is priced at par, its spread is particularly easy to interpret as a spread over the. short-term rate benchmark received in exchange for bearing credit risk. Over time, however, as the credit quality of the issuer changes, the price of an FRN. with a fixed spread changes. As a result, because an investor pays a premium or gets a discount to face amount when buying the FRN, in addition to its spread, that spread is no longer as easily interpreted..  

The effective spread converts an FRN's premium or discount into a run rate and adds it to the actual spread. Let the actual spread be $s^{\mathit{f l o a t}}$ ; the price of the floater $P$ ; the present value factor, as before $\overset{\cdot}{A}\overset{q l o a t}{\mathop{A}}$ ; and the effective spread $s^{e f f}$ . Then, investors are indifferent between receiving $s^{\mathit{f l o a t}}$ for a price of $P$ and $s^{e f f}$ for a price of 100 if,  

$$
\begin{array}{r}{100s^{e f f}A^{f l o a t}-100=100s^{f l o a t}A^{f l o a t}-P}\ {s^{e f f}=s^{f l o a t}+\frac{100-P}{100A^{f l o a t}}}\end{array}
$$  

This section concludes by noting that the trades described here for earn-. ing the credit spread are subject not only to the risk of default, but also to financing risk. Whenever a bond is purchased for a relatively long-term holding period, but is financed with short-term repo, there is the risk that the repo rate will increase by more than the discounting or benchmark rates. In that case, the bond will earn less than the benchmark short-term rate (e.g., LIBOR) plus the spread. An even more extreme risk is that repo lenders will refuse to roll positions, because they no longer wish to lend to the borrower, because they no longer wish to lend against a particular bond, or because they need the cash themselves. In that scenario, corporate bond investors with short-term repo financing will have to sell their bonds, most likely at a. loss, to repay outstanding repo loans. Financing risk in the context of credit. risk appears again, later in this chapter, as a key difference between bonds. and credit default swaps.  
