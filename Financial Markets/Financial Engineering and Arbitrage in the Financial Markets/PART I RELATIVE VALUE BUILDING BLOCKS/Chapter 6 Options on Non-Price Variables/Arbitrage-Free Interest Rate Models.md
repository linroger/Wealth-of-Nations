---
tags:
  - arbitrage_free_models
  - interest_rate_models
  - short_rate_models
  - swaptions
  - yield_curve
aliases:
  - AFIRM
  - IRM
  - Interest Rate Modeling
key_concepts:
  - Arbitrage-free model
  - Model calibration
  - Short rate models
  - Trinomial trees
  - Yield curve tilts
---

# 6.3 ARBITRAGE-FREE INTEREST RATE MODELS  

There are two good reasons for abandoning the simple Black model with convexity adjustments in favor of an arbitrage-free reduced-form model. First, it is the consistency of inputs which prevents the possibility of arbitraging oneself. The various Black model guises are. often used separately, with different inputs and adjustments, to price the same or similar structures. Bond options are European swaptions in disguise. CMS optionlets on shorter. rates are related to swaptions. Caps and floors are related to swaptions on short swap rates. Even very tight manual controls can sometimes fail to ensure that the models we use to. price these seemingly unrelated structures produce the same prices. The second reason for using an arbitrage-free model is that options come in a variety of exotic flavors and simple. adjustments may be difficult to derive. Many options, especially with American exercise features, require the modeling of the evolution of the entire yield curve and not just one main. driving rate.  

However, arbitrage-free modeling is not without a cost. The main cost is borne right at the start, in model calibration. These models impose a rigid structure on the evolution of interest rates allowing only for a deterministic time-dependent volatility structure. Yet we observe many caps and floors and many European swaptions with almost infinite combinations of option term and final swap term. We face an overdetermined system of too many inputs and only a few parameters to fit them with. The real world is messy and does not conform easily to a normal or log-normal reality, and exhibits skews. This necessarily implies that there is no guarantee that options not used directly in the calibration may not at times be mispriced. The second cost of arbitrage-free modeling is that because of its numeric complications, we sometimes focus on the trees and not the forest. We devote time to minutely calibrate a short-term tree, and we miss the fact that our model may only have one overriding stochastic factor that does not allow for yield curve tilts. So while we have a perfectly volatility-calibrated yield curve-fitted European swaption model, the model still misprices multiple American exercise features or options on the difference between the 10-year point. and the 2-year point. In this last case, the simpler, non-arbitrage-free model may actually be better!  

In this section, we review a few popular short rate models, and their most com-. mon numerical implementation through the use of trinomial trees, the general one-factor. Heath-Jarrow-Morton framework which subsumes most short rate models, and we finish with a two-factor approach of the LIBOR market model to addressing yield curve tilts..  

# 6.3.1 Short Rate Models  

We skip the discussion of early equilibrium models of Vasicek (1977), Rendleman and Bartter (1980), and Cox, Ingersoll, and Ross (1985), which attempt to endogenize how interest rates are formed from underlying economic activity, and focus on reduced-form no-arbitrage models.. Reduced-form models take the yield curve as a given and price derivatives relative to it. Short. rate models focus on describing the stochastic evolution of the instantaneous discount rate as moves through time. They have a non-stochastic mean, or drift, component, and a stochastic (random) component.  

