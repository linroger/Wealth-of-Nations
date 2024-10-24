---
aliases:
- Alias_280_Lecture Note 1-Discounted Cash Flow Valuation-Computing Free Cash Flows.md
- Alias_277_Lecture Note 1-Discounted Cash Flow Valuation-Computing Free Cash Flows.md
tags:
- tag_example
title: Lecture Note 1-Discounted Cash Flow Valuation-Computing Free Cash Flows
---



# Lecture Note 1-Discounted Cash Flow Valuation-Computing Free Cash Flows

## TABLE OF CONTENTS

Lecture Note 1 - Discounted Cash Flow Valuation: Computing Free Cash Flows
Lecture Note 2 - Computing Cost of Capital: Cost of Equity,  Cost of Preferred Stock and Cost of Debt
Lecture Note 3 - Discounted Cash Flow Valuation: Value Drivers and Implementing the Free Cash Flow Model
Lecture Note 4 - Discounted Cash Flow Valuation: EVA and Discounted EVA Models
Lecture Note 5 - Valuation by Multiples
Lecture Note 6 - Computing Cost of Capital: Financial Leverage and Cost of Capital
Lecture Note 7 - Firm Valuation: Projecting Pro-Forma Financial Statements
Lecture Note 8 - Firm Valuation: Valuing Mergers,  Acquisitions & Multi-Business Firms
Lecture Note 9 - Security Analysis and Investor Behavior
Lecture Note 10 - Value and Momentum
Lecture Note 11 - Accruals,  Asset Growth and External Financing
Lecture Note 12 - Quality and Stock Returns

# LECTURE NOTE 1 DISCOUNTED CASH FLOW VALUATION: COMPUTING FREE CASH FLOWS

## OBJECTIVE INTRODUCE STUDENTS TO THE MECHANICS OF COMPUTING FREE CASH FLOWS

Outline Of The Lecture

- Define value of firm,  equity,  debt,  and preferred stock
- Define free cash flows to firm (FCFF),  free cash flows to equity (FCFE),  free cash flows to debt (FCFD),  and free cash flows to preferred stock (FCFP)
- Invested Capital - Asset base generating free cash flows to firm and the *rearranged balance sheet*
- Non-operating assets - Excess cash & marketable securities
- J M Smucker (SJM) Financial Statements
- Computing capital expenditures,  depreciation & amortization,
change in working capital,  taxes on EBIT,  and effective tax rate
- Deferred taxes
- Rearranged balance sheet with deferred taxes and goodwill; compute invested capital
- Investments in other companies
- Special Items
- Long-term operating liabilities

**A General Discounted Cash Flow (DCF) Model**
The intrinsic value of an asset,  V,  is the present value of all its expected future *free cash flows* (FCF):

$$V=\sum_{t=1}^{\infty}\frac{E\big{(}FCF_{t}\big{)}}{\big{(}1+r\big{)}^{t}}\tag{1}$$

- $E(FCF_t) =$E(FCF_t) =The forecasted free cash flows from the asset over its life.
- r = An appropriate risk-adjusted cost of capital.
- Free cash flows refer to cash flows that are available to the owner of the asset after meeting all obligations.
- The convention is to focus on cash flows after corporate taxes but before any personal taxes.
- We focus first on the numerator and discuss how to compute free cash flows.
- Later,  we turn to the denominator and discuss how to compute cost of capital.

**Valuing a Firm**

By definition,  the value of a firm is the sum of the value of debt,  preferred stock,  and equity:
$$\text{Firm Value}\equiv D+P+E$$(2a) D is the value of all interest bearing liabilities,  P is the value of preferred stock,  and E is the value of common stock.[1]
$$\text{Firm Value}=\text{Total Enterprise Value(V)}+\text{Value of NonOperating Assets}\tag{2b}$$

- Total Enterprise Value (V) represents the value of the operating assets of the firm.
- More generally,  we can value an N-asset firm by summing the values of all its N assets (the assets can be both operating and non-operating).
$$\text{Firm Value } =  V(\text{asset 1}) + V(\text{asset 2}) +…+V(\text{asset N})\tag{2c}$$
- This is called the *value-additivity principle*.

The firm can also be valued from the *liability side* (right hand side) of the balance sheet by valuing each financial claim:$D + P + E.$

## DEFINING VALUE OF FIRM,  DEBT,  PREFERRED STOCK,  AND EQUITY

- The total enterprise (operating) value of a firm,  V,  is the PV of the *free (operating) cash flows to firm* (FCFF) discounted at the *weighted average cost of capital* (WACC).
- The value of debt is the PV of the *cash flows to debt* discounted at the *cost of debt* ($r_d$).
- The value of preferred stock is the PV of the cash flows to preferred stock at the *cost of preferred stock* ($r_p$).
- The value of equity is the PV of the free cash flows to equity (FCFE) discounted at the *cost of equity* ($r_e$).

| Valuation            | Cash Flows                   | Discount rate         |
| -------------------- | ---------------------------- | --------------------- |
| (1) Enterprise value | Free cash flows to firm,   FCF | Weighted average cost |
|                      |                              | of capital (WACC)     |
| (2) Debt             | Cash flows to debt,   FCFD     | Cost of Debt,   r_d     |
| (3) Preferred stock  | Cash flows to preferred      | Cost of Preferred     |
|                      | stock,   FCFP                  | Stock,   r_p            |
| (4) Common Stock     | Free cash flows to           | Cost of Equity,   r_e   |
|                      | equity,   FCFE                 |                       |

