---
title: "LECTURE NOTE 3 DISCOUNTED CASH FLOW VALUATION: VALUE DRIVERS AND IMPLEMENTING THE FREE CASH FLOW MODEL"
aliases: ["LECTURE NOTE 3 DISCOUNTED CASH FLOW VALUATION: VALUE DRIVERS AND IMPLEMENTING THE FREE CASH FLOW MODEL"]
linter-yaml-title-alias: "LECTURE NOTE 3 DISCOUNTED CASH FLOW VALUATION: VALUE DRIVERS AND IMPLEMENTING THE FREE CASH FLOW MODEL"
---
# LECTURE NOTE 3 DISCOUNTED CASH FLOW VALUATION: VALUE DRIVERS AND IMPLEMENTING THE FREE CASH FLOW MODEL

## OBJECTIVE

Introduce students to a practically implementable three-stage free cash flow valuation model based on analyst earnings forecasts and plowback rates.

# OUTLINE

- Firm valuation based on value drivers: growth,  ROI,  and plowback rate
- Terminal value based on value drivers
- Assets in place and PVGO
- Value drivers and equity valuation

## ECONOMIC VALUE DRIVERS AND FREE CASH FLOWS

- The objective of valuation is to relate firm value to underlying
  economic value drivers.

- We will discuss how to forecast free cash flows in terms of
  some key value drivers and show how these value drivers affect firm value.

- We will develop a simple three-stage free cash flow valuation
  model that can be used to compute total enterprise value (V) and the value of equity (E).

- This approach does not require forecasting income statements,
  balance sheets,  and cash flow statements and can give valuations quite close to that based on full-fledged pro-forma financial statements.

Note that the reference to firm value here is to Total Enterprise Value. You have to add the value of non-operating assets (excess cash,  etc.) to get total firm value.

Some simple formulas of firm (total enterprise) value No growth case: The _total enterprise value of a firm_ whose profits are expected to be constant in perpetuity is equal to:

$$V_{0}=\frac{NOPAT_{1}}{WACC}\tag{1}$$

where NOPT$_1$is the constant expected profits (equal to the free cash flows) in perpetuity and WACC is the weighted average cost of capital. This is also referred to as the _Earnings Power Value (EPV)_.

Constant growth case:

When the free cash flows to the firm are expected to grow at a constant rate$g$forever ($g<WACC$),  then:

$$V_{0}=\frac{FCFF_{1}}{WACC-g}\tag{2}$$

This is simply the _Gordon growth model_. To understand valuation in contexts other than these simple ones we need to understand the role of value drivers.

## VALUE DRIVERS OF FREE CASH FLOWS AND FIRM VALUE THERE ARE THREE KEY VALUE DRIVERS OF FREE CASH FLOWS

- The rate of growth of a company's revenues,  profits,  and
  operating assets (g).

- The return on new investment (ROI),  which determines the
  profitability of the new investments undertaken by the business.

- The firm's reinvestment rate (b),  which determines its capital
  expenditure (new investments) policy.

- There are only two independent value drivers. Given two
  value drivers,  the third one can be determined as a function of the other two.

CapEx refer to capital expenditures (both new and replacement capital expenditures,  includes acquisitions)

ΔWC refers to change in working capital,  which is a measure of new working capital investments. Dep & Amort refers to all depreciation and amortization (more generally also all non-cash items) To keep things simple,  assume that we are in a low inflation environment. Consider free cash flows to firm:

$$FCFF=NOPAT+Dep\, \&\, \, Amort-CapEx-\Delta WC\tag{3}$$

Define:

$$Gross\,  Investment=CapEx+\Delta WC\tag{4}$$

Gross investment refers to _new and replacement_ capital expenditures and investments. Also define:

$$\text{Net New Investment }= CapEx + ΔWC-Dep, Amort \tag{5}$$

- Net new investment refers to _new_ capital investments made in excess of replacement capital investments.
- Economically,  replacement investments are needed to maintain existing production capacity and sales while new investments are needed to generate additional growth.

Now we can define free cash flows to the firm as:$$FCFF=NOPAT-Net\,  New\,  Investment\tag{6}$$
Thus,  free cash flows to firm are the cash left over from NOPAT after a firm has spent sufficient funds on new investments. If a firm makes no net new investment,  then FCFF = NOPAT into perpetuity (equation (1)).

Define the _reinvestment rate_ (b) as the rate at which a firm reinvests its NOPAT (for NOPAT >= 0):

