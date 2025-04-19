---
tags:
  - forward_rates
  - hjm_model
  - monte_carlo
  - no_arbitrage
  - risk_neutral
aliases:
  - HJM framework
  - Heath-Jarrow-Morton
key_concepts:
  - Forward rate curve
  - HJM model dynamics
  - Risk-neutral world
  - Stochastic differential equation
  - Zero coupon bond
---

# [[6. A Brief Introduction to Stochastic Calculus#3 Some Specific Models|Implementing Heath, Jarrow & Merton (HJM) Model]]
# 1.1 HJM model by Monte Carlo Simulation.

The Heath-Jarrow-Morton framework refers to a class of models that are derived by directly  modelling the dynamics of instantaneous forward-rates. The central insight of this framework  is to recognize that there is an explicit relationship between the drift and volatility parameters  of the forward-rate dynamics in a no-arbitrage world.

The familiar short-rate models can be derived in the HJM framework but in general, however,  HJM models are non-Markovian. As a result, it is not possible to use the PDE-based  computational approach for pricing derivatives. Instead, discrete-time HJM models and MonteCarlo methods are often used in practice.

Instead of modelling the short-end of the curve and then building the forward curve for the  longer end of the curve, HJM employ a model for the whole forward rate curve.

Let  $F(t;T)$  denote the forward rate curve for time t. Therefore the price of a zero coupon bond  at time  $t$    and maturing at time  $\mathrm{T}$   and which pay   $\S1$  , can be written as:

$$
Z(t;T)=e^{\int_{t}^{T}F(t;s)d s.}
$$

The stochastic differential for the above zero coupon bond can then be written as:

$$
d Z(t;T)=u(t,T)Z(t,T)d t+\sigma(t,T)Z(t;T)d X.
$$

Since the value of the zero coupon bond at time par  $Z(t;t)=1$  ,  the volatility of the bond must  also be zero such that   $\sigma(t,t)=0$  .   we can write    $Z(t;T)$  :

$$
\begin{array}{r}{F(t;T)=-\frac{\partial}{\partial T}l o g Z(t;T)}\end{array}
$$

Differentiating with respect to t and by substitution, an equation for the evolution of the forward  curve is found.

$$
\begin{array}{r}{d Z(t;T)=\frac{\partial}{\partial T}\Big(\frac{1}{2}\sigma^{2}(t,T)-u(t,T)\Big)\,d t-\frac{\partial}{\partial T}\sigma(t,T)d X.}\end{array}
$$

We can use the forward rate to derive the stochastic differential equation for the spot rate.

$$
\boldsymbol{r}(t)=\boldsymbol{F}(t;t)
$$

Assume today is   $\mathbf{t}^{*}$   and the whole forward curve is known today,   $F(t;T)$  , the spot rate for  anytime t in the future can then be written as:

$$
\begin{array}{r}{r(t)=F(t;T)=F(t^{*},t)+\int_{t^{*}}^{t}d F(s;t).}\end{array}
$$

From (1.4) for the forward rate process for F, we have

$$
\begin{array}{r}{r(t)=F(t^{*},t)+\int_{t^{*}}^{t}\left(\sigma(s,t)\frac{\partial\sigma(s,t)}{\partial t}-\frac{\partial u(s,t)}{\partial t}\right)d s-\int_{t_{*}}^{t}\frac{\partial\sigma(s,t)}{\partial t}d X(s).}\end{array}
$$

The stochastic differential equation for r is found after differentiating (1.6) with respect to time  t.
$$
\begin{array}{r l}&{d r=\left(\frac{\partial F(t\ast,t)}{\partial t}-\frac{\partial u(s,t)}{\partial t}+\int_{t\ast}^{t}\left(\sigma(s,t)\frac{\partial^{2}(s,t)}{\partial t^{2}}+\left(\frac{\partial\sigma(s,t)}{\partial t}\right)^{2}-\frac{\partial^{2}u(s,t)}{\partial t^{2}}\right)d s\quad\right)}\\ &{}\\ &{-\int_{t\ast}^{t}\frac{\partial^{2}\sigma(s,t)}{\partial t^{2}}d X(s))d t-\frac{\partial\sigma(s,t)}{\partial s}d X}\end{array}
$$

