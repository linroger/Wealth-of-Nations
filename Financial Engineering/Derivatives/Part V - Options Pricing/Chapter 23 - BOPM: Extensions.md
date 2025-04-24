---
tags:
  - american_options
  - binomial_tree
  - bopm
  - continuous_dividends
  - european_options
aliases:
  - American put pricing
  - BOPM extensions
  - Binomial option pricing
key_concepts:
  - American option pricing
  - Binomial approach
  - Continuous dividend
  - Early exercise
  - Path-dependent options
---
# BOPM: Extensions  

# Aims  

• To show how the BOPM is used to price American options – these are path-dependent options and subject to early exercise.   
• To adapt the BOPM to price options on stocks that pay a continuous dividend, options on foreign exchange, and options on futures contracts.   
• To use the BOPM to price options on stocks that pay dividends at discrete intervals.   
• To demonstrate how the binomial approach can be speeded up using control variate techniques and trinomial trees.   
• To show how stock price movements in the binomial tree are determined by the ‘real world’ volatility of stock returns.  

# 23.1 AMERICAN OPTIONS  

So far we have used the BOPM to price European options (which can only be exercised at maturity). American options can be exercised at any time, over the life of the option. The question arises as to when it is optimal to exercise an American option and how this a!ects the price of American options. The following results hold for American options:  

• For a call option on a non-dividend paying stock, early exercise is never optimal. • For a call option on a dividend paying stock, early exercise is sometimes optimal. • For a put option on a stock (with or without dividends), early exercise is sometimes optimal.  

As we shall see American options on stock indices, commodities, currencies and futures contracts can be priced using results for options on stocks that pay continuous dividends.  

# 23.1.1 European Put  

We price a two-period European put with $K=100$ using RNV. The tree for the stock price has $S=100$ , $U=1.1$ , $D=0.9$ , $R=1+r=1.05$ and the risk-neutral probability $q=$ $(R-D)/(U-D)=0.75$ . First we calculate the payo!s at maturity (Figure 23.1) $P_{u u}=$ $\operatorname*{max}(K-S_{u u},0)=0$ , $P_{u d}=\operatorname*{max}(K-S_{u d},0)=1$ and $P_{d d}=\operatorname*{max}(K-S_{d d},0)=19$ . We then move backwards through the tree:  

$$
\begin{array}{l}{{P_{u}=\displaystyle\frac{1}{R}[q P_{u u}+(1-q)P_{u d}]=\displaystyle\frac{0.75(0)+0.25(1)}{1.05}=0.238}}\\ {{P_{d}=\displaystyle\frac{1}{R}[q P_{u d}+(1-q)P_{d d}]=\displaystyle\frac{0.75(1)+0.25(19)}{1.05}=2.857}}\end{array}
$$  

The (European) put premium is:  

$$
P={\frac{1}{R}}[q P_{u}+(1-q)P_{d}]={\frac{0.75(0.238)+0.25(2.857)}{1.05}}=0.850
$$  

# 23.1.2 American Put  

For an American put option the payo!s at maturity are the same as for the European put. But early exercise may be proftable at nodes $_{U,D}$ and at $t=0$ . To price the American put we see if the intrinsic value $I V=K-S$ (which is the cash received for early exercise) at any of the nodes is greater than the ‘recursive values’1 for the put, $P_{u}$ or $P_{d}$ (that is, the value of the put if you do not exercise it at that node). If $I V>$ ‘recursive value’ then early exercise is proftable and we replace the recursive value, ${}^{\cdot}P_{u}$ or $P_{d}^{\phantom{\dagger}}$ with the $I V$ at that node. Expressed mathematically the payo! to an American put at node- $U$ is:  

![](e02996963c9acaa767d8975dcf4fd641ede360c4e0bb4ecee315f4aa9cefef34.jpg)  
FIGURE 23.1 European and American put  

$$
P_{u}^{*}=\operatorname*{max}(I V_{u},P_{u})
$$  

At node- $U$ , $P_{u}=0.238$ and $I V_{u}=K-S_{u}=-10$ so early exercise is not proftable and we retain $P_{u}=0.238$ in the tree. At node- ${\bf\nabla}\cdot{\cal D} $ , $P_{d}=2.857$ and $I V_{d}=K-S_{d}=10$ so early exercise is proftable and we replace $P_{d}=2.857$ in the tree with $P_{d}^{*}=10$ . The ‘recursive value’ at $t=0$ now becomes:  

$$
P^{*}=\frac{1}{R}[q P_{u}+(1-q)P_{d}^{*}]=\frac{0.75(0.238)+0.25(10)}{1.05}=2.551
$$  

Finally, we compare $P^{*}=2.551$ and $I V_{0}=\operatorname*{max}(K-S_{0},0)=0$ , which indicates that early exercise is not proftable at $t=0$ and hence the American put premium is $P^{*}=2.551$ . Notice that the American put is worth more than the equivalent European put (which has $P=0.8503$ ) – the American put has extra ‘optionality’ as it allows for the possibility that early exercise may be proftable.  

