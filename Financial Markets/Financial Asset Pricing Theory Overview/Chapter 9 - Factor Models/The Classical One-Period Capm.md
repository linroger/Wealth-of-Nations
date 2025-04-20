---
tags:
  - asset_pricing
  - capm
  - market_portfolio
  - mean_variance
  - quadratic_utility
aliases:
  - Capital Asset Pricing Model
  - Sharpe-Lintner-Mossin Model
key_concepts:
  - Classical CAPM
  - Consumption-based asset pricing
  - Market portfolio return
  - Mean-variance analysis
  - Quadratic utility function
---

# 9.2 The classical one-period CAPM  

The classical CAPM developed by Sharpe (1964), Lintner (1965), and Mossin (1966) says that return on the market portfolio is a pricing factor so that.  

$$
\mathrm{E}[R_{i}]=\alpha+\beta[R_{i},R_{M}]\left(\mathrm{E}[R_{M}]-\alpha\right),\quad i=1,2,\ldots,I,
$$  

for some zero-beta return $\alpha$ , which is identical to the risk-free rate if such exists. Here the marketbeta is defined as $\beta[R_{i},R_{M}]=\mathrm{Cov}[R_{i},R_{M}]/\mathrm{Var}[R_{M}]$  

The classical CAPM is usually derived from mean-variance analysis. If all individuals have quadratic utility or returns are normally distributed, any individual will optimally pick a meanvariance efficient portfolio. If $R_{l}$ denotes the return on the portfolio chosen by individual $\textit{l}$ and $w_{l}$ denotes individual. $\textit{l}$ 's share of total wealth, the return on the market portfolio will be $\begin{array}{r}{R_{M}=\sum_{l=1}^{L}w_{l}R_{l}}\end{array}$ and the market portfolio will be mean-variance eficient. As was already stated in Theorem 4.6 (demonstrated later in this chapter), the return on any mean-variance efficient portfolio will satisfy an equation like (9.1). In particular, this is true for the market portfolio when it is efficient..  

To see how the classical CAPM fits into the consumption-based asset pricing framework, consider a model in which all individuals have time-additive expected utility and are endowed with some time 0 wealth but receive no time 1 income from non-financial sources. Let us consider an arbitrary individual with initial wealth endowment. $e_{0}$ . If the individual consumes $c_{0}$ at time 0 she will invest $e_{0}-c_{0}$ in the financial assets. Representing the investment by the portfolio weight vector. $\pi$ , the gross return on the portfolio will be $\begin{array}{r}{R^{\pi}=\pi\cdot R=\sum_{i=1}^{I}\pi_{i}R_{i}}\end{array}$ . The time $^{1}$ consumption wil equal the total dividend of the portfolio, which is the gross return multiplied by the initial investment, i.e.  

$$
c=R^{\pi}(e_{0}-c_{0}).
$$  

We can substitute this into the marginal rate of substitution of the individual so that the associated state-price deflator becomes  

$$
\zeta=e^{-\delta}\frac{u^{\prime}(c)}{u^{\prime}(c_{0})}=e^{-\delta}\frac{u^{\prime}\left(R^{\pi}(e_{0}-c_{0})\right)}{u^{\prime}(c_{0})}.
$$  

If the economy has a representative individual, she has to own all the assets, i.e. she has to invest. in the market portfolio. We can then replace. $R^{\pi}$ by $R_{M}$ , the gross return on the market portfolio.. We can obtain the classical CAPM from this relation if we either assume that the utility function is quadratic or that the return on the market portfolio is normally distributed..  

Quadratic utility. The quadratic utility function $u(c)~=~-(\bar{c}-c)^{2}$ is a special case of the. satiation HARA utility functions. Marginal utility $u^{\prime}(c)=2(\bar{c}-c)$ is positive for $c<c$ so that consumption in excess of. $c$ will decrease utility. Another problem is that the absolute risk aversion $\mathrm{ARA}(c)=1/({\bar{c}}-c)$ is increasing in the level of consumption. For quadratic utility, Eq. (9.2) becomes  

