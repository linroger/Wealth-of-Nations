# 16.8 INTRODUCTION TO THE SMILE  

Markets trade many options with the same underlying, but different strike prices and different expirations. Does the difference in strike price between options that are identical in every other aspect have any important implications?  

At first, the answer to this question seems to be no. After all, vanilla options are written on an underlying, with say, price $S_{t},$ and this price will have only one volatility at any time t, regardless of the strike price $K_{i}.$ Hence, it appears that, regardless of the differences in the strike price, the implied volatility of options written on the same underlying, with the same expiration, should be the same.  

Yet, this first impression is wrong. In reality, options that are identical in every respect, except for their strike, in general, have different implied volatilities. Overall, the more out-of-the-money a call (put) option is, the higher is the corresponding implied volatility. This well-established empirical fact is known as the volatility smile, or volatility skew, and has major implications for hedging, pricing, and marking-to-market of many important instruments. In the remainder of this chapter, we discuss the volatility smile and skews using caps and floors as vehicles for conveying the main ideas. This will indirectly give us an opportunity to discuss the engineering of this special class of convex instruments.  

From this point and on, in this chapter we will use the term smile only. This will be the case even when the smile is, in fact, a one-sided skew. However, whenever relevant, we will point out the differences.  
