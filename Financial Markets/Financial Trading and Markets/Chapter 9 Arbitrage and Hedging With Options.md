---
tags:
  - arbitrage
  - derivative_securities
  - futures_contracts
  - hedging
  - options
  - risk_management
  - swaps
aliases:
  - Chapter 9
  - Derivatives
  - Hedging with Options
key_concepts:
  - Arbitrage and pricing
  - Derivative security definition
  - Futures contracts explained
  - Hedging with derivatives
  - Market participants roles
  - Options and swaps
---

# Arbitrage and Hedging With Options  

# 9.1 DERIVATIVE SECURITIES MARKETS AND HEDGING  

As discussed earlier, a  derivative security  is simply a financial instrument whose value is derived from that of another security, financial index, or rate. A large number of different types of derivative securities have become increasingly important for management and hedging a variety of different types of risks. There exist a huge variety of derivative securities. Some of the more frequently traded derivatives follow:  

Futures contracts , which provide for the transfer of a given asset at an agreed-to price at a future date. Options , which confer the right but not obligation to buy or sell an asset at a pre specified price on or before a given date. Options are introduced with more detail in the appendix to Chapter 7. Swaps , which provide for the exchange of one set of cash flows for another set of cash flows.  

Hybrids , which combine features of two or more securities (e.g., a convertible bond).  

Risk factors frequently hedged with derivatives include, but are not limited to, uncertainties associated with underlying and related asset price movements, interest and exchange rate variability, debtor default, and economy-wide and sector-specific output levels. Markets for explicit insurance policies on such a wide array of risks do not exist largely due to contracting costs. Most insurance policies are fairly standardized (e.g., health, life, and many casualty policies), while customized insurance contracts are expensive and time consuming to write. Businesses must be able to act quickly to manage their risks in this environment of rapid change. Flexibility and liquidity along with low contracting and transactions costs are key to the success of the risk management operations of a firm. An active and efficient market for derivative securities can help firms hedge and manage a variety of different types of risks.  

Business firms and individual investors desiring to hedge risks are not the only participants in markets for derivatives. A second type of market participant is the speculator who takes a position in a security based on his expectation regarding future price movement. Although the speculator is essentially concerned with his own trading profits, he plays an important role in maintaining liquidity in derivative markets, affording business and individual investors the opportunity to hedge risks quickly and efficiently. The speculator is often the counter party to a hedger’s trade, selling or purchasing derivatives as required by hedgers.  
The arb it rage ur, who exploits situations where derivatives are mispriced relative to one another, not only provides additional liquidity to derivative markets, but plays an important role in their pricing. By constantly seeking price misalignment s for a variety of types of securities, and by understanding the payoffs of securities relative to one another, arbitragers help ensure that derivative securities are fairly priced. This activity reduces price volatility and uncertainty faced by hedgers. In addition, the presence of arb it rage urs provides liquidity to other market participants.  

As discussed in Chapter 2, derivative securities are traded in the United States either on exchanges or over the counter (OTC) markets. Substantial market interest is required for exchange listing, whereas securities with smaller followings or even customized contracts can be traded OTC, including trading between banks and other major participants. The role of the derivatives dealer is essentially the same as that for other security dealers: to facilitate transactions for clients at competitive prices. Derivative dealers match counterparties for derivative contracts, act as counter party for many of their own custom contracts, and provide an array of support services including expert advice and carefully engineered customized risk management products. It is necessary that the dealer providing full support services have a proper understanding of his client and the client’s business and needs. Since some clients do not have an understanding of the technical terms used in the industry, the dealer must be an effective communicator. It is equally important for the dealer to understand the nature of the securities with which he deals and how serving as a market maker for derivatives affects the risk structure of his employer. This understanding usually requires strong analytical skills.  

Many stock options in the United States and Europe are traded on exchanges. The largest U.S. stock options exchanges are the Chicago Board Options Exchange and the NASDAQ OMX Group. The NYSE operates the options markets of the former American Exchange and the International Stock Exchange maintains an options market. Options are also traded on numerous commodities, futures contracts, currencies, and other financial instruments such as Treasury instruments and index contracts.  

Options can be classified into either the European variety or the American variety. European options may be exercised only at the time of their expiration; American options may be exercised any time before and including the date of expiration. Most option contracts traded in the United States (and Europe as well) are of the American variety. American options can never be worth less than their otherwise identical European counterparts. In fact, because most call options have time value in addition to their intrinsic or exercise value (calls on stocks that go ex-dividend before the call expires can be an important exception to this), we usually do not exercise American calls before exercise. This means that we can often value American call options (on non-dividend  paying stock) as though they are European calls.  
# 9.2 PUT  CALL PARITY  

First, since the call (put) owner has the right to buy (sell) the underlying stock at a price of    $X,$   the terminal payoff functions for calls and puts are written as follows:  

$$
\begin{array}{r}{c_{T}=\mathbf{M}\mathbf{A}\mathbf{X}[0,\;S_{T}-X]}\\ {\mathbf{\ell}}\\ {p_{T}=\mathbf{M}\mathbf{A}\mathbf{X}[0,\;X-S_{T}]}\end{array}
$$  

If we subtract  Equation (9.2)  from  Equation (9.1)  we obtain the terminal value  put  call relation :  

$$
c_{T}-p_{T}={\bf M A X}[0,\;S_{T}-X]-{\bf M A X}[0,\;X-S_{T}]=S_{T}-X
$$  

A slight rewrite of this terminal put  call relation allows us to write the terminal or exercise value a put given the terminal value of a call with identical exercise terms:  

$$
p_{T}=c_{T}+X-S_{T}
$$  

Since the terminal value of a put is always given by  Equation (9.4) , the time-zero value of a put must be given by  Equation (9.5) :  

This arbitrage-free relationship allows us to value a put based on the price knowledge of a call with exactly the same exercise terms. The put  call parity function holds regardless of the stochastic process generating stock prices, but assumes that the underlying stock pays no dividends during the lives of the options.  

# Illustration: Hedging With a Call, a Put and a Collar  

Suppose that an investor has 1000 shares of stock that are currently worth  $\S50$   per share each. The investor wishes to lock in his gains on the stock, but does not want to sell at this time for tax reasons. The current two-year riskless return rate is  $5\%$  . The investor could write two-year calls on these shares, with an exercise price of   $\S50$   per share, receiving  $\S8$  for each share that he owns. That is, he could receive  $\S8$   per share by selling covered calls. He could also purchase two-year puts on each share which would enable him to eliminate downside risk. What are the potential hedging strategies available to the investor? What are the costs and benefits of each?  

First, the investor could simply write covered calls. This strategy offers no downside risk protection, but it does provide the investor with  $\S8$   (or   $\S8000$   total) in immediate cash flows. The strategy also limits the investor’s upside potential on the shares, locking out any gains should the share price rise above   $\S50$  . This is because the investor would be obliged to sell the stock to the owner of the call should its price rise above   $\S50$   per share. The owner of the call would not exercise this option if the share price remains below  $\S50$  . While the covered call strategy does reduce portfolio volatility, it is more significant to the investor as a means of generating short-run income at the expense of potential stock profits.  
A second potential strategy for the investor is to purchase puts. We can use  l parity to value these puts. Since the riskless rate is    $r_{f}\,{=}\,0.05,$  , the exercise price is  $X=\S50,$   $S_{0}=\S50,$   $T\!=$   $c_{0}=\S8,$  the current share price is   , and the    two-year call price is   , we can use Equation (9.5)  to value the put:  

$$
p_{0}=8+50\mathrm{e}^{-0.05\times2}-50=3.24
$$  

Each put will protect the investor from downside stock price movements below   $\S50$   per share, and, based on the data given, a fair price for each put is   $\S3.24$  . Thus, for   $\S3.24,$   the investor can lock in a minimum selling price of   $\S50$   for each share. The puts will not require the investor to give up any gains above   $\S50$  .  

What if the investor objects to paying  $\S3.24$   to eliminate downside price risk? Another possibility is to simultaneously purchase a put and write a call, in effect financing the cost of the put with proceeds from selling the call. One such strategy is to create a  collar , which is a package consisting of a long position in a put and a short position in a call. Here, if the investor purchases a put for   $\S3.24$   and sells a call for  $\S8$  , he nets  $\S4.76$   per share. If the share price drops below   $\S50$   in two years, he puts his shares to the put writer for   $\S50$  . If the share price rises above  $\S50$   in two years, his shares are called away from him at  $\S50$   per share. Thus, for a net cash flow today of   $\S4.76,$  , the investor gives up all potential profits and losses on his shares, locking or “collaring” in a price of   $\S50$  today.  

# 9.3 OPTIONS AND HEDGING IN A BINOMIAL ENVIRONMENT  

The  binomial option pricing model  is based on the assumption that the underlying stock follows a binomial return generating process. This means that for any period during the life of the option, the stock’s value will be only one of two potential constant values. For example, the stock’s value will be either    $u$   (multiplicative upward movement) times its  $d$  current value or  (multiplicative downward movement) times its current value.  

Consider a stock currently selling for 100 and assume for this stock that    $u$   equals 1.2  $d$  and  equals 0.8. The stock’s value in the forthcoming period will be either 120 (if outcome  $u$   is realized) or 80 (if outcome    $d$   is realized). Suppose that there exists a European call trading on this particular stock during this one-time period model with an exercise price of 90. The call expires at the end of this period when the stock value is either 120 or 80 as in  Figure 9.1 . Thus, if the stock were to increase to 120, the call would be worth 30  $(c_{u}=30)$  ), since one could exercise the call by paying 90 for a stock which is worth 120. If the stock value were to decrease to 80, the value of the call would be zero   $(c_{d}=0)$   since no one would wish to exercise by paying 90 for shares that are worth only 80. Furthermore, suppose that the current riskless return rate is 0.10. Based on this information, we should be able to determine the value of the call.  

Note that we have not specified probabilities of a stock price increase or decrease during the period prior to option expiration. Nor have we specified a discount rate for the option or made inferences regarding investor risk preferences. We will value this call based on the fact that during this single time period, we can construct a riskless hedge  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9707d9b496f83da4a4dadc85df69886b04e68a22dc7bbaff1cada00aa88dbfcf.jpg)  
FIGURE 9.1 One-time-period binomial model.  

portfolio consisting of a position in a single call and offsetting positions in    $\alpha$   shares of underlying stock. This means that by purchasing a single call and by selling    $\alpha$   shares of stock, we can create a portfolio whose value is the same regardless of whether the underlying stock price increases or decreases. Let us first define the following terms:  

