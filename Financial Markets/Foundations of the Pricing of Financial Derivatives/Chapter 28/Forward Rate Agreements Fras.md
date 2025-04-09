# 28.6 FORWARD RATE AGREEMENTS (FRAS)

Recall that an FRA, or forward rate agreement, is a forward contract on an interest rate. Let us assume that we are interested in an FRA on the one-period spot rate. Let the. FRA expire at time 3. Recall that the equilibrium fixed rate that the long agrees to pay. would be the forward rate. From Figure 28.1, that rate would be. $8.2\%$ . There is a slight inconsistency, however, in that $8.2\%$ is a continuously compounded rate, inasmuch as the HJM model is based on the evolution of continuously compounded rates. FRA payoffs are always based on add-on rates. Thus, we need to respecify the term structure in terms of one-period add-on rates. Let us take the one-period continuously compounded spot rate at time 0 of $6.8\%$ . Thus, the present value of 1.0 in one period would be $e^{-0.068}=\hat{0}.9343$ ,a number we have previously used as the price of a one-period zero-coupon bond at time 0. The one-period add-on rate, denoted simply as $r_{:}$ , would, therefore, be $0.9343(1+r)=1$ which gives us $r=7.0365\%$ . We can get this rate directly, however, as $e^{0.068}-1$ . From Figure 28.1, we know that the one-period spot rates are the top numbers in each cell, so we can convert each to its add-on equivalent. With the FRA expiring at time 3, we would need the four possible one-period rates at time 3, which would be.

$$
\begin{array}{r l}&{e^{0.11265}-1=0.119240}\ &{e^{0.09265}-1=0.097078}\ &{e^{0.07265}-1=0.075354}\ &{e^{0.05265}-1=0.050461.}\end{array}
$$

We learned in Chapter 26 that we price the FRA as the forward rate. We can actually use zero-coupon bond prices instead of forward rates. We would have the price of a three-period bond, $B(3)$ , divided by the price of a four-period bond, $B(4)$ , minus 1:

$$
{\frac{B(3)}{B(4)}}-1={\frac{0.8025}{0.7393}}-1=0.085456.
$$

Thus, the parties would reach an agreement at time 0 that at time 3, the long would pay this rate and receive the one-period spot rate at time 3, with the difference discounted by the current spot rate.3 Thus, the four possible payoffs of the FRA at time 3 are their values at time 3, as follows:

$$
V F R A(3,0.085456)^{+++}=(0.119240-0.085456)0.8935=0.0302
$$

$$
V F R A(3,0.085456)^{++-}=(0.097078-0.085456)0.9115=0.0106
$$

$$
V F R A(3,0.085456)^{--+}=(0.075354-0.085456)0.9299=-0.0094
$$

$$
V F R A(3,0.085456)^{\mathrm{--}\mathrm{}}=(0.054061-0.085456)0.9487=-0.0298.
$$

Now, we step back to time 2 and calculate the possible values of the FRA based on the next two payments,

$$
{\begin{array}{r l}&{V F R A(3,0.085456)^{++}=\left[0.5(0.0302)+0.5(0.0106)\right]0.8954=0.0183}\ &{V F R A(3,0.085456)^{+-}=\left[0.5(0.0106)+0.5(-0.0094)\right]0.9226=0.0006}\ &{V F R A(3,0.085456)^{--}=\left[0.5(-0.0094)+0.5(-0.0298)\right]0.9507=-0.0186.}\end{array}}
$$

Usually, we would just show the remaining values in the tree, but it is important to see the following result. Let us step back to time 1 and calculate the possible values of the. FRA:

$$
\begin{array}{r l}&{V F R A(3,0.085456)^{+}=\left[0.5(0.0183)+0.5(0.0006)\right]0.9119=0.0086}\ &{V F R A(3,0.085456)^{-}=\left[0.5(0.0006)+0.5(-0.0186)\right]0.9491=-0.0086.}\end{array}
$$

Notice the symmetry of these values. This result ensures us that the value at time 1 will be zero, which is precisely what we know has to be true for an FRA priced at the equilibrium forward rate. Thus, to summarize, Figure 28.7 shows the tree of values of the FRA.

![](images/e2623bd1b93c24a0b5abc3600a9ff5cb9937a10b925c55ce394ee97e3ef5bafb.jpg)
FIGURE 28.7 Binomial Tree of FRA Values

![](images/136425c84945e3338541c55c5cc1ee79e68e8be58902c884717574e514d257fa.jpg)
FIGURE 28.8 Tree of One-Period Add-on Spot Rates Through Time 2
