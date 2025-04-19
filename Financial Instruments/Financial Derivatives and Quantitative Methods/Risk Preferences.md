---
title: Risk Preferences
tags:
  - hedging
  - portfolio_risk
  - risk_aversion
  - risk_preferences
  - utility_theory
aliases:
  - Investor Preferences
  - Risk Assessment
  - Riskiness
key_concepts:
  - Hedging risk with assets
  - Investor portfolio risk
  - Risk aversion notions
  - Total vs partial payoffs
  - Utility theory
---

 #Risk_Preferences

# Risk Preferences

These notes explore the conceptual tools that help investors in assessing the “riskiness" of their portfolios. We ask: Given two assets or portfolios $A$ and $B$ can we say which one is “riskier"? This turns out to be closely linked to the more general question of “"[[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]". We ask: If an investor has the choice between two mutually exclusive portfolios,  $A$ and $B$，which of these two portfolios does he prefer? Can we specify certain general patterns of investment choice,  whereby all “sensible”investors can be expected to prefer $A$ over $B$ if $A$ has certain well-defined properties relative to $B$ .For historical reasons,  this whole area of investigation is called utility theory — we ask,  what [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]s will give the highest “utility” to an investor if all investor's have similar preferences.

As a special application of this kind of query,  we can then assess relative riskiness. Given a choice between two mutually exclusive portfolios $A$ and $B$ ,  both having the same expected payoffs (average payoffs),  which of these portfolios will a“risk-averse” investor choose? We will explore three different notions of risk aversion that help answering such questions: (i) preference for certainty; (ii) variance aversion; (iii) stochastic dominance.

Keywords: Roy's Safety First Rule,  Value at Risk,  Domar-Musgrave Risk Measure,  Conditional Value at Risk,  Variance and Semi-Variance,  Lower Partial Moments,  Coherent risk Measures,  Risk Aversion,  Risk Premia,  1st and 2nd order stochastic dominance

Reading: Chapter 18 from Hull as a supplement to these notes.

# 1 Background

