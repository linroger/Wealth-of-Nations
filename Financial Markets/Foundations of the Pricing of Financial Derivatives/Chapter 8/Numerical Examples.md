# 8.3 NUMERICAL EXAMPLES

Now let us take a look at some numerical examples. Let us first look at a simple problem with two binomial time steps. Later we extend the problem to more time steps. We use the following inputs: $S=100$ $X=100$ $\tau=2$ (time to expiration), $\sigma=0.4$ $r=0.07$ (discrete), and $n=2$ . With the inputs expressed in these terms, we have to convert them to their binomial analogs. Thus, we now introduce a reasonable and widely used formula to convert the volatility and risk-free rate of the asset return to the binomial parameters,

$$
\begin{array}{c}{u=e^{\sigma\sqrt{\tau/n}}}\ {d=1/u}\ {r(p e r p e r i o d)=(1+r)^{\tau/n}-1.}\end{array}
$$

Note here that $d$ is the reciprocal of $\boldsymbol{\mathscr{u}}$ , but that does not have to be the case. Research on the binomial model has produced many formulas for converting volatility of the underlying to the $\boldsymbol{\mathscr{u}}$ and $d$ factors. In the limit, all of them produce the desired result. This is just one of the more widely used formulas. The calculations are

$$
{\begin{array}{c}{u=e^{0.4{\sqrt{2/2}}}=1.4918}\ {d=1/1.4918=0.6703}\ {r(p e r p e r i o d)=(1+r)^{T/n}=(1.07)^{2/2}-1=0.07.}\end{array}}
$$

We obtain $u=1.4918$ $d=0.6703$ , and the per-period risk-free rate is 0.07. The length of a time step is $2({\mathrm{years}})/2=1.$ That is, each time step is one year. The standard binomial tree is as shown in Figure 8.3.9

The standard Greeks are computed as follows:

$$
\begin{array}{l}{\displaystyle\Delta_{c}=\frac{c_{u}-c_{d}}{S u-S d}=\frac{55.72-0}{149.18-67.03}=0.6783\mathrm{and}\Delta_{p}}\ {\displaystyle=\frac{p_{d}-p_{u}}{S u-S d}=\frac{26.43-0}{149.18-67.03}=0.3217,}\end{array}
$$

$$
\Gamma_{c}=\frac{\left(\frac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}\right)-\left(\frac{c_{u d}-c_{d^{2}}}{S u d-S d^{2}}\right)}{(1/2)(S u^{2}-S d^{2})}=\frac{\left(\frac{122.5S-0}{222.5S-100}\right)-\left(\frac{0-0}{100-44.93}\right)}{(1/2)(222.5S-44.93)}=0.0113\:a
$$

$$
\Gamma_{p}=\frac{\left(\frac{p_{d^{2}}-p_{u d}}{S u d-S d^{2}}\right)-\left(\frac{p_{u d}-p_{u^{2}}}{S u^{2}-S u d}\right)}{(1/2)(S u^{2}-S d^{2})}=\frac{\left(\frac{55.07-0}{100-44.93}\right)-\left(\frac{0-0}{22.55-100}\right)}{(1/2)(222.55-44.93)}=0.0113,
$$

$$
\Theta_{c}=\frac{c_{u d}-c}{2\Delta t}=\frac{0-25.34}{2(1)}=-12.67\mathrm{and}\Theta_{p}=\frac{\rho_{u d}-p}{2\Delta t}=\frac{0-12.68}{2(1)}=-6.34.
$$

Note that from Equations (8.3) and (8.7), the put-call parity relationship for delta and gamma hold. The tree for the more precise method is as shown in Figure 8.4: The positioning of this tree in the context of time merits an explanation. The current state is the middle position of time 2 where the asset is at 100 and the call is at 25.34.10 In general terms, the current state is where the asset price is $S_{u d}$ . To obtain the states above and below, where the asset price is $S_{u^{2}}$ and $S_{d^{2}}$ , we have to back up and generate states $S_{u}$ and $S_{d}$ and then back up to generate S. Once we have this information, we can generate the prices $S_{u^{2}}$ and $S_{d^{2}}$ . The option still expires in two years, and with two periods, each time step is one year. It is important to understand that the time steps before the current step, time 2, are artificial. They do not imply a past history. And in general, $S_{u d}$ does not have to equal

