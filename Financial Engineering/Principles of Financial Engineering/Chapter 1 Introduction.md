# INTRODUCTION  

# 1  

# CHAPTER OUTLINE  

# .1 A Unique Instrument..  

1.1.1 Buying a Default-Free Bond.. 3   
1.1.2 Buying Stocks . 5   
1.1.3 Buying a Defaultable Bond .. 7   
1.1.4 First Conclusions. 10   
.2 A Money Market Problem ... 10   
1.2.1 The Problem . 11   
1.2.2 Solution.. 11   
1.2.3 Some Implications.. 13   
.3 A Taxation Example... 13   
1.3.1 The Problem . 14   
1.3.1.1 Another strategy . 15   
1.3.2 Implications.. 16   
1.4 Some Caveats for What Is to Follow . 17   
.5 Trading Volatility . 18   
1.5.1 A Volatility Trade . 20   
1.5.2 Recap... . 21   
.6 Conclusions.. 22   
uggested Reading ... 22   
Exercises . 22  

Market professionals and investors take long and short positions on elementary assets such as stocks, default-free bonds, and debt instruments that carry a default risk. There is also a great deal of interest in trading currencies, commodities, and, recently, inflation, volatility, and correlation. Looking from the outside, an observer may think that these trades are done overwhelmingly by buying and selling the asset in question outright, for example, by paying “cash” and buying a US Treasury bond. This is wrong. It turns out that most of the financial objectives can be reached in a much more convenient fashion by going through a proper swap. There is an important logic behind this and we choose this as the first principle to illustrate in this introductory chapter.  

# 1.1 A UNIQUE INSTRUMENT  

First, we would like to introduce the equivalent of the integer zero, in finance. Remember the property of zero in algebra. Adding (subtracting) zero to any other real number leaves this number the same. There is a unique financial instrument that has the same property with respect to market and credit risk. Consider the cash flow diagram in Figure 1.1. Here, the time is continuous and the $t_{0}$ , $t_{1}$ , $t_{2}$ represent some specific dates. Initially we place ourselves at time $t_{0}$ . The following deal is struck with a bank. At time $t_{1}$ we borrow 100 US dollars (USD100), at the going interest rate of time $t_{1}$ , called the LIBOR and denoted by the symbol ${L_{t_{1}}}.^{1}$ We pay the interest and the principal back at time $t_{2}$ . The loan has no default risk and is for a period of $\delta$ units of time.2 Note that the contract is written at time $t_{0}$ , but starts at the future date $t_{1}$ . Hence this is an example of forward contracts. The actual value of $L_{t_{1}}$ will also be determined at the future date $t_{1}$ .  

Now, consider the time interval from $t_{0}$ to $t_{1}$ , expressed as $t\in\left[t_{0},\ t_{1}\right]$ . At any time during this interval, what can we say about the value of this forward contract initiated at $t_{0}$ ?  

It turns out that this contract will have a value identically equal to zero for all $t\in\left[t_{0},\ t_{1}\right]$ regardless of what happens in world financial markets. Perceptions of future interest rate movements may go from zero to infinity, but the value of the contract will still remain zero. In order to prove this assertion, we calculate the value of the contract at time $t_{0}$ . Actually, the value is obvious in one sense. Look at Figure 1.1. No cash changes hands at time $t_{0}$ . So, the value of the contract at time $t_{0}$ must be zero. This may be obvious but let us show it formally.  

To value the cash flows in Figure 1.1, we will calculate the time $t_{1}$ value of the cash flows that will be exchanged at time $t_{2}$ . This can be done by discounting them with the proper discount factor.  

![](4e50c6aee01eab590473ea46f25469a1554d91c66c4960d2319d1a415b49166d.jpg)  

# FIGURE 1.1  

A forward loan.  

The best discounting is done using the $L_{t_{1}}$ itself, although at time $t_{0}$ the value of this LIBOR rate is not known. Still, the time $t_{1}$ value of the future cash flows are  

$$
P V_{t_{1}}=\frac{L_{t_{1}}\delta100}{(1+L_{t_{1}}\delta)}+\frac{100}{(1+L_{t_{1}}\delta)}
$$  

At first sight, it seems we would need an estimate of the random variable $L_{t_{1}}$ to obtain a numerical answer from this formula. In fact, some market practitioners may suggest using the corresponding forward rate that is observed at time $t_{0}$ in lieu of $L_{t_{1}}$ , for example. But a closer look suggests a much better alternative. Collecting the terms in the numerator  

$$
P V_{t_{1}}=\frac{(1+L_{t_{1}}\delta)100}{(1+L_{t_{1}}\delta)}
$$  

the unknown terms cancel out and we obtain:  

$$
P V_{t_{1}}=100
$$  

This looks like a trivial result, but consider what it means. In order to calculate the value of the cash flows shown in Figure 1.1, we don’t need to know $L_{t_{1}}$ . Regardless of what happens to interest rate expectations and regardless of market volatility, the value of these cash flows, and hence the value of this contract, is always equal to zero for any $t\in\left[t_{0},\ t_{1}\right]$ . In other words, the price volatility of this instrument is identically equal to zero.  

