---
tags:
  - cost_of_capital
  - financial_statement_analysis
  - lecture_notes
  - security_analysis
  - valuation
aliases:
  - Financial Analysis
  - Security Analysis
  - Valuation Lectures
key_concepts:
  - Cost of capital and security
  - Discounted cash flow models
  - Financial statement analysis
  - Lecture notes on valuation
  - Residual income models
  - Valuation and Security Analysis
---

# Lectures on Valuation and Security Analysis

# Abstract

This document contains my lecture notes on Valuation and Security Analysis developed over 25 years while teaching at Cornell, University of Chicago, and Northwestern University. There are twelve lecture notes in this document covering cash flows, valuation, cost of capital, and security analysis. Additional teaching material including EXCEL valuation templates are available for download at my personal website: www.sharingfin.com. All of these are provided as is for anyone to use. They could be useful for teaching Valuation, Security Analysis, and Financial Statement Analysis.

# Preface

This document contains my lecture notes on Valuation and Security Analysis developed over 25 years while teaching at Cornell University, University of Chicago, and Northwestern University. There are twelve lecture notes covering valuation, cost of capital, and security analysis. When I started teaching valuation at Cornell in the spring of 1995, there wasn't any one book on valuation that covered the topics I wanted to cover. I decided then to prepare my own lecture notes by culling material from different sources including from the MBA and PhD courses I took during my PhD days at UCLA. I have included a bibliography (by no means exhaustive) of all the material I consulted over the years in preparing the lecture notes. As my knowledge, understanding, and thinking about these issues evolved over time, I started including original material in my lectures which ultimately led to me writing several academic papers on valuation, implied cost of capital, and security analysis. I owe a lot of gratitude to my students whose incisive and insightful questions inspired me to find answers. I have learnt a lot from them.

The one book that led to my interest in academic finance was Financial Theory and Corporate Policy (Second Edition) by Tom Copeland and Fred Weston. I learnt more about finance from this brilliant book than any other book on finance I have ever read. This book was introduced to me by Professor Tom Cook during an independent study I conducted with him in the spring of 1989 when I was a MBA student at the University of Denver. My thinking on valuation and discounted cash flow models was heavily influenced by the ideas in this book. Tom Copeland took these ideas with him to McKinsey and ultimately made them a part of the Valuation text book he authored with his colleagues at McKinsey. I have used these books extensively in my classes over the years.

The one person who had the most profound influence on my teaching and research career is my dear friend Charles Lee who is now at the University of Washington, Seattle. Charles came to Cornell in 1996 after a stint at the NYSE. I was already teaching valuation at Cornell but his arrival and our collaboration and friendship significantly changed (for the better) how I approached Valuation and Security Analysis. Charles is a brilliant teacher and I learned much from him. He introduced me to Residual Income Models and the symbiotic relationship between Capital Market Accounting and Finance. This led me to undertake a major revision of my teaching material to incorporate these ideas and to let the students taking our classes at Cornell see the connections. I became a better teacher because of him. We went on to co-author several papers based on our discussions of these ideas.

In addition to Valuation and Security Analysis, I have also taught Portfolio Management and Investments at both Cornell and the University of Chicago. Much of the material I developed for teaching these courses, especially on the portfolio management side, was inspired by a MBA course on portfolio theory taught by Michael Brennan which I audited when I was at UCLA. Michael would then become my PhD advisor and was instrumental in shaping my career. I intend to share these lecture notes soon. The book I have found the most useful in teaching portfolio theory and one I still refer to is Modern Portfolio Theory and Investment Analysis (Third Edition) by Edwin Elton and Martin Gruber. This is an outstanding text book.

The person who inspired me to undertake this project of putting together my lecture notes and releasing them to the public is Ravi Jagannathan of Northwestern University. A brilliant academic, Ravi is also a personal friend and a great mentor. I have learned much from him over the years discussing and debating various issues in finance. He reviewed my lecture notes, found them valuable and felt it would be useful to the profession at large. Many thanks to him for motivating me to do this.

In addition to these lectures on Valuation and Security Analysis, I have also covered advanced valuation topics covering international valuation and capital budgeting, and real options in a separate course at Cornell. I hope to make this teaching material available soon.

I am making all of this material as well as any future teaching material available on my personal website: www.sharingfin.com. The website contains this PDF file as well as the underlying Word documents so anyone can take the material and update them. I am also providing on my website, a copy of a syllabus from the last time I taught this course (in 2015) to provide a road map of how this material could be used in teaching. Finally, I am providing on my website, an EXCEL Valuation template that is an important part of the course material. It has several valuation models, and spread sheets for computing free cash flows, economic profits, and cost of capital for the publicly traded company, Smucker's (Ticker: SJM). This is a necessary template that students use to perform many of the valuation exercises for the class. They typically adapt this template for a company of their choice to perform similar analysis.

I think I learned more about finance from the MBA courses taught by my professors than from the PhD courses taught by them. I think it may be because we become better communicators when we have to explain ideas and concepts to those who are seeing them for the first time. I have certainly become a better student of finance as a result of my years of teaching. From that perspective, my students are my best teachers. Thank you to all of you, wherever you are. I hope this material is useful to all.

# Lectures on Valuation and Security Analysis

# Table of Contents

Lecture Note 1 - Discounted Cash Flow Valuation: Computing Free CashFlows

Lecture Note 2 - Computing Cost of Capital: Cost of Equity, Cost of Preferred Stock and Cost of Debt

Lecture Note 3 - Discounted Cash Flow Valuation: Value Drivers and Implementing the Free Cash Flow Model

Lecture Note 4 - Discounted Cash Flow Valuation: EVA and Discounted EVA Models

Lecture Note 5 - Valuation by Multiples

Lecture Note 6 - Computing Cost of Capital: Financial Leverage and Cost of Capital

Lecture Note 7 - Firm Valuation: Projecting Pro-Forma Financial Statements

Lecture Note 8 - Firm Valuation: Valuing Mergers, Acquisitions & Multi-Business Firms

Lecture Note 9 - Security Analysis and Investor Behavior

Lecture Note 10 - Value and Momentum

Lecture Note 11 - Accruals, Asset Growth and External Financing

Lecture Note 12 - Quality and Stock Returns

# Lecture Note 1 Discounted Cash Flow Valuation: Computing Free Cash Flows

# Objective

Introduce students to the mechanics of computing free cash flows.

# Outline of the lecture

· Define value of firm, equity, debt, and preferred stock
Define free cash flows to firm (FCFF), free cash flows to equity (FCFE), free cash flows to debt (FCFD), and free cash flows to preferred stock (FCFP)
· Invested Capital - Asset base generating free cash flows to firm and the rearranged balance sheet
· Non-operating assets - Excess cash & marketable securities
· J M Smucker (SJM) Financial Statements Computing capital expenditures, depreciation & amortization, change in working capital, taxes on EBIT, and effective tax rate
· Deferred taxes Rearranged balance sheet with deferred taxes and goodwill; compute invested capital
· Investments in other companies
· Special Items
·Long-term operating liabilities

# A General Discounted Cash Flow (DCF) Model

The intrinsic value of an asset, V, is the present value of all its expected future free cash flows (FCF):

$$
V=\sum_{t=1}^{\infty}{\frac{E{\bigl(}F C F_{t}{\bigr)}}{(1+r)^{t}}}
$$

E (FCF) = The forecasted free cash flows from the asset over its life. R An appropriate risk-adjusted cost of capital.

· Free cash flows refer to cash flows that are available to the owner of the asset after meeting all obligations.
· The convention is to focus on cash flows after corporate taxes but before any personal taxes.
· We focus first on the numerator and discuss how to compute free cash flows.
· Later, we turn to the denominator and discuss how to compute cost of capital.

# Valuing a Firm

By definition, the value of a firm is the sum of the value of debt, preferred stock, and equity:

$$
\mathrm{Firm~Value}\equiv D+P+E
$$

D is the value of all interest bearing liabilities, $\mathrm{P}$ is the value of preferred stock, and E is the value of common stock. 1

Total Enterprise Value (V) represents the value of the operating assets of the firm.

More generally, we can value an N-asset firm by summing the values of all its N assets (the assets can be both operating and non-operating).

Firm Value $=$ V (asset 1) + V (asset 2) +...+ V (asset N).

This is called the value-additivity principle.

The firm can also be valued from the liability side (right hand side) of the balance sheet by valuing each financial claim: $\mathrm{D}+\mathrm{P}$ $+\textrm{E}$

# Defining value of firm, debt, preferred stock, and equity

· The total enterprise (operating) value of a firm, V, is the PV of the free (operating) cash flows to firm (FCFF) discounted at the weighted average cost of capital (WACC). The value of debt is the PV of the cash flows to debt discounted at the cost of debt $\left(\mathrm{r_{d}}\right)$
· The value of preferred stock is the PV of the cash flows to preferred stock at the cost of preferred stock $\left(\mathrm{r_{p}}\right)$ The value of equity is the PV of the free cash flows to equity (FCFE) discounted at the cost of equity $\left(\mathrm{r_{e}}\right)$

<html><body><table><tr><td>Valuation</td><td>Cash Flows</td><td>Discount rate</td></tr><tr><td>(1) Enterprise value of the firm</td><td>Free cash flows to firm, FCFF</td><td>Weighted average cost of capital (WACC)</td></tr><tr><td>(2) Debt</td><td>Cash flows to debt, FCFD</td><td>Cost of Debt, rd</td></tr><tr><td>(3) Preferred stock</td><td>Cash flows to preferred stock,</td><td>Cost of Preferred Stock, rp</td></tr><tr><td>(4) Common Stock</td><td>FCFP Free cash flows to equity, FCFE</td><td>Cost of Equity, re</td></tr></table></body></html>

# Free cash flows to firm

Total operating cash flows available after meeting all operating expenses, taxes, capital expenditures, and investments in working capital but before any interest and debt principal repayments, and preferred dividends and repayments.

# Free cash flows to debt

This represents the sum of interest payments and net principal repayments (if any) each period.

# Free cash flows to preferred stock

This represents the sum of preferred dividends and any net retirement of preferred stock.

# Free cash flows to equity

This is the residual cash flow available to common equity after meeting all operating expenses, interest expenses, taxes, capital expenditures, working capital requirements, net debt repayments, and preferred dividends and repayments.

# Determining free cash flows

Consider a simple income statement and balance sheet:

<html><body><table><tr><td>The Income Statement Sales</td></tr><tr><td>- Cost of Goods Sold -- Selling, general, and administrative expenses - Depreciation and Amortization Expenses = Earnings Before Interest and Taxes (EBIT) = Net Income Before Extraordinary Items</td></tr><tr><td>= Earnings Before Taxes (EBT)</td></tr><tr><td>- Interest Expense</td></tr><tr><td>- Taxes</td></tr></table></body></html>
<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Current operating assets (accounts receivable, operating cash, inventories)</td><td>Current (non-interest-bearing) operating liabilities (accounts payable, salaries payable, etc.)</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment)</td><td>Short-term debt (notes payable, floating rate debt, currently maturing long-term debt)</td></tr><tr><td>Other long-term operating Assets</td><td>Long-term debt (long-term bonds, bank loans) Preferred Stock</td></tr><tr><td>Total Assets</td><td>Common Stock Equity + Total Liabilities</td></tr></table></body></html>

# Free Cash Flows to the Firm (FCFF)

From the simple balance sheet and income statement:

<html><body><table><tr><td>Free cash flows to the Firm - Top down Earnings Before Interest and Taxes (EBIT)</td></tr><tr><td>= Net Operating Profits After Taxes (NOPAT)* + Depreciation and amortization & other non-cash expenses** - Capital Expenditures*** - Change in Working Capital (Change in current operating assets - Change in current operating liabilities) = Free Cash flows to the Firm</td></tr><tr><td>Free cash flows to the Firm -- Bottom Up</td></tr><tr><td>+ Net Income Before Extraordinary Items + After-tax interest expense = Net Operating Profits After Taxes (NOPAT)* + Depreciation and Amortization & other non-cash expenses** - Capital Expenditures*** - Change in Working Capital (Change in current operating</td></tr><tr><td>assets - Change in current operating liabilities) = Free Cash Flows to the Firm Net Income = (EBIT - Interest Expense)*(1 - Tax Rate)</td></tr><tr><td>Net Income + Interest Expense*(1 - Tax Rate) = EBIT*(1 - Tax Rat Net Income + Interest Expense*(1 - Tax Rate) = NOPAT (Note that Interest Expense* Tax Rate is the Interest Tax Shield) *Textbook refers to NOPAT as NOPLAT. ** Net of any non-cash income ***Capital expenditures also include acquisitions.</td></tr></table></body></html>
# Asset base generating the free cash flows to the firm

Rearrange the items on the simple balance sheet on page 7 by subtracting current operating liabilities from both sides of the balancesheet.

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Net Operating Working Capital (Current operating assets - Current operating liabilities) +</td><td>Short-term debt (floating rate debt, currently maturing long- term debt) +</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment)</td><td>Long-term debt (long-term bonds, bank loans) +</td></tr><tr><td>Other long-term operating assets</td><td>Preferred Stock +</td></tr><tr><td></td><td>Common Stock +</td></tr><tr><td>= Invested Capital</td><td>= Total Investor Funds</td></tr></table></body></html>

Invested capital represents the operating assets employed in the operations of the business, which generate NOPAT and the free cash flows to the firm (FCFF).

The cost of financing through non-interest bearing liabilities like accounts payable is included in the cost of goods sold. How?
# Define gross value to include the value of non-interest bearing liabilities

Gross value $=$ Value of current operating liabilities + Value of short-term debt $+$ Value of long-term debt $+$ Value of preferred stock $+$ Value of equity

Subtract non-interest bearing liabilities from both sides

Value (as we define it) $=$ Gross value - Value of (non-interest bearing) current operating liabilities

$=$ Value of short-term debt $+$ Value of long-term debt $+$ Value of preferred stock $+$ Value of equity

We implicitly subtract the value of non-interest bearing current operating liabilities from gross value by subtracting their costs through the cost of goods sold in computing free cash flows.

Invested Capital $=$ Book value of short-term debt + Book value of long-term debt $+$ Book value of preferred stock $+$ Book value of equity

We will consider excess cash, minority interest, deferred taxes, good will, special items and other long-term liabilities soon.
# Free Cash Flows to Equity (FCFE)

Free cash flows to equity represent the residual cash flows to common stockholders after all senior claimants (debt, preferred stock) are paid off.

<html><body><table><tr><td>Free Cash Flows to Equity</td></tr><tr><td>+ Net Income Before Extraordinary Items + Depreciation and Amortization & non-cash expenses</td></tr><tr><td>- Capital Expenditures - Change in Working Capital (Change in current operating</td></tr><tr><td></td></tr><tr><td></td></tr><tr><td>assets - Change in current operating liabilities)</td></tr><tr><td>- Net Payments of Debt Principal</td></tr><tr><td>- Preferred Dividends & repayments</td></tr></table></body></html>

FCFE represents the source of funds to equity. It can be distributed through dividends, stock repurchases, and can also be parked in short-term or long-term marketable securities to preserve financial slack.
· Free cash flows to equity represent capacity to payout while dividends and stock repurchases represent actual payout.
· From the statement of cash flows: FCFE $=$ Cash flow from operations $+$ Cash flow from investing $+$ Cash flow from non-equity financing.

# What if there is no preferred stock?

Then, simply set preferred dividends and repayments equal to zero in our discussion earlier.

# What if there is no interest-bearing debt?

Then, set interest expenses and net debt payments to zero.

In this case, the firm is reduced to what is referred to as an allequity firm, i.e., a firm financed fully by equity.

For an all-equity firm, also referred to as an unlevered firm:

FCFF = FCFE - After-tax interest and non-operating income

(We are yet to introduce non-operating income directly in our discussion).

# Free Cash Flows to Debt (FCFD)

Interest Expense $+$ Net Debt Repayments (net of any new debt issues)

# Free Cash Flows to Preferred Stock (FCFP)

Preferred Dividends $+$ Any Retirement of Preferred Stock
# Non-Operating Assets

The definition of free cash flow to the firm (FCFF) includes only cash flows from operations.
· It excludes interest income and any other non-operating income.
· How do we deal with non-operating assets such as excess cash, discontinued operations, etc? The answer is easy given the value additivity principle.
Value of a firm is a sum of the values of its individual assets (divisions, lines of business, operating and non-operating assets).

#
# Excess Cash & Marketable Securities

Consider a firm that has significant excess cash in hand in addition to capital invested in its operations.

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess cash</td><td>Short-term debt (floating rate debt, currently maturing long- term debt)</td></tr><tr><td>Invested Capital</td><td>Long-term debt (long-term bonds, bank loans)</td></tr><tr><td>Net Operating Working Capital (Current operating assets - Current operating liabilities)</td><td>Preferred Stock</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment) + Other long-term operating assets</td><td>Common Stock</td></tr><tr><td>Total Capital</td><td>Total Investor Funds</td></tr></table></body></html>

As a thumb rule, depending on the industry, persistent cash balanceover $2\%$ of sales could be considered excess cash not directly related to operations. For practical purposes, however, items such as cash $\&$ marketable securities, and other shortterm liquid investments may all be treated as excess cash.

Based on value additivity:

Total Firm Value $=$ Total Enterprise Value $+$ Excess cash.
# Value of Excess Cash

Value of excess cash is simply assumed to be equal to its book value from the balance sheet. Why?

# Effect of Excess Cash on the Income Statement

Excess cash earns interest income, which appears after interest expense as either interest income or non-operating income.

# Other non-operating assets

Investments in long-term bonds and equities of unrelated companies may constitute other non-operating assets.

We can compute their value by discounting any expected future cash flow from these assets or simply take their market value if available or book value as a last resort.

However, be very careful in denoting any asset as a nonoperating asset, especially, those that seem to have recurring cash flows.

These items will appear under "Other long-term assets" and can be identified only by looking at a firm's footnotes.

For brevity, I will simply use the term “Excess Cash" to refer to all of excess cash and non-operating assets.
# Smucker Financial Statements for fiscal year 2014 (see Smucker-July 2015 version 7.0. Xls and 10-K report)

J.M.SMUCKER (SJM) - INCOME STATEMENT

Millions - Detail U.S. Dollars 2014

NET SALES 5,692.7
Cost of Goods Sold (includes dep&amort) 3,781.7
GROSS PROFIT 1,911.0
Selling, General and Admin Expenses 1,031.3
Other Operating Expenses (2.1)

# OPERATING INCOME AFTER Dep & Amort. (EBIT)

Interest Expense
Non-Operating Income and Special Items (Expense)\* Non-Operating Income (Expense) Special Items (Expense)

# PRETAX INCOME

881.8 79.9
(278.9) 4.2
(283.1) 523.0 178.1
$34.1\%$ 0.0 344.9
Total Income Taxes
Effective Tax Rate $(\%)$ (total income taxes/pre-tax income)
Less: Minority Interest

NET INCOME before extraordinary items

Extraordinary Items & Discontinued Operations NET INCOME after extraordinary items

0.0
344.9

\* Includes interest income as well as special items.

Special items are what CapIQ calls as unusual items.

# J.M.SMUCKER - BALANCE SHEET

#
# Millions - Detail U.S. Dollars

# ASSETS

Cash
Net Receivables
Inventories
Other Current Assets\*
CURRENT ASSETS
Gross Property, Plant & Equipment
Less: Accumulated Depreciation
Net Property, Plant & Equipment

125.6
430.1
1,163.6
333.0
2,052.3
2,699.1
1,020.8
1,678.3
Good Will & Other Intangibles 12,960.1
Other Long-Term Assets 191.9
TOTALASSETS 16,882.6

# LIABILITIES AND EQUITY

Short-Term Debt 226.0
Accounts Payable 402.8
Income Taxes Payable 0.0
Other Current Liabilities 393.8
CURRENTLIABILITIES 1,022.6
Long-Term Debt 5,944.9
Deferred Taxes 2,473.3
Other Liabilities 354.9
Minority Interest\*\* 0.0
TOTALLIABILITIES 9,795.7
Preferred Stock (Carrying Value) 0.0
Common Stock $^+$ Capital Surplus 6,037.6
Retained Earnings 1,049.3
Less: Treasury Stock 0.0
COMMON EQUITY 7,086.9
TOTAL LIABILITIES AND EQUITY 16 882 6

\* - Mostly deferred income taxes.
Since 2009, FAS 160 places minority interest under stockholder equity.

#
# J.M.SMUCKER - Statement of Cash Flows

Millions - Detail U.S. Dollars 2014

# OPERATIONS (Outflows --, Inflows $+$

Net Income before Extraordinary Items 344.9
Depreciation, Depletion and Amortization 268.4
Deferred Taxes and Investment Tax Credit 7.7
Other Funds 198.3
Net Change in Operating Assets & Liab (86.1)
Extraordinaries 0.0
NET CASH FLOW FROM OPERATIONS 733.2

# INVESTMENTS (Outflows --, Inflows +)

Capital Expenditures (247.7)

Disposal of Fixed Assets & Investments 2.6

Acquisitions net of Divestitures (1,320.5)

Other Investing Activities (30.1)

NETCASHFLOWFROMINVESTING (1.95.7)

# FINANCING (Outflows --, Inflows $+$

Cash Common Dividends (254.0)

Cash Preferred Dividends 0.0

Change in Current Debt (22.4)

Change in Long-Term Debt 1,188.6

Change in Common and Preferred Stock (23.5

Other Financing Activities (25.5)

# NETCASHFLOWFROMFINANCING 863.2

Exchange Rate Effect (28.6)

INCREASE (DECREASE) IN CASH (27.9)

#
# SMUCKER Historical Free Cash Flows J.M.SMUCKER

Historical Free Cash Flows (NMN means Not Meaningful Number) (based on the income statement and the statement of cash flows)

Millions - Detail U.S. Dollars

2014

Free Cash Flows to the Firm: Top Down Approach

Earnings Before Interest and Taxes (EBIT) 881.8
Less: Taxes on EBIT (accounting taxes - change in deferred taxes) 292.6
Estimate Accounting Taxes on EBIT (EBIT \* effective tax rate) 300.3
Estimate change in deferred income taxes (non-cash taxes) 7.7
Net Operating Profits After Taxes, NOPAT 589.2
Add: Depreciation, amortization, and other non-cash operating expenses 466.7
Less: Net Change in Working Capital 86.1
Less: Net Capital Expenditures & Acquisitions\*\* 1,565.6
Free Cash Flows to the Firm (FCFF) (S 95.8)

Free Cash Flows to the Firm: Bottom Up Approach

Net Income Before Extraordinary Items 344.9 Add: Change in deferred income taxes (non-cash taxes) 7.7 Adjusted Net Income Before Extraordinary Items 352.6 Add: Minority Interest (adjusted for any dividends paid) 0.0 Add: After-Tax Interest Expense 52.7 Less: After-Tax Interest Income 0.0 Less: After-Tax Non-operating Income and special items (183.9) Net Operating Profits After Taxes, NOPAT 589.2 Add: Depreciation, amortization, and other non-cash operating expenses 466.7 Less: Net Change in Working Capital 86.1 Less: Net Capital Expenditures & Acquisitions\*\* 1,565.6 Free Cash Flows to the Firm (FCFF) (595.8) Capacity to pay all investors (FCFF/NOPAT) -101.1%

Capacity to pay all investors - 10 year mean

54.4%

Check top down FCFF and bottom up FCFF are the same (difference)

0.0
Free Cash Flows to Equity 2014

Net Income Before Extraordinary Items 344.9
Add: Change in deferred income taxes 7.7
Adjusted Net Income Before Extraordinary Items 352.6
Add: Depreciation, amortization, and other non-cash operating expenses 466.7
Less: Net Change in Working Capital 86.1
Less: Net Capital Expenditures & Acquisitions\*\* 1,565.6
Less: Net Debt Principal Repayment (1,166.2)
Less: Preferred Dividends Plus Retirements 0.0
Free Cash Flows to Equity (FCFE) 333.8
Capacity to pay out equity $96.8\%$

Free Cash Flows to Debt (FCFD) (interest $^+$ net repayment)

(1086.3)

Free Cash Flows to Preferred Stock (FCFP) 0.0

2014
Common Dividends Paid & Net Stock Repurchased 277.5

10 Year Mean
Capacity to payout to shareholders (FCFE/Adjusted Net Income) $113.5\%$
Actual Payout Ratio (dividends $^+$ stock repurchase)/Adjusted net income $101.0\%$

Note that for this firm, actual payout closely tracks the capacity to payout.

\* - The tax shields, after-tax interest expenses, after-tax interest income, etc., are based on the effective tax rate which is the ratio of income taxes to earnings before taxes.
\*\* - This comes from the statement of cash flows. I exclude "Other investing activities."

#
# Computing components of free cash flows

Capital expenditures

Capital expenditures include all new and replacement property, plant, and equipment, acquisitions, and other operating investments. They can be obtained in one of two ways:

A) If we are computing free cash flows from historical statements, then capital expenditures can be obtained directly from the statement of cash flows from the section on investments. Make sure that you include only operating investments.
b) If statement of cash flows are not available, capital expenditures can be computed as $=$ Change in net fixed assets (NPPE) $+$ depreciation & amortization.

# Depreciation & Amortization

Depreciation expenses are often buried among cost of goods sold (COG) and selling, general, and administrative expenses (SG&A). The only way to get them is from the statement of cash flows.

It is the difference between change in all current operating assets (including any operating cash) and the change in all current operating liabilities.

$\Delta\mathrm{WC}=\Delta$ Current Assets - $\Delta$ Current Liabilities

Current operating assets include accounts receivables, inventories, etc. Current operating liabilities include accounts payable, taxes payable (which is different from deferred income taxes), etc.

Changes in Working Capital: Balance Sheet or Statement of Cash Flows?

· The change in working capital items taken from the statement of cash flows would not necessarily match the changes computed directly from the balance sheet.
· The numbers from the statement of cash flows are more accurate.
· Therefore, for historical analysis, use the numbers from the statement of cash flows.
· When you project future pro-forma statements, the two items would match by construction (we will discuss this later).

# Effective tax rate

Refers to the ratio of income taxes provided on the income statement to pre-tax income (earnings before taxes (EBT)) from historical statements (Taxes/EBT).

# Taxes on EBIT

Income statements report taxes based on earnings before taxes (EBT) not based on EBIT. Therefore, we have to compute taxes on EBIT as follows:

Taxes on EBIT $=$

Provision for Income Taxes from Income Statement. $+$ Tax shield from interest expense (effective tax rate\*interest expense) -Tax on Interest Income. - Tax on non-operating income at the effective tax rate.

An easier approach is to multiply the EBIT by the effective tax rate:

Taxes on EBIT $=$ Effective tax rate \* EBIT

# Deferred income taxes

· Taxes reported in financial statements and taxes paid to the government are not the same. Why? Different rules. For computing free cash flows, only taxes paid to the government are relevant. Difference between taxes reported in financial statements and taxes paid to government gives rise to deferred taxes. · Use deferred taxes to back out the taxes paid to government.

# Deferred Tax Liabilities

Taxes paid to government less than taxes reported in financial statements $\Rightarrow$ deferred tax liabilities $\Rightarrow$ good tax management
Accelerated depreciation for tax purposes vs. Straight-line depreciation for accounting purposes. Like borrowing money from the govt. Although there are no lega liabilities.

# Deferred Tax Assets

Taxes paid to government greater than taxes reported in accounting statements $\Rightarrow$ deferred tax assets $\Rightarrow$ bad tax management Certain business entertainment expenses may be deductible for accounting purposes but not for tax purposes. This is like lending money to the govt., hence an asset.
# Compute change in net deferred income taxes

Change in deferred tax liabilities

Deferred tax liabilities (t) - Deferred tax liabilities (t-1) An increase is a cash inflow because this is how much we underpaid relative to taxes reported in the financial statements.

Change in deferred tax assets Deferred tax assets (t) - Deferred tax assets (t-1) An increase is a cash outflow because this is how much we overpaid relative to reported taxes.

We need to net the inflows and out flows. Therefore, compute:

Change in net deferred taxes Change in deferred tax liabilities - Change in deferred tax assets

When we have historical statement of cash flows available, we can obtain the change in deferred income taxes directly from the statement of cash flows (see Smucker EXCEL workbook, statement of cash flows, also p.18 of this handout).

Adjusting NOPAT and Net Income for Deferred Taxes
Top Down Approach

NOPAT $=$ Earnings Before Interest and Taxes (EBIT) - (Taxes on EBIT - Change in net deferred taxes)

Bottom up Approach

NOPAT $=$

Net Income Before Extraordinary Items
$+$ Change in deferred taxes
+ After-tax interest expense
- After-tax interest income
After-tax non-operating income (if any)

[+ Add any minority interest (to be discussed)]

Adjusted Net Income $=$ Net Income Before Extraordinary Items $+$ Change in deferred taxes

# Deferred Taxes in the modified balance sheet

Deferred taxes are like quasi-equity in the sense these funds belong to shareholders until the taxes are paid to the government. Hence, add them to equity in calculating total investor funds to match invested capital.

# Net Deferred Tax Liabilities $=$

Deferred tax liabilities -- Deferred tax assets

Original Balance Sheet
<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess Cash (Cash, Marketable Securities, and Other Short-Term & Long- Term Investments)</td><td>Current (non-interest-bearing) operating liabilities (accounts payable and other accruals)</td></tr><tr><td>Current operating assets (accounts receivable, operating cash, inventories)</td><td></td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment) Other long-term operating</td><td>Short-term debt (floating rate debt, currently maturing long- term debt)</td></tr><tr><td>assets</td><td>Long-term debt (long-term bonds, bank loans) Deferred Tax Liabilities</td></tr><tr><td>Deferred Tax Assets</td><td>Preferred Stock</td></tr><tr><td>Total Assets</td><td>Common Stock TotalLiabilities</td></tr></table></body></html>

# Modified Balance Sheet

Subtract Current operating liabilities & Deferred Tax Assets from both sides (subtracting from both sides ensures that the modified balance sheet remains in balance).

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess cash Invested Capital</td><td>Short-term debt (floating rate debt, currently maturing long- term debt) Long-term debt (long-term</td></tr><tr><td>Net Operating Working Capital (Current operating assets - Current operating liabilities)</td><td>bonds, bank loans) Preferred Stock Net Deferred Tax Liabilities = (Deferred Tax Liabilities - Deferred Tax Assets)</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment) Other long-term operating assets</td><td>Common Stock</td></tr><tr><td>Total Capital</td><td>Total Investor Funds</td></tr></table></body></html>

We should treat net deferred tax liabilities as quasi-equity and add it to common stock in computing book value of equity.
# Goodwill

Goodwill is an asset on the balance sheet that represents the price premiums paid for acquisitions over the market value of their net tangible assets.

# What does good will represent?

· Intangible assets such as brand name (say Coco Cola or Pepsi brand name) and any synergies.
Overpayment (due to winner's curse).

Goodwill unlike other fixed assets does not wear out on a regular basis and does not need to be replaced on a regular basis.

FASB rules SFAS 141 & 142 recognize this concern and require goodwill to be written down only when it gets impaired. Impairment is determined by a set of complex accounting rules and may be triggered by a drop in the firm's market value. If there is no impairment, goodwill is kept at its original amount on the balance sheet.

Until 2001, the goodwill asset was amortized mechanically on a straight-line basis over a 40-year period. Historical statements prior to 2001 should be adjusted to undo the impact of goodwill amortization on the financial statements since it is a non-cash expense.
# Original Balance Sheet with Good Will

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess Cash (Cash, Marketable Securities, and Other Short-Term & Long- Term Investments) Current operating assets (accounts receivable, operating cash, inventories) Fixed Operating Assets (Net property, plant, and equipment) Other long-term operating assets Deferred Tax Assets Good Will</td><td>Current operating (non- interest bearing) liabilities (accounts payable and other accruals) Short-term debt (floating rate debt, currently maturing long-term debt) Long-term debt (long-term bonds, bank loans)</td></tr></table></body></html>

# Modified Balance Sheet with Goodwill

Subtract current operating liabilities and deferred tax assets from both sides.

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess cash</td><td>Short-term debt (floating rate debt, currently maturing long-term debt) Long-term debt (long-term bonds, bank loans)</td></tr><tr><td>Invested Capital Net Operating Working Capital (Current operating assets - Current operating liabilities)</td><td>Preferred Stock (Deferred Tax Liabilities - Deferred Tax Assets)</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment) Other long-term operating assets</td><td>Common Stock</td></tr><tr><td>Good Will Total Capital</td><td>Total Investor Funds</td></tr></table></body></html>

# Accounting for investments in other companies

If company A invested in another company B, the accounting method used, in general, depends on the percentage of the voting stockA owns.
<html><body><table><tr><td>A's ownership of B</td><td>Accounting Method used by A</td><td>A's income Statement</td><td>A's balance Sheet</td><td>A's Cash Flow Statement</td><td>Comments</td></tr><tr><td>< 20%</td><td>Cost E.g.: A owns 10% of B.</td><td>Any dividends from B included in other income below EBIT of A. A's share of B's earnings not reported.</td><td>Investment is a long-term asset under "Other long- term assets" at cost.</td><td>No effect</td><td>The asset is most likely operating: dividend income is also operating.</td></tr><tr><td>20% to 49% Deemed to have sufficient influence over B.</td><td>Equity E.g.: A owns 30% of B.</td><td>A reports 30% of B's income below EBIT as "Equity in earnings (losses) of unconsolidated affiliates."</td><td>The investment is a long-term asset under "Other long- term assets." Book or fair market value</td><td>The portion of income that is non-cash is deducted in the Operating section. Depends on any dividends from B to A.</td><td>Earnings and assets should be operating.</td></tr><tr><td>>= 50% Deemed to have “control" over B; B is now a subsidiary of A.</td><td>Consolidated E.g.: A owns 80% of B and minority shareholders own the rest.</td><td>A consolidates B's income statement in its own income statement. The income that belongs to minority owners of B is deducted as "Minority interest below EBIT.</td><td>A includes all of B's assets and liabilities on its own balance sheet. The 20% owned by others is shown as "Minority Interest' under equity.</td><td>The minority earnings deduction is non-cash and added back. Any dividends paid to minority shareholders offset the deduction.</td><td>Since 2008/2009 minority interest is reported separately under shareholder's equity and not under liabilities. See SFAS 160.</td></tr></table></body></html>

# Modified Balance Sheet with Minority Interest

Subtract current operating liabilities and deferred tax assets from both sides.

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess cash</td><td>Short-term debt (floating rate debt, currently maturing long-term debt) Long-term debt (long-term bonds, bank loans)</td></tr><tr><td>Invested Capital Net Operating Working Capital (Current operating assets - Current operating liabilities)</td><td>Preferred Stock (Deferred Tax Liabilities - Deferred Tax Assets)</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and equipment) Other long-term operating assets Good Will</td><td>Common Stock (Including Minority Interest)</td></tr><tr><td>Total Capital</td><td>Total Investor Funds</td></tr></table></body></html>

# Things to keep in mind on subsidiary accounting

·If you add “equity in earnings of unconsolidated affiliates" to operating income, remember to add the assets corresponding to that income to operating assets. Be consistent in your treatment of income and assets.

In computing free cash flows, remember to subtract any noncash income (recall other non-cash expenses in our free cash flow definition, just as you add other non-cash expenses, you must subtract non-cash income). Thus, if you add “equity in earnings" to operating income, remember to subtract any noncash portion from the free cash flows. This may not be easy to sort out from the financial statements (see footnotes).

· For fully consolidated statements, remember that the minority interest deduction in the income statement is most likely a non-cash expense. The statement of cash flows would add it back, net of any dividend distribution to minority shareholders. A dividend distribution to minority shareholders reduces the operating cash flows available to majority shareholders.

The consolidation accounting is careful in delineating income and equity attributable to minority and majority interests but not so when it comes to operating cash flows. There is no reporting consistency in the dividends paid to minority interest and in some instances they are not even reported on the statement of cash flows (Mulford and Dar, 2012). Thus, it is hard to determine how much of the operating cash flows belong to minority interest.

#
# Special Items

· These represent unusual or non-recurring items reported above taxes and below EBIT by the company.
· This is not a description used by the company or GAAP.
This is a description used by analysts and databases such as Compustat and CapIQ. Analysts remove special items in comparing earnings across periods.
This is to be distinguished from extraordinary items, which is a GAAP item reported below Net Income Before Extraordinary Items.
Special items typically consist of: 0 Impairment of goodwill O Gain (Loss) on sale of Assets $\bigcirc$ Insurance settlements and legal settlements O Restructuring charges O Other unusual items.
The default assumption is that we should treat them as nonoperating unless otherwise they are recurring and predictable.
These items do not affect the top-down approach to computing FCFF since they appear below EBIT. They do affect the bottom-up approach. You may not want to include them in computing FCFE either.

# Long-term operating liabilities

·Pension liabilities arise from defined benefit plans in terms of what the firms owes its employees in the future. There i a lot of complicated actuarial accounting associated with estimating these items. SFAS 158 requires reporting of net pension liabilities (if underfunded) and assets (if overfunded).
· Post-retirement obligations consist of the present value of post-retirement healthcare and welfare benefits and are distinct from pension liabilities. Unlike interest-bearing debt and lease obligations they are not financial liabilities but long-term operating liabilities created by the operations of the company.
The interest expenses associated with these liabilities are part of the pension expenses and post-retirement benefit expenses (just like the interest cost on accounts payable) and are, therefore, included in operating expenses.
Therefore, just like we subtracted accounts payable in computing net working capital, we also should subtract these operating liabilities from operating assets. However, for calculations to evaluate credit risk, we shoul include them in the calculation of debt ratios.

See the modified balance sheet on the next page.

# Modified Balance Sheet with long-term operating liabilities

Subtract long-term operating liabilities from both sides.

<html><body><table><tr><td>Assets</td><td>Liabilities</td></tr><tr><td>Excess cash</td><td rowspan="3">Short-term debt (floating rate debt, currently maturing long-term debt) Long-term debt (long-term bonds, bank loans) Preferred Stock (Deferred Tax Liabilities - Deferred Tax Assets)</td></tr><tr><td>Invested Capital Net Operating Working Capital (Current operating assets - Current operating liabilities)</td></tr><tr><td>Fixed Operating Assets (Net property, plant, and Common Stock (Including equipment) Minority Interest) Other long-term operating assets Less: long-term operating liabilities Good Will Total Capital</td></tr></table></body></html>

# How to estimate invested capital?

From the previous page:

Invested Capital $=$ [Short-term debt $+$ Long-term debt $+$ Book value of preferred stock $+$ (Deferred tax liabilities - Deferred tax assets) $+$ Book value of common stock including minority interest] - Excess cash

This is useful if you are writing code to compute IC from databases such as Compustat or CapIQ.

It is also the difference between operating assets and operating liabilities.

Invested Capital = Operating Assets -- Operating Liabilities
Operating Assets $=$ Total Assets - Excess Cash - Deferred tax assets
Operating Liabilities $=$ Total Assets - Total Debt - Book Value Common and Preferred stock - Minority Interest - Deferred tax liabilities

Note that my use of the term "Excess Cash" also includes all non-operating assets.

# Equity Equivalents

Note that net deferred income taxes is like quasi-equity in the sense including it in book value of equity provides a better measure of the equity capital.

Therefore, the adjusted book value of equity is:

$=$ Book Value of Equity from the balance sheet $+$ Net deferred income taxes

The adjusted net income definition consistent with the adjusted book value of equity is:

Net Income Before Extraordinary Items $+$ Change in deferred income taxes

There are other items that could be added to the equity equivalents (see pages 145-147 of the text book):

· Minority interest (which is now under book equity). Equity portion of hybrid securities such as convertible debt or convertible preferred.

# Things to keep in mind

Whether an item is operating or non-operating depends on a subjective analysis of the operations of the particular firm. Refer to 10-K reports and footnotes in financial statements in making these judgments.
· In the same vain, when you cannot clearly determine whether a balance sheet or an income statement item is operating or non-operating just make an assumption and consistently follow that assumption in your calculations.
Apply the “who cares rule'. If an item such as deferred taxes or non-operating income is too small to be material in your calculations, you might as well just ignore them. It may not be worth your time to figure out the exact numbers and their effects.

The EXCEL workbook Smucker-July 2015 version 7.0. Xls contains various worksheets that can be used as templates for the valuation exercises you will perform with Boeing.

# Lecture Note 2 Computing Cost of Capital: Cost of Equity, Cost of Preferred Stock and Cost of Debt

# Objective

Introduce students to the mechanics of computing cost of capital.

# Outline

· Define weighted average cost of capital (WACC) ·Systematic risk Vs. Idiosyncratic Risk
· Risk-return trade-off among major asset classes
· Capital Asset Pricing Model (CAPM)
Estimating cost of equity: risk-free rate, risk premium, and adjusted beta.
· Computing cost of debt
Computing WACC for Smucker.

# Cost of Capital

Cost of capital is also variously referred to as opportunity cost of capital, discount rate, hurdle rate, expected return, and minimum rate of return:

Cost of debt, rd.
Cost of preferred stock, rp.
Cost of equity, $\mathrm{r_{e}}$ Weighted average cost of capital, WACC, which depends on $\Gamma_{\mathrm{d}},\Gamma_{\mathrm{p}} $ and $\mathrm{r_{e}}$ in the following manner.

$$
W A C C=r_{e}\frac{E}{V}+r_{p}\frac{P}{V}+r_{d}(1-T_{c})\frac{D}{V}
$$

where E, P, and D are market values of equity, preferred stock, and debt respectively, $\mathrm{V=D+P+E}_{}$ and $\mathrm{T_{c}}$ is the corporate income tax rate. When there is no preferred stock, $\mathrm{P=}0$ , equation (la) simplifies to the familiar:

$$
W A C C=r_{e}\frac{E}{V}{+r_{d}}(1-T_{c})\frac{D}{V}
$$

We will discuss how to estimate each element of the WACC formula.

# Systematic Risk Vs Idiosyncratic Risk

Systematic risk: Risk of a decline in the value of a stock or portfolio due to market-wide movements or general economic conditions.

Example: The decline in NASDAQ and DJIA, increase in energy prices, economic slowdown.

Idiosyncratic Risk: Risk of a decline in the value of a stock or portfolio due to firm-specific events such as (a) accounting irregularities, (b) union problems, (c) product defects, etc.

# Which risk is relevant for cost of capital?

· In perfect markets, theoretically, only systematic risk should matter in computing cost of capital. This is because idiosyncratic risk should be diversifiable. ·Violations of perfect market assumption (E.g.: employees holding too much of their savings in own company stock and not diversifying) could lead idiosyncratic risk to be priced. High systematic risk $\Rightarrow$ High cost of capital.

# Estimating Cost of Equity

There are three approaches to estimating the cost of equity of a firm:

1) The asset pricing approach: The asset pricing approach relies on asset pricing models provided by financial theory. In particular:

A) Single factor model: The Capital Asset Pricing Model (CAPM). We will focus only on CAPM. B) Multi-Factor models.

2) The discounted cash flow (DCF) approach: This approach estimates cost of equity as the internal rate of return that equates the present value of projected free cash flows to equity (FCFE) to current stock price. The cost of equity estimated from the DCF approach is referred to as the implied cost of capital (I will post some of my research in this area).

3) An Integrated approach: This approach uses a DCF model to estimate risk premium on the market and then uses this risk premium along with CAPM to estimate cost of equity Of the firm.

We will discuss the asset pricing approach in detail now.
# Major Asset Classes in US: Ibbotson Associates 2012 Yearbook (market results for 1926-2011)

(1) Large company stocks

S&P 500 market index.

(2) Small company stocks

The bottom $20\%$ of the stocks in NYSE by market capitalization plus AMEX and NASDAQ stocks.

(3) Long-term corporate bonds

High grade AAA corporate bonds.

(4) Long-term and intermediate term US government Bonds (maturity 15 to 30 Years)

(5) US Treasury bills (1 Month maturity)

(6) Inflation.

Note: Including data for 2012-2014 does not change the averages much.
Table 7 Basic Series and Porfolios: Summary Statistics of Annual Total Returns in Percent
<html><body><table><tr><td rowspan="2">Asset Class</td><td colspan="3">From 1926 to 2011</td></tr><tr><td>GeometricMean</td><td>Arithmetic Mean</td><td>StandardDeviation</td></tr><tr><td>Large Company Stocks</td><td>9.8</td><td>11.8</td><td>20.3</td></tr><tr><td>Small Company Stocks</td><td>11.9</td><td>16.5</td><td>32.5</td></tr><tr><td>Long-Term CorporateBonds</td><td>6.1</td><td>6.4</td><td>8.4</td></tr><tr><td>Long-TermGovernmentBonds</td><td>5.7</td><td>6.1</td><td>9.8</td></tr><tr><td>Intermediate-Term Government Bonds</td><td>5.4</td><td>5.5</td><td>5.7</td></tr><tr><td>U.S. Treasury Bills</td><td>3.6</td><td>3.6</td><td>3.1</td></tr><tr><td>Inflation</td><td>3.0</td><td>3.1</td><td>4.2</td></tr></table></body></html>

Risk-return staircase: Higher systematic risks, higher return in the long-run.

# Real T-Bill return

The real T-bill return is the nominal T-bill return minus the inflation rate. The arithmetic average real T-bill return over the 1926-2011 sample period is $0.5\%$ per annum. T-bills are good inflation hedge in the long-run!

# Maturity (term) risk premium

(a) Long-term bond prices are more sensitive to interest rate fluctuations than short-term T-bills. This makes long-term bonds more risky for lenders. How?
(b) The term risk premium is the average return on long-term government bonds minus the average return on 1-month US treasury bills. For the 1926-2011 sample period, the term risk premium (arithmetic mean) is $2.5\%$ per annum.

# Default risk premium

(a) Investors in long-term corporate bonds are subject to default risk.
(b) The default risk premium is the average return on longterm corporate bonds minus the average return on longterm government bonds. For the 1926-2011 sample period, the default risk premium (arithmetic mean) is $0.3\%$ per annum. Why so low?

# Equity risk premium

A) The equity risk premium is the average return on large company stocks minus the average return on short-term treasury bills, or long-term government bonds.

(b) For the 1926-2011 sample period, the equity risk premium (arithmetic mean) with respect to shortterm treasury bills is $8.2\%$ per annum. The equity risk premium (arithmetic mean) with respect to long-term government bonds is $5.7\%$ per annum.

(c) Is $6\%$ to $8\%$ range appropriate now?

# Small stock premium

(a) The small stock premium is the average return on small company stocks minus the average return on large company stocks.
(b) For the 1926-2011 sample period, the small stock premium (arithmetic mean) is $4.7\%$ per annum.

# Arithmetic Mean Vs Geometric Mean

Suppose we want to compute the average of annual returns over the last T years.

# Arithmetic Mean

$$
r_{A}=\sum_{t=1}^{T}{\frac{r_{t}}{T}}
$$

# Geometric Mean

$$
r_{G}=\left[\left(1+r_{1}\right)\times\left(1+r_{2}\right)\times\cdots\times\left(1+r_{T}\right)\right]^{1/T}-1.0
$$

# Relation between geometric mean and arithmetic mean

$$
r_{G}\approx r_{A}-\big/_{2}\upsigma^{2}
$$

where $\upsigma$ is the standard deviation of returns.

· Geometric mean is a better measure of past performance. · Arithmetic mean is a better guide to expected future performance.

# Capital Asset Pricing Model (CAPM) approach

The cost of capital/expected return of an asset ‘i' is:

$$
\mathrm{E(r_{i})=r_{f}+^{\mathrm{{\ell\times}}}R i s k P r e m i u m^{\prime\mathrm{{\prime}}}}
$$

Rf is the risk-free rate and “Risk Premium' is an appropriate risk premium. CAPM computes the risk premium for the stock/asset as a linear function of the market risk premium:

$$
r_{e}=r_{f}+\beta_{e}\left\lfloor E(r_{m})-r_{f}\right\rfloor
$$

rf $=$ The risk-free rate of interest.
$\mathrm{E(r_{m})-r_{f}}$ The risk-premium on the market index,
βe The beta measures systematic risk. It measures co-movements between the market and the stock. $\upbeta_{\mathrm{e}}>1$ , riskier than the market portfolio.
$\upbeta_{\mathrm{e}}<1$ , less risky than the market portfolio.
$\upbeta_{\mathrm{e}}=1$ , as risky as the market portfolio.
$\upbeta_{\mathrm{e}}=0$ , risk-free asset.

# Be consistent in choosing risk-free rates and risk premia.

T-bill yield $\Leftrightarrow$ Risk premium based on T-bill returns.
T-bond yield $\Leftrightarrow$ Risk premium based on T-bond returns.

# Estimating the risk-free rate

For long-term projects, it is customary to use the longterm US government bond yield as the risk-free rate.

· You can use maturities ranging from 10 to 30 years. The yield to maturity (YTM) on 10 to 30-Year Treasury bond can be obtained from Yahoo Finance.

http://finance.yahoo.com/bonds

· July 2015 YTM on the 30-year Treasury bond was $2.9\%$

July 2015 YTM on the 10-year Treasury bond was 2.2%.

Risk Premium on the Market, $E(r_{m}-r_{\mathcal{P}}$

<html><body><table><tr><td colspan="2">Arithmetic Mean</td><td>Geometric Mean</td></tr><tr><td>Risk premium with respect to 1-month T-bills</td><td>8.2%</td><td>6.2%</td></tr><tr><td>Risk premium with respect to</td><td>5.7%</td><td>4.1%</td></tr><tr><td>long-term govt. Bonds</td><td></td><td></td></tr></table></body></html>

Estimates based on historical data range from $4.1\%$ to $8.2\%$

# Forward-looking risk premium from a three-stage valuation model

 ![500](96cb5c803f55bfe7fae81a4919435b9b99e042bb51972201adfbfe825b9a85eb.jpg)

The monthly risk premium is estimated by first computing an implied cost of capital from a threestage discounted cash flow model and then subtracting the long-term treasury yield. We will discuss the three-stage valuation model used in this paper in the next Lecture.

# Market Risk Premium - Bottom Line

· An estimate of between 5 and $6\%$ relative to 30-year bonds seems reasonable.
● For small stocks (less than \$1 billion in market cap), we can add an additional risk premium of up to $3\%$ to the CAPM risk premium. Risk premium for small stocks $=$ CAPM risk premium $+$ (a risk premium up to $3\%$

#
# Estimating beta from monthly returns

Beta estimates can be obtained from Yahoo Finance. Yahoo uses 24 to 60 months of data to estimate betas.

http://finance.yahoo.com/q/ks?s $\equiv$ SJM+Key+Statistics

The beta-estimation regression is:

$$
\mathrm{R}_{\mathrm{it}}=\mathbf{a}+\upbeta_{\mathrm{raw}}\mathrm{R}_{\mathrm{mt}}+\mathbf{e}_{\mathrm{t}}
$$

Rit is a stock's monthly stock return, $\mathrm{R_{mt}}$ is the monthly return on S&P 500 index, and $\mathrm{e_{t}}$ is the idiosyncratic error.

Beta adjustment formula

$$
\mathrm{\Delta\beta_{adjusted}=(1/3)~+(2/3)*\Delta\beta_{p a w}}
$$

This adjustment takes into account mean-reversion in individual stock betas and the noise in estimating them.

· Raw beta is the historical beta. Adjusted beta is the predicted future beta. Equation (6) is the forecasting equation estimated from past data. Make sure to do the adjustment when using individual stock betas.

An alternative is to average the betas of similar firms in the industry. If you have more than 10 stocks, no need for the adjustment since portfolio betas are less noisy.
# A checklist for using Beta from online data sources

· Is the Beta computed from monthly returns? Use betas computed from daily returns only as a last resort. How does one estimate betas using daily or weekly returns? We use Dimson beta. ·● If it is based on monthly returns, how many months of data were used? At least 24 months of data is preferable. Finally, has the Beta been adjusted using the adjustment formula given in equation (6)? If not perform the adjustment.

# Beta sources

Yahoo Finance, Thomson-Reuters, Compustat, Valueline, Bloomberg all provide betas computed with at least 24 months of data. All these sources use S&P 500 as the market index. Valueline and Bloomberg also provide adjusted betas.
# Computing Cost of Equity for Smucker using CAPM

Smucker is in the Processed & Packaged Goods Industry within the Consumer Goods Sector. The unadjusted beta for SMUCKER is (as of July 8, 2022):

Source Beta Yahoo Finance 1.21

Adjustedbeta: $1/3+2/3^{*}1.21=1.14$ MarketRiskPremium $=6\%$ Yield on 30-Year T-bond $=2.9\%$

Using CAPM:

Cost of Equity $=2.9+1.14^{*}6=9.74\%.$

The market cap for Smucker is \$12.98 billion. It is at the higher end of the mid-cap range and lower-end of the large-cap range. It is not a small company. No need to add a small firm premium.

# Cost of Debt

The cost of debt depends on:

· The current level of interest rates.
· The default risk of the company.
The seniority and maturity of the particular debt issue.

# Long-term debt

Long-term debt is usually in the form of coupon bonds. For traded coupon bonds, the cost of debt is computed as the yield to maturity (IRR) given the current market price.

$$
P_{B0}=\sum_{t=1}^{T}{\frac{C_{t}}{(1+y t m)^{t}}}+{\frac{F V}{(1+y t m)^{T}}}
$$

where $\mathrm{C_{t}}$ is annual or semi-annual coupon payments. If the coupon payments are semi-annual, then T is 2 times the maturity in years of the bond and ytm is the semi-annual yield to maturity.

An easier way to obtain yield to maturity for coupon bonds is to use the yield on a portfolio of bonds with the same bond rating (and same maturity) as the issue under consideration. What is yield to worst?
# Cost of debt based on ratings

Obtain the bond rating for all publicly traded bonds of your company from Moody's Bond Record or Standard & Poor's (you can obtain these from BLOOMBERG).
·Also available in the Osiris database (through the online Library link). The current yield to maturity for corporate bonds with a given rating and given maturity can be obtained from http://finance.yahoo.com/bonds/composite_bond_rates
· Note that the yields reported are promised yields computed based on promised cash flows. However, if the default risk is high, the expected cash flows from the bond will be lower than the promised cash flows. Thus, the expected yield (cost of debt) would be lower than the promised yield for bonds with very high default risk, i.e., junk bonds.
For most high-grade bonds, the promised yield will be close to the expected yield and, therefore, you can just use the promised yield.
· Note that the coupon rate is not the cost of debt. Coupon rate is a historical rate while cost of debt refers to the current yields.

# Private Placement Debt

The yield on privately placed debt can be based on the ratings of comparable publicly traded bonds (available on Bloomberg).

Note that the yield on privately placed debt should, in general, be higher than comparable publicly traded debt because the privately placed debt is less liquid.

# Bank Debt

For bank debt (which is not usually traded) we can analogously use the yield on comparable publicly traded bonds.

# Short-Term Debt

Permanent short-term debt should be included in computing cost of debt. For short-term debt and floating-rate debt, coupon rates are usually good proxies of yield to maturity.

Note: All permanent interest bearing debt should be included in the cost of debt calculations.

# Weighted Average Cost of Debt

If you have different kinds of debt then you can compute a weighted average cost of debt (for instance) as follows:

$$
r_{d}=\sum_{i=1}^{M}\frac{D_{i}}{D}\times r_{d i}
$$

where $\mathrm{D}_{\mathrm{i}}$ is the market value of the ‘i'th debt issue, D is the sum of market values of all debt, M is the number of debt issues and $\mathrm{r_{di}}$ is the cost of debt for the ‘i'th issue.

Note 1: Debt should include all permanent interest-bearing debt (including long-term lease liabilities), which may include floating rate debt and revolving credit lines.

Note 2: Non-interest bearing current liabilities (accounts payable) and non-interest bearing long-term liabilities (such as deferred taxes) should not be included.

Note 3: Capital Leases (long-term leases that are capitalized on the balance sheet) should be included.

# Cost of Preferred Stock

It is easy to estimate the cost of preferred stock. Preferred stocks have fixed dividend payments with no future growth. Therefore, the cost of preferred stock, $\mathrm{r_{p}}$ is given by:

$$
r_{p}=\frac{D_{p}}{P_{p0}}
$$

where $\mathrm{D_{p}}$ is the annual fixed preferred dividend and $\mathrm{P_{p0}}$ is the market value of preferred stock (we can approximate this with the book value).

Note that preferred stock is more risky than debt but less risky than equity. Also, note that preferred dividends are not taxdeductible.

The cost of finite-maturity preferred stock can be computed in the same way we compute yield to maturity on a coupon bond.
# Computing weighted average cost of debt for Smucker

<html><body><table><tr><td>YearendedApril 30,2015</td><td></td><td></td><td>$MM</td><td colspan="2">AsofAugust 12,2015</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>Maturity</td><td>Coupon</td><td>BookValue</td><td>Price</td><td>MarketValue</td><td>weight</td><td>Rating</td><td>YTM</td><td>weight*YTM</td></tr><tr><td>1.75%</td><td>3/15/2018</td><td>1.75%</td><td>496.9</td><td>100.27</td><td>498.22</td><td>0.082</td><td>A 3</td><td>1.64%</td><td>0.13%</td></tr><tr><td>2.50%</td><td>3/15/2020</td><td>2.50%</td><td>494.3</td><td>99.79</td><td>493.26</td><td>0.081</td><td>A 3</td><td>2.55%</td><td>0.21%</td></tr><tr><td>3.50%</td><td>10/15/2021</td><td>3.50%</td><td>796</td><td>102.78</td><td>818.16</td><td>0.134</td><td>A 3</td><td>3.00%</td><td>0.40%</td></tr><tr><td>3.00%</td><td>3/15/2022</td><td>3.00%</td><td>395.3</td><td>98.21</td><td>388.22</td><td>0.064</td><td>A 3</td><td>3.31%</td><td>0.21%</td></tr><tr><td>3.50%</td><td>3/15/2025</td><td>3.50%</td><td>991.9</td><td>98.41</td><td>976.08</td><td>0.160</td><td>A 3</td><td>3.70%</td><td>0.59%</td></tr><tr><td>4.25%</td><td>3/15/2035</td><td>4.25%</td><td>641.8</td><td>95.13</td><td>610.52</td><td>0.100</td><td>A 3</td><td>4.63%</td><td>0.46%</td></tr><tr><td>4.38%</td><td>3/15/2045</td><td>4.38%</td><td>583.8</td><td>93.30</td><td>544.70</td><td>0.089</td><td>A 3</td><td>4.80%</td><td>0.43%</td></tr><tr><td>Short-termborrowings</td><td></td><td>0.45%</td><td>226</td><td></td><td>226.00</td><td>0.037</td><td>A 3</td><td>0.45%</td><td>0.02%</td></tr><tr><td>Term loan</td><td>3/23/2020</td><td>1.53%</td><td>1,545</td><td></td><td>1,545</td><td>0.253</td><td>A 3</td><td>1.53%</td><td>0.39%</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Total</td><td></td><td>2.79%</td><td>6,170.90</td><td></td><td>6,100.07</td><td>1.00</td><td></td><td></td><td>2.84%</td></tr><tr><td></td><td></td><td>Wtd. Avg.</td><td></td><td></td><td></td><td></td><td></td><td></td><td>CostofDebt</td></tr><tr><td></td><td></td><td></td><td>MarketValueofDebt</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td colspan="4">dividedbyBookValueofDebt 1.012</td><td></td><td></td><td></td><td></td><td>*SourceBloomberg</td></tr></table></body></html>

· The ditferent maturity debt outstanding can be obtained from the footnotes to the financial statements.
· Market Value $=$ Book Value \* Price/100.
· Ratings are from Moody's where A 3 is equivalent to A- by S&P. Weighted average cost of debt is $2.84\%$ The weighted average coupon rate is $2.79\%$ which is a bit lower than the cost of debt. Using coupon interest rate could lead to highly erroneous estimates of cost of debt. The coupon rates reflect historical interest rates that existed at the time the debt was issued.
· See Worksheet 12 in Smucker-July 2015 version 7.0. Xls.

# Weighted Average Cost of Capital for SMUCKER

From page (18), the cost of equity from CAPM, $\mathrm{r_{e}}=9.74\%$

Market value of equity as of July 8, 2022 is \$12,979 MM.

Book value of interest bearing debt as of July 28, 2014 was about \$6,171 MM with maturities ranging from 1 year to 30 years.

$$
\mathrm{D}/\mathrm{V}=6,171/19,150=0.32,\mathrm{E}/\mathrm{V}=0.68.
$$

Weighted average cost of debt is $2.84\%$

$$
\mathrm{WACC}=9.74\%^{*}0.68+2.84\%^{*}(1-0.34)^{*}0.32=7.2\%.
$$

(for tax rate we can use a company $^{\bullet}\mathrm{s}$ statutory tax rate inclusive of both state and federal taxes of around $38\%$ or the effective tax rate of $34\%$ in 2014).

Note: Book value of debt may not always be a good proxy for market value of debt (even for high grade bonds) since interest rates have fallen drastically in the last 5 years.

For Smucker, however, the ratio of market value of debt to book value of debt is about 1.
# Lecture Note 3 Discounted Cash Flow Valuation: Value Drivers and Implementing the Free Cash Flow Model

# Objective

Introduce students to a practically implementable three-stage free cash flow valuation model based on analyst earnings forecasts and plowback rates.

# Outline

· Firm valuation based on value drivers: growth, ROI, and plowbackrate
· Terminal value based on value drivers
· Assets in place and PVGO
· Value drivers and equity valuation
# Economic Value Drivers and Free Cash Flows

● The objective of valuation is to relate firm value to underlying economic value drivers.
We will discuss how to forecast free cash flows in terms of some key value drivers and show how these value drivers affect firm value.
·We will develop a simple three-stage free cash flow valuation model that can be used to compute total enterprise value (V) and the value of equity (E). This approach does not require forecasting income statements, balance sheets, and cash flow statements and can give valuations quite close to that based on full-fledged pro-forma financial statements.

Note that the reference to firm value here is to Total Enterprise Value. You have to add the value of non-operating assets (excess cash, etc.) to get total firm value.

# Some simple formulas of firm (total enterprise) value

No growth case:

The total enterprise value of $\overset{\cdot}{a}$ firm whose profits are expected to be constant in perpetuity is equal to:

$$
V_{0}=\frac{N O P A T_{1}}{W A C C}
$$

Where NOPAT; is the constant expected profits (equal to the free cash flows) in perpetuity and WACC is the weighted average cost of capital. This is also referred to as the Earnings PowerValue $(E P V)$

# Constant growth case:

When the free cash flows to the firm are expected to grow at a constant rate $g$ forever $(g<W A C C)$ , then:

$$
V_{0}=\frac{F C F F_{1}}{W A C C-g}
$$

This is simply the Gordon growth model.

To understand valuation in contexts other than these simple ones we need to understand the role of value drivers.

# Value Drivers of free cash flows and firm value

There are three key value drivers of free cash flows:

The rate of growth of a company's revenues, profits, and operating assets (g).
· The return on new investment (ROI), which determines the profitability of the new investments undertaken by the business.
The firm's reinvestment rate (b), which determines its capital expenditure (new investments) policy. There are only two independent value drivers. Given two value drivers, the third one can be determined as a function oi the other two.

CapEx refer to capital expenditures (both new and replacement capital expenditures, includes acquisitions)

$\varDelta W C$ refers to change in working capital, which is a measure of new working capital investments.

Dep & Amort refers to all depreciation and amortization (more generally also all non-cash items)

To keep things simple, assume that we are in a low inflation environment.
Consider free cash flows to firm:

Define:

Gross Investment CapEx + AWC

Gross investment refers to new and replacement capital expenditures and investments. Also define:

Net new investment refers to new capital investments made in excess of replacement capital investments.

Economically, replacement investments are needed to maintain existing production capacity and sales while new investments are needed to generate additional growth.

Now we can define free cash flows to the firm as:

$$
F C F F=N O P A T-N e t N e w I n v e s t m e n t
$$

Thus, free cash flows to firm are the cash left over from NOPAT after a firm has spent sufficient funds on new investments. If a firm makes no net new investment, then $\mathrm{FCFF}=\mathrm{NOPAT}$ into perpetuity (equation (1)).

Define the reinvestment rate (b) as the rate at which a firm reinvests its NOPAT (for NOPAT $>=0$

$$
B=\frac{N e t N e w I n v e s t m e n t}{N O P A T}
$$

Can “b' be > 1? Can “b' be < 0? Explain?

Using equation (7), write FCFF in equation (6) as:

$$
F C F F=(I-b)\times N O P A T
$$

$(1-\mathsf{b})$ is the proportion of NOPAT available for payout to all investors of the firm (capacity to payout all investors).

# We can forecast free cash flows by forecasting growth in profits $\mathbf{\deltag}^{\prime}$ and the reinvestmentrate $\mathbf{\nabla}^{6}b^{2}$

Example: Consider two firms A and B with the same operating risks and capital structure. Assume that inflation is close to zero (to avoid any inflation induced growth). Both firms are expected to earn net operating profits after taxes (NOPAT) of $\$100$ in Year 1. If the two firms do not invest in new assets, both will continue to earn $\$100$ for ever. The WACC for both firms is $8\%$

1) Assume that Firm A reinvests $15\%$ of its NOPAT in new investments and earns $20\%$ return on them. Firm B, however, earns only $10\%$ return on new investments. If firm B wants to achieve the same growth in profits as firm A, what percentage of its NOPAT should it reinvest each year? Which firm will have more free cash flows and which firm will be more valuable?
2) Suppose now Firm A and Firm B have the same return on new investments equal to $20\%$ Firm A reinvests at a rate of $30\%$ a year. However, Firm B does not face the same investment opportunities as Firm A and can reinvest only $15\%$ a year. Which firm will have more free cash flows and which firm will be more valuable?
# Example 1: How return on investment drives firm value?

# Firm A

ROI $20\%$ Sample NOPAT calculation: Year 2 NOPAT $=$ Year 1 NOPAT $+$ Year 1 Net Inves tment \* RO 1 b $15\%$ $=100+15*0.20=$ 103 Example 2: How growth drives firm value (provided ROI $>$ WACC)

Company A

'ROI 20% b 30% WACC 8%

Annual growth rate in NOPAT & FCFF
<html><body><table><tr><td>Firm A</td><td>Year 1</td><td>Year 2</td><td>Year 3</td><td>Year 4</td><td>Year 5</td><td>Year 6</td><td>Year 7</td><td>Year 8</td><td></td><td></td><td></td><td>Year 9 Year 10 Year 11 Year 12</td></tr><tr><td>NOPAT</td><td>100.0</td><td>106.0</td><td>112.4</td><td>119.1</td><td>126.2</td><td>133.8</td><td>141.9</td><td>150.4</td><td>159.4</td><td>168.9</td><td>179.1</td><td>189.8</td></tr><tr><td>NetInvestment</td><td>30.0</td><td>31.8</td><td>33.7</td><td>35.7</td><td>37.9</td><td>40.1</td><td>42.6</td><td>45.1</td><td>47.8</td><td>50.7</td><td>53.7</td><td>56.9</td></tr><tr><td>FCFF</td><td>70.0</td><td>74.2</td><td>78.7</td><td>83.4</td><td>88.4</td><td>93.7</td><td>99.3</td><td>105.3</td><td>111.6</td><td>118.3</td><td>125.4</td><td>132.9</td></tr></table></body></html>

6.0%

Firm A's Value \$3,50 o (us ing the Gordon growth model)

# Company B

ROI 20% b 15% WACC 8%

<html><body><table><tr><td>Firm B</td><td>Year 1</td><td>Year 2</td><td>Year 3</td><td>Year 4</td><td>Year 5</td><td>Year 6</td><td>Year 7</td><td>Year 8</td><td>Year 9 Year 10</td><td></td><td>Year 11 Year 12</td><td></td></tr><tr><td>NOPAT</td><td>100.0</td><td>103.0</td><td>106.1</td><td>109.3</td><td>112.6</td><td>115.9</td><td>119.4</td><td>123.0</td><td>126.7</td><td>130.5</td><td>134.4</td><td>138.4</td></tr><tr><td>Net Investment</td><td>15.0</td><td>15.5</td><td>15.9</td><td>16.4</td><td>16.9</td><td>17.4</td><td>17.9</td><td>18.4</td><td>19.0</td><td>19.6</td><td>20.2</td><td>20.8</td></tr><tr><td>FCFF</td><td>85.0</td><td>87.6</td><td>90.2</td><td>92.9</td><td>95.7</td><td>98.5</td><td>101.5</td><td>104.5</td><td>107.7</td><td>110.9</td><td>114.2</td><td>117.7</td></tr></table></body></html>

I Annual growth rate in NOPAT & FCFF 3.0 % Firm B's Value \$1,70 o (using the Gordon growth model)

Result 2: For the same return on capital, a faster growing firm would be worth more than a slow growing firm. Until Year 7, Firm A, the faster growing firm generates lower FCFF than firm B, the slower growing firm. Firm A also reinvests more than Firm B.

# Growth in NOPAT

In the above example, growth in NOPAT is given by:

$$
G_{t}={\frac{N O P A T_{t}-N O P A T_{t-1}}{N O P A T_{t-1}}}
$$

$$
{\begin{array}{r l}&{g_{t}={\frac{N O P A T_{t}-N O P A T_{t-1}}{I_{t-1}}}\times{\frac{I_{t-1}}{N O P A T_{t-1}}}}\ &{\qquad=R O I_{t}\times b_{t-1}}\end{array}}
$$

Where $\mathrm{NOPAT_{\mathrm{t}}-N O P A T_{\mathrm{t}-1}}$ is the profit from new investment, $\mathrm{ROI_{t}}$ is the return on net new investment, $\mathrm{I}_{\mathrm{t}-1}$ is the new investment made at the beginning of the year, and $\mathbf{b}_{\mathrm{t}-1}$ is the reinvestment rate. In the steady state, $\mathbf{b}_{\mathrm{t-1}}=\mathbf{b}_{\mathrm{t}}=\mathbf{b}$ and $\mathrm{ROI_{t}=}$ $\mathsf{R O I}_{\mathsf{t}-1}=\mathsf{R O I}$ then:

$$
G=b\times R O I
$$

Where $g$ is referred to as the sustainable growth rate. Thus, a firm can increase its growth rate by:

Improving its return on investments (ROI) (both new and existing assets). E.g.: efficiency improvements. Investing more capital (b) in projects with high return on investment. E.g.: expanding markets.

# Practical implementation of the FCFF valuation model

The free cash flow model is implemented as follows in practice to compute total enterprise value:

$$
V_{0}=\sum_{t=1}^{T}\frac{E\bigl (F C F F_{t}\bigr)}{\bigl (1+W A C C\bigr)^{t}}+\frac{T V_{T}}{\bigl (1+W A C C\bigr)^{T}}
$$

Where $\mathrm{TV}_{\mathrm{T}}$ is the continuing value in period T for the FCFF valuation model (see Chapter 10 of KGW).

# Three stage valuation

1. High Growth: High return on investment (ROI), High reinvestment rate (b), High growth $(\mathrm{g})$ in sales and profits.

2。 Transition: Competition drives down ROI on existing and new assets. Firm faces declining investment opportunities (fewer positive NPV projects) leading to lower reinvestment rates. 2 Declining reinvestment rates and ROI are accompanied by declining growth.

3. Mature: Firm reaches a steady state with constant growth, ROI, and reinvestment rates. New investments are likely to earn just the cost of capital.

We will use this intuition in our implementation of the valuation model.

# Continuing value based on the Gordon Growth Model

Free cash flows (FCFF) grow at a constant rate $g$ after $\mathrm{T}{+}1$ .The PV of cash flows after $\mathrm{T}$ as of time T:

$$
T V_{T}=\frac{F C F F_{T+1}}{W A C C-g}
$$

Since $\mathrm{FCFF_{T+1}}=\mathrm{NOPAT_{T+1}}(1-\mathrm{b})$ (see equation 8) where b is the steady-state reinvestment rate starting in year $\mathrm{T}{+}1$

$$
T V_{T}={\frac{N O P A T_{T+1}(1-b)}{W A C C-g}}
$$

In the steady-state, from the sustainable growth model (eq. 9):

$$
\mathbf{\mu}_{\mathbf{g}}=\mathbf{\epsilon}~\mathbf{b}\times\mathbf{ROI}
$$

Where $g$ is the steady-state growth in profits and ROI is the steady-state return on new investments.

· What would be a good choice for steady-state growth?

· What would be a good choice for steady-state ROI?

# Terminal value based on value drivers

From equation (13), $\mathbf{b}=\mathbf{g}/\mathrm{ROI}$ . Substitute this into equation (12):

$$
T V_{T}={\frac{N O P A T_{T+1}(1-g/R O I)}{W A C C-g}}
$$

Equation (14) is the value-driver based terminal value formula.

# No Growth Perpetuity Continuing Value Formula

Suppose the return on new investments equals cost of capital, i.e., $\mathrm{ROI}=\mathrm{WACC}$ .Substitute $\mathrm{ROI}=\mathrm{WACC}$ in equation (14):

$$
\begin{array}{l} {{T V_{T}=\displaystyle\frac{N O P A T_{T+1}(1-g/W A C C)}{W A C C-g}} }\ {{\displaystyle=\frac{N O P A T_{T+1}} {W A C C-g}\times\frac{W A C C-g}{W A C C}=\displaystyle\frac{N O P A T_{T+1}}{W A C C}}}\end{array}
$$

We get the perpetuity formula for the no-growth case.

This doesn't mean that there is no nominal growth in earnings simply that any such growth does not add to value.

We will use the more general formula in equation (14), which gives us the option to set ROI ≥ WACC.
# Three-Stage FCFF Valuation Model

This model is used to compute the total enterprise value (value of operating assets) of the firm. The model contains three stages. They are:

1) High Growth Stage: (2 years) marked by high NOPAT growth, high reinvestment rates, and high return on investment. 2) Transition Stage: (15 years from Year 2 to Year 17) marked by mean-reversion where growth rates, reinvestment rates, and return on investment all decline to a long run steady state. 3) Steady State: (forever from Year 17) marked by steady-state equilibrium where growth, reinvestment rate, and return on investment settle into long run steady state.

# Inputs to the Model

1) Year O NOPAT and Year O Invested Capital.
2) Growth forecasts (g) and reinvestment rate (b) for the high growth stage.
3) Steady state growth $(\mathrm{g})$ and return on investment (ROI)
4) Weighted average cost of capital (WACC).
5) Year O book value (ideally market value) of debt and preferred stock, excess cash, shares outstanding and current stock price.

See Worksheet (9) for the FCFF model to value the firm in the EXCEL workbook Smucker-July 2015 version 7.0. Xls.

# 15-Year Valuation Model

We combine all these elements together and provide the following implementation:

$$
V_{0}=\sum_{t=1}^{T}\frac{N O P A T_{t}\times (1-b_{t})}{\left (1+W A C C\right)^{t}}+\frac{N O P A T_{T+1}\times (1-g/R O I)}{\left (1+W A C C\right)^{T}\times\left (W A C C-g\right)}
$$

${\begin{array}{r l} {{\mathrm{VOPAT}} _{\mathrm{t}}={\mathrm{Net~Operating~Profits~After~Taxes~for}}}\ {\mathbf{\uprho}_{\mathrm{t}}}&{={\mathrm{Reinvestment~rate~for~year~\cdot~t'}}.}\ {{\mathrm{VACC}} }&{={\mathrm{Weighted~Average~Cost~of~Capital}}.}\ {\mathbf{\uprho}}&{={\mathrm{Steady-state~growth~in~NOPAT~and~ca}}}\ {{\mathrm{QOI}} }&{={\mathrm{Steady-state~ROI}}\geq{\mathrm{WACC}}.}\ {\mathbf{\uprho}}&{={\mathrm{Number~of~years~of~explicit~NOPAT~f~}}}\end{array}}$ year 't'. B 8 sh flows. 7 orecasts. WW will implement the model with $\mathrm{T}{=}15$ years.

$$
E\big (F C F F_{t}\big)=N O P A T_{t}\times (1-b_{t})
$$

$$
N O P A T_{t+1}=N O P A T_{t}\times (1+g_{t+1})
$$

Growth rate declines exponentially (or linearly in logs) from $(\mathrm{g}2)$ in Year 2 to steady-state growth $(\mathrm{g})$ in Year 17. For $\mathfrak{t}=2$ to 15:

$$
\begin{array}{c}{g_{t+1}=g_{t}\times\operatorname{EXP}\left[\log\left (g\slash g_{2}\right)/T\right]}\ {b_{t}=b_{t-1}-\displaystyle\frac{b_{1}-b}{T}}\end{array}
$$
# Reinvestment Rates for the High Growth Stage

Reinvestment rates are computed as follows:

Reinvestment rate $(\mathrm{b})=(1-\mathrm{FCFF/NOPAT})$ . FCFF/NOPAT is capacity payout all investors (for NOPAT $>0$ 一

# Sequential Valuation of Equity

Given total firm value, equity is valued sequentially as follows:

$\mathrm{E}=\mathrm{V}$ alue of the Firm - Value of Pref. Stock & Min. Int. -Value of Debt

# Assets-in-place and PVGO

Total Enterprise Value $(\mathrm{V})=$ Value of assets-in-place + Present Value of Growth Opportunities (PVGO)

Value of assets-in-place $=$ NOPAT 1/WACC . Value of assets-inplace is simply the no-growth value (earnings power value, EPV).

Whether growth is value adding, value neutral or value destroying depends on whether $\mathrm{ROI}>\mathrm{WACC}$ $\mathrm{ROI}=\mathrm{WACC}$ Or $\mathrm{ROI}<\mathrm{WACC}$

PVGO = V - Value of assets in place.
# Value Drivers and Direct Valuation of Equity

We can value equity directly using the same analytical approach that we used to compute the total enterprise value by making the following substitutions.

<html><body><table><tr><td>Value Firm</td><td>Value Equity</td></tr><tr><td>NOPAT</td><td>EPS (earnings per share)</td></tr><tr><td>FCFF</td><td>FCFE</td></tr><tr><td>Return on Invested Capital, ROIC</td><td>Return on Equity, ROE</td></tr><tr><td>Reinvestment Rate, b</td><td>Plowback Rate, k</td></tr><tr><td>Growth in NOPAT, g</td><td>Growth in EPS, g</td></tr><tr><td>WACC</td><td>Cost of Equity, re</td></tr><tr><td>Return on new Investments, ROI</td><td>Return on new equity i investments. ROE*</td></tr></table></body></html>

The plowback rate $\mathbf{\nabla}^{6}\mathrm{k}^{\circ}$ represents the proportion of net income that is retained in the firm. Thus:

For Net Income $>0$ $\mathbf{\nabla}^{6}\mathrm{k}^{\circ}$ is computed from historical data as:

$$
\mathrm{k}=1-(\mathrm{FCFE/NetIncome})
$$

(FCFE/Net Income) is the payout capacity since this represents the firm's capacity to pay its shareholders.

We could use actual payout (dividends $+$ net stock repurchase).

# Free Cash Flow to Equity (FCFE) Valuation Model

$$
V_{E}=\sum_{t=1}^{T}\frac{F E_{t}\times (1-k_{t})}{\left (1+r_{e}\right)^{t}}+\frac{F E_{T+1}\times (1-g/R O E^{*})}{\left (1+r_{e}\right)^{T}\times\left (r_{e}-g\right)}
$$

FE stands for forecast earnings per share and $\mathrm{ROE^{*}}$ is the return on new equity investments. This approach is referred to as the directvaluationof equity.

The three-stage model to value equity directly is provided in worksheet (10) in the EXCEL workbook Smucker-July 2015 version 7.0. Xls.

# Data needed for implementing the equity valuation model

> Analyst consensus earnings forecasts for the first two years (FY 1 and FY 2)
> Plowback rates for the first stage
> Long-run steady-state growth and ROI
> Beta, market risk premium, and risk-free rate
Number of shares outstanding
Book (market) value of interest-bearing debt, preferred stock
> Cash and short-term investments

Mucker (SJM) EPS forecasts (as of August 19, 2022 FV 2
<html><body><table><tr><td colspan="4">FY 1</td><td rowspan="2">Next Year</td></tr><tr><td>Earnings Est</td><td>Current Qtr. Jul 15</td><td>Next Qtr. Oct 15</td><td>Current Year Apr 16</td></tr><tr><td>Avg. Estimate</td><td>1.23</td><td>1.54</td><td>5.72</td><td>6.31</td></tr><tr><td>No. Of Analysts</td><td>15.00</td><td>15.00</td><td>16.00</td><td>17.00</td></tr><tr><td>Low Estimate</td><td>1.02</td><td>1.43</td><td>5.65</td><td>5.92</td></tr><tr><td>High Estimate</td><td>1.33</td><td>1.60</td><td>5.80</td><td>6.60</td></tr><tr><td>Year Ago EPS</td><td>1.34</td><td>1.53</td><td>5.38</td><td>5.72</td></tr></table></body></html>

http://finance.yahoo.com/q/ae?s $\:=\:$ SJM $+.$ Analyst+Estimates

# Estimating 12 month and 24 month ahead forecasts

As of August 19, 2022, FY 1 is only an eight-month forecast. Trailing 12-month earnings consists 8/12 of $\mathrm{EPS}_{0}$ and 4/12 of $\mathrm{FY}_{1}$ . Next 12 month earnings consist 8/12 of FY 1 and 4/12 of FY 2. Let $\Nu=$ number of months to the next fiscal year-end (April 2016); Thus, $_{\mathrm{N}=8}$

Trailing 12-month earnings, $\mathrm{FE}_{0}$ and 12-month ahead forecast, FE 1
$\mathrm{FE}_{0}=\mathrm{EPS}_{0}*(\mathrm{N}/12)+\mathrm{FY}_{1}*(1-\mathrm{N}/12)$
$\mathrm{FE}_{0}=5.38\mathrm{~}^{\ast}\: (8/12)+5.72\mathrm{~}^{\ast}\: (1-8/12)=\mathbb{5}5.49$

$\mathrm{FE}_{1}=\mathrm{FY}_{1}*(\mathrm{N}/12)+\mathrm{FY}_{2}*(1-\mathrm{N}/12)$ $\mathrm{FE}_{1}=5.72*(8/12)+6.31*(1{-}8/12)=\S 5.92$ $\mathrm{g}_{2}=\mathrm{FY}2/\mathrm{FY}1-1=5.92/5.49-1=7.8\%$ $\mathrm{FE}_{2}=\mathrm{FE}_{1}\mathrm{*}(1\mathrm{+}\mathrm{g}_{2})=5.92\mathrm{*}1.078=\S 6.38$
# Smucker beta and market cap

<html><body><table><tr><td colspan="3">The J. M. Smucker Company (SJM) - NYSE Watchlist 111.88 ±2.91 (2.67%) 4:02PM EDT After Hours : 111.88 0.00 (0.00%) 4:16PM EDT - Nasdaq Real Time Price</td></tr><tr><td>Prev Close: 108.97</td><td>Day's Range:</td><td>110.32 -112.91</td></tr><tr><td>Open: 110.63</td><td>52 wk Range:</td><td>95.60 -120.65</td></tr><tr><td>:p! 8 112.03 x 200</td><td>Volume:</td><td>1,375,400</td></tr><tr><td>Ask. 112.07 x 600</td><td>Avg Vol (3 m):</td><td>817,120</td></tr><tr><td>1 y Target Est: 121.11</td><td>Market Cap:</td><td>13.39 B</td></tr><tr><td>Beta:</td><td>1.22 P/E (ttm):</td><td>33.64</td></tr><tr><td>Next Eanings Date: 27-Aug-15 自</td><td>EPS (ttm):</td><td>3.33</td></tr><tr><td></td><td>Div & Yield:</td><td>2.68 (2.50%)</td></tr></table></body></html>

You can also get shares outstanding, financial statements for three years, and other key statistics from Yahoo Finance.

http://finance.yahoo.com/q/ks?s $=$ SJM+Key+Statistics

This is a screen capture from August 19, 2022. The current beta and market cap can be obtained from the same link. All of the data in the worksheets are as of July 2015.
# Other data

Balance sheet data
Cash $=$ Cash & cash equivalents & Short-term Inv. $=$ \$0.1256 billion.
Debt $=$ Long-term debt $+$ Short-term debt \$6.171 billion.

Shares outstanding $=$ 0.11967 billion

Cost of Equity for Smucker using CAPM

As of July 2015, it was $9.74\%$

Plowback rate in Stage 1

From worksheet 4: Average payout ratio over the last 10 years is about 1. The current payout ratio is 0.81. This gives a plowback rate range of 0 to 0.19. I use the higher number. You can take the most recent number, average it over 5 years, etc. It is your choice.

Steady-state information
Steady-state growth $=3\%$ (assume nominal GDP growth)
Steady-stateROI $\mathrm{\Lambda}=\mathrm{Cost}$ of equity, $9.74\%$
Steady-state plowback rate, $\mathrm{k}=\mathrm{g}/\mathrm{ROI}=0.03/0.0974=0.31$

Smucker intrinsic value $=\$83.59$ per share Current price $(\mathrm{July~8}, 2022)=\$108.46$ per share P/V ratio $=108.46/83.59=1.30$ (overvalued by $30\%$
# Year T Year T+1

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">2015 Year 0</td><td rowspan="2">2016 Year 1</td><td rowspan="2">2017 Year 2 Stage 1: High Growth</td><td rowspan="2">2018 Year 3</td><td rowspan="2">2019 Year 4</td><td rowspan="2">2020 2021 Year 5</td><td rowspan="2">2022 Year 6 Year 7</td><td rowspan="2"></td><td rowspan="2">2023</td><td rowspan="2">2024</td><td rowspan="2">2025 Year 10 Year 11</td><td rowspan="2">2026</td><td rowspan="2">2027 Year 12 Year 13 Year 14</td><td rowspan="2">2028</td><td rowspan="2">2029 Year 15</td></tr><tr><td>Year 8 Year 9</td></tr><tr><td></td><td></td><td></td><td>8.7%</td><td>8.1%</td><td>7.5%</td><td>7.0%</td><td>6.5%</td><td>6.1%</td><td>5.7%</td><td>5.3%</td><td>Stage 2: Transition 4.9%</td><td>4.6%</td><td>4.3%</td><td>4.0%</td><td>3.7%</td><td>Sto 3.5%</td></tr><tr><td>b 0 k</td><td>0.19</td><td>0.19</td><td>0.20</td><td>0.21</td><td>0.21</td><td>0.22</td><td>0.23</td><td>0.24</td><td>0.25</td><td>0.25</td><td>0.26</td><td>0.27</td><td>0.28</td><td>0.28</td><td>0.29</td><td>0.30</td></tr><tr><td>EPS</td><td>5.44</td><td>5.82</td><td>6.33</td><td>6.88</td><td>7.40</td><td>7.92</td><td>8.43</td><td>8.95</td><td>9.46</td><td>9.96</td><td>10.45</td><td>10.93</td><td>11.40</td><td>11.85</td><td>12.29</td><td>12.72</td></tr><tr><td>Net New Equity Investments</td><td>1.03</td><td>1.11</td><td>1.25</td><td>1.41</td><td>1.58</td><td>1.75</td><td>1.93</td><td>2.12</td><td>2.32</td><td>2.52</td><td>2.73</td><td>2.94</td><td>3.15</td><td>3.37</td><td>3.59</td><td>3.82</td></tr><tr><td>FCFE</td><td>4.40</td><td>4.71</td><td>5.07</td><td>5.46</td><td>5.82</td><td>6.16</td><td>6.50</td><td>6.83</td><td>7.14</td><td>7.44</td><td>7.72</td><td>7.99</td><td>8.24</td><td>8.48</td><td>8.70</td><td>8.90</td></tr><tr><td>Growth in FCFE</td><td></td><td>7.1%</td><td>7.6%</td><td>7.6%</td><td>6.5%</td><td>6.0%</td><td>5.5%</td><td>5.0%</td><td>4.6%</td><td>4.2%</td><td>3.8%</td><td>3.5%</td><td>3.2%</td><td>2.9%</td><td>2.6%</td><td>2.3%</td></tr><tr><td>Book Value Per Share</td><td>59.27</td><td>60.38</td><td>61.63</td><td>63.04</td><td>64.62</td><td>66.38</td><td>68.31</td><td>70.43</td><td>72.75</td><td>75.27</td><td>77.99</td><td>80.93</td><td>84.08</td><td>87.45</td><td>91.04</td><td>94.86</td></tr><tr><td>ROE</td><td></td><td>9.8%</td><td>10.5%</td><td>11.2%</td><td>11.7%</td><td>12.2%</td><td>12.7%</td><td>13.1%</td><td>13.4%</td><td>13.7%</td><td>13.9%</td><td>14.0%</td><td>14.1%</td><td>14.1%</td><td>14.1%</td><td>14.0%</td></tr><tr><td>ROI</td><td></td><td>37.1%</td><td>45.8%</td><td>44.0%</td><td>36.7%</td><td>32.9%</td><td>29.6%</td><td>26.6%</td><td>24.0%</td><td>21.6%</td><td>19.5%</td><td>17.6%</td><td>15.9%</td><td>14.4%</td><td>13.1%</td><td>11.8%</td></tr><tr><td>RI (Residual Income)</td><td></td><td>0.05</td><td>0.45</td><td>0.87</td><td>1.26</td><td>1.62</td><td>1.97</td><td>2.30</td><td>2.60</td><td>2.87</td><td>3.12</td><td>3.33</td><td>3.51</td><td>3.66</td><td>3.77</td><td>3.85</td></tr><tr><td>(ROE -re)</td><td></td><td>0.1%</td><td>0.7%</td><td>1.4%</td><td>2.0%</td><td>2.5%</td><td>3.0%</td><td>3.4%</td><td>3.7%</td><td>3.9%</td><td>4.1%</td><td>4.3%</td><td>4.3%</td><td>4.4%</td><td>4.3%</td><td>4.2%</td></tr><tr><td colspan="3">DiscountedFreeCashFlowValuation</td><td colspan="9"></td><td colspan="5"></td></tr><tr><td colspan="8">PV of FCFE during thefirst 15 years 50.16 Book Value of Equity 33.42</td><td colspan="7">Discounted Residual Income (EVA for shareholders) Valuation $59.27</td><td colspan="2"></td></tr><tr><td colspan="8">Continuing value based on cash flows beyond Year 15 Intrinsic Value of Equity per share</td><td colspan="7">$14.42</td><td colspan="4"></td></tr><tr><td></td><td colspan="4">$83.59 $108.46 Intrinsic Value of Equity per share</td><td colspan="7">PV of Residual Income during the first 15 years Continuingvalue based onResidual Incomebeyondyear 15</td><td colspan="5">$9.90</td><td colspan="4" rowspan="3"></td></tr><tr><td colspan="8">Price Per Share</td><td colspan="6">$83.59</td></tr><tr><td colspan="2">P/V</td><td colspan="3">1.30</td><td colspan="6"></td><td colspan="5"></td><td colspan="5"></td></tr><tr><td colspan="8"></td><td colspan="6"></td><td colspan="5"></td></tr><tr><td colspan="10">Value of assets-in-place and PVGO Value of equity inbillions of S</td><td colspan="5"></td><td colspan="5">$10.00</td></tr><tr><td colspan="8">Value of assets-in-place $59.75 $23.83</td><td colspan="5"></td><td colspan="5">$6.17</td><td colspan="4"></td></tr><tr><td colspan="8">PVGO</td><td colspan="4">Value of debt (use bookvalue), billions of S Value of preferred stock（usebookvalue), billionsofS</td><td colspan="5"></td><td colspan="5">$0.00</td></tr><tr><td colspan="8">IntrinsicValue of Equity per share</td><td colspan="5">Total FirmValue, billionsof S</td><td colspan="5">$16.17</td><td colspan="5"></td></tr><tr><td colspan="8"></td><td colspan="5"></td><td colspan="5">S 16.05</td><td colspan="5"></td></tr><tr><td colspan="8"></td><td colspan="5"></td><td colspan="5"></td><td colspan="5"></td></tr></table></body></html>

# Sensitivity Analysis

Examine how your valuations change when you adjust your key assumptions, for example you can test how Low Estimate and High Estimate of earnings forecasts affect your valuations.

You can examine the sensitivity of your analysis to your cost of capital estimates and the payout ratios.

# Distressed Firms

Even if trailing earnings are negative, as long as the firm has positive earnings forecasts, you can still use the model.

If both FY 1 and FY 2 forecasts are negative, then it is hard to perform DCF valuation.

If NOPAT is negative, you can use a normalized NOPAT (average or median of the prior 5 or 10 years).

# Lecture Note 4 Discounted Cash Flow Valuation: EVA and Discounted EVA Models

# Objective

Introduce students to the concept of economic profits, valuation models based on economic profits and their relation to the free cash flow model.

# Outline

· Economic Profits vs. Accounting Profits
●Return on Invested Capital (ROIC)
Economic profit definition and practical aspects of computation
· ROIC Tree
· An example involving Smucker
Valuation model based on economic profits to compute total enterprisevalue
· Terminal value computation
Valuing equity based on economic profits/residual income

# Economic Profits Vs Accounting Profits

Economic profits refer to excess profits over and above the minimum profits a firm is expected to earn for its investors.

Thus, in computing economic profits, the minimum profits expected by the investors in return for the use of their capital (the opportunity cost of giving their capital to the firm for its use) is considered an expense.

Similar to a firm paying rent for leasing a warehouse from someone, we have economic rent for the use of capital.

Economic profits are also referred to as Economic Value Added (EVA) (the term popularized by Stern Stewart).

# Return on Invested Capital (ROIC)

While the return on new investment (ROl) is theoretically very appealing, it is not easily available. Typically, the ROI is likely to be available only to analysts inside the firm and even then not too precisely.

There is an alternate measure that computes the return on all existing operating assets of $\mathrm{\Delta}a$ firm referred to as the return on invested capital (ROIC). The return on invested capital is defined as:

$$
R O I C=\frac{N O P A T_{t}}{I C_{t-1}}
$$

Where NOPATt is the net operating profits after taxes and $\mathrm{IC}_{\mathrm{t}-1}$ is the (beginning of year) invested capital defined as the sum of operating working capital and net fixed and long-term operating assets.

· ROIC is relatively easy to compute for individual firms and even divisions of individual firms.
· ROIC is also a better measure of the operating performance of a firm than either ROA (return on assets) or ROE (return on equity).

# EVA definition

EVA is a flow measure computed each year and is defined as follows:

$$
\begin{array}{l}{E V A_{t+l}=(N O P A T_{t+l}-W A C C\times I C_{t})}\ {E V A_{t+l}=(R O I C_{t+l}-W A C C)\times I C_{t}}\end{array}
$$

$\mathrm{IC_{t}}$ is the beginning of the period invested capital, $\mathrm{NOPAT}_{\mathrm{t+l}}$ is the net operating profits after taxes for period $_{\mathrm{t}+1}$ , and $\mathrm{ROIC}_{\mathrm{t+1}}$ is the return on invested capital for period $_{\mathrm{t+1}}$

Equation (3) facilitates setting an EVA target in terms of returns. For instance, the return target could be $2\%$ in excess of cost of capital.

EVA can improve, if:

The return on existing capital base improves or the cost of capital declines.
More capital is invested in new projects that earn a return higher than cost of capital.
Capital invested in projects earning return lower than cost of capital (negative NPV projects) is liquidated or reassigned t more profitable projects.

# How to measure invested capital?

Book values: Book values represent historical values and, therefore, can be distorted by inflation. Profits are in this year's dollars while book values are in past dollars. In high inflation environments, this could distort ROIC measures. Market Value of Used Assets: This is appropriate only when the market value of used assets is substantially higher than their historical book value (e.g.: real estate, airplanes). In most cases, the market value of used assets is lower. Therefore, using book values is not likely to introduce significant distortions. Replacement cost: Using replacement cost of assets ignores the fact that it may not be economically justifiable to replace the assets. An existing firm in the industry that built a plant several years ago at a lower (real) cost does have a competitive advantage over new entrants, who have to achieve the same productive capacity at a higher cost. This advantage should be reflected in its return on investment.

In sum, using book values may be appropriate in most situations.

# Invested capital with and without goodwill

Compute invested capital (and the return on invested capital, ROIC) both with and without goodwill in EVA calculations.

Including goodwill in invested capital allows you to determine how well the company is using investor funds.

Excluding goodwill allows you to measure the performance of the operating assets of the company.

In situations in which a company overpaid for an acquisition, the ROIC including goodwill can often be substantially lower than ROIC excluding goodwill.

Invested Capital (without good will) $=$ Net Fixed Assets $+$ Net long-term operating assets $+$ Net Working Capital

Invested Capital (with good will) $\begin{array}{r} {{}=\mathrm{Net}} \end{array}$ Fixed Assets $+$ Net long-term operating assets $+$ Net Working Capital $+$ Good Will & Intangible Assets

Note: Net long-term operating assets are net of long-term operating liabilities.
# ROIC Tree

The return on invested capital can be broken down into two components providing further intuition into the value drivers of thebusiness:

$$
\mathit{R O I C}_{t}=\frac{\mathit{N O P A T}_{t}}{\mathit{I C}_{t-1}}=\begin{array}{l l l l}&{\frac{\mathit{N O P A T}_{t}}{\mathit{S a l e s}_{t}}}&{\times}&{\frac{\mathit{S a l e s}_{t}}{\mathit{I C}_{t-1}}}\end{array}
$$

This is just the Du Pont decomposition from your accounting classes. The ratios given here can be further disaggregated into more detailed financial ratios (see pages 166-168 in KGW text book).

Operating margin measures how effectively the company converts revenues to profits.
Capital turnover measures how effectively the company employs its invested capital.

These ratios could be used to understand a firm's operating strategy.

Example: Wholesalers typically have slim margins but high turnover. Car companies, on the other hand, have high margins and low turnover.

# An Example Involving Smucker (see worksheet 5)

<html><body><table><tr><td colspan="7">Economic Value Added and Value Drivers</td><td>WACC</td><td>7.2%</td><td></td></tr><tr><td></td><td colspan="3"></td><td colspan="2">(based on the income statement and the statement of cash flows)</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="5">Millions - Detail U.S. Dollars</td><td></td><td>2014</td><td>2013</td><td>2012</td><td>2011</td></tr><tr><td colspan="5">Net Fixed Assets & Other Long-Term Assets</td><td></td><td>1,870.20</td><td>1,410.50</td><td>1,294.30</td><td>1,230.10</td></tr><tr><td></td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">Goodwill &Intangibles</td><td></td><td></td><td></td><td>12,960.106,122.50</td><td></td><td>6,142.30 6,241.60</td><td></td></tr><tr><td></td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">All Long-term Ope rating Assets</td><td></td><td></td><td></td><td>14,830.30</td><td>7,533.00</td><td>7,436.607,471.70</td><td></td></tr><tr><td></td><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Other long-te rm ope rating liabilities</td><td></td><td></td><td></td><td></td><td>354.90</td><td>247.90</td><td></td><td>331.20</td><td>321.70</td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Operating Current Assets (rec & iny)</td><td colspan="3"></td><td></td><td></td><td>1,593.70</td><td>1,240.40</td><td>1,259.20</td><td>1,309.10</td></tr><tr><td colspan="3">OperatingCurrentLiabilities (payables andother)</td><td></td><td></td><td></td><td>796.60</td><td>542.60</td><td>546.80</td><td>566.90</td></tr><tr><td colspan="3">Net Working Capital</td><td></td><td></td><td></td><td>797.10</td><td>697.80</td><td>712.40</td><td>742.20</td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="6">Invested Capital (with goodwill and intangibles)</td><td>15,272.50</td><td>7,982.90</td><td>7,817.80</td><td>7,892.20</td></tr><tr><td colspan="6">Invested Capital (without goodwill and intangibles)</td><td>2,312.40</td><td>1,860.40</td><td>1,675.50</td><td>1,650.60</td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>NOPAT</td><td></td><td></td><td></td><td></td><td></td><td>589.22</td><td>626.58</td><td>631.21</td><td>579.30</td></tr><tr><td>FCFF</td><td></td><td></td><td></td><td></td><td></td><td>(595.78)</td><td>554.78</td><td>755.21</td><td>(130.48)</td></tr><tr><td colspan="3">Reinvestment Rate, b</td><td></td><td></td><td></td><td>201.1%</td><td>11.5%</td><td>-19.6%</td><td>122.5%</td></tr><tr><td colspan="3">Growth in NOPAT, g</td><td></td><td></td><td></td><td>-6.0%</td><td>-0.7%</td><td>9.0%</td><td>4.9%</td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">ROIC (with goodwill and intangibles)</td><td></td><td></td><td></td><td>7.4%</td><td>8.0%</td><td>8.0%</td><td>8.0%</td></tr><tr><td colspan="6">ROIC (without goodwill and intangibles)</td><td>31.7%</td><td>37.4%</td><td>38.2%</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>39.7%</td></tr><tr><td colspan="3">EVA (with goodwill and intangibles)</td><td></td><td></td><td></td><td>15.6</td><td>64.8</td><td>64.1</td><td>61.1</td></tr><tr><td colspan="2">ROIC - WACC</td><td></td><td></td><td></td><td></td><td>0.2%</td><td>0.8%</td><td>0.8%</td><td>0.8%</td></tr><tr><td></td><td colspan="2"></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="3">EVA (without goodwill and intangibles)</td><td></td><td></td><td></td><td>455.5</td><td>506.2</td><td>512.6</td><td>474.5</td></tr><tr><td colspan="3">ROIC - WACC</td><td></td><td></td><td></td><td>24.5%</td><td>30.2%</td><td>31.1%</td><td>32.5%</td></tr></table></body></html>

Let us examine the source of the decline in ROIC:

<html><body><table><tr><td colspan="5">ROIC Tree (components of ROIC)</td><td></td><td>2014 2013</td><td>2012</td><td>2011</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="7">After-tax operating profit margin, NOPAT (t)/Sales (t)</td><td>11.2%</td><td>10.7%</td><td>10.5%</td></tr><tr><td colspan="7">Inv. Cap. Turnover, Sales (t)/IC (t-1) (with good will)</td><td>0.71 0.72</td><td>0.75</td><td>0.77</td></tr><tr><td colspan="7">Working Capital Turnover, Sales (t)/WC (t-1)</td><td>8.16 7.88</td><td>7.95</td><td>7.62</td></tr><tr><td colspan="7">Receivables Turnover, Sales (t/Receivables (t-1)</td><td>18.40 17.89</td><td>16.97</td><td>16.04</td></tr><tr><td colspan="7">Inventory Turnover, Sales (t)/Inventory (t-1)</td><td>5.93</td><td>6.13</td><td>6.40</td></tr><tr><td colspan="6">Net Fixed Assets Turnover, Sales (t)/Net Fixed Assets (t-1)</td><td>6.11 4.04 4.33</td><td></td><td>4.79</td><td>5.91</td></tr><tr><td colspan="6">All Long-term Assets Turnover, Sales (t/LT Assets (t-1)</td><td>0.76</td><td>0.75</td><td>0.79</td><td>0.83</td></tr></table></body></html>

Decline in net fixed asset turnover ratios has led to a decline in ROIC.

# Sustainable growth rate calculations

<html><body><table><tr><td colspan="7">Average ROIC (with good will & intangibles) over the last 10 years</td></tr><tr><td colspan="5">Average ROIC (without good will & intangibles) over the last 10 years</td><td></td><td>9.1% 37.4%</td></tr><tr><td colspan="6">Average Reinvestment Rate over the last 10 years</td><td></td><td>70.4%</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>Sustainable growth (with good will & intangibles) based on 10 year mean</td><td></td><td></td><td>6.4%</td></tr><tr><td>Sustainable growth (w/o good will & intangibles) based on 10 year mean</td><td></td><td></td><td></td><td></td><td></td><td></td><td>26.3%</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Compounded (geometric) average growth in NOPAT over the last 10 years</td><td></td><td></td><td></td><td></td><td></td><td></td><td>11.3%</td></tr></table></body></html>

# Discounted EVA Valuation Model

The following equation shows how economic profits are related to current total enterprise value of the firm:

Equation (5) breaks-up value into invested capital plus the present value of forecasted future economic profits (EVA).

Recall from our earlier discussion:

$$
F C F F_{t}=N O P A T_{t}-I_{t}
$$

Where $\mathrm{I_{t}}$ is the net new investment made by the firm each period out of its NOPAT. Thus, the invested capital base of the firm increases each period by the net new investments made by the firm:

$$
I C_{t}=I C_{t-1}+I_{t}
$$

Where $\mathrm{I_{t}}$ is the net new investment.

# Characteristics of the EVA Valuation Model

·The FCFF valuation model and the EVA valuation model are mathematically equivalent; they are just two ways of expressing the same value.

A change in $I C_{\theta}$ independent of any economic change in a firm's investment policy or cash flows will have no effect on firm value.

# NPV and EVA

Recall the definition of NPV of a project, $N P V=V_{0}-I_{0}$ where ${\mathrm{V}}_{0}$ is the present value of free cash flows of the project and $\mathrm{I}_{0}$ is the initial (new) investment. Then:

$$
V_{0}=\underbrace{I_{0}}_{\searrow}\qquad+\underbrace{N P V}_{\hdots}.
$$

Thus the present value of all future EVA from equation (5) is to a firm what NPV is to a project. They both represent value added to the shareholders.

# EVA valuation model is equivalent to the FCFF model

Perpetuity Case: Let us prove this for the case in which future economic profits are a constant perpetuity.

This implie $\mathrm{{s}(N O P A T_{1}-W A C C\times I C_{0})=(N O P A T_{2}-}$ $\mathrm{WACC}\times\mathrm{IC}_{1})=(\mathrm{NOPAT}_{3}-\mathrm{WACC}\times\mathrm{IC}_{2}):$ and so on.

$$
V_{0}=I C_{0}+\sum_{t=1}^{\infty}\frac{E\big (N O P A T_{1}-W A C C\times I C_{0}\big)}{\big (1+W A C C\big)^{t}}
$$

The second term on the RHS of (9) is the present value of a perpetuity. Therefore:

$$
{\begin{array}{r l}&{V_{0}=I C_{0}+{\cfrac{N O P A T_{1}-W A C C\times I C_{0}}{W d C C}}}\ &{\quad=I C_{0}+{\cfrac{N O P A T_{1}}{W A C C}}-{\cfrac{W A C C\times I C_{0}}{W A C C}}}\ &{\quad=I C_{0}+{\cfrac{N O P A T_{1}}{W A C C}}-I C_{0}}\ &{\quad={\cfrac{N O P A T_{1}}{W A C C}}}\end{array}}
$$

This is just the present value of perpetuity for the FCFF model.

(A more general proof is available on request)
# Practical Implementation of the EVA Valuation Model

The EVA valuation model:

$$
\begin{array}{l} {{V_{0}=I C_{0}+\displaystyle\sum_{t=1}^{T}\frac{E\big[N O P A T_{t}-W A C C\times I C_{t-1}\big]}{\big(1+W A C C\big)^{t}} }}\ {{\quad+\displaystyle\frac{T E V_{T}} {\big (1+W A C C\big)^{T}}}}\end{array}
$$

where TEV is the PV of economic profits beyond year T.

$$
\begin{array}{l} {{T E V_{T}=\displaystyle\frac{N O P A T_{T+1}-W A C C\times I C_{T}} {W A C C}}}\ {{\displaystyle+\frac{N O P A T_{T+1}(g/R O I)(R O I-W A C C)}{W A C C(W A C C-g)}} }\end{array}
$$

Where ROI is the return on new investment in the steady state and $\ '_{\mathrm{g}}$ is the steady state growth.

The first term on the right hand side is the PV of constant EVA in perpetuity from assets in place as of year T. The second term is the PV of incremental economic profits from new investments after T. The second term is also referred to as the present value of growth opportunities (PVGO).

# Perpetual no-growth terminal economic value

In the steady state, if $\mathrm{ROI}=\mathrm{WACC}$ then the second term on the right hand side of equation (11) equals zero and the terminal economic value is equal to:

$$
T E V_{T}=\frac{N O P A T_{T+1}-W A C C\times I C_{T}}{W A C C}
$$

# Terminal value of the FCFF model and the terminal value of the EVA model

The terminal value for the free cash flow model is the sum of the terminal economic value of the economic profit model plus the invested capital at T.

$$
\mathrm{TV_{T}=T E V_{T}+I C_{T}}
$$

This relationship should hold for any period 't' in the future.

# See worksheet 9 in Smucker-July 2015 version 7.0. Xls

All these formulas are embedded in the worksheets.

# EVA Model for Direct Valuation of Equity

We can value equity directly using earnings per share (EPS) forecasts.

<html><body><table><tr><td>Value Firm</td><td>Value Equity</td></tr><tr><td>NOPAT</td><td>EPS (earnings per share)</td></tr><tr><td>FCFF</td><td>FCFE</td></tr><tr><td>Return on Invested Capital, ROIC</td><td>Return on Equity, ROE</td></tr><tr><td>Reinvestment Rate, b</td><td>Plowback Rate, k</td></tr><tr><td>Growth in NOPAT, g</td><td>Growth in EPS, g</td></tr><tr><td>Invested Capital ICt = ICt-1 + b*NOPAT</td><td>Book Value per Share Bt = Bt-1 + k*EPSt</td></tr><tr><td>EVA</td><td>Residual Income (RI)</td></tr><tr><td>WACC</td><td>Cost of Equity, re</td></tr><tr><td>Return on new investments, ROI</td><td>Return on new equity investments, ROE*</td></tr></table></body></html>

# Residual Income Model/EVA Model to Value Equity

$$
V_{E}=\underbrace{B_{0}}_{B o o k E q u i t\nu}+\sum_{t=1}^{\infty}\frac{E\big (F E_{t}-r_{e}\times B_{t-1}\big)}{\big (1+r_{e}\big)^{t}}
$$

FE stands for Forecast Earnings Per Share. The EVA model to value equity is often referred to as the EBO model in accounting.

The free cash flow model and the residual income/EBO model are identical models.
# Continuing values for the residual income model

$$
T E V_ {{\scriptscriptstyle T}} =\frac{F E_ {{\scriptscriptstyle T}+1}-r_{e}\times B_{{\scriptscriptstyle T}} }{r_{e}}+\frac{F E_{{\scriptscriptstyle T}+1}(g/R O E^{*})(R O E^{*}-r_{e})}{r_{e}(r_{e}-g)}
$$

When incremental investments do not create economic value:

$$
T E V_{_T}=\frac{F E_{_{T+1}}-r_{e}\times B_{_T}}{r_{e}}
$$

The terminal value for the FCFE model is related to the terminal value for the residual income/EBO model as follows:

$$
\mathrm{TV_{T}=T E V_{T}+B_{T}}
$$

See worksheet 10 in the EXCEL workbook Smucker-July 2015 version 7.0. Xls.

All these formulas are embedded in the worksheets.

# Lecture Note 5 Valuation by Multiples

# Objective

Introduce students to the mechanics of valuation using comparable multiples.

# Outline

·Defining valuation multiple
Valuing equity: P/E, P/C, P/B and P/S multiples
· Price multiples and value drivers
Total enterprise value multiples
Valuation by comparable transactions

# Valuation Multiple

A valuation multiple is the ratio of the market value to a consistent accounting base.

$$
M u l t i p l e={\frac{M a r k e t V a l u e}{A c c o u n t i n g B a s e}}
$$

If the objective is to value the equity of the firm, then we can use the following ratios:

Price-to-Earnings (P/E) Ratio: This is the ratio of price per share to earnings per share.
Price-to-Cash Flow (P/C) Ratio: This is the ratio of price per share to gross (equity) cash flows per share. Gross cash flows to equity are usually defined as net income $+$ depreciation & amortization.
· Price-to-Book (P/B) Ratio: This is the ratio of price per share to book value of equity per share. This is also referred to as the Market-to-Book Ratio (M/B).
· Price-to-Sales (P/S) Ratio: This is the ratio of price per share to sales per share. Do you see any inconsistency in the definition of this multiple?

# Example of Valuation by Multiples

Firm A 2013 Earnings \$100 MM Nov 2014 Market value of equity \$1,000 MM Price-to-current earnings (P/E): \$1,000/\$100 = 10

<html><body><table><tr><td>Comparable Firms</td><td>P/E</td></tr><tr><td>1</td><td>17</td></tr><tr><td>2</td><td>11</td></tr><tr><td>3</td><td>15</td></tr><tr><td>4</td><td>12</td></tr><tr><td>5</td><td>7</td></tr><tr><td>Mean</td><td>12.4</td></tr><tr><td>Median</td><td>12</td></tr></table></body></html>

Value of equity of my firm based on your multiple is:

# My Value $=$ Your P/E \* My Earnings

Value based on median P/E $=12^{*}100=\$1,2000$ Value based on mean P/E $=12.4^{*}100=\mathbb{\mathbb{S}}1.240\mathrm{MM}$

Firm A seems undervalued by $\$200 M$ to \$240 MM based on comparable multiples valuation technique.

The actual computations are simple. The difficulty is in choosing appropriate comparables. We will focus on how to choose comparables based on value drivers.
# P/E Ratio and Value Drivers

From the Gordon growth model, the price of a stock:

$$
P_{0}=\frac{F C F E_{1}}{r_{e}-g}=\frac{E_{1}(1-k)}{r_{e}-g}
$$

Where FCFEi is forecasted free cash flows to equity, $\mathrm{E}_{1}$ is forecasted earnings or EPS, and $\mathbf{\epsilon}^{\zeta}\mathbf{k}^{,}$ is the plowback ratio. Thus, P/E ratio in terms of projected next period earnings:

$$
\frac{P_{0}}{E_{1}}=\frac{(1-k)}{r_{e}-g}
$$

Since $\mathrm{E}_{1}=\mathrm{E}_{0}(1+\mathrm{g})$ , P/E ratio in terms of current earnings:

$$
\frac{P_{0}}{E_{0}}=\frac{(1+g)(1-k)}{r_{e}-g}
$$

Equations (2) and (3) show the value drivers that affect P/E ratios, namely, expected growth in earnings, plowback rate, and cost of equity.

Therefore, when choosing comparables for P/E based valuation, we should look for firms with similar expected growth rates, plowback rates, and operating risk/cost of equity.

# P/B and Value Drivers

Since $\mathrm{ROE}=\mathrm{E}_{1}/\mathrm{B}_{0}\Rightarrow\mathrm{E}_{1}=\mathrm{ROE}\times\mathrm{B}_{0}$ . From the Gordon growth model:

$$
P_{0}=\frac{B_{0}\times R O E\times (1-k)}{r_{e}-g}
$$

Since $\mathbf{g}=\mathbf{k}^{*}\mathbf{ROE}$ in the steady state:

$$
\frac{P_{0}}{B_{0}}=\frac{R O E-g}{r_{e}-g}
$$

Add and subtract $\mathrm{r_{e}}$ to the numerator:

$$
\frac{P_{0}}{B_{0}}=1+\frac{R O E-r_{e}}{r_{e}-k\times R O E}
$$

Equation (5) can also be derived from the discounted residual income (EVA for shareholders) model.

P/B is strongly influenced by ROE. All else equal, a lower ROE leads to a lower P/B and a higher ROE leads to a higher P/B.
While choosing comparable firms, look for firms with similar ROE, growth, and operating risk.

# P/S and Value Drivers

Define net profit margin as Net Income / Sales. Then: $\mathrm{E}_{0}=$ Profit Margin $\times\mathrm{\bfS}_{0}$ . From the Gordon Growth Model:

$$
P_{0}=\frac{F C F E_{1}}{r_{e}-g}=\frac{E_{1}(1-k)}{r_{e}-g}
$$

$$
P_{0}=\frac{F C F E_{1}}{r_{e}-g}=\frac{E_{0}(1+g)(1-k)}{r_{e}-g}
$$

$$
P_{0}=\frac{S_{0}\times P r o f i t~M a r g i n\times (1+g)(1-k)}{r_{e}-g}
$$

$$
\frac{P_{0}}{S_{0}}{=}\frac{P r o f i t M a r g i n{\times (1+g)(1-k)}}{r_{e}-g}
$$

· P/S ratio is increasing in profit margin. All else equal, firms with higher profit margin should have higher P/S.

In choosing comparables based on P/S, look for firms with similar profit margins, earnings growth rates, return on equity, and operating risk.

Home Furnishing Industry
<html><body><table><tr><td>tick</td><td>Name</td><td>p</td><td>size</td><td>Beta</td><td>P/E 0</td><td>P/E 1</td><td>P/B</td><td>P/S</td><td>Ltg</td><td>ROE</td><td>Nmarg</td></tr><tr><td>BSET</td><td>BASSETTFURNITUREINDS</td><td>14.32</td><td>167.8</td><td>0.73</td><td>27.54</td><td>19.35</td><td>0.73</td><td>0.52</td><td>10</td><td>2.6%</td><td>1.9%</td></tr><tr><td>BSH</td><td>BUSH INDUSTRIES -CL A</td><td>4.84</td><td>67</td><td>0.82</td><td>484.00</td><td>40.33</td><td>0.48</td><td>0.20</td><td>10.5</td><td>0.1%</td><td>0.0%</td></tr><tr><td>CRC</td><td>CHROMCRAFT REVINGTONINC</td><td>13.05</td><td>78.7</td><td>0.48</td><td>7.86</td><td>7.05</td><td>1.86</td><td>0.38</td><td>13</td><td>23.6%</td><td>4.8%</td></tr><tr><td>DFS</td><td>DEPARTMENT 56 INC -SER A</td><td>12.9</td><td>168.7</td><td>1.15</td><td>6.36</td><td>6.29</td><td>1.90</td><td>0.82</td><td>9</td><td>30.0%</td><td>12.8%</td></tr><tr><td>ETH</td><td>ETHAN ALLEN INTERIORS INC</td><td>34.37</td><td>1297.8</td><td>1.06</td><td>15.28</td><td>14.32</td><td>2.56</td><td>1.44</td><td>14</td><td>16.8%</td><td>9.4%</td></tr><tr><td>FLXS</td><td>FLEXSTEELINDS</td><td>16.72</td><td>104.3</td><td>0.47</td><td>14.29</td><td>11.15</td><td>1.17</td><td>0.36</td><td>10</td><td>8.2%</td><td>2.5%</td></tr><tr><td>FBN</td><td>FURNITURE BRANDS INTL INC</td><td>23.85</td><td>1326.9</td><td>1.11</td><td>11.99</td><td>11.30</td><td>1.53</td><td>0.58</td><td>16</td><td>12.8%</td><td>4.9%</td></tr><tr><td>LZB</td><td>LA-Z-BOY INC</td><td>23.98</td><td>1360.1</td><td>0.73</td><td>14.36</td><td>13.40</td><td>2.24</td><td>0.62</td><td>15</td><td>15.6%</td><td>4.3%</td></tr><tr><td>LEG</td><td>LEGGETT&PLATTINC</td><td>22.44</td><td>4367.4</td><td>1</td><td>20.40</td><td>19.35</td><td>2.23</td><td>1.03</td><td>15</td><td>10.9%</td><td>5.1%</td></tr><tr><td>LBY</td><td>LIBBEY INC</td><td>26</td><td>396.1</td><td>0.51</td><td>11.50</td><td>10.83</td><td>2.25</td><td>0.91</td><td>11</td><td>19.6%</td><td>7.9%</td></tr><tr><td>MHK</td><td>MOHAWK INDUSTRIES INC</td><td>56.95</td><td>3784.3</td><td>0.98</td><td>13.59</td><td></td><td>13.21 1.99</td><td>0.90</td><td>15</td><td>14.7%</td><td>6.6%</td></tr><tr><td>NWL</td><td>NEWELL RUBBERMAID INC</td><td>30.33</td><td>8107.2</td><td>0.57</td><td>20.49</td><td></td><td>19.32 3.96</td><td>1.12</td><td>12</td><td>19.3%</td><td>5.5%</td></tr><tr><td>SCSS</td><td>SELECT COMFORT CORP</td><td>9.4</td><td>278.8</td><td>0.95</td><td>36.15</td><td>28.49</td><td>96.05</td><td>0.89</td><td>30</td><td>16.7%</td><td>2.5%</td></tr><tr><td>STLY</td><td>STANLEY FURNITURE CO INC</td><td>23.25</td><td>151.6</td><td>0.86</td><td>12.17</td><td>10.86</td><td>61.60</td><td>0.65</td><td>15</td><td>13.2%</td><td>5.4%</td></tr><tr><td>TUP</td><td>TUPPERWARECORP</td><td>15.08</td><td>879.3</td><td>0.79</td><td>10.40</td><td></td><td>11.09 6.00 0.79</td><td></td><td>10</td><td>57.7%</td><td>7.6%</td></tr></table></body></html>

LA-Z-BOY Earnings (current in MM\$) 94.72 Book Value (currentin MM\$) 606.1 Sales (current in MM\$) 2201

 ![500](82245aff332e62c71a45aa455b00ba7096827a1e0193957386af476da15dbe61.jpg)

# Correlation

P/E and Growth 30%

●P/E is positively correlated with growth. Firms with high growth should have high P/E.
Choose firms with similar expected growth rates, plowback rates, and operating risk/cost of equity.

 ![500](7ca59a6fa938bbbc11a9e3ca67d61723be705a7de1de7bf5cada11a9c3f878af.jpg)

# Correlation

P/B and ROE 69%

· P/B is positively correlated with ROE. Firms with high ROE should have high P/B. · Choose firms with similar ROE, growth, and operating risk.

 ![500](66aa2fe6fd2433aab982c03fc5d3d589c8c0dbffe3ba62daf957f157583afc73.jpg)

# Correlation

P/S and Margin 60%

· P/S ratio is positively correlated with profit margin. Firms with high profit margin should have high P/S. Choose firms with similar profit margins, earnings growth rates, return on equity, and operating risk.

# How to choose firms with similar operating risks?

The following proxies for operating risk can be used:

· Industry, technology, customers.
Firm size (market capitalization, sales, assets, and number of employees).
· Beta of the firm.
· Financial leverage. Why financial leverage?

Exercise: Value LA-Z-BOY using comparable multiples.

# Total enterprise value (operating value) multiples

Firm Value $\begin{array}{r l}{\mathbf{\tau}}& {{}=\mathbf{\tau}\quad\mathrm{E}+\mathbf{P}+\mathbf{D}\mathbf{\tau}} \ {\mathbf{\tau}}& {{}=\mathbf{\tau}\quad\mathrm{E}+\mathbf{P}+\mathbf{D}\mathbf{\tau}} \end{array}$
Value of net operating assets
$+$ Cash & non-operating assets

Value of operating assets is called total enterprise value:

Total EnterpriseValue $=$ (Market Value of Equity $+$ Minority Interest $+$ Market Value of Preferred Stock $+$ Market Value of Debt) - Cash & Non-Operating Assets

For debt, preferred stock, minority interest and cash & nonoperating assets, you may use book values. Exceptions?

Enterprise Value-to-EBITDA (EV/EBITDA): Firms with similar growth in EBIT/EBITDA, similar reinvestment rates, and similar operating risks.

Enterprise Value-to-Invested Capital (EV/IC): Firms with similar ROIC, reinvestment rates, and operating risks.

Enterprise Value-to-Sales (EV/S): Choose firms with similar operating profit margins in addition to matching on growth rates, operating risks, and reinvestment rates.

My Equity Value $=$ [Your (EV/EBITDA) \* My EBITDA $+$ My Cash & Non-operating assets] My debt, pref. Stock & minority interest

# Valuation Based on Comparable Transactions

This approach is widely used in pricing IPOs, mergers, and acquisitions. Suppose you want to value a potential target.

· Examine comparable transactions (acquisitions) over the last several years in the target's industry or similar industries. Make sure that the target firm and the acquired firms that were part of the prior transactions have similar business characteristics.
Compute acquisition multiples from each transaction and the mean and median across all comparable transactions.
Project the accounting base for the target firm. Multiply the accounting base with the mean or median transaction multiple to compute the value of equity or total enterprise value of the target firm.

# Pitfalls with this approach

· Difficult to find recent comparable transactions. Prior transaction prices would include the value of any projected synergies, premium for corporate control and the effects of over-bidding.

This could lead to valuations that are too high.

# Lecture Note 6 Computing Cost of Capital: Financial Leverage and Cost of Capital

# Objective

Introduce students to levering and unlevering betas and cost of equity.

# Outline

· Operating risk vs. Financial risk
Modigliani & Miller propositions 1 and 2
· Levering and unlevering betas and cost of capital
Divisional cost of capital
Adjusted present value (APV) model (bonus)

# Operating Risk Vs Financial Risk

Operating Risk: It refers to the risks (both idiosyncratic and systematic) underlying a firm's business. Idiosyncratic operating risks would include bad management, product defects, labor problems, and etc. Systematic operating risks refer to the sensitivity of a firm's operating cash flows (NOPAT and FCFF) to general economic conditions. E.g.: weakening of the Euro, oil shocks, etc.

Financial Risk: It refers to the additional variability imposed on the free cash flows to shareholders due to the presence of debt. The presence of financial leverage magnifies the operating risks faced by the shareholders.

Financial leverage makes good-times better and bad-times worse for the shareholders. It increases the risk to shareholders who arethe residual claimants.

Only systematic risk should matter for cost of capital.

# Trade-off between operating risk and financial leverage

Firms with high operating risk are likely to follow a conservative (low debt) financial leverage policy.

Debt capacity of a firm (the amount of debt it can undertake without significantly increasing its cost of debt) is inversely related to its operating risks.
# Capital Structure and Cost of Capital

Modigliani & Miller (1958), American Economic Review derived two results under the following perfect market assumptions:

(1)  Individuals and firms can borrow and lend at the same market rate of interest and no transaction costs.
(2) No agency costs, no bankruptcy costs, and no personal taxes.
(3) No barriers to the free flow of information in the security markets.

# Unlevered Firm

All-equity firm, a firm with no debt.

Following M&M, assume no growth and infinite life. This means the expected free cash flow to the firm (FCFF) are constant and equal to NOPAT.
Revenues Rev
Less: operating costs -OC
Gross income GI
Less: depreciation -Dep
Earnings before int. & taxes EBIT
Less: Taxes -Tax
Net Operating Profits After NOPAT [=EBIT (1-T)]
Taxes

The free cash flows to the shareholders of the unlevered firm:

$$
F C F F=N O P A T+D e p-C a p E x-A W C
$$

FCFF $\cong$ FCFE since there is no debt. Note that for the no growth case, Dep $=$ CapEx and $\Delta\mathrm{WC=0}$

Value of the unlevered firm

$$
V_{u}=\frac{E (F C F F)}{\rho}
$$

Where $\rho$ is the unlevered cost of equity (cost of capital for the unlevered firm).

Consider an identical firm with both debt (perpetual) and equity. D is the market value of debt and E is the market value of equity for the levered firm.

Income statement for the levered firm

Revenues Rev Less: operating costs -OC Gross income GI Less: depreciation -Dep Earnings before int. & taxes EBIT Less: Interest -rd D Earnings before taxes EBT Less: Taxes -Tax Net Income NI

$\mathrm{r_{d}}$ is the cost of debt of a long-term bond with no intermediate principal repayments. Assume market value of debt $=$ facevalue of debt. Free cash flows to equity (FCFE) of the levered firm:

$$
F C F E=N I+D e p-C a p E x-A W C
$$

Is equal to NI since CapEx $=$ Dep and $\Delta\mathrm{WC=0}$

Free cash flows to debt: ra D (no principal repayments)

We now show that the sum of cash flows to shareholders and bondholders equals FCFF plus the interest tax shield:

$$
\mathrm{NI}+\mathrm{Dep}-\mathrm{CapEx}-\Delta\mathrm{WC}+\mathrm{r_{d}}\mathrm{D}
$$

The first term on the RHS of equation (5) is exactly the same as that for the unlevered firm; we can discount the first term at the unlevered cost of equity p.

The second term is the interest tax shield assumed to have the same risk as the levered firm's debt; we can discount it at $\mathrm{r}>=$ rd。

Value of the levered firm, VL

$$
\begin{array}{c c} {{V_{L}=\displaystyle\frac{E(F C F F)}{\rho}+T_{c}\times D}} \ {{\Rightarrow}} & {{V_{L}=V_{u}+T_{c}\times D}} \end{array}
$$

$\mathrm{T}\mathrm{. D}$ represents the PV of tax shields from debt. Equation (7) forms the basis of the adjusted present value model.
In a world without corporate taxes $(\mathrm{T_{c}}=0)$ , the value of a firm is independent of its capital structure, financial leverage, or debt. In other words:

$$
V_{L}=V_{u}
$$

Arbitrage? $\mathrm{V_{L}>V_{U}? V_{L}<V_{U}?}$

Modigliani & Miller Proposition $2$ (with corporate taxes):

M&M derived a relation between cost of equity of a levered firm and leverage in a world with corporate taxes:

$r_{e}=\rho+(1-T_{c})(\rho-r_{d})\frac{D}{E}$ (9)
Re Levered cost of equity, compensation for both operating and financial systematic risk.
P Unlevered cost of equity, compensation for operatingsystematic risk.
(1-T)(p -ra) D/E Leverage risk premium.
D/E Market value debt-to-equity ratio for the levered firm.

$$
V_{L}=\frac{E (F C F F)}{\rho}+T_{c}\times D
$$

Which is the adjusted present value $(A P V)$ valuation model under the perpetuity case.

Define weighted average cost of capital (WACC) such that the value from the following model is equal to the value from the APV model in equation 10:

$$
V_{L}={\frac{E (F C F F)}{W A C C}}
$$

Where FCFF=NOPAT. Equation (11) represents a more traditional DCF valuation model (in the perpetuity case).

In the APV valuation model in (10), the tax advantage of debt is explicitly shown as an addition to the unlevered value.

In the WACC valuation model in (11), the tax advantage of debt is implicit in the discount rate (WACC).

From equation (11):

$$
\begin{array}{c} {{W A C C=\displaystyle\frac{E(F C F F)}{V_{L}} =\rho\times\displaystyle\frac{V_{u}}{V_{L}}}}\ {{=\rho\times\displaystyle\left[\frac{V_{L}-T_{c}\times D}{V_{L}} \right]}}\end{array}
$$

$$
W A C C=\rho\times\left[1-T_{c}\times\frac{D}{V_{L}}\right]
$$

$\mathrm{D}/\mathrm{V_{L}}$ is the market value leverage ratio of the levered firm.

In step 1, we used the fact that $\mathrm{E (FCFF)}=\uprho\times\mathrm{V}_{\mathrm{u}}$ from (3).
In step 2, we used the fact that $\mathrm{V_{u}}\mathrm{=V_{L}}-\mathrm{T_{c}}\times\mathrm{D}$ from (7).

# Proposition 1 (restated)

In a world without corporate taxes $(\mathrm{T_{c}}=0)$ , the WACC of a firm is independent of its capital structure or debt.

Henceforth, we will remove the subscript $\mathrm{L}$ from $\mathrm{V_{L}}$ and denote $\mathrm{V_{L}}$ as V.

Substitute for p from equation (9) into equation (12 a), the M & M expression for WACC, and simplify. This gives the traditional WACC formula:

$$
W A C C=r_{e}\frac{E}{V}+(1-T_{c}) r_{d}\frac{D}{V}
$$

Where D, $\mathrm{E}$ ,and $\mathrm{V}$ represent market values of debt, levered equity, and the firm respectively.

Thus, there is no inconsistency between the traditional definition of WACC and the M & M definition for firms with a target debt level or capital structure.

To summarize:

· Use WACC valuation models when the firm has a permanent level of debt on its balance sheet or has a target debt level.
WACC formula also assumes that any change in debt level does not have an appreciable effect on the cost of debt.
· Look at the EXCEL file “Example involving FCFF, FCFE and FCFD. Xls" on the course website to understand the source of interest tax shields.

 ![500](48f8a96188881d6d9071e364e0aff268fc27978c34f72e709818df7dd9ce6adf.jpg)

# With direct and indirect costs of financial distress

Recall the value of the firm according to the APV model:

$$
V_{L}=V_{u}+T_{c}\times D
$$

What is the optimal capital structure or debt level according to this model?

With the introduction of bankruptcy costs:

$$
V_{L}=V_{u}+T_{c}\times D-P V (B C)
$$

Where PV (BC) refers to present value of bankruptcy costs.

Trade-off between increased value from higher debt, due to increased interest tax shields, and the value lost due to greater likelihood of bankruptcy. This trade-off provides a debt level at which value is maximized and WACC is minimized.

# How do we measure D/E and D/V?

· Ratios based on market value of equity and market value of debt. Book value of debt may be appropriate as long as interest rates or default risk has not changed significantly since the debt was originally issued.

Include all permanent interest bearing debt.

# Levering and Unlevering Cost of Capital

# Define:

βu =  Beta of an unlevered firm. It is variously called as asset beta, firm beta, or unlevered equity beta. It measures a firm's business risk.
βe  =   Levered equity beta or simply equity beta. It measures a firm's business risk $+$ leverage risk.
βd  = Debt beta (assumed zero for high-grade debt).
Using CAPM:

$$
\begin{array}{r}{\rho=r_{f}+\beta_{u}E\big (r_{m}-r_{f}\big)}\ {r_{e}=r_{f}+\beta_{e}E\big (r_{m}-r_{f}\big)}\ {r_{d}=r_{f}+\beta_{d}E\big (r_{m}-r_{f}\big)}\end{array}
$$

Where:

$\rho=$ the cost of equity for the unlevered firm.
$r_{e}={}$ the cost of equity for the levered firm.
$r_{d}=$ the cost of debt.
Substitute the CAPM definitions for $\uprho,\uprho_{\uprho}$ , and $\mathrm{r_{d}}$ from equations (13), (14) and (15) into:

$$
R_{e}=\rho+(1-T_{c})(\rho-r_{d})\frac{D}{E}
$$

This gives:

$$
\beta_{e}=\beta_{u}+(1-T_{c})(\beta_{u}-\beta_{d})\frac{D}{E}
$$

Equation (17) can be used to find the equity beta given the asset beta and the target debt-equity ratio. Rearranging:

$$
\beta_{u}=\frac{(1-T_{c}) D/E}{1+(1-T_{c}) D/E}\beta_{d}+\frac{1}{1+(1-T_{c}) D/E}\beta_{e}
$$

Equation (18) can be used to unlever the equity beta. This is useful in:

· In evaluating how a change in capital structure will affect a firm's cost of capital. Computing cost of capital for individual divisions or projects (more on this later).

We can directly get the unlevered cost of equity by inverting equation (16) and solving for p:

$$
\rho=\frac{r_{e}+r_{d}(1-T_{c}) D/E}{1+(1-T_{c}) D/E}
$$

We can also solve for $\uprho$ from the M&M WACC formula in equation (12 a):

$$
\rho=\frac{W A C C}{1-T_{c}(D/V)}
$$

Note that both equations will give the same value for p given the same information.

These are not new expressions but algebraic transformations of the original expressions.

If (only if) $\upbeta_{\mathrm{d}}=0$ (for high quality debt such as AAA), then:

$$
\beta_{u}=\frac{\beta_{e}}{1+(1-T_{c}) D/E}
$$

Example: The United Southern Construction Company (USC) currently has longterm debt with a book value of $\$400$ , current liabilities (does not contain any short-term debt) with a book value of $\$50$ , and equity with a book value of $\$1000{M M}$ . The company's treasurer believes that the firm can maintain a long run target capital structure of $35\%$ debt to value, without losing the firm's ability to borrow at $7\%$ . The current risk-free rate is $5\%$ . The firm has a marginal tax rate of $39\%$ . The expected risk premium on the market next year is estimated to be $5\%$ and the equity beta of the company is estimated to be 1.2. The company's stock currently trades at $\$20$ per share. It has 10 million shares outstanding. The company's long-term debt is in the form of bonds, which are currently trading at $\$1,002$ per bond. The company has 50,0 o 0 bonds currently outstanding. Assume that the market value of current liabilities is the same as their book value.

1)  What is the company's current cost of equity? Its weighted average cost of capital?
2) What will be the new weighted average cost of capital if the company changes its capital structure to its target capital structure?
3) Gordon Phillips is the treasurer of United Construction & Lumber Associated (UCLA), which is a competitor of USC. He estimates that his firm faces the same risks as USC. By chance, he happens to find out the WACC used by USC. Since the risks faced by the two firms are the same, he concludes that he can use USC's WACC to compute the NPV of a project (with the same risk as that of the entire firm) that he is currently evaluating. Is his analysis right? Why or Why not?
1)
A) Use only interest-bearing debt.
B) Use market values of debt and equity. If market values are not available for debt, it is reasonable to use book values since for most debt except high yield debt market values are quite close to book values.

Market Value of Debt, $\mathrm{D}=\mathbb{S}1\small, 002\times 50\small, 000/\mathbb{S}1\small, 000,000=\mathbb{S}50.1\mathrm{MM}.$ Market Value of Equity, $\mathrm{E}=\S 20{\times}10\mathbf{M}\mathbf{M}=\S 200\mathbf{M}\mathbf{M}$ Market Value of Firm, $\mathrm{V}=\mathrm{D}\mathrm{+E}=\mathbb{S}\hat{\mathsf{S}}0.1+\mathbb{S}200=\mathbb{S}2\hat{\mathsf{S}}0.1\mathrm{MM}$ $\mathrm{D}/\mathrm{V}=0.20,\mathrm{E}/\mathrm{V}=0.80,\mathrm{D}/\mathrm{E}=0.25$

$$
\mathrm{r_{e}=r_{f}+\beta_{e}\left[E (r_{m}-r_{f})\right]=~5\%+1.2\times 5\%=11\%,~r_{d}=7\%}
$$
$$
\therefore=\mathrm {{r_{e}} }\left (\mathrm {{E}} /\mathrm {{V}} \right)+\mathrm {{r_{d}} }\left (\mathrm {{1-\mathrm{{T_{c}} }}}\right)\mathrm {{D}} /\mathrm {{V}} =11\times 0.80+7\times\left (1-0.39\right)\times 0.20=9.65^{\circ}/\mathrm {{out}}
$$

2) There are several ways to solve this. The easiest approach is to use the Modigliani-Miller WACC formula.

Approach 1 (using the M&M formula for WACC)

$$
\mathrm{WACC}=\mathrm{\rho}(1-\mathrm{T_{c}}\times\mathrm{D}/\mathrm{V})
$$

The unlevered cost of equity:

$$
\Rightarrow\rho=9.65/(1-0.39\times 0.20)=10.47\%
$$

The new D/V ratio $=0.35$ . The new WACC:

$$
\mathbf{WACC}=10.47{\times}(1-0.39{\times}0.35)=9.04\%
$$

Approach 2 (using the M&M formula for levered cost of equity)

Compute the unlevered cost of equity from:

$$
\begin{array}{r l}&{\mathrm{r}_{\mathrm{e}}=\uprho+(\uprho-\mathrm{r}_{\mathrm{d}})(1-\mathrm{T}_{\mathrm{c}})\mathrm{D}/\mathrm{E}}\ &{\Rightarrow\uprho=[\mathrm{r}_{\mathrm{e}}+\mathrm{r}_{\mathrm{d}}(1-\mathrm{T}_{\mathrm{c}})\mathrm{D}/\mathrm{E}]/[1+(1-\mathrm{T}_{\mathrm{c}})\mathrm{D}/\mathrm{E}]}\ &{\mathrm{\Gamma}_{\mathrm {{{\mathrm{~}} }}}=(11+7\times 0.61\times 0.25)/(1+0.61\times 0.25)=10.47\%}\end{array}
$$

Compute levered cost of equity at the new $\mathrm{D/E}$ ratio:

$\mathrm{D}/\mathrm{E}=(\mathrm{D}/\mathrm{V})/(\mathrm{E}/\mathrm{V})=0.35/0.65=0.54$ $\mathrm{r}_{\mathrm{e}}=10.47+(10.47-7)\times 0.61\times 0.54=11.61\%$ $\mathrm{WACC}=11.61\times 0.65+7\times 0.61\times 0.35=9.04\%$

Approach 3 (using levered and unlevered betas)
We will solve this by levering and unlevering betas. The debt is risky. The cost of debtof $7\%$ is consistent with a debt beta of 0.4 (backout from CAPM). The unlevered beta:

$$
\begin{array}{r l}&{\beta_{\mathrm{u}}=\beta_{\mathrm{d}}(1-\mathrm{T}_{\mathrm{c}})(\mathrm{D}/\mathrm{E})/[1+(1-\mathrm{T}_{\mathrm{c}})\mathrm{D}/\mathrm{E}]+\beta_{\mathrm{e}}/[1+(1-\mathrm{T}_{\mathrm{c}})\mathrm{D}/\mathrm{E}]}\ &{}\ &{\beta_{\mathrm{u}}=0.4\times 0.61\times 0.25/[1+0.61\times 0.25]+1.2/[1+0.61\times 0.25]=1.09}\end{array}
$$

The new levered equity beta at the new $\mathrm{D/E}$ ratio of 0.54:

$$
\beta_{\mathrm{e}}=1.09+(1.09-0.40)\times 0.61\times 0.54=1.32
$$

From CAPM, $\mathrm{r_{e}}=5\%+1.32\times 5\%=11.6\%$ .Use the new $\boldsymbol{\mathrm{r_{e}}}$ to compute the new WACC as in approach 2.

3) The correct answer is that the treasurer of UCLA should not use the WACC directly since the appropriate capital structure for UCLA may not be the same as that for USC, especially if USC's capital structure is far from the optimal capital structure. UCLA should compute the unlevered cost of equity from USC's WACC and then relever it at the appropriate leverage ratio.

# Divisional (Project) Cost of Capital

Consider an all-equity firm that has two divisions: food processing and computer peripherals. Both $\mathrm{F}$ and $\mathrm{C}$ contribute equally to the value of the firm. Assume that the risk-free rate is $5\%$ and the market risk premium is $5.5\%$ .The following information is available:

<html><body><table><tr><td></td><td>Unlevered Equity F Beta</td><td>Cost of capital using CAPM</td></tr><tr><td>Computer</td><td>1.5</td><td>5+1.5 (5.5)=13.3%</td></tr><tr><td>Food</td><td>0.5</td><td>5+0.5 (5.5)=7.8%</td></tr><tr><td>Firm</td><td>1.0</td><td>5+1.0 (5.5)=10.5%</td></tr></table></body></html>

· A project in the computer division has an IRR of $12\%$ · A project in the food division has an IRR of $9\%$

Suppose that the firm uses the firm's overall WACC to evaluate these projects. What decisions will the company reach? Evaluate?

Suppose you want to spin-off the Food division and so you want to determine its value. If you use the Firm's cost of capital to value the division will you gain or lose?
# Input Needed to Compute Divisional WACC

The target capital structure, D/V, for the division. · The cost of equity, $\boldsymbol{\mathrm{r}}_{\mathrm{e}}$ , the cost of debt, rd, and the effective tax rate, $\mathrm {{T_{c}} ,}$ , for the division.

# The Pure-Play Approach

Divisions and publicly traded firms operating in the same line of business (industry) offering similar products and services face similar systematic operating risks.

10 Identify one or more pure-play publicly traded firms that are in the same industry as the division with similar operating risks and product lines.
2) Estimate each pure-play firm's levered equity beta. This is just the beta you can get from Yahoo Finance.
3) Unlever each levered equity beta using the pure-play firm's market value D/E ratio (see equations (19), (20), and (21)).
4) Take the average of unlevered equity betas if there is more than one pure-play firm. The average represents the systematic operating risk of the division.

5) Debt ratio to re-lever the unlevered equity beta?

Use the average debt ratio of pure-play firms. Subjectively adjust the pure-play firm debt ratios if you believe they are too high or too low. Use the debt ratio of the parent firm.

6) You can also directly compute the unlevered cost of equity, p, from equation (20) and relever it to obtain $\mathrm{r_{e}}$ basedon the division's target D/E ratio.

7 Cost of debt.

Use the average cost of debt of the pure-play firms. Use the cost of debt of the parent only if you believe that the division's debt is as risky as the parent's debt.

8) We can use the effective tax rate of the parent as the effective tax rate of the division.
9) Once the cost of equity, cost of debt, debt ratios, and effective tax rates are determined, we can compute the WACC for the division.

# Drawback of the pure-play approach

How easy is it to find a pure-play firm that matched your division?

# Adjusted Present Value Model (general version)

This method is useful when (a) capital structures vary significantly over time and (b) leverage is high and, therefore, it is difficult to estimate levered cost of equity (LBO restructuring situations).

Discount after-tax operating cash flows at the unlevered cost of equity p and discount interest tax shields and the rest at appropriate discount rates.

$$
V_{0}=\sum_{t=1}^{T}\frac{F C F F_{t}}{\left (1+\rho\right)^{t}}+\frac{T V_{T}}{\left (1+\rho\right)^{T}}+\sum_{t=1}^{T}\frac{I N T_{t}\times T_{c}}{\left (1+r_{d}\right)^{t}}+\frac{T_{c}D_{T}}{\left (1+r_{d}\right)^{T}}
$$

FCFFt $=$ Free cash flows from operations in year 't'.
INTt $=$ Interest payments.
TVT $=$ Estimated terminal value in period T.
Tc 二 Effective corporate income-tax rate.
P $=$ Unlevered cost of equity.
Rd $=$ Cost of debt.
DT $=$ Present value of interest payments beyond year T. Typically assumed equal to value of debt outstanding in year T.

Also, there is no direct provision for bankruptcy costs, although it may be indirectly considered through declines in sales or increases in operating costs.

# Lecture Note 7 Firm Valuation: Projecting Pro-Forma Financial Statements

# Sales Driven Pro-forma Financial Statements

Ij+ vicvast uaics.

2) Project Operating Expenses & Taxes.
3) Project Working Capital.
4) Project Fixed Assets & Depreciation.
5) Set financing policy: target Capital Structure with both debt and equity.
6) Project interest expenses and income.
7) Set distribution policy: Target dividend payout.
8) Other Items. A) Non-operating income. B) Good will and other intangibles. C) Preferred dividends. D) Minority interest
9) Generate balanced financial statements; compute future free cash flows and value the firm and value the equity.

# Forecasting Sales

There are two key steps to forecasting future sales:

Projecting industry sales.
Projecting the market share of the firm within the industry.

(1 + growth in firm sales) $=$ (1 + growth in industry sales) \* $1+$ growth in market share)

Note: Growth in $\mathrm{Y}=[\mathrm{Y}(\mathrm{t})-\mathrm{Y}(\mathrm{t}-\mathrm{l})]/\mathrm{Y}(\mathrm{t}-\mathrm{l})$

# Forecasting Industry Sales and Market Share

1) Evaluate the (short-run) effects of macroeconomic condition on the industry in which your firm operates.
2) Project long-run industry sales based on tools such as the product life-cycle model and Porter's industry structure 5- forces (Chapter 4 of the text book) model.
3) Evaluate your firm's strategic position in the industry and evaluate its competitive advantages vis-a-vis other firms in the industry.

# Macroeconomic conditions and industry sales

1) Macroeconomic forecasts help predict the short-run prospects of industries.

2) Sources of information about macroeconomic activity over the next 12 to 24 months:

A) Index of leading economic indicators constructed by the Conference Board is an average of several economic variables considered to be leading indicators of economic activity. The index can predict economic activity 6 to 9 months ahead.

B) Consensus forecasts of economists: Many private consulting firms and universities publish surveys of the forecasts of various Wall Street economists about future GDP growth, inflation, unemployment etc. The consensus predictions of these economists is often more informative than individual forecasts.

3) The effect of macroeconomic conditions on industry sales can be evaluated either qualitatively or quantitatively through tools such as regression analysis.

# Using Regression to Forecast Short-Run Industry Sales Given Short-Run GDP Growth Forecasts

Using data over the last 10 to 15 years, regress annual real growth in industry sales on annual real GDP growth.

Real growth in industry sales can be measured either in terms of growth in number of units sold (say cars or computers) or by measuring growth in constant dollar sales.

Fit a simple linear regression as follows:

Real growth in industry sales = a + b\*Real GDP growth

Where ‘a’ is the intercept and $\mathbf{\hat{\gamma}}_{\mathrm{b}},$ is the slope.

The estimated regression equation can be used to estimate the growth in industry sales over the next two to three years, given forecasts of GDP growth.

We also need to forecast the rate of inflation or unit prices over the next two to three years to convert real industry sales forecasts to nominal industry sales forecasts.

# Projecting Long-Run Industry Sales

Long-run industry sales depend very little on macroeconomic conditions since macroeconomic conditions tend to average out in the long run (neither a protracted slump nor a long period of high prosperity).

Several tools are available to forecast long-run industry sales:

1) Using historical mean or median real industry sales growth; not useful for new industries.
2) The Product Life-Cycle Model can be used predict the stage in the life cycle of a product (development, expansion, maturity, or decline). The product life-cycle model captures the phenomenon of mean-reversion.
3) Porter's Industry Structure Analysis can also be helpful in predicting long-run industry prospects; five forces affect an industry's profitability: substitute products, supplier bargaining power, customer bargaining power, entry/exit barriers; industry competitiveness.
4) Use the tools you learned in your strategy class to provide a strategic perspective on the industry and the firm.

# Projecting the Firm's Market Share

Changes in a firm's market share are driven by the competitive position of the firm in the industry:

· A combination of price and product attributes that cannot be easily replicated by competitors.
Marketing strategies of firms in the industry. Changing consumer tastes.
·Entry/Exit Barriers.

Overall, your projections of the company's market share should be consistent with your analysis of the firm's strategy.

# Three-Stage Sales Growth Model

In predicting the firm's sales growth, we can use the three-stage growth model we discussed earlier.

· In the first stage (the high growth stage lasting say 2 years) estimate specific year-to-year growth rates in firm sales.
· In the second stage (the transition stage from years 3 to 16), the sales growth rate declines toward a long-run steady state growth beyond year 16.
In the third stage (the steady-state beyond year 16), the firm's sales are expected to grow forever at the long-run growth rate of the economy.
· Mean-reversion is the idea underlying these models.

# Keep in mind that forecasting future sales is as much an art as it is a science.

# Projecting Operating Expenses, Taxes, Working Capital, and Fixed Assets

In projecting these items, we usually rely on historical financial ratios. Broadly, the following principles are worth considering:

· Use at least 5 years of financial statement data in computing the various financial ratios.
· Look for any trends in these ratios. For instance, is the gross margin improving or declining, and if so why?
· Are the assumptions you are making consistent with the firm's projected operating strategy?
· Are historical ratios good predictors of the future, especially if you expect the operating environment of the firm to change?

# Projecting Operating Expenses

Operating expenses such as cost of goods sold (COGS), sales, general & administrative expenses (SG&A) are often computed as a percentage of sales. Thus:

Operating Expenses/Sales $=$ (COGS + SG&A - Dep.& Amort.)/Sales

COGS and SG&A typically include Dep&Amort; hence we remove these expenses from COGS & SG&A.

Projecting Operating Working Capital

Forecast operating current assets and liabilities using the following ratios:

Operating Cash/Sales (if any) Accounts Receivables/Sales Inventory/Sales Other Operating Current Assets/Sales

Accounts Payable/Sales Wages & Salaries Payable/Sales Accrued Expenses Payable/Sales Other Operating Current Liabilities/Sales (You can modify historical ratios to reflect a better inventory management system, faster collection of receivables or favorable credit on payables.)

# Projecting Operating Fixed Assets

Net Property, Plant, and Equipment (NPPE) Gross Property, Plant, and Equipment (GPPE)

Consider ratios: NPPE/Sales Other Long-Term Assets/Sales

Depreciation expenses are projected as a percentage of this year's NPPE: Depreciation&Amortization/NPPE.

Accum. Dep & Amort (t) $=$ Accum. Dep & Amort (t-1) + Dep & Amort (t)

GPPE (t) $=$ NPPE (t) $+$ Accumulated Dep & Amort (t)

Capital expenditures are computed as follows:

Capital Expe $\mathrm{nditures (t)}=[\mathrm{NPPE (t)}-\mathrm{NPPE (t-1)}]$ $+$ Dep & Amort (t) $+$ Change in other long-term assets

# Projecting Taxes

· Use the effective tax rate computed from historical statements.
· Income Taxes Payable (which is a current operating liability) is usually projected as a fraction of income taxes provided in the income statement. It is also projected as a fraction of sales. Changes in deferred income taxes can be projected as fraction of the income taxes provided in the income statement or held constant at the base year levels. OperatingRatios 2014 Sales Growth $1.5\%$ Operating Expenses/Sales\* $79.8\%$ \* Depreciation expenses have been removed.
Working Capital/Sales
Net Receivables/Sales 7.6% Inventories/Sales 20.4% Accounts Payable/Sales 7.1% Other current assets/sales 0.0% Other current liabilities/Sales (no tax
Payable) $6.9\%$ Fixed Assets & Depreciation
Gross, Property, Plant, & Equipment
(GPPE) 2699.1 Net Property, Plant, and Equipment (NPPE) 1678.3 GPPE/Sales 47.4% NPPE/Sales $29.5\%$ Depreciation/this year's
NPPE $16.0\%$ Other Long Term
Assets/Sales 3.4% Other Current Assets (mostly def. Tax
Assets) 333.0 Goodwill & Intangibles 12,960.1
Non-Operating Income/Sales $-4.9\%$

Taxes
Effective Tax Rate $34.1\%$ Income TaxesPayable/Total Income Taxes $0.0\%$ Change in net deferred taxes/Total Income
Taxes $4.3\%$ Financing
Cash Payout Ratio $80.5\%$ Book debt/equity ratio $87.1\%$ Book preferred stock/equity
Ratio 0.0% Other long-term liabilities
(SMM) 354.9 Deferred Tax Liabilities
(SMM) 2473.3 Minority Interest 0.0 ST Debt/Total Interest Bearing Debt 3.7% Weighted average interest rate as of 04/15 2.8% Assume that the interest on excess cash is $0.5\%$

Computing Debt-to-Value Ratio

Book value of equity (Fiscal
2014) 7,087 Book value of minority interest (Fiscal 2014) 0 Book value of all equity 7,087 Num ber of shares outstanding (millions) 119.7 Current stock price (July 8,
2015) \$108.46 Market value of equity (July 8, 2022, \$ MM) 12,979 Total Market value of all equity (\$ MM) 12,979 Book value of debt (Fiscal 2014, S MM) 6,171 Book value of preferred stock (Fiscal 2014, \$
MM) 0 Market value of the firm
(SMM) 19,150 Book value of the firm
(SMM) 13,258 Market D/V ratio 0.32
# Market P/V ratio Book D/V ratio

You could vary other long-term liabilities with sales.
# Financing Policy

The firm needs to finance its capital expenditures. It can do that with a combination of internal funds, external debt, and external equity.

# Target Capital Structure

· Financing is based on a target book D/E ratio that corresponds to a target market D/E ratio.
● The firm uses both debt and equity (internal and external).
If the firm has excess cash and does not want to repurchase stock (because it does not want to reduce stock below a certain level) then it can pay the excess cash out as dividends (redistributing total equity among retained earnings and stock). Thus, dividends are the plug to balance the books in this financing model. With excess cash, therefore, the firm's actual dividend payout is likely to exceed its target dividend payout.
· The WACC based DCF approach is appropriate here.
More general financing schemes would include pecking order financing: internal funds, short-term debt, long-term debt, and external equity in that order. The APV approach is more fitting here.

# Distribution Policy

· Examine the current practice and if there is no reason to believe that the firm will change its dividend payout policy maintain the current policy.
If the firm regularly repurchases stock, treat the stock repurchases also as dividend payouts.

# Other Items

Any goodwill left on the balance sheet needs to be kept as it is. It is hard to forecast goodwill.
Any non-operating items need to be taken into account. However, it is hard to think of non-operating items that need to forecast for a long period of time. Such items need to be treated with care and caution.
· If there is any preferred stock, remember to take into account preferred dividends.
· Keep minority interest at current levels.
· Deferred tax assets and liabilities should also be kept at current levels. Long-term liabilities may stay at current levels or vary with sales.
The coupon rate can be decreased or increased over time based on current interest rates.

# Performance Scenarios

It may be a good idea to develop several performance scenarios for the firm and the industry. For instance (see Chapter 9 in KGW for more discussion):

· Increasing market share and high sales growth.
· Constant market share and moderate sales growth.
Losing market share and declining sales growth.

The ratios used to forecast operating expenses; working capital, fixed assets etc. May vary depending on the performance scenario.

# Pro-forma Projections for Smucker

See EXCEL worksheets 6, 7, and 8 for proforma financial statements for Smucker in the workbook Smucker-July 2015 version 7.0. Xls.

# Lecture Note 8 Firm Valuation: Valuing Mergers, Acquisitions & Multi-Business Firms

# What are Mergers and Acquisitions?

Mergers and acquisitions are economically no different from internal capital expenditures such as building a new plant, buying a new machine, expanding capacity, or investing in new technology. Capital expenditures are internal investments needed to grow a firm. Acquisitions are external investments needed to grow a firm. Therefore, the same DCF valuation techniques we use to value internal capital expenditures (capital budgeting) can also be used to value external investments such as acquisitions. Acquirer (buyer) and the Target (seller).

# Acquisitions Vs Internal Investments

Management faces the choice of growth through internal investments or growth through acquisitions. In general, acquisitions provide:

· A faster and (may be) cheaper way to enter a new market. Strategic assets such as brand name, proprietary technology, patents, experienced management etc. That are difficult to develop internally.

# Economic Forces Behind Mergers & Acquisitions

· While acquisitions and internal investments are comparable at the firm level they have different effects at the industry level.

At the industry level, internal investment adds to existing capital stock, while mergers and acquisitions are mostly a reallocation of existing assets. What drives firms? Choice to expand through acquisitions or through internal investments? The capacity utilization in the industry: specifically, excess capacity drives industry consolidation through mergers while peak capacity utilization induces industry expansion through internal corporate investments (see Andrade and Stafford, 1999). The excess capacity may be a result of external economic shocks such as deregulation, foreign competition, etc.
The market for corporate control acts to consolidate the excess capacity. Poorly managed firms get taken over by new owners who restructure these firms and create additional value (control premium) through better management (Manne, 1965).
· A behavioral reason often cited for takeovers and acquisitions

Is managerial hubris (see Roll, 1986).

# Types of Mergers

Horizontal Mergers and Acquisitions: These transactions involve two firms in the same line of business. United Airlines with Continental.

· Vertical Mergers and Acquisitions: These transactions involve a firm acquiring a supplier or a distributor or a retailer.

Conglomerate Mergers: These transactions involve two firms in unrelated lines of business. Such mergers were common in the 1960 s and 1970 s. The most commonly cited reason for conglomerate mergers is diversification.

# Mergers by Mode of Acquisition & Form of Payment

Mode of Acquisition: (a) Mergers are generally friendly deals that enjoy the cooperation of incumbent managers, (b) Tender offers are usually hostile takeover offers made directly to target's shareholders with the active resistance of incumbent managers. ·Form of Payment: (a) Stock offer involves the use of acquirer's stock (b) Cash offer involves simple cash payment (c) there could be a mixture of stock and cash.

# Right Reasons for Mergers and Acquisitions

1) Achieving Operating Synergies:

a) In horizontal mergers or acquisitions (involves two firms in the same industry or line of business), operating synergy gains typically arise from economies of scale, which reduce costs, increased market power, which increases sales and profit margins, or complementary resources. B) In vertical integration (involves suppliers, distributors or retailers) synergies arise from having better control of the production and distribution chain and because the target may have skills or markets that enhances the value of the acquirer. C) These synergies can be valued by discounting the incremental cash flows associated with synergies, i.e., reduced costs, increased sales, etc., at the WACC of the combined firm. Why the combined firm?
2) Achieving Financial Synergies: A company with excess cash and not enough investment opportunities may want to take over a cash-strapped firm with profitable investment opportunities. The value of these synergies represents the value of projects that would otherwise have not been taken.
3) Tax Synergies: A company that is paying high taxes on its income may want to acquire another firm with accumulated tax losses in order to reduce its own taxes or vice-versa. The

Value of these synergies represents the present value of taxes saved due to the acquisition (tax inversions).

# 4) Value from better management:

A) A new group of managers may be able to increase firm value by cutting costs or by increasing sales. The value from better management is referred to as control premium.
B) The value from better management is the difference between the value under new management (restructured value) and the value under old management (un-restructured value). This value is defined as the present value of incremental cash flows (improved sales, reduced costs) associated with new management.

# Some Dubious Reasons for Mergers & Acquisitions

1) Diversification. Why is this dubious reason?

2) Increasing earnings per share or EPS Accretion.

A) EPs Vs Cash Flows. B) Is maximizing EPS the same as maximizing value? C) Can you provide conditions under which this may be true?

# Valuing Mergers & Acquisitions

VT Stand-alone value of the target.
VA Stand-alone value of the acquirer.
V Value of the combined company.
P Price paid for the target.
△V Value created by the acquisition.
Vs Value of operating, financial, and tax synergies from the acquisition.
Vc Value from better management (control premium)

Value created by the acquisition:

Maximum price for the target VT+ △V

This assumes that all of the value created by the acquisition accrues to the target shareholders.

Value created for the buyer $=$ Maximum price for the target - Purchase price $(\mathrm{V_{T}}+\Delta\mathrm{V})-\mathrm{P}$

The value created by the acquisition:

$\Delta{\mathrm{V}}=\mathrm{~\ensuremath~{~\mathrm~{~V~s~}~}~}+\mathrm{~\ensuremath~{~\mathrm~{~V~}_{C}}~}$

Note that ${\mathrm{V_{S}}}$ and $\mathrm{V_{C}}$ can be less than zero. Why?

# Computing the stand-alone value of the target

· Valuation based on forecasting free cash flows to firm (FCFF), computing terminal value, WACC etc.
· In computing WACC, remember the cost of capital for the target firm or division depends on the target's systematic risks. The debt-to-value ratios to be used in the WACC calculation should once again be based on the systematic risks of the target firm. Remember the following fundamental principle about computing cost of capital: it is not who raises money that determines the cost of capital, it is what the money is raised for. Money raised to finance more risky (systematically) investments would be more costly than money raised to financeless risky investments. Thus, the actual cost at which the acquirer raises funds to finance the acquisition has little relevance to determining the cost of capital for the acquisition (the target).

# Stand-alone value of the acquirer

Value based on acquirer's cash flows and cost of capital.

# Valuing Synergies and Better Management

We discussed the valuation of synergies and control premium on pages 5 and 6.
# Market Reaction to Merger Announcements

Short-Term Market Reaction

Immediately after the announcement of an acquisition, the market value of the target firm (controlling for market movements) goes up by $20\%$ to $35\%$ (see papers by Jensen and Ruback (1983), Bradley, Desai, and Kim (1983), Jarrell, Brickley, and Netter (1988), Franks, Harris, and Titman (1991)).

The same studies indicate that after the announcement of a merger/acquisition, on average, the market value of the acquiring firm (after controlling for market movements) either dropsby about $3\%$ in the case of stock offers or goes up marginally in the case of cash offers.

The evidence suggests that:

Initially, all the gains from a merger or acquisition accrue to the target shareholders (the sellers) and the buyers get next to nothing. Why? Probably because of the bidding that usually accompanies most merger transactions and the resulting winner's curse.

# Long-Run Market Reaction

W Hat lappeis tu uit suuek piite Ui atquiig cupaies ili ull long-run? Loughran and Vijh (1997), Journal of Finance, study this question using 947 mergers and acquisitions from 1970 to 1989.
They compute buy-and-hold abnormal returns (compared to matching firms) earned by the acquiring firms for a five-year period after the acquisition date. They find that firms that complete stock mergers earn significantly negative abnormal returns of $-25\%$ over the next five years while firms that complete cash tender offers earn significantly positive abnormal returns of $61.7\%$ over the next five years.
· Mitchell and Stafford (2000) also find that acquirers that use stock financing underperform comparable firms by about $8\%$ during the next three years.
Fuller, Netter, and Stegemoller (2002) and Moeller, Schlingemann, and Stulz (2005) also report similar loss of value for long-term shareholders of the merged firms.
Why? An adverse selection argument (see Myers and Majluf (1984)) would say that acquirers issue stock only when the stock is overvalued. Acquirers are likely to use cash when their stock is undervalued.
Moral: If you are a long-term target shareholder, beware of acquirers bearing stock offers.

# Empirical evidence on the existence of synergies

The empirical evidence on the ex-post performance does not provide much support for the existence of synergies, on average.

A McKinsey study examined 116 acquisition programs in U.S. and U.K. from 1972 to 1983. The study limited itself to Fortune 200 largest U.S. industrials or the Financial Times top 150 U.K. industrials. An acquisition program is judged to be successful if the acquisitions created positive EVA over the next 3 to 5 years. The study found that $61\%$ of the programs ended in failure and only $23\%$ in success. The study also found that the acquisitions that succeeded involved acquirers with strong core businesses prior to the acquisition.
Other studies (see Mitchell and Lehn (1990)) indicate that more than $20\%$ of the acquisitions get divested within 3 years and about $50\%$ by 10 years.
Devos, Kadapakkam, and Krishnamurthy (2009) study 264 large mergers from 1980 to 2004 and estimate average synergy gains to be $10\%$ of the combined equity value of the merging firms. Operating synergies accounted for most of the synergy gains and were higher for focused mergers and undervalued acquirers. The operating synergies arise from cutting back on capital expenditures and investments in working capital and not from revenue increases or cost savings.

# Possible Reasons for Failure of acquisitions

· Overestimation of synergies.
· Overbidding in multiple bidder situations. E.g.: RJR-Nabisco and Winner's curse.
· Poor post-acquisition integration.

# Leveraged Buy-outs

A leverage buy-out (LBO) differs from ordinary acquisitions in the following ways:

A) It is heavily debt financed (often $80\%$ to $90\%$ debt most of which tends to well below investment grade, junk bonds). The debt funds are often borrowed against the physical assets of the acquired business.
B) The ownership transfers to a small group of private (institutional) investors, which is often led by the management of the pre-LBO firm. After the LBO transaction, the shares of the firm no longer trade on the open market.
C) The buyers are, thus, not a traditional corporation as in other acquisitions, but a newly formed non-operating company capitalized by their (often tiny) equity investments and the borrowed funds. The entire resources of the new corporation are then used to pay the purchase price.
D) One of the motives stated for LBO transactions is reducing the agency costs of free cash flows. The idea is that the high level of debt would discipline managers and force them to be more efficient.

# LBO Target Characteristics

1. Cash cows: Companies with low to moderate sale growth, with large and stable free cash flows.

2. Mature industry: Companies in high technology industries where rapid product obsolescence takes place are not preferred. Similarly, companies in highly cyclical industries are not preferred.

3. Strong balance sheets: The acquirers look for firms with strong balance sheets and tangible assets and no contingent liabilities. The capacity to raise large amounts of debt financing depends on this factor. Along these lines, acquirers prefer firms with little or no long-term debt, which indicates unutilized debt capacity.

4. Quality Management: A quality management team is necessary for cutting costs, reducing unnecessary capital expenditures and achieving efficiency. The management must be capable of dealing with the pressure from the debt servicing requirements associated with a large debt.

# Do LBO transactions create ex-post value?

Kaplan (1989) studied 48 LBOs involving management buy-out that took place between 1980-86. He finds that there were dramatic improvements in sales, profits, and cash flows in the three years after the LBO.

Anslinger and Copeland (1996, HBR) find leveraged buyout firms earn returns greater than their cost of capital in their acquisitions.

# Valuation of Multi-Business Firms

Individual business units are defined as separable entities that have no significant synergies with other parts of the company. They could be spun-off as stand-alone businesses.

· Estimate free cash flows from operations (FCFF) for each business unit.
· Compute WACC for each business unit using the divisional cost of capital approach based on pure-play firms.
· Value each business unit using the DCF approach (you can also use the multiples approach to get relative value).
Consider the costs and benefits involving corporate headquarters. This requires a great deal of judgment.
The operating value of the firm (total enterprise value) is the sum of the values of the individual business unit plus the value (or minus the cost) associated with headquarters.
Add the value of excess cash to the operating value to get the total firm value.

# Lecture Note 9 Security Analysis and Investor Behavior

# Factors that complement valuation

We need valuation models because marketsare not alwaysefficient.

Valuation, however, isonly the beginning of security analysis.

A comprehensive approach to security analysisrequires knowledge of add itional firm-spec ific factorsthat complement valuation:

- Hasthe sentiment or momentum changed?
What isthe quality of earnings?
What isthe quality of a stock?
- Isthe firm raising new capital or returming capital?
- Isthe firm growing itsassets rapidly? Doesthe firm need external capital?

Why do these thingsmatter if we already know a firm'svaluation? Because, all valuation models are noisy.

Blind Men and an Eephant

# Some questions on security analysis

Why are ma rkets ineffic ient?

- Because investors are not " rational" in the sense of classical economics: (a) they are not intuitive statisticiansand (b) they are not e xp ec te d utility m a xim ize rs.

Even if marketsare inefficient, how do we know any of the stockselection strategies (value, momentum, earningsqua lity, fund a mental analysis, asset growth, or financing activity) work?

We will explore these questionsfor the rest of the course.

We will examine large sample evidence on the successor failure of the various stock selection strategies.

We will discuss how to integrate these various individual strategies into a simple stock sc reening/selection model.

# Eficient Markets vs. Behavioral Finance

Behavioral finance isan alternative to efficient markets. It triesto explain market ineffic ienciesusing."modelsin whic h some agentsare not fully rational." See Ba rberis and Thaler (2003).

It owesitsexistence to the path-breaking work of several psyc hologists inc luding Daniel Kahneman and Amos Tversky.

- Kahneman won the 2002 Nobel prize in economicseven though he isnot an economist.

Fsc her Black (1986) refersto agents who are not fully rational as noise traders.

- Noise traders believe they are trading on information although they are tra d ing on noise.

Security analysisand active money management isan attempt to a rb itrage the mispricing caused by noise traders.

We will explore the common behavioral biasesthat individualsexhibit and how we might guard against them.

# VV Investor Behavior

" The investor's $c h i e f$ problem -and even hisworst enemy-is likely to be himself."

- Benjamin Graham Considered the fatherof value investing ' Investing is $\sin p/\theta$ , but not easy.

 ![500](2db13791772207165e5746ee8d897ab41ae32e033bd953d0591acadc1f834755.jpg)

"Success in investing doesn't correlate with IQ once you are above the level of 1 o 0.... What you need isthe temperamentto controlthe urges that get other people into trouble in investing."

 ![500](fb47cb99920c154a7dec638921d84f8ef3cd5bbee2a8b0013996781de5f57a55.jpg)

-Warren Buffett

# Psychology of Investing Success

Good investing isabout making good predictions.

Making good predictionsisabout understa nding probability and sta tistic s.

People are good intuitive grammarians.

Are they good intuitive statisticians?

Are they good at estimating probabilities?

# Heuristics and Cognitive Biases

Heuristic: A simple procedure that helpsfind adequate, though often imperfect answersto d iffic ult q ue stions;

- A short-cut or rule of thumb .

Exa mples: Ed uc ated guess, Com mon sense, Gut feel

- People use heuristics when estimating probabilities. - These heuristicscan give rise to systematic biases in our jud gmentsand dec ision-making .

# Dr. McCoy and Spock

Psycholog ists\* refer to two different systemsembedded in our mindsto expla in the way our bra ins work.

System 1: isthe Dr. McCoy (M) System which is emotional, intuitive, reflexive, effortlessand fast.

System 2: isthe Soock (S) System which is rational, logical, and analytical, but also slow and lazy.

The M system can give rise to cognitive biases. The Ssystem attemptsto monitor and control the M system, but isnot a lw a ys suc c e ssful.

 ![500](3ed2bd9942bf607827b4e146475e1511f8317025db3876d8de8c2c241cde7a0c.jpg)

# Ho w Do They Work?

 ![500](8a694d0d075fda929773d151a9230282cee97707b9ab06b2a939819626c10d85.jpg)

Whatis 95 x 78?

Recognizing the sad face and the smiley face isautomatic, which isthe work of the M system.

Thisisnot automatic. McCoy is use le ss here. This req uires Spoc k.

# Division of Labor

There isa division of laborbetween the two systems.

# M Syste m :

- Our brain'sgo-to system for routine decisions and isalwayson. - Takesover in emergencies, reacts automatically to dangers and c hallenges, deals with familiar situations, and makesaccurate short-term p re d ic tions. - It sometimesanswers $e a s i e r$ questionsthan the one it wasasked, isimpulsiv and intuitive, and doesn't understand logic and statistics.

# S System :

- Continuousy monitorsthe M system and triesto keep it out of trouble. - It iscalled to action only when the M system runs into difficulty $(95\times 78)$ - Only one that can follow rules, make deliberate choices, exercise executive Control, etc., but it has limited resources.
From Neuroscience: Partsof the brain associated with the M system are evolutionarily older than those of the Ssystem.

# Are We Dr. McCoy or Spock?

Shane Frederick (2005) hasdesigned a Cognitive Reflection Test (CRT) consisting of 3 questionsthat isa simple measure of the susc eptib ility to the M system.

- The score is 3 for getting all questions correct and 0 for getting none of them correct.

—A $1\boldsymbol{o}$ w score indicates greaterinfluence by the emotional M system and a high score ind icates lesser influence.

- The test wasadministered to variousgroups (see the next page) and 1/3 rd of the participants got none of the answers right! Only 17% got all rig ht.

This suggests that $a//o f u s$ are prone to decisionsunder the M system; unchecked by the more logical Ssystem.

# >> CRT Test Sc ores

Table 1 CRT Scores, by Location
<html><body><table><tr><td></td><td></td><td colspan="4">Percentage scoring 0, 1, 2 or 3</td><td></td></tr><tr><td>Locations atwhichdata werecollected</td><td>Mean CRTscore</td><td>"Low" 0</td><td>1</td><td>2</td><td>"High" 3</td><td>N=</td></tr><tr><td>Massachusetts Institute of Technology</td><td>2.18</td><td>7%</td><td>16%</td><td>30%</td><td>48%</td><td>61</td></tr><tr><td>Princeton University</td><td>1.63</td><td>18%</td><td>27%</td><td>28%</td><td>26%</td><td>121</td></tr><tr><td>Boston fireworks displaya</td><td>1.53</td><td>24%</td><td>24%</td><td>26%</td><td>26%</td><td>195</td></tr><tr><td>Carnegie Mellon University</td><td>1.51</td><td>25%</td><td>25%</td><td>25%</td><td>25%</td><td>746</td></tr><tr><td>Harvard Universityb</td><td>1.43</td><td>20%</td><td>37%</td><td>24%</td><td>20%</td><td>51</td></tr><tr><td>University of Michigan: Ann Arbor</td><td>1.18</td><td>31%</td><td>33%</td><td>23%</td><td>14%</td><td>1267</td></tr><tr><td>Web-based studies?</td><td>1.10</td><td>39%</td><td>25%</td><td>22%</td><td>13%</td><td>525</td></tr><tr><td>Bowling Green University</td><td>0.87</td><td>50%</td><td>25%</td><td>13%</td><td>12%</td><td>52</td></tr><tr><td>University of Michigan: Dearborn</td><td>0.83</td><td>51%</td><td>22%</td><td>21%</td><td>6%</td><td>154</td></tr><tr><td>Michigan State University</td><td>0.79</td><td>49%</td><td>29%</td><td>16%</td><td>6%</td><td>118</td></tr><tr><td>University of Toledo</td><td>0.57</td><td>64%</td><td>21%</td><td>10%</td><td>5%</td><td>138</td></tr><tr><td>Overall</td><td>1.24</td><td>33%</td><td>28%</td><td>23%</td><td>17%</td><td>3428</td></tr></table></body></html>

# The CRT Test

Answer the following questionsin 90 secondsor 30 seconds per question (no cheating !)

(Answersprovided on the last page.)

# Figure 1 The Cognitive Reflection Test (CRT)

(1)  A bat and a ball cost $\$1.10$ in total. The bat costs $\$1.00$ more than the ball. How much does the ball cost? . Cents
(2) If it takes 5 machines 5 minutes to make 5 widgets, how long would it take 100 machines to make 100 widgets? Minutes
(3) In a lake, there is a patch of lily pads. Every day, the patch doubles in size. If it takes 48 days for the patch to cover the entire lake, how long would it take for the patch to cover half of the lake? Days

# Lim ited Resources of S System

Self control and deliberate thought draw on the same limited resources:

- It ishard to multiply 95 times 78 in your head, taIk on the cell phone, and run uphill all at the same time!

- Self controlistiring and leadsto ego depletion ma king sub seq uent cog nitive ta sks ha rder to complete.

- Weig ht loss req uires two sim ulta neousy d iffic ult ta sks: exercise and controlling what we eat. This istiring for the Ssystem.

# : When Are We Likely to Rely on the M System?

Accord ing to Psyc holog ists M system is influential:

- When the Ssystem is cognitively busy or impaired 》 People'sbehavior after a few drinks, a seepless night, or a long, stressful meeting.
- When the problem is ill-structured and complex.
- When information is incomplete, ambiguous, and changing.
- When goalsare ill-defined, shifting, or competing.
- When stress is high due to time constraints or high stakes.
- When decisionsdepend on interacting with other people.

All of this more or less appliesto investment decisions!

Quantitative investment strategiesattempt to minimize the influence of the M system and enhance the role of the Ssystem.

# Various Behavioral Bia ses

Optimism bias
Overconfidence and illusion of confidence
Availability biasand Hind sig ht bias
The law of small numbers
Anchoring
Base Rate Neglect and Representativeness
Regression to the mean
Affect Heuristic, Halo effect, Confirmation bias, and Familiarity
Bia s
Prospect Theory, Loss Aversion, and Fra ming
Mental accounting and Sunk cost fa llacy
Intuitions vs. Formula s

# Optimism Bia s

Consider these questions:

- What isa new restaurant owner'sestimate of chance of success? - What isan entrepreneur'sestimate of chance of success? - What isa CEO'sestimate of value gain to his shareholders from a recent acquisition?

60%of new restaura nts are out of business in 3 years. The chances that a small business will survive for 5 years in the U.S. are about 35%.

Optimistic CEOsta ke on too much debt, overpay for targets, and engage in va lue-destroying mergers (Roll, 1986: “Hubris Hypothesis' ; Malmendier and Tate, 2008).

Lench and Ditto (2008): People believe more positive than negative life eventswill occur to them.

# >> Optimism Bia s

Optimism likely hasan evolutionary advantage and psychologists have shown that it is largely inherited.

Optimistsare the inventors, the entrepreneurs, and successful political and military leaders. They are cheerful, resilient, healthier, and live longer. They are necessary forthe economic development of a society. The key though isto be optimistic without losing track of rea lity.

While optimism may be good for the society and a good life strategy, it is not necessa rily a good investment strategy.

- Forecastsof Dow 36,000 in 1999 during the dot-com bubble.
Over-optimism during the 2001-2006 Housing Bubble.

Be skeptical in evaluating optimistic ea rningsforecastsand investment recommendations.

Engage in premortem to overcome groupthink and optimism

# Overconfidence

Lake Wobegon where "allthe women are strong, allthe men are good looking, and all the children are above average'

- Garrison Keillor A Prairie Home Companion

 ![500](b025f876a9cb972d0805a2941b49ea4b7344418cf4873bc5f8935900ad16a6cb.jpg)

Overconfidence leadspeople to overestimate their abilitiesand fo rec a sting skills.

It leadsto confidence intervalsthat are too narrow and judgmentsthat are too certain, which can give rise to extreme actionsand excessive trading.

# Overconfidence

Doctors vs. Weathermen (Montier, 2010):

-Doctors think they are right $90\%$ of the time on their diagnosesbased on case notesbut are correct only $15\%$ of the time!

- Weathermen think they are right $50\%$ of the time on their predictions from weather patternsand they are right $50\%$ of the time. Why the difference?

In a survey, CFOspredicted 1-year S&P 500 returnsand a 10 percentile low estimate and a 90 percentile $h i g h$ estimate.

- 11,600 forecastscollected from March 2001 to February 2010 (Ben-David, Graham, and Harvey, 2013). Zero correlation between CFO forecastsand realized returns.

- Their confidence intervalsare too na rrow indicating overconfidence in their forecasting skill!

<html><body><table><tr><td colspan="3">S&P 500 Realizations falling in various intervals</td></tr><tr><td></td><td>% below 10 th percentile</td><td>% between n 10 th and 90 th percentile</td><td>% above 90 th percentile</td></tr><tr><td>AllForecasts</td><td>35.6</td><td>32.8</td><td>31.6</td></tr></table></body></html>

# Evidence on Overconfidence

Overc onfidence is universa I\* :

$63\%$ of Americansconsider themselvesto be above average in inte lligence. 71%of Men and 57%of Women consider themselves above average!

$-70\%$ of Canadiansthink they have above average intelligence.

- 69%of Swedish college studentsestimate they are above average d rivers.

-- 75%of U.S. chess players believed they were underrated relative to U.S. chess federation ratings.

- 6%of students at Cornell who took a sense-of-humortest thought they had an above-average sense of humor.

Self-attrib ution bias: Success is due to our ability and failure isdue to externaI c ircumstances.

Makespeople more overconfident over time.

# Skill and Confidence

The least skille $d$ tend to be the most overconfident:

- Chess players who were in the bottom half of the rating scale are the ones who considered themselvesthe most under-rated.

- Students who scored in the $1\boldsymbol{o}$ west 25%of a sense-of-humor test thought they had an above-average sense of humor.

- The incompetent face two hurdles. One, they are below average in ability. Two, they are una ware they are below average.

- There isevidence that improving the skilof the incompetent reduces their overconfidence.

People who are highly competent suffer from underconfidence:

- Students in the top 25%of the humor test underestimated the number of their peers who were less funny.

Confidence is $\it{n o t}$ an indicator of ability although people often mistake confidence for ability. Christopher Chabrisand Daniel Smons (2010) refer to thisasthe llusion of Confidence.

# >> Overconfidence Among Investors

Barber and Odean (2000) examine data from a large discount brokerage firm 0 ver 1991 to 1996 and find :

- Investors who trade the most earn the lowest annual returns $(11\%)$ net of transaction costscompared to those who trade the least $(19\%)$

- Investors who switch to online trading, trade more actively, speculatively, and less profitably than before (Barber and Odean, 2002); Online trad ing reducestheir returnsfrom $2\%$ above the market beforeto $3\%$ below the market after.

-Men trade $45\%$ more actively than women and underperformed women by about $1\%$ a year (Barber and Odean, 2001). - Overconfidence isthe possble culprit.

Individual investors should be aware of overconfidence in their forecasting skills (for pricesand fundamentals) and excessive tra d ing that mig ht result from it.

# Availability Heuristic and Hindsight Bias

Availability Heuristic : Judging frequenciesand probabilitiesby the "ease with which examplescome to mind ." It isheavily influenced by media coverage.

- Death by accidents wasjudged 300 times more likely than death by diabetes, but the true ratio is 1:4.
- Disaster insurance purc hases shoot up after a disaster.
- Investors' estimatesof the probability of a crash probably increased in 2009 after observing the crash of 2008/09 even though crashesare rare.

Hind sig ht bias: "I knew it all along The tendency to revise the history of one'sbeliefs in light of what actually happened ; Common among stock market pundits. - The worse the consequence, the greater the hindsight bias (secondgue ssing) - Assessthe quality of a decision by the process, not by the outcome.

# The Law of Small Numbers

Which one of these earnings
Sequences appearpredictable
And how would you
Characterize the performance
Of thesefirms?

Annual Earnings Patterns
<html><body><table><tr><td></td><td>Firm A</td><td>Firm B</td><td>Firm C</td></tr><tr><td>Year 1</td><td>Decrease</td><td>Increase</td><td>Decrease</td></tr><tr><td>Year 2</td><td>Increase</td><td>Increase</td><td>Increase</td></tr><tr><td>Year 3</td><td>Decrease</td><td>Increase</td><td>Increase</td></tr><tr><td>Year 4</td><td>Decrease</td><td>Increase</td><td>Decrease</td></tr><tr><td>Year 5</td><td>Decrease</td><td>Increase</td><td>Decrease</td></tr></table></body></html>

The $l a w o f l a r g e n u m b e r s$ sa ysthat the average of resultsobtained from a large sample of data should be. Close to the population average, e.g., the average height of U.S. men.

People, however, behave asif the "law of large numbers" should apply to small samplesas well. This behavioraI biasisreferred to "tongue-in-cheek" asthe law of small numbers.

In small samples, random processes prod uce ma ny sequencesthat appearto people to be not random at all- llusion of Pattern.

Studies show that there is no hot hand in basketball. It isan example of our desire to seek pattern and causality in randomness.

# >> Anchoring

Visitorsto the San Francisco Exploratorium were asked one of the following setsof que stions:

Set 1: (1) lsthe height of the tallest redwood tree more or lessthan 1,20 ( feet? (2) What isthe height of the ta llest red wood? Set 2: (1) lsthe height of the tallest redwood tree more or lessthan 180 feet? (2) What isthe height of the tallest redwood?

The first group estimated 844 feet on average and the second estimated 282 feet.

This isanc horing. People anchor to the value in the question when estimating an unknown quantity. Anchorsthat are random can be as effective as potentia lly informative anc hors.

- Anc horing Index: (844-282)/(1,200-180) = 55%. This value istypica

In negotiations, the party that isthe first mover can use anc horsto its advantage. If you are the counter-party, focusattention on argumentsagainst the anc hor.

# Ba se Rate Neglect and Representativeness

# Consider this question:

" Tom is a graduate student at your state university. Please rank the following nine fields of graduate studies in order of the likelihood that Tom is now a student in each of these fields (1 is most likely, 9 isleast likely): business administration, computer science, engineering, humanities and education, law, medicine, library science, physical and life sciences, social science and social work."

- The answer dependson the proportion of graduate studentsenrolled in the different fields, statisticsthat should be readily available from the university.

- The proportion of students in a field isreferred to asthe $b a s e r a t e$ .Since more studentstypically enroll in humanities and education than in computer science, it ismore likely that Tom isa humanities student than a computer science student.

# Base Rate Neglect and Representativeness

The following isa persona lity sketch of Tom written during Tom'ssenior year in high sc hool by a psyc hologist, on the basisof psyc hological tests of unc erta in valid ity:

" Tom is of high intelligence, although lacking in true creativity. He has a need for order and clarity, and for neat and tidy systems in which every detail finds its appropriate place. His writing is rather dull and mechanical, occasionally enlivened by somewhat corny puns and flashes of imagination of sci-fi type. He has a strong drive for competence. He seemsto have little feeling and little sympathy for othe people, and does not enjoy interacting with others. Self-centered, he nonetheless hasa deep moral sense.'

Now, please rank the following nine fieldsof specialization (same as on the previous page) in order of the likelihood that Tom is now a graduate student in each of these fields.

Which field do you think most people pick asthe most likely now for Tom?

# Base Rate Neglect and Representativeness

Most people pick Computer Science, ignoring base rates. Thisis $b$ ase rate neglect. The choice of computer science isbased on the representativenessheuristic.

Repre sentativeness isthe act of judg ing. Probabilities by simila rity. $o f$ the desc ription to stereotypes, ignoring both the base ratesand the doubtsabout the accuracy of the description.

Since Tom'sdescription sounds $\sin i/a r$ to that of a nerd, people wrongly conc lude'that he is likely a computer science student. What isneeded to reach thisconcluson isevidence that he had high gradesin Math/Computer science. The desc ription is not informative.

The M system substitutesa question about simila rity in place of the question about probability $b e c a u s e$ the question about simila rity is easier to answer than the question about probability.

The correct way. To evaluate the probability. That Tom isa graduate student in any of those fieldsisto use Ba yes' $T h e o r e m$ , named after Reverend Thomas Bayes, an eig hteenth century English mathematic ian and Presb yterian minister.

# Regression to the Mean

# Sp orts Illustrated Jinx:

- Nov 20, 2013: Alabama QBfeatured on the Sl cover Nov 30, 2013: Alabama losesto Auburn

No jinx! Regression to the mean and bad luck.

Period 1 growth:

Frm 1: Above average growth $=$ Above average performance $^+$ Above average luck Frm 2: Below Average growth $=$ Below average performance $^+$ Below Average luck

 ![500](4acdc8b374f952327af42516a646e2f2dd941e50261699ff6c10f0970a9dabaf.jpg)

Period 2 growth

- Frm 1: Above average performance $+$ Average luck - Frm 2: Below average performance $^+$ Average luck

Extreme past performance tendsto moderate.

Lgnoring thiscan give rise to the extrapolation bias. Be aware of thisin evaluating the past performance of firms, money managers, etc.

# Affect Heuristic and Halo Effect

Affect Heuristic\*: People let their likesand disikesand emotions determine their beliefsabout the world, and rely on them to make jud gmentsand dec isions, regard lessof objective evidence.

- Attitudesabout environment, nuclear power, red meat, guns, cars, etc.
- If you like a CEO, you underestimate the risksof owning the stock and overestimate the benefitsof owning the stock regardlessof what the data says.
- Here the Ssystem acts in concert with the M system searching for inform ation to reinforce existing be liefs.

Halo effect: The tendency to like everything about a person, including thingsunobserved, is known asthe halo effect.

- Halo effect givestoo much weight to first impressions, often ignoring subsequent (perhapscontradictory) information.
- This isthe way the M system simplifiesthe complex task of evaluating someone's ab ilities.

# >> Confirmation Bias and Familia rity Bias

Confirmation bias: We test our beliefsand hypothesesby searching for confirming evidence, contrary to the recommended practice which isto test hypothesesby trying to refute them.

- The confirmatory biasof the M system favorsuncritical acceptance of ideas and suggestions.

- If you have an investment thesis, try looking for evidence that will refute your thesis: Talk to colleagues who are likely to question your thesis.

Familiarity bias: Thingsthat appear familiaralso appearto be true, e.g, a statement or an answerthat soundsfamiliar.

- Repetition makesit easy for people to believe in falsehoods because fa milia rity is not easily d istinguished from truth. Psychologists refer to this asthe llusion of Truth.

- The impression of familiarity is produced by the M system and the S system relies on it for a true/false judgment.

# Rationality in Economics

The expected utility theory in economicsmakestwo assumptions:

- People'sutility or "happiness" increases with their wealth (prefer more to le ss).

-People are $r i s k a v e r s e$ and they demand a risk premium for taking risk. This implies people'shappiness increasesat a decreasing rate (an extra million is worth more to usthan to Bill Gates).

Are people with equal wealth equally happy? - Kahneman and Tversky (1979)

# Prospect Theory and Loss Aversion

Today Jack and Jill have a wealth of \$5 million. - Yesterday, Jack had \$1 million and Jill had \$9 million. Are they equally Happy?

Consider these two problems: - Problem 1: Which do you choose? 》Get $\$900$ for sure or $90\%$ chance to get $\$1$ ,000. - Problem 2: Which do you choose? 》Lose $\$900$ for sure or $90\%$ chance to lose \$1, ooo?

Two conclusions:

- Happiness people experience isdetermined by recent $c h a n g e$ inwea lth not just the current $\mathinner{|{e V\in I}}$ of wealth (because Jack and Jill have different reference points). Expected utility theory lacksa reference point.

- People are loss averse because the sure lossin Problem 2 isaversive. People disike losing more than they like winning.

# Loss Averse Utility Func tion

The curve isSshaped.

People are risk averse over
Ga insand risk-seeking over
lo sse s.
The resp onse to losses is
Stronger than the response
To ga ins.
-A $\$100$ loss bringsmore pain than the a $\$100$ gain brings plea sure. This is loss a ve rsion.

 ![500](1e4990ec25286cb61db46be8f4fa067345a3ecea412a3da8b9445f74e33a76ba.jpg)

# Disposition Effect: Evidence of Loss Aversion

People sell winnerstoo early and hold on to loserstoo long.

- In the housing market, when pricesare fa lling, se llers set their asking pricestoo high, close to their original purc hase price.

- Brokerage customers in the U.S. exhib it disposition effect (Odean, 1998).

- Grinblatt and Keloharju (2001) find disposition effect in the Fnnish stock ma rket.

This is c onsiste nt with loss a version:

- You don't want to sell the asset and turn a paper loss into a sure loss. You hold on to the asset and the risk, hoping either the loss will be sma ller or it might turn into a gain.

This is inconsistent with rational behavior:
- Tax considerations would predict: sellosers and hold on to winners.
- This is not information-based trading : Stoc ks that individuals sell perform better than those they do not.

# Fra ming

Loss aversion suggeststhat dec ision ma king is sensitive to the way a lternativesare framed.

- Harvard Medical Sc hool study on the surgical treatment of lung cancer

》 Half the physician partic ipantsreceived statisticsabout survivalrates: " The onemonth survival rate is $90\%$ " The other half received statisticsabout morta lity rates: "There is a $10\%$ morta lity rate in the first month."
》 Guess which group chose surgery more? $84\%$ in the first group and only $50\%$ in the second group. The M system reactsdifferently to emotional wordsand the implied gains and losses: Survival is good, Morta lity is bad ,.
- Case 1: Given \$10,000, choose either 》 (A) a sure gain of \$5,000 or (B) a $50\%$ chance of winning \$10,000?
- Case 2: Given $\$20$ ,000, choose either 》(C) a sure lossof $\$5,000$ or (D) a $50\%$ chance of losing \$10,000?
Estate Tax vs. Death Tax: Whic h is more unpopular?
Watch out for framing effectswhen presented with choices.

# : Mental Accounting and Sunk Cost Fallacy

Consider the following pair of problems:

A woman has bought two $\$80$ tickets to the theater. When she arrives at the theater, she opens her wallet and discovers that the tickets are missing. Will she buy two more tickets to the play?

A woman goesto the theater, intending to buy two ticketsthat cost \$80 each. She arrives at the theater, opens her wallet, and discoversto her dismay that the \$160 with which she was going to make the purchase is missing. She could use her credit card. Will she buy the tickets?

- People who see only the first story believe that the woman will go home without seeing the show. Those who see only the second story believe that she will charge ticketsfor the show. Why the d ifferential response?

- Because of mental accounting and sunk cost fallacy.

》 Tic ketsto the play belong to the play account, lossof cash belongsto the general revenue account.

》 In the first case, there isa sunk cost fa llacy. The loss of tic kets is sunk. The question now iswhat should she do going forward?

# Intuitions vs. Fo rm ulas

Psyc hologist Paul Meehl (1954) conc luded $\boldsymbol{\mathcal{A}}\boldsymbol{a}$ tistic a / predictions (S system) were more accurate than the subjective clinica/predictions of tra ined professiona ls (M system).

- Meehl reviewed 20 studiesinvolving prediction of academic successof freshmen, psyc hiatric prognosis, criminal recidivism, success of naval tra inees, parole outcomesetc.

Subsequent studieshave shown that algorithm $\mathtt{s}$ match or exceed the accuracy of experts in environments involving a significant degree of uncertainty:

- Length of hosp ital sta ys, d iag nosis of ca rd iac d isease, susc eptib ility of babiesto SD syndrome, evaluating new born infants (Apgar score), college admissions, prospects of new business success, credit risk evaluation by banks, winnersof football games, future pricesof Bordeaux wine, oddsof recidivism among juvenile offenders, etc.

Algorithmsare less biased and more consistent than experts.

Qua ntitative/ Rule-based investment strategiesmight be superior to subjective recommendationsof investment experts.

# An Intuitive Model of Investing

Glamour Stocks (Low B/M, High Volume, LongTerm Positive Earnings Surprises)

Quantitative strategies combine value and momentum.

 ![500](24be346b009b04113b92fe151424d9b49b30dc949e450bc5bd74f33a24955f58.jpg)

(High B/M, Low Volume, Long-Term Negative Earnings Surprises)

La konishok, Shle ifer, and Vishny (1994): value strategieswork due to extrapolation bias.

Investorsextrapolate past performance too far into the future.

Investors overconfidentin their ability to predict the future based on the past.

Momentum Life Cycle Hypothesis (MLC) From: Lee and Swaminathan (2000)

# Stock screens based on Value and Momentum

Value:

Book-to-Market (B/M) Dividend yield (D/P) Earnings-to-Price (E/P) Sales-to-Price (S/P) Cash flow-to-Price (C/P) Poor long-run stock returns.

Momentum: Price Momentum Earnings Momentum
Earnings quality
External Financing

As of 2009, in the active U.S. Large Cap value space, quant managers managed only about $8\%$ oftheroughly $\$800$ billion in total assets under management (AUM).

Although, from 2000 to 2009, quant value managers outperformed fundamental value managers on a risk-adjusted basis (Lakonishok and Swaminathan, 2010).

# > Conclusions and Takeaways

Be skeptical of over-optimistic forecastsand recommendations.
Be skeptical of your own forecasting skill, overconfidence lurks.
Beware of the recommendationsof stock market experts. They suffer from extreme
Overc onfidence and hind sight bias.
Beware of the anchoring effectswhen you are a buyer.
Beware of the extrapolation biasand be mindfulof regression to the mean when evaluating past performance.

If you are an individual investor:

Beware of excessive trading in the short-term and focuson the long-term.
-Winnie-the-Pooh: “ Don't underestimate the value of doing nothing." Don't invest in strategiesor a ssets that you don't understand.
Focuson Valuation; Prepare, Pre-Commit, and Wait (standing ordersto buy).
Switchoff the noise (Cable showsetc.) and keep a real-time investment diary to learn from mistakes.

When making. Decisionsorevaluating alternatives, beware of the confirmatory bias. Look for the “outside" view.

Engage in a pre-mortem to overcome overconfident over-optimism.

Smple algorithms/formulas check listscan often trump expert intuition.

Quantitative orrule-based investment strategiesmight represent a way to avoid these p syc hologic al trap s.

# Answersto the CRT

# Figure 1 The Cognitive Reflection Test (CRT)

(1) A bat and a ball cost $\$1.10$ in total. The bat costs $\$1.00$ more than the ball. How much does the ball cost? --- cents
(2) If it takes 5 machines 5 minutes to make 5 widgets, how long would it take 100 machines to make 100 widgets? Minutes
(3) In a lake, there is a patch of lily pads. Every day, the patch doubles in size. If it takes 48 days for the patch to cover the entire lake, how long would it take for the patch to cover half of the lake? Days

1. 5 cents
2. 5 Minutes
3. 47 days

# Lecture Note 10 Value and Momentum

# Market efficiency hypothesis

Stock price equals intrinsic or fundamental value:

$$
\mathrm{P}=\mathrm{V}
$$

Price reflects all available information about a firm.

# Weak form market efficiency

Weak form efficiency says that current price contains all of the information in past prices.

# Semi-strong form market efficiency

Semi-strong form efficiency says that current prices contain all public information.

When we refer to efficient markets, we refer to this notion.

# Strong form market efficiency

Semi-strong form efficiency says that current prices contain all information both public and private.

# Evidence on violations of weak-form efficiency

Reversals at Short Horizons (1 month and 1 week).

> Buy Losers, Sell Winners - Contrarian strategy \* Momentum strategies at Intermediate Horizons (3 to 12 months).

: Buy Winners, Sell Losers - Momentum strategy.

Reversals at Long Horizons (3 to 5 years).

> Buy Losers, Sell Winners - Contrarian strategy.

Evidence on violations of semi-strong form efficiency

· Value strategies
Strategies involving any publicly available information:
· Earnings surprises, analyst forecasts, accounting information, etc.

# Momentum Life Cycle (Lee and Swaminathan, 2000)

Glamour Stocks (Low B/M, High Volume, LongTerm Positive Earnings Surprises)

 ![500](6d28573b050acc4e4d4708c6a7fc67f41250f46f0bc91bf61dbe6fa58c8981c4.jpg)

Early stage winner are Value Winners. Late stage winners are Glamour/Growth Winners. Early stage losers are Glamour/Growth Losers. Late stage losers are Value Losers.

# Value Strategies

> Value strategies have been popular at least since Graham and Dodd (1934) and possibly longer.

The idea is that smart investors can determine the intrinsic value of a firm through a full financial analysis of the firm and buy stocks whose intrinsic value is above the stock price $\mathrm {{V}} >\mathrm {{P}} $ Or $\mathrm{V/P}>1).$ ) and short stocks whose intrinsic value is below the stock price ( $\mathrm{(V<P}$ Or $\mathrm{V/P}<1\$

Stocks with high earnings-to-price ratio $(\mathrm{E/P})$ ,book equity-tomarket equity ratio (B/M), cash flows-to-price ratio (C/P), sales-to-price $(\mathrm{S}/\mathrm{P})$ and dividend yield (D/P) are considered undervalued stocks. They are referred to as value stocks.

OEarnings is last year's Net Income Before Extraordinary Items and Cash flows $=$ Earnings $+$ Depreciation & Amortization. O Earnings can also be FY 1 and FY 2 or the 12-month forecast.

Stocks with low E/P, B/M, C/P, S/P, and D/P are considered overvalued. They are referred to as growth or glamour stocks.

Earnings, Book, Cash flows, Sales or Dividends are rough proxies of the intrinsic value and are compared to the market price. We have already discussed estimating V using DCF models and comparable multiples.

How does a strategy of buying value stocks and selling glamour stocks perform?

# Do value strategies work?

Under the efficient markets paradigm, value stocks should not earn higher returns than glamour stocks (unless value stocks are systematically riskier).

Lakonishok, Shleifer and Vishny (1994) empirically test value strategies among U.S. stocks.

· Sort the universe of U.S stocks each year based on their valuation ratios (B/M, E/P, and C/P). Divide the universe into 10 equal-weighted portfolios and then compute the returns on each portfolio over the next 1 to 5 years. Repeat this process in April of each year between 1968 and 1989. The $10\%$ of the stocks with the highest valuation ratios (B/M, $\mathrm{E/P}$ , or C/P) are the most undervalued (value) stocks and the $10\%$ with the lowest ratios are the most overvalued (glamour or growth) stocks. · See Table I from LSV (1994) on the next page.

# TableI ReturnsforDecilePortfoliosBased on One-Dimensional Classifications byVarious Measures ofValue

At the end of each April between 1968 and 1989, 10-decile portfolios are formed in ascending orderbasedon $B/M$ $c/P$ $\scriptstyle{E/P}$ ,and GS. $B/M$ istheratioofbookvalueofequitytomarket value of equity; $C/P$ is the ratioof cash flow tomarketvalue of equity; $_{E/P}$ is the ratio of earnings to marketvalue of equity, and $_{G S}$ refers to preformation 5-year average growth rate of sales. The returns presented in the table are averages over all formation periods. $\kappa_{t}$ is the averagereturninyear $\boldsymbol{\mathbf{\rho}}_{t}$ after formation, $t=1,\ldots, 5,$ $A R$ is the average annual return over 5 postformation years. $\scriptstyle{C R_{5}}$ is the compounded 5-yearreturn assuming annual rebalancing. SAAR is the average annual size-adjusted return computed over 5 postformation years. The glamour portfolio refers to the decile portfolio containing stocks ranking lowest on $B/M$ $C/P$ ,or $\mathbf{\varDelta}E/P$ ,or highest on $_{G S}$ .The value portfolio refers to the decile portfolio containing stocks ranking highest on $B/M$ $C/P$ ,or $\mathbf{\Delta}E/P$ ,or lowest on GS.

<html><body><table><tr><td></td><td>Glamour</td><td colspan="7"></td><td></td><td>Value</td></tr><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td colspan="9">Panel A: B/M</td><td></td></tr><tr><td>R 1</td><td>0.110</td><td>0.117</td><td>0.135</td><td>0.123</td><td>0.131</td><td>0.154</td><td>0.154</td><td>0.170</td><td>0.183</td><td>0.173</td></tr><tr><td>R 2</td><td>0.079</td><td>0.107</td><td>0.140</td><td>0.145</td><td>0.153</td><td>0.156</td><td>0.169</td><td>0.164</td><td>0.182</td><td>0.188</td></tr><tr><td>R 3</td><td>0.107</td><td>0.132</td><td>0.155</td><td>0.167</td><td>0.165</td><td>0.172</td><td>0.191</td><td>0.207</td><td>0.196</td><td>0.204</td></tr><tr><td>R 4</td><td>0.081</td><td>0.133</td><td>0.136</td><td>0.160</td><td>0.170</td><td>0.169</td><td>0.188</td><td>0.204</td><td>0.213</td><td>0.207</td></tr><tr><td>R 5</td><td>0.088</td><td>0.137</td><td>0.163</td><td>0.175</td><td>0.171</td><td>0.176</td><td>0.216</td><td>0.201</td><td>0.206</td><td>0.215</td></tr><tr><td>AR</td><td>0.093</td><td>0.125</td><td>0.146</td><td>0.154</td><td>0.158</td><td>0.166</td><td>0.184</td><td>0.189</td><td>0.196</td><td>0.198</td></tr><tr><td>CR 5</td><td>0.560</td><td>0.802</td><td>0.973</td><td>1.045</td><td>1.082</td><td>1.152</td><td>1.320</td><td>1.375</td><td>1.449</td><td>1.462</td></tr><tr><td>SAAR</td><td>-0.043</td><td>-0.020</td><td>-0.003</td><td>0.004</td><td>0.006</td><td>0.012</td><td>0.024</td><td>0.028</td><td>0.033</td><td>0.035</td></tr><tr><td colspan="9">Panel B: C/P</td></tr><tr><td>R 1</td><td>0.084</td><td>0.124</td><td>0.140</td><td>0.140</td><td>0.153</td><td>0.148</td><td>0.157</td><td>0.178</td><td>0.183</td><td>0.183</td></tr><tr><td>R 2</td><td>0.067</td><td>0.108</td><td>0.126</td><td>0.153</td><td>0.156</td><td>0.170</td><td>0.177</td><td>0.180</td><td>0.183</td><td>0.190</td></tr><tr><td>R 3</td><td>0.096</td><td>0.133</td><td>0.153</td><td>0.172</td><td>0.170</td><td>0.191</td><td>0.191</td><td>0.202</td><td>0.193</td><td>0.204</td></tr><tr><td>R 4</td><td>0.098</td><td>0.111</td><td>0.146</td><td>0.159</td><td>0.166</td><td>0.172</td><td>0.182</td><td>0.192</td><td>0.223</td><td>0.218</td></tr><tr><td>R 5</td><td>0.108</td><td>0.134</td><td>0.161</td><td>0.162</td><td>0.187</td><td>0.177</td><td>0.191</td><td>0.209</td><td>0.212</td><td>0.208</td></tr><tr><td>AR</td><td>0.091</td><td>0.122</td><td>0.145</td><td>0.157</td><td>0.166</td><td>0.171</td><td>0.180</td><td>0.192</td><td>0.199</td><td>0.201</td></tr><tr><td>CR 5</td><td>0.543</td><td>0.779</td><td>0.969</td><td>1.074</td><td>1.158</td><td>1.206</td><td>1.283</td><td>1.406</td><td>1.476</td><td>1.494</td></tr><tr><td>SAAR</td><td>-0.049</td><td>-0.025</td><td>-0.006</td><td>0.005</td><td>0.013</td><td>0.019</td><td>0.025</td><td>0.034</td><td>0.037</td><td>0.039</td></tr><tr><td colspan="9">Panel C: E/P</td></tr><tr><td>R 1</td><td>0.123</td><td>0.125</td><td>0.140</td><td>0.130</td><td>0.135</td><td>0.156</td><td>0.170</td><td>0.180</td><td>0.193</td><td>0.162</td></tr><tr><td>R 2</td><td>0.101</td><td>0.113</td><td>0.124</td><td>0.143</td><td>0.167</td><td>0.164</td><td>0.180</td><td>0.185</td><td>0.183</td><td>0.174</td></tr><tr><td>R 3</td><td>0.118</td><td>0.138</td><td>0.157</td><td>0.171</td><td>0.171</td><td>0.191</td><td>0.198</td><td>0.188</td><td>0.188</td><td>0.195</td></tr><tr><td>R 4</td><td>0.111</td><td>0.124</td><td>0.145</td><td>0.151</td><td>0.157</td><td>0.159</td><td>0.198</td><td>0.199</td><td>0.205</td><td>0.214</td></tr><tr><td>R 5</td><td>0.119</td><td>0.129</td><td>0.151</td><td>0.167</td><td>0.171</td><td>0.168</td><td>0.196</td><td>0.201</td><td>0.211</td><td>0.207</td></tr><tr><td>AR</td><td>0.114</td><td>0.126</td><td>0.143</td><td>0.152</td><td>0.160</td><td>0.167</td><td>0.188</td><td>0.191</td><td>0.196</td><td>0.190</td></tr><tr><td>CR 5</td><td>0.717</td><td>0.808</td><td>0.953</td><td>1.031</td><td>1.102</td><td>1.168</td><td>1.370</td><td>1.393</td><td>1.446</td><td>1.388</td></tr><tr><td>SAAR</td><td>-0.035</td><td>-0.024</td><td>-0.009</td><td>-0.001</td><td>0.005</td><td>0.013</td><td>0.026</td><td>0.026</td><td>0.029</td><td>0.019</td></tr></table></body></html>
# Summary of key findings

· Value stocks outperform glamour stocks each year over the next five years. The results become stronger in Years 2 to 5.

Value strategies are long-term strategies with low portfolio turnover. Investors need to be patient to earn abnormal returns with value strategies.

·Violation of semi-strong form market efficiency.

# Why do value strategies outperform?

LsV argue it is because of the extrapolation bias. Investors extrapolate past performance too far into the future for both value stocks and glamour stocks. See Table V of the paper.
. Value stocks have lower growth rates in earnings, sales, and cash flows compared to glamour stocks.
Investors mistakenly believe glamour stocks will continue to grow at a faster rate for a very long time while they assume that value stocks will grow at a slower rate also for a long time. They ignore regression to mean and extrapolate the past too far into the future. They overreact to past performance.
Investors are too optimistic about glamour (growth) stocks and too pessimistic about value stocks. As a result glamour stocks become overvalued and value stocks become undervalued.

# Table V Fundamental Variables, Past Performance, and Future Performance of Glamour and Value Stocks

Panel 1: At the end of each April between 1968 and 1989, 10-decile portfolios are formed based on the ratio of end-of-previous-year's book value of equity to end-of-April market value of equity. Numbers are presented for the first (lowest $B/M$ ）andtenth (highest $B/M$ ) deciles. These portfolios are denoted Glamour and Value, respectively.

Panel 2: At the end of each April between 1968 and 1989, 9 groups of stocks are formed. The stocks are independently sorted in ascending order into 3 groups ((1) bottom 30 percent, (2) middle 40 percent, (3) top 30 percent) based on $c/P$ ,the ratio of cash flow to marketvalue of equity, and $\mathbf{\Delta}_{G S}$ ,thepreformation 5-year weightedaverage salesgrowthrank. Numbers are presented for $(C/P_{1}$ $G S_{3}$ ), thebottom 30 percentby $C/P$ and the top 30 percent by GS, and for $c/P_{3}$ $\boldsymbol{G S}_{1})$ the top 30 percent by $c/P$ and the bottom 30 percent by GS. These portfolios are denoted Glamour and Value, respectively.

All numbers in the table are averages over all formation periods.

$E/P$ ， $c/P$ $s/P$ $D/P$ $B/M$ ,and SIZE, defined below, use the end-of-April market value of equity and preformationyear accounting numbers. $E/P$ is the ratio of earnings to market value of equity. $s/P$ is the ratio of sales to market value of equity. $D/P$ is the ratio of dividends to market value of equity. $B/M$ is the ratio of book value to market value of equity. SIZE is the total dollar value of equity (in millions). $A E G_{(\iota, J)}$ is the geometric average growth rate of earningsforthe portfoliofromyear $^i$ to year $j$ $A C G_{(i_{2}, j)}$ and $A S G_{(i, j)}$ are defined analogously for cash flow and sales, respectively. $R E T U R N_{(-3,0)}$ is the cumulative stock return on the portfolio over the 3 years prior to formation.

<html><body><table><tr><td></td><td colspan="2">Panel 1</td><td colspan="2">Panel 2</td></tr><tr><td></td><td>Glamour B/M</td><td>Value B/M 10</td><td>Glamour C/P, GS 3</td><td>Value C/P 3, GS,</td></tr><tr><td colspan="5">Panel A:FundamentalVariables</td></tr><tr><td>E/P</td><td>0.029</td><td>0.004</td><td>0.054</td><td>0.114</td></tr><tr><td>C/P</td><td>0.059</td><td>0.172</td><td>0.080</td><td>0.279</td></tr><tr><td>S/P</td><td>0.993</td><td>6.849</td><td>1.115</td><td>5.279</td></tr><tr><td>D/P</td><td>0.012</td><td>0.032</td><td>0.014</td><td>0.039</td></tr><tr><td>B/M</td><td>0.225</td><td>1.998</td><td>0.385</td><td>1.414</td></tr><tr><td>SIZE</td><td>663</td><td>120</td><td>681</td><td>390</td></tr><tr><td colspan="5">PanelB: PastPerformance-GrowthRates andPastReturns</td></tr><tr><td>AEG (-5,0)</td><td>0.309</td><td>-0.274</td><td>0.142</td><td>0.082</td></tr><tr><td>ACG (-5,0)</td><td>0.217</td><td>-0.013</td><td>0.210</td><td>0.078</td></tr><tr><td>ASG (-5,0)</td><td>0.091</td><td>0.030</td><td>0.112</td><td>0.013</td></tr><tr><td>RETURN (-3,0)</td><td>1.455</td><td>-0.119</td><td>1.390</td><td>0.225</td></tr><tr><td colspan="5">Panel C:FuturePerformance</td></tr><tr><td>AEG (0., 5)</td><td>0.050</td><td>0.436</td><td>0.089</td><td>0.086</td></tr><tr><td>ACG (0,5)</td><td>0.127</td><td>0.070</td><td>0.112</td><td>0.052</td></tr><tr><td>ASG (0,5)</td><td>0.062</td><td>0.020</td><td>0.100</td><td>0.037</td></tr><tr><td>AEG (2,5)</td><td>0.070</td><td>0.215</td><td>0.084</td><td>0.147</td></tr><tr><td>ACG (2,5)</td><td>0.086</td><td>0.111</td><td>0.095</td><td>0.088</td></tr><tr><td>ASG (2,5)</td><td>0.059</td><td>0.023</td><td>0.082</td><td>0.038</td></tr></table></body></html>

# Are value stocks riskier?

Fama and French (1992, 1993, and 1996) also find evidence that value stocks earn higher returns than growth or glamour Stocks.

· Fama and French (1993) find high B/M stocks tend to have lower standard deviations and market betas than do low B/M stocks (Tables 2 and 4). Thus, on traditional measures of risk, value stocks are less risky.

They argue, however, that value stocks face a higher systematic earnings distress risk than do glamour stocks:

0 The earnings distress risk, according to FF, is due to the fact value stocks typically experience persistently low earnings, a risk not captured by the market beta.

They propose a three-factor model to explain the variation in stock returns and for performance measurement:

$$
R_{i t}-r_{f t}=a_{i}+b_{i}\left (r_{m t}-r_{f t}\right)+s_{i}S M B_{t}+h_{i}H M L_{t}+\varepsilon_{t}
$$

Rit-rft is the excess return on the stock or the portfolio
$\mathrm {{r}_{\mathrm{{mt}-\mathrm{{r}_{\mathrm{{ft}} }}}}}$ is the Market factor
SMB (Small Minus Big) is the Size factor, return spread between small stocks and large stocks.
HML (High Minus Low) is the Value factor, return spread between high B/M (value) and low B/M (growth) stocks.

The risk vs. Mispricing debate is still unsettled.

# Contrarian strategies based on past stock returns

Another manifestation of value strategies is contrarian strategies based on past stock price performance (recall the Momentum Life Cycle).

Buy long-run losers and sell long-run winners.

 ![500](0e343b6557b45ded5af84677516f3a714daceadd051def2564888d22ac254312.jpg)

Stocks with high past performance (high stock returns) underperform stocks with poor past performance where past performance is measured over the previous 5 years.

This is most likely due to the extrapolation bias. > Violation of weak form market efficiency.

# Evidence on contrarian strategies

- DeBondt and Thaler (1985) provided initial evidence of this strategy. Results from Fama and French (1996) below.

At the beginning of each year or each month (say January 1, 2014) rank all stocks by their 5 year returns.

Top $10\%$ (R 10) of the stocks with the highest returns are the long-term winners. Bottom $10\%$ (R 1) with the lowest returns are the long-term losers. Returns of (R 1-R 10) are below.

Table VI Average Monthly Excess Returns (in Percent) on Equal-Weight NYSE Deciles Formed Monthly Based on Continuously Compounded Past Returns

At the beginning of each month t, all NYSE firms on CRSP with returns for months t - x to t - y are allocated to deciles based on their continuously compounded returns between t - x and t - y. For example, firms are allocated to the 12-2 portfolios for January 1931 based on their continuously compounded returns for January 1930 through November 1930. Decile 1 contains the NYSE stocks with the lowest continuously compounded past returns. The portfolios are reformed monthly, and equal-weight simple returns in excess of the one-month bill rate are calculated for January 1931 (3101) to December 1993 (9312). The table shows the averages of these excess returns for 6307 to 9312 (366 months) and 3101 to 6306 (390 months).

<html><body><table><tr><td></td><td>Portfolio Formation</td><td colspan="10">Average Excess Returns</td></tr><tr><td>Period</td><td>Months</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>9</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>6307-9312</td><td>60-2</td><td>0.86</td><td>0.76</td><td>0.73</td><td>0.75</td><td>0.70</td><td>0.71</td><td>0.74</td><td>0.70</td><td>0.66</td><td>0.73</td></tr><tr><td>6307-9312</td><td>60-13</td><td>1.16</td><td>0.81</td><td>0.77</td><td>0.76</td><td>0.74</td><td>0.72</td><td>0.72</td><td>0.73</td><td>0.54</td><td>0.42</td></tr><tr><td>3101-6306</td><td>60-2</td><td>2.49</td><td>1.78</td><td>1.74</td><td>1.50</td><td>1.39</td><td>1.33</td><td>1.27</td><td>1.18</td><td>1.28</td><td>1.14</td></tr><tr><td>3101-6306</td><td>60-13</td><td>2.62</td><td>1.85</td><td>1.63</td><td>1.61</td><td>1.43</td><td>1.24</td><td>1.34</td><td>1.28</td><td>1.08</td><td>1.01</td></tr></table></body></html>

Returns are monthly averages in percent.

Loser (1) outperforms winner (1 o) by $0.13\%$ to $1.6\%$ a month depending on the time-period (weaker post 1963). The (60-13) strategy which skips the most recent year performs better. Why?

# Value Strategies in the United States

Value vs. Growth: 1927-2014 Value (High B/M, Top $30\%$ ) - Growth (Low B/M, Bottom $30\%$ B/M: Book Value of Equity / Market Value of Equity

 ![500](34ee74b7e5083dd19d0f3fc2459c6dffae2a52f603cfe20a2648ab5a02d59316.jpg)

 ![500](7d0da92bad200def0a10b6613ba5e2f7fe752c349596b84463eaa953d0d9f815.jpg)
Value Premium (HML $=$ High B/M - Low B/M) in Developed International Markets: 1991-2014
Data from KenFrench's website http://mba.tuck dartmcuth. Edu/pages/faculty/ken french/data_library. Html

# Fundamental Analysis and Value Investing

· Piotroski (20 o 0) argues that financial statement variables can be used to separate value stocks into value winners and value losers (see the Momentum Life Cycle).
· Value winners are value firms that have stronger future prospects and are likely to turnaround while value losers are value trap firms which may be financially distressed and less likely to turnaround.
· Piotroski creates an aggregate fundamental signal based on several accounting ratios and uses the signal to divide the $20\%$ Of the stocks (in NYSE, AMEX, and Nasdaq) with the highest B/M ratios (most undervalued stocks) into winners and losers.
· Piotroski constructs his winner and loser portfolios every year from 1976 to 1996 based on the prior fiscal year's data and computes buy-and-hold returns over the next year.
· Piotroski refers to his fundamental signal as the $F.$ Score.
· How would you use the F-Score in your final valuation project?

# F-Score

Construct binary variables (1 for positive signals and 0 for negative signals) based on nine fundamental ratios. Changes are computed as this year's ratio minus last year's ratio (fiscal or trailing 12 month).

# Profitability

1) Net income/Total Assets (ROA): (1 if positive, 0 otherwise) Positive ROA is a good signal (you can also use ROIC).

2) Cash flow from operations/Total Assets (CFO): (1 if positive, 0 otherwise). Positive CFO is a good signal.

3) Change in ROA (△ROA): (1 if an increase, 0 otherwise). An increase in ROA is a good signal.

# Leverage/Liquidity

4) Change in LT debt-to-total assets (△LEVER) (1 if a decrease, 0 otherwise). A decrease in leverage is a good signal.

5) Change in a firm's Current Ratio (ratio of current assets to current liabilities) ALIQUID (1 if an increase, 0 otherwise). An increase in liquidity is a good signal.

6) A dummy variable (EQ_OFFER) equal to 1 if the firm did not issue equity in the previous year, zero otherwise. Why?
# Operating Efficiency

7) Change in Gross Margin ratio (Gross income/Sales) (1 if an increase, O otherwise).

8) Change in Asset Turnover ratio (Sales/Total Assets) (1 if an increase, O otherwise) (you can also use Sales/Invested Capital).

Recall ROIC tree (Equation 4, page 8) in Lecture Note 4:

ROIC $=$ Operating Profit Margin \* Invested Capital Turnover

# Accrual

9) Accrual $=$ (Net Income - Cash flow from operations)/Total Assets $={\mathrm{ROA}}-{\mathrm{CFO}}$ (1 for negative accruals, O for positive accruals). Positive or high accruals suggest a firm is not generating cash flows consistent with its reported earnings. We will discuss this in detail in the next lecture.

F-Score $=$ Sum of the 9 binary scores above.

Maximum F-Score is 9; Minimum F-Score is 0.

A low F-score is bad and a high F-score is good.

Use F-Score to divide value stocks into value winners and value losers.
# Performance of F-Score Portfolios

High F-score - Low F-score earns about $23\%$ on average over the next twelve months (see Table 3).
·High F-Score is the long/buy side; Low F-Score is short/sell side.
· Returns are high among small firms which are illiquid. Among large firms, hedge returns are concentrated on the short side. See Table 4. Shorting is costly for individuals. Therefore, we focus on the long/buy side of the strategy which is high F-score. This suggests returns to this strategy are likely to be low in long only portfolios and for large institutional portfolios. These investors face capacity constraints in investing in small-cap and especially micro-cap stocks because of liquidity considerations.
High (low) F-score stocks exhibit positive (negative) price momentum consistent with the intuition of the Momentum Life Cycle (Table 6).
· See Table 7 for regression results that control for other effects.
· See Figure 1 for annual long-short returns.
· Data from 1976-1996.

This table presents buy-and-hold rewrns to a fundamental invesunent strategy based on purchasing high BM firms wth strong fundatmental signals F_SCORE is equal to the sum of nine indivdual bimary signals, or F_SCORE = F_ ROA F_△ROA +F_CFO +F_ACCRUAL +F_AMARGIN $^+$ F_ATURN+F_ALEVER+F_ALIQUID $\cdot$ EQ_OFFER, whereeach binary signal equals one (zero) if the underiying realzation is a good (bad) signal about future firm performance A F_SCoRE equal to zero (nine) means the firm possesses the least (most) favorabic set of financial signals The Low F_SCORE porfoho consists of firms with an aggregate scoie of 0 or 1; the High F_SCORE porfoho consusts of firms with a score of 8 or 9

<html><body><table><tr><td>Panel A: One-Year RawReturnsa</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>Mean</td><td>%01</td><td>25%</td><td>Median</td><td>75%</td><td>90%</td><td>%Positive</td><td></td></tr><tr><td>All Firms</td><td>0.239</td><td>-0391</td><td>-0.150</td><td>0.105</td><td>0438</td><td>0.902</td><td>0 610</td><td>14,043</td></tr><tr><td>F_SCORE</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0</td><td>0 112</td><td>-0.688</td><td>-0.302</td><td>0000</td><td>0.511</td><td>1.051</td><td>0.491</td><td>57</td></tr><tr><td>1</td><td>0079</td><td>-0.590</td><td>-0.298</td><td>~0.042</td><td>0253</td><td>0.741</td><td>0454</td><td>339</td></tr><tr><td>2</td><td>0.159</td><td>-0.512</td><td>-0.278</td><td>0.024</td><td>0369</td><td>0.898</td><td>0520</td><td>859</td></tr><tr><td></td><td>0.159</td><td>-0.513</td><td>-0.250</td><td>0.034</td><td>0368</td><td>0.867</td><td>0535</td><td>1618</td></tr><tr><td>4</td><td>0.202</td><td>-0.412</td><td>-0.181</td><td>0 070</td><td>0412</td><td>0875</td><td>0.573</td><td>2462</td></tr><tr><td>5</td><td>0234</td><td>-0.375</td><td>-0.146</td><td>0114</td><td>0.447</td><td>0.900</td><td>0616</td><td>2787</td></tr><tr><td>6</td><td>0.294</td><td>-0.833</td><td>-0.107</td><td>0143</td><td>0.470</td><td>0908</td><td>0651</td><td>2579</td></tr><tr><td>7</td><td>0.304</td><td>-0.294</td><td>-0.070</td><td>0164</td><td>0.487</td><td>0941</td><td>0.681</td><td>1894</td></tr><tr><td>8</td><td>0.304</td><td>-0265</td><td>-0.066</td><td>0.163</td><td>0483</td><td>0 922</td><td>0.675</td><td>1115</td></tr><tr><td>6</td><td>0.341</td><td>-0 272</td><td>-0.102</td><td>0.167</td><td>0506</td><td>1.200</td><td>0.661</td><td>333</td></tr><tr><td>Low Score</td><td>0078</td><td>-0.589</td><td>-0.300</td><td>-0.027</td><td>0.270</td><td>0.773</td><td>0460</td><td>396</td></tr><tr><td>High Score</td><td>0.313</td><td>-0267</td><td>-0.074</td><td>0166</td><td>0.484</td><td>0.955</td><td>0672</td><td>1448</td></tr><tr><td>High-All t-Statistic/</td><td>0074</td><td>0124</td><td>0.076</td><td>0061</td><td>0.046</td><td>0053</td><td>0.062</td><td></td></tr><tr><td>(p-Value)</td><td>3279</td><td></td><td></td><td>(0.000)</td><td></td><td></td><td>(0 000)</td><td></td></tr><tr><td>Bootstrap Result</td><td></td><td></td><td>0/1000</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(p-Value)</td><td>1/1000 (0.001)</td><td>0/1000 (0.000)</td><td>(0 000)</td><td>0/1000 (0.000)</td><td>16/1000 (0 016)</td><td>110/1000 (0.110)</td><td></td><td></td></tr><tr><td>High-Low</td><td></td><td>0322</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>{-Statistic/ (p-Value)</td><td>0.235</td><td></td><td>0226</td><td>0.198</td><td>0214</td><td>0.182</td><td>0.212</td><td></td></tr></table></body></html>

TABLE 4 One-Year Marret-Adjusted Buy-and-Hold Returns to a Value Investment Strategy Based on Fundamental Signals by SrzePartitron
<html><body><table><tr><td rowspan="3"></td><td colspan="3">Small Firms</td><td colspan="3">MediumFirms</td><td colspan="3">Large Firms</td></tr><tr><td>Mean</td><td>Median</td><td>2</td><td>Mean</td><td>Median</td><td>n</td><td>Mean</td><td>Median</td><td></td></tr><tr><td>All Firms</td><td>0.091</td><td>-0 077</td><td>8302</td><td>0008</td><td>-0.059</td><td>3906</td><td>0003</td><td>-0.028</td><td>1835</td></tr><tr><td>F.SCORE</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0</td><td>0.000</td><td>-0.076</td><td>32</td><td>-0 146</td><td>-0235</td><td>17</td><td>-0.120</td><td>-0.047</td><td>8</td></tr><tr><td>1</td><td>-0.104</td><td>-0 227</td><td>234</td><td>-0 083</td><td>-0.228</td><td>79</td><td>-0136</td><td>-0.073</td><td>26</td></tr><tr><td>2</td><td>-0.016</td><td>-0 171</td><td>582</td><td>-0.045</td><td>-0.131</td><td>218</td><td>0.081</td><td>-0.076</td><td>59</td></tr><tr><td>3</td><td>0.003</td><td>-0.168</td><td>1028</td><td>-0.049</td><td>-0108</td><td>429</td><td>-0036</td><td>-0.068</td><td>161</td></tr><tr><td>4</td><td>0.058</td><td>~0116</td><td>1419</td><td>-0.024</td><td>-0.104</td><td>687</td><td>-0.002</td><td>-0.023</td><td>356</td></tr><tr><td>5</td><td>0079</td><td>-0.075</td><td>1590</td><td>0.028</td><td>-0 060</td><td>808</td><td>-0.004</td><td>-0.031</td><td>686</td></tr><tr><td>6</td><td>0.183</td><td>-0030</td><td>1438</td><td>0029</td><td>-0 041</td><td>736</td><td>0.012</td><td>-0 004</td><td>405</td></tr><tr><td>7</td><td>0.182</td><td>0.005</td><td>1084</td><td>0.027</td><td>-0 028</td><td>540</td><td>0.028</td><td>-0.015</td><td>270</td></tr><tr><td>8</td><td>0 170</td><td>0.001</td><td>671</td><td>0081</td><td>0024</td><td>312</td><td>0.012</td><td>-0 041</td><td>132</td></tr><tr><td>9</td><td>0.204</td><td>-0.017</td><td>224</td><td>0.068</td><td>0.032</td><td>80</td><td>0.059</td><td>-0.045</td><td>29</td></tr><tr><td>Low Score</td><td>T 60'0</td><td>-0.209</td><td>266</td><td>-0.094</td><td>-0.282</td><td>96</td><td>-0 132</td><td>-0.066</td><td>34</td></tr><tr><td>High Score</td><td>0.179</td><td>-0.007</td><td>895</td><td>0.079</td><td>0.024</td><td>392</td><td>0.020</td><td>-0.045</td><td>161</td></tr><tr><td>High-All t-Statistic/</td><td>0.088</td><td>0.070</td><td></td><td>0.071</td><td>0083</td><td></td><td>0.017</td><td>-0 017</td><td></td></tr><tr><td>(pValue)</td><td>2.456</td><td>(0.000)</td><td></td><td>2.870</td><td>(0.000)</td><td></td><td>0.872</td><td>(0.203)</td><td></td></tr><tr><td>High-Low t-Statistic/</td><td>0.270</td><td>0.202</td><td></td><td>0.173</td><td>0256</td><td></td><td>015</td><td>0021</td><td></td></tr></table></body></html>

\*Each year, all firms on Compustat wth sufhcient size and BM data are ranked on the bass of the most recent fiscal year-end market capitalization. The 33 3 and 66 7 percentile cutofs from the prior year's.distribuuon of firm size (MVE) are used to classify the high BM firms mnto small, mednum, and large firms each year All other definitions and test statistics are as described in table 3

$59\%$ of the sample $(\mathbf{n}{=}8{,}302)$ is concentrated among small firms and only $13\%$ $({\bf n}=1,835)$ is concentrated among large firms. The excess returns in large cap value portfolios are lower. In small cap and especially micro-cap value portfolios, capacity may be limited because of liquidity constraints. · The median market cap of Pietroski's sample (see Table 6) is only \$14.37 million!

 ![500](79bfd3a8f627d094f02e272cb783646632e8a5961fdd3aa3c651c4e7eb7b3ef5.jpg)
FIG. 1 --One-year market-adjusted returns to a hedge portfolio based on a fundamental analysis strategy by calendar year. This figure documents one-year market-adjusted returns by calendar year to a hedge portfolio taking a long position in firms with a strong $F_{-}S C O R E$ $(F_{-}S C O R E$ greater than or equal to 5) and a short posihon in firms with a weak F_SCORE (F_SCORE less than 5) Returns are cumulated over a one-year period startung four months after fiscal year-end. A market-adjusted return is defined as the firm's 12-month buy-andhold return less the buy-and-hold return on the value-weighted market index over the same investmenthorizon

The figure above suggests the F-score long-short strategy earned positive returns in almost every year from 1977 to 1996.

The returns may not be as high for large institutional investors because of liquidity considerations.

Nevertheless, the intuition behind the F-Score is appealing.
# Price momentum strategies

 ![500](6229daeef596bdd20d71e243f365b47da7930d904d58137d6354d9c8c61ae779.jpg)

> Momentum is evidence of return continuation. High returns followed by high returns and vice-versa.

Returns over the 3 to 12 month horizon (referred to as the medium-term) are characterized by price momentum. - Underreaction to news is often cited as the cause of price momentum.

# Implementing price momentum strategies

At the beginning of each month (say January 1, 2000), rank all available stocks by their prior 6-month returns.

Divide the stocks into 10 portfolios. Top $10\%$ (R 10) of stocks with the highest returns are the medium-term winners and bottom $10\%$ (R 1) are the medium-term losers.

Buy the winners (R 10) and sell the losers (R 1).

Contrast this with long-horizon contrarian strategies where we buy long-term losers and sell long-term winners.

Hold this long-short momentum portfolio for horizons ranging from 3 to 12 months and compute the average return earned by this portfolio.

Jegadeesh and Titman (1993) originally implemented this strategy using historical data from 1963 to 1990 and found that the winners outperformed the losers on average by $0.7\%$ to $1.5\%$ a month. Annualized, this translates to $8.4\%$ to $18\%$ a year.

Momentum strategies are higher portfolio turnover strategies compared to value strategies and hence face potentially higher transaction costs.

# Momentum results from Lee and Swaminathan (2000)

# TableI Returns to Price Momentum Portfolios

This table presents average monthly and annual returns in percentages for price momentum portfolio strategies involving NYSE/AMEX stocks for the time period from 1965 to 1995. At the beginning of each month starting in January 1965, all stocks in the NYSE and AMEX are sorted based on their previous $J$ months' returns and divided into 10 equal-weighted portfolios. R 1 represents the loser portfolio with the lowest returns, and $R 10$ represents the winner portfoliowith the highest returns during the previous $\J_{\parallel}$ months. $\kappa$ represents monthly holding periods where $K=\mathrm{three}$ , six, nine, or 12 months. Monthly holding period returns are computed as an equal-weighted average of returns from strategies initiated at the beginning of this month and past months. The annual returns (Year 1, Year 2, Year 3, Year 4, and Year 5) are computed as event time returns for five 12-month periods following the portfolio formation date. Return refers to the geometric average monthly return in percentages, and Volume represents the average daily turnover in percentages, both measured over the portfolio formation period, J.SzRnk represents the time-series average of the median size decile of the portfolio (based on NYSE/AMEX stocks in the sample) on the portfolio formation date. Price represents the time-series average of the median stock price of the portfolio in dollars on the portfolio formation date. The numbers in parentheses represent $t$ statistics. The $t$ statisticsfor monthly return ( $\kappa=$ three, six nine, or 12) are simple t-statistics, whereas those for annual returns are based on the Hansen-Hodrick (1980) correction for autocorrelation up to lag 11.

<html><body><table><tr><td></td><td></td><td></td><td></td><td></td><td></td><td colspan="4">Monthly Returns</td></tr><tr><td>J</td><td>Portfolio</td><td>Return</td><td>Volume</td><td>SzRnk</td><td>Price</td><td>K=3</td><td>K=6</td><td>K=9</td><td>K = 12</td></tr><tr><td>6</td><td>R 1</td><td>-6.36</td><td>0.1671</td><td>3.56</td><td>9.00</td><td>0.59 (1.39)</td><td>0.58 (1.38)</td><td>0.57 (1.40)</td><td>0.65 (1.58)</td></tr><tr><td></td><td>R 5</td><td>0.25</td><td>0.1212</td><td>6.13</td><td>20.79</td><td>1.31</td><td>1.29</td><td>1.31</td><td>1.30</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>(4.66)</td><td>(4.55)</td><td>(4.59)</td><td>(4.52)</td></tr><tr><td>R 10</td><td></td><td>8.30</td><td>0.2349</td><td>5.05</td><td>19.41</td><td>1.62</td><td>1.62</td><td>1.65</td><td>1.53</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>(4.76)</td><td>(4.72)</td><td>(4.78)</td><td>(4.45)</td></tr><tr><td></td><td>R 10 - R 1</td><td></td><td></td><td></td><td></td><td>1.04</td><td>1.05</td><td>1.08</td><td>0.88</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>(3.89)</td><td></td><td>(4.92)</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(4.28)</td><td></td><td>(4.18)</td></tr></table></body></html>

The above table reproduces only a portion of Table I.

· J refers to the measurement period and K refers to the holding period. Past returns are computed for the prior 6 months $(\mathrm{J}{=}6)$ ,the momentum portfolios constructed, and the stocks held for 3, 6, 9, or 12 months $(\mathrm{K}{=}3$ , 6, 9, or 12). The holding period returns are reported in $\%$ per month. · Winners outperform losers by about $1\%$ per month or $12\%$ annualized which is a violation of weak-form market efficiency. · Multiple monthly averages by 12 to annualize them. The numbers in parentheses are t-statistics. T-statistic $>2$ is significant.
# Price Momentum in the U.S.: 1927-2014 Winner (Top $30\%$ ) - Loser (Bottom $30\%$ Return measured from month -12 to -2

 ![500](a44f5e2dc30280090960f00446a2e2ddab855fede713c2c957551ced023013ab.jpg)

# Momentum Premium in Developed Intl Markets from 1991-2014 WML $=$ Winner (Top $30\%$ ) - Loser (Bottom 30%) Return measured from month -12 to -2

 ![500](c1aaf389abc8d6c7295ccd40b5a45b9256f7f34b34cf5495ed959d11503a72af.jpg)
Data from Ken French's website http://mba.tuck.dartmouth.edupages/faculty/ken french/data_library. Html

# Price Momentum and Trading Volume

· Lee and Swaminathan (2 oo 0) show that momentum profits can be enhanced by combining it with trading volume. Trading volume (V): Shares Traded/Shares Outstanding. Compute average daily trading volume over J months. Form portfolios based on Price Momentum and Trading Volume through independent sorts. Form 10 portfolios based on momentum and 3 portfolios based on turnover; the intersection provides 30 portfolios. A portion of Table II below.

<html><body><table><tr><td></td><td></td><td colspan="4">K=3</td><td colspan="4">K=6</td></tr><tr><td>J</td><td>Portfolio</td><td>V 1</td><td>V 2</td><td>V 3</td><td>V 3-V 1</td><td>V 1</td><td>V 2</td><td>V 3</td><td>V 3-V 1</td></tr><tr><td>3</td><td>R 1</td><td>1.24 (3.17)</td><td>0.96 (2.32)</td><td>0.19 (0.44)</td><td>-1.05 (5.11)</td><td>1.19 (3.06)</td><td>0.87 (2.16)</td><td>0.25 (0.59)</td><td>-0.93 (-5.14)</td></tr><tr><td></td><td>R 5</td><td>1.41 (5.62)</td><td>1.45</td><td>1.20</td><td>-0.20</td><td>1.42</td><td>1.38</td><td>1.23</td><td>-0.19</td></tr><tr><td></td><td>R 10</td><td>1.25</td><td>(5.02) 1.61</td><td>(3.40) 1.45</td><td>(-1.28) 0.20</td><td>(5.62) 1.43</td><td>(4.77) 1.59</td><td>(3.48) 1.36</td><td>(-1.20) -0.07</td></tr><tr><td></td><td>R 10-R 1</td><td>(4.12) 0.01</td><td>(4.93) 0.66</td><td>(4.05) 1.26</td><td>(1.09) 1.26</td><td>(4.68) 0.25</td><td>(4.87) 0.73</td><td>(3.77) 1.11</td><td>(-0.45) 0.86</td></tr><tr><td>6</td><td>R 1</td><td>(0.03) 1.16</td><td>(2.78) 0.77</td><td>(5.69) 0.03</td><td>(6.09) -1.14</td><td>(1.25) 1.12</td><td>(3.56) 0.67</td><td>(5.42) 0.09</td><td>(5.71) 1.04</td></tr><tr><td></td><td>R 5</td><td>(2.80) 1.37</td><td>(1.82)</td><td>(0.06)</td><td>(5.22)</td><td>(2.74)</td><td>(1.61)</td><td>(0.20)</td><td>5.19</td></tr><tr><td></td><td></td><td>(5.50)</td><td>1.34 (4.64)</td><td>1.19 (3.39)</td><td>-0.18 (-1.10)</td><td>1.36 (5.37)</td><td>1.34</td><td>1.15</td><td>-0.21 (-1.33)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(4.63)</td><td>(3.28)</td><td></td></tr><tr><td></td><td>R 10</td><td>1.63</td><td>1.82</td><td>1.57</td><td>-0.06</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>1.67</td><td>1.78</td><td>1.55</td><td>-0.12</td></tr><tr><td></td><td></td><td>(5.12)</td><td>(5.55)</td><td>(4.28)</td><td>(0.31)</td><td>(5.30)</td><td>(5.41)</td><td>(4.16)</td><td>(-0.67)</td></tr><tr><td></td><td>R 10-R 1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>0.47 (1.64)</td><td>1.05 (3.79)</td><td>1.55 (5.78)</td><td>1.07 (4.68)</td><td>0.54 (2.07)</td><td>1.11 (4.46)</td><td>1.46</td><td>0.91 (4.61)</td></tr></table></body></html>

Returns are in $\%$ per month and t-statistics are in parentheses.

Momentum profits are stronger among stocks with high trading volume and volume results are stronger among losers. R 10-R 1 is higher in V 3 compared to V 1. V 3-V 1 is lower among R 1 than R 10. Why?
# Early and Late Stage Momentum Strategies

Glamour Stocks (Low B/M, High Volume, LongTerm Positive Earnings Surprises)

 ![500](b10a1609f5e50474820e812aa1609abce96f4dc7a7a9a62fdfc9ec6930d01838.jpg)

(High B/M, Low Volume, Long-Term Negative Earnings Surprises)

Trading volume is low when stocks are out of favor (neglected) and high when stocks are in favor (glamorous). Early stage momentum strategy: Buy low volume winners (R 10 V 1) and Sell high volume losers (R 1 V 3). Late stage momentum strategy: Buy high volume winners (R 10 V 3) and Sell low volume losers (R 1 V 1). Tables V and IX show that low volume stocks behave like value stocks and high volume stocks behave like glamour Stocks.

# TableVll Early and Late Stage Strategies Based on Price Momentum and Trading Volume

This table summarizes annual returns from early (R 10 Vl-RIV 3 or R 5 Vl-R 1 V 5) and late stage (R 10 V 3-RIV 1 or R 5 V 5- $R l V I$ price momentum-trading volume strategies and compares them to the returns from a simple price momentum strategy (R 10-R 1 or R 5-RI) for the time period 1965-1995. Early represents a zero investment portfolio that is long low volume winners (R 10 V 1 or R 5 V 1) and short high volume losers (R 1 V 3 or R 1 V 5). Late represents a zero investment portfolio that is long high volume winners (R 10 V 3 or R 5 V 5) and short low volume losers (R 1 V 1). Rl represents the loser portfolio with the lowest returns and Rl 0 represents the winner portfolio with the highest returns during the previous 6 months. Vl represents the porfolio with the lowe st trading volume and $V 3\left (V 5\right)$ repre sents the portfolio with the highest trading volume when 3 (5) volume portfolios are formed. The volume is computed as the average daily turnover over the previous six months. Yearl, Year 2, Year 3, Year 4 and Year 5 represent the compounded returns in each of the five 12-month periods following the portfolio formation month. The number of monthly observations is 325 except for Panel D, where it is 265. The numbers within parentheses are t-statistics computed with the Hansen-Hodrick autocorrelation correction up to 11 lags.

Panel A: Raw Returns
<html><body><table><tr><td>Strategy</td><td>Year 1</td><td>Year 2</td><td>Year 3</td><td>Year 4</td><td>Year 5</td></tr><tr><td>R 10-R 1 (Simple)</td><td>12.49</td><td>-1.10</td><td>-. 32</td><td>-2.77</td><td>-2.96</td></tr><tr><td rowspan="2">R 10 V 3-R 1 V 1 (Late)</td><td>( 5.04)</td><td>(-. 66)</td><td>( -. 15)</td><td>(-1.68)</td><td>( -2.46)</td></tr><tr><td>6.84</td><td>-5.35</td><td>-3.91</td><td>-6.33</td><td>-4.78</td></tr><tr><td rowspan="2">R 10 V 1-R 1 V 3 (Early)</td><td>(2.53)</td><td>(-2.17)</td><td>( -1.53)</td><td>(-3.54)</td><td>( -2.64)</td></tr><tr><td>16.70</td><td>6.19</td><td>5.85</td><td>1.53</td><td>-. 11</td></tr><tr><td rowspan="2">(R 10 V 3-R 1 V 1)-(R 10-R 1)</td><td>( 5.85)</td><td>( 3.16)</td><td>(2.56)</td><td>(. 64)</td><td>( -. 06)</td></tr><tr><td>-5.65</td><td>-4.25</td><td>-3.59</td><td>-3.56</td><td>-1.81</td></tr><tr><td rowspan="2">(R 10 V 1-R 1 V 3)-(R 10-R 1)</td><td>( -5.21)</td><td>(-3.00)</td><td>(-2.93)</td><td>( -3.14)</td><td>( -1.37)</td></tr><tr><td>4.21</td><td>7.29</td><td>6.17</td><td>4.29</td><td>2.85</td></tr><tr><td></td><td>(2.40)</td><td>(3.40)</td><td>(2.91)</td><td>(2.92)</td><td>(1.73)</td></tr></table></body></html>

Momentum reverses in the long-run (see simple) but more so for late-stage securities.

Early-stage strategies out perform simple strategies which in turn outperform late-stage strategies.

Profitability of momentum strategies can be enhanced by combining momentum with trading volume.

- Volume and momentum are both technical variables.

# Earnings Momentum Strategies

These are strategies based on a firm's quarterly earnings surprises and revisions in security analyst earnings forecasts. Buy stocks with positive earnings momentum and sell stocks with negative earnings momentum.

# Three measures of earnings momentum

1. Quarterly earnings surprises referred to as standardized unexpected earnings (SUE).

2. Price reaction around quarterly earnings announcements referred to as cumulative abnormal returns (CAR). 3. Revisions in consensus analyst forecasts of annual and quarterly earnings of a firm referred to as analyst forecast revisions (FREV).

The hypothesis is that stocks with positive earnings momentum should outperform stocks with negative earnings momentum over a 3 to 6 month period after the portfolio formation date.

We will review evidence presented by Chan, Jegadeesh and Lakonishok (1996) on the profitability of these strategies.

Typically we look for stocks with extreme momentum.
# Chan, Jegadeesh, and Lakonishok (1996)

Standardized unexpected earnings (SUE)

At the beginning of a month, measure SUE for each stock as follows:

$$
S U E_{i, t}=\frac{e_{i, q}-e_{i, q-4}-\mu_{i}}{\sigma_{i}}
$$

Eiq = This quarter's earnings (September 2022)
$\mathbf{e}_{1,\ensuremath{\mathrm{q}}-4}=$ Earnings the same calendar quarter last year (September 2014)
μi Average seasonal change in quarterly earnings measured over the prior 8 quarters
Oi Standard deviation of changes in quarterly earnings over the prior 8 quarters.

Since the unexpected earnings are standardized by the standard deviation, this is referred to as the standardized unexpected earnings (SUE).

Initially studied by Foster, Olsen, and Shevlin (1984) and Bernard and Thomas (1989).

You can also define the earnings surprise relative to consensus earnings forecasts: (Actual - Forecast)/Forecast (if Forecast $>$ 0) or (Actual - Forecast)/Dispersion in Forecasts.

# SUE results

# Table III Mean Returns and Characteristics for Portfolios Classified by Standardized Unexpected Earnings

AtthebeginningofeverymonthfromJanuary 1977 toJanuary 1993, allstocks arerankedbytheir most recent past standardized unexpected earnings and assigned to one of ten portfolios. Standardized unexpected earnings is unexpected earnings (the change in quarterly earnings per share from its value four quarters ago) divided by the standard deviation of unexpected earnings over the last eight quarters. The assignment usesbreakpoints based on New York Stock Exchange (NYSE) issues only. All stocks are equally-weighted in a portfolio. The sample includes all NYSE, American Stock Exchange (AMEX), and Nasdaq domestic primary issues with coverage on the Center for Research in Security Prices (CRSP) and COMPUSTAT. Panel A reports the average past six-month return for each portfolio, and buy-and-hold returns over periods following portfolio formation (in the following six months and in the first, second, and third subsequent years). Panel B reports accounting characteristics for each portfolio: book value of common equity relative to marketvalue,andcashflow (earningsplusdepreciation) relative to marketvalue. Panel Creports each portfolio's most recent past and subsequent values of quarterly standardized unexpected earnings. Panel D reports abnormal returns around earnings announcement dates. Abnormal returns arerelativetotheequally-weightedmarketindexand arecumulatedfrom twodaysbefore to one day after the date of earnings announcement. In Panel E, averages of percentage revisions relativetothebeginning-of-monthstockpriceinmonthlymeanIB/E/Sestimatesofcurrent fiscal-year earnings per share are reported.

<html><body><table><tr><td></td><td>1 (Low)</td><td>2</td><td>3</td><td>4</td><td>5</td><td>9</td><td>7</td><td>8</td><td>9</td><td>10 (High)</td></tr><tr><td colspan="10">PanelA:Returns</td></tr><tr><td>Past 6-monthreturn</td><td>-0.052</td><td>-0.004</td><td>0.027</td><td>0.062</td><td>0.099</td><td>0.127</td><td>0.149</td><td>0.166</td><td>0.186</td><td>0.226</td></tr><tr><td>Return 6 monthsafter portfolioformation</td><td>0.051</td><td>0.063</td><td>0.081</td><td>0.091</td><td>0.105</td><td>0.114</td><td>0.114</td><td>0.115</td><td>0.119</td><td>0.119</td></tr><tr><td>Returnfirstyearafter portfolioformation</td><td>0.138</td><td>0.160</td><td>0.193</td><td>0.205</td><td>0.225</td><td>0.232</td><td>0.227</td><td>0.226</td><td>0.225</td><td>0.213</td></tr><tr><td>Returnsecondyearafter portfolioformation</td><td>0.169</td><td>0.183</td><td>0.194</td><td>0.212</td><td>0.218</td><td>0.215</td><td>0.218</td><td>0.211</td><td>0.204</td><td>0.180</td></tr><tr><td>Returnthirdyearafter portfolioformation</td><td>0.185</td><td>0.189</td><td>0.204</td><td>0.216</td><td>60.208</td><td>0.211</td><td>0.211</td><td>0.208</td><td>0.197</td><td>0.179</td></tr></table></body></html>

At the beginning of each month form 10 portfolios based on the most recent quarter's SUE. 10 is the winner portfolio with the most positive earnings surprises, 1 is the loser portfolio with the most negative earnings surprises. Winners outperform losers by about $7\%$ over the next 6 months (this is referred to as the post-earnings announcement drift).

Earnings momentum disappears after 6 months.

The price reaction around a quarterly earnings announcement (CAR) is measured as follows:

$$
C A R_{i, t}=\sum_{k=-2}^{+1}(r_{i, k}-r_{m, k})
$$

Whereday $^{\circ}0^{\circ}$ is the day of the announcement. We start from day -2 and go till day $+1$ to capture any pre-announcement information leakage.

Ri. K stockreturn on day‘k $\begin{array}{r l}{\mathbf{r}_{\mathrm{m, k}}}&{{}=}\end{array}$ market (S&P 500) return on day ‘k'

· CAR is the return earned by the stock relative to the market around the earnings announcement date.
Positive return suggests market interpreted earnings news as good news and negative return suggests market interpreted earnings news as bad news.
· Also studied by Foster, Olsen, and Shevlin (1984).

# CAR results

# Table IV Mean Returns and Characteristics for Portfolios Classified by Abnormal Return Around Earnings Announcement

AtthebeginningofeverymonthfromJanuary 1977 toJanuary 1993, all stocksareranked bytheir abnormal return around the most recent past announcement of quarterly earnings and assigned to one of ten portfolios. Abnormal returns are relative to the equally-weighted market index and are cumulated from two days before to one day after the date of earnings announcement. The assignment uses breakpoints based on New York Stock Exchange (NYSE) issues only. All stocks are equally-weighted in a portfolio. The sample includes all NYSE, American Stock Exchange (AMEX), and Nasdaq domestic primary issues with coverage on Center for Research in Security Prices (CRSP) and COMPUSTAT. Panel A reports the average past six-month return for each portfolio, and buy-and-hold returns over periods following portfolio formation (in the following six months and in the first, second, and third subsequent years). Panel B reports accounting characteristics for each portfolio: book value of common equity relative to market value, and cash flow (earningsplus depreciation) relative to marketvalue. Panel C reports each portfolio'smostrecent past and subsequent values of quarterly standardized unexpected earnings (the change in quarterly earnings per share from its value four quarters ago, divided by the standard deviation of unexpected earnings over the last eight quarters). Panel D reports abnormal returns around earnings announcement dates. In Panel E, averages of percentage revisions relative to the beginning-of-month stock price in monthly mean IB/E/S estimates of current fiscal-year earnings persharearereported.

<html><body><table><tr><td></td><td>1 (Low)</td><td>2</td><td>3</td><td></td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10 (High)</td></tr><tr><td></td><td colspan="10">Panel A:Returns</td></tr><tr><td>Past 6-monthreturn</td><td>-0.026</td><td>0.039</td><td>0.061</td><td>0.074</td><td>0.085</td><td>0.099</td><td>0.113</td><td>0.132</td><td>0.161</td><td>0.223</td></tr><tr><td>Return 6 monthsafter portfolioformation</td><td>0.063</td><td>0.077</td><td>0.088</td><td>0.093</td><td>0.094</td><td>0.099</td><td>0.099</td><td>0.101</td><td>0.111</td><td>0.122</td></tr><tr><td>Returnfirstyearafter portfolioformation</td><td>0.155</td><td>0.174</td><td>0.183</td><td>0.194</td><td>0.198</td><td>0.208</td><td>0.208</td><td>0.212</td><td>0.221</td><td>0.238</td></tr><tr><td>Returnsecondyearafter portfolioformation</td><td>0.186</td><td>0.190</td><td>0.185</td><td>0.192</td><td>0.197</td><td>0.198</td><td>0.199</td><td>0.196</td><td>0.205</td><td>0.207</td></tr><tr><td>Returnthirdyearafter portfolioformation</td><td>0.183</td><td>0.188</td><td>0.185</td><td>0.190</td><td></td><td>0.1960.200</td><td>0.198</td><td>0.198</td><td>0.198</td><td>0.214</td></tr></table></body></html>

At the beginning of each month form 10 portfolios based on the most recent quarter's CAR. 10 is the winner portfolio with the most positive earnings surprise, 1 is the loser portfolio with the most negative earnings surprise.

· Winners outperform losers by about $6\%$ in the first 6 months.

Security analysts provide forecasts of next year's earnings per share (EPS). Consensus forecasts are the average of individual earnings forecasts. Changes in the consensus are a measure of the momentum in the earnings expectations of a firm.

Revisions in consensus forecasts over the prior J months:

$$
F R E V_{i, t}=\sum_{j=1}^{J}\frac{f_{i, t-j}-f_{i, t-j-1}}{P_{i, t-j-1}}
$$

The forecast $(\mathrm{f_{i, t-j}})$ in month j’ minus the forecast in month $\mathrm{\Theta}^{\circ}\mathrm{j}-1\mathrm{\Omega}^{\circ}$ $(\mathrm{f_{i, t-j-1}})$ scaled by the stock price at the end of month $\mathsf{\Sigma}^{\leftarrow}\mathrm{j}{-1}^{\cdot}\left (\mathrm{P}_{\mathrm{i, t-j-1}}\right)$ Take the sum of this scaled change over the prior $\mathrm{J}=3$ 0 r 6 months.

We can compute revisions for fiscal year 1 forecast (FY 1), fiscal year 2 forecast (FY 2), and also for quarterly forecasts.

# FREV results

# Table V Mean Returns and Characteristics for Portfolios Classified by Revision in Analyst Forecasts

At the beginning of every month from January 1977 to January 1993, all stocks are ranked by their movingaverageofthelastsixmonths'revisionsinmeanIB/E/Sestimatesofcurrentfiscal-year earnings per share, relative to beginning-of-month stock price, and assigned to one of ten portfolios. The assignment uses breakpoints based on NewYork Stock Exchange (NYSE) issues only. All stocksareequally-weightedinaportfolio.ThesampleincludesallNYSE,AmericanStockExchange (AMEX), and Nasdaq domesticprimaryissueswith coverage onthe CenterforResearch in Security Prices (CRSP) and COMPUSTAT. Panel A reports the average past six-month return for each portfolio, and buy-and-hold returns over periods following portfolio formation (in the following six months and in the first, second, and third subsequent years). Panel B reports accounting characteristics for each portfolio: book value of common equity relative to market value, and cash flow (earnings plus depreciation) relative to market value. Panel C reports each portfolio's most recentpast and subsequentvalues of quarterly standardizedunexpectedearnings (the changein quarterly earnings per share from its value four quarters ago, divided by the standard deviation ofunexpectedearnings overthelasteightquarters). PanelDreports abnormalreturns around earnings announcement dates. Abnormal returns are relative to the equally-weighted market index and are cumulated from two daysbefore the one day after the date of earnings announcement. In Panel E, averages of percentage revisions relative to the beginning-of-month stock price in monthly mean I/B/E/S estimates of current fiscal-year earnings per share are reported.

<html><body><table><tr><td></td><td>1 (Low)</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10 (High)</td></tr><tr><td colspan="10">Panel A:Returns</td></tr><tr><td>Past 6-monthreturn</td><td>-0.066</td><td>0.002</td><td>0.032</td><td>0.058</td><td>0.083</td><td>0.099</td><td>0.116</td><td>0.156</td><td>0.191</td><td>0.248</td></tr><tr><td>Return 6 monthsafter portfolioformation</td><td>0.046</td><td>0.070</td><td>0.072</td><td>0.079</td><td>0.083</td><td>0.082</td><td>0.087</td><td>0.106</td><td>0.116</td><td>0.123</td></tr><tr><td>Return firstyearafter portfolioformation</td><td>0.132</td><td>0.159</td><td>0.164</td><td>0.171</td><td>0.177</td><td>0.174</td><td>0.177</td><td>0.203</td><td>0.216</td><td>0.229</td></tr><tr><td>Return secondyear afterportfolio formation</td><td>0.159</td><td>0.180</td><td>0.178</td><td>0.187</td><td></td><td>0.1800.171</td><td>0.178</td><td>0.175</td><td>0.188</td><td>0.214</td></tr><tr><td>Returnthirdyearafter portfolioformation</td><td>0.177</td><td>0.182</td><td>0.174</td><td>0.173</td><td>0.1860.179</td><td></td><td>0.176</td><td>0.189</td><td>0.194</td><td>0.202</td></tr></table></body></html>

At the beginning of each month form 10 portfolios based on FREV. 10 is the winner portfolio with the most positive earnings forecast revisions, 1 is the loser portfolio with the most negative earnings forecast revisions.

Winners outperform losers by about $8\%$ over the next 6 months.

This momentum appears a bit long-lasting.

# How are the various momentum strategies related? Table VII Monthly Cross-Sectional Regressions of Returns on Prior Return and Prior Earnings Surprises

Cross-sectional regressions are estimated each month from January 1977 to January 1993 of individual stock returns on size, compound return over the prior six months (R 6), the abnormal return relative to the equally-weighted market index cumulated from two days before to one day after the most recent past announcement date of quarterly earnings (ABR), unexpected earnings (the change in the most recent past quarterly earnings per share from its value four quarters ago) scaled by the standard deviation of unexpected earnings over the past eight quarters (SUE), and a moving average of the past six months' revisions in I/B/E/S mean analyst earnings forecasts relative to beginning-of-month stock price (REV 6). In the regression each explanatory variable is expressed in terms of its percentile rank and scaled to fall between zero and one. The dependent variable is the stock's buy-and-hold return either over the subsequent six months (Panel A), or over the nextyear (Panel B). The reported statistics are themeans ofthe time series of coefficients from the month-by-month regressions, and in parentheses the $t.$ statisticsrelativetothe autocorrelation-adjusted standard error of the mean. The sample includes all domestic primary firms on New York Stock Exchange (NYSE), American Stock Exchange (AMEX), and Nasdaq with coverage on the Center forResearchin SecurityPrices (CRSP) and COMPUSTAT.

<html><body><table><tr><td>Intercept</td><td>Size</td><td>R 6</td><td>ABR</td><td>SUE</td><td>REV 6</td></tr><tr><td colspan="6">Panel A: Dependent Variable: Six-Month Return</td></tr><tr><td>0.085 (2.50)</td><td>-0.037 (-1.42)</td><td>0.057</td><td></td><td></td><td></td></tr><tr><td>0.093</td><td>-0.033</td><td>(4.07)</td><td>0.037</td><td></td><td></td></tr><tr><td>(2.82)</td><td>(-1.22)</td><td></td><td>(9.25)</td><td></td><td></td></tr><tr><td>0.085</td><td>-0.041</td><td></td><td></td><td>0.060</td><td></td></tr><tr><td>(2.50)</td><td>(-1.52)</td><td></td><td></td><td>(6.00)</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>0.060</td></tr><tr><td>0.086</td><td>-0.042</td><td></td><td></td><td></td><td>(5.45)</td></tr><tr><td>(2.46)</td><td>(-1.62)</td><td></td><td></td><td></td><td></td></tr><tr><td>0.067</td><td>-0.044</td><td></td><td>0.022</td><td>0.037</td><td>0.040</td></tr><tr><td>(1.97)</td><td>(-1.69)</td><td></td><td>(4.40)</td><td>(4.63)</td><td>(4.00)</td></tr><tr><td>0.062</td><td>-0.044</td><td>0.029</td><td>0.017</td><td>0.032</td><td>0.031</td></tr><tr><td>(1.82)</td><td>(-1.69)</td><td>(2.07)</td><td>(4.25)</td><td>(4.00)</td><td>(3.10)</td></tr><tr><td colspan="6">Panel B: Dependent Variable: One-Year Return</td></tr><tr><td>0.190</td><td>-0.084</td><td>0.103</td><td></td><td></td><td></td></tr><tr><td>(2.88)</td><td>(-1.33)</td><td>(3.96)</td><td></td><td></td><td></td></tr><tr><td>0.209</td><td>-0.075</td><td></td><td>0.055</td><td></td><td></td></tr><tr><td>(3.22)</td><td>(-1.14)</td><td></td><td>(7.86)</td><td></td><td></td></tr><tr><td>0.206</td><td>-0.084</td><td></td><td></td><td>0.071</td><td></td></tr><tr><td>(3.12)</td><td>(-1.27)</td><td></td><td></td><td>(4.18)</td><td></td></tr><tr><td>0.205</td><td>-0.085</td><td></td><td></td><td></td><td>0.076</td></tr><tr><td></td><td>(-1.33)</td><td></td><td></td><td></td><td>(3.80)</td></tr><tr><td>(3.01)</td><td></td><td></td><td>0.038</td><td>0.037</td><td>0.054</td></tr><tr><td>0.179</td><td>-0.087</td><td></td><td></td><td>(2.64)</td><td>(3.00)</td></tr><tr><td>(2.63)</td><td>(-1.36)</td><td></td><td>(5.43)</td><td></td><td></td></tr><tr><td>0.166 (2.44)</td><td>-0.089 (-1.41)</td><td>0.076 (3.17)</td><td>0.026 (3.71)</td><td>0.026 (2.00)</td><td>0.031 (1.94)</td></tr></table></body></html>

# Each momentum variable has incremental predictive power.
# Behavioral finance explanations of momentum and value

Efficient market hypothesis

 ![500](756aa5f7e1be83288752e8732e9b637f1590d09557e4aeb52609f38cd383c51f.jpg)

Underreaction (Price adjusts to news with a lag)

 ![500](b8f3d66fa690d702d6c5a3f43588511c85406c786c72d5a1a92c76f5a24e230a.jpg)

Eventual Overreaction (Price eventually overreacts)

 ![500](ab072994fea35206ae63cf2aa2ffe3999f58b6e8b26dc2f4a02af7cf034501b0.jpg)
# Market inefficiency and limited arbitrage

Why doesn't arbitrage eliminate these “inefficiencies/mispricing?

Two possible explanations:

> These are not inefficiencies. These are rational risk premium for some unknown systematic risk!

Arbitrage is neither cost-less nor risk-less.

# Limited Arbitrage (Shleifer and Vishny, 1997)

Arbitrageurs face finite investment horizons, are risk averse, and have limited capital.
Strategies that are highly volatile and where prices may take 2 while to converge to fundamental value are quite risky for arbitrageurs and hard to fully arbitrage away.
With high volatility, the risk the arbitrageurs face is that convergence may not occur during their “short investment horizon and prices may in fact diverge further away from the fundamental value raising the risk of further capital loss. Can you think of examples? This is the noise trader risk.
Most of the inefficiencies tend to be concentrated among small or illiquid stocks where risk and transaction costs are high. Investors may also be slow to learn about these strategies.

# Incorporating this information in security analysis

Once stock valuation is determined, we would like to know the stock's:

· Price momentum
· Most recent quarterly earnings surprises (SUE and CAR)
· Changes in analyst earnings forecasts

Before a decision is made to buy or sell the stock.

Thus, momentum signals can be used effectively to provide timing decisions to avoid being too early to long or short a stock.

The results on price momentum and trading volume provided an early taste of how value and momentum might be combined.

We will now discuss some direct findings on the interaction of value and momentum.

# The Interaction between Value and Momentum

Asness (1997) examines value and momentum interaction.
· Monthly data from July 1963 to December 1994 for all firms in NYSE, AMEX, and Nasdaq.
· Momentum: PAST (2,12) is the average monthly return of a stock starting 12 months ago and ending a month ago (skipping the most recent month to avoid the one-month reversals). 0 For a portfolio formation date of January 1, 2022, the returns are averaged over 11 months: January 2014 to November 2014.
·Value: Log B/M (Stock) - Log B/M (Industry). 0 This measure of value determines how cheap or expensive a company is within its industry.
· Each month sort all stocks independently into 5 Value portfolios and 5 Momentum portfolios. The intersection of the 5 X 5 gives 25 Value-Momentum portfolios.
· The results are in Table 4 of the paper and presented on the next page. The results are average monthly returns in $\%$ Multiply them by 12 to annualize them approximately.
● Tables 1 to 3 show that winners are expensive and losers are Cheap. Value and Momentum are negatively correlated. Does this help or hurt portfolio diversification?

Table 4. Sorting on PAST (2,12) and Log (BV/MV) within Industry
<html><body><table><tr><td>AverageValue-Weighted</td><td>Q 1 (Expensive</td><td></td><td></td><td></td><td>05 (Cheap Log</td><td>05-Q 1</td></tr><tr><td>Statistic</td><td>Log (BV /MV)</td><td>Q 2</td><td>Q 3</td><td></td><td>[BV/MV)</td><td>(t-Statisticy*</td></tr><tr><td>Loser PAST (2,12)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Monthly retum</td><td>0.03%</td><td>0.49%</td><td>0.80%</td><td>0.83%</td><td>1.00%</td><td>0.97%</td></tr><tr><td>Log (BV /MV)</td><td>-1.24</td><td>-0.72</td><td>-0.36</td><td>-0.12</td><td>0.29</td><td>(4.38)</td></tr><tr><td>D/P</td><td>2.31%</td><td>3.28%</td><td>4.07%</td><td>4.34%</td><td>6.04%</td><td></td></tr><tr><td>PAST (2,12)</td><td>0.92</td><td>-1.63</td><td>-1.72</td><td>-1.90</td><td>277-</td><td></td></tr><tr><td>02</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Monthlyretum</td><td>0.61%</td><td>0.59%</td><td>0.90%</td><td>1.25%</td><td>1.35%</td><td>0.74%</td></tr><tr><td>Log (BV/MV)</td><td>-1.23</td><td>-0.72</td><td>-0.37</td><td>-0.13</td><td>0.20</td><td>(3.57)</td></tr><tr><td>D/P</td><td>2.62%</td><td>3.66%</td><td>4.45%</td><td>4.55%</td><td>6.70%</td><td></td></tr><tr><td>PAST (2/12)</td><td>0.03</td><td>0.03</td><td>-0.01</td><td>-0.02</td><td>10'0-</td><td></td></tr><tr><td>Q 3</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Monthlyretum</td><td>0.52%</td><td>0.93%</td><td>0.80%</td><td>1.19%</td><td>1.44%</td><td>0.92%</td></tr><tr><td>Log (BV /MV)</td><td>-1.31</td><td>-0.78</td><td>-0.41</td><td>-0.18</td><td>0.19</td><td>(4.94)</td></tr><tr><td>D/P</td><td>2.40%</td><td>3.55%</td><td>4.29%</td><td>4.24%</td><td>6.98%</td><td></td></tr><tr><td>PASI (2/12)</td><td>1.12</td><td>1.13</td><td>1.11</td><td>1.10</td><td>1.10</td><td></td></tr><tr><td>04</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Monthly retum</td><td>0.99%</td><td>0.97%</td><td>1.17%</td><td>1.45%</td><td>1.68%</td><td>0.69%</td></tr><tr><td>Log (BV /MV)</td><td>-1.42</td><td>-0.85</td><td>-0.49</td><td>-0.24</td><td>0.10</td><td>(3.39)</td></tr><tr><td>D/P</td><td>2.02%</td><td>3.13%</td><td>3.80%</td><td>3.80%</td><td>6.35%</td><td></td></tr><tr><td>PASI (2/12)</td><td>2.32</td><td>2.28</td><td>2.26</td><td>2.27</td><td>2.28.</td><td></td></tr><tr><td>Wimer PAST (2,12)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Monthlyretum</td><td>1.50%</td><td>1.44%</td><td>1.49%</td><td>1.60%</td><td>1.62%</td><td>0.13%</td></tr><tr><td>Log (BV /MV)</td><td>-1.64</td><td>-0.88</td><td>-0.60</td><td>-0.35</td><td>0.13</td><td>(0.65)</td></tr><tr><td>D/P</td><td>1.32%</td><td>2.32%</td><td>2.69%</td><td>2.80%</td><td>6.34%</td><td></td></tr><tr><td>PAST (2/12)</td><td>5.01</td><td>4.34</td><td>4.31</td><td>4.35</td><td>4.47</td><td></td></tr><tr><td>Retum difference</td><td>1.47</td><td>0.95</td><td>0.69</td><td>0.76</td><td>0.62</td><td></td></tr><tr><td>(t-Statisticb</td><td>(5.71)</td><td>(3.47)</td><td>(2.66)</td><td>(3.10)</td><td>(2.57)</td><td></td></tr></table></body></html>

AZero-investment portfolio that is long the Q 5 column entry for each row and short the Q 1 column entry for that row; that is, it tests a long/short portfolio strategy based on the column variable that attempts to hold the row variable constant. We report the average retum on this long/ short portfolio strategy and the f-statistic for the test of whether this average returm is zero. BTest similar to that described in Footnote a but for long /short portfolios fomed on the row variable that attempt to hold the column variable constant.

How does momentum perform among value (cheap) and growth (expensive) stocks? How does value perform among winners and losers? Explain?

How does this compare to the findings on Volume and Momentum?

Relate to the Momentum Life Cycle.

Conclusion: Buy Value- Winners and Sell Growth/Glamour Losers.
# Value and Momentum Everywhere

The intuition behind the Momentum Life Cycle (MLC) is not unique to stocks. It applies equally well to asset classes other than stocks such as country stock indices, bonds, currencies, real estate, and commodities.

Asness, Moskowitz, and Pedersen (2013) examine the profitability of value and momentum strategies among:

Individual stocks in the United States, United Kingdom,
Developed Continental Europe, and Japan,
Country equity index futures
Government bonds
Currencies
Commodity futures
A) They find that value and momentum strategies work in each of these markets and are also negatively correlated with each Other.
B) Value strategies are positively correlated across different markets and momentum strategies are also positively correlated across different markets.
C) They construct a global three-factor model consisting of a global market factor, a global value factor and a global momentum factor covering all asset classes.
D) There is very little correlation between these factors and macroeconomic variables.

# Data

The firms chosen for the study constitute roughly the largest $17\%$ $13\%$ $20\%$ , and $26\%$ of the firms in the U.S., U.K., Europe, and Japan. They are chosen to represent $90\%$ of the market capitalization of these countries. Data from January 1972 to July 2011. 18 developed country equity index futures: Australia, Austria, Belgium, Canada, Denmark, France, Germany, Hong Kong, Italy, Japan, Netherlands, Norway, Portugal, Spain, Sweden, Switzerland, the United Kingdom, and the United States. Data from January 1978 to July 2011. Currencies of Australia, Canada, Germany, Japan, New Zealand, Norway, Sweden, the United Kingdom, and the United States. Returns are computed from forward contracts and are all dollardenominated. Data from January 1979 to July 2011. Global government bonds of Australia, Canada, Denmark, Japan, Norway, Sweden, Switzerland, the U.K., and the U.S. Data from January 1982 to July 2011. Commodity futures: Aluminum, Copper, Nickel, Zinc, lead, Tin, Brent Crude and Gas Oil, Live Cattle, Feeder Cattle, Lean Hogs, Corn, Soybeans, Soy Meal, Soy Oil, and Wheat, WTI Crude, RBOB Gasoline, Heating Oil, Natural Gas, Gold, Silver, Coffee, Cocoa, Sugar and Platinum. The data is from January 1972 to July 2011. Returns are computed from the futures prices.

# Value and momentum measures in different markets

Individual Stocks and Country Stock Indices: B/M Ratios (MSCI reports B/M ratios for countries)

For the next three markets, value is defined based on the past performance measure of DeBondt and Thaler (1985).

Commodities : Log (Pt-5/Pt), where $\mathrm{P_{t}}$ is the spot price of the commodity, this is simply the negative of the past five-year returns.

Currencies: Log $\mathrm{(SE_{t-5}/S E_{t})}$ $\mathrm{Log (1+h_{f})/L o g (1+h_{d})}$ , where $\mathrm{SE_{t}}$ is the spot exchange measured as the price of foreign currency in dollars, $\mathrm{h}_{\mathrm{f}}$ and $\mathrm{h_{d}}$ are the 5-year foreign and U.S. inflation rates. This measures the 5-year decline in the purchasing power parity.

Bonds: 5-Year change in YTM of bonds; since yields move inversely with prices an increase in yield implies drop in prices and vice-versa.

High values indicate value and low values indicate glamour.

Price momentum is simply the 11 month return MOM (2,12) starting 12 months ago and ending a month ago.

Value and momentum factors are dollar-neutral long-short portfolios that take a position on every security based on its rank.

Alphas are the intercepts from a 1-factor market model.
Panel A: Individual Stock Portfolios
<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="5">ValuePortfolios</td><td colspan="5">Momentum Portfolios</td><td colspan="2">50/50 Combination</td></tr><tr><td>P 1</td><td>P 2</td><td>P 3</td><td>P 3-P 1</td><td>Factor</td><td>P 1</td><td>P 2</td><td>P 3</td><td>P 3-P 1</td><td>Factor</td><td>P 3-P 1</td><td>Factor</td></tr><tr><td rowspan="7">U.S.stocks 01/1972 to 07/2011</td><td>Mean</td><td>9.5%</td><td>10.6%</td><td>13.2%</td><td>3.7%</td><td>3.9%</td><td>8.8%</td><td>9.7%</td><td>14.2%</td><td>5.4%</td><td>7.7%</td><td>4.6%</td><td>5.8%</td></tr><tr><td>(t-stat)</td><td>(3.31)</td><td>(4.33)</td><td>(5.19)</td><td>(1.83)</td><td>(1.66)</td><td>(2.96)</td><td>(4.14)</td><td>(4.82)</td><td>(2.08)</td><td>(2.84)</td><td>(3.98)</td><td>(5.40)</td></tr><tr><td>Stdev</td><td>17.9%</td><td>15.4%</td><td>15.9%</td><td>12.8%</td><td>14.8%</td><td>18.6%</td><td>14.8%</td><td>18.5%</td><td>16.4%</td><td>17.0%</td><td>7.2%</td><td>6.8%</td></tr><tr><td></td><td>0.53</td><td>0.69</td><td>0.83</td><td>0.29</td><td>0.26</td><td>0.47</td><td>0.66</td><td>0.77</td><td>0.33</td><td>0.45</td><td>0.63</td><td>0.86</td></tr><tr><td>Sharpe</td><td> 1.7%</td><td>0.8%</td><td>3.6%</td><td>5.3%</td><td>5.8%</td><td>-2.3%</td><td></td><td>0.2%</td><td>3.7% 6.0%</td><td>8.7%</td><td>5.7%</td><td>7.2%</td></tr><tr><td>Alpha</td><td>(-1.59)</td><td>(1.02)</td><td>(3.17)</td><td>(2.66)</td><td>(2.49)</td><td>(-1.68)</td><td></td><td>(0.29)</td><td></td><td>(3.22)</td><td>(5.05)</td><td>(7.06)</td></tr><tr><td>(t-stat)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(2.34)</td><td>(2.30)</td><td>Correlation (Val, Mom)=</td><td>-0.53</td><td>-0.65</td></tr><tr><td>U.K. stocks 01/1972 to</td><td>Mean</td><td>10.8% 12.5%</td><td>15.3%</td><td>4.5%</td><td>5.5%</td><td></td><td>9.2% 13.8%</td><td>15.2%</td><td></td><td>%0'9</td><td>7.2%</td><td>6.3%</td></tr><tr><td rowspan="7">07/2011</td><td>(t-stat)</td><td>(3.17)</td><td>(3.48)</td><td>(4.12)</td><td>(1.83)</td><td>(2.10)</td><td>(2.32)</td><td>(3.81)</td><td>(4.04)</td><td>(2.37)</td><td>(3.00)</td><td>(4.23)</td><td>7.2% (5.85)</td></tr><tr><td>Stdev</td><td>18.6%</td><td>19.7%</td><td>20.3%</td><td>13.4%</td><td>14.4%</td><td>24.9%</td><td></td><td>22.7%</td><td>23.7%</td><td>15.9%</td><td>15.0% 0.48</td><td>8.1% 6.7%</td></tr><tr><td>Sharpe</td><td>0.58</td><td>0.64</td><td>0.75</td><td>0.33</td><td>0.38</td><td></td><td>0.37</td><td>0.61</td><td></td><td>0.38</td><td>0.77</td><td>1.07</td></tr><tr><td>Alpha</td><td>-0.2%</td><td>0.5% (0.42)</td><td>3.2%</td><td>3.5%</td><td>4.4%</td><td>-3.2% (-2.13)</td><td></td><td>2.1%</td><td>3.5%</td><td>6.7% 8.0%</td><td>%0'9 (4.05)</td><td>7.2%</td></tr><tr><td>(t-stat)</td><td>(-0.17)</td><td></td><td>(2.03)</td><td>(1.47)</td><td>(1.74)</td><td></td><td></td><td>(2.06)</td><td>(2.31)</td><td>(2.66)</td><td>(3.36)</td><td>(5.84)</td></tr><tr><td></td><td>11.8%</td><td>14.6%</td><td>16.7%</td><td>4.8%</td><td>5.2%</td><td>9.2%</td><td>13.3%</td><td>17.3%</td><td>Correlation (Val, N</td><td>Mom)=</td><td>-0.43 5.9%</td><td>-0.62</td></tr><tr><td>Europe stocks Mean 01/1974 to (t-stat)</td><td>(3.53)</td><td>(4.43)</td><td>(4.61)</td><td>(2.32)</td><td>(2.95)</td><td>(2.72)</td><td>(4.65)</td><td>(5.56)</td><td>(3.37)</td><td>8.1% (4.59)</td><td>9.8% (4.77)</td><td>6.9% (6.55) 5.8%</td></tr><tr><td>07/2011</td><td>Stdev</td><td>18.3%</td><td>18.0%</td><td>19.8%</td><td>11.5%</td><td>9.7%</td><td>20.6% 0.44</td><td>17.5% 0.76</td><td>19.0% 0.91</td><td>14.7% 0.55</td><td>13.1% 0.75</td><td>6.8%</td></tr><tr><td></td><td>Sharpe Alpha</td><td>0.64 -0.4%</td><td>0.81 2.2%</td><td>0.84 3.1%</td><td>0.42 3.5%</td><td>0.54 4.0%</td><td>-3.5%</td><td>2.2%</td><td>%0'9</td><td></td><td>10.7%</td><td>0.87 6.1%</td></tr><tr><td></td><td></td><td>(-0.30)</td><td>(2.06)</td><td>(2.57)</td><td>(1.71)</td><td>(2.32)</td><td>（-2.54)</td><td>(2.39)</td><td>(4.18)</td><td>9.1% (3.88)</td><td>(5.05)</td><td>(4.88)</td></tr><tr><td>(t-stat)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(6.77)</td></tr><tr><td></td><td></td><td></td><td>8.2%</td><td>14.7%</td><td></td><td>10.2%</td><td>8.4%</td><td></td><td></td><td></td><td>Correlation (Val, Mom)=</td><td>-0.52 -0.55 5.9%</td></tr><tr><td>Japan stocks 01/1974 to 07/2011</td><td>Mean (t-stat)</td><td>2.6% (0.61)</td><td>(2.02)</td><td>(3.69)</td><td>12.0% (4.31)</td><td>(4.22)</td><td>(2.19)</td><td>%66 (2.94)</td><td>10.1% (2.69)</td><td>1.7% (0.57)</td><td>2.2% (0.81)</td><td>6.4% (4.28)</td></tr><tr><td></td><td>Stdev</td><td>23.6%</td><td>22.1%</td><td>21.8%</td><td>15.3%</td><td>13.2%</td><td>23.5%</td><td>20.6%</td><td>23.1%</td><td>18.6%</td><td>16.5%</td><td>8.1%</td></tr><tr><td></td><td>Sharpe</td><td>0.11</td><td>0.37</td><td>0.67</td><td>0.79</td><td>0.77</td><td>0.36</td><td>0.48</td><td>0.44</td><td>0.09</td><td>0.13</td><td>0.78</td></tr><tr><td></td><td>Alpha</td><td>-5.6%</td><td>0.1%</td><td>7.3%</td><td>13.0%</td><td>10.7%</td><td>1.1%</td><td>0.8%</td><td>0.5%</td><td>1.7%</td><td>2.2%</td><td>6.8%</td></tr><tr><td></td><td>(t-stat)</td><td>(-3.36)</td><td>(0.12)</td><td>(3.95)</td><td>(4.71)</td><td>(4.47)</td><td>(-0.59)</td><td>(0.73)</td><td>(0.31)</td><td>(0.54)</td><td>(0.84)</td><td>(4.63)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>Correlation (Val,</td><td>Mom)=</td><td>- 0.60 -0.64</td></tr><tr><td>Countryindices</td><td></td><td>3.1%</td><td>%9'9</td><td>9.1%</td><td>%0'9</td><td>5.7%</td><td>2.3%</td><td>5.8%</td><td>11.0%</td><td>8.7%</td><td>7.4%</td><td>7.3%</td></tr><tr><td>01/1978 to</td><td>Mean (t-stat)</td><td>(1.10)</td><td>(2.40)</td><td>(3.20)</td><td>(3.45)</td><td>(3.40)</td><td>(0.81)</td><td>(2.13)</td><td>(3.72)</td><td>(4.14)</td><td>(3.57)</td><td>10.6% (6.62)</td></tr><tr><td>07/2011</td><td>Stdev</td><td>16.2%</td><td>15.7%</td><td>16.2%</td><td>9.8%</td><td>9.5%</td><td>16.2%</td><td>15.4%</td><td>16.8%</td><td>11.9%</td><td>11.8%</td><td>(5.72) 6.3% 10.6%</td></tr><tr><td></td><td>Sharpe</td><td>0.19</td><td>0.42 0.5%</td><td>0.56 2.7%</td><td>0.61 5.9%</td><td>0.60 5.3%</td><td>0.14 -3.9%</td><td>0.37 -0.3%</td><td>0.65</td><td>0.73 8.2%</td><td>0.63 7.1%</td><td>1.16 1.00 7.1% 10.0%</td></tr><tr><td></td><td>Alpha</td><td>3.2%</td></table></body></html>
# Alternate Fixed Income Measures

Since fixed income results are the weakest, the authors use alternate measures of value for fixed income. From Panel C of Table I:

<html><body><table><tr><td colspan="9">Panel C: AlternativeValue Measures for Fixed Income</td></tr><tr><td></td><td></td><td colspan="5">Value Portfolios</td><td colspan="2">50-50 Combination</td></tr><tr><td>Fixed income 01/1983 to 07/2011</td><td></td><td>P 1</td><td>P 2</td><td>P 3</td><td>P 3-P 1</td><td>Factor</td><td>P 3-P 1</td><td>Factor</td></tr><tr><td rowspan="7">Value = 5-year yield change (yield to yield 5 years ago)</td><td>Mean</td><td>3.0%</td><td>4.0%</td><td>4.2%</td><td>1.1%</td><td>0.5%</td><td>0.8%</td><td>0.7%</td></tr><tr><td>(t-stat)</td><td>(2.31)</td><td>(3.58)</td><td>(3.76)</td><td>(0.97)</td><td>(0.39)</td><td>(1.03)</td><td>(1.08)</td></tr><tr><td>Stdev</td><td>7.0%</td><td>5.9%</td><td>5.9%</td><td>6.3%</td><td>6.4%</td><td>4.0%</td><td>3.5%</td></tr><tr><td>Sharpe</td><td>0.43</td><td>0.67</td><td>0.71</td><td>0.18</td><td>0.07</td><td>0.19</td><td>0.20</td></tr><tr><td>Alpha</td><td>-1.3%</td><td>0.3%</td><td>0.7%</td><td>1.9%</td><td>1.4%</td><td>0.8%</td><td>0.7%</td></tr><tr><td>(t-stat)</td><td>(1.87)</td><td>(-0.51)</td><td>(1.03)</td><td>(1.68)</td><td>(1.21)</td><td>(1.10)</td><td>(1.15)</td></tr><tr><td></td><td></td><td></td><td colspan="3">Correlation (Val, Mom)=</td><td>0.17</td><td>-0.35</td></tr><tr><td rowspan="7">Value =real bond yield (10-year yield to 5-year inflation forecast)</td><td>Mean</td><td>%6'0</td><td>2.1%</td><td>2.9%</td><td>2.0%</td><td>1.9%</td><td>%6'0</td><td>1.4%</td></tr><tr><td>(t-stat)</td><td>(1.84)</td><td>(3.36)</td><td>(4.17)</td><td>(3.78)</td><td>(3.58)</td><td>(2.44)</td><td>(2.63)</td></tr><tr><td>Stdev</td><td>2.6%</td><td>3.2%</td><td>3.6%</td><td>2.7%</td><td>2.8%</td><td>1.9%</td><td>2.9%</td></tr><tr><td>Sharpe</td><td>0.36</td><td>0.65</td><td>0.81</td><td>0.73</td><td>0.70</td><td>0.46</td><td>0.49</td></tr><tr><td>Alpha</td><td>-0.6%</td><td>0.1%</td><td>0.4%</td><td>1.0%</td><td>%6'0</td><td>0.4%</td><td>0.6%</td></tr><tr><td>(t-stat)</td><td>(2.02)</td><td>(-0.15)</td><td>(1.09)</td><td>(2.36)</td><td>(2.09)</td><td>(1.17)</td><td>(1.25)</td></tr><tr><td></td><td></td><td></td><td></td><td colspan="2">Correlation (Val, Mom) =</td><td>-0.09</td><td>0.03</td></tr><tr><td rowspan="7">Value = term spread (10-year yield to short rate)</td><td>Mean</td><td>0.8%</td><td>1.5%</td><td>2.3%</td><td>1.5%</td><td>1.7%</td><td>0.6%</td><td>1.1%</td></tr><tr><td>(t-stat)</td><td>(1.25)</td><td>(2.37)</td><td>(3.60)</td><td>(2.69)</td><td>(3.22)</td><td>(1.47)</td><td>(1.96)</td></tr><tr><td>Stdev</td><td>3.2%</td><td>3.2%</td><td>3.2%</td><td>2.8%</td><td>2.5%</td><td>2.2%</td><td>2.9%</td></tr><tr><td>Sharpe</td><td>0.25</td><td>0.250.48</td><td>0.73</td><td>0.55</td><td>0.65</td><td>0.28</td><td>0.37</td></tr><tr><td>Alpha</td><td>1.2%</td><td>0.7%</td><td>0.1%</td><td>1.3%</td><td>1.4%</td><td>0.5%</td><td>0.8%</td></tr><tr><td>(t-stat)</td><td>(-3.03)</td><td>(1.79)</td><td>(0.28)</td><td>(2.78)</td><td>(3.31)</td><td>(1.22)</td><td>(1.55)</td></tr><tr><td></td><td></td><td></td><td></td><td colspan="2">Correlation (Val, Mom)=</td><td>0.22</td><td>0.28</td></tr><tr><td rowspan="7">Value=composite average of all threemeasures</td><td>Mean</td><td>0.3%</td><td>1.6%</td><td>3.0%</td><td>2.6%</td><td>2.9%</td><td>1.3%</td><td>2.2%</td></tr><tr><td>(t-stat)</td><td>(0.58)</td><td>(2.56)</td><td>(4.63)</td><td>(4.88)</td><td>(5.89)</td><td>(3.17)</td><td>(4.30)</td></tr><tr><td>Stdev</td><td>3.2%</td><td>3.4%</td><td>3.4%</td><td>2.9%</td><td>2.6%</td><td>2.1%</td><td>2.7%</td></tr><tr><td>Sharpe</td><td>0.11</td><td>0.48</td><td>0.87</td><td>0.91</td><td>1.10</td><td>0.59</td><td>0.81</td></tr><tr><td>Alpha</td><td>-1.5%</td><td>0.3%</td><td>0.8%</td><td>2.3%</td><td>2.6%</td><td>1.0%</td><td>1.8%</td></tr><tr><td>(t-stat)</td><td>(-4.01)</td><td>(-0.80)</td><td>(2.25)</td><td>(4.40)</td><td>(5.48)</td><td>(2.55)</td><td>(3.66)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>0.03</td><td>0.04</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td colspan="2">Correlation (Val, Mom) =</td><td></td><td></td></tr></table></body></html>

Overall the evidence suggests value and momentum work everywhere, and combining value and momentum is a good investment strategy.
# Recap

· Momentum Life Cycle Model Framework
Value strategies and Past performance (contrarian) strategies Enhancing Value strategies using financial statement information: Value Winners and value Losers
· Momentum strategies Enhancing momentum strategies using trading volume into early-stage (buy low volume winner and sell high volume loser) and late-stage (buy high volume winner and sell low volume loser) strategies
· Interaction between value and momentum; value and momentum are negatively correlated; momentum works better among glamour/growth/expensive stocks and value works better among losers
· Value and momentum work everywhere.
· Risk vs. Mispricing debate and Limited Arbitrage.

# Lecture Note 11 Accruals, Asset Growth and External Financing

# Free Cash Flows to the Firm (FCFF)

From equation (3) of Lecture Note 3:

$$
\begin{array}{r}{F C F F (t)=N O P A T (t)+D e p (t)-\Delta W C (t)-C a p E x (t)}\end{array}
$$

NOPAT (t) $=$ Net operating profits after taxes for year 't'.
Dep (t) $=$ Depreciation & Amortization for year ‘t'.
△WC (t) $=$ Change in operating working capital for year 't'.
CapEx (t) $=$ Capital expenditures and acquisitions.

Gross investment (GI):

$$
G I (t)=C a p E x (t)+\Delta W C (t)
$$

The net new investment:

$$
\begin{array}{r}{I (t)=\underbrace{\big[C a p E x (t)+\Delta W C (t)\big]}_{\mathrm{Gross~Investment}}-\underbrace{D e p (t)}_{\mathrm{Replacement~Inve}}}\end{array}
$$

Estment

$$
F C F F (t)=N O P A T (t)-I (t)
$$

FCFF is the residual cash left over from profits after a firm has reinvested a portion of its profits in the firm.

The accounting literature refers to the net new investment as Total Accruals and $[\Delta\mathrm{WC-Dep}]$ as Working Capital Accruals.
# Working capital accruals (Sloan, 1996)

Cash flow from operations (CFO) (in general):

$$
\begin{array}{r l}&{C F O (t)=N e t I n c o m e (t)+D e p (t)-\Delta W C (t)}\ &{\qquad=N e t I n c o m e (t)-[\Delta W C (t)-D e p (t)]}\ &{\qquad=N e t I n c o m e (t)-W C A (t)}\end{array}
$$

From equation (5):

$$
N e t I n c o m e (t)=C F O (t)+W C A (t)
$$

· CFO represents permanent earnings (less mean-reverting) because CFO is less subject to accounting distortions. WCA represents temporary earnings (more mean-reverting) possibly due to managerial manipulation because it contains receivables, inventory, etc.
· Since WCA is a dollar number, typically it is scaled by average total assets (see Sloan, 1996) or invested capital.
WCA/Average Total Assets or WCA/Average Invested Capital.

# FIGURE 1

Time Series Properties of Earnings, Accruals and Operating Cash Flows. Year O is the year in which firms are ranked and assigned in equal numbers to ten portfolios based on each of the three respective variables. Earnings is measured as income from continuing operations scaled by average total assets for the year. Accruals is the change in non-cash current assets, less the change in current liabilities (exclusive of short-term debt and taxes payable), less depreciation expense, all divided by average total assets. Cash flow is the difference between earnings and accruals (as defined above).

 ![500](6dcdf68e166eb39e0d4b8e8072c3585b990decdc24561a125004ca5c501b1261.jpg)

# Earnings Quality and Stock Returns

· Earmgs accompameu oy extree accruais tenu wo revert faster than earnings accompanied by extreme cash flows. Thus, the cash flow component of earnings seems more persistent than the accrual component of earnings. Extrapolation bias?
· Sloan (1996) shows that investors, contrary to the observed empirical results, treat the accrual component as more persistent than the cash flow component.
· If high earnings are due to high accruals and low cash flows (due to increase in receivables, inventory, decrease in payables, etc.) then the earnings are considered to be of lower earnings quality. See equation (6).
If high earnings are due to low accruals and high cash flows then the earnings are considered to be of higher earnings quality.
· If investors are unable to distinguish between low quality and high quality earnings and focus only on quantity, they would overvalue stocks with high accruals (and lower cash flows) and undervalue stocks with low accruals (and higher cash flows).
· Thus, a strategy of long low accrual stocks and short high accrual stocks should outperform. The results suggest investors have an earnings fixation. They focus on earnings more than they do on cash flows.
· Where are high accrual and low accrual portfolios in the MLC?

TABLE 6 Time-series Means of Equal Weighted Portfolio Abnormal Stock Returns Sample Consists of 40,679 Firm-yearsBetween 1962 and 1991 a
<html><body><table><tr><td rowspan="2">PortfolioAccrual Ranking</td><td colspan="3">Size Adjusted Returnsb</td><td colspan="3">JensenAlphasc</td></tr><tr><td>yeart+1</td><td>yeart+2</td><td>yeart+3</td><td>yeart+1</td><td>year t+2</td><td>year 1+3</td></tr><tr><td>Lowest</td><td>0.049 (2.65)"</td><td>0.016 (1.17)</td><td>0.007 (0.55)</td><td>0.039 (2.01)*</td><td>0.007 (0.40)</td><td>0.001 (0.08)</td></tr><tr><td>2</td><td>0.028 (3.60)</td><td>0.019 (1.65)</td><td>0.006 (0.68)</td><td>0.020 (1.68)</td><td>0.022 (1.53)</td><td>0.012 (1.06)</td></tr><tr><td>3</td><td>0.024 (3.84)**</td><td>0.012 (2.27)*</td><td>-0.006 (-0.86)</td><td>0.018 (1.70)</td><td>0.014 (1.28)</td><td>-0.006 (-0.72)</td></tr><tr><td>4</td><td>0.012 (1.66)</td><td>0.001 (0.05)</td><td>0.020 (2.72)</td><td>0.017 (2.09)*</td><td>0.002 (0.17)</td><td>0.017 (1.29)</td></tr><tr><td>5</td><td>0.001 (0.03)</td><td>0.002 (0.22)</td><td>0.006 (0.86)</td><td>0.010 (0.87)</td><td>0.004 (0.38)</td><td>0.014 (1.12)</td></tr><tr><td>6</td><td>0.010 (1.43)</td><td>0.005 (0.72)</td><td>0.016 (1.90)</td><td>0.006 (0.57)</td><td>0.002 (0.24)</td><td>0.003</td></tr><tr><td>7</td><td>-0.002 (-0.22)</td><td>0.003 (0.60)</td><td>-0.006</td><td>0.004</td><td>0.006</td><td>(0.43) 0.005</td></tr><tr><td>8</td><td>-0.021 (-3.03)"</td><td>-0.002</td><td>(-0.83) -0.001</td><td>(0.39) 0.011</td><td>(0.97) -0.004</td><td>(0.56) 0.002</td></tr><tr><td>9</td><td>-0.035 (-3.70)*</td><td>(-0.31) -0.018 (-2.52)</td><td>(-0.01) -0.015</td><td>(-1.17) -0.028</td><td>(-0.39) -0.012</td><td>(0.16) -0.012</td></tr><tr><td>Highest</td><td>-0.055 (-3.98)*</td><td>-0.032</td><td>(-1.60) -0.022</td><td>(-3.04)* -0.064</td><td>(-1.36) -0.040</td><td>(-1.15) -0.036</td></tr><tr><td>Hedged</td><td>0.104 (4.71)**</td><td>(-2.25)* 0.048 (3.15)</td><td>(-1.61) 0.029 (1.64)</td><td>(-4.68)" 0.104 (4.42)"*</td><td>(-2.87)** 0.048 (2.41)</td><td>(-2.47)* 0.038 (1.62)</td></tr></table></body></html>

# FIGURE 2

Returns by calendar year to a hedge portfolio taking a long position in the stock of firms in the lowest decile of accruals and an equal-sized short position in the stock of firms in the highest decile of accruals. Returns are cumulated over a one-year period beginning four months after the fiscal year end. Accruals is the change in non-cash current assets, less the change in current liabilities (exclusive of short-term debt and taxes payable), less depreciation expense, all divided by average total assets.

 ![500](ef97d3d08f60993d32cfcb1b1f13a372f21701186a4c1e9d30a4ee9cb0cb4b56.jpg)

# Which component of accruals is more mispriced?

Working capital accruals consist of several components:

Change in current operating assets:
Change in receivables $+$ Change in Inventory $+$ Change in other
Current operating assets
Change in current operating liabilities:
Change in accounts payable $+$ Change in other current operating
Liabilities
They confirm Sloan's findings and also examine the mispricing of various components of accruals.

TABLE 3 Characteristics and Returns for Portfolios Sorted by Accruals
<html><body><table><tr><td></td><td>1</td><td></td><td></td><td></td><td>5</td><td>6</td><td></td><td></td><td></td><td>10</td><td>1-10</td><td></td></tr><tr><td>(Low)</td><td>2</td><td colspan="9">4</td><td>(High)</td><td>t-Statistic</td></tr><tr><td></td><td colspan="10">C. Raw Retums</td><td></td><td></td><td></td></tr><tr><td>3 years before</td><td>.113</td><td>.140</td><td>.151</td><td>.159</td><td>.169</td><td>.185</td><td>.191</td><td>.224</td><td>.281</td><td></td><td>.376</td><td>-. 263</td><td>-8.34</td></tr><tr><td>2 years before</td><td>.130</td><td>.141</td><td>.151</td><td>.147</td><td>.163</td><td>.164</td><td>.199 .199</td><td>.232</td><td></td><td>.273</td><td>.419</td><td>-. 289</td><td>-6.59</td></tr><tr><td>1 year before</td><td>.304</td><td>.251</td><td>.229</td><td>.210</td><td>201</td><td>.198</td><td></td><td></td><td>.207</td><td>.220</td><td>.281</td><td>.024</td><td>.97</td></tr><tr><td>1 year after</td><td>.178</td><td>.178</td><td>.174</td><td>.170</td><td>.163</td><td>.157</td><td></td><td>.157</td><td>.150</td><td>.140</td><td>.090</td><td>.088</td><td>3.79</td></tr><tr><td>2 years after</td><td>.157 .189</td><td>.165</td><td>.177</td><td>.179</td><td>.170</td><td>.155</td><td>.156</td><td></td><td>.157</td><td>.137</td><td>.097</td><td>.060</td><td>3.76</td></tr><tr><td>3 years after</td><td>.184</td><td></td><td>.178</td><td>.184</td><td>.174</td><td>.182</td><td>.183</td><td></td><td>.168</td><td>.175</td><td>.132</td><td>.057</td><td>3.08</td></tr><tr><td colspan="10"></td><td></td><td></td><td></td><td></td></tr><tr><td>3 years before</td><td>-. 028</td><td>-. 004</td><td>.010</td><td>.014</td><td>.024</td><td>.041 .026</td><td>.049</td><td></td><td>.084</td><td>.142</td><td>.243</td><td>-. 271</td><td>-9.20</td></tr><tr><td>2 years before</td><td>-. 002</td><td>.003</td><td>.013</td><td>.008</td><td>.024</td><td></td><td>.057</td><td></td><td>.093</td><td>.139</td><td>.294</td><td>-. 296</td><td>-7.21</td></tr><tr><td>1 year before</td><td>.150</td><td>.094</td><td>.072</td><td>.055</td><td>.042</td><td>.044</td><td>.048</td><td></td><td>.057</td><td>.072</td><td>.143</td><td>.007</td><td>.35</td></tr><tr><td>1 year after</td><td>.026</td><td>.024</td><td>.023</td><td>.017</td><td>.009</td><td>.007</td><td>.003</td><td></td><td>-. 001</td><td>-. 001</td><td>-. 047</td><td>.074</td><td>3.83</td></tr><tr><td>2 years after</td><td>.004</td><td>.009</td><td>.018</td><td>.019</td><td>.010</td><td>.001</td><td>.006</td><td></td><td>.006</td><td>-. 009</td><td>-. 041</td><td>.044</td><td>2.97</td></tr><tr><td>3 years after</td><td>.018</td><td>.012</td><td>.005</td><td>.010</td><td>.002</td><td>.009</td><td>.015</td><td></td><td>.000</td><td>.012</td><td>-. 025</td><td>.043</td><td>2.48</td></tr></table></body></html>

NoTE. The sample compnise alldomestic common stocks (except fnancial fms) on NYSE, AMEX ,and NASDAQ with coverage on CRSP and Computat and with available data. At the end ofApl each yearfm 19 t 1995, all tock aranedby accual relative to averagettal asst d asined tooneof 0 equalyweighted porfols asming arepn delay of fohfm te end of thfsayear) eagealfacal, eng, and chactenst forech pfo are ened ipnels A adBllt abveitae divdedbyveae tofmastsAvageaabuyadholdres ae presenedpalCforeahyamtreeyearsror pfolofotonthreeaaefoon along with e dffrnce etween thebottm and top deciles and the t-statstic forthe men diference. Pnel Deot average aual res mexces of ter oncnol ptfolos mathedbyszdbooktkLg eistnatl logafkt valefequty lliondllas) booktark sthatfbook tmkevaofequty ae aual gowh  sale over the pior thee year is the average of the vale-weighted aual gowth te m sale of each potfolioover the the years pior to potfolo fomation Other Variables are defined in the note to table .

1 is low accrual portfolio, 10 is high accrual portfolios

The accrual effect is concentrated among high accrual portfolios.
Thus, it is more of a short or sell signal.

High accrual portfolios have high past performance but exhibit poor future performance up to three years after portfolio formation.

Portfolios are formed in April of each year (1971-1995) and abnormal returns are computed relative to size-B/M portfolios.
 ![500](1391fd56cb9fb5f91fb3933cd31db216f0448bdba120cc47af96f364da9646d6.jpg)
Fic. 1. —-Operating performance of portfolios sorted by accruals

Firms with high accruals experience extreme growth in earnings, cash flows, accounts receivables, inventories and accounts payable from Year -1 to 0. It is possible accruals grow with sales or in anticipation of future sales; however sales (asset) turnover (sales/avg. Total assets) remain flat in the pre-formation years (-5 to 0) and decline in the post-formation years $(0\mathrm{to}+5)$ for the high accrual firms.
The sudden decline in earnings and sales in Year $+1$ raises the possibility of prior years? Managerial earnings manipulation perhaps to avoid a disappointing earnings report.

TABLE 4 Returns for Portfolios Sorted by Accrual Components
<html><body><table><tr><td>1 (Low)</td><td></td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td></td><td>10 (High)</td><td>1-10</td><td>t-Statistic</td></tr><tr><td colspan="10"></td></tr><tr><td colspan="10"></td></tr><tr><td>R 1</td><td>.165</td><td>.161</td><td>.161</td><td>.165</td><td></td><td></td><td></td><td>.151</td><td>.142</td><td>.112</td><td>.054</td><td>2.66</td></tr><tr><td>R 2</td><td>.168</td><td>.164</td><td>.172</td><td>.157</td><td>.170 .153</td><td>.175 .172</td><td>.156 .160</td><td>.151</td><td>.144</td><td>.112</td><td>.056</td><td>2.94</td></tr><tr><td>R 3</td><td>.183</td><td>.186</td><td>.192</td><td>.177</td><td>.173</td><td>.175</td><td>.181</td><td>.177</td><td>.165</td><td>.140</td><td>.043</td><td>2.78</td></tr><tr><td>AR 1</td><td>.006</td><td>.005</td><td>.007</td><td>.012</td><td>.021</td><td>.023</td><td>.007</td><td>.005</td><td>.001</td><td>.025</td><td>.031</td><td>2.23</td></tr><tr><td>AR 2</td><td>.004</td><td>.001</td><td>.009</td><td>.003</td><td>.000</td><td>.018</td><td>.010</td><td>.002</td><td>.001</td><td>-. 024</td><td>.028</td><td>2.10</td></tr><tr><td>AR 3</td><td>.003</td><td>.007</td><td>.019</td><td>.007</td><td>.004</td><td>.007</td><td>.012</td><td>.010</td><td>.002</td><td>-. 015</td><td>.018</td><td>1.17</td></tr><tr><td colspan="10">B.Ranked by Change in Inventory</td></tr><tr><td>R 1</td><td>.190</td><td>.174</td><td>.176</td><td>.163</td><td>.158</td><td>.154</td><td>.161</td><td>.155</td><td>.133</td><td>.095</td><td>.095</td><td>4.63</td></tr><tr><td>R 2</td><td>.165</td><td>.172</td><td>.168</td><td>.158</td><td>.160</td><td>.167</td><td>.163</td><td>.150</td><td>.139</td><td>.110</td><td>.055</td><td>3.45</td></tr><tr><td>R 3</td><td>.182</td><td>.185</td><td>.177</td><td>.189</td><td>.164</td><td>.178</td><td>.181</td><td>.180</td><td>.167</td><td>.144</td><td>.038</td><td>2.06</td></tr><tr><td>AR 1</td><td>.029</td><td>.014</td><td>.023</td><td>.014</td><td>.012</td><td>.005</td><td>.011</td><td>.006</td><td>.011</td><td>.043</td><td>.072</td><td>4.34</td></tr><tr><td>AR 2</td><td>.001 -. 001</td><td>.012</td><td>.013</td><td>.009</td><td>.006</td><td>.012</td><td>.011</td><td>.002</td><td>-. 008</td><td>-. 032</td><td>.033</td><td>2.34</td></tr><tr><td>AR 3</td><td></td><td>.007</td><td>.010</td><td>.021</td><td>-. 001</td><td>.010</td><td>.013</td><td>.012</td><td>.001</td><td>-. 017</td><td>.016</td><td>.84</td></tr><tr><td colspan="10">C.Ranked by Change in Other Current Assets</td></tr><tr><td></td><td>.187</td><td>.172</td><td>.155</td><td>.149</td><td>.158</td><td>.154</td><td>.154</td><td>.151</td><td>.145</td><td>.133</td><td>.054</td><td>4.61</td></tr><tr><td>R 1 R 2</td><td>.161</td><td>.163</td><td>.175</td><td>.151</td><td>.160</td><td>.153</td><td>.140</td><td>.158</td><td>.142</td><td>.148</td><td>.014</td><td>1.29</td></tr><tr><td>R 3</td><td>.184</td><td>.174</td><td>.182</td><td>.163</td><td>.178</td><td>.165</td><td>.185</td><td>.170</td><td>.172</td><td>.174</td><td>.011</td><td>.75</td></tr><tr><td>AR 1</td><td>.033</td><td>.018</td><td>.004</td><td>-. 001</td><td>.006</td><td>.004</td><td>.002</td><td>.006</td><td>.000</td><td>.012</td><td>.045</td><td>4.29</td></tr><tr><td>AR 2</td><td>.004</td><td>.005</td><td>.019</td><td>-. 004</td><td>.005</td><td>.000</td><td>-. 013</td><td>.010</td><td>-. 005</td><td>.002</td><td>.002</td><td>.14</td></tr><tr><td>AR 3</td><td>.009</td><td>-. 002</td><td>.012</td><td>-. 007</td><td>.009</td><td>-. 005</td><td>.019</td><td>.003</td><td>.009</td><td>.008</td><td>.000</td><td>.01</td></tr><tr><td colspan="10">D. Ranked by Change in Accounts Payable</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>R 1 R 2</td><td>.184 .153</td><td>.167</td><td>.162 .166</td><td>.166 .164</td><td>.160 .164</td><td>.156</td><td>.160 .154</td><td>.149 .156</td><td>.145 .135</td><td>.109 .120</td><td>.074 .033</td><td>5.86 2.55</td></tr><tr><td>R 3</td><td>.179</td><td>.168 .184</td><td>.176</td><td>.173</td><td>.187</td><td>.171 .176</td><td>.167</td><td>.175</td><td>.175</td><td>.154</td><td>.024</td><td>1.60</td></tr><tr><td>AR 1</td><td>.026</td><td>.011</td><td>.009</td><td>.016</td><td>.009</td><td></td><td></td><td>.003</td><td>.001</td><td>.031</td><td>.057</td><td>5.79</td></tr><tr><td>AR 2</td><td>-. 006</td><td>.008</td><td>.008</td><td>.009</td><td>.010</td><td>.007</td><td>.010</td><td></td><td></td><td>-. 021</td><td>.015</td><td>1.21</td></tr><tr><td>AR 3</td><td>.002</td><td>.010</td><td>.006</td><td>.003</td><td>.020</td><td>.019 .007</td><td>.002 .001</td><td>.006 .006</td><td>-. 014 .009</td><td>-. 007</td><td>.009</td><td>.49</td></tr><tr><td colspan="10"></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>E.Ranked by Change in Other Current Liabilities</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>R 1</td><td>.147 .142</td><td>.158</td><td>.141 .160</td><td>.158</td><td>.161</td><td>.167</td><td>.162</td><td>.151</td><td>.164</td><td>.148 .138</td><td>-. 001 .004</td><td>-. 07 .27</td></tr><tr><td>R 2 R 3</td><td></td><td>.156</td><td>.164</td><td>.154</td><td>.166</td><td>.155</td><td>.160</td><td>.163 .184</td><td>.155 .165</td><td>.167</td><td>.010</td><td>.75</td></tr><tr><td></td><td>.177</td><td>.179</td><td></td><td>.167</td><td>.183</td><td>.179</td><td>.183</td><td></td><td></td><td>.011</td><td></td><td>-1.28</td></tr><tr><td>AR 1</td><td>.006</td><td>.002</td><td>.012 .001</td><td>.005</td><td>.008</td><td>.016</td><td>.013</td><td>.003 .013</td><td>.021 .010</td><td>.000</td><td>.017 -. 013</td><td>-1.01</td></tr><tr><td>AR 2 AR 3</td><td>-. 014 .003</td><td>.001 .006</td><td>-. 008</td><td>.003 -. 005</td><td>.009 .007</td><td>.000 .006</td><td>.007 .015</td><td>.018</td><td>.004</td><td>.009</td></table></body></html>

NoTE.- The sample compnses alldomestic common stocks (except fnancial fums) on NYSE, AMEX, and NASDAQ with coverage on CRSP and Compustat, and with avalable data At the end ofApnl eachyear fom 197 l to 1995, all stocks are ranked bya component of accuals relative to average total assets and asigned to ne of 10 orfolios (assuming areoting delay of fou months fom the end of the fscal year) Annual luy-and-hold retus are caleulated over the subsequent year as welas retums in excess of theretun on a connol potfolo matched by size and book-to-market. Average retuns in each of the fut to third years following pottfolio fomation (Rl, R 2, and R 3, respectively) and exces retuns in each of the fust to thid postfmation yeas (ARl, AR 2, and AR 3) on the equally weighted decile portfolios are reported Also reported is the difference between the bottom and top decile porfolios and thet-statisticforthemean difference.

Every component except “change in other current liabilities" appears mispriced. “Change in inventory” produces the biggest spread in returns. An increase in each of the components produces lower returns. An increase in accounts payable which lowers accruals also appears to generate poor returns perhaps because investors are slow to realize slowing business prospects. Explain?
# Are the results driven by extrapolation bias?

Extrapolation bias suggests investors ignore regression to mean and extrapolate past performance too far into the future. Could the accrual results be due to extrapolation bias since firms with high growth in sales tend to also have high growth in working capital (accruals)? The authors decompose accruals into discretionary and nondiscretionary accruals. Non-discretionary accruals are those required to support the current level of sales. Discretionary accruals represent excess beyond what is required.

Of working capital for a firm to its current sales. For example, in the cas inventory, $I_{i t}$ and sales, Sales,. For firm i in year t, we define

$$
E_{t}(I_{t t})=\frac{\sum_{k=1}^{5}I_{t t-k}}{\sum_{k=1}^{5}\mathrm{Sales}_{i t-k}}\mathrm{Sales}_{i t}.
$$

The nondiscretionary change in inventory, $\mathbf{NDI}_{i t}$ is then given by

$$
\mathrm{NDI}_{n}=E_{t}(I_{i t})-I_{i t-1},
$$

And the discretionary change in inventory. $D I_{i t}$ is

$$
D I_{t t}=I_{t t}-E_{t}(I_{i t}).
$$

Expected accruals are computed based on past ratios of inventory to sales. Growth in accruals beyond that needed to support increasing sales is discretionary and due to managerial manipulation.

The \*I' above refers to inventory not net new investments.
TABLE 5 Returns for Portfolios Sorted by Discretionary and Nondiscretionary Accruals
<html><body><table><tr><td></td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>10</td><td></td><td></td><td></td><td></td></tr><tr><td>(Low)</td><td>2</td><td>3</td><td></td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>6</td><td>(High)</td><td>1-10</td><td>t-Statistic</td><td>2-9</td><td>t-Statistic</td></tr><tr><td colspan="10">A. Discretionary Accruals</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>R 1</td><td>.178</td><td>.190</td><td>.178</td><td>.171</td><td>.163</td><td>.150</td><td>.149</td><td>.152</td><td>.128</td><td>.100</td><td>.078</td><td>5.50</td><td>.062</td><td>6.01</td></tr><tr><td>R 2</td><td>.159</td><td>.175</td><td>.171</td><td>.159</td><td>.165</td><td>.159</td><td>.154</td><td>.154</td><td>.144</td><td>.110</td><td>.049</td><td>4.13</td><td>.032</td><td>2.33</td></tr><tr><td>R 3</td><td>.186</td><td>.188</td><td>.182</td><td>.188</td><td>.187</td><td>.174</td><td>.167</td><td>.171</td><td>.160</td><td>.145</td><td>.041</td><td>3.10</td><td>.028</td><td>2.07</td></tr><tr><td>AR 1</td><td>.032</td><td>.036</td><td>.023</td><td>.017</td><td>.010</td><td>.000</td><td>-. 000</td><td>.004</td><td>-. 019</td><td>-. 043</td><td>.074</td><td>5.51</td><td>.056</td><td>5.79</td></tr><tr><td>AR 2</td><td>.008</td><td>.018</td><td>.013</td><td>.001</td><td>.010</td><td>.006</td><td>.001</td><td>.003</td><td>-. 004</td><td>-. 033</td><td>.041</td><td>3.74</td><td>.022</td><td>1.66</td></tr><tr><td>AR 3</td><td>.016 .015</td><td>.010</td><td></td><td>.014</td><td>.017</td><td>.004</td><td>-. 002</td><td>.004</td><td>-. 007</td><td>-. 015</td><td>.031</td><td>2.71</td><td>.021</td><td>1.87</td></tr><tr><td colspan="10">B. Nondiscretionary Accruals</td><td colspan="5"></td></tr><tr><td>R 1</td><td>.139</td><td>.166</td><td>.157</td><td>.163</td><td>.165</td><td>.161</td><td>.158</td><td>.153</td><td>.159</td><td>.135</td><td>.004</td><td>.17</td><td>.007</td><td>.46</td></tr><tr><td>R 2</td><td>.138</td><td>.156</td><td>.169</td><td>.159</td><td>.166</td><td>.155</td><td>.174</td><td>.149</td><td>.158</td><td>.126</td><td>.012</td><td>.67</td><td>-. 002</td><td>-. 10</td></tr><tr><td>R 3</td><td>.161</td><td>.168</td><td>.184</td><td>.179</td><td>.178</td><td>.174</td><td>.192</td><td>.179</td><td>.175</td><td>.156</td><td>.006</td><td>.31</td><td>-. 007</td><td>-. 36</td></tr><tr><td>AR 1</td><td>-. 011</td><td>.011</td><td>.008</td><td>.014</td><td>.012</td><td>.008</td><td>.007</td><td>.003</td><td>.013</td><td>-. 005</td><td>-. 006</td><td>-. 26</td><td>-. 001</td><td>-. 10</td></tr><tr><td>AR 2</td><td>-. 013</td><td>.000</td><td>.013</td><td>.004</td><td>.011</td><td>.001</td><td>.019</td><td>-. 004</td><td>.006</td><td>-. 016</td><td>.003</td><td>.19</td><td>-. 006</td><td>-. 38</td></tr><tr><td>AR 3</td><td>-. 007</td><td>-. 002</td><td>.013</td><td>.009</td><td>.006</td><td>.003</td><td>.023</td><td>.010</td><td>.006</td><td>-. 006</td><td>-. 001</td><td>-. 05</td><td>-. 008</td><td>-. 49</td></tr></table></body></html>

NoTE. The samle coise ll domestic common stocks (except fnacial fms) onNYSE, AMEX, and NASDAQ with coverage on CRSP and Compustat and with avalable data. AtthedfAahyf 9 t 1 llstcrerndbyus yyelaatlahisfrnn, sks areasidtf pfols (an n dyffhfthndof thaear) al uyldreaeallatd osbequnt y WelasreefrenlfolthdbyizedotmkRwedexechftthrflwolofon and ARretvelquallywddle flere rsdbwetbt d tl  nitstat, awell thd betwedhl adite  ahnh at l shttttxeayledeiatftvtdlabltyyelatttal asin eg. $(2).$ The nondiscretionary component of the change in an item is given by $\tilde{z}(I_{\mathrm{s}})-I_{\mathrm{s}-1},$ and the diseretionay component is I - E, (I).

All of the mispricing is due to discretionary accruals.

There is no spread in returns when portfolios are formed based on non-discretionary accruals.

The results suggest the accrual results are perhaps due to earningsmanipulation.

AR refers to abnormal returns relative to a control portfolio matched by size and book-to-market.
# Total Accruals (TAC) and Asset Growth

The reinvestment rate (b) is the ratio of net new investments to net operating profits after taxes:

$$
B (t)=\frac{I (t)}{N O P A T (t)}
$$

Invested capital (IC) is the sum of net operating working capital and net fixed and long-term operating assets. Change in invested capital equals net new investments:

$$
\begin{array}{r}{\begin{array}{r l}&{I (t)=I C (t)-I C (t-1)}\ &{I (t)=\underbrace{\left[C a p E x (t)+\Delta W C (t)\right]}_{\mathrm{Gross~Investment}}-\underbrace{D e p (t)}_{\mathrm{Replacement~Inve}}}\end{array}}\end{array}
$$

Stment Product of reinvestment rate (b) and the return on invested capital ROIC gives growth in invested capital gIC:

$$
\begin{array}{l} {{g I C(t)=b(t)\times R O I C(t)}} \ {{\qquad=\displaystyle\frac{I(t)}{N O P A T(t)}\times\frac{N O P A T(t)}{I C(t-1)}} }\ {{\qquad=\displaystyle\frac{I_{t}} {I C_{t-1}}=\frac{I C (t)-I C (t-1)}{I C (t-1)}}}\end{array}
$$

Bhojraj and Swaminathan (2009) refer to the growth in invested capital as the net new investment accruals NNI. (1-b) is capacity to pay all investors from operating profits.

# Growth in invested capital

Growth in invested capital or net operating assets is the same as the total accrual measure suggested by Richardson, Sloan, Soliman, and Tuna (2005). 3

Equation (9) shows that this total accrual measure is influenced by a firm's capital expenditure policy as well as its profitability captured by the return on invested capital.

In the empirical literature, different proxies of this total accrual measure have been used: growth in total assets, growth in net operating assets, change in net operating assets divided by total assets, or capital expenditures divided by total assets.

Given the findings that high working capital accrual firms underperform low working capital accrual firms, the hypothesis with respect  to total accruals  is that firms with high total accruals should also underperform.

Or in other words, firms with high growth in their total assets, net operating assets, or invested capital should underperform.

# Empirical findings on growth in total assets

Cooper, Gulen, and Schill (2008) examine the predictive power of annual growth in total assets. Growth in Total Assets for year 't? Is:

$$
\mathrm{gTA (t)}=[\mathrm{TA (t)}-\mathrm{TA (t-1)}]/\mathrm{TA (t-1)}
$$

# Table II Asset Growth Decile Portfolio Returns and Characteristics in Event Time

At the end of June of each year t over 1968 to 2002, stocks are allocated into deciles based on asset growth rates defined as the percentage change in total assets from the fiscal year ending in calendar year $t-2$ to fiscal year ending in calendar year t-1. Equal- and value-weighted portfolios are formed based on June (t) asset growth decile cutoffs. The portfolios are held for 1 year, from July of year $t$ to June of year $_{t+1}$ , and then rebalanced. Portfolio return statistics are reported every year for 10 years around the portfolio formation year (t) over the period of July 1968 to June of 2003. Panel A reports average annual aset growth rates. Panl B 1 reports average monthly rawreturnsto equal-weighted portfolios and Panel. 2 reports average monthly raw returns to value-weighted portfolios. Panel C.1 reports three-factor alphas ofthe equal-weighted portfolios and Panel C.2 reports three-factor alphas of the value-weighted portfolios for all frms and for three size-sorted groups. The size groups are defined by ranking firms into one of three groups small medium, and large) using the $30^{\mathrm{th}}$ and $70^{\mathrm{th}}$ NYSEmakeqitrtlJfetPrport three-factor alphas of the equal-weighted portfolios and Panel D.2 reports subperiod thre-factor alphas of the value-weighted portfolios. In Panel A, the year $^{-1}$ row reports the asset growth rates from fiscal year ending in calendar year $t{-}2$ $t{-}1$ year 1 reports the asset growth rates from fiscal year ending in calendar year $t{-}1$ t $t,$ etc. In Panel B, the year $^{-1}$ row reports the portfolio returns over July $(t{-}1)$ June (t) and year 1 reports the portfolio returns over July $(t).$ June $_{(t+1)}$ In Panel B, [-5,-1] ([1, 5) is the cumulative portfolio return over the 5 years prior (after) the portfolio formation period. All numbers, with the exception of the $t\cdot$ statistics, are in decimal form, that is 0.01 is $1\%$

Panel A: Average Annual Asset Growth Rates
<html><body><table><tr><td colspan="10">AssetGrowthDeciles</td></tr><tr><td>YEAR</td><td>1 (Low)</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10 (High)</td><td>Spread (10-1)</td><td>t (spread)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>-5 -4</td><td>0.0762</td><td>0.0771</td><td>0.0800</td><td>0.0783</td><td>0.0845</td><td>0.0924</td><td>0.102</td><td>0.1148</td><td>0.1191</td><td>0.1023</td><td>0.0260</td><td>5.04 7.34</td></tr><tr><td>-3</td><td>0.0686 0.0595</td><td>0.0704</td><td>0.0723</td><td>0.0756</td><td>0.0841</td><td>0.0937</td><td>0.1041</td><td>0.1177</td><td>0.1320 0.1483</td><td>0.1158 0.1401</td><td>0.0472 0.0805</td><td>8.61</td></tr><tr><td></td><td></td><td>0.0544</td><td>0.0641</td><td>0.0700</td><td>0.0792</td><td>0.0960</td><td>0.1097</td><td>0.1306</td><td></td><td></td><td></td><td>26.05</td></tr><tr><td>-2 -1</td><td>-0.0009</td><td>0.0257</td><td>0.0423</td><td>0.0579</td><td>0.0727</td><td>0.0930</td><td>0.1141</td><td>0.1442</td><td>0.1818</td><td>0.2143</td><td>0.2152</td><td>15.60</td></tr><tr><td></td><td>-0.2115</td><td>-0.0679</td><td>-0.0079</td><td>0.0319</td><td>0.0661</td><td>0.1025</td><td>0.1480</td><td>0.2168</td><td>0.3529</td><td>0.8357</td><td>1.0471</td><td>23.33</td></tr><tr><td>1</td><td>-0.0225 0.0249</td><td>0.0078</td><td>0.0332</td><td>0.0532</td><td>0.0719</td><td>0.0906</td><td>0.1098</td><td>0.1328</td><td>0.1580</td><td>0.1693</td><td>0.1918</td><td>9.41</td></tr><tr><td>2 3</td><td>0.0444</td><td>0.0305 0.0440</td><td>0.0445</td><td>0.0590</td><td>0.0707</td><td>0.0832</td><td>0.0947</td><td>0.1071</td><td>0.1137 0.0989</td><td>0.1076 0.0870</td><td>0.0827</td><td>7.49</td></tr><tr><td>4</td><td>0.0584</td><td>0.0503</td><td>0.0508 0.0549</td><td>0.0590 0.0607</td><td>0.0692 0.066</td><td>0.0759 0.0728</td><td>0.0875 0.0786</td><td>0.0909 0.0887</td><td>0.0927</td><td>0.0782</td><td>0.0426 0.0198</td><td>3.86</td></tr><tr><td>5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.0554</td><td>0.0561</td><td>0.0583</td><td>0.0622</td><td>0.0667</td><td>0.0708</td><td>0.0797</td><td>0.0832</td><td>0.0869</td><td>0.0767</td><td>0.0213</td><td>3.81</td></tr></table></body></html>

(continued)

Firms with high growth in total assets in the most recent year tend to have higher growth in assets in the prior years, as well as in future years. Growth in future years reverts to mean quite fast.
# What about their stock returns?

Panel B.2: Value-Weighted Portfolio Auerage Monthly Raw Returns
<html><body><table><tr><td colspan="10">Asset Growth Deciles</td></tr><tr><td>YEAR</td><td>1 (Low)</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10 (High)</td><td>Spread (10-1)</td><td>t (spread)</td></tr><tr><td>-5</td><td>0.0121</td><td>0.0123</td><td>0.0117</td><td>0.0129</td><td>0.0142</td><td>0.0146</td><td>0.0165</td><td>0.0207</td><td>0.0243</td><td>0.0271</td><td>0.0150</td><td>7.55</td></tr><tr><td>-4</td><td>0.0114</td><td>0.0109</td><td>0.0119</td><td>0.0131</td><td>0.0128</td><td>0.0146</td><td>0.0172</td><td>0.0202</td><td>0.0288</td><td>0.0307</td><td>0.0193</td><td>9.15</td></tr><tr><td>-3</td><td>0.0064</td><td>0.0085</td><td>0.0100</td><td>0.0123</td><td>0.0143</td><td>0.0151</td><td>0.0157</td><td>0.0212</td><td>0.0279</td><td>0.0357</td><td>0.0292</td><td>10.92</td></tr><tr><td>-2</td><td>0.0062</td><td>0.0083</td><td>0.0090</td><td>0.0116</td><td>0.0135</td><td>0.0149</td><td>0.017</td><td>0.0206</td><td>0.0266</td><td>0.0396</td><td>0.0334</td><td>12.86</td></tr><tr><td>-1</td><td>0.0223</td><td>0.0175</td><td>0.0153</td><td>0.0146</td><td>0.0147</td><td>0.0141</td><td>0.0153</td><td>0.0177</td><td>0.0192</td><td>0.0230</td><td>0.0007</td><td>0.28</td></tr><tr><td>1</td><td>0.0148</td><td>0.0124</td><td>0.0122</td><td>0.0116</td><td>0.0100</td><td>0.0100</td><td>0.0102</td><td>0.0092</td><td>0.0077</td><td>0.0043</td><td>-0.0105</td><td>-5.04</td></tr><tr><td>2</td><td>0.0133</td><td>0.0126</td><td>0.0125</td><td>0.0101</td><td>0.0109</td><td>0.0102</td><td>0.0098</td><td>0.0097</td><td>0.0097</td><td>0.0065</td><td>-0.0068</td><td>-3.39</td></tr><tr><td>3</td><td>0.0169</td><td>0.0137</td><td>0.0141</td><td>0.0126</td><td>0.0102</td><td>0.0112</td><td>0.0116</td><td>0.0105</td><td>0.0116</td><td>0.0116</td><td>-0.0053</td><td>-2.82</td></tr><tr><td>4</td><td>0.0132</td><td>0.0107</td><td>0.012</td><td>0.0109</td><td>0.0114</td><td>0.0103</td><td>0.0103</td><td>0.0123</td><td>0.0111</td><td>0.0120</td><td>-0.0012</td><td>-0.61</td></tr><tr><td>5</td><td>0.0128</td><td>0.0133</td><td>0.0121</td><td>0.0123</td><td>0.0103</td><td>0.01</td><td>0.0107</td><td>0.0113</td><td>0.013</td><td>0.0126</td><td>-0.0002</td><td>-0.11</td></tr><tr><td colspan="10">CumulativeReturn</td><td></td><td></td><td></td></tr><tr><td>[-5,-1]</td><td>1.0449</td><td>0.9918</td><td>1.0078</td><td>1.2375</td><td>1.3631</td><td>1.4788</td><td>1.7985</td><td>2.5321</td><td>3.9221</td><td>6.4272</td><td>5.3822</td><td>4.78</td></tr><tr><td>[1, 5]</td><td>1.2879</td><td>1.1133</td><td>1.1305</td><td>1.0038</td><td>0.931</td><td>0.8934</td><td>0.9352</td><td>0.9056</td><td>0.9458</td><td>0.7911</td><td>-0.4967</td><td>-4.25</td></tr></table></body></html>

· In each of the past 5 years high asset growth firms have outperformed low asset growth firms (these are average monthly returns, multiply them by 12 to get a rough annual return number).

·Starting in Year $+1$ , over the next five years high asset growth firms underperform low asset growth firms.

· Cumulative over the prior 5 years, high asset growth firms outperform low asset growth firms by $53\%$ ;howeverover the next 5 years they underperform by about $50\%$

· The results suggest we should avoid firms with very high growth in their total assets. Why? Extrapolation bias? Overinvestment?

# Sub-period results

Panel D 2: Value-Weighted Porfolio Fama-French Monthly Alphas
<html><body><table><tr><td colspan="10">AssetGrowthDeciles</td><td colspan="3"></td></tr><tr><td>Period</td><td>1 (Low)</td><td></td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>6</td><td>10 (High)</td><td>(10-1)</td><td>t (spread)</td></tr><tr><td>1968-1980</td><td>0.003</td><td>0.0029</td><td>0.002</td><td>0.0016</td><td>-0.0002</td><td>0.0005</td><td>-0.0001</td><td>0.0003</td><td>0.0004</td><td>-0.0005</td><td>-0.0035</td><td>-1.69</td></tr><tr><td>1981-1990</td><td>0.0006</td><td>-0.0001</td><td>0.0022</td><td>0.0025</td><td>0.0005</td><td>0.0018</td><td>0.0018</td><td>0.0001</td><td>-0.0009</td><td>-0.0059</td><td>-0.0066</td><td>-2.51</td></tr><tr><td>1991-2003</td><td>0.0037</td><td>0.001</td><td>0.001</td><td>0.0017</td><td>0.001</td><td>0.0005</td><td>0.0035</td><td>0.0031</td><td>0.0002</td><td>-0.007</td><td>-0.0107</td><td>-2.52</td></tr></table></body></html>

· Year 1 alphas from Fama-French 3-factor model show that the results are not driven by size or value effects.

Most of the effect seems to be driven by the underperformance of high asset growth firms. The spread in returns between portfolio 10 (high asset growth) and portfolio 1 (low asset growth) is mostly due to the negative returns of portfolio 10. Just like the accrual findings, this is also a short or sell signal.

The negative performance of high asset growth firms seems to have become stronger over time. Perhaps due to the tech bubble of the 1998 and 1999? Any thoughts?

· Fama-French alphas are the intercept from running a regression of the monthly returns of a portfolio on the three factors: market factor, size factor (SMB), and the value factor (HML). See page 10 of Lecture Note 10 on Value and Momentum.

# Controlling for other effects

# Table Ill Fama-MacBeth Regressions of Annual Stock Returns on Asset Growth and Other Variables

Annual stock returns from July 1968 to June 2003 are regressed on lagged accounting and return-based variables. BM (book-to-market ratio) is calculated using the Compustat data in the fiscal year ending in calendar year t 1 and is defined as in Davis, Fama, and French (20). MV is the June (t) market value, BHRET 6 is the buy-and-hold return over January (t)-June (t), BHRET 36 is the 36-month buy and hold return over July (t-3) to June (t), $C I$ is the measure o abnormal capital investment as defined in Titman, Wei, and Xie (2004), L 2 ASSETG is the asset growth defined as the percentage change in total assets from the fiscal year ending in calendar year $t-3$ tofscal year ending in calendar yeart-2, ASETG is the asset growth defined as the percentage change in total assets from the fiscal year ending in calendar year $t\mathrm{-2}$ tofiscal yearending in calendaryeart-1, 5 ASSETG is a 5-year weighted averagerank of asset growth, and 5 SALESGisa 5-yearweighted average rank of growth rate in sales. ACCRUALS is from Sloan (1996) and NOA/A is net operating assets divided by total assets adjusted from Hirshleifer, Hou, Teoh, and Zhang (2004). More details on the construction of these variables are provided in the Appendix. Size groups are defined by ranking firms into one of three groups (small medium, and large) usingthe $30^{\mathrm{th}}$ and $70^{\mathrm{th}}$ NYSE marke quitypercentils in June of yart Panel Areports egressos forallfirms, and Panels B C, and D report regressions fo smal, medium, and large firms, respectively. Beta estimates are time-series averages of cross-sectional regression betas obtained from annual cross-sectional regressions. The t-statistics, in parentheses, are adjusted forautocorrelation inthebeta estimates.

<html><body><table><tr><td colspan="10"></td><td colspan="5"></td></tr><tr><td>Model</td><td></td><td>Constant</td><td>ASSETG</td><td>L 2 ASSETG</td><td>BM</td><td>MV</td><td>BHRET 6</td><td>BHRET 36</td><td>5 YSALESG</td><td>CI</td><td>NOA/A</td><td>ACCRUALS 5 YASSETG</td><td></td></tr><tr><td>1</td><td>Beta</td><td>0.1373</td><td>-0.0922</td><td></td><td>0.029</td><td>-0.0044</td><td>0.0248</td><td>0.0056</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>t-stat</td><td>(4.55)</td><td>(-6.52)</td><td></td><td>(3.40)</td><td>(-1.57)</td><td>(1.09)</td><td>(0.57)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>Beta</td><td>0.1423</td><td>-0.0874</td><td>-0.0312</td><td>0.0276</td><td>-0.0044</td><td>0.0234</td><td>0.0062</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>t-stat</td><td>(4.65)</td><td>(-6.76)</td><td>(-2.25)</td><td>(3.32)</td><td>(-1.58)</td><td>(1.06)</td><td>(0.62)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>3</td><td>Beta</td><td>0.1378</td><td>-0.0893</td><td></td><td>0.0281</td><td>-0.0043</td><td>0.0241</td><td>0.0055</td><td>-0.0041</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>t-stat</td><td>(3.79)</td><td>(-7.41)</td><td></td><td>(3.52)</td><td>(-1.57)</td><td>(1.11)</td><td>(0.55)</td><td>(-0.27)</td><td></td><td></td><td></td><td></td></tr><tr><td>4</td><td>Beta</td><td>0.1378</td><td>-0.0868</td><td></td><td>0.029</td><td>-0.0044</td><td>0.024</td><td>0.0058</td><td></td><td>-0.0072</td><td></td><td></td><td></td></tr><tr><td></td><td>t-stat</td><td>(4.55)</td><td>(-6.05)</td><td></td><td>(3.38)</td><td>(-1.60)</td><td>(1.06)</td><td>(0.58)</td><td></td><td>(-3.32)</td><td></td><td></td><td></td></tr><tr><td>5</td><td>Beta</td><td>0.2058</td><td>-0.0918</td><td></td><td>0.0322</td><td>-0.0046</td><td>0.0249</td><td>0.0044</td><td></td><td></td><td>-0.1109</td><td></td><td></td></tr><tr><td></td><td>t-stat</td><td>(4.25)</td><td>(-6.10)</td><td></td><td>(3.75)</td><td>(-1.62)</td><td>(1.11)</td><td>(0.45)</td><td></td><td></td><td>(-2.43)</td><td></td><td></td></tr><tr><td>6</td><td>Beta</td><td>0.1223</td><td>-0.0704</td><td></td><td>0.0347</td><td>-0.0045</td><td>0.0122</td><td>0.0046</td><td></td><td></td><td></td><td>-0.1785</td><td></td></tr><tr><td></td><td>t-stat</td><td>(3.89)</td><td>(-5.24)</td><td></td><td>(4.22)</td><td>(-1.59)</td><td>(0.41)</td><td>(0.44)</td><td></td><td></td><td></td><td>(-4.00)</td><td></td></tr><tr><td>7</td><td>Beta</td><td>0.1739</td><td>-0.0839</td><td></td><td>0.0245</td><td>-0.0041</td><td>0.0229</td><td>0.0049</td><td></td><td></td><td></td><td></td><td>-0.0275</td></tr><tr><td></td><td>t-stat</td><td>(5.43)</td><td>(-6.98)</td><td></td><td>(3.14)</td><td>(-1.50)</td><td>(1.03)</td><td>(0.48)</td><td></td><td></td><td></td><td></td><td>(-2.22)</td></tr></table></body></html>

Asset growth is a strong predictor of next year's stock returns even after controlling for value, past sales growth, momentum, accruals, capital expenditures, etc.

· The results are strong even for large size firms (Panel D).

· The results in this paper show that asset growth is the strongest predictor of returns.

The slope coefficients are annual returns and the t-statistics are in parentheses.

# Components of asset growth

Growth in total assets can be due to:

O Growth in cash. O Growth in current assets O Growth in fixed assets.

· How do these different components of assets contribute to the asset growth results?

Growth in total assets can be financed by: 0 Growth in operating liabilities 0 Growth in debt financing 0 Growth in (external) equity financing 0 Growth in retained earnings

· How do these different types of financing contribute to the asset growth effect?
Equity $=$ Preferred Stock $+$ Minority Interest $+$ Common Stock - Retained Earnings
· Debt $=$ Short-term debt $+$ Long-term debt

# Table IV Fama-MacBeth Annual Stock Return Regressions: Asset and Financing Decompositions

Annual stock returns from July 1968 to June 2003 are regressed on variables obtained from a balance sheet decomposition of asset growth into an investment aspect and a financing aspect. The investment decomposition defines total assets as the sum of: (1) Cash (△Cash: Compustat #1 ), (2) Noncash current assets (△CurAsst: Compustat #4 - Compustat #1 ), (3) Property, plant and equipment (△PPE: Compustat #8 ), and (4) Other assets (△OthAssets: △Total assets - △Cash - △CurAsst - △PPE). The financing decomposition defines total assets as the sum of: (1) Retained earnings (△RE: Compustat #36 ), (2) Stock (△Stock: Compustat #130 + Compustat $\ #60 +$ Compustat #38 - Compustat #36 ), (3) Debt (△Debt: Compustat $\ #9 +$ Compustat #34 ), and (4) Operating liabilities (△OpLiab: △Total assets $-\Delta R E-\Delta S t o c h-\Delta D e b t).$ Variables used in the cross-sectional regressions are changes in these variables from the fiscal year ending in calendar year $t-2$ to the fiscal year ending in calendar year $t{-}1$ scaled by total assets in the fiscal year ending in calendar year $t{-}2$ . Size groups are defined by ranking firms into one of three groups (small, medium, and large) using the $30^{\mathrm{th}}$ and $70^{\mathrm{th}}$ NYSE market equity percentiles in June of year t. Panel A reports regressions for all firms, and Panels B, C, and D report regressions for small, medium, and large firms, respectively. Beta estimates are time-series averages of cross-sectional regression betas obtained from annual cross-sectional regressions. T-statistics, in parentheses, are adjusted for autocorrelation in the beta estimates.

Panel A. All Firms
<html><body><table><tr><td>Constant</td><td>△Cash</td><td>△CurAsst</td><td>△PPE</td><td>△OthAssets</td><td>△OpLiab</td><td>△Debt</td><td>△Stock</td><td>△RE</td></tr><tr><td>0.1555</td><td>-0.0014</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.38)</td><td>(-0.03)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1639</td><td></td><td>-0.1995</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.64)</td><td></td><td>(-4.80)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1629</td><td></td><td></td><td>-0.2015</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.41)</td><td></td><td></td><td>(-3.91)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1556</td><td></td><td></td><td></td><td>-0.1202</td><td></td><td></td><td></td><td></td></tr><tr><td>(5.34)</td><td></td><td></td><td></td><td>(-3.34)</td><td></td><td></td><td></td><td></td></tr><tr><td>0.1703</td><td>0.0076</td><td>-0.154</td><td>-0.1483</td><td>-0.0704</td><td></td><td></td><td></td><td></td></tr><tr><td>(5.61)</td><td>(0.19)</td><td>(-3.74)</td><td>(-2.76)</td><td>(-1.95)</td><td></td><td></td><td></td><td></td></tr><tr><td>0.1615</td><td></td><td></td><td></td><td></td><td>-0.1704</td><td></td><td></td><td></td></tr><tr><td>(5.45)</td><td></td><td></td><td></td><td></td><td>(-4.00)</td><td></td><td></td><td></td></tr><tr><td>0.1595</td><td></td><td></td><td></td><td></td><td></td><td>-0.1583</td><td></td><td></td></tr><tr><td>(5.47)</td><td></td><td></td><td></td><td></td><td></td><td>(-6.59)</td><td></td><td></td></tr><tr><td>0.1612</td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.2158</td><td></td></tr><tr><td>(5.50)</td><td></td><td></td><td></td><td></td><td></td><td></td><td>(-1.88)</td><td></td></tr><tr><td>0.1567</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.0654</td></tr><tr><td>(5.39)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(-0.83)</td></tr><tr><td>0.1689</td><td></td><td></td><td></td><td></td><td>-0.0507</td><td>-0.1503</td><td>-0.1986</td><td>-0.0759</td></tr><tr><td>(5.59)</td><td></td><td></td><td></td><td></td><td>(-0.99)</td><td>(-5.01)</td><td>(-2.13)</td><td>(-0.91)</td></tr></table></body></html>

<html><body><table><tr><td colspan="9">Panel D. Large Size Firms</td></tr><tr><td>Constant</td><td>△Cash</td><td>△CurAsst</td><td>△PPE</td><td>△OthAssets</td><td>△OpLiab</td><td>△Debt</td><td>△Stock</td><td>△RE</td></tr><tr><td>0.1225</td><td>0.0446</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.34)</td><td>(0.54)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1273</td><td></td><td>-0.0892</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.50)</td><td></td><td>(-1.18)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1319</td><td></td><td></td><td>-0.1897</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(5.60)</td><td></td><td></td><td>(-2.62)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.1233</td><td></td><td></td><td></td><td>-0.1579</td><td></td><td></td><td></td><td></td></tr><tr><td>(5.43)</td><td></td><td></td><td></td><td>(-1.53)</td><td></td><td></td><td></td><td></td></tr><tr><td>0.1345</td><td>0.0562</td><td>-0.0165</td><td>-0.1665</td><td>-0.1125</td><td></td><td></td><td></td><td></td></tr><tr><td>(5.72)</td><td>(0.72)</td><td>(-0.22)</td><td>(-2.64)</td><td>(-1.12)</td><td></td><td></td><td></td><td></td></tr><tr><td>0.125</td><td></td><td></td><td></td><td></td><td>-0.0538</td><td></td><td></td><td></td></tr><tr><td>(5.41)</td><td></td><td></td><td></td><td></td><td>(-0.68)</td><td></td><td></td><td></td></tr><tr><td>0.1251</td><td></td><td></td><td></td><td></td><td></td><td>-0.0688</td><td></td><td></td></tr><tr><td>(5.51)</td><td></td><td></td><td></td><td></td><td></td><td>(-1.79)</td><td></td><td></td></tr><tr><td>0.1277</td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.3374</td><td></td></tr><tr><td>(5.41)</td><td></td><td></td><td></td><td></td><td></td><td></td><td>(-3.27)</td><td></td></tr><tr><td>0.129</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.1208</td></tr><tr><td>(5.55)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(-1.06)</td></tr><tr><td>0.1319</td><td></td><td></td><td></td><td></td><td>0.0789</td><td>-0.056</td><td>-0.3228</td><td>-0.1097</td></tr><tr><td>(5.69)</td><td></td><td></td><td></td><td></td><td>(0.92)</td><td>(-1.15)</td><td>(-2.61)</td><td>(-0.95)</td></tr></table></body></html>

How do these results differ from those for all firms?

# Risk or mispricing?

· Three factor Fama-French results show that the asset growth effect is not captured by size and value effects. The paper also shows that high asset growth firms experience negative earnings surprises around future quarterly earnings announcements. · Suggests investors are too optimistic about the future earnings of these firms and are disappointed when they see the actuals.

# Questions and interpretation

Firms with high working capital accruals underperform.
Firms with high asset growth, capital expenditures, growth in invested capital underperform.
The hypothesis behind working capital accruals is about investors not understanding quality of earnings and not paying sufficient attention to cash flows. Why do firms with high asset growth underperform? Is it because managers overinvest anticipating high future sales that do not materialize?
· Is it because investors become overoptimistic about the future prospects of firms that are on an investment spree? Another manifestation of the extrapolation bias?
· If equity investors do not pay sufficient attention to the difference between earnings and cash flows what about corporate bond investors? Do they understand the difference?

# Accruals, asset growth, and corporate bond returns

Bhojraj and Swaminathan (2009) examine the relationship between accruals and corporate bond returns:

· Debt is serviced from cash flows not earnings; hence earnings quality and cash flow analysis should be even more important to corporate bond investors. The corporate bond market tends to be dominated by institutional investors compared to the stock market which has more individual investors.
· Stocks and bonds are both contingent claims on the same underlying cash flows and firm value. Common cash flow information is relevant for the valuation of both securities.
Since institutional investors are likely to be more sophisticated than individual investors, perhaps the corporate bond market processes cash flow information more efficiently than the stock market.

# Two questions

· Does the corporate bond market price earnings quality/cash flow information more efficiently than the stock market? · Specifically, is there an accrual effect in the corporate bond market? Is there less earnings fixation?

Table 1 Summary statistics on corporate bonds

<html><body><table><tr><td></td><td>Nfirms</td><td>Nbonds</td><td>Nfirms</td><td>Nbonds</td><td>Nfirms</td><td>Nbonds</td><td>Nfirms</td><td>Nbonds</td><td>Nfirms</td><td>Nbonds</td></tr><tr><td>1973</td><td>195</td><td>327</td><td>61</td><td>135</td><td>89</td><td>131</td><td>32</td><td>37</td><td>22</td><td>24</td></tr><tr><td>1974</td><td>202</td><td>362</td><td>72</td><td>160</td><td>94</td><td>148</td><td>28</td><td>32</td><td>19</td><td>22</td></tr><tr><td>1975</td><td>352</td><td>1722</td><td>137</td><td>785</td><td>168</td><td>671</td><td>50</td><td>216</td><td>26</td><td>50</td></tr><tr><td>1976</td><td>428</td><td>2016</td><td>147</td><td>890</td><td>218</td><td>794</td><td>68</td><td>269</td><td>36</td><td>63</td></tr><tr><td>1977</td><td>452</td><td>2146</td><td>156</td><td>975</td><td>221</td><td>793</td><td>79</td><td>304</td><td>43</td><td>74</td></tr><tr><td>1978</td><td>479</td><td>2209</td><td>156</td><td>974</td><td>224</td><td>844</td><td>84</td><td>299</td><td>63</td><td>92</td></tr><tr><td>1979</td><td>490</td><td>2278</td><td>159</td><td>1007</td><td>228</td><td>872</td><td>81</td><td>295</td><td>72</td><td>104</td></tr><tr><td>1980</td><td>502</td><td>2316</td><td>158</td><td>985</td><td>239</td><td>899</td><td>84</td><td>324</td><td>76</td><td>108</td></tr><tr><td>1981</td><td>498</td><td>2345</td><td>154</td><td>954</td><td>226</td><td>941</td><td>79</td><td>345</td><td>62</td><td>105</td></tr><tr><td>1982</td><td>489</td><td>2329</td><td>161</td><td>961</td><td>202</td><td>889</td><td>84</td><td>321</td><td>65</td><td>158</td></tr><tr><td>1983</td><td>495</td><td>2363</td><td>166</td><td>1062</td><td>184</td><td>813</td><td>91</td><td>307</td><td>80</td><td>181</td></tr><tr><td>1984</td><td>484</td><td>2279</td><td>153</td><td>968</td><td>177</td><td>793</td><td>91</td><td>333</td><td>77</td><td>185</td></tr><tr><td>1985</td><td>515</td><td>2401</td><td>170</td><td>1088</td><td>185</td><td>827</td><td>80</td><td>309</td><td>109</td><td>177</td></tr><tr><td>1986</td><td>560</td><td>2656</td><td>173</td><td>1155</td><td>203</td><td>927</td><td>81</td><td>366</td><td>133</td><td>208</td></tr><tr><td>1987</td><td>575</td><td>2617</td><td>165</td><td>1110</td><td>184</td><td>866</td><td>92</td><td>396</td><td>159</td><td>245</td></tr><tr><td>1988</td><td>569</td><td>2571</td><td>168</td><td>1094</td><td>189</td><td>825</td><td>91</td><td>422</td><td>152</td><td>230</td></tr><tr><td>1989</td><td>596</td><td>2715</td><td>167</td><td>1170</td><td>196</td><td>861</td><td>109</td><td>456</td><td>156</td><td>228</td></tr><tr><td>1990</td><td>585</td><td>2645</td><td>164</td><td>1071</td><td>190</td><td>930</td><td>103</td><td>416</td><td>157</td><td>228</td></tr><tr><td>1991</td><td>594</td><td>2766</td><td>173</td><td>1001</td><td>211</td><td>1156</td><td>109</td><td>373</td><td>161</td><td>236</td></tr><tr><td>1992</td><td>658</td><td>3051</td><td>152</td><td>925</td><td>211</td><td>1308</td><td>131</td><td>429</td><td>212</td><td>389</td></tr><tr><td>1993</td><td>712</td><td>3108</td><td>136</td><td>848</td><td>217</td><td>1247</td><td>153</td><td>558</td><td>241</td><td>455</td></tr><tr><td>1994</td><td>710</td><td>2536</td><td>123</td><td>642</td><td>218</td><td>1001</td><td>152</td><td>476</td><td>236</td><td>417</td></tr><tr><td>1995</td><td>771</td><td>2553</td><td>135</td><td>666</td><td>225</td><td>975</td><td>169</td><td>457</td><td>271</td><td>455</td></tr><tr><td>1996</td><td>824</td><td>2641</td><td>134</td><td>735</td><td>228</td><td>886</td><td>181</td><td>502</td><td>305</td><td>518</td></tr><tr><td>1997</td><td>786</td><td>2403</td><td>124</td><td>662</td><td>224</td><td>835</td><td>174</td><td>460</td><td>284</td><td>446</td></tr><tr><td colspan="9">Panel B: summary statistics on monthly returns andfactors</td><td></td></tr><tr><td>Variable</td><td></td><td></td><td>Mean (%)</td><td></td><td>Std. (%)</td><td></td><td></td><td>Autocorrelation</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>Lagl</td><td></td><td>Lag 3</td></tr><tr><td>LT Gov. Bonds</td><td></td><td></td><td>0.76</td><td></td><td>3.16</td><td></td><td></td><td>0.09</td><td></td><td>-0.13</td></tr><tr><td>AAA/AA</td><td></td><td></td><td>0.77</td><td></td><td>2.51</td><td></td><td></td><td>0.14</td><td></td><td>0.18</td></tr><tr><td>A</td><td></td><td></td><td>0.79</td><td></td><td></td><td>2.37</td><td></td><td>0.13</td><td></td><td>0.20</td></tr><tr><td>BBB</td><td></td><td></td><td>0.84</td><td></td><td></td><td>2.43</td><td></td><td>0.12</td><td></td><td>0.22</td></tr><tr><td><BBB</td><td></td><td></td><td>1.04</td><td></td><td>2.57</td><td></td><td></td><td>0.22</td><td></td><td>0.10</td></tr><tr><td>All bonds</td><td></td><td></td><td>0.84</td><td></td><td>2.29</td><td></td><td></td><td>0.12</td><td></td><td>0.21</td></tr><tr><td>Def</td><td></td><td></td><td>0.05</td><td></td><td>1.31</td><td></td><td></td><td>-0.14</td><td></td><td>0.05</td></tr><tr><td>Term</td><td></td><td></td><td>0.18</td><td></td><td>3.16</td><td></td><td></td><td>0.10</td><td></td><td>-0.12</td></tr></table></body></html>

Panel C: firm market capitalization (size) ranks
<html><body><table><tr><td>Sample</td><td>Mean</td><td>Median</td><td>Stdev</td></tr><tr><td>Overallc corporate bond sample</td><td>7.45</td><td>8</td><td>2.39</td></tr><tr><td>Bond sample limited to availability of accruals</td><td>7.49</td><td>8</td><td>2.36</td></tr><tr><td>Bond sample limited to membership in Lehman indices and availability of accruals</td><td>8.06</td><td></td><td>1.95</td></tr></table></body></html>

The sample of firms used in this study represents larger firms because they are all rated by Moody's or S&P 500.

If there are multiple bond issues outstanding per firm, the bond return for the firm is value-weighted average of the individual bond returns based on the market value of each outstanding bond issue.

Since bonds are less volatile than stocks, we cannot just compare return spreads; we will have to compare them on an equivalentvolatilitybasis.

Sharpe Ratios provide a comparison on a volatility adjusted basis.

NNI $=$ Growth in invested capital [IC (t) - IC (t-1)]/IC (t-1)

WCA = [△WC - Dep]/Beginning year Total Assets

# Accrual effect in the stock returns of the sample firms

Table 2 Operating accruals and stock returns

<html><body><table><tr><td colspan="9">Panel A: Net new investment accruals (NNI)</td></tr><tr><td>Portfolio</td><td>NNI</td><td>Qtr 1</td><td>Qtr 2 </td><td>Qtr 3</td><td>Qtr 4</td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-32.87</td><td>3.38 (5.39)</td><td>3.48 (5.64)</td><td>3.45 (5.59)</td><td>3.68 (7.24)</td><td>20.56 (7.94)</td><td>19.85 (8.71)</td><td>18.50 (7.67)</td></tr><tr><td>P 3</td><td>5.93</td><td>2.64 (5.41)</td><td>2.77 (5.61)</td><td>2.71 (5.40)</td><td>2.96 (5.50)</td><td>16.63 (6.53)</td><td>17.99 (7.64)</td><td>16.79 (7.93)</td></tr><tr><td>P 5</td><td>117.53</td><td>2.36 (3.27)</td><td>2.56 (3.45)</td><td>2.70 (3.48)</td><td>3.09 (3.85)</td><td>13.92 (4.55)</td><td>16.58 (5.48)</td><td>17.22 (6.32)</td></tr><tr><td>P 5-P 1</td><td></td><td>-1.02 (-3.55)</td><td>-0.92 (-3.00)</td><td>-0.75 (-2.16)</td><td>-0.59 (-1.43)</td><td>-6.64 (-4.51)</td><td>-3.27 (-2.16)</td><td>-1.28 (-0.95)</td></tr><tr><td>Absolute sharpe ratio</td><td></td><td></td><td></td><td></td><td></td><td>0.71</td><td>0.33</td><td>0.14</td></tr><tr><td colspan="9">Panel B: Net working capital accruals (WCA)</td></tr><tr><td>Portfolio</td><td>WCA</td><td>Qtr 1</td><td>Qtr 2 </td><td>Qtr 3</td><td>Qtr 4 </td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-13.39</td><td>3.22 (5.04)</td><td>3.20 (5.03)</td><td>3.03 (4.82)</td><td>2.11 (5.04)</td><td>17.87 (6.38)</td><td>16.84 (6.82)</td><td>17.22 (7.30)</td></tr><tr><td>P 3</td><td>-3.96</td><td>3.13 (5.99)</td><td>3.31 (6.56)</td><td>3.27 (6.42)</td><td>2.35 (7.02)</td><td>17.92 (8.11)</td><td>19.19 (9.47)</td><td>17.48 (8.57)</td></tr><tr><td>P 5</td><td>5.27</td><td>2.48 (3.27)</td><td>2.75 (3.62)</td><td>2.80 (3.73)</td><td>2.09 (4.46)</td><td>14.23 (4.70)</td><td>17.44 (6.34)</td><td>17.94 (6.82)</td></tr><tr><td>P 5-P 1</td><td></td><td>-0.73 (-2.39)</td><td>-0.45 (-1.54)</td><td>-0.23 (-0.81)</td><td>-0.01 (-0.07)</td><td>-3.64 (-2.71)</td><td>0.60 (0.58)</td><td>0.72 (0.61)</td></tr><tr><td>Absolute sharpe ratio</td><td></td><td></td><td></td><td></td><td></td><td>0.41</td><td>0.08</td><td>0.08</td></tr></table></body></html>

# Accrual effect in the bond returns of sample firms

Table 3 Operating accruals and corporate bond returns

<html><body><table><tr><td colspan="12">Panel A: Net new investment accruals (NNI)</td></tr><tr><td>Porfolio</td><td>NNI</td><td>Rating</td><td>Duration</td><td>NFRM Qtr 1</td><td></td><td>Qtr 2</td><td>Qtr 3</td><td>Qtr 4 </td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-32.87</td><td>9.9</td><td>6.4</td><td>81</td><td>2.72 (7.18)</td><td>2.64 (7.35)</td><td>2.48 (7.16)</td><td>2.34 (5.78)</td><td>10.63 (6.18)</td><td>10.68 (6.30)</td><td>10.36 (5.97)</td></tr><tr><td>P 3</td><td>5.93</td><td>7.7</td><td>7.2</td><td>82</td><td>2.47 (6.26)</td><td>2.42 (6.33)</td><td>2.30 (6.20)</td><td>2.18 (4.99)</td><td>9.71 (5.55)</td><td>10.24 (5.71)</td><td>10.09 (5.38)</td></tr><tr><td>P 5</td><td>117.53</td><td>9.1</td><td>6.6</td><td>81</td><td>2.35 (6.35)</td><td>2.33 (6.45)</td><td>2.28 (6.49)</td><td>2.21 (5.18)</td><td>9.48 (5.72)</td><td>10.03 (5.96)</td><td>10.44 (5.72)</td></tr><tr><td>P 5-P 1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.37 (-5.29)-0.31 (-4.18)-0.20 (-3.00)-0.13 (-1.83)</td><td></td><td>-1.15 (-4.15)-0.65 (-2.59)</td><td>0.08 (0.20)</td></tr><tr><td>Absolute sharpe ratio</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.65</td><td>0.36</td><td>0.03</td></tr><tr><td colspan="10">Panel B: Net working capital accruals (WCA)</td><td></td><td></td><td></td></tr><tr><td>Portfolio</td><td>WCA</td><td>Rating</td><td></td><td>Duration</td><td>NFRM Qtr 1</td><td>Qtr 2</td><td>Qtr 3</td><td>Qtr 4 </td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-13.39</td><td>9.73</td><td>6.84</td><td>84</td><td>2.57 (6.87)</td><td>2.55 (6.98)</td><td>2.43 (6.93)</td><td>2.35 (5.60)</td><td>10.30 (5.99)</td><td>10.87 (6.35)</td><td>10.48 (5.99)</td></tr><tr><td>P 3</td><td>-3.96</td><td>8.47</td><td>7.30</td><td>84</td><td>2.41 (6.18)</td><td>2.40 (6.37)</td><td>2.33 (6.30)</td><td>2.25 (5.17)</td><td>9.75 (5.63)</td><td>10.43 (5.95)</td><td>10.17 (5.50)</td></tr><tr><td>P 5</td><td>5.27</td><td>9.32</td><td>6.81</td><td>84</td><td>2.43 (6.71)</td><td>2.32 (6.60)</td><td>2.22 (6.48)</td><td>2.10 (5.07)</td><td>9.37 (5.70)</td><td>9.87 (6.17)</td><td>10.35 (5.69)</td></tr><tr><td>P 5-P 1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>(6-) 860- (087-) 0- (88-) 070- (9-) 70- (981-) 910-</td><td></td><td>）-1.00 (-3.28)-0.14 (-0.38</td></tr><tr><td>Absolute sharpe ratio</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.49</td><td>0.52</td><td>0.06</td></tr></table></body></html>

There is a strong accrual effect in corporate bonds.
# Ratings and Duration adjusted corporate bond returns

Table 5 Ratings and duration adjusted corporate bond returns
<html><body><table><tr><td colspan="8">Panel A: Net new investment accruals (NNI)</td></tr><tr><td>Portfolio</td><td>NNI</td><td>Qtr 1</td><td>Qtr 2</td><td>Qtr 3</td><td>Qtr 4</td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-32.87</td><td>0.18 (3.38)</td><td>0.14 (2.35)</td><td>0.07 (1.00)</td><td>-0.04 (-0.49)</td><td>0.51 (1.58)</td><td>-0.26 (-0.90)</td><td>-0.11 (-0.37)</td></tr><tr><td>P 3</td><td>5.93</td><td>0.02 (0.63)</td><td>0.00 (0.07)</td><td>-0.05 (-1.12)</td><td>-0.13 (-2.14)</td><td>-0.18 (-0.99)</td><td>-0.45 (-2.37)</td><td>-0.58 (-3.29)</td></tr><tr><td>P 5</td><td>117.53</td><td>-0.11 (-1.87)</td><td>-0.12 (-1.88)</td><td>-0.11 (-1.81)</td><td>-0.05 (-0.44)</td><td>-0.51 (-2.24)</td><td>-0.52 (-1.73)</td><td>0.06 (0.12)</td></tr><tr><td>P 5-P 1</td><td></td><td>-0.29 (-4.51)</td><td>-0.26 (-3.83)</td><td>-0.18 (-2.66)</td><td>-0.01 (-0.06)</td><td>-1.02 (-3.49)</td><td>-0.26 (-0.66)</td><td>0.17 (0.31)</td></tr><tr><td colspan="9">Panel B: Net working capital accruals (WCA)</td></tr><tr><td>Portfolio</td><td>WCA</td><td>Qtr 1</td><td>Qtr 2</td><td>Qtr 3</td><td>Qtr 4</td><td>Year 1</td><td>Year 2</td><td>Year 3</td></tr><tr><td>P 1</td><td>-13.39</td><td>0.03 (0.56)</td><td>0.06 (1.01)</td><td>-0.01 (-0.18)</td><td>-0.03 (-0.29)</td><td>0.07 (0.25)</td><td>0.00 (0.01)</td><td>-0.22 (-0.71)</td></tr><tr><td>P 3</td><td>-3.96</td><td>-0.01 (-0.23)</td><td>-0.01 (-0.15)</td><td>0.00 (0.04)</td><td>-0.04 (-0.51)</td><td>-0.07 (-0.32)</td><td>-0.19 (-1.00)</td><td>-0.35 (-1.96)</td></tr><tr><td>P 5</td><td>5.27</td><td>-0.06 (-0.97)</td><td>-0.14 (-1.95)</td><td>-0.18 (-2.41)</td><td>-0.24 (-2.90)</td><td>-0.70 (-2.80)</td><td>-1.00 (-3.48)</td><td>-0.32 (-1.25)</td></tr><tr><td>P 5-P 1</td><td></td><td>-0.09 (-1.39)</td><td>-0.20 (-2.98)</td><td>-0.17 (-2.43)</td><td>-0.22 (-2.67)</td><td>-0.77 (-3.00)</td><td>-1.01 (-3.41)</td><td>-0.09 (-0.28)</td></tr></table></body></html>

This table summarizes ratings and duration adjusted corporate bond returns of investment and accrual porfolios using bond market retums for the full sample (as in Table 3) from January 1973 to February 1997. Portfolios are formed and the returns are deined as in Table 3. The raw returns are adjusted for bond rating and maturity as follows. First, all available bonds (including those that belong to frms for which accruals and net new investments data are not available) are sorted into three rating categories-AAA/AA, A and BBB and below BBB. Next, the firms are sorted in to three duration categories. We then subtract from each bond's return the return of the rating-duration porfolio to which the bond belongs to compute risk-adjusted bond retum. The risk-adjusted bond returns of each frm are then value-weighted to compute the benchmark-adjusted bond retum for each firm. These retums are the used to compute porfolio returns over the next four quarters and next three years as presented below. ${\mathrm{Qtr}}=1.$ 2, 3, and 4 are the next four quarter returns. The numbers in parentheses are Newey-West & Hansen-Hodrick auto-correlation corrected t-statistics. The number of lags used in the autocorrelation correction is two for quarterly returns and 11 for annual returns

· The relevant risks for corporate bond are default risk and maturity risk.
· Match each corporate bond to a benchmark portfolio of bonds with similar ratings and duration and compute riskadjusted return as the bond return minus the matching portfolio return. Risk adjusted results mirror the raw results in Table 2.
· Results suggest that the corporate bond market also misprices information in accruals about earnings quality and is fixated on earnings. Why?

# External Financing

$$
F C F F (t)=N O P A T (t)-I (t)
$$

If free cash flows $>0$ , then the firm can return capital to its investors through dividends, stock buybacks and debt retirements. If free cash flows $<0$ , then the firm uses external financing to fund its net new investments.

The external financing consists of debt issues and equity issues

# Pecking order financing

· There is an adverse selection argument against raising external capital (Myers and Majluf, 1984).
● Firms will issue external equity or debt only when their equity or debt is overvalued.
If investors cannot distinguish between good firms and bad firms when they come to the market to issue equity, they will assign an average value to all firms that issue equity.
· This average value is too low for good firms and high for bad firms. So good firms who do not want to dilute their equity will stay out and the only firms that come to the market are bad firms.
● Therefore their prices will drop when the issue external equity Or debt. Data supports this hypothesis.
Therefore, good firms will prefer internal funds to external financing.

# Long term returns after external equity financing

Firms that issue equity underperform in the long-run. There is evidence of long-term underperformance after IPOs and SEOs (Loughran and Ritter, 1995).

Pontiff and Woodgate (2008) use growth in shares outstanding to study the effects of external equity financing.

Annual growth in shares (adjusted for stock splits) can be computed based on the shares outstanding reported by a company.

If growth in shares is positive this implies the company is issuing equity.

If growth in shares is negative, this implies the company is repurchasing stock.

Since managers tend to issue shares when their stock is overvalued and buyback shares when their stock is undervalued positive growth in shares should lead to negative stock returns in the future and negative growth in shares should lead to positive stock returns in the future.

Table IHI of Pontiff and Woodgate (2008).

There was much less stock issuance activity and no predictability in the pre-1970 period (Table VI). Why?
Panel C: Dependent variable is the one-year stock return
<html><body><table><tr><td colspan="9"></td></tr><tr><td>Intercept</td><td>BM</td><td>BM Dum</td><td>ME</td><td>MOM</td><td>ISSUE</td><td>DT-ISSUE</td><td>DT-Dum</td><td>Avg. R 2</td></tr><tr><td>10.36</td><td>4.56 (5.41)</td><td>8.39</td><td></td><td></td><td></td><td></td><td></td><td>1.37</td></tr><tr><td>(3.84)</td><td></td><td>(7.54)</td><td>-1.15</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>28.88</td><td></td><td></td><td>(-1.76)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(3.21)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.28</td></tr><tr><td>15.92</td><td></td><td></td><td></td><td>9.62</td><td></td><td></td><td></td><td></td></tr><tr><td>(7.17)</td><td>3.33</td><td></td><td></td><td>(3.61)</td><td></td><td></td><td></td><td>1.17</td></tr><tr><td>23.30</td><td>(3.65)</td><td>8.58</td><td>-1.20</td><td>8.66</td><td></td><td></td><td></td><td></td></tr><tr><td>(2.71)</td><td></td><td>(9.48)</td><td>(-1.93)</td><td>(3.58)</td><td></td><td></td><td></td><td>3.59</td></tr><tr><td>16.95</td><td></td><td></td><td></td><td></td><td>-27.32</td><td></td><td></td><td></td></tr><tr><td>(7.32)</td><td></td><td></td><td></td><td></td><td>(-7.51)</td><td></td><td></td><td>0.49</td></tr><tr><td>18.17</td><td></td><td></td><td></td><td></td><td></td><td>-8.38</td><td>-4.68</td><td></td></tr><tr><td>(8.95)</td><td></td><td></td><td></td><td></td><td></td><td>(-5.94)</td><td>(-2.32)</td><td>1.22</td></tr><tr><td>18.20</td><td></td><td></td><td></td><td></td><td>-20.71</td><td>-4.81</td><td>-3.60</td><td></td></tr><tr><td>(8.94)</td><td>2.59</td><td>7.96</td><td>-1.37</td><td></td><td>(-5.08)</td><td>(-2.87)</td><td>(-1.74)</td><td>1.43</td></tr><tr><td>27.25 (3.38)</td><td>(3.33)</td><td>(8.54)</td><td>(-2.32)</td><td>8.02 (3.50)</td><td>-16.52</td><td>-3.41</td><td>-3.24</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>(-5.61)</td><td>(-2.60)</td><td>(-2.63)</td><td>4.27</td></tr><tr><td colspan="9">Panel D: Dependent variable is the second-year stock return.</td><td></td></tr><tr><td>Intercept</td><td>BM</td><td>BM Dum</td><td>ME</td><td>MOM</td><td>ISSUE</td><td>DT-ISSUE</td><td>DT-Dum</td><td>Avg. R 2</td></tr><tr><td>12.98 (5.52)</td><td>3.38 (4.33)</td><td>5.75 (5.50)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>30.14</td><td></td><td></td><td>-1.13</td><td></td><td></td><td></td><td></td><td>1.02</td></tr><tr><td>(4.14)</td><td></td><td></td><td>(-2.25)</td><td></td><td></td><td></td><td></td><td>1.45</td></tr><tr><td>17.55</td><td></td><td></td><td></td><td>-2.78</td><td></td><td></td><td></td><td></td></tr><tr><td>(8.69)</td><td></td><td></td><td></td><td>(-1.35)</td><td></td><td></td><td></td><td>0.46</td></tr><tr><td>23.26</td><td>2.38</td><td>6.46</td><td>-0.93</td><td>-3.69</td><td></td><td></td><td></td><td></td></tr><tr><td>(3.27)</td><td>(3.28)</td><td>(6.94)</td><td>(-1.87)</td><td>(-1.97)</td><td></td><td></td><td></td><td>2.71</td></tr><tr><td>17.93</td><td></td><td></td><td></td><td></td><td>-20.03</td><td></td><td></td><td></td></tr><tr><td>(8.70)</td><td></td><td></td><td></td><td></td><td>(-6.20)</td><td></td><td></td><td>0.31</td></tr><tr><td>18.13</td><td></td><td></td><td></td><td></td><td></td><td>-5.40</td><td>-1.82</td><td></td></tr><tr><td>(8.96)</td><td></td><td></td><td></td><td></td><td></td><td>(-3.25)</td><td>(-0.44)</td><td>0.51</td></tr><tr><td>18.19</td><td></td><td></td><td></td><td></td><td>-13.69</td><td>-3.55</td><td>-1.70</td><td></td></tr><tr><td>(8.98)</td><td></td><td></td><td></td><td></td><td>(-4.00)</td><td>(-1.97)</td><td>(-0.41)</td><td>0.60</td></tr><tr><td>23.81</td><td>2.10</td><td>6.32</td><td>-0.92</td><td>-3.94</td><td>-11.63</td><td>-2.68</td><td>-0.80</td><td></td></tr><tr><td>(3.40)</td><td>(3.02)</td><td>(6.86)</td><td>(-1.84)</td><td>(-2.19)</td><td>(-3.88)</td><td>(--1.86)</td><td>(-0.20)</td><td>3.14</td></tr></table></body></html>

ISSUE is past one year growth in shares outstanding DT-ISSUE is past five-year growth in shares outstanding. The table reports similar results based on Year 3 stock returns.

How is this related to our discussion on stock mergers?
# What is the relation between asset growth and external financing?

· Firms whose assets grow due to net new investments are the ones who might need external financing.
· Are the asset growth effect and the external financing effect two sides of the same coin?
· In other words, is the underperformance of high asset growth firms and firms that issue equity and debt essentially the same effect since these firms are one and the same? See also Table 4 D of Cooper, Gulen and Schill (2008).
· Pontiff and Woodgate (2008) also show that their results are not driven by the underperformance following stock mergers.
· Overall the results suggest that high accruals, high asset growth, and high external financing are all bearish signals for individual stocks.
Are there firms for which high asset growth and external financing might not be negative signals? How would you ascertain that? What additional information about the firm you might need to determine this?
·How would you use this in your final valuation project?

# Lecture Note 12 Quality and Stock Returns

# Value Drivers of free cash flows and firm value

There are three key value drivers of free cash flows and value:

· The rate of growth of a company's revenues, profits, and operating assets (g).
· The return on new investment (ROI), which determines the profitability of the new investments undertaken by the business.
· The firm's reinvestment rate/plowback rate (b) or $(\mathrm{k})$ ,which determines its capital expenditure (new investments) policy.
There are only two independent value drivers. Given two value drivers, the third one can be determined as a function o the other two.

Recall from Lecture Note 5 (Valuation by Multiples):

$$
\frac{P_{0}}{E_{0}}=\frac{(1+g)(1-k)}{r_{e}-g}
$$

$$
\frac{P_{0}}{B_{0}}=\frac{R O E-g}{r_{e}-g}
$$

Firm valuation is driven by $(\mathrm{g})$ ,(RO 1), and $(\mathrm{k})$ which are the variables used to measure quality. ROE, ROA, and ROIC are used as proxies of ROI.

# What is Quality?

<html><body><table><tr><td>Firm</td><td>g</td><td>k</td><td>ROE</td><td>re</td><td>P/E*</td><td>P/B*</td></tr><tr><td>A</td><td>5%</td><td>50%</td><td>10%</td><td>9%</td><td>13.13</td><td>1.25</td></tr><tr><td>B</td><td>6%</td><td>45%</td><td>13.33%</td><td>9%</td><td>19.43</td><td>2.43</td></tr></table></body></html>

· Since B grows faster than $\mathrm{A}$ and earns a higher ROE, B is a higher quality firm than A.

$\mathrm{P/E^{*}}$ and $\mathrm{P}/\mathrm{B}^{\ast}$ represent the warranted or fair value valuation multiples based on the expressions in equations (1) and (2). B is more valuable than A. Higher quality should lead to higher intrinsic value.

· If the observed multiples were different from the warranted multiples then the stocks would be mispriced.

B is higher quality than A. Is B a better investment than A?

Case 1: P/E (A) $\underline {{\underline{{\mathbf{\delta\pi}} }}}$ 13.13, P/B (A) $\underline {{\underline{{\mathbf{\delta\pi}} }}}$ 1.25; P/E (B) $\underline {{\underline{{\mathbf{\delta\pi}} }}}$ 19.43, $\mathrm{P}/\mathrm{B}(\mathrm{B}){=}2.43$

Case 2: P/E (A)=9, P/B (A)=0.7; and P/E (B)=25, P/B (B)=3.

Case 3: P/E (A) $=$ 13.13, P/B (A)=1.25 and P/E (B) $=$ 13.13, $\mathrm{P}/\mathrm{B}(\mathrm{B}){=}1.25$

Quality cannot be pursued independent of valuation!
# When would we prefer higher quality?

Holding valuations constant, we would prefer companies with higher growth, higher ROI and lower risk.

If a firm earns a high return on investment, then a given growth rate can be achieved with lower plowback rate. The firm can then return more capital to investors. Sustainable growth rate: g $=\mathrm{k^{*}}$ ROI.

# Measures of Quality

High Growth in earnings, EBIT, and sales.
High ROE, ROA, ROIC o Profit margins O Turnover ratios

Low beta, standard deviation Low plow back rates and reinvestment rates

Recall the F-score of Pietroski (2000) from Lecture Note 10:

Value Winners and Value Losers based on ROA, CFO/TA, △ROA, Leverage and Liquidity, Change in Gross Margin and Turnover Ratio, Accrual, Equity Issuance.

F-Score is a measure of quality.
# Gross Profitability Premium

Novy-Marx (2012) examines one measure of quality:

Gross Profits/Total Assets

Gross Profits $=$ Sales - Cost of Goods Sold (excluding depreciation and amortization)

Why gross profits?

There really isn't any theoretical rationale for favoring Gross Profits/Total Assets over EBITDA/Total Assets.

Table 1 estimates cross-sectional regressions involving gross profitability, earnings, and cash flows and controlling for size, B/M ratios, and past returns.

Every month from July 1963 to December 2010, monthly regressions of next month's return on all independent variables are estimated using all available firms. The monthly time-series of  cross-sectional  regression  estimates  are  averaged   and reported.

Note all subsequent results are in monthly returns in percent multiply by 12 to get an approximate annual figure.
Table 1. Fama-MacBeth regressions of retums on measures of profitability.
Panel A reports results from Fama-MacBeth regressions of returns on gross profits (revenues minus cost of goods sold, REVT - COGS) scaled by assets (AT), and income before extraordinary items (IB) and free cash flow (net income plus amortization and depreciation minus changes in working capital and capital expenditures, ${\bf N I}+$ DP - WCAPCH - CAPX) each scaled by book equity. Panel B repeats the tests employing profitability measures demeaned by industry (Fama-French 49). Regressions include controls for book-to-market $(\log (\mathbf{B}/\mathbf{M}),$ , size $(\log (\mathrm{ME}))$ , and past performance measured at horizons of one month $(r_{1,0})$ and twelve to two months $(r_{12,2})$ Independent variables are trimmed at the one and $99\%$ levels. The sample
<html><body><table><tr><td colspan="8">couesorsix, aldc coveishu slope coefficients (x 10²) and [test-statistics] from</td></tr><tr><td>independent variables</td><td>(1) (2)</td><td colspan="6">regressions of the form rtj = β'xij + etj (3) (4) (5)</td></tr><tr><td colspan="8">Panel A: straight profitability variables</td></tr><tr><td>gross profitability</td><td>0.75 [5.49]</td><td></td><td></td><td>0.69 [5.22]</td><td>0.62</td><td></td><td>0.61</td></tr><tr><td>earnings</td><td></td><td>0.22</td><td></td><td>0.08</td><td>[4.63]</td><td>-0.02 [-0.06]</td><td>[4.59] -0.07 [-0.27]</td></tr><tr><td>free cash flow</td><td></td><td>[0.84]</td><td>0.27 [2.28]</td><td>[0.31]</td><td>0.20 [1.64]</td><td>0.39 [3.17]</td><td>0.33 [2.67]</td></tr><tr><td>log (B/M)</td><td>0.35</td><td>0.30</td><td>0.26</td><td>0.34</td><td>0.30</td><td>0.27</td><td>0.31</td></tr><tr><td>log (ME)</td><td>[5.98] -0.09</td><td>[4.97] -0.12</td><td>[4.59] -0.13 [-3.20]</td><td>[5.54] -0.11</td><td>[5.17] -0.11</td><td>[4.48] -0.13</td><td>[5.05] -0.11 [-2.92]</td></tr><tr><td>11,0</td><td>[-2.29] -5.57</td><td>[-3.24] -5.49</td><td>-5.52</td><td>[-2.78] -5.64</td><td>[-2.80] -5.66</td><td>[-3.34] -5.56</td><td>-5.70</td></tr><tr><td>112,2</td><td>[-13.8] 0.76 [3.87]</td><td>[-13.7] 0.78 [4.02]</td><td>[-13.7] 0.78 [4.02]</td><td>[-14.1] 0.74 [3.80]</td><td>[-14.1] 0.74 [3.80]</td><td>[-13.9] 0.76 [3.93]</td><td>[-14.3] 0.73 [3.74]</td></tr><tr><td colspan="8">Panel B: profitability variables demeaned by industry</td></tr><tr><td>gross profitability</td><td>1.00 [8.99]</td><td></td><td></td><td>0.94 [9.75]</td><td>0.94 [8.38]</td><td></td><td>0.92 [8.39]</td></tr><tr><td>earnings</td><td></td><td>0.28 [1.86]</td><td></td><td>0.04 [0.15]</td><td></td><td>0.09 [0.51]</td><td>0.02 [0.13]</td></tr><tr><td>free cash flow</td><td></td><td></td><td>0.16 [2.54]</td><td></td><td>0.09 [1.23]</td><td>0.25 [3.30]</td><td>0.21 [2.54]</td></tr><tr><td>log (B/M)</td><td>0.35 [5.57]</td><td>0.32 [5.40]</td><td>0.30 [5.13]</td><td>0.33 [5.15]</td><td>0.34 [5.33]</td><td>0.31 [5.12]</td><td>0.34 [5.30]</td></tr><tr><td>log (ME)</td><td>-0.09 [-2.19]</td><td>-0.11 [-2.65]</td><td>-0.11 [-2.64]</td><td>-0.10 [-2.62]</td><td>-0.10 [-2.31]</td><td>-0.11 [-2.69]</td><td>-0.10 [-2.35]</td></tr><tr><td>11,0</td><td>-5.63 [-13.2]</td><td>-5.50 [-13.5]</td><td>-5.52 [-13.5]</td><td>-5.67 [-13.4]</td><td>-5.66 [-13.2]</td><td>-5.53 [-13.6]</td><td>-5.67 [-13.3]</td></tr><tr><td>112,2</td><td>0.76 [3.66]</td><td>0.78 [3.98]</td><td>0.78 [3.95]</td><td>0.75 [3.63]</td><td>0.75 [3.63]</td><td>0.77 [3.92]</td><td>0.74 [3.61]</td></tr></table></body></html>

# Multi-factor time-series regressions

Table 2.
Excess returns to portfolios sorted on profitability.

This table shows monthly value-weighted average excess returns to portfolios sorted on gross profits-to-assets (REVT - COGS) / AT), employing NYSE breakpoints, and results of time-series regressions of these portfolios' returns on the Fama-French factors. It also shows time-series average portfolio characteristics (porfolio gross profits-to-assets (GP/A), book-to-market (B/M), average firm size (ME, in $\$10^{6}$ 0, and number of firms (n)). Panel B provides similar results for portfolios sorted on book-to-market. The sample excludes financial firms (those with one-digit SIC codes of six), and covers July 1963 to December 2010.

<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="4">Panel A: portfolios sorted on grossprofits-to-assels FF 3 alphas and factor loadings</td><td colspan="4">portfolio characteristics</td></tr><tr><td></td><td>MKT</td><td></td><td>SMB</td><td>HML</td><td>GP/A B/M</td><td></td><td>ME</td></tr><tr><td>Low</td><td>0.31 [1.65]</td><td>-0.18 [-2.54]</td><td>0.94 [57.7]</td><td>0.04 [1.57]</td><td>0.15 [5.87]</td><td>0.10</td><td>1.10</td><td>748</td><td>771</td></tr><tr><td>2</td><td>0.41</td><td>-0.11</td><td>1.03</td><td>-0.07</td><td>0.20</td><td>0.20</td><td>0.98</td><td>1,100</td><td>598</td></tr><tr><td>3</td><td>[2.08] 0.52</td><td>[-1.65] 0.02</td><td>[67.5] 1.02</td><td>[-3.13] -0.00</td><td>[8.51] 0.12</td><td>0.30</td><td>1.00</td><td>1,114</td><td>670</td></tr><tr><td>4</td><td>[2.60] 0.41</td><td>[0.27] 0.05</td><td>[69.9] 1.01</td><td>[-0.21] 0.04</td><td>[5.42] -0.24</td><td>0.42</td><td>0.53</td><td>1,114</td><td>779</td></tr><tr><td>High</td><td>[1.94] 0.62 [3.12]</td><td>[0.83] 0.34 [5.01]</td><td>[70.6] 0.92 [58.31</td><td>[1.90] -0.04</td><td>[-11.2] -0.29 [-12.3]</td><td>0.68</td><td>0.33</td><td>1,096</td><td>938</td></tr><tr><td>H-L</td><td>0.31 [2.49]</td><td>0.52 [4.49]</td><td>-0.03 [-0.99]</td><td>[2.03] -0.08 [-2.15]</td><td>-0.44 [-10.8]</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="5">Panel B: portfolios sorted onbook-to-market FF 3 alphas and factor loadings</td><td colspan="4">portfolio characteristics</td></tr><tr><td>a</td><td>MKT</td><td>SMB</td><td>HML</td><td>GP/A</td><td>B/M</td><td>ME</td><td>n</td></tr><tr><td>Low</td><td>0.39 [1.88]</td><td>0.13 [2.90]</td><td>0.98 [90.1]</td><td>-0.09 [-5.62]</td><td>-0.39 [-23.9]</td><td>0.43</td><td>0.25</td><td>1.914</td><td>965</td></tr><tr><td>2</td><td>0.45 [2.33]</td><td>-0.02 [-0.29]</td><td>0.99 [78.1]</td><td>0.05 [2.61]</td><td>0.04 [2.23]</td><td>0.31</td><td>0.54</td><td>1,145</td><td>696</td></tr><tr><td>3</td><td>0.56 [2.99]</td><td>0.03 [0.53]</td><td>0.96 [63.5]</td><td>0.04 [2.09]</td><td>0.22 [9.71]</td><td>0.26</td><td>0.79</td><td>849</td><td>640</td></tr><tr><td>4</td><td>0.67 [3.58]</td><td>-0.00 [-0.03]</td><td>0.96 [74.8]</td><td>0.10 [5.66]</td><td>0.53 [27.1]</td><td>0.21</td><td>1.12</td><td>641</td><td>655</td></tr><tr><td>High</td><td>0.80 [3.88]</td><td>0.07 [1.04]</td><td>1.01 [60.7]</td><td>0.25 [10.7]</td><td>0.51 [20.5]</td><td>0.21</td><td>5.47</td><td>367</td><td>703</td></tr><tr><td>H-L</td><td>0.41 [2.95]</td><td>-0.06 [-0.71]</td><td>0.03 [1.44]</td><td>0.34 [12.0]</td><td>0.91 [30.0]</td><td></td><td></td><td></td><td></td></tr></table></body></html>
This table shows monthly value-weighted average excess returns to portfolios of stocks from developed markets outside North America (Australia, Austria, Belgium, Denmark, Finland, France, Germany, Great Britain, Hong Kong, Italy, Japan, the Netherlands, New Zealand, Norway, Singapore, Spain, Sweden, and Switzerland) sorted on gross profits-to-assets ((REVT - COGS) / AT) and book-to-market, and results of time-series regressions of these portfolios' returms on the Global Fama-French factors. It also shows time-series average portfolio characteristics (portfolio gross profits-to-assets (GP/A), book-to-market (B/M), average firm size (ME, in $\$10^{6}$ ), and number of firms (n). The sample excludes financial firms (those with one-digit SIC codes of six), and covers July 1990 to October 2009.

Table 5. Returns to portfolios sorted on GP/A and B/M, international evidence
<html><body><table><tr><td></td><td colspan="8"></td></tr><tr><td></td><td></td><td colspan="4">Global FF 3 factor loadings MKT</td><td colspan="4">portfolio characteristics B/M</td></tr><tr><td>Low</td><td>-0.16</td><td>-0.72</td><td>1.23</td><td>SMB 0.35</td><td>HML 0.21</td><td>GP/A 0.09</td><td>0.91</td><td>ME 936</td><td>n 1,211</td></tr><tr><td></td><td>[-0.37] 0.19</td><td>[-2.81] -0.29</td><td>[20.8] 1.10</td><td>[3.06] 0.26</td><td>[1.98] 0.19</td><td>0.20</td><td>0.79</td><td>1,530</td><td>1,211</td></tr><tr><td>3</td><td>[0.50] 0.29</td><td>[-1.65] -0.07</td><td>[27.2] 1.12</td><td>[3.26] 0.20</td><td>[2.65] -0.12</td><td>0.32</td><td>0.72</td><td>1,843</td><td>1,211</td></tr><tr><td>4</td><td>[0.76] 0.44</td><td>[-0.40] 0.17</td><td>[29.7] 0.94</td><td>[2.76] 0.06</td><td>[-1.76] -0.03</td><td>0.54</td><td>0.95</td><td>1,946</td><td>1,211</td></tr><tr><td>High</td><td>[1.44] 0.60</td><td>[1.30] 0.27</td><td>[31.7] 0.88</td><td>[1.05] 0.32</td><td>[-0.65] 0.11</td><td>1.02</td><td>1.46</td><td>940</td><td>1,211</td></tr><tr><td>H-L</td><td>[1.95] 0.76 [2.25]</td><td>[1.60] 0.99 [2.97]</td><td>[22.7] -0.35 [-4.61]</td><td>[4.21] -0.04</td><td>[1.58] -0.10</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td colspan="8">Panel B: portfolios sorted on book-to-market</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="4">Global FF 3 factor loadings</td><td colspan="4">portfolio characteristics</td></tr><tr><td>α</td><td>MKT</td><td>SMB</td><td>HML</td><td>GP/A</td><td>B/M</td><td>ME</td><td>n</td></tr><tr><td></td><td>0.09 [0.25]</td><td>-0.16 [-1.09]</td><td>1.05 [30.6]</td><td>0.07 [1.04]</td><td>-0.25 [-4.11]</td><td>0.32</td><td>0.19</td><td>2.180</td><td>1,211</td></tr><tr><td>2</td><td>0.29 [0.81]</td><td>-0.18 [-1.16]</td><td>1.07 [29.3]</td><td>0.23 [3.24]</td><td>0.18 [2.78]</td><td>0.29</td><td>0.46</td><td>2,041</td><td>1,211</td></tr><tr><td>3</td><td>0.29 [0.85]</td><td>-0.21 [-1.39]</td><td>1.06 [30.9]</td><td>0.17 [2.47]</td><td>0.29 [4.73]</td><td>0.27</td><td>0.71</td><td>1,465</td><td>1,211</td></tr><tr><td>4</td><td>0.44 [1.25]</td><td>-0.07 [-0.37]</td><td>1.05 [25.0]</td><td>0.28 [3.49]</td><td>0.33 [4.52]</td><td>0.31</td><td>1.08</td><td>941</td><td>1,211</td></tr><tr><td>High</td><td>0.61 [1.79]</td><td>0.15 [0.84]</td><td>1.01 [24.8]</td><td>0.38 [4.83]</td><td>0.28 [3.88]</td><td>0.40</td><td>8.13</td><td>564</td><td>1,211</td></tr><tr><td>H-L</td><td>0.51 [2.12]</td><td>0.31 [1.46]</td><td>-0.03 [-0.69]</td><td>0.31 [3.30]</td><td>0.53 [6.11]</td><td></td><td></td><td></td><td></td></tr></table></body></html>

This table shows the value-weighted average excess returns to portfolios double sorted, using NYSE breakpoints, on gross profits-to-assets and book-to-market, and results of time-series regressions of both sorts' high-minus-low portfolios' returns on the Fama-French factors. The table also shows the average number of firms, and the average size of firms, in each portfolio (the portfolios exhibit little gross-profits to asset variation within book-to-market quintiles, and little book-to-market variation within profitability quintiles). The sample excludes financial firms (those with one-digit SIC codes of six), and covers July 1963 to December 2010.

Table 6. Double sorts on gross profits-to-assets and book-to-market.
<html><body><table><tr><td rowspan="2"></td><td rowspan="2">gross profits-to-asset quintiles</td><td colspan="5"></td><td colspan="5">Panel A: portfolio average retums and time-series regression results profitability strategies</td></tr><tr><td>L</td><td>2</td><td>3</td><td>4</td><td>H</td><td>1 e</td><td>α</td><td>β mkt</td><td>B smb</td><td>Pkm!</td></tr><tr><td rowspan="4">quintiles book-to-market</td><td>L</td><td>-0.08</td><td>0.19</td><td>0.27</td><td>0.26</td><td>0.56</td><td>0.64 [3.52]</td><td>0.83 [4.76][-6.03][-4.81]</td><td>-0.24</td><td>-0.27</td><td>-0.01 [-0.18]</td></tr><tr><td>2</td><td>0.19</td><td>0.30</td><td>0.40</td><td>0.70</td><td>0.90</td><td>0.70</td><td>0.69</td><td>-0.12</td><td>0.26</td><td>0.01 [0.09]</td></tr><tr><td>3</td><td>0.38</td><td>0.39</td><td>0.74</td><td>0.69</td><td>0.87</td><td>[4.13] 0.49</td><td>0.27</td><td>[4.00][-3.05] 0.09</td><td>[4.61] 0.53</td><td>0.10</td></tr><tr><td>4</td><td>0.50</td><td>0.60</td><td>0.94</td><td>1.04</td><td>0.93</td><td>[2.80] 0.43</td><td>[1.64] 0.28</td><td>[2.30] 0.07</td><td>[9.89] 0.65</td><td>[1.77] -0.14</td></tr><tr><td></td><td>H</td><td>0.65 0.83</td><td></td><td>0.96</td><td>1.09</td><td>1.08</td><td>[2.47] [2.06]  [-0.94] 0.44 [2.38][1.79][1.83]</td><td>0.34</td><td>-0.04</td><td>[9.40] 0.51 [12.6]</td><td>[-1.27] -0.08 1[-2.52]</td></tr><tr><td rowspan="5">strategies book-to-market:</td><td>pe</td><td>0.73 [3.52]</td><td>0.64 [3.42]</td><td>0.69 [3.76]</td><td>0.83 [4.74]</td><td>0.52 [2.81]</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>a</td><td>0.45 [2.76]</td><td>0.27 [1.65]</td><td>0.39 [2.26]</td><td>0.38 [2.80]</td><td>-0.03 [-0.20]</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>-0.18 [-4.77]</td><td>-0.06 [-1.44]</td><td>-0.03 [-0.86]</td><td>-0.06</td><td>0.02</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>smb</td><td>-0.04</td><td>0.27</td><td>0.32</td><td>[-1.95] 0.74</td><td>[0.72] 0.75</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>[-0.75] 0.91</td><td>[5.00] 0.81</td><td>[5.57] 0.58</td><td>[16.6] 0.69</td><td>[16.2] 0.85</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>[15.7]</td><td>[14.1]</td><td>[9.52]</td><td>[14.2]</td><td>[17.0]</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td colspan="8">Panel B: portfolio average number of firms (left) and average firm size (right, $106) grossprofits-to-assetquintiles</td><td></td></tr><tr><td></td><td>L</td><td></td><td></td><td></td><td></td><td></td><td></td><td>gross profits-to-asset quintiles</td><td></td><td></td><td>H</td></tr><tr><td></td><td></td><td></td><td>2</td><td>3</td><td>4</td><td>H</td><td>L</td><td>2</td><td>3</td><td>4</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>number of firms</td><td></td><td></td><td></td><td></td><td>average firm size</td><td></td><td></td></tr><tr><td rowspan="5">quintiles B/M</td><td>L</td><td>195</td><td>101</td><td>128</td><td>194</td><td>343</td><td>653</td><td>1,461</td><td>1,891</td><td>2.694</td><td>2,493</td></tr><tr><td>2</td><td>104</td><td>95</td><td>130</td><td>170</td><td>192</td><td>1,002</td><td>1,729</td><td>1,590</td><td>1,238</td><td>669</td></tr><tr><td>3</td><td>113</td><td>104</td><td>128</td><td>145</td><td>142</td><td>1,003</td><td>1,402</td><td>1,266</td><td>534</td><td>277</td></tr><tr><td>4</td><td>144</td><td>129</td><td>128</td><td>128</td><td>118</td><td>955</td><td>1,118</td><td>630</td><td>268</td><td>187</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>108</td><td>568</td><td>424</td><td>443</td><td>213</td><td></td></tr><tr><td>H</td><td>174</td><td>151</td><td>135</td><td>120</td><td></td><td></td><td></td><td></td><td></td><td>102</td></tr></table></body></html>

This table shows the performance of portfolios formed using only the 500 largest non-financial firms for which gross profits-to-assets (GP/A) and book-to-market (B/M) are both available. Portfolios are tertile sorted on GP/A (Panel A), B/M (Panel B), and the sum of the firms' GP/A and B/M ranks within the sample (Panel C). It also shows time-series average porfolio characteristics (portfolio GP/A, portfolio B/M, average firm size (ME, in $\$10^{9}$ , and number of firms $(\boldsymbol{\mathrm{n}}))$ . The sample covers July 1963 to December 2010.

Table 7. Performance of large stock profitability and value strategies.
<html><body><table><tr><td></td><td></td><td colspan="5">FF 3 alphas and factor loadings</td><td colspan="3">portfolio characteristics</td></tr><tr><td></td><td></td><td>α</td><td>MKT</td><td>SMB</td><td>HML</td><td>GP/A</td><td>B/M</td><td>ME</td><td>n</td></tr><tr><td>Low</td><td>0.38 [1.88]</td><td>-0.15 [-1.96]</td><td>1.02 [55.1]</td><td>-0.04 [-1.38]</td><td>0.22 [7.89]</td><td>0.12</td><td>1.02</td><td>5.93</td><td>150</td></tr><tr><td>2</td><td>0.57 [2.51]</td><td>0.00 [0.06]</td><td>1.13 [74.4]</td><td>0.11 [5.08]</td><td>0.08 [3.36]</td><td>0.31</td><td>0.86</td><td>7.82</td><td>200</td></tr><tr><td>High</td><td>0.65 [3.03]</td><td>0.25 [3.84]</td><td>1.02 [68.5]</td><td>0.08 [3.69]</td><td>-0.18 [-7.81]</td><td>0.64</td><td>0.41</td><td>9.20</td><td>150</td></tr><tr><td>H-L</td><td>0.27 [2.33]</td><td>0.40 [3.75]</td><td>0.00 [0.17]</td><td>0.11 [3.23]</td><td>-0.40 [-10.5]</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="10">Panel B: portfolios sorted on book-to-market</td></tr><tr><td>Low</td><td>0.38</td><td>α 0.07</td><td>MKT 1.10</td><td>SMB 0.04</td><td>HML -0.48</td><td>GP/A 0.51</td><td>0.25</td><td>ME 1.03</td><td>n 150</td></tr><tr><td>2</td><td>[1.56] 0.52</td><td>[1.08] -0.00</td><td>[69.5] 1.07</td><td>[1.86] 0.07</td><td>[-20.2] 0.08</td><td>0.34</td><td>0.58</td><td>7.27</td><td>200</td></tr><tr><td>High</td><td>[2.49] 0.70</td><td>[-0.02] 0.02</td><td>[79.7] 1.02</td><td>[3.56] 0.06</td><td>[3.91] 0.52</td><td>0.21</td><td>1.55</td><td>5.33</td><td>150</td></tr><tr><td>H-L</td><td>[3.60] 0.32</td><td>[0.40] -0.05</td><td>[73.3] -0.08</td><td>[2.85] 0.01</td><td>[24.9] 1.01</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="10">[2.16] [-0.64] [-4.41] [0.56] Panel C: portfolios sorted on average gross profits-to-assets and book-to-market ranks</td></tr><tr><td>Low</td><td>0.19 [0.79]</td><td>-0.20 [-2.25]</td><td>1.12 [53.2]</td><td>0.01 [0.25]</td><td>-0.27 [-8.51]</td><td>0.22</td><td>0.45</td><td>7.72</td><td>150</td></tr><tr><td>2</td><td>0.59 [3.00]</td><td>0.10</td><td>1.01</td><td>0.02</td><td>0.09</td><td>0.38</td><td>0.68</td><td>8.83</td><td>200</td></tr><tr><td>high</td><td>0.81</td><td>[1.95] 0.17</td><td>[87.3] 1.08</td><td>[1.32] 0.15</td><td>[5.05] 0.29</td><td>0.45</td><td>1.21</td><td>5.87</td><td>150</td></tr><tr><td>H-L</td><td>[3.81] 0.62</td><td>[2.80] 0.37</td><td>[77.0] -0.04</td><td>[7.62] 0.14</td><td>[13.8] 0.56</td><td></td><td></td><td></td><td></td></tr></table></body></html>

Table A.2. Fama-MacBeth regressions employing EBITDA and XSGA.
<html><body><table><tr><td></td><td colspan="6">slopecoefficients (xl 0²) and[test-statistics]from regressions of the formrj = β'x, j + ∈tj</td></tr><tr><td>independent variables</td><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6)</td></tr><tr><td>grossprofitability</td><td>0.75 [5.49]</td><td></td><td></td><td>0.53 [3.76]</td><td>1.47 [4.51]</td><td></td></tr><tr><td>EBITDA-to-assets</td><td></td><td>1.42 [4.28]</td><td></td><td>1.07 [3.03]</td><td></td><td>1.65 [4.73]</td></tr><tr><td>XSGA-to-assets</td><td></td><td></td><td>0.65 [4.07]</td><td></td><td>-0.69 [-2.05]</td><td>0.73 [4.70]</td></tr><tr><td>log (B/M)</td><td>0.35 [5.98]</td><td>0.33 [5.70]</td><td>0.38 [6.94]</td><td>0.37 [6.38]</td><td>0.38 [6.49]</td><td>0.38 [6.46]</td></tr><tr><td>log (ME)</td><td>-0.09 [-2.29]</td><td>-0.13 [-3.44]</td><td>-0.07 [-1.69]</td><td>-0.11 [-2.99]</td><td>-0.10 [-2.65]</td><td>-0.10 [-2.78]</td></tr><tr><td>112,2</td><td>0.76 [3.87]</td><td>0.76</td><td>0.77</td><td>0.72</td><td>0.71</td><td>0.72</td></tr><tr><td>11.0</td><td>-5.57 [-13.8]</td><td>[3.89] -5.57 [-14.1]</td><td>[3.96] -5.67 [-14.0]</td><td>[3.74] -5.71 [-14.4]</td><td>[3.71] -5.83 [-14.0]</td><td>[3.78] -5.85 [-14.8]</td></tr></table></body></html>

This table reports results from Fama-MacBeth regressions of firms' returns on gross profits (revenues minus cost of goods sold, Compustat REVT - COGS), earnings before interest, taxes, depreciation, and amortization (EBITDA), and selling, general, and administrative expenses (XSGA), each scaled by assets (AT). Regressions include controls for book-to-market $(\log (\mathbf{B}/\mathbf{M}))$ ,size $(\mathrm{log}(\mathrm{ME}))$ , and past performance measured at horizons of one month $\left (r_{1,0}\right)$ and twelve to two months $(r_{12,2}).$ Independent variables are trimmed at the one and 99% levels. The sample excludes financial firms (those with one-digit SIC codes of six), and covers July 1963 to December 2010.
Table A.3. Fama-MacBeth regre ssions with asset turnover and gross margins. This table reports results from Fama-MacBeth regressions of firms' returns on profitability (gross profits-to-assets, measured as revenues minus cost of goods sold (REVT - COGS) scaled by assets (AT)), asset turnover (REVT / AT), and gross margins (GP / REVT). Regressions include controls for book-to-market (log (B/M)), size (log (ME)), and past performance measured at horizons of one month (r 1, o) and twelve to two months (r 12,2). Independent variables are trimmed at the one and $99\%$ levels. The sample covers July 1963 to December 2010, and excludes financial firms (those with one-digit SIC codes of six).
<html><body><table><tr><td></td><td colspan="7">slopecoefficients (xlo 2) and[test-statistics] from regressions of the formrj =β'x, j + ∈j</td></tr><tr><td>independent variables</td><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6)</td><td>(7)</td></tr><tr><td>profits-to-assets</td><td>0.75 [5.49]</td><td></td><td></td><td>0.83 [6.92]</td><td>0.81 [5.70]</td><td></td><td>0.82 [5.08]</td></tr><tr><td>assettumover</td><td></td><td>0.13 [2.59]</td><td></td><td>-0.04 [-0.87]</td><td></td><td>0.16 [3.27]</td><td>-0.01 [-0.28]</td></tr><tr><td>grossmargins</td><td></td><td></td><td>0.28 [2.67]</td><td></td><td>0.12 [0.97]</td><td>0.37 [3.31]</td><td>0.15 [0.83]</td></tr><tr><td>log (B/M)</td><td>0.35 [5.98]</td><td>0.31 [5.32]</td><td>0.33 [5.73]</td><td>0.36 [6.09]</td><td>0.37 [6.30]</td><td>0.33 [5.70]</td><td>0.37 [6.35]</td></tr><tr><td>log (ME)</td><td>-0.09 [-2.29]</td><td>-0.10 [-2.44]</td><td>-0.11 [-2.66]</td><td>-0.10 [-2.35]</td><td>-0.09 [-2.29]</td><td>-0.10 [-2.39]</td><td>-0.09 [-2.26]</td></tr><tr><td>112,2</td><td>-5.57 [-13.8]</td><td>-5.56 [-13.8]</td><td>-5.44 [-13.4]</td><td>-5.62 [-14.0]</td><td>-5.59 [-13.8]</td><td>-5.59 [-13.9]</td><td>-5.65 [-14.0]</td></tr><tr><td>71.0</td><td>0.76 [3.87]</td><td>0.77 [3.94]</td><td>0.83 [4.21]</td><td>0.75 [3.85]</td><td>0.76 [3.85]</td><td>0.78 [3.98]</td><td>0.75 [3.84]</td></tr></table></body></html>
# Summary of key findings

· Gross profitability seems to work after controlling for a measure of value, B/M ratios.
· It also seems to work internationally.
· The results are weaker for large firms; again controlling for the value effect makes the results stronger.
● High Gross Profits/Total Assets firms are more expensive, growth firms (negative HML) and larger in size (negative SMB).

# Questions

Will this finding survive a more comprehensive measure of value that took into account other measures of value?

Is it simply a proxy for other measures of value?

This key issue is not addressed in the paper.

The paper reports monthly  returns with monthly portfolio formation. Does this require high portfolio turnover? What about longer holding periods? For instance, annual returns? Are the results still strong?

# Quality Minus Junk (Asness, Frazzini, and Pedersen, 2013)

Quality is defined as firms that are “safe, profitable, growing, and well managed.'

Thus quality implies high growth, high return on investments, low risk, and returning capital to investors. They define:

# Profitability

GPOA: gross profits/total assets
ROE: return on equity
ROA: return on assets
CFOA: cash flow from operations/total assets
GMAR: gross margin
ACC: Fraction of earnings due to cash flows

Each month, each variable is cross-sectionally ranked and converted to a Z-score.

With 1000 stocks in a month, rank the stocks from 1 to 1000 by gross profits/total assets or any of the other measures, where 1 is the lowest profitability and 1000 is the highest profitability. The Z-score for a stock is based on its rank:

$$
\mathsf{Z-s c o r e}=(\mathrm{Rank-AvgRank})/\mathrm{StDevRank}
$$

The average of all the individual Z-scores is the profitability score.

# Growth

5-year growth in GPOA
5-year growth in ROE
5-year growth in ROA
5-year growth in CFOA
5-year growth in GMAR
5-year growth in ACC

# Safety

BAB: Low beta
IVOL: Low idiosyncratic volatility
LEV: Low leverage
Ohlson's O-Score: Low bankruptcy risk
Altman's Z-Score: Low bankruptcy risk
EVOL: Low ROE volatility

Low betas, volatility_and leverage get high ranks and high Oscores and Altman's Z-score get high ranks.

# Payout

EISS: Negative of growth in shares (a decline is positive) DISS: Negative of net debt issuance (a decline is positive) NPOP:  Total net payout/earnings (payout ratio)

Compute Z-scores for each category in the same manner as for profitability.

# Quality Score

Quality is the average of the Z-scores of profitability, growth.
Safety, and payout.

$$
Q u a l i t y=z (P r o f i t a b i l i y+G r o w t h+S a f e t y+P a y
$$

T

# Ten Quality Portfolios

Form 10 quality portfolios every month based on the latest quality score by sorting all available firms by quality. Portfolio 10 is high quality and portfolio 1 is low quality.

# Quality Minus Junk (QMJ) Factor

Construct two size portfolios based on the median NYSE market cap. Stocks with market cap $>$ median form the Big portfolio. Stocks with market cap $<$ median form the Small portfolio.

Within each size portfolio form three quality portfolios for an intersection of six portfolios. All portfolios are value-weighted.

 ![500](b2de75c1c38dce029240389b8a91a5c87bbf4d51a9290c726dce1fcd6ca2f74c.jpg)
# Global sample of firms

# Table I Summary Statistics

This table shows summary statistics as of June of each year. The sample includes all U.S. common stocks (CRSP “shrcd" equal to 10 or 11) and all global stocks ("tcpi”" equal to 0) in the merged CRSP/Xpressfeed global databases.

<html><body><table><tr><td>Country</td><td>Total number of Average number stocks</td><td>of stocks</td><td>Firm size (Billion-USD)</td><td>Weight in global portfolio</td><td></td><td>End Year</td></tr><tr><td>Australia</td><td>2,142</td><td>660</td><td>0.63</td><td>0.018</td><td>1986</td><td>2012</td></tr><tr><td>Austria</td><td>126</td><td>56</td><td>0.70</td><td>0.002</td><td>1990</td><td>2012</td></tr><tr><td>Belgium</td><td>231</td><td>91</td><td>2.37</td><td>0.009</td><td>1990</td><td>2012</td></tr><tr><td>Canada</td><td>1,901</td><td>541</td><td>1.08</td><td>0.022</td><td>1982</td><td>2012</td></tr><tr><td>Switzerland</td><td>343</td><td>135</td><td>4.06</td><td>0.023</td><td>1986</td><td>2012</td></tr><tr><td>Germany</td><td>1,492</td><td>596</td><td>3.01</td><td>0.061</td><td>1989</td><td>2012</td></tr><tr><td>Denmark</td><td>227</td><td>85</td><td>1.08</td><td>0.004</td><td>1986</td><td>2012</td></tr><tr><td>Spain</td><td>212</td><td>82</td><td>4.48</td><td>0.014</td><td>1986</td><td>2012</td></tr><tr><td>Finland</td><td>202</td><td>83</td><td>1.66</td><td>0.005</td><td>1986</td><td>2012</td></tr><tr><td>France</td><td>1,088</td><td>397</td><td>2.85</td><td>0.044</td><td>1986</td><td>2012</td></tr><tr><td>United Kingdom</td><td>3,312</td><td>1.103</td><td>1.83</td><td>0.095</td><td>1986</td><td>2012</td></tr><tr><td>Greece</td><td>239</td><td>132</td><td>0.48</td><td>0.002</td><td>1995</td><td>2012</td></tr><tr><td>Hong Kong</td><td>1,351</td><td>516</td><td>1.21</td><td>0.026</td><td>1989</td><td>2012</td></tr><tr><td>Ireland</td><td>106</td><td>38</td><td>1.58</td><td>0.002</td><td>1987</td><td>2012</td></tr><tr><td>Israel</td><td>284</td><td>97</td><td>0.64</td><td>0.003</td><td>1995</td><td>2012</td></tr><tr><td>Italy</td><td>356</td><td>129</td><td>2.37</td><td>0.018</td><td>1986</td><td>2012</td></tr><tr><td>Jap an</td><td>3,856</td><td>1.988</td><td>1.29</td><td>0.202</td><td>1986</td><td>2012</td></tr><tr><td>Netherlands</td><td>250</td><td>109</td><td>4.70</td><td>0.021</td><td>1986</td><td>2012</td></tr><tr><td>Norway</td><td>429</td><td>120</td><td>0.96</td><td>0.004</td><td>1986</td><td>2012</td></tr><tr><td>New Zealand</td><td>176</td><td>69</td><td>1.26</td><td>0.003</td><td>1990</td><td>2012</td></tr><tr><td>Portugal</td><td>92</td><td>38</td><td>1.96</td><td>0.002</td><td>1990</td><td>2012</td></tr><tr><td>Singapore</td><td>860</td><td>353</td><td>0.60</td><td>0.009</td><td>1990</td><td>2012</td></tr><tr><td>Sweden</td><td>677</td><td>203</td><td>1.35</td><td>0.012</td><td>1986</td><td>2012</td></tr><tr><td>United States</td><td>19,356</td><td>3,594</td><td>1.31</td><td>0.399</td><td>1951</td><td>2012</td></tr></table></body></html>

A large sample of firms across many countries.

Does quality command a premium? Regress M/B ratios on Quality Score. High quality firms should be expensive!
# Table III Results: Cross Sectional Regressions, the Price of Quality

This table reports coefficients from Fama-Macbeth regressions. The dependent variable is the z-score of a stock's market to book ratio (MB) in month t. The explanatory variables are the quality scores in month t and a series of controls. Size is the z-score of the stock's market equity (ME). Ret (t) is the stock returm in month t. $\mathbb{R}e t (t-12, t)$ is the stock return in the prior year. All variables are rescaled to have a zero mean and a standard deviation of one. When indicated (\*"Industry FE", "Country FE") variables are standardized by industry-country pairs. Average R 2 is the time series averages of the adjusted R-square of the cross sectional regression. Standard errors are adjusted for heteroskedasticity and autocorrelation (Newey and West (1987)) with a lag length of 12 months. T-statistics are shown below the coefficient estimates and $5\%$ statistical significance is indicated in bold.

Panel A: The Price ofQuality
<html><body><table><tr><td rowspan="2"></td><td colspan="4">Long Sample (U.S.,1956 -2012)</td><td colspan="4">Broad Sample (Global, 1986- 2012)</td></tr><tr><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(0)</td><td>(2)</td><td>(8)</td></tr><tr><td>Quality</td><td>0.32 (22.47)</td><td>0.19 (15.94)</td><td>0.32 (23.92)</td><td>0.20 (B.94)</td><td>0.24 (23.33)</td><td>0.10 (17.20)</td><td>0.22 (2439)</td><td>0.09 (15.54)</td></tr><tr><td>Size</td><td></td><td>0.31 (19.19)</td><td></td><td>0.30 (27.08)</td><td></td><td>0.29 (17.71)</td><td></td><td>0.31 (20.91)</td></tr><tr><td>Ret (t-12, t)</td><td></td><td>0.27 (2136)</td><td></td><td>0.28</td><td></td><td>0.27</td><td></td><td>0.28</td></tr><tr><td></td><td></td><td></td><td></td><td>(26.50)</td><td></td><td>(18.60)</td><td></td><td>(22.54)</td></tr><tr><td>Industry FE</td><td>No</td><td>No</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td><td>Yes</td></tr><tr><td>Country FE</td><td></td><td></td><td></td><td></td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Average R 2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.12</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>0.31</td><td>0.11</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>0.25</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>0.30</td><td>0.06</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.05</td><td>0.26</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr></table></body></html>

Panel B: The Price ofEach Quality Component
<html><body><table><tr><td rowspan="2"></td><td colspan="5">Long Sample (U.S.,1956 -2012)</td><td colspan="5">BroadSample (G 1 obal, 1986-2012)</td></tr><tr><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6)</td><td>(2)</td><td>(8)</td><td>(9)</td><td>(10)</td></tr><tr><td>Profitability</td><td>0.41 (26.19)</td><td></td><td></td><td></td><td>0.30 (23.64)</td><td>0.29 (33.76)</td><td></td><td></td><td></td><td>0.19 (3137)</td></tr><tr><td>Growth</td><td></td><td>0.38 (3118)</td><td></td><td></td><td>0.11 (12.25)</td><td></td><td>0.28 (35.02)</td><td></td><td></td><td>0.08 (2.67)</td></tr><tr><td>Safety</td><td></td><td></td><td>0.14 (9.95)</td><td></td><td>-0.08</td><td></td><td></td><td>0.11 (8.19)</td><td></td><td>-0.10 -(2.59)</td></tr><tr><td>Payout</td><td></td><td></td><td></td><td>-0.10</td><td>-(1138) -0.13</td><td></td><td></td><td></td><td>-0.06 -(4.69)</td><td>-0.10 -(1123)</td></tr><tr><td>Size</td><td></td><td></td><td></td><td></td><td>(+81)- 0.28 (2622)</td><td></td><td></td><td></td><td></td><td>0.31 (2167)</td></tr><tr><td>Ret (t-12, t)</td><td></td><td></td><td></td><td></td><td>0.28 (28.69)</td><td></td><td></td><td></td><td></td><td>0.28 (23.33)</td></tr><tr><td>Industry FE</td><td>No</td><td>No</td><td>No</td><td>No</td><td>Yes</td><td>No</td><td>No</td><td>No</td><td>No</td><td>s</td></tr><tr><td>Country FE</td><td></td><td></td><td></td><td></td><td></td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>Average R 2</td><td>0.18</td><td>0.15</td><td>0.03</td><td>0.01</td><td>0.40</td><td>0.09</td><td>0.08</td><td>0.02</td><td>0.01</td><td>0.31</td></tr></table></body></html>

# Table IV Quality-Sorted Portfolios

This table shows calendar-time portfolio retums. Each calendar month, stocks in each country in are ranked in ascending order on the basis of their quality score. The ranked stocks are assigned to one of ten portfolios. U.S. sorts are based on NYSE breakpoints. Portfolios are value-weighted, refreshed every calendar month, and rebalanced every calendar month to maintain value weights. We form one set of portfolios in each country and compute global portfolios by weighting each country's portfolio by the country's total (lagged) market capitalization. The rightmost column reports returns of a self-financing portfolio that is long the high quality portfolio and shorts the low quality portfolio. This table includes all available common stocks on the CRSP/Xpressfeed merged database for the markets listed in Table I Alpha is the intercept in a time-series regression of monthly excess return. The explanatory variables are the monthly returns from the market portfolio (MKT) and size (SMB), book-to-market (HML), and momentum (UMD) factor-mimicking portfolios. Panel A reports results from our Long Sample of domestic stocks. The sample period runs from June 1956 to December 2012. Panel B reports results from our Broad Sample of global stocks. The sample period runs from June 1986 to December 2012. Returns are in USD, do not include currency hedging, and excess returms are above the U.S. Treasury bill rate. Returns and alphas are in monthly percent, t-statistics are shown below the coefficient estimates, and $5\%$ statistical significance is indicated in bold. Beta is the realized loading on the market portfolio. Information ratio is equal to 4-factor alpha (intercept) divided by the standard deviation of the estimated residuals in the timeseries regression. Sharpe ratios and information ratios are annualized.

<html><body><table><tr><td>PanelA: LongSample U.S.,1956-2012</td><td>P 1 (Low)</td><td>P 2</td><td>P 3</td><td>P 4</td><td>P 5</td><td>P 6</td><td>P 7</td><td>P 8</td><td>P 9</td><td>P 10 (High)</td><td>H-L</td></tr><tr><td>Eressretum</td><td>0.15 (0.55)</td><td>0.36 (156)</td><td>0.38 (061)</td><td>0.39 (2.04)</td><td>0.45 (2.51)</td><td>0.45 (2.60)</td><td>0.57 (3.42)</td><td>0.47 (2.75)</td><td>0.58 (3.48)</td><td>0.61 (3.68)</td><td>0.47 (2.80)</td></tr><tr><td>CAPM alpha</td><td>-0.53 (-4.62)</td><td>-0.24 (-2.85)</td><td>-0.15 (-2.25)</td><td>-0.12 (2.01</td><td>-0.02 (-0.33)</td><td>-0.01 (-0.18)</td><td>0.13 (2.41)</td><td>0.01 (0.23)</td><td>0.14 (2.71)</td><td>0.18 (2.86)</td><td>0.71 (4.92)</td></tr><tr><td>3-factoralpha</td><td>-0.67 (-7.83)</td><td>-0.38 (-5.47)</td><td>-0.25 (-4.47)</td><td>-0.21 (-4.11)</td><td>-0.08 (-144)</td><td>-0.06 (-109)</td><td>0.12 (2.26)</td><td>0.01 (0.12)</td><td>0.16 (3.37)</td><td>0.29 (5.24)</td><td>0.97 (9.02)</td></tr><tr><td>4 factoralpha</td><td>-0.56 (-6.24)</td><td>-0.42 (-5.73)</td><td>-0.26 (-4.26)</td><td>-0.29 (-5.39)</td><td>-0.14 (-2.37)</td><td>-0.12 (-2.22)</td><td>0.04 (0.68)</td><td>-0.05 (-108)</td><td>0.19 (3.62)</td><td>0.41 (orL)</td><td>0.97 (8.55)</td></tr><tr><td>Beta</td><td>1.28</td><td>1.22</td><td>1.08</td><td>1.09</td><td>1.03</td><td>1.01</td><td>0.97</td><td>1.00</td><td>0.95</td><td>0.90</td><td>-0.38</td></tr><tr><td>Sharpe Ratio</td><td>0.07</td><td>0.21</td><td>0.25</td><td>0.27</td><td>0.33</td><td>0.35</td><td>0.46</td><td>0.37</td><td>0.46</td><td>0.49</td><td>0.37</td></tr><tr><td>InfomationRatio</td><td>-0.90</td><td>-0.82</td><td>-0.61</td><td>-0.77</td><td>-0.34</td><td>-0.32</td><td>0.10</td><td>-0.15</td><td>0.52</td><td>1.02</td><td>1.23</td></tr><tr><td>Adjusted R 2</td><td>0.90</td><td>0.91</td><td>0.92</td><td>0.93</td><td>0.90</td><td>0.91</td><td>0.91</td><td>0.93</td><td>0.92</td><td>0.90</td><td>0.60</td></tr></table></body></html>

<html><body><table><tr><td>PanelB: BroadSample Global. 1986-2012</td><td>P 1 (Low)</td><td>P 2</td><td>P 3</td><td>P 4</td><td>P 5</td><td>P 6</td><td>P 7</td><td>P 8</td><td>P 9</td><td>P 10 (High)</td><td>H-L</td></tr><tr><td>Eressretum</td><td>-0.03 (s 0'0-)</td><td>0.35 (101)</td><td>0.43 (142)</td><td>0.38 (L 25)</td><td>0.52 (185)</td><td>0.46 (174)</td><td>0.57 (2.29)</td><td>0.52 (2.08)</td><td>0.61 (2.54)</td><td>0.65 (2.78)</td><td>0.68 (3.22)</td></tr><tr><td>CAPM alpha</td><td>-0.61 (-3.20)</td><td>-0.20 (-119)</td><td>-0.06 (-0.42)</td><td>-0.12 (-0.90)</td><td>0.07 (0.53)</td><td>0.03 (0.25)</td><td>0.17 (152)</td><td>0.11 (105)</td><td>0.22 (2.05)</td><td>0.28 (2.44)</td><td>0.89 (5.00)</td></tr><tr><td>3-factoralpha</td><td>-0.73 (-4.14)</td><td>-0.33 (-2.08)</td><td>-0.18 (-133)</td><td>-0.24 (-198)</td><td>-0.02 (-0.17)</td><td>-0.04 (-0.35)</td><td>0.10 (0.92)</td><td>0.11 (0.98)</td><td>0.24 (2.17)</td><td>0.39 (3.49)</td><td>1.12 (7.68)</td></tr><tr><td>4 factoralpha</td><td>-0.46 (2.49)</td><td>-0.24 (-144)</td><td>-0.09 (-0.63)</td><td>-0.23 (-175)</td><td>0.01 (0.06)</td><td>-0.04 (-0.36)</td><td>0.10 (0.91)</td><td>0.11 (0.95)</td><td>0.23 (197)</td><td>0.47 (3.96)</td><td>0.93 (6.06)</td></tr><tr><td>Beta</td><td>1.14</td><td>1.12</td><td>1.00</td><td>1.03</td><td>0.94</td><td>0.91</td><td>0.85</td><td>0.87</td><td>0.82</td><td>0.78</td><td>-0.36</td></tr><tr><td>Sharpe Ratio</td><td>-0.01</td><td>0.20</td><td>0.27</td><td>0.24</td><td>0.36</td><td>0.33</td><td>0.44</td><td>0.40</td><td>0.49</td><td>0.53</td><td>0.62</td></tr><tr><td>InfomationRatio</td><td>-0.53</td><td>-0.30</td><td>-0.13</td><td>-0.37</td><td>0.01</td><td>-0.08</td><td>0.19</td><td>0.20</td><td>0.41</td><td>0.84</td><td>1.28</td></tr><tr><td>AdjustedR 2</td><td>0.79</td><td>0.80</td><td>0.81</td><td>0.84</td><td>0.81</td><td>0.82</td><td>0.82</td><td>0.82</td><td>0.80</td><td>0.79</td><td>0.56</td></tr></table></body></html>

# How do the various components of quality perform?

Table VI Quality Minus Junk: Returns

This table shows calendar-time portfolio returms and factor loadings. Quality minus Junk (QMD) factors are constructed as the intersection of six value-weighted portfolios formed on size and quality. At the end of each calendar month, stocks are assigned to two size-sorted portfolios based on their market capitalization. For U.S. securities, the size breakpoint is the median NYSE market equity. For International securities the size breakpoint is the Soth percentile by country. We use conditional sorts, first sorting on size, then on quality. Portfolios are value-weighted, refreshed every calendar month, and rebalanced every calendar month to maintain value weights. The QMJ factor retum is the average return on the two high quality porfolios minus the average returm on the two low quality (junk) portfolios. Portfolios based on profitability, growth, safety and payout score are constructed in a similar manner. We form one set of portfolios in each country and compute global portfolios by weighting each country's portfolio by the country's total (lagged) market capitalization. This table includes all available common stocks on the CRSP/Xpressfed merged database for the markets listed in Table I. Alpha is the intercept in a time-series regression of monthly excess retum. The explanatory variables are the monthly retums from the market portfolio (MKT) and size (SMB). Book-to-market (HML), and momentum (UMD) factor-mimicking portfolios. Panel A reports results from our Long Sample of domestic stocks. The sample period runs from June 1956 to December 2012. Panel B reports results from our Broad Sample of global stocks. The sample period runs from June 1986 to December 2012. Retums are in USD, do not include curency hedging, and excess returms are above the U.S. Treasury bill rate. Retums and alphas are in monthly percent, t-statistics are shown below the coefficient estimates, and $5\%$ statistical significance is indicated in bold. Information ratio is equal to 4-factor alpha (intercept) divided by the standard deviation of the estimated residuals in the time-series regression. Sharpe ratios and information ratios (i.e., the Sharpe ratio of the regression residual) are annualized.

<html><body><table><tr><td rowspan="3"></td><td colspan="5">Panel A: Long Sample (ULS., 1956 - 2012)</td><td colspan="5">Panel B: Broad Sample (Global, 1986 - 2012)</td></tr><tr><td>QMJProfitability</td><td></td><td>Safety</td><td>Growth</td><td>Payout</td><td colspan="2">QMJProfitability</td><td>Safety</td><td>Growth</td><td>Payout</td></tr><tr><td>Evress Retums</td><td>0.40</td><td>0.27</td><td>0.23 (2.06)</td><td>0.12</td><td>0.31</td><td>0.38 (3.22)</td><td>0.34</td><td>0.19</td><td>0.02</td><td>0.38</td></tr><tr><td rowspan="2">CAPM-alpha</td><td>(4.38)</td><td>(3.81)</td><td></td><td>(163)</td><td>(3.37)</td><td></td><td>(3.30)</td><td>(133)</td><td>(0.24)</td><td>(3.4)</td></tr><tr><td>0.55</td><td>0.33</td><td>0.42</td><td>0.08</td><td>0.46</td><td>0.52</td><td>0.43</td><td>0.34</td><td>0.02</td><td>0.49</td></tr><tr><td rowspan="2">3-factoralpha</td><td>(727)</td><td>(4.78)</td><td>(4.76)</td><td>(90 T)</td><td>(6.2)</td><td>(5.73)</td><td>(4.61)</td><td>(3.07)</td><td>(0.1 S)</td><td>(5.29)</td></tr><tr><td>0.68</td><td>0.45</td><td>0.59</td><td>0.20</td><td>0.43</td><td>0.61</td><td>0.53</td><td>0.50</td><td>0.14</td><td>++'0</td></tr><tr><td rowspan="2">4-factor alpha</td><td>(o 1 T)</td><td>(7.82)</td><td>(8.68)</td><td>(3.32)</td><td>(6.86)</td><td>(99'D)</td><td>(6.1)</td><td>(5.40)</td><td>(192)</td><td>(5.1)</td></tr><tr><td>0.66</td><td>0.53</td><td>0.57</td><td>0.38</td><td>0.21</td><td>0.45</td><td>0.49</td><td>0.39</td><td>0.29</td><td>0.19</td></tr><tr><td rowspan="2"></td><td>(10.20)</td><td>(8.71)</td><td>(7.97)</td><td>(6.13)</td><td>(3.43)</td><td>(5.50)</td><td>(5.34)</td><td>(4.00)</td><td>(3.91)</td><td>(2.26)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="2">MKT</td><td>-0.25</td><td>-0.11</td><td>-0.34 (-20.77)</td><td>0.05</td><td>-0.20</td><td>t 7'0-</td><td>-0.16</td><td>-0.28</td><td>0.00</td><td>-0.18</td></tr><tr><td>(-17.02)</td><td>(-8.08)</td><td></td><td>(3.35)</td><td>(-H.47)</td><td>(-H.36)</td><td>(-8.33)</td><td>(-B.74)</td><td>(-0.06)</td><td>(-0.50)</td></tr><tr><td rowspan="2">SMB</td><td>-0.38</td><td>-0.21</td><td>-0.41</td><td>-0.05</td><td>-0.30</td><td>-0.33</td><td>-0.20</td><td>-0.31</td><td>-0.18</td><td>-0.23</td></tr><tr><td>(-17.50)</td><td>(-10.21)</td><td>(-17.00)</td><td>(-2.53)</td><td>(-H.82)</td><td>(-9.46)</td><td>(-5.07)</td><td>(-7.48)</td><td>(-5.62)</td><td>(-6.58)</td></tr><tr><td rowspan="2">HML</td><td>-0.12</td><td>-0.28</td><td>-0.23 (-8.50)</td><td>-0.44</td><td>0.39</td><td>10'0- (-0.31)</td><td>-0.16 (3.93)</td><td>-0.22 (5.23)</td><td>-0.38 (-1162)</td><td>0.36 (686)</td></tr><tr><td>(-5.03)</td><td>(-12.16)</td><td></td><td>(-18.81)</td><td>(5.68)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="2">UMD</td><td>d.0</td><td>-0.07</td><td>10'0</td><td>-0.17</td><td>0.21</td><td>0.15</td><td>0.03</td><td>0.10</td><td>-0.14</td><td>0.24</td></tr><tr><td>(0.82)</td><td>(-3.80)</td><td>(0.64)</td><td>(-8.55)</td><td>(00.79)</td><td>(5.54)</td><td>(101)</td><td>(3.07)</td><td>(-5.64)</td><td>(8.57)</td></tr><tr><td>Sharpe Ratio</td><td>0.58</td><td>0.51</td><td>0.27</td><td>0.22</td><td>0.45</td><td>0.62</td><td>0.63</td><td>0.26</td><td>0.05</td><td>0.66</td></tr><tr><td>InfomationRatio Adjusted R 2</td><td>1.46 0.57</td><td>1.25 0.37</td><td>1.14 0.63</td><td>0.88 0.40</td><td>0.49 0.60</td><td>1.16 0.60</td><td>1.13 0.34</td><td>0.84 0.58</td><td>0.83 0.35</td><td>0.48 0.52</td></tr></table></body></html>

Profitability and Safety seem to contribute the most. High quality stocks are larger in size (negative SMB) and more expensive (negative HML). Junkier stocks tend to be smaller and cheaper.
# Table VI (Continued) Quality Minus Junk: By Country

This table shows calendar-time portfolio returns and factor loadings. Quality minus Junk (QMI) factors are constructed as the intersection of six value-weighted portfolios formed on size and quality. At the end of each calendar month, stocks are assigned to two size-sorted porfolios based on their market capitalization. For U.S. securities, the size breakpoint is the median NYSE market equity. For International securities the size breakpoint is the Soth percentile by country. We use conditional sorts, first sorting on size, then on quality. Portfolios are value-weighted, refreshed every calendar month, and rebalanced every calenda 1 month to maintain value weights. The QMJ factor retum is the average retum on the two high quality porfolios minus the average returm on the two low quality (junk) portfolios. Portfolios based on profitability. Growth, safety and payout score are constructed in a similar manner. We form one set of portfolios in each country and compute global portfolios by weighting each country's portfolio by the country's total (lagged) market capitalization. This table includes all available common stocks on the CRSP/Xpressfeed merged database for the markets listed in Table I Alpha is the intercept in a time-series regression o 1 monthly excess retum. The explanatory variables are the monthly retums from the market portfolio (MKT) and size (SMB) book-to-market (HML), and momentum (UMD) factor-mimicking portfolios. Panel A reports results from our Long Sample oi domestic stocks. The sample period runs from June 1956 to December 2012. Panel B reports results from our Broad Sample o 1 global stocks. Panel C reports results by country. The sample period runs from June 1986 to December 2012. Returns are in USD, do not include currency hedging, and excess returns are above the U.S. Treasury bill rate. Returns and alphas are in monthly percent, t-statistics are shown below the coeffcient estimates, and $5\%$ statistical significance is indicated in bold. Information ratio is equal to 4-factor alpha (intercept) divided by the standard deviation of the estimated residuals in the time. Series regression. Sharpe ratios and information ratios are annualized.

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">Excess retum</td><td rowspan="2">T-stat Evcess retun</td><td rowspan="2">4-factor Alpha</td><td rowspan="2">T-stat Alpha</td><td colspan="4">Factor Loading</td><td rowspan="2">Ratio</td><td colspan="2">Shape Information Number of</td><td rowspan="2">Date Range months</td></tr><tr><td>MKT</td><td>SMB</td><td>HML</td><td>UMD</td><td></td><td>Ratio</td></tr><tr><td>Australia</td><td>0.34</td><td>1.51</td><td>0.55</td><td>2.73</td><td>-0.17</td><td>-0.40</td><td>0.10</td><td>0.00</td><td>0.36</td><td>0.75</td><td>210</td><td>1995-2012</td></tr><tr><td>Aushria</td><td>0.21</td><td>0.66</td><td>0.38</td><td>1.42</td><td>-0.33</td><td>-0.04</td><td>-0.15</td><td>0.11</td><td>0.16</td><td>0.36</td><td>198</td><td>1996-2012</td></tr><tr><td>Belgium</td><td>0.43</td><td>1.59</td><td>0.36</td><td>1.57</td><td>-0.16</td><td>-0.09</td><td>-0.16</td><td>0.27</td><td>0.38</td><td>0.41</td><td>210</td><td>1995-2012</td></tr><tr><td>Canada</td><td>0.61</td><td>2.98</td><td>0.39</td><td>2.05</td><td>-0.19</td><td>-0.07</td><td>0.28</td><td>0.21</td><td>0.59</td><td>0.43</td><td>306</td><td>1987-2012</td></tr><tr><td>Switzerland</td><td>0.39</td><td>1.41</td><td>+9'0</td><td>3.17</td><td>-0.35</td><td>-0.31</td><td>-0.33</td><td>0.08</td><td>0.34</td><td>0.79</td><td>210</td><td>1995-2012</td></tr><tr><td>Gemany</td><td>0.48</td><td>2.35</td><td>0.59</td><td>3.56</td><td>-0.24</td><td>-0.11</td><td>-0.19</td><td>0.05</td><td>0.56</td><td>0.92</td><td>210</td><td>1995-2012</td></tr><tr><td>Denmak</td><td>0.66</td><td>2.08</td><td>0.49</td><td>1.90</td><td>-0.20</td><td>-0.25</td><td>-0.34</td><td>0.17</td><td>0.50</td><td>0.48</td><td>107</td><td>1996-2012</td></tr><tr><td>Spain</td><td>0.15</td><td>0.58</td><td>0.20</td><td>0.88</td><td>-0.25</td><td>-0.08</td><td>-0.06</td><td>0.18</td><td>0.14</td><td>0.22</td><td>210</td><td>1995-2012</td></tr><tr><td>Finland</td><td>0.53</td><td>1.40</td><td>0.59</td><td>1.93</td><td>-0.08</td><td>-0.17</td><td>-0.51</td><td>10'0-</td><td>0.34</td><td>0.48</td><td>210</td><td>1995-2012</td></tr><tr><td>France</td><td>0.45</td><td>1.86</td><td>0.53</td><td>2.96</td><td>-0.27</td><td>-0.04</td><td>-0.17</td><td>0.16</td><td>0.45</td><td>0.76</td><td>210</td><td>1995-2012</td></tr><tr><td>United Kingdom</td><td>0.17</td><td>0.69</td><td>0.32</td><td>1.35</td><td>-0.27</td><td>-0.16</td><td>-0.15</td><td>0.08</td><td>0.15</td><td>0.33</td><td>246</td><td>1992-2012</td></tr><tr><td>Greece</td><td>1.35</td><td>2.54</td><td>1.06</td><td>3.07</td><td>-0.07</td><td>-0.21</td><td>-0.19</td><td>0.34</td><td>0.79</td><td>0.98</td><td>126</td><td>2002-2012</td></tr><tr><td>Hong Kong</td><td>0.61</td><td>1.72</td><td>1.02</td><td>4.15</td><td>-0.27</td><td>-0.42</td><td>-0.18</td><td>0.08</td><td>0.41</td><td>1.04</td><td>210</td><td>1995-2012</td></tr><tr><td>Ireland</td><td>0.53</td><td>0.85</td><td>0.84</td><td>1.59</td><td>-0.53</td><td>0.04</td><td>-0.17</td><td>0.12</td><td>0.20</td><td>0.39</td><td>208</td><td>1995-2012</td></tr><tr><td>Lsrael</td><td>0.66</td><td>1.72</td><td>0.85</td><td>2.67</td><td>-0.33</td><td>-0.13</td><td>-0.12</td><td>0.07</td><td></td><td>0.85</td><td>138</td><td>2001-2012</td></tr><tr><td></td><td>0.72</td><td>2.54</td><td>0.69</td><td>3:60</td><td>-0.21</td><td>-0.12</td><td>-0.22</td><td>0.26</td><td>0.62</td><td>16'0</td><td>198</td><td>1996-2012</td></tr><tr><td>Japan</td><td>0.22</td><td>1.02</td><td>0.38</td><td>2.40</td><td>-0.31</td><td>-0.28</td><td>-0.15</td><td>0.10</td><td>0.23</td><td>0.59</td><td>246</td><td>1992-2012</td></tr><tr><td>Netherlands</td><td>0.10</td><td>0.33</td><td>0.34</td><td>1.43</td><td>-0.37</td><td>-0.08</td><td>-0.15</td><td>0.04</td><td>0.08</td><td>0.35</td><td>210</td><td>1995-2012</td></tr><tr><td>Norway</td><td>0.61</td><td>1.95</td><td>0.68</td><td>2.47</td><td>-0.19</td><td>-0.23</td><td>-0.13</td><td>0.18</td><td>0.47</td><td>0.61</td><td>210</td><td>1995-2012</td></tr><tr><td>New Zealand</td><td>0.07</td><td>0.22</td><td>-0.05</td><td>-0.17</td><td>-0.15</td><td>-0.06</td><td>-0.14</td><td>0.16</td><td>0.05</td><td>-0.04</td><td>210</td><td>1995-2012</td></tr><tr><td>Portugal</td><td>0.86</td><td>1.87</td><td>0.89</td><td>2.30</td><td>-0.26</td><td>-0.08</td><td>-0.26</td><td>0.18</td><td>0.53</td><td>0.67</td><td>150</td><td>2000-2012</td></tr><tr><td>Sumgapore</td><td>0.26</td><td>0.90</td><td>0.44</td><td>2.38</td><td>-0.22</td><td>-0.31</td><td>-0.11</td><td>0.06</td><td>0.22</td><td>0.60</td><td>210</td><td>1995-2012</td></tr><tr><td>Sweden</td><td>0.40</td><td>1.49</td><td>0.50</td><td>2.36</td><td>-0.22</td><td>-0.26</td><td>-0.22</td><td>0.15</td><td>0.32</td><td>0.53</td><td>256</td><td>1991-2012</td></tr><tr><td>United States</td><td>0.40</td><td>4.38</td><td>0.66</td><td>10.20</td><td>-0.25</td><td>-0.38</td><td>-0.12</td><td>0.02</td><td>0.58</td><td>1.46</td><td>678</td><td>1956-2012</td></tr><tr><td>Global</td><td>0.38</td><td>3.22</td><td>0.45</td><td>5.50</td><td>-0.24</td><td>-0.33</td><td>10'0-</td><td>0.15</td><td>0.62</td><td>1.16</td><td>324</td><td>1986-2012</td></tr></table></body></html>

# Buffett's alpha (Frazzini, Kabiller, and Pedersen, 2012)

· Berkshire Hathaway has the highest Sharpe Ratio of any stock or mutual fund with a history more than 30 years.

O Sharpe Ratio of 0.76 during 1976 to 2011. O Market has only a Sharpe Ratio of 0.39 during the same period.

· It also has a significant alpha based on traditional risk factor models.
Why?

The authors identify the following factors:

· Buying “safe stocks: low beta and low volatility.
·Buying “value” stocks.
·Buying “quality” stocks. Applying a high leverage partly using cheap “insurance float from the insurance and reinsurance businesses.

As we saw from the earlier literature, these are all factors that generate excess returns.

How do they measure leverage?

$$
L_{t}=\frac{T A_{t}^{M V}-C a s h_{t}^{M V}}{E q u i t y_{t}^{M V}}
$$

$$
T A_{t}^{M V}=T A_{t}^{B V}+E q u i t y_{t}^{M V}-E q u i t y_{t}^{B V}
$$

This assumes book value of debt $=$ market value of debt; which would underestimate leverage. The definition of debt here includes all non-interest bearing operating liabilities, deferred tax liabilities and derivativecontract liabilities.

L = (Net Debt + Equity)/Equity $=1+\mathrm{Net}$ Debt/Equity

With this measure they estimate a leverage of 1.6 to 1. For every $\$1$ of equity, Berkshire borrows $\$0.60$ andinvests $\$1.60$ in its assets. The portfolio weight on assets is 1.6 and the weight on debt is -0.60 and the weights sum to 1.

Another measure of leverage they use is:

$$
\mathrm{L=(Equity+Debt+Float)/Equity}=1+(\mathrm{Debt+Float})
$$

Float is Insurance Float. With this measure they estimate a leverage of 1.4 to 1. This excludes other operating liabilities.

# Berkshire's public vs. Private holdings

Berkshire's public holdings can be obtained from Berkshire's quarterly 13-F filings to the SEC.

From this, the monthly market values of all public holdings and the monthly returns of this mimicking portfolio can be computed.

How do they estimate the market value of private holdings (which includes the value of Buffett himself) and their returns?

$$
\begin{array}{l}{P r i v a t e_{t}^{M V}=T A_{t}^{M V}-P u b l i c_{t}^{M V}-C a s h_{t}^{M V}}\ {r_{t+1}^{P r i v a t e}}&{=\frac{\Delta P r i v a t e_{t+1}^{M V}}{P r i v a t e_{t}^{M V}}}\ {~}\ {=\frac{r_{t+1}^{f}L i a b i l i t i e s_{t}^{M V}+r_{t+1}^{E q u i t y}E q u i t y_{t}^{M V}-r_{t+1}^{p u b l i c}P u b l i c_{t}^{M V}-r_{t+1}^{f}C a s i}{P r i v a t e_{t}^{M V}}}\end{array}
$$

Berkshire stock's excess return can be written as a weighted average of its private return and public return leveraged up:

$$
\begin{array}{r l}&{r_{t+1}^{E q u i t y}-r_{t+1}^{f}=\left[w_{t}\left (r_{t+1}^{p r i v a t e}-r_{t+1}^{f}\right)+(1-w_{t})\big (r_{t+1}^{p u b l i c}-r_{t+1}^{f}\big)\right]L_{t}}\ &{}\ &{w_{t}=\frac{P r i v a t e_{t}^{M V}}{P r i v d t e_{t}^{M V}+P u b l i c_{t}^{M V}}}\end{array}
$$

See the appendix of the paper for the algebra of the derivation from the equation for private returns.
# Table 1

# Buffett's Performance Relative to All Other Stocks and Mutual Funds.

This table shows the Sharpe ratio (SR) and Information ratio (IR) of Berkshire Hathaway relative to the universe of common stocks on the CRSP Stock database from 1926 to 2011, and relative to the universe of actively managed equity mutual funds on the CRSP Mutual Fund database from 1976 to 2011. The Information ratio is defined as the intercept in a regression of monthly excess returns divided by the standard deviation of the residuals. The explanatory variable in the regression is the monthly excess returms of the CRSP value-weighted market portfolio. Sharpe ratios and information ratios are annualized.

<html><body><table><tr><td></td><td colspan="5">SalupleDistributionofSharpe Ratios</td><td colspan="2">Buffett Performance</td></tr><tr><td></td><td>Numberof stocks/finds</td><td>Median 95 th Percentile goth Percentile</td><td></td><td></td><td>Maxinmm</td><td>Rank</td><td>Percentile</td></tr><tr><td>PauelA: SRofEquityMhtunlFuncds All fiuds im CRSP data 1976-2011</td><td>3,479</td><td>0.242</td><td>0.49</td><td>1.09</td><td>2.99</td><td>88</td><td>97.5%</td></tr><tr><td>All finds alive n 1976 and 2011</td><td>140</td><td>0.37</td><td>0.52</td><td>0.76</td><td>0.76</td><td>1</td><td>100.0%</td></tr><tr><td>All fnds alive m 1976 with at least 10-yearhistory</td><td>264</td><td>0.35</td><td>0.51</td><td>0.65</td><td>0.76</td><td>1</td><td>100.0%</td></tr><tr><td>All fndswith at least 10-yearhistory</td><td>1,994</td><td>0.30</td><td>0.47</td><td>0.65</td><td>0.90</td><td>4</td><td>99.8%</td></tr><tr><td>All funds with at least 30-yearhistory</td><td>196</td><td>0.37</td><td>0.51</td><td>0.72</td><td>0.76</td><td>1</td><td>100.0%</td></tr><tr><td>Pamel B: SRof CommonStocks</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>All stocks in CRSP data 1926-2011</td><td>23,390</td><td>0.195</td><td>0.61</td><td>1.45</td><td>2.68</td><td>1360</td><td>93.9%</td></tr><tr><td>All stocks alive m 1976 and 2011</td><td>598</td><td>0.32</td><td>#0</td><td>0.56</td><td>0.76</td><td>1</td><td>100.0%</td></tr><tr><td>Allstocks alive m 1976 with at least 10-yearhistory</td><td>3,633</td><td>0.27</td><td>0.45</td><td>0.61</td><td>0.86</td><td>7</td><td>99.896</td></tr><tr><td>All stocks with at least 10-year history</td><td>9,035</td><td>0.26</td><td>0.48</td><td>0.73</td><td>1.12</td><td>62</td><td>99.3%</td></tr><tr><td>All stocks withat least 30-yearhistory</td><td>1,777</td><td>0.31</td><td>0.44</td><td>0.57</td><td>0.76</td><td>1</td><td>100.0%</td></tr><tr><td></td><td colspan="5">SampleDistributionof InformafionRatios</td><td colspan="2">Buffett Perforumnce</td></tr><tr><td></td><td>Numberof stocks/funds</td><td colspan="3">Median 95 th Percentile 9 gth Percentile</td><td>Maxinmm</td><td>Rank</td><td>Percentile</td></tr><tr><td>Panel C: IRof EquityMutual Fundk AllfiudsinCRSPdata 1976-2011</td><td></td><td>-0.060</td><td>0.39</td><td>0.89</td><td>284</td><td>100</td><td>97.1%</td></tr><tr><td>Allfindsaliveim 1976 and 2011</td><td>3,479 140</td><td>0.050</td><td>0.39</td><td>0.68</td><td>0.81</td><td>2</td><td>99.3%</td></tr><tr><td>Allfinds alive in 1976 with at least 10-yearhistory</td><td>264</td><td>-0.025</td><td>0.30</td><td>0.60</td><td>0.81</td><td>2</td><td>99.6%</td></tr><tr><td>All fnds with at least 10-yearhistory</td><td>1,994</td><td>0.022</td><td>0.38</td><td>0.77</td><td>122</td><td>42</td><td>97.9%6</td></tr><tr><td>All funds with at least 30-yearhistory</td><td>196</td><td>+20'0</td><td>0.34</td><td>0.66</td><td>0.81</td><td>2</td><td>99.5%</td></tr><tr><td>Panel D: IRof Comumon Stocks</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>AllstocksinCRSPdata 1926-2011</td><td>23,390</td><td>0.089</td><td>t 50</td><td>1.41</td><td>167</td><td>1510</td><td>93.3%</td></tr><tr><td>Allstocks aliveim 1976 and 2011</td><td>598</td><td>0.183</td><td>0.32</td><td>0.46</td><td>0.66</td><td>1</td><td>100.0%</td></tr><tr><td>All stocks alive m 1976 with atleast 10-yearhistory</td><td>3,633</td><td>0.146</td><td>0.36</td><td>0.57</td><td>0.80</td><td>13</td><td>99.7%</td></tr><tr><td>All stocks with at least 10-year history</td><td>9,035</td><td>0.136</td><td>0.38</td><td>0.62</td><td>1.07</td><td>58</td><td>99.49</td></tr><tr><td>All stocks with at least 30-year history</td><td>1,777</td><td>0.130</td><td>0.29</td><td>0.43</td><td>0.66</td><td>1</td><td>100.0%</td></tr></table></body></html>

# Buffett's returns decomposed (from Table 2)

<html><body><table><tr><td></td><td colspan="3">Buffett Performance</td><td></td><td colspan="3">Buffett-Stvle Portfolio</td></tr><tr><td></td><td>Berkshire Hathaway</td><td>Public U.S. stocks (fom 13 F filings)</td><td>Private holdings</td><td>Overall stock market performance</td><td>Berkshire Hathaway</td><td>Public US. Stocks (from 13 F filings)</td><td>Private holdings</td></tr><tr><td>Sample</td><td>1976-2011</td><td>1980-2011</td><td>1984-2011</td><td>1976-2011</td><td>1976-2011</td><td>1980-2011</td><td>1984-2011</td></tr><tr><td>Beta</td><td>0.67</td><td>0.77</td><td>0.28</td><td>1.00</td><td>0.67</td><td>0.77</td><td>0.28</td></tr><tr><td>Average excess retum</td><td>19.0%</td><td>11.8%</td><td>9.6%</td><td>6.1%</td><td>26.4%</td><td>18.4%</td><td>13.8%</td></tr><tr><td>Total Volatility</td><td>24.8%</td><td>17.2%</td><td>22.3%</td><td>15.8%</td><td>24.8%</td><td>17.2%</td><td>22.3%</td></tr><tr><td>Idiosyncratic Volatility</td><td>22.4%</td><td>12.0%</td><td>21.8%</td><td>0.0%</td><td>22.4%</td><td>12.0%</td><td>21.8%</td></tr><tr><td>Sharpe ratio</td><td>0.76</td><td>0.69</td><td>0.43</td><td>0.39</td><td>1.06</td><td>1.07</td><td>0.62</td></tr><tr><td>Infomation ratio Leverage</td><td>0.66</td><td>0.56</td><td>0.36</td><td>0.00</td><td>0.99</td><td>1.11</td><td>0.55</td></tr><tr><td></td><td>1.64</td><td>1.00</td><td>1.00</td><td>1.00</td><td>3.79</td><td>2.46</td><td>3.01</td></tr><tr><td colspan="2">Sub period excess retums:</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1976-1980</td><td>42.1%</td><td>31.4%</td><td></td><td>7.8%</td><td>8.0%</td><td>30.7%</td><td></td></tr><tr><td>1981-1985</td><td>28.6%</td><td>20.9%</td><td>18.5%</td><td>4.3%</td><td>46.4%</td><td>27.8%</td><td>22.1%</td></tr><tr><td>1986-1990</td><td>17.3%</td><td>12.5%</td><td>9.7%</td><td>5.4%</td><td>17.9%</td><td>13.1%</td><td>7.0%</td></tr><tr><td>1991-1995</td><td>29.7%</td><td>18.8%</td><td>22.9%</td><td>12.0%</td><td>41.7%</td><td>24.0%</td><td>30.9%</td></tr><tr><td>1996-2000</td><td>14.9%</td><td>12.0%</td><td>8.8%</td><td>11.8%</td><td>39.4%</td><td>23.2%</td><td>28.8%</td></tr><tr><td>2001-2005</td><td>3.2%</td><td>2.2%</td><td>1.7%</td><td>1.6%</td><td>28.5%</td><td>16.8%</td><td>10.4%</td></tr><tr><td>2006-2011</td><td>3.3%</td><td>3.0%</td><td>2.3%</td><td>0.8%</td><td>3.3%</td><td>5.7%</td><td>-8.1%</td></tr></table></body></html>

Both public and private stocks outperform the market.

· Public stocks have a higher Sharpe ratio than private holdings suggesting Buffett's skill is in public stock selection not necessarily in private firm management.
· The returns of Berkshire are much higher than the returns of both public and private portfolios because of the use of leverage and diversification.
Buffett style portfolio is a portfolio constructed to have similar factor tilts as Buffett's portfolios (see also Table 5 on the covariation between  Buffett style portfolio and Buffett performance). It earns far higher returns perhaps because it doesn't take into account transaction and other costs. Any other reasons?

# Table 4

# Buffett's Exposures: What Kind of Companies does Berkshire Own?

This table shows calendar-time portfolio returns. We report statistics for, respectively, Berkshire Hathaway stock, the mimicking portfolio of Berkshire's publicly traded stocks as reported in its 13 F filings and the mimicking portfolio of Berkshire's private holdings. To construct the mimicking portfolio of Berkshire's publicly traded stocks, at the end of each calendar quarter, we collect Berkshire's common stock holdings from its 13 F filings and compute portfolio monthly returns, weighted by Berkshire's dollar holdings, under the assumption that the firm did not change holdings between reports. The stocks in the portfolio are refreshed quarterly based on the latest 13 F and the portfolio is rebalanced monthly to keep constant weights. The mimicking portfolio of Berkshire's private holdings is constructed following the procedure described in Appendix A. Alpha is the intercept in a regression of monthly excess return. The explanatory variables are the monthly returns of the standard size, value, and momentum factors, the Frazzini and Pedersen (2010) Betting-Against-Beta factor, and the Asness, Frazzini and Pedersen (2012) Quality-MinusJunk factor. Alphas are annualized, t-statistics are shown below the coefficient estimates, and $5\%$ statistical significance is indicated in bold.

<html><body><table><tr><td rowspan="2">Alpha</td><td colspan="3">Berkshire stocl 1976-2011</td><td colspan="3">13 Fportfolio 1980-2011</td><td colspan="3">PrivateHoldings 1984-20011</td></tr><tr><td>12.5% (3.28)</td><td>11.1% (2.92)</td><td>7.0% (1.79)</td><td>5.5% (2.60)</td><td>4.7% (2.26)</td><td>0.1% (0.04)</td><td>5.8% (1.39)</td><td>5.0% (1.20)</td><td>4.9% (1.12)</td></tr><tr><td>MKT</td><td>0.84</td><td>0.78</td><td>0.97</td><td>0.86</td><td>0.83</td><td>1.04</td><td>0.40</td><td>0.35</td><td>0.35</td></tr><tr><td>SMB</td><td>(11.49) -0.30</td><td>(10.49) -0.39</td><td>(10.62) -0.07</td><td>(21.33) -0.18</td><td>(19.86) -0.23</td><td>(21.04) 0.11</td><td>(4.92) -0.29</td><td>(4.19) -0.34</td><td>(3.33) -0.33</td></tr><tr><td>HML</td><td>-(2.91) 0.47</td><td>-(3.61) 0.30</td><td>-(0.52) 0.21</td><td>-(3.16) 0.30</td><td>-(3.97) 0.19</td><td>(1.52) 0.10</td><td>-(2.53) 0.26</td><td>-(2.93) 0.14</td><td>-(2.09) 0.13</td></tr><tr><td>UMD</td><td>(4.24) 0.06 (0.86)</td><td>(2.39) 0.02</td><td>(1.72) 0.01</td><td>(4.88) -0.02</td><td>(2.74) -0.05</td><td>(1.48) -0.06</td><td>(2.19) 0.08</td><td>(1.01) 0.05</td><td>(0.97) 0.05</td></tr><tr><td>BAB</td><td></td><td>(0.29) 0.27 (3.12)</td><td>(0.16) 0.18</td><td>-(0.60)</td><td>-(1.34) 0.16</td><td>-(1.69) 0.07</td><td>(1.13)</td><td>(0.63) 0.18</td><td>(0.63) 0.18</td></tr><tr><td>Qualilty</td><td></td><td></td><td>(2.11) 1.40 (3.50)</td><td></td><td>(3.50)</td><td>(1.58) 1.49 (7.12)</td><td></td><td>(2.07)</td><td>(1.97) 0.04 (0.08)</td></tr><tr><td>R 2 bar</td><td>0.24</td><td>0.26</td><td>0.28</td><td>0.56</td><td>0.57</td><td>0.62</td><td>0.07</td><td>0.08</td><td>0.08</td></tr></table></body></html>

· Betas with respect to the various factors tell us the story.

Larger firms $\mathrm{(SMB<0)}$ 0, Value firms $(\mathrm{HML}>0)$ , safe low beta firms $(\mathrm{BAB}>0)$ , high quality firms $\mathrm{(Quality>0)}$

· No significant trend chasing (momentum) bets $(\mathrm{UMD}=0)$

# Recipe for success - Buffett's strategy

Larger size
Value
Safety
Quality
Leverage (especially cheap insurance float is available).

Insurance float arises because we pay insurance premiums ahead of time but insurance companies pay out claims much later. The float is a liability but is available at a much lower cost. Authors estimate $36\%$ of Berkshire's liabilities is float.

This table shows the cost of Berkshire's funds coming from insurance float. The data is hand-collected from Buffett's comment in Berkshire Hathaway's annual reports. Rates are annualized, in percent.

Table 3 Buffett's Cost of Leverage: The Case of His Insurance Float
<html><body><table><tr><td></td><td>Fraction of years with negative cost</td><td>Average cost of fimds (Trucated)*</td><td colspan="5">Spread over benckmark rates</td></tr><tr><td></td><td></td><td></td><td>T-BillFedFunds</td><td>rate</td><td>1-Month Libor</td><td>6-Month Libor</td><td>10-Year Bond</td></tr><tr><td>1976-1980</td><td>0.79</td><td>1.67</td><td>-4.59</td><td>-5.65</td><td></td><td></td><td>-5.76</td></tr><tr><td>1981-1985</td><td>0.20</td><td>10.95</td><td>1.10</td><td>-0.27</td><td></td><td></td><td>-1.28</td></tr><tr><td>1986-1990</td><td>0.00</td><td>3.07</td><td>-3.56</td><td>-4.61</td><td>-4.80</td><td>4.90</td><td>-5.30</td></tr><tr><td>1991-1995</td><td>0.60</td><td>2.21</td><td>-2.00</td><td>-2.24</td><td>-2.46</td><td>-2.71</td><td>-4.64</td></tr><tr><td>1996-2000</td><td>0.60</td><td>2.36</td><td>-2.70</td><td>-3.10</td><td>-3.33</td><td>-3.48</td><td>-3.56</td></tr><tr><td>2001-2005</td><td>0.60</td><td>1.29</td><td>-0.82</td><td>-0.96</td><td>-1.05</td><td>-1.19</td><td>-3.11</td></tr><tr><td>2006-2011</td><td>1.00</td><td>4.00</td><td>-5.84</td><td>-6.06</td><td>-6.29</td><td>-6.59</td><td>-7.67</td></tr><tr><td>Full sample</td><td>0.60</td><td>2.20</td><td>-3.09</td><td>-3.81</td><td>-3.69</td><td>-3.88</td><td>-4.80</td></tr></table></body></html>

\* In years when cost of funds is reported as "less than zero" and no numerical value is available we set cost of funds to zero

# References

I have tried my best to include below all the material I reviewed over a twenty year period in preparing my lecture notes. It is by no means exhaustive.

1. Andrade, Gregor, and Erik Stafford, 1999, “Investigating the Economic Role of Mergers," Working paper, Harvard Business School.
2. Anslinger, Patricia, L., and Thomas E. Copeland, 1996, “growth through Acquisitions: A Fresh Look,” Harvard Business Review, 74, pp. 126-135.
3. Asness, Clifford, 2007, “The Interaction of Value and Momentum Strategies,” Financial Analysts Journal, March/April 1997, pp. 29-36.
4. Asness, Clifford, Toby Moskowitz, Lasse Pedersen, 2013, "Value and Momentum Everywhere," Journal of Finance, 68 (June 2013), pp. 929-985.
5. Asness, Clifford, Andrea Frazzini, and Lasse Pedersen, 2013, “Quality Minus Junk," Working Paper, AQR Capital Management.
6. Barberis, Nicholas, and Richard Thaler, 2003, “A Survey of Behavioral Finance” Chapter 18 in the Handbook of the Economics of Finance edited by George Constantinides, Milt Harris, and Rene Stulz, published by Elsevier Science B.V.
7. Barberis, Nicholas, Andrei Shleifer, and Robert Vishny. 1998. “A Model of Investor Sentiment." Journal of Financial Economics 49 (3): 307-343.
8. Benninga, Simon, Z., and Oded H. Sarig, 1997, “Corporate Finance: A valuation Approach. McGraw-Hill
9. Bernstein, Richard, 1995, “Style Investing: Unique Insight In to Equity Management," John Wiley & Sons Inc.
10. Bhojraj, Sanjeev, and Bhaskaran Swaminathan, 2009, “How does the corporate bond market value capital investments and accruals? Review of Accounting Studies, 14, pp. 31-62.
11. Bradley, Michael, Anand Desai, and E. Han Kim, 1983, “The rationale behind interfirm tender offers: Information or synergy? Journal of Financial Economics, 11, pp. 183- 206.
12. Levy, Haim, and Marshall Sarnat, 1994, Fifth Edition, “Capital Investment & Financial Decisions, Prentice Hall.
13. Chan, K. C., N. Jegadeesh, and J. Lakonishok, 1996, “Momentum Strategies," Journal of Finance, 51, 1681-1713.
14. Chan, Konan, Louis Chan, Narasimhan Jegadeesh, and Josef Lakonishok, 2006, "Earnings Quality and Stock Returns,”" Journal of Business, Vol. 79, No. 3, pp. 1041- 1082.
15. Cooper, Michael, Huseyin Gulen, and Michael Schill, 2008, “Asset Growth and the Cross-Section of Stock Returns," Journal of Finance, 63 (August 2008), pp. 1609-1651.
16. Copeland, Thomas E., J. Fred Weston, 1988, “Financial Theory and Corporate Policy," Third Edition, 1988, Addison-Wesley Publishing.
17. Copeland, Tom, Tim Koller, and Jack Murrin, \*'Valuation: Measuring and Managing the Value of Companies,” Third Edition (University Edition), 2000, McKinsey& Company.
18. Daniel, K., D. Hirshleifer, and A. Subrahmanyam, 2001, “Overconfidence, arbitrage, anc equilibrium asset pricing,” Journal of Finance 56, 921-965.
19. Damodaran, Aswath, 1994, “Damodaran on Valuation: Security Analysis for Investment and Corporate Finance,” First Edition, John Wiley & Sons, Inc.
20. Damodaran, Aswath, 1996, “Invesment Valuation: Tools and techniques for determining the value of any asset," John Wiley & Sons, Inc.
21. DeBondt, Werner, F. M., and Richard Thaler, 1985, “Does the Stock market Overreact?\* The Journal of Finance, Vol. 40, pp. 793-805.
22. Devos, Erik, Palani-Rajan Kadapakkam, and Srinivasan Krishnamurthy, 2009, “How Do Mergers Create Value? Comparison of Taxes, market Power, and Efficiency Improvements as Explanations for Synergies,” The Rview of Financial Studies, Vol. 2, pp. 179-1211.
23. Elton, Edwin, J., and Martin J. Gruber, 1987, “Modern Portfolio Theory and Investment Analysis, Third Edition, John Wiley & Sons.
24. Ehrhardt, Michael, C., 1994, "The Search for Value: Measuring the Company's Cost of Capital," Harvard Business School Press.
25. Fairfield, Patricia M. and Whisenant, Scott and Yohn, Teri Lombardi, 2003, “Accrued Earnings and Growth: Implications for Earnings Persistence and Market Mispricing," Accounting Review, Vol. 78, pp. 353-371.
26. Fama, E., and K. French, 1992, "The cross-section of expected stock returns,” Journal o) Finance 47, 427-466.
27. Fama, E., and K. French, 1993, “Common risk factors in the returns on stocks and bonds," Journal of Financial Economics 33, 3-56.
28. Fama, E. F., and K. R. French, 1996, μMultifactor Explanations of Asset Pricing Anomalies," Journal of Finance, Vol. 47, pp. 427-465.
29. Foster, George, Chris Olsen, and Terry Shevlin, 1984, “Earnings Releases, Anomalies, and the Behavior of Security Returns," The Accounting Review, Vol. 59, pp. 574-603.

30. Franks, Julian, Robert Harris, and Sheridan Titman, 1991, “The postmerger share-price performance of acquiring firms,”" Journal of Financial Economics, Vol. 29, pp. 81-96.

31. Frazzini, Andrea, David Kabiller, and Lasse Pedersen, 2012, “Buffett's Alpha," Working Paper, AQR Capital Management.

32. Frederick, Shane, 2005, “"Cognitive Reflection and Decision Making,” Journal of Economic Perspectives, Vol. 19, No. 4 (Fall 2005), pp. 25-42.
33. Fuller, Kathleen, Jeffry Netter, and Mike Stegmoller, 2002, "What Do Returns to Acquiring Firms Tell us? Evidence from Firms That Make Many Acquisitions” The Journal of Finance, Vol. 57, pp. 1763-1793.
34. Graham, Benjamin, and David L. Dodd, 1934, “Security Analysis,” Whittlesey House.
35. Grullon, Gustavo, Roni Michaely, and Bhaskaran Swaminathan, 2002, “Are Dividend Changes a Sign of Firm Maturity?" Journal of Business, Vol. 75, issue 3, pp. 387-424.
36. Hong, Harrison, and Jeremy C. Stein, 1999, A Unified Theory of Underreaction, Momentum Trading, and Overreaction in Asset Markets,” The Journal of Finance, Vol. 54, pp. 2143-2184.
37. Jagannathan, Ravi, Ellen R. McGrattan, Anna Scherbina, Fall 2000, "The Declining U.S. Equity Premium,” Federal Reserve Bank of Minneapolis.
38. Jarrell, Gregg, , James A. Brickley, and Jeffry M. Netter, 1988, The Markt for Corporate Control: The Empirical Evidence Since 1980,”" Journal of Economic Perspectives, Vol. 2, No. 1, pp. 49-68.
39. Jegadeesh, N., and S. Titman, 1993, “Returns to buying winners and selling losers: Implications for stock market efficiency," Journal of Finance 48, 65-92.
40. Jensen, Michael, C., and Richard S. Ruback, 1983, "the market for corporate control: The scientific evidence,” Journal of Financial Economics, 11, pp. 5-50.
41. Kaplan, Steven, 1989,\*“The effects of management buyouts on operating performance and value,”" Journal of Financial Economics, Vol. 24, pp. 217-254.
42. Koller, Tim, March Goedhart, and David Wessels, 2010, "Valuation: Measuring and Managing the Value of Companies,” Fifth Edition (University Edition), McKinsey & Company.
43. Lakonishok, J., A. Shleifer, and R. W. Vishny, “Contrarian Investment, Extrapolation, and Risk," Journal of Finance, Vol. 49, pp. 1541-1578.
44. Lee, Charles M. C., and Bhaskaran Swaminathan, 2000, Price Momentum and Trading Volume,”" Journal of Finance, 55, 2017-2069.
45. Li, Yan, David Ng, and Bhaskaran Swaminathan, 2013, “Predicting market returns using aggregate implied cost of capital,” Journal of Financial Economics, 110, 419-436.
46. Li, Yan, David Ng, and Bhaskaran Swaminathan, 2014, “Predicting time varying value premium using implied cost of capital, Working Paper, Temple University, Cornell University and LSV Asset Management.
47. Loughran, T., and A. M. Vijh, 1997, Do Long-Term Shareholders Benefit From Corporate Acquisitions? The Journal of Finance, 52 (5), 1765-1790.
48. Manne, Henry, G., 1965, “Mergers and the Market for Corporate Control.,” Journal of Political Economy, Vol. 73, No. 2, pp. 110-120.
49. Marren, Joseph, H., 1993,\*Mergers & Acquisitions: A Valuation Handbook, McGrawHill.
50. Mitchell, Mark, and Kenneth Lehn, 1990, "Do Bad Bidders Become Good Targets? Journal of Political Economy, Vol. 98, pp. 372-98.
51. Mitchell, Mark, and Erik Stafford, 2000, “Managerial Decisions and Long-Term Stock Price Performance," The Journal of Business, 73, pp. 287-329.
52. Modigliani, Franco and Merton H. Miller, 1958, “the Cost of Capital, Corporation Finance and the Theory of Investment," The American Economic Review, Vol. 48, No. 3, pp. 261-297.
53. Moeller, Sara B., Frderik Schlingemann, and Rene Stulz, 2005, "Wealth Destruction on a Massive Scale? A study of Acquiring-Firm returns in the Recent Merger Wave," The Journal of Finance, Vol. 60, pp. 757-782.
54. Myers, Stewart, C., and Nicholas S. Majluf, 1984, “Corporate financing and investment decisions when firms have information that investors do not have,”" Journal of Financial Economics, Vol. 13, pp. 187-221.
55. Novy-Marx, Robert, 2013, "The Other Side of Value: The Gross Profitability Premium," Journal of Financial Economics 108 (1), 1-28.
56. O'Shaughnessy, James P., 2012, "What Works on Wall Street," Fourth Edition, McGraw Hill.
57. Piotroski, Joseph, 2000,\*Value Investing: The Use of Historical Financial Statement Information to Separate Winners from Losers,”" Journal of Accounting Research, Vol. 38, Supplement 2000, pp. 1-41.
58. Pontiff, Jeffrey, and Artemiza Woodgate, 2008, “Share Issuance and Cross-sectional Returns," Journal of Finance, 63 (April 2008), pp. 921-945.
59. Richardson, Scott, A., Richard G. Sloan, Mark T. Soliman, Irem Tuna, 2005, “Accrual reliability, earnings persistence and stock prices," Journal of Accounting and Economics, Vol. 39, pp. 437-485,
60. Roll, Richard, 1986, "The Hubris Hypothesis of Corporate Takeovers,” The Journal of Business, Vol. 59, No. 2, pp. 197-216.
61. Shleifer, Andrei & Vishny, Robert W, 1997. "The Limits of Arbitrage," The Journal of Finance, Vol. 52 (1), pages 35-55.
62. Sloan, Richard, 1996, “Do Stock Prices Fully Reflect Information in Accruals and Cash Flows about Future Earnings?" The Accounting Review, Vol. 71, No. 3, 289-315.
63. Stewart, Bennett, II, G., 1991, "The Quest for Value," HarperBusiness.

