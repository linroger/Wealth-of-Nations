# PRINCIPAL PROTECTION TECHNIQUES  

# 23  

# CHAPTER OUTLINE  

23.1 Introduction .. . 809   
3.2 The Classical Case... 810   
23.3 The CPPI . . 811   
3.4 Modeling the CPPI Dynamics 813   
23.4.1 Interpretation.. 814   
23.4.2 How to Pick λ . 815   
3.5 An Application: CPPI and Equity Tranches . 815   
23.5.1 A Numerical Example .. 816   
23.5.1.1 The initial position . 817   
23.5.1.2 Dynamic adjustments . 818   
23.5.1.3 Default and switching out of CPPI into zero-coupon bond.. 820   
3.6 Differences Between CPDO and CPPI ... .. 820   
23.7 A Variant: The DPPI. 821   
23.8 Application of CPPI in the Insurance Sector: ICPPI.. . 822   
3.9 Real-World Complications .. . 824   
23.9.1 The Gap Risk 824   
23.9.2 The Issue of Liquidity .. 824   
23.9.3 Which Principal Protection Technique is Best in Practice? . 825   
23.10 Conclusions.. 825   
Suggested Reading .. . 826   
Exercises . 826  

# 23.1 INTRODUCTION  

Investment products, where the principal is protected, have always been popular in financial markets. However, until recently the so-called guaranteed products sector has relied mainly on static principal protection which consists of a static portfolio of a default-free bond plus a basket of options. This is also sometimes referred to as option-based portfolio insurance (OBPI). However, recent advances in financial engineering techniques have made it possible to create guaranteed products and offer protection in other ways. As structurers understood dynamic replication better, they realized that dynamic replication could synthetically create options on risks where no traded options exist. This led to the creation of dynamic rebalancing techniques, the best known being the constant proportion portfolio insurance (CPPI). CPPI products on a variety of assets have been sold by banks, including equity indices and credit default swap indices. With the development of credit markets, CPPI was applied to credit indices and the implied tranches as well. As expertise on the dynamic replication techniques grew, market activity led to new innovations such as the dynamic proportion portfolio insurance (DPPI). The heyday of CPPI product development and innovation was during the years before the GFC, but CPPI applications continue to exist in various markets.  

A major reason for the popularity of the guaranteed product sector is regulatory behavior. Several countries do not let investment banks issue structured products involving “exotic” risks unless the product provides some principal protection guarantee. CPPI is a protected note and is not subject to these restrictions. In addition, many funds are not allowed, by law, to invest in securities that are speculative grade. Other dynamic proportion techniques are not principal protected, but both the principal and the coupon can be rated AAA by the main rating agencies, although they offer unusually high coupons. These make them attractive to conservative funds as well.1  

In this chapter, we discuss the classical static principal protection methodology followed by an introduction to the CPPI as an extension of this classical methodology. We show the dynamics of the portfolio value that applies this technique under some simple conditions and provide the results of some simulations as well. We then deal with the application of the methodology to standard credit index tranches and discuss the complications that may arise when this is implemented. Finally, we introduce some modeling aspects and discuss the so-called gap risk, and deal briefly with the DPPI.  

# 23.2 THE CLASSICAL CASE  

At the simplest level a guaranteed product consists of either a zero-coupon bond and a static call option position or protective put option position. The former was discussed in detail in Chapter 20. Both of these approaches date back to Leland (1980) and are nowadays referred to as option-based portfolio insurance (OBPI). The protective put option strategy consists of protecting a risky investment from downside market movements using a put option, while allowing participation in the growth of a risky asset. The put option could be either based on a traded index option such as options on the S&P500 index or a synthetic put option based on dynamic replication using index futures. One of the complications in such guaranteed products is that the options may be too expensive, depending on the level of volatility. Out-of-the-money put options, for example, are typically very expensive. In Chapter 20 we discussed several limitations of guaranteed products based on a combination of a zero-coupon bond and call option.  

These problems have led to several modifications of the traditional principal protection methods. Dynamically adjusted principal protection methods (versions of CPPI) and the dynamically adjusted methods that yield triple-A products have been developed as a result. We study the CPPI techniques first and discuss their application to standard credit tranches.  

In practice structurers and portfolio managers also use other principal protection techniques such as risk control, volatility capping, and risk budgeting, but since they are not based on financial engineering principles in a way that OBPI and CPPI are, we do not discuss them further in this book.2  

# 23.3 THE CPPI  

The main advantage of the CPPI as a principal protection technique is that it gives a higher participation in the underlying asset than one can get from traditional capital protection. It also can be applied when interest rates are “too” low, or when options do not trade for some underlying risk. Before we discuss the CPPI algorithm and the associated risks we consider some market examples.  

# EXAMPLE  

The CPPI investment is an alternative to standard tranche products, which offer limited upside (fixed premium) in exchange for unlimited downside (potential total loss of principal). CPPI offers limited downside (because of principal protection) and unlimited upside, but exposes investors to the market risk of the underlying default swaps contracts that comprise the coupon.  

With yields hovering near record lows until recently, credit investors are increasingly moving to structures that contain some element of market exposure. That has posed a problem for rating agencies, which are default oriented, and prompted a move to a more valuation-based approach for some products. Leveraged super senior tranches, also subject to market volatility, were the market risk product of choice last year, but in recent months have ceded popularity to CPPI.  

Banks profit from ratings on CPPI coupons because the regulatory capital treatment of rated products under Basel II is much kinder than on unrated holdings.  