This means that given any instrument at time $t$ , we can add (or subtract) the LIBOR loan to it, and the value of the original instrument will not change for all $t\in\left[t_{0},t_{1}\right]$ . We now apply this simple idea to a number of basic operations in financial markets.  

# 1.1.1 BUYING A DEFAULT-FREE BOND  

For many of the operations they need, market practitioners do not “buy” or “sell” bonds. There is a much more convenient way of doing business.  

The cash flows of buying a default-free coupon bond with par value 100 forward are shown in Figure 1.2. The coupon rate, set at time $t_{0}$ , is $r_{t_{0}}$ . The price is USD100, hence this is a par bond and the maturity date is $t_{2}$ . Note that this implies the following equality:  

$$
100=\frac{r_{t_{0}}\delta100}{(1+r_{t_{0}}\delta)}+\frac{100}{(1+r_{t_{0}}\delta)}
$$  

which is true, because at $t_{0}$ , the buyer is paying USD100 for the cash flows shown in Figure 1.2.  

Buying (selling) such a bond is inconvenient in many respects. First, one needs cash to do this. Practitioners call this funding, in case the bond is purchased.3 When the bond is sold short it will generate new cash and this must be managed.4 Hence, such outright sales and purchases require inconvenient and costly cash management.  

![](c239d0e39ab9e74f10695075176dbb2f321cc6b3fc1951ba2515ff22e1f53f78.jpg)  

# FIGURE 1.2  

Buying default-free bond.  

Second, the security in question may be a registered bond, instead of being a bearer bond, whereas the buyer may prefer to stay anonymous.  

Third, buying (selling) the bond will affect balance sheets, called books in the industry. Suppose the practitioner borrows USD100 and buys the bond. Both the asset and the liability sides of the balance sheet are now larger. This may have regulatory implications.5  

Finally, by securing the funding, the practitioner is getting a loan. Loans involve credit risk. The loan counterparty may want to factor a default risk premium into the interest rate.6  

Now consider the following operation. The bond in question is a contract. To this contract “add” the forward LIBOR loan that we discussed in the previous section. This is shown in Figure 1.3a. As we already proved, for all $t\in\left[t_{0},\ t_{1}\right]$ , the value of the LIBOR loan is identically equal to zero. Hence, this operation is similar to adding zero to a risky contract. This addition does not change the market risk characteristics of the original position in any way. On the other hand, as Figures 1.3a and b show, the resulting cash flows are significantly more convenient than the original bond.  

The cash flows require no upfront cash, they do not involve buying a registered security, and the balance sheet is not affected in any way.7 Yet, the cash flows shown in Figure 1.3 have exactly the same market risk characteristics as the original bond.  

Since the cash flows generated by the bond and the LIBOR loan in Figure 1.3 accomplish the same market risk objectives as the original bond transaction, then why not package them as a separate instrument and market them to clients under a different name? This is an interest rate swap (IRS). The party is paying a fixed rate and receiving a floating rate. The counterparty is doing the reverse.8 IRSs are among the most liquid instruments in financial markets.  

![](1d2b53f983d8cef124218399173c6d9accca123a0762476fae7c9da49cdc556e.jpg)  

# FIGURE 1.3  

Engineering a simple IRS.  

# 1.1.2 BUYING STOCKS  

Suppose now we change the basic instrument. A market practitioner would like to buy a stock $S_{t}$ at time $t_{0}$ with a $t_{1}$ delivery date. We assume that the stock does not pay dividends. Hence, this is, again, a forward purchase. The stock position will be liquidated at time $t_{2}$ . Also, assume that the time $t_{0}$ perception of the stock market gains or losses is such that the markets are demanding a price  

$$
S_{t_{0}}=100
$$  

for this stock as of time $t_{0}$ . This situation is shown in Figure 1.4a, where $\Delta S_{t_{2}}$ is the unknown stock price appreciation or depreciation to be observed at time $t_{2}$ . Note that the original price being 100, the time $t_{2}$ stock price can be written as  

$$
\begin{array}{c}{S_{t_{2}}=S_{t_{1}}+\Delta S_{t_{2}}}\\ {=100+\Delta S_{t_{2}}}\end{array}
$$  

Hence the cash flows shown in Figure 1.4a.  

![](072b23a1a6e3e7a600d4a32ba46a66ef12aa75a96e5ff709f31d3234f895cef8.jpg)  

# FIGURE 1.4  

Engineering an equity or commodity swap.  

It turns out that whatever the purpose of buying such a stock was, this outright purchase suffers from even more inconveniences than in the case of the bond. Just as in the case of the Treasury bond, the purchase requires cash, is a registered transaction with significant tax implications, and immediately affects the balance sheets, which have regulatory implications. A fourth inconvenience is a very simple one. The purchaser may not be allowed to own such a stock.9 Last, but not least, there are regulations preventing highly leveraged stock purchases.  

