# 16.9 PRELIMINARIES  

The volatility smile has important implications for trading, hedging, and pricing financial instru-. ments. To illustrate how far things have come in this area, we look at a position taken with the objective of benefiting from abnormal conditions regarding the volatility smile..  

We can trade stocks, bonds, or, as we have seen before, the slope of the yield curve. We may,. for example, expect that the long-term yields will decline relative to the short-term yields. This is. called a flattening of the yield curve and it invites curve-flattening strategies that (short) sell short maturities, and buy long maturities. This can be done using cash instruments (i.e., bonds) or swaps..  

In any case, such trades have become routine in financial markets. A more recent relative value trade relates to the volatility smile. Consider the following episode..  

# EXAMPLE  

Over the last month, European equity options traders have seen interest by contrarian investors, namely hedge funds, in buying at-the-money volatility and selling out-of-the-money volatility to take advantage of a skew in volatility levels in certain markets..  

... the skew trade involves an investor buying at-the-money vol and selling out-of-the-money vol. Due to supply/demand pressures, the level of out-of-the-money vol sometimes rises higher than normal. In other. words, the spread between out, and at-the-money volatility increases, causing a so-called skew. Investors put on the trade in anticipation of the skew dissipating. [A trader] explained that along with the bull run of US and European equity markets has come a sense of unease among some investors regarding a downturn. Many have thus sought protection via over-the-counter. put contracts. Because out-of-the-money puts are usually cheaper than at-the-money puts, many investors have. opted for the former. The heavy volume has caused out-of-the-money vol levels to rise. Many investors want crash protection but today puts are too expensive. So, instead of buying today at 100 they buy puts at 80.  

(Based on an article in Derivatives Week (now part of GlobalCapital)  

According to this example, equity investors that had heavily invested during the "stock market bubble' of the 1990s were looking for crash protection. They were long equities and would have. suffered significant losses if markets crashed. Instead of selling the stocks that they owned, they.  

bought put options. With a put an investor has the right to sell the underlying stocks at a predetermined price, say, $K.$ If market price declines below $K$ , the investor would have some protection.  

According to the reading, the large number of investors who were willing to buy puts increased, first, the at-the-money (ATM) volatility.' The ATM options became expensive. To lower the cost of insurance sought, investors instead bought options that were, according to the reading, $20\%$ out-of-the-money. These options were cheaper. But as more and more investors bought them, the out-of-the-money volatility started to increase relative to ATM volatility of the same option series. This led to an abnormally steep skew.  

The reading suggests that this "abnormal' skew may have attracted some hedge funds who expected the abnormality to disappear in the longer run. According to one theory, these funds sold out-of-the-money volatility and bought ATM volatility. This position will make money if the skew flattens and out-of-the-money volatility decreases relative to the ATM volatility.' As this example shows, the skew, or smile, should be considered as an integral part of financial markets activity. However, as we see in this section, its existence causes several complications and difficulties in financial modeling and in risk management.  

# 16.1O A FIRST LOOK AT THE SMILE  

The volatility smile can be a confusing notion, and we need to discuss some preliminary ideas before getting into the mechanics of pricing and market applications. It is well known that the. Black-Scholes assumptions are not very realistic. And yet, the Black-Scholes formula is routinely used by options traders, although these traders know better than anybody else that the assumptions behind the model are problematic. One of the major Black-Scholes assumptions, for example, is that volatility is constant during the life of an option. How can a trader still use the Black-Scholes formula if the realized volatility is known to fluctuate significantly during the life of the option?  

If this Black-Scholes assumption is violated, wouldn't the price given by the Black-Scholes. formula be "wrong," and, hence, the volatility implied by the formula be erroneous? This question. needs to be carefully considered. In the end, we will see that there are really no inconsistencies in traders' behavior. We can explain this as follows..  

1. First, note that the Black-Scholes formula is simple and depends on a small number of parameters. In fact, the only major parameter that it depends on is the volatility,. $\sigma.$ A simple formula has some advantages. It is easy to understand and remember. But, more importantly, it is also easy to realize where or when it may go wrong. A simple formula permits developing ways to correct for any inaccuracies informally by making subjective adjustments during trading. The Black-Scholes formula has one parameter, and it may be easier to remember how to "adjust' this parameter to cover for the imperfections of the formula.10  

2. An important aspect of the Black--Scholes formula is that it has become a convention. In other words, it has become a standard among professionals and also in computer platforms. The formula provides a way to connect a volatility quote to a dollar value attached to this quote.. This way traders use the same formula to put a dollar value on a volatility number quoted by. the market. This helps in developing common platforms for hedging, risk managing, and. trading volatility.  

3. Thus, once we accept that the use of the BlackScholes formula amounts to a convention, and that traders differ in their selection of the value of the parameter $\sigma$ , then the critical process is no longer the option price, but the volatility. This is one reason why in many markets, such as caps, floors, and swaptions markets, the volatility is quoted directly.  

One way to account for the imperfections of the Black-Scholes assumptions would be for traders to adjust the volatility parameter.  

4. However, the convention creates new risks. Once the underlying is the volatility process, another issue emerges. For example, traders could add a risk premium to quoted volatilities. Just like the risk premium contained in asset prices, the quotes on volatility may incorporate a. risk premium.  

The volatility smile and its generalization, the volatility surface, could then contain a great deal of information concerning the implied volatilities and any arbitrage relations between them. Trading, pricing, hedging, and arbitraging of the smile thus become important.  