$$b=\frac{Net\,  New\,  Investment}{NOPAT}\tag{7}$$
Can 'b' be$>1$? Can 'b' be$<0$? Explain?

Using equation (7),  write FCFF in equation (6) as:
$$FCFF=(1-b)\times NOPAT\tag{8}$$
(1 - b) is the proportion of NOPAT available for payout to all investors of the firm (capacity to payout all investors).

We can forecast free cash flows by forecasting growth in profits 'g' and the reinvestment rate 'b'.

Example: Consider two firms A and B with the same operating risks and capital structure. Assume that inflation is close to zero (to avoid any inflation induced growth). Both firms are expected to earn net operating profits after taxes (NOPAT) of$100 in Year 1. If the two firms do not invest in new assets,  both will continue to earn$100 for ever. The WACC for both firms is 8%.

1. Assume that Firm A reinvests 15% of its NOPAT in new investments and earns 20% return
	on them. Firm B,  however,  earns only 10% return on new investments. If firm B wants to achieve the same growth in profits as firm A,  what percentage of its NOPAT should it reinvest each year? Which firm will have more free cash flows and which firm will be more valuable?

1. Suppose now Firm A and Firm B have the same return on new investments equal to 20%. Firm A reinvests at a rate of 30% a year. However,  Firm B does not face the same investment opportunities as Firm A and can reinvest only 15% a year. Which firm will have more free cash flows and which firm will be more valuable?

## EXAMPLE 1: HOW RETURN ON INVESTMENT DRIVES FIRM VALUE? FIRM A

| ROI | 20% |
| - | - |
| b | 15% |

Sample NOPAT calculation:
Year 2 NOPAT = Year 1 NOPAT + Year 1 Net Investment \* ROI = 100 + 15 \* 0.20 = 103

## EXAMPLE 2: HOW GROWTH DRIVES FIRM VALUE (PROVIDED ROI > WACC)

| WACC | 8% |
| - | - |
| Assumption: NOPAT on base assets at the beginning of Year 1 does not change over time. | |
| Annual growth rate in NOPAT & FCFF | 3.0% |
| Firm B's Value |$1, 700 (using the Gordon growth model) |

Result 2: For the same return on capital,  a faster growing firm would be worth more than a slow growing firm. Until Year 7,  Firm A,  the faster growing firm generates lower FCFF than firm B,  the slower growing firm. Firm A also reinvests more than Firm B.

**Growth in NOPAT**

In the above example,  growth in NOPAT is given by:

$$g_{t}=\frac{NOPAT_{t}-NOPAT_{t-1}}{NOPAT_{t-1}}$$

$$\Rightarrow\quad g_{t}=\frac{NOPAT_{t}-NOPAT_{t-1}}{I_{t-1}}\times\frac{I_{t-1}}{NOPAT_{t-1}} \tag{9a}$$
$$=ROI_{t}\times b_{t-1}$$

where NOPAT$_{t}$- NOPAT$_{t-1}$is the profit from new investment,  ROI$_{t}$is the return on net new investment,  I$_{t-1}$is the new investment made at the beginning of the year,  and b$_{t-1}$is the reinvestment rate. In the steady state,  b$_{t-1}$= b$_{t}$= b and ROI$_{t}$= ROI$_{t-1}$= ROI then:

$$g=b\times ROI\tag{9b}$$

where g is referred to as the _sustainable growth rate_. Thus,  a firm can increase its growth rate by:

- Improving its return on investments (ROI) (both new and existing assets). E.g.: efficiency improvements.
- Investing more capital (b) in projects with high return on investment. E.g.: expanding markets.

**Practical implementation of the FCFF valuation model**

The free cash flow model is implemented as follows in practice to compute _total enterprise value_:
$$V_{0}=\sum_{t=1}^{T}\frac{E\big{(}FCFF_{t}\big{)}}{\big{(}1+WACC\big{)}^{t}}+\frac{TV_{T}}{\big{(}1+WACC\big{)}^{T}}\tag{10}$$
where TVT is the continuing value in period T for the FCFF valuation model (see Chapter 10 of KGW).

#### THREE STAGE VALUATION
1. High Growth: High return on investment (ROI),  High reinvestment rate (b),  High growth (g) in sales and profits.
1. Transition: Competition drives down ROI on existing and new assets. Firm faces declining investment opportunities (fewer positive NPV projects) leading to lower reinvestment rates Declining reinvestment rates and ROI are accompanied by declining growth.
1. Mature: Firm reaches a steady state with constant growth,  ROI,  and reinvestment rates. New investments are likely to earn just the cost of capital.

