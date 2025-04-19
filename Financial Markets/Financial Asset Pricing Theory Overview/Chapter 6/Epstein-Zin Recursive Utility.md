---
tags:
  - consumption_choice
  - epstein_zin_utility
  - portfolio_choice
  - recursive_utility
  - state_price_deflator
aliases:
  - Derived utility
  - EZ utility
  - Indirect utility
key_concepts:
  - Epstein-Zin preferences
  - Indirect utility
  - Relative risk aversion
  - Subjective discount factor
  - Wealth dynamics
---

# 6.6 Epstein-Zin recursive utility  

Now consider the Epstein-Zin preferences introduced in Section 5.7.3, where the utility index $\mathcal{U}_{t}$ is specified recursively as  

$$
\begin{array}{r}{\mathcal{U}_{t}=\left(a c_{t}^{\frac{1-\gamma}{\theta}}+b\left(\operatorname{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}]\right)^{\frac{1}{\theta}}\right)^{\frac{\theta}{1-\gamma}}.}\end{array}
$$  

Here is the relative risk aversion, $b$ is the subjective discount factor, and $\begin{array}{r}{\theta=(1-\gamma)/(1-\frac{1}{\psi})}\end{array}$ $\gamma$   
where $\psi$ is the elasticity of intertemporal substitution.  

At time $t$ , the objective of the individual is to maximize $\mathcal{U}_{t}$ over all consumption and portfolio. strategies $(c_{t},c_{t+1},c_{t+2},.~.~)$ and $(\pi_{t},\pi_{t+1},\pi_{t+2},...)$ .Let $J_{t}$ denote the maximum value of $\mathcal{U}_{t}$  

typically referred to as the indirect utility or derived utility. The dynamic programming idea implies that  

$$
J_{t}=\operatorname*{sup}_{c_{t},\pi_{t}}\left\{a c_{t}^{\frac{1-\gamma}{\theta}}+b\left(\mathrm{E}_{t}[J_{t+1}^{1-\gamma}]\right)^{\frac{1}{\theta}}\right\}^{\frac{\theta}{1-\gamma}}.
$$  

The indirect utility is clearly depending on wealth. The wealth dynamics is given by  

$$
W_{t+1}=(W_{t}-c_{t})\pi_{t}^{\top}R_{t+1}=(W_{t}-c_{t})R_{t+1}^{\pi_{t}}
$$  

We conjecture that  

$$
J_{t}=h_{t}W_{t}.
$$  

Substituting the conjecture and the wealth dynamics into (6.66), we obtain  

$$
h_{t}W_{t}=\operatorname*{sup}_{c_{t},\pi_{t}}\left\{a c_{t}^{\frac{1-\gamma}{\theta}}+b(W_{t}-c_{t})^{\frac{1-\gamma}{\theta}}\left(\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi_{t}}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}\right\}^{\frac{\theta}{1-\gamma}}.
$$  

In particular, for the optimal values of $c_{t}$ and $\pi_{t}$ , we have  

$$
\begin{array}{r}{h_{t}W_{t}=\left\{a c_{t}^{\frac{1-\gamma}{\theta}}+b(W_{t}-c_{t})^{\frac{1-\gamma}{\theta}}\left(\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi_{t}}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}\right\}^{\frac{\theta}{1-\gamma}}}\ {=c_{t}\left\{a+b\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{\frac{1-\gamma}{\theta}}\left(\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi_{t}}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}\right\}^{\frac{\theta}{1-\gamma}}.}\end{array}
$$  

# 6.6.1 First-order condition wrt. $c_{t}$  

In the maximization in (6.68), the first-order condition with respect to $c_{t}$ implies that  

$$
a c_{t}^{\frac{1-\gamma}{\theta}-1}=b(W_{t}-c_{t})^{\frac{1-\gamma}{\theta}-1}\left(\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}
$$  

yielding  

$$
a\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{1-\frac{1-\gamma}{\theta}}=b\left(\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}
$$  

Substituting that into (6.69), we obtain  

$$
\begin{array}{c}{{h_{t}W_{t}=c_{t}\left\{a+a\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{\frac{1-\gamma}{\theta}}\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{1-\frac{1-\gamma}{\theta}}\right\}^{\frac{\theta}{1-\gamma}}}}\ {{=c_{t}\left(a\frac{W_{t}}{c_{t}}\right)^{\frac{\theta}{1-\gamma}}=a^{\frac{\theta}{1-\gamma}}c_{t}\left(\frac{W_{t}}{c_{t}}\right)^{\frac{\theta}{1-\gamma}}}}\end{array}
$$  

giving  

$$
h_{t}=a^{\frac{\theta}{1-\gamma}}\left({\frac{c_{t}}{W_{t}}}\right)^{1-\frac{\theta}{1-\gamma}}.
$$  

Substituting the expression for $h_{t}$ into the first-order condition (6.70) gives  

