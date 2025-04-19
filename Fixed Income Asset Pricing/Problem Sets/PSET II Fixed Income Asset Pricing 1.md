---
linter-yaml-title-alias: FIXED INCOME ASSET PRICING
title: PSET II Fixed Income Asset Pricing 1
tags:
  - duration_convexity
  - fixed_income_asset_pricing
  - interest_rate_hedge
  - leveraged_inverse_floater
  - term_sheet
aliases:
  - Homework 2
  - JCH Fixed Income Group
  - LIF
  - PSET II
key_concepts:
  - Cash flows decomposition
  - Convexity
  - Duration calculation
  - Fixed rate note
  - Leveraged Inverse Floaters
---

# PSET II Fixed Income Asset Pricing 1

Bus 35130
Spring 2024
John Heaton
March 25,  2024

## HOMEWORK 2 DUE AT THE BEGINNING OF CLASS 3

This homework is on the pricing and risk assessment of Leveraged Inverse Floaters. Please,  write the solution to the homework as a clean report addressed to the principals of the fixed income group at JCH Fixed Income Group,  LLP. The principals of JCH Fixed Income Group are very demanding,  so make sure to describe exactly the source of your results. However,  the report must be clean and concise. An appendix to the report may contain any additional material. The data for this homework are collected in the data file *HW2 Data.xls* available on canvas. Note 1: For each section below,  there are questions that require pencil and paper (PP) answers,  and questions that require actual computation using data and computer programs (CP). You are to do both. Note 2: As with previous homework assignments there are "guides" for doing the homework in Excel,  Matlab and Python. In each code provides partial solutions to the questions.

To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.

## LEVERAGE INVERSE FLOATERS

Recommended Reading: Veronesi's Book. Chapter 2 (esp. 2.8); Chapter 3 (esp. 3.7) In an environment of low interest rates,  inverse floaters are popular investment vehicles that allow a fund manager to obtain a higher yield,  by betting on the direction of the movement in interest rates. In particular,  consider the following term sheet for a Leveraged Inverse Floater.

## LEVERAGED INVERSE FLOATER TERM SHEET

| Date                    | February 17,    2009                                        |
|-------------------------|----------------------------------------------------------|
| Maturity                | February 17,    2014 (5 year)                               |
| Payments Frequency      | Semi-annual                                              |
| Interest Payment        | Base Interest Rate minus 2 times Reference Interest Rate |
| Base Interest Rate      | 10%                                                      |
| Reference Interest Rate | 6 month T-bill rate with standard 6 month lag            |

### GENERAL EQUATIONS
#### Z-FACTOR

The Z-Factor is calculated as:

$$Z = \frac{P}{F}$$

where:

- $P$is the price of the bond.
- $F$is the face value of the bond.
#### CONTINUOUSLY COMPOUNDED YIELD

The Continuously Compounded Yield is calculated using the formula:

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T}$$

where:

- $F$is the face value of the bond.
- $C$is the coupon payment.
- $P$is the price of the bond.
- $T$is the time to maturity in years.
- $\ln$denotes the natural logarithm.
#### SEMI ANNUALLY COMPOUNDED YIELD

The Semi Annually Compounded Yield is calculated using the formula:

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right]$$

where:

- $F$is the face value of the bond.
- $C$is the coupon payment.
- $P$is the price of the bond.
- $T$is the time to maturity in years.
### CALCULATIONS FOR MATURITIES 0.5,  1,  AND 1.5 YEARS
#### MATURITY 0.5 YEARS
- **Given Values**:
- Price ($P$): 100.5
- Face Value ($F$): 100
- Coupon Payment ($C$): 1.25 (Assuming a 2.5% annual coupon rate,  prorated for 0.5 years)
- Time to Maturity ($T$): 0.5
- **Z-Factor**:

$$Z = \frac{P}{F} = \frac{100.5}{100} = 1.005$$

- **Continuously Compounded Yield**:

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 1.25}{100.5})}{0.5} \approx 0.005992$$

- **Semi Annually Compounded Yield**:

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 1.25}{100.5} \right)^{\frac{1}{1}} - 1 \right] \approx 0.006001$$

