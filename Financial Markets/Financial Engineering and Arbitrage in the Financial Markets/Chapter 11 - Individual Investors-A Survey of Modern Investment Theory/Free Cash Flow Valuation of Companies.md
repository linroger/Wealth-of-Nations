---
tags:
  - company_valuation
  - cost_of_equity
  - discounting
  - fcfe
  - fcff
  - free_cash_flow
aliases:
  - Company Valuation
  - FCF Valuation
  - Free Cash Flow
key_concepts:
  - Discount rate for equity
  - Dividends vs FCFE vs FCFF
  - Perpetual stock valuation
  - Present value of cash flows
  - Stock cash flow definitions
---

# 11.2  FREE CASH FLOW VALUATION OF COMPANIES  

The value of any security is equal to the present value of its cash flows. The value of the bond is the PV of the coupon annuity plus the PV of the principal. The value of the option is the PV of the contingent payout it might pay. The value of a real estate investment is the PV of the rent we may get minus expenses plus the PV of the future price we may sell for net of the initial price plus costs.  

The value' of the stock (company) is equal to the discounted value of its cash flows. But there are problems with this definition:.  

What are the cash flows for a stock? Dividends, earnings, cash position?   
How do we handle the perpetual nature of the stock, no principal and unending uneven cash flow? At what rate do we discount?   
Is there an extra value to the voting right?  

A good way to proceed is to draw a contrast to bonds. In bonds, the numerator variables are. known: coupons and face. In stocks, they are unknown (literally, they depend on the success of the company) and undefined (dividends? What if the company does not pay dividends, but. reinvests?). First, we solve the second problem. We have three potential definitions of the. numerator cash flows:  

Dividends paid to equity holders only.   
FCFE - Free cash flow to equity holders only.   
FCFF -- Free cash flow to the firm's claimants, both debt and equity.  

We will come back to the precise definitions of these. Each of these could grow, decline, or. go up and down, over time. To each of these variables, we attach a variable that describes their changing nature. For convenience, we assume geometric growth; so we will start with the best. estimate for the current year, denoted with the subscript 1, and then we assume a percentage. change per year, g. If the growth pattern is uneven, we can handle it by dividing the future into. life stages and discounting those separately. That is an easy problem.  

What about the perpetual nature of the stock? The company may last forever, or fold, or. be sold in a few years. How many cash flows are we going to get? No problem. Let's think. like a real estate investor. If I buy the apartment to hold for 5 years, I will get rent for 5 years. and then sell the apartment. Conditional on today's information about real estate, how much should I expect for the apartment in 5 years? The next investor will buy it from me, improve. it, and hold it for 7 years and then sell to the next one. In effect, when I buy today, I am buying. my cash flows, the next investor's cash flows, and the next's. Then in 5 years, I sell the PV of the rest of the cash flows to the next investor; then in 7 years, he sells the PV of the remaining. cash flows. It does not matter what holding horizon we assume, 5 years, 10, or perpetual. The discounting should produce the same value today equal to the PV of the cash flows to infinity.  

At what rate do we discount? That depends on what we discount. Dividends and FCFEs are paid to equity holders, so they should be discounted with the cost of equity. Dividends are paid only if the management declares them; FCFE is defined irrespective of that as the cash flow before any reinvestment/dividend decision. We will discount them at the same rate, in effect giving the right to vote a zero value. We will rely on the argument that the price per share is the same to the controlling and small stock holders, and the controlling ones act in the interest of all.  

FCFFs are paid to both debt and equity holders. They include interest paid on the debt, any. repayment of debt, dividend and any stock repurchases. They should be discounted by the WACC - the weighted-average cost of capital. If the company has preferred stock, we include. their cost in the WACC calculation..  

The cost of debt is relatively easy to figure out. Look up the yield currently paid by the company on all its outstanding debt. The interest rate the company pays has to do with the default-free level of interest rates (government curve) plus the default premium related to the company's credit standing. The total is relatively easy to observe. The concept of the cost of equity sounds a bit more nebulous, but need not be. It is equal to the cost of equity for the entire stock market plus the risk premium for our company based on its sensitivity to the systematic risk factors. We cover the details in the next section. The main thing we need to be conscious of at all times is the old Miller-Modigliani argument of no free tradeoffs of the leverage changes. The company could load up on relatively cheap short-term debt. Should we use a lower WACC rate to discount FCFFs? Miller and Modigliani say no. The increased leverage makes the cost of equity (and long-term debt) go up and the average cost stays the same, tax considerations excluded. So, before we proceed with the actual valuation techniques, the last word of caution is: beware of false precision. The cost of capital is an estimate. The numerator cash flows are estimates. Stock valuation is not a relative value, but an absolute value technique, therefore it involves:  

