---
tags:
  - arbitrage_free
  - bdt_model
  - binomial_tree
  - calibration
  - libor_tree
  - pricing_functions
  - volatility_quotes
  - zero_coupon_bonds
aliases:
  - Application 2
  - BDT
  - LIBOR
key_concepts:
  - Arbitrage-free benchmark prices
  - BDT model
  - Calibrating a model
  - Extracting LIBOR tree
  - Pricing functions
---

# 13.3 APPLICATION 2: CALIBRATION  

Calibrating a model means selecting the model parameters such that the observed arbitrage-free benchmark prices are duplicated by the use of this model. In this section we give two examples for this procedure. Since we already discussed several examples of how the fundamental theorem can be applied to SDEs, in this section we concentrate instead on tree models. As the last section has shown, calibration can be done using Monte Carlo and the SDEs as well.  

# 13.3.1 CALIBRATING A TREE  

The BDT model is a good example for procedures that extract information from market prices. The model calibrates future trajectories of the spot rate $r_{t}$ . The BDT model illustrates the way arbitrage-. free dynamics can be extracted from liquid and arbitrage-free asset prices.12.  

The basic idea of the BDT model is that of any other calibration methodology. Let it be implicit binomial trees, estimation of state prices implicit in asset prices, or estimation of risk-neutral probabili-. ties. The model assumes that we are given a number of benchmark arbitrage-free zero-coupon bond. prices and a number of relevant volatility quotes in these markets. These volatility quotes can come from liquid caps and floors or from swaptions that are discussed in Chapters 16 and 17, respectively. The procedure evolves in three steps. First, arbitrage-free benchmark securities' prices and the relevant volatilities are obtained. Second, from these data the arbitrage-free dynamics of the relevant variable are extracted. Finally, other interest-sensitive securities are priced using these arbitrage-free dynamics.  

This section illustrates the procedure using a three-period binomial tree. To simplify the nota-. tion and concentrate on understanding the main ideas, this section assumes that the time intervals $\Delta$ in the tree equal 1 year, and that the day-count parameter. $\delta$ in a LIBOR setting equals 1 as well.. The reader can easily generalize this simple example..  

# 13.3.2 EXTRACTING A LIBOR TREE  

Suppose we have arbitrage-free prices of three default-free benchmark zero-coupon bonds $\{B(t_{0},t_{1})$ $B(t_{0},t_{2}),B(t_{0},t_{3})\}$ . Also suppose we observe reliable volatility quotes $\sigma_{i}i=0$ , 1, 2 for the LIBOR rates $L_{t_{0}},L_{t_{1}},L_{t_{2}}$  

First note that. $\sigma_{0}$ is by definition equal to 0, because time. $t_{0}$ variables have already beer observed at time $t_{0}$ . Next, assume that we have the following data:  

$$
\begin{array}{c}{\sigma_{1}=15\%}\ {\sigma_{2}=20\%}\ {B(t_{0},t_{1})=0.95}\ {B(t_{0},t_{2})=0.87}\ {B(t_{0},t_{3})=0.79}\end{array}
$$  

From these data, we extract information concerning the future arbitrage-free behavior of the LIBOR rates $L_{t_{i}}$ . We first need some pricing functions that tie the arbitrage-free bond prices to the dynamics of. the LIBOR rates. These pricing functions are readily available from the fundamental theorem.  

# 13.3.2.1 Pricing functions  

Consider the fundamental theorem written for times $t_{0}$ and $t_{3}$ . Suppose there are $k$ states of the world at time $t_{3}$ and consider the matrix equation discussed in Chapter 11:  

$$
S_{k x1}=D_{k x k}Q_{k x1}
$$  

Here, $S$ is a $(k x1)$ vector of arbitrage-free asset prices at time $t_{0},D$ is the payoff matrix at time $t_{3}$ and $Q$ is the $(k x1)$ vector of positive state prices at time $t_{3}$  

Suppose the first asset is a 1-year LIBOR-based deposit and the second asset is the bond $B(t_{0},$ $t_{3})$ , which matures and pays 1 dollar at $t_{3}$ . Then, the first two rows of the matrix equation in Eq. (13.56) will be as follows:  

