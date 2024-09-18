---
title: Fixed Income HW Assignments
---
# Fixed Income HW Assignments
### HW 1

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{March 18, 2024}
\begin{document}
\maketitle

\section*{Homework 1}
\textbf{Due before 6pm on Monday March 25 before 6pm central time.}

You have been retained by the JCH Fixed Income Group to provide a forecast about future short term interest rates, namely, the 3 month t-bill rate. You decide to use two sources of data: historical interest rate data and current forward rates. The data necessary for this forecasting exercise are contained in the Excel file DTB3 2024.XLS, which you can find on Canvas. This dataset contains daily observations of the 3 month t-bill rate from April 4, 1954 until March 14, 2024 (sheet “DTB3”) as well as the Treasury Strip Price on March 08, 2024 (sheet “Strip Prices”). You are to write a report including all relevant information and computations, and provide a forecast for $n$ horizons ranging between 6 months and 5 years. Please, follow the steps below.

\begin{quote}
\textbf{Note 1:} For each section below, there are questions that require a “pencil and paper” (PP) answer, and questions that require actual computations using data and computer programs (CP). You are supposed to do both. For the computer-based questions you may use any software you like. There are guides, however, for Matlab, Excel, and Python. You are, however, not required to use any of these pieces of code!

\textbf{Note 2:} Some code you might use:
\begin{itemize}
    \item For Matlab users, we made available the Matlab code “HW1 2024 Guide.m”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example, you will need to fill in some formulas and/or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.
    \item For Excel users, we made available the spreadsheet “HW1 2024 Guide.xlsm”. This Excel spreadsheet contains instructions to use the XLSTAT functions answer the CP questions below. Inputs though are required to complete some formulas or to produce some of the results. The Excel spreadsheet is supposed to facilitate the computations for the homework.
    \item For Python users, we made available the Python code “HW1 2024 Guide.py”. This code provides a start to the solutions. You will need to fill in the parts of the code that are missing. For example, you will need to fill in some formulas and/or inputs. The code won’t run until you fix those spots. Look for the spots marked by “??”.
\end{itemize}
\end{quote}

\subsection*{Estimation and Forecast}
\begin{enumerate}
    \item Let us denote by $r_{t}$ the Bond Equivalent Yield (TN 1, page 22) on day $t$.
    \begin{description}
        \item[(PP)] Below are Treasury Bill quotes from the Wall Street Journal from a few years ago. Please, explain why the rates in “Ask” differ from those in “Asked Yield”. Use the quoted rates with maturity 6/11/2020 and 3/25/2021 to explain the point in detail (i.e. show that the “Ask” quotes indeed imply “Asked yield”.)
        \item[(CP)] The data in DTB3 2024.XLS are quoted on a discount basis $d_{t}$. Please determine a time series of BEY and provide the appropriate plot (note that here $n = 91$).
    \end{description}
    \item The AR(1) process for interest rates is the following:
    \[
    r_{t+1} = \omega + \epsilon r_{t} + \vartheta_{t+1}
    \]
    where $\vartheta_{t+1} \sim N(0, \varphi^2)$
    \begin{description}
        \item[(PP)] Show OLS based formulas for determining $\hat{\omega}$, $\hat{\epsilon}$ and $\varphi$.
        \item[(PP)] Demonstrate why and how “mean reversion” of interest rates can be modeled with AR(1) process.
        \item[(CP)] Estimate the AR(1) process for interest rates.
    \end{description}
    \item Let $\hat{\omega}$, $\hat{\epsilon}$ and $\varphi$ be the estimated parameters from (1). Use (1) together with the most recent interest rate available on DTB3.XLS, call it $r_{\text{TODAY}}$, to make a forecast of future interest rates $r_{\text{TODAY}+T}$.
    \begin{description}
        \item[(PP)] Carry the daily interest rate forecast for the following three days, i.e. calculate $r_{\text{TODAY}+1\text{day}}$, $r_{\text{TODAY}+2\text{days}}$, …, $r_{\text{TODAY}+3\text{days}}$. Show all work, including all the formulas used.
        \item[(CP)] Forecast interest rates for horizons $T = 6$ months, and 1, 2, …, 5 years (a plot would suffice). Explain how you make the forecasts. (Tip: When you make the forecasts, assume there are 252 (business) days in one year).
    \end{description}
    \item The Treasury Strip Prices are contained in DTB3 2024.xls.
    \begin{description}
        \item[(PP)] Compute both the current yield curve and forward rates for the first three maturities. Show all work, including all the formulas used. Discuss what a “forward rate” is.
        \item[(CP)] Compute both the current yield curve and forward rates for all maturities and compare the forecasts of future interest rates that are implicit in the forward rates to those obtained in point (3) above. Plot the forecasts and the corresponding forward rates. Discuss your findings.
    \end{description}
\end{enumerate}

