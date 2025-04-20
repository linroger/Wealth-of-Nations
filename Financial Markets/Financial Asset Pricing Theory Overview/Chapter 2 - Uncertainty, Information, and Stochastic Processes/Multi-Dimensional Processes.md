---
tags:
  - asset_pricing
  - brownian_motion
  - continuous_time
  - correlation
  - covariance
  - discrete_time
  - exogenous_shocks
  - ito_process
  - multi_dimensional_processes
  - stochastic_processes
aliases:
  - Multi-dimensional analysis
  - Multi-dimensional models
  - Multi-process models
key_concepts:
  - Asset pricing models
  - Brownian motion
  - Continuous-time model
  - Covariances and correlations
  - Discrete-time model
  - Exogenous shocks
  - Instantaneous correlation
  - Ito processes
  - Multi-dimensional processes
  - Two-dimensional processes
---

# 2.7 Multi-dimensional processes  

So far we have only considered one-dimensional processes, i.e. processes with a value space which is $\mathbb{R}$ or a subset of $\mathbb{R}$ . In most asset pricing models we need to keep track of several processes, e.g. dividend and price processes for different assets, and we will often be interested in covariances and correlations between different processes.  

If the exogenous shocks in the model are one-dimensional, then increments over the smallest. time interval considered in the model will be perfectly correlated. In a discrete-time model where the exogenous shocks. $\varepsilon_{1},\ldots,\varepsilon_{T}$ are one-dimensional, changes in any two processes between two. subsequent points in time, say. $t$ and $t+1$ , will be perfectly correlated. For example, suppose. $X$ and $Y$ are two general processes defined by  

$$
\Delta X_{t+1}=\mu_{X t}+\sigma_{X t}\varepsilon_{t+1},\qquad\Delta Y_{t+1}=\mu_{Y t}+\sigma_{Y t}\varepsilon_{t+1}
$$  

where $\varepsilon_{t+1}$ has a mean of zero and a variance of one. $\mu_{X t},\mu_{Y t},\sigma_{X t}$ , and $\sigma_{Y t}$ are known at time $t$ and reflect the conditional means and standard deviations of the increments to the processes over the next period. By using the properties of covariances and variances we get  

$$
\begin{array}{r l}&{\mathrm{Cov}_{t}[\Delta X_{t+1},\Delta Y_{t+1}]=\sigma_{X t}\sigma_{Y t}\mathrm{Var}_{t}[\varepsilon_{t+1}]=\sigma_{X t}\sigma_{Y t},}\ &{\mathrm{Var}_{t}[\Delta X_{t+1}]=\sigma_{X t}^{2},\quad\mathrm{Var}_{t}[\Delta Y_{t+1}]=\sigma_{Y t}^{2},}\ &{\mathrm{Corr}_{t}[\Delta X_{t+1},\Delta Y_{t+1}]=1.}\end{array}
$$  

Increments in two processes over more than one sub-period are generally not perfectly correlated even with a one-dimensional shock..  

In a continuous-time model where the exogenous shock processe $z=(z_{t})_{t\in[0,T]}$ is one-dimensional, the instantaneous increments of any two processes will be perfectly correlated. For example, if we consider the two Ito processes $X$ and $Y$ defined by  

$$
\mathrm{~\boldmath~\sigma~}=\mu_{X t}d t+\sigma_{X t}d z_{t},\quad\mathrm{~\boldmath~}d Y_{t}=\mu_{Y t}d t+\sigma_{Y t}d z_{t},
$$  

then $\operatorname{Cov}_{t}[d X_{t},d Y_{t}]=\sigma_{X t}\sigma_{Y t}d t$ so that the instantaneous correlation becomes  

$$
\operatorname{Corr}_{t}[d X_{t},d Y_{t}]={\frac{\operatorname{Cov}_{t}[d X_{t},d Y_{t}]}{{\sqrt{\operatorname{Var}_{t}[d X_{t}]\operatorname{Var}_{t}[d Y_{t}]}}}}={\frac{\sigma_{X t}\sigma_{Y t}d t}{{\sqrt{\sigma_{X t}^{2}d t\sigma_{Y t}^{2}d t}}}}=1.
$$  

Increments over any non-infinitesimal time interval are generally not perfectly correlated, i.e. for any $h>0$ a correlation like $\operatorname{Corr}_{t}[X_{t+h}-X_{t},Y_{t+h}-Y_{t}]$ is typically different from one but close to. one for small $h$  

To obtain non-perfectly correlated changes over the shortest time period considered by the. model we need an exogenous shock of a dimension higher than one, i.e. a shock vector. One can. without loss of generality assume that the different components of this shock vector are mutually. independent and generate non-perfect correlations between the relevant processes by varying the. sensitivities of those processes towards the different exogenous shocks. We will first consider the case of two processes and later generalize.  

# 2.7.1 Two-dimensional processes  

