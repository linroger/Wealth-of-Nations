---
tags:
  - '#american_put_option'
  - '#change_of_variable'
  - '#crank_nicolson_method'
  - '#explicit_finite_difference'
  - '#finite_difference_methods'
  - '#hopscotch_method'
  - '#implicit_finite_difference'
  - '#numerical_methods'
  - '#option_pricing'
  - '#trinomial_tree'
---
# 21.8 FINITE DIFFERENCE METHODS  

Finite difference methods value a derivative by solving the differential equation that the derivative satisfies. The differential equation is converted into a set of difference equations, and the difference equations are solved iteratively.  

To illustrate the approach, we consider how it might be used to value an American put option on a stock paying a dividend yield of $q$ . The differential equation that the option must satisfy is, from equation (17.6),  

$$
\frac{\partial f}{\partial t}+(r-q)S\frac{\partial f}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}f}{\partial S^{2}}=r f
$$  

Suppose that the life of the option is $T$ We divide this into $N$ equally spaced intervals of length $\Delta t=T/N.$ A total of $N+1$ times are therefore considered  

$$
0,\Delta t,2\Delta t,\dots,T
$$  

Suppose that $S_{\mathrm{max}}$ is a stock price sufficiently high that, when it is reached, the put has virtually no value. We define $\Delta S=S_{\operatorname*{max}}/M$ and consider a total of $M+1$ equally spaced stock prices:  

$$
0,\Delta S,2\Delta S,\ldots,S_{\mathrm{max}}
$$  

The level $S_{\mathrm{max}}$ is chosen so that one of these is the current stock price.  

![](6facc8a1d79ed4b8d6309548f063322e92cbbfa30849342642ff1bedb6b15596.jpg)  
Figure 21.14 First 1,024 points of a Sobol' sequence.  

The time points and stock price points define a grid consisting of a total of $(M+1)(N+1)$ points, as shown in Figure 21.15. We define the. $(i,j)$ point on the grid as the point that corresponds to time $i\Delta t$ and stock price $j\Delta S$ We will use the variable $f_{i,j}$ to denote the value of the option at the $(i,j)$ point.  

# Implicit Finite Difference Method  

For an interior point. $(i,j)$ on the grid,. $\partial f/\partial S$ can be approximated as  

$$
\frac{\partial f}{\partial S}=\frac{f_{i,j+1}-f_{i,j}}{\Delta S}
$$  

or as  

$$
\frac{\partial f}{\partial S}=\frac{f_{i,j}-f_{i,j-1}}{\Delta S}
$$  

Equation (21.22) is known as the forward difference approximation, equation (21.23) is known as the backward difference approximation. We use a more symmetrical  

approximation by averaging the two:  

$$
\frac{\partial f}{\partial S}=\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta S}
$$  

For $\partial f/\partial t$ we will use a forward difference approximation so that the value at time $i\Delta t$ is related to the value at time $(i+1)\Delta t$  

$$
\frac{\partial f}{\partial t}=\frac{f_{i+1,j}-f_{i,j}}{\Delta t}
$$  

Consider next $\partial^{2}f/\partial S^{2}$ . The backward difference approximation for. $\partial f/\partial S$ at the $(i,j)$ point is given by equation (21.23). The backward difference at the $(i,j+1)$ point is  

$$
\frac{f_{i,j+1}-f_{i,j}}{\Delta S}
$$  

Hence a finite difference approximation for $\partial^{2}f/\partial S^{2}$ at the $(i,j)$ point is  

$$
\frac{\partial^{2}f}{\partial S^{2}}=\left(\frac{f_{i,j+1}-f_{i,j}}{\Delta S}-\frac{f_{i,j}-f_{i,j-1}}{\Delta S}\right)\bigg/\Delta S
$$  

or  

$$
\frac{\partial^{2}f}{\partial S^{2}}=\frac{f_{i,j+1}+f_{i,j-1}-2f_{i,j}}{\Delta S^{2}}
$$  

![](67d0720e88153bc1d9b02690300dc8411ccd6e6350fa578b4d2b383c9a3a0161.jpg)  
Figure 21.15 Grid for finite difference approach.  

Substituting equations (21.24), (21.25), and (21.26) into the differential equation (21.21) and noting that $S=j\Delta S$ gives  

$$
\frac{f_{i+1,j}-f_{i,j}}{\Delta t}+(r-q)j\Delta S\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta S}+\frac{1}{2}\sigma^{2}j^{2}\Delta S^{2}\frac{f_{i,j+1}+f_{i,j-1}-2f_{i,j}}{\Delta S^{2}}=r f_{i,j}
$$  

for $j=1,2,\dots,M-1$ and $i=0,1,\ldots,N-1$ Rearranging terms, we obtain  

