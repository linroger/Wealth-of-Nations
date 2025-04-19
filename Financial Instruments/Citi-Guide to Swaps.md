---
tags:
  - basis_swap
  - cross_currency_swap
  - discounted_cashflows
  - interest_rate_parity
  - ltfx_contract
aliases:
  - Citi Guide
  - Forward Foreign Exchange
  - LTFX
  - POS
  - Swap Pricing
key_concepts:
  - Basis swap definition
  - Common swap structures
  - Long-Dated Foreign Exchange (LTFX)
  - Principal-Only Swap (POS)
  - Swap pricing
---

# Citi: Guide to Swaps
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/59cbb3bf077d183bee84082f8912543ab40beb0fd68755edaf570eb43772404e.jpg)  
Swap Pricing: Discounted Cashflows  
# Common Swap Structures  
- Basis swap (i.e. floating/floating) is one of the basic building block in fixed/fixed and fixed/floating CCS. - A basis swap in this context is defined as the exchange of LIBORs in two different currencies with both initial and final exchange of principal. - Cost of a basis swap is quoted against USD LIBOR flat (e.g. USD LIBOR vs YEN LIBOR 17 bps) and is driven by demand and supply of - ABC company has 3 year funding in JPY and is required to hedge exchange rate exposure created by this foreign currency debt.  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/f35dc8c9080181c2c3c1bea98c809b9375d4cce66f19c6c37b9ca65aa2e09b24.jpg)  
Fixed/Fixed Cross Currency Swap  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/e8d51269b4bda87fdcdb052e60d7f54b665079141ed29efebbbf978b599b9472.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/dca05016d8b5e83b47b7a627856e9b83eab47708d543924ab873f09a4a3de064.jpg)  
- Compared to a full cross currency swap, a Principal-Only Swap (POS) costs less because a POS does not provide a hedge against exchange rate risks on coupon payments.   
Consider a 3-year USD/JPY sw wit - At maturity, company receives JPY principal and pays USD principal at current spot rate (in fact can be any agreed exchange rate).   
- Same as a long-dated forward contract of the company buying JPY and selling USD at current spot rate.   
Due to the interest rate differential between JPY and USD, forward USD/JPY exchange rate is lower than spot rate (i.e. JPY at premium).   
The contract to buy JPY/sell USD forward at current spot rate has a positive value to the Company.   
- As a compensation to Citibank (i.e. to make NPV = 0), the Company will need to pay a periodic coupon (either in USD or JPY) to Citibank.  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/d1405d291d249b6e5134b2badef797ed0f956933f56fb317e1b4f4fae2b0a714.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/5d30cb096867177a776b8b2b83ce035cf7be1eeab66d94f66442c184ffaa73b6.jpg)  
- Consider a 3-year USD/JPY swap with only coupon exchanges.  
There are no principal exchanges. If the USD fixed rate is known, we can solve  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/4c870be77e84c1d920946860a73a6bfe4326d20abfd3c994a501df6e2b3ee0e5.jpg)  
- A Long-Dated Foreign Exchange (LTFX) contract is a Zero Coupon Currency & Interest Rate Swap - Instead of exchanging coupons, at the time of dealing, the Principal amount on one set of cashflows is set so that the NPV = 0.  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/3a3bf1801696da00a49e28434ab75f65e31e6370c6e8ad0e2b4f042cc422e146.jpg)  
Aside: Using Interest Rate Parity - Pricing Forward Foreign Exchange  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/7d1c546377efcd526ea660f6b9844b8acf31576afeb27ef1054c4dc57b11f700.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/72bec48fa2ab3da51ac1bf17c68bdcb38539c8b6d40056da27e3d5473d4cbc46.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/a8459166d58fcf01fccc212addf037162fdf9c29d8a65bcba12b20ddea8a564c.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/ff9dcc5f5faaf10edcc3f66a65f9b0a44353548119281890c513c7507f48a20c.jpg)  
Rather than using zero coupon rates, each currencies’ discount factors may be use \* Short Cut: Forward Rate = Spot X dfUSD/dfJPY 105 X 0.9420 / 0.9975  
 ![500](https://cdn-mineru.openxlab.org.cn/extract/3d1b2355-dc75-4129-9dcd-d49d557b4a1c/37505301aa69af139a1a3b4e06727873b4e99db05ef83f99c0e18abeb1146899.jpg)  