Now, apply the same technique to this transaction. Add the LIBOR loan to the cash flows shown in Figure 1.4a and obtain the cash flows in Figure 1.4b. As before, the market risk characteristics of the portfolio are identical to those of the original stock. The resulting cash flows can be marketed jointly as a separate instrument. This is an equity swap and it has none of the inconveniences of the outright purchase. But, because we added a zero to the original cash flows, it has exactly the same market risk characteristics as a stock. In an equity swap, the party is receiving any stock market gains and paying a floating LIBOR rate plus any stock market losses.10  

Note that if $S_{t}$ denoted the price of any commodity, such as oil, then the same logic would give us a commodity swap.11  

# 1.1.3 BUYING A DEFAULTABLE BOND  

Consider the bond in Figure 1.1 again, but this time assume that at time $t_{2}$ the issuer can default. The bond pays the coupon $c_{t_{0}}$ with  

$$
r_{t_{0}}<c_{t_{0}}
$$  

where $r_{t_{0}}$ is a risk-free rate. The bond sells at par value, USD100 at time $t_{0}$ . The interest and principal are received at time $t_{2}\ i f$ there is no default. If the bond issuer defaults the investor receives nothing. This means that we are working with a recovery rate of zero. Figure 1.5a shows this characterization.  

This transaction has, again, several inconveniences. In fact, all the inconveniences mentioned there are still valid. But, in addition, the defaultable bond may not be very liquid.12 Also, because it is defaultable, the regulatory agencies will certainly impose a capital charge on these bonds if they are carried on the balance sheet.  

A much more convenient instrument is obtained by adding the “zero” from Figure 1.1 to the defaultable bond and forming a new portfolio. Figures 1.5a and b visualized the cash flows of a defaultable bond together with those of a forward LIBOR loan. The combination of the defaultable bond and the LIBOR loan is show in Figure 1.5c, in which we assume $\delta=1$ . But we can go one step further in this case. Assume that at time $t_{0}$ there is an IRS, as shown in Figure 1.3, trading actively in the market. Then we can subtract this IRS from Figure 1.5c and obtain a much clearer picture of the final cash flows. This operation is shown in Figure 1.6. In fact, this last step eliminates the unknown future LIBOR rates $L_{t_{i}}$ and replaces them with the known swap rate $s_{t_{0}}$ .  

The resulting cash flows don’t have any of the inconveniences suffered by the defaultable bond purchase. Again, they can be packaged and sold separately as a new instrument. Letting $s_{t_{0}}$ denote the rate on the corresponding IRS, the instrument requires receipts of a known and constant premium $\mathrm{Sp}_{t_{0}}=c_{t_{0}}-s_{t_{0}}$ periodically. Against this a floating (contingent) cash flow is paid. In case of default, the counterparty is compensated by USD100. This is similar to buying and selling default insurance. The instrument is called a credit default swap (CDS). Since their initiation during the  

![](0cb1560da1b2acecfad43fd5a6289cea6ac253157afb798641d7f3d5c8d48e06.jpg)  

# FIGURE 1.5  

A risky bond and a LIBOR loan.  

![](a3a3e306396ea3581e561292f75f957ac71823832aab99a3e01840e79664fce8.jpg)  

# FIGURE 1.6  

A credit default swap.  

1990s CDSs have become very liquid instruments and completely changed the trading and hedging of credit risk. The insurance premium, called the $C D S$ spread, $\mathrm{cds}_{t_{0}}$ , is given by  

$$
\mathrm{cds}_{t_{0}}=\mathrm{Sp}_{t_{0}}=c_{t_{0}}-s_{t_{0}}
$$  

This rate is positive since $c_{t_{0}}$ should incorporate a default risk premium, which the default-free bond does not have.13  

# 1.1.4 FIRST CONCLUSIONS  

This section discussed examples of the first method of financial engineering. Switching from cash transactions to trading various swaps has many advantages. By combining an instrument with a forward LIBOR loan contract in a specific way, and then selling the resulting cash flows as separate swap contracts, the financial engineer has succeeded in accomplishing the same objectives much more efficiently and conveniently. The resulting swaps are likely to be more efficient, cost effective, and liquid than the underlying instruments. They also have better regulatory and tax implications.  

Clearly, one can sell as well as buy such swaps. Also, one can reverse engineer the bond, equity, and the commodities by combining the swap with the LIBOR deposit. Chapter 4 will generalize this swap engineering. In the next section, we discuss another major financial engineering principle: the way one can build synthetic instruments.  

We now introduce some simple financial engineering strategies. We consider two examples that require finding financial engineering solutions to a daily problem. In each case, solving the problem under consideration requires creating appropriate synthetics. In doing so, legal, institutional, and regulatory issues need to be considered.  

The nature of the examples themselves is secondary here. Our main purpose is to bring to the forefront the way of solving problems using financial securities and their derivatives. The chapter does not go into the details of the terminology or of the tools that are used. In fact, some readers may not even be able to follow the discussion fully. There is no harm in this since these will be explained in later chapters.  

# 1.2 A MONEY MARKET PROBLEM  