The last term is highly path-dependent as both the random and the volatility component depend  on historical observations of these parameters. Because of the dependency of historical values,  this makes the above model a non Markov for derivative pricing, one need to be in risk neutral  world. To move to the risk-neutral world, we start with a hedged portfolio.

Suppose we can hedge a bond with another bond with maturity T. The hedged portfolio is then  :

$$
\Pi=Z(t;T_{1})-\Delta Z(t;T_{2})
$$

The change of the portfolio is given by

If

$$
\begin{array}{r l}&{\Pi=Z(t;T_{1})-\Delta Z(t;T_{2})}\\ &{\quad=Z(t;T_{1})(u(t,T_{1})d t+\sigma(t,T_{1})d X)-\Delta Z(t;T_{2})(u(t,T_{2})d t+\sigma(t,T_{2})d X)}\\ &{}\\ &{\Delta=\frac{Z(t;T_{1})\sigma(t,T_{1})}{Z(t;T_{2})\sigma(t,T_{2})}}\end{array}
$$

The portfolio is hedged and is therefore risk-free. Let the return equal to the risk-free rate r(t)  and rearranging we find that

$$
\begin{array}{r}{\frac{\mathsf{u}(t;T_{1})-r(t)}{\sigma(t;T_{1})}=\frac{\mathsf{u}(t;T_{2})-r(t)}{\sigma(t;T_{2})}\qquad\mathrm{and}\qquad u(t,T)=r(t)+\lambda(\mathsf{t})\sigma(\mathsf{t},\mathsf{T}).}\end{array}
$$

Where  $\lambda(t)$  𝑖𝑠 𝑡ℎ𝑒 𝑚𝑎𝑟𝑘𝑒𝑡 𝑝𝑟𝑖𝑐𝑒 𝑜𝑓 𝑟𝑖𝑠𝑘

In order to write down an expression for the risk-neutral forward curve, we know that the term   ${\bf u}(\mathrm{t},\mathrm{T})$   is disappears and is replaced instead with   $\mathbf{r}(\mathbf{t})$  . From equation 1.2, we can then write the  evolution of the zero coupon bond as:

$$
d Z(t;T)=r(t)Z(t,T)d t+\sigma(t,T)Z(t;T)d X.
$$

The SDE for the risk-neutral forward rate curve is written as:

$$
d F(t;T)=m(t,T)d t-v(t,T)d X.
$$

Where the forward volatility is

$$
\begin{array}{r}{v(t,T)^{1}=-\frac{\partial}{\partial T}\sigma(t,T)}\end{array}
$$

And the drift of the forward is given by    $\begin{array}{r}{m(t,T)^{2}=v(t,T)\int_{t}^{T}v(t,s)d s.}\end{array}$  The SDE for the risk-neutral forward curve becomes:
$$
\begin{array}{r}{d F(t;T)=v(t,T)\left(\int_{t}^{T}v(t,s)d s.\right)+v(t,T)d X.}\end{array}
$$

This is a single factor model which can be problematic if one is pricing derivative with various  maturities. For example, spread option which pays the difference between rates at two different  maturities. The above HJM model can be generalized for as   $\mathbf{N}$  -dimensional stochastic  differential equation

$$
\begin{array}{r}{d F(t;T)=m(t,T)d t-\sum_{i=1}^{N}v_{i}\left(t,T\right)d X_{i}}\end{array}
$$

Via Musiela parameter iz ation for multi-factor, we use the equation below to simulate the  forward curve at different maturities.

$$
\begin{array}{r}{d\bar{F}(t,\tau)=\left(\sum_{i=1}^{d}\overline{{\upsilon_{i}}}(t,\tau)\int_{0}^{\tau}\overline{{\upsilon_{l}}}(t,\tau)d s+\frac{\partial\bar{F}(t,\tau)}{\partial\tau}\right)d t+\sum_{i=1}^{d}\overline{{\upsilon_{l}}}(t,\tau)d X}\end{array}
$$

Where  $\mathbf{d}<\mathbf{n}$   and  $\mathbf{n}$    is the number of factors to be included in the model. Since we have semiannual data from 6 month to 25 years, the full dimension of the data would require 50 factors  but in practise only 3 factors is used.

To implement multi-factor HJM model, one needs to account for correlation in the term  structure and the technique used to accomplish this is the Principal Component Analysis  (PCA). This technique also enables us to estimate the volatility functions.

# 1.2 Principal Component Analysis