$$
\begin{array}{r l}{\left(\underset{{\cal B}(t_{0},t_{3})}{1}\right)=}&{\left(\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{1}\right.\quad\cdots\quad\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{k}\right)}\ &{\times\left(\begin{array}{c}{\boldsymbol{Q}^{1}}\ {\cdots}\ {\cdots}\ {\boldsymbol{Q}^{k}}\end{array}\right)}\end{array}
$$  

where $\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}$ represents the return to the savings account investment in the ith state of time $t_{3}$ . We can write the second row as.  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}Q^{i}
$$  

Normalizing by the savings account, this becomes  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}\frac{[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)]^{i}}{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}}Q^{i}
$$  

Relabeling the risk-neutral probabilities  

$$
{\tilde{p}}_{i}=\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}Q^{i}
$$  

gives  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}{\frac{1}{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}}}{\tilde{p}}_{i}
$$  

Thus, we obtain the pricing equation for the $t_{3}$ maturity bond as:  

$$
B(t_{0},t_{3})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

Proceeding in a similar way, we can obtain the pricing equations for the two remaining bonds:  

$$
\begin{array}{r}{B(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}}\left[\cfrac{1}{\left(1+L_{t_{0}}\right)}\right]\qquad}\ {B(t_{0},t_{2})=E_{t_{0}}^{\tilde{P}}\left[\cfrac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)}\right]\qquad}\end{array}
$$  

The first equation is trivially true, since $L_{t_{0}}$ is known at time $t_{0}$  

# 13.3.3 OBTAINING THE BDT TREE  

In this particular example, we have three benchmark prices and two volatilities. This gives five equations:  

$$
B(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)}\right]
$$  

$$
B(t_{0},t_{2})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)}\right]
$$  

$$
B(t_{0},t_{3})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

$$
\operatorname{Vol}\left(L_{t_{1}}\right)=\sigma_{1}
$$  

$$
\operatorname{Vol}\left(L_{t_{2}}\right)=\sigma_{2}
$$  

Once we specify a model for the dynamics of $L_{t_{i}}$ , we can solve these equations to obtain the arbitrage-free paths for $L_{t_{i}}$  

# 13.3.3.1 Specifying the dynamics  

We now obtain this arbitrage-free dynamics. Following the tradition in tree models, we simplify. the notation and use the index. $i=0,1,2,3$ to denote "time,"' and the letters. $u$ and $d$ to represent the up and down states at each node. First note that we have five equations and, hence, we can at most, get five pieces of independent information from these equations. In other words, the specified dynamic must have at most five unknowns in it. Consider the following three-period binomial tree:  

$$
\begin{array}{r}{L_{0}\overset{\textbf{\emph{L}}_{1}^{u u}\phantom{\\\\[\textbf{\emph{L}}_{2}^{u u}]}}{\phantom{\nabla_{L_{1}^{d}}\times}}L_{2}^{u d}}\ {\phantom{m m m m m m}\:L_{1}^{d}\phantom{m m m m m}\:\bigwedge_{L_{2}^{d u}}}\end{array}
$$  

The dynamic has seven unknowns, namely $\{L_{0},L_{1}^{u},L_{1}^{d},L_{2}^{u d},L_{2}^{d u},L_{2}^{d d},L_{2}^{u u}\}$ . That is two more than the number of equations we have. At least two unknowns must be eliminated by imposing additional restrictions on the model. These will come from the specification of variances, as we will now see.  

# 13.3.3.2 The variance of L;  

The spot LIBOR rate $L_{i},i=0,1,2$ has a binomial specification. This means that at any node, the spot rate can take one of only two possible values. Thus, the percentage variance of $L_{i}$ conditional on state $j$ at "time" $i$ , is given by13  

$$
V a r(L_{i}|j)=E\tilde{P}[\ln(L_{i})-\ln(\overline{{L}}_{i})^{2}|j]
$$  

where  

$$
\mathrm{~l~n~}\left.\overline{{L}}_{i}=E\tilde{P}[\ln(L_{i})|j]\right.
$$  

is the conditional expected value of $L_{i}.$  

We now make two additional assumptions. The first assumption is for notational purposes only We let $j=u$ , and hence assume that we are in an "up"' state. The outcome for $j=d$ will be similar.  

Second, we let  

$$
\begin{array}{c c}{{\displaystyle p_{i}^{u}=\frac{1}{2}}}&{{\forall i}}\ {{}}&{{}}\ {{\displaystyle p_{i}^{d}=\frac{1}{2}}}&{{\forall i}}\end{array}
$$  

