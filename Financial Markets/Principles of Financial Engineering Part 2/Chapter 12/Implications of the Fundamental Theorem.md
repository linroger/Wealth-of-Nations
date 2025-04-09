# 12.5 IMPLICATIONS OF THE FUNDAMENTAL THEOREM  

The fundamental theorem of asset pricing has a number of implications that play a critical role in. financial engineering and derivatives pricing. First, using this theorem we can obtain probability. distributions that can be used in asset pricing. These probability distributions will be objective and. operational. Second, the theorem leads to the so-called Martingale representation of asset prices. Such a representation is useful in modeling asset price dynamics. Third, we will see that the Martingale representation can serve to objectively set expected asset returns. This property eliminates the need to model and estimate the "drift factors' in asset price dynamics. We will now study these issues in more detail.  

# 12.5.1 RESULT 1: RISK-ADJUSTED PROBABILITIES  

$Q^{i}$ introduced in the previous section can be modified judiciously in order to obtain convenient probability distributions that the financial engineer can work with. These distributions do not provide real-world odds on the states of the world. $\omega^{i}$ , and hence cannot be used directly in econometric. prediction. Yet they do yield correct arbitrage-free prices. (This section shows how.) But there is more. As there are many such distributions, the market practitioner can also choose the distribution that fits his/her current needs best. How to makes this choice is discussed in the next section..  

# 12.5.1.1 Risk-neutral probabilities  

Using the state prices $Q^{i}$ we first obtain the so-called risk-neutral probability distribution. Consider the first row of the matrix equation (12.9). Assume that it represents the savings account. 15  

$$
\left(1+r_{t_{0}}\right)Q^{1}+\cdots+\left(1+r_{t_{0}}\right)Q^{n}=1
$$  

Relabel, using  

$$
\tilde{p}_{i}=\left(1+r_{t_{0}}\right)Q^{i}
$$  

According to Eq. (12.40), we have  

$$
\tilde{p}_{i}+\cdots+\tilde{p}_{n}=1
$$  

where  

$$
0<\tilde{p}_{i}
$$  

since each $Q^{i}$ is positive. This implies that the numbers. $\tilde{p}_{i}$ have the properties of a discrete proba-. bility distribution. They are positive and they add up to one. Since they are determined by the markets, we call them "risk-adjusted" probabilities. They are, in fact, obtained as linear combinations of $n$ current asset prices. This particular set of synthetic probabilities is referred to as the riskneutral probability distribution.  

To be more precise, the risk-neutral probabilities $\{\tilde{p}_{i}\}$ are time $t_{0}$ probabilities on the states that occur at time. $T$ Thus, if we wanted to be more exact, they would have to carry two more subscripts, $t_{0}$ and $T.$ Yet, these will be omitted for notational convenience and assumed to be understood by the reader.  

# 12.5.1.2 Other probabilities  

Several other synthetic probabilities can be generated, and these may turn out to be more useful than the risk-neutral probabilities. Given the positive $Q^{i}$ we can rescale these by any positive normalizing factor so that they can be interpreted as probabilities. There are many ways to proceed. In fact, as long as a current asset price $S_{k t_{0}}$ is nonzero and $z_{i}^{j}$ are positive, one can choose any kth row of the matrix equation in Eq. (12.9) to write and then define  

$$
1=\sum_{i=1}^{n}\frac{z_{k}^{i}}{S_{k t_{0}}}Q^{i}
$$  

and then define  

$$
{\frac{z_{k}^{i}}{S_{k t_{0}}}}Q^{i}={\tilde{p}}_{i}^{k}
$$  

$\tilde{p}_{i}^{k},i=1,...,n,$ can be interpreted as probabilities obtained after normalizing by the $S_{k t_{0}}$ asset. $\tilde{p}_{i}^{k}$ will be positive and will add up to one. Hence, they will have the characteristics of a probability distribution, but again they cannot be used in prediction since they are not the actual probabilities of a particular state of the world $\omega^{i}$ occurring. Clearly, for each nonzero $S_{k t_{0}}$ we can obtain a new probability $\tilde{p}_{i}^{k}$ . These will be different across states $\omega^{i}$ , as long as the time. $T$ value of the asset is. positive in all states.16  

It turns out that how we normalize a sequence of $\{Q^{i}\}$ in order to convert them into some syn thetic probability is important. The special case, where  

$$
S_{k t_{0}}=B(t_{0},T)
$$  

