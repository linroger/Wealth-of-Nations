# 22.3 STANDARD TRANCHE VALUATION MODEL  

We now show how the distribution of. $D$ can be calculated under correlations different than O and.   
1. We discuss the standard market model for pricing standard tranches for a portfolio of $n$ names.  

# 22.3.1 THE GAUSSIAN COPULA MODEL  

This model is equivalent to the so-called Gaussian copula model, in a one factor setting. Let  

$$
\{S^{j}\},\quad j=1,\dots,n
$$  

be a sequence of latent variables. Their role is to generate statistically dependent zero-one variables.3 There is no model of a random variable that can generate dependent zero-one random variables with a closed-form density or distribution function.. $\{S^{j}\}$ are used in a Monte Carlo approach to do this..  

It is assumed that. $S^{j}$ follows a normal distribution and that the default of the ith name occurs the first time $S^{j}$ falls below a threshold denoted by $L_{\alpha}$ where $a$ is the jth name's default probability. The important step is the way. $S^{j}$ is structured. Consider the following one factor case,.  

$$
S^{j}=\rho^{j}F+\sqrt{1-(\rho^{j})^{2}}\in^{j}
$$  

where $F$ is a common latent variable independent of $\in^{j},\rho^{j}$ is a constant parameter, and $\in^{j}$ is the idiosyncratic component. The random variables in this setup have some special characteristics. $F$ has no superscript, so it is common to all $S^{j},j=1$ ... $n$ and it has a standard normal distribution. $\in^{j}$ are specific to each. $i$ and are also distributed as standard normal,  

$$
\begin{array}{l}{{\in}^{j}\sim N(0,1)}\ {F\sim N(0,1)}\end{array}
$$  

Finally, the common factor and the idiosyncratic components are uncorrelated.  

$$
E[\epsilon^{j}F]=0
$$  

It turns out that $\in^{j}$ and $F$ may have any desired distribution.4 If this distribution is assumed to. be normal, then the model described becomes similar to a Gaussian copula model. Note this case is in fact a one factor latent variable model.  

We obtain the mean and variance of a typical $S^{j}$ as follows  

$$
\begin{array}{c}{{E[S^{j}]=\rho E[F]+E\Big[\sqrt{1-(\rho^{2}}\in^{j}\Big]}}\ {{=0}}\end{array}
$$  

and  

$$
\begin{array}{c}{{E[(S^{j})^{2}]=\rho^{2}E[F^{2}]+E[(1-\rho^{2})(\in^{j})^{2}]}}\ {{=1+\rho^{2}-\rho^{2}=1}}\end{array}
$$  

since both random variables on the right side have zero mean and unit second moment by assumption and since $F$ is uncorrelated with $\in^{j}.$ The model above has an important characteristic that we. will use in stripping default correlation. It turns out that the correlation between defaults can be conveniently modeled using the common factor variable and the associated $\rho^{i}$ .Calculate the correlation  

$$
\begin{array}{r l}&{E[S^{j}S^{k}]=E\Big[\rho F+\sqrt{1-\rho^{2}}\in^{j}\Big]\Big[\rho F+\sqrt{1-\rho^{2}}\in^{k}\Big]}\ &{\qquad=\rho^{2}E[F^{2}]+E[2(1-\rho^{2})\in^{j}\in^{i}]+E\Big[\rho\sqrt{(1-\rho^{2})}\in^{j}F\Big]+E\Big[\rho\sqrt{(1-\rho^{2})}\in^{i}F\Big]}\end{array}
$$  

This gives  

$$
\mathrm{Corr}[S^{i}S^{j}]=\rho^{i}\rho^{j}
$$  

The case where  

$$
\rho^{i}\rho^{j}
$$  

for all $i,j$ is called the compound correlation and is the market convention. The compound default correlation coefficients is then given by $\rho^{2}$ .The $i t h$ name default probability is defined as  

$$
p^{i}=P\Big(\Big(\rho F+\sqrt{1-\rho^{2}\in^{i}}\Big)\leq L_{\alpha}\Big)
$$  

The probability is that the value of $S^{i}$ will fall below the level $L_{\alpha}$ . Remember that in Chapter 19 we introduced Merton's (1974) structural model of default where the default occurs when the value of the firm falls below the debt issued by the firm. Hence, at first glance, it appears that the market convention here is similar to Merton's model. This is somewhat misleading, however, since $S^{i}$ has no structural interpretation here. It will be mainly used to generate correlated binomial variables.  

This above setup provides an agenda one can follow to price and hedge the tranches. It will. also help us to back out an implied default correlation once we observe liquid tranche spreads in the market.  

The agenda is as follows: First, observe the CDS rate $\mathrm{cds}_{t}^{i}$ for each name in the markets. Using this, calculate the risk-neutral default probability. $p^{i}$ . Using this find the corresponding $L_{\alpha}^{i}$ . Generate pseudo-random numbers for $F$ and $\in^{i}$ . Next, assume a value for $\rho$ and calculate the implied $S^{i}$ Check to see if the value of $S^{i}$ obtained this way is less than $L_{\alpha}^{i}$ . This way, obtain a simulated default process:  

$$
d^{i}={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S^{i}<L_{\alpha}}\ {0}&{{\mathrm{otherwise}}}\end{array}\right.}
$$  

