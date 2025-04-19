---
tags:
  - asset_pricing
  - bond_equivalent_yield
  - fixed_income
  - interest_rates
  - t_bill_rate
aliases:
  - 3-month T-bill rate
  - BEY
  - Homework 1
  - PSET 1
key_concepts:
  - Bond equivalent yield
  - Fixed income asset pricing
  - Historical interest rate data
  - Mean reversion of rates
  - Short term interest rates
---

# PSET I
# Fixed Income Asset Pricing Bus 35130 Spring 2024 John Heaton  
March 18, 2024

## Homework 1  
Due before 6 pm on Monday March 25 before 6 pm central time.  

You have been retained by the JCH Fixed Income Group to provide a forecast about future short term interest rates, namely, the 3 month t-bill rate. You decide to use two sources of data: historical interest rate data and current forward rates. The data necessary for this forecasting exercise are contained in the Excel file , which you can find on Canvas. This dataset contains daily observations of the 3 month t-bill rate from April 4, 1954 until March 14, 2024 (sheet “DTB 3”) as well as the Treasury Strip Price on March 08, 2024 (sheet “Strip Prices”). You are to write a report including all relevant information and computations, and provide a forecast for n horizons ranging between 6 months and 5 years. Please, follow the steps below.  

Note 1: For each section below, there are questions that require a “pencil and paper” $(P P)$ answer, and questions that require actual computations using data and computer programs $(C P)$ . You are supposed to do both. For the computer based questions you may used any software you like. There are guides however for Matlab, Excel and Python. You are, however, not required to use any of these pieces of code!  

Note 2: Some code you might use:  

For Matlab users, we made available the Matlab code “HW 1 2024 Guide. M”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example you will need to fill in some formulas and or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.  For Excel users, we made available the spreadsheet “HW 1 2024 Guide. Xlsm”. This Excel spreadsheet contains instructions to use the XLSTAT functions answer the CP questions below. Inputs though are required to complete some formulas or to produce some of the results. The Excel spreadsheet is supposed to facilitate the computations for the homework.  

For Python users, we made available the Python code “HW 1 2024 Guide. Py”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example you will need to fill in some formulas and or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.
## Estimation and Forecast  
1. Let us denote by $r_{t}$ the Bond Equivalent Yield (TN 1, page 22) on day $t$ .  

$(P P)$ Below are Treasury Bill quotes from the Wall Street Journal from a few years ago. Please, explain why the rates in “Ask” differ from those in “Asked Yield”. Use the quoted rates with maturity 6/11/2020 and 3/25/2021 to explain the point in detail (i.e. show that the “Ask” quotes indeed implies “Asked yield”.)  

$(C P)$ The data in ${\cal D}T{\cal B}\mathcal{B}_{-}\mathcal{Q}{\mathcal{Q}}\mathcal{\xi}_{+}X{\cal L}S$ are quoted on a discount basis $d_{t}$ . Please determine a time series of BEY and provide the appropriate plot (note that here $n=91$ ).  

2. The $A R(1)$ process for interest rates is the following:  

$$
r_{t+1}=\alpha+\beta r_{t}+\varepsilon_{t+1}
$$  

where $\varepsilon_{t+1}\sim N(0,\sigma^{2})$  

$(P P)$ Show OLS based formulas for determining $\hat{\alpha}$ , $\hat{\beta}$ and $\sigma$ .   
$(P P)$ Demonstrate why and how “mean reversion” of interest rates can be modeled with $A R(1)$ process.   
$(C P)$ Estimate the AR (1) process for interest rates.  

3. Let $\hat{\alpha}$ , $\hat{\beta}$ and $\sigma$ be the estimated parameters from (1). Use (1) together with the most recent interest rate available on $D T B\it{3.X L S}$ , call it rTODAY , to make a forecast of future interest rates ${\cal T}T O D A Y+T$ .  

$(P P)$ Carry the daily interest rate forecast for the following three days, i.e. calculate rTODAY +1 day, rTODAY +2 days, ..., rTODAY +3 days. Show all work, including all the  

Formulas used.  

$(C P)$ Forecast interest rates for horizons $T=6$ months, and $1,2,...,5$ years (a plot would suffice). Explain how you make the forecasts. (Tip: When you make the forecasts, assume there are 252 (business) days in one year).  

4. The Treasury Strip Prices are contained in DTB 3 2024. Xls.  

$(P P)$ Compute both the current yield curve and forward rates for the first three maturities. Show all work, including all the formulas used. Discuss what a “forward rate” is.   
$(C P)$ Compute both the current yield curve and forward rates for all maturities and compare the forecasts of future interest rates that are implicit in the forward rates to those obtained in point (3) above. Plot the forecasts and the corresponding forward rates. Discuss your findings.