Consider a Japanese bank in search of a 3-month money market loan. The bank would like to borrow USD in Euromarkets and then on-lend them to its customers. This interbank loan will lead to cash flows as shown in Figure 1.7. From the borrower’s angle, USD100 is received at time $t_{0}.$ , and then it is paid back with interest 3 months later at time $t_{0}+\delta$ . The interest rate is denoted by the symbol $L_{t_{0}}$ and is determined at time $t_{0}$ . The tenor of the loan is 3 months. Therefore,  

$$
\delta=\frac{1}{4}
$$  

and the interest paid becomes $L_{t_{0}}(1/4)$ . The possibility of default is assumed away.14  

![](3fdba7e688a4ccc0e72b37ead1ba0670fb3cc467bfbc6a68e4e166e7fa691757.jpg)  

# FIGURE 1.7  

A USD loan.  

The money market loan displayed in Figure 1.7 is a fairly liquid instrument. In fact, banks purchase such “funds” in the wholesale interbank markets, and then on-lend them to their customers at a slightly higher rate of interest.  

# 1.2.1 THE PROBLEM  

Now, suppose the above-mentioned Japanese bank finds out that this loan is not available due to the lack of appropriate credit lines. The counterparties are unwilling to extend the USD funds. The question then is: Are there other ways in which such dollar funding can be secured?  

The answer is yes. In fact, the bank can use foreign currency markets judiciously to construct exactly the same cash flow diagram as in Figure 1.7 and thus create a synthetic money market loan. The first cash flow is negative and is placed below the time axis because it is a payment by the investor. The subsequent sale of the asset, on the other hand, is a receipt, and hence is represented by a positive cash flow placed above the time axis. The investor may have to pay significant taxes on these capital gains. A relevant question is then: Is it possible to use a strategy that postpones the investment gain to the next tax year? This may seem an innocuous statement, but note that using currency markets and their derivatives will involve a completely different set of financial contracts, players, and institutional setup than the money markets. Yet, the result will be cash flows identical to those in Figure 1.7.  

# 1.2.2 SOLUTION  

To see how a synthetic loan can be created, consider the following series of operations:  

1. The Japanese bank first borrows local funds in yen in the onshore Japanese money markets. This is shown in Figure 1.8a. The bank receives yen at time $t_{0}$ and will pay yen interest rate $L_{t_{0}}^{Y}\delta$ at time $t_{0}+\delta$ .   
2. Next, the bank sells these yen in the spot market at the current exchange rate $\boldsymbol{e}_{t_{0}}$ to secure USD100. This spot operation is shown in Figure 1.8b.   
3. Finally, the bank must eliminate the currency mismatch introduced by these operations. In orde to do this, the Japanese bank buys $100(1+L_{t_{0}}^{Y}\delta)f_{t_{0}}$ yen at the known forward exchange rate $f_{t_{0}}$ ,  

![](b0d746872262c46f8e4dd10feeae3649163271adfe40ecc7859c672b517ebe98.jpg)  

# FIGURE 1.8  

A synthetic USD loan.  

in the forward currency markets. This is the cash flow shown in Figure 1.8c. Here, there is no exchange of funds at time $t_{0}$ . Instead, forward dollars will be exchanged for forward yen at $t_{0}+\delta$ .  

Now comes the critical point. In Figure 1.8, add vertically all the cash flows generated by these operations. The yen cash flows will cancel out at time $t_{0}$ because they are of equal size and different sign. The time $t_{0}+\delta$ yen cash flows will also cancel out because that is how the size of the forward contract is selected. The bank purchases just enough forward yen to pay back the local yen loan and the associated interest. The cash flows that are left are shown in Figure 1.8d, and these are exactly the same cash flows as in Figure 1.7. Thus, the three operations have created a synthetic USD loan. The existence of the FX-forward played a crucial role in this synthetic.  

# 1.2.3 SOME IMPLICATIONS  

There are some subtle but important differences between the actual loan and the synthetic. First, note that from the point of view of Euromarket banks, lending to Japanese banks involves a principal of USD100, and this creates a credit risk. In case of default, the 100 dollars lent may not be repaid. Against this risk, some capital has to be put aside. Depending on the state of money markets and depending on counterparty credit risks, money center banks may adjust their credit lines toward such customers.  

On the other hand, in the case of the synthetic dollar loan, the international bank’s exposure to the Japanese bank is in the forward currency market only. Here, there is no principal involved. If the Japanese bank defaults, the burden of default will be on the domestic banking system in Japan. There is a risk due to the forward currency operation, called counterparty risk and since the Global Financial Crisis (GFC) this has received much more attention since it can be economically important. Thus, the Japanese bank may end up getting the desired funds somewhat easier if a synthetic is used.  

There is a second interesting point to the issue of credit risk mentioned earlier. The original money market loan was a Euromarket instrument. Banking operations in Euromarkets are considered offshore operations, taking place essentially outside the jurisdiction of national banking authorities. The local yen loan, on the other hand, would be subject to supervision by Japanese authorities, obtained in the onshore market. In case of default, there may be some help from the Japanese Central Bank, unlike a Eurodollar loan where a default may have more severe implications on the lending bank.15  

