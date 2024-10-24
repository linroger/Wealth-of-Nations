---
aliases:
- Alias_273_Understanding Bonds, Pricing And The Risks.md
- Alias_276_Understanding Bonds, Pricing And The Risks.md
tags:
- tag_example
---

# UNDERSTANDING BONDS, PRICING AND THE RISKS

"My name is Bond, James Bond"

## ABSTRACT

In this article we illustrate how to price bonds and calculate the accrued interest, cleanand dirty price, from which we can compute a bond invoice i.e., the present value for a given cash investment in the bond. We present the classical bond pricing formulae and show how to modify this formula to account for accrued interest.

To be able to evaluate bond cash flows and compute their present value we must compute the yield to maturity (YTM) or the internal rate of return (IRR) of the bond. There is no closed-form analytical solution. Therefore, it must be solved for using an optimization algorithm such as Newton-Raphson. This requires an initial guess for the YTM. In this article, we present a highly accurate approximation formula for the YTM, which can be used as a good initial guess for low latency calculations.

To conclude we demonstrate bond pricing with a live market example and compute the accrued interest, cleanand dirty price for a US treasury bond. We show how to solve for its yield to maturity and compute the present value of the bond cash flows. With this information we show how to compute the present value of any cash investment in this underlying bond and assess the DV01 risk, that is the change in value of the investment for a one basis point fall in the bond yield. With this article we provide an Excel workbook to demonstrate all calculations.

Keywords: Bond, dirty price, clean price, accrued interest, yield to maturity, internal rate of return, cash flows, optimization, Newton-Raphson, low latency, DV01

## 1. INTRODUCTION TO BOND PRICING

[Bonds](Bonds.md) prices are quoted in percent terms and are quoted like a discount or growth factor. Equivalently, they can also be quoted as a yield to maturity, which is the internal rate of return (IRR). Using the bond price, we can compute the present value of a bond investment; simply multiply the investment notional by the price in percent to get the present value.

𝑃𝑟𝑒𝑠𝑒𝑛𝑡 𝑉𝑎𝑙𝑢𝑒 = 𝐼𝑛𝑣𝑒𝑠𝑡𝑚𝑒𝑛𝑡 × 𝐵𝑜𝑛𝑑 𝑃𝑟𝑖𝑐𝑒 (1)

Consider a bond quoted in with a price of 140.958963%. If we make an investment of USD 1,000,000 in this bond then the present value of our invested funds plus interest earned will be worth USD 1,000,000 x 140.958963% i.e., USD 1,409,589.63.

## 2. CALCULATION TYPES

[Bonds](Bonds.md) have many bespoke features and idiosyncrasies that must be accounted for when pricing and trading bonds. Such pricing features may modify the bond coupon schedule, discount factor calculations, tax considerations and many other parts of the bond pricing calculation. To simplify pricing considerations and mitigate legal recourse, bonds are grouped into calculation types by pricing feature. There are over 5,000 bond types of which around 50 are liquid and actively trade. US Treasuries have bond calculation type 1, this bond calculation type is sometimes referred to as the "US Treasury Street" method. On the Bloomberg terminal the calculation type can be found on the bond description page. Bloomberg also provides a full list of Bond calculation types and gives a brief description of the calculation methodology, (Bloomberg, 2016)

## 3. BOND PRESENT VALUE & PRICING FORMULAE

To compute the present value (PV) of a bond given the yield to maturity the following formula is used,$$PV={\frac{C/t}{(1+y/t)^{1}}}+{\frac{C/t}{(1+y/t)^{2}}}+{\frac{C/t}{(1+y/t)^{3}}}+\cdots+{\frac{P r i n c i p a l+C/t}{(1+y/t)^{n\times t}}}\quad{\tag{2a}}$$ Equivalently we can write this as,$$
PV=\sum_{i=1}^nC/t\cdot DF(i)+Principal\cdot DF(n)\quad\quad\quad\quad\tag{2b}$$
with$𝐷𝐹(𝑖) = \frac{1}{(1+\frac{y}{t})^{i}}$  and where C is the annual coupon rate, t is the number of coupons per year, y is the yield to maturity (or internal rate of return, IRR) and n is the number of years to maturity. We can compute the bond price in percent from the bond present value as follows,$$𝑃𝑟𝑖𝑐𝑒 = \frac{𝑃𝑉}{𝐷𝑒𝑛𝑜𝑚𝑖𝑛𝑎𝑡𝑖𝑜𝑛}\tag{3}$$
To illustrate bond pricing, let us consider the following bond,

