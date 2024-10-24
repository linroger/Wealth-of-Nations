---
aliases:
- Alias_360_Fixed Income HW LaTeX Files.md
- Alias_363_Fixed Income HW LaTeX Files.md
tags:
- tag_example
title: Fixed Income HW LaTeX Files
---


# Fixed Income HW LaTeX Files
### HW 1

```
\documentclass[11pt]{report}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage{geometry}
\usepackage{float}    % for the H option
\usepackage{longtable}
\geometry{letterpaper, margin=0.8in}
\title{Bus 35130 Spring 2024\\ Solution to Homework 1}
\author{John Heaton}
\date{March 25, 2024}

\begin{document}
\maketitle

\section*{Estimation and Forecast}

\textbf{(PP)} The difference between the bid and ask yields reflects the difference between bid and ask prices. Bid prices from dealers are less than ask prices and hence the bid yields are higher than ask yields. To convert to the "Asked Yield" we use the formulas in TN1, on , to obtain BEY for maturities 6/11/2020 (quoted ask $d = 0.093/100$, $n = 66$) and 3/25/2021 (quoted ask $d = 0.160/100$, $n = 353$) as follows:
$$
BEY_{6/11/2020} = \frac{365 \times 0.00093}{360 - 0.00093 \times 66} = 0.0943\%
$$

$$
BEY_{3/25/2021} = \frac{365 \times 0.00160}{360 - 0.00160 \times 353} = 0.1625\%
$$
which are close to the corresponding asked yields in the quoted table.

\textbf{(CP)} We first eliminate the days that have missing values. These are non-business dates (such as Christmas and Thanksgiving) on which no prices were recorded. Next, note that the rates given in the datafile are in percentages. To get the BEY, use the formula on  of TN1:
$$
BEY = \frac{365 \times d}{360 - d \times 91}
$$

\begin{itemize}
    \item The quoted discounts and BEYs are plotted below in Figure 1. You can see that the differences are very small.
\end{itemize}

\subsection*{1. The parameters can be estimated using an OLS regression.}

\textbf{(PP)} We regress $r_{t+1}$ on $r_t$. There are 17,542 observations for the T-bill rates. Thus, the observations 1-17,541 can be treated as the independent variable $X$, and observations 2-17,542 as the dependent variable $Y$.

In general, for a univariate regression of the form
$$
Y_i = \alpha + \beta X_i + u_i, \quad i = 1, \ldots, n
$$
the OLS estimates are
$$
\hat{\beta} = \frac{\sum_{i=1}^{n} (X_i - \overline{X})(Y_i - \overline{Y})}{\sum_{i=1}^{n} (X_i - \overline{X})^2},
$$
$$
\hat{\alpha} = \overline{Y} - \hat{\beta} \overline{X},
$$
where
$$
\overline{X} = \frac{1}{n} \sum_{i=1}^n X_i, \quad \overline{Y} = \frac{1}{n} \sum_{i=1}^n Y_i.
$$

Finally, to estimate the standard error of the error term, we can first compute the sample standard errors,
$$
\hat{u}_i = Y_i - \hat{\alpha} - \hat{\beta} X_i, \quad i = 1, \ldots, n.
$$
Then
$$
\hat{\sigma} = \sqrt{\frac{1}{n} \sum_{i=1}^n \hat{u}_i^2}.
$$

\textit{Note: The adjustment in $\hat{\sigma}$ for degrees of freedom is not typical in time series regression. Because the right-hand-side variable is a random variable, the typical results about unbiasedness of regression estimates do not apply here. Main point: if you divided by $n$ versus $n-2$ with such a large sample, there will be little numerical difference!}

\textbf{(PP)} AR(1) process for interest rates is the following:
$$
r_{t+1} = \alpha + \beta r_t + \epsilon_t \quad (1)
$$
"Mean reversion" of interest rates can be modeled with AR(1) process since, according to AR(1) process, the projected interest rates converge to the long-term level of interest rates over time under stationarity condition, i.e. when $|\beta| < 1$. In this case, the long-term level of interest rates, i.e. "unconditional mean", under AR(1) process is the following:
$$
E(r) = \overline{r} = \frac{\alpha}{1 - \beta}
$$

To better see the mean reversion, subtract $r_t$ from both sides and rewrite
$$
r_{t+1} - r_t = (1 - \beta) [\overline{r} - r_t] + \epsilon_t \quad (2)
$$
Thus, if $r_t > \overline{r}$, we have $E[r_{t+1} - r_t] = (1 - \beta) [\overline{r} - r_t] < 0$, and hence a high rate tends to be followed by a negative \emph{change} in interest rates, and vice versa.

\textbf{(CP)} The results of the regression are summarized in Table 1.

\begin{table}[h!]
\centering
\begin{tabular}{l c c}
\hline
Coefficients & Estimate & t-value \\
\hline
$\alpha$ & $2.01702 \times 10^{-5}$ & $1.7677$ \\
$\beta$ & $0.9996$ & $4722.4$ \\
$\sigma$ & $9.05099 \times 10^{-4}$ &  \\
\hline
\end{tabular}
\caption{Estimation of the AR(1)}
\end{table}

Given these estimates, the average long-run interest rate is
$$
\overline{r} = \frac{\hat{\alpha}}{1 - \hat{\beta}} = 0.04874
$$

\subsection*{2. The most current interest rate is from 2024-03-14, $r_{TODAY} = 5.3945\%$.}

\textbf{(PP)} Let $r_{TODAY}(n)$ denote the forecast for the interest rate $n$ days from today. From the equation for AR(1) process above, using the estimates of $\alpha$ and $\beta$, we have
$$
r_{TODAY}(1) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}.
$$

If we compare the equation above with the equation for AR(1) process, we see that the error term does not show up in the forecast. That is because we expect it to be 0. Next, in order to forecast the interest rate 2 days from today, we can just use the forecast we just made for tomorrow:
$$
r_{TODAY}(2) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}(1).
$$

More generally,
$$
r_{TODAY}(n+1) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}(n), \quad n = 1, 2, 3, \ldots
$$

As a result, the interest rate forecast for the following three days is the following:
$$
r_{TODAY}(1) = \hat{\alpha} + \hat{\beta} r_{TODAY} = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3945\% = 5.3943\%
$$
$$
r_{TODAY}(2) = \hat{\alpha} + \hat{\beta} r_{TODAY}(1) = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3943\% = 5.3941\%
$$
$$
r_{TODAY}(3) = \hat{\alpha} + \hat{\beta} r_{TODAY}(2) = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3941\% = 5.3939\%
$$

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_0.png}
\caption{Quoted discounts and BEYs}
\end{figure}

\textbf{(CP)} You can use a loop in Matlab or Python to compute the forecasts. The results are plotted below in Figure 2:
Our forecast of the AR(1) process also gets closer and closer to its long-run average as the forecasting horizon increases.

\subsection*{3. We can calculate yields from the Strip prices $Z(t, T)$ using the formula on  of TN1:}

Here, $t$ is the present date, 2024-03-14. We have multiple maturities $T$, so we can calculate yields for different maturities. From these prices, we can calculate the 6-month forward rates from the formula on  of TN1:
$$
f(t, T_1, T_2) = \frac{\ln(Z(t, T_1)) - \ln(Z(t, T_2))}{T_2 - T_1}
$$

\textbf{(PP)} Using the formula above, i.e. $y(t, T) = -\frac{1}{T} \ln(Z(t, T))$, the current yields for the first three maturities are determined as follows:
$$
r(0, 0.5) = -\frac{1}{0.5} \ln(0.9745) = 5.174\%
$$
$$
r(0, 1) = -\frac{1}{1} \ln(0.9526) = 4.859\%
$$
$$
r(0, 1.5) = -\frac{1}{1.5} \ln(0.9330) = 4.622\%
$$

Using the formula above, i.e. $f(t, T_1, T_2) = \frac{\ln(Z(t,T_1)) - \ln(Z(t,T_2))}{T_2 - T_1}$, the forward rates for the first three maturities are determined as follows:
$$
f(0, 0.5, 1) = \frac{\ln(0.9745) - \ln(0.9526)}{1.0 - 0.5} = 5.174\%
$$
$$
f(0, 1, 1.5) = \frac{\ln(0.9526) - \ln(0.9330)}{1.5 - 1.0} = 4.545\%
$$
$$
f(0, 1.5, 2) = \frac{\ln(0.9330) - \ln(0.9150)}{2 - 1.5} = 4.147\%
$$

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{4_image_0.png}
\caption{Yields and Forward Rates}
\end{figure}

\textbf{(CP)} Figure 3 shows the yield and forward curve extracted from the strips, while Figure 4 shows the implicit forecasts from the Strips and the forecasts calculated in question 3:
These forward rates are often thought of as market forecasts of future (6-month) interest rates. As we shall see, this is not correct, as we need to adjust for "a market risk premium" (as well as a convexity factor). In the terminology that we will develop, forward rates are "expected future rates" under the risk-neutral dynamics (plus a convexity factor). But the market participants are not risk-neutral, and therefore forgetting the risk premium may yield serious forecast errors.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Time Series Forecast and Long-term Interest Rate}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_1.png}
\caption{Implicit Forecasts from Strips}
\end{figure}

\end{document}
```

### HW 2