$$
a\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{1-\frac{1-\gamma}{\theta}}=b\left(\mathrm{E}_{t}\left[a^{\theta}\left(\frac{c_{t+1}}{W_{t+1}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}.
$$  

Eliminating the $a$ 's and substituting in the budget constraint (6.67), we arrive at  

$$
\begin{array}{r l}&{\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{1-\frac{1-\gamma}{\theta}}=b\left(\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{\left(W_{t}-c_{t}\right)R_{t+1}^{\pi_{t}}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{1-\gamma}\right]\right)^{\frac{1}{\theta}}}\ &{\qquad=b\left(\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{\left(W_{t}-c_{t}\right)}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right]\right)^{\frac{1}{\theta}}}\ &{\qquad=b\left(\frac{W_{t}-c_{t}}{c_{t}}\right)^{1-\frac{1-\gamma}{\theta}}\left(\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right]\right)^{\frac{1}{\theta}}}\end{array}
$$  

so that  

$$
1=b\left(\mathrm{E}_{t}\left[\left({\frac{c_{t+1}}{c_{t}}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right]\right)^{\frac{1}{\theta}}
$$  

and thus  

$$
1=b^{\theta}\operatorname{E}_{t}\left[\left({\frac{c_{t+1}}{c_{t}}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right]=\operatorname{E}_{t}\left[b^{\theta}\left({\frac{c_{t+1}}{c_{t}}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right].
$$  

Since $\begin{array}{r}{1-\gamma-\theta=\theta(1-\frac{1}{\psi})-\theta=-\theta/\psi}\end{array}$ , we have  

$$
1=\mathrm{E}_{t}\left[b^{\theta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right].
$$  

# 6.6.2 First-order condition wrt. $\pi_{t}$  

The maximization with respect to the optimal portfolio is subject to the condition that $\pi_{t}^{\top}\mathbf{1}=1$ i.e. $\pi_{1{t}}+\cdot\cdot\cdot+\pi_{N{t}}=1$ . Hence $\pi_{1t}=1-\left(\pi_{2t}+\cdot\cdot\cdot+\pi_{N t}\right)$ and the portfolio return can be written. as  

$$
R_{t+1}^{\pi_{t}}=\sum_{j=1}^{N}\pi_{j t}R_{j,t+1}=\pi_{1t}R_{1,t+1}+\sum_{j=2}^{N}\pi_{j t}R_{j,t+1}=R_{1,t+1}+\sum_{j=2}^{N}\pi_{j t}(R_{j,t+1}-R_{1,t+1}).
$$  

Substituting this into the right-hand side of (6.68), we can see that the first-order condition with respect to $\pi_{j t}$ $j=2,\ldots,N$ , implies that  

$$
0=\mathrm{E}_{t}\left[h_{t+1}^{1-\gamma}\left(R_{t+1}^{\pi_{t}}\right)^{-\gamma}\left(R_{j,t+1}-R_{1,t+1}\right)\right].
$$  

Using (6.71) and subsequently (6.67), we have  

$$
\begin{array}{r}{|=\operatorname{E}_{t}\left[\left(\frac{c_{t+1}}{W_{t+1}}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{-\gamma}\left(R_{j,t+1}-R_{1,t+1}\right)\right]=\operatorname{E}_{t}\left[\left(\frac{c_{t+1}}{\left(c_{t}-W_{t}\right)}\right)^{1-\gamma-\theta}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}\left(R_{j,t+1}-R_{1,t+1}\right)\right]}\end{array}
$$  

and since $1-\gamma-\theta=-\theta/\psi$ and we can multiply with anything that is time $t$ measurable, we conclude that  

$$
\begin{array}{r}{0=\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}\left(R_{j,t+1}-R_{1,t+1}\right)\right].}\end{array}
$$  

Multiplying by. $\pi_{j t}$ and summing over $j$ gives  

$$
\begin{array}{r l}&{0=\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}\displaystyle\sum_{j=2}^{N}\pi_{j t}(R_{j,t+1}-R_{1,t+1})\right]}\ &{\quad=\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}\left(R_{t+1}^{\pi_{t}}-R_{1,t+1}\right)\right],}\end{array}
$$  

which implies that  

$$
\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}R_{1,t+1}\right]=\mathrm{E}_{t}\left[\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta}\right]=b^{-\theta},
$$  

where the last equality follows from (6.72), and thus  

$$
\mathrm{E}_{t}\left[b^{\theta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}R_{1,t+1}\right]=1.
$$  

The above computation could be done for any of the $N$ assets so we conclude that  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[b^{\theta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}R_{j,t+1}\right]=1,\quad j=1,\dots,N.}\end{array}
$$  

# 6.6.3 The state-price deflator  

We can now see that the optimal decisions of the individual give rise to a next-period state-price deflator given by  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=b^{\theta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1}.
$$  

In particular if $\gamma=1/\psi$ and thus $\theta=1$ , we are back to the traditional state-price deflator for time-additive power utility,. $\zeta_{t+1}/\zeta_{t}=b(c_{t+1}/c_{t})^{-\gamma}$  

# 6.7 Concluding remarks  

This chapter has characterized the optimal consumption and portfolio choice of an individual by. the first-order condition of her utility maximization problem. The characterization provides a link. between asset prices and the optimal consumption plan of any individual. In the next chapter we will look at the market equilibrium..  
