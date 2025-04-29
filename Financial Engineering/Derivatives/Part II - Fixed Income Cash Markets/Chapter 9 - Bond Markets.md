---
tags:
  - bond_markets
  - coupon_bonds
  - default_risk
  - spot_yields
  - zero_coupon_bonds
aliases:
  - Bond Pricing
  - Chapter 9
  - Yield to Maturity
key_concepts:
  - Coupon bond pricing
  - Default risk in bonds
  - Risk-free arbitrage profits
  - Spot rates explained
  - Zero-coupon bonds analysis
---
# Bond Markets  

# Aims  

• To explain spot rates (yields) and the ‘yield to maturity’ on a bond. • To show that the ‘fair’ price of a coupon paying bond is determined by spot yields – otherwise risk-free arbitrage profts can be made by a strategy known as coupon stripping. • To show how the yield to maturity is ‘derived’ from the market price of the bond.  

There are a wide variety of diferent types of bonds. A conventional government bond usually pays to the holder a fxed amount of cash (‘the coupon’) every 6 months plus the maturity (redemption, par, or principal) value at the end of the bond’s life. However, not all bonds have fxed coupons or fxed maturity dates. For example, some corporate bonds can be redeemed (or ‘called’) prior to their maturity date while other corporate bonds (i.e. convertible bonds) can be exchanged for common stock (equity) of the issuer, at some future date. So convertibles have a ‘mixture’ of payments in terms of coupons and then dividends if converted into equity.  

Bonds are usually issued to obtain long term fnance – the initial maturities are from 1 year to 30 years (with some being non-redeemable and known as perpetuities). They are issued by governments, and their agencies (e.g. Municipal Securities in the US and Local Authority Bonds in the UK) and by the corporate sector. They may be denominated in the home currency of the issuer or in a foreign currency (e.g. a UK corporate issuing dollar denominated bonds). A key diference between government issued bonds and those issued by corporates, is default risk. Generally speaking government bonds denominated in the home currency are described as ‘risk-free’, meaning there is no default risk. This is because governments usually have the legal right to raise taxes or to print their own currency, in order to pay the interest and principal on the bonds. But even Government bonds issued by the US government are not entirely free of default risk – but we assume such risk is very low. However, Greek bonds issued in 2010 and denominated in euros were not perceived as being risk-free. This is because holders of Greek bonds might not believe that the Greek government has the (de facto) democratic legitimacy and ability to raise enough euros from taxes to pay the interest and principal – and the Greek government cannot ‘print’ euros (only the European Central Bank can). Hence Greek government bonds issued in the years after 2010 are subject to a high probability of default. Also, zero default risk would not necessarily be true for government bonds denominated in a foreign currency – as was the case for countries like Mexico and Argentina, who efectively defaulted on dollar interest payments on their dollar denominated bonds.  

In this chapter we discuss ‘risk-free’ government bonds, which provide the main analytic concepts for the reader to study other types of bonds mentioned above and how bond portfolios are hedged using futures and options.  

# 9.1 PRICES, YIELDS, AND RETURN  

We begin with an analysis of the relationship between bond prices, spot yields and the yield to maturity. After discussing ‘zero-coupon bonds’, we demonstrate how we can use risk-free arbitrage to price a coupon paying bond by considering it as a series of zero-coupon bonds. This allows a consistent methodology for the pricing of bonds.  

# 9.1.1 Pure Discount/Zero-coupon Bonds  

Bonds which have a single payout, but have a maturity greater than 1 year, are usually classifed as pure discount bonds or zero-coupon bonds. Suppose a pure discount bond has a single payout M(dollar) in $T$ years’ time. If we know $M,T$ and the observed market price $P_{0}$ then we can calculate the current (compound) spot rate (yield), $r_{i}$ , using:  

$$
r=\left[\frac{M}{P_{0}}\right]^{1/T}-1
$$  

Hence:  

$$
P_{0}=\frac{M}{(1+r)^{T}}
$$  

Example 9.1 calculates the spot rate (yield) for a zero-coupon bond with maturity of 6 years.  

# EXAMPLE 9.1  

# Spot Rates on a Zero-coupon Bond  

Data: The current price, $P$ of a 6-year, zero-coupon paying bond with maturity value $\$100,000$ is $\$81,350.06$ .  

Question: Calculate the compound spot rate (yield), $r$ .  

