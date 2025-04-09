# 12.4 AN APPLICATION  

The framework based on state prices and elementary insurance contracts is a surprisingly poten1. and realistic pricing tool. Before going any further and obtaining more results from the  

fundamental theorem of asset pricing, we prefer to provide a real-world example. The following reading deals with the S&P500 index and its associated options.  

# EXAMPLE  

The S&P500 is an index of 500 leading stocks from the United States. It is closely.   
monitored by market participants and traded in futures markets. One can buy and sell liquid options written on the S&P500 at the Chicago Board of Options Exchange (CBOE)..   
These options with an expiration date of December 2001 are shown in Table 11.1 as they.   
were quoted on August 10, 2001.  

At the time these data were gathered, the index was at 1187. The three most liquid call options are  

$$
\{1275-\mathrm{Call},1200-\mathrm{Call},1350-\mathrm{Call}\}
$$  

The three most liquid put options, on the other hand, are  

$$
\{1200-\mathrm{Put},1050-\mathrm{Put},900-\mathrm{Put}\}
$$  

Not surprisingly, all the liquid options are out-of-the-money as liquid options generally are.9  

We will now show how this information can be used to obtain (i) the states of the world $\omega^{i}$ (ii) the state prices $Q^{i}$ , and (ii) the corresponding synthetic probabilities associated with. $Q^{i}$ We will do this in the simple setting used thus far..  

# 12.4.1 OBTAINING THE $\omega^{I}$  

A financial engineer always operates in response to a particular kind of problem and the states of the world to be defined relative to the needs, at that time. In our present example we are working with S&P500 options, which means that the focus is on equity markets. Hence, the corresponding states of the world would relate to different states in which the US stock market might be at a future date. Also, we need to take into account that trader behavior singles out a relatively small number of liquid options with expirations of about 3 months. For the following example, refer to Table 12.1.  

<html><body><table><tr><td colspan="6">Table 12.1 S&P500 Option Quotes</td></tr><tr><td>Calls</td><td>Last Sale</td><td>Bid</td><td>Ask</td><td>Volume</td><td>Open Interest</td></tr><tr><td>Dec 1175</td><td>67.1</td><td>68</td><td>70</td><td>51</td><td>1378</td></tr><tr><td>Dec 1200</td><td>46.5</td><td>52.8</td><td>54.8</td><td>150</td><td>8570</td></tr><tr><td>Dec 1225</td><td>41</td><td>40.3</td><td>42.3</td><td>1</td><td>6792</td></tr><tr><td>Dec 1250</td><td>28.5</td><td>29.6</td><td>31.6</td><td>0</td><td>11,873</td></tr><tr><td>Dec 1275</td><td>22.8</td><td>21.3</td><td>23.3</td><td>201</td><td>6979</td></tr><tr><td>Dec 1300</td><td>15.8</td><td>15</td><td>16.2</td><td>34</td><td>16,362</td></tr><tr><td>Dec 1325</td><td>9.5</td><td>10</td><td>11</td><td>0</td><td>9281</td></tr><tr><td>Dec 1350</td><td>6.8</td><td>6.3</td><td>7.3</td><td>125</td><td>8916</td></tr><tr><td>Dec 1375</td><td>4.1</td><td>4</td><td>4.7</td><td>0</td><td>2818</td></tr><tr><td>Dec 1400</td><td>2.5</td><td>2.5</td><td>3.2</td><td>10</td><td>17,730</td></tr><tr><td>Dec 1425</td><td>1.4</td><td>1.4</td><td>1.85</td><td>0</td><td>4464</td></tr><tr><td>Dec 1450</td><td>0.9</td><td>0.8</td><td>1.25</td><td>6</td><td>9383</td></tr><tr><td>Dec 1475</td><td>0.5</td><td>0.35</td><td>0.8</td><td>0</td><td>122</td></tr><tr><td>Puts</td><td>Last Sale</td><td>Bid</td><td>Ask</td><td>Volume</td><td>Open Interest</td></tr><tr><td>Dec 800</td><td>1.65</td><td>1.2</td><td>1.65</td><td>10</td><td>1214</td></tr><tr><td>Dec 900</td><td>4.3</td><td>3.4</td><td>4.1</td><td>24</td><td>11,449</td></tr><tr><td>Dec 950</td><td>5.4</td><td>5.3</td><td>6.3</td><td>10</td><td>8349</td></tr><tr><td>Dec 995</td><td>10.1</td><td>8.5</td><td>9.5</td><td>0</td><td>11,836</td></tr><tr><td>Dec 1025</td><td>13</td><td>11.1</td><td>12.6</td><td>11</td><td>5614</td></tr><tr><td>Dec 1050</td><td>13.6</td><td>14</td><td>15.5</td><td>106</td><td>19,483</td></tr><tr><td>Dec 1060</td><td>16.5</td><td>15.7</td><td>17.2</td><td>1</td><td>1597</td></tr><tr><td>Dec 1075</td><td>22.5</td><td>18</td><td>19.5</td><td>1</td><td>316</td></tr><tr><td>Dec 1100</td><td>26</td><td>22.7</td><td>24.7</td><td>0</td><td>17,947</td></tr><tr><td>Dec 1150</td><td>39</td><td>35.3</td><td>37.3</td><td>2</td><td>16,587</td></tr><tr><td>Dec 1175</td><td>44</td><td>44.1</td><td>46.1</td><td>14</td><td>4897</td></tr><tr><td>Dec 1200</td><td>53</td><td>53.9</td><td>55.9</td><td>897</td><td>26,949</td></tr></table></body></html>  