Finally calculate the number of defaults for the trial as  

$$
D=\sum_{i=1}^{n}d^{i}
$$  

Repeating this procedure. $m$ times will yield. $m$ replicas of the random variable $D$ If $m$ is large, we can use the resulting histogram as the default loss distribution on the $n$ reference names and then calculate the spreads for each tranche.  

# 22.3.2 IMPLIED CORRELATIONS  

The valuation of synthetic CDO tranches follows similar principles as the valuation of CDS described in Chapter 18. The break-even spread on a tranche is defined as the spread that sets the present value of the payments equals the present value of the payoffs of the tranche. The present value depends on the cash flows, the probability of receiving the cash flows and a discount factor. This is again analogous to the valuation of the single-name CDS. What is different in CDO tranche valuation is that now we have multiple underlying assets and the probability of cash flows must take into account the correlation structure between cash flows. This is what the standard market model described above achieves by using a Gaussian copula model specification. The standard Gaussian copula market model can be used in a similar way as the Black-Scholes model which is the standard market model in option markets. We used the Black-Scholes model to either calculate theoretical option prices based on given input parameters or to back out implied volatilities given observed market option prices. In the standard (Gaussian copula) market model, we can use default probabilities as input parameters and determine tranche spreads or we can start with market observed tranche spreads and calculate the implied probabilities. Since we are using the standard market model, the default loss distribution will depend on a certain level of default correlation due to the choice of $\rho.$ The implied correlation is that level of. $\rho$ which yields a calculated tranche. spread that equals the observed spread in the markets. The coefficient $\rho$ is the only unknown vari-. able if we observe tranche spreads.  

![](images/40ee47e19890890454cd0da94682a29abba52310339ae0b90bfc410eed9bc7f9.jpg)  
Compound correlation  

# FIGURE 22.3  

Compound correlation.  

The reason why market participants prefer to quote implied correlation instead of the market. spread directly is that correlation is independent of the overall spread level of the underlyings. This is similar to the market practice in option markets where implied volatilities instead of option prices. are quoted.  

It is common in the market to imply a correlation from market quotes for tranches. The correla-. tion that if plugged into the standard model results in the spreads observed in the market is called the compound correlation or tranche correlation. In other words, the compound correlation is the corre-. lation found by calibrating the Gaussian copula model to the price of a CDO tranche. The implied default correlation $\rho$ is the correlation that, given the observed market spread, sets the present value of the two legs of a CDO tranche equal to zero. Figure 22.3 shows a typical compound correlation plot. It shows the compound correlation for different tranches. Similar to equity markets, where the Black-Scholes model leads to implied volatility skews, smiles, or frowns, the Gaussian copula approach to model the expected loss in a given tranche leads to different correlations. The compound. correlations exhibit a typical correlation skew or correlation smile. With increasing tranche seniority, the implied correlation first decreases and then increases.  

We observe that the implied compound correlation for the mezzanine tranche is lower than for the senior and equity tranches. This dip in correlations reflects the fact that the market assigns a higher price to the risk of losses in senior tranches than predicted by the Gaussian copula model compared to the equity tranche. In other words, the market view is that defaults tend to cluster as they become more frequent.  

One of the limitations of compound correlations is that for some (mezzanine) tranches, the tranche correlation is not uniquely defined and may not even exist. These computation issues imply that the implied correlation is conceptually different from implied volatility. We will see in Section 22.6 how so-called base correlations address this issue.  

Below we have a simple example that shows this process.  

# EXAMPLE  

Let $n=3$ . Assume that the default probability is $1\%$ ; and let the default correlation be $\rho^{2}=0.36$ . We generate 10,000 replicas for each $\{S^{1},S^{2},S^{3}\}$ using  