They are usually identified by the underlying evolution equation written in continuous time,. where discrete changes $\Delta$ are replaced by instantaneous changes denoted with a small letter. $d$ . This is similar to standard calculus where, for example, we model the position of a train relative to the departure point as a variable $s=s(t)$ , which is a function of time $t$ . If the train is traveling at a constant speed $\nu$ then the function is simply $s=\nu\cdot t$ The change in the train's position, or the distance from the departure point, can be written in the form of a differential equation, as $d s=\nu\cdot d t$ . In differential calculus, the position equation $s=\nu\cdot t$ is referred to as a general solution to the differential equation $d s=\nu\cdot d t$ , which is also known as the equation of motion. We can then identify the constant parameters and impose some initial conditions, e.g. $\nu=60\mathrm{km}/h$ and $t_{o}=0:00\mathrm{am}$ l. If the train traveled for $d t=1$ h then the position is $s=60\cdot1=60\mathrm{km}$ away from the departure point. So the typical set-up is: define the instantaneous equation of motion for a variable of interest as a function of dependent variables; obtain the general solution for the current position of the dependent variable; and solve for the current position numerically relative to the starting point. In cases where we cannot obtain the general solution, we mimic the instantaneous equation of motion with a numerical tree or grid (e.g. a trinomial explicit tree) and obtain the solution numerically. That is, we have a computerized algorithm, instead of a neat mathematical function, to compute the dependent variable for any level of independent variables..  

In stochastic calculus, the set-up is the same as in the standard differential calculus, except that in addition to the deterministic independent time variable. $t$ , we add a stochastic independent variable $Z$ . All dependent variables of interest to us, and changes in them, depend on one. of these (time or random variable only) or both. Depending on the form of the equation of motion for an interest rate, we may or may not be able to obtain the general solution for the interest rate itself or derivatives on it. The models differ in the form of dependence on time and on the stochastic variable..  

In the Ho-Lee model (Ho and Lee, 1986), the instantaneous short rate changes are given a normal form:  

$$
\begin{array}{r}{d r=\mu(t)d t+\sigma d z}\end{array}
$$  