$S_{0}=$  Initial stock value  $u=\mathbf{M}$  ul tip li cat ive upward stock price movement  $d=$   Multiplicative downward stock price movement  $c_{u}=\mathrm{MAX}[0,u S_{0}-\mathit{X}],$  ; value of call if stock price increases  $c_{d}=\mathrm{MAX}[0,\!d S_{0}-\mathit{X}];$  ; value of call if stock price decreases  $\alpha={\mathrm{Hedge}}$   ratio  $r_{f}\!=$   Riskless return rate  $X=$   Exercise price of the call  

In our numerical example offered above, we use the following to determine the value of the call in the binomial framework:  

$$
\begin{array}{l}{S_{0}=100}\\ {u=1.2}\\ {d=0.8}\\ {c_{u}=30}\\ {c_{d}=0}\\ {r_{f}=0.10}\\ {X=90}\end{array}
$$  

Our first step in determining the value of the call is to determine    $\alpha,$   the  hedge ratio . The absolute value of the hedge ratio defines the number of shares of stock that must be sold (or short sold) for each long call position in order to maintain a riskless portfolio. This riskless portfolio will be comprised of one c  option along with a short position in    $-\alpha$   shares of stock, actually, the absolute value of  α  shares of stock, since alpha is negative. In this case, the riskless hedge portfolio made up of one call option and    $\alpha$   shares of stock will have the same value whether the stock price increases to    $u S_{0}$   or decreases to    $d S_{0}$   (see  Figure 9.1 ).  
If we were to purchase one call and sell    $-\alpha$   shares of stock, our riskless hedge condition is given as follows:  

$$
c_{u}+\alpha u S_{0}=c_{d}+\alpha d S_{0}
$$  

  
$$
30+\alpha\bullet120=0+\alpha\bullet80
$$  

We defined the absolute value of    $\alpha$   to be the number of shares to sell for every call purchased. This value is known as a hedge ratio. By maintaining this hedge ratio, we maintain our hedged portfolio. Solve for the hedge ratio    $\alpha$   as follows:  

$$
\begin{array}{l}{\alpha=\displaystyle\frac{c_{u}-c_{d}}{S_{0}(d-u)}}\\ {\alpha=\displaystyle\frac{30-0}{100(0.8-1.2)}=-\,0.75}\end{array}
$$  

In our example,    $\alpha=-0.75,$  , meaning that the investor should sell 0.75 shares of underlying stock for each call option that he purchases to maintain a riskless portfolio. If the investor shorts 0.75 shares for each call purchased, the riskless portfolio will be worth    $-60$   regardless of whether the stock rises to 120 or drops to 80 (see  Figure 9.1 ). Similarly, if the investor purchased 0.75 shares for each call sold or written, the riskless portfolio will be worth 60 regardless of whether the stock rises to 120 or drops to 80. Thus, as long as the investor can confirm that there are only two potential outcomes for the underlying stock price, and determine what these prices are, he can create a hedge or riskless portfolio comprised of the option and    $\alpha$   shares of the underlying stock. Since this hedge portfolio is riskless, it must earn the riskless rate of return for arbitrage opportunities to be avoided:  

$$
c_{u}+\alpha u S_{0}=c_{d}+\alpha d S_{0}=(c_{0}+\alpha S_{0})(1+r_{f})
$$  

Thus, our problem now is to value the call,  $c_{0}$  . From here, we can work equally well either with outcome    $u$   or outcome  $d_{.}$  ; since it makes no difference we can choose outcome  $d$  . Note that the time-zero option value    $c_{0}$   can be solved for by rearranging  Equation (9.8) . If Equation (9.8)  does not hold, or if the current price of the option is inconsistent with Equation (9.8) , a riskless arbitrage opportunity will exist. Thus, we will rewrite  Equation (9.8)  to solve for the zero NPV condition that eliminates positive profit arbitrage opportunities:  

$$
c_{0}+\alpha S_{0}=\frac{c_{d}+\alpha d S_{0}}{(1+r_{f})}
$$  

It is now quite simple to solve for the call value  $c_{0}$   by rewriting  Equation (9.9) :  

$$
\begin{array}{c}{c_{0}=\cfrac{-(1+r_{f})\alpha S_{0}+c_{d}+\alpha d S_{0}}{(1+r_{f})}}\\ {c_{0}=\cfrac{(1+0.10)\cdot0.75\cdot100+0-0.75\cdot0.8\cdot100}{(1+0.10)}=20.4545}\end{array}
$$  
Equation (9.10)  is quite appropriate for evaluating a European call in a one-time period binomial framework. That is, in the model presented thus far, share prices can either increase or decrease once by a pre specified amount or percentage. Thus, there are only two potential prices that the stock can assume at the expiration of the stock. This binomial option pricing model can easily be extended to cover as many potential outcomes and time periods as necessary for a particular scenario.  

# Arbitrage in the One-Time Period Case  

We found the arbitrage-free value of the call in the above example to be 20.4545. What if its price in the marketplace were instead 19? In this scenario, since the call is undervalued, we will purchase it, along with taking a short position in 0.75 shares of the underlying stock at  $\S100$  . This initial investment will be    $\textstyle-\,\S56,$  , which we will loan at the riskless rate of   $10\%$  . Our initial and time-one cash flows are computed as follows:  

Time-zero cash flow: 1  $\begin{array}{l}{1\times-19.00-0.75\times-100-56=0}\\ {1\times30.00-0.75\times120+56(1.1)=1\times0-0.75\times80+56(1.1)=1.6}\end{array}$  Time-one cash flow: 1  

Thus, the time-zero cash flow nets to zero. If the stock price rises to 120 in time one, the call pays   $\S30$  , the short position requires   $\S90$   to settle, and the loan repays   $\S61.60$  . If the stock price drops to 80 in time one, the call pays 0, the short position requires  $\S60$   to settle and the loan repays   $\S61.60$  . Regardless, the time-one net cash flow is  $\S1.60$  , representing a time-one arbitrage profit equal to 1.6, resulting from a time zero investment of zero.  

# Extending the Binomial Model to Two Periods  

As we stated above,  Equation (9.10)  is appropriate for evaluating a European call in a one-time-period framework. That is, in the model presented thus far, share prices can either increase or decrease once by a pre specified percentage. Thus, there are only two potential prices that the stock can assume at the expiration of the stock. Our next step in the development of a more realistic model is to extend the framework to two time periods. One complication is that the hedge ratio only holds for the beginning of the first time period. After this period, the hedge ratio must be updated to reflect price changes and movement through time. Thus, our first step in extending the model to two time periods is to substitute for the hedge ratio based on  Equation (9.10) :  

$$
c_{0}=\frac{(1+r_{f})\displaystyle\frac{(c_{u}-c_{d})}{S_{0}(u-d)}S_{0}+c_{d}-\displaystyle\frac{(c_{u}-c_{d})}{S_{0}(u-d)}d S_{0}}{(1+r_{f})}
$$  

The next two steps of our development are to simplify  Equation (9.11) :  

$$
c_{0}=\frac{\displaystyle\frac{(1+r_{f})(c_{u}-c_{d})+c_{d}(u-d)-d(c_{u}-c_{d})}{(u-d)}}{(1+r_{f})}
$$  
$$
c_{0}=\frac{c_{u}\displaystyle\frac{(1+r_{f})-d}{(u-d)}+c_{d}\displaystyle\frac{u-(1+r_{f})}{(u-d)}}{(1+r_{f})}
$$  

Assume for the moment that    $r_{f}$   can be regarded as a riskless discount rate and that investors will discount cash flows derived from the call based on this riskless rate; that is, for the moment, assume that investors are risk neutral. This assumption is reasonable if investors investing in options behave as though they are risk neutral; in fact they will evaluate options as though they are risk neutral because they can eliminate risk by setting appropriate hedge ratios. Their extent of risk aversion will already be reflected in the current value that they associate with underlying stock given its potential future values. Note that Equation (9.13)  defines the current call value in terms of the two potential call prices  cu and  cd  and this riskless return rate. Since it is reasonable to assume that investors behave towards options as though they are risk neutral, the numerator of  Equation (9.13)  might be regarded as an expected cash flow. Hence, the terms which  $c_{u}$   and  $c_{d}$   are multiplied by might be regarded as probabilities. Define    $p$   to be the probability that the risk neutral investor associates with the stock price changing to    $u S_{0}$   and   $\left(1\mathrm{~-~}p\right)$   as the probability  $p$  that the stock price changes to    $d S_{0}$  :  

$$
p={\frac{(1+r_{f})-d}{(u-d)}}\qquad\qquad(1-p)={\frac{u-(1+r_{f})}{(u-d)}}
$$  

We simplify  Equation (9.13)  by substituting in  Equations (9.14) :  

$$
c_{0}=\frac{c_{u}p+c_{d}(1-p)}{(1+r_{f})}
$$  

Equation (9.15)  represents a slightly simplified version of the one-time period option pricing model. However, it is easily extended to a two-period model if we assume that    $u$   and  $d$   are constant over the periods. Let  $c_{u^{2}}$   be the call’s expiration value after two time periods assuming that the stock’s price has risen twice;    $c_{d^{2}}$   is the value of the call assuming the stock price declined twice during the two periods and    $c_{u d}$   is the value of the call assuming the stock price increased once and decreased once during these two periods. Thus, our two-time-period model becomes:  

$$
c_{0}=\frac{c_{u^{2}}p^{2}+2p(1-p)c_{u d}+(1\!-\!p)^{2}c_{d^{2}}}{{(1+r_{f})}^{2}}
$$  

# Illustration: Two-Time-Period Hedges  

Now, we will extend our illustration above from a single period to two periods, each with a riskless return rate equal to 0.10. As before, the stock currently sells for 100 and will change to either 120 or 80 in one time period   $(u=1.2,\,d=0.8)$  ). However, in the second period, the stock will change a second time by a factor of either 1.2 or 0.8, leading to  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/256c2c8f3be69310a64730494e26566de15c1273636c509141c25ecf9532e75d.jpg)  
FIGURE 9.2 Two-time-period binomial model.  

potential values of either 144 (up then up again), 96 (up once and down once), or 64 (down twice). The lattice (tree) associated with this stock price process is depicted in Figure 9.2 . Call option prices are also given for the second period. The probability of upward and downward movements are computed with the  Equation (9.14)  set as follows:  

$$
p={\frac{((1+0.1)-0.8)}{(1.2-0.8)}}=0.75\qquad(1-p)={\frac{(1.2-(1+0.05))}{(1.2-0.8)}}=0.25
$$  

The time-zero call value in this two-period binomial framework is computed with Equation (9.16)  as follows:  

$$
_{1}={\frac{(144-90)\times0.75^{2}+2\times0.75(1-0.75))\times(96-90)+(1-0.75)^{2}\times0}{(1+0.10)^{2}}}=26.962
$$  

