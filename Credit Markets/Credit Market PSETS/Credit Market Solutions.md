---
title: Credit Market Solutions
tags:
  - bond_symbology
  - credit_market_solutions
  - government_bonds
  - us_treasuries
  - yield_curve
aliases:
  - FINM 35700
  - Homework 1
  - Treasury bonds
  - UChicago
key_concepts:
  - Bond symbology exploration
  - Historical coupon time series
  - On-the-run US treasuries
  - US treasury instruments
  - US treasury yield curve
---

# Credit Market Solutions
## Solution to Homework 1

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

This homework relies on:

- the government and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] symbology file `bond_symbology`,
- the "on-the-run" treasuries data file `govt_on_the_run` and
- the market data file `bond_market_prices_eod`.

You can find more details on US treasury instruments in the FINM 37400 Fixed Income course.

```python
import QuantLib as ql
import pandas as pd
import numpy as np
from matplotlib import pyplot as plt
import seaborn as sns
import scipy as sp
import plotly.express as px
import plotly.graph_objects as go
```

# Problem 1: Explore symbology for US treasuries and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]

## a. Load and explore US government bond symbology

Load the `bond_symbology` Excel file into a dataframe. It contains symbology for both government and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]].

Select US Treasury bonds only (class = 'Govt',  ticker = 'T'). For each government bond issue,  calculate its initial term/time-to-maturity in years (based on issue date and maturity date),  as well as the current time-to-maturity. Assume a year has 365.25 days (alternatively,  use QuantLib yearFraction function).

```python
import pandas as pd

# Import bond market prices
bond_market_prices_eod = pd.read_excel('data/bond_market_prices_eod.xlsx')
display(bond_market_prices_eod)

# Import CDS market data
cds_market_data_eod = pd.read_excel('data/cds_market_data_eod.xlsx')
display(cds_market_data_eod)

# Import CDX IG 42 5Y basket composition
cdx_ig_42_5y_basket_composition = pd.read_excel('data/cdx_ig_42_5y_basket_composition.xlsx')
display(cdx_ig_42_5y_basket_composition)

# Import CDX symbology
cdx_symbology = pd.read_excel('data/cdx_symbology.xlsx')
display(cdx_symbology)

# Import corporate symbology
corp_symbology = pd.read_excel('data/corp_symbology.xlsx')
display(corp_symbology)

# Import government on-the-run data
govt_on_the_run = pd.read_excel('data/govt_on_the_run.xlsx')
display(govt_on_the_run)

# Import government symbology
govt_symbology = pd.read_excel('data/govt_symbology.xlsx')
display(govt_symbology)

# Import LQD basket composition
lqd_basket_composition = pd.read_excel('data/lqd_basket_composition.xlsx')
display(lqd_basket_composition)

# Import LQD corporate symbology
lqd_corp_symbology = pd.read_excel('data/lqd_corp_symbology.xlsx')
display(lqd_corp_symbology)

# Import market prices EOD
market_prices_eod = pd.read_excel('data/market_prices_eod.xlsx')
display(market_prices_eod)

# Import SOFR swaps market data
sofr_swaps_market_data_eod = pd.read_excel('data/sofr_swaps_market_data_eod.xlsx')
display(sofr_swaps_market_data_eod)

# Import SOFR swaps symbology
sofr_swaps_symbology = pd.read_excel('data/sofr_swaps_symbology.xlsx')
display(sofr_swaps_symbology)
```

```python
# Load bond_symbology.xlsx
bond_symbology = pd.read_excel('bond_symbology.xlsx')

# Set as-of-date
as_of_date = pd.to_datetime('2024-04-01')

# Add term and TTM columns
bond_symbology['term'] = (bond_symbology['maturity'] - bond_symbology['start_date']).dt.days / 365.25
bond_symbology['TTM'] = (bond_symbology['maturity'] - as_of_date).dt.days / 365.25

# Create Govt bonds symbology df
govt_symbology = bond_symbology[(bond_symbology['class'] == 'Govt') 
                                   & (bond_symbology['ticker'] == 'T')].copy()

# Display govt_symbology
display(govt_symbology.head())
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
	  <th>329</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 000 DKHP 42</td>
	  <td>US 912810 EG 95</td>
	  <td>US 9127963 M 90</td>
	  <td>T 8 3/4 08/15/20</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>8.750</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1990-08-15</td>
	  <td>2020-08-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>17059.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>INAC</td>
	  <td>30.001369</td>
	  <td>-3.627652</td>
	</tr>
	<tr>
	  <th>330</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 000 DJN 4 B 7</td>
	  <td>US 912810 EH 78</td>
	  <td>NaN</td>
	  <td>T 7 7/8 02/15/21</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>7.875</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1991-02-15</td>
	  <td>2021-02-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>10076.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>INAC</td>
	  <td>30.001369</td>
	  <td>-3.123888</td>
	</tr>
	<tr>
	  <th>331</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 000 DHBM 88</td>
	  <td>US 912810 EJ 35</td>
	  <td>NaN</td>
	  <td>T 8 1/8 05/15/21</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>8.125</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1991-05-15</td>
	  <td>2021-05-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>10067.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>INAC</td>
	  <td>30.001369</td>
	  <td>-2.880219</td>
	</tr>
	<tr>
	  <th>332</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 000 DKP 182</td>
	  <td>US 912810 EK 08</td>
	  <td>NaN</td>
	  <td>T 8 1/8 08/15/21</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>8.125</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1991-08-15</td>
	  <td>2021-08-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>9506.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>INAC</td>
	  <td>30.001369</td>
	  <td>-2.628337</td>
	</tr>
	<tr>
	  <th>333</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 000 DFRYP 0</td>
	  <td>US 912810 EL 80</td>
	  <td>NaN</td>
	  <td>T 8 11/15/21</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>8.000</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>1991-11-15</td>
	  <td>2021-11-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>30632.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>INAC</td>
	  <td>30.001369</td>
	  <td>-2.376454</td>
	</tr>
  </tbody>
</table>
<p>5 rows × 25 columns</p>
</div>

```python
# 10y cut-off date
cut_off_date_10y = pd.to_datetime('2014-04-01')
govt_symbology_10y = govt_symbology[govt_symbology['start_date'] >= cut_off_date_10y].copy()

# Plot the US Treasury coupons by issue date (last 10 years)
govt_symbology_10y.plot(x='start_date',                    y='coupon',                    grid=True,                    style='-*',                    title='US Treasury coupons by issue date (last 10 years)',                    figsize=(12,                   8))
```

    <Axes: title={'center': 'US Treasury coupons by issue date (last 10 years)'},                    xlabel='start_date'>
![png](CreditMarketSolutions_7_1.png)

## b. Historical time series of US treasury coupons

Plot the time series of coupons for for US treasury notes/bonds issued in the last 10 years (indexed by issue date).
What can you say about the overall level of issued coupons in the last 4 years?

```python
import plotly.express as px

fig = px.scatter(govt_symbology_10y,                    x='start_date',                    y='coupon',                    title='US Treasury coupons by issue date (last 10 years)')
fig.update_layout(xaxis_title='Issue Date',                    yaxis_title='Coupon',                    template='plotly_white')
fig.show()
```

```python
# 4y cut-off date
cut_off_date_4y = pd.to_datetime('2020-04-01')
govt_symbology_4y = govt_symbology[govt_symbology['start_date'] >= cut_off_date_4y].copy()

# Plot the US Treasury coupons by issue date (last 10 years)
govt_symbology_4y.plot(x='start_date',                    y='coupon',                    grid=True,                    style='-*',                    title='US Treasury coupons by issue date (last 4 years)',                    figsize=(12,                   8))

# describe
govt_symbology_4y[['start_date',                    'coupon']].describe()
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
	  <th>start_date</th>
	  <th>coupon</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>count</th>
	  <td>239</td>
	  <td>239.000000</td>
	</tr>
	<tr>
	  <th>mean</th>
	  <td>2022-04-11 07:37:54.476987392</td>
	  <td>2.366109</td>
	</tr>
	<tr>
	  <th>min</th>
	  <td>2020-04-15 00:00:00</td>
	  <td>0.125000</td>
	</tr>
	<tr>
	  <th>25%</th>
	  <td>2021-04-07 12:00:00</td>
	  <td>0.625000</td>
	</tr>
	<tr>
	  <th>50%</th>
	  <td>2022-04-18 00:00:00</td>
	  <td>2.500000</td>
	</tr>
	<tr>
	  <th>75%</th>
	  <td>2023-04-08 12:00:00</td>
	  <td>4.000000</td>
	</tr>
	<tr>
	  <th>max</th>
	  <td>2024-04-01 00:00:00</td>
	  <td>5.000000</td>
	</tr>
	<tr>
	  <th>std</th>
	  <td>NaN</td>
	  <td>1.663802</td>
	</tr>
  </tbody>
</table>
</div>

![png](CreditMarketSolutions_10_1.png)

What can you say about the overall level of issued coupons in the last 4 years?

Based on the summary statistics provided,  we can make following observations:

- The average (mean) coupon rate is 2.367.
- The median coupon rate (50 th percentile) is 2.5
- The minimum coupon rate is 0.125,  while the maximum is 5.00.
- The coupon rate increased from decade lows of 0.125 in 2020,  to decade highs of 5.00 in 2023.

## c. Load the on-the-run US treasuries

Load the `govt_on_the_run` Excel file into a dataframe. Select the current on-the-run 2 Y,  3 Y,  5 Y,  7 Y,  10 Y,  20 Y and 30 Y issues (off-the-run issues have the B & C suffix). Create a separate symbology dataframe for on-the-run treasuries only,  to be used later on for the on-the-run government yield curve bootstrapping.

```python
# Load govt_on_the_run,                    as of 2024-04-01

# Keep OTR treasuries only
govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run['ticker'].str.contains('B|C')]
display(govt_on_the_run_simple)
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
	<tr>
	  <th>15</th>
	  <td>GT 5 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 M 44 ZQJ 1</td>
	  <td>US 91282 CKG 59</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>GT 7 Govt</td>
	  <td>2024-04-19</td>
	  <td>BBG 01 M 44 ZS 07</td>
	  <td>US 91282 CKF 76</td>
	</tr>
  </tbody>
</table>
</div>

```latex

```python
# Create symbology for on-the-run treasuries only
govt_symbology_otr = govt_symbology[govt_symbology['isin'].isin(govt_on_the_run_simple['isin'])]
govt_symbology_otr = govt_symbology_otr.sort_values(by='TTM')
display(govt_symbology_otr)
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
	  <th>879</th>
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
	  <td>2024-03-31</td>
	  <td>2026-03-31</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>66000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>1.995893</td>
	  <td>1.995893</td>
	</tr>
	<tr>
	  <th>878</th>
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
	  <td>2024-03-31</td>
	  <td>2029-03-31</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>67000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>4.996578</td>
	  <td>4.996578</td>
	</tr>
	<tr>
	  <th>877</th>
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
	  <td>2024-03-31</td>
	  <td>2031-03-31</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>43000.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>6.995209</td>
	  <td>6.995209</td>
	</tr>
	<tr>
	  <th>871</th>
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
	  <td>2024-02-15</td>
	  <td>2034-02-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>84104.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>10.001369</td>
	  <td>9.875428</td>
	</tr>
	<tr>
	  <th>434</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 LK 8 Y 0 L 1</td>
	  <td>US 912810 TZ 12</td>
	  <td>US 912810 TZ 12</td>
	  <td>T 4 1/2 02/15/44</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.500</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2024-02-15</td>
	  <td>2044-02-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>29684.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>19.961670</td>
	  <td>19.874059</td>
	</tr>
	<tr>
	  <th>433</th>
	  <td>T</td>
	  <td>Govt</td>
	  <td>BBG 01 L 8 YJKX 8</td>
	  <td>US 912810 TX 63</td>
	  <td>US 912810 TX 63</td>
	  <td>T 4 1/4 02/15/54</td>
	  <td>US TREASURY N/B</td>
	  <td>US GOVERNMENT</td>
	  <td>4.250</td>
	  <td>FIXED</td>
	  <td>…</td>
	  <td>2024-02-15</td>
	  <td>2054-02-15</td>
	  <td>NORMAL</td>
	  <td>Unsecured</td>
	  <td>48846.0</td>
	  <td>US</td>
	  <td>USD</td>
	  <td>ACTV</td>
	  <td>30.001369</td>
	  <td>29.875428</td>
	</tr>
  </tbody>
</table>
<p>6 rows × 25 columns</p>
</div>

## d. Load and explore US [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] symbology data

Starting from the `bond_symbology` dataframe,  create a corporate bond dataframe containing

- bullet/non-callable (mty_typ="AT MATURITY"),
- senior unsecured (rank = "Sr Unsecured"),
- fixed coupon (cpn_type="FIXED")

Bonds only,  with following columns:

| ticker | isin | figi | security | name | coupon | start_date | maturity | term | TTM |
|----------|-------|-------|-------------|-----|----------|---------|---------|---------|---------|

Where

- `term` refers to the initial term/time-to-maturity in years
- `TTM` refers to the current time-to-maturity in years

Create a separate dataframe for VZ issuer only (ticker = 'VZ') and display it.

```python
# Create Corp bonds symbology df
corp_symbology = bond_symbology[bond_symbology['class'] == 'Corp'].copy()

corp_symbology = corp_symbology[(corp_symbology['mty_typ'] == 'AT MATURITY') 
                                   & (corp_symbology['rank'] == 'Sr Unsecured')
                                   & (corp_symbology['cpn_type'] == 'FIXED')]

# Keep selected columns only
corp_symbology = corp_symbology[['ticker',                    'isin',                    'figi',                    'security',                    'name',                    'coupon',                    'start_date',                    'maturity',                    'term',                    'TTM']]

# Filter for VZ issuer
corp_symbology_vz =  corp_symbology[corp_symbology['ticker'] == 'VZ']
corp_symbology_vz = corp_symbology_vz.sort_values(by='TTM')

# Display corp_symbology_vz
display(corp_symbology_vz)
```

# Problem 2: Explore EOD market prices and yields

## a. Load and explore treasury market prices and yields

Load the `bond_market_prices_eod` Excel file into a dataframe. It provides market data for US treasuries and [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] as of 2024-04-01.

Merge the treasuries symbology dataframe with the market data and add the following columns:

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
|----------|-------|-------------|-----|----------|---------|---------|---------|---------|

Plot a graph/scatter plot of treasury mid yields by TTM.

```python
# Load bond_market_prices_eod
bond_market_prices_eod['midPrice'] = 0.5*(bond_market_prices_eod['bidPrice'] + bond_market_prices_eod['askPrice'])
bond_market_prices_eod['midYield'] = 0.5*(bond_market_prices_eod['bidYield'] + bond_market_prices_eod['askYield'])

display(bond_market_prices_eod.head())

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

```python
# Merge market data as of 2024-04-01 into treasury symbology
govt_agg = govt_symbology.merge(bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])

govt_agg.head()

# Plot a graph/scatter plot of treasury mid yields by TTM
govt_agg.plot(x='TTM',                    y='midYield',                    grid=True,                    style='*',                    title='US Treasury Yields by TTM',                    figsize=(12,                   8))
```

    <Axes: title={'center': 'US Treasury Yields by TTM'},                    xlabel='TTM'>
![png](CreditMarketSolutions_20_1.png)

```python
Merge market data as of 2024-04-01 into treasury symbology
govt_agg = govt_symbology.merge(bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])

govt_agg.head()

fig = px.scatter(govt_agg,                    x='TTM',                    y='midYield',                    title='US Treasury Yields by TTM')
fig.update_layout(xaxis_title='Time to Maturity (Years)',                    yaxis_title='Mid Yield',                    template='plotly_white')
fig.show()
```

      Cell In[25],                    line 1
        Merge market data as of 2024-04-01 into treasury symbology
                                     ^
    SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers

## b. Explore on-the-run treasuries only

Create a separate joint dataframe for on-the-run treasuries only.

Plot a graph/scatter plot of on-the-run treasury mid yields by TTM.

```python
# Merge market data as of 2024-04-01 into treasury OTR symbology
govt_agg_otr = govt_symbology_otr.merge(bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])

fig = px.scatter(govt_agg_otr,                    x='TTM',                    y='midYield',                    title='OTR US Treasury yields by TTM')
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',                    yaxis_title='Mid Yield',                    template='plotly_white')
Fig.Show ()
```

## c. Load and explore corporate bond market prices and yields

Merge the filtered [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] symbology dataframe with the market data and add the following columns:

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
|----------|-------|-------------|-----|----------|---------|---------|---------|---------|

List the unique tickers/issuers available in the dataframe.

```python
# Merge market data as of 2024-04-01 into corp symbology
Corp_agg = corp_symbology.Merge (bond_market_prices_eod,                     on=['ticker',                   'figi',                   'isin'])

Print (corp_symbology. Shape)

Display (corp_agg.Head ())
```

    (67,                    10)

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
	  <th>isin</th>
	  <th>figi</th>
	  <th>security</th>
	  <th>name</th>
	  <th>coupon</th>
	  <th>start_date</th>
	  <th>maturity</th>
	  <th>term</th>
	  <th>TTM</th>
	  <th>date</th>
	  <th>class</th>
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
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>APPLE INC</td>
	  <td>3.850</td>
	  <td>2013-05-03</td>
	  <td>2043-05-04</td>
	  <td>30.001369</td>
	  <td>19.088296</td>
	  <td>2024-04-19</td>
	  <td>Corp</td>
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
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>APPLE INC</td>
	  <td>4.450</td>
	  <td>2014-05-06</td>
	  <td>2044-05-06</td>
	  <td>30.001369</td>
	  <td>20.095825</td>
	  <td>2024-04-19</td>
	  <td>Corp</td>
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
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>APPLE INC</td>
	  <td>3.450</td>
	  <td>2015-02-09</td>
	  <td>2045-02-09</td>
	  <td>30.001369</td>
	  <td>20.859685</td>
	  <td>2024-04-19</td>
	  <td>Corp</td>
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
	  <td>US 037833 BH 21</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>APPLE INC</td>
	  <td>4.375</td>
	  <td>2015-05-13</td>
	  <td>2045-05-13</td>
	  <td>30.001369</td>
	  <td>21.114305</td>
	  <td>2024-04-19</td>
	  <td>Corp</td>
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
	  <td>DIS</td>
	  <td>US 254687 DV 52</td>
	  <td>BBG 00 QNKP 8 R 8</td>
	  <td>DIS 6.55 03/15/33</td>
	  <td>WALT DISNEY COMPANY/THE</td>
	  <td>6.550</td>
	  <td>2019-11-22</td>
	  <td>2033-03-15</td>
	  <td>13.311431</td>
	  <td>8.952772</td>
	  <td>2024-04-19</td>
	  <td>Corp</td>
	  <td>109.441</td>
	  <td>110.055</td>
	  <td>0.6910</td>
	  <td>5.209</td>
	  <td>5.127</td>
	  <td>109.7480</td>
	  <td>5.1680</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Unique tickers
corp_agg_unique_tickers = corp_agg [['ticker',                    'name']]. drop_duplicates ()

Display (corp_agg_unique_tickers)
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
	  <th>name</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL</td>
	  <td>APPLE INC</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>DIS</td>
	  <td>WALT DISNEY COMPANY/THE</td>
	</tr>
	<tr>
	  <th>21</th>
	  <td>F</td>
	  <td>FORD MOTOR CREDIT CO LLC</td>
	</tr>
	<tr>
	  <th>22</th>
	  <td>GM</td>
	  <td>GENERAL MOTORS FINL CO</td>
	</tr>
	<tr>
	  <th>24</th>
	  <td>IBM</td>
	  <td>IBM CORP</td>
	</tr>
	<tr>
	  <th>37</th>
	  <td>MS</td>
	  <td>MORGAN STANLEY</td>
	</tr>
	<tr>
	  <th>46</th>
	  <td>ORCL</td>
	  <td>ORACLE CORP</td>
	</tr>
	<tr>
	  <th>49</th>
	  <td>VZ</td>
	  <td>VERIZON COMMUNICATIONS</td>
	</tr>
  </tbody>
</table>
</div>

## d. Yield curve plots

Plot a graph/scatter plot of mid yield curves by TTM (one line per ticker/issuer).

Add a separate line for on-the-run US treasury yield curve (risk free curve).

What can you say about the credit issuer yields,  compared to US treasury yields?

```python
Fig = px.Scatter (corp_agg,                    x='TTM',                    y='midYield',                    color='ticker',                    title='Corporate Bond Yields by TTM')
Fig. Add_trace (px.Scatter (govt_agg_otr,                    x='TTM',                    y='midYield'). Data[0])
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',                    yaxis_title='Mid Yield',                    template='plotly_white')
Fig.Show ()
```

# Problem 3: Underlying treasury benchmarks and credit spreads

## a. Add underlying benchmark bond mid yields

Start with the corporate bond symbology dataframe. Use the column 'und_bench_yield' to identify the underlying benchmark bond for each bond issue.

Add two new columns to the joint corporate bond dataframe:

| und_bench_yield | credit_spread |
|----------|-------|

Where

- `und_bench_yield` = underlying benchmark bond mid yield and
- `credit_spread` = issue yield - underlying benchmark bond mid yield.

