---
tags:
  - pricing_equation
  - radon_nikodym
  - risk_free_return
  - risk_neutral_probability
  - state_price_deflator
aliases:
  - Alternative Representations
  - Risk-Neutral Valuation
key_concepts:
  - Asset price
  - Radon-Nikodym derivative
  - Risk-free return
  - Risk-neutral probability measure
  - State-price deflator
---

# 4.6 A preview of alternative formulations  

The previous sections show that a state-price deflator is a good way to represent the marketwide pricing mechanism in a financial market. Paired with characteristics of any individual asset, the state-price defator leads to the price of the asset. This section shows that we can capture the same information in other ways. The alternative representations can be preferable for some specific purposes and we will return to them in later chapters. Here we will only give a preview. For simplicity we keep the discussion in a one-period framework.  

# 4.6.1 Risk-neutral probabilities  

Suppose that a risk-free dividend can be constructed and that it provides a gross return of $R^{f}$ A probability measure $\mathbb{Q}$ is called a risk-neutral probability measure if the following conditions are. satisfied:  

(i) $\mathbb{P}$ and $\mathbb{Q}$ are equivalent, i.e. attach zero probability to the same events; (ii) the random variable. $d\mathbb{Q}/d\mathbb{P}$ (explained below) has finite variance; (iii) the price of any asset $i=1,\dots,I$ is given by  

$$
\begin{array}{r}{{P}_{i}=\mathrm{E}^{\mathbb{Q}}\left[(R^{f})^{-1}D_{i}\right]=(R^{f})^{-1}\mathrm{E}^{\mathbb{Q}}\left[D_{i}\right],}\end{array}
$$  

i.e. the price of any asset equals the expected discounted dividend using the risk-free interest rate as the discount rate and the risk-neutral probabilities when computing the expectation.  

The risk-free return is not random and can therefore be moved in and out of expectations as in the above equation. Given the return (or, equivalently, the price) of the risk-free asset, all the market-wide pricing information is captured by a risk-neutral probability measure.  

In the case of a finite state space $\Omega=\{1,2,\dots,S\}$ , a probability measure $\mathbb{Q}$ is fully characterized by the state probabilities $q_{\omega}=\mathbb{Q}(\omega)$ . Since we have assumed that the real-world probability measure $\mathbb{P}$ is such that. $p_{\omega}>0$ for all $\omega$ , equivalence between $\mathbb{P}$ and $\mathbb{Q}$ demands that $q_{\omega}>0$ for all $\omega$ . With finite $\Omega$ the pricing equation in(ii) can be written as $\begin{array}{r}{P_{i}=R_{f}^{-1}\sum_{\omega=1}^{S}q_{\omega}D_{i\omega}}\end{array}$  

Why is $\mathbb{Q}$ called a risk-neutral probability measure? Since the gross return on asset $i$ is $R_{i}=$ $D_{i}/P_{i}$ , we can rewrite (4.71) as  

$$
\begin{array}{r}{\mathrm{E}^{Q}[R_{i}]=R^{f},}\end{array}
$$  

i.e. all assets have an expected return equal to the risk-free return under the risk-neutral probability. measure. If all investors were risk-neutral, they would rank assets according to their expected. returns only and the market could only be in equilibrium if all assets had the same expected returns. The definition of a risk-neutral probability measure. $\mathbb{Q}$ thus implies that asset prices in the real-world are just as they would have been in an economy in which all individuals are risk-neutral and the state probabilities are given by. $\mathbb{Q}$ . The price adjustments for risk are thus incorporated. in the risk-neutral probabilities..  

Next, let us explore the link between risk-neutral probability measures and state prices. First, assume a finite state space. Given a state-price vector $\psi$ and the associated state-price deflator $\zeta$ we can define  

$$
q_{\omega}=\frac{\psi_{\omega}}{\sum_{s=1}^{S}\psi_{s}}=R^{f}\psi_{\omega}=R^{f}p_{\omega}\zeta_{\omega},\quad\omega=1,\ldots,S.
$$  

All the $q_{\omega}$ 's are strictly positive and sum to one so they define an equivalent probability measure. Furthermore, (4.18) implies that  

$$
P_{i}=\psi\cdot D_{i}=\sum_{\omega=1}^{S}\psi_{\omega}D_{i\omega}=\sum_{\omega=1}^{S}(R^{f})^{-1}q_{\omega}D_{i\omega}=\mathrm{E}^{\mathbb{Q}}\left[(R^{f})^{-1}D_{i}\right],
$$  

$\mathbb{Q}$ is indeed a risk-neutral probability measure. Note that $q_{\omega}>p_{\omega}$ if and only if $\zeta_{\omega}>(R^{f})^{-1}=$ $\operatorname{E}[\zeta]$ , i.e. if the value of the state-price deflator for state $\omega$ is higher than average.  