In the discrete-time example above, we can avoid the perfect correlation between $\Delta X_{t+1}$ and $\Delta Y_{t+1}$ by introducing a second shock. Suppose that.  

$$
\Delta X_{t+1}=\mu_{X t}+\sigma_{X1t}\varepsilon_{1,t+1}+\sigma_{X2t}\varepsilon_{2,t+1}
$$  

and  

$$
\Delta Y_{t+1}=\mu_{Y t}+\sigma_{Y1t}\varepsilon_{t+1}+\sigma_{Y2t}\varepsilon_{2,t+1},
$$  

where $\varepsilon_{1,t+1}$ and $\varepsilon_{2,t+1}$ are independent and have zero mean and unit variance. Now the covariance is given by  

$$
\mathrm{Cov}_{t}[\Delta X_{t+1},\Delta Y_{t+1}]=\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t},
$$  

while the variances are  

$$
\mathrm{Var}_{t}\big[\Delta X_{t+1}\big]=\sigma_{X1t}^{2}+\sigma_{X2t}^{2},\quad\mathrm{Var}_{t}\big[\Delta Y_{t+1}\big]=\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2}.
$$  

The correlation is thus  

$$
\mathrm{Corr}_{t}[\Delta X_{t+1},\Delta Y_{t+1}]=\frac{\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t}}{\sqrt{(\sigma_{X1t}^{2}+\sigma_{X2t}^{2})(\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2})}}.
$$  

Since  

$$
\sigma_{X1t}^{2}\sigma_{Y2t}^{2}+\sigma_{X2t}^{2}\sigma_{Y1t}^{2}-2\sigma_{X1t}\sigma_{Y1t}\sigma_{X2t}\sigma_{Y2t}=\left(\sigma_{X1t}\sigma_{Y2t}-\sigma_{X2t}\sigma_{Y1t}\right)^{2}\geq0,
$$  

it follows that  

$$
\begin{array}{r}{\left(\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t}\right)^{2}\leq\big(\sigma_{X1t}^{2}+\sigma_{X2t}^{2}\big)\big(\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2}\big),}\end{array}
$$  

and therefore the squared correlation is generally smaller than one. The correlation will equal $^{-1}$ or $+1$ only if $\sigma_{X1t}=\sigma_{Y1t}=0$ or $\sigma_{X2t}=\sigma_{Y2t}=0$ so that we are effectively back to the single shock case.  

Similarly, in the continuous-time setting we add a standard Brownian motion so that  

$$
d X_{t}=\mu_{X t}d t+\sigma_{X1t}d z_{1t}+\sigma_{X2t}d z_{2t},\qquadd Y_{t}=\mu_{Y t}d t+\sigma_{Y1t}d z_{1t}+\sigma_{Y2t}d z_{2t},
$$  

where $z_{1}=\left(z_{1t}\right)$ and $z_{2}=\left(z_{2t}\right)$ are independent standard Brownian motions. This generates an instantaneous covariance of $\operatorname{Cov}_{t}[d X_{t},d Y_{t}]=\left(\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t}\right)d t$ , instantaneous variances of $\mathrm{Var}_{t}[d X_{t}]=\left(\sigma_{X1t}^{2}+\sigma_{X2t}^{2}\right)d t$ and $\mathrm{Var}_{t}[d Y_{t}]=\left(\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2}\right)d t$ and thus an instantaneous correlation of  

$$
\mathrm{Corr}_{t}[d X_{t},d Y_{t}]=\frac{\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t}}{\sqrt{\left(\sigma_{X1t}^{2}+\sigma_{X2t}^{2}\right)\left(\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2}\right)}},
$$  

which again can be anywhere in the interval $[-1,+1]$  

The shock coefficients $\sigma_{X1t}$ $\sigma_{X2t}$ $\sigma_{Y1t}$ , and $\sigma_{Y2t}$ are determining the two instantaneous variances and the instantaneous correlation. But many combinations of the four shock coefficients will give rise to the same variances and correlation. We have one degree of freedom in fixing the shock coefficients. For example, we can put $\sigma_{X2t}\equiv0$ , which has the nice implication that it will simplify various expressions and interpretations. If we thus write the dynamics of $X$ and $Y$ as  

$$
d X_{t}=\mu_{X t}d t+\sigma_{X t}d z_{1t},\qquadd Y_{t}=\mu_{Y t}d t+\sigma_{Y t}\left[\rho_{t}d z_{1t}+\sqrt{1-\rho_{t}^{2}}d z_{2t}\right],
$$  

$\sigma_{X t}^{2}$ and $\sigma_{Y t}^{2}$ are the variance rates of $X_{t}$ and $Y_{t}$ , respectively, while the covariance is. $\mathrm{Cov}_{t}[d X_{t},d Y_{t}]=$ $\rho_{t}\sigma_{X t}\sigma_{Y t}$ . If $\sigma_{X t}$ and $\sigma_{Y t}$ are both positive, then. $\rho_{t}$ will be the instantaneous correlation between the two processes. $X$ and $Y$  

