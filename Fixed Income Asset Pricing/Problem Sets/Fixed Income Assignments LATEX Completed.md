---
aliases: [Alias_362_Fixed Income Assignments LATEX Completed.md,  Alias_359_Fixed Income Assignments LATEX Completed.md]
tags: [tag_example]
title: Fixed Income Assignments LATEX Completed
---

# Fixed Income Assignments LATEX Completed

## HW 1

```latex
\documentclass[11pt]{report}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage{multirow}
\usepackage{geometry}
\usepackage{float}
\usepackage{array}
\usepackage{booktabs}
\usepackage{multicol}
\usepackage{longtable}
\usepackage{tikz}
\usepackage{tikz-cd}
\usetikzlibrary{shapes, positioning}
\geometry{letterpaper,  margin=0.8in}

\title{Bus 35130 Spring 2024\\ Homework Questions and Solutions}
\author{Roger Lin}
\date{June 1st,  2024}

\begin{document}
\maketitle

\section*{Homework 1}
\textbf{Due before 6pm on Monday March 25 before 6pm central time.}

You have been retained by the JCH Fixed Income Group to provide a forecast about future short term interest rates,  namely,  the 3 month t-bill rate. You decide to use two sources of data: historical interest rate data and current forward rates. The data necessary for this forecasting exercise are contained in the Excel file DTB3 2024.XLS,  which you can find on Canvas. This dataset contains daily observations of the 3 month t-bill rate from April 4,  1954 until March 14,  2024 (sheet “DTB3”) as well as the Treasury Strip Price on March 08,  2024 (sheet “Strip Prices”). You are to write a report including all relevant information and computations,  and provide a forecast for $n$ horizons ranging between 6 months and 5 years. Please,  follow the steps below.

\begin{quote}
	\textbf{Note 1:} For each section below,  there are questions that require a “pencil and paper” (PP) answer,  and questions that require actual computations using data and computer programs (CP). You are supposed to do both. For the computer-based questions you may use any software you like. There are guides,  however,  for Matlab,  Excel,  and Python. You are,  however,  not required to use any of these pieces of code!
	
	\textbf{Note 2:} Some code you might use:
	\begin{itemize}
		\item For Matlab users,  we made available the Matlab code “HW1 2024 Guide.m”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example,  you will need to fill in some formulas and/or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.
		\item For Excel users,  we made available the spreadsheet “HW1 2024 Guide.xlsm”. This Excel spreadsheet contains instructions to use the XLSTAT functions answer the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] questions below. Inputs though are required to complete some formulas or to produce some of the results. The Excel spreadsheet is supposed to facilitate the computations for the homework.
		\item For Python users,  we made available the Python code “HW1 2024 Guide.py”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example,  you will need to fill in some formulas and/or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.
	\end{itemize}
\end{quote}

\section*{Estimation and Forecast}

\begin{enumerate}
	\item Let us denote by $r_{t}$ the Bond Equivalent Yield (TN 1,  page 22) on day $t$.
	      \begin{description}
	      	\item[(PP)] Below are Treasury Bill quotes from the Wall Street Journal from a few years ago. Please,  explain why the rates in “Ask” differ from those in “Asked Yield”. Use the quoted rates with maturity 6/11/2020 and 3/25/2021 to explain the point in detail (i.e. show that the “Ask” quotes indeed imply “Asked yield”.)
	      	
	      	\textbf{Solution:} The difference between the bid and ask yields reflects the difference between bid and ask prices. Bid prices from dealers are less than ask prices and hence the bid yields are higher than ask yields. To convert to the "Asked Yield" we use the formulas in TN1,  to obtain BEY for maturities 6/11/2020 (quoted ask $d = 0.093/100$,  $n = 66$) and 3/25/2021 (quoted ask $d = 0.160/100$,  $n = 353$) as follows:
	      	$$
	      	BEY_{6/11/2020} = \frac{365 \times 0.00093}{360 - 0.00093 \times 66} = 0.0943\%
	      	$$
	      	
	      	$$
	      	BEY_{3/25/2021} = \frac{365 \times 0.00160}{360 - 0.00160 \times 353} = 0.1625\%
	      	$$
	      	which are close to the corresponding asked yields in the quoted table.
	      	        
	      	\item[(CP)] The data in DTB3 2024.XLS are quoted on a discount basis $d_{t}$. Please determine a time series of BEY and provide the appropriate plot (note that here $n = 91$).
	      	
	      	\textbf{Solution:} We first eliminate the days that have missing values. These are non-business dates (such as Christmas and Thanksgiving) on which no prices were recorded. Next,  note that the rates given in the data file are in percentages. To get the BEY,  use the formula on of TN1:
	      	$$
	      	BEY = \frac{365 \times d}{360 - d \times 91}
	      	$$
	      	        
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{3monthtbill}
	      		\caption{Quoted discounts and BEYs}
	      	\end{figure}
	      \end{description}
	      
	\item The AR(1) process for interest rates is the following:
	      $$
	      r_{t+1} = \omega + \epsilon r_{t} + \vartheta_{t+1}
	      $$
	      where $\vartheta_{t+1} \sim N(0,  \varphi^2)$
	      \begin{description}
	      	\item[(PP)] Show OLS based formulas for determining $\hat{\omega}$,  $\hat{\epsilon}$ and $\varphi$.
	      	
	      	\textbf{Solution:} We regress $r_{t+1}$ on $r_t$. There are 17, 542 observations for the T-bill rates. Thus,  the observations 1-17, 541 can be treated as the independent variable $X$,  and observations 2-17, 542 as the dependent variable $Y$.
	      	
	      	In general,  for a univariate regression of the form
	      	$$
	      	Y_i = \alpha + \beta X_i + u_i,  \quad i = 1,  \ldots,  n
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
	      	\overline{X} = \frac{1}{n} \sum_{i=1}^n X_i,  \quad \overline{Y} = \frac{1}{n} \sum_{i=1}^n Y_i.
	      	$$
	      	
	      	Finally,  to estimate the standard error of the error term,  we can first compute the sample standard errors, 
	      	$$
	      	\hat{u}_i = Y_i - \hat{\alpha} - \hat{\beta} X_i,  \quad i = 1,  \ldots,  n.
	      	$$
	      	Then
	      	$$
	      	\hat{\sigma} = \sqrt{\frac{1}{n} \sum_{i=1}^n \hat{u}_i^2}.
	      	$$
	      	
	      	\textit{Note: The adjustment in $\hat{\sigma}$ for degrees of freedom is not typical in time series regression. Because the right-hand-side variable is a random variable,  the typical results about unbiasedness of regression estimates do not apply here. Main point: if you divided by $n$ versus $n-2$ with such a large sample,  there will be little numerical difference!}
	      	        
	      	\item[(PP)] Demonstrate why and how “mean reversion” of interest rates can be modeled with AR(1) process.
	      	
	      	\textbf{Solution:} AR(1) process for interest rates is the following:
	      	$$
	      	r_{t+1} = \alpha + \beta r_t + \epsilon_t \quad (1)
	      	$$
	      	"Mean reversion" of interest rates can be modeled with AR(1) process since,  according to AR(1) process,  the projected interest rates converge to the long-term level of interest rates over time under stationarity condition,  i.e. when $|\beta| < 1$. In this case,  the long-term level of interest rates,  i.e. “unconditional mean”,  under AR(1) process is the following:
	      	$$
	      	E(r) = \overline{r} = \frac{\alpha}{1 - \beta}
	      	$$
	      	To better see the mean reversion,  subtract $r_t$ from both sides and rewrite
	      	$$
	      	r_{t+1} - r_t = (1 - \beta) [\overline{r} - r_t] + \epsilon_t \quad (2)
	      	$$
	      	Thus,  if $r_t > \overline{r}$,  we have $E[r_{t+1} - r_t] = (1 - \beta) [\overline{r} - r_t] < 0$,  and hence a high rate tends to be followed by a negative \emph{change} in interest rates,  and vice versa.
	      	    
	      	\item[(CP)] Estimate the AR(1) process for interest rates.
	      	
	      	\textbf{Solution:} The results of the regression are summarized in Table 1.
	      	
	      	\begin{table}[H]
	      		\centering
	      		\begin{tabular}{l c c}
	      			\hline
	      			Coefficients & Estimate                 & t-value  \\
	      			\hline
	      			$\alpha$     & $2.01702 \times 10^{-5}$ & $1.7677$ \\
	      			$\beta$      & $0.9996$                 & $4722.4$ \\
	      			$\sigma$     & $9.05099 \times 10^{-4}$ &          \\
	      			\hline
	      		\end{tabular}
	      		\caption{Estimation of the AR(1)}
	      	\end{table}
	      	
	      	Given these estimates,  the average long-run interest rate is
	      	$$
	      	\overline{r} = \frac{\hat{\alpha}}{1 - \hat{\beta}} = 0.04874
	      	$$
	      \end{description}
	      
	\item Let $\hat{\omega}$,  $\hat{\epsilon}$ and $\varphi$ be the estimated parameters from (1). Use (1) together with the most recent interest rate available on DTB3.XLS,  call it $r_{\text{TODAY}}$,  to make a forecast of future interest rates $r_{\text{TODAY}+T}$.
	      \begin{description}
	      	\item[(PP)] Carry the daily interest rate forecast for the following three days,  i.e. calculate $r_{\text{TODAY}+1\text{day}}$,  $r_{\text{TODAY}+2\text{days}}$,  …,  $r_{\text{TODAY}+3\text{days}}$. Show all work,  including all the formulas used.
	      	
	      	\textbf{Solution:} The most current interest rate is from 2024-03-14,  $r_{TODAY} = 5.3945\%$.
	      	
	      	Let $r_{TODAY}(n)$ denote the forecast for the interest rate $n$ days from today. From the equation for AR(1) process above,  using the estimates of $\alpha$ and $\beta$,  we have
	      	$$
	      	r_{TODAY}(1) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}.
	      	$$
	      	
	      	If we compare the equation above with the equation for AR(1) process,  we see that the error term does not show up in the forecast. That is because we expect it to be 0. Next,  in order to forecast the interest rate 2 days from today,  we can just use the forecast we just made for tomorrow:
	      	$$
	      	r_{TODAY}(2) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}(1).
	      	$$
	      	
	      	More generally, 
	      	$$
	      	r_{TODAY}(n+1) = \hat{\alpha} + \hat{\beta} \times r_{TODAY}(n),  \quad n = 1,  2,  3,  \ldots
	      	$$
	      	
	      	As a result,  the interest rate forecast for the following three days is the following:
	      	$$
	      	r_{TODAY}(1) = \hat{\alpha} + \hat{\beta} r_{TODAY} = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3945\% = 5.3943\%
	      	$$
	      	$$
	      	r_{TODAY}(2) = \hat{\alpha} + \hat{\beta} r_{TODAY}(1) = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3943\% = 5.3941\%
	      	$$
	      	$$
	      	r_{TODAY}(3) = \hat{\alpha} + \hat{\beta} r_{TODAY}(2) = (2.01702 \times 10^{-5}) + 0.9996 \times 5.3941\% = 5.3939\%
	      	$$
	      	
	      	\item[(CP)] Forecast interest rates for horizons $T = 6$ months,  and 1,  2,  …,  5 years (a plot would suffice). Explain how you make the forecasts. (Tip: When you make the forecasts,  assume there are 252 (business) days in one year).
	      	
	      	\textbf{Solution:} You can use a loop in Matlab or Python to compute the forecasts. The results are plotted below in Figure 2:
	      	Our forecast of the AR(1) process also gets closer and closer to its long-run average as the forecasting horizon increases.
	      	
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{hw1-2}
	      		\caption{Time Series Forecast and Long-term Interest Rate}
	      	\end{figure}
	      \end{description}
	      
	\item The Treasury Strip Prices are contained in DTB3 2024.xls.
	      \begin{description}
	      	\item[(PP)] Compute both the current yield curve and forward rates for the first three maturities. Show all work,  including all the formulas used. Discuss what a “forward rate” is.
	      	
	      	\textbf{Solution:} We can calculate yields from the Strip prices $Z(t,  T)$ using the formula on  of TN1:
	      	
	      	Here,  $t$ is the present date,  2024-03-14. We have multiple maturities $T$,  so we can calculate yields for different maturities. From these prices,  we can calculate the 6-month forward rates from the formula on  of TN1:
	      	$$
	      	f(t,  T_1,  T_2) = \frac{\ln(Z(t,  T_1)) - \ln(Z(t,  T_2))}{T_2 - T_1}
	      	$$
	      	
	      	Using the formula above,  i.e. $y(t,  T) = -\frac{1}{T} \ln(Z(t,  T))$,  the current yields for the first three maturities are determined as follows:
	      	$$
	      	r(0,  0.5) = -\frac{1}{0.5} \ln(0.9745) = 5.174\%
	      	$$
	      	$$
	      	r(0,  1) = -\frac{1}{1} \ln(0.9526) = 4.859\%
	      	$$
	      	$$
	      	r(0,  1.5) = -\frac{1}{1.5} \ln(0.9330) = 4.622\%
	      	$$
	      	
	      	Using the formula above,  i.e. $f(t,  T_1,  T_2) = \frac{\ln(Z(t, T_1)) - \ln(Z(t, T_2))}{T_2 - T_1}$,  the forward rates for the first three maturities are determined as follows:
	      	$$
	      	f(0,  0.5,  1) = \frac{\ln(0.9745) - \ln(0.9526)}{1.0 - 0.5} = 5.174\%
	      	$$
	      	$$
	      	f(0,  1,  1.5) = \frac{\ln(0.9526) - \ln(0.9330)}{1.5 - 1.0} = 4.545\%
	      	$$
	      	$$
	      	f(0,  1.5,  2) = \frac{\ln(0.9330) - \ln(0.9150)}{2 - 1.5} = 4.147\%
	      	$$
	      	\begin{table}[H]
	      		\centering
	      		\begin{tabular}{|c|c|c|c|}
	      			\hline
	      			\textbf{Mat} & \textbf{Zfun} & \textbf{Yield1} & \textbf{Fwds} \\
	      			\hline
	      			0.5          & 0.974463      & 0.051738        & 0.051738      \\
	      			1.0          & 0.952569      & 0.048593        & 0.045448      \\
	      			1.5          & 0.933020      & 0.046219        & 0.041471      \\
	      			2.0          & 0.914968      & 0.044433        & 0.039076      \\
	      			2.5          & 0.897856      & 0.043098        & 0.037758      \\
	      			3.0          & 0.881326      & 0.042109        & 0.037166      \\
	      			3.5          & 0.865146      & 0.041388        & 0.037057      \\
	      			4.0          & 0.849176      & 0.040872        & 0.037265      \\
	      			4.5          & 0.833330      & 0.040517        & 0.037672      \\
	      			5.0          & 0.817564      & 0.040285        & 0.038201      \\
	      			\hline
	      		\end{tabular}
	      		\caption{Zfun,  Yield1,  and Fwds Values by Maturity}
	      		\label{tab:values}
	      	\end{table}
	      	    
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{yield_and_forwards}
	      		\caption{Yields and Forward Rates}
	      	\end{figure}
	      	    
	      	\item[(CP)] Compute both the current yield curve and forward rates for all maturities and compare the forecasts of future interest rates that are implicit in the forward rates to those obtained in point (3) above. Plot the forecasts and the corresponding forward rates. Discuss your findings.
	      	
	      	\textbf{Solution:} Figure 3 shows the yield and forward curve extracted from the strips,  while Figure 4 shows the implicit forecasts from the Strips and the forecasts calculated in question 3:
	      	    
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{hw1-5}
	      		\caption{Implicit Forecasts from Strips}
	      	\end{figure}
	      	    
	      	These forward rates are often thought of as market forecasts of future (6-month) interest rates. As we shall see,  this is not correct,  as we need to adjust for "a market risk premium" (as well as a convexity factor). In the terminology that we will develop,  forward rates are "expected future rates" under the risk-neutral dynamics (plus a convexity factor). But the market participants are not risk-neutral,  and therefore forgetting the risk premium may yield serious forecast errors.
	      \end{description}
\end{enumerate}
\newpage
```

## HW 2