This general principle of working backwards through the tree and seeing if early exercise is worthwhile applies when pricing all types of American options: on stock indices, currencies, futures contracts and commodities (e.g. corn, oil, gas etc.).  

# 23.2 OPTIONS ON OTHER UNDERLYING ASSETS  

It is convenient here to use the annual continuously compounded interest rate, denoted $r$ (decimal). One dollar today is worth $\$1e^{r d t}$ after a small time interval $(=T/n)$ . The equation for the risk-neutral probability $q$ when pricing an option on a stock which pays no dividends is:  

$$
q=(e^{r d t}-D)/(U-D)
$$  

# 23.2.1 Continuous Dividend Yield  

If a stock has a continuous annual dividend yield $\delta$ (decimal), then the (total) return on the stock consists of the capital gain plus the dividend yield $R_{s}=d(\ln S)+\delta$ , where $d(\ln S)\approx$ $(d S/S)$ is the growth (or proportionate change) in the stock price. In a risk-neutral world, the (total) return on a stock must equal the risk-free rate $\boldsymbol{R_{s}}=\boldsymbol{r}$ and hence, the expected growth in the stock price $d(\ln S)$ equals $r-\delta$ and $S_{1}=S_{0}e^{(r-\delta)d t}$ . In a risk-neutral world, the expected stock price at time $t_{1}$ is given by:  

$$
E^{*}S_{1}=q S_{0}U+(1-q)S_{0}D=S_{0}e^{(r-\delta)d t}
$$  

Hence:  

$$
q=(a-D)/(U-D)
$$  

where a e(r𝑤+)≡).  

When using the binomial recursion formula to price an option on a stock which pays continuous dividends at a (constant) rate $\delta$ , the only change required is that $\cdot_{S e}r^{d t},$ in the defnition of $q$ is replaced by $S e^{(r-\delta).d t}$ . The values $\dot{U}=e^{\sigma\sqrt{d t}}$ and $D=1/U=e^{-\sigma{\sqrt{d t}}}$ remain unchanged.  

# 23.2.2 Options on Foreign Currency and Futures  

To price options on a foreign currency, the equivalent to $\delta$ is the foreign risk-free rate $r_{f}$ . For options on a futures contract the underlying futures price grows at the rate $\delta=r$ , hence the defnitions for $a$ become:  

• Option on foreign currency: $a=e^{(r_{d}-r_{f})d t}$ underlying $S=$ spot exchange rate • Option on futures: $a=1$ underlying is the futures price $F$  

When setting up the tree, $U=e^{\sigma{\sqrt{d t}}}$ and $D=1/U$ remain unchanged and $\sigma$ is the real world historical volatility of the underlying asset (i.e. volatility of the stock return, volatility of the return $d S/S$ on the exchange rate or the volatility of the return $d F/F$ of the futures price, depending on the types of option being considered). Hence, the binomial tree for the underlying asset is constructed in the usual way. Hence, the only di!erence in the BOPM is the defnition of $\cdot_{a^{\prime}}$ (and hence $q$ in Equation 23.4).  

The maturity of the option $T$ is divided into $n=3$ or more time steps, with each step $d t=T/n$ – this gives a reasonably accurate value for the option’s price. For a European option on a stock we only require the payo!s at maturity $T$ to price the option. For $n=30$ time steps there are $n+1=31$ terminal stock prices – which is manageable. But for $n=30$ there are $2^{\dot{3}0}$ or about a billion alternative stock price paths (e.g. even for $n=3$ there are 8 possible paths). Since many exotic options are path dependent, the BOPM with $n=30$ takes considerable computing power and it may take quite a while for the computer to ‘grind out’ a value for the option price. Hence various methods to speed up the calculations are used, such as trinomial trees and control variate techniques.  

# 23.2.3 Control Variate Techniques  

Control variate techniques can be used in the BOPM framework to obtain more accurate values for option premia (for any fxed number of nodes, in the tree). To illustrate this approach suppose we wish to price an American option – which is path dependent. If we value the American option using the standard BOPM with $n=100$ , this should give a good estimate of its true price. Assume this ‘true BOPM price’ is $f_{A m}^{n=100}=5.27$ – but computational time will be considerable.  

To save on computational time, suppose we decide to price an American option using   
only $n=5$ steps in the BOPM and this gives $f_{A m}^{n=5}=5.48$ . In order to get closer to the true price   
$f_{A m}^{n=100}=5.27$ ,datrhde cBoOntPrMol vwairtiha tnoiqcuael caudljautsets $f_{A m}^{n=5}=5.48$ ianEthuerofpoellaonwionpgtiowna $n=5$ $f_{E u r}^{n=5}=5.3$   
(on the same underlying, with the same strike and time to maturity). Both the American   
and European binomial prices with $n=5$ are subject to error. However, we know the ‘exact’   
tBhleacpkr–icSechofltehseprAicme feorirca nEuorpotipoena tiso:n $f_{E u r}^{B S}=5.1$ (say). Using the control variate technique, $f_{A m}^{C V}$  