In many continuous-time models, one stochastic process is defined in terms of a function of two other, not necessarily perfectly correlated, stochastic processes. For that purpose we need the following two-dimensional version of Ito's Lemma.  

Theorem 2.6 Suppose $X=\left(X_{t}\right)$ and $Y=\left(Y_{t}\right)$ are two stochastic processes with dynamics  

$$
\begin{array}{r l r}{\tau_{X2t}d z_{2t},}&{{}}&{d Y_{t}=\mu_{Y t}d t+\sigma_{Y1t}d z_{1t}+\sigma_{Y2t}d z_{2}}\end{array}
$$  

where $z_{1}=(z_{1t}$ and $z_{2}~=~(z_{2t})$ are independent standard Brownian motions. Let $g(X,Y,t)$ be $a$ real-valued function for which all the derivatives gt, ox, $\textstyle{\frac{\partial g}{\partial t}},{\frac{\partial g}{\partial X}},{\frac{\partial g}{\partial Y}},{\frac{\partial^{2}g}{\partial X^{2}}},{\frac{\partial^{2}g}{\partial Y^{2}}}$ , and! $\frac{\partial^{2}g}{\partial X\partial Y}$ erist and are continuous. Then the process $W=\left(W_{t}\right)$ defined by $W_{t}=g(X_{t},Y_{t},t)$ is an Ito process with  

$$
\begin{array}{l}{{d W_{t}=\displaystyle\left(\frac{\partial g}{\partial t}+\frac{\partial g}{\partial X}\mu_{X t}+\frac{\partial g}{\partial Y}\mu_{Y t}+\frac{1}{2}\frac{\partial^{2}g}{\partial X^{2}}\left(\sigma_{X1t}^{2}+\sigma_{X2t}^{2}\right)+\frac{1}{2}\frac{\partial^{2}g}{\partial Y^{2}}\left(\sigma_{Y1t}^{2}+\sigma_{Y2t}^{2}\right)}}\ {{\mathrm{}+\frac{\partial^{2}g}{\partial X\partial Y}\left(\sigma_{X1t}\sigma_{Y1t}+\sigma_{X2t}\sigma_{Y2t}\right)\displaystyle\right)d t}}\ {{\mathrm{}+\displaystyle\left(\frac{\partial g}{\partial X}\sigma_{X1t}+\frac{\partial g}{\partial Y}\sigma_{Y1t}\right)d z_{1t}+\left(\frac{\partial g}{\partial X}\sigma_{X2t}+\frac{\partial g}{\partial Y}\sigma_{Y2t}\right)d z_{2t},}}\end{array}
$$  

where the dependence of all the partial derivatives on $\left({X}_{t},Y_{t},t\right)$ has been notationally suppressed.  

Alternatively, the result can be written more compactly as  

$$
d W_{t}=\frac{\partial g}{\partial t}d t+\frac{\partial g}{\partial X}d X_{t}+\frac{\partial g}{\partial Y}d Y_{t}+\frac{1}{2}\frac{\partial^{2}g}{\partial X^{2}}\left(d X_{t}\right)^{2}+\frac{1}{2}\frac{\partial^{2}g}{\partial Y^{2}}\left(d Y_{t}\right)^{2}+\frac{\partial^{2}g}{\partial X\partial Y}\left(d X_{t}\right)\left(d Y_{t}\right),
$$  

where it is understood that $(d t)^{2}=d t\cdot d z_{1t}=d t\cdot d z_{2t}=d z_{1t}\cdot d z_{2t}=0$  

Example 2.1 Suppose that the dynamics of $X$ and $Y$ are given by (2.16) and $W_{t}=X_{t}Y_{t}$ .In order to find the dynamics of $W$ , we apply the above version of Ito's Lemma with the function $g(X,Y)=X Y$ . The relevant partial derivatives are  

$$
{\frac{\partial g}{\partial t}}=0,\quad{\frac{\partial g}{\partial X}}=Y,\quad{\frac{\partial g}{\partial Y}}=X,\quad{\frac{\partial^{2}g}{\partial X^{2}}}=0,\quad{\frac{\partial^{2}g}{\partial Y^{2}}}=0,\quad{\frac{\partial^{2}g}{\partial X\partial Y}}=1.
$$  

Hence,  

$$
d W_{t}=Y_{t}d X_{t}+X_{t}d Y_{t}+(d X_{t})(d Y_{t}).
$$  

In particular, if the dynamics of $X$ and $Y$ are written on the form.  

$$
d X_{t}=X_{t}\left[m_{X t}d t+v_{X1t}d z_{1t}+v_{X2t}d z_{2t}\right],\qquadd Y_{t}=Y_{t}\left[m_{Y t}d t+v_{Y1t}d z_{1t}+v_{Y2t}d z_{2t}\right],
$$  

we get  

$$
d W_{t}=W_{t}\left[\left(m_{X t}+m_{Y t}+v_{X1t}v_{Y1t}+v_{X2t}v_{Y2t}\right)d t+\left(v_{X1t}+v_{Y1t}\right)d z_{1t}+\left(v_{X2t}+v_{Y2t}\right)d z_{2t}\right].
$$  

For the special case, where both $X$ and $Y$ are geometric Brownian motion so that $m_{x}$ $m_{Y}$ $v_{X1}$ $v_{X2}$ $v_{Y1}$ , and $v_{Y2}$ are all constants, it follows that $W_{t}=X_{t}Y_{t}$ is also a geometric Brownian motion.  

Example 2.2Define $W_{t}=X_{t}/Y_{t}$ . In this case we need to apply Ito's Lemma with the function $g(X,Y)=X/Y$ which has derivatives  

$$
{\frac{\partial g}{\partial t}}=0,\quad{\frac{\partial g}{\partial X}}={\frac{1}{Y}},\quad{\frac{\partial g}{\partial Y}}=-{\frac{X}{Y^{2}}},\quad{\frac{\partial^{2}g}{\partial X^{2}}}=0,\quad{\frac{\partial^{2}g}{\partial Y^{2}}}=2{\frac{X}{Y^{3}}},\quad{\frac{\partial^{2}g}{\partial X\partial Y}}=-{\frac{1}{Y^{2}}}.
$$  

Then  

$$
\begin{array}{l}{{d W_{t}=\displaystyle\frac{1}{Y_{t}}d X_{t}-\displaystyle\frac{X_{t}}{Y_{t}^{2}}d Y_{t}+\displaystyle\frac{X_{t}}{Y_{t}^{3}}(d Y_{t})^{2}-\displaystyle\frac{1}{Y_{t}^{2}}(d X_{t})(d Y_{t})}}\ {{~=W_{t}\left[\displaystyle\frac{d X_{t}}{X_{t}}-\displaystyle\frac{d Y_{t}}{Y_{t}}+\left(\displaystyle\frac{d Y_{t}}{Y_{t}}\right)^{2}-\displaystyle\frac{d X_{t}}{X_{t}}\displaystyle\frac{d Y_{t}}{Y_{t}}\right].}}\end{array}
$$  

In particular, if the dynamics of $X$ and $Y$ are given by (2.20), the dynamics of $W_{t}=X_{t}/Y_{t}$ becomes  

$$
\begin{array}{c}{{d W_{t}=W_{t}\Big[\left(m_{X t}-m_{Y t}+\left(v_{Y1t}^{2}+v_{Y2t}^{2}\right)-\left(v_{X1t}v_{Y1t}+v_{X2t}v_{Y2t}\right)\right)~d t}}\ {{{}~+\left(v_{X1t}-v_{Y1t}\right)~d z_{1t}+\left(v_{X2t}-v_{Y2t}\right)~d z_{2t}\Big].}}\end{array}
$$  

Note that for the special case, where both $X$ and $Y$ are geometric Brownian motions,. $W=X/Y$   
is also a geometric Brownian motion..  

We can apply the two-dimensional version of Ito's Lemma to prove the following useful result relating expected discounted values and the drift rate..  

Theorem 2.7 Under suitable regularity conditions, the relative drift rate of an Ito process $X=$ $X_{t}$ ) is given by the process. $m=\left(m_{t}\right)$ if and only if $\begin{array}{r}{X_{t}=\operatorname{E}_{t}[X_{T}\exp\{-\int_{t}^{T}m_{s}d s\}]}\end{array}$  