In this continuous time notation, the instantaneous change in the (instantaneous) short rate $r$ has a general time-dependent mean component $\mu(t)$ and a normal random component. In the latter, we have a constant volatility parameter $\sigma$ multiplying the normal variable $d z$ which is distributed, $N(0,d t)$ . So, if the current super-short ("overnight') discount rate is at $5\%$ and the annual volatility is $\sigma=0.1$ , then we are postulating that, in the absence of any drift, the short rate 1 month later at $t=1/12$ is normally distributed with a mean of $5\%$ and standard deviation of $0.1.\frac{1}{12}=0.8333\%.$ This necessarily means that interest rates in the model can be negative, although with very low probabilities. As written, the Ho-Lee model also imposes a rigid drift along the instantaneous forward curve on the evolution of the short rate $(\mu(t)$ can be derived analytically as a forward at $t$ plus $\sigma^{2}t$ ). The advantages of the model are that zero-coupon bond prices have an analytical solution simplifying the numerical implementation of the model.  

Hull and White (1990) improve the model by introducing mean reversion into the drift structure $\mu(t)$ . The differential equation is:.  

$$
d r=[\theta(t)-\alpha r]d t+\sigma d z
$$  

As written, the equation postulates that the short rate. $r$ drifts along the variable $\theta(t)/\alpha$ and if it moves away from that level as a result of a random shock, it reverts to that mean level with speed $\alpha$ . The mean reverting level is equal to the initial forward yield curve plus a small term. The Hull-White specification restricts the short rate away from extreme values and yields analytic formulas for bond prices, but still does not prevent negative interest rate values.  

The Black and Karasinski (1991) model does exactly that. The short rate is log-normal, rather than normal, and it is subject to mean reversion. The functional form is:  

$$
d r=[\theta(t)-\alpha(t)l n r]d t+\sigma(t)d z
$$  

The model is most appealing from the perspective of allowable interest rate movements . mean reversion, no negative values, and a time-dependent volatility structure -- but completely loses analytic tractability. The only way to use it is through a numeric implementation. Most commonly, this is done with the use of a trinomial tree..  

# 6.3.2 Trinomial Trees and Calibration  

Trinomial trees are discretized representations of continuous equations of motions. They are. equivalent to explicit methods of numerical analysis in mathematics. Instead of an instantaneous time movement $d t$ of an interest rate starting at the initial position $r_{0}=5\%$ at time $t_{0}=0$ along a continuous straight line representing time along the horizontal axis, we intro-. duce a small discrete step $\Delta t$ of segment-by-segment jumps of the rate $r$ along the horizontal axis. That is, time changes discretely, not continuously. The stochastic (random) nature of the. movement of the interest rate is accomplished by splitting the movement along the horizontal line (originally flat at $5\%$ ) into three discrete nodes in which the line can jump (up, middle, and down). The movement can then continue from each node (say $5.10\%$ $5\%$ $4.9\%$ ) separately along the time-segmentized line, with new jumps allowed on each new horizontal line. We therefore measure the level of the interest rate vertically, and time horizontally, and the interest rates are discretized in both dimensions. The discretization along the vertical axis is equivalent. to converting the assumed continuous normal or log-normal distribution to a trinomial and relying on the central limit theorem, with some stochastic calculus corrections, that with ever smaller $\Delta t$ steps the discrete and the continuous are going to be the same. If we construct a. dense enough tree, the algorithm will produce the same prices as the original equations would if they were solvable.  

![](6d4c5199dcbe110f83043d7e9bb15198c32678d4c6c08b19c5d4032823feac03.jpg)  
Figure 6.3 Examples of recombinant trinomial trees  

The typical trinomial tree is recombinant. Subsequent nodes of a node are the same as some of the subsequent nodes of another node, and there are multiple ways to get to any interior node. The recombinant feature reduces the number of calculation as it reduces the overall number of nodes, and allows the algorithm to handle American exercise options. The drift and mean reversion of interest rates are controlled jointly by assigning the interest rate levels for the nodes and the probabilities of jumping to those nodes. Parts (a) and (b) in Figures 6.3 show simple recombinant trinomial trees, both with instantaneous forward short-rate drifting up.  

In both trees, the up-jump followed by a middle-jump is the same as the middle-jump followed by an up-jump, and the same for down-middle sequences, i.e. either way the interest. rate ends up at the same level along the vertical axis after two time steps. That need not be the set-up of a trinomial tree. While tree (a) in Figure 6.3, does not allow any nodes with interest rates decreasing from $5\%$ at time $t_{0}$ and appears to be drifting up, tree (b) has the same drift up, owing to the way in which the probabilities of the nodes are assigned. Let us compute the. mean for the next time period $t_{1}$ . In tree (a), the mean is:  

$$
\bar{r}_{1}=\frac{1}{6}\cdot5.20+\frac{4}{6}+\cdot5.10+\frac{1}{6}\cdot5.00=5.10
$$  

In tree (b) the mean is:  

$$
\bar{r}_{1}=\frac{4}{6}\cdot5.20+\frac{1}{6}+\cdot5.00+\frac{1}{6}\cdot4.80=5.10
$$  

In the last time period $t_{3}$ , the mean for tree (a) is:  

$$
{\tilde{\mathbf{\tau}}}_{3}=\left({\frac{1}{6}}\right)^{3}\cdot5.60+3\left({\frac{1}{6}}\right)^{2}\left({\frac{4}{6}}\right)\cdot5.50+\cdot\cdot\cdot+3\left({\frac{1}{6}}\right)^{2}\left({\frac{4}{6}}\right)\cdot5.10+\left({\frac{1}{6}}\right)^{3}\cdot5.00=3{\mathrm{~m~e~}}^{-}
$$  

and for tree (b) is:  

$$
{\mathrm{~\boldmath~\sigma~}}_{3}=\left({\frac{4}{6}}\right)^{3}\cdot5.60+3\left({\frac{4}{6}}\right)^{2}\left({\frac{1}{6}}\right)\cdot5.40+\cdot\cdot\cdot+3\left({\frac{1}{6}}\right)^{2}\left({\frac{4}{6}}\right)\cdot4.60+\left({\frac{1}{6}}\right)^{3}\cdot4.40=5.
$$  

We compute these by observing that in each tree there are multiple ways to get to a given node at time $t_{3}$ . To compute the unconditional probabilities of each node, we cumulate the conditional probabilities across paths. For example, in tree (a), there are three ways to get to node $5.50\%$ at time $t_{3}$ : up-up-mid, up-mid-up, and mid-up-up, each path with probability $\left({\frac{1}{6}}\right)^{2}\left({\frac{4}{6}}\right)$  

We could similarly compute the unconditional variances for each time slice $t_{\mathrm{n}}$ by taking square deviations from the mean and weighting them by probabilities. At this point, the reader should be sensing how these variances may be related to the implied volatilities on caps and floors and how the reverse calibration process may proceed. Good examples of building trinomial trees for the Hull-White model are given in Hull and White (1996).  

We do not cover the details of the tree calibration process here except to point out the main restricting conditions that the tree algorithm must meet:  

The tree must price all zero-coupon bonds correctly: $\$100$ to be received at time. $t_{\mathrm{n}}$ assigned to each node at time slice. $t_{\mathrm{n}}$ discounted and probability-weighted backwards along the tree branches must produce the price of a zero-coupon bond maturing at time $t_{\mathrm{n}}$ The tree must price a target set of liquid caplets/floorlets and European swaptions; e.g. in. order to set the drift and volatility inputs, we consider a 1-year caplet on 3-month LIBOR; we build the tree out to time slice $t_{\mathrm{n}}=1$ year; for each final node, we recover the 3-month LIBOR analytically, or by continuing the tree for another 3 months, from the conditional 3-. month discount bonds; we search for a volatility input which, combined with the drift inputs,. will produce the correct price of the caplet when discounted and probability-weighted from. the pay time of the caplet backward in the tree all the way back to time $t_{0}$ ; we repeat the. procedure for caplet/floorlets with ever increasing expiry dates.  

Since the drift and volatility input parameters are time-dependent constants, there are only. so many inputs with which to match the traded prices of all the caps/floors and swaptions. The calibration process is in most cases overdetermined, and not all options prices can be matched. exactly.  

# 6.3.3 The Heath-Jarrow-Morton Model and the LIBOR Market Model  

The HJM model (Heath, Jarrow, and Morton, 1992) is often referred to as the best no-arbitrage interest model. In fact, it is simply a generalized framework of no-arbitrage conditions that interest rate models must satisfy. The HJM argument starts by postulating a general process for the set of all instantaneous forward rates maturing at time $\tau$ for periods $(\tau,\tau+1)$ . It then derives the link between the drift term and the general volatility term that all models must satisfy. In the most general form of the model, the short rates are non-Markov, i.e. they are path dependent, which means that recombinant trees cannot be built for them. However, one can impose restrictions on the general form to reduce the general HJM framework to Markov forms, and one can show that all no-arbitrage short-term models are special cases of it.  

The subtle point about the HJM frameworks is that when modeling the forward rates, rather than short rates, the solution for the drift term in the risk-neutral world depends only on the volatility parameters and does not include the unknown equilibrium price of risk. That is often not so in short rate models unless one skips directly to the risk-neutral world, but that then renders the interpretation of volatility and drift parameters difficult (e.g. not directly translatable to Black-Scholes volatilities).  

Here is the general idea of the HJM framework in a three-step numerical example. The simplifying assumptions and the notation are as follows..  

We use a binomial tree with annual steps $\Delta t=1$ from time $t=0$ to time $t=3$ years from now. We denote by $f_{t}(\tau,\tau+1)$ the continuously compounded forward rate at time $t$ for year $\tau$ , e.g. $f_{0}(0,1)$ is the forward rate today for the period from today to 1 year from today, i.e. the 1-year spot rate, and $f_{0}(1,2)$ is today's forward rate for the period from 1 year to 2 years from today. We use superscripts $u$ and $d$ repeatedly to denote the up and down steps.   
The model is normal, rather than log-normal. We take the starting yield curve at time $t$ and we add the drift and the volatility, $f_{t}(\tau,\tau+1)+\theta_{t}(\tau,\tau+1)\Delta t\pm\sigma(\tau,\tau+1)\Delta t$ , instead   
of multiplying it to get expressions like $f_{t}(\tau,\tau+1)e^{\theta(\tau)\Delta t\pm\sigma(\tau)\Delta t}$ To get a recombinant tree we set the probability of the up state equal to the probability of the down state and equal to $^1/_{2}$ , i.e. $\begin{array}{r}{q=1-q=\frac{1}{2}}\end{array}$ , and we set the volatility to be constant for each forward maturity $\tau$ , i.e. $\sigma$ only has a $\tau,\tau+1$ index, but does not have a time $t$ subscript. We assume that initially at time $t=0$ , the forward 1-year rates for years 0, 1, and 2 are $f_{0}(0,1)=4.8\%$ $f_{0}(1,2)=5.0\%$ and $f_{0}(2,3)=5.2\%$ , respectively. The volatility of the $1\times2$ forward rate is $\sigma(1,2)=0.02$ (equivalent to $40\%$ log-normal, $0.02=0.05\times0.40)$ and the volatility of the $2\times3$ forward rate is $\sigma(2,3)=0.03$  

The set-up is depicted in Figure 6.4. It follows the Black-Scholes set-up of Chapter 5, the only exception being the issue of fixing the drift terms for the diffusion in the tree through a bootstrap. To do this, we use the no-arbitrage restriction that the tree must price each successive maturity zero-coupon bond correctly.  

$$
\begin{array}{l}{{f_{1}^{u}(1,2)=f_{0}(1,2)+{\theta_{0}}(1,2)+\sigma\left(1,2\right)=0.050+\theta_{0}(1,2)+0.02}}\ {{f_{1}^{u}(2,3)=f_{0}(2,3)+{\theta_{0}}(2,3)+\sigma\left(2,3\right)=0.052+\theta_{0}(2,3)+0.03}}\end{array}
$$  

fo (0, 1) = 4.8% $f_{0}\left(1,2\right)=5.0\%$ $f_{0}\left(2,3\right)=5.2\%$  

$$
\begin{array}{l}{{f_{1}^{d}(1,2)=f_{0}(1,2)+{\theta_{0}}(1,2)+\sigma\left(1,2\right)=0.050+\theta_{0}(1,2)-0.02}}\ {{f_{1}^{d}(2,3)=f_{0}(2,3)+{\theta_{0}}(2,3)+\sigma\left(2,3\right)=0.052+\theta_{0}(2,3)-0.03}}\end{array}
$$  

![](4eccfcecb747eb4e96a13619003bcaf7cb462bf75917a73e242109d2f28137f0.jpg)  
Figure 6.5 A one-factor three-step HJM model continued  

To fix the drift term $\theta_{0}(1,2)$ , we price the 2-year $\$100$ zero-coupon bond. We sweep backwards through the tree, probability weighting the values of 1-year discount bonds in the up and down states at time $t=1$ , and discounting them by 1 year to time $t=0$  

$$
P_{0}(0,2)=e^{-0.048}\times\left(\frac{1}{2}e^{-0.07-\theta_{0}(1,2)}\times100+\frac{1}{2}e-0.03-\theta_{0}(1,2)\times100\right)
$$  

From today's yield curve, we know that the 2-year zero-coupon bond is worth:  

$$
P_{0}(0,2)=100\times e^{-0.048}\times e^{-0.05}=90.665
$$  

Setting the two equations equal, we get. $\theta_{0}(1,2)=0.00020$ .We also get the two. $1\times2$ forward rates in the up and down states at time $t=1$  

$$
f_{1}^{u}(1,2)=7.02\%\quad\mathrm{and}\quad f_{1}^{d}(1,2)=3.02\%
$$  

Next we can fix the $\theta_{0}(2,3)$ drift term by pricing the 3-year zero-coupon bond and setting its value equal to:  

$$
P_{0}(0,3)=100\times e^{-0.048}\times e^{-0.05}\times e^{-0.052}=86.071
$$  

We use the newly computed $f_{1}(1,2)$ values at time $t=1$ to probability weight the values. of discount bonds with 2 years left to maturity in the up and down states at time $t=1$ ; we discount them by 1 year to time $t=0$  

$$
\begin{array}{l}{{\displaystyle{\tt\partial\rho}_{0}(0,3)=e^{-0.048}}}\ {{\displaystyle\qquad\times\left(\frac12e^{-0.0702}\times e-0.082-\theta_{0}(2,3)\times100+\frac12e^{-0.0302}\times e^{-0.022-\theta_{0}(2,3)}\times100+\frac12e^{-0.0302}\times e^{-0.022-\theta_{0}(3,3)}\right)=0.}}\end{array}
$$  

Setting this equal to 86.071, we get $\theta_{0}(2,3)=0.001049$ and the two $2\times3$ forward rates in. the up and down states at time. $t=1$  

$$
f_{1}^{u}(2,3)=8.30495\%\quad\mathrm{and}\quad f_{1}^{d}(2,3)=2.30495\%
$$  

The next step is to go to time. $t=2$ and, again, given the volatility. $\sigma(2,3)=0.03$ and today's price of the 3-year zero-coupon bond, to fix the drift term $\theta_{1}(2,3)$  

$$
f_{2}^{u u}\left(2,3\right)=11.35\%
$$  

fo (0, 1) = 4.8% fo (1, 2) = 5.0% $f_{0}\left(2,3\right)=5.2\%$  

$$
f_{2}^{u d}\left(2,3\right)=5.35\%
$$  

$$
\begin{array}{c}{{f_{1}^{d}(1,2)}}\ {{f_{1}^{d}(2,3)}}\end{array}=\begin{array}{c}{{3.02000\%}}\ {{2.30495\%}}\end{array}
$$  

$$
f_{2}^{d d}\left(2,3\right)=-0.65\%
$$  

We use the price of the 3-year zero-coupon bond to fix the last drift term:  

$$
\begin{array}{l}{{P_{0}(0,3)=e^{-0.048}}}\ {{\displaystyle\times\left[\frac12\times e^{-0.0702}\times\left(\frac12e^{-0.1130495-\theta_{1}(2,3)}\times100+\frac12e^{-0.0530495-\theta_{1}(2,3)}\times100\right)\right.}}\ {{\displaystyle\left.+\frac12\times e^{-0.0302}\times\left(\frac12e^{-0.0530495-\theta_{1}(2,3)}\times100+\frac12e^{+0.006951-\theta_{1}(2,3)}\times100\right)\right.}}\end{array}
$$  

We set this value equal to 86.071, to get $\theta_{1}(2,3)=0.00045$ and the final forward rates:  

$$
f_{2}^{u u}(2,3)=11.35\%,f_{2}^{u d}(2,3)=5.35\%,
$$  

Figure 6.6 shows the final tree for the evolution of the forward curve. Here is the summary of the important points about our HJM exercise:.  

We have chosen $\sigma(1,2)=0.02$ and $\sigma(2,3)=0.03$ first. In reality, these two would have. to be bootstrapped from the prices of caplets setting 1 and 2 years from today, and paying 2 and 3 years from today. Thus, we would end up with a joint or nested bootstraps in the following order:. $\bigcirc$ fit the volatility $\sigma(1,2)$ and the drift $\theta_{0}(1,2)$ to hit the first caplet and the 2-year zero; then $\bigcirc$ fit the volatility. $\sigma(2,3)$ and the drifts. $\theta_{0}(2,3)$ and $\theta_{1}(2,3)$ to hit the second caplet and the 3-year zero.   
We have some degree of freedom (three drifts and two volatilities) on the structure of the drifts and volatilities, so we can either impose restrictions (smoothness), or fit additional securities, like a 1-into-2 European swaption..   
Changing to a log-normal forward model is quite easy. Replace the additive drift and diffusion (volatility) terms with exponential terms. This would preclude our negative rate in the down-down node of the time $t=2$ step. All non-option bonds will be priced perfectly in our tree. All calibrating options will be priced correctly. And the model is arbitrage free overall and step-by-step..   
The model as described is still one factor with maturity-dependent volatility structure.  

While the HJM framework can be extended to many factors, the numerical complexity of it and calibration issues make even two-factor extensions very difficult. To accommodate two factors in our tree set-up, we would have to introduce in the diffusion equations at least one additional volatility term for the second factor (and perhaps one more drift term). This alone. would necessitate at least a trinomial. It would also significantly complicate the calibration to caplets. What other security would we have to choose at the first step of the bootstrap to. fix the drift term and two volatility terms? It would have to be an option whose value was sensitive to more than one factor. In our model a caplet setting in one year and a 1-into-1 swaption are identical. If the tree was more finely sliced into shorter time steps, we could try to fit caplets/floorlets and longer swaptions at the same time, but even that most likely would not. help. Caps and short European swaptions are not multifactor sensitive options. Their values. depend mostly on the volatility of the entire yield curve and not so much on the correlation. structure which drives tilts and non-parallel moves. To properly calibrate the model, we would need to introduce multiple-exercise options (like Bermudans) or yield curve options..  

As a more tractable extension of HJM, Brace, Gatarek, and Musiela (1997), and others, have proposed a non-arbitrage-free framework of modeling directly discrete LIBOR forwards instead of instantaneous forwards from which all other rates have to be recovered. This approach simplifies implementation and calibration since the nodes have LIBOR forwards, very much like in our example implementation in Figures 6.4 to 6.6. The HJM actually models instantaneous forward from which actual LIBOR forward have to be recovered. BGM models LIBORs directly. This makes hitting cap prices trivial, but at the expense of delinking rates. of different maturities from each other under the same risk-neutral measure. It does, however,. allow an easy introduction of additional volatility factors. The numerical procedure is often a non-recombinant tree or Monte Carlo..  

# 6.3.4 Bermudan Swaptions and Multifactor Models  

The HJM and BGM model frameworks can both be extended to more than one stochastic factor. To appreciate the importance of having such a model, consider a Bermudan swaption. Suppose the yield curve is flat at. $5\%$ and you purchase the right to enter into a pay-fixed $5\%$ interest rate swap. Your right is exercisable every 6 months for the next 5 years. Upon exercise, the swap you will enter into will have a final maturity of 10 years from today. The. structure described would be referred to as a 5-into-5 Bermudan put swaption. The equivalent European swaption would have only one exercise time in 5 years and upon exercise, the swap we would enter into would have another 5 years left to maturity. The Bermudan swaption gives us the multiple exercise rights. Today we can exercise into a 10-year swap, in 6 months we can exercise into a 9.5-year swap, in one year we can exercise into a 9-year swap, etc. If the yield curve is not flat, but upward sloping from $3\%$ to $5\%$ , then the most likely exercise. point is 5 years from today. If the yield curve is flat at $5\%$ , then exercising today, in 5 years. and anywhere in between is approximately equally likely. In a one-factor model, the yield curve moves in parallel with today's entire curve, up or down. This is not a problem in valuing a one-time exercise European swaption. In fact, we have shown that we can do that in a Black-Scholes model just as well as in a complicated term-structure model with the use of simple convexity adjustments. Suppose, however that, we use a short rate term structure model to value the Bermudan. The exercise right will be evaluated correctly at each node by comparing the discounted value of future exercise to the immediate exercise value. Yet what will be missing is any allowance for non-parallel yield curve moves. In a short-term model, the allowable yield curve moves do not include tilting and inversion. An inversion from a flat yield curve at $5\%$ would clearly favor early exercise of the put swaption. The unfortunate fact is that a one-factor model cannot even tell how much that extra "volatility"' of the yield curve is worth, because tilts cannot be accommodated in it. On the flip side, a two-factor model would have to be calibrated to curve tilt-sensitive options, like other Bermudans or spread options,. through one or more correlation inputs..  
