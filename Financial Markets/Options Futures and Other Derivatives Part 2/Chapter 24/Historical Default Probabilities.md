---
tags:
  - '#conditional_probability'
  - '#credit_rating_bbb'
  - '#cumulative_default_rates'
  - '#default_intensity'
  - '#default_probability'
  - '#hazard_rates'
  - '#historical_default_probabilities'
  - '#rating_agencies'
  - '#unconditional_default_probability'
---
# 24.2  HISTORICAL DEFAULT PROBABILITIES  

Table 24.1 is typical of the data produced by rating agencies. It shows the default experience during a 15-year period of bonds that had a particular rating at the beginning of the period. For example, a bond with a credit rating of BBB has a $0.16\%$ chance of defaulting by the end of the first year, a $0.45\%$ chance of defaulting by the end of the second year, and so on. The probability of a bond defaulting during a particular year can be calculated from the table. For example, the probability that a bond initially rated BBB will default during the second year is $0.45\%\mathrm{~-~}0.16\%=0.29\%$  

# Hazard Rates  

From Table 24.1 we can calculate the probability of a bond rated CCC/C defaulting during the third year as $41.41\%\:-\:36.64\%=4.77\%$ . We will refer to this as the unconditional default probability. It is the probability of default during the third year as seen today. The probability that the bond will survive until the end of year 2 is $100\%\:-\:36.64\%=63.36\%$ . The probability that it will default during the third year conditional on no earlier default is therefore $0.0477/0.6336$ or $7.53\%$  

The $7.53\%$ we have just calculated is a conditional probability for a 1-year time period. Suppose instead that we consider a short time period of length $\Delta t$ The hazard rate $\lambda(t)$ at time $t$ is defined so that $\lambda(t)\Delta t$ is the probability of default between time. $t$ and $t+\Delta t$ conditional on no earlier default..  

If $V(t)$ is the cumulative probability of the company surviving to time $t$ (i.e., no default by time $t_{,}$ , the conditional probability of default between time $t$ and $t+\Delta t$ is $[V(t)~-~V(t+\Delta t)]/V(t)$ Since this equals $\lambda(t)\Delta t_{}$ it follows that  

$$
V(t+\Delta t)-V(t)=-\lambda(t)V(t)\Delta t
$$  

Taking limits  

$$
\frac{d V(t)}{d t}=-\lambda(t)V(t)
$$  

from which  

$$
V(t)=e^{-\int_{0}^{t}\lambda(\tau)d\tau}
$$  

Table 24.1 Average cumulative default rates $(\%)$ , 1981-2019 (Source: S&P Global Ratings Research and S&P Global Market Intelligence's CreditPro).   


<html><body><table><tr><td rowspan="2">Rating</td><td colspan="8">Time (years)</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>7</td><td>10</td><td>15</td></tr><tr><td>AAA</td><td>0.00</td><td>0.03</td><td>0.13</td><td>0.24</td><td>0.35</td><td>0.51</td><td>0.70</td><td>0.91</td></tr><tr><td>AA</td><td>0.02</td><td>0.06</td><td>0.12</td><td>0.21</td><td>0.31</td><td>0.50</td><td>0.72</td><td>1.02</td></tr><tr><td>A</td><td>0.05</td><td>0.14</td><td>0.23</td><td>0.35</td><td>0.47</td><td>0.79</td><td>1.24</td><td>1.89</td></tr><tr><td>BBB</td><td>0.16</td><td>0.45</td><td>0.78</td><td>1.17</td><td>1.58</td><td>2.33</td><td>3.32</td><td>4.69</td></tr><tr><td>BB</td><td>0.61</td><td>1.92</td><td>3.48</td><td>5.05</td><td>6.52</td><td>9.01</td><td>11.78</td><td>14.67</td></tr><tr><td>B</td><td>3.33</td><td>7.71</td><td>11.55</td><td>14.58</td><td>16.93</td><td>20.36</td><td>23.74</td><td>27.12</td></tr><tr><td>CCC/C</td><td>27.08</td><td>36.64</td><td>41.41</td><td>44.10</td><td>46.19</td><td>48.26</td><td>50.38</td><td>52.59</td></tr></table></body></html>  

Defining $Q(t)$ as the probability of default by time $t$ , so that $Q(t)=1-V(t)$ gives  

$$
Q(t)=1-e^{-\int_{0}^{t}\lambda(\tau)d\tau}
$$  

or  

$$
Q(t)=1-e^{-\overline{{{\lambda}}}(t)t}
$$  

where $\overline{{\lambda}}(t)$ is the average hazard rate between time 0 and time $t$ Another term used for.   
the hazard rate is default intensity..  
