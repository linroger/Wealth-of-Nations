---
tags:
  - black_scholes_model
  - corporate_debt
  - equity_collar
  - equity_warrants
  - options_theory
aliases:
  - Advanced Options
  - Merton Model
  - Risk Reversal
  - Zero Cost Collar
key_concepts:
  - Black-Scholes formula
  - Corporate debt valuation
  - Equity collar strategy
  - Equity warrants explained
  - European call option
---
# ADVANCED OPTIONS  

# Other Options  

# Aims  

• To show how a corporate’s debt and equity can be valued using options theory.   
• To examine di!erent types of equity warrants, which are long-term options on a company’s stock.   
• To examine quantos which are long-term equity options written on foreign stocks but with the payout in the home currency.   
• To show how an equity collar enables a portfolio manager to set an upper and lower limit on the performance of her existing equity portfolio. If this is achieved at zero ‘up-front’ cost then it is known as a zero cost collar or a risk reversal.  

In this chapter we show how the debt and equity of a frm can be valued using options theory. Then we examine equity warrants, which are stock options ‘attached to’ bonds. Finally, we discuss how an equity collar places a foor price and a ceiling price on a stock (or stock portfolio).  

# 30.1 CORPORATE EQUITY AND DEBT  

Merton (1974) and Black–Scholes (1973) noted that the debt and equity of a frm can be valued using options theory. Suppose a corporation has two sources of fnance, debt $D$ and equity $E$ . If the value of the frm’s assets $V_{t}$ at time $t$ , exceeds the face value of debt (bonds) outstanding $K_{B}$ then the equity holders have a positive stake in the frm. On the other hand, if $V_{t}<K_{B}$ the bondholders may put the frm into liquidation. In this case the equity holders receive nothing but they can ‘walk away’, as they have limited liability and any other assets they own cannot be taken by the liquidator. The payo! to equity holders is therefore like a call option with a payo!, max $[V_{t}-K_{B},0]$ . We have:  

![](fa48180c279ae6f986495279744258657df3ee347ed22993b8a32a3ae4eec4e7.jpg)  
FIGURE 30.1 Payo!s  

