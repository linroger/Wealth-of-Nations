---
tags:
  - feynman_kac
  - money_illusion
  - nominal_bonds
  - ode_solutions
  - real_bonds
aliases:
  - Short Rate Model
  - Vasicek Model
key_concepts:
  - Feynman-Kac Formula
  - First Derivatives
  - Nominal vs Real Bonds
  - ODE Solutions
  - System of Equations
---

$\textbf{Define}$
$$
Q = \log (\text{CPI}), \quad y = \log (Y)
$$
$\textbf{so that}$
$$
Dq = \bar{\pi} dt + \sigma_\pi dW_\pi, \quad dy = \bar{g} dt + \sigma_g dW_g
$$
$\textbf{and recall}$
$$
D\bar{\pi} = (\alpha_\pi - \beta_\pi \bar{\pi}) dt + \sigma_\pi dW_\pi, \quad
D\bar{g} = (\alpha_g - \beta_g \bar{g}) dt + \sigma_g dW_g
$$
$\textbf{From the pricing equation we have}$
$$
Z (t, T) = E \left[ e^{-\rho (T-t)-(q (T)-q (t))-\gamma (y (T)-y (t))} \right]
$$
$\textbf{To be slightly more general, consider the following case}$
$$
Z (t, T) = E \left[ e^{-\rho (T-t)-\eta (q (T)-q (t))-\gamma (y (T)-y (t))} \right]
= e^{\eta q (t)+\gamma y (t)} E \left[ e^{-\rho (T-t)} G (q (T), y (T)) \right]
= e^{\eta q (t)+\gamma y (t)} V (q, y, \bar{\pi}, \bar{g}, t)
$$
When $\eta = 1$, we have the case for nominal bonds. When $\eta = 0$, we have the case of real bonds. When $\eta$ is intermediate, this can be considered a case in which inflation affects the utility function of agents directly. A case in the literature is the one of money illusion.
\textbf{From the Feynman-Kac formula, we have that $V$ satisfies}
$$
\rho V = V_t + V_q E[dq] + V_y E[dy] + V_\pi E[d\pi] + V_g E[dg] 
+ \frac{1}{2} V_{qq} E[dq^2] + \frac{1}{2} V_{yy} E[dy^2] 
+ \frac{1}{2} V_{\pi\pi} E[d\pi^2] + \frac{1}{2} V_{gg} E[dg^2] 
+ V_{qy} E[dqdy] + V_{q\pi} E[dqd\pi] + V_{qg} E[dqdg] 
+ V_{y\pi} E[dyd\pi] + V_{yg} E[dydg] + V_{\pi g} E[d\pi dg].
$$
$\textbf{with final condition}$
$$
V (q, y, \bar{\pi}, \bar{g}, T) = e^{-\eta q (T)-\gamma y (T)}.
$$
$\textbf{We can conjecture the following}$
$$
V (q, y, \bar{\pi}, \bar{g}, t) = e^{-\eta q (t)-\gamma y (t) + A (t; T) - \eta B (t; T) \bar{\pi} - \gamma C (t; T) \bar{g}}
$$
Taking the first derivatives:
$$
V_t = A' (t; T) V, \quad V_q = -\eta V, \quad V_qq = \eta^2 V, \quad V_y = -\gamma V, 
\quad V_{yy} = \gamma^2 V
$$
$$
V_\pi = -\eta B (t; T) V, \quad V_{\pi\pi} = \eta^2 B (t; T)^2 V, \quad 
V_g = -\gamma C (t; T) V, \quad V_{gg} = \gamma^2 C (t; T)^2 V.
$$
$\textbf{Substituting and deleting the common V}$
$$
\rho = \big[ A' (t; T) - \eta B' (t; T) \bar{\pi} - \gamma C' (t; T) \bar{g} \big]
+ \frac{1}{2} \eta^2 \sigma_\pi^2 + \frac{1}{2} \gamma^2 \sigma_g^2 
+ \eta \gamma \sigma_\pi \sigma_g \rho_{\pi g}.
$$
Factoring out variables $\bar{\pi}$ and $\bar{g}$:
$$
\rho = -\eta \big[ B' (t; T) + 1 - \beta_\pi \big] \bar{\pi} 
- \gamma \big[ C' (t; T) + 1 - \beta_g \big] \bar{g}
+ A' (t; T) - \eta B (t; T) \alpha_\pi - \gamma C (t; T) \alpha_g.
$$
This is satisfied for all values of $\bar{\pi}$ and $\bar{g}$ if and only if the following system is satisfied:
$$
0 = B' (t; T) + 1 - \beta_\pi, \quad 0 = C' (t; T) + 1 - \beta_g,
$$
$$
\rho = A' (t; T) - \eta B (t; T) \alpha_\pi - \gamma C (t; T) \alpha_g.
$$
$\textbf{with final conditions}$
$$
B (T, T) = 0, \quad C (T, T) = 0, \quad A (T, T) = 0.
$$
The first two ODEs have solutions:
$$
B (t, T) = \frac{1 - e^{-\beta_\pi (T-t)}}{\beta_\pi}, \quad
C (t, T) = \frac{1 - e^{-\beta_g (T-t)}}{\beta_g}.
$$
The last ODE has solution:
$$
 \begin{aligned}
A\left (t, T\right)& \left (-\rho+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}\right)(T-t)  \\
&+\left[\eta^{2}\sigma_{\pi}\sigma_{\overline{\pi}}\rho_{\pi\overline{\pi}}+\gamma\eta\sigma_{g}\sigma_{\overline{\pi}}\rho_{g\overline{\pi}}-\eta\alpha_{\pi}+\frac{1}{2}\frac{\eta^{2}\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}+\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{\pi}}\left (\left (T-t\right)\right) \\
&+\left[\eta\gamma\sigma_{\pi}\sigma_{\overline{g}}\rho_{\pi\overline{g}}+\gamma^{2}\sigma_{g}\sigma_{\overline{g}}\rho_{g\overline{g}}-\gamma\alpha_{g}+\frac{1}{2}\frac{\gamma^{2}\sigma_{\overline{g}}^{2}}{\beta_{g}}+\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{g}}\left ((T-t)\right) \\
&-\frac{1}{4}\frac{\eta^{2}\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}B\left (t, T\right)^{2}-\frac{1}{4}\frac{\gamma^{2}\sigma_{\overline{g}}^{2}}{\beta_{g}}C\left (t, T\right)^{2}-\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi g}}}{\left (\beta_{\pi}+\beta_{g}\right)}B\left (t, T\right) C\left (t, T\right)
\end{aligned}$$

Setting $\eta = 1$ provides the formula for $A(t, T)$ in the text. Moreover, the case $\eta = 0$ corresponds to the real bond, obtaining:
$$
A_{\text{real}}(t, T) = \left ( -\rho + \frac{1}{2} \gamma^2 \sigma_g^2 \right) (T-t)
+ \frac{\gamma^2 \sigma_g^2}{\beta_g} \big[ (T-t) - C (t, T) \big]
- \frac{1}{4} \frac{\gamma^2 \sigma_g^2}{\beta_g^2} C (t, T)^2.
$$