```latex
\maketitle

\section*{Homework 2}
\textbf{Due at the beginning of class 3}

This homework is on the pricing and risk assessment of Leveraged Inverse Floaters. Please,  write the solution to the homework as a clean report addressed to the principals of the fixed income group at JCH Fixed Income Group,  LLP. The principals of JCH Fixed Income Group are very demanding,  so make sure to describe exactly the source of your results. However,  the report must be clean and concise. An appendix to the report may contain any additional material.

The data for this homework are collected in the data file HW2 Data.xls available on canvas.

\begin{quote}
	\textbf{Note 1:} For each section below,  there are questions that require pencil and paper (PP) answers,  and questions that require actual computation using data and computer programs (CP). You are to do both.
	
	\textbf{Note 2:} As with previous homework assignments there are “guides” for doing the homework in Excel,  Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.
\end{quote}

\subsection*{Leverage Inverse Floaters}
\textbf{Recommended Reading: Veronesi’s Book. Chapter 2 (esp. 2.8); Chapter 3 (esp. 3.7)}

In an environment of low interest rates,  inverse floaters are popular investment vehicles that allow a fund manager to obtain a higher yield,  by betting on the direction of the movement in interest rates. In particular,  consider the following term sheet for a Leveraged Inverse Floater.

\subsubsection*{Leveraged Inverse Floater Term Sheet}
\begin{itemize}
	\item Date: February 17,  2009
	\item Maturity: February 17,  2014 (5 year)
	\item Payments Frequency: Semi-annual
	\item Interest Payment: Base Interest Rate minus 2 times Reference Interest Rate
	\item Base Interest Rate: 10\%
	\item Reference Interest Rate: 6 month T-bill rate with standard 6 month lag
\end{itemize}

\begin{enumerate}
	\item \textbf{Bootstrap methodology}
	      \begin{description}
	      	\item[(PP)] Describe bootstrap methodology for extracting the term structure of interest rates.
	      	        
	      	\textbf{Solution:} In order to perform the bootstrap procedure,  we need securities at semi-annual frequency. We can cherry-pick from the dataset such securities. Table 1 contains the data used in the bootstrap procedure. Unfortunately,  already at $T = 10$ years we do not have notes with maturities at semi-annual frequency; using bonds we can get to $T = 12.5$,  but they may have some price differences due to liquidity. (For instance,  see the break at $T = 10$ in both Figure 1 and 2.) Even using bonds,  we must stop the procedure after $T = 12.5$ as there is no more data at semi-annual frequency.
	      	
	      	To bootstrap the discounts,  we can use the procedure illustrated in teaching notes:
	      	For every $i$
	      	$$
	      	Z(0,  T_i) = \frac{P(0,  T_i) - c_i/2 \sum_{j=1}^{i-1} Z(0,  T_j)}{1 + c_i/2}
	      	$$
	      	
	      	Alternatively,  we can use a matrix formulation. In line with the semi-annual frequency,  let $T_i = \frac{i}{2}$ for $1 \leq i \leq 25$. Define a cash-flow matrix,  $C$,  where an element $c_{ij}$ denotes the payoff at time $T_j$ of the bond with maturity $T_i$. By ordering the bonds increasing in maturity,  $C$ is lower diagonal. Also,  let $P$ denote a column vector with element $p_i$ equal to the price of bond with maturity $T_i$. In particular,  we have
	      	$$
	      	\begin{pmatrix}
	      		P_1(0,  T_1) \\
	      		P_2(0,  T_2) \\
	      		\vdots      \\
	      		P_n(0,  T_n) 
	      	\end{pmatrix} =
	      	\begin{pmatrix}
	      		c_1/2 + 100 & 0           & 0      & \cdots & 0           \\
	      		c_2/2       & c_2/2 + 100 & 0      & \cdots & 0           \\
	      		\vdots      & \vdots      & \vdots & \vdots & \vdots      \\
	      		c_n/2       & c_n/2       & c_n/2  & \cdots & c_n/2 + 100 
	      	\end{pmatrix}
	      	\begin{pmatrix}
	      		Z_1(0,  T_1) \\
	      		Z_2(0,  T_2) \\
	      		\vdots      \\
	      		Z_n(0,  T_n) 
	      	\end{pmatrix}
	      	$$
	      	or,  in vector notation
	      	$$
	      	P = CZ
	      	$$
	      	where $Z$ is a column vector with $i$ element equal to $Z(0,  T_i)$. Then,  we obtain
	      	$$
	      	Z = C^{-1}P
	      	$$
	      	
	      	Note that the $P$ vector is made up of the invoice or dirty prices. Here,  the securities are handpicked to have zero accrued interest,  so this simplifies. The calculations below take the price to be the mean of the bid and ask quotes.
	      	
	      	\item[(PP)] The AllBondQuotes 20090217 tab of the data file provided contains Treasury Bills,  Notes and Bonds on February 17,  2009. Use these data to manually compute the spot rates for maturity 0.5,  1,  and 1.5. Show your work. TIP: Maturity 0.4999 can be considered 0.5,  and so on.
	      	        
	      	\textbf{Solution:} Use the bond data as of February 17,  2009 and applying formulas on  from TN1,  the bootstrapped yields to maturity for maturity 0.5,  1,  and 1.5 are calculated as follows:
	      	
	      	$$
	      	Z(0,  0.5) = \frac{P_1(0,  0.5)}{1 + \frac{c_1}{2}} = \frac{1.0150}{1 + 0.0175} = 0.9975
	      	$$
	      	
	      	$$
	      	Z(0,  1) = \frac{P_2(0,  1) - \frac{c_2}{2} Z(0,  0.5)}{1 + \frac{c_2}{2}} = \frac{1.0291 - 0.0175 \times 0.9975}{1 + 0.0175} = 0.9942
	      	$$
	      	
	      	$$
	      	Z(0,  1.5) = \frac{P_3(0,  1.5) - \frac{c_3}{2} (Z(0,  0.5) + Z(0,  1))}{1 + \frac{c_3}{2}} = \frac{1.0522 - 0.02065 (0.9975 + 0.9942)}{1 + 0.02065} = 0.9907
	      	$$
	      	
	      	where the bond prices are determined as the average of bid and ask values.
	      	        
	      	\item[(CP)] The AllBondQuotes 20090217 tab of the data file provided contains Treasury Bills,  Notes and Bonds on February 17,  2009.
	      	\begin{itemize}
	      		\item Use these data to bootstrap the term structure of interest rates for as long a maturity as possible,  and obtain the discount function. In particular,  you will see that for several maturities,  you will have a choice of which bonds to use in your bootstrap. Compute two discount curves,  (a) one that uses the most recently issued bonds (as of 02/19/2009),  and (b) one that uses the oldest bonds. Discuss the differences. Make sure to report what data you actually use for the bootstrap as well as any approximation you have to carry out. [Note: The bonds with highest coupon are the oldest ones].
	      		\item Plot the resulting term structure of interest rates (i.e. the spot rate function) for both cases (a) and (b). Discuss the difference and any other visible feature of the yield curve.
	      	\end{itemize}
	      	\textbf{Solution:} Table 1 displays the data from the selected securities. We show the difference in term structure depending on the type of securities used. The left panel shows the bonds that were issued most recently (“new bonds”) while the right panel shows the bonds that were issued long ago. The column type is 2 for a note and 1 for a bond.
	      	
	      	\begin{table}[H]
	      		\tiny
	      		\centering
	      		\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|c|c|}
	      			\hline
	      			Maturity  & Type & Coupon & Ask      & Bid      & $T_i$   & Maturity  & Type & Coupon & Ask      & Bid      & $T_i$   \\
	      			\hline
	      			New Bonds &      &        &          &          &         & Old Bonds &      &        &          &          &         \\
	      			\hline
	      			20090815  & 2    & 3.5    & 101.4844 & 101.5156 & 0.4944  & 20090815  & 2    & 6      & 102.6797 & 102.7109 & 0.4944  \\
	      			20100215  & 2    & 3.5    & 102.8945 & 102.9258 & 0.9944  & 20100215  & 2    & 6.5    & 105.7461 & 105.7773 & 0.9944  \\
	      			20100815  & 2    & 4.125  & 105.2031 & 105.2422 & 1.4944  & 20100815  & 2    & 5.75   & 107.6875 & 107.7344 & 1.4944  \\
	      			20110215  & 2    & 5      & 108.5313 & 108.5625 & 1.9944  & 20110215  & 2    & 5      & 108.5313 & 108.5625 & 1.9944  \\
	      			20110815  & 2    & 5      & 110.2656 & 110.3125 & 2.4944  & 20110815  & 2    & 5      & 110.2656 & 110.3125 & 2.4944  \\
	      			20120215  & 2    & 1.375  & 100.4453 & 100.4766 & 2.9944  & 20120215  & 2    & 4.875  & 110.7656 & 110.8125 & 2.9944  \\
	      			20120815  & 2    & 4.375  & 110.8672 & 110.8984 & 3.4944  & 20120815  & 2    & 4.375  & 110.8672 & 110.8984 & 3.4944  \\
	      			20130215  & 2    & 3.875  & 109.9063 & 109.9531 & 3.9944  & 20130215  & 2    & 3.875  & 109.9063 & 109.9531 & 3.9944  \\
	      			20130815  & 2    & 4.25   & 112.1563 & 112.2188 & 4.4944  & 20130815  & 2    & 4.25   & 112.1563 & 112.2188 & 4.4944  \\
	      			20140215  & 2    & 4      & 111.6719 & 111.7344 & 4.9944  & 20140215  & 2    & 4      & 111.6719 & 111.7344 & 4.9944  \\
	      			20140815  & 2    & 4.25   & 113.3594 & 113.3906 & 5.4944  & 20140815  & 2    & 4.25   & 113.3594 & 113.3906 & 5.4944  \\
	      			20150215  & 2    & 4      & 111.9063 & 111.9375 & 5.9944  & 20150215  & 1    & 11.25  & 150.4375 & 150.4688 & 5.9944  \\
	      			20150815  & 2    & 4.25   & 113.2031 & 113.2344 & 6.4944  & 20150815  & 1    & 10.625 & 149.9219 & 149.9531 & 6.4944  \\
	      			20160215  & 2    & 4.5    & 114.875  & 114.9063 & 6.9944  & 20160215  & 1    & 9.25   & 142.7813 & 142.8125 & 6.9944  \\
	      			20160815  & 2    & 4.875  & 117.0781 & 117.1094 & 7.4944  & 20160815  & 2    & 4.875  & 117.0781 & 117.1094 & 7.4944  \\
	      			20170215  & 2    & 4.625  & 115.4844 & 115.5313 & 7.9944  & 20170215  & 2    & 4.625  & 115.4844 & 115.5313 & 7.9944  \\
	      			20170815  & 2    & 4.75   & 116.8438 & 116.875  & 8.4944  & 20170815  & 1    & 8.875  & 144.9531 & 145      & 8.4944  \\
	      			20180215  & 2    & 3.5    & 107.5781 & 107.6406 & 8.9944  & 20180215  & 2    & 3.5    & 107.5781 & 107.6406 & 8.9944  \\
	      			20180815  & 2    & 4      & 111.6875 & 111.7188 & 9.4944  & 20180815  & 2    & 4      & 111.6875 & 111.7188 & 9.4944  \\
	      			20190215  & 2    & 2.75   & 100.875  & 100.9375 & 9.9944  & 20190215  & 1    & 8.875  & 149.5938 & 149.625  & 9.9944  \\
	      			20190815  & 1    & 8.125  & 143.8438 & 143.875  & 10.4944 & 20190815  & 1    & 8.125  & 143.8438 & 143.875  & 10.4944 \\
	      			20200215  & 1    & 8.5    & 147.7266 & 147.7578 & 10.9944 & 20200215  & 1    & 8.5    & 147.7266 & 147.7578 & 10.9944 \\
	      			20200815  & 1    & 8.75   & 151.1563 & 151.1875 & 11.4944 & 20200815  & 1    & 8.75   & 151.1563 & 151.1875 & 11.4944 \\
	      			20210215  & 1    & 7.875  & 143.5391 & 143.5703 & 11.9944 & 20210215  & 1    & 7.875  & 143.5391 & 143.5703 & 11.9944 \\
	      			20210815  & 1    & 8.125  & 147.1094 & 147.1406 & 12.4944 & 20210815  & 1    & 8.125  & 147.1094 & 147.1406 & 12.4944 \\
	      			\hline
	      		\end{tabular}
	      		\caption{Securities used in Bootstrap}
	      	\end{table}
	      	
	      	Figures 1 and 2 plot the discount function and the yield curve implied by these calculations. The vertical dotted line denotes the point at which bond securities are used to bootstrap also for the “new bonds”. Clearly,  depending on the type of securities used,  we can get quite different results. The period surrounding 2009 showed large differences between new bonds and old bond prices,  due to liquidity. Newly issued bonds were much more liquid than old bonds,  which resulted in large price discrepancies. (The comparison between old and new bonds was not part of the assignment).
	      	
	      	\begin{figure}[h]
	      		\centering
	      		\includegraphics[width=1\textwidth]{hw2-1}
	      		\caption{Zero Coupon Discount Curves}
	      	\end{figure}
	      	
	      	
	      	\begin{figure}[h]
	      		\centering
	      		\includegraphics[width=1\textwidth]{hw2-2}
	      		\caption{Zero Coupon Yield Curves}
	      	\end{figure}
	      \end{description}
	      
	      
	\item \textbf{Leverage Inverse Floater pricing}
	      \begin{description}
	      	\item[(PP)] Describe the cash flows of the Leverage Inverse Floater provided in Term Sheet. How can we decompose the Leverage Inverse Floater into simpler securities?\\
	      	\textbf{Solution:} The coupon rate at any time $t$ is given by
	      	$$
	      	c(T_i) = 10\% - 2 \times r_2(T_{i-1}) \quad (1)
	      	$$
	      	The investor who is long the Leveraged Inverse Floater receives a 10\% fixed coupon and pays “floating” at the rate that is twice the floating six-month T-bill rate (six months lag). At maturity,  in addition,  the investor will receive the principal. Therefore,  it is as if the investor is long one 10\% coupon bond with five years to maturity and short 2 floating rate bonds with five years to maturity. This combination ensures receiving a cash flow over time identical to (1). However,  such a position would imply an outflow of the principal at maturity,  instead of an inflow. It follows that we need to add two zero coupon bonds with five years maturity to exactly mimic all of the cash flows from the Leveraged Inverse Floater.
	      	    
	      	\item[(PP)] Discuss intuitively the benefits from investing in the Leverage Inverse Floaters as compared to an existing,  traded,  regular fixed rate note with the same maturity.
	      	    
	      	\textbf{Solution:} What is the benefit from going long the Leveraged Inverse Floater? The current semi-annual rate on February 17,  2009 was 0.49\%. Therefore,  the current cash flow from this security is 9.02\% so long as the short-term rate does not increase. Given the data above,  a fixed rate coupon bond with a 5-year maturity has a coupon equal to $c = 4.0\%$. Of course,  this bond is also cheaper at 111.70. However,  the discount function above implies that the price of a fixed-rate 5-year bond with a coupon of 9.2\% would have a price of 135.97. As long as the short rate does not move,  the Leveraged Inverse Floater generates a higher cash flow without increasing the price comparably. For this reason,  investments in this type of instrument are called “yield enhancing strategies”. Yet,  they imply a speculation on the direction of interest rates movements,  as discussed next.
	      	    
	      	\item[(CP)] Use the results in Point 1 to compute the price of Leverage Inverse Floater described in the Term Sheet (which term structure do you use? Remember you have to come up with one price and not two. Explain your choice).
	      	    
	      	\textbf{Solution:} The price of the inverse floater is then
	      	$$
	      	P_{IFL}(0; 5) = P_{Fixed}(0,  5) - 2 \times P_{Fl}(0; 5) + 2 \times Z(0; 5) \quad (2)
	      	$$
	      	Given the discount function in Table 1 above,  we have
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
	      	Note that in the computation above we are implicitly assuming that the coupon $c(T_i)$ will never get negative,  as the Leverage Inverse Floater would never require an additional payment from investors.
	      \end{description}
	      
	\item \textbf{Duration and convexity}
	      \begin{description}
	      	\item[(PP)] Describe the duration of a fixed income security and how it is calculated in general. How is the duration of the Leverage Inverse Floater calculated? What are its components?
	      	    
	      	\textbf{Solution:} The duration of the fixed rate bond is based on the following general formula
	      	$$
	      	D_{Fixed} = \sum_{i=1}^n w_i T_i = 4.2141
	      	$$
	      	where $T_i = 0.5,  1,  \ldots,  5$ and
	      	$$
	      	w_i = \frac{Z(0; T_i) c_i/2}{P_{Fixed}} \quad \text{for } i = T_i = 0.5,  \ldots,  4.5 \quad \text{and} \quad w_n = \frac{Z(0; T_n) (1 + c_i/2)}{P_{Fixed}} \quad \text{for } T_n = 5.
	      	$$
	      	
	      	The duration of the Leveraged Inverse Floater can be computed from the rule “the duration of a portfolio is equal to the weighted average of the durations.” So,  first,  we need to compute the duration of each of the securities in formula (2). The duration of the zero coupon bond $Z(0,  5)$ is $D_Z = 5$,  while the duration of the Floating Rate Bond is $D_{Fl} = 0.5$,  six months,  and the duration of the fixed rate bond is $D_{Fixed} = 4.2141$ as shown above.
	      	    
	      	\item[(CP)] Calculate the duration of the Leverage Inverse Floater. Plot the value of the Leverage Inverse Floater against a hypothetical parallel shift in the term structure of interest rates.
	      	    
	      	\begin{table}[h!]
	      		\centering
	      		\begin{tabular}{|cccc|cccc|c|c|}
	      			\hline
	      			\textbf{T}         & \textbf{$\text{T}^2$} & \textbf{Z} & \textbf{Old Bond} & \textbf{Fixed} & \textbf{Float} & \textbf{Zero} & \textbf{LIF} & \textbf{4\% Bond} & \textbf{9.5\% Bond} \\
	      			\hline
	      			-                  & -                     & 1.0000     & -                 & 5.0            & -              & -             & 100.00       & -                 & -                   \\
	      			0.5                & 0.25                  & 0.9970     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			1.0                & 1.0                   & 0.9929     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			1.5                & 2.25                  & 0.9914     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			2.0                & 4.0                   & 0.9863     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			2.5                & 6.25                  & 0.9792     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			3.0                & 9.0                   & 0.9638     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			3.5                & 12.25                 & 0.9586     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			4.0                & 16.0                  & 0.9478     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			4.5                & 20.25                 & 0.9359     & 5.0               & 5.0            & -              & -             & -            & 2.0               & 4.75                \\
	      			5.0                & 25.0                  & 0.9235     & 105.0             & -              & -              & -             & 100.00       & 102.0             & 104.75              \\
	      			\hline
	      			
	      			\textbf{Price}     &                       &            &                   & 140.73         & 100.00         & 92.35         & 125.43       & 111.70            & 138.32              \\
	      			\hline
	      			\textbf{Duration}  &                       &            &                   & 4.21           & 0.50           & 5.0           & 11.29        & 4.60              &                     \\
	      			\hline
	      			
	      			\textbf{Convexity} &                       &            &                   & 19.64          & 0.25           & 25.0          & 58.45        & 22.30             &                     \\
	      			\hline
	      		\end{tabular}
	      		\caption{Calculations of Prices,  Durations,  Convexities}
	      		\label{tab:prices_durations_convexities}
	      	\end{table}
	      	
	      	\textbf{Solution:} It then follows that the duration of the Leveraged Inverse Floater is
	      	$$
	      	D_{LIF} = \frac{1}{P_{LIF}} \left( P_{Fixed}(0,  5) \times D_{Fixed} - 2 \times P_{Fl}(0; 5) \times D_{Fl} + 2 \times Z(0; 5) \times D_Z \right)
	      	$$
	      	$$
	      	= \frac{1}{125.43} \left( 140.74 \times 4.214 - 2 \times 1 \times 0.5 + 2 \times 92.35 \times 5 \right) = 11.29
	      	$$
	      	
	      	According to the duration of LIF of 11.29,  it is obvious that it has quite a high sensitivity to interest rates. Figure 3 plots the value of the Leveraged Inverse Floater,  plotted against a parallel shift in the term structure of interest rates. The decline in value for a shift up in interest rates is quite dramatic. The dash-dotted line plots the decline in value for the 5-year fixed rate bond,  with coupon rate 4.0\%,  which is valued at 111.70 on February 17,  2009. The duration of the 5-year fixed bond is 4.60. Thus,  the sensitivity to interest rates is much smaller,  as illustrated in Figure 3.
	      	
	      	Finally,  note in Figure 3 that the perturbations are mainly positive. This is because the short rate is already at 0.49\%,  so negative parallel shifts must be quite small to keep the short rate sensible.
	      	    
	      	
	      	    
	      	\item[(PP)] Discuss your finding regarding the duration of the Leverage Inverse Floater and discuss the risk that an investor may face by investing in the Leverage Inverse Floater. In particular,  compare the duration (and risk) of the Leverage Inverse Floater to that of a regular existing traded fixed-rate note with the same maturity.
	      	    
	      	\textbf{Solution:} Based on the duration of LIF of 11.29,  it is obvious that it has quite a high sensitivity to interest rates. Figure 3 plots the value of the Leveraged Inverse Floater,  plotted against a parallel shift in the term structure of interest rates. The decline in value for a shift up in interest rates is quite dramatic. The dash-dotted line plots the decline in value for the 5-year fixed rate bond,  with coupon rate 4.0\%,  which is valued at 111.70 on February 17,  2009. The duration of the 5-year fixed bond is 4.60. Thus,  the sensitivity to interest rates is much smaller,  as illustrated in Figure 3.
	      	
	      	Finally,  note in Figure 3 that the perturbations are mainly positive. This is because the short rate is already at 0.49%,  so negative parallel shifts must be quite small to keep the short rate sensible.
	      	    
	      	\item[(PP)] Describe the convexity of a fixed income security and how it is calculated in general. How is the convexity of the Leverage Inverse Floater calculated? What are its components?
	      	    
	      	\textbf{Solution:} In general,  convexity of the fixed rate bond is calculated as follows:
	      	$$
	      	C_{Fixed} = \sum_{i=1}^n w_i T_i^2 = 19.6431
	      	$$
	      	
	      	Accordingly,  convexity of the inverse floater can be computed as the weighted average of the convexities of the securities in the mimicking portfolio. The convexity of the zero coupon bond is $C_Z = 5^2 = 25$,  while the convexity of the floating rate bond is essentially zero $C_{Fl} = 0.5^2 = 0.25$.
	      	
	      	\item[(CP)] What is the value of the convexity of the Leverage Inverse Floater? Discuss.
	      	    
	      	\textbf{Solution:} It follows that the convexity of the inverse floater is
	      	$$
	      	C_{LIF} = \frac{1}{P_{LIF}} \left( P_{Fixed}(0,  5) \times C_{Fixed} - 2 \times P_{Fl}(0; 5) \times C_{Fl} + 2 \times Z(0; 5) \times C_Z \right)
	      	$$
	      	$$
	      	= \frac{1}{125.43} \left( 140.74 \times 19.6431 - 2 \times 100 \times 0.25 + 2 \times 92.35 \times 25 \right) = 58.45
	      	$$
	      	Compare this to the quoted 5-year fixed rate bond which has a much lower convexity of 22.30.
	      	    
	      	\begin{table}[h!]
	      		\centering
	      		\begin{tabular}{|cccc|ccccc|}
	      			\hline
	      			\textbf{T} & \textbf{Y} & \textbf{Y Shift} & \textbf{Z}     & \textbf{Fixed} & \textbf{Float} & \textbf{Zero} & \textbf{LIF} & \textbf{4\% Bond} \\
	      			\hline
	      			-          & 0          & 1.0000           & -              & 100.00         & 100.00         & 2.0           & -            & -                 \\
	      			0.5        & 0.004975   & (0.00002)        & 1.0000         & 5.0            & -              & -             & -            & 2.0               \\
	      			1.0        & 0.005804   & 0.00080          & 0.9992         & 5.0            & -              & -             & -            & 2.0               \\
	      			1.5        & 0.006244   & 0.00124          & 0.9981         & 5.0            & -              & -             & -            & 2.0               \\
	      			2.0        & 0.006942   & 0.00194          & 0.9961         & 5.0            & -              & -             & -            & 2.0               \\
	      			2.5        & 0.008430   & 0.00343          & 0.9915         & 5.0            & -              & -             & -            & 2.0               \\
	      			3.0        & 0.012256   & 0.00726          & 0.9785         & 5.0            & -              & -             & -            & 2.0               \\
	      			3.5        & 0.011218   & 0.00712          & 0.9754         & 5.0            & -              & -             & -            & 2.0               \\
	      			4.0        & 0.013147   & 0.00842          & 0.9696         & 5.0            & -              & -             & -            & 2.0               \\
	      			4.5        & 0.014752   & 0.00975          & 0.9571         & 5.0            & -              & -             & -            & 2.0               \\
	      			5.0        & 0.015939   & 0.01094          & 0.9468         & 105.0          & -              & -             & 100.00       & 102.0             \\
	      			\hline
	      			           &            &                  & \textbf{Price} & 143.72         & 100.00         & 94.68         & 133.08       & 114.30            \\
	      			\hline
	      		\end{tabular}
	      		\caption{Sensitivity of Portfolio to Parallel Shift in Term Structure}
	      		\label{tab:sensitivity}
	      	\end{table}
	      	    
	      	\begin{figure}  
	      		\centering
	      		\includegraphics[width=0.8\textwidth]{hw2-3}
	      		\caption{Interest Rate Sensitivity}
	      	\end{figure}    
	      	    
	      	  
	      	        
	      	
	      	\item \textbf{THIS IS AN OPTIONAL QUESTION FOR THOSE THAT ARE INTERESTED! Value-at-Risk calculations}
	      	\begin{description}
	      		\item[(PP)] Describe the Value-at-Risk concept and how it can be applied to fixed income securities,  including Leverage Inverse Floaters. \\
	      		\item \indent \textbf{Solution:}Value-at-Risk (VaR) is a statistical measure used to assess the potential loss in value of a portfolio over a defined period for a given confidence interval. It provides an estimate of the maximum loss that a portfolio could face due to market risk under normal market conditions. VaR can be applied to fixed income securities,  including Leverage Inverse Floaters,  to measure the risk associated with fluctuations in interest rates.\\
	      		     
	      		The main parameters for VaR are:
	      		\begin{itemize}
	      			\item	1.	Time Horizon: The period over which the risk is assessed.
	      			\item 2.Confidence Level: The probability that the loss will not exceed the VaR.
	      			\item 3.Loss Amount: The potential loss in value.\\
	      		\end{itemize} 
	      		For fixed income securities,  VaR can be calculated by considering the changes in interest rates and their impact on the prices of the securities. The key parameters involved in the calculation are the duration and convexity of the securities,  which measure the sensitivity of the security's price to changes in interest rates.\\ \\
	      		Leverage Inverse Floaters (LIF) are a type of fixed income security with high sensitivity to interest rate changes due to their leveraged nature. The coupon payments of an LIF typically increase when interest rates fall,  and decrease when interest rates rise,  making their price movements highly volatile. To compute the VaR for LIF,  we need to factor in this heightened sensitivity,  which is reflected in their high duration and convexity.
	      		    
	      		\item[(CP)] Use the Duration and Convexity computed in Part 3 along with the data in DBT6 tab of the data file provided to assess the risk of the Leverage Inverse Floater. In particular,  compute the 1-day,  95\% and 99\% Value-at-Risk of the Leverage Inverse Floater,  by using both the “historical approach, ” and the “normal distribution.” Compare the result Value-at-Risk with the one of a regular 5-year bond. Comment. Tip: See Veronesi’s Book,  Ch. 3.2.8 and 3.8. In particular,  the 100-$\omega$\% Value-at-Risk is the value VaR such that $Pr(L < VaR) = \omega$ where $L$ is the portfolio dollar loss over one day.  
	      	\end{description}
	      	\begin{table}[h!]
	      		\centering
	      		\begin{tabular}{|c|c|c|}
	      			\hline
	      			\textbf{VaR Metric}       & \textbf{Leverage Inverse Floater} & \textbf{5-year Bond} \\
	      			\hline
	      			1-day 95\% VaR            & -169.76                           & -55.64               \\
	      			1-day 99\% VaR            & -250.58                           & -81.99               \\
	      			1-day 95\% Historical VaR & 200.13                            & 64.76                \\
	      			1-day 99\% Historical VaR & 615.99                            & 198.09               \\
	      			\hline
	      		\end{tabular}
	      		\caption{1-day VaR Values for Leverage Inverse Floater and 5-year Bond}
	      		\label{tab:1day_var}
	      	\end{table} 
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{images/hw2-4}
	      	\end{figure}    
	      	    
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=1\textwidth]{images/hw2-5}
	      	\end{figure}  
	      	    
	      \end{description}
\end{enumerate}
```

## HW 3