$K_{B}=$ face value of zero coupon bonds debt issued, which mature at time $T$   
$D_{t}=$ value of bonds (debt at times $t\left(\leq T\right)$   
$V_{t}=$ market value of the frm’s assets at $t\left(\leq T\right)$   
$E_{t}=$ value of shareholder’s equity at time $t\left(\leq T\right)$  

Case A: Solvency at Time $\tau$  

If the value of the frm $V_{T}$ exceeds the face value $K_{B}$ of the bonds $(V_{T}\geq K_{B})$ , the bonds are worth $D_{T}=K_{B}$ and the equity is worth $E_{T}=V_{T}-K_{B}$ .  

# Case B: Insolvency at Time T  

If $V_{T}<K_{B}$ then the bonds are worth $D_{T}=V_{T}$ and $E_{T}=0$ .  

For the above two states, the payo!s to equity and debt holders are (see Figure 30.1):  

$$
\begin{array}{l}{E_{T}=\operatorname*{max}[0,V_{T}-K_{B}]}\\ {D_{T}=K_{B}-\operatorname*{max}[0,K_{B}-V_{T}]}\end{array}
$$  

The value of the equity is therefore like a European call on the value of the frm’s assets with a strike price of $K_{B}$ . If we assume that $V_{t}$ follows a geometric Brownian motion (GBM), then value of the frm’s equity $E_{t}$ (at $t\leq T_{\cdot}$ ) is given by the Black–Scholes formula for a European call option:  

$$
E_{t}=C_{E}(V_{t},K_{B},\sigma,r,T-t)
$$  

Now consider the market value of the debt at time $T.$ . The equity holders can ‘hand over’ the frm to the bondholders if $V_{T}<K_{B}$ . The bondholders have written a put option on the assets of the frm. The payo! to the bondholders consists of a short put plus an amount $K_{B}$ (at time $T_{\mathbf{\delta}}$ ). The value of the debt today $D_{t}$ equals the PV of the face value of the bonds, $D_{t}=K_{B}e^{-r(T-t)}$ less the value of the put held by the equity shareholders:  

$$
D_{t}=K_{B}e^{-r(T-t)}-P_{E}(V_{t},K_{B},\sigma,r,T-t)
$$  

where $P_{E}(V_{t},K_{B},\sigma,r,T-t)$ is the current value of a European put on the frm’s assets with a strike price of $K_{B}$ . The call and put premia $C_{E}(.)$ and $P_{E}(.)$ are given by the Black–Scholes formulas. Note that the current value of the debt $D_{t}$ is less than the value of a risk-free bond $(=K_{B}e^{-r(T-t)})$ because of the risk of default represented by the written put $P_{E}(.)$ because if default occurs, the bondholders will not be paid the full face value of their bonds.  

# 30.1.1 Pricing  

It was Merton (1973) who provided a closed-form solution for pricing the corporate bond $D_{t}$ . Since the value of the frm is assumed to follow a Brownian motion, the equation for $D_{t}$ has similar features to the Black–Scholes formula. The market price of the risky corporate debt is:  

$$
D_{t}=B e^{-r\tau}[(1/L)N(d_{1})+N(d_{2})]
$$  

$\tau=T-t=$ time to maturity of the loan/debt/corporate bond  

$$
L={\mathrm{leverage~ratio}}=B e^{-r\tau}/V
$$  

The Merton model also provides an equation for the yield spread (over risk-free T-bonds) that should be charged to a corporate borrower:  

$$
S p r e a d=r_{c o r p}-r=(-1/\tau)\ln[N(d_{2})+(1/L)N(d_{1})]
$$  

The predictions of the model are quite intuitive. In particular, the spread should increase the higher is either the leverage ratio or the volatility of the frm’s assets. An extended version of the above approach can be used in measuring credit default risk in the following way.1 If $D_{t}$ and $V_{t}$ could be accurately measured then Equation (30.4) can be inverted to solve for the implied volatility $\sigma_{V}^{2}$ of the frm’s total assets. Suppose $\sigma_{V}=\mathfrak{s}12.12\mathrm{m}$ . Then assuming normality, there is only a $5\%$ chance that the value of the frm V will fall below $\$200$ . Suppose the current value of the frm is $\$1000$ and its outstanding debt is $\$800$ . Then our option’s model implies that there is a $5\%$ chance of the frm going into ‘fnancial distress’, over the life of the debt (i.e. the period $\tau$ ). Unfortunately $V$ and $D$ are not easily measured for a levered frm (e.g. which has non-marketable bank loans) so further analysis is needed to make the model operational.  

It is worth noting that we have taken a fairly simple example, where all debt matures on the same date (i.e. a zero-coupon bond). Valuing coupon paying corporate bonds is obviously more di\$cult since each coupon payment represents a put option and if an ‘early’ put option is exercised, the ‘later’ put options are worthless. Also, corporate bonds often contain convertible or call provisions (i.e. the payo!s are path dependent). This means that it may not be technically possible to derive closed-form solutions and other methods such as binomial trees, Monte Carlo simulation and numerical solution of PDEs are required – these techniques are discussed in other parts of the book.  

# 30.2 WARRANTS  

Equity warrants are one of the oldest manifestations of options. They are call options written by a frm on its own stock. Initially they arose because a frm issuing long-term bonds felt the bonds would be more attractive to investors (and therefore could be issued at a lower yield) if warrants were ‘attached’ to the bond. The warrants give the bondholder the opportunity to purchase the frm’s stock at some time in the future, at a price fxed today.2 If the frm does well in the future and its stock price increases, then the warrants would be ‘in-the-money’ and could be exercised at a proft by the warrant holder.  

Equity warrants are sometimes referred to as ‘equity kickers’ since they give the holder the opportunity to participate in the ‘upside’ if the frm is successful in the future but also allow the investor the relative security of a corporate bondholder (who receive payments ahead of stockholders). These warrants are often ‘stripped’ from the bonds and traded separately on stock exchanges. Warrants are also sometimes given out by companies, either in payment for underwriters’ fees or as part of a company’s executive remuneration package – they are then referred to as executive stock options. The maturity of a warrant could be anything from about 2 to 12 years (or more) and hence warrants are ‘long-term’ options carrying the credit risk of the issuing frm.  

# 30.2.1 Valuing European Warrants  

European warrants can only be exercised on a certain day. They can be valued much like ordinary European stock options. However, if a warrant is exercised, then the company has to issue more stocks and hence increase the number of stocks outstanding. This ‘dilution’ does not occur when an exchange traded option is exercised, as the option writer has to purchase stocks on the NYSE.  

Suppose a company has $N$ stocks outstanding with current price $S_{0}$ so the value of the company to equity holders is $V_{0}=N S_{0}$ . Today the company issues $M$ (European) warrants and each warrant allows the holder to purchase one stock from the company at time $T_{:}$ , at a strike price of $K$ . The value of the company does not change on announcement of the warrant issue (assuming any future cash fow from the warrants does not change the underlying proftability of the company by improving incentives or lowering costs of production). After the announcement of the warrant issue, the value of the company remains at $V_{0}=N S_{0}$ as the future exercise of the options (and consequent ‘dilution’) is already refected in the current stock market price, $S_{0}$ – the market is said to be ‘e\$cient’. If the stock price at maturity of the warrant is $S_{T}$ , the value of the equity in the company will be $V_{T}=N S_{T}$ (with or without the warrants).  

If the warrants are exercised at $T$ , there is a cash infow to the company of $M.K$ and the market value of the company’s equity increases from $V_{T}$ to $V_{T}+M K$ , while the number of stocks outstanding rises to $N+M$ . The stock price immediately after exercise is therefore:  

$$
S_{T}^{*}={\frac{V a l u e\:o f f r m}{N u m b e r\:o f s t o c k s}}={\frac{N S_{T}+M K}{N+M}}
$$  

If exercised, the payo! to the warrant holder is $S_{T}^{*}-K$ . Substituting for $S_{T}^{*}$ from (30.6) and rearranging:  

$$
\mathrm{Warrantpayoffat}T=\frac{N}{N+M}\mathrm{max}[S_{T}-K,0]
$$  

The warrant payo! is equivalent to holding $N/(N+M)$ regular call options. The current price of the stock is $S_{0}$ which using Black–Scholes gives a call premium $C_{0}$ , so the value of each warrant is:  

$$
{\mathrm{Value~of~one~warrant~at~}}t=0:V_{w}={\frac{N}{N+M}}{\mathsf{C}}_{0}
$$  

So the total cost of the warrant issue is $M V_{w}$ . The total value of the company’s equity will decline by $M V_{w}$ as soon as the decision to issue the warrants is announced and therefore the stock price will fall by $M V_{w}/N$ at $t=0$ .  

A bond with a warrant attached will sell at a lower yield (higher price) than a conventional bond. This makes the ‘bond-plus-warrant’ an attractive source of fnance for small frms with growth potential. The bond-plus-warrant will have lower coupon payments than a conventional bond (with the same maturity and tenor) and therefore involves less cash outfow for the frm but also gives the warrant holder a share in high profts should these occur in the future.  

‘Warrant’ is often used as a generic term for an option with a long maturity date. As well as warrants on individual stocks there are also warrants (often on stock indices) written by third parties (e.g. Morgan Stanley, Citigroup) which are sold to investors and then traded on an exchange (e.g. American Stock Exchange), rather than OTC.  

# 30.2.2 Quanto  

A quanto is a long maturity option based on a foreign stock index such as the Nikkei 225 and traded (say) on the American Stock Exchange (AMEX). For example, if $S_{T}>K$ a long call (quanto) on the Nikkei 225 gives a US holder a payo! at expiration of $S_{T}-K$ . However, the special feature of a quanto is that at the time the option is purchased, the contract fxes the rate of exchange between the yen and the US dollar which will apply at maturity of the quanto. Hence there is no exchange risk.  

For example, if the payo! $S_{T}-K$ on the Nikkei 225 is equivalent to $\yen20,000$ and the exchange rate agreed at $t=0$ is 100 Yen/USD, then the USD payo! is $\$200$ . Thus a quanto allows a US investor to speculate on future value of the Nikkei 225 index without incurring any exchange rate risk.  

# 30.3 EQUITY COLLAR  

Suppose you hold stocks (with price $S_{0}$ ) but are worried about a fall in prices and want to secure a minimum value for your portfolio, then today you could buy a put, with a low strike price $K_{1}(<S_{0})$ . The ‘stock put’ allows unlimited upside potential, should stock prices rise. However, if you are willing to forego some of the upside potential, you could sell a call with a high strike price, $K_{2}(>S_{0})$ . The cash received from selling the call can be used to o!set the cost of the put. The payo! to this strategy is an equity collar – it establishes a minimum and maximum value for your existing stocks (Figure 30.2).  

An equity collar has the same payo! profle as a bull spread which we discussed in Chapter 17. The key di!erence is that the bull spread is constructed using only options but an equity collar starts with a stock and then uses options to provide a foor and a ceiling on the future value of the stocks.  

The payo! from the equity collar is given in detail in Table 30.1 for three possible outcomes for the stock price at maturity $T$ , of the options. The lower bound for the payo! on the collar is $K_{1}$ and the upper bound is $K_{2}$ . The net cost of establishing the collar is:  

$$
\begin{array}{r}{\mathrm{Net}\mathrm{cost}=P(S_{0},K_{1},\sigma,r,T)-C(S_{0},K_{2},\sigma,r,T)\quad\mathrm{where}K_{2}>K_{1}}\end{array}
$$  

![](c01af33b0d7a5709ad59d674b333da04506ee62e685a3b81f132e58a1d95cfc8.jpg)  

FIGURE 30.2 Equity collar   
TABLE 30.1 Equity collar payo!s   


<html><body><table><tr><td>S<K</td><td>K≤S ≤ k</td><td>S > K</td></tr><tr><td>Long stocks</td><td>ST ST</td><td>ST</td></tr><tr><td>Long put (K)</td><td>K-S</td><td></td></tr><tr><td>Short call (K)</td><td></td><td>-(S - K)</td></tr><tr><td>Payoff</td><td>K</td><td>ST K2</td></tr><tr><td>Profit</td><td>K-(P-C)</td><td>S-(P- C) K-(P- C)</td></tr></table></body></html>  

If the stock price at maturity lies between the two strike prices, then the proft and the breakeven stock price are:  

$$
\begin{array}{l}{\Pi=(S_{T}-S_{0})-P+C=0}\\ {S_{B E}=S_{0}+(P-C)}\end{array}
$$  

# 30.3.1 Zero-cost Collar (Risk Reversal, Range Forward)  

If the strike prices are chosen so that the put and call premia exactly o!set each other (i.e. $P=C$ ) then the collar can be set up at zero cost – this is called a risk reversal, range forward or simply, $a$ zero-cost collar. By defnition a ‘risk reversal’ has $P=C$ and hence $S_{B E}=S_{0}$  

(Equation 30.11). Suppose we chose a foor level $K_{1}$ and hence via Black–Scholes $P$ is fxed, then a zero-cost collar requires:  

$$
C(S_{0},K_{2},\sigma,r,T)=P
$$  

We ‘invert’ the Black–Scholes formula for $c$ and solve (30.12) for $K_{2}$ (e.g. by using Excel’s ‘Solver’). Once you have chosen $K_{1}$ , you must accept whatever value that arises from Equation (30.12) for $K_{2}$ , which ensures $C=P$ .  

The beauty of the zero-cost collar is that an investor holding stocks can fx a maximum and minimum value for her stocks at no ‘up-front’ cost. There is a guaranteed minimum value for the stocks and yet the investor can still share in some of the upside should stock prices rise. However, this is not a ‘something for nothing’ outcome – fnancial markets never give you that! True, the (zero cost) collar gives you a foor value – which you like. But the ‘hidden cost’ is the fact that it eliminates the possibility of very large upside gains (which you might get if you only held the stocks plus the put, but this would involve a cost equal to the put premium).  

In a zero-cost collar $P=C$ implies that you can only choose one of the strikes, either for the call or the put. Also the zero-cost collar will probably involve at least one strike price for which there may not be exchange traded options available. For example, suppose the portfolio manager chooses $K_{1}=159$ , for the put which using Black–Scholes gives $P=2.2$ . For a zero-cost collar the portfolio manager now requires $C=2.2$ . But suppose inverting the Black–Scholes equation for the call premium (e.g. using Excel’s ‘Solver’) gives $K_{2}=170.80$ . Since there is no traded call option with $K_{2}=160.80$ then either the collar will not quite be ‘zero cost’ or OTC options must be used.  

# 30.4 SUMMARY  

• Options theory can be used to value a corporate’s equity and debt (i.e. bank loans and bonds issued). The payo! to equity holders is like a call option. The value of the equity in the frm is therefore equal to the value of a European call on the frm’s assets, with a strike price equal to the face value of the bonds (debt). • Bondholders have written a put option on the frm’s assets. Hence the value of the frm’s debt is equal to the market value of the bonds issued, less the value of the put held by the equity holders (with a strike price equal to the face value of the bonds). • Warrants are ‘long maturity’ options on a stock with maturities ranging from 2 to 12 years. Warrants are often initially attached to bonds, which have a lower yield than plain vanilla bonds. For investors, the warrant combines the relative safety of a conventional bond but allows upside potential if the stock price rises. The warrant is like a call option on the value of the frm and can be priced using a variant of the Black–Scholes formula. • A quanto is an option with a payo! at maturity which depends on the level of a foreign stock index but with payments made in the home currency, based on an exchange rate which is fxed when the quanto is purchased. Quantos therefore provide a low cost method for portfolio managers to take a position in foreign stocks (or stock indices) without incurring FX risk.  

• An equity collar establishes a minimum and maximum value for stocks (or stock portfolio) already held by an investor. An equity collar consists of the initial stock holdings, together with a long put with a low strike price $K_{1}$ and a short call with a high strike price $K_{2}$ . If the collar has zero ‘up-front’ cost (that is, $P=C$ ) it is called a zero-cost collar (risk reversal).  

# EXERCISES  

# Question 1  

An investment manager holds a portfolio worth $\$4,351,700$ , which can be thought of as 10,000 shares of a single stock worth $S_{0}=435.17$ (which pays no dividends). Her performance will be evaluated in 78 days $T=78/365)$ and she would like to establish a maximum and minimum proft over the remaining period until the evaluation is made.  