### FREE CASH FLOWS TO FIRM
- Total *operating* cash flows available after meeting all operating expenses,  taxes,  capital expenditures,  and investments in working capital but *before* any interest and debt principal repayments,  and preferred dividends and repayments.

### FREE CASH FLOWS TO DEBT
- This represents the sum of interest payments and net principal repayments (if any) each period.

### FREE CASH FLOWS TO PREFERRED STOCK
- This represents the sum of preferred dividends and any net retirement of preferred stock.

### FREE CASH FLOWS TO EQUITY
- This is the *residual* cash flow available to common equity after meeting all *operating* expenses,  interest expenses,  taxes,  capital expenditures,  working capital requirements,  net debt repayments,  and preferred dividends and repayments.

## DETERMINING FREE CASH FLOWS

Consider a simple income statement and balance sheet:

## THE INCOME STATEMENT

| The Income Statement                                |
|-----------------------------------------------------|
| Sales                                               |
| - Cost of Goods Sold                                |
| - Selling,   general,   and administrative expenses     |
| - Depreciation and Amortization Expenses            |
| = Earnings Before Interest and Taxes (EBIT)         |
| - Interest Expense                                  |
| = Earnings Before Taxes (EBT)                       |
| - Taxes                                             |
| = Net Income Before Extraordinary Items             |

## THE BALANCE SHEET

| Assets                                    | Liabilities                                    |
|-------------------------------------------|------------------------------------------------|
| Current operating assets                  | Current (non-interest-bearing) operating       |
| (accounts receivable,   operating cash,       | liabilities (accounts payable,   salaries        |
| inventories)                              | payable,   etc.)                                 |
| Fixed Operating Assets (Net property,       | Short-term debt (notes payable,   floating rate  |
| plant,   and equipment)                     | debt,   currently maturing long-term debt)       |
| Other long-term operating Assets          | Long-term debt (long-term bonds,   bank loans)   |
|                                           | Preferred Stock                                |
| Total Assets                              | Common Stock + Equity + Total Liabilities      |

## FREE CASH FLOWS TO THE FIRM (FCFF)

From the simple balance sheet and income statement:

###### FREE CASH FLOWS TO THE FIRM - TOP DOWN

Earnings Before Interest and Taxes (EBIT)

- - Taxes on EBIT (say at 39%)
= Net Operating Profits After Taxes (NOPAT)
- - Depreciation and amortization & other non-cash expenses
- - Capital Expenditures
- - Change in Working Capital (Change in current operating assets - Change in current operating liabilities)
= Free Cash flows to the Firm

Free cash flows to the Firm - Bottom Up

- - Net Income Before Extraordinary Items
- +After-tax interest expense
= Net Operating Profits After Taxes (NOPAT)
- - Depreciation and Amortization & other non-cash expenses
- Capital Expenditures
- Change in Working Capital (Change in current operating assets - Change in current operating liabilities)
= Free Cash Flows to the Firm

$$\text{Net Income} = (EBIT - \text{Interest Expense})*(1 - \text{Tax Rate})$$
$$\text{Net Income} = EBIT*(1 - \text{Tax Rate}) - \text{Interest Expense}*(1 - \text{Tax Rate})$$
$$\text{Net Income} + \text{Interest Expense}*(1 - Tax Rate)  =  EBIT*(1 - \text{Tax Rate})$$
$$\text{Net Income} + \text{Interest Expense}*(1 - \text{Tax Rate})  =  NOPAT$$
Note that *$$\text{Interest Expense}* \text{Tax Rate}=\text{Interest Tax Shield}$$

## ASSET BASE

Generating The Free Cash Flows To The Firm

- Rearrange the items on the simple balance sheet on page 7 by subtracting current operating liabilities from both sides of the balance sheet.

| Assets                                                 | Liabilities                          |
|--------------------------------------------------------|--------------------------------------|
| Net Operating Working Capital                          | Short-term debt (floating rate debt,   |
| (Current operating assets – Current operating          | currently maturing long-term debt) + |
| liabilities) + Fixed Operating Assets (Net property,     | Long-term debt (long-term bonds,       |
| plant,   and equipment) + Other long-term operating      | bank loans) + Preferred Stock +      |
| assets                                                 | Common Stock +                       |
| = Invested Capital                                     | = Total Investor Funds               |

- *Invested capital* represents the operating assets employed in the *operations* of the business,  which generate NOPAT and the free cash flows to the firm (FCFF).
- The cost of financing through non-interest bearing liabilities like accounts payable is included in the cost of goods sold. How?

## DEFINE GROSS VALUE TO INCLUDE THE VALUE OF NON-INTEREST BEARING LIABILITIES

Gross value = Value of current operating liabilities +
Value of short-term debt +
Value of long-term debt +
Value of preferred stock +
Value of equity

## SUBTRACT NON-INTEREST BEARING LIABILITIES FROM BOTH SIDES

Value (as we define it) = Gross value - Value of (non-interest bearing) current operating liabilities
  = Value of short-term debt + Value of long-term debt + Value of preferred stock + Value of equity

- We implicitly subtract the value of non-interest bearing current operating liabilities from gross value by subtracting their costs through the cost of goods sold in computing free cash flows.

