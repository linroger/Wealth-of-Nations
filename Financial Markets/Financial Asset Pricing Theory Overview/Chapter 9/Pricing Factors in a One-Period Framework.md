---
tags:
  - factor_beta
  - one_period_framework
  - pricing_factors
  - risk_premium
  - zero_beta_return
aliases:
  - Factor Model
  - Pricing Factor
key_concepts:
  - Factor beta calculation
  - Gross return equation
  - Pricing factor definition
  - Pricing factor theorem
  - Zero-beta return
---

# 9.3 Pricing factors in a one-period framework  

In Section 4.6.2 we defined a one-dimensional pricing factor in a one-period framework and dis-. cussed the relation between pricing factors and state-price deflators. Below we generalize this to the case of multi-dimensional factors and give a more rigorous treatment..  

# 9.3.1 Definition and basic properties  

We will say that a $K$ -dimensional random variable $\pmb{x}=(x_{1},\dots,x_{K})^{\top}$ is a pricing factor for the market if there exists some $\alpha\in\mathbb R$ and some $\eta\in\mathbb{R}^{K}$ so that  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},\pmb{x}]^{\top}\pmb{\eta},\quad i=1,\ldots,I,}\end{array}
$$  

where the factor-beta of asset $i$ is thee $K$ -dimensional vector $\beta[R_{i},\pmb{x}]$ given by  

$$
\beta[R_{i},{\pmb x}]=\left(\mathrm{Var}[{\pmb x}]\right)^{-1}\mathrm{Cov}[{\pmb x},R_{i}].
$$  

Here $\mathrm{Var}[{\boldsymbol{x}}]$ is the $K\times K$ variance-covariance matrix of $_{\mathbf{\nabla}}\mathbf{\phi}_{\mathbf{\phi}}$ and $\mathrm{Cov}[\pmb{x},\pmb{R}_{i}]$ is the $K$ -vector with elements $\mathrm{Cov}[x_{k},R_{i}]$ . Saying that $_{\mathbf{\nabla}}\mathbf{\phi}_{\mathbf{\phi}}$ is a pricing factor we implicitly require that $\mathrm{Var}[{\pmb x}]$ is nonsingular. The vector. $\pmb{\eta}$ is called a factor risk premium and $\alpha$ is called the zero-beta return..  

We can write (9.4) more compactly as  

$$
\operatorname{E}[R]=\alpha\mathbf{1}+\underline{{\underline{{\beta}}}}[R,x]\eta,
$$  

where $\pmb{R}=\left(R_{1},\ldots,R_{I}\right)^{\top}$ is the return vector, $\mathbf{1}=\left(1,\ldots,1\right)^{\top}$ , and $\underline{{\underline{{\beta}}}}[R,x]$ is the $I\times K$ matrix with $\beta[R_{i},\pmb{x}]$ as the $i$ 'th row. Due to the linearity of expectations and covariance, (9.4) will also hold for all portfolios of the. $I$ assets. Note that if a risk-free asset is traded in the market, it will. have a zero factor-beta and, consequently,. $\alpha=R^{f}$  

The equation (9.4) involves the gross return $R_{i}$ on asset $i$ .What about the rate of return $r_{i}=R_{i}-1;$ Clearly, $\operatorname{E}[R_{i}]=1+\operatorname{E}[r_{i}]$ , and the properties of covariance give  

$$
\operatorname{Cov}[{\pmb x},R_{i}]=\operatorname{Cov}[{\pmb x},1+r_{i}]=\operatorname{Cov}[{\pmb x},r_{i}]\quad\Rightarrow\quad\beta[R_{i},{\pmb x}]=\beta[r_{i},{\pmb x}].
$$  

Consequently, (9.4) implies that  

$$
\operatorname{E}[r_{i}]=(\alpha-1)+\beta[r_{i},\pmb{x}]^{\top}\eta.
$$  

If a risk-free asset exists,. $\alpha-1=R^{f}-1=r^{f}$ , the risk-free net rate of return.  

The relation (9.4) does not directly involve prices. But since the expected gross return is $\operatorname{E}[R_{i}]=$ $\operatorname{E}[D_{i}]/P_{i}$ , we have $P_{i}=\mathrm{E}[D_{i}]/\mathrm{E}[R_{i}]$ and hence the equivalent relation  

$$
P_{i}=\frac{\operatorname{E}[D_{i}]}{\alpha+\beta[R_{i},x]^{\top}\eta}.
$$  