# EXAMPLE  

We let $S_{T}$ represent the value of the S&P500 at expiration and then use the strike prices $K_{i}$ of the liquid options to define the future states of the world. In fact, strike prices of puts and calls discussed in the preceding example divide the $S_{T}$ axis into intervals of equal length. But only a handful of these options are liquid, implying that fine subdivisions were perhaps not needed by the markets for that day and that particular expiration. Accordingly, we can use the strike prices of the three liquid out-of-the-money puts to obtain the intervals  

$$
\omega^{1}=S_{T}<900
$$  

$$
\omega^{2}=900\leq S_{T}<1050
$$  

$$
\omega^{3}=1050\leq S_{T}<1200
$$  

Note that the liquid puts lead to intervals of equal length. It is interesting, but also expected, that the liquid options have this kind of regularity in their strikes. Next, we use the three out-of-the-money calls to get three intervals to define three additional states of the world as  

$$
\begin{array}{c}{{\omega^{4}=1200\leq S_{T}<1275}}\ {{{}}}\ {{\omega^{5}=1275\leq S_{T}<1350}}\ {{{}}}\ {{\omega^{6}=1350\leq S_{T}}}\end{array}
$$  

Here, the last interval is obtained from the highest strike liquid call option. Figure 12.2. shows these options and the implied intervals. Since these intervals relate to future values of $S_{T}$ we consider them the relevant states of the world for $S_{T}$  

We pick the midpoint of the bounded intervals as an approximation to that particular state. Let these midpoints be denoted by $\{{\overline{{S}}}^{i},i=2,...,5\}$ . These midpoints can then be used as a finite set of points that represent $\omega^{i}$ . For the first and last half-open intervals, we select. the values of the two extreme points, $\overline{{S}}^{1}$ , and $\overline{{S}}^{6}$ , arbitrarily for the time being. We let  

$$
\overline{{S}}^{1}=750
$$  

![](6927f8527df7c9b0d5c59f4d13751b567b9d64644e86d549269e494325fe2e97.jpg)  

# FIGURE 12.2  

Option payoffs and states of the world.  

$$
\overline{{S}}^{6}=1400
$$  

so that the distance between. $\overline{{S}}^{i}$ remains constant. This arbitrary selection of the "end. states" is clearly unsatisfactory. In fact, by doing this we are in a sense setting the volatility of the random variables arbitrarily. We can, however, calibrate our selection. Once our educated guesses are plugged in, we can try to adjust these extreme values so that the. resulting $Q^{i}$ all become positive and price some other liquid asset correctly. In a sense,. calibration is an attempt to see which value of the two "end states" replicates the observed prices. But for the time being, we ignore this issue and assume that the end points are. selected correctly.  

It is open to debate if selecting just six states of the world, as in the example, might represent. future possibilities concerning $S_{T}$ accurately. Traders dealing with the risk in the example must. have thought so, since on that particular date trading approximately six liquid options was sufficient to resolve their tasks. It seems that if a finer subdivision of the future possibilities were more appropriate, then more liquid strikes would have been traded..  

Hence, as usual in financial engineering, the specific values of. $\omega^{i}$ that we select are based on the values of liquid instruments. In our case, the possible states of the world were chosen as dictated by liquid call and put options..  

# 12.4.2 ELEMENTARY CONTRACTS AND OPTIONS  

