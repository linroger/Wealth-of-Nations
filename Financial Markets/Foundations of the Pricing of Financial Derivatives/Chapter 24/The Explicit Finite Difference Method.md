---
tags:
  - '#explicit_finite_difference_method'
  - '#finite_difference_grid'
  - '#log_transform'
  - '#option_pricing'
  - '#partial_derivatives'
  - '#risk_neutral_valuation'
  - '#trinomial_method'
  - '#weighted_average'
---
# 24.2 THE EXPLICIT FINITE DIFFERENCE METHOD

It may be useful to visualize the following small section from the grid illustrated in Figure 24.3. Define any arbitrary point, $t_{:}$ across the columns representing time. Each column is related to the column next to it by one increment or decrement of time, $\Delta t$ Each row is the natural log of the asset price. Each row above or below it increments the log of the asset price by $\Delta y$ . From the point corresponding to the log of asset price, $y,$ and time, $t_{:}$ look to the right one column at the option prices one asset price up, the current asset price, and one asset price down.

IABLE 24.3 A Portion of the Explicit Finite Difference Grid


<html><body><table><tr><td></td><td colspan="2">Time</td></tr><tr><td>In S</td><td>t</td><td>t+△t</td></tr><tr><td>y+△y</td><td rowspan="4">Wy,t</td><td>Wy+△y,t+△t</td></tr><tr><td>y</td><td>y,t+△t</td></tr><tr><td>y-△y</td><td></td></tr><tr><td></td><td>Wy-△y,t+△t</td></tr></table></body></html>

What we are going to do is to express the option price. $w_{y,t}$ as a weighted average of these three option prices to the right, discounted one period at the risk-free rate, that is, in this general form:

$$
w_{y,t}=\frac{\omega_{1}w_{y+\Delta y,t+\Delta t}+\omega_{2}w_{y,t+\Delta t}+\omega_{3}w_{y-\Delta y,t+\Delta t}}{e^{r_{c}\Delta t}}.
$$

The explicit finite difference method solves for. $w_{y,t}$ in terms of the known values of. Wy+Ay,t+At, Wy,t+st, and wy-y,t+At. The three prices one time step ahead are assumed to be. already known. Of course, we shall need to know the three prices to the right, but we will obviously know these prices. Recall from Table 24.2 that we know all the prices in the rightmost column. That means we can fill in the prices one column to the left. What we do not know, however, is the weights in Equation (24.13), and that is what the explicit finite difference method will provide. We shall approach this problem by examining the differentials, which represent the derivatives, which represent the differences in prices. along the grid.

We can obtain finite difference estimates of the partial derivatives as follows. First, $\Delta w_{y,t}/\Delta t$ is approximately

$$
\frac{\Delta w_{y,t}}{\Delta t}=\frac{w_{y,t+\Delta t}-w_{y,t}}{\Delta t}.
$$

Note that we are holding the asset price constant and moving along the grid by a time step. We shall also, however, need a way to relate the price corresponding to. $y$ and $t$ to the price one step later corresponding to $y+\Delta y$ and $y-\Delta y$ . One way is called the forward difference,

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y+\Delta y,t+\Delta t}-w_{y,t+\Delta t}}{\Delta y},
$$

and another is called the backward difference,

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y,t+\Delta t}-w_{y-\Delta y,t+\Delta t}}{\Delta y}.
$$

We typically average these two estimates to obtain

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y+\Delta y,t+\Delta t}-w_{y-\Delta y,t+\Delta t}}{2\Delta y}.
$$

The second partial differential can be estimated as

$$
\begin{array}{r}{\frac{\Delta^{2}w_{y,t}}{\Delta y^{2}}=\frac{\frac{w_{y+\Delta y,t+\Delta t}-w_{y,t+\Delta t}}{\Delta y}-\frac{w_{y,t+\Delta t}-w_{y-\Delta y,t+\Delta t}}{\Delta y}}{\Delta y}.}\ {=\frac{w_{y+\Delta y,t+\Delta t}-2w_{y,t+\Delta t}+w_{y-\Delta y,t+\Delta t}}{\Delta y^{2}}}\end{array}
$$

Substituting these estimates of the partial differentials into the difference Equation (24.6) and rearranging gives us

$$
w_{y,t}=\frac{\omega_{1}w_{y-\Delta y,t+\Delta t}+\omega_{2}w_{y,t+\Delta t}+\omega_{3}w_{y+\Delta t,t+\Delta t}}{1+r_{c}\Delta t},
$$

where

$$
\begin{array}{l}{\displaystyle{\omega_{1}=\left[\frac{1}{2}\left(\frac{\sigma}{\Delta y}\right)^{2}-\frac{1}{2}\left(\frac{r_{c}-\frac{\sigma^{2}}{2}}{\Delta y}\right)\right]\Delta t}}\ {\displaystyle{\omega_{2}=1-\left(\frac{\sigma}{\Delta y}\right)^{2}\Delta t}}\ {\displaystyle{\omega_{3}=\left[\frac{1}{2}\left(\frac{\sigma}{\Delta y}\right)^{2}+\frac{1}{2}\left(\frac{r_{c}-\frac{\sigma^{2}}{2}}{\Delta y}\right)\right]\Delta t}.}\end{array}
$$

In other words, the option price at $t$ is a discounted weighted average of the next three possible option prices at $t+\Delta t$ where the weights are given in Equation (24.20). These weights sum to unity and are the risk neutral/equivalent martingale probabilities of the three log asset prices $y+\Delta y,y$ and $y-\Delta y$ at $t+\Delta t$ This technique is, therefore, essentially a risk-neutral trinomial method.

Filling in the full grid with the option prices is now simple. As noted previously, the. rightmost column is the set of option prices at expiration and is already known. Using. the rightmost column to provide the three known option prices, we can then solve for the. second-to-rightmost column of option prices. Other missing prices in the topmost row can be filled in by knowing the second-to-topmost row, as noted previously. The prices in the bottommost row are, as noted previously, zero. The process then continues leftward until. the leftmost column is filled in. When the entire grid is filled in, the current option price can be read from the row corresponding to the log of the current asset price in the leftmost column.3

The log transform allows the weights to be independent of time. Thus, $\omega_{i},i=1,2,3$ need to be obtained only once.4 The weights should be constrained to be nonnegative, which is important, by choosing $\Delta t\leq\Delta y^{2}\big/\sigma^{2}$ and $\Delta y\leq\sigma^{2}|r_{c}-\sigma^{2}/2|$
