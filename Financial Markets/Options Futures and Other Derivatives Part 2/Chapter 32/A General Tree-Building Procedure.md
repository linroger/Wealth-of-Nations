# 32.5 A GENERAL TREE-BUILDING PROCEDURE  

Hull and White have proposed a robust two-stage procedure for constructing trinomial. trees to represent a wide range of one-factor models.' This section first explains how the procedure can be used for the Hull-White model in equation (32.4) and then shows. how it can be extended to represent other models, such as Black-Karasinski..  

# First Stage  

The Hull-White model for the instantaneous short rate $r$ is  

$$
\begin{array}{r}{d r}{\boldsymbol{\it{\/}}d\boldsymbol{\it{\/}}r=\left[\theta(t)-a r\right]d t+\sigma d\boldsymbol{\it{z}}}\end{array}
$$  

We suppose that the time step on the tree is constant and equal to $\Delta t$ 8.  

Assume that the $\Delta t$ rate, $R$ , follows the same process as $r$  

$$
d R=[\theta(t)-a R]d t+\sigma d z
$$  

Clearly, this is reasonable in the limit as $\Delta t$ tends to zero. The first stage in building a tree for this model is to construct a tree for a variable $R^{*}$ that is initially zero and follows the process  

$$
d R^{*}=-a R^{*}d t+\sigma d z
$$  

This process is symmetrical about $\boldsymbol{R}^{*}=\boldsymbol{0},$ The variable $\boldsymbol{R}^{*}(t+\Delta t)-\boldsymbol{R}^{*}(t)$ is normally distributed. If terms of higher order than $\Delta t$ are ignored, the expected value of $\boldsymbol{R}^{*}(t+\Delta t)-\boldsymbol{R}^{*}(t)$ is $-a\boldsymbol{R}^{*}(t)\Delta t$ and the variance of $R^{*}(t+\Delta t)-R^{*}(t)$ is $\sigma^{2}\Delta t$  

![](3ec933a2ea0765320089f2b42abe48ac0ce20098e8e10d7ea608d4b011e2ee5c.jpg)  
Figure 32.6 Tree for $R^{*}$ in Hull-White model (first stage).  

The spacing between interest rates on the tree, $\Delta R$ , is set as  

$$
\Delta R=\sigma\sqrt{3\Delta t}
$$  

This proves to be a good choice of $\Delta R$ from the viewpoint of error minimization.  

The objective of the first stage of the procedure is to build a tree similar to that shown in Figure 32.6 for $R^{*}$ . To do this, it is first necessary to resolve which of the three. branching methods shown in Figure 32.5 will apply at each node. This will determine the overall geometry of the tree. Once this is done, the branching probabilities must also. be calculated.  

Define $(i,j)$ as the node where $t=i\Delta t$ and $\boldsymbol{R}^{*}=j\Delta\boldsymbol{R}$ (The variable $i$ is a positive integer and $j$ is a positive or negative integer.) The branching method used at a node must lead to the probabilities on all three branches being positive. Most of the time, the branching shown in Figure $32.5\mathrm{a}$ is appropriate. When. $a>0$ , it is necessary to switch from the branching in Figure 32.5a to the branching in Figure 32.5c for a sufficiently large $j.$ Similarly, it is necessary to switch from the branching in Figure $32.5\mathrm{a}$ to the branching in Figure $32.5\mathrm{b}$ when $j$ is sufficiently negative. Define $j_{\mathrm{max}}$ as the value of $j$ where we switch from the Figure $32.5\mathrm{a}$ branching to the Figure $32.5\mathrm{c}$ branching and $j_{\mathrm{min}}$ as the value of $j$ where we switch from the Figure $32.5\mathrm{a}$ branching to the Figure 32.5b branching. Hull and White show that probabilities are always positive if $j_{\mathrm{max}}$ is set equal to the smallest integer greater than $0.184/(a\Delta t)$ and $j_{\mathrm{min}}$ is set equal to $-j_{\mathrm{max}}$ 9 Define $p_{u},p_{m}$ , and $p_{d}$ as the probabilities of the highest, middle, and lowest branches emanating from the node. The probabilities are chosen to match the expected change and variance of the change in $R^{*}$ over the next time interval $\Delta t$ The probabilities must also sum to unity. This leads to three equations in the three probabilities.  