$$
\zeta=e^{-\delta}\frac{\bar{c}-R^{\pi}(e_{0}-c_{0})}{\bar{c}-c_{0}}=e^{-\delta}\frac{\bar{c}}{\bar{c}-c_{0}}-e^{-\delta}\frac{e_{0}-c_{0}}{\bar{c}-c_{0}}R^{\pi},
$$  

which is affine in the portfolio return. It now follows from the discussion in Section 4.6.2 (also see later section in the present chapter) that the portfolio return is a pricing factor so that  

$$
\begin{array}{r}{\operatorname{E}[R_{i}]=\alpha+\beta[R_{i},R^{\pmb{\pi}}]\left(\operatorname{E}[R^{\pmb{\pi}}]-\alpha\right).}\end{array}
$$  

Again, if this applies to a representative individual, we can replace $R^{\pi}$ by the market portfolio return $R_{M}$ and we have the classical CAPM.  

For the quadratic utility function the absolute risk tolerance is $\operatorname{ART}(c)=-c+{\bar{c}}$ . If all individuals have quadratic utility functions (possibly with different $\bar{c}$ 's) and we assume that a risk-free asset is traded and all time 1 endowments are spanned by traded assets, Theorem 7.6 implies that the optimal consumption of any individual is affine in the aggregate endowment and therefore it can be implemented by investing in a portfolio of the risk-free asset and the market portfolio of all assets. The return on the portfolio will be a weighted average of the risk-free return and the market return, $R^{\pi}=w_{f}R^{f}+(1-w_{f})R_{M}$ , and substituting this into (9.3) we see that the state-price deflator associated with any given individual will be affine in $R_{M}$ . Again, Theorem 9.3 will then give us the classical CAPM.  

Normally distributed returns. We will show that for almost any utility function we can derive the classical CAPM relation if returns are jointly normally distributed. We need the following result called Stein's Lemma:  

Lemma 9.1 (Stein's Lemma) If $x$ and $y$ are jointly normally distributed random variables and $g:{\mathbb{R}}\rightarrow{\mathbb{R}}$ is a differentiable function with. $\operatorname{E}[|g^{\prime}(y)|]<\infty$ , then  

$$
\mathrm{Cov}[x,g(y)]=\mathrm{E}[g^{\prime}(y)]\mathrm{Cov}[x,y].
$$  

Proof: Define the random variable $\varepsilon$ by $\varepsilon=x-\alpha-\beta y$ , where $\beta=\mathrm{Cov}[x,y]/\mathrm{Var}[y]$ $\alpha=$ $\operatorname{E}[x]-\beta\operatorname{E}[y]$ , and $\mathrm{Cov}[\varepsilon,y]=0$ . Since $\varepsilon$ and $y$ are jointly normally distributed, the fact that they are uncorrelated implies that they will be independent. It follows that $\mathrm{Cov}[\varepsilon,g(y)]=0$ for any function $g$ . Therefore,  

$$
y)]=\beta\operatorname{Cov}[y,g(y)]+\operatorname{Cov}[\varepsilon,g(y)]=\beta\operatorname{Cov}[y,g(y)
$$  

Let us write the mean and variance of $y$ as $\mu_{y}$ and $\sigma_{y}^{2}$ , respectively. Then  

$$
\operatorname{Cov}[y,g(y)]=\operatorname{E}[y g(y)]-\operatorname{E}[y]\operatorname{E}[g(y)]=\operatorname{E}[(y-\mu_{y})g(y)]=\int_{-\infty}^{\infty}(y-\mu_{y})g(y)f(y)d y,
$$  

where  

$$
f(y)=\frac{1}{\sigma_{y}\sqrt{2\pi}}\exp{\left\{-\frac{1}{2\sigma_{y}^{2}}(y-\mu_{y})^{2}\right\}}
$$  

is the probability density function of $y$ . Noting that $f^{\prime}(y)=-f(y)(y-\mu_{y})/\sigma_{y}^{2}$ , integration by. parts gives  

$$
\begin{array}{l}{{\displaystyle\int_{-\infty}^{\infty}(y-\mu_{y})g(y)f(y)d y=-\sigma_{y}^{2}\int_{-\infty}^{\infty}g(y)f^{\prime}(y)d y}}\ {{\displaystyle\qquad=\sigma_{y}^{2}\int_{-\infty}^{\infty}g^{\prime}(y)f(y)d y-\sigma_{y}^{2}\Big[g(y)f(y)\Big]_{y=-\infty}^{\infty}}}\ {{\displaystyle\qquad=\sigma_{y}^{2}\mathrm{E}[g^{\prime}(y)]}}\end{array}
$$  

provided that $g(y)$ does not approach plus or minus infinity faster than $f(y)$ approaches zero as $y\rightarrow\pm\infty$ . Hence,  

$$
\operatorname{Cov}[x,g(y)]=\beta\operatorname{Cov}[y,g(y)]=\beta\sigma_{y}^{2}\operatorname{E}[g^{\prime}(y)]=\operatorname{Cov}[x,y]\operatorname{E}[g^{\prime}(y)]
$$  

as claimed.  

For any state-price deflator of the form $\zeta=g(x)$ where $x$ and $R_{i}$ are jointly normally distributed,. we thus have.  

$$
\begin{array}{r l}&{1=\mathrm{E}[g(x)R_{i}]=\mathrm{E}[g(x)]\mathrm{E}[R_{i}]+\mathrm{Cov}[g(x),R_{i}]}\ &{\phantom{=}=\mathrm{E}[g(x)]\mathrm{E}[R_{i}]+\mathrm{E}[g^{\prime}(x)]\mathrm{Cov}[x,R_{i}]}\ &{\phantom{=}=\mathrm{E}[g(x)]\mathrm{E}[R_{i}]+\mathrm{E}[g^{\prime}(x)]\mathrm{E}[(x-\mathrm{E}[x])R_{i}]}\ &{\phantom{=}=\mathrm{E}\left[\{\mathrm{E}[g(x)]-\mathrm{E}[x]E[g^{\prime}(x)]+\mathrm{E}[g^{\prime}(x)]x\right\}R_{i}]}\ &{\phantom{=}=\mathrm{E}[(a+b x)R_{i}],}\end{array}
$$  

for some constants $a$ and $b$ . Therefore, we can safely assume that $g(x)$ is affine in $x$  

In (9.2) we have  

$$
\zeta=e^{-\delta}\frac{u^{\prime}\left(R^{\pi}(e_{0}-c_{0})\right)}{u^{\prime}(c_{0})}=g(R^{\pi}),
$$  

and if the individual asset returns are jointly normally distributed, the return on any portfolio and the return on any individual asset will also be jointly normally distributed. According to Stein's Lemma we can then safely assume that $\zeta$ is affine in. $R^{\pi}$ . Again, this implies that. $R^{\pi}$ is a pricing factor. Note, however, that to apply Stein's Lemma, we have to check that $\operatorname{E}[|g^{\prime}(R^{\pi})|]$ is finite. In. our case,  

$$
g^{\prime}(R^{\pi})=e^{-\delta}(e_{0}-c_{0})\frac{u^{\prime\prime}\left(R^{\pi}(e_{0}-c_{0})\right)}{u^{\prime}(c_{0})}.
$$  

With log-utility, $u^{\prime\prime}(c)=-1/c^{2}$ , and since $\mathrm{E}[1/(R^{\pi})^{2}]$ is infinite (or undefined if you like) when $R^{\pi}$ is normally distributed, we cannot apply Stein's Lemma. In fact, when $R^{\pi}$ is normally distributed, we really need the utility function to be defined on the entire real line, which is not the case for the most reasonable utility functions. For negative exponential utility, there is no such problem.  

The assumptions leading to the classical CAPM are clearly problematic. Preferences are poorly represented by quadratic utility functions or other mean-variance utility functions. Returns are not normally distributed. A more fundamental problem is the static nature of the one-period CAPM. Later in this chapter we will discuss how the CAPM can be extended to a dynamic setting. It turns out that we can derive an intertemporal CAPM under much more appropriate assumptions about utility functions and return distributions. We will need CRRA utility and lognormally distributed returns. In addition, we will need the return distribution to be stationary, i.e. the same for all future periods of the same length.  
