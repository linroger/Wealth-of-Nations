---
tags:
  - american_options
  - bopm
  - european_options
  - fixed_income_derivatives
  - interest_rate_lattice
aliases:
  - BOPM
  - Chapter 41
  - Pricing Derivatives
key_concepts:
  - American option pricing
  - Arbitrage-free pricing
  - European option pricing
  - Interest rate lattice
  - Term structure consistency
---
# Pricing Fixed Income Derivatives: BOPM  

# Aims  

• To derive an interest rate lattice, which precludes risk-free arbitrage profts and is consistent with the current term structure of interest rates. • To demonstrate how the BOPM is used to price European and American options such as caps, foors, collars, swaptions, callable bonds, and FRAs/FRNs with caps and foors.  

In this chapter we price many diferent fxed income derivatives using the BOPM with an arbitrage-free lattice for the short-rate of interest. This ‘no-arbitrage’ approach ensures that the interest rate lattice is constructed so it is impossible to make risk-free profts by trading (diferent bonds) along the current yield curve. The lattice is calibrated so that it exactly mimics the current observed term structure – hence, the current term structure is an input to the BOPM and the output is the derivatives price.1  

Pricing interest rate derivatives is more di\$cult than pricing options on stocks, currencies, commodities and futures contracts because some of the assumptions of the original Black–Scholes model are unlikely to hold for fxed income assets. In particular:  

(i) the underlying stochastic process for short-term interest rates is more complex than for stock prices – for example, interest rates are mean reverting and therefore do not follow a geometric Brownian motion (GBM).  

(ii) to price some interest rate derivatives we need not only the possible paths taken by a 90-day interest rate but the possible paths for interest rates with other maturities.   
(iii) the volatility of interest rates may not be constant and may be diferent at diferent horizons.   
(iv) if interest rates are stochastic, we should not discount the option’s payofs using a constant interest rate.  

In Chapter 40 we noted that Black’s model is widely used to price some fxed income derivatives such as European options on T-bonds, T-bond futures, Eurocurrency futures and swaptions because it provides a closed-form solution. But it has its limitations and in particular it does not price American and ‘exotic’ fxed income options. The BOPM is more fexible and can price many diferent fxed income derivatives – although being a numerical technique it is subject to estimation error and may require considerable computing power.  

# 41.1 NO-ARBITRAGE APPROACH: BOPM  

The BOPM can be used to price interest rate derivatives in much the same way as we demonstrated for stocks, but there are also some key diferences. First, we require a lattice for the sequence of one-period spot rates (Figure 41.1) but this lattice must not allow any arbitrage profts to be made along the yield curve. This means that, given our chosen sequence of one-period spot rates, it must not be possible to sell a (zero-coupon) bond and use the proceeds to purchase other (zero-coupon) bonds and make risk-free profts.  

![](fbe9d23f71d964b765d83f7ac0baa865e27a368b20a8e35934909c55da0fd4b7.jpg)  
FIGURE 41.1 Short-rate lattice  

The lattice in Figure 41.1 shows the possible one-period rates over four time periods and $q$ is the risk neutral probability of an ‘up’ move. As noted in an earlier chapter, when pricing options, under risk-neutral valuation (RNV) we can assign a value $q={}^{1}/_{2}$ . The size of the ‘up’ and ‘down’ movements in the one-period rates are then derived to be consistent both with the current observed term structure of 1-year, 2-year etc. spot rates and with empirical estimates of the term structure of volatilities of these spot rates. This is directly analogous to the calculation of $U$ and $D$ in the BOPM for stock options. However, for interest rates, the details of how to calculate the ‘up’ and ‘down’ movements are a little more complex. Assume for the moment that all the one-period rates in the lattice have been calculated and do not allow any risk-free arbitrage opportunities.  

Terms such as $V_{u u}$ (see Figure 41.1) denote the value of the derivative at this node. Also it can be shown that at each node such as (at $t=2$ ), we know not only the one-period rate $r_{u u}$ , say, but also the two-period rate (at node-uu) that is $r_{u u}(2,4)$ and the three period rate, $r_{u u}(2,5)$ etc., although the latter are not marked on the lattice of Figure 41.1.  

# 41.1.1 Notation  

What is important in the lattice (Figure 41.1) is the time period $t$ along the horizontal axis and the number of ‘up’ moves. We could use the notation $r_{t,i}$ where $t=$ time and $i=u,d,$ , uu, dd, ud, etc. However, this cannot be used when programming the BOPM. Therefore we designate $i$ as the number of ‘up’ moves in the lattice. This implies that the following equivalent notation can be used:  

$$
r_{1d}=r_{10},r_{1u}=r_{11}\mathrm{and}r_{2,d d}=r_{2,0,}r_{2,u d}=r_{2,1},r_{2,u u}=r_{2,2}
$$  

When using $r_{t,i}$ the $i$ indicates the number of ‘up’ moves. A ‘down’ move is given the number zero, which geometrically is a horizontal move (Figure 41.2). Any of the one-period rates such as $r_{10}$ and $r_{11}$ are like one-period forward rates, when viewed from time zero.  

Given the short-rate lattice in Figure 41.2, we can:  

• demonstrate that no risk-free arbitrage profts are possible • illustrate how the size of the ‘up’ and ‘down’ movements in the lattice can be made consistent with the current term structure of interest rates and volatilities.  

# 41.1.2 Short-rate Lattice and the Term Structure  

At each node $(t,i)$ we have a short-rate $r_{t,i}\geq0$ which is the one-period rate applicable from $t$ to $t+1$ (Figure 41.2). At time $t$ there are a total of $t+1$ nodes indexed by $i=0$ to $t$ . We do not assign real world probabilities for a transition to ‘up’ (or ‘fat’) for the short-rate. Because we are pricing an option, we assume RNV and assign risk-neutral probabilities for an ‘up’ move of $^1/_{2}$ .  

![](012cc5dbb987b22689c20ddbaa3537bdd28c1f4ee921c248047cceadd2fd65a7.jpg)  
FIGURE 41.2 Short-rate lattice, rt,i  

Consider any interest rate security (e.g. 3-year zero-coupon bond) which has a value $V_{t,i}$ at node $(t,i)$ somewhere in the middle of the lattice. Under RNV:  

$$
V_{t,i}=\frac{1}{\left(1+r_{t,i}\right)}\left(\frac{1}{2}V_{t+1,i+1}+\frac{1}{2}V_{t+1,i}\right)+D_{t,i}
$$  