#### MATURITY 1 YEAR
- **Given Values**:
- Price ($P$): 101
- Face Value ($F$): 100
- Coupon Payment ($C$): 2.5 (Assuming a 2.5% annual coupon rate)
- Time to Maturity ($T$): 1
- **Z-Factor**:

$$Z = \frac{P}{F} = \frac{101}{100} = 1.01$$

- **Continuously Compounded Yield**:

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 2.5}{101})}{1} \approx -0.024170$$

- **Semi Annually Compounded Yield**:

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 2.5}{101} \right)^{\frac{1}{2}} - 1 \right] \approx -0.024024$$

#### MATURITY 1.5 YEARS
- **Given Values**:
- Price ($P$): 101.5
- Face Value ($F$): 100
- Coupon Payment ($C$): 3.75 (Assuming a 2.5% annual coupon rate,  prorated for 1.5 years)
- Time to Maturity ($T$): 1.5
- **Z-Factor**:

$$Z = \frac{P}{F} = \frac{101.5}{100} = 1.015$$

- **Continuously Compounded Yield**:

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 3.75}{101.5})}{1.5} \approx -0.030738$$

- **Semi Annually Compounded Yield**:

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 3.75}{101.5} \right)^{\frac{1}{3}} - 1 \right] \approx -0.030503$$

---

# GENERAL EQUATIONS

## Z-FACTOR

The Z-Factor is calculated as:

$$Z = \frac{P}{F}$$

where:

- $P$is the price of the bond.
- $F$is the face value of the bond (assumed to be 100).

## CONTINUOUSLY COMPOUNDED YIELD

The Continuously Compounded Yield is calculated using the formula:

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T}$$

where:

- $F$is the face value of the bond (assumed to be 100).
- $C$is the coupon payment.
- $P$is the price of the bond.
- $T$is the time to maturity in years.
- $\ln$denotes the natural logarithm.

## SEMI ANNUALLY COMPOUNDED YIELD

The Semi Annually Compounded Yield is calculated using the formula:

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right]$$

where:

- $F$is the face value of the bond (assumed to be 100).
- $C$is the coupon payment.
- $P$is the price of the bond.
- $T$is the time to maturity in years.

# CALCULATIONS FOR MATURITIES 0.5,  1,  AND 1.5 YEARS

## MATURITY 0.5 YEARS
- Price ($P$): 102.6953
- Face Value ($F$): 100 (assumed)
- Coupon Payment ($C$): 100 × 0.03 × 0.5 = 1.5 (semi-annual coupon rate of 0.03,  prorated for 0.5 years)
- Time to Maturity ($T$): 0.5

### Z-FACTOR

$$Z = \frac{P}{F} = \frac{102.6953}{100} = 1.026953$$

### CONTINUOUSLY COMPOUNDED YIELD

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 1.5}{102.6953})}{0.5} \approx 0.054429$$

### SEMI ANNUALLY COMPOUNDED YIELD

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 1.5}{102.6953} \right)^{\frac{1}{1}} - 1 \right] \approx 0.054921$$

## MATURITY 1 YEAR
- Price ($P$): 105.7617
- Face Value ($F$): 100 (assumed)
- Coupon Payment ($C$): 100 × 0.0325 = 3.25 (semi-annual coupon rate of 0.0325)
- Time to Maturity ($T$): 1

### Z-FACTOR

$$Z = \frac{P}{F} = \frac{105.7617}{100} = 1.057617$$

### CONTINUOUSLY COMPOUNDED YIELD

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 3.25}{105.7617})}{1} \approx -0.031734$$

### SEMI ANNUALLY COMPOUNDED YIELD

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 3.25}{105.7617} \right)^{\frac{1}{2}} - 1 \right] \approx -0.031438$$

## MATURITY 1.5 YEARS
- Price ($P$): 107.7109
- Face Value ($F$): 100 (assumed)
- Coupon Payment ($C$): 100 × 0.0288 × 1.5 = 4.32 (semi-annual coupon rate of 0.0288,  prorated for 1.5 years)
- Time to Maturity ($T$): 1.5

### Z-FACTOR

$$Z = \frac{P}{F} = \frac{107.7109}{100} = 1.077109$$

### CONTINUOUSLY COMPOUNDED YIELD

