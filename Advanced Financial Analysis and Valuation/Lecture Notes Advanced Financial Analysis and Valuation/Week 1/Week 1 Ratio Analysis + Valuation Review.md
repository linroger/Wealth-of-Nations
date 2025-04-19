---
title: Week 1 Ratio Analysis + Valuation Review
cssclasses:
  - academia
tags:
  - dividend_discount_model
  - enterprise_valuation
  - equity_valuation
  - free_cash_flow
  - ratio_analysis
  - roic
  - valuation
  - wacc
aliases:
  - DCF
  - DDM
  - Valuation Methods
  - Week 1 Review
key_concepts:
  - Discount rate components
  - Dividend discount model
  - Enterprise DCF process
  - Enterprise vs equity models
  - Free cash flow
  - NOPAT and FCF
  - Operating vs investing items
  - ROE decomposition
  - ROIC operational efficiency
  - ROIC vs ROA
  - Valuation basics
---

# Week 1 Ratio Analysis + Valuation Review

[[Week 1 Ratio Analysis + Valuation Review|Ratio Analysis]]

[Week 1 Introduction](Zhe/Week%201/Week%201%20Introduction.md)

[Week 1 Market Efficiency](Zhe/Week%201/Week%201%20Market%20Efficiency.md)

[Week 1 Ratio Analysis + Valuation Review](Zhe/Week%201/Week%201%20Ratio%20Analysis%20+%20Valuation%20Review.md)

## RATIO ANALYSIS REVIEW

We can decompose ROE,  a common profitability measure,  into operating and financing parts. We use ROIC rather than the more traditional ROA:

 ![500](47f6500fe5d8755b4df15b4982060e45.png)