\end{document}
```

### HW 2

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{March 25, 2024}
\begin{document}
\maketitle

\section*{Homework 2}
\textbf{Due at the beginning of class 3}

This homework is on the pricing and risk assessment of Leveraged Inverse Floaters. Please, write the solution to the homework as a clean report addressed to the principals of the fixed income group at JCH Fixed Income Group, LLP. The principals of JCH Fixed Income Group are very demanding, so make sure to describe exactly the source of your results. However, the report must be clean and concise. An appendix to the report may contain any additional material.

The data for this homework are collected in the data file HW2 Data.xls available on canvas.

\begin{quote}
\textbf{Note 1:} For each section below, there are questions that require pencil and paper (PP) answers, and questions that require actual computation using data and computer programs (CP). You are to do both.

\textbf{Note 2:} As with previous homework assignments there are “guides” for doing the homework in Excel, Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides, but use of one of them is recommended.
\end{quote}

\subsection*{Leverage Inverse Floaters}
\textbf{Recommended Reading: Veronesi’s Book. Chapter 2 (esp. 2.8); Chapter 3 (esp. 3.7)}

In an environment of low interest rates, inverse floaters are popular investment vehicles that allow a fund manager to obtain a higher yield, by betting on the direction of the movement in interest rates. In particular, consider the following term sheet for a Leveraged Inverse Floater.

\subsubsection*{Leveraged Inverse Floater Term Sheet}
\begin{itemize}
    \item Date: February 17, 2009
    \item Maturity: February 17, 2014 (5 year)
    \item Payments Frequency: Semi-annual
    \item Interest Payment: Base Interest Rate minus 2 times Reference Interest Rate
    \item Base Interest Rate: 10\%
    \item Reference Interest Rate: 6 month T-bill rate with standard 6 month lag
\end{itemize}

\begin{enumerate}
    \item \textbf{Bootstrap methodology}
    \begin{description}
        \item[(PP)] Describe bootstrap methodology for extracting the term structure of interest rates.
        \item[(PP)] The AllBondQuotes 20090217 tab of the data file provided contains Treasury Bills, Notes and Bonds on February 17, 2009. Use these data to manually compute the spot rates for maturity 0.5, 1, and 1.5. Show your work. TIP: Maturity 0.4999 can be considered 0.5, and so on.
        \item[(CP)] The AllBondQuotes 20090217 tab of the data file provided contains Treasury Bills, Notes and Bonds on February 17, 2009.
        \begin{itemize}
            \item Use these data to bootstrap the term structure of interest rates for as long a maturity as possible, and obtain the discount function. In particular, you will see that for several maturities, you will have a choice of which bonds to use in your bootstrap. Compute two discount curves, (a) one that uses the most recently issued bonds (as of 02/19/2009), and (b) one that uses the oldest bonds. Discuss the differences. Make sure to report what data you actually use for the bootstrap as well as any approximation you have to carry out. [Note: The bonds with highest coupon are the oldest ones].
            \item Plot the resulting term structure of interest rates (i.e. the spot rate function) for both cases (a) and (b). Discuss the difference and any other visible feature of the yield curve.
        \end{itemize}
    \end{description}
    
    \item \textbf{Leverage Inverse Floater pricing}
    \begin{description}
        \item[(PP)] Describe the cash flows of the Leverage Inverse Floater provided in Term Sheet. How can we decompose the Leverage Inverse Floater into simpler securities?
        \item[(PP)] Discuss intuitively the benefits from investing in the Leverage Inverse Floaters as compared to an existing, traded, regular fixed rate note with the same maturity.
        \item[(CP)] Use the results in Point 1 to compute the price of Leverage Inverse Floater described in the Term Sheet (which term structure do you use? Remember you have to come up with one price and not two. Explain your choice).
    \end{description}

    \item \textbf{Duration and convexity}
    \begin{description}
        \item[(PP)] Describe the duration of a fixed income security and how it is calculated in general. How is the duration of the Leverage Inverse Floater calculated? What are its components?
        \item[(CP)] Calculate the duration of the Leverage Inverse Floater. Plot the value of the Leverage Inverse Floater against a hypothetical parallel shift in the term structure of interest rates.
        \item[(PP)] Discuss your finding regarding the duration of the Leverage Inverse Floater and discuss the risk that an investor may face by investing in the Leverage Inverse Floater. In particular, compare the duration (and risk) of the Leverage Inverse Floater to that of a regular existing traded fixed-rate note with the same maturity.
        \item[(PP)] Describe the convexity of a fixed income security and how it is calculated in general. How is the convexity of the Leverage Inverse Floater calculated? What are its components?
        \item[(CP)] What is the value of the convexity of the Leverage Inverse Floater? Discuss.
    \end{description}

    \item \textbf{THIS IS AN OPTIONAL QUESTION FOR THOSE THAT ARE INTERESTED! Value-at-Risk calculations}
    \begin{description}
        \item[(PP)] Describe the Value-at-Risk concept and how it can be applied to fixed income securities, including Leverage Inverse Floaters.
        \item[(CP)] Use the Duration and Convexity computed in Part 3 along with the data in DBT6 tab of the data file provided to assess the risk of the Leverage Inverse Floater. In particular, compute the 1-day, 95\% and 99\% Value-at-Risk of the Leverage Inverse Floater, by using both the “historical approach,” and the “normal distribution.” Compare the result Value-at-Risk with the one of a regular 5-year bond. Comment. Tip: See Veronesi’s Book, Ch. 3.2.8 and 3.8. In particular, the 100-$\omega$\% Value-at-Risk is the value VaR such that $Pr(L < VaR) = \omega$ where $L$ is the portfolio dollar loss over one day.
    \end{description}
\end{enumerate}

\end{document}
```

