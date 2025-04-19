---
tags:
  - downside_risk
  - european_option
  - no_arbitrage
  - protective_put
  - put_call_parity
  - stock_index_options
aliases:
  - Car Insurance
  - Protective Put
  - S&P 500
  - Stock-XYZ
key_concepts:
  - European put option
  - downside risk control
  - protective put
  - put call parity
  - stock index options
---
# Uses of Options  

# Aims  

• To show how a protective put is used to control downside risk for an individual stock or a portfolio of stocks.   
• To show how ‘put–call parity’ is established by using a no-arbitrage approach.   
• To demonstrate how put–call parity may be used to structure a ‘guaranteed bond’.   
• To show how we can use stock index options to ‘insure’ a diversifed stock portfolio against a general fall in stock prices, whilst also maintaining upside potential, should stock prices increase.   
• To outline some ‘exotic options’.  

# 15.1 PROTECTIVE PUT  

# 15.1.1 Stock-XYZ  

If you already hold stocks-XYZ then you may wish to limit any potential losses on the stocks but also be able to take advantage of any rise in the price of the stock, should this occur. Hence you want to limit the downside, but share in any upside potential. The way to do this is to continue to hold the stocks-XYZ asset but also to purchase a (European) put option on stock-XYZ, with a desired strike price and a time to maturity which matches the period you feel vulnerable to a fall in the price of stocks-XYZ. Finance Blog 15.1 sets the scene by interpreting your car insurance contract in terms of a protective put.  

# Finance Blog 15.1 Car Insurance as a Protective Put  

Car insurance is like a (put) option, with maturity of one year and with the strike price $K$ set equal to the insured value of your car. Suppose your car is currently worth $S_{0}=\S40,000$ and you decide to insure it for a year for a maximum of $\$36,000$ , so the ‘deductible’ (or ‘excess’) in your insurance contract is $\$4,000$ (i.e. $10\%$ of its market value). You pay an insurance premium upfront which we assume is $P=\$720$ (i.e. $2\%$ of the insured value of $\$36,000$ . The insurance premium of $P=\$720$ is just like paying a put premium. The fact that you choose a deductible of $\$4,000$ means that the strike price in the put $K=\$36,000$ is below the current spot (market) price of your car $S_{0}=\mathbb{S}40,000-\mathbb{s}0$ your insurance contract with the deductible is like purchasing a $\cdot10\%$ -out-of-the-money’ put.  

Suppose that by the end of the year $(=T)$ you have not had an accident and the value of your car remains largely unchanged at $S_{T}\approx\$40,000$ , so you do not make an insurance claim. Viewed as a put option, you could deliver your car in Chicago and receive $K=\$36,000$ by using (‘exercising’) the put option. But you would not do this as your car is currently worth $S_{T}\approx\$40,000$ if you sell in the ‘cash (auction) market’. Your car insurance contract is like an (implicit) put option that has expired ‘out-of-the-money’ since $K=\$36,000<S_{T}\approx\S40,000)$ and your put option (insurance) is worthless.  

However, suppose you have an accident and the market value of your car falls to $S_{T}=\$5,000$ .  

The insurance company will only pay you a maximum of $\$36,000$ if you ‘deliver’ your car to them. This is like delivery of the underlying asset, at maturity of a put option contract with a strike price of $K=\$36,000$ .  

Alternatively, the insurance company will allow you to keep your car worth $S_{T}=\$5,000$ and will give you a cash payout of $\$31,000$ – giving a total value of $\$36,000$ . This is like ‘cash settling’ the put contract, which pays a cash amount of $K-S_{T}=\S36,000-\S5,000=$ $\$31,000$ . So the market value of your car $S_{T}=\$5,000$ plus the cash settlement from the put contract comes to $K=\$36,000$ .  