Invested Capital = Book value of short-term debt +
Book value of long-term debt +
Book value of preferred stock +

#### BOOK VALUE OF EQUITY

 We will consider excess cash,  minority interest,  deferred taxes,  good will,  special items and other long-term liabilities soon.

#### FREE CASH FLOWS TO EQUITY (FCFE)

Free cash flows to equity represent the *residual* cash flows to common stockholders after all senior claimants (debt,  preferred stock) are paid off.

## FREE CASH FLOWS TO EQUITY
- - Net Income Before Extraordinary Items
- - Depreciation and Amortization & non-cash expenses
- - Capital Expenditures
- -Change in Working Capital (Change in current operating assets - Change in current operating liabilities)
- -Net Payments of Debt Principal
- - Preferred Dividends & repayments
= Free Cash Flows to Equity

- FCFE represents the source of funds to equity. It can be distributed through dividends,  stock repurchases,  and can also be parked in short-term or long-term marketable securities to preserve financial slack.
- Free cash flows to equity represent capacity to payout while dividends and stock repurchases represent actual payout.
- From the statement of cash flows: FCFE = Cash flow from operations + Cash flow from investing + Cash flow from non-equity financing.

*What if there is no preferred stock?*

- Then,  simply set preferred dividends and repayments equal to zero in our discussion earlier.

*What if there is no interest-bearing debt?*

- Then,  set interest expenses and net debt payments to zero. In this case,  the firm is reduced to what is referred to as an allequity firm,  i.e.,  a firm financed fully by equity.
- For an all-equity firm,  also referred to as an unlevered firm: FCFF = FCFE - After-tax interest and non-operating income (We are yet to introduce non-operating income directly in our discussion).

##### FREE CASH FLOWS TO DEBT (FCFD)
- $$\text{Free Cash Flows to Debt (FCFD)}=\text{Interest Expense} + \text{Net Debt Repayments(net of any new debt issues)}$$
##### FREE CASH FLOWS TO PREFERRED STOCK (FCFP)

$$\text{Free Cash Flows to Preferred Stock (FCFP)}= \text{Preferred Dividends} + \text{Any Retirement of Preferred Stock}$$

## NON-OPERATING ASSETS
- The definition of free cash flow to the firm (FCFF) includes only cash flows from operations.
- It excludes interest income and any other non-operating income.
- How do we deal with non-operating assets such as excess cash,  discontinued operations,  etc?
- The answer is easy given the *value additivity principle.*
- Value of a firm is a sum of the values of its individual assets (divisions,  lines of business,  operating and non-operating assets).

## EXCESS CASH & MARKETABLE SECURITIES

Consider a firm that has significant excess cash in hand in addition to capital invested in its *operations*.

| **Assets**                                     | **Liabilities**                             |
|------------------------------------------------|---------------------------------------------|
| Excess cash                                    | Short-term debt (floating rate debt,          |
|                                                | currently maturing long-term debt)          |
| **Invested Capital**                           | Long-term debt (long-term bonds,   bank loans)|
| Net Operating Working Capital (Current         | Preferred Stock                             |
| operating assets – Current operating           | (Deferred Tax Liabilities – Deferred Tax    |
| liabilities)                                   | Assets)                                     |
| Fixed Operating Assets (Net property,   plant,   and equipment) + Other long-term operating assets   | Common Stock              |
|   **Total Capital**  | **Total Investor Funds**                    |

As a thumb rule,  depending on the industry,  persistent cash balance over 2% of sales could be considered excess cash not directly related to operations. For practical purposes,  however,  items such as *cash & marketable securities,  * and other shortterm liquid investments may all be treated as *excess cash*. Based on value additivity: Total Firm Value = Total Enterprise Value + Excess cash.

$$Income Statement Table 
\begin{align*}
\text{The Income Statement} \\ \text{Sales} \\ - &\ \text{Cost of Goods Sold} \\ - &\ \text{Selling,   general,   and administrative expenses} \\ - &\ \text{Depreciation and Amortization Expenses} \\ = &\ \text{Earnings Before Interest and Taxes (EBIT)} \\ - &\ \text{Interest Expense} \\ = &\ \text{Earnings Before Taxes (EBT)} \\ - &\ \text{Taxes} \\ = &\ \text{Net Income Before Extraordinary Items} \end{align*}$$


## VALUE OF EXCESS CASH
- Value Of Excess Cash Is Simply Assumed To Be Equal To Its Book Value From The Balance Sheet. Why? Effect Of Excess Cash On The Income Statement
- Excess cash earns interest income,   which appears after interest expense as either interest income or non-operating income.
- Other non-operating assets Investments in long-term bonds and equities of unrelated companies may constitute other non-operating assets.
- We can compute their value by discounting any expected future cash flow from these assets or simply take their market value if available or book value as a last resort.
- However,   be very careful in denoting any asset as a nonoperating asset,   especially,   those that seem to have *recurring* cash flows. These items will appear under "Other long-term assets" and can be identified only by looking at a firm's footnotes.

For brevity,   I will simply use the term "Excess Cash" to refer to all of excess cash and non-operating assets.

## SMUCKER FINANCIAL STATEMENTS FOR FISCAL YEAR 2014
(See Smucker-July 2015 Version 7.0.Xls And 10-K Report)
J.M.Smucker (Sjm) - Income Statement

