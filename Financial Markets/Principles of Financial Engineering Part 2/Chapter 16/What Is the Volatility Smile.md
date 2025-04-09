# 16.11 WHAT IS THE VOLATILITY SMILE?  

Consider the Black-Scholes world with vanilla European call and put options written on the equity price (index), $S_{t},$ that expire on the same date $T.$ Let $K_{i}$ denote the ith strike of the option series and $\sigma_{i}$ the constant Black-Scholes instantaneous (implied) volatility coefficient for the strike $K_{i}$ Finally, let $r$ be the constant risk-free rate.  

The Black-Scholes setting makes many assumptions beyond that of constant volatility. In particular, the underlying equity does not make any dividend payments, and there are no transaction. costs, tax issues, or regulatory costs. Finally,. $S_{t}$ is assumed to follow the geometric stochastic dif-. ferential equation (SDE)  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty]
$$  

where $W_{t}$ is a Wiener process defined under the probability. $P$ . Here, the parameter $\mu$ may also depend on $S_{t}.$ The crucial assumption is that the diffusion component is given by. $\sigma{\cal S}_{t}$ .This is the. assumption that we are concerned with in this chapter. The Black-Scholes setting assumes that the absolute volatility during an infinitesimally small interval ${\mathrm{d}}t$ is given (heuristically) by11  

$$
\sqrt{E_{t}^{P}[\left(\mathrm{d}S_{t}-\mu S_{t}~\mathrm{d}t\right)^{2}]}=\sigma S_{t}\sqrt{\mathrm{d}t}
$$  

Thus, for a small interval,. $\Delta$ , we can write the percentage volatility approximately as  

$$
\frac{\sqrt{E_{t}^{p}[\left(\Delta S_{t}-\mu S_{t}\Delta\right)^{2}]}}{S_{t}}\cong\sigma\sqrt{\Delta}
$$  

According to this, as. $S_{t}$ changes, the percentage volatility during intervals of length $\Delta$ remains approximately constant.  

In this environment, a typical put option's price is given by the Black--Scholes formula:  

$$
P(S_{t},K,\sigma,r,T)=-S_{t}N(-d_{1})+K e^{-r(T-t)}N(-d_{2})
$$  

with  