The third point has to do with pricing. If the actual and synthetic loans have identical cash flows, their values should also be the same excluding credit risk issues. If there is a value discrepancy the markets will simultaneously sell the expensive one, and buy the cheaper one, realizing a windfall gain. This means that synthetics can also be used in pricing the original instrument.16  

Fourth, note that the money market loan and the synthetic can in fact be each other’s hedge. Finally, in spite of the identical nature of the involved cash flows, the two ways of securing dollar funding happen in completely different markets and involve very different financial contracts. This means that legal and regulatory differences may be significant.  

# 1.3 A TAXATION EXAMPLE  

Now consider a totally different problem. We create synthetic instruments to restructure taxable gains. The legal environment surrounding taxation is a complex and ever-changing phenomenon; therefore, this example should be read only from a financial engineering perspective and not as a tax strategy. Yet the example illustrates the close connection between what a financial engineer does and the legal and regulatory issues that surround this activity.  

# 1.3.1 THE PROBLEM  

In taxation of financial gains and losses, there is a concept known as a wash-sale. Suppose that during the year 2014, an investor realizes some financial gains. Normally, these gains are taxable that year. But a variety of financial strategies can possibly be used to postpone taxation to the year after. To prevent such strategies, national tax authorities have a set of rules known as wash-sale and straddle rules. It is important that professionals working for national tax authorities in various countries understand these strategies well and have a good knowledge of financial engineering. Otherwise some players may rearrange their portfolios, and this may lead to significant losses in tax revenues. From our perspective, we are concerned with the methodology of constructing synthetic instruments.  

Suppose that in September 2014, an investor bought an asset at a price $S_{0}=\$100$ . In December 2014, this asset is sold at $S_{1}=\$150$ . Thus, the investor has realized a capital gain of $\$50$ . These cash flows are shown in Figure 1.9.  

One may propose the following solution. This investor is probably holding assets other than the $S_{t}$ mentioned earlier. After all, the right way to invest is to have diversifiable portfolios. It is also reasonable to assume that if there were appreciating assets such as $S_{t},$ , there were also assets that lost value during the same period. Denote the price of such an asset by $Z_{t}$ . Let the purchase price be $Z_{0}$ . If there were no wash-sale rules, the following strategy could be put together to postpone year 2014 taxes.  

Sell the $Z\cdot$ -asset on December 2014, at a price $Z_{1}$ , $Z_{1}<Z_{0}$ , and, the next day, buy the same $Z_{t}$ at a similar price. The sale will result in a loss equal to  

$$
Z_{1}-Z_{0}<0
$$  

The subsequent purchase puts this asset back into the portfolio so that the diversified portfolio can be maintained. This way, the losses in $Z_{t}$ are recognized and will cancel out some or all of the capital gains earned from $S_{t}.$ . There may be several problems with this strategy, but one is fatal. Tax authorities would call this a wash-sale (i.e., a sale that is being intentionally used to “wash” the 2014 capital gains) and would disallow the deductions.17  

![](e076938103d7ddd4f49b313978be8d1a0f35c99f1fd23c3303cdaead6281443b.jpg)  

# FIGURE 1.9  

An investment liquidated on December 2014.  

# 1.3.1.1 Another strategy  

Investors can find a way to sell the $Z$ -asset without having to sell it in the usual way. This can be done by first creating a synthetic $Z$ -asset and then realizing the implicit capital losses using this synthetic, instead of the $Z$ -asset held in the portfolio.  

Suppose the investor originally purchased the $Z.$ -asset at a price $Z_{0}=\$100$ and that asset is currently trading at $Z_{1}=\$50$ , with a paper loss of $\$50$ . The investor would like to recognize the loss without directly selling this asset. At the same time, the investor would like to retain the original position in the $Z$ -asset in order to maintain a well-balanced portfolio. How can the loss be realized while maintaining the $Z$ -position and without selling the $Z_{t}^{\cdot}$ ?  

The idea is to construct a proper synthetic. Consider the following sequence of operations:  

Buy another $Z$ -asset at price $Z_{1}=\$50$ on November 26, 2014.   
Sell an at-the-money call on $Z$ with expiration date December 30, 2014.   
Buy an at-the-money put on $Z$ with the same expiration.  

The specifics of call and put options will be discussed in later chapters. For those readers with no background in financial instruments we can add a few words. Briefly, options are instruments that give the purchaser a right. In the case of the call option, it is the right to purchase the underlying asset (here the Z-asset) at a prespecified price (here $\$50$ ). The put option is the opposite. It is the right to sell the asset at a prespecified price (here $\$50$ ). When one sells options, on the other hand, the seller has the obligation to deliver or accept delivery of the underlying at a prespecified price.  

For our purposes, what is important is that short call and long put are two securities whose expiration payoff, when added, will give the synthetic short position shown in Figure 1.10. By selling the call, the investor has the obligation to deliver the $Z$ -asset at a price of $\$50$ if the call holder demands it. The put, on the other hand, gives the investor the right to sell the $Z$ -asset at $\$50$ if he or she chooses to do so.  