| Millions - Detail     U.S. Dollars | 2014 |
| ---- | ---- |
|  |  |
| NET SALES | 5692.7 |
| Cost of Goods Sold (includes dep&amort) | 3,  781.7 |
| GROSS PROFIT | 1911.0 |
| Selling,   General and Admin Expenses | 1,  031.3 |
| Other Operating Expenses | (2.1) |
| OPERATING INCOME AFTER Dep & Amort.(EBIT) | 881.8 |
| Interest Expense | 79.9 |
| Non-Operating Income and Special Items (Expense)* | (278.9) |
| Non-Operating Income (Expense) | 4.2 |
| Special Items (Expense) | (283.1) |
| PRETAX INCOME | 523.0 |
| Total Income Taxes | 178.1 |
| Effective Tax Rate (%) (total income taxes/pre-tax income) | 34.1% |
| Less: Minority Interest | 0.0 |
| NET INCOME before extraordinary items | 344.9 |
|  |  |
| Extraordinary Items & Discontinued Operations | 0.0 |
| NET INCOME after extraordinary items |  |
| 344.9 |  |
|  |  |

- Includes interest income as well as special items.

## SPECIAL ITEMS ARE WHAT CAPIQ CALLS AS UNUSUAL ITEMS. J.M.SMUCKER - BALANCE SHEET

Dr. Bhaskaran Swaminathan,   PhD

| Millions - Detail     U.S. Dollars | 2014 |
| ---- | ---- |
| ASSETS |  |
| Cash | 125.6 |
| Net Receivables | 430.1 |
| Inventories | 1,  163.6 |
| Other Current Assets* | 333.0 |
| CURRENT ASSETS | 2,  052.3 |
| Gross Property,   Plant & Equipment | 2,  699.1 |
| Less: Accumulated Depreciation | 1,  020.8 |
| Net Property,   Plant & Equipment | 1,  678.3 |
| Good Will & Other Intangibles | 12,  960.1 |
| Other Long-Term Assets | 191.9 |
| TOTAL ASSETS | 16,  882.6 |
|  |  |
| LIABILITIES AND EQUITY |  |
| Short-Term Debt | 226.0 |
| Accounts Payable | 402.8 |
| Income Taxes Payable | 0.0 |
| Other Current Liabilities | 393.8 |
| CURRENT LIABILITIES | 1,  022.6 |
| Long-Term Debt | 5,  944.9 |
| Deferred Taxes | 2,  473.3 |
| Other Liabilities | 354.9 |
| Minority Interest** | 0.0 |
| TOTAL LIABILITIES | 9,  795.7 |
| Preferred Stock (Carrying Value) | 0.0 |
| Common Stock + Capital Surplus | 6,  037.6 |
| Retained Earnings | 1,  049.3 |
| Less: Treasury Stock | 0.0 |
| COMMON EQUITY | 7,  086.9 |
| TOTAL LIABILITIES AND EQUITY | 16,  882.6 |

- - Mostly deferred income taxes.
Since 2009,   FAS 160 places minority interest under stockholder equity.

## J.M.SMUCKER - STATEMENT OF CASH FLOWS

| Millions - Detail     U.S. Dollars       | 2014      |
|------------------------------------------|-----------|
| OPERATIONS (Outflows --,   Inflows +)      |           |
| Net Income before Extraordinary Items    | 344.9     |
| Depreciation,   Depletion and Amortization | 268.4     |
| Deferred Taxes and Investment Tax Credit | 7.7       |
| Other Funds                              | 198.3     |
| Net Change in Operating Assets & Liab    | (86.1)    |
| Extraordinaries                          | 0.0       |
| NET CASH FLOW FROM OPERATIONS            | 733.2     |
| INVESTMENTS (Outflows --,   Inflows +)     |           |
| Capital Expenditures                     | (247.7)   |
| Disposal of Fixed Assets & Investments   | 2.6       |
| Acquisitions net of Divestitures         | (1,  320.5) |
| Other Investing Activities               | (30.1)    |
| NET CASH FLOW FROM INVESTING             | (1,  595.7) |
| FINANCING (Outflows --,   Inflows +)       |           |
| Cash Common Dividends                    | (254.0)   |
| Cash Preferred Dividends                 | 0.0       |
| Change in Current Debt                   | (22.4)    |
| Change in Long-Term Debt                 | 1,  188.6   |
| Change in Common and Preferred Stock     | (23.5)    |
| Other Financing Activities               | (25.5)    |
| NET CASH FLOW FROM FINANCING             | 863.2     |
| Exchange Rate Effect                     | (28.6)    |
| INCREASE (DECREASE) IN CASH              | (27.9)    |

## SMUCKER HISTORICAL FREE CASH FLOWS
J.M.Smucker Historical Free Cash Flows (Nmn Means Not Meaningful Number) (Based On The Income Statement And The Statement Of Cash Flows)

