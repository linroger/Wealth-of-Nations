---
tags:
  - black_model
  - bond_price_options
  - european_swaptions
  - option_pricing
  - yield_curve
aliases:
  - Caps/Floors
  - European Swaptions
  - Options on Bond Prices
key_concepts:
  - Black model
  - Bond price options
  - Forward bond price
  - Price volatility
  - Yield curve construction
---

# 6.1  BLACK MODELS FOR BOND PRICE OPTIONS, CAPS/FLOORS, AND EUROPEAN SWAPTIONS  

In this section, we tackle the cases where most of the complications of arbitrage-free yield curve construction can be ignored. This is because these issues cause only second-order errors in the discounting and not first-order errors in the diffusion of the underlying variable. The idea is to decouple the primary driver of the value of the option - a long bond price or a swap rate - from the short-term discounting rate, and in effect treat the primary driver like the diffused stock price in the Black-Scholes, while constructing a correctly bootstrapped, but constant, discounting curve. This necessarily implies that the connection between the short and long rates in the yield curve is broken..  

# 6.1.1Options on Bond Prices  

Options on bond prices are typically quoted over-the-counter for short expiries or are embedded.   
in bond and swap contracts. A one-time callable or putable bond can be viewed as a package.   
of a bullet bond and a call option held by the issuer or a put option held by the buyer. In either.   
case, one party has the right to buy/sell the bond at a fixed strike price expressed in dollars. A European swaption is a very similar contract dressed in swap language..  

The main model for dealing with short expiry options on long-term bond is the forward formulation of the Black-Scholes introduced as the Black model of Chapter 5. We assume that prior to using the model, we bootstrapped the yield curve using the methods of Chapter 2 - that is, we have a set of spot discount factors $d f(0,T)$ to any date $T$ in the future that allow us to discount any cash flows on those dates. The prices of calls and puts on bond prices are:  