$$
a_{j}f_{i,j-1}+b_{j}f_{i,j}+c_{j}f_{i,j+1}=f_{i+1,j}
$$  

where  

$$
\begin{array}{l}{{a_{j}=\frac{1}{2}(r-q)j\Delta t-\frac{1}{2}\sigma^{2}j^{2}\Delta t}}\ {{b_{j}=1+\sigma^{2}j^{2}\Delta t+r\Delta t}}\ {{c_{j}=-\frac{1}{2}(r-q)j\Delta t-\frac{1}{2}\sigma^{2}j^{2}\Delta t}}\end{array}
$$  

The value of the put at time $T\mathrm{is}\operatorname*{max}(K-S_{T},0)$ , where $S_{T}$ is the stock price at time $T$ Hence,  

$$
f_{N,j}=\operatorname*{max}(K-j\Delta S,0),~j=0,1,~\dots,M
$$  

The value of the put option when the stock price is zero is $K$ Hence,  

$$
f_{i,0}=K,i=0,1,...,N
$$  

We assume that the put option is worth zero when $S=S_{\mathrm{max}}$ , so that  

$$
f_{i,M}=0,i=0,1,...,N
$$  

Equations (21.28), (21.29), and (21.30) define the value of the put option along the three edges of the grid in Figure 21.15, where $S=0,S=S_{\mathrm{max}}$ and $t=T.$ It remains to use equation (21.27) to arrive at the value of $f$ at all other points. First the points corresponding to time $T-\Delta t$ are tackled. Equation (21.27) with $i=N-1$ gives  

$$
a_{j}f_{N-1,j-1}+b_{j}f_{N-1,j}+c_{j}f_{N-1,j+1}=f_{N,j}
$$  

for $j=1,2,\dots,M-1$ . The right-hand sides of these equations are known from equation (21.28). Furthermore, from equations (21.29) and (21.30),  

$$
\begin{array}{l}{f_{N-1,0}=K}\ {}\ {f_{N-1,M}=0}\end{array}
$$  

Equations (21.31) are therefore $M-1$ simultaneous equations that can be solved for the $M-1$ unknowns: $f_{N-1,1},f_{N-1,2}$ $\cdots,f_{N-1,M-1}$ 22 After this has been done, each value of $f_{N-1,j}$ is compared with $K-j\Delta S$ If $f_{N-1,j}<K-j\Delta S$ , early exercise at time $T-\Delta t$ is optimal and $f_{N-1,j}$ is set equal to $K-j\Delta S$ The nodes corresponding to time $T-2\Delta t$ are handled in a similar way, and so on. Eventually, $f_{0,1},f_{0,2},f_{0,3},\ldots$ $f_{0,M-1}$ are obtained. One of these is the option price of interest.  

The control variate technique can be used in conjunction with finite difference. methods. The same grid is used to value an option similar to the one under. consideration but for which an analytic valuation is available. Equation (21.20) is then used.  

# Example 21.10  

Table 21.4 shows the result of using the implicit finite difference method as just described for pricing the American put option in Example 21.1. Values of 20, 10, and 5 were chosen for $M,N,$ and $\Delta S$ , respectively. Thus, the option price is evaluated at $\$5$ stock price intervals between $\$0$ and $\$100$ and at half-month time intervals throughout the life of the option. The option price given by the grid is $\$4.07$ . The same grid gives the price of the corresponding European option as $\$3.91$ . The true European price given by the Black-Scholes-Merton formula is $\$4.08$ The control variate estimate of the American price is therefore  

$$
4.07+(4.08-3.91)=\S4.24
$$  

# Explicit Finite Difference Method  

The implicit finite difference method has the advantage of being very robust. It always converges to the solution of the differential equation as. $\Delta S$ and $\Delta t$ approach zero.23 One of the disadvantages of the implicit finite difference method is that. $M-1$ simultaneous equations have to be solved in order to calculate the $f_{i,j}$ from the $f_{i+1,j}.$ The method can be simplified if the values of $\partial f/\partial S$ and $\partial^{2}f/\partial S^{2}$ at point $(i,j)$ on the grid are assumed to be the same as at point $(i+1,j)$ . Equations (21.24) and (21.26) then become  

$$
\begin{array}{r l}&{\frac{\partial f}{\partial S}=\frac{f_{i+1,j+1}-f_{i+1,j-1}}{2\Delta S}}\ &{\frac{\partial^{2}f}{\partial S^{2}}=\frac{f_{i+1,j+1}+f_{i+1,j-1}-2f_{i+1,j}}{{\Delta S^{2}}}}\end{array}
$$  

The difference equation is  

$$
\frac{f_{i+1,j}-f_{i,j}}{\Delta t}+(r-q)j\Delta S\frac{f_{i+1,j+1}-f_{i+1,j-1}}{2\Delta S}
$$  

or  