As already mentioned, the mean change in. $\boldsymbol{R}^{*}$ in time $\Delta t$ is $-a\boldsymbol{R}^{*}\Delta t$ and the variance of the change is $\sigma^{2}\Delta t.$ At node $(i,j),\boldsymbol{R}^{*}=j\Delta R$ If the branching has the form shown. in Figure 32.5a, the. $p_{u},p_{m}$ and $p_{d}$ at node $(i,j)$ must satisfy the following three. equations to match the mean and standard deviation:  

$$
\begin{array}{c}{{p_{u}\Delta R-p_{d}\Delta R=-a j\Delta R\Delta t}}\ {{p_{u}\Delta R^{2}+p_{d}\Delta R^{2}=\sigma^{2}\Delta t+a^{2}j^{2}\Delta R^{2}\Delta t^{2}}}\ {{p_{u}+p_{m}+p_{d}=1}}\end{array}
$$  

Using $\Delta R=\sigma\sqrt{3\Delta t}.$ the solution to these equations is  

$$
\begin{array}{r l}&{p_{u}=\frac{1}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}-a j\Delta t)}\ &{p_{m}=\frac{2}{3}-a^{2}j^{2}\Delta t^{2}}\ &{p_{d}=\frac{1}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}+a j\Delta t)}\end{array}
$$  

Similarly, if the branching has the form shown in Figure 32.5b, the probabilities are  

$$
\begin{array}{r}{p_{u}=\frac{1}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}+a j\Delta t)}\ {p_{m}=-\frac{1}{3}-a^{2}j^{2}\Delta t^{2}-2a j\Delta t}\ {p_{d}=\frac{7}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}+3a j\Delta t)}\end{array}
$$  

Finally, if the branching has the form shown in Figure 32.5c, the probabilities are  

$$
\begin{array}{r}{p_{u}=\frac{7}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}-3a j\Delta t)}\ {p_{m}=-\frac{1}{3}-a^{2}j^{2}\Delta t^{2}+2a j\Delta t}\ {p_{d}=\frac{1}{6}+\frac{1}{2}(a^{2}j^{2}\Delta t^{2}-a j\Delta t)}\end{array}
$$  

To illustrate the first stage of the tree construction, suppose that $\sigma=0.01,a=0.1$ and $\Delta t=1$ year. In this case, $\Delta R=0.01\sqrt{3}=0.0173,\widehat{j_{\operatorname*{max}}}$ is set equal to the smallest integer greater than $0.184/0.1$ and $j_{\mathrm{min}}=-j_{\mathrm{max}}.$ This means that. $j_{\mathrm{max}}=2$ and $j_{\mathrm{min}}=-2$ and the tree is as shown in Figure 32.6. The probabilities on the branches. emanating from each node are shown below the tree and are calculated using the equations above for $p_{u},p_{m}$ and $p_{d}$  

Note that the probabilities at each node in Figure 32.6 depend only on $j$ For example, the probabilities at node B are the same as the probabilities at node F Furthermore, the tree is symmetrical. The probabilities at node $\mathrm{\bfD}$ are the mirror image of the probabilities at node B.  

# Second Stage  

The second stage in the tree construction is to convert the tree for $R^{*}$ into a tree for $R$ This is accomplished by displacing the nodes on the. $R^{*}$ -tree so that the initial term.  

structure of interest rates is exactly matched. Define  

$$
\alpha(t)=R(t)-R^{*}(t)
$$  

The $\alpha(t)$ 's that apply as the time step $\Delta t$ on the tree becomes infinitesimally small can be calculated analytically from equation (32.5).10 However, we want a tree with a finite $\Delta t$ to match the term structure exactly, so we use an iterative procedure to determine the $\alpha$ 's.  

Define $\alpha_{i}$ as $\alpha(i\Delta t)$ , the value of $R$ at time i $\Delta t$ on the $R$ -tree minus the corresponding value of $\boldsymbol{R}^{*}$ at time $i~\Delta t$ on the $\boldsymbol{R}^{*}$ tree. Define $Q_{i,j}$ as the present value of a security that pays off $\$1$ if node $(i,j)$ is reached and zero otherwise. The $\alpha_{i}$ and $Q_{i,j}$ can be calculated using forward induction in such a way that the initial term structure is matched exactly.  

# Illustration of Second Stage  