```
\documentclass[11pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 2}
\author{John Heaton}
\date{March 31, 2024}

\begin{document}
\maketitle

\section*{Inverse Floater}

\subsection*{1. (PP) The size of the Treasury securities data available on February 17, 2009 is huge.}

In order to perform the bootstrap procedure, we need securities at semi-annual frequency. We can cherry-pick from the dataset such securities. Table 1 contains the data used in the bootstrap procedure. Unfortunately, already at $T = 10$ years we do not have notes with maturities at semi-annual frequency; using bonds we can get to $T = 12.5$, but they may have some price differences due to liquidity. (For instance, see the break at $T = 10$ in both Figure 1 and 2.) Even using bonds, we must stop the procedure after $T = 12.5$ as there is no more data at semi-annual frequency.

To bootstrap the discounts, we can use the procedure illustrated in teaching notes:
For every $i$
$$
Z(0, T_i) = \frac{P(0, T_i) - c_i/2 \sum_{j=1}^{i-1} Z(0, T_j)}{1 + c_i/2}
$$

Alternatively, we can use a matrix formulation. In line with the semi-annual frequency, let $T_i = \frac{i}{2}$ for $1 \leq i \leq 25$. Define a cash-flow matrix, $C$, where an element $c_{ij}$ denotes the payoff at time $T_j$ of the bond with maturity $T_i$. By ordering the bonds increasing in maturity, $C$ is lower diagonal. Also, let $P$ denote a column vector with element $p_i$ equal to the price of bond with maturity $T_i$. In particular, we have
$$
\begin{pmatrix}
P_1(0, T_1) \\
P_2(0, T_2) \\
\vdots \\
P_n(0, T_n)
\end{pmatrix} =
\begin{pmatrix}
c_1/2 + 100 & 0 & 0 & \cdots & 0 \\
c_2/2 & c_2/2 + 100 & 0 & \cdots & 0 \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
c_n/2 & c_n/2 & c_n/2 & \cdots & c_n/2 + 100
\end{pmatrix}
\begin{pmatrix}
Z_1(0, T_1) \\
Z_2(0, T_2) \\
\vdots \\
Z_n(0, T_n)
\end{pmatrix}
$$
or, in vector notation
$$
P = CZ
$$
where $Z$ is a column vector with $i$ element equal to $Z(0, T_i)$. Then, we obtain
$$
Z = C^{-1}P
$$

Note that the $P$ vector is made up of the invoice or dirty prices. Here, the securities are handpicked to have zero accrued interest, so this simplifies. The calculations below take the price to be the mean of the bid and ask quotes.

\textbf{(PP)} Use the bond data as of February 17, 2009 and applying formulas on  from TN1, the bootstrapped yields to maturity for maturity 0.5, 1, and 1.5 are calculated as follows:

$$
Z(0, 0.5) = \frac{P_1(0, 0.5)}{1 + \frac{c_1}{2}} = \frac{1.0150}{1 + 0.0175} = 0.9975
$$

$$
Z(0, 1) = \frac{P_2(0, 1) - \frac{c_2}{2} Z(0, 0.5)}{1 + \frac{c_2}{2}} = \frac{1.0291 - 0.0175 \times 0.9975}{1 + 0.0175} = 0.9942
$$

$$
Z(0, 1.5) = \frac{P_3(0, 1.5) - \frac{c_3}{2} (Z(0, 0.5) + Z(0, 1))}{1 + \frac{c_3}{2}} = \frac{1.0522 - 0.02065 (0.9975 + 0.9942)}{1 + 0.02065} = 0.9907
$$

where the bond prices are determined as the average of bid and ask values.

\textbf{(CP)} Table 1 displays the data from the selected securities. We show the difference in term structure depending on the type of securities used. The left panel shows the bonds that were issued most recently (“new bonds”) while the right panel shows the bonds that were issued long ago. The column type is 2 for a note and 1 for a bond.

\begin{table}[h!]
\centering
\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|}
\hline
Maturity & Type & Coupon & Ask & Bid & $T_i$ & Maturity & Type & Coupon & Ask & Bid & $T_i$ \\
\hline
New Bonds & & & & & & Old Bonds & & & & & \\
20090815 & 2 & 3.5 & 101.4844 & 101.5156 & 0.4944 & 20090815 & 2 & 6 & 102.6797 & 102.7109 & 0.4944 \\
20100215 & 2 & 3.5 & 102.8945 & 102.9258 & 0.9944 & 20100215 & 2 & 6.5 & 105.7461 & 105.7773 & 0.9944 \\
20100815 & 2 & 4.125 & 105.2031 & 105.2422 & 1.4944 & 20100815 & 2 & 5.75 & 107.6875 & 107.7344 & 1.4944 \\
20110215 & 2 & 5 & 108.5313 & 108.5625 & 1.9944 & 20110215 & 2 & 5 & 108.5313 & 108.5625 & 1.9944 \\
20110815 & 2 & 5 & 110.2656 & 110.3125 & 2.4944 & 20110815 & 2 & 5 & 110.2656 & 110.3125 & 2.4944 \\
20120215 & 2 & 1.375 & 100.4453 & 100.4766 & 2.9944 & 20120215 & 2 & 4.875 & 110.7656 & 110.8125 & 2.9944 \\
20120815 & 2 & 4.375 & 110.8672 & 110.8984 & 3.4944 & 20120815 & 2 & 4.375 & 110.8672 & 110.8984 & 3.4944 \\
20130215 & 2 & 3.875 & 109.9063 & 109.9531 & 3.9944 & 20130215 & 2 & 3.875 & 109.9063 & 109.9531 & 3.9944 \\
20130815 & 2 & 4.25 & 112.1563 & 112.2188 & 4.4944 & 20130815 & 2 & 4.25 & 112.1563 & 112.2188 & 4.4944 \\
20140215 & 2 & 4 & 111.6719 & 111.7344 & 4.9944 & 20140215 & 2 & 4 & 111.6719 & 111.7344 & 4.9944 \\
20140815 & 2 & 4.25 & 113.3594 & 113.3906 & 5.4944 & 20140815 & 2 & 4.25 & 113.3594 & 113.3906 & 5.4944 \\
20150215 & 2 & 4 & 111.9063 & 111.9375 & 5.9944 & 20150215 & 1 & 11.25 & 150.4375 & 150.4688 & 5.9944 \\
20150815 & 2 & 4.25 & 113.2031 & 113.2344 &6.4944 & 20150815 & 1 & 10.625 & 149.9219 & 149.9531 & 6.4944 \\
20160215 & 2 & 4.5 & 114.875 & 114.9063 & 6.9944 & 20160215 & 1 & 9.25 & 142.7813 & 142.8125 & 6.9944 \\
20160815 & 2 & 4.875 & 117.0781 & 117.1094 & 7.4944 & 20160815 & 2 & 4.875 & 117.0781 & 117.1094 & 7.4944 \\
20170215 & 2 & 4.625 & 115.4844 & 115.5313 & 7.9944 & 20170215 & 2 & 4.625 & 115.4844 & 115.5313 & 7.9944 \\
20170815 & 2 & 4.75 & 116.8438 & 116.875 & 8.4944 & 20170815 & 1 & 8.875 & 144.9531 & 145 & 8.4944 \\
20180215 & 2 & 3.5 & 107.5781 & 107.6406 & 8.9944 & 20180215 & 2 & 3.5 & 107.5781 & 107.6406 & 8.9944 \\
20180815 & 2 & 4 & 111.6875 & 111.7188 & 9.4944 & 20180815 & 2 & 4 & 111.6875 & 111.7188 & 9.4944 \\
20190215 & 2 & 2.75 & 100.875 & 100.9375 & 9.9944 & 20190215 & 1 & 8.875 & 149.5938 & 149.625 & 9.9944 \\
20190815 & 1 & 8.125 & 143.8438 & 143.875 & 10.4944 & 20190815 & 1 & 8.125 & 143.8438 & 143.875 & 10.4944 \\
20200215 & 1 & 8.5 & 147.7266 & 147.7578 & 10.9944 & 20200215 & 1 & 8.5 & 147.7266 & 147.7578 & 10.9944 \\
20200815 & 1 & 8.75 & 151.1563 & 151.1875 & 11.4944 & 20200815 & 1 & 8.75 & 151.1563 & 151.1875 & 11.4944 \\
20210215 & 1 & 7.875 & 143.5391 & 143.5703 & 11.9944 & 20210215 & 1 & 7.875 & 143.5391 & 143.5703 & 11.9944 \\
20210815 & 1 & 8.125 & 147.1094 & 147.1406 & 12.4944 & 20210815 & 1 & 8.125 & 147.1094 & 147.1406 & 12.4944 \\
\hline
\end{tabular}
\caption{Securities used in Bootstrap}
\end{table}

Figures 1 and 2 plot the discount function and the yield curve implied by these calculations. The vertical dotted line denotes the point at which bond securities are used to bootstrap also for the “new bonds”. Clearly, depending on the type of securities used, we can get quite different results. The period surrounding 2009 showed large differences between new bonds and old bond prices, due to liquidity. Newly issued bonds were much more liquid than old bonds, which resulted in large price discrepancies. (The comparison between old and new bonds was not part of the assignment).

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_0.png}
\caption{Zero Coupon Discount Curves}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{2_image_0.png}
\caption{Zero Coupon Yield Curves}
\end{figure}

\subsection*{2. (PP) The value of the Leveraged Inverse Floater can be computed as follows.}

The coupon rate at any time $t$ is given by
$$
c(T_i) = 10\% - 2 \times r_2(T_{i-1}) \quad (1)
$$
The investor who is long the Leveraged Inverse Floater receives a 10% fixed coupon and pays “floating” at the rate that is twice the floating six-month T-bill rate (six months lag). At maturity, in addition, the investor will receive the principal. Therefore, it is as if the investor is long one 10% coupon bond with five years to maturity and short 2 floating rate bonds with five years to maturity. This combination ensures receiving a cash flow over time identical to (1). However, such a position would imply an outflow of the principal at maturity, instead of an inflow. It follows that we need to add two zero coupon bonds with five years maturity to exactly mimic all of the cash flows from the Leveraged Inverse Floater.

\textbf{(CP)} The price of the inverse floater is then
$$
P_{IFL}(0; 5) = P_{Fixed}(0, 5) - 2 \times P_{Fl}(0; 5) + 2 \times Z(0; 5) \quad (2)
$$
Given the discount function in Table 1 above, we have
$$
P_{Fixed}(0; 5) = 140.74; \quad (3)
$$
$$
P_{Fl}(0; 5) = 100; \quad (4)
$$
$$
Z(0; 5) = 92.35 \quad (5)
$$
obtaining a value for the Leveraged Inverse Floater equal to
$$
P_{IFL}(0; 5) = 125.43
$$
Note that in the computation above we are implicitly assuming that the coupon $c(T_i)$ will never get negative, as the Leverage Inverse Floater would never require an additional payment from investors.

\textbf{(PP)} What is the benefit from going long the Leveraged Inverse Floater? The current semi-annual rate on February 17, 2009 was 0.49%. Therefore, the current cash flow from this security is 9.02% so long as the short-term rate does not increase. Given the data above, a fixed rate coupon bond with a 5-year maturity has a coupon equal to $c = 4.0\%$. Of course, this bond is also cheaper at 111.70. However, the discount function above implies that the price of a fixed-rate 5-year bond with a coupon of 9.2% would have a price of 135.97. As long as the short rate does not move, the Leveraged Inverse Floater generates a higher cash flow without increasing the price comparably. For this reason, investments in this type of instrument are called “yield enhancing strategies”. Yet, they imply a speculation on the direction of interest rates movements, as discussed next.

\subsection*{3. (PP) The duration of the fixed rate bond is based on the following general formula}

$$
D_{Fixed} = \sum_{i=1}^n w_i T_i = 4.2141
$$
where $T_i = 0.5, 1, \ldots, 5$ and
$$
w_i = \frac{Z(0; T_i) c_i/2}{P_{Fixed}} \quad \text{for } i = T_i = 0.5, \ldots, 4.5 \quad \text{and} \quad w_n = \frac{Z(0; T_n) (1 + c_i/2)}{P_{Fixed}} \quad \text{for } T_n = 5.
$$

The duration of the Leveraged Inverse Floater can be computed from the rule “the duration of a portfolio is equal to the weighted average of the durations.” So, first, we need to compute the duration of each of the securities in formula (2). The duration of the zero coupon bond $Z(0, 5)$ is $D_Z = 5$, while the duration of the Floating Rate Bond is $D_{Fl} = 0.5$, six months, and the duration of the fixed rate bond is $D_{Fixed} = 4.2141$ as shown above.

\textbf{(CP)} It then follows that the duration of the Leveraged Inverse Floater is
$$
D_{LIF} = \frac{1}{P_{LIF}} \left( P_{Fixed}(0, 5) \times D_{Fixed} - 2 \times P_{Fl}(0; 5) \times D_{Fl} + 2 \times Z(0; 5) \times D_Z \right)
$$
$$
= \frac{1}{125.43} \left( 140.74 \times 4.214 - 2 \times 1 \times 0.5 + 2 \times 92.35 \times 5 \right) = 11.29
$$

\textbf{(PP)} According to the duration of LIF of 11.29, it is obvious that it has quite a high sensitivity to interest rates. Figure 3 plots the value of the Leveraged Inverse Floater, plotted against a parallel shift in the term structure of interest rates. The decline in value for a shift up in interest rates is quite dramatic. The dash-dotted line plots the decline in value for the 5-year fixed rate bond, with coupon rate 4.0%, which is valued at 111.70 on February 17, 2009. The duration of the 5-year fixed bond is 4.60. Thus, the sensitivity to interest rates is much smaller, as illustrated in Figure 3.

Finally, note in Figure 3 that the perturbations are mainly positive. This is because the short rate is already at 0.49%, so negative parallel shifts must be quite small to keep the short rate sensible.

\textbf{(PP)} In general, convexity of the fixed rate bond is calculated as follows:
$$
C_{Fixed} = \sum_{i=1}^n w_i T_i^2 = 19.6431
$$

Accordingly, convexity of the inverse floater can be computed as the weighted average of the convexities of the securities in the mimicking portfolio. The convexity of the zero coupon bond is $C_Z = 5^2 = 25$, while the convexity of the floating rate bond is essentially zero $C_{Fl} = 0.5^2 = 0.25$.

\textbf{(CP)} It follows that the convexity of the inverse floater is
$$
C_{LIF} = \frac{1}{P_{LIF}} \left( P_{Fixed}(0, 5) \times C_{Fixed} - 2 \times P_{Fl}(0; 5) \times C_{Fl} + 2 \times Z(0; 5) \times C_Z \right)
$$
$$
= \frac{1}{125.43} \left( 140.74 \times 19.6431 - 2 \times 100 \times 0.25 + 2 \times 92.35 \times 25 \right) = 58.45
$$
Compare this to the quoted 5-year fixed rate bond which has a much lower convexity of 22.30.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Interest Rate Sensitivity}
\end{figure}

\end{document}
```

### HW 3

