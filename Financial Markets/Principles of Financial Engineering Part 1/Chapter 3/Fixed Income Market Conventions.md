# 3.5 FIXED INCOME MARKET CONVENTIONS  

In the previous chapter, we saw that bond markets quote prices rather than yields. To avoid confusion in financial engineering, it is crucial to be aware of the conventions underlying fixed income trades and the instruments. In this section, we briefly review some of these market conventions.  

# 3.5.1 HOW TO QUOTE YIELDS  

Markets use three different ways to quote yields. These are, respectively, the money market yield, the bond equivalent yield, and the discount rate.1o we will discuss these using default-free pure discount. bonds with maturity $T$ as an example. Let the time $t$ price of this bond be denoted by $B(t,T)$ . The bond is default free and pays 100 at time $T.$ Now, suppose $R$ represents the time- $t$ yield of this bond.  

It is clear that $B(t,T)$ will be equal to the present value of 100, discounted using. $R$ but how should this present value be expressed? For example, assuming that. $(T-t)$ is measured in days and. that this period is less than 1 year, we can use the following definition:  

$$
B(t,T)=\frac{100}{\left(1+R\right)^{((T-t)/365)}}
$$  

vhere $((T-t)/365)$ is the remaining life of the bond as a fraction of year, which here is "defined" Is 365 days.  

But we can also think of discounting using the alternative formula:  