$B(t_{0},T)$ being the current price of a. $T.$ -maturity risk-free pure discount bond, is especially interesting. This yields the so-called. $T.$ forward measure. Because the discount bond matures at time $T.$ the time $T$ values of the asset are given by.  

$$
z_{k}^{i}=1
$$  

for all $i.$  

Thus, we can simply divide state prices $Q^{i}$ by the current price of a default-free discount bond maturing at time $t_{0}$ , and obtain the $T.$ -forward measure:  

$$
\tilde{p}_{i}^{T}=Q^{i}\frac{1}{B(t_{0},T)}
$$  

We will see in Chapter 14 that the. $T$ forward measure is the natural way to deal with payoffs associated with time $T.$ Let's consider an example.  

# EXAMPLE  

Suppose short-term risk-free rates are $5\%$ and that there are four states of the world. We observe the following arbitrage-free bid prices for four assets at time $t_{0}$  

$$
S_{1t_{0}}=2.45238,S_{2t_{0}}=1.72238,S_{3t_{0}}=6.69429,S_{4t_{0}}=3.065
$$  

It is assumed that at time $T=t_{0}+1$ , measured in years, the four possible values for each asset will be given by the matrix:  

$$
\left[\begin{array}{l l l l}{10}&{3}&{1}&{1}\ {2}&{3}&{2}&{1}\ {1}&{10}&{10}&{1}\ {8}&{2}&{10}&{2}\end{array}\right]
$$  

We can form the matrix equation and then solve for the corresponding $Q^{i}$  

$$
\begin{array}{r}{\left[\begin{array}{c}{1}\ {S_{1t_{0}}}\ {S_{2t_{0}}}\ {S_{3t_{0}}}\ {S_{4t_{0}}}\end{array}\right]=\left[\begin{array}{c c c c}{1+0.5}&{1+0.5}&{1+0.5}&{1+0.5}\ {10}&{3}&{1}&{1}\ {2}&{3}&{2}&{1}\ {1}&{10}&{10}&{6}\ {8}&{2}&{10}&{2}\end{array}\right]\left[\begin{array}{c}{Q^{1}}\ {Q^{2}}\ {Q^{3}}\ {Q^{4}}\end{array}\right]}\end{array}
$$  

Using the first four rows of this system, we solve for $Q^{i}$ -..  

$$
Q^{1}=0.1,Q^{2}=0.3,Q^{3}=0.07,Q^{4}=0.482
$$  

Next, we obtain the risk-neutral probabilities by using  

$$
\tilde{p}_{i}=(1+0.5)Q^{i}
$$  

which gives  

$$
\tilde{p}_{1}=0.105,\tilde{p}_{2}=0.315,\tilde{p}_{3}=0.0735,\tilde{p}_{4}=0.5065
$$  

As a final point, note that we used the first four rows of the system shown here to determine the values of $Q^{i}$ . However, the price of $S_{4t_{0}}$ is also arbitrage-free:  

$$
\sum_{i=1}^{4}Q^{i}S_{4T}^{i}=3.065
$$  

as required.  

Interestingly, for short-term instruments, and with "normal" short-term interest rates of around $3-5\%$ , the savings account normalization makes little difference. If $T-t_{0}$ is small, $Q^{i}$ will be only marginally different from p 17  

# 12.5.1.3 A remark  

Can derivatives be used for normalization? For example, instead of normalizing by a savings account or by using bonds, could we normalize with a swap? The answer is no. There are probabilities called swap measures, but the normalization that applies in these cases is not a swap, but an annuity. Most derivatives are not usable in the normalization process because normalization by an $S_{k t}$ implies, essentially, that the state prices $Q^{i}$ are multiplied by factors such as  

$$
\frac{z_{k}^{i}}{S_{k t}}\frac{S_{k t}}{z_{k}^{i}}=1
$$  

and then grouped according to  

$$
\frac{z_{k}^{i}}{S_{k t}}\frac{S_{k t}}{z_{k}^{i}}Q^{i}=\frac{S_{k t}}{z_{k}^{i}}\tilde{p}_{i}^{k}
$$  

17 For example, at a $5\%$ Short rate, a 1-month discount bond will sll for approximately  

$$
B(t_{0},t)={\frac{1}{1+0.5{\frac{1}{12}}}}=0.9958
$$  

so that dividing by this scale factor will not modify $Q^{i}$ very much.  

