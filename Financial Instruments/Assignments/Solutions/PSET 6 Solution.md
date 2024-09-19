---
title: PSET 6 Solution
---

# PSET 6 Solution
## Winter 2024 John Heaton Solution To Homework 6 1. Implied Volatility

From the CBOE site I extract options prices with expiration of February 21, 2024 and compute "mid" prices as an average of bid and ask. To compute the Black-Scholes-Merton (BSM) implied volatility I need the maturity, the continuously compounded risk free rate r and the continuously compounded dividend yield y. Let T = 0.35 (365 days in a year and 129 days to maturity). From the Federal Reserve website the annually compounded 3
months constant maturity rate was r1(0.25) = 5.43% on February 12 (some interpolation could be done here. Any reasonable extraction is fine!). Converting this to continuous compounding units gives r(0.25) = ln (1 + r1(0.25)/4) × 4 = 5.39%.

From Robert Shiller's dataset, the January 2021 to June 2023 average dividend yield (annually compounded) was equal to y1 = 1.51%, which, converted into continuous compounding units, gives y = 1.50%.

The BSM implied volatility is computed using solver (I use Matlab, but Excel does exactly the same calculation but takes a bit more time unless you know how to use macros). The results are shown Figure 1 for moneyness from 08 to 1.1.

As you can see the volatility is not constant, but it is decreasing with the moneyness of the option (as in the Figure from Teaching Note 6). The PLUS security has one-year to maturity with embedded call options so it would be nice to have implied volatility for a one-year maturity. I use the February 2025 options (maturity of 12 months) (don't worry if you didn't do this!). Implied volatility from the June 2024 and February 2025 call options with r(1) = 4.8% (from the one-year constant maturity yield) are show in Figure 2.

## 2. Valuing And Analyzing A Structured Security

( 1) In order to value the PLUS follow these steps:

