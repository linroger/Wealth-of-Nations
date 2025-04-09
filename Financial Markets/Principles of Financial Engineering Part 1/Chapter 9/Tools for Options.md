# 9.5 TOOLS FOR OPTIONS  

The Black-Scholes PDE can be exploited to obtain the major tools available to an option trader or market maker. First of these is the Black-Scholes formula, which gives the arbitrage-free price of a plain vanilla call (put) option under specific assumptions.  

The second set of tools is made up of the "Greeks." These measure the sensitivity of an option's price with respect to changes in various market parameters. The Greeks are essential in hedging and risk managing options books. They are also used in pricing and in options strategies.  

The third set of tools are ad hoc modifications of these theoretical constructs by market practitioners. These modifications adapt the theoretical tools to the real world, making them more "realistic."  

# 9.5.1 SOLVING THE FUNDAMENTAL PDE  

The convexity of option payoffs implies an arbitrage argument, namely that the expected net gains (losses)from $S_{t}$ oscillations are equal to time decay during the same period. This leads to the. Black-Scholes PDE:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

with the boundary condition  

$$
C(T)=\operatorname*{max}[S_{T}-K,0]
$$  

Now, under some conditions PDEs can be solved analytically and a closed-form formula can be obtained. See Duffie (2001). In our case, with specific assumptions concerning the dynamics of $S_{t},$ this PDE has such a closed-form solution. This solution is the market benchmark known as the Black-Scholes formula.  

# 9.5.2 BLACKSCHOLES FORMULA  

An introduction to the Black--Scholes formula first requires a good understanding of the underlying. assumptions. Suppose we consider a plain vanilla call option written on a stock at time t. The option expires at time $T>t$ and has strike price $K.$ It is of European style and can be exercised only at expiration date $T.$ Further, the underlying asset price and the related market environment. denoted by $S_{t}$ have the following characteristics:  

1. The risk-free interest rate is constant at $r$   
2. The underlying stock price dynamics are described in continuous time by the stochastic differential equation (SDE):15  

$$
\mathrm{d}S_{t}=\mu(S_{t})S_{t}{\mathrm{~}}\mathrm{d}t+\sigma S_{t}{\mathrm{~}}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

where $W_{t}$ represents a Wiener process with respect to real-world probability $P$ 16  

To emphasize an important aspect of the previous SDE, the dynamics of $S_{t}$ are assumed to have a constant percentage variance during infinitesimally short intervals. Yet, the drift component, $\mu(S_{t})S_{t}.$ can be general and need not be specified further. Arbitrage arguments are used to eliminate $\mu(S_{t})$ and replace it with the risk-free instantaneous spot rate $r$ in the previous equation.  

3. The stock pays no dividends, and there are no stock splits or other corporate actions during the period $[t,T]$   
4. Finally, there are no transaction costs and no bid-ask spreads.  

Under these assumptions, we can solve the PDE in Eqs. (9.49) and (9.51) and obtain the Black-Scholes formula:  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

where $d_{1},d_{2}$ are  

$$
\begin{array}{l}{{d_{1}={\displaystyle\frac{\log(S_{t}/K)+(r+(\sigma^{2}/2))(T-t)}{\sigma\sqrt{T-t}}}}}\ {{d_{2}={\displaystyle\frac{\log(S_{t}/K)+(r-(\sigma^{2}/2))(T-t)}{\sigma\sqrt{T-t}}}}}\end{array}
$$  

These increments are the continuous time equivalents of sequences of normally distributed variables. For a discussion of stochastic differential equations and the Wiener process, see, for example, Oksendal (2010). Hirsa and Neftci (2013) provides the heuristics.  

$N(x)$ denotes the cumulative standard normal probability:  

$$
N(x)=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

In this formula,. $r,\sigma,T_{:}$ and $K$ are considered parameters, since the formula holds in this version, only when these components are kept constant.'7 The variables are $S_{t}$ and $t.$ The latter is allowed to change during the life of the option..  

Given this formula, we can take the partial derivatives of  

$$
C(t)=C(S_{t},t\mid r,\sigma,T,K)
$$  

with respect to the variables $S_{t}$ and $t$ and with respect to the parameters $r,\sigma,T,$ and $K$ These partials are the Greeks. They represent the sensitivities of the option price with respect to a small variation in the parameters and variables. Implied volatility $(\sigma_{\mathrm{IV}})$ is calculated by backing out the $\sigma$ that gives the observed option price $C(t)$ if one was to plug it into the pricing formula (9.52) together with the other input parameters such as $r,T,K,S_{t},$ and $t.$ Since the implied volatility is implied by the observed market price of the option, its calculation is similar to that of the yield to maturity for bonds which is calculated based on the market price of the bonds, a pricing formula and other input parameters such as maturity and frequency of cash flow payments.  

# 9.5.2.1 Black's formula  

