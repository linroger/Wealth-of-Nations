---
tags:
  - asset_pricing
  - efficient_returns
  - excess_returns
  - mean_variance_frontier
  - portfolio_returns
aliases:
  - Efficient Portfolios
  - Hansen and Richard (1987)
  - Mean-Variance Analysis
key_concepts:
  - Asset pricing theory
  - Constant-mimicking return
  - Excess return definition
  - Mean-variance efficient returns
  - Portfolio return variance
---

# 9.4 Mean-variance efficient returns and pricing factors  

We have introduced the mean-variance frontier earlier in Sections 4.6.3 and 6.2.5. Here we provide. an alternative characterization of the mean-variance efficient returns and study the link between mean-variance efficiency and asset pricing theory..  

As before let $\pmb{R}=\left(R_{1},\ldots,R_{I}\right)^{\top}$ denote the vector of gross returns on the $I$ traded assets and define $\pmb{\mu}=\mathrm{E}[\pmb{R}]$ and $\underline{{\underline{{\Sigma}}}}=\mathrm{Var}[{\boldsymbol{R}}]$ . A portfolio $\pi$ is mean-variance efficient if there is an $m\in\mathbb{R}$ so that $\pi$ solves  

$$
\operatorname*{min}_{\boldsymbol{\pi}}\boldsymbol{\pi}^{\top}\underline{{\boldsymbol{\Sigma}}}\boldsymbol{\pi}\quad\mathrm{s.t.}\quad\boldsymbol{\pi}^{\top}\boldsymbol{\mu}=m,\quad\boldsymbol{\pi}^{\top}{\bf1}=1,
$$  

i.e. $\pi$ has the lowest return variance among all portfolios with expected return $m$  

# 9.4.1 Orthogonal characterization  

Following Hansen and Richard (1987) we will show that a return $R$ is mean-variance efficient if and only if it can be written on the form ${\cal R}={\cal R}^{*}+w{\cal R}^{e*}$ for some number $w$ . Here $R^{*}$ is the. return on the portfolio corresponding to the dividend $\zeta^{\ast}$ defined in (4.46) and. $R^{e*}$ is a particular excess return to be defined shortly. This characterization of the mean-variance portfolios turn out to be preferable for discussing the link between mean-variance analysis and asset pricing models.  

# $R^{*}$ and mean-variance analysis  

