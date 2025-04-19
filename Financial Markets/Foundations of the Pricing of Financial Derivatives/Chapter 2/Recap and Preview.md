---
tags:
  - '#american_put_options'
  - '#arbitrage_strategy'
  - '#continuous_compounding'
  - '#convexity'
  - '#dividend_impact'
  - '#option_price_bounds'
  - '#option_pricing'
  - '#put_call_parity'
  - '#risk_free_rate'
  - '#trading_days'
---
# 2.13 RECAP AND PREVIEW

In this chapter we identified certain conditions that restrict option prices. For example, we covered upper and lower limits, the relationships between options differing by exercise price or time to expiration, and we derived the relationship between put and call option prices. We also covered the effect of interest rates and volatility on option prices. These results do not identify specific option prices, but they do give us restrictions on option prices and, thereby, enable us to narrow down prices so that we can say more than simply that prices are nonnegative.

In Chapter 3, we shall take a step away from derivatives and provide a review of. some of the general mathematical results that we need to recall from previous courses. This review will be foundational material from what is hopefully previously taken math. courses. You may actually just need to skim over it..

# QUESTIONS AND PROBLEMS

1 In your own words, define arbitrage.

2 Based on the following illustration of two instruments (1 and 2) and two points in time (0 and 1), design an arbitrage strategy. Defend your answer by computing cash flows at both points in time.

![](9c9f699347a55688e1435daf982da378a1fdb6aa81f5bd856a98cf81ac776fb2.jpg)

3  This problem, as well as the next one, explores American put lower boundary violations. Consider the following inputs: Suppose the stock price is $S_{t}=95$ , strike price is $X=100$ , risk-free interest rate is $r_{c}=5.0\%$ (continuously compounded, annualized, applies to both maturities--option and dividend), time to maturity is one year, a $4.75$ dividend will be paid in one month, and the quoted American put price is 4.95. Identify the arbitrage opportunity and illustrate how it would be captured.

4 Consider the same inputs as the previous problem, but now let the dividend amount increase to 4.9875 per share paid in one month and the quoted put price be 5.04. Again, the stock price is $S_{t}=95$ , the strike price is $X=100$ , the risk-free interest rate is $r_{c}=5.0\%$ , and the time to maturity is one year. Identify the arbitrage opportunity and illustrate how it would be captured.

5 This problem as well as the next one explores American put-call parity violations. Consider the following inputs: Suppose the stock price is $S_{t}=100$ , strike price is $X=$ 100, risk-free interest rate is $r_{c}=5.0\%$ (continuously compounded, annualized, applies to both maturities-option and dividend), time to maturity is six months, a dividend of 1 will be paid in three months, and the quoted American put price is 6.02. If the quoted American call price is 4.98, identify the arbitrage opportunity and illustrate how it would be captured.

6 Again, consider the same inputs as the previous problem except now the American call price is 8.54. Identify the arbitrage opportunity and illustrate how it would be captured.

# NOTES

1. There is some debate on whether to use trading days rather than calendar days. In the US, there are approximately 252 trading days in a year.
2. We are also making a subtle assumption that the asset incurs no costs to hold. At one time, many securities had costs to hold and store, owing to the fact that physical certificates were issued, but that is no longer true as securities are now almost exclusively issued in electronic form. Most commodities such as oil and gold would incur storage costs, and these costs would factor into the pricing models, but we shall ignore these until we get to pricing forwards and futures much later in the book.
3. If there are costs involved in doing the trades, the prices will be pushed to near equality, such that transaction costs would discourage further exploitation of any small remaining price difference.
4. We assume continuous compounding and annualized rate $(r_{c})$ and express the time to expiration as a fraction of a year $(\tau)$ . Thus, the present value of 1.0 is $e^{-r_{c}\tau}$
5. We described what happens at expiration as involving a transaction in the underlying. Some option contracts are written to provide cash settlement, meaning that instead of actually buying or selling the underlying, the short pays the long a cash settlement, which is equal to the exercise values as given by Equations (2.4) and (2.5).
6. Throughout this book, we assume positive risk-free rates. 7. We skipped calling our portfolios C and D, so that you would not confuse C for a call and because we use $D_{t}$ as the present value of the dividends paid over the life of the option..
8. Clearly, we could have also assumed no dividends, so the arguments here imply that there are dividends on the underlying.
9. A function is convex if a weighted average of two points is greater than a point in between the two points. Technically the fact that we have an inequality means that the option price function might not be convex at some point, but it will generally be the case that convexity holds. It will fail to hold only in the extreme case when all of the options are very deep-in-the-money or deep out-of-the-money.
10. Of course, we can again make various algebraic arrangements to put any of the instruments in the middle of the two inequalities to put bounds on their prices.