```python
# Use the column 'und_bench_yield' to identify the underlying benchmark bond for each bond issue.
corp_merged = corp_agg.Merge (bond_symbology [['isin',                    'und_bench_isin']],                    on='isin')

# Create df containing govt_benchmark_yields
govt_benchmark_yields = bond_market_prices_eod[bond_market_prices_eod['class'] == 'Govt'][['isin',                    'midYield']]
Govt_benchmark_yields.Rename (columns={'midYield': 'und_bench_yield',                    'isin': 'und_bench_isin'},                    inplace=True)

# Add benchmark bond yield
Corp_merged = corp_merged.Merge (govt_benchmark_yields,                    on='und_bench_isin')
Corp_merged['credit_spread'] = corp_merged['midYield'] - corp_merged['und_bench_yield']
display (corp_merged [['ticker',                    'isin',                    'figi',                    'security',                    'und_bench_isin',                    'midYield',                    'und_bench_yield',                    'credit_spread']])
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
	  <th>isin</th>
	  <th>figi</th>
	  <th>security</th>
	  <th>und_bench_isin</th>
	  <th>midYield</th>
	  <th>und_bench_yield</th>
	  <th>credit_spread</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL</td>
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3295</td>
	  <td>4.8410</td>
	  <td>0.4885</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL</td>
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.2360</td>
	  <td>4.8410</td>
	  <td>0.3950</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL</td>
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3575</td>
	  <td>4.8410</td>
	  <td>0.5165</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL</td>
	  <td>US 037833 BH 21</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3720</td>
	  <td>4.8410</td>
	  <td>0.5310</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>DIS</td>
	  <td>US 254687 DV 52</td>
	  <td>BBG 00 QNKP 8 R 8</td>
	  <td>DIS 6.55 03/15/33</td>
	  <td>US 91282 CJZ 59</td>
	  <td>5.1680</td>
	  <td>4.6220</td>
	  <td>0.5460</td>
	</tr>
	<tr>
	  <th>…</th>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	</tr>
	<tr>
	  <th>62</th>
	  <td>VZ</td>
	  <td>US 92343 VEA 89</td>
	  <td>BBG 00 HC 11 V 79</td>
	  <td>VZ 4 1/2 08/10/33</td>
	  <td>US 91282 CJZ 59</td>
	  <td>5.5545</td>
	  <td>4.6220</td>
	  <td>0.9325</td>
	</tr>
	<tr>
	  <th>63</th>
	  <td>VZ</td>
	  <td>US 92344 GAM 87</td>
	  <td>BBG 00003 TCX 8</td>
	  <td>VZ 7 3/4 12/01/30</td>
	  <td>US 91282 CKG 59</td>
	  <td>5.4835</td>
	  <td>4.6710</td>
	  <td>0.8125</td>
	</tr>
	<tr>
	  <th>64</th>
	  <td>VZ</td>
	  <td>US 92343 VER 15</td>
	  <td>BBG 00 M 1 BQWX 0</td>
	  <td>VZ 4.329 09/21/28</td>
	  <td>US 91282 CKG 59</td>
	  <td>5.3755</td>
	  <td>4.6710</td>
	  <td>0.7045</td>
	</tr>
	<tr>
	  <th>65</th>
	  <td>VZ</td>
	  <td>US 92343 VDY 74</td>
	  <td>BBG 00 G 6 QW 2 B 8</td>
	  <td>VZ 4 1/8 03/16/27</td>
	  <td>US 91282 CKJ 98</td>
	  <td>5.3295</td>
	  <td>4.8225</td>
	  <td>0.5070</td>
	</tr>
	<tr>
	  <th>66</th>
	  <td>VZ</td>
	  <td>US 92343 VDD 38</td>
	  <td>BBG 00 DGYP 877</td>
	  <td>VZ 2 5/8 08/15/26</td>
	  <td>US 91282 CKH 33</td>
	  <td>5.4150</td>
	  <td>4.9870</td>
	  <td>0.4280</td>
	</tr>
  </tbody>
</table>
<p>67 rows × 8 columns</p>
</div>

## b. Credit spread curve plots

Plot a graph/scatter plot of credit spread curves by TTM (one line per issuer).

```python
Fig = px.Scatter (corp_merged,                    x='TTM',                    y='credit_spread',                    color='ticker',                    title='Corporate Bond Credit Spreads by TTM')
Fig. Update_traces (mode='lines+markers') 
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',                    yaxis_title='Credit Spread',                    template='plotly_white')
Fig.Show ()
```

## c. Add g-spreads

Add two new columns to the joint corporate bond dataframe:

| interp_tsy_yield | g_spread |
|----------|-------|

Where

- `interp_tsy_yield` = interpolated treasury yield (using on-the-run treasuries only),  matching the issue maturity
- `g_spread` = issue yield - interp_tsy_yield.

```python
# Interpolate OTR Treasury yields on corporate bond TTMs
Interp_tsy_yield_vec = np.Interp (corp_merged['TTM'],                    govt_agg_otr['TTM'],                    govt_agg_otr['midYield'])

# Add interp_tsy_yield and g_spread
Corp_merged['interp_tsy_yield'] = interp_tsy_yield_vec
Corp_merged['g_spread'] = corp_merged['midYield'] - corp_merged['interp_tsy_yield']

# Display results
display (corp_merged [['ticker',                    'isin',                    'figi',                    'security',                    'und_bench_isin',                    'midYield',                    'und_bench_yield',                    'credit_spread',                    'interp_tsy_yield',                    'g_spread']])
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
	  <th>isin</th>
	  <th>figi</th>
	  <th>security</th>
	  <th>und_bench_isin</th>
	  <th>midYield</th>
	  <th>und_bench_yield</th>
	  <th>credit_spread</th>
	  <th>interp_tsy_yield</th>
	  <th>g_spread</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>AAPL</td>
	  <td>US 037833 AL 42</td>
	  <td>BBG 004 HST 0 K 7</td>
	  <td>AAPL 3.85 05/04/43</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3295</td>
	  <td>4.8410</td>
	  <td>0.4885</td>
	  <td>4.823789</td>
	  <td>0.505711</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>AAPL</td>
	  <td>US 037833 AT 77</td>
	  <td>BBG 006 F 8 VWJ 7</td>
	  <td>AAPL 4.45 05/06/44</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.2360</td>
	  <td>4.8410</td>
	  <td>0.3950</td>
	  <td>4.838151</td>
	  <td>0.397849</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>AAPL</td>
	  <td>US 037833 BA 77</td>
	  <td>BBG 0081 TNL 50</td>
	  <td>AAPL 3.45 02/09/45</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3575</td>
	  <td>4.8410</td>
	  <td>0.5165</td>
	  <td>4.828336</td>
	  <td>0.529164</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>AAPL</td>
	  <td>US 037833 BH 21</td>
	  <td>BBG 008 N 1 BQC 1</td>
	  <td>AAPL 4 3/8 05/13/45</td>
	  <td>US 912810 TZ 12</td>
	  <td>5.3720</td>
	  <td>4.8410</td>
	  <td>0.5310</td>
	  <td>4.825065</td>
	  <td>0.546935</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>DIS</td>
	  <td>US 254687 DV 52</td>
	  <td>BBG 00 QNKP 8 R 8</td>
	  <td>DIS 6.55 03/15/33</td>
	  <td>US 91282 CJZ 59</td>
	  <td>5.1680</td>
	  <td>4.6220</td>
	  <td>0.5460</td>
	  <td>4.631770</td>
	  <td>0.536230</td>
	</tr>
	<tr>
	  <th>…</th>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	  <td>…</td>
	</tr>
	<tr>
	  <th>62</th>
	  <td>VZ</td>
	  <td>US 92343 VEA 89</td>
	  <td>BBG 00 HC 11 V 79</td>
	  <td>VZ 4 1/2 08/10/33</td>
	  <td>US 91282 CJZ 59</td>
	  <td>5.5545</td>
	  <td>4.6220</td>
	  <td>0.9325</td>
	  <td>4.627480</td>
	  <td>0.927020</td>
	</tr>
	<tr>
	  <th>63</th>
	  <td>VZ</td>
	  <td>US 92344 GAM 87</td>
	  <td>BBG 00003 TCX 8</td>
	  <td>VZ 7 3/4 12/01/30</td>
	  <td>US 91282 CKG 59</td>
	  <td>5.4835</td>
	  <td>4.6710</td>
	  <td>0.8125</td>
	  <td>4.655541</td>
	  <td>0.827959</td>
	</tr>
	<tr>
	  <th>64</th>
	  <td>VZ</td>
	  <td>US 92343 VER 15</td>
	  <td>BBG 00 M 1 BQWX 0</td>
	  <td>VZ 4.329 09/21/28</td>
	  <td>US 91282 CKG 59</td>
	  <td>5.3755</td>
	  <td>4.6710</td>
	  <td>0.7045</td>
	  <td>4.711414</td>
	  <td>0.664086</td>
	</tr>
	<tr>
	  <th>65</th>
	  <td>VZ</td>
	  <td>US 92343 VDY 74</td>
	  <td>BBG 00 G 6 QW 2 B 8</td>
	  <td>VZ 4 1/8 03/16/27</td>
	  <td>US 91282 CKJ 98</td>
	  <td>5.3295</td>
	  <td>4.8225</td>
	  <td>0.5070</td>
	  <td>4.835487</td>
	  <td>0.494013</td>
	</tr>
	<tr>
	  <th>66</th>
	  <td>VZ</td>
	  <td>US 92343 VDD 38</td>
	  <td>BBG 00 DGYP 877</td>
	  <td>VZ 2 5/8 08/15/26</td>
	  <td>US 91282 CKH 33</td>
	  <td>5.4150</td>
	  <td>4.9870</td>
	  <td>0.4280</td>
	  <td>4.927693</td>
	  <td>0.487307</td>
	</tr>
  </tbody>
</table>
<p>67 rows × 10 columns</p>
</div>

## d. G-spread curve plots

Plot a graph/scatter plot of g-spread curves by TTM (one line per issuer).

```python
Fig = px.Scatter (corp_merged,                    x='TTM',                    y='g_spread',                    color='ticker',                    title='Corporate Bond G-Spreads by TTM')
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',                    yaxis_title='G-Spread',                    template='plotly_white') 
Fig.Show ()
```

# Problem 4: Explore sections 1 to 5 in the QuantLib example notebook

Explore sections 1 to 5 in the example notebook and identify concepts discussed in the first lecture. Collect open questions for the upcoming TA Review session on the analytics library.

Find the 'ORCL 2.95 04/01/30' bond (mentioned on page 12 in Session 1) in the bond symbology file. Create the corresponding fixed rate bond object and display the future cashflows. Do you match the cashflows displayed on page 13?

Going forward,  we will be using QuantLib for curve calibration (US Treasury + SOFR),  as well as pricing and risk of various cash and synthetic credit instruments.

```python
# Find the 'ORCL 2.95 04/01/30' bond in bond symbology
Corp_symbology_orcl = bond_symbology[bond_symbology['security'] == 'ORCL 2.95 04/01/30']

Display (corp_symbology_orcl.Transpose ())
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
	  <th>312</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>ticker</th>
	  <td>ORCL</td>
	</tr>
	<tr>
	  <th>class</th>
	  <td>Corp</td>
	</tr>
	<tr>
	  <th>figi</th>
	  <td>BBG 00 SXGDGF 0</td>
	</tr>
	<tr>
	  <th>isin</th>
	  <td>US 68389 XBV 64</td>
	</tr>
	<tr>
	  <th>und_bench_isin</th>
	  <td>US 91282 CKG 59</td>
	</tr>
	<tr>
	  <th>security</th>
	  <td>ORCL 2.95 04/01/30</td>
	</tr>
	<tr>
	  <th>name</th>
	  <td>ORACLE CORP</td>
	</tr>
	<tr>
	  <th>type</th>
	  <td>GLOBAL</td>
	</tr>
	<tr>
	  <th>coupon</th>
	  <td>2.95</td>
	</tr>
	<tr>
	  <th>cpn_type</th>
	  <td>FIXED</td>
	</tr>
	<tr>
	  <th>dcc</th>
	  <td>30/360</td>
	</tr>
	<tr>
	  <th>cpn_freq</th>
	  <td>2</td>
	</tr>
	<tr>
	  <th>days_settle</th>
	  <td>2</td>
	</tr>
	<tr>
	  <th>start_date</th>
	  <td>2020-04-01 00:00:00</td>
	</tr>
	<tr>
	  <th>cpn_first</th>
	  <td>2020-10-01 00:00:00</td>
	</tr>
	<tr>
	  <th>acc_first</th>
	  <td>2020-04-01 00:00:00</td>
	</tr>
	<tr>
	  <th>maturity</th>
	  <td>2030-04-01 00:00:00</td>
	</tr>
	<tr>
	  <th>mty_typ</th>
	  <td>CALLABLE</td>
	</tr>
	<tr>
	  <th>rank</th>
	  <td>Sr Unsecured</td>
	</tr>
	<tr>
	  <th>amt_out</th>
	  <td>3250.0</td>
	</tr>
	<tr>
	  <th>country</th>
	  <td>US</td>
	</tr>
	<tr>
	  <th>currency</th>
	  <td>USD</td>
	</tr>
	<tr>
	  <th>status</th>
	  <td>ACTV</td>
	</tr>
	<tr>
	  <th>term</th>
	  <td>9.998631</td>
	</tr>
	<tr>
	  <th>TTM</th>
	  <td>5.998631</td>
	</tr>
  </tbody>
</table>
</div>

```python
# Construct fixed rate cashflow schedule for ORCL 2.95 04/01/30

Issue_date = ql.Date (1,                    4,                    2020)        # 2020-04-01
Maturity_date = ql.Date (1,                    4,                    2030)     # 2030-04-01

Coupon_freq = ql. Semiannual
Coupon_term = ql.Period (coupon_freq)
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Day_count_conv = ql. Unadjusted
Date_generation = ql. DateGeneration. Backward
Month_end = True

# Fixed_rate_schedule
Fixed_rate_schedule = ql.Schedule (issue_date,                   
                       Maturity_date,                   
                       Coupon_term,                   
                       Calendar,                   
                       Day_count_conv,                   
                       Day_count_conv,                   
                       Date_generation,                   
                       Month_end)
```

```python
# Construct corporate bond object for ORCL 2.95 04/01/30

# Day_count: 30/360 for fixed-rate Corp bonds
Day_count = ql. Thirty 360 (ql. Thirty 360. USA)

# Settlement_days: 2 for Corp Bonds
Settlement_days = 2

# Coupons
Coupon_rate = 0.295     # 2.95%
Coupons = [coupon_rate]

# Payment_convention
Payment_convention = ql. Unadjusted

# Face_value
Face_value = 100
# Construct the fixed_rate_bond
Face_value = 100
Fixed_rate_bond = ql.FixedRateBond (
    Settlement_days,                   
    Face_value,                   
    Fixed_rate_schedule,                   
    Coupons,                   
    Day_count,                   
    Payment_convention)
```

```python
# Display the contractual cashflows. 
X = [(cf.Date (). To_date (),                    cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date_fixed,                    cf_amount = zip (*x)
Fixed_rate_bond_cashflows = pd.DataFrame (data={'CashFlowDate': cf_date_fixed,                    'CashFlowAmount': cf_amount})

# Cashflows match the ones displayed on page 13 (from Bloomberg CSHF screenshot),                    up to the face value multiplier.
Display (fixed_rate_bond_cashflows)
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
	  <th>CashFlowDate</th>
	  <th>CashFlowAmount</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>2020-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2021-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2021-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2022-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2022-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>2023-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>2023-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>2024-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>2024-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>9</th>
	  <td>2025-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>2025-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>2026-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>2026-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>2027-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>2027-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>15</th>
	  <td>2028-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>16</th>
	  <td>2028-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>17</th>
	  <td>2029-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>18</th>
	  <td>2029-10-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>19</th>
	  <td>2030-04-01</td>
	  <td>14.75</td>
	</tr>
	<tr>
	  <th>20</th>
	  <td>2030-04-01</td>
	  <td>100.00</td>
	</tr>
  </tbody>
</table>
</div>

# Credit Markets
## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

- Alex Popovici
- alex.popovici@uchicago.edu

# Basic Usage of QuantLib analytics library
## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1\. Objects and Handles
  - a. Define a quote object and inspect the value
  - b. Define quoteHandle as a handle/smart pointer to the quote object
  - c. Calendars and day-count conventions
- 2\. Cashflow Schedules
  - a. Construct semi-annual cashflow schedule object,  for fixed-rate bonds
  - b. Inspect the semi-annual cashflow schedule
  - c. Construct quarterly cashflow schedule object,  for floating-rate bonds
  - d. Inspect the quarterly cashflow schedule
- 3\. Discount Curve / Yield Curve Term Structure
  - a. Constructing a Flat Yield Curve
  - b. Inspect the discount curve
- 4\. Fixed and Floating Rate Bonds
  - a. Constructing a fixed rate bond object
  - b. Investigate the fixed-rate bond cash-flows
  - c. Constructing a floating rate bond object: linked to SOFR index
- 5\. Bond Present Value Calculation (no credit risk)
  - a. Direct function call using risk-free bond pricing engine
  - b. Manual Calculation to validate PV (for fixed and floating-rate bonds)
  - c. Bond Clean vs Dirty Prices (adjusted to settle date)
- 6\. Market Data Scenarios
  - a. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices
  - b. Compute scenario DV 01,  duration and convexity
  - c. Yield to Price conversions
  - d. Price to Yield conversions
- 7\. Analytical Duration,  Convexity and Z-Spread (flat yield model)
  - a. Compute bond duration,  convexity and Z-Spread
  - b. Validate Z-Spread
- 8\. Treasury Yield Curve Calibration (via Bootstrapping)
  - a. Calibrate treasury flat yield curve (simple case of one calibration instrument)
  - b. Display the calibrated Treasury discount curve dataframe
  - c. Plot the calibrated Treasury Zero Rates and Discount Factors curves
  - d. Reprice the bond on the yield curve to validate the calibration

```python
Import QuantLib as ql
Import numpy as np
Import pandas as pd
```

# 1. Objects and Handles
## a. Define a quote object and inspect the value

```python
Quote = ql.SimpleQuote (. 01)
Print (quote.Value ())

Quote.SetValue (. 02)
Print (quote.Value ())
```

    0.01
    0.02

## b. Define quoteHandle as a handle/smart pointer to the quote object

```python
QuoteHandle = ql.QuoteHandle (quote)
QuoteHandle.Value ()
```

    0.02

### When the quote object is changed,  the quoteHandle changes value as well

```python
Quote.SetValue (. 03)
QuoteHandle.Value ()
```

    0.03

## c. Calendars and day-count conventions

```python
# Dates
Todays_date = ql.Date.TodaysDate ()
Test_date = todays_date + 90
Print ('todays_date =',                    todays_date)
Print ('test_date =',                    test_date)
# Calendars
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Holiday_list = list (calendar.HolidayList (todays_date,                    test_date))
Print ('holiday_list =',                    holiday_list)
# Day count conventions
Day_count = ql. Actual 360 ()
Print ('day_count =',                    day_count)

# Year fractions
Test_year_fraction = day_count.YearFraction (todays_date,                    test_date)
Print ('Year Fraction  from',                    todays_date,                    'to',                    test_date,                   '] =',                    test_year_fraction)
```

    Todays_date = May 4 th,                    2024
    Test_date = August 2 nd,                    2024
    Holiday_list = [Date (27,                   5,                   2024),                    Date (19,                   6,                   2024),                    Date (4,                   7,                   2024)]
    Day_count = Actual/360 day counter
    Year Fraction  from May 4 th,                    2024 to August 2 nd,                    2024 ] = 0.25

# 2. Cashflow Schedules
## a. Construct semi-annual cashflow schedule object,  for fixed-rate bonds

```python
Issue_date = ql.Date (2,                    4,                    2024)        # 2024-04-02
Maturity_date = ql.Date (2,                    4,                    2028)     # 2028-04-02
Coupon_freq = ql. Semiannual
Coupon_term = ql.Period (coupon_freq)
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Day_count_conv = ql. Unadjusted
Date_generation = ql. DateGeneration. Backward
Month_end = True

# Fixed_rate_schedule
Fixed_rate_schedule = ql.Schedule (issue_date,                   
                       Maturity_date,                   
                       Coupon_term,                   
                       Calendar,                   
                       Day_count_conv,                   
                       Day_count_conv,                   
                       Date_generation,                   
                       Month_end)
```

## b. Inspect the semi-annual cashflow schedule
- Use list () to get a list of all the dates in Schedule,  and len () to get number of dates
- Use ] for random access
- Use startDate (),  endDate ()

```python
Print ("All dates: ",                    list (fixed_rate_schedule))
Print ("Length: ",                    len (fixed_rate_schedule))
Print ("The 3 rd coupon date: ",                    [fixed_rate_schedule])  # random access
Print ("Start Date: ",                    fixed_rate_schedule.StartDate ())
Print ("End Date: ",                    fixed_rate_schedule.EndDate ())
```

    All dates:  [Date (2,                   4,                   2024),                    Date (2,                   10,                   2024),                    Date (2,                   4,                   2025),                    Date (2,                   10,                   2025),                    Date (2,                   4,                   2026),                    Date (2,                   10,                   2026),                    Date (2,                   4,                   2027),                    Date (2,                   10,                   2027),                    Date (2,                   4,                   2028)]
    Length:  9
    The 3 rd coupon date:  [<QuantLib.QuantLib.Schedule; proxy of <Swig Object of type 'Schedule *' at 0x17891c9c0> >]
    Start Date:  April 2 nd,                    2024
    End Date:  April 2 nd,                    2028

## c. Construct quarterly cashflow schedule object,  for floating-rate bonds

```python
# Floating_rate_bond_schedule
Floating_rate_schedule = ql.Schedule (
    Issue_date,                   
    Maturity_date,                   
    Ql.Period (ql. Quarterly),                   
    Calendar,                   
    Day_count_conv,                   
    Day_count_conv,                   
    Date_generation,                   
    Month_end,                   
)
```

## d. Inspect the quarterly cashflow schedule

```python
Print ("All dates: ",                    list (floating_rate_schedule))
Print ("Length: ",                    len (floating_rate_schedule))
Print ("Start Date: ",                    fixed_rate_schedule.StartDate ())
Print ("End Date: ",                    fixed_rate_schedule.EndDate ())
```

    All dates:  [Date (2,                   4,                   2024),                    Date (2,                   7,                   2024),                    Date (2,                   10,                   2024),                    Date (2,                   1,                   2025),                    Date (2,                   4,                   2025),                    Date (2,                   7,                   2025),                    Date (2,                   10,                   2025),                    Date (2,                   1,                   2026),                    Date (2,                   4,                   2026),                    Date (2,                   7,                   2026),                    Date (2,                   10,                   2026),                    Date (2,                   1,                   2027),                    Date (2,                   4,                   2027),                    Date (2,                   7,                   2027),                    Date (2,                   10,                   2027),                    Date (2,                   1,                   2028),                    Date (2,                   4,                   2028)]
    Length:  17
    Start Date:  April 2 nd,                    2024
    End Date:  April 2 nd,                    2028

# 3. Discount Curve / Yield Curve Term Structure
## a. Constructing a Flat Yield Curve

```python
# Set the static valuation date: 2024-04-02
Calc_date = ql.Date (2,                    4,                    2024)
Ql.Settings.Instance (). EvaluationDate = calc_date

# Using 5% flat interest rate for testing
Flat_rate = ql.SimpleQuote (0.05)
Rate_handle = ql.QuoteHandle (flat_rate)
Day_count = ql. Actual 360 ()
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Continuous_comp = ql. Continuous # continously compounded rate of 5%
Flat_yield_curve = ql.FlatForward (calc_date,                    rate_handle,                    day_count,                    continuous_comp)
Flat_yield_curve_handle = ql.YieldTermStructureHandle (flat_yield_curve)
```

## b. Inspect the discount curve

```python
Ref_date = flat_yield_curve.ReferenceDate ()
Test_date = ql.Date (30,                    6,                    2025)

# Calc year fraction between ref_date and test_date
YearFrac = flat_yield_curve.DayCounter (). YearFraction (ref_date,                    test_date)

Print ("Reference Date =",                    ref_date)
Print ("Test Date =",                    test_date)
Print ("Year Fraction between Reference Date and Test Date : ",                    yearFrac)
Print ("Discount Factor for Test Date",                    test_date,                    ": ",                    flat_yield_curve.Discount (test_date))
Print ("custom DF calculation for Test Date",                    test_date,                    ": ",                    np.Exp (-flat_rate.Value () * yearFrac))
Print ("Difference in Discount Factor: ",                    flat_yield_curve.Discount (test_date) - np.Exp (-flat_rate.Value () * yearFrac))
```

    Reference Date = April 2 nd,                    2024
    Test Date = June 30 th,                    2025
    Year Fraction between Reference Date and Test Date :  1.261111111111111
    Discount Factor for Test Date June 30 th,                    2025 :  0.9388913116117773
    Custom DF calculation for Test Date June 30 th,                    2025 :  0.9388913116117772
    Difference in Discount Factor: 1.1102230246251565 e-16

# 4. Fixed and Floating Rate Bonds
## a. Constructing a fixed rate bond object