$$
f_{A m}^{C V,n=5}=f_{A m}^{n=5}+(f_{E u r}^{B S}-f_{E u r}^{n=5})=5.48+(5.1-5.3)=5.28
$$  

The control variate technique adjusts the American binomial price $f_{A m}^{n=5}$ (obtained using $n=5$ ), by the error in the BOPM estimate when pricing the (equivalent) European option, $(f_{E u r}^{B S}-f_{E u r}^{n=5})=-0.2$ . If the BOPM overpriced the European option by 0.2 (with $n=5$ ) we as퐸s𝜇u푟me i𝜇t will overprice the American option by the same amount. The control variate $f_{A m}^{C V,n=5}=5.28$ $n=100\mathrm{\Omega}$ $f_{A m}^{n=100}=5.27$ t=han the ‘unadjusted’ binomial estimate $f_{A m}^{n=5}=5.48$ with $n=5$ , and the c=ontrol variate approach takes much less computing time.  

# 23.3 OPTIONS ON FUTURES CONTRACTS  

Below, we show that RNV and backward recursion using the BOPM equation produces the same price for an option on a futures contract, as the ‘full no-arbitrage’ approach. A one-period call option on a futures contract delivers a long position in a futures contract. If the futures price at expiry of the option contract is $F_{T}$ and the strike is $K$ then a long call option at maturity can be cash settled for:  

$$
\mathrm{Payoffrom~call}=\operatorname*{max}(0,F_{T}-K)
$$  

Suppose the risk-free rate $r=10\%$ (per period, continuously compounded), $F_{0}=100$ , $U=$ 1.15 and $D=0.9$ , so $F_{u}=F_{0}U=115$ and $F_{d}=F_{0}D=90\$ . The payo!s for a one-period $\left\langle T=1\right\rangle$ ) call option on a futures contract with strike price $K=100$ are:  

$$
C_{u}=\operatorname*{max}(0,F_{u}-K)=15\qquadC_{d}=\operatorname*{max}(0,F_{d}-K)=0.
$$  

We noted above that an option on a futures contract can be priced under RNV using:  

$$
q=(1-D)/(U-D)=0.4
$$  

which gives:  

$$
C=e^{-r T}[q C_{u}+(1-q)C_{d}]=e^{-0.10(1)}[0.4(15)+0.6(0)]=5.429.
$$  

We now show that we obtain the same call premium using no-arbitrage and delta hedging. Suppose you are long one call at $t=0$ with (an unknown) call premium $c$ . To create a risk-free portfolio you would short futures contracts, since if $F$ increases you would lose on the short futures but gain on the long call. If you short $h$ -futures for each long call then the payo!s at $T=1$ are:  

$$
\begin{array}{r}{V_{u}=C_{u}-h(F_{u}-F_{0})}\\ {V_{d}=C_{d}-h(F_{d}-F_{0})}\end{array}
$$  

To delta hedge we choose $h$ so these payo!s are equal, which implies:  

$$
h={\frac{C_{u}-C_{d}}{F_{u}-F_{d}}}={\frac{15-0}{115-90}}=0.6
$$  

The cost of setting up the hedge portfolio at $t=0$ is simply the cost of the long call $c$ , since it cost nothing to enter the futures contact. (We ignore margin payments.) Our portfolio of one long call and $h$ short futures is risk-free and must therefore earn the risk-free rate $r=10\%$ (continuously compounded), otherwise arbitrage profts can be made. The cost of setting up the hedge portfolio at $t=0$ is simply the cost of the call $c$ , fnanced using borrowed funds. At $T$ the bank loan outstanding is $\bar{C}e^{\bar{r}T}$ and for no arbitrage profts this must equal the known payo! on the hedge position $V_{u}$ (or $V_{d.}^{\quad\cdot\mathrm{~\scriptsize~~\it~\cdot~}}$ ):  

$$
\begin{array}{c}{{C e^{r T}=V_{u}=C_{u}-h(F_{u}-F_{0})}}\\ {{C e^{0.10(1)}=15-0.6(115-100)}}\\ {{C=5.429}}\end{array}
$$  

We can obtain the solution for $c$ algebraically by substituting for $h$ from Equation (23.8) in (23.9), using $F_{u}=F_{0}U$ and $F_{d}=F_{0}D$ and rearranging to give:  

$$
C=e^{-r T}[q C_{u}+(1-q)C_{d}]\ q=(1-D)/(U-D)
$$  

Hence the ‘full no-arbitrage’ approach produces the same equation for the call premium as directly invoking RNV via (23.6b). Extending the above approach to the $n$ -period case, for European call or put futures options, is straightforward. We simply work backwards through the tree from $t=n$ to $t=0$ using $q=(1-D)/(U-D)$ .  