The important point here is this: When the short call and the long put positions shown in Figure 1.10 are added together, the result will be equivalent to a short position on stock $Z_{t}$ . In fact, the investor has created a synthetic short position using options.  

Now consider what happens as time passes. If $Z_{t}$ appreciates by December 30, the call will be exercised. This is shown in Figure 1.11a. The call position will lose money, since the investor has to deliver, at a loss, the original $Z$ -stock that cost $\$100$ . If, on the other hand, the $Z_{t}$ decreases, then the put position will enable the investor to sell the original $Z$ -stock at $\$50$ . This time the call will expire worthless.18 This situation is shown in Figure 1.11b. Again, there will be a loss of $\$50$ . Thus, no matter what happens to the price $Z_{t}.$ , either the investor will deliver the original $Z$ -asset purchased at a price $\$100$ , or the put will be exercised and the investor will sell the original $Z$ -asset at $\$50$ . Thus, one way or another, the investor is using the original asset purchased at $\$100$ to close an option position at a loss. This means he or she will lose $\$50$ while keeping the same $Z$ -position, since the second Z, purchased at $\$50$ , will still be in the portfolio.  

The timing issue is important here. For example, according to US tax legislation, wash-sale rules will apply if the investor has acquired or sold a substantially identical property within a  

![](0196a1346d63e613bcf15f98f27d9d9dc3f8666272e1f1c50acdfbbdbce6ad6c.jpg)  

# FIGURE 1.10  

Two positions that cancel each other.  

31-day period. According to the strategy outlined here, the second $Z$ is purchased on November 26, while the options expire on December 30. Thus, there are more than 31 days between the two operations.19  

# 1.3.2 IMPLICATIONS  

There are at least three interesting points to our discussion. First, the strategy offered to the investor was risk-free and had zero cost aside from commissions and fees. Whatever happens to the new long position in the $Z$ -asset, it will be canceled by the synthetic short position. This situation is shown in the lower half of Figure 1.10. As this graph shows, the proposed solution has no market risk, but may have counterparty, or operational risks. The second point is that, once again, we have created a synthetic, and then used it in providing a solution to our problem. Finally, the example  

![](a458ea7969a8bc594461de661f9cee7cad881c64d9968dc4f62aa5c2084d062e.jpg)  

# FIGURE 1.11  

The strategy with the $Z$ initially at 50. Two ways to realize loss.  

displays the crucial role legal and regulatory frameworks can play in devising financial strategies. Although this book does not deal with these issues, it is important to understand the crucial role they play at almost every level of financial engineering.  

# 1.4 SOME CAVEATS FOR WHAT IS TO FOLLOW  

A newcomer to financial engineering usually follows instincts that are harmful for good understanding of the basic methodologies in the field. Hence, before we start, we need to lay out some basic rules of the game that should be remembered throughout the book.  

1. This book is written from a market practitioner’s point of view. Investors, pension funds, insurance companies, and governments are clients, and for us they are always on the other sid of the deal. In other words, we look at financial engineering from a trader’s, broker’s, and dealer’s angle. The approach is from the manufacturer’s perspective rather than the viewpoint of the user of the financial services. This premise is crucial in understanding some of the logic discussed in later chapters.  

2. We adopt the convention that there are two prices for every instrument unless stated otherwise. The agents involved in the deals often quote two-way prices. In economic theory, economic agents face the law of one price. The same good or asset cannot have two prices. If it did, we would then buy at the cheaper price and sell at the higher price.  

Yet for a market maker, there are two prices: one price at which the market participant is willing to buy something from you, and another one at which the market participant is willing to sell the same thing to you. Clearly, the two cannot be the same. An automobile dealer will buy a used car at a low price in order to sell it at a higher price. That is how the dealer makes money. The same is true for a market practitioner. A swap dealer will be willing to buy swaps at a low price in order to sell them at a higher price later.20 In the meantime, the instrument, just like the used car sold to a car dealer, is kept in inventories.  

3. It is important to realize that a financial market participant is not an investor and never has “money.” He or she has to secure funding for any purchase and has to place the cash generated by any sale. In this book, almost no financial market operation begins with a pile of cash. The only “cash” is in the investor’s hands, which in this book is on the other side of the transaction.  

It is for this reason that market practitioners prefer to work with instruments that have zero-value at the time of initiation. Such instruments would not require funding and are more practical to use.21 They also are likely to have more liquidity.  

4. The role played by regulators, professional organizations, and the legal profession is much more important for a market professional than for an investor. Although it is far beyond the scope of this book, many financial engineering strategies have been devised for the sole purpose of dealing with them.  

Remembering these premises will greatly facilitate the understanding of financial engineering.  

# 1.5 TRADING VOLATILITY  

Practitioners or investors can take positions on expectations concerning the price of an asset. Volatility trading involves positions taken on the volatility of the price. This is an attractive idea, but how does one buy or sell volatility? Answering this question will lead to a third basic methodology in financial engineering. This idea is a bit more complicated, so the argument here will only be an introduction. Chapter 9 will present a more detailed treatment of the methodology.  

In order to discuss volatility trading, we need to introduce the notion of convexity gains. We start with a forward contract. Let us stay within the framework of the previous section and  

