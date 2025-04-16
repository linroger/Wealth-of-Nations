---
tags:
  - '#barbell_portfolio'
  - '#coupon_bonds'
  - '#equity_swaps'
  - '#forward_contracts'
  - '#futures_contracts'
  - '#interest_rate_derivatives'
  - '#interest_rate_swaps'
  - '#libor'
  - '#yield_curve_calculation'
  - '#zero_coupon_bonds'
---
# 3.14 CONCLUSIONS  

This chapter has developed two main ideas. First, we considered the engineering aspects of simple interest rate derivatives such as forward loans and FRAs. Second, we developed our first contractual equation. This equation was manipulated to obtain synthetic loans, synthetic deposits, and synthetic FRAs. A careful use of such contractual equations may provide useful techniques that are normally learned only after working in financial markets. We introduced the term structure of interest rates and introduced the forward rate (LIBOR) processes. The chapter continued to build on the simple graphical financial engineering methods that are based on cash flow manipulations.  

Before concluding, we would like to emphasize some characteristics of forward contracts that can be found in other swap-type derivatives as well. It is these characteristics that make these contracts very useful instruments for market practitioners.  

First, at the time of initiation, the forward (future) contract did not require any initial cash pay-. ments. This is a convenient property if our business is trading contracts continuously during the day. We basically don't have to worry about "funding" issues..  

Second, because forward (future) contracts have zero initial value, the position taker does not have anything to put on the balance sheet. The trader did not "buy' or "sell' something tangible. With a forward (futures) contract, the trader has simply taken a position. So these instruments are off-balance sheet items.  

Third, forward contracts involve an exchange at a future date. This means that if one of the counterparties "defaults" before that date, the damage will be limited, since no principal amount was extended. What is at risk is simply any capital gains that may have been earned.  

# SUGGESTED READING  

Futures and forward markets have now been established for a wide range of financial contracts, commodities, and services. This chapter dealt only with basic engineering aspects of interest rate forwards and futures contracts, and a comprehensive discussion was avoided. It may be best to go over a survey of existing futures and forward contracts. We recommend two good introductory sources. The first is the Foreign Exchange and Money Markets, an introductory survey prepared by Reuters and published by Wiley. Hull (2014), Das (1994), and Wilmott (2006) are among the best sources for a detailed analysis of forward and futures contracts. There are many more fixed income instruments involving more complicated parameters than those discussed here. Some of these will certainly be examined in later chapters. But reading some market-oriented books that deal with technical aspects of these instruments may be helpful at this point. Two such books are Serrat and Tuckman (2011) and Questa (1999). McNeil et al. (2005) provide a review of quantitative risk management and VaR.  

# APPENDIXCALCULATING THE YIELD CURVE  

How do we calculate the (government) yield curve?5 The traditional way of calculating yield curves starts with liquid bond prices and then obtains the discounts and related yields. Thus, the method first calculates the implied zero-coupon prices, and then the corresponding yields and forward rates from observed coupon bond prices.  

We will briefly review this approach to yield curve calculation. It may still be useful in markets where liquid interest rate derivatives do not trade. First, we need to summarize the concepts..  

# PAR YIELD CURVE  

Consider a straight coupon bond with coupon rate $c$ exactly equaling the yield at time $t$ for that maturity. The current price of this "par' bond will be exactly 100, the par value. Such a bond will have a yield to maturity, the par yield. The current price of these bonds is equal to 100 and their coupon would be indicative of the correct yield for that maturity and credit at that particular time.  

We can write the present value of a three-period par bond, paying interest annually, as  

$$
100={\frac{100c}{(1+y)}}+{\frac{100c}{{(1+y)}^{2}}}+{\frac{100(1+c)}{{(1+y)}^{2}}}
$$  

where the par yield implies that $c=y$  

This property is desirable because with coupon bonds, the maturity does not give the correct timing for the average cash receipt, and if we consider bonds with coupons different than the par yield, the durations of the bonds would be different and the implied yields would also differ.  

# ZERO-COUPON YIELD CURVE  

We can also calculate a yield curve using zero-coupon bonds with par value 100 by exploiting the equality,  

