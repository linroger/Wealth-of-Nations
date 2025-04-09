# 16.4 DIRAC DELTA FUNCTIONS  

Consider the integral of the Gaussian density with mean $K$ given below  

$$
\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi\beta^{2}}}e^{-(1/2)\left(x-K\right)^{2}/\beta^{2}}\mathrm{d}x=1
$$  

where $\beta^{2}$ is the "variance" parameter. Let $f(x)$ denote the density:  

$$
f(x)=\frac{1}{\sqrt{2\pi\beta^{2}}}e^{-(1/2)(x-K)^{2}/\beta^{2}}
$$  

We will use $f(x)$ as a mathematical tool instead of representing a probability density associated with a financial variable. To see how this is done, suppose we consider the values of $\beta$ that sequentially go from 1 toward 0. The densities will be as shown in Figure 16.3. Clearly, if $\beta$ is very small, the "density"' will essentially be a spike at $K.$ but still will have an area under it that adds up to 1.  

Now consider the "expectations" calculated with such an $f(x)$ . Let $C(x_{t})$ be a random value that depends on the random variable $x_{t}$ indexed by the time $t.$ Then we can write  

$$
E[C(x_{t})]=\intop_{-\infty}^{\infty}C(x_{t})f(x_{t})\mathrm{d}x_{t}
$$  

![](images/b18d7e4ec23a581d1da4c2ea6f62047e3d4e8f14dcd5ba05486604b42b623326.jpg)  

# FIGURE 16.3  

Density as $\beta$ goes to zero.  

Now we push. $\beta$ toward zero. The density $f(x_{t})$ will become a spike at $K.$ This means that all. values of. $C(x_{t})$ will be multiplied by a probability of almost zero, except the ones around $x_{t}=K$ After all, at the limit $f(.)$ is nonzero only around $x_{t}=K$ . Thus at the limit we obtain  

$$
\operatorname*{lim}_{\beta\to0}\int C(x_{t})f(x_{t})\mathrm{d}x_{t}=C(K)
$$  

The integral of the product of a function $C(x_{t})$ and of $f(x_{t})$ as $\beta$ goes to zero picks up the value of the function at $x_{t}=K$  

Hence we define the Dirac delta function as  

$$
\delta_{K}(x)=\operatorname*{lim}_{\beta\to0}f(x,K,\beta)
$$  

Remember that $\beta$ determines how close $f(x)$ is to a spike at. $K$ The integral can then be rewritten as  

$$
\int_{-\infty}^{\infty}C(K)\delta_{K}(x)\mathrm{d}x_{t}=C(K)
$$  

This integral shows the most useful property of dirac delta function for our purposes. Essentially, the dirac delta picks up the value of $C(x_{t})$ at the point $x_{t}=K$ We now apply this property to option payoffs at expiration.  