| Millions - Detail     U.S. Dollars | 2014 |
| ---- | ---- |
| Free Cash Flows to the Firm: Top Down Approach |  |
|  |  |
| Earnings Before Interest and Taxes (EBIT) | 881.8 |
| Less: Taxes on EBIT (accounting taxes - change in deferred taxes) | 292.6 |
| Estimate Accounting Taxes on EBIT (EBIT * effective tax rate) | 300.3 |
| Estimate change in deferred income taxes (non-cash taxes) | 7.7 |
| Net Operating Profits After Taxes,   NOPAT | 589.2 |
| Add: Depreciation,   amortization,   and other non-cash operating expenses | 466.7 |
| Less: Net Change in Working Capital | 86.1 |
| Less: Net Capital Expenditures & Acquisitions** | 1,  565.6 |
| Free Cash Flows to the Firm (FCFF) | (595.8) |
| Free Cash Flows to the Firm: Bottom Up Approach |  |
| Net Income Before Extraordinary Items | 344.9 |
| Add: Change in deferred income taxes (non-cash taxes) | 7.7 |
| Adjusted Net Income Before Extraordinary Items | 352.6 |
| Add: Minority Interest (adjusted for any dividends paid) | 0.0 |
| Add: After-Tax Interest Expense | 52.7 |
| Less: After-Tax Interest Income | 0.0 |
| Less: After-Tax Non-operating Income and special items | (183.9) |
| Net Operating Profits After Taxes,   NOPAT | 589.2 |
| Add: Depreciation,   amortization,   and other non-cash operating expenses | 466.7 |
| Less: Net Change in Working Capital | 86.1 |
| Less: Net Capital Expenditures & Acquisitions** | 1,  565.6 |
| Free Cash Flows to the Firm (FCFF) | (595.8) |
| Capacity to pay all investors (FCFF/NOPAT) | -101.1% |
| Capacity to pay all investors - 10 year mean | 54.4% |
| Check top down FCFF and bottom up FCFF are the same (difference) | 0.0 |

| **Free Cash Flows to Equity**                    | **2014**     |
|--------------------------------------------------|--------------|
| Net Income Before Extraordinary Items            | 344.9        |
| Add: Change in deferred income taxes             | 7.7          |
| Adjusted Net Income Before Extraordinary Items   | 352.6        |
| Add: Depreciation,   amortization,   and other       | 466.7        |
| non-cash operating expenses                      |              |
| Less: Net Change in Working Capital              | 86.1         |
| Less: Net Capital Expenditures & Acquisitions    | 1,  565.6      |
| Less: Net Debt Principal Repayment               | (1,  166.2)    |
| Less: Preferred Dividends Plus Retirements       | 0.0          |
| **Free Cash Flows to Equity (FCFE)**             | 333.8        |
| **Capacity to pay out equity**                   | 96.8%        |
| **Free Cash Flows to Debt (FCFD)(interest + net repayment) **               | (1086.3)  |
|                                                  |                    |
| **Free Cash Flows to Preferred Stock (FCFP)**    |      0.0                                 |
|                                                  |                |
|  | **2014**  |
|                         **Common Dividends Paid & Net Stock Repurchased**                          | 277.5     |
|                                                   |   10 Year Mean                |
| **Capacity to payout to shareholders(FCFE/Adjusted Net Income)**            | **$113.5\%$** |
| **Actual Payout Ratio${} \frac{(\text{dividends} + \text{stock repurchase})}{\text{Adjusted net income}} {}$**                           | **$101.0\%$** |
|                                                   |                   |

Note That For This Firm,   Actual Payout Closely Tracks The Capacity To Payout.
- - The tax shields,   after-tax interest expenses,   after-tax interest income,   etc.,   are based on the *effective tax rate* which is the ratio of income taxes to earnings before taxes. ** - This comes from the statement of cash flows. I exclude "Other investing activities."

## COMPUTING COMPONENTS OF FREE CASH FLOWS
#### CAPITAL EXPENDITURES
- Capital Expenditures Include All New And Replacement Property,   Plant,   And Equipment,   Acquisitions,   And Other Operating Investments.
- They Can Be Obtained In One Of Two Ways:
- a) If We Are Computing Free Cash Flows From Historical statements,   then capital expenditures can be obtained directly from *the statement of cash flows* from the section on investments. Make sure that you include only operating investments.
- b) If statement of cash flows are not available,   capital expenditures can be computed as = Change in net fixed assets
(NPPE) + depreciation & amortization.

#### DEPRECIATION & AMORTIZATION
- Depreciation expenses are often buried among cost of goods sold (COG) and selling,   general,   and administrative expenses
(SG&A). The only way to get them is from the statement of cash flows.

Change in operating working capital
- It is the difference between change in all current operating assets (including any operating cash) and the change in all current operating liabilities.$$\Delta WC = \Delta  \text{Current Assets}- \Delta \text{Current Liabilities}$$
- Current operating assets include accounts receivables,   inventories,   etc. Current operating liabilities include accounts payable,   taxes payable (which is different from deferred income taxes),   etc.

#### CHANGES IN WORKING CAPITAL: BALANCE SHEET OR STATEMENT OF CASH FLOWS?

- The change in working capital items taken from the statement of cash flows would not necessarily match the changes computed directly from the balance sheet.
- The numbers from the statement of cash flows are more accurate.
- Therefore,   for historical analysis,   use the numbers from the statement of cash flows.
- When you project future pro-forma statements,   the two items would match by construction (we will discuss this later).

#### EFFECTIVE TAX RATE
- Refers to the ratio of income taxes provided on the income statement to pre-tax income (earnings before taxes (EBT)) from historical statements (Taxes/EBT).

