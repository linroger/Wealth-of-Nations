---
cssclasses: academia
linter-yaml-title-alias: BINOMIAL TREES AND MONTE CARLO SIMULATIONS
title: Teaching Note 5 Risk Neutral Pricing
tags:
  - binomial_trees
  - option_hedging
  - replicating_portfolio
  - risk_neutral_pricing
  - zero_coupon_bond
aliases:
  - Heaton
  - Risk Neutrality
  - TN5
key_concepts:
  - Binomial tree example
  - Continuously compounded rate
  - Option hedging strategy
  - Relative pricing on trees
  - Replicating portfolio concept
---

# Teaching Note 5 Risk Neutral Pricing

John Heaton

The University of Chicago

Booth School of Business

NBER

[[Fixed Income Lecture Notes]]

 [[Introduction to Fixed Income Asset Pricing]]

 [[Lecture Note 2Interest Rate Risk Management And Factors]]

 [[Forward Rates and Term Structure]]

 [[Teaching Note 4 Interest Rate Derivatives]]

 [[Teaching Note 5 Risk Neutral Pricing]]

[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

[Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

[PSET V Fixed Income Asset Pricing](PSET%20V%20Fixed%20Income%20Asset%20Pricing.md)

## BINOMIAL TREES
- Let's start from an example.
- Let's assume the six-month,  *continuously compounded* risk-free rate is estimated to move according to the following tree (step = 1/2 year),  where there is probability p = 1/2 to move up or down.
![|500](Pasted%20image%2020240426062238.png)

## BINOMIAL TREES
- The expected rate in six and twelve months are

$$\begin{array}{l l l}{{E\left[r_{1}\right]}}&{{=}}&{{\frac{1}{2}r_{1,   u}+\frac{1}{2}r_{1,   d}=0.02305}}\\ {{}}&{{}}&{{1}}\\ {{E\left[r_{2}\right]}}&{{=}}&{{\frac{1}{4}r_{2,   u u}+\frac{1}{2}r_{2,   u d}+\frac{1}{4}r_{2,   d d}=}}\end{array}$$

- Note: $r_t$ here is the continuously compounded,  one period interest rate.
- For trees,  it is convenient to denote bonds in terms of steps and nodes.
- Let $Z_{i,   j}\left(k\right)$
- be the value of a zero coupon bond at index time i (e.g. $i = 1$),  at node j (e.g. $j = *u,    d*…$) and with maturity at index $k$ (e.g. $k = 2$).
- For instance

$$\begin{array}{r c l}{{Z_{0}\left(1\right)}}&{{=}}&{{\mathrm{Zero~at~time~0~that~matures~at~time~1}}}\\ {{Z_{1,   u}\left(2\right)}}&{{=}}&{{\mathrm{Zero~at~time~1~in~node~}u p\mathrm{~that~matures~at~time~2}}}\end{array}$$

## RELATIVE PRICING ON TREES
- **EXAMPLE:** BOND AND OPTION
- Suppose that by using any of the methodologies in TN 1 we obtained the following discounts:

$$Z_{0}\left(1\right)=0.9916,   \ Z_{0}\left(2\right)=0.9781,   \ Z_{0}\left(3\right)=0.9615$$

- Let $C_0$ be a call option on a six-month zero-coupon bond with maturity $i = 1$ and strike price K.
- A call option on a zero coupon bond gives its owner the right,  *but not the obligation*,  to buy a six-month zero coupon at $i$ for price $K$.
- The payoff to the buyer of the option is

$$C_{1}=\operatorname*{max}{\big(}Z_{1}\left(2\right)-K{\big)}$$

- At time $i = 1$,  we know $Z_1 (2)$ under the two scenarios that the yield went up or down.
- Thus we can compute $C_1$. Assuming K = 0.99,  consider the tree
- ![|500](Pasted%20image%2020240426062615.png)
- We now consider a hedging strategy that allows us to evaluate options on the tree.
## THE OPTION HEDGING STRATEGY
- Consider a portfolio at time $i = 0$ that is long the option and short ∆ units of the 2-period zero coupon bonds
	- Its value at time $j=0$ is

$$\Pi_{0}=C_{0}-\Delta\times Z_{0}\left(2\right)$$

	+ What is its value at time $j = 1$?  

In up node: $$\Pi_{1,   u}=C_{1,   u}-\Delta Z_{1,   u}(2)$$

In down node: $$\Pi_{1,   d}=C_{1,   d}-\Delta Z_{1,   d}(2)$$

- Besides ∆,  all quantities on the right-hand side are known.
- Key step CHOOSE $\Delta$ TO MAKE $\Pi_{1,   u}$ = $\Pi_{1,   d}$
- Imposing equality
$$C_{1,   u}-\Delta Z_{1,   u}\left(2\right)=C_{1,   d}-\Delta Z_{1,   d}\left(2\right)$$
- yields

$$\Delta=\frac{C_{1,   u}-C_{1,   d}}{Z_{1,   u}\left(2\right)-Z_{1,   d}\left(2\right)}$$

	+ $\Delta$ is now known. For instance,   if $K=$ we have $\Delta=0.4076$

	+ In this case,   we find $Π_{1,   u} = C_{1,   u} − ∆Z_{1,   u} (2) = −0.3998$ (also equal to = $Π_{1,   d}$)

- What is the value of the portfolio at time $i = 0$?
	- The portfolio is riskless between time $i = 0$ and $i = 1.$
	- Therefore,  its value must be the discounted value of $\Pi_{1,   u}$ using the risk free rate to discount.

$$\mathrm{\underline{{\mathrm{~No~Arbitrage}}}\Longrightarrow\Pi_{0}=Z_{0}\left(1\right)\Pi_{1,   u}}$$

- (Recall $\Pi_{1,   u}$ = $\Pi_{1,   d}$ so it does not matter what you put on the RHS)

## THE OPTION VALUE

- Therefore $$C_{0}-\Delta Z_{0}\left(2\right)=Z_{0}\left(1\right)\Pi_{1,   u}$$
- implying

$$C_{0}\ =\ \Delta Z_{0}\left(2\right)+Z_{0}\left(1\right)\Pi_{1,   u}=0.00223$$

- (recall $Z_{0}\left(1\right)=0.9916,   \ Z_{0}\left(2\right)=0.9781,   \ Z_{0}\left(3\right)=0.9615$)

## THE REPLICATING PORTFOLIO
- Note that the option is a portfolio of zeros:
- $N_1 = ∆$ = of one-year zero $Z_0(2)$; and
- $N_2 = Π_{1,   u} = −0.3998$ of six-month zero $Z_0(1)$.
- That is,  the portfolio of bonds $$P_{0}=N_{1}\times Z_{0}(2)+N_{2}\times Z_{0}(1)$$
- exactly replicates the payoff of the option.

## THE REPLICATING PORTFOLIO

![|500](Pasted%20image%2020240426063208.png)

- P is called "replicating portfolio,  " a key concept.
- What was special about the fact that C0 was an option on zero-coupon bond?
	- Nothing in particular!
	- We could do the same derivation with any other security.
- Let's do the same steps,  but now using ANY other security,  that depends on interest rates.
- Generically,  let Z0 (j) be any zero coupon bond,  and let's consider the following generic tree
	- ![|250](Pasted%20image%2020240426063258.png)
- Let's follow the same steps:
- *Step 1*: Portfolio $$\Pi_{0}=V_{0}-\Delta Z_{0}\left(j\right)$$
- *Step 2*: Choose $\Delta$ to make portfolio at time $j=1$ independent of interest rates $$\Pi_{1,   n}=\Pi_{1,   d}$$ $$\Longleftrightarrow$$ $$V_{1,   u}-\Delta Z_{1,   u}\left(j\right)=V_{1,   d}-\Delta Z_{1,   d}\left(j\right)$$ $$\Longleftrightarrow$$ $$\Delta=\frac{V_{1,   u}-V_{1,   d}}{Z_{1,   n}\left(j\right)-Z_{1,   d}\left(j\right)}\tag{1}$$
- *Step 3*: The portfolio is riskless,  no arbitrage requires

$$\Pi_{0}=Z_{0}\left(1\right)\Pi_{1,   u}\;\mathrm{or,   ~equivalently,   }\;\Pi_{0}=Z_{0}\left(1\right)\Pi_{1,   d}$$

- In fact,  we can take the expected value using *any* probability $\tilde{p}$

$$\Pi_{1,   u}=\Pi_{1,   d}=E^{\bar{p}}\left[\Pi_{1}\right]$$

- where

$$E^{\tilde{p}}\left[\Pi_{1}\right]=\tilde{p}\Pi_{1,   u}+(1-\tilde{p})\Pi_{1,   d}$$$$=\tilde{p}\left[V_{1,   u}-\Delta Z_{1,   u}\left(j\right)\right]+(1-\tilde{p})\left[V_{1,   d}-\Delta Z_{1,   d}\left(j\right)\right]$$$$=E^{\tilde{p}}\left[V_{1}\right]-\Delta E^{\tilde{p}}\left[Z_{1}\left(j\right)\right]$$

- Substituting

$$\begin{array}{r c l}{{\Pi_{0}}}&{{=}}&{{Z_{0}\left(1\right)E^{\bar{p}}\left[\Pi_{1}\right]}}\\ {{}}&{{\Longleftrightarrow}}\\ {{V_{0}-\Delta Z_{0}\left(j\right)}}&{{=}}&{{Z_{0}\left(1\right)\left\{E^{\bar{p}}\left[V_{1}\right]-\Delta E^{\bar{p}}\left[Z_{1}\left(j\right)\right]\right\}}}\end{array}$$

- Step 4: Rearrange $$V_{0}=Z_{0}\left(1\right)E^{\beta}\left(V_{1}\right)-\Delta\times\left\{Z_{0}\left(1\right)E^{\beta}\left[Z_{1}\left(j\right)\right]-Z_{0}\left(j\right)\right\}\tag{2}$$
- Substitute ∆ from (1) and rearrange again

$$\frac{Z_{0}\left(1\right)E^{\tilde{p}}\left[Z_{1}\left(j\right)\right]-Z_{0}\left(j\right)}{Z_{1,   u}\left(j\right)-Z_{1,   d}\left(j\right)}=\frac{Z_{0}\left(1\right)E^{\tilde{p}}\left(V_{1}\right)-V_{0}}{V_{1,   u}-V_{1,   d}}$$

- This last expression is key to the whole fixed income asset pricing.
- To interpret it,  let's rewrite the equality as

$$E^{\tilde{p}}\left[\frac{V_{0}}{V_{0}}\right]-\frac{1}{Z_{0}(1)}=\frac{E^{\tilde{p}}\left[\frac{Z_{1}(j)}{Z_{0}(j)}\right]-\frac{1}{Z_{0}(1)}}{\left[\frac{V_{1,   n}}{V_{0}}-\frac{V_{1,   d}}{V_{0}}\right]}=\frac{\left[\frac{Z_{1,   n}(j)}{Z_{0}(j)}-\frac{Z_{1,   d}(j)}{Z_{0}(j)}\right]}{\left[\frac{Z_{1,   n}(j)}{Z_{0}(j)}-\frac{Z_{1,   d}(j)}{Z_{0}(j)}\right]}\tag{3}$$

- Notice

$$E^{\vec{p}}\left[\frac{V_{1}}{V_{0}}\right]=\mbox{Expected Return(under$\vec{p}$)from purchasing$V_{0}$}$$

$$E^{\vec{p}}\left[\frac{V_{1}}{V_{0}}\right]-\frac{1}{Z_{0}\left(1\right)}=\mbox{Expected Return in Excess of Treasury}$$

$$\left[\frac{V_{1,   u}}{V_{0}}-\frac{V_{1,   d}}{V_{0}}\right]=\mbox{Risk from investing in$V_{0}$}$$

- The above hold for *any* $\tilde{p}$. To have economic meaning,  we must though use the *true* $\tilde{p}$ = p = 0.5.
- Denoting E[.] (without superscript) the expectations under the true probability,  we have

$${\frac{E\left[{\frac{V_{1}}{V_{0}}}\right]-{\frac{1}{Z_{0}(1)}}}{\left[{\frac{V_{1,   u}}{V_{0}}}-{\frac{V_{1,   d}}{V_{0}}}\right]}}\ =\ {\frac{\mathrm{Expected~Excess~Return}}{\mathrm{Risk~from~investment}}}={\left\{\begin{array}{l l}{\mathrm{Sharpe~Ratio}}&{o r}\\ {\mathrm{Market~Price~of}}&{\mathrm{Interest~Rate~Risk}}\end{array}\right.}$$

- Similarly for the right hand side of (3).
## NO ARBITRAGE IMPLICATION 1
- Equality (3) applies to all securities that depend on the interest rate.
- That is,  for any security $V$,  we have $$E\left[\frac{V_{0}}{V_{0}}\right]-\frac{1}{Z_{0}(1)}=\lambda\tag{4}$$
 - where $\lambda$ does not depend on the security considered.
- This includes options,  long term bonds and so on.
- *Caveat*: The quantity $$\left[\frac{V_{1,   u}}{V_{0}}-\frac{V_{1,   d}}{V_{0}}\right]$$
- can be positive or negative (for bonds,  it is negative: if interest rate is "up",  then $V_u$ is "down".
- Thus $V_{1,   u}  < V_{1,   d})$.

## NO ARBITRAGE IMPLICATION 2
- If we know λ,  we can compute the price of any other security simply by inverting (4):

$$V_{0}=Z_{0}\left(1\right)\left\{E\left[V_{1}\right]-\lambda\left[V_{1,   u}-V_{1,   d}\right]\right\}\tag{5}$$

 - **WHERE DO WE GET** Λ?
- Since relation (4) holds for all securities,  it holds for the 2-period bond:

$$\lambda=\frac{E\left[\frac{Z_{1}(2)}{Z_{0}(2)}\right]\,   -\,   \frac{1}{Z_{0}(1)}}{\left[\frac{Z_{1,   u}(2)}{Z_{0}(2)}\,   -\,   \frac{Z_{1,   d}(2)}{Z_{0}(2)}\right]}$$

- From the original tree we can compute

$$\lambda={\frac{1.010705882-1.008435379}{-0.015817224}}=-0.1435$$

- Using (5),  the price of the call option is

$$C_{0}\ =\ Z_{0}\left(1\right)\left\{E\left[C_{1}\right]+0.1435\times\left[C_{1,   u}-C_{1,   d}\right]\right\}=0.00223$$

- Once we know λ,  we can compute the price of *any* derivative security on the interest rate,  maturing (for now)
one period ahead,  by using (5).

## OPTION PRICING EXAMPLE
- **Example**: How do we price a caplet? That is,  a security that pays at i = 1 the amount

$$\operatorname{pay}\left(i\right)=\mathbb{N}\times\operatorname*{max}\left(r_{i}-{\overline{{r}}}\right)$$

- where $N$ is some notional.
- If $N = 1000$ and r = (at the money),  we have

$$\begin{array}{r c l}{{\mathrm{pay}_{u}(1)}}&{{=}}&{{N\times\operatorname*{max}(0.0387-0.0168,   0)=21.9}}\\ {{\mathrm{pay}_{d}(1)}}&{{=}}&{{N\times\operatorname*{max}(0.0074-0.0168,   0)=0.}}\end{array}$$

- We then immediately obtain

$$\begin{array}{r c l}{{\mathrm{Caplet}\left(0\right)}}&{{=}}&{{Z_{0}\left(1\right)\left\{E\left[\mathrm{pay}\left(1\right)\right]+0.1435\left[\mathrm{pay}_{u}-\mathrm{pay}_{d}\right]\right\}}}\\ {{}}&{{=}}&{{13.97}}\end{array}$$

## NO ARBITRAGE PRICING
- Can we obtain the price of a 2-period bond itself $Z_0(2)$?
- No! That's one of our inputs. (We used it to compute λ)
- Can we obtain the price of any security that matures in period $j = 2$ (rather than $j = 1$)?
- Yes,  by moving backward (but need more work). - We will see how to do so using a different pricing methodology.

## RISK NEUTRAL PRICING
- Recall that "Step 4" in our derivations above gave us the equation (2) is

$$V_{0}=Z_{0}\left(1\right)E^{p}\left(V_{1}\right)-\Delta\times\left\{Z_{0}\left(1\right)E^{p}\left[Z_{1}\left(j\right)\right]-Z_{0}\left(j\right)\right\}\tag{6}$$

- This equation held for *any* probability $\hat{p}$. We can thus choose a $\hat{p}$ that makes life easier.
- What is the probability $\tilde{p}$ that makes the second term = 0?
- That is,  we want to find the probability π∗ such that

$$Z_{0}\left(1\right)E^{*}\left[Z_{1}\left(j\right)\right]-Z_{0}\left(j\right)=0$$

- where E∗[] denotes the expectation that uses the probability π∗.
- Develop the expectation $$Z_0\left(1\right)\left[\pi^{\ast}Z_{1,   \alpha}\left(j\right)+\left(1-\pi^{\ast}\right)Z_{1,   \delta}\left(j\right)\right]-Z_0\left(j\right)=0\tag{7}$$
- to get $$\pi^{\ast}\left[Z_{1,   \alpha}\left(j\right)+Z_{1,   \delta}\left(j\right)\right]+Z_{1,   \delta}\left(j\right)=Z_0\left(j\right)/Z_0\left(1\right)$$

## RISK NEUTRAL PROBABILITIES
- Solving the previous equation,  we obtain

$$\pi^{*}=\frac{Z_{0}\left(j\right)/Z_{0}\left(1\right)-Z_{1,   d}\left(j\right)}{Z_{1,   u}\left(j\right)-Z_{1,   d}\left(j\right)}$$

- $\pi^{*}$ is the *risk neutral probability* or *risk adjusted probability* of moving up in the tree.
- E∗ [.] - the expectation computed using π∗ - is called *risk neutral* expectation.
- The term "risk neutral" refers to the fact that under π∗,  all assets yield the risk free rate of return.
- In fact,  from its derivation in equation (7) we also have

$$\underbrace{\pi^{*}\frac{Z_{1,   u}\left(j\right)}{Z_{0}\left(j\right)}+\left(1-\pi^{*}\right)\frac{Z_{1,   d}\left(j\right)}{Z_{0}\left(j\right)}}_{\text{Expected Return on2-period bond}}=\underbrace{\frac{1}{Z_{0}\left(1\right)}}_{\text{Return on1-period Bond}}$$

- Indeed,  because under $\tilde{p}$ = π∗ the last term in (6) is zero,  we have the
risk-neutral pricing formula

$$V_{0}=Z_{0}\left(1\right)E^{*}\left[V_{1}\right]$$

## RISK NEUTRAL PRICING
- The risk neutral pricing formula implies

$$\underbrace{E^{*}\left[\frac{V_{1}}{V_{0}}\right]}_{\mbox{$\left[\mbox{Return on$V$}\right]$}}=\underbrace{\frac{1}{Z_{0}(1)}}_{\mbox{$\left[\mbox{Return on$6$-month Tbill}\right.$}}\tag{9}$$

- Risk neutral pricing is nothing more than a "trick" to easily compute the price of derivatives. - It implies a simple recipe to price securities:
- Recipe:
1. Assume agents are risk neutral.
1. Find risk neutrality probabilities,  that is,  find π∗.
1. Compute the price of derivatives using π∗ and discounting at the risk free rate.

## DOES RISK NEUTRAL PRICING WORK?
- In the example above,  using the 2-period bond (j = 2) we obtain π∗ = 0.643546229
- The call price is then

$$\begin{array}{l l l}{{C_{0}}}&{{=}}&{{Z_{0}\left(1\right)\left(\pi^{*}\times C_{1,   u}+\left(1-\pi^{*}\right)\times C_{1,   d}\right)}}\\ {{}}&{{=}}&{{0.9916\times\left(0.6435\times0+0.35645\times\right)}}\\ {{}}&{{=}}&{{0.00223}}\end{array}$$

- The price of the caplet is

$$\begin{array}{r c l}{{\mathrm{Caplet}_{0}}}&{{=}}&{{Z_{0}\left(1\right)\times E^{*}\left[\sf{pay}\left(1\right)\right]}}\\ {{}}&{{=}}&{{0.9916\times\left(0.6435\times21.9+0.35645\times0\right)}}\\ {{}}&{{=}}&{{13.97}}\end{array}$$

- It works beautifully.

## RISK NEUTRAL VS. TRUE PROBABILITIES
- Under the risk neutral probabilities,  the expected interest rate is

$$E^{*}\left[r_{1}\right]=\pi^{*}\times r_{1,   u}+\left(1-\pi^{*}\right)\times r_{1,   d}=0.0275$$

- If your boss asks you what is your forecast of the interest rate in six months,  would you tell him 2.75%?
- In the real world,  the expected interest rate was $$E\left[r_{1}\right]=2.305\%<2.75\%=E^{*}\left[r_{1}\right]$$
- Passing from the real to the risk neutral world implies increasing the *expected* interest rate.
- Interestingly,  note that the forward rate is (recall the time step is 0.5)

$$f(0,   1,   2)=-2\times\ln\left(\frac{Z_{0}(2)}{Z_{0}(1)}\right)=2.7487\%$$

This is very close to the risk-neutral expected future rate

## USING RISK NEUTRAL TREES
- From now on,  we assume that the tree that we are using is "risk neutral"
- Rather than finding probabilities that make an original "true" tree into a risk neutral one,  we start immediately from the latter.
- We will see later how to build a tree that is risk neutral directly from traded securities. - Suppose that the short-term,  continuously compounded interest rate moves according to the following tree.
- At every time (1 period = 6 months),  there is equal *risk neutral* probability ($π^∗ = 1/2$) to move up or down.
![|500](Pasted%20image%2020240426064656.png)
- The value of a zero-coupon bond paying one dollar in period i = 1 is (the time step $∆t = 0.$5)

$$\underline{{{Z_{0}\left(1\right)=e^{-r_{0}\times\Delta t}\times1=0.9916}}}$$

- What is the value of bond paying $1 in one year (i = 2)?
- It can be obtained by proceeding backward on the tree:
![|500](Pasted%20image%2020240426064740.png)
- Similarly,  a bond paying $1 in 1.5 years (i = 3):
- ![|500](Z.%20Clippings/Pasted%20image%2020240426064801.png)
- These prices imply the zero-coupon yields

$$\begin{array}{r c l}{{y_{0}(1)}}&{{=}}&{{-\frac{\ln[Z_{0}(1)]}{\Delta t}=0.0168}}\\ {{}}&{{}}&{{}}\\ {{y_{0}(2)}}&{{=}}&{{-\frac{\ln[Z_{0}(2)]}{2\Delta t}=0.0222}}\\ {{}}&{{}}&{{}}\\ {{y_{0}(3)}}&{{=}}&{{-\frac{\ln[Z_{0}(3)]}{3\Delta t}=0.0267}}\end{array}$$

- The methodology is actually quite simple.
- In addition,  computers can be programmed rather easily to carry out the backward computation.
- Example:

 ![500](Pasted%20image%2020240426064841.png)

## DESCRIBING BIG TREES

HOW DO WE DESCRIBE A LONG TREE?

- Using the earlier notation u,  uu etc is OK for small trees.
- When we start looking at long trees (30-60 steps),  then we use a slightly different notation.
- Specifically,  each point on the tree can be described by a time index i and a node index j.
- In the example in Table 2,  $i = 0*,    …,   * 10$ and $j = 1*,    …,   * 11.$
- Notice that given a tree,  we can insert any type of known cash flow.
- Specifically,  at any time-node (*i,  j*),  we just must add the CF

$$P_{i,   j}=e^{-r_{i,   j}\Delta t}\left(\frac{1}{2}P_{i+1,   j}+\frac{1}{2}P_{i+1,   j+1}+C F_{i+1}\right)$$

- So,  for example,  a 1.5 year,  4% coupon bond is just given by
![|500](Pasted%20image%2020240426065006.png)

- This tree gives "ex-coupon" prices.
- Using ex-coupon prices is useful in a number of circumstances,  as we shall see.

## EXAMPLES

- Trees turn out to be very useful tools (not only pedagogically).
- One of the most important features of them is the ability to deal with "American options."
- As a consequence,  a very simple application of the "tree" methodology is the computation of prices of callable bonds.

## CALLABLE BONDS
- Consider the 1.5 year,  4% coupon bond we discussed earlier,  but assume it is callable at par 100.
- That is,  at any point in time before maturity,  the issuer (Treasury) may "call it back" in exchange of 100.
	- In general,  bonds become callable after some period of time.
	- For example,  the Nov 2012 Treasury bond is callable at par starting on Nov 2007.
	- If issuer calls the bond between coupon days,  it has to pay the accrued interest to the bond holder.

## HOW DO WE COMPUTE THE PRICE OF AMERICAN OPTIONS?

WE MOVE BACKWARDS ON THE TREE

- At any node (*i,  j*) the issuer can decide whether to "exercise" option or wait.
- If exercises,  the payoff (= value of the option) is

$$C a l l_{i,   j}^{\mathrm{E}_{\mathrm{x}}}=P_{i,   j}-100$$

- If waits,  the value of the option

$$C a l l_{i,   j}^{\mathrm{Wait}}~=~e^{-r_{i,   j}\Delta t}E^{*}\left[C a l_{i+1}\right]=e^{-r_{i,   j}\Delta t}\left(\frac{1}{2}C a ll_{i+1,   j}+\frac{1}{2}C a ll_{i+1,   j+1}\right)$$

- Therefore,  the value at node *i,  j* is

$$Call_{i,   j}=\max\left(Call_{i,   j}^{bus},   Call_{(i)}^{bus}\right)\tag{10}$$

 $$=\max\left(e^{-r_{i,   j}\Delta t}E^{r}\left[Call_{i+1}\right],   P_{i,   j}-100\right)$$

- Since at maturity $I=T/\Delta t$ we have

$$Call_{i,   j}=0\text{for all}j$$

- (the option expires worthless at maturity,  as the issuer has to redeem the bond at par)
- we can start the procedure (10) backward.
![|500](Pasted%20image%2020240426065149.png)

### WHAT IS THEN THE PRICE OF THE CALLABLE BOND?
- The buyer of a callable bond is: (1) buying a non-callable bond; + (2) Selling a call to the issuer.
- Hence,

$$\begin{array}{l l l}{{P_{0}^{\mathbf{Call}}\left(3\right)}}&{{=}}&{{P_{0}^{\mathbf{NoCall}}\left(3\right)-C_{0}\left(3\right)}}\\ {{}}&{{=}}&{{101.93-1.16}}\\ {{}}&{{=}}&{{100.77}}\end{array}$$

## CAPS AND FLOORS
- A cap is a security that pays the stream of cash-flows

$$CF\left(t\right)=\Delta t\times N\times\max\left(r\left(t-1\right)-\overline{r}\right)\tag{11}$$

- where $r$ is the strike rate,  $r (t)$ is some floating rate interest rate,  such as the three month t-bill rate or LIBOR,  $N$ is the notional and $∆t$ is the amount of time between payments.
- Each payment (11) is called "caplet".
	- Caps offer insurance against the interest rate increasing to above some level.
	- They are often attached to floating rate bonds,  so as to limit the amount of interest to pay.
- A floor is instead a security paying

$$CF\left(t\right)=\Delta t\times N\times\max\left(\bar{r}-r\left(t-1\right)\right)\tag{12}$$

## CAP PRICING EXAMPLE
- Consider a 1.5 years cap,  with continuously compounded strike rate $r = 3\%$,  semi-annual payments ($∆t = 1/2$) and $N = 100$.
- Assume that the risk-neutral tree is given by (18) and let
$CF_{i,   j}\left(i+1\right)=$ Cash Flow at time $i+1$,  due to rate at node $i,   j$

$$=\frac{1}{2}\times N\times\max\left(r_{i,   j}-\overline{r}\right)$$

- We then have:
![|500](Pasted%20image%2020240426065423.png)

## CAP PRICING EXAMPLE
- Given these cash flows,  define

-$$ \begin{aligned}V_{i,   j}&=\text{ Value at time }i\text{ of all Cash Flows at times }k>i\\&=\quad e^{-\frac12r_{i,   j}}\times\left(\frac12V_{i+1,   j}+\frac12V_{i+1,   j+1}+CF_{i,   j}\left(i+1\right)\right)\end{aligned}$$

- Then,  the following backward tree gives a cap price $V_0 = 0.87$
- Table 3 shows the pricing of a cap on the bigger tree in Table 2,  with r = 5%; and N = 100.
![|500](Pasted%20image%2020240426065546.png)

![|500](Pasted%20image%2020240426065611.png)

## SWAPS AND SWAPTIONS

- Similarly,  the computation of Swaps and Swaptions (options to enter into a Swap) are simple.
- Consider a 2 year swap (Maturity = i = 4),  with swap rate (c.c.) $r =,    N = 100$.
- Again,  denote by $CF_{i,   j}\left(i+1\right)=$ Cash Flow at time $i+1$,  due to rate at node $i,   j$

$$=\frac{1}{2}\times N\times\left(r_{i,   j}-\overline{r}\right)$$

- We obtain the tree of cash flows:
![|500](Pasted%20image%2020240426065653.png)

- The tree for the value of the swap (for the fixed payer) is then immediately computed. - Denoting again

$$\begin{array}{l l}{{V_{i,   j}}}&{{=\ \text{Value at time}\ i\ \text{of all CashFlows at times}\ k>i}} \\ {{=}}&{{e^{-\frac{1}{2}r_{i,   j}}\times\left(\frac{1}{2}V_{i+1,   j}+\frac{1}{2}V_{i+1,   j+1}+C F_{i,   j}\left(i+1\right)\right)}}\end{array}$$

- we obtain

V3*,  uuu* = e−0.08/22.47 = 2.37 $V_{2,   uu}$ = e−0.0638/2× ×[1/2(2.37 + 1.12) +1.67] = 3.31 V3*,  uud* = e−0.053/21.15 = 1.12 $V_{1,   u}$ = e−0.0433/2× ×[1/2(3.31 +) +0.64] = 2.67 $V_{2,   ud}$ = e−0.0361/2× ×[1/2(1.12 +) +] = 0.86 V0 = e−0.0168/2× ×[1/2(2.67 − 1.32) −] = 0 V3*,  udd* = e−0.032/2.07 = 0.07 $V_{1,   d}$ = e−0.0120/2× ×[1/2(− 1.68) −] = −1.32 $V_{2,   dd}$ = e−0.0083/2× ×[1/2(− 1.25) −1.1] = −1.68 $$\begin{array}{l}{{V_{3,   d d d}=e^{-0.0054/2}\times}}\\ {{\times\left(-1.25\right)=-1.25}}\end{array}$$

![|500](Z.%20Clippings/020240426065908.png)

- The swap rate r = 0.0304 was chosen to make the value of the Swap contract = 0 at time i = 0.

## SWAPTIONS
- A Swaption is an option to enter into a swap,  at a given swap rate $r_X$
	- A *Receiver Swaption* is an option to enter into a swap and receive fixed $r_X$.
	- A *Payer Swaption* is an option to enter into a swap and pay fixed $r_X$.
- Computing now the value of a European Swaption is simple.
- Consider for instance a European Swaption with maturity $T = 1$ (i.e. $i = 2$) to enter a one year swap and pay fixed $r_X$ =0.0304
- Let $r_{i,   j}$ be the swap rate in the node ij
- Then:
	- If $r_{2,   j}$ *> $r^*_X$ we exercise the option (we pay $r_X$ instead of current rate $r_{2,   j}$).
	- If $r_{2,   j}$ *< $r^*_X$ we do not exercise the option (we are better off paying the market rate $r_{2,   j}$).
- It looks complicated. How do we model this decision?
	- We remember that the swap rate $r_{i,   j}$ is determined in node ij to make the value of the swap at that node equal to 0.

## SWAPTIONS
- Therefore,  we first compute the value of the swap with *given* swap rate $r_X$ along the tree $V_{i,   j}$

$$V_{i,   j}=e^{-r_{i,   j}\Delta t}\left(\frac{1}{2}V_{i+1,   j}+\frac{1}{2}V_{i+1,   j+1}+(r_{i,   j}-r_{X})\right)$$

- Since $V_{2j} > 0$ if and only if $r_X$ *< r*2j = current market swap rate
	- we exercise at time i = 2 in node j if and only if V2j > 0.
- The payoff of the swaption at i = 2 is then

$$\mathrm{Payoff}_{2j}=C_{2,   j}=\operatorname*{max}{(V_{2j})}$$

- The value of the European Swaption can then be computed by backward calculations:

$$C_{i,   j}=e^{-r_{i j}\Delta t}\left(\frac{1}{2}C_{i+1,   j}+\frac{1}{2}C_{i+1,   j+1}\right)$$

## SWAPTIONS: EXAMPLE
- Consider receiver swaption with a strike swap rate $r_X$ =
- The swaption is at the money,  that is $r_X$ = r0 = current swap rate at 0.
- The relevant tree for Vi,  j is then the one given earlier.
- Since $V_{2,   uu}$ = 3.31,  $V_{2,   ud}$ = 0.86 and $V_{2,   dd}$ = −1.68,  we only exercise in the top two nodes at i = 2.
- The tree to value the swaption is then given by:
![|500](Z.%20Clippings/Pasted%20image%2020240426070045.png)
## AMERICAN SWAPTIONS: EXAMPLE
- Computing an American style swaption exploits the same methodology illustrated earlier. That is,  we must have

$$C_{i,   j}^{A m}=\operatorname*{max}\left(V_{i,   j},   \ e^{-r_{i,   j}\Delta t}\times\left(\frac{1}{2}C_{i+1,   j}^{A m}+\frac{1}{2}C_{i+1,   j+1}^{A m}\right)\right)$$

- In this case,  we find
- ![|500](Pasted%20image%2020240426070115.png)
## SWAPTIONS: EXAMPLES

- Note that $C^{Am}_0= 1.53 *> C*0 = 1.22$. An American option always gives more "rights" than the European option.
- Note also that we exercise before maturity at node ($1,    u$).
- In a slightly more serious exercise,  we have a table like the following:
- Let the "Terms" be:
	- r = 0.03999;
	- T = 5 years;
	- Semi-annual payments;
	- At-the-money Payer Swaption with T ∗ = 3 years:
	- (In the last panel,  a "*" denotes early exercise of the option)

![|500](Pasted%20image%2020240426070229.png)

![|500](Pasted%20image%2020240426070244.png)

## TREE BUILDING
- HOW CAN WE CONSTRUCT A TREE?
- There are various models and methodologies. We consider two simple models here.

## THE HO-LEE MODEL

- The Ho-Lee model makes a simple assumption about the dynamics of the short-term interest rate. - Let ∆t be the time step. Then,  for every node (*i,  j*) the next interest rate is given by

$$r_{i+1,   j}=r_{i,   j}+\theta_{i}\times\Delta t+\sigma\times\sqrt{\Delta t}\quad\mbox{for a"up"movement}\tag{13}$$

 $$r_{i+1,   j+1}=r_{i,   j}+\theta_{i}\times\Delta t-\sigma\times\sqrt{\Delta t}\quad\mbox{for a"down"movement}\tag{14}$$

- where the risk neutral probability of an up movement is π∗ = 0.5; σ is the annualized volatility; and θi are chosen recursively so as to fit the current term structure of interest rates.
- The tree from Ho Lee is naturally *recombining*: an "up + down" movement produces the same interest rate as a "down + up" movement.
	- To see this easily,  consider $r_{0}$ and use the "$u$,  $d$,  $ud$,  $du$" notation.

$$r_{1,   u}=r_{0}+\theta_{0}\times\Delta t+\sigma\times\sqrt{\Delta t}$$

 $$r_{1,   d}=r_{0}+\theta_{0}\times\Delta t-\sigma\times\sqrt{\Delta t}$$

- Similarly,  the next steps are:

$$\begin{array}{r c l}{{r_{2,   u d}}}&{{=}}&{{r_{1,   u}+\theta_{1}\times\Delta t-\sigma\times\sqrt{\Delta t}}}\\ {{}}&{{=}}&{{r_{0}+\left(\theta_{0}+\theta_{1}\right)\times\Delta t}}\end{array}$$

- and

$$\begin{array}{r c l}{{r_{2,   d u}}}&{{=}}&{{r_{1,   d}+\theta_{1}\times\Delta t+\sigma\times\sqrt{\Delta t}}}\\ {{}}&{{=}}&{{r_{0}+\left(\theta_{0}+\theta_{1}\right)\times\Delta t}}\\ {{}}&{{=}}&{{r_{2,   u d}}}\end{array}$$

 - HOW DO WE SELECT $Θ_i$?
- We choose $θ_i$ iteratively from $i = 0,    1,    …,    n$,  to fit the zero-coupon bond prices.
- To illustrate,  consider the zero-coupon bonds

$$Z_{0}\left(1\right)=0.9916,   \ Z_{0}\left(2\right)=0.9781,   \ Z_{0}\left(3\right)=0.9615$$

- We already have the root of the tree: $r_0 = − ln(Z_0(1))/2 = 0.0169.$
- We next must choose $r_{1,   u}$ and $r_{1,   d}$. Let volatility be $σ =0.015$
- We can search for $θ_0$ such that the value of the bond from the tree equals $Z_0 (2) = 0.9781$.
- Given a $θ_0$ we have
- ![|500](Z.%20Clippings/020240426070530.png)
- We want to search over $\theta_0$ so that $Z_0(2)=0.9781$
- Searching over $θ_0$ we find $θ_0 =0.021145$,  resulting thus in![|500](Pasted%20image%2020240426070706.png)
- Given $θ_0$,  we now look for $θ_1$ by trying to match the next bond $Z_0(3) = 0.9615$.
 ![500](Pasted%20image%2020240426070744.png)
- Clearly,  $Z_0(3)$ from the tree only depends on $θ_1$.
- Searching for $θ_1$ yields $θ_1 = 0.013807$,  yielding
![|500](Pasted%20image%2020240426070808.png)
- And so on for all the possible available maturities.

## THE SIMPLE BLACK-DERMAN-TOY
- One potential issue with the Ho-Lee model is that interest rates can easily get negative. If σ is large,  for instance,  there is nothing in the procedure above that guarantees that $r_{i,   j} > 0$.
- A simple solution is to model the Ho-Lee mode in " logarithm",  that is,  let $z_{ij}=\ln(r_{ij})$ and then assume

$$z_{i+1,   j}=z_{i,   j}+\theta_{i}\times\Delta t+\sigma\times\sqrt{\Delta t}\quad\text{for a"up"movement}\tag{15}$$

$$z_{i+1,   j+1}=z_{i,   j}+\theta_{i}\times\Delta t-\sigma\times\sqrt{\Delta t}\quad\text{for a"down"movement}\tag{16}$$

- Clearly,  even if $z_{ij} < 0$ we have $r_{i,   j}  = e^{z_{ij}} > 0$.
- Note that now σ is the standard deviation of log interest rates. It can be estimated from $∆ ln(rt).$
- Note that now $\sigma$ is the standard deviation of log interest rates. It can be estimated from $\Delta \ln(r_t)$.
	 - Note that to a first order approximation $\Delta z_t \approx \frac{1}{r_t} \Delta r_t$.
	 - Therefore,  $\sigma(z_t) \approx \sigma(r_t)/r_t$
	 - In the previous example,  $\sigma(r_t) = 0.015$ and $r_0 = 1.69%$,  and thus $\sigma(z_t) \approx 88.91%$.
	 - Using the same procedure,  we obtain $\theta_0 = 0.603652218$,  $\theta_1 = 0.089246544$ and the binomial tree.
![|500](Pasted%20image%2020240426071058.png)
## THE BLACK-DERMAN-TOY MODEL
- The previous models are popular,  but they have constant volatility.
- It is hard for them to match the term structure of volatility,  that is,  the fact that options of different maturity may have different volatility.
- The Black-Derman-Toy model still assumes $z_{i,   j} = \log(r_{i,   j})$ as in the simple BDT,  but it assumes that between $i$ and $i+1$,  for every two adjacent nodes $j$ and $j+1$,  the variance is

  $$ \sigma^2_{i+1}\Delta t = \text{Variance}[z_{i}|z_{i-1,   j}] = \frac{1}{2} (z_{i,   j} - E[z_{i}|z_{i-1,   j}])^2 + \frac{1}{2} (z_{i,   j+1} - E[z_{i}|z_{i-1,   j}])^2 $$

- This implies that for every node $j$:$$ \sigma^2_{i+1}\Delta t = \frac{1}{2} \left(\frac{1}{2} (z_{i,   j} - z_{i,   j+1}) \right)^2 + \frac{1}{2} \left(\frac{1}{2} (z_{i,   j+1} - z_{i,   j}) \right)^2 $$$$ = \frac{1}{4} (z_{i,   j} - z_{i,   j+1})^2 $$
- The final equation is then $$ \sigma_{i+1}\sqrt{\Delta t} = \frac{1}{2} (z_{i,   j} - z_{i,   j+1}) \tag{17} $$
- We then need two types of inputs in this model
  1. The current term-structure of yields;
  1. The current term-structure of forward volatility of interest rates.
- The forward volatility can be estimated from options (caps and floors),  and it reflects the volatility of forward rates with the indicated maturity.
- Therefore,  assume the following data
![|200](Pasted%20image%2020240426072414.png)

- **Objective**: Construct an interest rate tree that matches the data in Table 1 exactly.
![|300](Pasted%20image%2020240426071241.png)
- For every two states j and j + 1,  using equation (17) we can rewrite

$$z_{i,   j+1}=z_{i,   j}-2\sigma_{i+1}\surd\Delta t$$

or

$$z_{i,   j+1}=z_{i}-2\times j\times\sigma_{i+1}\surd\Delta t\tag{19}$$

- The unknowns in our original model,  with $∆t = 1$ are then
![|500](Pasted%20image%2020240426071318.png)

- At time $i = 1$ we look for $z_{1,   u}$,  at time $i = 2$ we need to look for $z_{2,   uu}$ etc.
- Since we are already using the "volatility" condition,  the only equation to satisfy for every $i$ is the bond price out of the tree corresponds to the data $Z(0,    T_i)$ that we have available.
- This last computation can be done recursively by going backward from the end of the tree,  as usual.
- **Example**: Suppose you had the data (extracted from Bloomberg)
![|500](Pasted%20image%2020240426071511.png)

- The implied BDT tree (already in interest rate format $r_{i,   j}$ = *exp*(zij) that matches the data is
![|500](Pasted%20image%2020240426072517.png)

## MONTE CARLO SIMULATIONS ON BINOMIAL TREES

- Monte Carlo simulations is the most popular methodology to price securities
- Consider a one-step *risk neutral* binomial tree with equal chance of up or down movement.
- We want to price an interest rate option that pays at time i = 1

$$c_{1}=100\times\operatorname*{max}(r_{1}-r_{K})$$

- where $r_K$ is the strike rate.
- Using risk neutral pricing,  the value of the option is:

$$c_{0}=E^{*}\left[e^{-\eta_{\rm{\tiny{0}}}T}\times c_{1}\right]=e^{-\eta_{\rm{\tiny{0}}}\times T}\left[\frac{1}{2}\times c_{1,   \rm{\tiny{0}}}+\frac{1}{2}\times c_{1,   \rm{\tiny{0}}}\right]\tag{21}$$

- Next figure computes the value of the option for a given binomial tree.
![|300](Pasted%20image%2020240426072605.png)
## MONTE CARLO SIMULATIONS ON BINOMIAL TREE

- Another way of computing the expected future payoff is to *simulate* upward and downward movements in the tree using a computer.
- In Excel and Matlab the function *RAND*() simulates a uniform $[0,    1]$ random variable.
- We can simulate *RAND*() a large number N of times,  and then impose the following:
	- (a) If *RAND*() < 0.5 =⇒ the interest rate moved up the tree
	- (b) If *RAND*() ≥ 0.5 =⇒ the interest rate moved *down* the tree
- For each of realization $s$ of $RAND()$,  we use the corresponding simulated $r_{1,   s}^{s}$ or $r_{1,   d}^{s}$ to compute the option payoff. $$c_{1}^{s}=100\times\max\left(r_{1}^{s}-r_{K}\right)$$
- We can compute the expected discounted payoff in (21) as the average of the discounted payoff across all simulations: $$\tilde{c}_{0}=\text{average of}\left\{e^{-r_{0}\times T}\times c_{1}^{1},   e^{-r_{0}\times T}\times c_{1}^{2},   e^{-r_{0}\times T}\times c_{1}^{3},   …,   e^{-r_{0}\times T}\times c_{1}^{3}\right\}$$ $$=\frac{1}{N}\sum_{s=1}^{N}e^{-r_{0}\times T}c_{1}^{s}\tag{22}$$
- NEXT TABLE ILLUSTRATES THE PROCEDURE
- The first column reports the simulation number.
- The second column displays the actual realization of the *RAND*() function in Excel.
- The third column tells us the movement in the tree implied by the *RAND*() realization.
- The fourth column reports the payoff at maturity,  i.e. $c^s_1 = 100 × max(r^s_1 − r_K,    0).$
- The last column computes the discounted payoff,  $e^{−r_0×T} × c^s_1$
![|500](Pasted%20image%2020240426072835.png)

- With only $N = 10$ simulation,  it is no surprise that the value of the security $\hat{c_0} = 0.693$ comes in rather different than the value from the tree ($c_0 = 0.8660$).
- However,  as the number of simulations $N$ increases,  the value from the simulations becomes more and more accurate.
- For instance

$$\begin{array}{l l l}{{N}}&{{=}}&{{500\Longrightarrow\hat{c}_{0}=0.897}}\\ {{N}}&{{=}}&{{1000\Longrightarrow\hat{c}_{0}=0.888}}\\ {{N}}&{{=}}&{{10000\Longrightarrow\hat{c}_{0}=0.8575}}\end{array}$$

## MONTE CARLO SIMULATIONS ON BINOMIAL TREES
- Consider once again the same option,  but now with one year to maturity,  i.e. i = 2.
- ![|500](Pasted%20image%2020240426072950.png)
- First note that the backward computation methodology is equivalent to the outright calculation of the value of the security as the risk neutral present discounted value of the payoff at maturity,  discounted at the risk free rate.
- That is,  the value of the security is equal to

  $$ c_0 = E^* \left[\left(e^{-r_0 \times 0.5} \right) \times \left(e^{-r_1 \times 0.5} \right) \times c_2 \right] \tag{23} $$

  $$ = E^* \left[e^{-(r_0+r_1) \times 0.5} \times c_2 \right] \tag{24} $$

- Indeed,  the interest rates $r_{2,   uu}$,  $r_{2,   ud}$,  $r_{2,   du}$,  and $r_{2,   dd}$ occur with a 25% chance.
- Thus,  the value of the option is also equal to

  $$ c_0 = 0.25 \times e^{-(r_{1,   u}) \times 0.5} \times c_{2,   uu} + 0.25 \times e^{-(r_{1,   d}) \times 0.5} \times c_{2,   ud} $$

  $$ +0.25 \times e^{-(r_{1,   d}) \times 0.5} \times c_{2,   du} + 0.25 \times e^{-(r_{1,   d}) \times 0.5} \times c_{2,   dd} \tag{25} $$

  $$ = 1.7784,    \tag{26} $$

	- the same price as from the tree.
- We now perform exactly the same simulation exercise as before two realizations of *RAND*()
- The only caveat now is to figure out how we should discount simulated cash flows back to time 0.
- From (24),  and its explicit development in (25) and (26) we must discount cash flow by using the realized
interest rate path in that simulation.
![|500](Pasted%20image%2020240426073107.png)
- Higher number of simulations improves accuracy:

$$\begin{array}{l l l}{{N}}&{{=}}&{{10\Longrightarrow{\hat{c}}_{0}=1.975}}\\ {{N}}&{{=}}&{{1,   000\Longrightarrow{\hat{c}}=1.839}}\end{array}$$

## MONTE CARLO SIMULATIONS FOR PATH DEPENDENT SECURITIES
- Many securities have payoffs that are path dependent
- The payoff at maturity depends on the whole path taken by interest rates before maturity
- Examples include
	- Asian options: Payoff at maturity depend on average interest rates;
	- Corridor bonds: Pay coupon so long interest rate is within a band;
	- Amortizing Interest Rate Swaps: The notional of IRS depend on path of interest rates:
	- Mortgage Backed Securities: Because of frictions in deciding when to pay back mortgage,  payoff depends on path of interest rates (and many other variables)
- The pricing of path dependent securities is easier to perform using Monte Carlo simulations.

## EXAMPLE: ASIAN OPTIONS
- An **Asian interest rate option** is an option whose payoff at maturity is given by

$$\text{Payoff at }T=\left\{\begin{array}{ll}\max\left(\text{average rate from 0 to}T-r_{K}\right)&\text{(Asian Cal)}\\ \max\left(r_{K}-\text{average rate from 0 to}T\right)&\text{(Asian Put)}\end{array}\right.\tag{27}$$

- This payoff makes the binomial tree non-combining,  as the payoff from "up-down movement" is different from the payoff from a "down-up movement"
- Denote by $r_{i,   j} = *average*(r_k)$ for $k ≤ $j on the path to $(*i,    j*).$
- For such short binomial tree we can still compute the value of path-dependent security using backward calculation.
![|500](Pasted%20image%2020240426073408.png)

![|500](Pasted%20image%2020240426073430.png)

## MONTE CARLO SIMULATIONS FOR PATH DEPENDENT SECURITIES

- The tree becomes non-recombining. When we use "big trees",  this is a serious problem.
- For instance,  for mortgage backed security with monthly payment we need a tree with 360 steps. This implies a tree with 2360 = 2.345E + 108 nodes by the end of the tree (!).
- MC simulations do not require a backward calculation. Problem solved! - In the example above,  with 10 simulations,  we obtain the following table:
 ![500](Pasted%20image%2020240426073453.png)

## MONTE CARLO SIMULATIONS WITH MULTI STEP TREES
- The approach readily extends to multi-period binomial trees,  which is an important extension as it allows us to evaluate relatively complex securities.
- For instance,  in the Ho-Lee model we can simulate directly the tree

$$r_{i+1,   j} = r_{i,   j} + \theta_{i} \times \Delta + \sigma \times \sqrt{\Delta} \quad \text{with RN probability } p^* = \frac{1}{2} \tag{28} $$

 $$r_{i+1,   j+1}=r_{i,   j}+\theta_{i}\times\Delta \sigma\times\sqrt{\Delta}\quad\mbox{with $\text{ RN probability }p^{*}=1/2$}\tag{29}$$

## HO-LEE BINOMIAL TREE

 ![500](Pasted%20image%2020240426074107.png)

## HO-LEE BINOMIAL TREE: SIMULATED DISCOUNTS

 ![500](Pasted%20image%2020240426074110.png)

- For each simulated path $r_0,    r_1^s,    r_2^s,    \ldots,    r_{k-1}^s$,  compute the simulated zero with maturity $T_k$ as $$ Z^s(0,    T_k) = e^{-\sum_{i=1}^{k-1} r_i^s \Delta t} $$

 ![500](Pasted%20image%2020240426074122.png)

## SIMULATED HO-LEE BINOMIAL TREE: VALUATION OF ZERO-COUPON BONDS

- The simulated value of a zero coupon bond is the *average* across simulated discounts

$$\widetilde{Z}(0,   T_{k})=\frac{1}{N}\sum_{i=1}^{N}Z^{\prime}(0,   T_{k})$$

- The simulated values with $N=1000$ are reported in the next table,  together with the data used to fit the Ho-Lee tree model
![200](Pasted%20image%2020240426074214.png)

## SIMULATED HO-LEE BINOMIAL TREE: VALUATION OF AN INTEREST RATE OPTION
- The same valuation methodology can be used to price long-term options,  such as one paying at $i = 1,   …$

$$\mathrm{Payoff~at~}i=100\times\operatorname*{max}{\big(}r_{i}-r_{K}{\big)}$$

- Risk neutral pricing implies that the price of this option is given by

$$c_{0}(T_{i})=E^{*}\left[\mbox{Present value of payoff at$T_{i}$}\right]\tag{30}$$

 $$=E^{*}\left[e^{-(r_{i}+r_{i}-r_{i+1})\times\lambda}\times100\times\max\left(r_{i}-r_{K}\right)\right]\tag{31}$$

- For each simulation path $s$,  $r_{0}$,  $r_{1}^{*}$,  $r_{1}^{*}$,  $r_{2}^{*}$,  $r_{n}^{*}$,  $s=1,   \ldots,   N$,  we compute the discounted payoff $$c_{0}^{s}(T_{i})=e^{-(r_{i}+r_{1}^{*}+r_{2}^{*}-r_{K})\times\lambda}\times100\times\max\left(r_{i}^{*}-r_{K}\right)\tag{32}$$$$=Z^{*}(0,   T_{i})\times\times100\times\max\left(r_{i}^{*}-r_{K}\right)$$
- where we used $Z^s(0,    T_i) = e^{-(r_0+r_1^s+r_2^s+\ldots+r_{i-1}^s) \times \Delta}$.
- Today's value of the option with maturity $T_i$ is then given by the average of $c_0^s(T_i)$
  - $$ \hat{c}_0(T_i) = \frac{1}{N} \sum_{s=1}^N c_0^s(T_i) $$
- Today's value of the option with maturity $T_i$ is then given by the average of $c^s_0(T_i$)

$$\hat{c}_{0}(T_{i})=\frac{1}{N}\sum_{s=1}^{N}c_{0}^{s}(T_{i})\tag{33}$$

- Panel A of next table reports the value of interest rate options with maturity from $T_i = 0.5$ to $T_i = 5$ and for a strike rate $r_K = 1.74\%$.
- Panel B of next table shows the results of the first ten simulated discounted payoffs in (32).
- For instance,  the first element of the first row is given by

$$c_{0}^{1}(0.5)=Z^{1}(0,   0.5)\times100\times\max(r_{1}^{1}-r_{K})=0.9913\times100\times\max(1.30\%-1.74\%)=0$$

- where the sequence of the simulated interest rate and discounts are given in Panels B and C of previous table.
- Similarly,  the second entry in the first row is given by

$$c_{0}^{1}(1)=Z^{1}(0,   1)\times100\times\max(r_{2}^{1}-r_{K})=0.9849\times100\times\max(3.61\%-1.74\%)=1.85.$$

- The option values in Panel A are then computed as the average of values in the corresponding column in Panel B.
	- (although the average is taken over all the 1,  000 simulated paths,  rather than only the ten paths reported inPanel B).

![|500](Z.%20Clippings/Pasted%20image%2020240426074608.png)

## HOW MANY SIMULATIONS ARE ENOUGH?
- A price of a security computed by Monte Carlo Simulations is an estimate of the true price.
- Using simulations we are generating a *sample* of observations of the price of the security
- Because it is an estimate,  we can compute the price's standard error.

$$\text{Standard error} = \frac{\text{Standard deviation of }\{c_{0}^{1},   c_{0}^{2},   c_{0}^{3},   …,   c_{0}^{N}\}}{\sqrt{N}}$$

- For instance,  the first two rows in next Table reports the prices (again) and standard errors of the long-term interest call options discussed earlier.
![|500](Z.%20Clippings/Pasted%20image%2020240426074807.png)

## MONTE CARLO SIMULATIONS AND CONFIDENCE INTERVALS

- How small should a standard error be to make a trader confident on the price of the option? - The related concept of a (95%) confidence interval answers this question:

$$\text{Confidence interval}=[\hat{\text{c}}_{0}-2\times\text{St.E}\pi.,   \hat{\text{c}}_{0}+2\times\text{St.E}\pi.]$$

- There 95% probability that the true value $c_{0}$ is between the upper and lower boundary of the confidence interval.
- In previous Table,  the upper and lower boundaries of the confidence interval are reported in the third and fourth rows,  respectively.
	- The last row of the table reports the value of the option from the Binomial Tree itself.
	- In all but one case,  the true price is within the confidence interval. - Is this surprising?
		- No,  because there is only 95% chance that the true value lies within the confidence interval.
		- I.e. for 5% of the time,  the true value will *not* be within the confidence interval.
- The confidence intervals in the Table are quite wide,  and so no trader would use them.
- Raising the number of simulations reduces the spread in the confidence interval.

## LONG-TERM ASIAN OPTIONS
- At this point,  we can estimate the values of a long-term Asian options with maturities $T_i = 0.5,   …$.
- Next table computes the value (Panel A),  and the first 10 simulated discounted payoffs (Panel B).
 ![500](Pasted%20image%2020240426074915.png)
## DURATION CALCULATIONS BY MONTE CARLO SIMULATIONS

- How can we compute measures of risk if we use Monte Carlo simulations for valuation?
	- We can use Monte Carlo simulations to compute the "spot rate" duration defined as

$$\mbox{\small Spot rate duration}=-\frac{1}{P}\frac{dP}{dr}\approx-\frac{1}{P(r_{0})}\frac{\bar{P}(r_{0}+dr)-\bar{P}(r_{0})}{dr}\tag{34}$$

	- That is,    compute the price starting from $r_{0}$ and from $r_{0}+dr$. Then approximate the duration numerically.  
	+ Important: To avoid introducing simulation errors,    use the *same* realizations of the RAND() for the computation of the two prices.
- Does it work?
	- Panel A of next Table contains the duration approximation for zero coupon bonds. It works pretty nicely.
	- Panel B and C compute the durations for long-term options and Asian options discussed earlier. note:
		- First,  the duration of the interest rate call option is negative.
		- Second,  the duration of Asian options is also negative and higher than the one of plain vanilla options.
			- This may be surprising,  as Asian options' underlying (the average of interest rates) is less volatile than the interest rate itself.
			- However,  the price of an Asian option is also smaller. Thus,  in percentage,  the sensitivity of the Asian option to changes in interest rates is higher.

## DURATION CALCULATIONS BY MONTE CARLO SIMULATIONS

 ![500](Z.%20Clippings/Pasted%20image%2020240426075100.png)

## MONTE CARLO SIMULATIONS IN GENERAL

- The Monte Carlo simulation method is far more general than what I presented so far.
- For instance,  the Ho-Lee model also works with "continuous" shocks $$r_{t+\Delta t}=r_{t}+\theta_{t}\Delta t+\sigma\sqrt{\Delta t\varepsilon_{t+\delta}}$$
- where $\Delta t$ is a small interval of time,  and $$\varepsilon_{t+\Delta t}\sim N(0,   1)$$
- More generally,  we can have $$r_{t+\Delta t}=r_{t}+\mu(r_{t})\Delta t+\sigma(r_{t})\sqrt{\Delta t\varepsilon_{t+\delta}}$$
- for some function $µ(r_t)$ and $σ(r_t)$.
	- Important: The functions $µ(r_t)$ and $σ(r_t)$ must be estimated with securities data,  to obtain "risk neutral" (or risk adjusted) processes.
	- The methodology is an extension of what we did to estimate $θ_i$ with Ho-Lee model on trees.
- The price of a security with payoff $g(r_T)$ at maturity $T,   $ with a time interval $∆t = T/n$,  is

$$Z(0,   T)~=~E^{*}\left[e^{-\sum_{j=0}^{n-1}r_{j}\Delta t}\times g(r_{T})\right]\approx{\frac{1}{N}}\sum_{s=1}^{N}\left[e^{-\sum_{j=0}^{n-1}r_{j}^{s}\Delta t}\times g(r_{T}^{s})\right]$$