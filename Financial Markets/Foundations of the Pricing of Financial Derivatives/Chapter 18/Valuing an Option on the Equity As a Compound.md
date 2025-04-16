---
tags:
  - '#call_on_call_option'
  - '#compound_option_valuation'
  - '#european_options'
  - '#hedge_portfolio'
  - '#ito_lemma'
  - '#option_pricing_model'
  - '#partial_differential_equation'
  - '#risk_free_rate'
---
# 18.2 VALUING AN OPTION ON THE EQUITY AS A COMPOUND OPTION

In valuing compound options, we must first recognize that there are calls on calls, calls on puts, puts on calls, and puts on puts. In addition, these options can be either European or American, and they can be mixed, as for example, an American call on a European put. We will use the simple notation $c c,c p,p c$ and $\mathbf{\Delta}p p$ to denote the price of a European call or put on a European call or put. We would use an uppercase $c$ or $p$ if either option is American, but we will not cover American options here.3

Now suppose there is a call option on the stock expiring at $T_{1}$ with an exercise price. of $X_{C}$ . Viewing stock as an option on the firm means the call option on the stock can be viewed as a compound option, specifically, a call on a call described in much more detail later. We denote this call on a call price as cc. Let this compound call expire before the debt matures $(T_{2})$ ; therefore,. $T_{1}<T_{2}$ . Let us now derive the value of this compound call option in terms of the underlying asset, $V_{t}$ , the value of the firm. We construct a hedge portfolio by purchasing $n_{1}$ units of the asset and $n_{2}$ compound call options. The value of this portfolio is initially4

$$
\begin{array}{r}{H_{t}=n_{1}V_{t}+n_{2}c c_{t}.}\end{array}
$$

We shall now temporarily drop the. $t$ subscript for notational simplification. We know that. the change in the value of this portfolio is given by the total differential,

$$
d H={\frac{\partial H}{\partial V}}d V+{\frac{\partial H}{\partial c c}}d c c.
$$

And note that dcc is the differential of the compound call price, cc. From Equation (18.3), we know that

$$
\begin{array}{l}{\displaystyle\frac{\partial H}{\partial V}=n_{1}}\ {\displaystyle\frac{\partial H}{\partial c c}=n_{2}.}\end{array}
$$

Thus, the change in the value of the hedge portfolio is

$$
d H=n_{1}d V+n_{2}d c c.
$$

Because the price of the option is a function of $V$ and $t$ , Ito's lemma permits us to express the change in the call price as

$$
d c c=\frac{\partial c c}{\partial t}d t+\frac{\partial c c}{\partial V}d V+\frac{1}{2}\frac{\partial^{2}c c}{\partial V^{2}}V^{2}\sigma_{V}^{2}d t.
$$

Now we substitute Equation (18.7) into the right-hand side of Equation (18.6). This gives

$$
d H=n_{1}d V+n_{2}{\frac{\partial c c}{\partial t}}d t+n_{2}{\frac{\partial c c}{\partial V}}d V+n_{2}{\frac{1}{2}}{\frac{\partial^{2}c c}{\partial V^{2}}}V^{2}\sigma_{\nu}^{2}d t.
$$

Because we are free to set $n_{1}$ and $n_{2}$ , then let $n_{1}=-n_{2}\left(\partial c c/\partial V\right)$ 5 Substituting into Equation (18.8) gives

$$
d H=n_{2}\frac{\partial c c}{\partial t}d t+n_{2}\frac{1}{2}\frac{\partial^{2}c c}{\partial V^{2}}V^{2}\sigma_{V}^{2}d t.
$$

This expression has no stochastic terms, so it is risk free. Therefore, the value of the hedge portfolio, $H.$ , should grow at the risk-free rate. Thus, we specify that.

$$
d H=H r_{c}d t.
$$

Substituting from Equation (18.3) for $H$ and $-n_{2}\left(\partial c c/\partial V\right)$ for $n_{1}$ , we obtain

$$
n_{2}{\frac{\partial c c}{\partial t}}d t+n_{2}{\frac{1}{2}}{\frac{\partial^{2}c c}{\partial V^{2}}}V^{2}\sigma_{V}^{2}d t=-n_{2}{\frac{\partial c c}{\partial V}}V r_{c}d t+n_{2}c c r_{c}d t.
$$

Dividing by $n_{2}$ and $d t$ gives

$$
c c r_{c}=\frac{\partial c c}{\partial V}V r_{c}+\frac{\partial c c}{\partial t}+\frac{1}{2}\frac{\partial^{2}c c}{\partial V^{2}}V^{2}\sigma_{V}^{2},
$$

which appears to be the same partial differential equation we obtained for the standard European call option.6 Unfortunately, there are some complicating factors in finding the solution. The solution for the call on call price in terms of the firm's asset price, not the stock price, is more difficult because the call (modeled here as a call on call) will exercise or not at an intervening time based on the value of the stock (modeled as the underlying call in this case) relative to the underlying call exercise price, $X_{U}$ . The call is not simply worth $\operatorname*{max}\left(0,V_{T_{1}}-X_{C}\right).$ The call on call payoff is made at time $T_{1}$ and is $\operatorname*{max}\left(0,c_{T_{1}}-X_{C}\right).$ Note that the value of. $c_{T_{1}}$ depends on $S_{T_{1}}$ that is used to solve another partial differential equation because it is a standard European option expiring later at $T_{2}$

We now turn to compound option boundaries and parities before introducing the general compound option valuation model..