```
\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 3}
\author{John Heaton}
\date{April 7, 2024}

\begin{document}
\maketitle

\section*{Part I. Duration Hedging and Factor Neutrality}

For simplicity, we are going to assume that at the two dates the LIF still has 5 years to maturity. To find the price of the LIF, we need to find zero coupon prices to discount the cash flows of the security. The $Z$'s are embedded in the yield curve data given so we need to extract them. Unlike homework 2, this time we cannot proceed by bootstrapping since we do not have price data for bonds of different maturities as of each date. An alternative is to interpolate the zero-coupon yield curve using the data given. Interpolation is fine in this case because these are zero coupon yields, and so there is no theoretical error in doing this approximation. In Matlab we can do the interpolation as follows:

$$
Y_{\text{int}} = \text{interp1}(\text{Mat}, \text{yields}, \text{MatInt}, 'cubic')
$$

where Mat is a vector of the maturities for which we have data, yields is a vector with the corresponding data on yields, MatInt is the vector of maturities (in this case semi-annual) for which we need yields, and cubic is just the interpolation method (cubic uses a polynomial of degree 3 to approximate the yield curve).

Once we have built the yield curve we can back out the $Z$'s and calculate the value of the LIF as we did in homework 2. The price of the LIF as of the two dates is:

\begin{table}[h!]
\centering
\begin{tabular}{l c}
\hline
 & LIF Prices \\
\hline
$P_{\text{LIF}}$ March 31, 2009 & 124.30 \\
$P_{\text{LIF}}$ April 30, 2009 & 119.04 \\
\hline
\end{tabular}
\caption{LIF Prices}
\end{table}

Now we can compare the change in price between the two dates with the one predicted by the duration and convexity calculation performed in homework 2. For the duration-based calculation, we need to compute an average change across maturities. The reason is that duration refers to a price change as a result of a parallel shift in the term structure, which means that we need to summarize the change in the yield curve by just one number. The results are:

\begin{table}[h!]
\centering
\begin{tabular}{l c c c}
\hline
 & Dur-based Return (\%) & Dur/Conv-based Return (\%) & Actual Return (\%) \\
\hline
Return (\%) & -2.015 & -2.005 & -4.233 \\
\hline
\end{tabular}
\caption{Duration and Convexity Approximations}
\end{table}

As we can see, both the duration-based computation and the duration/convexity-based computation understate the change in value. The reason is that the yield curve is changing its shape in a non-parallel manner as shown in Figure 1. One way to take into account these non-parallel changes is to use two or more factors from the principal components analysis.

The principal components approach is explained in detail in TN2. Notice that the magnitude of the eigenvalues is related to the proportion of the variance in the data explained by their corresponding factors. Matlab orders the eigenvalues in ascending order. Therefore, if we want to use a two-factor model the eigenvectors that we must use are the last two in the matrix of eigenvectors (with eigenvalues $\lambda_1 = 1.581$ and $\lambda_2 = 0.103$). The following are the betas corresponding to the first two factors:

\begin{table}[h!]
\centering
\begin{tabular}{c c c}
\hline
Maturity (years) & $\beta_{1,i}$ & $\beta_{2,i}$ \\
\hline
0.5 & 0.3391 & 0.6615 \\
1 & 0.3657 & 0.3785 \\
1.5 & 0.3519 & 0.1677 \\
2 & 0.3321 & -0.0047 \\
2.5 & 0.3178 & -0.1024 \\
3 & 0.3060 & -0.1752 \\
3.5 & 0.2976 & -0.2558 \\
4 & 0.2900 & -0.3132 \\
4.5 & 0.2804 & -0.3182 \\
5 & 0.2669 & -0.2916 \\
\hline
\end{tabular}
\caption{Factor Betas}
\end{table}

As in the teaching notes, the first factor came out to have loadings (i.e. $\beta$'s) approximately constant across maturities, and for this reason can be referred to as a "level" factor. The second factor has loading that switches sign between positive (at the short end) to negative (at the long end), implying that when this factor kicks in, the short-end of the term structure increases, while the long end decreases. Such a behavior implies a shift in the slope of the term structure, from which the name “Slope factor”. Note that differently from the TN, the betas of the second factor are positive at the short end and negative at the long end of the maturity spectrum, rather than the other way around. In PCA there is an indeterminacy between the signs of $\beta$'s and the sign of the factor. If we define a new factor $\tilde{\phi}_2 = -\phi_2$, we obtain a factor that has loadings that are negative at the short end and positive at the long end of the maturity spectrum. The important fact is that when this factor kicks in, it changes the slope.

To calculate the factor durations we use the formulas in TN2. The duration of the LIF and its components with respect to the level and slope factors is:

\begin{table}[h!]
\centering
\begin{tabular}{l c c}
\hline
Security & Level Duration & Slope Duration \\
\hline
LIF & 3.007 & -3.953 \\
Fixed & 1.155 & -1.118 \\
Zero & 1.335 & -1.458 \\
Floating & 0.170 & 0.331 \\
\hline
\end{tabular}
\caption{Factor Durations}
\end{table}

With the factor durations, now we can calculate the predicted change in the value of the LIF given the change in the factors between the two dates as follows:
$$
\% \Delta P_{\text{LIF}} = -D_{\text{LIF,level}} \times \Delta \phi_{\text{level}} - D_{\text{LIF,slope}} \times \Delta \phi_{\text{slope}}
$$

\begin{table}[h!]
\centering
\begin{tabular}{l c c c c}
\hline
 & Dur-based Return (\%) & Dur/Conv-based Return (\%) & Factor-Based Return (\%) & Actual Return (\%) \\
\hline
Return (\%) & -2.015 & -2.005 & -3.786 & -4.233 \\
\hline
\end{tabular}
\caption{Duration, Convexity, and Factor Approximations}
\end{table}

We see that the factor-based prediction is much closer to the actual return. The reason is that the factors incorporate changes along the entire term structure taking into account that those changes do not affect all maturities in the same magnitude or in the same direction.

\section*{Part II: Predictability of Bond Returns}

We start by looking at some plots. Consider the forward spread and the annual return on the 5-year bond. Figure 3 shows their time series, where we lag the return by 5 years to make it synchronous with the forward spread so as to highlight the correlation (if any).

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Annual Returns of 5-year Bond and 5-year Forward Spread}
\end{figure}

Figure 4 also shows a scatter plot of the 5-year forward spread versus the bond return of a 5-year bond. The figures show an association between forward rates and subsequent bond returns, although the cloud is rather wide and so the forward spread does not appear to explain a lot of the variation in bond returns. Figure 5 shows the (in sample) fit of the model, when we predict future bond returns using the lagged forward spread.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{4_image_0.png}
\caption{Realized 5-year Bond Return vs 5-year Forward Spread}
\end{figure}

Table 6 below formalizes this evidence using OLS regressions. We regress the log excess bond return on the forward spread. Let $Z_t(n)$ denote the zero coupon bond in year $t$ with $n$ years to maturity. Define the log excess bond return using a $n$-year bond as
$$
LER_t(n) = \log \left( \frac{Z_{t+1}(n-1)}{Z_t(n)} \right) - \log \left( \frac{1}{Z_t(1)} \right)
$$
Denote also $f_t(n)$ the forward rate at $t$ for an investment at $n-1$ and maturity $n$. As we know $f_t(n) = \log \left( \frac{Z_t(n)}{Z_t(n-1)} \right)$. We then run the regression
$$
LER_t(n) = \alpha + \beta [f_t(n) - y_t(1)] + \epsilon_t
$$

Table 6 shows the results for each zero-coupon bond with maturity $n = 2, \ldots, 5$.

\begin{table}[h!]
\centering
\begin{tabular}{l c c c c c}
\hline
n & $\alpha$ & $\beta$ & $t(\alpha)$ & $t(\beta)$ & $R^2$ \\
\hline
2.0000 & 0.0467 & 0.7926 & 0.1937 & 2.4776 & 0.0839 \\
3.0000 & -0.0935 & 1.0326 & -0.1907 & 2.4469 & 0.0820 \\
4.0000 & -0.0918 & 1.0014 & -0.1327 & 2.1900 & 0.0668 \\
5.0000 & -0.2947 & 1.1750 & -0.3536 & 2.3812 & 0.0780 \\
\hline
\end{tabular}
\caption{Fama - Bliss Regressions 1953 - 2023}
\end{table}

Note the implication of the empirical results:
\begin{itemize}
    \item A high forward spread $\implies$ predict high future bond excess return.
    \item A positive bond excess return requires its yield to decline (yield $\downarrow \implies Z(t, n) \uparrow$)
    \item The forward spread is high when the term structure slopes upwards
    \item $\implies$ a rising term structure predicts lower future yields.
\end{itemize}

\subsection*{Cochrane - Piazzesi Factor}

Cochrane - Piazzesi propose a single factor to predict future bond returns. In essence, they define a factor as a linear combination of forward rates
$$
x_t = a_0 y_t + a_1 f^{(2)}_t + \ldots + a_5 f^{(5)}_t
$$

The coefficients $a_0, \ldots, a_5$ are estimated from another regression of average bond returns on forward rates. (This is slightly different from the question in the assignment, in which you were allowed to (a) use the regression coefficient in the Teaching Notes; and (b) use only 3 forwards instead of 5 as in the original Cochrane and Piazzesi paper). Table 7 shows the results of the regression.

\begin{table}[h!]
\centering
\begin{tabular}{l c c c c c}
\hline
n & $\alpha$ & $\beta$ & $t(\alpha)$ & $t(\beta)$ & $R^2$ \\
\hline
2.0000 & -0.0353 & 0.4761 & -0.1501 & 3.1582 & 0.1296 \\
3.0000 & -0.0791 & 0.8960 & -0.1848 & 3.2647 & 0.1372 \\
4.0000 & -0.1820 & 1.2770 & -0.3113 & 3.4044 & 0.1475 \\
5.0000 & -0.4561 & 1.6369 & -0.6162 & 3.4468 & 0.1506 \\
\hline
\end{tabular}
\caption{Cochrane - Piazzesi Regressions: 1953 - 2023}
\end{table}

Figures 6 to 8 show the performance of the CP factor to predict the return of a 5-year bond. Note that Figure 8 shows that the expected excess return predicted by CP factor at the end of the sample is negative. That is, the model implies a negative risk premium on the 5-year bond for the next year.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{6_image_0.png}
\caption{Annual Returns of 5-year Bond and CP Factor}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{7_image_0.png}
\caption{Realized 5-year Bond Return vs 5-year CP Factor}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{8_image_0.png}
\caption{5-year Bond Return and Predicted Return from CP Factor}
\end{figure}

\subsection*{In-Sample vs Out-of-Sample Predictive Regressions (this was not part of the assignment)}

One important issue with the Cochrane - Piazzesi factor compared to Fama - Bliss is that the CP regression is in sample. That is, the factor CP is first computed with a regression over the overall sample, and then it is used to predict future bond returns. For the purpose of the paper – namely, the inference about the existence of a common factor affecting bond returns – the procedure is fine. The objective of investigation in Cochrane and Piazzesi was to discover if there is a common factor affecting all bond expected excess returns. In sample regressions are perfectly fine for this investigation. However, if we want to have an investment strategy we cannot use an in-sample regression, but we need an out-of-sample one. One possibility is to use data up to $t$ to compute the CP factor, and then use data after $t$ for the regression. This can be done. However, another methodology is to just use the forward rates used by CP to predict future bond returns. That is, run

$$
LER_t(n) = \alpha + \beta_1 y_t(1) + \beta_2 f_t(3) + \beta_3 f_t(5) + \epsilon_t
$$
(we leave out $f_t(2)$ and $f_t(4)$ to avoid multicollinearity). Table 8 reports the result. As can be seen, using the forward rates has a strong predictive power on future bond returns. That is, the results of the CP factor are not only due to it being an in-sample predictor, but there is something in the forward rates that help explain future bond returns.

\begin{table}[h!]
\centering
\begin{tabular}{l c c c c c c c c}
\hline
n & $\alpha$ & $y_t(1)$ & $f_t(3)$ & $f_t(5)$ & $t(\alpha)$ & $t(y_t(1))$ & $t(f_t(3))$ & $t(f_t(5))$ & $R^2$ \\
\hline
2.0000 & -0.9287 & -0.4445 & 0.5145 & 0.1040 & -2.0245 & -1.8193 & 1.0977 & 0.3114 & 0.1473 \\
3.0000 & -1.3791 & -1.0557 & 1.3420 & -0.0475 & -1.6366 & -2.3523 & 1.5585 & -0.0774 & 0.1395 \\
4.0000 & -1.8014 & -1.6754 & 2.0315 & -0.0831 & -1.5644 & -2.7319 & 1.7265 & -0.0991 & 0.1500 \\
5.0000 & -2.6458 & -2.0297 & 1.9953 & 0.3936 & -1.8130 & -2.6116 & 1.3381 & 0.3705 & 0.1515 \\
\hline
\end{tabular}
\caption{Forward-based Regressions: 1953 - 2023}
\end{table}

\subsection*{PCA Regressions (Also this part was not part of the homework)}

A final interesting question is whether PCA factors – level, slope, and curvature factors – described in the previous section, are able to explain future bond returns. Indeed, slope has been used several times as a predictor of future bond returns. Table 9 shows the result. Interestingly these factors are also predicting returns.

\begin{table}[h!]
\centering
\begin{tabular}{l c c c c c c c c}
\hline
n & $\alpha$ & Level & Slope & Curvature & $t(\alpha)$ & $t(\text{Level})$ & $t(\text{Slope})$ & $t(\text{Curvature})$ & $R^2$ \\
\hline
2.0000 & -0.5401 & -0.0147 & -0.4397 & 0.9258 & -1.3640 & -0.4423 & -2.0009 & 1.1241 & 0.1319 \\
3.0000 & -1.0036 & -0.0382 & -0.9823 & 1.2145 & -1.3835 & -0.6271 & -2.4399 & 0.8049 & 0.1286 \\
4.0000 & -1.5253 & -0.0715 & -1.5455 & 1.5574 & -1.5478 & -0.8642 & -2.8258 & 0.7598 & 0.1494 \\
5.0000 & -2.2703 & -0.1024 & -2.1469 & 1.7551 & -1.8359 & -0.9864 & -3.1282 & 0.6823 & 0.1675 \\
\hline
\end{tabular}
\caption{PCA Regressions: 1953 - 2023}
\end{table}

\end{document}
```