On the other hand, if you had initially insured your car for $\$40,000$ then you would lose nothing after your accident, since the insurance company would pay out $\$40,000$ and take delivery of your wrecked car. But this insurance contract would cost you more than $\$720$ , since it gives you more protection should you have an accident. Here the actual car insurance policy is like buying an at-the-money put (i.e. $K=S_{0}=\mathfrak{H}40,000)$ since this put contract would pay you $K=\$40,000$ on delivery of your wrecked car (to the delivery point in Chicago).  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

# 15.1.2 Stock Index Options  

Stock index options (SIO), are frequently used to hedge the market (systematic) risk of a diversi!ed portfolio of stocks. The most popular index options in the USA (which trade on the  

CBOE) are written on the S&P 500 (SPX) index, the S&P 100 (OEX) index, the Nasdaq 100 index (NDX) and the Dow Jones Industrial Index (DJX). These contracts are European, except for options on the S&P 100, which are American. A fund manager using index options is hedging the market risk of her diversifed stock portfolio (but leaving the portfolio exposed to some specifc risk, although in a well-diversifed portfolio this should be relatively small). To understand the hedging process we need to consider contract specifcations for index options and we focus on the S&P 500 contract.  

The S&P 500 stock index must be translated into a dollar amount. In the options market the value of one index point on the S&P 500 is taken to be $z=\$100$ . Hence, if the current S&P 500, $S_{0}=2\mathrm{,000}$ index points (on the NYSE), then the dollar value of the index is $V_{I}=z S_{0}=\mathbb{\mathbb{S}}200,000$ . Stock index options are cash settled and one option contract is to buy or sell $\$100$ times the index, at the specifed strike price. Hence, the dollar payof to a call on the S&P 500 index is $\$100m a x(S_{T}-K,0)$ and for a put is $\$100m a x(K-S_{T},0)$ . The call and put premia are quoted in ‘index points’.  

# 15.1.3 Protective Put for a Portfolio of Stocks  

Suppose you hold a diversifed stock portfolio worth $V_{s}=\$40$ , whose composition mirrors the S&P 500 (i.e. your portfolio has $\beta_{p}=1\dot{}$ ) and you fear a fall in the overall stock market. You can limit the downside risk by purchasing index puts. This is called a protective put. If the S&P 500 index currently stands at $S_{0}=2\mathrm{,000}$ (index points), then to protect your stock portfolio you should purchase $N_{p}$ index-puts:  

$$
N_{p}=\frac{\oint\displaylimits_{-\infty}^{+}\eta a l u e\ o f s t o c k\ p o r t f o l i o}{\oint\displaylimits_{-\infty}^{+}\dotsb\mathcal{S}_{0}(i n d e x)}\beta_{p}=\frac{V_{p}}{V_{I}}\beta_{p}=20
$$  

Assume the strike price $K=2{,}000$ (an ATM-put). If the index falls by 400 points $(20\%)$ to $S_{T}=1600$ , then the value of your stock portfolio falls by $\$800,000$ . But if you cash-settle the put (at maturity) the payof from your 20 contracts is $\$800,000$ ${\it\Delta}=20$ contracts $\times400$ points $\times$ $\$100$ index point . Here, the loss on the stock portfolio is exactly ofset by the gain on the puts. However, there is also the put premium to consider. If the put premium paid is $P=50$ index points, the 20 put contracts would have cost $\$100,000$ $(=20$ contracts $\times\$100\times50$ index points). Without the puts you would have lost $\$800,000$ , with the puts the net value of your stock $+$ put position is unchanged at $\$40$ , but the cost of this insurance is the put premium of $\$100,000$ .  