We will use this intuition in our implementation of the valuation model.

#### CONTINUING VALUE BASED ON THE GORDON GROWTH MODEL

Free cash flows (FCFF) grow at a constant rate g after T+1. The PV of cash flows after T as of time T:

$$TV_{T}=\frac{FCFF_{T+1}}{WACC-g}\tag{11}$$
Since FCFF$_{T+1}$= NOPAT$_{T+1}$(1 - b) (see equation 8) where b is the steady-state reinvestment rate starting in year T+1:
$$TV_{T}=\frac{NOPAT_{T+1}(1-b)}{WACC-g}\tag{12}$$
In the steady-state,  from the sustainable growth model (eq. 9):
$$g=\quad b\times ROI\tag{13}$$
where g is the steady-state growth in profits and ROI is the steady-state return on new investments.

- \What would be a good choice for steady-state growth?
- \What would be a good choice for steady-state ROI?

#### TERMINAL VALUE BASED ON VALUE DRIVERS

From equation (13),  b = g/ROI. Substitute this into equation (12):

$$TV_{T}=\frac{NOPAT_{T+1}(1-g/ROI)}{WACC-g}\tag{14}$$
Equation (14) is the _value-driver based terminal value formula_.

**No Growth Perpetuity Continuing Value Formula**

Suppose the return on new investments equals cost of capital,  i.e.,  ROI = WACC. Substitute ROI = WACC in equation (14):

$$TV_{T}=\frac{NOPAT_{T+1}(1-g/WACC)}{WACC-g}\tag{15}$$
$$=\frac{NOPAT_{T+1}}{WACC-g}\times\frac{WACC-g}{WACC}=\frac{NOPAT_{T+1}}{WACC}$$

We get the perpetuity formula for the _no-growth_ case. This doesn't mean that there is no nominal growth in earnings simply that any such growth does not add to value.

We will use the more general formula in equation (14),  which gives us the option to set ROI ≥ WACC.

Three-Stage FCFF Valuation Model This model is used to compute the total enterprise value (value of operating assets) of the firm. The model contains three stages. They are:

1. _High Growth Stage_: (2 years) marked by high NOPAT growth,  high reinvestment rates,  and high return on investment.
1. _Transition Stage_: (15 years from Year 2 to Year 17) marked by mean-reversion where growth rates,  reinvestment rates,  and return on investment all decline to a long run steady state.
1. _Steady State_: (forever from Year 17) marked by steady-state equilibrium where growth,  reinvestment rate,  and return on investment settle into long run steady state.

## INPUTS TO THE MODEL

1. Year 0 NOPAT and Year 0 Invested Capital.
1. Growth forecasts (g) and reinvestment rate (b) for the _high growth_ stage.
1. _Steady state_ growth (g) and return on investment (ROI).
1. Weighted average cost of capital (WACC).
1. Year 0 book value (ideally market value) of debt and preferred
	stock,  excess cash,  shares outstanding and current stock price.

See Worksheet (9) for the FCFF model to value the firm in the EXCEL workbook _Smucker-July 2015 version 7.0.xls_.

## 15-YEAR VALUATION MODEL

We combine all these elements together and provide the following implementation:

$$V_{0}=\sum_{t=1}^{T}\frac{NOPAT_{t}\times(1-b_{t})}{\left(1+WACC\right)^{t}}+\frac{NOPAT_{T+1}\times(1-g/ROI)}{\left(1+WACC\right)^{T}\times\left(WACC-g\right)}\tag{16}$$

- NOPATt = Net Operating Profits After Taxes for year 't'.
- bt = Reinvestment rate for year 't'.
- WACC = Weighted Average Cost of Capital.
- g = Steady-state growth in NOPAT and cash flows.
- ROI = Steady-state ROI ≥ WACC.
- T = Number of years of explicit NOPAT forecasts. We will implement the model with T=15 years.
$$E(FCFF_{t})=NOPAT_{t}\times(1-b_{t})\tag{17}$$
$$NOPAT_{t+1}=NOPAT_{t}\times(1+g_{t+1})\tag{18}$$
Growth rate declines _exponentially_ (or linearly in logs) from (g2) in Year 2 to steady-state growth (g) in Year 17. For t = 2 to 15:
$$g_{t+1}=g_{t}\times\mbox{EXP}\left[\log\left(g/g_{2}\right)/T\right]\tag{19}$$
$$b_{t}=b_{t-1}-\frac{b_{1}-b}{T}\tag{20}$$
Reinvestment Rates for the High Growth Stage Reinvestment rates are computed as follows:
- Reinvestment rate (b) = (1 - FCFF/NOPAT).
- FCFF/NOPAT is capacity payout all investors (for NOPAT > 0).

