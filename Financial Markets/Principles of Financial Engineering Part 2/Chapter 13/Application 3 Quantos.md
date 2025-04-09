# 13.4 APPLICATION 3: QUANTOS  

The first two examples of the application of the fundamental theorem shown thus far were essen-.   
tially numerical. The pricing of quanto contracts constitutes another application of the fundamental.   
theorem. This requires a conceptual discussion. It is a good example of how the techniques intro-.   
duced in Chapter 12 can be used in modeling. The section is also intended to complete the discussion of the financial engineering aspects of quantoed assets that we started in Chapter 10..  

A quantoed foreign asset makes future payoffs in the domestic currency at a known exchange rate. An exchange rate, $x_{t},$ is chosen at initiation, to settle the contract at time T. For example, using quantos, a dollar-based investor could benefit from the potential upside of a foreign stock market, while eliminating the implicit currency exposure to exchange rate movements.  

# 13.4.1 PRICING QUANTOS  

The following application of the fundamental theorem starts with pricing a quanto forward. Let $S_{t}^{*}$ be a foreign stock denominated in the foreign currency. Let. $x_{t}$ be the exchange rate defined as the number of domestic currency, per 1 unit of foreign currency. The fundamental theorem can be used with the domestic risk-neutral measure $\tilde{P}$ to obtain the time $t_{0}$ value of the forward contract:  

$$
V(t_{0})=e^{-r(T-t_{0})}E_{t_{0}}^{\tilde{P}}x_{t_{0}}\left[S_{T}^{*}-F_{t_{0}}\right]
$$  

$F_{t_{0}}$ is the time $T$ forward value of the foreign stock. It is measured in foreign currency. Setting the $V(t_{0})$ equal to zero gives the forward value. $F_{t_{0}}$  

$$
F_{t_{0}}=E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]
$$  

Thus, in order to calculate. $F_{t_{0}}$ we need to evaluate the expectation of the foreign currency denominated $S_{T}^{*}$ under the domestic risk-neutral measure. $\tilde{P}$  

$$
E_{t_{0}}^{\tilde{P}}[S_{T}^{*}].
$$  

The fact that the state prices, $Q^{i}$ , in the fundamental theorem are denominated in the domestic currency, whereas $S_{t}^{*}$ is denominated in the foreign currency, makes this a nontrivial exercise.  

But, if used judiciously, the fundamental theorem can still be exploited for obtaining the expectation in Eq. (13.101). To maintain continuity, we use the simple framework developed in Chapter 12. In particular, we assume that there are only two periods, $t_{0}$ and $T.$ with $n$ states of the world at time $T.$ The notation remains the same.  

Consider the matrix equation of the fundamental theorem for three assets. The first is the domestic savings account $B_{t}$ which starts at 1 dollar and earns the domestic annual rate. $r.$ The second is a foreign savings account,. $B_{t}^{*}$ which starts with 1 unit of the foreign currency and earns the. foreign interest rate $r^{*}$ . These interest rates are assumed to be constant. The foreign currency has. dollar value $x_{t0}$ at time $t_{0}$ Finally, we have the foreign stock, $S_{t_{0}}^{*}$  

Putting these into the matrix equation implied by the fundamental theorem we get  

$$
\left(\begin{array}{c}{{1}}\ {{x_{t_{0}}}}\ {{x_{t_{0}}S_{t_{0}}^{*}}}\end{array}\right)=\left(\begin{array}{c c c}{{1+r(T-t_{0})}}&{{\cdots}}&{{1+r(T-t_{0})}}\ {{x_{T}^{1}[1+r^{*}(T-t_{0})]}}&{{\cdots}}&{{x_{T}^{n}[1+r^{*}(T-t_{0})]}}\ {{x_{T}^{1}S_{T}^{*1}}}&{{\cdots}}&{{x_{T}^{n}S_{T}^{*n}}}\end{array}\right)\left(\begin{array}{c}{{Q^{1}}}\ {{\cdots}}\ {{\cdots}}\ {{\cdots}}\ {{Q^{k}}}\end{array}\right)
$$  

Here, $x_{T}^{i}$ and $S_{T}^{*i}$ have $i$ superscripts because their time $T$ value depends on the state that is realized at that time. This system involves domestic state prices, and therefore the value of the foreign stock $S_{t_{0}}^{*}$ is converted into domestic currency by multiplying with $x_{t_{0}}.~Q^{i},i=1,...,n$ are the state prices assumed to be known and positive.  

