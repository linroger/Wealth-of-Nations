---
title: Credit Markets Homework 2
tags:
  - bond_market_data
  - cashflow_schedules
  - credit_markets
  - fixed_rate_bonds
  - quantlib
aliases:
  - Credit Markets
  - Fixed Rate Bonds
  - Homework 2
key_concepts:
  - Bond cash flows
  - Cashflow schedules
  - Fixed rate bonds
  - QuantLib date object
  - Symbology data
---

# Credit Markets Homework 2

This homework relies on:

- The corporate and government bonds symbology file `bond_symbology`,
- The "on-the-run" treasuries data file `govt_on_the_run`,
- The bond market data file `bond_market_prices_eod`,  containing EOD price data as of 2024-04-08.

# Problem 1: Constructing fixed rate bonds

```python
Import QuantLib as ql
Import pandas as pd
Import datetime as dt

# Use static calculation/valuation date of 2024-04-08,          matching data available in the market prices EOD file
Calc_date = ql.Date (8,          4,          2024)
Ql.Settings.Instance (). EvaluationDate = calc_date
```

## a. Prepare the symbology and market data files for fixed rate government and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]

Load the `bond_symbology`,  `bond_market_prices_eod` and `govt_on_the_run` Excel files into dataframes.

Filter the symbology frame for fixed rate bonds only (cpn_type="FIXED").

```python
# Set as-of-date
As_of_date = pd. To_datetime ('2024-04-08')

# Load bond_symbology. Xlsx

Bond_symbology  = bond_symbology[bond_symbology['cpn_type'] == 'FIXED']

# Add term and TTM columns
Bond_symbology['term'] = (bond_symbology['maturity'] - bond_symbology['start_date']). Dt. Days / 365.25
Bond_symbology['TTM'] = (bond_symbology['maturity'] - as_of_date). Dt. Days / 365.25
Display (bond_symbology.Head ())
# Load bond_market_prices_eod
# Add mid prices and yields
Bond_market_prices_eod['midPrice'] = 0.5*(bond_market_prices_eod['bidPrice'] + bond_market_prices_eod['askPrice'])
Bond_market_prices_eod['midYield'] = 0.5*(bond_market_prices_eod['bidYield'] + bond_market_prices_eod['askYield'])
Display (bond_market_prices_eod.Head ())

Bond_symbology

# Load govt_on_the_run,          as of 2024-04-08
# Keep OTR treasuries only
Govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run['ticker']. Str.Contains ('B|C')]
Display (govt_on_the_run_simple.Head ())

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>ticker</th>
	  <th>class</th>
	  <th>figi</th>
	  <th>isin</th>
	  <th>und_bench_isin</th>
	  <th>security</th>
	  <th>name</th>
	  <th>type</th>
	  <th>coupon</th>
	  <th>cpn_type</th>
	  <th>…</th>
	  <th>acc_first</th>
	  <th>maturity</th>
	  <th>mty_typ</th>
	  <th>rank</th>
	  <th>amt_out</th>
	  <th>country</th>
	  <th>currency</th>
	  <th>status</th>
	  <th>term</th>
	  <th>TTM</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>US 037833 AL 42</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>3.850</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2013-05-03</td>
	  <td>2043-05-04</td>
	  <td>AT MATURITY</td>
	  <td>Sr Unsecured</td>
	  <td>3000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>30.001369</td>
	  <td>19.069131</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>US 037833 AT 77</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.450</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2014-05-06</td>
	  <td>2044-05-06</td>
	  <td>AT MATURITY</td>
	  <td>Sr Unsecured</td>
	  <td>1000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>30.001369</td>
	  <td>20.076660</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>US 037833 BA 77</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>3.450</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2015-02-09</td>
	  <td>2045-02-09</td>
	  <td>AT MATURITY</td>
	  <td>Sr Unsecured</td>
	  <td>2000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>30.001369</td>
	  <td>20.840520</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>US 037833 BH 21</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.375</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2015-05-13</td>
	  <td>2045-05-13</td>
	  <td>AT MATURITY</td>
	  <td>Sr Unsecured</td>
	  <td>2000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>30.001369</td>
	  <td>21.095140</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 00 C 7 QBCQ 1</td>
	  <td>US 037833 BW 97</td>
	  <td>US 91282 CJZ 59</td>
	  <td>AAPL 4 1/2 02/23/36</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.500</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2016-02-23</td>
	  <td>2036-02-23</td>
	  <td>CALLABLE</td>
	  <td>Sr Unsecured</td>
	  <td>1250.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>20.000000</td>
	  <td>11.876797</td>
	</tr>
  </tbody>
</table>
<p>5 rows × 25 columns</p>
</div>

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>date</th>
	  <th>class</th>
	  <th>ticker</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>bidPrice</th>
	  <th>askPrice</th>
	  <th>accrued</th>
	  <th>bidYield</th>
	  <th>askYield</th>
	  <th>midPrice</th>
	  <th>midYield</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>IBM</td>
	  <td>US 459200 KX 88</td>
	  <td>BBG 01 DMT 8986</td>
	  <td>97.453</td>
	  <td>97.706</td>
	  <td>0.9635</td>
	  <td>5.248</td>
	  <td>5.173</td>
	  <td>97.5795</td>
	  <td>5.2105</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>IBM</td>
	  <td>US 459200 GS 40</td>
	  <td>BBG 0000 L 5 Z 27</td>
	  <td>99.145</td>
	  <td>99.818</td>
	  <td>2.2245</td>
	  <td>5.683</td>
	  <td>5.617</td>
	  <td>99.4815</td>
	  <td>5.6500</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>GM</td>
	  <td>US 37046 AFD 28</td>
	  <td>BBG 019 LXFPP 4</td>
	  <td>97.075</td>
	  <td>97.556</td>
	  <td>0.5225</td>
	  <td>6.472</td>
	  <td>6.342</td>
	  <td>97.3155</td>
	  <td>6.4070</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>GM</td>
	  <td>US 37046 AFA 88</td>
	  <td>BBG 017 B 6 GFF 0</td>
	  <td>95.012</td>
	  <td>95.453</td>
	  <td>2.1245</td>
	  <td>6.337</td>
	  <td>6.216</td>
	  <td>95.2325</td>
	  <td>6.2765</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>F</td>
	  <td>US 34540 TZC 97</td>
	  <td>BBG 017 QYHT 99</td>
	  <td>98.950</td>
	  <td>99.289</td>
	  <td>2.0675</td>
	  <td>6.419</td>
	  <td>6.298</td>
	  <td>99.1195</td>
	  <td>6.3585</td>
	</tr>
  </tbody>
</table>
</div>

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>ticker</th>
	  <th>date</th>
	  <th>figi</th>
	  <th>isin</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>GT 10 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 L 8 YJFB 3</td>
	  <td>US 91282 CJZ 59</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>GT 2 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 M 44 ZLG 5</td>
	  <td>US 91282 CKH 33</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>GT 20 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 LK 8 Y 0 L 1</td>
	  <td>US 912810 TZ 12</td>
	</tr>
	<tr>
	  <th>9</th>
	  <td>GT 3 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 M 9 L 5 M 64</td>
	  <td>US 91282 CKJ 98</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>GT 30 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 L 8 YJKX 8</td>
	  <td>US 912810 TX 63</td>
	</tr>
  </tbody>
</table>
</div>

## b. Add function to construct generic fixed rate cashflow schedules from symbology data

Use one row of the symbology dataframe as input to the function. Use the helper function to convert a date string to a QuantLib date object.

```python
Def get_ql_date (date) -> ql. Date:
    """
    Convert dt. Date to ql. Date
    """
    If isinstance (date,          dt. Date):
        Return ql.Date (date. Day,          date. Month,          date. Year)
    Elif isinstance (date,          str):
        Date = dt.Datetime.Strptime (date,          "%Y-%m-%d"). Date ()
        Return ql.Date (date. Day,          date. Month,          date. Year)
    Else:
        Raise ValueError (f"to_qldate,          {type (date)},          {date}")
