---
tags:
  - fed_funds_rate
  - fra_pricing
  - interest_rates
  - libor
  - ois_rates
  - repo_rates
aliases:
  - BBA
  - annualized yields
  - forward rate agreement
key_concepts:
  - compound interest
  - forward rates
  - present value
  - simple interest
  - terminal value
---
# FIXED INCOME: CASH MARKETS  

# Interest Rates  

# Aims  

• To examine diferent conventions when returns or interest rates (yields) are ‘annualised’ – namely ‘simple interest’, ‘compound interest’ and ‘continuously compounded interest’.   
• To calculate present value and terminal value using diferent interest rate conventions.   
• Show how to switch between simple interest rates, compound rates and continuously compounded rates.   
• To calculate forward rates from spot rates, using diferent interest rate conventions.   
• To show how a Forward Rate Agreement (FRA) is priced.  

This chapter provides an overview of the key interest rates used in the market and diferent day-count and interest rate conventions used when calculating ‘annual yields’. We also discuss how forward rates are derived from spot interest rates and how FRAs are priced.  

8.1 LIBOR, REPOS, FED FUNDS, AND OIS RATES  

# 8.1.1 LIBOR  

LIBOR (London Interbank Ofer Rate) is the interest rate at which an AA-rated bank agrees to lend out funds to another AA-rated bank. LIBOR is an unsecured loan and borrowing is for maturities of one day to one year. The rate quoted will often be an average of LIBOR rates taken from a survey of ‘reference banks’, usually at 11 a.m. London time, under the auspices of the British Bankers Association (BBA). This is known as the ‘LIBOR-fxing’ and provides a reference rate for use in valuing many derivatives transactions (e.g. interest rate swaps).  

In recent years there has been an investigation into manipulation of LIBOR rates submitted by the reference banks, which has resulted in lengthy jail terms of up to 14 years for some of those involved. As a result there is a proposal that LIBOR fxing rates will not be determined by a ‘survey’ of hypothetical (or guesses) of the rate at which you will lend money for various currencies and maturity dates but instead will be based on actual transactions at maturities where there is an active liquid market.  

LIBOR rates are applicable to any ‘ofshore’ currency that banks borrow or lend in London. So, for example, there are US dollar, yen, etc. LIBOR rates quoted in London. The equivalent rates elsewhere are Euribor (countries that use the Euro), NYBOR (New York), PIBOR (Paris), FIBOR (Frankfurt), ADIBOR (Abu Dhabi), SIBOR (Saudi or Singapore) and HKIBOR (Hong Kong).  

The Fed Funds rate is the rate at which US banks (who hold reserves at the US central bank, the Federal Reserve) lend to each other, overnight. In the UK, overnight leading rates between banks is called the sterling overnight index average (SONIA) and for the Eurozone it is the euro overnight index average (EONIA).  

# 8.1.2 Repurchase Agreement (Repo)  

A repo or more accurately a ‘sale and repurchase agreement’ is a form of collateralised borrowing. Suppose a market maker wishes to borrow $\$100$ overnight. He can agree to ‘sell’ securities (e.g. T-bills or T-bonds) which he holds, to a counterparty (e.g. broker) for their current market price of $\$100$ , in exchange for $\$100$ cash. He also simultaneously agrees to ‘buy back’ the securities the next day at a price higher than $\$100$ , say $(\$100$ . This is equivalent to an overnight interest rate of $0.018\%$ or $6.48\%$ p.a. (using an actual/360 day count convention).  

If the securities in the repo are less liquid than government bonds (or have substantial credit risk) the amount of cash loaned will be less than the market value of the securities – this is the haircut demanded by the lender of the funds. If the haircut is $1\%$ then the lender will only supply $\$9.90$ cash when the $\$100$ of bonds are handed over and the overnight interest rate charged on the $\$9.90$ will be at $6.48\%$ p.a., that is an interest payment of $\$1,782$ $\stackrel{\prime}{=}0.0648\times$ $\$90.9m/360)$ . Hence the lender of the funds holds securities which are worth more than the $\$9.90$ . If the borrower defaults, the lender can subsequently sell the securities at their market price one day later and is virtually assured that he will receive from the sales at least $\$9.90$ plus the $\$1,782$ interest.  

Note that in principle any security can be used in a repo, such as a bill, bond or even equities but the greater the risk of the collateral losing value over the term of the repo loan, the larger will be the haircut. If the borrower of funds is a highly rated creditworthy institution and provides highly liquid government securities as collateral then the haircut may be between zero and $0.25\%$ (i.e. $^1/_{4}$ of $1\%$ ). When viewed from the perspective of the borrower the transaction is a repo. From the point of view of the counterparty, the supplier of funds, it is a reverse repo. The most common type of repo is an overnight repo, which can be rolled over each day. Longer maturity repos are known as term repos. A repo is a secured loan (i.e. collateral is provided) and hence the repo rate is generally slightly below the Fed Funds rate.  

# 8.1.3 Risk-free Rate  