The CPPI is a structure which has constant leverage. Dynamic PPI (proportion portfolio insurance) is the name for strategies where the leverage ratio changes during the investment period. CPPI works by dynamically moving the investment between a safe asset and a risky asset, depending on the performance of the risky asset and depending on how much cash one has in hand. The main criterion in doing this is to protect the principal, while at the same time getting the highest participation rate.  

The idea of CPPI can be related to the classical principal protection methods and is summarized as follows. In the classical principal protection, the investor buys a zero-coupon bond and invests the remaining funds to options. CPPI relaxes this with a clever modification. If the idea is to be long a bond with value 100 at $T.$ , then one can invest any carefully selected sum to the risky asset as long as one makes sure that the total value of the portfolio remains above the value of the zero-coupon bond during the investment period. Then, if the portfolio value is above the value of the zero-coupon bond, at any desired time the risky investment can be liquidated and the bond bought. This will still guarantee the protection of the principal, $N.$ This way, the structurer is not limited to investing just the leftover funds. Instead, the procedure makes possible an investment of funds of any size, as long as risk management and risk preference constraints are met.  

Let the initial investment of $N$ be the principal. The principal is also the initial net asset value of the positions—call it $V_{t_{0}}$ . Next, calculate the present value of $N$ to be received in $T$ years. Call this the floor, $\boldsymbol{F}_{t_{0}}$ .3  

$$
F_{t_{0}}=\frac{N}{\left(1+r_{t_{0}}\right)^{\mathrm{T}}}
$$  

Let the increment $C u_{t}$ be called the cushion:  

$$
C u_{t_{0}}=V_{t_{0}}-F_{t_{0}}
$$  

Then, select a leverage ratio $\lambda$ in general satisfying $1<\lambda.$ . This parameter has no time subscript and is constant during the life of the structured note. Using the $\lambda$ calculate the amount to be invested in the risky asset $R_{t_{0}}$ as:  

$$
R_{t_{0}}=\lambda\big[V_{t_{0}}-F_{t_{0}}\big]
$$  

This gives the initial exposure to the risky asset $S_{t}.$ . Invest $R_{t_{0}}$ in the risky asset and deposit the remaining $V_{t_{0}}-R_{t_{0}}$ into a risk-free deposit account.4  

$$
D_{t_{0}}=V_{t_{0}}-R_{t_{0}}
$$  

Note that the cash deposit $D_{t_{0}}$ is less than the time $t_{0}$ value of a risk-free zero-coupon bond that matures at time $T_{:}$ , denoted by $B(t_{0},\tau)N_{:}$ , where $B(t_{0},T)$ is the time $t_{0}$ price of a default-free discount bond with par value $\$1$ . Hence, in case of a sudden and sizable downward jump in $S_{t}$ , the note will not have enough cash in hand to switch to a zero-coupon bond. This is especially true if the jump in $S_{t}$ leads to flight to quality and increases the $B(t_{i},~T)$ at some future date $t_{i}$ . This is called the gap risk by the structurers and is studied later in the chapter.  

Apply this algorithm at every rebalancing date $t_{i\cdot}$ ,  

$$
t_{i}-t_{i-1}=\delta_{i}
$$  

as long as $F_{t_{i}}<V_{t_{i}}$ . This algorithm would increase the investment in the risky asset if things go well (i.e., if $V_{t_{i}}$ increases), and decrease the investment in case markets decline (i.e., if $V_{t_{i}}$ decreases).  

Finally, if at some time $\tau^{*}\ V_{\tau^{*}}$ falls and becomes equal to $\boldsymbol{F}_{\tau^{*}}$ , liquidate the risky investment position and switch all investment to cash. Since the floor $F_{t_{i}}$ is the present value at $t_{i\cdot}$ , of 100 to be received at $T_{\mathbf{\delta}}$ , this will guarantee that principal $N$ can be returned to the investors at $T.$ .  

# 23.4 MODELING THE CPPI DYNAMICS  

We now obtain the equations that give the dynamics of $V_{t}$ under the typical CPPI scheme. The equations are obtained from a relatively simple setting to highlight the important aspects of the methodology. The two points on which we focus are the following: first, we will see that from a single portfolio point of view, CPPI algorithms may be much more stable than they appear from the outside if there are no jumps. However, in reality there are jumps which lead to the gap risk. Second, we show that the CPPI methodology may have a more fragile structure with respect to yield curve movements than anticipated. This may be especially the case if sharp downward jumps in $S_{t}$ are correlated with a sudden steepening of the curve—exactly what happens during periods of excessive market stress.5  

Let us place ourselves in a Black Scholes-type environment, with constant interest rates $r$ and constant volatility $\sigma$ . Further, the $S_{t}$ follows the Wiener process-driven SDE,  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}
$$  

We know from the previous discussion that the investment in risky assets is  

$$
R_{t}=\lambda C u_{t}
$$  

and that the changes in the cushion are given by  

$$
\mathrm{d}C u_{t}=\mathrm{d}(V_{t}-F_{t})
$$  

This means  

$$
\mathrm{d}C u_{t}=(V_{t}-R_{t})\frac{\mathrm{d}B_{t}}{B_{t}}+R_{t}\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}F_{t}
$$  

where $B_{t}$ is the value of the zero-coupon bond at time $t.^{6}$ In this expression, we can replace $V_{t},R_{t}$ with their respective values to obtain  