Elementary insurance contracts $C_{i}$ do not trade directly in world financial markets. Yet, $C_{i}$ are not far from a well-known instrument class options-and they trade "indirectly.' This section shows how elementary insurance contracts can be obtained from options, and vice versa. Plain vanilla options are, in fact, close relatives of elementary insurance contracts. The best way to see this is to consider a numerical example. (Generalizations are straightforward.)  

# EXAMPLE  

Start with the first and last options selected for the previous example. Note that the 900-put is equivalent to $K_{1}-\overline{{S}}^{1}$ units of $C_{1}$ because it pays approximately this many dollars if state $\omega_{1}$ occurs and nothing in all other states. Similarly, the 1350-call is equivalent to $\overline{{S}}^{6}-K_{6}$ units of $C_{6}$ because it pays approximately this many dollars if state 6 occurs and nothing. otherwise.  

The other calls and puts have payoffs in more than one state, but they also relate to elementary contracts in straightforward ways. For example, the 1050-put is equivalent to a portfolio of two elementary insurance contracts, $K_{2}-\overline{{S}}^{1}$ units of $C_{1}$ and $K_{2}-\overline{{S}}^{2}$ units of ${\bf C}_{2}$ because it makes these payments in states 1 and 2, respectively, and nothing else in other states. In fact, pursuing this reasoning, we can obtain the following matrix equation between the payoffs of elementary contracts $\mathrm{C}_{1},...$ $C_{6}$ and the option prices:  

$$
\left[\begin{array}{c}{900-\mathrm{Put}}\ {1050-\mathrm{Put}}\ {1200-\mathrm{Put}}\ {1200-\mathrm{Call}}\ {1200-\mathrm{Call}}\ {1275-\mathrm{Call}}\ {1350-\mathrm{Call}}\ {1350-\mathrm{Call}}\end{array}\right]=\left[\begin{array}{c c c c c c}{z_{1}^{1}}&{0}&{0}&{0}&{0}&{0}\ {z_{2}^{1}}&{z_{2}^{2}}&{0}&{0}&{0}&{0}\ {z_{3}^{1}}&{z_{3}^{2}}&{z_{3}^{3}}&{0}&{0}&{0}\ {0}&{0}&{0}&{z_{4}^{4}}&{z_{4}^{5}}&{z_{4}^{6}}\ {0}&{0}&{0}&{0}&{z_{5}^{5}}&{z_{5}^{6}}\ {0}&{0}&{0}&{0}&{0}&{z_{6}^{6}}\end{array}\right]\left[\begin{array}{c}{C_{1}}\ {C_{2}}\ {C_{3}}\ {C_{4}}\ {C_{5}}\ {C_{6}}\end{array}\right]
$$  

This equation holds since we have  

$$
Q^{i}=C_{i}
$$  

for all i.10  

Thus, given the arbitrage-free values of traded puts and calls with different strikes but similar in. every other aspect, we can easily obtain the values of the elementary insurance contracts $C_{i}$ by inverting the $(6\times6)$ matrix on the right side. In fact, it is interesting to see that the matrix equation. in the example contains two triangular subsystems that can be solved separately and recursively.  

Hence, the existence of liquid options makes a direct application of the fundamental theorem of asset pricing possible. Given a large enough number of liquid option contracts, we can obtain the state prices, $Q^{i}$ , if these exist, and, if they are all positive, use them to price other illiquid assets that depend on the same risk.'' Obviously, when traders deal with interest rate, or exchange rate risk, or when they are interested in pricing contracts on commodities, they would use liquid options for those particular sectors and work with different definitions of the state of the world.  

# 12.4.3 ELEMENTARY CONTRACTS AND REPLICATION  

We now show how elementary insurance contracts and options that belong to a series can be used in replicating instruments with arbitrary payoffs. Consider an arbitrary financial asset, $S_{t}$ that is worth $z_{T}^{i}$ in state of the world $\omega^{i}$ $i=1,...,n$ , at time $T.$ Given $n$ elementary insurance contracts $C_{i}$ we can immediately form a replicating portfolio for this asset. Assuming, without any loss of generality, that the time $T$ payoffs of the $S_{t}$ asset are denoted by $0<z_{T}^{i}$ , we can consider buying the following portfolio:  

$$
\{z_{T}^{1}\mathrm{units~of~}C_{1},z_{T}^{2}\mathrm{units~of~}C_{2},...,z_{T}^{n}\mathrm{units~of~}C_{n}\}
$$  