Traditionally LIBOR was taken as a measure of the ‘risk-free’ rate when pricing derivatives but after the 2007–8 crash this is not always the case. A weighted average of the rates in brokered transactions (with the weights proportional to amounts loaned) in the Fed Funds overnight (unsecured lending) market, is known as the efective federal funds rate. If a bank borrows overnight in the Fed Funds market for 3 months (say) by rolling over its borrowing each day, then the interest rate it pays over the 3 months is the geometric average of the overnight rates. An overnight index swap (OIS) is an arrangement where a fxed rate for 3 months (say) can be swapped for the geometric average of the overnight rates (over the 3 months). This swap is a way of fxing the borrowing cost equal to the OIS rate. Hence the OIS rate is also very close to being a risk-free rate. There is a term structure of OIS rates, so a zero-curve can be used to determine a set of ‘risk-free’ rates that can be used in derivatives pricing. This causes some technical issues when LIBOR rates determine payofs at maturity of a derivative (e.g. FRA, swaps, caps) but we use OIS as risk-free discount rates. We avoid these problems by assuming LIBOR is an acceptable risk-free rate.  

# 8.2 DAY-COUNT CONVENTIONS  

Interest rates (yields) are usually presented as ‘annual percentage rates’ but it is important to know whether these fgures are based on ‘simple interest’ $r_{s}$ , ‘compound interest’ $r$ , or ‘continuously compounded’ rates, $r_{c}$ . For example, an interest rate of $2\%$ payable over 3 months may be quoted as a simple interest rate of $r_{s}=8\%$ However, if an investor rolled over four, 3-month investments (and the interest rate remained constant), she could actually earn an annual ‘compound rate’ of $(1.02)^{4}=1.0824$ or $r=8.24\%$ p.a. The annual compound rate exceeds the simple rate because the compound rate assumes the investor earns ‘interest-on-interest’. We use the following notation:  

$a=$ number of days in the year the convention used to calculate an ‘annual rate’ m actual number of days to maturity of the ‘asset’ $T=m/a=$ number of years or fraction of year the investment is held maturity  

Initially, for ease of calculation we assume $a=360$ (even though there are actually 365 days in a year) and if the investment is for 3 months we assume the actual number of days to maturity is $m=90$ , hence $T=90/360=0.25$ years.1 For an investment which lasts for 2 years we take $m=720$ , hence $T=720/360=2$ years.  

# 8.2.1 Simple Interest  

Suppose you place $P_{0}=\$100$ in a deposit account at $t=0$ which pays out $M=\$102$ after 90 days. Similarly, you could purchase an asset (e.g. T-bill or zero-coupon bond or stock) for $P_{0}=\$100$ at $t=0$ and sell it 3 months later for $M=\$102$ . You have made $2\%$ over 3 months which is sometimes referred to as the ‘periodic’ or ‘per period’ interest rate (yield). Because the interest rate refers to a transaction which begins today and has a single cash fow at one point in the future (with no interim payments), the interest rate is also known as the 3-month spot interest rate (or spot yield).  

Over the 90 days you have actually made $\$2$ or $2\%$ on your outlay of $\$100$ . Everything which follows is ‘fctitious’ since your investment ends after 90 days. But it is useful to have some rules for ‘annualising’ the ‘periodic rate’ of $2\%$ , earned over 90 days which we do by using either simple interest, compound interest or continuously compounded interest. As long as everyone knows which ‘annualising convention’ has been used there will be no confusion and everyone will agree on the fnal amount received.  

If you make $2\%$ over 3 months then the simple annual return is defned as $r_{s}=8\%$ The simple interest rate of $8\%$ p.a. assumes that you do not earn any ‘interest-on-interest’ on the deal. Conceptually, it is as if you took the $\$2$ interest at the end of the frst 3 months and spent it but you continued to reinvest $\$100$ (not $\$102$ ) over the next 3 months – repeating this procedure at the end of 6 months and 9 months. Hence you have received four interest payments of $\$2$ every 90 days on an investment of $\$100$ (at the beginning of each 90-day period).2 The ‘simple’ annual interest rate (yield) is defned as:  

$$
r_{s}=\left(\frac{M}{P_{0}}-1\right)\frac{1}{T}=\left(\frac{102}{100}-1\right)\frac{360}{90}=0.08
$$  

Hence the market price of the bond is given by:  

$$
P_{0}=\frac{M}{(1+r_{s}T)}
$$  

This equation says that the value today (i.e. the present value) of an amount $M=\$102$ which accrues in $n=90/360$ years, when a simple interest rate of $r_{s}=8\%$ p.a. is used, is $P_{0}=\$100$ . Rearranging (8.2) tells us that if you invest $P_{0}=\$100$ at simple annual rate of $r_{s}=8\%$ p.a. then the terminal value after $T=90/360$ years is:  

$$
M=P_{0}\left(1+r_{s}T\right)
$$  

# 8.2.2 Compound Interest  

Suppose you again place $P_{0}=\$100$ in a deposit account at $t=0$ which pays out $M=\$102$ after 90 days. Or you purchase an asset for $P_{0}=\$100$ at $t=0$ and sell it 3 months $T=1/4$ of a year) later for $M=\$102$ . Your return over 3 months is $2\%$ which implies a compound annual return (yield) of $r=(1.02)^{4}-1=0.0824$ or $8.24\%$ p.a. This calculation assumes that the initial $\$100$ investment is ‘rolled over’ and any interest earned is also reinvested in each successive 3-month period (at the same rate of return as in the frst 3 months). Expressed algebraically:  

$$
r=\left[{\frac{M}{P_{0}}}\right]^{\frac{1}{T}}-1=\left[{\frac{102}{100}}\right]^{4}-1=0.08243
$$  