### HW 3

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{}
\begin{document}
\maketitle

\section*{Homework 3}
\textbf{Due at the beginning of Class 4}

\begin{quote}
\textbf{Note 1:} For each section below, there are questions that require a “pencil and paper” (PP) answer, and questions that require actual computations using data and computer programs (CP). You are supposed to do both.

\textbf{Note 2:} As with Homework \#1 there are “guides” for doing the homework in Excel, Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides, but use of one of them is recommended.
\end{quote}

\subsection*{Part I: Duration Hedging and Factor Neutrality}
Consider the Leverage Inverse Floater discussed in HW 2. The data set FBYields 2024 v2.xlsx contains monthly data on continuously compounded zero coupon yields (1 month - 5 years) from June 1952 to December 2023.

\begin{enumerate}
    \item[(PP)] Describe the Principal Component methodology, and what “Level,” “Slope,” and “Curvature” mean? Are these assumptions or results of the analysis? Why the names?
    \item[(CP)] Use this zero-coupon bond term structure to compute the value of the LIF on March 31, 2009 as well as on April 30, 2009. Compare the change in value of LIF with the one predicted by the duration computation performed in HW 2 (for the latter computation, you have to compute the average change in the term structure over the two dates (why?)). Discuss your results, also in view of the actual change of the term structure of interest rates over the two dates. (Tip: It is OK for this exercise to keep the maturity of LIF to 5 years on both dates. Tip 2: It helps to actually plot the term structures on the dates on the same graph.)
    \item[(CP)] Use the time series of the data to compute the Principal Component betas for level and slope. Plot the beta coefficients as well as the level and slope factors (Tip: See the Guide files for Matlab or Excel).
    \item[(CP)] Compute the factor durations against level and slope. (Tip: This is a small modification from the solution to HW 2)
    \item[(CP)] Compare the variation in LIF (in point (A)) with the one predicted from the factor duration in point (B). Discuss. (To compute the actual change in Factor 1 (level) and 2 (slope), you just have to multiply the betas in point (B) by the actual change in the yields over the two days.)
\end{enumerate}

