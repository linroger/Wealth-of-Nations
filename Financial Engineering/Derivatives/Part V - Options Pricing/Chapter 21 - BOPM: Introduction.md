---
tags:
  - binomial_option_pricing_model
  - bopm
  - delta_hedging
  - european_call_option
  - risk_neutral_valuation
aliases:
  - BOPM
  - Binomial Model
  - Option Pricing
key_concepts:
  - Binomial option pricing model
  - Delta hedging
  - European call option
  - Risk-free arbitrage portfolio
  - Risk-neutral valuation
---
# OPTIONS PRICING  

# BOPM: Introduction  

# Aims  

• To demonstrate how the binomial option pricing model (BOPM), is used to determine option premia by establishing a risk-free arbitrage portfolio consisting of a position in stocks and the option – this is delta hedging.   
• To show how delta hedging and the no-arbitrage approach can be interpreted in terms of risk-neutral valuation (RNV), which allows us to price options using a simple backward recursion.   
• To demonstrate how RNV leads to other useful approaches to pricing options such as Monte Carlo simulation.  

We present a detailed account of the BOPM for pricing options using the no-arbitrage principle – the option is priced so that traders faced with this ‘BOPM price’ cannot undertake trades which result in risk-free profts. We construct a risk-free portfolio from two risky assets, namely calls and stocks. Using the principle of delta hedging, whereby the proportions held in stocks and the option gives a risk-free portfolio (over small intervals of time) – we obtain the BOPM formula for the price of the option. We then interpret the BOPM formula in terms of risk-neutral valuation (RNV). Using insights from RNV we can then price an option without going through all the details involved in delta hedging and forming a ‘risk-free arbitrage portfolio’ – instead we price the option directly by using the BOPM formula and ‘backward recursion’.  

# 21.1 ONE-PERIOD BOPM  

To understand delta hedging and risk-neutral valuation we frst price a European call option (on a non-dividend paying stock), which has one period to expiration. The basic idea is to construct a portfolio consisting of the call option and some stocks, so that the portfolio is risk-free (over a small interval of time).  

The current stock price is $S=100$ and the stock pays no dividends. Consider a one-period problem where there are only two possible outcomes for the stock price at $t=1$ , namely an ‘up’ move with $U=1.1$ and a ‘down’ move with $D=0.9$ , hence:  

$S=100=$ stock price today $S_{u}=S U=110=$ stock price after an ‘up’ move, ${\cal S}_{d}={\cal S}{\cal D}=90=$ stock price after a ‘down’ move. $K=100=$ strike price of a call option, $r=0.05=$ one-period risk-free rate of interest $C=$ the unknown call premium (i.e. price of the call)  

Suppose the ‘real world’ probability of the stock price moving up or down is $p=1/2$ , so the ‘real world’ expected stock price at $t=1$ is $E S_{1}=100=1/2(110)+1/2(90)$ and since $S=100$ the expected stock return $\mu=(E S_{1}/S)-1=0$ . As we see below, somewhat surprisingly, neither the ‘real world’ probability $p$ of a rise in the stock price nor the ‘real world’ expected return on the stock $\mu$ determine the call premium.  

The payofs when holding either one stock or one long call are given in Figure 21.1. Note that if the payof to a long call is $+10$ (at $t=1\dot{}$ ), then the payof to a short (sold/written) call is $-10$ . The diference between the two possible outcomes for the stock is $S_{u}-S_{d}=20$ and for the call is $C_{u}-C_{d}=10\$ . We defne the hedge ratio as $h=(C_{u}-C_{d})/(S_{u}-S_{d})=1/2$ .  

Below, we see that if today $(t=0)$ Ms Arb sells one call and buys $^1/_{2}$ stock (or alternatively if Ms Arb sells 100 calls and buys 50 stocks) then she has set up a risk-free portfolio (over a small interval of time). To be ‘risk-free’ this portfolio must have a known value at $t=1$ no matter what the values of the stock price and call premium are at $t=1$ . To set up this ‘hedge portfolio’ involves a cash outlay at time $t=0$ but because the payof at $t=1$ is known, Ms Arb’s hedge portfolio must have a return equal to the risk-free rate – or proftable arbitrage opportunities are possible. Consider the payof to portfolio-A where Ms Arb is long $1/2$ -stock and short 1-call.  