Again a simple algebraic rearrangement gives:  

$$
P_{0}=\frac{M}{(1+r)^{T}}
$$  

It also follows from (8.5) that if you invest $P_{0}$ at a compound annual rate $r=0.0824$ for a period of $T$ years (or fraction of a year), it will eventually accrue to:  

$$
M=P_{0}(1+r)^{T}
$$  

For example, $\$100$ invested at a compound rate of $8.243\%$ p.a. over 3 months accrues to:  

$$
M=100(1+0.08243)^{1/4}=102
$$  

Alternatively, suppose you invest $\$100$ , but this time you receive $M=\$108$ after $T=2$ years (i.e. $a=360$ days and $m=720$ days). The annual compound return is:  

$$
r=\left[{\frac{108}{100}}\right]^{\frac{1}{2}}-1=\left[{\frac{M}{P_{0}}}\right]^{\frac{1}{T}}-1=0.0392
$$  

This return is slightly less than $4\%$ p.a. because the compound return assumes that the ‘interest’ earned at the end of year-1, is reinvested in the second year. Note that the above formulas work regardless of whether $T$ is in years or fractions of a year.  

# 8.2.3 Continuously Compounded Rate  

For $P_{0}=\$100$ , $M=\$102$ and an investment over 90 days, the continuously compounded annual rate (yield) is defned as:  

$$
r_{c}=(360/90)\ln(102/100)=(1/T)\ln(M/P_{0})=0.07921(7.921\%)
$$  

Once we have defned $r_{c}$ in this way then it must be the case that:  

$$
P=M e^{-r_{c}T}a n d M=P e^{r_{c}T}
$$  

where $T=m/a$ is the number of years (or fraction of a year) to maturity. The continuously compounded rate assumes you earn interest-on-interest over ‘very short periods of time’. In practice, it is almost equivalent to assuming you earn interest daily and you reinvest this daily interest payment, each day. The continuously compounded rate is defned so if you did invest $P=\$100$ today at $r_{c}=0.079218$ $(7.9218\%)$ , and you earned interest ‘every second’ then you would end up with $M=100e^{0.0792(90/360)}=\S102$ after 90 days. So the continuously compounded rate is like an ordinary compound rate, but where the compounding takes place ‘every second’.  

The continuously compounded rate $(7.9218\%$ p.a.) is less than the compound rate ( $8.2432\%$ p.a.). The reason for this is a little involved. If you start of with $P_{0}=100$ then whatever interest rate convention you use, you must always end up with $M=\$102$ after 90 days. But the continuously compounded rate of $7.9218\%$ p.a. can be rationalised by assuming that interest-on-interest accrues ‘every second’. To end up with $M=\$102$ at the end of 90 days, therefore requires a lower continuously compounded annual rate $(=7.9218\%$ if interest accrues every second, than if interest is ‘rolled over’ only every 90 days – as is the case when using the compound rate of $8.243\%$ p.a.  

# 8.2.4 Daily Compounding  

We now show that a continuously compounded rate is nearly equivalent to using daily compounding. Suppose the simple annual rate is $r_{s}=0.10$ ( $10\%$ . The terminal value after 1 year, of an investment of $P_{0}$ today, when compounding is $q$ times per year is:  

$$
T V_{n}=P_{0}(1+r_{s}/q)^{q}
$$  

TABLE 8.1 Compounding frequency and terminal value   


<html><body><table><tr><td>Compounding frequency</td><td>Terminal value of $100 at end of year (rs=10% p.a.)</td></tr><tr><td>Annually (q = 1)</td><td>$110</td></tr><tr><td>Quarterly (q = 4)</td><td>$110.38</td></tr><tr><td>Weekly (q = 52)</td><td>$110.51</td></tr><tr><td>Daily (q = 365)</td><td>$110.5155</td></tr><tr><td>Continuously compounded</td><td>TV = $100e(0.1) = $110.5171</td></tr></table></body></html>  

Suppose the frequency of compounding increases so that $q$ increases from 1, 2, 3, . . . to say $q=365$ times per year. The terminal value in 1 year, of $P_{0}=\$100$ invested today is given in Table 8.1, for diferent values of $q$ . If $r_{s}=0.10$ $10\%$ p.a.) and interest is compounded each quarter $(q=4)$ then the $\$100$ accrues to $T V=\$110.38$ at the end of the year. But if interest is compounded daily $\dot{\boldsymbol{q}}=365\boldsymbol{\mathrm{)}}$ then $T V=\$110.5155$ . What is the terminal value if we assume the continuously compounded rate is $r_{c}=0.10?$ The terminal value after 1 year is $M=100e^{0.10(1)}={\tt S}110.5171$ , which is very close to the result for daily compounding.  

# 8.2.5 Switching Between Interest Rates  

For an investment of $P_{0}=\$100$ , our conventions when defning simple, compound and continuously compounded rates must all give the same terminal value $M=\$102$ after $T=1/4$ year, hence:  

$$
M=P_{0}\left(1+r_{s}T\right)=P_{0}(1+r)^{T}=P_{0}e^{r_{c}T}
$$  

It immediately follows that:  

$$
r_{c}=\ln(1+r)\quad\mathrm{and}\quad(1+r)=(1+r_{s}T)^{1/T}
$$  