\subsection*{Part II: Predicting Zero-Coupon Bond Returns}
\textbf{Recommended readings:}
\begin{itemize}
    \item Book. Chapter 7.3
    \item Cochrane and Piazzesi (2005) “Bond Risk Premia” American Economic Review. \\
    \url{http://www.stanford.edu/~piazzesi/cp.pdf}
\end{itemize}

\begin{enumerate}
    \item[(PP)] Explain the logic behind Fama-Bliss regressions. According to the Expectation Hypothesis, what should be the regression coefficients of the regression?
    \item[(CP)] Use the data FBYields 2024 v2.xlsx and run Fama-Bliss and Cochrane-Piazzesi annual predictive regressions of zero coupon bonds with time to maturity $T = 2, 3, 4, 5$. Please, only use annual data for this exercise, so as to avoid econometric problems (overlapping samples).
    \begin{description}
        \item[(CP)] Plot the expected excess return for the 5-year bond over time using both Fama-Bliss and Cochrane-Piazzesi methodologies. As of the last day in the sample (December 2023), what is the 1-year forecast of the 5-year bond excess return? Compare the difference in prediction about the 2022-2023 excess bond returns between Fama and Bliss and Cochrane and Piazzesi.
        \item[(PP)] What do your results imply about time varying risk premia? Interpret in light of your knowledge of macro-economic events (inflation, growth, etc).
        \item[(PP)] How well can you predict future bond returns? Do your results differ from those illustrated in the teaching notes? Discuss.
    \end{description}
\end{enumerate}

\end{document}
```

### HW 4

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{}
\begin{document}
\maketitle

\section*{Homework 4}
\textbf{Due at the beginning of Class 5}

\begin{quote}
\textbf{Note 1:} For each section below, there are questions that require a “pencil and paper” (PP) answer, and questions that require actual computations using data and computer programs (CP). You are supposed to do both.

\textbf{Note 2:} As with Homework \#1 there are “guides” for doing the homework in Excel, Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides, but use of one of them is recommended.
\end{quote}

\subsection*{Part I: Real and Nominal Bonds}
The dataset “DataTIPS.xlsx” contains data on nominal bonds and Treasury Inflation Protected Securities (TIPS) on Jan 15, 2013.

\begin{enumerate}
    \item[(PP)] Write down the relation between nominal rates and real rates. Interpret each term economically.
    \item[(PP)] What does a negative real rate imply? Provide an intuition about negative real rates using more than one potential explanation.
    \item[(PP)] In the first quarter of 2013, the median forecast of professional forecasters about the average three-month rate for the next 10 years was 2.4\%. Compare this average with your estimated nominal 10-year rate. Is it higher? Is it lower? Explain the difference, if any, in economic terms.
    \item[(CP)] Fit the Nelson Siegel model to the TIPS on Jan 15, 2013. Plot the resulting term structure of real rates. Interpret in light of your answer to point 2.
    \item[(CP)] Fit the Nelson Siegel model to the nominal bonds. Plot the resulting term structure of nominal rates. Interpret in light of your answer to point 3.
    \item[(CP)] Compute breakeven inflation rate, that is, those rate $\omega(\epsilon)$ such that $r_{\text{nominal}}(0, \epsilon) = r_{\text{real}}(0, \epsilon) + \omega(\epsilon)$. Interpret your results. What does the break-even rate really capture?
\end{enumerate}

\subsection*{Part II: Swap Spread Trades}
\textbf{Recommended readings:}
\begin{itemize}
    \item Book. Chapter 5.
    \item Harvard Business School Case: “Fixed Income Arbitrage in a Financial Crisis (C): TED Spread and Swap Spread in November 2008”
    \item Duarte, Longstaff and Yu, “Risk and Return in Fixed-Income Arbitrage: Nickels in Front of a Steamroller?” Review of Financial Studies, 2006. \\
    \url{http://www.owlnet.rice.edu/~jd10/nickelsRFS.pdf}
\end{itemize}

Today is February 17, 2009 and you are evaluating the Swap / Treasury curve. You decide to set up 100 million swap spread trade on the thirty-year T-Bond / Swap. Daily quote on the 30-year bond, maturing on February 15 2039, are contained in spreadsheet Daily Bond Swaps in HW4 Data.xls. The spreadsheet also contains daily data on the 30-year swap, three month LIBOR and three month Repo rate. You have access to some past data, such as the ones in the H15 Swap.txt, which contains daily data on swap rates, LIBOR and Repo, but for a longer sample, as well as Treasury constant maturity rates. (All these data are also collected in the Excel guide 35130 HW4 2022 Guide.xlsx for Excel users).

\begin{enumerate}
    \item[(PP)] Look at the data and decide which direction to set up a swap spread trade. Is there an arbitrage? If so, why do you think there is one? Discuss.
    \item[(PP)] What do you do? Describe the working of the swap spread trade. How do you take positions in the Treasury Bond? What about the swap?
    \item[(CP)] Consider now one quarter after the initiation of the trade (May 18, 2009). Suppose JCH Capital Management needs to liquidate the position immediately, due to large unexpected redemptions from investors. What is the value of the swap-spread trade positions? In particular, the trade has two parts: the T-Bond trade and the Swap trade. Compute the fair valuation of the two parts as follows:
    \begin{itemize}
        \item[(A)] The value of the T-bond part is just the value of the bond, multiplied by its position. You can read it right from the data. Recall though the overall position of the bond trade.
        \item[(B)] The value of the swap part should use the standard valuation formula of swaps, as a fixed rate bond minus a floating rate bond (see Teaching Note 4, page 11, Eq.(8)). The floating rate leg should be “easy” (what is the value of floating rate bond at reset dates?). For the fixed leg, proceed as follows:
        \begin{itemize}
            \item Determine what is the appropriate “coupon rate” for the fixed leg of the swap in the valuation.
            \item Determine how many “coupon” periods there are left.
            \item To compute the present value of future coupons, you need an appropriate discount function $Z(T)$. Extract the LIBOR curve from current swap rates as of May 18, 2009, using the procedure on TN3, page 11. Because for maturity less than one year there are no swap quotes, you can use LIBOR rates themselves in the computation.
            \begin{itemize}
                \item Note that you need an interpolation of maturities, as data only come on fixed maturities, but you need specific quarters to compute the present value.
            \end{itemize}
            \item Plot the estimated zero-coupon LIBOR curve.
            \item Use the estimated $Z(T)$ to compute the value of the fixed leg of the swap.
        \end{itemize}
    \item[(C)] Given your results in [A] and [B], did the trade (so far) make money or lose money? Can you reconcile it with your answer to point 1? What happened to the swap spread between Feb 9 and May 18, 2009?
    \end{itemize}
    \item[(CP)] (Optional: No Grade Given. No hint in the code.) Follow the trading strategy cash flows. What is the sequence of cash flows? Consider only quarterly frequency.
    \item[(CP)] (Optional: No Grade Given. No hint in the code.) Follow also the value of the trade over time. Consider only quarterly frequency.
\end{enumerate}

\end{document}
```

### HW 5

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{}
\begin{document}
\maketitle

\section*{Homework 5}
\textbf{Due at the beginning of Class 6}

\begin{quote}
\textbf{Note:} As with past homework assignments there are “guides” for doing the homework in Excel, Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides, but use of one of them is recommended.
\end{quote}

\subsection*{Part I: Using Black’s Formula for Caps, Floors, and Swaptions}
\begin{enumerate}
    \item[(CP)] Attached are two data screens from Bloomberg. Figure ?? quotes out to 30 years. In using this data use the mid-point quotes. The second, figure ??, provides data on implied flat Black forward-volatility for Caps and Floors and implied Black volatility for Swaptions. This screen also provides the 1-month LIBOR rate needed for the exercise. (There may be some slight inconsistency in the quotes in the figures because they were not extracted from Bloomberg at exactly the same time.) Compute:
    \begin{itemize}
        \item The dollar value of a two-year Cap (quoted caps are at-the-money, and therefore the strike rate equals the current swap rate). The only thing you need to enter in the code is the proper volatility and swap rates (along with 3-month LIBOR) to produce this price and the swaption price below.
        \item The dollar value of a 1-year swaption to enter into a 5-year swap.
    \end{itemize}
    \item[(PP)] In the exercise above, make sure to illustrate the option-pricing formulas used for (a) the first caplet in the cap (i.e., the one with 6-months to maturity); and (b) the swaption. Show your work. (Look at the code and match it to the notation from the class notes).
\end{enumerate}

\subsection*{Part II: Interest Rate Trees}
\begin{enumerate}
    \item[(PP)] Consider the following interest rate tree, where each time interval is 1-year (that is, $\Delta t = 1$).

    \begin{align*}
    &i = 0 && i = 1 && i = 2 \\
    &r_{2,uu} = 0.05 && && \\
    &r_{1,u} = 0.04 && r_{2,ud} = 0.03 && r_{2,du} = 0.03 \\
    &r_{0} = 0.03 && r_{1,d} = 0.02 && r_{2,dd} = 0.01 \\
    \end{align*}

    The probability of an “up” movement can either be $p = 40\%$ or $p = 70\%$. You also know the current value of a 2-period zero coupon bond is $Z_{0}(2) = 0.94$.

    \begin{enumerate}
        \item[(a)] Find the risk neutral probability $\pi^{*}$ (see TN4, page 21) at time 0.
        \item[(b)] You have to compute the value of a one-year call option on the interest rate $r_{1}$ at the strike rate $r_{K} = 3\%$ and notional $N = 1000$, that is, with payoff $payoff_{1u} = 1000 \cdot \max(r_{1u} - r_{K}, 0)$ in the “up” node; and $payoff_{1d} = 1000 \cdot \max(r_{1d} - r_{K}, 0)$ in the “down” node. Use the risk-neutral probability $\pi^{*}$ in the previous point to compute the price for this option.
        \item[(c)] Does it matter which probability $p$ is the true one (i.e., whether $p = 40\%$ or $p = 70\%$)? Why?
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
                so that $P_{1,u}$ and $P_{1,d}$ correspond to the total value of an investor in the coupon bond would receive (remember that such an investor is entitled to the coupon at time $i = 1$ in both nodes).
                \item Check that the replicating portfolio “replicates”, that is, that indeed $P_{1,u}$ and $P_{1,d}$ corresponds to the payoffs of the coupon bond.
            \end{itemize}
        \end{itemize}
    \end{enumerate}
\end{enumerate}

\end{document}
```

### HW 6

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{}
\begin{document}
\maketitle

\section*{Homework 6}
\textbf{Due at the beginning of Class 8}

\begin{quote}
\textbf{Note:} As with past homeworks there are “guides” for doing the homework in Excel, Matlab and Python. Each code provides partial solutions to the questions. To make the code run you are required to complete some formulas or to produce some of the results yourself. You are not required to use any of the guides, but use of one of them is recommended.
\end{quote}

\subsection*{Pricing the Freddie Mac 6\% Callable Bond}
Attached below you will find the prospectus of Freddie Mac 6\%, 20-year callable bond, issued on June 7, 2007. Your task in this homework is to obtain its fair valuation, using both the Ho-Lee model and the Simple BDT model. Proceed as follows:

\begin{enumerate}
    \item[(CP)] Use the data in ”HW6 Data Bonds.xls” and extract the discount curve $Z(0, T)$ from the Treasuries using Nelson-Siegel model.
    \item[(CP)] Build the Ho-Lee tree, given by
    \[
    r_{i+1,j} = r_{i,j} + \omega(i) + \epsilon \cdot \vartheta_{i+1}
    \]
    where $\epsilon$ is the volatility of interest rates, $\omega(i)$ are chosen to fit the term structure of interest rates exactly, and
    \[
    \vartheta(i) = 
    \begin{cases} 
    +1 & \text{with probability } \frac{1}{2} \\
    -1 & \text{with probability } \frac{1}{2}
    \end{cases}
    \]
    Let $r_{0}$ match the first zero-coupon bond $Z_{0}(0.5)$ from Nelson-Siegel model. The methodology to fit the model to the term structure of interest rates is explained in TN4. Both the Matlab file and the guide spreadsheet that are available contain the routine to build it. You need a value of $\epsilon$. Use the data on six-month rates available in the dataset (HW6 FRB H15.csv) to estimate $\epsilon$ (this can be done by taking the standard deviation of first differences in interest rates, over six-month periods, which is one time step). Remember to annualize the volatility estimates, as $\epsilon$ in Ho-Lee and BDT are annualized.
    \item[(CP)] After fitting the tree to the data, please plot the zero-coupon bond yields from the tree and from the original zero-coupon bonds $Z(T)$ obtained from Nelson and Siegel (and used as inputs for the tree). Are they the same? Show also the first 10 time-steps of the interest rate tree (table 10 x 10).
    \item[(CP)] Use the tree to price the Freddie Mac Callable bond. Recall from the teaching notes that a callable bond can be decomposed in a non-callable bond minus a call option. Therefore:
    \begin{itemize}
        \item Obtain the price of the non-callable bond
        \item Obtain the price of the call option written on the non-callable bond
        \item Obtain the price of the callable bond as the difference
    \end{itemize}
    Please, make sure to incorporate the fact that the callable bond becomes callable only after the First-Call-Date.
    \item[(CP)] Show the first 10 nodes of the non-callable bond, the option to call, and the callable security.
    \item[(CP)] Plot the price of the non-callable and of the callable security against interest rates at call time, as well as 1, 2, 3 semesters before. How does the callable and non-callable bonds compare? Comment and discuss.
    \item[(CP)] Compute the duration and convexity of callable and non-callable bond at time 0. Comment on the difference between the two securities.
    \item[(CP)] Ho Lee versus Simple BDT. Redo all of the points above for the Simple BDT model (note: in both the Matlab file and the spreadsheet, this amounts to changing BDT Flag from 0 to 1 and re-run the routine to build the tree. Everything else should be automatic, except for the estimate of $\epsilon$ which now should use log differences in rates). Comment on the difference in price, if any, from the two methodologies.
\end{enumerate}

\begin{quote}
\textbf{Additional notes for Matlab users:}
\begin{enumerate}
    \item Note 1: Below you will find a generic backward algorithm for any security $P$ with periodic cash flows $c$, maturity at time $n$, and generic payoff $g = [g_{1}, …, g_{n}]$.
    \[
    PP(:,:) = \text{zeros}(n,n); \quad \% \text{initialize matrix for security}
    \]
    \[
    PP(1:n,n) = g; \quad \% \text{set final payoff of bond i equal to 1 for all nodes}
    \]
    \[
    \text{for j = n-1:-1:1} \quad \% \text{move backward on the tree, from i-1, back to 1}
    \]
    \[
    PP(1:j,j) = \exp(-\text{ImTree}(1:j,j) \cdot dt) \cdot (0.5 \cdot PP(1:j,j+1) + 0.5 \cdot PP(2:j+1,j+1,i) + c \cdot dt);
    \]
    \[
    \text{end}
    \]
    \item Note 2: To plot bond prices against interest rates at a given time $j$, you just need to use the following command:
    \[
    \text{plot(ImTree}(1:j,j), PP(1:j,j))
    \]
\end{enumerate}
\end{quote}

\begin{center}
PRICING SUPPLEMENT DATED May 22, 2007 \\
(to Offering Circular Dated July 28, 2006)
\end{center}

\begin{quote}
\$100,000,000 \\
Freddie Mac \\
6.00\% Fixed Rate Medium-Term Notes Due June 7, 2027 \\
Redeemable periodically, beginning June 7, 2011 \\
\begin{itemize}
    \item Issue Date: June 7, 2007
    \item Maturity Date: June 7, 2027
    \item Subject to Redemption: Yes. The Medium-Term Notes are redeemable at our option, in whole only, upon notice of not less than 5 Business Days, at a price of 100\% of the principal amount, plus accrued interest to the Redemption Date.
    \item Redemption Date(s): Semiannually, on June 7 and December 7, commencing June 7, 2011
    \item Interest Rate Per Annum: 6.00\%
    \item Frequency of Interest Payments: Semiannually, in arrears, commencing December 7, 2007
    \item Interest Payment Dates: June 7 and December 7
    \item Principal Payment: At maturity, or upon redemption
    \item CUSIP Number: 3128X6AT3
\end{itemize}
You should read this Pricing Supplement together with Freddie Mac’s Global Debt Facility Offering Circular, dated July 28, 2006 (the “Offering Circular”), and all documents that are incorporated by reference in the Offering Circular, which contain important detailed information about the Medium-Term Notes and Freddie Mac. See “Available Information” in the Offering Circular. Capitalized terms used in this Pricing Supplement have the meanings we gave them in the Offering Circular, unless we specify otherwise.

The Medium-Term Notes may not be suitable investments for you. You should not purchase the Medium-Term Notes unless you understand and are able to bear the redemption, yield, market, liquidity and other possible risks associated with the Medium-Term Notes. You should read and evaluate the discussion of risk factors (especially those risk factors that may be particularly relevant to this security) that appears in the Offering Circular under “Risk Factors” before purchasing any of the Medium-Term Notes.

The Medium-Term Notes, including any interest or return of discount on the Medium-Term Notes, are not guaranteed by and are not debts or obligations of the United States or any federal agency or instrumentality other than Freddie Mac.

Any discussion of tax issues set forth in this Pricing Supplement and the related Offering Circular was written to support the promotion and marketing of the transactions described in this Pricing Supplement. Such discussion was not intended or written to be used, and it cannot be used, by any person for the purpose of avoiding any tax penalties that may be imposed on such person. Each investor should seek advice based on its particular circumstances from an independent tax advisor.

\begin{center}
\begin{tabular}{|c|c|}
\hline
\textbf{Per Medium-Term Note} & \textbf{Total} \\
\hline
Price to Public (1)(2) & 100\% & \$100,000,000 \\
\hline
Underwriting Discount (2) & 0.415\% & \$415,000 \\
\hline
Proceeds to Freddie Mac (1)(3) & 99.585\% & \$99,585,000 \\
\hline
\end{tabular}
\end{center}

\begin{itemize}
    \item (1) Plus accrued interest, if any, from June 7, 2007.
    \item (2) See “Distribution Arrangements” in the Offering Circular.
    \item (3) Before deducting expenses payable by Freddie Mac estimated at \$1,000.
\end{itemize}

\begin{center}
Goldman, Sachs \& Co.
\end{center}

\end{quote}

\end{document}
```

### HW 7

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}