```

```python
Def create_schedule_from_symbology (details: dict):
    '''Create a QuantLib cashflow schedule from symbology details dictionary (usually one row of the symbology dataframe)
    '''
    
    # Create maturity from details['maturity']
    Maturity = get_ql_date (details['maturity'])
    
    # Create acc_first from details['acc_first']
    Acc_first =  get_ql_date (details['acc_first'])
    
    # Create calendar for Corp and Govt asset classes
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    # define period from details['cpn_freq'] … Can be hard-coded to 2 = semi-annual frequency
    Period = ql.Period (2)
    
    # business_day_convention
    Business_day_convention = ql. Unadjusted
    
    # termination_date_convention
    Termination_date_convention = ql. Unadjusted
    
    # date_generation
    Date_generation=ql. DateGeneration. Backward
    
    # Create schedule using ql. MakeSchedule interface (with keyword arguments)
    Schedule = ql.MakeSchedule (effectiveDate=acc_first,           # this may not be the same as the bond's start date
                            TerminationDate=maturity,         
                            Tenor=period,         
                            Calendar=calendar,         
                            Convention=business_day_convention,         
                            TerminalDateConvention=termination_date_convention,         
                            Rule=date_generation,         
                            EndOfMonth=True,         
                            FirstDate=ql.Date (),         
                            NextToLastDate=ql.Date ())
    Return schedule
```

```python
# Use one row of the symbology dataframe as input to the create_schedule_from_symbology () function.
Corp_bond_details = bond_symbology[bond_symbology['class'] == 'Corp']. Iloc[10]
Print ("Corp bond details for",          corp_bond_details['security'])
Display (corp_bond_details)

# Create cashflow_schedule
Cashflow_schedule = create_schedule_from_symbology (corp_bond_details)
Print ("Cashflow dates for",          corp_bond_details['security'])

# List cashflow dates
For date in cashflow_schedule:
        Print (date)
```

    Corp bond details for AAPL 3.35 02/09/27
    Ticker                           AAPL
    Class                            Corp
    Figi                     BBG 00 FXTS 8 Z 0
    Isin                     US 037833 CJ 77
    Und_bench_isin           US 91282 CKJ 98
    Security           AAPL 3.35 02/09/27
    Name                        APPLE INC
    Type                           GLOBAL
    Coupon                           3.35
    Cpn_type                        FIXED
    Dcc                            30/360
    Cpn_freq                            2
    Days_settle                         2
    start_date        2017-02-09 00:00:00
    cpn_first         2017-08-09 00:00:00
    acc_first         2017-02-09 00:00:00
    maturity          2027-02-09 00:00:00
    Mty_typ                      CALLABLE
    Rank                     Sr Unsecured
    Amt_out                        2250.0
    Country                            US
    Currency                          USD
    Status                           ACTV
    Term                         9.998631
    TTM                          2.839151
    Name: 10,          dtype: object
    Cashflow dates for AAPL 3.35 02/09/27
    February 9 th,          2017
    August 9 th,          2017
    February 9 th,          2018
    August 9 th,          2018
    February 9 th,          2019
    August 9 th,          2019
    February 9 th,          2020
    August 9 th,          2020
    February 9 th,          2021
    August 9 th,          2021
    February 9 th,          2022
    August 9 th,          2022
    February 9 th,          2023
    August 9 th,          2023
    February 9 th,          2024
    August 9 th,          2024
    February 9 th,          2025
    August 9 th,          2025
    February 9 th,          2026
    August 9 th,          2026
    February 9 th,          2027

## c. Add function to construct generic fixed rate bond objects from symbology data

Use one row of the symbology dataframe as input to the function. Use create_schedule_from_symbology () internally to create the cashflow schedule.

```python
Def create_bond_from_symbology (details: dict):
    '''Create a US fixed rate bond object from symbology details dictionary (usually one row of the symbology dataframe)
    '''
    
     # Create day_count from details['dcc']
     # For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)
     # For US [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] use ql. Thirty 360 (ql. Thirty 360. USA)
    
    If details['class'] == 'Corp':
        Day_count = ql. Thirty 360 (ql. Thirty 360. USA)
    Elif details['class'] == 'Govt':
        Day_count = ql.ActualActual (ql. ActualActual. ISMA)
    Else:
        Raise ValueError (f"unsupported asset class,          {type (details['class'])},          {details['class']}")
    # Create issue_date from details['start_date']
    Issue_date = get_ql_date (details['start_date'])
    
    # Create days_settle from details['days_settle']
    Days_settle = int (float (details['days_settle']))

    # Create coupon from details['coupon']
    Coupon = float (details['coupon'])/100.
    # Create cashflow schedule
    Schedule = create_schedule_from_symbology (details)
    
    Face_value = 100
    Redemption = 100
    
    Payment_convention = ql. Unadjusted
        
    # Create fixed rate bond object
    Fixed_rate_bond = ql.FixedRateBond (
        Days_settle,         
        Face_value,         
        Schedule,         
        [coupon],         
        Day_count,         
        Payment_convention,         
        Redemption,         
        Issue_date)        

    Return fixed_rate_bond

```

```python
# Use one row of the symbology dataframe as input to the function.
Corp_bond_object = create_bond_from_symbology (corp_bond_details)

Print ("Corp bond object details for",          corp_bond_details['security'])
Print ('Start date: ',          corp_bond_object.StartDate ())
Print ('Maturity date: ',          corp_bond_object.MaturityDate ())
Print ('Bond face notional: ',          corp_bond_object.Notional ())