Answer: $r=(\S100,000/\S81,350.06)^{1/6}\mathrm{-}1=0.035(\mathrm{or}3.5\%\mathrm{p.a.})$  

Taking logarithms of (9.1b) and using the approximation $\ln(1+x)\approx x$ we obtain $\ln P=\ln M-r T$ and diferentiating (with respect to $r$ ) we obtain:  

$$
d P/P=-T d r=-D d r
$$  

Proportionate change in bond price $=-^{\ast}I$ uration’ Absolute change in yield  

For a zero-coupon bond, the time to maturity (in years) is also the ‘duration’ of the bond. The proportionate (percentage) change in the bond price is usually referred to as the (holding period) ‘return on the bond’.1  

For example, for a two-year zero-coupon bond $\quad T=D=2$ ), Equation (9.2) implies that when the spot yield increases from $2\%$ to $2.1\%$ p.a. over 1 week (say), then the percentage change in the bond price (over 1 week) will be a fall of around $0.2\%$ . Hence, if the initial price of the bond is $P=\$99$ , the price in 1 week’s time would be (close to) $\$98.8$ .  

If we have lots of ‘zeros’ of diferent maturities then we can observe their current market prices and calculate spot rates for 1 year, 2 year, 3 years, etc. For example, (compound) spot rates at $10\ \mathrm{a.m}$ . today might be 5, 5.12, 5.23, . . . 5.51, 5.52, 5.52, 5.52, . . . for years 1, 2, 3, . . . , 15, 16, 17, 18, . . . , respectively. If we plot a simple graph of the spot rates against time to maturity, then this is known as the (spot) yield curve (at $10\mathrm{a.m}$ . today) – here the yield curve is upward sloping and then fattens out for maturities longer than 16 years.  

What these spot rates imply is that if you want to borrow, say, $\$1,000$ today and pay back all the interest and principal in exactly 16 years’ time, then you will end up owing $\$2,362.42=81,000$ 1.0552 16. Alternatively, if the maturity value of a 16-year zero-coupon bond is $M=\$362.42$ , and the 16-year spot yield is $5.52\%$ , then the market price of the bond today is $P=\$1,000$ . So the 16-year spot rate is the cost of borrowing money today, with one single repayment in exactly 16 years’ time. As our yield curve is currently upward sloping, it costs more to borrow money the longer the time horizon over which you wish to borrow. Apart from the bid–ask spread (which we ignore), then the cost of lending money today, with one repayment in 1 year’s time is $5\%$ p.a., and with one repayment in 2 years it is $5.12\%$ p.a., etc.  

The price of zeros is determined by the supply of bonds (i.e. borrowers of money) and the demand for bonds (i.e. lenders of money). Usually, governments are borrowers of money and issue bonds while pension funds, insurance companies, and (older) individuals are lenders of money and they purchase bonds. The price of a ‘zero’ will change today, when the balance of supply and demand in the market for funds (for a particular maturity date), changes. But note that it is always true of fxed-income assets like bonds that the bond price and (spot) yields always move in opposite directions.  

Generally speaking interest rates of all maturities tend to move up and down together. For example, if at 3 p.m. all spot rates are higher by $0.1\%$ , say, this would be called a ‘parallel shift’ in the yield curve. Analytically, spot yields are the ‘building blocks’ for analysing fxed-income assets such as coupon-paying bonds, and other fxed income derivatives such as swaps, caps, and foors.  

# 9.1.2 Coupon Paying Bonds  

Coupon paying bonds provide a known stream of cash fows called coupons, C, payable each year (say) over the remaining life of the bond. Most bonds have a known fnal payment at maturity known as the ‘par value’, the ‘principal value’ or ‘maturity value’, $M$ (Figure 9.1). There are some bonds which although they pay coupons, are never redeemed and these are known as perpetuities (e.g. $6\%$ Consols’ issued by the UK government).  

Bond prices quoted in the fnancial press and on electronic trading screens are known as ‘clean prices’. The pricing formulas below all refer to the clean price. However, the actual price paid by an investor is known as the ‘invoice price’ and includes accrued or ‘rebate’ interest (see Cuthbertson and Nitzsche 2008).  

![](286b5e7c85fae80ef5a663bc29f90e2a73aec94eabb181c9d7cdbce16d4b8ae0.jpg)  
FIGURE 9.1 Coupon paying bond  