$$
B(t,T)=\frac{100}{(1+y_{t}^{T})^{T-t}}
$$  

where $B(t,T)$ is time- $t$ price of default-free zero-coupon bond that pays 100 at time $T.$ The $y_{t}^{T}$ will correspond to the. $(T-t)$ -maturity zero-coupon yield.  

It turns out that the par yield curve and the zero-coupon yield curve are different in general. We now show the calculations in an example.  

# EXAMPLE  

We would like to show the relationship between par yields and zero-coupon yields. Suppose we are given the following zero-coupon bond prices:.  

$$
\begin{array}{r}{B(0,1)=96.00}\ {B(0,2)=91.00}\ {B(0,3)=87.00}\end{array}
$$  

1. What are the zero-coupon yields? 2. What are the par yields for the same maturities? To calculate the zero-coupon yields, we use the following formula:  

$$
B(t,T)=\frac{100}{(1+y_{t}^{T})^{T-t}}
$$  

and obtain:  

$$
96.00=\frac{100}{{(1+y_{0}^{1})}^{1}}
$$  

Solving for the unknown zero-coupon yields:  

$$
y_{0}^{1}=0.04167,\quad y_{0}^{2}=0.04828,\quad y_{0}^{3}=0.04752
$$  

We now calculate par yields using the relationship with $t_{n}=T$  

$$
P(t_{0},T)=\sum_{i=0}^{n}\tilde{y}B(t_{0},t_{i})+B(t_{0},T)=100
$$  

Thee $\tilde{y}$ that satisfies this equation will be the par yield for maturity $T.$ The idea here is that, when discounted by the correct discount rate, the sum of the cash flows generated by a par bond should equal 100; i.e., we must have $P(t_{0},T)=100.$ Only one. $\tilde{y}$ will make this possible for every $T.$  

Calculating the par yields, we obtain  

$$
\tilde{y}_{0}^{1}=y_{0}^{1}=0.04167,\quad\tilde{y}_{0}^{2}=0.04813,\quad\tilde{y}_{0}^{3}=0.04745
$$  

As these numbers show, the par yields and the zero-coupon yields are slightly different.  

# ZERO-COUPON CURVE FROM COUPON BONDS  

Traditional methods of calculating the yield curve involve obtaining a zero-coupon yield curve. from arbitrary coupon bond prices. This procedure is somewhat outdated now, but it may still be useful in economies with newly developing financial markets. Also, the method is a good illustration of how synthetic asset creation can be used in yield curve construction. It is important to. remember that all these calculations refer to default-free bonds.  

Consider a 2-year coupon bond. The default-free bond carries an annual coupon of $c$ percent and has a current price of $P$ $\textit{P}(t,t+2)$ . The value at maturity is 100. Suppose we know the level of the current annual interest rate $r_{t}$ 36 Then the portfolio  

$\left\{\frac{100c}{(1+r_{t})}\right.$ units of time $t$ borrowing, and buying two-period coupon bond, $P(t,t+2)\Biggr\}$ will yield the cash flow equivalent to $1+c$ units of a two-period discount bond. Thus, we have  

$$
P(t,t+2)-{\frac{100c}{1+r_{t}}}=(100(1+c))/(1+y_{t}^{2})^{2}
$$  

If the coupon bond price $P(t,t+2)$ and the 1-year interest rate $r_{t}$ are known, then the 2-year zero-coupon yield $y_{t}^{2}$ can be calculated from this expression. Zero-coupon yields for other maturities can be calculated by forming similar synthetics for longer maturity zero-coupon bonds, recursively.  

# EXERCISES  

1. You have a 4-year coupon bond that pays semiannual interest. The coupon rate is $8\%$ and the par value is 100. a. Can you construct a synthetic equivalent of this bond? Be explicit and show your cash flows. b. Price this coupon bond assuming the following term structure (represented by bid/ask prices. at annual frequency) and by using a linear interpolation to discount semi-annual cashflows: $B_{1}=0.90/0.91,\quad B_{2}=0.87/0.88,\quad B_{3}=0.82/0.83,\quad B_{4}=0.80/0.81$  