Because the call is priced relative to the stock and riskless asset, any deviation of the market price of the call from this theoretical binomial price creates an arbitrage opportunity for investors, just as in the one-time period illustration above.  

We calculate the hedge ratio for time zero to be    $-0.75$   from  Equation (9.7)  and the hedge ratio in time one to be either    $-0.875$   or    $^{-1}$  , depending on whether the share price increases or decreases in the first period:  

$$
\alpha_{0}=\frac{30-0}{100(0.8-1.2)}=-\,0.75
$$  

$$
\alpha_{u}=\frac{54-6}{120(0.8-1.2)}=-\,1\quad\alpha_{d}=\frac{6-0}{80(0.8-1.2)}=-\,0.1875
$$  

Thus, the investor will hedge by shorting 0.75 shares for each long call in the first period, and will update his hedge ratio to either 1 or 0.1875 short shares in the second period. Also, note the change in time perspectives for    $u$   and    $d$   in the second period after one period has elapsed.  
# Extending the Binomial Model to    $\textdollar{n}$   Time Periods  

The binomial model is easily extended to    $n$   time periods (evenly split within the interval  $T)$  ) by implementing the binomial theorem to obtain the following 1 :  

$$
c_{0}=\frac{\displaystyle\sum_{j=0}^{n}\frac{n!}{j!(n-j)!}p^{j}(1\!-\!p)^{n-j}\mathbf{M}\mathbf{A}\mathbf{X}\big[0,u^{j}d^{n-j}S_{0}-X\big]}{(1+r_{f})^{n}}
$$  

Computing  Equation (9.17)  might be simplified by using  Equation (9.18) , where  $a$   is deter2 mined by  Equation (9.19) :  

$$
c_{0}=\frac{\displaystyle\sum_{j=a}^{n}\frac{n!}{j!(n-j)!}p^{j}(1\!-\!p)^{n-j}\big[u^{j}d^{n-j}S_{o}-X\big]}{\displaystyle(1+r_{f})^{n}}
$$  

$$
a=\mathbf{M}\mathbf{A}\mathbf{X}\left[I N T\left(\frac{\ln\left(\cfrac{X}{S_{0}d^{n}}\right)}{\ln\left(\cfrac{u}{d}\right)}+1\right),\;0\right]
$$  

The binomial option pricing model prices calls and puts relative to the pricing of underlying securities and the riskless return. That is, the binomial model prices an option against a portfolio comprising the underlying security and the riskless asset. Any deviation in the market prices from their binomial prices suggests one or both of the following:  

1.  The binomial option pricing model does not apply to this market.

 2.  There is an arbitrage opportunity in this market.  

# Illustration: Three Time Periods  

Now, we will extend our illustration above from two periods to three, each with a riskless return rate equal to 0.10. As we see in  Figure 9.3 , by the third period, potential stock values are  $\hat{1.2}^{3}\times100=172.8,$  ,  $1.2^{2}\times0.8\times{\stackrel{\smile}{100}}=115.{\stackrel{.}{2}},$  ,  $0.8^{2}\times1.2\,\overset{\cdot}{\times}\,100=\overset{\cdot}{7}6.8,$  , or  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/baedb94e5931e7cb607a54509c5fcec9715b22bf5ba1161b2418efa24b1132bc.jpg)  
FIGURE 9.3 Three-time-period binomial model.  

$0.8^{3}\times100=51.2.$  . The time-zero call value in this three-period binomial framework is computed with  Equations (9.19) and (9.18)  as follows:  

$$
a=\mathbf{M}\mathbf{A}\mathbf{X}\left[I N T\left({\frac{\ln\left({\cfrac{90}{100\times0.8^{3}}}\right)}{\ln\left({\cfrac{1.2}{0.8}}\right)}}+1\right),\,0\right]=2
$$  

$$
{\begin{array}{r l}{c_{0}}&{={\frac{(3\times0.75^{2}\times0.25)\times(1.2^{2}\times0.8\times100-90)+(1\times0.75^{3})\times(1.2^{3}\times100-90)}{(1+0.10)^{3}}}}\\ &{={\frac{(0.421875\times25.2)+(0.421875\times82.8)}{1.331}}={\frac{10.63125+34.93125}{1.331}}=34.231}\end{array}}
$$  

3 Put  call parity still applies :  

$$
p_{0}=34.23178+90/(1.1)^{3}-100=1.85
$$  

# Obtaining Multiplicative Upward and Downward Movement Values  

One apparent difficulty in applying the binomial model as it is presented above is in obtaining estimates for    $u$   and    $d$   that are required for  $p;$   all other inputs are normally quite easily obtained. There are several methods that are used to obtain parameters for the  

3 We will discount the exercise money with a discrete discount function since the binomial model is a discrete time model.  
binomial method from the actual security returns generating process. For example, following    $\cos,$   Ross, and Rubinstein (1979) , derive the following to estimate probabilities of an uptick  $p$   and downtick   $(1-p)$  : 4  

$$
p=\frac{\mathrm{e}^{r_{f}}-d}{u-d}\;(1-p)=\frac{u-\mathrm{e}^{r_{f}}}{u-d}
$$  

Cox et al. also propose the following to estimate    $u$   and  $d$   in the binomial approximation to the Wiener process, where    $\sigma$   is the standard deviation of stock returns:  

$$
u=\mathbf{e}^{\sigma}\quad d={\frac{1}{u}}
$$  

or, if  $n$   and    $T$   differ from 1:  

$$
u=\mathrm{e}^{\left(\sigma\times\sqrt{\frac{T}{n}}\right)}\quad d=\frac{1}{u}
$$  

Suppose, for example, that for a particular Wiener process,    $\sigma=0.30$   and    $r_{f}\!=\!0.05$  . Using Equations (9.20) and (9.22) , we estimate  $p,\,u,$   and  $d$   for a single-time-period binomial process as follows:  

$$
\begin{array}{l}{u=\mathrm{e}^{0.3}=1.3498588}\\ {\mathrm{~}}\\ {d={\frac{1}{u}}=0.7408182}\end{array}
$$  

# Binomial Model: An Illustration  

Suppose that we wished to evaluate a call and a put with an exercise price equal to  $\S110$   on a share of stock currently selling for   $\S100$  . The underlying stock-return standard deviation equals 0.30 and the current riskless return rate equals 0.05. If both options are of the European variety and expire in six months, what are their values?  

First, we will compute the call’s value using the binomial model. We will vary the number of jumps in the model as the example progresses. First, let    $n=1$   and use  Equations (9.20) and (9.22)  to compute  $p,\,u,$   and  $d$  :  

ﬃﬃﬃﬃﬃ 
$$
u\!=\!e^{0.3\times{\sqrt{0.5}}}\!=1.2363111
$$  

$$
d=\frac{1}{1.2363111}=0.8088578
$$  
$$
p={\frac{\mathrm{e}^{r_{f}T}-d}{u-d}}=0.5063881
$$  

Thus, in a risk-neutral environment, there is a 0.5064 probability that the stock price will increase to 123.63 and a 0.4936 probability that the stock price will be 80.88678. Similarly, in a risk-neutral environment, there is a 0.5064 probability that the call will be worth 13.63; therefore, its current value is   $6.73=0.5064\times{\dot{1}}3.63\times\mathrm{e}^{-0.05\times0.5}$  . The call value is deter $n=a=1$  mined by the binomial model as follows where :  

$$
c_{0}={\frac{\displaystyle\sum_{j=a}^{n}{\frac{n!}{j!(n-j)!}}p^{j}(1-p)^{n-j}\big[u^{j}\times d^{n-j}S_{o}-X\big]}{\displaystyle(1+r_{f})^{T}}}}\\ {c_{0}={\frac{0.506388^{1}\times0.4936119^{1-1}\times[1.236311^{1}\times0.8088578^{1-1}\times100-110]}{\left(1+0.05\right)^{5}}}=6.77.}\end{array}
$$  

We can also use the binomial model to value the put with identical exercise terms on the 5 underlying stock :  

$$
p_{0}=\frac{\displaystyle\sum_{j=0}^{a-1}\frac{n!}{j!(n-j)!}p^{j}(1-p)^{n-j}\big[X-u^{j}d^{n-j}S_{o}\big]}{\displaystyle(1+r_{f})^{T}}}\\ {p_{0}=\frac{0.506388^{0}\times0.4936119^{1}\times[110-1.23631^{0}\times0.8088578^{1}\times100]}{\displaystyle(1+0.05)^{5}}=14.08}\end{array}
$$  

Now, revise the illustration by dividing the single six-month interval into two threemonth intervals; that is,    $n=2$  . We will now use a two-period binomial model to evaluate calls and puts on this stock. First, we use  Equations (9.20) and (9.22)  to compute  $p,\,\,u,$  and  $d^{6}$  :  

$$
\begin{array}{l}{u=\mathrm{e}^{\left(0.3\times\sqrt{\frac{0.5}{2}}\right)}=1.1618342}\\ {\begin{array}{l}{d=\displaystyle\frac{1}{1.1618342}=0.8607079}\\ {\displaystyle p=\frac{\mathrm{e}^{r_{i}T/n}-d}{u-d}=0.5043415}\end{array}}\end{array}
$$  

5 Recall that put  call parity, demonstrated in the Options and Hedging in a Binomial Environment section, can be used to value puts. We verify this for this example by using  Equation (9.3)  as follows:  $14.08=6.73+110\mathrm{e}^{-0.{\hat{0}}5\times0.5}-100$  .  

6 When there are multiple jumps per period   $(n>1)$  ), and/or when  T  does not equal 1,  $p={\frac{{\mathfrak{e}}^{r_{f}(T/n)}-d}{u-d}}$  and  $(1-p)={\frac{u-\mathrm{e}^{r_{f}(T/n)}}{u-d}}$  .  
Thus, there is a   $0.5043^{2}$    probability that the stock price will increase to 134.98, a 0.5 probability that the stock price will remain unchanged at 100, and a  $0.4957^{2}$    probability that the stock price will decline to 74.08. Thus, there is a 0.2543 probability that the call will be exercised, in which case, it will be worth 24.98. Therefore, the call’s current value is  $6.20=0.2543\times24.98\times\mathrm{e}^{-0.05\times0.5}$  . Call and put values are determined by the binomial model as follows where  $n=a=2$  :  

$$
c_{0}=\frac{\displaystyle\sum_{j=a}^{n}\frac{n!}{j!(n-j)!}p^{j}(1\!-\!p)^{n-j}\big[u^{j}d^{n-j}S_{o}-X\big]}{\displaystyle(1+r_{f})^{T}}
$$  

$$
c_{0}={\frac{0.5043^{2}\times0.4957^{2-2}\times[1.16185^{2}\times0.8607^{2-2}\times100-110]}{\left(1+0.05\right)^{0.5}}}=6.20
$$  

