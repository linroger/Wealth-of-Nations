---
tags:
  - compounding
  - continuous_compounding
  - fixed_cash_flows
  - interest_rate_quotations
  - money_market
aliases:
  - Interest Rate Quotes
  - Rate Quotations
key_concepts:
  - Compounding frequency
  - Continuous compounding
  - Fixed cash flows
  - Interest rates
  - Simple interest
---

# 2.1 INTEREST RATE QUOTATIONS  

An investment with fixed cash flows is completely described by its price and cash flows. It seems enough to know, for example, that a bond paying 102 in six months costs 101.4925 today, or that a $\$100,000,000$ year loan made six months from today will return $\$103,030,100$ in two years. Nevertheless, investors and traders often prefer to quote and think about valuations in terms of interest rates. As shown herein, the bond and loan just described earn semiannually compounded rates of $1\%$ and $2\%$ per year,  

respectively. Rates are more intuitive than prices and cash flows because.   
rates automatically normalize for the amount invested and for the investment horizon. The bond costs 101.4925 and matures in six months, while.   
the loan invests $\$100,000,000$ in six months for 1.5 years, but their respec-.   
tive interest rates can be sensibly and intuitively compared..  

Interest rates are always quoted as annual rates over a term or tenor,. which is described as a number of periods of fixed length. A money market instrument, for example, might offer $1\%$ per year for 90 days on an investment of $\$100,000$ . If this $1\%$ is quoted as a simple rate of interest, under the actual/360 convention described in Section 1.7, then the interest payment at the end of the 90 days is,  

$$
\$100,000
$$  

If the $1\%$ interest rate on the money market instrument is quoted not as a simple rate, but as a daily compounded rate, then interest is computed differently: the investment earns simple interest daily, but interest is earned on accumulated balances, which include interest already earned. After the first day, then, the balance includes one day of simple interest,  

$$
\$100,000
$$  

Over the second day, the entire balance at the end of the first day, given. in Equation (2.2), earns another day of simple interest. This implies that interest is compounded, that is, the. $\$2.78$ of interest earned over the first. day itself earns interest on the second day. As a result, the total balance at the end of the second day is,.  

$$
5100,002.78\left(1+{\frac{1\%}{360}}\right)=5100,000\left(1+{\frac{1\%}{360}}\right)^{2}=5100,005.56
$$  

where the first equality comes from substituting the left-hand side of (2.2) for the $\$100,002.78$ in (2.3).  

Continuing in this fashion, the total balance at the end of the 90 days, which is the amount paid by the money market instrument at maturity, is,  

$$
\mathbb{S}100,000\bigg(1+\frac{1\%}{360}\bigg)^{90}=\mathbb{S}100,250.31
$$  

Comparing the interest component of Equation (2.4), that is, $\$250.31$ , with that of (2.1), that is,. $\$250.00$ , shows the effect of compound interest in this example. A daily compounded rate of. $1\%$ on $\$100,000$ earns 31 cents more  

than a simple interest rate of. $1\%$ . When rates are higher, and when the term.   
of the investment is longer, the difference can be much larger.  

Return now to the bond and loan examples given at the start of this section. In these cases, interest is likely to be semiannually compounded, where, by convention, a semiannual period is exactly one half of a year. Therefore, the six-month bond, which costs 101.4925 today and pays 102 after six months, earns $1\%$ in the sense that,  

$$
\$101.49256
$$  

The loan invests. $\$100$ million six months from today and, three semi-. annual periods (i.e., 1.5 years) later, returns $\$103,030,000$ This investment. earns a semiannually compounded rate of. $2\%$ in the sense that,.  

$$
\S100,000,000\bigg(1+\frac{2\%}{2}\bigg)^{3}=\S103,030,100
$$  

This section illustrates concepts with daily and semiannual periods.. Daily periods are common in money markets and in the swap market discussed in the next section. Semiannual periods are common in many government and corporate bond markets, like the US government bond market, discussed in Chapter 1. Different periods are used in other contexts,. however. Mortgage markets use monthly periods, for example, because mortgage payments are typically paid monthly..  

More generally, then, let. $_n$ be the number of periods per year; let $N$ be the number of periods; and let. $\hat{r}$ be the interest rate to be compounded $_n$ times per year. Then, investing. $F$ at the rate $\hat{r}$ grows, after $N$ periods, to a total balance of,  

$$
F{\Bigg(}1+{\frac{\hat{r}}{n}}{\Bigg)}^{N}
$$  

Markets should ensure that the final proceeds from identical investments of the same term are the same, regardless of the compounding convention. If, for example, the market offers 102 on a 1-year investment of 100, that investment might be quoted as earning $2\%$ annually; $1.9901\%$ semiannually compounded; or $1.9819\%$ compounded monthly, because,  

$$
100(1+2\%)=100\left(1+{\frac{1.9901\%}{2}}\right)^{2}=100\left(1+{\frac{1.9819\%}{12}}\right)^{12}=102\left(1+{\frac{1.9819\%}{12}}\right)^{12}=102\times10^{-12}.
$$  

Note that the greater the frequency of compounding, the lower the quoted. interest rate. These rates are set such that more frequent compounding, that is, paying more interest on interest, exactly offsets the lower rate earned on the initial investment.  

This section concludes by noting that some contexts use continuous compounding, in which interest is conceptualized as being paid every instant. This quoting convention can appear in money markets; is frequently used at financial firms, because rates and discount factors have to be calculated at irregular intervals; and is used almost exclusively by researchers for mathematical convenience. Continuous compounding is presented in Appendix A2.1.  