Suppose that the continuously compounded zero rates in the example in Figure 32.6 are as shown in Table 32.1. The value of $Q_{0,0}$ is 1.0. The value of $\alpha_{0}$ is chosen to give the. right price for a zero-coupon bond maturing at time. $\Delta t$ That is, $\alpha_{0}$ is set equal to the initial $\Delta t$ -period interest rate. Because. $\Delta t=1$ in this example, $\alpha_{0}=0.03824$ . This defines the position of the initial node on the. $R$ -tree in Figure 32.7. The next step is to calculate the values of. $Q_{1,1},Q_{1,0}$ and $\mathcal{Q}_{1,-1}$ . There is a probability of 0.1667 that the. $(1,1)$ node is reached and the discount rate for the first time step is. $3.82\%$ . The value of $Q_{1,1}$ is therefore $0.1667e^{-0.03824}=0.1604.$ Similarly, $Q_{1,0}=0.6417$ and $Q_{1,-1}=0.1604$  

Once $Q_{1,1},Q_{1,0}$ and $\scriptstyle Q_{1,-1}$ have been calculated, $\alpha_{1}$ can be determined. It is chosen to give the right price for a zero-coupon bond maturing at time $2\Delta t.$ Because $\Delta R=0.01732$ and $\Delta t=1$ , the price of this bond as seen at node $\mathrm{B}$ .5 $e^{-(\alpha_{1}+0.01732)}$ . Similarly, the price as seen at node $\mathrm{C}$ $e^{-\alpha_{1}}$ and the price as seen at node $\mathrm{\bfD}$ .5 $e^{-(\alpha_{1}-0.01732)}$ .The price as seen at the initial node A is therefore  

$$
Q_{1,1}e^{-(\alpha_{1}+0.01732)}+Q_{1,0}e^{-\alpha_{1}}+Q_{1,-1}e^{-(\alpha_{1}-0.01732)}
$$  

From the initial term structure, this bond price should be $e^{-0.04512\times2}=0.9137$  

Table 32.1 Zero rates for example in Figures 32.6 and 32.7.   


<html><body><table><tr><td>Maturity</td><td>Rate (%)</td></tr><tr><td>0.5</td><td>3.430</td></tr><tr><td>1.0</td><td>3.824</td></tr><tr><td>1.5</td><td>4.183</td></tr><tr><td>2.0</td><td>4.512</td></tr><tr><td>2.5</td><td>4.812</td></tr><tr><td>3.0</td><td>5.086</td></tr></table></body></html>  

$$
d R=[\theta(t)-a R]d t+\sigma d z\quad{\mathrm{and}}\quad d R^{*}=-a R^{*}d t+\sigma d z
$$  

so that $d\alpha=\left[\theta(t)-a\alpha(t)\right]c$ lt. Using equation (32.7), it can be seen that the solution to this is  

$$
\alpha(t)=F(0,t)+\frac{\sigma^{2}}{2a^{2}}(1-e^{-a t})^{2}.
$$  

![](7d4d73ea5e92ae6a7faff831342dbcfdb8293e22794f16a265a85c31878d71ae.jpg)  
Figure 32.7 Tree for $R$ in Hull-White model (the second stage).  

Substituting for the $Q$ s in equation (32.11),  

$$
0.1604e^{-(\alpha_{1}+0.01732)}+0.6417e^{-\alpha_{1}}+0.1604e^{-(\alpha_{1}-0.01732)}=0.9137
$$  

or  

$$
e^{-\alpha_{1}}(0.1604e^{-0.01732}+0.6417+0.1604e^{0.01732})=0.9137
$$  

or  

$$
\alpha_{1}=\mathrm{ln}\bigg[\frac{0.1604e^{-0.01732}+0.6417+0.1604e^{0.01732}}{0.9137}\bigg]=0.05205
$$  

This means that the central node at time $\Delta t$ in the tree for $R$ corresponds to an interest rate of $5.205\%$ (see Figure 32.7).  

The next step is to calculate $Q_{2,2},Q_{2,1},Q_{2,0},Q_{2,-1}$ , and $Q_{2,-2}$ . The calculations can be shortened by using previously determined $Q$ values. Consider $Q_{2,1}$ as an example.. This is the value of a security that pays off $\$1$ if node $\mathrm{F}$ is reached and zero otherwise. Node F can be reached only from nodes B and C. The interest rates at these nodes are $6.937\%$ and $5.205\%$ , respectively. The probabilities associated with the $\mathrm{B-F}$ and $\mathrm{C-F}$ branches are 0.6566 and 0.1667. The value at node $\mathrm{B}$ of a security that pays $\$1$ at node $\mathrm{F}$ is therefore $0.6566e^{-0.06937}$ . The value at node $\mathrm{C}$ is $0.1667e^{-0.05205}$ . The variable $Q_{2,1}$ is $0.6566e^{-0.06937}$ times the present value of $\$1$ received at node B plus $0.1\dot{6}67e^{-0.05205}$ times the present value of $\$1$ received at node C; that is,  