These equations allow us to fnd values of $r_{c},r$ and $r_{s}$ that are equivalent to each other. By this we mean that if we use either $r_{c}$ or $r$ or $r_{s}$ in the appropriate formula they will all give the same value for $M$ (e.g. after investing $P_{0}=\$100$ for $\mathrm{T}={}^{1}/_{4}$ of a year).  

For example, if you are given the compound annual rate, $r=0.082432$ p.a. then the equivalent continuously compounded rate is $r_{c}=\ln(1+r)=0.07921$ p.a. (and vice versa). Similarly, if you are given the simple annual rate $r_{s}=0.08$ p.a. (for $T=90/360)$ then the equivalent compound rate is $(1+r)=(1+r_{s}T)^{1/T}=[1+(0.08/4)]^{4}=1.02^{4}=1.082432$ (and vice versa). If you substitute these values either for $r_{c}$ , $r$ or $r_{s}$ in (8.12) you obtain $M=\$102$ in all cases.  

# 8.2.6 Present Values  

The diferent interest rate conventions must give the same present value (when used in the appropriate formulas) and these are summarised below.  

In the analysis above we invested $P_{0}=\$100$ in an asset (e.g. a zero coupon bond) with a known interest rate (yield) and calculated $M=\$102$ after 3 months. The above ‘present value’ equations allow you to calculate the market price for a (zero coupon) bond given the appropriate (simple, compound or continuously compounded) yield and the time to maturity.  

# 8.3 FORWARD RATES  

Spot interest rates (yields) refer to borrowing (or lending) money starting today, with a single fnal payment at a known time in the future. Suppose instead you go to a bank today, but ofer to lend $\$100$ , starting in 1 year’s time, with repayment 1 year later – the agreed interest rate is known as a forward rate. For example, if today you ofered to lend $\$100$ starting in 1 year’s time and the bank quotes a forward rate $f_{12}=11\%$ then you would receive $\$111$ at the end of year-2. How does the bank know what forward rate to quote? The bank calculates forward rates from today’s observed spot rates of interest.  

Figure 8.1 may help here, in terms of a heuristic argument. The ‘correct’ forward rate is based on the fact that investing $\$1$ over 2 years at $r_{2}$ should give the same dollar amount at the end of year-2 as investing at $r_{1}=9\%$ in the frst year, followed by an investment earning $f_{12}$ between years one and two.  

![](e7e20ec59788dd82a9f36ad07684011e2faae2a87acefe1fe731393c41870b64.jpg)  
1- year investment at $\boldsymbol{r}_{1}$ plus a forward investment at $f_{12}$ gives the same dollar amount as a 2-year investment at $r_{2}$   
FIGURE 8.1 Forward rate, $f_{12}$  

In Figure 8.1 note that the 2-year investment earns $10\%$ in each of the two years. Also, in the frst year, the 2-year spot rate is $1\%(=10\%-9\%)$ higher than the 1-year spot rate $(r_{1}=9\%$ ). Hence between $t=1$ and $t=2$ the forward rate must equal $10\%$ plus the amount ‘lost’ in the frst year. Hence the forward rate is:  

$$
f_{12}=10\%+(10\%-9\%)=11\%=2r_{2}-r_{1}
$$  

# 8.3.1 Compound Rates  

The above calculation ignores interest-on-interest which makes the correct forward rate a little higher at $11.009\%$ (see below). More formally, let $f_{12}$ denote the (compounded) forward rate applicable between years 1 and 2. Consider the following alternative investment strategies:  

Strategy-1: $A=\$100$ invested over 2 years gives $\$4$ at $t=2$ .   
Strategy-2: $A=\$100$ invested at $r_{1}$ gives $\mathcal{S}A(1+r_{1})=\mathbb{\S}109$ at the end of year-1.  

At $t=0$ (today) obtain a forward quote to lend $\$109$ at the end of year-1 for a further year at a forward interest rate of $f_{12}$ . At $t=2$ you know that you will receive from strategy-2:  

$$
\S109\left(1+f_{12}\right)=\S A(1+r_{1})(1+f_{12})
$$  

Since the two investment strategies are risk-free, then arbitrage will ensure that both strategies will result in the same payout at $t=2$ , hence:  

$$
A(1+r_{2})^{2}=A(1+r_{1})(1+f_{12})
$$  

Rearranging (8.16) we can solve for the forward rate:  

$$
(1+f_{12})=\frac{(1+r_{2})^{2}}{(1+r_{1})}=\frac{(1.10)^{2}}{(1.09)}=1.11009
$$  

If we use the approximation $\ln(1+r)^{T}\approx r T$ (for $-1<r<1$ ) then (8.17) can be expressed as a linear relationship:  

$$
2r_{2}\approx r_{1}+f_{12}
$$  

For the moment assume the approximations in Equation (8.18) are accurate. We can repeat the above argument for a 3-period horizon to obtain:  

$$
(1+r_{3})^{3}=(1+r_{1})(1+f_{13})^{2}
$$  

$$
3r_{3}\approx r_{1}+2f_{13}
$$  

where $f_{13}$ is the (annual) forward rate between year-1 and year-3 and hence applies to an investment horizon of $3-1=2$ years. Note that we can also compare our 3-year investment at $r_{3}$ with a known 2-year investment at $r_{2}$ and the forward rate $f_{23}$ between years 2 and 3 is:  

$$
(1+r_{3})^{3}=(1+r_{2})^{2}(1+f_{23})
$$  