c. What is the $1\times2$ FRA rate?  

2. You have purchased 1 Eurodollar contract at a price of $Q_{0}=94.13$ , with an initial margin of $5\%$ . You keep the contract for 5 days and then sell it by taking the opposite position. In the meantime, you observe the following settlement prices:  

$$
\{Q_{1}=94.23,Q_{2}=94.03,Q_{3}=93.93,Q_{4}=93.43,Q_{5}=93.53\}
$$  

a. Calculate the string of mark-to-market losses or gains.  

b. Suppose the spot interest rate during this 5-day period was unchanged at $6.9\%$ . What is the total interest gained or paid on the clearing firm account?   
c. What are the total gains and losses at settlement?  

l. The treasurer of a small bank has borrowed funds for 3 months at an interest rate of $6.73\%$ and has lent funds for 6 months at. $7.87\%$ . The total amount is USD38 million..  

To cover his exposure created by the mismatch of maturities, the dealer needs to borrow another USD38 million for months, in 3 months' time, and hedge the position now with an FRA The market has the following quotes from three dealers:.  

<html><body><table><tr><td>BANK A</td><td>3×6</td><td>6.92-83</td></tr><tr><td>BANK B</td><td>3×6</td><td>6.87-78</td></tr><tr><td>BANK C</td><td>3×6</td><td>6.89-80</td></tr></table></body></html>  

a. What is (are) the exposure(s) of this treasurer? Represent the result on cash flow diagrams.   
b. Calculate this treasurer's break-even forward rate of interest, assuming no other costs.   
c.What is the best FRA rate offered to this treasurer?.  

d. Calculate the settlement amount that would be received (paid) by the treasurer if, on the settlement date, the LIBOR fixing was. $6.09\%$  

4. A corporation will receive UsD7 million in 3 months' time for a period of 3 months. The current 3-month interest rate quotes are $5.67{-}5.61$ . The Eurodollar futures price is 94.90. Suppose in 3 months the interest rate becomes $5.25\%$ for 3-month Eurodeposits and the. Eurodollar futures price is 94.56.. a. How many ticks has the futures price moved? b. How many futures contracts should this investor buy or sell if she wants to lock in the current rates? c. What is the profit (loss) for an investor who bought the contract at 94.90?.  

5. Suppose practitioners learn that the ICE Benchmark Administration (IBA) will change the panel of banks used to calculate the yen LIBOR. One or more of the "weaker"' banks will be replaced by "stronger' banks at a future date. IBA replaced the British Banker's Association (BBA) in 1 February 2014.  

The issue here is not whether yen LIBOR will go down, as a result of the panel now being. "stronger." In fact, due to market movements, even with stronger banks in the panel, the yen. LIBOR may in the end go up significantly. Rather, what is being anticipated is that the yen. LIBOR should decrease in London relative to other yen fixings, such as Tibor. Thus, to. benefit from such a BBA move, the market practitioner must form a position where the risks originating from market movements are eliminated and the "only" relevant variable remains the decision by the BBA.  

a. How would a trader benefit from such a change without taking on too much risk?  

b. Using cash flow diagrams, show how this can be done.  

c. In fact, show which spread FRA position can be taken. Make sure that the position is (mostly) neutral toward market movements and can be created, the only significant variable being the decision by the IBA.  

(From Thomson Reuters IFR, issue 1267) Traders lost money last week following the British Bankers' Association (BBA) decision to remove one Japanese bank net from the. yen LIBOR fixing panel. The market had been pricing in no significant changes to the. panel just the day before the changes were announced.  

Prior to the review, a number of dealers were reported to have been short the LIBOR/ Tibor spread by around 17 bp, through a twos into fives forward rate agreement (FRA). spread contract. This was in essence a bet that the Japanese presence on the LIBOR fixing. panel would be maintained.  

When the results of the review were announced on Wednesday January 20, the spread moved out by around 5 bp to around 22 bp-leaving the dealers with mark-to-market losses. Some were also caught out by a sharp movement in the one-year yen/dollar LIBOR basis swap, which moved in from minus 26 bp to minus 14 bp.  