# 23.3.1 American Futures Option  

What about pricing an American futures option where we have the possibility of early exercise? To keep things simple, suppose we hold a two-period American call option on a futures contract. Early exercise at node- $U$ is worthwhile if the intrinsic value $I V_{u}=\operatorname*{max}(F_{u}-K,0)>C_{u}$ , where the recursive formula gives $C_{u}=e^{-r\Delta t}[q C_{u u}+(1-q)C_{u d}]$ .  

If this is the case, we replace $C_{u}$ in the tree by $F_{u}-K$ . This calculation is repeated for node- ${\bf\nabla}\cdot{\cal D}_{{\bf\mu}}$ (and at $t=0\mathrm{\dot{\Omega}}$ ) – that is comparing $I V_{d}$ , and $C_{d}$ and then $I V_{0}$ and $C_{0}$ – and taking the maximum value in each case.  

# 23.3.2 Numerical Example  

Suppose an American call futures option has a time to maturity $T=1/3$ year, strike price $K=100$ and the current futures price is $F_{0}=100$ , with the volatility of the futures (return) $\sigma=30\%$ p.a. We divide the time period $T$ into $k=$ number of ‘ups’ periods so each step in the tree is $\Delta t=T/n=1/12$ (which represents 1 month). We set $U=\stackrel{\cdot}{e^{\sigma\sqrt{d t}}}=e^{0.3/\sqrt{12}}=1.\dot{09}05$ and $D=e^{-\sigma{\sqrt{d t}}}=e^{-0.3/{\sqrt{12}}}=0.9170$ .  

For a futures option $\delta=r$ so $q=(1-D)/(U-D)=0.4784$ (and hence the option price is independent of the risk-free rate). The intrinsic value of the option at each node is $\begin{array}{r}{I V=}\end{array}$ $\operatorname*{max}(F-K,0)$ . Let each node be denoted $(t,k)$ where $t=$ time and $k=$ number of ‘ ’.  

In Figure 23.2 the upper cells show the stock price and the lower cells the option value (price). At $n=4$ , the option is exercised at the two upper nodes, only. For $(t,k)=(3,2)$ 3 3 and (2,2), the intrinsic value of the option exceeds its binomial recursive value – hence here the option is assumed to be exercised and the lower cells at these nodes show the option’s intrinsic value $I V=\operatorname*{max}(F-K,0)$ , rather than its binomial recursive value. The $I V\mathrm{{s}}$ at these nodes are then used in calculating the next recursive values as we move backwards through the tree and the American call premium is 6.387. (As we increase the number of nodes in the tree, so that $n>30$ , we obtain a more accurate estimate of the call premium.)  

![](9aa89c5eed0544cc0df938cf87c2688b3f6b7d93bc4b4c723d2bb8ab612bd698.jpg)  
FIGURE 23.2 Binomial tree for American call on index futures Note: Shaded areas indicate intrinsic value, used in the calculations  

For American options on stocks paying continuous dividends at a rate $\delta$ and options on FX, the procedure is the same as above. The tree is constructed using $U=e^{\sigma{\sqrt{d t}}}$ and $D=1/U$ where $\sigma$ is the real world (estimated annual) standard deviation of the stock return or FX return. Also $a=e^{(r-\delta)d t}$ for the option on the stock and $a=e^{(r-r_{f})d t}$ for the FX-option (where $r=$ domestic interest rate and $r_{f}=$ foreign interest rate).  

The BOPM can also be used to price options where the underlying asset is a stochastic interest rate (e.g. options on T-bonds, on T-bond futures or options on interest rates, known as caps and foors) but this requires a tree where interest rates are allowed to vary at each node. This is dealt with in Chapter 41.  

# 23.4 OPTIONS ON DIVIDEND-PAYING STOCKS  

# 23.4.1 Dividends and the BOPM  

We have already seen that for a stock (or stock index) that pays a constant continuous dividend yield $\delta$ , we simply use $a=e^{(r-\delta)d t}$ as the risk-neutral probability and proceed in the usual fashion to price European or American options on the dividend paying stock (index). In practice, the continuously compounded dividend rate $\delta$ has to be estimated and clearly while the assumption of a constant dividend rate is not unreasonable for a stock index (which contains many stocks), it is not plausible for individual stocks, where dividend payments tend to be bunched in certain months of the year. The BOPM gets a little tricky when dividends are discrete.  

# 23.4.2 Single Known Dividend Yield  

Assume the option matures in 30 days, $T=30/252$ , $\Delta t=1/252$ so that $n=T/\Delta t=30.$ . We now apply the BOPM to a European call option where the underlying stock (index) pays $a$ single dividend at time $t=i(\Delta t)$ . If the time $t=i(\Delta t)$ is prior to the stock going ex-dividend, the nodes on the tree correspond to stock prices:  

$$
{\cal S}U^{j}D^{i-j}\qquad(j=0,1,2,\ldots i)
$$  

