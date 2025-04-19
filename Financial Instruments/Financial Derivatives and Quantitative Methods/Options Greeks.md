---
cssclasses: academia
title: Options Greeks
tags:
  - delta
  - gamma
  - greeks
  - options_greeks
  - rho
  - theta
  - vega
aliases:
  - Black-Scholes
  - Option Pricing
  - The Greeks
key_concepts:
  - Delta of option
  - Hedging risks
  - Option price changes
  - Risk management
  - Volatility smiles
---

# Options Greeks
# The Greeks

### Introduction

We have studied how to price an option using the Black-Scholes formula. Now we wish to consider how the option price changes,  either over time or as the parameters in the formula are changed. As the price of an option changes,  the risk of the option changes too. Therefore,  knowing how the option price changes enables the trader to hedge the risks of holding the option.

These notes will consider the various measures of how the option price changes. These measures are known as the Greeks,  as each of them is given a Greek letter. 1 We shall consider what these Greek letters measure and how they relate to each other. We shall also consider implied volatility and volatility smiles. We shall make use of the put-call parity condition for European options.

Keywords: Delta,  Gamma,  Rho,  Vega,  Theta,  Hedging,  Volatility smiles

### The Greeks

We have from the Black-Scholes formula that the price of a call option depends on the price of the underlying asset,  S,  the strike priceK,  the time to maturity,  T ,  the interest rate,  r,  and the volatility,  σ. Write this as a function $C=C (S,   K,   T,   r,   σ)$. Then using a first-order approximation,  we have

$$\begin{aligned}
C (S+\delta S,   K,   T+\delta T,   r+\delta r,   \sigma+\delta\sigma)& =C (S,   K,   T,   r,   \sigma) \\
&+\delta S\frac{\partial C}{\partial S}+\delta T\frac{\partial C}{\partial T}+\delta r\frac{\partial C}{\partial r}+\delta\sigma\frac{\partial C}{\partial\sigma}.
\end{aligned}$$

This shows the effect of varying each of the parameters,  $S,   T ， T_{0}$ by small amounts $\delta S$ $\delta T$ ， $\delta r$ and δσ,   but withK fixed. The same will be true for any option or portfolio of options. Thus,  if $Π=C (S,   T,   r,   σ)$ is the value of the option or portfolio of options,  then the value of the portfolio after a small change in the parameters is given by 3

$$\begin{aligned}
\Pi (S+\delta S,   K,   T+\delta T,   r+\delta r,   \sigma+\delta\sigma)& =\Pi (S,   K,   T,   r,   \sigma) \\
&+\delta S\frac{\partial\Pi}{\partial S}+\delta T\frac{\partial\Pi}{\partial T}+\delta r\frac{\partial\Pi}{\partial r}+\delta\sigma\frac{\partial\Pi}{\partial\sigma}.
\end{aligned}$$

Each of the partial effects is given a Greek letter.

Delta $\Delta$ = $\partial \Pi / \partial S$ . 
- $\Delta$ measures how the option price changes when the price of the underlying asset changes.
Theta $\Theta=-\partial\Pi/\partial T$ .
- $\Theta$ measures how the option price changes as the time to maturity decreases.
Rho $\rho=\partial\Pi/\partial r$.
-  $\rho$ measures how the option price changes as the interest rate changes.
Vega $v=\partial\Pi/\partial\sigma$ .
-  $V$ measures how the option price changes as the volatility changes.
There is also another Greek that measures how $\Delta$ changes as $S$ changes. This is known as Gamma.
Gamma $\Gamma$ = $\partial \Delta / \partial S$ = $\partial ^{2}\Pi / \partial S^{2}$.
-  $\Gamma$ measures the rate of change of the option's $\Delta$ as the price of the underlying changes.

We shall discuss each of these a little further.

### Delta

We have shown in the binomial model that holding a position that is $\Delta$ units long in the stock and short one call option,   we have a portfolio that is risk-free. The price of this portfolio is $\Pi (S,   K,   T,   r,   \sigma)=\Delta S-C (S,   K,   T,   r,   \sigma)$. The Delta of the portfolio is therefore

$$\Delta_{\Pi}=\frac{\partial\Pi}{\partial S}=\Delta-\frac{\partial C}{\partial S}=\Delta-\Delta_{C}$$

Where $\Delta_{C}$ is the Delta of the call option. If the portfolio is risk-free,   it will not depend on $S$ and hence $\Delta_{\Pi}=0$. Such a portfolio is said to be delta neutral. It therefore follows that $\Delta_{C}=\Delta$. That is,   the $\Delta$ we calculate in replicating the option or creating a risk-neutral portfolio is the Delta of the option itself.