The change of measure from the real-world probability measure. $\mathbb{P}$ to the risk-neutral probability measure $\mathbb{Q}$ is given by the ratios $\xi_{\omega}\equiv q_{\omega}/p_{\omega}=R^{f}\zeta_{\omega}$ . The change of measure is fully captured by the random variable $\xi$ that takes on the value $\xi_{\omega}$ if state $\omega$ is realized. This random variable is called the Radon-Nikodym derivative for the change of measure and is often denoted by. $d\mathbb{Q}/d\mathbb{P}$ Note that the $\mathbb{P}$ -expectation of any Radon-Nikodym derivative. $\xi=d\mathbb{Q}/d\mathbb{P}$ must be $^{1}$ to ensure that the new measure is a probability measure. This is satisfied by our risk-neutral probability measure since  

$$
\operatorname{E}^{\mathbb{P}}\left[{\frac{d\mathbb{Q}}{d\mathbb{P}}}\right]=\sum_{\omega=1}^{S}p_{\omega}\xi_{\omega}=\sum_{\omega=1}^{S}p_{\omega}R^{f}\zeta_{\omega}=R^{f}\sum_{\omega=1}^{S}p_{\omega}\zeta_{\omega}=1.
$$  

When the state space is infinite, state-price deflators still make sense. Given a state-price deflator $\zeta$ , we can define a risk-neutral probability measure $\mathbb{Q}$ by the random variable  

$$
\xi=\frac{d\mathbb{Q}}{d\mathbb{P}}=R^{f}\zeta.
$$  

Conversely, given a risk-neutral probability measure $\mathbb{Q}$ and the risk-free gross return $R^{f}$ , we can define a state-price deflator $\zeta$ by  

$$
\zeta=(R^{f})^{-1}\frac{d\mathbb{Q}}{d\mathbb{P}}.
$$  

In the case of a finite state space, the risk-neutral probability measure is given by $\xi_{\omega}=q_{\omega}/p_{\omega}$ $\omega=1,\ldots,S$ , and we can construct a state-price vector $\psi$ and a state-price deflator $\zeta$ as  

$$
\psi_{\omega}=(R^{f})^{-1}q_{\omega},\qquad\zeta_{\omega}=(R^{f})^{-1}\xi_{\omega}=(R^{f})^{-1}\frac{q_{\omega}}{p_{\omega}},\quad\omega=1,\ldots,S.
$$  

We summarize the above observations in the following theorem:  

Theorem 4.4 Assume that a risk-free asset exists. Then there is a one-to-one correspondence between state-price deflators and risk-neutral probability measures.  

Combining this result with Theorems 4.1 and 4.2, we reach the next conclusion.  

Theorem 4.5 Assume that a risk-free asset exists. Prices admit no arbitrage if and only if a risk-neutral probability measure exists. The market is complete if and only if there is a unique riskneutral probability measure. If the market is complete and arbitrage-free, the unique risk-neutral probability measure $\mathbb{Q}$ is characterized by $d\mathbb{Q}/d\mathbb{P}=R_{f}\zeta^{*}$ , where $\zeta^{*}$ is given by (4.46).  

Risk-neutral probabilities are especially useful for the pricing of derivative assets. In Chapter 11 we will generalize the definition of risk-neutral probabilities to multi-period settings and we will also define other probability measures that are useful in derivative pricing..  

# 4.6.2 Pricing factors  

We will say that a (one-dimensional) random variable $x$ is a pricing factor for the market if there. exists some $\alpha,\eta\in\mathbb{R}$ so that  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},x]\eta,\quad i=1,\ldots,I,}\end{array}
$$  

where the factor-beta of asset $i$ is given by  

$$
\beta[R_{i},x]=\frac{\mathrm{Cov}[R_{i},x]}{\mathrm{Var}[x]}.
$$  

The constant $\eta$ is called the factor risk premium and. $\alpha$ the zero-beta return. Due to the linearity. of expectations and covariance, (4.73) will also hold for all portfolios of the $I$ assets. Note that if a risk-free asset is traded in the market, it will have a zero factor-beta and, consequently, $\alpha=R^{f}$  

The relation (4.73) does not directly involve prices. But since the expected gross return is $\operatorname{E}[R_{i}]=\operatorname{E}[D_{i}]/P_{i}$ , we have $P_{i}=\mathrm{E}[D_{i}]/\mathrm{E}[R_{i}]$ and hence the equivalent relation  

$$
P_{i}=\frac{\mathrm{E}[D_{i}]}{\alpha+\beta[R_{i},x]\eta}.
$$  