$$Y_{cc} = \frac{\ln(\frac{F + C}{P})}{T} = \frac{\ln(\frac{100 + 4.32}{107.7109})}{1.5} \approx -0.035018$$

### SEMI ANNUALLY COMPOUNDED YIELD

$$Y_{sa} = 2 \times \left[\left(\frac{F + C}{P} \right)^{\frac{1}{2T}} - 1 \right] = 2 \times \left[\left(\frac{100 + 4.32}{107.7109} \right)^{\frac{1}{3}} - 1 \right] \approx -0.034654$$

---

Do the following:

1. Bootstrap methodology
(PP) Describe **bootstrap** methodology for extracting the term structure of interest rates.

- Step 1: We begin the bootstrap methodology for
- The bootstrap methodology extracts interest rates embedded in the prices of zero coupon bonds of a similar credit risk across different maturities. It begins with the aggregation of the market prices for similar types of bonds across the maturity spectrum. Using the market price and semiannual coupon for the shortest maturity bond,  we can extract the price of the zero coupon bond with the same maturity for this cash flow strip. Using this zero coupon bond price,  we can then solve for the zero coupon bond price for the next shortest maturity,  and once we calculate this,  we can then solve for the zero coupon bond price of the following shortest maturity cash flow strip. We continue this process until we reach the final maturity. Once we accomplish this,  we are left with a range of zero coupon bond prices for various maturities at a given date. From these zero coupon bond prices,  we can then derive the spot yield,  which would be the discounting factor used to discount a \$100 face value bond to the corresponding zero coupon bond price. This would give us the spot yields for the range of maturities,  which forms the term structure.

> [!NOTE]
> 1. Gather market data:
>
> 	 - Collect the available market data for various fixed-income securities,  such as government bonds,  [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]],  or interest rate swaps.
> 	 - The data should include the security's price,  coupon rate (if applicable),  maturity date,  and any other relevant information.
> 1. Identify the shortest maturity security:
>
> 	 - From the collected market data,  identify the security with the shortest maturity date.
> 	 - This security will serve as the starting point for the bootstrap process.
> 1. Determine the spot rate for the shortest maturity:
>
> 	 - Calculate the spot rate (zero-coupon rate) for the shortest maturity security.
> 	 - For a zero-coupon bond,  the spot rate is simply the yield to maturity.
> 	 - For a coupon-bearing bond,  the spot rate can be derived from the bond's price and coupon payments using the following formula:
> Bond Price = Coupon Payments × Discount Factors + Face Value × Discount Factor at Maturity
> where Discount Factor = 1 / (1 + Spot Rate)^Time to Maturity
> 1. Move to the next shortest maturity:
>
> 	 - Select the security with the next shortest maturity date from the remaining market data.
> 1. Determine the discount factors for known maturities:
>
> 	 - Using the spot rates calculated in the previous steps,  determine the discount factors for all maturities up to the current security's maturity.
> 	 - The discount factor for a given maturity is calculated as: Discount Factor = 1 / (1 + Spot Rate)^Time to Maturity
> 1. Calculate the spot rate for the current maturity:
>
> 	 - Use the bond pricing formula to set up an equation that relates the security's price to its coupon payments and the unknown spot rate.
> 	 - Solve the equation for the unknown spot rate,  considering the discount factors for the known maturities.
> 	 - This spot rate represents the zero-coupon rate for the current maturity.
> 1. Repeat steps 4-6:
>
> 	 - Continue the process by moving to the next shortest maturity security and repeating steps 4-6.
> 	 - At each iteration,  use the previously calculated spot rates to determine the discount factors for the known maturities and solve for the unknown spot rate.
> 1. Construct the yield curve:
>
> 	 - After completing the iterations for all available maturities,  the result is a series of spot rates corresponding to different maturities.
> 	 - Plot these spot rates against their respective maturities to create the yield curve.
> 	 - The yield curve represents the term structure of interest rates,  showing the relationship between interest rates and maturities.
> 1. Interpolation and extrapolation (optional):
>
> 	 - If desired,  interpolation techniques can be used to estimate spot rates for maturities that are not directly observed in the market data.
> 	 - Extrapolation methods can be employed to extend the yield curve beyond the longest available maturity.