Sequential Valuation of Equity
Given total firm value,  equity is valued sequentially as follows:

- E = Value of the Firm - Value of Pref. Stock & Min. Int. \Value of Debt

Assets-in-place and PVGO

- Total Enterprise Value (V) = Value of assets-in-place + Present Value of Growth Opportunities (PVGO)

Value of assets-in-place = NOPAT1/WACC.

- Value of assets-inplace is simply the no-growth value (earnings power value,  EPV).
- Whether growth is value adding,  value neutral or value destroying depends on whether ROI > WACC,  ROI = WACC or ROI < WACC.
- PVGO = V - Value of assets in place.

Value Drivers and Direct Valuation of Equity

We can _value equity directly_ using the same analytical approach that we used to compute the total enterprise value by making the following substitutions.

| Value Firm | Value Equity |
|----------------------------------|-----------------------------------|
| NOPAT | EPS (earnings per share) |
| FCFF | FCFE |
| Return on Invested Capital,  ROIC | Return on Equity,  ROE |
| Reinvestment Rate,  b | Plowback Rate,  k |
| Growth in NOPAT,  g | Growth in EPS,  g |
| WACC | Cost of Equity,  r |
| e | |
| | |
| Return on new Investments,  ROI | Return on new equity investments,  |
| ROE\* | |

The plowback rate 'k' represents the proportion of net income that is retained in the firm. Thus:

- FCFE = EPS\*(1 - k) (similar to equation (8))
- For Net Income > 0,  'k' is computed from historical data as: k = 1 - (FCFE/Net Income)
	- (FCFE/Net Income) is the _payout capacity_ since this represents the firm's capacity to pay its shareholders. We could use actual payout (dividends + net stock repurchase).

---

- **Free Cash Flow to Equity (FCFE) Valuation Model**
	 - V_E = \sum_{t=1}^T \frac{FE_t \times (1-k_t)}{(1+r_e)^t} + \frac{FE_{T+1} \times (1-g/ROE^*)}{(1+r_e)^T \times (r_e - g)} \tag{21}
	 - _FE_ stands for forecast earnings per share and _ROE^_* is the return on new equity investments. This approach is referred to as the direct valuation of equity.
	 - The three-stage model to value equity directly is provided in worksheet (10) in the EXCEL workbook _Smucker-July 2015 version 7.0.xls_.
- **Data needed for implementing the equity valuation model**
	 - Analyst consensus earnings forecasts for the first two years (FY1 and FY2)
	 - Plowback rates for the first stage
	 - Long-run steady-state growth and ROI
	 - Beta,  market risk premium,  and risk-free rate
	 - Number of shares outstanding
	 - Book (market) value of interest-bearing debt,  preferred stock
	 - Cash and short-term investments
- **Smucker (SJM) EPS forecasts (as of August 19,  2022)**
	 - FY1
		  - Current Qtr. (Jul 15): 1.23
		  - Next Qtr. (Oct 15): 1.54
		  - Current Year (Apr 16): 5.72
	 - FY2
		  - Next Year (Apr 17): 6.31
	 - Yahoo Finance Link
	 - Estimating 12 month and 24 month ahead forecasts
		  - As of August 19,  2022,  FY1 is only an eight-month forecast.
		  - Trailing 12-month earnings,  FE0,  and 12-month ahead forecast,  FE1
				- FE0 = EPS0 * (N/12) + FY1 * (1 – N/12)
				- FE0 = 5.38 * (8/12) + 5.72 * (1-8/12) =$5.49
				- FE1 = FY1 * (N/12) + FY2 * (1 – N/12)
				- FE1 = 5.72 * (8/12) + 6.31 * (1-8/12) =$5.92
				- g2 = FY2/FY1 - 1 = 6.31/5.49 – 1 = 7.8%
				- FE 2 = FE 1*(1+g 2) = 5.92*1.078 =$6.38
		  - Trailing 12-month earnings,  FE 0 and 12-month ahead forecast,  FE 1$$FE_0 = EPS_0 \times \left(\frac{N}{12}\right) + FY1 \times \left(1 - \frac{N}{12}\right)$$
		- $$FE_0 = 5.38 \times \left(\frac{8}{12}\right) + 5.72 \times \left(1-\frac{8}{12}\right) = \$5.49$$
	 - $$FE_1 = FY_1 \times \left(\frac{N}{12} \right) + FY_2 \times \left(1 – \frac{N}{12} \right)$$$$FE_1 = 5.72 \times \left(\frac{8}{12}\right) + 6.31 \times \left(1-\frac{8}{12}\right) = \$5.92$$$$
	 - G_{2} = \frac{FY_{2}}{FY} 1 - 1 = 5.92/5.49 – 1 = 7.8\%$$