Proof: Suppose first that the relative drift rate is given by. $m$ so that $d X_{t}=X_{t}[m_{t}d t+v_{t}d z_{t}]$ Let us use Ito's Lemma to identify the dynamics of the process. $\begin{array}{r}{W_{t}=X_{t}\exp\{-\int_{0}^{t}m_{s}d s\}}\end{array}$ or $W_{t}~=~X_{t}Y_{t}$ , where $\begin{array}{r}{Y_{t}~=~\exp\{-\int_{0}^{t}m_{s}d s\}}\end{array}$ .Note that $d Y_{t}~=~-Y_{t}m_{t}d t$ so that $Y$ is a locally deterministic stochastic process. From Example 2.1, the dynamics of $W$ becomes  

$$
d W_{t}=W_{t}\left[\left(m_{t}-m_{t}+0\right)d t+v_{t}d z_{t}\right]=W_{t}v_{t}d z_{t}.
$$  

Since $W$ has zero drift, it is a martingale. It follows that $W_{t}=\mathrm{E}_{t}[W_{T}]$ , i.e. $\begin{array}{r l r}{X_{t}\exp\{-\int_{0}^{t}m_{s}d s\}=}\end{array}$ $\begin{array}{r}{\mathrm{E}_{t}[X_{T}\exp\{-\int_{0}^{T}m_{s}d s\}]}\end{array}$ and hence $\begin{array}{r}{X_{t}=\operatorname{E}_{t}[X_{T}\exp\{-\int_{t}^{T}m_{s}d s\}]}\end{array}$  

