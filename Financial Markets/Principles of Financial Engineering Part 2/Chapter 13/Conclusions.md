# 13.5 CONCLUSIONS  

This chapter dealt with three applications of the fundamental theorem of asset pricing. In general, a financial engineer needs to use such approaches when static replication of the assets is not possible. Mark-to-market requirements or construction of new products often requires calculating arbitrage-free prices internally without having recourse to synthetics that can be put together using liquid prices observed in the markets. The methods outlined in this chapter show some standard ways of doing this.  

# SUGGESTED READING  

There are several sources the reader may consult to learn more on the methods introduced in this chapter via some simple examples. One of our preferred sources is Clewlow and Strickland (1998), which provides some generic codes for computer applications as well. A recent book that deals with the topic of Monte Carlo in finance is Jackel (2o02). The series of articles referenced in Avellaneda et al. (2001) provides an in-depth discussion of calibration issues. Finally, the original Black et al. (1990) model is always an illuminating reading on the BDT model. For quanto assets,. and related discussion, consider Hull (2014). Wilmott (2006) is very useful for learning further application of the techniques presented here..  

# EXERCISES  

1. (Black-Derman-Toy model.) You observe the following default-free discount bond prices $B$ $(t,T_{\mathrm{i}})$ , where time is measured in years:  

$$
B(0,1)=95,B(0,2)=93,B(0,3)=91,B(0,4)=89
$$  

These prices are assumed to be arbitrage-free. In addition, you are given the following cap-floor volatilities:  

$$
\sigma(0,1)=0.20,\sigma(0,2)=0.25,\sigma(0,3)=0.20,\sigma(0,4)=0.18
$$  

where $\sigma(t,T_{i})$ is the (constant) volatility of the LIBOR rate $L_{T_{i}}$ that will be observed at. $T_{i}$   
with tenor of 1 year..  

a. Using the Black-Derman-Toy model, calibrate a binomial tree to these data.   
b. Suppose you are given a bond call option with the following characteristics. The underlying, $B(2,4)$ , is a two-period bond, expiration $T=2$ , strike $K_{B}=93$ You know that the BDT tree is a good approximation to arbitrage-free LIBOR dynamics. What is the forward price of $B$ (2, 4)?   
c. Calculate the arbitrage-free value of this call option using the BDT approach.  

2. (Exchange rates and LIBOR rates.) You know that the euro/dollar exchange rate $e_{t}$ follows the real-world dynamics:  

$$
\mathrm{d}e_{t}=\mu\mathrm{d}t+0.15e_{t}\mathrm{d}W_{t}
$$  

The current value of the exchange rate is $e_{o}=1.1015$ . You also know that the price of a 1-year USD discount bond is given by  

$$
B(t,t+1)^{\mathrm{US}}=98.93\
$$  

while the corresponding euro-denominated bond is priced as  

$$
B(t,t+1)^{\mathrm{EU}}=98.73\
$$  

Both of these prices are arbitrage-free and there is no credit risk.  

a. What are the 1-year LIBOR rates in these two currencies at time $t?$ b. What are the continuously compounded interest rates $r_{t}^{\mathrm{US}},r_{t}^{\mathrm{EUR}}$ c. Obtain the arbitrage-free dynamics of the $e_{t}$ In particular, state clearly whether we need to use continuously compounded rates or LIBOR rates to do this. d. Is there a continuous time dynamic that can be written using the LIBOR rates?  

3. (European option.) Consider again the data given in the previous question.  

a.Use $\Delta=1$ year to discretize the system.   
b. Generate five sets of standard normal random numbers with five random numbers in each set. How do you know that these five trajectories are arbitrage-free?   
c. Calculate the value of the following option using these trajectories. The strike is 0.95, the expiration is 3 years, and the European style applies.  

4. (European FX option.) Suppose you know that the current value of the peso-dollar exchange rate is 3.75 pesos per dollar. The yearly volatility of the Mexican peso is $20\%$  

The Mexican interest rate is $8\%$ , whereas the US rate is $3\%$ . You will price a dollar option written on the Mexican peso. The option is of European style and has a maturity of 270 days. All processes under consideration are known to be geometric.  

a. Price this option using a standard Monte Carlo model. You will select the number of series, the size of the approximating time intervals, and other parameters of the Monte Carlo exercise.   
b. Now assume that Mexico's foreign currency reserves follow a geometric SDE with a volatility of $10\%$ and a drift coefficient of $5\%$ a year. The current value of reserves is USD7 billion. If reserves fall below USD6 billion, there will be a one-shot devaluation of $100\%$ . Is this information important for pricing the option? Explain.   
c. Use importance sampling to reprice the option. Your pricing is supposed to incorporate the risk of devaluation.  

# EXCEL EXERCISES  

5. (European Option.)  