$$
\mathrm{d}C u_{t}=(C u_{t}+F_{t}-\lambda C u_{t})\frac{\mathrm{d}B_{t}}{B_{t}}+\lambda C u_{t}\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}F_{t}
$$  

But the value of the floor increases according to  

$$
\mathrm{d}F_{t}=F_{t}{\frac{\mathrm{d}B_{t}}{B_{t}}}
$$  

This means  

$$
\mathrm{d}C u_{t}=(1-\lambda)C u_{t}\frac{\mathrm{d}B_{t}}{B_{t}}+\lambda C u_{t}\frac{\mathrm{d}S_{t}}{S_{t}}
$$  

Substituting further,  

$$
\mathrm{d}C u_{t}=(\lambda(\mu-r)+r)C u_{t}\mathrm{d}t+\lambda\sigma c\mathrm{d}W_{t}
$$  

This is a geometric stochastic differential equation whose solution is given by  

$$
C u_{t}=C u_{t_{0}}e^{\left(\lambda(\mu-r)+r-((\lambda^{2}\sigma^{2})/2)\right)(t-t_{0})+\lambda\sigma W_{t}}
$$  

We can combine this with $F_{t_{0}}$ to get the behavior of the portfolio net asset value for all $t\in[t_{0},T]$  

$$
V_{t}=F_{t_{0}}e^{r(t-t_{0})}+C u_{t}
$$  

Using standard results from stochastic calculus, we can calculate the expected portfolio value as of time $t$  

$$
E_{t_{0}}^{P}[V_{t}]=F_{t_{0}}+\left(100-F_{t_{0}}e^{r(T-t_{0})}\right)e^{r(t-t_{0})+\lambda(\mu-r)(t-t_{0})}
$$  

Note that the probability measure we use in this expectation is the real-world probability and not the risk-adjusted measure. This is the case since the drift of the $S_{t}$ process was taken to be the $\mu$ and not the risk-free rate $r$ .  

# 23.4.1 INTERPRETATION  

There are two equations in the above derivation that are very suggestive. The first relates to the dynamics of the cushion over time,  

$$
\mathrm{d}C u_{t}=(\lambda(\mu-r)+r)C u_{t}\mathrm{d}t+\lambda C u_{t}{\frac{\mathrm{d}S_{t}}{S_{t}}}
$$  

Note that with such a dynamic the cushion itself can never go below zero over time. In fact, suppose $C u_{t}$ becomes very small at time $t$ . The first term on the right-hand side of the equation will be positive. Also, being a Wiener-driven system, $S_{t}$ cannot exhibit jumps and over infinitesimal periods must change infinitesimally. The second term on the right-hand side then shows that the changes in $S_{t}$ affect the cushion with a coefficient of $\lambda C u_{t}.$ , which goes to zero as $C u_{t}$ approaches zero. Under these conditions, as the cushion $C u_{t}$ goes toward zero, the $\mathrm{d}C u_{t}$ will go to zero as well.  

This leads to an interesting conclusion. The CPPI method will always “work” in the sense that as the market goes against the investor, the cushion will never become negative. In the worst case, the cushion will be zero which means that the risky investment is liquidated. This leaves the investor with the zero-coupon bond which matures at a value of 100. Hence, the principal is “always” protected.  

Before we continue with the implications of this result consider the second interesting equation. The expected value of the portfolio was calculated as  

$$
E_{t_{0}}^{P}[V_{t}]=F_{t_{0}}+\left(100-F_{t_{0}}e^{r(T-t_{0})}\right)e^{r(t-t_{0})+\lambda(\mu-r)(t-t_{0})}
$$  

This is also very suggestive because, as long as $r<\mu$ , which means that the risky asset expected return is higher than the risk-free rate, the expected value of the portfolio can be increased indefinitely by picking higher and higher leverage factors, $\lambda$ .  

Thus we have reached an unrealistic result. The CPPI strategy will always work, in the sense that the investor’s initial investment is always protected, while at the same time the higher the leverage the higher the expected gains. This implies picking the highest possible leverage factor that is available to the structurer. Yet, it is clear that in the real world this is not the prudent approach. This, in turn, suggests that the model we discussed above may be missing some critical features of real-world investment.  

There are at least two possibilities, the first being the limits on borrowing. There are credit limits and the leverage cannot be increased indefinitely in the real world. The second possibility is more interesting.  

In the real world, $S_{t}$ process may not follow a geometric process and may contain jump factors. If this is the case, as $C u_{t}{\rightarrow}0$ , a downward jump in $S_{t}$ can make $C u_{t}$ negative. The portfolio value will fall below the floor and the investor’s initial investment is lost,  

$$
V_{t}<F_{t}
$$  

This is the gap risk. Note that, if there are such jumps in $S_{t}$ , then the presence of the leverage factor $1<\lambda$ will magnify them. The higher the $\lambda$ the higher will be the effect of a downward jump.  

# 23.4.2 HOW TO PICK λ  

The discussion involving the gap risk suggests a methodology for selecting a numerical value for the critical leverage parameter $\lambda$ . The structurer would first determine an acceptable threshold for the gap probability using the investor’s risk preferences. Then, using the observed volatility and jump parameters, the structurer would work backward and determine $\lambda$ that makes the gap probability equal to this desired amount. This could be done with Monte Carlo or with semiparametric methods as in Cont and Tankov (2009).  

Clearly this determination of $\lambda$ will be model dependent. A structurer would have a number of other ways to deal with this gap risk, some of which are discussed below.  