(a) Decompose the PLUS payoff into simpler securities.
The payoff of the PLUS security at maturity is $$\pi(T)=\left\{\begin{array}{cc}min\left[10+10\times3\times\left(\frac{S_T-S_0}{S_0}\right).9\right]&if\,S_T>S_0\\ 10\times\frac{S_T}{S_0}&if\,S_T\leq S_0\end{array}\right.$$.
S0 units of the index. Let Starting with ST ≤ S0, this is just a long position in 10
N =
10
S0 be the number of units of the index determined by this part of the payoff. With the S&P500 at 5,000.57 N = 0.0020
Finding the payoff for the case when ST *> S*0 is simpler than it first appears.

The trick is to plot the payoff and to analyze the chart to determine the basic securities. Figure 3 gives the PLUS payoff for different values of ST .
```LaTeX
\begin{document}
\begin{table}[ht]
\centering
\begin{tabular}{|c|c|}
\hline
\textbf{Range}         & \textbf{Slope}                          \\ \hline
$S_T \leq S_0$         & $N = \frac{10}{5,000.57} = 0.0020$      \\ \hline
$S_0 < S_T \leq K_1$   & $3 \times N = 0.0060$                   \\ \hline
$S_T > K_1$            & 0                                       \\ \hline
\end{tabular}
\caption{Slope of the PLUS for different values of $S_T$}
\end{table}
\end{document}
```



```latex
\usepackage{amsmath}
\usepackage{booktabs}
\usepackage{array}
\usepackage{hyperref}

\begin{document}

% First Table
\begin{table}[ht]
\centering
\begin{tabular}{|c|c|}
\hline
\textbf{Range}         & \textbf{Slope}                          \\ \hline
$S_T \leq S_0$         & $N = \frac{10}{5,000.57} = 0.0020$      \\ \hline
$S_0 < S_T \leq K_1$   & $3 \times N = 0.0060$                   \\ \hline
$S_T > K_1$            & 0                                       \\ \hline
\end{tabular}
\caption{Slope of the PLUS for different values of $S_T$}
\end{table}

\end{document}
```
We see that there are two points where the slope changes. The first point is S0, while the second is where:

$$10+10\times3\times{\frac{S_{T}-S_{0}}{S_{0}}}=11.9$$
This is where ST = 5, 317.27. Call this point K1. After K1 the slope is zero.

Table 1 reports the slopes of the PLUS security:

Range
Slope

$S_T\leq S_0\quad\quad\quad\quad\quad N=\frac{10}{5,000.57}=0.0020$

$\underline{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}$
$S_0<S_T\leq K_1\quad\quad3\times N=0.0060$

$S_T>K_1\quad\quad\quad\quad\quad\quad\quad\quad0$
Alternatively, let N be the number of units of the underlying securities implicitly held in the PLUS security. Table 2 reports the resulting slopes for this position:

Range
Slope

$$\frac{S_{T}\leq S_{0}}{S_{0}<S_{T}\leq K_{1}}\frac{1}{3}$$
So, the payoff of the PLUS can be rewritten as

$$\pi(T)=N\cdot[S_{T}+2\cdot m a x(S_{T}-S_{0})-3\cdot m a x(S_{T}-K_{1})]$$
The PLUS security is long e−yN units of the underlying index, 2N units of an at the money call option and short 3N units of a call option with strike price K1.

(b) Use the Black and Scholes model to price the identified simpler securities. 
- Assuming the PLUS was issued on February 18, 2024, N = 0.0020 and K1 = 5, 317.27. To price the at the money option I use the implied volatility for a February 2025 call option with strike equal to 5000: σATM = 17.2%. For the OTM option I use the implied volatility for a February 2025 call option with strike equal to 5300: σOTM = 15.1%. The prices of the options are:
	- $c^{ATM}=418.26$ and $c^{OTM}=235.01$. 
Hence:

$$V^{PLUS}=N\cdot\left[e^{-y}S_{0}+2\cdot c^{ATM}-3\cdot c^{OTM}\right]=10.114$$
3. **Adjust the parameters to obtain a value equal to the issue price.** 
- In the prospectus the security is sold for 10 dollars, but according to the model the value is actually greater than par. In order to increase its value we can change the strike price of the *OTM* option by decreasing the maximum payoff currently set at 11.9.
Let C be the maximum payoff.
Changing this value implicitly
changes the strike price, K1, of the OTM option. The value of C that sets the
PLUS security value to $10 is C = 11.61 implying a value of K′
1 = 5, 268.42. By
decreasing C the upside potential of the security is decreased as shown in Figure (4).
so

$$d_{1}^{ATM}=d_{1}(S,S_{0})=\frac{ln\left(\frac{S}{S_{0}}\right)+\left(r-y+\frac{\sigma^{2}}{2}\right)\cdot T}{\sigma\cdot\sqrt{T}}$$

$$d_{1}^{OTM}=d_{1}(S,K_{1})=\frac{ln\left(\frac{S}{K_{1}}\right)+\left(r-y+\frac{\sigma^{2}}{2}\right)\cdot T}{\sigma\cdot\sqrt{T}}$$
∂V P LUS

for $S=S_{0}$ we get $e^{-y}N\left(d_{1}^{MTM}\right)=0.621$ and $e^{-y}N\left(d_{1}^{OTM}\right)=0.447$. Therefore $\frac{\partial V^{PLUS}}{\partial S}=0.00177$. (In this calculation I used the appropriate implied volatility for 
∂S
= 0.00177. (In this calculation I used the appropriate implied volatility for each option.)
To compute the beta of the PLUS use the formula

$$\beta^{P L U S}={\frac{{\frac{q V^{P L U S}}{V^{P L U S}}}}{{\frac{d S}{S}}}}={\frac{d V^{P L U S}}{d S}}\cdot{\frac{S}{V^{P L U S}}}=0.0020\cdot{\frac{S}{V^{P L U S}}}$$
that results in

$$\beta^{P L U S}=0.0020\cdot{\frac{5000.57}{10.114}}=0.88$$
which is less than 1. At the current level of the S&P500 the security is less risky than the S&P500 itself. Computing the value of beta for different values of S (keeping the same implied volatilities used to compute option prices) and for different times to maturity (see Figure 5), we see that as we approach maturity, the beta of the PLUS increases substantially in the region between S0 and K1.

This happens because between S0 and K1 the PLUS security is a leveraged investment
(the slope of the payoff increases in that region since the at the money option becomes in the money). In may be helpful to see how the value of the security changes when the value of the underlying changes at different points in time.

This is shown in Figure 6.