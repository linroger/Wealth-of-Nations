---
tags:
  - brownian_motion
  - european_options
  - monte_carlo_simulation
  - risk_neutral_valuation
  - stochastic_process
aliases:
  - Brownian Motion
  - Greeks
  - MCS
  - RNV
key_concepts:
  - Calculate the Greeks
  - Complex option pricing
  - Pricing options with MCS
  - Reduce computational time
  - Stochastic path for asset
---
# Pricing Options: Monte Carlo Simulation  

# Aims  

• To analyse how plain vanilla European options can be priced under risk-neutral valuation (RNV), using Monte Carlo simulation (MCS).   
• To show how we can reduce computational time in MCS.   
• To show how ‘the Greeks’ are calculated using MCS.   
• To apply MCS in pricing complex options, such as options whose payof depends on several underlying variables (e.g. spread options, barrier options, options with stochastic volatility).  

The concept of RNV can be used to determine option premia using MCS. This method is especially useful for some exotic options where the option payofs depend on the complete path taken by the underlying asset $S_{t}$ (and not just on the fnal value $S_{T}$ ), or where the option payof depends on more than one underlying asset. The method can be adapted to accommodate any stochastic path for the underlying asset. However, the method has some drawbacks. It is computationally time consuming and not particularly suited in handling situations where early exercise is possible (i.e. American options).  

# 26.1 BROWNIAN MOTION: PARALLEL UNIVERSE  

Pricing options using MCS requires a stochastic process for the underlying asset. Suppose we assume that the stock return has an annual mean return of $\mu=0.15$ ( $15\%$ p.a.)  