![](6577a8cdf1e60455b8fda667083394f33a96c6b893280ae5c595a746e9961bb3.jpg)  

# FIGURE 1.12  

Payoff function of long USD/YEN forward contract.  

assume that $F_{t_{0}}$ is the forward dollar yen exchange rate.22 Suppose at time $t_{0}$ we take a long position in USD as shown in Figure 1.12. The upward sloping line is the so-called payoff function.23 For example, if at time $t_{0}+\Delta$ the forward price becomes $F_{t_{0}+\Delta}$ , we can close the position with a gain:  

$$
\mathrm{Gain}=F_{t_{0}+\Delta}-F_{t_{0}}
$$  

It is important, for the ensuing discussion, that this payoff function be a straight line with a constant slope.  

Now, suppose there exists another instrument whose payoff depends on the $F_{T}$ . But this time the dependence is nonlinear24 or convex as shown in Figure 1.13 by the convex curve $C(F_{t})$ . It is important that the curve be smooth, and that the derivative  

$$
\frac{\partial C(F_{t})}{\partial F_{t}}
$$  

exist at all points.  

Finally, suppose this payoff function has the additional property that as time passes the function changes shape. In fact as expiration time $T$ approaches, the curve becomes a (piecewise) straight line just like the forward contract payoff. This is shown in Figure 1.14.  

![](e0b6444c8e18e8b0fe14b04d086cbb4b64e75eeea241ceab7c70a53c04a7cd30.jpg)  

# FIGURE 1.13  

Payoff function of a nonlinear (convex) instrument.  

![](c28e5fa197b1e9f97f3c430c3d1fb57a40fef12a93495c9103af4c767bb9acc5.jpg)  

# FIGURE 1.14  

Payoff function before and at expiration.  

# 1.5.1 A VOLATILITY TRADE  

Volatility trades depend on the simultaneous existence of two instruments, one whose value moves linearly as the underlying risk changes, while the other’s value moves according to a convex curve.  

First, suppose $\{F_{t_{1}},\ldots.F_{t_{n}}\}$ are the forward prices observed successively at times $t<t_{1}$ , . $t_{n}<T$ as shown in Figure 1.13. Note that these values are selected so that they oscillate around $F_{t_{0}}$ .  

Second, note that at every value of $F_{t_{i}}$ we can get an approximation of the curve $C(F_{t})$ using the tangent at that point as shown in Figure 1.13. Clearly, if we know the function $C(.)$ , we can then calculate the slope of these tangents. Let the slope of these tangents be denoted by $D_{i}$ .  

The third step is the crucial one. We form a portfolio that will eliminate the risk of directional movements in exchange rates. We first buy one unit of the $C(F_{t})$ at time $t_{0}$ . Note that we do need cash for doing this since the value at $t_{0}$ is nonzero.  

$$
0<C(F_{t_{0}})
$$  

Simultaneously, we sell $D_{0}$ units of the forward contract $F_{t_{0}}$ . Note that the forward sale does not require any upfront cash at time $t_{0}$ .  

Finally, as time passes, we recalculate the tangent $D_{i}$ of that period and adjust the forward sale accordingly. For example, if the slope has increased, sell $D_{i}-D_{i-1}$ units more of the forward  

![](26bc9cafe8452621a96c5fa5a3910f638a0efe0f893eeee8446416c028be649c.jpg)  
Ignore the movement of the curve, assumed small. Note that as the curve moves down slope changes  

# FIGURE 1.15  

Oscillations in the forward price and rebalancing the hedge.  

contracts. If the slope has decreased cover $D_{i}-D_{i-1}$ units of the forwards.25 As $F_{t_{i}}$ oscillates continue with this rebalancing.  

We can now calculate the net cash flows associated with this strategy. Consider the oscillations in Figures 1.13 and 1.15,  

$$
(F_{t_{i-1}}=F^{0}){\rightarrow}(F_{t_{i}}=F^{1}){\rightarrow}(F_{t_{i+1}}=F^{0})
$$  

with $F^{0}<F^{1}$ . In this setting if the trader follows the algorithm described above, then at every oscillation, the trader will  

1. First sell $D_{i}-D_{i-1}$ additional units at the price $F^{1}$ .   
2. Then, buy the same number of units at the price of $F^{0}$ .  

For each oscillation, the cash flows can be calculated as  

$$
{\mathrm{Gain}}=(D_{1}-D_{0})(F^{1}-F^{0})
$$  

Since $F^{0}<F^{1}$ and $D^{0}<D^{1}$ , this gain is positive as summarized in Figure 1.15. By hedging the original position in $C(.)$ and periodically rebalancing the hedge, the trader has in fact succeeded to monetize the oscillations of $F_{t_{i}}$ .  

# 1.5.2 RECAP  

Look at what the trader has accomplished. By holding the convex instrument and then trading the linear instrument against it, the trader realized positive gains. These gains are bigger, the bigger the oscillations. Also they are bigger, the bigger the changes in the slope terms $D_{i}.$ In fact, the trader gains whether the price goes down or up. The gains are proportional to the realized volatility.  