The absolute drift of $X$ is the limit of $\begin{array}{r}{\frac{1}{\Delta t}\operatorname{E}_{t}[X_{t+\Delta t}-X_{t}]}\end{array}$ as $\Delta t\rightarrow0$ . If $\begin{array}{r}{X_{t}=\operatorname{E}_{t}[X_{T}\exp\{-\int_{t}^{T}m_{s}d s\}]}\end{array}$ for all $t$ , then  

$$
\begin{array}{r l}&{\displaystyle\frac{1}{\Delta t}\operatorname{E}_{t}\big[X_{t+\Delta t}-X_{t}\big]=\frac{1}{\Delta t}\operatorname{E}_{t}\left[\left(\operatorname{E}_{t+\Delta t}\left[X_{T}e^{-\int_{t+\Delta t}^{T}m_{s}d s}\right]\right)-\left(\operatorname{E}_{t}\left[X_{T}e^{-\int_{t}^{T}m_{s}d s}\right]\right)\right]}\ &{\quad\quad\quad=\frac{1}{\Delta t}\operatorname{E}_{t}\left[X_{T}e^{-\int_{t+\Delta t}^{T}m_{s}d s}-X_{T}e^{-\int_{t}^{T}m_{s}d s}\right]}\ &{\quad\quad=\operatorname{E}_{t}\left[X_{T}e^{-\int_{t}^{T}m_{s}d s}\frac{e^{\int_{t}^{t+\Delta t}m_{s}d s}-1}{\Delta t}\right]}\ &{\quad\quad\quad\rightarrow m_{t}\operatorname{E}_{t}\left[X_{T}e^{-\int_{t}^{T}m_{s}d s}\right]=m_{t}X_{t},}\end{array}
$$  

i.e. the relative drift rate equals $m_{t}$  

# 2.7.2 $K$ -dimensional processes  

Simultaneously modeling the dynamics of a lot of economic quantities requires the use of a lot of shocks to those quantities. For that purpose we will work with vectors of shocks. In particular for continuous-time modeling, we will represent shocks to the economy by a vector standard Brownian motion. We define this below and state Ito's Lemma for processes of a general dimension.  

A $K$ -dimensional standard Brownian motion ${\boldsymbol{z}}=(z_{1},\dots,z_{K})^{\top}$ is a stochastic process. where the individual components. $z_{i}$ are mutually independent one-dimensional standard Brownian motions. If we let $\mathbf{0}=(0,\ldots,0)^{\top}$ denote the zero vector in. $\mathbb{R}^{K}$ and let. $\underline{{\underline{{I}}}}$ denote the identity matrix of dimension $K\times K$ (the matrix with ones in the diagonal and zeros in all other entries), then we can write the defining properties of a $K$ -dimensional Brownian motion. $_{z}$ as follows:  

(i) $z_{\mathrm{0}}=\mathbf{0}$ (ii) for all $t,t^{\prime}\geq0$ with $t<t^{\prime}$ .. $z_{t^{\prime}}-z_{t}\sim N(\mathbf{0},(t^{\prime}-t)\underline{{\underline{{I}}}})$ [normally distributed increments], (ii) for all $0\leq t_{0}<t_{1}<\dots<t_{n}$ , the random variables $z_{t_{1}}-z_{t_{0}},\dots,z_{t_{n}}-z_{t_{n-1}}$ are mutually independent [independent increments], (iv) $_{z}$ has continuous sample paths in $\mathbb{R}^{K}$  

Here, $N(\mathbf{\boldsymbol{a}},\underline{{\boldsymbol{b}}})$ denotes a $K$ -dimensional normal distribution with mean vector $\pmb{a}$ and variancecovariance matrix $\boldsymbol{\underline{{\underline{{b}}}}}$ . As for standard Brownian motions, we can also define multi-dimensional. generalized Brownian motions, which simply are vectors of independent one-dimensional generalized Brownian motions.  

A $K$ -dimensional diffusion process $\pmb{X}=(X_{1},\ldots,X_{K})^{\top}$ is a process with increments of the form  

$$
d X_{t}=\mu(X_{t},t)d t+\underline{{\underline{{\sigma}}}}(X_{t},t)d z_{t},
$$  

where is a function from $\mathbb{R}^{K}\times\mathbb{R}_{+}$ into $\mathbb{R}^{K}$ , and is a function from $\mathbb{R}^{K}\times\mathbb{R}_{+}$ into the space $\pmb{\mu}$ $\underline{{\underline{{\sigma}}}}$   
of $K\times K$ -matrices. As before, $_{z}$ is a $K$ -dimensional standard Brownian motion. The evolution of.   
the multi-dimensional diffusion can also be written componentwise as  