```

    Corp bond object details for AAPL 3.35 02/09/27
    Start date: February 9 th,          2017
    Maturity date: February 9 th,          2027
    Bond face notional: 100.0

## d. Add function that returns a dataframe with (future) cash flows details for a bond object

Use the "Investigate Bond Cashflows" section in the Quantlib Basic notebook as a template.

The results dataframe should contain following columns:

| CashFlowDate | CashFlowAmount | CashFlowYearFrac |
|----------|-------|-------------|

Pick one government and one corporate bond from symbology,  create the bond objects and display the future cashflows.

```python
Def get_bond_cashflows (bond: ql. FixedRateBond,          calc_date=ql. Date) -> pd. DataFrame:
    '''Returns all future cashflows as of calc_date,          i.e. with payment dates > calc_date.
    '''    
    Day_counter = bond.DayCounter ()    
    
    X = [(cf.Date (),          day_counter.YearFraction (calc_date,          cf.Date ()),          cf.Amount ()) for cf in bond.Cashflows ()]
    Cf_date,          cf_yearFrac,          cf_amount = zip (*x)
    Cashflows_df = pd.DataFrame (data={'CashFlowDate': cf_date,          'CashFlowYearFrac': cf_yearFrac,          'CashFlowAmount': cf_amount})

    # filter for payment dates > calc_date
    Cashflows_df = cashflows_df[cashflows_df. CashFlowYearFrac > 0]
    Return cashflows_df

```

```python
# Pick one government and one corporate bond from symbology,          create the bond objects.
Govt_bond_details = bond_symbology[bond_symbology['class'] == 'Govt']. Iloc[10]
Print ("Govt bond details for",          govt_bond_details['security'])
Display (govt_bond_details)

# Create govt_bond_object
Govt_bond_object = create_bond_from_symbology (govt_bond_details)
```

    Govt bond details for T 7 5/8 02/15/25
    Ticker                              T
    Class                            Govt
    Figi                     BBG 000 DLBVY 0
    Isin                     US 912810 ET 17
    Und_bench_isin           US 912797 KS 58
    Security             T 7 5/8 02/15/25
    Name                  US TREASURY N/B
    Type                    US GOVERNMENT
    Coupon                          7.625
    Cpn_type                        FIXED
    Dcc                           ACT/ACT
    Cpn_freq                            2
    Days_settle                         1
    start_date        1995-02-15 00:00:00
    cpn_first         1995-08-15 00:00:00
    acc_first         1995-02-15 00:00:00
    maturity          2025-02-15 00:00:00
    Mty_typ                        NORMAL
    Rank                        Unsecured
    Amt_out                        9509.0
    Country                            US
    Currency                          USD
    Status                           ACTV
    Term                        30.001369
    TTM                          0.856947
    Name: 348,          dtype: object

```python
# Govt bond: display the future cashflows.
Print ("Govt bond future cashflows for",          govt_bond_details['security'])
Govt_bond_cf = get_bond_cashflows (govt_bond_object,          calc_date=calc_date)
Display (govt_bond_cf)

# Corp bond: display the future cashflows.
Print ("Corp bond future cashflows for",          corp_bond_details['security'])
Corp_bond_cf = get_bond_cashflows (corp_bond_object,          calc_date=calc_date)
Display (corp_bond_cf)
```

    Govt bond future cashflows for T 7 5/8 02/15/25

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>CashFlowDate</th>
	  <th>CashFlowYearFrac</th>
	  <th>CashFlowAmount</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>58</th>
	  <td>August 15 th,  2024</td>
	  <td>0.333333</td>
	  <td>3.8125</td>
	</tr>
	<tr>
	  <th>59</th>
	  <td>February 15 th,  2025</td>
	  <td>0.833333</td>
	  <td>3.8125</td>
	</tr>
	<tr>
	  <th>60</th>
	  <td>February 15 th,  2025</td>
	  <td>0.833333</td>
	  <td>100.0000</td>
	</tr>
  </tbody>
</table>
</div>

    Corp bond future cashflows for AAPL 3.35 02/09/27

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>CashFlowDate</th>
	  <th>CashFlowYearFrac</th>
	  <th>CashFlowAmount</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>14</th>
	  <td>August 9 th,  2024</td>
	  <td>0.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>February 9 th,  2025</td>
	  <td>0.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>August 9 th,  2025</td>
	  <td>1.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>February 9 th,  2026</td>
	  <td>1.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>August 9 th,  2026</td>
	  <td>2.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>February 9 th,  2027</td>
	  <td>2.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>February 9 th,  2027</td>
	  <td>2.836111</td>
	  <td>100.000</td>
	</tr>
  </tbody>
</table>
</div>

# Problem 2: US Treasury yield curve calibration (On-The-Runs)

## a. Create the on-the-run US treasury bond objects

Restrict the symbology + market data dataframe to "on-the-run"/OTR US treasury notes/bonds only and create the treasury bond objects.

Extend the treasuries symbology dataframe with the following market data columns (code from Homework 1):

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
|----------|-------|-------------|-----|----------|---------|---------|---------|---------|

Plot a graph/scatter plot of on-the-run treasury mid yields by TTM.

```python
# Create symbology for on-the-run treasuries only
Govt_symbology_otr = bond_symbology[bond_symbology['isin']. Isin (govt_on_the_run_simple['isin'])]. Copy ()
Govt_symbology_otr = govt_symbology_otr. Sort_values (by='TTM')

# Merge market data as of 2024-04-01 into treasury OTR symbology
Govt_combined_otr = govt_symbology_otr.Merge (bond_market_prices_eod,           on=['class',         'ticker',         'figi',         'isin'])