- **Smucker beta and market cap**
	 - The J. M. Smucker Company (SJM)
		  - Current Price: 111.88
		  - Beta: 1.22
		  - Market Cap: 13.39B
- **Other data**
	 - Balance sheet data
		  - Cash =$0.1256 billion.
		  - Debt =$6.171 billion.
		  - Shares outstanding = 0.11967 billion
	 - Cost of Equity for Smucker using CAPM
		  - As of July 2015,  it was 9.74%.
	 - Plowback rate in Stage 1
		  - From worksheet 4: Average payout ratio over the last 10 years is about 1. The current payout ratio is 0.81. This gives a plowback rate range of 0 to 0.19.
	 - Steady-state information
		  - Steady-state growth = 3% (assume nominal GDP growth)
		  - Steady-state ROI = Cost of equity,  9.74%
		  - Steady-state plowback rate,  k = g/ROI = 0.03/0.0974 = 0.31
	 - Smucker intrinsic value =$83.59 per share
		  - Current price (July 8,  2022) =$108.46 per share
		  - P/V ratio = 108.46/83.59 = 1.30 (overvalued by 30%).

## FREE CASH FLOW TO EQUITY (FCFE) VALUATION MODEL
  - $$V_E = \sum_{t=1}^{T} \frac{FE_t \times (1 - k_t)}{(1 + r_e)^t} + \frac{FE_{T+1} \times (1 - g / ROE^*)}{(1 + r_e)^T \times (r_e - g)} \tag{21}$$
  - FE stands for forecast earnings per share and ROE* is the return on new equity investments. This approach is referred to as the direct valuation of equity.
  - The three-stage model to value equity directly is provided in worksheet (10) in the EXCEL workbook _Smucker-July 2015 version 7.0. Xls_.
- Data needed for implementing the equity valuation model
  - Analyst consensus earnings forecasts for the first two years (FY 1 and FY 2)
  - Plowback rates for the first stage
  - Long-run steady-state growth and ROI
  - Beta,  market risk premium,  and risk-free rate
  - Number of shares outstanding
  - Book (market) value of interest-bearing debt,  preferred stock
  - Cash and short-term investments
