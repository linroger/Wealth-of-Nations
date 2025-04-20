---
tags:
  - binomial_model
  - black_scholes
  - libor
  - option_pricing
  - put_call_parity
aliases:
  - Binomial
  - Black-Scholes
  - LIBOR
  - Option Pricing Exercise
  - Put-Call Parity
key_concepts:
  - Binomial model inputs
  - Black-Scholes model
  - Black-Scholes output
  - Continuous put-call parity
  - Delta difference
  - Dividend yield calculation
  - Fair forward calculation
  - Futures cash-and-carry parity
  - Greeks of calls/puts
  - Implied volatility
  - Interest rate conversion
  - Option pricing exercise
  - Put-call parity
  - Strike price impact
---

# 5.9 A REAL-LIFE OPTION PRICING EXERCISE  

In this section, we put everything we have learned so far to use in one comprehensive exercise using very simple Excel models. The Black-Scholes takes five minutes to set up; the binomial takes a bit longer, but only because we have to be careful in converting the inputs consistently.  

# 5.9.1 Consistency Checks: Put-Call Parity, Black-Scholes, and Binomial  

Option models are relative value tools. We observe the implied volatility of one option and use it to price another. We observe the short-term interest rate and value the forward relative to the spot. We also use the interest rate as an input into the option valuation model. The prices of the call minus the put have to produce the value of the forward. Black-Scholes has to give the same price for European calls and puts as the binomial. If not, we are not using the models correctly.  

# Data  

We start with the following. The 6-month LIBOR is. $3\%$ semiannually compounded (ignore Act/360). The stock index is at 1,000. The annualized volatility of the at-the-money options is $20\%$ . The total present value of the dividends we estimate over the 6-month period is $\$4.987521$ on a $\$1,000$ investment in the index. (The dividends here could represent the interest rate differential in currencies, commodity storage fees, or stock lending fees.)  

# Discrete-to-Continuous Conversion  

We need to make sure that we use all the variables either as discrete or as continuous. We don't want to mix them. First the interest rate conversion. We trace a. $\$1$ investment over 6 months:  

$$
e^{r_{c}T}=1+\frac{r_{d}}{2}
$$  

with the discrete rate $r_{d}=3\%$ , time $T=0.5$ year. We get the continuous equivalent rate $r_{c}=2.9777\%$ . Next we convert the dividends. Since we are given the total present value of $D=\$4.987521$ , and we know the spot value of the index $S=1{,}000$ , then assuming we simply hold stocks for 6 months we get the continuous dividend yield 8 from:  

$$
{\cal S}\times e^{-\delta T}={\cal S}-{\cal D}
$$  

The dividend yield is $\delta=1\%$  

Futures Cash-and-Carry Parity  

The fair forward in continuous time is equal to:  

$$
F=S\times e^{(r_{C}-\delta)T}
$$  

Plugging in we get $F=1,009.938.$ We verify that we would get the same in discrete time:  

$$
F=(S-D)\times\left(1+{\frac{r_{d}}{2}}\right)=995.012479\times1.015=1,009.938
$$  

Data Summary  

We have:  

$$
\begin{array}{l}{S=1,000}\ {r_{C}=2.9777\%}\ {\delta=1\%}\ {\sigma=0.20}\ {T=0.5}\ {F=1,099.93\S}\end{array}
$$  

Table 5.3Black-Scholes output for $K=980$   