$$
3r_{3}\approx2r_{2}+f_{23}
$$  

Equations (8.20) and (8.22) can be used to calculate the (compound) forward rates $f_{13}$ and $f_{23}$ from the known spot rates.  

# 8.3.2 Continuously Compounded Rates  

If we use ‘continuously compounded’ spot rates $r_{2},r_{3}$ then the no-arbitrage equation (equivalent to Equation 8.16) is:  

$$
A e^{3r_{3}}=A e^{2r_{2}}e^{f_{23}}
$$  

and (taking logs and rearranging), the continuously compounded forward rate $f_{23}$ is3:  

$$
f_{23}=3r_{3}-2r_{2}
$$  

which is an exact relationship (and not an approximation).  

# 8.3.3 Simple Rates: Day-count Conventions  

Some interest rates such as LIBOR are quoted as ‘simple’ rates and the day-count convention for calculating the interest cash fow is ‘actual/ $360^{\circ}-{\bf s}0$ by convention $\mathrm{\dot{1}y e a r}^{\mathrm{3}}=360$ days. For ease of exposition, we assume that the ‘actual’ number of days in any 3-month period is 90.  

Consider investing $\$4$ for 6 months $\mathrm{\Delta}n=180/360$ years at the (simple) 6-month spot rate $r_{n}=0.03$ $3\%$ p.a.). The investment is worth $A(1+r_{n}(180/360))$ after 6 months. An alternative is to invest for 3 months $m=90/360$ years) at the 3-month spot rate $r_{m}=0.02\left(2\%\right)$ followed by a forward rate agreement at $f_{m,n}$ for a further 3 months $(n-m=90/360$ years). This alternative strategy is worth $A[1+r_{m}(90/360)][1+f_{m,n}(90/360)]$ after 6 months. Equating these two amounts and rearranging gives the ‘simple’ forward rate, which applies to an investment which begins in 3 months’ time and terminates after a further 3 months:  

$$
f_{_{m,n}}={\frac{360}{90}}\left[{\frac{[1+r_{n}(180/360)]}{[1+r_{m}(90/360)]}}-1\right]={\frac{1}{n-m}}\left[{\frac{(1+r_{n}n)}{(1+r_{m}m)}}-1\right]=0.0398\left(3.98\left(1-{\frac{1}{2}}\right)-1\right).
$$  

In a forward rate agreement (FRA), the convention is that interest rates are quoted as ‘simple’ rates on an ‘actual/360 basis’. Hence at $t=0$ , the quoted rate for a $3\times6$ FRA is $3.98\%$ p.a. This is known as ‘pricing the $3\times6$ FRA’. Alternatively, if $m=180/360$ and $n=270/360$ then the above equation using 6 and 9 month spot rates would ‘price’ a $6\times9$ FRA.  

Forward rates can be calculated for any horizon by using the appropriate formula, together with data on interest rates (yields) from the (spot) yield curve. From the above analysis, the following equations can be used to calculate forward rates for ‘simple’, discrete compounded and continuously compounded spot rates, respectively:  

$$
f_{m,n}=\left[{\frac{n}{n-m}}\right]r_{n}-\left[{\frac{m}{n-m}}\right]r_{m}=\left[{\frac{n r_{n}-m r_{m}}{n-m}}\right]
$$  

where $n>m$ and $n$ and $m$ are expressed in years or fractions of a year (using ‘actual/ $360^{\circ}$ convention for pricing FRAs). For example, if a $3\times6$ FRA has 91 days to maturity and the interest payment is after a further 91 days then $m=91/360$ and $n=182/360)$ . Alternatively, if simple interest rates have been ‘converted’ to equivalent continuously compounded spot rates (see Equation 8.13) and $n=3$ years, $m=2$ years, then (8.26c) gives $f_{23}=3r_{3}-2r_{2}$ .  

# 8.3.4 Spot and Forward (Yield) Curves  

It is a matter of arithmetic, that if the yield curve for spot rates4 between times $m$ and $n$ is upward sloping then the forward rate $f_{m,n}$ will be above the spot rate $r_{n}$ (and vice versa). Algebraically, this can be easily seen by a simple rearrangement of the continuously compounded forward rate equation:  

$$
f_{m,n}=\left[{\frac{n}{n-m}}\right]r_{n}-\left[{\frac{m}{n-m}}\right]r_{m}=r_{n}+\left[{\frac{m}{n-m}}\right]\left(r_{n}-r_{m}\right)
$$  

If $r_{n}>r_{m}$ then $f_{m,n}>r_{n}$ (i.e. the forward rate ending at time $n$ is greater than the $n$ -period spot rate).  

![](661795dab33550ffae2eab0bc87f271ff65faf5a8c341beb8ab62bb1606d9154.jpg)  
Upward sloping yield curve  

![](c9e93281ea1507a0e1077930db40b3616618859eabcd2420f61e7ccbed376b3d.jpg)  
Downward sloping yield curve   
FIGURE 8.2 Yield curve  

On the website an Excel fle takes data on 10 (continuously compounded) spot rates and calculates all the one-period forward rates $f_{t,t+k}\left(k=1,2,\ ...,\ 10\right)$ . In one example we assume an upward sloping (spot) yield curve and in the other, we assume a downward sloping curve and we then plot the spot and forward yield curves. When spot rates increase with time to maturity (i.e. $r_{1}<r_{2}<\ldots<r_{10})$ then the forward rate curve lies above the spot rate curve (and vice versa) – see Figure 8.2.  