$$
f_{i,j}=a_{j}^{*}f_{i+1,j-1}+b_{j}^{*}f_{i+1,j}+c_{j}^{*}f_{i+1,j+1}
$$  

Table 21.4 Grid to value American option in Example 21.1 using implicit finite difference methods.   


<html><body><table><tr><td rowspan="2">Stock price (dollars)</td><td colspan="11">Ods. Time to maturity (months)</td></tr><tr><td>5</td><td>4.5</td><td>4</td><td>3.5</td><td>3</td><td>2.5</td><td>2</td><td></td><td>1.5</td><td>1</td><td>0.5</td><td>0</td></tr><tr><td>100</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>95</td><td>0.02</td><td>0.02</td><td>0.01</td><td>0.01</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>90</td><td>0.05</td><td>0.04</td><td>0.03</td><td>0.02</td><td>0.01</td><td>0.01</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>85</td><td>0.09</td><td>0.07</td><td>0.05</td><td>0.03</td><td>0.02</td><td>0.01</td><td></td><td>0.01</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>80</td><td>0.16</td><td>0.12</td><td>0.09</td><td>0.07</td><td>0.04</td><td></td><td>0.03</td><td>0.02</td><td>0.01</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>75</td><td>0.27</td><td>0.22</td><td>0.17</td><td>0.13</td><td>0.09</td><td></td><td>0.06</td><td>0.03</td><td>0.02</td><td>0.01</td><td>0.00</td><td>0.00</td></tr><tr><td>70</td><td>0.47</td><td>0.39</td><td>0.32</td><td>0.25</td><td>0.18</td><td></td><td>0.13</td><td>0.08</td><td>0.04</td><td>0.02</td><td>0.00</td><td>0.00</td></tr><tr><td>65</td><td>0.82</td><td>0.71</td><td>0.60</td><td>0.49</td><td>0.38</td><td></td><td>0.28</td><td>0.19</td><td>0.11</td><td>0.05</td><td>0.02</td><td>0.00</td></tr><tr><td>60</td><td>1.42</td><td>1.27</td><td>1.11</td><td>0.95</td><td>0.78</td><td></td><td>0.62</td><td>0.45</td><td>0.30</td><td>0.16</td><td>0.05</td><td>0.00</td></tr><tr><td>55</td><td>2.43</td><td>2.24</td><td>2.05</td><td>1.83</td><td>1.61</td><td></td><td>1.36</td><td>1.09</td><td>0.81</td><td>0.51</td><td>0.22</td><td>0.00</td></tr><tr><td>50</td><td>4.07</td><td>3.88</td><td>3.67</td><td>3.45</td><td>3.19</td><td></td><td>2.91</td><td>2.57</td><td>2.17</td><td>1.66</td><td>0.99</td><td>0.00</td></tr><tr><td>45</td><td>6.58</td><td>6.44</td><td>6.29</td><td>6.13</td><td>5.96</td><td></td><td>5.77</td><td>5.57</td><td>5.36</td><td>5.17</td><td>5.02</td><td>5.00</td></tr><tr><td>40</td><td>10.15</td><td>10.10</td><td>10.05</td><td>10.01</td><td>10.00</td><td>10.00</td><td></td><td>10.00</td><td>10.00</td><td>10.00</td><td>10.00</td><td>10.00</td></tr><tr><td>35</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td></td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td></tr><tr><td>30</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td></td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td></tr><tr><td>25</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td></td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td></tr><tr><td>20</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td></td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td></tr><tr><td>15</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td></td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td></tr><tr><td>10</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td></td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td></tr><tr><td>5</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td></td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td></tr><tr><td>0</td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td></td><td>50.00</td><td>50.00</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>50.00</td><td>50.00</td><td>50.00</td></tr></table></body></html>  

where  

$$
\begin{array}{l}{{a_{j}^{*}=\displaystyle\frac{1}{1+r\Delta t}(-\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t)}}\ {{\mathrm{}}}\ {{b_{j}^{*}=\displaystyle\frac{1}{1+r\Delta t}(1-\sigma^{2}j^{2}\Delta t)}}\ {{c_{j}^{*}=\displaystyle\frac{1}{1+r\Delta t}(\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t)}}\end{array}
$$  

This creates what is known as the explicit finite difference method.24 Figure 21.16 shows. the difference between the implicit and explicit methods. The implicit method leads to equation (21.27), which gives a relationship between three different values of the option at time $i\Delta t$ (i.e., $f_{i,j-1},f_{i,j},$ and $f_{i,j+1})$ and one value of the option at time $(i+1)\Delta t$ (i.e., $f_{i+1,j})$ . The explicit method leads to equation (21.34), which gives a relationship between one value of the option at time i $\Delta t$ (i.e., $f_{i,j})$ and three different values of the option at time $(i+1)$ $\Delta t$ (i.e., $f_{i+1,j-1},f_{i+1,j},f_{i+1,j+1})$  