The price is equal to the expected dividend discounted by a risk-adjusted rate. You may find this relation unsatisfactory since the price implicitly enters the right-hand side through the "returnbeta" $\beta[R_{i},\pmb{x}]$ . However, we can define a "dividend-beta' by  

$$
\beta[D_{i},{\pmb x}]=(\mathrm{Var}[{\pmb x}])^{-1}\mathrm{Cov}[{\pmb x},D_{i}]
$$  

and inserting $\begin{array}{r}{D_{i}=R_{i}P_{i}}\end{array}$ we see that $\beta[D_{i},{\pmb x}]=P_{i}\beta[R_{i},{\pmb x}]$ . Equation (9.4) now implies that  

$$
\frac{\operatorname{E}[D_{i}]}{P_{i}}=\alpha+\frac{1}{P_{i}}\beta[D_{i},{\pmb x}]^{\top}{\pmb\eta}
$$  

so that  

$$
P_{i}=\frac{\operatorname{E}[D_{i}]-\beta[D_{i},\pmb{x}]^{\top}\pmb{\eta}}{\alpha}.
$$  

Think of the numerator as a certainty equivalent of the risky dividend. The current price is the.   
certainty equivalent discounted by the zero-beta return, which is the risk-free return if this exists. The following result shows that pricing factors are not unique.  

Theorem 9.1 If the $K$ -dimensional random variable $_{x c}$ is a pricing factor, then any $\hat{\pmb x}$ of the form ${\hat{\pmb x}}={\pmb a}+\underline{{\underline{{A}}}}{\pmb x}$ where $\pmb{a}\in\mathbb{R}^{K}$ and $\underline{{\underline{{A}}}}$ is a non-singular $K\times K$ matrix is also a pricing factor.  

Proof: According to (A.1), (A.2), and (1.2), we have  

$$
\begin{array}{r}{\operatorname{Cov}[{\hat{\boldsymbol{x}}},R_{i}]=\operatorname{Cov}[{\boldsymbol{a}}+\underline{{\boldsymbol{A}}}\boldsymbol{x},R_{i}]=\underline{{\boldsymbol{A}}}\operatorname{Cov}[\boldsymbol{x},R_{i}],}\ {\big(\operatorname{Var}[{\hat{\boldsymbol{x}}}]\big)^{-1}=\big(\operatorname{Var}[{\boldsymbol{a}}+\underline{{\boldsymbol{A}}}\boldsymbol{x}]\big)^{-1}=\big(\operatorname{Var}[\underline{{\boldsymbol{A}}}\boldsymbol{x}]\big)^{-1}=\big(\underline{{\boldsymbol{A}}}\operatorname{Var}[\boldsymbol{x}]\underline{{\boldsymbol{A}}}^{\top}\big)^{-1}=\big(\underline{{\boldsymbol{A}}}^{\top}\big)^{-1}\big(\operatorname{Var}[\boldsymbol{x}]\big)^{-1}\underline{{\boldsymbol{A}}}^{-1},}\end{array}
$$  

and thus  

$$
\beta[R_{i},{\hat{x}}]={\big(}\operatorname{Var}[{\hat{x}}]{\big)}^{-1}\operatorname{Cov}[{\hat{x}},R_{i}]={\big(}{\underline{{\underline{{A}}}}}^{\tau}{\big)}^{-1}{\big(}\operatorname{Var}[{\pmb{x}}]{\big)}^{-1}{\underline{{\underline{{A}}}}}^{-1}{\underline{{\underline{{A}}}}}\operatorname{Cov}[{\pmb{x}},R_{i}]={\big(}{\underline{{\underline{{A}}}}}^{\tau}{\big)}^{-1}\beta[R_{i},{\pmb{x}}].
$$  

If we define $\hat{\eta}=\underline{{\underline{{A}}}}\eta$ , we obtain  

$$
\beta[R_{i},\hat{\pmb{x}}]^{\top}\hat{\pmb{\eta}}=\left(\left(\underline{{\underline{{A}}}}^{\top}\right)^{-1}\beta[R_{i},\pmb{x}]\right)^{\top}\underline{{\underline{{A}}}}\pmb{\eta}=\beta[R_{i},\pmb{x}]^{\top}\pmb{\eta}
$$  

and, hence,  

$$
\begin{array}{r}{\mathrm{E}[R_{i}]=\alpha+\beta[R_{i},\hat{\pmb x}]^{\top}\hat{\pmb\eta},\quad i=1,\dots,I,}\end{array}
$$  