Besides the obvious fact that forward rates directly tell you at what rates you can borrow (or lend) money over diferent horizons, starting sometime in the future, they are also widely used in pricing many diferent types of fxed-income securities – particularly derivative contracts based on interest rate products such as FRAs, T-bill and T-bond futures contracts, options on T-bonds, interest rate swap contracts, caps, foors, forward swaps and swaptions.  

# 8.4 FORWARD RATE AGREEMENTS (FRAs)  

In a forward rate agreement (FRA), one party may agree to receive a foating interest rate (e.g. LIBOR) in exchange for paying a known fxed rate of interest (of say $3\%$ p.a.), starting at a specifc date in the future. A forward rate agreement (FRA) is a form of forward contract that allows you to ‘fx’ or hedge interest-rate risk over a specifc time period, starting in the future.  

The FRA rate agreed in the contract at time $t=0$ can apply to any two dates in the future. For example, a $3\times6$ FRA has a fxed FRA rate equal to today’s quoted forward rate $f_{3,6}$ for the period beginning in 3 months time and ending in 6 months’ time. The quoted forward rate is calculated using ‘simple interest’ and an ‘actual/ $360^{\circ}$ day-count convention. A $6\times9$ FRA would most likely have a diferent quoted forward rate, $f_{6,9}$ since this forward rate applies to the period beginning in 6 months’ time and ending in 9 months’ time.  

# 8.4.1 Bank Loan  

If you have a foating rate bank loan with Citibank (at LIBOR), with an interest rate reset in 3 months’ time, and you fear a rise in interest rates, then your future borrowing costs will be higher. Conversely, if you have a bank deposit linked to a foating rate which is reset in 3 months’ time, then you will lose out if interest rates fall, since your deposit will earn less interest. We show that:  

To hedge a rise in future loan rates $\Rightarrow$ buy (‘go long’) an FRA.   
To hedge a fall in future deposit rates $\Rightarrow$ sell (‘short’) an FRA.  

Suppose on 16 December Ms Forward has an outstanding loan of $Q=\$100$ from Citibank. The previous interest rate reset-date was 15 December, when LIBOR was $2.5\%$ p.a. (say). Hence, over the period 15 December to 15 March the interest rate on the loan is determined by the LIBOR rate on 15 December of $2.5\%$ $(t=0)$ ), and Ms Forward can do nothing about this. The next loan interest rate reset date is 15 March ( $\mathit{i}=3$ months), when the interest rate charged on the loan will be the prevailing 3-month LIBOR rate on 15 March. The actual payment of the loan interest will take place on 15 June $\mathit{i}=6$ months).  

Assume that on 16 December Ms Forward thinks LIBOR rates will rise between 16 December and 15 March, increasing the interest cost of the loan at the next loan reset date. She continues to hold her bank loan from Citibank but she can hedge the interest rate risk by buying a $3\times6$ FRA today (from Morgan Stanley), at an agreed ‘fxed’ FRA rate $f_{3,6}=3\%$ p.a. (simple interest) to begin on 15 March and lasting for a further 92 days until 15 June. The payof to Ms Forward from the FRA at $T=15$ March:  

‘Payof’ from long FRA at $T=Q\left(L I B O R_{T}-A g r e e d F R A r a t e,f_{3,6}\right)\times(92/360).$  

Hence, if the out-turn LIBOR rate on 15 March is $3.5\%$ which is greater than the agreed FRA rate $f_{3,6}$ , the seller of the FRA (e.g. Morgan Stanley) will pay Ms Forward:  

Payof Ms Forward, long FRA at $T=\S10\mathrm{m}\left(0.035-0.03\right)\times\left(92/360\right)=\S12,778^{5}$  

Hence, if Ms Forward has a bank loan but also holds the (long) FRA, then the efective interest cost of the loan repayments on 15 March is:  

$$
\begin{array}{r l}&{=L I B O R_{T}\ (92/360)-(L I B O R_{T}-f_{3,6})(92/360)}\\ &{=f_{3,6}\times(92/360)}\end{array}
$$  

Hence, by taking out the FRA, Ms Forward has efectively swapped the foating-rate payments on her bank loan, for fxed-rate payments at the FRA rate $f_{3,6}=3\%$ , negotiated on 16 December (with JPMorgan). The efective dollar cost of the loan plus the long FRA is:  

Efective $\$8$ -cost of loan $\l=$ Actual interest loan Payof to  

$$
\begin{array}{c}{{=Q\left[L I B O R_{T}\left(92/360\right)-\left(L I B O R_{T}-f_{3,6}\right)\left(92/360\right)\right]}}\\ {{=Q f_{3,6}\times\left(92/360\right)=\S89,444-\S12,778=\S76,666}}\end{array}
$$  

The loan interest of $\$89,444$ is reduced by the payof from the long FRA, so the net payment is $\$76,666$ , which is $0.7666\%$ of $\$100$ over 92 days – that is, $3.0\%$ p.a. (using simple interest and scaling up by 360/92).  

Of course, if the 3-month LIBOR rate on 15 March turns out to be $2.5\%$ (i.e. lower than $f_{3,6}=3\%)$ then Ms Forward will pay $\$12,778$ to Morgan Stanley (the seller of the FRA). However, in this case, the interest payments on her original bank loan will be at the lower LIBOR rate of $2.5\%$ p.a. so again she efectively ends up with net payments (i.e. the bank loan plus the FRA) equal to the fxed FRA rate $f_{3,6}=3\%$ p.a.  