How does $R^{*}$ fit into the mean-variance framework? The following lemma shows that it is a meanvariance efficient return on the downward-sloping part of the mean-variance frontier. Furthermore, it is the return with minimum second moment. (Recall that the second moment of a random variable $x$ is $\mathrm{E}[x^{2}]$  

Lemma 9.2 $R^{*}$ has the following properties:  

(a) $R^{*}$ is the return that has minimum second moment,   
(b) $R^{*}$ is a mean-variance efficient return located on the downward-sloping part of the efficient frontier.  

Proof: The return on a portfolio $\pi$ is the random variable $R^{\pi}=\pi^{\top}R$ . The second moment of this return is $\begin{array}{r}{\operatorname{E}[(R^{\pi})^{2}]=\pi^{\top}\operatorname{E}[R R^{\top}]\pi}\end{array}$ . Consider the minimization problem  

$$
\operatorname*{min}_{\pi}\pi^{\top}\operatorname{E}[R R^{\top}]\pi\qquad\mathrm{s.t.}\quad\pi^{\top}{\bf1}=1.
$$  

The Lagrangian is $\mathcal{L}=\pi^{\top}\operatorname{E}[R R^{\top}]\pi+\lambda\left(1-\pi^{\top}\mathbf{1}\right)$ , where $\lambda$ is the Lagrange multiplier. The first-order condition for $\pi$ is  

$$
2\operatorname{E}[R R^{\top}]\pi-\lambda\mathbf{1}=0\quad\Rightarrow\quad\pi=\frac{\lambda}{2}\left(\operatorname{E}[R R^{\top}]\right)^{-1}\mathbf{1}.
$$  

Imposing the constraint $\pmb{\pi}^{\top}\mathbf{1}=1$ , we get $\lambda/2=1/({\bf1}^{\top}\operatorname{E}[R R^{\prime}]{\bf1})$ , and substituting this into the above expression for $\pi$ , we see that $\pi$ is indeed identical to $\pi^{*}$ in (4.53).  

Since $\pi^{*}$ is the portfolio minimizing the second moment of gross returns among all portfolios, it is also the portfolio minimizing the second moment of gross returns among the portfolios with the same mean return as $\pi^{*}$ , i.e. portfolios with $\operatorname{E}[R^{\pi}]=\operatorname{E}[R^{*}]$ . For these portfolios the variance of. return is  

$$
\operatorname{Var}\left[R^{\pi}\right]=\operatorname{E}[(R^{\pi})^{2}]-(\operatorname{E}[R^{\pi}])^{2}=\operatorname{E}[(R^{\pi})^{2}]-\left(\operatorname{E}[R^{*}]\right)^{2}.
$$  

It then follows that $\pi^{*}$ is the portfolio minimizing the variance of return among all the portfolios.   
having the same mean return as. $\pi^{*}$ . Hence, $\pi^{*}$ is indeed a mean-variance efficient portfolio. In a.   
(standard deviation, mean)-diagram returns with same second moment. $K=\operatorname{E}[(R^{\pi})^{2}]$ yield points.   
on a circle with radius $\sqrt{K}$ centered in (0,0), since $\left(\sigma(R^{\pi})\right)^{2}+\left(\operatorname{E}[R^{\pi}]\right)^{2}=\operatorname{E}[(R^{\pi})^{2}]$ . The return.   
$R^{*}$ therefore corresponds to a point on the downward-sloping part of the efficient frontier.  

# The constant-mimicking return  

In a market without a risk-free asset you may wonder how close you can get to a risk-free dividend. Of course this will depend on what you mean by "close."' If you apply a mean-square measure, the. distance between the dividend $D^{\theta}=\theta^{\top}D$ of a portfolio $\pmb{\theta}$ and a risk-free dividend of 1 is  

$$
{\begin{array}{r l}&{\operatorname{E}\left[(D^{\theta}-1)^{2}\right]=\operatorname{E}\left[\left(\theta^{\top}D-1\right)^{2}\right]}\ &{\qquad=\operatorname{E}\left[\theta^{\top}D D^{\top}\theta+1-2\theta^{\top}D\right]}\ &{\qquad=\theta^{\top}\operatorname{E}\left[D D^{\top}\right]\theta+1-2\theta^{\top}\operatorname{E}\left[D\right].}\end{array}}
$$  

Minimizing with respect to $\pmb{\theta}$ , we get $\theta_{\mathrm{cm}}=\left(\mathrm{E}\left[D D^{\top}\right]\right)^{-1}\mathrm{E}\left[D\right]$ where the subscript "cm' is short for "constant-mimicking." Let us transform this to a vector $\pi_{\mathrm{cm}}$ of portfolio weights by using (3.6). Applying (3.2) and (4.52), we get  

$$
\begin{array}{r l}&{\mathrm{diag}(P)\pmb{\theta}_{\mathrm{cm}}=\mathrm{diag}(P)\left(\mathrm{E}\left[D D^{\top}\right]\right)^{-1}\mathrm{E}\left[D\right]}\ &{\qquad=\mathrm{diag}(P)[\mathrm{diag}(P)]^{-1}\left(\mathrm{E}\left[R R^{\top}\right]\right)^{-1}\left[\mathrm{diag}(P)\right]^{-1}\mathrm{E}\left[D\right]}\ &{\qquad=\left(\mathrm{E}\left[R R^{\top}\right]\right)^{-1}\mathrm{E}\left[R\right]}\end{array}
$$  

so that  

$$
\pi_{\mathrm{cm}}=\frac{1}{\mathbf{1}^{\top}\left(\mathrm{E}\left[R R^{\top}\right]\right)^{-1}\mathrm{E}\left[R\right]}\left(\mathrm{E}\left[R R^{\top}\right]\right)^{-1}\mathrm{E}\left[R\right]=\frac{\mathrm{E}[(R^{*})^{2}]}{\mathrm{E}[R^{*}]}\left(\mathrm{E}\left[R R^{\top}\right]\right)^{-1}\mathrm{E}\left[R\right],
$$  

where the last equality comes from (4.58). The constant-mimicking return is thus  

$$
R_{\mathrm{cm}}=\left(\pmb{\pi}_{\mathrm{cm}}\right)^{\top}\pmb{R}=\frac{\operatorname{E}[\left(R^{*}\right)^{2}]}{\operatorname{E}[R^{*}]}\operatorname{E}\left[\pmb{R}\right]^{\top}\left(\operatorname{E}\left[\pmb{R}\pmb{R}^{\top}\right]\right)^{-1}\pmb{R}.
$$  

Excess returns and $R^{e*}$  

An excess return is simply the difference between two returns. Since any return corresponds to a dividend for a unit initial payment, an excess return can be seen as a dividend for a zero initial payment. Of course, in absence of arbitrage, a non-zero excess return will turn out positive in some states and negative in other states.  

Typically, excess returns on different portfolios relative to the same "reference"' return are considered. For a reference return $\check{R}=\check{\pi}^{\top}R$ , the set of all possible excess returns are given by.  

$$
\underline{{R}}^{e}[\check{R}]=\left\{\boldsymbol{\pi}^{\top}\boldsymbol{R}-\check{R}~|~\boldsymbol{\pi}^{\top}\mathbf{1}=1\right\},
$$  

where as before $\kappa$ is the $I$ -dimensional vector of returns on the basis assets, and $\pi$ denotes a portfolio weight vector of these $I$ assets.  

It is useful to observe that the set of excess returns is the same for all reference returns. An excess return relative to a reference return $\check{R}$ is given by. $\pi^{\top}R-\check{R}=(\pi-\check{\pi})^{\top}R$ for some portfolio weight vector $\pi$ . We can obtain the same excess return relative to another reference return $\dot{R}=\dot{\pi}^{\top}R$ using the portfolio. $\pi+\dot{\pi}-\check{\pi}$ .(Check for yourself!) Hence, we can simply talk about the set of excess returns,. $R^{e}$ , without specifying any reference return, and we can write it as  

$$
\underline{{R}}^{e}=\{(\pi^{e})^{\top}{\pmb R}|(\pi^{e})^{\top}{\bf1}=0\}.
$$  

The set of excess returns is a linear subspace of the set of all random variables (in the case with $S$ possible outcomes this is equivalent to. $\mathbb{R}^{S}$ ) in the sense that  

1. if $w$ is a number and. $R^{e}$ is an excess return, then $w R^{e}$ is an excess return; Check: $R^{e}=(\pi^{e})^{\top}R$ with $(\pmb{\pi}^{e})^{\top}{\bf1}=0$ implies that. $w R^{e}=(w\pmb{\pi}^{e})^{\top}\pmb{R}$ with $(w\pmb{\pi}^{e})^{\top}\mathbf{1}=$ $w(\pmb{\pi}^{e})^{\top}\mathbf{1}=0$  

2. if $R^{e1}$ and $R^{e2}$ are two excess returns, then $R^{e1}+R^{e2}$ is also an excess return.  

Check: $R^{e i}=(\pi^{e i})^{\top}R$ with $(\pmb{\pi}^{e i})^{\top}\mathbf{1}=0$ implies that $R^{e1}+R^{e2}=(\pmb{\pi}^{e1}+\pmb{\pi}^{e2})^{\top}\pmb{R}$ , where $(\pmb{\pi}^{e1}+\pmb{\pi}^{e2})^{\top}\mathbf{1}=0$  

Define  

$$
R^{e*}=\frac{\mathrm{E}[R^{*}]}{\mathrm{E}[(R^{*})^{2}]}\left(R_{\mathrm{cm}}-R^{*}\right)=\mathrm{E}[R]^{\top}\left(\mathrm{E}[R R^{\top}]\right)^{-1}R-\frac{\mathrm{E}[R^{*}]}{\mathrm{E}[(R^{*})^{2}]}R^{*}.
$$  

Of course, $R_{\mathrm{{cm}}}-R^{*}$ is an excess return, and since $R^{e*}$ is a multiplum of that, we can conclude that $R^{e*}$ is an excess return. Here are some important properties of $R^{e*}$  

Lemma 9.3 (a) For any excess return $R^{e}$ , we have  

$$
\operatorname{E}[R^{e}R^{*}]=0.
$$  

In particular,  

$$
\operatorname{E}[R^{e*}R^{*}]=0.
$$  

(b) For any excess return $R^{e}$ we have  

$$
\operatorname{E}[R^{e}]=\operatorname{E}[R^{e*}R^{e}].
$$  

Proof: (a) For any return. $R^{i}$ , we have $\operatorname{E}[R^{*}R^{i}]=\operatorname{E}[(R^{*})^{2}]$ (cf. Lemma 4.1), and hence for any excess return $R^{e}=R^{i}-R^{j}$ , we have  

$$
\operatorname{E}[R^{*}R^{e}]=\operatorname{E}[R^{*}(R^{i}-R^{j})]=\operatorname{E}[R^{*}R^{i}]-\operatorname{E}[R^{*}R^{j}]=\operatorname{E}[(R^{*})^{2}]-\operatorname{E}[(R^{*})^{2}]=0.
$$  

In particular, this is true for the excess return $R^{e*}$  

(b) Write the excess return $R^{e}$ as the difference between the return on some portfolio $\pi$ and $R^{*}$ i.e. $R^{e}=\pi^{\top}R-R^{*}$ .Then  

$$
\operatorname{E}[R^{e*}R^{e}]=\operatorname{E}[R^{e*}\left(\pi^{\top}R-R^{*}\right)]=\pi^{\top}\operatorname{E}[R^{e*}R]-\operatorname{E}[R^{e*}R^{*}]=\pi^{\top}\operatorname{E}[R^{e*}R].
$$  

Using (9.18), we get  

$$
\operatorname{E}[R^{e*}R]=\operatorname{E}\left[\left(\operatorname{E}[R]^{\top}\left(\operatorname{E}[R R^{\top}]\right)^{-1}R\right)R\right]-{\frac{\operatorname{E}[R^{*}]}{\operatorname{E}[(R^{*})^{2}]}}\operatorname{E}[R^{*}R].
$$  

Let us first consider the last part. From Lemma 4.1, we have. $\operatorname{E}[R^{*}R_{i}]=\operatorname{E}[(R^{*})^{2}]$ for each $i$ so that $\operatorname{E}[R^{*}R]=\operatorname{E}[(R^{*})^{2}]\mathbf{1}$ . Now look at the first part of (9.23). It can be shown in general that, for any vector $_{\alpha}$ $\operatorname{E}[{\pmb{x}}^{\top}{\pmb{R}}{\pmb{R}}]=\operatorname{E}[{\pmb{R}}{\pmb{R}}^{\top}]{\pmb{x}}$ . Applying this with. ${\pmb x}=\left(\mathrm{E}[R{\pmb R}^{\top}]\right)^{-1}\mathrm{E}[{\pmb R}]$ we obtain  

$$
\operatorname{E}\left[\left(\operatorname{E}[R]^{\top}\left(\operatorname{E}[R R^{\top}]\right)^{-1}R\right)R\right]=\operatorname{E}[R R^{\top}]\left(\operatorname{E}[R R^{\top}]\right)^{-1}\operatorname{E}[R]=\operatorname{E}[R].
$$  

We can now rewrite (9.23):  

$$
\operatorname{E}[R^{e*}{\cal R}]=\operatorname{E}[{\cal R}]-\operatorname{E}[R^{*}]\mathbf{1}.
$$  

Going back to (9.22), we have  

$$
\pi^{\top}\operatorname{E}[R^{e*}R]=\pi^{\top}\left(\operatorname{E}[R]-\operatorname{E}[R^{*}]\mathbf{1}\right)=\pi^{\top}\operatorname{E}[R]-
$$  

as had to be shown.  

(c) The first part follows immediately from (b). The second part comes from  

$$
\operatorname{Var}[R^{e*}]=\operatorname{E}[(R^{e*})^{2}]-(\operatorname{E}[R^{e*}])^{2}=\operatorname{E}[R^{e*}]-(\operatorname{E}[R^{e*}])^{2}=\operatorname{E}[R^{e*}](1-\operatorname{E}[R^{e*}])
$$  

where we have used the first part.  

# A characterization of the mean-variance frontier in terms of $R^{*}$ and $R^{e*}$  

First we show that any return can be decomposed using $R^{*}$ $R^{e*}$ , and some "residual' excess return.  

Theorem 9.6 For any return $R_{i}$ , we can find a number. $w_{i}$ and an excess return. $\eta_{i}\in\underline{{R}}^{e}$ so that  

$$
R_{i}=R^{*}+w_{i}R^{e*}+\eta_{i}
$$  

and  

$$
\begin{array}{r}{\operatorname{E}[\eta_{i}]=\operatorname{E}[R^{*}\eta_{i}]=\operatorname{E}[R^{e*}\eta_{i}]=0.}\end{array}
$$  

Proof: Define $w_{i}=\left(\mathrm{E}[R_{i}]-\mathrm{E}[R^{*}]\right)/\mathrm{E}[R^{e*}]$ and $\eta_{i}=R_{i}-R^{*}-w_{i}R^{e*}$ . Then (9.24) and $\mathrm{E}[\eta_{i}]=0$ hold by construction.. $\eta_{i}$ is the difference between the two excess returns $R_{i}-R^{*}$ and $w_{i}R^{e*}$ and therefore itself an excess return. Now. $\mathrm{E}[R^{*}\eta_{i}]=0$ follows from (9.19) and from (9.21) we have $\mathrm{E}[\eta_{i}R^{e*}]=\mathrm{E}[\eta_{i}]$ , which we know is zero..  

Due to the relations. $\mathrm{E}[R^{*}R^{e*}]=\mathrm{E}[R^{*}\eta_{i}]=\mathrm{E}[R^{e*}\eta_{i}]=0$ , the decomposition is said to be orthogonal.  

Note that the same $w_{i}$ applies for all returns with the same expected value. The return variance is  

$$
\begin{array}{r l}&{\mathrm{Var}[R_{i}]=\mathrm{Var}\left[R^{*}+w_{i}R^{e*}\right]+\mathrm{Var}[\eta_{i}]+2\mathrm{Cov}\left[R^{*}+w_{i}R^{e*},\eta_{i}\right]}\ &{\qquad=\mathrm{Var}\left[R^{*}+w_{i}R^{e*}\right]+\mathrm{Var}[\eta_{i}]+2\left\{\mathrm{E}\left[\left(R^{*}+w_{i}R^{e*}\right)\eta_{i}\right]-\mathrm{E}\left[R^{*}+w_{i}R^{e*}\right]\mathrm{E}[\eta_{i}]\right\}}\ &{\qquad=\mathrm{Var}\left[R^{*}+w_{i}R^{e*}\right]+\mathrm{Var}[\eta_{i}].}\end{array}
$$  

Clearly the minimum variance for a given mean, i.e. a given $w_{i}$ is obtained for $\eta_{i}=0$ . We therefore have the following result:.  

Theorem 9.7 A return. $R_{i}$ is mean-variance efficient if and only if it can be written as  

$$
R_{i}=R^{*}+w_{i}R^{e*}
$$  

for some number $w_{i}$  

Varying $w_{i}$ from $-\infty$ to $+\infty$ $R_{i}=R^{*}+w_{i}R^{e*}$ runs through the entire mean-variance frontier in the direction of higher and higher expected returns (since $\operatorname{E}[R^{e*}]=\operatorname{E}[(R^{e*})^{2}]>0$  

Note that from (9.18) that the constant-mimicking return can be written as  

$$
R_{\mathrm{cm}}=R^{*}+\frac{\mathrm{E}\left[(R^{*})^{2}\right]}{\mathrm{E}[R^{*}]}R^{e*}
$$  

so the constant-mimicking return is mean-variance efficient.  

# Allowing for a risk-free asset  

Now let us assume that a risk-free asset with return. $R^{f}$ exists (or can be constructed as a portfolio of the basic assets). Then from Lemma 4.1 we have that $R^{f}\operatorname{E}[R^{*}]=\operatorname{E}[R^{*}R^{f}]=\operatorname{E}[(R^{*})^{2}]$ , and hence  

$$
R^{f}={\frac{\operatorname{E}[(R^{*})^{2}]}{\operatorname{E}[R^{*}]}}={\frac{1}{{\mathbf{1}}^{\top}\left({\mathrm{E}}[R R^{\top}]\right)^{-1}{\mathrm{E}}[R]}}.
$$  

In addition we have  

$$
\operatorname{E}[R]^{\top}\left(\operatorname{E}[R R^{\top}]\right)^{-1}R=1.
$$  

Let us just show this for the case with two assets, a risk-free and a risky so that $\pmb{R}=(\tilde{R},R^{f})^{\top}$ where $\tilde{R}$ is the return on the risky asset. Then  

$$
\begin{array}{r l}&{\mathrm{E}[R]^{\top}\left(\mathrm{E}[R R^{\top}]\right)^{-1}R=\left(\mathrm{E}[\tilde{R}],R^{f}\right)^{\top}\left(\mathrm{E}[\tilde{R}^{2}]\quad R^{f}\mathrm{E}[\tilde{R}]\right)^{-1}\left(\frac{\tilde{R}}{R^{f}}\right)}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\mathrm{E}[\tilde{R}],}\ &{=\frac{1}{(R^{f})^{2}\left(\mathrm{E}[\tilde{R}^{2}]-(\mathrm{E}[\tilde{R}])^{2}\right)}\left(\mathrm{E}[\tilde{R}],R^{f}\right)^{\top}\left(\underset{-R^{f}\mathrm{E}[\tilde{R}]}{(R^{f})^{2}}\quad-R^{f}\mathrm{E}[\tilde{R}]\right)\left(\frac{\tilde{R}}{R^{f}}\right)}\ &{=\frac{1}{(R^{f})^{2}\left(\mathrm{E}[\tilde{R}^{2}]-(\mathrm{E}[\tilde{R}])^{2}\right)}\left(\mathrm{E}[\tilde{R}],R^{f}\right)^{\top}\left(\underset{R^{f}}{(R^{f})^{2}}\left(\tilde{R}-\mathrm{E}[\tilde{R}]\right)\right)}\ &{=1.}\end{array}
$$  

Substituting (9.27) and (9.28) into the general definition of $R^{e*}$ in (9.18), we get  

$$
R^{e*}=1-\frac{1}{R^{f}}R^{*}.
$$  

Consequently,  

$$
R^{f}=R^{*}+R^{f}R^{e*}
$$  

so the $w_{i}$ corresponding to the risk-free return is $R^{f}$ itself. With $R^{f}>1$ , we see that $R^{*}+R^{e*}$ corresponds to a point on the frontier below the risk-free rate. (Again we use the fact that $\mathrm{E}[R^{e*}]>0$  

# The minimum-variance return  

With the decomposition in Theorem 9.7, it is easy to find the minimum-variance return. The variance of any mean-variance efficient return is  

$$
\begin{array}{r l}&{\mathrm{Var}\left[R^{*}+w R^{e*}\right]=\mathrm{E}\left[(R^{*}+w R^{e*})^{2}\right]-(\mathrm{E}\left[R^{*}+w R^{e*}\right])^{2}}\ &{\qquad=\mathrm{E}\left[(R^{*})^{2}\right]+w^{2}\mathrm{E}\left[(R^{e*})^{2}\right]+2w\mathrm{E}\left[R^{*}R^{e*}\right]}\ &{\qquad-\left(\mathrm{E}[R^{*}]\right)^{2}-w^{2}\left(\mathrm{E}[R^{e*}]\right)^{2}-2w\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]}\ &{\qquad=\mathrm{E}\left[(R^{*})^{2}\right]+w^{2}\mathrm{E}\left[R^{e*}\right]\left(1-\mathrm{E}\left[R^{e*}\right]\right)-\left(\mathrm{E}[R^{*}]\right)^{2}-2w\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}],}\end{array}
$$  