### HW 4

```
\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 4}
\author{John Heaton}
\date{April 14, 2024}

\begin{document}
\maketitle

\section*{Part I: Real and Nominal Bonds}

The relation between nominal rates and real rates is
$$
r_{\text{nominal}}(T) = r_{\text{real}}(T) + \pi(T) - \frac{1}{2}\sigma^2_\pi + \text{RP}
$$
That is, the nominal rate equals the real rate, plus expected inflation (this is the Fisher equation) plus a risk premium (RP) minus a (minor) convexity term, as inflation increases nominal bonds in a convex manner. Higher expected inflation or higher risk premia increase the nominal rate. See discussion in the teaching notes.

The real rate can be negative. From the above relation, this may simply mean that expected inflation is higher than the nominal rate (and the other terms). However, economically, why can a negative real rate occur? A simple decomposition of real rates has
$$
r_{\text{real}}(T) = \rho + \gamma \text{Expected GDP Growth} - \frac{\gamma^2}{2} \text{Macroeconomic Risk}
$$
That is, why would an investor buy Treasury bonds? To set aside the issue of inflation, consider TIPS (or real bonds). Why would an investor buy real bonds? Well, for saving purposes. However, this desire to save depends on two quantities: The prediction of economic growth and the amount of uncertainty in the economy. The higher the expected economic growth, the lower is the interest in savings. If the economy is strong, our jobs are secure, etc., then we can actually borrow (save less) to purchase homes, cars, and the like. This willingness of people to borrow for consumption tends to increase real rates ($r_{\text{real}}(T)$ increases). On the other hand, the higher the macroeconomic risk in the economy, the higher is the likelihood of “rainy days” which provides an incentive to borrow less and rather purchase bonds (real bonds) to have a buffer against bad times (many financial advisors recommend families to set up “emergency funds”. Well, do not invest your emergency fund in stocks, as you may need it exactly in bad times!). This savings requirement for rainy days tends to decrease bond rates (as households bid up the price of bonds).

Negative rates therefore may be due to a combination of low economic growth prospects but large macroeconomic risk. These quantities are weighted by the risk aversion $\gamma$ of agents in the economy: the higher the risk aversion and the stronger the effects.

How do risk premia affect all this? In the first quarter of 2013, the median forecast of professional forecasters about the average three-month rate for the next 10 years was 2.4\%. Our estimates of the yield curve on Jan 15, 2013 show a 10-year yield around 2\%. This implies that the average expected future short-term rate over the next 10 years is 0.4\% higher than the 10-year yield. From the simple formula in TN3
$$
y_t(10) = E_t \left[ \frac{1}{n} \sum_{i=1}^{n} y_{t+i}(0.25) \right] + \text{RP}_t
$$
where $n = 40$ is the number of quarters in 10 years. If the yield is lower than the expected future yield, according to the expectation hypothesis, it should be due to a negative risk premium. A negative risk premium can occur whenever Treasury bonds have hedging properties against variation in the stock market.

We finally move to fit the Nelson-Siegel model to the TIPS on Jan 15, 2013. From the formula in the teaching notes
$$
P_{\text{TIPS}} = \frac{\text{Idx}(T)}{\text{Idx}(0)} \left[ \sum_{i=1}^{n} \frac{c}{2} Z(0, T_i) + Z(0, T_n) \right]
$$
Quoted prices are already net of the index ratio. Moreover, there is no accrued interest because the maturity is on the round semi-annual cycle. Therefore, bid/ask reflect only the parenthesis itself. This makes it easier to compute the term structure of real rates then, because we can use directly the bid/ask price (midpoint) and use those directly together with the cash flow matrix to compute the real zero coupon bonds.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_0.png}
\caption{Fitting of the NS Model to TIPS Data}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{2_image_0.png}
\caption{Real Discount Factor}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Real Yield}
\end{figure}

We next fit the nominal yields using the NS model to the data. In this case, there are many more data points than in the case of real bonds, but the model does a good job in fitting the data, as shown in Figure 4.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{4_image_0.png}
\caption{Fitting of the NS Model to Nominal Bond Data}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{5_image_0.png}
\caption{Nominal Discount Factor}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{6_image_0.png}
\caption{Nominal Yield and Forward Curve}
\end{figure}

We finally use the nominal yields and the real yield to compute “breakeven inflation rates”, that is, the difference between the nominal and the real yield. These are shown in Figure 7. The breakeven rate ranges between 2\% and 2.7\%. These implied forecasts of inflation rates seem reasonable, although we should always remember that the difference between nominal and real yields also includes risk premia. Breakeven rates depend on risk premia, as explained above. Interestingly, from the survey of professional forecasters, we find that the median forecast of average CPI inflation for the next 10 years is 2.3\%, a bit lower than the breakeven inflation rate at the 10-year mark, which is around 2.67\%. The difference could be due to a positive risk premium RP, as discussed above. Indeed, we have
$$
\text{RP} = 2.67\% - 2.4\% + \frac{1}{2}\sigma^2_\pi = 0.27\% + \frac{1}{2}\sigma^2_\pi
$$
This positive risk premium is in contrast with the negative risk premium obtained above using the forecasts of future short-term rates.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{7_image_0.png}
\caption{Break Even Rate}
\end{figure}

\section*{Part II: Swap Spread Trades}

\subsection*{1. Data on February 17, 2009}

LIBOR(0) = 1.25\%, Repo(0) = 0.30\%, Thirty-year Swap Rate = 3.21\% while the price and coupon of a thirty-year note were $P(0, 30) = 100.36$ and $c = 3.50\%$, respectively. The (semi-annually) compounded yield to maturity of the 30-year note $y$ is obtained from the formula
$$
100.36 = \frac{c}{2} \sum_{j=1}^{60} \frac{1}{(1 + \frac{y}{2})^j} + \frac{1}{(1 + \frac{y}{2})^{60}}
$$
Computation gives $y = 3.49\%$, very close to the constant maturity rate for the same maturity, which was $\text{CMT} = 3.47\%$. We can define the swap spread in various ways, but it is essentially the difference in coupon from a swap and the YTM on the Treasury. (Here, this is almost the exact same as using the coupon of the treasury instead. This is because the bond is trading near par.) Thus $\text{SS} = 3.21\% - 3.49\% = -28$ basis points. Additionally, the LIBOR-repo spread, or LRS, is $1.25 - 0.30 = 0.95\%$. In the past, we typically observed a fixed rate on the swap that is larger than the treasury. In this case, the issue was whether the excess was large enough to make up for the loss on the LRS given that the trade involves receiving repo and paying LIBOR. (For instance, see Figure 8 for a feel of how the trade worked.) However, in this situation, a trader can make money on both ends of the deal by doing the opposite. Namely,

\begin{itemize}
    \item[(a)] Go long the 30-year bond through a repo transaction. In cash flow terms, pay Repo and receive the treasury coupon.
    \item[(b)] Enter into a fixed for floating swap in which I receive LIBOR and pay the fixed.
\end{itemize}

The net quarterly cash flows are
$$
CF(T_i) = 0.25 \times [\text{Coupon} - \text{Repo}(T_{i-1})] + 0.25 \times [\text{LIBOR}(T_{i-1}) - \text{Swap Rate}]
$$
where notice that we consider an “accrued” coupon to be “paid” at quarterly frequency, for simplicity.

More precisely, consider a trade of size \$100 million. The number of T-Notes (with 100 principal) corresponding to \$100 million is $N = 9,964,191$. Therefore, adjusting for the size of the trade, and assuming no haircut, the cash flow at time $T_i$ is
$$
CF(T_i) = 0.25 \times [N \times \text{coupon} - 100 \text{mil} \times \text{Swap Rate}] + 100 \text{mil} \times 0.25 \times [\text{LIBOR}(T_{i-1}) - \text{Repo}(T_{i-1})]
$$

\subsection*{2. Cash Flow Calculation}

Use the above cash flow equation to get that the first cash-flow realized is $CF (\text{May}) \approx \$305,774.23$ (for an annualized value of \$1,223,096.92 if rates were to hold constant).

The first term in $CF(T_i)$ above is always the same each quarter, as neither the swap rate nor the coupon of the initial swap and T-note change over time. The second parenthesis is instead reset every 3 months. Still, the trade would be profitable unless LIBOR dropped to where it was below the repo rate, which is quite unlikely given the lower risk of collateralized debt. Thus, the trade locks in the less stable profit, the SS, and profits on the stable fact that LIBOR is above repo. See Figure 8 for the historical relationship using 5-year swaps and 5-year coupon bonds.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{8_image_0.png}
\caption{5-year Swap Spread and Funding Spread Over Time}
\end{figure}

Figure 9 uses daily data to illustrate the evolution of the LRS side of the trade over the following quarters (for this solution, the data have been updated to June 2010, for illustrative purposes). The spread drops substantially—almost half—but is still well above zero. Combined with the locked-in profit on the SS side, the trade is still generating positive cash-flow.

Given the data provided, we only have one quarter of data after the position is put on, so it would seem that we can only calculate one cash flow generated by the trade. However, we can actually compute the cash flow for August using the data given in May. The SS cash flow is fixed, and the August LRS cash flow depends on LIBOR and the repo rate quoted one quarter earlier—the floating part resets one quarter before payment. With updated data to June 2010, we can follow the cash flows all the way to August 2010. Figure 10 displays the cash flows of the trade, and Figure 11 displays the net cash flows.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{9_image_0.png}
\caption{Repo and LIBOR Rates}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{10_image_0.png}
\caption{Cash Flows of the Trade}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{11_image_0.png}
\caption{Net Cash Flows of the Trade}
\end{figure}

\subsection*{3. Value of the Position}

From the strategy above, we are long $N$ T-notes, short \$100 million in the Repo market, and short a fixed for floating swap. The computation of the value of the long T-note (minus Repo) is straightforward. Assuming we take the repo interest paid over time, the value of this position at reset dates is
$$
V_{\text{T-Note}} = N \times P(t;T) - 100 \text{mil}
$$
where $P(t;T)$ is the value of the 30-year note.

To value the swap is slightly more cumbersome, as we need to compute the value of the swap as the swap rate changes over time. Recall that the value of the swap at the reset date is
$$
V_{\text{Swap}} = P_{\text{Fixed}}(0;T) - P_{\text{Fl}}(0;T)
$$
where $P_{\text{Fixed}}(0;T)$ is the value of the fixed rate bond implicit in the fixed part of the swap. In particular, the coupon on this component equals the swap rate at initiation, namely, $c_{\text{swap}} = 3.21\%$. Therefore, at every reset date $T_i$, let $n_i$ be the number of remaining payments in the swap. We have
$$
P_{\text{Fixed}}(T_i;T) = \frac{c_{\text{swap}}}{4} \sum_{j=1}^{n_i} Z_{\text{LIBOR}}(T_i;T_j) + Z_{\text{LIBOR}}(T_i;T_{n_i})
$$
If we knew the LIBOR curve $Z_{\text{LIBOR}}(T_i;T_j)$, we are done. We can use current swap rates to compute the LIBOR curve every $T_i$. Since we only have a sample of swap rates in the data set, we need to interpolate to a quarterly frequency. After having interpolated, at every $T_i$ we have a set of swap rates $c_{\text{swap}}(T_i;T_j)$ for maturity $T_j$, $j = i+1, i+2, \ldots$. From the swap rates, we can finally obtain the LIBOR curve from the following bootstrap procedure
$$
Z_{\text{LIBOR}}(T_i;T_{i+1}) = \frac{1}{1 + \text{LIBOR}(T_i) \times 0.25}
$$
$$
Z_{\text{LIBOR}}(T_i;T_j) = \frac{1 - 0.25 \times c(T_i;T_j) \sum_{k=1}^{j-1} Z_{\text{LIBOR}}(T_i;T_{i+k})}{1 + c(T_i;T_j) \times 0.25}
$$

From the swap curve, we can compute the value of the fixed leg of the swap.

The floating leg of the swap is much simpler, as $P_{\text{Fl}}(0;T) = 1$. The value of the swap follows.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{12_image_0.png}
\caption{Value of Short Swap and Repo}
\end{figure}

Figure 12 plots the value of the swap and the Treasury (minus Repo) over time. Both start at zero by construction, and as rates change, so do the value of both quantities. In particular, the price of the T-note decreased, and so did the treasury coupon minus repo position. This was partly offset by the increase in value in the swap trade. However, Figure 13 shows that the T-note price dropped by more than the increase in the swap value, generating a drop in the value of the overall position. Thus, while the cash flows are positive, there is a capital loss if the position is unwound after a quarter. Still, the capital loss due to moving rates is small relative to the positive cash flows.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{13_image_0.png}
\caption{Total Value of Short Swap Spread Position}
\end{figure}

\subsection*{4. Arbitrage Opportunity?}

It is important to consider whether the above trade is an arbitrage opportunity. As mentioned earlier, the cash flows are comprised of two parts, the SS and LRS. The former is fixed every period, and we showed that by taking the short end it will be a positive inflow. The LRS varies with changes in LIBOR and the repo, but we strongly expect LIBOR to always be larger as securitized loans (the repo) are less risky. Thus, while the amount gained from the LRS varies it is incredibly unlikely it will become negative, especially so negative as to outweigh the positive flow from the SS position. Thus, by holding the position to maturity one realizes positive cash flows for 30 years and does not need to worry about possible losses from unwinding early.

In this view, the above trade is an arbitrage. However, this conclusion hinges on the ability to hold the position to maturity. Unwinding the position early could induce significant losses, as demonstrated above in Figure 13, due to the fact that the value of the position fluctuates up until maturity where it is known. In fact, the fluctuating value of the position exposes the trade to margin calls. While the value is fixed at $T = 30$, in the meantime, the value could plummet to the point where the margin calls are significant. Thus, the trade is exposed to funding risk. It is likely that this funding risk is what kept traders from exploiting the apparent arbitrage in February. Given the financial turmoil, few were willing to deal with the potential margin calls and possible short-term losses even though they were assured profits in the long run.

\end{document}
```

