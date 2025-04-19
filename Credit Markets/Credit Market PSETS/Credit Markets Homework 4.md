---
title: Credit Markets Homework 4
tags:
  - bond_duration
  - bond_valuation
  - cds_pricing
  - credit_market_homework
  - hazard_rate_model
  - ibm_bonds
  - ir01
  - risky_bonds
  - scenario_analysis
aliases:
  - Bond Sensitivities
  - Credit Markets HW4
  - Homework 4
  - Risky Bond Pricing
key_concepts:
  - Bond duration calculation
  - Bond market data
  - CDS hazard rate
  - CDS-implied prices
  - Intrinsic vs market basis
  - Risky bond pricing
  - Scenario IR 01
  - Yield curve calibration
---

# Credit Markets Homework 4

This homework relies on multiple files (from previous weeks):

- The bond symbology file `bond_symbology`,
- The "on-the-run" treasuries data file `govt_on_the_run`,
- The bond market data file `bond_market_prices_eod`,
- The CDS data file `cds_market_data_eod`.
- The SOFR Is Swap symbology file `sofr_swap_symbology`,
- The SOFR Is Swap market data file `sofr_swaps_market_data_eod`.

```python
# Import tools from previous homeworks
From credit_market_tools import *

# Use static calculation/valuation date of 2024-04-19,            matching data available in the market prices EOD file
Calc_date = ql.Date (19,            4,            2024)
Ql.Settings.Instance (). EvaluationDate = calc_date

# Calculation/valuation date as pd datetime
As_of_date = pd. To_datetime ('2024-04-19')
```

-----------------------------------------------------------
# Problem 1: Pricing risky bonds in the hazard rate model
## This is building upon
- Homework 2 "Problem 2: US Treasury yield curve calibration (On-The-Runs)",
- Homework 3 "Problem 3: US SOFR swap curve calibration" and
- Homework 3 "Problem 4: CDS Hazard Rate calibration".

## a. Prepare the market data
### Load the symbology + market data dataframes. Calibrate the following curves as of 2024-04-19
- The "on-the-run" US Treasury curve,
- The US SOFR curve and
- The IBM CDS hazard rate curve (on the top of SOFR discount curve).

```python
# US Treasury "On-The-Run" yield curve calibration
# Follow Homework 2 Problem 2 and populate the US Treasury On-The-Run symbology + market data frame

# Load bond_symbology. Xlsx
Bond_symbology  = pd. Read_excel ('./data/bond_symbology. Xlsx')
Bond_symbology  = bond_symbology[bond_symbology['cpn_type'] == 'FIXED']

# Add term and TTM columns
Bond_symbology['term'] = (bond_symbology['maturity'] - bond_symbology['start_date']). Dt. Days / 365.25
Bond_symbology['TTM'] = (bond_symbology['maturity'] - as_of_date). Dt. Days / 365.25

# Load bond_market_prices_eod
Bond_market_prices_eod = pd. Read_excel ('./data/bond_market_prices_eod. Xlsx')

# Add mid prices and yields
Bond_market_prices_eod['midPrice'] = 0.5*(bond_market_prices_eod['bidPrice'] + bond_market_prices_eod['askPrice'])
Bond_market_prices_eod['midYield'] = 0.5*(bond_market_prices_eod['bidYield'] + bond_market_prices_eod['askYield'])

# Load govt_on_the_run,            as of 2024-04-19
Govt_on_the_run = pd. Read_excel ('./data/govt_on_the_run. Xlsx')

# Keep OTR treasuries only
Govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run['ticker']. Str.Contains ('B|C')]

# Create symbology for on-the-run treasuries only
Govt_symbology_otr = bond_symbology[bond_symbology['isin']. Isin (govt_on_the_run_simple['isin'])]. Copy ()
Govt_symbology_otr = govt_symbology_otr. Sort_values (by='maturity')

# Merge market data as of 2024-04-19 into treasury OTR symbology
Govt_combined_otr = govt_symbology_otr.Merge (bond_market_prices_eod,             on=['class',           'ticker',           'figi',           'isin'])
Display (govt_combined_otr.Head ())

# Tsy_yield_curve calibration
Tsy_yield_curve = calibrate_yield_curve_from_frame (calc_date,            govt_combined_otr,            'midPrice')
Tsy_yield_curve_handle = ql.YieldTermStructureHandle (tsy_yield_curve)
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
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 M 44 ZLG 5</td>
	  <td>US 91282 CKH 33</td>
	  <td>US 91282 CKH 33</td>
	  <td>T 4 1/2 03/31/26</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.500</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1.995893</td>
	  <td>1.946612</td>
	  <td>2024-04-19</td>
	  <td>99.1055</td>
	  <td>99.1094</td>
	  <td>0.26955</td>
	  <td>4.988</td>
	  <td>4.986</td>
	  <td>99.10745</td>
	  <td>4.9870</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 M 9 L 5 M 64</td>
	  <td>US 91282 CKJ 98</td>
	  <td>US 91282 CKJ 98</td>
	  <td>T 4 1/2 04/15/27</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.500</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2.997947</td>
	  <td>2.986995</td>
	  <td>2024-04-19</td>
	  <td>99.1094</td>
	  <td>99.1172</td>
	  <td>0.08590</td>
	  <td>4.824</td>
	  <td>4.821</td>
	  <td>99.11330</td>
	  <td>4.8225</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 M 44 ZQJ 1</td>
	  <td>US 91282 CKG 59</td>
	  <td>US 91282 CKG 59</td>
	  <td>T 4 1/8 03/31/29</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.125</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>4.996578</td>
	  <td>4.947296</td>
	  <td>2024-04-19</td>
	  <td>97.6094</td>
	  <td>97.6172</td>
	  <td>0.24800</td>
	  <td>4.672</td>
	  <td>4.670</td>
	  <td>97.61330</td>
	  <td>4.6710</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 M 44 ZS 07</td>
	  <td>US 91282 CKF 76</td>
	  <td>US 91282 CKF 76</td>
	  <td>T 4 1/8 03/31/31</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.125</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>6.995209</td>
	  <td>6.945927</td>
	  <td>2024-04-19</td>
	  <td>96.8906</td>
	  <td>96.9063</td>
	  <td>0.24805</td>
	  <td>4.654</td>
	  <td>4.651</td>
	  <td>96.89845</td>
	  <td>4.6525</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 L 8 YJFB 3</td>
	  <td>US 91282 CJZ 59</td>
	  <td>US 91282 CJZ 59</td>
	  <td>T 4 02/15/34</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.000</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>10.001369</td>
	  <td>9.826146</td>
	  <td>2024-04-19</td>
	  <td>95.1250</td>
	  <td>95.1406</td>
	  <td>0.73630</td>
	  <td>4.623</td>
	  <td>4.621</td>
	  <td>95.13280</td>
	  <td>4.6220</td>
	</tr>
  </tbody>
</table>
<p>5 rows × 33 columns</p>
</div>

```python
# SOFR risk-free yield curve calibration
# Follow Homework 3 Problem 3 and populate the SOFR symbology + market data frame

# Sofr_symbology
Sofr_symbology = pd. Read_excel ('./data/sofr_swaps_symbology. Xlsx')
Sofr_symbology. Set_index ('figi',            inplace=True)
Display (sofr_symbology)

# Sofr_market_quotes
Sofr_market_quotes = pd. Read_excel ('./data/sofr_swaps_market_data_eod. Xlsx')

# Sofr_combined
Sofr_combined = sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes['date'] == as_of_date],            how='left',            on=['figi'])
Display (sofr_combined.Head ())

