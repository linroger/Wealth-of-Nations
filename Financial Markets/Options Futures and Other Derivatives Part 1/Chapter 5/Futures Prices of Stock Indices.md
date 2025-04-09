# 5.9 FUTURES PRICES OF STOCK INDICES  

We introduced futures on stock indices in Section 3.5 and showed how a stock index futures contract is a useful tool in managing equity portfolios. Table 3.3 shows futures prices for a number of different indices. We are now in a position to consider how index futures prices are determined.  

A stock index can usually be regarded as the price of an investment asset that pays dividends. The investment asset is the portfolio of stocks underlying the index, and the  

# Business Snapshot 5.3 The CME Nikkei 225 Futures Contract  

The arguments in this chapter on how index futures prices are determined require that the index be the value of an investment asset. This means that it must be the value of a portfolio of assets that can be traded. The asset underlying the Chicago Mercantile Exchange's futures contract on the Nikkei 225 Index does not qualify, and the reason why is quite subtle. Suppose $S$ is the value of the Nikkei 225 Index. This is the value of a portfolio of 225 Japanese stocks measured in yen. The variable underlying the CME futures contract on the Nikkei 225 has a dollar value of 5S. In other words, the futures contract takes a variable that is measured in yen and treats it as though it is dollars.  

We cannot invest in a portfolio whose value will always be 5S dollars. The best we. can do is to invest in one that is always worth 5S yen or in one that is always worth 5QS dollars, where $Q$ is the dollar value of 1 yen. The variable 5S dollars is not,. therefore, the price of an investment asset and equation (5.8) does not apply..  

CME's Nikkei 225 futures contract is an example of a quanto. A quanto is a derivative where the underlying asset is measured in one currency and the payoff is in another currency. Quantos will be discussed further in Chapter 30.  

dividends paid by the investment asset are the dividends that would be received by the holder of this portfolio. It is usually assumed that the dividends provide a known yield rather than a known cash income. If. $q$ is the dividend yield rate (expressed with. continuous compounding), equation (5.3) gives the futures price,. $F_{0}$ aS  

$$
F_{0}=S_{0}e^{(r-q)T}
$$  

This shows that the futures price increases at rate $r\mathrm{~-~}q$ with the maturity of the futures contract. In Table 3.3, the S&P 500 settlements are declining at roughly $0.5\%$ per six months, or $1\%$ per year. This indicates that the dividend yield anticipated by the market on the S&P 500 during the first year was about $1\%$ per annum greater than the risk-free rate.  

# Example 5.5  

Consider a 3-month futures contract on an index. Suppose that the stocks underlying the index provide a dividend yield of. $1\%$ per annum (continuously compounded), that the current value of the index is 1,300, and that the continuously compounded risk-free interest rate is $5\%$ per annum. In this case,. $r=0.05$ $S_{0}=1\ensuremath{,}300$ $T=0.25$ , and $q=0.01$ . Hence, the futures price, $F_{0}$ , is given by  

$$
F_{0}=1,300e^{(0.05-0.01)\times0.25}=\S1{,}313{.}07
$$  

In practice, the dividend yield on the portfolio underlying an index varies week by week throughout the year. For example, a large proportion of the dividends on the NYSE. stocks are paid in the first week of February, May, August, and November each year. The chosen value of $q$ should represent the average annualized dividend yield during the life of the contract. The dividends used for estimating $q$ should be those for which the ex-dividend date is during the life of the futures contract.  

# Business Snapshot 5.4. Index Arbitrage in October 1987  

To do index arbitrage, a trader must be able to trade both the index futures contract and the portfolio of stocks underlying the index very quickly at the prices quoted in the market. In normal market conditions this is possible using program trading, and the relationship in equation (5.8) holds well. Examples of days when the market was. anything but normal are October 19 and 20 of 1987. On what is termed "Black Monday,' October 19, 1987, the market fell by more than $20\%$ , and the 604 million shares traded on the New York Stock Exchange easily exceeded all previous records. The exchange's systems were overloaded, and orders placed to buy or sell shares on that day could be delayed by up to two hours before being executed.  