![](213e3387d663e5465ea5ddf634a6e346a387882b3b1f6d2fda705bc6a4c09b05.jpg)  
Figure 21.16 Difference between implicit and explicit finite difference methods.  

# Example 21.11  

Table 21.5 shows the result of using the explicit version of the finite difference method for pricing the American put option described in Example 21.1. As in Example 21.10, values of 20, 10, and 5 were chosen for. $M,N.$ and $\Delta S$ , respectively. The option price given by the grid is. $\$4.26$ 25  

# Change of Variable  

When geometric Brownian motion is used for the underlying asset price, it is computationally more efficient to use finite difference methods with ln. $S$ rather than $S$ as the underlying variable. Define $Z=\ln S$ Equation (21.21) becomes  

$$
\frac{\partial f}{\partial t}+\left(r-q-\frac{\sigma^{2}}{2}\right)\frac{\partial f}{\partial Z}+\frac{_1}{2}\sigma^{2}\frac{\partial^{2}f}{\partial Z^{2}}=r f
$$  

The grid then evaluates the derivative for equally spaced values of $Z$ rather than for equally spaced values of. $S$ . The difference equation for the implicit method becomes.  

$$
\frac{f_{i+1,j}-f_{i,j}}{\Delta t}+(r-q-\sigma^{2}/2)\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta Z}+\frac{1}{2}\sigma^{2}\frac{f_{i,j+1}+f_{i,j-1}-2f_{i,j}}{\Delta Z^{2}}=r f_{i,j}
$$  

or  

$$
\alpha_{j}f_{i,j-1}+\beta_{j}f_{i,j}+\gamma_{j}f_{i,j+1}=f_{i+1,j}
$$  

Table 21.5 Grid to value American option in Example 21.1 using explicit finite difference methods.   


<html><body><table><tr><td rowspan="2">Stock price (dollars)</td><td colspan="11">Time to maturity (months)</td></tr><tr><td>5</td><td>4.5</td><td>4</td><td>3.5</td><td>3</td><td>2.5</td><td>2</td><td>1.5</td><td></td><td>1 0.5</td><td></td><td>0</td></tr><tr><td>100</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>95</td><td>0.06</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>90</td><td>-0.11</td><td>0.05</td><td>0.00</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>85</td><td>0.28</td><td>0.05</td><td>0.05</td><td>0.00</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>80</td><td>- 0.13</td><td>0.20</td><td>0.00</td><td>0.05</td><td>0.00</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>75</td><td>0.46</td><td>0.06</td><td>0.20</td><td>0.04</td><td>0.06</td><td></td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>70</td><td>0.32</td><td>0.46</td><td>0.23</td><td>0.25</td><td>0.10</td><td></td><td>0.09</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>65</td><td>0.91</td><td>0.68</td><td>0.63</td><td>0.44</td><td>0.37</td><td></td><td>0.21</td><td>0.14</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>60</td><td>1.48</td><td>1.37</td><td>1.17</td><td>1.02</td><td>0.81</td><td></td><td>0.65</td><td>0.42</td><td>0.27</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>55</td><td>2.59</td><td>2.39</td><td>2.21</td><td>1.99</td><td>1.77</td><td></td><td>1.50</td><td>1.24</td><td>0.90</td><td>0.59</td><td>0.00</td><td>0.00</td></tr><tr><td>50</td><td>4.26</td><td>4.08</td><td>3.89</td><td>3.68</td><td>3.44</td><td></td><td>3.18</td><td>2.87</td><td>2.53</td><td>2.07</td><td>1.56</td><td>0.00</td></tr><tr><td>45</td><td>6.76</td><td>6.61</td><td>6.47</td><td>6.31</td><td>6.15</td><td></td><td>5.96</td><td>5.75</td><td>5.50</td><td>5.24</td><td>5.00</td><td>5.00</td></tr><tr><td>40</td><td>10.28</td><td>10.20</td><td>10.13</td><td>10.06</td><td>10.01</td><td>10.00</td><td></td><td>10.00</td><td>10.00</td><td>10.00</td><td>10.00</td><td>10.00</td></tr><tr><td>35</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td></td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td><td>15.00</td></tr><tr><td>30</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td></td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td></tr><tr><td>25</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td></td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td><td>25.00</td></tr><tr><td>20</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td></td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td></tr><tr><td>15</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td></td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td><td>35.00</td></tr><tr><td>10</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td></td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td></tr><tr><td>5</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td></td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td><td>45.00</td></tr><tr><td>0</td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td></td><td>50.00</td><td>50.00</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td></tr></table></body></html>  

where  