### HW 5

```
\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 5}
\author{John Heaton}
\date{April 22, 2024}

\begin{document}
\maketitle

\section*{Part I: Using Black’s formula for Caps, Floors, and Swaptions}

\subsection*{1. (CP) Use the data in the attached Bloomberg screen to compute:}
\begin{itemize}
    \item The dollar value of a two-year Cap;
    \item The dollar value of a 1-year swaption to enter into a 5-year swap.
\end{itemize}

\subsection*{2. (PP) Option-Pricing Formulas}
Illustrate the option-pricing formulas used for:
\begin{itemize}
    \item The first caplet in the cap (i.e. the one with 6-months to maturity);
    \item The swaption.
\end{itemize}
Show your work.

We first interpolate the available Swap data to fill in the curve for the quarterly maturities. The zero yield on the Zero with maturity of 0.25 is given by the first interpolated swap rate:
$$
Z(0, 0.25) = \frac{1}{1 + c(0.25) \times 0.25}
$$

Beyond that date we use the Bootstrap method:
$$
Z(0.5) = \frac{1 - c(0.5) \times 0.25 \times Z(0.25)}{1 + c(0.5) \times 0.25}
$$

$$
Z(T) = \frac{1 - c(T)\Delta \sum_{t=0.25}^{T-0.25} Z(t)}{1 + c(T) \Delta}
$$

Clearly, there are important issues here:
\begin{itemize}
    \item The interpolation is only approximate. We normally have far more data to do this.
    \item We have anchored the swap curve with the one-month LIBOR curve. LIBOR is for uncollateralized borrowing – and thus is risky – while swaps now are fully collateralized, and thus there is less risk.
\end{itemize}

\subsection*{3. Forward Rates}
Once we have the zero-coupon curve, we can compute quarterly forward rates from the forward discount:
$$
F(0, T_i, T_{i+1}) = \frac{Z(0, T_i)}{Z(0, T_{i+1})}
$$

\subsection*{4. Caplets and Swaptions}
From the forward rates, we employ the formula in the teaching notes to compute the caplets. The following table shows the results for the interpolations of the 1st and 2nd caplet and the swaption:

\begin{table}[h!]
\centering
\begin{tabular}{cccccc}
\hline
i & $T_i$ & Interpolate & $Z(0, T_i)$ & Fwd Discount & Rate Discount \\
\hline
1 & 0.25 & 0.003212 & 0.99920 & & \\
2 & 0.50 & 0.003428 & 0.99829 & 0.99909 & 0.00364 \\
3 & 0.75 & 0.003569 & 0.99733 & 0.99904 & 0.00385 \\
4 & 1.00 & 0.003620 & 0.99639 & 0.99906 & 0.00377 \\
5 & 1.25 & 0.003558 & 0.99556 & 0.99917 & 0.00331 \\
6 & 1.50 & 0.003422 & 0.99488 & 0.99932 & 0.00274 \\
7 & 1.75 & 0.003285 & 0.99427 & 0.99939 & 0.00246 \\
8 & 2.00 & 0.003220 & 0.99358 & 0.99931 & 0.00276 \\
9 & 2.25 & 0.003216 & 0.99279 & 0.99921 & 0.00318 \\
10 & 2.50 & 0.003213 & 0.99201 & 0.99920 & 0.00318 \\
11 & 2.75 & 0.003211 & 0.99121 & 0.99920 & 0.00319 \\
12 & 3.00 & 0.003210 & 0.99042 & 0.99920 & 0.00320 \\
13 & 3.25 & 0.003246 & 0.98951 & 0.99908 & 0.00369 \\
14 & 3.50 & 0.003337 & 0.98839 & 0.99887 & 0.00452 \\
15 & 3.75 & 0.003454 & 0.98713 & 0.99873 & 0.00511 \\
16 & 4.00 & 0.003570 & 0.98582 & 0.99867 & 0.00532 \\
17 & 4.25 & 0.003685 & 0.98446 & 0.99862 & 0.00554 \\
18 & 4.50 & 0.003813 & 0.98298 & 0.99850 & 0.00601 \\
19 & 4.75 & 0.003947 & 0.98141 & 0.99841 & 0.00639 \\
20 & 5.00 & 0.004080 & 0.97979 & 0.99834 & 0.00664 \\
21 & 5.25 & 0.004211 & 0.97811 & 0.99829 & 0.00686 \\
22 & 5.50 & 0.004342 & 0.97637 & 0.99822 & 0.00715 \\
23 & 5.75 & 0.004476 & 0.97455 & 0.99814 & 0.00745 \\
24 & 6.00 & 0.004610 & 0.97267 & 0.99807 & 0.00775 \\
\hline
\end{tabular}
\caption{Caplet and Swaption Calculations}
\end{table}

\begin{table}[h!]
\centering
\begin{tabular}{cccccc}
\hline
Cap & Strike Rate & Volatility & $T_i$ & $f(T_{i-1}, T_i)$ & Caplet Value (x 100) \\
\hline
1-year Cap & 0.00362 & 1.0679 & 0.25 & 0.003644 & 0.01939 \\
 & & & 0.50 & 0.003644 & 0.02721 \\
 & & & 0.75 & 0.003853 & 0.03040 \\
 & & & 1.00 & 0.003772 & 0.03472 \\
Total & & & & & 0.08451 \\
\hline
2-year Cap & 0.00322 & 1.28170 & 0.25 & 0.003644 & 0.02721 \\
 & & & 0.50 & 0.003853 & 0.03927 \\
 & & & 0.75 & 0.003772 & 0.04389 \\
 & & & 1.00 & 0.00331 & 0.04003 \\
 & & & 1.25 & 0.00274 & 0.03326 \\
 & & & 1.50 & 0.00246 & 0.03108 \\
 & & & 1.75 & 0.00276 & 0.03929 \\
Total & & & & & 0.25403 \\
\hline
\end{tabular}
\caption{Caplet Calculations for 1-year and 2-year Cap}
\end{table}

\subsection*{5. Swaption Calculation}
The swaption uses a similar strategy. We have to compute the LIBOR curve up to year 5 to compute the discounts $Z(0, T_i)$.

From the teaching notes, we have to compute the quantity:
$$
A = \Delta \sum_{i=5}^{24} Z(0, T_i)
$$
and then use Black’s formula. The table below shows the calculations:

\begin{table}[h!]
\centering
\begin{tabular}{cccc}
\hline
Strike Rate (5-year swap rate) & 0.00408 \\
Forward 5-year Swap Rate & 0.00481 \\
Swaption Volatility & 0.9912 \\
Swaption Maturity & 1 year \\
\hline
$d1$ & 0.6617 \\
$d2$ & -0.3295 \\
$A$ & 4.9315 \\
Swaption Value & 0.01023 \\
\hline
\end{tabular}
\caption{Swaption Calculation}
\end{table}

\section*{Part II: Interest Rate Trees}

\subsection*{1. Risk Neutral Probability and Market Price of Risk}
Consider the following interest rate tree, where each time interval is 1-year ($\Delta = 1$):

$$
\begin{array}{ccc}
i = 0 & i = 1 & i = 2 \\
 & r_{2,uu} = 0.05 & \\
 & r_{1,u} = 0.04 & \\
r_0 = 0.03 & r_{2,ud} = 0.03 & r_{2,du} = 0.03 \\
 & r_{1,d} = 0.02 & \\
 & & r_{2,dd} = 0.01 \\
\end{array}
$$

The probability of an “up” movement can either be $p = 40\%$ or $p = 70\%$. The current value of a 2-period zero coupon bond is $Z_0(2) = 0.94$.

(a) Compute the risk neutral probability $\pi^*$ and confirm the same price for the option in point (b). What is the market price of risk under $\pi^*$?

First, compute the tree for the 2-period bond:

$$
\begin{array}{ccc}
i = 0 & i = 1 & i = 2 \\
 & r_{2,uu} = 0.05 & Z_{2,uu}(2) = 1 \\
 & r_{1,u} = 0.04 & Z_{1,u}(2) = e^{-0.04} = 0.96079 \\
r_0 = 0.03 & r_{2,ud} = 0.03 & Z_{2,ud}(2) = 1 \\
 & r_{1,d} = 0.02 & Z_{1,d}(2) = e^{-0.02} = 0.9802 \\
 & & r_{2,dd} = 0.01 & Z_{2,dd}(2) = 1 \\
\end{array}
$$

The risk neutral probability can be computed from:
$$
\pi^* = \frac{Z_0(2)/Z_0(1) - Z_{1,d}(2)}{Z_{1,u}(2) - Z_{1,d}(2)} = \frac{0.96862 - 0.9802}{0.96079 - 0.9802} = 0.59646
$$

(b) Compute the value of a one-year call option on the interest rate $r_1$ at the strike rate $r_K = 3\%$ and notional $N = 1000$:
$$
\text{payoff}_{1,u} = 1000 \times \max(r_{1,u} - r_K, 0)
$$
$$
\text{payoff}_{1,d} = 1000 \times \max(r_{1,d} - r_K, 0)
$$

Use the pricing formula involving the market price of risk $\lambda$ to compute the value of the option under both probabilities ($p = 40\%$ and $p = 70\%$). Show your work and comment on the results.

The value using the formula:
$$
V = Z_0(1) \times E^*[ \text{payoff}_1] = Z_0(1) \times [0.59646 \times 10] = 0.97045 \times 5.9646 = 5.79
$$

(c) The probability to go up the tree does not show up in the formula, and therefore it does not matter. The risk neutral methodology is only a tool to price securities by no arbitrage. The risk from the strategy has been eliminated by the replication strategy. Therefore, the true probability does not enter the calculation anymore.

(d) Find the portfolio of securities that replicates the payoff of the option in point (b). What is the value of this portfolio at time 0? How does it compare with the value of the option computed in point (b)? Show your work and comment.

The portfolio is:
$$
P_0 = N_1Z_0(2) + N_2Z_0(1)
$$
The position in long-term bonds is:
$$
N_1 = \Delta = \frac{V_{1,u} - V_{1,d}}{Z_{1,u}(2) - Z_{1,d}(2)} = -515.21868
$$
The value of $N_2$ is:
$$
N_2 = \Pi_{1,d} = \text{payoff}_{1,d} - \Delta \times Z_{1,d}(2) = 0 - (-515.21868) \times Z_{1,d}(2) = 505.01667
$$
The value of the portfolio is:
$$
P_0 = N_1Z_0(2) + N_2Z_0(1) = 5.79
$$

To check:
$$
P_{1,u} = N_1Z_{1,u}(2) + N_2 = 10
$$
$$
P_{1,d} = N_1Z_{1,d}(2) + N_2 = 0
$$

(e) Assume the risk neutral probability $\pi^*$ computed in point (c) is constant throughout the binomial tree. Use the risk neutral methodology to compute:
1. The value of a 3-year zero-coupon bond:

$$
\begin{array}{cccc}
j\backslash i & 0 & 1 & 2 & 3 \\
0 & 0.908892 & 0.921387 & 0.951229 & 1 \\
1 & 0.958989 & 0.970446 & 1 \\
2 & 0.99005 & 1 \\
3 & 1 \\
\end{array}
$$

At any node $i, j$:
$$
Z_{ij}(3) = e^{-r_{ij}} (\pi^* Z_{i+1,j} + (1 - \pi^*) Z_{i+1,j+1})
$$

2. The value of a 3-year coupon bond with annual coupon equal to 3%:

$$
\begin{array}{cccc}
j\backslash i & 0 & 1 & 2 & 3 \\
0 & 0.993472 & 0.977852 & 0.979766 & 1 \\
1 & 1.017165 & 0.999559 & 1 \\
2 & 1.019751 & 1 \\
3 & 1 \\
\end{array}
$$

At any node $i, j$:
$$
P_{ij}(3) = e^{-r_{ij}} (\pi^* P_{i+1,j}(3) + (1 - \pi^*) P_{i+1,j+1}(3) + 0.03)
$$

3. Compute the replicating portfolio at time $i = 0$. Find $N_0$ in the 3-period bond and $N_1$ in the 1-period bond to replicate the coupon bond:

$$
\begin{array}{ccc}
i = 0 & i = 1 & i = 2 \\
 & Z_{2,uu}(3) = 95.12294 & \\
 & Z_{1,u}(3) = 92.13868 & \\
Z_0(3) = 90.88915 & Z_{2,ud}(3) = 97.04455 & Z_{2,du}(3) = 97.04455 \\
 & Z_{1,d}(3) = 95.89893 & \\
 & & Z_{2,dd}(3) = 99.00498 \\
\end{array}
$$

Choose $N_0$ and $N_1$ so that:
$$
P_{1,u} = P_{C,u}(3) + c
$$
$$
P_{1,d} = P_{C,d}(3) + c
$$

Substitute the expression for $P_{ij}$:
$$
N_1 Z_{1,u}(3) + N_2 = P_{C,u}(3) + c
$$
$$
N_1 Z_{1,d}(3) + N_2 = P_{C,d}(3) + c
$$

Solving the system:
$$
N_1 = \frac{P_{C,u}(3) - P_{C,d}(3)}{Z_{1,u}(3) - Z_{1,d}(3)}
$$
$$
N_2 = P_{C,u}(3) + c - N_0 Z_{1,u}(3)
$$

Substitute to find:
$$
N_1 = 1.045485
$$
$$
N_2 = 0.044556
$$

Its value today is then:
$$
P_0 = N_1 Z_0(3) + N_2 Z_0(1) = 0.993472
$$

The replicating portfolio replicates, and we have the tree:

$$
\begin{array}{ccc}
i = 0 & i = 1 \\
 & P_{1,u} = 1.007852 \\
P_0 = 0.993472 & \\
 & P_{1,d} = 1.047165 \\
\end{array}
$$

Note that the portfolio replicates the full payoff of the coupon bond at time $i = 1$, including the coupon.

\end{document}
```