\title{Fixed Income Asset Pricing\\
Bus 35130 Spring 2024\\
John Heaton}
\date{}
\begin{document}
\maketitle

\section*{Homework 7}
\textbf{Relative Value Trades and Mortgage Backed Securities\\
Due at the beginning of class 9}

\begin{quote}
\textbf{Note 1:} The first part of this assignment is about a simple relative value trade on Trees. The other parts of the assignment are on Mortgage Backed Securities, and valuation using both trees and Monte Carlo simulations. It appears long as we describe all of the steps, but the guide Matlab and Excel codes perform automatically large parts of the exercise. Available on Canvas are guideline files in Excel, Matlab and Python that implement many of the steps.

\textbf{Note 2:} Parts I and II are “pencil and paper” (PP) questions. The other parts use data and computer programs (CP). You are supposed to do both.
\end{quote}

\subsection*{Part I: Relative Value Trades on Binomial Trees (PP)}
Consider the following binomial tree. Each time interval is 1-year (that is, $\Delta t = 1$).

\begin{align*}
&i = 0 && i = 1 && i = 2 \\
&r_{2,uu} = 0.05 && && \\
&r_{1,u} = 0.04 && r_{2,ud} = 0.03 && r_{2,du} = 0.03 \\
&r_{0} = 0.03 && r_{1,d} = 0.02 && r_{2,dd} = 0.01 \\
\end{align*}

