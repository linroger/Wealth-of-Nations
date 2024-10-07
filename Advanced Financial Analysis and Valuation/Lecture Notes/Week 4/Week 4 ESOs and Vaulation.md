---
title: Week 4 ESOs and Vaulation
---
# Week 4 ESOs and Vaulation

Thomas Rauter

[Week 4 Valuing Young and High‐Growth Companies](Week%204%20Valuing%20Young%20and%20High‐Growth%20Companies.md)
[Options](Options.md)
[Options Financial Engineering](Options%20Financial%20Engineering.md)
[Options and Futures Pricing](Options%20and%20Futures%20Pricing.pdf)
[8. Options](8.%20Options.pdf)
[Binomial Tree Steps](Binomial%20Tree%20Steps.md)
[Binomial Option Pricing](Binomial%20Option%20Pricing.md)
[Binomial Trees and Option Pricing MBA](Binomial%20Trees%20and%20Option%20Pricing%20MBA.md)
[Lecture Note 4- Binomial Tree](Lecture%20Note%204-%20Binomial%20Tree)
[Option Pricing And Implied Volatility](Option%20Pricing%20And%20Implied%20Volatility.md)
[Notes on Basic Options Properties](Notes%20on%20Basic%20Options%20Properties.md)
[Teaching Note 7-Exotic Options And Derivative Pricing By Monte Carlo Simulation](Teaching%20Note%207-Exotic%20Options%20And%20Derivative%20Pricing%20By%20Monte%20Carlo%20Simulation.md)
[Teaching Note 5- Black Scholes Formula](Teaching%20Note%205-%20Black%20Scholes%20Formula.md)
[Lecture Notes 5-Black Scholes Equation](Lecture%20Notes%205-Black%20Scholes%20Equation)
[7. BlackScholesModel](7.%20BlackScholesModel.pdf)

## ADVANCED FINANCIAL ANALYSIS AND VALUATION OF GLOBAL FIRMS

## EQUITY COMPENSATION IN HIGH‐GROWTH COMPANIES

- ESOs align management interests with shareholders
	   - Options protect managers and employees on the downside
	   - Counteracts their risk aversion and rewards risk‐taking
- Young and high‐growth firms are often short on cash
	   - ESOs allow cash‐poor firms with growth prospects to compete for talent
- As a consequence, ESOs are highly used in high‐growth companies
- ![400](Week%204%20ESOs%20and%20Vaulation-20240503013907497.png)
- From a valuation perspective, compensation (or equity‐linked securities) are tricky
- Value of compensation (or securities) depends on the value of the stock that you are trying to estimate– creates circularity

## STOCK‐BASED COMPENSATION @ GOOGLE

- 25% of operating income and 8% of total expenses
- Including comp changes operating margin by 6%
![](Week%204%20ESOs%20and%20Vaulation-20240503013938092.png)

## EMPLOYEE STOCK OPTIONS
- Employee stock options, like warrants, conversion options on bonds, etc.
   - Give holders rights to purchase shares at prices possibly different from intrinsic value  or current price (often much below)
   - A transfer of wealth between existing and new shareholders
   - Clearly, such claims will impact a valuation, but estimating how much is difficult
	   - Exercise depends on future stock price
- Simple (and correct) approach is not available due to contingent nature
   - We need option pricing approach (e.g., Black‐Scholes model)
- If stock options are used by a firm to compensate employees, two issues need to be considered to avoid overvaluing common stock:
	   - Cash‐equivalent cost of future stock option grants
	   - Value of employee stock options outstanding on valuation date
- Valuation of future grants and outstanding options should be considered if the
firm is a heavy user of stock compensation

## BASIC ACCOUNTING RECAP FOR STOCK COMPENSATION

- In 2004, the FASB issued SFAS No. 123R, which requires firms to treat the fair value of granted options as compensation expense, with the expense taken over vesting period
- To expense the cost of an option, the firm must determine the option's value
	   - Value typically determined using an option pricing model (e.g., Black‐Scholes)
	   - Should adjust model to reflect vesting requirements and the fact that ESOs are generally  not transferable 