$$
\begin{array}{l}{\displaystyle\alpha_{j}=\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)-\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}}\ {\displaystyle\beta_{j}=1+\frac{\Delta t}{\Delta Z^{2}}\sigma^{2}+r\Delta t}\ {\displaystyle\gamma_{j}=-\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)-\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}}\end{array}
$$  

The difference equation for the explicit method becomes  

$$
\frac{f_{i+1,j}-f_{i,j}}{\Delta t}+(r-q-\sigma^{2}/2)\frac{f_{i+1,j+1}-f_{i+1,j-1}}{2\Delta Z}+\frac{1}{2}\sigma^{2}\frac{f_{i+1,j+1}+f_{i+1,j-1}-2f_{i+1,j}}{\Delta Z^{2}}=r f_{i,j}-f_{i+1,j+1}
$$  

or  

$$
\alpha_{j}^{*}{f_{i+1,j-1}}+\beta_{j}^{*}{f_{i+1,j}}+\gamma_{j}^{*}{f_{i+1,j+1}}=f_{i,j}
$$  

where  

$$
\begin{array}{l}{\displaystyle\alpha_{j}^{*}=\frac{1}{1+r\Delta t}\Biggl[-\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)+\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}\Biggr]}\ {\displaystyle\beta_{j}^{*}=\frac{1}{1+r\Delta t}\Biggl(1-\frac{\Delta t}{\Delta Z^{2}}\sigma^{2}\Biggr)}\ {\displaystyle\gamma_{j}^{*}=\frac{1}{1+r\Delta t}\Biggl[\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)+\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}\Biggr]}\end{array}
$$  

The change of variable approach has the property that $\alpha_{j},\beta_{j}$ and $\gamma_{j}$ as well as $\alpha_{j}^{*},\beta_{j}^{*}$ and $\gamma_{j}^{\ast}$ are independent of. $j$ In most cases, a good choice for. $\Delta Z$ is $\overset{\cdot\prime}{\sigma}\sqrt{3\Delta t}$  

# Relation to Trinomial Tree Approaches  

The explicit finite difference method is equivalent to the trinomial tree approach.26 In the expressions for $a_{j}^{*},b_{j}^{*}$ and $c_{j}^{*}$ in equation (21.34), we can interpret terms as follows:  

$\begin{array}{r l}&{-\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t:}\ &{}\ &{1-\sigma^{2}j^{2}\Delta t:}\ &{}\ &{\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t:}\end{array}$ Probability of stock price decreasing from $j\Delta S$ to $(j-1)\Delta S$ in time $\Delta t$ Probability of stock price remaining unchanged at $j\Delta S$ in time $\Delta t$ Probability of stock price increasing from $j\Delta S$ to $(j+1)\Delta S$ in time $\Delta t$  

This interpretation is illustrated in Figure 21.17. The three probabilities sum to unity. They give the expected increase in the stock price in time. $\Delta t$ as $(r-q)j\Delta S\Delta t=$ $(r-q)S\Delta t$ . This is the expected increase in a risk-neutral world. For small values of $\Delta t$ they also give the variance of the change in the stock price in time $\Delta t$ as $\sigma^{2}j^{2}\Delta S^{2}\Delta\dot{t}=\sigma^{2}\bar{S^{2}}\Delta t.$ This corresponds to the stochastic process followed by $S$ The value of $f$ at time i $\Delta t$ is calculated as the expected value of $f$ at time $(i+1)\Delta t$ in a risk-neutral world discounted at the risk-free rate..  

![](671ef148039f0a3d20e19232f13a3732814cfd487f8ec0a1a3742c3bdb3b30c2.jpg)  
Figure 21.17 Interpretation of explicit finite difference method as a trinomial tree.  

For the explicit version of the finite difference method to work well, the three "probabilities"  

$$
\begin{array}{r}{-\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t,}\ {1-\sigma^{2}j^{2}\Delta t\qquad}\ {\frac{1}{2}(r-q)j\Delta t+\frac{1}{2}\sigma^{2}j^{2}\Delta t}\end{array}
$$  

should all be positive. In Example $21.11,1-\sigma^{2}j^{2}\Delta t$ is negative when $j\ge13$ (i.e., when $S\ge65$ ). This explains the negative option prices and other inconsistencies in the top left-hand part of Table 21.5. This example illustrates the main problem associated with the explicit finite difference method. Because the probabilities in the associated tree may be negative, it does not necessarily produce results that converge to the solution of the differential equation.27  

When the change-of-variable approach is used (see equations (21.36) to (21.39), the probability that $Z=\ln S$ will decrease by $\Delta Z$ , stay the same, and increase by. $\Delta Z$ are  

$$
\begin{array}{c}{\displaystyle-\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)+\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}}\ {\displaystyle1-\frac{\Delta t}{\Delta Z^{2}}\sigma^{2}}\ {\displaystyle\frac{\Delta t}{2\Delta Z}(r-q-\sigma^{2}/2)+\frac{\Delta t}{2\Delta Z^{2}}\sigma^{2}}\end{array}
$$  