```latex
\maketitle
\section*{Homework 3}
\textbf{Due at the beginning of Class 4}

\begin{quote}
	\textbf{Note 1:} For each section below,  there are questions that require a “pencil and paper” (PP) answer,  and questions that require actual computations using data and computer programs (CP). You are supposed to do both.
	
	\textbf{Note 2:} As with Homework \#1 there are “guides” for doing the homework in Excel,  Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.
\end{quote}

\subsection*{Part I: Duration Hedging and Factor Neutrality}
Consider the Leverage Inverse Floater discussed in HW 2. The data set FBYields 2024 v2.xlsx contains monthly data on continuously compounded zero coupon yields (1 month - 5 years) from June 1952 to December 2023.

\begin{enumerate}
	\item[(PP)] Describe the Principal Component methodology,  and what “Level, ” “Slope, ” and “Curvature” mean? Are these assumptions or results of the analysis? Why the names?
	          
	      \textbf{Solution:} Principal Component Analysis (PCA) is a statistical technique used to simplify the complexity in high-dimensional data while retaining trends and patterns. It transforms the data into a new coordinate system such that the greatest variance by any projection of the data comes to lie on the first coordinate (called the first principal component),  the second greatest variance on the second coordinate,  and so on. In the context of yield curves,  PCA helps identify the key factors driving changes in interest rates across different maturities.
	          
	      The terms "Level, " "Slope, " and "Curvature" refer to the first three principal components of the yield curve movements:
	      \begin{itemize}
	      	\item \textbf{Level:} Represents parallel shifts in the yield curve,  affecting all maturities equally.
	      	\item \textbf{Slope:} Represents changes in the steepness of the yield curve,  typically affecting short and long maturities in opposite directions.
	      	\item \textbf{Curvature:} Represents changes in the curvature of the yield curve,  typically affecting medium-term maturities more than short or long ones.
	      \end{itemize}
	      
	      
	\item[(CP)] Use this zero-coupon bond term structure to compute the value of the LIF on March 31,  2009 as well as on April 30,  2009. Compare the change in value of LIF with the one predicted by the duration computation performed in HW 2 (for the latter computation,  you have to compute the average change in the term structure over the two dates (why?)). Discuss your results,  also in view of the actual change of the term structure of interest rates over the two dates. (Tip: It is OK for this exercise to keep the maturity of LIF to 5 years on both dates. Tip 2: It helps to actually plot the term structures on the dates on the same graph.)
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|ccccccccc|}
	      		\hline
	      		& 20090331 &  & & LIF Cash Flows & & \\
	      		\hline
	      		T         & $T^2$ & YC       & Z      & Fixed  & Float  & Zero   & LIF    \\
	      		\hline
	      		-         & -     & -        & 1.0000 & -      & -      & 100.00 & -      \\
	      		0.50      & 0.25  & 0.003353 & 0.9983 & 5.0    & -      & -      & -      \\
	      		1.00      & 1.00  & 0.006119 & 0.9939 & 5.0    & -      & -      & -      \\
	      		1.50      & 2.25  & 0.006987 & 0.9886 & 5.0    & -      & -      & -      \\
	      		2.0       & 4.00  & 0.007781 & 0.9846 & 5.0    & -      & -      & -      \\
	      		2.50      & 6.25  & 0.009695 & 0.9761 & 5.0    & -      & -      & -      \\
	      		3.00      & 9.00  & 0.011627 & 0.9657 & 5.0    & -      & -      & -      \\
	      		3.50      & 12.25 & 0.012508 & 0.9572 & 5.0    & -      & -      & -      \\
	      		4.00      & 16.00 & 0.013362 & 0.9480 & 5.0    & -      & -      & -      \\
	      		4.50      & 20.25 & 0.014802 & 0.9356 & 5.0    & -      & -      & -      \\
	      		5.0       & 25.0  & 0.016709 & 0.9199 & 105.0  & -      & 100.0  & -      \\
	      		\hline
	      		Price     &       &          &        & 140.33 & 100.00 & 91.99  & 124.30 \\
	      		Duration  &       &          &        & 4.21   & 0.50   & 5.0    & 11.35  \\
	      		Convexity &       &          &        & 19.63  & 0.25   & 25.0   & 58.76  \\
	      		\hline
	      	\end{tabular}
	      	\caption{Data for March 31st,  2009}
	      \end{table}
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|ccccccccc|}
	      		\hline
	      		  & 20090430 &   &   &   &   & LIF Cash Flows &   &   \\
	      		\hline
	      		T & $T^2$ & YC & Z & Fixed & Float & Zero & LIF \\
	      		\hline
	      		- & - & - & 1.0000 & - & - & 100.00 & - \\
	      		0.50 & 0.25 & 0.002596 & 0.9987 & 5.0 & - & - & - \\
	      		1.00 & 1.00 & 0.005077 & 0.9949 & 5.0 & - & - & - \\
	      		1.50 & 2.25 & 0.007088 & 0.9894 & 5.0 & - & - & - \\
	      		2.0 & 4.00 & 0.009054 & 0.9821 & 5.0 & - & - & - \\
	      		2.50 & 6.25 & 0.011494 & 0.9717 & 5.0 & - & - & - \\
	      		3.00 & 9.00 & 0.013822 & 0.9594 & 5.0 & - & - & - \\
	      		3.50 & 12.25 & 0.015542 & 0.9471 & 5.0 & - & - & - \\
	      		4.00 & 16.00 & 0.017101 & 0.9339 & 5.0 & - & - & - \\
	      		4.50 & 20.25 & 0.018712 & 0.9192 & 5.0 & - & - & - \\
	      		5.0 & 25.0 & 0.020305 & 0.9035 & 105.0 & - & 100.0 & - \\
	      		\hline
	      		Price & & & & 138.35 & 100.00 & 90.35 & 119.04 \\
	      		Duration & & & & 4.20 & 0.50 & 5.0 & 11.63 \\
	      		Convexity & & & & 19.57 & 0.25 & 25.0 & 60.28 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Data for April 30th,  2009}
	      \end{table}
	      
	      
	      \textbf{Solution:} For simplicity,  we are going to assume that at the two dates the LIF still has 5 years to maturity. To find the price of the LIF,  we need to find zero coupon prices to discount the cash flows of the security. The $Z$'s are embedded in the yield curve data given so we need to extract them. Unlike homework 2,  this time we cannot proceed by bootstrapping since we do not have price data for bonds of different maturities as of each date. An alternative is to interpolate the [[Lecture 7-Risk and Return of Bonds#7.1 Zero-coupon yield curve|zero-coupon yield curve]] using the data given. Interpolation is fine in this case because these are zero coupon yields,  and so there is no theoretical error in doing this approximation. In Matlab we can do the interpolation as follows:
	      $$
	      Y_{\text{int}} = \text{interp1}(\text{Mat},  \text{yields},  \text{MatInt},  'cubic')
	      $$
	      where Mat is a vector of the maturities for which we have data,  yields is a vector with the corresponding data on yields,  MatInt is the vector of maturities (in this case semi-annual) for which we need yields,  and cubic is just the interpolation method (cubic uses a polynomial of degree 3 to approximate the yield curve).
	      
	      Once we have built the yield curve we can back out the $Z$'s and calculate the value of the LIF as we did in homework 2. The price of the LIF as of the two dates is:
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{l c}
	      		\hline
	      		                                & LIF Prices \\
	      		\hline
	      		$P_{\text{LIF}}$ March 31,  2009 & 124.30     \\
	      		$P_{\text{LIF}}$ April 30,  2009 & 119.04     \\
	      		\hline
	      	\end{tabular}
	      	\caption{LIF Prices}
	      \end{table}
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.9\textwidth]{images/hw3-1}
	      	\caption{Term Structures on March 31,  2009 and April 30,  2009}
	      \end{figure}
	      
	      Now we can compare the change in price between the two dates with the one predicted by the duration and convexity calculation performed in homework 2. For the duration-based calculation,  we need to compute an average change across maturities. The reason is that duration refers to a price change as a result of a parallel shift in the term structure,  which means that we need to summarize the change in the yield curve by just one number. The results are:
	         
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{cc}
	      		\hline
	      		T                         & dr         \\
	      		\hline
	      		0.50                      & (0.000757) \\
	      		1.00                      & (0.001043) \\
	      		1.50                      & 0.000097   \\
	      		2.0                       & 0.001273   \\
	      		2.50                      & 0.001739   \\
	      		3.00                      & 0.002194   \\
	      		3.50                      & 0.003034   \\
	      		4.00                      & 0.003739   \\
	      		4.50                      & 0.003910   \\
	      		5.0                       & 0.003596   \\
	      		\hline
	      		Mean (dr)                 & 0.001784   \\
	      		Duration                  & 11.35      \\
	      		Convexity                 & 58.76      \\
	      		Return (Duration Based)   & -2.026\%   \\
	      		Return (Dur/Convex Based) & -2.016\%   \\
	      		Return (Actual)           & -4.233\%   \\
	      		\hline
	      	\end{tabular}
	      	\caption{Duration and Convexity Data}
	      \end{table}
	         
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{l c c c}
	      		\hline
	      		            & Dur-based Return (\%) & Dur/Conv-based Return (\%) & Actual Return (\%) \\
	      		\hline
	      		Return (\%) & -2.015                & -2.05                      & -4.233             \\
	      		\hline
	      	\end{tabular}
	      	\caption{Duration and Convexity Approximations}
	      \end{table}
	      
	      As we can see,  both the duration-based computation and the duration/convexity-based computation understate the change in value. The reason is that the yield curve is changing its shape in a non-parallel manner as shown in Figure 1. One way to take into account these non-parallel changes is to use two or more factors from the principal components analysis.
	      
	      
	      
	      
	\item[(CP)] Use the time series of the data to compute the Principal Component betas for level and slope. Plot the beta coefficients as well as the level and slope factors (Tip: See the Guide files for Matlab or Excel).
	      
	      \textbf{Solution:} The principal components approach is explained in detail in TN2. Notice that the magnitude of the eigenvalues is related to the proportion of the variance in the data explained by their corresponding factors. Matlab orders the eigenvalues in ascending order. Therefore,  if we want to use a two-factor model the eigenvectors that we must use are the last two in the matrix of eigenvectors (with eigenvalues $\lambda_1 = 1.581$ and $\lambda_2 = 0.103$). The following are the betas corresponding to the first two factors:
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.9\textwidth]{images/hw3-2}
	      	\caption{Factor Loadings}
	      \end{figure}
	      
	          
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{c c c}
	      		\hline
	      		Maturity (years) & $\beta_{1, i}$ & $\beta_{2, i}$ \\
	      		\hline
	      		0.5              & 0.3391        & 0.6615        \\
	      		1                & 0.3657        & 0.3785        \\
	      		1.5              & 0.3519        & 0.1677        \\
	      		2                & 0.3321        & -0.0047       \\
	      		2.5              & 0.3178        & -0.1024       \\
	      		3                & 0.3060        & -0.1752       \\
	      		3.5              & 0.2976        & -0.2558       \\
	      		4                & 0.2900        & -0.3132       \\
	      		4.5              & 0.2804        & -0.3182       \\
	      		5                & 0.2669        & -0.2916       \\
	      		\hline
	      	\end{tabular}
	      	\caption{Factor Betas}
	      \end{table}
	          
	         
	      As in the teaching notes,  the first factor came out to have loadings (i.e. $\beta$'s) approximately constant across maturities,  and for this reason can be referred to as a "level" factor. The second factor has loading that switches sign between positive (at the short end) to negative (at the long end),  implying that when this factor kicks in,  the short-end of the term structure increases,  while the long end decreases. Such a behavior implies a shift in the slope of the term structure,  from which the name “Slope factor”. Note that differently from the TN,  the betas of the second factor are positive at the short end and negative at the long end of the maturity spectrum,  rather than the other way around. In PCA there is an indeterminacy between the signs of $\beta$'s and the sign of the factor. If we define a new factor $\tilde{\phi}_2 = -\phi_2$,  we obtain a factor that has loadings that are negative at the short end and positive at the long end of the maturity spectrum. The important fact is that when this factor kicks in,  it changes the slope.
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{images/hw3-3}
	      	\vspace{-25pt} % Adjust the value as needed
	      	\caption{Factor Loading on Level}
	      \end{figure}
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{images/hw3-4}
	      	\vspace{-25pt} % Adjust the value as needed
	      	\caption{Factor Loading on Slope}
	      \end{figure}
	      
	\item[(CP)] Compute the factor durations against level and slope. (Tip: This is a small modification from the solution to HW 2)
	      
	      \textbf{Solution:} To calculate the factor durations we use the formulas in TN2. The duration of the LIF and its components with respect to the level and slope factors is:
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{l c c}
	      		\hline
	      		Security & Level Duration & Slope Duration \\
	      		\hline
	      		LIF      & 3.007          & -3.953         \\
	      		Fixed    & 1.155          & -1.118         \\
	      		Zero     & 1.335          & -1.458         \\
	      		Floating & 0.170          & 0.331          \\
	      		\hline
	      	\end{tabular}
	      	\caption{Factor Durations}
	      \end{table}
	          
	      
	\item[(CP)] Compare the variation in LIF (in point (A)) with the one predicted from the factor duration in point (B). Discuss. (To compute the actual change in Factor 1 (level) and 2 (slope),  you just have to multiply the betas in point (B) by the actual change in the yields over the two days.)
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{ccccccccc}
	      		\hline
	      		  & 20090331 &   &   &   &   & LIF Cash Flows &   &   \\
	      		\hline
	      		T & $T^2$ & YC & Z & Fixed & Float & Zero & LIF \\
	      		\hline
	      		- & - & - & 1.0000 & - & - & 100.00 & - \\
	      		0.50 & 0.25 & 0.003353 & 0.9983 & 5.0 & - & - & - \\
	      		1.00 & 1.00 & 0.006119 & 0.9939 & 5.0 & - & - & - \\
	      		1.50 & 2.25 & 0.006987 & 0.9886 & 5.0 & - & - & - \\
	      		2.0 & 4.00 & 0.007781 & 0.9846 & 5.0 & - & - & - \\
	      		2.50 & 6.25 & 0.009695 & 0.9761 & 5.0 & - & - & - \\
	      		3.00 & 9.00 & 0.011627 & 0.9657 & 5.0 & - & - & - \\
	      		3.50 & 12.25 & 0.012508 & 0.9572 & 5.0 & - & - & - \\
	      		4.00 & 16.00 & 0.013362 & 0.9480 & 5.0 & - & - & - \\
	      		4.50 & 20.25 & 0.014802 & 0.9356 & 5.0 & - & - & - \\
	      		5.0 & 25.0 & 0.016709 & 0.9199 & 105.0 & - & 100.0 & - \\
	      		\hline
	      		Price & & & & 140.33 & 100.00 & 91.99 & 124.30 \\
	      		Duration & & & & 4.21 & 0.50 & 5.0 & 11.35 \\
	      		Convexity & & & & 19.63 & 0.25 & 25.0 & 58.76 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Data for March 31st,  2009}
	      \end{table}
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{ccccccccc}
	      		\hline
	      		  & 20090430 &   &   &   &   & LIF Cash Flows &   &   \\
	      		\hline
	      		T & $T^2$ & YC & Z & Fixed & Float & Zero & LIF \\
	      		\hline
	      		- & - & - & 1.0000 & - & - & 100.00 & - \\
	      		0.50 & 0.25 & 0.002596 & 0.9987 & 5.0 & - & 100.00 & - \\
	      		1.00 & 1.00 & 0.005077 & 0.9949 & 5.0 & - & - & - \\
	      		1.50 & 2.25 & 0.007088 & 0.9898 & 5.0 & - & - & - \\
	      		2.0 & 4.00 & 0.009054 & 0.9821 & 5.0 & - & - & - \\
	      		2.50 & 6.25 & 0.011494 & 0.9717 & 5.0 & - & - & - \\
	      		3.00 & 9.00 & 0.013822 & 0.9598 & 5.0 & - & - & - \\
	      		3.50 & 12.25 & 0.015542 & 0.9471 & 5.0 & - & - & - \\
	      		4.00 & 16.00 & 0.017101 & 0.9339 & 5.0 & - & - & - \\
	      		4.50 & 20.25 & 0.018712 & 0.9192 & 5.0 & - & - & - \\
	      		5.0 & 25.0 & 0.020305 & 0.9035 & 105.0 & - & 100.00 & - \\
	      		\hline
	      		Price & & & & 138.35 & 100.00 & 90.35 & 119.04 \\
	      		Duration & & & & 4.20 & 0.50 & 5.0 & 11.63 \\
	      		Convexity & & & & 19.57 & 0.25 & 25.0 & 60.28 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Data for April 30th,  2009}
	      \end{table}
	      
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{cc}
	      		\hline
	      		                          & Value      \\
	      		\hline
	      		dr: Level                 & 0.005105   \\
	      		dr: Slope                 & (0.005694) \\
	      		Factor Duration           & (0.0385)   \\
	      		\hline
	      		Return (Duration Based)   & -2.026\%   \\
	      		Return (Dur/Convex Based) & -2.016\%   \\
	      		Return (Factor Based)     & -3.849\%   \\
	      		Return (Actual)           & -4.233\%   \\
	      		\hline
	      	\end{tabular}
	      	\caption{Factor Returns and Durations}
	      \end{table}
	      
	      \textbf{Solution:} With the factor durations,  now we can calculate the predicted change in the value of the LIF given the change in the factors between the two dates as follows:
	      $$
	      \% \Delta P_{\text{LIF}} = -D_{\text{LIF, level}} \times \Delta \phi_{\text{level}} - D_{\text{LIF, slope}} \times \Delta \phi_{\text{slope}}
	      $$
	      \begin{table}[H]
	      	\centering
	      	\small
	      	\begin{tabular}{l c c c c}
	      		\hline
	      		            & Dur-based Return (\%) & Dur/Conv-based Return (\%) & Factor-Based Return (\%) & Actual Return (\%) \\
	      		\hline
	      		Return (\%) & -2.015                & -2.05                      & -3.786                   & -4.233             \\
	      		\hline
	      	\end{tabular}
	      	\caption{Duration,  Convexity,  and Factor Approximations}
	      \end{table}
	      
	      We see that the factor-based prediction is much closer to the actual return. The reason is that the factors incorporate changes along the entire term structure taking into account that those changes do not affect all maturities in the same magnitude or in the same direction.
\end{enumerate}

\section*{Part II: Predicting Zero-Coupon Bond Returns}
\textbf{Recommended readings:}
\begin{itemize}
	\item Book. Chapter 7.3
	\item Cochrane and Piazzesi (2005) “Bond Risk Premia” American Economic Review. \\
	      \url{http://www.stanford.edu/~piazzesi/cp.pdf}
\end{itemize}

\begin{enumerate}
	\item[(PP)] Explain the logic behind Fama-Bliss regressions. According to the Expectation Hypothesis,  what should be the regression coefficients of the regression?
	      
	      \textbf{Solution:} The Fama-Bliss regression is used to test the Expectation Hypothesis (EH) which posits that the forward rates are unbiased predictors of future spot rates. The regression typically takes the form:
	      $$
	      r_{t+1}(n-1) - r_t(n) = \alpha + \beta (f_t(n) - r_t(n)) + \epsilon_t
	      $$
	      where $r_{t+1}(n-1)$ is the realized return on an $n-1$ year bond,  $r_t(n)$ is the $n$-year yield at time $t$,  and $f_t(n)$ is the forward rate implied by the term structure. According to the Expectation Hypothesis,  the forward rates should be unbiased predictors of the future spot rates,  which implies that $\alpha$ should be zero and $\beta$ should be one.
	      
	\item[(CP)] Use the data FBYields 2024 v2.xlsx and run Fama-Bliss and Cochrane-Piazzesi annual predictive regressions of zero coupon bonds with time to maturity $T = 2,  3,  4,  5$. Please,  only use annual data for this exercise,  so as to avoid econometric problems (overlapping samples).
	          
	          
	      \begin{description}
	      	\item[(CP)] Plot the expected excess return for the 5-year bond over time using both Fama-Bliss and Cochrane-Piazzesi methodologies. As of the last day in the sample (December 2023),  what is the 1-year forecast of the 5-year bond excess return? Compare the difference in prediction about the 2022-2023 excess bond returns between Fama and Bliss and Cochrane and Piazzesi.
	      	        
	      	\textbf{Solution:} We start by looking at some plots. Consider the forward spread and the annual return on the 5-year bond. Figure 11 shows their time series,  where we lag the return by 5 years to make it synchronous with the forward spread so as to highlight the correlation (if any).
	      	
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=0.8\textwidth]{Fama_Bliss_5-year_Bond_Return_and_5-year_Forward_Spread.png}
	      		\caption{Fama Bliss 5-year Bond Return and 5-year Forward Spread}
	      	\end{figure}
	      	
	      	Figure 12 also shows a scatter plot of the 5-year forward spread versus the bond return of a 5-year bond. The figures show an association between forward rates and subsequent bond returns,  although the cloud is rather wide and so the forward spread does not appear to explain a lot of the variation in bond returns. Figure 4 shows the (in sample) fit of the model,  when we predict future bond returns using the lagged forward spread.
	      	
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=0.8\textwidth]{hw3-5.png}
	      		\caption{Realized 5-year Bond Return vs 5-year Forward Spread}
	      	\end{figure}
	      	
	      	
	      	Table 1 below formalizes this evidence using OLS regressions. We regress the log excess bond return on the forward spread. Let $Z_t(n)$ denote the zero coupon bond in year $t$ with $n$ years to maturity. Define the log excess bond return using a $n$-year bond as
	      	$$
	      	LER_t(n) = \log \left( \frac{Z_{t+1}(n-1)}{Z_t(n)} \right) - \log \left( \frac{1}{Z_t(1)} \right)
	      	$$
	      	Denote also $f_t(n)$ the forward rate at $t$ for an investment at $n-1$ and maturity $n$. As we know $f_t(n) = \log \left( \frac{Z_t(n)}{Z_t(n-1)} \right)$. We then run the regression
	      	$$
	      	LER_t(n) = \alpha + \beta [f_t(n) - y_t(1)] + \epsilon_t
	      	$$
	      	Table 1 shows the results for each zero-coupon bond with maturity $n = 2,  \ldots,  5$.
	      	
	      	\begin{table}[H]
	      		\centering
	      		\begin{tabular}{l c c c c c}
	      			\hline
	      			n      & $\alpha$ & $\beta$ & $t(\alpha)$ & $t(\beta)$ & $R^2$  \\
	      			\hline
	      			2.000  & 0.0467   & 0.7926  & 0.1937      & 2.4776     & 0.0839 \\
	      			3.0000 & -0.0935  & 1.0326  & -0.1907     & 2.4469     & 0.0820 \\
	      			4.0000 & -0.0918  & 1.0014  & -0.1327     & 2.1900     & 0.0668 \\
	      			5.000  & -0.2947  & 1.1750  & -0.3536     & 2.3812     & 0.0780 \\
	      			\hline
	      		\end{tabular}
	      		\caption{Fama - Bliss Regressions 1953 - 2023}
	      	\end{table}
	      	
	      	Note the implication of the empirical results:
	      	\begin{itemize}
	      		\item A high forward spread $\implies$ predict high future bond excess return.
	      		\item A positive bond excess return requires its yield to decline (yield $\downarrow \implies Z(t,  n) \uparrow$)
	      		\item The forward spread is high when the term structure slopes upwards
	      		\item $\implies$ a rising term structure predicts lower future yields.
	      	\end{itemize}
	      	\begin{figure}[H]
	      		\centering
	      		\includegraphics[width=0.8\textwidth]{Fama_Bliss_5-year_Bond_Return_and_Predicted_Return_from_5-year_Forward_Spread.png}
	      		\caption{Fama Bliss 5-year Bond Return and Predicted Return from 5-year Forward Spread}
	      	\end{figure}
	      	\item[(PP)] What do your results imply about time varying risk premia? Interpret in light of your knowledge of macro-economic events (inflation,  growth,  etc).
	      	
	      	\textbf{Solution:} The results suggest that time-varying risk premia are a significant component of bond returns. When the forward spread is high,  it indicates higher expected excess returns on bonds,  which can be interpreted as compensation for taking on more risk. This behavior is consistent with periods of economic uncertainty or higher inflation expectations,  where investors demand higher premiums for holding longer-term bonds. Conversely,  a low forward spread suggests lower risk premia,  aligning with periods of economic stability and low inflation expectations.
	      	
	      	\item[(PP)] How well can you predict future bond returns? Do your results differ from those illustrated in the teaching notes? Discuss.
	      	
	      	\textbf{Solution:} The predictive power of forward spreads on future bond returns is evident but not extremely strong,  as indicated by the $R^2$ values in the regressions. The scatter plots and regression results show a relationship,  but the variance explained by the models is limited. This aligns with the teaching notes,  which also highlight the challenge of predicting bond returns accurately due to the influence of various macroeconomic factors. However,  the consistency of the positive relationship between forward spreads and future returns underscores the utility of these predictors in fixed income analysis.
	      \end{description}
	      
	\item[(CP)] Cochrane - Piazzesi propose a single factor to predict future bond returns. In essence,  they define a factor as a linear combination of forward rates
	      $$
	      x_t = a_0 y_t + a_1 f^{(2)}_t + \ldots + a_5 f^{(5)}_t
	      $$
	      The coefficients $a_0,  \ldots,  a_5$ are estimated from another regression of average bond returns on forward rates. (This is slightly different from the question in the assignment,  in which you were allowed to (a) use the regression coefficient in the Teaching Notes; and (b) use only 3 forwards instead of 5 as in the original Cochrane and Piazzesi paper). Table 2 shows the results of the regression.
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{l c c c c c}
	      		\hline
	      		n      & $\alpha$ & $\beta$ & $t(\alpha)$ & $t(\beta)$ & $R^2$  \\
	      		\hline
	      		2.000  & -0.0353  & 0.4761  & -0.1501     & 3.1582     & 0.1296 \\
	      		3.0000 & -0.0791  & 0.8960  & -0.1848     & 3.2647     & 0.1372 \\
	      		4.0000 & -0.1820  & 1.2770  & -0.3113     & 3.4044     & 0.1475 \\
	      		5.000  & -0.4561  & 1.6369  & -0.6162     & 3.4468     & 0.1506 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Cochrane - Piazzesi Regressions: 1953 - 2023}
	      \end{table}
	      
	      Figures 5 to 7 show the performance of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor to predict the return of a 5-year bond. Note that Figure 7 shows that the expected excess return predicted by [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor at the end of the sample is negative. That is,  the model implies a negative risk premium on the 5-year bond for the next year.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{CP-_5-year_Bond_Return_and_CP_Factor.png}
	      	\caption{CP- 5-year Bond Return and [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] Factor}
	      \end{figure}
	      
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{Realized_5-year_Bond_Return_vs_5-year_CP_Factor.png}
	      	\caption{Realized 5-year Bond Return vs 5-year [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] Factor}
	      \end{figure}
	      
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw3-8.png}
	      	\caption{CP- 5-year Bond Return and Predicted Return from [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] Factor}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{CP-_5-year_Bond_Return_and_Predicted_Return_from_CP_Factor.png}
	      	\caption{CP- 5-year Bond Return and Predicted Return from [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] Factor}
	      \end{figure}
	      
	      
	      
	      \subsection*{In-Sample vs Out-of-Sample Predictive Regressions (this was not part of the assignment)}
	      
	      One important issue with the Cochrane - Piazzesi factor compared to Fama - Bliss is that the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] regression is in sample. That is,  the factor [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is first computed with a regression over the overall sample,  and then it is used to predict future bond returns. For the purpose of the paper – namely,  the inference about the existence of a common factor affecting bond returns – the procedure is fine. The objective of investigation in Cochrane and Piazzesi was to discover if there is a common factor affecting all bond expected excess returns. In sample regressions are perfectly fine for this investigation. However,  if we want to have an investment strategy we cannot use an in-sample regression,  but we need an out-of-sample one. One possibility is to use data up to $t$ to compute the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor,  and then use data after $t$ for the regression. This can be done. However,  another methodology is to just use the forward rates used by [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] to predict future bond returns. That is,  run
	      
	      $$
	      LER_t(n) = \alpha + \beta_1 y_t(1) + \beta_2 f_t(3) + \beta_3 f_t(5) + \epsilon_t
	      $$
	      (we leave out $f_t(2)$ and $f_t(4)$ to avoid multicollinearity). Table 3 reports the result. As can be seen,  using the forward rates has a strong predictive power on future bond returns. That is,  the results of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor are not only due to it being an in-sample predictor,  but there is something in the forward rates that help explain future bond returns.
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{l c c c c c c c c c}
	      		\hline
	      		n      & $\alpha$ & $y_t(1)$ & $f_t(3)$ & $f_t(5)$ & $t(\alpha)$ & $t(y_t(1))$ & $t(f_t(3))$ & $t(f_t(5))$ & $R^2$  \\
	      		\hline
	      		2.000  & -0.9287  & -0.4445  & 0.5145   & 0.1040   & -2.0245     & -1.8193     & 1.0977      & 0.3114      & 0.1473 \\
	      		3.0000 & -1.3791  & -1.0557  & 1.3420   & -0.0475  & -1.6366     & -2.3523     & 1.5585      & -0.0774     & 0.1395 \\
	      		4.0000 & -1.8014  & -1.6754  & 2.0315   & -0.0831  & -1.5644     & -2.7319     & 1.7265      & -0.0991     & 0.1500 \\
	      		5.000  & -2.6458  & -2.0297  & 1.9953   & 0.3936   & -1.8130     & -2.6116     & 1.3381      & 0.3705      & 0.1515 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Forward-based Regressions: 1953 - 2023}
	      \end{table}
	      
	      \subsection*{PCA Regressions (Also this part was not part of the homework)}
	      
	      A final interesting question is whether PCA factors – level,  slope,  and curvature factors – described in the previous section,  are able to explain future bond returns. Indeed,  slope has been used several times as a predictor of future bond returns. Table 4 shows the result. Interestingly these factors are also predicting returns.
	      
	      \begin{table}[H]
	      	\small
	      	\centering
	      	\begin{tabular}{l c c c c c c c c c}
	      		\hline
	      		n      & $\alpha$ & Level   & Slope   & Curvature & $t(\alpha)$ & $t(\text{Level})$ & $t(\text{Slope})$ & $t(\text{Curvature})$ & $R^2$  \\
	      		\hline
	      		2.000  & -0.5401  & -0.0147 & -0.4397 & 0.9258    & -1.3640     & -0.4423           & -2.009            & 1.1241                & 0.1319 \\
	      		3.0000 & -1.0036  & -0.0382 & -0.9823 & 1.2145    & -1.3835     & -0.6271           & -2.4399           & 0.8049                & 0.1286 \\
	      		4.0000 & -1.5253  & -0.0715 & -1.5455 & 1.5574    & -1.5478     & -0.8642           & -2.8258           & 0.7598                & 0.1494 \\
	      		5.000  & -2.2703  & -0.1024 & -2.1469 & 1.7551    & -1.8359     & -0.9864           & -3.1282           & 0.6823                & 0.1675 \\
	      		\hline
	      	\end{tabular}
	      	\caption{PCA Regressions: 1953 - 2023}
	      \end{table}

```

## HW 4