$$
\begin{array}{l}{S^{1}=0.25F+\sqrt{64}\in^{1}}\ {~}\ {S^{2}=0.25F+\sqrt{64}\in^{2}}\ {~}\ {S^{3}=0.25F+\sqrt{64}\in^{3}}\end{array}
$$  

For example, we select four standard pseudo-random variables  

$$
\begin{array}{l}{{F=-1.12615}}\ {{}}\ {{\epsilon^{1}=-2.17236}}\ {{}}\ {{\epsilon^{2}=0.64374}}\ {{}}\ {{\epsilon^{3}=-0.326163}}\end{array}
$$  

Using these we obtain $S^{i}$ as  

$$
\begin{array}{l}{S^{1}=-2.41358}\ {{}}\ {S^{2}=-0.160698}\ {{}}\ {S^{3}=-0.936621}\end{array}
$$  

We then calculate the corresponding. $S^{j}$ and see if they are less than. $L_{\cdot01}=-2.32$ where the latter is the threshold that gives a. $1\%$ tail probability in a standard normal distribution.  

If $S^{1}<-2.32$ $S^{2}<-2.32$ $S^{3}<-2.32$ , then we let the corresponding $d^{i}=1$ . Otherwis! they are zero. We then add the three $d^{i}$ to get the $D$ for that Monte Carlo run.  

In this particular case, $d^{1}=1$ $d^{2}=0$ $d^{\bar{3}}=0$ . So the first Monte Carlo run gives $D=1$  

Next we would like to show an example dealing with implied correlation calculations. The example again starts with a Monte Carlo sample on the. $D$ , obtains the tranche spreads, then extends. this to three functions, calculated numerically, that show the mapping between tranche spreads and. correlation.  

# EXAMPLE: IMPLIED CORRELATION  

Suppose we are given a Monte Carlo sample of correlated defaults from a reference portfolio,  

$$
\operatorname{Sample}=\{D_{1},...,D_{m}\}
$$  

Then, we can obtain the histogram of the number of defaults.  

Assume $\rho=0.3$ $n=100$ , and $m=1000$ . Running the procedure above we obtain 1000 replicas of $D_{i}$ . We can do at least two analyses with the distribution of $D$ First we can calculate the fair value of the tranches of interest. For example, with recovery $40\%$ and zero interest rates, we can compute the value of the equity tranche in this case as  

$$
\sec^{e}=[0.05(0)+0.12(33.33)0.6+0.15(66)0.6+(1-0.05-0.12-0.15)]0.6=0.68
$$  

This 1-year spread is based on the fact that the party that sells protection with nominal $N=100$ on the first three defaults will lose nothing if there are no defaults, will lose a third of the investment if there is one default, will lose two-thirds if there are two defaults, and finally will lose all investments if there are three defaults.  

Repeating this for all values of. $\rho^{2}\in[0,1]$ we can get three surfaces. These graphs plot the. value of the equity, mezzanine, and senior tranches against the fair value of the tranche.  

Note that the value of the equity tranche goes up as correlation increases. The value of the mezzanine tranche is a $U.$ -shaped curve, whereas the value of the senior tranche is again monotonic.. The end of chapter exercises provide another numerical example..  

# 22.3.3 THE CENTRAL LIMIT EFFECT  

Why does the default loss distribution change as a function of the correlation? This is an important technical problem that has to do with the central limit theorem and the assumptions behind it. Now define the correlated zero-one stochastic process $z_{i}$  

$$
z_{j}={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}S^{j}\leq L_{\alpha}}\ {0}&{{\mathrm{otherwise}}}\end{array}\right.}
$$  

Next calculate a sum of these random variables as  

$$
Z^{n}=\sum_{j=1}^{n}z^{j}
$$  

According to the central limit theorem, even if. $z^{j}$ are individually very far from being normally distributed and are correlated, then the distribution of the sum will approach a normal distribution if the underlying processes have finite means and variances as in. $n\to\infty$  

$$
{\frac{\sum_{i}^{n}z_{i}-\sum_{i}^{n}\mu_{i}}{\sqrt{\sum_{i}^{n}\sigma_{i}^{2}}}}\to N(\mu^{d},\sigma^{d})
$$  

Thus if we had a very high number of names in the reference portfolio, the distribution of $D$ will look like normal. On the other hand, with finite $n$ and highly correlated $z^{j}$ , this convergence effect will be slow. The higher the "correlation"' $\rho$ , the slower will the convergence be. In particular, with $n$ around 100, the distribution of the $D$ will be heavily dependent on the size of $\rho$ and will be far from normal. This is where the relationship between Index tranches and correlation comes in. In the extreme case when correlation is perfect, the sum will involve the same $z^{j}$  