```python
# Day_count: ACT/ACT for Govt bonds
Day_count_govt = ql.ActualActual (ql. ActualActual. ISMA)

# Day_count: 30/360 for fixed-rate Corp bonds
Day_count_corp_fixed = ql. Thirty 360 (ql. Thirty 360. USA)

# Day_count: ACT/360 for floating-rate bonds
Day_count_floater = ql. Actual 360 ()
# Settlement_days: 1 for Govt bonds
Settlement_days_govt = 1

# Settlement_days: 2 for Corp Bonds
Settlement_days_corp = 2

# Govt Bonds specs
Day_count = day_count_govt
Settlement_days = settlement_days_govt

# Coupons
Coupon_rate = 0.04
Coupons = [coupon_rate]

# Payment_convention
Payment_convention = ql. Unadjusted

# Face_value
Face_value = 100
# Construct the fixed_rate_bond
Face_value = 100
Fixed_rate_bond = ql.FixedRateBond (
    Settlement_days,                   
    Face_value,                   
    Fixed_rate_schedule,                   
    Coupons,                   
    Day_count,                   
    Payment_convention)
```

## b. Investigate the fixed-rate bond cash-flows

```python
X = [(cf.Date (),                    cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date_fixed,                    cf_amount = zip (*x)
Cf_frame_fixed = pd.DataFrame (data={'CashFlowDate': cf_date_fixed,                    'CashFlowAmount': cf_amount})
Display (cf_frame_fixed)
```

            CashFlowDate  CashFlowAmount
    0  October 2 nd,                    2024             2.0
    1    April 2 nd,                    2025             2.0
    2  October 2 nd,                    2025             2.0
    3    April 2 nd,                    2026             2.0
    4  October 2 nd,                    2026             2.0
    5    April 2 nd,                    2027             2.0
    6  October 2 nd,                    2027             2.0
    7    April 2 nd,                    2028             2.0
    8    April 2 nd,                    2028           100.0

## c. Constructing a floating rate bond object: linked to SOFR index

```python
# Sofr_term_structure_handle: using 5% flat interest rate for testing
Rate_handle = ql.QuoteHandle (ql.SimpleQuote (5/100))
Sofr_term_structure = ql.FlatForward (calc_date,                    rate_handle,                    day_count_floater,                    ql. Continuous)
Sofr_term_structure_handle = ql.YieldTermStructureHandle (sofr_term_structure)

# Set SOFR index history
Im = ql.IndexManager.Instance ()
Sofr_index = ql.Sofr (sofr_term_structure_handle)

# Set SOFR fixings
Im.ClearHistory (sofr_index.Name ())
Sofr_index.AddFixing (ql.Date (28,                    ql. March,                    2024),                    5/100)
Sofr_index.AddFixing (ql.Date (1,                    ql. April,                    2024),                    5/100)
# Floating_rate_bond
Floating_rate_bond = ql.FloatingRateBond (settlement_days,                   
                                Face_value,                   
                                Floating_rate_schedule,                   
                                Sofr_index,                   
                                Day_count_floater,                   
                                Payment_convention,                   
                                Spreads=[25/10000],                    # 25 bps floating rate
                                IssueDate=issue_date)

```

```python
X = [(cf.Date (),                    cf.Amount ()) for cf in floating_rate_bond.Cashflows ()]
Cf_date_float,                    cf_amount = zip (*x)
Cf_frame_float = pd.DataFrame (data={'CashFlowDate': cf_date_float,                    'CashFlowAmount': cf_amount})
Print (cf_frame_float)
```

             CashFlowDate  CashFlowAmount
    0      July 2 nd,                    2024        1.335104
    1   October 2 nd,                    2024        1.349865
    2   January 2 nd,                    2025        1.349865
    3     April 2 nd,                    2025        1.320345
    4      July 2 nd,                    2025        1.335104
    5   October 2 nd,                    2025        1.349865
    6   January 2 nd,                    2026        1.349865
    7     April 2 nd,                    2026        1.320345
    8      July 2 nd,                    2026        1.335104
    9   October 2 nd,                    2026        1.349865
    10  January 2 nd,                    2027        1.350044
    11    April 2 nd,                    2027        1.320520
    12     July 2 nd,                    2027        1.335104
    13  October 2 nd,                    2027        1.350044
    14  January 2 nd,                    2028        1.350044
    15    April 2 nd,                    2028        1.335370
    16    April 2 nd,                    2028      100.000000

# 5. Bond Present Value Calculation (no credit risk)
## a. Direct function call using risk-free bond pricing engine

```python
# Fixed_rate_bond PV
Bond_engine = ql.DiscountingBondEngine (flat_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (bond_engine)
Fixed_rate_bond_pv = fixed_rate_bond.NPV ()
Print ('fixed_rate_bond_pv =',                    fixed_rate_bond_pv)

# Floating_rate_bond PV
Floating_rate_bond.SetPricingEngine (bond_engine)
Floating_rate_bond_pv = floating_rate_bond.NPV ()
Print ('floating_rate_bond_pv =',                    floating_rate_bond_pv)
```

    Fixed_rate_bond_pv = 95.93321956659715
    Floating_rate_bond_pv = 100.91327849916414

## b. Manual Calculation to validate PV (for fixed and floating-rate bonds)

```python
# Validate fixed-rate bond PV
Used_cf_frame = cf_frame_fixed
Used_bond_pv = fixed_rate_bond_pv

# Validate floating-rate bond PV
Discount_yearfrac = np.Zeros ((len (used_cf_frame,                   )))
Discount_factor = np.Zeros ((len (used_cf_frame,                   )))

I = 0
For cf_date in used_cf_frame['CashFlowDate']:
    Discount_yearfrac[i] = flat_yield_curve.DayCounter (). YearFraction (flat_yield_curve.ReferenceDate (),                    cf_date)
    Discount_factor[i] = flat_yield_curve.Discount (cf_date)
    I += 1

Used_cf_frame['YearFrac'] = discount_yearfrac
Used_cf_frame['DiscountFactor'] = discount_factor
Used_cf_frame['NPV'] = used_cf_frame['CashFlowAmount'] * used_cf_frame['DiscountFactor']

Used_cf_frame
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
	  <th>CashFlowDate</th>
	  <th>CashFlowAmount</th>
	  <th>YearFrac</th>
	  <th>DiscountFactor</th>
	  <th>NPV</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>October 2 nd,  2024</td>
	  <td>2.0</td>
	  <td>0.508333</td>
	  <td>0.974904</td>
	  <td>1.949807</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>April 2 nd,  2025</td>
	  <td>2.0</td>
	  <td>1.013889</td>
	  <td>0.950569</td>
	  <td>1.901138</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>October 2 nd,  2025</td>
	  <td>2.0</td>
	  <td>1.522222</td>
	  <td>0.926713</td>
	  <td>1.853426</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>April 2 nd,  2026</td>
	  <td>2.0</td>
	  <td>2.027778</td>
	  <td>0.903582</td>
	  <td>1.807163</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>October 2 nd,  2026</td>
	  <td>2.0</td>
	  <td>2.536111</td>
	  <td>0.880905</td>
	  <td>1.761810</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>April 2 nd,  2027</td>
	  <td>2.0</td>
	  <td>3.041667</td>
	  <td>0.858917</td>
	  <td>1.717833</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>October 2 nd,  2027</td>
	  <td>2.0</td>
	  <td>3.550000</td>
	  <td>0.837361</td>
	  <td>1.674722</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>April 2 nd,  2028</td>
	  <td>2.0</td>
	  <td>4.058333</td>
	  <td>0.816346</td>
	  <td>1.632693</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>April 2 nd,  2028</td>
	  <td>100.0</td>
	  <td>4.058333</td>
	  <td>0.816346</td>
	  <td>81.634627</td>
	</tr>
  </tbody>
</table>
</div>

```python
Pv_manual = used_cf_frame['NPV']. Sum ()
Print ('NPV engine = ',                    used_bond_pv)
Print ('NPV manual = ',                    pv_manual)
Print ('NPV diff = ',                    pv_manual - used_bond_pv)
```

    NPV engine =  95.93321956659715
    NPV manual =  95.93321956659715
    NPV diff =  0.0

## c. Bond Clean vs Dirty Prices (adjusted to settle date)

```python
Print ('Bond Notional = ',                    fixed_rate_bond.Notional ())
Print ('Settle Date = ',                    fixed_rate_bond.SettlementDate ())
Print ('Discount Factor to Settle Date = ',                    round (flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),                    4))
Print ('Bond NPV (Calc Date) = ',                    round (fixed_rate_bond.NPV (),                    4))
Print ('Bond NPV Adjusted to Settle Date = ',                    round (fixed_rate_bond.NPV () / flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),                    4))
Print ('Bond Dirty Price = ',                    round (fixed_rate_bond.DirtyPrice (),                    4))
Print ('Bond Clean Price = ',                    round (fixed_rate_bond.CleanPrice (),                    4))
Print ('Bond Accrued = ',                    round (fixed_rate_bond.AccruedAmount (),                    4))

```

    Bond Notional =  100.0
    Settle Date =  April 3 rd,                    2024
    Discount Factor to Settle Date =  0.9999
    Bond NPV (Calc Date) =  95.9332
    Bond NPV Adjusted to Settle Date =  95.9465
    Bond Dirty Price =  95.9465
    Bond Clean Price =  95.9356
    Bond Accrued =  0.0109

# 6. Market Data Scenarios
## a. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices

```python
# Start with interest_rate_bump = 0
Interest_rate_bump = ql.SimpleQuote (0.0)
Flat_yield_curve_bumped = ql.ZeroSpreadedTermStructure (flat_yield_curve_handle,                    ql.QuoteHandle (interest_rate_bump))

Bond_engine = ql.DiscountingBondEngine (ql.YieldTermStructureHandle (flat_yield_curve_bumped))
Fixed_rate_bond.SetPricingEngine (bond_engine)

Price_base = fixed_rate_bond.CleanPrice ()

# Original price (zero interest rate bump)
Print ("Price (base case): ",                    round (price_base,                    4))

# Bump interest rate by +1 bps (parallel shift)
Interest_rate_bump.SetValue (0.0001)
Price_up_1 bp = fixed_rate_bond.CleanPrice ()
Print ("Price in +1 bps scenario: ",                    round (price_up_1 bp,                    4))
Print ("Price diff in +1 bps scenario: ",                    round (price_up_1 bp - price_base,                    6))

# Bump interest rate by -1 bps (parallel shift)
Interest_rate_bump.SetValue (-0.0001)
Price_down_1 bp = fixed_rate_bond.CleanPrice ()
Print ("Price for -1 bps scenario: ",                    round (price_down_1 bp,                    4))
Print ("Price diff in -1 bps scenario: ",                    round (price_down_1 bp - price_base,                    6))

 # Remove interest rate bump
Interest_rate_bump.SetValue (0)
```

    Price (base case):  95.9356
    Price in +1 bps scenario:  95.8993
    Price diff in +1 bps scenario:  -0.036268
    Price for -1 bps scenario: 95.9719
    Price diff in -1 bps scenario:  0.036283

## b. Compute scenario DV 01,  duration and convexity

```python
# Compute scenario delta/gamma sensitivities
Dv 01 = round ((price_down_1 bp - price_base) * 1 e 4 / 100,                    4)
Duration = round (dv 01 / fixed_rate_bond.DirtyPrice () * 100,                    4)
Gamma_1 bp = (price_down_1 bp - 2*price_base + price_up_1 bp) * 1 e 8 / 100
Convexity = round (gamma_1 bp / fixed_rate_bond.DirtyPrice () * 100,                    4)

Print ("DV 01: ",                    dv 01)
Print ("Duration: ",                    duration)
Print ("Convexity: ",                    convexity)
```

    DV 01:  3.6283
    Duration:  3.7816
    Convexity:  14.9262

## c. Yield to Price conversions

```python
# Use original interest rate yield of 5%
# Flat_rate.SetValue (0.05)
Print ('Bond PV for',                    flat_rate.Value ()*100,                    'pct yield: ',                    round (fixed_rate_bond.NPV (),                    4))
# Change interest rate yield to 6% and recompute bond PV
Flat_rate.SetValue (0.06)
Print ('Bond PV for',                    flat_rate.Value ()*100,                    'pct yield: ',                    round (fixed_rate_bond.NPV (),                    4))

# Set interest rate yield back to 5%
Flat_rate.SetValue (0.05)
```

    Bond PV for 5.0 pct yield: 95.9332
    Bond PV for 6.0 pct yield: 92.3743

## d. Price to Yield conversions

```python
# Bond_market_price = fixed_rate_bond.CleanPrice ()
Bond_market_price = 95.00   # Clean market price

Compounding = ql. Compounded
# Compounding = ql. Continuous

Settle_date = fixed_rate_bond.SettlementDate (calc_date)
Day_counter = fixed_rate_bond.DayCounter ()

Print ('day_counter =',                    day_counter)
Print ('coupon_freq =',                    coupon_freq)
Print ('calc_date =',                    calc_date)
Print ('settle_date =',                    settle_date)
Implied_yield = fixed_rate_bond.BondYield (bond_market_price,                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 100
Print ('implied_yield =',                    round (implied_yield,                    4))
```

    Day_counter = Actual/Actual (ISMA) day counter
    Coupon_freq = 2
    Calc_date = April 2 nd,                    2024
    Settle_date = April 3 rd,                    2024
    Implied_yield = 5.4076

# 7. Analytical Duration,  Convexity and Z-Spread (flat yield model)
## a. Compute bond duration,  convexity and Z-Spread

```python
# Flat_bond_yield (used as an input to compute duration and convexity)
Flat_bond_yield = 5.5 # in pct
Flat_bond_yield_rate = ql.InterestRate (flat_bond_yield/100,                    day_count,                    compounding,                    coupon_freq)

# Calc Duration and Convexity
Bond_duration = ql.BondFunctions.Duration (fixed_rate_bond,                    flat_bond_yield_rate)
Bond_convexity = ql.BondFunctions.Convexity (fixed_rate_bond,                    flat_bond_yield_rate)

# Calc z-spread for a given market price
Bond_market_price = 95.3194     # Clean market price,                    implies zero Z-Spread!
Bond_market_price = 95          # Test market price,                    implies Z-Spread > 0
Bond_zspread = ql.BondFunctions.ZSpread (fixed_rate_bond,                    bond_market_price,                    flat_yield_curve,                    day_count,                    compounding,                    coupon_freq,                    settle_date)

# Print results
Print ('Bond Duration =',                    round (bond_duration,                    4))
Print ('Bond Convexity =',                    round (bond_convexity,                    4))
Print ('Bond Z-Spread bps =',                    round (bond_zspread * 10000,                    4))

```

    Bond Duration = 3.6247
    Bond Convexity = 15.4882
    Bond Z-Spread bps = 26.5978

## b. Validate Z-Spread

```python
Def calc_clean_price_with_zspread (fixed_rate_bond,                    yield_curve_handle,                    zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,                    zspread_quote_handle,                    ql. Compounded,                    ql. Semiannual)
    Yield_curve_bumped_handle = ql.YieldTermStructureHandle (yield_curve_bumped)
    
    # Set Valuation engine
    Bond_engine = ql.DiscountingBondEngine (yield_curve_bumped_handle)
    Fixed_rate_bond.SetPricingEngine (bond_engine)
    Bond_clean_price = fixed_rate_bond.CleanPrice ()
    Return bond_clean_price

```

```python
# Compare the original and the z-spread computed clean prices
Bond_zspread_price = calc_clean_price_with_zspread (fixed_rate_bond,                    flat_yield_curve_handle,                    bond_zspread)

Print ('Bond Z-Spread bps =',                    round (bond_zspread * 10000,                    2))
Print ('bond_market_price =',                    bond_market_price)
Print ('bond_zspread_price =',                    bond_zspread_price)
Print ('bond price diff =',                    bond_zspread_price - bond_market_price)
```

    Bond Z-Spread bps = 26.6
    Bond_market_price = 95
    Bond_zspread_price = 94.99999999999486
    Bond price diff = -5.144329406903125 e-12

# 8. Treasury Yield Curve Calibration (via Bootstrapping)
## a. Calibrate treasury flat yield curve (simple case of one calibration instrument)

```python
# Fixed_rate_bond: 4% coupon and 2028-04-02 maturity

# Clean price quote
Tsy_clean_price_quote = 96.0
Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
# Create BondHelper object
Bond_helper = ql.BondHelper (
    Tsy_clean_price_handle,                   
    Fixed_rate_bond)

Bond_helper_list = [bond_helper]
        
Tsy_flat_yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,                    bond_helper_list,                    day_count)
Tsy_flat_yield_curve.EnableExtrapolation ()

Tsy_yield_curve_handle = ql.YieldTermStructureHandle (tsy_flat_yield_curve)

```

## b. Display the calibrated Treasury discount curve dataframe

```python
Def get_yield_curve_details_df (yield_curve,                    curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),                    3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),                    3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,                    yield_curve.DayCounter (),                    ql. Compounded). Rate () * 100,                    3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,                   
                             'YearFrac': yearfracs,                   
                             'DiscountFactor': discounts,                   
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
```

```python
# Display Treasury yield curve details
Tsy_flat_yield_curve_simple_df = get_yield_curve_details_df (tsy_flat_yield_curve)                  # using calibration grid
Display (tsy_flat_yield_curve_simple_df)

Grid_dates = [tsy_flat_yield_curve.ReferenceDate () + ql.Period (y,                    ql. Years) for y in list (range (0,                   30,                   2))]
Tsy_flat_yield_curve_details_df = get_yield_curve_details_df (tsy_flat_yield_curve,                    grid_dates)    # using external grid
Display (tsy_flat_yield_curve_details_df)

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
	  <td>2023-04-14</td>
	  <td>0.000</td>
	  <td>1.000</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2030-04-01</td>
	  <td>6.964</td>
	  <td>0.135</td>
	  <td>33.285</td>
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
	  <td>2023-04-14</td>
	  <td>0.0</td>
	  <td>1.000</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2025-04-14</td>
	  <td>2.0</td>
	  <td>0.563</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2027-04-14</td>
	  <td>4.0</td>
	  <td>0.317</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2029-04-14</td>
	  <td>6.0</td>
	  <td>0.178</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2031-04-14</td>
	  <td>8.0</td>
	  <td>0.100</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>2033-04-14</td>
	  <td>10.0</td>
	  <td>0.057</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>2035-04-14</td>
	  <td>12.0</td>
	  <td>0.032</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>2037-04-14</td>
	  <td>14.0</td>
	  <td>0.018</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>2039-04-14</td>
	  <td>16.0</td>
	  <td>0.010</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>9</th>
	  <td>2041-04-14</td>
	  <td>18.0</td>
	  <td>0.006</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>2043-04-14</td>
	  <td>20.0</td>
	  <td>0.003</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>2045-04-14</td>
	  <td>22.0</td>
	  <td>0.002</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>2047-04-14</td>
	  <td>24.0</td>
	  <td>0.001</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>2049-04-14</td>
	  <td>26.0</td>
	  <td>0.001</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>2051-04-14</td>
	  <td>28.0</td>
	  <td>0.000</td>
	  <td>33.285</td>
	</tr>
  </tbody>
</table>
</div>

## c. Plot the calibrated Treasury Zero Rates and Discount Factors curves

```python
Plt = tsy_flat_yield_curve_details_df.Plot (x='Date',                    y='ZeroRate',                    grid=True,                    style='*-',                    title='Treasury Flat Curve: Zero Rates',                    figsize=(12,                   4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = tsy_flat_yield_curve_details_df.Plot (x='Date',                    y='DiscountFactor',                    grid=True,                    style='*-',                    title='Treasury Flat Curve: Discount Factors',                    figsize=(12,                   4))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```

    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_101_1.png)

![png](CreditMarketSolutions_101_2.png)

## d. Reprice the bond on the yield curve to validate the calibration

```python
# 1. Price risk-free bond
Risk_free_bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_handle)

Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
Risk_free_bond_price = fixed_rate_bond.CleanPrice ()
Risk_free_bond_yield = fixed_rate_bond.BondYield (risk_free_bond_price,                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 100

Print ('tsy_clean_price_quote: ',                    tsy_clean_price_quote)
Print ('risk_free_bond_price: ',                    risk_free_bond_price)
Print ('price_calibration_error: ',                    risk_free_bond_price-tsy_clean_price_quote)
Print ('risk_free_bond_yield: ',                    risk_free_bond_yield)

```

    Tsy_clean_price_quote: 96.0
    Risk_free_bond_price: 96.0
    Price_calibration_error: 0.0
    Risk_free_bond_yield: 5.119227409362794

# Homework 2

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

### Due Date: 2024-04-16

- Alex Popovici
- alex.popovici@uchicago.edu

This homework relies on:

- The corporate and government bonds symbology file `bond_symbology`,
- The "on-the-run" treasuries data file `govt_on_the_run`,
- The bond market data file `bond_market_prices_eod`,  containing EOD price data as of 2024-04-08.

# Problem 1: Constructing fixed rate bonds

```python
Import QuantLib as ql
Import pandas as pd
Import datetime as dt

# Use static calculation/valuation date of 2024-04-08,                    matching data available in the market prices EOD file
Calc_date = ql.Date (8,                    4,                    2024)
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

# Load govt_on_the_run,                    as of 2024-04-08
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
    If isinstance (date,                    dt. Date):
        Return ql.Date (date. Day,                    date. Month,                    date. Year)
    Elif isinstance (date,                    str):
        Date = dt.Datetime.Strptime (date,                    "%Y-%m-%d"). Date ()
        Return ql.Date (date. Day,                    date. Month,                    date. Year)
    Else:
        Raise ValueError (f"to_qldate,                    {type (date)},                    {date}")
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
    
    # define period from details['cpn_freq'] ... Can be hard-coded to 2 = semi-annual frequency
    Period = ql.Period (2)
    
    # business_day_convention
    Business_day_convention = ql. Unadjusted
    
    # termination_date_convention
    Termination_date_convention = ql. Unadjusted
    
    # date_generation
    Date_generation=ql. DateGeneration. Backward
    
    # Create schedule using ql. MakeSchedule interface (with keyword arguments)
    Schedule = ql.MakeSchedule (effectiveDate=acc_first,                     # this may not be the same as the bond's start date
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
Print ("Corp bond details for",                    corp_bond_details['security'])
Display (corp_bond_details)

# Create cashflow_schedule
Cashflow_schedule = create_schedule_from_symbology (corp_bond_details)
Print ("Cashflow dates for",                    corp_bond_details['security'])

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
    Name: 10,                    dtype: object
    Cashflow dates for AAPL 3.35 02/09/27
    February 9 th,                    2017
    August 9 th,                    2017
    February 9 th,                    2018
    August 9 th,                    2018
    February 9 th,                    2019
    August 9 th,                    2019
    February 9 th,                    2020
    August 9 th,                    2020
    February 9 th,                    2021
    August 9 th,                    2021
    February 9 th,                    2022
    August 9 th,                    2022
    February 9 th,                    2023
    August 9 th,                    2023
    February 9 th,                    2024
    August 9 th,                    2024
    February 9 th,                    2025
    August 9 th,                    2025
    February 9 th,                    2026
    August 9 th,                    2026
    February 9 th,                    2027

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
        Raise ValueError (f"unsupported asset class,                    {type (details['class'])},                    {details['class']}")
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

Print ("Corp bond object details for",                    corp_bond_details['security'])
Print ('Start date: ',                    corp_bond_object.StartDate ())
Print ('Maturity date: ',                    corp_bond_object.MaturityDate ())
Print ('Bond face notional: ',                    corp_bond_object.Notional ())

```

    Corp bond object details for AAPL 3.35 02/09/27
    Start date: February 9 th,                    2017
    Maturity date: February 9 th,                    2027
    Bond face notional: 100.0