# Sofr_yield_curve calibration
Sofr_yield_curve = calibrate_sofr_curve_from_frame (calc_date,            sofr_combined,            'midRate')
Sofr_yield_curve_handle = ql.YieldTermStructureHandle (sofr_yield_curve)

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
	  <th>bbg</th>
	  <th>name</th>
	  <th>tenor</th>
	  <th>type</th>
	  <th>dcc</th>
	  <th>exchange</th>
	  <th>country</th>
	  <th>currency</th>
	  <th>status</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 KFWPJJ 9</th>
	  <td>USOSFR 1</td>
	  <td>Curncy</td>
	  <td>USOSFR 1 Curncy</td>
	  <td>USD Is ANN VS SOFR 1 Y</td>
	  <td>1</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPJX 3</th>
	  <td>USOSFR 2</td>
	  <td>Curncy</td>
	  <td>USOSFR 2 Curncy</td>
	  <td>USD Is ANN VS SOFR 2 Y</td>
	  <td>2</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPK 15</th>
	  <td>USOSFR 3</td>
	  <td>Curncy</td>
	  <td>USOSFR 3 Curncy</td>
	  <td>USD Is ANN VS SOFR 3 Y</td>
	  <td>3</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPK 51</th>
	  <td>USOSFR 5</td>
	  <td>Curncy</td>
	  <td>USOSFR 5 Curncy</td>
	  <td>USD Is ANN VS SOFR 5 Y</td>
	  <td>5</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPK 79</th>
	  <td>USOSFR 7</td>
	  <td>Curncy</td>
	  <td>USOSFR 7 Curncy</td>
	  <td>USD Is ANN VS SOFR 7 Y</td>
	  <td>7</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPKB 4</th>
	  <td>USOSFR 10</td>
	  <td>Curncy</td>
	  <td>USOSFR 10 Curncy</td>
	  <td>USD Is ANN VS SOFR 10 Y</td>
	  <td>10</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPKF 0</th>
	  <td>USOSFR 20</td>
	  <td>Curncy</td>
	  <td>USOSFR 20 Curncy</td>
	  <td>USD Is ANN VS SOFR 20 Y</td>
	  <td>20</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>BBG 00 KFWPKH 8</th>
	  <td>USOSFR 30</td>
	  <td>Curncy</td>
	  <td>USOSFR 30 Curncy</td>
	  <td>USD Is ANN VS SOFR 30 Y</td>
	  <td>30</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
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
	  <th>figi</th>
	  <th>ticker</th>
	  <th>class</th>
	  <th>bbg</th>
	  <th>name</th>
	  <th>tenor</th>
	  <th>type</th>
	  <th>dcc</th>
	  <th>exchange</th>
	  <th>country</th>
	  <th>currency</th>
	  <th>status</th>
	  <th>date</th>
	  <th>bidRate</th>
	  <th>askRate</th>
	  <th>midRate</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>BBG 00 KFWPJJ 9</td>
	  <td>USOSFR 1</td>
	  <td>Curncy</td>
	  <td>USOSFR 1 Curncy</td>
	  <td>USD Is ANN VS SOFR 1 Y</td>
	  <td>1</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>2024-04-19</td>
	  <td>5.2149</td>
	  <td>5.2202</td>
	  <td>5.21755</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>BBG 00 KFWPJX 3</td>
	  <td>USOSFR 2</td>
	  <td>Curncy</td>
	  <td>USOSFR 2 Curncy</td>
	  <td>USD Is ANN VS SOFR 2 Y</td>
	  <td>2</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>2024-04-19</td>
	  <td>4.8913</td>
	  <td>4.8964</td>
	  <td>4.89385</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>BBG 00 KFWPK 15</td>
	  <td>USOSFR 3</td>
	  <td>Curncy</td>
	  <td>USOSFR 3 Curncy</td>
	  <td>USD Is ANN VS SOFR 3 Y</td>
	  <td>3</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>2024-04-19</td>
	  <td>4.6687</td>
	  <td>4.6761</td>
	  <td>4.67240</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>BBG 00 KFWPK 51</td>
	  <td>USOSFR 5</td>
	  <td>Curncy</td>
	  <td>USOSFR 5 Curncy</td>
	  <td>USD Is ANN VS SOFR 5 Y</td>
	  <td>5</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>2024-04-19</td>
	  <td>4.4148</td>
	  <td>4.4184</td>
	  <td>4.41660</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>BBG 00 KFWPK 79</td>
	  <td>USOSFR 7</td>
	  <td>Curncy</td>
	  <td>USOSFR 7 Curncy</td>
	  <td>USD Is ANN VS SOFR 7 Y</td>
	  <td>7</td>
	  <td>SWAP</td>
	  <td>ACT/360</td>
	  <td>NONE</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>2024-04-19</td>
	  <td>4.3090</td>
	  <td>4.3122</td>
	  <td>4.31060</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Credit curve calibration using IBM CDS par spreads 
# Follow Homework 3 Problem 4 and create the IBM hazard rate curve

# Cds_market_quotes
Cds_market_quotes = pd. Read_excel ('./data/cds_market_data_eod. Xlsx')

# Create par spreads (bps) dataframe
Par_spread_col_names = [f'par_spread_{n}y' for n in [1,           2,           3,           5,           7,           10]]
Cds_par_spreads_df = cds_market_quotes. Set_index ('date')[par_spread_col_names]

Cds_par_spreads = list (cds_par_spreads_df. Loc[as_of_date])
Print (cds_par_spreads)

# Cds_recovery_rate
Cds_recovery_rate = 0.4

# Hazard_rate_curve
Hazard_rate_curve = calibrate_cds_hazard_rate_curve (calc_date,            sofr_yield_curve_handle,            cds_par_spreads,            cds_recovery_rate)

# Hazard_rate_curve calibrated to IBM CDS par spreads
Default_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)
```

    [12.0769,            17.3082,            24.866,            39.6501,            53.9093,            65.3221]

## b. Create the IBM risky bond objects
### Identify the following 3 IBM fixed rate bonds in the symbology table and create the corresponding fixed rate bonds (3 bond objects)

- Security = 'IBM 3.3 05/15/26' / figi = 'BBG 00 P 3 BLH 05'
- Security = 'IBM 3.3 01/27/27' / figi = 'BBG 00 FVNGFP 3'
- Security = 'IBM 3 1/2 05/15/29' / figi = 'BBG 00 P 3 BLH 14'

Use the create_bond_from_symbology () function (discussed in from Homework 2,  Problem 1 b) to create the bonds objects.

List the bond cashflows using the get_bond_cashflows () function.

```python
# Corp_symbology_ibm
Corp_symbology_ibm = bond_symbology[(bond_symbology. Ticker == 'IBM') & (bond_symbology. Cpn_type == 'FIXED')]

# Corp_combined_ibm
Corp_combined_ibm = corp_symbology_ibm.Merge (bond_market_prices_eod,            how='inner',            on=['class',            'ticker',            'isin',            'figi'])
Corp_combined_ibm. Set_index ('figi',            inplace=True)

# Keep selected IBM bonds only
Ibm_selected_figis = ['BBG 00 P 3 BLH 05',            'BBG 00 FVNGFP 3',            'BBG 00 P 3 BLH 14']
Ibm_df = corp_combined_ibm. Loc[ibm_selected_figis]

