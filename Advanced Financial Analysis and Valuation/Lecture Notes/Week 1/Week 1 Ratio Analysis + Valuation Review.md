---
title: Week 1 Ratio Analysis + Valuation Review
---

[Week 1 Introduction](Week%201%20Introduction.md)
[Week 1 Market Efficiency](Week%201%20Market%20Efficiency.md)
[Week 1 Ratio Analysis + Valuation Review](Week%201%20Ratio%20Analysis%20+%20Valuation%20Review.md)

## RATIO ANALYSIS REVIEW

We can decompose ROE, a common profitability measure, into operating and financing parts. We use ROIC rather than the more traditional ROA:
![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201307298.png)

- ROIC captures only operating items whereas ROA commingles operating and non-operating
	- E.g., net income (ROA's numerator) includes both sales revenue (operating) and gains on trading securities (non-operating)
	- E.g., total assets (ROA's denominator) includes both inventory (operating) and excess cash and marketable securities (non-operating)
![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201338763.png)

## USING ROIC

Using ROIC means reclassifying items in the balance sheet and income statement as operating or investing.
![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201452441.png)

![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201711193.png)

### RECLASSIFICATION PROCESS
- Operating items are part of the company's core business and affect the NOPAT.
- Investing items are related to how the business finances its operations and growth.
![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201732949.png)
### ROIC DEEP DIVE
A detailed look into ROIC can provide insights into a firm's operational efficiency and profitability.
You can also take a deeper dive into ROIC
![500](Advanced%20Financial%20Analysis%20and%20Valuation%20Lecture%20Notes-20240419201757910.png)
---

- UPS’ ROIC advantage over FedEx comes from advantages in both operating margin and turnover
- On margin, UPS’ benefit is driven by higher reliance on labor (higher compensation/revenues) but lower reliance on equipment (lower purchased transportation/revenues, lower fuel/revenues)
- UPS also has better capital efficiency (invested capital turnover)

**Decomposing ROIC:**

$$ \text{Return on Invested Capital (ROIC)} = \frac{\text{NOPAT}}{\text{Avg. Invested Capital}} $$

$$ \text{NOPAT} = \text{NI} + (1 - \text{t}) * \text{Interest} $$

$$ \text{ROIC} = \text{Post-tax Operating Profit Margin} \times \text{Invested Capital Turnover} $$

$$ \text{Post-tax Operating Profit Margin} = \frac{\text{NOPAT}}{\text{Revenue}} $$

$$ \text{Invested Capital Turnover} = \frac{\text{Revenue}}{\text{Avg. Invested Capital}} $$

| Ratio                                         | Definition                                                                                                    |     |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | --- |

| Return on equity (ROE)                        | $$\frac{\text{Net income available for common}}{\text{Avg. common shareholders' equity}}$$

                    |     |

| Return on assets (ROA)                        | $$\frac{\text{Net income + (interest expense} \times \text{(1-tax rate))}}{\text{Avg. total assets}}$$

        |     |

| Return on invested capital (ROIC)             | $$\frac{\text{NOPAT}}{\text{Avg. invested capital}}$$

                                                         |     |

| Return on newly invested capital (RONIC)      | $$\frac{\text{NOPAT}_{t+1} - \text{NOPAT}_{t}}{\text{Invested capital}_{t+1} - \text{invested capital}_{t}}$$

 |     |

| Invested capital turnover                     | $$\frac{\text{Revenue}}{\text{Avg. invested capital}}$$

                                                       |     |

| Total asset turnover                          | $$\frac{\text{Revenue}}{\text{Avg. total assets}}$$

                                                           |     |

| Fixed asset turnover                          | $$\frac{\text{Revenue}}{\text{Avg. fixed assets}}$$

                                                           |     |

| Net operating profit after tax (NOPAT) margin | $$\frac{\text{Operating income (or EBIT)} \times \text{(1-tax rate)}}{\text{Revenue}}$$

                       |     |

| Days sales outstanding                        | $$\frac{\text{Accounts receivable}}{\text{Revenue} / 365}$$

                                                   |     |

| Days payables outstanding                     | $$\frac{\text{Accounts payable}}{\text{COGS} / 365}$$

                                                         |     |

| Inventory turns                               | $$\frac{\text{COGS}}{\text{Avg. inventory}}$$

                                                                 |     |

## VALUATION REVIEW

### VALUATION BASICS

$$V_0=\sum_{t=1}^\infty\frac{Projected\textit{ Future Payoffs}_t}{(l^2+Discount\text{ Rate})^t}$$

1. Value today (i.e., t = 0)
2. "Flows" expected to be received in the future
	- May be received in one lump sum, in a constant stream, or in different amounts each year
3. Discount rate applied to future flows, representing:
	- Time value of money
		 - Consumption tomorrow instead of consumption today
		 - Constant rate for all assets
	- Risk of the flows
		 - Varies by type of flow (capital)

### VALUATION BASICS: DIVIDEND DISCOUNT MODEL ("DDM")

- In theory, the dividend discount model is what underpins value:
- ![](Z.%20Clippings/duction-20240430070400507.png)
- However, the DDM's usefulness relies heavily on the ability to forecast future dividends
	- Dividends are chosen by management and many companies do not pay dividends
	- In practice, we rarely use the DDM

### OVERVIEW OF COMMON VALUATION METHODS

Instead, we use measures of flows between the firm and the market (s), e.g., free cash flow, because these flows can be better estimated than dividends.
![](Z.%20Clippings/Week%201%20Introduction-20240430070424005.png)

## ENTERPRISE VS. EQUITY METHOD VALUATION

- Enterprise valuation models value the flows (cash flows, earnings, etc.) due to all investors (i.e., both equity and debt holders)
- Equity valuation models value the flows due to equity holders only
- The two models can be bridged by:
![](Z.%20Clippings/Week%201%20Introduction-20240430070518379.png)
## ENTERPRISE DCF REVIEW

- This model discounts **free cash flow** (i.e., cash flow generated by business operations - less any reinvestment back into the business - that is available to all investors) at the weighted average cost of capital (i.e., a blend of the cost of debt and the cost of equity)
- Ideally used to value companies that will maintain their capital structure at a target leverage ratio
![](Z.%20Clippings/Week%201%20Introduction-20240430070537661.png)
### FOUR-PART PROCESS

1. **Free Cash Flow ("FCF")**
	- Forecast operating line items and line items affecting invested capital
	- Calculate net operating profit after tax ("NOPAT") and changes to invested capital
	- Calculate projected FCF

	> Note: McKinsey valuation book uses net operating profit less adjusted taxes ("NOPLAT"), which 1) adjusts for cash taxes on operating income and 2) treats deferred taxes as non-operating items. NOPAT treats deferred taxes as operating, but as long as tax expense and deferred taxes are treated consistently, using NOPAT vs NOPLAT leads to the same results.

2. **Discounting**
	- Calculate the present value of FCFs in the explicit forecast period by discounting the forecasted FCFs with WACC
	- Apply a mid-year adjustment to the PVs as appropriate

3. **Continuing Value**
	- Continuing value represents the value of the firm's FCFs after the explicit forecast period
	- It is typically a perpetuity
	- With growth & reinvestment, continuing value is defined as:

	$$\frac{FCF_{T+1}}{WACC - g}$$

	Where

	 - $FCF_{T+1}$ is the FCF in the first year after the explicit forecast period
	 - $WACC$ is the weighted average cost of capital
	 - $g$ is the long-term growth rate
	- Further discounted by WACC to determine present value of continuing value

4. **Equity Value Calculation**
	- Sum the present values of the forecasted FCFs and the continuing value
	- (+) the present value of non-operating assets (e.g., equity investments) if applicable
	- (-) net debt (debt and debt equivalents minus cash and cash equivalents)
	- (-) the value of preferred stock and noncontrolling interest if applicable
	- Estimated price per share = equity value divided by the number of shares outstanding

---

## ENTERPRISE DCF REVIEW (CONT.) FREE CASH FLOW ("FCF")

At a high level, free cash flow is calculated as:

$$\text{FCF} = \text{NOPAT} + \text{D\&A} - \text{increase in non-cash WC} - \text{capital expenditures} - \text{other adjustments to invested capital}$$

- ![](Z.%20Clippings/Week%201%20Introduction-20240430065500761.png)

---

## ENTERPRISE .)

!s/Attachments%201/Week%201%20Introduction-20240430070839683.png)

![](Z.%20Clippings/Week%201%20Introduction-20240430070902224.png)

### ECONOMIC PROFIT[](Z.%20Clippings/Week%201%20Introduction-20240430070944839.png)

![](Z.%20Clippings/Week%201%20Introduction-20240430071008690.png)

![](Z.%20Clippings/Week%201%20Introduction-20240430071022323.png)

![](Z.%20Clippings/Attachments%201/Week%201%20Introduction-20240430071040238.png)

### DISCOUNTING

- Calculate the present value of FCFs in the explicit forecast period by discounting the forecasted FCFs with WACC:

$$PV_{FCF} = \sum_{t=1}^T \frac{FCF_t}{(1+WACC)^t}$$

Where:

- $D$ and $E$ are measured using market values where possible
- $K_d$ represents the cost of debt
- $K_e$ represents the cost of equity
- $T_m$ represents the marginal tax rate, which is used to value the interest tax shield

### CONTINUING VALUE
- Continuing value represents the value of the firm's FCFs after the explicit forecast period
- It is typically a perpetuity
- With growth & reinvestment, continuing value is defined as:

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
- (+) the present value of non-operating assets (e.g., equity investments) if applicable
- (-) net debt (debt and debt equivalents minus cash and cash equivalents)
- (-) the value of preferred stock and noncontrolling interest if applicable
- Estimated price per share = equity value divided by the number of shares outstanding