Principal Component Analysis (PCA) is a way to analyse the yield curve. It makes use of  historical time series data and implied co variances to find factors that explain the variance in  the term structure. Each additional factor is found so that they cumulatively maximize the  contribution to the variance. Based on these factors, volatility functions are obtained to explain  the underlying volatility of an interest rate model. For example, when implementing the HJM  model there are two main elements used in the model construction process-one is the definition  of volatility function for the model, the other involves a practical way of obtaining prices from  the model.

PCA can also be explained as a technique for finding common movements in the rates, for  finding the eigenvalues and ei gen vectors of the matrix. This tells us that large part of the  movement of the forward curve is due to parallel shift. The next most important movement  would be twisting of the curve, followed by a bending.
# Data

To implement the HJM model we use historical yield curve data from Bank of England from  January   $4^{\mathrm{th}}~2005$   to May   $31^{\mathrm{st}}\,2011$  . The data is semi-annually spaced starting from 6 month  maturity to 25 years maturity. For example, the data are the yield implied from zero coupon  bonds from 6 month maturity to 25 years. In addition, these data are nominal yield data which  has already been stripped and are downloaded from Bank of England website.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2df0fbe58fa362c42e2922327bd3216d051a7d69af085c4634a9c58b6b45424a.jpg)
Figure 1.1  Data Source: See spreadsheet attached. Fwd curve tap.

# 1.3 Covariance Matrix

Once we have obtained the daily time series and removed all the gaps in the data and adjusted  for possible jumps, we then take the difference of the data in the form of

$$
d_{i,j}=r\big(t_{i}+1,\tau_{j}\big)-r(t,\tau)
$$

We then calculate the covariance using the differenced data and we can write it in the form of  covariance matrix,   $\Sigma$  .

$$
C o v(X)=\Sigma=E(X X^{T})=\left(\begin{array}{c c c}{{\sigma_{1}^{2}}}&{{\cdots}}&{{\sigma_{1n}^{2}}}\\ {{\vdots}}&{{\ddots}}&{{\vdots}}\\ {{\sigma_{n1}^{2}}}&{{\cdots}}&{{\sigma_{n}^{2}}}\end{array}\right)
$$

See the NxN covariance matrix tap in the attached spreadsheet. Once the spreadsheet is opened,  then it can be seen that the function CovMat is used referencing the entire array of covariance  data (=CovMat(Data difference!B2:AY1618)).  The covariance data are annualized by scaling  a factor of 252/10,0000. This can be seen in the VBA code in the spreadsheet  (Worksheet Function.  $\mathrm{Cov(x,y)}*252⁄10000)$
# 1.4 Eigenvalues / Ei gen vectors.

The above covariance matrix can be factorized further by:

$$
\Sigma=\mathrm{V}\Lambda\mathrm{V}^{\mathrm{T}}
$$

Where V is an ei gen vector matrix   $(V_{i},\ldots V_{n})$   and  $\Lambda$   is and eiganvlue matrix   $\binom{\lambda_{i}}{\vdots}\begin{array}{c c c}{{\cdots}}&{{0}}\\ {{\ddots}}&{{\ddots}}&{{\vdots}}\\ {{0}}&{{\cdots}}&{{\lambda_{n}}}\end{array}$  And we end up with transformed independent Brownian motions.     $\mathrm{V}\boldsymbol{\Lambda}^{1/}\!2\mathrm{d}\mathrm{X}$   dX where   $\mathrm{d}\mathrm{X}$   is  independent Brownian motions or these are also referred to as principle component.

To compute the eigenvalues and the ei gen vectors, we use the data from the covariance matrix  and a numerical method called the Jacobi method which is suitable for symmetric matrix. We  can then use the pre-build VBA function to compute the eigenvalues and ei gen vectors. This  function is available within the spreadsheet provided during the CQF HJM lecture.

From the attached spreadsheet and within the “Prin.Component.Analysis” tab, we use the  function   $\risingdotseq$  Eigenvalues eve c(Cover i ance Matrix s!B2:AY51,Prin.Component.Analysis!B4) to  compute  a raw vector of the eigenvalues form the covariance matrix and we referemce ce;; B4  for numerical tolerance for computation.

We  also  use  the  function   $\risingdotseq$  Ei gen vectors Em at(Cover i ance Matrix s!B2:AY51,Prin.Component.Analysis!B4) to compute  the ei gen vector of the covariance matrix dat. The result is then a   $50\mathbf{x}50$   matrix of the  ei gen vector data. So, for each eigenvalues there is a corresponding column vector of  ei gen vectors.