Display (ibm_df. T)
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
	  <th>figi</th>
	  <th>BBG 00 P 3 BLH 05</th>
	  <th>BBG 00 FVNGFP 3</th>
	  <th>BBG 00 P 3 BLH 14</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>ticker</th>
	  <td>IBM</td>
	  <td>IBM</td>
	  <td>IBM</td>
	</tr>
	<tr>
	  <th>class</th>
	  <td>Corp</td>
	  <td>Corp</td>
	  <td>Corp</td>
	</tr>
	<tr>
	  <th>isin</th>
	  <td>US 459200 JZ 55</td>
	  <td>US 459200 JR 30</td>
	  <td>US 459200 KA 85</td>
	</tr>
	<tr>
	  <th>und_bench_isin</th>
	  <td>US 91282 CKH 33</td>
	  <td>US 91282 CKJ 98</td>
	  <td>US 91282 CKG 59</td>
	</tr>
	<tr>
	  <th>security</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>IBM 3.3 01/27/27</td>
	  <td>IBM 3 1/2 05/15/29</td>
	</tr>
	<tr>
	  <th>name</th>
	  <td>IBM CORP</td>
	  <td>IBM CORP</td>
	  <td>IBM CORP</td>
	</tr>
	<tr>
	  <th>type</th>
	  <td>GLOBAL</td>
	  <td>GLOBAL</td>
	  <td>GLOBAL</td>
	</tr>
	<tr>
	  <th>coupon</th>
	  <td>3.3</td>
	  <td>3.3</td>
	  <td>3.5</td>
	</tr>
	<tr>
	  <th>cpn_type</th>
	  <td>FIXED</td>
	  <td>FIXED</td>
	  <td>FIXED</td>
	</tr>
	<tr>
	  <th>dcc</th>
	  <td>30/360</td>
	  <td>30/360</td>
	  <td>30/360</td>
	</tr>
	<tr>
	  <th>cpn_freq</th>
	  <td>2</td>
	  <td>2</td>
	  <td>2</td>
	</tr>
	<tr>
	  <th>days_settle</th>
	  <td>2</td>
	  <td>2</td>
	  <td>2</td>
	</tr>
	<tr>
	  <th>start_date</th>
	  <td>2019-05-15 00:00:00</td>
	  <td>2017-01-27 00:00:00</td>
	  <td>2019-05-15 00:00:00</td>
	</tr>
	<tr>
	  <th>cpn_first</th>
	  <td>2019-11-15 00:00:00</td>
	  <td>2017-07-27 00:00:00</td>
	  <td>2019-11-15 00:00:00</td>
	</tr>
	<tr>
	  <th>acc_first</th>
	  <td>2019-05-15 00:00:00</td>
	  <td>2017-01-27 00:00:00</td>
	  <td>2019-05-15 00:00:00</td>
	</tr>
	<tr>
	  <th>maturity</th>
	  <td>2026-05-15 00:00:00</td>
	  <td>2027-01-27 00:00:00</td>
	  <td>2029-05-15 00:00:00</td>
	</tr>
	<tr>
	  <th>mty_typ</th>
	  <td>AT MATURITY</td>
	  <td>AT MATURITY</td>
	  <td>AT MATURITY</td>
	</tr>
	<tr>
	  <th>rank</th>
	  <td>Sr Unsecured</td>
	  <td>Sr Unsecured</td>
	  <td>Sr Unsecured</td>
	</tr>
	<tr>
	  <th>amt_out</th>
	  <td>3000.0</td>
	  <td>500.0</td>
	  <td>3250.0</td>
	</tr>
	<tr>
	  <th>country</th>
	  <td>US</td>
	  <td>US</td>
	  <td>US</td>
	</tr>
	<tr>
	  <th>currency</th>
	  <td>USD</td>
	  <td>USD</td>
	  <td>USD</td>
	</tr>
	<tr>
	  <th>status</th>
	  <td>ACTV</td>
	  <td>ACTV</td>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>term</th>
	  <td>7.000684</td>
	  <td>9.998631</td>
	  <td>10.001369</td>
	</tr>
	<tr>
	  <th>TTM</th>
	  <td>2.069815</td>
	  <td>2.773443</td>
	  <td>5.0705</td>
	</tr>
	<tr>
	  <th>date</th>
	  <td>2024-04-19 00:00:00</td>
	  <td>2024-04-19 00:00:00</td>
	  <td>2024-04-19 00:00:00</td>
	</tr>
	<tr>
	  <th>bidPrice</th>
	  <td>95.946</td>
	  <td>95.042</td>
	  <td>91.825</td>
	</tr>
	<tr>
	  <th>askPrice</th>
	  <td>96.13</td>
	  <td>95.28</td>
	  <td>92.108</td>
	</tr>
	<tr>
	  <th>accrued</th>
	  <td>1.448</td>
	  <td>0.788</td>
	  <td>1.5365</td>
	</tr>
	<tr>
	  <th>bidYield</th>
	  <td>5.404</td>
	  <td>5.25</td>
	  <td>5.365</td>
	</tr>
	<tr>
	  <th>askYield</th>
	  <td>5.306</td>
	  <td>5.154</td>
	  <td>5.298</td>
	</tr>
	<tr>
	  <th>midPrice</th>
	  <td>96.038</td>
	  <td>95.161</td>
	  <td>91.9665</td>
	</tr>
	<tr>
	  <th>midYield</th>
	  <td>5.355</td>
	  <td>5.202</td>
	  <td>5.3315</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Create ibm_bond_objects
Ibm_bond_objects = [ create_bond_from_symbology (df_row. To_dict ()) for index,            df_row in ibm_df.Iterrows ()]

# List the bond cashflows
For i in range (0,            3):
    Print ('Bond cashflows for',            ibm_df. Iloc[i]['security'])
    Display (get_bond_cashflows (ibm_bond_objects[i],            calc_date)) 

```

    Bond cashflows for IBM 3.3 05/15/26

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
	  <th>9</th>
	  <td>May 15 th,  2024</td>
	  <td>0.072222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>November 15 th,  2024</td>
	  <td>0.572222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>May 15 th,  2025</td>
	  <td>1.072222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>November 15 th,  2025</td>
	  <td>1.572222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>May 15 th,  2026</td>
	  <td>2.072222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>May 15 th,  2026</td>
	  <td>2.072222</td>
	  <td>100.00</td>
	</tr>
  </tbody>
</table>
</div>

    Bond cashflows for IBM 3.3 01/27/27

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
	  <td>July 27 th,  2024</td>
	  <td>0.272222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>January 27 th,  2025</td>
	  <td>0.772222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>July 27 th,  2025</td>
	  <td>1.272222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>January 27 th,  2026</td>
	  <td>1.772222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>July 27 th,  2026</td>
	  <td>2.272222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>January 27 th,  2027</td>
	  <td>2.772222</td>
	  <td>1.65</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>January 27 th,  2027</td>
	  <td>2.772222</td>
	  <td>100.00</td>
	</tr>
  </tbody>
</table>
</div>

    Bond cashflows for IBM 3 1/2 05/15/29

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
	  <th>9</th>
	  <td>May 15 th,  2024</td>
	  <td>0.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>November 15 th,  2024</td>
	  <td>0.572222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>May 15 th,  2025</td>
	  <td>1.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>November 15 th,  2025</td>
	  <td>1.572222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>May 15 th,  2026</td>
	  <td>2.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>November 15 th,  2026</td>
	  <td>2.572222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>May 15 th,  2027</td>
	  <td>3.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>November 15 th,  2027</td>
	  <td>3.572222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>May 15 th,  2028</td>
	  <td>4.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>November 15 th,  2028</td>
	  <td>4.572222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>May 15 th,  2029</td>
	  <td>5.072222</td>
	  <td>1.75</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>May 15 th,  2029</td>
	  <td>5.072222</td>
	  <td>100.00</td>
	</tr>
  </tbody>
</table>
</div>

## c. Compute CDS-implied (intrinsic) prices for the IBM fixd rate bonds

Price the 3 IBM bonds using the CDS-calibrated hazard rate curve for IBM (via RiskyBondEngine).

Display the clean prices and yields for the 3 test bonds.

```python
# Flat_recovery_rate
Flat_recovery_rate = 0.40

# Risky bond engine uses the calibrated CDS hazard rate curve for pricing credit default risk 
Risky_bond_engine = ql.RiskyBondEngine (default_prob_curve_handle,            flat_recovery_rate,            tsy_yield_curve_handle)

# Model/intrinsic prices and yields
Ibm_model_prices = []
Ibm_model_yields = []

# Print the clean prices and yields for the 3 test bonds
For i in range (0,            3):
    Fixed_rate_bond = ibm_bond_objects[i]
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine)
    
    CorpBondModelPrice = round (fixed_rate_bond.CleanPrice (),            3)
    CorpBondModelYield = round (fixed_rate_bond.BondYield (corpBondModelPrice,            ql. Thirty 360 (ql. Thirty 360. USA),            ql. Compounded,            ql. Semiannual) * 100,            3)

    Ibm_model_prices.Append (corpBondModelPrice)
    Ibm_model_yields.Append (corpBondModelYield)
# Display relevant metrics
Ibm_df['modelPrice'] = ibm_model_prices
Ibm_df['modelYield'] = ibm_model_yields

display (ibm_df [['security',            'modelPrice',            'modelYield']])

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
	  <th>modelPrice</th>
	  <th>modelYield</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>96.274</td>
	  <td>5.229</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>95.562</td>
	  <td>5.040</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>92.867</td>
	  <td>5.117</td>
	</tr>
  </tbody>
</table>
</div>

## d. Compute the "intrinsic" vs market price basis for the IBM bonds

Load the market mid prices and yields from the bond market data dataframe as of 2024-04-19.

Compute and display the basis between the "CDS-implied intrinsic" vs market prices and yields:

- BasisPrice = modelPrice - midPrice
- BasisYield = modelYield - midYield

Are the CDS intrinsic prices lower or higher than the bond prices observed on the market? What factors could explain the basis?

