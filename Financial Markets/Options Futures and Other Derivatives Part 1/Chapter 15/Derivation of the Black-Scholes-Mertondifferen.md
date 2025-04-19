---
tags:
  - '#arbitrage_opportunities'
  - '#black_scholes_merton_equation'
  - '#boundary_conditions'
  - '#derivative_pricing'
  - '#european_options'
  - '#forward_contract'
  - '#perpetual_derivative'
  - '#risk_free_interest_rate'
---
# 15.6 DERIVATION OF THE BLACK-SCHOLES-MERTONDIFFERENTIAL EQUATION  

In this section, the notation is different from elsewhere in the book. We consider a derivative's price at a general time $t$ (not at time zero). If $T$ is the maturity date, the time to maturity is $T-t$  

The stock price process we are assuming is the one we developed in Section 14.3:  

$$
d S=\mu S d t+\sigma S d z
$$  

Suppose that. $f$ is the price of a call option or other derivative contingent on $S$ Thee variable $f$ must be some function of. $S$ and $t.$ Hence, from equation (14.14),  

$$
d f=\left({\frac{\partial f}{\partial S}}\mu S+{\frac{\partial f}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}\sigma^{2}S^{2}\right)d t+{\frac{\partial f}{\partial S}}\sigma S d z
$$  

The discrete versions of equations (15.8) and (15.9) are  

$$
\Delta S=\mu S\Delta t+\sigma S\Delta z
$$  

and  

$$
\Delta f=\left({\frac{\partial f}{\partial S}}\mu S+{\frac{\partial f}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial S^{2}}}\sigma^{2}S^{2}\right)\Delta t+{\frac{\partial f}{\partial S}}\sigma S\Delta z
$$  

where $\Delta f$ and $\Delta S$ are the changes in $f$ and $S$ in a small time interval $\Delta t$ Recall from the discussion of Ito's lemma in Section 14.6 that the Wiener processes underlying $f$ and $S$ are the same. In other words, the $\Delta z(=\epsilon\sqrt{\Delta t})$ in equations (15.10) and (15.11) are the same. It follows that a portfolio of the stock and the derivative can be constructed so that the Wiener process is eliminated. The portfolio is  

$-1$ : derivative $+\partial f/\partial S$ : shares.  

The holder of this portfolio is short one derivative and long an amount $\partial f/\partial S$ of shares. Define $\Pi$ as the value of the portfolio. By definition  

$$
\Pi=-f+\frac{\partial f}{\partial S}S
$$  

The change $\Delta\Pi$ in the value of the portfolio in the time interval $\Delta t$ is given by  

$$
\Delta\Pi=-\Delta f+\frac{\partial f}{\partial S}\Delta S
$$  

Substituting equations (15.10) and (15.11) into equation (15.13) yields  

$$
\Delta\Pi=\left(-\frac{\partial f}{\partial t}-\frac{1}{2}\frac{\partial^{2}f}{\partial S^{2}}\pmb{\sigma}^{2}S^{2}\right)\Delta t
$$  

Because this equation does not involve. $\Delta z$ , the portfolio must be riskless during time. $\Delta t$ The assumptions listed in the preceding section imply that the portfolio must instant-. aneously earn the same rate of return as other short-term risk-free securities. If it earned more than this return, arbitrageurs could make a riskless profit by borrowing money to buy the portfolio; if it earned less, they could make a riskless profit by shorting the. portfolio and buying risk-free securities. It follows that.  

$$
\Delta\Pi=r\Pi\Delta t
$$  

where $r$ is the risk-free interest rate. Substituting from equations (15.12) and (15.14) into (15.15), we obtain  

$$
\left(\frac{\partial f}{\partial t}+\frac{1}{2}\frac{\partial^{2}f}{\partial S^{2}}\sigma^{2}S^{2}\right)\Delta t=r\bigg(f-\frac{\partial f}{\partial S}S\bigg)\Delta t
$$  

so that  

$$
{\frac{\partial f}{\partial t}}+r S{\frac{\partial f}{\partial S}}+\frac{1}{2}\sigma^{2}S^{2}{\frac{\partial^{2}f}{\partial S^{2}}}=r f
$$  

