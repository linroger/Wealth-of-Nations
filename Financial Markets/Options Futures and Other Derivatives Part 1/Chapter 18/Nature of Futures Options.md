---
tags:
  - american_options
  - expiration_dates
  - futures_contracts
  - futures_options
  - option_payoffs
aliases:
  - Futures Call Option
  - Futures Option
  - Futures Put Option
key_concepts:
  - 'American options: exercise anytime'
  - 'Call option: long futures contract'
  - Expiration before futures contract
  - 'Futures option: right, not obligation'
  - 'Put option: short futures contract'
---

# 18.1 NATURE OF FUTURES OPTIONS  

A futures option is the right, but not the obligation, to enter into a futures contract at a certain futures price by a certain date. Specifically, a futures call option is the right to enter into a long futures contract at a certain price; a futures put option is the right to enter into a short futures contract at a certain price. Futures options are generally American; that is, they can be exercised any time during the life of the contract.  

If a futures call option is exercised, the holder acquires a long position in the underlying futures contract plus a cash amount equal to the most recent settlement futures price minus the strike price. If a futures put option is exercised, the holder acquires a short position in the underlying futures contract plus a cash amount equal to the strike price minus the most recent settlement futures price. As the following examples show, the effective payoff from a futures call option is $\operatorname*{max}(F-K,0)$ and the effective payoff from a futures put option is $\operatorname*{max}(K-F,0)$ , where $F$ is the futures price at the time of exercise and. $K$ is the strike price..  

# Example 18.1  

Suppose it is August 15 and a trader has one September futures call option.   
contract on copper with a strike price of 320 cents per pound. One futures.   
contract is on 25,000 pounds of copper. Suppose that the futures price of copper.   
for delivery in September is currently 331 cents, and at the close of trading on.   
August 14 (the last settlement) it was 330 cents. If the option is exercised, the trader receives a cash amount of.  

$$
25.000\times(330-320)\mathrm{cents}=\S2{,}500
$$  

plus a long position in a futures contract to buy 25,000 pounds of copper in September. If desired, the position in the futures contract can be closed out immediately. This would leave the trader with the $\$2,500$ cash payoff plus an amount  

$$
25\small{,}000\times(331-330)\mathrm{cents}=\S250
$$  

reflecting the change in the futures price since the last settlement. The total payoff from exercising the option on August 15 is. $\$2,750$ , which equals. $25{,}000(F-K)$ where $F$ is the futures price at the time of exercise and $K$ is the strike price..  

# Example 18.2  

A trader has one December futures put option on corn with a strike price of 600 cents per bushel. One futures contract is on 5,000 bushels of corn. Suppose that the current futures price of corn for delivery in December is 580, and the most recent settlement price is 579 cents. If the option is exercised, the trader receives a cash amount of  

$$
5,000\times(600-579)\mathrm{cents}=\S1,050
$$  

plus a short position in a futures contract to sell 5,o00 bushels of corn in December. If desired, the position in the futures contract can be closed out. This would leave the trader with the $\$1,050$ cash payoff minus an amount  

$$
5,000\times(580-579)\mathrm{cents}=\S50
$$  

reflecting the change in the futures price since the last settlement. The net payoff from exercise is $\$1,000$ , which equals $5,000(K\mathrm{~-~}F)$ , where $F$ is the futures price at the time of exercise and $K$ is the strike price.  

# Expiration Months  

Futures options are referred to by the delivery month of the underlying futures contract not by the expiration month of the option. As mentioned earlier, most futures options are American. The expiration date of a futures option contract is usually a short period of time before the last trading day of the underlying futures contract. (For example, the CME Group Treasury bond futures option expires on the latest Friday. that precedes by at least two business days the end of the month before the futures. delivery month.) Exceptions are the CME Group mid-curve Eurodollar and the mid-. curve three-month SOFR contracts where the futures contract expires much later than the options contract.  

# Options on Interest Rate Futures  

In Chapter 6, we discussed the interest rate futures contracts traded by the CME Group. Options on interest rate futures are also traded by the exchange. Consider, for example, the Treasury bond futures option contract. This is an option to enter into a Treasury bond futures contract. One Treasury bond futures contract is for the delivery of bonds with a principal of $\$100,000$ The price of the Treasury bond futures option is quoted as a percentage of the face value of the underlying Treasury bonds to the nearest sixtyfourth of $1\%$  

As explained in Chapter 6, the CME's most popular contract on short-term interest rates has traditionally been its Eurodollar futures contract. As LIBOR is phased out, the exchange expects this to be replaced by the three-month SOFR futures contract. Options on Eurodollar futures have been popular and are expected to be replaced by options on three-month SOFR futures, which were launched by the CME in January 2020. It will be recalled that the Eurodollar rate is a forward-looking rate (a borrowing rate for the next three months) whereas SOFR is a backward-looking rate (calculated by compounding overnight rates for the previous three months). Eurodollar and threemonth SOFR futures are designed so that a one-basis-point move in the futures price is worth $\$25$ per contract. The same is true of options on these futures contracts.  

Interest rate futures option contracts work in the same way as the other futures options contracts discussed in this chapter. For example, in addition to the cash payoff, the holder of a call option obtains a long position in the futures contract when the. option is exercised and the option writer obtains a corresponding short position. The total payoff from the call, including the value of the futures position, is. $\operatorname*{max}(F-K,0)$ where $F$ is the futures price at the time of exercise and. $K$ is the strike price.  

Interest rate futures prices increase when bond prices increase (i.e., when interest rates fall). They decrease when bond prices decrease (i.e., when interest rates rise). An investor who thinks that short-term interest rates will rise can speculate by buying put options on Eurodollar or SOFR futures, whereas an investor who thinks the rates will fall can speculate by buying call options on Eurodollar or SOFR futures. An investor who thinks that long-term interest rates will rise can speculate by buying put options on Treasury note futures or Treasury bond futures, whereas an investor who thinks the rates will fall can speculate by buying call options on these instruments.  

# Example 18.3  

Suppose that the June SOFR futures is 99.35 (indicating an interest rate of $0.65\%$ per annum) and that an investor expects short-term interest rates to decline so that overnight rates between June and September are less than $0.5\%$ per annum. Suppose also that the price of a call option with a strike price of 99.50 is 0.05 (i.e., 5 basis points). The investor could buy a call option contract with a strike price of 99.50 for $\$25\times5$ or $\$125$ . If the investor exercises the call when the futures price is 99.70 (indicating an interest rate of $0.3\%$ per annum), the payoff to the investor is $\$25\times20$ , or $\$500$ , and the investor's profit is $\$375$  

# Example 18.4  

It is August and the futures price for the December Treasury bond contract is 96-09 (or $96{\frac{9}{32}}=96.28125)$ . The yield on long-term government bonds is about. $6.4\%$ per annum. An investor who feels that this yield will fall by December. might choose to buy December calls with a strike price of 98. Assume that the price of these calls is 1-04 (or $1\frac{4}{64}=1.0625\%$ of the principal). If long-term rates. fall to $6\%$ per annum and the Treasury bond futures price rises to 100-00, the investor will make a net profit per. $\$100$ of bond futures of  

$$
100.00-98.00-1.0625=0.9375
$$  

Since one option contract is for the purchase or sale of instruments with a face value of $\$100,000$ , the investor's profit is $\$937.50$ per option contract bought.  