If time $t=i(\Delta t)$ is after the stock goes ex-dividend the nodes would have values  

$$
S(1-\delta)U^{j}D^{i-j}\qquad(j=0,1,2,\ldots i)
$$  

where $\delta$ is the known single dividend yield. For example, given a single dividend payment prior to the 2nd node, the binomial tree is shown in Figure 23.3. If there are several known dividend yields $\delta_{i}$ over the life of the option, then the nodes after the ex-dividend dates would be $S(1-\delta_{i})U^{j}D^{i-j}$ .  

![](2dd835fa50c131d06b8b3bf5df252c0c685510118560cb537b27e1eaa4f35105.jpg)  
Ex-dividend date just before 2nd node Single dividend payable with dividend yield known – the tree recombines  

FIGURE 23.3 Single dividend, known dividend yield  

# 23.4.3 Known Dollar Dividend  

First note that when a dividend is paid, the stock price falls by the amount of the dividend payment $D$ . (We ignore any tax issues here.)2 If we let $U=1/D$ then unfortunately with discrete dividends, the binomial tree for $s$ does not recombine and there are a very large number of nodes to evaluate. To avoid this problem and obtain a recombining tree we proceed as follows. We let $U$ and $D$ apply to the stock price minus the present value of all known future dividends (over the life of the option), which we denote $S^{*}$ . Suppose a single ex-dividend date is at $\tau$ and the dividend paid is $D i v$ . Then the values for $S^{*}$ at times $i\Delta t$ are:  

Before -dividend date: $\begin{array}{l l}{{S^{*}=S-(D i v)e^{-r(\tau-i\Delta t)}}}&{{\mathrm{for}i\Delta t<\tau}}\\ {{S^{*}=S}}&{{\mathrm{for}i\Delta t>\tau}}\end{array}$ After -dividend date:  

The tree for $S^{*}$ is constructed using $U=e^{\sigma^{*}\sqrt{\Delta t}}$ , $D=1/U$ where $\sigma^{*}=$ volatility of $S^{*}$ .3 This gives us a recombining tree for $S^{*}$ . To obtain a ‘new’ tree, we now add back the PV of future dividends, at each node. Suppose we have calculated $S_{0}^{*}$ at $t=0$ . Then a ‘new’ tree for $s$ at times $i\Delta t$ is:  

Before -dividend date: $\begin{array}{l l}{{S_{n e w}=S_{0}^{*}U^{j}D^{i-j}+D i v\ e^{-r(\tau-i\Delta t)}}}&{{\mathrm{for}\ i\Delta t<\tau}}\\ {{S_{n e w}=S_{0}^{*}U^{j}D^{i-j}}}&{{\mathrm{for}\ i\Delta t>\tau}}\end{array}$ After -dividend date:  

The option is then priced o! this ‘new’ tree $S_{n e w}$ using $q=(e^{r\Delta t}-D)/(U-D)$ as the risk-neutral probability.4  

For example, suppose $r=5\%$ , there is one dividend of $\$10$ with an ex-dividend date at the end the second month (0.1667 years), then $P V(D i v)=\S10\ e^{-0.05(0.1667)}=\S9.917$ . If $S_{0}=\$100$ then $S_{0}^{*}=\S90.083$ . We calculate the tree for $S_{n e w}$ using the above equations and then work backwards through the tree (from the maturity date of the option) to give the European call (or put) premium.  

To value an American call with strike $K=110$ on a dividend paying stock we would calculate the intrinsic value at each node and the early exercise decision is based on $I V=S_{n e w}-K$ (not $S^{*}-K)$ . For example, if the stock has just gone ex-dividend and at the next ‘upper node’ $S^{*}=\$110$ and the dividend at $\tau$ is $D i v=\$3$ then $S_{n e w}=\$113$ (since the present value of the dividend at $\tau$ is the dividend itself of $\$3$ ). For an instant, $S_{n e w}=\$113$ and then ‘immediately’ it falls to $\$110$ as it goes ex-dividend. But just before the stock goes ex-dividend the call has an intrinsic value of $I V=3$ . If $I V=3$ at this node and this is greater than the recursive value $C_{\tau}$ in the tree, then we replace $C_{\tau}$ with $I V=3$ . We proceed in this way at each node, to see if the intrinsic value exceeds the recursive value. So, apart from the construction of the stock price tree, an American option on a stock which pays discrete dividends is priced in the usual way.  

# 23.5 SUMMARY  