$$
\begin{array}{l}{C=[F N(d_{1})-K N(d_{2})]d f(0,T)}\ {P=[K N(-d_{2})-F N(-d_{1})]d f(0,T)}\ {\mathrm{with}~d_{1}=\frac{\ln\frac{K}{F}+(\sigma^{2}/2)T}{\sigma\sqrt{T}}\mathrm{and}d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

where $F$ is the forward price of the bond on the option expiry date, and. $\sigma$ is the volatility of the price of the bond, also known as the price volatility of the bond to distinguish it from the yield volatility. The main assumption here is that the forward price (not spot price) of the bond. has a constant volatility.  

Consider a 6-month call option on a $5\%$ year $5\%$ semi-annual coupon bond. For simplicity assume that the yield curve out to 1 year is flat at. $4\%$ quarterly compounded. The bond. currently trades at 103 and the strike is 102.50. There are three issues to consider:  

In order to compute the forward price of the bond at the expiry of the option, we need to present value the coupon cash flows between now and expiry.. The forward bond price volatility is assumed constant; yet it is clear that the price volatility. will decrease over the life of the bond to zero at maturity. Interest rate volatilities are often quoted in terms of yield, not price volatilities; a yield volatility is the standard deviation of the percentage changes in yields i.e. y/ys.  

Let us tackle each issue. First, to compute the forward price of the bond (forward to option expiry), we can present-value all the coupons that the bond will throw off between now and the option expiry to today, net the present value against the spot bond price, and then future-value the bond to the option expiry using the cash-and-carry principle.  

Our semi-annual bond will pay one coupon cash flow equal to $100\times5\%/2=2.5$ one quarter from today. The PV of that is $\begin{array}{r}{2.5/\left(1+\frac{0.{\dot{0}}4}{4}\right)=2.475}\end{array}$ We subtract that from the spot price of the bond and then future value the net to the option expiry date. The whole expression is:  

$$
F=(S-C F_{\tau}\times d f(0,\tau))\times\frac{1}{d f(0,T)}
$$  

or  

$$
F=(103-2.475)\times\left(1+{\frac{0.04}{4}}\right)^{2}=102.545
$$  

We sweep the issue of the declining price volatility of the bond under the carpet. While it is true that at maturity the price volatility is zero, we are relying on the fact that the option expiry is short relative to the maturity of the bond and we can ignore this effect. Lastly, the quick and dirty conversion of yield volatilities to price volatilities is accomplished easily by multiplying the yield volatility by the modified duration of the bond and the current level of the yield. This. follows from the application of Ito calculus to the derivation of the stochastic process for the bond price, given the yield process and the observation that the percentage change in the bond. price is approximately equal to the modified duration times the change in yield. Hence the conversion expression is:  

$$
\sigma=M o d D\times y t m\times\sigma_{y t m}
$$  

where ModD is the modified duration of the bond at the option expiry (forward duration), $y t m$ is the yield-to-maturity on the bond at option expiry (forward yield), and. $\sigma_{y t m}$ is the yield volatility of the forward bond price. If the forward yield is. $4.9\%$ , the yield volatility is $25\%$ and the forward modified duration is 4.2, then the price volatility input into the model is:  

$$
\sigma=4.2\times0.049\times25\%=5.145\%
$$  

The call value using the Black formula is:  

$$
\begin{array}{r l}&{C=[102.545\times N(d_{1})-102.5\times N(d_{2})]d f(0,T)=1.467}\ &{\mathrm{with}d_{1}=\frac{\ln\frac{102.545}{103}+(0.05145^{2}/2)0.5}{0.05145\sqrt{0.5}}=-0.1035,\quad d_{2}=d_{1}-0.05145\sqrt{0.5}=-0.1}\ &{\mathrm{and}N(d_{1})=0.4588,\quad N(d_{2})=0.4444,\quad d f(0,0.5)=1/\left(1+\frac{0.04}{4}\right)^{2}=0.9803}\end{array}
$$  

The call is worth $1.47\%$ of the principal of the bond, and in order to delta hedge the dealer will buy $45.88\%$ of the bond's face value.  

# 6.1.2 Cap and Floor Definitions  

Many interest rate option structures are not options expiring on a single date, but rather packages of optionlets, each expiring on a single date. They are constructed to mimic the periodic cash flows of bonds and swaps and they borrow the language of bonds and swaps like the principal or face value and day-count applied to interest accrual calculations.  

Caps and floors are packages of options, looking like calls and puts, correspondingly, on the same underlying short-term interest rate with sequential expiry dates. The vast majority of caps and floors have the 3-month LIBOR as their underlying rate. The expiry dates on. the options, called caplets or floorlets, follow a quarterly or semi-annual schedule, typically matched to the maturity of the underlying rate, starting with immediate expiry and ending with the last expiry date, being one period prior to the stated maturity of the cap. For example, a. 5-year cap on 3-month LIBOR struck at $4.5\%$ consists of 20 caplets with expiries of 0 months,. 3 months, 6 months, 9 months, and so on, all the way to 57 months. The payouts on the. options are delayed by 3 months, i.e. made in arrears; the last payout is on the maturity date of the cap, i.e. in 60 months. The payoff on each caplet is equal to the greater of zero and the difference between the underlying LIBOR rate on the expiry date and the strike rate of. $4.5\%$ times the day-count fraction on an Act/360 basis for the period covered by the LIBOR rate. A floor is a "put' equivalent of a cap; that is, the payoff of each floorlet is equal to the greater. of zero and the difference between the strike rate of. $4.5\%$ and the underlying LIBOR rate on. the expiry date, times the same day-count fraction. All these details are designed to match the swap market convention, since caps and floors are viewed as natural supplements to swaps.  

Let us illustrate, in Table 6.1, a $4.5\%$ cap and a $4.5\%$ floor by assuming some hypothetical (unknown up front, except for the first one) LIBOR rates (in column 2) for future option expiry dates (called set dates), and day-counts for the subsequent 3-month period until the pay dates. The principal amount is $\$100$ million.  

The buyer of the cap benefits if spot LIBOR rates on future dates exceed $4.5\%$ . The buyer of the floor benefits if spot LIBOR rates on future dates are below $4.5\%$ . The first caplet and floorlet may be deleted, unless specifically stated to the contrary, i.e. technically we have  

Table 6.15-year $4.5\%$ $\$100$ million cap and floor on 3-month LIBOR   


<html><body><table><tr><td colspan="8">100 million (dates in months from today)</td></tr><tr><td>Set date</td><td></td><td colspan="3">Cap</td><td colspan="3">Floor</td><td></td></tr><tr><td></td><td>LIBOR</td><td>max(L -K, 0)</td><td>Days</td><td>Payout</td><td>max(K -L, 0)</td><td>Days</td><td>Payout</td><td>Pay date</td></tr><tr><td>0</td><td>4.50</td><td>0</td><td>91</td><td>0</td><td>0</td><td>91</td><td>0</td><td>3</td></tr><tr><td>3</td><td>4.20</td><td>0</td><td>91</td><td>0</td><td>0.3</td><td>91</td><td>75,833</td><td>6</td></tr><tr><td>6</td><td>4.81</td><td>0.31</td><td>92</td><td>79,222</td><td>0</td><td>92</td><td>0</td><td>9</td></tr><tr><td>9</td><td>5.20</td><td>0.7</td><td>90</td><td>175,000</td><td>0</td><td>90</td><td>0</td><td>12</td></tr><tr><td>12</td><td>5.40</td><td>0.9</td><td>89</td><td>222,500</td><td>0</td><td>89</td><td>0</td><td>15</td></tr><tr><td>15</td><td>5.55</td><td>1.05</td><td>91</td><td>265,417</td><td>0</td><td>91</td><td>0</td><td>18</td></tr><tr><td>18</td><td>5.83</td><td>1.33</td><td>92</td><td>339,889</td><td>0</td><td>92</td><td>0</td><td>21</td></tr><tr><td>21</td><td>6.21</td><td>1.71</td><td>91</td><td>432,250</td><td>0</td><td>91</td><td>0</td><td>24</td></tr><tr><td>24</td><td>6.43</td><td>1.93</td><td>90</td><td>482,500</td><td>0</td><td>90</td><td>0</td><td>27</td></tr><tr><td>27</td><td>6.11</td><td>1.61</td><td>92</td><td>411,444</td><td>0</td><td>92</td><td>0</td><td>30</td></tr><tr><td>30</td><td>5.73</td><td>1.23</td><td>91</td><td>310,917</td><td>0</td><td>91</td><td>0</td><td>33</td></tr><tr><td>33</td><td>5.32</td><td>0.82</td><td>91</td><td>207,278</td><td>0</td><td>91</td><td>0</td><td>36</td></tr><tr><td>36</td><td>5.17</td><td>0.67</td><td>89</td><td>165,639</td><td>0</td><td>89</td><td>0</td><td>39</td></tr><tr><td>39</td><td>4.85</td><td>0.35</td><td>92</td><td>89,444</td><td>0</td><td>92</td><td>0</td><td>42</td></tr><tr><td>42</td><td>4.62</td><td>0.12</td><td>91</td><td>30,333</td><td>0</td><td>91</td><td>0</td><td>45</td></tr><tr><td>45</td><td>4.33</td><td>0</td><td>91</td><td>0</td><td>0.17</td><td>91</td><td>42,972</td><td>48</td></tr><tr><td>48</td><td>4.02</td><td>0</td><td>89</td><td>0</td><td>0.48</td><td>89</td><td>118,667</td><td>51</td></tr><tr><td>51</td><td>3.78</td><td>0</td><td>92</td><td>0</td><td>0.72</td><td>92</td><td>184,000</td><td>54</td></tr><tr><td>54</td><td>3.66</td><td>0</td><td>91</td><td>0</td><td>0.84</td><td>91</td><td>212,333</td><td>57</td></tr><tr><td>57</td><td>3.21</td><td>0</td><td>90</td><td>0</td><td>1.29</td><td>90</td><td>322,500</td><td>60</td></tr></table></body></html>  

19 optionlets. Bought caps can be viewed as protection against interest rate increases, while floors can be viewed as protection against interest rate declines..  

The at-, in-, and out-of-the money terminology for caps and floors is a little different from stock options; there, we usually had only one option, here we have many, bought as a package. A cap or floor is said to be (struck) at-the-money if the strike price is chosen to be the swap rate of the same maturity as the maturity of the cap. Correspondingly, one can talk about in-the-money or out-of-the-money caps and floors depending on whether their strike is greater or less than the swap rate. The statement applies on an aggregate basis, not to individual optionlets. If, in our illustration, the 5-year swap rate on an $\mathrm{Act}/360$ basis is $5\%$ , then our cap would be called in-the-money (as the swap rate is higher than the strike), even though based on today's LIBOR the caplets are really at-the-money, and on a forward basis some caplets may be out-of-the-money. Our floor would be out-of-the-money as the swap rate is above the strike.  

# 6.1.3 Relationship of Caps and Floors to FRAs and Swaps  

We have shown that a swap is a package of FRAs dissected along the set dates. A 5-year. quarterly swap can be viewed as a package of 20 FRAs with consecutive maturities. The start date of each FRA matches the set date of the swap, and the end date of the FRA matches the pay date of the swap corresponding to the next set date. In a 5-year quarterly swap, the first FRA is $0\times3$ , the next $3\times6$ , and so on. The last one is $57\times60$  

Instead of dissecting swaps along set and pay dates, we can dissect them along rate levels. A pay-fixed swap can be viewed as a long cap and a short floor. And each constituent FRA can be viewed as a long caplet and short floorlet position. Suppose we buy a $\$100$ million 5-year cap struck at $4.5\%$ and sell a $\$100$ million 5-year floor struck at $4.5\%$ . When LIBOR exceeds the strike, the payoff on the floor is zero and the payoff on the cap is equal to LIBOR minus the fixed rate of $4.5\%$ . This is equivalent to a receipt of LIBOR and payment of fixed $4.5\%$ When LIBOR is below the strike, the payoff on the cap is zero and the liability on the floor is equal to the fixed rate of $4.5\%$ minus LIBOR. This is equivalent to a receipt of LIBOR and payment of fixed $4.5\%$ . That is, no matter where LIBOR sets, the cash flows are equivalent to those of a swap with a fixed rate of $4.5\%$ . Table 6.2 summarizes the situation.  

Each row is a dissection of an FRA into a caplet and a floorlet. The sum of the rows is equal. to the swap. Each column group is a dissection of the swap into a long cap and a short floor. The net receipt on the swap is identical to the net of the cap and floor positions..  

# Put-Call Parity for Caps/Floors  

# Cap struck at K - Floor struck at $K=S$ wap with fixed rate. $K$  

Suppose that we do not pick the strike rate randomly, but instead we select it in such a way that the premium we pay on the cap is equal to the premium we receive on the floor. That is, we have no net cash flow up front. What swap would have no net cash flow up front? A par swap or an on-market swap. We can thus conclude the following.  

$$
C a p(w i t h K=S w a p r a t e)-F l o o r(w i t h K=S w a p r a t e)=P a r s w a p
$$  

Recall the put-call parity for stocks and the analogous relationship for stock options struck at the forward. As implied volatilities increased, the values of the calls and puts, both struck at the forward, increased by the same amount as their payoff was still equivalent to the forward. The same is true for caps and floors. In order to conform to the constraint of no-arbitrage, if prices of caps struck at the swap rate increase (due to implied volatility rise), the prices of. floors struck at the swap rate must also increase by the same amount. The pricing assumptions do not change the payout on the combined position, which is still equivalent to an on-market swap. These considerations are the basis for the in-the-moneyness language for caps and floors. as defined above.  

One can construct swaps out of caps and floors, and vice versa. A cap can be viewed as. a combination of a pay-fixed swap and a long floor position. A floor can be viewed as a combination of a long cap position and a receive-fixed swap..  

# 6.1.4 A Cap Application  

Bond issuers often combine a long over-the-counter cap position with a floating rate bond sold to investors. This ensures that the coupon payments on the bond do not exceed a certain desired level.  

Suppose a company issues a 5-year bond paying quarterly floating coupons equal to LIBOR. The company also buys from a dealer a cap struck at $4.5\%$ . If LIBOR on any coupon set date. exceeds $4.5\%$ , the company's net obligation will stay at. $4.5\%$ . If LIBOR on any coupon date is below $4.5\%$ , the company takes advantage of the floating nature of the issue, and pays less than $4.5\%$ . Its net obligation is thus the lower of the two, LIBOR or $4.5\%$ . The hypothetical cash flows are summarized in Table 6.3 and illustrated graphically in Figure 6.1.  

<html><body><table><tr><td>0 -75,833 79,222 175,000 222,500 265,417 339,889 432,250 482,500 411,444 310,917 207,278 165,639 89,444 30,333 -42,972 Net 1,137,500 1,137,500 1,150,000 1,125,000 1,112,500 1,137,500 1,150,000 1,137,500 1,125,000 1,150,000 1,137,500 1,137,500 1,112,500 1,150,000 1,137,500 1,137,500 Swap Pay 1,137,500 1,061,667 1,229,222 1,300,000 1,335,000 ,402,917 ,489,889 1,569,750 1,607,500 1,561,444 1,448,417 ,344,778 1,278,139 1,239,444 1,167,833 1,094,528 Receive Pay date 3 6 9 2 5 8 忆 72 30 3 6 39 2 5 -75,833 0 0 0 0 0 0 0 0 0 0 0 0 0 -42,972 Payout Short floor (0 ^7-y)xeu 3 0 0 0 0 0 0 0 0 0 0 0 0 0 79,222 175,000 222,500 265,417 339,889 432,250 482,500 411,444 310,917 207,278 165,639 89,444 Payout 30,333 Long cap max(L -K, 0) 0.31 0.7 1.05 1.33 1.71 1.93 1.61 1.23 0.82 0.67 0.35 0.9 0.12 0 0 Days 9 9 92 9 9 2 9 9 2 9 9 2 9 LIBOR 4.50 4.20 4.81 5.20 5.40 5.55 5.83 6.21 6.43 6.11 5.73 5.32 5.17 4.85 4.62 Set Date</td></tr></table></body></html>  

![](857a00f8034c9206b99a8e561d63a605d97bc10f928eee1aab204317c6f2b748.jpg)  
Figure 6.1  A floating-rate bond insured with a $4.5\%$ cap  

For months 9 to 45, when LIBOR exceeds $4.5\%$ , the company effectively pays. $4.5\%$ rate times the appropriate day-count..  

A mirror-image application of a long floor position is on the investment side. Suppose a. portfolio manager owns a floating rate bond and fears that, as rates come down, her income from the bond will decline. She can purchase a floor struck at the desired level to maintain her income at or above that level.  

Table 6.3 5-year $\$100$ million floating rate bond and $4.5\%$ cap   


<html><body><table><tr><td colspan="8">(dates in months from today)</td></tr><tr><td colspan="6"></td><td colspan="3"></td></tr><tr><td>Set date</td><td>LIBOR</td><td>Days</td><td>max(L-K, 0)</td><td>Payout</td><td>Floating bond Coupon</td><td>Pay date</td><td>Net</td><td></td></tr><tr><td>0</td><td>4.50</td><td>91</td><td>0</td><td>0</td><td>-1,137,500</td><td>3</td><td></td><td>-1,137,500</td></tr><tr><td>3</td><td>4.20</td><td>91</td><td>0</td><td>0</td><td>-1,061,667</td><td>6</td><td></td><td>1,061,667</td></tr><tr><td>6</td><td>4.81</td><td>92</td><td>0.31</td><td>79,222</td><td>-1,229,222</td><td></td><td>9</td><td>-1,150,000</td></tr><tr><td>9</td><td>5.20</td><td>90</td><td>0.7</td><td>175,000</td><td>-1,300,000</td><td></td><td>12</td><td>-1,125,000</td></tr><tr><td>12</td><td>5.40</td><td>89</td><td>0.9</td><td>222,500</td><td>-1,335,000</td><td></td><td>15</td><td>-1,112,500</td></tr><tr><td>15</td><td>5.55</td><td>91</td><td>1.05</td><td>265,417</td><td>-1,402,917</td><td></td><td>18</td><td>-1,137,500</td></tr><tr><td>18</td><td>5.83</td><td>92</td><td>1.33</td><td>339,889</td><td>-1,489,889</td><td></td><td>21</td><td>-1,150,000</td></tr><tr><td>21</td><td>6.21</td><td>91</td><td>1.71</td><td>432,250</td><td>-1,569,750</td><td></td><td>24</td><td>-1,137,500</td></tr><tr><td>24</td><td>6.43</td><td>90</td><td>1.93</td><td>482,500</td><td>-1,607,500</td><td></td><td>27</td><td>-1,125,000</td></tr><tr><td>27</td><td>6.11</td><td>92</td><td>1.61</td><td>411,444</td><td>-1,561,444</td><td></td><td>30</td><td>-1,150,000</td></tr><tr><td>30</td><td>5.73</td><td>91</td><td>1.23</td><td>310,917</td><td>-1,448,417</td><td></td><td>33</td><td>-1,137,500</td></tr><tr><td>33</td><td>5.32</td><td>91</td><td>0.82</td><td>207,278</td><td>-1,344,778</td><td></td><td>36</td><td>-1,137,500</td></tr><tr><td>36</td><td>5.17</td><td>89</td><td>0.67</td><td>165,639</td><td>-1,278,139</td><td></td><td>39</td><td>-1,112,500</td></tr><tr><td>39</td><td>4.85</td><td>92</td><td>0.35</td><td>89,444</td><td>-1,239,444</td><td></td><td>42</td><td>-1,150,000</td></tr><tr><td>42</td><td>4.62</td><td>91</td><td>0.12</td><td>30,333</td><td>-1,167,833</td><td></td><td>45</td><td>-1,137,500</td></tr><tr><td>45</td><td>4.33</td><td>91</td><td>0</td><td></td><td>0 -1,094,528</td><td></td><td>48</td><td>-1,094,528</td></tr><tr><td>48</td><td>4.02</td><td>89</td><td>0</td><td></td><td>0 -993,833</td><td></td><td>51</td><td>-993,833</td></tr><tr><td>51</td><td>3.78</td><td>92</td><td>0</td><td></td><td>0 -966,000</td><td></td><td>54</td><td>-966,000</td></tr><tr><td>54</td><td>3.66</td><td>91</td><td>0</td><td></td><td>0 -925,167</td><td></td><td>57</td><td>-925,167</td></tr><tr><td>57</td><td>3.21</td><td>90</td><td>0</td><td></td><td>0</td><td>-802,500</td><td>60</td><td>-802,500</td></tr></table></body></html>  

# 6.1.5 Pricing of Caps and Floors  

The pricing of caps and floors follows the standard Black-Scholes model, or the Black version thereof, with the following enhancements:.  

Prior to using the model the discounting curve has been bootstrapped and we have a set of. spot discount factors $d f(0,T)$ to any date $T$ in the future that allow us to discount any cash. flows on those dates.   
Each caplet/floorlet is priced separately with forward LIBOR playing the role of the forward stock/currency price in the Black model and a volatility input is applied to it.   
While the caplets/floorlets are priced separately, they all depend on the evolution of the. same LIBOR rate; therefore the volatility structure input into pricing must be self-consistent and, in particular, not allow for negative forward volatilities..  

The model is not arbitrage free. We have a fixed yield curve with clearly defined constant LIBOR forwards to future set dates. Yet we diffuse the LIBOR rates with a volatility input, i.e. assume that they are stochastic, while at the same time we discount the cash flows from the pay dates to today using the constant discount factors. The valuation formula for caplet setting on date $T$ is:  

$$
\begin{array}{r l}&{C=F a c e\times[F N(d_{1})-K N(d_{2})]\times\displaystyle\frac{d a y s}{360}\times d f(0,T+3m o n t h s)}\ &{P=F a c e\times[K N(-d_{2})-F N(-d_{1})]\times\displaystyle\frac{d a y s}{360}\times d f(0,T+3m o n t h s)}\ &{\mathrm{with~}d_{1}=\displaystyle\frac{\ln\frac{F}{K}+(\sigma^{2}/2)T}{\sigma\sqrt{T}}\mathrm{~and~}d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

where $F$ is the forward 3-month LIBOR from set date $T$ over the subsequent 3 months, F ace is the notional principal of face value of the cap/floor, days/360 is the day-count for the interest payment period from the forward set date $T$ to the payment date for that period 3 months later which is also the next set date, and $d f(0,T+3m o n t h s)$ is the discount factor from today to the pay date of the caplet/floorlet which is 3 months after the set date. For example, to value the third of the 20 caplets in the 5-year cap, we would input $F a c e=\$100$ million, days/360 might be equal to 91/360, if there are 91 days in the interest accrual period between 6 months and 9 months from today, and the discount factor $d f(0,T+3$ months) would cover the period from today to the pay date of the caplet in 9 months. The volatility input would be appropriate for diffusing LIBOR over the next 6 months and the time input would be $\begin{array}{r}{T=\frac{1}{2}}\end{array}$ to correspond to the 6 months to the LIBOR set time. The $\sigma$ input is always entered on an annualized basis.  

Cap/floor implied volatilities are often quoted as flat volatilities. A dealer may quote a $24\%$ volatility for a 5-year cap and $27\%$ volatility for a 3-year cap with the same strike. That is, if. we apply $24\%$ as input into each of the 20 caplet-pricing models spanning 5 years and. $27\%$ as input into each of the 12 caplet-pricing models spanning 3 years we will get the quoted price in basis points of the face value of the caps. Yet the 5-year cap is the 3-year cap plus 8 more caplets spanning years 4 and 5. A simple arbitrage rule is that a longer expiry cap or floor must be more expensive than a shorter expiry cap or floor with the same strike. So, a 5-year cap costs more than a 3-year cap. But the flat volatility quoted on the 5-year cap may be lower than that on the 3-year cap, just not arbitrarily lower..  

Flat volatilities are like yields-to-maturity on coupon bonds. They are "averages" of individ-. ual caplet volatilities that produce the same overall price. By observing ever longer maturity caps and floors, we can bootstrap them to produce individual caplet volatility input called spot volatilities. We observe 6-month, 1-year, 2-year, etc., caps/floors and bootstrap a 3-month caplet volatility, then 6- and 9-month volatilities, then 12-, 15-, 18-, and 21-month volatilities, and so on. These spot caplet volatilities typically follow a humped pattern, first rising out to. 1-2 years and then slowly declining.  

The spot volatilities of caplets/floorlets must follow certain logic rules. Suppose we bootstrap the volatility for the eight caplet setting in 21 months as $29\%$ and the volatility for the ninth caplet setting in 24 months as $18\%$ . Let us not forget that we are diffusing the same 3-month LIBOR in each caplet-pricing model. By the simple propagation rule for a log-normal variable with a deterministic volatility schedule, we have the following relationship for the spot 24-month volatility as a function of the spot 21-month volatility and the forward volatility spanning the 3 month period from 21 to 24 months:  

$$
\sigma_{0-24}\sqrt{\frac{24}{12}}=\sigma_{0-21}\sqrt{\frac{21}{12}}+\sigma_{21-24}\sqrt{\frac{3}{12}}
$$  

Substituting $\sigma_{0-24}=0.18$ and $\sigma_{0-21}=0.29$ , we get $\sigma_{21-24}=-0.258$ . Even in the risk-. neutral world, LIBOR volatility input cannot be negative. The relationship between the spot and forward caplet/floorlet volatilities which disallows negative forward volatilities puts constraints on the volatility bootstrap process. In our example, perhaps we bootstrapped the 21-month volatility from the flat volatilities to be too high at. $29\%$ , and that is why we cannot fit the price of the 24-month caplet..  

# 6.1.6 European Swaption Definitions  

Swaptions (swap options) are options to enter into a swap. Unlike a cap which consists of a series of caplets with sequential expiry dates, a swaption has one expiry date and is exercised once. Upon exercise, the holder of a swaption will enter into a swap with multiple pay and receive cash flows. Exercise can be European-style (once at expiry only), American style (once any time prior to or on the expiry date), or Bermudan style (once on any swap set date prior to or on the expiry date). For example, a 3-into-7 $\$100$ million European call swaption struck at. $5\%$ , gives the owner the right to receive fixed $5\%$ against floating LIBOR, on a. $\$100$ million 7-year swap. If the option is exercised on the expiry date, which is 3 years from today, the swap would start on that day and end 7 years later. The same swaption can be referred to as 3-year/10-year-final swaption to imply that the exercise right is in 3 years and the final maturity of the swap is in 10 years from today. A Bermudan or American version would be exercisable between today and 3 years from today, not just 3 years from today, and the swap. would start immediately at exercise and end 10 years from today. The "3-into-. $\cdot7^{\cdot\cdot}$ language is rarely used with American and Bermudan options; the "3-year/10-year-final' language is preferable (if the option is exercised in 2 years, the swap will last 8 years)..  

Calls are options to receive (fixed) on the swap; puts are options to pay (fixed) on the. swap. The call/put terminology corresponds to the view of swaps as exchanges of bonds. A receive-fixed swap can be thought of as a bought fixed rate bond and a sold floating rate bond, or a bought fixed rate bond financed by a revolving loan. So a call swaption is like an option to buy a fixed rate bond, just as a call is an option to buy a stock. A put swaption is an option to sell a fixed rate bond, i.e. the option to pay a fixed rate on an obligation, and to receive a. floating financing rate.  

![](cd699c492e0db903bec2e57a7f16d657c5ef1dd5524234c7793fa57c2ce4b452.jpg)  
Years 0-5  

![](1ea7a5323c15b440490f38806070cf9deb74aebcfe87fb3d6740206e0119fb7a.jpg)  
Years 5-10, if call exercised   
Figure 6.2 A European call swaption to cancel a swap  

# 6.1.7 Options to Cancel Swaps  

A swaption can be packaged with a swap to bestow the right to cancel the swap. Suppose we pay a fixed rate of $4.5\%$ on a 10-year quarterly swap; we receive 3-month LIBOR. If. our swap counterparty sells us a 5-into-5 call swaption struck at 4.5, the call gives us the right to receive $4.5\%$ on a 5-year swap starting 5 years from today. However, if we exercise. the call, then we will exactly offset the remaining cash flows on the existing 10-year swap (Figure 6.2).  

The call swaption, which we defined as the right to enter a swap to receive fixed, can also be defined as the right to cancel a pay-fixed swap. The "call' language conforms to the call provisions on fixed coupon bonds. Analogously, the "put' notion for swap options to cancel corresponds to the right of the fixed coupon bondholders to put the bonds back to the issuer at par.  

# 6.1.8 Relationship of Swaptions to Forward Swaps  

From the above construction, one should also be able to see the following put-call parity relationship:  

Put-Call Parity for European Swaptions  

# Call Swaption -- Put Swaption $=$ Forward Swap  

Suppose we buy a 5-into-5 call swaption struck at $4.5\%$ and sell a 5-into-5 put swaption struck at $4.5\%$ . If 5-year swap rates are low in 5 years, say at $3\%$ , then we will exercise our call right to receive fixed $4.5\%$ (above market). The holder of the put we sold will not exercise.  

Alternatively, if 5-year swap rates are high in 5 years, say at. $6\%$ , then the holder of the put we. sold will exercise his right to pay fixed. $4.5\%$ (below market). We will not exercise our call. His exercise decision will force us to receive fixed. $4.5\%$ . Thus no matter what swap rates are. in 5 years, we will enter into a 5-year receive-fixed swap at that time. Viewed from today, this is a forward swap agreement. It starts at a future known date (5 years) and ends at a future known date (10 years), and the fixed rate. $(4.5\%)$ on it is agreed today.  

In addition, if instead of. $4.5\%$ we choose the strike rate in such a way that the premium. paid for the call equals that received for the put, then the sure forward swap will be arranged at no cost to either party, i.e. it will be a par forward swap..  

This relationship will be true no matter what the level of implied volatilities used by dealers as input into their pricing models, because the static arbitrage constraint will not change..  

Swaptions can be synthesized from forward swaps and other swaptions. A call is equivalent to a forward receive-fixed swap and a put swaption. A put is equivalent to a forward pay-fixed swap and a call swaption.  

Swaptions can also be viewed as one-time options on long (swap) rates. Note that, in the above discussion, we decided that the call holder will exercise when future swap rates are lower than the strike. This guarantees that the present value of the swap he chooses to exercise into is positive  that is, he has a positive payoff. This is true because the LIBOR leg part of the swap (equivalent to the floating rate bond) always prices (present-values) to par, and the positive PV will come from the discounted value of the differences between the strike and the actual lower fair swap rate, i.e. the bond with a fixed coupon equal to the strike will price above par. If the fair rate were equal to the strike, the fixed bond with a coupon equal to the strike would also price to par. So the payoff of the call can be viewed as the difference between the strike and the fair swap rate times the day-count-corrected annuity factor, or sum of discount factors, for all swap payment dates.  

$$
\begin{array}{r}{C a l l=m a x\left[0,K-S w a p r a t e\right]\times A n n u i t y f a c t o r}\ {P u t=m a x\left[0,S w a p r a t e-K\right]\times A n n u i t y f a c t o r}\end{array}
$$  

Swaptions and caps and floors are also related, but not so simply. Both types of options. are ways of dissecting swaps, i.e. share the risk of the swap with other players. Caps and floors can be forward starting to make them look identical to swaptions in terms of start and end dates. But caps and floors dissect swaps on the floating side, while swaptions do so on the fixed side. Caps and floors are packages of several mini-options on each swaplet (FRA), while swaptions are one-time options on the entire swap. The two are related for the following reason. The long (forward) swap rate, which is the underlying rate for the swaption, is a package of forward starting swaplets (FRAs). That one rate can be exchanged costlessly into a series of short-term fixed rates (equal to FRA rates for the respective pay. periods), or further into unknown floating rate payments (as on-market FRAs cost noth-. ing to enter into). A long cap and short floor position is equivalent to those floating rate payments.  

Because of these interrelationships between long and short rates, one can claim that the. prices of swaptions and caps and floors are interrelated (as are their implied volatilities). The modeling of these relationships is extremely complex..  

# 6.1.9 Pricing of European Swaptions  

The pricing of European call and put swaptions follows the standard Black-Scholes model, or the Black version thereof, with the following enhancements:.  

Prior to using the model the discounting curve has been bootstrapped and we have a set of spot discount factors $d f(0,T)$ to any date $T$ in the future that allow us to discount any cash flows on those dates. That same yield curve bootstrap produces all forward discount factors $d f(t,T)$ that allow us to discount any cash flows from future dates $T$ back to prior future dates $t$ That same yield curve bootstrap produces the forward swap rate $F(T,M)$ known today from the swaption expiry date $T$ to the final swap maturity date $M$   
The one-time exercise option is priced with the forward swap rate $F(T,M)$ playing the role of the forward stock/currency price in the Black model and an annual volatility input is applied to that forward swap rate  

The model is not arbitrage free. We have a fixed yield curve with clearly defined constant LIBOR forwards to future set dates and constant forward swap rates from any date to any subsequent future date. Yet we diffuse the one forward swap rate. $F(T,M)$ with a volatility input, i.e. assume that it is stochastic, while at the same time we discount the cash flows from the pay dates to today using the constant discount factors. The valuation formula for a European swaption expiring on date $T$ and with a final swap date $M$ is:  

$$
{\begin{array}{l}{C=F a c e\times[F(T,M)\times N(d_{1})-K\times N(d_{2})]\times A F(T,M)\times d f(0,T)}\ {P=F a c e\times[K\times N(-d_{2})-F(T,M)\times N(-d_{1})]\times A F(T,M)\times d f(0,T)}\ {d_{1}={\frac{\ln{\frac{F}{K}}+(\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}\quad{\mathrm{and}}\quad d_{2}=d_{1}-\sigma{\sqrt{T}}}\end{array}}
$$  

where $F(T,M)$ is the forward swap rate from the expiry date $T$ to the final swap maturity date $M$ , F ace is the notional principal of face value of the swaption, $A F(T,M)$ is the annuity factor for $\$1$ received/paid as the interest payment on the entire fixed leg of the forward swap from date $T$ to date $M$ , and $d f(0,T)$ is the discount factor from today to the swaption expiry date.  

Let us define all the inputs through an example and assume that the yield curve is flat at $4.5\%$ semi-annually compounded. For a 5-into-5-year $\$10$ million call swaption struck at $4.5\%$ , we set $T=5$ and $M=10$ From the yield curve, we compute a zero-PV forward swap rate $F(T,M)=4.5\%$ If the swap into which the swaption is exercisable follows the standard US convention, then upon exercise in 5 years we will receive fixed $4.5\%$ semi-annually on a 30/360 basis and pay quarterly LIBOR flat on an Act/360 basis for the next 5 years. The discount factor is  

$$
d f(0,5)={\frac{1}{\left(1+{\frac{0.045}{2}}\right)^{10}}}=0.80051.
$$  

The annuity factor ignores the floating leg and is computed as the present value of. $\$1$ On the fixed leg's interest payment dates. In general, the formula for the annuity factor is:  

$$
A F(T,M)=\sum_{k=n_{T}}^{n_{M-1}}d a y f r a c{(k,k+1)}\times d f(T,t_{k+1})
$$  

We take day-count fractions for each fixed coupon period. $(\approx1/2)$ and multiply them by the forward discount factors from the fixed coupon pay dates $(5^{1}/2$ , 6, $6{}^{1}/2$ , ..., 10 years) to the. swaption expiry date (5 years)..  

If the convention were different from 30/360 we might need to adjust it for the fact that $\$1$ of interest might be multiplied by an Act/360 or Act/Act fraction not equal to $^1/2$ . Here we can use a simple textbook annuity formula divided by 2 to get.  

$$
A F(T,M)=\frac{1}{2}\left(\frac{1}{0.045/2}-\frac{1}{(0.045/2)(1+0.045/2)^{10}}\right)=8.8662/2=4.4331
$$  

This is a forward price value of a basis point (PVBP). The last input is the volatility which we assume we imply from other observed swaptions.  

The theory of why the Black model, as opposed to a more complicated arbitrage-free interest rate model, is adequate is beyond the scope of the book. However, we state here that it can be shown that in a forward swap rate risk-neutral world relative to the fixed leg annuity, it is correct to use constant interest rates for discounting as long as we set the expected swap rate to the forward swap rate (unadjusted for convexity) and the option is exercisable into a standard swap with a fixed leg following the pay dates of the numeraire annuity. (This is not true, for example, of constant maturity swaps in which the exercise value is multiplied by a constant, not a future, annuity factor.)  

# 6.1.10 Limitations of the Black Model  

It is important to realize that the Black models - for bond price options, caps/floors, and European swaptions are self-consistent individually but are not consistent with each other. In particular, while all the interest rates considered, e.g. forward LIBOR rates in caps and floors,. and forward swap rates in European swaptions, are related to each other through the yield curve, the different versions of the Black model treat them independently. The cap volatilities are quoted separately on a flat or per caplet basis. The European swaption volatilities have to be quoted as a matrix indexed by the expiries and final swap maturities. Also, there is nothing in the models to ensure that the pricing is logical. There is no mechanism to force 2-into-8 and 3-into-7 swaptions to have similar volatility inputs, or to force a 3-into-2 swaption and a 4-year cap to have similar volatility inputs. It is left to the user to recognize similar structures and to use appropriate inputs.  