where the simplifications leading to the last expression are due to Lemma 9.3. The first-order condition with respect to $w$ implies that  

$$
w=\frac{\mathrm{E}[R^{*}]}{1-\mathrm{E}[R^{e*}]}.
$$  

The minimum-variance return is thus  

$$
R_{\operatorname*{min}}=R^{*}+\frac{\mathrm{E}[R^{*}]}{1-\mathrm{E}[R^{e*}]}R^{e*}=R^{*}+\frac{\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]}{\mathrm{Var}[R^{e*}]}R^{e*}.
$$  

When a risk-free asset exists, this simplifies to $R_{\operatorname*{min}}=R^{f}$ , because $\mathrm{E}[R^{*}]/(1-\mathrm{E}[R^{e*}])=R^{f}$ using (9.29).  

# 9.4.2 Link between mean-variance efficient returns and state-price deflators  

Theorem 9.8 Let. $R$ denote a gross return. Then there exists $a,b\in\mathbb{R}$ so that $\zeta=a+b R$ satisfies $P_{i}=\operatorname{E}[\zeta D_{i}]$ for $i=1,\ldots,I$ if and only if. $R$ is a mean-variance efficient return different from the constant-mimicking return.  

Proof: According to Theorem 9.6 we can decompose the return $R$ as  

