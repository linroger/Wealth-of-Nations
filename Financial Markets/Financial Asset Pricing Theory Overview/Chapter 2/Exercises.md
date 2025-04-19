---
tags:
  - '#asset_pricing'
  - '#asset_returns'
  - '#brownian_motion'
  - '#geometric_brownian_motion'
  - '#law_of_iterated_expectations'
  - '#ordinary_differential_equation'
  - '#return_variance'
  - '#stochastic_process'
  - '#two_period_economy'
---
# 2.8 Exercises  

EXERCISE 2.1 In the two-period economy illustrated in Figures 2.1 and 2.2 consider an asset paying a dividend at time 2 given by  

$$
D_{2}=\left\{\begin{array}{l l}{{0,}}&{{\mathrm{for}\omega=3,}}\ {{5,}}&{{\mathrm{for}\omega\in\{1,2,4\},}}\ {{10,}}&{{\mathrm{for}\omega\in\{5,6\}.}}\end{array}\right.
$$  

(a) What is the expectation at time $0$ Of $D_{2}$ ? What is the expectation at time $^{1}$ of $D_{2}$ ? Verify that the Law of Iterated Expectations holds for these expectations.  

(b) What is the variance at time $0$ of $D_{2}$ ? What is the variance at time 1 of $D_{2}$ ? Confirm that $\mathrm{Var}[D_{2}]=\mathrm{E}\left[\mathrm{Var}_{1}[D_{2}]\right]+\mathrm{Var}\left[\mathrm{E}_{1}[D_{2}]\right]$  

EXERCISE 2.2Let $X=\left(X_{t}\right)$ and $Y=\left(Y_{t}\right)$ be the price processes of two assets with no intermediate dividends and assume that  

$$
\begin{array}{r}{d X_{t}=X_{t}\left[0.05d t+0.1d z_{1t}+0.2d z_{2t}\right],}\ {d Y_{t}=Y_{t}\left[0.07d t+0.3d z_{1t}-0.1d z_{2t}\right].}\end{array}
$$  

(a) What is the expected rate of return of each of the two assets?  

(b) What is the return variance and volatility of each of the two assets?  

(c) What is the covariance and the correlation between the returns on the two assets?  

EXERCISE 2.3 Suppose $X=\left(X_{t}\right)$ is a geometric Brownian motion, $d X_{t}=\mu X_{t}d t+\sigma X_{t}d z_{t}$ What is the dynamics of the process $y=\left(y_{t}\right)$ defined by $y_{t}=(X_{t})^{n}$ ? What can you say about the. distribution of future values of the $y$ process?  

EXERCISE 2.4 Suppose that the continuous-time stochastic process $X=\left(X_{t}\right)$ is defined as  

$$
X_{t}=\frac{1}{2}\int_{0}^{t}\lambda_{s}^{2}d s+\int_{0}^{t}\lambda_{s}d z_{s},
$$  

where $z~=~\left(z_{t}\right)$ is a one-dimensional standard Brownian motion and $\lambda\:=\:(\lambda_{t})$ is some "nice" stochastic process.  

(a) Argue that $\begin{array}{r}{d X_{t}=\frac{1}{2}\lambda_{t}^{2}d t+\lambda_{t}d z_{t}}\end{array}$   
(b) Suppose that the continuous-time stochastic process $\xi=\left(\xi_{t}\right)$ is defined as $\xi_{t}=\exp\{-X_{t}\}$ Show that $d\xi_{t}=-\lambda_{t}\xi_{t}d z_{t}$  

EXERCISE 2.5 (Adapted from Bjork (2004).) Define the process $y=\left(y_{t}\right)$ by $y_{t}=z_{t}^{4}$ , where $z=\left(z_{t}\right)$ is a standard Brownian motion. Find the dynamics of $y$ . Show that  

$$
y_{t}=6\int_{0}^{t}z_{s}^{2}d s+4\int_{0}^{t}z_{s}^{3}d z_{s}.
$$  

Show that $\operatorname{E}[y_{t}]\equiv\operatorname{E}[z_{t}^{4}]=3t^{2}$  

EXERCISE 2.6 (Adapted from Bjork (2004).) Define the process $y=\left(y_{t}\right)$ by $y_{t}=e^{a z_{t}}$ , where $a$ is a constant and $z=\left(z_{t}\right)$ is a standard Brownian motion. Find the dynamics of $y$ . Show that  

$$
y_{t}=1+\frac{1}{2}a^{2}\int_{0}^{t}y_{s}d s+a\int_{0}^{t}y_{s}d z_{s}.
$$  

Define $m(t)=\operatorname{E}[y_{t}]$ . Show that. $m$ satisfies the ordinary differential equation  

$$
m^{\prime}(t)={\frac{1}{2}}a^{2}m(t),\quad m(0)=1.
$$  

Show that $m(t)=e^{a^{2}t/2}$ and conclude that  

$$
\begin{array}{r}{\mathrm{E}\left[e^{a z_{t}}\right]=e^{a^{2}t/2}.}\end{array}
$$  