But in this operation, both. $z_{k}^{i}$ $i=1,...,n$ and $S_{k t}$ should be nonzero. Otherwise the ratios would be undefined. This will be seen below.  

# 12.5.1.4 Swap measure  

The normalizations thus far used only one asset, $S_{k t}$ in converting $Q^{i}$ into probabilities $\tilde{p}^{k}$ . This need not be so. We can normalize using a linear combination of many assets, and sometimes this proves very useful. This is the case for the so-called swap, or annuity, measure. The swap measure is dealt with in Chapter 17.  

# 12.5.2 RESULT 2: MARTINGALE PROPERTY  

The fundamental theorem of asset pricing also provides a convenient model for pricing and riskmanagement purposes. All properly normalized asset prices have a Martingale property under a properly selected synthetic probability $\tilde{p}^{k}$ . Let $X_{t}$ be a stochastic process that has the following property:.  

$$
X_{t}=E_{t}^{\tilde{p}^{k}}[X_{T}]\quad t<T
$$  

This essentially says that $X_{t}$ have no predictable trend for all $t.X_{t}$ is referred to as a Martingale. To see how this can be applied to asset pricing theory, first choose the risk-neutral probability $\tilde{P}$ as the working probability distribution.  

# 12.5.2.1 Martingales under $\tilde{\pmb{P}}$  

Consider any kth row in the matrix equation (12.9)  

$$
S_{k t_{0}}=(z_{k}^{1})Q^{1}+(z_{k}^{2})Q^{2}+\cdots+(z_{k}^{n})Q^{n}
$$  

Replace $Q^{i}$ with the risk-neutral probabilities $\tilde{p}_{i}$ using  

$$
Q^{i}=\frac{1}{1+r_{t_{0}}}\tilde{p}_{i}
$$  

$r_{t_{0}}$ is the interest on a risk-free 1-year deposit.  

This gives  

$$
S_{k t_{0}}-{\frac{1}{1+r_{t_{0}}}}\left[z_{k}^{1}\tilde{p}_{1}+\cdots+z_{k}^{n}\tilde{p}_{n}\right]
$$  

Here, the right-hand side is an average of the future values of $S_{k T},$ weighted by $\tilde{p_{i}}$ Thus, bringing back the time subscripts, the current arbitrage-free price $S_{k t_{0}}$ satisfies  

$$
S_{k t_{0}}=\frac{1}{\left(1+r_{t_{0}}\right)}E_{t_{0}}^{\tilde{p}}[s_{k T}]\quad t_{0}<T
$$  

In general terms, letting  

$$
X_{t}={\frac{\mathrm{time}-t{\mathrm{value~of~}}S_{k t}}{\mathrm{time}-t{\mathrm{value~of~the~savings~account}}}}
$$  

we see that asset values normalized by the savings deposit have the Martingale property:  

$$
X_{t}=E_{t}^{\tilde{p}}[X_{T}]\quad t<T
$$  

Thus, all tools associated with Martingales immediately become available to the financial engineer for pricing and risk management..  

# 12.5.2.2 Martingales under other probabilities  

The convenience of working with Martingales is not limited to the risk-neutral measure $\tilde{P}$ A normalization with any non-zero price $S_{j t}$ will lead to another Martingale. Consider the same kth row of the matrix equation in Eq. (12.9)  

$$
S_{k t_{0}}=(z_{k}^{1})Q^{1}+\cdots+(z_{k}^{n})Q^{n}
$$  

This time, replace $Q^{i}$ using $S_{j t_{0}},j\ne k$ normalization:  

$$
\tilde{p}_{i}^{j}=Q^{1}\frac{z_{j}^{i}}{S_{j t_{0}}}
$$  

We obtain, assuming that the denominator elements are positive:  

$$
{{S}_{k t_{0}}}={{s}_{j t_{0}}}\left[{z}_{k}^{1}\frac{1}{z_{j}^{1}}{{\tilde{p}}_{1}^{j}}+\cdots+z_{k}^{n}\frac{1}{z_{j}^{n}}{{\tilde{p}}_{n}^{j}}\right]
$$  

this means that the ratio,  

$$
X_{t}=\frac{S_{k t}}{S_{j t}}
$$  

is a Martingale under $\tilde{P}^{j}$ measure:  

$$
X_{t}-E_{t}^{\tilde{p}^{j}}[X_{T}]\quad t<T
$$  