We start with two results that are obtained by the following methods shown in Chapter 12 Define the domestic risk-neutral measure. $\tilde{P}$ as  

$$
\tilde{p}_{i}=(1+r(T-t_{0}))Q^{i}
$$  

Then, from the third row of Eq. (13.102) we obtain the equality,  

$$
x_{t_{0}}S_{t_{0}}^{*}=\frac{1}{1+r(T-t_{0})}\sum_{i=1}^{n}x_{T}^{i}S_{T}^{*i}\tilde{p}_{i}
$$  

This means that  

$$
x_{t_{0}}S_{t_{0}}^{*}=\frac{1}{1+r(T-t_{0})}E_{t_{0}}^{\tilde{P}}[x_{T}S_{T}^{*}]
$$  

Using the second row of the system in Eq. (13.102), we obtain a similar equality for the exchange rate. After switching from $Q^{i}$ to the risk-neutral probabilities $\tilde{P}$  

$$
x_{t_{0}}=\frac{1+r^{*}(T-t_{0})}{1+r(T-t_{0})}E_{t_{0}}^{\tilde{P}}[x_{T}]
$$  

We use Eqs. (13.105) and (13.106) in calculating the desired quantity, $E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]$ .We know from elementary statistics that  

$$
\mathrm{Cov}(S_{T}^{*},x_{T})=E_{t_{0}}^{\tilde{P}}[S_{T}^{*}x_{T}]-E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]E_{t_{0}}^{\tilde{P}}[x_{T}]
$$  

Rearranging, we can write:  

$$
E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]=\frac{E_{t_{0}}^{\tilde{P}}[S_{T}^{*}x_{T}]-\mathrm{Cov}(S_{T}^{*},x_{T})}{E_{t_{0}}^{\tilde{P}}[x_{T}]}
$$  

We substitute in the numerator from Eq. (13.105) and in the denominator from Eq. (13.106) to obtain  

$$
E_{t_{0}}^{\tilde{P}}\big[S_{T}^{*}\big]=\frac{[1+r(T-t_{0})]x_{t_{0}}S_{t_{0}}^{*}-\mathrm{Cov}(S_{T}^{*},x_{T})}{x_{t_{0}}[(1+r(T-t_{0}))/(1+r*(T-t_{0}))]}
$$  

We prefer to write this in a different form using the correlation coefficient denoted by $\rho$ and the percentage annual volatilities of $x_{t}$ and $S_{t}^{*}$ denoted by $\sigma_{x},\sigma_{s},$ respectively. Let  

$$
\operatorname{Cov}(S_{T}^{*},x_{T})=\rho\sigma_{x}\sigma_{s}(x_{t_{0}}S_{t_{0}}^{*})(T-t_{0})
$$  

The expression in Eq. (13.109) becomes  