## d. Add function that returns a dataframe with (future) cash flows details for a bond object

Use the "Investigate Bond Cashflows" section in the Quantlib Basic notebook as a template.

The results dataframe should contain following columns:

| CashFlowDate | CashFlowAmount | CashFlowYearFrac |
|----------|-------|-------------|

Pick one government and one corporate bond from symbology,  create the bond objects and display the future cashflows.

```python
Def get_bond_cashflows (bond: ql. FixedRateBond,                    calc_date=ql. Date) -> pd. DataFrame:
    '''Returns all future cashflows as of calc_date,                    i.e. with payment dates > calc_date.
    '''    
    Day_counter = bond.DayCounter ()    
    
    X = [(cf.Date (),                    day_counter.YearFraction (calc_date,                    cf.Date ()),                    cf.Amount ()) for cf in bond.Cashflows ()]
    Cf_date,                    cf_yearFrac,                    cf_amount = zip (*x)
    Cashflows_df = pd.DataFrame (data={'CashFlowDate': cf_date,                    'CashFlowYearFrac': cf_yearFrac,                    'CashFlowAmount': cf_amount})

    # filter for payment dates > calc_date
    Cashflows_df = cashflows_df[cashflows_df. CashFlowYearFrac > 0]
    Return cashflows_df

```

```python
# Pick one government and one corporate bond from symbology,                    create the bond objects.
Govt_bond_details = bond_symbology[bond_symbology['class'] == 'Govt']. Iloc[10]
Print ("Govt bond details for",                    govt_bond_details['security'])
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
    Name: 348,                    dtype: object

```python
# Govt bond: display the future cashflows.
Print ("Govt bond future cashflows for",                    govt_bond_details['security'])
Govt_bond_cf = get_bond_cashflows (govt_bond_object,                    calc_date=calc_date)
Display (govt_bond_cf)

# Corp bond: display the future cashflows.
Print ("Corp bond future cashflows for",                    corp_bond_details['security'])
Corp_bond_cf = get_bond_cashflows (corp_bond_object,                    calc_date=calc_date)
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
Govt_combined_otr = govt_symbology_otr.Merge (bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])

# Plot a graph/scatter plot of treasury OTR mid yields by TTM
Govt_combined_otr.Plot (x='TTM',                    y='midYield',                    grid=True,                    style='*-',                    title='OTR US Treasury yields by TTM',                    figsize=(12,                   4))
```

    <Axes: title={'center': 'OTR US Treasury yields by TTM'},                    xlabel='TTM'>
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
    
    For index,                    row in sorted_details_frame.Iterrows ():
        Bond_object = create_bond_from_symbology (row)
        
        Tsy_clean_price_quote = row[price_quote_column]
        Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
        
        Bond_helper = ql.BondHelper (tsy_clean_price_handle,                    bond_object)
        Bond_helpers.Append (bond_helper)
        
    Yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,                    bond_helpers,                    day_count)
    # yield_curve = ql.PiecewiseFlatForward (calc_date,                    bond_helpers,                    day_count)
    
    Yield_curve.EnableExtrapolation ()
    Return yield_curve
Def get_yield_curve_details_df (yield_curve,                    curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),                    3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),                    3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,                    yield_curve.DayCounter (),                    ql. Compounded). Rate () * 100,                    3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,                   
                             'YearFrac': yearfracs,                   
                             'DiscountFactor': discounts,                   
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
```

```python
# Calibrate the bid,                    ask and mid discount factor curves as of 2024-04-08.
Tsy_yield_curve_bid = calibrate_yield_curve_from_frame (calc_date,                    govt_combined_otr,                    'bidPrice')
Tsy_yield_curve_mid = calibrate_yield_curve_from_frame (calc_date,                    govt_combined_otr,                    'midPrice')
Tsy_yield_curve_ask = calibrate_yield_curve_from_frame (calc_date,                    govt_combined_otr,                    'askPrice')

# Display the calibration results for the mid curve
Tsy_yield_curve_df = get_yield_curve_details_df (tsy_yield_curve_mid)
Display (tsy_yield_curve_df)

Ql_dates_yearly = [calc_date + ql.Period (y,                    ql. Years) for y in list (range (0,                    30,                    1))]
Tsy_yield_curve_monthly_df = get_yield_curve_details_df (tsy_yield_curve_mid,                    curve_dates=ql_dates_yearly)
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
Plt = tsy_yield_curve_df.Plot (x='Date',                    y=['ZeroRate'],                    style='*-',                    grid=True,                    title=f'US Treasury OTR yield curve as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = tsy_yield_curve_monthly_df.Plot (x='Date',                    y=['ZeroRate'],                    style='*-',                    grid=True,                    title=f'US Treasury Yearly yield curve as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

```

    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_129_1.png)

![png](CreditMarketSolutions_129_2.png)

## d. Plot calibrated discount factors

Plot the discount factor curve up to the 30 years point,  using a 6 months discretization grid.

```python
Plt = tsy_yield_curve_df.Plot (x='Date',                    y=['DiscountFactor'],                    style='*-',                    grid=True,                    title=f'US Treasury OTR discount factor curve as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Discount Factor')
Plt. Set_xlabel ('Date')

Plt = tsy_yield_curve_monthly_df.Plot (x='Date',                    y=['DiscountFactor'],                    style='*-',                    grid=True,                    title=f'US Treasury Yearly discount factor curve as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Discount Factor')
Plt. Set_xlabel ('Date')
```

    Text (0.5,                    0,                    'Date')
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
For index,                    row in govt_combined_otr.Iterrows ():
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    Calculated_mid_prices.Append (bond_object.CleanPrice ())
    
Govt_combined_otr['calc_mid_price'] = calculated_mid_prices
Govt_combined_otr['calib_error'] = govt_combined_otr['midPrice'] - govt_combined_otr['calc_mid_price']

# Compare the calculated clean mid prices to the original market mid prices.
display (govt_combined_otr [['security',                    'isin',                    'figi',                    'midPrice',                    'calc_mid_price',                    'calib_error']])
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

# Calculate dv 01 s,                    durations and convexities
Dv 01 s = []
Calc_durations = []
Calc_convexities = []

For index,                    row in govt_combined_otr.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()    
    
    Bond_yield = bond_object.BondYield (row['calc_mid_price'],                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 100
    
    Flat_int_rate = ql.InterestRate (bond_yield / 100,                    day_counter,                    compounding,                    coupon_freq)
    Bond_duration = ql.BondFunctions.Duration (bond_object,                    flat_int_rate)
    Bond_convexity = ql.BondFunctions.Convexity (bond_object,                    flat_int_rate)
    Bond_dv 01 = bond_object.DirtyPrice () * bond_duration / 100
    
    Dv 01 s.Append (bond_dv 01)
    Calc_durations.Append (bond_duration)
    Calc_convexities.Append (bond_convexity)

# Add new risk columns and display results    
Govt_combined_otr['dv 01'] = dv 01 s
Govt_combined_otr['duration'] = calc_durations
Govt_combined_otr['convexity'] = calc_convexities

display (govt_combined_otr [['security',                    'isin',                    'figi',                    'calc_mid_price',                    'dv01',                    'duration',                    'convexity']])

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
# Calculate scenario dv 01 s,                    durations and convexities
Scen_dv 01 s = []
Scen_durations = []
Scen_convexities = []

For index,                    row in govt_combined_otr.Iterrows ():
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    # create interest rate scenarios
    Interest_rate_bump = ql.SimpleQuote (0.0)
    Calibrated_yield_curve_bumped = ql.ZeroSpreadedTermStructure (tsy_yield_curve_mid_handle,                    ql.QuoteHandle (interest_rate_bump))
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

display (govt_combined_otr [['security',                    'isin',                    'figi',                   'scen_dv01',                    'scen_duration',                    'scen_convexity']])

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
Corp_combined = corp_symbology.Merge (bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])

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

For index,                    row in corp_combined.Iterrows ():
    Bond_details = row. To_dict ()
    Corp_bond_object = create_bond_from_symbology (bond_details)
    Corp_bond_object_dict[row['security']] = corp_bond_object
    
# Display the future cashflows for one corp bond object in the dictionary
Corp_bond_key = corp_combined. Iloc[10]['security']
Corp_bond_cf = get_bond_cashflows (corp_bond_object_dict[corp_bond_key],                    calc_date=calc_date)

Print ("Corp bond future cashflows for",                    corp_bond_key)
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

For index,                    row in corp_combined.Iterrows ():
        
    Bond_object = create_bond_from_symbology (row)    
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()

    Clean_price = bond_object.CleanPrice ()
    
    # yield in pct
    Calc_yield = bond_object.BondYield (clean_price,                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 1 e 2
    Flat_int_rate = ql.InterestRate (calc_yield / 100,                    day_counter,                    compounding,                    coupon_freq)
    Bond_market_price = row['midPrice']
    
    # zspread in bps
    Calc_zspread = ql.BondFunctions.ZSpread (bond_object,                    bond_market_price,                    tsy_yield_curve_mid,                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 1 e 4
    
    Calc_yields.Append (calc_yield)
    Calc_zspreads.Append (calc_zspread)

# Add new columns and display results
Corp_combined['calc_yield'] = calc_yields
Corp_combined['calc_zspread'] = calc_zspreads

display (corp_combined [['security',                    'isin',                    'figi',                    'midPrice',                    'calc_yield',                    'calc_zspread']])

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
Def calc_clean_price_with_zspread (fixed_rate_bond,                    yield_curve_handle,                    zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,                    zspread_quote_handle,                    ql. Compounded,                    ql. Semiannual)
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

For index,                    row in corp_combined_small.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)    
    Bond_object.SetPricingEngine (bond_engine)
        
    Bond_zspread_price = calc_clean_price_with_zspread (bond_object,                    tsy_yield_curve_mid_handle,                    row['calc_zspread']/1 e 4)
    Bond_zspread_prices.Append (bond_zspread_price)
    
# Validate that you match the original market prices,                    which were used as input to the z-Spread function.
Corp_combined_small['bond_zspread_price'] = bond_zspread_prices
Corp_combined_small['price_difference'] = corp_combined_small['midPrice'] - corp_combined_small['bond_zspread_price']

display (corp_combined_small [['security',                    'isin',                    'figi',                    'calc_zspread',                    'midPrice',                    'bond_zspread_price',                   'price_difference']])
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

For index,                    row in corp_combined.Iterrows ():
    
    Bond_object = create_bond_from_symbology (row)
    Bond_object.SetPricingEngine (bond_engine)
    
    Settle_date = bond_object.SettlementDate (calc_date)
    Day_counter = bond_object.DayCounter ()    
    
    Bond_yield = bond_object.BondYield (row['midPrice'],                    day_counter,                    compounding,                    coupon_freq,                    settle_date) * 100
    
    Flat_int_rate = ql.InterestRate (bond_yield / 100,                    day_counter,                    compounding,                    coupon_freq)
    Bond_duration = ql.BondFunctions.Duration (bond_object,                    flat_int_rate)
    Bond_convexity = ql.BondFunctions.Convexity (bond_object,                    flat_int_rate)        
    
    Calc_durations.Append (bond_duration)
    Calc_convexities.Append (bond_convexity)

# Add new risk columns and display results
Corp_combined['calc_duration'] = calc_durations
Corp_combined['calc_convexity'] = calc_convexities

display (corp_combined [['security',                    'isin',                    'figi',                    'midPrice',                    'calc_duration',                    'calc_convexity']]. head ())

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

Plt = corp_combined_aapl.Plot (x='maturity',                    y=['calc_duration'],                    style='*-',                    grid=True,                    title=f'Duration for AAPL bonds as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Duration')
Plt. Set_xlabel ('Maturity date')

Plt = corp_combined_aapl.Plot (x='maturity',                    y=['calc_convexity'],                    style='*-',                    grid=True,                    title=f'Convexity for AAPL bonds as of {as_of_date.Date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Convexity')
Plt. Set_xlabel ('Maturity date')

```

    Text (0.5,                    0,                    'Maturity date')
![png](CreditMarketSolutions_150_1.png)

![png](CreditMarketSolutions_150_2.png)

# Credit Markets
## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

- Alex Popovici
- alex.popovici@uchicago.edu

# Advanced Usage of QuantLib analytics library
## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1\. SOFR Is swap rates and SOFR discount curve calibration
  - a. SOFR curve calibration (via Bootstrapping)
  - b. Display the calibrated SOFR discount curve dataframe
  - c. Plot the calibrated SOFR Zero Rates and Discount Factors curves
  - d. Validate SOFR calibration by pricing SOFR swaps
- 2\. Credit Default Swaps (CDS): calibration + pricing
  - a. CDS Hazard Rate calibration
  - b. Plot the calibrated Hazard Rate and Survival Probability curves
  - c. CDS valuation
- 3\. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)
  - a. Create Corporate Bond
  - b. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)
  - c. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)
- 4\. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)
  - a. Create and Display the Custom Credit Curve
  - b. Price Risky Bond on Custom Credit Curve (with Credit Risk)
- 5\. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions
  - a. Nelson Siegel basis functions
  - b. Plot Basis Functions for Nelson-Siegel + extensions
  - c. Constructing smooth Nelson-Siegel hazard rate / survival probability curves
  - d. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

```python

```

# 1. SOFR Is swap rates and SOFR discount curve calibration

## a. SOFR curve calibration (via Bootstrapping)

Overnight Index Swap contract is an interest rate swap contract exchanging and overnight index interest rate (e.g. Fed Funds,  SOFR,  LIBOR) for a fixed interest rate until the contract maturity. The fixed rate is set at a rate agreed upon by both parties. The floating leg portion of the swap is compounded and paid at reset dates.

```python
# Set the static valuation date: 2023-04-14
Calc_date = ql.Date (14,                    4,                    2023)
Ql.Settings.Instance (). EvaluationDate = calc_date

# Calendar
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)

# Settle_days
Settle_days = 2

# SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap tenors: 1 Y,                    2 Y,                    3 Y,                    5 Y 7 Y,                    10 Y,                    20 Y and 30 Y
SOFR_tenors = [ql.Period (y,                    ql. Years) for y in [1,                    2,                    3,                    5,                    7,                    10,                    20,                    30]]
               
# SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap rates (as of 2023-04-14)
SOFR_rates = [4.81,                    4.11,                    3.73,                    3.38,                    3.32,                    3.26,                    3.20,                    3.02]

SOFR_OIS_swap_helpers = []
For (SOFR_tenor,                    SOFR_rate) in zip (SOFR_tenors,                    SOFR_rates):
    SOFR_OIS_swap_helpers.Append (ql.OISRateHelper (settle_days,                    SOFR_tenor,                    ql.QuoteHandle (ql.SimpleQuote (SOFR_rate/100)),                    ql.Sofr ()))

# Create SOFR yield curve
Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,                    calendar,                    SOFR_OIS_swap_helpers,                    ql. Actual 360 ())
Sofr_yield_curve.EnableExtrapolation ()
Sofr_yield_curve_handle = ql.YieldTermStructureHandle (sofr_yield_curve)

Print (sofr_yield_curve.ReferenceDate ())

```

    April 18 th,                    2023

## b. Display the calibrated SOFR discount curve dataframe

```python
Def get_yield_curve_details_df (yield_curve,                    curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),                    3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),                    3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,                    yield_curve.DayCounter (),                    ql. Compounded). Rate () * 100,                    3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,                   
                             'YearFrac': yearfracs,                   
                             'DiscountFactor': discounts,                   
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
# Display SOFR yield curve
Grid_dates = [sofr_yield_curve.ReferenceDate () + ql.Period (y,                    ql. Years) for y in list (range (0,                   30,                   2))]
Sofr_yield_curve_simple_df = get_yield_curve_details_df (sofr_yield_curve)                  # using calibration grid
Sofr_yield_curve_details_df = get_yield_curve_details_df (sofr_yield_curve,                    grid_dates)    # using external grid

Print (sofr_yield_curve_simple_df)
Print (sofr_yield_curve_details_df)

```

             Date  YearFrac  DiscountFactor  ZeroRate
    0  2023-04-18     0.000           1.000     4.808
    1  2024-04-18     1.017           0.953     4.808
    2  2025-04-21     2.039           0.921     4.094
    3  2026-04-20     3.050           0.895     3.706
    4  2028-04-18     5.075           0.846     3.347
    5  2030-04-18     7.103           0.795     3.291
    6  2033-04-18    10.147           0.724     3.232
    7  2043-04-20    20.297           0.530     3.173
    8  2053-04-18    30.439           0.415     2.931
              Date  YearFrac  DiscountFactor  ZeroRate
    0   2023-04-18     0.000           1.000     4.808
    1   2025-04-18     2.031           0.922     4.100
    2   2027-04-18     4.058           0.869     3.527
    3   2029-04-18     6.089           0.820     3.319
    4   2031-04-18     8.117           0.770     3.272
    5   2033-04-18    10.147           0.724     3.232
    6   2035-04-18    12.175           0.680     3.221
    7   2037-04-18    14.206           0.638     3.209
    8   2039-04-18    16.233           0.600     3.197
    9   2041-04-18    18.264           0.564     3.185
    10  2043-04-18    20.292           0.530     3.173
    11  2045-04-18    22.322           0.503     3.125
    12  2047-04-18    24.350           0.478     3.076
    13  2049-04-18    26.381           0.455     3.028
    14  2051-04-18    28.408           0.434     2.979

## c. Plot the calibrated SOFR Zero Rates and Discount Factors curves

```python
Plt = sofr_yield_curve_details_df.Plot (x='Date',                    y='ZeroRate',                    grid=True,                    style='*-',                    title='SOFR Curve: Zero Rates',                    figsize=(12,                   5))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = sofr_yield_curve_details_df.Plot (x='Date',                    y='DiscountFactor',                    grid=True,                    style='*-',                    title='SOFR Curve: Discount Factors',                    figsize=(12,                   5))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```

    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_161_1.png)

![png](CreditMarketSolutions_161_2.png)

## d. Validate SOFR calibration by pricing SOFR swaps

```python
# Validate SOFR swaps
Sofr_index = ql.Sofr (sofr_yield_curve_handle)
# Swap_engine = ql.DiscountingSwapEngine (sofr_yield_curve_handle)

Print ('SOFR Swap valuation: PVs should be close to zero!')

For (SOFR_tenor,                    SOFR_rate) in zip (SOFR_tenors,                    SOFR_rates):    
    Start_date = calendar.Advance (calc_date,                    settle_days,                    ql. Days)
    Schedule = ql.MakeSchedule (start_date,                    calendar.Advance (start_date,                    SOFR_tenor),                    ql.Period ('1 Y'),                    calendar=calendar)        
    OisSwap = ql.MakeOIS (SOFR_tenor,                    sofr_index,                    SOFR_rate/100,                    nominal=100)
    
    # oisSwap.SetPricingEngine (swap_engine)
    Print ('Swap PV for',                    SOFR_tenor,                    'tenor /',                    SOFR_rate,                    'coupon : ',                    oisSwap.NPV ()) 
    
```

    SOFR Swap valuation: PVs should be close to zero!
    Swap PV for 1 Y tenor / 4.81 coupon : 0.0
    Swap PV for 2 Y tenor / 4.11 coupon : 2.842170943040401 e-14
    Swap PV for 3 Y tenor / 3.73 coupon : -4.263256414560601 e-14
    Swap PV for 5 Y tenor / 3.38 coupon : -4.033573475226149 e-11
    Swap PV for 7 Y tenor / 3.32 coupon : -2.842170943040401 e-14
    Swap PV for 10 Y tenor / 3.26 coupon : 7.105427357601002 e-15
    Swap PV for 20 Y tenor / 3.2 coupon : -2.1316282072803006 e-14
    Swap PV for 30 Y tenor / 3.02 coupon : -6.394884621840902 e-14

# 2. Credit Default Swaps (CDS): calibration + pricing
## a. CDS Hazard Rate calibration

```python
CDS_recovery_rate = 0.4

CDS_day_count = ql. Actual 360 ()

# CDS standard tenors: 1 Y,                    2 Y,                    3 Y,                    5 Y 7 Y and 10 Y
CDS_tenors = [ql.Period (y,                    ql. Years) for y in [1,                    2,                    3,                    5,                    7,                    10]]
              
# CDS spreads for IBM as of calc_date = 2023-04-14
CDS_spreads = [17.25,                    24.09,                    35.58,                    55.58,                    70.51,                    79.92]

CDS_helpers = [ql.SpreadCdsHelper ((CDS_spread / 10000.0),                    CDS_tenor,                    settle_days,                    ql.TARGET (),                   
                                  Ql. Quarterly,                    ql. Following,                    ql. DateGeneration. TwentiethIMM,                    CDS_day_count,                    CDS_recovery_rate,                    sofr_yield_curve_handle)
               
For (CDS_spread,                    CDS_tenor) in zip (CDS_spreads,                    CDS_tenors)]

# Bootstrap hazard_rate_curve
Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,                    CDS_helpers,                    CDS_day_count)
Hazard_rate_curve.EnableExtrapolation ()

# Display calibrated hazard rates and survival probabilities
Hazard_list = [(hr[0]. To_date (),                    
                CDS_day_count.YearFraction (calc_date,                    hr[0]),                   
                Hr[1] * 100,                   
                Np.Exp (-hr[1]*CDS_day_count.YearFraction (calc_date,                    hr[0])),                   
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

Grid_dates,                    year_frac,                    hazard_rates,                    sp_manual,                    surv_probs = zip (*hazard_list)

Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,                    
                                     'YearFrac': year_frac,                   
                                     'HazardRate': hazard_rates,                   
                                     'SPManual': sp_manual,                   
                                     'SurvivalProb': surv_probs})
Print (hazard_rates_df)

```

             Date   YearFrac  HazardRate  SPManual  SurvivalProb
    0  2023-04-14   0.000000    0.285237  1.000000      1.000000
    1  2024-06-20   1.202778    0.285237  0.996575      0.996575
    2  2025-06-20   2.216667    0.540041  0.988100      0.991133
    3  2026-06-22   3.236111    1.033609  0.967104      0.980745
    4  2028-06-20   5.261111    1.511140  0.923575      0.951188
    5  2030-06-20   7.288889    1.925096  0.869082      0.914772
    6  2033-06-20  10.333333    1.803340  0.829987      0.865903

## b. Plot the calibrated Hazard Rate and Survival Probability curves

```python
Plt = hazard_rates_df.Plot (x='Date',                    y='HazardRate',                    grid=True,                    style='*-',                    title='IBM Hazard Rates Curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Hazard Rate (%)')
Plt. Set_xlabel ('Date')

Plt = hazard_rates_df.Plot (x='Date',                    y='SurvivalProb',                    grid=True,                    style='*-',                    title='IBM Survival Probability Curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')