It is obvious that the probability associated with a particular Martingale is a function of the normalization that is chosen, and that the implied Martingale property can be exploited in pricing. By choosing a Martingale, the financial engineer is also choosing the probability that he or she will be working with. In the remainder of this chapter and in the next, we will see several examples of how Martingale properties can be utilized.  

# 12.5.3 RESULT 3: EXPECTED RETURNS  

The next implication of the fundamental theorem is useful in modeling arbitrage-free dynamics for asset prices. Every synthetic probability leads to a particular expected return for the asset prices under consideration. These expected returns will differ from the true (subjective) expectations of players in the markets, but because they are agreed upon by all market participants and are associated with arbitrage-free prices, they will be even more useful than the true expectations.  

We conduct the discussion in terms of the risk-neutral probability $\tilde{P}$ but our conclusions are valid for all other $\tilde{p}^{k}$ . Consider again the Martingale property for an asset whose price is denoted by $S_{t},$ but this time reintroduce the day's adjustment parameter $\delta$ , dropping the assumption that $t_{i}$ represents years. We can write, for some $0<\delta$  

$$
S_{t}=\frac{1}{(1+r_{t}\delta)}E_{t}^{\tilde{P}}[S_{t+\delta}]
$$  

Rearrange to obtain  

$$
(1+r_{t}\delta)=E_{t}^{\tilde{P}}\left[\frac{S_{t+\delta}}{S_{t}}\right]
$$  

According to this expression, under the probability $\tilde{P}$ expected net annual returns for all liquid. assets will equal $r_{t},$ the risk-free rate observed at time. $t$  

Similar results concerning the expected returns of the assets are obtained under other probabilities $\tilde{p}^{k}$ . The expected returns will be different under different probabilities. Market practitioners can. select the working probability so as to set the expected return of the asset to a desired number.18.  

In Chapter 14, we will see more complicated applications of this idea using time. $T$ forward measures. There, the expected change in the forward rates is set equal to zero by a judicious choice of probabilities.  

# 12.5.3.1 Martingales and risk premia  

Let us see how the use of Martingales "internalizes" the risk premia associated with nondiversifiable market risks. Let $X_{t},t\in[t_{0},T]$ be a risky asset and $\Delta>0$ be a small time interval. The annualized gross return of $X_{t}$ as expected by players at time $t$ is defined by  

$$
1+\hat{R_{t}}\Delta=E_{t}^{P}\left[\frac{X_{t+\Delta}}{X_{t}}\right]
$$  

vhere $P$ represents the real-world probability used by market participants in setting up their expecation. Since this is an actual market expectation, the gross return will contain a risk premium:  

$$
\hat{R_{t}}=r_{t}=\mu_{t}
$$  

where $r_{t}$ is the risk-free rate and. $\mu_{t}$ is the risk premium commanded by the risky asset.l' Putting these together, we have.  

$$
(1+r_{t}\Delta+\mu_{t}\Delta)=E_{t}^{P}\left[\frac{X_{t+\Delta}}{X_{t}}\right]
$$  

or  

$$
X_{t}=\frac{1}{(1+r_{t}\Delta+\mu_{t}\Delta)}=E_{t}^{P}[X_{t+\Delta}]
$$  

This equality states that the asset price $X_{t+\Delta}$ discounted by the factor. $(1+r_{t}\Delta+\mu_{t}\Delta)$ is a Martingale only if we use the probability $P$ . Note that in this setup there are two unknowns: (i) the risk premium $\mu_{t}$ and (ii) the real-world probability. $P_{\cdot}^{20}$ Future cash flows accordingly need to be discounted by subjective discount factors and real-world probabilities need to be estimated. The pricing problem under these conditions is more complex. Financial engineers have to determine the value of the risk premium in addition to "projecting" future earnings or cash flows.  

Now consider an alternative. Setting the (positive) risk premium equal to zero in the previous equation gives the inequality  

$$
X_{t}<\frac{1}{(1+r_{t}\Delta)}E_{t}^{P}[X_{t+\Delta}]
$$  

But this is the same as risk-free savings account normalization. This means that by switching from $P$ to $\tilde{P}$ we can restore the equality  

$$
X_{t}=\frac{1}{(1+r_{t}\Delta)}E_{t}^{\tilde{P}}[X_{t+\Delta}]
$$  

Thus, normalization and synthetic probabilities internalize the risk premia by converting both unknowns into a known and objective probability $\tilde{P}$ . Equation (12.77) can be exploited for pricing and risk management.  