9.1.3 Coupon-yield (Interest-yield, Flat-yield, ‘Current-yield’ in USA)  

The ‘coupon-yield’ on a bond is usually quoted in the fnancial press and is calculated as:  

$$
I n t e r e s t-y i e l d=\frac{A n n u a l C o u p o n}{C u r r e n t C l e a n P r i c e}\times100\%
$$  

The ‘coupon-yield’ is a very poor measure of the return on a bond since:  

• it ignores any capital gains which occur if the bond is purchased at a price below its maturity value, $M$ ;   
• it ignores ‘interest-on-interest’ from coupon payments.  

# 9.1.4 Yield to Maturity (Redemption Yield)  

Knowing the market price $P$ , the coupon $c$ (here paid annually) the maturity value $M$ , and the number of years to maturity, $T$ then the yield to maturity (YTM), $y_{:}$ , is the solution to:  

$$
P=\frac{C_{1}}{(1+y)}+\frac{C_{2}}{(1+y)^{2}}+\ldots+\frac{C_{T}}{(1+y)^{T}}+\frac{M}{(1+y)^{T}}
$$  

It can be shown (using the annuity formula) that this simplifes to:  

$$
P=C\left[\frac{1}{y}-\frac{1}{y(1+y)^{T}}\right]+\frac{M}{(1+y)^{T}}=C\times A(y,T)+\frac{M}{(1+y)^{T}}
$$  

where the ‘annuity value’ is defned as: $A(\mathrm{y},\mathrm{T})=\left[\frac{1}{y}-\frac{1}{y(1+y)^{T}}\right]$  

The ‘annuity value’ is the present value of $\$1$ paid at the end of each year, for $T$ years using the YTM as the discount rate. The YTM is the rate $y$ which equates the present value of future cash fows $C_{i}$ and the maturity value $M$ , with the current market price. Hence, the YTM is the ‘internal rate of return’ (IRR) of the bond. Here $P$ , $C_{i}M$ and $T$ are known and we (or the Financial Times/Wall Street Journal) calculate $y$ using Excel’s ‘IRR’ inbuilt command.  

If coupon payments are annual then $i={1,2,3}$ . . . refers to years and $y$ is an annual (compound) rate. However, for government bonds the coupons are usually paid semi-annually and in this case we replace $y$ in the above formula by $y/2$ and $C_{i}$ is replaced by the semi-annual coupon payments $C_{i}/2$ (and $i=1$ for 6 months, $i=2$ for 1 year, etc.). It follows that $y/2$ is the ‘semi-annual rate’, and $y$ is the quoted ‘simple’ annual rate (which in the US is known as ‘the bond equivalent yield’). If $y=$ the (unknown) 5-year YTM (p.a.), then a 5-year bond with semi-annual coupon payments $\mathrm{\Delta}C/2$ every 6 months), has a market price given by:  

$$
\frac{C/2}{+y/2)}+\frac{C/2}{(1+y/2)^{2}}+\frac{C/2}{(1+y/2)^{3}}+\dots\dots+\frac{C/2}{(1+y/2)^{9}}+\frac{C/2}{(1+y/2)^{10}}+\frac{C/2}{(1+y/2)^{10}}
$$  

Knowing the market price of the bond and all the variables on the right-hand side of the above equation, we can calculate the YTM and a simple example is given in Example 9.2, where the YTM is $6\%$ p.a.  

# EXAMPLE 9.2  

# Calculation of YTM  