(PP) The *AllBondQuotes 20090217* tab of the data file provided contains Treasury Bills,  Notes and Bonds on February 17,  2009. Use these data to manually compute the spot rates for maturity 0.5,  1,  and 1.5. Show your work. TIP: Maturity 0.4999
can be considered 0.5,  and so on.

$$\begin{align*}
Z(0,   0.5) &= \frac{102.6935 - 99.70412776}{1.03} \\
Z(0,   1) &= \frac{105.7617 - 0.0325 \times 99.70412776 - 99.92425116}{1.0325} \\
Z(0,   1.5) &= \frac{107.7109 - 0.0288 (99.29125116 + 99.70412776)}{1.0288} - 99.1395 \\
r &= 2 \left( \frac{100}{(99.7042 - 1)^2} \right) - 0.00593355 \\
r &= 2 \left( \frac{100}{(99.29125116 + 1)^2} \right) - 0.000709507 \\
r &= 2 \left( \frac{100}{(99.1395 + 1)^{2/3}} \right) - 0.00576968
\end{align*}$$

(CP) The *AllBondQuotes 20090217* tab of the data file provided contains Treasury Bills,    Notes and Bonds on February 17,    2009. (i) Use these data to bootstrap the term structure of interest rates for as long a maturity as possible,    and obtain the discount function. In particular,    you will see that for several maturities,    you will have a choice of which bonds to use in your bootstrap.

Compute two discount curves,    (a) one that uses the most recently issued bonds (as of 02/19/2009),    and (b) one that uses the oldest bonds. Discuss the differences. Make sure to report what data you actually use for the bootstrap as well as any approximation you have to carry out. \[Note: The bonds with highest coupon are the oldest ones].
(ii) Plot the resulting term structure of interest rates (i.e. the spot rate function)
for both cases (a) and (b). Discuss the difference and any other visible feature of the yield curve.