# Plot a graph/scatter plot of treasury OTR mid yields by TTM
Govt_combined_otr.Plot (x='TTM',          y='midYield',          grid=True,          style='*-',          title='OTR US Treasury yields by TTM',          figsize=(12,         4))
```

    <Axes: title={'center': 'OTR US Treasury yields by TTM'},          xlabel='TTM'>
![png](CreditMarketSolutions_124_1.png)

## b. Calibrate the on-the-run treasury yield curve (bootstrapping)

The function below shows how to calibrate a smooth yield/discount factor curve from the on-the-run treasury dataframe.

Calibrate the bid,  ask and mid discount factor curves as of 2024-04-08.

Display the calibration results for the mid curve,  using get_yield_curve_details_df ().

```python
Def calibrate_yield_curve_from_frame (
        Calc_date: ql. Date,         
        Treasury_details: pd. DataFrame,         
        Price_quote_column: str):
    '''Create a calibrated yield curve from a details dataframe which includes bid/ask/mid price quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = treasury_details. Sort_values (by='maturity')    
    
    # For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)
    Day_count = ql.ActualActual (ql. ActualActual. ISMA)

    Bond_helpers = []
    
    For index,          row in sorted_details_frame.Iterrows ():
        Bond_object = create_bond_from_symbology (row)
        
        Tsy_clean_price_quote = row[price_quote_column]
        Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
        
        Bond_helper = ql.BondHelper (tsy_clean_price_handle,          bond_object)
        Bond_helpers.Append (bond_helper)
        
    Yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,          bond_helpers,          day_count)
    # yield_curve = ql.PiecewiseFlatForward (calc_date,          bond_helpers,          day_count)
    
    Yield_curve.EnableExtrapolation ()
    Return yield_curve
Def get_yield_curve_details_df (yield_curve,          curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),          3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),          3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,          yield_curve.DayCounter (),          ql. Compounded). Rate () * 100,          3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,         
                             'YearFrac': yearfracs,         
                             'DiscountFactor': discounts,         
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
```

```python
# Calibrate the bid,          ask and mid discount factor curves as of 2024-04-08.
Tsy_yield_curve_bid = calibrate_yield_curve_from_frame (calc_date,          govt_combined_otr,          'bidPrice')
Tsy_yield_curve_mid = calibrate_yield_curve_from_frame (calc_date,          govt_combined_otr,          'midPrice')
Tsy_yield_curve_ask = calibrate_yield_curve_from_frame (calc_date,          govt_combined_otr,          'askPrice')

# Display the calibration results for the mid curve
Tsy_yield_curve_df = get_yield_curve_details_df (tsy_yield_curve_mid)
Display (tsy_yield_curve_df)

Ql_dates_yearly = [calc_date + ql.Period (y,          ql. Years) for y in list (range (0,          30,          1))]
Tsy_yield_curve_monthly_df = get_yield_curve_details_df (tsy_yield_curve_mid,          curve_dates=ql_dates_yearly)
Display (tsy_yield_curve_monthly_df)

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>Date</th>
	  <th>YearFrac</th>
	  <th>DiscountFactor</th>
	  <th>ZeroRate</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>2024-04-08</td>
	  <td>0.000</td>
	  <td>1.000</td>
	  <td>5.025</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2026-03-31</td>
	  <td>2.000</td>
	  <td>0.907</td>
	  <td>4.982</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2027-04-15</td>
	  <td>3.000</td>
	  <td>0.866</td>
	  <td>4.910</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2029-03-31</td>
	  <td>5.000</td>
	  <td>0.795</td>
	  <td>4.683</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2031-03-31</td>
	  <td>7.000</td>
	  <td>0.726</td>
	  <td>4.675</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>2034-02-15</td>
	  <td>9.833</td>
	  <td>0.638</td>
	  <td>4.677</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>2044-02-15</td>
	  <td>19.833</td>
	  <td>0.382</td>
	  <td>4.968</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>2054-02-15</td>
	  <td>29.917</td>
	  <td>0.253</td>
	  <td>4.701</td>
	</tr>
  </tbody>
</table>
</div>

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>Date</th>
	  <th>YearFrac</th>
	  <th>DiscountFactor</th>
	  <th>ZeroRate</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>2024-04-08</td>
	  <td>0.0</td>
	  <td>1.000</td>
	  <td>5.025</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2025-04-08</td>
	  <td>1.0</td>
	  <td>0.952</td>
	  <td>5.014</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2026-04-08</td>
	  <td>2.0</td>
	  <td>0.907</td>
	  <td>4.982</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2027-04-08</td>
	  <td>3.0</td>
	  <td>0.866</td>
	  <td>4.910</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2028-04-08</td>
	  <td>4.0</td>
	  <td>0.830</td>
	  <td>4.776</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>2029-04-08</td>
	  <td>5.0</td>
	  <td>0.795</td>
	  <td>4.683</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>2030-04-08</td>
	  <td>6.0</td>
	  <td>0.761</td>
	  <td>4.667</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>2031-04-08</td>
	  <td>7.0</td>
	  <td>0.726</td>
	  <td>4.675</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>2032-04-08</td>
	  <td>8.0</td>
	  <td>0.694</td>
	  <td>4.672</td>
	</tr>
	<tr>
	  <th>9</th>
	  <td>2033-04-08</td>
	  <td>9.0</td>
	  <td>0.663</td>
	  <td>4.670</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>2034-04-08</td>
	  <td>10.0</td>
	  <td>0.633</td>
	  <td>4.680</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>2035-04-08</td>
	  <td>11.0</td>
	  <td>0.603</td>
	  <td>4.707</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>2036-04-08</td>
	  <td>12.0</td>
	  <td>0.573</td>
	  <td>4.745</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>2037-04-08</td>
	  <td>13.0</td>
	  <td>0.544</td>
	  <td>4.788</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>2038-04-08</td>
	  <td>14.0</td>
	  <td>0.517</td>
	  <td>4.831</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>2039-04-08</td>
	  <td>15.0</td>
	  <td>0.490</td>
	  <td>4.871</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>2040-04-08</td>
	  <td>16.0</td>
	  <td>0.465</td>
	  <td>4.907</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>2041-04-08</td>
	  <td>17.0</td>
	  <td>0.441</td>
	  <td>4.935</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>2042-04-08</td>
	  <td>18.0</td>
	  <td>0.419</td>
	  <td>4.955</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>2043-04-08</td>
	  <td>19.0</td>
	  <td>0.398</td>
	  <td>4.966</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>2044-04-08</td>
	  <td>20.0</td>
	  <td>0.379</td>
	  <td>4.967</td>
	</tr>
	<tr>
	  <th>21</th>
	  <td>2045-04-08</td>
	  <td>21.0</td>
	  <td>0.362</td>
	  <td>4.958</td>
	</tr>
	<tr>
	  <th>22</th>
	  <td>2046-04-08</td>
	  <td>22.0</td>
	  <td>0.346</td>
	  <td>4.941</td>
	</tr>
	<tr>
	  <th>23</th>
	  <td>2047-04-08</td>
	  <td>23.0</td>
	  <td>0.332</td>
	  <td>4.918</td>
	</tr>
	<tr>
	  <th>24</th>
	  <td>2048-04-08</td>
	  <td>24.0</td>
	  <td>0.318</td>
	  <td>4.890</td>
	</tr>
	<tr>
	  <th>25</th>
	  <td>2049-04-08</td>
	  <td>25.0</td>
	  <td>0.305</td>
	  <td>4.860</td>
	</tr>
	<tr>
	  <th>26</th>
	  <td>2050-04-08</td>
	  <td>26.0</td>
	  <td>0.294</td>
	  <td>4.827</td>
	</tr>
	<tr>
	  <th>27</th>
	  <td>2051-04-08</td>
	  <td>27.0</td>
	  <td>0.282</td>
	  <td>4.794</td>
	</tr>
	<tr>
	  <th>28</th>
	  <td>2052-04-08</td>
	  <td>28.0</td>
	  <td>0.272</td>
	  <td>4.761</td>
	</tr>
	<tr>
	  <th>29</th>
	  <td>2053-04-08</td>
	  <td>29.0</td>
	  <td>0.262</td>
	  <td>4.729</td>
	</tr>
  </tbody>
</table>
</div>

## c. Plot the calibrated US Treasury yield (zero rate) curves

Create a graph/scatter plot of the newly computed mid yields by maturity.

```python
Plt = tsy_yield_curve_df.Plot (x='Date',          y=['ZeroRate'],          style='*-',          grid=True,          title=f'US Treasury OTR yield curve as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = tsy_yield_curve_monthly_df.Plot (x='Date',          y=['ZeroRate'],          style='*-',          grid=True,          title=f'US Treasury Yearly yield curve as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

```

    Text (0.5,          0,          'Date')
![png](CreditMarketSolutions_129_1.png)

![png](CreditMarketSolutions_129_2.png)

## d. Plot calibrated discount factors

Plot the discount factor curve up to the 30 years point,  using a 6 months discretization grid.

```python
Plt = tsy_yield_curve_df.Plot (x='Date',          y=['DiscountFactor'],          style='*-',          grid=True,          title=f'US Treasury OTR discount factor curve as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Discount Factor')
Plt. Set_xlabel ('Date')

Plt = tsy_yield_curve_monthly_df.Plot (x='Date',          y=['DiscountFactor'],          style='*-',          grid=True,          title=f'US Treasury Yearly discount factor curve as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Discount Factor')
Plt. Set_xlabel ('Date')
```

    Text (0.5,          0,          'Date')
![png](CreditMarketSolutions_131_1.png)

![png](CreditMarketSolutions_131_2.png)

# Problem 3: Pricing and risk metrics for US Treasury bonds

## a. US Treasury pricing on the calibrated discount factor curve

Follow Section 5. "Bond Present Value Calculation (no credit risk)" in the QuantLib Basic notebook to re-price the US on-the-run treasuries using the calibrated discount factor curve.

You will need to switch the bond_engine to use the new on-the-run treasury yield curve:
Bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid)

Extend the dataframe with the following computed columns for clean mid prices:

| calc_mid_price |
|---------------|

To validate the calibration,  compare the calculated clean mid prices to the original market mid prices.

```python
# Create risk free bond_engine using calibrated US OTR yield curve
Tsy_yield_curve_mid_handle = ql.YieldTermStructureHandle (tsy_yield_curve_mid)
Bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)

# Calculate mid prices
Calculated_mid_prices = []
For index,          row in govt_combined_otr.Iterrows ():
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    Calculated_mid_prices.Append (bond_object.CleanPrice ())
    
Govt_combined_otr['calc_mid_price'] = calculated_mid_prices
Govt_combined_otr['calib_error'] = govt_combined_otr['midPrice'] - govt_combined_otr['calc_mid_price']

# Compare the calculated clean mid prices to the original market mid prices.
display (govt_combined_otr [['security',          'isin',          'figi',          'midPrice',          'calc_mid_price',          'calib_error']])
```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>midPrice</th>
	  <th>calc_mid_price</th>
	  <th>calib_error</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>T 4 1/2 03/31/26</td>
	  <td>US 91282 CKH 33</td>
	  <td>BBG 01 M 44 ZLG 5</td>
	  <td>99.10745</td>
	  <td>99.10745</td>
	  <td>-1.058709 e-11</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>T 4 1/2 04/15/27</td>
	  <td>US 91282 CKJ 98</td>
	  <td>BBG 01 M 9 L 5 M 64</td>
	  <td>99.11330</td>
	  <td>99.11330</td>
	  <td>-8.918732 e-11</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>T 4 1/8 03/31/29</td>
	  <td>US 91282 CKG 59</td>
	  <td>BBG 01 M 44 ZQJ 1</td>
	  <td>97.61330</td>
	  <td>97.61330</td>
	  <td>-2.130207 e-11</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>T 4 1/8 03/31/31</td>
	  <td>US 91282 CKF 76</td>
	  <td>BBG 01 M 44 ZS 07</td>
	  <td>96.89845</td>
	  <td>96.89845</td>
	  <td>7.219114 e-12</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>T 4 02/15/34</td>
	  <td>US 91282 CJZ 59</td>
	  <td>BBG 01 L 8 YJFB 3</td>
	  <td>95.13280</td>
	  <td>95.13280</td>
	  <td>-9.521273 e-13</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>T 4 1/2 02/15/44</td>
	  <td>US 912810 TZ 12</td>
	  <td>BBG 01 LK 8 Y 0 L 1</td>
	  <td>95.67970</td>
	  <td>95.67970</td>
	  <td>3.720402 e-11</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>T 4 1/4 02/15/54</td>
	  <td>US 912810 TX 63</td>
	  <td>BBG 01 L 8 YJKX 8</td>
	  <td>92.63285</td>
	  <td>92.63285</td>
	  <td>-6.167511 e-12</td>
	</tr>
  </tbody>
</table>
</div>

## b. Compute analytical DV 01,  Duration and Convexity for US on-the-run treasuries (using flat yield)

Compute analytical DV 01,  Duration and Convexity metrics,  as described in Section 7. "Analytical Duration,  Convexity and Z-Spread (flat yield model)" in the QuantLib Basic notebook.

Remember that DV 01 = Dirty_Price * Duration.

Extend the dataframe with the following calculated risk metrics:

| dv 01 | duration | convexity |
|-------|-------|-------------|

```python
# Set yield conventions
Compounding = ql. Compounded
Coupon_freq = ql. Semiannual

# Calculate dv 01 s,          durations and convexities
Dv 01 s = []
Calc_durations = []
Calc_convexities = []

For index,          row in govt_combined_otr.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()    
    
    Bond_yield = bond_object.BondYield (row['calc_mid_price'],          day_counter,          compounding,          coupon_freq,          settle_date) * 100
    
    Flat_int_rate = ql.InterestRate (bond_yield / 100,          day_counter,          compounding,          coupon_freq)
    Bond_duration = ql.BondFunctions.Duration (bond_object,          flat_int_rate)
    Bond_convexity = ql.BondFunctions.Convexity (bond_object,          flat_int_rate)
    Bond_dv 01 = bond_object.DirtyPrice () * bond_duration / 100
    
    Dv 01 s.Append (bond_dv 01)
    Calc_durations.Append (bond_duration)
    Calc_convexities.Append (bond_convexity)

# Add new risk columns and display results    
Govt_combined_otr['dv 01'] = dv 01 s
Govt_combined_otr['duration'] = calc_durations
Govt_combined_otr['convexity'] = calc_convexities

display (govt_combined_otr [['security',          'isin',          'figi',          'calc_mid_price',          'dv01',          'duration',          'convexity']])

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>calc_mid_price</th>
	  <th>dv 01</th>
	  <th>duration</th>
	  <th>convexity</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>T 4 1/2 03/31/26</td>
	  <td>US 91282 CKH 33</td>
	  <td>BBG 01 M 44 ZLG 5</td>
	  <td>99.10745</td>
	  <td>1.849051</td>
	  <td>1.863622</td>
	  <td>4.451242</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>T 4 1/2 04/15/27</td>
	  <td>US 91282 CKJ 98</td>
	  <td>BBG 01 M 9 L 5 M 64</td>
	  <td>99.11330</td>
	  <td>2.747474</td>
	  <td>2.772054</td>
	  <td>9.297408</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>T 4 1/8 03/31/29</td>
	  <td>US 91282 CKG 59</td>
	  <td>BBG 01 M 44 ZQJ 1</td>
	  <td>97.61330</td>
	  <td>4.333122</td>
	  <td>4.434461</td>
	  <td>22.994377</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>T 4 1/8 03/31/31</td>
	  <td>US 91282 CKF 76</td>
	  <td>BBG 01 M 44 ZS 07</td>
	  <td>96.89845</td>
	  <td>5.791786</td>
	  <td>5.970920</td>
	  <td>41.667226</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>T 4 02/15/34</td>
	  <td>US 91282 CJZ 59</td>
	  <td>BBG 01 L 8 YJFB 3</td>
	  <td>95.13280</td>
	  <td>7.615610</td>
	  <td>7.955616</td>
	  <td>75.391888</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>T 4 1/2 02/15/44</td>
	  <td>US 912810 TZ 12</td>
	  <td>BBG 01 LK 8 Y 0 L 1</td>
	  <td>95.67970</td>
	  <td>12.302563</td>
	  <td>12.768977</td>
	  <td>216.798414</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>T 4 1/4 02/15/54</td>
	  <td>US 912810 TX 63</td>
	  <td>BBG 01 L 8 YJKX 8</td>
	  <td>92.63285</td>
	  <td>15.088734</td>
	  <td>16.178632</td>
	  <td>378.784333</td>
	</tr>
  </tbody>
</table>
</div>

## c. Compute scenario DV 01,  Duration and Convexity for US on-the-run treasuries (using calibrated yield curve)

Compute the scenario DV 01,  Duration and Convexity metrics using +/-1 bp interest rate shocks,  as described in Section 6. "Market Data Scenarios" in the QuantLib Basic notebook.

Remember that DV 01 = Dirty_Price * Duration.

Extend the dataframe with the following scenario sensitivities metrics:

| scen_dv 01 | scen_duration | scen_convexity |
|-------|-------|-------------|

```python
# Calculate scenario dv 01 s,          durations and convexities
Scen_dv 01 s = []
Scen_durations = []
Scen_convexities = []

For index,          row in govt_combined_otr.Iterrows ():
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    # create interest rate scenarios
    Interest_rate_bump = ql.SimpleQuote (0.0)
    Calibrated_yield_curve_bumped = ql.ZeroSpreadedTermStructure (tsy_yield_curve_mid_handle,          ql.QuoteHandle (interest_rate_bump))
    Bond_engine_bumped = ql.DiscountingBondEngine (ql.YieldTermStructureHandle (calibrated_yield_curve_bumped))
    Bond_object.SetPricingEngine (bond_engine_bumped)
    Dirty_price_base = bond_object.DirtyPrice ()
    
    # Create +1 bp scenario
    Interest_rate_bump.SetValue (0.0001)
    Dirty_price_plus = bond_object.DirtyPrice ()    
    
    # Create -1 bp scenario
    Interest_rate_bump.SetValue (-0.0001)
    Dirty_price_minus = bond_object.DirtyPrice ()
    
    # Calc scenario risks        
    Scen_dv 01 = (dirty_price_minus - dirty_price_base)*100
    Scen_duration = scen_dv 01  / dirty_price_base * 100
    Scen_convexity = (dirty_price_plus + dirty_price_minus - 2 * dirty_price_base) / (dirty_price_base * 0.0001**2)
    
    Scen_dv 01 s.Append (scen_dv 01)
    Scen_durations.Append (scen_duration)
    Scen_convexities.Append (scen_convexity)

# Add new scenario risk columns and display results
Govt_combined_otr['scen_dv 01'] = scen_dv 01 s
Govt_combined_otr['scen_duration'] = scen_durations
Govt_combined_otr['scen_convexity'] = scen_convexities

display (govt_combined_otr [['security',          'isin',          'figi',         'scen_dv01',          'scen_duration',          'scen_convexity']])

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>scen_dv 01</th>
	  <th>scen_duration</th>
	  <th>scen_convexity</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>T 4 1/2 03/31/26</td>
	  <td>US 91282 CKH 33</td>
	  <td>BBG 01 M 44 ZLG 5</td>
	  <td>1.917009</td>
	  <td>1.932116</td>
	  <td>3.804732</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>T 4 1/2 04/15/27</td>
	  <td>US 91282 CKJ 98</td>
	  <td>BBG 01 M 9 L 5 M 64</td>
	  <td>2.795157</td>
	  <td>2.820163</td>
	  <td>8.223355</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>T 4 1/8 03/31/29</td>
	  <td>US 91282 CKG 59</td>
	  <td>BBG 01 M 44 ZQJ 1</td>
	  <td>4.458591</td>
	  <td>4.562865</td>
	  <td>22.023635</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>T 4 1/8 03/31/31</td>
	  <td>US 91282 CKF 76</td>
	  <td>BBG 01 M 44 ZS 07</td>
	  <td>5.953203</td>
	  <td>6.137330</td>
	  <td>40.873603</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>T 4 02/15/34</td>
	  <td>US 91282 CJZ 59</td>
	  <td>BBG 01 L 8 YJFB 3</td>
	  <td>7.778639</td>
	  <td>8.125924</td>
	  <td>74.548926</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>T 4 1/2 02/15/44</td>
	  <td>US 912810 TZ 12</td>
	  <td>BBG 01 LK 8 Y 0 L 1</td>
	  <td>12.535804</td>
	  <td>13.011061</td>
	  <td>218.735445</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>T 4 1/4 02/15/54</td>
	  <td>US 912810 TX 63</td>
	  <td>BBG 01 L 8 YJKX 8</td>
	  <td>15.492212</td>
	  <td>16.611255</td>
	  <td>390.983324</td>
	</tr>
  </tbody>
</table>
</div>

# Problem 4: Pricing and risk metrics for [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]

## a. Create the fixed-rate corporate bond objects

Restrict the symbology dataframe to fixed rate [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] only and create the corporate bond objects.

```python
# Create the fixed-rate corporate bond symbology + combined dataframes
Corp_symbology = bond_symbology[bond_symbology['cpn_type'] == 'FIXED']
Corp_combined = corp_symbology.Merge (bond_market_prices_eod,           on=['class',         'ticker',         'figi',         'isin'])

Display (corp_combined.Head ())
```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>ticker</th>
	  <th>class</th>
	  <th>figi</th>
	  <th>isin</th>
	  <th>und_bench_isin</th>
	  <th>security</th>
	  <th>name</th>
	  <th>type</th>
	  <th>coupon</th>
	  <th>cpn_type</th>
	  <th>…</th>
	  <th>term</th>
	  <th>TTM</th>
	  <th>date</th>
	  <th>bidPrice</th>
	  <th>askPrice</th>
	  <th>accrued</th>
	  <th>bidYield</th>
	  <th>askYield</th>
	  <th>midPrice</th>
	  <th>midYield</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>US 037833 AL 42</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>3.850</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>30.001369</td>
	  <td>19.069131</td>
	  <td>2024-04-19</td>
	  <td>82.155</td>
	  <td>82.733</td>
	  <td>1.8070</td>
	  <td>5.357</td>
	  <td>5.302</td>
	  <td>82.4440</td>
	  <td>5.3295</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>US 037833 AT 77</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.450</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>30.001369</td>
	  <td>20.076660</td>
	  <td>2024-04-19</td>
	  <td>89.955</td>
	  <td>90.676</td>
	  <td>2.0645</td>
	  <td>5.267</td>
	  <td>5.205</td>
	  <td>90.3155</td>
	  <td>5.2360</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>US 037833 BA 77</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>3.450</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>30.001369</td>
	  <td>20.840520</td>
	  <td>2024-04-19</td>
	  <td>75.944</td>
	  <td>76.561</td>
	  <td>0.7095</td>
	  <td>5.387</td>
	  <td>5.328</td>
	  <td>76.2525</td>
	  <td>5.3575</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>US 037833 BH 21</td>
	  <td>US 912810 TZ 12</td>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.375</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>30.001369</td>
	  <td>21.095140</td>
	  <td>2024-04-19</td>
	  <td>87.214</td>
	  <td>87.825</td>
	  <td>1.9445</td>
	  <td>5.399</td>
	  <td>5.345</td>
	  <td>87.5195</td>
	  <td>5.3720</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>AAPL</td>
	  <td>Corp</td>
	  <td>BBG 00 C 7 QBCQ 1</td>
	  <td>US 037833 BW 97</td>
	  <td>US 91282 CJZ 59</td>
	  <td>AAPL 4 1/2 02/23/36</td>
	  <td>APPLE INC</td>
	  <td>GLOBAL</td>
	  <td>4.500</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>20.000000</td>
	  <td>11.876797</td>
	  <td>2024-04-19</td>
	  <td>95.507</td>
	  <td>95.927</td>
	  <td>0.7500</td>
	  <td>5.007</td>
	  <td>4.958</td>
	  <td>95.7170</td>
	  <td>4.9825</td>
	</tr>
  </tbody>
</table>
<p>5 rows × 33 columns</p>
</div>

```python
# Create the corporate bond objects and store them in a dictionary
Corp_bond_object_dict = {}

For index,          row in corp_combined.Iterrows ():
    Bond_details = row. To_dict ()
    Corp_bond_object = create_bond_from_symbology (bond_details)
    Corp_bond_object_dict[row['security']] = corp_bond_object
    
# Display the future cashflows for one corp bond object in the dictionary
Corp_bond_key = corp_combined. Iloc[10]['security']
Corp_bond_cf = get_bond_cashflows (corp_bond_object_dict[corp_bond_key],          calc_date=calc_date)

Print ("Corp bond future cashflows for",          corp_bond_key)
Display (corp_bond_cf)
```

    Corp bond future cashflows for AAPL 3.35 02/09/27

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>CashFlowDate</th>
	  <th>CashFlowYearFrac</th>
	  <th>CashFlowAmount</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>14</th>
	  <td>August 9 th,  2024</td>
	  <td>0.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>February 9 th,  2025</td>
	  <td>0.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>August 9 th,  2025</td>
	  <td>1.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>February 9 th,  2026</td>
	  <td>1.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>August 9 th,  2026</td>
	  <td>2.336111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>February 9 th,  2027</td>
	  <td>2.836111</td>
	  <td>1.675</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>February 9 th,  2027</td>
	  <td>2.836111</td>
	  <td>100.000</td>
	</tr>
  </tbody>
</table>
</div>

## b. Compute analytical Yields and Z-Spreads

Compute analytical Yields and Z-Spreads metrics,  as described in Section 7. "Analytical Duration,  Convexity and Z-Spread (flat yield model)" in the QuantLib Basic notebook.

Extend the dataframe with the following calculated risk metrics:

| calc_yield | calc_zspread |
|-------|-------------|

```python
# Create risk free bond engine
Bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)

# Set yield conventions
Compounding = ql. Compounded
Coupon_freq = ql. Semiannual

# Calculate yields and zspreads
Calc_yields = []
Calc_zspreads = []

For index,          row in corp_combined.Iterrows ():
        
    Bond_object = create_bond_from_symbology (row)    
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()

    Clean_price = bond_object.CleanPrice ()
    
    # yield in pct
    Calc_yield = bond_object.BondYield (clean_price,          day_counter,          compounding,          coupon_freq,          settle_date) * 1 e 2
    Flat_int_rate = ql.InterestRate (calc_yield / 100,          day_counter,          compounding,          coupon_freq)
    Bond_market_price = row['midPrice']
    
    # zspread in bps
    Calc_zspread = ql.BondFunctions.ZSpread (bond_object,          bond_market_price,          tsy_yield_curve_mid,          day_counter,          compounding,          coupon_freq,          settle_date) * 1 e 4
    
    Calc_yields.Append (calc_yield)
    Calc_zspreads.Append (calc_zspread)

# Add new columns and display results
Corp_combined['calc_yield'] = calc_yields
Corp_combined['calc_zspread'] = calc_zspreads

display (corp_combined [['security',          'isin',          'figi',          'midPrice',          'calc_yield',          'calc_zspread']])

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>midPrice</th>
	  <th>calc_yield</th>
	  <th>calc_zspread</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>82.4440</td>
	  <td>4.856568</td>
	  <td>47.185879</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>90.3155</td>
	  <td>4.850879</td>
	  <td>38.554147</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>76.2525</td>
	  <td>4.852979</td>
	  <td>50.409844</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>US 037833 BH 21</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>87.5195</td>
	  <td>4.839887</td>
	  <td>53.364752</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>AAPL 4 1/2 02/23/36</td>
	  <td>US 037833 BW 97</td>
	  <td>BBG 00 C 7 QBCQ 1</td>
	  <td>95.7170</td>
	  <td>4.703094</td>
	  <td>27.719772</td>
	</tr>
	<tr>
	  <th>…</th>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	</tr>
	<tr>
	  <th>765</th>
	  <td>VZ 4 1/8 03/16/27</td>
	  <td>US 92343 VDY 74</td>
	  <td>BBG 00 G 6 QW 2 B 8</td>
	  <td>96.8010</td>
	  <td>4.823859</td>
	  <td>49.623387</td>
	</tr>
	<tr>
	  <th>766</th>
	  <td>VZ 2 5/8 08/15/26</td>
	  <td>US 92343 VDD 38</td>
	  <td>BBG 00 DGYP 877</td>
	  <td>94.0115</td>
	  <td>4.864209</td>
	  <td>51.321929</td>
	</tr>
	<tr>
	  <th>767</th>
	  <td>VZ 1.1 06/15/26</td>
	  <td>US 92346 MHD 65</td>
	  <td>BBG 011 C 76 F 52</td>
	  <td>89.8095</td>
	  <td>4.869580</td>
	  <td>130.763458</td>
	</tr>
	<tr>
	  <th>768</th>
	  <td>VZ 1.05 06/15/26</td>
	  <td>US 92346 MHG 96</td>
	  <td>BBG 011 F 6 KFX 4</td>
	  <td>89.7155</td>
	  <td>4.869594</td>
	  <td>130.413052</td>
	</tr>
	<tr>
	  <th>769</th>
	  <td>VZ 1.45 03/20/26</td>
	  <td>US 92343 VGG 32</td>
	  <td>BBG 00 ZLKTF 09</td>
	  <td>92.8615</td>
	  <td>4.838803</td>
	  <td>53.518133</td>
	</tr>
  </tbody>
</table>
<p>770 rows × 6 columns</p>
</div>

## c. Validate Z-Spread computation for a few fixed rate [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]

Pick 3 [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] (at your discretion) and use function below to re-price them using the calibrated flat z-spread. Follow the example in Section 7. "Analytical Duration,  Convexity and Z-Spread (flat yield model)".

Validate that you match the original market prices,  which were used as input to the z-Spread function.

```python
Def calc_clean_price_with_zspread (fixed_rate_bond,          yield_curve_handle,          zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,          zspread_quote_handle,          ql. Compounded,          ql. Semiannual)
    Yield_curve_bumped_handle = ql.YieldTermStructureHandle (yield_curve_bumped)
    
    # Set Valuation engine
    Bond_engine = ql.DiscountingBondEngine (yield_curve_bumped_handle)
    Fixed_rate_bond.SetPricingEngine (bond_engine)
    Bond_clean_price = fixed_rate_bond.CleanPrice ()
    Return bond_clean_price

```

```python
# Create risk free bond engine
Bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)

# Set yield conventions
Compounding = ql. Compounded
Coupon_freq = ql. Semiannual

# Pick 3 [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] (at your discretion)
Corp_combined_small = corp_combined[: 3]. Copy ()

# Calculate prices with zspreads
Bond_zspread_prices = []

For index,          row in corp_combined_small.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)    
    Bond_object.SetPricingEngine (bond_engine)
        
    Bond_zspread_price = calc_clean_price_with_zspread (bond_object,          tsy_yield_curve_mid_handle,          row['calc_zspread']/1 e 4)
    Bond_zspread_prices.Append (bond_zspread_price)
    
# Validate that you match the original market prices,          which were used as input to the z-Spread function.
Corp_combined_small['bond_zspread_price'] = bond_zspread_prices
Corp_combined_small['price_difference'] = corp_combined_small['midPrice'] - corp_combined_small['bond_zspread_price']

display (corp_combined_small [['security',          'isin',          'figi',          'calc_zspread',          'midPrice',          'bond_zspread_price',         'price_difference']])
```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>calc_zspread</th>
	  <th>midPrice</th>
	  <th>bond_zspread_price</th>
	  <th>price_difference</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>47.185879</td>
	  <td>82.4440</td>
	  <td>82.4440</td>
	  <td>1.153637 e-10</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>38.554147</td>
	  <td>90.3155</td>
	  <td>90.3155</td>
	  <td>5.365720 e-09</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>50.409844</td>
	  <td>76.2525</td>
	  <td>76.2525</td>
	  <td>1.136868 e-13</td>
	</tr>
  </tbody>
</table>
</div>

## d. Compute Duration and Convexity for fixed rate [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] (using flat yield)

Compute analytical Duration and Convexity metrics,  as described in Section 7. "Analytical Duration,  Convexity and Z-Spread (flat yield model)" in the QuantLib Basic notebook.

Extend the dataframe with the following calculated risk metrics:

| calc_duration | calc_convexity |
|-------|-------------|

Display the head of the dataframe.

```python
# Create risk free bond engine
Bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)

# Set yield conventions
Compounding = ql. Compounded
Coupon_freq = ql. Semiannual

# Calculate durations and convexities
Calc_durations = []
Calc_convexities = []

For index,          row in corp_combined.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()    
    
    Bond_yield = bond_object.BondYield (row['midPrice'],          day_counter,          compounding,          coupon_freq,          settle_date) * 100
    
    Flat_int_rate = ql.InterestRate (bond_yield / 100,          day_counter,          compounding,          coupon_freq)
    Bond_duration = ql.BondFunctions.Duration (bond_object,          flat_int_rate)
    Bond_convexity = ql.BondFunctions.Convexity (bond_object,          flat_int_rate)        
    
    Calc_durations.Append (bond_duration)
    Calc_convexities.Append (bond_convexity)

# Add new risk columns and display results
Corp_combined['calc_duration'] = calc_durations
Corp_combined['calc_convexity'] = calc_convexities

display (corp_combined [['security',          'isin',          'figi',          'midPrice',          'calc_duration',          'calc_convexity']]. head ())

```

<div>
<style scoped>
	.dataframe tbody tr th: only-of-type {
		Vertical-align: middle;
	}

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
	<tr style="text-align: right;">
	  <th></th>
	  <th>security</th>
	  <th>isin</th>
	  <th>figi</th>
	  <th>midPrice</th>
	  <th>calc_duration</th>
	  <th>calc_convexity</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>82.4440</td>
	  <td>12.457334</td>
	  <td>206.273029</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>90.3155</td>
	  <td>12.495140</td>
	  <td>212.739235</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>76.2525</td>
	  <td>13.575123</td>
	  <td>243.879961</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>US 037833 BH 21</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>87.5195</td>
	  <td>12.825713</td>
	  <td>226.836395</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>AAPL 4 1/2 02/23/36</td>
	  <td>US 037833 BW 97</td>
	  <td>BBG 00 C 7 QBCQ 1</td>
	  <td>95.7170</td>
	  <td>8.978502</td>
	  <td>99.027501</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Visualize duration and convexity for one ticker (for better understanding of risks) [Not part of homework]
Corp_combined_aapl = corp_combined[corp_combined['ticker'] == 'AAPL']

Plt = corp_combined_aapl.Plot (x='maturity',          y=['calc_duration'],          style='*-',          grid=True,          title=f'Duration for AAPL bonds as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Duration')
Plt. Set_xlabel ('Maturity date')

Plt = corp_combined_aapl.Plot (x='maturity',          y=['calc_convexity'],          style='*-',          grid=True,          title=f'Convexity for AAPL bonds as of {as_of_date.Date ()}',          figsize=(12,         4))
Plt. Set_ylabel ('Convexity')
Plt. Set_xlabel ('Maturity date')

```

    Text (0.5,          0,          'Maturity date')
![png](CreditMarketSolutions_150_1.png)

![png](CreditMarketSolutions_150_2.png)