At time $T$ this portfolio should be worth exactly the same as $S_{t},$ since whatever state occurs, the.   
basket of insurance contracts will make the same time. $T$ payoff as the original asset. This provides.  

an immediate synthetic for $S_{t}$ . Accordingly, if there are no-arbitrage opportunities, the value of the portfolio and the value of $S_{t}$ will be identical as of time $t$ as well.12 We consider an example.  

# EXAMPLE  

Take any four independent assets $S_{k t},k=1,...,4$ with different payoffs, $z_{k}^{i}$ , in the states $\{\omega^{i},i=1,...,4\}$ . We can express each one of these assets in terms of the elementary insurance contracts. In other words, we can find one synthetic for each $S_{k t}$ by purchasing the portfolios:  

$$
\{z_{k}^{1}\mathrm{unit~of~}C_{1},z_{k}^{2}\mathrm{~unit~of~}C_{2},z_{k}^{3}\mathrm{~unit~of~}C_{3},z_{k}^{4}\mathrm{~unit~of~}C_{4}\}
$$  

Putting these in matrix form, we see that arbitrage-free values, $S_{k t_{0}}$ , of these assets at time $t_{0}$ have to satisfy the matrix equation:  

$$
\left[\begin{array}{c}{{1}}\ {{S_{1t_{0}}}}\ {{S_{2t_{0}}}}\ {{S_{3t_{0}}}}\ {{S_{4t_{0}}}}\end{array}\right]=\left[\begin{array}{c c c c c}{{1+r_{t_{0}}}}&{{1+r_{t_{0}}}}&{{1+r_{t_{0}}}}&{{1+r_{t_{0}}}}\ {{z_{1}^{1}}}&{{z_{1}^{2}}}&{{z_{1}^{3}}}&{{z_{1}^{4}}}\ {{z_{2}^{1}}}&{{z_{2}^{2}}}&{{z_{2}^{3}}}&{{z_{2}^{4}}}\ {{z_{3}^{1}}}&{{z_{3}^{2}}}&{{z_{3}^{3}}}&{{z_{3}^{4}}}\ {{z_{4}^{1}}}&{{z_{4}^{2}}}&{{z_{4}^{3}}}&{{z_{4}^{4}}}\end{array}\right]\left[\begin{array}{c}{{Q^{1}}}\ {{Q^{2}}}\ {{Q^{3}}}\ {{Q^{4}}}\end{array}\right]
$$  

where the matrix on the right-hand side contains all possible values of the assets $S_{k t}$ in states $\omega^{i}$ at time $T$ 13  

Hence, given the prices of actively traded elementary contracts $C_{i}.$ we can easily calculate the time $t$ cost of forming the portfolio:.  

$$
\mathrm{Cost}=C_{1}z_{T}^{1}+C_{2}z_{T}^{2}+\dots+C_{n}z_{T}^{n}
$$  

This can be regarded as the cost basis for the $S_{t}$ asset. Adding a proper margin to it will give the fair market price $S_{t}.$  

# EXAMPLE  

Suppose the $S_{t}$ asset has the following payoffs in the states of the world $i=1,...,4$ -..  

$$
\{z_{T}^{1}=10,z_{T}^{2}=1,z_{T}^{2}=14,z_{T}^{2}=16\}
$$  

Then, buying 10 units of the first insurance contract $C_{1}$ will guarantee the 10 in the first. state, and so on.  

Suppose we observe the following prices for the elementary insurance contracts:  

$$
C_{1}=0.3,C_{2}=0.2,C_{3}=0.4,C_{4}=0.07
$$  

Then the total cost of the insurance contracts purchased will be  

$$
\begin{array}{c}{{\mathrm{Cost}=(0.3)10+(0.2)(1)+(0.4)14+(0.07)16}}\ {{{}}}\ {{=9.92}}\end{array}
$$  

This should equal the current price of $S_{t}$ once a proper profit margin is added.  

Clearly, if such elementary insurance contracts actively traded in financial markets, the job of a financial engineer would be greatly simplified. It would be straightforward to construct synthetics for any asset, and then price them using the cost of the replicating portfolios as shown in the example. However, there is a close connection between. $C_{i}$ and options of the same series that differ only in their strikes. We saw how to obtain. $C_{i}$ from liquid option prices. Accordingly, if options. with a broad array of strikes trade in financial markets, then traders can create static replicating portfolios for assets with arbitrary payoffs.14  