She fnds that a zero-cost equity collar can be constructed by buying a put with $K_{p}=430$ and selling a call with $K_{c}=448.75$ , both with maturity $T=78/365$ years. The continuously compounded risk-free rate is $4.14\%$ p.a. and the volatility of the stock is $15\%$ p.a.  

Use Black–Scholes (with Excel) to show that $P=C=7.96$ so the zero-cost collar is fairly priced. Show your calculated values for $d_{1},d_{2},N(d_{1}),N(-d_{1})$ etc.  

# Question 2  

A fund already holds stocks and a zero-cost equity collar is constructed by buying a put with $K_{p}=430$ for a price $P=7.96$ and selling a call with $K_{c}=448.75$ and price $C=7.96$ .  

Calculate and explain the payo!s if the stock price at maturity ends up at either $S_{T}=460$ or 435 or 415.  

# Question 3  

The current price of stock-Z is $S_{0}=100$ (which pays no dividends). Ms Sparkle, a fund manager, originally invested $\$800,000$ in stock-Z and is now worth $\$10$ . Over the next year Ms Sparkle is worried about increased volatility in the stock market and wants to lock in a minimum value for her holdings in stock-Z of $\$900,000$ , in 1 year’s time. Options traders’ current view is that the volatility of stock-Z is $\sigma=50\%$ p.a. and the risk-free rate is $3\%$ (continuously compounded).  

What will it cost Ms Sparkle to insure her portfolio? What is the cost in relation to the current value of Ms Sparkle’s holdings of stock-Z?  

# Question 4  

Given the scenario in question 3, Ms Sparkle thinks the cost of providing a foor is rather expensive, as it takes a big chunk out of her past gains of $\$200,000$ . She decides to sell a call today with strike $K_{c}=120$ .  

(a) What is now the net cost of Ms Sparkle’s position? Qualitatively, will Ms Sparkle’s stocks and options positions give her a proft after 1 year, if stock-Z is worth $\$115$ in a year’s time?   
(b) If Ms Sparkle decides today that she wants a zero-cost collar, what strike price will her written call have and what will her proft/loss be if in 1 year’s time the stock-Z is worth $\$130$ . Ex-post, will Ms Sparkle be happy that she went for a zero-cost collar?  

# Question 5  

Explain why the value of the equity in a frm is like a European call on the value of the frm’s assets with a strike price equal to the face value of the bonds $K_{B}$ issued by the frm. Consider the outcomes for equity and debt holders if the frm is solvent or insolvent at maturity of the bonds.  

# Question 6  

Explain why an equity warrant is like a call option.  

# Question 7  

How does a ‘quanto’ di!er from a plain vanilla call option?  