```python
# Compute basis
Ibm_df['basisPrice'] = ibm_df['modelPrice'] - ibm_df['midPrice']
Ibm_df['basisYield'] = ibm_df['modelYield'] - ibm_df['midYield']

# Display relevant metrics
display (ibm_df [['security',            'midPrice',            'modelPrice',            'basisPrice',            'midYield',            'modelYield',            'basisYield']])
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
	  <th>midPrice</th>
	  <th>modelPrice</th>
	  <th>basisPrice</th>
	  <th>midYield</th>
	  <th>modelYield</th>
	  <th>basisYield</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>96.0380</td>
	  <td>96.274</td>
	  <td>0.2360</td>
	  <td>5.3550</td>
	  <td>5.229</td>
	  <td>-0.1260</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>95.1610</td>
	  <td>95.562</td>
	  <td>0.4010</td>
	  <td>5.2020</td>
	  <td>5.040</td>
	  <td>-0.1620</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>91.9665</td>
	  <td>92.867</td>
	  <td>0.9005</td>
	  <td>5.3315</td>
	  <td>5.117</td>
	  <td>-0.2145</td>
	</tr>
  </tbody>
</table>
</div>

CDS-implied,  intrinsic bond prices are higher than bond market prices.

Following factors could explain the basis dislocation for the 3 IBM bonds:

1. Hazard Rate curve mismatch: the synthetic CDS credit market is underestimating the credit risk in the IBM issuer curve,  relative to the cash corporate bond market. This opens the opportunity for Bond vs CDS basis arbitrage trades,  as discussed in Session 2.
1. Risk-free yield curve mismatch: the (synthetic) SOFR yield curve is tighter than the (cash) US Treasury curve. This is usually due to a funding differential for cash vs. Synthetic products.
1. Temporarily dislocation: Individual bonds are temporarily dislocated from their "fair value" from the issuer curve (e.g. in a Nelson-Siegel type parametric model). This can happen due to buying vs. Selling imbalance in that particular bond.
1. Liquidity discounts: in general,  less liquid (e.g. off-the-run) bonds trade at a price discount to more liquid (e.g. on-the-run) bonds. This usually causes a liquidty-implied "richer" basis (wider in yield space).

-----------------------------------------------------------
# Problem 2: Compute scenario sensitivities for risky bonds
## a. Compute scenario IR 01 s and Durations for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Compute the scenario IR 01 and Durations using a '-1 bp' interest rate shock,  as described in Section 6. "Market Data Scenarios" in the QuantLib Basics notebook.

Display the computed scenario IR 01 and Durations.

Remember that IR 01 = Dirty_Price * Duration.

```python
# Bump interest rate by -1 bps (parallel shift)
Interest_rate_scenario_1 bp_down = ql.SimpleQuote (-0.0001)
Tsy_yield_curve_handle_1 bp_down = ql.YieldTermStructureHandle (ql.ZeroSpreadedTermStructure (tsy_yield_curve_handle,            ql.QuoteHandle (interest_rate_scenario_1 bp_down)))
Risky_bond_engine_1 bp_down = ql.RiskyBondEngine (default_prob_curve_handle,            flat_recovery_rate,            tsy_yield_curve_handle_1 bp_down)
```

```python
# Model scenario metrics
Ibm_scen_prices_1 bp_down = []
Ibm_scen_IR 01 = []
Ibm_scen_duration = []
# Calculate IR 01 and duration
For i in range (0,            3):
    Fixed_rate_bond = ibm_bond_objects[i]
    
    # Calc model dirty price for base case
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine)    
    Dirty_price_base = fixed_rate_bond.DirtyPrice ()
    
    # Scenario: 1 bp down
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine_1 bp_down)    
    Price_1 bp_down = fixed_rate_bond.CleanPrice ()
    Ibm_scen_prices_1 bp_down.Append (price_1 bp_down)
    
    # Compute scenario IR 01 and duration sensitivities
    Price_base = ibm_model_prices[i]
    Ir 01 = (price_1 bp_down - price_base) * 1 e 4 / 100
    Duration = ir 01 / dirty_price_base * 100

    Ibm_scen_IR 01. Append (ir 01)
    Ibm_scen_duration.Append (duration)
# Display relevant metrics
Ibm_df['scen_IR 01'] = ibm_scen_IR 01
Ibm_df['scen_duration'] = ibm_scen_duration

display (ibm_df [['security',            'scen_IR01',            'scen_duration']])

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
	  <th>scen_IR 01</th>
	  <th>scen_duration</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>1.969808</td>
	  <td>2.015714</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>2.482201</td>
	  <td>2.576234</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>4.326882</td>
	  <td>4.583408</td>
	</tr>
  </tbody>
</table>
</div>

## b. Compute analytical DV 01 s and Durations for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Compute and display the analytical IR 01 and Durations

Compare the analytic DV 01 s vs. The scenario IR 01 s. Are they expected to be similar?

```python
# Analytic metrics
Ibm_analytic_durations = []
Ibm_analytic_DV 01 s = []

# Calculate IR 01 and duration
For i in range (0,            3):
    Fixed_rate_bond = ibm_bond_objects[i]
    
    # Calc model dirty price for base case
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine)    
    Dirty_price_base = fixed_rate_bond.DirtyPrice ()
    
    # Compute analytical duration and DV 01
    Bond_yield_rate = ql.InterestRate (ibm_model_yields[i]/100,            ql.ActualActual (ql. ActualActual. ISMA),            ql. Compounded,            ql. Semiannual)
    Analytic_duration = ql.BondFunctions.Duration (fixed_rate_bond,            bond_yield_rate)
    Analytic_DV 01 = analytic_duration * dirty_price_base /100 

    Ibm_analytic_durations.Append (analytic_duration)
    Ibm_analytic_DV 01 s.Append (analytic_DV 01)
# Display relevant metrics
Ibm_df['analytic_DV 01'] = ibm_analytic_DV 01 s
Ibm_df['analytic_duration'] = ibm_analytic_durations

display (ibm_df [['security',            'analytic_DV01',            'analytic_duration']])

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
	  <th>analytic_DV 01</th>
	  <th>analytic_duration</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>1.884085</td>
	  <td>1.927993</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>2.479507</td>
	  <td>2.573438</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>4.223564</td>
	  <td>4.473966</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Compare the analytical DV 01 s vs. The scenario IR 01 s. Are they expected to be similar?
display (ibm_df [['security',            'scen_IR01',            'analytic_DV01']])
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
	  <th>scen_IR 01</th>
	  <th>analytic_DV 01</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>1.969808</td>
	  <td>1.884085</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>2.482201</td>
	  <td>2.479507</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>4.326882</td>
	  <td>4.223564</td>
	</tr>
  </tbody>
</table>
</div>

DV 01 s and IR 01 s are expected to be similar,  since a -1 bp change in the (risk free) interest rate curve causes approximately a -1 bp change in the (risky) bond yield curve.

## c. Compute scenario CS 01 s (credit spread sensitivities) for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Apply a '-1 bp' (parallel shift) scenario to the IBM CDS Par Spread quotes and calibrate the scenario hazard rate curve.

Create a new scenario RiskyBondEngine,  using the scenario hazard rate curve.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped hazard rate curve) to obtain the '-1 bp' scenario CS 01 (credit spread sensitivities).

Compare the scenario CS 01 s vs analytic DV 01 s. Are they expected to be similar?

```python
# Hazard_rate_curve calibration (from IBM CDS par spreads)
Cds_par_spreads_1 bp_down = [ps - 1 for ps in cds_par_spreads]
Print (cds_par_spreads)
Print (cds_par_spreads_1 bp_down)

# Hazard_rate_curve
Hazard_rate_curve_1 bp_down = calibrate_cds_hazard_rate_curve (calc_date,            sofr_yield_curve_handle,            cds_par_spreads_1 bp_down,            cds_recovery_rate)
Default_prob_curve_handle_1 bp_down = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve_1 bp_down)

# Risky bond engine for CDS Par Spread -1 bp scenario
Risky_bond_engine_cds_1 bp_down = ql.RiskyBondEngine (default_prob_curve_handle_1 bp_down,            flat_recovery_rate,            tsy_yield_curve_handle)

```

    [12.0769,            17.3082,            24.866,            39.6501,            53.9093,            65.3221]
    [11.0769,            16.3082,            23.866,            38.6501,            52.9093,            64.3221]

```python
# Calculate CS 01
Ibm_model_cs 01 = []