This gives a convenient method for finding $\Delta$ from the Black-Scholes formula. Let's take the Black-Scholes formula:

$$C (S,   K,   T,   r,   \sigma)=SN (d_1)-e^{-rT}KN (d_2)$$

Where

$$\begin{array}{rcl}d_1&=&\frac{\ln (\frac{S}{K})+(r+\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\\\\d_2&=&d_1-\sigma\sqrt{T}=\frac{\ln (\frac{S}{K})+(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\end{array}$$

We wish to find $\partial C/\partial S$,   where we have to remember that both $d_{1}$ and $d_{2}$ depend on $S$. To find $\Delta$,   we first note that the call price has the property:

That if we double the strike $K$ and double the price of the underlying $S$,   the call price doubles. This is exactly what we should expect. If we change the currency denomination of the asset from pounds to dollars and there are two dollars per pound,   then the strike price and the price of the underlying should double,   and the call price should also be double. A function with this property is said to be linearly homogeneous in $S$ and $K$. More generally,   this means that

$$\lambda C (S,   K,   T,   r,   \sigma)=C (\lambda S,   \lambda K,   T,   r,   \sigma)$$

For any $\lambda>0$. It therefore follows from Euler's Theorem that

$$C (S,   K,   T,   r,   \sigma)=S\frac{\partial C}{\partial S}+K\frac{\partial C}{\partial K}.$$

Since the Black-Scholes formula has the form $C ( S,   K,   T,   r,   \sigma) =SxKy$ where $x=N (d_{1})$ and $y=e^{-rT}N (d_{2})$. This therefore implies that $\partial C/\partial S =N (d_{1})$ and $(\partial C/\partial K = -e^{-rT^{\prime}}N (d_{2}))$ and therefore that $\Delta=N (d_{1})$.

Question: Give an interpretation for $\partial C/\partial K$ \[Hint: Consider the effect of a one-unit increase in the strike price on the profitability of holding the option.

Notice that since $\Delta =N ( d_{1})$ ， 0 $\leq$ $\Delta$ $\leq$ 1 as $N (d_{1})$ is a cumulative probability. This is again what we should expect. The $\Delta$ tells us how much of the underlying asset to buy to replicate the option. Only if we know for sure that the option will be exercised will we replicate it by buying the underlying asset. If there is some possibility that the option will not be exercised then we only need to buy a fraction of the underlying asset (whilst partly borrowing in order to pay for the asset).

Question: What is the $\Delta$ of a forward contract? \[Hint: The forward contract has a value of $S-Ke^{-rT}$

It is important to remember that $\Delta$ changes (with $S$ and $T$ ) and therefore a portfolio that replicates the call will change over time and as the time to

Maturity gets closer. The appropriate replicating portfolio or hedge thus changes over time. This is known as rebalancing,   and the strategy of keeping a delta-neutral portfolio is known as dynamic delta-hedging.

The $\Delta$ of a put option can easily be calculated from the put-call parity conditions for European options:

$$C=P+(S-Ke^{-rT}).$$

Differentiating the above equation with respect to $S$

$$\Delta_C=\Delta_P+1$$

Where $\Delta_{C}=\partial C/\partial S$ and $\Delta_{P}=\partial P/\partial S$. Thus

$$\Delta_P=\Delta_C-1=N (d_1)-1.$$

The $\Delta$ of the put option is negative (-1 $\leq$ $\Delta _{P}$ $\leq$ 0). Indicating that to replicate the put option,   we must short-sell the underlying asset or to hedge a long position in the option,   we buy the underlying asset.

Question: How would you hedge a long position in the forward contract? What is the $\Delta$ of a forward contract?

## Theta

Theta measures how the option price changes as the time to maturity approaches. With some differentiation and manipulation,   it can be shown that

$$\Theta_C=-\frac{\partial C}{\partial T}=-\frac{SN' (d_1)\sigma}{2\sqrt{T}}-rKe^{-rT}N (d_2).$$

This shows that $\Theta_{C}<0$. That is,   the price of the option declines as maturity approaches or that longer-dated options are more valuable. We know that

This is true for American options because the longer-dated options give all the opportunities for profit as the earlier-dated options and more besides. The same applies for European options (on non-dividend-paying stocks) because the early exercise of an American call option is never optimal and therefore European and American call options are equivalent. To see that early exercise is not optimal,   consider again the put-call parity condition $C=P+(S-$ $Ke^{-rT}$ ). Since the put option is a limited liability asset,   its price must be non-negative. Hence $P\geq 0$ and therefore $C\geq S-Ke^{-rT}$ .Thus a lower bound for the call price is $C$ $\geq$ $\operatorname* { max} \{ 0,   SKe^{r^{\prime }T}\}$ .Now if $r>0$ this means $C>S-K$ .Since the American option cannot be worth less than the equivalent European option,   we therefore also have $C^{A}>S-K^{6}$ and hence it will always be better to sell the option rather than exercise it early. Thus American and European options on non-dividend-paying stock are equivalent.

The situation is slightly different for European put options. From differentiating the put-call parity condition with respect to $T$,   we get

$$-\Theta_C=-\Theta_P+rKe^{-rT}.$$

Hence

$$\Theta_{P}=-\frac{\partial C}{\partial T}=-\frac{SN' (d_{1})\sigma}{2\sqrt{T}}-rKe^{-rT}N (d_{2})+rKe^{rT}$$

Which may be of either sign. The same argument applies as for a call option. The longer-dated option will in general be more valuable. However,   for an American put option,   early exercise may be optimal. This is because by exercising early,   the investor gets the strike price earlier. In the extreme case where the option is deep-in-the money and the stock price is close to zero,   then there is little chance of falling lower. As there may be some chance of it increasing,   it may be optimal to exercise early and get the maximum gain at an earlier point in time. TThus,   an American put option will be worth more than a European option.

than a European put option. It should be reThus,  ered that $\Theta$ should not really be negative,   the way $\Delta$ is a European put option may in some cases be positive.

It should be remembered that $\Theta$ should not really be considered a hedge parameter in the way $\Delta$ is a hedge parameter for $S$. There is no uncertainty about the approach of the expiration date and hence no risk against which to hedge. Nevertheless,   $\Theta$ is related to another hedge parameter,   Gamma,   and therefore it is information that is normally tracked by traders.

### Gamma

Gamma measures how much $\Delta$ changes as the price of the underlying asset S changes and thus provides information about the appropriate dynamic hedging strategy and how $\Delta$ should be changed as S changes. If $\Gamma$ is large,   then it will be necessary to change $\Delta$ by a large amount asS changes. In this case,   it will be risky to leave $\Delta$ unchanging even over shorter periods. On the other hand,   if $\Gamma$ is small,   then the costs of leaving $\Delta$ unchanged will be relatively small. Often,   traders wish to create a portfolio which is gamma. Neutral as well as delta-neutral. The reason for this is that it may not be feasible or desirable to change $\Delta$ continuously to keep a completely delta-neutral portfolio,   and hence a gamma-neutral portfolio will mean that the costs of not keeping the portfolio completely delta-neutral will be minimised. It is important to realise,   however,   that a gamma-neutral portfolio cannot be achieved by using only the underlying asset (or a forward contract) since the Gamma of the underlying asset is zero. Thus,   suppose that the delta-neutral portfolio has a Gamma of $\Gamma_{x}$ and that there is another traded option that has a gamma of $\Gamma_{y}$ . Then selling $\Gamma_{x}/\Gamma_{y}$ of the traded options will create a new portfolio that is gamma-neutral.

Given that for a call option $\Delta=N (d_{1})$ and $\Gamma$ = $\partial \Delta / \partial S$,   it is easy to calculate that the Gamma for a call option is

$$\Gamma_C=\frac{N' (d_1)}{S\sigma\sqrt{T}}$$

Where $d_{1}$ is as given above and $N^{\prime }( d)$ = $( e^{d^{2}/ 2}) / \sqrt {2\pi }$ .Since $N^{\prime}(d)>0$ we have that $\Gamma_{C}>0$ which shows that the call price is a convex function of the price of the underlying asset. Since $\Delta_{P}=\Delta_{C}-1$ from the put-call parity condition,   we have by differentiating that

$$\Gamma_P=\Gamma_C$$

So that the Gamma of a put and an equivalent call are the same.

We can see the relationship between $\Delta$ ， $\Theta$ and $\Gamma$ from the Black-ScholesMerton Partial Differential Equation. This states that the price $C^{r}$ of any option or portfolio of options satisfies.

$$C=\frac{1}{r}\left\{\left (\frac{\partial C}{\partial T}+rS\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 C}{\partial S}\right)\right\}$$

Which can be re-written as

$$C=\frac{1}{r}\left\{\left ((-\Theta+rS\Delta+\frac{1}{2}\sigma^2\Gamma\right)\right\}.$$

This equation can be used for calculating one of $\Theta$ ， $\Gamma$ and $\Delta$ if the other two are known. Also it follows directly from this equation that any portfolio which is delta-neutral and gamma-neutral is also theta-neutral

## Vega

Vega measures how the option price changes as volatility changes. The Vega of a call option is given by

$$v_C=S\sqrt{T}N' (d_1).$$

Also from the put-call parity condition,   we have that $UC=UP$. It is important to understand why Vega is studied. In the Black-Scholes model,   volatility is assumed to be constant. Thus,   it makes much less sense to consider how the Black-Scholes formula changes in response to a change in volatility than to a change in the underlying price. However,   the relevant volatility for calculating the option price is the volatility of the underlying asset over the lifetime of the option. This is a future volatility,   which is not observable. It can be seen that the Vega of a call or put option is positive? And so ,   from this,   it is possible to use the known market price of the option to impute the volatility. This is known as the implied volatility. It is therefore possible to use market prices to calculate implied volatility. More on this later.

## [[Options Greeks#Options Gree Rho|Rho]]
Rho measures the sensitivity of the option price with respect to the interest rate. As with the volatility,   an assumption of the Black-Scholes model is that interest rates are constant over the life of the option. For a call option,   it can be shown that

$$\rho_C=KTe^{-rT}N (d_2)$$

Which is non-negative. This is because a rise in the interest rate reduces the present value of the strike price to be paid out if the option is exercised,   and this will raise the option price. From the put-call parity condition $C=$ $P+(S-Ke^{-rT})$,   we get

$$\rho_C=\rho_P+KTe^{-rT}$$

So that

$$\rho_P=KTe^{-rT}(N (d_2)-1)=-KTe^{-rT}N (-d_2)$$

Which is non-positive. This is because as the interest rate rises,   the present value of the strike price received at expiration,   if the option is exercised,   declines,   reducing the price of the put.

## Volatility

### Implied volatility and volatility smiles

As we have discussed,   the volatility that is required to calculate the Black-Scholes formula is a future volatility which is in principle unknown. It may be calculated on the basis of historic volatility,   but this may not be an accurate reflection of future volatility. It is therefore common to take the market prices for options and calculate the volatility which,   if used in the Black-Scholes formula,   would give the market price. This can be done as Vega is positive so that no two different volatilities can imply the same price.

If the Black-Scholes formula were correct,   then all similarly dated options on the same underlying should have the same implied volatility. If,   however,   the implied volatility is calculated and plotted against the strike price,   then there is typically a U-shaped pattern with the bottom of the U near the at-the-money strike price. Such a pattern is known as a volatility smile. Given that Vega is positive,   one might imagine that this implies some arbitrage opportunity. Either the low volatility options are underpriced or the higher volatility options are overpriced,   and one can buy the low volatility options and sell the high volatility options to yield a profit. However,   these smiles appear to persist,   so the arbitrage opportunity is probably more apparent than real.

The smile is more an expression of the market’s view of the imperfections of the Black-Scholes model itself. The two main imperfections are first the assumption that the underlying prices follow geometric Brownian motion and

So are lognormally distributed and second that the dynamic hedging which requires continuous adjustment can be carried out without cost.

## Fat tails,   jumps,   and stochastic volatility

The assumption of geometric Brownian motion matches the data well but not perfectly. When one compares actual data to that expected,   one finds that actual data exhibits kurtosis. This means that the tails are fatter or thicker than expected and the distribution is more highly peaked at the centre.

One way of modelling fat tails is to assume that volatility is itself stochastic and itself follows something like a geometric Brownian motion process. Another approach is to assume that volatility is a function of changes in the stock price so that big changes increase volatility.

Another approach is to consider processes that allow for jumps at some discrete points. The jumps themselves follow a Poisson process and this is added to the continuous Brownian motion process for the stock return. These mixed models are known as jump-diffusion processes.

These alternatives for the Black-Scholes model are not universally better. Which model fits better will depend on the market being studied. Thus,   jumps in stock prices are quite common but are less common in foreign exchange markets. This leaves much open for analysis and future work,   and most trading banks will have teams of analysts working on exactly this. They will typically be using discrete and numerical methods as well as mathematical models. This,   of course,   also makes a topic for dissertation work.

### Conclusion

We have discussed what is meant by the Delta,   Theta,   Gamma,   Rho,   and Vega of an option. We have considered the relationship between $\Theta$ ， $\Delta$ and Γ for an option or portfolio of options. We have also discussed how to impute volatility from knowledge of market prices and the empirical phenomenon of volatility smiles and how these might be accounted for by stochastic modelling of volatility.