# 13.10 USING DerivaGem  

The software accompanying this book, DerivaGem, is a useful tool for becoming. comfortable with binomial trees. After loading the software in the way described at the end of this book, go to the Equity_FX_Indx_Fut_Opts_Calc worksheet. Choose. Equity as the Underlying Type and select Binomial American as the Option Type..  

Enter the stock price, volatility, risk-free rate, time to expiration, exercise price, and tree steps, as 50, $30\%$ $5\%$ , 2, 52, and 2, respectively. Click on the Put button and then on Calculate. The price of the option is shown as 7.428 in the box labeled Price. Now click on Display Tree and you will see the equivalent of Figure 13.10. (The red numbers in the software indicate the nodes where the option is exercised.)  

Return to the Equity_FX_Indx_Fut_Opts_Calc worksheet and change the number of time steps to 5. Hit Enter and click on Calculate. You will find that the value of the option changes to 7.671. By clicking on Display Tree the five-step tree is displayed, together with the values of $u$ , d, a, and $p$ calculated above.  

DerivaGem can display trees that have up to 10 steps, but the calculations can be done for up to 500 steps. In our example, 500 steps gives the option price (to two decimal places) as 7.47. This is an accurate answer. By changing the Option Type to Binomial European, we can use the tree to value a European option. Using 500 time steps, the value of a European option with the same parameters as the American option is 6.76. (By changing the Option Type to Black-Scholes European, we can display the value of the option using the Black-Scholes-Merton formula that will be presented in Chapter 15. This is also 6.76.)  

By changing the Underlying Type, we can consider options on assets other than stocks. These will now be discussed.  
