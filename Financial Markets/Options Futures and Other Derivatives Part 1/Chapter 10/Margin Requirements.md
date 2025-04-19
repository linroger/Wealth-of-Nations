---
tags:
  - futures_contracts
  - margin_account
  - margin_requirements
  - naked_options
  - options_trading
aliases:
  - Margin
  - Margin Call
  - Naked Option
key_concepts:
  - buying on margin
  - initial margin requirement
  - maintenance margin
  - margin as guarantee
  - writing naked options
---

# 10.7 MARGIN REQUIREMENTS  

We discussed margin requirements for futures contracts in Chapter 2. The purpose of. margin is to provide a guarantee that the entity providing margin will live up to its obligations. If a trader buys an asset such as a stock or an option for cash there is no margin requirement. This is because the trade does not give rise to future obligations. As discussed in Section 5.2, if the trader shorts a stock, margin is required because the. trader then has the obligation to close out the position by buying the stock at some. future time. Similarly, when the trader sells (i.e., writes) an option, margin is required. because the trader has obligations in the event that the option is exercised..  

Assets are not always purchased for cash. For example, when shares are purchased in the United States, an investor can borrow up to. $50\%$ of the price from the broker. This. is known as buying on margin. If the share price declines so that the loan is substantially more than $50\%$ of the stock's current value, there is a "margin call', where the broker. requests that cash be deposited by the investor. If the margin call is not met, the broker sells the stock.  

When call and put options with maturities less than 9 months are purchased, the option price must be paid in full. Investors are not allowed to buy these options on. margin because options already contain substantial leverage and buying on margin would raise this leverage to an unacceptable level. For options with maturities greater than 9 months investors can buy on margin, borrowing up to. $25\%$ of the option value.  

# Writing Naked Options  

As mentioned, a trader who writes options is required to maintain funds in a margin account. Both the trader's broker and the exchange want to be satisfied that the trader will not default if the option is exercised. The amount of margin required depends on the trader's position.  

A naked option is an option that is not combined with an offsetting position in the underlying stock. The initial and maintenance margin required by the CBOE for a written naked call option is the greater of the following two calculations:  

1. A total of. $100\%$ of the proceeds of the sale plus $20\%$ of the underlying share. price less the amount, if any, by which the option is out of the money 2. A total of $100\%$ of the option proceeds plus $10\%$ of the underlying share price.  

For a written naked put option, it is the greater of  

1. A total of. $100\%$ of the proceeds of the sale plus $20\%$ of the underlying share. price less the amount, if any, by which the option is out of the money 2. A total of $100\%$ of the option proceeds plus $10\%$ of the exercise price.  

The $20\%$ in the preceding calculations is replaced by $15\%$ for options on a broadly based stock index because a stock index is usually less volatile than the price of an individual stock.  

# Example 10.3  

An investor writes four naked call option contracts on a stock. The option price is $\$5$ , the strike price is. $\$40$ , and the stock price is. $\$38$ . Because the option is $\$2$ Out of the money, the first calculation gives.  

$$
400\times(5+0.2\times38-2)=\S4{,}240
$$  

The second calculation gives  

$$
400\times(5+0.1\times38)=\S3.520
$$  

The initial margin requirement is therefore $\$4,240$ . Note that, if the option had been a put, it would be $\$2$ in the money and the margin requirement would be  

$$
400\times(5+0.2\times38)=\S5.040
$$  

In both cases, the proceeds of the sale can be used to form part of the margin account.  

A calculation similar to the initial margin calculation (but with the current market price. of the contract replacing the proceeds of sale) is repeated every day. Funds can be withdrawn from the margin account when the calculation indicates that the margin required is less than the current balance in the margin account. When the calculation indicates that a greater margin is required, a margin call will be made..  

# Other Rules  

In Chapter 12, we will examine option trading strategies such as covered calls, protective puts, spreads, combinations, straddles, and strangles. The CBOE has special rules for determining the margin requirements when these trading strategies are used. These are described in the CBOE Margin Manual, which is available on the CBOE website (www.cboe.com).  

As an example of the rules, consider an investor who writes a covered call. This is a written call option when the shares that might have to be delivered are already owned.  

Covered calls are far less risky than naked calls, because the worst that can happen is that the investor is required to sell shares already owned at below their market value. No margin is required on the written option. However, the investor can borrow an amount equal to $0.5\operatorname*{min}(S,K)$ , rather than the usual 0.5S, on the stock position.  
