---
tags:
  - interest_rate_derivatives
  - otc_contracts
  - payer_swaption
  - receiver_swaption
  - swaptions
aliases:
  - ATM Swaption
  - Swap Option
  - Swaption Pricing
key_concepts:
  - Cash settlement
  - Fixed-for-floating swap
  - OTC contract
  - Payer vs receiver
  - Swaption volatility cube
---

# 16.5 SWAPTIONS  

A swaption is an over-the-counter (OTC) contract that gives the buyer the right, at expiration, to enter into a fixed-for-floating interest rate swap of a prespecified maturity and strike rate. For example, a. $^{\mathfrak{s}_{2}}$ -year-5-year" or $\mathrm{~\ensuremath~{~\hat{~}{~2~}y5y}~}\$ swaption is a two-year option to enter into a five-year swap at some. prespecified strike. A receiver swaption gives the buyer the right to receive fixed and pay floating, while a payer swaption gives the buyer the right to pay fixed and receive floating.  

For presenting the pricing of swaptions, consider a $\$100$ million $2.36\%$ 5y5y receiver swaption traded on May 14, 2021. This option gives the buyer the right, in five years, on May 14, 2026, to receive $2.36\%$ and pay LIBOR on $\$100$ million for five years, that is, until May 14, 2031. To write down the value of this swaption at expiration, let $C_{5}(5,10)$ denote the five-year par swap rate, five years from today (which matures in 10 years), and let $A_{5}(5,10)$ denote the value five years from today of an annuity of $\$1$ per year, paid on each of the fixed-rate payment dates of a five-year swap starting in five years (and ending in 10 years). Then, in five years, at the expiration of the swaption, the value of receiving $2.36\%$ for five years is,.  

$$
\S100\mathrm{mm}\times[2.36\%-C_{5}(5,10)]^{+}\times A_{5}(5,10)
$$  

Inspection of the payoff (16.12) reveals that a 5y5y receiver swaption. is a put on the five-year par swap rate, five year forward. More generally, a $T$ -year- $\cdot\tau$ -year receiver swaption is a $T$ -year put option on the $\tau$ -year par swap rate, $T$ -years forward. Similarly, a $T$ -year- $\cdot\tau$ -year payer swaption is a $T$ -year call option on the $\tau$ -year par swap rate, $T$ -years forward.  

Table 16.7 applies BSM to the example of this section. As just discussed, the rate underlying the $2.36\%$ 5y5y receiver option traded on May 14, 2021, is the forward par rate on a swap from May 14, 2026, to May 14, 2031. Hence $S_{0}$ of BSM is $2.36\%$ , and the swaption of the example, with its strike. at $2.36\%$ , is ATM.4 For the $2.36\%$ 5y5y, the other parameters are clearly $T=5$ $\tau=5$ , and $K=2.36\%$ . The value of the annuity on the swap from May 14, 2026, to May 14, 2031, as of May 14, 2021, is 4.287. Finally, the market price of this receiver option on the pricing date is 3.03 per 100 notional amount or $\$3.03$ million on $\$100$ million. Appendix A16.3 shows that, when the underlying forward swap rate is normally distributed, the value of a receiver swaption per unit notional is,.  

$$
A_{0}(T,T+\tau)\times\pi^{N}(S_{0},T,K,\sigma)
$$  

where $\pi^{N}$ is once again from Appendix A16.4. Setting the market price of $\$3.03$ million equal to. $\$100$ million times (16.13), Table 16.7 shows that. the implied volatility of this swaption is. $0.793\%$  

The analogous formula for a payer swaption per unit notional is,  

$$
A_{0}(T,T+\tau)\times\xi^{N}(S_{0},T,K,\sigma)
$$  

The prices of ATM swaptions, which are by far the most commonly traded swaptions, are quoted in a matrix of either premia or implied normal volatilities. Table 16.8 is an example of the latter for US dollar swaptions as of May 14, 2021. For example, the ATM 2y10y options is priced with an implied volatility of 77.7 basis points.5 The price of the 5y5y option introduced previously is quoted at a volatility of 79.3 basis points.  

TABLE 16.7  A 5y5y Receiver Swaption per 100 Notional Amount of Swaps, as of May 14, 2021.   


<html><body><table><tr><td>Quantity</td><td>Value</td></tr><tr><td>So</td><td>2.36%</td></tr><tr><td></td><td>5</td></tr><tr><td>T</td><td></td></tr><tr><td>2</td><td>5</td></tr><tr><td>K</td><td>2.36%</td></tr><tr><td></td><td>0.793%</td></tr><tr><td>Ao(T,T +t)</td><td>4.287</td></tr><tr><td>πN(So, T,K,o) VReceiver</td><td>0.007074</td></tr><tr><td>= $100 mm ×A ×πN 0</td><td>3.03mm</td></tr></table></body></html>  

IABLE 16.8 USD ATM Swaption Normal Volatilities in Basis Points, as of May 14, 2021.   