which confirms that $\hat{\pmb x}$ is a pricing factor.  

Let us look at some important consequences of this theorem.  

In general the $k$ 'th element of the factor beta $\beta[R_{i},\pmb{x}]$ is not equal to $\mathrm{Cov}[x_{k},R_{i}]/\mathrm{Var}[x_{k}]$ This will be the case, however, if the elements in the pricing factor are mutually uncorrelated, i.e. $\mathrm{Cov}[x_{j},x_{k}]=0$ for $j\neq k$ . In fact, we can orthogonalize the pricing factor so that this will be satisfied. Given any pricing factor $_{x}$ , we can find a non-singular $K\times K$ matrix $\underline{{\underline{{V}}}}$ so that $\underline{{\underline{{V}}}}\underline{{\underline{{V}}}}^{\top}=\operatorname{Var}[{\pmb x}]$ . Defining ${\hat{x}}=\underline{{\underline{{V}}}}^{-1}x$ , we know from above that $\hat{\pmb x}$ is also a pricing factor and the variance-covariance matrix is  

$$
\operatorname{Var}[{\hat{\pmb x}}]={\underline{{\underline{{V}}}}}^{-1}\operatorname{Var}[{\pmb x}]\left({\underline{{\underline{{V}}}}}^{-1}\right)^{\top}={\underline{{\underline{{V}}}}}^{-1}{\underline{{\underline{{V}}}}}{\underline{{\underline{{V}}}}}^{\top}\left({\underline{{V}}}^{\top}\right)^{-1}={\underline{{\underline{{I}}}}},
$$  

i.e. the $K\times K$ identity matrix. It is therefore no restriction to look only for uncorrelated pricing factors.  

We can also obtain a pricing factor with mean zero. If. $_{\mathbf{\nabla}}\mathbf{\phi}_{\mathbf{\phi}}$ is any pricing factor, just define. ${\hat{\pmb x}}={\pmb x}-\mathrm{E}[{\pmb x}]$ .Clearly, $\hat{\pmb x}$ has mean zero and, due to the previous theorem, it is also a pricing. factor. It is therefore no restriction to look only for zero-mean pricing factors.  

Finally, note that we can replace the constant vector $\pmb{a}$ in the above theorem with a $K$ dimensional random variable $\varepsilon$ with the property that $\mathrm{Cov}[R_{i},\varepsilon]=\mathbf{0}$ for all $i$ . In particular we have that if $_{x c}$ is a pricing factor and $\varepsilon$ is such a random variable, then $x+\varepsilon$ is also a pricing factor.  

# 9.3.2 Returns as pricing factors  

Suppose now that the pricing factor is a vector of returns on portfolios of the $I$ assets. Then (9.4) holds with each. $x_{k}$ replacing $R_{i}$ . We have $\operatorname{Cov}[{\pmb x},{\pmb x}]=\operatorname{Var}[{\pmb x}]$ and hence ${\underline{{\underline{{\beta}}}}}[{\pmb x},{\pmb x}]=\underline{{\underline{{I}}}}$ , the $K\times K$ identity matrix. Consequently,  

$$
\begin{array}{r}{\operatorname{E}[{\boldsymbol{x}}]=\alpha\mathbf{1}+\eta\quad\Rightarrow\quad\eta=\operatorname{E}[{\boldsymbol{x}}]-\alpha\mathbf{1},}\end{array}
$$  

where $\mathbf{1}$ is a $K$ -dimensional vector of ones. In this case we can therefore rewrite (9.4) as  

$$
\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},\pmb{x}]^{\top}\left(\operatorname{E}[\pmb{x}]-\alpha\mathbf{1}\right),\quad i=1,\ldots,I.
$$  

It is now clear that the classical CAPM has the return on the market portfolio as the single pricing factor. More generally, we will demonstrate in Section 9.4.3 that a return works as a single pricing factor if and only if it is the return on a mean-variance efficient portfolio (different from the minimum-variance portfolio).  

For the case of a one-dimensional pricing factor. $x$ , Section 4.6.2 explained that the return. $R^{x}$ on the factor-mimicking portfolio also works as a pricing factor. We can generalize this to a multi-dimensional pricing factor in the following way. Given a pricing factor $\pmb{x}=\left(x_{1},\dots,x_{K}\right)^{\top}$ orthogonalize to obtain. $\hat{\pmb x}=(\hat{x}_{1},\dots,\hat{x}_{K})^{\top}$ . For each $\hat{x}_{k}$ construct a factor-mimicking portfolio with corresponding return $R^{\ddot{x}_{k}}$ . Then the return vector $\pmb{R}^{\hat{x}}=\left(R^{\hat{x}_{1}},\ldots,R^{\hat{x}_{K}}\right)^{\top}$ will work as a pricing factor and we have an equation like.  