That is to say, we assume that the up-and-down risk-neutral probabilities are constant over the life of the tree and that they are equal. We will see that this assumption, which at first may look fairly strong, is actually not a restriction. Using these assumptions and the binomial nature of the LIBOR rate, we can immediately calculate the following:14  

$$
\begin{array}{l}{{{\cal E}\tilde{P}[\ln(L_{i})\mid j=u]=p^{u}\ln(L_{i}^{u u})+(1-p^{u})\ln(L_{i}^{u d})}}\ {{{}}}\ {{{}=\displaystyle\frac12\left[\ln(L_{i}^{u u})+\ln(L_{i}^{u d})\right]}}\end{array}
$$  

Replacing this in Eq. (13.71) gives  

$$
V a r(L_{i}\mid j=u)=E\tilde{P}\left[\left(\ln(L_{i})-\frac{1}{2}\left[\ln(L_{i}^{u u})+\ln(L_{i}^{u d})\right]\right)^{2}|j=u\right]
$$  

Simplifying and regrouping, we obtain  

$$
V a r(L_{i}\mid j=u)=\left(\frac{1}{2}\left[-\ln(L_{i}^{u u})+\ln(L_{i}^{u d})\right]\right)^{2}
$$  

This means that the volatility at time $i$ , in state $u$ , is given by  

$$
\sigma_{i}^{u}=\frac{1}{2}\mathrm{ln}\left[\frac{L_{i}^{u u}}{L_{i}^{u d}}\right]
$$  

The result for the down state will be similar:  

$$
\sigma_{i}^{d}=\frac{1}{2}\mathrm{ln}\left[\frac{L_{i}^{d u}}{L_{i}^{d d}}\right]
$$  

These volatility estimates are functions of the possible values that the LIBOR rate can take dur-. ing the subsequent period. Hence, given the market quotes on LIBOR volatilities, these formulas can be solved backward to obtain $L_{i}^{u u},L_{i}^{u d}$ . We will do this next.  

# 13.3.4 CALIBRATING THE TREE  

The elements of the tree can now be calibrated to the observed prices. Using the assumptions concerning (i) the binomial nature for the process $L_{i}$ (ii) that $p^{u}={p^{d}}=1/2$ , and (ii) that the tree is recombining, we get the following five equations:  

$$
B(t_{0},t_{1})=\frac{1}{(1+L_{0})}
$$  

$$
B(t_{0},t_{2})=\frac{1}{2}\frac{1}{(1+L_{0})(1+L_{1}^{u})}+\frac{1}{2}\frac{1}{(1+L_{0})(1+L_{1}^{d})}
$$  

$$
\begin{array}{r l}{B(t_{0},t_{3})=}&{\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{u})(1+L_{2}^{u u})}\right]+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{u})(1+L_{2}^{u d})}\right]}\ &{+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{d})(1+L_{2}^{d u})}\right]+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{d})(1+L_{2}^{d d})}\right]}\end{array}
$$  

$$
\begin{array}{l}{\displaystyle\frac{1}{2}\mathrm{ln}\left[\frac{L_{1}^{u}}{L_{1}^{d}}\right]=0.15}\ {\displaystyle\frac{1}{2}\mathrm{ln}\left[\frac{L_{2}^{u u}}{L_{2}^{u d}}\right]=0.20}\end{array}
$$  

Of these equations, the first and second are straightforward. We just applied the risk-neutral. measures to price the benchmark bonds. When weighted by these probabilities, the values of future payoffs discounted by the LIBOR rates become Martingales and hence, equal the current price of. the appropriate bond, see Figure 13.1.  

![](9fe599e38ae9690b7fd7156550afc9deb9ef8f4d2cc2d25b76d79b4c1af2d9f4.jpg)  

# FIGURE 13.1  

LIBOR rates and present value of future payoffs.  

The third equation represents the pricing function for the bond that matures at time $t=3$ . It is interesting to see what it does. According to the tree used here, there are four possible paths the LIBOR rate can take during $t=0$ , 1, 2. These are  

$$
\begin{array}{l}{{\{L_{0},L_{1}^{u},L_{2}^{u u}\}}}\ {{}}\ {{\{L_{0},L_{1}^{u},L_{2}^{u d}\}}}\ {{}}\ {{\{L_{0},L_{1}^{d},L_{2}^{d u}\}}}\ {{}}\ {{\{L_{0},L_{1}^{d},L_{2}^{d u}\}}}\ {{}}\end{array}
$$  