# 23.5 AN APPLICATION: CPPI AND EQUITY TRANCHES  

We will use structured credit as an application of the CPPI technique. The credit sector has experienced significant growth and innovation in recent years. The GFC did not leave it unaffected but the sector has recovered since and its products are likely to remain a part of the financial landscape. Two paradigms are observed in the structured credit sector. The first tracks some credit derivatives index, and the second is managed credit derivatives funds. CPPI techniques can be useful in both of these trends as shown in the example from the markets.  

# EXAMPLE  

Retail credit CPPI first ABN AMRO and AXA last week announced that they had closed the first principal protected credit derivatives fund targeted at retail investors. AXA persuaded its home regulator in France to permit the leveraged fund, and similar deals are expected to be launched in other regimes.  

The fund is structured like an actively managed synthetic collateralized debt obligation. It will have a minimum of 100 credit default swap references and is starting with just under 120 names.  

It uses CPPI from ABN AMRO to provide the capital protection that was necessary to obtain regulatory approval for its sale to retail investors in France. The insurance is provided on a binary basis if the basket of default swaps managed by AXA performs so poorly that a zero-coupon bond would have to be bought to guarantee investor capital, then there would be an effective wind-up.  

In this section, we discuss the application of the CPPI technique to standard credit index tranches. It turns out that combining CPPI and iTraxx tranches is quite simple in terms of financial engineering, although there are some practical issues that need to be resolved in practice. Here is the algorithm.  

1. Receive cash of $N=100$ from the investor.   
2. Calculate the difference between par and the cost of a zero-coupon bond $F_{t},$ and as before let this term be $C u_{t}$ , the cushion.   
3. Multiply the cushion $C u_{t}$ by the leverage factor $\lambda$ . This is the leveraged amount.   
4. Subtract the leveraged amount, $C u_{t}\times\lambda$ , from the 100 total cash $N$ and invest, $C u_{t}\times\lambda$ , in the risky asset, which in this case is assumed to be the iTraxx $0-3\%$ equity tranche. Keep the remaining cash or reserve cash, $\begin{array}{r}{I O O-C u_{t}\times\lambda.}\end{array}$ , in a deposit account or as collateral.7   
5. As the price of the iTraxx equity tranche goes up and down, adjust the allocation between risk asset and reserve cash to keep the leverage of the trade constant at $\lambda.$ .  

Thus far this is a straightforward application of the previously discussed CPPI algorithm. The only major complication is in the definition of the risky asset. Standard equity tranches are quoted as upfront percentages and this will lead to a modification of the algorithm. In fact, suppose the amount to be invested in the risky asset is $R_{t},$ and suppose also that the iTraxx equity tranche quote is given by $q_{t}$ where the latter is a pure number denoting the upfront payment as a percentage.8 Then the relationship between the amount allocated in the risky asset and the notional amount invested in the equity tranche $N^{\mathrm{Eq}}$ will be as follows:  

$$
N_{t_{i}}^{\mathrm{Eq}}=\frac{R_{t_{i}}}{(1-q_{t})}
$$  

In terms of the amount invested in the risky asset, $R_{t_{i}}$ , this can also be written as  

$$
R_{t_{i}}=N_{t_{i}}^{\mathrm{Eq}}\times(1-q_{t})=N_{t_{i}}^{\mathrm{Eq}}-\frac{R_{t_{i}}}{(1-q_{t})}q_{t}
$$  

It may be helpful to discuss a numerical example at this point.  

# 23.5.1 A NUMERICAL EXAMPLE  

The following example shows how CPPI can be combined with the ITraxx and has similarities to a real-world product CPPI product that was called SPRING and developed by the IXIS CDO group.  

First we note that the equity tranche of the iTraxx Index is quoted as an upfront percentage of the notional plus 500 basis point running-fee paid quarterly. Assume that the upfront fee of the iTraxx equity tranche is $q_{t}=20\%$ of the notional amount invested in the equity tranche $N^{\mathrm{Eq}}$ and that the annual LIBOR rate is $L_{t}=5\%$ . For simplicity, suppose the swap curve is flat at $5.095\%$ as well. The CPPI is applied with daily adjustment periods denoted by $t_{i},i=0,1,...,n.$ . The leverage factor is assumed to be 2. Assume no bid ask spreads. Figure 23.1 illustrates how the leveraged amount $C u_{t}\times\lambda$ is invested in the risky asset. It also shows that the equity tranche of the iTraxx index is quoted as an upfront cash amount.  

![](033d2347fe0d204da0d5723724dd406ff962041dea0e5962f83151def95a7386.jpg)  

# FIGURE 23.1  

iTraxx CPPI example.  

We apply the steps above in a straightforward fashion to a 5-year CPPI note where the underlying is the equity tranche.  

# 23.5.1.1 The initial position  

Initially the CPPI will have the following structure.  

1. Receive $N=100$ .   
2. The floor is  

$$
\begin{array}{r l}{F_{t}}&{{}={\frac{100}{\left(1+0.05095\right)^{5}}}}\\ {\ }&{{}=78}\end{array}
$$  

3. The cushion is  

$$
\begin{array}{r l}{C u_{t}}&{{}=100-78}\\ {\phantom{\sum}}&{{}=22}\end{array}
$$  

4. Assuming a leverage of  

$$
\lambda=2
$$  

the amount to be invested in the risky asset is  

$$
22\times2=44
$$  