where $D_{t,i}$ is the cash fow (e.g. coupon payment at node $(t,i)$ , which depends solely on $t$ and $i$ (i.e. it is not path dependent). We use this recursion to derive our short-rate lattice so that it is consistent with observed prices (and hence spot rates) of zero-coupon bonds of 1-year, 2-year etc. maturities.  

# 41.1.3 Arbitrage Opportunities  

Is the lattice free from arbitrage opportunities? The answer is yes. To see this most simply, consider possible arbitrage opportunities over one period when you are currently at node $(t,i)$ . We know that:  

$$
V_{t,i}=\frac{1}{2}\left[\frac{V_{t+1,i}+V_{t+1,i+1}}{(1+r_{t,i})}\right]
$$  

Proftable arbitrage over one period requires $V_{t,i}\leq0$ and $V_{t+1,i}\geq0$ , $V_{t+1,i+1}\geq0$ with one of these inequalities being strict. This is impossible since the coe\$cients on the $V$ ’s in parentheses are both positive. Hence no arbitrage is possible over one period and by induction it can be shown that this is true over longer horizons.  

# 41.1.4 The Lattice Meets the Data  

The lattice of one-period rates must be representative of actual observed interest rates. But what does ‘representative’ mean? Consider the lattice at the end of year-1 (Figure 41.2). First, the ‘spread’ between $r_{d}$ and $r_{u}$ at $t_{1}$ should represent the observed volatility of these one-period rates, which when viewed from $t_{0}$ is the volatility of the forward rate between $t_{1}$ and $t_{2}$ , which can be denoted $\sigma_{1}$ .  

Second, it would seem reasonable that our (one-year) spot rates in the lattice should also be consistent with the observed term structure, for 1-year, 2-year, 3-year etc., spot rates and zero-coupon bond prices. Let us see how this is accomplished in the Black–Derman–Toy (BDT) (1990) model. Today, we observe the current spot rates, $r_{i}$ and the corresponding (zero-coupon) bond prices (with face value of $\$1$ ), where $P_{0,i}=\mathbb{\S}1/(1+r_{i})^{i}$ for $i={1,2,3,4,5}$ and also the volatilities of the implicit forward rates (Table 41.1).  

The quoted one-year bond price $P_{\mathrm{0,1}}=0.9852$ is determined solely by the observed 1-year spot rate $r=1.5\%$ . Our aim is to construct a lattice of one-period interest rates consistent with the observed data in Table 41.1. To do so we move forward through the lattice. First we need to fnd $r_{u}$ and $r_{d}$ (see Figure 41.2). In the BDT model, spot rates are assumed to be lognormally distributed so  

$$
\ln(r_{u}/r_{d})=2\sigma_{1}\sqrt{d t}
$$  

where $\sigma_{1}=20\%$ is the volatility of the observed forward rate between at $t_{1}$ and $d t=1$ -year. Hence $\sigma_{1}$ determines the ‘gap’ between $r_{u}$ and $r_{d}$ as one would expect. Once we fx $r_{d}$ then $r_{u}$ is determined by the above equation. We have to ‘fx’ $r_{d}$ by trial-and-error (iteratively) so that $r_{d}$ and $r_{u}$ are consistent with the observed 2-year spot rate and with the observed current (two-year maturity) bond price $P_{0}(2)=0.9612$ . Suppose we arbitrarily choose $r_{d}=2.01\%$ , then from (41.3):  

$$
r_{u}=\mathrm{e}^{2(0.20)(1)}(2.01\%)=1.4918(2.01\%)=3\%
$$  

Hence $r_{u}=1.4918r_{d}$ . With these ‘trial values’ of $r_{d}$ and $r_{u}$ we can now work out the price of a 2-year zero-coupon bond using Equation (41.1) (with $D_{t,i}=0\mathrm{\i}$ ):  

$$
V_{u}=\frac{1}{1.03}\left[\frac{1}{2}(\Phi1)+\frac{1}{2}(\S1)\right]=0.9709
$$  

TABLE 41.1 Initial term structure and volatilities   


<html><body><table><tr><td>Maturity of zero rates</td><td>Spot rates</td><td>Prices</td><td>Volatility</td></tr><tr><td>1 year</td><td>0.015</td><td>0.9852</td><td>91 = 0.2</td></tr><tr><td>2 years</td><td>0.02</td><td>0.9612</td><td>92 = 0.19</td></tr><tr><td>3 years</td><td>0.025</td><td>0.9286</td><td>93 = 0.18</td></tr><tr><td>4 years</td><td>0.03</td><td>0.8885</td><td>94 = 0.17</td></tr><tr><td>5 years</td><td>0.035</td><td>0.8420</td><td></td></tr></table></body></html>  

$$
V_{d}=\frac{1}{1.0201}\left[\frac{1}{2}(\S1)+\frac{1}{2}(\S1)\right]=0.9803
$$  

$$
V_{0}(2)=\frac{1}{1.015}\left[\frac{1}{2}(0.9709)+\frac{1}{2}(0.9803)\right]=0.9612
$$  

Here our trial value of the 2-year bond price $V_{0}(2)=0.9612$ is equal to the quoted bond price $P_{0}(2)=0.9612.$ Hence, our initial guess $r_{d}=2.01\%$ is consistent with the observed 2-bond price and spot yield. If we had found that $V_{0}(2)\neq P_{0}(2)$ , then another ‘trial value’ for $r_{d}$ would be required. In practice, what we have are two (non-linear) equations (41.1) and (41.3) in two unknowns $r_{d}$ and $r_{u}$ which in general can be solved using some iterative algorithm (e.g. Excel’s ‘Solver’). Having obtained $r_{u}$ and $r_{d}$ we now move forward through the lattice, so:  

$$
\begin{array}{r}{r_{u d}=r_{d d}e^{2\sigma_{2}\sqrt{\Delta t}}}\\ {r_{u u}=r_{u d}e^{2\sigma_{2}\sqrt{\Delta t}}}\end{array}
$$  

Once we have ‘fxed’ $r_{d d}$ , then we can use (41.7a) and (41.7b) with $\sigma_{2}=19\%$ (Table 41.1) to determine $r_{u d}$ and $r_{u u}$ . Again, we use the lattice to obtain a trial value for a 3-year coupon bond, $V_{0}(3)$ using backward recursion from $t_{2}$ (with $r_{u}$ and $r_{d}$ already known). We alter $r_{d d}$ until the calculated $V_{0}(3)$ equals the quoted price of the 3-year zero, $P_{0}(3)=0.9286$ . Now our interest rate lattice is consistent with the observed term structure of interest rates $(1.5\%$ , $2\%$ , . . . ) and forward volatilities $20\%$ , $19\%$ , . . . ) of Table 41.1. The resulting ‘arbitrage free’ lattice is shown in Table 41.2.  

It is now straightforward to extend the lattice beyond $t=3$ given spot rates and volatilities for 4-year, 5-year etc. zero coupon bonds. To obtain our no-arbitrage one-period lattice we have undertaken a sequence of separate ‘backward recursions’ to price each of the 1-year, 2-year etc. bonds and this is computationally intensive. However, it is possible to use a ‘forward recursion’ which requires just one ‘sweep’ through the lattice and is computationally easier (see Clewlow and Strickland 1998, Chapter 5).  