$$
\begin{array}{l}{\displaystyle d X_{i t}=\mu_{i}({\pmb X}_{t},t)d t+\pmb{\sigma}_{i}({\pmb X}_{t},t)^{\top}d z_{t}}\ {\displaystyle=\mu_{i}({\pmb X}_{t},t)d t+\sum_{k=1}^{K}\sigma_{i k}({\pmb X}_{t},t)d z_{k t},\quad i=1,\dots,K,}\end{array}
$$  

where $\pmb{\sigma}_{i}(\pmb{X}_{t},t)^{\top}$ is the $i$ th row of the matrix $\underline{{\underline{{\sigma}}}}\left(\boldsymbol{X}_{t},t\right)$ , and $\sigma_{i k}(X_{t},t)$ is the $(i,k)$ 'th entry (i.e. the entry in row $i$ , column $k$ ). Since $d z_{1t},\dots,d z_{K t}$ are mutually independent and all $N(0,d t)$ distributed, the expected change in the $i$ 'th component process over an infinitesimal period is  

$$
\operatorname{E}_{t}[d X_{i t}]=\mu_{i}(X_{t},t)d t,\quad i=1,\ldots,K,
$$  

so that $\mu_{i}$ can be interpreted as the drift of the. $i$ 'th component. Furthermore, the covariance. between changes in the. $\imath$ 'th and the. $j$ th component processes over an infinitesimal period becomes  

$$
\begin{array}{l}{{\displaystyle\mathrm{Cov}_{t}[d X_{i t},d X_{j t}]=\mathrm{Cov}_{t}\left[\displaystyle\sum_{k=1}^{K}\sigma_{i k}(X_{t},t)d z_{k t}\displaystyle\sum_{l=1}^{K}\sigma_{j l}(X_{t},t)d z_{l t}\right]}}\ {{\displaystyle\qquad=\sum_{k=1}^{K}\sum_{l=1}^{K}\sigma_{i k}(X_{t},t)\sigma_{j l}(X_{t},t)\mathrm{Cov}_{t}[d z_{k t},d z_{l t}]}}\ {{\displaystyle\qquad=\sum_{k=1}^{K}\sigma_{i k}(X_{t},t)\sigma_{j k}(X_{t},t)d t}}\ {{\displaystyle\qquad=\sigma_{i}(X_{t},t)^{\top}\sigma_{j}(X_{t},t)d t,\quad i,j=1,\ldots,K,}}\end{array}
$$  

where we have applied the usual rules for covariances and the independence of the components of $_{z}$ . In particular, the variance of the change in the. $i$ 'th component process of an infinitesimal. period is given by  

$$
\operatorname{Var}_{t}[d X_{i t}]=\operatorname{Cov}_{t}[d X_{i t},d X_{i t}]=\sum_{k=1}^{K}\sigma_{i k}(X_{t},t)^{2}d t=\|\sigma_{i}(X_{t},t)\|^{2}d t,\quad i=1,\dots,K.
$$  

The volatility of the $i$ th component is given by $\|\pmb{\sigma}_{i}(\pmb{X}_{t},t)\|$ . The variance-covariance matrix of changes of $X_{t}$ over the next instant is $\underline{{\Sigma}}(X_{t},t)d t=\underline{{\underline{{\sigma}}}}(X_{t},t)\underline{{\underline{{\sigma}}}}(X_{t},t)^{\top}d t$ . The correlation between instantaneous increments in two component processes is  

$$
\mathrm{Corr}_{t}[d X_{i t},d X_{j t}]=\frac{\sigma_{i}(X_{t},t)^{\top}\sigma_{j}(X_{t},t)d t}{\sqrt{\|\sigma_{i}(X_{t},t)\|^{2}d t\|\sigma_{j}(X_{t},t)\|^{2}d t}}=\frac{\sigma_{i}(X_{t},t)^{\top}\sigma_{j}(X_{t},t)}{\|\sigma_{i}(X_{t},t)\|\|\sigma_{j}(X_{t},t)\|},
$$  

which can be any number in $[-1,1]$ depending on the elements of $\sigma_{i}$ and $\sigma_{j}$  

Similarly, we can define a $K$ -dimensional Ito process $\pmb{x}=(X_{1},\ldots,X_{K})^{\top}$ to be a proces: with increments of the form  

$$
d X_{t}=\mu_{t}d t+\underline{{\underline{{\sigma}}}}_{t}d z_{t},
$$  

where ${\pmb\mu}=({\pmb\mu}_{t})$ is a $K$ -dimensional stochastic process and $\underline{{\underline{{\sigma}}}}=\left(\underline{{\underline{{\sigma}}}}_{t}\right)$ is a stochastic process with values in the space of $K\times K$ --matrices.  

Next, we state a multi-dimensional version of Ito's Lemma, where a one-dimensional process is defined as a function of time and a multi-dimensional process.  