- Name: Coca-Cola 7.5% maturing 27-Sep-2025
- Type: Eurobond, Annual Coupons (30/360)  Settlement:
- Settlement: 27-Sep-2022
- Denomination: USD 1,000
- Coupon: 7.50%
- Bond Yield or IRR:  8.00%

As illustrated in figure (1), we calculate the bond present value using equation (2b), from which we can compute the bond price using equation (3). Firstly, we compute the discount factors at each time period. Secondly, we scale each cash flow by the corresponding discount factor to compute each cash flow's present value. Thirdly, we sum cash flow PV's giving a total bond PV of USD 987.11. Finally, we divide the bond PV by the bond denomination USD 1,000, which gives the bond price of 98.711%.

|time|0|1|2|3|
|---|---|---|---|---|
|Discount|Factor|0.9259|0.8573|0.7938|
|Present|Value|69.44|64.3|853.37|
|Net|Present|Value|987.11||
|Bond|Price|98.7115%|||

![](CleanShot%202024-02-06%20-000246@2x.png)
When pricing bonds part-way through a coupon period the bond pricing formula is modified as follows,

$$P V={\frac{C/t}{(1+y/t)^{a}}}+{\frac{C/t}{(1+y/t)^{a+1}}}+{\frac{C/t}{(1+y/t)^{a+2}}}+\cdots+{\frac{P r i n c i p a l+C/t}{(1+y/t)^{a+m}}\tag{4a}}$$

Equivalently we can write this as,

$$P V=\sum_{i=1}^{n}C/t\cdot D F(i)+P r i n c i p a l\cdot D F(n)\tag{4b}$$

with$𝐷𝐹(𝑖) = \frac{1}{(1+\frac{y}{t})^{a+i-1}}$and where a is the fraction of the current coupon remaining i.e., the number of days to the next coupon / the total number of days in the current coupon period and m is the number of whole coupons to maturity. If we price the same Coca-Cola bond but this time with a mid-coupon settlement date that is 133 days after the coupon start date, then using equations (3) and (4b) we arrive at the price illustrated in figure (2) following the same steps as in figure (1).
![](CleanShot%202024-02-06%20-000245@2x.png)
 Figure 2: Illustration of Coca-Cola Bond Price when Pricing Mid-Coupon

### 4. ACCRUED INTEREST, CLEAN AND DIRTY PRICES

When trading bonds mid-coupon, the partial interest accrued from the coupon start date to the transaction settlement date is called the **accrued interest**. So far, all the prices we have looked at have been **dirty prices**, which is the present value of all bond coupons to be received. However, any accrued interest belongs to the seller and must be paid to the seller on the settlement date. The present value of remaining coupons, when normalized into percent, is called the **clean price**. It is calculated by subtracting the accrued interest in percent from the dirty price.$$\text{𝐶𝑙𝑒𝑎𝑛 𝑃𝑟𝑖𝑐𝑒} = \text{𝐷𝑖𝑟𝑡𝑦 𝑃𝑟𝑖𝑐𝑒} − \text{𝐴𝑐𝑐𝑟𝑢𝑒𝑑 𝐼𝑛𝑡𝑒𝑟𝑒𝑠𝑡} \tag{5}$$

 The accrued interest in cash terms and as a percent is calculated as follows,$$\text{Accrued Interest} = \left(\frac{\text{Number of days Accrued}}{\text{Total Days in Coupon Period}} \right) \times \text{Full Coupon} \tag{6a}$$

$$\text{Accrued Interest in \%} = \left(\frac{\text{Accrued Interest}}{\text{Denomination}} \right) \times 100 \tag{6b}$$
For the Coca-Cola bond the accrued interest is calculated as,$$A c c r u e d\;I n t e r e s t=\left({\frac{200}{360}}\right)\times75=41.67$$

$$A c c r u e d\;I n t e r e s t\;i n\;\%=\left(\frac{41.67}{1,000}\right)=4.167\%$$
Having calculated the dirty price as 96.426% we can subtract the accrued interest of 4.167% to obtain a clean price of 92.259% as follows,

| Bond Prices | PV |  | Accrual Fraction |
| ---- | ---- | ---- | ---- |
| Dirty Price | 103.023% | 1,030.23 | 0.5556 |
| Accrued Interest | 4.167% | 41.67 |  |
| Clean Price | 98.857% | 988.57 |  |