### HW 6

```

\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 6}
\author{John Heaton}
\date{April 28, 2024}

\begin{document}
\maketitle

\section*{Part I: Pricing Freddie Mac 6\% Callable Bond}

The prospectus of Freddie Mac 6\%, 20-year callable bond, issued on June 7, 2007, shows that the bond becomes callable in June 2011, and it can only be called on coupon dates. We are going to follow the same steps as in the note, but now on a much bigger tree. We can concentrate on a tree with 40 steps, that is, a 20-year binomial tree with semi-annual increments $\Delta = 0.5$.

We begin with fitting the model to the current interest rates. We proceed as follows:

1. First, we use the data in ”HW4 Data Bonds.xls” and extract the discount curve $Z(0, T)$ from the Treasuries using the Nelson-Siegel model, as we did in HW4. Figures 1 through 3 show the resulting fit.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_0.png}
\caption{Fitted Data}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{2_image_0.png}
\caption{Zero Coupon Curve}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Yield Curve}
\end{figure}

2. Next, we build the Ho-Lee tree, given by
$$
r_{i+1,j} = r_{i,j} + \theta(i) \times \Delta + \sigma \times \sqrt{\Delta} \times \epsilon_{i+1}
$$
where $\sigma$ is the volatility of interest rates, $\theta(i)$ are chosen to fit the term structure of interest rates exactly, and
$$
\epsilon(i) =
\begin{cases} 
+1 & \text{with probability } \frac{1}{2} \\
-1 & \text{with probability } \frac{1}{2}
\end{cases}
$$

We need to estimate $\sigma$. We use the data provided, which are monthly. If we use the formula $\text{St.Dev.}(dr_t)$ where $dr_t = r_{t+1} - r_t$ is the change in interest rate, we obtain a volatility in monthly unit. Because $\sigma$ needs to be annualized, we choose
$$
\sigma = \text{St.Dev.}(dr_t) \sqrt{12} = 1.60\%
$$

Using the routine provided, we obtain the following tree (first 10 steps).

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{4_image_0.png}
\caption{Ho-Lee Interest Rate Tree}
\end{figure}

We can also plot the yield of zero-coupon bonds using the tree and the original data. Because an outcome of the procedure is to produce the whole set of binomial trees for zero-coupon bonds $Z(:, :, i)$, we can compute the zero-coupon bond for each bond $i$, $Z(1, 1, i)$, and then compute the yield to maturity across maturities.

Clearly, there is no difference between the inputs used and the outcome of the tree, by construction.

What does $\theta(i)$ look like? The next figure shows $\theta(i)$ together with the following quantity
$$
\frac{\partial f(0, T(i+1))}{\partial t} + \sigma^2 T(i)
$$
where $f(0, T(i))$ is the forward rate at 0 with maturity $T(i)$ (and 0.5 steps), and $T(i) = i\Delta$.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{5_image_0.png}
\caption{Theta versus Forward Rate Derivative}
\end{figure}

Interestingly, the two curves are very close to each other. It turns out that as the time steps decrease to 0 we obtain exactly the same value. That is, as $\Delta \rightarrow 0$, we indeed obtain
$$
\theta(t) = \frac{\partial f(0, t)}{\partial t} + \sigma^2 t
$$
where $f(0, t)$ is the instantaneous forward rate, namely, the forward rate at 0 for an investment between $t$ and $t + dt$.

3. We finally come to price the Freddie Mac Callable bond. We follow the instructions as in the assignment, and proceed as follows:

         - Obtain the price of the non-callable bond, using the algorithm
$$
\text{PP}(:, :) = \text{zeros}(n, n); \quad \text{PP}(1:n, n) = 100; \quad \text{set final payoff of bond i equal to 1 for all nodes}
$$
$$
\text{for } j = n-1:-1:1 \quad \text{move backward on the tree, from i-1, back to 1}
$$
$$
\text{PP}(1:j, j) = \exp(-\text{ImTree}(1:j, j) \times dt) \times (0.5 \times \text{PP}(1:j, j+1) + 0.5 \times \text{PP}(2:j+1, j+1, i) + 3 \times dt);
$$
We obtain the tree (first 10 steps).

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{non_callable_bond_tree.png}
\caption{Non-callable 20-year, 6\% Coupon Bond}
\end{figure}

         - Obtain the price of the call option written on the non-callable bond. In this case we define $iFCT$ the first time when the option can be exercised. And then we use the algorithm
$$
\text{Call}(:, :) = \text{zeros}(n, n); \quad \text{Call}(1:n, n) = 0; \quad \text{set final payoff of bond i equal to 0 for all nodes}
$$
$$
\text{for } j = n-1:-1:1 \quad \text{move backward on the tree, from i-1, back to 1}
$$
$$
\text{if } j \geq iFCT
$$
$$
\text{Call}(1:j, j) = \max(\exp(-\text{ImTree}(1:j, j) \times dt) \times (0.5 \times \text{Call}(1:j, j+1) + 0.5 \times \text{Call}(2:j+1, j+1, i)), \text{PP}(i:j, j) - 100);
$$
$$
\text{else}
$$
$$
\text{Call}(1:j, j) = \exp(-\text{ImTree}(1:j, j) \times dt) \times (0.5 \times \text{Call}(1:j, j+1) + 0.5 \times \text{Call}(2:j+1, j+1, i));
$$
We obtain the tree.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{call_option_tree.png}
\caption{Call Option Tree}
\end{figure}

         - We finally obtain the price of the callable bond as the difference.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{callable_bond_tree.png}
\caption{Callable Bond Tree}
\end{figure}

Note that the value of the bond is $PC_0(40) = \$91.5301$, which is well below 100, the likely issue price. The value of the non-callable bond does not depend on the tree used, because the tree exactly fits the zero-coupon bonds $Z(T)$ and the non-callable bond can be valued directly from $Z(T)$. Thus, the low value of the callable bond must come from an excessive value of the call option $Call_0$. That is, the volatility $\sigma = 1.60\%$ is too high. The likely reason is that the data set also includes the extremely high volatility of interest rates in the 1980s. If we restrict the data to the last 10 years in the sample (120 months). The volatility is much smaller, and equal to $\sigma = 0.67\%$. In this case, indeed, we obtain $PC_0 = \$99.45$, which is very close to par.

5. Figure 6 plots the price of the non-callable and of the callable security against interest rates at call time, as well as 1, 2, 3 semesters before.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{6_image_0.png}
\caption{Bond Prices at Different Times Before FCD}
\end{figure}

The non-callable bond shows the usual pattern, with positive convexity. Instead, the callable security shows a negatively convex pattern with respect to interest rates. The reason is that as interest rates decline, it becomes more and more likely that the bond will be called at par. Hence, the value of the bond reflects this loss in future upside potential of the callable bond, and thus results in a negatively convex pattern. Indeed, in the first top left panel, we see that at the first call date, if interest rates are low enough, then the value of the bond exactly equals 100, as the bond gets called.

6. We finally get to compute the duration and convexity of callable and non-callable bonds at time 0. This exercise required a bit of thinking, but the idea is to use the definition of duration and convexity, but this time on a tree. Recall the sensitivity of the bond price to changes in interest rates is (use “up” $u$ and “down” $d$ notation for convenience)

$$
\Delta = \frac{PC_{1u} - PC_{1d}}{r_{1u} - r_{1d}}
$$

and the dollar convexity is the change in “Delta” (not of duration!) due to changes in the interest rate

$$
C\$ = \frac{\Delta_{1u} - \Delta_{1d}}{r_{1u} - r_{1d}}
$$

We then obtain

$$
D = - \frac{\Delta}{PC_0}
$$

and

$$
C = \frac{C\$}{PC_0}
$$

By applying these formulas to the two types of bonds, we obtain

$$
D_{NC} = 11.8598; \quad D_{Callable} = 6.9214
$$

and

$$
C_{NC} = 179.59; \quad C_{Callable} = -18.9098
$$

The non-callable security is strongly positively convex, while the callable security is mildly positive convex. The reason is that at issuance, the call time is still pretty far away. For instance, if we were to consider the first-call time to be just one year from now, and redo the computations, we would find $C_{Callable} = -86.60$.

7. Ho Lee versus Simple BDT. Redo all of the points above for the Simple BDT model. Switching to logarithm produces a different tree for interest rates. The difference from before is that $\sigma$ needs to use log interest rates

$$
\sigma = \text{St.Dev.}(d \log(r_t)) \sqrt{12}
$$
where $d \log(r_t) = \log(r_{t+1}) - \log(r_t)$. The non-callable bond of course does not depend on the tree, as discussed earlier, as the tree fits the current term structure of interest rates. Instead, the callable bond becomes more expensive, at $95.6329$. That is, using the same inputs, but just a different model, we obtain a higher price. The value of the option depends on the distribution of future interest rates, and the two models produced different statistical distributions in the two cases.

\end{document}
```