The 2-period bond is $Z_{0}(2) = 0.94$, which implied a risk-neutral probability $\omega = 0.59618073$. The true probability to move up the tree is $p = 0.5$.

The three period, fixed-coupon bond with coupon rate $c = 3\%$ is trading at par 100. Your model, instead, prescribes it should trade at $P_{0}(3) = 99.34716$. The three-period zero coupon bond $Z_{0}(3) = 90.88915$ seems to be trading at the proper price.

\begin{enumerate}
    \item Design a relative value trading strategy to take advantage of the miss-pricing (according to your model). Please, be clear on what you sell and what you buy. Recall that the only traded securities are the coupon bond (which is miss-priced) and the 3-period zero-coupon bond (which is correctly priced). In addition, you can buy and sell 1-period bonds (i.e., borrow and lend at the rates on the tree).
    \item Make a binomial tree with the trading strategy up to maturity: Indicate the positions in traded securities at any point. (You can use Excel for this. But make sure to report the trees in the assignment).
    \item What is the total profit and loss?
\end{enumerate}

\subsection*{Part II: Interest Rate Trees and MBS (PP)}
Consider the interest rate tree examined in HW5, reported below. Recall that each time interval is 1-year (that is, $\Delta t = 1$).

\begin{align*}
&i = 0 && i = 1 && i = 2 \\
&r_{2,uu} = 0.05 && && \\
&r_{1,u} = 0.04 && r_{2,ud} = 0.03 && r_{2,du} = 0.03 \\
&r_{0} = 0.03 && r_{1,d} = 0.02 && r_{2,dd} = 0.01 \\
\end{align*}