![](images/9af3da2495acc7a2c188491f6ae8e47d4d6b58987bb7bdfc315d2002d0b5b08b.jpg)
FIGURE 8.3 Standard Binomial Greeks Example

![](images/c3d91e8b12b4217aec65cca63bf788288f316c307ce6f70652a5531b1506bc5f.jpg)
FIGURE 8.4 Expanded Binomial Tree Example

TABLE 8.1 Prices, Deltas, Gammas, and Thetas from Standard Binomial (500 Time Steps), Expanded Binomial, and Black-Scholes-Merton Models.


<html><body><table><tr><td>Price/Greek</td><td>StandardBinomial</td><td>Expanded Binomial</td><td>Black-Scholes-Merton</td></tr><tr><td>C</td><td>27.7750</td><td>27.7750</td><td>27.7546</td></tr><tr><td>p</td><td>15.1189</td><td>15.1189</td><td>15.1102</td></tr><tr><td>c</td><td>0.6989</td><td>0.6995</td><td>0.6992</td></tr><tr><td></td><td>0.3009</td><td>0.3005</td><td>0.3008</td></tr><tr><td>r=r</td><td>0.0062</td><td>0.0061</td><td>0.0062</td></tr><tr><td>p C</td><td>-7.7853</td><td>-7.7853</td><td>-7.7751</td></tr><tr><td>p</td><td>-1.8668</td><td>-1.8668</td><td>-1.8655</td></tr></table></body></html>

S and only does so if $d$ is the reciprocal of $\boldsymbol{\mathscr{u}}$ . That is the case in this example, given the formula we chose to convert volatility to $\boldsymbol{\mathscr{u}}$ and $d$ , but it does not have to be in general.

Delta and gamma are computed as follows:

$$
\Delta_{c}=\frac{c_{u^{2}}-c_{d^{2}}}{S u^{2}-S d^{2}}=\frac{135.21-0}{222.55-44.93}=0.7612,
$$

$$
\Delta_{p}=\frac{p_{d^{2}}-p_{u^{2}}}{S u^{2}-S d^{2}}=\frac{42.41-0}{222.55-44.93}=0.2388,
$$

$$
\Gamma_{c}=\frac{\biggl(\frac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}\biggr)-\biggl(\frac{c_{u d}-c_{d^{2}}}{S u d-S d^{2}}\biggr)}{(1/2)(S u^{2}-S d^{2})}=\frac{\biggl(\frac{135.21-25.34}{22.35-100}\biggr)-\biggl(\frac{25.34-0}{100-44.93}\biggr)}{(1/2)(222.55-44.93)}=0.0049,3292\ldots
$$

$$
\Gamma_{p}=\frac{\left(\frac{\b{b}_{d^{2}}-\b{b}_{u d}}{S u d-S d^{2}}\right)-\left(\frac{\b{b}_{u d}-\b{b}_{u2}}{S u^{2}-S u d}\right)}{(1/2)(S u^{2}-S d^{2})}=\frac{\left(\frac{42.41-12.68}{100-44.93}\right)-\left(\frac{12.68-0}{222.5S-100}\right)}{(1/2)(222.55-44.93)}=0.0049.
$$

Theta is the same as in the standard method, but this will not always be the case. The.
period two time steps ahead in both models is the expiration, so the option value will be.
the same, but for models with more time steps, the thetas will not always be the same.

The expanded method works better for a limited number of time steps, but with the. incredible speed of the computers of today, most binomial computations can be done with. a large number of time steps reasonably fast. In that case, the length of each time step would be very short, and the standard method will give relatively accurate measures of delta and gamma. Let us work a problem with a large number of time steps. We will see in Chapter 9 that these answers should converge to those obtained from the Black-Scholes-Merton. model. Working the same problem with 500 time steps, we get the following results in Table 8.1, which we show alongside the Black-Scholes-Merton values.11

The differences are, as expected, quite small.