the voodoo art of predicting the future prospects of the company: $g$ the inexact accounting science of defining the cash flow, $D$ , FCFE or FCFF; the inexact science of modeling the cost of equity,. $r_{E}$ , and by extension WACC; and. the exact science of doing the discounting right..  

# 11.2.1 Free Cash Flow Definitions  

In order to understand deeply the cash flow definitions, we review the construction of the company's accounting statements. We focus primarily on the flow statements: the income statement (I/S) and the cash flow statement, also known as the "sources and uses"' statement. Even for a small or an upstart company, where we simply try to estimate future cash profits, it pays to run things through the accounting logic to make sure we don't miss any tax, accrual, or reinvestment variables. Let us take the perspective of a manufacturing or service company, not a financial one.  

Consider the I/S for ABC Corp for the ending fiscal year 2011 in Table 11.1. The top half of the I/S deals with ongoing operations. We subtract direct and indirect costs from sales revenue, then we subtract the depreciation allowance for the deteriorating production capacity. EBIT represents our first estimate of the health of our operations. Bear in mind that a lot of accrual thinking goes into the seemingly innocuous variables like revenue or costs. What do we do with a 5-year sales contract that combines manufactured product delivery with consulting services that is paid for over a 7-year period with partial money-back guarantee? The product took 3 years to develop. Accountants have capitalized some of the costs, expensed some others, and booked some revenue before it was actually received.  

Table 11.1 The income statement of ABC Corp. for 2011. Amounts in $\mathbb{S}$ millions   


<html><body><table><tr><td>Revenue</td><td>$10,000</td></tr><tr><td>-Costofgoods sold (CoGS)</td><td>-4,000</td></tr><tr><td>-Administrative andsellingexpenses</td><td>-1,000</td></tr><tr><td>Earningsbeforeinterest,taxesanddepreciation(EBITDA)</td><td>5,000</td></tr><tr><td>- Depreciation expense (DEP)</td><td>-1,000</td></tr><tr><td>Earnings before interest and taxes (EBIT)</td><td>4,000</td></tr><tr><td>-Interest expense (INT)</td><td>- 1,000</td></tr><tr><td>Earnings before taxes (EBT)=Taxable income</td><td>3,000</td></tr><tr><td>-Tax</td><td>-900</td></tr><tr><td>Netincome (NI)=Earnings</td><td>$2,100</td></tr></table></body></html>  

The bottom half of the I/S has to do with the financing and tax costs to non-equity claimants: interest expense and taxes; the latter computed independently according to cash accrual rules of the tax code. The net income number is a blend of some real and accrued revenues and expenses, a non-cash arbitrary depreciation allowance and some financing cost. Omitted financing cost includes any repayment of debt or new refinancing. There is no accounting for new investments on the I/S.  

The simplified sources and uses statement in Table 11.2 attempts to provide the missing. information. It takes a decidedly cash as opposed to accrual perspective. It is divided into three sections seeking to explain the cash from operations, investment and financing..  

The purpose of the first section is the same as of the top of the income statement, but on the cash basis. So we add back the unreal depreciation expense and make adjustments for shortterm trade financing we provided or enjoyed, financing for inventories and work-in-progress. In Table 11.2, the ABC Corp freed cash by liquidating $\$500$ worth of inventory or accounts. receivable, but it used cash to pay off additional $\$1,000$ of accounts payable perhaps because its suppliers tightened their payment terms. The combined increase in current assets minus the increase in current liabilities is called the change in the net working capital (NwC). For ABC, it is equal to. $+\$500$ for 2010.  

Table 11.2 The cash flow statement of ABC Corp for 2011. Amounts in $\$1$ millions   


<html><body><table><tr><td>Net income (NI)</td><td>$ 2,100</td></tr><tr><td>+ Depreciation expense (DEP)</td><td>+ 1,000</td></tr><tr><td>-Increasesin current assets</td><td>+500</td></tr><tr><td>+Increasesin currentliabilities</td><td>-1,000</td></tr><tr><td>Cash flow from operations</td><td></td></tr><tr><td>- Increases in gross fixed assets (CAPEX)</td><td>-1,000</td></tr><tr><td>-Investments</td><td>-500</td></tr><tr><td>Cashflowfrominvestments</td><td></td></tr><tr><td>+Increases inlong-term liabilities(△DEBT)</td><td>+ 1,000</td></tr><tr><td>-Dividends (D) Cash flow from financing</td><td>-700</td></tr><tr><td>Netcash</td><td>+ 300 $ 1,400</td></tr></table></body></html>  

