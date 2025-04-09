# 20.1 THE NATURE OF THE PROBLEM OF PRICING AN AMERICAN PUT

Based on geometric Brownian motion, the price of an American put follows the partial differential equation,

$$
\frac{\partial P_{t}}{\partial t}=r_{c}P_{t}-r_{c}S_{t}\frac{\partial P_{t}}{\partial S_{t}}-\frac{1}{2}\frac{\partial^{2}P_{t}}{\partial{S_{t}}^{2}}\sigma^{2}S_{t}^{2}.
$$

For a European put, in which we would use a lowercase $p$ , the PDE would still apply with.
the following boundary condition:.

$$
\begin{array}{r}{p_{T}=\operatorname*{max}\bigl(0,X-S_{T}\bigr),}\end{array}
$$

where $S_{T}$ is the asset price at expiration. For an American put we require the additional condition,

$$
P_{t}\ge\operatorname*{max}\bigl(0,X-S_{t}\bigr).
$$

This condition simply means that at any time. $t$ prior to expiration, the American put value must be worth at least its exercise value because it can be exercised immediately.. Because $t$ and $S_{t}$ change, this is a free boundary problem and had for many years been thought to be unsolvable. Geske and Johnson (1984), however, obtained a solution as. an $_n$ -fold compound option, using Geske's (1979b) compound option formula and the. equivalent martingale/risk neutrality assumption. We shall demonstrate this result here.

Consider the layout in continuous time: From $t$ to $t+d t$ is time unit dt. From. $t$ to time $t+2d t$ is time unit $2d t$ , and so on. At any instant the put can be exercised. If it is not exercised at that instant, we move forward and consider whether it is optimal to exercise the put at the next instant. The exercise decision will be determined by many factors and will take into account that optimality may come from waiting until later to exercise it.