```html
<html><body><table><tr><td>U.s.TreasuryQuotes</td><td></td><td>Monday, April 06,2020</td></tr><tr><td colspan="4">TreasuryNotes&Bonds|TreasuryBills</td></tr><tr><td>Treasury billbid and ask data are representative over-the-counter quotations as of 3 pm Eastern time quoted as a discount to face value. Treasury bill yields are to maturityandbasedontheaskedquote.</td><td></td><td></td><td></td></tr><tr><td>MATURITY</td><td>BID ASKED</td><td>CHG</td><td>ASKED YIELD</td></tr><tr><td>4/9/2020</td><td>0.018 0.008</td><td>-0.023</td><td>0.008</td></tr><tr><td>4/14/2020</td><td>0.043 0.033</td><td>unch.</td><td>0.033</td></tr><tr><td>4/16/2020</td><td>0.043 0.033</td><td>+0.035</td><td>0.033</td></tr><tr><td>4/21/2020</td><td>0.048 0.038</td><td>+0.008</td><td>0.038</td></tr><tr><td>4/23/2020</td><td>0.035</td><td>0.025 -0.010</td><td>0.025</td></tr><tr><td>4/28/2020</td><td>0.055</td><td>0.045 +0.010</td><td>0.046</td></tr><tr><td>4/30/2020</td><td>0.058</td><td>0.048 +0.013</td><td>0.048</td></tr><tr><td>5/5/2020</td><td>0.085</td><td>0.075 +0.003</td><td>0.076</td></tr><tr><td>5/7/2020</td><td>0.055</td><td>0.045 -0.003</td><td>0.046</td></tr><tr><td>5/12/2020</td><td>0.085</td><td>0.075 +0.013</td><td>0.076</td></tr><tr><td>5/14/2020</td><td>0.090</td><td>0.080 +0.023</td><td>0.081</td></tr><tr><td>5/19/2020</td><td>0.058</td><td>0.048 -0.015</td><td>0.048</td></tr><tr><td>5/21/2020</td><td>0.095</td><td>0.085 +0.038</td><td>0.086</td></tr><tr><td>5/26/2020</td><td>0.060</td><td>0.050 +0.013</td><td>0.051</td></tr><tr><td>5/28/2020</td><td>0.075</td><td>0.065 +0.003</td><td>0.066</td></tr><tr><td>6/2/2020</td><td>0.113</td><td>0.103 +0.015</td><td>0.104</td></tr><tr><td>6/4/2020</td><td>0.078</td><td>0.068 +0.018</td><td>0.069</td></tr><tr><td>6/11/2020</td><td>0.103</td><td>0.093 +0.023</td><td>0.094</td></tr><tr><td>6/18/2020</td><td>0.110</td><td>0.100 +0.025</td><td>0.102</td></tr><tr><td>6/25/2020</td><td>0.088</td><td>0.078 +0.030</td><td>0.079</td></tr><tr><td>7/2/2020</td><td>0.098</td><td>0.088 +0.013</td><td>0.089</td></tr><tr><td>7/9/2020</td><td>0.125</td><td>0.115 +0.030</td><td>0.117</td></tr><tr><td>7/16/2020</td><td>0.145</td><td>0.135 +0.038</td><td>0.137</td></tr><tr><td>7/23/2020</td><td>0.143</td><td>0.133 +0.025</td><td>0.135</td></tr><tr><td>7/30/2020</td><td>0.150</td><td>0.140 +0.020</td><td>0.142</td></tr><tr><td>8/6/2020</td><td>0.148</td><td>0.138 +0.030</td><td>0.140</td></tr><tr><td>8/13/2020</td><td>0.150</td><td>0.140 +0.038</td><td>0.142</td></tr><tr><td>8/20/2020</td><td>0.150</td><td>0.140 +0.023</td><td>0.142</td></tr><tr><td>8/27/2020</td><td>0.145</td><td>0.135 +0.025</td><td>0.137</td></tr><tr><td>9/3/2020</td><td>0.143</td><td>0.133 +0.025</td><td>0.134</td></tr><tr><td>9/10/2020</td><td>0.155</td><td>0.145 +0.020</td><td>0.148</td></tr><tr><td>9/17/2020</td><td>0.093</td><td>0.083 +0.007</td><td>0.084</td></tr><tr><td>9/24/2020</td><td>0.165</td><td>0.155 +0.018</td><td>0.157</td></tr><tr><td>10/1/2020</td><td>0.165</td><td>0.155 +0.018</td><td>0.157</td></tr><tr><td>10/8/2020</td><td>0.168</td><td>0.158 +0.015</td><td>0.160</td></tr><tr><td>11/5/2020</td><td>0.155</td><td>0.145 +0.035</td><td>0.148</td></tr><tr><td>12/3/2020</td><td>0.133</td><td>0.123 +0.013</td><td>0.125</td></tr><tr><td>12/31/2020</td><td>0.138</td><td>0.128 +0.008</td><td>0.130</td></tr><tr><td>1/28/2021</td><td>0.150</td><td>0.140 +0.030</td><td>0.143</td></tr><tr><td>2/25/2021</td><td>0.153</td><td>0.143 +0.018</td><td>0.145</td></tr><tr><td>3/25/2021</td><td>0.170</td><td>0.160 +0.020</td><td>0.163</td></tr></table></body></html>
```

Source: Tullett Prebon  

Source: Wall Street Journal Web Site https://www.wsj.com/market-data/bonds/treasuries