with standard deviation, $\sigma=0.20$ ( $20\%$ and is subject to random events:  

$$
R_{t}=\mu+\sigma\varepsilon_{t}\qquad\varepsilon_{t}\sim n i i d(0,1)
$$  

where  

$$
R_{t}\equiv(S_{t}/S_{t-1})-1
$$  

We assume the random error $\ensuremath{\varepsilon}_{t}$ is normal, independent, and identically distributed with mean zero and a standard deviation of one, $n i i d(0,1)$ . The standard deviation of the stock return $R_{t}$ is $\sigma$ . The random variable $\ensuremath{\varepsilon}_{t}$ represents ‘frm specifc’ events (such as strikes, legal disputes, regulatory and environmental issues, unexpected cost increases, breakdown of equipment, reputational damage, etc.). Substituting (26.1b) in (26.1a) and rearranging, gives the stochastic process for the stock price:  

$$
S_{t}=(1+\mu+\sigma\varepsilon_{t})S_{t-1}
$$  

This equation represents the behaviour of the stock price over annual intervals. Over a small interval of time, for example, $d t=0.01$ years (i.e. approximately 2.5 trading days) the mean return is $\mu$ and the standard deviation is $\sigma{\sqrt{d t}}$ . Hence, the path for stock prices over a small interval of time is:  

$$
S_{t}=S_{t-1}(1+\mu.d t+\sigma\sqrt{d t}\ \varepsilon_{t})
$$  

which is known as a (discrete) Brownian motion. Setting $S_{0}=100$ , we draw successive values for $\varepsilon_{1},\varepsilon_{2},\varepsilon_{3}\ldots$ from $\varepsilon_{t}{\sim}n i i d(0,1)$ and using Equation (26.3) we generate a random series for $S_{t}$ . Note that (26.3) is a recursion, so if $\varepsilon_{1}=0.49$ :  

$$
S_{1}=100(1+0.15(0.01)+0.20\sqrt{0.01}0.49)=101.13
$$  

$S_{1}$ is then used to calculate $S_{2}$ If the next random draw from the normal distribution is $\varepsilon_{2}=0.765$ then:  

$$
S_{2}=101.13(1+0.15(0.01)+0.20\sqrt{0.01}0.765)=103.08
$$  

We can repeat this say $n=200$ times, to obtain 200 data points for the stock price, which represents 2 years in total $(n=T/d t=2/0.01=200)$ . This gives us just one possible path that the stock price might have taken over this 2-year horizon. Starting again with $S_{0}=100$ , we can draw another 200 random values for $\varepsilon_{t}$ and get a ‘new’ path for the stock price over 2 years – one in which the ‘true’ mean return is still $15\%$ p.a. and the standard deviation $20\%$ p.a. but the series of random shocks $\varepsilon_{t}$ are diferent.  

We have created a ‘parallel universe’ where the initial value $S_{0}$ , the mean return and standard deviation are fxed but we introduce random ‘frm specifc’ events $\varepsilon_{t}$ into our stock price series. We are replaying history but at each point pricing a European call in time we ‘roll the dice’ to simulate the positive or negative random variable $\varepsilon_{t}$ , which represents random events that might afect the frm’s stock price. The simulated possible paths for the stock price over the 2-year horizon are shown in Figure 26.1.  

![](b97aa255b3d0210914a25b1e932b313179f083083869a76281392b7ffaec99d1.jpg)  
FIGURE 26.1 Brownian motion  

Along any single realised path the stock price will not grow at exactly $15\%$ p.a. because of the ‘randomness’ in the price series. For example, if the frst few random shocks $\varepsilon_{t}$ are relatively large negative numbers, then the stock price after the frst few periods will be very low. Hence even after 2 years the fnal stock price $S_{200}$ may sometimes end up below its initial value of $S_{0}=100$ (Figure 26.1). On average, across all the simulated stock price series, the stock price grows at $15\%$ p.a. but there is substantial variation around this mean value, because the standard deviation of stock returns, $\sigma=20\%$ is quite large.  

Excel and MATLAB fles to generate a Brownian motion for stock prices, given the mean return and standard deviation of returns, can be found on the website.  

# 26.2 PRICING A EUROPEAN CALL  

Consider pricing a European call on a stock using Monte Carlo simulation. First we need to set up a stochastic equation for the stock price in a risk-neutral world – that is assuming the  

stock price grows at the risk-free rate. Let $T$ ( $\stackrel{\cdot}{=}1$ year be the life of the option, the time step $d t=0.01$ (about 2.5 trading days) and therefore we generate $n=T/d t=100$ values for the stock price, for each run of the MCS. Assume the following values apply:  

$$
=100,K=100,\sigma=0.20\left(20\%\right),r=0.05\left(5\%\right),T=1\mathrm{year},n=T/d t=100
$$  

In continuous time fnance (see later chapters) the return on a stock over a small interval of time (measured in the conventional way $R_{t}\equiv(S_{t}/S_{t-1})-1\approx d S/S)$ , is assumed to follow a geometric Brownian motion:  

$$
d S/S=\mu d t+\sigma\sqrt{d t}\varepsilon_{t}
$$  

where $\mu=$ actual (‘real world’) growth rate of the stock price. (Equation 26.6 is the continuous time version of the discrete geometric Brownian motion, Equation (26.3.) It is shown in Chapter 47 (using Ito’s lemma) that Equation 26.6 implies the following equation for the continuously compounded (log) return, $d[\ln(S)]$ :  

$$
d[\ln(S)]=(\mu-\sigma^{2}/2)d t+\sigma\sqrt{d t}\varepsilon_{t}
$$  

Discrete time versions of Equations (26.6) and (26.7) are:  

$$
\begin{array}{l}{S_{t}=(1+\mu.d t+\sigma\sqrt{d t}\varepsilon_{t})S_{t-1}}\\ {S_{t}=S_{t-1}\exp[(\mu-\sigma^{2}/2)d t+\sigma\sqrt{d t}\varepsilon_{t}]}\end{array}
$$  

Equation (26.8a) has a random term which is normally distributed but it only produces an approximation to a lognormal distribution for $S_{T}$ (and approaches the lognormal as $d t\rightarrow0\mathrm{\large.}$ ). However, (26.8b) gives an exact lognormal distribution for $S_{T}$ for all values of $d t$ . Hence, if the payof to an option depends only on $S_{T}$ then (26.8b) can be used to give the value of $S_{T}$ in ‘one step’ – thus saving on computational time. The reason we use (26.8b) is that the Black–Scholes model assumes the terminal stock price has a lognormal distribution – although both recursions give paths for $S_{t}$ which are similar, when $d t<0.01$ . An example of MATLAB code to generate ‘nsim’ columns of values for $S_{t}$ , each column of which contains $\mathbf{\dot{nobs}}^{\prime}=n=T/d t$ observations is given in Example 26.1 (where $\mu=r$ , the risk-free rate, as we are pricing the option in a risk-neutral world).  

# EXAMPLE 26.1  

# MATLAB file for Geometric Brownian Motion  

$r=0.02\ ;\ s i g m a\ =\ 0.20;T\ =\ 1;\ d t\ =\ 1/100;\ n o b s$ $\mathbf{\Sigma}=\mathbf{\Sigma}$ T/dt ; nsim = 5000;  

% j is the column index  

e = randn(nobs,1); % generate nobs x 1 series of N(0,1) errors t=1; while t < nobs; % t is the row index $\scriptstyle t\ =\ t+1$ ; Stock(t, j) = Stock(t-1, j).\* ( exp( ( r-sigma.^2./2 ).\*dt + sigma.\*sqrt(dt).\*e(t) ) ); end $\scriptstyle j=j+1$ ; end % 'Stock' has dimension (nobs x nsim)  

We can use MCS under RNV to obtain the price of a European option (on a non-dividend paying stock). For any run- $i$ $(i=1,2,\dots,m)$ in the MCS:  

• Use the Brownian motion in Equations (26.8a) or (26.8b) with $\mu=r$ (under RNV)1 to generate the fnal stock price $S_{100}^{i}$ . The payof to the call is:  

$$
\mathrm{Callpayoff}=\operatorname*{max}(S_{100}^{i}-K,0)
$$  

• Discount the call payof at the risk-free rate (this is RNV again) to obtain our frst estimate of the option premium:  

$$
\widehat{C}^{i}=e^{-r T}\mathrm{max}(S_{100}^{i}-K,0)
$$  

• Repeat the above $m=10{,}000$ times to obtain 10,000 values for ${\widehat{C}}^{i}$ • The best estimate of the option premium from the MCS is:  

$$
\widehat C=(1/m)\sum_{i=1}^{m}\widehat C^{i}
$$  

For a standard European option where the payof depends only on $S_{T}$ we can use Equation (26.8b) to obtain $S_{T}$ in ‘one step’ (i.e. set $d t=T,$ ) and the distribution for $S_{T}$ will be lognormal. (But for path-dependent options we have to recursively generate all 100 values of $S_{t}$ , for each run of the MCS – see Section 26.6.)  

In the Excel spreadsheet in Table 26.1 we fnd that $\widehat{C}=8.29$ but as we have only used $m=200$ runs of the MCS (for pedagogic purposes) this will be a long way from the ‘correct’ value given by the Black–Scholes equation. MCS requires a large number of simulations before $\widehat{\boldsymbol{C}}$ settles down to a near constant value. Each run of the MCS gives a value for the discounted payof ${\widehat{C}}^{i}$ which could be plotted in a histogram – which (because of the asymmetric payofs to the option) will have a lower bound of zero and a long right tail. The standard deviation of ${\widehat{C}}^{i}$ (i.e. the ‘width’ of this non-symmetric histogram) is:  

TABLE 26.1 Pricing a Vanilla Call Using MCS   


<html><body><table><tr><td>Time</td><td>Sim 1</td><td>Sim 2</td><td>Sim 3</td><td>Sim 4</td><td>Sim 5 </td><td>Sim 6</td><td>Sim 7</td><td>Sim 8</td><td>Sim 9</td><td>Sim 10</td></tr><tr><td>0</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td><td>100</td></tr><tr><td>0.01</td><td>102.0683</td><td>98.24254</td><td>98.87855</td><td>101.5431</td><td>103.5184</td><td>95.2749</td><td>100.6461</td><td>99.78637</td><td>99.00934</td><td>100.2764</td></tr><tr><td>0.02</td><td>101.4991</td><td>98.61617</td><td>97.02375</td><td>101.1719</td><td>102.4285</td><td>94.31592</td><td>104.9234</td><td>97.97129</td><td>97.66684</td><td>100.5254</td></tr><tr><td>.….</td><td>….</td><td>:.</td><td></td><td></td><td></td><td></td><td>…</td><td>….</td><td>…</td><td></td></tr><tr><td>0.95</td><td>132.726</td><td>115.302</td><td>121.9</td><td>93.21048</td><td>74.42675</td><td>104.8382</td><td>137.0511</td><td>83.4953</td><td>78.38809</td><td>106.5505</td></tr><tr><td>0.96</td><td>132.0004</td><td>115.3534</td><td>121.933</td><td>95.04815</td><td>75.91156</td><td>106.4852</td><td>138.3202</td><td>81.60178</td><td>77.16147</td><td>104.5654</td></tr><tr><td>0.97</td><td>133.2309</td><td>113.4452</td><td>125.1421</td><td>99.45439</td><td>74.88303</td><td>108.0976</td><td>138.6531</td><td>81.6501</td><td>77.80683</td><td>107.2737</td></tr><tr><td>0.98</td><td>131.967</td><td>110.7992</td><td>122.8945</td><td>98.97497</td><td>74.8229</td><td>106.5214</td><td>135.3777</td><td>84.09324</td><td>77.13906</td><td>108.8608</td></tr><tr><td>0.99</td><td>132.0259</td><td>112.8501</td><td>120.0849</td><td>97.57811</td><td>75.52392</td><td>106.7636</td><td>137.2358</td><td>84.23462</td><td>77.61826</td><td>109.955</td></tr><tr><td>1</td><td>130.4202</td><td>115.9259</td><td>122.0662</td><td>97.48344</td><td>75.87743</td><td>105.2443</td><td>135.0986</td><td>85.72814</td><td>78.28576</td><td>108.3915</td></tr></table></body></html>  

<html><body><table><tr><td>Call Payoff for each “run"</td><td>25.42017</td><td>10.92586</td><td>17.06618</td><td>0</td><td>0</td><td>0.24429</td><td>30.09859</td><td>0</td><td>0</td><td>3.391519</td></tr><tr><td>Mean payoff for Call</td><td>8.71466</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>PV of "mean payoff"</td><td>8.289641</td><td colspan="2">Equals the MCS call premium</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Put Payoff: Max(K-S0)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Put Payoff for</td><td>0</td><td>0</td><td>0</td><td>7.516557</td><td>29.12257</td><td>0</td><td>0</td><td>19.27186</td><td>26.71424</td><td>0</td></tr><tr><td>each “run" Mean payoff</td><td>8.262523</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>for Put</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>PV of "mean payoff"</td><td>7.859555</td><td>Equals the MCS put</td><td>premium</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>  

$$
s t d\nu(\widehat{C}^{i})=[1/(m-1)]\sum_{i=1}^{m}(\widehat{C}^{i}-\widehat{C})^{2}
$$  

Although the outcomes for each ${\widehat{C}}^{i}$ are not normally distributed we know from the central limit theorem, that the distribution of the mean value approaches the normal distribution as m increases. Also the ‘standard error’2 of our estimate of $\widehat{\boldsymbol{C}}$ is given by $s t d e(\widehat{C})=s t d\upnu$ $({\widehat{C}}^{i})/{\sqrt{m}}$ . A $95\%$ confdence interval for the ‘true’ option price $c$ from the MCS is:  

$$
\widehat{C}-1.96\frac{s t d\nu(\widehat{C}^{i})}{\sqrt{m}}<C<\widehat{C}+1.96\frac{s t d\nu(\widehat{C}^{i})}{\sqrt{m}}.
$$  

To increase the accuracy by a factor of 10 requires an increase of the number of simulations by $\cdot_{100\mathrm{m}},$ . The number of runs in the MCS has to be rather large before $\widehat{\cal C}$ settles down and we fnd that for $m=5{,}000$ trials (using MATLAB), the fnal MCS value is $\widehat{C}=10.541$ , which is $0.86\%$ above the Black–Scholes value, $\mathrm{C^{\mathrm{BS}}}=10.451$ .  

Figure 26.2 shows how the MCS values for the call and put premia change as we increase the number of simulations (‘nsim’). Because MCS is a numerical technique there is always some error in the calculation of the option premium. The $95\%$ standard error bands for the MCS call premium gives a range of 10.13 to 10.94, which includes the Black–Scholes price CBS 10.451.  

Excel and MATLAB fles to calculate European call and put premia can be found on the website.  

![](897dc52e1bc15f317e161dcf8d3f120068ba133c7e20cb836c51059d12755f5f.jpg)  
FIGURE 26.2 Call and put premia using MCS  

# 26.3 VARIANCE REDUCTION METHODS  

The computation time of the MCS can be reduced by using a number of ‘variance reduction methods’, such as the control variate method and antithetic variables.  

# 26.3.1 Antithetics  

In the antithetic method, each time we draw a value for $+\varepsilon_{t}$ we also use $-\pmb{\varepsilon}_{t}$ and both are used to generate two new values for the stock price. We therefore get ‘two stock prices from one random draw’. This technique can be applied to any symmetric distribution. Using antithetics we have two discounted payofs for the call for each simulation: $C_{+}^{i}$ using $+\varepsilon$ and $C_{-}^{i}$ using $-\varepsilon$ . We then take the average of these two (discounted) payofs, as the+payof for simulation $i$ . The estimate of the option premium for run $i$ of the simulation and the fnal option premium are:  

$$
\begin{array}{l c}{{\mathrm{Option\premium\for\run\}i:\quad}}&{{C^{i*}=(C_{+}^{i}+C_{-}^{i})/2}}\\ {{\mathrm{Final\option\premium:}\quad}}&{{\widehat{C}^{*}=(1/m)\displaystyle\sum_{i=1}^{m}C^{i*}}}\end{array}
$$  

If the standard deviation of $C^{i*}$ using (26.10) is $s t d\nu(C^{i*})$ then the ‘standard error’ in estimating the true option premium is stdv $(\bar{C}^{(i)*})/\sqrt{m}$ . We obtain a much more accurate estimate from the $m$ -pairs $(C_{+}^{i},C_{-}^{i})$ than if we used $2m$ values of $C^{i}$ . This is because in the antithetic variates case, the two payofs $C_{+}^{i}$ and $C_{-}^{i}$ are equivalent to holding two calls, one which depends on $+\varepsilon_{t}$ and the other that depends on $-\pmb{\varepsilon}_{t}$ – hence these are perfectly negatively correlated and therefore the variance in outcomes from our ‘pseudo-portfolio’ of two options is less than that when using $2m$ values $C^{i}$ for the ‘single option’.  

# 26.3.2 Control Variates  

This approach is exactly the same as that used when trying to speed up the calculations in the BOPM (see Chapter 23). Suppose we want to calculate the price $f_{A}^{M C S}$ of a ‘complex’ option-A using MCS – this might be an Asian call option, for example, where the option payof depends on the average value of the underlying $s$ , over the life of the option.3  

Suppose we consider a plain vanilla European call option- $\cdot\mathrm{B}^{4}$ whose price $f_{B}^{B S}$ is directly given by the Black–Scholes equation. We could also price this European option-B using MCS, giving a price $f_{B}^{M C S}$ . The value of $f_{B}^{M C S}$ would be close to, but not equal to $f_{B}^{B S}$ (because of MCS sampling error). The control variate technique adjusts the MCS price of the Asian call option-A $(f_{A}^{M C S})$ depending on how big the error is in the MCS valuation of (the plain vanilla European) call option-B. The new ‘improved’ control variate MCS estimate for the Asian call option-A is therefore:  

$$
f_{A}^{n e w}=f_{A}^{M C S}+(f_{B}^{B S}-f_{B}^{M C S})
$$  

There are a number of other numerical techniques available to ‘speed up’ MCS and the interested reader should consult Hull (2018), Wilmott (1998) and the excellent book by Clewlow and Strickland (1998).  

# 26.4 THE GREEKS  

The delta of an option can be calculated using MCS by repeating the whole Monte Carlo procedure with a diferent starting value for the underlying asset price (and with all other factors held constant) – this is the ‘perturbation approach’ to calculating the option’s delta (which we have used with the BOPM).  

# 26.4.1 Perturbation Approach  

For example, suppose we consider the call option of Section 26.2, which we have already priced using MCS. Denote the price of the call option $f(S)$ , where $S=100$ is the initial stock price. To calculate the call option’s delta, we repeat the MCS with a new starting value $S^{+}=S+h$ , where $h$ is small (e.g. $h=0.1\dot{}\mathrm{~,~}$ ). Keep all other factors $(K,r,\sigma,T)$ unchanged, including $n=T/d t$ , the original random number series, and number of runs $m$ of the MCS. Using the new starting value for the stock price $S^{+}$ , we obtain a new MCS value for the call option premium $f(S^{+})$ . The option’s delta is then calculated as:  

$$
\Delta^{+}=\frac{f(S^{+})-f(S)}{S^{+}-S}=\frac{f(S^{+})-f(S)}{h}
$$  

A more accurate estimate of $\Delta$ can be obtained using a central diference approximation. The initial stock price is $S$ . Rerun the full MCS using $S^{-}=S-h$ and calculate:  

$$
\Delta^{-}=\frac{f(S^{-})-f(S)}{S^{-}-S}=\frac{f(S^{-})-f(S)}{-h}
$$  

The average (central diference) estimate of delta is:  

$$
\Delta_{a v}=\frac{\Delta^{+}+\Delta^{-}}{2}=\frac{f(S^{+})-f(S^{-})}{2h}
$$  

The ‘Greeks’ are more fully dealt with in Chapter 28 but it is worth briefy outlining how some of these are calculated using MCS. The above calculation for delta could be repeated for any of the variables that infuence the option price (e.g. $\mathbf{\Delta}_{r,\sigma,t)}$ to obtain an estimate of rho, vega, and theta, respectively. For example, the vega $\Lambda$ of an option is the change in the option premia for a small change in volatility $\Lambda=\partial f/\partial\sigma$ . Using a central diference, vega is calculated (following Equation 26.13) from a MCS as:  

$$
\Lambda_{a v}=\frac{\Lambda^{+}+\Lambda^{-}}{2}=\frac{f(\sigma^{+})-f(\sigma^{-})}{2h}
$$  

where $\sigma^{+}=\sigma+h$ and $\sigma^{-}=\sigma-h$ . An option’s gamma is the change in delta as the stock price changes $\Gamma=\partial^{2}f/\partial S^{2}=\partial\Delta/\partial S$ and can be approximated using:  

$$
\Gamma=(\Delta^{+}-\Delta^{-})/\mathrm{h}=[f(\mathrm{S}^{+})-2f(\mathrm{S})+f(\mathrm{S}^{-})]/h^{2}
$$  

# 26.5 MULTIPLE STOCHASTIC FACTORS  

Using MCS to price a European option that depends on more than one underlying asset is straightforward. We simply assume a stochastic process for each underlying asset, for example for two diferent stocks (or stock indices paying continuous dividends $\delta$ ) we might use the two geometric Brownian motions:  

$$
\begin{array}{c}{d S_{A}=(r-\delta_{A})S_{A}d t+\sigma_{A}S_{A}d z_{A}}\\ {d S_{B}=(r-\delta_{B})S_{B}d t+\sigma_{B}S_{B}d z_{B}}\end{array}
$$  

where $d z_{i}=\varepsilon_{i}\sqrt{d t}\left(i=A,B\right)$ . Note that the ‘real world’ growth rate of the stock price $\mu$ has been replaced by the risk-neutral term $r-\delta$ – this ensures that (for a dividend paying stock) the expected stock return (capital gain plus dividend yield) equals the risk-free rate $r$ – this is RNV.  

We can approximate these two continuous time stochastic diferential equations (SDE) using discrete time versions. In addition, we must ensure that the two random variables $d z_{A}$ and $d z_{B}$ have the same correlation coefcient as the ‘real world’ returns on the two stocks A and B (see the Choleski decomposition in Appendix 26).  

# 26.5.1 Pricing a Spread Option  

The payof to a European call spread option is $\operatorname*{max}(S_{A,T}-S_{B.T}-K,0)$ . Each run of the MCS gives two values $S_{A,T},S_{B,T}$ at the maturity date of the call option, which we assume occurs after $n=100\left(=T/\Delta t\right)$ time steps. The call premium for any run- $i$ of the MCS is $\widehat{C}^{i}=e^{-r T}\mathrm{max}(S_{A,100}^{i}-S_{B,100}^{i}-K,0)$ and the MCS estimate of the call premium is:  

$$
\widehat C=(1/m)\sum_{i=1}^{m}\widehat C^{i}
$$  

# 26.5.2 Stochastic Interest Rates  

Suppose we want to value a European call option on stock-A (which pays continuous dividends) under the assumption of stochastic interest rates. The Brownian motion for stock-A under risk-neutrality is:  

$$
d S_{A}=(r-\delta_{A})S_{A}d t+\sigma_{A}S_{A}d z_{A}
$$  

Our second equation has to mimic the behaviour of interest rates and because interest rates are usually assumed to be mean reverting we cannot use a Brownian motion. There are many mean reverting equations for interest rates (see Chapters 41 and 49) and a fairly straightforward one is:  

$$
d r=\beta(\overline{{r}}-r)d t+\sigma_{r}d z_{r}\qquad\beta>0
$$  

For example, suppose the current interest rate $r$ is above its long-run value $\overline{{r}}=3\%$ (say, given by our sample of data). Then according to Equation (26.19) the change in the interest rate next period will be negative – thus moving the interest rate closer to its long run level of $3\%$ . The speed at which the interest rate approaches its long-run value is given by the parameter $\beta$ (which has to be estimated).  

The random errors in Equation (26.18) and (26.19) will have a correlation coefcient equal to the correlation between returns on stock-A and the change in the interest rate, in our sample of ‘real world’ data. (The correlation between stock returns and changes in interest rates is likely to be small.) We then simulate the stock price and interest rate using (discrete versions of) both Equations (26.18) and (26.19). The payof to the European call option on stock-A is $\operatorname*{max}(S_{A,T}^{i}-K,0)$ . Because interest rates are stochastic, we take the average value of $r$ in each Monte Carlo simulation as our discount rate:  

$$
r_{a v}^{i}=(1/n)\sum_{k=1}^{n}r_{k}^{i}\quad\mathrm{where}\quad n=T/d t
$$  

Hence the call premium for run- $i$ of the MCS and for the fnal option premium is:  

$$
\widehat{C}^{i}=e^{-r_{a v}^{i}T}\mathrm{max}(S_{A,T}^{i}-K,0)\mathrm{and}\widehat{C}=(1/m)\sum_{i=1}^{m}\widehat{C}^{i}
$$  

# 26.5.3 Stochastic Volatility  

Suppose we want to value a European call option on a stock (paying a continuous dividend) under the assumption of stochastic volatility – unlike the Black–Scholes approach, which assumes a constant volatility. We require a stochastic diferential equation to model the random behaviour of volatility $V\equiv\sigma^{2}$ . Volatility is usually modelled as a mean reverting process. The stochastic equations for the stock price and its volatility (variance) are5:  

$$
\begin{array}{c}{d S=(r-\delta)S d t+S\sqrt{V}d z_{s}}\\ {d V=\beta(\overline{{V}}-V)d t+\xi V^{\alpha}d z_{\nu}}\end{array}
$$  

where $d z_{i}=\varepsilon_{i}\sqrt{d t}$ , $\overline{{V}}$ is the long-run average level of the variance and $\xi$ is the volatility of the variance $V$ . The terms $\overline{{V}},\xi,\alpha$ , and $\beta$ are constants which have to be estimated (often $\alpha$ is set equal to $1/_{2}^{\cdot}$ ). In generating the simulated values for $V$ and $s$ , the correlation between the stock return and its volatility is refected in the Monte Carlo ‘draws’ of $d z_{s}$ and $d z_{\nu}$ which mimic this correlation.6 It is clear from the frst equation that to obtain a value for $s$ requires a value for $V$ (and vice versa) but given starting values for $S_{0}$ and $V_{0}$ , future values for both are given by using these two recursive equations.  

For reasonable values of the parameters it can be shown that the generated series for stock returns (from the above two equations) has ‘fat tails’ and some skewness – as found in real world stock return data. Hence our MCS gives the price of the European call under an assumption of ‘non-normality’, unlike the Black–Scholes model. After generating values for the terminal stock price (using the above two equations), for $n=100$ (time steps, say) then the option payof and call premium are calculated in the usual way from the $m$ -simulations:  

$$
\widehat{C}^{i}=e^{-r T}\mathrm{max}(S_{100}^{i}-K,0)\quad\mathrm{and}\quad\widehat{C}=(1/m)\sum_{i=1}^{m}\widehat{C}^{i}
$$  

If we really believe that volatility is stochastic we could compare the MCS option price under stochastic volatility with the (incorrect) value given by the Black–Scholes formula to see how misleading the latter might be. For standard European options with less than one year to maturity, the impact of stochastic volatility on the option price is not particularly large (except for deep out-of-the-money options) but the efect is larger for options with longer maturity dates.  

MCS is useful when pricing options under stochastic volatility but sometimes a closed-form solution is possible if the stochastic process for $V$ is relatively simple. In fact, a closed-form solution is possible given the above equation for $V$ , as long as $V$ is uncorrelated with S (Hull and White 1987). Also for $\alpha=0.5$ , Heston (1973) provides an approximate closed-form solution for the option price $P_{H}$ , of the form:  

$$
P_{H}=f[(S,K,r,\delta,T-t);\quad(\overline{{V}},\xi,\rho,\alpha,b)]
$$  

The frst set of variables in (26.23) are the usual Black–Scholes inputs but the second set arise from the stochastic volatility model and these parameters must be estimated – which implies the resulting option price using Equation (26.23) will be subject to estimation error.  

# 26.6 PATH-DEPENDENT OPTIONS  

Consider using MCS to price a 1-year European ATM up-and-out call option with $K=100$ and $S_{0}=100\$ . This is a ‘knock-out barrier option’ with the upper barrier set at $H=110$ say.7 The option payofs are as follows. If over the life of the option, the stock price hits (or crosses) the upper level $H=110$ (from below) then the call is ‘knocked out’ – that is, at this point the option ceases to exist and it must therefore expire worthless, even if at maturity $S_{T}>K$ . If the stock price does not cross $H$ (at any time over the life of the option), the option payof at maturity $T$ is the same as for a plain vanilla call, $\operatorname*{max}(S_{T}-K,0)$ . Assume the stock price is (only) checked at $4\ \mathrm{p.m}$ . each day to ascertain whether it has crossed the barrier or not.  

To price this option under RNV we simulate a discrete geometric Brownian motion (GBM) for $s$ (using Equation 26.8b), setting $\mu=r$ , (RNV) and using $d t=1/252$ and $n=T/d t=252$ time steps. At each of the 252 time steps in the MCS, we check to see if $S$ has crossed the barrier $H=110$ . If in run- $i$ of the MCS the stock price crosses the barrier, we assign a payof of zero for the option at $T$ for that ‘run’ of the MCS, even if $S_{T}^{i}>K$ at maturity of the option. If $s$ does not cross the barrier $H=110$ at any of the 252 time steps then the option payof is the usual $\operatorname*{max}(S_{T}^{i}-K,0)$ . Hence:  

$$
\begin{array}{l l l}{{p a y o f f^{i}~=~\operatorname*{max}(S_{100}^{i}-K,0)~}}&{{~\operatorname{if}S_{k}^{i}<H\operatorname{for}k=1,2\dots n}}\\ {{p a y o f f^{i}~=~0~}}&{{~\operatorname{if}S_{k}^{i}\geq H\operatorname{for}k=1,2\dots n}}\end{array}
$$  

The MCS option premium $\widehat{\boldsymbol{C}}$ is the average over all $m=10{,}000$ simulations of the option payofs (discounted at the risk-free rate)8:  

$$
\widehat C=e^{-r T}(1/m)\sum_{i=1}^{m}(p a y o f f^{i})
$$  

MATLAB fles to calculate call and put premia for barrier options can be found on the website.  

A limitation of the basic MCS method is that it can only usefully be used for European style options. When pricing American options we have to know the value of the option for all values of $s$ at each point in time in the MCS, so that we can compare the ‘MCS price’ with the option’s intrinsic value, at each time period. In its basic form, the ‘mathematical problem’ with MCS arises because the method solves in a forward direction (i.e. start at $S_{0}$ and simulate values to $S_{T}\mathrm{~.~}$ ), rather than in a backward direction (e.g. as with the BOPM and the backward fnite diference method discussed later). However, there are more complex simulation methods that can be used to price American and other non-standard options (e.g. see Longstaf and Schwartz 2001).  

# 26.7 SUMMARY  

• The stochastic behaviour of stock prices can be represented by a geometric Brownian motion (GBM), in continuous time. Using a discrete time approximation to a GBM we can generate a series for the stock price once we have an estimate of the mean return on the stock and its standard deviation.   
• When pricing an option using MCS under risk-neutral valuation, we (a) set the growth rate of the stock price equal to the risk-free rate $(\mu=r)$ in the GBM, and (b) we discount the option payofs using the risk-free rate. The only estimated input in the GBM is therefore the volatility of the stock return.   
• MCS is a numerical technique and therefore the resulting option price is subject to error.   
• For options whose price is determined by two or more ‘variables’ (e.g. two underlying stochastic variables $S_{A}$ and $S_{B}{\mathrm{:}}$ ), MCS tends to be a relatively efcient numerical method of obtaining option premia, and it can easily accommodate correlations between the underlying stochastic variables (e.g. using the Choleski decomposition).  

• MCS is very fexible and can handle any parametric stochastic processes for the underlying assets (e.g. normal, mixture-normal, Student’s- $t$ , etc.) and for any other variables that may infuence option prices, such as stochastic interest rates and stochastic volatility. This makes MCS very useful in pricing complex European options. • Antithetic variables or the control variate technique can be used in a MCS to speed up calculations and to improve the accuracy of the estimated option price (for any given number of simulations).  

# APPENDIX 26: MCS, SEVERAL STOCHASTIC VARIABLES  

To price options using MCS we often assume that (continuously compounded) returns on the underlying assets (i.e. proportionate change in prices over a small interval of time) are multivariate normal and therefore price levels are multivariate lognormal. We will demonstrate how correlated variables can be generated in a MCS and we concentrate on the two-asset case, but this can easily be generalised to $N$ -assets.  

Standard computer software can be used to generate two normally distributed, identical and independent random variables $\varepsilon_{1}$ and $\ensuremath{\varepsilon}_{2}$ , with zero mean $(E\varepsilon_{i}=0)$ and a standard deviation of 1, $\mathrm{var}(\varepsilon_{i})\equiv E(\varepsilon_{i}^{2})=1$ . Hence $\varepsilon_{i}\left(i=1,2\right)\sim n i i d(0,1)$ . These random variables are independent and therefore have zero correlation (and covariance) by construction, that is $E(\varepsilon_{1}\varepsilon_{2})=0$ . We wish to create two normally distributed variables $z_{1}$ and $z_{2}$ both with mean zero and standard deviation of unity but with a correlation coefcient equal to $\rho$ . This is accomplished using the following two equations:  

$$
\begin{array}{l}{{z_{1}=\varepsilon_{1}}}\\ {{\phantom{\varepsilon_{2}=\rho\varepsilon_{1}+\sqrt{1-\rho^{2}}\varepsilon_{2}}}}\end{array}
$$  

The variables $z_{1}$ and $z_{2}$ have $\varepsilon_{1}$ in common and this is the source of the correlation between $z_{1}$ and $z_{2}$ . It is easy to see that:  

$$
E z_{1}=E z_{2}=0
$$  

$$
\operatorname{var}(z_{1})=E(\varepsilon_{1}^{2})\equiv\operatorname{var}(\varepsilon_{1})=1
$$  

$$
\operatorname{var}(z_{2})=\rho^{2}\operatorname{var}(\varepsilon_{1})+(1-\rho^{2})\operatorname{var}(\varepsilon_{2})=1
$$$$
\begin{array}{r l}&{\qquad\mathrm{var}(\mathcal{L}_{2})=\rho^{-}\mathrm{var}(\varepsilon_{1})+\iota_{1}-\rho^{-})\mathrm{var}(\varepsilon_{2})=\iota}\\ &{\qquad\mathrm{cov}(z_{1},z_{2})={E}(z_{1}z_{2})=\rho{E}(\varepsilon_{1}^{2})+\sqrt{1-\rho^{2}}{E}(\varepsilon_{1}\varepsilon_{2})=\rho}\\ &{\qquad\mathrm{corr}(z_{1},z_{2})=\mathrm{cov}(z_{1},z_{2})/(\sigma(z_{1})\sigma(z_{2}))=\rho}\end{array}
$$  

Let $\mu=$ annual mean return (growth rate of the stock price), $\sigma=$ annual standard deviation of stock returns, $T=$ time to maturity of the option (years), $n=$ number of time-steps  

chosen in the MCS and the time interval is $d t=T/n$ . We now simulate (multivariate lognormal) stochastic variables $S_{1t},S_{2t}$ using $z_{1t}$ and $z_{2t}$ :  

$$
\begin{array}{r}{{S_{1t}}={S_{1t-1}}\exp\left[(\mu_{1}-\sigma_{1}^{2}/2)d t+\sigma_{1}\sqrt{d t}z_{1t}\right]}\\ {{S_{2t}}={S_{2t-1}}\exp\left[(\mu_{2}-\sigma_{2}^{2}/2)d t+\sigma_{2}\sqrt{d t}z_{2t}\right]}\end{array}
$$  

The correlation coefcient between $z_{1}$ and $z_{2}$ is $\rho$ so the two return series $\ln(S_{i,t}/S_{i,t-1})$ also have a correlation coefcient of $\rho$ . The variables $S_{1t},S_{2t}$ could be any two underlying ‘assets’ depending on the option pricing problem at hand (e.g. two stock prices or one stock price and one interest rate or one stock price and the volatility of the stock return).9 If we are simulating ‘real world’ values $S_{1}$ and $S_{2}$ then $\mu$ is the ‘real world’ mean growth rate of the variable. If we are pricing an option using MCS under RNV then we replace $\mu$ by its ‘risk-neutral equivalent’ – which would be $\mu=r-\delta$ for an option on an asset (e.g. stock) with a continuous payment (e.g. dividend yield) of $\delta$ p.a.  

# Choleski Decomposition to Obtain Correlated Variables  

We now present the two-variable case in matrix form. Assume continuously compounded asset returns $d(\ln S_{i})$ are multivariate normal, $N(0,\Sigma)$ , and we have statistical estimates of the variance-covariance matrix of returns $\Sigma$ , from which we can construct the correlation matrix, $c$ . For the $(2\times2)$ case we have:  

$$
\begin{array}{l}{{\Sigma=\left[\sigma_{11}\ \sigma_{12}\right]}}\\ {{\sigma_{21}\ \sigma_{22}}}\\ {{{\cal C}=\left[\begin{array}{l}{{1\ \rho}}\\ {{\rho\ 1}}\end{array}\right]}}\end{array}
$$  

where $\sigma_{12}=\sigma_{21}$ and the correlation coefcient $\rho=\sigma_{12}/\sigma_{1}\sigma_{2}$ . A simple piece of matrix algebra allows us to map the correlation matrix into two matrices $A$ such that:  

$$
C=A A^{'}
$$  

where $A$ is the lower triangular matrix:  

$$
A=\left[\stackrel{1}{\rho}\sqrt{1-\rho^{2}}\right]
$$  

The A-matrix is the Choleski factorisation of the correlation matrix $c$ . It is easy to check that $C=A A^{'}$ . The reason for the Choleski factorisation is that if $\boldsymbol{\varepsilon}=\left(\varepsilon_{1},\varepsilon_{2}\right)^{\prime}$ $2\times1$ vector) consists of two independent $N(0,1)$ variables then we can generate our two correlated standard normal variates $\boldsymbol{Z}=\left[z_{1},z_{2}\right]^{\prime}$ using:  

$$
{\boldsymbol{Z}}={\boldsymbol{A}}{\boldsymbol{\varepsilon}} 
$$  

The (two) variables in $Z$ will have zero mean, unit variance but have a correlation of $\rho$ . Most computer programs can generate $N$ correlated normally distributed random variables $Z=\left[z_{1},z_{2},....z_{n}\right]^{\prime}$ using the Choleski decomposition (or some other numerical algorithm), given the $N\times N$ covariance matrix $\Sigma_{N\times N}$ as an input.  

There is a MATLAB fle on the website which uses the Choleski decomposition to produce correlated multivariate normal random variables.  

Practical Issues  

Most software packages produce uniform $U(0,1)$ pseudo-random numbers which lie between 0 and 1 and occur with equal probability. These can be ‘transformed’ into standard normal variables in a variety of ways. For example, if $u_{i}$ is distributed $U(0,1)$ then $\varepsilon=\sum_{i=1}^{12}u_{i}-6$ gives an (approximate) standard normal variable $\varepsilon\sim n i i d(0,1)$ . In Excel the uniform $U(0,1)$ distribution is given by the command: RAND( ), so $\varepsilon=\sum_{i=1}^{12}R A N D(\mathbf{\varepsilon})_{i}-6$ is niid(0,1). A more succinct way of generating in Excel is to use the inverse cumulative normal command, so $\varepsilon=$ NORMSINV(RAND( )). However, these numerical methods give too many values for $\varepsilon_{i}$ that are close to the mean, than for a ‘true’ normal distribution. This problem can be mitigated by other ‘transformations’ (e.g. Box–Muller transformation).  

Two possible numerical problems in a MCS are either that our simulated ‘pseudo’ random numbers are not in fact random at all or, that the Choleski decomposition fails numerically (when the number of assets $N$ is large). Random number generators actually use a deterministic algorithm. They take a particular ‘seed number’ as a starting point and generate numbers that appear random (and pass tests for statistical independence, etc.). For a given ‘seed number’, the same set of random numbers will be repeated. The problem is that as you increase the number of ‘runs’ in the MCS, the random number generator may ‘choose’ a seed it has already used. This leads to repetitions or cycles in your ‘pseudo’ random numbers and a spurious increase in accuracy of your Monte Carlo results.  

Another problem is that standard MCS tends to produce numbers which ‘cluster’, so additional observations do not provide new information – and this tends to bias the simulation results. However, so called quasi-Monte Carlo (QMC) techniques or ‘low discrepancy sequences’ avoid producing ‘clusters’, so MCS becomes much more efcient and can produce accurate results with substantially fewer ‘runs’. The idea is that the ‘quasi-random’ sample, ‘remembers’ the previous sample and tries to position itself away from any previous samples, thus ‘flling’ the sample space without any clustering.  

Finally, in order to undertake the Cholesky decomposition the estimated variancecovariance matrix $\Sigma$ must be positive semi-defnite. This requires (i) the number of data observations to be greater than the number of assets $N$ in the covariance matrix $\Sigma$ , and (ii) there is no perfect collinearity amongst the asset returns. However, if the dimension of $\Sigma$ is large, then near perfect collinearity may become a practical problem.  

# EXERCISES  

# Question 1  

The return on a stock can be represented by $R_{t}=\mu+\sigma\varepsilon_{t}$ where $\varepsilon_{t}\sim n i i d(0,1)$ and $R_{t}\equiv(S_{t}/S_{t-1})-1$ . What does this imply for the stochastic equation for the stock price $S_{t}$ ?  

# Question 2  

When using MCS, assume the path for the stock price $s$ , over a small interval of time is:  

$$
S_{t}=(1+\mu.d t+\sigma\sqrt{d t}\ \varepsilon_{t})S_{t-1}
$$  

$\mu=10\%$ (expected return on the stock), $\sigma=20\%$ (volatility of stock return) and the initial stock price is $S_{0}=100$ . Explain how you would simulate the stock price for each trading day over a horizon of 10 days.  

# Question 3  

Suppose stock prices follow a GBM with mean $\mu=0$ and standard deviation $\sigma>0$ . After many periods (e.g. $T=100$ periods) would you expect most of the simulated paths for the stock price to end up close to the initial stock price?  

# Question 4  

Discrete time versions of a Brownian motion (over small time intervals $d t$ ) can be represented as:  

(1) $S_{t}=(1+\mu.d t+\sigma\sqrt{d t}\ \varepsilon_{t})S_{t-1}$ or (2) $S_{t}=S_{t-1}\exp[(\mu-\sigma^{2}/2)d t+\sigma\sqrt{d t}\varepsilon_{t}]$  

What, if any, are the diferent outcomes for the stock price produced by these equations after many time periods?  

# Question 5  

How can you calculate the delta of a European option (on a non-dividend paying stock) when using MCS to price the option?  

# Question 6  

Suppose you price a European option using MCS under the assumption that the underlying stock price $s$ follows a geometric Brownian motion and assuming that volatility (variance) $V$ of the underlying stock price is stochastic and mean reverting. As the number of runs in the MCS is increased, would you expect the option price given by the MCS to approach the Black–Scholes price?  

# Question 7  

Suppose you price a European option using MCS under the assumption that the underlying stock price $s$ follows a geometric Brownian motion and assuming that volatility (variance) $V$ of the underlying stock price is stochastic and mean reverting.   
Explain what stochastic equation you might use to simulate the behaviour of volatility (variance) $V$ and provide any intuitive interpretation of this equation.  