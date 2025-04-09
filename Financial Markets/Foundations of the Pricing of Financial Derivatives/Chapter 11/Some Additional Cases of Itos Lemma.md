# 11.5 SOME ADDITIONAL CASES OF ITO'S LEMMA

Let us look at two more cases of Ito's lemma. First, we look at the case where our random process is a function of not one but two random processes, $x$ and $y.$ An example of this situation might be a currency option, whereby the performance is determined by the exchange rate and an interest rate. Alternatively, there are options that pay off based on the greater or poorer performing of two assets that are stochastic.

So let $x$ and $y$ follow stochastic differential equations driven by Ito processes. For now, we do not have to specify those processes precisely. Consider a function $F$ determined by $x,y,$ and $t.$ Applying Ito's lemma to F, we obtain.

$$
d F={\frac{\partial F}{\partial x}}d x+{\frac{\partial F}{\partial y}}d y+{\frac{\partial F}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x^{2}}}d x^{2}+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial y^{2}}}d y^{2}+{\frac{\partial^{2}F}{\partial x\partial y}}d x d y.
$$

Depending on the specifications of. $d x$ and $d y$ , we may be able to simplify this expression. further. Note that there is no interaction term with $d x$ and $d t$ or with $d y$ and $d t$ as these will go to zero by the product of $d x$ and $d\mathbb{W}$ and the product of $d y$ and $d\mathbb{W}.$ To take this equation further, we have to specify the processes describing $x$ and $y$

So now consider two processes, $d x$ and $d y$ , both with different but constant parameters and the same Brownian motion,

$$
\begin{array}{r}{d x=\mu_{x}d t+\sigma_{x}d W_{t}}\ {d y=\mu_{y}d t+\sigma_{y}d W_{t}.}\end{array}
$$

Now consider another process, $z$ , defined as the product of $x$ and $y$ . Products can occur in finance where the price of an asset is multiplied by an exchange rate or the quantity is multiplied by price:

$$
z=x y.
$$

We need to identify the stochastic process for $d z$ Applying Ito's lemma we obtain:6

$$
d z={\frac{\partial z}{\partial x}}d x+{\frac{\partial z}{\partial y}}d y+{\frac{1}{2}}{\frac{\partial^{2}z}{\partial x^{2}}}d x^{2}+{\frac{1}{2}}{\frac{\partial^{2}z}{\partial y^{2}}}d y^{2}+{\frac{\partial^{2}z}{\partial x\partial y}}d x d y.
$$

Because $z$ is a very simple function of. $x$ and $y$ , the partial derivatives in the above expression are easily obtained from Equation (11.24),

$$
\begin{array}{l}{{\displaystyle\frac{\partial{z}}{\partial x}=y,\quad\frac{\partial{z}}{\partial y}=x,\quad\frac{\partial^{2}{z}}{\partial x^{2}}=0,}}\ {{\displaystyle\frac{\partial^{2}{z}}{\partial y^{2}}=0,\quad\frac{\partial^{2}{z}}{\partial x\partial y}=\frac{\partial}{\partial x}\left(\frac{\partial{z}}{\partial y}\right)=\frac{\partial}{\partial y}\left(\frac{\partial{z}}{\partial x}\right)=1.}}\end{array}
$$

Thus, simplifying equation (11.25) to

$$
d z=y d x+x d y+d x d y.
$$

Now let us examine dxdy. First, we show that the variance of $d x d y=0$ . Using the fact that $d t^{k}\to0$ for $k>1$ , we have that

$$
\begin{array}{r l}&{\mathrm{var}(d x d y)=\mathrm{var}\left[\left(\mu_{x}d t+\sigma_{x}d W_{t}\right)\left(\mu_{y}d t+\sigma_{y}d W_{t}\right)\right]}\ &{\mathrm{~}=\mathrm{var}\left(\mu_{x}d t\mu_{y}d t+\mu_{x}d t\sigma_{y}d W_{t}+\mu_{y}d t\sigma_{x}d W_{t}+\sigma_{x}d W_{t}\sigma_{y}d W_{t}\right)}\ &{\mathrm{~}=0.}\end{array}
$$