Due to the way probabilities,. $p^{u}$ and $p^{d}$ , are picked in this model, each path is equally likely to occur. This gives the third equation..  

The last two equations are simply the volatilities at each node. We see that as the volatilities depend only on the time index. $i,$  

$$
\begin{array}{l}{\displaystyle\frac{1}{2}\mathrm{ln}\left[\frac{L_{2}^{u u}}{L_{2}^{u d}}\right]=0.20}\ {\displaystyle\frac{1}{2}\mathrm{ln}\left[\frac{L_{2}^{d u}}{L_{2}^{d d}}\right]=0.20}\end{array}
$$  

which means that  

$$
L_{2}^{u u}L_{2}^{d d}=L_{2}^{u d}L_{2}^{d u}
$$  

This adds another equation to the five listed earlier and makes the number of unknowns equal. to the number of equations. Under the further assumption that the tree is recombining, we have  

$$
L_{2}^{u u}L_{2}^{d d}=(L_{2}^{u d})^{2}
$$  

NowEqs. $(13.81){-}(13.85)$ and (13.92)-(13.93) can be solved for the seven unknowns $\{L_{0},L_{1}^{u},L_{1}^{d},L_{2}^{u u},L_{2}^{d u},L_{2}^{u d},L_{2}^{d d}\}$  

The simplest way to solve these equations is to start from $i=0$ and work forward, since the system is recursive. It is trivial to obtain $L_{0}$ from the first equation. The second and fourth equations give $L_{1}^{u},L_{1}^{d}$ , and the remaining three equations give the last three unknowns. There is one caveat. The system of equations $(13.81){-}(13.85)$ is not linear. Hence, a nonlinear hill-climbing solution procedure must be used to determine the unknowns.  

# EXAMPLE  

The situation is shown in the figure below. There are three periods. Hence, we have three. discounts given by the corresponding zero-coupon bond prices and three volatilities. The first volatility is zero, since we do know the value of. $L_{0}$  

The system in Eqs. (13.81)-(13.85) can be solved recursively. First, we solve for $L_{0}$ then for $L_{1}^{u}$ and $L_{1}^{d}$ , and last for the time $t=2$ LIBOR rates. The nonlinear equations solved using Mathematica yield the following results:  

$$
L_{0}=5.26\%\begin{array}{l l}{{\longrightarrow L_{1}^{u}=6.39\%\displaystyle{\longrightarrow}\longleftarrow\ell_{2}^{u u}=11.8\%}}\ {{\longrightarrow L_{1}^{d}=4.73\%\displaystyle{\longrightarrow}\ell_{2}^{u d}=L_{2}^{d u}=9.7\%}}\ {{\longrightarrow L_{2}^{d d}=5.3\%}}\end{array}
$$  

We now discuss how BDT trees that give arbitrage-free paths for LIBOR rates or other spot rates can be used.  

# 13.3.5 USES OF THE TREE  

Arbitrage-free trees have many uses. (i) We can price baskets of options written on the LIBOR rates $L_{i}$ . These are called caps and floors and are very liquid. (ii) We can use the tree to price swaps and related derivatives. (ii) Finally, we can use the tree to price forward caps, floors, and swaps. We discuss one example below.  

# 13.3.5.1 Application: pricing a cap  

A caplet is an option written on a particular LIBOR rate $L_{t_{i}}$ . A cap rate, $L_{K}.$ is selected as a strike price, and the buyer of the caplet is compensated if the LIBOR rate moves above $L_{K}$ see Figures 13.2 and 13.3. The expiration date is $t_{i}.$ and the settlement date is $t_{i+1}$ . A caplet then "caps" the interest cost of the buyer. A sequence of consecutive caplets written on $L_{t_{i}},L_{t_{i+1}},...,L_{t_{i+\tau}}$ forms a $\tau$ period cap. Similarly, a sequence of consecutive floorlets forms a floor. An interest rate floor is a derivative contract in which the buyer receives payments at the end of each period in which the interest rate is below the agreed strike price.  

Suppose we have the following caplet to price:  

The $t_{i}$ are such that $t_{i}-t_{i-1}=12$ months. At time $t_{2}$ the LIBOR rate $L_{t_{2}}$ will be observed. A notional amount $N$ is selected at time $t_{0}$ Let it be given by  