The second section covers investments in capital (fixed) assets (CAPEX), or their disposal, and investments in other companies. ABC bought $\$1,000$ worth of new plant equipment and made a $\$500$ investment in a joint venture in China in 2011. The additions and subtractions in this section are made irrespective of how these purchases were financed. The CAPEX variable should in principle include only the maintenance portion and not new growth-oriented capital expenditures (often not separated out in the statements).  

The third section deals with long-term financing. Interest had already been subtracted to arrive at net income. Here we add new financing obtained or subtract any debt repaid. We also. subtract the dividends paid or stock repurchases. In 2011, ABC issued. $\$1,000$ of new lease bonds (to finance equipment?) and paid $\$700$ in dividends. The bottom line of the cash flow. statement corresponds to the change in the cash position reported on ABC's balance sheet for the end of 2011 relative to the beginning balance.  

The FCFF and FCFE definitions share the philosophy of the cash flow statement. For FCFF, we start with the net income number and make adjustments to it to arrive at the best estimate of the cash flow available to the debt and equity claimants from operations, after making operations-related investments decisions, and before we make any strategic growth-related reinvestment and financing decisions. For FCFE, we further adjust the estimate by taking into account changes in the company's long-term financing position. For FCFF, since we add back. interest, we make an adjustment for the lost tax shield (if we were to not incur interest, we would not save on the tax deduction).  

Here is the formal definition of the FCFF.  

$$
F C F F=E B I T(1-\tau)+D E P-C A P E X-N W C
$$  

Assuming the tax rate of $\tau=30\%$ , the FCFF for ABC for 2011 was:  

$$
F C F F_{0}=\mathbb{\S}2,800+1,000-1,000-500=\mathbb{\S}2,300
$$  

The formal definition of the FCFE contains the additional subtraction of long-term debtrelated expenditures, interest and principal changes, net of the tax shield.  

$$
\begin{array}{r}{F C F E=F C F F-I N T(1-\tau)+\Delta D E B T}\end{array}
$$  

The FCFE for ABC for 2011 was:  

$$
F C F E_{0}=\mathbb{\S}2,300-700+1,000=\mathbb{\S}2,600
$$  

Another way to get at the FCFE is to start with net income which nets the first terms of the two definitions, $E B I T$ and INT, and subtracts taxes. That is, we can also write:  

$$
F C F E=N I+D E P-C A P E X-\Delta N W C+\Delta D E B T
$$  

Plugging into the equation the amounts for 2011, we get:  

$$
F C F E_{0}=\mathbb{S}2,100+1,000-1,000-500+1,000=\mathbb{S}2,600
$$  

We have computed three cash flow variables for ABC for 2010:  

$D_{0}=\$700$ million $F C F E_{0}=\mathbb{S}2,600$ million $F C F F_{0}=\$2,300$ million  

We have denoted them all with the time subscript zero, since they all referred to the. currently ending accounting period. Note that the. $F C F E_{0}$ for 2011 exceeds the $F C F F_{0}$ due to the significant increase in the company's long-term debt, hardly a sustainable situation.  

Suppose we develop pro-forma income cash flow statements for 2012. We think that in the coming year, 2012, the capital expenditures (CAPEX) will drop to the long-term level of $\$500$ and the new issuance of debt (DEBT) will drop even further to the long-term annual refinance level of $\$300$ All the other variables will stay the same. The company will embark. on an ambitious growth plan, but will finance most of the growth with retained earnings. In 2012 ABC plans to raise the total dividends paid to shareholders to $\$750$ We are forecasting for 2012:  

$D_{1}=\mathbb{S}750$ million $F C F E_{1}=\mathbb{\mathbb{S}}2,400$ million $F C F F_{1}=\mathbb{\mathbb{S}}2,800$ million  

# 11.2.2 Growth and the Discounting of the Cash Flows  

We start with the discounting of the equity cash flows. As the next section will show, we can use the CAPM or a multifactor model to estimate the cost of equity for ABC by adding to the risk-free rate the risk premiums for the priced market factors. Suppose we use the CAPM with the inputs of the risk-free rate $r_{F}=3\%$ , the market $\beta=1.25$ , zero additional factor loadings, and the market risk premium $r_{M}-r_{F}=8\%$ . The equity cost of capital is:.  