```

    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_167_1.png)

![png](CreditMarketSolutions_167_2.png)

## c. CDS valuation

```python
# CDS specs
Side = ql. Protection. Seller

Face_notional = 100

Contractual_spread = 100 / 10000

Cds_start_date = ql.Date (14,                    4,                    2023)
Cds_maturity_date = ql.Date (20,                    6,                    2028)

# Create CDS schedule
Cds_schedule = ql.MakeSchedule (cds_start_date,                    cds_maturity_date,                    ql.Period ('3 M'),                   
                            Ql. Quarterly,                    ql.TARGET (),                    ql. Following,                    ql. Unadjusted,                    ql. DateGeneration. TwentiethIMM)

# Create CDS object
Cds_obj = ql.CreditDefaultSwap (side,                    face_notional,                    contractual_spread,                    cds_schedule,                    ql. Following,                    ql. Actual 360 ())

# Create CDS Implied Credit Curve and pricing engine
Cds_surv_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)

Cds_pricing_engine = ql.MidPointCdsEngine (cds_surv_prob_curve_handle,                    CDS_recovery_rate,                    sofr_yield_curve_handle)
Cds_obj.SetPricingEngine (cds_pricing_engine)
# Print CDS valuation results
Print ('CDS protection start date: ',                    cds_obj.ProtectionStartDate ())
Print ('CDS fair/par spread: ',                    round (cds_obj.FairSpread ()*10000,                    3))
Print ('CDS PV: ',                    round (cds_obj.NPV (),                    4))    
Print ('CDS Premium Leg PV: ',                    round (cds_obj.CouponLegNPV (),                    4))
Print ('CDS Default Leg PV',                    round (cds_obj.DefaultLegNPV (),                    4))
Print ('Survival Prob. To Maturity: ',                    round (hazard_rate_curve.SurvivalProbability (cds_maturity_date),                    4))

```

    CDS protection start date: April 14 th,                    2023
    CDS fair/par spread: 55.502
    CDS PV: 2.0855
    CDS Premium Leg PV: 4.6868
    CDS Default Leg PV -2.6013
    Survival Prob. To Maturity: 0.9512

# 3. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)
## a. Create Corporate Bond

```python
Issue_date = ql.Date (14,                    4,                    2023)
Maturity_date = ql.Date (14,                    4,                    2027)
Coupon_freq = ql. Semiannual
Coupon_term = ql.Period (coupon_freq)
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Day_count_conv = ql. Unadjusted
Date_generation = ql. DateGeneration. Backward
Month_end = True
Schedule = ql.Schedule (issue_date,                   
                       Maturity_date,                   
                       Coupon_term,                   
                       Calendar,                   
                       Day_count_conv,                   
                       Day_count_conv,                   
                       Date_generation,                   
                       Month_end)

# Corp Bonds specs
Day_count = ql. Thirty 360 (ql. Thirty 360. USA)
Settlement_days = 2
Coupon_rate = 0.04
Coupons = [coupon_rate]
Payment_convention = ql. Unadjusted

# Construct the FixedRateBond
Face_value = 100
Fixed_rate_bond = ql.FixedRateBond (
    Settlement_days,                   
    Face_value,                   
    Schedule,                   
    Coupons,                   
    Day_count,                   
    Payment_convention)

X = [(cf.Date (),                    cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date,                    cf_amount = zip (*x)
Cf_frame = pd.DataFrame (data={'CashFlowDate': cf_date,                    'CashFlowAmount': cf_amount})
Print (cf_frame)

```

             CashFlowDate  CashFlowAmount
    0  October 14 th,                    2023             2.0
    1    April 14 th,                    2024             2.0
    2  October 14 th,                    2024             2.0
    3    April 14 th,                    2025             2.0
    4  October 14 th,                    2025             2.0
    5    April 14 th,                    2026             2.0
    6  October 14 th,                    2026             2.0
    7    April 14 th,                    2027             2.0
    8    April 14 th,                    2027           100.0

## b. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)

```python
Compounding = ql. Compounded
# Compounding = ql. Continuous

Day_counter = fixed_rate_bond.DayCounter ()

Risk_free_bond_engine = ql.DiscountingBondEngine (sofr_yield_curve_handle)

Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
Risk_free_bond_price = fixed_rate_bond.CleanPrice ()
Risk_free_bond_yield = fixed_rate_bond.BondYield (risk_free_bond_price,                    day_counter,                    ql. Compounded,                    ql. Semiannual) * 100

Print ('risk_free_bond_price: ',                    risk_free_bond_price)
Print ('risk_free_bond_yield: ',                    risk_free_bond_yield)

```

    Risk_free_bond_price: 101.54536292727957
    Risk_free_bond_yield: 3.5807016439305466

## c. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Cds_curve_risky_bond_engine: using calibrated IBM CDS curve
Cds_curve_risky_bond_engine = ql.RiskyBondEngine (cds_surv_prob_curve_handle,                    bond_recovery_rate,                    sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (cds_curve_risky_bond_engine)

# 3. Calculate intrinsic risky bond on custom survival probability curve
Risky_bond_price = fixed_rate_bond.CleanPrice ()
Risky_bond_yield = fixed_rate_bond.BondYield (risky_bond_price,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100

Print ('risky_bond_price: ',                    risky_bond_price)
Print ('risky_bond_yield: ',                    risky_bond_yield)

# Compute the credit I-Spread,                    relative to risk-free bond (SOFR curve)
Risky_bond_credit_ispread_bps = (risky_bond_yield - risk_free_bond_yield) * 100
Print ('risky_bond_ispread_bps: ',                    risky_bond_credit_ispread_bps)

# Calc z-spread
Risky_bond_zspread_bps = ql.BondFunctions.ZSpread (fixed_rate_bond,                    risky_bond_price,                    sofr_yield_curve,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 1 e 4
Print ('risky_bond_zspread_bps: ',                    risky_bond_zspread_bps)
```

    Risky_bond_price: 99.77353776497536
    Risky_bond_yield: 4.061950922012331
    Risky_bond_ispread_bps: 48.12492780817843
    Risky_bond_zspread_bps: 47.384353360489136

# 4. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)
## a. Create and Display the Custom Credit Curve

```python
# 2. Create custom survival probability curve
Custom_surv_prob_dates = [calc_date + ql.Period (T ,                    ql. Years) for T in range (11)]
Custom_average_hazard_rates = [0.0030,                    0.0060,                    0.0090,                    0.0110,                    0.0125,                    0.0140,                    0.0150,                    0.0160,                    0.0170,                    0.0180,                    0.0190]
Custom_surv_prob_levels = [np.Exp (-T * custom_average_hazard_rates[T]) for T in range (11)]
# Custom_surv_prob_levels = [1.0,                    0.9950,                    0.9860,                    0.9733,                    0.9569,                    0.9370,                    0.9166,                    0.8940,                    0.8728,                    0.8504,                    0.8269]

# Custom_surv_prob_curve
Custom_surv_prob_curve = ql.SurvivalProbabilityCurve (custom_surv_prob_dates,                    custom_surv_prob_levels,                    ql. Actual 360 (),                    ql.TARGET ())
Custom_surv_prob_curve.EnableExtrapolation ()
Custom_surv_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (custom_surv_prob_curve)

# 3. Display custom credit curve
Custom_surv_prob_df = pd.DataFrame (data={'Date': custom_surv_prob_dates,                   
                                          'Average Hazard Rates': custom_average_hazard_rates,                   
                                          'Survival Probs': custom_surv_prob_levels})

Plt = custom_surv_prob_df.Plot (x='Date',                    y='Average Hazard Rates',                    grid=True,                    style='*-',                    title='Custom Hazard Rate Curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Hazard Rate (%)')
Plt. Set_xlabel ('Date')

Plt = custom_surv_prob_df.Plot (x='Date',                    y='Survival Probs',                    grid=True,                    style='*-',                    title='Custom Survival Probability Curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')
```

    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_177_1.png)

![png](CreditMarketSolutions_177_2.png)

## b. Price Risky Bond on Custom Credit Curve (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Custom_curve_risky_bond_engine
Custom_curve_risky_bond_engine = ql.RiskyBondEngine (custom_surv_prob_curve_handle,                    bond_recovery_rate,                    sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (custom_curve_risky_bond_engine)

# 3. Price risky bond on custom survival probability curve
Risky_bond_price = fixed_rate_bond.CleanPrice ()
Risky_bond_yield = fixed_rate_bond.BondYield (risky_bond_price,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100

Print ('risky_bond_price: ',                    risky_bond_price)
Print ('risky_bond_yield: ',                    risky_bond_yield)

# Compute the credit I-Spread,                    relative to risk-free bond (SOFR curve)
Risky_bond_credit_ispread_bps = (risky_bond_yield - risk_free_bond_yield) * 100
Print ('risky_bond_ispread_bps: ',                    risky_bond_credit_ispread_bps)

# Calc z-spread
Risky_bond_zspread_bps = ql.BondFunctions.ZSpread (fixed_rate_bond,                    risky_bond_price,                    sofr_yield_curve,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 1 e 4
Print ('risky_bond_zspread_bps: ',                    risky_bond_zspread_bps)
```

    Risky_bond_price: 98.75601148481837
    Risky_bond_yield: 4.342892980575562
    Risky_bond_ispread_bps: 76.21913366450156
    Risky_bond_zspread_bps: 75.04528626811441

# 5. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions
## a. Nelson Siegel basis functions

```python
# Nelson_siegel curve shape: Nelson-Siegel
Def nelson_siegel (params,                    maturity):
    ''' params = (theta 1,                    theta 2,                    theta 3,                    lambda)'''    
    
    If (maturity > 0):
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
    Else:            
        Slope_1 = 1

    Curvature_1 = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature_1
    
    Return total_value

# Nelson_siegel_extended curve shape: Nelson-Siegel-Svensson
Def nelson_siegel_extended (params,                    maturity):

    If (maturity > 0):
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
    Else:            
        Slope_1 = 1

    Curvature_1 = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature_1    
    
    If (params[5] != 0):
        If (maturity > 0):
            Slope_2 = (1 - np.Exp (-maturity/params[5]))/(maturity/params[5])
        Else:
            Slope_2 = 1

        Curvature_2 = slope_2 - np.Exp (-maturity/params[5])

        Total_value = total_value + params[4] * curvature_2
    Return total_value

```

## b. Plot Basis Functions for Nelson-Siegel + extensions

```python

Curve_shapes_df = pd.DataFrame ([T,                    nelson_siegel ([1,                    0,                    0,                    2],                    T),                    
                                 Nelson_siegel ([0,                    1,                    0,                    2],                    T),                    
                                 Nelson_siegel ([0,                    0,                    2,                    2],                    T)] for T in range (0,                   30,                   1))
Curve_shapes_df. Columns = ['TTM',                    'Level',                    'Slope',                    'Curvature']

Curve_shapes_df 2 = pd.DataFrame ([T,                    nelson_siegel_extended ([1,                    0,                    0,                    2,                    0,                    0],                    T),                    
                                 Nelson_siegel_extended ([0,                    1,                    0,                    2,                    0,                    0],                    T),                    
                                 Nelson_siegel_extended ([0,                    0,                    2,                    2,                    0,                    0],                    T),                    
                                 Nelson_siegel_extended ([0,                    0,                    0,                    2,                    1,                    10],                    T)] for T in range (0,                   30,                   1))
Curve_shapes_df 2. Columns = ['TTM',                    'Level',                    'Slope',                    'Curvature_1',                    'Curvature_2']

Print (curve_shapes_df 2. Head ())

Plt = curve_shapes_df.Plot (x='TTM',                    y=['Level',                    'Slope',                    'Curvature'],                    grid=True,                    style='-',                    title='Nelson-Siegel basis functions',                    figsize=(12,                   5))
Plt. Set_ylabel ('Curve Level')
Plt. Set_xlabel ('Time to maturity (years)')

Plt = curve_shapes_df 2. Plot (x='TTM',                    y=['Level',                    'Slope',                    'Curvature_1',                    'Curvature_2'],                    grid=True,                    style='-',                    title='Nelson-Siegel-Svensson basis functions',                    figsize=(12,                   5))
Plt. Set_ylabel ('Curve Level')
Plt. Set_xlabel ('Time to maturity (years)')

```

       TTM  Level     Slope  Curvature_1  Curvature_2
    0    0    1.0  1.000000     0.000000     0.000000
    1    1    1.0  0.786939     0.360816     0.046788
    2    2    1.0  0.632121     0.528482     0.087615
    3    3    1.0  0.517913     0.589566     0.123121
    4    4    1.0  0.432332     0.593994     0.153880
    Text (0.5,                    0,                    'Time to maturity (years)')
![png](CreditMarketSolutions_183_2.png)

![png](CreditMarketSolutions_183_3.png)

## c. Constructing smooth Nelson-Siegel hazard rate / survival probability curves

```python
# Nelson_siegel_params = [theta 1,                    theta 2,                    theta 3,                    lambda] = [long term level,                    short - long slope,                    curvature,                    lambda]
Nelson_siegel_params = [0.0300,                    -0.0100,                    -0.0010,                    2]

Nelson_siegel_surv_prob_dates = [calc_date + ql.Period (T ,                    ql. Years) for T in range (31)]
Nelson_siegel_average_hazard_rates = [nelson_siegel (nelson_siegel_params,                    T) for T in range (31)]
Nelson_siegel_surv_prob_levels = [np.Exp (-T * nelson_siegel_average_hazard_rates[T]) for T in range (31)]

# Nelson_siegel_surv_prob_curve
Nelson_siegel_credit_curve = ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,                    nelson_siegel_surv_prob_levels,                    ql. Actual 360 (),                    ql.TARGET ())
Nelson_siegel_credit_curve.EnableExtrapolation ()
Nelson_siegel_credit_curve_handle = ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)

Nelson_siegel_surv_prob_df = pd.DataFrame (data={'Dates': nelson_siegel_surv_prob_dates,                   
                                          'Average Hazard Rates': nelson_siegel_average_hazard_rates,                   
                                          'Survival Probs': nelson_siegel_surv_prob_levels})
# Print (nelson_siegel_surv_prob_df)

Plt = nelson_siegel_surv_prob_df.Plot (x='Dates',                    y=['Average Hazard Rates'],                    grid=True,                    style='-',                    title='Nelson-Siegel smooth hazard rate curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Average hazard rate')
Plt. Set_xlabel ('Maturity')

Plt = nelson_siegel_surv_prob_df.Plot (x='Dates',                    y=['Survival Probs'],                    grid=True,                    style='-',                    title='Nelson-Siegel smooth survival probability curve',                    figsize=(12,                   5))
Plt. Set_ylabel ('Survival Prob')
Plt. Set_xlabel ('Maturity')
```

    Text (0.5,                    0,                    'Maturity')
![png](CreditMarketSolutions_185_1.png)

![png](CreditMarketSolutions_185_2.png)

## d. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Nelson_siegel_risky_bond_engine
Nelson_siegel_risky_bond_engine = ql.RiskyBondEngine (nelson_siegel_credit_curve_handle,                    bond_recovery_rate,                    sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)

# Price risky bond using Nelson-Siegel survival probability curve
Nelson_siegel_risky_bond_price = fixed_rate_bond.CleanPrice ()
Nelson_siegel_risky_bond_yield = fixed_rate_bond.BondYield (nelson_siegel_risky_bond_price,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100

Print ('nelson_siegel_surv_prob_risky_bond_price: ',                    nelson_siegel_risky_bond_price)
Print ('nelson_siegel_surv_prob_risky_bond_yield: ',                    nelson_siegel_risky_bond_yield)

# Compute the credit I-Spread (relative to risk-free SOFR bond)
Nelson_siegel_risky_bond_credit_ispread = (nelson_siegel_risky_bond_yield - risk_free_bond_yield) * 1 e 2
Print ('nelson_siegel_risky_bond_ispread: ',                    nelson_siegel_risky_bond_credit_ispread)

# Compute z-spread
Nelson_siegel_risky_bond_zspread = ql.BondFunctions.ZSpread (fixed_rate_bond,                    nelson_siegel_risky_bond_price,                    sofr_yield_curve,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 1 e 4
Print ('nelson_siegel_risky_bond_zspread: ',                    nelson_siegel_risky_bond_zspread)
```

    Nelson_siegel_surv_prob_risky_bond_price: 95.95463373300109
    Nelson_siegel_surv_prob_risky_bond_yield: 5.134316444396973
    Nelson_siegel_risky_bond_ispread: 155.3614800466426
    Nelson_siegel_risky_bond_zspread: 152.96353195435728

<hr><font color="green"><h1>from file: 5 FINM_35700_CreditMarkets_Spring 2024_Solution_3</h1></font>

# Homework 3

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

### Due Date: 2024-04-23

- Alex Popovici
- alex.popovici@uchicago.edu

This homework relies on:

- The SOFR Is symbology file `sofr_swap_symbology`,
- The SOFR swaps market data file `sofr_swaps_market_data_eod` and
- The CDS spreads market data file `cds_market_data_eod`.

-----------------------------------------------------------
# Problem 1: Risk & Scenario analysis for a fixed rate corporate bond (yield model)
## Use the QuantLib Basic notebook (or previous homeworks) as templates

```python
Import QuantLib as ql
Import numpy as np
Import pandas as pd
Import datetime as dt

Def get_ql_date (date) -> ql. Date:
    """
    Convert dt. Date to ql. Date
    """
    If isinstance (date,                    dt. Date):
        Return ql.Date (date. Day,                    date. Month,                    date. Year)
    Elif isinstance (date,                    str):
        Date = dt.Datetime.Strptime (date,                    "%Y-%m-%d"). Date ()
        Return ql.Date (date. Day,                    date. Month,                    date. Year)
    Else:
        Raise ValueError (f"to_qldate,                    {type (date)},                    {date}")
    
Def create_schedule_from_symbology (details: dict):
    '''Create a QuantLib cashflow schedule from symbology details dictionary (usually one row of the symbology dataframe)
    '''
    
    # Create maturity from details['maturity']
    Maturity = get_ql_date (details['maturity'])
    
    # Create acc_first from details['acc_first']
    Acc_first =  get_ql_date (details['acc_first'])
    
    # Create calendar for Corp and Govt asset classes
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    # define period from details['cpn_freq'] ... Can be hard-coded to 2 = semi-annual frequency
    Period = ql.Period (2)
    
    # business_day_convention
    Business_day_convention = ql. Unadjusted
    
    # termination_date_convention
    Termination_date_convention = ql. Unadjusted
    
    # date_generation
    Date_generation=ql. DateGeneration. Backward
    
    # Create schedule using ql. MakeSchedule interface (with keyword arguments)
    Schedule = ql.MakeSchedule (effectiveDate=acc_first,                     # this may not be the same as the bond's start date
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
        Raise ValueError (f"unsupported asset class,                    {type (details['class'])},                    {details['class']}")
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

Def get_bond_cashflows (bond: ql. FixedRateBond,                    calc_date=ql. Date) -> pd. DataFrame:
    '''Returns all future cashflows as of calc_date,                    i.e. with payment dates > calc_date.
    '''    
    Day_counter = bond.DayCounter ()    
    
    X = [(cf.Date (),                    day_counter.YearFraction (calc_date,                    cf.Date ()),                    cf.Amount ()) for cf in bond.Cashflows ()]
    Cf_date,                    cf_yearFrac,                    cf_amount = zip (*x)
    Cashflows_df = pd.DataFrame (data={'CashFlowDate': cf_date,                    'CashFlowYearFrac': cf_yearFrac,                    'CashFlowAmount': cf_amount})

    # filter for payment dates > calc_date
    Cashflows_df = cashflows_df[cashflows_df. CashFlowYearFrac > 0]
    Return cashflows_df
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
    
    For index,                    row in sorted_details_frame.Iterrows ():
        Bond_object = create_bond_from_symbology (row)
        
        Tsy_clean_price_quote = row[price_quote_column]
        Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
        
        Bond_helper = ql.BondHelper (tsy_clean_price_handle,                    bond_object)
        Bond_helpers.Append (bond_helper)
        
    Yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,                    bond_helpers,                    day_count)
    # yield_curve = ql.PiecewiseFlatForward (calc_date,                    bond_helpers,                    day_count)
    
    Yield_curve.EnableExtrapolation ()
    Return yield_curve
Def get_yield_curve_details_df (yield_curve,                    curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),                    3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),                    3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,                    yield_curve.DayCounter (),                    ql. Compounded). Rate () * 100,                    3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,                   
                             'YearFrac': yearfracs,                   
                             'DiscountFactor': discounts,                   
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
Def calc_clean_price_with_zspread (fixed_rate_bond,                    yield_curve_handle,                    zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,                    zspread_quote_handle,                    ql. Compounded,                    ql. Semiannual)
    Yield_curve_bumped_handle = ql.YieldTermStructureHandle (yield_curve_bumped)
    
    # Set Valuation engine
    Bond_engine = ql.DiscountingBondEngine (yield_curve_bumped_handle)
    Fixed_rate_bond.SetPricingEngine (bond_engine)
    Bond_clean_price = fixed_rate_bond.CleanPrice ()
    Return bond_clean_price
Def calibrate_sofr_curve_from_frame (
        Calc_date: ql. Date,                   
        Sofr_details: pd. DataFrame,                   
        Rate_quote_column: str):
    '''Create a calibrated yield curve from a SOFR details dataframe which includes rate quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = sofr_details. Sort_values (by='tenor')    
    
    # settle_days
    Settle_days = 2
    
    # For US SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swaps 
    Day_count = ql. Actual 360 ()

    # For US SOFR Swaps     
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    Sofr_helpers = []
    
    For index,                    row in sorted_details_frame.Iterrows ():
        Sofr_quote = row[rate_quote_column]
        Tenor_in_years = row['tenor']
        Sofr_tenor = ql.Period (tenor_in_years,                    ql. Years)
        
        # create sofr_rate_helper
        Sofr_helper = ql.OISRateHelper (settle_days,                    sofr_tenor,                    ql.QuoteHandle (ql.SimpleQuote (sofr_quote/100)),                    ql.Sofr ())
                        
        Sofr_helpers.Append (sofr_helper)
        
    Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,                    calendar,                    sofr_helpers,                    day_count)
    Sofr_yield_curve.EnableExtrapolation ()
    
    Return sofr_yield_curve
Def calibrate_cds_hazard_rate_curve (calc_date,                    sofr_yield_curve_handle,                    cds_par_spreads_bps,                    cds_recovery_rate = 0.4):
    '''Calibrate hazard rate curve from CDS Par Spreads'''
    CDS_settle_days = 2

    CDS_day_count = ql. Actual 360 ()

    # CDS standard tenors: 1 Y,                    2 Y,                    3 Y,                    5 Y 7 Y and 10 Y
    CDS_tenors = [ql.Period (y,                    ql. Years) for y in [1,                    2,                    3,                    5,                    7,                    10]]
    CDS_helpers = [ql.SpreadCdsHelper ((cds_par_spread / 10000.0),                    CDS_tenor,                    CDS_settle_days,                    ql.TARGET (),                   
                                  Ql. Quarterly,                    ql. Following,                    ql. DateGeneration. TwentiethIMM,                    CDS_day_count,                    cds_recovery_rate,                    sofr_yield_curve_handle)
               
    For (cds_par_spread,                    CDS_tenor) in zip (cds_par_spreads_bps,                    CDS_tenors)]

    # bootstrap hazard_rate_curve
    Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,                    CDS_helpers,                    CDS_day_count)
    Hazard_rate_curve.EnableExtrapolation ()

    Return (hazard_rate_curve)
Def get_hazard_rates_df (hazard_rate_curve):
    '''Return dataframe with calibrated hazard rates and survival probabilities'''
    
    CDS_day_count = ql. Actual 360 ()
    
    Hazard_list = [(hr[0]. To_date (),                    
                CDS_day_count.YearFraction (calc_date,                    hr[0]),                   
                Hr[1] * 1 e 4,                   
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

    Grid_dates,                    year_frac,                    hazard_rates,                    surv_probs = zip (*hazard_list)

    Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,                    
                                     'YearFrac': year_frac,                   
                                     'HazardRateBps': hazard_rates,                                                        
                                     'SurvivalProb': surv_probs})
    Return (hazard_rates_df)
```

## a. Create generic fixed-rate corporate bond

Fix the calculation date as of April 15 2024 and use a coupon of 5% and a maturity of 10 years (April 15 2034).

Display the fixed rate bond cashflows.

```python
# Import tools from previous homeworks
# Use static calculation/valuation date of 2024-04-15,                    matching data available in the market prices EOD file
Calc_date = ql.Date (15,                    4,                    2024)
Ql.Settings.Instance (). EvaluationDate = calc_date
```

    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    Cell In[99],                    line 2
          1 # import tools from previous homeworks
    ----> 2 from credit_market_tools import *
          4 # Use static calculation/valuation date of 2024-04-15,                    matching data available in the market prices EOD file
          5 calc_date = ql.Date (15,                    4,                    2024)
    ModuleNotFoundError: No module named 'credit_market_tools'

```python
# Bond_details
Test_bond_details = {'class': 'Corp',                   
                'start_date': '2024-04-15',                    
                'acc_first': '2024-04-15',                    
                'maturity': '2034-04-15',                    
                'coupon': 5,                   
                'dcc' : '30/360',                   
                'days_settle' : 2}

# Use create_bond_from_symbology () to create the bond
Test_fixed_rate_bond = create_bond_from_symbology (test_bond_details)

Test_fixed_rate_bond_cashflows_df = get_bond_cashflows (test_fixed_rate_bond,                    calc_date)
Print (test_fixed_rate_bond_cashflows_df)
```

              CashFlowDate  CashFlowYearFrac  CashFlowAmount
    0   October 15 th,                    2024          0.508333             2.5
    1     April 15 th,                    2025          1.008333             2.5
    2   October 15 th,                    2025          1.508333             2.5
    3     April 15 th,                    2026          2.008333             2.5
    4   October 15 th,                    2026          2.508333             2.5
    5     April 15 th,                    2027          3.008333             2.5
    6   October 15 th,                    2027          3.508333             2.5
    7     April 15 th,                    2028          4.008333             2.5
    8   October 15 th,                    2028          4.508333             2.5
    9     April 15 th,                    2029          5.008333             2.5
    10  October 15 th,                    2029          5.508333             2.5
    11    April 15 th,                    2030          6.008333             2.5
    12  October 15 th,                    2030          6.508333             2.5
    13    April 15 th,                    2031          7.008333             2.5
    14  October 15 th,                    2031          7.508333             2.5
    15    April 15 th,                    2032          8.008333             2.5
    16  October 15 th,                    2032          8.508333             2.5
    17    April 15 th,                    2033          9.008333             2.5
    18  October 15 th,                    2033          9.508333             2.5
    19    April 15 th,                    2034         10.008333             2.5
    20    April 15 th,                    2034         10.008333           100.0

## b. Compute the bond price,  DV 01,  duration and convexity (analytic method)

Assume that the market yield of the bond is 6%. Compute the bond price,  DV 01,  duration and convexity,  using the analytic method.

```python
# Test_bond_yield of 6%
Test_bond_yield = 6

# Test_bond_clean_price
Test_bond_clean_price = test_fixed_rate_bond.CleanPrice (test_bond_yield/100,                    test_fixed_rate_bond.DayCounter (),                    ql. Compounded,                    ql. Semiannual)
Test_bond_dirty_price = test_fixed_rate_bond.DirtyPrice (test_bond_yield/100,                    test_fixed_rate_bond.DayCounter (),                    ql. Compounded,                    ql. Semiannual)

# Compute analytical dv 01,                    duration and convexity
Test_bond_yield_rate = ql.InterestRate (test_bond_yield/100,                    test_fixed_rate_bond.DayCounter (),                    ql. Compounded,                    ql. Semiannual)
Test_bond_duration = ql.BondFunctions.Duration (test_fixed_rate_bond,                    test_bond_yield_rate)
Test_bond_convexity = ql.BondFunctions.Convexity (test_fixed_rate_bond,                    test_bond_yield_rate)
Test_bond_dv 01 = test_bond_duration * test_bond_dirty_price / 100

Print ('test_bond_clean_price: ',                    round (test_bond_clean_price,                    2))
Print ('test_bond_dirty_price: ',                    round (test_bond_dirty_price,                    2))
Print ('test_bond_dv 01: ',                    round (test_bond_dv 01,                    2))
Print ('test_bond_duration: ',                    round (test_bond_duration,                    2))
Print ('test_bond_convexity: ',                    round (test_bond_convexity,                    2))
```

    Test_bond_clean_price: 92.56
    Test_bond_dirty_price: 92.58
    Test_bond_dv 01: 7.09
    Test_bond_duration: 7.66
    Test_bond_convexity: 71.74

## c. Scenario bond prices: "re-pricing" vs "second-order approximations"

Compute the scenario bond prices on the following scenario yield grid: [from 1% to 11% in steps of 0.5%]

Compute the second-order scenario price approximations using duration and convexity sensitivities (formula 13 from Lecture 1).

Plot the scenario prices (Y-axis) vs yieds (X-axis),  for both the "re-pricing" and "second-order approximations" method.

Here we are using formula [13] from Lecture 1,  which gives us the second-order price approximation via duration/convexity (second order Taylor expansion in yield parameter).

$$\begin{align}
\Delta B (y) = B\left (y+\Delta y\right)-B\left (y\right)\approx B\cdot\left[- D\cdot\Delta y+\frac{1}{2}\cdot\Gamma\cdot\left (\Delta y\right)^{2}\right]
\end{align}$$

We implement formula [13] into the `calc_second_order_price_change (...)` function,                    taking into account that $B (y)$ is the dirty bond price.
```python
Def calc_second_order_price_change (dirty_price,                    yield_diff,                    duration,                    convexity):
    Return dirty_price * (- yield_diff * duration + 0.5 * yield_diff*yield_diff*convexity)

# Bond_yield_grid : yield grid [from 1% to 11% in steps of 0.5%]    
Bond_yield_grid = [y for y in np.Arange (1,                    11.5,                    0.5)]

# Scenario_prices
Scenario_prices = [round (test_fixed_rate_bond.CleanPrice (y/100,                    test_fixed_rate_bond.DayCounter (),                    ql. Compounded,                    ql. Semiannual),                    3) for y in bond_yield_grid]

# Second_order_approx_prices
Second_order_approx_prices = [round (test_bond_clean_price + calc_second_order_price_change (test_bond_dirty_price,                    (y - test_bond_yield) / 100,                    test_bond_duration,                    test_bond_convexity),                    2) 
                                   For y in bond_yield_grid]

# Plot bond_scennarios_df
Bond_scenarios_df = pd.DataFrame (data={'ScenYields': bond_yield_grid,                    'ScenPrices': scenario_prices,                    'ApproxPrices': second_order_approx_prices})
Print (bond_scenarios_df.Round (1))

# Plot Scenario Prices for "analytic re-pricing" vs "second-order approximations
Plt = bond_scenarios_df.Plot (x='ScenYields',                    y=['ScenPrices',                    'ApproxPrices'],                    grid=True,                    style='-*',                    title='Scenario Prices for "analytic re-pricing" vs "second-order approximations"',                    figsize=(12,                   4))
Plt.Axhline (test_bond_clean_price,                    color='red',                    linestyle='--',                    alpha=0.7)
Plt. Set_ylabel ('Scenario Price')
Plt. Set_xlabel ('Yield')

```

        ScenYields  ScenPrices  ApproxPrices
    0          1.0       138.0         136.3
    1          1.5       132.4         131.2
    2          2.0       127.1         126.2
    3          2.5       122.0         121.5
    4          3.0       117.2         116.8
    5          3.5       112.6         112.4
    6          4.0       108.2         108.1
    7          4.5       104.0         104.0
    8          5.0       100.0         100.0
    9          5.5        96.2          96.2
    10         6.0        92.6          92.6
    11         6.5        89.1          89.1
    12         7.0        85.8          85.8
    13         7.5        82.6          82.7
    14         8.0        79.6          79.7
    15         8.5        76.7          76.9
    16         9.0        74.0          74.3
    17         9.5        71.4          71.8
    18        10.0        68.8          69.5
    19        10.5        66.4          67.4
    20        11.0        64.2          65.4
    Text (0.5,                    0,                    'Yield')
![png](CreditMarketSolutions_200_2.png)
## d. Extreme events scenarios

Compute and show the scenario bond price for a bond yield of 15% (extreme event scenario).

Compute and show the second-order scenario price approximation in the extreme event scenario.

How accurate is the second-order scenario price approximations (using duration and convexity sensitivities)?

Compute and show the analytic DV 01,                    duration and convexity in the extreme event scenario.
```python
Extreme_event_bond_yield = 15
Extreme_event_bond_clean_price = round (test_fixed_rate_bond.CleanPrice (extreme_event_bond_yield/100,                    test_fixed_rate_bond.DayCounter (),                    ql. Compounded,                    ql. Semiannual),                    3)
Extreme_event_second_order_approx_price = round (test_bond_clean_price + calc_second_order_price_change (test_bond_dirty_price,                    (extreme_event_bond_yield - test_bond_yield) / 100,                    test_bond_duration,                    test_bond_convexity),                    2) 
                             
Print ('extreme_event_scenario_price: ',                    extreme_event_bond_clean_price)
Print ('extreme_event_approx_price: ',                    extreme_event_second_order_approx_price)
Print ('extreme_event_approx_error: ',                    round (extreme_event_second_order_approx_price - extreme_event_bond_clean_price,                    2))                             
```

    Extreme_event_scenario_price: 49.033
    Extreme_event_approx_price: 55.62
    Extreme_event_approx_error: 6.59
-----------------------------------------------------------
# Problem 2: Perpetual bonds
## a. Price a fixed rate perpetual bond
We are interested in a fixed rate perpetual bond (infinite maturity) on a face notional of $100 and semi-annual coupon c.

Assuming that the bond has a (continuously componded) yield of y,                    what is the fair value price of the bond?

For simplicity,                    you can assume T+0 settlement and zero accrued. 

You can use following sympy code (implementing Formula 5 from Session 1) as a starting point.
```python
# Import libraries
Import sympy as sp

# Define fixed rate bond specs as symbolic variables
T = sp.Symbols ('T')
C = sp.Symbols ('c')
Y = sp.Symbols ('y')

# Define symbolic equation for generic fixed rate bond pv
Bond_pv_eq =  1 + (c/2  / (sp.Exp (y/2) - 1) - 1 )* (1 - sp.Exp (-T*y))
Print ('Analytic formula for bond_pv: ',                    bond_pv_eq)
Display (bond_pv_eq)
```

    Analytic formula for bond_pv: (1 - exp (-T*y))*(c/(2*(exp (y/2) - 1)) - 1) + 1
$\displaystyle \left (1 - e^{- T y}\right) \left (\frac{c}{2 \left (e^{\frac{y}{2}} - 1\right)} - 1\right) + 1$
We start with the formula for pricing a risky fixed rate bond on a face of 100%,                    derived in Lecture 1,                    formulas [4] and [5].

$$\begin{align}
B_{0}^{T}=B (0,                    c,                    T,                    y)=\sum_{k=1}^{2 T}\frac{c}{2}\cdot e^{-k\cdot\frac{y}{2}}+e^{-T\cdot y}
\end{align}$$

$$\begin{align}
=1+\frac{\frac{c}{2}-\left (e^{\frac{y}{2}}-1\right)}{e^{\frac{y}{2}}-1}\cdot\left (1-e^{-T\cdot y}\right)
\end{align}$$

$$\begin{align}
=1+\frac{c-y_{sa}}{y_{sa}}\cdot\left[1-\left (1+\frac{y_{sa}}{2}\right)^{-2 T}\right]
\end{align}$$

Remember that the the semi-annual yield is given by:  $y_{sa} = 2 \cdot \left (e^{\frac{y}{2}}-1 \right)$.

In the case of the fixed rate perpetual bond,                    the bond maturity and cashflows extend to "infinity",                    so the pricing formula simplifies in terms of $y_{sa}$ to

$$\begin{align}
B_{0}^{\infty}=B (0,                    c,                   \infty,                    y)=\sum_{k=1}^{\infty}\frac{c}{2}\cdot e^{-k\cdot\frac{y}{2}} =  \frac{c}{2 \cdot \left (e^{\frac{y}{2}}-1 \right)}=\frac{c}{y_{sa}},                   
\end{align}$$
To obtain the fair price on a face of $100,                    one has to multiply the formula above by 100:
$$\begin{align}
B_{0}^{\infty}(100) =  \frac{100 \cdot c}{2 \cdot \left (e^{\frac{y}{2}}-1 \right)} = 100 \cdot \frac{c}{y_{sa}},                   
\end{align}$$
## b. Perpetual bonds priced "at par"
For which yield y does the bond trade "at par",                    i.e. fair value price = $100?

$$\begin{align}
B_{0}^{\infty}(100)=100 \iff y=2\cdot \ln \left ( 1 + \frac{c}{2} \right) \iff y_{sa} = c.
\end{align}$$
Hence,                    the perpetual bond trades "at par" if the smi-annual yield $y_{sa}$ matches the semi-annual coupon c (same result as for "regular" fixed rate bonds).

## c. Duration and DV 01 for a fixed rate perpetual bond
Compute Duration and DV 01 of the perpetual bond.
```python
# Define symbolic equations
Perpetual_bond_price = c / (sp.Exp (y/2) - 1) / 2
Print ('1. Perpetual bond price (with coupon c): ')
Display (perpetual_bond_price)

# Find first and second order derivatives
First_order_derivative = perpetual_bond_price.Diff (y)
Print ('2. Perpetual bond DV 01: ')
Display (-first_order_derivative)

Perpetual_bond_duration =  sp.Simplify (- first_order_derivative / perpetual_bond_price)
Print ('3. Perpetual bond duration: ')
Display (perpetual_bond_duration)
```

    1. Perpetual bond price (with coupon c):
$\displaystyle \frac{c}{2 \left (e^{\frac{y}{2}} - 1\right)}$
    2. Perpetual bond DV 01:
$\displaystyle \frac{c e^{\frac{y}{2}}}{4 \left (e^{\frac{y}{2}} - 1\right)^{2}}$
    3. Perpetual bond duration:
$\displaystyle \frac{e^{\frac{y}{2}}}{2 e^{\frac{y}{2}} - 2}$
Hence,                    PV 01 and duration of a fixed rate perpetual bond are given by

$$\begin{align}
PV 01 = -\frac{\partial B}{\partial y} = -\frac{\partial}{\partial y}\left[\frac{c}{2 \cdot \left ( e^{\frac{y}{2}}-1 \right) }\right]=\frac{c \cdot e^{\frac{y}{2}}}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} = \frac{c \cdot \left ( 1 + \frac{y_{sa}}{2} \right) }{y_{sa}^2}
\end{align}$$
$$\begin{align}
D = -\frac{1}{B} \cdot \frac{\partial B}{\partial y} = \frac{e^{\frac{y}{2}}}{2 \cdot \left ( e^{\frac{y}{2}} - 1 \right)} = \frac{1 + \frac{y_{sa}}{2} }{y_{sa}}.
\end{align}$$
## d. Convexity of a fixed rate perpetual bond
Compute the convexity of the perpetual bond.
```python
Second_order_derivative = sp.Simplify (first_order_derivative.Diff (y))
Print ('Second order derivative: ')
Display (second_order_derivative)

Perpetual_bond_convexity =  sp.Simplify (second_order_derivative / perpetual_bond_price)
Print ('Perpetual bond convexity: ')
Display (perpetual_bond_convexity)

```

    Second order derivative:
$\displaystyle - \frac{c \left (\left (e^{\frac{y}{2}} - 1\right) e^{\frac{y}{2}} - 2 e^{y}\right)}{8 \left (e^{\frac{y}{2}} - 1\right)^{3}}$
    Perpetual bond convexity:
$\displaystyle \frac{\left (1 + e^{- \frac{y}{2}}\right) e^{y}}{4 \left (- 2 e^{\frac{y}{2}} + e^{y} + 1\right)}$
Hence,                    second order derivative and convexity $\Gamma$ of the fixed rate perpetual bond are given by

$$\begin{align}
\frac{\partial^{2} B}{\partial y^{2}} = \frac{\partial^{2}}{\partial y^{2}}\left[\frac{\frac{c}{2}}{e^{\frac{y}{2}}-1}\right] = \frac{\partial}{\partial y}\left[\frac{c \cdot e^{\frac{y}{2}}}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} \right] = \frac{c \cdot e^{\frac{y}{2}} \cdot \left (e^{\frac{y}{2}} + 1 \right)}{8 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^3}  = \frac{c \cdot \left ( 1 + \frac{y_{sa}}{2} \right) \cdot \left ( 2 + \frac{y_{sa}}{2} \right)}{y_{sa}^3}
\end{align}$$