```latex
\maketitle
\section*{Homework 4}
\textbf{Due at the beginning of Class 5}

\begin{quote}
	\textbf{Note 1:} For each section below,  there are questions that require a “pencil and paper” (PP) answer,  and questions that require actual computations using data and computer programs (CP). You are supposed to do both.
	
	\textbf{Note 2:} As with Homework \#1 there are “guides” for doing the homework in Excel,  Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.
\end{quote}

\subsection*{Part I: Real and Nominal Bonds}
The dataset “DataTIPS.xlsx” contains data on nominal bonds and Treasury Inflation Protected Securities (TIPS) on Jan 15,  2013.

\begin{enumerate}
	\item[(PP)] Write down the relation between nominal rates and real rates. Interpret each term economically.
	\item[(PP)] What does a negative real rate imply? Provide an intuition about negative real rates using more than one potential explanation.
	\item[(PP)] In the first quarter of 2013,  the median forecast of professional forecasters about the average three-month rate for the next 10 years was 2.4\%. Compare this average with your estimated nominal 10-year rate. Is it higher? Is it lower? Explain the difference,  if any,  in economic terms.
	\item[(CP)] Fit the Nelson Siegel model to the TIPS on Jan 15,  2013. Plot the resulting term structure of real rates. Interpret in light of your answer to point 2.
	\item[(CP)] Fit the Nelson Siegel model to the nominal bonds. Plot the resulting term structure of nominal rates. Interpret in light of your answer to point 3.
	\item[(CP)] Compute breakeven inflation rate,  that is,  those rate $\omega(\epsilon)$ such that $r_{\text{nominal}}(0,  \epsilon) = r_{\text{real}}(0,  \epsilon) + \omega(\epsilon)$. Interpret your results. What does the break-even rate really capture?
\end{enumerate}

\subsection*{Part II: Swap Spread Trades}
\textbf{Recommended readings:}
\begin{itemize}
	\item Book. Chapter 5.
	\item Harvard Business School Case: “Fixed Income Arbitrage in a Financial Crisis (C): TED Spread and Swap Spread in November 2008”
	\item Duarte,  Longstaff and Yu,  “Risk and Return in Fixed-Income Arbitrage: Nickels in Front of a Steamroller?” Review of Financial Studies,  2006. \url{http://www.owlnet.rice.edu/~jd10/nickelsRFS.pdf}
\end{itemize}

Today is February 17,  2009 and you are evaluating the Swap / Treasury curve. You decide to set up 100 million swap spread trade on the thirty-year T-Bond / Swap. Daily quote on the 30-year bond,  maturing on February 15 2039,  are contained in spreadsheet Daily Bond Swaps in HW4 Data.xls. The spreadsheet also contains daily data on the 30-year swap,  three month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and three month Repo rate. You have access to some past data,  such as the ones in the H15 Swap.txt,  which contains daily data on swap rates,  [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and Repo,  but for a longer sample,  as well as Treasury constant maturity rates. (All these data are also collected in the Excel guide 35130 HW4 2022 Guide.xlsx for Excel users).

\begin{enumerate}
	\item[(PP)] Look at the data and decide which direction to set up a swap spread trade. Is there an arbitrage? If so,  why do you think there is one? Discuss.
	\item[(PP)] What do you do? Describe the working of the swap spread trade. How do you take positions in the Treasury Bond? What about the swap?
	\item[(CP)] Consider now one quarter after the initiation of the trade (May 18,  2009). Suppose JCH Capital Management needs to liquidate the position immediately,  due to large unexpected redemptions from investors. What is the value of the swap-spread trade positions? In particular,  the trade has two parts: the T-Bond trade and the Swap trade. Compute the fair valuation of the two parts as follows:
	      \begin{itemize}
	      	\item[(A)] The value of the T-bond part is just the value of the bond,  multiplied by its position. You can read it right from the data. Recall though the overall position of the bond trade.
	      	\item[(B)] The value of the swap part should use the standard valuation formula of swaps,  as a fixed rate bond minus a floating rate bond (see Teaching Note 4,  page 11,  Eq.(8)). The floating rate leg should be “easy” (what is the value of floating rate bond at reset dates?). For the fixed leg,  proceed as follows:
	      	      \begin{itemize}
	      	      	\item Determine what is the appropriate “coupon rate” for the fixed leg of the swap in the valuation.
	      	      	\item Determine how many “coupon” periods there are left.
	      	      	\item To compute the present value of future coupons,  you need an appropriate discount function $Z(T)$. Extract the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve from current swap rates as of May 18,  2009,  using the procedure on TN3,  page 11. Because for maturity less than one year there are no swap quotes,  you can use [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rates themselves in the computation.
	      	      	      \begin{itemize}
	      	      	      	\item Note that you need an interpolation of maturities,  as data only come on fixed maturities,  but you need specific quarters to compute the present value.
	      	      	      \end{itemize}
	      	      	\item Plot the estimated zero-coupon [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve.
	      	      	\item Use the estimated $Z(T)$ to compute the value of the fixed leg of the swap.
	      	      \end{itemize}
	      	\item[(C)] Given your results in [A] and [B],  did the trade (so far) make money or lose money? Can you reconcile it with your answer to point 1? What happened to the swap spread between Feb 9 and May 18,  2009?
	      \end{itemize}
	         
	       
	\item[(CP)] (Optional: No Grade Given. No hint in the code.) Follow the trading strategy cash flows. What is the sequence of cash flows? Consider only quarterly frequency.
	\item[(CP)] (Optional: No Grade Given. No hint in the code.) Follow also the value of the trade over time. Consider only quarterly frequency.
\end{enumerate}

\section*{Part I: Real and Nominal Bonds}
\begin{enumerate}
	\item \noindent (PP): Write down the relation between nominal rates and real rates. Interpret each term economically.
	      
	      \textbf{Solution:} The relation between nominal rates and real rates is
	      $$
	      r_{\text{nominal}}(T) = r_{\text{real}}(T) + \pi(T) - \frac{1}{2}\sigma^2_\pi + \text{RP}
	      $$
	      That is,  the nominal rate equals the real rate,  plus expected inflation (this is the Fisher equation) plus a risk premium (RP) minus a (minor) convexity term,  as inflation increases nominal bonds in a convex manner. Higher expected inflation or higher risk premia increase the nominal rate. See discussion in the teaching notes.
	      
	\item (PP): What does a negative real rate imply? Provide an intuition about negative real rates using more than one potential explanation.
	      
	      \textbf{Solution:} The real rate can be negative. From the above relation,  this may simply mean that expected inflation is higher than the nominal rate (and the other terms). However,  economically,  why can a negative real rate occur? A simple decomposition of real rates has
	      $$
	      r_{\text{real}}(T) = \rho + \gamma \text{Expected GDP Growth} - \frac{\gamma^2}{2} \text{Macroeconomic Risk}
	      $$
	      That is,  why would an investor buy Treasury bonds? To set aside the issue of inflation,  consider TIPS (or real bonds). Why would an investor buy real bonds? Well,  for saving purposes. 
	      
	      However,  this desire to save depends on two quantities: The prediction of economic growth and the amount of uncertainty in the economy. The higher the expected economic growth,  the lower is the interest in savings. If the economy is strong,  our jobs are secure,  etc.,  then we can actually borrow (save less) to purchase homes,  cars,  and the like. This willingness of people to borrow for consumption tends to increase real rates ($r_{\text{real}}(T)$ increases). 
	      
	      On the other hand,  the higher the macroeconomic risk in the economy,  the higher is the likelihood of “rainy days” which provides an incentive to borrow less and rather purchase bonds (real bonds) to have a buffer against bad times (many financial advisors recommend families to set up “emergency funds”. Well,  do not invest your emergency fund in stocks,  as  you may need it exactly in bad times!). This savings requirement for rainy days tends to decrease bond rates (as households bid up the price of bonds).
	      
	      Negative rates therefore may be due to a combination of low economic growth prospects but large macroeconomic risk. These quantities are weighted by the risk aversion $\gamma$ of agents in the economy: the higher the risk aversion and the stronger the effects.
	      
	\item (CP): In the first quarter of 2013,  the median forecast of professional forecasters about the average three-month rate for the next 10 years was 2.4\%. Compare this average with your estimated nominal 10-year rate. Is it higher? Is it lower? Explain the difference,  if any,  in economic terms.
	      
	      \textbf{Solution:} How do risk premia affect all this? In the first quarter of 2013,  the median forecast of professional forecasters about the average three-month rate for the next 10 years was 2.4\%. Our estimates of the yield curve on Jan 15,  2013 show a 10-year yield around 2\%. This implies that the average expected future short-term rate over the next 10 years is 0.4\% higher than the 10-year yield. From the simple formula in TN3
	      $$
	      y_t(10) = E_t \left[ \frac{1}{n} \sum_{i=1}^{n} y_{t+i}(0.25) \right] + \text{RP}_t
	      $$
	      where $n = 40$ is the number of quarters in 10 years. If the yield is lower than the expected future yield,  according to the expectation hypothesis,  it should be due to a negative risk premium. A negative risk premium can occur whenever Treasury bonds have hedging properties against variation in the stock market.
	      
	\item Question 4: Fit the Nelson Siegel model to the TIPS on Jan 15,  2013. Plot the resulting term structure of real rates. Interpret in light of your answer to point 2.
	      
	      \textbf{Solution:} We finally move to fit the Nelson-Siegel model to the TIPS on Jan 15,  2013. From the formula in the teaching notes
	      $$
	      P_{\text{TIPS}} = \frac{\text{Idx}(T)}{\text{Idx}(0)} \left[ \sum_{i=1}^{n} \frac{c}{2} Z(0,  T_i) + Z(0,  T_n) \right]
	      $$
	      Quoted prices are already net of the index ratio. Moreover,  there is no accrued interest because the maturity is on the round semi-annual cycle. Therefore,  bid/ask reflect only the parenthesis itself. This makes it easier to compute the term structure of real rates then,  because we can use directly the bid/ask price (midpoint) and use those directly together with the cash flow matrix to compute the real zero coupon bonds.
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|c|c|c|}
	      		\hline
	      		\textbf{NS Parameters} & \textbf{Treasury Bond} & \textbf{TIPS} \\
	      		\hline
	      		$\theta_{0}$           & 0.0395                 & 0.0138        \\
	      		$\theta_{1}$           & -0.0262                & -0.0219       \\
	      		$\theta_{2}$           & -0.0739                & -0.0675       \\
	      		$\lambda$              & 2.093                  & 2.4401        \\
	      		\hline
	      	\end{tabular}
	      	\caption{Parameter Values for Nominal Treasury Bond and TIPS}
	      	\label{tab:params}
	      \end{table}
	      
	      $$
	      r_{real}(t) = \theta_{0} + \theta_{1} \left( \frac{1 - e^{-\lambda t}}{\lambda t} \right) + \theta_{2} \left( \frac{1 - e^{-\lambda t}}{\lambda t} - e^{-\lambda t} \right)
	      $$
	      
	      $$
	      r_{real}(t) = 0.0138 - 0.0219 \left( \frac{1 - e^{-2.4401 t}}{2.4401 t} \right) - 0.0675 \left( \frac{1 - e^{-2.4401 t}}{2.4401 t} - e^{-2.4401 t} \right)
	      $$
	      
	      \begin{table}[H]
	      	\centering
	      	\tiny
	      	\begin{tabular}{|l|c|c|c|c|c|c|c|c|c|c|}
	      		\hline
	      		\multirow{2}{*}{\textbf{Security}} & \multirow{2}{*}{\textbf{Coupon}} & \multirow{2}{*}{\textbf{Ask}} & \multirow{2}{*}{\textbf{Bid}} & \multirow{2}{*}{\textbf{Maturity}} & \multirow{2}{*}{\shortstack{\textbf{Time to}\\\textbf{maturity}}} & \multirow{2}{*}{\textbf{Issued}} & {\textbf{Ref CPI}} &
	      		\multirow{2}{*}{\textbf{Ref CPI}} &
	      		\multirow{2}{*}{\shortstack{\textbf{Index}\\\textbf{Ratio}}} \\
	      		& & & & & & & \textbf{at Issuance} & \\
	      		\hline
	      		TII 1.875 07/15/13 Govt & 1.875 & 101.945313 & 101.90625   & 7/15/13 & 0.5 & 7/15/03 & 183.66452 & 230.82203 & 1.256759  \\
	      		TII 2 01/15/14 Govt     & 2     & 103.546875 & 103.421875  & 1/15/14 & 1   & 1/15/04 & 184.77419 & 230.82203 & 1.249211  \\
	      		TII 2 07/15/14 Govt     & 2     & 105.953125 & 105.828125  & 7/15/14 & 1.5 & 7/15/04 & 188.49677 & 230.82203 & 1.224541  \\
	      		TII 1.625 01/15/15 Govt & 1.625 & 106.71875  & 106.6484375 & 1/15/15 & 2   & 1/15/05 & 190.94516 & 230.82203 & 1.208839  \\
	      		TII 1.875 07/15/15 Govt & 1.875 & 109.625    & 109.4765625 & 7/15/15 & 2.5 & 7/15/05 & 194.50968 & 230.82203 & 1.186668  \\
	      		TII 2 01/15/16 Govt     & 2     & 111.320313 & 111.1875    & 1/15/16 & 3   & 1/15/06 & 198.47742 & 230.82203 & 1.1629637 \\
	      		TII 2.5 07/15/16 Govt   & 2.5   & 115.414063 & 115.2890625 & 7/15/16 & 3.5 & 7/15/06 & 201.95161 & 230.82203 & 1.1435751 \\
	      		TII 2.375 01/15/17 Govt & 2.375 & 116.59375  & 116.46875   & 1/15/17 & 4   & 1/15/07 & 201.66452 & 230.82203 & 1.1445482 \\
	      		TII 2.625 07/15/17 Govt & 2.625 & 120.289063 & 120.109375  & 7/15/17 & 4.5 & 7/15/07 & 207.25639 & 230.82203 & 1.1137028 \\
	      		TII 1.625 01/15/18 Govt & 1.625 & 116.390625 & 116.203125  & 1/15/18 & 5   & 1/15/08 & 209.49645 & 230.82203 & 1.1017945 \\
	      		TII 1.375 07/15/18 Govt & 1.375 & 116.882813 & 116.703125  & 7/15/18 & 5.5 & 7/15/08 & 215.63997 & 230.82203 & 1.0704074 \\
	      		TII 2.125 01/15/19 Govt & 2.125 & 121.945313 & 121.703125  & 1/15/19 & 6   & 1/15/09 & 214.69971 & 230.82203 & 1.0750924 \\
	      		TII 1.875 07/15/19 Govt & 1.875 & 122.164063 & 121.9140625 & 7/15/19 & 6.5 & 7/15/09 & 213.51819 & 230.82203 & 1.0801415 \\
	      		TII 1.375 01/15/20 Govt & 1.375 & 118.890625 & 118.6953125 & 1/15/20 & 7   & 1/15/10 & 216.12461 & 230.82203 & 1.0674044 \\
	      		TII 1.25 07/15/20 Govt  & 1.25  & 118.960938 & 118.7578125 & 7/15/20 & 7.5 & 7/15/10 & 218.08532 & 230.82203 & 1.0584024 \\
	      		TII 1.125 01/15/21 Govt & 1.125 & 117.648438 & 117.4375    & 1/15/21 & 8   & 1/15/11 & 218.75255 & 230.82203 & 1.0551741 \\
	      		TII 0.625 07/15/21 Govt & 0.625 & 113.835938 & 113.6484375 & 7/15/21 & 8.5 & 7/15/11 & 225.38381 & 230.82203 & 1.0241278 \\
	      		TII 0.125 01/15/22 Govt & 0.125 & 108.664063 & 108.484375  & 1/15/22 & 9   & 1/15/12 & 226.33474 & 230.82203 & 1.0198237 \\
	      		TII 0.125 07/15/22 Govt & 0.125 & 108.617188 & 108.4140625 & 7/15/22 & 9.5 & 7/15/12 & 229.96306 & 230.82203 & 1.0037353 \\
	      		TII 2.375 01/15/25 Govt & 2.375 & 134.84375  & 134.3671875 & 1/15/25 & 12  & 1/15/13 & 198.47742 & 230.82203 & 1.1629637 \\
	      		TII 2 01/15/26 Govt     & 2     & 131.024338 & 130.5234375 & 1/15/26 & 13  & 1/15/06 & 198.47742 & 230.82203 & 1.1629637 \\
	      		TII 2.375 01/15/27 Govt & 2.375 & 137.507813 & 137.1015625 & 1/15/27 & 14  & 1/15/07 & 201.66452 & 230.82203 & 1.1445482 \\
	      		TII 1.75 01/15/28 Govt  & 1.75  & 129.046875 & 128.6953125 & 1/15/28 & 15  & 1/15/08 & 209.49645 & 230.82203 & 1.1017945 \\
	      		TII 2.5 01/15/29 Govt   & 2.5   & 141.96875  & 141.53125   & 1/15/29 & 16  & 1/15/09 & 214.69971 & 230.82203 & 1.0750924 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Treasury Inflation Protected Securities}
	      	\label{tab:tips}
	      \end{table}
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|c|}
	      		\hline
	      		\textbf{Coupon} & \textbf{Ask} & \textbf{Bid} & \textbf{Maturity} & \textbf{Price} & \textbf{Y} & \textbf{Z} & \textbf{Fitted} & \textbf{Sum Sqr} \\
	      		\hline
	      		1.875           & 101.95       & 101.91       & 0.50              & 101.93         & (0.0121)   & 1.0060     & 101.55          & 0.1428           \\
	      		2.000           & 103.55       & 103.42       & 1.00              & 103.48         & (0.0148)   & 1.0149     & 103.51          & 0.0006           \\
	      		2.000           & 105.95       & 105.83       & 1.50              & 105.89         & (0.0165)   & 1.0251     & 105.55          & 0.1146           \\
	      		1.625           & 106.72       & 106.65       & 2.00              & 106.68         & (0.0175)   & 1.0356     & 106.88          & 0.0378           \\
	      		1.875           & 109.63       & 109.48       & 2.50              & 109.55         & (0.0179)   & 1.0458     & 109.39          & 0.0254           \\
	      		2.000           & 111.32       & 111.19       & 3.00              & 111.25         & (0.0179)   & 1.0553     & 111.71          & 0.2081           \\
	      		2.500           & 115.41       & 115.29       & 3.50              & 115.35         & (0.0176)   & 1.0636     & 115.42          & 0.0045           \\
	      		2.375           & 116.59       & 116.47       & 4.00              & 116.53         & (0.0171)   & 1.0707     & 116.94          & 0.1703           \\
	      		2.625           & 120.29       & 120.11       & 4.50              & 120.20         & (0.0164)   & 1.0764     & 119.97          & 0.0530           \\
	      		1.625           & 116.39       & 116.20       & 5.00              & 116.30         & (0.0155)   & 1.0808     & 116.59          & 0.0849           \\
	      		1.375           & 116.88       & 116.70       & 5.50              & 116.79         & (0.0146)   & 1.0839     & 116.33          & 0.2132           \\
	      		2.125           & 121.95       & 121.70       & 6.00              & 121.82         & (0.0137)   & 1.0857     & 122.00          & 0.0319           \\
	      		1.875           & 122.16       & 121.91       & 6.50              & 122.04         & (0.0127)   & 1.0864     & 121.51          & 0.2799           \\
	      		1.375           & 118.89       & 118.70       & 7.00              & 118.79         & (0.0118)   & 1.0860     & 118.79          & 0.0000           \\
	      		1.250           & 118.96       & 118.76       & 7.50              & 118.86         & (0.0108)   & 1.0848     & 118.41          & 0.1992           \\
	      		1.125           & 117.65       & 117.44       & 8.00              & 117.54         & (0.0099)   & 1.0826     & 117.82          & 0.0751           \\
	      		0.625           & 113.84       & 113.65       & 8.50              & 113.75         & (0.0090)   & 1.0798     & 113.62          & 0.0139           \\
	      		0.125           & 108.66       & 108.48       & 9.00              & 108.57         & (0.0079)   & 1.0723     & 108.49          & 0.0645           \\
	      		0.125           & 108.62       & 108.41       & 9.50              & 108.52         & (0.0073)   & 1.0723     & 108.49          & 0.0054           \\
	      		2.375           & 134.84       & 134.37       & 12.00             & 134.61         & (0.0038)   & 1.0464     & 134.92          & 0.0995           \\
	      		2.000           & 131.02       & 130.52       & 13.00             & 130.77         & (0.0026)   & 1.0444     & 131.01          & 0.0532           \\
	      		2.375           & 137.51       & 137.10       & 14.00             & 137.30         & (0.0020)   & 1.0464     & 137.36          & 0.0032           \\
	      		1.750           & 129.05       & 128.70       & 15.00             & 128.87         & (0.0006)   & 1.0090     & 128.59          & 0.0789           \\
	      		2.500           & 141.97       & 141.53       & 16.00             & 141.75         & 0.0003     & 0.9960     & 141.66          & 0.0076           \\
	      		\hline
	      	\end{tabular}
	      	\caption{Prices,  Durations,  Convexities}
	      	\label{tab:prices_durations_convexities}
	      \end{table}
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|c|c|c|}
	      		\hline
	      		\textbf{NS Parameters} & \textbf{TIPS} & \textbf{Treasuries} \\
	      		\hline
	      		theta0                 & 0.013771363   & 0.039532917         \\
	      		theta1                 & -0.02188646   & -0.02618547         \\
	      		theta2                 & -0.06751297   & -0.073916933        \\
	      		la                     & 2.440119514   & 2.00933176          \\
	      		\hline
	      	\end{tabular}
	      	\caption{Nelson-Siegel Parameters for TIPS and Treasuries}
	      	\label{tab:ns_parameters}
	      \end{table}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-1.png}
	      	\caption{Fitting of the NS Model to TIPS Data}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-2.png}
	      	\caption{Real Discount Factor}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-3.png}
	      	\caption{Real Yield}
	      \end{figure}
	      
	\item (CP): Fit the Nelson Siegel model to the nominal bonds. Plot the resulting term structure of nominal rates. Interpret in light of your answer to point 3.\\
	      \textbf{Solution:}We next fit the nominal yields using the NS model to the data. In this case,  there are many more data points than in the case of real bonds,  but the model does a good job in fitting the data,  as shown in Figure 4.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-4.png}
	      	\caption{Fitting of the NS Model to Nominal Bond Data}
	      \end{figure}
	      
	      $$
	      r_{nominal}(t) = \theta_{0} + \theta_{1} \left( \frac{1 - e^{-\lambda t}}{\lambda t} \right) + \theta_{2} \left( \frac{1 - e^{-\lambda t}}{\lambda t} - e^{-\lambda t} \right)
	      $$
	      Given the values:
	      •	$\theta_{0} = 0.0395$\\
	      •	$\theta_{1} = -0.0262$\\
	      •	$\theta_{2} = -0.0739$\\
	      •	$\lambda = 2.093$\\
	      
	      We can plug these values into the Nelson-Siegel function:
	      
	      $$
	      r_{nominal}(t) = 0.0395 - 0.0262 \left( \frac{1 - e^{-2.093 t}}{2.093 t} \right) - 0.0739 \left( \frac{1 - e^{-2.093 t}}{2.093 t} - e^{-2.093 t} \right)
	      $$
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-5.png}
	      	\caption{Nominal Discount Factor}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-6.png}
	      	\caption{Nominal Yield and Forward Curve}
	      \end{figure}
	      
	\item Question 6: Compute breakeven inflation rate,  that is,  those rate $\omega(\epsilon)$ such that $r_{\text{nominal}}(0,  \epsilon) = r_{\text{real}}(0,  \epsilon) + \omega(\epsilon)$. Interpret your results. What does the break-even rate really capture?
	      
	      \textbf{Solution:} We finally use the nominal yields and the real yield to compute “breakeven inflation rates”,  that is,  the difference between the nominal and the real yield. These are shown in Figure 7. The breakeven rate ranges between 2\% and 2.7\%. These implied forecasts of inflation rates seem reasonable,  although we should always remember that the difference between nominal and real yields also includes risk premia. Breakeven rates depend on risk premia,  as explained above. Interestingly,  from the survey of professional forecasters,  we find that the median forecast of average CPI inflation for the next 10 years is 2.3\%,  a bit lower than the breakeven inflation rate at the 10-year mark,  which is around 2.67\%. The difference could be due to a positive risk premium RP,  as discussed above. Indeed,  we have
	      $$
	      \text{RP} = 2.67\% - 2.4\% + \frac{1}{2}\sigma^2_\pi = 0.27\% + \frac{1}{2}\sigma^2_\pi
	      $$
	      This positive risk premium is in contrast with the negative risk premium obtained above using the forecasts of future short-term rates.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-7.png}
	      	\caption{Break Even Rate}
	      \end{figure}
	      
	      \section*{Part II: Swap Spread Trades}
	      
	\item Question 1: Look at the data and decide which direction to set up a swap spread trade. Is there an arbitrage? If so,  why do you think there is one? Discuss.
	      
	      \textbf{Solution:} LIBOR(0) = 1.25\%,  Repo(0) = 0.30\%,  Thirty-year Swap Rate = 3.21\% while the price and coupon of a thirty-year note were $P(0,  30) = 100.36$ and $c = 3.50\%$,  respectively. The (semi-annually) compounded yield to maturity of the 30-year note $y$ is obtained from the formula
	      $$
	      100.36 = \frac{c}{2} \sum_{j=1}^{60} \frac{1}{(1 + \frac{y}{2})^j} + \frac{1}{(1 + \frac{y}{2})^{60}}
	      $$
	      Computation gives $y = 3.49\%$,  very close to the constant maturity rate for the same maturity,  which was $\text{CMT} = 3.47\%$. We can define the swap spread in various ways,  but it is essentially the difference in coupon from a swap and the YTM on the Treasury. (Here,  this is almost the exact same as using the coupon of the treasury instead. This is because the bond is trading near par.) Thus $\text{SS} = 3.21\% - 3.49\% = -28$ basis points. Additionally,  the LIBOR-repo spread,  or LRS,  is $1.25 - 0.30 = 0.95\%$. In the past,  we typically observed a fixed rate on the swap that is larger than the treasury. In this case,  the issue was whether the excess was large enough to make up for the loss on the LRS given that the trade involves receiving repo and paying LIBOR. (For instance,  see Figure 8 for a feel of how the trade worked.) However,  in this situation,  a trader can make money on both ends of the deal by doing the opposite. Namely, 
	      
	      \begin{itemize}
	      	\item[(a)] Go long the 30-year bond through a repo transaction. In cash flow terms,  pay Repo and receive the treasury coupon.
	      	\item[(b)] Enter into a fixed for floating swap in which I receive [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and pay the fixed.
	      \end{itemize}
	      
	      The net quarterly cash flows are
	      $$
	      CF(T_i) = 0.25 \times [\text{Coupon} - \text{Repo}(T_{i-1})] + 0.25 \times [\text{LIBOR}(T_{i-1}) - \text{Swap Rate}]
	      $$
	      where notice that we consider an “accrued” coupon to be “paid” at quarterly frequency,  for simplicity.
	      
	      More precisely,  consider a trade of size \$100 million. The number of T-Notes (with 100 principal) corresponding to \$100 million is $N = 9, 964, 191$. Therefore,  adjusting for the size of the trade,  and assuming no haircut,  the cash flow at time $T_i$ is
	      $$
	      CF(T_i) = 0.25 \times [N \times \text{coupon} - 100 \text{mil} \times \text{Swap Rate}] + 100 \text{mil} \times 0.25 \times [\text{LIBOR}(T_{i-1}) - \text{Repo}(T_{i-1})]
	      $$
	      
	\item Question 2: What do you do? Describe the working of the swap spread trade. How do you take positions in the Treasury Bond? What about the swap?
	      
	      \textbf{Solution:} Use the above cash flow equation to get that the first cash-flow realized is $CF (\text{May}) \approx \$305, 774.23$ (for an annualized value of \$1, 223, 096.92 if rates were to hold constant).
	      
	      The first term in $CF(T_i)$ above is always the same each quarter,  as neither the swap rate nor the coupon of the initial swap and T-note change over time. The second parenthesis is instead reset every 3 months. Still,  the trade would be profitable unless [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] dropped to where it was below the repo rate,  which is quite unlikely given the lower risk of collateralized debt. Thus,  the trade locks in the less stable profit,  the SS,  and profits on the stable fact that [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is above repo. See Figure 8 for the historical relationship using 5-year swaps and 5-year coupon bonds.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-8.png}
	      	\caption{5-year Swap Spread and Funding Spread Over Time}
	      \end{figure}
	      
	\item (CP): Consider now one quarter after the initiation of the trade (May 18,  2009). Suppose JCH Capital Management needs to liquidate the position immediately,  due to large unexpected redemptions from investors. What is the value of the swap-spread trade positions?
	      
	      \textbf{Solution:} Figure 9 uses daily data to illustrate the evolution of the LRS side of the trade over the following quarters (for this solution,  the data have been updated to June 2010,  for illustrative purposes). The spread drops substantially—almost half—but is still well above zero. Combined with the locked-in profit on the SS side,  the trade is still generating positive cash-flow.
	      
	      Given the data provided,  we only have one quarter of data after the position is put on,  so it would seem that we can only calculate one cash flow generated by the trade. However,  we can actually compute the cash flow for August using the data given in May. The SS cash flow is fixed,  and the August LRS cash flow depends on [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the repo rate quoted one quarter earlier—the floating part resets one quarter before payment. With updated data to June 2010,  we can follow the cash flows all the way to August 2010. Figure 10 displays the cash flows of the trade,  and Figure 11 displays the net cash flows.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{LIBOR_and_Repo_Rates.png}
	      	\caption{[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and Repo Rates}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{LIBOR-Repo_Spread.png}
	      	\caption{LIBOR-Repo Spread}
	      \end{figure}
	      
	      % General Information Table
	      \begin{table}[H]
	      	\tiny
	      	\centering
	      	\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|}
	      		\hline
	      		\textbf{crspid} & \textbf{qdate} & \textbf{matdt} & \textbf{couprt} & \textbf{bid} & \textbf{ask} & \textbf{\shortstack{Time to &        &         &      \\ Maturity}} & \textbf{\shortstack{Acc.\\ Interest}} & \textbf{\shortstack{3M\\ LIBOR}} & \textbf{\shortstack{3M\\ REPO}} \\
	      		\hline
	      		
	      		20390215.1035   & 20090217       & 20390215       & 3.5             & 100.328125   & 100.390625   & 29.9944                     & 0.019  & 1.24563 & 0.3  \\
	      		20390215.1035   & 20090518       & 20390215       & 3.5             & 88.3125      & 88.34375     & 29.7417                     & 0.8892 & 0.785   & 0.15 \\
	      		20390215.1035   & 20090817       & 20390215       & 3.5             & 86.453125    & 86.515625    & 29.4944                     & 0      & 0.43125 & 0.15 \\
	      		20390215.1035   & 20091118       & 20390215       & 3.5             & 86.578125    & 86.640625    & 29.2417                     & 0.8845 & 0.26906 & 0.06 \\
	      		20390215.1035   & 20100223       & 20390215       & 3.5             & 81.96875     & 82.015625    & 28.9778                     & 0.058  & 0.25194 & 0.06 \\
	      		20390215.1035   & 20100519       & 20390215       & 3.5             & 89.84375     & 89.921875    & 29.7194                     & 0.9475 & 0.53781 & 0.17 \\
	      		\hline
	      	\end{tabular}
	      \end{table}
	      
	      % Swap Rates Table
	      \begin{table}[H]
	      	\tiny
	      	\centering
	      	\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|c|}
	      		\hline
	      		\textbf{crspid} & \textbf{qdate} & \textbf{matdt} & \textbf{\shortstack{1Y &      &      &      &      &      &      &      \\ SWAP}} & \textbf{\shortstack{2Y\\ SWAP}} & \textbf{\shortstack{3Y\\ SWAP}} & \textbf{\shortstack{4Y\\ SWAP}} & \textbf{\shortstack{5Y\\ SWAP}} & \textbf{\shortstack{7Y\\ SWAP}} & \textbf{\shortstack{10Y\\ SWAP}} & \textbf{\shortstack{30Y\\ SWAP}} \\
	      		\hline
	      		20390215.1035   & 20090217       & 20390215       & 1.36                   & 1.6  & 1.93 & 2.21 & 2.43 & 2.73 & 2.97 & 3.21 \\
	      		20390215.1035   & 20090518       & 20390215       & 0.85                   & 1.25 & 1.74 & 2.14 & 2.44 & 2.88 & 3.22 & 3.68 \\
	      		20390215.1035   & 20090817       & 20390215       & 0.73                   & 1.42 & 2.02 & 2.47 & 2.81 & 3.3  & 3.7  & 4.17 \\
	      		20390215.1035   & 20091118       & 20390215       & 0.45                   & 1.05 & 1.63 & 2.1  & 2.47 & 3    & 3.45 & 4.15 \\
	      		20390215.1035   & 20100223       & 20390215       & 0.5                    & 1.12 & 1.74 & 2.27 & 2.71 & 3.32 & 3.83 & 4.54 \\
	      		20390215.1035   & 20100519       & 20390215       & 0.92                   & 1.27 & 1.68 & 2.07 & 2.4  & 2.9  & 3.32 & 3.95 \\
	      		\hline
	      	\end{tabular}
	      \end{table}
	      
	      % Treasury Rates Table
	      \begin{table}[H]
	      	\tiny
	      	\centering
	      	\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
	      		\hline
	      		\textbf{crspid} & \textbf{qdate} & \textbf{matdt} & \textbf{\shortstack{1M &      &      &      &      &      &      &      &      &      &      \\ TCM}} & \textbf{\shortstack{3M\\ TCM}} & \textbf{\shortstack{6M\\ TCM}} & \textbf{\shortstack{1Y\\ TCM}} & \textbf{\shortstack{2Y\\ TCM}} & \textbf{\shortstack{3Y\\ TCM}} & \textbf{\shortstack{5Y\\ TCM}} & \textbf{\shortstack{7Y\\ TCM}} & \textbf{\shortstack{10Y\\ TCM}} & \textbf{\shortstack{20Y\\ TCM}} & \textbf{\shortstack{30Y\\ TCM}} \\
	      		\hline
	      		20390215.1035   & 20090217       & 20390215       & 0.26                   & 0.32 & 0.48 & 0.61 & 0.87 & 1.22 & 1.65 & 2.05 & 2.64 & 3.7  & 3.47 \\
	      		20390215.1035   & 20090518       & 20390215       & 0.12                   & 0.19 & 0.3  & 0.5  & 0.93 & 1.36 & 2.09 & 2.73 & 3.22 & 4.16 & 4.18 \\
	      		20390215.1035   & 20090817       & 20390215       & 0.11                   & 0.18 & 0.27 & 0.45 & 1.04 & 1.54 & 2.43 & 3.09 & 3.48 & 4.26 & 4.33 \\
	      		20390215.1035   & 20091118       & 20390215       & 0.04                   & 0.04 & 0.15 & 0.29 & 0.77 & 1.27 & 2.21 & 2.9  & 3.56 & 4.29 & 4.29 \\
	      		20390215.1035   & 20100223       & 20390215       & 0.08                   & 0.12 & 0.2  & 0.36 & 0.87 & 1.42 & 2.37 & 3.13 & 3.69 & 4.49 & 4.63 \\
	      		20390215.1035   & 20100526       & 20390215       & 0.16                   & 0.17 & 0.23 & 0.37 & 0.82 & 1.28 & 2.06 & 2.68 & 3.21 & 3.94 & 4.11 \\
	      		\hline
	      	\end{tabular}
	      \end{table}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{Zero_Curve_from_Interpolated_Swap_Rates.png}
	      	\caption{Zero Curve from Interpolated Swap Rates}
	      \end{figure}
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{Interpolated_Swap_Curve.png}
	      	\caption{Interpolated Swap Curve}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.6\textwidth]{hw4-13.png}
	      	\caption{Cash Flows of the Trade}
	      \end{figure}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.6\textwidth]{hw4-12.png}
	      	\caption{Net Cash Flows of the Trade}
	      \end{figure}
	      
	\item (CP): Given your results in [A] and [B],  did the trade (so far) make money or lose money? Can you reconcile it with your answer to point 1? What happened to the swap spread between Feb 9 and May 18,  2009?
	      
	      \textbf{Solution:} From the strategy above,  we are long $N$ T-notes,  short \$100 million in the Repo market,  and short a fixed for floating swap. The computation of the value of the long T-note (minus Repo) is straightforward. Assuming we take the repo interest paid over time,  the value of this position at reset dates is
	      $$
	      V_{\text{T-Note}} = N \times P(t;T) - 100 \text{mil}
	      $$
	      where $P(t;T)$ is the value of the 30-year note.
	      
	      To value the swap is slightly more cumbersome,  as we need to compute the value of the swap as the swap rate changes over time. Recall that the value of the swap at the reset date is
	      $$
	      V_{\text{Swap}} = P_{\text{Fixed}}(0;T) - P_{\text{Fl}}(0;T)
	      $$
	      where $P_{\text{Fixed}}(0;T)$ is the value of the fixed rate bond implicit in the fixed part of the swap. In particular,  the coupon on this component equals the swap rate at initiation,  namely,  $c_{\text{swap}} = 3.21\%$. Therefore,  at every reset date $T_i$,  let $n_i$ be the number of remaining payments in the swap. We have
	      $$P_{\text{Fixed}}(T_i;T) = \frac{c_{\text{swap}}}{4} \sum_{j=1}^{n_i} Z_{\text{LIBOR}}(T_i;T_j) + Z_{\text{LIBOR}}(T_i;T_{n_i})$$
	      If we knew the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve $Z_{\text{LIBOR}}(T_i;T_j)$,  we are done. We can use current swap rates to compute the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve every $T_i$. Since we only have a sample of swap rates in the data set,  we need to interpolate to a quarterly frequency. After having interpolated,  at every $T_i$ we have a set of swap rates $c_{\text{swap}}(T_i;T_j)$ for maturity $T_j$,  $j = i+1,  i+2,  \ldots$. From the swap rates,  we can finally obtain the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve from the following bootstrap procedure
	      $$Z_{\text{LIBOR}}(T_i;T_{i+1}) = \frac{1}{1 + \text{LIBOR}(T_i) \times 0.25}$$
	      $$
	      Z_{\text{LIBOR}}(T_i;T_j) = \frac{1 - 0.25 \times c(T_i;T_j) \sum_{k=1}^{j-1} Z_{\text{LIBOR}}(T_i;T_{i+k})}{1 + c(T_i;T_j) \times 0.25}
	      $$
	      
	      From the swap curve,  we can compute the value of the fixed leg of the swap.
	      
	      The floating leg of the swap is much simpler,  as $P_{\text{Fl}}(0;T) = 1$. The value of the swap follows.
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-11.png}
	      	\caption{Value of Short Swap and Repo}
	      \end{figure}
	      
	      Figure 32 plots the value of the swap and the Treasury (minus Repo) over time. Both start at zero by construction,  and as rates change,  so do the value of both quantities. In particular,  the price of the T-note decreased,  and so did the treasury coupon minus repo position. This was partly offset by the increase in value in the swap trade. However,  Figure 33 shows that the T-note price dropped by more than the increase in the swap value,  generating a drop in the value of the overall position. Thus,  while the cash flows are positive,  there is a capital loss if the position is unwound after a quarter. Still,  the capital loss due to moving rates is small relative to the positive cash flows.
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|l|l|}
	      		\hline
	      		\textbf{Parameter}       & \textbf{Value} \\
	      		\hline
	      		Date - Initial           & 20090217       \\
	      		Issue Date               & 2/17/09        \\
	      		Maturity                 & 2/17/14        \\
	      		\hline
	      		[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]]                    & 1.25           \\
	      		Repo                     & 0.30           \\
	      		Thirty-year Swap Rate    & 3.21           \\
	      		\hline
	      		\textbf{Five year note}  &                \\
	      		Price                    & 100.36         \\
	      		Accrued Interest         & 0.02           \\
	      		Coupon                   & 3.50           \\
	      		YTM                      & 3.49           \\
	      		\hline
	      		Swap Spread (SS)         & (0.28)         \\
	      		Libor-Repo Spread (LRS)  & 0.95           \\
	      		Swap Spread minus Carry  & (1.2231)       \\
	      		\hline
	      		Position                 & 100, 000, 000    \\
	      		T-Note position          & 996, 231        \\
	      		\hline
	      		\textbf{First Cash Flow} &                \\
	      		SS Cash Flow             & 69, 202         \\
	      		LRS Cash Flow            & 236, 408        \\
	      		Total                    & 305, 609        \\
	      		\hline
	      	\end{tabular}
	      	\caption{Position Value on February 17th,  2009}
	      	\label{tab:initial_data}
	      \end{table}
	      
	      \begin{table}[H]
	      	\centering
	      	\begin{tabular}{|l|l|}
	      		\hline
	      		\textbf{Parameter}        & \textbf{Value} \\
	      		\hline
	      		Date - One Quarter Later  & 20090518       \\
	      		\hline
	      		\textbf{Thirty Year Note} &                \\
	      		Price                     & 88.33          \\
	      		Accrued Interest          & 0.8892         \\
	      		Value                     & 88, 881, 021     \\
	      		\hline
	      		TNote-Repo Value          & (11, 118, 979)   \\
	      		Swap Value                & 8, 636, 298      \\
	      		Trade Value               & (2, 482, 680)    \\
	      		\hline
	      	\end{tabular}
	      	\caption{Position Value on May 18th,  2009}
	      	\label{tab:quarterly_data}
	      \end{table}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw4-10.png}
	      	\caption{Total Value of Short Swap Spread Position}
	      \end{figure}
	      
	\item (PP): It is important to consider whether the above trade is an arbitrage opportunity. Discuss the factors that might influence the determination of whether this trade is arbitrage or not.
	      
	      \textbf{Solution:} It is important to consider whether the above trade is an arbitrage opportunity. As mentioned earlier,  the cash flows are comprised of two parts,  the SS and LRS. The former is fixed every period,  and we showed that by taking the short end it will be a positive inflow. The LRS varies with changes in [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the repo,  but we strongly expect [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] to always be larger as securitized loans (the repo) are less risky. Thus,  while the amount gained from the LRS varies it is incredibly unlikely it will become negative,  especially so negative as to outweigh the positive flow from the SS position. Thus,  by holding the position to maturity one realizes positive cash flows for 30 years and does not need to worry about possible losses from unwinding early.
	      
	      In this view,  the above trade is an arbitrage. However,  this conclusion hinges on the ability to hold the position to maturity. Unwinding the position early could induce significant losses,  as demonstrated above in Figure 13,  due to the fact that the value of the position fluctuates up until maturity where it is known. In fact,  the fluctuating value of the position exposes the trade to margin calls. While the value is fixed at $T = 30$,  in the meantime,  the value could plummet to the point where the margin calls are significant. Thus,  the trade is exposed to funding risk. It is likely that this funding risk is what kept traders from exploiting the apparent arbitrage in February. Given the financial turmoil,  few were willing to deal with the potential margin calls and possible short-term losses even though they were assured profits in the long run.
	      
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{|c|c|c|c|c|c|c|}
	      		\hline
	      		\textbf{Date - Initial} & \textbf{20090217} & \textbf{20090518} & \textbf{20090817} & \textbf{20091118} & \textbf{20100223} & \textbf{20100526} \\
	      		\hline
	      		Issue Date              & 2/17/09           & 5/18/09           & 8/17/09           & 11/18/09          & 2/23/10           & 5/26/10           \\
	      		Maturity                & 2/17/14           & 5/18/14           & 8/17/14           & 11/18/14          & 2/23/15           & 5/26/15           \\
	      		\hline
	      		[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]]                   & 1.25              & 0.79              & 0.43              & 0.27              & 0.25              & 0.54              \\
	      		Repo                    & 0.30              & 0.15              & 0.15              & 0.06              & 0.06              & 0.07              \\
	      		Thirty-year Swap Rate   & 2.97              & 3.22              & 3.70              & 3.45              & 3.83              & 3.32              \\
	      		\hline
	      		\multicolumn{7}{|c|}{Five year note} \\
	      		\hline
	      		Price                   & 100.36            & 88.33             & 86.48             & 86.61             & 81.99             & 89.88             \\
	      		Accrued Interest        & 0.02              & 0.89              & -                 & 0.88              & 0.06              & 0.95              \\
	      		Coupon                  & 3.50              & 3.50              & 3.50              & 3.50              & 3.50              & 3.50              \\
	      		YTM                     & 3.49              & 3.96              & 4.05              & 4.04              & 4.27              & 3.89              \\
	      		\hline
	      		Swap Spread (SS)        & (0.52)            & (0.74)            & (0.35)            & (0.59)            & (0.44)            & (0.57)            \\
	      		Libor-Repo Spread (LRS) & 0.95              & 0.64              & 0.28              & 0.21              & 0.19              & 0.47              \\
	      		Swap Spread minus Carry & (1.4631)          & (1.3777)          & (0.6284)          & (0.8004)          & (0.6309)          & (0.9491)          \\
	      		Position                & 100, 000, 000       & 100, 000, 000       & 100, 000, 000       & 100, 000, 000       & 100, 000, 000       & 100, 000, 000       \\
	      		T-Note position         & 996, 231           & 1, 120, 859         & 1, 156, 278         & 1, 142, 937         & 1, 218, 766         & 1, 100, 954         \\
	      		\hline
	      		\multicolumn{7}{|c|}{First Cash Flow} \\
	      		\hline
	      		SS Cash Flow            & 129, 202           & 175, 751           & 86, 743            & 137, 570           & 108, 920           & 133, 335           \\
	      		LRS Cash Flow           & 236, 408           & 158, 750           & 70, 313            & 52, 265            & 47, 985            & 91, 953            \\
	      		Total                   & 365, 609           & 334, 501           & 157, 056           & 189, 835           & 156, 905           & 225, 287           \\
	      		\hline
	      		\multicolumn{7}{|c|}{Date - One Quarter Later} \\
	      		\hline
	      		\textbf{20090518}       & \textbf{20090817} & \textbf{20091118} & \textbf{20100223} & \textbf{20100526} & \textbf{20100630} &                   \\
	      		\hline
	      		Thirty Year Note        &                   &                   &                   &                   &                   &                   \\
	      		\hline
	      		Price                   & 88.33             & 86.48             & 86.61             & 81.99             & 89.88             & 93.16             \\
	      		Accrued Interest        & 0.8892            & 0.8845            & 0.0580            & 0.9475            & 1.2859            & -                 \\
	      		Value                   & 88, 881, 021        & 96, 936, 750        & 101, 167, 263       & 93, 778, 207        & 110, 700, 920       & 103, 976, 467       \\
	      		TNote-Repo Value        & (11, 118, 979)      & (3, 063, 250)       & 1, 167, 263         & (6, 221, 793)       & 10, 700, 920        & 3, 976, 467         \\
	      		Swap Value              & 13, 035, 087        & 8, 453, 017         & (344, 481)         & 4, 237, 549         & (2, 727, 136)       & 6, 620, 205         \\
	      		Trade Value             & 1, 916, 069         & 5, 389, 767         & 822, 782           & (1, 984, 243)       & 7, 973, 784         & 10, 596, 672        \\
	      		\hline
	      	\end{tabular}
	      	\caption{Data Table}
	      	\label{tab:data_table}
	      \end{table}
```