$$
E_{t_{0}}^{\tilde{P}}\big[S_{T}^{*}\big]=\frac{1+r^{*}(T-t_{0})}{1+r(T-t_{0})}[1+(r-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

We can approximate this as15  

$$
E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]\cong[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

This gives the foreign currency denominated price of the quanto forward in the domestic currency:  

$$
F_{t_{0}}\cong[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

The present value of this in domestic currency will be the spot value of the quanto:  

$$
V_{t_{0}}=x_{t_{0}}\frac{1}{1+r(T-t_{0})}[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

We can also write this relationship by reinterpreting the interest rates as continuously compounded rates:  

$$
V_{t_{0}}=e^{-r(T-t_{0})}e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})}x_{t_{0}}S_{t_{0}}^{*}
$$  

According to this expression, the value of the quanto feature depends on the sign of the correlation between exchange rate movements and the value of the foreign stock. If this correlation is positive, then the quanto feature is negatively priced. If the correlation is negative, the quanto feature has positive value.16 If the correlation is zero, the quanto feature has zero value.  

$$
{\frac{1}{1+z}}=1-z
$$  

for small z. In the approximation, we ignore all terms of order $(T-t_{0})^{2}$ and higher.   
16Suppose the correlation is positive. Then, when foreign stock's value goes up, in general, the foreign currency will. also go up. The quanto eliminates this opportunity from the point of view of a stockholder, and hence, has a negative value and the quantoed asset is cheaper.  

# 13.4.2 THE PDE APPROACH  

Our next example shows how the fundamental theorem can be used to obtain partial differential equations (PDE) for quanto instruments. The treatment will be in continuous time and is essentially. heuristic. Consider the same two-currency environment. The domestic and foreign savings deposits are denoted by $B_{t}$ and $B_{t}^{*}$ , respectively. The corresponding continuously compounded rates are assumed to be constant, for simplicity, at $r$ and $r^{*}$ . This means that the savings account values increase incrementally according to the following (ordinary) differential equations:.  

$$
\begin{array}{r}{\mathrm{d}B_{t}=r B_{t}\mathrm{d}t\quad t\in[0,\infty)}\ {\mathrm{d}B_{t}^{*}=r^{*}B_{t}^{*}\mathrm{d}t\quad t\in[0,\infty)}\end{array}
$$  

Let $x_{t}$ be the exchange rate expressed as the domestic currency price of 1 unit of foreign currency. $x_{t}$ satisfies the SDE:  

$$
\mathrm{d}x_{t}=\upmu_{x}x_{t}\mathrm{d}t+\sigma_{x}x_{t}\mathrm{d}W_{1t}\quad t\in[0,\infty)
$$  

under the appropriate Martingale measure.  

First we obtain the exchange rate dynamics under the $B_{t}$ normalization. Note that $B_{t}^{*}$ is a traded asset and its price in domestic currency is $x_{t}B_{t}^{*}$ . According to the results obtained in Chapter 12, with $B_{t}$ normalization, and the corresponding risk-neutral measure $\tilde{P}$ , the ratio  

$$
\frac{x_{t}B_{t}^{*}}{B_{t}}
$$  

should behave as a Martingale. This means that the drift of the implied dynamics should be zero. Taking total derivatives,17  

$$
E_{t}^{\tilde{P}}\left[\mathrm{d}\frac{x_{t}B_{t}^{*}}{B_{t}}\right]=E_{t}^{\tilde{P}}\left[\frac{B_{t}^{*}}{B_{t}}\mathrm{d}x_{t}+\frac{x_{t}}{B_{t}}\mathrm{d}B_{t}^{*}-\frac{x_{t}B_{t}^{*}}{B_{t}^{2}}\mathrm{d}B_{t}\right]=0
$$  

Replacing from Eqs. (13.116), (13.117), and (13.118), we obtain18  

$$
\frac{B_{t}^{*}}{B_{t}}\upmu_{x}x_{t}\mathrm{d}t+\frac{x_{t}}{B_{t}}r^{*}B_{t}^{*}\mathrm{d}t-\frac{x_{t}B_{t}^{*}}{B_{t}^{2}}r B_{t}\mathrm{d}t=\frac{x_{t}B_{t}^{*}}{B_{t}}\left[\upmu_{x}+r^{*}-r\right]\mathrm{d}t
$$  

In order for this drift to be zero, we must have, under $\tilde{P}$ , at all times:  

$$
\mu_{x}+r^{\ast}-r=0
$$  

Replacing this drift in Eq. (13.118) gives the exchange rate dynamics under the $\tilde{P}$  

$$
\mathrm{d}x_{t}=(r-r^{*})x_{t}\mathrm{d}t+\sigma_{x}x_{t}\mathrm{d}W_{1t}\quad t\in[0,\infty)
$$  

Next, consider the $\tilde{P}$ dynamics of the foreign stock $S_{t}^{*}$  

$$
\mathrm{d}S_{t}^{*}=\upmu_{s}S_{t}^{*}\mathrm{d}t+\sigma_{x}S_{t}^{*}\mathrm{d}W_{2t}\quad t\in[0,\infty)
$$  

Under the $B_{t}$ normalization, the domestic currency value of the foreign stock should behave as a Martingale. Applying Ito's Lemma:  

$$
E_{t}^{\Tilde{P}}\left[\mathrm{d}\frac{x_{t}S_{t}^{*}}{B_{t}}\right]=E_{t}^{\Tilde{P}}\left[\frac{S_{t}^{*}}{B_{t}}\mathrm{d}x_{t}+\frac{x_{t}}{B_{t}}\mathrm{d}S_{t}^{*}-\frac{x_{t}S_{t}^{*}}{B_{t}^{2}}\mathrm{d}B_{t}+\frac{\mathrm{d}x_{t}\mathrm{d}S_{t}^{*}}{B_{t}}\right]=0
$$  

Replacing the differentials and simplifying, we obtain  

$$
\begin{array}{l}{{\displaystyle{\frac{S_{t}^{*}}{B_{t}}}(r-r^{*})x_{t}+\frac{x_{t}}{B_{t}}\upmu_{s}S_{t}^{*}-\frac{x_{t}S_{t}^{*}}{B_{t}^{2}}r B_{t}+\frac{\rho\sigma_{x}\sigma_{s}x_{t}S_{t}^{*}}{B_{t}}}}\ {~}\ {{\displaystyle=\frac{x_{t}S_{t}^{*}}{B_{t}}\left[(r-r^{*})+\upmu_{s}-r+\rho\sigma_{x}\sigma_{s}\right]=0}}\end{array}
$$  

In order for this drift to be zero we must have, under $\tilde{P}$ , at all times:  

$$
\upmu_{S}=r^{*}-\rho\sigma_{x}\sigma_{s}
$$  

This gives the arbitrage-free stock price dynamics:  

$$
\mathrm{d}S_{t}^{*}=(r^{*}-\rho\sigma_{x}\sigma_{s})S_{t}^{*}\mathrm{d}t+\sigma_{x}S_{t}^{*}\mathrm{d}W_{2t}\quad t\in[0,\infty)
$$  

These dynamics imply that:  

$$
E_{t}^{\Tilde{P}}[S_{T}^{*}]=e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t)}S_{t}^{*}
$$  