<html><body><table><tr><td>Data</td><td colspan="4">Black-Scholes pre-calc</td><td>Call</td><td>Put</td></tr><tr><td></td><td></td><td>d</td><td>0.283490</td><td>Price</td><td>71.25126</td><td>41.75576</td></tr><tr><td>S</td><td>1,000</td><td>d2</td><td>0.142069</td><td>Delta</td><td>0.608549</td><td>-0.386463</td></tr><tr><td>K</td><td>980</td><td>N(d1)</td><td>0.611600</td><td>Gamma</td><td>0.002696</td><td>0.002696</td></tr><tr><td>T</td><td>182.5</td><td>N(d2)</td><td>0.556487</td><td>Vega</td><td>269.6325</td><td>269.6325</td></tr><tr><td>r</td><td>2.98%</td><td>N(-d1)</td><td>0.388400</td><td></td><td></td><td></td></tr><tr><td>sig</td><td>20.00%</td><td>N(-d2)</td><td>0.443513</td><td></td><td></td><td></td></tr><tr><td>S</td><td>1.00%</td><td>sig√T</td><td>0.141421</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>e(-8T)</td><td>0.995012</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>('p)u</td><td>0.383229</td><td></td><td></td><td></td></tr></table></body></html>  

# Black-Scholes Prices for $\mathrm{K}=980$  

First, let us price calls and puts struck at $K=980$ . We plug into the. $d_{1}$ and $d_{2}$ formulas:  

$$
d_{1}={\frac{\ln{\frac{S}{K}}+(r-\delta+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}={\frac{\ln{\frac{1.000}{980}}+(0.029777-0.01+0.20^{2}/2)\times0.5}{0.20{\sqrt{0.5}}}}=0.2
$$  

and $d_{2}=d_{1}-\sigma\sqrt{T}=0.283490-0.20\sqrt{0.5}=0.142069$  

From the cumulative normal distributions, we get $N(d_{1})=0.611600$ and $N(d_{2})=$ 0.556487. We also get $N(-d_{1})=0.388400$ and $N(-d_{2})=0.443513$ . We then plug into. the Black-Scholes formula to get.  

$$
{\begin{array}{r l}&{C=S e^{-\delta T}N(d_{1})-K e^{-r T}N(d_{2})}\ &{\quad=1,000\times e^{-0.01\times0.5}\times0.611600-980\times e^{-0.02977\times0.5}\times0.556487}\ &{\quad=71.25126}\end{array}}
$$  

and  

$$
{\begin{array}{r l}&{P=K e^{-r T}N(-d_{2})-S e^{-\delta T}N(-d_{1})}\ &{\quad=980\times e^{-0.029777\times0.5}\times0.443513-1,000\times e^{-0.01\times0.5}\times0.388400}\ &{\quad=41.75576}\end{array}}
$$  

Table 5.3 shows the Black-Scholes Excel output for the prices and the Greeks of calls and puts with $K=980$  

Black-Scholes Prices for $\mathrm{K}=\mathrm{F}=1,009.938$  

We repeat the exercise for options with the strike price equal to the forward. Table 5.4 contains the Excel output.  

Note that the price of the call and the put is the same when the strike is equal to the forward,. and that irrespective of the strike the delta difference must be equal to 1. This follows from the put-call parity.  

We plug into the continuous version of the put-call parity with dividends:  

$$
C-P=S e^{-\delta T}-K e^{-r T}
$$  

Table 5.4Black-Scholes output for $K=1,009.938$   


<html><body><table><tr><td>Data</td><td colspan="3">Black-Scholes pre-calc</td><td>Call</td><td colspan="2">Put</td></tr><tr><td></td><td></td><td>d</td><td>0.070710</td><td>Price</td><td>56.0908</td><td>56.0908</td></tr><tr><td>S</td><td>1,000</td><td>d2</td><td>-0.070711</td><td>Delta</td><td>0.525551</td><td>-0.469461</td></tr><tr><td>K</td><td>1,009.938</td><td>N(d1)</td><td>0.528186</td><td>Gamma</td><td>0.0028</td><td>0.0028</td></tr><tr><td>T</td><td>182.5</td><td>N(d2)</td><td>0.471814</td><td>Vega</td><td>279.9870</td><td>279.9870</td></tr><tr><td>r</td><td>2.98%</td><td>N(-d1)</td><td>0.471814</td><td></td><td></td><td></td></tr><tr><td>sig</td><td>20.00%</td><td>N(-d2)</td><td>0.528186</td><td></td><td></td><td></td></tr><tr><td></td><td>1.00%</td><td>sig √T</td><td>0.141421</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>e(-8T)</td><td>0.995012</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>n(d1)</td><td>0.397946</td><td></td><td></td><td></td></tr></table></body></html>  

First for the strike $K=980$ ..  

$$
71.25126-41.75576=1,000\times0.995012-980\times0.985221=29.495
$$  

The fair value of the off-market forward to buy stock at 980 is. $\$29.495$ . To lock in thet purchase price of 980 by buying calls and selling puts, one would have to spend out-of-pocket $\$29.495$  

Next for the strike $K=1,009.938$  

$$
56.0908-56.0908=1.000\times0.995012-1.009.938\times0.985221=0
$$  

The fair value of the on-market forward to buy stock at 1,009.938 is. $\$0$ (costless). To lock in the purchase price of 1,009.938 by buying calls and selling puts, one would not have to spend anything out-of-pocket.  

# Convert the Inputs for a Binomial with $\Nu=100$ Steps  

Using the logic of Section 5.6, but applying the continuous Black-Scholes equivalents listed in Section 5.7, we set up the binomial tree with $N=100$ steps. Our time step is one-half year divided by 100 or $\Delta t=1/200$ . We then compute  

$$
u=e^{\sigma{\sqrt{\Delta t}}},\quad d=1/u,\quad q={\frac{e^{r\Delta t}-d}{u-d}}
$$  

Table 5.5 shows the Excel output of the pre-calculated variables.  

Table 5.5Binomial inputs with $N=100$ steps   


<html><body><table><tr><td>Data</td><td></td><td>Set-up</td><td>100</td><td>Steps</td><td></td></tr><tr><td></td><td></td><td>△t</td><td>0.005000</td><td>n</td><td>1.014243</td></tr><tr><td>S</td><td>1,000</td><td>sig√t</td><td>0.014142</td><td>p</td><td>0.985957</td></tr><tr><td>K</td><td>1,000</td><td>r△t</td><td>0.000149</td><td>b</td><td>0.499961</td></tr><tr><td>T</td><td>182.5</td><td>-8△t</td><td>-0.000050</td><td>1-q</td><td>0.500039</td></tr><tr><td>R</td><td>2.9778%</td><td>e(sig)√△t)</td><td>1.014243</td><td></td><td></td></tr><tr><td>sig</td><td>20.00%</td><td>e(r △t)</td><td>1.000149</td><td></td><td></td></tr><tr><td></td><td>1.00%</td><td>e(-8 △t)</td><td>0.999950</td><td></td><td></td></tr></table></body></html>  

Table 5.6 Binomial output for $K=980$   


<html><body><table><tr><td>Data</td><td></td><td>Set-up</td><td>100</td><td></td><td>Call</td><td>Put</td></tr><tr><td></td><td></td><td>△t</td><td>0.005000</td><td>Price</td><td>71.34</td><td>41.84</td></tr><tr><td>S</td><td>1,000</td><td>sig√t</td><td>0.014142</td><td>Delta</td><td>0.6085</td><td>-0.3866</td></tr><tr><td>K</td><td>980</td><td>r△t</td><td>0.000149</td><td></td><td></td><td></td></tr><tr><td>T</td><td>182.5</td><td>-8△t</td><td>-0.000050</td><td>u</td><td>1.014243</td><td></td></tr><tr><td>r</td><td>2.9778%</td><td>e(sig √t)</td><td>1.014243</td><td>p</td><td>0.985957</td><td></td></tr><tr><td>sig</td><td>20.00%</td><td>e(r △t)</td><td>1.000149</td><td>b</td><td>0.499961</td><td></td></tr><tr><td></td><td>1.00%</td><td>e(-8 △t)</td><td>0.999950</td><td>1-q</td><td>0.500039</td><td></td></tr></table></body></html>  

Table 5.7 Binomial output for $K=1,009.938$   


<html><body><table><tr><td>Data</td><td></td><td>Set-up</td><td>100</td><td></td><td>Call</td><td>Put</td></tr><tr><td></td><td></td><td>△t</td><td>0.005000</td><td>Price</td><td>56.20</td><td>56.20</td></tr><tr><td>S</td><td>1,000</td><td>sig√△t</td><td>0.014142</td><td>Delta</td><td>0.5255</td><td>-0.4696</td></tr><tr><td>K</td><td>1,009.938</td><td>r△t</td><td>0.000149</td><td></td><td></td><td></td></tr><tr><td>T</td><td>182.5</td><td>-8△t</td><td>-0.000050</td><td>n</td><td>1.014243</td><td></td></tr><tr><td>r</td><td>2.9778%</td><td>e(sig)√△t</td><td>1.014243</td><td>p</td><td>0.985957</td><td></td></tr><tr><td>sig</td><td>20.00%</td><td>e(r △t)</td><td>1.000149</td><td>b</td><td>0.499961</td><td></td></tr><tr><td>8</td><td>1.00%</td><td>e(-8 △t)</td><td>0.999950</td><td>1-q</td><td>0.500039</td><td></td></tr></table></body></html>  

We set up the tree, assign the option values at the last time step $N=100$ (expiry) and use the recursive algorithm for the values of the calls and puts at every node of the tree:  

$$
C=e^{-r\Delta t}[q C_{u}+(1-q)C_{d}]
$$  

# Price the $\mathrm{K}=980$ Options in the Binomial  

Table 5.6 shows the Excel output from the binomial for calls and puts struck at $K=980$  

The prices are off by about 9 cents. To improve the accuracy, we would need to increase the number of steps or apply other error-reducing methods. One such method that is commonly used -- the variance-reduction method-- is to compute deviations from known continuous values instead of absolute prices. Most commercially available option-modeling software comes with plenty of tricks to eliminate pricing errors.  

# Price the $\mathrm{K}=1,009.938$ Options in the Binomial  

Table 5.7 shows the Excel output from the binomial for calls and puts struck at. $K=1,009.938$ This time we are off by 11 cents. We would want to calibrate our model to ensure that it does not have significant pricing errors for any strikes, or any other inputs..  

# Options on Non-Price Variables  

Options can be written on any variable, not just the price of some asset. Suppose we write a put option on the temperature reading in Paris on July 15, 2014, with a strike temperature. of $23~^{\circ}\mathrm{C}$ We need to define how the outcome of the event will be translated into a monetary. payoff. With stocks or currencies, this is automatic. Once we know the size of the option, say 100 shares, the payoff is equal to the price difference per unit times the size. With options on non-price variables, we have to define a number that translates the units of the non-price variable into money. Once we specify the multiplier of. $\yen500$ per $1~^{\circ}\mathbf{C}$ , the definition of our. option is complete. If the temperature in Paris on the expiry date is. $17~^{\circ}\mathrm{C}$ our put option pays $23-17=6$ times 500, or $\mathbf{\epsilon}{\epsilon}3\mathbf{,}000$ If the temperature is $26~^{\circ}\mathrm{C}$ , the put pays nothing.  

When valuing an option on a non-price variable, it is very important to determine whether. the non-price variable is a linear or near-linear function of a price of something or whether it is not a linear function. If it is a linear function, then the valuation will rely on fairly simple. modifications of the Black-Scholes model. The examples of this case include currencies and stock indexes. If the option is not a linear function of a price, then the valuation can be very. complex. The examples of this second case are options on long interest rates. To hedge an option on an interest rate, one will need to buy or sell a bond. The payoff of the option is linear in the rate; the bond price is polynomial in the rate. This "convexity"' of the bond price in the rate will mean that if the convexity is ignored then, even instantaneously, the hedge will be off. The goal of this chapter is to ease the reader into the complicated world of stock, currency, and interest rate options that require convexity adjusted models or full-blown interest rate models.  

As a preview, we look at two easy cases. The first, common example of a non-price variable is a stock index like the S&P 500 or Nikkei 225. A stock index is not a price of anything, but a divisor-normalized number designed to track the percentage changes in a basket of stocks.. The basket changes over time as some stocks come in and some are removed. Consider the. Nikkei 225 index. In order to define a payoff of an option we need to translate the index points into yen. For example, we may specify that an 11,000 call will pay the difference between the index value and strike level times $\yen10,000$ , or zero, whichever is greater. If the index hits 11,078.23 on the expiry date of the call, the holder would get  

$$
(11,078.23-11,000)\times\yen10,000=\yen782,300
$$  

The second, slightly more difficult case involves the multiplier that is not be specified in what seems natural. Suppose a US investor wants exposure to the Japanese stock market, but does not want to bear currency risk. We could define the multiplier in dollars per Nikkei point, e.g. $\$250$ per point. The holder would then get  

$$
(11,078.23-11,000)\times\S250=\S19,557.50
$$  

The option defined in yen is easy to price and hedge; the one in dollars is not. The yendenominated option is hedged like a stock option, by borrowing money in yen, buying the delta amount of stocks in the right proportions, and using the multiplier to define the total amount to be spent on shares. The dollar option is harder to hedge. It carries currency exposure as yen-denominated gains, and losses on the stocks have to be translated into dollars at a fictitious one-for-one fixed rate. The dollar option requires a "convexity" or "quanto" adjustment. to Black-Scholes in order to price it.  

A much harder non-price-based option example is an interest rate. An option on an interest rate is different from an option on a price of a bond, in which case we only need to specify the principal of the bond as the size. For options written directly on the interest rate, whether spot or forward, we cannot easily specify a "size.' We can specify a multiplier, explicitly as. $\$25$ per 1 bp of the difference between the underlying rate and the strike rate, or implicitly through a principal and day-count, e.g. $\$10,000$ times the quarterly 30/360 day-count of $^1/4$ times the rate difference in percent. In either case, the payout is linear in the rate: we get. $\$25$ per 1 bp rate change. Hedging such an option may be difficult. The rate cannot be bought or sold, only an instrument - a forward zero-coupon or coupon bond -- whose value depends on it. The option fixes a linear yield-payout relationship; the price-yield relationship for the hedged instrument. is non-linear. In some cases, this non-linearity can be ignored or handled with a "convexity' adjustment to the simple model; in many cases, however, it cannot be ignored, as it would lead to a significant mispricing and mishedging of the option. That is when we need a complicated arbitrage-free term-structure model.  

There are also cases, where the "convexity"' has to be taken into account in calculations that appear to have nothing to do with options. Examples of that include the quanto forward,. analogous to the dollar Nikkei payoff, and the forward LIBOR (FRA), when constructing the. yield curve using LIBOR-based Eurodollar futures..  