$$
N=\mathbb{S}1\mathrm{million}
$$  

![](328a8ce0a1d3e1d1938c65d4b3b20edf1cd56478b3c0c88d173a4eaad775f54e.jpg)  

# FIGURE 13.2  

Caplet payoff.  

![](37b093cae75fa9d96fa771d7a5de825a6782778b327440dac1860a2402429b27.jpg)  

# FIGURE 13.3  

Floorlet payoff.  

If the LIBOR rate $L_{t_{2}}$ is in excess of the cap rate $L_{K}=6.5\%$ , the client will receive payoff:  

$$
C(t_{3})=\frac{N\big(L_{t_{2}}-L_{K}\big)}{100}
$$  

at time $t_{3}$ . Otherwise the client is paid nothing.  

For this "insurance," the client pays a premium equal to $C(t_{0})$  

The question is how to determine an arbitrage-free value of the caplet premium $C(t_{0})$ . The fundamental theorem says that the expected value of the expiration date payoff, discounted by the risk-free rate, will equal $C(t_{0})$ if we evaluate the expectation using the risk-neutral probability. That is to say, remembering that we have $\delta=1$  

$$
C(t_{0})=E_{t_{0}}^{\tilde{P}}\left[\frac{C(t_{3})}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

with expiration payoff  

$$
C(t_{3})=N\operatorname*{max}\left[\frac{\left(L_{t_{2}}-L_{K}\right)}{100},0\right]
$$  

The pricing of the caplet is done with the BDT tree determined previously. In the example, the tree had four possible trajectories, each occuring with probability 1/4. Using these we can calculate the caplet price.  

According to the BDT tree, the caplet ends in-the-money in three of the four trajectories. Calculating the possible payoffs in each case and then dividing by the discount factors, we get the. numerical equivalent of the expectation in Eq. (13.98).  

$$
C_{0}=0.25\left[\begin{array}{c}{{\displaystyle\frac{53000}{(1.0526)(1.0639)(1.118)}+\frac{144400}{(1.0526)(1.0473)(1.0793)}}}\ {{}}\ {{+\frac{14400}{(1.0526)(1.0639)(1.0793)}}}\end{array}\right]
$$  

$$
=\$16,587
$$  

We should emphasize that under these circumstances the discount factors are random variables. They cannot be taken out of the expectation operator. Also, the center node, which is recombining and, hence, leads to the same value for $L_{2}^{u d}$ and $L_{2}^{d u}$ , still requires different discount factors since the average interest rate is different across the two middle trajectories.  

# 13.3.5.2 Some assumptions of the model  

It may be worthwhile to summarize some of the assumptions that were used in the previous discussion.  

The BDT approach is an example of a one-factor model, since the short rate, here represented by the LIBOR rate $L_{i},$ is assumed to be the only variable determining bond prices. This means that bond prices are perfectly correlated.   
The distribution of interest rates is lognormal in the limit.   
We made several simplifying assumptions concerning the framework. There were neither taxes, nor any trading costs.  

Needless to say, the procedure also rests on the premise that the original data are arbitrage-free.  

# 13.3.5.3 Remarks  

The BDT approach may be considered simplistic. Yet, until the advent of the Forward LIBOR Model that we will introduce in the next chapter, market professionals preferred to stay with the BDT approach given the more sophisticated alternatives. A simple model may not fit reality. exactly, but may have three important advantages.  

1. If the model depends on few parameters, then few parameters have to be determined and the. chance of error is less..   
2. If the model is simple, a trader or risk manager will accumulate some personal experience in how to adjust for weaknesses of the model..   
3. Simple models whose weaknesses are well known and well tried may be better than more sophisticated models with no track record..  

We will see that another model with known weaknesses, namely the Black-Scholes model, is preferred by traders for similar reasons.  

# 13.3.6 REAL-WORLD COMPLICATIONS  

The BDT model as used in the previous example is, of course, based on symbolic parameters, such as two states, readily available pure discount bond prices, and so on. And as mentioned earlier, it rests on several restrictive assumptions.  

In a real-world application, the following additions to the example discussed above need to be made. (i) Day-count conventions need to be checked and corrected for, (ii) settlement may be done at time $t=2$ , then further discounting may be needed from $t=3$ to $t=2$ , and (ii) in market applications, caps consisting of several caplets instead of a single caplet are priced.  