The BlackScholes formula in Eq. (9.52) is the solution to the fundamental PDE when delta hedg-. ing is done with the "cash" underlying. As discussed earlier, trading gains and funding costs lead to the PDE:  

$$
r C_{s}S_{t}-r C+\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}=-C_{t}
$$  

with the boundary condition:  

$$
C(S_{T},T)=\operatorname*{max}[S_{T}-K,0]
$$  

When the underlying becomes a forward contract, $S_{t}$ will become the corresponding forward price denoted by $F_{t}$ and the Black-Scholes PDE will change slightly.  

Unlike a cash underlying, buying and selling a forward contract does not involve funding. Long. and short forward positions are commitments to buy and sell at a future date. $T.$ rather than outright purchases of the underlying asset. Thus, the only cash movements will be interest expense for funding the call, and cash gains from hedge adjustments. This means that the corresponding PDE will look like  

$$
-r C+\frac{1}{2}C_{s s}\sigma^{2}F_{t}^{2}=-C t
$$  

with the same boundary condition:  

$$
C(F_{T},T)=\operatorname*{max}[F_{T}-K,0]
$$  

where $F_{t}$ is now the forward price of the underlying  

The solution to this PDE is given by the so-called Black's formula in the case where the options are of European style.  

$$
C(F_{t},t)^{\mathrm{Black}}=e^{-r(T-t)}[F_{t}N(d_{1})-K N(d_{2})]
$$  

with  

$$
d_{1}^{\mathrm{Black}}=\frac{\log(F_{t}/K)+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{(T-t)}}
$$  

$$
d_{2}^{\mathrm{Black}}=d_{1}^{\mathrm{Black}}-\sigma\sqrt{(T-t)}
$$  

Black's formula is useful in many practical circumstances where the Black-Scholes formula. cannot be applied directly. Interest rate derivatives such as caps and floors, for example, are options written on LIBOR rates that will be observed at future dates. Such settings lend themselves better. to the use of Black's formula. The underlying risk is a forward interest rate such as forward LIBOR, and the related option prices are given by Black's formula. However, the reader should. remember that in the preceding version of Black's formula the spot rate is taken as constant. In Chapter 16, this assumption will be relaxed..  

# 9.5.3 OTHER FORMULAS  

The Black-Scholes type PDEs can be solved for a closed-form formula under somewhat different conditions as well. These operations result in expressions that are similar but contain further parameters and variables. We consider two cases of interest. Our first example is a chooser option.  

# 9.5.3.1 Chooser options  

Consider a vanilla put, $P\left(t\right)$ and a vanilla call,. $C\left(t\right)$ written on $S_{t}$ with strike. $K$ and expiration $T.$ A chooser option then is an option that gives the right to choose between $C(t)$ and $P(t)$ at some later date $T_{0}$ . Its payoff at time. $T_{0}$ with $T_{0}<T$ is  

$$
C^{h}(T_{0})=\operatorname*{max}\left[C\left(S_{T_{0}},T_{0}\right),P\left(S_{T_{0}},T_{0}\right)\right]
$$  

Arbitrage arguments lead to the equality  

$$
P\big(S_{T_{0}},T_{0}\big)=-\big(S_{T_{0}}-K e^{-r(T-T_{0})}\big)+C\big(S_{T_{0}},T_{0}\big)
$$  

Using this, Equation (9.64) can be written as  

$$
C^{h}(T_{0})=\operatorname*{max}\left[C\left(S_{T_{0}},T_{0}\right),-\left(S_{T_{0}}-K e^{-r(T-T_{0})}\right)+C\left(S_{T_{0}},T_{0}\right)\right]
$$  

or, taking the common term out,  

$$
C^{h}(T_{0})=C\big(S_{T_{0}},T_{0}\big)+\operatorname*{max}\big[-\big(S_{T_{0}}-K e^{-r(T-T_{0})}\big),0\big]
$$  

In other words, the chooser option payoff is either equal to the value of the call at time $T_{0}$ or it is that plus a positive increment, in the case that  

$$
\left(S_{T_{0}}-K e^{-r(T-T_{0})}\right)<0
$$  

But, this is equal to the payoff of a put with strike price $K e^{-r(T-T_{0})}$ and exercise date $T_{0}$ . Thus, the pricing formula for the chooser option is given by  

$$
C^{h}(t)=[S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})]+[-S_{t}N(-\overline{{d}}_{1})+K e^{-r(T-T_{0})}e^{-r(T_{0}-t)}N(-\overline{{d}}_{2})]
$$  

Simplifying:  

$$
C^{h}(t)=[S_{t}(N(d_{1})-N(-\overline{{d}}_{1}))]+K e^{-r(T-t)}(N(-\overline{{d}}_{2})-N(d_{2}))
$$  

with  