• For options on a stock paying dividends at the continuous rate $\delta$ (decimal), the stock price tree is constructed using $U=e^{\sigma{\sqrt{d t}}}$ and $D=1/U$ but the risk-neutral probability is now $q=(a-D)/(U-D)$ where $a=e^{(r-\delta)\Delta t}$ . The option is then priced in the usual way by backward recursion (under RNV).   
• For options on a foreign currency, $\delta=r_{f}$ the foreign interest rate and hence $a=e^{(r-r_{f})\Delta t}$ (where $a=1\mathrm{\dot{\Omega}}$ ), $S=$ spot- rate and $\sigma=$ volatility of the return (proportionate change) in the spot-FX rate.   
• For options on a futures contract, $\delta=r$ hence $a=1$ and $q=(1-D)/(U-D)$ . In the tree $s$ is replaced by $F$ the forward rate, and $\sigma$ is the volatility of $d F/F$ .   
• American, European and many path-dependent ‘exotic options’ can be priced using the BOPM under RNV – so the method is very fexible.   
• American options are valued using backward recursion but at each node we test to see if early exercise is proftable by comparing the intrinsic value $I V$ (when exercised) with the binomial recursive value (no exercise), and we take the maximum of these two values. For example at node- $U_{:}$ , the value of the put can be written $P_{u}^{*}=\operatorname*{max}(I V_{u},P_{u})$ , where $P_{u}$ is the BOPM recursive value.  

• To price an option on a stock that pays discrete dividends we construct a tree where we let $U$ and $D$ apply to $S^{*}{=}$ ‘the stock price minus the present value of all known future dividends over the life of the option’. This allows the tree to recombine, which substantially improves computational e\$ciency. The option is then priced o! a ‘new’ tree for $S_{n e w}$ where we add back the PV of future dividends, at each node. Expected payo!s are calculated using the (usual) risk-neutral probability, $q=(e^{r d t}-D)/(U-D)$ . • Computational time in the BOPM can be reduced by using control variate techniques or a trinomial tree (see Appendix 23).  

# APPENDIX 23: BOPM AND RISK-NEUTRAL VALUATION  

As we see in Chapters 47 and 48, continuous time models of stock prices $s$ can be represented in terms of continuously compounded $(^{\bullet}\log^{\cdot})$ returns $d(\ln S)$ or proportionate changes $d S/S$ over a short period of time, $d t\to0$ . The ‘up’ and ‘down’ movements in the binomial tree for stock prices are an approximation to these continuous time processes and are designed to produce an outcome for the stock price $S_{T}$ at $T$ , which is (approximately) lognormal. This requires movements of the stock price in the tree to replicate the ‘real world’ volatility of the stock price. In addition, when pricing options (on a non-dividend paying stock) using the BOPM under risk-neutral valuation (RNV), we must set the growth rate of the stock price equal to the risk-free rate.  

In the BOPM we divide the time to maturity of the option T(years) into $n$ -periods of equal length, $d t=T/n$ . Over a small interval of time $d t$ , the expected return of the stock is measured as (where $\mu=$ continuously compounded annual growth rate, decimal). Over a small time interval, the variance of the stock return is $\sigma^{2}d t$ (where $\sigma=$ annual standard deviation (decimal) of the continuously compounded stock return and is calculated from historical data). Hence:  

$$
{\begin{array}{r l r l}&{E(S_{1})/S_{0}=e^{\mu\ d t}}&&{{\mathrm{(expected~return~in~the~'real~world')}}}\\ &{\operatorname{var}(S_{1}/S_{0})=\sigma^{2}d t}&&{{\mathrm{(variance~in~the~'real~world')}}}\end{array}}
$$  

We price an option (on a non-dividend paying stock) using the BOPM under RNV. Therefore we calibrate $U,D$ and $q$ , so the stock price in the tree satisfes two conditions (over the time period $d t$ ):  

1. Expected return equals the risk-free rate $E(S_{1})/S_{0}=e^{r d t}$ (RNV)   
2. Variance of the stock price, $\nu a r(S_{1})=S_{0}^{2}\sigma^{2}d t$ (‘real world’ volatility)  

Hence, RNV and replicating the ‘real world’ volatility gives two equations and three unknowns $(U,D,q)$ :  

$$
E(S_{1})=q S_{0}U+(1-q)S_{0}D=S_{0}e^{r d t}
$$  

$$
\begin{array}{c}{\operatorname{var}(S_{1})\equiv E(S_{1}^{2})-[E(S_{1})]^{2}}\\ {=q(S_{0}U)^{2}+(1-q)(S_{0}D)^{2}-[q S_{0}U+(1-q)S_{0}D]^{2}=S_{0}^{2}\sigma^{2}d t}\end{array}
$$  

From (23.A.1):  

$$
[q U+(1-q)D]=e^{r.d t}
$$  

Multiplying (23.A.3) by $(U+D)$ and simplifying:  

$$
\begin{array}{c}{{(U+D)[q U+(1-q)D]=(U+D)e^{r.d t}}}\\ {{q U^{2}+(1-q)D^{2}+U D=(U+D)e^{r.d t}}}\end{array}
$$  

Simplifying (23.A.2):  

$$
[q U^{2}+(1-q)D^{2}]-[q U+(1-q)D]^{2}=\sigma^{2}d t
$$  

Substituting in (23.A.6) from (23.A.5) and (23.A.3):  

