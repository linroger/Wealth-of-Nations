---
title: Fixed Income Asset Pricing Midterm
aliases: [Fixed Income Asset Pricing Bus 35130 Spring 2019 John Heaton and Oleg Sydyak]
---

# Fixed Income Asset Pricing Midterm

Fixed Income Asset Pricing Bus 35130 Spring 2019 John Heaton and Oleg Sydyak

Midterm Solution

## INSTRUCTIONS

- There are 3 questions, each worth 35 points.

·The questions cover various aspects of the material covered in class.Read all the question and start from those with which you feel most comfortable

·Answer all questions to the best of your abilities.

- Do not get hung up in calculations. Sometimes, just setting up an equation or giving an intuitive argument are sufficient for partial credit (if correct!)Move on!
- You may use a calculator and refer to one 8.5" by 11" sheet of notes (two-sided).

·You must write your answers on this midterm.Use back pages for any calculations. No other piece of paper,besides your formula sheet, is allowed.

Honor Code:Ipledge my honor thatIhave notviolated the Honor Code during this exam ination.

------------------------------------------------------------------

Problem 1.(35 points) True/False Questions. Grade depends on completeness of answer

(1.A)(7 points)(True/False)The duration of a foating rate note with semi-annual pay ments is at most equal to 0.5.

True.As we know from TN 1 and the discussion in class (see homework),foating rate notes rest to $P=100$ at every coupon date.Let $T_{i}<t<T_{i+1}$ be the time between coupon payments $T_{i}$ and $T_{i+1}=T_{i}+0.5$,then

$$P(t)=e^{-r(t,T_{i+1})\times0.5}(100+c(T_{i+1})/2)$$

where $c(T_{i+1})$ is the (annualized)coupon payment at time $T_{i+1}$ and 100 is the price of the bond at time $T_{i+1}$，when it will reset back to 100.Because at $t$ the next coupon has been determined (by the interest rate at time $T_{i}$),the coupon $c(T_{i+1})$ is fixed as of time $t$.Therefore, this is like the value of a zero coupon bond that pays $(100+c(T_{i+1})/2)$ at $T_{i+1}$.It follows that its duration must be

$$D=-\frac{1}{P(t)}\frac{d\:P}{d\:r}=T_{i+1}-t$$

Thus, the maximum duration is $T_{i+1}-T_{i}=0.5$

(1.B)(7 points)[True/False|If the spot curve is increasing, the forward rate is above the spot curve,while if the spot curve is decreasing, the forward rate is below the spot curve.

True:This relation was developed also in TN 1.The continuously compounded forward rate is given by

$$f(0,T_1,T_2)=\frac{log(Z(0,T_1))-log(Z(0,T_2))}{T_2-T_1}=\frac{-r(0,T_1)T_1+r(0,T_2)T_2}{T_2-T_1}$$

which gives

$$f(0,T_1,T_2)=r(0,T_1)+T_2\frac{r(0,T_2)-r(0,T_1)}{T_2-T_1}$$

That is, the forward rate is equal to the spot rate plus a multiple of the slope of the term structure of the interest rate.If the slope is positive,the forward rate must be above the spot rate.If the slope is negative, the forward rate must be below the spot rate.

------------------------------------------------------------------

(1.C) (7 points) (True/False) The value of a fixed-for-floating swap is always equal to zero both at inception of the contract and later.

False. Indeed, in a fixed-for-foating swap, one counterparty received a fixed payment and pays a foating payment linked to, say, LIBOR. The fixed payment is set at time 0 to make the value of the contract equal to zero. Indeed, the value of a swap is given by the portfolio
$$V^{swap}(t,T)=P_{c}^{Fi}(t,T)-P^{Fl}(t,T)$$
where $P_{c}^{Fi}(t,T)$ is the value of a fixed rate bond with coupon rate ${\boldsymbol{L}}$,and $P^{Fl}(t,T)$ is the value of a floating rate bond. At initiation of the contract, the floating rate bond is just equal to par $P^{Fl}(t,T)=100$.The coupon rate $t$ is such that
$$V^{swap}(0,T)=0\Longrightarrow P^{Fi}(0,T)=100$$
However, once $\boldsymbol{L}$ is fixed, the value of the fixed rate bond $P_{c}^{Fi}(t,T)$ changes over time as the yield curve change, while the floating rate bond $P^{Fl}(t,T)$ resets to 100 every reset time. This implies that the value of the swap changes over time as the interest rates change.

------------------------------------------------------------------

(1.D) (7 points) (True/False) In binomial trees, risk neutral probabilities are crazy because they assume that investors are really risk neutral.Everyone knows that market participants are on average risk averse.

False: Agents are not risk neutral even if we use risk neutral probabilities.It is a pricing methodology that allows for easier formulas. Indeed, risk neutral probabilities are also called “risk adjusted” probabilities,meaning that the risk premium that market participants require to hold bonds is embedded in such probabilities. Indeed, it is possible to show that for any probability $\not{\mu}$,we must have that every security that depend on the interest rate must have a market price of risk

$$\frac{\frac{E^p[V_1]}{V_0}-\frac{1}{Z_0(1)}}{\frac{V_1u}{V_0}-\frac{V_1d}{V_0}}=\lambda $$

which gives the pricing formula

$$V_0=Z_0(1)\{E^p[V_1]-\lambda[V_{1u}-V_{1d}]\}$$

This relation holds for any $P$.When we use the “true”probability $F$,the above equation reflect the risk / return relation required to hold the security $V$:The risk premium (numerator) is the excess return while the denominator is the “risk" (plus or minus)to hold the security.

But for pricing purposes, the value $V_{0}$ is unchanged if we use different probabilities $P$.So, we can choose a probaibility $p=\pi^{\text{ 常}}$ such that $\lambda=0$ and therefore make the pricing formula simpler

$$V_0=Z_0(1)E^*[V_1]\Longrightarrow\frac{E^*[V_1]}{V_0}=\frac{1}{Z_0(1)}$$

Under the probability $\pi^{*}$ all securities must yield the risk free rate. Solving this equation also yields the formula for the risk neutral probability

$$\pi^*=\frac{V_0/Z_0(1)-V_{1d}}{V_{1u}-V_{1d}}.$$

------------------------------------------------------------------

(1.E) (7 points) (True/False) Suppose the current yield-to-maturity on a one-year Treasury Bill is $4\%$ and the market expect inflation of $2\%$ over the next year. The yield-to maturity on a one-year Treasury inflation protected security would necessarily be $2\%$

False.We know that
$$r_{nominal}(T)=r_{real}(T)+\pi(T)-1/2\sigma_{\pi}^{2}+RP$$
where $\pi(T)$ is expected inflation and $RP$ is theriskpremium due to inflation expo sure. There is also a small convexity adjust that needs to be made.

------------------------------------------------------------------

Problem 2. 35 points) You fit the following model to the current term structure of interest rates and you came up with the following binomial tree.The probability of moving up the tree is 1/2.(Risk-neutral). For simplicity, the time step is one year.

