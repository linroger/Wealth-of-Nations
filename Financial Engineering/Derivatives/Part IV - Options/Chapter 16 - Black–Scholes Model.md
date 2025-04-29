---
tags:
  - black_scholes_model
  - delta_hedging
  - european_options
  - implied_volatility
  - option_premium
  - option_prices
  - option_pricing
  - stock_price
  - strike_price
  - time_to_maturity
aliases:
  - BSM
  - Black-Scholes
  - Option Pricing Model
key_concepts:
  - Delta hedging
  - European call/put prices
  - Implied volatility
  - Option premium
  - Option price determinants
  - Stock price
  - Strike price
  - Time to expiration
---
# Black–Scholes Model  

# Aims  

• To demonstrate how option prices change with changes in the price of the underlying asset, its volatility, interest rates and time to maturity.   
• To establish upper and lower bounds for the price of European calls and puts.   
• To show how the Black–Scholes formula is used to price European calls and puts.   
• To show how options and the underlying asset (e.g. stock-Z) can be combined into a portfolio which does not change in value when there is a small change in the price of the underlying asset – this is delta hedging.   
• To explain implied volatility and its use in options trading.  

# 16.1 DETERMINANTS OF OPTION PRICES  

It can be shown that the option premium varies second-by-second as the stock price, the risk-free interest rate and the volatility of the stock change, over time. Let us develop some intuitive arguments which give some insight into the determination of European option prices. We consider each factor in turn, holding all the other factors constant. This intuitive approach will help us understand the mathematical formulas for option prices which we present later. In each case we assume the investor has a long options position (i.e. has purchased a call or a put) and we only consider European stock options (where the stock pays no dividends). The results are summarised in Table 16.1.  

TABLE 16.1 Factors afecting the option premia   


<html><body><table><tr><td></td><td>Long European call option</td><td>Long European put option</td></tr><tr><td>Time to expiration, T</td><td>+</td><td>+</td></tr><tr><td>Current stock price, Sg</td><td>+</td><td></td></tr><tr><td>Strike price, K</td><td></td><td>+</td></tr><tr><td>Stock return volatility, o</td><td>+</td><td>+</td></tr><tr><td>Risk-free rate, r</td><td>+</td><td>一</td></tr></table></body></html>