$$
\begin{array}{l}{p_{0}=\displaystyle\frac{\displaystyle\sum_{j=0}^{a}\frac{n!}{j!(n-j)!}p^{j}(1-p)^{n-j}\big[X-u^{j}d^{n-j}S_{o}\big]}{\displaystyle(1+r_{f})^{T}}}\\ {p_{0}=\displaystyle\frac{0.5043^{2-2}\times0.4957^{2}\times[110-1.1618^{2-2}\times0.8607^{2}\times100]+2\times0.5043\times0}{\displaystyle(1+0.05)^{0.5}}}\\ {\qquad=6.20+110\mathrm{e}^{-0.05\times5}-100=13.48}\end{array}
$$  

As the six-month period is divided into more and finer sub intervals, the values of the call and put will approach their Black-Scholes values.  Table 9.1  extends this example to more than two sub intervals.  

# 9.4 THE GREEKS AND HEDGING IN A BLACK-SCHOLES ENVIRONMENT  

As the number of trials    $n$   in a binomial distribution approaches infinity, the binomial distribution approaches the normal distribution. Black and Scholes (see Appendix 9. B) provide a derivation for an option pricing model based on the assumption that the natural logs of stock price relatives will be normally distributed.   We introduced the Black-Scholes model in the appendix to Chapter 7. The assumptions on which the  Black-Scholes options pricing model  and its derivation are based are as follows:  

1.  There are no restrictions on short sales of stock or writing of call options.

 2.  There are no taxes or transactions costs.

 3.  There exists continuous trading of stocks and options.

 4.  There exists a single constant riskless interest rate that applies for both borrowing and lending.  

7  $t$   $S_{t}\div S_{t-1}$  The stock price relative for a given period  is defined as . Thus, the log of the stock price relative is defined as  $\ln[S_{t}\div S_{t-1}]$  .  
TABLE 9.1 Convergence of Binomial Model to Black-Scholes Model 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3ce8ab5798a713f48e1598555f3a4b000766155a508c801f692dec9dd8be16fb.jpg)  

5.  The range of potential stock prices is continuous. This means that a stock’s price can take on any real value.

 6.  The underlying stock will pay no dividends during the life of the option.

 7.  The option can be exercised only on its expiration date; that is, it is a European option.

 8.  Shares of stock and option contracts are infinitely divisible.

 9.  Stock prices follow an I to process; that is, they follow a continuous time-random walk in two-dimensional continuous space. This simply means that stock prices are randomly distributed and can take on any positive value at any time.  

From an applications perspective, one of the more useful aspects of the Black-Scholes model is that it only requires five inputs. All of these inputs, with the exception of the var8 iance of underlying stock returns, is normally quite easily obtained :  

1.  The current stock price   $(S_{0})$  : Use the most recent quote.

 2.  The variance of returns on the underlying stock   $\hat{(\sigma^{2})}$  : Several methods for estimating stock vol at ili ties were discussed in Chapter 7.  
3.  The exercise price of the option   $(X)$   is given by the contract.

 4.  The time to maturity of the option   $(T)$   is given by the contract.

 5.  For the risk-free return rate   $(r_{f})$  , use a Treasury instrument rate with an appropriate term to maturity.  

It is important to note that the following less easily obtained factors are not required as model inputs:  

1.  The expected or required return on the stock or option.

 2.  Investor attitudes toward risk.  

If the assumptions given above hold, the Black-Scholes model specifies that the value of a call option is as follows:  

$$
c_{0}=S_{0}N(d_{1})-\frac{X}{\mathbf{e}^{r_{f}T}}N(d_{2})
$$  

$$
d_{1}=\frac{\ln(S_{0}/X)+(r_{f}+0.5\sigma^{2})T}{\sigma\sqrt{T}}
$$
 ﬃﬃﬃﬃ  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  

where    $N(d^{*})$   is the cumulative normal distribution function for   $(d^{*})$  .  

# Black-Scholes Model Sensitivities  

Options can be very volatile instruments, and hedging is crucial for traders’ management of options portfolios. Sources of sensitivity, or the “Greeks,” are key to this management process. The Black-Scholes model can provide much useful information concerning options and underlying shares. First, assuming that investors behave as though they are risk neutral and that other Black-Scholes assumptions hold,  $N(d_{2})$   might be interpreted as the probability that the stock price will be sufficiently high at the expiration date of the option to warrant its exercise. Thus,    $N(d_{2})$   might be regarded as the probability that investors assign to  $S_{T}$   exceeding    $X;$   that is, the probability at exercise at time    $T$   implied by the call at its current market price    $c_{0}$   is  $N(d_{2})$  . A second particularly useful point is that  $N(d_{1})$  might be interpreted as a hedge ratio, although it must be updated at every period. This means that    $N(d_{1})$   can be interpreted as the number of shares to short for every purchased call, but, as the option’s time to maturity diminishes, and as share prices change, this hedge ratio will change. In addition,  $N(d_{1})$   is the sensitivity of the option value to changes in the stock price. This sensitivity means that the option’s value will change by    $N(d_{1})$   for each unit of change in the underlying stock price. In the finance industry, this value is often referred to as the call  delta .  

Option traders find it very useful to know how the values of their option positions will change as the various factors used in the pricing model change. Knowledge of these sensitivities (sometimes called  Greeks ) is particularly useful to investors holding portfolios of options and can often be extended to weighted averages for the portfolios.  
For example, we mentioned above that the sensitivity of the call’s value to the stock’s 10 price is Delta:  

$$
\frac{\partial c}{\partial S}=N(d_{1})\,{>}\,0\,\qquad\quad D e l t a\quad\Delta
$$  

Thus, a small increase in the value of the underlying stock would lead to approximately    $N$   $(d_{1})$   times that increase in the price of the call option. A call investor can hedge his portfolio risk associated with infinitesimal share price changes by shorting  $N(d_{1})$   shares of underlying stock for each purchased call option. Thus, the hedged portfolio would consist of an offsetting position of  $N(d_{1})$   underlying shares for each call option in the portfolio.  

In addition, the trader can offset this delta risk with multiple positions in options and the underlying stock. For example, if the trader was long a single call option with a delta of 0.5, this risk could be neutralized with offsetting positions in a portfolio of stock and one or more other option contracts on that stock. Thus, in our example, the stock delta could be offset with a portfolio whose weighted average delta was    $-0.5,$   comprised of a single short position in a call option with a delta equal to 0.25 and a short position in 0.25 shares of the underlying stock. Any portfolio whose weighted average delta is 0.5 could be comprised to offset the original call option delta risk.  

There is a major caveat to the application of this hedge ratio. In addition to the Black Scholes assumptions, this sensitivity or delta measure worsens as the change in the stock price increases. Furthermore, a large change in the stock price will lead to a change in the value of the  delta neutral portfolio  because delta is based on a derivative or “point slope,” and applies only to infinitesimal changes in the stock price. Thus, because this delta is based on a partial derivative with respect to the share price, it holds exactly only for an infinitesimal change in the share price; it holds only approximately for finite changes in the share price. This delta only approximates the change in the call value resulting from a change in the share price because any change in the price of the underlying shares would lead to a change in the delta itself:  