- Accounting for ESOs hinges on the grant date, vesting period, and exercise date
	   - Grant date: Value of the grant is measured but expense is not recorded immediately
	   - Vesting period: Compensation expense is recorded over the vesting period
		   - Reduces earnings | increases paid‐in capital from options
  - Exercise Date
	   - Upon exercise, firm receives cash for the exercise price and issues shares
	   - Records cash and paid‐in capital from common stock | removes paid-in capital from options

## BASIC ACCOUNTING RECAP FOR STOCK COMPENSATION (CONT.)

- Example: Suppose Firm A grants **10MM ESOs** with an **exercise price of $50** on 12/31/2005 when Firm A's stock price was $50. On that date, Firm A uses an option pricing model to determine the **fair value of these ESOs at $30 each**. The ESOs fully vest in **4 years**. All the ESOs are exercised on 12/31/2011; Firm A's stock price was $120 at that time.
![](Week%204%20ESOs%20and%20Vaulation-20240503014131264.png)

## BOTH FUTURE AND PAST GRANTS ARE RELEVANT

![](Week%204%20ESOs%20and%20Vaulation-20240503014212124.png)

## DEALING WITH FUTURE GRANTS
- Cash‐equivalent cost of future stock option grants :
	- Compensation expense associated with stock option grants (and other equity based pay) is usually buried within SGA and/or CGS
	   - Stock option expense is added back in cash flow statement as a non‐cash expense, analogous to add‐back for depreciation in computation of  FCF
- But you should treat the stock compensation expense 'as if' it were a cash expense in the computation of future FCF
	   - Accounts for share value that will be handed over to employees in the future
- In essence, you use past stock compensation expense as a proxy for future stock compensation and include it in the FCF as a cash‐equivalent
	   - Do not add it back to FCF!
 - What Do Many Analysts Do?
	   - Treat is as a non‐cash expense and add it back (wrong)
	   - Divide by fully‐diluted shares (only relevant for existing options)

## EXAMPLE: YELP INC. – INCORRECT

![](20and%20Vaulation-20240503014542156.png)

- Other Non‐Cash Charges (Benefits) exactly
match the Credit Suisse estimates for stockbased compensation (Figure 13 in the report)
- This clearly overstates the FCF (by a substantial
amount)

## EXAMPLE: FACEBOOK – CORRECT

![](Week%204%20ESOs%20and%20Vaulation-20240503014550055.png)
Here, the analyst added stock‐based compensation in the calculation of Adjusted EBITDA but subtracted it again in the calculation of FCF for valuation

## DEALING WITH PAST GRANTS

- Value of employee stock options outstanding on valuation date:
	   - Need to be valued separately
	   - Again, this is different from the value of future grants
	   - Here, we account for the value that has already been given to managers
- Fair value of vested outstanding employee options and the portion of unvested options that are expected to vest (i.e., not be forfeited due to turnover), net of tax corporate benefits, should be subtracted from enterprise value
- Use an option valuation model
	   - Use Black‐Scholes to estimate value of outstanding options as of valuation date
	   - Black‐Scholes assumptions are typically disclosed in the footnotes
	   - See Canvas for Excel sheet to do the valuation

## ESO – INCORRECT BUT RELATIVELY EASY APPROACH
- Exercise value approach  (to value options outstanding)
   - Assume in‐the‐money outstanding that are vested options were to be exercised immediately