We highlight the largest eigenvalues and the corresponding ei gen vectors which are for the  maturity point of 1.5 years, 6 years and 25 years.  We can then take the ei gen vel u es data, sort  them in ascending order. The result shows the following largest eigenvalues or largest principal  components.

Table 1.1

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1f89239b6490460c0c4efaf67f607e0651ff70dbae6ab0e3b7398ffb89d1318d.jpg)

# 0.003931095

The largest eigenvalue at the maturity point of 1.5 has a value of 0.002647853 and a variance  of  $67\%$  . This means that   $67\%$   of total variations are explained by the first principal component  which has the highest eigenvalue.   $84.9\%$   of the total variation is explained by the sum of the  first two principal components and finally,   $93\%$   of the total variations are explained by the all  three principal components. The figure below shows the term-structure of ei gen vectors  corresponding to the largest eigenvalues (principal components).
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e687c9df3ea36f1a298658474be70c49f4b063f9c70f7ae866af09d4ecdf4271.jpg)

The figure above shows how the yield curve responds to different shocks. For example, as  stated before the first principal component is due to parallel shift in the yield curve while, the  second and the third principal components are due to twist and bending of the curve  respectively.

# 1.5 Risk-Neutral Drift

Once we have calculated the eigenvalues and ei gen vectors, we need to also calculate the  volatility matrix and finally the risk-neutral drift before we begin HJM simulations.   The volatility matrix is given by

$$
\bar{v}(\tau j)=\sqrt{\lambda_{i}}(v_{i})j
$$

To compute first the drift, we take the largest eigenvalues given in table 1.1. We take the square  root of these and multiply these result with an array of data corresponding to the three principal  components. The result is a volatility matrix corresponding to all three principal components  for all maturities (see the volatility matrix tab).

The next step is to find the risk-neutral drift  $\mathbf{m(t)}$   by integrating the volatility function

$$
\begin{array}{r}{{\boldsymbol v}(t,T)=\int_{t}^{T}{\boldsymbol v}(t,s)d s}\end{array}
$$
 𝑣(𝑡, 𝑇) = ∫𝑣(𝑡, 𝑠)𝑑𝑠

We then fit a function of the volatility so that we can do the integration. The first volatility is a  flat line (parallel shift). We also fit polynomial function of the second and the third volatility  function. Once we have these functions, we then do the integration. (See figure 1.3 below for  the  $2^{\mathrm{nd}}$   volatility function). See also the attached spreadsheet, v1, v2 and v3 tabs.

Table 1.2 (Volatility matrix)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c8836b7dd81be271bea7a42b464bf4e77810fe6d988dd2108c8ffae5f97fa8d1.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c772ed7147df3910915ce76531154f321ff4ae9eaba3aa6a8303fe6ce63dfc4e.jpg)

In spreadsheet, under the “sim forward rates” tab, we show the calculated risk-neutral function   $\mathbf{M}(\mathbf{t})$   with fitted values.

# 1.6 Simulated Forward Curves

We have now the drift M(t) for each maturity. We also have the three factor vol at ili ties for each  maturity. Before we do the simulation we need to generate three columns of normal random  variables  for  the  whole  curve  using  excel  build  function  (=Rand).

=RAND()+RAND()+RAND()+RAND() $+$ RAND()+RAND()+RAND()+RAND()+RAND()+RAND()+RAND() $+$ RAND()-6

Now we have all the ingredients to start to simulate the forward curve using the following  equation:

$$
\begin{array}{l}{{F(t,T)=F(t,t)+\,m(t)d t+(v o l_{1}*W_{1}+v o l_{2}*W_{2}+v o l_{3}*W_{3})*\sqrt{d t}}}\\ {{\qquad\qquad+\,\left(\displaystyle\frac{F(t)-F(t-1}{d t}\right)d t}}\end{array}
$$

Where  $\mathrm{F(t,t)}$   is the current rate,  $\mathbf{M}(\mathbf{t})$   is the drift, vols are the vol at ili ties for the first, second and  third factors. The  $\mathbf{W}$   is the Brownian motion generated via the excel function Rand.  We then get the simulated entire HJM forward curve which we can use to price bonds or  derivatives for any maturity points.

One issue we may notice in the simulated forward curve is that the rates we get at the longer  end of the maturity seems to be negative.  We may simply take the absolute value of the result  alternatively, re-investigate or check any potential errors in the data (this may be difficult if  one is working with large data set as in this case).
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a4bc1825f0c29a0515652ee5e9fda1af26bd94449efc586d6bc93641412d8f0d.jpg)
Figure 1.4