For i in range (0,            3):
    Fixed_rate_bond = ibm_bond_objects[i]     
    Price_base = ibm_model_prices[i]   
    
    # set scenario pricing engine
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine_cds_1 bp_down)
    
    # calc credit spread scenario price
    Price_cds_1 bp_down = fixed_rate_bond.CleanPrice ()

    # calc price diff
    Price_diff_cds_1 bp_down = price_cds_1 bp_down - price_base
    
    Ibm_model_cs 01. Append (price_diff_cds_1 bp_down * 1 e 4 / 100)

Ibm_df['CS 01'] = ibm_model_cs 01

# Compare the scenario CS 01 s vs analytic DV 01 s. Are they expected to be similar?
display (ibm_df [['security',            'scen_IR01',            'analytic_DV01',            'CS01']])

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
	  <th>scen_IR 01</th>
	  <th>analytic_DV 01</th>
	  <th>CS 01</th>
	</tr>
	<tr>
	  <th>figi</th>
	  <th></th>
	  <th></th>
	  <th></th>
	  <th></th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>BBG 00 P 3 BLH 05</th>
	  <td>IBM 3.3 05/15/26</td>
	  <td>1.969808</td>
	  <td>1.884085</td>
	  <td>1.970422</td>
	</tr>
	<tr>
	  <th>BBG 00 FVNGFP 3</th>
	  <td>IBM 3.3 01/27/27</td>
	  <td>2.482201</td>
	  <td>2.479507</td>
	  <td>2.516812</td>
	</tr>
	<tr>
	  <th>BBG 00 P 3 BLH 14</th>
	  <td>IBM 3 1/2 05/15/29</td>
	  <td>4.326882</td>
	  <td>4.223564</td>
	  <td>4.297695</td>
	</tr>
  </tbody>
</table>
</div>

CS 01 s and DV 01 s are expected to be similar,  since a -1 bp change in the credit spread curve causes approximately a -1 bp change in the (risky) bond yield curve.

## d. Compute scenario REC 01 (recovery rate sensitivity) for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Apply a +1% scenario bump to the IBM recovery rate (bump the flat_recovery_rate parameter by 1%,  from 40% to 41%).

Create a new scenario RiskyBondEngine,  using the scenario new recovery rate.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped recovery rate) to obtain the +1% scenario REC 01 (recovery rate sensitivity).

```python
# Bump recovery rate by 1% up
Flat_recovery_rate_1 pct_up = flat_recovery_rate + 0.01
Risky_bond_engine_rec_1 pct_up = ql.RiskyBondEngine (default_prob_curve_handle,            flat_recovery_rate_1 pct_up,            tsy_yield_curve_handle)

# Calculate REC 01
Ibm_model_rec 01 = []

For i in range (0,            3):
    Fixed_rate_bond = ibm_bond_objects[i]
    Price_base = ibm_model_prices[i]    
    
    # set scenario pricing engine
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine_rec_1 pct_up)
    
    # calc price diff
    Price_rec_1 pct_up = fixed_rate_bond.CleanPrice ()    
    Price_diff_rec_1 pct_up = price_rec_1 pct_up - price_base
    
    Ibm_model_rec 01. Append (price_diff_rec_1 pct_up)

# Display relevant metrics
Ibm_df['REC 01'] = ibm_model_rec 01
print (ibm_df [['security',            'REC01']])

```

                            Security     REC 01
    Figi                                      
    BBG 00 P 3 BLH 05    IBM 3.3 05/15/26  0.005857
    BBG 00 FVNGFP 3    IBM 3.3 01/27/27  0.009410
    BBG 00 P 3 BLH 14  IBM 3 1/2 05/15/29  0.029299

-----------------------------------------------------------
# Problem 3: Perpetual CDS

We are interested in a perpetual CDS contract (infinite maturity) on a face notional of $100,  flat interest rate of 4% and coupon of 5% (quarterly payments).

For simplicity,  we assuming a flat hazard rate of 1% per annum,  a recovery rate of 40%,  T+0 settlement and zero accrued.

Use the simple CDS valuation formulas derived in Session 3 as a template.

The value of the perpetual CDS is obtained as a limit case of the simple CDS valuation formulas derived in Session 3,  for $T \to \infty$.

$$\begin{align}
PV_{CDS\_PL}\left (c,            r,            h,            R,            \infty \right) = \frac{c}{4 \cdot \left (e^{\left (r+h\right)/4}-1 \right)} \simeq \frac{c}{r+h}
\end{align}$$

$$\begin{align}
PV_{CDS\_DL}\left (c,            r,            h,            R,           \infty \right) = \frac{\left (1-R\right)\cdot h}{r+h} 
\end{align}$$

$$\begin{align}
PV_{CDS} = PV_{CDS\_PL} - PV_{CDS\_DL}
\end{align}$$

$$\begin{align}
CDS\_ParSpread = c \cdot \frac{PV_{CDS\_DL}}{PV_{CDS\_PL}} \simeq \left (1-R\right)\cdot h
\end{align}$$
```python
Def calc_perpetual_cds_premium_leg_pv (c,            r,            h,            R,            face):
    Return (c / 4 / (np.Exp ((r+h)/4)-1) * face)

Def calc_perpetual_cds_default_leg_pv (c,            r,            h,            R,            face):
    Return ((1 - R) * h / (r + h) * face)

Def calc_perpetual_cds_pv (c,            r,            h,            R,            face):
    Return (calc_perpetual_cds_premium_leg_pv (c,            r,            h,            R,            face) - calc_perpetual_cds_default_leg_pv (c,            r,            h,            R,            face))

Def calc_perpetual_cds_par_spread (c,            r,            h,            R,            face):
    Return (c * calc_perpetual_cds_default_leg_pv (c,            r,            h,            R,            face) / calc_perpetual_cds_premium_leg_pv (c,            r,            h,            R,            face))
```

## a. Compute the fair value of the CDS premium and default legs.
```python
# Constant model parameters
R = 0.04
C = 0.05
H = 0.01
R = 0.40
Face = 100

# Perpetual_cds_premium_leg_pv
Perpetual_cds_premium_leg_pv = calc_perpetual_cds_premium_leg_pv (c,            r,            h,            R,            face)
Print ('perpetual_cds_premium_leg_pv: ',            round (perpetual_cds_premium_leg_pv,            2))

# Perpetual_cds_default_leg_pv
Perpetual_cds_default_leg_pv = calc_perpetual_cds_default_leg_pv (c,            r,            h,            R,            face)
Print ('perpetual_cds_default_leg_pv: ',            round (perpetual_cds_default_leg_pv,            2))
```

    Perpetual_cds_premium_leg_pv: 99.38
## b. Compute the CDS PV and the CDS Par Spread.
```python
Perpetual_cds_pv = calc_perpetual_cds_pv (c,            r,            h,            R,            face)
Print ('perpetual_cds_pv: ',            round (perpetual_cds_pv,            2))

Perpetual_cds_par_spread_bps = calc_perpetual_cds_par_spread (c,            r,            h,            R,            face) * 1 e 4
Print ('perpetual_cds_par_spread_bps: ',            round (perpetual_cds_par_spread_bps,            2))

Perpetual_cds_par_spread_approx_bps = (1 - R) * h * 1 e 4
Print ('perpetual_cds_par_spread_approx_bps: ',            round (perpetual_cds_par_spread_approx_bps,            2))

```

    Perpetual_cds_default_leg_pv: 12.0
    Perpetual_cds_pv: 87.38
    Perpetual_cds_par_spread_bps: 60.38
    Perpetual_cds_par_spread_approx_bps: 60.0
## c. Compute the following CDS risk sensitivities:
- IR 01 (PV sensitivity to Interest Rate change of '-1 bp')
- HR 01 (PV sensitivity to Hazard Rate change of '-1 bp')
- REC 01 (PV sensitivity to Recovery Rate change of '+1%')