$$
B(t,T)=\frac{100}{(1+R((T-t)/365)}
$$  

Again, suppose we use neither formula but instead set  

$$
B(t,T)=100-R\bigg(\frac{T-t}{365}\bigg)100
$$  

Some readers may think that given these formulas, Eq. (3.2) is the right one to use. But this is not correct! In fact, they may all be correct, given the proper convention..  

The best way to see this is to consider a simple example. Suppose a market quotes prices $B(t,T)$ instead of the yields $R$ 11 Also suppose the observed market price is  

$$
B(t,T)=95.00
$$  

with $(T-\mathfrak{t})=180$ days and the year defined as 365 days. We can then ask the following question: Which one of the formulas in Eqs. (3.2)-(3.4) will be more correct to use? It turns out that these formulas can all yield the same price, 95.00, $i f$ we allow for the use of different Rs.  

In fact, with. $R_{1}=10.9613\%$ the first formula is "correct," since  

$$
B(t,T)\begin{array}{c}{{100}}\ {{(1+.109613)^{(180/365)}}}\ {{=95.00}}\end{array}
$$  

On the other hand, with. $R_{2}=10.6725\%$ the second formula is "correct," since  

$$
B(t,T)\begin{array}{c}{{100}}\ {{(1+.106725(180/365))}}\ {{=95.00}}\end{array}
$$  

Finally, if we let $R_{3}=10.1389\%$ , the third formula will be "correct":  

$$
\begin{array}{c}{B(t,T)=100-.101389\left(\frac{180}{365}\right)100}\ {=95.00}\end{array}
$$  

Thus, for (slightly) different values of $R_{i},$ all formulas give the same price. But which one of hese is the "right"' formula to use?  

That is exactly where the notion of convention comes in. A market can adopt a convention to quote yields in terms of formula (3.2), (3.3), or (3.4). Suppose formula (3.2) is adopted. Then, once traders see a quoted yield in this market, they would "know"' that the yield is defined in terms of formula (3.2) and not by (3.3) or (3.4). This convention, which is only an implicit understanding during the execution of trades, will be expressed precisely in the actual contract and will be known by all traders. A newcomer to a market can make serious errors if he or she does not pay enough attention to such market conventions.  

# EXAMPLE  

In the United States, bond markets quote the yields in terms of formula (3.2). Such values of $R$ are called bond equivalent yields.  

Money markets that deal with interbank deposits and loans use the money market yield convention and utilize formula (3.3) in pricing and risk management.  

Finally, the Commercial Paper and Treasury Bills yields are quoted in terms of formula (3.4). Such yields are called discount rates.  

Finally, the continuous discounting and the continuously compounded yield $r$ is defined by the formula  

$$
B(t,T)=100e^{-r(T-t)}
$$  

where the $e^{x}$ is the exponential function. It turns out that markets do not like to quote continuously. compounded yields. One exception is toward retail customers. Some retail bank accounts quote the continuously compounded savings rate. On the other hand, the continuously compounded rate is often used in some theoretical models and was, until lately, the preferred concept for academics..  

One final convention needs to be added at this point. Markets have an interest payments convention as well. For example, the offer side interest rate on major Euroloans, the LIBOR, is paid at the conclusion of the term of the loan as a single payment. We say that LIBOR is paid in-arrears. On the other hand, many bonds make periodic coupon payments that occur on dates earlier than the maturity of the relevant instrument. Most OISs have one payment if shorter than 1 year and a 12-month period for longer swaps.12  

# 3.5.2 DAY-COUNT CONVENTIONS  

The previous discussion suggests that ignoring quotation conventions can lead to costly numerical errors in pricing and risk management. A similar comment can be made about day-count conventions. A financial engineer will always check the relevant day-count rules in the products that he or she is working on. The reason is simple. The definition of a "year' or of a "month' may change from one market to another and the quotes that one observes will depend on this convention. The major day-count conventions are as follows:  

1. The 30/360 basis. Every month has 30 days regardless of the actual number of days in that particular month, and a year always has 360 days. For example, an instrument following this convention and purchased on May 1 and sold on July 13 would earn interest on  

$$
30+30+12=72
$$  

days, while the actual calendar would give 73 days.  

More interestingly, this instrument purchased on February 28, 2003, and sold the next day, on March 1, 2003, would earn interest for 3 days. Yet, a money market instrument such as an interbank deposit would have earned interest on only 1 day (using the actual/360 basis mentioned below).  

2. The 30E/360 basis. This is similar to 30/360 except for a small difference at the end of the month, and it is used mainly in the Eurobond markets. The difference between 30/360 and 30E/360 is illustrated by the following table, which shows the number of days interest is earned starting from March 1 according to the two conventions:  

<html><body><table><tr><td>Convention</td><td>March 1-March 30</td><td>March 1-March 31</td><td>March 1-April 1</td></tr><tr><td>30E/360</td><td>29days</td><td>29days</td><td>30days</td></tr><tr><td>30/360</td><td>29 days</td><td>30days</td><td>30days</td></tr></table></body></html>  

According to this, a Eurobond purchased on March 1 and sold on March 31 gives an extra day of interest in the case of 30/360, whereas in the case of 30E/360, one needs to hold it until the beginning of the next month to get that extra interest.  

3. The actual/360 basis. If an instrument is purchased on May 1 and sold on July 13, then it is held 73 days under this convention. This convention is used by most money markets. Actual/ 360 is also sometimes written as ACT/360, where ACT is an abbreviation for actual..   
4. The actual/365 basis. This is the case for Eurosterling money markets, for example.   
5. Actual/actual. Many bond markets use this convention.  

An example will show why these day-count conventions are relevant for pricing and risk management. Suppose you are involved in an interest rate swap. You pay LIBOR and receive fixed. The market quotes the LIBOR at 5.01, and quotes the swap rate at 6.23/6.27. Since you are receiving fixed, the relevant cash flows will come from paying 5.01 and receiving 6.23 at regular intervals. But these numbers are somewhat misleading. It turns out that LIBOR is quoted on an ACT/360 basis. That is to say, the number 5.01 assumes that there are 360 days in a year.  

However, the swap rates may be quoted on an ACT/365 basis, and all calculations may be based on a 365-day year.13 Also the swap rate may be annual or semiannual. Thus, the two interest rates where one pays 5.01 and receives 6.23 are not directly comparable.  

# EXAMPLE  

Swap markets are the largest among all financial markets, and the swap curve has become the central pricing and risk management tool in finance. Hence, it is worth discussing swap market conventions briefly.  

USD swaps are liquid against $3\mathrm{m}$ -LIBOR and 6m-LIBOR. The day-count basis is annual, ACT/360.   
Japanese yen (JPY) swaps are liquid against 6m-LIBOR. The day-count basis is semiannual, ACT/365.   
British pound (GBP) swaps are semiannual, ACT/365 versus 6m-LIBOR.   
Finally, Euro (EUR) swaps are liquid against 6m-LIBOR and against 6m-Euribor. The day-count basis is annual 30/360.  

Table 3.1 summarizes the day-count and yield/discount conventions for some important markets around the world. A few comments are in order. First note that the table is a summary of three types of conventions. The first is the day-count, and this is often ACT/360. However, when the. 30/360 convention is used, the 30E/360 version is more common. Second, the table tells us about the yield quotation convention. Third, we also have a list of coupon payment conventions concern-. ing long-term bonds. Often, these involve semiannual coupon payments.14  

Finally, note that the table also provides a list of the major instruments used in financial mar. kets. The exact definitions of these will be given gradually in the following chapters.  

# 3.5.2.1 Holiday conventions  

Financial trading occurs across borders. But holidays adopted by various countries are always somewhat different. There are special independence days, special religious holidays. Often during Christmas time, different countries adopt different holiday schedules. In writing financial contracts, this simple point should also be taken into account, since we may not receive the cash we were counting on if our counterparty's markets were closed due to a special holiday in that country.  

Hence, all financial contracts stipulate the particular holiday schedule to be used (London, New York, and so on), and then specify the date of the cash settlement if it falls on a holiday.. This could be the next business day or the previous business day, or other arrangements could. be made.  

<html><body><table><tr><td colspan="3">Table 3.1 Day-Count and Yield/Discount Conventions</td></tr><tr><td></td><td>Day-Count</td><td>Yield Cash</td></tr><tr><td colspan="3">United States</td></tr><tr><td>Depo/CD</td><td>ACT/360</td><td>Yield</td></tr><tr><td>T-Bill/CP/BA</td><td>ACT/360</td><td>Discount</td></tr><tr><td>Treasuries</td><td>ACT/ACT, semiannual</td><td>B-E yield</td></tr><tr><td>Repo</td><td>ACT/360</td><td>Yield</td></tr><tr><td colspan="3">Euromarket</td></tr><tr><td>Depo/CD/ECP</td><td>ACT/360 (ACT/365 for sterling)</td><td>Yield</td></tr><tr><td>Eurobond</td><td>30E/360</td><td>Yield</td></tr><tr><td colspan="3">United Kingdom</td></tr><tr><td>Depo/CD/Sterling CP</td><td>ACT/365</td><td>Yield</td></tr><tr><td>BA/T-bill</td><td>ACT/365</td><td>Discount</td></tr><tr><td>Gilt</td><td>ACT/365 (semiannual)</td><td>B-E yield</td></tr><tr><td>Repo</td><td>ACT/365</td><td>Yield</td></tr><tr><td colspan="3">Germany</td></tr><tr><td>Depo/CD/Sterling CP</td><td>ACT/360</td><td>Yield</td></tr><tr><td>Bund</td><td>30E/360 (annual)</td><td>B-E yield</td></tr><tr><td>Repo</td><td>ACT/360</td><td>Yield</td></tr><tr><td colspan="3">Japan</td></tr><tr><td>Depo/CD</td><td>ACT/365</td><td>Yield</td></tr><tr><td>Repo domestic</td><td>ACT/365</td><td>Yield</td></tr><tr><td>Repo international</td><td>ACT/360</td><td>Yield</td></tr></table></body></html>  

# 3.5.3 TWO EXAMPLES  

We consider how day-count conventions are used in two important cases. The first example summarizes the confirmation of short-term money market instruments, namely a Eurodollar deposit. The second example discusses the confirmation summary of a Eurobond. Eurocurrency markets and Eurobonds were introduced in Chapter 2.  

# EXAMPLE: A EURODOLLAR DEPOSIT  

<html><body><table><tr><td>Amount</td><td>$100,000</td></tr><tr><td>Tradedate</td><td>Tuesday,June5,2002</td></tr><tr><td>Settlementdate</td><td>Thursday,June 7,2002</td></tr><tr><td>Maturity</td><td>Friday, July 5, 2002</td></tr><tr><td>Days</td><td>30</td></tr><tr><td>Offer rate</td><td>4.789%</td></tr><tr><td>Interestearned</td><td>(100,000)× 0.04789 × 30/360</td></tr></table></body></html>  

Note three important points. First, the depositor earns interest on the settlement date, but does. not earn interest for the day the contract matures. This gives 30 days until maturity. Second, we are looking at the deal from the bank's side, where the bank sells a deposit, since the interest rate is the offer rate. Third, note that interest is calculated using the formula.  

$$
(1+r\delta)100,000-100,000
$$  

and not according to  

$$
(1+r)^{\delta}100,000-100,000
$$  

where  

$$
\delta=30/360
$$  

is the day-count adjustment.  

The second example involves a Eurobond trade.  

EXAMPLE: A EUROBOND   


<html><body><table><tr><td>Trade date</td><td>EuropeanInvestmentBank,5.0%(Annual Coupon) Tuesday,June 5, 2002</td></tr><tr><td>Settlementdate</td><td>Monday,June11,2002</td></tr><tr><td>Maturity</td><td>December28,2006</td></tr><tr><td>Previous coupon</td><td>April 25,2001</td></tr><tr><td>Next coupon</td><td>April 25,2002</td></tr><tr><td>Days in coupon period</td><td>360</td></tr><tr><td>Accruedcoupon</td><td>Calculate using money market yield</td></tr></table></body></html>  

We have two comments concerning this example. The instrument is a Eurobond, and Eurobonds make coupon payments annually, rather than semiannually (as is the case of Treasuries, for example). Second, the Eurobond year is 360 days. Finally, accrued interest is calculated the same way as in money markets.  

We can now define the major instruments that will be used. The first of these are the forward loans. These are not liquid, but they make a good starting point. We then move to FRAs and to Eurocurrency futures.  