### HW 7

```
\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Bus 35130 Spring 2024\\ Solution to Homework 7}
\author{John Heaton}
\date{May 5, 2024}

\begin{document}
\maketitle

\section*{Part I: Relative Value Trade on Trees}

The binomial tree of the coupon bond with coupon rate $c = 3$ that we need to replicate (the “theoretical” price) is:

$$
\begin{array}{cccc}
t = 0 & t = 1 & t = 2 & t = 3 \\
99.34716 & 97.7852 & 97.97663 & 100 \\
& 101.7165 & 99.95589 & 100 \\
& 101.9751 & 100 \\
& & 100 \\
\end{array}
$$

As mentioned, the 3-year zero coupon bond is fairly priced and it is on the following tree:

$$
\begin{array}{cccc}
t = 0 & t = 1 & t = 2 & t = 3 \\
90.88915 & 92.13868 & 95.12294 & 100 \\
& 95.89893 & 97.04455 & 100 \\
& 99.00498 & 100 \\
& & 100 \\
\end{array}
$$

Finally, we need the interest rate tree, which is given by:

$$
\begin{array}{ccc}
t = 0 & t = 1 & t = 2 \\
0.03 & 0.04 & 0.05 \\
& 0.02 & 0.03 \\
& & 0.01 \\
\end{array}
$$

We replicate the coupon-bond using the zero-coupon bond. At time 0, we have:

$$
\Delta_0 = \frac{(P_{1u} + c) - (P_{1d} + c)}{Z_{1u}(3) - Z_{1d}(3)} = 1.045485
$$

The position in “cash” (borrowing) is:

$$
C_0 = e^{-r_0}(-P_{1u} - c + \Delta_0 Z_{1u}(3)) = -4.323913
$$

Note that we take into account the fact that we have to pay the coupon tomorrow ($c$) in the present value.

The value of the replicating portfolio today is:

$$
\Pi_0 = \Delta_0 Z_0(3) - C_0 = 99.34716
$$

which is equal to the “theoretical” value of the coupon bond. So, we sell the mispriced bond at 100, and purchase the portfolio $\Pi_0$ for 99.34718, and make a profit today.

The next table shows the trading strategy going forward:

$$
\begin{array}{cccc}
t=0 & t=1 \text{ (start)} & t=1 \text{ (end)} & t=2 \\
\Delta_{1,u} = 1.03 & \Pi_{\text{cum},uu} = 100.9766 & \\
\Delta_0 = 1.045485 & C_{1,u} = -2.882368 & \Pi_{\text{ex},uu} = 97.97663 \\
C_0 = -4.323913 & \Pi_{\text{cum},u} = 100.7852 & \Pi_{1,u} = 97.7852 \\
\Pi_0 = 99.34716 & \Pi_{\text{ex},u} = 97.7852 & \Pi_{\text{cum},ud} = \Pi_{\text{cum},du} = 102.9559 \\
& \Delta_{1,d} = 1.03 & \Pi_{\text{ex},ud} = \Pi_{\text{ex},du} = 99.95589 \\
& C_{1,d} = -2.940596 & \Pi_{\text{cum},d} = 104.7165 \\
& \Pi_{1,d} = 101.7165 & \Pi_{\text{ex},d} = 101.7165 \\
& & \Pi_{\text{cum},dd} = 104.9751 \\
& & \Pi_{\text{ex},dd} = 101.9751 \\
\end{array}
$$

In particular, we divide time $t = 1$ in two periods. The start of the period shows the value of the portfolio designed at time 0 as the result of an up or down movement in interest rate. The start of the period includes the payment of the coupon $c = 3$. As can be seen, the ex-coupon price is indeed equal to the theoretical value in the first binomial tree.

The end of the period included the rebalancing, that is, the new position in the zero coupon bond, e.g. $\Delta_{1u} = \frac{(P_{2uu} + c) - (P_{2ud} + c)}{Z_{2uu}(3) - Z_{2ud}(3)} = 1.03$, the new position in cash, e.g. $C_{1u} = e^{-r_{1u}}(-P_{2uu} - c + \Delta_{1u} Z_{2uu}(3)) = -2.882368$, and the check that the new portfolio after rebalancing has the same value of the old portfolio (as it has). This means that the strategy is self financing. (This is equivalent to noticing that $C_{1u} = C_0 e^{r_0} + (\Delta_{1u} - \Delta_0)Z_{1u}(3) + c = -2.882368$)

The other periods are similar. We stop at time $t = 2$ as clearly the last $\Delta$ is always zero, as the bonds converge to 100 in the last period. Therefore, the position in cash in the last period must be equal to the present value of 103 one period later, as in fact it is. For instance, $\Pi_{2,uu} = 97.97663 = e^{-r_{2uu}}$. Hence, simply investing the last value of the portfolio at the risk-free rate provides the last cash flow of the bond we want to replicate.

\section*{Part II: Interest Rate Trees}

\subsection*{1. Compute the value of a 3% Pass-Through MBS with maturity $i = 3$}

The underlying pool has a coupon rate of $r_m = 3.469\%$, principal value $N = 100$, and maturity $i = 3$. Follow the steps in TN 5 (but recall the risk-neutral probability is not 0.5).

The value of the coupon is:

$$
C = \sum_{i=1}^{3} \left( 1 + r_m \right)^i = 35.67228
$$

Therefore, the principal outstanding, interest payments, and principal payments are as given in the next table:

$$
\begin{array}{ccc}
\text{Year} & \text{Principal Outstanding} & \text{Interest Payment} & \text{Principal Payment} \\
0 & 100 & 3.469 & 32.20328 \\
1 & 67.79672 & 2.351868 & 33.32042 \\
2 & 34.4763 & 1.195983 & 34.4763 \\
3 & 0 & 0 & 0 \\
\end{array}
$$

We next compute the non-callable tree, whose entries are the present values of future coupons $C$. The risk-neutral probability, recall, is $\pi^* = 0.596181$. We obtain:

$$
\begin{array}{ccc}
\text{Principal Outstanding} & 100 & 67.79672 & 34.4763 \\
\text{Non-Callable Tree } V_{ij} & 100.5722 & 67.14152 & 33.93253 \\
& 69.17526 & 34.61801 \\
& 35.31734 \\
\end{array}
$$

We can compute the call options by comparing the value from waiting $C_{\text{Wait},ij} = e^{-r_{ij} \Delta t} (\pi^* C_{i+1,j} + (1 - \pi^*) C_{i+1,j+1})$ and the value from exercising $C_{\text{Ex},ij} = V_{ij} - \text{OP}_i$ where $V_{ij}$ is the non-callable tree, and $\text{OP}_i$ is the outstanding principal (which depends only on $i$).

$$
\begin{array}{ccc}
\text{Call Option} & 0.57204 & 0.05498 & 0 \\
& 1.378546 & 0.141708 \\
& 0.841038 \\
\end{array}
$$

The value of the mortgage is indeed close to 100: $V_0 - C_0 = 100.0002$. Exercise occurs at the following nodes, indicated by “1”:

$$
\begin{array}{ccc}
\text{Exercise Times} & 0 & 0 & 0 \\
& 1 & 1 \\
& 1 \\
\end{array}
$$

We can finally compute the value of a Pass-Through Security with interest rate $r = 3\%$.

$$
\begin{array}{cccc}
\text{Time} & \text{Outstanding Principal} & \text{Principal Payment} & \text{Interest Payment (3\%)} \\
0 & 100 & 32.20328 & 3 \\
1 & 67.79672 & 33.32042 & 2.033901 \\
2 & 34.4763 & 34.4763 & 1.034289 \\
3 & 0 & 0 & 0 \\
\end{array}
$$

Whenever node $(ij)$ corresponds to an exercise time, then the value of PT equals the value of outstanding principal at $i$. Whenever it is not an exercise node, then we use the usual formula:

$$
P^{\text{PT}}_{ij} = e^{-r_{ij} \Delta t} (\pi^* P^{\text{PT}}_{i+1,j} + (1 - \pi^*) P^{\text{PT}}_{i+1,j+1} + \text{CF}_{i+1})
$$

where:

$$
\text{CF}_{i+1} = \text{Principal Payment}_{i+1} + \text{Interest Payment}_{i+1}
$$

\section*{Part III: Pricing MBS on Trees}

We want to price the Ginnie Mae Pass-Through security GNSF 4, which on November 1, 2014, was trading at \$106.5781. This pass-through security was collateralized by a pool of mortgages with a weighted average coupon (WAC) = 4.492\%, and a weighted average maturity (WAM) = 311 (months). We proceed as follows:

1. Compute Forward Volatilities from Cap Volatility Quotes: The software was set up to compute both the LIBOR curve from the swap data and the forward volatilities from the available cap volatilities. Figure 1 plots the LIBOR curve and the Forward Curve, quarterly compounded. Instead, Figure 2 plots the forward and flat volatility. As it can be seen, the data are rather sparse, and so interpolation methods are required. Moreover, we can also see a couple of “humps” in the volatility, around maturity of 7 years and 10 years. These humps may be artificial data errors, such as stale quotes. The impact on the flat volatility is not that big, but the impact on the forward volatilities – those that need to be entered in the binomial tree – is substantial. The reason is that the flat volatility can be thought of as an average of forward volatilities. It follows that forward volatilities are sort of marginal values of the flat volatilities. Thus, little variation of an average (flat vol) implies large variation of the marginal value (forward volatility), as it is apparent from the plot. Some smoothing of the data in this case would be warranted, to eliminate the noise in the data.

2. Fit the BDT model to the discount curve and forward volatilities. The next step is to fit the BDT model. Both the Matlab code and Excel spreadsheet guides were set up to do this automatically. The algorithm is described in Teaching Notes 5, but essentially, the methodology ensures that the tree is consistent with the current yield curve and the option implied, percent volatilities obtained above. Because the coupons will be paid monthly, we would need to have the binomial tree be calibrated at the monthly frequency, that is, $\Delta t = 1/12$. While this could be done easily in the code, it adds one more step (interpolation of zero-coupon and implied volatilities at the monthly horizon) and it adds quite a bit of computation time. We therefore keep the assumption $\Delta t = 0.25$, for simplicity. Table 1 contains the results of the binomial tree. The BDT model fits well the current zero coupon curve, as shown in Figure 3.

How does this tree price the original caps? As it can be seen from Figure 4 the model does not do much of a good job on this dimension, especially at the long horizon. The convergence of $\sigma_i$ as becoming the volatilities for the binomial tree from the Market model is really a convergence result at the high frequency, and quarterly observations are not sufficient.

3. Use the BDT model to value GNSF4. We finally obtain the price of the pass-through security GNSF 4. We proceed as follows:

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{1_image_0.png}
\caption{Fitted Data}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{2_image_0.png}
\caption{Zero Coupon Curve}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{3_image_0.png}
\caption{Yield Curve}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{4_image_0.png}
\caption{Ho-Lee Interest Rate Tree}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{5_image_0.png}
\caption{Theta versus Forward Rate Derivative}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{non_callable_bond_tree.png}
\caption{Non-callable 20-year, 6\% Coupon Bond}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{call_option_tree.png}
\caption{Call Option Tree}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{callable_bond_tree.png}
\caption{Callable Bond Tree}
\end{figure}

(a) We compute the dollar coupon and the scheduled interest and principal payments. These calculations allow us to compute the scheduled outstanding principal balance. We do these computations assuming an outstanding principal of 100 (so that, the price will be also in percentage of 100, like the quoted value of the security).

The coupon must satisfy the equation:

$$
P_0 = C \sum_{j=1}^{n} \left( \frac{1}{1 + r_m \cdot \Delta t} \right)^j
$$

where $n$ is the number of coupon payments and $\Delta t$ is the time step. A useful formula is the following: define $a = \left( \frac{1}{1 + r_m \cdot \Delta t} \right)$, then we have the result that:

$$
\sum_{j=1}^{n} a^j = \frac{a - a^{n+1}}{1 - a}
$$

Given $C$, you can compute the scheduled principal and interest payment and remaining principal over time:

$$
\begin{aligned}
& \text{Interest paid in step } i: \text{IntPaid}(i) = \text{WAC} \cdot \Delta t \cdot \text{PP}(i); \\
& \text{Principal paid in step } i: \text{PriPaid}(i) = \text{MCoupon} - \text{IntPaid}(i); \\
& \text{Principal remaining for next period } i+1: \text{PP}(i+1) = \text{PP}(i) - \text{PriPaid}(i).
\end{aligned}
$$

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{6_image_0.png}
\caption{Scheduled Interest and Principal Payments}
\end{figure}

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{7_image_0.png}
\caption{Principal Balance}
\end{figure}

Figure 5 shows the scheduled interest payments and the scheduled principal payments (top panel) as well as the remaining balance (bottom panel). The latter is the “strike price” for the call option to prepay, discussed next.

(b) We finally compute the value of the non-callable mortgage on the tree (i.e., the present value of future coupons. This part is identical to previous cases, except that there is no bullet capital payment at maturity) as well as the call option. That is, for every $(j, i)$ we move backward by computing:

$$
V_{\text{NoC}}(j,i) = \exp(-\text{ImTree}(j,i) \cdot \Delta t) \cdot (\text{MCoupon} + \frac{1}{2} \cdot (V_{\text{NoC}}(j,i+1) + V_{\text{NoC}}(j+1,i+1)));
$$

and if $i > 1$ (assume exercise can only be after time 1):

$$
\text{Call}(j,i) = \max(V_{\text{NoC}}(j,i) - \text{PP}(i), \exp(-\text{ImTree}(j,i) \cdot \Delta t) \cdot (\frac{1}{2} \cdot (\text{Call}(j,i+1) + \text{Call}(j+1,i+1))));
$$

while at $i = 1$:

$$
\text{Call}(j) = \exp(-\text{ImTree}(j) \cdot \Delta t) \cdot (\frac{1}{2} \cdot (\text{Call}(j) + \text{Call}(j+1,2)));
$$

The value of the callable mortgage at every node is therefore:

$$
V_{\text{C}}(j,i) = V_{\text{NoC}}(j,i) - \text{Call}(j,i);
$$

We obtain the value of the pool of mortgages at time 0 equal to $100.7935, and without the prepayment option, the value is $119.3734.

\begin{figure}[h!]
\centering
\includegraphics[width=0.8\textwidth]{8_image_0.png}
\caption{Bond Prices at Different Times Before FCD}
\end{figure}

(c) We finally price the GNSF 4. We use the new coupon rate (4\%) and the new optimal prepayment time computed in the previous point to compute the cash flows of the pass-through security and thus its value at time 0. We use a backward algorithm like before (and explained in TN5) with the additional issue that we need to know when exercise occurred. Exercise occurs when the value of the call option (already computed) equals the payoff from exercise, that is, when $\text{Call}(j, i) = V_{\text{NoC}}(j, i) - \text{PP}(i)$. Therefore, at these times, we have that the pass-through investors get the full principal back.

- If at node $(j,i)$, if $\text{Call}(j,i) = V_{\text{NoC}}(j,i) - \text{PP}(i)$, then the value of the pass-through security equals the principal $V_{\text{PT}}(j,i) = \text{PP}(i)$.
- Otherwise, there is no exercise and the cash flow of Pass-Through equals interest plus scheduled principal paid (all next period).

The pass-through cash flow:

$$
\text{CF}_{\text{PassThrough}}(i+1,1) = \overline{r} \cdot \Delta t \cdot \text{PP}(i) + \text{PriPaid}(i);
$$

the value of PT security given by backward computation:

$$
V_{\text{PT}}(j,i) = \exp(-\text{ImTree}(j,i) \cdot \Delta t) \cdot (\text{CF}_{\text{PassThrough}}(i+1,1) + \frac{1}{2} \cdot (V_{\text{PT}}(j,i+1) + V_{\text{PT}}(j+1,i+1))).
$$

\begin{table}[h!]
\centering
\begin{tabular}{cccccccccc}
\hline
0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 \\
\hline
100.1208 & 97.8462 & 93.9685 & 88.7171 & 82.4991 & 75.7702 & 68.8145 & 61.9621 & 55.3699 & 48.9792 \\
0 & 99.4883 & 98.9708 & 96.5098 & 92.2775 & 86.9897 & 81.2369 & 75.1187 & 68.8343 & 62.4412 \\
0 & 0 & 98.9708 & 98.4474 & 97.9183 & 94.9904 & 90.6372 & 85.8818 & 80.5740 & 74.8459 \\
0 & 0 & 0 & 98.4474 & 97.9183 & 97.3831 & 96.8420 & 93.2870 & 89.5428 & 85.0567 \\
0 & 0 & 0 & 0 & 97.9183 & 97.3831 & 96.8420 & 96.2948 & 94.8280 & 92.1418 \\
0 & 0 & 0 & 0 & 0 & 97.3831 & 96.8420 & 96.2948 & 95.7414 & 95.1819 \\
0 & 0 & 0 & 0 & 0 & 0 & 96.8420 & 96.2948 & 95.7414 & 95.1819 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 96.2948 & 95.7414 & 95.1819 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 95.7414 & 95.1819 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 95.1819 \\
\hline
\end{tabular}
\caption{GNSF 4 (First 10 Steps)}
\end{table}

We obtain that the value of GNSF 4 without the Option to Exercise is \$113.3296, while the value of GNSF 4 with optimal exercise is \$100.1208.

The price is not close to the traded price (\$106.5781). The reason is that optimal exercise makes all agents exercise too soon. However, in reality, many households cannot exercise the prepayment option. If the call option is not optimized, then the value of the pass-through security increases. The question then is what probability of exercise should we give in the various nodes to obtain a value of the security that is close to the one in the data. We use Monte Carlo Simulations for that.

\section*{Part IV: Use Monte Carlo Simulations on Trees}

\subsection*{1. Simulate interest rate paths from the tree}

We can simulate interest rate paths from the tree and then compute the value of complicated securities on the tree. The Matlab codes and the Excel spreadsheets were set up to be able to run such simulations.

\subsection*{2. Compute the value of 30-year cap and 30-year Asian cap}

Generically speaking, for each simulated path $s$ of interest rates $[r_0, r^s_1, …, r^s_{n-1}]$ we can associate its sequence of cash flows $[\text{CF}^s_1, \text{CF}^s_2, …, \text{CF}^s_n]$ and then compute its present value:

$$
V^s_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF}^s_i
$$

Note that to discount a cash flow at time $i$ we need to use interest rates until $i-1$, the step before (because the last rate $r^s_{i-1}$ is the discount from $i$ back to $i-1$).

The value of the security is then:

$$
\hat{V}_0 = \frac{1}{\text{NSim}} \sum_{s=1}^{\text{NSim}} V^s_0
$$

We can also compute the standard errors by computing first the standard deviation of $V^s_0$ and dividing by the square root of the number of simulations $\text{NSim}$:

$$
\text{st.error} = \frac{\text{St.Deviation}[V^1_0, V^2_0, …, V^{\text{NSim}}_0]}{\sqrt{\text{NSim}}}
$$

For instance, in a Cap we have:

$$
\text{CF}^s_i = \max(r^s_i - r_k, 0)
$$

Note that this is not a plain vanilla cap but a Cap in Arrears, as the interest rate at time $i$ is paid at time $i$ and not at $i+1$ (moreover, we are simulating continuously compounded rates. In principle, we should change $r^s_i$ into a quarterly compounded rate through the usual formula). With $\text{NSim} = 5000$, the methodology above yields:

$$
V^{\text{Cap}}_0 = 276.1099; \quad \text{st.error} = 3.2422
$$

Still a pretty large standard error. We would need to increase the number of simulations to 100,000 to start having some reasonably small standard error.

\subsection*{3. Compute the value of an Asian Cap}

Once we know how to do MC simulations, computing the value of an Asian Cap is straightforward. The only thing we have to change is the payoff, which now is:

$$
\text{CF}^s_i = \max(\text{average}[r_0, r^s_1, …, r^s_i] - r_k, 0)
$$

That’s it. No other changes needed. The same code yields:

$$
V^{\text{AsianCap}}_0 = 116.5956; \quad \text{st.error} = 1.8092
$$

Quite a smaller value: Asian options are often preferred to standard options because they cost much less, although clearly, there is more risk. For instance, if the average is small due to a low period of interest rates and then interest rate suddenly increase, the Asian Cap (or Caplet) may be out of the money, while a regular Cap would actually be in-the-money, implying that the Cap would be better able to hedge against sudden variation in interest rates.

\subsection*{4. Compute the value of Mortgage-Backed Security through a Prepayment Function}

The same methodology can be used to compute the value of Mortgage-Backed Security through a Prepayment Function. In this case, the logic is to simulate paths of interest rates, and for each path, provide a probability $p_t$ that investors will prepay the mortgage (i.e., a fraction $p_t$ of investors prepay the mortgages).

The prepayment function was simple:

$$
p_i = c_1 \max(r_m - s_p - r_i, c_2)
$$

Given a sequence of interest rates $r^s_i$ and thus corresponding simulated $p^s_i$, we can compute the full cash flow sequence as per TN 5, page.

We can compute sequentially the following items (now at quarterly frequency but this can be done at any frequency):

$$
\begin{aligned}
& \text{Mortgage interest payment:} & \text{Is}_i = \frac{r_m}{4} \times \text{Ls}_i \\
& \text{Scheduled principal:} & \text{Pay}_{\text{scheduled},si} = \text{Cs}_i - \text{Is}_i \\
& \text{Principal prepayment:} & \text{Pay}_{\text{prepaid},si} = p^s_i \times (\text{Ls}_i - \text{Pay}_{\text{scheduled},si}) \\
& \text{Outstanding principal:} & \text{Ls}_{i+1} = \text{Ls}_i - \text{Pay}_{\text{scheduled},si} - \text{Pay}_{\text{prepaid},si} \\
& \text{Update of scheduled coupon:} & \text{Cs}_{i+1} = (1 - p^s_i) \times \text{Cs}_i \\
\end{aligned}
$$

Given the dynamics of $\text{Ls}_i$ from the simulations, we can compute the path through future cash flows:

$$
\begin{aligned}
& \text{Pass-through interest payment:} & \text{IPT,s}_i = \frac{r_{\text{PT}}}{4} \times \text{Ls}_i \\
& \text{Total cash flow:} & \text{CF}^s_i = \text{IPT,i}_i + \text{Pay}_{\text{scheduled},si} + \text{Pay}_{\text{prepaid},si} \\
\end{aligned}
$$

The price of the pass-through MBS in simulation $s$ is thus the same as for the general case:

$$
V^{\text{PT,s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF}^s_i
$$

Note that computing the value of IO and PO is immediate from above, after we know the full amount of cash flows. The idea is simply to divide up the interest-only cash flows from the principal-only cash flows:

$$
\begin{aligned}
& \text{IO cash flow:} & \text{CF IO,s}_i = \text{IPT,i}_i \\
& \text{PO cash flow:} & \text{CF IO,s}_i = \text{Pay}_{\text{scheduled},si} + \text{Pay}_{\text{prepaid},si} \\
\end{aligned}
$$

and the prices for each simulated rate path are:

$$
\begin{aligned}
& V^{\text{IO,s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF IO,s}_i \\
& V^{\text{PO,s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF PO,s}_i \\
\end{aligned}
$$

The final values of the pass-through and the IO and PO securities are given by the average of these simulated values, as discussed earlier.

Given $r_m = 0.04492$, we use the parameters $c_1 = 5$, $c_2 = 0$, and $s_p = 0.015$, and we obtain the value of GNSF 4 equal to $\hat{V}^{\text{GNSF4}}_0 = 106.1751$ with standard errors $\text{s.e.} = 0.1747$. This is not too far from the traded price, actually. Note that the parameters $c_1$, $c_2$, and $s_p$ determine a Risk Neutral probability $p^*_i$ of prepayment, as we obtained this value not from an estimate of the true prepayment frequency of homeowners, but to match the price of the PT itself. That is, there could be a risk premium component in this probability as well.

These are given by $\hat{V}^{\text{IO}}_0 = 26.1264$ and $\hat{V}^{\text{PO}}_0 = 80.0487$. Clearly, because the sum of the cash flows flowing to PO and IO equals the total cash flows to GNSF 4, the sum of the prices of IO and PO must be the same as the price of GNSF 4.

\end{document}
```