Working term by term, the first term has $d t^{2}\to0$ The next two terms involving dtc. ${\mathit{d W}}_{t}\to0$ because $d\mathbb{W}_{t}$ has the square root of. $d t$ in it and that means that. $d t$ is raised to the power 3/2. Finally, recall that earlier we had var $\left(d W_{t}^{2}\right)=\operatorname{var}\left(\varepsilon_{t}^{2}d t\right)=d t^{2}\operatorname{var}\left(\varepsilon_{t}^{2}\right)=0$ Now, if $\mathrm{var}(d x d y)=0$ , then $d x d y=E(d x d y)$ , which means that. $d x d y$ is almost surely constant.. Using the facts that. $d\mathbf{W}_{t}^{2}=\varepsilon_{t}^{2}d t$ $d t^{k}\to0$ for $k>1$ , and $E\big(\varepsilon_{t}^{2}\big)=1$ , we show that. $d x d y=$ $\sigma_{x}\sigma_{y}d t$ as follows:

$$
\begin{array}{r l}&{E(d x d y)=E\big[\big(\mu_{x}d t+\sigma_{x}d W_{t}\big)\big(\mu_{y}d t+\sigma_{y}d W_{t}\big)\big]}\ &{\qquad=E\big(\mu_{x}d t\mu_{y}d t+\mu_{x}d t\sigma_{y}d W_{t}+\mu_{y}d t\sigma_{x}d W_{t}+\sigma_{x}d W_{t}\sigma_{y}d W_{t}\big)}\ &{\qquad=E\big(\sigma_{x}d W_{t}\sigma_{y}d W_{t}\big)=\sigma_{x}\sigma_{y}E\Big(d W_{t}^{2}\Big)=\sigma_{x}\sigma_{y}d t=d x d y.}\end{array}
$$

Substituting this result into Equation (11.25), we obtain

$$
d z=y d x+x d y+\sigma_{x}\sigma_{y}d t.
$$

Now let us assume the two processes, $d x$ and $d y$ , are driven by different Wiener processes, $d\mathbb{W}_{t}$ and $d\boldsymbol{\mathcal{Q}}_{t}$

$$
\begin{array}{r}{d\mathrm{W}_{t}=\varepsilon_{\mathrm{W},t}\sqrt{d t}}\ {d Q_{t}=\varepsilon_{Q,t}\sqrt{d t}.}\end{array}
$$

Note the additional subscript for clarity. These processes could be independent, or they could be correlated. Let us start with the general case of a nonzero correlation, so letd $\rho_{\mathbb{W},\mathbb{Q}}$ be the correlation between the $d\mathbb{W}_{t}$ and $d\boldsymbol{\mathcal{Q}}_{t}$

Now let us specify the processes for $x$ and $y$ , as driven by $d\mathbb{W}_{t}$ and $d\underline{{Q}}_{t}$

$$
\begin{array}{r}{d x=\mu_{x}d t+\sigma_{x}d W_{t}}\ {d y=\mu_{y}d t+\sigma_{y}d Q_{t}.}\end{array}
$$

Recall that we are interested in $z$ , the product of $x$ and $y$ . We found the total differential of $z$ as Equation (11.25) and we obtained the partial derivatives in Equation (11.26). Therefore, $d z$ is given as

$$
\begin{array}{r l}&{d z=x d y+y d z+d x d y=x d y+y d x+\left(\mu_{x}d t+\sigma_{x}d W_{t}\right)\left(\mu_{y}d t+\sigma_{y}d Q_{t}\right)}\ &{\quad=x d y+y d x+\mu_{x}\mu_{y}d t^{2}+\mu_{y}\sigma_{x}d W_{t}d t+\mu_{x}\sigma_{y}d t d Q+\sigma_{x}\sigma_{y}d W_{t}d Q_{t}}\ &{\quad=x d y+y d x+\sigma_{x}\sigma_{y}d W_{t}d Q_{t}.}\end{array}
$$