<html><body><table><tr><td rowspan="2">Option Exp.</td><td colspan="11">Swap Tenor</td></tr><tr><td>1y</td><td>2y</td><td>3y</td><td>4y</td><td>5y</td><td>7y</td><td>10y</td><td>12y</td><td>15y</td><td>20y</td><td>30y</td></tr><tr><td>1m</td><td>12.1</td><td>18.6</td><td>34.1</td><td>45.9</td><td>57.1</td><td>64.7</td><td>70.7</td><td>71.0</td><td>71.1</td><td>71.3</td><td>71.5</td></tr><tr><td>3m</td><td>14.1</td><td>23.3</td><td>39.8</td><td>51.7</td><td>62.5</td><td>69.2</td><td>74.4</td><td>74.5</td><td>74.4</td><td>74.3</td><td>74.3</td></tr><tr><td>6m</td><td>16.7</td><td>29.4</td><td>45.5</td><td>56.0</td><td>66.4</td><td>72.0</td><td>76.3</td><td>76.2</td><td>75.8</td><td>75.6</td><td>75.3</td></tr><tr><td>1y</td><td>29.3</td><td>44.1</td><td>57.0</td><td>64.1</td><td>70.3</td><td>73.9</td><td>76.8</td><td>76.5</td><td>75.8</td><td>75.0</td><td>74.2</td></tr><tr><td>2y</td><td>59.2</td><td>68.9</td><td>73.3</td><td>76.0</td><td>77.2</td><td>77.5</td><td>77.7</td><td>77.0</td><td>75.7</td><td>74.1</td><td>72.9</td></tr><tr><td>3y</td><td>76.7</td><td>79.6</td><td>79.5</td><td>79.4</td><td>79.3</td><td>78.6</td><td>77.6</td><td>76.7</td><td>75.1</td><td>72.8</td><td>71.2</td></tr><tr><td>4y</td><td>81.4</td><td>81.2</td><td>80.7</td><td>80.2</td><td>79.8</td><td>78.4</td><td>76.6</td><td>75.5</td><td>73.7</td><td>71.3</td><td>69.4</td></tr><tr><td>5y</td><td>82.3</td><td>81.2</td><td>80.5</td><td>79.9</td><td>79.3</td><td>77.7</td><td>75.4</td><td>74.1</td><td>72.2</td><td>69.9</td><td>67.5</td></tr><tr><td>10y</td><td>73.5</td><td>72.3</td><td>71.8</td><td>71.2</td><td>70.8</td><td>69.2</td><td>66.8</td><td>65.6</td><td>63.8</td><td>61.6</td><td>59.4</td></tr></table></body></html>  

Swaption skew, discussed in the next section, refers to the fact that implied volatilities for ATM swaptions in Table 16.8 are valid only for ATM swaptions. The broader swaptions market, therefore, actually trades a volatility cube, where the third dimension represents strike, usually in 50 basis-point increments away from the forward swap rate corresponding to each entry of the swaption matrix. For a 5y5y as of May 14, 2021, with the underlying par forward swap at $2.36\%$ , a volatility cube would show volatilities for the 5y5y at higher strikes of $2.86\%$ $3.36\%$ , and so forth, and for lower strikes of $1.86\%$ $1.36\%$ , etc.  

The skew applies not only for trading swaptions that are not ATM but. also for valuing or marking existing swaptions that were initiated as ATM. options. Consider the $2.36\%$ 5y5y receiver swaption traded on May 14, 2021. The underlying swap of this swaption, from initiation to expiration,. is a $2.36\%$ swap from May 14, 2025, to May 14, 2031. As of May 14, 2021, this swap is a par swap, but over time this will no longer be the case. Say, for example, that one month later, on June 14, 2021, the rate of the forward par swap corresponding to those dates is $2.50\%$ . In that case, the $2.36\%$ receiver swaption can be characterized as a 4-year-11-month-5-year that is 14 basis points out-of-the-money. Valuing the option, therefore, requires an interpolation between the ATM and the 50 basis-point, out-of-the-money. volatilities, as well as an interpolation between the 4y5y and 5y5y option expirations. In practice, these interpolations are carried out by means of a stochastic volatility model, discussed later in this chapter.  

This section describes swaptions as if they are physically settled, mean-. ing that, at expiration, the counterparties enter into a swap at the appropriate rate and maturity. In fact, however, swaptions in the United States are almost always cash settled and, in Europe, can be physically or cash settled. In the United States, the cash settlement is found by multiplying the. appropriate annuity factor, evaluated along the swap curve, by the difference between the par rate and the strike, in the case of payers, or the difference between the strike and the par rate, in the case of receivers. In Europe, the annuity factor is computed at a flat rate equal to the appropriate par swap. rate, which can lead to very minor valuation differences between the two forms of settlement. As a final note, for some swaptions in Europe, the premium is paid at the expiration date rather than the trade date, which changes. valuations accordingly.  