as derived in the previous section. Here the interest rates $r$ and $r^{*}$ should be interpreted as continuously compounded rates. In the previous section, they were actuarial rates for the period $T-t_{0}$  

# 13.4.2.1 A PDE for quantos  

Finally, using these results we can obtain a PDE for an arbitrary quanto asset written on a risk associated with a foreign economy. Let this foreign currency denominated asset be denoted by $S_{t}^{*}$ . Let $V_{t}$ denote the time $t$ value of the quanto,  

$$
V(t)=x_{t}V(S_{t}^{*},~t)
$$  

$V(.)$ , being a pricing function of the asset, needs to be determined. $x_{t}$ is the initial exchange rate. written in the quanto contract and, hence,. $V(t)$ is expressed in domestic currency terms. Under. $B_{t}$ normalization, $V(t)$ should behave as a Martingale. Applying Ito's Lemma we obtain:19  

$$
E_{t}^{\tilde{P}}\bigg[\mathrm{d}\frac{V(t)}{B_{t}}\bigg]=E_{t}^{\tilde{P}}\bigg[\frac{V_{t}}{B_{t}}\mathrm{d}t+\frac{V_{s}}{B_{t}}\mathrm{d}S_{t}^{*}-\frac{V}{B_{t}^{2}}\mathrm{d}B_{t}+\frac{1}{2}\frac{V_{s s}\sigma_{s}^{2}(S_{t}^{*})^{2}}{B_{t}}\mathrm{d}t\bigg]=0
$$  

Replacing the stochastic differentials and simplifying yields the implied PDE,  

$$
V_{t}+(r^{*}-\rho\sigma_{x}\sigma_{s})S_{t}^{*}V_{s}+\frac{1}{2}V_{S S}\sigma_{s}^{2}(S_{t}^{*})^{2}-r V=0
$$  

with the terminal condition:  

$$
V(T)=x_{t}V(S_{T}^{*},T)
$$  

We apply this PDE to two special cases.  

# 13.4.3 QUANT0 FORWARD  

Suppose we know that a quanto forward has the value,  

$$
V(t)=q(t)S_{t}^{*}
$$  

but that the time-dependent function $q(t)$ is unknown. The PDE derived in the previous section can be used to solve for $q(t)$ . Differentiating Eq. (13.134), we get the partial derivatives:  

$$
V_{t}=\frac{\partial\boldsymbol{q}(t)}{\partial t}S_{t}^{*}=\dot{\boldsymbol{q}}S_{t}^{*}
$$  

$$
V_{s}=q(t)
$$  

$$
V_{s s}=0
$$  

We replace these in the PDE for the quanto,  

$$
{\dot{q}}S_{t}^{\ast}+(r^{\ast}-\rho\sigma_{x}\sigma_{s})q(t)S_{t}^{\ast}-r q(t)S_{t}^{\ast}=0
$$  