$$
\mathrm{E}[R_{i}]=\alpha+\beta[R_{i},R^{\hat{x}}]\cdot\left(\mathrm{E}[R^{\hat{x}}]-\alpha\mathbf{1}\right),\quad i=1,\ldots,I.
$$  

It is therefore no restriction to assume that pricing factors are returns.  

# 9.3.3 From a state-price deflator to a pricing factor  

From the definition of a covariance we have that $\operatorname{Cov}[R_{i},\zeta]=\operatorname{E}[R_{i}\zeta]-\operatorname{E}[\zeta]\operatorname{E}[R_{i}]$ . From (4.3), we now get that.  

$$
\operatorname{E}[R_{i}]={\frac{1}{\operatorname{E}[\zeta]}}-{\frac{\operatorname{Cov}[R_{i},\zeta]}{\operatorname{E}[\zeta]}}.
$$  

With $\beta[R_{i},\zeta]=\mathrm{Cov}[R_{i},\zeta]/\mathrm{Var}[\zeta]$ and $\eta=-\operatorname{Var}[\zeta]/\operatorname{E}[\zeta]$ , we can rewrite the above equation as  

$$
\mathrm{E}[R_{i}]=\frac{1}{\mathrm{E}[\zeta]}+\beta[R_{i},\zeta]\eta,
$$  

which shows that the state-price deflator is a pricing factor. Although the proof is simple, the results is important enough to deserve its own theorem:  

Theorem 9.2 Any state-price deflator $\zeta$ is a pricing factor..  

In the above argument we did not use positivity of the state-price deflator, only the pricing equation (4.1) or, rather, the return version (4.3). Any random variable. $x$ that satisfies $P_{i}=\operatorname{E}[x D_{i}]$ for all assets works as a pricing factor. In particular, this is true for the random variable $\zeta^{*}$ defined in (4.46) whether it is positive or not. We therefore have that.  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha^{*}+\beta[R_{i},\zeta^{*}]\eta^{*},\quad i=1,\dots,I,}\end{array}
$$  

where $\alpha^{*}=1/\operatorname{E}[\zeta^{*}]$ and $\eta^{*}=-\operatorname{Var}[\zeta^{*}]/\operatorname{E}[\zeta^{*}]$ . Alternatively, we can scale by the price of $\zeta^{*}$ and use the return $R^{*}$ defined in (4.54) as the factor so that  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha^{*}+\beta[R_{i},R^{*}]\eta^{*},\quad i=1,\dots,I,}\end{array}
$$  

where $\alpha^{*}=1/\operatorname{E}[\zeta^{*}]$ as before but now $\eta^{*}=-\operatorname{Var}[\zeta^{*}]/\left(\operatorname{E}[\zeta^{*}]\operatorname{E}[(\zeta^{*})^{2}]\right)$  

More generally, we have the following result:  

Theorem 9.3 If the $K$ -dimensional random variable $_{x}$ satisfies  

(i) $\mathrm{Var}[{\boldsymbol{x}}]$ is non-singular;  

(ii) $a\in\mathbb R$ and $\pmb{b}\in\mathbb{R}^{K}$ exist so that $\zeta=a+b^{\top}x$ has the properties $\mathrm{E}[\zeta]\neq0$ and $P_{i}=\operatorname{E}[\zeta D_{i}]$ for $i=1,\dots,I$  

then $_{x c}$ is a pricing factor.  

Proof: Substituting $\zeta=a+b^{\top}x$ into (9.12), we get  

$$
{\begin{array}{r l}&{\operatorname{E}[R_{i}]={\frac{1}{a+b^{\top}\operatorname{E}[x]}}-{\frac{b^{\top}\operatorname{Cov}[R_{i},x]}{a+b^{\top}\operatorname{E}[x]}}}\ &{\qquad={\frac{1}{a+b^{\top}\operatorname{E}[x]}}-{\frac{\left(\operatorname{Var}[x]b\right)^{\top}\left(\operatorname{Var}[x]\right)^{-1}\operatorname{Cov}[R_{i},x]}{a+b^{\top}\operatorname{E}[x]}}}\ &{\qquad=\alpha+\beta[R_{i},x]^{\top}\eta,}\end{array}}
$$  

