---
tags: [14da9a5e,  434ad435,  924fe824,  04a7d030,  6a9cd852,  8954d4d1]
title: Untitled 2
---
# Untitled 2

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

- Alex Popovici
- alex.popovici@uchicago.edu

This homework relies on:

- the government and corporate bonds symbology file `bond_symbology`,
- the “on-the-run” treasuries data file `govt_on_the_run` and
- the market data file `bond_market_prices_eod`.

You can find more details on US treasury instruments in the FINM 37400 Fixed Income course.

```latex
<span id="cb1-1"><span>import</span> QuantLib <span>as</span> ql</span>
<span id="cb1-2"><span>import</span> pandas <span>as</span> pd</span>
<span id="cb1-3"><span>import</span> numpy <span>as</span> np</span>
<span id="cb1-4"><span>from</span> matplotlib <span>import</span> pyplot <span>as</span> plt</span>
<span id="cb1-5"><span>import</span> seaborn <span>as</span> sns</span>
<span id="cb1-6"><span>import</span> scipy <span>as</span> sp</span>
<span id="cb1-7"><span>import</span> plotly.express <span>as</span> px</span>
<span id="cb1-8"><span>import</span> plotly.graph_objects <span>as</span> go</span>
<span id="cb1-9"></span>
```

## Problem 1: Explore symbology for US treasuries and corporate bonds

## a. Load and explore US government bond symbology

Load the `bond_symbology` Excel file into a dataframe. It contains symbology for both government and corporate bonds.

Select US Treasury bonds only (class = ‘Govt’,  ticker = ‘T’). For each government bond issue,  calculate its initial term/time-to-maturity in years (based on issue date and maturity date),  as well as the current time-to-maturity. Assume a year has 365.25 days (alternatively,  use QuantLib yearFraction function).

```latex
<span id="cb2-1"><span>import</span> pandas <span>as</span> pd</span>
<span id="cb2-2"></span>
<span id="cb2-3"><span># Import bond market prices</span></span>
<span id="cb2-4">bond_market_prices_eod <span>=</span> pd.read_excel(<span>'data/bond_market_prices_eod.xlsx'</span>)</span>
<span id="cb2-5">display(bond_market_prices_eod)</span>
<span id="cb2-6"></span>
<span id="cb2-7"><span># Import CDS market data</span></span>
<span id="cb2-8">cds_market_data_eod <span>=</span> pd.read_excel(<span>'data/cds_market_data_eod.xlsx'</span>)</span>
<span id="cb2-9">display(cds_market_data_eod)</span>
<span id="cb2-10"></span>
<span id="cb2-11"><span># Import CDX IG 42 5Y basket composition</span></span>
<span id="cb2-12">cdx_ig_42_5y_basket_composition <span>=</span> pd.read_excel(<span>'data/cdx_ig_42_5y_basket_composition.xlsx'</span>)</span>
<span id="cb2-13">display(cdx_ig_42_5y_basket_composition)</span>
<span id="cb2-14"></span>
<span id="cb2-15"><span># Import CDX symbology</span></span>
<span id="cb2-16">cdx_symbology <span>=</span> pd.read_excel(<span>'data/cdx_symbology.xlsx'</span>)</span>
<span id="cb2-17">display(cdx_symbology)</span>
<span id="cb2-18"></span>
<span id="cb2-19"><span># Import corporate symbology</span></span>
<span id="cb2-20">corp_symbology <span>=</span> pd.read_excel(<span>'data/corp_symbology.xlsx'</span>)</span>
<span id="cb2-21">display(corp_symbology)</span>
<span id="cb2-22"></span>
<span id="cb2-23"><span># Import government on-the-run data</span></span>
<span id="cb2-24">govt_on_the_run <span>=</span> pd.read_excel(<span>'data/govt_on_the_run.xlsx'</span>)</span>
<span id="cb2-25">display(govt_on_the_run)</span>
<span id="cb2-26"></span>
<span id="cb2-27"><span># Import government symbology</span></span>
<span id="cb2-28">govt_symbology <span>=</span> pd.read_excel(<span>'data/govt_symbology.xlsx'</span>)</span>
<span id="cb2-29">display(govt_symbology)</span>
<span id="cb2-30"></span>
<span id="cb2-31"><span># Import LQD basket composition</span></span>
<span id="cb2-32">lqd_basket_composition <span>=</span> pd.read_excel(<span>'data/lqd_basket_composition.xlsx'</span>)</span>
<span id="cb2-33">display(lqd_basket_composition)</span>
<span id="cb2-34"></span>
<span id="cb2-35"><span># Import LQD corporate symbology</span></span>
<span id="cb2-36">lqd_corp_symbology <span>=</span> pd.read_excel(<span>'data/lqd_corp_symbology.xlsx'</span>)</span>
<span id="cb2-37">display(lqd_corp_symbology)</span>
<span id="cb2-38"></span>
<span id="cb2-39"><span># Import market prices EOD</span></span>
<span id="cb2-40">market_prices_eod <span>=</span> pd.read_excel(<span>'data/market_prices_eod.xlsx'</span>)</span>
<span id="cb2-41">display(market_prices_eod)</span>
<span id="cb2-42"></span>
<span id="cb2-43"><span># Import SOFR swaps market data</span></span>
<span id="cb2-44">sofr_swaps_market_data_eod <span>=</span> pd.read_excel(<span>'data/sofr_swaps_market_data_eod.xlsx'</span>)</span>
<span id="cb2-45">display(sofr_swaps_market_data_eod)</span>
<span id="cb2-46"></span>
<span id="cb2-47"><span># Import SOFR swaps symbology</span></span>
<span id="cb2-48">sofr_swaps_symbology <span>=</span> pd.read_excel(<span>'data/sofr_swaps_symbology.xlsx'</span>)</span>
<span id="cb2-49">display(sofr_swaps_symbology)</span>
```

|  | date | class | ticker | isin | figi | bidPrice | askPrice | accrued | bidYield | askYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-04-19 | Corp | IBM | US 459200 KX 88 | BBG 01 DMT 8986 | 97.453 | 97.706 | 0.9635 | 5.248 | 5.173 |
| 1 | 2024-04-19 | Corp | IBM | US 459200 GS 40 | BBG 0000 L 5 Z 27 | 99.145 | 99.818 | 2.2245 | 5.683 | 5.617 |
| 2 | 2024-04-19 | Corp | GM | US 37046 AFD 28 | BBG 019 LXFPP 4 | 97.075 | 97.556 | 0.5225 | 6.472 | 6.342 |
| 3 | 2024-04-19 | Corp | GM | US 37046 AFA 88 | BBG 017 B 6 GFF 0 | 95.012 | 95.453 | 2.1245 | 6.337 | 6.216 |
| 4 | 2024-04-19 | Corp | F | US 34540 TZC 97 | BBG 017 QYHT 99 | 98.950 | 99.289 | 2.0675 | 6.419 | 6.298 |
| … | … | … | … | … | … | … | … | … | … | … |
| 821 | 2024-04-19 | Corp | VZ | US 92343 VDY 74 | BBG 00 G 6 QW 2 B 8 | 96.703 | 96.899 | 0.4240 | 5.367 | 5.292 |
| 822 | 2024-04-19 | Corp | VZ | US 92343 VEA 89 | BBG 00 HC 11 V 79 | 92.230 | 92.607 | 0.9125 | 5.582 | 5.527 |
| 823 | 2024-04-19 | Corp | VZ | US 92343 VER 15 | BBG 00 M 1 BQWX 0 | 95.789 | 96.079 | 0.3850 | 5.414 | 5.337 |
| 824 | 2024-04-19 | Corp | VZ | US 92343 VES 97 | BBG 00 N 8 J 22 P 5 | 93.604 | 93.944 | 0.8070 | 5.407 | 5.322 |
| 825 | 2024-04-19 | Corp | VZ | US 92343 VEU 44 | BBG 00 PZ 10 YF 2 | 93.089 | 93.377 | 1.5620 | 5.462 | 5.399 |

826 rows × 10 columns

|  | date | ticker | short_name | tier | sector | region | currency | doc_clause | running_coupon | cds_assumed_recovery | par_spread_1 y | par_spread_2 y | par_spread_3 y | par_spread_5 y | par_spread_7 y | par_spread_10 y |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-01-02 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 13.6831 | 18.8194 | 28.3917 | 44.7053 | 62.1494 | 69.1972 |
| 1 | 2024-01-03 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 14.2256 | 19.6610 | 29.4493 | 46.4866 | 63.6475 | 71.4311 |
| 2 | 2024-01-04 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 13.8318 | 19.1828 | 28.8454 | 45.4735 | 62.6543 | 70.9180 |
| 3 | 2024-01-05 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 13.6181 | 18.7703 | 28.3417 | 44.7575 | 61.9778 | 70.2746 |
| 4 | 2024-01-08 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 13.4433 | 18.3692 | 27.7599 | 43.8548 | 60.8378 | 68.8914 |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 71 | 2024-04-15 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 12.0135 | 16.8549 | 24.4589 | 38.7203 | 54.1499 | 64.8137 |
| 72 | 2024-04-16 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 12.2996 | 17.4094 | 25.2142 | 40.1146 | 55.1220 | 65.6635 |
| 73 | 2024-04-17 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 12.4232 | 17.1464 | 25.3140 | 40.2663 | 55.2605 | 66.5756 |
| 74 | 2024-04-18 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 12.3517 | 17.5932 | 25.1507 | 40.0698 | 54.7934 | 66.0532 |
| 75 | 2024-04-19 | IBM | Intl Business Machs Corp | SNRFOR | Technology | N.Amer | USD | XR 14 | 0.01 | 0.4 | 12.0769 | 17.3082 | 24.8660 | 39.6501 | 53.9093 | 65.3221 |

76 rows × 16 columns

|  | date | index_symbol | index_ticker | index_series | index_weight | ticker | name | seniority | sector | implied_rating | currency | doc_clause | cds_coupon | cds_recovery | cds_par_spread_1 y | cds_par_spread_2 y | cds_par_spread_3 y | cds_par_spread_5 y | cds_par_spread_7 y | cds_par_spread_10 y |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | ABX | Barrick Gold Corp | SNRFOR | Basic Materials | A | USD | XR 14 | 100 | 40 | 10.8035 | 17.2391 | 25.5981 | 44.7979 | 64.1402 | 82.3295 |
| 1 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | AEP | Amern Elec Pwr Co Inc | SNRFOR | Utilities | A | USD | XR 14 | 100 | 40 | 10.4695 | 15.2003 | 23.2108 | 37.4360 | 51.0402 | 63.9027 |
| 2 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | AES | The AES Corp | SNRFOR | Utilities | BB | USD | XR 14 | 100 | 40 | 31.7554 | 55.2736 | 78.2859 | 126.3347 | 166.3675 | 180.9695 |
| 3 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | AIG | Amern Intl Gp Inc | SNRFOR | Financials | A | USD | XR 14 | 100 | 40 | 19.4843 | 27.4915 | 35.2190 | 52.1935 | 78.1249 | 95.0203 |
| 4 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | ALL | Allstate Corp | SNRFOR | Financials | AA | USD | XR 14 | 100 | 40 | 7.1240 | 10.4222 | 14.8189 | 24.5515 | 32.3016 | 42.8434 |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 120 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | VRZN | Verizon Comms Inc | SNRFOR | Telecommunications Services | BBB | USD | XR 14 | 100 | 40 | 35.9909 | 44.2447 | 51.4093 | 67.8014 | 87.8595 | 107.2258 |
| 121 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | WALMINC | WALMART INC | SNRFOR | Consumer Services | AA | USD | XR 14 | 100 | 40 | 8.9994 | 13.5101 | 18.5765 | 28.8583 | 39.0980 | 50.1219 |
| 122 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | WHR | Whirlpool Corp | SNRFOR | Consumer Goods | BB | USD | XR 14 | 100 | 40 | 33.1632 | 53.4151 | 85.6808 | 150.6406 | 190.4388 | 217.7965 |
| 123 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | WMB | WILLIAMS COS INC | SNRFOR | Energy | BBB | USD | XR 14 | 100 | 40 | 15.4765 | 25.3299 | 39.3661 | 68.4092 | 96.7565 | 116.3833 |
| 124 | 2024-04-25 | CDX_CDXIG 542 | CDX-NAIG | 42 | 0.8 | WY | Weyerhaeuser Co | SNRFOR | Basic Materials | AA | USD | XR 14 | 100 | 40 | 9.4613 | 15.2397 | 22.9177 | 36.7591 | 52.9787 | 66.2565 |

125 rows × 20 columns

|  | symbol | ticker | class | security | name | type | dcc | coupon | cpn_first | maturity | currency |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | CDX_CDXIG 041 | CDXIG 041 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/33 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2033-12-20 | USD |
| 1 | CDX_CDXIG 042 | CDXIG 042 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/34 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2034-06-20 | USD |
| 2 | CDX_CDXIG 141 | CDXIG 141 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/24 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2024-12-20 | USD |
| 3 | CDX_CDXIG 142 | CDXIG 142 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/25 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2025-06-20 | USD |
| 4 | CDX_CDXIG 241 | CDXIG 241 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/25 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2025-12-20 | USD |
| 5 | CDX_CDXIG 242 | CDXIG 242 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/26 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2026-06-20 | USD |
| 6 | CDX_CDXIG 341 | CDXIG 341 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/26 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2026-12-20 | USD |
| 7 | CDX_CDXIG 342 | CDXIG 342 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/27 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2027-06-20 | USD |
| 8 | CDX_CDXIG 541 | CDXIG 541 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/28 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2028-12-20 | USD |
| 9 | CDX_CDXIG 542 | CDXIG 542 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/29 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2029-06-20 | USD |
| 10 | CDX_CDXIG 741 | CDXIG 741 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 41 12/30 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2023-12-20 | 2030-12-20 | USD |
| 11 | CDX_CDXIG 742 | CDXIG 742 | Curncy | MARKIT CDX IG | MARKIT CDX. NA. IG. 42 06/31 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2031-06-20 | USD |
| 12 | CDX_CXPEM 041 | CXPEM 041 | Curncy | MARKIT CDX EM | MARKIT CDX. EM. 41 06/34 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2034-06-20 | USD |
| 13 | CDX_CXPEM 541 | CXPEM 541 | Curncy | MARKIT CDX EM | MARKIT CDX. EM. 41 06/29 | CREDIT DEFAULT SWAP | ACT/360 | 1 | 2024-06-20 | 2029-06-20 | USD |
| 14 | CDX_CXPHY 041 | CXPHY 041 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 41 12/33* | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2023-12-20 | 2033-12-20 | USD |
| 15 | CDX_CXPHY 042 | CXPHY 042 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 42 06/34 | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2024-06-20 | 2034-06-20 | USD |
| 16 | CDX_CXPHY 341 | CXPHY 341 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 41 12/26* | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2023-12-20 | 2026-12-20 | USD |
| 17 | CDX_CXPHY 342 | CXPHY 342 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 42 06/27 | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2024-06-20 | 2027-06-20 | USD |
| 18 | CDX_CXPHY 541 | CXPHY 541 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 41 12/28* | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2023-12-20 | 2028-12-20 | USD |
| 19 | CDX_CXPHY 542 | CXPHY 542 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 42 06/29 | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2024-06-20 | 2029-06-20 | USD |
| 20 | CDX_CXPHY 741 | CXPHY 741 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 41 12/30* | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2023-12-20 | 2030-12-20 | USD |
| 21 | CDX_CXPHY 742 | CXPHY 742 | Curncy | MARKIT CDX HY | MARKIT CDX. NA. HY. 42 06/31 | CREDIT DEFAULT SWAP | ACT/360 | 5 | 2024-06-20 | 2031-06-20 | USD |

|  | ticker | class | figi | isin | trace | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | country | currency |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | DIS | Corp | BBG 00 QNKJ 092 | US 254687 CZ 75 | DIS 4921182 | US 91282 CGU 99 | DIS 3.7 09/15/24 | WALT DISNEY COMPANY/THE | GLOBAL | 3.700 | FIXED | 30/360 | 2 | 2 | 2019-11-22 | 2020-03-15 | 2019-09-15 | 2024-09-15 | CALLABLE | Sr Unsecured | US | USD |
| 1 | DIS | Corp | BBG 00 QNKPCL 5 | US 254687 DD 54 | DIS 4907444 | US 91282 CGU 99 | DIS 3.7 10/15/25 | WALT DISNEY COMPANY/THE | GLOBAL | 3.700 | FIXED | 30/360 | 2 | 2 | 2019-11-22 | 2020-04-15 | 2019-10-15 | 2025-10-15 | CALLABLE | Sr Unsecured | US | USD |
| 2 | DIS | Corp | BBG 00 QNKGJP 6 | US 254687 DK 97 | DIS 4907439 | US 91282 CGR 60 | DIS 3 3/8 11/15/26 | WALT DISNEY COMPANY/THE | GLOBAL | 3.375 | FIXED | 30/360 | 2 | 2 | 2019-11-22 | 2020-05-15 | 2019-11-15 | 2026-11-15 | CALLABLE | Sr Unsecured | US | USD |
| 3 | DIS | Corp | BBG 00 QNKP 8 R 8 | US 254687 DV 52 | DIS 4908605 | US 91282 CGM 73 | DIS 6.55 03/15/33 | WALT DISNEY COMPANY/THE | GLOBAL | 6.550 | FIXED | 30/360 | 2 | 2 | 2019-11-22 | 2020-03-15 | 2019-09-15 | 2033-03-15 | AT MATURITY | Sr Unsecured | US | USD |
| 4 | DIS | Corp | BBG 00 QNKR 4 J 4 | US 254687 DZ 66 | DIS 4908062 | US 91282 CGM 73 | DIS 6.2 12/15/34 | WALT DISNEY COMPANY/THE | GLOBAL | 6.200 | FIXED | 30/360 | 2 | 2 | 2019-11-22 | 2019-12-15 | 2019-06-15 | 2034-12-15 | AT MATURITY | Sr Unsecured | US | USD |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 260 | VZ | Corp | BBG 017 BR 3 G 75 | US 92346 MJT 99 | VZ 5414106 | US 91282 CGT 27 | VZ 4.15 05/15/29 | VERIZON COMMUNICATIONS | DOMESTIC MTN | 4.150 | FIXED | 30/360 | 2 | 2 | 2022-05-19 | 2022-11-15 | 2022-05-19 | 2029-05-15 | CALLABLE | Sr Unsecured | US | USD |
| 261 | VZ | Corp | BBG 017 QYK 9 Z 0 | US 92346 MJZ 59 | VZ 5420578 | US 912810 TL 26 | VZ 4.65 06/15/52 | VERIZON COMMUNICATIONS | DOMESTIC MTN | 4.650 | FIXED | 30/360 | 2 | 2 | 2022-06-03 | 2022-12-15 | 2022-06-03 | 2052-06-15 | CALLABLE | Sr Unsecured | US | USD |
| 262 | VZ | Corp | BBG 0191 HMXJ 3 | US 92346 MKG 59 | VZ 5458130 | US 912810 TL 26 | VZ 4.6 08/15/52 | VERIZON COMMUNICATIONS | DOMESTIC MTN | 4.600 | FIXED | 30/360 | 2 | 2 | 2022-08-11 | 2023-02-15 | 2022-08-11 | 2052-08-15 | CALLABLE | Sr Unsecured | US | USD |
| 263 | VZ | Corp | BBG 019 LXC 9 P 3 | US 92346 MKQ 32 | VZ 5477070 | US 91282 CGT 27 | VZ 4 1/2 09/15/29 | VERIZON COMMUNICATIONS | DOMESTIC MTN | 4.500 | FIXED | 30/360 | 2 | 2 | 2022-09-22 | 2023-03-15 | 2022-09-22 | 2029-09-15 | CALLABLE | Sr Unsecured | US | USD |
| 264 | VZ | Corp | BBG 012 MB 8 P 10 | USU 9221 ABY 39 | VZ 5252610 | US 91282 CGM 73 | VZ 2.355 03/15/32 | VERIZON COMMUNICATIONS | EURO-DOLLAR | 2.355 | FIXED | 30/360 | 2 | 2 | 2021-09-20 | 2022-03-15 | 2021-09-20 | 2032-03-15 | CALLABLE | Sr Unsecured | US | USD |

265 rows × 22 columns

|  | ticker | date | figi | isin |
| --- | --- | --- | --- | --- |
| 0 | GT 10 Govt | 2024-04-19 | BBG 01 L 8 YJFB 3 | US 91282 CJZ 59 |
| 1 | GT 10 B Govt | 2024-04-19 | BBG 01 JZY 4 GQ 6 | US 91282 CJJ 18 |
| 2 | GT 10 C Govt | 2024-04-19 | BBG 01 HQWRSG 4 | US 91282 CHT 18 |
| 3 | GT 2 Govt | 2024-04-19 | BBG 01 M 44 ZLG 5 | US 91282 CKH 33 |
| 4 | GT 20 Govt | 2024-04-19 | BBG 01 LK 8 Y 0 L 1 | US 912810 TZ 12 |
| 5 | GT 20 B Govt | 2024-04-19 | BBG 01 K 7339 S 7 | US 912810 TW 80 |
| 6 | GT 20 C Govt | 2024-04-19 | BBG 01 HZNQ 0 S 3 | US 912810 TU 25 |
| 7 | GT 2 B Govt | 2024-04-19 | BBG 01 LNVJ 702 | US 91282 CKB 62 |
| 8 | GT 2 C Govt | 2024-04-19 | BBG 01 L 3 DFJ 02 | US 91282 CJV 46 |
| 9 | GT 3 Govt | 2024-04-19 | BBG 01 M 9 L 5 M 64 | US 91282 CKJ 98 |
| 10 | GT 30 Govt | 2024-04-19 | BBG 01 L 8 YJKX 8 | US 912810 TX 63 |
| 11 | GT 30 B Govt | 2024-04-19 | BBG 01 JZY 4 HS 2 | US 912810 TV 08 |
| 12 | GT 30 C Govt | 2024-04-19 | BBG 01 HQWRRD 9 | US 912810 TT 51 |
| 13 | GT 3 B Govt | 2024-04-19 | BBG 01 LW 4 R 927 | US 91282 CKE 02 |
| 14 | GT 3 C Govt | 2024-04-19 | BBG 01 L 8 YJD 28 | US 91282 CKA 89 |
| 15 | GT 5 Govt | 2024-04-19 | BBG 01 M 44 ZQJ 1 | US 91282 CKG 59 |
| 16 | GT 5 B Govt | 2024-04-19 | BBG 01 LNVJ 8 B 8 | US 91282 CKD 29 |
| 17 | GT 5 C Govt | 2024-04-19 | BBG 01 L 3 DFGS 8 | US 91282 CJW 29 |
| 18 | GT 7 Govt | 2024-04-19 | BBG 01 M 44 ZS 07 | US 91282 CKF 76 |
| 19 | GT 7 B Govt | 2024-04-19 | BBG 01 LNVJ 3 Y 4 | US 91282 CKC 46 |
| 20 | GT 7 C Govt | 2024-04-19 | BBG 01 L 3 DFFJ 0 | US 91282 CJX 02 |

|  | ticker | class | figi | isin | trace | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | country | currency |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | B | Govt | BBG 01 FSQGRT 9 | US 912796 CQ 02 | TSRYS 5551439 | B 09/14/23 | TREASURY BILL | US GOVERNMENT | 0.000 | ZERO | ACT/360 | NaN | 1 | 2023-03-16 | NaT | NaT | 2023-09-14 | US | USD |
| 1 | B | Govt | BBG 01 FY 3 YC 89 | US 912796 CR 84 | TSRYS 5554749 | B 09/21/23 | TREASURY BILL | US GOVERNMENT | 0.000 | ZERO | ACT/360 | NaN | 1 | 2023-03-23 | NaT | NaT | 2023-09-21 | US | USD |
| 2 | B | Govt | BBG 01 G 14 BS 72 | US 912796 CS 67 | TSRYS 5557561 | B 09/28/23 | TREASURY BILL | US GOVERNMENT | 0.000 | ZERO | ACT/360 | NaN | 1 | 2023-03-30 | NaT | NaT | 2023-09-28 | US | USD |
| 3 | B | Govt | BBG 01 BYWNTS 7 | US 912796 CU 14 | TSRYS 5513508 | B 04/18/23 | TREASURY BILL | US GOVERNMENT | 0.000 | ZERO | ACT/360 | NaN | 1 | 2022-12-20 | NaT | NaT | 2023-04-18 | US | USD |
| 4 | B | Govt | BBG 01 C 3 GB 4 X 6 | US 912796 CV 96 | TSRYS 5516304 | B 04/25/23 | TREASURY BILL | US GOVERNMENT | 0.000 | ZERO | ACT/360 | NaN | 1 | 2022-12-27 | NaT | NaT | 2023-04-25 | US | USD |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 377 | T | Govt | BBG 01 FQJ 5 MY 4 | US 91282 CGR 60 | TSRYS 5548232 | T 4 5/8 03/15/26 | US TREASURY N/B | US GOVERNMENT | 4.625 | FIXED | ACT/ACT | 2.0 | 1 | 2023-03-15 | 2023-09-15 | 2023-03-15 | 2026-03-15 | US | USD |
| 378 | T | Govt | BBG 01 G 14 BV 75 | US 91282 CGS 44 | TSRYS 5557563 | T 3 5/8 03/31/30 | US TREASURY N/B | US GOVERNMENT | 3.625 | FIXED | ACT/ACT | 2.0 | 1 | 2023-03-31 | 2023-09-30 | 2023-03-31 | 2030-03-31 | US | USD |
| 379 | T | Govt | BBG 01 G 14 BW 91 | US 91282 CGT 27 | TSRYS 5557562 | T 3 5/8 03/31/28 | US TREASURY N/B | US GOVERNMENT | 3.625 | FIXED | ACT/ACT | 2.0 | 1 | 2023-03-31 | 2023-09-30 | 2023-03-31 | 2028-03-31 | US | USD |
| 380 | T | Govt | BBG 01 G 14 BXX 2 | US 91282 CGU 99 | TSRYS 5557560 | T 3 7/8 03/31/25 | US TREASURY N/B | US GOVERNMENT | 3.875 | FIXED | ACT/ACT | 2.0 | 1 | 2023-03-31 | 2023-09-30 | 2023-03-31 | 2025-03-31 | US | USD |
| 381 | T | Govt | BBG 01 G 5 ZMM 43 | US 91282 CGV 72 | TSRYS 5565937 | T 3 3/4 04/15/26 | US TREASURY N/B | US GOVERNMENT | 3.750 | FIXED | ACT/ACT | 2.0 | 1 | 2023-04-17 | 2023-10-15 | 2023-04-15 | 2026-04-15 | US | USD |

382 rows × 19 columns

|  | date | holdings_date | etf_ticker | isin | security | issuer | coupon | maturity | cpn_type | class | currency | bidYield | askYield | midYield | face_notional | face_notional_weight |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-04-25 | 2024-04-24 | LQD | US 03522 AAJ 97 | ABIBB 4.9 02/01/46 | ANHEUSER-BUSCH COMPANIES LLC 4.9 02/01/2046 (S… | 1900-01-04 21:36:00 | 2046-02-01 | FIXED | CORP | USD | 5.776 | 5.730 | 5.7530 | 79521000 | 0.298516 |
| 1 | 2024-04-25 | 2024-04-24 | LQD | US 87264 ABF 12 | TMUS 3 7/8 04/15/30 | T-MOBILE USA INC 3.875 04/15/2030 (SENIOR) | 1900-01-03 21:00:00 | 2030-04-15 | FIXED | CORP | USD | 5.610 | 5.549 | 5.5795 | 62735000 | 0.235502 |
| 2 | 2024-04-25 | 2024-04-24 | LQD | US 126650 CZ 11 | CVS 5.05 03/25/48 | CVS HEALTH CORP 5.05 03/25/2048 (SENIOR) | 1900-01-05 01:12:00 | 2048-03-25 | FIXED | CORP | USD | 6.279 | 6.238 | 6.2585 | 66171000 | 0.248401 |
| 3 | 2024-04-25 | 2024-04-24 | LQD | US 38141 GFD 16 | GS 6 3/4 10/01/37 | GOLDMAN SACHS GROUP INC/THE T 2 6.75 10/01/2037… | 1900-01-06 18:00:00 | 2037-10-01 | FIXED | CORP | USD | 6.210 | 6.153 | 6.1815 | 48331000 | 0.181431 |
| 4 | 2024-04-25 | 2024-04-24 | LQD | US 716973 AG 71 | PFE 5.3 05/19/53 | PFIZER INVESTMENT ENTERPRISES PTE 5.3 05/19/20… | 1900-01-05 07:12:00 | 2053-05-19 | FIXED | CORP | USD | 5.777 | 5.740 | 5.7585 | 49272000 | 0.184963 |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 2459 | 2024-04-25 | 2024-04-24 | LQD | US 278642 AU 75 | EBAY 3.6 06/05/27 | EBAY INC 3.6 06/05/2027 (SENIOR) | 3.6 | 2027-06-05 | FIXED | CORP | USD | 5.471 | 5.370 | 5.4205 | 804000 | 0.003018 |
| 2460 | 2024-04-25 | 2024-04-24 | LQD | US 25470 DBJ 72 | WBD 3 5/8 05/15/30 | DISCOVERY COMMUNICATIONS LLC 3.625 05/15/2030 … | 3.625 | 2030-05-15 | FIXED | CORP | USD | 6.278 | 6.202 | 6.2400 | 721000 | 0.002707 |
| 2461 | 2024-04-25 | 2024-04-24 | LQD | US 458140 AX 85 | INTC 3.15 05/11/27 | INTEL CORPORATION 3.15 05/11/2027 (SENIOR) | 3.15 | 2027-05-11 | FIXED | CORP | USD | 5.315 | 5.242 | 5.2785 | 657000 | 0.002466 |
| 2462 | 2024-04-25 | 2024-04-24 | LQD | US 742718 EV 74 | PG 2.85 08/11/27 | PROCTER & GAMBLE CO 2.85 08/11/2027 (SENIOR) | 2.85 | 2027-08-11 | FIXED | CORP | USD | 4.983 | 4.898 | 4.9405 | 644000 | 0.002418 |
| 2463 | 2024-04-25 | 2024-04-24 | LQD | US 02005 NBQ 25 | ALLY 4 3/4 06/09/27 | ALLY FINANCIAL INC 4.75 06/09/2027 (SENIOR) | 4.75 | 2027-06-09 | FIXED | CORP | USD | 6.185 | 6.079 | 6.1320 | 301000 | 0.001130 |

2464 rows × 16 columns

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | amt_out | country | currency | status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | Corp | BBG 00 GNBL 206 | US 037833 CR 93 | US 91282 CKJ 98 | AAPL 3.2 05/11/27 | APPLE INC | GLOBAL | 3.2 | FIXED | 30/360 | 2 | 2 | 2017-05-11 | 2017-11-11 | 2017-05-11 | 2027-05-11 | CALLABLE | Sr Unsecured | 2000.0 | US | USD | ACTV |
| 1 | AAPL | Corp | BBG 00 GXJ 4 BZ 9 | US 037833 CX 61 | US 91282 CKJ 98 | AAPL 3 06/20/27 | APPLE INC | GLOBAL | 3.0 | FIXED | 30/360 | 2 | 2 | 2017-06-20 | 2017-12-20 | 2017-06-20 | 2027-06-20 | CALLABLE | Sr Unsecured | 1000.0 | US | USD | ACTV |
| 2 | AAPL | Corp | BBG 00 HMQPZ 05 | US 037833 DB 33 | US 91282 CKJ 98 | AAPL 2.9 09/12/27 | APPLE INC | GLOBAL | 2.9 | FIXED | 30/360 | 2 | 2 | 2017-09-12 | 2018-03-12 | 2017-09-12 | 2027-09-12 | CALLABLE | Sr Unsecured | 2000.0 | US | USD | ACTV |
| 3 | AAPL | Corp | BBG 00 J 59 YWR 6 | US 037833 DK 32 | US 91282 CKJ 98 | AAPL 3 11/13/27 | APPLE INC | GLOBAL | 3.0 | FIXED | 30/360 | 2 | 2 | 2017-11-13 | 2018-05-13 | 2017-11-13 | 2027-11-13 | CALLABLE | Sr Unsecured | 1500.0 | US | USD | ACTV |
| 4 | AAPL | Corp | BBG 01 GKRFG 36 | US 037833 ET 32 | US 91282 CKG 59 | AAPL 4 05/10/28 | APPLE INC | GLOBAL | 4.0 | FIXED | 30/360 | 2 | 2 | 2023-05-10 | 2023-11-10 | 2023-05-10 | 2028-05-10 | CALLABLE | Sr Unsecured | 1500.0 | US | USD | ACTV |
| … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … | … |
| 2459 | ZBH | Corp | BBG 013 JSZH 77 | US 98956 PAV 40 | US 91282 CJZ 59 | ZBH 2.6 11/24/31 | ZIMMER BIOMET HOLDINGS | GLOBAL | 2.6 | FIXED | 30/360 | 2 | 2 | 2021-11-24 | 2022-05-24 | 2021-11-24 | 2031-11-24 | CALLABLE | Sr Unsecured | 750.0 | US | USD | ACTV |
| 2460 | ZTS | Corp | BBG 00 HMQT 197 | US 98978 VAL 71 | US 91282 CKJ 98 | ZTS 3 09/12/27 | ZOETIS INC | GLOBAL | 3.0 | FIXED | 30/360 | 2 | 2 | 2017-09-12 | 2018-03-12 | 2017-09-12 | 2027-09-12 | CALLABLE | Sr Unsecured | 750.0 | US | USD | ACTV |
| 2461 | ZTS | Corp | BBG 00 TQH 47 F 4 | US 98978 Was 25 | US 91282 CKG 59 | ZTS 2 05/15/30 | ZOETIS INC | GLOBAL | 2.0 | FIXED | 30/360 | 2 | 2 | 2020-05-12 | 2020-11-15 | 2020-05-12 | 2030-05-15 | CALLABLE | Sr Unsecured | 750.0 | US | USD | ACTV |
| 2462 | ZTS | Corp | BBG 01 BFQSYF 9 | US 98978 VAV 53 | US 91282 CJZ 59 | ZTS 5.6 11/16/32 | ZOETIS INC | GLOBAL | 5.6 | FIXED | 30/360 | 2 | 3 | 2022-11-16 | 2023-05-16 | 2022-11-16 | 2032-11-16 | CALLABLE | Sr Unsecured | 750.0 | US | USD | ACTV |
| 2463 | ZTS | Corp | BBG 005 BRYP 85 | US 98978 VAH 69 | US 912810 TZ 12 | ZTS 4.7 02/01/43 | ZOETIS INC | GLOBAL | 4.7 | FIXED | 30/360 | 2 | 2 | 2013-10-30 | 2014-02-01 | 2013-08-01 | 2043-02-01 | CALLABLE | Sr Unsecured | 1150.0 | US | USD | ACTV |

2464 rows × 23 columns

|  | date | class | ticker | isin | figi | bid | ask | mid_clean | mid_dirty | bid_yield | ask_yield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2023-04-14 | Corp | DIS | US 254687 CZ 75 | BBG 00 QNKJ 092 | 98.6780 | 98.8480 | 98.7630 | 99.1020 | 4.679 | 4.551 |
| 1 | 2023-04-14 | Corp | DIS | US 254687 DD 54 | BBG 00 QNKPCL 5 | 98.4540 | 98.8210 | 98.6370 | 98.6680 | 4.361 | 4.203 |
| 2 | 2023-04-14 | Corp | DIS | US 254687 DK 97 | BBG 00 QNKGJP 6 | 97.0900 | 97.3690 | 97.2300 | 98.6640 | 4.260 | 4.174 |
| 3 | 2023-04-14 | Corp | DIS | US 254687 DV 52 | BBG 00 QNKP 8 R 8 | 115.1630 | 115.9840 | 115.5740 | 116.1740 | 4.624 | 4.529 |
| 4 | 2023-04-14 | Corp | DIS | US 254687 DZ 66 | BBG 00 QNKR 4 J 4 | 112.9390 | 113.5860 | 113.2620 | 115.3800 | 4.742 | 4.674 |
| … | … | … | … | … | … | … | … | … | … | … | … |
| 592 | 2023-04-14 | Govt | T | US 91282 CGR 60 | BBG 01 FQJ 5 MY 4 | 102.1250 | 102.1563 | 102.1406 | 102.5547 | 3.845 | 3.834 |
| 593 | 2023-04-14 | Govt | T | US 91282 CGS 44 | BBG 01 G 14 BV 75 | 100.3750 | 100.4375 | 100.4063 | 100.5742 | 3.563 | 3.553 |
| 594 | 2023-04-14 | Govt | T | US 91282 CGT 27 | BBG 01 G 14 BW 91 | 100.0703 | 100.0859 | 100.0781 | 100.2461 | 3.609 | 3.606 |
| 595 | 2023-04-14 | Govt | T | US 91282 CGU 99 | BBG 01 G 14 BXX 2 | 99.5703 | 99.5820 | 99.5762 | 99.7559 | 4.105 | 4.099 |
| 596 | 2023-04-14 | Govt | T | US 91282 CGV 72 | BBG 01 G 5 ZMM 43 | 99.7578 | 99.7734 | 99.7656 | 99.7852 | 3.836 | 3.831 |

597 rows × 11 columns

|  | date | figi | bidRate | askRate | midRate |
| --- | --- | --- | --- | --- | --- |
| 0 | 2024-01-02 | BBG 00 KFWPJJ 9 | 4.7960 | 4.8046 | 4.80030 |
| 1 | 2024-01-02 | BBG 00 KFWPJX 3 | 4.1368 | 4.1452 | 4.14100 |
| 2 | 2024-01-02 | BBG 00 KFWPK 15 | 3.8258 | 3.8327 | 3.82925 |
| 3 | 2024-01-02 | BBG 00 KFWPK 51 | 3.5907 | 3.5943 | 3.59250 |
| 4 | 2024-01-02 | BBG 00 KFWPK 79 | 3.5297 | 3.5333 | 3.53150 |
| … | … | … | … | … | … |
| 635 | 2024-04-25 | BBG 00 KFWPK 79 | 4.3894 | 4.3925 | 4.39095 |
| 636 | 2024-04-25 | BBG 00 KFWPK 51 | 4.4813 | 4.4846 | 4.48295 |
| 637 | 2024-04-25 | BBG 00 KFWPK 15 | 4.7085 | 4.7143 | 4.71140 |
| 638 | 2024-04-25 | BBG 00 KFWPJX 3 | 4.9220 | 4.9280 | 4.92500 |
| 639 | 2024-04-25 | BBG 00 KFWPJJ 9 | 5.2389 | 5.2465 | 5.24270 |

640 rows × 5 columns

|  | figi | ticker | class | bbg | name | tenor | type | dcc | exchange | country | currency | status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | BBG 00 KFWPJJ 9 | USOSFR 1 | Curncy | USOSFR 1 Curncy | USD Is ANN VS SOFR 1 Y | 1 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 1 | BBG 00 KFWPJX 3 | USOSFR 2 | Curncy | USOSFR 2 Curncy | USD Is ANN VS SOFR 2 Y | 2 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 2 | BBG 00 KFWPK 15 | USOSFR 3 | Curncy | USOSFR 3 Curncy | USD Is ANN VS SOFR 3 Y | 3 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 3 | BBG 00 KFWPK 51 | USOSFR 5 | Curncy | USOSFR 5 Curncy | USD Is ANN VS SOFR 5 Y | 5 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 4 | BBG 00 KFWPK 79 | USOSFR 7 | Curncy | USOSFR 7 Curncy | USD Is ANN VS SOFR 7 Y | 7 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 5 | BBG 00 KFWPKB 4 | USOSFR 10 | Curncy | USOSFR 10 Curncy | USD Is ANN VS SOFR 10 Y | 10 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 6 | BBG 00 KFWPKF 0 | USOSFR 20 | Curncy | USOSFR 20 Curncy | USD Is ANN VS SOFR 20 Y | 20 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| 7 | BBG 00 KFWPKH 8 | USOSFR 30 | Curncy | USOSFR 30 Curncy | USD Is ANN VS SOFR 30 Y | 30 | SWAP | ACT/360 | NONE | US | USD | ACTV |

```latex
<span id="cb3-1"><span># Load bond_symbology.xlsx</span></span>
<span id="cb3-2">bond_symbology <span>=</span> pd.read_excel(<span>'bond_symbology.xlsx'</span>)</span>
<span id="cb3-3"></span>
<span id="cb3-4"><span># Set as-of-date</span></span>
<span id="cb3-5">as_of_date <span>=</span> pd.to_datetime(<span>'2024-04-01'</span>)</span>
<span id="cb3-6"></span>
<span id="cb3-7"><span># Add term and TTM columns</span></span>
<span id="cb3-8">bond_symbology[<span>'term'</span>] <span>=</span> (bond_symbology[<span>'maturity'</span>] <span>-</span> bond_symbology[<span>'start_date'</span>]).dt.days <span>/</span> <span>365.25</span></span>
<span id="cb3-9">bond_symbology[<span>'TTM'</span>] <span>=</span> (bond_symbology[<span>'maturity'</span>] <span>-</span> as_of_date).dt.days <span>/</span> <span>365.25</span></span>
<span id="cb3-10"></span>
<span id="cb3-11"><span># Create Govt bonds symbology df</span></span>
<span id="cb3-12">govt_symbology <span>=</span> bond_symbology[(bond_symbology[<span>'class'</span>] <span>==</span> <span>'Govt'</span>) </span>
<span id="cb3-13">                                   <span>&amp;</span> (bond_symbology[<span>'ticker'</span>] <span>==</span> <span>'T'</span>)].copy()</span>
<span id="cb3-14"></span>
<span id="cb3-15"><span># Display govt_symbology</span></span>
<span id="cb3-16">display(govt_symbology.head())</span>
<span id="cb3-17"></span>
```

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | amt_out | country | currency | status | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 329 | T | Govt | BBG 000 DKHP 42 | US 912810 EG 95 | US 9127963 M 90 | T 8 3/4 08/15/20 | US TREASURY N/B | US GOVERNMENT | 8.750 | FIXED | ACT/ACT | 2 | 1 | 1990-08-15 | 1991-02-15 | 1990-08-15 | 2020-08-15 | NORMAL | Unsecured | 17059.0 | US | USD | INAC | 30.001369 | -3.627652 |
| 330 | T | Govt | BBG 000 DJN 4 B 7 | US 912810 EH 78 | NaN | T 7 7/8 02/15/21 | US TREASURY N/B | US GOVERNMENT | 7.875 | FIXED | ACT/ACT | 2 | 1 | 1991-02-15 | 1991-08-15 | 1991-02-15 | 2021-02-15 | NORMAL | Unsecured | 10076.0 | US | USD | INAC | 30.001369 | -3.123888 |
| 331 | T | Govt | BBG 000 DHBM 88 | US 912810 EJ 35 | NaN | T 8 1/8 05/15/21 | US TREASURY N/B | US GOVERNMENT | 8.125 | FIXED | ACT/ACT | 2 | 1 | 1991-05-15 | 1991-11-15 | 1991-05-15 | 2021-05-15 | NORMAL | Unsecured | 10067.0 | US | USD | INAC | 30.001369 | -2.880219 |
| 332 | T | Govt | BBG 000 DKP 182 | US 912810 EK 08 | NaN | T 8 1/8 08/15/21 | US TREASURY N/B | US GOVERNMENT | 8.125 | FIXED | ACT/ACT | 2 | 1 | 1991-08-15 | 1992-02-15 | 1991-08-15 | 2021-08-15 | NORMAL | Unsecured | 9506.0 | US | USD | INAC | 30.001369 | -2.628337 |
| 333 | T | Govt | BBG 000 DFRYP 0 | US 912810 EL 80 | NaN | T 8 11/15/21 | US TREASURY N/B | US GOVERNMENT | 8.000 | FIXED | ACT/ACT | 2 | 1 | 1991-11-15 | 1992-05-15 | 1991-11-15 | 2021-11-15 | NORMAL | Unsecured | 30632.0 | US | USD | INAC | 30.001369 | -2.376454 |

```latex
<span id="cb4-1"><span># 10y cut-off date</span></span>
<span id="cb4-2">cut_off_date_10y <span>=</span> pd.to_datetime(<span>'2014-04-01'</span>)</span>
<span id="cb4-3">govt_symbology_10y <span>=</span> govt_symbology[govt_symbology[<span>'start_date'</span>] <span>&gt;=</span> cut_off_date_10y].copy()</span>
<span id="cb4-4"></span>
<span id="cb4-5"><span># Plot the US Treasury coupons by issue date (last 10 years)</span></span>
<span id="cb4-6">govt_symbology_10y.plot(x<span>=</span><span>'start_date'</span>,  y<span>=</span><span>'coupon'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-*'</span>,  title<span>=</span><span>'US Treasury coupons by issue date (last 10 years)'</span>,  figsize<span>=</span>(<span>12</span>, <span>8</span>))</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-5-output-1.png)

## b. Historical time series of US treasury coupons

Plot the time series of coupons for for US treasury notes/bonds issued in the last 10 years (indexed by issue date). What can you say about the overall level of issued coupons in the last 4 years?

```latex
<span id="cb5-1"><span>import</span> plotly.express <span>as</span> px</span>
<span id="cb5-2"></span>
<span id="cb5-3">fig <span>=</span> px.scatter(govt_symbology_10y,  x<span>=</span><span>'start_date'</span>,  y<span>=</span><span>'coupon'</span>,  title<span>=</span><span>'US Treasury coupons by issue date (last 10 years)'</span>)</span>
<span id="cb5-4">fig.update_layout(xaxis_title<span>=</span><span>'Issue Date'</span>,  yaxis_title<span>=</span><span>'Coupon'</span>,  template<span>=</span><span>'ggplot2'</span>)</span>
<span id="cb5-5">fig.show()</span>
```

```latex
Unable to display output for mime type(s): application/vnd.plotly.v1+json
```

```latex
<span id="cb7-1"><span># 4y cut-off date</span></span>
<span id="cb7-2">cut_off_date_4y <span>=</span> pd.to_datetime(<span>'2020-04-01'</span>)</span>
<span id="cb7-3">govt_symbology_4y <span>=</span> govt_symbology[govt_symbology[<span>'start_date'</span>] <span>&gt;=</span> cut_off_date_4y].copy()</span>
<span id="cb7-4"></span>
<span id="cb7-5"><span># Plot the US Treasury coupons by issue date (last 10 years)</span></span>
<span id="cb7-6">govt_symbology_4y.plot(x<span>=</span><span>'start_date'</span>,  y<span>=</span><span>'coupon'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-*'</span>,  title<span>=</span><span>'US Treasury coupons by issue date (last 4 years)'</span>,  figsize<span>=</span>(<span>12</span>, <span>8</span>))</span>
<span id="cb7-7"></span>
<span id="cb7-8"><span># describe</span></span>
<span id="cb7-9">govt_symbology_4y[[<span>'start_date'</span>,  <span>'coupon'</span>]].describe()</span>
```

|  | start_date | coupon |
| --- | --- | --- |
| count | 239 | 239.000000 |
| mean | 2022-04-11 07:37:54.476987392 | 2.366109 |
| min | 2020-04-15 00:00:00 | 0.125000 |
| 25% | 2021-04-07 12:00:00 | 0.625000 |
| 50% | 2022-04-18 00:00:00 | 2.500000 |
| 75% | 2023-04-08 12:00:00 | 4.000000 |
| max | 2024-04-01 00:00:00 | 5.000000 |
| std | NaN | 1.663802 |

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-7-output-2.png)

What can you say about the overall level of issued coupons in the last 4 years?

Based on the summary statistics provided,  we can make following observations:

- The average (mean) coupon rate is 2.367.
- The median coupon rate (50 th percentile) is 2.5
- The minimum coupon rate is 0.125,  while the maximum is 5.00.
- The coupon rate increased from decade lows of 0.125 in 2020,  to decade highs of 5.00 in 2023.

## c. Load the on-the-run US treasuries

Load the `govt_on_the_run` Excel file into a dataframe. Select the current on-the-run 2 Y,  3 Y,  5 Y,  7 Y,  10 Y,  20 Y and 30 Y issues (off-the-run issues have the B & C suffix). Create a separate symbology dataframe for on-the-run treasuries only,  to be used later on for the on-the-run government yield curve bootstrapping.

```latex
<span id="cb8-1"><span># Load govt_on_the_run,  as of 2024-04-01</span></span>
<span id="cb8-2"></span>
<span id="cb8-3"><span># Keep OTR treasuries only</span></span>
<span id="cb8-4">govt_on_the_run_simple <span>=</span> govt_on_the_run[<span>~</span>govt_on_the_run[<span>'ticker'</span>].<span>str</span>.contains(<span>'B|C'</span>)]</span>
<span id="cb8-5">display(govt_on_the_run_simple)</span>
```

|  | ticker | date | figi | isin |
| --- | --- | --- | --- | --- |
| 0 | GT 10 Govt | 2024-04-19 | BBG 01 L 8 YJFB 3 | US 91282 CJZ 59 |
| 3 | GT 2 Govt | 2024-04-19 | BBG 01 M 44 ZLG 5 | US 91282 CKH 33 |
| 4 | GT 20 Govt | 2024-04-19 | BBG 01 LK 8 Y 0 L 1 | US 912810 TZ 12 |
| 9 | GT 3 Govt | 2024-04-19 | BBG 01 M 9 L 5 M 64 | US 91282 CKJ 98 |
| 10 | GT 30 Govt | 2024-04-19 | BBG 01 L 8 YJKX 8 | US 912810 TX 63 |
| 15 | GT 5 Govt | 2024-04-19 | BBG 01 M 44 ZQJ 1 | US 91282 CKG 59 |
| 18 | GT 7 Govt | 2024-04-19 | BBG 01 M 44 ZS 07 | US 91282 CKF 76 |

```latex
<span id="cb9-1"><span># Create symbology for on-the-run treasuries only</span></span>
<span id="cb9-2">govt_symbology_otr <span>=</span> govt_symbology[govt_symbology[<span>'isin'</span>].isin(govt_on_the_run_simple[<span>'isin'</span>])]</span>
<span id="cb9-3">govt_symbology_otr <span>=</span> govt_symbology_otr.sort_values(by<span>=</span><span>'TTM'</span>)</span>
<span id="cb9-4">display(govt_symbology_otr)</span>
```

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | amt_out | country | currency | status | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 879 | T | Govt | BBG 01 M 44 ZLG 5 | US 91282 CKH 33 | US 91282 CKH 33 | T 4 1/2 03/31/26 | US TREASURY N/B | US GOVERNMENT | 4.500 | FIXED | ACT/ACT | 2 | 1 | 2024-04-01 | 2024-09-30 | 2024-03-31 | 2026-03-31 | NORMAL | Unsecured | 66000.0 | US | USD | ACTV | 1.995893 | 1.995893 |
| 878 | T | Govt | BBG 01 M 44 ZQJ 1 | US 91282 CKG 59 | US 91282 CKG 59 | T 4 1/8 03/31/29 | US TREASURY N/B | US GOVERNMENT | 4.125 | FIXED | ACT/ACT | 2 | 1 | 2024-04-01 | 2024-09-30 | 2024-03-31 | 2029-03-31 | NORMAL | Unsecured | 67000.0 | US | USD | ACTV | 4.996578 | 4.996578 |
| 877 | T | Govt | BBG 01 M 44 ZS 07 | US 91282 CKF 76 | US 91282 CKF 76 | T 4 1/8 03/31/31 | US TREASURY N/B | US GOVERNMENT | 4.125 | FIXED | ACT/ACT | 2 | 1 | 2024-04-01 | 2024-09-30 | 2024-03-31 | 2031-03-31 | NORMAL | Unsecured | 43000.0 | US | USD | ACTV | 6.995209 | 6.995209 |
| 871 | T | Govt | BBG 01 L 8 YJFB 3 | US 91282 CJZ 59 | US 91282 CJZ 59 | T 4 02/15/34 | US TREASURY N/B | US GOVERNMENT | 4.000 | FIXED | ACT/ACT | 2 | 1 | 2024-02-15 | 2024-08-15 | 2024-02-15 | 2034-02-15 | NORMAL | Unsecured | 84104.0 | US | USD | ACTV | 10.001369 | 9.875428 |
| 434 | T | Govt | BBG 01 LK 8 Y 0 L 1 | US 912810 TZ 12 | US 912810 TZ 12 | T 4 1/2 02/15/44 | US TREASURY N/B | US GOVERNMENT | 4.500 | FIXED | ACT/ACT | 2 | 1 | 2024-02-29 | 2024-08-15 | 2024-02-15 | 2044-02-15 | NORMAL | Unsecured | 29684.0 | US | USD | ACTV | 19.961670 | 19.874059 |
| 433 | T | Govt | BBG 01 L 8 YJKX 8 | US 912810 TX 63 | US 912810 TX 63 | T 4 1/4 02/15/54 | US TREASURY N/B | US GOVERNMENT | 4.250 | FIXED | ACT/ACT | 2 | 1 | 2024-02-15 | 2024-08-15 | 2024-02-15 | 2054-02-15 | NORMAL | Unsecured | 48846.0 | US | USD | ACTV | 30.001369 | 29.875428 |

## d. Load and explore US corporate bonds symbology data

Starting from the `bond_symbology` dataframe,  create a corporate bond dataframe containing * bullet/non-callable (mty_typ=“AT MATURITY”),  * senior unsecured (rank = “Sr Unsecured”),  * fixed coupon (cpn_type=“FIXED”)

Bonds only,  with following columns:

| ticker | isin | figi | security | name | coupon | start_date | maturity | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

where * `term` refers to the initial term/time-to-maturity in years * `TTM` refers to the current time-to-maturity in years

Create a separate dataframe for VZ issuer only (ticker = ‘VZ’) and display it.

```latex
<span id="cb10-1"><span># Create Corp bonds symbology df</span></span>
<span id="cb10-2">corp_symbology <span>=</span> bond_symbology[bond_symbology[<span>'class'</span>] <span>==</span> <span>'Corp'</span>].copy()</span>
<span id="cb10-3"></span>
<span id="cb10-4">corp_symbology <span>=</span> corp_symbology[(corp_symbology[<span>'mty_typ'</span>] <span>==</span> <span>'AT MATURITY'</span>) </span>
<span id="cb10-5">                                   <span>&amp;</span> (corp_symbology[<span>'rank'</span>] <span>==</span> <span>'Sr Unsecured'</span>)</span>
<span id="cb10-6">                                   <span>&amp;</span> (corp_symbology[<span>'cpn_type'</span>] <span>==</span> <span>'FIXED'</span>)]</span>
<span id="cb10-7"></span>
<span id="cb10-8"><span># Keep selected columns only</span></span>
<span id="cb10-9">corp_symbology <span>=</span> corp_symbology[[<span>'ticker'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'security'</span>,  <span>'name'</span>,  <span>'coupon'</span>,  <span>'start_date'</span>,  <span>'maturity'</span>,  <span>'term'</span>,  <span>'TTM'</span>]]</span>
<span id="cb10-10"></span>
<span id="cb10-11"><span># Filter for VZ issuer</span></span>
<span id="cb10-12">corp_symbology_vz <span>=</span>  corp_symbology[corp_symbology[<span>'ticker'</span>] <span>==</span> <span>'VZ'</span>]</span>
<span id="cb10-13">corp_symbology_vz <span>=</span> corp_symbology_vz.sort_values(by<span>=</span><span>'TTM'</span>)</span>
<span id="cb10-14"></span>
<span id="cb10-15"><span># Display corp_symbology_vz</span></span>
<span id="cb10-16">display(corp_symbology_vz)</span>
```

|  | ticker | isin | figi | security | name | coupon | start_date | maturity | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 893 | VZ | US 92343 VDD 38 | BBG 00 DGYP 877 | VZ 2 5/8 08/15/26 | VERIZON COMMUNICATIONS | 2.625 | 2016-08-01 | 2026-08-15 | 10.036961 | 2.370979 |
| 898 | VZ | US 92343 VDY 74 | BBG 00 G 6 QW 2 B 8 | VZ 4 1/8 03/16/27 | VERIZON COMMUNICATIONS | 4.125 | 2017-03-16 | 2027-03-16 | 9.998631 | 2.954141 |
| 900 | VZ | US 92343 VER 15 | BBG 00 M 1 BQWX 0 | VZ 4.329 09/21/28 | VERIZON COMMUNICATIONS | 4.329 | 2018-10-22 | 2028-09-21 | 9.916496 | 4.473648 |
| 927 | VZ | US 92344 GAM 87 | BBG 00003 TCX 8 | VZ 7 3/4 12/01/30 | VERIZON COMMUNICATIONS | 7.750 | 2001-09-07 | 2030-12-01 | 29.232033 | 6.666667 |
| 899 | VZ | US 92343 VEA 89 | BBG 00 HC 11 V 79 | VZ 4 1/2 08/10/33 | VERIZON COMMUNICATIONS | 4.500 | 2017-08-10 | 2033-08-10 | 16.000000 | 9.357974 |
| 884 | VZ | US 92343 VBS 25 | BBG 00580 D 503 | VZ 6.4 09/15/33 | VERIZON COMMUNICATIONS | 6.400 | 2013-09-18 | 2033-09-15 | 19.991786 | 9.456537 |
| 928 | VZ | US 92344 GAX 43 | BBG 0000 BH 8 D 4 | VZ 5.85 09/15/35 | VERIZON COMMUNICATIONS | 5.850 | 2005-09-13 | 2035-09-15 | 30.004107 | 11.455168 |
| 889 | VZ | US 92343 VCV 45 | BBG 009 PNV 1 G 8 | VZ 4.272 01/15/36 | VERIZON COMMUNICATIONS | 4.272 | 2015-08-20 | 2036-01-15 | 20.405202 | 11.789185 |
| 896 | VZ | US 92343 VDU 52 | BBG 00 G 6 QW 5 Q 5 | VZ 5 1/4 03/16/37 | VERIZON COMMUNICATIONS | 5.250 | 2017-03-16 | 2037-03-16 | 20.000000 | 12.955510 |
| 880 | VZ | US 92343 VAF 13 | BBG 00000 BHR 9 | VZ 6 1/4 04/01/37 | VERIZON COMMUNICATIONS | 6.250 | 2007-04-03 | 2037-04-01 | 29.995893 | 12.999316 |
| 881 | VZ | US 92343 VAK 08 | BBG 0000 M 1 DD 6 | VZ 6.4 02/15/38 | VERIZON COMMUNICATIONS | 6.400 | 2008-02-12 | 2038-02-15 | 30.009582 | 13.875428 |
| 894 | VZ | US 92343 VDR 24 | BBG 00 GX 2 G 1 Z 5 | VZ 4.812 03/15/39 | VERIZON COMMUNICATIONS | 4.812 | 2017-07-06 | 2039-03-15 | 21.689254 | 14.951403 |
| 882 | VZ | US 92343 VBE 39 | BBG 0027 BCJ 08 | VZ 4 3/4 11/01/41 | VERIZON COMMUNICATIONS | 4.750 | 2011-11-03 | 2041-11-01 | 29.995893 | 17.585216 |
| 885 | VZ | US 92343 VBT 08 | BBG 00580 DD 79 | VZ 6.55 09/15/43 | VERIZON COMMUNICATIONS | 6.550 | 2013-09-18 | 2043-09-15 | 29.990418 | 19.455168 |
| 892 | VZ | US 92343 VDC 54 | BBG 00 DGYPVQ 5 | VZ 4 1/8 08/15/46 | VERIZON COMMUNICATIONS | 4.125 | 2016-08-01 | 2046-08-15 | 30.036961 | 22.370979 |
| 886 | VZ | US 92343 VCK 89 | BBG 0083 CP 3 G 1 | VZ 4.862 08/21/46 | VERIZON COMMUNICATIONS | 4.862 | 2015-03-11 | 2046-08-21 | 31.446954 | 22.387406 |
| 897 | VZ | US 92343 VDV 36 | BBG 00 G 6 QW 816 | VZ 5 1/2 03/16/47 | VERIZON COMMUNICATIONS | 5.500 | 2017-03-16 | 2047-03-16 | 29.998631 | 22.954141 |
| 890 | VZ | US 92343 VCX 01 | BBG 009 PNW 3 Z 2 | VZ 4.522 09/15/48 | VERIZON COMMUNICATIONS | 4.522 | 2015-08-20 | 2048-09-15 | 33.073238 | 24.457221 |
| 895 | VZ | US 92343 VDS 07 | BBG 00 GX 2 GTT 1 | VZ 5.012 04/15/49 | VERIZON COMMUNICATIONS | 5.012 | 2017-07-06 | 2049-04-15 | 31.775496 | 25.037645 |
| 887 | VZ | US 92343 VCM 46 | BBG 0083 CP 816 | VZ 5.012 08/21/54 | VERIZON COMMUNICATIONS | 5.012 | 2015-03-11 | 2054-08-21 | 39.446954 | 30.387406 |
| 891 | VZ | US 92343 VCZ 58 | BBG 009 PNW 578 | VZ 4.672 03/15/55 | VERIZON COMMUNICATIONS | 4.672 | 2015-08-20 | 2055-03-15 | 39.567420 | 30.951403 |

## Problem 2: Explore EOD market prices and yields

## a. Load and explore treasury market prices and yields

Load the `bond_market_prices_eod` Excel file into a dataframe. It provides market data for US treasuries and corporate bonds as of 2024-04-01.

Merge the treasuries symbology dataframe with the market data and add the following columns:

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Plot a graph/scatter plot of treasury mid yields by TTM.

```latex
<span id="cb11-1"><span># Load bond_market_prices_eod</span></span>
<span id="cb11-2"></span>
<span id="cb11-3"></span>
<span id="cb11-4">bond_market_prices_eod[<span>'midPrice'</span>] <span>=</span> <span>0.5</span><span>*</span>(bond_market_prices_eod[<span>'bidPrice'</span>] <span>+</span> bond_market_prices_eod[<span>'askPrice'</span>])</span>
<span id="cb11-5">bond_market_prices_eod[<span>'midYield'</span>] <span>=</span> <span>0.5</span><span>*</span>(bond_market_prices_eod[<span>'bidYield'</span>] <span>+</span> bond_market_prices_eod[<span>'askYield'</span>])</span>
<span id="cb11-6"></span>
<span id="cb11-7">display(bond_market_prices_eod.head())</span>
```

|  | date | class | ticker | isin | figi | bidPrice | askPrice | accrued | bidYield | askYield | midPrice | midYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-04-19 | Corp | IBM | US 459200 KX 88 | BBG 01 DMT 8986 | 97.453 | 97.706 | 0.9635 | 5.248 | 5.173 | 97.5795 | 5.2105 |
| 1 | 2024-04-19 | Corp | IBM | US 459200 GS 40 | BBG 0000 L 5 Z 27 | 99.145 | 99.818 | 2.2245 | 5.683 | 5.617 | 99.4815 | 5.6500 |
| 2 | 2024-04-19 | Corp | GM | US 37046 AFD 28 | BBG 019 LXFPP 4 | 97.075 | 97.556 | 0.5225 | 6.472 | 6.342 | 97.3155 | 6.4070 |
| 3 | 2024-04-19 | Corp | GM | US 37046 AFA 88 | BBG 017 B 6 GFF 0 | 95.012 | 95.453 | 2.1245 | 6.337 | 6.216 | 95.2325 | 6.2765 |
| 4 | 2024-04-19 | Corp | F | US 34540 TZC 97 | BBG 017 QYHT 99 | 98.950 | 99.289 | 2.0675 | 6.419 | 6.298 | 99.1195 | 6.3585 |

```latex
<span id="cb12-1"><span># Merge market data as of 2024-04-01 into treasury symbology</span></span>
<span id="cb12-2">govt_agg <span>=</span> govt_symbology.merge(bond_market_prices_eod,   on<span>=</span>[<span>'class'</span>, <span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb12-3"></span>
<span id="cb12-4">govt_agg.head()</span>
<span id="cb12-5"></span>
<span id="cb12-6"><span># Plot a graph/scatter plot of treasury mid yields by TTM</span></span>
<span id="cb12-7">govt_agg.plot(x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*'</span>,  title<span>=</span><span>'US Treasury Yields by TTM'</span>,  figsize<span>=</span>(<span>12</span>, <span>8</span>))</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-12-output-1.png)

```latex
<span id="cb13-1"><span># Merge market data as of 2024-04-01 into treasury symbology</span></span>
<span id="cb13-2">govt_agg <span>=</span> govt_symbology.merge(bond_market_prices_eod,   on<span>=</span>[<span>'class'</span>, <span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb13-3"></span>
<span id="cb13-4">govt_agg.head()</span>
<span id="cb13-5"></span>
<span id="cb13-6">fig <span>=</span> px.scatter(govt_agg,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>,  title<span>=</span><span>'US Treasury Yields by TTM'</span>)</span>
<span id="cb13-7">fig.update_layout(xaxis_title<span>=</span><span>'Time to Maturity (Years)'</span>,  yaxis_title<span>=</span><span>'Mid Yield'</span>,  template<span>=</span><span>'plotly_white'</span>)</span>
<span id="cb13-8">fig.show()</span>
```

```latex
Unable to display output for mime type(s): application/vnd.plotly.v1+json
```

## b. Explore on-the-run treasuries only

Create a separate joint dataframe for on-the-run treasuries only.

Plot a graph/scatter plot of on-the-run treasury mid yields by TTM.

```latex
<span id="cb15-1"><span># Merge market data as of 2024-04-01 into treasury OTR symbology</span></span>
<span id="cb15-2">govt_agg_otr <span>=</span> govt_symbology_otr.merge(bond_market_prices_eod,   on<span>=</span>[<span>'class'</span>, <span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb15-3"></span>
<span id="cb15-4">fig <span>=</span> px.scatter(govt_agg_otr,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>,  title<span>=</span><span>'OTR US Treasury yields by TTM'</span>)</span>
<span id="cb15-5">fig.update_traces(mode<span>=</span><span>'lines+markers'</span>)</span>
<span id="cb15-6">fig.update_layout(xaxis_title<span>=</span><span>'Time to Maturity (Years)'</span>,  yaxis_title<span>=</span><span>'Mid Yield'</span>,  template<span>=</span><span>'plotly_white'</span>)</span>
<span id="cb15-7">fig.show()</span>
```

```latex
Unable to display output for mime type(s): application/vnd.plotly.v1+json
```

## c. Load and explore corporate bond market prices and yields

Merge the filtered corporate bonds symbology dataframe with the market data and add the following columns:

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

List the unique tickers/issuers available in the dataframe.

```latex
<span id="cb17-1"><span># Merge market data as of 2024-04-01 into corp symbology</span></span>
<span id="cb17-2">corp_agg <span>=</span> corp_symbology.merge(bond_market_prices_eod,   on<span>=</span>[<span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb17-3"></span>
<span id="cb17-4"><span>print</span>(corp_symbology.shape)</span>
<span id="cb17-5"></span>
<span id="cb17-6">display(corp_agg.head())</span>
```

|  | ticker | isin | figi | security | name | coupon | start_date | maturity | term | TTM | date | class | bidPrice | askPrice | accrued | bidYield | askYield | midPrice | midYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | US 037833 AL 42 | BBG 004 HST 0 K 7 | AAPL 3.85 05/04/43 | APPLE INC | 3.850 | 2013-05-03 | 2043-05-04 | 30.001369 | 19.088296 | 2024-04-19 | Corp | 82.155 | 82.733 | 1.8070 | 5.357 | 5.302 | 82.4440 | 5.3295 |
| 1 | AAPL | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | AAPL 4.45 05/06/44 | APPLE INC | 4.450 | 2014-05-06 | 2044-05-06 | 30.001369 | 20.095825 | 2024-04-19 | Corp | 89.955 | 90.676 | 2.0645 | 5.267 | 5.205 | 90.3155 | 5.2360 |
| 2 | AAPL | US 037833 BA 77 | BBG 0081 TNL 50 | AAPL 3.45 02/09/45 | APPLE INC | 3.450 | 2015-02-09 | 2045-02-09 | 30.001369 | 20.859685 | 2024-04-19 | Corp | 75.944 | 76.561 | 0.7095 | 5.387 | 5.328 | 76.2525 | 5.3575 |
| 3 | AAPL | US 037833 BH 21 | BBG 008 N 1 BQC 1 | AAPL 4 3/8 05/13/45 | APPLE INC | 4.375 | 2015-05-13 | 2045-05-13 | 30.001369 | 21.114305 | 2024-04-19 | Corp | 87.214 | 87.825 | 1.9445 | 5.399 | 5.345 | 87.5195 | 5.3720 |
| 4 | DIS | US 254687 DV 52 | BBG 00 QNKP 8 R 8 | DIS 6.55 03/15/33 | WALT DISNEY COMPANY/THE | 6.550 | 2019-11-22 | 2033-03-15 | 13.311431 | 8.952772 | 2024-04-19 | Corp | 109.441 | 110.055 | 0.6910 | 5.209 | 5.127 | 109.7480 | 5.1680 |

```latex
<span id="cb19-1"><span># Unique tickers</span></span>
<span id="cb19-2">corp_agg_unique_tickers <span>=</span> corp_agg[[<span>'ticker'</span>,  <span>'name'</span>]].drop_duplicates()</span>
<span id="cb19-3"></span>
<span id="cb19-4">display(corp_agg_unique_tickers)</span>
```

|  | ticker | name |
| --- | --- | --- |
| 0 | AAPL | APPLE INC |
| 4 | DIS | WALT DISNEY COMPANY/THE |
| 17 | F | FORD MOTOR CREDIT CO LLC |
| 18 | GM | GENERAL MOTORS FINL CO |
| 20 | IBM | IBM CORP |
| 33 | MS | MORGAN STANLEY |
| 42 | ORCL | ORACLE CORP |
| 45 | VZ | VERIZON COMMUNICATIONS |

## d. Yield curve plots

Plot a graph/scatter plot of mid yield curves by TTM (one line per ticker/issuer).

Add a separate line for on-the-run US treasury yield curve (risk free curve).

What can you say about the credit issuer yields,  compared to US treasury yields?

```latex
<span id="cb20-1">fig <span>=</span> px.scatter(corp_agg,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>,  color<span>=</span><span>'ticker'</span>,  title<span>=</span><span>'Corporate Bond Yields by TTM'</span>)</span>
<span id="cb20-2">fig.add_trace(px.scatter(govt_agg_otr,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>).data[<span>0</span>])</span>
<span id="cb20-3">fig.update_traces(mode<span>=</span><span>'lines+markers'</span>)</span>
<span id="cb20-4">fig.update_layout(xaxis_title<span>=</span><span>'Time to Maturity (Years)'</span>,  yaxis_title<span>=</span><span>'Mid Yield'</span>,  template<span>=</span><span>'plotly_white'</span>)</span>
<span id="cb20-5">fig.show()</span>
```

```latex
Unable to display output for mime type(s): application/vnd.plotly.v1+json
```

## Problem 3: Underlying treasury benchmarks and credit spreads

## a. Add underlying benchmark bond mid yields

Start with the corporate bond symbology dataframe. Use the column ‘und_bench_yield’ to identify the underlying benchmark bond for each bond issue.

Add two new columns to the joint corporate bond dataframe:

| und_bench_yield | credit_spread |
| --- | --- |

Where

- `und_bench_yield` = underlying benchmark bond mid yield and
- `credit_spread` = issue yield - underlying benchmark bond mid yield.

```latex
<span id="cb22-1"><span># Use the column 'und_bench_yield' to identify the underlying benchmark bond for each bond issue.</span></span>
<span id="cb22-2">corp_merged <span>=</span> corp_agg.merge(bond_symbology[[<span>'isin'</span>,  <span>'und_bench_isin'</span>]],  on<span>=</span><span>'isin'</span>)</span>
<span id="cb22-3"></span>
<span id="cb22-4"><span># Create df containing govt_benchmark_yields</span></span>
<span id="cb22-5">govt_benchmark_yields <span>=</span> bond_market_prices_eod[bond_market_prices_eod[<span>'class'</span>] <span>==</span> <span>'Govt'</span>][[<span>'isin'</span>,  <span>'midYield'</span>]]</span>
<span id="cb22-6">govt_benchmark_yields.rename(columns<span>=</span>{<span>'midYield'</span>: <span>'und_bench_yield'</span>,  <span>'isin'</span>: <span>'und_bench_isin'</span>},  inplace<span>=</span><span>True</span>)</span>
<span id="cb22-7"></span>
<span id="cb22-8"><span># Add benchmark bond yield</span></span>
<span id="cb22-9">corp_merged <span>=</span> corp_merged.merge(govt_benchmark_yields,  on<span>=</span><span>'und_bench_isin'</span>)</span>
<span id="cb22-10">corp_merged[<span>'credit_spread'</span>] <span>=</span> corp_merged[<span>'midYield'</span>] <span>-</span> corp_merged[<span>'und_bench_yield'</span>]</span>
<span id="cb22-11">display(corp_merged[[<span>'ticker'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'security'</span>,  <span>'und_bench_isin'</span>,  <span>'midYield'</span>,  <span>'und_bench_yield'</span>,  <span>'credit_spread'</span>]])</span>
<span id="cb22-12"></span>
```

|  | ticker | isin | figi | security | und_bench_isin | midYield | und_bench_yield | credit_spread |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | US 037833 AL 42 | BBG 004 HST 0 K 7 | AAPL 3.85 05/04/43 | US 912810 TZ 12 | 5.3295 | 4.8410 | 0.4885 |
| 1 | AAPL | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | AAPL 4.45 05/06/44 | US 912810 TZ 12 | 5.2360 | 4.8410 | 0.3950 |
| 2 | AAPL | US 037833 BA 77 | BBG 0081 TNL 50 | AAPL 3.45 02/09/45 | US 912810 TZ 12 | 5.3575 | 4.8410 | 0.5165 |
| 3 | AAPL | US 037833 BH 21 | BBG 008 N 1 BQC 1 | AAPL 4 3/8 05/13/45 | US 912810 TZ 12 | 5.3720 | 4.8410 | 0.5310 |
| 4 | DIS | US 254687 DV 52 | BBG 00 QNKP 8 R 8 | DIS 6.55 03/15/33 | US 91282 CJZ 59 | 5.1680 | 4.6220 | 0.5460 |
| … | … | … | … | … | … | … | … | … |
| 65 | VZ | US 92344 GAX 43 | BBG 0000 BH 8 D 4 | VZ 5.85 09/15/35 | US 91282 CJZ 59 | 5.5755 | 4.6220 | 0.9535 |
| 66 | DIS | USU 25497 AR 66 | BBG 00 N 3 BD 9 G 0 | DIS 7 1/8 04/08/28 | US 91282 CKG 59 | 5.3415 | 4.6710 | 0.6705 |
| 67 | DIS | USU 25497 AW 51 | BBG 00 N 3 BZ 921 | DIS 8.45 08/01/34 | US 91282 CJZ 59 | 5.5975 | 4.6220 | 0.9755 |
| 68 | DIS | USU 25497 BM 60 | BBG 00 N 55 NLL 7 | DIS 7.9 12/01/2095 | US 912810 TV 08 | 6.1400 | 4.7105 | 1.4295 |
| 69 | DIS | USU 25497 BN 44 | BBG 00 N 55 NPV 7 | DIS 8 1/4 10/17/2096 | US 912810 TV 08 | 6.1660 | 4.7105 | 1.4555 |

70 rows × 8 columns

## b. Credit spread curve plots

Plot a graph/scatter plot of credit spread curves by TTM (one line per issuer).

```latex
<span id="cb23-1">fig <span>=</span> px.scatter(corp_merged,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'credit_spread'</span>,  color<span>=</span><span>'ticker'</span>,  title<span>=</span><span>'Corporate Bond Credit Spreads by TTM'</span>)</span>
<span id="cb23-2">fig.update_traces(mode<span>=</span><span>'lines+markers'</span>) </span>
<span id="cb23-3">fig. Update_layout (xaxis_title<span>=</span><span>'Time to Maturity (Years)'</span>,  yaxis_title<span>=</span><span>'Credit Spread'</span>,  template<span>=</span><span>'plotly_white'</span>)</span>
<span id="cb23-4">fig.Show ()</span>
```

```latex
Unable to display output for mime type (s): application/vnd. Plotly. V 1+json
```

## c. Add g-spreads

Add two new columns to the joint corporate bond dataframe:

| interp_tsy_yield | g_spread |
| --- | --- |

Where

- `interp_tsy_yield` = interpolated treasury yield (using on-the-run treasuries only),  matching the issue maturity
- `g_spread` = issue yield - interp_tsy_yield.

```latex
<span id="cb25-1"><span># Interpolate OTR Treasury yields on corporate bond TTMs</span></span>
<span id="cb25-2">interp_tsy_yield_vec <span>=</span> np.Interp (corp_merged[<span>'TTM'</span>],  govt_agg_otr[<span>'TTM'</span>],  govt_agg_otr[<span>'midYield'</span>])</span>
<span id="cb25-3"></span>
<span id="cb25-4"><span># Add interp_tsy_yield and g_spread</span></span>
<span id="cb25-5">corp_merged[<span>'interp_tsy_yield'</span>] <span>=</span> interp_tsy_yield_vec</span>
<span id="cb25-6">corp_merged[<span>'g_spread'</span>] <span>=</span> corp_merged[<span>'midYield'</span>] <span>-</span> corp_merged[<span>'interp_tsy_yield'</span>]</span>
<span id="cb25-7"></span>
<span id="cb25-8"><span># Display results</span></span>
<span id="cb25-9">display (corp_merged [[<span>'ticker'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'security'</span>,  <span>'und_bench_isin'</span>,  <span>'midYield'</span>,  <span>'und_bench_yield'</span>,  <span>'credit_spread'</span>,  <span>'interp_tsy_yield'</span>,  <span>'g_spread'</span>]])</span>
```

|  | ticker | isin | figi | security | und_bench_isin | midYield | und_bench_yield | credit_spread | interp_tsy_yield | g_spread |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | US 037833 AL 42 | BBG 004 HST 0 K 7 | AAPL 3.85 05/04/43 | US 912810 TZ 12 | 5.3295 | 4.8410 | 0.4885 | 4.823789 | 0.505711 |
| 1 | AAPL | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | AAPL 4.45 05/06/44 | US 912810 TZ 12 | 5.2360 | 4.8410 | 0.3950 | 4.838151 | 0.397849 |
| 2 | AAPL | US 037833 BA 77 | BBG 0081 TNL 50 | AAPL 3.45 02/09/45 | US 912810 TZ 12 | 5.3575 | 4.8410 | 0.5165 | 4.828336 | 0.529164 |
| 3 | AAPL | US 037833 BH 21 | BBG 008 N 1 BQC 1 | AAPL 4 3/8 05/13/45 | US 912810 TZ 12 | 5.3720 | 4.8410 | 0.5310 | 4.825065 | 0.546935 |
| 4 | DIS | US 254687 DV 52 | BBG 00 QNKP 8 R 8 | DIS 6.55 03/15/33 | US 91282 CJZ 59 | 5.1680 | 4.6220 | 0.5460 | 4.631770 | 0.536230 |
| … | … | … | … | … | … | … | … | … | … | … |
| 65 | VZ | US 92344 GAX 43 | BBG 0000 BH 8 D 4 | VZ 5.85 09/15/35 | US 91282 CJZ 59 | 5.5755 | 4.6220 | 0.9535 | 4.656601 | 0.918899 |
| 66 | DIS | USU 25497 AR 66 | BBG 00 N 3 BD 9 G 0 | DIS 7 1/8 04/08/28 | US 91282 CKG 59 | 5.3415 | 4.6710 | 0.6705 | 4.773931 | 0.567569 |
| 67 | DIS | USU 25497 AW 51 | BBG 00 N 3 BZ 921 | DIS 8.45 08/01/34 | US 91282 CJZ 59 | 5.5975 | 4.6220 | 0.9755 | 4.632015 | 0.965485 |
| 68 | DIS | USU 25497 BM 60 | BBG 00 N 55 NLL 7 | DIS 7.9 12/01/2095 | US 912810 TV 08 | 6.1400 | 4.7105 | 1.4295 | 4.712500 | 1.427500 |
| 69 | DIS | USU 25497 BN 44 | BBG 00 N 55 NPV 7 | DIS 8 1/4 10/17/2096 | US 912810 TV 08 | 6.1660 | 4.7105 | 1.4555 | 4.712500 | 1.453500 |

70 rows × 10 columns

## d. G-spread curve plots

Plot a graph/scatter plot of g-spread curves by TTM (one line per issuer).

```latex
<span id="cb26-1">fig <span>=</span> px.Scatter (corp_merged,  x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'g_spread'</span>,  color<span>=</span><span>'ticker'</span>,  title<span>=</span><span>'Corporate Bond G-Spreads by TTM'</span>)</span>
<span id="cb26-2">fig. Update_traces (mode<span>=</span><span>'lines+markers'</span>)</span>
<span id="cb26-3">fig. Update_layout (xaxis_title<span>=</span><span>'Time to Maturity (Years)'</span>,  yaxis_title<span>=</span><span>'G-Spread'</span>,  template<span>=</span><span>'plotly_white'</span>) </span>
<span id="cb26-4">fig.Show ()</span>
```

```latex
Unable to display output for mime type (s): application/vnd. Plotly. V 1+json
```

## Problem 4: Explore sections 1 to 5 in the QuantLib example notebook

Explore sections 1 to 5 in the example notebook and identify concepts discussed in the first lecture. Collect open questions for the upcoming TA Review session on the analytics library.

Find the ‘ORCL 2.95 04/01/30’ bond (mentioned on page 12 in Session 1) in the bond symbology file. Create the corresponding fixed rate bond object and display the future cashflows. Do you match the cashflows displayed on page 13?

Going forward,  we will be using QuantLib for curve calibration (US Treasury + SOFR),  as well as pricing and risk of various cash and synthetic credit instruments.

```latex
<span id="cb28-1"><span># Find the 'ORCL 2.95 04/01/30' bond in bond symbology</span></span>
<span id="cb28-2">corp_symbology_orcl <span>=</span> bond_symbology[bond_symbology[<span>'security'</span>] <span>==</span> <span>'ORCL 2.95 04/01/30'</span>]</span>
<span id="cb28-3"></span>
<span id="cb28-4">display (corp_symbology_orcl.Transpose ())</span>
```

|  | 312 |
| --- | --- |
| ticker | ORCL |
| class | Corp |
| figi | BBG 00 SXGDGF 0 |
| isin | US 68389 XBV 64 |
| und_bench_isin | US 91282 CKG 59 |
| security | ORCL 2.95 04/01/30 |
| name | ORACLE CORP |
| type | GLOBAL |
| coupon | 2.95 |
| cpn_type | FIXED |
| dcc | 30/360 |
| cpn_freq | 2 |
| days_settle | 2 |
| start_date | 2020-04-01 00:00:00 |
| cpn_first | 2020-10-01 00:00:00 |
| acc_first | 2020-04-01 00:00:00 |
| maturity | 2030-04-01 00:00:00 |
| mty_typ | CALLABLE |
| rank | Sr Unsecured |
| amt_out | 3250.0 |
| country | US |
| currency | USD |
| status | ACTV |
| term | 9.998631 |
| TTM | 5.998631 |

```latex
<span id="cb29-1"><span># Construct fixed rate cashflow schedule for ORCL 2.95 04/01/30</span></span>
<span id="cb29-2"></span>
<span id="cb29-3">issue_date <span>=</span> ql.Date (<span>1</span>,  <span>4</span>,  <span>2020</span>)        <span># 2020-04-01</span></span>
<span id="cb29-4">maturity_date <span>=</span> ql.Date (<span>1</span>,  <span>4</span>,  <span>2030</span>)     <span># 2030-04-01</span></span>
<span id="cb29-5"></span>
<span id="cb29-6">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb29-7">coupon_term <span>=</span> ql.Period (coupon_freq)</span>
<span id="cb29-8">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb29-9">day_count_conv <span>=</span> ql. Unadjusted</span>
<span id="cb29-10">date_generation <span>=</span> ql. DateGeneration. Backward</span>
<span id="cb29-11">month_end <span>=</span> <span>True</span></span>
<span id="cb29-12"></span>
<span id="cb29-13"><span># fixed_rate_schedule</span></span>
<span id="cb29-14">fixed_rate_schedule <span>=</span> ql.Schedule (issue_date, </span>
<span id="cb29-15">                       maturity_date, </span>
<span id="cb29-16">                       coupon_term, </span>
<span id="cb29-17">                       calendar, </span>
<span id="cb29-18">                       day_count_conv, </span>
<span id="cb29-19">                       day_count_conv, </span>
<span id="cb29-20">                       date_generation, </span>
<span id="cb29-21">                       month_end)</span>
```

```latex
<span id="cb30-1"><span># Construct corporate bond object for ORCL 2.95 04/01/30</span></span>
<span id="cb30-2"></span>
<span id="cb30-3"><span># day_count: 30/360 for fixed-rate Corp bonds</span></span>
<span id="cb30-4">day_count <span>=</span> ql. Thirty 360 (ql. Thirty 360. USA)</span>
<span id="cb30-5"></span>
<span id="cb30-6"><span># settlement_days: 2 for Corp Bonds</span></span>
<span id="cb30-7">settlement_days <span>=</span> <span>2</span></span>
<span id="cb30-8"></span>
<span id="cb30-9"><span># coupons</span></span>
<span id="cb30-10">coupon_rate <span>=</span> <span>0.295</span>     <span># 2.95%</span></span>
<span id="cb30-11">coupons <span>=</span> [coupon_rate]</span>
<span id="cb30-12"></span>
<span id="cb30-13"><span># payment_convention</span></span>
<span id="cb30-14">payment_convention <span>=</span> ql. Unadjusted</span>
<span id="cb30-15"></span>
<span id="cb30-16"><span># face_value</span></span>
<span id="cb30-17">face_value <span>=</span> <span>100</span></span>
<span id="cb30-18"></span>
<span id="cb30-19"></span>
<span id="cb30-20"><span># Construct the fixed_rate_bond</span></span>
<span id="cb30-21">face_value <span>=</span> <span>100</span></span>
<span id="cb30-22">fixed_rate_bond <span>=</span> ql.FixedRateBond (</span>
<span id="cb30-23">    settlement_days, </span>
<span id="cb30-24">    face_value, </span>
<span id="cb30-25">    fixed_rate_schedule, </span>
<span id="cb30-26">    coupons, </span>
<span id="cb30-27">    day_count, </span>
<span id="cb30-28">    payment_convention)</span>
```

```latex
<span id="cb31-1"><span># Display the contractual cashflows. </span></span>
<span id="cb31-2">x <span>=</span> [(cf.Date (). To_date (),  cf.Amount ()) <span>for</span> cf <span>in</span> fixed_rate_bond.Cashflows ()]</span>
<span id="cb31-3">cf_date_fixed,  cf_amount <span>=</span> <span>zip</span>(<span>*</span>x)</span>
<span id="cb31-4">fixed_rate_bond_cashflows <span>=</span> pd.DataFrame (data<span>=</span>{<span>'CashFlowDate'</span>: cf_date_fixed,  <span>'CashFlowAmount'</span>: cf_amount})</span>
<span id="cb31-5"></span>
<span id="cb31-6"><span># Cashflows match the ones displayed on page 13 (from Bloomberg CSHF screenshot),  up to the face value multiplier.</span></span>
<span id="cb31-7">display (fixed_rate_bond_cashflows)</span>
```

|  | CashFlowDate | CashFlowAmount |
| --- | --- | --- |
| 0 | 2020-10-01 | 14.75 |
| 1 | 2021-04-01 | 14.75 |
| 2 | 2021-10-01 | 14.75 |
| 3 | 2022-04-01 | 14.75 |
| 4 | 2022-10-01 | 14.75 |
| 5 | 2023-04-01 | 14.75 |
| 6 | 2023-10-01 | 14.75 |
| 7 | 2024-04-01 | 14.75 |
| 8 | 2024-10-01 | 14.75 |
| 9 | 2025-04-01 | 14.75 |
| 10 | 2025-10-01 | 14.75 |
| 11 | 2026-04-01 | 14.75 |
| 12 | 2026-10-01 | 14.75 |
| 13 | 2027-04-01 | 14.75 |
| 14 | 2027-10-01 | 14.75 |
| 15 | 2028-04-01 | 14.75 |
| 16 | 2028-10-01 | 14.75 |
| 17 | 2029-04-01 | 14.75 |
| 18 | 2029-10-01 | 14.75 |
| 19 | 2030-04-01 | 14.75 |
| 20 | 2030-04-01 | 100.00 |

---

## From file: 2 UChicago_FINM_35700_CreditMarkets_Spring 2024_Examples_QuantLib_Basics

## Credit Markets

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

- Alex Popovici
- alex.popovici@uchicago.edu

## Basic Usage of QuantLib analytics library

## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1. Objects and Handles
	- 1. Define a quote object and inspect the value
	- 2. Define quoteHandle as a handle/smart pointer to the quote object

	- 3. Calendars and day-count conventions
- 2. Cashflow Schedules
	- 1. Construct semi-annual cashflow schedule object,  for fixed-rate bonds
	- 2. Inspect the semi-annual cashflow schedule
	- 3. Construct quarterly cashflow schedule object,  for floating-rate bonds
	- 4. Inspect the quarterly cashflow schedule
- 3. Discount Curve / Yield Curve Term Structure
	- 1. Constructing a Flat Yield Curve
	- 2. Inspect the discount curve
- 4. Fixed and Floating Rate Bonds
	- 1. Constructing a fixed rate bond object
	- 2. Investigate the fixed-rate bond cash-flows
	- 3. Constructing a floating rate bond object: linked to SOFR index
- 5. Bond Present Value Calculation (no credit risk)
	- 1. Direct function call using risk-free bond pricing engine
	- 2. Manual Calculation to validate PV (for fixed and floating-rate bonds)
	- 3. Bond Clean vs Dirty Prices (adjusted to settle date)
- 6. Market Data Scenarios
	- 1. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices
	- 2. Compute scenario DV 01,  duration and convexity
	- 3. Yield to Price conversions
	- 4. Price to Yield conversions
- 7. Analytical Duration,  Convexity and Z-Spread (flat yield model)
	- 1. Compute bond duration,  convexity and Z-Spread

	- 2. Validate Z-Spread
- 8. Treasury Yield Curve Calibration (via Bootstrapping)
	- 1. Calibrate treasury flat yield curve (simple case of one calibration instrument)
	- 2. Display the calibrated Treasury discount curve dataframe
	- 3. Plot the calibrated Treasury Zero Rates and Discount Factors curves
	- 4. Reprice the bond on the yield curve to validate the calibration

```latex
<span id="cb32-1"><span>import</span> QuantLib <span>as</span> ql</span>
<span id="cb32-2"><span>import</span> numpy <span>as</span> np</span>
<span id="cb32-3"><span>import</span> pandas <span>as</span> pd</span>
```

## 1. Objects and Handles

## a. Define a quote object and inspect the value

```latex
<span id="cb33-1">quote <span>=</span> ql.SimpleQuote (<span>0.\1</span>)</span>
<span id="cb33-2"><span>print</span>(quote.Value ())</span>
<span id="cb33-3"></span>
<span id="cb33-4">quote.SetValue (<span>0.\1</span>)</span>
<span id="cb33-5"><span>print</span>(quote.Value ())</span>
```

## b. Define quoteHandle as a handle/smart pointer to the quote object

```latex
<span id="cb35-1">quoteHandle <span>=</span> ql.QuoteHandle (quote)</span>
<span id="cb35-2">quoteHandle.Value ()</span>
```

### When the quote object is changed,  the quoteHandle changes value as well

```latex
<span id="cb37-1">quote.SetValue (<span>0.\1</span>)</span>
<span id="cb37-2">quoteHandle.Value ()</span>
```

## c. Calendars and day-count conventions

```latex
<span id="cb39-1"><span># dates</span></span>
<span id="cb39-2">todays_date <span>=</span> ql.Date.TodaysDate ()</span>
<span id="cb39-3">test_date <span>=</span> todays_date <span>+</span> <span>90</span></span>
<span id="cb39-4"><span>print</span>(<span>'todays_date ='</span>,  todays_date)</span>
<span id="cb39-5"><span>print</span>(<span>'test_date ='</span>,  test_date)</span>
<span id="cb39-6"></span>
<span id="cb39-7"></span>
<span id="cb39-8"><span># calendars</span></span>
<span id="cb39-9">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb39-10">holiday_list <span>=</span> <span>list</span>(calendar.HolidayList (todays_date,  test_date))</span>
<span id="cb39-11"><span>print</span>(<span>'holiday_list ='</span>,  holiday_list)</span>
<span id="cb39-12"></span>
<span id="cb39-13"></span>
<span id="cb39-14"><span># day count conventions</span></span>
<span id="cb39-15">day_count <span>=</span> ql. Actual 360 ()</span>
<span id="cb39-16"><span>print</span>(<span>'day_count ='</span>,  day_count)</span>
<span id="cb39-17"></span>
<span id="cb39-18"><span># year fractions</span></span>
<span id="cb39-19">test_year_fraction <span>=</span> day_count.YearFraction (todays_date,  test_date)</span>
<span id="cb39-20"><span>print</span>(<span>'Year Fraction  from'</span>,  todays_date,  <span>'to'</span>,  test_date, <span>'] ='</span>,  test_year_fraction)</span>
```

```latex
Todays_date = October 6 th,  2024
Test_date = January 4 th,  2025
Holiday_list = [Date (14, 10, 2024),  Date (11, 11, 2024),  Date (28, 11, 2024),  Date (25, 12, 2024),  Date (1, 1, 2025)]
Day_count = Actual/360 day counter
Year Fraction  from October 6 th,  2024 to January 4 th,  2025 ] = 0.25
Todays_date = October 6 th,  2024
Test_date = January 4 th,  2025
Holiday_list = [Date (14, 10, 2024),  Date (11, 11, 2024),  Date (28, 11, 2024),  Date (25, 12, 2024),  Date (1, 1, 2025)]
Day_count = Actual/360 day counter
Year Fraction  from October 6 th,  2024 to January 4 th,  2025 ] = 0.25
```

## 2. Cashflow Schedules

## a. Construct semi-annual cashflow schedule object,  for fixed-rate bonds

```latex
<span id="cb41-1">issue_date <span>=</span> ql.Date (<span>2</span>,  <span>4</span>,  <span>2024</span>)        <span># 2024-04-02</span></span>
<span id="cb41-2">maturity_date <span>=</span> ql.Date (<span>2</span>,  <span>4</span>,  <span>2028</span>)     <span># 2028-04-02</span></span>
<span id="cb41-3">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb41-4">coupon_term <span>=</span> ql.Period (coupon_freq)</span>
<span id="cb41-5">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb41-6">day_count_conv <span>=</span> ql. Unadjusted</span>
<span id="cb41-7">date_generation <span>=</span> ql. DateGeneration. Backward</span>
<span id="cb41-8">month_end <span>=</span> <span>True</span></span>
<span id="cb41-9"></span>
<span id="cb41-10"><span># fixed_rate_schedule</span></span>
<span id="cb41-11">fixed_rate_schedule <span>=</span> ql.Schedule (issue_date, </span>
<span id="cb41-12">                       maturity_date, </span>
<span id="cb41-13">                       coupon_term, </span>
<span id="cb41-14">                       calendar, </span>
<span id="cb41-15">                       day_count_conv, </span>
<span id="cb41-16">                       day_count_conv, </span>
<span id="cb41-17">                       date_generation, </span>
<span id="cb41-18">                       month_end)</span>
```

## b. Inspect the semi-annual cashflow schedule

- Use list () to get a list of all the dates in Schedule,  and len () to get number of dates
- Use ] for random access
- use startDate (),  endDate ()

```latex
<span id="cb42-1"><span>print</span>(<span>"All dates: "</span>,  <span>list</span>(fixed_rate_schedule))</span>
<span id="cb42-2"><span>print</span>(<span>"Length: "</span>,  <span>len</span>(fixed_rate_schedule))</span>
<span id="cb42-3"><span>print</span>(<span>"The 3 rd coupon date: "</span>,  [fixed_rate_schedule])  <span># random access</span></span>
<span id="cb42-4"><span>print</span>(<span>"Start Date: "</span>,  fixed_rate_schedule.StartDate ())</span>
<span id="cb42-5"><span>print</span>(<span>"End Date: "</span>,  fixed_rate_schedule.EndDate ())</span>
```

```latex
All dates:  [Date (2, 4, 2024),  Date (2, 10, 2024),  Date (2, 4, 2025),  Date (2, 10, 2025),  Date (2, 4, 2026),  Date (2, 10, 2026),  Date (2, 4, 2027),  Date (2, 10, 2027),  Date (2, 4, 2028)]
Length:  9
The 3 rd coupon date:  [&lt; QuantLib. QuantLib. Schedule; proxy of &lt; Swig Object of type 'Schedule *' at 0 x 3073 ef 540&gt; &gt;]
Start Date:  April 2 nd,  2024
End Date:  April 2 nd,  2028
All dates:  [Date (2, 4, 2024),  Date (2, 10, 2024),  Date (2, 4, 2025),  Date (2, 10, 2025),  Date (2, 4, 2026),  Date (2, 10, 2026),  Date (2, 4, 2027),  Date (2, 10, 2027),  Date (2, 4, 2028)]
Length:  9
The 3 rd coupon date:  [&lt; QuantLib. QuantLib. Schedule; proxy of &lt; Swig Object of type 'Schedule *' at 0 x 3073 ef 540&gt; &gt;]
Start Date:  April 2 nd,  2024
End Date:  April 2 nd,  2028
```

## c. Construct quarterly cashflow schedule object,  for floating-rate bonds

```latex
<span id="cb44-1"><span># floating_rate_bond_schedule</span></span>
<span id="cb44-2">floating_rate_schedule <span>=</span> ql.Schedule (</span>
<span id="cb44-3">    issue_date, </span>
<span id="cb44-4">    maturity_date, </span>
<span id="cb44-5">    ql.Period (ql. Quarterly), </span>
<span id="cb44-6">    calendar, </span>
<span id="cb44-7">    day_count_conv, </span>
<span id="cb44-8">    day_count_conv, </span>
<span id="cb44-9">    date_generation, </span>
<span id="cb44-10">    month_end, </span>
<span id="cb44-11">)</span>
```

## d. Inspect the quarterly cashflow schedule

```latex
<span id="cb45-1"><span>print</span>(<span>"All dates: "</span>,  <span>list</span>(floating_rate_schedule))</span>
<span id="cb45-2"><span>print</span>(<span>"Length: "</span>,  <span>len</span>(floating_rate_schedule))</span>
<span id="cb45-3"><span>print</span>(<span>"Start Date: "</span>,  fixed_rate_schedule.StartDate ())</span>
<span id="cb45-4"><span>print</span>(<span>"End Date: "</span>,  fixed_rate_schedule.EndDate ())</span>
```

```latex
All dates:  [Date (2, 4, 2024),  Date (2, 7, 2024),  Date (2, 10, 2024),  Date (2, 1, 2025),  Date (2, 4, 2025),  Date (2, 7, 2025),  Date (2, 10, 2025),  Date (2, 1, 2026),  Date (2, 4, 2026),  Date (2, 7, 2026),  Date (2, 10, 2026),  Date (2, 1, 2027),  Date (2, 4, 2027),  Date (2, 7, 2027),  Date (2, 10, 2027),  Date (2, 1, 2028),  Date (2, 4, 2028)]
Length:  17
Start Date:  April 2 nd,  2024
End Date:  April 2 nd,  2028
All dates:  [Date (2, 4, 2024),  Date (2, 7, 2024),  Date (2, 10, 2024),  Date (2, 1, 2025),  Date (2, 4, 2025),  Date (2, 7, 2025),  Date (2, 10, 2025),  Date (2, 1, 2026),  Date (2, 4, 2026),  Date (2, 7, 2026),  Date (2, 10, 2026),  Date (2, 1, 2027),  Date (2, 4, 2027),  Date (2, 7, 2027),  Date (2, 10, 2027),  Date (2, 1, 2028),  Date (2, 4, 2028)]
Length:  17
Start Date:  April 2 nd,  2024
End Date:  April 2 nd,  2028
```

## 3. Discount Curve / Yield Curve Term Structure

## a. Constructing a Flat Yield Curve

```latex
<span id="cb47-1"><span># Set the static valuation date: 2024-04-02</span></span>
<span id="cb47-2">calc_date <span>=</span> ql.Date (<span>2</span>,  <span>4</span>,  <span>2024</span>)</span>
<span id="cb47-3">ql.Settings.Instance (). EvaluationDate <span>=</span> calc_date</span>
<span id="cb47-4"></span>
<span id="cb47-5"><span># using 5% flat interest rate for testing</span></span>
<span id="cb47-6">flat_rate <span>=</span> ql.SimpleQuote (<span>0.05</span>)</span>
<span id="cb47-7">rate_handle <span>=</span> ql.QuoteHandle (flat_rate)</span>
<span id="cb47-8">day_count <span>=</span> ql. Actual 360 ()</span>
<span id="cb47-9">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb47-10">continuous_comp <span>=</span> ql. Continuous <span># continously compounded rate of 5%</span></span>
<span id="cb47-11">flat_yield_curve <span>=</span> ql.FlatForward (calc_date,  rate_handle,  day_count,  continuous_comp)</span>
<span id="cb47-12">flat_yield_curve_handle <span>=</span> ql.YieldTermStructureHandle (flat_yield_curve)</span>
```

## b. Inspect the discount curve

```latex
<span id="cb48-1">ref_date <span>=</span> flat_yield_curve.ReferenceDate ()</span>
<span id="cb48-2">test_date <span>=</span> ql.Date (<span>30</span>,  <span>6</span>,  <span>2025</span>)</span>
<span id="cb48-3"></span>
<span id="cb48-4"><span># calc year fraction between ref_date and test_date</span></span>
<span id="cb48-5">yearFrac <span>=</span> flat_yield_curve.DayCounter (). YearFraction (ref_date,  test_date)</span>
<span id="cb48-6"></span>
<span id="cb48-7"><span>print</span>(<span>"Reference Date ="</span>,  ref_date)</span>
<span id="cb48-8"><span>print</span>(<span>"Test Date ="</span>,  test_date)</span>
<span id="cb48-9"><span>print</span>(<span>"Year Fraction between Reference Date and Test Date : "</span>,  yearFrac)</span>
<span id="cb48-10"><span>print</span>(<span>"Discount Factor for Test Date"</span>,  test_date,  <span>": "</span>,  flat_yield_curve.Discount (test_date))</span>
<span id="cb48-11"><span>print</span>(<span>"custom DF calculation for Test Date"</span>,  test_date,  <span>": "</span>,  np.Exp (<span>-</span>flat_rate.Value () <span>*</span> yearFrac))</span>
<span id="cb48-12"><span>print</span>(<span>"Difference in Discount Factor: "</span>,  flat_yield_curve.Discount (test_date) <span>-</span> np.Exp (<span>-</span>flat_rate.Value () <span>*</span> yearFrac))</span>
<span id="cb48-13"></span>
```

```latex
Reference Date = April 2 nd,  2024
Test Date = June 30 th,  2025
Year Fraction between Reference Date and Test Date :  1.261111111111111
Discount Factor for Test Date June 30 th,  2025 :  0.9388913116117773
Custom DF calculation for Test Date June 30 th,  2025 :  0.9388913116117772
Difference in Discount Factor: 1.1102230246251565 e-16
Reference Date = April 2 nd,  2024
Test Date = June 30 th,  2025
Year Fraction between Reference Date and Test Date :  1.261111111111111
Discount Factor for Test Date June 30 th,  2025 :  0.9388913116117773
Custom DF calculation for Test Date June 30 th,  2025 :  0.9388913116117772
Difference in Discount Factor: 1.1102230246251565 e-16
```

## 4. Fixed and Floating Rate Bonds

## a. Constructing a fixed rate bond object

```latex
<span id="cb50-1"><span># day_count: ACT/ACT for Govt bonds</span></span>
<span id="cb50-2">day_count_govt <span>=</span> ql.ActualActual (ql. ActualActual. ISMA)</span>
<span id="cb50-3"></span>
<span id="cb50-4"><span># day_count: 30/360 for fixed-rate Corp bonds</span></span>
<span id="cb50-5">day_count_corp_fixed <span>=</span> ql. Thirty 360 (ql. Thirty 360. USA)</span>
<span id="cb50-6"></span>
<span id="cb50-7"><span># day_count: ACT/360 for floating-rate bonds</span></span>
<span id="cb50-8">day_count_floater <span>=</span> ql. Actual 360 ()</span>
<span id="cb50-9"></span>
<span id="cb50-10"></span>
<span id="cb50-11"><span># settlement_days: 1 for Govt bonds</span></span>
<span id="cb50-12">settlement_days_govt <span>=</span> <span>1</span></span>
<span id="cb50-13"></span>
<span id="cb50-14"><span># settlement_days: 2 for Corp Bonds</span></span>
<span id="cb50-15">settlement_days_corp <span>=</span> <span>2</span></span>
<span id="cb50-16"></span>
<span id="cb50-17"><span># Govt Bonds specs</span></span>
<span id="cb50-18">day_count <span>=</span> day_count_govt</span>
<span id="cb50-19">settlement_days <span>=</span> settlement_days_govt</span>
<span id="cb50-20"></span>
<span id="cb50-21"><span># coupons</span></span>
<span id="cb50-22">coupon_rate <span>=</span> <span>0.04</span></span>
<span id="cb50-23">coupons <span>=</span> [coupon_rate]</span>
<span id="cb50-24"></span>
<span id="cb50-25"><span># payment_convention</span></span>
<span id="cb50-26">payment_convention <span>=</span> ql. Unadjusted</span>
<span id="cb50-27"></span>
<span id="cb50-28"><span># face_value</span></span>
<span id="cb50-29">face_value <span>=</span> <span>100</span></span>
<span id="cb50-30"></span>
<span id="cb50-31"></span>
<span id="cb50-32"><span># Construct the fixed_rate_bond</span></span>
<span id="cb50-33">face_value <span>=</span> <span>100</span></span>
<span id="cb50-34">fixed_rate_bond <span>=</span> ql.FixedRateBond (</span>
<span id="cb50-35">    settlement_days, </span>
<span id="cb50-36">    face_value, </span>
<span id="cb50-37">    fixed_rate_schedule, </span>
<span id="cb50-38">    coupons, </span>
<span id="cb50-39">    day_count, </span>
<span id="cb50-40">    payment_convention)</span>
```

## b. Investigate the fixed-rate bond cash-flows

```latex
<span id="cb51-1">x <span>=</span> [(cf.Date (),  cf.Amount ()) <span>for</span> cf <span>in</span> fixed_rate_bond.Cashflows ()]</span>
<span id="cb51-2">cf_date_fixed,  cf_amount <span>=</span> <span>zip</span>(<span>*</span>x)</span>
<span id="cb51-3">cf_frame_fixed <span>=</span> pd.DataFrame (data<span>=</span>{<span>'CashFlowDate'</span>: cf_date_fixed,  <span>'CashFlowAmount'</span>: cf_amount})</span>
<span id="cb51-4">display (cf_frame_fixed)</span>
```

|  | CashFlowDate | CashFlowAmount |
| --- | --- | --- |
| 0 | October 2 nd,  2024 | 2.0 |
| 1 | April 2 nd,  2025 | 2.0 |
| 2 | October 2 nd,  2025 | 2.0 |
| 3 | April 2 nd,  2026 | 2.0 |
| 4 | October 2 nd,  2026 | 2.0 |
| 5 | April 2 nd,  2027 | 2.0 |
| 6 | October 2 nd,  2027 | 2.0 |
| 7 | April 2 nd,  2028 | 2.0 |
| 8 | April 2 nd,  2028 | 100.0 |

## c. Constructing a floating rate bond object: linked to SOFR index

```latex
<span id="cb52-1"><span># sofr_term_structure_handle: using 5% flat interest rate for testing</span></span>
<span id="cb52-2">rate_handle <span>=</span> ql.QuoteHandle (ql.SimpleQuote (<span>5</span><span>/</span><span>100</span>))</span>
<span id="cb52-3">sofr_term_structure <span>=</span> ql.FlatForward (calc_date,  rate_handle,  day_count_floater,  ql. Continuous)</span>
<span id="cb52-4">sofr_term_structure_handle <span>=</span> ql.YieldTermStructureHandle (sofr_term_structure)</span>
<span id="cb52-5"></span>
<span id="cb52-6"><span># Set SOFR index history</span></span>
<span id="cb52-7">im <span>=</span> ql.IndexManager.Instance ()</span>
<span id="cb52-8">sofr_index <span>=</span> ql.Sofr (sofr_term_structure_handle)</span>
<span id="cb52-9"></span>
<span id="cb52-10"><span># Set SOFR fixings</span></span>
<span id="cb52-11">im.ClearHistory (sofr_index.Name ())</span>
<span id="cb52-12">sofr_index.AddFixing (ql.Date (<span>28</span>,  ql. March,  <span>2024</span>),  <span>5</span><span>/</span><span>100</span>)</span>
<span id="cb52-13">sofr_index.AddFixing (ql.Date (<span>1</span>,  ql. April,  <span>2024</span>),  <span>5</span><span>/</span><span>100</span>)</span>
<span id="cb52-14"></span>
<span id="cb52-15"></span>
<span id="cb52-16"><span># floating_rate_bond</span></span>
<span id="cb52-17">floating_rate_bond <span>=</span> ql.FloatingRateBond (settlement_days, </span>
<span id="cb52-18">                                face_value, </span>
<span id="cb52-19">                                floating_rate_schedule, </span>
<span id="cb52-20">                                sofr_index, </span>
<span id="cb52-21">                                day_count_floater, </span>
<span id="cb52-22">                                payment_convention, </span>
<span id="cb52-23">                                spreads<span>=</span>[<span>25</span><span>/</span><span>10000</span>],  <span># 25 bps floating rate</span></span>
<span id="cb52-24">                                issueDate<span>=</span>issue_date)</span>
```

```latex
<span id="cb53-1">x <span>=</span> [(cf.Date (),  cf.Amount ()) <span>for</span> cf <span>in</span> floating_rate_bond.Cashflows ()]</span>
<span id="cb53-2">cf_date_float,  cf_amount <span>=</span> <span>zip</span>(<span>*</span>x)</span>
<span id="cb53-3">cf_frame_float <span>=</span> pd.DataFrame (data<span>=</span>{<span>'CashFlowDate'</span>: cf_date_float,  <span>'CashFlowAmount'</span>: cf_amount})</span>
<span id="cb53-4">display (cf_frame_float)</span>
```

|  | CashFlowDate | CashFlowAmount |
| --- | --- | --- |
| 0 | July 2 nd,  2024 | 1.335104 |
| 1 | October 2 nd,  2024 | 1.349865 |
| 2 | January 2 nd,  2025 | 1.349865 |
| 3 | April 2 nd,  2025 | 1.320345 |
| 4 | July 2 nd,  2025 | 1.335104 |
| 5 | October 2 nd,  2025 | 1.349865 |
| 6 | January 2 nd,  2026 | 1.349865 |
| 7 | April 2 nd,  2026 | 1.320345 |
| 8 | July 2 nd,  2026 | 1.335104 |
| 9 | October 2 nd,  2026 | 1.349865 |
| 10 | January 2 nd,  2027 | 1.350044 |
| 11 | April 2 nd,  2027 | 1.320520 |
| 12 | July 2 nd,  2027 | 1.335104 |
| 13 | October 2 nd,  2027 | 1.350044 |
| 14 | January 2 nd,  2028 | 1.350044 |
| 15 | April 2 nd,  2028 | 1.335370 |
| 16 | April 2 nd,  2028 | 100.000000 |

## 5. Bond Present Value Calculation (no credit risk)

## a. Direct function call using risk-free bond pricing engine

```latex
<span id="cb54-1"><span># fixed_rate_bond PV</span></span>
<span id="cb54-2">bond_engine <span>=</span> ql.DiscountingBondEngine (flat_yield_curve_handle)</span>
<span id="cb54-3">fixed_rate_bond.SetPricingEngine (bond_engine)</span>
<span id="cb54-4">fixed_rate_bond_pv <span>=</span> fixed_rate_bond.NPV ()</span>
<span id="cb54-5"><span>print</span>(<span>'fixed_rate_bond_pv ='</span>,  fixed_rate_bond_pv)</span>
<span id="cb54-6"></span>
<span id="cb54-7"><span># floating_rate_bond PV</span></span>
<span id="cb54-8">floating_rate_bond.SetPricingEngine (bond_engine)</span>
<span id="cb54-9">floating_rate_bond_pv <span>=</span> floating_rate_bond.NPV ()</span>
<span id="cb54-10"><span>print</span>(<span>'floating_rate_bond_pv ='</span>,  floating_rate_bond_pv)</span>
```

```latex
Fixed_rate_bond_pv = 95.93321956659715
Floating_rate_bond_pv = 100.91327849916415
Fixed_rate_bond_pv = 95.93321956659715
Floating_rate_bond_pv = 100.91327849916415
```

## b. Manual Calculation to validate PV (for fixed and floating-rate bonds)

```latex
<span id="cb56-1"><span># Validate fixed-rate bond PV</span></span>
<span id="cb56-2">used_cf_frame <span>=</span> cf_frame_fixed</span>
<span id="cb56-3">used_bond_pv <span>=</span> fixed_rate_bond_pv</span>
<span id="cb56-4"></span>
<span id="cb56-5"><span># Validate floating-rate bond PV</span></span>
<span id="cb56-6">discount_yearfrac <span>=</span> np.Zeros ((<span>len</span>(used_cf_frame, )))</span>
<span id="cb56-7">discount_factor <span>=</span> np.Zeros ((<span>len</span>(used_cf_frame, )))</span>
<span id="cb56-8"></span>
<span id="cb56-9">i <span>=</span> <span>0</span></span>
<span id="cb56-10"><span>for</span> cf_date <span>in</span> used_cf_frame[<span>'CashFlowDate'</span>]:</span>
<span id="cb56-11">    discount_yearfrac[i] <span>=</span> flat_yield_curve.DayCounter (). YearFraction (flat_yield_curve.ReferenceDate (),  cf_date)</span>
<span id="cb56-12">    discount_factor[i] <span>=</span> flat_yield_curve.Discount (cf_date)</span>
<span id="cb56-13">    i <span>+=</span> <span>1</span></span>
<span id="cb56-14"></span>
<span id="cb56-15">used_cf_frame[<span>'YearFrac'</span>] <span>=</span> discount_yearfrac</span>
<span id="cb56-16">used_cf_frame[<span>'DiscountFactor'</span>] <span>=</span> discount_factor</span>
<span id="cb56-17">used_cf_frame[<span>'NPV'</span>] <span>=</span> used_cf_frame[<span>'CashFlowAmount'</span>] <span>*</span> used_cf_frame[<span>'DiscountFactor'</span>]</span>
<span id="cb56-18"></span>
<span id="cb56-19">used_cf_frame</span>
```

|  | CashFlowDate | CashFlowAmount | YearFrac | DiscountFactor | NPV |
| --- | --- | --- | --- | --- | --- |
| 0 | October 2 nd,  2024 | 2.0 | 0.508333 | 0.974904 | 1.949807 |
| 1 | April 2 nd,  2025 | 2.0 | 1.013889 | 0.950569 | 1.901138 |
| 2 | October 2 nd,  2025 | 2.0 | 1.522222 | 0.926713 | 1.853426 |
| 3 | April 2 nd,  2026 | 2.0 | 2.027778 | 0.903582 | 1.807163 |
| 4 | October 2 nd,  2026 | 2.0 | 2.536111 | 0.880905 | 1.761810 |
| 5 | April 2 nd,  2027 | 2.0 | 3.041667 | 0.858917 | 1.717833 |
| 6 | October 2 nd,  2027 | 2.0 | 3.550000 | 0.837361 | 1.674722 |
| 7 | April 2 nd,  2028 | 2.0 | 4.058333 | 0.816346 | 1.632693 |
| 8 | April 2 nd,  2028 | 100.0 | 4.058333 | 0.816346 | 81.634627 |

```latex
<span id="cb57-1">pv_manual <span>=</span> used_cf_frame[<span>'NPV'</span>].<span>sum</span>()</span>
<span id="cb57-2"><span>print</span>(<span>'NPV engine = '</span>,  used_bond_pv)</span>
<span id="cb57-3"><span>print</span>(<span>'NPV manual = '</span>,  pv_manual)</span>
<span id="cb57-4"><span>print</span>(<span>'NPV diff = '</span>,  pv_manual <span>-</span> used_bond_pv)</span>
```

```latex
NPV engine =  95.93321956659715
NPV manual =  95.93321956659715
NPV diff =  0.0
NPV engine =  95.93321956659715
NPV manual =  95.93321956659715
NPV diff =  0.0
```

## c. Bond Clean vs Dirty Prices (adjusted to settle date)

```latex
<span id="cb59-1"><span>print</span>(<span>'Bond Notional = '</span>,  fixed_rate_bond.Notional ())</span>
<span id="cb59-2"><span>print</span>(<span>'Settle Date = '</span>,  fixed_rate_bond.SettlementDate ())</span>
<span id="cb59-3"><span>print</span>(<span>'Discount Factor to Settle Date = '</span>,  <span>round</span>(flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),  <span>4</span>))</span>
<span id="cb59-4"><span>print</span>(<span>'Bond NPV (Calc Date) = '</span>,  <span>round</span>(fixed_rate_bond.NPV (),  <span>4</span>))</span>
<span id="cb59-5"><span>print</span>(<span>'Bond NPV Adjusted to Settle Date = '</span>,  <span>round</span>(fixed_rate_bond.NPV () <span>/</span> flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),  <span>4</span>))</span>
<span id="cb59-6"><span>print</span>(<span>'Bond Dirty Price = '</span>,  <span>round</span>(fixed_rate_bond.DirtyPrice (),  <span>4</span>))</span>
<span id="cb59-7"><span>print</span>(<span>'Bond Clean Price = '</span>,  <span>round</span>(fixed_rate_bond.CleanPrice (),  <span>4</span>))</span>
<span id="cb59-8"><span>print</span>(<span>'Bond Accrued = '</span>,  <span>round</span>(fixed_rate_bond.AccruedAmount (),  <span>4</span>))</span>
```

```latex
Bond Notional =  100.0
Settle Date =  April 3 rd,  2024
Discount Factor to Settle Date =  0.9999
Bond NPV (Calc Date) =  95.9332
Bond NPV Adjusted to Settle Date =  95.9465
Bond Dirty Price =  95.9465
Bond Clean Price =  95.9356
Bond Accrued =  0.0109
Bond Notional =  100.0
Settle Date =  April 3 rd,  2024
Discount Factor to Settle Date =  0.9999
Bond NPV (Calc Date) =  95.9332
Bond NPV Adjusted to Settle Date =  95.9465
Bond Dirty Price =  95.9465
Bond Clean Price =  95.9356
Bond Accrued =  0.0109
```

## 6. Market Data Scenarios

## a. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices

```latex
<span id="cb61-1"><span># start with interest_rate_bump = 0</span></span>
<span id="cb61-2">interest_rate_bump <span>=</span> ql.SimpleQuote (<span>0.0</span>)</span>
<span id="cb61-3">flat_yield_curve_bumped <span>=</span> ql.ZeroSpreadedTermStructure (flat_yield_curve_handle,  ql.QuoteHandle (interest_rate_bump))</span>
<span id="cb61-4"></span>
<span id="cb61-5">bond_engine <span>=</span> ql.DiscountingBondEngine (ql.YieldTermStructureHandle (flat_yield_curve_bumped))</span>
<span id="cb61-6">fixed_rate_bond.SetPricingEngine (bond_engine)</span>
<span id="cb61-7"></span>
<span id="cb61-8">price_base <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb61-9"></span>
<span id="cb61-10"><span># Original price (zero interest rate bump)</span></span>
<span id="cb61-11"><span>print</span>(<span>"Price (base case): "</span>,  <span>round</span>(price_base,  <span>4</span>))</span>
<span id="cb61-12"></span>
<span id="cb61-13"><span># Bump interest rate by +1 bps (parallel shift)</span></span>
<span id="cb61-14">interest_rate_bump.SetValue (<span>0.0001</span>)</span>
<span id="cb61-15">price_up_1 bp <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb61-16"><span>print</span>(<span>"Price in +1 bps scenario: "</span>,  <span>round</span>(price_up_1 bp,  <span>4</span>))</span>
<span id="cb61-17"><span>print</span>(<span>"Price diff in +1 bps scenario: "</span>,  <span>round</span>(price_up_1 bp <span>-</span> price_base,  <span>6</span>))</span>
<span id="cb61-18"></span>
<span id="cb61-19"><span># Bump interest rate by -1 bps (parallel shift)</span></span>
<span id="cb61-20">interest_rate_bump.SetValue (<span>-</span><span>0.0001</span>)</span>
<span id="cb61-21">price_down_1 bp <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb61-22"><span>print</span>(<span>"Price for -1 bps scenario: "</span>,  <span>round</span>(price_down_1 bp,  <span>4</span>))</span>
<span id="cb61-23"><span>print</span>(<span>"Price diff in -1 bps scenario: "</span>,  <span>round</span>(price_down_1 bp <span>-</span> price_base,  <span>6</span>))</span>
<span id="cb61-24"></span>
<span id="cb61-25"> <span># Remove interest rate bump</span></span>
<span id="cb61-26">interest_rate_bump.SetValue (<span>0</span>)</span>
<span id="cb61-27"></span>
```

```latex
Price (base case):  95.9356
Price in +1 bps scenario:  95.8993
Price diff in +1 bps scenario:  -0.036268
Price for -1 bps scenario: 95.9719
Price diff in -1 bps scenario:  0.036283
Price (base case):  95.9356
Price in +1 bps scenario:  95.8993
Price diff in +1 bps scenario:  -0.036268
Price for -1 bps scenario: 95.9719
Price diff in -1 bps scenario:  0.036283
```

## b. Compute scenario DV 01,  duration and convexity

```latex
<span id="cb63-1"><span># Compute scenario delta/gamma sensitivities</span></span>
<span id="cb63-2">dv 01 <span>=</span> <span>round</span>((price_down_1 bp <span>-</span> price_base) <span>*</span> <span>1 e 4</span> <span>/</span> <span>100</span>,  <span>4</span>)</span>
<span id="cb63-3">duration <span>=</span> <span>round</span>(dv 01 <span>/</span> fixed_rate_bond.DirtyPrice () <span>*</span> <span>100</span>,  <span>4</span>)</span>
<span id="cb63-4">gamma_1 bp <span>=</span> (price_down_1 bp <span>-</span> <span>2</span><span>*</span>price_base <span>+</span> price_up_1 bp) <span>*</span> <span>1 e 8</span> <span>/</span> <span>100</span></span>
<span id="cb63-5">convexity <span>=</span> <span>round</span>(gamma_1 bp <span>/</span> fixed_rate_bond.DirtyPrice () <span>*</span> <span>100</span>,  <span>4</span>)</span>
<span id="cb63-6"></span>
<span id="cb63-7"><span>print</span>(<span>"DV 01: "</span>,  dv 01)</span>
<span id="cb63-8"><span>print</span>(<span>"Duration: "</span>,  duration)</span>
<span id="cb63-9"><span>print</span>(<span>"Convexity: "</span>,  convexity)</span>
<span id="cb63-10"></span>
<span id="cb63-11"></span>
```

```latex
DV 01:  3.6283
Duration:  3.7816
Convexity:  14.9262
DV 01:  3.6283
Duration:  3.7816
Convexity:  14.9262
```

## c. Yield to Price conversions

```latex
<span id="cb65-1"><span># Use original interest rate yield of 5%</span></span>
<span id="cb65-2"><span># flat_rate.SetValue (0.05)</span></span>
<span id="cb65-3"><span>print</span>(<span>'Bond PV for'</span>,  flat_rate.Value ()<span>*</span><span>100</span>,  <span>'pct yield: '</span>,  <span>round</span>(fixed_rate_bond.NPV (),  <span>4</span>))</span>
<span id="cb65-4"></span>
<span id="cb65-5"></span>
<span id="cb65-6"><span># Change interest rate yield to 6% and recompute bond PV</span></span>
<span id="cb65-7">flat_rate.SetValue (<span>0.06</span>)</span>
<span id="cb65-8"><span>print</span>(<span>'Bond PV for'</span>,  flat_rate.Value ()<span>*</span><span>100</span>,  <span>'pct yield: '</span>,  <span>round</span>(fixed_rate_bond.NPV (),  <span>4</span>))</span>
<span id="cb65-9"></span>
<span id="cb65-10"><span># Set interest rate yield back to 5%</span></span>
<span id="cb65-11">flat_rate.SetValue (<span>0.05</span>)</span>
```

```latex
Bond PV for 5.0 pct yield: 95.9332
Bond PV for 6.0 pct yield: 92.3743
Bond PV for 5.0 pct yield: 95.9332
Bond PV for 6.0 pct yield: 92.3743
```

## d. Price to Yield conversions

```latex
<span id="cb67-1"><span># bond_market_price = fixed_rate_bond.CleanPrice ()</span></span>
<span id="cb67-2">bond_market_price <span>=</span> <span>95.00</span>   <span># Clean market price</span></span>
<span id="cb67-3"></span>
<span id="cb67-4">compounding <span>=</span> ql. Compounded</span>
<span id="cb67-5"><span># compounding = ql. Continuous</span></span>
<span id="cb67-6"></span>
<span id="cb67-7">settle_date <span>=</span> fixed_rate_bond.SettlementDate (calc_date)</span>
<span id="cb67-8">day_counter <span>=</span> fixed_rate_bond.DayCounter ()</span>
<span id="cb67-9"></span>
<span id="cb67-10"><span>print</span>(<span>'day_counter ='</span>,  day_counter)</span>
<span id="cb67-11"><span>print</span>(<span>'coupon_freq ='</span>,  coupon_freq)</span>
<span id="cb67-12"><span>print</span>(<span>'calc_date ='</span>,  calc_date)</span>
<span id="cb67-13"><span>print</span>(<span>'settle_date ='</span>,  settle_date)</span>
<span id="cb67-14"></span>
<span id="cb67-15"></span>
<span id="cb67-16">implied_yield <span>=</span> fixed_rate_bond.BondYield (bond_market_price,  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>100</span></span>
<span id="cb67-17"><span>print</span>(<span>'implied_yield ='</span>,  <span>round</span>(implied_yield,  <span>4</span>))</span>
```

```latex
Day_counter = Actual/Actual (ISMA) day counter
Coupon_freq = 2
Calc_date = April 2 nd,  2024
Settle_date = April 3 rd,  2024
Implied_yield = 5.4076
Day_counter = Actual/Actual (ISMA) day counter
Coupon_freq = 2
Calc_date = April 2 nd,  2024
Settle_date = April 3 rd,  2024
Implied_yield = 5.4076
```

## 7. Analytical Duration,  Convexity and Z-Spread (flat yield model)

## a. Compute bond duration,  convexity and Z-Spread

```latex
<span id="cb69-1"><span># flat_bond_yield (used as an input to compute duration and convexity)</span></span>
<span id="cb69-2">flat_bond_yield <span>=</span> <span>5.5</span> <span># in pct</span></span>
<span id="cb69-3">flat_bond_yield_rate <span>=</span> ql.InterestRate (flat_bond_yield<span>/</span><span>100</span>,  day_count,  compounding,  coupon_freq)</span>
<span id="cb69-4"></span>
<span id="cb69-5"><span># Calc Duration and Convexity</span></span>
<span id="cb69-6">bond_duration <span>=</span> ql.BondFunctions.Duration (fixed_rate_bond,  flat_bond_yield_rate)</span>
<span id="cb69-7">bond_convexity <span>=</span> ql.BondFunctions.Convexity (fixed_rate_bond,  flat_bond_yield_rate)</span>
<span id="cb69-8"></span>
<span id="cb69-9"><span># Calc z-spread for a given market price</span></span>
<span id="cb69-10">bond_market_price <span>=</span> <span>95.3194</span>     <span># Clean market price,  implies zero Z-Spread!</span></span>
<span id="cb69-11">bond_market_price <span>=</span> <span>95</span>          <span># Test market price,  implies Z-Spread &gt; 0</span></span>
<span id="cb69-12">bond_zspread <span>=</span> ql.BondFunctions.ZSpread (fixed_rate_bond,  bond_market_price,  flat_yield_curve,  day_count,  compounding,  coupon_freq,  settle_date)</span>
<span id="cb69-13"></span>
<span id="cb69-14"><span># Print results</span></span>
<span id="cb69-15"><span>print</span>(<span>'Bond Duration ='</span>,  <span>round</span>(bond_duration,  <span>4</span>))</span>
<span id="cb69-16"><span>print</span>(<span>'Bond Convexity ='</span>,  <span>round</span>(bond_convexity,  <span>4</span>))</span>
<span id="cb69-17"><span>print</span>(<span>'Bond Z-Spread bps ='</span>,  <span>round</span>(bond_zspread <span>*</span> <span>10000</span>,  <span>4</span>))</span>
```

```latex
Bond Duration = 3.6247
Bond Convexity = 15.4882
Bond Z-Spread bps = 26.5978
Bond Duration = 3.6247
Bond Convexity = 15.4882
Bond Z-Spread bps = 26.5978
```

## b. Validate Z-Spread

```latex
<span id="cb71-1"><span>def</span> calc_clean_price_with_zspread (fixed_rate_bond,  yield_curve_handle,  zspread):</span>
<span id="cb71-2">    zspread_quote <span>=</span> ql.SimpleQuote (zspread)</span>
<span id="cb71-3">    zspread_quote_handle <span>=</span> ql.QuoteHandle (zspread_quote)</span>
<span id="cb71-4">    yield_curve_bumped <span>=</span> ql.ZeroSpreadedTermStructure (yield_curve_handle,  zspread_quote_handle,  ql. Compounded,  ql. Semiannual)</span>
<span id="cb71-5">    yield_curve_bumped_handle <span>=</span> ql.YieldTermStructureHandle (yield_curve_bumped)</span>
<span id="cb71-6">    </span>
<span id="cb71-7">    <span># Set Valuation engine</span></span>
<span id="cb71-8">    bond_engine <span>=</span> ql.DiscountingBondEngine (yield_curve_bumped_handle)</span>
<span id="cb71-9">    fixed_rate_bond.SetPricingEngine (bond_engine)</span>
<span id="cb71-10">    bond_clean_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb71-11">    <span>return</span> bond_clean_price</span>
```

```latex
<span id="cb72-1"><span># Compare the original and the z-spread computed clean prices</span></span>
<span id="cb72-2">bond_zspread_price <span>=</span> calc_clean_price_with_zspread (fixed_rate_bond,  flat_yield_curve_handle,  bond_zspread)</span>
<span id="cb72-3"></span>
<span id="cb72-4"><span>print</span>(<span>'Bond Z-Spread bps ='</span>,  <span>round</span>(bond_zspread <span>*</span> <span>10000</span>,  <span>2</span>))</span>
<span id="cb72-5"><span>print</span>(<span>'bond_market_price ='</span>,  bond_market_price)</span>
<span id="cb72-6"><span>print</span>(<span>'bond_zspread_price ='</span>,  bond_zspread_price)</span>
<span id="cb72-7"><span>print</span>(<span>'bond price diff ='</span>,  bond_zspread_price <span>-</span> bond_market_price)</span>
```

```latex
Bond Z-Spread bps = 26.6
Bond_market_price = 95
Bond_zspread_price = 94.99999999999486
Bond price diff = -5.144329406903125 e-12
Bond Z-Spread bps = 26.6
Bond_market_price = 95
Bond_zspread_price = 94.99999999999486
Bond price diff = -5.144329406903125 e-12
```

## 8. Treasury Yield Curve Calibration (via Bootstrapping)

## a. Calibrate treasury flat yield curve (simple case of one calibration instrument)

```latex
<span id="cb74-1"><span># fixed_rate_bond: 4% coupon and 2028-04-02 maturity</span></span>
<span id="cb74-2"></span>
<span id="cb74-3"><span># clean price quote</span></span>
<span id="cb74-4">tsy_clean_price_quote <span>=</span> <span>96.0</span></span>
<span id="cb74-5">tsy_clean_price_handle <span>=</span> ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))</span>
<span id="cb74-6"></span>
<span id="cb74-7"></span>
<span id="cb74-8"><span># Create BondHelper object</span></span>
<span id="cb74-9">bond_helper <span>=</span> ql.BondHelper (</span>
<span id="cb74-10">    tsy_clean_price_handle, </span>
<span id="cb74-11">    fixed_rate_bond)</span>
<span id="cb74-12"></span>
<span id="cb74-13">bond_helper_list <span>=</span> [bond_helper]</span>
<span id="cb74-14">        </span>
<span id="cb74-15">tsy_flat_yield_curve <span>=</span> ql.PiecewiseLogCubicDiscount (calc_date,  bond_helper_list,  day_count)</span>
<span id="cb74-16">tsy_flat_yield_curve.EnableExtrapolation ()</span>
<span id="cb74-17"></span>
<span id="cb74-18">tsy_yield_curve_handle <span>=</span> ql.YieldTermStructureHandle (tsy_flat_yield_curve)</span>
```

## b. Display the calibrated Treasury discount curve dataframe

```latex
<span id="cb75-1"><span>def</span> get_yield_curve_details_df (yield_curve,  curve_dates<span>=</span><span>None</span>):</span>
<span id="cb75-2">    </span>
<span id="cb75-3">    <span>if</span>(curve_dates <span>==</span> <span>None</span>):</span>
<span id="cb75-4">        curve_dates <span>=</span> yield_curve.Dates ()</span>
<span id="cb75-5"></span>
<span id="cb75-6">    dates <span>=</span> [d.to_date () <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb75-7">    discounts <span>=</span> [<span>round</span>(yield_curve.Discount (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb75-8">    yearfracs <span>=</span> [<span>round</span>(yield_curve.TimeFromReference (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb75-9">    zeroRates <span>=</span> [<span>round</span>(yield_curve.ZeroRate (d,  yield_curve.DayCounter (),  ql. Compounded). Rate () <span>*</span> <span>100</span>,  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb75-10"></span>
<span id="cb75-11">    yield_curve_details_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Date'</span>: dates, </span>
<span id="cb75-12">                             <span>'YearFrac'</span>: yearfracs, </span>
<span id="cb75-13">                             <span>'DiscountFactor'</span>: discounts, </span>
<span id="cb75-14">                             <span>'ZeroRate'</span>: zeroRates})                             </span>
<span id="cb75-15">    <span>return</span> yield_curve_details_df</span>
```

```latex
<span id="cb76-1"><span># Display Treasury yield curve details</span></span>
<span id="cb76-2">tsy_flat_yield_curve_simple_df <span>=</span> get_yield_curve_details_df (tsy_flat_yield_curve)                  <span># using calibration grid</span></span>
<span id="cb76-3">display (tsy_flat_yield_curve_simple_df)</span>
<span id="cb76-4"></span>
<span id="cb76-5">grid_dates <span>=</span> [tsy_flat_yield_curve.ReferenceDate () <span>+</span> ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> <span>list</span>(<span>range</span>(<span>0</span>, <span>30</span>, <span>2</span>))]</span>
<span id="cb76-6">tsy_flat_yield_curve_details_df <span>=</span> get_yield_curve_details_df (tsy_flat_yield_curve,  grid_dates)    <span># using external grid</span></span>
<span id="cb76-7">display (tsy_flat_yield_curve_details_df)</span>
```

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-02 | 0.0 | 1.000 | 5.185 |
| 1 | 2028-04-02 | 4.0 | 0.817 | 5.185 |

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-02 | 0.0 | 1.000 | 5.185 |
| 1 | 2026-04-02 | 2.0 | 0.904 | 5.185 |
| 2 | 2028-04-02 | 4.0 | 0.817 | 5.185 |
| 3 | 2030-04-02 | 6.0 | 0.738 | 5.185 |
| 4 | 2032-04-02 | 8.0 | 0.667 | 5.185 |
| 5 | 2034-04-02 | 10.0 | 0.603 | 5.185 |
| 6 | 2036-04-02 | 12.0 | 0.545 | 5.185 |
| 7 | 2038-04-02 | 14.0 | 0.493 | 5.185 |
| 8 | 2040-04-02 | 16.0 | 0.445 | 5.185 |
| 9 | 2042-04-02 | 18.0 | 0.403 | 5.185 |
| 10 | 2044-04-02 | 20.0 | 0.364 | 5.185 |
| 11 | 2046-04-02 | 22.0 | 0.329 | 5.185 |
| 12 | 2048-04-02 | 24.0 | 0.297 | 5.185 |
| 13 | 2050-04-02 | 26.0 | 0.269 | 5.185 |
| 14 | 2052-04-02 | 28.0 | 0.243 | 5.185 |

## c. Plot the calibrated Treasury Zero Rates and Discount Factors curves

```latex
<span id="cb77-1">plt <span>=</span> tsy_flat_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'ZeroRate'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'Treasury Flat Curve: Zero Rates'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb77-2">plt. Set_ylabel (<span>'Zero Rate (%)'</span>)</span>
<span id="cb77-3">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb77-4"></span>
<span id="cb77-5">plt <span>=</span> tsy_flat_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'DiscountFactor'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'Treasury Flat Curve: Discount Factors'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb77-6">plt. Set_ylabel (<span>'Discount Factors'</span>)</span>
<span id="cb77-7">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-55-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-55-output-3.png)

## d. Reprice the bond on the yield curve to validate the calibration

```latex
<span id="cb79-1"><span># 1. Price risk-free bond</span></span>
<span id="cb79-2">risk_free_bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_handle)</span>
<span id="cb79-3"></span>
<span id="cb79-4">fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)</span>
<span id="cb79-5">risk_free_bond_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb79-6">risk_free_bond_yield <span>=</span> fixed_rate_bond.BondYield (risk_free_bond_price,  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>100</span></span>
<span id="cb79-7"></span>
<span id="cb79-8"><span>print</span>(<span>'tsy_clean_price_quote: '</span>,  tsy_clean_price_quote)</span>
<span id="cb79-9"><span>print</span>(<span>'risk_free_bond_price: '</span>,  risk_free_bond_price)</span>
<span id="cb79-10"><span>print</span>(<span>'price_calibration_error: '</span>,  risk_free_bond_price<span>-</span>tsy_clean_price_quote)</span>
<span id="cb79-11"><span>print</span>(<span>'risk_free_bond_yield: '</span>,  risk_free_bond_yield)</span>
```

```latex
Tsy_clean_price_quote: 96.0
Risk_free_bond_price: 96.0
Price_calibration_error: 0.0
Risk_free_bond_yield: 5.119227409362794
Tsy_clean_price_quote: 96.0
Risk_free_bond_price: 96.0
Price_calibration_error: 0.0
Risk_free_bond_yield: 5.119227409362794
```

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

### Due Date: 2024-04-16

- Alex Popovici
- alex.popovici@uchicago.edu

This homework relies on:

- the corporate and government bonds symbology file `bond_symbology`,
- the “on-the-run” treasuries data file `govt_on_the_run`,
- the bond market data file `bond_market_prices_eod`,  containing EOD price data as of 2024-04-08.

## Problem 1: Constructing fixed rate bonds

```latex
<span id="cb81-1"><span>import</span> QuantLib <span>as</span> ql</span>
<span id="cb81-2"><span>import</span> pandas <span>as</span> pd</span>
<span id="cb81-3"><span>import</span> datetime <span>as</span> dt</span>
<span id="cb81-4"></span>
<span id="cb81-5"><span># Use static calculation/valuation date of 2024-04-08,  matching data available in the market prices EOD file</span></span>
<span id="cb81-6">calc_date <span>=</span> ql.Date (<span>8</span>,  <span>4</span>,  <span>2024</span>)</span>
<span id="cb81-7">ql.Settings.Instance (). EvaluationDate <span>=</span> calc_date</span>
```

## a. Prepare the symbology and market data files for fixed rate government and corporate bonds

Load the `bond_symbology`,  `bond_market_prices_eod` and `govt_on_the_run` Excel files into dataframes.

Filter the symbology frame for fixed rate bonds only (cpn_type=“FIXED”).

```latex
<span id="cb82-1"><span># Set as-of-date</span></span>
<span id="cb82-2">as_of_date <span>=</span> pd. To_datetime (<span>'2024-04-08'</span>)</span>
<span id="cb82-3"></span>
<span id="cb82-4"><span># Load bond_symbology. Xlsx</span></span>
<span id="cb82-5"></span>
<span id="cb82-6">bond_symbology  <span>=</span> bond_symbology[bond_symbology[<span>'cpn_type'</span>] <span>==</span> <span>'FIXED'</span>]</span>
<span id="cb82-7"></span>
<span id="cb82-8"><span># Add term and TTM columns</span></span>
<span id="cb82-9">bond_symbology[<span>'term'</span>] <span>=</span> (bond_symbology[<span>'maturity'</span>] <span>-</span> bond_symbology[<span>'start_date'</span>]). Dt. Days <span>/</span> <span>365.25</span></span>
<span id="cb82-10">bond_symbology[<span>'TTM'</span>] <span>=</span> (bond_symbology[<span>'maturity'</span>] <span>-</span> as_of_date). Dt. Days <span>/</span> <span>365.25</span></span>
<span id="cb82-11">display (bond_symbology.Head ())</span>
<span id="cb82-12"></span>
<span id="cb82-13"></span>
<span id="cb82-14"><span># Load bond_market_prices_eod</span></span>
<span id="cb82-15"></span>
<span id="cb82-16"></span>
<span id="cb82-17"><span># Add mid prices and yields</span></span>
<span id="cb82-18">bond_market_prices_eod[<span>'midPrice'</span>] <span>=</span> <span>0.5</span><span>*</span>(bond_market_prices_eod[<span>'bidPrice'</span>] <span>+</span> bond_market_prices_eod[<span>'askPrice'</span>])</span>
<span id="cb82-19">bond_market_prices_eod[<span>'midYield'</span>] <span>=</span> <span>0.5</span><span>*</span>(bond_market_prices_eod[<span>'bidYield'</span>] <span>+</span> bond_market_prices_eod[<span>'askYield'</span>])</span>
<span id="cb82-20">display (bond_market_prices_eod.Head ())</span>
<span id="cb82-21"></span>
<span id="cb82-22">bond_symbology</span>
<span id="cb82-23"></span>
<span id="cb82-24"><span># Load govt_on_the_run,  as of 2024-04-08</span></span>
<span id="cb82-25"></span>
<span id="cb82-26"></span>
<span id="cb82-27"><span># Keep OTR treasuries only</span></span>
<span id="cb82-28">govt_on_the_run_simple <span>=</span> govt_on_the_run[<span>~</span>govt_on_the_run[<span>'ticker'</span>].<span>str</span>. contains (<span>'B|C'</span>)]</span>
<span id="cb82-29">display (govt_on_the_run_simple.Head ())</span>
```

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | amt_out | country | currency | status | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | Corp | BBG 004 HST 0 K 7 | US 037833 AL 42 | US 912810 TZ 12 | AAPL 3.85 05/04/43 | APPLE INC | GLOBAL | 3.850 | FIXED | 30/360 | 2 | 2 | 2013-05-03 | 2013-11-04 | 2013-05-03 | 2043-05-04 | AT MATURITY | Sr Unsecured | 3000.0 | US | USD | ACTV | 30.001369 | 19.069131 |
| 1 | AAPL | Corp | BBG 006 F 8 VWJ 7 | US 037833 AT 77 | US 912810 TZ 12 | AAPL 4.45 05/06/44 | APPLE INC | GLOBAL | 4.450 | FIXED | 30/360 | 2 | 2 | 2014-05-06 | 2014-11-06 | 2014-05-06 | 2044-05-06 | AT MATURITY | Sr Unsecured | 1000.0 | US | USD | ACTV | 30.001369 | 20.076660 |
| 2 | AAPL | Corp | BBG 0081 TNL 50 | US 037833 BA 77 | US 912810 TZ 12 | AAPL 3.45 02/09/45 | APPLE INC | GLOBAL | 3.450 | FIXED | 30/360 | 2 | 2 | 2015-02-09 | 2015-08-09 | 2015-02-09 | 2045-02-09 | AT MATURITY | Sr Unsecured | 2000.0 | US | USD | ACTV | 30.001369 | 20.840520 |
| 3 | AAPL | Corp | BBG 008 N 1 BQC 1 | US 037833 BH 21 | US 912810 TZ 12 | AAPL 4 3/8 05/13/45 | APPLE INC | GLOBAL | 4.375 | FIXED | 30/360 | 2 | 2 | 2015-05-13 | 2015-11-13 | 2015-05-13 | 2045-05-13 | AT MATURITY | Sr Unsecured | 2000.0 | US | USD | ACTV | 30.001369 | 21.095140 |
| 4 | AAPL | Corp | BBG 00 C 7 QBCQ 1 | US 037833 BW 97 | US 91282 CJZ 59 | AAPL 4 1/2 02/23/36 | APPLE INC | GLOBAL | 4.500 | FIXED | 30/360 | 2 | 2 | 2016-02-23 | 2016-08-23 | 2016-02-23 | 2036-02-23 | CALLABLE | Sr Unsecured | 1250.0 | US | USD | ACTV | 20.000000 | 11.876797 |

|  | date | class | ticker | isin | figi | bidPrice | askPrice | accrued | bidYield | askYield | midPrice | midYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 2024-04-19 | Corp | IBM | US 459200 KX 88 | BBG 01 DMT 8986 | 97.453 | 97.706 | 0.9635 | 5.248 | 5.173 | 97.5795 | 5.2105 |
| 1 | 2024-04-19 | Corp | IBM | US 459200 GS 40 | BBG 0000 L 5 Z 27 | 99.145 | 99.818 | 2.2245 | 5.683 | 5.617 | 99.4815 | 5.6500 |
| 2 | 2024-04-19 | Corp | GM | US 37046 AFD 28 | BBG 019 LXFPP 4 | 97.075 | 97.556 | 0.5225 | 6.472 | 6.342 | 97.3155 | 6.4070 |
| 3 | 2024-04-19 | Corp | GM | US 37046 AFA 88 | BBG 017 B 6 GFF 0 | 95.012 | 95.453 | 2.1245 | 6.337 | 6.216 | 95.2325 | 6.2765 |
| 4 | 2024-04-19 | Corp | F | US 34540 TZC 97 | BBG 017 QYHT 99 | 98.950 | 99.289 | 2.0675 | 6.419 | 6.298 | 99.1195 | 6.3585 |

|  | ticker | date | figi | isin |
| --- | --- | --- | --- | --- |
| 0 | GT 10 Govt | 2024-04-19 | BBG 01 L 8 YJFB 3 | US 91282 CJZ 59 |
| 3 | GT 2 Govt | 2024-04-19 | BBG 01 M 44 ZLG 5 | US 91282 CKH 33 |
| 4 | GT 20 Govt | 2024-04-19 | BBG 01 LK 8 Y 0 L 1 | US 912810 TZ 12 |
| 9 | GT 3 Govt | 2024-04-19 | BBG 01 M 9 L 5 M 64 | US 91282 CKJ 98 |
| 10 | GT 30 Govt | 2024-04-19 | BBG 01 L 8 YJKX 8 | US 912810 TX 63 |

## b. Add function to construct generic fixed rate cashflow schedules from symbology data

Use one row of the symbology dataframe as input to the function. Use the helper function to convert a date string to a QuantLib date object.

```latex
<span id="cb83-1"><span>def</span> get_ql_date (date) <span>-&gt;</span> ql. Date:</span>
<span id="cb83-2">    <span>"""</span></span>
<span id="cb83-3"><span>    convert dt. Date to ql. Date</span></span>
<span id="cb83-4"><span>    """</span></span>
<span id="cb83-5">    <span>if</span> <span>isinstance</span>(date,  dt. Date):</span>
<span id="cb83-6">        <span>return</span> ql.Date (date. Day,  date. Month,  date. Year)</span>
<span id="cb83-7">    <span>elif</span> <span>isinstance</span>(date,  <span>str</span>):</span>
<span id="cb83-8">        date <span>=</span> dt.Datetime.Strptime (date,  <span>"%Y-%m-</span><span>%d</span><span>"</span>). Date ()</span>
<span id="cb83-9">        <span>return</span> ql.Date (date. Day,  date. Month,  date. Year)</span>
<span id="cb83-10">    <span>else</span>:</span>
<span id="cb83-11">        <span>raise</span> <span>ValueError</span>(<span>f"to_qldate,  </span><span>{</span><span>type</span>(date)<span>}</span><span>,  </span><span>{</span>date<span>}</span><span>"</span>)</span>
```

```latex
<span id="cb84-1"><span>def</span> create_schedule_from_symbology (details: <span>dict</span>):</span>
<span id="cb84-2">    <span>'''Create a QuantLib cashflow schedule from symbology details dictionary (usually one row of the symbology dataframe)</span></span>
<span id="cb84-3"><span>    '''</span></span>
<span id="cb84-4">    </span>
<span id="cb84-5">    <span># Create maturity from details['maturity']</span></span>
<span id="cb84-6">    maturity <span>=</span> get_ql_date (details[<span>'maturity'</span>])</span>
<span id="cb84-7">    </span>
<span id="cb84-8">    <span># Create acc_first from details['acc_first']</span></span>
<span id="cb84-9">    acc_first <span>=</span>  get_ql_date (details[<span>'acc_first'</span>])</span>
<span id="cb84-10">    </span>
<span id="cb84-11">    <span># Create calendar for Corp and Govt asset classes</span></span>
<span id="cb84-12">    calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb84-13">    </span>
<span id="cb84-14">    <span># define period from details['cpn_freq'] ... Can be hard-coded to 2 = semi-annual frequency</span></span>
<span id="cb84-15">    period <span>=</span> ql.Period (<span>2</span>)</span>
<span id="cb84-16">    </span>
<span id="cb84-17">    <span># business_day_convention</span></span>
<span id="cb84-18">    business_day_convention <span>=</span> ql. Unadjusted</span>
<span id="cb84-19">    </span>
<span id="cb84-20">    <span># termination_date_convention</span></span>
<span id="cb84-21">    termination_date_convention <span>=</span> ql. Unadjusted</span>
<span id="cb84-22">    </span>
<span id="cb84-23">    <span># date_generation</span></span>
<span id="cb84-24">    date_generation<span>=</span>ql. DateGeneration. Backward</span>
<span id="cb84-25">    </span>
<span id="cb84-26">    <span># Create schedule using ql. MakeSchedule interface (with keyword arguments)</span></span>
<span id="cb84-27">    schedule <span>=</span> ql.MakeSchedule (effectiveDate<span>=</span>acc_first,   <span># this may not be the same as the bond's start date</span></span>
<span id="cb84-28">                            terminationDate<span>=</span>maturity, </span>
<span id="cb84-29">                            tenor<span>=</span>period, </span>
<span id="cb84-30">                            calendar<span>=</span>calendar, </span>
<span id="cb84-31">                            convention<span>=</span>business_day_convention, </span>
<span id="cb84-32">                            terminalDateConvention<span>=</span>termination_date_convention, </span>
<span id="cb84-33">                            rule<span>=</span>date_generation, </span>
<span id="cb84-34">                            endOfMonth<span>=</span><span>True</span>, </span>
<span id="cb84-35">                            firstDate<span>=</span>ql.Date (), </span>
<span id="cb84-36">                            nextToLastDate<span>=</span>ql.Date ())</span>
<span id="cb84-37">    <span>return</span> schedule</span>
```

```latex
<span id="cb85-1"><span># Use one row of the symbology dataframe as input to the create_schedule_from_symbology () function.</span></span>
<span id="cb85-2">corp_bond_details <span>=</span> bond_symbology[bond_symbology[<span>'class'</span>] <span>==</span> <span>'Corp'</span>]. Iloc[<span>10</span>]</span>
<span id="cb85-3"><span>print</span>(<span>"Corp bond details for"</span>,  corp_bond_details[<span>'security'</span>])</span>
<span id="cb85-4">display (corp_bond_details)</span>
<span id="cb85-5"></span>
<span id="cb85-6"><span># Create cashflow_schedule</span></span>
<span id="cb85-7">cashflow_schedule <span>=</span> create_schedule_from_symbology (corp_bond_details)</span>
<span id="cb85-8">display (<span>"Cashflow dates for"</span>,  corp_bond_details[<span>'security'</span>])</span>
<span id="cb85-9"></span>
<span id="cb85-10"><span># List cashflow dates</span></span>
<span id="cb85-11"><span>for</span> date <span>in</span> cashflow_schedule:</span>
<span id="cb85-12">        <span>print</span>(date)</span>
<span id="cb85-13"></span>
```

```latex
Corp bond details for AAPL 3.35 02/09/27
Corp bond details for AAPL 3.35 02/09/27
February 9 th,  2017
August 9 th,  2017
February 9 th,  2018
August 9 th,  2018
February 9 th,  2019
August 9 th,  2019
February 9 th,  2020
August 9 th,  2020
February 9 th,  2021
August 9 th,  2021
February 9 th,  2022
August 9 th,  2022
February 9 th,  2023
August 9 th,  2023
February 9 th,  2024
August 9 th,  2024
February 9 th,  2025
August 9 th,  2025
February 9 th,  2026
August 9 th,  2026
February 9 th,  2027
February 9 th,  2017
August 9 th,  2017
February 9 th,  2018
August 9 th,  2018
February 9 th,  2019
August 9 th,  2019
February 9 th,  2020
August 9 th,  2020
February 9 th,  2021
August 9 th,  2021
February 9 th,  2022
August 9 th,  2022
February 9 th,  2023
August 9 th,  2023
February 9 th,  2024
August 9 th,  2024
February 9 th,  2025
August 9 th,  2025
February 9 th,  2026
August 9 th,  2026
February 9 th,  2027
```

```latex
Ticker                           AAPL
Class                            Corp
Figi                     BBG 00 FXTS 8 Z 0
Isin                     US 037833 CJ 77
Und_bench_isin           US 91282 CKE 02
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
Name: 10,  dtype: object
```

## c. Add function to construct generic fixed rate bond objects from symbology data

Use one row of the symbology dataframe as input to the function. Use create_schedule_from_symbology () internally to create the cashflow schedule.

```latex
<span id="cb90-1"><span>def</span> create_bond_from_symbology (details: <span>dict</span>):</span>
<span id="cb90-2">    <span>'''Create a US fixed rate bond object from symbology details dictionary (usually one row of the symbology dataframe)</span></span>
<span id="cb90-3"><span>    '''</span></span>
<span id="cb90-4">    </span>
<span id="cb90-5">     <span># Create day_count from details['dcc']</span></span>
<span id="cb90-6">     <span># For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)</span></span>
<span id="cb90-7">     <span># For US Corporate bonds use ql. Thirty 360 (ql. Thirty 360. USA)</span></span>
<span id="cb90-8">    </span>
<span id="cb90-9">    <span>if</span> details[<span>'class'</span>] <span>==</span> <span>'Corp'</span>:</span>
<span id="cb90-10">        day_count <span>=</span> ql. Thirty 360 (ql. Thirty 360. USA)</span>
<span id="cb90-11">    <span>elif</span> details[<span>'class'</span>] <span>==</span> <span>'Govt'</span>:</span>
<span id="cb90-12">        day_count <span>=</span> ql.ActualActual (ql. ActualActual. ISMA)</span>
<span id="cb90-13">    <span>else</span>:</span>
<span id="cb90-14">        <span>raise</span> <span>ValueError</span>(<span>f"unsupported asset class,  </span><span>{</span><span>type</span>(details[<span>'class'</span>])<span>}</span><span>,  </span><span>{</span>details[<span>'class'</span>]<span>}</span><span>"</span>)</span>
<span id="cb90-15"></span>
<span id="cb90-16">    </span>
<span id="cb90-17">    <span># Create issue_date from details['start_date']</span></span>
<span id="cb90-18">    issue_date <span>=</span> get_ql_date (details[<span>'start_date'</span>])</span>
<span id="cb90-19">    </span>
<span id="cb90-20">    <span># Create days_settle from details['days_settle']</span></span>
<span id="cb90-21">    days_settle <span>=</span> <span>int</span>(<span>float</span>(details[<span>'days_settle'</span>]))</span>
<span id="cb90-22"></span>
<span id="cb90-23">    <span># Create coupon from details['coupon']</span></span>
<span id="cb90-24">    coupon <span>=</span> <span>float</span>(details[<span>'coupon'</span>])<span>/</span><span>100.</span></span>
<span id="cb90-25"></span>
<span id="cb90-26"></span>
<span id="cb90-27">    <span># Create cashflow schedule</span></span>
<span id="cb90-28">    schedule <span>=</span> create_schedule_from_symbology (details)</span>
<span id="cb90-29">    </span>
<span id="cb90-30">    face_value <span>=</span> <span>100</span></span>
<span id="cb90-31">    redemption <span>=</span> <span>100</span></span>
<span id="cb90-32">    </span>
<span id="cb90-33">    payment_convention <span>=</span> ql. Unadjusted</span>
<span id="cb90-34">        </span>
<span id="cb90-35">    <span># Create fixed rate bond object</span></span>
<span id="cb90-36">    fixed_rate_bond <span>=</span> ql.FixedRateBond (</span>
<span id="cb90-37">        days_settle, </span>
<span id="cb90-38">        face_value, </span>
<span id="cb90-39">        schedule, </span>
<span id="cb90-40">        [coupon], </span>
<span id="cb90-41">        day_count, </span>
<span id="cb90-42">        payment_convention, </span>
<span id="cb90-43">        redemption, </span>
<span id="cb90-44">        issue_date)        </span>
<span id="cb90-45"></span>
<span id="cb90-46">    <span>return</span> fixed_rate_bond</span>
```

```latex
<span id="cb91-1"><span># Use one row of the symbology dataframe as input to the function.</span></span>
<span id="cb91-2">corp_bond_object <span>=</span> create_bond_from_symbology (corp_bond_details)</span>
<span id="cb91-3"></span>
<span id="cb91-4"><span>print</span>(<span>"Corp bond object details for"</span>,  corp_bond_details[<span>'security'</span>])</span>
<span id="cb91-5"><span>print</span>(<span>'Start date: '</span>,  corp_bond_object.StartDate ())</span>
<span id="cb91-6"><span>print</span>(<span>'Maturity date: '</span>,  corp_bond_object.MaturityDate ())</span>
<span id="cb91-7"><span>print</span>(<span>'Bond face notional: '</span>,  corp_bond_object.Notional ())</span>
```

```latex
Corp bond object details for AAPL 3.35 02/09/27
Start date: February 9 th,  2017
Maturity date: February 9 th,  2027
Bond face notional: 100.0
Corp bond object details for AAPL 3.35 02/09/27
Start date: February 9 th,  2017
Maturity date: February 9 th,  2027
Bond face notional: 100.0
```

## d. Add function that returns a dataframe with (future) cash flows details for a bond object

Use the “Investigate Bond Cashflows” section in the Quantlib Basic notebook as a template.

The results dataframe should contain following columns:

| CashFlowDate | CashFlowAmount | CashFlowYearFrac |
| --- | --- | --- |

Pick one government and one corporate bond from symbology,  create the bond objects and display the future cashflows.

```latex
<span id="cb93-1"><span>def</span> get_bond_cashflows (bond: ql. FixedRateBond,  calc_date<span>=</span>ql. Date) <span>-&gt;</span> pd. DataFrame:</span>
<span id="cb93-2">    <span>'''Returns all future cashflows as of calc_date,  i.e. with payment dates &gt; calc_date.</span></span>
<span id="cb93-3"><span>    '''</span>    </span>
<span id="cb93-4">    day_counter <span>=</span> bond.DayCounter ()    </span>
<span id="cb93-5">    </span>
<span id="cb93-6">    x <span>=</span> [(cf.Date (),  day_counter.YearFraction (calc_date,  cf.Date ()),  cf.Amount ()) <span>for</span> cf <span>in</span> bond.Cashflows ()]</span>
<span id="cb93-7">    cf_date,  cf_yearFrac,  cf_amount <span>=</span> <span>zip</span>(<span>*</span>x)</span>
<span id="cb93-8">    cashflows_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'CashFlowDate'</span>: cf_date,  <span>'CashFlowYearFrac'</span>: cf_yearFrac,  <span>'CashFlowAmount'</span>: cf_amount})</span>
<span id="cb93-9"></span>
<span id="cb93-10">    <span># filter for payment dates &gt; calc_date</span></span>
<span id="cb93-11">    cashflows_df <span>=</span> cashflows_df[cashflows_df. CashFlowYearFrac <span>&gt;</span> <span>0</span>]</span>
<span id="cb93-12">    <span>return</span> cashflows_df</span>
```

```latex
<span id="cb94-1"><span># Pick one government and one corporate bond from symbology,  create the bond objects.</span></span>
<span id="cb94-2">govt_bond_details <span>=</span> bond_symbology[bond_symbology[<span>'class'</span>] <span>==</span> <span>'Govt'</span>]. Iloc[<span>10</span>]</span>
<span id="cb94-3">display (<span>"Govt bond details for"</span>,  govt_bond_details[<span>'security'</span>])</span>
<span id="cb94-4">display (govt_bond_details)</span>
<span id="cb94-5"></span>
<span id="cb94-6"><span># Create govt_bond_object</span></span>
<span id="cb94-7">govt_bond_object <span>=</span> create_bond_from_symbology (govt_bond_details)</span>
```

```latex
Ticker                              T
Class                            Govt
Figi                     BBG 000 DLBVY 0
Isin                     US 912810 ET 17
Und_bench_isin           US 912797 KJ 59
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
Name: 339,  dtype: object
```

```latex
<span id="cb98-1"><span># Govt bond: display the future cashflows.</span></span>
<span id="cb98-2"><span>print</span>(<span>"Govt bond future cashflows for"</span>,  govt_bond_details[<span>'security'</span>])</span>
<span id="cb98-3">govt_bond_cf <span>=</span> get_bond_cashflows (govt_bond_object,  calc_date<span>=</span>calc_date)</span>
<span id="cb98-4">display (govt_bond_cf)</span>
<span id="cb98-5"></span>
<span id="cb98-6"><span># Corp bond: display the future cashflows.</span></span>
<span id="cb98-7"><span>print</span>(<span>"Corp bond future cashflows for"</span>,  corp_bond_details[<span>'security'</span>])</span>
<span id="cb98-8">corp_bond_cf <span>=</span> get_bond_cashflows (corp_bond_object,  calc_date<span>=</span>calc_date)</span>
<span id="cb98-9">display (corp_bond_cf)</span>
```

```latex
Govt bond future cashflows for T 7 5/8 02/15/25
Govt bond future cashflows for T 7 5/8 02/15/25
Corp bond future cashflows for AAPL 3.35 02/09/27
Corp bond future cashflows for AAPL 3.35 02/09/27
```

|  | CashFlowDate | CashFlowYearFrac | CashFlowAmount |
| --- | --- | --- | --- |
| 58 | August 15 th,  2024 | 0.333333 | 3.8125 |
| 59 | February 15 th,  2025 | 0.833333 | 3.8125 |
| 60 | February 15 th,  2025 | 0.833333 | 100.0000 |

|  | CashFlowDate | CashFlowYearFrac | CashFlowAmount |
| --- | --- | --- | --- |
| 14 | August 9 th,  2024 | 0.336111 | 1.675 |
| 15 | February 9 th,  2025 | 0.836111 | 1.675 |
| 16 | August 9 th,  2025 | 1.336111 | 1.675 |
| 17 | February 9 th,  2026 | 1.836111 | 1.675 |
| 18 | August 9 th,  2026 | 2.336111 | 1.675 |
| 19 | February 9 th,  2027 | 2.836111 | 1.675 |
| 20 | February 9 th,  2027 | 2.836111 | 100.000 |

## Problem 2: US Treasury yield curve calibration (On-The-Runs)

## a. Create the on-the-run US treasury bond objects

Restrict the symbology + market data dataframe to “on-the-run”/OTR US treasury notes/bonds only and create the treasury bond objects.

Extend the treasuries symbology dataframe with the following market data columns (code from Homework 1):

| date | bidPrice | askPrice | midPrice | bidYield | askYield | midYield | term | TTM |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Plot a graph/scatter plot of on-the-run treasury mid yields by TTM.

```latex
<span id="cb100-1"><span># Create symbology for on-the-run treasuries only</span></span>
<span id="cb100-2">govt_symbology_otr <span>=</span> bond_symbology[bond_symbology[<span>'isin'</span>]. Isin (govt_on_the_run_simple[<span>'isin'</span>])]. Copy ()</span>
<span id="cb100-3">govt_symbology_otr <span>=</span> govt_symbology_otr. Sort_values (by<span>=</span><span>'TTM'</span>)</span>
<span id="cb100-4"></span>
<span id="cb100-5"><span># Merge market data as of 2024-04-01 into treasury OTR symbology</span></span>
<span id="cb100-6">govt_combined_otr <span>=</span> govt_symbology_otr.Merge (bond_market_prices_eod,   on<span>=</span>[<span>'class'</span>, <span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb100-7"></span>
<span id="cb100-8"><span># Plot a graph/scatter plot of treasury OTR mid yields by TTM</span></span>
<span id="cb100-9">govt_combined_otr.Plot (x<span>=</span><span>'TTM'</span>,  y<span>=</span><span>'midYield'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'OTR US Treasury yields by TTM'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-67-output-1.png)

## b. Calibrate the on-the-run treasury yield curve (bootstrapping)

The function below shows how to calibrate a smooth yield/discount factor curve from the on-the-run treasury dataframe.

Calibrate the bid,  ask and mid discount factor curves as of 2024-04-08.

Display the calibration results for the mid curve,  using get_yield_curve_details_df ().

```latex
<span id="cb101-1"><span>def</span> calibrate_yield_curve_from_frame (</span>
<span id="cb101-2">        calc_date: ql. Date, </span>
<span id="cb101-3">        treasury_details: pd. DataFrame, </span>
<span id="cb101-4">        price_quote_column: <span>str</span>):</span>
<span id="cb101-5">    <span>'''Create a calibrated yield curve from a details dataframe which includes bid/ask/mid price quotes.</span></span>
<span id="cb101-6"><span>    '''</span></span>
<span id="cb101-7">    ql.Settings.Instance (). EvaluationDate <span>=</span> calc_date</span>
<span id="cb101-8"></span>
<span id="cb101-9">    <span># Sort dataframe by maturity</span></span>
<span id="cb101-10">    sorted_details_frame <span>=</span> treasury_details. Sort_values (by<span>=</span><span>'maturity'</span>)    </span>
<span id="cb101-11">    </span>
<span id="cb101-12">    <span># For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)</span></span>
<span id="cb101-13">    day_count <span>=</span> ql.ActualActual (ql. ActualActual. ISMA)</span>
<span id="cb101-14"></span>
<span id="cb101-15">    bond_helpers <span>=</span> []</span>
<span id="cb101-16">    </span>
<span id="cb101-17">    <span>for</span> index,  row <span>in</span> sorted_details_frame.Iterrows ():</span>
<span id="cb101-18">        bond_object <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb101-19">        </span>
<span id="cb101-20">        tsy_clean_price_quote <span>=</span> row[price_quote_column]</span>
<span id="cb101-21">        tsy_clean_price_handle <span>=</span> ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))</span>
<span id="cb101-22">        </span>
<span id="cb101-23">        bond_helper <span>=</span> ql.BondHelper (tsy_clean_price_handle,  bond_object)</span>
<span id="cb101-24">        bond_helpers.Append (bond_helper)</span>
<span id="cb101-25">        </span>
<span id="cb101-26">    yield_curve <span>=</span> ql.PiecewiseLogCubicDiscount (calc_date,  bond_helpers,  day_count)</span>
<span id="cb101-27">    <span># yield_curve = ql.PiecewiseFlatForward (calc_date,  bond_helpers,  day_count)</span></span>
<span id="cb101-28">    </span>
<span id="cb101-29">    yield_curve.EnableExtrapolation ()</span>
<span id="cb101-30">    <span>return</span> yield_curve</span>
<span id="cb101-31"></span>
<span id="cb101-32"></span>
<span id="cb101-33"></span>
<span id="cb101-34"><span>def</span> get_yield_curve_details_df (yield_curve,  curve_dates<span>=</span><span>None</span>):</span>
<span id="cb101-35">    </span>
<span id="cb101-36">    <span>if</span>(curve_dates <span>==</span> <span>None</span>):</span>
<span id="cb101-37">        curve_dates <span>=</span> yield_curve.Dates ()</span>
<span id="cb101-38"></span>
<span id="cb101-39">    dates <span>=</span> [d.to_date () <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb101-40">    discounts <span>=</span> [<span>round</span>(yield_curve.Discount (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb101-41">    yearfracs <span>=</span> [<span>round</span>(yield_curve.TimeFromReference (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb101-42">    zeroRates <span>=</span> [<span>round</span>(yield_curve.ZeroRate (d,  yield_curve.DayCounter (),  ql. Compounded). Rate () <span>*</span> <span>100</span>,  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb101-43"></span>
<span id="cb101-44">    yield_curve_details_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Date'</span>: dates, </span>
<span id="cb101-45">                             <span>'YearFrac'</span>: yearfracs, </span>
<span id="cb101-46">                             <span>'DiscountFactor'</span>: discounts, </span>
<span id="cb101-47">                             <span>'ZeroRate'</span>: zeroRates})                             </span>
<span id="cb101-48">    <span>return</span> yield_curve_details_df</span>
```

```latex
<span id="cb102-1"><span># Calibrate the bid,  ask and mid discount factor curves as of 2024-04-08.</span></span>
<span id="cb102-2">tsy_yield_curve_bid <span>=</span> calibrate_yield_curve_from_frame (calc_date,  govt_combined_otr,  <span>'bidPrice'</span>)</span>
<span id="cb102-3">tsy_yield_curve_mid <span>=</span> calibrate_yield_curve_from_frame (calc_date,  govt_combined_otr,  <span>'midPrice'</span>)</span>
<span id="cb102-4">tsy_yield_curve_ask <span>=</span> calibrate_yield_curve_from_frame (calc_date,  govt_combined_otr,  <span>'askPrice'</span>)</span>
<span id="cb102-5"></span>
<span id="cb102-6"><span># Display the calibration results for the mid curve</span></span>
<span id="cb102-7">tsy_yield_curve_df <span>=</span> get_yield_curve_details_df (tsy_yield_curve_mid)</span>
<span id="cb102-8">display (tsy_yield_curve_df)</span>
<span id="cb102-9"></span>
<span id="cb102-10">ql_dates_yearly <span>=</span> [calc_date <span>+</span> ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> <span>list</span>(<span>range</span>(<span>0</span>,  <span>30</span>,  <span>1</span>))]</span>
<span id="cb102-11">tsy_yield_curve_monthly_df <span>=</span> get_yield_curve_details_df (tsy_yield_curve_mid,  curve_dates<span>=</span>ql_dates_yearly)</span>
<span id="cb102-12">display (tsy_yield_curve_monthly_df)</span>
```

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-08 | 0.000 | 1.000 | 5.102 |
| 1 | 2026-03-31 | 2.000 | 0.907 | 4.981 |
| 2 | 2029-03-31 | 5.000 | 0.795 | 4.685 |
| 3 | 2031-03-31 | 7.000 | 0.726 | 4.676 |
| 4 | 2034-02-15 | 9.833 | 0.638 | 4.678 |
| 5 | 2044-02-15 | 19.833 | 0.382 | 4.968 |
| 6 | 2054-02-15 | 29.917 | 0.253 | 4.702 |

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-08 | 0.0 | 1.000 | 5.102 |
| 1 | 2025-04-08 | 1.0 | 0.952 | 5.072 |
| 2 | 2026-04-08 | 2.0 | 0.907 | 4.981 |
| 3 | 2027-04-08 | 3.0 | 0.868 | 4.850 |
| 4 | 2028-04-08 | 4.0 | 0.831 | 4.743 |
| 5 | 2029-04-08 | 5.0 | 0.795 | 4.685 |
| 6 | 2030-04-08 | 6.0 | 0.760 | 4.674 |
| 7 | 2031-04-08 | 7.0 | 0.726 | 4.676 |
| 8 | 2032-04-08 | 8.0 | 0.694 | 4.671 |
| 9 | 2033-04-08 | 9.0 | 0.663 | 4.669 |
| 10 | 2034-04-08 | 10.0 | 0.633 | 4.681 |
| 11 | 2035-04-08 | 11.0 | 0.603 | 4.710 |
| 12 | 2036-04-08 | 12.0 | 0.573 | 4.748 |
| 13 | 2037-04-08 | 13.0 | 0.544 | 4.791 |
| 14 | 2038-04-08 | 14.0 | 0.516 | 4.833 |
| 15 | 2039-04-08 | 15.0 | 0.490 | 4.873 |
| 16 | 2040-04-08 | 16.0 | 0.465 | 4.908 |
| 17 | 2041-04-08 | 17.0 | 0.441 | 4.936 |
| 18 | 2042-04-08 | 18.0 | 0.419 | 4.956 |
| 19 | 2043-04-08 | 19.0 | 0.398 | 4.967 |
| 20 | 2044-04-08 | 20.0 | 0.379 | 4.967 |
| 21 | 2045-04-08 | 21.0 | 0.362 | 4.958 |
| 22 | 2046-04-08 | 22.0 | 0.346 | 4.941 |
| 23 | 2047-04-08 | 23.0 | 0.332 | 4.917 |
| 24 | 2048-04-08 | 24.0 | 0.318 | 4.890 |
| 25 | 2049-04-08 | 25.0 | 0.305 | 4.859 |
| 26 | 2050-04-08 | 26.0 | 0.294 | 4.827 |
| 27 | 2051-04-08 | 27.0 | 0.282 | 4.794 |
| 28 | 2052-04-08 | 28.0 | 0.272 | 4.762 |
| 29 | 2053-04-08 | 29.0 | 0.262 | 4.730 |

## c. Plot the calibrated US Treasury yield (zero rate) curves

Create a graph/scatter plot of the newly computed mid yields by maturity.

```latex
<span id="cb103-1">plt <span>=</span> tsy_yield_curve_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span>[<span>'ZeroRate'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'US Treasury OTR yield curve as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb103-2">plt. Set_ylabel (<span>'Zero Rate (%)'</span>)</span>
<span id="cb103-3">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb103-4"></span>
<span id="cb103-5">plt <span>=</span> tsy_yield_curve_monthly_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span>[<span>'ZeroRate'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'US Treasury Yearly yield curve as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb103-6">plt. Set_ylabel (<span>'Zero Rate (%)'</span>)</span>
<span id="cb103-7">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-70-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-70-output-3.png)

## d. Plot calibrated discount factors

Plot the discount factor curve up to the 30 years point,  using a 6 months discretization grid.

```latex
<span id="cb105-1">plt <span>=</span> tsy_yield_curve_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span>[<span>'DiscountFactor'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'US Treasury OTR discount factor curve as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb105-2">plt. Set_ylabel (<span>'Discount Factor'</span>)</span>
<span id="cb105-3">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb105-4"></span>
<span id="cb105-5">plt <span>=</span> tsy_yield_curve_monthly_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span>[<span>'DiscountFactor'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'US Treasury Yearly discount factor curve as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb105-6">plt. Set_ylabel (<span>'Discount Factor'</span>)</span>
<span id="cb105-7">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-71-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-71-output-3.png)

## Problem 3: Pricing and risk metrics for US Treasury bonds

## a. US Treasury pricing on the calibrated discount factor curve

Follow Section 5. “Bond Present Value Calculation (no credit risk)” in the QuantLib Basic notebook to re-price the US on-the-run treasuries using the calibrated discount factor curve.

You will need to switch the bond_engine to use the new on-the-run treasury yield curve: bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_mid)

Extend the dataframe with the following computed columns for clean mid prices:

| calc_mid_price |
| --- |

To validate the calibration,  compare the calculated clean mid prices to the original market mid prices.

```latex
<span id="cb107-1"><span># Create risk free bond_engine using calibrated US OTR yield curve</span></span>
<span id="cb107-2">tsy_yield_curve_mid_handle <span>=</span> ql.YieldTermStructureHandle (tsy_yield_curve_mid)</span>
<span id="cb107-3">bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)</span>
<span id="cb107-4"></span>
<span id="cb107-5"><span># Calculate mid prices</span></span>
<span id="cb107-6">calculated_mid_prices <span>=</span> []</span>
<span id="cb107-7"><span>for</span> index,  row <span>in</span> govt_combined_otr.Iterrows ():</span>
<span id="cb107-8">    bond_object <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb107-9">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb107-10">    calculated_mid_prices.Append (bond_object.CleanPrice ())</span>
<span id="cb107-11">    </span>
<span id="cb107-12">govt_combined_otr[<span>'calc_mid_price'</span>] <span>=</span> calculated_mid_prices</span>
<span id="cb107-13">govt_combined_otr[<span>'calib_error'</span>] <span>=</span> govt_combined_otr[<span>'midPrice'</span>] <span>-</span> govt_combined_otr[<span>'calc_mid_price'</span>]</span>
<span id="cb107-14"></span>
<span id="cb107-15"><span># Compare the calculated clean mid prices to the original market mid prices.</span></span>
<span id="cb107-16">display (govt_combined_otr [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'midPrice'</span>,  <span>'calc_mid_price'</span>,  <span>'calib_error'</span>]])</span>
```

|  | security | isin | figi | midPrice | calc_mid_price | calib_error |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | T 4 1/2 03/31/26 | US 91282 CKH 33 | BBG 01 M 44 ZLG 5 | 99.10745 | 99.10745 | 1.082867 e-11 |
| 1 | T 4 1/8 03/31/29 | US 91282 CKG 59 | BBG 01 M 44 ZQJ 1 | 97.61330 | 97.61330 | -1.315925 e-11 |
| 2 | T 4 1/8 03/31/31 | US 91282 CKF 76 | BBG 01 M 44 ZS 07 | 96.89845 | 96.89845 | -2.633271 e-11 |
| 3 | T 4 02/15/34 | US 91282 CJZ 59 | BBG 01 L 8 YJFB 3 | 95.13280 | 95.13280 | -9.805490 e-13 |
| 4 | T 4 1/2 02/15/44 | US 912810 TZ 12 | BBG 01 LK 8 Y 0 L 1 | 95.67970 | 95.67970 | 3.655032 e-11 |
| 5 | T 4 1/4 02/15/54 | US 912810 TX 63 | BBG 01 L 8 YJKX 8 | 92.63285 | 92.63285 | -5.925926 e-12 |

## b. Compute analytical DV 01,  Duration and Convexity for US on-the-run treasuries (using flat yield)

Compute analytical DV 01,  Duration and Convexity metrics,  as described in Section 7. “Analytical Duration,  Convexity and Z-Spread (flat yield model)” in the QuantLib Basic notebook.

Remember that DV 01 = Dirty_Price * Duration.

Extend the dataframe with the following calculated risk metrics:

| dv 01 | duration | convexity |
| --- | --- | --- |

```latex
<span id="cb108-1"><span># Set yield conventions</span></span>
<span id="cb108-2">compounding <span>=</span> ql. Compounded</span>
<span id="cb108-3">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb108-4"></span>
<span id="cb108-5"><span># Calculate dv 01 s,  durations and convexities</span></span>
<span id="cb108-6">dv 01 s <span>=</span> []</span>
<span id="cb108-7">calc_durations <span>=</span> []</span>
<span id="cb108-8">calc_convexities <span>=</span> []</span>
<span id="cb108-9"></span>
<span id="cb108-10"><span>for</span> index,  row <span>in</span> govt_combined_otr.Iterrows ():</span>
<span id="cb108-11">    </span>
<span id="cb108-12">    bond_object <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb108-13">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb108-14">    </span>
<span id="cb108-15">    settle_date <span>=</span> bond_object.SettlementDate (calc_date)</span>
<span id="cb108-16">    day_counter <span>=</span> bond_object.DayCounter ()    </span>
<span id="cb108-17">    </span>
<span id="cb108-18">    bond_yield <span>=</span> bond_object.BondYield (row[<span>'calc_mid_price'</span>],  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>100</span></span>
<span id="cb108-19">    </span>
<span id="cb108-20">    flat_int_rate <span>=</span> ql.InterestRate (bond_yield <span>/</span> <span>100</span>,  day_counter,  compounding,  coupon_freq)</span>
<span id="cb108-21">    bond_duration <span>=</span> ql.BondFunctions.Duration (bond_object,  flat_int_rate)</span>
<span id="cb108-22">    bond_convexity <span>=</span> ql.BondFunctions.Convexity (bond_object,  flat_int_rate)</span>
<span id="cb108-23">    bond_dv 01 <span>=</span> bond_object.DirtyPrice () <span>*</span> bond_duration <span>/</span> <span>100</span></span>
<span id="cb108-24">    </span>
<span id="cb108-25">    dv 01 s.Append (bond_dv 01)</span>
<span id="cb108-26">    calc_durations.Append (bond_duration)</span>
<span id="cb108-27">    calc_convexities.Append (bond_convexity)</span>
<span id="cb108-28"></span>
<span id="cb108-29"><span># Add new risk columns and display results    </span></span>
<span id="cb108-30">govt_combined_otr[<span>'dv 01'</span>] <span>=</span> dv 01 s</span>
<span id="cb108-31">govt_combined_otr[<span>'duration'</span>] <span>=</span> calc_durations</span>
<span id="cb108-32">govt_combined_otr[<span>'convexity'</span>] <span>=</span> calc_convexities</span>
<span id="cb108-33"></span>
<span id="cb108-34">display (govt_combined_otr [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'calc_mid_price'</span>,  <span>'dv01'</span>,  <span>'duration'</span>,  <span>'convexity'</span>]])</span>
```

|  | security | isin | figi | calc_mid_price | dv 01 | duration | convexity |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | T 4 1/2 03/31/26 | US 91282 CKH 33 | BBG 01 M 44 ZLG 5 | 99.10745 | 1.849051 | 1.863622 | 4.451242 |
| 1 | T 4 1/8 03/31/29 | US 91282 CKG 59 | BBG 01 M 44 ZQJ 1 | 97.61330 | 4.333122 | 4.434461 | 22.994377 |
| 2 | T 4 1/8 03/31/31 | US 91282 CKF 76 | BBG 01 M 44 ZS 07 | 96.89845 | 5.791786 | 5.970920 | 41.667226 |
| 3 | T 4 02/15/34 | US 91282 CJZ 59 | BBG 01 L 8 YJFB 3 | 95.13280 | 7.615610 | 7.955616 | 75.391888 |
| 4 | T 4 1/2 02/15/44 | US 912810 TZ 12 | BBG 01 LK 8 Y 0 L 1 | 95.67970 | 12.302563 | 12.768977 | 216.798414 |
| 5 | T 4 1/4 02/15/54 | US 912810 TX 63 | BBG 01 L 8 YJKX 8 | 92.63285 | 15.088734 | 16.178632 | 378.784333 |

## c. Compute scenario DV 01,  Duration and Convexity for US on-the-run treasuries (using calibrated yield curve)

Compute the scenario DV 01,  Duration and Convexity metrics using +/-1 bp interest rate shocks,  as described in Section 6. “Market Data Scenarios” in the QuantLib Basic notebook.

Remember that DV 01 = Dirty_Price * Duration.

Extend the dataframe with the following scenario sensitivities metrics:

| scen_dv 01 | scen_duration | scen_convexity |
| --- | --- | --- |

```latex
<span id="cb109-1"><span># Calculate scenario dv 01 s,  durations and convexities</span></span>
<span id="cb109-2">scen_dv 01 s <span>=</span> []</span>
<span id="cb109-3">scen_durations <span>=</span> []</span>
<span id="cb109-4">scen_convexities <span>=</span> []</span>
<span id="cb109-5"></span>
<span id="cb109-6"><span>for</span> index,  row <span>in</span> govt_combined_otr.Iterrows ():</span>
<span id="cb109-7">    bond_object <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb109-8">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb109-9">    </span>
<span id="cb109-10">    <span># create interest rate scenarios</span></span>
<span id="cb109-11">    interest_rate_bump <span>=</span> ql.SimpleQuote (<span>0.0</span>)</span>
<span id="cb109-12">    calibrated_yield_curve_bumped <span>=</span> ql.ZeroSpreadedTermStructure (tsy_yield_curve_mid_handle,  ql.QuoteHandle (interest_rate_bump))</span>
<span id="cb109-13">    bond_engine_bumped <span>=</span> ql.DiscountingBondEngine (ql.YieldTermStructureHandle (calibrated_yield_curve_bumped))</span>
<span id="cb109-14">    bond_object.SetPricingEngine (bond_engine_bumped)</span>
<span id="cb109-15">    dirty_price_base <span>=</span> bond_object.DirtyPrice ()</span>
<span id="cb109-16">    </span>
<span id="cb109-17">    <span># Create +1 bp scenario</span></span>
<span id="cb109-18">    interest_rate_bump.SetValue (<span>0.0001</span>)</span>
<span id="cb109-19">    dirty_price_plus <span>=</span> bond_object.DirtyPrice ()    </span>
<span id="cb109-20">    </span>
<span id="cb109-21">    <span># Create -1 bp scenario</span></span>
<span id="cb109-22">    interest_rate_bump.SetValue (<span>-</span><span>0.0001</span>)</span>
<span id="cb109-23">    dirty_price_minus <span>=</span> bond_object.DirtyPrice ()</span>
<span id="cb109-24">    </span>
<span id="cb109-25">    <span># Calc scenario risks        </span></span>
<span id="cb109-26">    scen_dv 01 <span>=</span> (dirty_price_minus <span>-</span> dirty_price_base)<span>*</span><span>100</span></span>
<span id="cb109-27">    scen_duration <span>=</span> scen_dv 01  <span>/</span> dirty_price_base <span>*</span> <span>100</span></span>
<span id="cb109-28">    scen_convexity <span>=</span> (dirty_price_plus <span>+</span> dirty_price_minus <span>-</span> <span>2</span> <span>*</span> dirty_price_base) <span>/</span> (dirty_price_base <span>*</span> <span>0.0001</span><span>**</span><span>2</span>)</span>
<span id="cb109-29">    </span>
<span id="cb109-30">    scen_dv 01 s.Append (scen_dv 01)</span>
<span id="cb109-31">    scen_durations.Append (scen_duration)</span>
<span id="cb109-32">    scen_convexities.Append (scen_convexity)</span>
<span id="cb109-33"></span>
<span id="cb109-34"><span># Add new scenario risk columns and display results</span></span>
<span id="cb109-35">govt_combined_otr[<span>'scen_dv 01'</span>] <span>=</span> scen_dv 01 s</span>
<span id="cb109-36">govt_combined_otr[<span>'scen_duration'</span>] <span>=</span> scen_durations</span>
<span id="cb109-37">govt_combined_otr[<span>'scen_convexity'</span>] <span>=</span> scen_convexities</span>
<span id="cb109-38"></span>
<span id="cb109-39">display (govt_combined_otr [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>, <span>'scen_dv01'</span>,  <span>'scen_duration'</span>,  <span>'scen_convexity'</span>]])</span>
```

|  | security | isin | figi | scen_dv 01 | scen_duration | scen_convexity |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | T 4 1/2 03/31/26 | US 91282 CKH 33 | BBG 01 M 44 ZLG 5 | 1.917037 | 1.932144 | 3.804813 |
| 1 | T 4 1/8 03/31/29 | US 91282 CKG 59 | BBG 01 M 44 ZQJ 1 | 4.458517 | 4.562789 | 22.022786 |
| 2 | T 4 1/8 03/31/31 | US 91282 CKF 76 | BBG 01 M 44 ZS 07 | 5.952983 | 6.137103 | 40.870958 |
| 3 | T 4 02/15/34 | US 91282 CJZ 59 | BBG 01 L 8 YJFB 3 | 7.778255 | 8.125523 | 74.543262 |
| 4 | T 4 1/2 02/15/44 | US 912810 TZ 12 | BBG 01 LK 8 Y 0 L 1 | 12.534962 | 13.010187 | 218.717486 |
| 5 | T 4 1/4 02/15/54 | US 912810 TX 63 | BBG 01 L 8 YJKX 8 | 15.491226 | 16.610198 | 390.955648 |

## Problem 4: Pricing and risk metrics for corporate bonds

## a. Create the fixed-rate corporate bond objects

Restrict the symbology dataframe to fixed rate corporate bonds only and create the corporate bond objects.

```latex
<span id="cb110-1"><span># Create the fixed-rate corporate bond symbology + combined dataframes</span></span>
<span id="cb110-2">corp_symbology <span>=</span> bond_symbology[bond_symbology[<span>'cpn_type'</span>] <span>==</span> <span>'FIXED'</span>]</span>
<span id="cb110-3">corp_combined <span>=</span> corp_symbology.Merge (bond_market_prices_eod,   on<span>=</span>[<span>'class'</span>, <span>'ticker'</span>, <span>'figi'</span>, <span>'isin'</span>])</span>
<span id="cb110-4"></span>
<span id="cb110-5">display (corp_combined.Head ())</span>
```

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | dcc | cpn_freq | days_settle | start_date | cpn_first | acc_first | maturity | mty_typ | rank | amt_out | country | currency | status | term | TTM | date | bidPrice | askPrice | accrued | bidYield | askYield | midPrice | midYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL | Corp | BBG 004 HST 0 K 7 | US 037833 AL 42 | US 912810 TZ 12 | AAPL 3.85 05/04/43 | APPLE INC | GLOBAL | 3.850 | FIXED | 30/360 | 2 | 2 | 2013-05-03 | 2013-11-04 | 2013-05-03 | 2043-05-04 | AT MATURITY | Sr Unsecured | 3000.0 | US | USD | ACTV | 30.001369 | 19.069131 | 2024-04-19 | 82.155 | 82.733 | 1.8070 | 5.357 | 5.302 | 82.4440 | 5.3295 |
| 1 | AAPL | Corp | BBG 006 F 8 VWJ 7 | US 037833 AT 77 | US 912810 TZ 12 | AAPL 4.45 05/06/44 | APPLE INC | GLOBAL | 4.450 | FIXED | 30/360 | 2 | 2 | 2014-05-06 | 2014-11-06 | 2014-05-06 | 2044-05-06 | AT MATURITY | Sr Unsecured | 1000.0 | US | USD | ACTV | 30.001369 | 20.076660 | 2024-04-19 | 89.955 | 90.676 | 2.0645 | 5.267 | 5.205 | 90.3155 | 5.2360 |
| 2 | AAPL | Corp | BBG 0081 TNL 50 | US 037833 BA 77 | US 912810 TZ 12 | AAPL 3.45 02/09/45 | APPLE INC | GLOBAL | 3.450 | FIXED | 30/360 | 2 | 2 | 2015-02-09 | 2015-08-09 | 2015-02-09 | 2045-02-09 | AT MATURITY | Sr Unsecured | 2000.0 | US | USD | ACTV | 30.001369 | 20.840520 | 2024-04-19 | 75.944 | 76.561 | 0.7095 | 5.387 | 5.328 | 76.2525 | 5.3575 |
| 3 | AAPL | Corp | BBG 008 N 1 BQC 1 | US 037833 BH 21 | US 912810 TZ 12 | AAPL 4 3/8 05/13/45 | APPLE INC | GLOBAL | 4.375 | FIXED | 30/360 | 2 | 2 | 2015-05-13 | 2015-11-13 | 2015-05-13 | 2045-05-13 | AT MATURITY | Sr Unsecured | 2000.0 | US | USD | ACTV | 30.001369 | 21.095140 | 2024-04-19 | 87.214 | 87.825 | 1.9445 | 5.399 | 5.345 | 87.5195 | 5.3720 |
| 4 | AAPL | Corp | BBG 00 C 7 QBCQ 1 | US 037833 BW 97 | US 91282 CJZ 59 | AAPL 4 1/2 02/23/36 | APPLE INC | GLOBAL | 4.500 | FIXED | 30/360 | 2 | 2 | 2016-02-23 | 2016-08-23 | 2016-02-23 | 2036-02-23 | CALLABLE | Sr Unsecured | 1250.0 | US | USD | ACTV | 20.000000 | 11.876797 | 2024-04-19 | 95.507 | 95.927 | 0.7500 | 5.007 | 4.958 | 95.7170 | 4.9825 |

```latex
<span id="cb111-1"><span># Create the corporate bond objects and store them in a dictionary</span></span>
<span id="cb111-2">corp_bond_object_dict <span>=</span> {}</span>
<span id="cb111-3"></span>
<span id="cb111-4"><span>for</span> index,  row <span>in</span> corp_combined.Iterrows ():</span>
<span id="cb111-5">    bond_details <span>=</span> row. To_dict ()</span>
<span id="cb111-6">    corp_bond_object <span>=</span> create_bond_from_symbology (bond_details)</span>
<span id="cb111-7">    corp_bond_object_dict[row[<span>'security'</span>]] <span>=</span> corp_bond_object</span>
<span id="cb111-8">    </span>
<span id="cb111-9"><span># Display the future cashflows for one corp bond object in the dictionary</span></span>
<span id="cb111-10">corp_bond_key <span>=</span> corp_combined. Iloc[<span>10</span>][<span>'security'</span>]</span>
<span id="cb111-11">corp_bond_cf <span>=</span> get_bond_cashflows (corp_bond_object_dict[corp_bond_key],  calc_date<span>=</span>calc_date)</span>
<span id="cb111-12"></span>
<span id="cb111-13"><span>print</span>(<span>"Corp bond future cashflows for"</span>,  corp_bond_key)</span>
<span id="cb111-14">display (corp_bond_cf)</span>
```

```latex
Corp bond future cashflows for AAPL 3.35 02/09/27
Corp bond future cashflows for AAPL 3.35 02/09/27
```

|  | CashFlowDate | CashFlowYearFrac | CashFlowAmount |
| --- | --- | --- | --- |
| 14 | August 9 th,  2024 | 0.336111 | 1.675 |
| 15 | February 9 th,  2025 | 0.836111 | 1.675 |
| 16 | August 9 th,  2025 | 1.336111 | 1.675 |
| 17 | February 9 th,  2026 | 1.836111 | 1.675 |
| 18 | August 9 th,  2026 | 2.336111 | 1.675 |
| 19 | February 9 th,  2027 | 2.836111 | 1.675 |
| 20 | February 9 th,  2027 | 2.836111 | 100.000 |

## b. Compute analytical Yields and Z-Spreads

Compute analytical Yields and Z-Spreads metrics,  as described in Section 7. “Analytical Duration,  Convexity and Z-Spread (flat yield model)” in the QuantLib Basic notebook.

Extend the dataframe with the following calculated risk metrics:

| calc_yield | calc_zspread |
| --- | --- |

```latex
<span id="cb113-1"><span># Create risk free bond engine</span></span>
<span id="cb113-2">bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)</span>
<span id="cb113-3"></span>
<span id="cb113-4"><span># Set yield conventions</span></span>
<span id="cb113-5">compounding <span>=</span> ql. Compounded</span>
<span id="cb113-6">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb113-7"></span>
<span id="cb113-8"><span># Calculate yields and zspreads</span></span>
<span id="cb113-9">calc_yields <span>=</span> []</span>
<span id="cb113-10">calc_zspreads <span>=</span> []</span>
<span id="cb113-11"></span>
<span id="cb113-12"><span>for</span> index,  row <span>in</span> corp_combined.Iterrows ():</span>
<span id="cb113-13">        </span>
<span id="cb113-14">    bond_object <span>=</span> create_bond_from_symbology (row)    </span>
<span id="cb113-15">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb113-16">    </span>
<span id="cb113-17">    settle_date <span>=</span> bond_object.SettlementDate (calc_date)</span>
<span id="cb113-18">    day_counter <span>=</span> bond_object.DayCounter ()</span>
<span id="cb113-19"></span>
<span id="cb113-20">    clean_price <span>=</span> bond_object.CleanPrice ()</span>
<span id="cb113-21">    </span>
<span id="cb113-22">    <span># yield in pct</span></span>
<span id="cb113-23">    calc_yield <span>=</span> bond_object.BondYield (clean_price,  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>1 e 2</span></span>
<span id="cb113-24">    flat_int_rate <span>=</span> ql.InterestRate (calc_yield <span>/</span> <span>100</span>,  day_counter,  compounding,  coupon_freq)</span>
<span id="cb113-25">    bond_market_price <span>=</span> row[<span>'midPrice'</span>]</span>
<span id="cb113-26">    </span>
<span id="cb113-27">    <span># zspread in bps</span></span>
<span id="cb113-28">    calc_zspread <span>=</span> ql.BondFunctions.ZSpread (bond_object,  bond_market_price,  tsy_yield_curve_mid,  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>1 e 4</span></span>
<span id="cb113-29">    </span>
<span id="cb113-30">    calc_yields.Append (calc_yield)</span>
<span id="cb113-31">    calc_zspreads.Append (calc_zspread)</span>
<span id="cb113-32"></span>
<span id="cb113-33"><span># Add new columns and display results</span></span>
<span id="cb113-34">corp_combined[<span>'calc_yield'</span>] <span>=</span> calc_yields</span>
<span id="cb113-35">corp_combined[<span>'calc_zspread'</span>] <span>=</span> calc_zspreads</span>
<span id="cb113-36"></span>
<span id="cb113-37">display (corp_combined [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'midPrice'</span>,  <span>'calc_yield'</span>,  <span>'calc_zspread'</span>]])</span>
```

|  | security | isin | figi | midPrice | calc_yield | calc_zspread |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL 3.85 05/04/43 | US 037833 AL 42 | BBG 004 HST 0 K 7 | 82.4440 | 4.856694 | 47.176515 |
| 1 | AAPL 4.45 05/06/44 | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | 90.3155 | 4.850831 | 38.561569 |
| 2 | AAPL 3.45 02/09/45 | US 037833 BA 77 | BBG 0081 TNL 50 | 76.2525 | 4.852891 | 50.421681 |
| 3 | AAPL 4 3/8 05/13/45 | US 037833 BH 21 | BBG 008 N 1 BQC 1 | 87.5195 | 4.839749 | 53.382060 |
| 4 | AAPL 4 1/2 02/23/36 | US 037833 BW 97 | BBG 00 C 7 QBCQ 1 | 95.7170 | 4.704213 | 27.610405 |
| … | … | … | … | … | … | … |
| 766 | DIS 7 1/8 04/08/28 | USU 25497 AR 66 | BBG 00 N 3 BD 9 G 0 | 106.2885 | 4.706609 | 64.840747 |
| 767 | DIS 8.45 08/01/34 | USU 25497 AW 51 | BBG 00 N 3 BZ 921 | 122.0445 | 4.656777 | 94.353981 |
| 768 | DIS 7.9 12/01/2095 | USU 25497 BM 60 | BBG 00 N 55 NLL 7 | 128.2810 | 4.509017 | 155.762213 |
| 769 | DIS 8 1/4 10/17/2096 | USU 25497 BN 44 | BBG 00 N 55 NPV 7 | 133.3885 | 4.503858 | 159.294000 |
| 770 | VZ 2.355 03/15/32 | USU 9221 ABY 39 | BBG 012 MB 8 P 10 | 79.7950 | 4.612098 | 92.740977 |

771 rows × 6 columns

## c. Validate Z-Spread computation for a few fixed rate corporate bonds

Pick 3 corporate bonds (at your discretion) and use function below to re-price them using the calibrated flat z-spread. Follow the example in Section 7. “Analytical Duration,  Convexity and Z-Spread (flat yield model)”.

Validate that you match the original market prices,  which were used as input to the z-Spread function.

```latex
<span id="cb114-1"><span>def</span> calc_clean_price_with_zspread (fixed_rate_bond,  yield_curve_handle,  zspread):</span>
<span id="cb114-2">    zspread_quote <span>=</span> ql.SimpleQuote (zspread)</span>
<span id="cb114-3">    zspread_quote_handle <span>=</span> ql.QuoteHandle (zspread_quote)</span>
<span id="cb114-4">    yield_curve_bumped <span>=</span> ql.ZeroSpreadedTermStructure (yield_curve_handle,  zspread_quote_handle,  ql. Compounded,  ql. Semiannual)</span>
<span id="cb114-5">    yield_curve_bumped_handle <span>=</span> ql.YieldTermStructureHandle (yield_curve_bumped)</span>
<span id="cb114-6">    </span>
<span id="cb114-7">    <span># Set Valuation engine</span></span>
<span id="cb114-8">    bond_engine <span>=</span> ql.DiscountingBondEngine (yield_curve_bumped_handle)</span>
<span id="cb114-9">    fixed_rate_bond.SetPricingEngine (bond_engine)</span>
<span id="cb114-10">    bond_clean_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb114-11">    <span>return</span> bond_clean_price</span>
```

```latex
<span id="cb115-1"><span># Create risk free bond engine</span></span>
<span id="cb115-2">bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)</span>
<span id="cb115-3"></span>
<span id="cb115-4"><span># Set yield conventions</span></span>
<span id="cb115-5">compounding <span>=</span> ql. Compounded</span>
<span id="cb115-6">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb115-7"></span>
<span id="cb115-8"><span># Pick 3 corporate bonds (at your discretion)</span></span>
<span id="cb115-9">corp_combined_small <span>=</span> corp_combined[:<span>3</span>]. Copy ()</span>
<span id="cb115-10"></span>
<span id="cb115-11"><span># Calculate prices with zspreads</span></span>
<span id="cb115-12">bond_zspread_prices <span>=</span> []</span>
<span id="cb115-13"></span>
<span id="cb115-14"><span>for</span> index,  row <span>in</span> corp_combined_small.Iterrows ():</span>
<span id="cb115-15">    </span>
<span id="cb115-16">    bond_object <span>=</span> create_bond_from_symbology (row)    </span>
<span id="cb115-17">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb115-18">        </span>
<span id="cb115-19">    bond_zspread_price <span>=</span> calc_clean_price_with_zspread (bond_object,  tsy_yield_curve_mid_handle,  row[<span>'calc_zspread'</span>]<span>/</span><span>1 e 4</span>)</span>
<span id="cb115-20">    bond_zspread_prices.Append (bond_zspread_price)</span>
<span id="cb115-21">    </span>
<span id="cb115-22"><span># Validate that you match the original market prices,  which were used as input to the z-Spread function.</span></span>
<span id="cb115-23">corp_combined_small[<span>'bond_zspread_price'</span>] <span>=</span> bond_zspread_prices</span>
<span id="cb115-24">corp_combined_small[<span>'price_difference'</span>] <span>=</span> corp_combined_small[<span>'midPrice'</span>] <span>-</span> corp_combined_small[<span>'bond_zspread_price'</span>]</span>
<span id="cb115-25"></span>
<span id="cb115-26">display (corp_combined_small [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'calc_zspread'</span>,  <span>'midPrice'</span>,  <span>'bond_zspread_price'</span>, <span>'price_difference'</span>]])</span>
```

|  | security | isin | figi | calc_zspread | midPrice | bond_zspread_price | price_difference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL 3.85 05/04/43 | US 037833 AL 42 | BBG 004 HST 0 K 7 | 47.176515 | 82.4440 | 82.4440 | 1.162306 e-10 |
| 1 | AAPL 4.45 05/06/44 | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | 38.561569 | 90.3155 | 90.3155 | 5.357080 e-09 |
| 2 | AAPL 3.45 02/09/45 | US 037833 BA 77 | BBG 0081 TNL 50 | 50.421681 | 76.2525 | 76.2525 | 1.989520 e-13 |

## d. Compute Duration and Convexity for fixed rate corporate bonds (using flat yield)

Compute analytical Duration and Convexity metrics,  as described in Section 7. “Analytical Duration,  Convexity and Z-Spread (flat yield model)” in the QuantLib Basic notebook.

Extend the dataframe with the following calculated risk metrics:

| calc_duration | calc_convexity |
| --- | --- |

Display the head of the dataframe.

```latex
<span id="cb116-1"><span># Create risk free bond engine</span></span>
<span id="cb116-2">bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_mid_handle)</span>
<span id="cb116-3"></span>
<span id="cb116-4"><span># Set yield conventions</span></span>
<span id="cb116-5">compounding <span>=</span> ql. Compounded</span>
<span id="cb116-6">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb116-7"></span>
<span id="cb116-8"><span># Calculate durations and convexities</span></span>
<span id="cb116-9">calc_durations <span>=</span> []</span>
<span id="cb116-10">calc_convexities <span>=</span> []</span>
<span id="cb116-11"></span>
<span id="cb116-12"><span>for</span> index,  row <span>in</span> corp_combined.Iterrows ():</span>
<span id="cb116-13">    </span>
<span id="cb116-14">    bond_object <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb116-15">    bond_object.SetPricingEngine (bond_engine)</span>
<span id="cb116-16">    </span>
<span id="cb116-17">    settle_date <span>=</span> bond_object.SettlementDate (calc_date)</span>
<span id="cb116-18">    day_counter <span>=</span> bond_object.DayCounter ()    </span>
<span id="cb116-19">    </span>
<span id="cb116-20">    bond_yield <span>=</span> bond_object.BondYield (row[<span>'midPrice'</span>],  day_counter,  compounding,  coupon_freq,  settle_date) <span>*</span> <span>100</span></span>
<span id="cb116-21">    </span>
<span id="cb116-22">    flat_int_rate <span>=</span> ql.InterestRate (bond_yield <span>/</span> <span>100</span>,  day_counter,  compounding,  coupon_freq)</span>
<span id="cb116-23">    bond_duration <span>=</span> ql.BondFunctions.Duration (bond_object,  flat_int_rate)</span>
<span id="cb116-24">    bond_convexity <span>=</span> ql.BondFunctions.Convexity (bond_object,  flat_int_rate)        </span>
<span id="cb116-25">    </span>
<span id="cb116-26">    calc_durations.Append (bond_duration)</span>
<span id="cb116-27">    calc_convexities.Append (bond_convexity)</span>
<span id="cb116-28"></span>
<span id="cb116-29"><span># Add new risk columns and display results</span></span>
<span id="cb116-30">corp_combined[<span>'calc_duration'</span>] <span>=</span> calc_durations</span>
<span id="cb116-31">corp_combined[<span>'calc_convexity'</span>] <span>=</span> calc_convexities</span>
<span id="cb116-32"></span>
<span id="cb116-33">display (corp_combined [[<span>'security'</span>,  <span>'isin'</span>,  <span>'figi'</span>,  <span>'midPrice'</span>,  <span>'calc_duration'</span>,  <span>'calc_convexity'</span>]]. head ())</span>
```

|  | security | isin | figi | midPrice | calc_duration | calc_convexity |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | AAPL 3.85 05/04/43 | US 037833 AL 42 | BBG 004 HST 0 K 7 | 82.4440 | 12.457334 | 206.273029 |
| 1 | AAPL 4.45 05/06/44 | US 037833 AT 77 | BBG 006 F 8 VWJ 7 | 90.3155 | 12.495140 | 212.739235 |
| 2 | AAPL 3.45 02/09/45 | US 037833 BA 77 | BBG 0081 TNL 50 | 76.2525 | 13.575123 | 243.879961 |
| 3 | AAPL 4 3/8 05/13/45 | US 037833 BH 21 | BBG 008 N 1 BQC 1 | 87.5195 | 12.825713 | 226.836395 |
| 4 | AAPL 4 1/2 02/23/36 | US 037833 BW 97 | BBG 00 C 7 QBCQ 1 | 95.7170 | 8.978502 | 99.027501 |

```latex
<span id="cb117-1"><span># Visualize duration and convexity for one ticker (for better understanding of risks) [Not part of homework]</span></span>
<span id="cb117-2">corp_combined_aapl <span>=</span> corp_combined[corp_combined[<span>'ticker'</span>] <span>==</span> <span>'AAPL'</span>]</span>
<span id="cb117-3"></span>
<span id="cb117-4">plt <span>=</span> corp_combined_aapl.Plot (x<span>=</span><span>'maturity'</span>,  y<span>=</span>[<span>'calc_duration'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'Duration for AAPL bonds as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb117-5">plt. Set_ylabel (<span>'Duration'</span>)</span>
<span id="cb117-6">plt. Set_xlabel (<span>'Maturity date'</span>)</span>
<span id="cb117-7"></span>
<span id="cb117-8">plt <span>=</span> corp_combined_aapl.Plot (x<span>=</span><span>'maturity'</span>,  y<span>=</span>[<span>'calc_convexity'</span>],  style<span>=</span><span>'*-'</span>,  grid<span>=</span><span>True</span>,  title<span>=</span><span>f'Convexity for AAPL bonds as of </span><span>{</span>as_of_date<span>.</span>date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb117-9">plt. Set_ylabel (<span>'Convexity'</span>)</span>
<span id="cb117-10">plt. Set_xlabel (<span>'Maturity date'</span>)</span>
```

```latex
Text (0.5,  0,  'Maturity date')
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-81-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-81-output-3.png)

---

## From file: 4 Examples_QuantLib_Advanced_FINM_35700_Credit_Markets_Spring 2024

## Credit Markets

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

- Alex Popovici
- alex.popovici@uchicago.edu

## Advanced Usage of QuantLib analytics library

## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1. SOFR Is swap rates and SOFR discount curve calibration
	- 1. SOFR curve calibration (via Bootstrapping)

	- 2. Display the calibrated SOFR discount curve dataframe
	- 3. Plot the calibrated SOFR Zero Rates and Discount Factors curves
	- 4. Validate SOFR calibration by pricing SOFR swaps
- 2. Credit Default Swaps (CDS): calibration + pricing
	- 1. CDS Hazard Rate calibration
	- 2. Plot the calibrated Hazard Rate and Survival Probability curves
	- 3. CDS valuation
- 3. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)
	- 1. Create Corporate Bond
	- 2. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)
	- 3. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)
- 4. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)
	- 1. Create and Display the Custom Credit Curve
	- 2. Price Risky Bond on Custom Credit Curve (with Credit Risk)
- 5. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions
	- 1. Nelson Siegel basis functions
	- 2. Plot Basis Functions for Nelson-Siegel + extensions
	- 3. Constructing smooth Nelson-Siegel hazard rate / survival probability curves
	- 4. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

## 1. SOFR Is swap rates and SOFR discount curve calibration

## a. SOFR curve calibration (via Bootstrapping)

Overnight Index Swap contract is an interest rate swap contract exchanging and overnight index interest rate (e.g. Fed Funds,  SOFR,  LIBOR) for a fixed interest rate until the contract maturity. The fixed rate is set at a rate agreed upon by both parties. The floating leg portion of the swap is compounded and paid at reset dates.

```latex
<span id="cb119-1"><span># Set the static valuation date: 2023-04-14</span></span>
<span id="cb119-2">calc_date <span>=</span> ql.Date (<span>14</span>,  <span>4</span>,  <span>2023</span>)</span>
<span id="cb119-3">ql.Settings.Instance (). EvaluationDate <span>=</span> calc_date</span>
<span id="cb119-4"></span>
<span id="cb119-5"><span># calendar</span></span>
<span id="cb119-6">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb119-7"></span>
<span id="cb119-8"><span># settle_days</span></span>
<span id="cb119-9">settle_days <span>=</span> <span>2</span></span>
<span id="cb119-10"></span>
<span id="cb119-11"><span># SOFR OIS swap tenors: 1 Y,  2 Y,  3 Y,  5 Y 7 Y,  10 Y,  20 Y and 30 Y</span></span>
<span id="cb119-12">SOFR_tenors <span>=</span> [ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> [<span>1</span>,  <span>2</span>,  <span>3</span>,  <span>5</span>,  <span>7</span>,  <span>10</span>,  <span>20</span>,  <span>30</span>]]</span>
<span id="cb119-13">               </span>
<span id="cb119-14"><span># SOFR OIS swap rates (as of 2023-04-14)</span></span>
<span id="cb119-15">SOFR_rates <span>=</span> [<span>4.81</span>,  <span>4.11</span>,  <span>3.73</span>,  <span>3.38</span>,  <span>3.32</span>,  <span>3.26</span>,  <span>3.20</span>,  <span>3.02</span>]</span>
<span id="cb119-16"></span>
<span id="cb119-17">SOFR_OIS_swap_helpers <span>=</span> []</span>
<span id="cb119-18"><span>for</span> (SOFR_tenor,  SOFR_rate) <span>in</span> <span>zip</span>(SOFR_tenors,  SOFR_rates):</span>
<span id="cb119-19">    SOFR_OIS_swap_helpers.Append (ql.OISRateHelper (settle_days,  SOFR_tenor,  ql.QuoteHandle (ql.SimpleQuote (SOFR_rate<span>/</span><span>100</span>)),  ql.Sofr ()))</span>
<span id="cb119-20"></span>
<span id="cb119-21"><span># Create SOFR yield curve</span></span>
<span id="cb119-22">sofr_yield_curve <span>=</span> ql.PiecewiseLinearZero (settle_days,  calendar,  SOFR_OIS_swap_helpers,  ql. Actual 360 ())</span>
<span id="cb119-23">sofr_yield_curve.EnableExtrapolation ()</span>
<span id="cb119-24">sofr_yield_curve_handle <span>=</span> ql.YieldTermStructureHandle (sofr_yield_curve)</span>
<span id="cb119-25"></span>
<span id="cb119-26"><span>print</span>(sofr_yield_curve.ReferenceDate ())</span>
```

```latex
April 18 th,  2023
April 18 th,  2023
```

## b. Display the calibrated SOFR discount curve dataframe

```latex
<span id="cb121-1"><span>def</span> get_yield_curve_details_df (yield_curve,  curve_dates<span>=</span><span>None</span>):</span>
<span id="cb121-2">    </span>
<span id="cb121-3">    <span>if</span>(curve_dates <span>==</span> <span>None</span>):</span>
<span id="cb121-4">        curve_dates <span>=</span> yield_curve.Dates ()</span>
<span id="cb121-5"></span>
<span id="cb121-6">    dates <span>=</span> [d.to_date () <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb121-7">    discounts <span>=</span> [<span>round</span>(yield_curve.Discount (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb121-8">    yearfracs <span>=</span> [<span>round</span>(yield_curve.TimeFromReference (d),  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb121-9">    zeroRates <span>=</span> [<span>round</span>(yield_curve.ZeroRate (d,  yield_curve.DayCounter (),  ql. Compounded). Rate () <span>*</span> <span>100</span>,  <span>3</span>) <span>for</span> d <span>in</span> curve_dates]</span>
<span id="cb121-10"></span>
<span id="cb121-11">    yield_curve_details_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Date'</span>: dates, </span>
<span id="cb121-12">                             <span>'YearFrac'</span>: yearfracs, </span>
<span id="cb121-13">                             <span>'DiscountFactor'</span>: discounts, </span>
<span id="cb121-14">                             <span>'ZeroRate'</span>: zeroRates})                             </span>
<span id="cb121-15">    <span>return</span> yield_curve_details_df</span>
<span id="cb121-16"></span>
<span id="cb121-17"></span>
<span id="cb121-18"></span>
<span id="cb121-19"><span># Display SOFR yield curve</span></span>
<span id="cb121-20">grid_dates <span>=</span> [sofr_yield_curve.ReferenceDate () <span>+</span> ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> <span>list</span>(<span>range</span>(<span>0</span>, <span>30</span>, <span>2</span>))]</span>
<span id="cb121-21"></span>
<span id="cb121-22"></span>
<span id="cb121-23">sofr_yield_curve_simple_df <span>=</span> get_yield_curve_details_df (sofr_yield_curve)                  <span># using calibration grid</span></span>
<span id="cb121-24">sofr_yield_curve_details_df <span>=</span> get_yield_curve_details_df (sofr_yield_curve,  grid_dates)    <span># using external grid</span></span>
<span id="cb121-25"></span>
<span id="cb121-26">display (sofr_yield_curve_simple_df)</span>
<span id="cb121-27">display (sofr_yield_curve_details_df)</span>
```

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2023-04-18 | 0.000 | 1.000 | 4.808 |
| 1 | 2024-04-18 | 1.017 | 0.953 | 4.808 |
| 2 | 2025-04-21 | 2.039 | 0.921 | 4.094 |
| 3 | 2026-04-20 | 3.050 | 0.895 | 3.706 |
| 4 | 2028-04-18 | 5.075 | 0.846 | 3.347 |
| 5 | 2030-04-18 | 7.103 | 0.795 | 3.291 |
| 6 | 2033-04-18 | 10.147 | 0.724 | 3.232 |
| 7 | 2043-04-20 | 20.297 | 0.530 | 3.173 |
| 8 | 2053-04-18 | 30.439 | 0.415 | 2.931 |

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2023-04-18 | 0.000 | 1.000 | 4.808 |
| 1 | 2025-04-18 | 2.031 | 0.922 | 4.100 |
| 2 | 2027-04-18 | 4.058 | 0.869 | 3.527 |
| 3 | 2029-04-18 | 6.089 | 0.820 | 3.319 |
| 4 | 2031-04-18 | 8.117 | 0.770 | 3.272 |
| 5 | 2033-04-18 | 10.147 | 0.724 | 3.232 |
| 6 | 2035-04-18 | 12.175 | 0.680 | 3.221 |
| 7 | 2037-04-18 | 14.206 | 0.638 | 3.209 |
| 8 | 2039-04-18 | 16.233 | 0.600 | 3.197 |
| 9 | 2041-04-18 | 18.264 | 0.564 | 3.185 |
| 10 | 2043-04-18 | 20.292 | 0.530 | 3.173 |
| 11 | 2045-04-18 | 22.322 | 0.503 | 3.125 |
| 12 | 2047-04-18 | 24.350 | 0.478 | 3.076 |
| 13 | 2049-04-18 | 26.381 | 0.455 | 3.028 |
| 14 | 2051-04-18 | 28.408 | 0.434 | 2.979 |

## c. Plot the calibrated SOFR Zero Rates and Discount Factors curves

```latex
<span id="cb122-1">plt <span>=</span> sofr_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'ZeroRate'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'SOFR Curve: Zero Rates'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb122-2">plt. Set_ylabel (<span>'Zero Rate (%)'</span>)</span>
<span id="cb122-3">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb122-4"></span>
<span id="cb122-5">plt <span>=</span> sofr_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'DiscountFactor'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'SOFR Curve: Discount Factors'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb122-6">plt. Set_ylabel (<span>'Discount Factors'</span>)</span>
<span id="cb122-7">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-85-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-85-output-3.png)

## d. Validate SOFR calibration by pricing SOFR swaps

```latex
<span id="cb124-1"><span># validate SOFR swaps</span></span>
<span id="cb124-2">sofr_index <span>=</span> ql.Sofr (sofr_yield_curve_handle)</span>
<span id="cb124-3"><span># swap_engine = ql.DiscountingSwapEngine (sofr_yield_curve_handle)</span></span>
<span id="cb124-4"></span>
<span id="cb124-5"><span>print</span>(<span>'SOFR Swap valuation: PVs should be close to zero!'</span>)</span>
<span id="cb124-6"></span>
<span id="cb124-7"><span>for</span> (SOFR_tenor,  SOFR_rate) <span>in</span> <span>zip</span>(SOFR_tenors,  SOFR_rates):    </span>
<span id="cb124-8">    start_date <span>=</span> calendar.Advance (calc_date,  settle_days,  ql. Days)</span>
<span id="cb124-9">    schedule <span>=</span> ql.MakeSchedule (start_date,  calendar.Advance (start_date,  SOFR_tenor),  ql.Period (<span>'1 Y'</span>),  calendar<span>=</span>calendar)        </span>
<span id="cb124-10">    oisSwap <span>=</span> ql.MakeOIS (SOFR_tenor,  sofr_index,  SOFR_rate<span>/</span><span>100</span>,  nominal<span>=</span><span>100</span>)</span>
<span id="cb124-11">    </span>
<span id="cb124-12">    <span># oisSwap.SetPricingEngine (swap_engine)</span></span>
<span id="cb124-13">    <span>print</span>(<span>'Swap PV for'</span>,  SOFR_tenor,  <span>'tenor /'</span>,  SOFR_rate,  <span>'coupon : '</span>,  oisSwap.NPV ()) </span>
<span id="cb124-14">    </span>
```

```latex
SOFR Swap valuation: PVs should be close to zero!
Swap PV for 1 Y tenor / 4.81 coupon : 0.0
Swap PV for 2 Y tenor / 4.11 coupon : 2.930988785010413 e-14
Swap PV for 3 Y tenor / 3.73 coupon : -4.085620730620576 e-14
Swap PV for 5 Y tenor / 3.38 coupon : -4.033395839542209 e-11
Swap PV for 7 Y tenor / 3.32 coupon : -2.4868995751603507 e-14
Swap PV for 10 Y tenor / 3.26 coupon : 3.552713678800501 e-15
Swap PV for 20 Y tenor / 3.2 coupon : -2.1316282072803006 e-14
Swap PV for 30 Y tenor / 3.02 coupon : -6.394884621840902 e-14
SOFR Swap valuation: PVs should be close to zero!
Swap PV for 1 Y tenor / 4.81 coupon : 0.0
Swap PV for 2 Y tenor / 4.11 coupon : 2.930988785010413 e-14
Swap PV for 3 Y tenor / 3.73 coupon : -4.085620730620576 e-14
Swap PV for 5 Y tenor / 3.38 coupon : -4.033395839542209 e-11
Swap PV for 7 Y tenor / 3.32 coupon : -2.4868995751603507 e-14
Swap PV for 10 Y tenor / 3.26 coupon : 3.552713678800501 e-15
Swap PV for 20 Y tenor / 3.2 coupon : -2.1316282072803006 e-14
Swap PV for 30 Y tenor / 3.02 coupon : -6.394884621840902 e-14
```

## 2. Credit Default Swaps (CDS): calibration + pricing

## a. CDS Hazard Rate calibration

```latex
<span id="cb126-1">CDS_recovery_rate <span>=</span> <span>0.4</span></span>
<span id="cb126-2"></span>
<span id="cb126-3">CDS_day_count <span>=</span> ql. Actual 360 ()</span>
<span id="cb126-4"></span>
<span id="cb126-5"><span># CDS standard tenors: 1 Y,  2 Y,  3 Y,  5 Y 7 Y and 10 Y</span></span>
<span id="cb126-6">CDS_tenors <span>=</span> [ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> [<span>1</span>,  <span>2</span>,  <span>3</span>,  <span>5</span>,  <span>7</span>,  <span>10</span>]]</span>
<span id="cb126-7">              </span>
<span id="cb126-8"><span># CDS spreads for IBM as of calc_date = 2023-04-14</span></span>
<span id="cb126-9">CDS_spreads <span>=</span> [<span>17.25</span>,  <span>24.09</span>,  <span>35.58</span>,  <span>55.58</span>,  <span>70.51</span>,  <span>79.92</span>]</span>
<span id="cb126-10"></span>
<span id="cb126-11">CDS_helpers <span>=</span> [ql.SpreadCdsHelper ((CDS_spread <span>/</span> <span>10000.0</span>),  CDS_tenor,  settle_days,  ql.TARGET (), </span>
<span id="cb126-12">                                  ql. Quarterly,  ql. Following,  ql. DateGeneration. TwentiethIMM,  CDS_day_count,  CDS_recovery_rate,  sofr_yield_curve_handle)</span>
<span id="cb126-13">               </span>
<span id="cb126-14"><span>for</span> (CDS_spread,  CDS_tenor) <span>in</span> <span>zip</span>(CDS_spreads,  CDS_tenors)]</span>
<span id="cb126-15"></span>
<span id="cb126-16"><span># bootstrap hazard_rate_curve</span></span>
<span id="cb126-17">hazard_rate_curve <span>=</span> ql.PiecewiseFlatHazardRate (calc_date,  CDS_helpers,  CDS_day_count)</span>
<span id="cb126-18">hazard_rate_curve.EnableExtrapolation ()</span>
<span id="cb126-19"></span>
<span id="cb126-20"><span># Display calibrated hazard rates and survival probabilities</span></span>
<span id="cb126-21">hazard_list <span>=</span> [(hr[<span>0</span>]. To_date (),  </span>
<span id="cb126-22">                CDS_day_count.YearFraction (calc_date,  hr[<span>0</span>]), </span>
<span id="cb126-23">                hr[<span>1</span>] <span>*</span> <span>100</span>, </span>
<span id="cb126-24">                np.Exp (<span>-</span>hr[<span>1</span>]<span>*</span>CDS_day_count.YearFraction (calc_date,  hr[<span>0</span>])), </span>
<span id="cb126-25">                hazard_rate_curve.SurvivalProbability (hr[<span>0</span>])) <span>for</span> hr <span>in</span> hazard_rate_curve.Nodes ()]</span>
<span id="cb126-26"></span>
<span id="cb126-27">grid_dates,  year_frac,  hazard_rates,  sp_manual,  surv_probs <span>=</span> <span>zip</span>(<span>*</span>hazard_list)</span>
<span id="cb126-28"></span>
<span id="cb126-29">hazard_rates_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Date'</span>: grid_dates,  </span>
<span id="cb126-30">                                     <span>'YearFrac'</span>: year_frac, </span>
<span id="cb126-31">                                     <span>'HazardRate'</span>: hazard_rates, </span>
<span id="cb126-32">                                     <span>'SPManual'</span>: sp_manual, </span>
<span id="cb126-33">                                     <span>'SurvivalProb'</span>: surv_probs})</span>
<span id="cb126-34"><span>print</span>(hazard_rates_df)</span>
```

```latex
         Date   YearFrac  HazardRate  SPManual  SurvivalProb
0  2023-04-14   0.000000    0.285237  1.000000      1.000000
1  2024-06-20   1.202778    0.285237  0.996575      0.996575
2  2025-06-20   2.216667    0.540041  0.988100      0.991133
3  2026-06-22   3.236111    1.033609  0.967104      0.980745
4  2028-06-20   5.261111    1.511140  0.923575      0.951188
5  2030-06-20   7.288889    1.925096  0.869082      0.914772
6  2033-06-20  10.333333    1.803340  0.829987      0.865903
         Date   YearFrac  HazardRate  SPManual  SurvivalProb
0  2023-04-14   0.000000    0.285237  1.000000      1.000000
1  2024-06-20   1.202778    0.285237  0.996575      0.996575
2  2025-06-20   2.216667    0.540041  0.988100      0.991133
3  2026-06-22   3.236111    1.033609  0.967104      0.980745
4  2028-06-20   5.261111    1.511140  0.923575      0.951188
5  2030-06-20   7.288889    1.925096  0.869082      0.914772
6  2033-06-20  10.333333    1.803340  0.829987      0.865903
```

## b. Plot the calibrated Hazard Rate and Survival Probability curves

```latex
<span id="cb128-1">plt <span>=</span> hazard_rates_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'HazardRate'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'IBM Hazard Rates Curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb128-2">plt. Set_ylabel (<span>'Hazard Rate (%)'</span>)</span>
<span id="cb128-3">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb128-4"></span>
<span id="cb128-5">plt <span>=</span> hazard_rates_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'SurvivalProb'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'IBM Survival Probability Curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb128-6">plt. Set_ylabel (<span>'Survival Probability'</span>)</span>
<span id="cb128-7">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-88-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-88-output-3.png)

## c. CDS valuation

```latex
<span id="cb130-1"><span># CDS specs</span></span>
<span id="cb130-2">side <span>=</span> ql. Protection. Seller</span>
<span id="cb130-3"></span>
<span id="cb130-4">face_notional <span>=</span> <span>100</span></span>
<span id="cb130-5"></span>
<span id="cb130-6">contractual_spread <span>=</span> <span>100</span> <span>/</span> <span>10000</span></span>
<span id="cb130-7"></span>
<span id="cb130-8">cds_start_date <span>=</span> ql.Date (<span>14</span>,  <span>4</span>,  <span>2023</span>)</span>
<span id="cb130-9">cds_maturity_date <span>=</span> ql.Date (<span>20</span>,  <span>6</span>,  <span>2028</span>)</span>
<span id="cb130-10"></span>
<span id="cb130-11"><span># Create CDS schedule</span></span>
<span id="cb130-12">cds_schedule <span>=</span> ql.MakeSchedule (cds_start_date,  cds_maturity_date,  ql.Period (<span>'3 M'</span>), </span>
<span id="cb130-13">                            ql. Quarterly,  ql.TARGET (),  ql. Following,  ql. Unadjusted,  ql. DateGeneration. TwentiethIMM)</span>
<span id="cb130-14"></span>
<span id="cb130-15"><span># Create CDS object</span></span>
<span id="cb130-16">cds_obj <span>=</span> ql.CreditDefaultSwap (side,  face_notional,  contractual_spread,  cds_schedule,  ql. Following,  ql. Actual 360 ())</span>
<span id="cb130-17"></span>
<span id="cb130-18"><span># Create CDS Implied Credit Curve and pricing engine</span></span>
<span id="cb130-19">cds_surv_prob_curve_handle <span>=</span> ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)</span>
<span id="cb130-20"></span>
<span id="cb130-21">cds_pricing_engine <span>=</span> ql.MidPointCdsEngine (cds_surv_prob_curve_handle,  CDS_recovery_rate,  sofr_yield_curve_handle)</span>
<span id="cb130-22">cds_obj.SetPricingEngine (cds_pricing_engine)</span>
<span id="cb130-23"></span>
<span id="cb130-24"></span>
<span id="cb130-25"><span># Print CDS valuation results</span></span>
<span id="cb130-26"><span>print</span>(<span>'CDS protection start date: '</span>,  cds_obj.ProtectionStartDate ())</span>
<span id="cb130-27"><span>print</span>(<span>'CDS fair/par spread: '</span>,  <span>round</span>(cds_obj.FairSpread ()<span>*</span><span>10000</span>,  <span>3</span>))</span>
<span id="cb130-28"><span>print</span>(<span>'CDS PV: '</span>,  <span>round</span>(cds_obj.NPV (),  <span>4</span>))    </span>
<span id="cb130-29"><span>print</span>(<span>'CDS Premium Leg PV: '</span>,  <span>round</span>(cds_obj.CouponLegNPV (),  <span>4</span>))</span>
<span id="cb130-30"><span>print</span>(<span>'CDS Default Leg PV'</span>,  <span>round</span>(cds_obj.DefaultLegNPV (),  <span>4</span>))</span>
<span id="cb130-31"><span>print</span>(<span>'Survival Prob. To Maturity: '</span>,  <span>round</span>(hazard_rate_curve.SurvivalProbability (cds_maturity_date),  <span>4</span>))</span>
```

```latex
CDS protection start date: April 14 th,  2023
CDS fair/par spread: 55.502
CDS PV: 2.0855
CDS Premium Leg PV: 4.6868
CDS Default Leg PV -2.6013
Survival Prob. To Maturity: 0.9512
CDS protection start date: April 14 th,  2023
CDS fair/par spread: 55.502
CDS PV: 2.0855
CDS Premium Leg PV: 4.6868
CDS Default Leg PV -2.6013
Survival Prob. To Maturity: 0.9512
```

## 3. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)

## a. Create Corporate Bond

```latex
<span id="cb132-1">issue_date <span>=</span> ql.Date (<span>14</span>,  <span>4</span>,  <span>2023</span>)</span>
<span id="cb132-2">maturity_date <span>=</span> ql.Date (<span>14</span>,  <span>4</span>,  <span>2027</span>)</span>
<span id="cb132-3">coupon_freq <span>=</span> ql. Semiannual</span>
<span id="cb132-4">coupon_term <span>=</span> ql.Period (coupon_freq)</span>
<span id="cb132-5">calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>
<span id="cb132-6">day_count_conv <span>=</span> ql. Unadjusted</span>
<span id="cb132-7">date_generation <span>=</span> ql. DateGeneration. Backward</span>
<span id="cb132-8">month_end <span>=</span> <span>True</span></span>
<span id="cb132-9">schedule <span>=</span> ql.Schedule (issue_date, </span>
<span id="cb132-10">                       maturity_date, </span>
<span id="cb132-11">                       coupon_term, </span>
<span id="cb132-12">                       calendar, </span>
<span id="cb132-13">                       day_count_conv, </span>
<span id="cb132-14">                       day_count_conv, </span>
<span id="cb132-15">                       date_generation, </span>
<span id="cb132-16">                       month_end)</span>
<span id="cb132-17"></span>
<span id="cb132-18"><span># Corp Bonds specs</span></span>
<span id="cb132-19">day_count <span>=</span> ql. Thirty 360 (ql. Thirty 360. USA)</span>
<span id="cb132-20">settlement_days <span>=</span> <span>2</span></span>
<span id="cb132-21">coupon_rate <span>=</span> <span>0.04</span></span>
<span id="cb132-22">coupons <span>=</span> [coupon_rate]</span>
<span id="cb132-23">payment_convention <span>=</span> ql. Unadjusted</span>
<span id="cb132-24"></span>
<span id="cb132-25"><span># Construct the FixedRateBond</span></span>
<span id="cb132-26">face_value <span>=</span> <span>100</span></span>
<span id="cb132-27">fixed_rate_bond <span>=</span> ql.FixedRateBond (</span>
<span id="cb132-28">    settlement_days, </span>
<span id="cb132-29">    face_value, </span>
<span id="cb132-30">    schedule, </span>
<span id="cb132-31">    coupons, </span>
<span id="cb132-32">    day_count, </span>
<span id="cb132-33">    payment_convention)</span>
<span id="cb132-34"></span>
<span id="cb132-35">x <span>=</span> [(cf.Date (),  cf.Amount ()) <span>for</span> cf <span>in</span> fixed_rate_bond.Cashflows ()]</span>
<span id="cb132-36">cf_date,  cf_amount <span>=</span> <span>zip</span>(<span>*</span>x)</span>
<span id="cb132-37">cf_frame <span>=</span> pd.DataFrame (data<span>=</span>{<span>'CashFlowDate'</span>: cf_date,  <span>'CashFlowAmount'</span>: cf_amount})</span>
<span id="cb132-38">display (cf_frame)</span>
```

|  | CashFlowDate | CashFlowAmount |
| --- | --- | --- |
| 0 | October 14 th,  2023 | 2.0 |
| 1 | April 14 th,  2024 | 2.0 |
| 2 | October 14 th,  2024 | 2.0 |
| 3 | April 14 th,  2025 | 2.0 |
| 4 | October 14 th,  2025 | 2.0 |
| 5 | April 14 th,  2026 | 2.0 |
| 6 | October 14 th,  2026 | 2.0 |
| 7 | April 14 th,  2027 | 2.0 |
| 8 | April 14 th,  2027 | 100.0 |

## b. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)

```latex
<span id="cb133-1">compounding <span>=</span> ql. Compounded</span>
<span id="cb133-2"><span># compounding = ql. Continuous</span></span>
<span id="cb133-3"></span>
<span id="cb133-4">day_counter <span>=</span> fixed_rate_bond.DayCounter ()</span>
<span id="cb133-5"></span>
<span id="cb133-6">risk_free_bond_engine <span>=</span> ql.DiscountingBondEngine (sofr_yield_curve_handle)</span>
<span id="cb133-7"></span>
<span id="cb133-8">fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)</span>
<span id="cb133-9">risk_free_bond_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb133-10">risk_free_bond_yield <span>=</span> fixed_rate_bond.BondYield (risk_free_bond_price,  day_counter,  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb133-11"></span>
<span id="cb133-12"><span>print</span>(<span>'risk_free_bond_price: '</span>,  risk_free_bond_price)</span>
<span id="cb133-13"><span>print</span>(<span>'risk_free_bond_yield: '</span>,  risk_free_bond_yield)</span>
```

```latex
Risk_free_bond_price: 101.54536292727956
Risk_free_bond_yield: 3.5807016439305506
Risk_free_bond_price: 101.54536292727956
Risk_free_bond_yield: 3.5807016439305506
```

## c. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)

```latex
<span id="cb135-1"><span># bond_recovery_rate</span></span>
<span id="cb135-2">bond_recovery_rate <span>=</span> <span>0.4</span></span>
<span id="cb135-3"></span>
<span id="cb135-4"><span># cds_curve_risky_bond_engine: using calibrated IBM CDS curve</span></span>
<span id="cb135-5">cds_curve_risky_bond_engine <span>=</span> ql.RiskyBondEngine (cds_surv_prob_curve_handle,  bond_recovery_rate,  sofr_yield_curve_handle)</span>
<span id="cb135-6">fixed_rate_bond.SetPricingEngine (cds_curve_risky_bond_engine)</span>
<span id="cb135-7"></span>
<span id="cb135-8"><span># 3. Calculate intrinsic risky bond on custom survival probability curve</span></span>
<span id="cb135-9">risky_bond_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb135-10">risky_bond_yield <span>=</span> fixed_rate_bond.BondYield (risky_bond_price,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb135-11"></span>
<span id="cb135-12"><span>print</span>(<span>'risky_bond_price: '</span>,  risky_bond_price)</span>
<span id="cb135-13"><span>print</span>(<span>'risky_bond_yield: '</span>,  risky_bond_yield)</span>
<span id="cb135-14"></span>
<span id="cb135-15"><span># Compute the credit I-Spread,  relative to risk-free bond (SOFR curve)</span></span>
<span id="cb135-16">risky_bond_credit_ispread_bps <span>=</span> (risky_bond_yield <span>-</span> risk_free_bond_yield) <span>*</span> <span>100</span></span>
<span id="cb135-17"><span>print</span>(<span>'risky_bond_ispread_bps: '</span>,  risky_bond_credit_ispread_bps)</span>
<span id="cb135-18"></span>
<span id="cb135-19"><span># Calc z-spread</span></span>
<span id="cb135-20">risky_bond_zspread_bps <span>=</span> ql.BondFunctions.ZSpread (fixed_rate_bond,  risky_bond_price,  sofr_yield_curve,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>1 e 4</span></span>
<span id="cb135-21"><span>print</span>(<span>'risky_bond_zspread_bps: '</span>,  risky_bond_zspread_bps)</span>
<span id="cb135-22"></span>
```

```latex
Risky_bond_price: 99.77353776497533
Risky_bond_yield: 4.061950922012331
Risky_bond_ispread_bps: 48.12492780817803
Risky_bond_zspread_bps: 47.38435336049067
Risky_bond_price: 99.77353776497533
Risky_bond_yield: 4.061950922012331
Risky_bond_ispread_bps: 48.12492780817803
Risky_bond_zspread_bps: 47.38435336049067
```

## 4. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)

## a. Create and Display the Custom Credit Curve

```latex
<span id="cb137-1"><span># 2. Create custom survival probability curve</span></span>
<span id="cb137-2">custom_surv_prob_dates <span>=</span> [calc_date <span>+</span> ql.Period (T ,  ql. Years) <span>for</span> T <span>in</span> <span>range</span>(<span>11</span>)]</span>
<span id="cb137-3">custom_average_hazard_rates <span>=</span> [<span>0.0030</span>,  <span>0.0060</span>,  <span>0.0090</span>,  <span>0.0110</span>,  <span>0.0125</span>,  <span>0.0140</span>,  <span>0.0150</span>,  <span>0.0160</span>,  <span>0.0170</span>,  <span>0.0180</span>,  <span>0.0190</span>]</span>
<span id="cb137-4">custom_surv_prob_levels <span>=</span> [np.Exp (<span>-</span>T <span>*</span> custom_average_hazard_rates[T]) <span>for</span> T <span>in</span> <span>range</span>(<span>11</span>)]</span>
<span id="cb137-5"><span># custom_surv_prob_levels = [1.0,  0.9950,  0.9860,  0.9733,  0.9569,  0.9370,  0.9166,  0.8940,  0.8728,  0.8504,  0.8269]</span></span>
<span id="cb137-6"></span>
<span id="cb137-7"><span># custom_surv_prob_curve</span></span>
<span id="cb137-8">custom_surv_prob_curve <span>=</span> ql.SurvivalProbabilityCurve (custom_surv_prob_dates,  custom_surv_prob_levels,  ql. Actual 360 (),  ql.TARGET ())</span>
<span id="cb137-9">custom_surv_prob_curve.EnableExtrapolation ()</span>
<span id="cb137-10">custom_surv_prob_curve_handle <span>=</span> ql.DefaultProbabilityTermStructureHandle (custom_surv_prob_curve)</span>
<span id="cb137-11"></span>
<span id="cb137-12"><span># 3. Display custom credit curve</span></span>
<span id="cb137-13">custom_surv_prob_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Date'</span>: custom_surv_prob_dates, </span>
<span id="cb137-14">                                          <span>'Average Hazard Rates'</span>: custom_average_hazard_rates, </span>
<span id="cb137-15">                                          <span>'Survival Probs'</span>: custom_surv_prob_levels})</span>
<span id="cb137-16"></span>
<span id="cb137-17">plt <span>=</span> custom_surv_prob_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'Average Hazard Rates'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'Custom Hazard Rate Curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb137-18">plt. Set_ylabel (<span>'Hazard Rate (%)'</span>)</span>
<span id="cb137-19">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb137-20"></span>
<span id="cb137-21">plt <span>=</span> custom_surv_prob_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'Survival Probs'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>'Custom Survival Probability Curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb137-22">plt. Set_ylabel (<span>'Survival Probability'</span>)</span>
<span id="cb137-23">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-93-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-93-output-3.png)

## b. Price Risky Bond on Custom Credit Curve (with Credit Risk)

```latex
<span id="cb139-1"><span># bond_recovery_rate</span></span>
<span id="cb139-2">bond_recovery_rate <span>=</span> <span>0.4</span></span>
<span id="cb139-3"></span>
<span id="cb139-4"><span># custom_curve_risky_bond_engine</span></span>
<span id="cb139-5">custom_curve_risky_bond_engine <span>=</span> ql.RiskyBondEngine (custom_surv_prob_curve_handle,  bond_recovery_rate,  sofr_yield_curve_handle)</span>
<span id="cb139-6">fixed_rate_bond.SetPricingEngine (custom_curve_risky_bond_engine)</span>
<span id="cb139-7"></span>
<span id="cb139-8"><span># 3. Price risky bond on custom survival probability curve</span></span>
<span id="cb139-9">risky_bond_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb139-10">risky_bond_yield <span>=</span> fixed_rate_bond.BondYield (risky_bond_price,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb139-11"></span>
<span id="cb139-12"><span>print</span>(<span>'risky_bond_price: '</span>,  risky_bond_price)</span>
<span id="cb139-13"><span>print</span>(<span>'risky_bond_yield: '</span>,  risky_bond_yield)</span>
<span id="cb139-14"></span>
<span id="cb139-15"><span># Compute the credit I-Spread,  relative to risk-free bond (SOFR curve)</span></span>
<span id="cb139-16">risky_bond_credit_ispread_bps <span>=</span> (risky_bond_yield <span>-</span> risk_free_bond_yield) <span>*</span> <span>100</span></span>
<span id="cb139-17"><span>print</span>(<span>'risky_bond_ispread_bps: '</span>,  risky_bond_credit_ispread_bps)</span>
<span id="cb139-18"></span>
<span id="cb139-19"><span># Calc z-spread</span></span>
<span id="cb139-20">risky_bond_zspread_bps <span>=</span> ql.BondFunctions.ZSpread (fixed_rate_bond,  risky_bond_price,  sofr_yield_curve,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>1 e 4</span></span>
<span id="cb139-21"><span>print</span>(<span>'risky_bond_zspread_bps: '</span>,  risky_bond_zspread_bps)</span>
<span id="cb139-22"></span>
```

```latex
Risky_bond_price: 98.75601148481836
Risky_bond_yield: 4.342892980575562
Risky_bond_ispread_bps: 76.21913366450114
Risky_bond_zspread_bps: 75.04528626811556
Risky_bond_price: 98.75601148481836
Risky_bond_yield: 4.342892980575562
Risky_bond_ispread_bps: 76.21913366450114
Risky_bond_zspread_bps: 75.04528626811556
```

## 5. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions

## a. Nelson Siegel basis functions

```latex
<span id="cb141-1"><span># nelson_siegel curve shape: Nelson-Siegel</span></span>
<span id="cb141-2"><span>def</span> nelson_siegel (params,  maturity):</span>
<span id="cb141-3">    <span>''' params = (theta 1,  theta 2,  theta 3,  lambda)'''</span>    </span>
<span id="cb141-4">    </span>
<span id="cb141-5">    <span>if</span>(maturity <span>&gt;</span> <span>0</span>):</span>
<span id="cb141-6">        slope_1 <span>=</span> (<span>1</span> <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>]))<span>/</span>(maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb141-7">    <span>else</span>:            </span>
<span id="cb141-8">        slope_1 <span>=</span> <span>1</span></span>
<span id="cb141-9"></span>
<span id="cb141-10">    curvature_1 <span>=</span> slope_1 <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb141-11"></span>
<span id="cb141-12">    total_value <span>=</span> params[<span>0</span>] <span>+</span> params[<span>1</span>] <span>*</span> slope_1 <span>+</span> params[<span>2</span>] <span>*</span> curvature_1</span>
<span id="cb141-13">    </span>
<span id="cb141-14">    <span>return</span> total_value</span>
<span id="cb141-15"></span>
<span id="cb141-16"><span># nelson_siegel_extended curve shape: Nelson-Siegel-Svensson</span></span>
<span id="cb141-17"><span>def</span> nelson_siegel_extended (params,  maturity):</span>
<span id="cb141-18"></span>
<span id="cb141-19">    <span>if</span>(maturity <span>&gt;</span> <span>0</span>):</span>
<span id="cb141-20">        slope_1 <span>=</span> (<span>1</span> <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>]))<span>/</span>(maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb141-21">    <span>else</span>:            </span>
<span id="cb141-22">        slope_1 <span>=</span> <span>1</span></span>
<span id="cb141-23"></span>
<span id="cb141-24">    curvature_1 <span>=</span> slope_1 <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb141-25"></span>
<span id="cb141-26">    total_value <span>=</span> params[<span>0</span>] <span>+</span> params[<span>1</span>] <span>*</span> slope_1 <span>+</span> params[<span>2</span>] <span>*</span> curvature_1    </span>
<span id="cb141-27">    </span>
<span id="cb141-28">    <span>if</span>(params[<span>5</span>] <span>!=</span> <span>0</span>):</span>
<span id="cb141-29">        <span>if</span>(maturity <span>&gt;</span> <span>0</span>):</span>
<span id="cb141-30">            slope_2 <span>=</span> (<span>1</span> <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>5</span>]))<span>/</span>(maturity<span>/</span>params[<span>5</span>])</span>
<span id="cb141-31">        <span>else</span>:</span>
<span id="cb141-32">            slope_2 <span>=</span> <span>1</span></span>
<span id="cb141-33"></span>
<span id="cb141-34">        curvature_2 <span>=</span> slope_2 <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>5</span>])</span>
<span id="cb141-35"></span>
<span id="cb141-36">        total_value <span>=</span> total_value <span>+</span> params[<span>4</span>] <span>*</span> curvature_2</span>
<span id="cb141-37">        </span>
<span id="cb141-38">    </span>
<span id="cb141-39">    <span>return</span> total_value</span>
```

## b. Plot Basis Functions for Nelson-Siegel + extensions

```latex
<span id="cb142-1"></span>
<span id="cb142-2">curve_shapes_df <span>=</span> pd.DataFrame ([T,  nelson_siegel ([<span>1</span>,  <span>0</span>,  <span>0</span>,  <span>2</span>],  T),  </span>
<span id="cb142-3">                                 nelson_siegel ([<span>0</span>,  <span>1</span>,  <span>0</span>,  <span>2</span>],  T),  </span>
<span id="cb142-4">                                 nelson_siegel ([<span>0</span>,  <span>0</span>,  <span>2</span>,  <span>2</span>],  T)] <span>for</span> T <span>in</span> <span>range</span>(<span>0</span>, <span>30</span>, <span>1</span>))</span>
<span id="cb142-5">curve_shapes_df. Columns <span>=</span> [<span>'TTM'</span>,  <span>'Level'</span>,  <span>'Slope'</span>,  <span>'Curvature'</span>]</span>
<span id="cb142-6"></span>
<span id="cb142-7">curve_shapes_df 2 <span>=</span> pd.DataFrame ([T,  nelson_siegel_extended ([<span>1</span>,  <span>0</span>,  <span>0</span>,  <span>2</span>,  <span>0</span>,  <span>0</span>],  T),  </span>
<span id="cb142-8">                                 nelson_siegel_extended ([<span>0</span>,  <span>1</span>,  <span>0</span>,  <span>2</span>,  <span>0</span>,  <span>0</span>],  T),  </span>
<span id="cb142-9">                                 nelson_siegel_extended ([<span>0</span>,  <span>0</span>,  <span>2</span>,  <span>2</span>,  <span>0</span>,  <span>0</span>],  T),  </span>
<span id="cb142-10">                                 nelson_siegel_extended ([<span>0</span>,  <span>0</span>,  <span>0</span>,  <span>2</span>,  <span>1</span>,  <span>10</span>],  T)] <span>for</span> T <span>in</span> <span>range</span>(<span>0</span>, <span>30</span>, <span>1</span>))</span>
<span id="cb142-11">curve_shapes_df 2. Columns <span>=</span> [<span>'TTM'</span>,  <span>'Level'</span>,  <span>'Slope'</span>,  <span>'Curvature_1'</span>,  <span>'Curvature_2'</span>]</span>
<span id="cb142-12"></span>
<span id="cb142-13"><span>print</span>(curve_shapes_df 2.Head ())</span>
<span id="cb142-14"></span>
<span id="cb142-15">plt <span>=</span> curve_shapes_df.Plot (x<span>=</span><span>'TTM'</span>,  y<span>=</span>[<span>'Level'</span>,  <span>'Slope'</span>,  <span>'Curvature'</span>],  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-'</span>,  title<span>=</span><span>'Nelson-Siegel basis functions'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb142-16">plt. Set_ylabel (<span>'Curve Level'</span>)</span>
<span id="cb142-17">plt. Set_xlabel (<span>'Time to maturity (years)'</span>)</span>
<span id="cb142-18"></span>
<span id="cb142-19">plt <span>=</span> curve_shapes_df 2.Plot (x<span>=</span><span>'TTM'</span>,  y<span>=</span>[<span>'Level'</span>,  <span>'Slope'</span>,  <span>'Curvature_1'</span>,  <span>'Curvature_2'</span>],  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-'</span>,  title<span>=</span><span>'Nelson-Siegel-Svensson basis functions'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb142-20">plt. Set_ylabel (<span>'Curve Level'</span>)</span>
<span id="cb142-21">plt. Set_xlabel (<span>'Time to maturity (years)'</span>)</span>
```

```latex
   TTM  Level     Slope  Curvature_1  Curvature_2
0    0    1.0  1.000000     0.000000     0.000000
1    1    1.0  0.786939     0.360816     0.046788
2    2    1.0  0.632121     0.528482     0.087615
3    3    1.0  0.517913     0.589566     0.123121
4    4    1.0  0.432332     0.593994     0.153880
   TTM  Level     Slope  Curvature_1  Curvature_2
0    0    1.0  1.000000     0.000000     0.000000
1    1    1.0  0.786939     0.360816     0.046788
2    2    1.0  0.632121     0.528482     0.087615
3    3    1.0  0.517913     0.589566     0.123121
4    4    1.0  0.432332     0.593994     0.153880
```

```latex
Text (0.5,  0,  'Time to maturity (years)')
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-96-output-3.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-96-output-4.png)

## c. Constructing smooth Nelson-Siegel hazard rate / survival probability curves

```latex
<span id="cb145-1"><span># nelson_siegel_params = [theta 1,  theta 2,  theta 3,  lambda] = [long term level,  short - long slope,  curvature,  lambda]</span></span>
<span id="cb145-2">nelson_siegel_params <span>=</span> [<span>0.0300</span>,  <span>-</span><span>0.0100</span>,  <span>-</span><span>0.0010</span>,  <span>2</span>]</span>
<span id="cb145-3"></span>
<span id="cb145-4">nelson_siegel_surv_prob_dates <span>=</span> [calc_date <span>+</span> ql.Period (T ,  ql. Years) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb145-5">nelson_siegel_average_hazard_rates <span>=</span> [nelson_siegel (nelson_siegel_params,  T) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb145-6">nelson_siegel_surv_prob_levels <span>=</span> [np.Exp (<span>-</span>T <span>*</span> nelson_siegel_average_hazard_rates[T]) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb145-7"></span>
<span id="cb145-8"><span># nelson_siegel_surv_prob_curve</span></span>
<span id="cb145-9">nelson_siegel_credit_curve <span>=</span> ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,  nelson_siegel_surv_prob_levels,  ql. Actual 360 (),  ql.TARGET ())</span>
<span id="cb145-10">nelson_siegel_credit_curve.EnableExtrapolation ()</span>
<span id="cb145-11">nelson_siegel_credit_curve_handle <span>=</span> ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)</span>
<span id="cb145-12"></span>
<span id="cb145-13">nelson_siegel_surv_prob_df <span>=</span> pd.DataFrame (data<span>=</span>{<span>'Dates'</span>: nelson_siegel_surv_prob_dates, </span>
<span id="cb145-14">                                          <span>'Average Hazard Rates'</span>: nelson_siegel_average_hazard_rates, </span>
<span id="cb145-15">                                          <span>'Survival Probs'</span>: nelson_siegel_surv_prob_levels})</span>
<span id="cb145-16"><span># print (nelson_siegel_surv_prob_df)</span></span>
<span id="cb145-17"></span>
<span id="cb145-18">plt <span>=</span> nelson_siegel_surv_prob_df.Plot (x<span>=</span><span>'Dates'</span>,  y<span>=</span>[<span>'Average Hazard Rates'</span>],  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-'</span>,  title<span>=</span><span>'Nelson-Siegel smooth hazard rate curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb145-19">plt. Set_ylabel (<span>'Average hazard rate'</span>)</span>
<span id="cb145-20">plt. Set_xlabel (<span>'Maturity'</span>)</span>
<span id="cb145-21"></span>
<span id="cb145-22">plt <span>=</span> nelson_siegel_surv_prob_df.Plot (x<span>=</span><span>'Dates'</span>,  y<span>=</span>[<span>'Survival Probs'</span>],  grid<span>=</span><span>True</span>,  style<span>=</span><span>'-'</span>,  title<span>=</span><span>'Nelson-Siegel smooth survival probability curve'</span>,  figsize<span>=</span>(<span>12</span>, <span>5</span>))</span>
<span id="cb145-23">plt. Set_ylabel (<span>'Survival Prob'</span>)</span>
<span id="cb145-24">plt. Set_xlabel (<span>'Maturity'</span>)</span>
<span id="cb145-25"></span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-97-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-97-output-3.png)

## d. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

```latex
<span id="cb147-1"><span># bond_recovery_rate</span></span>
<span id="cb147-2">bond_recovery_rate <span>=</span> <span>0.4</span></span>
<span id="cb147-3"></span>
<span id="cb147-4"><span># nelson_siegel_risky_bond_engine</span></span>
<span id="cb147-5">nelson_siegel_risky_bond_engine <span>=</span> ql.RiskyBondEngine (nelson_siegel_credit_curve_handle,  bond_recovery_rate,  sofr_yield_curve_handle)</span>
<span id="cb147-6">fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)</span>
<span id="cb147-7"></span>
<span id="cb147-8"><span># Price risky bond using Nelson-Siegel survival probability curve</span></span>
<span id="cb147-9">nelson_siegel_risky_bond_price <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb147-10">nelson_siegel_risky_bond_yield <span>=</span> fixed_rate_bond.BondYield (nelson_siegel_risky_bond_price,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb147-11"></span>
<span id="cb147-12"><span>print</span>(<span>'nelson_siegel_surv_prob_risky_bond_price: '</span>,  nelson_siegel_risky_bond_price)</span>
<span id="cb147-13"><span>print</span>(<span>'nelson_siegel_surv_prob_risky_bond_yield: '</span>,  nelson_siegel_risky_bond_yield)</span>
<span id="cb147-14"></span>
<span id="cb147-15"><span># Compute the credit I-Spread (relative to risk-free SOFR bond)</span></span>
<span id="cb147-16">nelson_siegel_risky_bond_credit_ispread <span>=</span> (nelson_siegel_risky_bond_yield <span>-</span> risk_free_bond_yield) <span>*</span> <span>1 e 2</span></span>
<span id="cb147-17"><span>print</span>(<span>'nelson_siegel_risky_bond_ispread: '</span>,  nelson_siegel_risky_bond_credit_ispread)</span>
<span id="cb147-18"></span>
<span id="cb147-19"><span># Compute z-spread</span></span>
<span id="cb147-20">nelson_siegel_risky_bond_zspread <span>=</span> ql.BondFunctions.ZSpread (fixed_rate_bond,  nelson_siegel_risky_bond_price,  sofr_yield_curve,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>1 e 4</span></span>
<span id="cb147-21"><span>print</span>(<span>'nelson_siegel_risky_bond_zspread: '</span>,  nelson_siegel_risky_bond_zspread)</span>
<span id="cb147-22"></span>
```

```latex
Nelson_siegel_surv_prob_risky_bond_price: 95.95463373300109
Nelson_siegel_surv_prob_risky_bond_yield: 5.134316444396973
Nelson_siegel_risky_bond_ispread: 155.3614800466422
Nelson_siegel_risky_bond_zspread: 152.963531954358
Nelson_siegel_surv_prob_risky_bond_price: 95.95463373300109
Nelson_siegel_surv_prob_risky_bond_yield: 5.134316444396973
Nelson_siegel_risky_bond_ispread: 155.3614800466422
Nelson_siegel_risky_bond_zspread: 152.963531954358
```

---

## From file: 5 FINM_35700_CreditMarkets_Spring 2024_Solution_3

## Homework 3

## FINM 35700 - Spring 2024

### UChicago Financial Mathematics

### Due Date: 2024-04-23

- Alex Popovici
- alex.popovici@uchicago.edu

This homework relies on:

- the SOFR Is symbology file `sofr_swap_symbology`,
- the SOFR swaps market data file `sofr_swaps_market_data_eod` and
- the CDS spreads market data file `cds_market_data_eod`.

| # Problem 1: Risk & Scenario analysis for a fixed rate corporate bond (yield model) ## Use the QuantLib Basic notebook (or previous homeworks) as templates. |
| --- |
| # Problem 2: Perpetual bonds ## a. Price a fixed rate perpetual bond We are interested in a fixed rate perpetual bond (infinite maturity) on a face notional of $100 and semi-annual coupon c. |
| Assuming that the bond has a (continuously componded) yield of y,  what is the fair value price of the bond? |
| For simplicity,  you can assume T+0 settlement and zero accrued. |
| You can use following sympy code (implementing Formula 5 from Session 1) as a starting point. |
| ::: { #14da9a5e .cell execution_count=103} ``` {. Python .cell-code} # import libraries import sympy as sp |
| # define fixed rate bond specs as symbolic variables T = sp.Symbols (‘T’) c = sp.Symbols (‘c’) y = sp.Symbols (‘y’) |
| # define symbolic equation for generic fixed rate bond pv bond_pv_eq = 1 + (c/2 / (sp.Exp (y/2) - 1) - 1 )* (1 - sp.Exp (-T*y)) print (‘Analytic formula for bond_pv:’,  bond_pv_eq) display (bond_pv_eq) ``` |
| ::: {. Cell-output .cell-output-stdout} |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: ::: |
| We start with the formula for pricing a risky fixed rate bond on a face of 100%,  derived in Lecture 1,  formulas [4] and [5]. |
|  |
|  |
|  |
| Remember that the the semi-annual yield is given by: . |
| In the case of the fixed rate perpetual bond,  the bond maturity and cashflows extend to “infinity”,  so the pricing formula simplifies in terms of to |
|  |
| To obtain the fair price on a face of $100,  one has to multiply the formula above by 100: |
| ## b. Perpetual bonds priced “at par” For which yield y does the bond trade “at par”,  i.e. fair value price = $100? |
|  |
| Hence,  the perpetual bond trades “at par” if the smi-annual yield matches the semi-annual coupon c (same result as for “regular” fixed rate bonds). |
| ## c. Duration and DV 01 for a fixed rate perpetual bond Compute Duration and DV 01 of the perpetual bond. |
| ::: { #434ad435 .cell execution_count=104} ``` {. Python .cell-code} # define symbolic equations perpetual_bond_price = c / (sp.Exp (y/2) - 1) / 2 print (‘1. Perpetual bond price (with coupon c):’) display (perpetual_bond_price) |
| # find first and second order derivatives first_order_derivative = perpetual_bond_price.Diff (y) print (‘2. Perpetual bond DV 01:’) display (-first_order_derivative) |
| perpetual_bond_duration = sp.Simplify (- first_order_derivative / perpetual_bond_price) print (‘3. Perpetual bond duration:’) display (perpetual_bond_duration) ``` |
| ::: {. Cell-output .cell-output-stdout} |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: ::: |
| Hence,  PV 01 and duration of a fixed rate perpetual bond are given by |
|  |
|  |
| ## d. Convexity of a fixed rate perpetual bond Compute the convexity of the perpetual bond. |
| ::: { #924fe824 .cell execution_count=105} ``` {. Python .cell-code} second_order_derivative = sp.Simplify (first_order_derivative.Diff (y)) print (‘Second order derivative:’) display (second_order_derivative) |
| perpetual_bond_convexity = sp.Simplify (second_order_derivative / perpetual_bond_price) print (‘Perpetual bond convexity:’) display (perpetual_bond_convexity) |
| ``` |
| ::: {. Cell-output .cell-output-stdout} |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: |
| ::: {. Cell-output .cell-output-display .cell-output-markdown} ::: ::: |
| Hence,  second order derivative and convexity of the fixed rate perpetual bond are given by |
|  |
|  |

## Problem 3: US SOFR swap curve calibration as of 2024-04-15

### Follow Section “1. SOFR Is swap rates and SOFR discount curve calibration + validation” in the QuantLib Advanced notebook

## a. Load and explore US SOFR swaps symbology and market data

Load the `sofr_swap_symbology` Excel file into a dataframe. Print all swap tenors available.

Load the `sofr_swaps_market_data_eod` Excel file into a dataframe. Print all dates available.

Plot the historial time series of SOFR rates for the available [1 Y,  2 Y,  3 Y,  5 Y,  7 Y,  10 Y,  20 Y,  30 Y] tenors.

```latex
<span id="cb149-1"><span># sofr_symbology</span></span>
<span id="cb149-2">sofr_symbology <span>=</span> pd. Read_excel (<span>'./data/sofr_swaps_symbology. Xlsx'</span>)</span>
<span id="cb149-3">sofr_symbology. Set_index (<span>'figi'</span>,  inplace<span>=</span><span>True</span>)</span>
<span id="cb149-4">display (sofr_symbology)</span>
<span id="cb149-5"></span>
<span id="cb149-6"><span># sofr_market_quotes</span></span>
<span id="cb149-7">sofr_market_quotes <span>=</span> pd. Read_excel (<span>'./data/sofr_swaps_market_data_eod. Xlsx'</span>)</span>
<span id="cb149-8"><span># print (sofr_market_quotes.Head ())</span></span>
<span id="cb149-9"></span>
<span id="cb149-10"><span># pivot to get SOFR rates time series</span></span>
<span id="cb149-11">sofr_quotes_ts <span>=</span> sofr_market_quotes.Pivot (index<span>=</span><span>"date"</span>,  columns<span>=</span><span>"figi"</span>,  values<span>=</span><span>"midRate"</span>)</span>
<span id="cb149-12">sofr_quotes_ts. Columns <span>=</span> sofr_symbology. Tenor[sofr_quotes_ts. Columns]</span>
<span id="cb149-13"><span># print (sofr_quotes_ts.Head ())</span></span>
<span id="cb149-14"></span>
<span id="cb149-15">plt <span>=</span> sofr_quotes_ts.Plot (grid<span>=</span><span>True</span>,  style<span>=</span><span>'-'</span>,  title<span>=</span><span>'SOFR Swaps: historical time series'</span>,  figsize<span>=</span>(<span>12</span>, <span>8</span>))</span>
<span id="cb149-16">plt. Set_ylabel (<span>'SOFR Rate'</span>)</span>
<span id="cb149-17">plt. Set_xlabel (<span>'Date'</span>)</span>
```

|  | ticker | class | bbg | name | tenor | type | dcc | exchange | country | currency | status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

| figi |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BBG 00 KFWPJJ 9 | USOSFR 1 | Curncy | USOSFR 1 Curncy | USD Is ANN VS SOFR 1 Y | 1 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPJX 3 | USOSFR 2 | Curncy | USOSFR 2 Curncy | USD Is ANN VS SOFR 2 Y | 2 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPK 15 | USOSFR 3 | Curncy | USOSFR 3 Curncy | USD Is ANN VS SOFR 3 Y | 3 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPK 51 | USOSFR 5 | Curncy | USOSFR 5 Curncy | USD Is ANN VS SOFR 5 Y | 5 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPK 79 | USOSFR 7 | Curncy | USOSFR 7 Curncy | USD Is ANN VS SOFR 7 Y | 7 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPKB 4 | USOSFR 10 | Curncy | USOSFR 10 Curncy | USD Is ANN VS SOFR 10 Y | 10 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPKF 0 | USOSFR 20 | Curncy | USOSFR 20 Curncy | USD Is ANN VS SOFR 20 Y | 20 | SWAP | ACT/360 | NONE | US | USD | ACTV |
| BBG 00 KFWPKH 8 | USOSFR 30 | Curncy | USOSFR 30 Curncy | USD Is ANN VS SOFR 30 Y | 30 | SWAP | ACT/360 | NONE | US | USD | ACTV
|

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-108-output-3.png)

## b. Calibrate the US SOFR yield curve (via bootstrapping)

The function below shows how to calibrate a smooth yield/discount factor curve from SOFR swaps.

Prepare a joint symbology & market dataframe quotes as of 2024-04-15.

Calibrate the SOFR discount factor curve as of 2024-04-15.

Follow section 1 b in the QuantLib Advanced notebook.

```latex
<span id="cb151-1"><span>def</span> calibrate_sofr_curve_from_frame (</span>
<span id="cb151-2">        calc_date: ql. Date, </span>
<span id="cb151-3">        sofr_details: pd. DataFrame, </span>
<span id="cb151-4">        rate_quote_column: <span>str</span>):</span>
<span id="cb151-5">    <span>'''Create a calibrated yield curve from a SOFR details dataframe which includes rate quotes.</span></span>
<span id="cb151-6"><span>    '''</span></span>
<span id="cb151-7">    ql.Settings.Instance (). EvaluationDate <span>=</span> calc_date</span>
<span id="cb151-8"></span>
<span id="cb151-9">    <span># Sort dataframe by maturity</span></span>
<span id="cb151-10">    sorted_details_frame <span>=</span> sofr_details. Sort_values (by<span>=</span><span>'tenor'</span>)    </span>  
<span id="cb151-11">    </span>  
<span id="cb151-12">    <span># settle_days</span></span>  
<span id="cb151-13">    settle_days <span>=</span> <span>2</span></span>  
<span id="cb151-14">    </span>  
<span id="cb151-15">    <span># For US SOFR OIS Swaps </span></span>  
<span id="cb151-16">    day_count <span>=</span> ql. Actual 360 ()</span>  
<span id="cb151-17"></span>  
<span id="cb151-18">    <span># For US SOFR Swaps     </span></span>  
<span id="cb151-19">    calendar <span>=</span> ql.UnitedStates (ql. UnitedStates. GovernmentBond)</span>  
<span id="cb151-20">    </span>  
<span id="cb151-21">    sofr_helpers <span>=</span> []</span>  
<span id="cb151-22">    </span>  
<span id="cb151-23">    <span>for</span> index,  row <span>in</span> sorted_details_frame.Iterrows ():</span>  
<span id="cb151-24">        sofr_quote <span>=</span> row[rate_quote_column]</span>  
<span id="cb151-25">        tenor_in_years <span>=</span> row[<span>'tenor'</span>]</span>  
<span id="cb151-26">        sofr_tenor <span>=</span> ql.Period (tenor_in_years,  ql. Years)</span>  
<span id="cb151-27">        </span>  
<span id="cb151-28">        <span># create sofr_rate_helper</span></span>  
<span id="cb151-29">        sofr_helper <span>=</span> ql.OISRateHelper (settle_days,  sofr_tenor,  ql.QuoteHandle (ql.SimpleQuote (sofr_quote<span>/</span><span>100</span>)),  ql.Sofr ())</span>  
<span id="cb151-30">                        </span>  
<span id="cb151-31">        sofr_helpers.Append (sofr_helper)</span>  
<span id="cb151-32">        </span>  
<span id="cb151-33">    sofr_yield_curve <span>=</span> ql.PiecewiseLinearZero (settle_days,  calendar,  sofr_helpers,  day_count)</span>  
<span id="cb151-34">    sofr_yield_curve.EnableExtrapolation ()</span>  
<span id="cb151-35">    </span>  
<span id="cb151-36">    <span>return</span> sofr_yield_curve</span>
```

```latex
<span id="cb152-1"><span># sofr_combined</span></span>
<span id="cb152-2">sofr_combined <span>=</span> sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes[<span>'date'</span>] <span>==</span> <span>'2024-04-15'</span>],  how<span>=</span><span>'left'</span>,  on<span>=</span>[<span>'figi'</span>])</span>
<span id="cb152-3">display (sofr_combined.Head ())</span>
<span id="cb152-4"></span>
<span id="cb152-5"><span># calibrate SOFR discount curve</span></span>
<span id="cb152-6">sofr_yield_curve <span>=</span> calibrate_sofr_curve_from_frame (calc_date,  sofr_combined,  <span>'midRate'</span>)</span>
<span id="cb152-7">sofr_yield_curve_handle <span>=</span> ql.YieldTermStructureHandle (sofr_yield_curve)</span>
```

|  | figi | ticker | class | bbg | name | tenor | type | dcc | exchange | country | currency | status | date | bidRate | askRate | midRate |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | BBG 00 KFWPJJ 9 | USOSFR 1 | Curncy | USOSFR 1 Curncy | USD Is ANN VS SOFR 1 Y | 1 | SWAP | ACT/360 | NONE | US | USD | ACTV | 2024-04-15 | 5.1898 | 5.1982 | 5.1940 |
| 1 | BBG 00 KFWPJX 3 | USOSFR 2 | Curncy | USOSFR 2 Curncy | USD Is ANN VS SOFR 2 Y | 2 | SWAP | ACT/360 | NONE | US | USD | ACTV | 2024-04-15 | 4.8359 | 4.8431 | 4.8395 |
| 2 | BBG 00 KFWPK 15 | USOSFR 3 | Curncy | USOSFR 3 Curncy | USD Is ANN VS SOFR 3 Y | 3 | SWAP | ACT/360 | NONE | US | USD | ACTV | 2024-04-15 | 4.6071 | 4.6135 | 4.6103 |
| 3 | BBG 00 KFWPK 51 | USOSFR 5 | Curncy | USOSFR 5 Curncy | USD Is ANN VS SOFR 5 Y | 5 | SWAP | ACT/360 | NONE | US | USD | ACTV | 2024-04-15 | 4.3659 | 4.3691 | 4.3675 |
| 4 | BBG 00 KFWPK 79 | USOSFR 7 | Curncy | USOSFR 7 Curncy | USD Is ANN VS SOFR 7 Y | 7 | SWAP | ACT/360 | NONE | US | USD | ACTV | 2024-04-15 | 4.2705 | 4.2735 | 4.2720 |

## c. Display the calibrated SOFR discount curve dataframe

Follow section 1 d (in the QuantLib Advanced notebook) to display the calibration details dataframe.

```latex
<span id="cb153-1"><span># Display and plot SOFR yield curve</span></span>
<span id="cb153-2">grid_dates <span>=</span> [sofr_yield_curve.ReferenceDate () <span>+</span> ql.Period (y,  ql. Years) <span>for</span> y <span>in</span> <span>list</span>(<span>range</span>(<span>0</span>, <span>30</span>, <span>1</span>))]</span>
<span id="cb153-3"></span>
<span id="cb153-4"></span>
<span id="cb153-5">sofr_yield_curve_simple_df <span>=</span> get_yield_curve_details_df (sofr_yield_curve)                  <span># using calibration grid</span></span>
<span id="cb153-6">sofr_yield_curve_details_df <span>=</span> get_yield_curve_details_df (sofr_yield_curve,  grid_dates)    <span># using external grid</span></span>
<span id="cb153-7"></span>
<span id="cb153-8">display (sofr_yield_curve_simple_df)</span>
<span id="cb153-9">display (sofr_yield_curve_details_df)</span>
```

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-17 | 0.000 | 1.000 | 5.192 |
| 1 | 2025-04-17 | 1.014 | 0.950 | 5.192 |
| 2 | 2026-04-17 | 2.028 | 0.909 | 4.829 |
| 3 | 2027-04-19 | 3.047 | 0.872 | 4.592 |
| 4 | 2029-04-17 | 5.072 | 0.806 | 4.339 |
| 5 | 2031-04-17 | 7.100 | 0.745 | 4.241 |
| 6 | 2034-04-17 | 10.144 | 0.660 | 4.183 |
| 7 | 2044-04-18 | 20.294 | 0.441 | 4.120 |
| 8 | 2054-04-17 | 30.436 | 0.320 | 3.814 |

|  | Date | YearFrac | DiscountFactor | ZeroRate |
| --- | --- | --- | --- | --- |
| 0 | 2024-04-17 | 0.000 | 1.000 | 5.192 |
| 1 | 2025-04-17 | 1.014 | 0.950 | 5.192 |
| 2 | 2026-04-17 | 2.028 | 0.909 | 4.829 |
| 3 | 2027-04-17 | 3.042 | 0.872 | 4.594 |
| 4 | 2028-04-17 | 4.058 | 0.838 | 4.466 |
| 5 | 2029-04-17 | 5.072 | 0.806 | 4.339 |
| 6 | 2030-04-17 | 6.086 | 0.774 | 4.290 |
| 7 | 2031-04-17 | 7.100 | 0.745 | 4.241 |
| 8 | 2032-04-17 | 8.117 | 0.715 | 4.222 |
| 9 | 2033-04-17 | 9.131 | 0.687 | 4.203 |
| 10 | 2034-04-17 | 10.144 | 0.660 | 4.183 |
| 11 | 2035-04-17 | 11.158 | 0.633 | 4.177 |
| 12 | 2036-04-17 | 12.175 | 0.608 | 4.171 |
| 13 | 2037-04-17 | 13.189 | 0.584 | 4.164 |
| 14 | 2038-04-17 | 14.203 | 0.561 | 4.158 |
| 15 | 2039-04-17 | 15.217 | 0.538 | 4.152 |
| 16 | 2040-04-17 | 16.233 | 0.517 | 4.146 |
| 17 | 2041-04-17 | 17.247 | 0.497 | 4.139 |
| 18 | 2042-04-17 | 18.261 | 0.477 | 4.133 |
| 19 | 2043-04-17 | 19.275 | 0.459 | 4.127 |
| 20 | 2044-04-17 | 20.292 | 0.441 | 4.120 |
| 21 | 2045-04-17 | 21.306 | 0.426 | 4.090 |
| 22 | 2046-04-17 | 22.319 | 0.411 | 4.059 |
| 23 | 2047-04-17 | 23.333 | 0.398 | 4.028 |
| 24 | 2048-04-17 | 24.350 | 0.385 | 3.998 |
| 25 | 2049-04-17 | 25.364 | 0.373 | 3.967 |
| 26 | 2050-04-17 | 26.378 | 0.361 | 3.936 |
| 27 | 2051-04-17 | 27.392 | 0.350 | 3.906 |
| 28 | 2052-04-17 | 28.408 | 0.340 | 3.875 |
| 29 | 2053-04-17 | 29.422 | 0.330 | 3.844 |

## d. Plot the calibrated US SOFR Zero Interest Rates and Discount Factor curves

Plot the SOFR zero rates and discount factor curves by maturity. Follow section 1 c in the QuantLib Advanced notebook.

```latex
<span id="cb154-1"><span># Plot the SOFR yield curve</span></span>
<span id="cb154-2">plt <span>=</span> sofr_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'ZeroRate'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>f'SOFR Curve: Zero Rates as of </span><span>{</span>calc_date<span>.</span>to_date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb154-3">plt. Set_ylabel (<span>'Zero Rate (%)'</span>)</span>
<span id="cb154-4">plt. Set_xlabel (<span>'Date'</span>)</span>
<span id="cb154-5"></span>
<span id="cb154-6">plt <span>=</span> sofr_yield_curve_details_df.Plot (x<span>=</span><span>'Date'</span>,  y<span>=</span><span>'DiscountFactor'</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*-'</span>,  title<span>=</span><span>f'SOFR Curve: Discount Factors as of </span><span>{</span>calc_date<span>.</span>to_date ()<span>}</span><span>'</span>,  figsize<span>=</span>(<span>12</span>, <span>4</span>))</span>
<span id="cb154-7">plt. Set_ylabel (<span>'Discount Factors'</span>)</span>
<span id="cb154-8">plt. Set_xlabel (<span>'Date'</span>)</span>
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-112-output-2.png)

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-112-output-3.png)

| # Problem 4: CDS Hazard Rate calibration and valuation ## Follow Section “2. CDS Hazard Rate calibration + Pricing” in the QuantLib Advanced notebook !!! |
| --- |
| # Problem 1: Pricing risky bonds in the hazard rate model ## This is building upon - Homework 2 “Problem 2: US Treasury yield curve calibration (On-The-Runs)”,  - Homework 3 “Problem 3: US SOFR swap curve calibration” and - Homework 3 “Problem 4: CDS Hazard Rate calibration”. |
| ## a. Prepare the market data ### Load the symbology + market data dataframes. Calibrate the following curves as of 2024-04-19: - the “on-the-run” US Treasury curve,  - the US SOFR curve and - the IBM CDS hazard rate curve (on the top of SOFR discount curve). |
| ::: { #04a7d030 .cell} ``` {. Python .cell-code} # US Treasury “On-The-Run” yield curve calibration # Follow Homework 2 Problem 2 and populate the US Treasury On-The-Run symbology + market data frame |
| # Load bond_symbology. Xlsx bond_symbology = pd. Read_excel (‘./data/bond_symbology. Xlsx’) bond_symbology = bond_symbology[bond_symbology[‘cpn_type’] == ‘FIXED’] |
| # Add term and TTM columns bond_symbology[‘term’] = (bond_symbology[‘maturity’] - bond_symbology[‘start_date’]). Dt. Days / 365.25 bond_symbology[‘TTM’] = (bond_symbology[‘maturity’] - as_of_date). Dt. Days / 365.25 |
| # Load bond_market_prices_eod bond_market_prices_eod = pd. Read_excel (‘./data/bond_market_prices_eod. Xlsx’) |
| # Add mid prices and yields bond_market_prices_eod[‘midPrice’] = 0.5_(bond_market_prices_eod[‘bidPrice’] + bond_market_prices_eod[‘askPrice’]) bond_market_prices_eod[‘midYield’] = 0.5_(bond_market_prices_eod[‘bidYield’] + bond_market_prices_eod[‘askYield’]) |
| # Load govt_on_the_run,  as of 2024-04-19 govt_on_the_run = pd. Read_excel (‘./data/govt_on_the_run. Xlsx’) |
| # Keep OTR treasuries only govt_on_the_run_simple = govt_on_the_run[~govt_on_the_run[‘ticker’]. Str.Contains (‘B|C’)] |
| # Create symbology for on-the-run treasuries only govt_symbology_otr = bond_symbology[bond_symbology[‘isin’]. Isin (govt_on_the_run_simple[‘isin’])]. Copy () govt_symbology_otr = govt_symbology_otr. Sort_values (by=‘maturity’) |
| # Merge market data as of 2024-04-19 into treasury OTR symbology govt_combined_otr = govt_symbology_otr.Merge (bond_market_prices_eod,  on=[‘class’, ‘ticker’, ‘figi’, ‘isin’]) display (govt_combined_otr.Head ()) |
| # tsy_yield_curve calibration tsy_yield_curve = calibrate_yield_curve_from_frame (calc_date,  govt_combined_otr,  ‘midPrice’) tsy_yield_curve_handle = ql.YieldTermStructureHandle (tsy_yield_curve) |
| ``` |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| ::: { #7f543a3b .cell} ``` {. Python .cell-code} # SOFR risk-free yield curve calibration # Follow Homework 3 Problem 3 and populate the SOFR symbology + market data frame |
| # sofr_symbology sofr_symbology = pd. Read_excel (‘./data/sofr_swaps_symbology. Xlsx’) sofr_symbology. Set_index (‘figi’,  inplace=True) display (sofr_symbology) |
| # sofr_market_quotes sofr_market_quotes = pd. Read_excel (‘./data/sofr_swaps_market_data_eod. Xlsx’) |
| # sofr_combined sofr_combined = sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes[‘date’] == as_of_date],  how=‘left’,  on=[‘figi’]) display (sofr_combined.Head ()) |
| # sofr_yield_curve calibration sofr_yield_curve = calibrate_sofr_curve_from_frame (calc_date,  sofr_combined,  ‘midRate’) sofr_yield_curve_handle = ql.YieldTermStructureHandle (sofr_yield_curve) |
| ``` |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| ::: { #28380123 .cell} ``` {. Python .cell-code} # Credit curve calibration using IBM CDS par spreads # Follow Homework 3 Problem 4 and create the IBM hazard rate curve |
| # cds_market_quotes cds_market_quotes = pd. Read_excel (‘./data/cds_market_data_eod. Xlsx’) |
| # Create par spreads (bps) dataframe par_spread_col_names = [f’par_spread_{n}y’ for n in [1, 2, 3, 5, 7, 10]] cds_par_spreads_df = cds_market_quotes. Set_index (‘date’)[par_spread_col_names] |
| cds_par_spreads = list (cds_par_spreads_df. Loc[as_of_date]) print (cds_par_spreads) |
| # cds_recovery_rate cds_recovery_rate = 0.4 |
| # hazard_rate_curve hazard_rate_curve = calibrate_cds_hazard_rate_curve (calc_date,  sofr_yield_curve_handle,  cds_par_spreads,  cds_recovery_rate) |
| # hazard_rate_curve calibrated to IBM CDS par spreads default_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve) ``` |
| ::: {. Cell-output .cell-output-stdout} |
| ## b. Create the IBM risky bond objects ### Identify the following 3 IBM fixed rate bonds in the symbology table and create the corresponding fixed rate bonds (3 bond objects). |
| - security = ‘IBM 3.3 05/15/26’ / figi = ‘BBG 00 P 3 BLH 05’ - security = ‘IBM 3.3 01/27/27’ / figi = ‘BBG 00 FVNGFP 3’ - security = ‘IBM 3 1/2 05/15/29’ / figi = ‘BBG 00 P 3 BLH 14’ |
| Use the create_bond_from_symbology () function (discussed in from Homework 2,  Problem 1 b) to create the bonds objects. |
| List the bond cashflows using the get_bond_cashflows () function. |
| ::: { #a76c0e59 .cell} ``` {. Python .cell-code} # corp_symbology_ibm corp_symbology_ibm = bond_symbology[(bond_symbology. Ticker == ‘IBM’) & (bond_symbology. Cpn_type == ‘FIXED’)] |
| # corp_combined_ibm corp_combined_ibm = corp_symbology_ibm.Merge (bond_market_prices_eod,  how=‘inner’,  on=[‘class’,  ‘ticker’,  ‘isin’,  ‘figi’]) corp_combined_ibm. Set_index (‘figi’,  inplace=True) |
| # Keep selected IBM bonds only ibm_selected_figis = [‘BBG 00 P 3 BLH 05’,  ‘BBG 00 FVNGFP 3’,  ‘BBG 00 P 3 BLH 14’] ibm_df = corp_combined_ibm. Loc[ibm_selected_figis] |
| display (ibm_df. T) ``` |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| ::: { #6a9cd852 .cell} ``` {. Python .cell-code} # Create ibm_bond_objects ibm_bond_objects = [ create_bond_from_symbology (df_row. To_dict ()) for index,  df_row in ibm_df.Iterrows ()] |
| # List the bond cashflows for i in range (0,  3): print (‘Bond cashflows for’,  ibm_df. Iloc[i][‘security’]) display (get_bond_cashflows (ibm_bond_objects[i],  calc_date)) |
| ``` |
| ::: {. Cell-output .cell-output-stdout} |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| ## c. Compute CDS-implied (intrinsic) prices for the IBM fixd rate bonds |
| Price the 3 IBM bonds using the CDS-calibrated hazard rate curve for IBM (via RiskyBondEngine). |
| Display the clean prices and yields for the 3 test bonds. |
| ::: { #c820515d .cell} ``` {. Python .cell-code} # flat_recovery_rate flat_recovery_rate = 0.40 |
| # Risky bond engine uses the calibrated CDS hazard rate curve for pricing credit default risk risky_bond_engine = ql.RiskyBondEngine (default_prob_curve_handle,  flat_recovery_rate,  tsy_yield_curve_handle) |
| # Model/intrinsic prices and yields ibm_model_prices = [] ibm_model_yields = [] |
| # Print the clean prices and yields for the 3 test bonds for i in range (0,  3): fixed_rate_bond = ibm_bond_objects[i] fixed_rate_bond.SetPricingEngine (risky_bond_engine) |
| corpBondModelPrice = round (fixed_rate_bond.CleanPrice (),  3) corpBondModelYield = round (fixed_rate_bond.BondYield (corpBondModelPrice,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) * 100,  3) |
| ibm_model_prices.Append (corpBondModelPrice) ibm_model_yields.Append (corpBondModelYield) |
| # Display relevant metrics ibm_df[‘modelPrice’] = ibm_model_prices ibm_df[‘modelYield’] = ibm_model_yields |
| display (ibm_df [[‘security’,  ‘modelPrice’,  ‘modelYield’]]) |
| ``` |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| ## d. Compute the “intrinsic” vs market price basis for the IBM bonds |
| Load the market mid prices and yields from the bond market data dataframe as of 2024-04-19. |
| Compute and display the basis between the “CDS-implied intrinsic” vs market prices and yields: |
| - basisPrice = modelPrice - midPrice - basisYield = modelYield - midYield |
| Are the CDS intrinsic prices lower or higher than the bond prices observed on the market? What factors could explain the basis? |
| ::: { #8954d4d1 .cell} ``` {. Python .cell-code} # Compute basis ibm_df[‘basisPrice’] = ibm_df[‘modelPrice’] - ibm_df[‘midPrice’] ibm_df[‘basisYield’] = ibm_df[‘modelYield’] - ibm_df[‘midYield’] |
| # Display relevant metrics display (ibm_df [[‘security’,  ‘midPrice’,  ‘modelPrice’,  ‘basisPrice’,  ‘midYield’,  ‘modelYield’,  ‘basisYield’]]) ``` |
| ::: {. Cell-output .cell-output-display} |
| ```{=html} |
| .dataframe tbody tr th { vertical-align: top; } |
| .dataframe thead th { text-align: right; } |
| ::: ::: |
| CDS-implied,  intrinsic bond prices are higher than bond market prices. |
| Following factors could explain the basis dislocation for the 3 IBM bonds: 1. Hazard Rate curve mismatch: the synthetic CDS credit market is underestimating the credit risk in the IBM issuer curve,  relative to the cash corporate bond market. This opens the opportunity for Bond vs CDS basis arbitrage trades,  as discussed in Session 2. 2. Risk-free yield curve mismatch: the (synthetic) SOFR yield curve is tighter than the (cash) US Treasury curve. This is usually due to a funding differential for cash vs. Synthetic products. 3. Temporarily dislocation: Individual bonds are temporarily dislocated from their “fair value” from the issuer curve (e.g. in a Nelson-Siegel type parametric model). This can happen due to buying vs. Selling imbalance in that particular bond. 4. Liquidity discounts: in general,  less liquid (e.g. off-the-run) bonds trade at a price discount to more liquid (e.g. on-the-run) bonds. This usually causes a liquidty-implied “richer” basis (wider in yield space). |

## Problem 2: Compute scenario sensitivities for risky bonds

## a. Compute scenario IR 01 s and Durations for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Compute the scenario IR 01 and Durations using a ‘-1 bp’ interest rate shock,  as described in Section 6. “Market Data Scenarios” in the QuantLib Basics notebook.

Display the computed scenario IR 01 and Durations.

Remember that IR 01 = Dirty_Price * Duration.

```latex
<span id="cb156-1"><span># Bump interest rate by -1 bps (parallel shift)</span></span>
<span id="cb156-2">interest_rate_scenario_1 bp_down <span>=</span> ql.SimpleQuote (<span>-</span><span>0.0001</span>)</span>
<span id="cb156-3">tsy_yield_curve_handle_1 bp_down <span>=</span> ql.YieldTermStructureHandle (ql.ZeroSpreadedTermStructure (tsy_yield_curve_handle,  ql.QuoteHandle (interest_rate_scenario_1 bp_down)))</span>
<span id="cb156-4">risky_bond_engine_1 bp_down <span>=</span> ql.RiskyBondEngine (default_prob_curve_handle,  flat_recovery_rate,  tsy_yield_curve_handle_1 bp_down)</span>
```

```latex
<span id="cb157-1"><span># Model scenario metrics</span></span>
<span id="cb157-2">ibm_scen_prices_1 bp_down <span>=</span> []</span>
<span id="cb157-3">ibm_scen_IR 01 <span>=</span> []</span>
<span id="cb157-4">ibm_scen_duration <span>=</span> []</span>
<span id="cb157-5"></span>
<span id="cb157-6"></span>
<span id="cb157-7"><span># Calculate IR 01 and duration</span></span>
<span id="cb157-8"><span>for</span> i <span>in</span> <span>range</span>(<span>0</span>,  <span>3</span>):</span>
<span id="cb157-9">    fixed_rate_bond <span>=</span> ibm_bond_objects[i]</span>
<span id="cb157-10">    </span>
<span id="cb157-11">    <span># Calc model dirty price for base case</span></span>
<span id="cb157-12">    fixed_rate_bond.SetPricingEngine (risky_bond_engine)    </span>
<span id="cb157-13">    dirty_price_base <span>=</span> fixed_rate_bond.DirtyPrice ()</span>
<span id="cb157-14">    </span>
<span id="cb157-15">    <span># Scenario: 1 bp down</span></span>
<span id="cb157-16">    fixed_rate_bond.SetPricingEngine (risky_bond_engine_1 bp_down)    </span>
<span id="cb157-17">    price_1 bp_down <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb157-18">    ibm_scen_prices_1 bp_down.Append (price_1 bp_down)</span>
<span id="cb157-19">    </span>
<span id="cb157-20">    <span># Compute scenario IR 01 and duration sensitivities</span></span>
<span id="cb157-21">    price_base <span>=</span> ibm_model_prices[i]</span>
<span id="cb157-22">    ir 01 <span>=</span> (price_1 bp_down <span>-</span> price_base) <span>*</span> <span>1 e 4</span> <span>/</span> <span>100</span></span>
<span id="cb157-23">    duration <span>=</span> ir 01 <span>/</span> dirty_price_base <span>*</span> <span>100</span></span>
<span id="cb157-24"></span>
<span id="cb157-25">    ibm_scen_IR 01.Append (ir 01)</span>
<span id="cb157-26">    ibm_scen_duration.Append (duration)</span>
<span id="cb157-27"></span>
<span id="cb157-28"></span>
<span id="cb157-29"><span># Display relevant metrics</span></span>
<span id="cb157-30">ibm_df[<span>'scen_IR 01'</span>] <span>=</span> ibm_scen_IR 01</span>
<span id="cb157-31">ibm_df[<span>'scen_duration'</span>] <span>=</span> ibm_scen_duration</span>
<span id="cb157-32"></span>
<span id="cb157-33">display (ibm_df [[<span>'security'</span>,  <span>'scen_IR01'</span>,  <span>'scen_duration'</span>]])</span>
```

|  | security | scen_IR 01 | scen_duration |
| --- | --- | --- | --- |

| figi |  |  |  |
| --- | --- | --- | --- |
| BBG 00 P 3 BLH 05 | IBM 3.3 05/15/26 | 1.969808 | 2.015714 |
| BBG 00 FVNGFP 3 | IBM 3.3 01/27/27 | 2.482201 | 2.576234 |
| BBG 00 P 3 BLH 14 | IBM 3 1/2 05/15/29 | 4.326882 | 4.583408
|

## b. Compute analytical DV 01 s and Durations for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Compute and display the analytical IR 01 and Durations

Compare the analytic DV 01 s vs. The scenario IR 01 s. Are they expected to be similar?

```latex
<span id="cb158-1"><span># Analytic metrics</span></span>
<span id="cb158-2">ibm_analytic_durations <span>=</span> []</span>
<span id="cb158-3">ibm_analytic_DV 01 s <span>=</span> []</span>
<span id="cb158-4"></span>
<span id="cb158-5"><span># Calculate IR 01 and duration</span></span>
<span id="cb158-6"><span>for</span> i <span>in</span> <span>range</span>(<span>0</span>,  <span>3</span>):</span>
<span id="cb158-7">    fixed_rate_bond <span>=</span> ibm_bond_objects[i]</span>
<span id="cb158-8">    </span>
<span id="cb158-9">    <span># Calc model dirty price for base case</span></span>
<span id="cb158-10">    fixed_rate_bond.SetPricingEngine (risky_bond_engine)    </span>
<span id="cb158-11">    dirty_price_base <span>=</span> fixed_rate_bond.DirtyPrice ()</span>
<span id="cb158-12">    </span>
<span id="cb158-13">    <span># Compute analytical duration and DV 01</span></span>
<span id="cb158-14">    bond_yield_rate <span>=</span> ql.InterestRate (ibm_model_yields[i]<span>/</span><span>100</span>,  ql.ActualActual (ql. ActualActual. ISMA),  ql. Compounded,  ql. Semiannual)</span>
<span id="cb158-15">    analytic_duration <span>=</span> ql.BondFunctions.Duration (fixed_rate_bond,  bond_yield_rate)</span>
<span id="cb158-16">    analytic_DV 01 <span>=</span> analytic_duration <span>*</span> dirty_price_base <span>/</span><span>100</span> </span>
<span id="cb158-17"></span>
<span id="cb158-18">    ibm_analytic_durations.Append (analytic_duration)</span>
<span id="cb158-19">    ibm_analytic_DV 01 s.Append (analytic_DV 01)</span>
<span id="cb158-20"></span>
<span id="cb158-21"></span>
<span id="cb158-22"><span># Display relevant metrics</span></span>
<span id="cb158-23">ibm_df[<span>'analytic_DV 01'</span>] <span>=</span> ibm_analytic_DV 01 s</span>
<span id="cb158-24">ibm_df[<span>'analytic_duration'</span>] <span>=</span> ibm_analytic_durations</span>
<span id="cb158-25"></span>
<span id="cb158-26">display (ibm_df [[<span>'security'</span>,  <span>'analytic_DV01'</span>,  <span>'analytic_duration'</span>]])</span>
```

|  | security | analytic_DV 01 | analytic_duration |
| --- | --- | --- | --- |

| figi |  |  |  |
| --- | --- | --- | --- |
| BBG 00 P 3 BLH 05 | IBM 3.3 05/15/26 | 1.884085 | 1.927993 |
| BBG 00 FVNGFP 3 | IBM 3.3 01/27/27 | 2.479507 | 2.573438 |
| BBG 00 P 3 BLH 14 | IBM 3 1/2 05/15/29 | 4.223564 | 4.473966
|

```latex
<span id="cb159-1"><span># Compare the analytical DV 01 s vs. The scenario IR 01 s. Are they expected to be similar?</span></span>
<span id="cb159-2">display (ibm_df [[<span>'security'</span>,  <span>'scen_IR01'</span>,  <span>'analytic_DV01'</span>]])</span>
```

|  | security | scen_IR 01 | analytic_DV 01 |
| --- | --- | --- | --- |

| figi |  |  |  |
| --- | --- | --- | --- |
| BBG 00 P 3 BLH 05 | IBM 3.3 05/15/26 | 1.969808 | 1.884085 |
| BBG 00 FVNGFP 3 | IBM 3.3 01/27/27 | 2.482201 | 2.479507 |
| BBG 00 P 3 BLH 14 | IBM 3 1/2 05/15/29 | 4.326882 | 4.223564
|

DV 01 s and IR 01 s are expected to be similar,  since a -1 bp change in the (risk free) interest rate curve causes approximately a -1 bp change in the (risky) bond yield curve.

## c. Compute scenario CS 01 s (credit spread sensitivities) for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Apply a ‘-1 bp’ (parallel shift) scenario to the IBM CDS Par Spread quotes and calibrate the scenario hazard rate curve.

Create a new scenario RiskyBondEngine,  using the scenario hazard rate curve.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped hazard rate curve) to obtain the ‘-1 bp’ scenario CS 01 (credit spread sensitivities).

Compare the scenario CS 01 s vs analytic DV 01 s. Are they expected to be similar?

```latex
<span id="cb160-1"><span># hazard_rate_curve calibration (from IBM CDS par spreads)</span></span>
<span id="cb160-2">cds_par_spreads_1 bp_down <span>=</span> [ps <span>-</span> <span>1</span> <span>for</span> ps <span>in</span> cds_par_spreads]</span>
<span id="cb160-3"><span>print</span>(cds_par_spreads)</span>
<span id="cb160-4"><span>print</span>(cds_par_spreads_1 bp_down)</span>
<span id="cb160-5"></span>
<span id="cb160-6"><span># hazard_rate_curve</span></span>
<span id="cb160-7">hazard_rate_curve_1 bp_down <span>=</span> calibrate_cds_hazard_rate_curve (calc_date,  sofr_yield_curve_handle,  cds_par_spreads_1 bp_down,  cds_recovery_rate)</span>
<span id="cb160-8">default_prob_curve_handle_1 bp_down <span>=</span> ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve_1 bp_down)</span>
<span id="cb160-9"></span>
<span id="cb160-10"><span># Risky bond engine for CDS Par Spread -1 bp scenario</span></span>
<span id="cb160-11">risky_bond_engine_cds_1 bp_down <span>=</span> ql.RiskyBondEngine (default_prob_curve_handle_1 bp_down,  flat_recovery_rate,  tsy_yield_curve_handle)</span>
```

```latex
[12.0769,  17.3082,  24.866,  39.6501,  53.9093,  65.3221]
[11.0769,  16.3082,  23.866,  38.6501,  52.9093,  64.3221]
```

```latex
<span id="cb162-1"><span># Calculate CS 01</span></span>
<span id="cb162-2">ibm_model_cs 01 <span>=</span> []</span>
<span id="cb162-3"></span>
<span id="cb162-4"><span>for</span> i <span>in</span> <span>range</span>(<span>0</span>,  <span>3</span>):</span>
<span id="cb162-5">    fixed_rate_bond <span>=</span> ibm_bond_objects[i]     </span>
<span id="cb162-6">    price_base <span>=</span> ibm_model_prices[i]   </span>
<span id="cb162-7">    </span>
<span id="cb162-8">    <span># set scenario pricing engine</span></span>
<span id="cb162-9">    fixed_rate_bond.SetPricingEngine (risky_bond_engine_cds_1 bp_down)</span>
<span id="cb162-10">    </span>
<span id="cb162-11">    <span># calc credit spread scenario price</span></span>
<span id="cb162-12">    price_cds_1 bp_down <span>=</span> fixed_rate_bond.CleanPrice ()</span>
<span id="cb162-13"></span>
<span id="cb162-14">    <span># calc price diff</span></span>
<span id="cb162-15">    price_diff_cds_1 bp_down <span>=</span> price_cds_1 bp_down <span>-</span> price_base</span>
<span id="cb162-16">    </span>
<span id="cb162-17">    ibm_model_cs 01.Append (price_diff_cds_1 bp_down <span>*</span> <span>1 e 4</span> <span>/</span> <span>100</span>)</span>
<span id="cb162-18"></span>
<span id="cb162-19">ibm_df[<span>'CS 01'</span>] <span>=</span> ibm_model_cs 01</span>
<span id="cb162-20"></span>
<span id="cb162-21"><span># Compare the scenario CS 01 s vs analytic DV 01 s. Are they expected to be similar?</span></span>
<span id="cb162-22">display (ibm_df [[<span>'security'</span>,  <span>'scen_IR01'</span>,  <span>'analytic_DV01'</span>,  <span>'CS01'</span>]])</span>
```

|  | security | scen_IR 01 | analytic_DV 01 | CS 01 |
| --- | --- | --- | --- | --- |

| figi |  |  |  |  |
| --- | --- | --- | --- | --- |
| BBG 00 P 3 BLH 05 | IBM 3.3 05/15/26 | 1.969808 | 1.884085 | 1.970422 |
| BBG 00 FVNGFP 3 | IBM 3.3 01/27/27 | 2.482201 | 2.479507 | 2.516812 |
| BBG 00 P 3 BLH 14 | IBM 3 1/2 05/15/29 | 4.326882 | 4.223564 | 4.297695
|

CS 01 s and DV 01 s are expected to be similar,  since a -1 bp change in the credit spread curve causes approximately a -1 bp change in the (risky) bond yield curve.

## d. Compute scenario REC 01 (recovery rate sensitivity) for the 3 IBM bonds

Use the 3 IBM test bonds defined in Problem 1.

Apply a +1% scenario bump to the IBM recovery rate (bump the flat_recovery_rate parameter by 1%,  from 40% to 41%).

Create a new scenario RiskyBondEngine,  using the scenario new recovery rate.

Reprice the risky bonds on the scenario RiskyBondEngine (using the bumped recovery rate) to obtain the +1% scenario REC 01 (recovery rate sensitivity).

```latex
<span id="cb163-1"><span># Bump recovery rate by 1% up</span></span>
<span id="cb163-2">flat_recovery_rate_1 pct_up <span>=</span> flat_recovery_rate <span>+</span> <span>0.01</span></span>
<span id="cb163-3">risky_bond_engine_rec_1 pct_up <span>=</span> ql.RiskyBondEngine (default_prob_curve_handle,  flat_recovery_rate_1 pct_up,  tsy_yield_curve_handle)</span>
<span id="cb163-4"></span>
<span id="cb163-5"><span># Calculate REC 01</span></span>
<span id="cb163-6">ibm_model_rec 01 <span>=</span> []</span>
<span id="cb163-7"></span>
<span id="cb163-8"><span>for</span> i <span>in</span> <span>range</span>(<span>0</span>,  <span>3</span>):</span>
<span id="cb163-9">    fixed_rate_bond <span>=</span> ibm_bond_objects[i]</span>
<span id="cb163-10">    price_base <span>=</span> ibm_model_prices[i]    </span>
<span id="cb163-11">    </span>
<span id="cb163-12">    <span># set scenario pricing engine</span></span>
<span id="cb163-13">    fixed_rate_bond.SetPricingEngine (risky_bond_engine_rec_1 pct_up)</span>
<span id="cb163-14">    </span>
<span id="cb163-15">    <span># calc price diff</span></span>
<span id="cb163-16">    price_rec_1 pct_up <span>=</span> fixed_rate_bond.CleanPrice ()    </span>
<span id="cb163-17">    price_diff_rec_1 pct_up <span>=</span> price_rec_1 pct_up <span>-</span> price_base</span>
<span id="cb163-18">    </span>
<span id="cb163-19">    ibm_model_rec 01.Append (price_diff_rec_1 pct_up)</span>
<span id="cb163-20"></span>
<span id="cb163-21"><span># Display relevant metrics</span></span>
<span id="cb163-22">ibm_df[<span>'REC 01'</span>] <span>=</span> ibm_model_rec 01</span>
<span id="cb163-23"><span>print</span>(ibm_df [[<span>'security'</span>,  <span>'REC01'</span>]])</span>
```

```latex
                        Security     REC 01
Figi                                      
BBG 00 P 3 BLH 05    IBM 3.3 05/15/26  0.005857
BBG 00 FVNGFP 3    IBM 3.3 01/27/27  0.009410
BBG 00 P 3 BLH 14  IBM 3 1/2 05/15/29  0.029299
```

<table><colgroup><col></colgroup><tbody><tr><td># Problem 3: Perpetual CDS We are interested in a perpetual CDS contract (infinite maturity) on a face notional of $100,  flat interest rate of 4% and coupon of 5% (quarterly payments).</td></tr><tr><td>For simplicity,  we assuming a flat hazard rate of 1% per annum,  a recovery rate of 40%,  T+0 settlement and zero accrued.</td></tr><tr><td>Use the simple CDS valuation formulas derived in Session 3 as a template.</td></tr><tr><td>The value of the perpetual CDS is obtained as a limit case of the simple CDS valuation formulas derived in Session 3,  for <span></span>.</td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td>::: { #72dfd093 .cell} ``` {. Python .cell-code} def calc_perpetual_cds_premium_leg_pv (c,  r,  h,  R,  face): return (c / 4 / (np.Exp ((r+h)/4)-1) * face)</td></tr><tr><td>def calc_perpetual_cds_default_leg_pv (c,  r,  h,  R,  face): return ((1 - R) * h / (r + h) * face)</td></tr><tr><td>def calc_perpetual_cds_pv (c,  r,  h,  R,  face): return (calc_perpetual_cds_premium_leg_pv (c,  r,  h,  R,  face) - calc_perpetual_cds_default_leg_pv (c,  r,  h,  R,  face))</td></tr><tr><td>def calc_perpetual_cds_par_spread (c,  r,  h,  R,  face): return (c * calc_perpetual_cds_default_leg_pv (c,  r,  h,  R,  face) / calc_perpetual_cds_premium_leg_pv (c,  r,  h,  R,  face)) ``` :::</td></tr><tr><td>## a. Compute the fair value of the CDS premium and default legs.</td></tr><tr><td>::: { #4bd5da00 .cell} ``` {. Python .cell-code} # constant model parameters r = 0.04 c = 0.05 h = 0.01 R = 0.40 face = 100</td></tr><tr><td># perpetual_cds_premium_leg_pv perpetual_cds_premium_leg_pv = calc_perpetual_cds_premium_leg_pv (c,  r,  h,  R,  face) print (‘perpetual_cds_premium_leg_pv:’,  round (perpetual_cds_premium_leg_pv,  2))</td></tr><tr><td># perpetual_cds_default_leg_pv perpetual_cds_default_leg_pv = calc_perpetual_cds_default_leg_pv (c,  r,  h,  R,  face) print (‘perpetual_cds_default_leg_pv:’,  round (perpetual_cds_default_leg_pv,  2)) ```</td></tr><tr><td>::: {. Cell-output .cell-output-stdout}</td></tr><tr><td>## b. Compute the CDS PV and the CDS Par Spread.</td></tr><tr><td>::: { #cdaf16cb .cell} ``` {. Python .cell-code} perpetual_cds_pv = calc_perpetual_cds_pv (c,  r,  h,  R,  face) print (‘perpetual_cds_pv:’,  round (perpetual_cds_pv,  2))</td></tr><tr><td>perpetual_cds_par_spread_bps = calc_perpetual_cds_par_spread (c,  r,  h,  R,  face) * 1 e 4 print (‘perpetual_cds_par_spread_bps:’,  round (perpetual_cds_par_spread_bps,  2))</td></tr><tr><td>perpetual_cds_par_spread_approx_bps = (1 - R) * h * 1 e 4 print (‘perpetual_cds_par_spread_approx_bps:’,  round (perpetual_cds_par_spread_approx_bps,  2))</td></tr><tr><td>```</td></tr><tr><td>::: {. Cell-output .cell-output-stdout}</td></tr><tr><td>## c.&nbsp; Compute the following CDS risk sensitivities: - IR 01 (PV sensitivity to Interest Rate change of ‘-1 bp’) - HR 01 (PV sensitivity to Hazard Rate change of ‘-1 bp’) - REC 01 (PV sensitivity to Recovery Rate change of ‘+1%’)</td></tr><tr><td>using the scenario method.</td></tr><tr><td>::: { #52a6323a .cell} ``` {. Python .cell-code} # CDS IR 01 r_1 bp_down = r - 0.0001 perpetual_cds_pv_r_1 bp_down = calc_perpetual_cds_pv (c,  r_1 bp_down,  h,  R,  face) perpetual_cds_ir 01 = perpetual_cds_pv_r_1 bp_down - perpetual_cds_pv print (‘perpetual_cds_ir 01 ($):’,  round (perpetual_cds_ir 01,  2))</td></tr><tr><td># CDS HR 01 h_1 bp_down = h - 0.0001 perpetual_cds_pv_h_1 bp_down = calc_perpetual_cds_pv (c,  r,  h_1 bp_down,  R,  face) perpetual_cds_hr 01 = perpetual_cds_pv_h_1 bp_down - perpetual_cds_pv print (‘perpetual_cds_hr 01 ($):’,  round (perpetual_cds_hr 01,  2))</td></tr><tr><td># CDS CS 01 perpetual_cds_par_spread_h_1 bp_down = calc_perpetual_cds_par_spread (c,  r,  h_1 bp_down,  R,  face) * 1 e 4 perpetual_cds_par_spread_bps_delta = perpetual_cds_par_spread_bps - perpetual_cds_par_spread_h_1 bp_down perpetual_cds_cs 01 = perpetual_cds_hr 01 / perpetual_cds_par_spread_bps_delta print (‘perpetual_cds_cs 01 ($):’,  round (perpetual_cds_cs 01,  2))</td></tr><tr><td># CDS REC 01 R_1 pct_up = R + 0.01 perpetual_cds_pv_R_1 pct_up = calc_perpetual_cds_pv (c,  r,  h,  R_1 pct_up,  face) perpetual_cds_rec 01 = perpetual_cds_pv_R_1 pct_up - perpetual_cds_pv print (‘perpetual_cds_rec 01 ($):’,  round (perpetual_cds_rec 01,  2))</td></tr><tr><td>```</td></tr><tr><td>::: {. Cell-output .cell-output-stdout}</td></tr><tr><td>## d.&nbsp; At what time T does the (implied) default probability over next 10 years drop to 1%?</td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td><span></span></td></tr><tr><td>::: { #389a2b49 .cell}</td></tr><tr><td>::: {. Cell-output .cell-output-stdout}</td></tr></tbody></table>

## Problem 4: Nelson-Siegel model for smooth hazard rate curves

## This exercise implements tsome of the concepts introduced in Lecture 4,  Section 1 “Parametric Hazard Rate Models”

## Follow Section “3. Smooth parametric yield and hazard rate curves: the Nelson-Siegel model” in the QuantLib Advanced notebook

## You can also take a look at Dr. Mark Hendricks Fixed Income notebooks describing the Nelson-Siegel model calibration on US Treasuries (GitHub repo link posted in Canvas)

## a. Prepare the market data as of 2024-04-19

Load the symbology + market data dataframes and create a combined dataframe for for all Verizon (ticker = ‘VZ’) fixed rate (cpn_type == ‘FIXED’) bonds with an outstanding amount greater than $100 MM (amt_out > 100).

Sort the dataframe by bond maturity and display the head of the dataframe.

Plot the VZ yields (Y-axis) by TTM (X-axis).

```latex
<span id="cb165-1"><span># corp_symbology_vz</span></span>
<span id="cb165-2">corp_symbology_vz <span>=</span> bond_symbology[(bond_symbology. Ticker <span>==</span> <span>'VZ'</span>) <span>&amp;</span> (bond_symbology. Cpn_type <span>==</span> <span>'FIXED'</span>) <span>&amp;</span> (bond_symbology. Amt_out <span>&gt;</span> <span>100</span>)]</span>
<span id="cb165-3"></span>
<span id="cb165-4"><span># Create vz_df</span></span>
<span id="cb165-5">vz_df <span>=</span> corp_symbology_vz.Merge (bond_market_prices_eod,  how<span>=</span><span>'inner'</span>,  on<span>=</span>[<span>'class'</span>,  <span>'ticker'</span>,  <span>'isin'</span>,  <span>'figi'</span>])</span>
<span id="cb165-6"></span>
<span id="cb165-7"><span># Sort the dataframe by bond maturity and display the head of the dataframe.</span></span>
<span id="cb165-8">vz_df. Sort_values (<span>'maturity'</span>,  inplace<span>=</span><span>True</span>)</span>
<span id="cb165-9">display (vz_df.Head ())</span>
<span id="cb165-10"></span>
<span id="cb165-11"><span># Plot the VZ yields (Y-axis) by TTM (X-axis).</span></span>
<span id="cb165-12">plt <span>=</span> vz_df.Plot (x<span>=</span><span>'TTM'</span>,  y <span>=</span> <span>'midYield'</span>,  figsize <span>=</span> (<span>12</span>,  <span>6</span>),  title <span>=</span> <span>"VZ Market Yields (pct)"</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*'</span>)</span>
<span id="cb165-13">plt. Set_ylabel (<span>'Bond Yields (pct)'</span>)</span>
<span id="cb165-14">plt. Set_xlabel (<span>'Bond TTM'</span>)</span>
```

|  | ticker | class | figi | isin | und_bench_isin | security | name | type | coupon | cpn_type | … | term | TTM | date | bidPrice | askPrice | accrued | bidYield | askYield | midPrice | midYield |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 39 | VZ | Corp | BBG 00 ZLKTF 09 | US 92343 VGG 32 | US 91282 CKH 33 | VZ 1.45 03/20/26 | VERIZON COMMUNICATIONS | GLOBAL | 1.450 | FIXED | … | 4.993840 | 1.916496 | 2024-04-19 | 92.783 | 92.940 | 0.1335 | 5.484 | 5.392 | 92.8615 | 5.4380 |
| 38 | VZ | Corp | BBG 00 DGYP 877 | US 92343 VDD 38 | US 91282 CKH 33 | VZ 2 5/8 08/15/26 | VERIZON COMMUNICATIONS | GLOBAL | 2.625 | FIXED | … | 10.036961 | 2.321697 | 2024-04-19 | 93.904 | 94.119 | 0.4965 | 5.467 | 5.363 | 94.0115 | 5.4150 |
| 37 | VZ | Corp | BBG 00 G 6 QW 2 B 8 | US 92343 VDY 74 | US 91282 CKJ 98 | VZ 4 1/8 03/16/27 | VERIZON COMMUNICATIONS | GLOBAL | 4.125 | FIXED | … | 9.998631 | 2.904860 | 2024-04-19 | 96.703 | 96.899 | 0.4240 | 5.367 | 5.292 | 96.8010 | 5.3295 |
| 36 | VZ | Corp | BBG 00 SK 3 XVL 1 | US 92343 VFF 67 | US 91282 CKJ 98 | VZ 3 03/22/27 | VERIZON COMMUNICATIONS | GLOBAL | 3.000 | FIXED | … | 7.003422 | 2.921287 | 2024-04-19 | 93.598 | 93.843 | 0.2585 | 5.403 | 5.307 | 93.7205 | 5.3550 |
| 35 | VZ | Corp | BBG 00 ZLKTF 27 | US 92343 VGH 15 | US 91282 CKG 59 | VZ 2.1 03/22/28 | VERIZON COMMUNICATIONS | GLOBAL | 2.100 | FIXED | … | 7.000684 | 3.923340 | 2024-04-19 | 88.334 | 88.624 | 0.1810 | 5.450 | 5.360 | 88.4790 | 5.4050 |

5 rows × 33 columns

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-138-output-3.png)

## b. Create the Nelson-Siegel curve shape (4 parameters) and compute the corresponding SSE function

For a given set of parameters,  write a function to compute the SSE “Sum of Squared Errors” penalty function in price space (defined as sum of squared differences between model and market prices for all Verizon fixed-rate bonds).

For each bond,  compute the bond DV 01,  using Section “9. Analytical Duration” in the QuantLib Basics notebook as a template.

Use 1/DV 01 as SSE weights,  as discussed in Lecture 3. You can ignore the liquidity adjuster for the purpose of this exercise.

```latex
<span id="cb167-1"><span>def</span> nelson_siegel (params,  maturity):</span>
<span id="cb167-2">    <span>''' params = (theta 1,  theta 2,  theta 3,  lambda)'''</span>        </span>
<span id="cb167-3">    <span>if</span>(maturity <span>==</span> <span>0</span> <span>or</span> params[<span>3</span>] <span>&lt;=</span> <span>0</span>):</span>
<span id="cb167-4">        slope_1 <span>=</span> <span>1</span></span>
<span id="cb167-5">        curvature <span>=</span> <span>0</span></span>
<span id="cb167-6">    <span>else</span>:</span>
<span id="cb167-7">        slope_1 <span>=</span> (<span>1</span> <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>]))<span>/</span>(maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb167-8">        curvature <span>=</span> slope_1 <span>-</span> np.Exp (<span>-</span>maturity<span>/</span>params[<span>3</span>])</span>
<span id="cb167-9"></span>
<span id="cb167-10">    total_value <span>=</span> params[<span>0</span>] <span>+</span> params[<span>1</span>] <span>*</span> slope_1 <span>+</span> params[<span>2</span>] <span>*</span> curvature</span>
<span id="cb167-11">    </span>
<span id="cb167-12">    <span>return</span> total_value</span>
<span id="cb167-13"></span>
<span id="cb167-14"><span>def</span> create_nelson_siegel_curve (calc_date,  nelson_siegel_params):</span>
<span id="cb167-15">    <span>''' nelson_siegel_params = (theta 1,  theta 2,  theta 3,  lambda)'''</span>            </span>
<span id="cb167-16">    nelson_siegel_surv_prob_dates <span>=</span> [calc_date <span>+</span> ql.Period (T ,  ql. Years) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb167-17">    nelson_siegel_average_hazard_rates <span>=</span> [nelson_siegel (nelson_siegel_params,  T) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb167-18">    nelson_siegel_surv_prob_levels <span>=</span> [np.Exp (<span>-</span>T <span>*</span> nelson_siegel_average_hazard_rates[T]) <span>for</span> T <span>in</span> <span>range</span>(<span>31</span>)]</span>
<span id="cb167-19">    </span>
<span id="cb167-20">    <span># cap and floor survival probs</span></span>
<span id="cb167-21">    nelson_siegel_surv_prob_levels <span>=</span> [<span>max</span>(<span>min</span>(x, <span>1</span>), <span>1 e-8</span>) <span>for</span> x <span>in</span> nelson_siegel_surv_prob_levels]</span>
<span id="cb167-22"></span>
<span id="cb167-23">    <span># nelson_siegel_surv_prob_curve</span></span>
<span id="cb167-24">    nelson_siegel_credit_curve <span>=</span> ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,  nelson_siegel_surv_prob_levels,  ql. Actual 360 (),  ql.TARGET ())</span>
<span id="cb167-25">    nelson_siegel_credit_curve.EnableExtrapolation ()</span>
<span id="cb167-26">    nelson_siegel_credit_curve_handle <span>=</span> ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)</span>
<span id="cb167-27">    </span>
<span id="cb167-28">    <span>return</span>(nelson_siegel_credit_curve_handle)</span>
<span id="cb167-29"></span>
<span id="cb167-30"></span>
<span id="cb167-31"><span>def</span> calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,  </span>
<span id="cb167-32">                      calc_date,  </span>
<span id="cb167-33">                      fixed_rate_bond_objects,  </span>
<span id="cb167-34">                      tsy_yield_curve_handle,  </span>
<span id="cb167-35">                      bond_recovery_rate <span>=</span> <span>0.4</span>):</span>
<span id="cb167-36">    </span>
<span id="cb167-37">    <span># nelson_siegel_surv_prob_curve_handle</span></span>
<span id="cb167-38">    nelson_siegel_surv_prob_curve_handle <span>=</span> create_nelson_siegel_curve (calc_date,  nelson_siegel_params)</span>
<span id="cb167-39">    </span>
<span id="cb167-40">    <span># nelson_siegel_risky_bond_engine</span></span>
<span id="cb167-41">    nelson_siegel_risky_bond_engine <span>=</span> ql.RiskyBondEngine (nelson_siegel_surv_prob_curve_handle,  bond_recovery_rate,  tsy_yield_curve_handle)</span>
<span id="cb167-42">    </span>
<span id="cb167-43">    bond_model_prices <span>=</span> []</span>
<span id="cb167-44">    bond_model_yields <span>=</span> []</span>
<span id="cb167-45">    </span>
<span id="cb167-46">    <span>for</span> fixed_rate_bond <span>in</span> fixed_rate_bond_objects:</span>
<span id="cb167-47">        fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)</span>
<span id="cb167-48">        </span>
<span id="cb167-49">        bond_price <span>=</span> fixed_rate_bond.CleanPrice ()                </span>
<span id="cb167-50">        bond_yield <span>=</span> fixed_rate_bond.BondYield (bond_price,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb167-51">        </span>
<span id="cb167-52">        bond_model_prices.Append (bond_price)</span>
<span id="cb167-53">        bond_model_yields.Append (bond_yield)</span>
<span id="cb167-54">    </span>
<span id="cb167-55">    <span>return</span>(bond_model_prices,  bond_model_yields)</span>
<span id="cb167-56"></span>
<span id="cb167-57"><span>def</span> nelson_siegel_sse (nelson_siegel_params,  </span>
<span id="cb167-58">                      calc_date,  </span>
<span id="cb167-59">                      fixed_rate_bond_objects,  </span>
<span id="cb167-60">                      market_prices,  </span>
<span id="cb167-61">                      calib_weights, </span>
<span id="cb167-62">                      tsy_yield_curve_handle,  </span>
<span id="cb167-63">                      bond_recovery_rate <span>=</span> <span>0.4</span>):</span>
<span id="cb167-64">    </span>
<span id="cb167-65">    <span># bond_model_prices</span></span>
<span id="cb167-66">    bond_model_prices,  bond_model_yields <span>=</span> calculate_nelson_siegel_model_prices_and_yields (nelson_siegel_params,  </span>
<span id="cb167-67">                      calc_date,  </span>
<span id="cb167-68">                      fixed_rate_bond_objects,  </span>
<span id="cb167-69">                      tsy_yield_curve_handle,  </span>
<span id="cb167-70">                      bond_recovery_rate)</span>
<span id="cb167-71">    <span># sse    </span></span>
<span id="cb167-72">    sse <span>=</span> <span>0</span></span>
<span id="cb167-73">    </span>
<span id="cb167-74">    <span>for</span> i <span>in</span> <span>range</span>(<span>len</span>(market_prices)):</span>
<span id="cb167-75">        model_error <span>=</span> market_prices[i] <span>-</span> bond_model_prices[i]                </span>
<span id="cb167-76">        sse <span>+=</span> model_error <span>*</span> model_error <span>*</span> calib_weights[i]                        </span>
<span id="cb167-77">    </span>
<span id="cb167-78">    <span>return</span>(sse)    </span>
<span id="cb167-79"></span>
<span id="cb167-80"></span>
<span id="cb167-81"><span>def</span> create_bonds_and_weights (bond_details,  tsy_yield_curve_handle):</span>
<span id="cb167-82">    </span>
<span id="cb167-83">    <span># risk_free_bond_engine</span></span>
<span id="cb167-84">    risk_free_bond_engine <span>=</span> ql.DiscountingBondEngine (tsy_yield_curve_handle)</span>
<span id="cb167-85"></span>
<span id="cb167-86"></span>
<span id="cb167-87">    fixed_rate_bond_objects <span>=</span> []</span>
<span id="cb167-88">    bond_market_prices <span>=</span> []    </span>
<span id="cb167-89">    bond_yields <span>=</span> []</span>
<span id="cb167-90">    bond_DV 01 s <span>=</span> []    </span>
<span id="cb167-91">    bond_durations <span>=</span> []    </span>
<span id="cb167-92">    </span>
<span id="cb167-93">    <span>for</span> index,  row <span>in</span> bond_details.Iterrows ():</span>
<span id="cb167-94">        fixed_rate_bond <span>=</span> create_bond_from_symbology (row)</span>
<span id="cb167-95">        fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)</span>
<span id="cb167-96">        </span>
<span id="cb167-97">        fixed_rate_bond_objects.Append (fixed_rate_bond)</span>
<span id="cb167-98">        </span>
<span id="cb167-99">        bond_price <span>=</span> row[<span>'midPrice'</span>]                </span>
<span id="cb167-100">        bond_yield <span>=</span> fixed_rate_bond.BondYield (bond_price,  ql. Thirty 360 (ql. Thirty 360. USA),  ql. Compounded,  ql. Semiannual) <span>*</span> <span>100</span></span>
<span id="cb167-101">        bond_yield_rate <span>=</span> ql.InterestRate (bond_yield<span>/</span><span>100</span>,  ql.ActualActual (ql. ActualActual. ISMA),  ql. Compounded,  ql. Semiannual)</span>
<span id="cb167-102">        bond_duration <span>=</span> ql.BondFunctions.Duration (fixed_rate_bond,  bond_yield_rate)</span>
<span id="cb167-103">        bond_DV 01   <span>=</span> fixed_rate_bond.DirtyPrice () <span>*</span> bond_duration</span>
<span id="cb167-104">        </span>
<span id="cb167-105">        bond_market_prices.Append (bond_price)</span>
<span id="cb167-106">        bond_yields.Append (bond_yield)</span>
<span id="cb167-107">        bond_DV 01 s.Append (bond_DV 01)</span>
<span id="cb167-108">        bond_durations.Append (bond_duration)   </span>
<span id="cb167-109">             </span>
<span id="cb167-110">    calib_weights <span>=</span> [<span>1</span> <span>/</span> d <span>for</span> d <span>in</span> bond_DV 01 s]</span>
<span id="cb167-111">    </span>
<span id="cb167-112">    sum_calib_weights <span>=</span> <span>sum</span>(calib_weights)</span>
<span id="cb167-113">    calib_weights <span>=</span> [x <span>/</span> sum_calib_weights <span>for</span> x <span>in</span> calib_weights]</span>
<span id="cb167-114">    </span>
<span id="cb167-115">    <span>return</span>(fixed_rate_bond_objects,  calib_weights,  bond_market_prices,  bond_yields,  bond_DV 01 s,  bond_durations)</span>
```

```latex
<span id="cb168-1"><span># bond_recovery_rate</span></span>
<span id="cb168-2">bond_recovery_rate <span>=</span> <span>0.4</span></span>
<span id="cb168-3"></span>
<span id="cb168-4"><span># initial_nelson_siegel_params</span></span>
<span id="cb168-5">initial_nelson_siegel_params <span>=</span> [<span>0.03</span>,  <span>-</span><span>0.01</span>,  <span>0.02</span>,  <span>5.0</span>]</span>
<span id="cb168-6"><span>print</span>(<span>'initial_nelson_siegel_params: '</span>,  initial_nelson_siegel_params)</span>
<span id="cb168-7"></span>
<span id="cb168-8">fixed_rate_bond_objects,  calib_weights,  bond_market_prices,  bond_yields,  bond_DV 01 s,  bond_durations <span>=</span> create_bonds_and_weights (vz_df,  tsy_yield_curve_handle)</span>
<span id="cb168-9">vz_df[<span>'duration'</span>] <span>=</span> bond_durations</span>
<span id="cb168-10">vz_df[<span>'calib_weight'</span>] <span>=</span> calib_weights</span>
<span id="cb168-11"></span>
<span id="cb168-12">init_bond_model_prices,  init_bond_model_yields <span>=</span> calculate_nelson_siegel_model_prices_and_yields (initial_nelson_siegel_params,  calc_date,  fixed_rate_bond_objects,  tsy_yield_curve_handle,  bond_recovery_rate)</span>
<span id="cb168-13">vz_df[<span>'initModelPrice'</span>] <span>=</span> init_bond_model_prices</span>
<span id="cb168-14">vz_df[<span>'initModelYield'</span>] <span>=</span> init_bond_model_yields</span>
<span id="cb168-15"></span>
<span id="cb168-16">display (vz_df [[<span>'security'</span>,  <span>'midPrice'</span>,  <span>'initModelPrice'</span>,  <span>'calib_weight'</span>]]. head ())</span>
<span id="cb168-17"></span>
<span id="cb168-18"><span># initial_sse</span></span>
<span id="cb168-19">initial_sse <span>=</span> nelson_siegel_sse (initial_nelson_siegel_params,  calc_date,  fixed_rate_bond_objects,  bond_market_prices,  calib_weights,  tsy_yield_curve_handle,  bond_recovery_rate)</span>
<span id="cb168-20"><span>print</span>(<span>'initial_sse ='</span>,  initial_sse)</span>
```

```latex
Initial_nelson_siegel_params: [0.03,  -0.01,  0.02,  5.0]
Initial_sse = 25.591932200527502
```

|  | security | midPrice | initModelPrice | calib_weight |
| --- | --- | --- | --- | --- |
| 39 | VZ 1.45 03/20/26 | 92.8615 | 90.983573 | 0.089548 |
| 38 | VZ 2 5/8 08/15/26 | 94.0115 | 91.761390 | 0.073728 |
| 37 | VZ 4 1/8 03/16/27 | 96.8010 | 93.959994 | 0.058387 |
| 36 | VZ 3 03/22/27 | 93.7205 | 91.109042 | 0.059143 |
| 35 | VZ 2.1 03/22/28 | 88.4790 | 85.516537 | 0.046217 |

## c. Calibrate the Nelson-Siegel model parameters to obtain the smooth Verizon credit curve

Use the US “on-the-run” Treasury yield curve (already calibrated in Problem 1) for risk-free discounting.

Minimize the SSE (pricing error) function to obtain the optimal/calibrated Nelson-Siegel parameter vector.

Create the calibrated/smooth credit curve corresponding to the optimal model parameters.

```latex
<span id="cb170-1"><span>from</span> scipy. Optimize <span>import</span> minimize</span>
<span id="cb170-2"></span>
<span id="cb170-3"><span>def</span> calibrate_nelson_siegel_model (initial_nelson_siegel_params, </span>
<span id="cb170-4">                                  calc_date,  </span>
<span id="cb170-5">                                  bond_details,  </span>
<span id="cb170-6">                                  tsy_yield_curve_handle,  </span>
<span id="cb170-7">                                  bond_recovery_rate <span>=</span> <span>0.4</span>):</span>
<span id="cb170-8">    <span># create_bonds_and_weights</span></span>
<span id="cb170-9">    fixed_rate_bond_objects,  calib_weights,  bond_market_prices,  bond_yields,  bond_DV 01 s,  bond_durations <span>=</span> create_bonds_and_weights (bond_details,  tsy_yield_curve_handle)</span>
<span id="cb170-10">    </span>
<span id="cb170-11">    <span># start calibration</span></span>
<span id="cb170-12">    param_bounds <span>=</span> [(<span>1 e-3</span>,  <span>0.1</span>),  (<span>-</span><span>0.1</span>,  <span>0.1</span>),  (<span>-</span><span>0.1</span>,  <span>0.1</span>),  (<span>1 e-3</span>,  <span>10</span>)]</span>
<span id="cb170-13">            </span>
<span id="cb170-14">    calib_results <span>=</span> minimize (nelson_siegel_sse, </span>
<span id="cb170-15">                                            initial_nelson_siegel_params,  </span>
<span id="cb170-16">                                            args <span>=</span> (calc_date,  </span>
<span id="cb170-17">                                                    fixed_rate_bond_objects,  </span>
<span id="cb170-18">                                                    bond_market_prices,  </span>
<span id="cb170-19">                                                    calib_weights, </span>
<span id="cb170-20">                                                    tsy_yield_curve_handle,  </span>
<span id="cb170-21">                                                    bond_recovery_rate), </span>
<span id="cb170-22">                                            bounds <span>=</span> param_bounds)</span>
<span id="cb170-23"></span>
<span id="cb170-24"></span>
<span id="cb170-25">    <span>return</span>(calib_results)</span>
<span id="cb170-26"></span>
```

```latex
<span id="cb171-1"><span># calibrate_nelson_siegel_model</span></span>
<span id="cb171-2">calib_results <span>=</span> calibrate_nelson_siegel_model (initial_nelson_siegel_params,  calc_date,  vz_df,  tsy_yield_curve_handle,  bond_recovery_rate)</span>
<span id="cb171-3"><span>print</span>(calib_results)</span>
<span id="cb171-4">    </span>
<span id="cb171-5"><span># calib_nelson_siegel_params</span></span>
<span id="cb171-6">calib_nelson_siegel_params <span>=</span> calib_results. X</span>
<span id="cb171-7"><span>print</span>(<span>'calib_nelson_siegel_params: '</span>,  calib_nelson_siegel_params)</span>
<span id="cb171-8"></span>
<span id="cb171-9"><span># calib_nelson_siegel_curve</span></span>
<span id="cb171-10">calib_nelson_siegel_curve <span>=</span> create_nelson_siegel_curve (calc_date,  calib_nelson_siegel_params)</span>
<span id="cb171-11"></span>
<span id="cb171-12"><span># calib_sse</span></span>
<span id="cb171-13">calib_sse <span>=</span> nelson_siegel_sse (calib_nelson_siegel_params,  calc_date,  fixed_rate_bond_objects,  bond_market_prices,  calib_weights,  tsy_yield_curve_handle,  bond_recovery_rate)</span>
<span id="cb171-14"><span>print</span>(<span>'initial_sse ='</span>,  <span>round</span>(initial_sse,  <span>3</span>),  <span>'calib_sse ='</span>,  <span>round</span>(calib_sse,  <span>3</span>))</span>
```

```latex
  Message: CONVERGENCE: REL_REDUCTION_OF_F_&lt;=_FACTR*EPSMCH
  Success: True
   Status: 0
      Fun: 0.20985462025254473
        X: [ 2.115 e-02 -2.079 e-02 -1.998 e-06  2.658 e+00]
      Nit: 45
      Jac: [-3.347 e-04 -4.851 e-05 -5.092 e-05  2.442 e-07]
     Nfev: 285
     Njev: 57
 Hess_inv: &lt; 4 x 4 LbfgsInvHessProduct with dtype=float 64&gt;
Calib_nelson_siegel_params: [ 2.11506077 e-02 -2.07855183 e-02 -1.99811247 e-06  2.65774329 e+00]
Initial_sse = 25.592 calib_sse = 0.21
```

## d. Compute smooth model prices,  yields and “edges”

Price all Verizon bonds on the calibrated credit curve and compute the corresponding model yields and edges.

Add following columns to the dataframe and display the head of the results:

| modelPrice | modelYield | edgePrice | edgeYield |
| --- | --- | --- | --- |

```latex
<span id="cb173-1"><span># Price all Verizon bonds on the calibrated credit curve and compute the corresponding yields.</span></span>
<span id="cb173-2">bond_model_prices,  bond_model_yields <span>=</span> calculate_nelson_siegel_model_prices_and_yields (calib_nelson_siegel_params,  calc_date,  fixed_rate_bond_objects,  tsy_yield_curve_handle,  bond_recovery_rate)</span>
<span id="cb173-3"></span>
<span id="cb173-4">vz_df[<span>'modelPrice'</span>] <span>=</span> bond_model_prices</span>
<span id="cb173-5">vz_df[<span>'modelYield'</span>] <span>=</span> bond_model_yields</span>
<span id="cb173-6">vz_df[<span>'edgePrice'</span>] <span>=</span> vz_df[<span>'modelPrice'</span>] <span>-</span> vz_df[<span>'midPrice'</span>]</span>
<span id="cb173-7">vz_df[<span>'edgeYield'</span>] <span>=</span> vz_df[<span>'modelYield'</span>] <span>-</span> vz_df[<span>'midYield'</span>]</span>
<span id="cb173-8"></span>
<span id="cb173-9">display (vz_df [[<span>'security'</span>,  <span>'midPrice'</span>, <span>'initModelPrice'</span>,  <span>'modelPrice'</span>,  <span>'edgePrice'</span>]]. head ())</span>
<span id="cb173-10">display (vz_df [[<span>'security'</span>,  <span>'midYield'</span>, <span>'initModelYield'</span>,  <span>'modelYield'</span>,  <span>'edgeYield'</span>]]. head ())</span>
```

|  | security | midPrice | initModelPrice | modelPrice | edgePrice |
| --- | --- | --- | --- | --- | --- |
| 39 | VZ 1.45 03/20/26 | 92.8615 | 90.983573 | 92.838491 | -0.023009 |
| 38 | VZ 2 5/8 08/15/26 | 94.0115 | 91.761390 | 93.984611 | -0.026889 |
| 37 | VZ 4 1/8 03/16/27 | 96.8010 | 93.959994 | 96.743183 | -0.057817 |
| 36 | VZ 3 03/22/27 | 93.7205 | 91.109042 | 93.818693 | 0.098193 |
| 35 | VZ 2.1 03/22/28 | 88.4790 | 85.516537 | 88.771584 | 0.292584 |

|  | security | midYield | initModelYield | modelYield | edgeYield |
| --- | --- | --- | --- | --- | --- |
| 39 | VZ 1.45 03/20/26 | 5.4380 | 6.552199 | 5.451398 | 0.013398 |
| 38 | VZ 2 5/8 08/15/26 | 5.4150 | 6.520478 | 5.427663 | 0.012663 |
| 37 | VZ 4 1/8 03/16/27 | 5.3295 | 6.441599 | 5.351789 | 0.022289 |
| 36 | VZ 3 03/22/27 | 5.3550 | 6.391251 | 5.316861 | -0.038139 |
| 35 | VZ 2.1 03/22/28 | 5.4050 | 6.335615 | 5.314845 | -0.090155 |

## e. Visualize the results of the calibrated credit model

Plot the model vs market prices (Y-axis) by maturity (X-axis).

Plot the model vs market yields (Y-axis) by maturity (X-axis).

Plot the edges in yield space (Y-axis) by maturity (X-axis).

What do you think about the quality of the model fit?

```latex
<span id="cb174-1"><span># Plot the model vs market prices (Y-axis) by maturity (X-axis).</span></span>
<span id="cb174-2">plt <span>=</span> vz_df.Plot (x<span>=</span><span>'maturity'</span>,  y <span>=</span> [<span>'midPrice'</span>,  <span>'modelPrice'</span>],  figsize <span>=</span> (<span>12</span>,  <span>6</span>),  title <span>=</span> <span>"Market vs Model Prices"</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*'</span>)</span>
<span id="cb174-3">plt. Set_ylabel (<span>'Bond Prices (pct)'</span>)</span>
<span id="cb174-4">plt. Set_xlabel (<span>'Bond Maturity'</span>)</span>
```

```latex
Text (0.5,  0,  'Bond Maturity')
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-144-output-2.png)

```latex
<span id="cb176-1"><span># Plot the model vs market yields (Y-axis) by maturity (X-axis).</span></span>
<span id="cb176-2">plt <span>=</span> vz_df.Plot (x<span>=</span><span>'maturity'</span>,  y <span>=</span> [<span>'midYield'</span>,  <span>'modelYield'</span>],  figsize <span>=</span> (<span>12</span>,  <span>6</span>),  title <span>=</span> <span>"Market vs Model Yields (pct)"</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*'</span>)</span>
<span id="cb176-3">plt. Set_ylabel (<span>'Bond Yields (pct)'</span>)</span>
<span id="cb176-4">plt. Set_xlabel (<span>'Bond Maturity'</span>)</span>
```

```latex
Text (0.5,  0,  'Bond Maturity')
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-145-output-2.png)

```latex
<span id="cb178-1"><span># Plot the edges in yield space (Y-axis) by maturity (X-axis).</span></span>
<span id="cb178-2">plt <span>=</span> vz_df.Plot (x<span>=</span><span>'maturity'</span>,  y <span>=</span> [<span>'edgeYield'</span>],  figsize <span>=</span> (<span>12</span>,  <span>6</span>),  title <span>=</span> <span>"Model Edges in yield space (pct)"</span>,  grid<span>=</span><span>True</span>,  style<span>=</span><span>'*'</span>)</span>
<span id="cb178-3">plt.Axhline (<span>0</span>,  color<span>=</span><span>'red'</span>,  linestyle<span>=</span><span>'--'</span>,  alpha<span>=</span><span>0.7</span>)</span>
<span id="cb178-4">plt. Set_ylabel (<span>'Yield Edge (pct)'</span>)</span>
<span id="cb178-5">plt. Set_xlabel (<span>'Bond Maturity'</span>)</span>
```

```latex
Text (0.5,  0,  'Bond Maturity')
```

![](file:///Users/rogerlin/Cursor_Projects/Credit_Markets/CreditMarketSolutions_files/figure-html/cell-146-output-2.png)

### What do you think about the quality of the model fit?

Model fit looks good,  given that fact that we are matching closely the market prices of 40 VZ bonds with only 4 Nelson-Siegel model parameters.