Theorem 2.8 Let $\pmb{X}=(\pmb{X}_{t})_{t\geq0}$ be an Ito process in $\mathbb{R}^{K}$ with dynamics $d X_{t}=\mu_{t}d t+\underline{{\underline{{\sigma}}}}_{t}d z_{t}$ or, equivalently,  

$$
d X_{i t}=\mu_{i t}d t+\sigma_{i t}^{\top}d z_{t}=\mu_{i t}d t+\sum_{k=1}^{K}\sigma_{i k t}d z_{k t},\quad i=1,\ldots,K,
$$  

where $z_{1},\dots,z_{K}$ are independent standard Brownian motions, and $\mu_{i}$ and $\sigma_{i k}$ are well-behaved stochastic processes.  

Let $g(X,t)$ $\textstyle{\frac{\partial g}{\partial t}}$ $\textstyle{\frac{\partial g}{\partial X_{i}}}$ , and $\frac{{{\partial}^{2}}g}{\partial{{X}_{i}}\partial{{X}_{j}}}$ Cenis and are continuous. Then the process $y=(y_{t})_{t\geq0}$ defined by $y_{t}=g(X_{t},t)$ is also an Ito process with. dynamics  

$$
\begin{array}{l}{{\displaystyle d y_{t}=\left(\frac{\partial g}{\partial t}({\pmb X}_{t},t)+\sum_{i=1}^{K}\frac{\partial g}{\partial X_{i}}({\pmb X}_{t},t){\mu_{i t}}+\frac{1}{2}\sum_{i=1}^{K}\sum_{j=1}^{K}\frac{\partial^{2}g}{\partial X_{i}\partial X_{j}}({\pmb X}_{t},t)\gamma_{i j t}\right)d t}}\ {{\displaystyle~+\sum_{i=1}^{K}\frac{\partial g}{\partial X_{i}}({\pmb X}_{t},t)\sigma_{i1t}d z_{1t}+\cdot\cdot\cdot+\sum_{i=1}^{K}\frac{\partial g}{\partial X_{i}}({\pmb X}_{t},t)\sigma_{i K t}d z_{K t}},}\end{array}
$$  

where $\gamma_{i j}=\sigma_{i1}\sigma_{j1}+\cdot\cdot\cdot+\sigma_{i K}\sigma_{j K}$ is the covariance between the processes $X_{i}$ and $X_{j}$  

The result can also be written as  

$$
d y_{t}=\frac{\partial g}{\partial t}(\pmb{X}_{t},t)d t+\sum_{i=1}^{K}\frac{\partial g}{\partial X_{i}}(\pmb{X}_{t},t)d X_{i t}+\frac{1}{2}\sum_{i=1}^{K}\sum_{j=1}^{K}\frac{\partial^{2}g}{\partial X_{i}\partial X_{j}}(\pmb{X}_{t},t)(d X_{i t})(d X_{j t}),
$$  

where in the computation of $(d X_{i t})(d X_{j t})$ one must use the rules $(d t)^{2}=d t\cdot d z_{i t}=0$ for all. $i$ $d z_{i t}\cdot d z_{j t}=0$ for $i\neq j$ , and $(d z_{i t})^{2}=d t$ for all $i$ . Alternatively, the result can be expressed using vector and matrix notation:  

$$
{^{\prime}y_{t}}=\left(\frac{{\partial g}}{{\partial t}}(X_{t},t)+\left({\frac{{\partial g}}{{\partial X}}(X_{t},t)}\right)^{\top}\mu_{t}+\frac{1}{2}\mathrm{tr}\left({\underline{{\sigma}}^{\top}\left[\frac{{\partial^{2}g}}{{\partial X^{2}}}(X_{t},t)\right]\underline{{\sigma}}_{t}}\right)\right)d t+\left({\frac{{\partial g}}{{\partial X}}(X_{t},t)}\right)^{\top}\underline{{\sigma}}_{t}d z_{t}
$$  

where  