where $\alpha=1/\left(a+b^{\top}\operatorname{E}[\pmb{x}]\right)$ and $\eta=-\alpha\operatorname{Var}[x]b$  

Whenever we have a state-price deflator of the form $\zeta=a+b^{\top}x$ , we can use $_{\alpha}$ as a pricing factor.  

# 9.3.4 From a pricing factor to a (candidate) state-price deflator  

Conversely:  

Theorem 9.4 Assume the. $K$ -dimensional random variable $_{x}$ is a pricing factor with an associated zero-beta return $\alpha$ different from zero. Then we can find $a\in\mathbb R$ and $\pmb{b}\in\mathbb{R}^{K}$ so that $\zeta=a+b^{\top}x$ satisfies $P_{i}=\operatorname{E}[\zeta D_{i}]$ for $i=1,\dots,I$  

Proof: Let $\pmb{\eta}$ denote the factor risk premium associated with the pricing factor $_{\mathbf{\nabla}}\mathbf{\phi}_{\mathbf{\phi}}$ . Define  

$$
\pmb{b}=-\frac{1}{\alpha}\left(\mathrm{Var}[\pmb{x}]\right)^{-1}\pmb{\eta},\quad\pmb{a}=\frac{1}{\alpha}-\pmb{b}^{\top}\mathrm{E}[\pmb{x}].
$$  

Then $\zeta=a+b^{\top}x$ works since  

$$
{\begin{array}{r l}&{\operatorname{E}[\zeta R i]=a\operatorname{E}[R_{i}]+b^{\top}\operatorname{E}[R_{i}x]}\ &{\qquad=a\operatorname{E}[R_{i}]+b^{\top}\left(\operatorname{Cov}[R_{i},x]+\operatorname{E}[R_{i}]\operatorname{E}[x]\right)}\ &{\qquad=\left(a+b^{\top}\operatorname{E}[x]\right)\operatorname{E}[R_{i}]+\operatorname{Cov}[R_{i},x]^{\top}b}\ &{\qquad={\cfrac{1}{\alpha}}\left(\operatorname{E}[R_{i}]-\operatorname{Cov}[R_{i},x]^{\top}\left(\operatorname{Var}[x]\right)^{-1}\eta\right)}\ &{\qquad={\cfrac{1}{\alpha}}\left(\operatorname{E}[R_{i}]-\beta[R_{i},x]^{\top}\eta\right)}\ &{\qquad=1}\end{array}}
$$  

for any $i=1,\dots,I$  

Inserting $a$ and $^{b}$ from the proof, we get  

$$
\zeta=a+b^{\top}{\pmb x}=\frac{1}{\alpha}\left(1-{\pmb\eta}^{\top}\left(\mathrm{Var}[{\pmb x}]\right)^{-1}\left({\pmb x}-\mathrm{E}[{\pmb x}]\right)\right).
$$  

Any pricing factor $_{x}$ gives us a candidate $\boldsymbol{a}+\boldsymbol{b}^{\intercal}\boldsymbol{x}$ for a state-price deflator but it will only be a. true state-price deflator if it is strictly positive. The fact that we can find a pricing factor for a given market does not imply that the market is arbitrage-free..  

# 9.3.5 The Arbitrage Pricing Theory  

Ross (1976) introduced the Arbitrage Pricing Theory as an alternative to the classical CAPM. The basic assumption is that a. $K$ -dimensional random variable $\pmb{x}=(x_{1},\dots,x_{K})^{\top}$ exists so that the return on any asset $i=1,\dots,I$ can be decomposed as  

$$
R_{i}=\operatorname{E}[R_{i}]+\beta[R_{i},{\boldsymbol{x}}]{\boldsymbol{x}}+\varepsilon_{i}=\operatorname{E}[R_{i}]+\sum_{k=1}^{K}\beta_{i k}x_{k}+\varepsilon_{i},
$$  

where $\mathrm{E}[x_{k}]=0$ $\mathrm{E}[\varepsilon_{i}]=0$ $\mathrm{Cov}[\varepsilon_{i},x_{k}]=0$ , and $\mathrm{Cov}[\varepsilon_{i},\varepsilon_{j}]=0$ for all $i$ $j\neq i$ , and $k$ .Due to the constraints on means and covariances, we have $\beta[R_{i},{\pmb x}]=(\mathrm{Var}[{\pmb x}])^{-1}\mathrm{Cov}[R_{i},{\pmb x}]$ as before. Note that one can always make a decomposition as in the equation above. Just think of regressing returns on the vector $_{x c}$ . The real content of the assumption lies in the restriction that the residuals are uncorrelated, i.e. $\mathrm{Cov}[\varepsilon_{i},\varepsilon_{j}]=0$ whenever $i\neq j$ . The vector $_{\alpha}$ is the source of all the common variations in returns across assets.  