Using the scenario method.
```python
# CDS IR 01 
R_1 bp_down = r - 0.0001
Perpetual_cds_pv_r_1 bp_down = calc_perpetual_cds_pv (c,            r_1 bp_down,            h,            R,            face)
Perpetual_cds_ir 01 = perpetual_cds_pv_r_1 bp_down - perpetual_cds_pv
Print ('perpetual_cds_ir 01 ($): ',            round (perpetual_cds_ir 01,            2))

# CDS HR 01 
H_1 bp_down = h - 0.0001
Perpetual_cds_pv_h_1 bp_down = calc_perpetual_cds_pv (c,            r,            h_1 bp_down,            R,            face)
Perpetual_cds_hr 01 = perpetual_cds_pv_h_1 bp_down - perpetual_cds_pv
Print ('perpetual_cds_hr 01 ($): ',            round (perpetual_cds_hr 01,            2))

# CDS CS 01
Perpetual_cds_par_spread_h_1 bp_down = calc_perpetual_cds_par_spread (c,            r,            h_1 bp_down,            R,            face) * 1 e 4
Perpetual_cds_par_spread_bps_delta = perpetual_cds_par_spread_bps - perpetual_cds_par_spread_h_1 bp_down
Perpetual_cds_cs 01 = perpetual_cds_hr 01 / perpetual_cds_par_spread_bps_delta
Print ('perpetual_cds_cs 01 ($): ',            round (perpetual_cds_cs 01,            2))

# CDS REC 01 
R_1 pct_up = R + 0.01
Perpetual_cds_pv_R_1 pct_up = calc_perpetual_cds_pv (c,            r,            h,            R_1 pct_up,            face)
Perpetual_cds_rec 01 = perpetual_cds_pv_R_1 pct_up - perpetual_cds_pv
Print ('perpetual_cds_rec 01 ($): ',            round (perpetual_cds_rec 01,            2))
```

    Perpetual_cds_ir 01 ($): 0.18
    Perpetual_cds_hr 01 ($): 0.3
    Perpetual_cds_cs 01 ($): 0.49
    Perpetual_cds_rec 01 ($): 0.2
## d. At what time T does the (implied) default probability over next 10 years drop to 1%?

$$\begin{align}
\mathbb{P} \left (\tau \in [T,            T+10] \right) = 1/100
\end{align}$$
$$\begin{align}
\mathbb{P} \left (\tau \in [T,            T+10] \right)
\end{align}$$

$$\begin{align}
= \mathbb{P} \left (\tau >T \right) - \mathbb{P} \left (\tau > T+10 \right)
\end{align}$$

$$\begin{align}
= e^{-h \cdot T} - e^{-h \cdot \left ( T + 10 \right)}
\end{align}$$

$$\begin{align}
= e^{-h \cdot T}\cdot \left (1 - e^{-h \cdot 10} \right).
\end{align}$$
$$\begin{align}
\mathbb{P} \left (\tau \in [T,            T+10] \right) = 1/100
\end{align}$$

$$\begin{align}
\iff e^{-h \cdot T}\cdot \left (1 - e^{-h \cdot 10} \right) = 1/100
\end{align}$$

$$\begin{align}
\iff T = \frac {\ln \left (100 \cdot \left (1 - e^{-h \cdot 10} \right) \right)} {h}
\end{align}$$
```python
# Calc T:
T = np.Log (100*(1-np.Exp (-h*10)))/h
Print ('T =',            T)
```

    T = 225.3001724944001
-----------------------------------------------------------
# Problem 4: Nelson-Siegel model for smooth hazard rate curves

## This exercise implements tsome of the concepts introduced in Lecture 4,            Section 1 "Parametric Hazard Rate Models"

## Follow Section "3. Smooth parametric yield and hazard rate curves: the Nelson-Siegel model" in the QuantLib Advanced notebook
## You can also take a look at Dr. Mark Hendricks Fixed Income notebooks describing the Nelson-Siegel model calibration on US Treasuries (GitHub repo link posted in Canvas).

## a. Prepare the market data as of 2024-04-19
Load the symbology + market data dataframes and create a combined dataframe for for all Verizon (ticker = 'VZ') fixed rate (cpn_type == 'FIXED') bonds with an outstanding amount greater than $100 MM (amt_out > 100).

Sort the dataframe by bond maturity and display the head of the dataframe.

Plot the VZ yields (Y-axis) by TTM (X-axis).
```python
# Corp_symbology_vz
Corp_symbology_vz = bond_symbology[(bond_symbology. Ticker == 'VZ') & (bond_symbology. Cpn_type == 'FIXED') & (bond_symbology. Amt_out > 100)]

# Create vz_df
Vz_df = corp_symbology_vz.Merge (bond_market_prices_eod,            how='inner',            on=['class',            'ticker',            'isin',            'figi'])

# Sort the dataframe by bond maturity and display the head of the dataframe.
Vz_df. Sort_values ('maturity',            inplace=True)
Display (vz_df.Head ())

# Plot the VZ yields (Y-axis) by TTM (X-axis).
Plt = vz_df.Plot (x='TTM',            y = 'midYield',            figsize = (12,            6),            title = "VZ Market Yields (pct)",            grid=True,            style='*')
Plt. Set_ylabel ('Bond Yields (pct)')
Plt. Set_xlabel ('Bond TTM')

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
      <th>39</th>
      <td>VZ</td>
      <td>Corp</td>
      <td>BBG 00 ZLKTF 09</td>
      <td>US 92343 VGG 32</td>
      <td>US 91282 CKH 33</td>
      <td>VZ 1.45 03/20/26</td>
      <td>VERIZON COMMUNICATIONS</td>
      <td>GLOBAL</td>
      <td>1.450</td>
      <td>FIXED</td>
      <td>…</td>
      <td>4.993840</td>
      <td>1.916496</td>
      <td>2024-04-19</td>
      <td>92.783</td>
      <td>92.940</td>
      <td>0.1335</td>
      <td>5.484</td>
      <td>5.392</td>
      <td>92.8615</td>
      <td>5.4380</td>
    </tr>
    <tr>
      <th>38</th>
      <td>VZ</td>
      <td>Corp</td>
      <td>BBG 00 DGYP 877</td>
      <td>US 92343 VDD 38</td>
      <td>US 91282 CKH 33</td>
      <td>VZ 2 5/8 08/15/26</td>
      <td>VERIZON COMMUNICATIONS</td>
      <td>GLOBAL</td>
      <td>2.625</td>
      <td>FIXED</td>
      <td>…</td>
      <td>10.036961</td>
      <td>2.321697</td>
      <td>2024-04-19</td>
      <td>93.904</td>
      <td>94.119</td>
      <td>0.4965</td>
      <td>5.467</td>
      <td>5.363</td>
      <td>94.0115</td>
      <td>5.4150</td>
    </tr>
    <tr>
      <th>37</th>
      <td>VZ</td>
      <td>Corp</td>
      <td>BBG 00 G 6 QW 2 B 8</td>
      <td>US 92343 VDY 74</td>
      <td>US 91282 CKJ 98</td>
      <td>VZ 4 1/8 03/16/27</td>
      <td>VERIZON COMMUNICATIONS</td>
      <td>GLOBAL</td>
      <td>4.125</td>
      <td>FIXED</td>
      <td>…</td>
      <td>9.998631</td>
      <td>2.904860</td>
      <td>2024-04-19</td>
      <td>96.703</td>
      <td>96.899</td>
      <td>0.4240</td>
      <td>5.367</td>
      <td>5.292</td>
      <td>96.8010</td>
      <td>5.3295</td>
    </tr>
    <tr>
      <th>36</th>
      <td>VZ</td>
      <td>Corp</td>
      <td>BBG 00 SK 3 XVL 1</td>
      <td>US 92343 VFF 67</td>
      <td>US 91282 CKJ 98</td>
      <td>VZ 3 03/22/27</td>
      <td>VERIZON COMMUNICATIONS</td>
      <td>GLOBAL</td>
      <td>3.000</td>
      <td>FIXED</td>
      <td>…</td>
      <td>7.003422</td>
      <td>2.921287</td>
      <td>2024-04-19</td>
      <td>93.598</td>
      <td>93.843</td>
      <td>0.2585</td>
      <td>5.403</td>
      <td>5.307</td>
      <td>93.7205</td>
      <td>5.3550</td>
    </tr>
    <tr>
      <th>35</th>
      <td>VZ</td>
      <td>Corp</td>
      <td>BBG 00 ZLKTF 27</td>
      <td>US 92343 VGH 15</td>
      <td>US 91282 CKG 59</td>
      <td>VZ 2.1 03/22/28</td>
      <td>VERIZON COMMUNICATIONS</td>
      <td>GLOBAL</td>
      <td>2.100</td>
      <td>FIXED</td>
      <td>…</td>
      <td>7.000684</td>
      <td>3.923340</td>
      <td>2024-04-19</td>
      <td>88.334</td>
      <td>88.624</td>
      <td>0.1810</td>
      <td>5.450</td>
      <td>5.360</td>
      <td>88.4790</td>
      <td>5.4050</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 33 columns</p>
</div>
    Text (0.5,            0,            'Bond TTM')
![png](CreditMarketSolutions_279_2.png)
## b. Create the Nelson-Siegel curve shape (4 parameters) and compute the corresponding SSE function.
For a given set of parameters,            write a function to compute the SSE "Sum of Squared Errors" penalty function in price space (defined as sum of squared differences between model and market prices for all Verizon fixed-rate bonds).
For each bond,            compute the bond DV 01,            using Section "9. Analytical Duration" in the QuantLib Basics notebook as a template.

Use 1/DV 01 as SSE weights,            as discussed in Lecture 3. You can ignore the liquidity adjuster for the purpose of this exercise.
```python
Def nelson_siegel (params,            maturity):
    ''' params = (theta 1,            theta 2,            theta 3,            lambda)'''        
    If (maturity == 0 or params[3] <= 0):
        Slope_1 = 1
        Curvature = 0
    Else:
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
        Curvature = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature
    
    Return total_value