## 5. YIELD TO MATURITY (YTM)

Bond prices can also be quoted as a yield to maturity (YTM), which is the bond's internal rate of return (IRR). Given a bond price we can compute the YTM by reverse engineering equation (4a) for the yield to maturity i.e., the y term,

$$P V={\frac{C/t}{(1+y/t)^{a}}}+{\frac{C/t}{(1+y/t)^{a+1}}}+{\frac{C/t}{(1+y/t)^{a+2}}}+\cdots+{\frac{P r n c i p a l+C/t}{(1+y/t)^{a+m}}}$$
 There is no analytical solution for the yield to maturity, it must be solved for using the Newton-Raphson technique or a similar search method. The Newton-Raphson method requires an initial guess. The better the guess the faster we can solve for a solution with fewer solver iteration steps. A reasonable guess for the yield to maturity might be the bond coupon rate. This works well for bonds trading close to par or 100, however bond coupons can be zero and many bonds trade far from par. A better, low latency initial guess that is highly accurate and reduces the number of search iterations is specified below,$$\text{Initial Guess} =$\left(\text{Coupon}+\left(\frac{\text{Par}-\text{Clean Price}}{\text{Time to Maturity}}\right)\right)/\left(\frac{\text{Par}+\text{Clean Price}}{2}\right) \tag{7}$$

The intuition behind this initial guess is to consider that each year we earn coupon interest plus we gain/lose on the bond price if not at par, we accrue this on average between the initial bond price (par) and the maturity price. Using the initial guess from equation (7) we can quickly find the yield to maturity in approximately three solver iterations.

## 6. DV01

The DV01 is a measure of bond risk, it captures the change in present value of a bond investment for a down-shift of one basis point (0.01%) in the bond yield to maturity. It is simple to calculate numerically, we reprice the bond with the yield shifted down by one basis point (1bps) compute the change in value.$$
DV01=\text{Bond P}V(YTM-0.01\%)-\text{Bond P}V(YTM)\tag{8}

$$
## 7. US TREASURY BOND EXAMPLE

To illustrate how to use all the different formulae presented, let us consider the following US treasury bond. It pays an annual coupon of 6.0% in two semi-annual payments of 3.0% and matures on 15th Feb 2026. 

Given a settlement or valuation date of 10th June 2016 there are 116 days of accrued interest owed to the seller out of a total of 182 accrual days within the current coupon period. The bond cash flows are based on the bond denomination of USD 1,000 as illustrated in figure (6). The present value of these bond coupons is evaluated using equation (4b) requoted below, $$PV=\sum_{i=1}^nC/t\cdot DF(i)+Principal\cdot DF(n)$$
We pay special attention that the discount factor for the ith bond coupon is calculated as follows to allow for accrued interest, $$𝐷𝐹(𝑖) = \frac{1}{(1+\frac{y}{t})^{a+i-1}}\tag{8}$$
where y denotes the yield to maturity in percent, t the number of coupons paid per year and a the coupon accrual fraction i.e., the fraction of the current coupon yet to accrue and be paid.  

To value the bond cash flows, we need to compute the yield to maturity given the target dirty bond price. We compute the yield to maturity using the NewtonRaphson method and a highly accurate initial guess calculated using equation (7) requoted below, Iteratively pricing the cash flows using the solver's iterative guess for the yield to maturity leads to an exact solution for the yield to maturity in three solver iterations, see figure (8). Having discovered the bond yield of 1.624644% we compute the total present value of the bond cash flows in figure (6).  We compute the dirty bond price using equation (3), the accrued interest using equation (6) and the clean price using equation (5). 

If we invest USD 1,000,000 in this US treasury bond, then we can compute the invoice or present value of this investment with coupons accruing interest of 6.00% 
by scaling by the appropriate bond price by the bond price using equation (1) as shown in figure (10). The total PV corresponds to the dirty price and the total coupons received. However, we must pay accrued interest to the bond seller. The net present value less accrued interest is denoted principal in figure (10) and corresponds to the clean price. 

The DV01 risk reflects the bond risk and is calculated numerically using equation (7). Should the yield to maturity fall (rise) by 1 basis point we will make a profit (loss) of USD 1,085.48, 


![](CleanShot%202024-02-06%20-000247@2x.png)