- Smucker (SJM) EPS forecasts (as of August 19,  2022)
  - FY 1
  - FY 2
  - [Link to Yahoo Finance Analyst Estimates](http://finance.yahoo.com/q/ae?s=SJM+Analyst+Estimates)
- Estimating 12 month and 24 month ahead forecasts
  - As of August 19,  2022,  FY 1 is only an eight-month forecast. Trailing 12-month earnings consists of 8/12 of EPS 0 and 4/12 of FY 1. Next 12 months earnings consist of 8/12 of FY 1 and 4/12 of FY 2. Let N = number of months to the next fiscal year-end (April 2016); Thus,  N=8.
	 - Trailing 12-month earnings,  FE 0 and 12-month ahead forecast,  FE 1
		- $$FE_0 = EPS_0 \times \left(\frac{N}{12}\right) + FY1 \times \left(1 - \frac{N}{12}\right)$$
		- $$FE_0 = 5.38 \times \left(\frac{8}{12}\right) + 5.72 \times \left(1-\frac{8}{12}\right) = \$5.49$$
	 - FE 1 = FY 1 \times (N/12) + FY 2 \times (1 – N/12)
	 - $$FE_1 = 5.72 \times \left(\frac{8}{12}\right) + 6.31 \times \left(1-\frac{8}{12}\right) = \$5.92$$
	 - G 2 = FY 2/FY 1 - 1 = 5.92/5.49 – 1 = 7.8%
	 - $$FE_2 = FE_1$$

---

**Free Cash Flow to Equity (FCFE) Valuation Model**

$$V_{E}=\sum_{t=1}^{T}\frac{FE_{t}\times(1-k_{t})}{\left(1+r_{e}\right)^{t}}+\frac{FE_{T+1}\times(1-g\, /\, ROE^{\*})}{\left(1+r_{e}\right)^{T}\times\left(r_{e}-g\right)}\tag{21}$$

FE stands for forecast earnings per share and ROE\* is the return on new equity investments. This approach is referred to as the direct valuation of equity. The three-stage model to value equity directly is provided in worksheet (10) in the EXCEL workbook Smucker-July 2015 version 7.0.xls.

Data needed for implementing the equity valuation model
 Analyst consensus earnings forecasts for the first two years

(FY 1 and FY 2)
 Plowback rates for the first stage  Long-run steady-state growth and ROI  Beta,  market risk premium,  and risk-free rate  Number of shares outstanding  Book (market) value of interest-bearing debt,  preferred stock  Cash and short-term investments

## FY 2 SMUCKER (SJM) EPS FORECASTS (AS OF AUGUST 19,  2022) FY 1

http://finance.yahoo.com/q/ae?s=SJM+Analyst+Estimates Estimating 12 month and 24 month ahead forecasts

As of August 19,  2022,  FY 1 is only an eight-month forecast. Trailing
12-month earnings consists 8/12 of EPS 0 and 4/12 of FY 1. Next 12
Month earnings consist 8/12 of FY 1 and 4/12 of FY 2. Let N = number of months to the next fiscal year-end (April 2016); Thus,  N=8.

Trailing 12-month earnings,  FE 0 and 12-month ahead forecast,  FE 1
FE 0 = EPS 0 * (N/12) + FY 1 * (1 - N/12)
FE 0 = 5.38 * (8/12) + 5.72 * (1-8/12) = $5.49

FE 1 = FY 1 * (N/12) + FY 2 * (1 - N/12)
FE 1 = 5.72 * (8/12) + 6.31 * (1-8/12) = $5.92

G 2 = FY 2/FY 1 -1 = 5.92/5.49 - 1 = 7.8%
FE 2 = FE 1*(1+g 2) = 5.92*1.078 = $6.38

## SMUCKER BETA AND MARKET CAP

You can also get shares outstanding,  financial statements for three years,  and other key statistics from Yahoo Finance. http://finance.yahoo.com/q/ks?s=SJM+Key+Statistics This is a screen capture from August 19,  2022. The current beta and market cap can be obtained from the same link. All of the data in the worksheets are as of July 2015.

## OTHER DATA BALANCE SHEET DATA CASH = CASH & CASH EQUIVALENTS & SHORT-TERM INV

|                      | =               | $0.1256 billion.                 |
|----------------------|-----------------|----------------------------------|
| Debt                 | =               | Long-term debt + Short-term debt |
|                      |                 | =                                |
| Shares outstanding = | 0.11967 billion |                                  |

Cost of Equity for Smucker using CAPM As of July 2015,  it was 9.74%. Plowback rate in Stage 1 From worksheet 4: Average payout ratio over the last 10 years is about 1. The current payout ratio is 0.81. This gives a plowback rate range of 0 to 0.19. I use the higher number. You can take the most recent number,  average it over 5 years,  etc. It is your choice. Steady-state information Steady-state growth = 3% (assume nominal GDP growth)
Steady-state ROI
= Cost of equity,  9.74%
Steady-state plowback rate,  k = g/ROI = 0.03/0.0974 = 0.31 Smucker intrinsic value = $83.59 per share Current price (July 8,  2022) = $108.46 per share P/V ratio = 108.46/83.59 = 1.30 (overvalued by 30%).

Worksheet (10) in the EXCEL workbook Smucker-July 2015 version 7.0. Xls Dr. Bhaskaran Swaminathan Sensitivity Analysis Examine how your valuations change when you adjust your key assumptions,  for example you can test how **Low Estimate** and High Estimate of earnings forecasts affect your valuations. You can examine the sensitivity of your analysis to your cost of capital estimates and the payout ratios.

Distressed Firms Even if trailing earnings are negative,  as long as the firm has positive earnings forecasts,  you can still use the model. If both FY 1 and FY 2 forecasts are negative,  then it is hard to perform DCF valuation. If NOPAT is negative,  you can use a normalized NOPAT (average or median of the prior 5 or 10 years).