---
tags:
  - callable_leveraged_cms
  - cms_spread_note
  - interest_rate_risk
  - monte_carlo_simulation
  - swaption_volatility
aliases:
  - CMS Spread Note
  - Callable Note
  - Swap Spread Note
key_concepts:
  - CMS spread
  - Discount curve construction
  - Implied swaption volatility
  - Monte Carlo simulation
  - Stochastic cash flows
---

# Pricing a Callable Leveraged Constant Maturity Swap Spread Note
## Summary
A callable leveraged constant maturity swap (CMS) spread note allows the holder to benefit from future changes in the spread between two swap interest rates. The issuer retains the right to call the note at pre-specified times in the future. The note is priced via Monte Carlo simulation using the current term structure of interest rates and at-the-money implied swaption volatilities.
## 1 Mathematical Formulation
The note under consideration periodically pays the holder a multiple of the spread between two index swap rates at scheduled future dates. The issuer of the note may call the note at pre-specified future dates. For a period of time prior to the first reset date, the note pays a fixed coupon.
On a payment date, the holder receives an amount equal to
$$
\begin{array}{r l r}
B(t_{i}) &=& B_{\text{fixed}}(t_{i}) + B_{\text{float}}(t_{i})\;, \\
B_{\text{fixed}}(t_{i}) &=& c_{i} \Delta t_{i} P \delta(n_{r_{0}} - i)\;, \\
B_{\text{float}}(t_{i}) &=& \operatorname{max}\left\{0, \left[r(t_{i}, T_{\text{long}}) - r(t_{i}, T_{\text{short}})\right] \kappa \Delta t_{i}\right\} \left(1 - \delta(t_{c} - t_{i})\right) \\
&\times& \delta(i - n_{r_{0}}) + C \Delta t_{i} \left(\delta(t_{c} - t_{i-1}) - \delta(t_{c} - t_{i})\right)\,, \quad i = \overline{1,N}\;,(6) \\
\delta(\tau) &=& 
\begin{cases}
0, & \tau < 0, \quad \tau \in [t_{0}, T], \\
1, & \tau \geq 0, \quad \tau \in [t_{0}, T],
\end{cases}
\end{array}
$$
### Where:
- $t_{i}$ - payment date; $t_{i} \in [t_{0}; T = t_{N}]$
- $B_{\text{fixed}}(t_{i})$ - fixed portion of the note payout
- $B_{\text{float}}(t_{i})$ - variable ("floating") portion of the note payout
- $n_{r_{j}}$ - $j$-th note rate reset time, $j = \overline{0, J}$, $n_{r_{J}} \leq N-1$
- $c_{i}$ - note coupon rate at time $t_{i}$
- $P$ - note principal
- $\Delta t_{i} = t_{i} - t_{i-1}$, $i = \overline{1, N}$
- $T$ - note maturity
- $t_{0}$ - note effective date
- $r (t_{i}, T_{\text{long}})$ - quoted rate at $t_{i}$ with a tenor of $T_{\text{long}} - t_{i}$ that contributes positively to the payout
- $r (t_{i}, T_{\text{short}})$ - quoted rate at $t_{i}$ with a tenor of $T_{\text{short}} - t_{i}$ that contributes negatively to the payout
- $\kappa$ - leverage coefficient
- $C$ - redemption price at call time $t_{c}$
- $t_{c}$ - time the note is called, $t_{c} \in [t_{n_{c_{0}}}, t_{N-1}]$
The holder of a note described by $(1.1)-(1.4)$ effectively owns three separate instruments:
1. An interest-only fixed coupon note maturing at $t_{n_{r_{0}}}$,
2. A long cap on the swap spread $r (t_{i}, T_{\text{long}}) - r (t_{i}, T_{\text{short}})$ struck at zero and expiring at $t_{N-1}$,
3. A short Bermudan call on the note itself struck at $C$, exercisable on any of the call dates and expiring at $t_{N-1}$.
As a practical matter, we set the call dates to coincide with rate reset dates, i.e., $t_{c} \in \{ t_{n_{r_{0}}}, \dots, t_{n_{r_{J}}} \}$. The first instrument can be priced using the current discount curve. A combination of the second and third instruments can only be priced using a simulation technique (Monte Carlo) due to the complexity of the options and the correlation between the two underlying rates—the constituents of the spread.
## 2 Simulation Algorithm
The algorithm proceeds as follows:
1. **Construct a discount curve** (e.g., as described in [7]);
2. **Simulate the term structure of $r (t_{i}, T_{\text{long}})$, $i = \overline{n_{r_{0}}, N-1}$**, using the forward rate extracted from the discount curve as the expected rate and assuming a lognormal rate distribution described in [1];
3. **Construct an implied rate volatility surface** using at-the-money implied swaption volatilities as a proxy;
4. **Compute correlation coefficients** $\rho_{i}$ from the volatility surface constructed above;
5. **Simulate the term structure of $r (t_{i}, T_{\text{short}})$, $i = \overline{n_{r_{0}}, N-1}$**, using the forward rate implied by the discount curve and the correlation coefficients;
6. **Starting at maturity and going back to the first call date**, activate call provisions on any call date when the expected present value of future cash flows on that date exceeds the redemption price;
7. **Aggregate present values (PV) of all stochastic cash flows** over scenarios to obtain the expected PV of the variable portion of the note;
8. **Add the PV of all deterministic cash flows** (i.e., those occurring prior to the first reset date) to obtain the total PV of the note.
We will now explain each step of the algorithm in more detail.
### 2.1 Constructing the Discount Curve
The discount curve is constructed from:
1. Short-term rates (LIBOR) starting from the valuation date up until the first Eurodollar (ED) futures expiry date;
2. ED futures starting with the front contract expiration date up until the 2-year swap expiration date;
3. Quoted par swap rates from 2 to 50 years,
using the FINCAD function `aaSwap crv3` as described in [2] with the following conventions:
- Standard compounding,
- Day count and business day conventions,
- Loglinear interpolation on discount factors,
- Linear interpolation on swap rates,
- Spot rate splicing for futures.
### 2.2 Simulating the Term Structure of the Underlying Interest Rates
We assume that both underlying interest rates follow the Black-76 lognormal process [1]:
$$
r(t) = r(0) e^{\left\{ \left( \mu - \frac{1}{2} \sigma^{2} \right) t + \sigma \sqrt{t} \mathcal{N}(t) \right\}}\;,
$$
Where:
- $\mu$ - drift,
- $\sigma$ - interest rate volatility inferred from at-the-money implied swaption volatilities,
- $\mathcal{N}(t)$ - random standard normal variable.
A Mersenne Twister [6] with antithetic variance reduction [5] is a good choice for a random number generator.
### 2.3 Simulating Correlated Underlying Interest Rates
The correlation coefficient between the two underlying rates can be computed as follows:
$$
\rho(t; T_{\text{short}}, T_{\text{long}}) = \frac{\sigma_{t+T_{\text{short}}, t+T_{\text{long}}}^{2} - \alpha^{2} \sigma_{t, T_{\text{short}}}^{2} - \beta^{2} \sigma_{t, T_{\text{long}}}^{2}}{2 \alpha \beta \sigma_{t, T_{\text{short}}} \sigma_{t, T_{\text{long}}}} \;,
$$
Where
$$
\alpha = \frac{\sum_{i=1}^{N} d F(t, t_{i})}{\sum_{i=m+1}^{N} d F(t, t_{i})} \;,
$$
$$
\beta = 1 - \alpha \;,
$$
- $\sigma_{\tau_{1}, \tau_{2}}$ - implied volatility of the forward rate between times $\tau_{1}$ and $\tau_{2}$ inferred from at-the-money implied swaption volatilities,
- $d F (\tau_{1}, \tau_{2})$ - discount factor corresponding to time $\tau_{2}$ in effect at time $\tau_{1}$.
The derivation of these equations is presented in Appendix B. Armed with these equations, we can now generate correlated standard normal variates from uncorrelated draws:
$$
\mathcal{N}_{\text{short}} = \mathcal{N}_{1}\;,
$$
$$
\mathcal{N}_{\text{long}} = \rho(t; T_{\text{short}}, T_{\text{long}}) \mathcal{N}_{1} + \sqrt{1 - \rho(t; T_{\text{short}}, T_{\text{long}})^{2}} \mathcal{N}_{2}\;,
$$
Where $\mathcal{N}_{1}, \mathcal{N}_{2}$ are independent standard normal variates (see Appendix B for proof). We recycle these to generate another simulation with the opposite sign (control variates). Feeding the results into the rate simulation, we obtain the expected payouts of the variable portion of the note.
### 2.4 Simulating Note Calls
We assume that the issuer is a rational player, and the note will necessarily be called at time $t_{c}$ if the present value of all expected future cash flows (to the holder) at that time exceeds the sum of present values of the next coupon and redemption amount paid at the following call (rate reset) date. We utilize the generated term structure of the underlying rates as if they were actual realizations of interest rate paths. In our model, the issuer has a "perfect crystal ball" (i.e., is 100% accurate in predicting future interest rates). In reality, the uncertainty over future interest rates detracts from the value of the issuer’s call option, and the value of the note to the holder is higher.
The note cannot be called at time $T$. At time $t_{N-1}$, the note will be called if the PV at $t_{N-1}$ of the sum of the expected remaining coupon payment and the redemption amount exceeds the redemption amount. The coupon amount for each scenario is determined by the simulated spread computed for each point in time as described in Section 2.3. If the note is called, all subsequent cash flows are set to 0. Continuing this process backward to time $t_{0}$, we obtain the PV of the variable portion of the note for a single scenario. Aggregating over all scenarios, we arrive at the expected PV of the variable portion of the note.
### 2.5 Pricing the Fixed Portion of the Note
The present value of the fixed cash flows at time $t$ can be computed using standard bond arithmetic (see, e.g., [3]):
$$
B_{L}(t) = \sum_{l=1}^{L} c_{l} \Delta t_{l} P d F(t, t_{l})\;,
$$
Where $L$ is the number of fixed coupon payment dates and the rest of the notation is the same as in $(1.1)-(1.4)$ and $(2.2)-(2.4)$.
Adding the result of this equation to the PV of the variable note portion computed in Sections 2.3–2.4, we arrive at the PV of the whole note.
## 3 Example
We consider a note with a 10% annual coupon paid quarterly during the first year and a variable coupon based on 50 times the spread between the 30-year and 10-year USD swap rates thereafter, reset and paid quarterly. The note pays nothing if the spread is negative, is not capped, and can be called at the issuer’s discretion on any reset date after Year 1. Swap quotes follow the standard market convention for USD. The results for 20,000 Monte Carlo simulations are given in Table 1. The interest rate quotes are presented in Tables 2–4. ATM swaption volatilities are presented in Table 5.
### Table 1: Note Pricing
![Table 1: Note Pricing](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d0c58ed4777dceea79e1a41741b39914ed92f44c4c83cc292f01c5b3702e24d0.jpg)
## Appendix A Transformation of Variables
Let $X_{1}$ and $X_{2}$ be independent standard normal variables. Construct
$$
\begin{array}{r c l}
Y_{1} &=& X_{1}\;, \\
Y_{2} &=& \rho X_{1} + \sqrt{1 - \rho^{2}} X_{2}\;.
\end{array}
$$
Then
$$
\begin{array}{r l r}
\operatorname{cov}(Y_{1}, Y_{2}) &=& E\left[(X_{1} - \overline{X}_{1})(\rho X_{1} + \sqrt{1 - \rho^{2}} X_{2} - (\rho \overline{X}_{1} + \sqrt{1 - \rho^{2}} \overline{X}_{2}))\right] \\
&=& E\left[(X_{1} - \overline{X}_{1}) \rho (X_{1} - \overline{X}_{1}) - \sqrt{1 - \rho^{2}} (X_{1} - \overline{X}_{1})(X_{2} - \overline{X}_{2})\right] \\
&=& \rho \sigma_{X_{1}}^{2} - \sqrt{1 - \rho^{2}} \operatorname{cov}(X_{1}, X_{2}) = \rho \sigma_{X_{1}}^{2}\;, \quad \text{(A.)}
\end{array}
$$
Since $X_{1}$ and $X_{2}$ are independent standard normal variables and hence $\operatorname{cov}(X_{1}, X_{2}) = 0$.
Thus,
$$
\operatorname{corr}(Y_{1}, Y_{2}) = \frac{\operatorname{cov}(Y_{1}, Y_{2})}{\sigma_{X_{1}} \sigma_{X_{2}}} = \frac{\rho \sigma_{X_{1}}^{2}}{\sigma_{X_{1}} \sigma_{X_{2}}} = \rho\;,
$$
Since $\sigma_{X_{1}} = \sigma_{X_{2}} = 1$.
### Table 2: LIBOR Quotes
![Table 2: LIBOR Quotes](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/423488a8e316fa74af9540b1b712c8f875a658cd5ae94a17a797ae96b4698aa7.jpg)
### Table 3: Future Quotes
![Table 3: Future Quotes](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bbf06e3025565783fb139253b1e236e6bdd608da263b736843f16a8fc58648ca.jpg)
### Table 4: Swap Quotes
![Table 4: Swap Quotes](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f0ae89221bed8ce4d9c1da110c06598ca0787c9ef59f9dc5e6c375398a7318e8.jpg)
### Table 5: ATM Implied Swaption Volatilities
![Table 5: ATM Implied Swaption Volatilities](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6a716cfc8d39427493c56d770daa6506f3d3da1126041a03e391af2749bce741.jpg)
For the corresponding interest rate volatilities, we have [4]:
$$
\sigma_{t+\tau, t+T}^{2} = \alpha^{2} \sigma_{t, T_{\text{short}}}^{2} + \beta^{2} \sigma_{t, T_{\text{long}}}^{2} + 2 \alpha \beta \sigma_{t, T_{\text{short}}} \sigma_{t, T_{\text{long}}} \rho_{t; \tau, T}\;,
$$
Where $\sigma_{t_{1}+\delta t, t_{2}}$ is the implied forward swaption volatility at time $t_{1}$ of forward interest rate effective between $t_{1}+\delta t$ and $t_{2}$. The respective correlation coefficient is:
$$
\rho_{t; \tau, T} = \frac{\sigma_{t+\tau, t+T}^{2} - \alpha^{2} \sigma_{t, T_{\text{short}}}^{2} - \beta^{2} \sigma_{t, T_{\text{long}}}^{2}}{2 \alpha \beta \sigma_{t, T_{\text{short}}} \sigma_{t, T_{\text{long}}}}\;.
$$
## References
1. F. Black. The pricing of commodity contracts. *Journal of Financial Economics*, 3:167–179, 1976.
2. FINCAD Financial Corporation. *Support and Reference*, 2007. [http://fincad.com/default.asp?id=17300&s=Support&n=References](http://fincad.com/default.asp?id=17300&s=Support&n=References).
3. F. Fabozzi. *The Handbook of Fixed Income Securities*. McGraw-Hill, 7 th edition, 2005.
4. W. Feller. *An Introduction to Probability Theory and Its Applications*, Volume 1. John Wiley & Sons, 3 rd edition, 1968.
5. P. Glasserman. *Monte Carlo Methods in Financial Engineering* (Stochastic Modelling and Applied Probability). Springer-Verlag, New York, 2004.
6. M. Matsumoto and T. Nishimura. Mersenne Twister: A 623-dimensionally equidistributed uniform pseudorandom number generator. *ACM Transactions on Modeling and Computer Simulation*, 8 (1):3–30, January 1998. [http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/ARTICLES/mt.pdf](http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/ARTICLES/mt.pdf).
7. P. Miron and P. Swannell. *Pricing and Hedging Swaps*. Euromoney Books, 1991.