The price is equal to the expected dividend discounted by a risk-adjusted rate. You may find this relation unsatisfactory since the price implicitly enters the right-hand side through the return-beta $\beta[R_{i},x]$ . However, we can define a dividend-beta by. $\beta[D_{i},x]=\mathrm{Cov}[D_{i},x]/\mathrm{Var}[x]$ and inserting $\begin{array}{r}{D_{i}=R_{i}P_{i}}\end{array}$ we see that $\beta[D_{i},x]=P_{i}\beta[R_{i},x]$ . Equation (4.73) now implies that  

$$
{\frac{\operatorname{E}[D_{i}]}{P_{i}}}=\alpha+{\frac{1}{P_{i}}}\beta[D_{i},x]\eta
$$  

so that  

$$
P_{i}=\frac{\operatorname{E}[D_{i}]-\beta[D_{i},\boldsymbol{x}]\eta}{\alpha}.
$$  

Think of the numerator as a certainty equivalent of the risky dividend. The current price is the.   
certainty equivalent discounted by the zero-beta return, which is the risk-free return if this exists.  

What is the link between pricing factors and state-price deflators? It follows from (4.10) that any state-price deflator $\zeta$ itself is a pricing factor. That equation does not require positivity of. the state-price deflator, only the pricing condition. Therefore any random variable $x$ that satisfies $P_{i}=\operatorname{E}[x D_{i}]$ for all assets works as a pricing factor. More generally, if $x$ is a random variable and $a,b$ are constants so that. $P_{i}=\operatorname{E}[(a+b x)D_{i}]$ for all assets $i$ , then $x$ is a pricing factor. In particular,. whenever we have a state-price deflator of the form. $\zeta=a+b x$ , we can use $x$ as a pricing factor.  

Conversely, if we have a pricing factor $x$ for which the associated zero-beta return $\alpha$ is nonzero, we can find constants. $a,b$ so that $\zeta=a+b x$ satisfies the pricing condition. $P_{i}=\operatorname{E}[\zeta D_{i}]$ for $i=1,\dots,I$ . In order to see this let. $\eta$ denote the factor risk premium associated with the pricing factor $x$ and define  

$$
b=-\frac{\eta}{\alpha\operatorname{Var}[x]},\quad a=\frac{1}{\alpha}-b\operatorname{E}[x].
$$  

Then $\zeta=a+b x$ works since  

$$
\begin{array}{l}{\displaystyle\mathrm{E}[\zeta R_{i}]=a\mathrm{E}[R_{i}]+b\mathrm{E}[R_{i}x]}\ {\displaystyle=a\mathrm{E}[R_{i}]+b\left(\mathrm{Cov}[R_{i},x]+\mathrm{E}[R_{i}]\mathrm{E}[x]\right)}\ {\displaystyle=\left(a+b\mathrm{E}[x]\right)\mathrm{E}[R_{i}]+b\mathrm{Cov}[R_{i},x]}\ {\displaystyle=\frac1\alpha\left(\mathrm{E}[R_{i}]-\frac{\mathrm{Cov}[R_{i},x]}{\mathrm{Var}[x]}\eta\right)}\ {\displaystyle=\frac1\alpha\left(\mathrm{E}[R_{i}]-\beta[R_{i},x]\eta\right)}\ {\displaystyle=1}\end{array}
$$  

for any $i=1,\dots,I$ . Inserting $a$ and $b$ , we get  

$$
\zeta=a+b x={\frac{1}{\alpha}}\left(1-{\frac{\eta}{\operatorname{Var}[x]}}\left(x-\operatorname{E}[x]\right)\right).
$$  

Any pricing factor $x$ gives us a candidate $a+b x$ for a state-price deflator but it will only be a true. state-price deflator if it is strictly positive. The fact that we can find a pricing factor for a given market does not imply that the market is arbitrage-free..  

Can the pricing factor be the return on some portfolio? No problem! Suppose $x$ is a pricing factor. Look for a portfolio $\pmb{\theta}$ which will generate the dividend as close as possible to $x$ in the sense that it minimizes $\operatorname{Var}[D^{\theta}-x]$ . Since  

$$
\begin{array}{r l}&{\operatorname{Var}\big[D^{\theta}-x\big]=\operatorname{Var}\big[D^{\top}\theta-x\big]=\operatorname{Var}\big[D^{\top}\theta\big]+\operatorname{Var}[x]-2\operatorname{Cov}\big[D^{\top}\theta,x\big]}\ &{\qquad=\theta^{\top}\operatorname{Var}[D]\theta+\operatorname{Var}[x]-2\theta^{\top}\operatorname{Cov}[D,x],}\end{array}
$$  

the minimum is obtained for  

$$
\pmb{\theta}=\left(\mathrm{Var}[\pmb{D}]\right)^{-1}\mathrm{Cov}[\pmb{D},\boldsymbol{x}].
$$  