This is the investment to be allocated to the equity tranche.  

5. The iTraxx equity tranche pays an upfront cash amount of $20\%\times N^{\mathrm{Eq}}$ . Therefore, if the risky asset exposure is $R_{t}=44$ , then the notional amount invested in the equity tranche $N^{\mathrm{Eq}}$ should be9  

$$
N^{\mathrm{Eq}}=\frac{44}{(1-0.20)}=55
$$  

Thus, sell equity tranche protection with notional $N^{\mathrm{Eq}}$ of 55. In other words, an equity tranche notional amount $N^{\mathrm{Eq}}$ of 55 implies an uncovered exposure of 55 less 11 $(=q_{t}\times55=20\%\times55)$ received upfront which leaves 44. The 44 is put into reserve cash. 6. When we buy the iTraxx equity tranche we enter into a swap on the iTraxx equity tranche. This implies that the cash allocated to the risky asset, in addition to the upfront cash received, is held as collateral for the swap. This is illustrated in Figure 23.1 in which we can see how the equity tranche notional amount $N^{\mathrm{Eq}}$ consists of the upfront payment (fee) of 11 and the risky asset. Note that the total amount of cash to be kept as collateral for the equity protection position is  

$$
q_{t}N^{\mathrm{Eq}}+(100-\lambda C u_{t})=20\%\times55+44=11+44=55
$$  

Since the risky asset investment is 44 and the cash invested initially is $N=I O O$ , a balance of 56 remains. The balance of 56 is kept in reserve cash and receives LIBOR.  

7. Does the trade indeed have a leverage of $\lambda=2$ as desired? We invested 44 in the risky asset and 56 in reserve cash. The total portfolio value (PV) is 100 which corresponds to the 100 initially invested. The cost of the zero-coupon bond $F_{t}$ was 78. Leverage can be calculated as follows:  

$$
{\mathrm{Leverage}}={\frac{{\mathrm{risky~asset}}}{{\mathrm{portfolio~value}}-F_{t}}}={\frac{44}{100-78}}=2
$$  

8. As the equity tranche quote changes over the rebalancing periods $t_{1},t_{2},\ldots$ adjust the position dynamically, reducing the exposure to the risky asset as $q_{t}$ increases, and increasing the exposure as $q_{t}$ decreases.  

Note that during this process the equity tranche position is actually taken as an unfunded investment. Still, the cash allocated to the risky asset, plus the upfront cash, is held as collateral for the position.  

# 23.5.1.2 Dynamic adjustments  