The two term structures appear to be roughly similar,    although the off the run bonds appear to have greater fluctuations,    and at times,    a higher spot rate. This could be due to the fact that off the run bonds are not traded as regularly,    and are oftentimes held in a portfolio until maturity. This means that the market for off the run bonds is more illiquid than the market for on the run bonds,    and that this would result in the less smooth term structure we observe.

 ![500](PSET%20II%20Fixed%20Income%20Asset%20Pricing-20240401170538265.png

 ![500](PSET%20II%20Fixed%20Income%20Asset%20Pricing-20240401184921797.png)

|           |                |                |               |          |                     |                     |
| --------- | -------------- | -------------- | ------------- | -------- | ------------------- | ------------------- |
| Dates     | Bond Price Old | Bond Price New | Annual Coupon | Maturity | Spot Rate Old Bonds | Spot Rate New Bonds |
| 8/15/2009 | 102.6953       | 101.5000       | 6.00          | 0.49     | 0.01080258          | 0.00492611          |
| 2/15/2010 | 105.7617       | 102.9102       | 6.50          | 0.99     | -0.0004125          | 0.00573728          |
| 8/15/2010 | 107.7109       | 105.2227       | 5.75          | 1.49     | 0.00577288          | 0.00612027          |
| 2/15/2011 | 108.5469       | 108.5469       | 5.00          | 1.99     | 0.00681706          | 0.00672485          |
| 8/15/2011 | 110.2891       | 110.2891       | 5.00          | 2.49     | 0.00820323          | 0.00813247          |
| 2/15/2012 | 110.7891       | 100.4609       | 4.88          | 2.99     | 0.0119855           | 0.01215572          |
| 8/15/2012 | 110.8828       | 110.8828       | 4.38          | 3.49     | 0.01165662          | 0.01160742          |
| 2/15/2013 | 109.9297       | 109.9297       | 3.88          | 3.99     | 0.01288277          | 0.01284569          |
| 8/15/2013 | 112.1875       | 112.1875       | 4.25          | 4.49     | 0.01401111          | 0.01397591          |
| 2/15/2014 | 111.7031       | 111.7031       | 4.00          | 4.99     | 0.01508872          | 0.01505964          |
| 8/15/2014 | 113.3750       | 113.3750       | 4.25          | 5.49     | 0.01632506          | 0.01629762          |
| 2/15/2015 | 150.4531       | 111.9219       | 11.25         | 5.99     | 0.02161538          | 0.01827873          |
| 8/15/2015 | 149.9375       | 113.2188       | 10.63         | 6.49     | 0.02188846          | 0.01995722          |
| 2/15/2016 | 142.7969       | 114.8906       | 9.25          | 6.99     | 0.02428518          | 0.02104869          |
| 8/15/2016 | 117.0938       | 117.0938       | 4.88          | 7.49     | 0.02242371          | 0.02271153          |
| 2/15/2017 | 115.5078       | 115.5078       | 4.63          | 7.99     | 0.02333984          | 0.0235906           |
| 8/15/2017 | 144.9766       | 116.8594       | 8.88          | 8.49     | 0.02674689          | 0.02384079          |
| 2/15/2018 | 107.6094       | 107.6094       | 3.50          | 8.99     | 0.02387718          | 0.02412073          |
| 8/15/2018 | 111.7031       | 111.7031       | 4.00          | 9.49     | 0.0239781           | 0.02423725          |
| 2/15/2019 | 149.6094       | 100.9063       | 8.88          | 9.99     | 0.02760558          | 0.02507135          |
| 8/15/2019 | 143.8594       | 143.8594       | 8.13          | 10.49    | 0.02861413          | 0.02925217          |
| 2/15/2020 | 147.7422       | 147.7422       | 8.50          | 10.99    | 0.02933139          | 0.02994457          |
| 8/15/2020 | 151.1719       | 151.1719       | 8.75          | 11.49    | 0.02933325          | 0.02990937          |
| 2/15/2021 | 143.5547       | 143.5547       | 7.88          | 11.99    | 0.03003364          | 0.03051389          |
| 8/15/2021 | 147.1250       | 147.1250       | 8.13          | 12.49    | 0.02968041          | 0.03013533          |

## 2. LEVERAGE INVERSE FLOATER PRICING

(PP) Describe the cash flows of the Leverage Inverse Floater provided in Term Sheet.

How can we decompose the Leverage Inverse Floater into simpler securities?
- The leveraged Inverse Floater can be decomposed into a long position in 2 zero-coupon bonds with a maturity at T=10 and one coupon bond with a fixed rate of 10% and a maturity at T=10,    in addition to a short position in 2 floating rate coupon bonds 
(PP) Discuss intuitively the benefits from investing in the Leverage Inverse Floaters as compared to an existing,    traded,    regular fixed rate note with the same maturity.
1. Higher yield: The LIF provides a higher yield due to the leverage factor and the inverse relationship with the reference interest rate.
2. Interest rate hedge: The LIF can act as a hedge against rising interest rates,    as its coupon payments increase when the reference interest rate decreases.
(CP) Use the results in Point 1 to compute the price of Leverage Inverse Floater described in the Term Sheet (which term structure do you use? Remember you have to come up with one price and not two. Explain your choice). 

## 3. DURATION AND CONVEXITY

(PP) Describe the **duration** of a fixed income security and how it is calculated in general. How is the duration of the Leverage Inverse Floater calculated? What are its components?

- The duration of a bond measures it's price sensitivity to changes in interest rates,    representing the weighted average time until a bond's cash flows are received.
- The Macaulay duration is defined as
$$D^{M c}=-\frac{(1+y/2)}{P}\frac{d P}{d y}$$
- Or equivalently,   
$$D^{M c}=\frac{1}{2}\sum_{j=1}^{n}w_{j}\times j$$
where
$$w_{j}=\frac{1}{P}\left(\frac{c/2}{\left(1+\frac{y}{2}\right)^{j}}\right),   \;w_{n}=\frac{1}{P}\left(\frac{c/2+100}{\left(1+\frac{y}{2}\right)^{n}}\right)$$

## MODIFIED DURATION

- The modified duration is instead defined as
$$M D=-\frac{1}{P}\frac{d P}{d y}$$
- Or equivalently,   
$$M D=\frac{D^{M c}}{\left(1+\frac{y}{2}\right)}$$
(CP) Calculate the duration of the Leverage Inverse Floater. Plot the value of the Leverage Inverse Floater against a hypothetical parallel shift in the term structure of interest rates.
 ![500](PSET%20II%20Fixed%20Income%20Asset%20Pricing-20240401212426843.png)