with the terminal condition,  

$$
V(T)=x_{t}S_{T}^{*}
$$  

Eliminating the common $S_{t}^{*}$ terms, this ordinary differential equation can be solved for $q(t)$  

$$
q(t)=x_{t}e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t)}
$$  

This is the same result as obtained earlier.  

# 13.4.4 QUANTO 0PTION  

Suppose the payoff $V(T)$ of a quanto asset relates to the payoff of a European call on a foreign stock $S_{t}^{*}$  

$$
V_{T}=x_{t}\operatorname*{max}[S_{T}^{*}-K^{*},0]
$$  

Here $K^{*}$ is a foreign currency denominated strike price and. $T$ is the expiration date. Then the. PDE derived in Eq. (13.132) can be solved using the equivalence with the Black-Scholes formula to obtain the pricing equation for a European quanto call:.  

$$
C(t)=x_{t}\left[S_{t}^{*}e^{(r^{*}-r-\rho\sigma_{x}\sigma_{s})(T-t)}N(b_{1})-K^{*}e^{-r(T-t)}N(b_{2})\right]
$$  

where  

$$
b_{1}={\frac{(\ln S_{t}^{*}/K^{*})+(r^{*}-\rho\sigma_{x}\sigma_{s}+0.5\sigma_{s}^{2})(T-t)}{\sigma_{s}\sqrt{T-t}}}
$$  

$$
b_{2}=b_{1}-\sigma_{s}\sqrt{T-t}
$$  

The value of the call will be measured in domestic currency.  

# 13.4.4.1 Black-Scholes and dividends  

We now explain how to trick the PDE in Eq. (13.132) in order to arrive at the Black-Scholes type. formula for the simple quantoed equity option shown above. To do this, we need the equivalent of the Black-Scholes formula in the case of a constant rate of dividends paid by the underlying stock. during the life of the option..  

Standard derivations in the Black-Scholes world will give the European call premium on a stock, $S_{t}.$ that pays dividends at a constant rate $Q$ aS,  

$$
C(t)=e^{-Q(T-t)}S_{t}N(\tilde{d}_{1})-K e^{-(r)(T-t)}N(\tilde{d}_{2})
$$  

with  

$$
\tilde{d}_{1}=\frac{(\ln S_{t}/K)+(r-Q+0.5\sigma_{s}^{2})(T-t)}{\sigma_{s}\sqrt{T-t}}
$$  

$$
\tilde{d}_{s}=\tilde{d}_{1}-\sigma_{s}\sqrt{T-t}
$$  

where $S_{t}$ is the dividend paying stock.  

Now, note that we can write the PDE in Eq. (13.138) as  

$$
V_{t}+(r-Q)S_{t}^{*}V_{s}+\frac{1}{2}V_{s s}\sigma_{s}^{2}(S_{t}^{*})^{2}-r V=0
$$  

where $Q$ is treated as a dividend yield, and is given by  

$$
Q=r-r^{*}+\rho\sigma_{x}\sigma_{s}
$$  

We can then use this $Q$ in the standard Black--Scholes formula with a known dividend yield to get the quantoed call premium.  

# 13.4.5 HOW TO HEDGE QUANTOS  

Quanto contracts require dynamic hedging. The dealer would form a portfolio made of the underlying foreign asset, the foreign currency (or, better, an FX-forward), and the domestic lending and borrowing. The weights of this portfolio would be adjusted dynamically, so that the portfolio replicates the changes in value of the quanto contract. The trading gains (losses) realized from these hedge adjustments form the basis for the quanto premium or discount.  

# 13.4.6 REAL-LIFE CONSIDERATIONS  

The discussion of quantoed assets in this section has been in a simple, abstract, and unrealistic world. We used the following assumptions, among others: (i) the underlying processes were assumed to be lognormal, so that the implied SDEs were geometric. (ii) The correlation coefficient and the volatility parameters were assumed to be constant during the life of the option. (iii) Similarly, interest rates were assumed to be constant, although the corresponding exchange rate was stochastic.  

These assumptions are not satisfied in most real-world applications. Especially important for quantos, the correlation coefficients between exchange rates and various risk factors are known to be quite unstable. The models discussed in this section therefore need to be regarded as a conceptual application of the fundamental theorem. They do not provide an algorithm for pricing real-world quantos.  