We can see from Eq. (23.28) that if the value of the risky asset increases or decreases, the leverage is going to change. Let, for example, $q_{t_{1}}=15\%$ , which can be interpreted as perceived risk decreasing (compared to the original value of $q_{t_{1}}=15\%$ , the index tightening, and the quoted price for protection falling. This corresponds to an increase in the value of the iTraxx equity tranche and the value of the risky asset investment. After all, one can buy protection at $15\%$ and close the position with a profit. Yet, with the structured note the position is continued after an adjustment. We cover these steps below.  

1. The value of the risky asset is  

$$
\begin{array}{r l}{N\big(1-q_{t_{1}}\big)}&{{}=44\times(1-15\%)}\\ {}&{{}=46.75}\end{array}
$$  

Due to unrealized gains, the value of the risky asset has gone up by  

$$
R_{t_{1}}-R_{t_{0}}=2.75
$$  

This is the case since we can close the position by buying equity protection at $15\%$ upfront. Then we recover the 44 deposited as collateral for the equity tranche investment, and in addition we receive the realized gain  

$$
55\times0.05=2.75
$$  

by not losing this position, it is as if we are investing 46.75 in the risky asset.  

2. Calculate the $V_{t_{1}}$ using  

$$
V_{t_{1}}=F_{t_{0}}{\left(1+L_{t_{0}}\right)}+N_{t_{0}}{\left(q_{t_{1}}-q_{t_{0}}\right)}+N_{t_{0}}{\left(1+L_{t_{0}}\right)}+N(0.05)
$$  

In this case, this amounts to  

$$
105.095+2.75+(11)(0.05)+55(0.05)
$$  

The first term is the interest on the 100 kept as cash or collateral. The second term is the capital gains from the $q_{t}$ move, the third is the LIBOR earned from the upfront deposit. Finally, the fourth term is the 500 bp running fee on the 55.  

3. What is the effect on leverage? The new leverage can be calculated as follows:  

$$
{\mathrm{Leverage}}={\frac{\mathrm{risky~asset}}{\mathrm{portfolio~value}-F_{t}}}={\frac{46.75}{102.75-78}}=1.8
$$  

To bring leverage back to the target level of 2, the portfolio needs to be rebalanced. The risky assets have a value of 46.75 and the reserve cash remains at 56. To obtain a leverage of 2 we need risky assets to increase to 49.5. This can be achieved by reallocating 2.75 from reserve cash to risky assets. As a result risky assets increase to 49.5 and reserve cash falls to 53.25. The increase in risky assets is used to buy more units of the iTraxx equity tranche. Since the current new upfront fee $q_{t_{1}}$ is $15\%$ , we can buy an equity notional amount of  

$$
N^{\mathrm{Eq}}=\frac{2}{(1-0.15)}=2.353
$$  

Since the upfront fee $q_{t_{1}}$ is $15\%$ , this implies that we receive an upfront payment or fee that can be calculated as follows:  

$$
\mathrm{fee}=2.353\times(1-q_{t})=2.353\times(1-15\%)=0.353.
$$  

We can verify the cash collateral corresponding to the notional amount $N^{\mathrm{Eq}}$ of the equity tranche.  

Collateral $\O=$ risky asset cash $^+$ initial upfront cash $^+$ additional upfront cash $=49.5+11+0.353=60.853$  

Figure 23.2 illustrates the difference between the value of risky assets, which is 49.5, and the cash allocated to risky assets, which is 46.75. The difference of 2.75 is due to the unrealized capital gains. Here we have assumed that the zero-coupon bond value will remain unchanged, but in reality, changes in the value of the zero-coupon bond and income flows will also affect leverage.  

The opposite adjustment will be implemented if $q_{t_{1}}$ decreases. We leave the details of this case to the end-of-chapter exercises. Instead, we will consider the case of a default.  

![](6d664aebfc2a092ce314f7cae62582a6f0e8579083ecea81011696732e7f3349.jpg)  

# FIGURE 23.2  

Dynamic adjustment.  

# 23.5.1.3 Default and switching out of CPPI into zero-coupon bond  

What is the liability of the bank that structures the CPPI if the iTraxx portfolio defaults? In the original numerical example, the investor received 100 and placed 56 into reserve cash and 44 into the risky asset. The notional amount of the equity tranche was 55 and it was backed by collateral of 44 in addition to the upfront fee of 11. In the scenario of a default of the iTraxx equity tranche, the equity tranche value would fall to zero. The structuring bank had bought principal protection for 78 which will be paid out to the purchase of the CPPI product. The principal protection costs the bank 78. Since the equity notional amount of the iTraxx tranch is 55, the bank needs to pay 55 to the counterparty, which implies that the total liability is 133 $(=55+78)$ . In terms of collateral, the bank holds cash of 44 related to the risky asset, reserve cash of 56 and the upfront fee payment of 11. The total cash assets are therefore 111. If we subtract assets from liabilities, we obtain a loss of 22. One possible strategy to avoid such a loss is to reduce the risk before default occurs. For example, if the value of the equity tranche deteriorates as credit quality drops, the portfolio could be switched from the CPPI structure to a zero-coupon bond when the value passes a certain threshold such as falling close to the cost of the zerocoupon bond.  

# 23.6 DIFFERENCES BETWEEN CPDO AND CPPI  

One of the more recent structured products that is sometimes described as sharing similarities with CPPI is called constant proportion debt obligation (CPDO). However, the two structures are very different and here we briefly contrast CPDO and CPPI to clear up any potential confusion. It is true that the CPDO approaches share some common features with CPPI products, but there are also important differences which imply that CPDOs are not really an example of principal protection products. What CPDOs have in common with CPPI structures is that they use a constant proportion approach to determining the leverage and they both rebalance the portfolio between a risky (credit) asset and the safe asset. As the name indicates, CPDOs are applied to credit indices such as iTraxx or CDX. There are two important differences between CPDO and CPPI structures. One of the selling points of CPDO is to try to achieve a high yield for investors. This is attempted by using a relatively high level of leverage. In contrast to CPPI, however, leverage in CPDO structures will be increased when the net asset value of the portfolio decreases and falls below the target level. If the net asset value of the portfolio rises and comes close to the target amount, leverage will be reduced. The way that CPPI products achieve principal protection is by guaranteeing the zerocoupon bond to the investor, while making the seller of the CPPI bear any losses. In a CPDO, on the other hand, there is no guaranteed principal protection. If the underlying risky asset that the CPDO invests in performs well, the investor receives promised coupon and principal payments, but if the asset does not perform well, only the remaining amount is paid to the investor and this may be less than the principal invested at the beginning. Another important difference between CPPI and CPDO is that different strategies are used to realize the intended performance. At inception the value of the CPDO is below the target portfolio value and the CPDO structure will at each time take risk exposure proportional to the amount the CPDO portfolio is lacking in order to reach the target value. This is in contrast to the CPPI structure which will take risk exposure positions depending on the amount of surplus the portfolio value has with respect to the floor value. The above discussion shows conceptually that CPDO structures do not offer the same protection as CPPI structures. This was also illustrated in real life as the GFC led to poor performance and closure of many CPDO structures.  

# 23.7 A VARIANT: THE DPPI  

Dynamic portfolio insurance (DPPI) methodology is a variation of the CPPI. The difference is that leverage is not constant but can change over time. Here is a brief example from the markets.  

# EXAMPLE  

LONDON, June 14 (Reuters)—PIMCO, one of the world’s biggest bond funds, has joined forces with Goldman Sachs to launch a range of derivative products. The investments include principal protected and leveraged structures aimed at institutional investors, high net worth individuals and private banks.  

The main product, launched under PIMCO is a principle protected investment based on Goldman’s Variable Proportion Portfolio Protection, similar to the better-known CPPI technology.  

The leverage ratio $\lambda_{t_{i}}$ which was constant during the CPPI adjustments can be made variable and becomes one of the unknowns to be determined. The structurer needs to provide an algorithm to do this. The idea is that the leverage ratio can be made to depend on some variables that one thinks are relevant to the problem under consideration in some optimal fashion. In particular, the exposure to the risky asset may depend on  

1. The past behavior of the returns   
2. The volatility of the returns   
3. The liquidity observed in the market for the underlying asset, since the methodology is heavily   
dependent on the correct rebalancing   
4. And upon the so-called gap risk.  

Finally, another relevant variable may the dependence of $\lambda_{t_{i}}$ on the swap curve parameters. The scenarios discussed above illustrated the importance of this. Note that this may be even more relevant for the credit market CPPI notes.  

In DPPI, the allocation between the risky asset and cash is dynamically managed with a variable leverage ratio that will depend on one or more of these factors. Supposedly, the CPPI exposure to the risky asset increases when things “go well,” and decreases when things “go badly.” At the outset, a variable leverage ratio seems to be better able to handle changes in the yield curve environment than the classical CPPI procedures. For example, the leverage ratio $\lambda_{t_{i}}$ may go down during high-volatility periods and may go up during low-volatility periods. The response to changes in the market liquidity could be similar.  

# 23.8 APPLICATION OF CPPI IN THE INSURANCE SECTOR: ICPPI  

CPPI techniques continue to be applied in different financial sectors despite the turmoil related to credit-linked CPPI products during the GFC. One example of the application of CPPI techniques is the insurance sector. The difficult economic climate following the GFC also affected the insurance sector and many insurance firm customers have become more cautious. There is still demand for guaranteed products that include upside participation. The UK’s with profit or traditional variable annuity (VA) products typically included restrictions on protection levels and fund choices. Customers are now asking for less restrictive guaranteed products with upside participation. In response, insurance firms are exploring a variation on CPPI-type structures. Insurance companies compete with other financial services such as banks for long-term savings customers, but prefer not to offer products that add risks to their own balance sheets or require expensive hedges based on derivatives. CPPI solutions have been applied in several countries’ insurance sectors. In Japan, insurers employ them to match guarantees embedded in VA policies. In Germany they were popular in $2006{-}2007$ since they allowed insurers to circumvent restrictive investment rules for insurance companies that attempted to offer state-subsidised “Riester” pension products.  

Traditional CPPI products however had several drawbacks. If the performance of the underlying risk asset resulted in the portfolio becoming cash-locked, investors missed out on future performance since the return reverted to the guaranteed level. This occurred in many instances during the GFC which implied that CPPI investors did not get the returns that they were expecting.  

The market has responded to the problems related to the path-dependent nature of traditional CPPI structures by innovating and producing so-called individual constant proportion portfolio insurance (ICPPI). ICPPI products are customized for each policyholder and provide discretion on the level of the account floor, the duration of the contract and the choice of risky assets within the CPPI structure.  

Another innovation found in some ICPPI products addresses the issue of rebalancing costs. As discussed earlier, traditional CPPI require regular rebalancing (between risky assets such as physical equities and safe assets) which incurs costs. To address this issue some ICPPI providers use derivatives to create quasi-synthetic portfolios that replicate equity movements without the need for purchases of physical equities. One drawback of this innovation is however that it introduces counterparty risk as well as market risk into ICPPI products. Insurers using such ICPPI structures consequently need to adapt their risk management practices related to counterparty risk, a topic that is discussed in the next chapter.  

The following CPPI application example is from the insurance sector.  

# EXAMPLE  

Asset management firm Allianz Global Investors is already using ICPPI structures. Kai Wallbaum,   
Frankfurt-based head of retail and life/asset solutions at the firm, says “We have installed an operational   
platform where we are able to manage on an individual account basis certain algorithmic strategies. One of   
the approaches clients often ask for is this individual CPPI, where we can manage a certain dynamic risk   
approach for each customer and provide a custom guarantee as well.” (Insurance Risk, 9 May 2013, “Insurers eye CPPI structures for next generation of savings products”, www.risk.net/2266887.)  

Another solution to the cash-lock scenario is to create an ICPPI product that is partly invested in a core insurance fund and partly invested in a third-party fund which contains its own guarantee level and allocations are changed between the two relatively infrequently, for example on a monthly instead of a daily basis. The guarantee from the third-party fund could be against decreases in the NAV by $80\%$ , for example, and this provides protection against locking in a low return while reducing operational and rebalancing costs. The following example describes one such product that was launched in 2012.  

# EXAMPLE  

Italian banking group Unicredit is one provider offering such a solution. The group pioneered an ICPPI   
product in 2012 called Green, aimed at its private banking clients, and achieved such success with this that   
it is now looking to partner with insurance providers to explore opportunities in other countries. A further challenge for insurers is raising awareness around the products and dispelling the notion that   
long-term guarantees are not worth their price tag. “A lot of insurers are still at the concept stage when it   
comes to developing new products and customers are not yet at a place where they can understand the cost  
benefit of ICPPIs,” [...] (Insurance Risk, 9 May 2013, “Insurers eye CPPI structures for next generati of savings products”, www.risk.net/226688  

The reading illustrates that one of the motivations for the use of CPPI techniques by insurance companies is to avoid the costs of expensive derivatives such as options used in OBPI approaches.  

As our review of CPPI structures showed in earlier sections, CPPI algorithms can be customized and depending on an investor’s risk aversion, the cushion can be set at a particular level. Some insurers have implemented systems to offer tailor-made CPPI specifications. Some of the issues of CPPI are highlighted. As the risky asset in the CPPI structure declines, for example, the funds are placed in a safe deposit or bond permanently and this provides principal protection but also prevents pensioners from benefiting from future market recoveries. The reading also provides an illustration of the dynamic rebalancing mechanisms that we discussed earlier. Rebalancing incurs transaction costs and these costs are higher for physical assets than derivatives. Derivatives on the other hand introduce counterparty risk, which is something that we cover in detail in the subsequent chapter.  

# 23.9 REAL-WORLD COMPLICATIONS  

The idea behind CPPI techniques is simple. Actually, even the modeling is fairly straightforward.   
Yet, in practice, several difficulties arise. We will look at only some of them.  

# 23.9.1 THE GAP RISK  

If a structurer does not want exposure to gap risk then it could be sold to other investors through other structured products. For example, with structured products such as autocallables, a high coupon is paid to the investor, but the structure is called automatically if the underlying price hits a preselected level. Note that with autocallables the investor receives a high coupon but also assumes the risk of large downward movements in a basket. The extra coupon received by the investor can be visualized as the cost of insuring the gap risk.10  

Another possibility frequently used in practice is to manage the gap risk using deep out-of-themoney puts. This is possible if the underlying is liquid. However, in the case of CPPI strategies, the underlying is often illiquid and this makes delta-hedging of the option positions difficult. Still, one can claim that during stress periods, correlations go toward one and liquid indices can become correlated with the illiquid underlying. Hence, carefully chosen deep out-of-the-money options on liquid indices can also hedge the gap risk. Banks generally charge a small “protection” or “gap” fee to cover gap risk, usually as a function of the notional leveraged exposure.  

# 23.9.2 THE ISSUE OF LIQUIDITY  

The issue of liquidity of the underlying is important to CPPI-type strategies for several reasons. First is the need to close the risky asset position when the cushion goes toward zero. If the underlying market is not liquid this may be very difficult to do, especially when markets are falling at a steep rate.11  

Second, if the underlying is illiquid, then options on the underlying may not trade and hedging the gap risk through out-of-the-money options may be impossible.  

The third issue is more technical. As mentioned in the previous section, gap risk can be modeled using the jump process augmented stochastic differential equations for $S_{t}.$ In this setting, jump risk is the probability that $C u_{t}$ is negative. This determines the numerical value selected for the $\lambda$ parameter. However, note that if the underlying is not liquid, then options on this underlying will not be liquid either. Yet, liquid option prices are needed to calibrate the parameters of the jump process. With illiquid option markets this may be impossible. Essentially, the selection of $\lambda$ would depend on arbitrarily made assumptions and/or historical data.  

# 23.9.3 WHICH PRINCIPAL PROTECTION TECHNIQUE IS BEST IN PRACTICE?  

In the introduction to this chapter, we noted that different principal protection techniques exist including OBPI, CPPI, DPPI, and others. Which principal protection technique works best in practice? It turns out that this is an empirical question and no theoretical ranking of the techniques can be provided. Options can at certain times be very expensive, making OBPI unattractive. At first glance, CPPI may appear similar to standard option replication strategies. However, there are fundamental differences since standard CPPI does not make assumptions about future portfolio volatility, the distribution of portfolio returns, or the investor’s time horizon. Because of the way that the cushion adjusts in CPPI, this approach will work well in a trending bull market with no reversals, since the hedger will keep increasing her exposure. There are some market environments when CPPI is less likely to do well. In a market without trends and oscillating prices, CPPI can be expected to perform poorly, since the hedge will buy on up-moves in prices only to see the market weaken subsequently and sell on down-moves in prices only to see the market rebound. Monte Carlo simulations and historical backtests that are specific to the underlying asset of interest and that incorporate assumptions about future market environments are required to decide which PPI technique generates the best risk-adjust performance for the hedger or investor. For the S&P500, for example, Lu (2010) provides a comparison of the performance of different portfolio insurance approaches including OBPI, CPPI, and DPPI.  

# 23.10 CONCLUSIONS  

There may be several other real-world complications. For example, consider the application of the CPPI to the credit sector. One very important question is what happens on a roll? Clearly the structurer would like to stay with on-the-run series, and during the roll there will be mark-to-market adjustments which may be infinitesimal and similar to jumps.  

A second question is how to pick the leverage factor in some optimal fashion. It is clear that this will involve some Monte Carlo approach but the more difficult issue is how to optimize this.  

# SUGGESTED READING  

The first academic papers on CPPI were by Perold (1986) who discusses CPPI for fixed-income instruments and Black and Jones (1987) who study CPPI for equity instruments. We also recommend the recent paper by Cont and Tankov (2009). Joossens and Schoutens (2010) discuss and compare CPPI and CPDO structures. Jin and Whetten (2005) summarize the evolution of CreditLinked CPPI Variations.  

# EXERCISES  

1. Consider the iTraxx CPPI example in this chapter. We assumed an increase in the value of the iTraxx tranche as $q_{t_{1}}$ dropped from $20\%$ to $15\%$ . Now assume that spreads widen and credit quality decreases so that $q_{t_{1}}$ increases from $20\%$ to $25\%$ . Calculate the resulting change in the leverage and explain the adjustment in detail required to return to the target leverage of 2.  

2. The iTraxx crossover index followed the path given below during three successive time periods:  

Assume that there are 30 reference names in this portfolio.  

a. You decide to select a leverage ratio of 2 and structure a five-year CPPI note on iTraxx crossover index. LIBOR rates are $5\%$ . Describe your general strategy and, more important, show your initial portfolio composition.   
b. Given the path above, calculate your portfolio adjustments for the three periods.   
c. In period four, iTraxx becomes 370 and one company defaults. Show your portfolio adjustments. (Assume a recovery of $40\%$ . Reminder: Do not forget that there are 30 names in the portfolio.)  