$$
d_{1,2}=\frac{\ln(S_{t}/K)+(r\pm(1/2)\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

$$
\overline{{d}}_{1,2}=\frac{\ln(S_{t}/K)+(r(T-t)\pm(1/2)\sigma^{2}(T_{0}-t))}{\sigma\sqrt{(T_{0}-t)}}
$$  

A more interesting example from our point of view is the application of the Black-Scholes approach to barrier options, which we consider next..  

# 9.5.3.2 Barrier options  

Barrier options will be treated in detail in the next chapter. Here we just define these instruments and explain the closed-form formula that is associated with them under some simplifying assumptions. This will close the discussion of the application spectrum of Black-Scholes type formulas.  

Consider a European vanilla call, written on $S_{t}$ ,with strike. $K$ and expiration $T$ $t<T.$ Assume that $S_{t}$ satisfies all Black-Scholes assumptions. Consider a barrier $H$ , and assume that $H{<}S_{t}{<}K$ as of time t. Suppose we write a contract stipulating that if, during the life of the contract, $[t,T],S_{t}$ falls below the level. $H_{:}$ the option disappears and the option writer will have no further obligation. In other words, as long as. $H<S_{u}.$ $u\in[t,T]$ , the vanilla option is in effect, but as soon as $S_{u}$ falls below $H.$ the option dies. This is a barrier option-specifically a down-and-out barrier. Two examples are shown in Figure 9.8a.  

The pricing formula for the down-and-out call is given by  

$$
\begin{array}{r l}{C^{b}(t)}&{{}=C(t)-J(t)\quad{\mathrm{~for~}}H\leq S_{t}}\ {C^{b}(t)}&{{}=0\quad{\mathrm{~for~}}S_{t}<H}\end{array}
$$  

Here $C(t)$ is the value of the vanilla call, which is given by the standard Black-Scholes formula, and where $J(t)$ is the discount that needs to be applied because the option may die if. $S_{t}$ falls below $H$ during $[t,T]$ . See Figure 9.8b. The formula for. $J(t)$ is  

$$
J(t)=S_{t}\left(\frac{H}{S_{t}}\right)^{(2(r-(1/2)\sigma^{2})/\sigma^{2})+2}N(c_{1})-K e^{-r(T-t)}\left(\frac{H}{S_{t}}\right)^{(2(r-\frac{1}{2}\sigma^{2}))/\sigma^{2}}N(c_{2})
$$  

where  

$$
c_{1,2}={\frac{\log(H^{2}/S_{t}K)+(r\pm(1/2)\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

It is interesting to note that when $S_{t}$ touches the barrier  

$$
S_{t}=H
$$  

![](images/35ab8f4a50af737445d4a2c1c181ef261c95bfdb05b46f1a9c8c5f953629fc0c.jpg)  

# FIGURE 9.8  

(a) Barrier option example. (b) Vanilla call and knock-in call.  

the formula for $J(t)$ becomes  

$$
J(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

That is to say, the value of $C^{b}(t)$ is zero:  

$$
C^{b}(t)=C(t)-C(t)
$$  

This characterization of a barrier option as a standard option plus or minus a discount term is. very useful from a financial engineering angle. In the next chapter, we will obtain some simple contractual equations for barriers, and the use of discounts will then be useful for obtaining. Black-Scholes type formulas for other types of barriers..  

![](images/a6d91db10974417882745c4530de37d45b1626c8cbd7118e7ac5890ce7510418.jpg)  

# FIGURE 9.8  

(Continued)  

# 9.5.4 USES OF BLACK-SCHOLES TYPE FORMULAS  

Obviously, the assumptions underlying the derivation of the Black-Scholes formula are quite restrictive. This becomes especially clear from the way we introduced options in this book. In particular, if options are used to bet on the direction of volatility, then how can the assumption of constant percentage volatility possibly be satisfied? This issue will be discussed further in later chapters where the way market professionals use the BlackScholes formula while trading volatility is clarified.  

When the underlying asset is an interest rate instrument or a foreign currency, some of the Black-Scholes assumptions become untenable.18 Yet, when these assumptions are relaxed, the logic used in deriving the Black-Scholes formula may not result in a PDE that can be solved for a closed-form formula.  

Hence, a market practitioner may want to use the Black-Scholes formula or variants of it, and then adjust the formula in some ad hoc, yet practical, ways. This may be preferable to trying to derive new complicated formulas that may accommodate more realistic assumptions. Also, even though the BlackScholes formula does not hold when the underlying assumptions change, acting as if the assumptions hold yields results that are surprisingly robust.19 We will see that this is. exactly what happens when traders adjust the volatility parameter depending on the "moneyness" of the option under consideration.  

This completes our brief discussion of the first set of tools that are essential for option analysis, namely Black-Scholes type closed-form formulas that give the arbitrage-free price of an option under some stringent conditions. Next, we discuss the second set of tools that traders and market makers routinely use: various sensitivity factors called the "Greeks."  