$$
R=R^{*}+w R^{e*}+\eta
$$  

for some $w\in\mathbb R$ and some excess return $\eta$ withe $\operatorname{E}[\eta_{i}]=\operatorname{E}[R^{*}\eta_{i}]=\operatorname{E}[R^{e*}\eta_{i}]=0$ $R$ is mean-variance efficient if and only if $\eta=0$ . We need to show that, for suitable $a,b\in\mathbb{R}$  

$$
\zeta=a+b R=a+b\left(R^{*}+w R^{e*}+\eta\right)
$$  

will satisfy $P_{i}=\operatorname{E}[\zeta D_{i}]$ for all $i$ if and only if $\eta=0$ and $w\neq\mathrm{E}[(R^{*})^{2}]/\mathrm{E}[R^{*}]$  

Recall that $P_{i}=\operatorname{E}[\zeta D_{i}]$ for all $i$ implies that $\operatorname{E}[\zeta R_{i}]=1$ for all returns $R_{i}$ and $\operatorname{E}[\langle R^{e}]=0$ for all excess returns $R^{e}$ . In particular,  

$$
\begin{array}{c}{1=\operatorname{E}[\zeta R^{*}]=\operatorname{E}\left[\left(a+b\left(R^{*}+w R^{e*}+\eta\right)\right)R^{*}\right]=a\operatorname{E}[R^{*}]+b\operatorname{E}\left[\left(R^{*}\right)^{2}\right]}\ {0=\operatorname{E}[\zeta R^{e*}]=\operatorname{E}\left[\left(a+b\left(R^{*}+w R^{e*}+\eta\right)\right)R^{e*}\right]=a\operatorname{E}[R^{e*}]+b w\operatorname{E}\left[\left(R^{e*}\right)^{2}\right]=(a+b w)\operatorname{E}[R^{e*}].}\end{array}
$$  