$$
\mathcal{Q}_{2,1}=0.6566e^{-0.06937}\times0.1604+0.1667e^{-0.05205}\times0.6417=0.1998
$$  

$$
,Q_{2,2}=0.0182,Q_{2,0}=0.4736,Q_{2,-1}=0.2033,\mathrm{and}Q_{2,-2}=0.01
$$  

The next step in producing the $R$ -tree in Figure 32.7 is to calculate $\alpha_{2}$ After that, the $Q_{3,j}$ s can then be computed. The variable $\alpha_{3}$ can then be calculated, and so on.  

# Formulas for $\pmb{\alpha}^{\prime}\pmb{S}$ and Q's  

To express the approach more formally, suppose that the $Q_{i,j}$ have been determined for $i\le m(m\ge0)$ . The next step is to determine. $\alpha_{m}$ so that the tree correctly prices a zero-. coupon bond maturing at $(m+1)\Delta t.$ The interest rate at node. $(m,j)$ is $\alpha_{m}+j\Delta R$ , so that the price of a zero-coupon bond maturing at time $(m+1)\Delta t$ is given by  

$$
P_{m+1}=\sum_{j=-n_{m}}^{n_{m}}Q_{m,j}\exp[-(\alpha_{m}+j\Delta R)\Delta t]
$$  

where $n_{m}$ is the number of nodes on each side of the central node at time m $\Delta t$ The solution to this equation is  

$$
\alpha_{m}=\frac{\ln{\sum_{j=-n_{m}}^{n_{m}}Q_{m,j}e^{-j\Delta R\Delta t}-\ln P_{m+1}}}{\Delta t}
$$  

Once $\alpha_{m}$ has been determined, the $Q_{i,j}$ for $i=m+1$ can be calculated using  

$$
Q_{m+1,j}=\sum_{k}Q_{m,k}q(k,j)\exp[-(\alpha_{m}+k\Delta R)\Delta t]
$$  

where $q(k,j)$ is the probability of moving from node $(m,k)$ to node $(m+1,j)$ and the summation is taken over all values of $k$ for which this is nonzero.  

# Extension to Other Models  

The procedure that has just been outlined can be extended to more general models of the form  

$$
d f(r)=[\theta(t)-a f(r)]d t+\sigma d z
$$  

where $f$ is a monotonic function of. $r.$ This family of models has the property that they can fit any term structure.11  

As before, we assume that the $\Delta t$ period rate, $R$ , follows the same process as $r$  

$$
d f(R)=[\theta(t)-a f(R)]d t+\sigma d z
$$  

We start by setting $x=f(R)$ , so that  

$$
 d x=[\theta(t)-a x]d t+\sigma d z
$$  

The first stage is to build a tree for a variable $x^{*}$ that follows the same process as $x$ except that $\theta(t)=0$ and the initial value is zero. The procedure here is identical to the procedure already outlined for building a tree such as that in Figure 32.6.  

As in Figure 32.7, the nodes at time $i\Delta t$ are then displaced by an amount $\alpha_{i}$ to provide an exact fit to the initial term structure. The equations for determining $\alpha_{i}$ and $Q_{i,j}$ inductively are slightly different from those for the $f(R)=R$ case. The value of $Q$ at the first node, $Q_{0,0}$ , is set equal to 1. Suppose that the $Q_{i,j}$ have been determined for $i\leq m$ $(m\ge0)$ ). The next step is to determine. $\alpha_{m}$ so that the tree correctly prices an $(m+1)\Delta t$ zero-coupon bond. Define. $g$ as the inverse function of. $f$ so that the $\Delta t$ -period interest rate at the. $j$ th node at time m $\Delta t$ is  

$$
g(\alpha_{m}+j\Delta x)
$$  

The price of a zero-coupon bond maturing at time $(m+1)\Delta t$ is given by  

$$
P_{m+1}=\sum_{j=-n_{m}}^{n_{m}}Q_{m,j}\exp[-g(\alpha_{m}+j\Delta x)\Delta t]
$$  