The probability of an “up” movement is $p = 40\%$, and the risk-neutral probability $\omega$ is in the solution to HW5 (or recompute it for this homework). You also know the current value of a 2-period zero-coupon bond is $Z_{0}(2) = 0.94$.

\begin{enumerate}
    \item[(a)] Compute the value of a 3\% Pass-Through MBS with maturity $i = 3$. The underlying pool has a coupon rate of $r_{m} = 3.469\%$, principal value $N = 100$, and maturity $i = 3$. Follow the steps in TN 5 (but recall the risk-neutral probability is not 0.5).
\end{enumerate}

\subsection*{Part III: Pricing MBS on Trees (CP)}
On November 1, 2014, the Ginnie Mae Pass-Through security GNSF 4 was trading at 106.5781. This pass-through security was collateralized by a pool of mortgages with a weighted average coupon (WAC) = 4.492\%, and a weighted average maturity (WAM) = 311 (months). As a junior analyst at the JCH Investment Group, you are examining the value of the GNSF 4 and trying to assess whether this price is in line with current interest rates and option prices.

You decide to use caps and floors to assess whether all of the interest rate optionality implicit in mortgage backed securities is taken into account in the current price of MBS. You decide to proceed as follows:

\begin{enumerate}
    \item Compute Forward Volatilities from Cap Volatility Quotes
    \begin{itemize}
        \item[(a)] Compute the zero-coupon LIBOR curve implicit in the swap curve, as usual (Note: This part is automatically done by the guide codes available on Canvas);
        \item[(b)] Compute the forward volatilities, also up to maturity of 30 years. Cap volatility quotes are available up to 30-years as well (Note: This part is automatically done by the guide code).
        \item[(c)] Plot the forward and the flat volatilities. Comment on your findings. Discuss. Provide an intuition about the relation between forward and flat volatilities.
    \end{itemize}
    \item Fit the BDT model to the discount curve and forward volatilities. Use the algorithm in TN 4 to fit the Black-Derman-Toy model (Note: automatically done by the guides, once fitted LIBOR curves and forward volatilities are carried over. Note that we fit the model at quarterly intervals instead of monthly intervals to keep the computational exercises simpler).
    \item Use the BDT model to value GNSF4. To obtain the price of the pass-through security GNSF 4, recall you must first do the following steps:
    \begin{itemize}
        \item[(a)] Compute the dollar coupon and the scheduled interest and principal payments. These calculations allow you to compute the scheduled outstanding principal balance. You can do these computations assuming outstanding principal of 100 (so that, the price will be also in percentage of 100, like the quoted value of the security). Note that the coupon must satisfy the equation
        \[
        P_{0} = C \sum_{j=1}^{n} \left( \frac{1}{1 + r_{m} \Delta t} \right)^{j}
        \]
        where $n$ is the number of coupon payments and $\Delta t$ is the time step. A useful formula is the following: define $a = \left( \frac{1}{1 + r_{m} \Delta t} \right)$, then we have the result that
        \[
        \sum_{j=1}^{n} a^{j} = \frac{a - a^{n+1}}{1 - a}
        \]
        so that
        \[
        C = P_{0} \frac{1 - a}{a - a^{n+1}}
        \]
        Given $C$, you can compute the scheduled principal and interest payment and remaining principal over time.
        \item[(b)] Compute the value of the non-callable mortgage on the tree (i.e., present value of future coupons. This part is identical to previous cases, except that there is no bullet capital payment at maturity).
        \item[(c)] Compute the value of the American call option from homeowner perspective, and thus the optimal time of prepayment. (This part again is identical to the previous homework, except that you must compare the present value of future payment at every node $(i, j)$ to the outstanding principal at time $i$.) What is the value of the pool of mortgages as of time zero? (i.e., what is the present value of future payments that takes into account the American option?)
        \item[(d)] Use the GNSF coupon rate (4\%) and the optimal prepayment time computed in the previous point to compute the cash flows of the pass-through security and thus its value at time 0.
    \end{itemize}
    \item Is the price that you obtained close to the quoted one? If not, explain why not intuitively. What may be going on to explain the discrepancy, if any?
\end{enumerate}

\subsection*{Part IV: Use Monte Carlo Simulations on Trees (CP)}
From the tree estimated in Part III, do the following:

\begin{enumerate}
    \item Use Monte Carlo simulationson the tree to price a 30-year cap and a 30-year Asian cap with strike rate $r_{k} = 2\%$. (Note: This is identical to the example in Chapter 13 in the book.)
    \item Use Monte Carlo simulations and the prepayment function
    \[
    p_{t} = c_{1} - \max(r_{m} - sp - r_{t}, c_{2})
    \]
    to do the following:
    \begin{itemize}
        \item Compute the value of the pass-through, interest-only and principal-only mortgage-backed securities discussed above. Note that both the guide files are already set up to do these calculations for given parameters of the prepayment function. Choose the parameters of the prepayment function to obtain a value of the PT security that is similar to the quoted one. (This can be done by trial and error).
        \item Vary the parameters of the prepayment functions and compute the values of IO and PO. Discuss your findings intuitively.
    \end{itemize}
\end{enumerate}

\end{document}
```