$$
\frac{\partial^{2}c}{\partial S^{2}}=\frac{\partial\Delta}{\partial S}=\frac{\partial N(d_{1})}{\partial S}=\frac{\displaystyle\frac{\mathrm{e}^{\frac{\left(-\frac{(d_{1}^{2})}{2}\right)}{\sqrt{2\pi}}}}{S\sigma\sqrt{T}}>0\quad\qquad G a m m a\quad\quad\Gamma
$$  

This change in delta resulting from a change in the share price is known as  gamma . Since gamma is positive, an increase in the share price will lead to an increase in delta. However, again, this change in delta resulting from a finite share price change is only approximate. Each time the share price changes, the investor must update his portfolio to reflect the changing delta.  

Gamma is very useful to traders that want to hold delta neutral portfolios. With a fairly large number of puts and calls on the same underlying stock to choose from, traders will be able to discern an infinity of portfolios (in theory with an infinity of potential stock price changes) that maintain delta neutrality. That is, with a single option and shares of its underlying stock, there will normally be a single hedge ratio that provides for portfolio delta neutrality. This delta neutrality means that fairly small changes in the underlying stock’s price will have a negligible impact on the value of the portfolio of shares and options. With two different options contracts, for example, contracts with different exercise prices, there may be an infinity of portfolios that maintain delta neutrality. However, there will probably be only one of these portfolios that simultaneously maintains delta and gamma neutrality (select portfolio weights appropriately because all gammas are positive). This delta-gamma neutral portfolio will normally minimize adjustments necessary to accommodate near-term future stock price changes in the hedged portfolio. At least two different options contracts along with underlying shares will be needed to maintain both delta and gamma neutrality. With two different options contracts and underlying shares, there will normally be a single combination of portfolio weights that simultaneously maintains delta and gamma neutrality; more than two different options contracts and underlying shares will allow for an infinite number of delta/gamma neutral portfolios.  
Since each call and put option has a date of expiration, calls and puts are said to amortize over time. As the date of expiration draws nearer (  $T$   gets smaller), the value of the European call (and put) option might be expected to decline as indicated by a positive theta :  

$$
\frac{\partial c}{\partial T}=r_{f}X\mathbf{e}^{-r_{f}T}N(d_{2})+S\frac{\sigma}{\sqrt{T}}\frac{\mathbf{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{2\sqrt{2\pi}}>0\qquad T h e t a\qquad\theta
$$
 ﬃﬃﬃﬃ ﬃﬃﬃﬃﬃﬃ  

Many traders seek to maintain portfolios that are simultaneously neutral with respect to delta, gamma, and theta. Be certain that the units of time for theta are consistent with those used in the calculation of the option value. Some option traders calculate option prices based on numbers of years (fractions of years) prior to option expiry, but prefer to calculate theta in days. This is acceptable, but divide the annual theta by 365 (or the number of trading days in the year) to obtain the daily theta.  

Vega , which actually is not a Greek letter, measures the sensitivity of the option price to the underlying stock’s standard deviation of returns. One might expect the call option price to be directly related to the underlying stock’s standard deviation:  

$$
\frac{\partial c}{\partial\sigma}=S\sqrt{T}\frac{\mathrm{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{\sqrt{2\pi}}>0\qquad V e g a\qquad\nu
$$
 ﬃﬃﬃﬃﬃﬃ  

Although the Black-Scholes model assumes that the underlying stock volatility is constant over time, in reality, volatility can and does shift. Vega provides an estimate for the impact of a volatility shift on the option’s value. Vega is also useful in calculating option implied vol at ili ties when the iteration process is made more efficient with the use of the NewtonRaphson method.  

A trader should expect that the value of the call would be directly related to the riskless return rate and inversely related to the call exercise price:  

$$
\frac{\partial c}{\partial\mathbf{e}^{r_{f}}}=T X\mathbf{e}^{-r_{f}T}N(d_{2})>0\qquad R h o\qquad\rho
$$  
$$
\frac{\partial c}{\partial X}=-\,\mathbf{e}^{-r_{f}T}N(d_{2})\!<\!0
$$  

The option rho can be very useful in economies with high or volatile interest rates, though most traders of “plain vanilla options” do not concern themselves much with call value sensitivities to exercise prices.  

# Illustration: Greeks Calculations for Calls  

In the appendix to Chapter 7, we worked through the Black-Scholes model to value a call. We summarize details as follows:  

$$
\begin{array}{c c}{{T=0.5}}&{{r_{f}=0.10}}\\ {{}}&{{}}\\ {{X=80}}&{{\sigma^{2}=0.16}}\\ {{}}&{{}}\\ {{\sigma=0.4}}&{{S_{0}=75}}\end{array}
$$  

$$
d_{1}={\frac{\ln\,(75/80)+(0.1+0.5\cdot0.16)0.5}{0.4\cdot{\sqrt{0.5}}}}={\frac{\ln\,(0.9375)+0.09}{0.2828}}=0.09
$$
  ﬃﬃﬃﬃﬃﬃﬃ  

ﬃﬃﬃﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-0.4\bullet\sqrt{0.5}=0.09-0.2828=-\,0.1928
$$
   

$$
N(d_{1})=N(0.09)=0.536\quad N(d_{2})=N(-0.1928)=0.42
$$  

$$
c_{0}=75\bullet0.536-(80\bullet0.9512)\bullet0.42=7.96
$$
     

Sensitivities (Greeks) for this call option are computed as follows:  

$$
\frac{\partial c}{\partial S}=N(d_{1})=\Delta=0.536
$$  

$$
\frac{\partial^{2}c}{\partial S^{2}}=\frac{\partial\Delta}{\partial S}=\frac{\partial N(d_{1})}{\partial S}=\frac{\frac{\mathrm{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{\sqrt{2\pi}}}{S\sigma\sqrt{T}}=I=0.0187
$$
 ﬃﬃﬃﬃ  

$$
\frac{\partial c}{\partial T}=-\,r_{f}X\mathrm{e}^{-r_{f}T}N(d_{2})-S\frac{\sigma}{\sqrt{T}}\frac{\mathrm{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{2\sqrt{2\pi}}=\theta=-\,11.6522\ \ \ \ \ \,D a i l y\ \ \ T h e t a=-\,0.0
$$
 ﬃﬃﬃﬃ ﬃﬃﬃﬃﬃﬃ  

$$
\frac{\partial c}{\partial\sigma}=S\sqrt{T}\frac{\mathbf{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{\sqrt{2\pi}}=\nu=21.07
$$
 ﬃﬃﬃﬃﬃﬃ  

$$
\frac{\partial c}{\partial e^{r_{f}}}=T X\mathrm{e}^{-r_{f}T}N(d_{2})=\rho=16.1156
$$  

$$
\frac{\partial c}{\partial X}=-\,\mathrm{e}^{-r_{f}T}N(d_{2})=-\,0.4029
$$  
Sometimes thetas are expressed in daily terms and sometimes vegas and rhos are expressed in terms based on one percentage point increases in standard deviation or interest rates.  

# Illustration: Hedging With Delta and Gamma Neutral Portfolios  

In our numerical example above, we can establish a delta neutral portfolio by purchasing a single call and shorting 0.536 shares of stock. The portfolio delta is the weighted average of its component security deltas, and one call has already been purchased:  

$$
\begin{array}{c}{{d e l t a_{S}\times\#_{S}+d e l t a_{C}\times\#_{C}=d e l t a_{p o r t}}}\\ {{\#_{C}=1}}\end{array}
$$  

The portfolio delta is to be set equal to zero for delta neutrality, and the delta of shares is 1.  

$$
\begin{array}{c}{{1\times\#_{S}+0.536\times\#_{C}=0}}\\ {{\#_{C}=1}}\end{array}
$$  

Clearly the solution to this system is   $\#_{S}=\;-\;0.536,$  , implying that delta neutrality requires an offsetting position in 0.536 shares of underlying stock.  

Next, suppose instead that we have purchased a single share of underlying stock and  $\Delta$     $\Gamma$  that we wish to maintain both delta and gamma neutrality (  and  equal zero) for our portfolio. These two criteria cannot simultaneously be accomplished with only a single option with our single share. Suppose that we can take positions in a second call option, with the same exercise terms as the first except that the exercise price equals 75 rather than 80. We calculate the delta and gamma of our second option to be 0.62483 and 0.0178, respectively. Stock deltas are 1 and stock gammas are zero. Now, we will seek to solve the following system:  

$$
\left[\begin{array}{c c c c}{d e l t a_{p o r t}}\\ {g a m m a_{p o r t}}\\ {\#_{S}}\\ {\mathbf{r}}\end{array}\right]=\left[\begin{array}{c c c c}{d e l t a_{S}}&{d e l t a_{C1}}&{d e l t a_{C2}}\\ {g a m m a_{S}}&{g a m m a_{C1}}&{g a m m a_{C2}}\\ {1}&{0}&{0}\\ {\mathbf{Y}}&{\mathbf{\Lambda}}&{\#}\end{array}\right]\quad\left[\begin{array}{c c c c}{\#_{S}}\\ {\#_{C1}}\\ {\#_{C2}}\end{array}\right]
$$  

$$
\left[\begin{array}{c}{d e l t a_{p o r t}}\\ {g a m m a_{p o r t}}\\ {\#_{S}}\\ {\textbf{r}\;\;\;\;\;\;=}\end{array}\right]=\left[\begin{array}{c c c c}{0}\\ {0}\\ {1}\end{array}\right]=\left[\begin{array}{c c c c}{1}&{0.53586}&{0.62483}\\ {0}&{0.0187}&{0.0178}\\ {1}&{0}&{0}\end{array}\right]\quad\left[\begin{array}{c}{\#_{S}}\\ {\#_{C1}}\\ {\#_{C2}}\end{array}\right]
$$  

$$
\left[\begin{array}{l}{\#_{S}}\\ {\#_{C1}}\\ {\#_{C2}}\end{array}\right]=\left[\begin{array}{c}{1}\\ {8.42}\\ {-\;8.82}\end{array}\right]=\left[\begin{array}{c c c}{0}&{0}&{1}\\ {-\;8.42}&{\;294.27}&{\;8.42}\\ {\;8.82}&{-\;252.37}&{\;8.42}\end{array}\right]\quad\left[\begin{array}{l}{0}\\ {0}\\ {1}\end{array}\right]
$$  
Thus, for each underlying share of stock purchased, a delta-gamma neutral portfolio requires a long position in 8.42 calls with   $\S80$   exercise prices and a short position in 8.82 calls with   $\S75$   exercise prices. The availability of additional option contracts would increase flexibility with respect to maintaining delta-gamma neutrality. On the other hand, simultaneous maintenance of theta neutrality along with delta-gamma neutrality would require at least one additional different option contract.  

# Put Sensitivities  

If put  call parity holds along with Black-Scholes assumptions given above, the BlackScholes put value is computed as follows:  

$$
p_{0}=-\;S_{0}N(-\,d_{1})+\frac{X}{\mathrm{e}^{r_{f}T}}N(-\,d_{2})
$$  

$$
d_{1}=\frac{\ln(S_{0}/X)+(r_{f}+0.5\sigma^{2})T}{\sigma\sqrt{T}}
$$
 ﬃﬃﬃﬃ  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  

In our numerical example, the put is worth 9.05 if its exercise terms are identical to those of the call in the same example. We can use these put sensitivities to hedge and manage portfolio risk in the same manner that we used the call sensitivities. Put sensitivities formulas and calculations for our example are as follows:  

$$
\frac{\partial p}{\partial S}=N(d_{1})-1=\Delta_{p}=-\,0.464
$$  

$$
\frac{\partial^{2}p}{\partial S^{2}}=\frac{\partial\Delta_{p}}{\partial S}=\frac{\partial N(d_{1})-1}{\partial S}=\frac{\mathrm{e}^{\frac{\left(-\frac{(d_{1}^{2})}{2}\right)}{\sqrt{2\pi}}}}{S\sigma\sqrt{T}}=\Gamma_{p}=0.0187
$$  

$$
\frac{\partial p}{\partial T}=r_{f}X\mathrm{e}^{-r_{f}T}N(-d_{2})-S\frac{\sigma}{\sqrt{T}}\frac{\mathrm{e}^{\left(\frac{-(-d_{1}^{2})}{2}\right)}}{2\sqrt{2I I}}=\theta_{p}=-\ 4.110;\ \ \ \,D a i l y\ \,T h e t a=-\ 0.01
$$
 ﬃﬃﬃﬃ ﬃﬃﬃﬃﬃﬃﬃ  

$$
\frac{\partial p}{\partial\sigma}=S\sqrt{T}\frac{\mathrm{e}^{\left(\frac{-(d_{1}^{2})}{2}\right)}}{\sqrt{2\pi}}=\nu_{p}=21.06
$$
 ﬃﬃﬃﬃﬃﬃ  

$$
\frac{\partial p}{\partial\mathbf{e}^{r_{f}}}=-\mathit{T X}\mathbf{e}^{-r_{f}T}N(-d_{2})=\rho_{p}=-21.93
$$  

$$
\frac{\partial p}{\partial X}=-\,\mathbf{e}^{-r_{f}T}(N(d_{2})-1)=0.548
$$  
# 9.5 EXCHANGE OPTIONS  

In this section, we discuss a variation of the Black-Scholes model provided by  Garman and Ko¨hlagen (1983)  and  Grabbe (1983)  for the valuation of currency options. The stock option pricing model is based on the assumption that investors price calls as though they expect the underlying stock to earn the risk free rate of return. However, when we value currency options, we acknowledge that interest rates might differ between the foreign and domestic countries, and that money might be borrowed in one country and loaned in another. Hence, we quote two interest rates—one each for the foreign and domestic currencies. In this scenario, we value currency options as follows:  

$$
c_{0}=s_{0}{\mathrm e}^{-r(f)T}N(d_{1})-\frac{X}{{\mathrm e}^{r(d)T}}N(d_{2})
$$  

$$
d_{1}={\frac{\ln\!\left({\frac{S_{0}}{X}}\right)+\left(r(d)-r(f)+{\frac{\sigma^{2}}{2}}\right)T}{\sigma{\sqrt{T}}}}
$$
 ﬃﬃﬃﬃ  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  

where    $r(d)$   is the domestic riskless rate (the rate for the currency that will be given up if the option is exercised),    $r(f)$   is the foreign riskless rate (the rate for the currency that might be purchased). The spot rate for the currency is  $s_{0}$  . The standard deviation of proportional exchange rates for the foreign currency to be purchased in terms of the domestic currency is    $\sigma$  . The exercise price of the option,    $X,$   represents the number of units of the domestic currency to be given up for each unit of the foreign currency. The following variation of put  call parity will apply to the valuation of currency puts:  

$$
p_{0}=c_{0}+X\mathbf{e}^{-r(d)T}-s_{0}\mathbf{e}^{-r(f)T}
$$  

# Illustration: FX Option Valuation  

Consider, for example, a currency option series on Swiss francs (CHF) denominated in U.S. dollars. Suppose that a six-month (0.5 years) call option is available on francs with an exercise price equal   $\S0.5556$  . The domestic and foreign riskless rates are 0.1. The current exchange rate is  $\S0.5556/\mathrm{CHF}$   and the standard deviation associated with the exchange rate is 0.4. What is the value of this currency call?  

To answer this question, we first calculate  $d_{1}$  :  

$$
d_{1}={\frac{\ln\left({\cfrac{0.5556}{0.5556}}\right)+\left(0.1-0.1+{\cfrac{0.4^{2}}{2}}\right)\bullet0.5}{0.4{\sqrt{0.5}}}}={\frac{0.04}{0.2828}}=0.1414
$$
 ﬃﬃﬃﬃﬃﬃﬃ  

Next we calculate  $d_{2}$  :  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}=0.1414-0.2828=-\,0.1414
$$  
Next, find cumulative normal density functions (  $\acute{z}$  -values) for  $d_{1}$   and    $d_{2}$  :  

$$
\begin{array}{l}{N(d_{1})=N(0.1414)=0.556}\\ {N(d_{2})=N(-\,0.1414)=0.443}\end{array}
$$  

Finally, we value the call as follows:  

$$
c_{0}=(\S0.5556\times0.556)-[\S0.5556\times0.9512]\times0.443=\S0.05943
$$  

We can evaluate a European put for CHF using  Equation (9.36)  as follows:  

$$
:c_{0}+X{\mathrm{e}}^{-r(d)T}-s_{0}{\mathrm{e}}^{-r(f)T}=0.05943+0.5556{\mathrm{e}}^{-0.1\times0.5}-0.5556{\mathrm{e}}^{-0.1\times0.5}=0.05943
$$  

Consider the next example where four call options are traded on CHF (Swiss Francs) with exercise prices  $X$   expressed in U.S. dollars. One U.S. dollar is currently worth 2 Swiss francs   $(s_{0}=2)$  . We wish to evaluate calls for each of the following European currency option series depicted in  Table 9.2 .  

We will work through  Equations (9.33) through (9.35)  to value the calls. Final solutions are given in the bottom line of  Table 9.3 .  

We use a currency-specific variation of the put  call parity relation ( Equation 9.36 ) to value the puts:  

$$
p_{0}=c_{0}+X\mathbf{e}^{-r(d)T}-s_{0}\mathbf{e}^{-r(d)T}
$$  

TABLE 9.2 Currency Option Illustration 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bc4d335612e141173a2c2860a01d56e4a22029b2aaac3b1a57868750ae441987.jpg)  

TABLE 9.3 Currency Option Values 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fbe0790e7960948e67db9ba15604844b2d5b9ec7d25b9724032025839e015657.jpg)  
Thus, put options with terms identical to those of the calls in  Tables 9.2 and 9.3  have the following values:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/34e3800d1ea54731e4dceeb34bfc7009578261694ed333894b4e844ed59dc8c0.jpg)  

# 9.6 HEDGING EXCHANGE EXPOSURE WITH CURRENCY OPTIONS  

Based on the example from Chapter 8, Hedging Exchange Exposure section, suppose that the Dayton Company of America expects to receive a payoff of  d 1,000,000 in three months, and intends to convert its cash flows to dollars. Continue to assume relevant data as follows:  

Spot exchange rate:   $\Updownarrow1.7640/\updownarrow$  Three-month forward exchange rate:   $\Updownarrow1.7540/\updownarrow$  U.K. borrowing interest rate:   $10.0\%$  U.S. borrowing interest rate:  $8.0\%$   $8.0\%$  U.K. lending interest rate:  U.S. lending interest rate:   $6.0\%$  

Also assume that there exist call and put options and forward contracts with the following terms, and that their premiums might not reflect formula values:  

Term to options expiration: 3 months Exercise price:  $\S1.75$  / d Put premium:  $\Updownarrow0.025/\updownarrow$  Call premium:   $\updownarrow0.065/\updownarrow$  Brokerage cost per options contract on  d 31,250:  $\S50$  

Our problem is to evaluate methods of managing the transaction risk associated with this extension of credit and the implications of each.  

We will consider two options-based hedging strategies here. The first is the put hedge (partial hedge) strategy which involves the purchase of a put on pounds, enabling the firm to protect itself against devaluation of pounds. If the value of pounds increases, the firm realizes a greater profit. However, the firm must pay the full cost of the put. With the conversion or call and put hedge strategy, the proceeds from the sale of a call are used to offset the purchase price of the put. This strategy acts as a collar, locking in the value of pounds at the origination s of the options contracts. Hence, the firm would not benefit from any appreciation in the value of the pound.  

First, we consider the put hedge strategy. We will purchase three month put options on d 1,000,000 with an exercise price of   $\Updownarrow1.75/\updownarrow$   with a total premium of   $\S25{,}000$  . Time-zero brokerage costs total  $\S1600$   (32 contracts at   $\S50$   per contract). Thus the total time-zero cash outlay is  $\S26{,}600$  . Forgone interest on the sum of the premium and brokerage costs totals  $\S399$  . Expressed in terms of future value, the total cash outlay is   $\S26{,}999$  . The result of this strategy is that the firm receives one of the following in three months:  
1.  An unlimited maximum less the  $\S26{,}999$   premium, forgone interest and brokerage fees. The dollar value of this strategy increases as the value of the dollar drops against the pound. Since cash flows are not certain, this hedge is considered partial.

 2.  A minimum of   $\mathbb{S}1{,}750{,}000$   less  $\S26,999$   for a net of   $^{\S1,723,001}$  . This minimum value to be received might be unacceptably low; however, there is upside cash flow potential.  

Alternatively, the firm can employ the conversion or the call and put hedge. This strategy involves the combination of calls and puts, such that total risk can be eliminated. Consider the writing of a call with an exercise price of   $\S1.75$   expiring in three months along with the purchase of a put with the same terms. The time-zero net cash flows are summarized as follows:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7e6aa0758d06671a37c7bb8133d2ca0a9395e61860751dc1fc12fc0ee883bd2f.jpg)  

The result of this conversion is that the interest earned on the net time-zero outlay is  $\S552$  . If the three-month exchange rate is less than  $\Updownarrow1.75/\updownarrow$  , the exchange rate of  $\Updownarrow1.75/\updownarrow$   is locked in by the put. If the exchange rate exceeds  $\mathbb{S}1.75/\mathfrak{L}_{i}$  , the obligation incurred by the short position in the call is activated. Thus, the firm’s exchange rate of  $\Updownarrow1.75/\updownarrow$   is locked in no matter what the market exchange rate is. The cash flows in three months are summarized as follows:  

Put cash flows   $(£1,000,000\times\mathbf{M}\mathbf{A}\mathbf{X}[1.75-\,S_{1},0])$  Call cash flows   $(£1,000,000\times\mathrm{MIN}[1.75-\,S_{1},\!0])$  

Total of option transactions:  

d1; 000; $000\times(1.75-S_{1})=\S1$ ðÞ; 750; 000 2 dð1; 000; 000 3 S1ÞExchange of currency  $=(£1,000,000\times S_{1})$  Þ Time zero cash   $\mathrm{flow}\mathrm{s}=\S36,800$  Interest on time zero flows  $=\!\!\Phi552$  Total time one cash flows  $=\overline{{\mathbb{S}1,787,352}}$  

This cash flow of   $\mathbb{S}1,787,352$   is assured in the absence of default risk.  

# Additional Reading  

Elton, Gruber, Brown, and Goetzmann (2010) , Chapters 21 to 24, offer good coverage of fixed income, options and futures arbitrage and hedging.  Grabbe (1996)  discusses currency option pricing and hedging. Jarrow and Rudd (1983) , while dated, provide a very useful overview of options pricing, hedging and arbitrage. The industry standard reading for options and derivatives is  Hull (2011) , going far beyond the scope and level of rigor of material in this chapter.  Neftci (2000)  provides excellent background reading in the mathematics of financial derivatives, again, going far beyond the scope of this chapter.  
# References  

Cox, J., Ross, S., & Rubinstein, M. (1979). Option pricing: A simplified approach.  Journal of Financial Economics ,  7 , 229  263. Elton, E., Gruber, M., Brown, S., & Goetzmann, W. (2010).  Modern portfolio theory and investment analysis  (8th ed.). New York: Wiley. Garman, M., & Ko¨hlagen, S. (1983). Foreign currency option values.  Journal of International Money and Finance ,  2 , 231  237. Grabbe, J. O. (1983). The pricing of call and put options on foreign exchange.  Journal of International Money and Finance ,  2 , 239  253. Grabbe, J. O. (1996).  International financial markets  (3rd ed.). Englewood Cliffs, NJ: Prentice Hall. Hull, J. C. (2011).  Options, futures and other derivatives  (8th ed.). Englewood Cliffs, NJ: Prentice Hall. Jarrow, R., & Rudd, A. (1983).  Option pricing . Homewood, IL: Dow Jones-Irwin. Jarrow, R. A., & Turnbull, S. M. (1999).  Derivative securities  (2nd ed.). Cincinnati: South-Western College Publishers. Neftci, S. N. (2000).  An introduction to the mathematics of financial derivatives  (2nd ed.). San Diego: Academic Press.  

# 9.7 EXERCISES  

1.  Some observers of derivatives markets agree that publicly traded corporations can use derivatives to mitigate operating risks but that shareholders would be better off if managers simply allowed shareholders to use their own portfolio management and hedging techniques to do so themselves. In fact, some critics argue that corporate managers are too concerned about mitigating risks and that they do so to protect their own jobs and preserve their own income and stock value.  

a.  Why might shareholders be in a better position to mitigate and hedge operating risks of corporations whose shares they own? b.  Why might shareholders be better off if corporate managers continue to hedge operating and financial risks?  

2.  Consider a one-time-period, two potential outcome framework where there exists Company   $\mathrm{Q}$   stock currently selling for   $\S50$   per share and a riskless  $\S100$   face value T-Bill currently selling for   $\S90$  . Suppose Company  $\mathrm{Q}$   faces uncertainty, such that it will pay its owner either   $\S30$   or  $\S70$   in one year. Further assume that a call with an exercise price of  $\S55$   exists on one share of  $\mathrm{Q}$   stock. a.  What are the two potential values the call might have at its expiration? b.  What is the riskless rate of return for this example? Remember, the Treasury bill pays  $\S100$   and currently sells for  $\S90$  . c.  What is the hedge ratio for this call option? d.  What is the current value of this option? e.  What is the value of a put with the same exercise terms as the call?  

3.  Rollins Company stock currently sells for   $\S12$   per share and is expected to be worth either  $\S10$   or   $\S16$   in one year. The current riskless return rate is 0.125. What would be the value of a one-year call with an exercise price of   $\S8?$  

4.  A stock currently selling for  $\S50$   has an annual returns variance equal to 0.36. The riskless return rate equals 0.08 per year. Under the binomial framework, what would be the value of nine-month (0.75 year) European calls and European puts with striking prices equal to  $\S80$   if the number of tree steps   $(n)$   were a. two?b.  three? c.  eight?  
5.  Ibis Company stock is currently selling for  $\S50$   per share and has a multiplicative upward movement equal to 1.2776 and a multiplicative downward movement equal to 0.7828. What is the value of a nine-month (0.75 year) European call and a European put with striking prices equal to  $\S60$   if the number of tree steps were two? Assume a riskless return rate equal to 0.081.  

6.  Stanton Company stock is trading for 50 in a two-time-period environment, with each relevant time period lasting 6 months. The stock might increase by exactly   $20\%$   in just one period or perhaps in both periods. Of course, the stock might not increase in either period. If the stock price does not increase in a given period, it will decline by 16.67 percent in that particular period. One-year options with an exercise price equal to 60 are trading on this stock. The annual riskless rate of return equals 0.  

a.  What is the value of a put in this environment? b.  What is the probability (risk-neutral probability) implied in this framework that the Stanton Company stock price will exceed 40 when options expire in one year?  

7.  Kestrel Company stock is currently selling for  $\S40$   per share. Its historical standard annual deviation of returns is 0.5 in this single-period environment. The one-year Treasury bill rate is currently   $5\%$  . Assume that all of the standard Black-Scholes option pricing model assumptions hold.  

a.  What is the value of a put on this stock if it has an exercise price of  $\S35$   and expires in one year? b.  What is the implied probability that the value of the stock will be less than   $\S30$   in one year?  

8.  Evaluate each of the European options in the series on ABC Company stock. Prices for each of the options are listed in the table. Determine whether each of the options in the series should be purchased or sold at the given market prices. The current market price of ABC stock is 120, the August options expire in nine days, September options in 44 days, and October options in 71 days. The stock return standard deviations prior to expiration s are projected to be 0.20 prior to August, 0.25 prior to September, and 0.20 prior to October. The Treasury bill rate is projected to be 0.06 for each of the three periods prior to expiration. Do not forget to convert the number of days given to fractions of 365-day years.  

Calls 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/052ece59ccf68f28cb80520cbf9db6bbaaef85157e935e142d88ef757cf6e7a0.jpg)  
Puts 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2c9da72ce6d70c90334f5bac0f4b3cf9cfe87272bad0a43b96921e80d5e0e872.jpg)  

Prices for five calls and five puts are given in the left columns. Expiration dates are given in column headings and current market prices are given in the table interiors.  

9.  What is the gamma of a long position in a single futures contract? Why?  

10.  Tanker Company stock currently sells for 30 per share and has an anticipated volatility (annual return standard deviation) equal to 0.6. Three-month (0.25 year) call options are available on this stock with an exercise price equal to 25. The current riskless return rate equals 0.05.  

a.  Calculate the call’s value. b.  Calculate the call’s delta, gamma, theta, vega, and rho. c.  What is the Black-Scholes implied probability that the stock price will exceed 25 three months from now? d.  What is the value of a put with the same exercise terms as the call? e.  What are the Greeks for the put in part d?  

11.  Tanker Company stock, which currently sells for 30 per share and has an anticipated volatility (annual return standard deviation) equal to 0.6, also has a three-month (0.25 year) call option with an exercise price equal to 30. The current riskless return rate equals 0.05.  

a.  Calculate this second call’s value. b.  Calculate this call’s delta, gamma, theta, vega, and rho. c.  What is the Black-Scholes implied probability that the stock price will exceed 30 three months from now? d.  What positions in these calls and the calls from Question 10 should be taken for each long share of stock to maintain a delta-gamma neutral portfolio? e.  What is the theta of the portfolio in part d?  

12.  A currency option series on Australian dollars (AUD) denominated in U.S. dollars. Suppose that a two-year call option is available on AUD with an exercise price equal USD0.65. The U.S. interest rate is 0.04 and the Australian rate is 0.06. The current exchange rate is USD0.7/AUD and the standard deviation associated with the exchange rate is 0.3. What is the value of this currency call? What is the value of a put with the same exercise terms?  

13.  Suppose that right now, the market price of one Chinese yuan (CNY) is USD0.15; that is, one can purchase or sell CNY1.00 for USD0.15. The proportional standard deviation for CNY in terms of USD is  $20\%$  . The Chinese riskless return rate over a two-year period is projected to be  $8\%$  ; U.S. rates over the same period are   $2\%$  . What is the dollar value of a two-year European put on a single yuan if the exercise price of the put is USD0.20?  
14.  Consider an extension of the Exercise 21 from Chapter 8 concerned with the management of transactions exposure. The Smedley Company sold products to a Japanese client for  f 15,000,000. Payment is due six months later. Relevant data are as follows: Spot exchange rate:  $\uptau105/\upPhi$   $9.0\%$  Japanese borrowing interest rate: U.S. borrowing interest rate:  $7.0\%$  Japanese lending interest rate:  $7.0\%$  U.S. lending interest rate:  $5.0\%$  There exist currency call and put options with the following terms: Size of options contracts:  f 1,000,000 Term to expiration of options contracts: six months Exercise price of put and call:  $\S0.009$  / f Put premium:  $\S0.00001$  / f Call premium:   $\S0.0001$  / f Brokerage cost per options contract:  $\S50$  Discuss the implications associated with each of the options-based methods for managing the transactions exposure risk associated with this extension of credit.  
# 9. A.1 THE BINOMIAL MODEL: ADDITIONAL CONSIDERATIONS  

# A Computationally More Efficient Version of the Binomial Model  

Here, we simply discuss a computationally more efficient version of the    $n$  -time-period binomial model  Equation (9.17) :  

$$
c_{0}=\frac{\displaystyle\sum_{j=0}^{n}\frac{n!}{j!(n-j)!}p^{j}(1\!-\!p)^{n-j}\mathbf{M}\mathbf{A}\mathbf{X}\big[0,u^{j}d^{n-j}S_{0}-X\big]}{(1+r_{f})^{n}}
$$  

The number of computational steps required to solve  Equation (9.17)  is reduced if we eliminate from consideration all of those outcomes where the option’s expiration date price is zero. Thus, the smallest non-negative integer for    $j$   where    $S_{n}\,>\,X$   is the smallest integer that exceeds the following from  Equation (9.19) :  

$$
a=\mathbf{M}\mathbf{A}\mathbf{X}\left[\frac{\ln\left(\cfrac{X}{S_{0}d^{n}}\right)}{\ln\left(\cfrac{u}{d}\right)},0\right]
$$  

This result is obtained by first determining the minimum number of price increases    $j$  needed for  $S_{n}$   to exceed    $X$  :  

$$
S_{n}=u^{j}d^{n-j}S_{0}>X
$$  

We then solve this inequality for the minimum non-negative integer value for  $j$   such that  $u_{j}d^{n-j}S_{0}{>}X.$  . Take logs of both sides to obtain:  

$$
\begin{array}{r l}&{j\cdot\ln(u)+n\cdot\ln(d)-j\cdot\ln(d)+\ln(S_{0})>\ln X}\\ &{j\cdot\ln\left(\frac{u}{d}\right)>\ln(X)-n\cdot\ln(d)-\ln(S_{0})}\end{array}
$$  

Next divide both sides by    $l n(u/d)$   and simplify to obtain  Equation (9.19) , where    $a$   is the smallest non-negative integer for  $j$   for which    $S_{n}>X$  . Finally, we substitute  Equation (9.19) into  Equation (9.7)  to obtain  the binomial option pricing model :  

$$
c_{0}=\frac{\displaystyle\sum_{j=a}^{n}\frac{n!}{j!(n-j)!}p^{j}(1\!-\!p)^{n-j}\big[u^{j}d^{n-j}S_{o}-X\big]}{\displaystyle(1+r_{f})^{n}}
$$  
Or  

$$
c_{0}=S_{0}\left[\sum_{j=a}^{n}\frac{n!}{j!(n-j)!}\frac{(p u)^{j}[(1-p)d]^{n-j}}{{(1+r_{f})}^{n}}\right]-\frac{X}{(1+r_{f})^{n}}\left[\sum_{j=a}^{n}\frac{n!}{j!(n-j)!}p^{j}(1-p)^{n-j}\right]
$$  

In short-hand form:  

$$
c_{0}=S_{0}B_{1}[a,n,p^{\prime}]-X(1\!+\!r_{f})^{-n}B_{2}[a,n,p]
$$  

where    $p^{\prime}=p u/(1+r_{f})$  . There are two more points regarding  Equation (9.18b) . First, assuming that investors behave as though they are risk neutral,    $B_{2}[a,\,n,\,p]$   can be interpreted as the probability that the stock price will be sufficiently high at the expiration date of the option to warrant its exercise. Second,    $B_{1}[a,\ n,\ p^{\prime}]$   can be interpreted as a hedge ratio, although it must be updated at every period.  

# Obtaining Multiplicative Upward and Downward Movement Values  

One apparent difficulty in applying the binomial model as it is presented above is in obtaining estimates for    $u$   and    $d$   that are required for  $p;$   all other inputs are normally quite easily obtained. There are several methods that are used to obtain parameters for the binomial method from the actual security returns generating process. For example, following Cox et al. (1979) , we can begin the process of estimating the mean and variance to be used in the binomial distribution by first approximating the mean and variance for the binomial process from the historical Wiener process as follows:  

$$
E[S_{T}]=S_{0}\mathbf{e}^{\mu T+\frac{1}{2}\sigma^{2}T}\approx p u S_{0}+(1-p)d S_{0}
$$  

$$
\sigma_{s}^{2}T=S_{0}^{2}(\mathrm{e}^{\sigma^{2}T}-1)(\mathrm{e}^{2\mu T+\sigma^{2}T})\approx[p u^{2}S_{0}^{2}+(1-p)d^{2}S_{0}^{2}]-[p u S_{0}+(1-p)d S_{0}]^{2}
$$  

Approximation 2 approaches equality as    $T$   approaches zero. Scaling    $S_{0}$   to one such that we work with returns rather than actual security prices, the following can be used for returns variance of a binomial process:  

$$
\sigma^{2}=[p u^{2}+(1-p)d^{2}]-[p u+(1-p)d]^{2}
$$  

11 We will rewrite  Equation (9.A.1.5)  as follows :  

$$
\sigma^{2}=p(1-p)(u-d)^{2}
$$  

11 The following are algebraic steps to obtain  Equation (9.A.1.6)  from  Equation (9.A.1.5) :  $\begin{array}{r l}&{\sigma^{2}=\lfloor p u^{2}+(1-p)d^{2}\rfloor-[p u+(1-p)d]^{2}=\lfloor p u^{2}+d^{2}-p d^{2}\rfloor-\lfloor p^{2}u^{2}+(1-p)^{2}d^{2}+2p u(1-p)d}\\ &{\sigma^{2}=\lfloor p u^{2}+d^{2}-p d^{2}\rfloor-\lfloor p^{2}u^{2}+d^{2}+p^{2}d^{2}-2p d^{2}+2p u d-2p^{2}u d\rfloor}\\ &{\sigma^{2}=\lfloor p u^{2}\rfloor-\lfloor p^{2}u^{2}+p^{2}d^{2}-p d^{2}+2p u d-2p^{2}u d\rfloor}\\ &{\sigma^{2}=p(u^{2}-p u^{2}-p d^{2}+d^{2}-2u d+2p u d)=p(1-p)(u^{2}+d^{2}-2u d)}\end{array}$  c  
Assume that the binomial process will lead to expected return for a security equaling the riskless rate:  

$$
\mathbf{e}^{\mu T+\frac{1}{2}\sigma^{2}T}=\mathbf{e}^{r_{f}}\approx p u+(1-p)d
$$  

Solving  Equation (9.A.1.7)  for    $p$   enables us to estimate probabilities of an uptick    $p$   and downtick   $(1-p)$   as:  

$$
p={\frac{\mathrm{e}^{r_{f}}-d}{u-d}}\ \left(1-p\right)={\frac{u-\mathrm{e}^{r_{f}}}{u-d}}
$$  

If we define    $d$   as   $1/u$   such that    $u d=1,$  , we can rewrite  Equation (9.A.1.6) , the variance of returns, as follows:  

$$
\begin{array}{r}{\sigma^{2}=p(1-p)(u\!-\!d)^{2}=p(1-p)(\mathrm{e}^{\delta}\!-\!\mathrm{e}^{-\delta})^{2}}\end{array}
$$  

Thus, we have simply substituted some constant  $e^{\S}$    for    $u$  . Substituting    $\sigma$   for    $\delta$   will provide a good approximation for variance (improving as the number of jumps in the binomial process,    $n$   approaches infinity):  

$$
\sigma^{2}=p(1-p)(\mathrm{e}^{\delta}\!-\!\mathrm{e}^{-\delta})^{2}=p(1-p)(\mathrm{e}^{\sigma}\!-\!\mathrm{e}^{-\sigma})^{2}
$$  

Thus, we can use the following to estimate    $u$   and    $d$   in the binomial approximation to the Wiener process:  

$$
u=\mathbf{e}^{\sigma}\quad d=\frac{1}{u}
$$  

or, if  $n$   and    $T$   differ from 1,  

$$
u=\mathbf{e}^{\sigma{\sqrt{\frac{T}{n}}}}\quad d={\frac{1}{u}}
$$  

Suppose, for example, that for a particular Wiener process,    $\sigma=0.30$   and    $r_{f}\!=\!0.05$  . Using Equations (9.A.1.7) and (9.A.1.10) , we estimate  $p,\,u,$   and    $d$   for a single time period binomial process as follows:  

$$
\begin{array}{l}{u=\mathrm{e}^{0.3}=1.3498588}\\ {\mathrm{~}}\\ {d={\frac{1}{u}}=0.7408182}\end{array}
$$  

We can verify our estimates with  Equations (9.A.1.6) and (9.A.1.9)  as follows:  

$$
\mathrm{e}^{0.005+\frac{1}{2}\times0.3^{2}}=\mathrm{e}^{0.05}
$$  

$$
=0.5097409\times1.3498588+(1-0.5097409)\times0.7408182=1.0512
$$  

$$
\boldsymbol{\tau}^{2}=p(1-p)(\mathrm{e}^{\delta}-\mathrm{e}^{-\delta})\approx0.5097409\times(1-0.5097409)(\mathrm{e}^{0.3}-\mathrm{e}^{-0.3})^{2}=0.0926974
$$  

As discussed above, there are several procedures for getting parameters  $\sigma,\,u,\,d,$  , and  $p$   for the binomial distribution. This procedure is probably the most commonly used, in part, because it provides a relatively straightforward method for estimating option Greeks.  
The primary difficulty with the one presented above is that it may result in negative probabilities. An additional methodology for estimating binomial distribution parameters is given in  Jarrow and Turnbull (1999: 136  138) .  

# 9. A.2 DERIVING THE BLACK-SCHOLES MODEL  

For this derivation, we shall assume that all standard Black-Scholes assumptions (see The Greeks and Hedging in a Black-Scholes Environment section) hold and that investors behave as though they are risk neutral. That is, investors price options as though they are risk neutral because they can always construct riskless hedges comprising options and their underlying securities, and that the returns of these hedged portfolios must be the riskless rate. The law of one price dictates that the current value of a call    $c$   on stock can be found from constructing a hedge portfolio:  

$$
c=\#s S+\#b B
$$  

$S$   is the current value of its underlying stock and    $B$   is the current value of a riskless Treasury instrument. Let # s  be the number of shares of stock to purchase and  $\#b$   be the number of Treasury instruments to short in order to replicate the cash flow structure of the call. Similarly, we can replicate the cash flow structure of a single bond as follows:  

$$
B=\#s S+c
$$  

Let    $V_{h}=B$   represent the value of a perfectly hedged portfolio. We can rewrite the above equation in terms of    $V H$   as follows:  

$$
V_{h}=c+\#s S
$$  

Since the hedge is riskless, its return should equal the riskless rate:  

$$
d V_{h}=r_{f}V_{h}d t=d c+\#s d S
$$  

The hedge requires that we short sell # s  shares of stock for each call that we purchase. The sensitivity of the call price to the stock price is    $\partial c/\partial S.$  . Thus, the hedge will require that we short  $\partial c/\partial S$   shares for each purchased call. We write the value of the hedge portfolio and rewrite its differential equation as follows:  

$$
V_{h}=c-\frac{\partial c}{\partial S}S
$$  

$$
r_{f}V_{h}d t=d c-\frac{\partial c}{\partial S}d S
$$  

We rearrange the above differential equation by substituting for    $V_{h}$   and solving for  $d c$  :  

$$
d c=r_{f}\left[c-{\frac{\partial c}{\partial S}}S\right]d t+{\frac{\partial c}{\partial S}}d S
$$  
which is rewritten as follows:  

$$
d c=r_{f}c d t-r_{f}\frac{\partial c}{\partial S}S d t+\frac{\partial c}{\partial S}d S
$$  

We shall assume that the instantaneous price change for the stock follows an Itoˆ process:  

$$
d S=\mu S d t+\sigma S d z
$$  

which requires us to use Itoˆ’s lemma to solve for  $d c$  . Substituting this Wiener process for  $d S$   into the preceding equation, we obtain the following:  

$$
d c=r_{f}c d t-r_{f}\frac{\partial c}{\partial S}S d t+\frac{\partial c}{\partial S}(\mu S d t+\sigma S d z)
$$  

We will rewrite  Equation (9.A.2.9)  separating out the term in the parentheses as follows:  

$$
\begin{array}{c}{d c=r_{f}c d t-r_{f}\displaystyle\frac{\partial c}{\partial S}S d t+\displaystyle\frac{\partial c}{\partial S}\mu S d t+\displaystyle\frac{\partial c}{\partial S}\sigma S d z}\\ {d c=\mu S\displaystyle\frac{\partial c}{\partial S}d t+\displaystyle\frac{\partial c}{\partial t}d t+\displaystyle\frac{1}{2}S^{2}\sigma^{2}\displaystyle\frac{\partial^{2}c}{\partial S^{2}}d t+\sigma S\displaystyle\frac{\partial c}{\partial S}d z}\end{array}
$$  

Note that the first and fourth terms in  Equation (9.A.2.11)  are identical to the third and fourth terms in  Equation (9.A.2.10) . Furthermore,  Equations (9.A.2.10) and (9.A.2.11)  solve for  dc . This means that the second and third terms in  Equation (9.A.2.11)  are identical to the first and second terms in  Equation (9.A.2.10) :  

$$
r_{f}c d t-r_{f}\frac{\partial c}{\partial S}S d t=\frac{\partial c}{\partial t}d t+\frac{1}{2}S^{2}\sigma^{2}\frac{\partial^{2}c}{\partial S^{2}}d t
$$  

which, after dividing by  $d t,$   is rewritten:  

$$
\frac{\partial c}{\partial t}=r_{f}c-r_{f}\frac{\partial c}{\partial S}S_{t}-\frac{1}{2}S^{2}\sigma^{2}\frac{\partial^{2}c}{\partial S^{2}}
$$  

This is the Black-Scholes differential equation. Its particular solution, subject to the  boundary condition   $c_{T}=\mathrm{MMAX}[0,S_{T}-\mathit{X}],$  , is given by  Equations (9.A.2.14)  through  (9.A.2.16) :  

$$
c_{0}=S_{0}N(d_{1})-\frac{X}{\mathbf{e}^{r_{f}T}}N(d_{2})
$$  

$$
d_{1}={\frac{\ln\left({\frac{S_{0}}{X}}\right)+\left(r_{f}+{\frac{1}{2}}\sigma^{2}\right)T}{\sigma{\sqrt{T}}}}
$$
 ﬃﬃﬃﬃ  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  
where    $N(d^{*})$   is the cumulative normal distribution function for   $(d^{*})$  . This function is frequently referred to in a statistics setting as the    $z.$  -value for   $(d^{*})$  . This solution to the Black-Scholes differential equation can be verified by finding the derivative of    $c_{0}$   in the Black-Scholes model with respect to  t . From a computational perspective, one would first work through  Equation (9.A.2.15)  and then  Equation (9.A.2.16)  before valuing the call with Equation (9.A.2.14) .  
