---
tags:
  - '#boundary_conditions'
  - '#call_options'
  - '#differential_equation'
  - '#optimal_exercise_price'
  - '#option_pricing'
  - '#perpetual_american_options'
  - '#put_options'
  - '#strike_price'
---
# 26.2  PERPETUAL AMERICAN CALL AND PUT OPTIONS  

The differential equation that must be satisfied by the price of a derivative when there is a dividend at rate $q$ is equation (17.6):  

$$
\frac{\partial f}{\partial t}+(r-q)S\frac{\partial f}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}f}{\partial S^{2}}=r f
$$  

Consider a derivative that pays off a fixed amount $Q$ when $S=H$ for the first time. If $S<H$ , the boundary conditions for the differential equation are that $f=Q$ when $S=H$ and $f=0$ when $S=0$ . The solution $f=Q(S/H)^{\alpha}$ satisfies the boundary conditions when $\alpha>0$ Furthermore, it satisfies the differential equation when  

$$
\begin{array}{r}{(r-q)\alpha+\frac{1}{2}\alpha(\alpha-1)\sigma^{2}=r}\end{array}
$$  

The positive solution to this equation is $\alpha=\alpha_{1}$ , where  

$$
\alpha_{1}=\frac{-w+\sqrt{w^{2}+2\sigma^{2}r}}{\sigma^{2}}
$$  

and $w=r-q-\sigma^{2}/2$ . It follows that the value of the derivative must be $Q(S/H)^{\alpha_{1}}$ because this satisfies the boundary conditions and the differential equation.  

Consider next a perpetual American call option with strike price $K$ If the option is. exercised when $S=H$ , the payoff is. $H-K$ and from the result just proved the value of the option is. $(H-K)(S/H)^{\alpha_{1}}$ . The holder of the call option can choose the asset price, $H$ at which the option is exercised. The optimal $H$ is the one that maximizes the value we have just calculated. Using standard calculus methods, it is $H=H_{1}$ , where  

$$
H_{1}=K\frac{\alpha_{1}}{\alpha_{1}-1}
$$  

The price of a perpetual call if $S<H_{1}$ is therefore  

$$
(H_{1}-K)\biggl(\frac{S_{0}}{H_{1}}\biggr)^{\alpha_{1}}=\frac{K}{\alpha_{1}-1}\biggl(\frac{\alpha_{1}-1}{\alpha_{1}}\frac{S}{K}\biggr)^{\alpha_{1}}
$$  

If $S>H_{1}$ , the call should be exercised immediately and is worth $S-K$  

To value an American put, we consider a derivative that pays off $Q$ when $S=H$ in the situation where. $S>H$ (so that the barrier. $H$ is reached from above). In this case, the boundary conditions for the differential equation are that $f=Q$ when $S=H$ and $f=0$ as $S$ tends to infinity. In this case, the solution $f=Q(S/H)^{-\alpha}$ satisfies the boundary conditions when. $\alpha>0$ . As above, we can show that it also satisfies the differential equation when. $\alpha=\alpha_{2}$ , where  

$$
\alpha_{2}=\frac{w+\sqrt{w^{2}+2\sigma^{2}r}}{{\sigma}^{2}}
$$  

If the holder of the American put chooses to exercise when $S=H$ , the value of the put is $(K-H)(S/H)^{-\alpha_{2}}$ . The holder of the put will choose the exercise level. $H=H_{2}$ to maximize this. This is.  

$$
H_{2}=K\frac{\alpha_{2}}{\alpha_{2}+1}
$$  

The price of a perpetual put if $S>H_{2}$ is therefore  

$$
(K-H_{2})\biggl(\frac{S_{0}}{H_{2}}\biggr)^{-\alpha_{2}}=\frac{K}{\alpha_{2}+1}\biggl(\frac{\alpha_{2}+1}{\alpha_{2}}\frac{S}{K}\biggr)^{-\alpha_{2}}
$$  

+ $S<H_{2}$ , the put should be exercised immediately and is worth $K-S$  

Section 15.6 and Problem 15.31 give particular cases of the results here for $q=0$  