Notice in deriving this equation that the terms $d t^{2},d\mathrm{W}_{t}d t.$ and $d\boldsymbol{\mathcal{Q}}_{t}d t$ go to zero because they all involve powers of $d t$ greater than 1. Now let us examine the $d\mathbb{W}_{t}d\mathcal{Q}_{t}$ term. We start by taking the variance of $d\mathbb{W}_{t}d\mathcal{Q}_{t}$ . We have

$$
\begin{array}{r}{\mathrm{var}\big(d\mathrm{W}_{t}d\mathcal{Q}_{t}\big)=\varepsilon_{\mathrm{W},t}\sqrt{d t}\varepsilon_{\mathcal{Q},t}\sqrt{d t}=\mathrm{var}\big(d t\varepsilon_{\mathrm{W},t}\varepsilon_{\mathcal{Q},t}\big)=d t^{2}\mathrm{var}\big(\varepsilon_{\mathrm{W},t}\varepsilon_{\mathcal{Q},t}\big)=0.}\end{array}
$$

The zero variance means that $d\mathrm{W}_{t}d\mathcal{Q}_{t}=E\big(d\mathrm{W}_{t}d\mathcal{Q}_{t}\big)$ , and so we evaluate $E\big(d W_{t}d Q_{t}\big)$ . We can obtain this result by making use of the definition of covariance and correlation. Note the first line here is the correlation times the product of the standard deviations of the two processes $(d t)$ and the second line is the definition of correlation. Thus,.

$$
\begin{array}{r l}&{\mathrm{cov}(d\mathbb{W},d\mathcal{Q})=d t\rho(d\mathbb{W},d\mathcal{Q})}\ &{\quad\quad=E\big(d\mathbb{W}_{t}d\mathcal{Q}_{t}\big)-E\big(d\mathbb{W}_{t}\big)E\big(d\mathcal{Q}_{t}\big)}\ &{\quad\quad=E\big(d\mathbb{W}_{t}d\mathcal{Q}_{t}\big).}\end{array}
$$

Hence,

$$
E\big(d W_{t}d Q_{t}\big)=d W_{t}d Q_{t}=\rho(d W,d Q)d t.
$$

Thus,

$$
d z=y d x+x d y+\sigma_{x}\sigma_{y}\rho(d W,d Q)d t.
$$

We can do one more thing to make this result a bit cleaner. Note that the correlation is expressed in terms of $d\mathbb{W}$ and $d\mathcal{Q}$ but the other terms are expressed in terms of $x$ and $y$ We know that $\rho_{d W d Q}=\mathrm{cov}(d W,d Q)/\sigma_{d W}\sigma_{d Q}$ . We also know from Equation (11.30) that the standard deviations of $d\mathbb{W}_{t}$ and $d\boldsymbol{\mathcal{Q}}_{t}$ are each the square root of $d t.$ Thus, $\sigma_{d\mathrm{W}}\sigma_{d\mathrm{Q}}=$ $d t$ and, $\rho(d\boldsymbol{W},d\boldsymbol{Q})d t=\mathrm{cov}(d\boldsymbol{W},d\boldsymbol{Q})$ . We also know that $\rho(d x,d y)=\mathrm{cov}(d x,d y)/\sigma_{d x}\overset{\sim}\sigma_{d y}.$ Using Equation (11.31), $\operatorname{cov}(d x,d y)=\sigma_{d x}\sigma_{d y}\operatorname{cov}(d\mathbb{W},d\boldsymbol{Q})=\rho(d\mathbb{W},d\boldsymbol{Q})d t$ Then cov $(d W,d Q)=\rho(d W,d Q)d t/\sigma_{d W}\sigma_{d Q}$ . Substituting into Equation (11.36),

$$
\begin{array}{r}{d z=y d x+x d y+\rho(x,y)d t.}\end{array}
$$

Of course, if these are independent Brownian motions, the correlation term disappears.