- Add total proceeds from such an exercise to enterprise value (plus tax benefits of tax deduction for amounts employees will report in income)
	   - Divide total estimated equity value by
		   - (# shares actually outstanding + # shares issued from assumed exercise)
	   - See Exhibit 14.5 in Koller et al. (p. 333)
- Understates true value of options outstanding because:
	   - Ignores unvested outstanding options that are expected to vest in future
	   - Ignores time value of options (options may go further in money between now  and maturity), so options are worth more than 'intrinsic value'
		   - This could be a reasonable approach if the valuation is for a firm to be acquired
		   - After acquisition, all in‐the‐money outstanding options are typically exercised immediately

## ESO VALUATION: EXAMPLE

![](Week%204%20ESOs%20and%20Vaulation-20240503014713501.png)

- At fiscal year end, Microsoft's (current) stock price was $80
- Thus, Microsoft had a large number of "in the money" ESOs (outstanding and exercisable)
- Exercisable = vested

## ESO VALUATION: EXERCISE VALUE APPROACH I

![](Week%204%20ESOs%20and%20Vaulation-20240503014728408.png)

- Even considering only exercisable (i.e., vested) options and ignoring potential stock price
increases, the overhang (or option value) is significant

## ESO VALUATION: EXERCISE VALUE APPROACH II

![](Week%204%20ESOs%20and%20Vaulation-20240503014744317.png)

- Considering all outstanding options causes the overhang to grow considerably
 - Note this approach still ignores potential stock price increases
- Need proper option valuation approach

## ESO VALUATION: BLACK‐SCHOLES APPROACH

![](Week%204%20ESOs%20and%20Vaulation-20240503014801782.png)

- Value of the options computed from Black‐Scholes model using assumptions given
	   - See spreadsheet on Canvas
	   - Appendix in the back of this slide deck
- Note: The values here are not yet adjusted for forfeiture, warrant conversion, and taxes
	   - See stock option tutorial on Canvas

## ESO TAX BENEFITS

![](Week%204%20ESOs%20and%20Vaulation-20240503014829574.png)

- The tax benefit highlighted in yellow is what you divide by the value of the options exercised (i.e., tax deduction) to obtain TESO
	   - In 2000: 5535/15814 = 35%
- Note: Stock option tutorial on Canvas uses 35%, but you can change it to current rate or firm‐specific rate

## SUMMARY FOR ESO TREATMENT
 - Computation Of Equity Value Is Reduced By Both:
 1. Cash Equivalent Cost (Net Of Tax) Of Future Option Grants:
	   - Incorporated into calculation of future free cash flows
	   - Tax benefits need to be captured like tax benefits of interest
 2. Value Of Outstanding Stock Options, Net Of Tax Benefit
	   - Value of outstanding options  * (1 – TESO)    
- Calculation includes vested options and portion of unvested outstanding options that are expected to vest
	   - Note: This already incorporates future tax benefits of exercising currently outstanding options, so we can ignore calculating these future tax benefits when calculating future free cash flows
	   - Technically, you have to use your equity valuation and not the market value, which creates circularity
		   - Effect is small unless your valuation is far from market value

## RESTRICTED STOCK UNITS
- A restricted stock unit is a promise to issue a share of stock to an employee, usually at no cost to the employee, upon completion of a vesting period
	   - They have become much more popular since the introduction of stock option expensing under FAS 123R
- The accounting for restricted stock unit is essentially the same as for ESOs
	   - Value of the RSU is expensed over the vesting period
	   - Firm receives income tax deduction when RSU vests (for fair value at vesting date)
- The valuation implications are also similar as ESOs
	   - We need to consider future grants in the FCFs (exactly like ESOs)
	   - We need to value and subtract the value of already granted RSUs

	   - $$EQUITY\quad PER\quad SHARE=\frac{V}{S+n(1-\tau)}$$
  
		   - V  = combined value of common equity and RSUs (which is equal to core operations plus  non‐operating assets less all other capital claims)  
		   - n = number of RSUs outstanding at the valuation date  
		   - $\tau$ = marginal income tax rate  
		   - S =  number of shares outstanding at the valuation date 

## APPENDIX DETAILS ON BLACK‐SCHOLES MODEL

- Value of call options without dividends:
![300](Week%204%20ESOs%20and%20Vaulation-20240503015155745.png)

- Value of call options with dividends:
- Note:  Can adjust the Black‐Scholes
value for dilution effect by multiplying the balance sheet value by the socalled warrant conversion factor:

## TAX BENEFITS FROM ESOS

- Stock options can provide tax benefits to the company (upon exercise)
- Calculate Enterprise Value – ((Estimated net value of options) x (1‐$t_{ESO}$))
		   - Question:  What is $t_{ESO}$?
		   - Tax rate at which firm receives tax benefits from options
		   - Depends on firm's tax position and the mix of qualified vs. nonqualified options
		   - $t_{ESO}$ varies between 0 and marginal tax rate, depending on mix of options
![](Week%204%20ESOs%20and%20Vaulation-20240503015322174.png)