$$
d_{1}={\frac{\log(S_{t}/K)+{\bigl(}(1/2)\sigma^{2}+r{\bigr)}(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

$$
d_{2}=d_{1}-\sigma{\sqrt{(T-t)}}
$$  

Suppose the markets quote implied volatility, $\sigma$ . To get the monetary value of an option with strike $K_{i}$ the trader will put the current values of $S_{t},t,$ and $r$ and the quoted value of the implied volatility $\sigma_{i}$ at which the trade went through, in this formula. According to this interpretation, the Black-Scholes formula is used to assign a dollar value to a quoted volatility. Conversely, given the correct option price $P(.)$ , the implied volatility, $\sigma_{i}$ for the $K_{i}$ put could be extracted.  

We can now define the volatility smile within this context. Consider a series of $T.$ expiration, liquid, and arbitrage-free out-of-the-money put option prices indexed by the strike prices $K_{i}$ denoted respectively by $P_{K_{i}}$  

$$
P_{K_{1}},...,P_{K_{n}}
$$  

for  

$$
K_{n}<\ldots<K_{1}<K_{0}=S_{t}
$$  

According to this, the. $K_{0}$ put is ATM and, as $K_{i}$ decreases, the puts go deeper out-of-the-money, see Figure 16.9.  

Then, given the (bid or ask) option prices, we can use the Black-Scholes formula backward andextract $\sigma_{i}$ that the trader used to conclude the deal on. $P_{K_{i}}$ . If the assumptions of the Black-Scholes world are correct, all the implied volatilities would turn out to be the same  

$$
\sigma_{K_{0}}=\sigma_{K_{1}}=\cdots=\sigma_{K_{n}}=\sigma
$$  

![](images/95cd77d0d6cb84e8d4b3704b26796b65c5f92f21370000057089deac53172425.jpg)  

# FIGURE 16.9  

Volatility smile: implied volatility against strike price.  

since the put options would be identical except for their strike price. Thus, in a market that conforms to the Black-Scholes world, the traders would use the same $\sigma$ in the Black-Scholes put formula to obtain each $P_{K_{i}},i=0,...,n.$ Going backward, we would then recover the same constant $\sigma$ from the prices.12  

Yet, if we conducted this exercise in reality with observed option prices, we would find that the implied volatilities would satisfy  

$$
\sigma_{K_{0}}<\sigma_{K_{1}}<\cdots<\sigma_{K_{n}}
$$  

In other words, the more out-of-the-money the put option is, the higher the corresponding implied volatility. As a result, we would obtain a "smiley" curve..  

We can also use the implied vols from progressively out-of-the-money call options and obtain, depending on the underlying instrument, the second half of the smile, as shown in Figure 16.10.  

# 16.11.1 SOME STYLIZED FACTS  

Volatility smiles observed in reality seem to have the following characteristics,  

1. Options written on equity indices yield, in general, a nonsymmetric one-sided "smile" as shown in Figure 16.10a. For this reason, they are often called skews.  

![](images/cadda1939b8954f8444b02781766a54980eb703841f211ffc1b15fe9655080f8.jpg)  

# FIGURE 16.10  

Skew for equity indices and typical symmetric FX smile.  

2. The FX markets are quite different in this respect. They yield a more or less symmetric smile, as in Figure 16.10b. However, the smile will rarely be exactly symmetric and it is routine practice in foreign exchange markets to trade this asymmetry using risk reversals.   
3. Options on various interest rates yield a more monotonous one-sided smile than the equity indices. The fact that "smile" patterns vary from market to market would suggest, on the surface, that there are different explanations involved.  

It is also natural to think that the dynamics of the smile vary depending on the sector. This point is relevant for risk management, running swaption, cap/floor books, and volatility trading. But, before we discuss it, we consider an example.  

# EXAMPLE  

Table 16.1 displays all the options written on the S&P100 index with a very short expiration. These data were obtained from live quotes early in the morning, so few trades had passed. However, the option bid-ask quotes were live, in the sense that reasonably sized trades could be conducted on them.  

When the data were gathered, the underlying was trading at 589.14. We use 12 out-of-the-. money puts and 9 out-of-the-money calls to obtain the Black-Scholes implied volatilities.  

The interest rate is taken to be $1.98\%$ , and the time to expiration was 8/365. Using these values and the bid prices for the options given in the table, the equations  

$$
\begin{array}{r}{C(S_{t},K_{i},r,T,\sigma_{i})=C_{i}}\ {}\ {P(S_{t},K_{j},r,T,\sigma_{j})=P_{j}}\end{array}
$$  

were solved for the implied vols of calls $\{\sigma_{i}\}$ and the implied vols of puts $\{\sigma_{i}\}$ $C_{i}$ and $P_{j}$ being observed option prices.  

<html><body><table><tr><td colspan="8">Table 16.1 OEX Options with January 18, 2002, Expiration</td></tr><tr><td>Calls</td><td>Bid</td><td>Ask</td><td>Vol</td><td>Puts</td><td>Bid</td><td>Ask</td><td>Vol</td></tr><tr><td>Jan 550</td><td>39.5</td><td>41.5</td><td>0</td><td>Jan 550</td><td>0.45</td><td>0.75</td><td>0</td></tr><tr><td>Jan 555</td><td>34.8</td><td>36.3</td><td>0</td><td>Jan 555</td><td>0.65</td><td>0.95</td><td>0</td></tr><tr><td>Jan 560</td><td>30</td><td>31.5</td><td>0</td><td> Jan 560</td><td>0.9</td><td>1.2</td><td>0</td></tr><tr><td>Jan 565</td><td>25.2</td><td>26.7</td><td>0</td><td>Jan 565</td><td>1.25</td><td>1.55</td><td>0</td></tr><tr><td>Jan 570</td><td>20.6</td><td>22.1</td><td>0</td><td> Jan 570</td><td>1.8</td><td>2.1</td><td>0</td></tr><tr><td>Jan 575</td><td>16.3</td><td>17.8</td><td>0</td><td>Jan 575</td><td>2.3</td><td>3</td><td>0</td></tr><tr><td>Jan 580</td><td>13</td><td>13.5</td><td>0</td><td>Jan 580</td><td>3.4</td><td>4.1</td><td>2</td></tr><tr><td>Jan 585</td><td>9.1</td><td>9.8</td><td>0</td><td>Jan 585</td><td>5</td><td>5.7</td><td>5</td></tr><tr><td>Jan 590</td><td>6.1</td><td>6.8</td><td>50</td><td>Jan 590</td><td>7.6</td><td>7.9</td><td>5</td></tr><tr><td>Jan 595</td><td>4.1</td><td>4.5</td><td>12</td><td>Jan 595</td><td>10.1</td><td>10.8</td><td>25</td></tr><tr><td> Jan 600</td><td>2.5</td><td>2.8</td><td>3</td><td> Jan 600</td><td>13.1</td><td>14.5</td><td>0</td></tr><tr><td>Jan 605</td><td>1.2</td><td>1.5</td><td>0</td><td>Jan 605</td><td>17.2</td><td>18.7</td><td>0</td></tr><tr><td>Jan 610</td><td>0.55</td><td>0.85</td><td>1</td><td>Jan 610</td><td>21.7</td><td>23.2</td><td>0</td></tr><tr><td>Jan 615</td><td>0.25</td><td>0.55</td><td>0</td><td>Jan 615</td><td>26.6</td><td>28.1</td><td>0</td></tr><tr><td>Jan 620</td><td>0.2</td><td>0.35</td><td>1</td><td>Jan 620</td><td>31.4</td><td>32.9</td><td>0</td></tr><tr><td>Jan 625</td><td>0.05</td><td>0.2</td><td>0</td><td>Jan 625</td><td>36.3</td><td>37.8</td><td>0</td></tr><tr><td>Jan 630</td><td>0</td><td>0.15</td><td>0</td><td>Jan 630</td><td>41</td><td>43</td><td>0</td></tr><tr><td>Jan 635</td><td>0</td><td>0.1</td><td>0</td><td>Jan 635</td><td>46</td><td>48</td><td>0</td></tr><tr><td>Jan 640</td><td>0</td><td>0.1</td><td>0</td><td> Jan 640</td><td>51</td><td>53</td><td>0</td></tr><tr><td>Jan 645</td><td>0</td><td>0.1</td><td>0</td><td>Jan 645</td><td>56.5</td><td>57.5</td><td>0</td></tr><tr><td>Jan 650</td><td>0</td><td>0.1</td><td>0</td><td> Jan 650</td><td>60.5</td><td>63.5</td><td>0</td></tr><tr><td> Jan 660</td><td>0</td><td>0.05</td><td>0</td><td> Jan 660</td><td>70.5</td><td>73.5</td><td>0</td></tr><tr><td> Jan 680</td><td>0</td><td>0.05</td><td>0</td><td> Jan 680</td><td>90.5</td><td>93.5</td><td>0</td></tr></table></body></html>  

![](images/c4876dc24cb5ff4ad99c0af3e9c25342ffbfb1f70c9c7bcbc78d6b68463656dd.jpg)  

# FIGURE 16.11  

Implied volatility of short-dated OEX options against moneyness.  

The resulting vols were plotted against. $K_{i}/S_{t}$ in Figure 16.11. We see a pronounced smile.. For example, the January 400 put, which traded at about $32\%$ out-of-the-money, had a vola-. tility of about $26\%$ , while the ATM option traded at an implied volatility of $18.5\%$  

OEX options are of American style and this issue was ignored in the example above. This would introduce an upward bias in the calculated volatilities. This bias is secondary for our purpose, but in real trading should be corrected. One correction has been suggested by Barone-Adesi and Whaley (1987).  

# 16.11.2 HOW CAN WE DEFINE MONEYNESS?  

The way a smile is plotted varies from one market to another. The implied volatility, denoted by $\sigma_{i:}$ always appears on the $y$ -axis. Unless stated otherwise, we extract this volatility from the. Black-Scholes formula in equity or FX markets, and from the Black formula in the case of interest. rates. The implied volatilities are then treated as if they were random and time varying..  

What to put on the horizontal axis is a more delicate question and eventually depends on how we define "moneyness" of an option. Sometimes the smile is plotted against moneyness measured by the ratio of the strike price to the current market price, $K_{i}/S_{t}$ If the smile is a function of how much the option is out-of-the-money only, then this normalization will stabilize the smile in the sense that as $S_{t}$ changes, the smile for that particular option series may be more or less invariant. But there are almost always factors other than moneyness that affect the smile, and some practitioners define moneyness differently.  

For example, sometimes the smile is plotted against $K_{i}e^{-r(T-t)}/S_{t}$ For short-dated options, this makes little difference, since $r(T-t)$ will be a small number. For longer-dated options, the difference is more relevant. By including this discount factor, market practitioners hope to eliminate the effect of the changes in the remaining life of the option.  

Sometimes the horizontal axis represents the option's delta. FX traders take the size of delta as a measure of moneyness. This practice can be challenged on the grounds that an option's delta depends on more variables than just moneyness. It also depends, for example, on the instantaneous implied volatility. Yet, as we will see later, there are some deltas at which volatility trading is particularly liquid in FX markets.  

The reader should note that the smile in Figure 16.9 is a plot of the implied volatility against the strike only. Figures 16.12 and 16.13 are plots of the implied volatility against the delta. These curves  

![](images/165eed02322fd1348bb57a3781307782ea3d78d90c41a355a89cbd7bd541002a.jpg)  

# FIGURE 16.12  

![](images/7a88620426fe85492c3db547e19aeeb55790d131e537a05bb5da10cfe4fd7ecd.jpg)  

# FIGURE 16.13  

Risk reversals and curvature of smile.  

relate to a particular time. $t$ and expiration date $T.$ As the latter change, the smile will, in general,.   
shift. It is quite important to know how changes in time $t$ and expiration date $T$ affect the smile.  

# 16.11.3 REPLICATING THE SMILE  

The volatility smile is a plot of the implied volatility of options that are alike in all respects except for their moneyness. The basic shape of the volatility smile has two major characteristics. The first relates to the extent of symmetry in the smile. The second is about how "pronounced" the curvature is. There are good approximations for measuring both characteristics.  

First, consider the issue of symmetry. Figure 16.12 shows three smiles for FX markets. One is symmetric, the other two are asymmetric with different biases. If the smile is symmetric, the volatilities across similarly out-of-the-money puts and calls will be the same. This means that if a trader buys a call and sells a put with the same moneyness, the structure will have zero value. Such positions were called risk reversals in Chapter 11. A symmetric smile implies that a zero cost risk reversal can be achieved by buying and selling similarly out-of-the-money options. In the case of asymmetric smiles, puts and calls with similar moneyness are sold at different implied volatilities, and this is labeled a bias. Thus, a risk reversal is one way of measuring the bias in a volatility smile.  

The way risk reversals measure the symmetry of the volatility smile is shown in Figure 16.13. We use the delta of the option as a measure of its moneyness on the $x$ -axis. ATM options would have a delta of around 50 and would be in the "middle" of the $x$ -axis. The volatility of the 25-delta risk reversal gives the difference between the volatilities of a 25-delta put and a 25-delta call as indicated in the graph. We can write this as  

$$
\sigma(25-d e l t a R R\mathrm{spread})=\sigma(25-d e l t a\mathrm{put})-\sigma(25-d e l t a\mathrm{call})
$$  

where $\sigma(25$ delta $R R$ spread), $\sigma(25$ delta put), and $\sigma$ (25-delta call) indicate, respectively, the implied volatilities of a risk reversal, a 25-delta put, and a 25-delta call.  

![](images/d54c881064089da7182da74d004c0e15aeacf1d22be69ca3f9a76a3d0f26f1dd.jpg)  

# FIGURE 16.14  

Butterfly measures curvature of smile.  

The curvature of the smile can be measured using a butterfly. Consider the sale of an ATM put and an ATM call along with the purchase of one 25-delta out-of-the-money put and a 25-delta outof-the-money call. This butterfly has a payoff diagram that should be familiar from Chapter 11. The position consists of buying two symmetric out-of-the-money volatilities and selling two ATM. volatilities. If there were no smile effects, these volatilities would all be the same and the net volatility position would be zero. On the other hand, the more pronounced the smile becomes, the higher the out-of-the-money volatilities would be relative to the ATM volatilities, and the net volatility position would become more and more positive. Figure 16.14 shows how a butterfly measures the magnitude of the curvature in a smile. The following equality holds:.  

$$
\sigma(25-d e l t a\mathrm{butterflyspread})=\sigma(25-d e l t a\mathrm{put})+\sigma(25-d e l t a\mathrm{call})-2\sigma(\mathrm{ATM})
$$  

where the $\sigma(25$ delta butterfly spread) and $\sigma(\mathrm{ATM})$ are the butterfly and the ATM implied volatili.   
ties, respectively.  

# 16.11.3.1 Contractual equations  

Chapter 3 dealt with contractual equations for simple assets. The equalities discussed in the preceding paragraphs now permit considering quite different types of contractual equations. In fact, we. can rearrange equalities shown in Eqs. (16.60) and (16.61) to generate some contractual equations for out-of-the-money implied volatilities:.  

![](images/1cf5cdea740f8753c2d33e8e13f23c5c54462880c5343ac2b1f6d934aacea64f.jpg)  

These equalities can be used to determine out-of-the-money volatilities in the case of vanilla.   
options. For example, if ATM, RR, and butterfly volatilities are liquid, we can use these equations.   
to "calculate' 25-delta call and put volatilities. However, it has to be noted that for exotic options,.   
adjusting the volatility parameter this way will not work. This issue will be discussed at the end of the chapter.  