#### TAXES ON EBIT
- Income statements report taxes based on earnings before taxes
(EBT) not based on EBIT. Therefore,   we have to compute taxes on EBIT as follows:
Taxes on EBIT = Provision for Income Taxes from Income Statement. + Tax shield from interest expense (effective tax rate*interest expense)
- Tax on Interest Income.
- Tax on non-operating income at the effective tax rate.
- An easier approach is to multiply the EBIT by the effective tax rate:
- Taxes on EBIT = Effective tax rate * EBIT

## DEFERRED INCOME TAXES

- Taxes reported in financial statements and taxes paid to the government are not the same. Why? Different rules.
- For computing free cash flows,   only taxes paid to the government are relevant.
- Difference between taxes reported in financial statements and taxes paid to government gives rise to *deferred taxes*.
- Use *deferred taxes* to back out the taxes paid to government.

## DEFERRED TAX LIABILITIES

- Taxes paid to government *less than* taxes reported in financial statements → deferred tax liabilities → good tax management
- Accelerated depreciation for tax purposes vs. straight-line depreciation for accounting purposes.
- Like borrowing money from the govt. although there are no legal liabilities.

## DEFERRED TAX ASSETS

- Taxes paid to government *greater than* taxes reported in accounting statements → deferred tax assets → bad tax management
- Certain business entertainment expenses may be deductible for accounting purposes but not for tax purposes.
- This is like lending money to the govt.,   hence an asset.

## COMPUTE CHANGE IN NET DEFERRED INCOME TAXES
- Change In Deferred Tax Liabilities = Deferred tax liabilities (t) - Deferred tax liabilities (t-1)
- An increase is a cash inflow because this is how much we underpaid relative to taxes reported in the financial statements.
 - Change In Deferred Tax Assets = Deferred tax assets (t) - Deferred tax assets (t-1)
 - An increase is a cash outflow because this is how much we overpaid relative to reported taxes.
 - We need to net the inflows and out flows. Therefore,   compute:
- Change In Net Deferred Taxes = Change in deferred tax liabilities - Change in deferred tax assets
- When we have historical statement of cash flows available,   we can obtain the change in deferred income taxes directly from the statement of cash flows (see Smucker EXCEL workbook,   statement of cash flows,   also p0.\1 of this handout).

## ADJUSTING NOPAT AND NET INCOME FOR DEFERRED TAXES
#### TOP DOWN APPROACH

NOPAT = Earnings Before Interest and Taxes (EBIT) - (Taxes on EBIT - Change in net deferred taxes)

#### BOTTOM UP APPROACH
NOPAT = Net Income Before Extraordinary Items
- Change in deferred taxes
- After-tax interest expense
- After-tax interest income
- After-tax non-operating income (if any) [+ Add any minority interest (to be discussed)]

Adjusted Net Income = Net Income Before Extraordinary Items + Change in deferred taxes

## DEFERRED TAXES IN THE MODIFIED BALANCE SHEET

- Deferred taxes are like *quasi-equity* in the sense these funds belong to shareholders until the taxes are paid to the government. Hence,   add them to equity in calculating total investor funds to match invested capital.
- Net Deferred Tax Liabilities = Deferred tax liabilities - Deferred tax assets

| **Assets**                                       | **Liabilities**                         |
|--------------------------------------------------|-----------------------------------------|
| Excess Cash (Cash,   Marketable Securities,   and    | Current (non-interest-bearing) operating|
| Other Short-Term & Long-Term Investments)        | liabilities (accounts payable and other |
|                                                  | accruals)                               |
| Current operating assets (accounts receivable,     | Short-term debt (floating rate debt,      |
| operating cash,   inventories)                     | currently maturing long-term debt)      |
| Fixed Operating Assets (Net property,   plant,   and | Long-term debt (long-term bonds,   bank   |
| equipment)                                       | loans)                                  |
| Other long-term operating assets                 | Deferred Tax Liabilities                |
| Deferred Tax Assets                              | Preferred Stock                         |
| **Total Assets**                                 | Common Stock                            |
|                                                  | **Total Liabilities**                   |

## MODIFIED BALANCE SHEET
- Subtract Current Operating Liabilities & Deferred Tax Assets From Both Sides (Subtracting From Both Sides Ensures That The Modified Balance Sheet Remains In Balance).

| **Assets**                                       | **Liabilities**                         |
|--------------------------------------------------|-----------------------------------------|
| Excess Cash                                      | Short-term debt (floating rate debt,      |
|                                                  | currently maturing long-term debt)      |
| **Invested Capital**                             | Long-term debt (long-term bonds,   bank   |
|                                                  | loans)                                  |
| Net Operating Working Capital (Current operating | Preferred Stock                         |
| assets – Current operating liabilities)          | (Deferred Tax Liabilities – Deferred Tax|
| Fixed Operating Assets (Net property,   plant,   and | Assets)                                 |
| equipment)                                       | Common Stock (Including Minority Interest) |
| Other long-term operating assets                 |                                         |
| Good Will                                        |                                         |
| **Total Capital**                                | **Total Investor Funds**                |

We should treat net deferred tax liabilities as *quasi-equity* and add it to common stock in computing book value of equity.

## GOODWILL
- Goodwill is an asset on the balance sheet that represents the price premiums paid for acquisitions over the *market value* of their net tangible assets.