If instead you had chosen a $10\%$ out-of-the-money put option $\prime K=1,800\rangle$ then the payof at maturity is $\$400,000$ $(=20$ contracts $\times200$ points $\times\$100$ index point which partly ofsets the loss of $\$800,000$ on your stocks. The net position is a loss of $\$400,000$ , which is $10\%$ of the initial value of your stock portfolio of $\$40$ . (This put with a lower strike price $K=1{,}800$ will cost you less than the ATM put with $K=2{,}000.$ )  

Of course, if the S&P index at maturity of the put is above $K$ , the puts are worthless and are not exercised. But the value of your stock portfolio would have risen. In this case the ‘insurance’ provided by the put option is not needed. However, insurance does not come ‘free’ – you pay for it in the form of the put premium of $\$100,000$ here.  

# 15.2 PUT–CALL PARITY: EUROPEAN OPTIONS  

In this section we derive the put–call parity relationship for European options (on a nondividend paying stock-ABC). Put–call parity is an arbitrage relationship between the (European) put premium $P$ , the call premium $c$ , the stock price $s$ , and holding an amount of cash equal to $\bar{K e^{-r T}}$ in a risk-free asset (e.g. as a bank deposit or a T-bill or zero-coupon bond which matures at $T$ , with face value $K_{\sun}$ ). The call and put options have the same underlying asset (stock-ABC), strike price $K$ and time to maturity, $T$ . The put–call parity relationship can be expressed as:  

$$
\begin{array}{c}{{\left(L o n g\right)S t o c k+\left(L o n g\right)P u t=\left(L o n g\right)C a l l+C a s h\left(e q u a l t o K e^{-r T}\right)}}\\ {{S+P=C+K e^{-r T}}}\end{array}
$$  

Note that the term $K e^{-r T}$ uses continuously compounded interest rates. (The equivalent expression using compound rates is $K/(1+r)^{T}$ .) We can nearly produce the above put–call parity result using our direction vectors to mimic the above equation, namely long stock $\{+1,+1\}$ plus long put $\{-1,0\}$ , equals $\{0,+1\}-\mathrm{{so}}$ the net result is a payof profle which mirrors that of a long call. (However, we have ‘lost’ the ‘cash’ so the direction vectors do not provide the full story.) Note that the ‘signs’ in (15.2) indicate whether you are long or short. They are all $\cdot_{+},$ , indicating long stocks, long puts, long calls and long ‘cash’ of $\$123,456$ , which implies the cash of $\$123,456$ is invested in a bank deposit at the risk-free rate, $r$ .  

To demonstrate put–call parity, we form two portfolios and show that they have the same payof at time $T$ – hence they must be worth the same today, otherwise risk-free arbitrage is possible. Consider the following two portfolios:  

Portfolio-A: One put option plus one stock at $t=0$ .   
Portfolio-B: One call option plus an amount of cash equal to $K e^{-r T}$ at $t=0$ .  

Consider the value of portfolio-A at expiration (Table 15.1). If the stock price at expiration $S_{T}>K$ then the put option expires worthless but the stock is worth $S_{T}$ . Alternatively, if $S_{T}<K$ then the put payof is $K-S_{T}$ and the stock is worth $S_{T}$ , hence portfolio-A has a payof $=(K-S_{T})+S_{T}=K$ .  

Now consider portfolio-B at expiration. If $S_{T}>K$ , the call option’s payof is $(S_{T}-K)$ while the cash amount $\bar{K}e^{-r T}$ held in the risk-free asset earns interest and is worth $K$ at time $T$ .1  

TABLE 15.1 Returns from two portfolios: put–call parity   


<html><body><table><tr><td>S>K</td><td>S<K</td></tr><tr><td>Portfolio-A ST</td><td>Ｋ</td></tr><tr><td>Portfolio-B (S-K)+K=S</td><td>Ｋ</td></tr><tr><td>Portfolio-A = One put option plus one stock at t = 0</td><td></td></tr><tr><td>Portfolio-B = One call option plus cash of Ke-rT at t = 0</td><td></td></tr></table></body></html>  

Hence the payof to portfolio-B is $(S_{T}-K)+K=S_{T}$ . Alternatively, if $S_{T}<K$ the call option expires worthless but the amount held in the risk-free asset plus interest earned is worth $K$ at time $T$ .  

These payofs are shown in Table 15.1 and it can be seen that both portfolio-A and portfolio-B give the same outcomes at $T$ and so must have the same value today – hence Equation (15.2) holds, otherwise risk-free arbitrage profts can be made.  

# 15.3 GUARANTEED BOND  

We are now in a position to understand ‘structured fnance’, which lies behind the advertisement in the ‘Texas Wall Street Journal’2 (Finance Blog 15.2).  

# Finance Blog 15.2 ‘Texas Wall Street Journal’  

‘Invest in our US “Bush Bonanza Fund.” Steer your way to success in the S&P bull market. Defy gravity, stay ahead if the bears attack.’  

We guarantee you will gain most of any upside in the S&P 500 index – but even if the index should fall to zero over the next 2 years you still get all your money back\*. For a total investment of $\$106.60$ today, we guarantee you a minimum amount of $\$100$ after 2 years, but we also ofer you the opportunity to obtain very high returns should the stock market increase – this is too good to miss!  

0There is an administration fee of $6.6\%$ of capital invested for this particular structured product which is known as a ‘guaranteed bond’.  

Source: Adapted from Cuthbertson and Nitzsche (2008).  

TABLE 15.2 Stock, option and bond prices   


<html><body><table><tr><td>Current stock price, S = $100</td></tr><tr><td>Interest rate, r = 0.05 (5%) (continuously compounded)</td></tr><tr><td>Current price 2-year bond = $90.50 (pays out $100 in 2 years)</td></tr><tr><td>Investment horizon, T = 2 years</td></tr><tr><td>Option prices (maturity in 2 years)</td></tr><tr><td>Call premium Put premium</td></tr><tr><td>K= 100 16.1 6.6</td></tr><tr><td>K=90 22.0 3.5</td></tr></table></body></html>

Notes: Continuously compounded interest rates are used here. $\$90.50e\times p(0.05\times2)=\$100$  

Suppose in the cash market and the options market you are today faced with prices in Table 15.2. How can Ms Lego ‘structure’ a ‘guaranteed bond’ over the 2-year investment horizon described in the advert in Finance Blog 15.2? For simplicity assume the S&P 500 stock index is a single stock with a price of $S=\$100$ today.  

Ms Lego must structure the guaranteed bond by investing a total of $\$106.60$ today, so that at the end of 2 years the investor gets $\$100$ back, even if the stock market falls (to zero). But if the stock market does well, the investor will share in (most) of the ‘upside’. Here are the questions Ms Lego needs to answer:  

• What should she do today? • Then what happens if the stock price in 2 years ends up at either 50 or 150? • What might Ms Lego do in order to ‘keep’ some of the investor’s money for the structured products division of her bank (and for her own future bonus) without taking any risks?  

First, notice that the call and put premia satisfy put–call parity:  

$$
C+K e^{-r T}=P+S
$$  

$$
16.1+90.5=6.6+100
$$  

# 15.3.1 Guaranteed Bond Using Stocks and Put Option  

Today Ms Lego buys $\$100$ of the stock on the NYSE. To guarantee a minimum price at which she can sell the stock in 2 years’ time, today she also buys a 2-year at-the-money (ATM) put with $K=\$100$ at a cost of $P=\$60$ . The total cost is $\$106.60$ – which equals the funds received from the investor.  

# Two Years Later  

If ${\pmb S}_{T}={\pmb5}{\bf0}$ Ms Lego delivers her stock in Chicago with the put contract and receives $K=\$100$ .  

If $\mathbf{\xi}_{S_{T}}=\mathbf{150}$ The stock is worth $\$150$ (on the NYSE). Ms Lego does not exercise the put – it is worthless.  

$$
\%R e t u r n t o i n\nu e s t o r=50/106.60=47\%
$$  

Hence the ‘stock plus put’ guarantees a minimum value of $K=\$100$ if the stock price falls, but allows considerable ‘upside’ $(47\%)$ for the investor if the stock price rises by $50\%$ to $\$150$ .  

# 15.3.2 Guaranteed Bond Using Bond and Call Option  

Ms Lego could use the put–call parity equation to structure the ‘guaranteed bond’ using the bond and a call option. Ms Lego uses the $\$106.60$ to invest in the bond $(\@{\mathfrak{O}}90.50)$ and also buys the (2-year) call with $K=100$ at a cost of $C=\$16.10$ . The total cost is again $\$106.60$ (because of put–call parity).  

# Two Years Later  

If ${\pmb S}_{T}={\pmb5}{\bf0}$ The bond has a maturity value of $\$100$ which is paid to the investor. Do not exercise the call, it is worthless.  

I $\nabla_{T}=150$ The call has a cash payof ${\bf\xi}=S_{T}-K=\$50$ , plus the bond with maturity value $\$100$ gives a total cash payout of $\$150$ .  

Hence the payof to the ‘bond $+$ call’ is the same as the payof to the ‘stock plus put’ – but we know this must be the case if put–call parity holds. So far Ms Lego who works in the structured products division of the bank has made no money. How might she keep some money for the structured products division of the bank (to pay her salary and bonus), without taking any risk?  

• Take $\$107.60$ from the investor for this structured product and keep $\$1$ for the bank.   
• Tell the investor that at the end of the 2 years his actual cash ‘payout’ will take place 1 month later (in order to sort out administrative details). The investment bank then places the funds in a bank deposit and ‘pockets’ the deposit interest over the 1-month period.   
• If the structured products department uses the ‘stock $^+$ put’ and the guaranteed return is based on a stock index which only takes account of changes in prices (and not dividends paid out, as with a ‘total return index’), then the bank might also ‘pocket’ any dividends paid on the stocks over the 2 years.  

• Ms Lego could also ofer an alternative deal where the investor could lose a maximum of about $10\%$ (over the 2 years) but ofer the investor a lower ‘administrative fee’ of $\$5.50$ . Ms Lego can structure this product by buying an out-of-the-money put with a strike of $K=90$ , at a cost of $P=\$3.50$ (see Table 15.2). The cost of ‘stock plus put’ $=\$100+\$3.50=\S103.50$ . Ms Lego therefore earns (for certain), $\$2$ $(=\$105.5-\$8103.5)$ for the structured products division of the bank, for each ‘guaranteed bond’ she sells to investors.  

# 15.4 OTHER OPTIONS  

The underlying asset in an options contract can be individual stocks, stock indices, currencies, precious metals such as gold and silver, futures contracts and T-bonds. There are also options whose payof depends on the future outcome for interest rates (e.g. caps and foors). There is a very large OTC market in options and some options are only available OTC (e.g. caps and foors).  

# 15.4.1 Caps, Floors, and Collars  

Simplifying a little, a caplet is a call option which pays of max $(r_{T}-K_{c a p},0)$ where $r_{T}$ is the interest rate (LIBOR) at the expiration of the option contract and $K_{c a p}$ is the strike (interest) rate. Clearly a caplet can be used to speculate on a future rise in (LIBOR) interest rates – if you expect interest rates to rise in the future (above $K_{c a p}\mathrm{,}$ ) then today you would purchase a caplet. However, let us consider how it can be used to insure against interest rate rises.  

Suppose in January LIBOR interest rates are currently $r_{0}=5\%$ . You have a foating rate loan of $\$10$ on which you pay LIBOR with a reset date in March and you are worried that interest rates will increase between January and March, so the interest cost of your loan will increase. You decide to purchase a caplet with $K_{c a p}=5\%$ which expires in March. In March if interest rates turn out to be $r_{T}=7\%$ , the caplet payof is $2\%$ . The cap contract also includes a notional principal amount of (say) $\$10$ and hence the cash payof would be $\$20,000$ .  

In March, if LIBOR, $r_{T}=7\%$ then your loan costs you $2\%$ more as interest rates have risen, but the caplet provides a cash payof of $2\%$ which will compensate you for your higher borrowing costs. So the efective maximum interest rate you will pay, if you have a bank loan and a caplet and if interest rates are high, is $K_{c a p}=5\%$ . But things can get even better. If in March, interest rates have fallen to $r_{T}=4\%$ then you can just ‘walk away’ (i.e. not exercise) the caplet and simply pay the low LIBOR interest rate of $4\%$ on your loan. Hence, once again a call option allows you to set the maximum efective interest rate you will pay on your loan but also allows you to beneft from any favourable outcomes (i.e. low loan rates). For this privilege you would have to pay the caplet premium ‘up front’ (i.e. in January).  

If your foating rate loan has a number of futures reset dates (e.g. March, June, September, December) then you can set the maximum interest you will pay on these future loan payments by buying a series of caplets, each with a maturity date which matches the reset dates for your loan. A series of caplets is known as a cap. Financial institutions will ‘design’ and sell you a cap in the OTC market. (Caps are not traded on an exchange.)  

A foorlet has a payof equal to max $(K_{F L}-r_{T},0)$ and is therefore a long put on interest rates. Clearly, if you are a speculator and you think interest rates are going to fall below $K_{F L}$ (in 3 months’ time say) then you can make a proft if today you buy a (3-month maturity) foorlet.  

Alternatively, if you have a bank deposit with a variable (foating) interest rate, with a reset date in 3 months’ time and you are worried that interest rates will fall, then a long foorlet will ensure that the minimum efective interest rate you earn on your deposits will be $K_{F L}=8\%$ , say. For example, if interest rates turn out to be $r_{T}=7\%$ in 3 months’ time, you exercise the foorlet and obtain a payof of $1\%(=K_{F L}-r_{T})$ , which when added to the interest on your deposit of $r_{T}=7\%$ implies the efective interest rate you receive is $8\%$ . On the other hand, if interest rates turn out to be $r_{T}=9\%$ , say, then you would not exercise the foorlet (since it is out-of-the-money), but your bank deposit would earn the current high interest rate of $9\%$ .  

A foor is a series of foorlets, with diferent maturity dates and can be used to ensure that the efective minimum interest rate you will receive from your deposit account (at foating rates) is $K_{F L}=8\%$ at each reset date (e.g. every 6 months).  

To summarise. A bank deposit on which you receive a variable interest rate is risky as you do not know what interest rates will be in the future. If you buy a foorlet (i.e. a put) with a strike of $K_{F L}=8\%$ then you are certain of receiving an efective minimum interest rate on your deposit of $8\%$ (even if market interest rates are low) but you can also take advantage of high deposit rates should they occur.  

Finally, the combination of a foating rate bank loan plus a long cap with $K_{c a p}=10\%$ and a short foor with $K_{F L}=8\%$ , is known as a collar. This is because the collar implies that the efective interest rate payable on the bank loan cannot go above $10\%$ nor fall below $8\%-80$ the efective interest payable is constrained at a desired upper and lower level.  

# 15.4.2 Exotic Options  

There is no end to the types of option that can be ofered in the OTC market and those with complex payofs are known as exotic options. For example, Asian options have a payof which is based on the average price over the life of the option. An Asian (average price) put option has a payof which depends on max $(K-S_{a v},0)$ where $S_{a v}$ is the average price over the life of the option (e.g. the average of end-of-the-month prices over one year). So, an Asian average price put option on euros would be useful for a US frm that wants to fx the average level of US dollars it will receive from its future export receipts in euros, each month over the next year. The Asian option costs less than using 12 vanilla options for each of the individual monthly euro receipts.  

Another type of exotic option are barrier options. These either ‘die’ or ‘come alive’, before the maturity date in the options contract. For example a (European) knockout option may specify that if the stock price rises or falls to a ‘barrier level’, the option will terminate (‘die’) on that date, and hence cannot be exercised later. If the option is terminated when the stock price falls to the barrier, then they are referred to as down-and-out options, while if they are terminated when the price rises to the barrier, they are up-and-out-options. These options, unless they have already been knocked out, have a payof at maturity which is the same as the payof from ‘plain vanilla’ calls and puts we have already discussed. But clearly, sometimes knock-out options ‘die’ before their maturity date and such outcomes are less favourable than payofs from plain vanilla options. For this reason knock-out options have lower premiums than plain vanilla options (with the same underlying asset, strike price, and time to maturity). In fnance, if you ‘get less’ you pay less.  

# 15.4.3 Other Options  

There are also options which are ‘embedded’ in other securities. Examples of embedded options include callable bonds, convertible bonds, warrants and executive stock options, and stock underwriting. The latter involves the underwriter agreeing to purchase any stocks which are not taken up by the public, at an agreed minimum price. The agreed minimum price is equivalent to the strike price in a put contract and the underwriting fee is the put premium. The corporate is long the put and the underwriter has written the put.  

# 15.5 SUMMARY  

• Put–call parity for European options links call and put premia for options (on the same underlying asset, with the same strike price and time to maturity). It provides two equivalent methods to structure a ‘guaranteed bond’ – namely, buying a ‘stock and a put’ or buying a ‘call and a bond’. A guaranteed bond provides the investor with a guaranteed minimum future value for her investment but also allows her to beneft from a rise in stock prices, should this occur.   
• An options contract can be written on individual stocks, stock indices, currencies, precious metals, futures contracts, and T-bonds. Some options have payofs which depend on the future level of interest rates (e.g. caps, foors, and collars). There is a very large OTC market in options (particularly for currencies and interest rates) and some options are only available OTC.   
• Options with complex payofs are known as exotic options. Examples include Asian options and barrier options, but there are many more.   
• Some options may be embedded in other securities (e.g. callable bonds, convertible bonds, warrants and executive stock options).  

# EXERCISES  

# Question 1  

What is a guaranteed bond and its relationship to put–call parity?  

# Question 2  

A long straddle is constructed from a long call with a premium of $C=\$13$ and a long put with $P=\$9$ . Both options have the same strike $K=100$ (and the same maturity date). The current stock price is $\$100$ . By how much must the stock price move so that you make a positive net proft on your long straddle, at maturity?  

# Question 3  

What is put–call parity for European options on a non-dividend paying stock? Why is the put–call parity useful when pricing calls and puts?  

# Question 4  

You currently hold a stock with $S_{0}=100$ . You buy an at-the-money put for $P=6$ . What is the maximum loss from holding the put and the stock?  

# Question 5  

Let $P=\$6$ , $K=165$ and the current stock price $S_{0}=164$ (i.e. the put is currently ITM).  

What is the proft profle (at expiration) and the breakeven stock price for a portfolio consisting of 100 stocks and 100 long puts? The profts are determined by the change in the price of the stocks, the payof from the long puts less the cost of the puts.  

What are the profts for $S_{T}=163?$  

# Question 6  

You are going to take out a 1-year bank loan for $\$1,000$ in 6 months’ time at a foating (LIBOR) interest rate (i.e. you will pay whatever the interest rate happens to be in 6 months). You are worried that interest rates will rise over the next 6 months, so you will pay more interest on your bank loan.  

How could a caplet with $K_{c}=3\%$ , be used to ‘insure’ yourself against higher interest rates in 1 year’s time? What is the outcome in 1 year’s time, if interest rates turn out to be either $r_{T}=7\%$ or $1\%?$  

# Question 7  

You are going to take out a 1-year bank loan for $\$1,000$ in 6 months’ time, at foating (LIBOR) interest rate (i.e. you will pay whatever the interest rate happens to be in 6 months’ time). You are worried that interest rates will rise over the next 6 months, so you will pay more interest on your bank loan.  

A colleague suggests you insure yourself against high future (LIBOR) loan rates by buying a 6-month foorlet with $K_{F L}=3\%$ , notional principal of $\$1,000$ today. Do you agree?  