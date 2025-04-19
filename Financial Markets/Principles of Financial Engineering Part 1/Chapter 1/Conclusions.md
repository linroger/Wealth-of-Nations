---
tags:
  - corporate_finance
  - financial_engineering
  - financial_instruments
  - risk_management
  - synthetics
aliases:
  - Chapter Conclusions
key_concepts:
  - Japanese loans and forwards
  - financial markets and instruments
  - regulation and taxation
  - solving practical problems
  - synthetics and replicating portfolios
---

# 1.6 CONCLUSIONS  

This chapter uses some examples in order to display the use of synthetics (or replicating portfolios as they are called in formal models). The main objective of this book is to discuss methods that use financial markets, instruments, and financial engineering strategies in solving practical problems concerning pricing, hedging, risk management, balance sheet management, and product. structuring. The book does not discuss the details of financial instruments, although for completion, some basics are reviewed when necessary. The book deals even less with issues of corporate finance. We assume some familiarity with financial instruments, markets, and rudimentary corpo-. rate finance concepts.  

Finally, the reader must remember that regulation, taxation, and even the markets themselves. are "dynamic" objects that change constantly. Actual application of the techniques must update the parameters mentioned in this book.  

# SUGGESTED READING  

There are excellent sources for studying financial instruments, their pricing, and the associated modeling. An excellent source for instruments and markets is Hull (2014). For corporate finance, Brealey and Myers (2013) and Ross et al. (2012) are two well-known references. Bodie et al. (2014) is recommended as background material on investments. Wilmott (2006) is a comprehensive and important source. Duffie (2001) provides the foundation for solid asset pricing theory.  

# EXERCISES  

1. Which two instruments can be used to replicate the payoffs of an IRS?.   
2. What are Eurodollars?   
3. Which two instruments can be used to create the payoffs of an equity swap?   
4. How can a synthetic foreign currency loan be engineered?  

# CASE STUDY: JAPANESE LOANS AND FORWARDS  

You are given the Reuters news item below. Read it carefully. Then answer the following questions.  

1. Show how Japanese banks were able to create the dollar-denominated loans synthetically using cash flow diagrams.   
2. How does this behavior of Japanese banks affect the balance sheet of the Western counterparties?.   
3. What are nostro accounts? Why are they needed? Why are the Western banks not willing to hold the yens in their nostro accounts?   
4. What do the Western banks gain if they do that?   
5. Show, using an "appropriate' formula, that the negative interest rates can be more than compensated by the extra. points on the forward rates. (Use the decompositions given in the text.). NEw YORK, (Reuters) - Japanese banks are increasingly borrowing dollar funds via the foreign exchange markets   
rather than in the traditional international loan markets, pushing some Japanese interest rates into negative territory,   
according to bank officials. The rush to fund in the currency markets has helped create the recent anomaly in short-term interest rates. For the   
first time in years, yields on Japanese Treasury bills and some bank deposits are negative, in effect requiring the lender   
of yen to pay the borrower. Japanese financial institutions are having difficulty getting loans denominated in U.S. dollars, experts said. They.   
said international banks are weary of expanding credit lines to Japanese banks, whose balance sheets remain burdened   
by bad loans. "The Japanese banks are still having trouble funding in dollars," said a fixed-income strategist at Merrill Lynch & Co.. So Japan's banks are turning to foreign exchange transactions to obtain dollars. The predominant mechanism for   
borrowing dollars is through a trade combining a spot and forward in dollar/yen.. Japanese banks typically borrow in yen, which they have no problem getting. With a three-month loan, for instance,   
the Japanese bank would then sell the yen for dollars in the spot market to, say, a British or American bank. The   
Japanese bank simultaneously enters into a three-month forward selling the dollars and getting back yen to pay off the   
yen loan at the stipulated forward rate. In effect, the Japanese bank has obtained a three-month dollar loan. Under normal circumstances, the dealer providing the transaction to the Japanese bank should not make anything   
but the bid-offer spread. But so great has been the demand from Japanese banks that dealers are earning anywhere from seven to 10 basis   
noints from the spot-forward trade. The problem is that the transaction saddles British and American banks with yen for three months. Normally,   
international banks would place the yen in deposits with Japanese banks and earn the three-month interest rate. But most Western banks are already bumping against credit limits for their banks on exposure to troubled Japanese.   
banks. Holding the yen on their own books in what are called NOsTRO accounts requires holding capital against them   
for regulatory purposes. So Western banks have been dumping yen holdings at any cost-to the point of driving interest rates on Japanese   
Treasury bills into negative terms. Also, large Western banks such as Barclays Plc and J.P. Morgan are offering   
negative interest rates on yen deposits-in effect saying no to new yen-denominated deposits. Western bankers said they can afford to pay up to hold Japanese Treasury bills-in effect earning negative yield   
because their earnings from the spot-forward trade more than compensate them for their losses on holding Japanese.   
paper with negative yield. Japanese six-month T-bills offer a negative yield of around O.o02 percent, dealers said. Among banks offering a   
negative interest rate on yen deposits was Barclays Bank Plc, which offered a negative O.02 percent interest rate on a   
three-month deposit.. The Bank of Japan, the central bank, has been encouraging government-lending institutions to make dollar loans to  

Japanese corporations to overcome the problem, said [a market professional]. (Reuters, November 9, 1998).  

This page intentionally left blank  

# INSTITUTIONAL ASPECTS OF DERIVATIVE MARKETS  

# 2  

# CHAPTER OUTLINE  

2.1 Introduction.. 26   
2.2 Markets.. 26   
2.2.1 Euromarkets. 27   
2.2.1.1 Eurocurrency markets 27   
2.2.1.2 Eurobond markets. .27   
2.2.1.3 Other Euromarkets . .28   
2.2.2 Onshore Markets . 28   
2.2.2.1 Futures and options exchanges .29   
2.2.2.2 Futures compared with forward contracts. .30   
2.2.3 Changes to the Infrastructure of Derivatives Markets Following the GFC 34   
2.3 Players.. . 35   
2.4 The Mechanics of Deals .... .36   
2.4.1 Orders. 37   
2.4.2 Confirmation and Settlement. . 38   
2.4.2.1 Regulatory update following the GFC. 39   
2.5 Market Conventions 39   
2.5.1 What to Quote... 40   
2.6 Instruments. 41   
..7 Positions . 41   
2.7.1 Long and Short Positions 41   
2.7.1.1 Payoff diagrams 42   
2.7.1.2 Real-world complications and short selling. 44   
2.7.2 Payoff Diagrams for Forwards and Futures ... 45   
2.7.3 Types of Positions.. 49   
2.7.3.1 Arbitrage 49   
2.7.3.2 Comparing performance. 50   
2.8 The Syndication Process. 50   
2.8.1 Selling Securities in the Primary Market.. 50   
2.8.1.1 Svndication of a bond versus a svndicated loan.... .51   
2.9 Conclusions. 51   
Suggested Reading 51   
Exercises . 51  