TABLE 41.2 Short-term interest rate lattice   


<html><body><table><tr><td>Number of ups</td><td colspan="4"></td></tr><tr><td>4</td><td></td><td></td><td>0.0744</td><td>0.1043</td></tr><tr><td>3</td><td></td><td>0.0496</td><td>0.0519</td><td>0.0742</td></tr><tr><td>2</td><td>0.0300</td><td>0.0340</td><td>0.0362</td><td>0.0528</td></tr><tr><td>1 0</td><td>0.0150</td><td>0.0201</td><td>0.0253</td><td>0.0376</td></tr><tr><td> Time</td><td>０</td><td>1</td><td>0.0232 2</td><td>0.0268 4</td></tr></table></body></html>  

# 41.2 PRICING A COUPON BOND  

Consider using the no-arbitrage interest rate lattice of Table 41.2, to price a 5-year, $4\%$ coupon bond, with face value $\$100$ .  

The known payof at $T=5$ is the fnal coupon of $\$4$ plus the principal of $\$100$ , making a total of $\$104$ at all nodes at $T=5$ (Table 41.3). To price the coupon bond we now simply work backwards through the lattice, discounting using the one-period rates in Table 41.2. For example, the price of the bond at node-(4,4) is:  

$$
V_{4,4}={\frac{(1/2)~\S104+(1/2)~\S104}{(1+0.1043)}}=\S94.18
$$  

Working our way backwards through the lattice fnally gives the current value of the 5-year coupon bond as $P_{0,0}(T=4)=102.62$ (per $\$100$ face value).2  

# 41.3 PRICING OPTIONS  

We can price interest rate derivatives such as European and American options on T-bonds, on T-bond futures, and options on Eurodollar futures using the no-arbitrage interest rate lattice (Table 41.2). Suppose the value of the underlying asset, at expiration of the option contract,  

TABLE 41.3 Pricing a $4\%$ , 5-year bond, $\$100$ principal   


<html><body><table><tr><td colspan="6">Coupon rate = 0.04, Coupon payment = 4</td></tr><tr><td>Number of ups 5</td><td colspan="5">104</td></tr><tr><td>4</td><td colspan="4"></td><td>94.18 104</td></tr><tr><td>3</td><td colspan="2"></td><td>96.61</td><td>100.81</td><td>104</td></tr><tr><td>2</td><td></td><td>98.02</td><td>100.77</td><td>102.78</td><td>104</td></tr><tr><td>1</td><td>101.57</td><td></td><td>102.97</td><td>103.89 104.23</td><td>104</td></tr><tr><td>0</td><td>102.62</td><td>106.75</td><td>106.65</td><td>106.18</td><td>105.29 104</td></tr><tr><td>Time</td><td></td><td>1</td><td>2</td><td>3 4</td><td>５</td></tr></table></body></html>  

$T$ is $Z_{i}$ (for all nodes-i at $T$ ). For example, the payofs to a call option are $V_{i}=\operatorname*{max}(Z_{i}-K,0)$ , where $i=u u,u d,d d$ for expiration at $T=2$ .  

For a European option on a T-bond, $Z_{i}$ are the T-bond prices in the lattice at maturity of the option contract. For an option on a bond future or on Eurodollar futures, $Z_{i}$ are the futures prices at $T$ . Having obtained the option payofs at $T$ , we then work backwards through the interest rate lattice, using $q=1/2$ and discounting at the appropriate one-period rates in Table 41.2, to obtain the option value at $t=0$ . Some examples will make this clear.  

# 41.3.1 European Call Option on a Bond  

Consider pricing a 4-year European call option $\begin{array}{r}{'{K}=\$104,}\end{array}$ on the 5-year coupon paying bond (in Table 41.3). The option expires at $T=4$ and the value of the coupon paying bond at each of the nodes at $t=4$ is given in Table 41.3. The call payof at each node at $T=4$ , is:  

which gives payofs $\{0,0,0,0.2299,1.2882\}$ which is given in Table 41.4.  

The value of the call at node (3,0), say, using the one-period interest rates (in Table 41.2) to discount the outcomes is:  

$$
V_{3,0}={\frac{(1/2)\ 0.2299+(^{1}/_{2})1.2882}{1+0.0253}}=\S0.7403
$$  

The other nodes are calculated in a similar fashion and we fnd that the value of the 4-year European call option (on a 5-year bond) with strike price $K=\$104$ , is $V_{\mathrm{0,0}}=0.1262$ (per $\$100$ maturity/principal value of the bond).  

TABLE 41.4 European call option $\cdot T=4)$ on 5-year bond   


<html><body><table><tr><td colspan="5">Strike rate = 104</td></tr><tr><td>Number of ups</td><td colspan="5"></td></tr><tr><td>4</td><td colspan="5">0</td></tr><tr><td>3</td><td colspan="5">0 0</td></tr><tr><td>2</td><td colspan="5">0 0</td></tr><tr><td>1</td><td></td><td>0.0260</td><td>0.0536</td><td>0.1109</td><td>0.2299</td></tr><tr><td>0</td><td>0.1262</td><td>0.2302</td><td>0.4160</td><td>0.7403</td><td>1.2882</td></tr><tr><td>Time</td><td>0</td><td>1</td><td>２</td><td>3</td><td>4</td></tr></table></body></html>  

# 41.3.2 American Call Option on a Bond  

To price an American call option on the bond, we merely have to compare the intrinsic value of the option $I V_{t,i}=P_{t,i}^{B}-K$ at each node with the recursive call premium $V_{t,i}$ in Table 41.4. If $I V_{t,i}>V_{t,i}$ then early exercise is proftable and the entry $V_{t,i}$ is replaced by $(P_{i}^{B}-K)$ . For example, at node-(3,0) the recursive value of the call is $V_{3,0}=\$0.7403$ (Table 41.4) while the intrinsic value $P_{3,0}^{B}-K=106.18-104=2.18$ (using Tabl,e 41.3). Therefore at node-(3,0) we ‘replace’ 0.7403 by the intrinsic value 2.18, which is the entry in square brackets in Table 41.5.  