$$
r_{E}=r_{F}+\beta(r_{M}-r_{F})=3\%+1.25\times8\%=13\%
$$  

We are projecting the long-term growth in FCFE to average $g=3\%$ per year. ABC has 200 million shares outstanding. Using the geometric growth assumption, the total value of the company's equity in $\$1$ millions is:  

$$
E Q_{0}={\frac{F C F E_{1}}{r_{E}-g}}={\frac{2,400}{0.13-0.03}}=24,000
$$  

The price per share is:  

$$
P_{0}=\mathbb{S}120
$$  

We can also approach the valuation from the dividend side. Here is how we may proceed. The company expects the total earnings for 2012 of $\$2,100$ million and will pay. $\$750$ million or $35.7\%$ out as dividends. Its earnings retention or plowback ratio can be defined as:.  

$$
b=64.3\%
$$  

It hopes to earn a long-term return on these retained earnings of $R O I=15.5\%$ . If that is the case, then it will be able to grow its dividend at an annual rate of:  

$$
g=b\times R O I=0.643\times15.5\%=9.964\%
$$  

The total value of the company's equity in $\$1$ millions is:.  

$$
E Q_{0}=\frac{D_{1}}{r_{E}-g}=\frac{750}{0.13-0.09964}=24,706
$$  

The price per share is:  

$$
P_{0}=\$123.53
$$  

We now turn to the slightly more complicated method of pricing the total enterprise value. of the company (market value of the assets as a going concern) by discounting FCFFs, and then subtracting the market value of the long-term debt to get the total value of the equity..  

After some research, we estimate that the total market value of the long-term debt is $\$12,500$ million, most of the debt is fairly recent and trades close to par, and the average. interest rate ABC pays on its long-term debt is about $r_{D}=8\%$ . This corresponds to the annual. interest expense of $\$1,000$ reported on the income statement. The average stock price over the. last three months has been. $\$125$ . The total equity value is about $\$125$ times 200 million or $\$25,000$ million. The company has no preferred. The company is financed with one-third debt. and two-thirds equity. We estimate the after-tax weighted-average cost of capital to be:  

$$
\begin{array}{l}{{W A C C=\displaystyle\frac{D E B T}{D E B T+E Q}\left(1-\tau\right)\times r_{D}+\displaystyle\frac{E Q}{D E B T+E Q}\times r_{E}}}\ {{W A C C=\displaystyle\frac{12,500}{12,500+25,000}\left(1-0.30\right)\times8\%+\displaystyle\frac{25,000}{12,500+25,000}\times13\%=10.53\%}}\end{array}
$$  

We estimate the long-term growth rate in FCFF to be $g=2.75\%$ . The total value of the firm's assets is:  

$$
V_{0}=\frac{F C F F_{1}}{W A C C-g}=\frac{2,800}{0.1053-0.0275}=35{,}989{.}72
$$  

Subtracting the value of the debt, we get the total value the company's equity in $\$1$ millions:  

$$
E Q_{0}=V_{0}-D E B T_{0}=35{,}989{.}72-12{,}500=23{,}489{.}72
$$  

The price per share is:  

$$
P_{0}=\$117.45
$$  

We got three different estimates of the fundamental price of the stock:. $\$120$ $\$123.53$ , and $\$117.45$ . If only we could ever get this close! Anyone involved in valuation is aware of the hours spent on reconciling accounting data, growth assumptions, and price estimates. Small. changes in the growth inputs produce vastly different price estimates. The income and cash. flow statements of real-life companies are never as easy to read as those of the ABC Corp. Usually they are full of extraordinary adjustments, negative earnings, one-time charges, and lots of confusing footnotes. However, giving up and simply pricing the company based on an. earnings multiple is not right, or is it?.  

Suppose we price the value of the equity as 10 times the earnings. We assume the fair P/E multiple to be 10. The earnings are $\$2,100$ . The total equity value is. $\$21,000$ million and the. per-share price of the stock is $\$105$ . Using a simple. $\mathrm{P/E}$ multiple implies using a no-growth perpetuity assumption. If we price the stock this way at $\$105$ and Mr. Market discounts is one day to. $\$85$ , wouldn't Benjamin Graham say that we have the required "margin of error" over the "intrinsic value"'? Private equity shops that routinely quote X-times-earnings (with X usually 4 or 6) must think so.  

# 11.2.3 Terminal Multiple Models of Cash Flow Discounting  

