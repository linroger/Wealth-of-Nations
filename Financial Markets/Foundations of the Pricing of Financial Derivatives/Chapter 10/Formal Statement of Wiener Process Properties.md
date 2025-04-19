---
tags:
  - covariance
  - normal_distribution
  - stochastic_process
  - time_series
  - wiener_process
aliases:
  - Brownian Motion
  - Stochastic Process Properties
  - Wiener Process Properties
key_concepts:
  - Covariance calculation
  - Independent increments
  - Normal distribution
  - Time series properties
  - Wiener process attributes
---

# 10.6 FORMAL STATEMENT OF WIENER PROCESS PROPERTIES

We now bring together important properties of Wiener processes. We also now assume the initial starting time is $t=0$ . Assume constants $t\geq0$ (e.g., calendar time expressed as fraction of year) and $0<b<t$ (e.g., historical point in time compared to. $t$ assuming $t>0$ As previously discussed, the standard Wiener process at time. $t$ or $\mathbf{}\mathbf{}{W}_{t}$ can be expressed with four key attributes:

Initial value of zero or $\mathbb{W}_{t}=0$ if $t=0$
Independent increments. For every $t>0$ , increments $\mathbb{W}_{t+\Delta t}-\mathbb{W}_{t}$ are independent of any $W_{b}$ , where $\Delta t$ denotes an increment of calendar time.
Normal distribution. For any $b$ $\mathbb{W}_{t}-\mathbb{W}_{b}$ is distributed normal with mean 0 and variance $t-b$
Continuity. For any $t.$ $\mathbf{}\mathbf{}{W}_{t}$ is continuous in $t$

We now briefly review selected properties of the Wiener process as well as introduce other properties useful for addressing tasks using Wiener processes.

# 10.6.1 Univariate Properties

As previously discussed, the standard Wiener process follows a normal distribution where the probability density function can be expressed as (recall we assume the initial time is O):

$$
n_{\mathrm{W}_{t}}\left(x\right)=\frac{e^{-\displaystyle\frac{x^{2}}{2t}}}{\sqrt{2\pi t}}.
$$

Note that

$$
E\left(W_{t}\right)=0\mathrm{andvar}\left(W_{t}\right)=t.
$$

Recall from the definition of variance and assuming $t>0$ , we have var $\left(\mathrm{W}_{t}\right)=E\left(\mathrm{W}_{t}^{2}\right)-$ $E\big(\mathrm{W}_{t}\big)^{2}=t-0=t.$

# 10.6.2 Selected Time Series Properties

Again, assume constants $t>0$ (e.g., calendar time expressed as a fraction of a year) and $0<b<t$ (e.g., historical point in time compared to $t$ ). The covariance of. $\mathbf{}\mathbf{}{W}_{t}$ and $W_{b}$ is

$$
\mathrm{cov}\left(\mathrm{W}_{t},\mathrm{W}_{b}\right)=b.
$$

Note that between 0 and $b$ $\mathbf{}\mathbf{}{W}_{t}$ and $W_{b}$ are perfectly positively correlated so the covariance is one. Further, between $b$ and $t.$ $\mathbf{}\mathbf{}{W}_{t}$ and $\mathbb{W}_{b}$ are uncorrelated, so the covariance is zero. Recall we assumed $t>b$ . Given independent increments as mentioned previously, we have cov $\left(\boldsymbol{W_{t}}-\boldsymbol{W_{b}}+\boldsymbol{W_{b}},\boldsymbol{W_{b}}\right)=\mathrm{cov}\left(\boldsymbol{W_{t}}-\boldsymbol{W_{b}},\boldsymbol{W_{b}}\right)+\mathrm{cov}\left(\boldsymbol{W_{b}},\boldsymbol{W_{b}}\right)=0+\boldsymbol{b}=\boldsymbol{b}$

For constants $c_{1}$ and $c_{2}$ , based on standard properties of covariance covered in Chapter 4, recall that

$$
\operatorname{cov}\left(c_{1}W_{t},c_{2}W_{b}\right)=c_{1}c_{2}\operatorname{cov}\left(W_{t},W_{b}\right)=c_{1}c_{2}b.
$$

Thus, the correlation between $c_{1}\mathrm{W}_{t}$ and $c_{2}W_{b}$ is

$$
\rho\left(c_{1}W_{t},c_{2}W_{b}\right)\equiv\frac{\mathrm{cov}\left(c_{1}W_{t},c_{2}W_{b}\right)}{\sqrt{c_{1}^{2}\mathrm{var}\left(W_{t}\right)}\sqrt{c_{2}^{2}\mathrm{var}\left(W_{b}\right)}}=\frac{\mathrm{cov}\left(W_{t},W_{b}\right)}{\sqrt{\mathrm{var}\left(W_{t}\right)}\sqrt{\mathrm{var}\left(W_{b}\right)}}=\frac{b}{\sqrt{t b}}=\sqrt{\frac{c_{2}^{2}\mathrm{var}\left(W_{t}\right)}{\sqrt{c_{2}^{2}\mathrm{var}\left(W_{b}\right)}}}.
$$

Now consider two generic points in time $j>0$ and $k>0$ and the same Wiener process;. however, we do not know whether $j>k,j<k$ , or $j=k$ . In this case,.

$$
\operatorname{cov}\left(W_{j},W_{k}\right)=\operatorname*{min}\left(j,k\right).
$$

If we assume $j>k$ , then based on Equation (10.17), we know cov $\left(\mathbb{W}_{j},\mathbb{W}_{k}\right)=k$ . Similarly, $j<k$ , we know cov $\left(\mathbb{W}_{j},\mathbb{W}_{k}\right)=j$ Thus, Equation (10.20) holds for all $j$ and $k$

$$
\rho\left(W_{j},W_{k}\right)={\frac{\operatorname{cov}\left(W_{j},W_{k}\right)}{\sqrt{\operatorname{var}\left(W_{j}\right)}{\sqrt{\operatorname{var}\left(W_{k}\right)}}}}={\frac{\operatorname*{min}\left(j,k\right)}{\sqrt{j k}}}={\sqrt{\frac{\operatorname*{min}\left(j,k\right)}{\operatorname*{max}\left(j,k\right)}}}.
$$

Now consider the same point in time $t>0$ and two correlated Wiener processes $(\mathbb{W}_{1,t}$ and $\mathbb{W}_{2,t}\mathrm{i}$ . That is, while $\varepsilon_{1,t}$ and $\varepsilon_{2,t}$ are independent, the Wiener processes are correlated. In this case, one of the Wiener processes (say $\mathbb{W}_{2,t}$ ) can be expressed as a linear function of the other Wiener process $(\mathbb{W}_{1,t})$ and an independent Wiener process, denoted $z_{t}$ . That is,

$$
\begin{array}{r}{W_{2,t}=\rho W_{1,t}+\left(1-\rho\right)z_{t}.}\end{array}
$$

In this case, we note

$$
E\left(W_{2,t}\right)=\rho E\left(W_{1,t}\right)+\left(1-\rho\right)E\left(z_{t}\right)=\rho0+\left(1-\rho\right)0=0,
$$

$$
\begin{array}{r l}&{\mathrm{var}\left(\boldsymbol{W}_{2,t}\right)=\rho^{2}\mathrm{var}\left(\boldsymbol{W}_{1,t}\right)+(1-\rho)^{2}\mathrm{var}\left(\boldsymbol{z}_{t}\right)+2\mathrm{cov}\left[\rho\boldsymbol{W}_{1,t},(1-\rho)\boldsymbol{z}_{t}\right]}\ &{\phantom{\mathrm{var}\left(\boldsymbol{W}_{1,t}\right)=}=\rho^{2}t+(1-\rho)^{2}t+2\rho\left(1-\rho\right)\mathrm{cov}\left(\boldsymbol{W}_{1,t},\boldsymbol{z}_{t}\right)}\ &{\phantom{\mathrm{var}\left(\boldsymbol{W}_{1,t}\right)=}=\rho^{2}t+(1-\rho)^{2}t+2\rho\left(1-\rho\right)t=t,\mathrm{and}}\ &{\phantom{\mathrm{var}\left(\boldsymbol{W}_{1,t},\boldsymbol{W}_{2,t}\right)=}\left(\boldsymbol{W}_{1,t},\rho\boldsymbol{W}_{1,t}+\left(1-\rho\right)\boldsymbol{z}_{t}\right)=\rho t+\left(1-\rho\right)\mathrm{cov}\left(\boldsymbol{W}_{1,t},\boldsymbol{z}_{t}\right)=\rho^{2}t+\left(\rho\right)\mathrm{cov}\left(\boldsymbol{W}_{1,t}\right),}\end{array}
$$

As a reminder, the last result occurs because $z_{t}$ and $\mathbb{W}_{1,t}$ are independent. Now, we have

$$
\rho\left(\boldsymbol{W}_{1,t},\boldsymbol{W}_{2,t}\right)=\frac{\mathrm{cov}\left(\boldsymbol{W}_{1,t},\boldsymbol{W}_{2,t}\right)}{\sqrt{\mathrm{var}\left(\boldsymbol{W}_{1,t}\right)}\sqrt{\mathrm{var}\left(\boldsymbol{W}_{2,t}\right)}}=\frac{\rho t}{\sqrt{t}\sqrt{t}}=\rho.
$$

These Wiener process properties will be useful in future chapters.