Clearly, this dynamic strategy has resulted in extracting cash from the volatility of the underlying forward rate $F_{t}.$ It turns out that one can package such expected volatility gains and sell them to clients. This leads to volatility trading. It is accomplished by using options and, lately, through volatility swaps.26  

# 1.6 CONCLUSIONS  

This chapter uses some examples in order to display the use of synthetics (or replicating portfolios as they are called in formal models). The main objective of this book is to discuss methods that use financial markets, instruments, and financial engineering strategies in solving practical problems concerning pricing, hedging, risk management, balance sheet management, and product structuring. The book does not discuss the details of financial instruments, although for completion, some basics are reviewed when necessary. The book deals even less with issues of corporate finance. We assume some familiarity with financial instruments, markets, and rudimentary corporate finance concepts.  

Finally, the reader must remember that regulation, taxation, and even the markets themselves are “dynamic” objects that change constantly. Actual application of the techniques must update the parameters mentioned in this book.  

# SUGGESTED READING  

There are excellent sources for studying financial instruments, their pricing, and the associated modeling. An excellent source for instruments and markets is Hull (2014). For corporate finance, Brealey and Myers (2013) and Ross et al. (2012) are two well-known references. Bodie et al. (2014) is recommended as background material on investments. Wilmott (2006) is a comprehensive and important source. Duffie (2001) provides the foundation for solid asset pricing theory.  

# EXERCISES  

1. Which two instruments can be used to replicate the payoffs of an IRS?   
2. What are Eurodollars?   
3. Which two instruments can be used to create the payoffs of an equity swap?   
4. How can a synthetic foreign currency loan be engineered?  

You are given the Reuters news item below. Read it carefully. Then answer the following questions.  

1. Show how Japanese banks were able to create the dollar-denominated loans synthetically using cash flow diagrams.   
2. How does this behavior of Japanese banks affect the balance sheet of the Western counterparties?   
3. What are nostro accounts? Why are they needed? Why are the Western banks not willing to hold the yens in their nostro accounts?   
4. What do the Western banks gain if they do that?   
5. Show, using an “appropriate” formula, that the negative interest rates can be more than compensated by the extra points on the forward rates. (Use the decompositions given in the text.) NEW YORK, (Reuters) - Japanese banks are increasingly borrowing dollar funds via the foreign exchange markets   
rather than in the traditional international loan markets, pushing some Japanese interest rates into negative territory,   
according to bank officials. The rush to fund in the currency markets has helped create the recent anomaly in short-term interest rates. For the   
first time in years, yields on Japanese Treasury bills and some bank deposits are negative, in effect requiring the lender   
of yen to pay the borrower. Japanese financial institutions are having difficulty getting loans denominated in U.S. dollars, experts said. They   
said international banks are weary of expanding credit lines to Japanese banks, whose balance sheets remain burdened   
by bad loans. “The Japanese banks are still having trouble funding in dollars,” said a fixed-income strategist at Merrill Lynch & Co. So Japan’s banks are turning to foreign exchange transactions to obtain dollars. The predominant mechanism for   
borrowing dollars is through a trade combining a spot and forward in dollar/yen. Japanese banks typically borrow in yen, which they have no problem getting. With a three-month loan, for instance,   
the Japanese bank would then sell the yen for dollars in the spot market to, say, a British or American bank. The   
Japanese bank simultaneously enters into a three-month forward selling the dollars and getting back yen to pay off the   
yen loan at the stipulated forward rate. In effect, the Japanese bank has obtained a three-month dollar loan. Under normal circumstances, the dealer providing the transaction to the Japanese bank should not make anything   
but the bid-offer spread. But so great has been the demand from Japanese banks that dealers are earning anywhere from seven to 10 basis   
points from the spot-forward trade. The problem is that the transaction saddles British and American banks with yen for three months. Normally,   
international banks would place the yen in deposits with Japanese banks and earn the three-month interest rate. But most Western banks are already bumping against credit limits for their banks on exposure to troubled Japanese   
banks. Holding the yen on their own books in what are called NOSTRO accounts requires holding capital against them   
for regulatory purposes. So Western banks have been dumping yen holdings at any cost—to the point of driving interest rates on Japanese   
Treasury bills into negative terms. Also, large Western banks such as Barclays Plc and J.P. Morgan are offering   
negative interest rates on yen deposits—in effect saying no to new yen-denominated deposits. Western bankers said they can afford to pay up to hold Japanese Treasury bills—in effect earning negative yield—   
because their earnings from the spot-forward trade more than compensate them for their losses on holding Japanese   
paper with negative yield. Japanese six-month T-bills offer a negative yield of around 0.002 percent, dealers said. Among banks offering a   
negative interest rate on yen deposits was Barclays Bank Plc, which offered a negative 0.02 percent interest rate on a   
three-month deposit. The Bank of Japan, the central bank, has been encouraging government-lending institutions to make dollar loans to  

Japanese corporations to overcome the problem, said [a market professional]. (Reuters, November 9, 1998).  

This page intentionally left blank  