Solving for $a$ and $b$ , we get  

$$
a=\frac{w}{w\operatorname{E}[R^{*}]-\operatorname{E}\left[(R^{*})^{2}\right]},\quad b=-\frac{1}{w\operatorname{E}[R^{*}]-\operatorname{E}\left[(R^{*})^{2}\right]}
$$  

so that  

$$
\zeta=\frac{w-(R^{*}+w R^{e*}+\eta)}{w\operatorname{E}[R^{*}]-\operatorname{E}\left[(R^{*})^{2}\right]}.
$$  

To avoid division by zero we have to assume that $w\operatorname{E}[R^{*}]\neq\operatorname{E}\left[(R^{*})^{2}\right]$ , which rules out the.   
constant-mimicking return, cf. (9.26).  

Now consider any other return $R_{i}$ and decompose to $R_{i}=R^{*}+w_{i}R^{e*}+\eta_{i}$ . Then  

$$
\begin{array}{l}{{\displaystyle{\mathrm{E}[\zeta R_{i}]=\frac{1}{w{\mathrm{E}[R^{*}]}-{\mathrm{E}[(R^{*})^{2}]}}\mathrm{E}\left[\left(w-(R^{*}+w R^{e*}+\eta)\right)\left(R^{*}+w_{i}R^{e*}+\eta_{i}\right)\right]}}}\ {{\displaystyle~=\frac{1}{w{\mathrm{E}[R^{*}]}-{\mathrm{E}[(R^{*})^{2}]}}\left(w{\mathrm{E}[R^{*}]}-{\mathrm{E}\left[(R^{*})^{2}\right]}-{\mathrm{E}[\eta\eta_{i}]}\right),}}\end{array}
$$  