## HW 5

```latex
\maketitle

\section*{Homework 5}
\textbf{Due at the beginning of Class 6}

\begin{quote}
	\textbf{Note:} As with past homework assignments,  there are “guides” for doing the homework in Excel,  Matlab,  and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.
\end{quote}

\section*{Part I: Using Black’s Formula for Caps,  Floors,  and Swaptions}

\subsection*{Questions}

\begin{enumerate}
	\item[(CP)] Attached are two data screens from Bloomberg. Figure ?? quotes out to 30 years. In using this data use the mid-point quotes. The second,  figure ??,  provides data on implied flat Black forward-volatility for Caps and Floors and implied Black volatility for Swaptions. This screen also provides the 1-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate needed for the exercise. (There may be some slight inconsistency in the quotes in the figures because they were not extracted from Bloomberg at exactly the same time.) Compute:
	      \begin{itemize}
	      	\item The dollar value of a two-year Cap (quoted caps are at-the-money,  and therefore the strike rate equals the current swap rate). The only thing you need to enter in the code is the proper volatility and swap rates (along with 3-month LIBOR) to produce this price and the swaption price below.
	      	\item The dollar value of a 1-year swaption to enter into a 5-year swap.
	      	            
	      	            
	      	         
	      \end{itemize}
	\item[(PP)] In the exercise above,  make sure to illustrate the option-pricing formulas used for (a) the first caplet in the cap (i.e.,  the one with 6-months to maturity); and (b) the swaption. Show your work. (Look at the code and match it to the notation from the class notes).
\end{enumerate}
\begin{itemize}
	\item The dollar value of a two-year Cap:
	          
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{cccccc}
	      		\hline
	      		i  & $T_i$ & Interpolate & $Z(0,  T_i)$ & Fwd Discount & Rate Discount \\
	      		\hline
	      		1  & 0.25  & 0.003212    & 0.99920     &              &               \\
	      		2  & 0.50  & 0.003428    & 0.99829     & 0.99909      & 0.00364       \\
	      		3  & 0.75  & 0.003569    & 0.99733     & 0.99904      & 0.00385       \\
	      		4  & 1.00  & 0.003620    & 0.99639     & 0.99906      & 0.00377       \\
	      		5  & 1.25  & 0.003558    & 0.99556     & 0.99917      & 0.00331       \\
	      		6  & 1.50  & 0.003422    & 0.99488     & 0.99932      & 0.00274       \\
	      		7  & 1.75  & 0.003285    & 0.99427     & 0.99939      & 0.00246       \\
	      		8  & 2.0   & 0.003220    & 0.99358     & 0.99931      & 0.00276       \\
	      		9  & 2.25  & 0.003216    & 0.99279     & 0.99921      & 0.00318       \\
	      		10 & 2.50  & 0.003213    & 0.99201     & 0.99920      & 0.00318       \\
	      		11 & 2.75  & 0.003211    & 0.99121     & 0.99920      & 0.00319       \\
	      		12 & 3.00  & 0.003210    & 0.99042     & 0.99920      & 0.00320       \\
	      		13 & 3.25  & 0.003246    & 0.98951     & 0.99908      & 0.00369       \\
	      		14 & 3.50  & 0.003337    & 0.98839     & 0.99887      & 0.00452       \\
	      		15 & 3.75  & 0.003454    & 0.98713     & 0.99873      & 0.00511       \\
	      		16 & 4.00  & 0.003570    & 0.98582     & 0.99867      & 0.00532       \\
	      		17 & 4.25  & 0.003685    & 0.98446     & 0.99862      & 0.00554       \\
	      		18 & 4.50  & 0.003813    & 0.98298     & 0.99850      & 0.00601       \\
	      		19 & 4.75  & 0.003947    & 0.98141     & 0.99841      & 0.00639       \\
	      		20 & 5.0   & 0.004080    & 0.97979     & 0.99834      & 0.00664       \\
	      		21 & 5.25  & 0.004211    & 0.97811     & 0.99829      & 0.00686       \\
	      		22 & 5.50  & 0.004342    & 0.97637     & 0.99822      & 0.00715       \\
	      		23 & 5.75  & 0.004476    & 0.97455     & 0.99814      & 0.00745       \\
	      		24 & 6.00  & 0.004610    & 0.97267     & 0.99807      & 0.00775       \\
	      		\hline
	      	\end{tabular}
	      	\caption{Caplet and Swaption Calculations}
	      \end{table}
	      
	      \textbf{Solution:} We first interpolate the available Swap data to fill in the curve for the quarterly maturities. The zero yield on the Zero with maturity of 0.25 is given by the first interpolated swap rate:
	      \[
	      	Z(0,  0.25) = \frac{1}{1 + c(0.25) \times 0.25}
	      \]
	      Beyond that date we use the Bootstrap method:
	      \[
	      	Z(0.5) = \frac{1 - c(0.5) \times 0.25 \times Z(0.25)}{1 + c(0.5) \times 0.25}
	      \]
	      \[
	      	\vdots \quad \vdots
	      \]
	      \[
	      	Z(T) = \frac{1 - c(T) \Delta \sum_{t=0.25}^{T-0.25} Z(t)}{1 + c(T) \Delta}
	      \]
	      
	      Clearly,  there are important issues here
	      \begin{itemize}
	      	\item The interpolation is only approximate. We normally have far more data to do this.
	      	\item We have anchored the swap curve with the one-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve. [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is for uncollateralized borrowing -- and thus is risky -- while swaps now are fully collateralized,  and thus there is less risk.
	      \end{itemize}
	      
	      Once we have the zero-coupon curve,  we can compute quarterly forward rates from the forward discount
	      \[
	      	F(0,  T_i,  T_{i+1}) = \frac{Z(0,  T_i)}{Z(0,  T_{i+1})}
	      \]
	      
	      From the forward rates,  we employ the formula in the teaching notes to compute the caplets. The following table shows the results for the interpolations the 1st and 2nd caplet and the swaption,  and then the next table shows the results for the caplets:
	      
	      
	      
	      \begin{enumerate}
	      	\item[5.] The swaption uses a similar strategy. We have to compute the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve up to year 5 in order to compute the discounts $Z(0,  T_i)$,  as described in the previous point.
	      	          
	      	\item[6.] From the teaching notes,  we have to compute the quantity
	      	      \[
	      	      	A = \Delta \sum_{i=5}^{24} Z(0,  T_i)
	      	      \]
	      	      and then use Black's formula as in the teaching notes. The next table shows the calculations:
	      \end{enumerate}
	      
	      
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{cccccc}
	      		\hline
	      		Cap        & Strike Rate & Volatility & $T_i$ & $f(T_{i-1},  T_i)$ & Caplet Value (x 100) \\
	      		\hline
	      		1-year Cap & 0.00362     & 1.0679     & 0.25  & 0.003644          & 0.01939              \\
	      		           &             &            & 0.50  & 0.003644          & 0.02721              \\
	      		           &             &            & 0.75  & 0.003853          & 0.03040              \\
	      		           &             &            & 1.00  & 0.003772          & 0.03472              \\
	      		Total      &             &            &       &                   & 0.08451              \\
	      		\hline
	      		2-year Cap & 0.00322     & 1.28170    & 0.25  & 0.003644          & 0.02721              \\
	      		           &             &            & 0.50  & 0.003853          & 0.03927              \\
	      		           &             &            & 0.75  & 0.003772          & 0.04389              \\
	      		           &             &            & 1.00  & 0.00331           & 0.04003              \\
	      		           &             &            & 1.25  & 0.00274           & 0.03326              \\
	      		           &             &            & 1.50  & 0.00246           & 0.03108              \\
	      		           &             &            & 1.75  & 0.00276           & 0.03929              \\
	      		Total      &             &            &       &                   & 0.25403              \\
	      		\hline
	      	\end{tabular}
	      	\caption{Caplet Calculations for 1-year and 2-year Cap}
	      \end{table}
	      
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{|c|c|}
	      		\hline
	      		Strike Rate (5-year swap rate) & 0.00408 \\
	      		Forward 5-year Swap Rate       & 0.00481 \\
	      		Swaption Volatility            & 0.9912  \\
	      		Swaption Maturity              & 1       \\
	      		\hline
	      		$d_1$                          & 0.6617  \\
	      		$d_2$                          & -0.3295 \\
	      		A                              & 4.9315  \\
	      		Swaption                       & 0.01023 \\
	      		\hline
	      	\end{tabular}
	      	\caption{Swaption Data}
	      	\label{tab:swaption_data}
	      \end{table}
	      
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{|c|c|c|c|}
	      		\hline
	      		\textbf{Maturity} & \textbf{Forward Rate} & \textbf{Discount Factor} & \textbf{Caplet Price} \\
	      		\hline
	      		0.25              & NaN                   & NaN                      & NaN                   \\
	      		0.50              & 0.003644              & 0.998288                 & 0.019389              \\
	      		0.75              & 0.003853              & 0.997328                 & 0.030398              \\
	      		1.00              & 0.003772              & 0.996388                 & 0.034723              \\
	      		\hline
	      	\end{tabular}
	      	\caption{One-Year Cap Table}
	      	\label{tab:one_year_cap}
	      \end{table}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw5-1.png}
	      	\caption{1 Year Caplet Price}
	      \end{figure}
	      
	      \begin{table}[h!]
	      	\centering
	      	\begin{tabular}{|c|c|c|c|}
	      		\hline
	      		\textbf{Maturity} & \textbf{Forward Rate} & \textbf{Discount Factor} & \textbf{Caplet Price} \\
	      		\hline
	      		0.25              & NaN                   & NaN                      & NaN                   \\
	      		0.50              & 0.003644              & 0.998288                 & 0.027213              \\
	      		0.75              & 0.003853              & 0.997328                 & 0.039266              \\
	      		1.00              & 0.003772              & 0.996388                 & 0.043886              \\
	      		1.25              & 0.003312              & 0.995564                 & 0.040031              \\
	      		1.50              & 0.002741              & 0.994882                 & 0.033263              \\
	      		1.75              & 0.002460              & 0.994271                 & 0.031085              \\
	      		2.0               & 0.002762              & 0.993585                 & 0.039286              \\
	      		\hline
	      	\end{tabular}
	      	\caption{Two-Year Cap Table}
	      	\label{tab:two_year_cap}
	      \end{table}
	      
	      \begin{figure}[H]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw5-2.png}
	      	\caption{Two Year Caplet Prices}
	      \end{figure}
	      
	      
	      
	      
	      \section*{Part II: Interest Rate Trees}
	      
	      \subsection*{Questions}
	      
	      \begin{enumerate}
	      	\item[(PP)] Consider the following interest rate tree,  where each time interval is 1-year (that is,  $\Delta t = 1$).The probability of an “up” movement can either be $p = 40\%$ or $p = 70\%$. You also know the current value of a 2-period zero coupon bond is $Z_{0}(2) = 0.94$.
	      	      
	      	      \begin{enumerate}
	      	      	\item[(a)] Find the risk neutral probability $\pi^{*}$ (see TN4,  page 21) at time 0.
	      	      	\item[(b)] You have to compute the value of a one-year call option on the interest rate $r_{1}$ at the strike rate $r_{K} = 3\%$ and notional $N = 1000$,  that is,  with payoff $payoff_{1u} = 1000 \cdot \max(r_{1u} - r_{K},  0)$ in the “up” node; and $payoff_{1d} = 1000 \cdot \max(r_{1d} - r_{K},  0)$ in the “down” node. Use the risk-neutral probability $\pi^{*}$ in the previous point to compute the price for this option.
	      	      	\item[(c)] Does it matter which probability $p$ is the true one (i.e.,  whether $p = 40\%$ or $p = 70\%$)? Why?
	      	      	\item[(d)] Find the portfolio of securities that replicates the payoff of the option in point (b). What is the value of this portfolio at time 0? How does it compare with the value of the option computed in point (b)? Show your work and comment.
	      	      	\item[(e)] Assume the risk-neutral probability $\pi^{*}$ computed in point (a) is constant throughout the binomial tree. Use the risk-neutral methodology to compute:
	      	      	      \begin{itemize}
	      	      	      	\item[(i)] the value of a 3-year zero-coupon bond, 
	      	      	      	\item[(ii)] the value of a 3-year coupon bond with annual coupon equal to 3\%.
	      	      	      	\item[(iii)] Compute a replicating portfolio at time 0 that replicates the payoff of the coupon bond at time $i = 1$. That is:
	      	      	      	      \begin{itemize}
	      	      	      	      	\item Define a portfolio with $N_{0}$ units of the 3-period zero-coupon bond $Z_{0}(3)$ and $N_{1}$ units of the 1-period zero $Z_{0}(1)$
	      	      	      	      	      \[
	      	      	      	      	      	P_{0} = N_{0}Z_{0}(3) + N_{1}Z_{0}(2)
	      	      	      	      	      \]
	      	      	      	      	      so that $P_{1, u}$ and $P_{1, d}$ correspond to the total value of an investor in the coupon bond would receive (remember that such an investor is entitled to the coupon at time $i = 1$ in both nodes).
	      	      	      	      	\item Check that the replicating portfolio “replicates”,  that is,  that indeed $P_{1, u}$ and $P_{1, d}$ corresponds to the payoffs of the coupon bond.
	      	      	      	      \end{itemize}
	      	      	      \end{itemize}
	      	      \end{enumerate}
	      \end{enumerate}
	      
	      \subsection*{Solutions}
	      
	      \subsection*{1. Risk Neutral Probability and Market Price of Risk}
	      
	      Consider the following interest rate tree,  where each time interval is 1-year ($\Delta = 1$):
	      
	      The probability of an “up” movement can either be $p = 40\%$ or $p = 70\%$. The current value of a 2-period zero coupon bond is $Z_0(2) = 0.94$.
	      \begin{enumerate}
	      	\item Compute the risk neutral probability $\pi^*$ and confirm the same price for the option in point (b). What is the market price of risk under $\pi^*$?
	      	      
	      	      First,  compute the tree for the 2-period bond:
	      	      
	      	      \begin{center}
	      	      	\begin{tikzpicture}[node distance=2cm,  auto]
	      	      		% Nodes
	      	      		\node (n0) at (0,  0) [draw,  rectangle,  align=center] {
	      	      			$r_0 = 0.03$
	      	      		};
	      	      		\node (n1u) at (3,  1.5) [draw,  rectangle,  align=center] {
	      	      			$r_{1, u} = 0.04$
	      	      		};
	      	      		\node (n1d) at (3,  -1.5) [draw,  rectangle,  align=center] {
	      	      			$r_{1, d} = 0.02$
	      	      		};
	      	      		\node (n2uu) at (6,  2.5) [draw,  rectangle,  align=center] {
	      	      			$r_{2, uu} = 0.05$
	      	      		};
	      	      		\node (n2uddu) at (6,  0) [draw,  rectangle,  align=center] {
	      	      			$r_{2, ud} = 0.03$ \\
	      	      			$r_{2, du} = 0.03$
	      	      		};
	      	      		\node (n2dd) at (6,  -2.5) [draw,  rectangle,  align=center] {
	      	      			$r_{2, dd} = 0.01$
	      	      		};
	      	      		
	      	      		% Labels at the top
	      	      		\node at (0,  3) {$i=0$};
	      	      		\node at (3,  3) {$i=1$};
	      	      		\node at (6,  3) {$i=2$};
	      	      		
	      	      		% Paths (arrows can be added here if needed)
	      	      		\path[-] (n0) edge (n1u);
	      	      		\path[-] (n0) edge (n1d);
	      	      		\path[-] (n1u) edge (n2uu);
	      	      		\path[-] (n1u) edge (n2uddu);
	      	      		\path[-] (n1d) edge (n2uddu);
	      	      		\path[-] (n1d) edge (n2dd);
	      	      	\end{tikzpicture}
	      	      \end{center}
	      	      
	      	      The risk neutral probability can be computed from:
	      	      $$
	      	      \pi^* = \frac{Z_0(2)/Z_0(1) - Z_{1, d}(2)}{Z_{1, u}(2) - Z_{1, d}(2)} = \frac{0.96862 - 0.9802}{0.96079 - 0.9802} = 0.59646
	      	      $$
	      	      
	      	\item Compute the value of a one-year call option on the interest rate $r_1$ at the strike rate $r_K = 3\%$ and notional $N = 1000$:
	      	      $$
	      	      \text{payoff}_{1, u} = 1000 \times \max(r_{1, u} - r_K,  0)
	      	      $$
	      	      $$
	      	      \text{payoff}_{1, d} = 1000 \times \max(r_{1, d} - r_K,  0)
	      	      $$
	      	      
	      	      Use the pricing formula involving the market price of risk $\lambda$ to compute the value of the option under both probabilities ($p = 40\%$ and $p = 70\%$). Show your work and comment on the results.
	      	      
	      	      The value using the formula:
	      	      $$
	      	      V = Z_0(1) \times E^*[ \text{payoff}_1] = Z_0(1) \times [0.59646 \times 10] = 0.97045 \times 5.9646 = 5.79
	      	      $$
	      	      
	      	\item The probability to go up the tree does not show up in the formula,  and therefore it does not matter. The risk neutral methodology is only a tool to price securities by no arbitrage. The risk from the strategy has been eliminated by the replication strategy. Therefore,  the true probability does not enter the calculation anymore.
	      	      
	      	\item Find the portfolio of securities that replicates the payoff of the option in point (b). What is the value of this portfolio at time 0? How does it compare with the value of the option computed in point (b)? Show your work and comment.
	      	      
	      	      The portfolio is:
	      	      $$
	      	      P_0 = N_1Z_0(2) + N_2Z_0(1)
	      	      $$
	      	      The position in long-term bonds is:
	      	      $$
	      	      N_1 = \Delta = \frac{V_{1, u} - V_{1, d}}{Z_{1, u}(2) - Z_{1, d}(2)} = -515.21868
	      	      $$
	      	      The value of $N_2$ is:
	      	      $$
	      	      N_2 = \Pi_{1, d} = \text{payoff}_{1, d} - \Delta \times Z_{1, d}(2) = 0 - (-515.21868) \times Z_{1, d}(2) = 505.01667
	      	      $$
	      	      The value of the portfolio is:
	      	      $$
	      	      P_0 = N_1Z_0(2) + N_2Z_0(1) = 5.79
	      	      $$
	      	      
	      	      To check:
	      	      $$
	      	      P_{1, u} = N_1Z_{1, u}(2) + N_2 = 10
	      	      $$
	      	      $$
	      	      P_{1, d} = N_1Z_{1, d}(2) + N_2 = 0
	      	      $$
	      	      
	      	\item Assume the risk neutral probability $\pi^*$ computed in point (c) is constant throughout the binomial tree. Use the risk neutral methodology to compute:
	      	      
	      	      \begin{enumerate}
	      	      	\item The value of a 3-year zero-coupon bond:
	      	      	      \begin{table}[h]
	      	      	      	\centering
	      	      	      	\begin{tabular}{c|cccc}
	      	      	      		$j \setminus i$ & 0        & 1        & 2        & 3 \\
	      	      	      		\hline
	      	      	      		0               & 0.908892 & 0.921387 & 0.951229 & 1 \\
	      	      	      		1               & 0.958989 & 0.970446 & 1        & 1 \\
	      	      	      		2               & 0.99005  & 1        & 1        & 1 \\
	      	      	      		3               & 1        & 1        & 1        & 1 \\
	      	      	      	\end{tabular}
	      	      	      	\caption{Value of 3-Year Zero-Coupon Bond}
	      	      	      \end{table}
	      	      	      
	      	      	      At any node $i,  j$:
	      	      	      $$
	      	      	      Z_{ij}(3) = e^{-r_{ij}} (\pi^* Z_{i+1, j} + (1 - \pi^*) Z_{i+1, j+1})
	      	      	      $$
	      	      	      
	      	      	      
	      	      	\item The value of a 3-year coupon bond with annual coupon equal to 3%:
	      	      	      \begin{table}[h]
	      	      	      	\centering
	      	      	      	\begin{tabular}{c|cccc}
	      	      	      		$j \setminus i$ & 0        & 1        & 2        & 3 \\
	      	      	      		\hline
	      	      	      		0               & 0.993472 & 0.977852 & 0.979766 & 1 \\
	      	      	      		1               & 1.017165 & 0.999559 & 1        & 1 \\
	      	      	      		2               & 1.019751 & 1        & 1        & 1 \\
	      	      	      		3               & 1        & 1        & 1        & 1 \\
	      	      	      	\end{tabular}
	      	      	      	\caption{Value of 3-Year 3\% Coupon Bond }
	      	      	      \end{table}
	      	      	      
	      	      	      
	      	      	      
	      	      	      
	      	      	      At any node $i,  j$:
	      	      	      $$
	      	      	      P_{ij}(3) = e^{-r_{ij}} (\pi^* P_{i+1, j}(3) + (1 - \pi^*) P_{i+1, j+1}(3) + 0.03)
	      	      	      $$
	      	      	      
	      	      	\item Compute the replicating portfolio at time $i = 0$. Find $N_0$ in the 3-period bond and $N_1$ in the 1-period bond to replicate the coupon bond:
	      	      	      
	      	      	      \begin{center}
	      	      	      	\begin{tikzpicture}[node distance=2cm,  auto]
	      	      	      		\centering
	      	      	      		% Nodes
	      	      	      		\node (n0) at (0,  0) [draw,  rectangle,  align=center] {
	      	      	      			$Z_0(3) = 90.88915$
	      	      	      		};
	      	      	      		\node (n1u) at (3,  1.5) [draw,  rectangle,  align=center] {
	      	      	      			$Z_{1, u}(3) = 92.13868$
	      	      	      		};
	      	      	      		\node (n1d) at (3,  -1.5) [draw,  rectangle,  align=center] {
	      	      	      			$Z_{1, d}(3) = 95.89893$
	      	      	      		};
	      	      	      		\node (n2uu) at (6,  2.5) [draw,  rectangle,  align=center] {
	      	      	      			$Z_{2, uu}(3) = 95.12294$
	      	      	      		};
	      	      	      		\node (n2uddu) at (6,  0) [draw,  rectangle,  align=center] {
	      	      	      			$Z_{2, ud}(3) = 97.04455$ \\
	      	      	      			$Z_{2, du}(3) = 97.04455$
	      	      	      		};
	      	      	      		\node (n2dd) at (6,  -2.5) [draw,  rectangle,  align=center] {
	      	      	      			$Z_{2, dd}(3) = 99.00498$
	      	      	      		};
	      	      	      		
	      	      	      		% Labels at the top
	      	      	      		\node at (0,  4) {$i=0$};
	      	      	      		\node at (3,  4) {$i=1$};
	      	      	      		\node at (6,  4) {$i=2$};
	      	      	      		
	      	      	      		% Paths (arrows can be added here if needed)
	      	      	      		\path[-] (n0) edge (n1u);
	      	      	      		\path[-] (n0) edge (n1d);
	      	      	      		\path[-] (n1u) edge (n2uu);
	      	      	      		\path[-] (n1u) edge (n2uddu);
	      	      	      		\path[-] (n1d) edge (n2uddu);
	      	      	      		\path[-] (n1d) edge (n2dd);
	      	      	      	\end{tikzpicture}
	      	      	      \end{center}
	      	      	      
	      	      	      \begin{itemize}
	      	      	      	\item \indent (iii.a.) Define a portfolio with $N_{0}$ units of the 3-period zero-coupon bond $Z_{0}(3)$ and $N_{1}$ units of the 1-period zero $Z_{0}(1)$
	      	      	      	      \[
	      	      	      	      	P_{0} = N_{0}Z_{0}(3) + N_{1}Z_{0}(2)
	      	      	      	      \]
	      	      	      	      so that $P_{1, u}$ and $P_{1, d}$ correspond to the total value of an investor in the coupon bond would receive (remember that such an investor is entitled to the coupon at time $i = 1$ in both nodes).\\
	      	      	      	      \begin{itemize}               
	      	      	      	      	\item \indent \textbf{Solution: }We want to choose $N_0$ and $N_1$ so that the portfolio $P_0 = N_1 Z_0(3) + N_2 Z_0(1)$ is such that
	      	      	      	      	      \[
	      	      	      	      	      	\begin{aligned}
	      	      	      	      	      		P_{1, u} & = P^C_{1, u}(3) + c \\
	      	      	      	      	      		P_{1, d} & = P^C_{1, d}(3) + c 
	      	      	      	      	      	\end{aligned}
	      	      	      	      	      \]
	      	      	      	      	      where $P^C_{ij}(3)$ is the price of the coupon bond. Note that we inserted also the coupon $c$. Substitute the expression for $P_{ij}$:
	      	      	      	      	      \[
	      	      	      	      	      	\begin{aligned}
	      	      	      	      	      		N_1 Z_{1, u}(3) + N_2 & = P^C_{1, u}(3) + c \\
	      	      	      	      	      		N_1 Z_{1, d}(3) + N_2 & = P^C_{1, d}(3) + c 
	      	      	      	      	      	\end{aligned}
	      	      	      	      	      \]
	      	      	      	      	      
	      	      	      	      	      where we used the fact that $Z_{1, u}(1) = Z_{1, d}(1) = 1$
	      	      	      	      	\item \indent Solving the system,  we obtain
	      	      	      	      	      
	      	      	      	      	      \begin{equation}
	      	      	      	      	      	N_1 = \frac{P^C_{1, u}(3) - P^C_{1, d}(3)}{Z_{1, u}(3) - Z_{1, d}(3)} 
	      	      	      	      	      \end{equation}
	      	      	      	      	      \begin{equation}
	      	      	      	      	      	N_2 = \frac{P^C_{1, u}(3) + c - N_0 Z_{1, u}(3)}{Z_{1, u}(3)} 
	      	      	      	      	      \end{equation}   
	      	      	      	      	         
	      	      	      	      	      
	      	      	      	      	      which is the same value we obtained in TN 4 (page 9,  where $N_2 = \Pi_{1u} = (C_{1u} - \Delta Z_{1u}(2))$.
	      	      	      	      	\item \indent Substitute to find
	      	      	      	      	      
	      	      	      	      	      \begin{equation}
	      	      	      	      	      	N_1 = 1.045485
	      	      	      	      	      \end{equation}
	      	      	      	      	      \begin{equation}
	      	      	      	      	      	N_2 = 0.044556 
	      	      	      	      	      \end{equation}
	      	      	      	      	      
	      	      	      	      	\item \indent Its value today is then
	      	      	      	      	      \[
	      	      	      	      	      	P_0 = N_1 Z_0(3) + N_2 Z_0(1) = 0.993472
	      	      	      	      	      \]
	      	      	      	      	      which is the same value of the 3-period coupon bond.\\
	      	      	      	      \end{itemize}     
	      	      	      	                      
	      	      	      	\item \indent (iii.b.) Check that the replicating portfolio “replicates”,  that is,  that indeed $P_{1, u}$ and $P_{1, d}$ corresponds to the payoffs of the coupon bond.\\
	      	      	      	      \begin{itemize}
	      	      	      	      	\item \indent \textbf{Solution:}  The replicating portfolio replicates,  and we have the tree:
	      	      	      	      	      \begin{center}
	      	      	      	      	      	\begin{tikzpicture}[node distance=2cm,  auto]
	      	      	      	      	      		% Nodes
	      	      	      	      	      		\node (n0) at (0,  0) [draw,  rectangle,  align=center] {
	      	      	      	      	      			$P_0 = 0.993472$
	      	      	      	      	      		};
	      	      	      	      	      		\node (n1u) at (3,  1.5) [draw,  rectangle,  align=center] {
	      	      	      	      	      			$P_{1, u} = 1.007852$
	      	      	      	      	      		};
	      	      	      	      	      		\node (n1d) at (3,  -1.5) [draw,  rectangle,  align=center] {
	      	      	      	      	      			$P_{1, d} = 1.047165$
	      	      	      	      	      		};
	      	      	      	      	      		
	      	      	      	      	      		% Labels at the top
	      	      	      	      	      		\node at (0,  3) {$i=0$};
	      	      	      	      	      		\node at (3,  3) {$i=1$};
	      	      	      	      	      		
	      	      	      	      	      		% Paths (arrows can be added here if needed)
	      	      	      	      	      		\path[-] (n0) edge (n1u);
	      	      	      	      	      		\path[-] (n0) edge (n1d);
	      	      	      	      	      		
	      	      	      	      	      	\end{tikzpicture}
	      	      	      	      	      \end{center}
	      	      	      	      	      
	      	      	      	      	      
	      	      	      	      	      Note that the portfolio replicates the full payoff of the coupon bond at time $i = 1$,  including the coupon.
	      	      	      	      \end{itemize}          
	      	      	      	                     
	      	      	      \end{itemize}
	      	      	      
	      	      	      
	      	      	      
	      	      \end{enumerate}
	      \end{enumerate}
```