We end with a brief review of two-stage models that avoid the difficult task of guessing the sustainable growth rate $g$ . In the above discussion, $g$ was given. In reality, $g$ drives the results.  

In the preceding FCFE example, changing $g$ from $3\%$ to $4\%$ changes the stock price from $\$120$ to $\$133.34$ . That is a big difference.  

Suppose, as is common in investment banking, we are working on the pro-forma accounting statements for an acquisition/merger target. We use a percentage-of-revenue forecasting model with financing adjustments. We estimate next year's FCFE to be $F C F E_{1}=\$2,400$ million. We project the FCFEs for the following 2 years to be. $F C F E_{2}=\mathbb{\mathbb{S}}2{\mathrm{,}}520$ and $F C F E_{3}=\mathbb{\mathbb{S}}2{\mathrm{,615}}$ What we need is the estimate of the equity value in year 3. If we had that, we could use the following two-stage model:  

$$
E Q_{0}=\frac{F C F E_{1}}{1+r_{E}}+\frac{F C F E_{2}}{(1+r_{E})^{2}}+\frac{F C F E_{3}}{(1+r_{E})^{3}}+\frac{E Q_{3}}{(1+r_{E})^{3}}
$$  

The first three terms represent the discounted value of the cash flows that come out of our pro-forma projections. The last term represents the plug for the terminal value of the company. That terminal value represents what we think the company could trade at or be sold for 3 years from now. If we don't want to make a cash flow growth assumption beyond year 3, we can use the terminal value multiple approach. Two multiples are commonly used in investment banking. Both use the enterprise value as the numerator. The enterprise value, $E V$ , is defined as:  

$$
E V=E Q+D E B T+P R E F+M I N T-C A S H
$$  

where PREF is the value of the preferred, if any, MINT is the value of the minority interest, if any, and $C A S H$ is the amount of cash on the balance sheet. The two multiples are:.  

EV/REVENUE EV/EBITDA  

The latter comes with some modifications for different industries; the logic being that the denominator is supposed to be the purest measure of operating profit, free of future growth and distribution outlays, and related only to core operations. Instead of EBITDA, we may want to use EBITDAR. For pharma companies, the. $R$ may represent R&D (future growth investment); for airlines the. $R$ may represent airplane leasing revenue (side business). The. "correct' multiple may be taken from "precedent transactions".  

Suppose, for 2014 (3 years from now), we project the partial income statement in Table 11.3 We also estimate the DEBT to be $\$12,865$ million and $F C F E_{3}=\mathbb{\mathbb{S}}2{\mathrm{,615}}$ million.  

We estimate that in the last year similar companies' enterprise values were valued at 6 times the EBITDA. We use the multiple of 6 to estimate that  

$$
E V_{3}=E Q_{3}+D E B T_{3}-C A S H_{3}=6\times E B I T D A_{3}
$$  

Table 11.3 The pro-forma income statement of ABC Corp for 2014. Amounts in $\mathbb{S}$ millions   


<html><body><table><tr><td>Revenue</td><td>$ 11,600</td></tr><tr><td>-Costofgoodssold (CoGS)</td><td>-4,200</td></tr><tr><td>-Administrative andsellingexpenses</td><td>-1,000</td></tr><tr><td>Earnings before interest, taxes and depreciation (EBITDA)</td><td>6,400</td></tr><tr><td>-Depreciation expense (DEP)</td><td>-1,200</td></tr><tr><td>Earnings before interest and taxes (EBIT)</td><td>5,400</td></tr></table></body></html>  

Our assumptions are  

$$
C A S H_{3}=F C F E_{3}=\mathbb{\mathbb{S}}2615,D E B T_{3}=\mathbb{\mathbb{S}}12,865,E B I T D A_{3}=\mathbb{\mathbb{S}}6,400
$$  

therefore:  

$$
E Q_{3}=\mathbb{S}28,150
$$  

We plug into the two-stage model to get the total equity value:  

$$
E Q_{0}={\frac{2{,}400}{1{.}13}}+{\frac{2{,}520}{1{.}13^{2}}}+{\frac{2{,}615}{1{.}13^{3}}}+{\frac{28{,}150}{1{.}13^{3}}}={\mathbb{S}}25{,}419{.}11
$$  

and the price per share:  

$$
P_{0}=\mathbb{\mathbb{S}}127.10
$$  

We can repeat the exercise using the $E V/R E V E N U E$ multiple; we can repeat the exercise using the FCFF method with WACC; we can also dig deeper into the pro-forma projections.  