where we have applied various results from earlier. We can now see that we will have $\operatorname{E}[\zeta R_{i}]=1$ for all returns $R_{i}$ if and only if $\mathrm{E}[\eta\eta_{i}]=0$ for all excess returns $\eta_{i}$ . In particular $\mathrm{E}[\eta^{2}]=0$ , which implies that $\eta=0$  

# 9.4.3 Link between mean-variance efficient returns and pricing factors  

Theorem 9.9 A return $R^{m v}$ is a pricing factor, i.e. an $\alpha\in\mathbb R$ exists so that.  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},R^{m v}]\left(\operatorname{E}[R^{m v}]-\alpha\right),\quad i=1,\dots,I,}\end{array}
$$  

if and only if. $R^{m v}$ is a mean-variance efficient return different from the minimum-variance return.  

The constant $\alpha$ must then be equal to the zero-beta return corresponding to $R^{\mathrm{mv}}$ , which is equal to the risk-free return if a risk-free asset exists.  

Proof: (If' part.) First, let us show that if $R^{\mathrm{mv}}$ is mean-variance efficient and different from the minimum-variance return, it will work as a pricing factor. This result is originally due to Roll (1977). For some $w$ , we have $R^{\mathrm{{mv}}}=R^{*}+w R^{e*}$ . Consider a general return $R_{i}$ and decompose as  

$$
R_{i}=R^{*}+w_{i}R^{e*}+\eta_{i}
$$  

as in Theorem 9.6. Then  

$$
\operatorname{E}[R_{i}]=\operatorname{E}[R^{*}]+w_{i}\operatorname{E}[R^{e*}]
$$  

and  

$$
\begin{array}{r}{\operatorname{Cov}[R_{i},R^{\mathrm{mv}}]=\operatorname{Var}[R^{*}]+w w_{i}\operatorname{Var}[R^{e*}]+(w+w_{i})\operatorname{Cov}[R^{*},R^{e*}]}\ {=\operatorname{Var}[R^{*}]+w w_{i}\operatorname{Var}[R^{e*}]-(w+w_{i})\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}\end{array}
$$  

which implies that  

$$
\operatorname{Cov}[R_{i},R^{\mathrm{\tiny{mv}}}]-\operatorname{Var}[R^{*}]+w\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]=w_{i}\left(w\operatorname{Var}[R^{e*}]-\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]\right).
$$  