Banks are the main participants in the FRA market, which are OTC instruments. By taking a long position in the FRA, Ms Forward has efectively ‘swapped’ the payment on her bank loan at an unknown foating rate (i.e. future 3-month LIBOR), for a known fxed-rate payment at the FRA rate, $f_{3,6}=3\%$ p.a. As we shall see in later chapters an interest-rate swap is nothing more than a series of FRAs over several reset periods. For example, a 5-year swap with future interest payment reset dates every 6 months, is equivalent to 9 $(=10-1)$ separate FRAs, each with the same FRA rate applying to each of the 9 future reset dates. This constant FRA rate (which applies at each of the reset dates), is then renamed as ‘the swap rate’. Note that the 5-year swap is analytically equivalent to 9 FRAs because the frst payment in the swap is at the current known LIBOR rate at $t=0$ (see Chapter 33 for further details on swaps).  

# 8.4.2 Settlement Procedure  

Consider the settlement procedure for the FRA at $T=15$ March. An FRA is a contract on a notional principal amount $\$2$ . However, there is no exchange of principal at the beginning or end of the contract – only the diference in interest payments on the notional principal is paid.  

The ‘settlement rate’ used in the contract is usually an average of the (appropriate) LIBOR rates on the settlement date $T(15\mathrm{{March})}$ .  

The ‘payof’ from the $3\times6$ FRA can be calculated at $T=15$ March, but interest is paid in arrears so the actual interest payment is due on the 15 June (92 days later). However, if you wish to receive your funds from the FRA on 15 March (i.e. ‘cash settlement’), the amount you will be paid is the present value of the amount owed on 15 June. Consider the payment at settlement on the following $3\times6$ FRA:  

(i) $f_{3,6}=3\%$ (fxed on 16 December) on a notional principal of $Q=\$100$ (ii) Actual (92-day) LIBOR on 15 March, $L I B O R_{T}=3.5\%$  

To calculate the ‘cash settlement’ (for Ms Forward) which is to be paid on 15 March, note that the amount due on 15 June (92 days later) is ‘Payof’ $=Q\left(L I B O R_{T}-F R A\right.$ -rate) 92/360. So, if the cash payment actually takes place on 15 June, the amount received needs to be discounted at the 92-day LIBOR rate on 15 March hence:  