![](https://storage.simpletex.cn/view/fgvwoP8ktTzgZ1BHMGGZ6smehg5KdDsXq)

Compute the following:(Make sureyou show all the computations at allnodes.)

2.A7 points) Compute the price today $i=0$)of the one-，two-, three-period zerocoupon bonds. The model fits a risk neutral tree, for every $(i,j)$ we can use the usual recursive formula
$$Z_{i,j}(k)=e^{-r_{ij}}0.5\left(Z_{i+1,j}(k)+Z_{i+1,j+1}(k)\right)$$
giving the binomial trees

![](https://storage.simpletex.cn/view/fwbN4y1qhhNf0lwFObHviNg8GilrA0lu5)

------------------------------------------------------------------

(2.B)(5 points)Using the zero-coupon bonds prices from point 2.A,compute the one period forward rates for $i=1$ and $i=2$.How do they compare with expected interest rates computed from the tree (using the risk-neutral probabilities)?

The forward rat i gie byr $f(0,k,k+1)=-log(\frac{Z_{0}(k+1)}{Z_{0}(k)}$ thereby obtaing

$$f(0,1,2)=4.98\%\:;\:f(0,2,3)=5.92\%$$

Interestingly, the expected risk neutral interest rates are

$$E^{*}[r_{1}]=5\%\:;\:E^{*}[r_{2}]=6.0\%$$

These are indeed very close to forward rates.The difference is a convexity correction

(2.C)(7 points) The market expects that because of a tightening of monetary policy, the one-period interest rate at time $i=1$ will be $4\%$.What is the implied market price of risk? Comment on its sign and its economic meaning.

We can use the true expectation of interest rates to back out the real probability $P$ to move up the tree.In particular, we have

$$E^p[r_1]=pr_{1u}+(1-p)r_{1d}=4\%\Longrightarrow p=\frac{4\%-r_{1d}}{r_{1u}-r_{1d}}=0.25$$

Thus,we can compute the market price of risk from the usual formula

$$\lambda=\frac{\frac{E^p[Z_1(2)]}{Z_0(2)}-\frac{1}{Z_0(1)}}{\frac{Z_{1u(2)}}{Z_0(2)}-\frac{Z_{1d(2)}}{Z_0(2)}}=\frac{1.051217-1.0408}{-.04163}=-0.25$$

Because the zero coupon bond moves inversely to the underlying risk factor (the interest rate)- as shown in the denominator of $\lambda$ being negative -the negative $\lambda$ indicates a positive risk premium. That is, agents want to be compensated to hold interest rate risk.

------------------------------------------------------------------

(2.D)(8 points)An investor would like to purchase a security with payoff given by

$$\text{Payoff}(i)=\begin{cases}0&i=0\\100\times max(Average(r_0,r_1)-r_0,0)&i=1\\100\times max(Average(r_0,r_1,r_2)-r_0,0)&i=2\end{cases}$$

Compute the value, at time $\dot{i}=0$ of this American option.(Tip 1:At time $i=0$ and $i=1$, the investor can either exercise the option or wait to exercise the option Tip2:The calculations below may help speed up your own calculations.)

<table>
	<tbody>
		<tr>
			<th>Quantity</th>
			<th>Value</th>
		</tr>
		<tr>
			<td>$(r_{0}+r_{1,u}$</td>
			<td>0.055</td>
| 		</tr> |
| 		<tr> |
			<td>$1\boldsymbol{r}_{0}$ +</td>
			<td>0.035</td>
		</tr>
		<tr>
			<td>$r_{0}+r_{1,u}$ $+r_{2,uu}$</td>
			<td>0.07</td>
		</tr>
		<tr>
			<td>$(r_{0}+r_{1,d}+r_{2,uu}$</td>
			<td>0.0567</td>
		</tr>
		<tr>
			<td>$r_{0}+r_{1},u$ $+r_{2,ud}$</td>
			<td>0.0567</td>
		</tr>
		<tr>
			<td>1+ + $f^{*}.$ 1 - ${\mathcal{T} }_{i}$</td>
			<td>0.0433</td>
		</tr>
		<tr>
			<td>$\gamma_{0}+r_{1},\eta_{0}$ $u+ r_{2}$ $d$</td>
			<td>0.0433</td>
		</tr>
		<tr>
			<td>$(r_{0}+r_{1,d}+r_{2,dd}$</td>
			<td>0.03</td>
		</tr>
	</tbody>
</table>

First let's calculate the values ifyou exercise at eachnode

![](https://storage.simpletex.cn/view/fBNL5IC9P9FZgqR2dTnkeSU0RUIlcBS3D)

------------------------------------------------------------------

The value of the option is then given by

![](https://storage.simpletex.cn/view/ftlk1teGA9PlGx3dxNLAyynwRrA4LSL0X)

(2.E) (8 points) Compute the replicating portfolio for the security in 2.D at each node along the tree. What other securities do you use to replicate?Why? What weights do you get? Check that the replication in fact replicates the security's payoff at $i=1$ and that the price of your replicating portfolio at $i-0$ equals the price from 2.D. (Tip: If you are unable to solve $2.D$，you can still receive partial credit for a correct setup in terms of generic payoffs.)

To do this replication we need to calculate positions in two securities at each node to track the payoff. Since we need a security that matches the variation at node $i=2$ wewill usethe (initial)3-period zero along with a l-period zero at each node. We work backwards.Let's start at node $\dot{i}=1$ and $j=u$.Let $N_{1,u}^{1}$ be the position in the l-period zero at this node and $N_{1,u}^{2}$ be the position in what is, at that node at 2-period zero. This must satisfy:

$$\begin{array}{rcl}N_{1,u}^1\times100+N_{1,u}^2\times90.48&=&3\\N_{1,u}^1\times100+N_{1,u}^2\times94.18&=&1.67\end{array}$$

The solution is $N_{1,u}^{1}=0.3567$ and $N_{1,u}^{2}=-0.3611$. Notice that the value of this portfolio is: $0.3567\times93.24-0.3611\times86.09=2.1756$ The positions in state $i=1,j=d$ must satisfy

------------------------------------------------------------------

$$\begin{array}{rcl}N_{1,d}^1\times100+N_{1,d}^2\times94.18&=&0.3333\\N_{1,d}^1\times100+N_{1,d}^2\times98.02&=&0\end{array}$$

The solution is $N_{1,2}^{1}=0.0850$ and $N_{1,d}^{2}=-0.0867$.Notice that the value of this portfolio is: $0.0850\times97.04-0.0867\times93.26=0.1617$ Finally at time 0 the two positions must satisfy:

$$\begin{array}{rcl}N_0^1\times100+N_0^2\times86.09&=&2.1756\\N_0^1\times100+N_0^2\times93.26&=&0.1617\end{array}$$

The solution is $N_{0}^{1}=0.2636$ and $N_{0}^{2}=-0.2809$ with a value of 1.123

------------------------------------------------------------------

Problem 3.(35 points）The pension plan of BBB Corp has \$1.000.000 inliabilities and is 80% funded.Also there are three bonds available to invest in for the pension plan asset portfolio.The following table contains the main characteristics of the pension plan’s assets, liabilities and available bonds

<table>
	<tbody>
		<tr>
			<th> </th>
			<th>Price</th>
			<th>Duration</th>
			<th>Convexity</th>
		</tr>
		<tr>
			<td>Liability</td>
			<td>$\$1,000,000$</td>
			<td>10</td>
			<td>100</td>
		</tr>
		<tr>
			<td>Assets</td>
			<td>$\$800,000$</td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>$\mathrm{Bond}_{1}$</td>
			<td>$S100$</td>
			<td>14</td>
			<td>150</td>
		</tr>
		<tr>
			<td>$\mathrm{Bond}_2$</td>
			<td>$S100$</td>
			<td>8</td>
			<td>50</td>
		</tr>
		<tr>
			<td>$\mathrm{Bond}_{3}$</td>
			<td>$S100$</td>
			<td>2</td>
			<td>4</td>
		</tr>
	</tbody>
</table>

(3.a) (5 points)If we believe that interest rate term structure will only move in a parallel fashion in the future,then what kind of bond portfolio will always outperform liability for all possible interestrate movements and by the greatestpossible amount out of all bond portfolios based on only three available bonds?Using the available three bonds,determine what bond or bonds are required and determine the exact position or positions. Assume that only long positions can be entered into (no short positions) and you are free to use any set of bonds you wish along with Cash if needed.(You don't need to use all of the bonds)

Wewould like tofind aportfoliowhich matches the duration of the assets with not short positions and that has highest convexity. We need:

$$1,000,000\times D_A=800,000\times D_L$$

or

$$D_L=\frac{1,000,000}{800,000}\times10=12.5$$

$\mathrm{Bond}_{1}$ ·I will satisfy this requirement with:

$$x_1\times14=12.5,\:\mathrm{or}\:x=0.8929$$

We invest $0.829\times800,000=\$714,285.71$.The convexity of this position is 133.93. This is higher than can be achievedwithjust long positions using any of the other bonds.

------------------------------------------------------------------

(3.b) The plan sponsor would like to create a bond portfolio that exactly matches duration and convexity of the liability to that of the assets.

(3.b.i)(5 points) Discuss the pros and cons of this strategy The good part of this strategy is that the equity of the portfolio will be protected from relatively large parallel shifts in the yield curve.However,it would not be protected from non-parallel shifts in the yield curve.

------------------------------------------------------------------

(3.b.i) (8 points) Select the two most appropriate bonds out of three available and determine the bond positions. Once the bond positions are determined, please illustrate that the total bond portfolio is not greater than the total assets avail able (it is okay to be smaller). As before, no short positions are allowed (i.e bond weights can not be negative). Explain intuitively why any other combination of bonds out of three available will not be suitable

With no short positions we need a combination of bonds such that their duration and convexity values straddle those of the liability (suitably scaled). This will work if we use bonds 1 and 2.Let ${:}E1$ be the position in bond 1 and ${\mathcal{L}}2$ be the position in bond 2.We need to satisfy:

$$\begin{array}{rcl}800,000\times(x_1\times14+x_2\times8)&=&1,000,000\times10\\800,000\times(x_1\times150+x_2\times50)&=&1,000,00\times100\end{array}$$

The solution to this is $x_{1}=0.75$ and $x_{2}=0.25$.This means $75\%\times\$800,000=\$600,000$ invested in bond 1 and $\$200,00$ in bond 2. There is zero cash position

------------------------------------------------------------------

(3.c) (4 points) Suppose now that you conduct a Principal Component Analysis of the yield curve and determine that three principal components are need to fit changes in the yield curve.Would you be comfortable with your hedge from part (3.b.ii)? Why or why not? If not, discuss how you might construct a better hedge. Would you need all three bonds in this case? Why or why not? I would not be comfortable with the positions so far since they would not be able to match three important characteristics of the yield curve. I would need to use all three bonds to match the Principal Component exposures of the liability position.

------------------------------------------------------------------

(3.d) XYZ insurance company has liability cash fows (aka benefit payouts), as summarized in the following table, for their annuity line of business. The table also contains continuously compounded spot rates, corresponding Z-factors and three PCA $\beta$ 's for Level, Slope and Curvature factors respectively. "Time” column in the table is the number of years from today until the payments are due, i.e. all the payments are made annually, with spot rates, Z-Factors, and PCA $\beta$ 's shown at the same annual frequency (TIP: this is a standalone question and not a continuation of questions 3a-3c)

<table>
	<tbody>
		<tr>
			<th>$\overline{\mathrm{Time}}$</th>
			<th>Spot Rates </th>
			<th>Z-Factors</th>
			<th>$\overline{\beta_{Level}}$</th>
			<th>$\overline{\beta_{\varsigma}}$ $l_{Slope}$</th>
			<th>$\overline{\beta_{Curvature}}$</th>
			<th>$\overline{{\mathrm{Liability}}}$ $CF$</th>
		</tr>
		<tr>
			<td>1</td>
			<td>0.0300</td>
			<td>0.9704</td>
			<td>0.0968</td>
			<td>0.3189</td>
			<td>0.2003</td>
			<td>$\$1,000$</td>
		</tr>
		<tr>
			<td>2</td>
			<td>0.0360</td>
			<td>0.9305</td>
			<td>0.1453</td>
			<td>0.0802</td>
			<td>(0.1099)</td>
			<td>$\$1,100$</td>
		</tr>
		<tr>
			<td>3</td>
			<td>0.0432</td>
			<td>0.8784</td>
			<td>0.1298</td>
			<td>(0.0500)</td>
			<td>(0.1348</td>
			<td>$\$1,200$</td>
		</tr>
		<tr>
			<td>4</td>
			<td>0.0518</td>
			<td>0.8129</td>
			<td>0.1227</td>
			<td>(0.0945</td>
			<td>(0.0257)</td>
			<td>$\$1,300$</td>
		</tr>
		<tr>
			<td>5</td>
			<td>0.0622</td>
			<td>0.7327</td>
			<td>0.1216</td>
			<td>(0.0988</td>
			<td>0.1314</td>
			<td>$\$1,400$</td>
		</tr>
	</tbody>
</table>

(3.d.i) (8 points). Using only information from the table above (and not the information for questions 3a-3c), calculate factor sensitivities (i.e. factor duration) for Level, Slope and Curvature factors a) for XYZ insurance company's Liability, using liability cash flows provided in the table above, and b) for three hypothetical zero coupon bonds with 1,3 and 5years to maturity respectively and principal $\$1000$ each

First let's calculate the relative value of the liability atdifferent horizons

<table>
	<tbody>
		<tr>
			<th>Time</th>
			<th>Value of Liability</th>
			<th>Relative Value of Liability</th>
		</tr>
		<tr>
			<td>1</td>
			<td>$0.9704\times1,000$ )=970.40</td>
			<td>$18.91\%$</td>
		</tr>
		<tr>
			<td>2</td>
			<td>$0.9305\times1,100=1,023.40$</td>
			<td>$19.95\%$</td>
		</tr>
		<tr>
			<td>3</td>
			<td>$0.8784\times1,200=1,054.08$</td>
			<td>$20.55\%$</td>
		</tr>
		<tr>
			<td>4</td>
			<td>$0.8129\times1,300=1,056.77$</td>
			<td>$20.60\%$</td>
		</tr>
		<tr>
			<td>5</td>
			<td>$0.7327\times1,400=1,025.78$</td>
			<td>$19.99\%$</td>
		</tr>
		<tr>
			<td>$\overline{Sum}$</td>
			<td>5,130.58</td>
			<td>$100\%$</td>
		</tr>
	</tbody>
</table>

The factor exposures for the liability would then be

- For Level:

$$\begin{array}{rcl}1\times18.91\%\times0.0968&+&2\times19.95\%\times0.1453+3\times20.55\%\times0.1298\\&+&4\times20.60\%\times0.1227+5\times19.99\%\times0.1216\\&=&0.3789\end{array}$$

·For Slope:

$$\begin{aligned}1\times18.91\%\times0.3189&+\quad2\times19.95\%\times0.0802+3\times20.55\%\times(-0.0500)\\&+\quad4\times20.60\%\times(-0.0945)+5\times19.99\%\times(-0.0922)\\&=\quad-0.1151\end{aligned}$$

------------------------------------------------------------------

For Curvature:
$$\begin{aligned}1\times18.91\%\times0.3003&+\quad2\times19.95\%\times(-0.1099)+3\times20.55\%\times(-0.1348)\\&+\quad4\times20.60\%\times(-0.0257)+5\times19.99\%\times0.1314\\&=\quad0.0211\end{aligned}$$
The exposures for the three zero coupon bonds are givenby:

<table>
	<tbody>
		<tr>
			<th>Bond Maturity</th>
			<th>$\mathrm{Level}$</th>
			<th>Slope</th>
			<th>Curvature</th>
		</tr>
		<tr>
			<td>1</td>
			<td>$1\times0.0968=0.0968$</td>
			<td>0.3189</td>
			<td>0.2003</td>
		</tr>
		<tr>
			<td>3</td>
			<td>$3\times0.1298=0.3894$</td>
			<td>$3\times(-0.0500)=-0.1500$</td>
			<td>$3\times(-0.1348)=-0.400$</td>
		</tr>
		<tr>
			<td>5</td>
			<td>$5\times0.1216=0.6080$</td>
			<td>$5\times(-0.0988)$ =-0.4940</td>
			<td>$5\times0.1314=0.6570$</td>
		</tr>
	</tbody>
</table>

------------------------------------------------------------------

(3.d.i) (5 points) Using factor sensitivities for XYZ insurance company's liability and three bonds calculated in the previous question (3.d.i), discuss how you can establish individual bond positions in a three bond portfolio such that bond portfolio's facton sensitivities would match liability's factor sensitivities for all three factors. Write down all the necessary equations but there is no need to solve them, i.e. no need to calculate actual bond positions

Let's assume that this fund is fully funded.We then need to match factor sensitivi ties of assets and liabilities. Let ${\mathcal{L}}1$，$l2$, and ${:}L5$ be the percent of assets in bonds with maturities 1, 2, and 5 years respectively. The we would need to solve the following set of equations

$$\begin{aligned}x_{1}\times0.0968+x_{2}\times0.3894+x_{5}\times0.6080&=\quad0.3789\\x_{1}\times0.3189+x_{2}\times(-0.1500)+x_{5}\times(-0.4940)&=\quad(-0.1151)\\x_{1}\times0.2003+x_{2}\times(-0.400)+x_{5}\times0.6570&=\quad0.0211\end{aligned}$$

------------------------------------------------------------------

### Fixed Income Asset Pricing Bus 35130 John Heaton

Midterm Solutions, Spring 2022

1. (60 points, 10 points each) Short-Answer/True-False Questions. Grade depends on com pleteness of answer,however you should try to be short and to the point in your response We're only looking for the obvious big point(s). We don’t give credit for long winded answers and will take off points if you add things that are wrong or irrelevant

(a) The duration of zero coupon bonds is given by its time to maturity. Therefore, it is independent of current interestrates.It follows that the convexity of a zero coupon bond has to be zero.

False: The convexity of a zero coupon bond is not the change in duration,but it is related to the second derivative of the security, divided by the price. The logic of $C=\frac{1}{Z(T)}\frac{d^{2}Z(T)}{dr^{2}}$ stens fron the second order Tayloraproximaion that has

$$Z(r+dr,T)\approx Z(r,T)+Z'(r,T)dr+\frac{1}{2}Z''(r,T)dr^2$$

where $Z^{\prime}(r_{0},T)$ and $Z^{\prime\prime}(r_{0},T)$ are the first and second derivative of $Z(r, T)$ = $exp(-rT)$ with respect to 7.Dividing by $Z(r,T)$ on both sides to compute the return, we obtain

$$\frac{Z(r+dr,T)-Z(r,T)}{Z(r,T}\approx-Ddr+\frac{1}{2}Cdr^{2}$$

where $D=-1/Z(r,T)Z^{\prime}(r,T)$ and $C=1/Z(r,T)Z^{\prime\prime}(r,T)$.As can be seen, $C$ is not the first derivative of $D$.In fact, in this case, we find

$$C=\frac{1}{Z(r,T)}Z''(r,T)=T^2$$

which is quite different from zero.

(b) Changes in the slope of the term structure of interest rates can be effectively hedged through the so called “Duration and Convexity" hedging

False:Duration and convexity hedging aim at hedging against large changes in the interest rates, as when rates move far and suddenly, some convexity effect generate positive or negative returns on the bond, not captured by the duration component (which is only linear).

Instead, changes in the slope of the term structure of interest rates can be effectively achieved by performing a factor neutrality approach. Using Principal Component Analysis, we can extract the factors, which normally generate a level, a slope, and a curvature factor. The slope factor can be then hedged by taking a position in a security that loads on the slope factor (i.e. with its beta on the factor different from 1, and in fact large).

------------------------------------------------------------------

(c)The following quotes are from Bloomberg and are from a single day:

<table>
	<tbody>
		<tr>
			<th>$\mathrm{Maturity}$ $^{\prime\prime}T$</th>
			<th>$\mathrm{LIBOR}$</th>
			<th>3 month Forward Rate $F(T$,</th>
			<th>$T+3$ months </th>
		</tr>
		<tr>
			<td>3 months</td>
			<td>$1.18438\%$</td>
			<td>$F(3~month.6~month)\colon$</td>
			<td>$\overrightarrow{07}_{0}$ 1.231</td>
		</tr>
		<tr>
			<td>months 6</td>
			<td>$1.66\%$</td>
			<td>$F(6~month,9~month)\colon$</td>
			<td>$\%$ 1.281</td>
		</tr>
		<tr>
			<td>9 months</td>
			<td>$1.82375\%$</td>
			<td>$F(9\:r$ $month,1\:s$ $year):$</td>
			<td>$1.45\%$</td>
		</tr>
		<tr>
			<td>1 vear</td>
			<td>$1.975\%$</td>
			<td> </td>
			<td> </td>
		</tr>
	</tbody>
</table>

There is an arbitrage in the quoted forward rate $F(9~months,1~year)~=~1.45\%$ compared to LIBOR rates. Discuss.

True: Yes, there is an arbitrage.To find out,we need to compute the forward rate implied by LIBOR quotes.And for this,we only need the “zero coupon bond prices implied by LIBOR curve
$$\begin{aligned}Z(0,0.75)&=\quad\frac{1}{1+LIBOR(9m)\times0.75}=\frac{1}{1+.0182375\times0.75}=0.9865;\\Z(0,1)&=\quad\frac{1}{1+LIBOR(12m)\times1}=\frac{1}{1+.01975}=0.9806\end{aligned}$$
Therefore
$$F^{LIBOR}(0.75,1)=\frac{1}{0.25}\left(\frac{Z(0,0.75)}{Z(0,1)}-1\right)=\frac{1}{0.25}\left(\frac{0.9865}{0.9806}-1\right)=2.407\%$$
The forwardrate implied by the LIBOR is far larger than the quoted FRA.Accord ing to the model, there is an arbitrage opportunity.

The following was not required to get full credit, but it is interesting to see how to exploit the arbitrage Because $F^{LIBOR}>F^{Quoted}$ we want to go long the security that gives us $F^{LIBOR}$

and short the security that makes us pay $F^{Quoted}$.The latter is simple, we simply enter into a FRA with a counterparty to receive LIBOR and pay the quoted FRA That is, denoting $T_{1}=0.75$ and $T_{2}=1=T_{1}+\Delta$ and $\Delta=0.25$,we have at $T_{2}$
$$\text{Cash Flow at}T_2\text{from FRA}=\left(LIBOR(0.75)-F^{Quoted}(T_1,T_2)\right)\Delta $$
How do we get $FLIBOR?$ We simply have to borrow and lend at LIBOR in the appropriate direction. In particular, by just looking at the formula for $F^{LIBOR}$,we se thathi sgiventh the ae teadtet roe $\frac{Z(0,0.75)}{Z(0,1)}-1]$ yea seroed reis follows

i. Sell one zero coupon bond maturing at $T_{1}=0.75$ for $Z(0,T_{1})$ ii. Buy $N=Z(0,T_{1})/Z(0,T_{2})$ zero coupon bond maturing at $T_{2}=1$ ·Today we are even,the total amount need for the long position is $N\times$ $Z(0,T_{2})=Z(0,T_{1})$ which equals the cash received from the short position.

------------------------------------------------------------------

At time $T_{1}=0.75$，we have to pay 1 from the short position in $Z(0,T_{1})$.Assume we borrow at whatever LIBOR rate will be available, $LIBOR(T_{1})$, for the following three month

At time $T_{2}=1$，we have to pay $1+LIBOR(T_{1})\Delta$ from the previous step, where $\Delta=0.25$ is the three month interval, but we receive $N$ from the long position in zero coupon.So,the total net cash fow

Net CashFlow at
$$\begin{array}{rcl}{\textrm{t}T_{2}\textrm{from Trading}}&{=}&{N-(1+LIBOR(T_{1})\Delta)}\\&{=}&{(Z(0,T_{1})/Z(0,T_{2})-1)-LIBOR(T_{1})\Delta}\\&{=}&{F^{LIBOR}\Delta-LIBOR(T_{1})\Delta}\end{array}$$

Summing the Net Cash Flow from Trading to the Cash Flow from FRA position, we obtain
$$\text{Arbitrage Profit}=F^{LIBOR}\Delta-F^{Quoted}\Delta>0$$

(d) The expectation hypothesis - the fact that the long-term yield equals the market forecast of future short-term rates is strongly supported by the historical data.

False: The expectation hypothesis is mostly violated in the data.For instance, the expectation hypothesis implies

$$f(t,t+9,t+12)=E_t[y_{t+9}]$$

where $y_{t+9}$ is the 3-month sport rate at time $t+9$, which we saw was vaiolated in the data when we proxy the expectation using professional forecasters' forecasts.

Similarly,the expectation hypothesis implies that the slope of the term structure $y_{t}(n)-y_{t}(1)$ should predict an increase in the yield $y_{t}(n)$ to a higher value $E[y_{t+1}(n-$ $1)]>y_{t}(n)$.But the data strongly suggest the opposite, namely, that a steep yield curve imply that long-term yields actually decline The evidence is suggestive of a time-varying risk premium

(e) The payoff of a receiver swaption is equivalent to the payoff of a call option on a coupon bond with coupon rate equal to the swap rate. Such call option has a strike price of par (=100)

True: A receiver swaption is an option to enter into a swap at a given maturity $T_{0}$ and received the fixed rate $C$ against LIBOR in a swap with tenor 7.The owner of a swaption will only exercise when the market swap rate at time $T_{O}$ is below the strike swap rate $\bar{c}$. In other words, the option owner will exercise at $T_{0}$ if and only if the value of the swap with swap rate $\mathbb{C}$ is positive. The payoff of the swaption is thus
$$\mathrm{Payoff}_{T_O}=\max\left(V_{T_O}^{Swap},0\right)$$

The value of a swap is equal to the fixed leg minus the floating leg, whose value is always par at reset dates:

$$V_{T_O}^{Swap}=P_{\overline{c}}(T_O,\tau)-100$$

------------------------------------------------------------------

where $P_{\overline{c}}(T_{O},\tau)\:=\:\sum_{j=1}^{n}Z(T_{0},T_{j})\overline{c}\Delta+\:Z(T_{O},\tau)$ (where we assume $T_{n}=\tau$）.It follows that the payoff of a swaption is
$$\mathrm{Payoff}_{T_{O}}=\max\left(P_{\overline{c}}(T_{O},\tau)-100,0\right)$$
which is the value of a call option on a coupon bond whose discounts $Z(T_{O},T_{j})$ are determined by the LIBOR curve at $T_{O}$

(f) The duration of an inverse foater may be higher than the time to maturity of the floater.

True:An inverse foater pays a coupon $c=c-r$.Say $T$ is its maturity. Therefore it can be replicated by a portfolio that is (A) long a coupon bond with coupon $C$ and maturity $I$, (B) short a floating rate bond with maturity 7,and (C) long a zero coupon bond with maturity $T$.The value is
$$P_{IV}=P_{Bonds}-P_{FR}+Z(0,T)$$
The duration of the inverse floater is
$$D_{IV}=w_{Bond}D_{Bond}+w_{FR}D_{FR}+w_{Zero}D_{Zero}$$
where
$$w_{Bond}=\frac{P_{bond}}{P_{I}V};\:w_{FR}=\frac{-P_{FR}}{P_{IV}};\:w_{Zero}=\frac{Z(0,T)}{P_{IV}}$$
Because $D_{FR}\approx0$ and $D_{Zero}=T$, it may well be possible for $D_{IV}>T$.An example was homework 2 for an leveraged inverse floater

[This is ecample - or an ecample like thiswas not required to get full credit/ For instance, if $r\approx0$ for every maturity, then $Z(0,T_{j})\approx1$ for every maturity, then
$$P_{Bond}=\overline{c}\Delta\sum_{j=1}^nZ(0,T_j)+Z(0,T)=\overline{c}\Delta n+1$$
Thus,at reset dates
$$P_{IV}=\bar{c}\Delta n+1-1+1=\bar{c}\Delta n+1$$
Therefore, $w_{Bonds}=1$，$w_{FR}=-1/(\bar{c}\Delta n+1)$ and $w_{zero}=1/(\bar{c}\Delta n+1)$.It follows that
$$D_{IV}=D_{Bond}+\frac{1}{\bar{c}\Delta n+1}T$$
As $\bar{C}$ declines $D_{Bond}\to T$ and the weight on zero coupon converges to1,giving a value above $T$

2.(50 points)You asked your assistant to fit some bond prices, and he came back with the following binomial trees for zero-coupon bonds.The true probability to go up the tree is $p=0.5$ and the time step is one year. Unfortunately, as you and your assistant were communicating, one entry. $(Z_{1,u}(3))$ did not go through, hence the question marks?? in the tree.Your assistant left for vacation and cannot be reached.

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/feYRfxwLulAiWLgN9RuVplNyguUBXoth9)

(a)(5 points) Compute the risk neutral probability at time $i=0$

The risk neutral probability is

$$\pi^*=\frac{Z_0(2)/Z_0(1)-Z_{1d}(2)}{Z_{1u}(2)-Z_{1d}(2)}=\frac{0.9/0.96-0.97}{0.92-0.97}=0.65$$

(b) (5 points) What is the value of $Z_{1,u}(3)$

Given the risk neutral probability, we can compute $Z_{1,u}(3)$ by recalling that every bond must yield the risk free rate under the risk neutral probabilities.That is,we know
$$\pi^*\frac{Z_{1u}(3)}{Z_0(3)}+(1-\pi^*)\frac{Z_{1d}(3)}{Z_0(3)}=\frac{1}{Z_0(1)}$$

which we can use to solve for $Z_{1u}(3)$

$$Z_{1u}(3)=\frac{\frac{Z_0(3)}{Z_0(1)}-(1-\pi^*)Z_{1d}(3)}{\pi^*}=\frac{0.85/.96-(1-0.65)\times0.94}{0.65}=0.856$$

(c）Erpected Bond Returns in Eccess of Risk Free Rate(not risk neutralexpectations here! Use the true ones for this part of the question.)

i.(5 points) What is the expected ercess return between $i=0$ and $i=1$ from an investment at time 0 in the 2-period bond $Z_{0}(2)$

------------------------------------------------------------------

The true probability to go up the tree is 0.5.Therefore.

$$\begin{aligned}E\left[\frac{Z_{1}(2)}{Z_{0}(2)}\right]-\frac{1}{Z_{0}(1)}&=\quad0.5\left(\frac{Z_{1u}(2)}{Z_{0}(2)}\right)+0.5\left(\frac{Z_{1d}(2)}{Z_{0}(2)}\right)-\frac{1}{Z_{0}(1)}\\&=\quad0.5\left(\frac{0.92}{0.9}\right)+0.5\left(\frac{0.97}{0.9}\right)-\frac{1}{0.96}\\&=\quad0.833\%\end{aligned}$$

ii.(10 points)Is this expected excess return (over the same period)the same as for an investment at time 0 in the 3-period bond $Z_{0}(3)$?If not,why not? Be as precise as possible.

In this case we have

$$\begin{aligned}E\left[\frac{Z_{1}(3)}{Z_{0}(3)}\right]-\frac{1}{Z_{0}(1)}&=\quad0.5\left(\frac{Z_{1u}(3)}{Z_{0}(3)}\right)+0.5\left(\frac{Z_{1d}(3)}{Z_{0}(3)}\right)-\frac{1}{Z_{0}(1)}\\&=\quad0.5\left(\frac{0.856}{0.85}\right)+0.5\left(\frac{0.94}{0.85}\right)-\frac{1}{0.96}\\&=\quad1.482\%\end{aligned}$$

The expected return is larger for the long-term bond.The reason,we should remember,is that all bonds on a tree have the same market price of risk

$$\lambda=\frac{\text{Expected Excess Return}}{(Risk)}=\frac{E\left[Z_1(T)/Z_0(T)\right]-1/Z_0(1)}{Z_{1u}(T)/Z_0(T)-Z_{1d}(T)/Z_0(T)}$$

Therefore, we obtain

$$E\left[\frac{Z_1(T)}{Z_0(T)}\right]-\frac{1}{Z_0(1)}=\lambda\left(\frac{Z_{1u}(T)}{Z_0(T)}-\frac{Z_{1d}(T)}{Z_0(T)}\right)$$

Long-term bonds have a higher expected excess returns simply because they have a higher risk.

(d）Consider a forward contract to purchase a l-period zero coupon bond at time $i=1$ for a price $F$.The payoff of the forward contract at $i=1$ is

$$\text{Payoff at 1}=Z_1(2)-F$$

The value of aforwardcontract isalwavs zero at time 0.

i.(15 points)What is the value of $F$?How does it compare with the risk neutral expected value of $E_{0}^{*}[Z_{1}(2)]$?How about with the forward discount $F(0,1,2)$ which can be computed from current bond prices? In each case explain any differences.

The risk neutral formula says that the value of the forward is

$$V_0=Z_0(1)\times E^*[Z_1(2)-F]$$

Because $V_{0}=0$,we immediately have

$$F=E^*[Z_1(2)]=\pi^*Z_{1u}(2)+(1-\pi^*)Z_{1d}(2)=0.65\times0.92+(1-0.65)\times0.97=0.9375$$

------------------------------------------------------------------

The forward discount isgiven by

$$F(0,1,2)=\frac{Z(0,2)}{Z(0,1)}=\frac{0.9}{0.96}=0.9375$$

They are the same! The forward discount just equals the risk-neutral expected future discount.

i. (10 points) What is a replicating strategy for the payoff to the forward contract? Do you actually need the binomial tree to create this strategy? Why or why not?

From the tree, the replicating portfolio is a portfolio of the underlying $Z_{0}(2)$ and short term bond $Z_{0}(1)$ given by

$$\begin{array}{rcl}\Delta&=&\dfrac{Pay_{1u}-Pay_{1u}}{Z_{1u}(2)-Z_{1d}(2)}=\dfrac{(Z_{1u}(2)-F)-(Z_{1d}(2)-F)}{Z_{1u}(2)-Z_{1d}(2)}=1\\N_{0}&=&Pay_{1u}-\Delta Z_{1u}(2)=-0.9375\end{array}$$

That is, we go long the long term bond, and we short 0.9375 of the short-term bond. Note that this is exactly the same strategy we would do also without a tree (i.e.we do not need a tree).

That is, the replication strategy works whether we use trees or not. Indeed, this portfolio at time $t=1$ is

$$P_1=\Delta Z_1(2)+N_0Z_1(1)=Z_1(2)-0.9375=Z_1(2)-F=\text{Payoff of forward contract}$$

------------------------------------------------------------------

3.(35 points) Using the history of changes in interest rates,you computed the following "betas" from principal component analysis

<table>
	<tbody>
		<tr>
			<th> </th>
			<th colspan="8">Maturity</th>
		</tr>
		<tr>
			<th>Factor</th>
			<th>3 months</th>
			<th>6 months</th>
			<th>1 year</th>
			<th>2 year</th>
			<th>4 year</th>
			<th>6 year</th>
			<th>8 year</th>
			<th>10 year</th>
		</tr>
		<tr>
			<td rowspan="3">$\beta_{i1}^{PCA}$ $R^{\tilde{2}}$</td>
			<td> </td>
			<td> </td>
			<td>$\overline{{\mathrm{P}}}$</td>
			<td>${\mathrm{anel~A:}}$</td>
			<td>$\overline{\mathrm{Level}}$</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>0.26</td>
			<td>0.28</td>
			<td>0.28</td>
			<td>0.26</td>
			<td>0.22</td>
			<td>0.18</td>
			<td>0.16</td>
			<td>0.15</td>
		</tr>
		<tr>
			<td>$75\%$</td>
			<td>$88\%$</td>
			<td>$96\%$</td>
			<td>$96\%$</td>
			<td>$89\%$</td>
			<td>$81\%$</td>
			<td>$71\%$</td>
			<td>$61\%$</td>
		</tr>
		<tr>
			<td rowspan="3">$\beta_{i2}^{PCA}$ $R^{\tilde{2}}$</td>
			<td> </td>
			<td> </td>
			<td>$\overline{{\mathrm{P}}}$</td>
			<td>$\mathrm{anel~B:}$</td>
			<td>$\mathrm{Slope}$</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>-0.40</td>
			<td>-0.24</td>
			<td>-0.08</td>
			<td>0.08</td>
			<td>0.12</td>
			<td>0.23</td>
			<td>0.24</td>
			<td>0.24</td>
		</tr>
		<tr>
			<td>$98\%$</td>
			<td>$97\%$</td>
			<td>$97\%$</td>
			<td>$97\%$</td>
			<td>$99\%$</td>
			<td>$97\%$</td>
			<td>$90\%$</td>
			<td>$81\%$</td>
		</tr>
		<tr>
			<td rowspan="3">$IIL$ $\beta_{i3}^{PCA}$ $R^{\ddot{2}}$</td>
			<td> </td>
			<td> </td>
			<td>$\overline{\mathrm{Pan}}$</td>
			<td>$\boxed{C:}$ $:\mathbb{C}$ $\mathrm{lel}$ $w$</td>
			<td>$\operatorname{lrvature}$</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>-0.17</td>
			<td>0.07</td>
			<td>0.20</td>
			<td>0.19</td>
			<td>0.01</td>
			<td>-0.17</td>
			<td>-0.30</td>
			<td>-0.39</td>
		</tr>
		<tr>
			<td>$99\%$</td>
			<td>$97\%$</td>
			<td>$99\%$</td>
			<td>$99\%$</td>
			<td>$99\%$</td>
			<td>$100\%$</td>
			<td>$99\%$</td>
			<td>$98\%$</td>
		</tr>
	</tbody>
</table>

(a)(15 points) What are the factor durations of 3-months, 4-year, and 10-year zerocoupon bonds? Compute them for all three factors and provide an intuitive reason for their values.

One can read off the factor duration from the table. For each zero-coupon bond with maturity $T_{i}$,the factor duration is
$$D_j(T_i)=T_i\beta_{ij}$$
So,we have

<table>
	<tbody>
		<tr>
			<th>Maturity</th>
			<th>3m</th>
			<th>$4y$</th>
			<th>$10y$</th>
		</tr>
		<tr>
			<td>$\overline{\mathrm{Level}}$</td>
			<td>$0.25\times0.26=0.065$</td>
			<td>$4\times0.22=0.88$</td>
			<td>$10\times0.15=1.5$</td>
		</tr>
		<tr>
			<td>Slope</td>
			<td>$0.25\times(-0.4)=-0.1$</td>
			<td>$4\times0.12=0.48$</td>
			<td>$10\times0.24=2.4$</td>
		</tr>
		<tr>
			<td>Curvature</td>
			<td>0.25 $\times(-0.17)$ =-0.042</td>
			<td>$4\times0.01=0.04$</td>
			<td>$10\times(-0.39)=-3.9$</td>
		</tr>
	</tbody>
</table>

(b)Your fund is long $\$100$ million in a particular fixed income portfolio. This portfolio has factor durations $D_{level}=0$ and $D_{slope}=-15$.The current term structure is flat at $5\%$ (continuously compounded)

i.(5 points)Suppose the level factor increases by 100bps and the slope factor also by 100bps. What is the impact on this portfolio? The approximate formula is
$$\frac{dP}{P}\approx-D_1\times\Delta\phi_1-D_2\times\Delta\phi_2$$
Therefore
$$\frac{dP}{P}\approx0\times100bps+15\times100bps=1500bps=15\%$$
ii.(10 points) Design a hedging strategy using the zero coupon bonds in 3a to hedge these positions.(You do not necessarily need to use all of them!)Discuss the choice of bonds in your answer.(Note:Partial credit given to set up the problem right, even without full numerical solution.

------------------------------------------------------------------

The hedged position is then

$$V=P+k_{3m}Z(3m)+k_{10y}Z(10y)$$

so that the change in value is

$$dV=dP+k_{3m}dZ(3m)+k_{10y}dZ(10y)$$

Using the factor representation

$$\begin{aligned}dV\approx&-D_{Level}Pd\phi_{1}&-D_{Slope}Pd\phi_{2}\\&-k_{3m}Z(3m)D_{3m,Level}d\phi_{1}&-k_{3m}Z(3m)D_{3m,Slope}d\phi_{2}\\&-k_{10y}Z(10y)D_{10,Level}d\phi_{1}&-k_{10y}Z(10y)D_{10,Slope}d\phi_{2}\end{aligned}$$

Therefore, to make $dV\approx0$ weneed

$$0=-D_{Level}P-k_{3m}Z(3m)D_{3m,Level}-k_{10y}Z(10y)D_{10,Level}\\0=-D_{Slope}P-k_{3m}Z(3m)D_{3m,Slope}-k_{10y}Z(10y)D_{10,Slope}$$

Because $D_{Level}=0$, we obtain

$$k_{3m}=-k_{10y}\frac{Z(10y)D_{10,Level}}{Z(3m)D_{3m,Level}}$$

Substitute into the "Slope equation,to find

$$\begin{aligned}k_{10y}&=\quad\frac{D_{Slope}P}{\left(\frac{Z(10y)D_{10,Level}}{Z(3m)D_{3m,Level}}Z(3m)D_{3m,Slope}-Z(10y)D_{10,Slope}\right)}\\&=\quad\frac{P}{Z(10y)}\frac{D_{10,Level}}{\left(\frac{D_{10,Level}}{D_{3m,Level}}D_{3m,Slope}-D_{10,Slope}\right)}\\&=\quad\frac{100}{e^{-.05\times10}}\frac{-15}{\left(\frac{1.5}{0.065}(-.1)-2.4\right)}\\&=\quad525.33\end{aligned}$$

Hence

$$k_{3m}=-525\frac{e^{-.05\times10}1.5}{e^{-.05\times0.25}.065}=-7445.43$$

In essence, to hedge the slope factor, we have to go long 525 million worth of 10-year bond, and short 7.445 billion worth of 3-month bonds. These are pretty extreme positions

ii.(5 points) Would the hedging strategy of part 3(b)i leave the fund with facton and/or residual risk exposure? Why or why not? Yes. You have not hedged curvature or residual risk

------------------------------------------------------------------

4. (35 points) Freddie Mac is one of the key players in mortgage backed securities market. The following statements are from a Freddie Mac's Annual Report at a time when Freddie Mac was a privately owned company:

“Our primary interest-rate risk measures are PMVS [Portfolio Market Value Sensitivity] and duration gap. PMVS is an estimate of the change in the market value of our net assets and liabilities from an instantaneous 50 basis point shock to interest rates. [.]PMVS is measured in two ways, one measuring the estimated sensitivity of our portfolio market value to parallel movements in interest rates (PMVS-Level or PMVS-L) and the other to nonparallel movements (PMVS-YC) [] The duration and convexity measures are used to estimate PMVS under the following formula: PMVS = -/Duration/ multiplied by [rate shock] plus [0.5 multiplied by Convezity] multiplied by [rate shock]2 [] To estimate PMVS-L, an instantaneous parallel 50 basis point shock is applied to the yield curve, as represented by the US swap curve []. This shock is applied to the duration and convexity of all interest-rate sensitive financial instruments. [] To estimate sensitivity related to the shape of the yield curve, a yield curve steepening and flattening of 25 basis points is applied to the duration of all interest-rate sensitive instruments. [..] The more adverse yield curve scenario is then used to determine thePMVS-yield curve."

Suppose for simplicity that the portfolio of Freddie Mac's assets is given by 1 unit each of the 1-year and the 10-year zero-coupon bonds in the table below. In addition, its liabilities are given by 2 units of the 7-year zero coupon bond (I know all these bonds have positive convexity, and not negative convexity as mortgage backed securities, but for the sake of this exercise, this will do).

------------------------------------------------------------------

Table 1:vields and discounts

<table>
	<tbody>
		<tr>
			<th> </th>
			<th>1 year</th>
			<th>7 year</th>
			<th>10 year</th>
		</tr>
		<tr>
			<td>$\dot{t}$ 1</td>
			<td>0.7125</td>
			<td>1.7307</td>
			<td>2.1456</td>
		</tr>
		<tr>
			<td>$Z(0,t)$</td>
			<td>99.29</td>
			<td>88.59</td>
			<td>80.69</td>
		</tr>
	</tbody>
</table>

(a) (15 points) Compute the duration and the convexity of the net assets and liabilities portfolio. (That is, I am asking the duration and convexity of Equity = Assets minus Liabilities

The equity is a portfolio $E=Z(0,1)+Z(0,10)-2Z(0,7)$.Thus, the durations and convexity can be easily computed from the duration and convexities of individual securities. In particular

$$D^{E}=\quad\frac{1}{E}\left(1\times Z(0,1)+10\times Z(0,10)-7\times2Z(0,7)\right)=-119.31\\C^{E}=\quad\frac{1}{E}\left(1\times Z(0,1)+10^{2}\times Z(0,10)-7^{2}\times2Z(0,7)\right)=-183.404$$

Note that duration is negative,implying that an increase in interest rates make the value of equity go up (and not down). Also, overall, equity is negatively convex.

(b) (10 points) Given the result in part 4a compute PMVS.L from a 50 basis point shock (positive or negative)

From theformula,we have

$$PMVS.L=-D^E(+/-.5/100)+1/2C^E(.5/100)^2=0.5943/-0.5988$$

That is,variation fo 59% - $60\%$ (!).The value is so higher because the value of equity here is tiny($E=2.8$ while assets $A=179.98$ and liabilities $L=177.18$ That is, this is a super levered position. Given the value of equity $E=2.8$, we can compute the dollar impact of the variation in interest rates,namely,a 50bps increase or decrease in interest rates generates a capital gain /loss of $\$1.66$ and $.\$1.67$.

(c) (10 points) Compute PMVS-YC from a 25 basis point fattening and steepening of the term structure.(Hint:This appears to be applied only toduration and not converity of allinterest rate sensitive securities.Hint 2:Itis OK toassume plus/minus 25 bps change at the eztremes,and 0at the 7-year level).What is larger in absolute value? PMVS_L or PMVS YC?

To compute thePMVS_YC we can decompose the variation in individual compo nents.That is

<table>
	<tbody>
		<tr>
			<th>1</th>
			<th>99.29</th>
			<th>$\overline{1}$</th>
			<th>+.25/100</th>
			<th>0.248225</th>
			<th>-.25/100</th>
			<th>-0.248225</th>
		</tr>
		<tr>
			<td>7</td>
			<td>88.59</td>
			<td>7</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
		</tr>
		<tr>
			<td rowspan="2">10</td>
			<td>80.69</td>
			<td>10</td>
			<td>-.25/100</td>
			<td>-2.01725</td>
			<td>+.25/100</td>
			<td>2.01725</td>
		</tr>
		<tr>
			<td> </td>
			<td> </td>
			<td>Tota</td>
			<td>-1.769025</td>
			<td>Total</td>
			<td> </td>
		</tr>
	</tbody>