Equation (15.16) is the Black-Scholes-Merton differential equation. It has many solutions, corresponding to all the different derivatives that can be defined with $S$ as the underlying variable. The particular derivative that is obtained when the equation is solved depends on the boundary conditions that are used. These specify the values of the derivative at the boundaries of possible values of $S$ and $t.$ In the case of a European call option, the key boundary condition is  

$$
f=\operatorname*{max}(S-K,0)\quad\mathrm{when}t=T
$$  

In the case of a European put option, it is  

$$
f=\operatorname*{max}(K-S,0)\quad\mathrm{when}t=T
$$  

# Example 15.5  

A forward contract on a non-dividend-paying stock is a derivative dependent on the stock. As such, it should satisfy equation (15.16). From equation (5.5), we know that the value of the forward contract,. $f,$ at a general time $t$ is given in terms of the stock price $S$ at this time by  

$$
f=S-K e^{-r(T-t)}
$$  

where $K$ is the delivery price. This means that  

$$
\ensuremath{\frac{\partial f}{\partial t}}=-r K e^{-r(T-t)},\qquad\ensuremath{\frac{\partial f}{\partial S}}=1,\qquad\ensuremath{\frac{\partial^{2}f}{\partial S^{2}}}=0
$$  

When these are substituted into the left-hand side of equation (15.16), we obtain  

$$
-r K e^{-r(T-t)}+r S
$$  

This equals $r f_{:}$ showing that equation (15.16) is indeed satisfied.  

# A Perpetual Derivative  

Consider a perpetual derivative that pays off a fixed amount. $Q$ when the stock price. equals $H$ for the first time. In this case, the value of the derivative for a particular $S$ has no dependence on. $t$ so the $\partial f/\partial t$ term vanishes and the partial differential equation (15.16) becomes an ordinary differential equation..  

Suppose first that $S<H.$ The boundary conditions for the derivative are. $f=0$ when $S=0$ and $f=Q$ when $S=H$ The simple solution $f=Q S/H$ satisfies both the boundary conditions and the differential equation. It must therefore be the value of the derivative.  

Suppose next that $S>H,$ The boundary conditions are now $f=0$ as $S$ tends to infinity and. $f=Q$ when. $S=H.$ The derivative price  

$$
f=Q{\biggl(}{\frac{S}{H}}{\biggr)}^{-\alpha}
$$  

where $\alpha$ is positive, satisfies the boundary conditions. It also satisfies the differential equation when  

$$
-r\alpha+{\textstyle\frac{1}{2}}\sigma^{2}\alpha(\alpha+1)-r=0
$$  

or $\alpha=2r/\sigma^{2}$ . The value of the derivative is therefore  

$$
f=Q\bigg(\frac{S}{H}\bigg)^{-2r/\sigma^{2}}
$$  

Problem 15.31 shows how equation (15.17) can be used to price a perpetual American put option. Section 26.2 extends the analysis to show how perpetual American call and put options can be priced when the underlying asset provides a yield at rate. $q$  

# The Prices of Tradeable Derivatives  

Any function $f(S,t)$ that is a solution of the differential equation (15.16) is the theoretical price of a derivative that could be traded. If a derivative with that price existed, it would not create any arbitrage opportunities. Conversely, if a function $f(S,t)$ does not satisfy the differential equation (15.16), it cannot be the price of a derivative without creating arbitrage opportunities for traders.  

To illustrate this point, consider first the function $e^{S}$ . This does not satisfy the. differential equation (15.16). It is therefore not a candidate for being the price of a derivative dependent on the stock price. If an instrument whose price was always $e^{S}$ existed, there would be an arbitrage opportunity. As a second example, consider the function $e^{(\sigma^{2}-2r)(T-t)}/S.$ This does satisfy the differential equation, and so is, in theory, the. price of a tradeable security. (It is the price of a derivative that pays off $1/S_{T}$ at time $T.$ For other examples of tradeable derivatives, see Problems 15.19, 15.20, and 15.31.  
