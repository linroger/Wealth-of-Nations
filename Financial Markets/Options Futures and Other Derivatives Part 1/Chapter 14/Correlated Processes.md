# 14.5 CORRELATED PROCESSES  

So far we have considered how the stochastic process for a single variable can be represented. We now extend the analysis to the situation where there are two or more variables following correlated stochastic processes. Suppose that the processes followed by two variables $x_{1}$ and $x_{2}$ are  

$$
d x_{1}=a_{1}d t+b_{1}d z_{1}\quad{\mathrm{and}}\quad d x_{2}=a_{2}d t+b_{2}d z_{2}
$$  

where $d z_{1}$ and $d z_{2}$ are Wiener processes.  

As has been explained, the discrete-time approximations for these processes are  

$$
\Delta x_{1}=a_{1}\Delta t+b_{1}\epsilon_{1}\sqrt{\Delta t}\quad\mathrm{and}\quad\Delta x_{2}=a_{2}\Delta t+b_{2}\epsilon_{2}\sqrt{\Delta t}
$$  

where $\epsilon_{1}$ and $\epsilon_{2}$ are samples from a standard normal distribution $\phi(0,1)$  

The variables $x_{1}$ and $x_{2}$ can be simulated in the way described in Section 14.3. If they. are uncorrelated with each other, the random samples $\epsilon_{1}$ and $\epsilon_{2}$ that are used to obtain. movements in a particular period of time $\Delta t$ should be independent of each other..  

If $x_{1}$ and $x_{2}$ have a nonzero correlation $\rho$ , then the $\epsilon_{1}$ and $\epsilon_{2}$ that are used to obtain movements in a particular period of time should be sampled from a bivariate normal distribution. Each variable in the bivariate normal distribution has a standard normal distribution and the correlation between the variables is $\rho$ . In this situation, we would refer to the Wiener processes $d z_{1}$ and $d z_{2}$ as having a correlation $\rho$  

Obtaining samples for uncorrelated standard normal variables in cells in Excel. involves putting the instruction "=NORMSINV(RANDQ)" in each of the cells. To sample standard normal variables $\epsilon_{1}$ and $\epsilon_{2}$ with correlation $\rho$ , we can set  

$$
\begin{array}{r}{\epsilon_{1}=u\quad\mathrm{and}\quad\epsilon_{2}=\rho u+\sqrt{1-\rho^{2}}\nu}\end{array}
$$  

where $u$ and $\nu$ are sampled as uncorrelated variables with standard normal distributions.  

Note that, in the processes we have assumed for $x_{1}$ and $x_{2}$ , the parameters. $a_{1},a_{2},b_{1}$ and $b_{2}$ can be functions of $x_{1},x_{2}$ , and $t$ In particular,. $a_{1}$ and $b_{1}$ can be functions of $x_{2}$ as well as $x_{1}$ and $t;$ and $a_{2}$ and $b_{2}$ can be functions of $x_{1}$ as well as $x_{2}$ and $t$  

The results here can be generalized. When there are three different variables following correlated stochastic processes, we have to sample three different e's. These have a trivariate normal distribution. When there are $n$ correlated variables, we have $n$ different $\epsilon$ 's and these must be sampled from an appropriate multivariate normal distribution. The way this is done is explained in Chapter 21.  