For most of October 19, 1987, futures prices were at a significant discount to the underlying index. For example, at the close of trading the S&P 500 Index was at 225.06 (down 57.88 on the day), whereas the futures price for December delivery on the S&P 500 was 201.50 (down 80.75 on the day). This was largely because the delays in processing orders made index arbitrage impossible. On the next day, Tuesday, October 20, 1987, the New York Stock Exchange placed temporary restrictions on. the way in which program trading could be done. This also made index arbitrage very difficult and the breakdown of the traditional linkage between stock indices and stock. index futures continued. At one point the futures price for the December contract was $18\%$ less than the S&P 500 Index. However, after a few days the market returned to. normal, and the activities of arbitrageurs ensured that equation (5.8) governed the. relationship between futures and spot prices of indices.  

# Index Arbitrage  

If $F_{0}>S_{0}e^{(r-q)T},$ profits can be made by buying the stocks underlying the index at the spot price (i.e., for immediate delivery) and shorting futures contracts. If $F_{0}<S_{0}e^{(r-q)T}$ profits can be made by doing the reverse-that is, shorting or selling the stocks underlying the index and taking a long position in futures contracts. These strategies are known as index arbitrage. When $F_{0}^{'}\overset{\cdot}{<}S_{0}e^{(r-q)T}$ index arbitrage is often done by a pension fund that owns an indexed portfolio of stocks. When $F_{0}>\stackrel{\leftarrow}{S}_{0}e^{(r-q)T}$ it might be done by a bank or a corporation holding short-term money market investments. For indices involving many stocks, index arbitrage is sometimes accomplished by trading a relatively small representative sample of stocks whose movements closely mirror those of the index. Usually index arbitrage is implemented through program trading. This involves using a computer system to generate the trades.  

Most of the time the activities of arbitrageurs ensure that equation (5.8) holds, but. occasionally arbitrage is impossible and the futures price does get out of line with the spot price (see Business Snapshot 5.4).  

# 5.1O FORWARD AND FUTURES CONTRACTS ON CURRENCIES  

We now move on to consider forward and futures foreign currency contracts. For the sake of definiteness we will assume that the domestic currency is the U.S. dollar (i.e., we take the perspective of a U.S. investor). The underlying asset is one unit of the foreign currency. We will therefore define the variable $S_{0}$ as the current spot price in U.S.. dollars of one unit of the foreign currency and $F_{0}$ as the forward or futures price in U.S.. dollars of one unit of the foreign currency. This is consistent with the way we have defined $S_{0}$ and $F_{0}$ for other assets underlying forward and futures contracts. However, as mentioned in Section 2.11, it does not necessarily correspond to the way spot and forward exchange rates are quoted. For major exchange rates other than the British pound, euro, Australian dollar, and New Zealand dollar, a spot or forward exchange rate is normally quoted as the number of units of the currency that are equivalent to one U.S. dollar..  

![](150b3ec3d5e296ca5d091603b386dafaf88e0c3167813b3efd425676cc5c300d.jpg)  
Figure 5.1 Two ways of converting 1,000 units of a foreign currency to dollars at time $T.$ Here, $S_{0}$ is spot exchange rate,. $F_{0}$ is forward exchange rate, and $r$ and $r_{f}$ are the dollar and foreign risk-free rates.  

A foreign currency has the property that the holder of the currency can earn interest. at the risk-free interest rate prevailing in the foreign country. For example, the holder can invest the currency in a foreign-denominated bond. We define $r_{f}$ as the value of the foreign risk-free interest rate when money is invested for time. $T.$ The variable $r$ is the domestic risk-free rate when money is invested for this period of time.  

The relationship between $F_{0}$ and $S_{0}$ is  

$$
F_{0}=S_{0}e^{(r-r_{f})T}
$$  

This is the well-known interest rate parity relationship from international finance. The reason it is true is illustrated in Figure 5.1. Suppose that an individual starts with 1,000 units of the foreign currency. There are two ways it can be converted to dollars at time $T.$ One is by investing it for. $T$ years at $r_{f}$ and entering into a forward contract to. sell the proceeds for dollars at time $T.$ This generates $1\small{,}00\bar{0}e^{r_{f}T}F_{0}$ dollars. The other is by exchanging the foreign currency for dollars in the spot market and investing the proceeds for $T$ years at rate $r$ . This generates $1{,}000S_{0}\bar{e}^{r T}$ dollars. In the absence of arbitrage opportunities, the two strategies must give the same result. Hence,  

$$
1,000e^{r_{f}T}F_{0}=1,000S_{0}e^{r T}
$$  

so that  

$$
F_{0}=S_{0}e^{(r-r_{f})T}
$$  

# Example 5.6  

Suppose that the 2-year interest rates in Australia and the United States are $3\%$ and $1\%$ , respectively, and the spot exchange rate is 0.7500 USD per AUD. From equation (5.9), the 2-year forward exchange rate should be  

$$
0.7500e^{(0.01-0.03)\times2}=0.7206
$$  

Suppose first that the 2-year forward exchange rate is less than this, say O.7000. An arbitrageur can:  

1. Borrow 1,000 AUD at $3\%$ per annum for 2 years, convert to 750 USD and invest the USD at $1\%$ (both rates are continuously compounded). 2. Enter into a forward contract to buy 1,061.84 AUD for $1,061.84\times0.7000=$ 743.29 USD in 2 years.  

The 750 USD that are invested at $1\%$ grow to $750e^{0.01\times2}=765.15\mathrm{~[~}$ JSD in 2 years. Of this, 743.29 USD are used to purchase 1,061.84 AUD under the terms of the forward contract. This is exactly enough to repay principal and interest on the 1,00 AUD that are borrowed $(1,\stackrel{.}{000}e^{0.0\stackrel{.}{3}\times2}=\stackrel{.}{1},\stackrel{.}{061}.84\$ ). The trategy therefore gives rise to a riskless profit of $765.15-743.29=21.87$ USD. (If this does not sound very exciting, consider following a similar strategy where you borrow 100 million AUD!)  

Suppose next that the 2-year forward rate is 0.7600 (greater than the 0.7206 value given by equation (5.9)). An arbitrageur can:  

1. Borrow 1,000 USD at $1\%$ per annum for 2 years, convert to. $1,000/0.7500=$ 1,333.33 AUD, and invest the AUD at $3\%$   
2. Enter into a forward contract to sell 1,415.79 AUD for $1,415.79\times0.76=$ 1,075.99 USD in 2 years.  

The 1,333.33 AUD that are invested at $3\%$ grow to $1,333.33e^{0.03\times2}=$ 1,415.79 AUD in 2 years. The forward contract has the effect of converting this to 1,075.99 USD. The amount needed to payoff the USD borrowings is $1,000e^{0.01\times2}=1,020.20$ USD. The strategy therefore gives rise to a riskless profit of $1,075.99-1,020.20=55.79$ USD.  

Table 5.4 shows currency futures quotes on May 21, 2020. The quotes are U.S. dollars per unit of the foreign currency. (In the case of the Japanese yen, the quote is U.S. dollars per 100 yen.) This is the usual quotation convention for futures contracts.. Equation (5.9) applies with $r$ equal to the U.S. risk-free rate and. $r_{f}$ equal to the foreign risk-free rate. The size of one contract is indicated at the top of each segment of the table..  

For all the currencies considered in the table, short-term interest rates were lower. than on the U.S. dollar. This corresponds to the. $r>r_{f}$ situation and explains why the settlement futures prices of these currencies increase with maturity. The CME launched futures on the cryptocurrency bitcoin in December 2017. The table shows.  

Table 5.4 Futures quotes for a selection of CME Group contracts on foreign currencies on May 21, 2020.   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Prior settlement</td><td>Last trade</td><td>Change</td><td>Volume</td></tr><tr><td colspan="6">Australian Dollar, USD per AUD, 100,000 AUD</td><td></td><td></td></tr><tr><td>June 2020</td><td>0.6597</td><td>0.6599</td><td>0.6549</td><td>0.6601</td><td>0.6567</td><td>-0.0034</td><td>92,674</td></tr><tr><td>Sept. 2020</td><td>0.6598</td><td>0.6598</td><td>0.6549</td><td>0.6602</td><td>0.6563</td><td>-0.0039</td><td>316</td></tr><tr><td colspan="6">British Pound, USD per GBP,62,500 GBP</td><td></td><td></td></tr><tr><td>June 2020</td><td>1.2235</td><td>1.2250</td><td>1.2186</td><td>1.2231</td><td>1.2219</td><td>-0.0012</td><td>69,106</td></tr><tr><td>Sept.2020</td><td>1.2217</td><td>1.2253</td><td>1.2191</td><td>1.2236</td><td>1.2246</td><td>+0.0010</td><td>388</td></tr><tr><td colspan="6">Canadian Dollar, USD per CAD, 100,000 CAD</td><td></td><td></td></tr><tr><td>June 2020</td><td>0.71930</td><td>0.71985</td><td>0.71575</td><td>0.71990</td><td>0.71705</td><td>-0.00285</td><td>51,980</td></tr><tr><td>Sept.2020</td><td>0.71915</td><td>0.71910</td><td>0.71665</td><td>0.72000</td><td>0.71720</td><td>-0.00280</td><td>562</td></tr><tr><td>Dec.2020</td><td>0.71790</td><td>0.71905</td><td>0.71680</td><td>0.72015</td><td>0.71680</td><td>-0.00335</td><td>164</td></tr><tr><td colspan="6">Euro, USD per EUR, 125,000 DEUR</td><td></td><td></td></tr><tr><td>June 2020</td><td>1.09840</td><td>1.10140</td><td>1.09415</td><td>1.09915</td><td>1.09510</td><td>-0.00405</td><td>136,609</td></tr><tr><td>Sept. 2020</td><td>1.10050</td><td>1.10320</td><td>1.09650</td><td>1.10120</td><td>1.09750</td><td>-0.00370</td><td>1,013</td></tr><tr><td>Dec.2020</td><td>1.10190</td><td>1.10550</td><td>1.09850</td><td>1.10350</td><td>1.10100</td><td>-0.00250</td><td>277</td></tr><tr><td colspan="6">Japanese Yen, USD per 100 yen, 12.5 million yen</td><td></td><td></td></tr><tr><td>June 2020</td><td>0.93015</td><td>0.93035</td><td>0.92745</td><td>0.93070</td><td>0.92970</td><td>-0.00100</td><td>61,018</td></tr><tr><td>Sept. 2020</td><td>0.93040</td><td>0.93125</td><td>0.92895</td><td>0.93200</td><td>0.93125</td><td>-0.00075</td><td>453</td></tr><tr><td colspan="6">Swiss Franc, USD per CHF, 125,000 CHF</td><td></td><td></td></tr><tr><td>June 2020</td><td>1.0371</td><td>1.0374</td><td>1.0303</td><td>1.0374</td><td>1.0304</td><td>-0.0070</td><td>18,155</td></tr><tr><td>Sept. 2020</td><td>1.0397</td><td>1.0397</td><td>1.0336</td><td>1.0402</td><td>1.0342</td><td>-0.0060</td><td>55</td></tr><tr><td colspan="6">Bitcoin, USD per BTC, 5 BTC</td><td></td><td></td></tr><tr><td>May 2020</td><td>9585</td><td>9610</td><td>8815</td><td>9570</td><td>9050</td><td>-520</td><td>8,738</td></tr><tr><td>June 2020</td><td>9655</td><td>9680</td><td>8900</td><td>9640</td><td>9165</td><td>-475</td><td>1,504</td></tr><tr><td>July 2020</td><td>9710</td><td>9710</td><td>8930</td><td>9685</td><td>9105</td><td>-580</td><td>130</td></tr></table></body></html>  

that, on May 21, 2020, one bitcoin was worth about $\$90000$ . Settlement of the contract is in cash on the last Friday of the month.  

# Example 5.7  

In Table 5.4, the September settlement price for the euro is about $0.2\%$ higher than the June settlement price, and the December settlement price is about. $0.2\%$ higher than the September settlement price. This indicates that the futures prices are increasing at about $4\times0.2=0.8\%$ per year with maturity. From equation (5.9) this is a rough estimate of the amount by which short-term euro interest rates were less than short-term U.S. interest rates in May 2020.  

# A Foreign Currency as an Asset Providing a Known Yield  

Equation (5.9) is identical to equation (5.3) with. $q$ replaced by $r_{f}.$ This is not a coincidence. A foreign currency can be regarded as an investment asset paying a known yield. The yield is the risk-free rate of interest in the foreign currency..  

To understand this, we note that the value of interest paid in a foreign currency depends on the value of the foreign currency. Suppose that the interest rate on British pounds is $5\%$ per annum. To a U.S. investor the British pound provides an income equal to $5\%$ of the value of the British pound per annum. In other words it is an asset that provides a yield of $5\%$ per annum.  