$$
{\frac{\partial g}{\partial X}}(X_{t},t)={\left(\begin{array}{l}{{\frac{\partial g}{\partial X_{1}}}(X_{t},t)}\ {\qquad\cdots}\ {\qquad\cdots}\ {{\frac{\partial g}{\partial X_{k}}}(X_{t},t){\right)},\quad{\frac{\partial^{2}g}{\partial X^{2}}}(X_{t},t)={\left(\begin{array}{l l l l}{{\frac{\partial^{2}g}{\partial X_{1}^{2}}}(X_{t},t)}&{{\frac{\partial^{2}g}{\partial X_{1}\partial X_{2}}}(X_{t},t)}&{\cdots}&{{\frac{\partial^{2}g}{\partial X_{1}\partial X_{k}}}(X_{t},t)}\ {{\frac{\partial^{2}g}{\partial X_{2}\partial X_{1}}}(X_{t},t)}&{{\frac{\partial^{2}g}{\partial X_{2}^{2}}}(X_{t},t)}&{\cdots}&{{\frac{\partial^{2}g}{\partial X_{2}\partial X_{k}}}(X_{t},t)}\ {\qquad\cdots}&{{\frac{\partial^{2}g}{\partial X_{k}\partial X_{k}}}(X_{t},t)}&{{\frac{\partial^{2}g}{\partial X_{k}\partial X_{2}}}(X_{t},t)}&{\cdots}&{{\frac{\partial^{2}g}{\partial X_{k}^{2}}}(X_{t},t)}\end{array}\right)}.
$$  

and tr denotes the trace of a quadratic matrix, i.e. the sum of the diagonal elements. For example $\textstyle\operatorname{tr}({\underline{{\underline{{A}}}}})=\sum_{i=1}^{K}A_{i i}$  

The probabilistic properties of a $K$ -dimensional diffusion process is completely specified by the drift function $\pmb{\mu}$ and the variance-covariance function $\stackrel{\Sigma}{=}$ . The values of the variance-covariance function are symmetric and positive-definite matrices. Above we had $\Sigma=\underline{{\underline{{\sigma}}}}\underline{{\underline{{\sigma}}}}^{\top}$ for a general $(K\times K)$ -matrix $\underline{{\underline{{\sigma}}}}$ . But from linear algebra it is well-known that a symmetric and positive-definite matrix can be written as $\hat{\underline{{\underline{{\sigma}}}}}\hat{\underline{{\underline{{\sigma}}}}}^{\top}$ for a lower-triangular matrix $\hat{\underline{{\underline{{\sigma}}}}}$ , i.e. a matrix with $\hat{\sigma}_{i k}=0$ for $k>i$ This is the so-called Cholesky decomposition. Hence, we may write the dynamics as  

$$
\begin{array}{r l}&{d X_{1t}=\mu_{1}(X_{t},t)d t+\hat{\sigma}_{11}(X_{t},t)d z_{1t}}\ &{d X_{2t}=\mu_{2}(X_{t},t)d t+\hat{\sigma}_{21}(X_{t},t)d z_{1t}+\hat{\sigma}_{22}(X_{t},t)d z_{2t}}\ &{\phantom{\hat{e}}\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\ &{d X_{K t}=\mu_{K}(X_{t},t)d t+\hat{\sigma}_{K1}(X_{t},t)d z_{1t}+\hat{\sigma}_{K2}(X_{t},t)d z_{2t}+\cdot\cdot\cdot+\hat{\sigma}_{K K}(X_{t},t)d z_{K t}}\end{array}
$$  

We can think of building up the model by starting with. $X_{1}$ . The shocks to $X_{1}$ are represented by. the standard Brownian motion $z_{1}$ and its coefficient $\hat{\sigma}_{11}$ is the volatility of $X_{1}$ . Then we extend the model to include $X_{2}$ . Unless the infinitesimal changes to $X_{1}$ and $X_{2}$ are always perfectly correlated we need to introduce another standard Brownian motion,. $z_{2}$ . The coefficient. $\hat{\sigma}_{21}$ is fixed to match the covariance between changes to $X_{1}$ and $X_{2}$ and then $\hat{\sigma}_{22}$ can be chosen so that $\sqrt{\hat{\sigma}_{21}^{2}+\hat{\sigma}_{22}^{2}}$ equals the volatility of $X_{2}$ . The model may be extended to include additional processes in the same manner.  

Some authors prefer to write the dynamics in an alternative way with a single standard Brownian  

motion $\hat{z}_{i}$ for each component $X_{i}$ such as  

$$
\begin{array}{r l}&{d X_{1t}=\mu_{1}(X_{t},t)d t+V_{1}(X_{t},t)d\hat{z}_{1t}}\ &{d X_{2t}=\mu_{2}(X_{t},t)d t+V_{2}(X_{t},t)d\hat{z}_{2t}}\ &{~\vdots}\ &{d X_{K t}=\mu_{K}(X_{t},t)d t+V_{K}(X_{t},t)d\hat{z}_{K t}}\end{array}
$$  

Clearly, the coefficient $V_{i}(X_{t},t)$ is then the volatility of $X_{i}$ . To capture an instantaneous non-zero correlation between the different components the standard Brownian motions $\hat{z}_{1},\dots,\hat{z}_{K}$ have to be mutually correlated. Let $\rho_{i j}$ be the correlation between $\hat{z}_{i}$ and $\hat{z}_{j}$ . If (2.31) and (2.30) are meant to represent the same dynamics, we must have  

$$
\begin{array}{r l}&{V_{i}=\sqrt{\hat{\sigma}_{i1}^{2}+\cdot\cdot\cdot+\hat{\sigma}_{i i}^{2}},\quad i=1,\dots,K,}\ &{\rho_{i i}=1;\quad\rho_{i j}=\frac{\sum_{k=1}^{i}\hat{\sigma}_{i k}\hat{\sigma}_{j k}}{V_{i}V_{j}},\rho_{j i}=\rho_{i j},\quad i<j.}\end{array}
$$  