Def create_nelson_siegel_curve (calc_date,            nelson_siegel_params):
    ''' nelson_siegel_params = (theta 1,            theta 2,            theta 3,            lambda)'''            
    Nelson_siegel_surv_prob_dates = [calc_date + ql.Period (T ,            ql. Years) for T in range (31)]
    Nelson_siegel_average_hazard_rates = [nelson_siegel (nelson_siegel_params,            T) for T in range (31)]
    Nelson_siegel_surv_prob_levels = [np.Exp (-T * nelson_siegel_average_hazard_rates[T]) for T in range (31)]
    
    # cap and floor survival probs
    Nelson_siegel_surv_prob_levels = [max (min (x,            1),            1 e-8) for x in nelson_siegel_surv_prob_levels]

    # nelson_siegel_surv_prob_curve
    Nelson_siegel_credit_curve = ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,            nelson_siegel_surv_prob_levels,            ql. Actual 360 (),            ql.TARGET ())
    Nelson_siegel_credit_curve.EnableExtrapolation ()
    Nelson_siegel_credit_curve_handle = ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)
    
    Return (nelson_siegel_credit_curve_handle)
Def calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,            
                      Calc_date,            
                      Fixed_rate_bond_objects,            
                      Tsy_yield_curve_handle,            
                      Bond_recovery_rate = 0.4):
    
    # nelson_siegel_surv_prob_curve_handle
    Nelson_siegel_surv_prob_curve_handle = create_nelson_siegel_curve (calc_date,            nelson_siegel_params)
    
    # nelson_siegel_risky_bond_engine
    Nelson_siegel_risky_bond_engine = ql.RiskyBondEngine (nelson_siegel_surv_prob_curve_handle,            bond_recovery_rate,            tsy_yield_curve_handle)
    
    Bond_model_prices = []
    Bond_model_yields = []
    
    For fixed_rate_bond in fixed_rate_bond_objects:
        Fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)
        
        Bond_price = fixed_rate_bond.CleanPrice ()                
        Bond_yield = fixed_rate_bond.BondYield (bond_price,            ql. Thirty 360 (ql. Thirty 360. USA),            ql. Compounded,            ql. Semiannual) * 100
        
        Bond_model_prices.Append (bond_price)
        Bond_model_yields.Append (bond_yield)
    
    Return (bond_model_prices,            bond_model_yields)

Def nelson_siegel_sse (nelson_siegel_params,            
                      Calc_date,            
                      Fixed_rate_bond_objects,            
                      Market_prices,            
                      Calib_weights,           
                      Tsy_yield_curve_handle,            
                      Bond_recovery_rate = 0.4):
    
    # bond_model_prices
    Bond_model_prices,            bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,            
                      Calc_date,            
                      Fixed_rate_bond_objects,            
                      Tsy_yield_curve_handle,            
                      Bond_recovery_rate)
    # sse    
    Sse = 0
    
    For i in range (len (market_prices)):
        Model_error = market_prices[i] - bond_model_prices[i]                
        Sse += model_error * model_error * calib_weights[i]                        
    
    Return (sse)    
Def create_bonds_and_weights (bond_details,            tsy_yield_curve_handle):
    
    # risk_free_bond_engine
    Risk_free_bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_handle)
    Fixed_rate_bond_objects = []
    Bond_market_prices = []    
    Bond_yields = []
    Bond_DV 01 s = []    
    Bond_durations = []    
    
    For index,            row in bond_details.Iterrows ():
        Fixed_rate_bond = create_bond_from_symbology (row)
        Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
        
        Fixed_rate_bond_objects.Append (fixed_rate_bond)
        
        Bond_price = row['midPrice']                
        Bond_yield = fixed_rate_bond.BondYield (bond_price,            ql. Thirty 360 (ql. Thirty 360. USA),            ql. Compounded,            ql. Semiannual) * 100
        Bond_yield_rate = ql.InterestRate (bond_yield/100,            ql.ActualActual (ql. ActualActual. ISMA),            ql. Compounded,            ql. Semiannual)
        Bond_duration = ql.BondFunctions.Duration (fixed_rate_bond,            bond_yield_rate)
        Bond_DV 01   = fixed_rate_bond.DirtyPrice () * bond_duration
        
        Bond_market_prices.Append (bond_price)
        Bond_yields.Append (bond_yield)
        Bond_DV 01 s.Append (bond_DV 01)
        Bond_durations.Append (bond_duration)   
             
    Calib_weights = [1 / d for d in bond_DV 01 s]
    
    Sum_calib_weights = sum (calib_weights)
    Calib_weights = [x / sum_calib_weights for x in calib_weights]
    
    Return (fixed_rate_bond_objects,            calib_weights,            bond_market_prices,            bond_yields,            bond_DV 01 s,            bond_durations)

```
```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Initial_nelson_siegel_params
Initial_nelson_siegel_params = [0.03,            -0.01,            0.02,            5.0]
Print ('initial_nelson_siegel_params: ',            initial_nelson_siegel_params)

Fixed_rate_bond_objects,            calib_weights,            bond_market_prices,            bond_yields,            bond_DV 01 s,            bond_durations = create_bonds_and_weights (vz_df,            tsy_yield_curve_handle)
Vz_df['duration'] = bond_durations
Vz_df['calib_weight'] = calib_weights

Init_bond_model_prices,            init_bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (initial_nelson_siegel_params,            calc_date,            fixed_rate_bond_objects,            tsy_yield_curve_handle,            bond_recovery_rate)
Vz_df['initModelPrice'] = init_bond_model_prices
Vz_df['initModelYield'] = init_bond_model_yields

display (vz_df [['security',            'midPrice',            'initModelPrice',            'calib_weight']]. head ())

# Initial_sse
Initial_sse = nelson_siegel_sse (initial_nelson_siegel_params,            calc_date,            fixed_rate_bond_objects,            bond_market_prices,            calib_weights,            tsy_yield_curve_handle,            bond_recovery_rate)
Print ('initial_sse =',            initial_sse)

```

    Initial_nelson_siegel_params: [0.03,            -0.01,            0.02,            5.0]
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
      <th>midPrice</th>
      <th>initModelPrice</th>
      <th>calib_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>39</th>
      <td>VZ 1.45 03/20/26</td>
      <td>92.8615</td>
      <td>90.983573</td>
      <td>0.089548</td>
    </tr>
    <tr>
      <th>38</th>
      <td>VZ 2 5/8 08/15/26</td>
      <td>94.0115</td>
      <td>91.761390</td>
      <td>0.073728</td>
    </tr>
    <tr>
      <th>37</th>
      <td>VZ 4 1/8 03/16/27</td>
      <td>96.8010</td>
      <td>93.959994</td>
      <td>0.058387</td>
    </tr>
    <tr>
      <th>36</th>
      <td>VZ 3 03/22/27</td>
      <td>93.7205</td>
      <td>91.109042</td>
      <td>0.059143</td>
    </tr>
    <tr>
      <th>35</th>
      <td>VZ 2.1 03/22/28</td>
      <td>88.4790</td>
      <td>85.516537</td>
      <td>0.046217</td>
    </tr>
  </tbody>
</table>
</div>
    Initial_sse = 25.591932200527502
## c. Calibrate the Nelson-Siegel model parameters to obtain the smooth Verizon credit curve.

Use the US "on-the-run" Treasury yield curve (already calibrated in Problem 1) for risk-free discounting.

Minimize the SSE (pricing error) function to obtain the optimal/calibrated Nelson-Siegel parameter vector. 

Create the calibrated/smooth credit curve corresponding to the optimal model parameters.
```python
From scipy. Optimize import minimize