The problems for the dealers were caused by BBA's decision to alter the nature of the fixing panel, which essentially resulted in one Japanese bank being removed to be replaced by a foreign bank. Bank of China, Citibank, Tokai Bank and Sakura were taken out, while Deutsche Bank, Norinchukin Bank, Rabobank and WestLB were added.  

The move immediately increased the overall credit quality of the grouping of banks responsible for the fixing rate. This caused the yen LIBOR fix-the average cost of panel banks raising funds in the yen money market-to fall by 8 bp in a single day. Dealers saic. that one Japanese bank was equivalent to a 5 bp lower yen LIBOR rate and that the removal of the Bank of China was equivalent to a 1 bp or 2 bp reduction..  

Away from the immediate trading losses, market reaction to the panel change was mixed. The move was welcomed by some, who claimed that the previous panel was unrepresentative of the yen cash business being done.  

"Most of the cash is traded in London by foreign banks. It doesn't make sense to have half Japanese banks on the panel," said one yen swaps dealer. He added that because of the presence of a number of Japanese banks on the panel, yen LIBOR rates were being pushed above where most of the active yen cash participants could fund themselves in the market. Others, however, disagreed. "It's a domestic [Japanese] market at the end of the day. The BBA could now lose credibility in Japan," said one US bank money markets trader. BBA officials said the selections were made by the BBA's FX and Money Markets Advisory Panel, following private nominations and discussions with the BBA LIBOR Steering Group. They said the aim of the advisory panel was to ensure that the contributor panels broadly reflected the "balance of activity in the interbank deposit market."  

6. You are given the following information:  

<html><body><table><tr><td>3-mLIBOR</td><td>3.2%</td><td>92days</td></tr><tr><td>3X6FRA</td><td>3.3%-3.4%</td><td>90days</td></tr><tr><td>6×9FRA</td><td>3.6%-3.7%</td><td>90days</td></tr><tr><td>9 × 12 FRA</td><td>3.8%-3.9%</td><td>90days</td></tr></table></body></html>  

a. Show how to construct a synthetic 9-month loan with fixed rate beginning with a 3-month loan. Plot the cash flow diagram. b. What is the fixed 9-month borrowing cost? . Consider the following instruments and the corresponding quotes. a. Rank these instruments in increasing order of their yields.  

<html><body><table><tr><td>Instrument</td><td>Quote</td></tr><tr><td>30-day US T-bill</td><td>5.5</td></tr><tr><td>30-dayUK T-bill</td><td>5.4</td></tr><tr><td>30-dayECP</td><td>5.2</td></tr><tr><td>30-dayinterbankdepositUSD</td><td>5.5</td></tr><tr><td>30-dayUSCP</td><td>5.6</td></tr></table></body></html>  

b. You purchase an ECP (Euro) with the following characteristics  

<html><body><table><tr><td>Valuedate Maturity</td><td>July 29,2002 September29,2002</td></tr></table></body></html>  

What payment do you have to make?  

8. Determine the dollar settlement of the $3\times6$ FRA for the amount $\$300,000$ assuming (a) the settlement occurs on the date of loan initiation and (b) if settlement occurs on the date of loan repayment. Use the following data to carry out the calculations. Interest rates are expressed as stated annual interest rates.  

$3\times6$ FRA rate $F_{t_{0}}=4.38\%$ and 3-m LIBOR rate $L_{t_{3}}=4.02\%$  

9. Assume the Eurodollar futures price at time $t_{0}$ is 93.83 and the contract expires in 3 months time a. Calculate the 3-month forward rate implied by this price. b. Calculate the repayment amount for bonds with maturities of 3, 6, 9 and 12 months if the investor bought $\$5$ million future contracts.  

0. Using the following bond price data calculate the $3\times6,6\times9,3\times9$ and $6\times12$ FRA rates.  

$$
B(t_{0},t_{1})=98.79,\quad B(t_{0},t_{2})=97.21,\quad B(t_{0},t_{3})=95.84,\quad B(t_{0},t_{4})=93.82
$$  

11. Barbell example.  

