---
tags:
  - '#brownian_motion'
  - '#drift_rate'
  - '#generalized_wiener_process'
  - '#ito_process'
  - '#markov_process'
  - '#stochastic_calculus'
  - '#stochastic_process'
  - '#variance_rate'
  - '#wiener_process'
---
# 14.2 CONTINUOUS-TIME STOCHASTIC PROCESSES  

Consider a variable that follows a Markov stochastic process. Suppose that its current value is 10 and that the change in its value during a year is $\phi(0,1)$ , where $\phi(m,\nu)$ denotes a probability distribution that is normally distributed with mean $m$ and variance $\nu$ 2 What is the probability distribution of the change in the value of the variable during 2 years?  

The change in 2 years is the sum of two normal distributions, each of which has a mean of zero and variance of 1.0. Because the variable is Markov, the two probability distributions are independent. When we add two independent normal distributions, the. result is a normal distribution where the mean is the sum of the means and the variance is the sum of the variances. The mean of the change during 2 years in the variable we are considering is, therefore, zero and the variance of this change is 2.0. Hence, the. change in the variable over 2 years has the distribution $\phi(0,2)$ . The standard deviation of the change is $\sqrt{2}$  

Consider next the change in the variable during 6 months. The variance of the change in the value of the variable during 1 year equals the variance of the change during the first 6 months plus the variance of the change during the second 6 months. We assume these are the same. It follows that the variance of the change during a 6-month period must be 0.5. Equivalently, the standard deviation of the change is $\bar{\sqrt{0.5}}$ The probability distribution for the change in the value of the variable during 6 months is $\phi(0,0.5)$  

A similar argument shows that the probability distribution for the change in the value of the variable during 3 months is $\phi(0,0.25)$ . More generally, the change during any time period of length $T$ is $\phi(0,T)$ . In particular, the change during a very short time period of length $\Delta t$ is $\phi(0,\Delta t)$  

Note that, when Markov processes are considered, the variances of the changes in successive time periods are additive. The standard deviations of the changes in. successive time periods are not additive. The variance of the change in the variable. in our example is 1.0 per year, so that the variance of the change in 2 years is 2.0 and the variance of the change in 3 years is 3.0. The standard deviations of the changes in. 2 and 3 years are $\sqrt{2}$ and $\sqrt{3}$ , respectively. Uncertainty is often measured by standard deviation. These results therefore explain why uncertainty is sometimes referred to as being proportional to the square root of time.  

# Wiener Process  

The process followed by the variable we have been considering is known as a Wiener process. It is a particular type of Markov stochastic process with a mean change of zero and a variance rate of 1.0 per year. It has been used in physics to describe the motion of a particle that is subject to a large number of small molecular shocks and is sometimes referred to as Brownian motion.  

Expressed formally, a variable $z$ follows a Wiener process if it has the following two properties:  

Property 1. The change $\Delta z$ during a small period of time t is  

$$
\Delta z=\epsilon\sqrt{\Delta t}
$$  

where e has a standard normal distribution $\phi(0,1)$  

Property 2. The values of $\Delta z$ for any two different short intervals of time, $\Delta t$ are independent.  

It follows from the first property that $\Delta z$ itself has a normal distribution with  

$$
\begin{array}{c}{{\mathrm{mean~of~}\Delta z=0}}\ {{\mathrm{standard~deviation~of~}\Delta z=\sqrt{\Delta t}}}\ {{\mathrm{variance~of~}\Delta z=\Delta t}}\end{array}
$$  

The second property implies that $z$ follows a Markov process..  

Consider the change in the value of $z$ during a relatively long period of time, $T.$ This can be denoted by. $z(T)-z(0)$ . It can be regarded as the sum of the changes in $z$ in $N$ small time intervals of length $\Delta t$ , where  

$$
N={\frac{T}{\Delta t}}
$$  

Thus,  

$$
z(T)-z(0)=\sum_{i=1}^{N}\epsilon_{i}\sqrt{\Delta t}
$$  

where the $\epsilon_{i}(i=1,2,\dots,N)$ are distributed $\phi(0,1)$ . We know from the second property of Wiener processes that the $\epsilon_{i}$ are independent of each other. It follows  

from equation (14.2) that $z(T)\mathrm{~-~}z(0)$ is normally distributed, with  

$$
\begin{array}{c}{{\mathrm{mean~of}\left[z(T)-z(0)\right]=0}}\ {{\mathrm{variance~of}\left[z(T)-z(0)\right]=N\Delta t=T}}\ {{\mathrm{standard~deviation~of}\left[z(T)-z(0)\right]=\sqrt{T}}}\end{array}
$$  

This is consistent with the discussion earlier in this section.  

# Example 14.1  

Suppose that the value, $z$ , of a variable that follows a Wiener process is initially 25 and that time is measured in years. At the end of 1 year, the value of the variable is normally distributed with a mean of 25 and a standard deviation of 1.0. At the end of 5 years, it is normally distributed with a mean of 25 and a standard deviation of $\sqrt{5}$ , or 2.236. Our uncertainty about the value of the variable at a certain time in the future, as measured by its standard deviation, increases as the square root of how far we are looking ahead.  

In ordinary calculus, it is usual to proceed from small changes to the limit as the small changes become closer to zero. Thus,. $d x=a d t$ is the notation used to indicate that $\Delta x=a\Delta t$ in the limit as $\Delta t\longrightarrow0$ . We use similar notational conventions in stochastic. calculus. So, when we refer to $d z$ as a Wiener process, we mean that it has the properties. for $\Delta z$ given above in the limit as $\Delta t\longrightarrow0$  

