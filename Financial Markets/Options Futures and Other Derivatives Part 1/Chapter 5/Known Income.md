# 5.5 KNOWN INCOME  

In this section we consider a forward contract on an investment asset that will provide a perfectly predictable cash income to the holder. Examples are stocks paying known dividends and coupon-bearing bonds. We adopt the same approach as in the previous section. We first look at a numerical example and then review the formal arguments.  

Consider a forward contract to purchase a coupon-bearing bond whose current price is $\$900$ . We will suppose that the forward contract matures in 9 months. We will also. suppose that a coupon payment of $\$40$ is expected on the bond after 4 months. We assume that the 4-month and 9-month risk-free interest rates (continuously compounded) are, respectively, $3\%$ and $4\%$ per annum.  

Suppose first that the forward price is relatively high at $\$910$ . An arbitrageur can borrow $\$900$ to buy the bond and enter into the forward contract to sell the bond for $\$910$ . The coupon payment has a present value of $40e^{-0.03\times4/12}=\$39.60$ Of the $\$900$ $\$39.60$ is therefore borrowed at $3\%$ per annum for 4 months so that it can be repaid with the coupon payment. The remaining $\$860.40$ is borrowed at $4\%$ per annum for 9 months. The amount owing at the end of the 9-month period is $86\hat{0}.40e^{0.04\times0.75}=$ $\$886.60$ . A sum of $\$910$ is received for the bond under the terms of the forward contract. The arbitrageur therefore makes a net profit of  

$$
910.00-886.60=\$23.40
$$  

Suppose next that the forward price is relatively low at. $\$870$ . An investor can short the bond and enter into the forward contract to buy the bond for. $\$870$ . Of the $\$900$ realized from shorting the bond, $\$39.60$ is invested for 4 months at $3\%$ per annum so that it grows into an amount sufficient to pay the coupon on the bond. The remaining $\$860.40$ is invested for 9 months at $4\%$ per annum and grows to $\$896.60$ . Under the terms of the forward contract, $\$870$ is paid to buy the bond and the short position is closed out. The. investor therefore gains  

$$
886.60-870=\$16.60
$$  

The two strategies we have considered are summarized in Table 5.3. The first strategy in Table 5.3 produces a profit when the forward price is greater than $\$896.60$ , whereas the second strategy produces a profit when the forward price is less than $\$886.60$ . It follows that if there are no arbitrage opportunities then the forward price must be $\$886.60$  

# A Generalization  

We can generalize from this example to argue that, when an investment asset will provide income with a present value of. $I$ during the life of a forward contract, we have.  

$$
F_{0}=(S_{0}-I)e^{r T}
$$  

Table 5.3  Arbitrage opportunities when 9-month forward price is out of line with spot price for asset providing known cash income. (Asset price $\l=\$900$ ; income of $\$40$ occurs at 4 months; 4-month and 9-month rates are, respectively,. $3\%$ and $4\%$ per annum.)   


<html><body><table><tr><td>Forward price = $910</td><td>Forward price = $870</td></tr><tr><td>Actionnow:</td><td>Actionnow:</td></tr><tr><td>Borrow$900: $39.60 for 4months</td><td>Short 1unit of asset torealize$900</td></tr><tr><td>and $860.40 for 9 months</td><td>Invest $39.60 for 4 months</td></tr><tr><td>Buy1 unit of asset</td><td>and$860.40for9 months</td></tr><tr><td>Enterintoforwardcontracttosell asset in 9 months for $910</td><td>Enter into a forward contract to buy</td></tr><tr><td>Actionin4months:</td><td>asset in 9 months for $870</td></tr><tr><td>Receive $40ofincome on asset</td><td>Actionin4months:</td></tr><tr><td>Use $40 to repay first loan</td><td>Receive $40 from 4-month investment Pay income of $40 on asset</td></tr><tr><td>with interest</td><td></td></tr><tr><td>Actionin9months: Sell asset for $910</td><td>Actionin9 months:</td></tr><tr><td>Use $886.60 to repay second loan</td><td>Receive $886.60from 9-month investment</td></tr><tr><td>withinterest</td><td>Buy asset for $870 Close out short position</td></tr><tr><td></td><td></td></tr><tr><td>Profit realized = $23.40</td><td>Profit realized = $16.60</td></tr></table></body></html>  

In our example $S_{0}=900.00,I=40e^{-0.03\times4/12}=39.60,r=0.04$ and $T=0.75$ , so that  

$$
F_{0}=(900.00-39.60)e^{0.04\times0.75}=\S886.60
$$  

This is in agreement with our earlier calculation. Equation (5.2) applies to any investment asset that provides a known cash income.  

If $F_{0}>(S_{0}-I)e^{r T}$ , an arbitrageur can lock in a profit by buying the asset and. shorting a forward contract on the asset; if. $F_{0}<(S_{0}-I)e^{r T}$ , an arbitrageur can lock in a profit by shorting the asset and taking a long position in a forward contract. If short sales are not possible, investors who own the asset will find it profitable to sell the asset and enter into long forward contracts.4  

# Example 5.2  

Consider a 10-month forward contract on a stock when the stock price is $\$50$ We assume that the risk-free rate of interest (continuously compounded) is $8\%$ per annum for all maturities and also that dividends of $\$0.75$ per share are expected after 3 months, 6 months, and 9 months. The present value of the dividends, $I.$ is  

$$
I=0.75e^{-0.08\times3/12}+0.75e^{-0.08\times6/12}+0.75e^{-0.08\times9/12}=2.162
$$  

The variable $T$ is 10 months, so that the forward price, $F_{0}$ from equation (5.2), is  

given by  

$$
F_{0}=(50-2.162)e^{0.08\times10/12}=\S51.14
$$  

If the forward price were less than this, an arbitrageur would short the stock and buy forward contracts. If the forward price were greater than this, an arbitrageur would short forward contracts and buy the stock in the spot market.  