$$
\left[(U+D)e^{r.d t}-U D\right]-e^{2r.d t}=\sigma^{2}d t
$$  

We have three unknowns $q$ , $U$ and $D$ and only two equations – the RNV equation (23.A.1) and the (simplifed) volatility equation (23.A.7). We arbitrarily use our one ‘degree of freedom’ by setting $U=1/D$ . Equation (23.A.1) or equivalently (23.A.3) gives directly:  

$$
q=\frac{a-D}{U-D}\qquad\quad a=e^{r d t}
$$  

If higher order terms than $d t$ are ignored, a solution to the volatility equation (23.A.7) (with $\mathrm{U}=1/D)$ is:  

$$
U=e^{\sigma{\sqrt{d t}}}\qquad\mathrm{and}\qquadD=e^{-\sigma{\sqrt{d t}}}
$$  

In a risk-neutral world $U$ and $D$ are independent of the expected growth rate of the stock (i.e. the expected ‘real world’ stock return $\mu$ ), and therefore so is the option price. From (23.A.9) we have $\dot{U}/D=e^{2\sigma\sqrt{d t}}$ so $U/D$ is determined by the ‘real world’ volatility of the stock return and hence so are the option premia.  

As we move from the ‘real world’ to our equations in a ‘risk-neutral’ world, the expected return on the stock changes from $\mu$ to $r$ (see 23.A.1) but the volatility of the stock return is the same as in the real world – this is a manifestation of Girsanov’s theorem. It is easy to see that (23.A.9) satisfes the volatility equation (23.A.7) by substituting (the Taylor series approximations up to order $d t$ ):  

$$
\begin{array}{r l r l}&{e^{\sigma\sqrt{d t}}=1+\sigma\sqrt{d t}+(1/2)\sigma^{2}d t}&&{e^{-\sigma\sqrt{d t}}=1-\sigma\sqrt{d t}+(1/2)\sigma^{2}d t}\\ &{e^{r d t}}&{=1+r d t}&&{e^{2r d t}=1+2r d t}\end{array}
$$  

in the left-hand side of (23.A.7) (and ignoring terms in $d t^{2}$ or higher).  

The above analysis can be repeated for an option on an asset that pays a continuous yield (e.g. dividend yield) at a rate $\delta$ . The return on a stock equals the capital gain $d S/S$ plus the (continuously compounded, dividend) yield . In a risk-neutral world the asset (stock) return equals the risk-free rate $r$ and hence the expected value of the asset price $E S_{1}=S_{0}e^{(r-\delta)d t}$ . Therefore, to price an option on an asset that pays a continuous yield, the only change in the above analysis is in (23.A.1) where we replace $S_{0}e^{r d t}$ with $S_{0}e^{(r-\delta)d t}$ which results in $a=e^{(r-\delta)d t}$ in (23.A.8).  

# Negative Risk-neutral Probabilities  

Sometimes when $\sigma$ is very small, the above formulas can give negative probabilities for $q$ – which are meaningless. One ‘trick’ to avoid this problem is to assume the option is written on a futures contract with futures price $F$ (even though in reality it is not!), then $a=1$ and we never get negative risk-neutral probabilities. The tree for $F$ is constructed at each node and the underlying cash market price at each node is obtained using $S_{i}=F_{i}e^{-(r-\delta)i d t}$ , where $\delta=$ constant dividend yield (or the foreign interest rate for a foreign currency option).  

# Other Risk-neutral Probabilities  

In the above derivation we found we had ‘one degree of freedom’ and imposed $U=1/D$ (Cox, Ross and Rubinstein 1979). This gives unique values for $U,D$ and $q$ with which to construct the binomial tree, which is then used to price the option. But we could have used another ‘trick’ in the derivation of $U,D$ and $q$ , which results in $q$ being the same for options with diferent underlying assets, $s$ (e.g. options on stocks that pay no dividends, on stocks that pay continuous dividends, options on FX-spot rates or commodities or futures contracts).  

This seems a little counter-intuitive but it is to do with how we ‘allocate’ our one degree of freedom. Given our two equations to determine the three ‘unknowns’ $U,D$ and $q$ we can arbitrarily set $q=0.5$ . Then solving our two equations (23.A.3) and (23.A.7) for $U$ and $D$ we obtain (when terms of higher order than are ignored):  

$$
\begin{array}{c}{{U=e^{(r-\sigma^{2}/2)d t}+\sigma\sqrt{d t}}}\\ {{{}}}\\ {{D=e^{(r-\sigma^{2}/2)d t}-\sigma\sqrt{d t}}}\end{array}
$$  

Clearly, using these values of $U$ and $D$ would give a di!erent tree for the stock price than if we use the Cox, Ross and Rubinstein formulas but the value of the option premium from backward recursion using the BOPM under RNV is the same using either approach. The different values for $q$ in the two trees would exactly o!set the di!erent values for $s$ , and the price of the option using backward recursion turns out to be the same. (After all we can only have one ‘correct’ or ‘no-arbitrage’ price for the option.)  