## HW 6

```latex
\newpage
\section*{Homework 6}
\textbf{Due at the beginning of Class 8}

\begin{quote}
	\textbf{Note:} As with past homework assignments there are “guides” for doing the homework in Excel,  Matlab,  and Python. Each code provides partial solutions to the questions. To make the code run,  you are required to complete some formulas or produce some of the results yourself. You are not required to use any of the guides,  but use of one of them is recommended.
\end{quote}
\subsection*{Pricing the Freddie Mac 6\% Callable Bond}
Attached below you will find the prospectus of Freddie Mac 6\%,  20-year callable bond,  issued on June 7,  2007. Your task in this homework is to obtain its fair valuation,  using both the Ho-Lee model and the Simple BDT model. Proceed as follows:

\begin{enumerate}
	\item[(CP)] Use the data in ”HW6 Data Bonds.xls” and extract the discount curve $Z(0,  T)$ from the Treasuries using the Nelson-Siegel model.
	\item[(CP)] Build the Ho-Lee tree,  given by
	      \[
	      	r_{i+1, j} = r_{i, j} + \omega(i) + \epsilon \cdot \vartheta_{i+1}
	      \]
	      where $\epsilon$ is the volatility of interest rates,  $\omega(i)$ are chosen to fit the term structure of interest rates exactly,  and
	      \[
	      	\vartheta(i) =
	      	\begin{cases}
	      		+1 & \text{with probability } \frac{1}{2} \\
	      		-1 & \text{with probability } \frac{1}{2} 
	      	\end{cases}
	      \]
	      Let $r_{0}$ match the first zero-coupon bond $Z_{0}(0.5)$ from Nelson-Siegel model. The methodology to fit the model to the term structure of interest rates is explained in TN4. Both the Matlab file and the guide spreadsheet that are available contain the routine to build it. You need a value of $\epsilon$. Use the data on six-month rates available in the dataset (HW6 FRB H15.csv) to estimate $\epsilon$ (this can be done by taking the standard deviation of first differences in interest rates,  over six-month periods,  which is one time step). Remember to annualize the volatility estimates,  as $\epsilon$ in Ho-Lee and BDT are annualized.
	\item[(CP)] After fitting the tree to the data,  please plot the zero-coupon bond yields from the tree and from the original zero-coupon bonds $Z(T)$ obtained from Nelson and Siegel (and used as inputs for the tree). Are they the same? Show also the first 10 time-steps of the interest rate tree (table 10 x 10).
	\item[(CP)] Use the tree to price the Freddie Mac Callable bond. Recall from the teaching notes that a callable bond can be decomposed into a non-callable bond minus a call option. Therefore:
	      \begin{itemize}
	      	\item Obtain the price of the non-callable bond.
	      	\item Obtain the price of the call option written on the non-callable bond.
	      	\item Obtain the price of the callable bond as the difference.
	      \end{itemize}
	      Please,  make sure to incorporate the fact that the callable bond becomes callable only after the First-Call-Date.
	\item[(CP)] Show the first 10 nodes of the non-callable bond,  the option to call,  and the callable security.
	\item[(CP)] Plot the price of the non-callable and of the callable security against interest rates at call time,  as well as 1,  2,  3 semesters before. How does the callable and non-callable bonds compare? Comment and discuss.
	\item[(CP)] Compute the duration and convexity of callable and non-callable bond at time 0. Comment on the difference between the two securities.
	\item[(CP)] Ho Lee versus Simple BDT. Redo all of the points above for the Simple BDT model (note: in both the Matlab file and the spreadsheet,  this amounts to changing BDT Flag from 0 to 1 and re-run the routine to build the tree. Everything else should be automatic,  except for the estimate of $\epsilon$ which now should use log differences in rates). Comment on the difference in price,  if any,  from the two methodologies.
\end{enumerate}
\begin{quote}
	\textbf{Additional notes for Matlab users:}
	\begin{enumerate}
		\item Note 1: Below you will find a generic backward algorithm for any security $P$ with periodic cash flows $c$,  maturity at time $n$,  and generic payoff $g = [g_{1},  …,  g_{n}]$.
		      \[
		      	PP(:, :) = \text{zeros}(n, n); \quad \% \text{initialize matrix for security}
		      \]
		      \[
		      	PP(1:n, n) = g; \quad \% \text{set final payoff of bond i equal to 1 for all nodes}
		      \]
		      \[
		      	\text{for j = n-1:-1:1} \quad \% \text{move backward on the tree,  from i-1,  back to 1}
		      \]
		      \[
		      	PP(1:j, j) = \exp(-\text{ImTree}(1:j, j) \cdot dt) \cdot (0.5 \cdot PP(1:j, j+1) + 0.5 \cdot PP(2:j+1, j+1, i) + c \cdot dt);
		      \]
		      \[
		      	\text{end}
		      \]
		\item Note 2: To plot bond prices against interest rates at a given time $j$,  you just need to use the following command:
		      \[
		      	\text{plot(ImTree}(1:j, j),  PP(1:j, j))
		      \]
	\end{enumerate}
\end{quote}

\begin{table}[h!]
	\centering
	\begin{tabular}{|c|c|}
		\hline
		\textbf{Metric} & \textbf{Value} \\
		\hline
		$P_{NC}$        & 108.5545       \\
		Call            & 17.0245        \\
		$P_{Call}$      & 91.53          \\
		\hline
	\end{tabular}
	\caption{Price of Freddie Mac Callable Bond}
	\label{tab:freddie_mac_callable_bond}
\end{table}

\newpage
\begin{center}
	PRICING SUPPLEMENT DATED May 22,  2007 \\
	(to Offering Circular Dated July 28,  2006)
\end{center}
\begin{quote}
	\begin{center}
		
		\$100, 000, 000 \\
		Freddie Mac \\
		6.00\% Fixed Rate Medium-Term Notes Due June 7,  2027 \\
		Redeemable periodically,  beginning June 7,  2011 \\
	\end{center}
	
	\begin{itemize}
		\item Issue Date: June 7,  2007
		\item Maturity Date: June 7,  2027
		\item Subject to Redemption: Yes. The Medium-Term Notes are redeemable at our option,  in whole only,  upon notice of not less than 5 Business Days,  at a price of 100\% of the principal amount,  plus accrued interest to the Redemption Date.
		\item Redemption Date(s): Semiannually,  on June 7 and December 7,  commencing June 7,  2011
		\item Interest Rate Per Annum: 6.00\%
		\item Frequency of Interest Payments: Semiannually,  in arrears,  commencing December 7,  2007
		\item Interest Payment Dates: June 7 and December 7
		\item Principal Payment: At maturity,  or upon redemption
		\item CUSIP Number: 3128X6AT3 \\
	\end{itemize}
	You should read this Pricing Supplement together with Freddie Mac’s Global Debt Facility Offering Circular,  dated July 28,  2006 (the “Offering Circular”),  and all documents that are incorporated by reference in the Offering Circular,  which contain important detailed information about the Medium-Term Notes and Freddie Mac. See “Available Information” in the Offering Circular. Capitalized terms used in this Pricing Supplement have the meanings we gave them in the Offering Circular,  unless we specify otherwise. \\
	
	The Medium-Term Notes may not be suitable investments for you. You should not purchase the Medium-Term Notes unless you understand and are able to bear the redemption,  yield,  market,  liquidity and other possible risks associated with the Medium-Term Notes. You should read and evaluate the discussion of risk factors (especially those risk factors that may be particularly relevant to this security) that appears in the Offering Circular under “Risk Factors” before purchasing any of the Medium-Term Notes.
	
	The Medium-Term Notes,  including any interest or return of discount on the Medium-Term Notes,  are not guaranteed by and are not debts or obligations of the United States or any federal agency or instrumentality other than Freddie Mac. \\
	
	Any discussion of tax issues set forth in this Pricing Supplement and the related Offering Circular was written to support the promotion and marketing of the transactions described in this Pricing Supplement. Such discussion was not intended or written to be used,  and it cannot be used,  by any person for the purpose of avoiding any tax penalties that may be imposed on such person. Each investor should seek advice based on its particular circumstances from an independent tax advisor.
	\begin{center}
		\begin{table}[h!]
			\centering
			\begin{tabular}{|l|c|c|c|}
				\hline
				                     & \textbf{Price to Public\textsuperscript{(1)(2)}} & \textbf{Underwriting Discount\textsuperscript{(2)}} & \textbf{Proceeds to Freddie Mac\textsuperscript{(1)(3)}} \\
				\hline
				Per Medium-Term Note & 100\%                                            & 0.415\%                                             & 99.585\%                                                 \\
				\hline
				Total                & \$100, 000, 000                                    & \$415, 000                                           & \$99, 585, 000                                             \\
				\hline
			\end{tabular}
		\end{table}
	\end{center}
	\begin{itemize}
		\item (1) Plus accrued interest,  if any,  from June 7,  2007.
		\item (2) See “Distribution Arrangements” in the Offering Circular.
		\item (3) Before deducting expenses payable by Freddie Mac estimated at \$1, 000.
	\end{itemize}
	\begin{center}
		Goldman,  Sachs \& Co.
	\end{center}
\end{quote}

\section*{Part I: Pricing Freddie Mac 6\% Callable Bond}

The prospectus of Freddie Mac 6\%,  20-year callable bond,  issued on June 7,  2007,  shows that the bond becomes callable in June 2011,  and it can only be called on coupon dates. We are going to follow the same steps as in the note,  but now on a much bigger tree. We can concentrate on a tree with 40 steps,  that is,  a 20-year binomial tree with semi-annual increments $\Delta = 0.5$.

\begin{enumerate}
	\item Use the data in ”HW6 Data Bonds.xls” and extract the discount curve $Z(0,  T)$ from the Treasuries using the Nelson-Siegel model.\\
	      
	\item \textbf{Solution:}  We use the data in ”HW4 Data Bonds.xls” and extract the discount curve $Z(0,  T)$ from the Treasuries using the Nelson-Siegel model,  as we did in HW4. 
	      
	      \begin{itemize}
	      	\item Figures 37 through 39 show the resulting fit. 
	      	      
	      	      \begin{figure}[h!]
	      	      	\centering
	      	      	\includegraphics[width=0.8\textwidth,  height=0.4 \textheight]{hw6-1.png}
	      	      	\caption{Fitted Data}
	      	      \end{figure}
	      	      
	      	      \begin{figure}[h!]
	      	      	\centering
	      	      	\includegraphics[width=0.8\textwidth]{hw6-2.png}
	      	      	\caption{Zero Coupon Curve}
	      	      \end{figure}
	      	      
	      	      \begin{figure}[h!]
	      	      	\centering
	      	      	\includegraphics[width=0.8\textwidth]{hw6-3.png}
	      	      	\caption{Yield Curve}
	      	      \end{figure}
	      	      
	      \end{itemize}
	      \newpage
	\item Build the Ho-Lee tree,  given by \( r_{i+1, j} = r_{i, j} + \theta(i) \times \Delta + \sigma \times \sqrt{\Delta} \times \epsilon_{i+1} \) where $\sigma$ is the volatility of interest rates,  $\theta(i)$ are chosen to fit the term structure of interest rates exactly,  and \[ \epsilon(i) = \begin{cases} +1 & \text{with probability } \frac{1}{2} \\ -1 & \text{with probability } \frac{1}{2} \end{cases} \] Let $r_{0}$ match the first zero-coupon bond $Z_{0}(0.5)$ from Nelson-Siegel model.\\
	      
	      \textbf{Solution:}  We need to estimate $\sigma$. We use the data provided,  which are monthly. If we use the formula $\text{St.Dev.}(dr_t)$ where $dr_t = r_{t+1} - r_t$ is the change in interest rate,  we obtain a volatility in monthly unit. Because $\sigma$ needs to be annualized,  we choose
	      $$
	      \sigma = \text{St.Dev.}(dr_t) \sqrt{12} = 1.60\%
	      $$
	      
	      Using the routine provided,  we obtain the following tree (first 10 steps).\\
	      \begin{table}[ht]
	      	\centering
	      	\resizebox{0.9\textwidth}{!}{
	      		\begin{tabular}{|c|cccccccccc|}
	      			\hline
	      			  & 0      & 1      & 2      & 3      & 4      & 5       & 6       & 7       & 8       & 9       \\
	      			\hline
	      			0 & 5.0684 & 6.0195 & 7.1238 & 8.303  & 9.5166 & 10.7459 & 11.9782 & 13.2075 & 14.4367 & 15.6597 \\
	      			1 & 0      & 3.761  & 4.8653 & 6.0445 & 7.2581 & 8.4874  & 9.7197  & 10.949  & 12.178  & 13.4012 \\
	      			2 & 0      & 0      & 2.6068 & 3.786  & 4.9997 & 6.2289  & 7.4613  & 8.6905  & 9.9197  & 11.1427 \\
	      			3 & 0      & 0      & 0      & 1.5276 & 2.7412 & 3.9704  & 5.2028  & 6.432   & 7.6613  & 8.8843  \\
	      			4 & 0      & 0      & 0      & 0      & 0.4827 & 1.7119  & 2.9443  & 4.1735  & 5.4028  & 6.6258  \\
	      			5 & 0      & 0      & 0      & 0      & 0      & -0.5466 & 0.6858  & 1.9151  & 3.1443  & 4.3673  \\
	      			6 & 0      & 0      & 0      & 0      & 0      & 0       & -1.5727 & -0.3434 & 0.8858  & 2.1088  \\
	      			7 & 0      & 0      & 0      & 0      & 0      & 0       & 0       & -2.6019 & -1.3727 & -0.1497 \\
	      			8 & 0      & 0      & 0      & 0      & 0      & 0       & 0       & 0       & -3.6312 & -2.4082 \\
	      			9 & 0      & 0      & 0      & 0      & 0      & 0       & 0       & 0       & 0       & -4.6667 \\
	      			\hline
	      		\end{tabular}
	      	}
	      	\caption{Ho Lee Interest Rate Tree}
	      	\label{tab:ho_lee_interest_rate_tree}
	      \end{table}
	      
	\item  After fitting the tree to the data,  please plot the zero-coupon bond yields from the tree and from the original zero-coupon bonds $Z(T)$ obtained from Nelson and Siegel (and used as inputs for the tree). Are they the same? Show also the first 10 time-steps of the interest rate tree (table 10 x 10).\\
	      
	      \textbf{Solution:}  We can also plot the yield of zero-coupon bonds using the tree and the original data. Because an outcome of the procedure is to produce the whole set of binomial trees for zero-coupon bonds $Z(:,  :,  i)$,  we can compute the zero-coupon bond for each bond $i$,  $Z(1,  1,  i)$,  and then compute the yield to maturity across maturities.
	      \begin{itemize}
	      	\item Clearly,  there is no difference between the inputs used and the outcome of the tree,  by construction.
	      	      
	      	\item What does $\theta(i)$ look like? The next figure shows $\theta(i)$ together with the following quantity
	      	      $$
	      	      \frac{\partial f(0,  T(i+1))}{\partial t} + \sigma^2 T(i)
	      	      $$
	      	      where $f(0,  T(i))$ is the forward rate at 0 with maturity $T(i)$ (and 0.5 steps),  and $T(i) = i\Delta$.
	      	      
	      	      \begin{figure}[H]
	      	      	\centering
	      	      	\includegraphics[width=0.8\textwidth]{hw6-06.png}
	      	      	\caption{Theta versus Forward Rate Derivative}
	      	      \end{figure}
	      	      
	      	\item Interestingly,  the two curves are very close to each other. It turns out that as the time steps decrease to 0 we obtain exactly the same value. That is,  as $\Delta \rightarrow 0$,  we indeed obtain
	      	      $$
	      	      \theta(t) = \frac{\partial f(0,  t)}{\partial t} + \sigma^2 t
	      	      $$
	      	      where $f(0,  t)$ is the instantaneous forward rate,  namely,  the forward rate at 0 for an investment between $t$ and $t + dt$.\\
	      \end{itemize}
	      
	\item  Use the tree to price the Freddie Mac Callable bond. Recall from the teaching notes that a callable bond can be decomposed into a non-callable bond minus a call option. 
	      
	      \begin{itemize}
	      	\item \indent Therefore: Obtain the price of the non-callable bond,  using the algorithm
	      	      $$
	      	      \text{PP}(:,  :) = \text{zeros}(n,  n); $$
	      	      $$ \text{PP}(1:n,  n) = 100; \quad \text{set final payoff of bond i equal to 1 for all nodes}
	      	      $$
	      	      $$
	      	      \text{for } j = n-1:-1:1 \quad \text{move backward on the tree,  from i-1,  back to 1}
	      	      $$
	      	      \begin{align}
	      	      	\text{PP}(1:j,  j) = \exp(-\text{ImTree}(1:j,  j) \times dt) \times (0.5 \times \text{PP}(1:j,  j+1) + 0.5 \times \text{PP}(2:j+1,  j+1,  i) + 3 \times dt); 
	      	      \end{align}
	      	      
	      \end{itemize}
	      
	      \textbf{Solution:}  We obtain the tree (first 10 steps).
	      
	      \begin{table}[ht]
	      	\centering
	      	\resizebox{0.9\textwidth}{!}{
	      		\begin{tabular}{|c|cccccccccc|}
	      			\hline
	      			  & 0        & 1       & 2        & 3        & 4        & 5        & 6        & 7        & 8        & 9        \\
	      			\hline
	      			0 & 108.5546 & 93.8025 & 81.8832  & 72.1938  & 64.2522  & 57.6845  & 52.2033  & 47.588   & 43.6682  & 40.3136  \\
	      			1 & 0        & 122.879 & 105.454  & 91.511   & 80.2557  & 71.0825  & 63.5339  & 57.2627  & 52.0051  & 47.5602  \\
	      			2 & 0        & 0       & 138.9691 & 118.5906 & 102.3822 & 89.3609  & 78.794   & 70.1328  & 62.9649  & 56.98    \\
	      			3 & 0        & 0       & 0        & 156.994  & 133.3317 & 114.5868 & 99.5816  & 87.4452  & 77.53    & 69.3533  \\
	      			4 & 0        & 0       & 0        & 0        & 177.0637 & 149.7566 & 128.1869 & 110.967  & 97.0764  & 85.7617  \\
	      			5 & 0        & 0       & 0        & 0        & 0        & 199.2266 & 167.901  & 143.2089 & 123.5376 & 107.7075 \\
	      			6 & 0        & 0       & 0        & 0        & 0        & 0        & 223.4648 & 187.7465 & 159.6359 & 137.2828 \\
	      			7 & 0        & 0       & 0        & 0        & 0        & 0        & 0        & 249.6826 & 209.2128 & 177.4063 \\
	      			8 & 0        & 0       & 0        & 0        & 0        & 0        & 0        & 0        & 277.6979 & 232.1573 \\
	      			9 & 0        & 0       & 0        & 0        & 0        & 0        & 0        & 0        & 0        & 307.2459 \\
	      			\hline
	      		\end{tabular}}
	      	\caption{Non callable 20 year,  6\% coupon bond}
	      	\label{tab:non_callable_20_year_bond}
	      \end{table}
	      
	\item Obtain the price of the call option written on the non-callable bond. In this case,  we define $iFCT$ the first time when the option can be exercised. And then we use the algorithm
	      
	      \begin{align*}
	      	  & \text{Call}(:,  :) = \text{zeros}(n,  n); \quad \% \text{initialize matrix for security}                                                                                                   \\
	      	  & \text{Call}(1:n,  n) = 0; \quad \% \text{set final payoff of bond i equal to 0 for all nodes}                                                                                             \\
	      	  & \text{for } j = n-1 \text{ to } 1 \quad \% \text{move backward on the tree,  from i-1,  back to 1}                                                                                         \\
	      	  & \quad \text{if } j \geq \text{iFCT}                                                                                                                                                      \\
	      	  & \quad \quad \text{Call}(1:j,  j) = \max \left( \exp(-\text{ImTree}(1:j,  j) \cdot dt) \cdot \left( 0.5 \cdot \text{Call}(1:j,  j+1) + 0.5 \cdot \text{Call}(2:j+1,  j+1,  i) \right),  \right. \\
	      	  & \quad \quad \quad \left. PP(i:j,  j) - 100 \right);                                                                                                                                       \\
	      	  & \quad \text{else}                                                                                                                                                                        \\
	      	  & \quad \quad \text{Call}(1:j,  j) = \exp(-\text{ImTree}(1:j,  j) \cdot dt) \cdot \left( 0.5 \cdot \text{Call}(1:j,  j+1) + 0.5 \cdot \text{Call}(2:j+1,  j+1,  i) \right);                     \\
	      	  & \quad \text{end}                                                                                                                                                                         \\
	      	  & \text{end}                                                                                                                                                                               
	      \end{align*}
	      
	      
	      
	      
	      
	      \textbf{Solution:}  We obtain the tree.
	      
	      \begin{table}[ht]
	      	\centering
	      	\resizebox{0.9\textwidth}{!}{
	      		\begin{tabular}{|c|cccccccccc|}
	      			\hline
	      			  & 0       & 1       & 2       & 3       & 4       & 5       & 6        & 7        & 8        & 9        \\
	      			\hline
	      			0 & 17.0245 & 10.0772 & 5.6257  & 2.9688  & 1.4963  & 0.7219  & 0.3319   & 0.1444   & 0.0590   & 0.0224   \\
	      			1 & 0       & 24.8458 & 15.1445 & 8.6906  & 4.6931  & 2.4165  & 1.1917   & 0.5604   & 0.2495   & 0.1044   \\
	      			2 & 0       & 0       & 35.4904 & 22.3442 & 13.2214 & 7.3166  & 3.8508   & 1.9417   & 0.9342   & 0.4260   \\
	      			3 & 0       & 0       & 0       & 49.5678 & 32.3211 & 19.7955 & 11.2453  & 6.0526   & 3.1216   & 1.5374   \\
	      			4 & 0       & 0       & 0       & 0       & 67.5744 & 45.7388 & 29.1396  & 17.0307  & 9.3793   & 4.9494   \\
	      			5 & 0       & 0       & 0       & 0       & 0       & 89.7366 & 63.1244  & 42.1129  & 25.4003  & 14.3228  \\
	      			6 & 0       & 0       & 0       & 0       & 0       & 0       & 115.8591 & 84.5694  & 59.6359  & 37.2828  \\
	      			7 & 0       & 0       & 0       & 0       & 0       & 0       & 0        & 145.3338 & 109.2128 & 77.4063  \\
	      			8 & 0       & 0       & 0       & 0       & 0       & 0       & 0        & 0        & 177.6979 & 132.1573 \\
	      			9 & 0       & 0       & 0       & 0       & 0       & 0       & 0        & 0        & 0        & 207.2459 \\
	      			\hline
	      		\end{tabular}}
	      	\caption{Call option tree}
	      	\label{tab:call_option_tree}
	      \end{table}
	      
	      We finally obtain the price of the callable bond as the difference\\
	      
	      \textbf{Solution:} Note that the value of the bond is $PC_0(40) = \$91.5301$,  which is well below 100,  the likely issue price. The value of the non-callable bond does not depend on the tree used,  because the tree exactly fits the zero-coupon bonds $Z(T)$ and the non-callable bond can be valued directly from $Z(T)$. Thus,  the low value of the callable bond must come from an excessive value of the call option $Call_0$. That is,  the volatility $\sigma = 1.60\%$ is too high. The likely reason is that the data set also includes the extremely high volatility of interest rates in the 1980s. If we restrict the data to the last 10 years in the sample (120 months). The volatility is much smaller,  and equal to $\sigma = 0.67\%$. In this case,  indeed,  we obtain $PC_0 = \$99.45$,  which is very close to par. \\
	      
	      \begin{table}[ht]
	      	\centering
	      	\resizebox{0.9\textwidth}{!}{
	      		
	      		\begin{tabular}{|c|cccccccccc|}
	      			\hline
	      			  & 0       & 1       & 2        & 3        & 4        & 5        & 6        & 7        & 8        & 9        \\
	      			\hline
	      			0 & 91.5301 & 83.7253 & 76.2575  & 69.2249  & 62.7560  & 56.9625  & 51.8714  & 47.4436  & 43.6092  & 40.2911  \\
	      			1 & 0       & 98.0332 & 90.3096  & 82.8205  & 75.5626  & 68.6660  & 62.3422  & 56.7024  & 51.7555  & 47.4558  \\
	      			2 & 0       & 0       & 103.4788 & 96.2464  & 89.1608  & 82.0444  & 74.9432  & 68.1912  & 62.0307  & 56.5540  \\
	      			3 & 0       & 0       & 0        & 107.4263 & 101.0105 & 94.7912  & 88.3364  & 81.3926  & 74.4084  & 67.8159  \\
	      			4 & 0       & 0       & 0        & 0        & 109.4893 & 104.0178 & 99.0473  & 93.9364  & 87.6971  & 80.8122  \\
	      			5 & 0       & 0       & 0        & 0        & 0        & 109.4900 & 104.7766 & 101.0960 & 98.1373  & 93.3847  \\
	      			6 & 0       & 0       & 0        & 0        & 0        & 0        & 107.6057 & 103.1770 & 100.0000 & 100.0000 \\
	      			7 & 0       & 0       & 0        & 0        & 0        & 0        & 0        & 104.3487 & 100.0000 & 100.0000 \\
	      			8 & 0       & 0       & 0        & 0        & 0        & 0        & 0        & 0        & 100.0000 & 100.0000 \\
	      			9 & 0       & 0       & 0        & 0        & 0        & 0        & 0        & 0        & 0        & 100.0000 \\
	      			\hline
	      		\end{tabular}}
	      	\caption{Callable Bond Tree}
	      	\label{tab:callable_bond_tree}
	      \end{table}
	      
	      
	      
	\item  Plot the price of the non-callable and of the callable security against interest rates at call time,  as well as 1,  2,  3 semesters before. How does the callable and non-callable bonds compare? Comment and discuss.\\
	      
	      \textbf{Solution:}  Figure 6 plots the price of the non-callable and of the callable security against interest rates at call time,  as well as 1,  2,  3 semesters before.
	      
	      \begin{figure}[h!]
	      	\centering
	      	\includegraphics[width=0.8\textwidth]{hw6-6.png}
	      	\caption{Bond Prices at Different Times Before FCD}
	      \end{figure}
	      
	      The non-callable bond shows the usual pattern,  with positive convexity. Instead,  the callable security shows a negatively convex pattern with respect to interest rates. The reason is that as interest rates decline,  it becomes more and more likely that the bond will be called at par. Hence,  the value of the bond reflects this loss in future upside potential of the callable bond,  and thus results in a negatively convex pattern. Indeed,  in the first top left panel,  we see that at the first call date,  if interest rates are low enough,  then the value of the bond exactly equals 100,  as the bond gets called. \\
	      
	\item  Compute the duration and convexity of callable and non-callable bonds at time 0. Comment on the difference between the two securities.\\
	      
	      \textbf{Solution:}  We finally get to compute the duration and convexity of callable and non-callable bonds at time 0. This exercise required a bit of thinking,  but the idea is to use the definition of duration and convexity,  but this time on a tree. Recall the sensitivity of the bond price to changes in interest rates is (use “up” $u$ and “down” $d$ notation for convenience)
	      
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
	      
	      By applying these formulas to the two types of bonds,  we obtain
	      
	      $$
	      D_{NC} = 11.8598; \quad D_{Callable} = 6.9214
	      $$
	      
	      and
	      
	      $$
	      C_{NC} = 179.59; \quad C_{Callable} = -18.9098
	      $$
	      
	      The non-callable security is strongly positively convex,  while the callable security is mildly positive convex. The reason is that at issuance,  the call time is still pretty far away. For instance,  if we were to consider the first-call time to be just one year from now,  and redo the computations,  we would find $C_{Callable} = -86.60$.\\
	      
	\item  Ho Lee versus Simple BDT. Redo all of the points above for the Simple BDT model (note: in both the Matlab file and the spreadsheet,  this amounts to changing BDT Flag from 0 to 1 and re-run the routine to build the tree. Everything else should be automatic,  except for the estimate of $\epsilon$ which now should use log differences in rates). Comment on the difference in price,  if any,  from the two methodologies.\\
	      
	      \textbf{Solution:}  Switching to logarithm produces a different tree for interest rates. The difference from before is that $\sigma$ needs to use log interest rates
	      
	      $$
	      \sigma = \text{St.Dev.}(d \log(r_t)) \sqrt{12}
	      $$
\end{enumerate}
\newpage
```