![](1ae91ac67892ebef35a6c011b6bbf2f3d2f220c03dbb09749df26a0ccb2ab5b4.jpg)  

Payof to Portfolio-A: long 1/2 stock, short 1-call  

$$
\begin{array}{r l}&{\mathrm{Payofffor~price~rise}=\left(1/2\right)\left(110\right)-10=45}\\ &{\mathrm{Payoff~for~price~fall}=\left(1/2\right)\left(90\right)-0\quad=45}\end{array}
$$  

The payof to portfolio-A at $t=1$ is known with certainty, no matter what the outcome for the stock price (i.e. either 110 or 90). Ms Arb has created a risk-free portfolio using a hedge ratio of $h=1/2$ . The cost of constructing portfolio-A at $t=0$ is the cost of buying the stocks less the receipt from the sale of the call, that is, $(1/2)100-C$ . Portfolio-A is risk-free and if there are to be no arbitrage profts to be made, portfolio-A must earn the risk-free rate:  

$$
\begin{array}{c}{1+r={\frac{C e r t a i n p a y o u t\ a t\ t=1}{C o s t o f i n i t i a l\ i n\nu e s t m e n t\ a t\ t=0}}}\\ {1.05={\frac{45}{(1/2)100-C}}}\end{array}
$$  

Therefore the ‘fair’, ‘correct’ or ‘no-arbitrage’ price of the call is $C=7.1428571$ . Alternatively, if you borrow $(1/2)100-C$ to set up portfolio-A then you will owe the bank $[(1/2)$ $100-C]1.05$ at $t=1$ and for no arbitrage profts to be made, this must equal the (known) payof of 45 at $t=1$ :  

Bank debt $t=1$ ) $\c=$ payof from portfolio- $t=1$  

$$
[(1/2)100-C]1.05=45\
$$  

Again the solution to Equation (21.2) is $C=7.1428571$  

# 21.1.1 Arbitrage: Overpriced Call  