This equation can be solved using a numerical procedure such as Newton-Raphson The value $\alpha_{0}$ of $\alpha$ when $m=0$ , is $f(R(0))$  

Once $\alpha_{m}$ has been determined, the $Q_{i,j}$ for $i=m+1$ can be calculated using  

$$
Q_{m+1,j}=\sum_{k}Q_{m,k}q(k,j)\exp[-g(\alpha_{m}+k\Delta x)\Delta t]
$$  

where $q(k,j)$ is the probability of moving from node $(m,k)$ to node $(m+1,j)$ and the summation is taken over all values of $k$ where this is nonzero.  

![](f7a0ab1da9db44fe3263e038e19337f87e6ca5736bd48883ddf67d4c8e029022.jpg)  
Figure 32.8 Tree for lognormal model.  

Figure 32.8 shows the results of applying the procedure to the Black-Karasinski model in equation (32.9):  

$$
d\ln(r)=[\theta(t)-a\ln(r)]d t+\sigma d z
$$  

when $a=0.22,\sigma=0.25$ $\Delta t=0.5$ , and the zero rates are as in Table 32.1.  

Setting $f(r)=r$ leads to the Hull-White model in equation (32.4); setting. $f(r)=\ln(r)$ leads to the Black-Karasinski model in equation (32.9). The main advantage of the $f(r)=r$ model is its analytic tractability.  

# Negative Rates  

Traditionally the main disadvantage of Hull-White has been that it allows interest rates to become negative. Some analysts have been reluctant to use a model where there is. any chance at all of negative rates and have therefore preferred $f(r)=\ln(r)$ even though it has no analytic tractability.  

This aversion to models that give rise to negative rates has changed somewhat in recent years because, as mentioned in earlier chapters, negative interest rates have become a feature of financial markets in some countries. The Ho-Lee and Hull-White models are similar in spirit to the Bachelier normal model discussed in Section 29.2.12. They can be used to value nonstandard deals in negative interest rate environments. An alternative is to use a "shifted Black-Karasinski" model. In this,. $r+\alpha$ rather than $r$ is assumed to follow the process in equation (32.9), so that.  

$$
d\ln(r+\alpha)=[\theta(t)-a\ln(r+\alpha)]d t+\sigma d z
$$  

The short-term interest rate can then become (almost) as low as $-\alpha$  

# Multiple Yield Curves  

The yield curve used for discounting is the risk-free zero curve obtained from the overnight indexed swaps (OIS) market. Up to now, we have implicitly assumed that this is also the yield curve determining payoffs on the derivative so that derivatives can be valued by modeling this one yield curve. When the payoffs depend on another yield. curve (e.g., the Treasury curve or a curve corresponding to risky borrowing), an analyst has to construct a model incorporating movements in both curves. One approach is to. use the methods discussed in this chapter to model the risk-free (OiS) short rate and set the spreads between the two rates at future times equal to the spreads between the forward rates calculated from the two yield curves today. A more sophisticated. approach is to use a three-dimensional tree where two short rates are modeled.13.  

# Using Analytic Results in Conjunction with Trees  

When a tree is constructed for the $f(r)=r$ version of the Hull-White model, the analytic results in Section 32.1 can be used to provide the complete term structure  

and European option prices at each node. It is important to recognize that the interest rate on the tree is the. $\Delta t$ period rate $R$ . It is not the instantaneous short rate. $r$  

From equations (32.6), (32.7), and (32.8), it can be shown (see Problem 32.15) that  

$$
P(t,T)=\hat{A}(t,T)e^{-\hat{B}(t,T)R}
$$  

where  

$$
\begin{array}{l}{{\mathrm{ln}\hat{A}(t,T)=\mathrm{ln}\frac{P(0,T)}{P(0,t)}-\frac{B(t,T)}{B(t,t+\Delta t)}\mathrm{ln}\frac{P(0,t+\Delta t)}{P(0,t)}}}\ {{-\frac{\sigma^{2}}{4a}(1-e^{-2a t})B(t,T)[B(t,T)-B(t,t+\Delta t)]}}\end{array}
$$  

and  

$$
\hat{B}(t,T)=\frac{B(t,T)}{B(t,t+\Delta t)}\Delta t
$$  

(In the case of the Ho-Lee model, we set $\hat{B}(t,T)=T-t$ in these equations.)  