Figure 14.1 illustrates what happens to the path followed by. $z$ as the limit $\Delta t\longrightarrow0$ is approached. Note that the path is quite "jagged." This is because the standard deviation of the movement in. $z$ in time $\Delta t$ equals $\sqrt{\Delta t}$ and, when $\Delta t$ is small, $\sqrt{\Delta t}$ is much bigger than $\Delta t$ Two intriguing properties of Wiener processes, related to this $\sqrt{\Delta t}$ property, are as follows:  

1. The expected length of the path followed by. $z$ in any time interval is infinite. 2. The expected number of times $z$ equals any particular value in any time interval is infinite.3  

# Generalized Wiener Process  

The mean change per unit time for a stochastic process is known as the drift rate and the variance per unit time is known as the variance rate. The basic Wiener process,. $d z$ that has been developed so far has a drift rate of zero and a variance rate of 1.0. The drift rate of zero means that the expected value of. $z$ at any future time is equal to its. current value. The variance rate of 1.0 means that the variance of the change in. $z$ in a time interval of length. $T$ equals $T$ A generalized Wiener process for a variable. $x$ can be defined in terms of $d z$ as  

$$
d x=a d t+b d z
$$  

where $a$ and $^b$ are constants.  

To understand equation (14.3), it is useful to consider the two components on the right-hand side separately. The a dt term implies that $x$ has an expected drift rate of. $a$ per unit of time. Without the. $b d z$ term, the equation is. $d x=a d t$ , which implies that.  

![](images/fc3cfd6086fe7d110151c6f1af678be2cc5d45a31a2850a0a6e2f2641a3d8af5.jpg)  
in equation (14.1).  

$d x/d t=a$ Integrating with respect to time, we get  

$$
x=x_{0}+a t
$$  

where $x_{0}$ is the value of $x$ at time 0. In a period of time of length. $T$ , the variable $x$ increases by an amount $a T.$ The $b d z$ term on the right-hand side of equation (14.3) can be regarded as adding noise or variability to the path followed by $x$ The amount of this noise or variability is $^b$ times a Wiener process. A Wiener process has a variance rate per unit time of 1.0. It follows that. $^b$ times a Wiener process has a variance rate per unit time of $b^{2}$ . In a small time interval $\Delta t$ , the change $\Delta x$ in the value of $x$ is given by equations (14.1) and (14.3) as  

$$
\Delta x=a\Delta t+b\epsilon\sqrt{\Delta t}
$$  

where, as before,. $\epsilon$ has a standard normal distribution $\phi(0,1)$ . Thus $\Delta x$ has a normal distribution with.  

$$
\begin{array}{r}{\operatorname*{mean~of~}\Delta x=a~\Delta t\quad}\ {\mathrm{~standard~deviation~of~}\Delta x=b{\sqrt{\Delta t}}}\ {\mathrm{~variance~of~}\Delta x=b^{2}\Delta t\quad}\end{array}
$$  

Similar arguments to those given for a Wiener process show that the change in the value of $x$ in any time interval $T$ is normally distributed with.  

$$
\begin{array}{c}{{\mathrm{mean~of~change~in~}x=a T}}\ {{\mathrm{standard~deviation~of~change~in~}x=b\sqrt{T}}}\ {{\mathrm{variance~of~change~in~}x=b^{2}T}}\end{array}
$$  

To summarize, the generalized Wiener process given in equation (14.3) has an expected drift rate (i.e., average drift per unit of time) of $a$ and a variance rate (i.e., variance per unit of time) of $b^{2}$ . It is illustrated in Figure 14.2.  

![](images/2849dca1092104c82a4f03496603068f7f3e97da0c7f9206faba31a9928c65d3.jpg)  
Figure 14.2 Generalized Wiener process with $a=0.3$ and $b=1.5$  

$$
\Delta X=a(0.5)+b(
$$  

# Example 14.2  

Consider the situation where the cash position of a company, measured in thousands of dollars, follows a generalized Wiener process with a drift of 20 per year and a variance rate of 900 per year. Initially, the cash position is 50. At the end of 1 year the cash position will have a normal distribution with a mean of 70 and a standard deviation of $\sqrt{900}$ , or 30. At the end of 6 months it will have a normal. distribution with a mean of 60 and a standard deviation of. $30\sqrt{0.5}=21.21$ . Our uncertainty about the cash position at some time in the future, as measured by its standard deviation, increases as the square root of how far ahead we are looking. (Note that the cash position can become negative. We can interpret this as a situation where the company is borrowing funds.).  

# Ito Process  

A further type of stochastic process, known as an Ito process, can be defined. This is a generalized Wiener process in which the parameters. $a$ and $^b$ are functions of the value of the underlying variable $x$ and time t. An Ito process can therefore be written as.  

$$
d x=a(x,t)d t+b(x,t)d z
$$  

Both the expected drift rate and variance rate of an Ito process are liable to change over time. They are functions of the current value of. $x$ and the current time, $t.$ In a small time interval between $t$ and $t+\Delta t$ , the variable changes from $x$ to $x+\Delta x$ , where  

$$
\Delta x=a(x,t)\Delta t+b(x,t)\epsilon\sqrt{\Delta t}
$$  

This equation involves a small approximation. It assumes that the drift and variance rate of $x$ remain constant, equal to their values at time. $t$ , in the time interval between $t$ and $t+\Delta t$  

Note that the process in equation (14.4) is Markov because the change in $x$ at time $t$ depends only on the value of $x$ at time $t$ , not on its history. A non-Markov process could be defined by letting $a$ and $^b$ in equation (14.4) depend on values of $x$ prior to time $t$  