For a stock (index) paying a continuous dividend at a rate $\delta$ , we replace $r$ by $r-\delta$ in Equations (23.A.10a) and (23.A.10b):  

$$
\begin{array}{c}{{U=e^{(r-\delta-\sigma^{2}/2)d t+\sigma\sqrt{d t}}}}\\ {{{}}}\\ {{D=e^{(r-\delta-\sigma^{2}/2)d t-\sigma\sqrt{d t}}}}\end{array}
$$  

In addition, for currency options $\delta=r_{f}$ the foreign interest rate and for options on futures contracts $\delta=r$ , so $r$ is omitted from the above equations. Hence, Equations (23.A.11a) and (23.A.11b) enable construction of a tree for the underlying asset and hence price options on dividend paying stocks, currencies and futures contracts when using $q=0.5$ .  

Note that the size of $U$ and $D$ (and the value of $q$ ) have all been derived assuming a risk-neutral world. So, when pricing options, the tree for the stock price does not represent actual movements in the stock price but it still correctly prices the option because of the equivalence of backward recursion using RNV and the ‘no-arbitrage’ approach.  

# Trinomial Tree  

When pricing an option, the use of a trinomial tree rather than a binomial tree can reduce computational time. The tree is set up so that at each node there is an up, middle, and down step. For example, for a non-dividend paying stock, the tree mimics the ‘real world’ volatility and has the stock price growing at the risk-free rate if:  

$$
\begin{array}{r c l}{{U}}&{{=}}&{{{\displaystyle e}^{\sigma\sqrt{3.4t}}}}\\ {{q_{d}}}&{{=}}&{{-\sqrt{\displaystyle\frac{d t}{12\sigma^{2}}}\left(r-\frac{\sigma^{2}}{2}\right)+\displaystyle\frac{1}{6}}}\\ {{}}&{{}}&{{}}\\ {{q_{u}}}&{{=}}&{{\sqrt{\displaystyle\frac{d t}{12\sigma^{2}}}\left(r-\frac{\sigma^{2}}{2}\right)+\displaystyle\frac{1}{6}}}\\ {{}}&{{}}&{{}}\\ {{q_{m}}}&{{=}}&{{2/3}}\end{array}
$$  

where $q_{d},q_{u},q_{m}$ are the risk-neutral probabilities for the down move, up move and for the ‘middle’ path. We then use backward recursion on the trinomial tree to calculate the option premium. For assets paying a continuous dividend yield at a rate $\delta$ , we replace $r$ by $r-\delta$ in the above equations. Also, for currency options $\delta=r_{f}$ the foreign interest rate and for options on futures $\delta=r$ , so $r$ is omitted from the above equations. The trinomial tree is equivalent to the explicit fnite di!erence method, discussed in Chapter 48.  

# EXERCISES  

# Question 1  

Why is the BOPM (and other ‘tree methods’) often seen to be more fexible than closed-form solutions for the options price, such as the Black–Scholes formula for calls and puts?  

# Question 2  

What are the drawbacks of using the BOPM to price options?  

# Question 3  

You want to price an American put option (on a non-dividend paying stock) using the BOPM with $n=20$ steps. How does the control variate technique improve the accuracy of the price of the American put? Explain.  

# Question 4  

You hold a long (European) put option on a futures contract. The current futures price is $F_{0}=$ 100 and the futures price can move to either $F_{u}=115$ or $F_{d}=90$ . The futures option has a strike price $K=100$ , $T=1$ period to maturity and the risk-free rate $r=10\%$ p.a. (continuously compounded).  

(a) Create a risk-free portfolio consisting of one long put and futures contracts.   
(b) Using the no-arbitrage condition, calculate the European put premium.   
(c) Check that the value of your hedge portfolio is the same at the up and the down nodes.   
(d) Check your answer in (b) by using the BOPM formula for the price of the put option.  

# Question 5  

The index futures price is $F_{0}=100\$ . An American put option on the futures index has $K=100$ , $r=8\%$ p.a. (continuously compounded), $\sigma=30\%$ p.a., $T=1/3$ year (4 months). Use a tree with $n=4$ steps to calculate the ‘up’ and ‘down’ moves for the futures price and show that the price of the American put is $P=6.3870$ .  

# Question 6  

The spot FX-rate is $S_{0}=1.52$ $(\$12$ , USD per GBP). An American put option on the USD has $K=1.5$ (USD/GBP), the interest rate in the US is $r=4\%$ p.a. (continuously compounded), the volatility of the USD-GBP spot exchange rate $\sigma=12\%$ p.a., the option has $T=1$ year to maturity and the interest rate in the UK is $r_{f}=5\%$ p.a. (continuously compounded).  

Use a tree with $n=4$ steps to calculate the ‘up’ and ‘down’ moves for the spot FX-rate and show that the price of the American put is $P=0.0658$ (USD/GBP).  