Suppose you have invested a given wealth in a portfolio. We can represent a zero net investment deviation from this portfolio by a vector $\pmb{w}=(w_{1},\dots,w_{I})^{\top}$ satisfying ${\pmb w}\cdot{\bf1}=0$ , where $w_{i}$ is the fraction of wealth additionally invested in asset $i$ . In other words, we increase the investment in some assets and decrease the investment in other assets. The additional portfolio return is  

$$
R^{w}=w^{\top}R=\sum_{i=1}^{I}w_{i}R_{i}=\sum_{i=1}^{I}w_{i}\operatorname{E}[R_{i}]+\sum_{i=1}^{I}w_{i}\beta_{i1}x_{1}+\dots+\sum_{i=1}^{I}w_{i}\beta_{i K}x_{K}+\sum_{i=1}^{I}w_{i}\varepsilon_{i}.
$$  

Suppose we can find $w_{1},\dots,w_{I}$ so that  

(i) i=1 wiik = 0 for k =1,...,K, (ii) $\begin{array}{r}{\sum_{i=1}^{I}w_{i}\varepsilon_{i}=0,}\end{array}$  

then  

$$
R^{w}=\sum_{i=1}^{I}w_{i}\mathrm{E}[R_{i}],
$$  

i.e. the added return is risk-free. To rule out arbitrage, a risk-free zero net investment should give a zero return so we can conclude that  

$$
R^{w}=\sum_{i=1}^{I}w_{i}\operatorname{E}[R_{i}]=0.
$$  

In linear algebra terms, we have thus seen that if a vector $\mathbf{\nabla}w$ is orthogonal to. $\mathbf{1}$ and to each of the. vectors $(\beta_{1k},\ldots,\beta_{I k})^{\top}$ $k=1,\ldots,K$ , then it must also be orthogonal to the vector of expected. returns $\operatorname{E}[R]$ . It follows that. $\operatorname{E}[R]$ must be spanned by the vectors $\mathbf{1}$ $(\beta_{1k},\ldots,\beta_{I k})^{\top}$ $k=1,\ldots,K$ i.e. that constants. $\alpha,\eta_{1},\dots,\eta_{K}$ exist so that  

$$
\mathrm{E}[R_{i}]=\alpha+\beta_{i1}\eta_{1}+\cdot\cdot\cdot+\beta_{i K}\eta_{K}=\alpha+\beta[R_{i},x]\eta,\quad i=1,2,\ldots,I,
$$  

i.e. $_{x c}$ is a pricing factor.  

With at least $K$ sufficiently different assets, we can satisfy condition (i) above. We just need the $I\times K$ matrix ${\underline{{\underline{{\beta}}}}}[{\pmb{R}},{\pmb{x}}]$ to have rank $K$ . What about condition (ii)? The usual argument given. is that if we pick $w_{i}$ to be of the order $1/I$ and $I$ is a very large number, then $\textstyle\sum_{i=1}w_{i}\varepsilon_{i}$ will be close to zero and we can ignore it. But close to zero does not mean equal to zero and if the residual portfolio return is non-zero, the portfolio is not risk-free and the argument breaks down. Even a very small dividend or return in a particular state can have a large influence on the current price and, hence, the expected return. With finitely many assets, we can only safely ignore the. residual portfolio return if the residual returns of all the individual assets are zero, i.e.. $\varepsilon_{i}=0$ for all $i=1,\dots,I$  

Theorem 9.5 If individual asset returns are of the form  

$$
R_{i}=\operatorname{E}[R_{i}]+\beta[R_{i},\pmb{x}]\pmb{x},\quad i=1,2,\dots,I,
$$  

and the $I\times K$ matrix ${\underline{{\underline{{\beta}}}}}[R,x]$ has rank. $K$ , then $_{x}$ is a pricing factor, i.e. $\alpha\in\mathbb R$ and $\eta\in\mathbb{R}^{K}$ exist so that  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},\pmb{x}]^{\top}\pmb{\eta},\quad i=1,2,\dots,I.}\end{array}
$$  

It is, however, fairly restrictive to assume that all the variation in the returns on a large number of assets can be captured by a low number of factors.  