At node (3,1) the intrinsic value (using Table 41.3) is $P_{3,1}^{B}-K=-0.11$ and therefore a call value of 0.1109 is used at this node (Table 41.5). Our ‘new’ recursive call value at node-(2,0) discounted using $r_{2,0}=0.0232$ (Table 41.2) is $V_{2,0}=1.1188=[(1/2)2.18+$ $(1/2)\ 0.1109]/(1+0.0232)$ (Tabl,e 41.5). But at node-(2,0) the intrinsic value is $I V_{2,0}=$ $(P_{2,0}^{B}-K)=106.65-104=2.65$ , which therefore ‘replaces’ the recursive value $V_{2,0}=1.1188$ in ,Table 41.5. The value of the American call option on the bond is found to be $V_{0,0}^{A m}=1.3653$ (Table 41.5), which of course must be at least as large as the price of the European, call on the bond of $V_{0,0}^{E u r}=0.1262$ (Table 41.4).  

Strike rate $=104$  

TABLE 41.5 American call option ( $\left(T=4\right)$ on 5-year bond   
Call premiums are per $\$100$ notional   


<html><body><table><tr><td>Number of ups</td><td colspan="5"></td></tr><tr><td>4 3</td><td colspan="4"></td><td>0 0</td></tr><tr><td>2</td><td colspan="4">0 0</td><td>0</td></tr><tr><td>1</td><td>0.0260</td><td>0.0536</td><td>0.1109</td><td></td><td>0.2299</td></tr><tr><td></td><td></td><td>[0.0]</td><td>[0.0]</td><td>[0.0]</td><td></td></tr><tr><td rowspan="3">0</td><td>1.3653</td><td>1.3255</td><td>1.1188</td><td>0.7403</td><td>1.2882</td></tr><tr><td>[0.0]</td><td>[2.75]</td><td>[2.65]</td><td>[2.18]</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Time</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td></tr></table></body></html>  

Note:  

(i) The payoff at ${\cal T}=4$ is $\mathsf{m a x}\{P_{i}^{B}-K,0\}$ and is the same for a European or American call.  

(ii) At each node we calculate the recursive value $V_{i}=[0.5V_{u}+0.5V_{d}]/(1+r_{i})$ and the intrinsic value $I V_{i}=\mathsf{m a x}\{P_{i}^{B}-K,0\}$ . The intrinsic value is given in parentheses [.]. For all four nodes at ${T=3}$ if $I V_{i}>V_{i}$ then we ‘replace’ $V_{i}$ with $I V_{j}$ in the lattice. We then calculate $V_{j}$ for nodes at ${\bar{T}}=2$ using the larger of $V_{j}$ and $I V_{\{\prime\}}$ etc.  

# 41.4 PRICING A CALLABLE BOND  

A callable bond is one where the issuer (e.g. company-X) can repurchase the bond at a fxed price at certain times over the life of the bond. We assume a ( $4\%$ -coupon) 5-year bond with maturity (par) value $\$100$ , can be ‘called’ in any of the years 1 to 4. Therefore company-X has a long call option on the bond, since it has the ‘option’ to recall it by paying the par value of the bond (if this turns out to be advantageous). However, if you are an investor (Ms Long) who holds a callable bond then this is equivalent to holding a conventional bond plus a written (embedded) American call option on the bond.  

Assume that if company-X decides to call the bond then it pays the maturity (par) value of the bond $\begin{array}{r}{\mathbf{\tilde{\psi}}_{M}=\$100\$ plus any coupon $c$ accruing to Ms Long. Assume the strike price in the call option equals the par value of the bond $\mathbf{\nabla}\cdot\mathbf{K}=M\mathbf{\nabla},$ , hence:  

Value of conventional bond $+$ Value of written call $\mathbf{\tau}=$ Value of callable bond  

In general, company-X will ‘call’ (i.e. buy back) the bond if the yield to maturity falls below the coupon yield $(=C/M)$ . (Company-X can then refnance its debt by selling ‘new’ bonds at the lower current yield to maturity). Assume that the bond is called if the current market value of the bond is higher than its maturity value $M$ (plus any coupon due), hence in the binomial lattice:  

Bond is called by company-X if: $V_{i}^{B}(r e c u r s i\nu e)>M+C$ Then replace $V_{i}^{B}$ recursive with $M+C$ in the lattice.  

The payofs in the lattice are discounted at the appropriate short-rate and we work backwards through the lattice, checking the above ‘call provision’ at each node.  

At maturity of the bond $(t=5)$ the value of the bond is $M+C=\$104$ in all states. The bond can be called at $T=4$ . At nodes (4,0) and (4,1) the bond prices are $V^{B}(r e c u r s i\nu e)=$ 105.29 and 104.23 (Table 41.3 $)>K=M+C=104$ , so at these nodes the bond will be ‘called’ by company-X. Hence the value of the callable bond to Ms Long at these two nodes is 104 (Table 41.6).  

At nodes-(4,2), (4,3), and (4,4) in Table 41.3, $V^{B}(r e c u r s i\nu e)<K=104$ and therefore in Table 41.6 these entries remain unchanged and equal to $V^{B}$ recursive . On the other hand, at node-(3,0) in Table 41.6, $V_{3,0}^{B}(r e c u r s i v e)=[(1/2)104+(1/2)104]/1.0253+4=105.43>K=$ 104, so the bond would be called and the entry in Table 41.6 is 104.  

So, the bond is called at nodes (1,0), (2,0), (3,0), (4,0), and (4,1) and at these nodes we have entries of 104. Working backwards through the lattice we fnd at $V_{0,0,}^{B}(c a l l a b l e)=$ 101.25. In addition, we have found that for a plain vanilla $4\%$ -coupon, 5-year bond, $V_{0,0}^{B}(c o n v e n t i o n a l)=102.62\$ (Table 41.3) and a long (American) call on this bond $=1.3653$ (Table 41.5) hence, the following relationship holds:  

Value of a conventional bond $^+$ Value of a written call Value of a callable bond  

$$
102.62+(-1.3653)=101.25\mathrm{(round}
$$  

TABLE 41.6 Pricing a 5-year callable bond   


<html><body><table><tr><td colspan="6">Coupon rate = 0.04 Coupon payment = 4</td></tr><tr><td>Number of ups ５</td><td colspan="5">104</td></tr><tr><td>4</td><td colspan="4"></td><td>98.18 104</td></tr><tr><td>3</td><td colspan="4">96.61</td><td>100.81 104</td></tr><tr><td>2</td><td></td><td>98.02</td><td>100.77</td><td>102.78</td><td>104</td></tr><tr><td>1</td><td>101.55</td><td>102.92</td><td>103.78</td><td>104</td><td>104</td></tr><tr><td>0</td><td>101.25 104</td><td>104</td><td>104</td><td>104</td><td>104</td></tr><tr><td>Time</td><td>0</td><td>2</td><td>3</td><td>4</td><td>５</td></tr></table></body></html>

Note: Bond can only be called in years 1 to 4.  

It is also the case that the above relationship holds at all nodes across the three lattices of Table 41.3 (conventional bond), Table 41.5 (American call) and Table 41.6 (callable bond) and not just at node (0,0).  

# 41.5 PRICING CAPS  

# 41.5.1 Pricing a 2-year European Cap  

To price a cap we frst price the individual caplets. Consider a one-period $T=1{\dot{}}$ caplet per $\$1$ of notional principal. Assume the cap payofs are determined at $t_{1}$ but paid out at $t_{2}$ . Hence, with a strike rate of $K=2\%$ the payofs to the caplet at $t_{1}$ using short-rates in Figure 41.1 (or Table 41.2) are:  

$$
V_{u}={\frac{m a x\{0,~r_{u}-K\}}{[1+r_{u}]}}={\frac{0.03-0.02}{1.03}}=0.009709
$$  

$$
V_{d}={\frac{m a x\{0,~r_{d}-K\}}{[1+r_{d}]}}={\frac{0.0201-0.02}{1.0201}}=0.000098
$$  

Using backward recursion:  

$$
{\mathrm{\boldmath~\Gamma~}}_{\mathrm{{\tiny~0}}}={\frac{q V_{u}+(1-q)V_{d}}{[1+r(0,1)]}}={\frac{(1/2){\mathrm{\tiny~0.009709+}}\left({\frac{1}{2}}\right){\mathrm{\tiny~0.000098}}}{1.015}}=0.004831~({\mathrm{per~\xi\gg1~\mathrm{\tiny~1~.}}})
$$  

The 1-year caplet premium is 0.004831 (per $\$1$ notional) – about $0.48\%$ of the principal. If the principal underlying the caplet is $Q=\$100,000$ then the invoice price of the (one-year)  

caplet is $\$483.10$ . Pricing a two-period caplet (where cash payment takes place at $t_{3}$ ) is straightforward once we know $V_{u u},V_{u d}$ , and $V_{d d}$ , which are given by:  

$$
V_{i}=\frac{m a x\{0,~r_{i}-K\}}{[1+r_{i}]}
$$  

where $i=^{\circ}u u^{\prime}$ or ‘ud’ or $\cdot_{d d},$ for each of the three nodes at $t_{2}$ (Figure 41.1). The three payofs at $t_{2}$ for $K=2\%$ are given by $m a x\{0,r_{i}-K\}=\{2.96\%,1.4\%0.32\%\}$ with $V_{i}=\{0.0282\$ 0.0135 0.0031 respectively. We then work backwards to obtain:  

$$
V_{u}=\frac{\left[q V_{u u}+(1-q)V_{u d}\right]}{\left[1+r_{u}\right]}=\frac{\left[\left(\frac{1}{2}\right)0.0282+\left(\frac{1}{2}\right)0.0135\right]}{1.03}=0.0203
$$  

$$
V_{d}=\frac{[q V_{u d}+(1-q)V_{d d}]}{[1+r_{d}]}=\frac{\left[\left(\frac{1}{2}\right)\ 0.0135+\left(\frac{1}{2}\right)0.0031\right]}{1.0201}=0.0082
$$  

and the two-period caplet premium is:  

$$
\begin{array}{l}{\displaystyle{\mathit{\check{r}}_{\mathrm{0}}=\frac{[q V_{u}+(1-q)V_{d}]}{[1+r_{\mathrm{0}}]}=\frac{\left[\left(\frac{1}{2}\right)0.0203+\left(\frac{1}{2}\right)0.0082\right]}{1.015}=0.01404\mathrm{(per\81\notion)}.}}\end{array}
$$  

Notice that although the above expressions look relatively complex, the premium $V_{0}$ for a two-period caplet, just depends on $a l l$ the one-period rates in the lattice up to $T=2$ . The price of the one-period and two-period caplets are 0.004831 and 0.01404. So the price of a cap (per $\$1$ notional) with caplets expiring at $T=1$ and $T=2$ is 0.01887 $(=0.004831+0.01404)$ . Pricing a European foorlet proceeds as above but the payofs at each node-i are $m a x\{0,K-r_{i}\}/(1+r_{i})$ .  

# 41.5.2 Pricing an American Caplet  

Suppose we are trying to price a 4-year American caplet. Again, we work backwards through the lattice. At all nodes at $t_{3}$ we calculate the ‘recursive value’ $V_{t,i}$ using Equation (41.2) and also the intrinsic values $I V_{t,i}=(r_{t,i}-K)/(1+r_{t,i})$ and at each node we use $\operatorname*{max}\{V_{t,i},I V_{t,i}\}$ . We then repeat the above procedure for the nodes at $t_{2}$ , working backwards through the lattice at $t_{1}$ and $t_{0}$ (since it may be worthwhile to exercise immediately). The lattice entry at $t_{0}$ is then the value of the American caplet.  

# 41.6 PRICING FRAS  

The payof in an FRA is based on the diference between the out-turn value for the interest rate $r_{i}$ at the maturity date $T$ and the agreed FRA rate, $r_{F R A}$ .  

In the BOPM the probability of $k$ ‘up’ moves after $n$ -time periods is given by the binomial probabilities $q_{k}^{n}={\binom{n}{k}}\mathrm{q^{k}(1-q)^{n-k}}$ . For example, for $q=0.5$ , the risk neutral probability of reaching node-ud, that is $k=1$ , ‘ups’ after $n=2$ steps is $q_{u d}^{2}=0.5~[=(2!/1!1!)$ (0.5)(0.5)]. Similarly $q_{u u}^{2}=0.25$ and $q_{d d}^{2}=0.25$ .  

Assume the FRA is on a notional principal of $\$1$ with maturity $T=2$ years. The payof is $(r_{i}-r_{F R A})$ , which we assume is paid out at $T=2$ . The fair ‘price’ for the FRA is that value of $r_{F R A}$ which makes the expected value of the payof from the FRA (in a risk-neutral world) equal to zero, when viewed from $t_{0}$ . Using the short-term rates in Figure 41.1 (or Table 41.2) we have:  

Expected payoff: $1\times2$ FRA  

$$
\begin{array}{c}{{q_{u u}^{n}(r_{u u}-r_{F R A})+q_{u d}^{n}(r_{u d}-r_{F R A})+q_{d d}^{n}(r_{d d}-r_{F R A})=0}}\\ {{0.25(4.96\%-r_{F R A})+0.5(3.4\%-r_{F R A})+0.25(2.32\%-r_{F R A})=0}}\end{array}
$$  

The sum of the risk-neutral probabilities is unity and the solution is:  

$$
r_{F R A}=\sum_{i}q_{i}^{n}~r_{i}=3.52\%
$$  

where for $n=2$ , $i=u u$ , ud, dd  

Therefore the FRA-rate $r_{F R A}$ equals the expected value (using risk neutral probabilities) of the one-period (forward) rates, at expiration of the FRA contract.  

# 41.6.1 Delayed Settlement FRA  

The payof to the FRA is determined at $T=2$ . But here, because interest is paid in arrears, the payment of the interest diferential is due at $t_{3}$ (i.e. ‘delayed settlement FRA’). The present value of this payment at $t=2$ , must equal zero, hence:  

$$
\frac{q_{u u}^{n}(r_{u u}-r_{F R A})}{(1+r_{u u})}+\frac{q_{u d}^{n}(r_{u d}-r_{F R A})}{(1+r_{u d})}+\frac{q_{d d}^{n}(r_{d d}-r_{F R A})}{(1+r_{d d})}=0
$$  

The solution for the delayed settlement $r_{F R A}$ , using the short-rates in Table 41.2 at $t=2$ is:  

$$
r_{F R A}^{d e l a y}=\frac{\sum_{i}q_{i}^{n}~r_{i}~/~\left(1+r_{i}\right)}{\sum_{i}q_{i}^{n}/~\left(1+r_{i}\right)}=0.0351~(o r~3.51\%)
$$  

where for $n=2$ , $i=u u$ , ud, dd. Clearly one could easily extend the above to price FRAs with a maturity longer than $T=2$ .  

# 41.7 PRICING A SWAPTION  

Consider an option on a swap with expiration at $T=2$ , which delivers a ‘pay-fxed, receive-foating’ swap, at a swap rate $K_{s p}$ . Assume the maturity of the deliverable swap is $N=2$ years, that is the life of deliverable swap begins at $T=2$ (at expiration of the swaption) and ends at $t=4$ ). This is a payer swaption. How can we price this swaption at $t=0?$ The key element is to obtain the value of the payofs on the swaption $\{V_{u u},V_{u d},V_{d d}\}$ for the 3 nodes at $T=2$ . Then all we need to do is apply backward recursion under RNV. The steps are given below.  

# 41.7.1 Stage 1: Calculate Swap Rates  

At each of the three nodes $(i=u u,u d,d d)$ at $T=2$ , calculate the (forward) swap rate ${\boldsymbol{s p}}_{i}$ ( $\left\langle T=2\right\rangle$ that would prevail on a 2-year swap, given the term structure at that node of the lattice (Figure 41.1). $s p_{i}(T=2)$ is a forward swap rate because it applies to the underlying swap in the swaption, which ‘begins’ at maturity of the option. The (forward) swap rate at $T=2$ is calculated so the present value (PV) of the foating leg of the swap equals the PV of the fxed leg. If the notional principal in the swap is $\$2$ then the value of the foating leg (at $T=2{\dot{}}$ ) is $\$2$ (see Chapter 34). The fxed leg of the deliverable 2-year swap has cash fows at $t=3$ and $t=4$ . Equating present values of the foating and fxed legs, we can solve for the unknown (forward) swap rate ${\boldsymbol{s p}}_{i}$ at each of the three nodes ( $\overset{\cdot}{i}=u\overset{\cdot}{u}$ , ud, and $d d$ ) at $T=2$ :  

$$
Q=\frac{s p_{i}Q}{[1+r_{i}(2,3)]}+\frac{Q(1+s p_{i})}{[1+r_{i}(2,4)]^{2}}
$$  

Note that at node-uu (say) $r_{u u}=r_{u u}(2,3)$ is the one-period rate but $r_{u u}(2,4)$ is a $^{\cdot_{2}}$ -year’ rate, which can be calculated from the one-period rates in Figure 41.1. At each of the three nodes $\overset{\cdot}{\iota}=u\boldsymbol{u}$ , ud, nd dd) at $T=2$ :  

$$
s p_{i}(T=2)=\left[1-{\frac{1}{[1+r_{i}(2,4)]^{2}}}\right]\ A N_{2-4}
$$  

where $\begin{array}{r}{A N_{i}^{2-4}=\left[\frac{1}{[1+r_{i}(2,3)]}+\frac{1}{[1+r_{i}(2,4)]^{2}}\right]}\end{array}$  

$A N_{i}^{2-4}$ is the annuity value of $\$1$ paid at $t=3$ and $t=4$ (over the life of the underlying 2-year swap). We now have three values for the (forward) swap rate at $T=2$ , namely $s p_{u u}$ , $s p_{u d}$ , and $s p_{d d}$ .  

# 41.7.2 Stage 2: Calculate Swaption Payoffs  

The payofs on the swaption (Chapter 39) per $\$1$ notional principal on the underlying swap at each node $\overset{\cdot}{i}=u\overset{\cdot}{u}$ , ud, dd) at $T=2$ , depends on the 2-year annuity value of $\operatorname*{max}\{s p_{i}-K_{s p},0\}$ (Chapter 39):  

$$
V_{i}=\operatorname*{max}\{s p_{i}-K_{s p},0\}\ A N_{i}^{2-4}\quad\mathrm{(i=uu,ud,dd)}
$$  

We now have values $V_{u u}$ , $V_{u d}$ and $V_{d d}$ for the swaption, at expiration $T=2,$ . Note that the $V_{i}$ depend only on $r_{i}(2,3),r_{i}(2,4)$ , that is, on the term structure from $t=2$ to the maturity date of the underlying cash-market swap at $t=4$ . This is fne because at each node-i, we know that we can construct the whole term structure from the one-period rates in the lattice.  

# 41.7.3 Stage 3: Backward Recursion  

It is now straightforward to price the swaption using backward recursion, discounting using the one-period rates (Figure 41.1). Given $V_{i}$ $\ {i=u u,u d,d d})$ we use the usual formulas to calculate $V_{u}$ $V_{d}$ and then $V_{0}$ . If the swaption premium $V_{0}=0.0140$ (per $\$1$ notional principal) then for a deliverable swap with notional principal of $\$100$ , the invoice price of the swaption is $\$140,000$ .  

Notice that when we price a caplet using the BOPM, we only require the sequence of one-period rates in the lattice (Figure 41.1). But to price a swaption, on a 2-year underlying swap we require the term structure at each node, since we need both the one-period rates $r_{i}(2,3)$ and the two-period rate $r_{i}(2,4)$ . This is because the underlying cash market swap has cash fows over several periods after expiration of the option (at $T=2$ ).  

# 41.8 PRICING FRNS WITH EMBEDDED OPTIONS  

A plain vanilla FRN is a bond with variable coupon payments that depends on a foating interest rate (LIBOR, fat). A plain vanilla FRN with maturity (par) value of $Q=\$100$ has a market price equal to its par value when initially issued $\mathit{\Omega}_{t}=0\mathit{\Omega}_{,}$ and its market value reverts to par at each reset date (see Chapter 34). The value of an FRN at each reset date is $Q$ if the foating rate in the FRN is LIBOR (fat) but not if the foating rate is LIBOR plus a spread. We assume the reset dates for the FRN correspond to the nodes in the short-rate lattice. The payof on an FRN is determined at each reset date, but cash is paid in arrears.  

# 41.8.1 Capped FRN  

Suppose we are considering a 5-year FRN, par value $Q=\$100$ , which has a capped foating rate at $K_{c a p}=6\%$ . At any reset date, if the LIBOR rate is above $K_{c a p}$ the investor holding the  

FRN only receives $K_{c a p}=6\%$ , rather than the higher LIBOR rate. Hence the market value of the FRN will be below its $\$100$ par value (at this node). A capped FRN is equivalent to a plain vanilla FRN plus an embedded written (short) cap.  

Payof capped $\mathrm{FRN}=1$ Payof vanilla $\mathrm{FRN}+$ written cap (with strike $K_{c a p}$ )  

$$
\begin{array}{r l}&{=L I B O R-\operatorname*{max}\{L I B O R-K_{c a p},0\}}\\ &{=K_{c a p}\qquad\mathrm{if}L I B O R>K_{c a p}}\\ &{=L I B O R\quad\mathrm{if}L I B O R\leq K_{c a p}}\end{array}
$$  

At maturity $\dot{T}=5\dot{,}$ the FRN is worth $\$100$ , its par value, at all nodes. Now consider each fve nodes-i for a capped FRN at $t=4$ (Table 41.7):  

If $r_{i}>K_{c a p}$ ∶ Coupon received (one period later) $=\S100K_{c a p}$  

$$
V_{i}^{C a p F R N}=\S100(1+K_{c a p})/(1+r_{i})
$$  

If $r_{i}<K_{c a p}$ Coupon received one period later $\mathbf{\Psi}_{|}=\$100\ r_{i}$  

$$
V_{i}^{C a p F R N}=\S100(1+r_{i})/(1+r_{i})=\S100
$$  

At node-(4,4) $r_{i}=10.43\%$ (Table 41.2) which is greater than $K_{c a p}=6\%$ , hence $V_{i}^{C a p F R N}=$ $100(1+K_{c a p})/(1+r_{i})=95.99$ (Table 41.7). Similarly at node-(4,3) $r_{i}>K_{c a p}$ and $V_{i}^{C a p F R N}=$ 98.67. The nodes (4,0), (4,1), (4,2) all have $r_{i}<6\%$ (Table 41.2) and the value of the FRN is $\$100$ . At nodes $t=3$ we calculate the ‘recurs v<e’ v%alue of the FRN: $V_{3,i}^{r e c u r s i\nu e}=[(1/2)V_{4,i+1}+$ $(1/2)V_{4,i}]/(1+r_{3,i})$ , which excludes any coupon payments. We now see, if the cap is operative at this node:  

$$
\mathrm{At}\ t=3,\mathrm{if}\ r_{i}>K_{c a p}\colon{\cal V}_{3,i}^{C a p F R N}={\cal V}_{3,i}^{r e c u r s i v e}+\S100K/(1+r_{i})
$$  

TABLE 41.7 Pricing a 5-year capped FRN   


<html><body><table><tr><td colspan="6">Cap rate, K = 0.06</td></tr><tr><td>Number of ups</td><td colspan="4"></td></tr><tr><td>４</td><td colspan="4">95.99</td></tr><tr><td>3</td><td colspan="3">96.18</td><td>98.67</td></tr><tr><td>2</td><td></td><td>97.88</td><td>99.37</td><td>100</td></tr><tr><td>1</td><td>98.82</td><td>99.70</td><td>100</td><td>100</td></tr><tr><td>0</td><td>99.35</td><td>99.85 100</td><td>100</td><td>100</td></tr><tr><td>Time</td><td>0</td><td>1</td><td>２ 3</td><td>4</td></tr></table></body></html>  

For example, at node-(3,3), $r_{3,3}=7.44>K_{c a p}=6\%$ hence (Table 41.7):  

$$
V_{3,3}^{C a p-F R N}={\frac{(1/2)~95.99+(1/2)~98.67}{1.0744}}+{\frac{6}{1.0744}}=96.18
$$  

At node-(3,2), $r_{3,2}=5.19<K_{c a p}=6\%$ , hence (Table 41.7):  

$$
V_{3,2}^{C a p-F R N}={\frac{(1/2)98.67+(1/2)100}{1.0519}}+{\frac{5.19}{1.0519}}=99.37
$$  

We go backwards through the lattice to obtain the value of the capped FRN at $t=0$ of 99.35. The embedded (long) cap must therefore be worth $100-99.35=0.65$ .  

# 41.8.2 Floored FRN  

Using a similar procedure we can price an FRN with an embedded foor, $K_{F L}=3\%$ . If at $t=4$ , $r_{i}<K_{F L}$ then the holder of the FRN will receive the ‘foor payment’ of $(\$100~K_{F L})$ and the FRN will be valued above par at $V_{i}=\S100(1+K_{F L})/(1+r_{i})\cdot$ – this occurs at nodes (1,0), (1,1), (2,0), (3,0), and (4,0) in Table 41.2 and hence at th퐹e퐿se nodes in Table 41.8, $V^{F L-F R N}$ is above its par value.  

If $r_{i}>K_{F L}$ then the foored-FRN pays a coupon based on the LIBOR rate $=\mathbb{S}100(1+r_{i})$ and the FRN is valued at par (Table 41.8). Moving backwards through the lattice, the value of a foored FRN (at $t=0$ ) is 102.19, hence the value of the embedded put is:  

Value of embedded long put $\c=$ Value of foored FRN Value of vanilla FRN  

$$
2.19=102.19-100
$$  

From Equation (41.16), a ‘foored FRN’ with foor level $K_{F L}$ is equivalent to a plain vanilla FRN (on LIBOR) with an embedded long put option on LIBOR, with strike equal to K .  

TABLE 41.8 Pricing a 5-year foored FRN   


<html><body><table><tr><td colspan="5">Floor rate = 0.03</td></tr><tr><td>Number of ups</td><td colspan="4"></td></tr><tr><td>4</td><td colspan="4">100</td></tr><tr><td>3</td><td colspan="3">100</td><td>100</td></tr><tr><td>2</td><td></td><td>100</td><td>100</td><td>100</td></tr><tr><td>1</td><td>100.0007</td><td>100</td><td>100</td><td>100</td></tr><tr><td>0</td><td>102.19 101.44</td><td>100.96</td><td>100.62</td><td>100.31</td></tr><tr><td>Time</td><td>0</td><td>1</td><td>2 3</td><td>4</td></tr></table></body></html>  

TABLE 41.9 Pricing a 5-year collared FRN   


<html><body><table><tr><td colspan="2">Cap rate = 0.06 Floor rate = 0.03</td><td colspan="3"></td></tr><tr><td>Number of ups 4</td><td colspan="3"></td><td>95.99</td></tr><tr><td>3</td><td colspan="3">96.18</td><td>98.67</td></tr><tr><td>2</td><td></td><td>97.88</td><td>99.37</td><td>100</td></tr><tr><td>1</td><td>98.82</td><td>99.70</td><td>100</td><td>100</td></tr><tr><td>0</td><td>101.54 101.29</td><td>100.96</td><td>100.62</td><td>100.31</td></tr><tr><td>Time</td><td>0</td><td>1 2</td><td>3</td><td>4</td></tr></table></body></html>  

# 41.8.3 Collared FRN  

Table 41.9 shows the values of a collared FRN with cap of $6\%$ and foor of $3\%$ . The entries at each node are either the par values of the vanilla FRN (when neither the cap nor foor are operative at this node) or the value of the capped FRN or the foored FRN (when these are operative). Working backwards through the lattice the collared-FRN is worth 101.54 at $t=0$ .  

Hence we can see that:  

Value of collared $F R N={}^{\cdot}$ Value of vanilla $F R N+V a$ lue of short call $^+$ Value of long put  

$$
101.54=100+(-0.65)+2.19
$$  

This completes our set of examples where we use the arbitrage-free short-rate lattice and the BOPM under RNV to price fxed income derivatives. The method is very fexible and can handle a wide variety of path-dependent interest rate options.  

# 41.9 MORE LATTICES  

Short-rates in the BDT model do not exhibit mean reversion, so if interest rates are very high (low) there is no tendency for them to return towards some long-run mean value. Use of a trinomial lattice rather than a binomial lattice can speed up computational time and can also make it easier to incorporate mean reversion in interest rates. (In addition, using a trinomial lattice can be shown to be equivalent to the fnite diference method (see Chapter 48)).  

A trinomial lattice for $t=2$ periods and with each period equal to 1 year is shown in Figure 41.3. The (continuously compounded) short-rate is given at each node and the probabilities of an ‘up’, ‘fat’ and ‘down’ move are assumed to be $q_{i}=(0.25,0.50,0.25)$ respectively. Broadly speaking, these probabilities are chosen so that the lattice exhibits mean reversion and it matches the ‘real world’ variance of the short-rate.  

![](acdd5340928460be4dfbec27be3ed8ff4929baedbd659c9323bdd0e97d4897f9.jpg)  
FIGURE 41.3 Trinomial-rate lattice  

The trinomial lattice is used in exactly the same way as the binomial lattice. Consider pricing a 2-year European caplet (on 1-year LIBOR) with notional principal $Q=\$10$ and $K=4\%$ . For simplicity assume the cash payouts actually occur at $t=2$ .3 The cash payouts at the fve nodes at $t=2$ are $V_{2,i}=\operatorname*{max}(r_{2,i}-K,0)$ and are shown in parentheses in Figure 41.3. The value of the caplet at node B is:  

$$
V_{B}=\S1\mathrm{m}[0.25(0.02)+0.50(0.01)+0.25(0.0)]\mathrm{e}^{-0.05(1)}=\S9,512\mathrm{m}
$$  

We can calculate $V_{C}$ and $V_{D}$ in a similar fashion and then use these values to determine $V_{A}$ , the premium for the caplet. Hull and White (1994) demonstrate how the trinomial lattice can be ‘adjusted’ so that it incorporates the empirically observed phenomenon of mean reversion for interest rates. For example, if interest rates follow the upper path A, B, E in Figure 41.3, then with mean reversion it would be more likely that the one-period rate would fall next period (towards its long-run mean value). This is accomplished in the lattice by increasing $q_{3}$ (the probability of a ‘down’ move) from 0.25 at node E (see Hull 2018 for more details). The Hull-White lattice also allows hedge parameters to be calculated so that options traders can establish vega, gamma, and delta neutral positions for their portfolios of interest rate options.4  

# 41.10 SUMMARY  

• The no-arbitrage approach begins with a model for the one-period short-rate $r_{t,i}$ , which is calibrated to ft the current term structure. That is the one-period rates are  

consistent with observed prices of zero-coupon bonds and the volatility of forward rates. The resulting lattice for one-period rates does not allow arbitrage profts to be made (by buying and selling zero-coupon bonds).   
• Bond prices and the price of many fxed income derivatives can then be found numerically, using the BOPM and backward recursion through the ‘no-arbitrage’ lattice.   
• The BOPM applied to the no-arbitrage short-rate lattice is very fexible and can be used to price both European and American bond options and many other path-dependent fxed income derivatives (e.g. caps, foors, swaptions, callable bonds, FRAs and FRNs with caps and foors).   
• Trinomial lattices increase computational speed. These lattices can also mimic mean reversion in short-rates, which more closely resembles their real world behaviour.  

# EXERCISES  

# Question 1  

Intuitively, explain how one-period interest rates in the no-arbitrage interest rate lattice of the BDT model are related to the term structure of volatility. Consider a two-period tree to illustrate your answer.  

# Data for Questions 2–5  

You are given the following data to be used in answering Questions 2–5. The interest rate lattice over three periods is:  

10%  

10%  

The risk-neutral probability of an ‘up’ move is $q=0.6$ and for a ‘down’ move is $(1-q)=0.4$ . The fgures in parentheses are the probability of reaching each node, times the number of ways to reach that node. They are therefore the BOPM terms:  

$$
q_{k}^{n}={\binom{n}{k}}q^{k}(1-q)^{n-k}
$$  

For $n=2$ , and $k=1$ up-moves, the probability of being at node ‘ud’ (or equivalently $\cdot_{d u^{\prime}}$ ) is:  

$$
q_{1}^{n}=q_{u d}^{n}={\binom{2}{1}}(0.6)^{1}(0.4)^{1}=0.48
$$  

Similarly the probability of $k=2$ up-moves (to reach node-uu) is:  

$$
q_{2}^{n}=q_{u u}^{n}={\binom{2}{2}}(0.6)^{2}(0.4)^{0}=0.36
$$  

# Question 2  

What is the invoice price of a 1-year European caplet with $K_{c}=10\%?$ The notional principal in the cap is $Q=\$10$ . Note that the payof for a 1-year caplet is determined at $t=1$ but the actual cash payout takes place at $t=2$ .  

# Question 3  

What is the invoice price of a 2-year European caplet with $K_{c}=10\%?$ The notional principa in the caplet is $Q=\$10$ . What is the invoice price of a 2-year cap (with annual payments)?  

# Question 4  

Qualitatively, explain how your analysis would change when pricing the 2-year cap, if the cap were an American style option.  

# Question 5  

Using the above lattice, what is the FRA-rate $r_{F R A}$ for a 2-year FRA where the cash payof is determined at $t=2$ but the actual payment is due at $t=32$ This is a ‘delayed settlement FRA’.  