This introductory section positions the topic of “[[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]”within the wider context of the course and sorts out a few preliminary issues.

Partial vs Total Payoffs: Investors buy various individual assets and combine these assets into overall portfolios. An investor cannot form a portfolio unless he is willing to purchase the individual assets out of which it is composed,  but these individual assets are relevant to the investor only insofar as they contribute to the payoff profile of the overall portfolio of which they are a part. Ultimately,  the investor ends up with one particular portfolio rather than any other portfolio,  and his final income will then be given by the payoffs of this particular portfolio.

If we wish to stress that we are talking about the investor's ultimate overall portfolio,  we talk of the “total payoffs” of the investor's overall portfolio (as opposed to the partial payoffs coming from individual assets),  and we speak of “mutually exclusive investments" that are open to the investor (each of which offering an alternative “total payoff” to the investor)

Using assets to hedge risk: It is important to make the distinction between the riskiness of an asset and its value. The value of an individual asset depends on the relationship between the payoffs of that asset and the payoffs of the other assets in the investor's overall portfolio. Thus it is possible for an individual asset to be very risky and yet to be very desirable; an asset is desirable if its risky payoffs are anti-correlated with the payoffs of the other assets in the investor's overall portfolio. Such anti-correlated assets provide the opportunity to hedge risk and allow the investor to reduce the risk of his/her overall portfolio. Investors may not wish to hold such hedging assets in isolation,  but they may wish to hold them as one component of their overall portfolios.

Hedging is a very important part of understanding how derivative securities and financial instruments are priced. We will see that the use of hedging assets can offset risk completely and allow the price of derivatives to be determined by relatively simple formulas

Overall Income Risk: Stochastic Dominance: The present handout is concerned with another question. Here we no longer ask the question “How well does the riskiness of this particular individual asset combine with the riskiness of the other assets in the investor's portfolio?". Instead,  we present the investor with a range of various complete or overall portfolios neither of which may be altered,  and ask the investor to choose one of them,  reject all others,  and subsequently live with the payoffs from the one portfolio that he has chosen. Thus we ask: “How does the riskiness of one particular overall portfolio (to which no further assets may be added) compare with the riskiness of some other,  alternative such portfolio?". We ask: when given the choice between two mutually exclusive overall portfolio payoffs,  which one does the investor regard as riskier (and hence less desirable) than the other?

How desirable is one overall portfolio compared with another? If investors are “risk-averse”,  then they will prefer “less risky” over “more risky” portfolios with the same average payoffs. What does it mean that a portfolio is "less risky" than another? There are a number of possible answers to this question and we will consider some of the alternatives that have been proposed. The concept of (second-order) Stochastic Dominance defined below is however. The most important as it gives a theoretically rigorous answer. If portfolio $A$ stochastically dominates portfolio $B$，then all “risk-averse” investors are well advised to prefer $A$ over $B$ ;they should choose portfolio $A$ and reject portfolio $B$ .This however,  does depend on what is meant by “risk-averse" and this we will consider later.

## 2 Preliminaries

In this section we set up the formal framework,  specify a concrete example,  and perform various preliminary computations for this example. Later sections will then offer formal definitions of investor preferences and refer back to the example from the present section.

Risky Investments: We consider an investor with a single-period time horizon. The investor has the choice between a number of mutually exclusive investments,  $A,   B,   C,    \ldots$ The payoffs of these investments depend on the state of the world. When deciding on his investment,  the investor does not know which of the various possible states of the world will come about payoffs are risky. However the investor knows the relative likelihood (probability) of each state and hence is capable of computing the expected value variance and [[Lecture 1- Probability Distributions of Returns|probability distribution]] of each asset

The Choice Problem: At the beginning of the period the investor chooses one of the available investments. He is then tied to the particular investment he has chosen and his end-of-period income will consist entirely of the payoffs from his chosen investment. How large will his income be? That depends on the state of the world during the period,  which cannot be foreseen at the beginning of the period but which can be analysed in terms of likelihoods ([[Lecture 1- Probability Distributions of Returns|probability distribution]]s).

When comparing any two of the various available investments,  the investor needs to ask himself: which of these two would I rather have? In answering this question,  the investor will take account of the knowledge he has about payof profiles of these investments. We consider the following concepts in assessing a payoff profile: expected payoffs,  variance of payoffs,  worst-case payoffs,  and “dispersion" of payoffs. Later we will use these concepts to declare precise definitions of risk aversion that reflect the choices of a reasonable investor

Example: By way of example,  we consider an economy with eight states of the world. For simplicity,  all eight states are equally likely,  so that the probability of state $i$ is $f_{i}=\frac{1}{8}$ (for $i=1,    2,    \ldots 8$ ). We consider the following six mutually exclusive investments

$$A=\begin{pmatrix}9\\9\\9\\9\\9\\9\\9\\9\end{pmatrix};\:B=\begin{pmatrix}11\\11\\11\\11\\11\\9\\9\\9\end{pmatrix};\:C=\begin{pmatrix}10\\10\\10\\10\\10\\10\\10\\10\end{pmatrix};\:D=\begin{pmatrix}14\\13\\12\\11\\9\\8\\7\\6\end{pmatrix};\:E=\begin{pmatrix}18\\16\\14\\12\\12\\8\\6\\4\\2\end{pmatrix};\:F=\begin{pmatrix}11\\11\\11\\11\\11\\11\\11\\11\\3\end{pmatrix}.$$

Casual inspection of these six investments reveals that $A$ and $C$ are riskfree,  all others are risky. We will be particularly interested in studying and comparing $D$，$E$ and $F$

State-wise dominance: We say that investment $X$ state-wise dominate investment $Y$ if $X$ pays more than $Y$ in at least one of the states and not less than $Y$ in any other state. Investment $X$ then is the dominating investment and $Y$ “"is dominated” (by $X$ ). Weshall write $X\geq Y$ for shorthand.

In our example,  $B$ dominates $A$ ,  since it pays 2 extra in states 14 and the same as $A$ in states 5-8. Likewise,  $C$ dominates $A$ .No other investment dominates any other. For instance,  $D$ does not dominate $E$ since it pays less than $E$ in states 1-4. In general,  if two investments have the same expected payoffs,  neither will dominate the other,  since any extra payoff in one of the states must be compensated by shortfalls in some of the other states.

Probability Distributions: To determine how risky a portfolio or asset is,  we will need to know the [[Lecture 1- Probability Distributions of Returns|probability distribution]]s of its payoffs.

An asset or portfolio will result in $Tl$ possible financial outcomes (sums of money or returns),  $x_{1},   x_{2},    \cdots,   x_{n}$ .We shall denote the probability of outcome

ILi by $f_{i}$ .If the portfolio is risky then for at least one value ${\mathcal L}_{i}$ ,  the probability satisfies $0<f_{i}<1$ .In this case we can think of the outcome $iL$ as a random variable taking on the values $x_{1},   x_{2},    \ldots,   x_{n}$ so that

$$f_i=\mathrm{Prob}(x=x_i).$$

From the example we see that $Tl$ can be less than the number of states. So for example portfolio $F$ has $n=2$ with $x_1=3$，$x_{2}=11$ 1 The probability mass function $f (x_{i})$ of an investment assigns to each possible payoff $\mathcal{L}_{i}$ of the investment its relative likelihood or probability. The value $f_{i}=f (x_{i})$ of the mass function is the likelihood that the investment will have a payoff of iLi pounds. We find the value of $f (x_{i})$ by summing over the likelihoods of all those states where the investment pays exactly ${\mathcal{L}}_{i}$ pounds. In our example,  for all six investments,  their state-specific payofs lie somewhere between 1 and 20,  and thus we may consider the relevant range of $X$ to be the interval [1,  20],  for all mass functions. For the risk-free investment $A$ ; payoff $x=9$ occurs always and all other payoffs occur never,  and thus we have

$$f^a (9)=1;\quad f^a (x)=0\text{for all other}\:x.$$

Likewise for $C$

$$f^c (10)=1;\quad f^c (x)=0\text{for all other}\:x.$$

What about the mass functions of the risky investments? For $B$ .we find that it pays 9 in four out of eight states,  11 in the other four states. Since all states are equally likely,  this means that

$$f^b (9)=\frac 12,    \quad f^b (11)=\frac 12,    \quad f^b (x)=0\text{for all other}\:x.$$

Likewise for $D$，$E$ and $F$ .Wehave

$f^{d}(x)=\frac{1}{8}$ for $x= 6,   7,   8,   9,   11,   12,   13,   14;$ $f^{d}( x) = 0$ for all other $2 L$ $f^{e}(x)=\frac{1}{8}$ for $x= 2,   4,   6,   8,   12,   14,   16,   18;$ $f^{e}( x) = 0$ for all other $3 L$
$$f^f (x)=\frac 18\text{for}\:x=3;\quad f^f (x)=\frac 78\text{for}\:x=11.$$

In some circumstances we will also think of $JL$ as a continuous variable taking on any value in some range $[a,   b]$ .In that case $f (x)$ is a continuous function and is known as a probability density function

Probability Mass Function: It is instructive to draw the histograms for the mass functions of the various investments,  with payoffs on the horizontal axis and probabilities on the vertical axis. Here we show $C$ with $D$ $D$ with $E$ and $D$ with $F$

Exercise: Draw the probability mass functions.

Cumulative Probability Functions: The cumulative probability func tion gives the probability that the payoff is less than or equal to a particulan value. We shall denote the cumulative probability by

$$F_i=F (x_i)=\mathrm{Prob}(x\leq x_i).$$

For a discrete distribution we haye

$$F (x_i)=\sum_{j=1}^if_j$$

And for a continuous distribution we have

$$\begin{aligned}F (x)=\int_a^xf (t)\: dt.\end{aligned}$$

The cumulative [[Lecture 1- Probability Distributions of Returns|probability distribution]] $F (x)$ is the area below the probability density function $f (t)$ below the value of $JL$

Exercise: Draw the cumulative probability functions

Expected Payoffs: As a first measure of investment performance,  we are interested in the average payofs (expected payoffs) of an investment. The expectedpayoffs of the risk-free investments are simply their fixed payoffs:

$$\operatorname{E}[A]=9;\quad\operatorname{E}[C]=10.$$

For the other investments,  we recall that all states are equally likely,  hence we merely need to sum over all payoffs and divide by the number of states:

$$\mathrm{E}[B]=\frac{11+11+11+11+9+9+9+9}{8}=10;$$

$$\mathrm{E}[D]=\frac{14+13+12+11+9+8+7+6}{8}=10;$$

$$\mathrm{E}[E]=\frac{18+16+14+12+8+6+4+2}{8}=10;$$

$$\operatorname{E}[F]=\frac{11+11+11+11+11+11+11+3}{8}=10.$$

Thus,  all investments except $A$ have the same average payoffs of 10. On this measure,  the five investments $B$ $F$ are all equally desirable.

Deviations: How large are the deviations of actual payofs from the mean? For the risk-free investments ( $A$ and $C$ ),  deviations are zero in all states. For the others,  we have：

$$\Delta B=\begin{pmatrix}+1\\+1\\+1\\+1\\-1\\-1\\-1\\-1\end{pmatrix};\:\Delta D=\begin{pmatrix}+4\\+3\\+2\\+1\\-1\\-2\\-3\\-4\end{pmatrix};\:\Delta E=\begin{pmatrix}+8\\+6\\+4\\+2\\-2\\-4\\-6\\-8\end{pmatrix};\:\Delta F=\begin{pmatrix}+1\\+1\\+1\\+1\\+1\\+1\\+1\\-7\end{pmatrix}.$$

A quick calculation shows that each of these deviations has an average of zero;

$$\mathrm{E}[B]=\mathrm{E}[D]=\mathrm{E}[E]=\mathrm{E}[F]=0,    $$

Confirming that on average,  the positive and negative deviations cancel each other out.

Casual inspection of these deviations shows that $E$ tends tohave much larger deviations than the other investments. $F$ had mostly small positive deviations but one fairly large negative one (in the last state),  whereas $D$ has variable deviations that are smaller than those of $E$ but never as large as the largest (negative) one from $F$

Variance: Varianceis the average of the squared deviations,  and as such it is an important summary measure of risk.

$$\Delta B^2=\begin{pmatrix}1\\1\\1\\1\\1\\1\\1\\1\\1\end{pmatrix};\:\Delta D^2=\begin{pmatrix}16\\9\\4\\1\\1\\4\\9\\16\end{pmatrix};\:\Delta E^2=\begin{pmatrix}64\\36\\16\\4\\4\\16\\36\\64\end{pmatrix};\:\Delta F^2=\begin{pmatrix}1\\1\\1\\1\\1\\1\\1\\49\end{pmatrix}.$$

Hence,

$$\mathrm{Var}[B]=\mathrm{E}[\Delta B^{2}]=\frac{1+1+1+1+1+1+1+1}{8}=\frac{8}{8}=1;$$

$$\mathrm{Var}[D]=\mathrm{E}[\Delta D^2]=\frac{16+9+4+1+1+4+9+16}{8}=\frac{60}{8}=7.5;$$

$$\mathrm{Var}[E]=\mathrm{E}[\Delta E^{2}]=\frac{64+36+16+4+4+16+36+64}{8}=\frac{240}{8}=30;$$
$$Var[F] = E[△F² = 1+1+ 1 +1 +1 + 1 + 1+ 49 56 = 7]$$

This we find that on average,  as expected $E$ has the largest deviations,  but $F$ has a smaller average deviation than $D$ ,  despite having one very large negative deviation in the last state. Based on this measure. Investment $F$ is

The most desirable of the last three investments,  closely followed by $D$，and then much later by. $E$

### Worst-case Payoffs

If your life income depends exclusively on one particular investment,  you will not just be interested in the average payoffs and average risk of that investment but you will also be interested in the actual payoffs in the various states. Ultimately,  you will receive one of these actual payoffs,  rather than the average payoff. In particular,  you will want to to know: What is the lowest possible payoff of my investment? This is the “worst-case” payoff Worst-case payoffs are the payoffs which have the largest negative deviation from the mean.

In our example,  the worst-case payoffs are 9 for $A$，9 for $B$，10 for $C$ 6 for $D$，2 for $E$，3 for $F$ .We note that for a risk-free investment,  worst-case payoffs are always equal to average payoffs,  since for risk-free investments. Payoffs are the same in all states and all deviations are zero.

## 3 Measures of Risk

We now want to ask the question whether risk can be quantified and whether the riskiness of various investments can be compared. We shall give a qualified and subtle yes to this question. It is possible to make comparisons between the riskiness of some pairs of portfolios but not others. Thus we shall have a partial ordering of portfolios according to their riskiness. Before proceeding we shall consider various measures of risk which have been considered in the literature

## Roy's Safety First Rule

Roy in a classic paper² proposed the following measure of risk

$$\rho_R=\mathrm{Prob}(x\leq\hat{x}).$$

This gives the probability that the outcome is less than some critical or disas ter level $\hat{x}$ and thus the risk measure $\rho_{R}$ measures the probability of disaster. Roy's risk measure is also known as the shortfall probability. The safety-first principle is then to choose a portfolio that minimises this probability of disaster. For a continuous distribution the Roy measure is simply the cumulative probability at $\hat{x}$
$$\rho_R=F (\hat{x})=\int_{x_{min}}^{\hat{x}}f (x)\: dx.$$

An upper bound can be found for this probability. Letting

$$\mu=\int xf (x)\:dx$$

Denote the mean of thedistribution and

$$\sigma^2=\int (x-\mu)^2\:dx$$

Denote the variance of the distribution,  it can be shown by Chebycheff's inequality that
$$\rho_R=F (\hat{x})\leq\frac{\sigma^2}{(\mu-\hat{x})^2}.$$

Roy suggested that if the entire distribution is not known then choosing the investment portfolio which minimised the ratio $\sigma^{2}/(\mu-\hat{x})^{2}$ would be desirable. Or equivalently the portfolio which maximised the square-root of the inverse. Taking $\hat{x}$ to be the risk-free payoff $T$ Roy would suggest choosing the portfolio which maximised $(\mu-r)/\sigma$ would be desirable. This later is

Just the reward to variability or Sharpe ratio introduced by Sharpe (1966) 3 which is widely used by professional investors

One problem with Roy's measure is that it looks only at probabilities and not the size of the loss. Thus suppose that there are two portfolios and take $\hat{x}=0$ so that any negatifs are positive. Roy's index is higher for portfolio $B$ though arguably portfolio $A$ is potentially more disastrous

### Value at Risk

Value at Risk (VaR) is the inverse of Roy's risk measure. Whereas Roy's measure asks what is the probability of a loss below a particular level $\hat{x}$ ,  VaR determines the value $\hat{x}$ such that the portfolio will suffer a loss of more that $\hat{x}$ with a given probability. It is usual to fix the probability of loss at $1\%$ or $5\%$ and calculate the return distribution say for one day so that the VaR measures the minimum loss likely to be suffered on 1 or 5 of the next 100 trading days. Using the cumulative distribution function we have

$$\alpha=F (VaR)$$

Or

$$VaR=F^{-1}(\alpha).$$

As with Roy's measure there are some problems with the use of VaR as a measure of risk. It only considers the distribution in the lower tail and will therefore ignore differences in the distribution above the VaR threshold. The VaR measure is not sub-additive which means that the it may be possible

<table>
	<tbody>
		<tr>
			<th>Prob</th>
			<th>$A$</th>
			<th>$B$</th>
			<th>$A+E$</th>
		</tr>
		<tr>
			<td>0.03</td>
			<td>-9</td>
			<td>1</td>
			<td>-8</td>
		</tr>
		<tr>
			<td>0.94</td>
			<td>1</td>
			<td>1</td>
			<td>2</td>
		</tr>
		<tr>
			<td>0.03</td>
			<td>1</td>
			<td>9</td>
			<td>-8</td>
		</tr>
		<tr>
			<td>VaR$( 5\%$</td>
			<td>-1</td>
			<td>1</td>
			<td>8</td>
		</tr>
	</tbody>
</table>

Table 1: VaR is not sub-additive

To combine two assets or portfolio and increase the VaR. Table 1 shows two portfolios $A$ and $B$ and calculates the VaR at the $5\%$ level for each. Since the probability of any loss is $3\%$，the maximum value of the portfolio in the lowest $5\%$ of the distribution is 1 in both cases. Thus VaR,  which is the loss at risk is negative for both portfolios. However combining the two portfolios produces a $6\%$ probability of a loss of 8 and thus the VaR at the $5\%$ level is 8. This shows that combining two portfolios can increase the VaR significantly. 4 Finally as we shall show the VaR can be inconsistent with second-order stochastic dominance

## Domar-Musgrave Risk Index

Domar and Musgrave? Proposed a measure of risk that measures the expected value of returns less than the returns on a risk-free investment. Letting 7 denote the return on a risk-free asset,  the Domar-Musgrave risk index is given by
$$\rho_{DM}=-\int_{x_{min}}^{r}(x-r) f (x)\:dx$$

In the caseof a continuousreturn or

$$\rho_{DM}=-\sum_{x_{i}\leq r}(x-r) f (x_{i})$$

In the discrete case. Calculating the riskindex for the three portfolios $D$，$E$ and $F$ from our example we find that

$$\rho_{DM}[D]=\frac{5}{4};\quad\rho_{DM}[E]=\frac{5}{2};\quad\rho_{DM}[F]=\frac{7}{8}.$$

It is possible to generalise the Domar-Musgrave risk index to any particular target return $\hat{x}$ which may or may not be the risk-free return. In this case the measure is also known as erpected shortfall as it measures the average return that falls short of some target return $\hat{x}$ .That is expected shortfall is measured by
$$\rho_{ES}=-\int_{x_{min}}^{\hat{x}}(x-\hat{x}) f (x)\:dx$$

In the case ofa continuousreturn or

$$\rho_{ES}=-\sum_{x_i\leq\hat{x}}(x-\hat{x}) f (x_i)$$

In the discretecase.

There are some difficulties with the Domar-Musgrave index or expected shortfall as a measure of risk too. Consider a case where the target is $\hat{x}=0$ and suppose that someportfolio $A$ hasareturn of -500 with probability 0.1 and portfolio $B$ has a return of -100 with probability 0.5 and that all other payoffs are positive (an hence do not affect the index). Then the risk index or expected shortfall for both portfolios is the same,  $\rho_{ES}[A]=\rho_{ES}[B]=50$ but perhaps many investors would regard portfolio $A$ with the potentially much larger loss as more risky.

### Conditional Value at Risk

Conditional Value of Risk (CVaR) was introduced by Rockafellar and Uryasev to overcome some of the problems that occur with using VaR as a risk

Measure. The conditional value at risk measure is related to the Domar Musgrave index. 7 Like the VaR the CVaR fixes a probability of loss and then takes the VaR as the target for the generalised Domar-Musgrave index Thus in the continuous case we have

$$CVaR=-\int_{x_{min}}^{VaR_{\alpha}}(x-VaR_{\alpha}) f (x)\: dx.$$

This is simply (minus) the expected value of the tail of the distribution below theVaR level.

## Variance and Semi-variance

Markowitz developed a mean-variance framework for [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] in. Which he argued that investors in choosing between portfolios with equal expected value should choose the portfolio with the minimum variance. 910 This work was later used by Sharpe and Lintner in developing the Capital Asset Pricing Model (CAPM). As we have seen variance is a measure of average deviation and weighs both positive and negative variations equally. In his 1959 book,  Portfolio Selection,  Markowitz suggested the idea of looking at. Semi-variance which only considers deviations below some critical threshold. Letting the threshold be $\hat{x}$ ,  the semi-variance risk measure is given by

$$\rho_{SV}=\sum_{x_i\leq\hat{x}}(x-\hat{x})^2 f (x_i)$$

For discrete distributions and

$$\rho_{SV}=\int_{x_{min}}^{\hat{x}}(x-\hat{x})^2 f (x)\:dx$$

For continuous distributions. Often the critical value is taken to be the mean return $\mu$ so that only deviations below the mean are taken into account. The reason for preferring the semi-variance is that the variance considers both very high and very low returns equally desirable or undesirable and therefore will choose portfolios that eliminate either extremes. The semivariance however,  concentrates only on losses and therefore portfolios chosen on the basis of semi-variance will focus on eliminating losses

Exercise: Calculate the semi-variance (using $\mu$ as the cut-off value) for the portfolios $D$，$E$ and $F$ from our example

### Lower Partial Moments

The measures we have consider so far are actually all special cases of the lower partial moments which were suggested by Fishburnll as suitable risk measures. The lower partial moments for a continuous distributions are given by

$$\rho_{LPM}^{\beta}=\int_{-\infty}^{\hat{x}}(\hat{x}-x)^{\beta}f (x)\:dx$$

For any $\beta\geq 0$ .It is easy to check that

$$\rho_{LPM}^0=\int_{x_{min}}^{\hat{x}}(\hat{x}-x)^0 f (x)\:dx=\int_{x_{min}}^{\hat{x}}f (x)\:dx=F (\hat{x})=\rho_R$$

$$\rho_{LPM}^{1}=\int_{x_{min}}^{\hat{x}}(\hat{x}-x) f (x)\:dx=-\int_{x_{min}}^{\hat{x}}(x-\hat{x}-) f (x)\:dx=\rho_{DM}$$

$$\rho_{LPM}^2=\int_{x_{min}}^{\hat{x}}(\hat{x}-x)^2 f (x)\:dx=\rho_{SV}.$$

Thus the zeroth lower partial moment (where $\beta=0$ ) is Roy's risk index,  the first lower partial moment (where $\beta=1$ ) is the expected shortfall or DomarMusgrave measure and the second lower partial moment (where $\beta=2$ ) is a semi-variance.

### Coherent Risk Measures

We have seen that several different measures of risk have been suggested There arehowever advantages and disadvantages to all these differentmea sures and no one measure is universally accepted as the best. In order to describe what might be acceptable for a risk measure a set of criteria were developed by Artzner,  Delbaen,  Eber,  and Heath 12 Consider two portfolios $A$ and $B$ ,  a measure of risk is called coherent if it satisfies the following four properties:

Subadditivity: $\rho (A+B)\leq\rho (A)+\rho (B)$

Monotonicity: if $A\leq B$ ,  then $\rho (A)\geq\rho (B)$

Positive homogeneity: if $\lambda>0$ ,  then $\rho (\lambda A)=\lambda\rho (A)$

Translation invariance: for any number 7772，$\rho (A+m)=\rho (A)-m$

We'll consider the rationale for each of these axioms. Subadditivity has an easy interpretation. If the subadditivity did not hold,  then $\rho (A+B)>$ $\rho (A)+\rho (B)$ .This would imply,  for instance,  that in order to decrease risk,  a firm might be motivated to break up into different incorporated affiliates or split portfolio into two separate parts. Such an artifact should not really decrease the overall risk. Monotonicity is perhaps obvious. If portfolio $A$ always has lower returns than portfolio $B$ then it ought to be defined as

Being more risky. Positive homogeneity is slightly more tricky to interpret. Subadditivity implies $\rho ( A) + \rho ( A)$ $\leq$ $2\rho ( A)$ .Taking $\lambda=2$ in thepositive homogeneity axiom then equivalent to the assumption that $\rho (A+A)\geq 2\rho (A)$ That is saying that a portfolio of $2 A$ is more risky than two portfolios of $A$ Translation invariance implies that the risk $\rho (A)$ decrease by $777 t$ ,  by adding a sure return 777. To a portfolio $A$ .The idea is that a risk measure is a measure of what kind of risk is acceptable. Thus if one adds a certain amount 100 (in every state) to the portfolio then the amount that needs to be added to this new portfolio to make it acceptable must have gone down by 100.

As we have seen some measures of risk are not coherent. For example VaR does not satisfy the assumption of subadditivity. Other measures such as Domar-Musgrave measure or expected shortfall are coherent. Nevertheless both VaR and expected shortfall have both detractors and advocates and no one measure is universally agreed to be better than others. 13

## 4 Investor Preferences

The measures of risk we have so far considered associate with a given [[Lecture 1- Probability Distributions of Returns|probability distribution]] a single number to measure risk. As we have seen there seems no universal agreement on what is the best measure and perhaps different people can have different views of risk simply because of their preferences A question therefore to ask is whether there are situation is which everyone would agree that invest $A$ was riskier than investment $B$ .To try to answer this question we look at investor's preferences over risky investments. It offers formal definitions of risk aversion that cover many realistic cases of investment choices. We consider pair-wise comparisons of mutually exclusive investments $X$ and $Y$ and ask which of the two investments is better,

Given a list of assumptions of “reasonable” investment behaviour. We use our example from the previous section for illustration

Complete Preferences: For any pair of investments $X$ and $Y$，the individual can express a preference for $X$ over $Y$ or visa-versa or is indifferent between the two.

Transitive Preferences: For any triple of investments,  $X$，$Y$ and $Z$ ,  if $X$ is preferred to $Y$ and $Y$ is preferred to $Z$ then $X$ is preferred to $Z$

The idea behind these two assumptions is that investors can make choices. This is obvious for complete preferences. Without this assumption there will be some consequence bundles that the investor cannot compare. If they cannot compare the outcomes then the choice between portfolios leading to these outcomes becomes impossible. It is equally true that transitivity is needed to be able to choose between alternative portfolios. Without transitivity there would be a chain of preferences amongst some three consequences $X$，$Y$，$Z$ such that $X$ is preferred to $Y$ and $c^{\prime}$ is preferred to $Z$ and $Z$ is preferred to $X$ In these circumstances it is impossible to say which consequence investment is the best

Non-satiation: We say that an investor is non-satiated if he prefers a dominating investment over a dominated one. In most work in theoretical fi nance,  we assume that all investors are non-satiated. This assumption makes sense,  since payoffs are made in cash and cash can be spent on a wide range of different consumption goods and any unwanted cash can be discarded at almost no cost (“free disposal"). The assumption of non-satiation is useful when making comparisons of investments that are at different average payoff levels,  but it does not let us decide between investments that have the same expected payoffs but different risk profiles. For those cases we need more specific risk assumptions

Risk Aversion I[Preference for Certainty]: We say that an investor has “preference for certainty” and is risk averse if a risk-free investment is preferred over a risky investment of equal expected payoffs

In our example,  if a risk-averse investor is given the choice between $C$ and $D$ ,  say,  he will choose $C$ since $C$ has the same expected payoffs as $D$ but no risk. We note that this definition of risk aversion does not require us to make judgements between different risky investments; we merely compare one risky investment with one risk-free investment of equal expected payoffs. "Preference for Certainty” is a very plausible assumption that is pretty much universally adopted in finance. However,  it is too weak to help us decide on choices between two risky investments,  such as $D$ and $E$ . For those choices we need more specific assumptions.

A diagrammatic way to represent preferences is to use indifference curves. Suppose there are just two states. Let the horizontal axis represents the amount of cash in state 1 and the vertical axis represents cash in state 2. Choose a particular investment $X$ .A line is drawn through the point $X$ which corresponds to all the other possible consequences of investments $Y$ which are indifferent to $X$ . This set of points $I (X)$ is called the indifference curve. Indifference curves cannot cross by the assumption of transitivity and because of the assumptions of monotonicity and transitivity the indifference curve is "thin” and downward sloping. All the points above the indifference curve belong to the weak preference set $WP (X)$ which represents all the points that are either preferred to or are indifferent to $X$

The slope of the indifference curve shows how much extra is required in state 2 to compensate the individual for a one unit decrease in the amount received in state 1. This amount is called the marginal rate of substitution. $MRS (X)$，is a measure of the marginal rate of substitution at $X$ .The marginal rate of substitution depends on preferences and therefore is likely to vary from one person to another even at the same consequence payoff $X$ .The ratio $q_{1}/q_{2}$ represents how much the market will compensate the individual for

Reducing the consequent payoff in state 1 by one unit. Decreasing the amount received in state 1 by one unit will save the investor $q 1$ on his investment Thus the amount extra that can be had in state 2 is $q_{1}/q_{2}$

Given our three assumptions little more can be said about indifference curves other than that they do not cross,  are thin and are downward sloping However there are some other features that we might expect preferences over uncertain outcomes to exhibit. Firstly risk aversion,  that is a desire for more certain rather than a riskier outcomes with the same expected value. 14 Secondly state independence,  that is that preferences depend on the outcome and not the state of nature per se. Thirdly separability,  that is that the preferences in one particular state are to some extent independent of the preferences in some other state that didn't actually occur

# Utility

We shall discuss the properties of risk aversion,  separability and state independence in greater detail shortly. First we consider another convenient way of representing preferences which is through a utility function. A utility function associates with each possible investment $X=(x_{1},   x_{2})$ a number $v (x_{1},   x_{2})$ such that $v (x_{1},   x_{2})>v (y_{1},   y_{2})$ if and only if $X$ is preferred to $Y=(y_{1},   y_{2})$ The only property of the utility function that is important is that it ranks consequences,  assigning a higher number to a preferred consequence. The actual size of the number is unimportant and any transformation of the function $U$ that produces the same ordering of consequences as does 2 is equally valid as a representation of preferences. Any transformation of $U$ that is an increasing function of $U$ will produce the same ranking. Therefore $U$ is said to be unique only up to a positive monotonic transformation and this representation is referred to as ordinalutility

To illustrate the ordinal nature of utility consider an example of a pref erence ranking which is the so-called Cobb-Douglas preferences

$$v (x_1,   x_2)=Ax_1^ax_2^b$$

Where $A$，$UL$ and $b$ are parameters. 15 Since $\log_{e}$ is a positive monotonic trans formation,  the alternative utility function

$$\hat{v}(x_1,   x_2)=\log_e (v (x_1,   x_2))=\log_e (A)+a\log_e (x_1)+b\log_e (x_2)$$

Is an equally valid representation of the same preferences.

The marginal rate of substitution is calculated by totally differentiating the utility function. Suppose there are just two states,  then totally differentiating $v (x_{1},   x_{2})$ gives

$$dv=\frac{\partial v (x_1,   x_2)}{\partial x_1}dx_1+\frac{\partial v (x_1,   x_2)}{\partial x_2}dx_2.$$

The partial derivatives are often called marginal utilities as they show how much utility is increased for a small (marginal) increase in the payoff in one state. Thus we define $MU_{1}( x_{1},   x_{2})$ = $\partial v ( x_{1},   x_{2}) / \partial x_{1}$ and $MU_{2}(x_{1},   x_{2})=$ $\partial v (x_{1},   x_{2})/\partial x_{2}$ .The marginal rate of substitution is calculated along an indifference curve where the utility does not change,  i.e.where $dv=0$ Hence
$$MRS (cx_1,   x_2)=-\frac{dx_2}{dx_1}=\frac{\frac{\partial v (x_1,   x_2)}{\partial x_1}}{\frac{\partial v (x 1,   x_2)}{\partial x_1}}.$$

Note that $MRS$ is defined to be a positive number and since theindifference curve is downward sloping,  the slope $dx_{2}/dx_{1}$ is multiplied by -1 to give a positive number. As we can see the marginal rate of substitution is the ratio of marginal utilities. In the case of Cobb-Douglas preferences the marginal rate of substitution is

$$MRS (x_1,   x_2)=\frac{\frac{a}{x_1}}{\frac{b}{x_2}}=\frac{xc_2}{bx_1}.$$

Remember that the marginal rate of substitution is slope of the indifference curve and therefore is independent of whether the utility is assigned using the function $v (x_{1},   x_{2})$ or $\hat{v}(x_{1},   x_{2})$

So far nothing has been said about probabilities in defining preferences. However the probabilities can be illustrated in a diagram. Take some point $X=(x_{1},   x_{2})$ in the diagram and suppose the probabilities of the two states are $7\pi 1$ and $7\pi 2$ where $\pi_{1}+\pi_{2}=1$ .The expected payof from this investment is

$$\mathrm{E}[X]=\pi_1 x_1+\pi_2 x_2.$$

The line of all points with the same expected value is called the fair odds line. The value $\operatorname{E}[X]$ is illustrated where the fair odds line hits the $45^{0}$ line through the origin. This is the point of certainty where the payoff is the same in both states. The slope of the line is $-\pi_{1}/\pi_{2}$ .A preference for certainty is reflected through the utility function if $v (E[X],   E[X])>v (x_{1},   x_{2})$ for $x_{1}\neq x_{2}$ .Let's consider the implications of a preference for certainty graphically in terms of the indifference curves. Consider the point where the $45^0$ line intersects the fair odds line. If there is a preference for certainty,  all points along the fair odds line must lie on a lower indifference curve that the indifference curve passing through the intersection of the fair odds line and the $45^0$ line. Thus the weak preference set $WP (E[X],   E[X])$ must lie above the fair odds line. This means that locally the indifference curve is convex to the origin or that the weak preference set is locally convex. If preferences are smooth then it implies that the marginal rate of substitution at the $45^{0}$ line is equal to the ratio of probabilities

$$MRS (E[X],   E[X])=\frac{\pi_{1}}{\pi_{2}}.$$

In this case then,  when there is a preference for certainty the indifference curve or preferences do reflect some information about the probabilities of the various states. That is if we did not know the probabilities of the states but knew an individuals preferences,  then we could infer the individual’s

Probability assessment of the states by calculating the marginal rate of substitution at the point of certainty. Note that this implies that the marginal rate of substitution along the $45^0$ line will be the same irrespective how far out along the $45^0$ line we are. The slope of the all indifference curves where they cut the $45^{0}$ line are the same

As we have mentioned in the case of financial assets where the payoffs are amounts of money,  the label of the state is likely to be unimportant. Thus we can reasonably suppose that how assets are viewed does not change if the states are simply relabelled. That is changing the name of the state from rain to shine and shine to rain should not affect how assets are viewed. 16 Indeed it is really the distribution of payoffs that matters and not how states are labelled at all. Thus we make the assumption that individuals are probabilistically sophisticated 17 and evaluate consequences simply by their distribution function. Probabilistic sophistication imposes a symmetry on preferences. Thus if points $X$ and $Y$ are on the same fair-odds line and are equal in distribution,  i.e. $x_{1}=y_{2}$ and ${:}\boldsymbol{U}_{2}=y_{1}$ then by the assumption the indifference curve through $X$ must also pass through $Y$

Expected Utility Maximization: The most common assumption about preferences is that utility is expected utility

$$v (x_1,   x_2)=pu_1 (x_1)+(1-p) u_2 (x_2)$$

Where $u_{1}(x_{1})$ and $u_{2}(x_{2})$ are the von-Neumann Morgenstern utility functions with $u^{\prime}(\cdot)>0$ and $u^{\prime\prime}(\cdot)\leq 0$ .Since $u_{1}(\cdot)$ and $u_{2}(\cdot)$ are concave functions the indifference curves in $(x_1,   x_2)$ -space are convex to the origin and thus are quasi-concave. It is typically assumed that the von-Neumann Morgenstern utility functions do not depend on the state so that $u_{1}(\cdot)=u_{2}(\cdot)$

Certainty Equivalent and Risk Aversion: The certainty equivalent. Of an investment $X$ is the value of an alternative safe investment $X^{ce}$ which

Has the same utility,

$$v (x^{ce},   x^{ce})=v (x_{1},   x_{2}).$$

Graphically the certainty equivalent is the value of the point on the $45^0$ line where it is cut by the indifference curve that passes through $(x_{1},   x_{2})$ .We can write the certainty equivalent as a function of $x_{1}$ and $x_{2}$ ,  i.e. $x^{\mathrm{ce}}(x_{1},   x_{2})$

In the case of expected utility the certainty equivalent is given by

$$x^{ce}(x_1,   x_2)=u^{-1}(\pi_1 u (x_1)+\pi_2 u (x_2)).$$

Since the inverse function $u^{-1}(\cdot)$ is an increasing monotonic transformation,  this function represents the same preferences as the expected utility function and the certainty equivalent can itself be treated as a utility function.

This property of the certainty equivalent is complectly general. Since indifference curves do not cross by the transitivity assumption,  the certainty equivalent gives the same preference ranking as the utility function itself Thus if preferred it is possible to treat the certainty equivalent as the utility function and work with the certainty equivalent. That is maximising the certainty equivalent is equivalent to maximising utility.

Risk Premia: Risk premia are a measure of how far the certainty equivalent is from the expected value. There are two alternatives to measuring this difference: the absolute difference and the relative difference.

The absolute risk premium is the amount that can be taken away from the expected value such that if this amount is received with certainty it is no worse than the original distribution. Consider the investment $X$，the absolute risk premium $\rho^{a}(x_{1},   y_{1})$ is defined by

$$v (E[X]-\rho^a (x_1,   x_2),   E[X]-\rho^a (x_1,   x_2))=v (x_1,   x_2).$$

To see how this relates to the certainty equivalent remember that

$$v (x^{ce}(x_1,   x_2),   x^{ce}(x_1,   x_2))=v (x_1,   x_2)$$

So that the absolute risk premium satisfies $\rho^{a}(x_{1},   x_{2})=E[X]-x^{ce}(x_{1},   x_{2})$ and it is a measure of the willingness to pay for certainty.

An alternative way to measure the willingness to pay for certainty is to measure the proportion 18 that can be taken away from expected value such that if this amount is received with certainty it is no worse than the original distribution. This amount is known as the relative risk premium. The relative risk premium $\rho^{r}(x_{1},   x_{2})$ and is defined by

$$v\left (\frac{E[X]}{\rho^r (x_1,   x_2)},    \frac{E[X]}{\rho^r (x_1,   x_2)}\right)=v (x_1,   x_2).$$

Since $v (x^{ce}(x_{1},   x_{2}),   x^{ce}(x_{1},   x_{2}))=v (x_{1},   x_{2})$ ,  the relative risk premium is simply the ratio of the expected value and certainty equivalent

$$\rho^r (x_1,   x_2)=\frac{E[X]}{y^{ce}(x_1,   x_2)}.$$

Diagrammatically the relative risk premium is the distance between the certainty equivalent and the expected value measured along the $45^{0}$ line.

Arrow-Pratt Theory: Arrow (Aspects of the Theory of Risk Bearing 1965) and Pratt (Econometrica,  1964) showed in the case of expected utility how the risk premium is related to the curvature of the von-Neumann Morgenstern utility function. Consider the investment $X$ with an expected payoff of $\pi x_{1}+(1-\pi) x_{2}=E[X]=w$ where $UU$ can be interpreted as initial wealth. The expected utility is $\pi u (x_{1})+(1-\pi) u (x_{2})$ .Suppose the individual pays an absolute risk premium of $\rho^{a}$ to eliminate the risk. Their utility would then be $u (E[X]-\rho^{a})$ where $\rho^{u}$ satisfies the equation

$$\pi u (x_1)+(1-\pi) u (x_2)=u (E[X]-\rho^a).$$

The risk premium is,  as before,  $\rho^{u}=w-x^{ce}$ .Some calculus using a Taylor expansion can be used to show that

$$\rho^a\approx-\frac{1}{2}\sigma^2\frac{u^{\prime\prime}(w)}{u^{\prime}(w)}$$

Where $\sigma^{2}=\pi x_{1}^{2}+(1-\pi) x_{2}^{2}$ is the variance of the portfolio. The function

$$A (w)=-\frac{u'' (w)}{u' (w)}$$

Is called the Arrow-Pratt coefficient of absolute risk aversion. It is a measure of the curvature of the utility function. By monotonicity $u^{\prime}(w)$ is positive,  so the risk premium is positive,  and the Arrow-Pratt coefficient of absolute risk aversion positive,  if the second derivative of the utility func tion $u^{\prime\prime}(w)$ is negative,  which indicates that the utility function is concave. The larger the coefficient $A (w)$ the greater the risk premium,  the greater will the individual pay to avoid the lottery and the more risk averse is the individual. It is well known that the only von-Neumann Morgenstern utility function which has a constant coefficient of absolute risk aversion is the negative exponential function

$$u (w)=-\exp^{-aw}\:.$$

It is alsopossible to define the Arrow-Pratt coefficient of relative risk aversion

$$R (w)=wA (w)$$

That corresponds to the relative risk premium. The von Neumann Morgen stern utility functions that exhibit constant relative risk aversion are of the power form
$$u (w)=\frac{w^{(1-r)}}{(1-r)}$$

With $u (w)=\log_{e}(w)$ when $r=1$ .Again it is easily checked that $R (w)=r$

## 5 Stochastic Dominance

First-order stochastic dominance: To examine stochastic dominance of two investments we look at the cumulative [[Lecture 1- Probability Distributions of Returns|probability distribution]] functions

Thus if two investments $X$ and $Y$ have cumulative distribution functions $F$ and $G$ respectively we say that $X$ first-order stochastically dominates. $Y$ if

$$F (x)\leq G (x)$$

For all possible values of $2 L$ (with strict inequality for at least one $3 L$ ). Remember that $F (x)=$prob$(X\leq x)$ so if $F (x)\leq G (x)$ then the probability of getting an outcome worse than $JL$ is always lower for $X$ than for $Y$ no matter which $. L$ we choose. We should think that most investors will prefer $X$ to $Y$ and one can show this is the case if the utility function is monotonic. Thus all investors with monotonically increasing preferences will agree that $X$ is better than $Y$

It is important to remember however that many investments will not be able to be ranked by first order stochastic dominance. For these investments $F (x)<G (x)$ for some $JL$ but $G (x)<F (x)$ for other values of $JL$ .Such investments are non-comparable according to first-order stochastic dominance Thus first-order stochastic dominance can only be used to find a partial ordering of the set of possible investment opportunities

Second-order stochastic dominance: For two investments $X$ and $Y$ with distribution functions $F$ and $G$ we say that $X$ second-order stochastically dominates $Y$ if
$$\int_{x_{min}}^xF (t)\: dt\leq\int_{x_{min}}^xG (t)\:dt$$

For all possible values of $JL$ (with strict inequality for at least one $X$ ). We can illustrate this condition by drawing the two cumulative distribution func tions. The net area between the two curves evaluated at some point $JL$ is the difference
$$\int_{x_{min}}^{x}G (t)-F (t)\: dt.$$

Taking into account positive and negative areas (negative if $G<F$ ) and this sum is required to be positive for all ${:}\boldsymbol{L}$ .Thus we must start with a positive area and if the curves ever cross the sum of the positive areas must always outweigh the negative areas that follow.

It can be shown that all investors who are risk-averse expected utility maximisers will agree that $X$ is better than $Y$ if $X$ second-order stochastically dominates $Y$ .The intuition is that with risk-aversion marginal utility is declining and thus higher weight is placed on lower return outcomes. If $X$ second-order stochastically dominates $Y$ then any positive area where $F<G$ is greater than any negative area where $G<F$ and therefore higher weight is put on the positive areas.

Thus we can conclude that every risk averse expected utility maximiser will agree that $X$ is preferable to $Y$ if $X$ second-order stochastically dominates $Y$ .Again not all investments will be comparable according to secondorder stochastic dominance so this again implies only a partial ordering of the set of all possible investments.

Stochastic Dominance and Variance: (1) If investment $X$ stochastically dominates investment $Y$ ,  then $X$ will have a lower variance and a better worst-case payoff than $Y$ .(2) However,  it is possible for $X$ to have a lower variance than $Y$ without $X$ stochastically dominating $Y$；lower variance is a necessary but not a sufficient condition for stochastic dominance.

Exercise: Compare portfolios $D$ and $E$ using the stochastic dominance criteria (first-order and second-order)

## 6 Increases in Risk

Consider the following two assets (or portfolios) $A$ and $B$ with payoffs

$$A=\begin{pmatrix}7\\4\\6\\0\end{pmatrix}\quad B=\begin{pmatrix}5\\5\\3\\3\end{pmatrix}$$

Where the four states occur with probabilities $\left( \frac {1}{6},   \frac{1}{3},   \frac{1}{4},   \frac{1}{4}\right)$ respectively. Whicl of these two assets is the riskier? The expected value of these assets are $E[A]=E[B]=4$ . The variance of the assets are $Var[A]=\frac{13}{2}$ and $Var[B]=$ 1 and it does seem reasonable to say that $A$ is riskier than $B$ as the payoffs are more spread out.

Consider the two assets $C$ and $D$ with payoffs

$$C=\begin{pmatrix}3\\3\\3\\3\\3\\3\\3\\11\end{pmatrix}\quad D=\begin{pmatrix}0\\0\\0\\0\\0\\4\\4\\4\\4\end{pmatrix}$$

Where all states occur with probability $\frac{1}{8}$ .Again $E[ C]$ = $E[ D]$ = 4 but $Var[C]=7$ and $Var[D]=4$ .In this case it seems much more arguable to conclude that $C$ is riskier than $D$ .Asset $C$ has a constant payout except in one state,  whereas $D$ has an equal chance of no payout or a slightly higher payout.

A natural way to define the concept of $A$ is "less risky than" $B$ is to suppose that $B$ is the same as $A$ plus some extra risk or "noise". To make it clear that we are dealing with assets with a random payoff,  we shall write $A$，$B$ etc. To indicate that the payoff to the assets is random.

To make this definition precise we have to consider what it means for two assets $A$ and $B$ to be equivalent and how"noise”can be defined. First consider the two assets $E$ and $F$ which have the following payoffs

$$E=\begin{pmatrix}7\\4\end{pmatrix}\quad F=\begin{pmatrix}4\\7\end{pmatrix}$$

Where both states are equally probable. These two assets are not the same,  since they pay out different amounts in different states. Nevertheless the two assets are equally risky. In both cases there is an equal chance of a payoff of either 4 or 7. In this case we write $\tilde{E}\stackrel{d}{=}\tilde{F}$ and say that the two assets are equal in distribution. This is the same as saying that investors are probabilistically sophisticated and care only about the distribution of the payoffs and not the states themselves

We have already seen that combining one asset with another can reduce the variance of the portfolioif the assets are negatively correlated. Therefore in defining "noise”we want to consider a situation that is uncorrelated with an asset $X$ .In fact we shall use a concept slightly stronger than uncorrelated,  namely mean independence. We say that a random variable $\epsilon$ is mean independent of $X$ if the the expected value of $\dot{\epsilon}$ is the same for every possible value of the random variable $X$ .That is $E_{\epsilon }[ \epsilon | X]$ = $E_{\epsilon }[ \epsilon ]$ for all possible values that $X$ can take.

Consider the the asset $B$ that has a payoff of 5 with probability $\frac{1}{2}$ and a payoff of 3 with probability $\frac{1}{2}$ .Suppose that $E$ has the followingvalues

$$\epsilon=\left\{\begin{matrix}2&\text{with probability}\frac{1}{3}\\-1&\text{with probability}\frac{2}{3}\end{matrix}\right.\quad\text{if}B=5$$

And

$$\epsilon=\left\{\begin{matrix}3&\text{with probability}\frac{1}{2}\\-3&\text{with probability}\frac{1}{2}\end{matrix}\right.\quad\text{if}B=3.$$

It is easy to calculate that $E_{\epsilon}[\epsilon|B=5]=E\epsilon[\epsilon|B=3]=0$ .Thus the mean of $t$ isthe sameindependent of the value of $B$ .Since the mean is the same independent of $B$，$E_{\epsilon}[\epsilon|B]=E_{\epsilon}[\epsilon]$ and it can be checked that

$$E_\epsilon[\epsilon]=\frac{1}{2}E_\epsilon[\epsilon|B=5]+\frac{1}{2}E\epsilon[\epsilon|B=3]=0.$$

Mean independence is weaker than independence but is stronger than uncorrelated. The implications are

$$\text{Independence}\Rightarrow\text{Mean Independence}\Rightarrow\text{Uncorrelated}$$

Remember that the two variables $X$ and $t$ are uncorrelated when $cov (X,    \epsilon)=$ $E[ X$ $\cdot$ $\epsilon ] -$ $E[ X]$ $\cdot$ $E[ \epsilon ]$ = 0 .To see that mean independence implies zero covariance note

$$E[X\cdot\epsilon]=E_{X}[E_{\epsilon}[X\cdot\epsilon|X]]=E_{X}[X\cdot E_{\epsilon}[\epsilon|X]]=E_{X}[X\cdot E_{\epsilon}[\epsilon]]=E_{X}[X]\cdot E_{\epsilon}[\epsilon].$$

Here the first equality holds by the Law of iterated expectation; the second equality holds as the expectation over $t$ is taken for each value of $X$ ;the third equality holds by mean independence,  $E_{\epsilon}[\epsilon|X]=E[\epsilon]$ ; and the last equality again holds as expectation over $X$ is taken for each value of $\epsilon$

In the example $E$ is not independent of $B$ because the distribution function for $t$ depends upon $B$ .However $B$ and $t$ are uncorrelated. This can be easily checked as
$$B\cdot\epsilon=\begin{pmatrix}6\\-3\\3\\-3\end{pmatrix}$$

With probabilities $\left (\frac{1}{6},    \:\frac{1}{3},    \:\frac{1}{4},    \:\frac{1}{4}\right)$ which gives $E[B\cdot\epsilon]=0$ .In this case the two variables $B$ and $t$ are said tobe orthogonal. Since $E[\epsilon]=0$ the covariance is zero and $B$ and $t$ are uncorrelated

In comparing the risk of two assets or portfolios $X$ and $Y$ we wish to compare variability or deviationfrom the mean rather than the levels of the variable. Therefore we compare the deviations $X-E[X]$ and $Y-E[Y]$ Therefore the standard definition for “riskier than" is as follows:

Risk: The asset or portfolio $Y$ is riskier than the asset or portfolio $X$ if there is a random variable $\epsilon$ such that

$$\tilde{Y}-E[\tilde{Y}]\stackrel{d}{=}\tilde{X}-E[\tilde{X}]+\tilde{\epsilon}\quad\mathrm{where}\quad E[\tilde{\epsilon}|\tilde{X}]=E[\tilde{\epsilon}]=0.$$

The definition says that the deviation of the random variable $Y$ from its mean is equal in distribution to the deviation of the random variable $\ddot{X}$ from its mean plus some noise ?. It turns out that this definition is exactly the same as second-order stochastic dominance but with the additional assumptior that the means of the two distributions are the same.

Consider our example again with asset $B$ and therandom variable $t$. We can calculate $B+\epsilon$ as follows

$$B+\epsilon=\left\{\begin{array}{ll}7&\text{with probability}\frac{1}{3}\\4&\text{with probability}\frac{2}{3}\end{array}\right.\quad\text{if}B=5$$

And

$$B+\epsilon=\left\{\begin{array}{ll}6&\text{with probability}\frac{1}{2}\\0&\text{with probability}\frac{1}{2}\end{array}\right.\quad\text{if}B=3.$$

Since $B=5$ or $B=3$ with equal probability we have

$$B+\epsilon=\begin{cases}\:7&\text{with probability}\:\frac{1}{6}\\\:4&\text{with probability}\:\frac{1}{3}\\\:6&\text{with probability}\:\frac{1}{4}\\\:0&\text{with probability}\:\frac{1}{4}\end{cases}.$$

This shows that $B+\epsilon$ and $A$ have the same distribution function and thus are equalin distribution. We can say that $A$ is riskier than $B$ because it is obtained from $B$ by adding some "noise".

It turns out that we cannot compare $C^{r}$ and $D$ using this definition. That is there is no noise $t$ such that $C\stackrel{d}{=}D+\epsilon$ or $D\stackrel{d}{=}C+\epsilon$ .We say that $C$ and $D$ are incomparable in terms of risk. Thus we simply have to accept that not all assets or portfolios can be compared in terms of their riskiness.

But all asset including $C$ and $D$ can be compared in terms ofvariance. This implies that in general variance is not a good measure of risk. Indeed that it is an over strong measure of risk and a larger variance does not always correspond to what we mean by larger risk. However the opposite is true:

$$\text{Greater Risk}\Rightarrow\text{Greater Variance}$$

Thus we can conclude that a riskier asset has the greater variance. To see this we can compute the variance of $Y$ ,  when $Y$ is riskier than $X$ as follows

$$\begin{aligned}
Var (Y)=var (Y-E[Y])& =\: var (X-E[X]+\epsilon) \\
&=\: var (X-E[X])+var (\epsilon)+2 cov (X-E[X],    \epsilon) \\
&=\: var (X)+var (\epsilon) \\
&\begin{matrix}{>}&{var (X).}\\\end{matrix}
\end{aligned}$$

Here the first line follows because $Y$ and $X+\epsilon$ are equal in distribution thesecond line follows from the rule for variances and the third line follows because $X$ and $t$ are uncorrelated. Finally since $E$ is noise,   its variance is positive so $var (X)+var (\epsilon)>var (X)$ .Thus greater variance is a necessary condition for greater risk but it is not sufficient.

# 7. Conclusion

There have been many measures of risk that have been proposed. Many measures that have been proposed are not coherent. Other measures which are coherent but are complete run into the problem that not all risk averse investors would necessarily agree on which investment is riskier. If however,   we accept a partial measure of risk that compares some but not all portfolios of investment,   then second order stochastic dominance of the equivalent (when the means are the same) measure of increases in risk will give a measure on which all risk averse investors will agree.