This portfolio is called the factor-mimicking portfolio. Using (3.6) and (3.7), the gross return on this portfolio is  

$$
R^{x}=\frac{\theta^{\top}\operatorname{diag}(P)R}{\theta^{\top}\operatorname{diag}(P)\mathbf{1}}=\frac{\operatorname{Cov}[D,x]^{\top}(\mathrm{Var}[D])^{-1}\operatorname{diag}(P)R}{\operatorname{Cov}[D,x]^{\top}(\mathrm{Var}[D])^{-1}\operatorname{diag}(P)\mathbf{1}}=\frac{\operatorname{Cov}[R,x]^{\top}(\mathrm{Var}[R])^{-1}R}{\operatorname{Cov}[R,x]^{\top}(\mathrm{Var}[R])^{-1}\mathbf{1}}.
$$  

The vector of covariances of the returns on the basic assets and the return on the factor-mimicking portfolio is  

$$
\operatorname{Cov}[R,R^{x}]={\frac{\operatorname{Cov}[R,x]}{\operatorname{Cov}[R,x]^{\top}(\operatorname{Var}[R])^{-1}\mathbf{1}}}
$$  

and therefore the beta of asset $i$ with respect to. $R^{x}$ is  

$$
\begin{array}{c}{\beta[R_{i},R^{x}]=\displaystyle\frac{\operatorname{Cov}[R_{i},R^{x}]}{\operatorname{Var}[R^{x}]}=\displaystyle\frac{\operatorname{Cov}[R_{i},x]}{\operatorname{Var}[R^{x}]\operatorname{Cov}[R,x]^{\top}(\operatorname{Var}[R])^{-1}\mathbf{1}}}\ {=\beta[R_{i},x]\displaystyle\frac{\operatorname{Var}[x]}{\operatorname{Var}[R^{x}]\operatorname{Cov}[R,x]^{\top}(\operatorname{Var}[R])^{-1}\mathbf{1}}.}\end{array}
$$  

Consequently, if $x$ is a pricing factor with zero-beta return $\alpha$ and factor risk premium $\eta$ , then the corresponding factor-mimicking return $R^{x}$ is a pricing factor with zero-beta return and factor risk premium  

$$
{\hat{\eta}}={\frac{\eta\operatorname{Var}[R^{x}]\operatorname{Cov}[R,x]^{\top}(\operatorname{Var}[R])^{-1}\mathbf{1}}{\operatorname{Var}[x]}}.
$$  

In that sense it is not restrictive to look for pricing factors only in the set of returns.  

Note that when the factor $x$ itself is a return, then it must satisfy  

$$
\operatorname{E}[x]=\alpha+\beta[x,x]\eta=\alpha+\eta\quad\Rightarrow\quad\eta=\operatorname{E}[x]-\alpha
$$  

so that  

$$
\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},x]\left(\operatorname{E}[x]-\alpha\right).
$$  

Now it is clear that the standard CAPM simply says that the return on the market portfolio is a pricing factor.  

We will discuss factor models in detail in Chapter 9. There we will also allow for multidimensional pricing factors.  

# 4.6.3 Mean-variance efficient returns  

A portfolio is said to be mean-variance efficient if there is no other portfolio with the same expected return and a lower return variance. The return on a mean-variance efficient portfolio is called a mean-variance efficient return. The mean-variance frontier is the curve in a $(\sigma[R],\operatorname{E}[R])$ plane traced out by all the mean-variance efficient returns.  

The analysis of mean-variance efficient portfolios was introduced by Markowitz (1952, 1959) as a tool for investors in making portfolio decisions. Nevertheless, mean-variance efficient portfolios are also relevant for asset pricing purposes due to the following theorem:  

Theorem 4.6 A return is a pricing factor if and only if it is a mean-variance efficient return different from the minimum-variance return.  

Combining this with results from the previous subsection, we can conclude that (almost) any mean-variance return $R^{\mathrm{mv}}$ give rise to a (candidate) state-price deflator of the form $\zeta=a+b R^{\mathrm{mv}}$ And the standard CAPM can be reformulated as "the return on the market portfolio is meanvariance efficient."  

We will not provide a proof of the theorem here but return to the issue in Chapter 9.  

# 4.7 Concluding remarks  

This chapter has introduced state-price deflators as a way representing the general pricing mecha-. nism of a financial market. Important properties of state-price deflators were discussed. Examples. have illustrated the valuation of assets with a given state-price deflator. But what determines. the state-price deflator? Intuitively, state prices reflect the value market participants attach to an extra payment in a given state at a given point in time. This must be related to their marginal. utility of consumption. To follow this idea, we must consider the optimal consumption choice of individuals. This is the topic of the next two chapters..  