Write a VBA program to simulate $M=100$ stock prices using a Monte Carlo technique to. calculate the prices of European Call and Put options based on the following data: $S(O)=100$ $K=105$ $T=1$ $r=8\%$ $\sigma=50\%$  

Gradually increase the value of. $M$ and report the observed resulting price of the options.  

6. (Digital Currency Options.) Write a VBA program to simulate. $M=100$ stock prices using a Monte Carlo technique to calculate the prices of digital call and put options FX options as discussed in the text. Use the following parameters:. $S(0)=\$1.54$ $K=\$1.58$ $T=1$ $r=8\%$ $r_{f}=6\%$ $\sigma=30\%$ ; payoff $R=\$10$ Gradually increase the value of $M$ and report the observed price of the options.  

7. (Barrier Option.) Write a VBA program to simulate $M=100$ stock prices using a Monte Carlo technique to calculate the price of Barrier down-and-out and down-and-in call options based on the following data:. $S(O)=100$ $K=110$ $T=1$ $r=8\%$ $\sigma=50\%$ $H=90$ Gradually increase the value of $M$ and report the observed price of the options.  

# MATLAB EXERCISES  

8. (European Options.) Write a MATLAB program to document the efficiency of a Monte Carlo approach to the estimation of European Call and Put option prices based on the following data:  

$S(O)=100$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ Plot a graph of estimated prices as a function of the number of stock price simulations.  

9. (Barrier Option.) Write a MATLAB program to document the efficiency of a Monte Carlo approach to the estimation of the price of Down-and-Out and Down-and-In Call options. based on the following data: $S(0)=100\$ $K=110$ $T=1$ $r=8\%$ $\sigma=30\%$ $H=90$ Plot a graph of estimated prices as a function of the number of stock price simulations.  

10. (Digital Currency Option.) Write a MATLAB program to observe the efficiency of Monte Carlo technique to estimate the price of Digital Call and Put price with the following data:. $S(0)=\$1.54$ $K=\$1.58$ $T=1$ $r=8\%$ $r_{f}=6\%$ $\sigma=30\%$ $R=\$10$ Plot the graph of estimated price v/s the no. of stock price simulation..  

11. (BDT Model Calibration.) Write a MATLAB program to calibrate the BDT model based on the following data on bond prices and implied volatilities $B(t_{0},t_{1})=0.95$ $B(t_{0},t_{2})=0.93$ $B(t_{0},t_{3})=0.91$ $B(t_{0},t_{4})=0.89$ $\sigma(0,1)=20\%$ $\sigma(0,2)=25\%$ $\sigma(0,3)=20\%$ $\sigma(0,4)=18\%$ Draw the LIBOR tree based on the output results.  

This page intentionally left blank  

# FIXED INCOME ENGINEERING 14  

# THAPTER OUTLINE  

4.1 Introduction.. 460   
4.2 A Framework for Swaps.. .461   
14.2.1 Equivalence of Cash Flows 464   
14.2.2 Pricing the Swap. 464   
14.2.2.1 Interpretation of the swap rate . 466   
14.2.3 Some Applications.. 468   
14.2.3.1 Another formula. 469   
14.2.3.2 Marking to market..... 470   
14.3 Term Structure Modeling.. .471   
14.3.1 Determining the Forward Rates from Swaps. 471   
14.3.2 Determining the $B(t_{0},t_{i})$ from Forward Rates 472   
14.3.3 Determining the Swap Rate... 472   
14.3.4 Real-World Complications . 472   
14.3.4.1 Remark.. 473   
4.4 Term Structure Dynamics. 473   
14.4.1 The Framework. 474   
14.4.2 Normalization and Forward Measure.... 475   
14.4.2.1 Risk-neutral measure is inconvenient. 475   
14.4.2.2 The forward measure.. 477   
14.4.2.3 Arbitrage-free SDEs for forward rates 478   
14.4.3 Arbitrage-Free Dynamics ... 479   
14.4.3.1 Review. 481   
14.4.4 A Monte Carlo Implementation .. 482   
4.5 Measure Change Technology . 483   
14.5.1 The Mechanics of Measure Changes. 485   
14.5.2 Generalization... 487   
4.6 An Application. 488   
14.6.1 Another Example of Measure Change 489   
14.6.2 Pricing CMS. 493   
4.7 In-Arrears Swaps and Convexit... 494   
14.7.1 Valuation.. 495   
14.7.2 Special Case.. 497   
4.8 Cross-Currency Swaps.. 498   
14.8.1 Pricing. 499   
14.8.2 Conventions 500  

Frineipies ol rinancral Engineering. Copyright $\copyright$ 2015 Elsevier Inc. All rights reserved. 45?  

14.9 Differential (Quanto) Swaps 500   
14.9.1 Basis Swaps. 501   
14.10 Conclusions... 501   
Suggested Reading ..- 502   
Exercises .. . 502   
EXCEL Exercises 503   
MATLAB Exercise . 505  