Def calibrate_nelson_siegel_model (initial_nelson_siegel_params,           
                                  Calc_date,            
                                  Bond_details,            
                                  Tsy_yield_curve_handle,            
                                  Bond_recovery_rate = 0.4):
    # create_bonds_and_weights
    Fixed_rate_bond_objects,            calib_weights,            bond_market_prices,            bond_yields,            bond_DV 01 s,            bond_durations = create_bonds_and_weights (bond_details,            tsy_yield_curve_handle)
    
    # start calibration
    Param_bounds = [(1 e-3,            0.1),            (-0.1,            0.1),            (-0.1,            0.1),            (1 e-3,            10)]
            
    Calib_results = minimize (nelson_siegel_sse,           
                                            Initial_nelson_siegel_params,            
                                            Args = (calc_date,            
                                                    Fixed_rate_bond_objects,            
                                                    Bond_market_prices,            
                                                    Calib_weights,           
                                                    Tsy_yield_curve_handle,            
                                                    Bond_recovery_rate),           
                                            Bounds = param_bounds)
    Return (calib_results)
```
```python
# Calibrate_nelson_siegel_model
Calib_results = calibrate_nelson_siegel_model (initial_nelson_siegel_params,            calc_date,            vz_df,            tsy_yield_curve_handle,            bond_recovery_rate)
Print (calib_results)
    
# Calib_nelson_siegel_params
Calib_nelson_siegel_params = calib_results. X
Print ('calib_nelson_siegel_params: ',            calib_nelson_siegel_params)

# Calib_nelson_siegel_curve
Calib_nelson_siegel_curve = create_nelson_siegel_curve (calc_date,            calib_nelson_siegel_params)

# Calib_sse
Calib_sse = nelson_siegel_sse (calib_nelson_siegel_params,            calc_date,            fixed_rate_bond_objects,            bond_market_prices,            calib_weights,            tsy_yield_curve_handle,            bond_recovery_rate)
Print ('initial_sse =',            round (initial_sse,            3),            'calib_sse =',            round (calib_sse,            3))

```

      Message: CONVERGENCE: REL_REDUCTION_OF_F_<=_FACTR*EPSMCH
      Success: True
       Status: 0
          Fun: 0.20985462025254473
            X: [ 2.115 e-02 -2.079 e-02 -1.998 e-06  2.658 e+00]
          Nit: 45
          Jac: [-3.347 e-04 -4.851 e-05 -5.092 e-05  2.442 e-07]
         Nfev: 285
         Njev: 57
     hess_inv: <4x4 LbfgsInvHessProduct with dtype=float64>
    Calib_nelson_siegel_params: [ 2.11506077 e-02 -2.07855183 e-02 -1.99811247 e-06  2.65774329 e+00]
    Initial_sse = 25.592 calib_sse = 0.21
## d. Compute smooth model prices,            yields and "edges"

Price all Verizon bonds on the calibrated credit curve and compute the corresponding model yields and edges.

Add following columns to the dataframe and display the head of the results:

| modelPrice | modelYield | edgePrice | edgeYield |
|----------|----------|----------|----------|
```python
# Price all Verizon bonds on the calibrated credit curve and compute the corresponding yields.
Bond_model_prices,            bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (calib_nelson_siegel_params,            calc_date,            fixed_rate_bond_objects,            tsy_yield_curve_handle,            bond_recovery_rate)

Vz_df['modelPrice'] = bond_model_prices
Vz_df['modelYield'] = bond_model_yields
Vz_df['edgePrice'] = vz_df['modelPrice'] - vz_df['midPrice']
Vz_df['edgeYield'] = vz_df['modelYield'] - vz_df['midYield']

display (vz_df [['security',            'midPrice',           'initModelPrice',            'modelPrice',            'edgePrice']]. head ())
display (vz_df [['security',            'midYield',           'initModelYield',            'modelYield',            'edgeYield']]. head ())
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
      <th>midPrice</th>
      <th>initModelPrice</th>
      <th>modelPrice</th>
      <th>edgePrice</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>39</th>
      <td>VZ 1.45 03/20/26</td>
      <td>92.8615</td>
      <td>90.983573</td>
      <td>92.838491</td>
      <td>-0.023009</td>
    </tr>
    <tr>
      <th>38</th>
      <td>VZ 2 5/8 08/15/26</td>
      <td>94.0115</td>
      <td>91.761390</td>
      <td>93.984611</td>
      <td>-0.026889</td>
    </tr>
    <tr>
      <th>37</th>
      <td>VZ 4 1/8 03/16/27</td>
      <td>96.8010</td>
      <td>93.959994</td>
      <td>96.743183</td>
      <td>-0.057817</td>
    </tr>
    <tr>
      <th>36</th>
      <td>VZ 3 03/22/27</td>
      <td>93.7205</td>
      <td>91.109042</td>
      <td>93.818693</td>
      <td>0.098193</td>
    </tr>
    <tr>
      <th>35</th>
      <td>VZ 2.1 03/22/28</td>
      <td>88.4790</td>
      <td>85.516537</td>
      <td>88.771584</td>
      <td>0.292584</td>
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
      <th>security</th>
      <th>midYield</th>
      <th>initModelYield</th>
      <th>modelYield</th>
      <th>edgeYield</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>39</th>
      <td>VZ 1.45 03/20/26</td>
      <td>5.4380</td>
      <td>6.552199</td>
      <td>5.451398</td>
      <td>0.013398</td>
    </tr>
    <tr>
      <th>38</th>
      <td>VZ 2 5/8 08/15/26</td>
      <td>5.4150</td>
      <td>6.520478</td>
      <td>5.427663</td>
      <td>0.012663</td>
    </tr>
    <tr>
      <th>37</th>
      <td>VZ 4 1/8 03/16/27</td>
      <td>5.3295</td>
      <td>6.441599</td>
      <td>5.351789</td>
      <td>0.022289</td>
    </tr>
    <tr>
      <th>36</th>
      <td>VZ 3 03/22/27</td>
      <td>5.3550</td>
      <td>6.391251</td>
      <td>5.316861</td>
      <td>-0.038139</td>
    </tr>
    <tr>
      <th>35</th>
      <td>VZ 2.1 03/22/28</td>
      <td>5.4050</td>
      <td>6.335615</td>
      <td>5.314845</td>
      <td>-0.090155</td>
    </tr>
  </tbody>
</table>
</div>
## e. Visualize the results of the calibrated credit model

Plot the model vs market prices (Y-axis) by maturity (X-axis).

Plot the model vs market yields (Y-axis) by maturity (X-axis).

Plot the edges in yield space (Y-axis) by maturity (X-axis).

What do you think about the quality of the model fit?
```python
# Plot the model vs market prices (Y-axis) by maturity (X-axis).
Plt = vz_df.Plot (x='maturity',            y = ['midPrice',            'modelPrice'],            figsize = (12,            6),            title = "Market vs Model Prices",            grid=True,            style='*')
Plt. Set_ylabel ('Bond Prices (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,            0,            'Bond Maturity')
![png](CreditMarketSolutions_289_1.png)
```python
# Plot the model vs market yields (Y-axis) by maturity (X-axis).
Plt = vz_df.Plot (x='maturity',            y = ['midYield',            'modelYield'],            figsize = (12,            6),            title = "Market vs Model Yields (pct)",            grid=True,            style='*')
Plt. Set_ylabel ('Bond Yields (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,            0,            'Bond Maturity')
![png](CreditMarketSolutions_290_1.png)
```python
# Plot the edges in yield space (Y-axis) by maturity (X-axis).
Plt = vz_df.Plot (x='maturity',            y = ['edgeYield'],            figsize = (12,            6),            title = "Model Edges in yield space (pct)",            grid=True,            style='*')
Plt.Axhline (0,            color='red',            linestyle='--',            alpha=0.7)
Plt. Set_ylabel ('Yield Edge (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,            0,            'Bond Maturity')
![png](CreditMarketSolutions_291_1.png)
### What do you think about the quality of the model fit?
Model fit looks good,            given that fact that we are matching closely the market prices of 40 VZ bonds with only 4 Nelson-Siegel model parameters.