# 1.7 Pricing Zero Coupon Bond

Since we have simulated the forward curve, we can easily compute the zero coupon bond for  any maturity point. For example, to compute the zero coupon yield now for a maturity of 2  years, we can start by summing up the 2 year forward rates. Below are more detailed  information on how to compute the zero coupon bond under HJM model.

There are two ways to calculate ZCB in HJM model:

Numerical integration of the current forward curve.

$$
\begin{array}{r}{Z(t,T)=\exp(\int_{0}^{T}f(t,s)d s}\end{array}
$$

Monte-Carlo (MC) Simulation

$$
Z(t,T)=\exp(\int_{0}^{T}r(s)d s
$$

We now use the MC method to compute the zero coupon bond.

From our previous calculation we do have the risk-neutral drift for all maturity points. We do  also have all the volatility factors for each maturity points. In addition, we do have also the  initial yield curve data. The next step is to integrate the forward rate curve for specific maturity  point and repeat these  $\mathbf{N}$   times to come up with final ZCB price using the formula

$$
\exp(-\sum r(t)d t)
$$

We then use the trapezium rule to compute the ZCB price by integrating the initial forward  curve. We use the function

$$
\!=\!\!\mathrm{EXP}(\!\mathrm{-int\_trp z m}(\!\mathrm{C8},\!\S\!\mathrm{B}\!\S11))
$$

(see VBA code module6 to see the function used). We can also either use the simulated forward  curve or use HJM function to calculate the forward curve quickly.
The final result can be seen in the spreadsheet under the tab “Zero cp n Price”.  Enter the  parameters and also number of simulations and the price of the bond is calculated. Reaching  the number of simulations to 1000, excel is extremely slow. The chart below shows the  simulated zero coupon bond price.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/583ba6767955d0b52c4e4ab27b7159c04f9c29b64599ae6f15f871f94f033a8b.jpg)
Figure 1.5

# Interest Rate Options (Cap/Floor)

# 1.8 Discount Factors

Since the underlying forward rates under HJM follow some stochastic process,  we need to use unique discounting factors for each simulation. For example, for  each simulation, the pay-off made at expiry T should be discounted by

$$
\textstyle\exp(\int_{0}^{T}r(s)d s
$$

Given the discount factors for each simulation and the simulated libor rates for the options  expiry date, we can calculate the price of each caplet and floorlet using the payoff

$$
\begin{array}{r l}{\mathrm{Cap:}}&{{}\,M a x(L-K,0)}\\ {\mathrm{Flow:}}&{{}\,M a x(K-L,\ 0)}\end{array}
$$

We then take the above payoff and scale these by a unique discount factor for each simulation.  In the attached spreadsheet, you will be able to see the discounted cap and floor prices for each  simulation

Table. 1.3
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f7e41f3f67149353adec371864d217ca3dc8e7335521be309f1bcf8e22f804b2.jpg)
Change the number of simulation input and press the gray button to see different iterations of  the Cap and Floor price computations. The figure below shows the CAP price convergence as  the number of simulations is increased from low number up to 1000 simulations. At lower  simulations prices seem to fluctuates but stabilize later afer 200 simulations. So increasing the  number of simulations from 400 to 1000 does not have any significant change in the prices but  also reduces the computation speed.

Figure 1.6

# Cap price covergence

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e1a548b1d3525a8b8453d1e416f5b20d95742095d3acadb3bcedc330bb952240.jpg)
# References

M. Avellaneda, A. Levy, A. Paras,  “Pricing and hedging derivative securities in markets with uncertain  vol at ili ties” , Journal of   Applied Finance, Vol 1, 1995

Paul Wilmott,  P.Wilmott on Quantitative Finance”,  $2^{n d}$   Edition, Volume 3, Wiley.     CQF  Lecture 2010/2011 – Heath, Jarrow and Merton Model     CQF Lecture 2010/ 2011 - Advanced Volatility Modelling in Complete Markets     P. Wilmott, A. Oztukel, “