If $w\ne\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]/\mathrm{Var}[R^{e*}]$ , which according to (9.31) means that $R^{\mathrm{mv}}$ is different from the minimum-variance return, then we can solve the above equation for $w_{i}$ with the solution  

Hence  

$$
w_{i}=\frac{\mathrm{Cov}[R_{i},R^{\mathrm{mv}}]-\mathrm{Var}[R^{*}]+w\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]}{w\mathrm{Var}[R^{e*}]-\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]}.
$$  

$$
{\begin{array}{r l}&{\operatorname{E}[R_{i}]=\operatorname{E}[R^{*}]+w_{i}\operatorname{E}[R^{e*}]}\ &{\qquad=\operatorname{E}[R^{*}]+{\frac{\operatorname{Cov}[R_{i},R^{\mathrm{mv}}]-\operatorname{Var}[R^{*}]+w\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}{w\operatorname{Var}[R^{e*}]-\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}}\operatorname{E}[R^{e*}]}\ &{\qquad=\alpha+{\frac{\operatorname{Cov}[R_{i},R^{\mathrm{mv}}]}{w\operatorname{Var}[R^{e*}]-\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}}\operatorname{E}[R^{e*}]}\end{array}}
$$  

where we have defined the constant $\alpha$ as  

$$
\alpha=\mathrm{E}[R^{*}]+\frac{w\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]-\mathrm{Var}[R^{*}]}{w\mathrm{Var}[R^{e*}]-\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]}\mathrm{E}[R^{e*}].
$$  

This applies to any return $R_{i}$ and in particular to. $R^{\mathrm{mv}}$ itself, which implies that  

and hence  

$$
\operatorname{E}[R^{\mathrm{mv}}]=\alpha+{\frac{\operatorname{Var}[R^{\mathrm{mv}}]}{w\operatorname{Var}[R^{e*}]-\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}}\operatorname{E}[R^{e}]
$$  

$$
\frac{\operatorname{E}[R^{e*}]}{w\operatorname{Var}[R^{e*}]-\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]}=\frac{\operatorname{E}[R^{\mathrm{mv}}]-\alpha}{\operatorname{Var}[R^{\mathrm{mv}}]}.
$$  

Substituting this back in, we get  

$$
\operatorname{E}[R_{i}]=\alpha+{\frac{\operatorname{Cov}[R_{i},R^{\mathrm{{mv}}}]}{\operatorname{Var}[R^{\mathrm{{mv}}}]}}\left(\operatorname{E}[R^{\mathrm{{mv}}}]-\alpha\right)=\alpha+\beta[R_{i},R^{\mathrm{{mv}}}]\left(\operatorname{E}[R^{\mathrm{{mv}}}]-\alpha\right),
$$  