Notes: We only consider options on stocks which pay no dividends. $'+'$ indicates a positive relationship between the option price and the variable chosen. That is, a rise (fall) in the variable is accompanied by a rise (fall) in the option premium. A ‘–’ indicates a negative relationship between the option price and the variable chosen. That is, a rise (fall) in the variable is accompanied by a fall (rise in the option premium.  

# 16.1.1 Time to Expiration, T  

Calls: The price today of a European call option $c$ is higher, the longer the time to maturity of the option. This is because a long-maturity option has more time to end up well in-the-money, that is for $S_{T}$ to be much higher than $K$ .  

Of course, $s$ could also fall over the life of the option, but losses are limited to the call premium no matter how far stock prices fall. Hence, the longer the time to maturity the higher the expected payof at maturity and therefore you are willing to pay more for longmaturity calls.  

Puts: The put premium on a European option increases with time to maturity, for the same reason as given for the call. This is because a long-maturity put option has more time to end up well in-the-money (i.e. $S_{T}<K)$ , yet the most you can lose is the put premium. (For puts there are some rare cases where the put premium falls as the time to maturity increases – but we ignore these).  

# 16.1.2 Strike Price, K and Stock Price, S  

Calls: If stock price movements are random, then the higher the current stock price $S_{0}$ relative to the strike price $K$ , the more likely it is that the stock price at expiration $S_{T}$ , will end up above the strike price and the call will have a positive payof. Hence the purchaser of a long European call option, will today be willing to pay a higher call premium $c$ , the higher is $S_{0}/K$ .  

Puts: It should be obvious that the price of a put option varies with $s$ in the opposite way to that for a call. Hence the price of a European put option $P$ depends negatively on $S_{0}/K$ .  

# 16.1.3 Volatility,  

Calls: The greater the volatility of the return on the stock $\sigma$ , the greater the possible range of stock prices that might occur at maturity of the option. But the most the holder of a long call option can lose is the call premium. High volatility increases the chance of a very high stock price and hence a very high payof for the call option (at maturity), while downside risk (if $\mathrm{S}_{\mathrm{T}}<\mathrm{K}\dot{}$ ) is limited to the call premium.  

Therefore the current price of a call option is higher, the higher is the volatility of the underlying stock return, since this implies a higher expected payof to the call.1 The latter statement does not imply that holders of call options like risk – it is just that higher volatility of stock returns implies a higher expected payof (at maturity) to the holder of the call and she is therefore willing to pay a higher call premium.  

Puts: The owner of a long put has a payof at maturity of $K-S_{T}$ (if $S_{T}<K\`$ ). The higher the volatility, the larger is the possible payof at maturity, if the stock price ends up below $K$ . However, high volatility also implies that the stock prices could rise well above $K$ , in which case the put is worthless at maturity. But no matter how high the stock price at maturity, the most you can lose is the put premium.  

Hence, the expected payof at maturity to holding the put is higher, the higher is the volatility of the underlying stock. So you are willing to pay a higher price today for a put which has an underlying stock with high volatility.  

# 16.1.4 Risk-free rate, r  

Calls: The European call option premium is higher the higher is the current interest rate, r – although unfortunately we cannot give a full intuitive interpretation of this result. But try this. At maturity, if you exercise the call option you have to pay the strike price $K$ . The present value of this payment is $K e^{-r T}$ . The higher is the interest rate the lower is the present value of your payment2 – hence the more you are prepared to pay for the call option.  

Puts: Higher interest rates reduce the put premium. If you exercise the put at expiration, you deliver a stock and receive $K$ . But the higher is the interest rate, then $K$ -dollars received at $T$ are worth less today, so you are willing to pay less today for the put.  

# 16.1.5 Price Bounds for European Options (Non-Dividend Paying Stocks)  

It is possible to establish limits on the range of possible values for the call and put premia and if the quoted price of an option lies outside these bounds then risk-free arbitrage profts can be made. The upper bounds for European options (on a non-dividend paying stock) are:  

$$
C_{e}\leq S~\mathrm{and}~P_{e}\leq K e^{-r T}
$$  

The lower bounds are:  

$$
C_{e}\geq\operatorname*{max}(S-K e^{-r T},0)~\mathrm{and}~P_{e}\geq\operatorname*{max}(K e^{-r T}-S,0)
$$  

As shown in Appendix 16, these upper and lower limits on the no-arbitrage values for calls and puts, only depend on the risk-free rate being positive.  

It would be extremely useful if all of the above factors could be included in a single equation to determine the call $c$ or put premium $P$ . This ‘closed form’ solution is the Black–Scholes equation for option prices and has the general form:  

$$
\emph{C}o r\ P=f[(S/K),r,\sigma,T]
$$  

To work out the exact functional form for the Black–Scholes equation is rather difcult but results in a ‘curved’ or ‘non-linear’ or ‘convex’ relationship between the call (or put) premium and the price of the underlying stock, S. This positive non-linear relationship for a long call is shown as the curve A-B in Figure 16.1. In fact, as the option approaches its maturity date, the ‘curve’ moves towards the ‘kinked line’ which represents the payof on the day the option matures. If the current stock price is $S_{t}$ then the current call premium would be $C_{t}$ (point B, Figure 16.1). However, if the stock price remained at $S_{t}$ the call premium would fall-towards point D and the option is said to ‘lose time value’ as it approaches maturity.  

# 16.1.6 Speculation with Calls  

Figure 16.1 shows how we can speculate over short horizons, using call options. Suppose a speculator purchases a call option (on a stock) at $C_{0}=\$3.1$ , and the stock price then increases from $S_{1}=\$100$ to $S_{2}=\$100.5$ . According to the Black–Scholes formula the call price rises to $C_{1}=\$3.3$ . If the speculator paid the $\$3.1$ to the clearing house at $t=0$ , then at $t=1$ when she closes out her initial (long) position by selling the call at $\$3.3$ (to another trader), the clearing house in Chicago credits the speculator’s (margin) account with a proft of $\$0.2$ , which is a percentage return3 of $6.45\%=(\S0.2/\S3.1)\times100\%$ .  

![](e699d295c3c333a25b520a78d882b9a01700d3f6b990d4e30a635c31fd098aad.jpg)  
FIGURE 16.1 Black–Scholes  

The ratio of the dollar change in the call premium $(\$0.2)$ to the dollar change in the stock price $(\$0.5)$ is known as the call option’s delta, which here is $\Delta_{c}=0.4(=\mathbb{5}0.2/\mathbb{5}0.5)$ .4 The delta of a call always lies between 0 and $+1$ . But note that although the dollar change in the call premium is usually less than the dollar change in the stock price, the option still provides ‘leverage’ compared to speculating with the stock – because leverage refers to percentage changes. To see this, note that in the above example, the option gives a return (per dollar invested) of $6.45\%$ . Had you invested your ‘own money’ in the stock you would have earned a considerably smaller percentage return on your capital invested – you would have paid $\$100$ for the stock and sold it for $\$100.5$ – a return on your ‘own capital’ of $0.5\%$ .5  

The change in dollar value and the ‘percentage return’ are two diferent concepts. In the above example, the percentage return on the stock is $R_{s}\equiv(S_{1}-S_{0})/S_{0}=0.5\%$ but the percentage return from the call is much larger at $R_{c}\equiv(C_{1}-C_{0})/C_{0}=6.45\%$ . As a speculator, it is the percentage return (on your ‘own funds’) that you are interested in, when you compare two investment strategies – betting on the call price versus betting on the stock price.  

Another way of looking at this is to note that the percentage change in the call premium for each $1\%$ change in the stock price is $12.9\%$ $(=6.45/0.5=R_{c}/R_{s})$ . The fgure of $12.9\%$ is known as the option’s elasticity6 and it clearly indicates that investing in the option provides leverage (i.e. a larger percentage return), compared to investing (the same amount of money)  

in the stock. Note that leverage works on the downside too. If the stock price falls by $1\%$ then the call premium will fall by $12.9\%$ . Leverage implies that the percentage change in the option premium will be larger than the percentage change in the underlying stock price.  

A speculator would purchase a call option if she expected a bull market, that is, a rise in stock prices. If stock prices rise (above $K$ ) she may achieve a higher percentage return from the long call than investing in the stock.  

Prior to maturity, the relationship between the put premium and the stock price is also a ‘curved line’ but for a put, the put premium $P$ and the stock price $s$ are negatively related. Hence, a speculator would purchase a put option if she felt that stock prices would fall in the near future. She would pay the put premium $P_{0}=\S2$ at $t=0$ . If the stock price subsequently fell then at $t=1$ the put premium would increase, to say $P_{1}=\S2.3$ . If she then closes out her initial position by selling the put (to another options trader), she will receive $\$2.3$ from the clearing house, making a proft of $15\%$ on her initial outlay of $\$2$ $(=\mathbb{S}0.3/\mathbb{S}2\times100\%)$ .  

We also noted above that the Black–Scholes formula (and our intuition) show that both the call and put premia are positively related to the volatility of the stock return. Suppose the perceived volatility of a stock increases (e.g. because traders think the future economic outlook has become more uncertain) then both call and put premia would increase. Had the speculator been long either calls or puts she could now close out her position at a proft. Options therefore allow speculators to make a potential proft (or loss) by predicting changes in volatility, $\sigma$ . This is sometimes referred to as trading volatility.  

# 16.2 BLACK–SCHOLES  

In the 1960s, options were being traded in the US over-the-counter but rather bizarrely no-one knew how to correctly price them. It was easy to work out that for a call option, say, the premium should be higher, the lower the strike price, the longer the time to maturity, the higher the interest cost and the greater the volatility of the underlying stock. But how could all of these be combined to give an explicit equation that could be used to quickly calculate the correct or fair price for the option? The Binomial Options Pricing Model (BOPM) had not been invented and the frst pricing equation for options was the work of Black, Scholes, and Merton – a brief history of the route to the Black–Scholes equation is given in Finance Blog 16.1.  

# Finance Blog 16.1 Noble Pursuits  

It was the combined work of Fischer Black, Myron Scholes, and Robert Merton in Boston that fnally solved the option pricing problem in the early 1970s. Black (after his degree in physics) initially worked on the pricing of warrants (i.e. options on stocks, issued by the company itself).  

Scholes was also working on options pricing in the late 1960s at the Sloan School of Management (MIT), where he met Black and they began working together. Meanwhile, a young applied mathematician, Robert Merton, joined MIT as a research assistant to Paul Samuelson in the economics faculty. Samuelson, based on his own earlier work, encouraged Merton to explore the theory of warrant pricing.  

At this time, Merton developed the use of continuous time fnance and Brownian motion. These mathematical ideas were to provide the basis for the Black–Scholes formula. Merton, Black, and Scholes exchanged ideas over several years at MIT. Their path to success might be described as a ‘Brownian motion with positive drift’ – there were many false starts but ultimately the problem was solved.  

In 1970, Black and Scholes completed their options pricing paper. They acknowledged Merton’s suggestion of combining the option and the underlying asset, to yield a risk-free portfolio. Black and Scholes’ paper was initially rejected by the Journal of Political Economy (JPE) – a publication of the economics faculty of the University of Chicago – because it was too specialised.  

It was then rejected by Harvard’s Review of Economics and Statistics but fnally, with the support of Eugene Fama and Merton Miller, it was accepted by the JPE and published in May/June 1973 under the title ‘The Pricing of Options and Corporate Liabilities’. Merton, who had collaborated with Black and Scholes, also produced a paper on options pricing in the Bell Journal of spring 1973.  

Coincidentally, the Chicago Board Options Exchange (CBOE) began trading options (initially in the large smoking room of the Chicago Board of Trade) in April 1973 and the ‘new’ Black–Scholes formula was soon in use by traders. (For more details of this ‘story see the excellent book by Bernstein 2007.) The Ivory Towers of academia produced something of real practical value (as well as aesthetically pleasing). Whether it be ‘Black Holes’ or ‘Black–Scholes’, the power of mathematics to solve problems is impressive – not least in modern fnance dealing with derivatives.  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

The Black–Scholes (1973) formula for pricing European options (on a stock which pays no dividends) was derived using continuous time fnance and stochastic calculus. The assumptions of the Black–Scholes model are:  

• All risk-free arbitrage opportunities are eliminated.   
• No transactions costs or taxes.   
• Investors can borrow and lend unlimited amounts at the risk-free interest rate which is constant over the life of the option.   
• Stock prices are random, like a ‘coin \$ip’ – if your frst \$ip gives ‘heads’ this does not help you to predict whether the next \$ip will give you a head or a tail. The technical term for the random stock price process (over very small time intervals) is a ‘geometric Brownian motion’.   
• Stock prices are continuous and do not experience sudden extreme jumps – such as after an announcement of a takeover or other major unexpected frm specifc events (e.g. new patents granted).   
• The stock pays no dividends.   
• The volatility of the stock (return) is known and constant over the life of the option (or is a deterministic function of time).  

# 16.2.1 Call Option  

To work out the Black–Scholes equation is rather difcult and at frst sight the formula looks rather formidable. For the call premium:  

$$
C=S N(d_{1})-N(d_{2})K e^{-r T}
$$  

$$
d_{1}={\frac{\ln(S/K)+(r+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}
$$  

$$
d_{2}=d_{1}-\sigma\sqrt{T}=\frac{\ln(S/K)+(r-\sigma^{2}/2)T}{\sigma\sqrt{T}}
$$  

where  

$C=$ price of call option call premium   
$\begin{array}{r l}{r}&{{}=}\end{array}$ risk-free rate of interest for horizon $T$ continuously compounded   
$\begin{array}{r l}{S}&{{}=}\end{array}$ current stock price   
$T\ =$ time to expiration maturity proportion of year   
$\sigma\ =$ annual standard deviation of the continuously compounded return the stock   
$\ln{}=$ natural logarithm of variable7  

The call premium depends positively on the current stock price relative to the strike price $(S/K)$ and the volatility of the stock return over the life of the option $(\sigma{\sqrt{T}})$ . In practice, the remaining ‘life’ of the option – that is, the time to maturity $T$ – is usually measured using trading days (rather than calendar days):  

$T=$ number of trading days to maturity of the option 252 where there are (approximately) 252 trading days in a year (i.e. Monday–Fridays and excluding ‘national’ holidays). The Black–Scholes ‘curve’ shows the relationship between the call premium and the stock price (Figure 16.1).  

Note that the only input to the Black–Scholes formula that is not known precisely is the volatility of the stock, $\sigma$ which has to be estimated. If two traders have diferent forecasts for the volatility of the stock (over the life of the option) then even if they both use the Black–Scholes formula they will quote diferent options prices. Traders can apply statistical models to forecast volatility8 but they mainly use an estimate of ‘implied volatility’ from ‘similar’ options (e.g. traded options with the same underlying stock and time to maturity as the option they wish to price, but with slightly diferent strike prices) – implied volatility is discussed further below.  

What is interesting yet very counterintuitive is that the call premium does not depend on the expected rate of return $\mu$ on the stock, in the real world. For example, if one trader thinks the stock price will grow at $5\%$ p.a. and a second trader that it will grow at $20\%$ p.a. – they will still agree on the same price for the option – even though the expected payof at maturity of the call option is clearly higher given the second trader’s $20\%$ growth assumption. This seems very counterintuitive. How can this be?  

It is not possible to fully explain this counterintuitive result at this point. But as we shall see, by combining the option and the stock into a risk-free portfolio, such a portfolio must earn the risk-free rate – otherwise traders can make risk-free arbitrage profts. This results in the risk-free rate $r$ ‘appearing’ in the Black–Scholes formula rather than the expected stock return $\mu$ .  

The term $N(d_{1})$ is the cumulative probability distribution function for a standard normal variable. It gives the probability that a variable with a standard normal distribution $\sim N(0,1)$ will have a value less than $d_{1}$ . For example, when $d_{1}=-1.96$ then $N(d_{1})=0.025$ which means there is $2.5\%$ of the total area of the normal curve to the left of the point –1.96 (Figure 16.2). The values of $N(d_{1})$ can be found in standard statistical tables or you can use the Excel function ‘NORMSDIST(–1.96)’ which will ‘return’ a value 0.025. So at the end of the day, $N(d_{1})$ is just a ‘number’ (which lies between 0 and $+1$ ). Here are some other values of $N(d_{1})$ that you might remember from statistics classes:  

$\begin{array}{r l}{N(-\infty)=0,\quad}&{N(-2.33)=0.01,\quad N(-1.96)=0.025,\quad N(-1.65)=0.05,}\\ {N(0)=0.5,\quad}&{N(2.33)=0.99,\quad N(1.96)=0.975,\quad\quad N(1.65)=0.95,}\end{array}$ N 1  

8The simplest forecast of daily volatility is the sample standard deviation $\widehat{\sigma}=\sqrt{\sum_{t=1}^{n}(R_{c c,t}-\overline{{R}}_{c c})^{2}/(n-1)}$ where $R_{c c,t}=\ln(P_{t}/P_{t-1})$ is the continuously compounded daily return on the stock. When pricing options, daily (continuously compounded) returns are usually used to estimate daily volatility and the annual volatility is then taken to be $\widehat{\sigma}\sqrt{252}$ – based on 252 trading days in the year.  

![](c5abaef020e2aef352b75c7358ff5027b679541c66a238f30264be61d310394a.jpg)  
FIGURE 16.2 Standard normal distribution, $N(0,1)$  

For negative values of $d_{1}$ we proceed as follows. We know, for example, that $\mathrm{N}(+1.96)=0.975$ . Because the normal distribution is symmetric, $N(-d_{1})=1-N(d_{1})$ and therefore $N(-1.96)=0.025$ . In Example 16.1 we calculate the Black–Scholes price for a European call and put option (on a non-dividend paying stock).  

# EXAMPLE 16.1  

# Pricing Calls and Puts  

${\cal S}=\$45$   
r 0.10 10   
$T=0.5$ years approximately 126 trading days  

$K=\$43$ $\sigma=0.20$ $20\%$ p.a.)  

# Call Premium, C  

$$
d_{1}={\frac{\ln(45/43)+(0.1+0.2^{2}/2)0.5}{0.2{\sqrt{0.5}}}}=0.7457
$$  

$$
d_{2}=d_{1}-\sigma\sqrt{T}=0.7457-0.2(0.5)^{1/2}=0.6043
$$  

Using the Excel function NORMSDIST $\mathrm{(d_{i})}$ , $N(0.7457)=0.7721$ and $N(0.6042)=$ 0.7272  

$$
C=S N(d_{1})-N(d_{2})K e^{-r T}=45\ (0.7721)-0.7272\ (40.9029)=\S5.00
$$  

# Put Premium, P  

The price $P$ , of a European put using the Black–Scholes formula is:  

$$
\begin{array}{r}{P=K e^{-r T}N(-d_{2})-S N(-d_{1})~}\\ {N(-d_{1})=1-N(d_{1})=1-0.7721=0.2279~}\\ {N(-d_{2})=1-N(d_{2})=1-0.7271=0.2728~}\\ {P=40.9029~(0.2728)-45(0.2279)=0.9069}\end{array}
$$  

Check the price of the put by using the put–call parity relationship:  

$$
P=C+K e^{-r T}-S=5+43e^{-0.10(0.5)}-45=0.9069
$$  

We have moved a long way from the simple ‘payof’ diagrams for calls and puts. We now know what causes option prices to change second-by-second.  

An Excel fle is available on the website to graph the relationship between the underlying stock price S and the call premium C (or put premium, P) given by the Black–Scholes formula.  

In practice, traders have all these calculations programmed using ‘in-house’ software. For example, an element of code is provided in Example 16.2 in MATLAB to calculate European call and put premia for alternative values of the stock price, $S.{}^{9}$ (Other programs would have a similar structure.)  

# EXAMPLE 16.2  

# MATLAB Code, Price Plain Vanilla Call and Put  

$k\ =\ 43$ % strike price (Note that in MATLAB '%' indicates a comment) $s\theta\ =\ 45$ ; % price of the underlying asset (stock)   
$r=\theta.1\theta$ $\%$ interest rate, contin. comp, decimal   
$d=\theta.\theta$ ; % dividend yield, contin. comp, decimal   
sigma $\mathbf{\varepsilon}=\mathbf{\varepsilon}\theta.2\theta$ ; % standard deviation, annual, decimal   
$t a u\ =\ \theta.5$ % time to maturity, years or fraction of a year   
c0 = bscall(k,s0,sigma,tau,r,d); % activate function/procedure for call premium   
p0 = bsput(k,s0,sigma,tau,r,d); % activate function/procedure for put premium   
pp0 = c0 - s0.\*exp(-d.\*tau) + k.\*exp(-r.\*tau) ; % put—call parity: check on BS formulas   
%   
% Setting up Stock Price data for graph   
%   
s = s0-10:1:s0+10; % S values are s0-10 to $s0+10$ in   
increments of 1   
c=bscall(k,s,sigma,tau,r,d); % Activate function/procedure for call p=bsput (k,s,sigma,tau,r,d); % Activate function/procedure for put %   
% Function: Black-Scholes Call Premium - Dividend paying stock %   
function c = bscall(k,s,sigma,tau,r,d)   
d1 = ( log( s./k ) + ( r - d + sigma.^2./2).\*tau )./ ( sigma.\*sqrt(tau) ); d2 = d1 - sigma.\*sqrt(tau);   
$c=s$ .\*exp(-d.\*tau).\*normcdf(d1) -k.\*exp(-r.\*tau).\*normcdf(d2);   
%   
% Function: Black-Scholes Put Premium - Dividend paying stock %   
function p=bsput(k,s,sigma,tau,r,d)   
d1 = ( log( s./k ) + ( r - d + sigma.^2./2).\*tau )./ ( sigma.\*sqrt(tau) ); d2 = d1 - sigma.\*sqrt(tau);   
p=k.\*exp(-r.\*tau).\*normcdf(-d2) - s.\*exp(-d1.\*tau).\*normcdf(-d1) ;  

After setting the (scalar) inputs $K,r,$ , tau (time to maturity), $\sigma$ (sigma) and the current stock price s0, the program uses the functions ‘bscall’ and ‘bsput’ (shown at the bottom of the program) – to calculate the option premia, $c$ and $p$ (using alternative values for the stock price).  

Put–call parity is used to calculate the put premium $p p0$ – this provides a check that we have programmed the formulas for c0 and $p0$ correctly. The functions ‘bscall’ and ‘bsput’ calculate 21 values for the call and put premia corresponding to $s=s0\ –10{:}1{:}\mathrm{s}0{+}10$ where $s0{=}45$ and s runs from 35 to 55 in increments of ‘1’. We can use the output from the MATLAB program to graph the call or put premium against the stock price.  

# 16.3 ARE STOCKS LESS RISKY IN THE LONG RUN?  

We can use the Black–Scholes equation to throw some light on whether stocks are less risky if you hold them for a long period rather than for a short period of time. It is often asserted that stocks are safer in the long run than in the short run – so a young person should hold lots of her wealth in stocks and only a little in a risk-free asset (e.g. bank deposit or government bond) and vice versa for a person nearing retirement. Is this true?  

It is true that if you invest $\$10$ in the stock market today then the probability of a loss (i.e. ending up with less than $\$10$ ) becomes smaller, the further ahead is the date at which you want to sell your stocks. But a more realistic approach is to ask what is the probability of ending up with a return on your stock market portfolio which is less than the return on the risk-free asset (e.g. bank deposit or AAA-government bond) – in Example 16.3 we will refer to this as the ‘shortfall probability’.  

# EXAMPLE 16.3  

# Shortfall Probability  

Suppose the risk-free rate is $r=5\%$ p.a. and the mean return on the stock market is $\mu_{R}=15\%$ p.a. with a standard deviation of $\sigma=20\%$ p.a. Then the mean excess return is $\mu_{X}=\mu_{R}-r=10\%$ p.a. The standard deviation of the excess return is also $\sigma=20\%$ p.a. The Sharpe ratio of the stock market portfolio is $0.5~(=10/20)$ ) – so these are reasonable ‘ball-park’ fgures to use.10  

(continued)  

# (continued)  

The shortfall probability over 1 year is the probability of observing an annual stock return $R$ which is less than $r$ or equivalently, the probability that the annual excess stock return $X=R-r$ is less than zero. The excess return is assumed to be normally distributed: $X\sim N(\mu_{X},\sigma)$ . The mean value of X is $\mu_{X}=10\%$ p.a. Over a 1-year horizon if the out-turn value for $X=0$ , then this is a fall of $10\%$ (below the mean), which is half a standard deviation $(=10/20)$ . In ‘statistical language’ if $X$ turns out to be less than zero then the ‘standard normal variable’ $z=(X-\mu)/\sigma<-0.5.$ . From the standard normal distribution, the probability of $z<-0.5$ is $46\%$ , which is therefore the shortfall probability over a 1-year horizon.  

Over 20 years, the mean excess return is $\mu_{X}T=200\%$ and the standard deviation is $\sigma\sqrt{T}=89.4\dot{4}\%$ . So over 20 years, the probability of an out-turn value for $X$ that is less than zero, is equivalent to the probability that $z<-200/89.44=-2.236$ , which is $1.27\%$ . Hence the shortfall probability is much lower over a 20-year horizon than over a 1-year horizon. This is because the mean excess return of the stock market is positive at $10\%$ p.a. However, the return on your stock portfolio could be less than the risk-free return of $5\%$ even over a 20-year horizon – although there is only a $1.27\%$ chance of that happening.  

The result from calculating the shortfall probability over 20 years might seem ‘comforting’, since it is much lower than the shortfall probability over 1 year, but it should not really be as comforting as it frst seems. This is because the ‘low probability’ of $1.27\%$ tells you nothing about how much you might lose if you did end up with a loss at the end of your 20-year investment horizon. As an investor you are not just interested in the probabilities attached to certain outcomes but in the potential dollar outcomes at the end of your investment horizon. It is dollars that buy things, not ‘probabilities’.  

For example, if the stock price is initially $W_{0}=\$100$ and can have only two outcomes $+20\%$ and $-20\%$ , then at the end of one year the maximum you can lose is $20\%$ $(\$20)$ of your initial investment. After 2 years the maximum you can lose is $36\%$ of your initial investment (i.e. wealth after two consecutive negative returns, $S_{2}=S_{0}\times0.8\times0.8=64\%$ of initial wealth). But after 20 years, one possible outcome is that your fnal wealth could be as low as $S_{20}=$ $S_{0}(0.8)^{20}=S_{0}(0.0115)$ , so over $99\%$ of your initial wealth could disappear. This outcome has a very low probability (about 1 in 100,000) but if it occurred you would be devastated.  

Most people are presumably concerned about both the likelihood of a loss and the severity of the loss, should it occur. How can we get a handle on both? Well, buying a European put option on a stock (index) protects your portfolio of stocks from any ‘downside’ and therefore deals with the severity of a loss. The put also reduces the probability of a loss to zero (assuming your counterparty does not default). It insures the value of your stocks at a level equal to the strike price in the put.  

The strike price you might choose could be set equal to your initial $\$10$ investment, compounded at the risk-free rate until the end of your investment horizon $T$ , that is a put with a strike price $K(T)=S_{0}e^{r T}=(\mathbb{S}1\mathrm{m})e^{r T}$ . Then you are guaranteed that your wealth at retirement will end up at least as high as if you had invested your money in the risk-free asset.  

The put premium you pay today ensures that the minimum future value of your stock portfolio in $T$ years will at least equal what you would have got by investing in the risk-free asset. But you also have the additional beneft that if the stock market rises substantially then you will not exercise your put but simply take advantage of a high value for your portfolio of stocks.  

The price of a put option increases with the time-to-maturity and with the volatility of the stock return. For example, suppose $S_{0}=K=\S100$ , $\sigma=0.20$ and the strike price in the put increases with the risk-free rate, $K(T)=S_{0}e^{r T}=(\mathbb{S}100)e^{r T}$ . Then a put option with maturities $T=\{1,5,10,20,30,70,100\}$ years will today cost $P=\{\mathbb{S}8,\mathbb{S}17.7,\mathbb{S}24.8$ , $\$34.5,41.43,459.7,4568.3\}$ – this is shown in the lower graph of Figure 16.3.11  

![](e2823954ecd354f5c566fe9d33a368c642b20dbabc48ce84262493b2877fb86b.jpg)  

![](15ef4062ce75b9881dab64e4299c4c04a2a31b921f4d65ead4047d02808085c1.jpg)  
FIGURE 16.3 Cost of put versus maturity, $T\colon K(T)=S_{0}\:e^{r T}$  

The put option may cost you quite a proportion of the value of your initial investment – depending on the horizon over which you want to insure your stock portfolio. For example, for a horizon of 30 years the cost of the put is $\$41.43$ . For a horizon of 100 years the put premium is $\$68.3$ . If current stock return volatility is high $\sigma=0.40$ (i.e. $40\%$ p.a. say) then the put premium (for each horizon, $T$ ) is substantially higher than for $\sigma=0.20$ (upper curve in Figure 16.3) – this is because the higher stock market risk, implies a higher insurance premium.  

So now you have your answer. Market participants (who trade options) think stocks are more risky the longer the investment horizon, because today they set a higher put premium the longer the maturity date of the put. You pay a bigger insurance premium, the longer the period over which you want to insure the value of your stocks at some minimum future level.  

An even broader question is how your holdings of stocks relative to holding risk-free assets (e.g. AAA rated government bonds) should vary over your life. It turns out that there are no clear-cut answers other than the usual intuitive ones. At any point in your life cycle, diversify as much as possible (i.e. hold a ‘passive’ international portfolio of stocks, bonds, and ‘alternative assets’). If you want to buy insurance at some point, say a few years before retirement, then do so. By buying a put you guarantee a minimum value for your level of fnal wealth, but you can also beneft from any upside in the stock market, should this occur.  

It might be advisable to buy a put when you are nearing retirement, so at a ‘reasonable cost’ you secure a \$oor price for your stocks but can also beneft from any remaining upside in the stock market. For example, with 5 years to retirement (and $\sigma=0.20\dot{}$ ) then you can guarantee that the return on your $\$100$ initial investment will at least equal the risk-free rate, if today you pay the put premium of $\$17.7$ – a not unreasonable insurance premium. Of course, after paying your insurance premium, if the return on the stock market over the next 5 years is higher than the risk-free interest rate, then you will not exercise the put, but you can sell your stocks at the current high price on the NYSE.  

# 16.4 DELTA HEDGING  

Black, Scholes, and Merton derive their option price formulas by assuming ‘delta hedging’ takes place. They set up a risk-free portfolio consisting of a position in the option and a position in the underlying stock. This portfolio is risk-free because any gain or loss from a small change in the stock price is exactly ofset by changes in the value of the option’s position – this is delta hedging. As we shall see, the ratio of the number of stocks to the number of options required to set up the hedge is given by the option’s delta and is denoted $\Delta_{c}$ (for a call).  

$$
\Delta_{c}=\frac{C h a n g e\ i n\ o p t i o n s\ p r i c e}{S m a l l\ c h a n g e\ i n\ s t o c k\ p r i c e}=\frac{C_{1}-C_{0}}{S_{1}-S_{0}}=N(d_{1})=+0.4
$$  

It can be shown that the delta of a (long) call option (on a non-dividend paying stock) is $\Delta_{c}=N(d_{1})$ , so the delta can be calculated directly from the Black–Scholes formula.12 Pictorially, $\Delta_{c}$ is the slope of the line which is tangent to the Black–Scholes curve (at the current stock price). This tangent line exactly coincides with the Black–Scholes curve for small changes in the stock price (e.g. Figure 16.4, when $S_{0}=\$100$ ). But for large changes in the stock price the ‘straight line’ and the ‘curve’ do not coincide. The true change in the call premium is given by the Black–Scholes curve and the approximate change in the call premium is given by the ‘tangent line’ – that is, the option’s delta.  

Approximate $\$5$ -change in call premium $\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b\b{\b{\b{\b{\b\b{\b{\b{\b\b{\b{\b\b{\b}{\b\b{\b{\b}\b{\b{\b}\b{\b{\b\b{\b}{\b\b{\b}{\b\b{\b}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}=\Delta_{c}}\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b{\b\b{\b{\b\b{\b{\b\b{\b{\b\b{\b\b{\b\b{\b{\b\b{\b\b{\b\b{\b\b{\b\b{\b\b{\b\b{\b\b\b{\b\b{\b\b}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}$ Small $\$1$ -change in stock price  

For simplicity, suppose each call is written on 1-stock. Assume the current stock price $S_{0}=100$ , the call premium is $C_{0}=\$10$ , and option’s delta is $\Delta_{c}=+0.4.$ The option’s delta of $+0.4$ simply means that when the stock price increases by $\$1$ the call premium increases to $\$10.4$ – that is, the call premium changes by (approximately) $\$0.4$ (in the same direction as the stock price).  

Suppose Ms Short works for a large investment bank on the options desk and she has just sold 100 call options to an investor (Mr Long). Ms Short has ‘written’ 100 calls. If Ms Short does nothing she is subject to market risk – if the stock price rises, so will the call premium and if Ms Short wants to close out her position by buying back the options, she will make a loss. To hedge her options position Ms Short should today buy 40 stocks for every 100 calls she has sold (written).  

If the stock price rises by $\$1$ , the call premium rises by (approximately) $\$0.4$ so that $C_{1}=$ $\$10.4$ . Mr Long who holds one long call gains $\$0.4$ since he bought each call for $\$10$ and could now sell it for $\$10.4$ . The options trader Ms Short has a (mark-to-market) loss of $\$0.4$ – since she sold each call at $\$10$ and to close out her position she would have to buy back the call at $\$10.4$ .  

![](9613c3cb65ea417174a8d6bf54dd5d73f4644e306f4d677762aee0ccc9f000ce.jpg)  
FIGURE 16.4 Delta of a call  

Ms Short has a loss of $\$40$ $\mathit{\Omega}^{\prime}=\Phi0.4\times100\$ calls on her 100 written calls, but this is ofset by the $\$40$ gain on her long position in stocks $(=40\mathrm{stocks}\times\$1)$ – she is delta-hedged. There is no loss on Ms Short’s portfolio consisting of $^{\cdot}0.4$ stocks for each call she has sold’ or equivalently ‘holding 40 stocks and selling 100 calls’. Ms Short’s portfolio is delta neutral – as long as the change in stock prices is small.  

To maintain a delta neutral position requires continuous rebalancing since $\Delta_{c}$ changes as the stock price changes. At a stock price of $\$100$ , $\Delta_{c}=0.4$ (say). But given the shape of the Black–Scholes curve, if the stock price on day-2 is $\$110$ then the slope is $\Delta_{c}=0.5$ (Figure 16.4). Hence, for a delta-neutral position to be maintained an extra 0.1 stocks $(=0.5-0.4)$ would have to be purchased by Ms Short for each call she has sold. Since Ms Short initially sold 100 calls then she will have to purchase an additional $0.1\times100=10$ stocks (making a total of 50 stocks held on day-2), in order to maintain her delta-hedged position over day-3. This is known as dynamic delta hedging.  

Delta hedging only provides a hedge against small changes in the stock price and not against large changes. Also the option’s delta does not take account of changes in the call premium due to changes in the volatility of the stock return, the risk-free rate or the time to expiration of the option – which all afect the price of the call via the Black–Scholes formula. To hedge your written calls against such changes requires additional hedging strategies involving ‘the Greeks’.  

# 16.5 IMPLIED VOLATILITY  

How can you determine ‘the options market’s’ average forecast of volatility for a particular stock (or stock index)? This is obtained from observed options prices by ‘inverting the ‘theoretical Black–Scholes equation’. Let’s see how this is done.  

Today, data on all the variables $z=\{S,K,r,T\}$ are available (Table 16.2) and the quoted call premium, $C_{q}=\$5.748$ is observable on the Chicago options exchange. The Black–Scholes (B–S) call premium is given by Equation (16.2), here represented as $C_{B S}=f(z,\sigma)$ . Implied volatility is that value for volatility $\sigma_{i}$ which makes the theoretical B–S call premium $C_{B S}$ equal to the quoted call premium, $C_{q}=\$5.748$ , that is, $\sigma_{i}$ is the solution to:  

$$
C_{q}=\S5.748=C_{B S}=f(S,K,r,T,\sigma_{i})
$$  

$\sigma_{i}$ is the option traders’ current forecast of stock return volatility, over the life of the option, assuming the B–S pricing equation is the correct model for determining the quoted call price.  

Conceptually, to solve for implied volatility, we choose alternative ‘trial values’ $\sigma_{i}$ and calculate the ‘theoretical’ B–S price, ${\widehat{\cal C}}_{B S,i}=f(z,\sigma_{i})$ and see if the B–S price equals the quoted price $C_{q}=\$5.748$ . For example, for $\sigma_{i}=0.282$ we fnd $\widehat{C}_{B S,i}=5.6265$ (Table 16.2), which is below the current quoted price $C_{q}=\$5.748$ . We know that the B–S call premium increases with volatility so we now assume a new trial value $\sigma_{i}=0.288$ which gives $\widehat{C}_{B S,i}=5.748$ and equals the quoted  

S 164   
K 165   
r 0.0521   
$T(\mathsf{y e a r s})=0.0959$   
Quoted call premium $=5.748$  

TABLE 16.2 Implied volatility   


<html><body><table><tr><td>Trial values for sigma, o;</td><td>d1</td><td>d2</td><td>N(d)</td><td>Theoretical B-S call premium</td></tr><tr><td>0.282</td><td>0.031267</td><td>-0.05606</td><td>0.398747</td><td>CBs,i = f(z,;) 5.626545</td></tr><tr><td>0.283</td><td>0.031466</td><td>-0.05617</td><td>0.398745</td><td>5.646796</td></tr><tr><td>0.284</td><td>0.031664</td><td>-0.05628</td><td>0.398742</td><td>5.667047</td></tr><tr><td>0.285</td><td>0.031862</td><td>-0.0564</td><td>0.39874</td><td>5.687298</td></tr><tr><td>0.286</td><td>0.03206</td><td>-0.05651</td><td>0.398737</td><td>5.707549</td></tr><tr><td>0.287</td><td>0.032257</td><td>-0.05662</td><td>0.398735</td><td>5.727799</td></tr><tr><td>0.288</td><td>0.032454</td><td>-0.05673</td><td>0.398732</td><td>5.74805</td></tr><tr><td>0.289</td><td>0.032651</td><td>-0.05685</td><td>0.39873</td><td>5.7683</td></tr></table></body></html>  

Implied volatility $\sigma_{\mathrm{i}}=0.288$ $28.8\%$ p.a.)  

price $C_{q}=\$5.748$ . Hence, $\sigma_{i}=0.288$ $28.8\%$ p.a.) is the current value of implied volatility. This is done in Table 16.2 by trial and error.  

Clearly, a more efcient way of proceeding would be to have a computer program choose alternative trial values for implied volatility $\sigma_{i}$ to minimise $(\widehat{C}_{B S,i}-C_{q})^{2}$ . An example of an iterative search procedure to calculate implied volatility can be found in the Excel spreadsheet on the website – which uses the Excel optimiser SOLVER.  

There are many iterative search algorithms which can be used to calculate implied volatility (e.g. Newton–Raphson procedure). An initial guess for implied volatility is $\sigma_{1}=[|(\ln(S/K)+r T)(2/T)|]^{1/2}$ followed by the iterative process:  

$$
\sigma_{i+1}=\sigma_{i}-\frac{[\widehat{C}_{i}-C]e^{d_{1}^{2}/2}\sqrt{2\pi}}{S\sqrt{T}}
$$  

where $\begin{array}{r}{d_{1}=\frac{\ln(S/K)+(r+\sigma_{i}^{2}/2)T}{\sigma\sqrt{T}}}\end{array}$ is from the B–S formula and is computed using $\sigma_{i}$ . The term $\widehat{C}_{B S,i}=$ $f(z,\sigma_{i})$ is the $\mathbf{B}{-}\mathbf{S}$ call premium and $C_{q}=\$5.748$ is the quoted call premium. The iteration proceeds until we obtain a value for $\sigma_{i}$ which satisfes $C_{q}=\widehat{C}_{B S,i}=f(z,\sigma_{i})$ to a high degree of accuracy.13  

One of the problems in interpreting implied volatilities is that it is possible to calculate diferent implied volatilities from options with diferent strike prices (but on the same underlying stock and with the same maturity date). For example, an at-the-money option might give an implied volatility of $20\%$ p.a. while a deep out-of-the-money option (on the same stock) might yield a fgure of $24\%$ . One way out of this dilemma is to take a weighted average of these two volatilities as a measure of the ‘true’ volatility. The weights could be based on the sensitivity of the option premium to changes in volatility (i.e. the option’s ‘vega’ – see Chapter 28). As the premium for an at-the-money option is more sensitive to changes in volatility (than for an OTM option) then the weights might be 0.8 and 0.2, for example, with the best estimate of implied volatility being $0.8(20\%)+0.2(24\%)=20.8\%$ .  

You can see how the market’s view of volatility has changed over time using the implied volatility of the S&P 500 (Figure 16.5) – available on the CBOE website.  

# 16.5.1 Trading Volatility: Mispriced Options and Delta Hedging  

Delta hedging can also be used to create a risk-free portfolio so that you can proft from any mispriced options. Suppose Ms Short thinks a European call option is currently overpriced at $c$ $=\$10.1$ because she thinks other traders are using a forecast of volatility in the Black–Scholes formula that is too high. Today, writing (selling) 100 options for $\$10.1$ will result in a proft for Ms Short if the option price falls towards its true (fair) value – as other option traders recognise they have used too high a fgure for volatility. Ms Short will then be able to close out her options positions, by buying the options at their new lower market price of say $\$9.8$ . Ms Short has been using options to ‘trade volatility’.14  

![](1f062ad7230560ed7dd0888dbf96c71a30ad1874461d6992d30868d045d71cd4.jpg)  
FIGURE 16.5 Implied volatility, S&P 500  

However, this is a highly risky strategy by Ms Short since the mispriced option could increase in price if stock prices increased, before market participants correct their forecast of volatility. Can Ms Short proft from mispricing in the options (due to a miscalculation of volatility by other traders) but hedge any price risk on the options, due to changes in stock prices? Yes, by delta hedging.  

Suppose the options delta is 0.4. Then Ms Short can today hedge her options position against changes in stock prices by buying 0.4 stocks for every option she has sold – so she buys 40 stocks $(=0.4\times100)$ . If the stock price increases by $\$1$ she gains $\$40$ on the 40 stocks but the call premium increases by $\$0.4$ and she makes a (mark-to-market) loss of 40 $(=\$0.4\times$ 100 options on her 100 written options. Her short options position is now hedged against changes in stock prices. She can therefore wait until the call premium falls, when ‘other traders’ revise downwards their forecasts of volatility. Ms Short can then close out by buying back the calls at $\$9.8$ (say).  

Notice that Ms Short only makes money if her own volatility forecast (which is diferent from the ‘average market view’ of volatility) is correct, and the other options traders later recognise this fact. She does not make any money from changes in the stock price, because she is delta-hedged. In practice there are some risks and costs attached to the above strategy (and to delta hedging):  

• when rebalancing the hedged portfolio, you incur transactions costs (e.g. bid–ask spreads). • delta hedging only gives a good hedge if changes in the stock price are small.  

# 16.6 SUMMARY  

• The call premium (on a European option) is positively related to the stock price, while the put premium is negatively related to the stock price. Both call and put premia increase when the volatility of the stock return $\sigma$ , increases. Call and put premia both increase with the maturity date of the option $T$ and they also depend on the risk-free rate r. These relationships are a consequence of the Black–Scholes formulas for calls and puts.  

• We can establish upper and lower limits for call and put premia. If quoted options prices lie outside these bounds then risk-free arbitrage profts can be made.   
• A speculator who thinks that stock prices will rise (fall) in the future will buy calls (buy puts). A speculator who forecasts that stock return volatility will increase (decrease) in the near future will buy (sell) either calls or puts or both. If these volatility forecasts are correct then the speculator can close out her options positions at a proft.   
• A (naked/open) position in options is risky but this risk can be removed (over small intervals of time) by delta hedging. For example, if you have sold 100 call options each with a delta of 0.4, then you can delta-hedge your position (over the next day) by buying 40 stocks, today. Your hedge-portfolio of ‘100 written calls and 40 long stocks’ will not change in value over the next day, for small changes in stock prices. This is a delta-neutral portfolio.   
• Because the delta of an option changes over time (as the stock price changes), then to maintain a delta-neutral (hedged) position, you need to frequently alter the number of stocks you hold – this is dynamic delta hedging.   
• Using the Black–Scholes equation and the quoted option price, we can solve for the market’s current forecast of volatility (of the underlying stock return), over the life of the option – this is the option’s implied volatility.   
• If your own forecast of a stock’s return volatility is lower (higher) than ‘implied volatility’, then you believe the ‘correct price’ of the option is below (above) its quoted price. You can take advantage of this mispricing by today selling (buying) the overpriced (underpriced) option. You also need to delta hedge your options position against changes in the options price due to changes in the stock price. You are ‘trading volatility’ but hedging the value of your options portfolio from any change in stock prices.  

# APPENDIX 16: PRICE BOUNDS ON EUROPEAN OPTIONS  

Upper Bounds: Calls and Puts (on Non-Dividend Paying Stock)  

If a quoted option price is below the lower bound or above the upper bound (as set out below) then there are arbitrage profts to be made. Establishing these bounds only requires the assumption of a positive risk-free (nominal) rate of interest.  

A European call option (on a non-dividend paying stock) gives the holder the right to take delivery of a stock, and the option can never be worth more than the current price of the stock. Hence the upper bound for European calls is $C_{e}\leq S$ .  

For a European put the minimum value is $K$ at maturity $T$ , so today the European put cannot be worth more than $P_{e}\leq K e^{-r T}$ .  

In the above cases if the upper bound does not hold then arbitrage profts can be made. For example, if $P_{e}>K e^{-r T}$ an arbitrageur Ms A sells a European put for $P_{e}$ , invests the proceeds at the risk-free rate giving a cash amount to Ms A of $P_{e}e^{r T}$ at $T.$ If $S_{T}>K$ , the long put is not exercised (as it is worthless) and Ms A is worth $P_{e}e^{r T}$ at $T.$ . If $S_{T}<K$ , the long put is exercised, with a cash payout from Ms A of $K-S_{T}$ . At $T$ , Ms A is worth $P_{e}e^{r T}-(K-S_{T})=(P_{e}e^{r T}-K)+$ $S_{T}>0$ .  

# Lower Bounds: Calls and Puts (on Non-Dividend Paying Stock)  

The lower bounds for European calls and puts are:  

$$
\begin{array}{l}{C_{e}\geq\operatorname*{max}(S-K e^{-r T},0)}\\ {P_{e}\geq\operatorname*{max}(K e^{-r T}-S,0)}\end{array}
$$  

To show that (16.A.1a) must hold for a European call option (on a non-dividend paying stock) assume that $C_{e}<S-K e^{-r T}$ . Then we can show that an arbitrageur Ms A by ‘buying low – selling high’ can earn risk-free profts. Today, Ms A buys the call for $C_{e}$ , borrows a stock from her broker and short-sells the stock for S. Today the net receipts of $S-C_{e}$ , accrue to $(S-C_{e})e^{r T}$ at $t=T$ . At $T$ , if $S_{T}>K$ , Ms A exercises the call option by taking delivery of the stock and paying $K$ and then returns the stock to her broker. Ms A’s net proft at $T$ is $\Pi_{T}=$ $(S-C_{e})e^{r T}-K$ , which has a present value (today) of $P V=(S-C_{e})-K e^{-r T}>0$ (given our initial assumption that $C_{e}<\bar{S}-K e^{-r T})$ . On the other hand, if $S_{T}\leq K$ then Ms A does not exercise the call but she can buy the stock in the cash-market for $S_{T}\leq K$ (and then returns it to her broker). Hence, she makes an even greater arbitrage proft at $T$ of $\Pi_{T}=(S-C_{e})e^{r T}-S_{T}$ . The worst outcome from a long call is that it expires out-of-the-money and hence is worth zero at $T-$ this implies a lower bound today for a European call is zero, $C_{e}\geq0$ .  

To show that the lower bound for a put is given by (16.A.1b) we take the counter example where $P_{e}<K e^{-r T}-S.$ To make an arbitrage proft Ms A would buy the put and the stock today by borrowing $P_{e}+S$ . At $T$ , this portfolio is worth the larger of $S_{T}$ (when $S_{T}>K)$ ) or $K$ (when $S_{T}<K)$ . At $T_{\mathbf{\delta}}$ , Ms A owes the bank $(P_{e}+S)e^{r T}$ . But given our initial starting assumption that $\textstyle P_{e}+S<K e^{-r T}$ , then Ms A has a positive arbitrage proft at $T.$ As the worst that can happen is that the put option expires worthless, its value today is greater than zero.  

# EXERCISES  

# Question 1  

Intuitively, would you pay more today for a European put option on a stock-A, with strike price ${K_{\mathrm{A}}}=100$ or a put option-B with strike $K_{\mathrm{B}}=98$ (on the same underlying stock-A)? Assume the current stock price is $S=96$ . Brie\$y explain.  

# Question 2  

Intuitively, why would you pay more for a (European) call option-A on a (non-dividend paying) stock-A which has an annual return volatility of $20\%$ p.a. or for a call option-B on stock-B which had an annual volatility of $10\%$ p.a.? Assume all other variables which in\$uence the call premium remain constant. Brie\$y explain.  

# Question 3  

If the delta of a long call option is $+0.6$ what does this mean? Assume the current stock price is $\$100$ .  

# Question 4  

Why is the delta of a long call option positive and the delta of a long put option negative?  

# Question 5  

You have just purchased 100 puts (on stock-A) with a delta of –0.4. How can you hedge your risk over a small interval of time? Assume the current stock price is $\$100$ .  

Explain, what happens if the stock price subsequently falls by $\$2$ .  

# Question 6  

Assume, $S=100$ , $r=10\%$ p.a. (continuously compounded), $K=100$ , $\sigma=20\%$ p.a. and a call has 6 months to maturity.  

Use the Black–Scholes formula to price the European call option on a (non-dividend paying) stock.  

What happens to the call premium if next day, volatility increases to $\sigma=30\%$ p.a.?  

# Question 7  

Explain the concept of ‘implied volatility’ $\sigma_{i m p}$ for a put option (on stock-A).  

# Question 8  

Explain how ‘implied volatility’ $\sigma_{i m p}$ for a put option (on stock-A) is calculated.  