Bond prices should therefore be calculated with equation (32.15), and not with equation (32.6).  

# Example 32.1  

Suppose zero rates are as in Table 32.2. The rates for maturities between those indicated are generated using linear interpolation.  

Consider a 3-year $(=3\times365$ days) European put option on a zero-coupon. bond that will pay 100 in 9 years $(=9\times365$ days). Interest rates are assumed to follow the Hull-White $(f(r)=r)$ model. The strike price is 63, $a=0.1$ , and $\sigma=0.01.\mathrm{A}\hat{:}$ -year tree is constructed and zero-coupon bond prices are calculated. analytically at the final nodes as just described. As shown in Table 32.3, the results from the tree are consistent with the analytic price of the option..  

Table 32.2 Zero curve with all rates continuously compounded, actual/365.   


<html><body><table><tr><td>Maturity</td><td>Days</td><td>Rate (%)</td></tr><tr><td>3 days</td><td>3</td><td>5.01772</td></tr><tr><td>1 month</td><td>31</td><td>4.98284</td></tr><tr><td>2 months</td><td>62</td><td>4.97234</td></tr><tr><td>3 months</td><td>94</td><td>4.96157</td></tr><tr><td>6 months</td><td>185</td><td>4.99058</td></tr><tr><td>1 year</td><td>367</td><td>5.09389</td></tr><tr><td>2 years</td><td>731</td><td>5.79733</td></tr><tr><td>3 years</td><td>1,096</td><td>6.30595</td></tr><tr><td>4 years</td><td>1,461</td><td>6.73464</td></tr><tr><td>5 years</td><td>1,826</td><td>6.94816</td></tr><tr><td>6 years</td><td>2,194</td><td>7.08807</td></tr><tr><td>7 years</td><td>2,558</td><td>7.27527</td></tr><tr><td>8 years</td><td>2,922</td><td>7.30852</td></tr><tr><td>9 years</td><td>3,287</td><td></td></tr><tr><td>10 years</td><td>3,653</td><td>7.39790 7.49015</td></tr></table></body></html>  

Table 32.3 Value of a 3-year put option on a 9-year zero-coupon bond with a strike price of 63: $a=0.1$ and $\sigma=0.01$ ; zero curve as in Table 32.2..   


<html><body><table><tr><td>Steps</td><td>Tree</td><td>Analytic</td></tr><tr><td>10</td><td>1.8468</td><td>1.8093</td></tr><tr><td>30</td><td>1.8172</td><td>1.8093</td></tr><tr><td>50</td><td>1.8057</td><td>1.8093</td></tr><tr><td>100</td><td>1.8128</td><td>1.8093</td></tr><tr><td>200</td><td>1.8090</td><td>1.8093</td></tr><tr><td>500</td><td>1.8091</td><td>1.8093</td></tr></table></body></html>  

This example provides a good test of the implementation of the model because. the gradient of the zero curve changes sharply immediately after the expiration of the option. Small errors in the construction and use of the tree are liable to have a big effect on the option values obtained. (See also Sample Application G of the. DerivaGem Applications software.)  

# Tree for American Bond Options  

The DerivaGem software accompanying this book implements the normal and. the lognormal model for valuing European and American bond options, caps/floors, and European swap options. Figure 32.9 shows the tree produced by the software when it is used to value a 1.5-year American call option on a 10-year bond using four time steps and the lognormal (Black-Karasinski) model. The parameters used in the lognormal model are $a=5\%$ and $\sigma=20\%$ . The underlying bond lasts 10 years, has. a principal of 100, and pays a coupon of $5\%$ per annum semiannually. The yield curve is flat at $5\%$ per annum. The strike price is 105. As explained in Section 29.1 the strike. price can be a cash strike price or a quoted strike price. In this case it is a quoted strike price. The bond price shown on the tree is the cash bond price. The accrued interest at each node is shown below the tree. The cash strike price is calculated as the quoted strike price plus accrued interest. The quoted bond price is the cash bond price minus accrued interest. The payoff from the option is the cash bond price minus the cash strike price. Equivalently it is the quoted bond price minus the quoted strike price..  

The tree gives the price of the option as 0.672.A much larger tree with 100 time steps gives the price of the option as 0.703. Note that the price of the 10-year bond cannot be computed analytically when the lognormal model is assumed. It is computed numerically by rolling back through a much larger tree than that shown.  