respectively. These movements in $Z$ correspond to the stock price changing from $S$ to $S e^{-\Delta Z},S$ and $S e^{\Delta Z}$ respectively. If we set $\Delta Z=\sigma\sqrt{3\Delta t}$ then the tree and the. probabilities are identical to those for the trinomial tree approach discussed in Section 21.4.  

# Other Finite Difference Methods  

Researchers have proposed other finite difference methods which are in many circumstances more computationally efficient than either the pure explicit or pure implicit method.  

In what is known as the hopscotch method, we alternate between the explicit and implicit calculations as we move from node to node. This is illustrated in Figure 21.18. At each time, we first do all the calculations at the "explicit nodes" (E) in the usual way. The "implicit nodes" (I) can then be handled without solving a set of simultaneous equations because the values at the adjacent nodes have already been calculated.  

![](428ad86de6453d8f420f7f453104967ab11584afc9d5394ed5658ff8442cbb42.jpg)  
Figure 21.18 The hopscotch method. I indicates node at which implicit calculations are done; E indicates node at which explicit calculations are done..  

In the Crank-Nicolson method, the estimate of  

$$
\frac{f_{i+1,j}-f_{i,j}}{\Delta t}
$$  

is set equal to an average of that given by the implicit and the explicit methods.  

# Applications of Finite Difference Methods  

Finite difference methods can be used for the same types of derivative pricing problems.   
as tree approaches. They can handle American-style as well as European-style deriva-.   
tives but cannot easily be used in situations where the payoff from a derivative depends.   
on the past history of the underlying variable. Finite difference methods can, at the expense of a considerable increase in computer time, be used when there are several.   
state variables. The grid in Figure 21.15 then becomes multidimensional..  

The method for calculating Greek letters is similar to that used for trees. Delta, gamma, and theta can be calculated directly from the $f_{i,j}$ values on the grid. For vega, it is necessary to make a small change to volatility and recalculate the value of the derivative using the same grid.  

# SUMMARY  

We have presented three different numerical procedures for valuing derivatives when no. analytic solution is available. These involve the use of trees, Monte Carlo simulation, and finite difference methods.  

Binomial trees assume that, in each short interval of time $\Delta t$ , a stock price either moves up by a multiplicative amount $u$ or down by a multiplicative amount $d$ . The sizes of $u$ and $d$ and their associated probabilities are chosen so that the change in the stock price has the correct mean and standard deviation in a risk-neutral world. Derivative prices are calculated by starting at the end of the tree and working backward. For an American option, the value at a node is the greater of (a) the value if it is exercised immediately and (b) the discounted expected value if it is held for a further period of time $\Delta t$  

Monte Carlo simulation involves using random numbers to sample many different. paths that the variables underlying the derivative could follow in a risk-neutral world.. For each path, the payoff is calculated and discounted at the risk-free interest rate. The arithmetic average of the discounted payoffs is the estimated value of the derivative..  

Finite difference methods solve the underlying differential equation by converting it to a difference equation. They are similar to tree approaches in that the computations work back from the end of the life of the derivative to the beginning. The explicit finite difference method is functionally the same as using a trinomial tree. The implicit finite difference method is more complicated but has the advantage that the user does not have to take any special precautions to ensure convergence.  

In practice, the method that is chosen is likely to depend on the characteristics of the derivative being evaluated and the accuracy required. Monte Carlo simulation works forward from the beginning to the end of the life of a derivative. It can be used for European-style derivatives and can cope with a great deal of complexity as far as the payoffs are concerned. It becomes relatively more efficient as the number of underlying variables increases. Tree approaches and finite difference methods work from the end of the life of a security to the beginning and can accommodate American-style as well as European-style derivatives. However, they are difficult to apply when the payoffs depend on the past history of the state variables as well as on their current values. Also, they are liable to become computationally very time consuming when three or more variables are involved.  

# FURTHER READING  

# General  