## HW 7

```latex
\maketitle
\section*{Homework 7}
\subsection*{ \textbf{Relative Value Trades and Mortgage Backed Securities}}
\begin{quote}
	\textbf{Note 1:} The first part of this assignment is about a simple relative value trade on Trees. The other parts of the assignment are on Mortgage Backed Securities,  and valuation using both trees and Monte Carlo simulations. It appears long as we describe all of the steps,  but the guide Matlab and Excel codes perform automatically large parts of the exercise. Available on Canvas are guideline files in Excel,  Matlab and Python that implement many of the steps. \\ \\
	\textbf{Note 2:} Parts I and II are “pencil and paper” (PP) questions. The other parts use data and computer programs (CP). You are supposed to do both.
\end{quote}
\section*{Part I: Relative Value Trades on Binomial Trees (PP)}
\begin{enumerate}
	\item Consider the following binomial tree. Each time interval is 1-year (that is,  $\Delta t = 1$).
	      
	      \begin{tikzpicture}[node distance=2cm,  auto]
	      	% Nodes
	      	\node (n0) at (0,  0) [draw,  rectangle,  align=center] {
	      		$r_0 = 0.03$
	      	};
	      	\node (n1u) at (3,  1.5) [draw,  rectangle,  align=center] {
	      		$r_{1, u} = 0.04$
	      	};
	      	\node (n1d) at (3,  -1.5) [draw,  rectangle,  align=center] {
	      		$r_{1, d} = 0.02$
	      	};
	      	\node (n2uu) at (6,  2.5) [draw,  rectangle,  align=center] {
	      		$r_{2, uu} = 0.05$
	      	};
	      	\node (n2uddu) at (6,  0) [draw,  rectangle,  align=center] {
	      		$r_{2, ud} = 0.03$ \\
	      		$r_{2, du} = 0.03$
	      	};
	      	\node (n2dd) at (6,  -2.5) [draw,  rectangle,  align=center] {
	      		$r_{2, dd} = 0.01$
	      	};
	      	
	      	% Labels at the top
	      	\node at (0,  3.25) {$i=0$};
	      	\node at (3,  3.25) {$i=1$};
	      	\node at (6,  3.25) {$i=2$};
	      	
	      	% Paths (arrows can be added here if needed)
	      	\path[-] (n0) edge (n1u);
	      	\path[-] (n0) edge (n1d);
	      	\path[-] (n1u) edge (n2uu);
	      	\path[-] (n1u) edge (n2uddu);
	      	\path[-] (n1d) edge (n2uddu);
	      	\path[-] (n1d) edge (n2dd);
	      \end{tikzpicture}
	\end{itemize}
	The 2-period bond is $Z_{0}(2) = 0.94$,  which implied a risk-neutral probability $\omega = 0.59618073$. The true probability to move up the tree is $p = 0.5$. \\
	
	The three period,  fixed-coupon bond with coupon rate $c = 3\%$ is trading at par 100. Your model,  instead,  prescribes it should trade at $P_{0}(3) = 99.34716$. The three-period zero coupon bond $Z_{0}(3) = 90.88915$ seems to be trading at the proper price.\\
	
	\begin{enumerate}
		Design a relative value trading strategy to take advantage of the miss-pricing (according to your model). Please,  be clear on what you sell and what you buy. Recall that the only traded securities are the coupon bond (which is miss-priced) and the 3-period zero-coupon bond (which is correctly priced). In addition,  you can buy and sell 1-period bonds (i.e.,  borrow and lend at the rates on the tree).\\ \\ 
		    
		\textbf{Solution:} The binomial tree of the coupon bond with coupon rate $c = 3\%$ that we need to replicate (the “theoretical” price) is:\\ \\
		
		\begin{table}[h!]
			\caption{3-year,  3\% coupon bond $P_{ij}$}
			\begin{tabular}{c|cccc}
				  & $t = 0$  & $t = 1$  & $t = 2$  & $t = 3$ \\
				\hline
				  & 99.34716 & 97.7852  & 97.97663 & 100     \\
				  &          & 101.7165 & 99.95589 & 100     \\
				  &          &          & 101.9751 & 100     \\
				  &          &          &          & 100     \\
			\end{tabular}
		\end{table}
		   
		\item Make a binomial tree with the trading strategy up to maturity: Indicate the positions in traded securities at any point. (You can use Excel for this. But make sure to report the trees in the assignment).\\ 
		      \textbf{Solution:} The 3-year zero coupon bond is fairly priced and it is on the following tree:
	\end{enumerate}
	
	\begin{table}[h!]
		\centering
		\begin{tabular}{c|cccc}
			         & $t = 0$  & $t = 1$  & $t = 2$  & $t = 3$ \\
			\hline
			$P_{00}$ & 90.88915 & 92.13868 & 95.12294 & 100     \\
			$P_{01}$ &          & 95.89893 & 97.04455 & 100     \\
			$P_{02}$ &          &          & 99.00498 & 100     \\
			$P_{03}$ &          &          &          & 100     \\
		\end{tabular}
		\caption{3-year,  zero-coupon bond $Z_{ij}(3)$}
	\end{table}
	
	
	What is the total profit and loss?\\
	\textbf{Solution:} Finally,  the interest rate tree is given by:
	\end{itemize}
	\end{itemize}
	
	\begin{table}[h!]
		\begin{center}{
				\caption{Interest Rate Tree}
				\begin{tabular}{c|ccc}
					         & $t = 0$ & $t = 1$ & $t = 2$ \\
					\hline
					$r_{00}$ & 0.03    & 0.04    & 0.05    \\
					$r_{01}$ &         & 0.02    & 0.03    \\
					$r_{02}$ &         &         & 0.01    \\
				\end{tabular}
				}\end{center}
			\end{table}
			
			\item We replicate the coupon-bond using the zero-coupon bond. At time 0,  we have:
			
			$$
			\Delta_0 = \frac{(P_{1u} + c) - (P_{1d} + c)}{Z_{1u}(3) - Z_{1d}(3)} = 1.045485
			$$
			
			\item The position in “cash” (borrowing) is:
			
			$$
			C_0 = e^{-r_0}(-P_{1u} - c + \Delta_0 Z_{1u}(3)) = -4.323913
			$$
			
			\item Note that we take into account the fact that we have to pay the coupon tomorrow ($c$) in the present value.
			
			\item The value of the replicating portfolio today is:
			
			$$
			\Pi_0 = \Delta_0 Z_0(3) - C_0 = 99.34716
			$$
			
			which is equal to the “theoretical” value of the coupon bond. So,  we sell the mispriced bond at 100,  and purchase the portfolio $\Pi_0$ for 99.34718,  and make a profit today.
			
			The next table shows the trading strategy going forward:
			\begin{table}[h!]
				\begin{center}
					\begin{tabular}{cccc}
						\toprule
						$t=0$                 & $t=1$(start)                        & $t=1$(end)                         & $t=2$                                \\
						\midrule
						$\Delta_0 = 1.045485$ & $\Delta_{1, u} = 1.03$               &                                    & $\Pi_{2, uu}^{\text{cum}} = 100.9766$ \\
						$C_0 = -4.323913$     & $C_{1, u} = -2.882368$               &                                    & $\Pi_{2, uu}^{\text{ex}} = 97.97663$  \\
						$\Pi_0 = 99.34716$    & $\Pi_{1, u}^{\text{cum}} = 100.7852$ & $\Pi_{1, u}^{\text{ex}} = 97.7852$  &                                      \\
						& & $\Pi_{2, ud}^{\text{cum}} = \Pi_{2, du}^{\text{cum}} = 102.9559$ \\
						& $\Delta_{1, d} = 1.03$ & $\Pi_{2, ud}^{\text{ex}} = \Pi_{2, du}^{\text{ex}} = 99.95589$ \\
						                      & $C_{1, d} = -2.940596$               &                                    &                                      \\
						                      & $\Pi_{1, d}^{\text{cum}} = 104.7165$ & $\Pi_{1, d}^{\text{ex}} = 101.7165$ & $\Pi_{2, dd}^{\text{cum}} = 104.9751$ \\
						                      &                                     &                                    & $\Pi_{2, dd}^{\text{ex}} = 101.9751$  \\
						\bottomrule
					\end{tabular}
				\end{center}
			\end{table}
			
			\end{itemize}
			   
			   
			\end{enumerate}
			
			In particular,  we divide time $t = 1$ in two periods. The start of the period shows the value of the portfolio designed at time 0 as the result of an up or down movement in interest rate. The start of the period includes the payment of the coupon $c = 3$. As can be seen,  the ex-coupon price is indeed equal to the theoretical value in the first binomial tree.\\
			
			The end of the period included the rebalancing,  that is,  
			\begin{enumerate}
				\item \indent the new position in the zero coupon bond,  e.g. $$\Delta_{1u} = \frac{(P_{2uu} + c) - (P_{2ud} + c)}{Z_{2uu}(3) - Z_{2ud}(3)} = 1.03$$,  
				\item \indent the new position in cash,  e.g. $$C_{1u} = e^{-r_{1u}}(-P_{2uu} - c + \Delta_{1u} Z_{2uu}(3)) = -2.882368$$,  
				\item \indent and the check that the new portfolio after rebalancing has the same value of the old portfolio (as it has). This means that the strategy is self financing. (This is equivalent to noticing that $$C_{1u} = C_0 e^{r_0} + (\Delta_{1u} - \Delta_0)Z_{1u}(3) + c = -2.882368$$ 
				      
				      The other periods are similar. We stop at time $t = 2$ as clearly the last $\Delta$ is always zero,  as the bonds converge to 100 in the last period. Therefore,  the position in cash in the last period must be equal to the present value of 103 one period later,  as in fact it is. For instance,  $\Pi_{2, uu} = 97.97663 = e^{-r_{2uu}}$. Hence,  simply investing the last value of the portfolio at the risk-free rate provides the last cash flow of the bond we want to replicate.
			\end{enumerate}
			
			
			\section*{Part II: Interest Rate Trees (PP)}
			
			Consider the interest rate tree examined in HW5,  reported below. Recall that each time interval is 1-year (that is,  $\Delta t = 1$).
			
			\begin{center}
				\begin{tikzpicture}[node distance=2cm,  auto]
					% Nodes
					\node (n0) at (0,  0) [draw,  rectangle,  align=center] {
						$r_0 = 0.03$
					};
					\node (n1u) at (3,  1.5) [draw,  rectangle,  align=center] {
						$r_{1, u} = 0.04$
					};
					\node (n1d) at (3,  -1.5) [draw,  rectangle,  align=center] {
						$r_{1, d} = 0.02$
					};
					\node (n2uu) at (6,  2.5) [draw,  rectangle,  align=center] {
						$r_{2, uu} = 0.05$
					};
					\node (n2uddu) at (6,  0) [draw,  rectangle,  align=center] {
						$r_{2, ud} = 0.03$ \\
						$r_{2, du} = 0.03$
					};
					\node (n2dd) at (6,  -2.5) [draw,  rectangle,  align=center] {
						$r_{2, dd} = 0.01$
					};
					
					% Labels at the top
					\node at (0,  3.25) {$i=0$};
					\node at (3,  3.25) {$i=1$};
					\node at (6,  3.25) {$i=2$};
					
					% Paths (arrows can be added here if needed)
					\path[-] (n0) edge (n1u);
					\path[-] (n0) edge (n1d);
					\path[-] (n1u) edge (n2uu);
					\path[-] (n1u) edge (n2uddu);
					\path[-] (n1d) edge (n2uddu);
					\path[-] (n1d) edge (n2dd);
				\end{tikzpicture}
			\end{center}
			
			
			The probability of an “up” movement is $p = 40\%$,  and the risk-neutral probability $\omega$ is in the solution to HW5 (or recompute it for this homework). You also know the current value of a 2-period zero-coupon bond is $Z_{0}(2) = 0.94$.
			
			\begin{enumerate}
				\item[(a)] Compute the value of a 3\% Pass-Through MBS with maturity $i = 3$. The underlying pool has a coupon rate of $r_{m} = 3.469\%$,  principal value $N = 100$,  and maturity $i = 3$. Follow the steps in TN 5 (but recall the risk-neutral probability is not 0.5).
			\end{enumerate}
			
			
			\textbf{Solution: } The value of the coupon is:
			
			$$
			C = \sum_{i=1}^{3} \left( 1 + r_m \right)^i = 35.67228
			$$
			
			Therefore,  the principal outstanding,  interest payments,  and principal payments are as given in the next table:
			
			$$
			\begin{array}{cccc}
				\text{Year} & \text{Principal Outstanding} & \text{Interest Payment} & \text{Principal Payment} \\
				\hline
				0           & 100                          & 3.469                   & 32.20328                 \\
				1           & 67.79672                     & 2.351868                & 33.32042                 \\
				2           & 34.4763                      & 1.195983                & 34.4763                  \\
				3           & 0                            & 0                       & 0                        \\
			\end{array}
			$$
			
			We next compute the non-callable tree,  whose entries are the present values of future coupons $C$. The risk-neutral probability,  recall,  is $\pi^* = 0.596181$. We obtain: \\
			
			
			\begin{table}[h!]
				\centering
				\caption{Non Callable Tree $V_{ij}$}
				\begin{tabular}{c|ccc}
					Principal Outstanding & 100      & 67.79672 & 34.4763  \\
					\hline
					time $i$              & 0        & 1        & 2        \\
					\hline
					                      & 100.5722 & 67.14152 & 33.93253 \\
					                      &          & 69.17526 & 34.61801 \\
					                      &          &          & 35.31734 \\
				\end{tabular}
			\end{table}
			
			We can compute the call options by comparing the value from waiting $$C_{\text{Wait}, ij} = e^{-r_{ij} \Delta t} (\pi^* C_{i+1, j} + (1 - \pi^*) C_{i+1, j+1})$$ and the value from exercising $$C_{\text{Ex}, ij} = V_{ij} - \text{OP}_i$$ where $V_{ij}$ is the non-callable tree,  and $\text{OP}_i$ is the outstanding principal (which depends only on $i$).
			
			$$
			\begin{array}{cccc}
				&\text{Call Option}\\
				\hline
				0.57204 & 0.05498  & 0        \\
				        & 1.378546 & 0.141708 \\
				        &          & 0.841038 \\
			\end{array}
			$$
			
			The value of the mortgage is indeed close to 100: $V_0 - C_0 = 100.0002$. Exercise occurs at the following nodes,  indicated by “1”:
			
			\begin{center}
				\begin{tabular}{ccc}
					\toprule
					\multicolumn{3}{c}{\textbf{Exercise Times}} \\
					\midrule
					0 & 0 & 0 \\
					  & 1 & 1 \\
					  &   & 1 \\
					\bottomrule
				\end{tabular}
			\end{center}
			
			We can finally compute the value of a Pass-Through Security with interest rate $r = 3\%$.
			
			
			
			\begin{center}
				\begin{tabular}{cccccc}
					\toprule
					& \multicolumn{5}{c}{\textit{time} $i$} \\
					\cmidrule(lr){2-6}
					& 0 & 1 & 2 & 3 \\
					\midrule
					\textbf{Outstanding Principal}  & 100      & 67.79672 & 34.4763  &          &   \\
					\textbf{Principal Payment}      &          & 32.20328 & 33.32042 & 34.4763  &   \\
					\textbf{Interest Payment (3\%)} &          & 3        & 2.033901 & 1.034289 &   \\
					\midrule
					\multicolumn{6}{c}{\textbf{Pass Through Security}} \\
					\midrule
					                                & 99.31729 & 66.69294 & 33.77872 &          &   \\
					                                &          & 67.79672 & 34.4763  &          &   \\
					                                &          &          & 34.4763  &          &   \\
					\bottomrule
				\end{tabular}
			\end{center}
			
			
			
			Whenever node $(ij)$ corresponds to an exercise time,  then the value of PT equals the value of outstanding principal at $i$. Whenever it is not an exercise node,  then we use the usual formula:
			
			$$
			P^{\text{PT}}_{ij} = e^{-r_{ij} \Delta t} (\pi^* P^{\text{PT}}_{i+1, j} + (1 - \pi^*) P^{\text{PT}}_{i+1, j+1} + \text{CF}_{i+1})
			$$
			
			where:
			
			$$
			\text{CF}_{i+1} = \text{Principal Payment}_{i+1} + \text{Interest Payment}_{i+1}
			$$
			
			\section*{Part III: Pricing MBS on Trees (CP)}
			
			\subsection*{Question 3}
			On November 1,  2014,  the Ginnie Mae Pass-Through security GNSF 4 was trading at 106.5781. This pass-through security was collateralized by a pool of mortgages with a weighted average coupon (WAC) = 4.492\%,  and a weighted average maturity (WAM) = 311 (months). As a junior analyst at the JCH Investment Group,  you are examining the value of the GNSF 4 and trying to assess whether this price is in line with current interest rates and option prices.
			
			You decide to use caps and floors to assess whether all of the interest rate optionality implicit in mortgage backed securities is taken into account in the current price of MBS. You decide to proceed as follows:
			
			\begin{enumerate}
				\item Compute Forward Volatilities from Cap Volatility Quotes
				      \begin{itemize}
				      	\item[(i)] Compute the zero-coupon [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve implicit in the swap curve,  as usual (Note: This part is automatically done by the guide codes available on Canvas);
				      	\item \begin{figure}[H]
				      	      \centering
				      	      \includegraphics[width=0.8\textwidth]{hw7-1.png}
				      	      \caption{[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and Forward Curves}
				      	\end{figure}
				      	\item \textbf{Solution: } The software was set up to compute both the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve from the swap data and the forward volatilities from the available cap volatilities. Figure 42 plots the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve and the Forward Curve,  quarterly compounded. \\
				      	\item[(ii)] Compute the forward volatilities,  also up to maturity of 30 years. Cap volatility quotes are available up to 30-years as well (Note: This part is automatically done by the guide code).
				      	\item[(iii)] Plot the forward and the flat volatilities. Comment on your findings. Discuss. Provide an intuition about the relation between forward and flat volatilities.
				      	      \begin{figure}[H]
				      	      	\centering
				      	      	\includegraphics[width=0.8\textwidth]{hw7-2.png}
				      	      	\caption{Forward and Flat Volatilities}
				      	      \end{figure}
				      	      
				      	       
				      	      
				      	\item \textbf{Solution: } Figure 43 plots the forward and flat volatility. As it can be seen,  the data are rather sparse,  and so interpolation methods are required. Moreover,  we can also see a couple of “humps” in the volatility,  around maturity of 7 years and 10 years. These humps may be artificial data errors,  such as stale quotes. The impact on the flat volatility is not that big,  but the impact on the forward volatilities – those that need to be entered in the binomial tree – is substantial. The reason is that the flat volatility can be thought of as an average of forward volatilities. It follows that forward volatilities are sort of marginal values of the flat volatilities. Thus,  little variation of an average (flat vol) implies large variation of the marginal value (forward volatility),  as it is apparent from the plot. Some smoothing of the data in this case would be warranted,  to eliminate the noise in the data.\\
				      	      
				      	      
				      	      
				      \end{itemize}
				\item Fit the BDT model to the discount curve and forward volatilities. Use the algorithm in TN 4 to fit the Black-Derman-Toy model (Note: automatically done by the guides,  once fitted [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curves and forward volatilities are carried over. Note that we fit the model at quarterly intervals instead of monthly intervals to keep the computational exercises simpler). \\
				       
				      
				      \begin{itemize}
				      	\begin{table}[h!]
				      		\centering
				      		\caption{Table 1: BDT Tree (First 10 Steps)}
				      		\begin{tabular}{c|*{10}{c}}
				      			\hline
				      			  & 0      & 1      & 2      & 3      & 4      & 5      & 6      & 7       & 8       & 9      \\
				      			\hline
				      			0 & 0.2325 & 0.5547 & 0.6716 & 0.8328 & 1.9113 & 4.047  & 7.1525 & 10.5522 & 13.1973 & 15.35  \\
				      			1 & 0      & 0.2787 & 0.3374 & 0.4214 & 0.9822 & 2.1204 & 3.8172 & 5.8239  & 7.6334  & 9.3127 \\
				      			2 & 0      & 0      & 0.1695 & 0.2132 & 0.5048 & 1.1109 & 2.0372 & 3.2143  & 4.4152  & 5.65   \\
				      			3 & 0      & 0      & 0      & 0.1079 & 0.2594 & 0.5821 & 1.0872 & 1.774   & 2.5538  & 3.4278 \\
				      			4 & 0      & 0      & 0      & 0      & 0.1333 & 0.305  & 0.5802 & 0.9791  & 1.4771  & 2.0796 \\
				      			5 & 0      & 0      & 0      & 0      & 0      & 0.1598 & 0.3097 & 0.5404  & 0.8544  & 1.2617 \\
				      			6 & 0      & 0      & 0      & 0      & 0      & 0      & 0.1653 & 0.2983  & 0.4942  & 0.7655 \\
				      			7 & 0      & 0      & 0      & 0      & 0      & 0      & 0      & 0.1646  & 0.2858  & 0.4644 \\
				      			8 & 0      & 0      & 0      & 0      & 0      & 0      & 0      & 0       & 0.1653  & 0.2818 \\
				      			9 & 0      & 0      & 0      & 0      & 0      & 0      & 0      & 0       & 0       & 0.1709 \\
				      			\hline
				      		\end{tabular}
				      	\end{table}
				      	
				      	
				      	
				      	\item \textbf{Solution: } Next step is to fit the BDT model. Both the Matlab code and Excel spreadsheet guides were set up to do this automatically. The algorithm is described in Teaching Notes 5,  but essentially,  the methodology ensures that the tree is consistent with the current yield curve and the option implied,  percent volatilities obtained above. Because the coupons will be paid monthly,  we would need to have the binomial tree be calibrated at the monthly frequency,  that is,  $\Delta t = 1/12$. While this could be done easily in the code,  it adds one more step (interpolation of zero-coupon and implied volatilities at the monthly horizon) and it adds quite a bit of computation time. We therefore keep the assumption $\Delta t = 0.25$,  for simplicity. Table 1 contains the results of the binomial tree. The BDT model fits well the current zero coupon curve,  as shown in Figure 44.
				      	\item How does this tree price the original caps? As it can be seen from Figure 4 the model does not do much of a good job on this dimension,  especially at the long horizon. The convergence of $\sigma_i$ as becoming the volatilities for the binomial tree from the Market model is really a convergence result at the high frequency,  and quarterly observations are not sufficient.
				      	      
				      	      \begin{figure}[H]
				      	      	\centering
				      	      	\includegraphics[width=0.8 \textwidth]{hw7-3.png}
				      	      	\caption{Tree implied discount function versus [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount}
				      	      \end{figure}
				      	      
				      	      \begin{figure}[H]
				      	      	\centering
				      	      	\includegraphics[width=0.8\textwidth]{hw7-4.png}
				      	      	\caption{Caps: Data versus Binomial Tree}
				      	      \end{figure} 
				      \end{itemize}
				      
				      
				        
				          
				          
				      
				          
				\item Use the BDT model to value GNSF4. To obtain the price of the pass-through security GNSF 4,  recall you must first do the following steps:
				      \begin{itemize}
				      	\item[(i.)] Compute the dollar coupon and the scheduled interest and principal payments. These calculations allow you to compute the scheduled outstanding principal balance. You can do these computations assuming outstanding principal of 100 (so that,  the price will be also in percentage of 100,  like the quoted value of the security). Note that the coupon must satisfy the equation
				      	      \[
				      	      	P_{0} = C \sum_{j=1}^{n} \left( \frac{1}{1 + r_{m} \Delta t} \right)^{j}
				      	      \]
				      	      where $n$ is the number of coupon payments and $\Delta t$ is the time step. A useful formula is the following: define $a = \left( \frac{1}{1 + r_{m} \Delta t} \right)$,  then we have the result that
				      	      \[
				      	      	\sum_{j=1}^{n} a^{j} = \frac{a - a^{n+1}}{1 - a}
				      	      \]
				      	      so that
				      	      \[
				      	      	C = P_{0} \frac{1 - a}{a - a^{n+1}}
				      	      \]
				      	      Given $C$,  you can compute the scheduled principal and interest payment and remaining principal over time.\\
				      	\item[(ii.)] Compute the value of the non-callable mortgage on the tree (i.e.,  present value of future coupons. This part is identical to previous cases,  except that there is no bullet capital payment at maturity). \\
				      	\item[(iii.)] Compute the value of the American call option from homeowner perspective,  and thus the optimal time of prepayment. (This part again is identical to the previous homework,  except that you must compare the present value of future payment at every node $(i,  j)$ to the outstanding principal at time $i$.) What is the value of the pool of mortgages as of time zero? (i.e.,  what is the present value of future payments that takes into account the American option?) \\
				      	\item[(iv.)] Use the GNSF coupon rate (4\%) and the optimal prepayment time computed in the previous point to compute the cash flows of the pass-through security and thus its value at time 0.
				      \end{itemize}
				\item Is the price that you obtained close to the quoted one? If not,  explain why not intuitively. What may be going on to explain the discrepancy,  if any?
			\end{enumerate}
			
			
			
			3. Use the BDT model to value GNSF4. We finally obtain the price of the pass-through security GNSF 4. We proceed as follows:
			\begin{enumerate}
				\item We compute the dollar coupon and the scheduled interest and principal payments. These calculations allow us to compute the scheduled outstanding principal balance. We do these computations assuming an outstanding principal of 100 (so that,  the price will be also in percentage of 100,  like the quoted value of the security).
				      
				      The coupon must satisfy the equation:
				      
				      $$
				      P_0 = C \sum_{j=1}^{n} \left( \frac{1}{1 + r_m \cdot \Delta t} \right)^j
				      $$
				      
				      where $n$ is the number of coupon payments and $\Delta t$ is the time step. A useful formula is the following: define $a = \left( \frac{1}{1 + r_m \cdot \Delta t} \right)$,  then we have the result that:
				      
				      $$
				      \sum_{j=1}^{n} a^j = \frac{a - a^{n+1}}{1 - a}
				      $$
				      
				      Given $C$,  you can compute the scheduled principal and interest payment and remaining principal over time:
				      
				      $$
				      \begin{aligned}
				      	  & \text{Interest paid in step } i:   & \text{IntPaid}(i) = \text{WAC} \cdot \Delta t \cdot \text{PP}(i);                                 \\
				      	  & \text{Scheduled principal:}        & \text{Pay}_{\text{scheduled}, si} = \text{Cs}_i - \text{Is}_i                                      \\
				      	  & \text{Principal prepayment:}       & \text{Pay}_{\text{prepaid}, si} = p^s_i \times (\text{Ls}_i - \text{Pay}_{\text{scheduled}, si})    \\
				      	  & \text{Outstanding principal:}      & \text{Ls}_{i+1} = \text{Ls}_i - \text{Pay}_{\text{scheduled}, si} - \text{Pay}_{\text{prepaid}, si} \\
				      	  & \text{Update of scheduled coupon:} & \text{Cs}_{i+1} = (1 - p^s_i) \times \text{Cs}_i                                                  \\
				      \end{aligned}
				      $$
				      
				      
				      
				      Figure 5 shows the scheduled interest payments and the scheduled principal payments (top panel) as well as the remaining balance (bottom panel). The latter is the “strike price” for the call option to prepay,  discussed next.
				      \begin{figure}[h!]
				      	\centering
				      	\includegraphics[width=0.8\textwidth]{hw7-5.png}
				      	\caption{Scheduled Interest and Principal Payments}
				      \end{figure}
				      
				      \begin{figure}[h!]
				      	\centering
				      	\includegraphics[width=0.8\textwidth]{hw7-6.png}
				      	\caption{Principal Balance}
				      \end{figure}
				      
				      \newpage
				\item We finally compute the value of the non-callable mortgage on the tree (i.e.,  the present value of future coupons. This part is identical to previous cases,  except that there is no bullet capital payment at maturity) as well as the call option. That is,  for every $(j,  i)$ we move backward by computing:
				      
				      $$
				      V_{\text{NoC}}(j, i) = \exp(-\text{ImTree}(j, i) \cdot \Delta t) \cdot (\text{MCoupon} + \frac{1}{2} \cdot (V_{\text{NoC}}(j, i+1) + V_{\text{NoC}}(j+1, i+1)));
				      $$
				      
				      and if $i > 1$ (assume exercise can only be after time 1):
				      
				      $$
				      \text{Call}(j, i) = \max(V_{\text{NoC}}(j, i) - \text{PP}(i),  \exp(-\text{ImTree}(j, i) \cdot \Delta t) \cdot (\frac{1}{2} \cdot (\text{Call}(j, i+1) + \text{Call}(j+1, i+1))));
				      $$
				      
				      while at $i = 1$:
				      
				      $$
				      \text{Call}(j) = \exp(-\text{ImTree}(j) \cdot \Delta t) \cdot (\frac{1}{2} \cdot (\text{Call}(j) + \text{Call}(j+1, 2)));
				      $$
				      
				      The value of the callable mortgage at every node is therefore:
				      
				      $$
				      V_{\text{C}}(j, i) = V_{\text{NoC}}(j, i) - \text{Call}(j, i);
				      $$
				      
				      We obtain the value of the pool of mortgages at time 0 equal to \$100.7935,  and without the prepayment option,  the value is \$119.3734.\\
				      
				      
				\item We finally price the GNSF 4. We use the new coupon rate (4\%) and the new optimal prepayment time computed in the previous point to compute the cash flows of the pass-through security and thus its value at time 0. We use a backward algorithm like before (and explained in TN5) with the additional issue that we need to know when exercise occurred. Exercise occurs when the value of the call option (already computed) equals the payoff from exercise,  that is,  when $\text{Call}(j,  i) = V_{\text{NoC}}(j,  i) - \text{PP}(i)$. Therefore,  at these times,  we have that the pass-through investors get the full principal back.\\
				      \begin{itemize}
				      	\item If at node $(j, i)$,  if $\text{Call}(j, i) = V_{\text{NoC}}(j, i) - \text{PP}(i)$,  then the value of the pass-through security equals the principal $V_{\text{PT}}(j, i) = \text{PP}(i)$.
				      	\item Otherwise,  there is no exercise and the cash flow of Pass-Through equals interest plus scheduled principal paid (all next period).
				      	      
				      	      The pass-through cash flow:
				      	      
				      	      $$
				      	      \text{CF}_{\text{PassThrough}}(i+1, 1) = \overline{r} \cdot \Delta t \cdot \text{PP}(i) + \text{PriPaid}(i);
				      	      $$
				      	      
				      	      the value of PT security given by backward computation:
				      	      
				      	      $$
				      	      V_{\text{PT}}(j, i) = \exp(-\text{ImTree}(j, i) \cdot \Delta t) \cdot (\text{CF}_{\text{PassThrough}}(i+1, 1) + \frac{1}{2} \cdot (V_{\text{PT}}(j, i+1) + V_{\text{PT}}(j+1, i+1))).
				      	      $$
				      \end{itemize}
				      
				      \begin{table}[h!]
				      	\centering
				      	\begin{tabular}{cccccccccc}
				      		\hline
				      		0        & 1       & 2       & 3       & 4       & 5       & 6       & 7       & 8       & 9       \\
				      		\hline
				      		100.1208 & 97.8462 & 93.9685 & 88.7171 & 82.4991 & 75.7702 & 68.8145 & 61.9621 & 55.3699 & 48.9792 \\
				      		0        & 99.4883 & 98.9708 & 96.5098 & 92.2775 & 86.9897 & 81.2369 & 75.1187 & 68.8343 & 62.4412 \\
				      		0        & 0       & 98.9708 & 98.4474 & 97.9183 & 94.9904 & 90.6372 & 85.8818 & 80.5740 & 74.8459 \\
				      		0        & 0       & 0       & 98.4474 & 97.9183 & 97.3831 & 96.8420 & 93.2870 & 89.5428 & 85.0567 \\
				      		0        & 0       & 0       & 0       & 97.9183 & 97.3831 & 96.8420 & 96.2948 & 94.8280 & 92.1418 \\
				      		0        & 0       & 0       & 0       & 0       & 97.3831 & 96.8420 & 96.2948 & 95.7414 & 95.1819 \\
				      		0        & 0       & 0       & 0       & 0       & 0       & 96.8420 & 96.2948 & 95.7414 & 95.1819 \\
				      		0        & 0       & 0       & 0       & 0       & 0       & 0       & 96.2948 & 95.7414 & 95.1819 \\
				      		0        & 0       & 0       & 0       & 0       & 0       & 0       & 0       & 95.7414 & 95.1819 \\
				      		0        & 0       & 0       & 0       & 0       & 0       & 0       & 0       & 0       & 95.1819 \\
				      		\hline
				      	\end{tabular}
				      	\caption{GNSF 4 (First 10 Steps)}
				      \end{table}
				      
				      We obtain that the value of GNSF 4 without the Option to Exercise is \$113.3296,  while the value of GNSF 4 with optimal exercise is \$100.1208.\\
				      
				      The price is not close to the traded price (\$106.5781). The reason is that optimal exercise makes all agents exercise too soon. However,  in reality,  many households cannot exercise the prepayment option. If the call option is not optimized,  then the value of the pass-through security increases. The question then is what probability of exercise should we give in the various nodes to obtain a value of the security that is close to the one in the data. We use Monte Carlo Simulations for that.
			\end{enumerate}
			
			\section*{Part IV: Use Monte Carlo Simulations on Trees (CP)}
			
			\subsection*{Question 4}
			From the tree estimated in Part III,  do the following:
			
			\begin{enumerate}
				\item Use Monte Carlo simulations on the tree to price a 30-year cap and a 30-year Asian cap with strike rate $r_{k} = 2\%$. (Note: This is identical to the example in Chapter 13 in the book.)
				        
				      \begin{itemize}     	
				      	\item \textbf{Solution: } Generically speaking,  for each simulated path $s$ of interest rates $[r_0,  r^s_1,  …,  r^s_{n-1}]$ we can associate its sequence of cash flows $[\text{CF}^s_1,  \text{CF}^s_2,  …,  \text{CF}^s_n]$ and then compute its present value:
				      	      
				      	      $$
				      	      V^s_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF}^s_i
				      	      $$
				      	      
				      	      Note that to discount a cash flow at time $i$ we need to use interest rates until $i-1$,  the step before (because the last rate $r^s_{i-1}$ is the discount from $i$ back to $i-1$).
				      	      
				      	      The value of the security is then:
				      	      
				      	      $$
				      	      \hat{V}_0 = \frac{1}{\text{NSim}} \sum_{s=1}^{\text{NSim}} V^s_0
				      	      $$
				      	      
				      	      We can also compute the standard errors by computing first the standard deviation of $V^s_0$ and dividing by the square root of the number of simulations $\text{NSim}$:
				      	      
				      	      $$
				      	      \text{st.error} = \frac{\text{St.Deviation}[V^1_0,  V^2_0,  …,  V^{\text{NSim}}_0]}{\sqrt{\text{NSim}}}
				      	      $$
				      	      
				      	      For instance,  in a Cap we have:
				      	      
				      	      $$
				      	      \text{CF}^s_i = \max(r^s_i - r_k,  0)
				      	      $$
				      	      
				      	      Note that this is not a plain vanilla cap but a Cap in Arrears,  as the interest rate at time $i$ is paid at time $i$ and not at $i+1$ (moreover,  we are simulating continuously compounded rates. In principle,  we should change $r^s_i$ into a quarterly compounded rate through the usual formula). With $\text{NSim} = 5000$,  the methodology above yields:
				      	      
				      	      $$
				      	      V^{\text{Cap}}_0 = 276.1099; \quad \text{st.error} = 3.2422
				      	      $$
				      	      
				      	      Still a pretty large standard error. We would need to increase the number of simulations to 100, 000 to start having some reasonably small standard error. \\
				      	      
				      	      
				      	      Once we know how to do MC simulations,  computing the value of an Asian Cap is straightforward. The only thing we have to change is the payoff,  which now is:
				      	      
				      	      $$
				      	      \text{CF}^s_i = \max(\text{average}[r_0,  r^s_1,  …,  r^s_i] - r_k,  0)
				      	      $$
				      	      
				      	      That’s it. No other changes needed. The same code yields:
				      	      
				      	      $$
				      	      V^{\text{AsianCap}}_0 = 116.5956; \quad \text{st.error} = 1.8092
				      	      $$
				      	      
				      	      Quite a smaller value: Asian options are often preferred to standard options because they cost much less,  although clearly,  there is more risk. For instance,  if the average is small due to a low period of interest rates and then interest rate suddenly increase,  the Asian Cap (or Caplet) may be out of the money,  while a regular Cap would actually be in-the-money,  implying that the Cap would be better able to hedge against sudden variation in interest rates. \\
				      	       
				      	      
				      \end{itemize} 
				\item Use Monte Carlo simulations and the prepayment function
				      \[
				      	p_{t} = c_{1} - \max(r_{m} - sp - r_{t},  c_{2})
				      \]
				      to do the following:
				      \begin{itemize}
				      	\item Compute the value of the pass-through,  interest-only and principal-only mortgage-backed securities discussed above. Note that both the guide files are already set up to do these calculations for given parameters of the prepayment function. Choose the parameters of the prepayment function to obtain a value of the PT security that is similar to the quoted one. (This can be done by trial and error).
				      	\item Vary the parameters of the prepayment functions and compute the values of IO and PO. Discuss your findings intuitively.
				      \end{itemize}
			\end{enumerate}
			
			
			\textbf{Solution:} Asian Cap Valuation
			Once we know how to do MC simulations,  computing the value of an Asian Cap is straightforward. The only thing we have to change is the payoff,  which now is:
			
			$$
			\text{CF}^s_i = \max(\text{average}[r_0,  r^s_1,  …,  r^s_i] - r_k,  0)
			$$
			
			That’s it. No other changes needed. The same code yields:
			
			$$
			V^{\text{AsianCap}}_0 = 116.5956; \quad \text{st.error} = 1.8092
			$$
			
			Quite a smaller value: Asian options are often preferred to standard options because they cost much less,  although clearly,  there is more risk. For instance,  if the average is small due to a low period of interest rates and then interest rate suddenly increase,  the Asian Cap (or Caplet) may be out of the money,  while a regular Cap would actually be in-the-money,  implying that the Cap would be better able to hedge against sudden variation in interest rates.
			
			4. \textbf{Solution:} Value of Mortgage-Backed Security through a Prepayment Function:
			
			The same methodology can be used to compute the value of Mortgage-Backed Security through a Prepayment Function. In this case,  the logic is to simulate paths of interest rates,  and for each path,  provide a probability $p_t$ that investors will prepay the mortgage (i.e.,  a fraction $p_t$ of investors prepay the mortgages).
			
			The prepayment function was simple:
			
			$$
			p_i = c_1 \max(r_m - s_p - r_i,  c_2)
			$$
			
			Given a sequence of interest rates $r^s_i$ and thus corresponding simulated $p^s_i$,  we can compute the full cash flow sequence as per TN 5,  page.
			
			We can compute sequentially the following items (now at quarterly frequency but this can be done at any frequency):
			
			$$
			\begin{aligned}
				  & \text{Mortgage interest payment:}  & \text{Is}_i = \frac{r_m}{4} \times \text{Ls}_i                                                    \\
				  & \text{Scheduled principal:}        & \text{Pay}_{\text{scheduled}, si} = \text{Cs}_i - \text{Is}_i                                      \\
				  & \text{Principal prepayment:}       & \text{Pay}_{\text{prepaid}, si} = p^s_i \times (\text{Ls}_i - \text{Pay}_{\text{scheduled}, si})    \\
				  & \text{Outstanding principal:}      & \text{Ls}_{i+1} = \text{Ls}_i - \text{Pay}_{\text{scheduled}, si} - \text{Pay}_{\text{prepaid}, si} \\
				  & \text{Update of scheduled coupon:} & \text{Cs}_{i+1} = (1 - p^s_i) \times \text{Cs}_i                                                  \\
			\end{aligned}
			$$
			
			Given the dynamics of $\text{Ls}_i$ from the simulations,  we can compute the path through future cash flows:
			
			$$
			\begin{aligned}
				  & \text{Pass-through interest payment:} & \text{IPT, s}_i = \frac{r_{\text{PT}}}{4} \times \text{Ls}_i                                        \\
				  & \text{Total cash flow:}               & \text{CF}^s_i = \text{IPT, i}_i + \text{Pay}_{\text{scheduled}, si} + \text{Pay}_{\text{prepaid}, si} \\
			\end{aligned}
			$$
			
			The price of the pass-through MBS in simulation $s$ is thus the same as for the general case:
			
			$$
			V^{\text{PT, s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF}^s_i
			$$
			
			Note that computing the value of IO and PO is immediate from above,  after we know the full amount of cash flows. The idea is simply to divide up the interest-only cash flows from the principal-only cash flows:
			
			$$
			\begin{aligned}
				  & \text{IO cash flow:} & \text{CF IO, s}_i = \text{IPT, i}_i                                                    \\
				  & \text{PO cash flow:} & \text{CF PO, s}_i = \text{Pay}_{\text{scheduled}, si} + \text{Pay}_{\text{prepaid}, si} \\
			\end{aligned}
			$$
			
			and the prices for each simulated rate path are:
			
			$$
			\begin{aligned}
				  & V^{\text{IO, s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF IO, s}_i \\
				  & V^{\text{PO, s}}_0 = \sum_{i=0}^{n-1} e^{-\sum_{j=0}^{i-1} r^s_j \Delta t} \text{CF PO, s}_i \\
			\end{aligned}
			$$
			The final values of the pass-through and the IO and PO securities are given by the average of these simulated values,  as discussed earlier. \\
			Given $r_m = 0.04492$,  we use the parameters $c_1 = 5$,  $c_2 = 0$,  and $s_p = 0.015$,  and we obtain the value of GNSF 4 equal to $\hat{V}^{\text{GNSF4}}_0 = 106.1751$ with standard errors $\text{s.e.} = 0.1747$. This is not too far from the traded price,  actually. \\Note that the parameters $c_1$,  $c_2$,  and $s_p$ determine a Risk Neutral probability $p^*_i$ of prepayment,  as we obtained this value not from an estimate of the true prepayment frequency of homeowners,  but to match the price of the PT itself. That is,  there could be a risk premium component in this probability as well.
			These are given by $\hat{V}^{\text{IO}}_0 = 26.1264$ and $\hat{V}^{\text{PO}}_0 = 80.0487$. Clearly,  because the sum of the cash flows flowing to PO and IO equals the total cash flows to GNSF 4,  the sum of the prices of IO and PO must be the same as the price of GNSF 4.
			
			\end{enumerate}
			\end{itemize}
\end{document}
```