- ROIC captures only operating items whereas ROA commingles operating and non-operating
	- E.g.,  [[Operating Income vs. Net Income What's the Difference|Net Income]] (ROA's numerator) includes both sales revenue (operating) and gains on trading securities (non-operating)
	- E.g.,  total assets (ROA's denominator) includes both inventory (operating) and excess cash and marketable securities (non-operating)
 ![500](f74f105527ff6562e1a3c4a125c50e21.png)

## USING ROIC

Using ROIC means reclassifying items in the balance sheet and income statement as operating or investing.

 ![500](34cc6de96cecefe0792bf378a3304df2.png)

 ![500](28e623f0c852fc77c1da480e48501bd0.png)

### RECLASSIFICATION PROCESS
- Operating items are part of the company's core business and affect the NOPAT.
- Investing items are related to how the business finances its operations and growth.
 ![500](f0cb236942d39633b9810a12b6fc3aa2.png)
### ROIC DEEP DIVE
A detailed look into ROIC can provide insights into a firm's operational efficiency and profitability.
You can also take a deeper dive into ROIC
 ![500](7b42d00a60d7036264e3148ecb368471.png)
---

- UPS’ ROIC advantage over FedEx comes from advantages in both [[Operating Margin]] and turnover
- On margin,  UPS’ benefit is driven by higher reliance on labor (higher compensation/revenues) but lower reliance on equipment (lower purchased transportation/revenues,  lower fuel/revenues)
- UPS also has better capital efficiency (invested capital turnover)

**Decomposing ROIC:**

$$ \text{Return on Invested Capital (ROIC)} = \frac{\text{NOPAT}}{\text{Avg. Invested Capital}} $$

$$ \text{NOPAT} = \text{NI} + (1 - \text{t}) * \text{Interest} $$

$$ \text{ROIC} = \text{Post-tax Operating Profit Margin} \times \text{Invested Capital Turnover} $$

$$ \text{Post-tax Operating Profit Margin} = \frac{\text{NOPAT}}{\text{Revenue}} $$

$$ \text{Invested Capital Turnover} = \frac{\text{Revenue}}{\text{Avg. Invested Capital}} $$

$$
\begin{array}{|l|l|}
\hline
\textbf{Ratio} & \textbf{Definition} \\ \hline
\text{Return on equity (ROE)} & \frac{\text{Net income available for common}}{\text{Avg. common shareholders' equity}} \\ \hline
\text{Return on invested capital (ROIC)} & \frac{\text{NOPAT}}{\text{Avg. invested capital}} \\ \hline
\text{Return on newly invested capital (RONIC)} & \frac{\text{NOPAT}_{t+1} - \text{NOPAT}_{t}}{\text{Invested capital}_{t+1} - \text{Invested capital}_{t}} \\ \hline
\text{Invested capital turnover} & \frac{\text{Revenue}}{\text{Avg. invested capital}} \\ \hline
\text{Total asset turnover} & \frac{\text{Revenue}}{\text{Avg. total assets}} \\ \hline
\text{Fixed asset turnover} & \frac{\text{Revenue}}{\text{Avg. fixed assets}} \\ \hline
\text{Net operating profit after tax (NOPAT) margin} & \frac{\text{Operating income (or EBIT)} \times (1-\text{tax rate})}{\text{Revenue}} \\ \hline
\text{Days sales outstanding} & \frac{\text{Accounts receivable}}{\text{Revenue} / 365} \\ \hline
\text{Days payables outstanding} & \frac{\text{Accounts payable}}{\text{COGS} / 365} \\ \hline
\text{Inventory turns} & \frac{\text{COGS}}{\text{Avg. inventory}} \\ \hline
\end{array}
$$

## VALUATION REVIEW

### VALUATION BASICS

$$V_0=\sum_{t=1}^\infty\frac{Projected\textit{ Future Payoffs}_t}{(l^2+Discount\text{ Rate})^t}$$

1. Value today (i.e.,  t = 0)
1. "Flows" expected to be received in the future
	- May be received in one lump sum,  in a constant stream,  or in different amounts each year
1. Discount rate applied to future flows,  representing:
	- Time value of money
		 - Consumption tomorrow instead of consumption today
		 - Constant rate for all assets
	- Risk of the flows
		 - Varies by type of flow (capital)

### VALUATION BASICS: DIVIDEND DISCOUNT MODEL ("DDM")

- In theory,  the dividend discount model is what underpins value:
-  ![500](179280fa1e69d0ab1dd2e546a4d10037.png)
- However,  the DDM's usefulness relies heavily on the ability to forecast future dividends
	- Dividends are chosen by management and many companies do not pay dividends
	- In practice,  we rarely use the DDM

### OVERVIEW OF COMMON VALUATION METHODS

Instead,  we use measures of flows between the firm and the market (s),  e.g.,  free cash flow,  because these flows can be better estimated than dividends.

 ![500](7856be1646d7babb6998471a3a86b2eb.png)

## ENTERPRISE VS. EQUITY METHOD VALUATION

- Enterprise valuation models value the flows (cash flows,  earnings,  etc.) due to all investors (i.e.,  both equity and debt holders)
- Equity valuation models value the flows due to equity holders only
- The two models can be bridged by:
 ![500](af5232b5117c85953567b0f598017104.png)
## ENTERPRISE DCF REVIEW

- This model discounts **free cash flow** (i.e.,  cash flow generated by business operations - less any reinvestment back into the business - that is available to all investors) at the weighted average cost of capital (i.e.,  a blend of the cost of debt and the cost of equity)
- Ideally used to value companies that will maintain their capital structure at a target leverage ratio
 ![500](1ff37736d5e1f2021817ce23373bace1.png)
### FOUR-PART PROCESS

1. **Free Cash Flow ("FCF")**
	- Forecast operating line items and line items affecting invested capital
	- Calculate net operating profit after tax ("NOPAT") and changes to invested capital
	- Calculate projected FCF

	> Note: McKinsey valuation book uses net operating profit less adjusted taxes ("NOPLAT"),  which 1) adjusts for cash taxes on [[Operating Income vs. Net Income What's the Difference|Operating Income]] and 2) treats deferred taxes as non-operating items. NOPAT treats deferred taxes as operating,  but as long as tax expense and deferred taxes are treated consistently,  using NOPAT vs NOPLAT leads to the same results.

1. **Discounting**
	- Calculate the present value of FCFs in the explicit forecast period by discounting the forecasted FCFs with WACC
	- Apply a mid-year adjustment to the PVs as appropriate

1. **Continuing Value**
	- Continuing value represents the value of the firm's FCFs after the explicit forecast period
	- It is typically a perpetuity
	- With growth & reinvestment,  continuing value is defined as:

	$$\frac{FCF_{T+1}}{WACC - g}$$

	Where

	 - $FCF_{T+1}$ is the FCF in the first year after the explicit forecast period
	 - $WACC$ is the weighted average cost of capital
	 - $g$ is the long-term growth rate
	- Further discounted by WACC to determine present value of continuing value

1. **Equity Value Calculation**
	- Sum the present values of the forecasted FCFs and the continuing value
	- (+) the present value of non-operating assets (e.g.,  equity investments) if applicable
	- (-) net debt (debt and debt equivalents minus cash and cash equivalents)
	- (-) the value of preferred stock and noncontrolling interest if applicable
	- Estimated price per share = equity value divided by the number of shares outstanding

---

## ENTERPRISE DCF REVIEW (CONT.) FREE CASH FLOW ("FCF")

At a high level,  free cash flow is calculated as:

$$\text{FCF} = \text{NOPAT} + \text{D\&A} - \text{increase in non-cash WC} - \text{capital expenditures} - \text{other adjustments to invested capital}$$

-  ![500](e629d3668bd30ab52c13c33d6bfada65.png)

---

## ENTERPRISE DCF REVIEW (CONT.)

 ![500](282fb15410f651458c418eaca129f629.png)

 ![500](3833f246a0c8fadd2ae41e7a46d704eb.png)

### ECONOMIC PROFIT MODEL REVIEW

 ![500](d0c3566e553d142cc0f34904f31461b8.png)

 ![500](d29b0d36e48ca034d4ab093e93bbe7b7.png)

 ![500](51a13933fd8986a1e9d83e9dff72159e.png)

 ![500](f1ac6f299ac7edc54dff342011d520a0.png)

### DISCOUNTING

- Calculate the present value of FCFs in the explicit forecast period by discounting the forecasted FCFs with WACC:

$$PV_{FCF} = \sum_{t=1}^T \frac{FCF_t}{(1+WACC)^t}$$

Where:

- $D$ and $E$ are measured using market values where possible
- $K_d$ represents the cost of debt
- $K_e$ represents the cost of equity
- $T_m$ represents the marginal tax rate,  which is used to value the interest tax shield

### CONTINUING VALUE
- Continuing value represents the value of the firm's FCFs after the explicit forecast period
- It is typically a perpetuity
- With growth & reinvestment,  continuing value is defined as:

$$CV = \frac{FCF_{T+1}}{WACC - g}$$

Where:

- $FCF_{T+1}$ is the FCF in the first year after the explicit forecast period
- $WACC$ is the weighted average cost of capital
- $g$ is the long-term growth rate
- $RONIC$ represents the return on new invested capital
- Further discounted by WACC to determine present value of continuing value
- Apply a mid-year adjustment to the PVs as appropriate
## ENTERPRISE DCF REVIEW (CONT.) EQUITY VALUE CALCULATION

- Sum the present values of the forecasted FCFs and the continuing value
- (+) the present value of non-operating assets (e.g.,  equity investments) if applicable
- (-) net debt (debt and debt equivalents minus cash and cash equivalents)
- (-) the value of preferred stock and noncontrolling interest if applicable
- Estimated price per share = equity value divided by the number of shares outstanding