Clewlow, L., and C. Strickland, Implementing Derivatives Models. Chichester: Wiley, 1998.   
Press, W. H., S. A. Teukolsky, W. T. Vetterling, and B. P. Flannery, Numerical Recipes in C: The Art of Scientific Computing, 3rd edn. Cambridge University Press, 2007.   
On Tree Approaches   
Cox, J. C, S. A. Ross, and M. Rubinstein. "Option Pricing: A Simplified Approach,' Journal of Financial Economics, 7 (October 1979): 229-64.   
Figlewski, S., and B. Gao. "The Adaptive Mesh Model: A New Approach to Efficient Option Pricing," Journal of Financial Economics, 53 (1999): 313-51.   
Hull, J. C., and A. White, "The Use of the Control Variate Technique in Option Pricing," Journal of Financial and Quantitative Analysis, 23 (September 1988): 237-51.   
Rendleman, R., and B. Bartter, "Two State Option Pricing," Journal of Finance, 34 (1979): 1092-1110.   
On Monte Carlo Simulation   
Boyle, P. P., "Options: A Monte Carlo Approach," Journal of Financial Economics, 4 (1977): 323-38.   
Boyle, P. P., M. Broadie, and P. Glasserman. "Monte Carlo Methods for Security Pricing, Journal of Economic Dynamics and Control, 21 (1997): 1267-1322.   
Broadie, M., P. Glasserman, and G. Jain. "Enhanced Monte Carlo Estimates for American Option Prices," Journal of Derivatives, 5 (Fall 1997): 25-44.   
On Finite Difference Methods   
Hull, J. C., and A. White, "Valuing Derivative Securities Using the Explicit Finite Difference Method," Journal of Financial and Quantitative Analysis, 25 (March 1990): 87-100.   
Wilmott, P., Derivatives: The Theory and Practice of Financial Engineering. Chichester: Wiley, 1998.  

# Practice Questions  

21.1. Which of the following can be estimated for an American option by constructing a single binomial tree: delta, gamma, vega, theta, rho?.   
21.2. Calculate the price of a 3-month American put option on a non-dividend-paying stock when the stock price is. $\$60$ , the strike price is. $\$60$ , the risk-free interest rate is. $10\%$ per annum, and the volatility is $45\%$ per annum. Use a binomial tree with a time interval of. 1 month.   
21.3. Explain how the control variate technique is implemented when a tree is used to value American options.   
21.4. Calculate the price of a 9-month American call option on corn futures when the current futures price is 198 cents, the strike price is 200 cents, the risk-free interest rate is $8\%$ per annum, and the volatility is $30\%$ per annum. Use a binomial tree with a time interval of 3 months.   
21.5. Consider an option that pays off the amount by which the final stock price exceeds the. average stock price achieved during the life of the option. Can this be valued using the binomial tree approach? Explain your answer..   
21.6. "For a dividend-paying stock, the tree for the stock price does not recombine; but the tree for the stock price less the present value of future dividends does recombine." Explain this statement..   
21.7. Show that the probabilities in a Cox, Ross, and Rubinstein binomial tree are negative. when the condition in footnote 8 holds.   
21.8. Use stratified sampling with 100 trials to improve the estimate of $\pi$ in Business Snapshot 21.1 and Table 21.1.   
21.9. Explain why the Monte Carlo simulation approach cannot easily be used for Americanstyle derivatives.   
21.10. A 9-month American put option on a non-dividend-paying stock has a strike price o $\$49$ . The stock price is $\$50$ , the risk-free rate is $5\%$ per annum, and the volatility is. $30\%$ per annum. Use a three-step binomial tree to calculate the option price.   
21.11. Use a three-time-step binomial tree to value a 9-month American call option on wheat futures. The current futures price is 400 cents, the strike price is 420 cents, the risk-free rate. is $6\%$ , and the volatility is $35\%$ per annum. Estimate the delta of the option from your tree.   
21.12. A 3-month American call option on a stock has a strike price of $\$20$ The stock price is $\$20$ the risk-free rate is $3\%$ per annum, and the volatility is $25\%$ per annum. A dividend of $\$2$ is expected in 1.5 months. Use a three-step binomial tree to calculate the option price.  

21.13. A 1-year American put option on a non-dividend-paying stock has an exercise price of. $\$18$ . The current stock price is $\$20$ , the risk-free interest rate is $15\%$ per annum, and the volatility of the stock price is $40\%$ per annum. Use the DerivaGem software with four. 3-month time steps to estimate the value of the option. Display the tree and verify that. the option prices at the final and penultimate nodes are correct. Use DerivaGem to value the European version of the option. Use the control variate technique to improve your estimate of the price of the American option.  

21.14. A 2-month American put option on a stock index has an exercise price of 480. The current level of the index is 484, the risk-free interest rate is. $10\%$ per annum, the dividend yield on the index is. $3\%$ per annum, and the volatility of the index is. $25\%$ per annum. Divide the life of the option into four half-month periods and use the tree approach to estimate the value of the option.  

21.15. How can the control variate approach improve the estimate of the delta of an American option when the tree approach is used?  

21.16. Suppose that Monte Carlo simulation is being used to evaluate a European call option. on a non-dividend-paying stock when the volatility is stochastic. How could the control variate and antithetic variable technique be used to improve numerical efficiency? Explain why it is necessary to calculate six values of the option in each simulation trial when both the control variate and the antithetic variable technique are used..  

21.17. How do equations (21.27) to (21.30) change when the implicit finite difference method is being used to evaluate an American call option on a currency?  