Data: The market price, $P$ of a 3-year, $4.5\%$ coupon paying bond with a face value of $\$1,000$ , is $\$959.37$ . Coupon payments are semi-annual ( $(6\times6$ months periods).  

Question: Calculate the YTM.  

$$
\begin{array}{c}{{P=\S22.50/(1+y/2)+\S22.50/(1+y/2)^{2}+\dots+\S22.50/(1+y/2)^{5}+}}\\ {{\S1,022.50/(1+y/2)^{6}=\S959.37}}\end{array}
$$  

The solution $\mathbf{\dot{y}}^{\prime}$ to the above equation is usually found using a simple algorithm (e.g. the IRR function in Excel. Excel gives $y=0.06$ (or $6\%$ ). This can be verifed by working out the PV of the RHS using $y=6\%$ , which is found to be $\$959.37$ .  

The YTM is made up of three elements:  

$Y T M=$ coupon rate $+$ interest on the coupons $^+$ capital gain (or loss) from the diference between the purchase price $P$ and the maturity value M.  

The YTM measures the (annual compound) rate of return on the bond if (i) it is held to maturity and (ii) all the future coupon payments can be reinvested (when received) at a rate of interest equal to the (current) YTM. If these conditions do not hold, then the YTM will not correctly measure the ‘return’ on the bond even if it is held to maturity.  

It is the assumption that the future coupon payments can be reinvested at the current YTM which creates problems, since we do not know today at what rate of interest we can reinvest these future payments. However, the YTM is the best single fgure we can use to (approximately) represent the average annual percentage return on the bond if it is held to maturity. The YTM is widely used when discussing strategies amongst bond market traders and traders of derivatives whose prices depend on interest rates (yields).  

The YTM can be calculated using the ‘clean price’ or the invoice price. For the UK when $P$ is the invoice price then $y$ is known as the gross redemption yield (and is published daily in the Financial Times). Note that the YTM does not determine (in an economic sense) the price of the bond – the YTM is derived from the observed market price of the bond. However, if someone has already calculated the YTM then Equation (9.4) can of course be used to calculate the bond price (see Example 9.3).  

# EXAMPLE 9.3  

# Calculation of Bond Price  

Data: 20-year, $4\%$ coupon paying bond, maturity value $M=\$1,000$ . The current YTM is $y=5\%$ p.a. Coupon payments are being made semi-annually ( $40\times6$ -month periods).  

Question: Calculate the price of the bond.  

Answer: $C=(0.04/2)\$1,000=\S20,$ $T=2(20\mathrm{years})=20\times6$ month periods $y/2=0.05/2=0.025$ semi annual rate  

The PV of the coupon payments is given by the annuity formula:  

$\mathrm{PV}\mathrm{(coupons)}=C[1-1/(1+y/2)^{T}]/(y/2)={\mathfrak{F}}20[1-1/(1.025)^{40}]/0.025=0.025\ \mathrm{(coss)}$ $\$502.06$  

of maturity payment $\mathbf{\varepsilon}=\$1,000/(1.025)^{40}=\S372.43$  

Market price of bond $=\$502.06+\S372.43=\S874.49$  

It is clear from Equation (9.4) that the YTM and the market price of a bond are negatively related and the relationship is non-linear (‘convex’ – see Figure 9.2).  

# Excel: Bond Price and Yields  

The Excel fle on the website calculates the prices of two diferent bonds for diferent values of the YTM and then graphs the ‘convex’ (non-linear) bond price-yield relationship for each of the two bonds. Duration and Modifed duration are also calculated using the Excel functions $\mathbf{\dot{\bar{\rho}}}=\mathbf{\Phi}$ DURATION’ and $\mathbf{\epsilon}^{\bullet}=$ MDURATION’.  

![](4fd138ca1f36fac3dc412fdf01f4a1e31d8da749950a55b58d26b1fed9c69693.jpg)  
FIGURE 9.2 Bond price and yield  

# 9.1.5 YTM and Coupon Rate  

The coupon rate (or coupon yield) is defned as $C/M$ . There are some ‘rules of thumb’ used by traders when discussing the relationship between the YTM and the coupon rate of a bond. It is easy to show that if the coupon rate equals the YTM, then the bond is currently trading at a market price equal to its maturity (par) value. For example, consider a bond with a $10\%$ (annual) coupon rate, which also has a YTM of $10\%$ and the bond has 2 years to maturity and a par (maturity) value of $M=£100$ . We can easily demonstrate that the market price of this bond equals its par value of £100. Using Equation (9.4):  

$$
P=£10/(1.1)+£110/(1.1)^{2}=£100
$$  

If the coupon rate $(C/M)$ is below the YTM, then the market price $P$ will be below the par value (of $M=£100\$ ) and the bond currently sells ‘at a discount’. Conversely, if the coupon rate $C/M$ is above the YTM the bond will today have a market price above its par value of $M=£100\cdot$ – it will be trading at a ‘premium’. The qualitative relationship between the market price, coupon rate $(C/M)$ and YTM is given in Table 9.1 and they can be deduced from the following rearrangement of Equation (9.4):  

$$
{\frac{P}{M}}={\frac{C}{M}}\left[{\frac{1-(1+y)^{T}}{y}}\right]+{\frac{1}{(1+y)^{T}}}
$$  

If the current YTM, $y=C/M$ , the coupon rate, then Equation (9.7) gives $P/M=1$ , that is the market price of the bond $P$ , equals its maturity value $M$ . Also, it follows that if $(C/M)$ is less than $y$ , then $(P/M)<1$ and the current market price will be less than the bond’s maturity value.  

TABLE 9.1 Yield and price relationship   


<html><body><table><tr><td>Bond sells at</td><td>Relationship</td></tr><tr><td>Par (P = M)</td><td>Coupon rate = YTM</td></tr><tr><td>Discount (P <M)</td><td>Coupon rate < YTM</td></tr><tr><td>Premium (P > M)</td><td>Coupon rate > YTM</td></tr></table></body></html>  

# 9.2 PRICING COUPON BONDS  

This section discusses why bonds are priced using spot rates. Bond prices that do not refect prevailing spot rates can be subject to coupon stripping and risk-free arbitrage opportunities – which is the reason market participants use spot rates to price bonds. The spot rate $r_{T}$ is the (annual compound) rate of return on an investment that has a one-of payout in $T$ years’ time. It is the return (yield) on a zero-coupon bond.  

$$
\mathrm{P}=\frac{M}{(1+r_{T})^{T}}
$$  

If there were zero-coupon bonds for all maturities then we could observe their prices $P_{1},P_{2}$ , etc. and use Equation (9.8) to calculate $r_{T}$ (for $T=1,2,3$ ). These spot rates would be the outcome of the demand and supply of zero-coupon bonds in the market. Any (non-callable) coupon bond can be viewed as a ‘bundle’ of zero-coupon bonds. Hence, the price of a coupon bond should equal the PV of the future coupon payments, where each coupon payment is discounted at the appropriate spot rate:  

$$
P={\frac{C_{1}}{(1+r_{1})}}+{\frac{C_{2}}{(1+r_{2})^{2}}}+\ldots+{\frac{C+M}{(1+r_{T})^{T}}}
$$  

Each $C_{i}$ may be viewed as a one-of payment at times $t=1,2,3,...,T$ (and for most bonds $C_{i}=C$ , a constant). The maturity (redemption) value $M$ is a one-of payment at time, $t=T$ . Each separate coupon (and $M$ ) may be considered as a strip of zero-coupon bonds, discounted at the spot rate applicable to payments at $t=1,2,3,\dots T.$ . Spot rates are the correct way to price government bonds, since all coupons at time $t$ on diferent bonds are discounted at the same spot rate $r_{t}$ . Once we have the spot rates, the price of a coupon paying bond is easy to calculate as shown in Example 9.4.  

# EXAMPLE 9.4  

# Pricing Coupon Paying Bonds Using Spot Rates  

Data: Bond-A : Exchequer Stock $8.75\%$ , annual coupon, 2 years to maturity, $M=£100$ Bond-B : Exchequer Stock $12\%$ , annual coupon, 2 years to maturity, $M=£100$ Current spot rates, $r_{1}=0.05$ (or $5\%$ ) and $r_{2}=0.06$ (or $6\%$ )  

Question: Calculate the market price of the two bonds.  

Answer: Pric $\mathrm{\Omega}\mathrm{:~(Bond-A)}=\mathrm{\Sigma}\mathrm{8.75/(1.05)^{1}}+\mathrm{\Sigma}\mathrm{108.75/(1.06)^{2}}=\mathrm{\Sigma}\mathrm{5105.12}$ Pric $\mathfrak{z}\left(\mathrm{Bond-B}\right)=\mathfrak{L}\mathbf{1}2/(1.05)^{1}+\mathfrak{L}\mathbf{1}12/(1.06)^{2}=\mathfrak{L}\mathbf{1}11.11$  

# 9.2.1 Calculation of Spot Rates  

We now turn to the problem of estimating spot rates when they are not directly observed in the market. In the US and the UK, T-bills which are risk-free pure discount bonds are only issued with maturities up to 1 year. In general, government bonds with maturities greater than 1 year are issued as coupon paying bonds. However, spot yields can be calculated from coupon-paying bonds in several ways and here we demonstrate the method known as bootstrapping. Example 9.5 considers the case where we can directly observe the 6-month and 12-month spot yields ( $\cdot\boldsymbol{r}_{1}$ and $r_{2}^{\cdot}$ ) on zero-coupon bonds but not the 18-month spot yield $r_{3}$ , since we assume there are no zero-coupon bonds with maturities longer than 1 year. However, the 18-month spot yield $r_{3}$ can be derived using the observed market price of a coupon paying bond with 18 months to maturity. As we see in later chapters, spot rates can also be calculated from observed Eurodollar futures prices and their implied forward rates and from observed swap rates.  

# EXAMPLE 9.5  

# Calculation of Spot Rates by Bootstrapping  

Data: Bond-A: 6-month zero coupon bond, spot rate $r_{1}=4\%$ p.a. Bond-B: 1-year zero-coupon bond, spot rate $r_{2}=4.2\%$ p.a. Bond-C: Coupon bond with maturity 1.5 years, face value, $M=\$100$ , coupon rate $=5\%$ , coupon paid every 6 month. Market price, $P=\$99.448$  

Question: Calculate the 18-month spot rate $(r_{3})$  

Answer: $\mathfrak{G}99.448=2.5/(1+r_{1}/2)+2.5/(1+r_{2}/2)^{2}+102.5/(1+r_{3}/2)^{3}$ Observed spot rates on 6-month and 12-month bills are $r_{1}=0.04$ and $r_{2}=0.042$ . Hence $99.448=2.4510+2.3982+102.5/(1+{r_{3}}/{2})^{3}$  

The only ‘unknown’ in the above equation is $r_{3}$ and $r_{3}=0.0542$ (or $5.42\%$ p.a.)  

Similarly, if we have coupon paying bonds for 2 years, 2.5 years, etc. then the bootstrapping procedure can be repeated to calculate spot rates for these years. In this way we can obtain the complete spot yield curve. Where a coupon paying bond does not exist for a particular maturity (e.g. for maturity of 7.5 years) then the spot rate can be derived as an interpolation of the (derived) 7-year and 8-year spot yields. In fact, it is a little more subtle than this since after deriving the spot yields for those years for which we have coupon paying bonds, a smooth curve is ftted to be ‘close to’ all these observed data points – using rather sophisticated techniques (e.g. cubic splines).  

# 9.2.2 Coupon Stripping  

Zero-coupon T-bonds can be created by dealer frms, by selling of the ‘ownership’ of the coupon payments from coupon paying bonds. However, observed interest rates on ‘stripped’ Treasuries can give a misleading measure of risk-free spot rates because (i) strips are less liquid/marketable, hence their yields refect a liquidity premium and (ii) there is preferential tax treatment for some holders of strips (e.g. some overseas purchasers) and this ‘tax efect’ is refected in observed yields. Even though spot rates are observable in the strips market, it may still be necessary to use ‘bootstrap procedures’ or ‘curve ftting’ to obtain good estimates of the true risk-free spot rates.  

We now demonstrate why coupon paying bonds should be priced using spot rates. This occurs because if coupon bonds are not priced using spot rates, then there is a potential (risk-free) arbitrage proft to be made from ‘coupon stripping’ the bond.  

Example 9.6 shows that the ‘fair price’ of a 2-year coupon paying bond, calculated using current spot rates is $\widehat{P}=\mathbb{S}972.4\bar{8}58$ . Suppose a dealer has not used spot rates to price the bond and is quoting a price of from selling 2 coupon $+$ Redemption value $\c=$ $\$1,040/(1.055)^{2}=\S934.3905$ – the bond is underpriced. You can make an arbitrage proft by ‘buying low and selling high’. You purchase the bond for $\$970$ from the dealer and simultaneously ofer to sell the frst coupon payment of $\$40$ to a pension fund and the second payment of $\$1,040$ to an insurance company. Given current spot-rates, the pension fund will be willing to pay you $\$38.0952$ today to secure the receipt of $\$40$ in 1 year’s time. Similarly the insurance company will be willing to pay you $\$934.3905$ today, to secure the receipt of $\$1,040$ in 2 years’ time. So today you receive a total of $\$923,4858$ from the pension fund and insurance company and you use this to purchase the 2-year coupon bond at $P=\$970$ , making a risk-free proft of $\$23,4858$ today. We assume that your trades do not afect current prices (or current spot yields).  

# EXAMPLE 9.6  

# Price of Coupon Paying Bonds  

Data:  

Coupon paying Treasury Bond, 2 years to maturity, $4\%$ (annual) coupon.   
Face value, $M=\$1,000$ . Quoted market price is $P=\$970$ .  

Observed 1-year spot rate $=5\%$  

Estimated 2-year spot rate $=5.5\%$  

Question: Calculate the ‘fair’ or ‘equilibrium’ price of the bond and hence show that there are profts to be made from coupon stripping.  

Answer: from selling 1 coupon $=\S40/(1.05)=\S38.0952$ from selling 2 coupon $^+$ Redemption value $=\mathbb{S}1,040/(1.055)^{2}=$ $\$934.3905$  

Using spot rates, ‘fair price’ $\widehat{P}=\$38.0952+\S934.3905=\S972.4858$  

Buy the bond for $P=\$970$ today and simultaneously sell the two ‘coupons’ and redemption value for $\$38.0952$ and $\$934.3905$ – making an arbitrage proft of $\$2.4858$ today.  

However, there are lots of arbitrageurs around to take advantage of this mispricing. So, many arbitrageurs buy the 2-year coupon bond, which will tend to increase its price. Also, by selling one-year and two-year strips, their prices fall (or equivalently their spot yields rise). Arbitrage will continue until the market price of the 2-year coupon bond equals the PV of the sum of the receipts from coupon stripping – that is, until the market price of the coupon bond equals its fair value. Since arbitrage here involves a near risk-free transaction – the market price of the bond will quickly refect its fair value. Our key result is therefore:  

The quoted price of a coupon bond is determined by the current term structure of spot rates. The YTM is then derived from the quoted price.  

# 9.3 SUMMARY  

• Spot rates (yields) refer to the cost of lending (or borrowing) money today, with the principal and interest payable at one specifc time in the future. • The YTM is an approximate measure of the annual return on a T-bond if it is held to maturity and all the future coupons are reinvested (at the current YTM). Hence, the YTM depends on (i) the coupon payments $c$ , (ii) any interest-on-interest on the reinvested coupons, (iii) the maturity value $M$ , (iv) the time to maturity of the bond,  

and (v) any capital gain (or loss) from the diference between the purchase price $P$ and the maturity value $M$ . • The ‘fair’ (‘no-arbitrage’) price of a coupon paying bond is determined by current spot yields – otherwise risk-free arbitrage profts can be made by a strategy known as coupon stripping. Once we have calculated the ‘fair’ price using current spot yields we can then infer the current YTM that is consistent with this price. • The market price of a bond and the yield to maturity YTM are inversely related.  

# EXERCISES  

# Question 1  

What is a Treasury ‘strip’?  

# Question 2  

What are the key features of a coupon paying bond that determines its yield to maturity? What are the strengths and defects of the yield to maturity as a measure of the return on the bond if held to maturity?  

# Question 3  

Assume that you require a $10\%$ (compound) return on a 5-year zero-coupon bond with a par (maturity) value of £1,000. What price would you pay for the bond today?  

# Question 4  

Consider a $7\%$ -coupon US government bond that has a par value of $\$1,000$ and matures 5 years from now. The coupon payments are annual. The current yield to maturity (YTM) for such bonds is $8\%$ p.a. (compound rate). Calculate the market price of the bond and state whether you expect this bond to sell at par, at a premium (over par), or at a discount.  

# Question 5  

Why are coupon paying bonds priced using spot yields? What then is the signifcance of the yield to maturity (YTM)?  

# Question 6  

Quoted (compound) spot rates (yields) are as follows:  

<html><body><table><tr><td>Year, t</td><td>Spot rate, % p.a.</td></tr><tr><td>1</td><td>r = 5.00</td></tr><tr><td>2</td><td>r2 = 5.40</td></tr><tr><td>3</td><td>r = 5.70</td></tr><tr><td>4</td><td>r4 = 5.90</td></tr><tr><td>5</td><td>r5 = 6.00</td></tr></table></body></html>  

(a) What are the discount factors for each year – that is, the value today of $\$1$ received in year $t?$   
(b) Calculate the present value PV and hence the fair price of the following Treasury notes/bonds with annual coupons, all of which have $M=\$1,000$ par value. (i) $5\%$ coupon, 2-year note (ii) $5\%$ coupon, 5-year note (iii) $10\%$ coupon, 5-year note   
(c) What are the one year (compound) forward rates applicable between (i) year-1 and year-2, (ii) year-2 and year-3?  