The fair price of the option is $C=7.143$ – otherwise risk-free arbitrage profts can be made. To see this, suppose the actual quoted option premium (by all option traders) is $C_{q}=\$10$ which exceeds the BOPM ‘fair price’ $C=7.143$ – the call is overpriced. Ms Arb spots this pricing anomaly. As usual, Ms Arb ‘sells high and buys low’. At $t=0$ , she sells (writes) the overpriced call and receives $C_{q}=\$10$ and hedges by purchasing $^1/_{2}$ a stock at $\mathrm{\DeltaS}=100\mathrm{\Omega}$ , at a net cost of $\$40$ , which she borrows from the bank. The guaranteed cash value of this hedged ‘portfolio-A’ at $t=1$ is $\$45$ (no matter whether the stock price goes up or down) and as she owes the bank $\$42$ ( $\dot{\mathbf{\xi}}=\$40\times1.05$ she makes an arbitrage proft of $\$3$ .  

Viewed slightly diferently, the net cost of setting up portfolio-A at $t=0$ is $\$40$ $(=(1/2)100{-}10)$ and if Ms Arb uses her ‘own funds’ of $\$40$ today then her return is  

$7.5\%(=\S3/\S40)$ , which is in excess of the risk-free (borrowing) rate of $5\%$ – again indicating risk-free arbitrage profts.  

Note that there will be lots of traders who try to implement this risk-free, yet proftable strategy. Selling calls would tend to lead to a fall in the quoted price of $C_{q}=10$ and move it towards the ‘fair’ no-arbitrage price $C=7.143$ . Hence, we expect the quoted call premium to deviate from its (BOPM) fair price only by a small amount and for any discrepancies to be quickly eliminated by the actions of arbitrageurs.  

# 21.1.2 Arbitrage: Underpriced Call  

Consider how to make arbitrage profts if the call is temporarily underpriced at a quoted price $C_{q}=\$7$ . Ms Arb buys low, sells high. So today, she buys the call at $C_{q}=7$ and hedges this position by short-selling $^1/_{2}$ stock, for which she receives $\$50~(=$ at $t=0$ . Her net cash infow at $t=0$ is $\$43$ $(=50-7)$ . This can be invested at the risk-free rate to give receipts at $t=1$ of $\$45.15$ $\mathit{\check{\Psi}}=43\times1.05\$ . Ms Arb’s hedged portfolio will be worth minus $\$45$ at $t=1$ – that is, when she closes out all her short stock and long call positions she will have lost $\$45$ (regardless of whether the stock price rises or falls). Hence she makes an overall proft at $t=1$ of $\$0.15$ .  

# 21.1.2.1 Formal Derivation  

We now derive the price of the call option algebraically. The two outcomes for the stock price are $S_{u}=S U$ and $S_{d}=S D$ (where in our example $U=1.1$ and $D=0.9$ as shown in Figure 21.1).1 Let:  

$$
\begin{array}{r}{C_{u}=\mathrm{payoff~to~a~long~call~if~the~stock~price~is~}S_{u}}\\ {C_{d}=\mathrm{payoff~to~a~long~call~if~the~stock~price~is~}S_{d}}\end{array}
$$  

Hence:  

$$
\begin{array}{r l r}{C_{u}=S_{u}-K=S U-K}&{{}\quad}&{(\mathrm{for}S_{u}>K\mathrm{otherwise}C_{u}\mathrm{~;}}\\ {C_{d}=S_{d}-K=S D-K}&{{}\quad}&{(\mathrm{for}S_{d}>K\mathrm{otherwise}C_{d}\mathrm{~;}}\end{array}
$$  

Portfolio-A: long $h$ -stocks, short 1-call  

$$
\begin{array}{r l}{\mathrm{Payoffforpriceriseat}t=1\quad}&{V_{u}=h S_{u}-C_{u}}\\ {\mathrm{Payoffforpricefallat}t=1\quad}&{V_{d}=h S_{d}-C_{d}}\end{array}
$$  

The payof to a long call at $t=1$ is $C_{u}$ or $C_{d}$ so the payof to a short call is $-C_{u}$ or $-C_{d}$ . For the two payofs to be equal:  

$$
\begin{array}{c l}{{h S_{u}-C_{u}=h S_{d}-C_{d}}}\\ {{{}}}\\ {{h=\displaystyle\frac{(C_{u}-C_{d})}{S_{u}-S_{d}}=\displaystyle\frac{(C_{u}-C_{d})}{S(U-D)}=\displaystyle\frac{(10-0)}{100(0.2)}=\displaystyle\frac{1}{2}}}\end{array}
$$  

In the above analysis we are short one call and (21.4) indicates that the hedge will then involve going long $h$ -stocks. The formula for the hedge ratio $h$ in (21.4) is the change in value of the option divided by the change in value of the stock and this is the option’s ‘delta’ – hence this approach is called delta hedging. Given the risk-free portfolio-A, we determine the call premium $c$ by equating the amount of bank debt owed at $t=1$ (due to the cost of setting up portfolio-A at $t=0$ ), with the known payof from portfolio-A at $t=1$ :  

Bank debt $t=1$ $\mathbf{\tau}=\mathbf{\tau}$ payof from portfolio- $t=1$ )  

$$
(h S-C)(1+r)=h S U-C_{u}
$$  

Substituting from Equation (21.4) for $h$ and (carefully) rearranging, the BOPM equation for the call premium is:  

$$
\begin{array}{l}{{C=\displaystyle\frac{1}{R}\left[q C_{u}+(1-q)C_{d}\right]}}\\ {{R=1+r}}\end{array}
$$  

and  

$$
q=(R-D)/(U-D)
$$  

# 21.2 RISK-NEUTRAL VALUATION  

Note that the formula for the call premium does not depend on the ‘real world’ probability $p$ of an ‘up’ move for the stock price (and hence is independent of the ‘real world’ expected return $\mu$ on the stock). In the formula for the call premium the ‘weights’ applied to the two option payofs $C_{u}$ and $C_{d}$ are $q$ and $1-q$ (which sum to unity), but there is little intuitive insight at present to be gleaned from Equation (21.6c) for $q$ .  

The ‘weight’ $q$ is known as the risk-neutral probability of a rise in the stock price, which must not be confused with the actual ‘real world’ probability of a rise in the stock price $p$ . The risk-neutral probability is simply a number which lies between 0 and 1 and is derived under the assumption that portfolio-A is risk-free.2 The expected payof to the option, using risk-neutral probabilities is:  

$$
E x p e c t e d p a y o f f t o l o n g c a l l o p t i o n=\left[q C_{u}+(1-q)C_{d}\right]
$$  

In some ways the term ‘risk-neutral probability’ could be misleading since it appears to imply that we are assuming investors are ‘risk neutral’ and hence do not care about risk. Investors in options do care about the level of risk they hold but in the BOPM they can set up a risk-free hedge portfolio and by defnition this has zero risk. An alternative is to call $q$ , an equivalent martingale probability and the latter is used frequently in the continuous time literature. However, we will stick with the more commonly used term, ‘risk-neutral probability’. Using Equation (21.6a) we can price the option using the risk-neutral probability $q$ and this method of pricing is known as risk-neutral valuation (RNV) and it plays a major role in the pricing of all types of options. Hence we can now state:  

The call premium $c$ is the expected payof at maturity, where the expectation uses risk-neutral probabilities $(q,1-q)$ and the expected payof is discounted using the risk-free rate.  

$q$ is not a ‘real probability’ it is a ‘pseudo-probability’: $q$ lies between 0 and 1 and the sum of $q$ and $1-q$ for the two possible outcomes is 1. But why is $q$ known as a risk-neutral probability? We use a ‘what if’ argument here, to help explain the term, ‘risk-neutral probability’. If the probability of an ‘up’ move equals $q$ , then what would we expect the stock price to be at $t=12$ This is given by:  

$$
r=5\%
$$  

where $E^{*}$ is the expected value, using risk-neutral probabilities.  

But the initial stock price is $S=100$ , so if we interpret $q$ as the probability of an ‘up’ move then this implies that the stock price (in the BOPM) is expected to grow at $5\%(=(105/100)-1)$ . But this is also the value of the risk-free rate, $r=5\%$ . Hence, the no-arbitrage BOPM price for the option given by Equation (21.6a) is consistent with the assumption that the stock price grows at a rate (or has an expected return) equal to the risk-free interest rate. Confused? Yes, RNV is a tricky concept. However, it turns out to be a brilliant insight since it allows us to price very complex options by:  

• using the ‘pseudo-probabilities’ $q$ , to ‘weight’ the option payofs, to give an ‘expected payof’ to the option (in a risk-neutral world).   
• Discount these expected payofs using the risk-free rate, to give the correct no-arbitrage price of the option.  

Rather miraculously we obtain the correct no-arbitrage ‘real world’ option price using the above two assumptions, even though in the real world the stock price does not grow at the risk-free rate.3 As long as we use our two ‘tricks’, they compensate for each other and enable us to obtain the ‘fair’ or ‘correct’ (i.e. no-arbitrage) option price, in the real world. What do we mean by ‘correct’? We mean a price for the option that does not allow any risk-free arbitrage profts to be made in the ‘real world’ – now that does sound sensible and ‘real’.  

Finally note that in Equation (21.6a) neither the actual probability $p$ of a rise in the stock price nor the real world growth rate of the stock $\mu$ , nor the risk preferences of investors, enter into the calculation of the price of the call. Hence all investors, regardless of their difering degrees of risk aversion or their diferent guesses about the ‘real world’ probability of a rise or fall in future stock prices can agree on the ‘fair’ or ‘correct’ price for a call option.  

# 21.2.1 RNV and No-arbitrage  

We can use some more tricks. If $q$ really is a risk-neutral probability, then in a risk-neutral world, the expected return on a stock must equal the risk free rate and hence $q$ must satisfy:  

$$
E^{*}(S_{1})=(S U)q+(1-q)S D=S\ R
$$  

From Equation (21.8) we can immediately deduce that $q=(R-D)/(U-D)=0.75$ which we know to be true from our ‘no-arbitrage’ approach. Similarly, in $a$ risk-neutral world the call option has a $q=0.75$ chance of being worth $C_{u}=10$ and a 0.25 chance of being worth $C_{d}=0$ . Hence its expected value (at $t=1$ ) in this risk-neutral world is:  

$$
E^{*}(C_{1})=0.75\left(10\right)+0.25\left(0\right)=7.5
$$  

Discounting at the risk-free rate, the call premium at $t=0$ in a risk-neutral world is:  

$$
\mathrm{C}=\left(1/R\right)E^{*}(C_{1})=(1.05)^{-1}7.5=7.143
$$  

Thus, using RNV the BOPM Equation (21.6a) gives the same value for $c$ as when we use the full ‘no-arbitrage’ approach. This establishes the equivalence of the two approaches. When pricing an option, if you interpret $q$ as the probability of an ‘up’ move, this is equivalent to assuming the expected stock return is equal to the risk-free rate $r\mathrm{~-~}$ that is, you are in a risk-neutral world. However, the resulting value for the option premium using Equation (21.6a) is valid in the real world, since Equation (21.6a) is consistent with no risk-free arbitrage profts. This is the principle of RNV.  

Using RNV we could say that the call premium at any time $t-1$ is given by:  

$$
C_{t-1}=(1/R)(E^{*}C_{t})
$$  

where $E^{*}(C_{t})$ is the expected payof to the option at time $t$ , and the expectation $E^{*}(C_{t})$ assumes we are in a risk-neutral world – that is, the stock price grows at the risk-free rate. This is also the basis for pricing options using Monte-Carlo simulation (MCS), as we see later. MCS involves simulating the stock price assuming the expected stock return equals the risk-free rate $(\mu=r)$ , calculating the expected payof from the option at maturity $T$ and discounting this expected payof using the risk-free rate.  

# 21.3 DETERMINANTS OF CALL PREMIUM  

# 21.3.1 Call Premium and Stock Returns  

Somewhat counter-intuitively the binomial pricing formula implies that if we have two otherwise identical call options (i.e. same strike price, expiration date, and same stock return volatility) but the underlying stock-A for one of the options has a ‘real world’ expected return of $\mu=0$ , while the other stock-B, has an expected return of $\mu=100\%$ p.a. (say), then the two options will have exactly the same call price. This is because in each case we can create a risk-free hedge portfolio, which by arbitrage arguments can only earn the risk-free rate. Put another way, the call premium is independent of the ‘real world’ expected return of the underlying stock, $\mu$ .  

# 21.3.2 Call Premium and Volatility  

Note, however, that we are not saying that the call premium is independent of the volatility of the underlying stock (represented in the BOPM by $S_{u}-S_{d}$ or equivalently $^{\cdot}U-D^{\prime}$ , which enters the defnition of $\displaystyle q$ ).4 Expected growth and volatility are very diferent concepts. After all, we can have a stock price with an expected growth (return) of zero but we may feel that the range of possible outcomes (around its expected value of zero) is very large. In our simple one-period model the call premium does depend on the range of possible values for $S\mathrm{~-~}$ that is on $U$ and $D\mathrm{~-~}$ which measure the volatility of the stock price in the BOPM (and as we have seen, volatility also plays a key role in the Black–Scholes option price formulas).  

To show that the call premium depends positively on the volatility of the stock, go back to our original example where $S_{u}=110$ and $S_{d}=90$ and the ‘volatility’ $S_{u}-S_{d}=20$ . Now change the volatility of the stock price, by assuming $S_{u}=120$ ( $U=1.2)$ and $S_{d}=80$ $(D=0.8)$ , so the volatility increases to $S_{u}-S_{d}=40$ . The ‘real world’ expected stock price (at $t=1\AA$ ) with $p=1/2$ is $S_{u}-S_{d}=20$ and the ‘real world’ expected return remains unchanged at $\mu=(E S_{1}/S_{0})-1=0\%$ .  

The payof to the call is either $C_{u}=20$ or $C_{d}=0$ . Also $q=(1.05-0.8)/(1.2-0.8)=0.625$ and hence using Equation (21.6a) the call premium $C=(0.625)20/1.05=11.905,$ ,5 which is higher than the call premium of $C=7.1428$ (when we assumed stock price volatility was lower (i.e. $S_{u}-S_{d}=20)$ ).  

Of course, the above examples have two key simplifying assumptions, namely that there are only two possible outcomes for the stock price and that the option expiration is after one period. However, by extending the number of branches in the binomial ‘tree’ we can obtain a large number of possible outcomes for the stock price. If we consider each ‘branch’ as representing a short time period, then conceptually we can see how the BOPM ‘approaches’ a continuous time formulation, which forms the basis of the famous Black–Scholes approach.  

# 21.4 PRICING A EUROPEAN PUT OPTION  

We can price a one-period put option by constructing a similar risk-free portfolio of stocks and the put. But this time the risk-free portfolio-B is obtained by going long some stocks and simultaneously going long one put. So, if $s$ falls the loss on the stock will be ofset by the gain on the put, making the portfolio of ‘stock $^+$ put’, risk-free. The payof to the put is max $(0,K-S_{T})$ . If $K=100$ (as before, Figure 21.2) then for $S_{u}=110$ the put payof is $P_{u}=0$ and for $S_{d}=90$ we have $P_{d}=10$ .  

The hedge ratio is $h_{p}=-(P_{u}-P_{d})/(S_{u}-S_{d})={}^{1}/2$ . For each long put option a delta hedge requires the purchase of $\%$ stock. The cost of setting up the delta hedge at $t=0$ is $(1/2)S+P$ and the payof at $t=1$ is:  

![](1268225356b19991e3b34c496a8a28ef0f5a8c62e73803030786cf5b04055b17.jpg)  

Payof to Portfolio-B: long 1/2-stock $^+$ long 1-put  

Equating the return on the risk-free hedge portfolio-B to the risk-free rate gives:  

$$
\frac{55}{(1/2)100+P}=1.05
$$  

Hence $P=2.38\$ . Alternatively using the BOPM risk-neutral valuation formula, we directly obtain the put premium:  

$$
P=\frac{1}{R}\left[q P_{u}+(1-q)P_{d}\right]=\frac{(0.75)0+(0.25)10}{1.05}=2.381
$$  

where (again) $q=(R-D)/(U-D)=0.75$ . Equation (21.13) has the same form as that for the call premium except that we use the put payofs $P_{u}$ and $P_{d}$ . The BOPM put premium $P=2.381$ can be checked by using put–call parity.  

$$
P=C-S+K/(1+r)=7.143-100+100/(1.05)=2.381
$$  

# 21.5 SUMMARY  

• By constructing a risk-free portfolio consisting of the option and the underlying stock and delta hedging, the BOPM can be used to determine the ‘no-arbitrage’ call and put premia.   
• The hedge ratio is given by the delta of the option.   
• The call and put premia are determined by (i) the current stock price S, (ii) the risk-free rate $R=1+r$ , (iii) $U$ and $D$ (which can be shown to determine the stock return volatility), (iv) $q=(R-D)/(U-D)$ , the risk-neutral probability, and (v) the time to maturity, $T$ . The option premia do not depend on the real-world expected stock return, $\mu$ .   
• The parameter $q$ can be interpreted as a risk-neutral probability of an ‘up’ move and two key results follow. First, the option premium ( $\overrightharpoon{C}$ or $P,$ given by the BOPM is the expected payof to the option at $T$ , using risk-neutral probabilities $q$ and the payof is discounted at the risk-free rate. Second, the BOPM formula Equation (21.6) derived via arbitrage is consistent with the assumption that the expected growth rate of the stock price equals the risk-free rate. This is risk-neutral valuation (RNV).   
• RNV provides a way of obtaining the correct value for option premia using the BOPM Equation (21.6), which involves backward recursion – this considerably simplifes the calculations. But behind this approach is the assumption that options traders have eliminated any risk-free arbitrage opportunities.   
• RNV also leads to other useful approaches to pricing options such as Monte Carlo simulation.  

# APPENDIX 21: NO-ARBITRAGE CONDITIONS  

We show that there are arbitrage opportunities if the inequalities $U>R>D$ do not hold for the underlying asset (stock), with current price S. First, note that it is always the case that $U>D$ (by construction). Consider the arbitrage opportunity when $D>R$ (and hence $U>R$ ). Here the outcome for either $U$ or $D$ is greater than the cost of borrowing. Hence at $t=0$ , borrow $s$ (e.g. bank loan) and buy the stock for $S-$ the net cash fow is zero (Table 21.A.1). The outcome for either $U$ or $D$ at $t=1$ is a debt to the bank of $R S$ . But at $t=1$ the value of the long position in the stock is either $S U$ or $S D$ and the net position is either $S(U-R)>0$ or $S(D-R)>0.$ This is an arbitrage opportunity as the net cash fow at $t=0$ is zero but there is a positive cash fow at $t=1$ , for both the $U$ and $D$ outcomes.  

For $R>U>D$ , the risk-free rate exceeds the return on the stock for both the $U$ and $D$ outcomes. The arbitrage strategy at $t=0$ involves short-selling the stock at $s$ and investing the proceeds (in a bank deposit) which accrues to $R S$ (Table 21.A.2). The cost of buying back the stock at $t=1$ is either $S U$ or $S D$ . Hence there is a zero cash fow at $t=0$ and a positive cash fow of either $S(R-U)>0$ or $S(R-D)>0$ at $t=1$ .  

TABLE 21.A.1 Case A: $U>D>R$   


<html><body><table><tr><td>Action</td><td>Cash Flow, t=0</td><td>Cash Flow 'Up-Move', t=1</td><td>Cash Flow 'Down Move', t=1</td></tr><tr><td>Borrow $S @ R</td><td>-S</td><td>-SR</td><td>-SR</td></tr><tr><td>Buy stock @ S</td><td>+S</td><td>SU</td><td>SD</td></tr><tr><td>Net cash flow</td><td>0</td><td>S(U - R)> 0</td><td>S(D -R)>0</td></tr></table></body></html>  

TABLE 21.A.2 Case B: $D<U<R$   


<html><body><table><tr><td>Action</td><td>Cash Flow, t=0</td><td>Cash Flow 'Up-Move', t=1</td><td>Cash Flow 'Down Move', t =1</td></tr><tr><td>Short-sell stock @ S</td><td>+S</td><td>-SU</td><td>-SD</td></tr><tr><td>Invest $S @ R</td><td>-S</td><td>SR</td><td>SR</td></tr><tr><td>Net cash flow</td><td>0</td><td>S(R-U)>0</td><td>S(R -D)> 0</td></tr></table></body></html>  

# EXERCISES  

# Question 1  

Show that the risk-neutral probability $q=(R-D)/(\mathrm{U}-D)$ in the (one-period) BOPM is consistent with the assumption that the underlying stock price $s$ (which pays no dividends) grows at the risk-free rate. $R=1+r$ , where $r=$ risk-free rate (per period, simple interest).  

# Question 2  

In the context of the equation to determine the call premium in the one-period BOPM, explain and interpret the equation for the call premium, using the concept of a risk-neutral probability.  

# Question 3  

In the one-period BOPM the current stock price $S=90$ , $U=1.1$ and $D=0.9$ . A one-period European call option (on a non-dividend paying stock) has $K=90$ . The risk-free interest rate is $r=2\%$ per period (simple interest).  

(a) Form a risk-free (hedge) portfolio, assuming you sell one call and hedge using stocks. Price the call option by showing that there are zero profts from your hedge portfolio at $t=1$ .   
(b) What is the value of the hedge portfolio at $t=1$ (for the two stock price outcomes)?   
(c) What is the return on the hedge portfolio between $t=0$ and $t=1?$  

# Question 4  

In the one-period BOPM the current stock price $S=90$ , $U=1.1$ and $D=0.9$ . A one-period European put option (on a non-dividend paying stock) has $K=90$ . The risk-free interest rate is $r=2\%$ per period (simple interest).  

(a) Form a risk-free (hedge) portfolio, assuming you buy one put and hedge using stocks. Price the put option by showing that there are zero profts from your hedge portfolio at $t=1$ .   
(b) What is the value of the hedge portfolio at $t=1$ (for the two stock price outcomes)?   
(c) What is the return on the hedge portfolio between $t=0$ and $t=1?$   
(d) If the price of a call option (same strike, underlying stock and time to maturity) is $C=5.2941$ , show that the put premium satisfes put–call parity.  

# Question 5  

In the one-period BOPM the current stock price $S=90$ and $U=1.1$ and $D=0.9$ . A one-period European put option (on a non-dividend paying stock) has $S=90$ . The risk-free interest rate is $r=2\%$ per period (simple interest).  