On June 16, 2014, a fund manager is considering the purchase of $\$1$ million face amount of US Treasury $1\textstyle{\frac{1}{2}}\mathrm{s}$ with a maturity date of May 31, 2019 at a cost of 990,468.75. The manager examines the bond further and, using his Bloomberg terminal, notices that the bond has a yield of $1.701\%$ and a modified duration of 4.748. Before deciding to buy the bond the manager considers the information in the following table about two other bonds:  

<html><body><table><tr><td colspan="6">Data on Three US Treasury Bonds as of June 16, 2014</td></tr><tr><td>Coupon</td><td>Maturity</td><td>Price</td><td>Yield</td><td>Duration</td><td>Convexity</td></tr><tr><td>0</td><td>May 31,2016</td><td>99.8398438</td><td>0.457%</td><td>1.943</td><td>0.048</td></tr><tr><td>1</td><td>May 31,2019</td><td>99.046875</td><td>1.701%</td><td>4.748</td><td>0.254</td></tr><tr><td>2</td><td>May 15,2024</td><td>99.140625</td><td>2.598%</td><td>8.701</td><td>0.859</td></tr></table></body></html>  

The three bonds in the table have maturities of approximately 2, 5, and 10 years. The fund manager could purchase the 1/ bond or alternatively a barbell portfolio consisting of the $0\%$ and the $2\%$ bonds. In a barbell portfolio, part of the portfolio is made up of long-term bonds. and the other part comprises very short-term bonds. The term "barbell' is based on the notion that the strategy resembles a barbell, heavily weighted at both ends and with nothing in between. Construct such a barbell portfolio and evaluate the alternative barbell strategy compared to the $1\%$ bond investment. Such barbell portfolio should be constructed to cost the same and have the same duration as the bullet investment. Your evaluation should consider the yield and the convexity of the. $1\%$ bond relative to the barbell strategy.  

# INTRODUCTION TO INTERESTRATE SWAP ENGINEERING  

# 4  

# CHAPTER OUTLINE  

#  

4.1 The Swap Logic 108   
4.1.1 The Equivalent of Zero in Finance... 108   
4.1.2 A Generalization. 111   
4.2 Applications .. 111   
4.2.1 Equity Swap. 111   
4.3 The Instrument: Swaps . 115   
4.4 Types of Swaps... 117   
4.4.1 Noninterest-Rate Swaps. 117   
4.4.1.1 Equity swaps .117   
4.4.2 Interest-Rate Swaps.. 119   
4.4.2.1 Basis swaps. 122   
4.4.2.2 What is an asset swap?. .123   
4.4.2.3 More complex swaps.. .124   
4.4.3 Swap Conventions . 124   
4.5 Engineering Interest-Rate Swaps.... .124   
4.5.1 A Horizontal Decomposition 126   
4.5.1.1 A synthetic coupon bond.. 127   
4.5.1.2 Pricing.. .127   
4.5.1.3 Valuing fixed cash flows.. .128   
4.5.1.4 Valuing floating cash flows 129   
4.5.1.5 An important remark 130   
4.5.2 A Vertical Decomposition.... . 130   
4.5.2.1 Pricing.. .133   
4.6 Uses of Swaps ... 133   
4.6.1 Uses of Equity Swaps . 134   
4.6.1.1 Fund management. 134   
4.6.1.2 Tax advantages. .134   
4.6.1.3 Regulations.. .135   
4.6.1.4 Creating synthetic positions .136   
4.6.1.5 Stripping credit risk .. .137   
4.6.2 Using Interest-Rate and Other Swaps 137   
4.6.3 Two Uses of Interest-Rate Swaps 138   
4.6.3.1 Changing portfolio duration. .138   
4.6.3.2 Using swaps to reduce a country's debt level. .138   
4.6.3.3 Technical uses. 139   
.7 Mechanics of Swapping New Issues. .140   
4.7.1 All-in-Cost .. 142   
4.8 Some Conventions.. 144   
4.8.1 Quotes.. 144   
4.9 Additional Terminology.. 145   
4.10 Conclusions.. . 145   
Suggested Reading 145   
Exercises . 146  
