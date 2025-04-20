---
tags:
  - call_option
  - currency_options
  - fx_market
  - fx_rates
  - put_option
aliases:
  - Currency Derivatives
  - FX Options
key_concepts:
  - Call option on dollar
  - Currency option mechanics
  - Dual nature of FX rates
  - Put option on yen
  - Strike price inversion
---

# 5.5 CURRENCY OPTIONS  

Options on currency rates work the same way as options on any asset price. Because currency.   
rates are prices of one currency in terms of another, they can be expressed with either currency.   
as the priced one and the pricing one. We do not express the prices of other assets in such inverted terms, for example, as the number of ABC shares per dollar. With currencies, both.   
ways - yen per dollar and dollar per yen - are natural. Due to this dual nature of FX rates,.   
currency options, just like forwards and futures, can be viewed in two ways..  

Let us consider a call option on the US dollar with a strike of 110 Japanese yen per dollar. (think of the dollar as the underlying asset) with one call covering $\$1,000$ (think of dollars as shares and each call is on 1,000 shares). If the dollar's price rises above $\yen110$ , the holder gets a payoff, otherwise not. The payoff, as with any call, is equal to the difference between the spot price of the underlying asset S (i.e. the spot FX rate in $\yen1S$ ) on the expiry date minus the strike $K$ , or nothing, times the number of units of the underlying asset (principal amount or size). That is, just like with any call, it is:.  

$$
C a l l^{\frac{J P Y}{U S D}}=S i z e^{U S D}\times M a x\left(S^{\frac{J P Y}{U S D}}-K^{\frac{J P Y}{U S D}},0\right)
$$  

where both $S$ and $K$ are in $\yen1S$ . The payoff is denominated in $\yen1$ . If the spot FX rate at expiry is $\yen117$ , we get $\yen7$ times the 1,000 unit size, or $\yen7,000$ , equivalent to $\$59.82905983$ at the $\yen117$ FX rate; if the spot FX rate at expiry is. $\yen102$ , we get nothing. A physical-settle. version of this option would be the right to buy 1,000 dollars for $\yen110$ apiece which would. be exercised only if the spot value of the dollar is greater than. $\yen110$ . But the right to buy the dollar is automatically equivalent to the right to sell the yen..  

The call on the dollar struck at. $\yen10$ is also a put on the yen struck at. $1/110=$ $\$0.00909091$ If the size of the call was 1,000 dollars, then the size of the put is 110,000 yen (converting, using the strike FX rate)..  

$$
C a l l^{\frac{U S D}{J P Y}}=S i z e^{J P Y}\times M a x(K^{\frac{U S D}{J P Y}}-S^{\frac{U S D}{J P Y}},0)
$$  

When the value of the yen goes down to $\$0.00854701$ , i.e. the spot FX rate moves to $\yen117$ we get a payout of  

$$
0.00909091-0.00854701=\$0.00054390
$$  

per unit of yen. This times the size of the option, 110,000 units of yen, gives us the total payoff of $\$59.82905983$ which is the same as $\yen7,000$ at the $\yen117$ FX rate. When the spot FX rate goes up to $\$0400980392$ , i.e. $\yen102$ , we get nothing. We have the following rule:.  

# Call on Currency 1 = Put on Currency 2  

with the size converted at the strike FX rate and the strike rate inverted. This rule is true for all currency options, standard or otherwise.  