21.18. An American put option on a non-dividend-paying stock has 4 months to maturity. The exercise price is $\$21$ , the stock price is $\$20$ , the risk-free rate of interest is. $10\%$ per annum, and the volatility is $30\%$ per annum. Use the explicit version of the finite. difference approach to value the option. Use stock price intervals of. $\$4$ and time intervals of 1 month.  

21.19. The spot price of copper is. $\$0.60$ per pound. Suppose that the futures prices (dollars per pound) are as follows:.  

<html><body><table><tr><td>3 months</td></tr><tr><td>6 months 0.57</td></tr><tr><td>9 months 0.54</td></tr><tr><td>12months 0.50</td></tr></table></body></html>  

The volatility of the price of copper is. $40\%$ per annum and the risk-free rate is. $6\%$ per annum. Use a binomial tree to value an American call option on copper with an. exercise price of $\$0.60$ and a time to maturity of 1 year. Divide the life of the option into four 3-month periods for the purposes of constructing the tree. (Hint: As explained. in Section 18.6, the futures price of a variable is its expected future price in a riskneutral world.)  

21.20. Use the binomial tree in Problem 21.19 to value a security that pays off $x^{2}$ in 1 year where $x$ is the price of copper.   
21.21. When do the boundary conditions for $S=0$ and $S\to\infty$ affect the estimates of derivative prices in the explicit finite difference method?   
21.22. How would you use the antithetic variable method to improve the estimate of the European option in Business Snapshot 21.2 and Table 21.2?   
21.23. A company has issued a 3-year convertible bond that has a face value of. $\$25$ and can be exchanged for two of the company's shares at any time. The company can call the issue, forcing conversion, when the share price is greater than or equal to. $\$18$ . Assuming that the company will force conversion at the earliest opportunity, what are the boundary conditions for the price of the convertible? Describe how you would use finite difference methods to value the convertible assuming constant interest rates. Assume there is no risk of the company defaulting.   
21.24. Provide formulas that can be used for obtaining three random samples from standard normal distributions when the correlation between sample $i$ and sample $j$ .5 $\rho_{i,j}.$   
21.25. An American put option to sell a Swiss franc for dollars has a strike price of. $\$0.80$ and a time to maturity of 1 year. The Swiss franc's volatility is. $10\%$ , the dollar interest rate is $6\%$ , the Swiss franc interest rate is $3\%$ , and the current exchange rate is 0.81. Use a threestep binomial tree to value the option. Estimate the delta of the option from your tree.   
21.26. A 1-year American call option on silver futures has an exercise price of. $\$9.00$ . The current futures price is $\$8.50$ , the risk-free rate of interest is $12\%$ per annum, and the volatility of the futures price is $25\%$ per annum. Use the DerivaGem software with four 3-month time steps to estimate the value of the option. Display the tree and verify that. the option prices at the final and penultimate nodes are correct. Use DerivaGem to value the European version of the option. Use the control variate technique to improve your estimate of the price of the American option.  

21.27. Answer the following questions concerned with the alternative procedures for constructing trees in Section 21.4:  

(a) Show that the binomial model in Section 21.4 is exactly consistent with the mean and variance of the change in the logarithm of the stock price in time $\Delta t$   
(b) Show that the trinomial model in Section 21.4 is consistent with the mean and variance of the change in the logarithm of the stock price in time $\Delta t$ when terms of order $(\Delta t)^{2}$ and higher are ignored.   
(c) Construct an alternative to the trinomial model in Section 21.4 so that the probabilities are $1/6,2/3$ , and $1/6$ on the upper, middle, and lower branches emanating from each node. Assume that the branching is from $S$ to $S u,S m$ , or $S d$ with $m^{2}=u d$ Match the mean and variance of the change in the logarithm of the stock price exactly.  

21.28. The DerivaGem Application Builder functions enable you to investigate how the prices of options calculated from a binomial tree converge to the correct value as the number of time steps increases. (See Figure 21.4 and Sample Application A in DerivaGem.) Consider a put option on a stock index where the index level is 900, the strike price is 900, the risk-free rate is $5\%$ , the dividend yield is $2\%$ , and the time to maturity is 2 years.  

(a) Produce results similar to Sample Application A on convergence for the situation where the option is European and the volatility of the index is $20\%$   
(b) Produce results similar to Sample Application A on convergence for the situation where the option is American and the volatility of the index is $20\%$   
(c) Produce a chart showing the pricing of the American option when the volatility is $20\%$ as a function of the number of time steps when the control variate technique is used.   
(d) Suppose that the price of the American option in the market is 85.0. Produce a chart showing the implied volatility estimate as a function of the number of time steps.   
21.29. Estimate delta, gamma, and theta from the tree in Example 21.3. Explain how each can be interpreted.   
21.30. How much is gained from exercising early at the lowest node at the 9-month point in. Example 21.4?  