---
tags:
  - '#crank_nicholson_method'
  - '#explicit_finite_difference_method'
  - '#finite_difference_grid'
  - '#implicit_finite_difference_method'
  - '#numerical_methods'
  - '#option_pricing'
  - '#partial_differential_equation'
---
# 24.3 THE IMPLICIT FINITE DIFFERENCE METHOD

The implicit finite difference method uses a somewhat different approach. Consider the section of the grid shown in Table 24.4.

Notice the difference with the explicit finite difference method. Here we have one price at. $t+\Delta t$ and three at time $t.$ Here we shall solve for three contemporaneous option prices. by using information about the next asset price. The first-order differential with respect to the asset price is estimated as

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y+\Delta y,t}-w_{y,t}}{\Delta y},
$$

or as

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y,t}-w_{y-\Delta y,t}}{\Delta y}.
$$

Averaging these two estimates we obtain

$$
\frac{\Delta w_{y,t}}{\Delta y}=\frac{w_{y+\Delta y,t}-w_{y-\Delta y,t}}{2\Delta y}.
$$

Note how each of these prices is at the same point in time, $t.$ The second order differential. is estimated as

$$
\begin{array}{r}{\frac{\Delta^{2}w_{y,t}}{\Delta y^{2}}=\frac{\frac{w_{y+\Delta y,t}-w_{y,t}}{\Delta y}-\frac{w_{y,t}-w_{y-\Delta y,t}}{\Delta y}}{\Delta y}.}\ {=\frac{w_{y+\Delta y,t}-2w_{y,t}+w_{y-\Delta y,t}}{\Delta y^{2}}}\end{array}
$$

The time differential is estimated the same way as in the explicit finite difference method, Equation (24.14). Now we substitute these values into the difference Equation, (24.6), to obtain

$$
\begin{array}{r l}&{\frac{1}{2}\sigma\bigg(\frac{w_{y+\Delta y,t}-2w_{y,t}+w_{y-\Delta y,t}}{\Delta y^{2}}\bigg)+\bigg(r_{c}-\frac{\sigma^{2}}{2}\bigg)\bigg(\frac{w_{y+\Delta y,t}-w_{y-\Delta y,t}}{2\Delta y}\bigg)}\ &{\qquad+\frac{w_{y,t+\Delta t}-w_{y,t}}{\Delta t}-r_{c}w_{y,t}=0.}\end{array}
$$

TABLE 24.4 A Portion of the Finite Difference Grid


<html><body><table><tr><td></td><td colspan="2">Time</td></tr><tr><td>In S</td><td>t</td><td>t+△t</td></tr><tr><td>y+△y</td><td>Wy+△y,t</td><td></td></tr><tr><td>y</td><td>Wy,t</td><td>m y,t+△t</td></tr><tr><td>y-△y</td><td>Wy-△y,t</td><td></td></tr></table></body></html>

Solving for $w_{y,t+\Delta t}$ gives

$$
\begin{array}{r}{w_{y,t+\Delta t}=\omega_{1}w_{y-\Delta y,t}+\omega_{2}w_{y,t}+\omega_{3}w_{y+\Delta y,t},}\end{array}
$$

where

$$
\begin{array}{l}{\displaystyle\omega_{1}=\frac{1}{2}\left(\frac{r_{c}-\frac{\sigma^{2}}{2}}{\Delta y}\right)\Delta t-\frac{1}{2}\frac{\sigma^{2}\Delta t}{\Delta y}}\ {\displaystyle\omega_{2}=1+\frac{\sigma^{2}\Delta t}{\Delta y^{2}}+r_{c}\Delta t}\ {\displaystyle\omega_{3}=-\frac{1}{2}\left(\frac{r_{c}-\frac{\sigma^{2}}{2}}{\Delta y}\right)\Delta t-\frac{1}{2}\frac{\sigma^{2}\Delta t}{\Delta y}.}\end{array}
$$

Note how the equation above solves for the prices $w_{y+\Delta y,t}$ $w_{y,t}$ and $w_{y-\Delta y,t}$ in terms of the known value $w_{y,t+\Delta t}$ .With three unknowns there must be three equations. Thus, the solution is obtained by solving simultaneously an entire column of option prices. The process starts at the next-to-rightmost column and works leftward..

The implicit finite difference method is generally considered the better approach,. because it will often work when the explicit method does not. But it is slightly more difficult to implement, requiring solving simultaneous equations. The Crank-Nicholson. method is also widely used. It essentially averages the explicit and implicit methods..
