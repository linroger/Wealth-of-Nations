# 11.6 REAL-WORLD COMPLICATIONS  

Actual implementation of the synthetic payoff structures discussed in this chapter requires dealing with several real-world imperfections. First of all, it must be remembered that these positions are shown at expiration, and that they are piecewise linear. In real life, payoff diagrams may contain sev-. eral convexities, which is an equivalent term for nonlinear payoffs. We will review these briefly..  

# 11.6.1 THE ROLE OF THE VOLATILITY SMILE  

The existence of volatility smile has especially strong effects on pricing and hedging of exotic options. If a volatility smile exists, the implied volatility becomes a function of the strike price. $K.$ For example, the expression that gave the binary option price in Eqs. (11.30)-(11.31) has to be modified to  

$$
\begin{array}{l}{{\displaystyle{\cal C}^{\mathrm{bin}}(t)=\operatorname*{lim}_{h\rightarrow0}\frac{{\cal C}^{K}(t)-{\cal C}^{K+h}(t)}{h}}~}\ {{\displaystyle~=\frac{\partial{\cal C}^{K}(t)}{\partial K}+\frac{\partial{\cal C}^{K}(t)}{\partial\sigma(K)}\frac{\partial\sigma(K)}{\partial(K)}}}\end{array}
$$  

The resulting formula and the analogy to plain vanilla deltas will change. These types of modi-. fications have to be applied to hedging and synthetically creating barrier options as well. Major modification will also be needed for barrier options.  

# 11.6.2 EXISTENCE OF POSITION LIMITS  

At time $t$ before expiration, an option's value depends on many variables other than the underlying $x_{t}$ . The volatility of $x_{t}$ and the risk-free interest rate $r_{t}$ are two random variables that affect all the positions discussed for $t<T.$ This is expressed in the Black-Scholes formula for the call premium of $t<T$  

$$
C_{t}=C(\boldsymbol{x}_{t},t|\sigma,r)
$$  

which is a function of the "parameters" $r,\sigma$ At $t=T$ this formula reduces to.  

$$
C_{T}=\operatorname*{max}[x_{T}-K,0]
$$  

Now, if the. $r$ and $\sigma$ are stochastic, then during the. $t\in[0,T)$ , the positions considered here will be subject to vega and rho risks as well. A player who is subject to limits on how much of these risks he or she can take, may have to unwind the position before $T.$ This is especially true for positions that have vega risk. The existence of limits will change the setup of the problem since, until now, sensitivities with respect to the $r$ and $\sigma$ parameters, did not enter the decision to take and maintain the positions discussed.  