What does good will represent?
- Intangible assets such as brand name (say Coco Cola or Pepsi brand name) and any synergies.
- Overpayment (due to winner's curse).

Goodwill unlike other fixed assets does not wear out on a regular basis and does not need to be replaced on a regular basis. FASB rules SFAS 141 & 142 recognize this concern and require goodwill to be written down only when it gets *impaired*.

- Impairment is determined by a set of complex accounting rules and may be triggered by a drop in the firm's market value. If there is no impairment,   goodwill is kept at its original amount on the balance sheet.
- Until 2001,   the goodwill asset was amortized mechanically on a straight-line basis over a 40-year period.
- Historical statements prior to 2001 should be adjusted to *undo* the impact of goodwill amortization on the financial statements since it is a non-cash expense.

## ORIGINAL BALANCE SHEET WITH GOOD WILL

| **Assets**                                       | **Liabilities**                         |
|--------------------------------------------------|-----------------------------------------|
| Excess Cash                                      | Short-term debt (floating rate debt,      |
|                                                  | currently maturing long-term debt)      |
| **Invested Capital**                             | Long-term debt (long-term bonds,   bank   |
|                                                  | loans)                                  |
| Net Operating Working Capital (Current operating | Preferred Stock                         |
| assets – Current operating liabilities)          | (Deferred Tax Liabilities – Deferred Tax|
| Fixed Operating Assets (Net property,   plant,   and | Assets)                                 |
| equipment)                                       | Common Stock (Including Minority Interest) |
| Other long-term operating assets                 |                                         |
| Good Will                                        |                                         |
| **Total Capital**                                | **Total Investor Funds**                |

| **Assets**                                     | **Liabilities**                             |
|------------------------------------------------|---------------------------------------------|
| Excess Cash (Cash,   Marketable Securities,   and  | Current operating (non-interest bearing)    |
| Other Short-Term & Long-Term Investments)      | liabilities (accounts payable and other     |
|                                                | accruals)                                   |
| Current operating assets (accounts receivable,   | Short-term debt (floating rate debt,          |
| operating cash,   inventories)                   | currently maturing long-term debt)          |
| Fixed Operating Assets (Net property,   plant,     | Long-term debt (long-term bonds,   bank loans)|
| and equipment)                                 | Deferred Tax Liabilities                    |
| Other long-term operating assets               | Preferred Stock                             |
| Deferred Tax Assets                            | Common Stock                                |
| Good Will                                      | **Total Liabilities**                       |
| **Total Assets**                               |                                             |

## ACCOUNTING FOR INVESTMENTS IN OTHER COMPANIES
- If company A invested in another company B,   the accounting method used,   in general,   depends on the percentage of the voting stock A owns.

| A’s ownership of B | Accounting Method Used by A | A’s income Statement | A’s balance Sheet | A’s Cash Flow Statement | Comments |
|--------------------|-----------------------------|----------------------|-------------------|-------------------------|----------|
| < 20%              | Cost                        | Any dividends from B included in other income below EBIT of A. A’s share of B’s earnings not reported. | Investment is a long-term asset under “Other long-term assets” at cost. | No effect | The asset is most likely operating; dividend income is also operating. |
| 20% to 49%         | Equity                      | A reports 30% of B’s income below EBIT as “Equity earnings (losses) of unconsolidated affiliates.” | The investment is a long-term asset under “Other long-term assets.” Book or fair market value | The portion of income that is non-cash is deducted in the Operating section. Depends on any dividends from B to A. | Earnings should and usually be operating. |
| >= 50%             | Consolidated                | A consolidates B’s income statement in its own income statement. The income that belongs to minority owners of B is deducted as “Minority interest” below EBIT. | A includes all of B’s assets and liabilities on its own balance sheet. The 20% owned by others is shown as “Minority Interest” under equity. | The minority earnings deduction is non-cash and added back. Any dividends paid to minority shareholders offset the deduction. | Since 2008/2009 minority interest is reported separately under shareholder’s equity and not under liabilities. See SFAS 160. |

## MODIFIED BALANCE SHEET WITH MINORITY INTEREST
- Subtract current operating liabilities and deferred tax assets from both sides.

| **Assets**                                       | **Liabilities**                         |
|--------------------------------------------------|-----------------------------------------|
| Excess Cash                                      | Short-term debt (floating rate debt,      |
|                                                  | currently maturing long-term debt)      |
| **Invested Capital**                             | Long-term debt (long-term bonds,   bank   |
|                                                  | loans)                                  |
| Net Operating Working Capital (Current operating | Preferred Stock                         |
| assets – Current operating liabilities)          | (Deferred Tax Liabilities – Deferred Tax|
| Fixed Operating Assets (Net property,   plant,   and | Assets)                                 |
| equipment)                                       | Common Stock (Including Minority Interest) |
| Other long-term operating assets                 |                                         |
| Good Will                                        |                                         |
| **Total Capital**                                | **Total Investor Funds**                |

Things to keep in mind on subsidiary accounting
- If you add "equity in earnings of unconsolidated affiliates" to
operating income,   remember to add the assets corresponding to that income to operating assets. Be consistent in your treatment of income and assets.
- In computing free cash flows,   remember to subtract any noncash income (recall other non-cash expenses in our free cash
flow definition,   just as you add other non-cash expenses,   you must subtract non-cash income). Thus,   if you add "equity in earnings" to operating income,   remember to subtract any noncash portion from the free cash flows. This may not be easy to sort out from the financial statements (see footnotes).
- For fully consolidated statements,   remember that the minority
interest deduction in the income statement is most likely a non-cash expense. The statement of cash flows would add it back,   net of any dividend distribution to minority shareholders. A dividend distribution to minority shareholders reduces the operating cash flows available to majority shareholders.
- The consolidation accounting is careful in delineating income
and equity attributable to minority and majority interests but not so when it comes to operating cash flows. There is no reporting consistency in the dividends paid to minority interest and in some instances they are not even reported on the statement of cash flows (Mulford and Dar,   2012). Thus,   it is hard to determine how much of the operating cash flows belong to minority interest.

## SPECIAL ITEMS

- These represent unusual or non-recurring items reported
above taxes and below EBIT by the company.
- This is not a description used by the company or GAAP.
- This is a description used by analysts and databases such as
Compustat and CapIQ. Analysts remove special items in comparing earnings across periods.
- This is to be distinguished from *extraordinary items*,   which
is a GAAP item reported below Net Income Before
Extraordinary Items.
- Special items typically consist of:
o Impairment of goodwill o Gain (Loss) on sale of Assets o Insurance settlements and legal settlements o Restructuring charges o Other unusual items.
- The default assumption is that we should treat them as nonoperating unless otherwise they are recurring and
predictable.
- These items do not affect the top-down approach to
computing FCFF since they appear below EBIT. They do affect the bottom-up approach.
- You may not want to include them in computing FCFE
either.

## LONG-TERM OPERATING LIABILITIES

- *Pension liabilities* arise from defined benefit plans in terms
of what the firms owes its employees in the future. There is a lot of complicated actuarial accounting associated with estimating these items. SFAS 158 requires reporting of net pension liabilities (if underfunded) and assets (if overfunded).
- *Post-retirement obligations* consist of the present value of
post-retirement healthcare and welfare benefits and are distinct from pension liabilities.
- Unlike interest-bearing debt and lease obligations they are
not financial liabilities but *long-term operating liabilities*
created by the operations of the company.
- The interest expenses associated with these liabilities are
part of the pension expenses and post-retirement benefit expenses (just like the interest cost on accounts payable) and are,   therefore,   included in operating expenses.
- Therefore,   just like we subtracted accounts payable in
computing net working capital,   we also should subtract
these operating liabilities from operating assets.
- However,   for calculations to *evaluate credit risk*,   we should
include them in the calculation of debt ratios.
 See the modified balance sheet on the next page.

## MODIFIED BALANCE SHEET WITH LONG-TERM OPERATING LIABILITIES
Subtract Long-Term Operating Liabilities From Both Sides.

Assets Liabilities
Excess cash
Short-term debt (floating rate debt,   currently maturing long-term debt)
Invested Capital
Long-term debt (long-term bonds,   bank loans) Preferred Stock (Deferred Tax Liabilities - Deferred Tax Assets)
Net Operating Working Capital (Current operating Assets - Current operating liabilities)
Fixed Operating Assets (Net property,   plant,   and equipment)
Common Stock (Including Minority Interest)
Other long-term operating assets Less: long-term operating liabilities Good Will Total Capital
Total Investor Funds

How to estimate invested capital?

From the previous page: Invested Capital
Short-term debt + Long-term debt

|     |      |     |     |     | + Book value of preferred stock        |
|-----|------|-----|-----|-----|----------------------------------------|
|     |      |     |     |     | + (Deferred tax liabilities - Deferred |
|     |      |     |     |     |                                        |
|     |      |     |     |     | + Book value of common stock           |
|     |      |     |     |     | including minority interest]           |
|     |      |     |     |     | - Excess cash                          |

 This is useful if you are writing code to compute IC from databases such as Compustat or CapIQ. It is also the difference between operating assets and operating liabilities.

 Invested Capital =
Operating Assets - Operating Liabilities

 Operating Assets =
Total Assets - Excess Cash
- Deferred tax assets Operating Liabilities =
Total Assets - Total Debt - Book Value
Common and Preferred stock - Minority Interest - Deferred tax liabilities

 Note that my use of the term "Excess Cash" also includes all non-operating assets.

Equity Equivalents

Note that net deferred income taxes is like quasi-equity in the sense including it in book value of equity provides a better measure of the equity capital.

Therefore,   the *adjusted book value* of equity is: =
Book Value of Equity from the balance sheet
- Net deferred income taxes

The *adjusted net income* definition consistent with the adjusted book value of equity is:
Net Income Before Extraordinary Items

- Change in deferred income taxes

There are other items that could be added to the equity equivalents (see pages 145-147 of the text book):

- Minority interest (which is now under book equity).
- Equity portion of hybrid securities such as convertible debt
or convertible preferred.

## THINGS TO KEEP IN MIND

- Whether an item is operating or non-operating depends on a
subjective analysis of the operations of the particular firm. Refer to 10-K reports and footnotes in financial statements in making these judgments.
- In the same vain,   when you cannot clearly determine whether
a balance sheet or an income statement item is operating or
non-operating just make an assumption and consistently follow that assumption in your calculations.
- Apply the "*who cares rule".* If an item such as deferred taxes
or non-operating income is too small to be material in your calculations,   you might as well just ignore them. It may not be worth your time to figure out the exact numbers and their effects.

##

The EXCEL workbook Smucker-July 2015 version 7.0.xls contains various worksheets that can be used as templates for the valuation exercises you will perform with Boeing.