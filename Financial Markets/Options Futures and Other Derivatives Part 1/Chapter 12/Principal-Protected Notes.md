---
tags:
  - european_call_option
  - principal_protected_notes
  - retail_market
  - risk_free_investment
  - zero_coupon_bond
aliases:
  - PPN
  - Principal Protected Notes
key_concepts:
  - Conservative investors
  - European call option
  - Principal-protected notes
  - Risky asset performance
  - Zero-coupon bond
---

# 12.1 PRINCIPAL-PROTECTED NOTES  

Options are often used to create what are termed principal-protected notes for the retail market. These are products that appeal to conservative investors. The return earned by the investor depends on the performance of a stock, a stock index, or other risky asset,  

but the initial principal amount invested is not at risk. An example will illustrate how a simple principal-protected note can be created.  

# Example 12.1  

Suppose that the 3-year interest rate is $6\%$ with continuous compounding. This means that $1,000e^{-0.06\times3}=\$835.27$ will grow to $\$1,000$ in 3 years. The differencee between $\$1,000$ and $\$835.27$ is $\$164.73$ . Suppose that a stock portfolio is worth. $\$1,000$ and provides a dividend yield of. $1.5\%$ per annum. Suppose further that a 3-year at-the-money European call option on the stock portfolio can be purchased for less than. $\$164.73$ . (From DerivaGem, it can be verified that this will be the. case if the volatility of the value of the portfolio is less than about. $15\%$ .) A bank can offer clients a $\$1,000$ investment opportunity consisting of:  

1. A 3-year zero-coupon bond with a principal of $\$1,000$   
2. A 3-year at-the-money European call option on the stock portfolio.  

If the value of the porfolio increases the investor gets whatever. $\$1,000$ invested in the portfolio would have grown to. (This is because the zero-coupon bond pays off $\$1,000$ and this equals the strike price of the option.) If the value of the portfolio goes down, the option has no value, but payoff from the zero-coupon bond ensures that the investor receives the original. $\$1,000$ principal invested.  

The attraction of a principal-protected note is that an investor is able to take a risky. position without risking any principal. The worst that can happen is that the investor. loses the chance to earn interest, or other income such as dividends, on the initial investment for the life of the note..  

There are many variations on the product in Example 12.1. An investor who thinks. that the price of an asset will decline can buy a principal-protected note consisting of a zero-coupon bond plus a put option. The investor's payoff in 3 years is then. $\$1,000$ plus the payoff (if any) from the put option..  

Is a principal-protected note a good deal from the retail investor's perspective? A bank will always build in a profit for itself when it creates a principal-protected note. This means that, in Example 12.1, the zero-coupon bond plus the call option will always cost the bank less than $\$1,000$ . In addition, investors are taking the risk that the bank will not be in a position to make the payoff on the principal-protected note at maturity. (Some retail investors lost money on principal-protected notes created by Lehman Brothers when it failed in 2008.) In some situations, therefore, an investor will be better off if he or she buys the underlying option in the usual way and invests the remaining principal in a risk-free investment. However, this is not always the case. The investor is likely to face wider bid-ask spreads on the option than the bank and is likely to earn lower interest rates than the bank. It is therefore possible that the bank can add value for the investor while making a profit itself.  

Now let us look at the principal-protected notes from the perspective of the bank. The economic viability of the structure in Example 12.1 depends critically on the level of interest rates and the volatility of the portfolio. If the interest rate is $3\%$ instead of $6\%$ the bank has only $1,000-1,\dot{0}00e^{-0.03\dot{\times}3}=\S86.07$ with which to buy the call option. If interest rates are $6\%$ , but the volatility is. $25\%$ instead of $15\%$ , the price of the option. would be about $\$221$ . In either of these circumstances, the product described in. Example 12.1 cannot be profitably created by the bank. However, there are a number of ways the bank can still create a viable 3-year product. For example, the strike price of the option can be increased so that the value of the portfolio has to rise by, say, $15\%$ before the investor makes a gain; the investor's return could be capped; the return of the investor could depend on the average price of the asset instead of the final price; a knockout barrier could be specified. The derivatives involved in some of these alternatives will be discussed later in the book. (Capping the option corresponds to the creation of a bull spread for the investor and will be discussed later in this chapter.)  

One way in which a bank can sometimes create a profitable principal-protected note when interest rates are low or volatilities are high is by increasing its life. Consider the situation in Example 12.1 when (a) the interest rate is $3\%$ rather than $6\%$ and (b) the stock portfolio has a volatility of. $15\%$ and provides a dividend yield of. $1.5\%$ DerivaGem shows that a 3-year at-the-money European option costs about $\$119$ . This is more than the funds available to purchase it $(\hat{1,000}-\hat{1},000e^{-0.03\times3}=\S86.07\$ . A 10-year at-the-money option costs about $\$217$ This is less than the funds available to purchase it $(1,000-\dot{\phantom{-}}1,000e^{-0.03\times10}=\S259.18,$ I, making the structure profitable. When. the life is increased to 20 years, the option cost is about. $\$281$ , which is much less than. the funds available to purchase ite $(1,000-1,000e^{-0.03\times20}=\mathbb{\mathbb{S}}451.19)$ I, so that the structure is even more profitable.  

A critical variable for the bank in our example is the dividend yield. The higher it is,. the more profitable the product is for the bank. If the dividend yield were zero, the. principal-protected note in Example 12.1 cannot be profitable for the bank no matter how long it lasts. (This follows from equation (11.4).).  