which verifies that. $R^{\mathrm{mv}}$ is a valid pricing factor.  

("Only if' part.) Next, let us show that if a return works as a pricing factor, it must be meanvariance efficient and different from the minimum-variance return. This proof is due to Hansen and Richard (1987). Assume that $R^{\mathrm{mv}}$ is a pricing factor. Decomposing as in Theorem 9.6  

$$
R^{\mathrm{mv}}=R^{*}+w R^{e*}+\eta,
$$  

we need to show that. $\eta=0$ (so $R^{\mathrm{mv}}$ is mean-variance efficient) and that $w\neq\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]/\mathrm{Var}[R^{e*}]$ (so $R^{\mathrm{mv}}$ is different from the minimum-variance return).  

Define a new return $R$ as the "efficient part" of $R^{\mathrm{mv}}$ , i.e.  

$$
R=R^{*}+w R^{e*}.
$$  

Since  

$$
\operatorname{Cov}[\eta,R^{\mathrm{mv}}]=\operatorname{E}[\eta R^{\mathrm{mv}}]-\operatorname{E}[\eta]\operatorname{E}[R^{\mathrm{mv}}]=\operatorname{E}[\eta R^{\mathrm{mv}}]=\operatorname{E}[\eta^{2}],
$$  

we get  

$$
\mathrm{Cov}[R,R^{\mathrm{mv}}]=\mathrm{Cov}[R^{\mathrm{mv}}-\eta,R^{\mathrm{mv}}]=\mathrm{Cov}[R^{\mathrm{mv}},R^{\mathrm{mv}}]-\mathrm{Cov}[\eta,R^{\mathrm{mv}}]=\mathrm{Var}[R^{\mathrm{mv}}]-\mathrm{E}[\eta^{2}].
$$  

On the other hand, $\operatorname{E}[R]=\operatorname{E}[R^{\mathrm{mv}}]$ so applying (9.32) for $R_{i}=R^{\mathrm{mv}}$ , we obtain  

$$
\operatorname{E}[R^{\mathrm{mv}}]-\alpha={\frac{\operatorname{Cov}[R,R^{\mathrm{mv}}]}{\operatorname{Var}[R^{\mathrm{mv}}]}}\left(\operatorname{E}[R^{\mathrm{mv}}]-\alpha\right)
$$  

and hence. $\operatorname{Cov}[R,R^{\mathrm{mv}}]=\operatorname{Var}[R^{\mathrm{mv}}]$ . We conclude that $\mathrm{E}[\eta^{2}]=0$ , which implies. $\eta=0$  

Suppose that $w=\operatorname{E}[R^{*}]\operatorname{E}[R^{e*}]/\operatorname{Var}[R^{e*}]$ and define a new gross return  

$$
R=R^{\mathrm{{mv}}}+\frac{1}{\mathrm{E}[R^{e*}]}R^{e*}.
$$  

Clearly, $\operatorname{E}[R]=\operatorname{E}[R^{\mathrm{mv}}]+1$ , and furthermore  

$$
\operatorname{Cov}[R,R^{\mathrm{mv}}]=\operatorname{Var}[R^{\mathrm{mv}}]+{\frac{1}{\operatorname{E}[R^{e*}]}}\operatorname{Cov}[R^{e*},R^{\mathrm{mv}}]=\operatorname{Var}[R^{\mathrm{mv}}]
$$  

since  

$$
\begin{array}{r l}&{\mathrm{Cov}[R^{e*},R^{\mathrm{mv}}]=\mathrm{Cov}[R^{e*},R^{*}+w R^{e*}]=\mathrm{Cov}[R^{e*},R^{*}]+w\mathrm{Var}[R^{e*}]}\ &{\qquad=\mathrm{Cov}[R^{e*},R^{*}]+\mathrm{E}[R^{*}]\mathrm{E}[R^{e*}]=\mathrm{E}[R^{e*}R^{*}]=0.}\end{array}
$$  

Applying (9.32) to the return $R$ , we get  

$$
\operatorname{E}[R]=\alpha+{\frac{\operatorname{Cov}[R,R^{\mathrm{{mv}}}]}{\operatorname{Var}[R^{\mathrm{{mv}}}]}}\left(\operatorname{E}[R^{\mathrm{{mv}}}]-\alpha\right)=\alpha+\left(\operatorname{E}[R^{\mathrm{{mv}}}]-\alpha\right)=\operatorname{E}[R^{\mathrm{{mv}}}],
$$  

which contradicts our early conclusion that $\operatorname{E}[R]=\operatorname{E}[R^{\mathrm{mv}}]+1$ . Hence our assumption about. $w$   
cannot hold.  

One implication of this theorem is that we can always find some returns that work as a pricing factor, namely the mean-variance efficient returns. Another implication is that the conclusion of the classical CAPM can be restated as "the market portfolio is mean-variance efficient."  