$$
{\begin{array}{r l}&{u a l~c a s h~p a y m e n t~15~M a r c h={\frac{1}{1+0.035(92/360)}}\left[{\mathfrak{H}}10{\overline{{\mathbf{m}}}}\ (0.035-0.03)\times(92/360)\right.}\\ &{\qquad\left.={\mathfrak{H}}12,778/1.008944={\mathfrak{H}}12,665\right.}\end{array}}
$$  

With an FRA, only the ‘diference in value’ is paid. The FRA is a ‘contract for diferences’, based on the diference between the out-turn LIBOR rate and the (fxed) FRA-rate, $f_{3,6}$ (and the notional principal amount, $Q$ ). If Ms Forward already has a variable-rate bank loan at 3-month LIBOR then she can use the long-FRA to ‘lock in’ the efective cost of the next loan interest payment at today’s quoted forward rate, $f_{3,6}$ . If the bank loan has several future interest rate reset dates then she needs a long-FRA for each reset date. This will lock in the efective cost of all the future loan interest payments at the current quoted forward rates $f_{3,6},f_{6,9},f_{9,12}$ , etc.  

# 8.4.3 Bank Deposit  

Suppose on 16 December Ms Forward has a bank deposit of $Q=\$100$ from Citibank, which pays 3-month LIBOR. Ms Forward is worried that interest rates will fall at the next reset date and she will earn less interest on her deposit account. To hedge her future deposit interest she should today, short (sell) an FRA. The payof to a short-FRA is:  

$$
{}^{*}P a y o f f i o s h o r t-F R A=Q\left(A g r e e d F R A r a t e,f_{3,6}-L I B O R_{T}\right)\times\left(92/360\right)
$$  

It follows that the bank deposit plus the short-FRA will provide an efective interest receipts of:  

Efective interest received $\c=$ Actual Interest Deposit Payof to  

$$
=L I B O R_{T}(92/360)+[f_{3,6}-L I B O R_{T}](92/360)=f_{3,6}\times(92/360)
$$  

and therefore Ms Forward ‘locks in’ an efective deposit interest rate of $f_{3,6}$ p.a., regardless of the out-turn value for LIBOR at the next reset date. Ms Forward may agree that any payments/receipts from the FRA are actually paid on 15 March, when the amount received needs to be discounted at the 92-day LIBOR rate on 15 March.  

# 8.5 SUMMARY  

• Calculating present value or terminal value can be undertaken using simple rates, compound rates, or continuously compounded interest rates. As long as we use the appropriate compounding or present value formulas for each type of interest rate, we obtain the same present value or terminal value.   
• The relationship between simple rates, compound rates, and continuously compounded interest rates, enables us to switch between the diferent rates.   
• A forward rate is an interest rate which applies to an investment which occurs between two future time periods. Forward rates can be calculated from spot rates. There is a spot yield curve and a forward yield curve.   
• Forward rates can be calculated using simple, compound, and continuously compounded spot rates of interest.   
• When pricing a forward rate agreement (FRA) we use forward rates that are calculated from spot-rates (using ‘simple interest’) and an ‘actual/ $360^{\circ}$ day-count convention.   
• An FRA is a contract agreed today, to exchange a cash fow based on the future LIBOR rate, in exchange for a fxed cash fow at the (pre-agreed) FRA rate. Only the diference in interest cash fows is paid (or received).  

A ‘long position’ in an FRA on a notional principle of $Q={\mathfrak{S}}100{\mathrm{m}}$ has:  

$$
\begin{array}{r}{P a y o f f,l o n g–F R A=\S Q\left(L I B O R_{T}-f x e d r a t e i n F R A\right)}\\ {\times\left(a c t u a l d a y s t o m a t u r i t y/360\right).}\end{array}
$$  

• To hedge a future payment on a bank loan linked to LIBOR, you should go long an FRA. To hedge a future payment on a bank deposit linked to LIBOR, you should short an FRA. In both cases you then ‘lock-in’ the current quoted forward rate, regardless of what happens to LIBOR rates in the future.  

# EXERCISES  

# Question 1  

Suppose a sum of $\$2,000$ is invested for a period of 7 months. The value of the investment at maturity is $\$2,150$ . Assuming a day-count convention of 360 days p.a. (a) Calculate the  

simple interest rate. (b) Calculate the equivalent compound interest rate and continuously compounded rate.  

# Question 2  

Suppose you make an investment of $\$50,000$ today that will attract an annual compound rate of $10\%$ p.a. How long will it take for your investment to amount to \$1m?  

# Question 3  

A 90-day T-bill has a face (par or maturity) value $M=\$100$ . Its market price is $P=\$97.5$ . Calculate the percent return you earn over 90 days if you buy this T-bill today and hold it to maturity – this is the ‘periodic return’ or ‘periodic rate of interest’ (yield) over 90 days.  

(This example could also apply to an investment in a bank deposit of $P=\$97.5$ and after 90 days you receive $M=\$100$ .)  

Assume we use ‘actual/ $365^{\prime}$ convention to scale up to an annual rate. The ‘actual number of days’ you hold the T-bill (or bank deposit) is 90, so $T=90/365$ years.  

Show that:  

(a) simple interest rate (yield) is $10.399\%$ p.a.   
(b) compound interest rate (yield) is $10.8134\%$ p.a.   
(c) continuously compounded interest rate (yield) is $10.268\%$ p.a.   
(d) What is the intuitive interpretation of these diferent interest rate conventions? Why is the simple annual rate ( $10.399\%$ p.a.) less than the compound rate ( $10.8134\%$ p.a.)?   
(e) Why is the continuously compounded rate $10.268\%$ p.a. less than the compound rate of $10.8134\%$ p.a.? Explain.  

Note also that the T-bill has a quoted discount rate of $10\%$ (actual/360 day count basis) and its market price has been calculated from the discount rate:  

$$
P=(M\mathrm{-Dollardiscount})=100-(90/360)(0.10)100=97.5
$$  

Note the use of ‘actual days/ $360^{\circ}$ to get the price – this is the (US) market convention when using the discount rate to calculate the price of a T-bill.  

# Question 4  

Very briefy, mention one practical use for spot interest rates and one practical use of forward interest rates.  

# Question 5  

The 1-year spot yield is $9\%$ p.a., the 2-year spot yield is $9.5\%$ p.a. and the 3-year spot yield is $10\%$ p.a. (compound rates).  

(a) Calculate the implied 1-year ahead, 1-year forward rate, $f_{12}$ . Explain. (b) Explain why a 1-year forward rate of $9.6\%$ would not be expected to prevail in the market.  

# Question 6  

(c) You can lend $\$100$ to a bank at a quoted forward interest rate $f_{1,2}^{q}=13\%$ p.a.. The 1-year and 2-year spot rates (yields) are currently $10\%$ p.a. and $12\%$ p.a., respectively (compound rates). Explain whether you would take the bank’s forward rate ofer.  

# Question 7  

Suppose a frm plans to borrow $\$5$ million in 180 days from bank-A at $12\%$ p.a. with tenor of 90 days (actual/360 day-count convention). The loan will be taken out at whatever 90-day LIBOR is on the day the loan begins and will be repaid in one lump sum, 90 days later. The frm would like to lock in the loan rate it pays so it enters into an FRA with bank-B. Determine the annualized cost of the ‘loan $^+$ FRA’ (compounded using 365-day year) for each of the following outcomes:  

(a) LIBOR in 180 days is $14\%$ .   
(b) LIBOR in 180 days is $8\%$ .  

# Question 8  

A company has a $\$200$ variable rate loan and faces an interest payment at the 6-month variable interest rate, 6 months from now. There is a concern that interest rates will rise over the next 6 months but this is not certain. The company is struggling to decide whether to hedge or not. After assessing the interest rate outlook, the company decides to hedge $50\%$ of its exposure and enters a $6\times12$ FRA on notional principal of $\$100$ at a FRA rate of $4\%$ p.a. Suppose the 6-month spot interest rate at $t=6$ months is $4.5\%$ p.a. Assume 6 months is $^1/_{2}$ year. Explain the company’s dollar net position on the FRA settlement date.  