---
linter-yaml-title-alias: FIXED INCOME ASSET PRICING BUS 35130 SPRING 2024 JOHN HEATON
title: PSET VI Fixed Income
tags:
  - bdt_model
  - bond_pricing
  - callable_bond
  - fixed_income
  - ho_lee_model
aliases:
  - Freddie Mac Bond
  - HW6
  - Homework 6
  - PSET VI
key_concepts:
  - Bond duration convexity
  - Callable bond valuation
  - Freddie Mac 6% bond
  - Ho-Lee interest rate
  - Nelson-Siegel model
  - Non-callable bond price
  - Simple BDT model
---

# PSET VI Fixed Income

## HOMEWORK 6

Due at the beginning of Class 8
Note As with past homeworks there are "guides" for doing the homework in Excel,  Matlab and Python. In each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.

## PRICING THE FREDDIE MAC 6% CALLABLE BOND

Attached below you will find the prospectus of Freddie Mac 6%,  20-year callable bond,  issued on June 7,  2007. Your task in this homework is to obtain its fair valuation,  using both the Ho-Lee model and the Simple BDT model. Proceed as follows:

1. (CP) Use the data in *"HW6 Data Bonds.xls"* and extract the discount curve $Z(0,          T)$ from the Treasuries using Nelson-Siegel model.

- Here are the discount curves and forward rates and 6 month Treasury yields plotted against time to maturity.
- ![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240508225148684.png)
- ![500](Z.%20Clippings/0PSET%206-20240508225138557.png)
1. (CP) Build the Ho-Lee tree,  given by

$$r_{i+1,         j}=r_{i,         j}+\theta(i)\times\Delta+\sigma\times\sqrt{\Delta}\times\epsilon_{i+1}$$

where $σ$ is the volatility of interest rates,  $θ(i)$ are chosen to fit the term structure of interest rates exactly,  and

$$\epsilon(i)=\left\{\begin{array}{l l}{{+1}}&{{\mathrm{with~probability}}}\\ {{-1}}&{{\mathrm{with~probability}}}\end{array}\right.\;\;1/2$$

Let $r_0$ match the first zero-coupon bond $Z_0(0.5)$ from Nelson Siegel model. The methodology to fit the model to the term structure of interest rates is explained in TN4. Both the matlab file and the guide spreadsheet that are available contain the routine to build it. You need a value of σ. Use the data on six-months rates available in the dataset (HW6 FRB H15*.csv*) to estimate σ (this can be done by taking the standard deviation of first differences in interest rates,  over six-month periods,  which is one time step). Remember to *annualize* the volatility estimates,  as $σ$ in Ho-Lee and BDT are annualized.

- The volatility of interest rates in the Ho-Lee model is given by $$\sigma^{HL}_{r_{t}}=st.dev(r_{t+1}-r_{{t}})$$

	This gives the monthly volatility of interest rates under the Ho-Lee model.

	- To annualize this volatility,  we multiply by $\sqrt{12}$,  such that annual volatility under the Ho-Lee model is $\sigma^{HL}_{r_{t}}\sqrt{12}$ =
	- The volatility of interest rates in the Simple Black Derman Toy model is given by $\sigma^{BDT}_{z_{t}}=st.dev(\ln(r_{{t+1}}-\ln(r_{t})))$
	- To find the annualized rate,  we multiply by $\sigma^{BDT}_{z_{t}} \times \sqrt{ 12 }$ =
1. (CP) After fitting the tree to the data,  please plot the zero-coupon bond yields from the tree and from the original zero-coupon bonds Z(T) obtained from Nelson and Siegel (and used as inputs for the tree). Are they the same? Show also the first 10 time-steps of the interest rate tree (table 10 x 10)
	1. The zero coupon bond yields derived from the Ho-Lee tree largely match those produced by the Nelson Siegel interpolation.
	1. ![500](Z.%20Clippings/ppings/Fixed%20Income%20PSET%206-20240509011443766.png)
1. (CP) Use the tree tree
ˆ Obtain the price of the non-callable bond
![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509205124687.png)
ˆ Obtain the price of
![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509205006803.png)
ˆ Obtain the price of the callable bond as the difference.
![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509205052239.png)
## PLEASE,  MAKE SURE TO INCORPORATE THE FACT THAT THE CALLABLE BOND BECOMES CALLABLE ONLY AFTER THE FIRST-CALL-DATE

(Matlab users: please see below for a generic algorithm to compute prices through backward calculation)

1. (CP) Show the first 10 nodes of the non-callable bond,  the option to call,  and the callable security.
1. (CP) Plot the price of the non-callable and of the callable security against interest rates at call time,  as well as 1,  2,  3 semesters before. How does the callable and non-callable bonds compare? Comment and discuss.

![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509230423297.png)

![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509230439162.png)

![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509230453676.png)

![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509230458912.png)

1. (CP) Compute the duration and convexity of callable and non-callable bond at time 0. Comment on the difference between the two securities.
1. (CP) **Ho Lee versus Simple BDT.** Redo all of the points above for the Simple BDT model (note: in both the matlab file and the spreadsheet,  this amounts to change BDT Flag from 0 to 1 and re-run the routine to build the tree. Everything else should be automatic,  except for the estimate of σ which now should use log differences in rates). Comment on the difference in price,  if any,  from the two methodologies.
- THe prices derived from the Ho-Lee model and the Black Derman Toy model should be the same,  because both models use the same zero discount curve as the input,  though the BDT model has a larger volatility.
![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233402903.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233401781.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233401063.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233400005.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233358725.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233357498.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233356378.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233354487.png)![500](Z.%20Clippings/Fixed%20Income%20PSET%206-20240509233351488.png)