$$\begin{align}
\Gamma = \frac{1}{B} \cdot \frac{\partial^{2} B}{\partial y^{2}} = \frac{e^{\frac{y}{2}} \cdot \left (e^{\frac{y}{2}} + 1 \right)}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} =  \frac{\left ( 1 + \frac{y_{sa}}{2} \right) \cdot \left ( 2 + \frac{y_{sa}}{2} \right)}{y_{sa}^2}. 
\end{align}$$
-----------------------------------------------------------
# Problem 3: US SOFR swap curve calibration as of 2024-04-15
### Follow Section "1. SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap rates and SOFR discount curve calibration + validation" in the QuantLib Advanced notebook !

## a. Load and explore US SOFR swaps symbology and market data

Load the `sofr_swap_symbology` Excel file into a dataframe. Print all swap tenors available.

Load the `sofr_swaps_market_data_eod` Excel file into a dataframe. Print all dates available.

Plot the historial time series of SOFR rates for the available [1 Y,                    2 Y,                    3 Y,                    5 Y,                    7 Y,                    10 Y,                    20 Y,                    30 Y] tenors.
```python
# Sofr_symbology
Sofr_symbology = pd. Read_excel ('./data/sofr_swaps_symbology. Xlsx')
Sofr_symbology. Set_index ('figi',                    inplace=True)
Display (sofr_symbology)

# Sofr_market_quotes
Sofr_market_quotes = pd. Read_excel ('./data/sofr_swaps_market_data_eod. Xlsx')
# Print (sofr_market_quotes.Head ())

# Pivot to get SOFR rates time series
Sofr_quotes_ts = sofr_market_quotes.Pivot (index="date",                    columns="figi",                    values="midRate")
Sofr_quotes_ts. Columns = sofr_symbology. Tenor[sofr_quotes_ts. Columns]
# Print (sofr_quotes_ts.Head ())

Plt = sofr_quotes_ts.Plot (grid=True,                    style='-',                    title='SOFR Swaps: historical time series',                    figsize=(12,                   8))
Plt. Set_ylabel ('SOFR Rate')
Plt. Set_xlabel ('Date')
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 10 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 20 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 30 Y</td>
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
    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_216_2.png)
## b. Calibrate the US SOFR yield curve (via bootstrapping)
The function below shows how to calibrate a smooth yield/discount factor curve from SOFR swaps. 

Prepare a joint symbology & market dataframe quotes as of 2024-04-15. 

Calibrate the SOFR discount factor curve as of 2024-04-15.

Follow section 1 b in the QuantLib Advanced notebook.
```python
Def calibrate_sofr_curve_from_frame (
        Calc_date: ql. Date,                   
        Sofr_details: pd. DataFrame,                   
        Rate_quote_column: str):
    '''Create a calibrated yield curve from a SOFR details dataframe which includes rate quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = sofr_details. Sort_values (by='tenor')    
    
    # settle_days
    Settle_days = 2
    
    # For US SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swaps 
    Day_count = ql. Actual 360 ()

    # For US SOFR Swaps     
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    Sofr_helpers = []
    
    For index,                    row in sorted_details_frame.Iterrows ():
        Sofr_quote = row[rate_quote_column]
        Tenor_in_years = row['tenor']
        Sofr_tenor = ql.Period (tenor_in_years,                    ql. Years)
        
        # create sofr_rate_helper
        Sofr_helper = ql.OISRateHelper (settle_days,                    sofr_tenor,                    ql.QuoteHandle (ql.SimpleQuote (sofr_quote/100)),                    ql.Sofr ())
                        
        Sofr_helpers.Append (sofr_helper)
        
    Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,                    calendar,                    sofr_helpers,                    day_count)
    Sofr_yield_curve.EnableExtrapolation ()
    
    Return sofr_yield_curve
```
```python
# Sofr_combined
Sofr_combined = sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes['date'] == '2024-04-15'],                    how='left',                    on=['figi'])
Display (sofr_combined.Head ())

# Calibrate SOFR discount curve
Sofr_yield_curve = calibrate_sofr_curve_from_frame (calc_date,                    sofr_combined,                    'midRate')
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
      <td>1</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>5.1753</td>
      <td>5.1831</td>
      <td>5.1792</td>
    </tr>
    <tr>
      <th>1</th>
      <td>BBG 00 KFWPJX 3</td>
      <td>USOSFR 2</td>
      <td>Curncy</td>
      <td>USOSFR 2 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
      <td>2</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.8155</td>
      <td>4.8225</td>
      <td>4.8190</td>
    </tr>
    <tr>
      <th>2</th>
      <td>BBG 00 KFWPK 15</td>
      <td>USOSFR 3</td>
      <td>Curncy</td>
      <td>USOSFR 3 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
      <td>3</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.5742</td>
      <td>4.5818</td>
      <td>4.5780</td>
    </tr>
    <tr>
      <th>3</th>
      <td>BBG 00 KFWPK 51</td>
      <td>USOSFR 5</td>
      <td>Curncy</td>
      <td>USOSFR 5 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
      <td>5</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.3085</td>
      <td>4.3143</td>
      <td>4.3114</td>
    </tr>
    <tr>
      <th>4</th>
      <td>BBG 00 KFWPK 79</td>
      <td>USOSFR 7</td>
      <td>Curncy</td>
      <td>USOSFR 7 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
      <td>7</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.2025</td>
      <td>4.2085</td>
      <td>4.2055</td>
    </tr>
  </tbody>
</table>
</div>
## c. Display the calibrated SOFR discount curve dataframe

Follow section 1 d (in the QuantLib Advanced notebook) to display the calibration details dataframe.
```python
# Display and plot SOFR yield curve
Grid_dates = [sofr_yield_curve.ReferenceDate () + ql.Period (y,                    ql. Years) for y in list (range (0,                   30,                   1))]
Sofr_yield_curve_simple_df = get_yield_curve_details_df (sofr_yield_curve)                  # using calibration grid
Sofr_yield_curve_details_df = get_yield_curve_details_df (sofr_yield_curve,                    grid_dates)    # using external grid

Display (sofr_yield_curve_simple_df)
Display (sofr_yield_curve_details_df)
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
      <td>2024-04-16</td>
      <td>0.000</td>
      <td>1.000</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2025-04-16</td>
      <td>1.014</td>
      <td>0.950</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2026-04-16</td>
      <td>2.028</td>
      <td>0.909</td>
      <td>4.809</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2027-04-16</td>
      <td>3.042</td>
      <td>0.873</td>
      <td>4.560</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2029-04-16</td>
      <td>5.072</td>
      <td>0.808</td>
      <td>4.281</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2031-04-16</td>
      <td>7.100</td>
      <td>0.748</td>
      <td>4.172</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2034-04-17</td>
      <td>10.147</td>
      <td>0.665</td>
      <td>4.108</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2044-04-18</td>
      <td>20.297</td>
      <td>0.447</td>
      <td>4.044</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2054-04-16</td>
      <td>30.436</td>
      <td>0.327</td>
      <td>3.743</td>
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
      <td>2024-04-16</td>
      <td>0.000</td>
      <td>1.000</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2025-04-16</td>
      <td>1.014</td>
      <td>0.950</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2026-04-16</td>
      <td>2.028</td>
      <td>0.909</td>
      <td>4.809</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2027-04-16</td>
      <td>3.042</td>
      <td>0.873</td>
      <td>4.560</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2028-04-16</td>
      <td>4.058</td>
      <td>0.839</td>
      <td>4.420</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2029-04-16</td>
      <td>5.072</td>
      <td>0.808</td>
      <td>4.281</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2030-04-16</td>
      <td>6.086</td>
      <td>0.777</td>
      <td>4.227</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2031-04-16</td>
      <td>7.100</td>
      <td>0.748</td>
      <td>4.172</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2032-04-16</td>
      <td>8.117</td>
      <td>0.719</td>
      <td>4.151</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2033-04-16</td>
      <td>9.131</td>
      <td>0.691</td>
      <td>4.129</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2034-04-16</td>
      <td>10.144</td>
      <td>0.665</td>
      <td>4.108</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2035-04-16</td>
      <td>11.158</td>
      <td>0.639</td>
      <td>4.101</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2036-04-16</td>
      <td>12.175</td>
      <td>0.613</td>
      <td>4.095</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2037-04-16</td>
      <td>13.189</td>
      <td>0.589</td>
      <td>4.088</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2038-04-16</td>
      <td>14.203</td>
      <td>0.567</td>
      <td>4.082</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2039-04-16</td>
      <td>15.217</td>
      <td>0.544</td>
      <td>4.076</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2040-04-16</td>
      <td>16.233</td>
      <td>0.523</td>
      <td>4.069</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2041-04-16</td>
      <td>17.247</td>
      <td>0.503</td>
      <td>4.063</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2042-04-16</td>
      <td>18.261</td>
      <td>0.484</td>
      <td>4.057</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2043-04-16</td>
      <td>19.275</td>
      <td>0.465</td>
      <td>4.050</td>
    </tr>
    <tr>
      <th>20</th>
      <td>2044-04-16</td>
      <td>20.292</td>
      <td>0.447</td>
      <td>4.044</td>
    </tr>
    <tr>
      <th>21</th>
      <td>2045-04-16</td>
      <td>21.306</td>
      <td>0.432</td>
      <td>4.014</td>
    </tr>
    <tr>
      <th>22</th>
      <td>2046-04-16</td>
      <td>22.319</td>
      <td>0.418</td>
      <td>3.984</td>
    </tr>
    <tr>
      <th>23</th>
      <td>2047-04-16</td>
      <td>23.333</td>
      <td>0.405</td>
      <td>3.954</td>
    </tr>
    <tr>
      <th>24</th>
      <td>2048-04-16</td>
      <td>24.350</td>
      <td>0.392</td>
      <td>3.923</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2049-04-16</td>
      <td>25.364</td>
      <td>0.380</td>
      <td>3.893</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2050-04-16</td>
      <td>26.378</td>
      <td>0.368</td>
      <td>3.863</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2051-04-16</td>
      <td>27.392</td>
      <td>0.357</td>
      <td>3.833</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2052-04-16</td>
      <td>28.408</td>
      <td>0.346</td>
      <td>3.803</td>
    </tr>
    <tr>
      <th>29</th>
      <td>2053-04-16</td>
      <td>29.422</td>
      <td>0.336</td>
      <td>3.773</td>
    </tr>
  </tbody>
</table>
</div>
## d. Plot the calibrated US SOFR Zero Interest Rates and Discount Factor curves

Plot the SOFR zero rates and discount factor curves by maturity. Follow section 1 c in the QuantLib Advanced notebook.
```python
# Plot the SOFR yield curve
Plt = sofr_yield_curve_details_df.Plot (x='Date',                    y='ZeroRate',                    grid=True,                    style='*-',                    title=f'SOFR Curve: Zero Rates as of {calc_date. To_date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = sofr_yield_curve_details_df.Plot (x='Date',                    y='DiscountFactor',                    grid=True,                    style='*-',                    title=f'SOFR Curve: Discount Factors as of {calc_date. To_date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```
    Text (0.5,                    0,                    'Date')
![png](CreditMarketSolutions_223_1.png)
![png](CreditMarketSolutions_223_2.png)
-----------------------------------------------------------
# Problem 4: CDS Hazard Rate calibration and valuation
## Follow Section "2. CDS Hazard Rate calibration + Pricing" in the QuantLib Advanced notebook !!!

## a. Load and explore the CDS market data (IBM credit issuer)

Load the `cds_market_data_eod` Excel file into a dataframe. 

Plot the historical time series of CDS Par Spreads for the available tenors.
```python
# Cds_market_quotes
Cds_market_quotes = pd. Read_excel ('./data/cds_market_data_eod. Xlsx')
Print (cds_market_quotes.Head ())

# Create par spreads (bps) dataframe
Par_spread_col_names = [f'par_spread_{n}y' for n in [1,                   2,                   3,                   5,                   7,                   10]]
Cds_par_spreads_df = cds_market_quotes. Set_index ('date')[par_spread_col_names]

Plt = cds_par_spreads_df.Plot (grid=True,                    style='-',                    title='IBM CDS Par Spreads ',                    figsize=(12,                   8))
Plt. Set_ylabel ('IBM CDS Par Spreads')
Plt. Set_xlabel ('Date')

```

            Date ticker                short_name    tier      sector  region   
    0 2024-01-02    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer  \
    1 2024-01-03    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    2 2024-01-04    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    3 2024-01-05    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    4 2024-01-08    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    
      Currency doc_clause  running_coupon  cds_assumed_recovery  par_spread_1 y   
    0      USD       XR 14            0.01                   0.4        13.6831  \
    1      USD       XR 14            0.01                   0.4        14.2256   
    2      USD       XR 14            0.01                   0.4        13.8318   
    3      USD       XR 14            0.01                   0.4        13.6181   
    4      USD       XR 14            0.01                   0.4        13.4433   
    
       Par_spread_2 y  par_spread_3 y  par_spread_5 y  par_spread_7 y  par_spread_10 y  
    0        18.8194        28.3917        44.7053        62.1494         69.1972  
    1        19.6610        29.4493        46.4866        63.6475         71.4311  
    2        19.1828        28.8454        45.4735        62.6543         70.9180  
    3        18.7703        28.3417        44.7575        61.9778         70.2746  
    4        18.3692        27.7599        43.8548        60.8378         68.8914  
    Text (0.5,                    0,                    'Date')
![png](png)
## b. Calibrate the IBM hazard rate curve as of 2024-04-15

Follow section 2 a in the QuantLib Advanced notebook. Use the calibrated SOFR discount curve from Problem 3 b.
```python
Def calibrate_cds_hazard_rate_curve (calc_date,                    sofr_yield_curve_handle,                    cds_par_spreads_bps,                    cds_recovery_rate = 0.4):
    '''Calibrate hazard rate curve from CDS Par Spreads'''
    CDS_settle_days = 2

    CDS_day_count = ql. Actual 360 ()

    # CDS standard tenors: 1 Y,                    2 Y,                    3 Y,                    5 Y 7 Y and 10 Y
    CDS_tenors = [ql.Period (y,                    ql. Years) for y in [1,                    2,                    3,                    5,                    7,                    10]]
    CDS_helpers = [ql.SpreadCdsHelper ((cds_par_spread / 10000.0),                    CDS_tenor,                    CDS_settle_days,                    ql.TARGET (),                   
                                  Ql. Quarterly,                    ql. Following,                    ql. DateGeneration. TwentiethIMM,                    CDS_day_count,                    cds_recovery_rate,                    sofr_yield_curve_handle)
               
    For (cds_par_spread,                    CDS_tenor) in zip (cds_par_spreads_bps,                    CDS_tenors)]

    # bootstrap hazard_rate_curve
    Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,                    CDS_helpers,                    CDS_day_count)
    Hazard_rate_curve.EnableExtrapolation ()

    Return (hazard_rate_curve)
Def get_hazard_rates_df (hazard_rate_curve):
    '''Return dataframe with calibrated hazard rates and survival probabilities'''
    
    CDS_day_count = ql. Actual 360 ()
    
    Hazard_list = [(hr[0]. To_date (),                    
                CDS_day_count.YearFraction (calc_date,                    hr[0]),                   
                Hr[1] * 1 e 4,                   
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

    Grid_dates,                    year_frac,                    hazard_rates,                    surv_probs = zip (*hazard_list)

    Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,                    
                                     'YearFrac': year_frac,                   
                                     'HazardRateBps': hazard_rates,                                                        
                                     'SurvivalProb': surv_probs})
    Return (hazard_rates_df)

```
```python
# CDS spreads for IBM as of calc_date = 2024-04-15
Cds_par_spreads = list (cds_par_spreads_df. Loc['2024-04-15'])
Print (cds_par_spreads)

# Cds_recovery_rate
Cds_recovery_rate = 0.4

# Hazard_rate_curve
Hazard_rate_curve = calibrate_cds_hazard_rate_curve (calc_date,                    sofr_yield_curve_handle,                    cds_par_spreads,                    cds_recovery_rate)

# Hazard_rates_df
Hazard_rates_df = get_hazard_rates_df (hazard_rate_curve)

Print (hazard_rates_df)

```

    [11.7219,                    16.1196,                    23.6826,                    37.2246,                    52.551,                    63.7804]
             Date   YearFrac  HazardRateBps  SurvivalProb
    0  2024-04-12   0.000000      19.372676      1.000000
    1  2025-06-20   1.205556      19.372676      0.997667
    2  2026-06-22   2.225000      35.805389      0.994032
    3  2027-06-21   3.236111      68.966639      0.987125
    4  2029-06-20   5.263889     102.209360      0.966876
    5  2031-06-20   7.291667     166.229764      0.934828
    6  2034-06-20  10.336111     164.376354      0.889198
## c. Plot the calibrated Hazard Rates and Survival Probability curves
Follow section 2 b in the QuantLib Advanced notebook. Use the calibrated SOFR discount curve from Problem 3 b.
```python
Plt = hazard_rates_df.Plot (x='Date',                    y='HazardRateBps',                    grid=True,                    style='*-',                    title=f'IBM Hazard Rates Curve as of {calc_date. To_date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Hazard Rate (bps)')
Plt. Set_xlabel ('Date')

Plt = hazard_rates_df.Plot (x='Date',                    y='SurvivalProb',                    grid=True,                    style='*-',                    title=f'IBM Survival Probability Curve as of {calc_date. To_date ()}',                    figsize=(12,                   4))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')

```
    Text (0.5,                    0,                    'Date')
![png](air/par spread and PV of a CDS 

Follow section 2 c in the QuantLib Advanced notebook. Construct a CDS object with 100 bps coupon and 2029-06-20 maturity. Compute the fair/par spread and PV.
```python
# CDS specs
Side = ql. Protection. Seller

Face_notional = 100

Contractual_spread = 100 / 10000

Cds_start_date = calc_date
Cds_maturity_date = ql.Date (20,                    6,                    2029)

# Create CDS schedule
Cds_schedule = ql.MakeSchedule (cds_start_date,                    cds_maturity_date,                    ql.Period ('3 M'),                   
                            Ql. Quarterly,                    ql.TARGET (),                    ql. Following,                    ql. Unadjusted,                    ql. DateGeneration. TwentiethIMM)

# Create CDS object
Cds_obj = ql.CreditDefaultSwap (side,                    face_notional,                    contractual_spread,                    cds_schedule,                    ql. Following,                    ql. Actual 360 ())

# Create CDS pricing engine
Default_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)
Cds_engine = ql.MidPointCdsEngine (default_prob_curve_handle,                    cds_recovery_rate,                    sofr_yield_curve_handle)
Cds_obj.SetPricingEngine (cds_engine)
# Print CDS valuation results
Print ('CDS protection start date: ',                    cds_obj.ProtectionStartDate ())
Print ('CDS fair/par spread: ',                    round (cds_obj.FairSpread ()*10000,                    3))
Print ('CDS PV: ',                    round (cds_obj.NPV (),                    4))    
Print ('CDS Premium Leg PV: ',                    round (cds_obj.CouponLegNPV (),                    4))
Print ('CDS Default Leg PV',                    round (cds_obj.DefaultLegNPV (),                    4))
Print ('Survival Prob. To Maturity: ',                    round (hazard_rate_curve.SurvivalProbability (cds_maturity_date),                    4))

```

    CDS protection start date: April 12 th,                    2024
    CDS fair/par spread: 37.172
    CDS PV: 2.9014
    CDS Premium Leg PV: 4.6179
    CDS Default Leg PV -1.7166
    Survival Prob. To Maturity: 0.9669
<hr><font color="green"><h1>from file: 6 FINM 35700_CreditMarkets_Spring 2024_Solution_4</h1></font>

# Homework 4

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

### Due Date: 2024-04-30

* Alex Popovici
* alex.popovici@uchicago.edu

This homework relies on multiple files (from previous weeks):

- The bond symbology file `bond_symbology`,                    
- The "on-the-run" treasuries data file `govt_on_the_run`,                   
- The bond market data file `bond_market_prices_eod`,                   
- The CDS data file `cds_market_data_eod`. 
- The SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swap symbology file `sofr_swap_symbology`,                   
- The SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swap market data file `sofr_swaps_market_data_eod`.
```python
# Import tools from previous homeworks
From credit_market_tools import *

# Use static calculation/valuation date of 2024-04-19,                    matching data available in the market prices EOD file
Calc_date = ql.Date (19,                    4,                    2024)
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
### Load the symbology + market data dataframes. Calibrate the following curves as of 2024-04-19:
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

# Load govt_on_the_run,                    as of 2024-04-19
Govt_on_the_run = pd. Read_excel ('./data/govt_on_the_run. Xlsx')

# Keep OTR treasuries only
Govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run['ticker']. Str.Contains ('B|C')]

# Create symbology for on-the-run treasuries only
Govt_symbology_otr = bond_symbology[bond_symbology['isin']. Isin (govt_on_the_run_simple['isin'])]. Copy ()
Govt_symbology_otr = govt_symbology_otr. Sort_values (by='maturity')

# Merge market data as of 2024-04-19 into treasury OTR symbology
Govt_combined_otr = govt_symbology_otr.Merge (bond_market_prices_eod,                     on=['class',                   'ticker',                   'figi',                   'isin'])
Display (govt_combined_otr.Head ())

# Tsy_yield_curve calibration
Tsy_yield_curve = calibrate_yield_curve_from_frame (calc_date,                    govt_combined_otr,                    'midPrice')
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
      <th>...</th>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
Sofr_symbology. Set_index ('figi',                    inplace=True)
Display (sofr_symbology)

# Sofr_market_quotes
Sofr_market_quotes = pd. Read_excel ('./data/sofr_swaps_market_data_eod. Xlsx')

# Sofr_combined
Sofr_combined = sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes['date'] == as_of_date],                    how='left',                    on=['figi'])
Display (sofr_combined.Head ())

# Sofr_yield_curve calibration
Sofr_yield_curve = calibrate_sofr_curve_from_frame (calc_date,                    sofr_combined,                    'midRate')
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 10 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 20 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 30 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
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
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
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
Par_spread_col_names = [f'par_spread_{n}y' for n in [1,                   2,                   3,                   5,                   7,                   10]]
Cds_par_spreads_df = cds_market_quotes. Set_index ('date')[par_spread_col_names]

Cds_par_spreads = list (cds_par_spreads_df. Loc[as_of_date])
Print (cds_par_spreads)

# Cds_recovery_rate
Cds_recovery_rate = 0.4

# Hazard_rate_curve
Hazard_rate_curve = calibrate_cds_hazard_rate_curve (calc_date,                    sofr_yield_curve_handle,                    cds_par_spreads,                    cds_recovery_rate)

# Hazard_rate_curve calibrated to IBM CDS par spreads
Default_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)
```

    [12.0769,                    17.3082,                    24.866,                    39.6501,                    53.9093,                    65.3221]
## b. Create the IBM risky bond objects
### Identify the following 3 IBM fixed rate bonds in the symbology table and create the corresponding fixed rate bonds (3 bond objects).

- Security = 'IBM 3.3 05/15/26' / figi = 'BBG 00 P 3 BLH 05'
- Security = 'IBM 3.3 01/27/27' / figi = 'BBG 00 FVNGFP 3'
- Security = 'IBM 3 1/2 05/15/29' / figi = 'BBG 00 P 3 BLH 14'

Use the create_bond_from_symbology () function (discussed in from Homework 2,                    Problem 1 b) to create the bonds objects.

List the bond cashflows using the get_bond_cashflows () function.
```python
# Corp_symbology_ibm
Corp_symbology_ibm = bond_symbology[(bond_symbology. Ticker == 'IBM') & (bond_symbology. Cpn_type == 'FIXED')]

# Corp_combined_ibm
Corp_combined_ibm = corp_symbology_ibm.Merge (bond_market_prices_eod,                    how='inner',                    on=['class',                    'ticker',                    'isin',                    'figi'])
Corp_combined_ibm. Set_index ('figi',                    inplace=True)

# Keep selected IBM bonds only
Ibm_selected_figis = ['BBG 00 P 3 BLH 05',                    'BBG 00 FVNGFP 3',                    'BBG 00 P 3 BLH 14']
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
Ibm_bond_objects = [ create_bond_from_symbology (df_row. To_dict ()) for index,                    df_row in ibm_df.Iterrows ()]

# List the bond cashflows
For i in range (0,                    3):
    Print ('Bond cashflows for',                    ibm_df. Iloc[i]['security'])
    Display (get_bond_cashflows (ibm_bond_objects[i],                    calc_date)) 

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
      <td>May 15 th,                    2024</td>
      <td>0.072222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>10</th>
      <td>November 15 th,                    2024</td>
      <td>0.572222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>11</th>
      <td>May 15 th,                    2025</td>
      <td>1.072222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>12</th>
      <td>November 15 th,                    2025</td>
      <td>1.572222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>13</th>
      <td>May 15 th,                    2026</td>
      <td>2.072222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>14</th>
      <td>May 15 th,                    2026</td>
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
      <td>July 27 th,                    2024</td>
      <td>0.272222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>15</th>
      <td>January 27 th,                    2025</td>
      <td>0.772222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>16</th>
      <td>July 27 th,                    2025</td>
      <td>1.272222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>17</th>
      <td>January 27 th,                    2026</td>
      <td>1.772222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>18</th>
      <td>July 27 th,                    2026</td>
      <td>2.272222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>19</th>
      <td>January 27 th,                    2027</td>
      <td>2.772222</td>
      <td>1.65</td>
    </tr>
    <tr>
      <th>20</th>
      <td>January 27 th,                    2027</td>
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
      <td>May 15 th,                    2024</td>
      <td>0.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>10</th>
      <td>November 15 th,                    2024</td>
      <td>0.572222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>11</th>
      <td>May 15 th,                    2025</td>
      <td>1.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>12</th>
      <td>November 15 th,                    2025</td>
      <td>1.572222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>13</th>
      <td>May 15 th,                    2026</td>
      <td>2.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>14</th>
      <td>November 15 th,                    2026</td>
      <td>2.572222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>15</th>
      <td>May 15 th,                    2027</td>
      <td>3.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>16</th>
      <td>November 15 th,                    2027</td>
      <td>3.572222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>17</th>
      <td>May 15 th,                    2028</td>
      <td>4.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>18</th>
      <td>November 15 th,                    2028</td>
      <td>4.572222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>19</th>
      <td>May 15 th,                    2029</td>
      <td>5.072222</td>
      <td>1.75</td>
    </tr>
    <tr>
      <th>20</th>
      <td>May 15 th,                    2029</td>
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
Risky_bond_engine = ql.RiskyBondEngine (default_prob_curve_handle,                    flat_recovery_rate,                    tsy_yield_curve_handle)

# Model/intrinsic prices and yields
Ibm_model_prices = []
Ibm_model_yields = []

# Print the clean prices and yields for the 3 test bonds
For i in range (0,                    3):
    Fixed_rate_bond = ibm_bond_objects[i]
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine)
    
    CorpBondModelPrice = round (fixed_rate_bond.CleanPrice (),                    3)
    CorpBondModelYield = round (fixed_rate_bond.BondYield (corpBondModelPrice,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100,                    3)

    Ibm_model_prices.Append (corpBondModelPrice)
    Ibm_model_yields.Append (corpBondModelYield)
# Display relevant metrics
Ibm_df['modelPrice'] = ibm_model_prices
Ibm_df['modelYield'] = ibm_model_yields

display (ibm_df [['security',                    'modelPrice',                    'modelYield']])

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
display (ibm_df [['security',                    'midPrice',                    'modelPrice',                    'basisPrice',                    'midYield',                    'modelYield',                    'basisYield']])
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
CDS-implied,                    intrinsic bond prices are higher than bond market prices.

Following factors could explain the basis dislocation for the 3 IBM bonds:
1. Hazard Rate curve mismatch: the synthetic CDS credit market is underestimating the credit risk in the IBM issuer curve,                    relative to the cash corporate bond market. This opens the opportunity for Bond vs CDS basis arbitrage trades,                    as discussed in Session 2. 
2. Risk-free yield curve mismatch: the (synthetic) SOFR yield curve is tighter than the (cash) US Treasury curve. This is usually due to a funding differential for cash vs. Synthetic products.
3. Temporarily dislocation: Individual bonds are temporarily dislocated from their "fair value" from the issuer curve (e.g. in a Nelson-Siegel type parametric model). This can happen due to buying vs. Selling imbalance in that particular bond.
4. Liquidity discounts: in general,                    less liquid (e.g. off-the-run) bonds trade at a price discount to more liquid (e.g. on-the-run) bonds. This usually causes a liquidty-implied "richer" basis (wider in yield space).

-----------------------------------------------------------
# Problem 2: Compute scenario sensitivities for risky bonds
## a. Compute scenario IR 01 s and Durations for the 3 IBM bonds
Use the 3 IBM test bonds defined in Problem 1. 

Compute the scenario IR 01 and Durations using a '-1 bp' interest rate shock,                    as described in Section 6. "Market Data Scenarios" in the QuantLib Basics notebook.

Display the computed scenario IR 01 and Durations.

Remember that IR 01 = Dirty_Price * Duration.
```python
# Bump interest rate by -1 bps (parallel shift)
Interest_rate_scenario_1 bp_down = ql.SimpleQuote (-0.0001)
Tsy_yield_curve_handle_1 bp_down = ql.YieldTermStructureHandle (ql.ZeroSpreadedTermStructure (tsy_yield_curve_handle,                    ql.QuoteHandle (interest_rate_scenario_1 bp_down)))
Risky_bond_engine_1 bp_down = ql.RiskyBondEngine (default_prob_curve_handle,                    flat_recovery_rate,                    tsy_yield_curve_handle_1 bp_down)
```
```python
# Model scenario metrics
Ibm_scen_prices_1 bp_down = []
Ibm_scen_IR 01 = []
Ibm_scen_duration = []
# Calculate IR 01 and duration
For i in range (0,                    3):
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

display (ibm_df [['security',                    'scen_IR01',                    'scen_duration']])

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
For i in range (0,                    3):
    Fixed_rate_bond = ibm_bond_objects[i]
    
    # Calc model dirty price for base case
    Fixed_rate_bond.SetPricingEngine (risky_bond_engine)    
    Dirty_price_base = fixed_rate_bond.DirtyPrice ()
    
    # Compute analytical duration and DV 01
    Bond_yield_rate = ql.InterestRate (ibm_model_yields[i]/100,                    ql.ActualActual (ql. ActualActual. ISMA),                    ql. Compounded,                    ql. Semiannual)
    Analytic_duration = ql.BondFunctions.Duration (fixed_rate_bond,                    bond_yield_rate)
    Analytic_DV 01 = analytic_duration * dirty_price_base /100 

    Ibm_analytic_durations.Append (analytic_duration)
    Ibm_analytic_DV 01 s.Append (analytic_DV 01)
# Display relevant metrics
Ibm_df['analytic_DV 01'] = ibm_analytic_DV 01 s
Ibm_df['analytic_duration'] = ibm_analytic_durations

display (ibm_df [['security',                    'analytic_DV01',                    'analytic_duration']])

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
display (ibm_df [['security',                    'scen_IR01',                    'analytic_DV01']])
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
DV 01 s and IR 01 s are expected to be similar,                    since a -1 bp change in the (risk free) interest rate curve causes approximately a -1 bp change in the (risky) bond yield curve.

## c. Compute scenario CS 01 s (credit spread sensitivities) for the 3 IBM bonds
Use the 3 IBM test bonds defined in Problem 1. 

Apply a '-1 bp' (parallel shift) scenario to the IBM CDS Par Spread quotes and calibrate the scenario hazard rate curve. 

Create a new scenario RiskyBondEngine,                    using the scenario hazard rate curve.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped hazard rate curve) to obtain the '-1 bp' scenario CS 01 (credit spread sensitivities).

Compare the scenario CS 01 s vs analytic DV 01 s. Are they expected to be similar?
```python
# Hazard_rate_curve calibration (from IBM CDS par spreads)
Cds_par_spreads_1 bp_down = [ps - 1 for ps in cds_par_spreads]
Print (cds_par_spreads)
Print (cds_par_spreads_1 bp_down)

# Hazard_rate_curve
Hazard_rate_curve_1 bp_down = calibrate_cds_hazard_rate_curve (calc_date,                    sofr_yield_curve_handle,                    cds_par_spreads_1 bp_down,                    cds_recovery_rate)
Default_prob_curve_handle_1 bp_down = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve_1 bp_down)

# Risky bond engine for CDS Par Spread -1 bp scenario
Risky_bond_engine_cds_1 bp_down = ql.RiskyBondEngine (default_prob_curve_handle_1 bp_down,                    flat_recovery_rate,                    tsy_yield_curve_handle)

```

    [12.0769,                    17.3082,                    24.866,                    39.6501,                    53.9093,                    65.3221]
    [11.0769,                    16.3082,                    23.866,                    38.6501,                    52.9093,                    64.3221]
```python
# Calculate CS 01
Ibm_model_cs 01 = []

For i in range (0,                    3):
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
display (ibm_df [['security',                    'scen_IR01',                    'analytic_DV01',                    'CS01']])

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
CS 01 s and DV 01 s are expected to be similar,                    since a -1 bp change in the credit spread curve causes approximately a -1 bp change in the (risky) bond yield curve.

## d. Compute scenario REC 01 (recovery rate sensitivity) for the 3 IBM bonds
Use the 3 IBM test bonds defined in Problem 1. 

Apply a +1% scenario bump to the IBM recovery rate (bump the flat_recovery_rate parameter by 1%,                    from 40% to 41%).

Create a new scenario RiskyBondEngine,                    using the scenario new recovery rate.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped recovery rate) to obtain the +1% scenario REC 01 (recovery rate sensitivity).
```python
# Bump recovery rate by 1% up
Flat_recovery_rate_1 pct_up = flat_recovery_rate + 0.01
Risky_bond_engine_rec_1 pct_up = ql.RiskyBondEngine (default_prob_curve_handle,                    flat_recovery_rate_1 pct_up,                    tsy_yield_curve_handle)

# Calculate REC 01
Ibm_model_rec 01 = []

For i in range (0,                    3):
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
print (ibm_df [['security',                    'REC01']])

```

                            Security     REC 01
    Figi                                      
    BBG 00 P 3 BLH 05    IBM 3.3 05/15/26  0.005857
    BBG 00 FVNGFP 3    IBM 3.3 01/27/27  0.009410
    BBG 00 P 3 BLH 14  IBM 3 1/2 05/15/29  0.029299
-----------------------------------------------------------
# Problem 3: Perpetual CDS
We are interested in a perpetual CDS contract (infinite maturity) on a face notional of $100,                    flat interest rate of 4% and coupon of 5% (quarterly payments).

For simplicity,                    we assuming a flat hazard rate of 1% per annum,                    a recovery rate of 40%,                    T+0 settlement and zero accrued.

Use the simple CDS valuation formulas derived in Session 3 as a template.

The value of the perpetual CDS is obtained as a limit case of the simple CDS valuation formulas derived in Session 3,                    for $T \to \infty$.

$$\begin{align}
PV_{CDS\_PL}\left (c,                    r,                    h,                    R,                    \infty \right) = \frac{c}{4 \cdot \left (e^{\left (r+h\right)/4}-1 \right)} \simeq \frac{c}{r+h}
\end{align}$$

$$\begin{align}
PV_{CDS\_DL}\left (c,                    r,                    h,                    R,                   \infty \right) = \frac{\left (1-R\right)\cdot h}{r+h} 
\end{align}$$

$$\begin{align}
PV_{CDS} = PV_{CDS\_PL} - PV_{CDS\_DL}
\end{align}$$

$$\begin{align}
CDS\_ParSpread = c \cdot \frac{PV_{CDS\_DL}}{PV_{CDS\_PL}} \simeq \left (1-R\right)\cdot h
\end{align}$$
```python
Def calc_perpetual_cds_premium_leg_pv (c,                    r,                    h,                    R,                    face):
    Return (c / 4 / (np.Exp ((r+h)/4)-1) * face)

Def calc_perpetual_cds_default_leg_pv (c,                    r,                    h,                    R,                    face):
    Return ((1 - R) * h / (r + h) * face)

Def calc_perpetual_cds_pv (c,                    r,                    h,                    R,                    face):
    Return (calc_perpetual_cds_premium_leg_pv (c,                    r,                    h,                    R,                    face) - calc_perpetual_cds_default_leg_pv (c,                    r,                    h,                    R,                    face))

Def calc_perpetual_cds_par_spread (c,                    r,                    h,                    R,                    face):
    Return (c * calc_perpetual_cds_default_leg_pv (c,                    r,                    h,                    R,                    face) / calc_perpetual_cds_premium_leg_pv (c,                    r,                    h,                    R,                    face))
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
Perpetual_cds_premium_leg_pv = calc_perpetual_cds_premium_leg_pv (c,                    r,                    h,                    R,                    face)
Print ('perpetual_cds_premium_leg_pv: ',                    round (perpetual_cds_premium_leg_pv,                    2))

# Perpetual_cds_default_leg_pv
Perpetual_cds_default_leg_pv = calc_perpetual_cds_default_leg_pv (c,                    r,                    h,                    R,                    face)
Print ('perpetual_cds_default_leg_pv: ',                    round (perpetual_cds_default_leg_pv,                    2))
```

    Perpetual_cds_premium_leg_pv: 99.38
## b. Compute the CDS PV and the CDS Par Spread.
```python
Perpetual_cds_pv = calc_perpetual_cds_pv (c,                    r,                    h,                    R,                    face)
Print ('perpetual_cds_pv: ',                    round (perpetual_cds_pv,                    2))

Perpetual_cds_par_spread_bps = calc_perpetual_cds_par_spread (c,                    r,                    h,                    R,                    face) * 1 e 4
Print ('perpetual_cds_par_spread_bps: ',                    round (perpetual_cds_par_spread_bps,                    2))

Perpetual_cds_par_spread_approx_bps = (1 - R) * h * 1 e 4
Print ('perpetual_cds_par_spread_approx_bps: ',                    round (perpetual_cds_par_spread_approx_bps,                    2))

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
Perpetual_cds_pv_r_1 bp_down = calc_perpetual_cds_pv (c,                    r_1 bp_down,                    h,                    R,                    face)
Perpetual_cds_ir 01 = perpetual_cds_pv_r_1 bp_down - perpetual_cds_pv
Print ('perpetual_cds_ir 01 ($): ',                    round (perpetual_cds_ir 01,                    2))

# CDS HR 01 
H_1 bp_down = h - 0.0001
Perpetual_cds_pv_h_1 bp_down = calc_perpetual_cds_pv (c,                    r,                    h_1 bp_down,                    R,                    face)
Perpetual_cds_hr 01 = perpetual_cds_pv_h_1 bp_down - perpetual_cds_pv
Print ('perpetual_cds_hr 01 ($): ',                    round (perpetual_cds_hr 01,                    2))

# CDS CS 01
Perpetual_cds_par_spread_h_1 bp_down = calc_perpetual_cds_par_spread (c,                    r,                    h_1 bp_down,                    R,                    face) * 1 e 4
Perpetual_cds_par_spread_bps_delta = perpetual_cds_par_spread_bps - perpetual_cds_par_spread_h_1 bp_down
Perpetual_cds_cs 01 = perpetual_cds_hr 01 / perpetual_cds_par_spread_bps_delta
Print ('perpetual_cds_cs 01 ($): ',                    round (perpetual_cds_cs 01,                    2))

# CDS REC 01 
R_1 pct_up = R + 0.01
Perpetual_cds_pv_R_1 pct_up = calc_perpetual_cds_pv (c,                    r,                    h,                    R_1 pct_up,                    face)
Perpetual_cds_rec 01 = perpetual_cds_pv_R_1 pct_up - perpetual_cds_pv
Print ('perpetual_cds_rec 01 ($): ',                    round (perpetual_cds_rec 01,                    2))
```

    Perpetual_cds_ir 01 ($): 0.18
    Perpetual_cds_hr 01 ($): 0.3
    Perpetual_cds_cs 01 ($): 0.49
    Perpetual_cds_rec 01 ($): 0.2
## d. At what time T does the (implied) default probability over next 10 years drop to 1%?

$$\begin{align}
\mathbb{P} \left (\tau \in [T,                    T+10] \right) = 1/100
\end{align}$$
$$\begin{align}
\mathbb{P} \left (\tau \in [T,                    T+10] \right)
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
\mathbb{P} \left (\tau \in [T,                    T+10] \right) = 1/100
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
Print ('T =',                    T)
```

    T = 225.3001724944001
-----------------------------------------------------------
# Problem 4: Nelson-Siegel model for smooth hazard rate curves

## This exercise implements tsome of the concepts introduced in Lecture 4,                    Section 1 "Parametric Hazard Rate Models"

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
Vz_df = corp_symbology_vz.Merge (bond_market_prices_eod,                    how='inner',                    on=['class',                    'ticker',                    'isin',                    'figi'])

# Sort the dataframe by bond maturity and display the head of the dataframe.
Vz_df. Sort_values ('maturity',                    inplace=True)
Display (vz_df.Head ())

# Plot the VZ yields (Y-axis) by TTM (X-axis).
Plt = vz_df.Plot (x='TTM',                    y = 'midYield',                    figsize = (12,                    6),                    title = "VZ Market Yields (pct)",                    grid=True,                    style='*')
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
      <th>...</th>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
      <td>...</td>
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
    Text (0.5,                    0,                    'Bond TTM')
![png](CreditMarketSolutions_279_2.png)
## b. Create the Nelson-Siegel curve shape (4 parameters) and compute the corresponding SSE function.
For a given set of parameters,                    write a function to compute the SSE "Sum of Squared Errors" penalty function in price space (defined as sum of squared differences between model and market prices for all Verizon fixed-rate bonds).
For each bond,                    compute the bond DV 01,                    using Section "9. Analytical Duration" in the QuantLib Basics notebook as a template.

Use 1/DV 01 as SSE weights,                    as discussed in Lecture 3. You can ignore the liquidity adjuster for the purpose of this exercise.
```python
Def nelson_siegel (params,                    maturity):
    ''' params = (theta 1,                    theta 2,                    theta 3,                    lambda)'''        
    If (maturity == 0 or params[3] <= 0):
        Slope_1 = 1
        Curvature = 0
    Else:
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
        Curvature = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature
    
    Return total_value

Def create_nelson_siegel_curve (calc_date,                    nelson_siegel_params):
    ''' nelson_siegel_params = (theta 1,                    theta 2,                    theta 3,                    lambda)'''            
    Nelson_siegel_surv_prob_dates = [calc_date + ql.Period (T ,                    ql. Years) for T in range (31)]
    Nelson_siegel_average_hazard_rates = [nelson_siegel (nelson_siegel_params,                    T) for T in range (31)]
    Nelson_siegel_surv_prob_levels = [np.Exp (-T * nelson_siegel_average_hazard_rates[T]) for T in range (31)]
    
    # cap and floor survival probs
    Nelson_siegel_surv_prob_levels = [max (min (x,                    1),                    1 e-8) for x in nelson_siegel_surv_prob_levels]

    # nelson_siegel_surv_prob_curve
    Nelson_siegel_credit_curve = ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,                    nelson_siegel_surv_prob_levels,                    ql. Actual 360 (),                    ql.TARGET ())
    Nelson_siegel_credit_curve.EnableExtrapolation ()
    Nelson_siegel_credit_curve_handle = ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)
    
    Return (nelson_siegel_credit_curve_handle)
Def calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,                    
                      Calc_date,                    
                      Fixed_rate_bond_objects,                    
                      Tsy_yield_curve_handle,                    
                      Bond_recovery_rate = 0.4):
    
    # nelson_siegel_surv_prob_curve_handle
    Nelson_siegel_surv_prob_curve_handle = create_nelson_siegel_curve (calc_date,                    nelson_siegel_params)
    
    # nelson_siegel_risky_bond_engine
    Nelson_siegel_risky_bond_engine = ql.RiskyBondEngine (nelson_siegel_surv_prob_curve_handle,                    bond_recovery_rate,                    tsy_yield_curve_handle)
    
    Bond_model_prices = []
    Bond_model_yields = []
    
    For fixed_rate_bond in fixed_rate_bond_objects:
        Fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)
        
        Bond_price = fixed_rate_bond.CleanPrice ()                
        Bond_yield = fixed_rate_bond.BondYield (bond_price,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100
        
        Bond_model_prices.Append (bond_price)
        Bond_model_yields.Append (bond_yield)
    
    Return (bond_model_prices,                    bond_model_yields)

Def nelson_siegel_sse (nelson_siegel_params,                    
                      Calc_date,                    
                      Fixed_rate_bond_objects,                    
                      Market_prices,                    
                      Calib_weights,                   
                      Tsy_yield_curve_handle,                    
                      Bond_recovery_rate = 0.4):
    
    # bond_model_prices
    Bond_model_prices,                    bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,                    
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
Def create_bonds_and_weights (bond_details,                    tsy_yield_curve_handle):
    
    # risk_free_bond_engine
    Risk_free_bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_handle)
    Fixed_rate_bond_objects = []
    Bond_market_prices = []    
    Bond_yields = []
    Bond_DV 01 s = []    
    Bond_durations = []    
    
    For index,                    row in bond_details.Iterrows ():
        Fixed_rate_bond = create_bond_from_symbology (row)
        Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
        
        Fixed_rate_bond_objects.Append (fixed_rate_bond)
        
        Bond_price = row['midPrice']                
        Bond_yield = fixed_rate_bond.BondYield (bond_price,                    ql. Thirty 360 (ql. Thirty 360. USA),                    ql. Compounded,                    ql. Semiannual) * 100
        Bond_yield_rate = ql.InterestRate (bond_yield/100,                    ql.ActualActual (ql. ActualActual. ISMA),                    ql. Compounded,                    ql. Semiannual)
        Bond_duration = ql.BondFunctions.Duration (fixed_rate_bond,                    bond_yield_rate)
        Bond_DV 01   = fixed_rate_bond.DirtyPrice () * bond_duration
        
        Bond_market_prices.Append (bond_price)
        Bond_yields.Append (bond_yield)
        Bond_DV 01 s.Append (bond_DV 01)
        Bond_durations.Append (bond_duration)   
             
    Calib_weights = [1 / d for d in bond_DV 01 s]
    
    Sum_calib_weights = sum (calib_weights)
    Calib_weights = [x / sum_calib_weights for x in calib_weights]
    
    Return (fixed_rate_bond_objects,                    calib_weights,                    bond_market_prices,                    bond_yields,                    bond_DV 01 s,                    bond_durations)

```
```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Initial_nelson_siegel_params
Initial_nelson_siegel_params = [0.03,                    -0.01,                    0.02,                    5.0]
Print ('initial_nelson_siegel_params: ',                    initial_nelson_siegel_params)

Fixed_rate_bond_objects,                    calib_weights,                    bond_market_prices,                    bond_yields,                    bond_DV 01 s,                    bond_durations = create_bonds_and_weights (vz_df,                    tsy_yield_curve_handle)
Vz_df['duration'] = bond_durations
Vz_df['calib_weight'] = calib_weights

Init_bond_model_prices,                    init_bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (initial_nelson_siegel_params,                    calc_date,                    fixed_rate_bond_objects,                    tsy_yield_curve_handle,                    bond_recovery_rate)
Vz_df['initModelPrice'] = init_bond_model_prices
Vz_df['initModelYield'] = init_bond_model_yields

display (vz_df [['security',                    'midPrice',                    'initModelPrice',                    'calib_weight']]. head ())

# Initial_sse
Initial_sse = nelson_siegel_sse (initial_nelson_siegel_params,                    calc_date,                    fixed_rate_bond_objects,                    bond_market_prices,                    calib_weights,                    tsy_yield_curve_handle,                    bond_recovery_rate)
Print ('initial_sse =',                    initial_sse)

```

    Initial_nelson_siegel_params: [0.03,                    -0.01,                    0.02,                    5.0]
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
    Fixed_rate_bond_objects,                    calib_weights,                    bond_market_prices,                    bond_yields,                    bond_DV 01 s,                    bond_durations = create_bonds_and_weights (bond_details,                    tsy_yield_curve_handle)
    
    # start calibration
    Param_bounds = [(1 e-3,                    0.1),                    (-0.1,                    0.1),                    (-0.1,                    0.1),                    (1 e-3,                    10)]
            
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
Calib_results = calibrate_nelson_siegel_model (initial_nelson_siegel_params,                    calc_date,                    vz_df,                    tsy_yield_curve_handle,                    bond_recovery_rate)
Print (calib_results)
    
# Calib_nelson_siegel_params
Calib_nelson_siegel_params = calib_results. X
Print ('calib_nelson_siegel_params: ',                    calib_nelson_siegel_params)

# Calib_nelson_siegel_curve
Calib_nelson_siegel_curve = create_nelson_siegel_curve (calc_date,                    calib_nelson_siegel_params)

# Calib_sse
Calib_sse = nelson_siegel_sse (calib_nelson_siegel_params,                    calc_date,                    fixed_rate_bond_objects,                    bond_market_prices,                    calib_weights,                    tsy_yield_curve_handle,                    bond_recovery_rate)
Print ('initial_sse =',                    round (initial_sse,                    3),                    'calib_sse =',                    round (calib_sse,                    3))

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
## d. Compute smooth model prices,                    yields and "edges"

Price all Verizon bonds on the calibrated credit curve and compute the corresponding model yields and edges.

Add following columns to the dataframe and display the head of the results:

| modelPrice | modelYield | edgePrice | edgeYield |
|----------|----------|----------|----------|
```python
# Price all Verizon bonds on the calibrated credit curve and compute the corresponding yields.
Bond_model_prices,                    bond_model_yields = calculate_nelson_siegel_model_prices_and_yields (calib_nelson_siegel_params,                    calc_date,                    fixed_rate_bond_objects,                    tsy_yield_curve_handle,                    bond_recovery_rate)

Vz_df['modelPrice'] = bond_model_prices
Vz_df['modelYield'] = bond_model_yields
Vz_df['edgePrice'] = vz_df['modelPrice'] - vz_df['midPrice']
Vz_df['edgeYield'] = vz_df['modelYield'] - vz_df['midYield']

display (vz_df [['security',                    'midPrice',                   'initModelPrice',                    'modelPrice',                    'edgePrice']]. head ())
display (vz_df [['security',                    'midYield',                   'initModelYield',                    'modelYield',                    'edgeYield']]. head ())
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
Plt = vz_df.Plot (x='maturity',                    y = ['midPrice',                    'modelPrice'],                    figsize = (12,                    6),                    title = "Market vs Model Prices",                    grid=True,                    style='*')
Plt. Set_ylabel ('Bond Prices (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,                    0,                    'Bond Maturity')
![png](CreditMarketSolutions_289_1.png)
```python
# Plot the model vs market yields (Y-axis) by maturity (X-axis).
Plt = vz_df.Plot (x='maturity',                    y = ['midYield',                    'modelYield'],                    figsize = (12,                    6),                    title = "Market vs Model Yields (pct)",                    grid=True,                    style='*')
Plt. Set_ylabel ('Bond Yields (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,                    0,                    'Bond Maturity')
![png](CreditMarketSolutions_290_1.png)
```python
# Plot the edges in yield space (Y-axis) by maturity (X-axis).
Plt = vz_df.Plot (x='maturity',                    y = ['edgeYield'],                    figsize = (12,                    6),                    title = "Model Edges in yield space (pct)",                    grid=True,                    style='*')
Plt.Axhline (0,                    color='red',                    linestyle='--',                    alpha=0.7)
Plt. Set_ylabel ('Yield Edge (pct)')
Plt. Set_xlabel ('Bond Maturity')

```
    Text (0.5,                    0,                    'Bond Maturity')
![png](CreditMarketSolutions_291_1.png)
### What do you think about the quality of the model fit?
Model fit looks good,                    given that fact that we are matching closely the market prices of 40 VZ bonds with only 4 Nelson-Siegel model parameters.
