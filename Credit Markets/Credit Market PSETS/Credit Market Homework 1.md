---
title: Credit Market Homework 1
tags:
  - bond_symbology
  - credit_market_homework
  - time_series_analysis
  - us_treasury_bonds
  - yield_curve
aliases:
  - Bond Symbology
  - FINM 35700
  - Homework 1
  - US Treasuries
key_concepts:
  - Bond symbology exploration
  - On-the-run treasuries
  - Time series of coupons
  - US treasury instruments
  - US treasury yields
---

# Credit Market Homework 1

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
	. Dataframe tbody tr th: only-of-type {
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
govt_symbology_10y.plot(x='start_date',         y='coupon',         grid=True,         style='-*',         title='US Treasury coupons by issue date (last 10 years)',         figsize=(12,        8))
```

    <Axes: title={'center': 'US Treasury coupons by issue date (last 10 years)'},         xlabel='start_date'>
![png](CreditMarketSolutions_7_1.png)

## b. Historical time series of US treasury coupons

Plot the time series of coupons for for US treasury notes/bonds issued in the last 10 years (indexed by issue date).
What can you say about the overall level of issued coupons in the last 4 years?

```python
import plotly.express as px

fig = px.scatter(govt_symbology_10y,         x='start_date',         y='coupon',         title='US Treasury coupons by issue date (last 10 years)')
fig.update_layout(xaxis_title='Issue Date',         yaxis_title='Coupon',         template='plotly_white')
fig.show()
```

```python
# 4y cut-off date
cut_off_date_4y = pd.to_datetime('2020-04-01')
govt_symbology_4y = govt_symbology[govt_symbology['start_date'] >= cut_off_date_4y].copy()

# Plot the US Treasury coupons by issue date (last 10 years)
govt_symbology_4y.plot(x='start_date',         y='coupon',         grid=True,         style='-*',         title='US Treasury coupons by issue date (last 4 years)',         figsize=(12,        8))

# describe
govt_symbology_4y[['start_date',         'coupon']].describe()
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
# Load govt_on_the_run,         as of 2024-04-01

# Keep OTR treasuries only
govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run['ticker'].str.contains('B|C')]
display(govt_on_the_run_simple)
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
	. Dataframe tbody tr th: only-of-type {
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

- Bullet/non-callable (mty_typ="AT MATURITY"),
- Senior unsecured (rank = "Sr Unsecured"),
- Fixed coupon (cpn_type="FIXED")

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
corp_symbology = corp_symbology[['ticker',         'isin',         'figi',         'security',         'name',         'coupon',         'start_date',         'maturity',         'term',         'TTM']]

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
	. Dataframe tbody tr th: only-of-type {
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
govt_agg = govt_symbology.merge(bond_market_prices_eod,          on=['class',        'ticker',        'figi',        'isin'])

govt_agg.head()

# Plot a graph/scatter plot of treasury mid yields by TTM
govt_agg.plot(x='TTM',         y='midYield',         grid=True,         style='*',         title='US Treasury Yields by TTM',         figsize=(12,        8))
```

    <Axes: title={'center': 'US Treasury Yields by TTM'},         xlabel='TTM'>
![png](CreditMarketSolutions_20_1.png)

```python
Merge market data as of 2024-04-01 into treasury symbology
govt_agg = govt_symbology.merge(bond_market_prices_eod,          on=['class',        'ticker',        'figi',        'isin'])

govt_agg.head()

fig = px.scatter(govt_agg,         x='TTM',         y='midYield',         title='US Treasury Yields by TTM')
fig.update_layout(xaxis_title='Time to Maturity (Years)',         yaxis_title='Mid Yield',         template='plotly_white')
fig.show()
```

      Cell In[25],         line 1
        Merge market data as of 2024-04-01 into treasury symbology
                                     ^
    SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers

## b. Explore on-the-run treasuries only

Create a separate joint dataframe for on-the-run treasuries only.

Plot a graph/scatter plot of on-the-run treasury mid yields by TTM.

```python
# Merge market data as of 2024-04-01 into treasury OTR symbology
govt_agg_otr = govt_symbology_otr.merge(bond_market_prices_eod,          on=['class',        'ticker',        'figi',        'isin'])

fig = px.scatter(govt_agg_otr,         x='TTM',         y='midYield',         title='OTR US Treasury yields by TTM')
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',         yaxis_title='Mid Yield',         template='plotly_white')
Fig.Show ()
```

## c. Load and explore corporate bond market prices and yields

Merge the filtered [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] symbology dataframe with the market data and add the following columns:

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
|----------|-------|-------------|-----|----------|---------|---------|---------|---------|

List the unique tickers/issuers available in the dataframe.

```python
# Merge market data as of 2024-04-01 into corp symbology
Corp_agg = corp_symbology.Merge (bond_market_prices_eod,          on=['ticker',        'figi',        'isin'])

Print (corp_symbology. Shape)

Display (corp_agg.Head ())
```

    (67,         10)

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
corp_agg_unique_tickers = corp_agg [['ticker',         'name']]. drop_duplicates ()

Display (corp_agg_unique_tickers)
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
Fig = px.Scatter (corp_agg,         x='TTM',         y='midYield',         color='ticker',         title='Corporate Bond Yields by TTM')
Fig. Add_trace (px.Scatter (govt_agg_otr,         x='TTM',         y='midYield'). Data[0])
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',         yaxis_title='Mid Yield',         template='plotly_white')
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
corp_merged = corp_agg.Merge (bond_symbology [['isin',         'und_bench_isin']],         on='isin')

# Create df containing govt_benchmark_yields
govt_benchmark_yields = bond_market_prices_eod[bond_market_prices_eod['class'] == 'Govt'][['isin',         'midYield']]
Govt_benchmark_yields.Rename (columns={'midYield': 'und_bench_yield',         'isin': 'und_bench_isin'},         inplace=True)

# Add benchmark bond yield
Corp_merged = corp_merged.Merge (govt_benchmark_yields,         on='und_bench_isin')
Corp_merged['credit_spread'] = corp_merged['midYield'] - corp_merged['und_bench_yield']
display (corp_merged [['ticker',         'isin',         'figi',         'security',         'und_bench_isin',         'midYield',         'und_bench_yield',         'credit_spread']])
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
Fig = px.Scatter (corp_merged,         x='TTM',         y='credit_spread',         color='ticker',         title='Corporate Bond Credit Spreads by TTM')
Fig. Update_traces (mode='lines+markers') 
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',         yaxis_title='Credit Spread',         template='plotly_white')
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
Interp_tsy_yield_vec = np.Interp (corp_merged['TTM'],         govt_agg_otr['TTM'],         govt_agg_otr['midYield'])

# Add interp_tsy_yield and g_spread
Corp_merged['interp_tsy_yield'] = interp_tsy_yield_vec
Corp_merged['g_spread'] = corp_merged['midYield'] - corp_merged['interp_tsy_yield']

# Display results
display (corp_merged [['ticker',         'isin',         'figi',         'security',         'und_bench_isin',         'midYield',         'und_bench_yield',         'credit_spread',         'interp_tsy_yield',         'g_spread']])
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
Fig = px.Scatter (corp_merged,         x='TTM',         y='g_spread',         color='ticker',         title='Corporate Bond G-Spreads by TTM')
Fig. Update_traces (mode='lines+markers')
Fig. Update_layout (xaxis_title='Time to Maturity (Years)',         yaxis_title='G-Spread',         template='plotly_white') 
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
	. Dataframe tbody tr th: only-of-type {
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

Issue_date = ql.Date (1,         4,         2020)        # 2020-04-01
Maturity_date = ql.Date (1,         4,         2030)     # 2030-04-01

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
X = [(cf.Date (). To_date (),         cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date_fixed,         cf_amount = zip (*x)
Fixed_rate_bond_cashflows = pd.DataFrame (data={'CashFlowDate': cf_date_fixed,         'CashFlowAmount': cf_amount})

# Cashflows match the ones displayed on page 13 (from Bloomberg CSHF screenshot),         up to the face value multiplier.
Display (fixed_rate_bond_cashflows)
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
