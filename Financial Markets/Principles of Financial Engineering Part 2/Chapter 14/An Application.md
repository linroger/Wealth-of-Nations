# 14.6 AN APPLICATION  

The forward measure and measure change technology are relevant for the pricing of many instruments. But there is one instrument class that has recently become quite popular with market participants and that can be priced with this technology. These are CMSs. They have properties that would illustrate some subtleties of the methods used thus far. In order to price them, forward rates need to be projected jointly..  

First, we present a reading that illustrates some of the recent interest in this instrument class.  

# EXAMPLE  

European institutional investors mindful of rising interest rates have been turning to constant maturity swap. products to hedge their long-dated liabilities over the past few months. Whereas mainstream interest rate swaps tend to reference LIBOR, CMS pay-out structures are linked to the 10-year swap rate instead-a useful hedge for investors with long-dated liabilities such as insurance companies.  

As the 10-year euro swap cratered from a peak of $3.77\%$ in April 2011 to a low of $1.44\%$ in early May this year, these firms piled into CMS structures to shield themselves against falling interest rates. The. spectre of the US Federal Reserve scaling back its asset purchases was enough to put paid to this trend. By the end of June, the 10-year swap rate had rocketed to above $2\%$ and CMS products are now gaining traction as a hedge against further rises.  

"Buying of CMS caps has picked up in the first half of the year because of the change of sentiment in the market, which has put rising rates to the forefront of investors' minds," said Ivan Jossang, head of EMEA. rates structuring at Morgan Stanley..  

Caps have traditionally been popular with investors due to the relative simplicity of the structure. Take the example of an investor buying a cap with a $3\%$ strike. If rates rise to $4\%$ by the time the cap expires, the investor will be paid 100 bp on the notional it originally agreed. "CMS is the main light exotic product that  

survived the crisis, and is the most important building block for pay-offs in rates," said Adrian Bracher,   
European head of rates structuring at Credit Suisse. As with many exotic products, CMS flourished in the run-up to the financial crisis and the market has   
since shrunk. There is no longer any CMS market to speak of in Swiss francs and sterling, with dollars and.   
euros remaining the most liquid currencies. [...] French insurance companies are without doubt the most prolific CMS users, and not just because of the.   
proximity of the euro swaps curve to sovereign yields, against which many of their liabilities are.   
benchmarked. They also offer savings products to policyholders comparable to bank deposits, which need.   
hedging if rates go up or down. [...]. Bank hedging of CMS trades has seriously impacted on the swaptions market, making the 10-year euro   
swaption trade at a premium to options on the longer end of the curve. This has led some of the more   
dynamic Dutch and Danish pension funds-which use swaptions to hedge their liabilities-to move into the   
comparatively cheaper 20-year and 30-year contracts, according to Jossang. CMS has also come into play on the asset side of the balance sheet. As 10-year swap rates are higher   
that 3-month Euribor, CMS can act as a useful yield enhancement tool, often overlaid on government bonds   
or even private placements from corporates if their treasurers can be persuaded to come on board.. (Thomson Reuters IFR Issue 1996, CMS makes comeback to hedge rate ri by Christopher Whittall, August 14, 20  

CMSs are instruments that build on the plain vanilla swaps in an interesting way. In a vanilla. swap, a fixed swap rate is exchanged against a floating LIBOR that is an interest rate relevant for that particular settlement period only. In a CMS, this will be generalized. The fixed leg is. exchanged against a floating leg, but the floating leg is not a "one-period" rate. It is itself a multiperiod swap rate that will be determined in the future..  

There are many versions of such exchanges, but as an example we consider the following. Suppose one party decides to pay $4\%$ during the next 3 years against receiving a 2-year swap rate that will be determined at the beginning of each one of those years. The future swap rates are. unknown at time $t_{0}$ and can be considered as floating payments, except they are not floating payments that depend on the perceived volatility for that particular year only. They are themselves averages of 1-year rates. Clearly, such swaps have significant nonlinearities and we cannot do the. same engineering as in the case of a plain vanilla swap.  

An example of CMS is shown in Figure 14.5. The reader can see that what is being exchanged at. each settlement date against a fixed payment is a floating rate that is a function of more than one forward rate. Under these conditions it is impossible to project individual forward rates using individual zero-drift. stochastic differential equations defined under different forward measures. Each leg of the CMS depends. on more than one forward rate and these need to be projected jointly, under a single measure..  

# 14.6.1 ANOTHER EXAMPLE OF MEASURE CHANGE  

This section provides another example to measure change technology from the FRA markets. Paidin-arrears FRAs make time $t_{i+1}$ payoffs:  

$$
N\delta[F(t_{0},t_{i})-L_{t_{i}}]
$$  

![](images/7e0b44a8ecd0f6aeb2e403578170233953c2a17b438f60626578384a0674b0a7.jpg)  

# FIGURE 14.5  

Example of a CMS.  

The market-traded FRAs, on the other hand, settle at time $t_{i}$ according to:  

$$
\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}
$$  

Finally, we have LIBOR-in-arrears FRAs that settle according to  

$$
N\delta[F(t_{0},t_{i})-L_{t_{i}}]
$$  

it time $t_{i}$ As we saw in Chapter 10, the LIBOR-in-arrears FRA payoffs settle in a "nonnatural" Nay, since $L_{t_{i}}$ -related payments would normally be received or paid at time $t_{i+1}$  

We now show that the paid-in-arrears FRA and market-traded FRAs lead to the same forward rate. First, remember that under the $\tilde{P}^{t_{i+1}}$ forward measure for paid-in-arrears FRAs, we have:  

$$
F(t_{0},t_{i})=E_{t_{0}}^{\tilde{P}^{t_{i+1}}}[L_{t_{i}}]
$$  

That is to say, the FRA rate $F\left(t_{0},t_{i}\right)$ is the average of possible values the LIBOR rate might take:  

$$
F(t_{0},t_{i})=\sum_{j=1}^{k}L_{t_{i}}^{j}\tilde{p}_{j}^{t_{i+1}}
$$  

vhere $j$ represents possible states of the world, which are assumed to be discrete and countable. Now, consider the settlement amount of market-traded FRAs:.  

$$
\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}
$$  

Would the forward rate implied by this contract be the same as the paid-in-arrears FRAs?  

The answer is yes. Using the measure change technology, we discuss how this can be shown. The idea is to begin with the expectation of this settlement amount under the. $\tilde{P}^{t_{i}}$ measure and show that it leads to the same forward rate. Thus, begin with.  

$$
E_{t_{0}}^{\tilde{P}^{t_{i}}}\left[\frac{N\delta[F(t_{0},t_{i})-L_{t_{i}}]}{(1+\delta L_{t_{i}})}\right]
$$  

Setting this equal to zero, and rearranging, leads to the pricing equation  

$$
F(t_{0},t_{i})=\frac{E_{t_{0}}^{\tilde{P}^{t_{i}}}[N\delta L_{t_{i}}/(1+\delta L_{t_{i}})]}{E_{t_{0}}^{\tilde{P}^{t_{i}}}[N\delta/(1+\delta L_{t_{i}})]}
$$  

Now we switch measures on the right-hand side of Eq. (14.142). We have two expectations and we will switch measures in both of them. But first, let. $N=1$ and, similarly, $\delta=1$  

Consider the numerator:  

$$
E_{t_{0}}^{\tilde{P}^{i_{i}}}\left[{\frac{L_{t_{i}}}{(1+L_{t_{i}})}}\right]=\sum_{j=1}^{k}{\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}}\tilde{p}_{j}^{t_{i}}
$$  

We know that for time $t_{i}$  

$$
\tilde{p}_{j}^{t_{i}}=\frac{1}{B(t_{0},t_{i})}Q^{j}
$$  

$$
\tilde{p}_{j}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{j}}{B(t_{0},t_{i+1})}Q^{j}
$$  

Thus:  

$$
\tilde{p}_{j}^{t_{i}}=\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

Replacing the right-hand side in Eq. (14.143), we get  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

In this expression, we recognize  

$$
\frac{B(t_{0},t_{i+1})}{B(t_{0},t_{i})}=\frac{1}{1+F(t_{0},t_{i})}
$$  

and  

$$
\frac{1}{B(t_{i},t_{i+1})^{j}}=1+L_{t_{i}}^{j}
$$  

Using these we get the equivalence:  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}=\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{\left(1+F(t_{0},t_{i})\right)}\left(1+L_{t_{i}}^{j}\right)\tilde{p}_{j}^{t_{i+1}}
$$  

Simplifying the common terms on the right-hand side reduces to  

$$
\sum_{j=1}^{k}\frac{L_{t_{i}}^{j}}{1+F(t_{0},t_{i})}\tilde{p}_{j}^{t_{i+1}}
$$  

This we immediately recognize as the expectation:  

$$
E_{t_{0}}^{\tilde{P}^{t_{i+1}}}\left[\frac{L_{t_{i}}^{j}}{1+F(t_{0},t_{i})}\right]
$$  

Now, consider the denominator in Eq. (14.142)  

$$
E_{t_{0}}^{\tilde{P}^{t_{i}}}\left[{\frac{1}{(1+L_{t_{i}})}}\right]=\sum_{j=1}^{k}{\frac{1}{\left(1+L_{t_{i}}^{j}\right)}}\tilde{p}_{j}^{t_{i}}
$$  

Using Eq. (14.144), we switch to the $\tilde{P}^{t_{i+1}}$ measure:  

$$
\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\tilde{p}_{j}^{t_{i}}=\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}
$$  

Use the equivalences in Eq. (14.144), substitute:  

$$
\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{B(t_{0},t_{i})}\frac{B(t_{0},t_{i+1})}{B(t_{i},t_{i+1})^{j}}\tilde{p}_{j}^{t_{i+1}}=\sum_{j=1}^{k}\frac{1}{\left(1+L_{t_{i}}^{j}\right)}\frac{1}{\left(1+F(t_{0},t_{i})\right)}\left(1+L_{t_{i}}^{j}\right)\tilde{p}_{j}^{t_{i+1}}
$$  

Note that, again, the random. $(1+L_{t_{i}}^{j})$ terms conveniently cancel, and on the right-hand side we obtain:  

$$
\begin{array}{l}{{=\displaystyle\sum_{j=1}^{k}\displaystyle\frac{1}{1+F(t_{0},t_{i})}\tilde{p}_{j}^{t_{i+1}}}}\ {{=\displaystyle\frac{1}{(1+F(t_{0},t_{i}))}}}\end{array}
$$  

Putting the numerator and denominator together for general $N$ and $\delta$ gives  

$$
F(t_{0},t_{i})=\frac{E_{t_{0}}^{\tilde{P}_{i}^{\prime}}\left[N\delta L_{t_{i}}/\left(1+\delta L_{t_{i}}\right)\right]}{E_{t_{0}}^{\tilde{P}{}^{i}}\left[N\delta/\left(1+\delta L_{t_{i}}\right)\right]}=\frac{E_{t_{0}}^{\tilde{P}^{i+1}}\left[N\delta\big(N_{t_{i}}^{j}/(1+F(t_{0},t_{i})\delta)\big)\right]}{(N\delta/(1+F(t_{0},t_{i})\delta))}
$$  

We simplify the common terms to get  

$$
F(t_{0},t_{i})=E_{t_{0}}^{\tilde{P}^{I_{i+1}}}\left[L_{t_{i}}^{j}\right]
$$  

Hence, we obtained the desired result. The FRA rate of paid-in-arrears FRAs is identical to the FRA rate of market-traded FRAs and is an unbiased predictor of the LIBOR rate $L_{t_{i}}$ , under the right forward measure.  

We conclude this section with another simple example.  

# EXAMPLE  

We can apply the forward measure technology to mark-to-market practices as well. The paid-in-arrears FRA will settle at time $t_{i+1}$ according to  

$$
\left[L_{t_{i}}-F(t_{0},t_{i})\right]N\delta
$$  

What is the value of this contract at time $t_{1}$ with $t_{0}<t_{1}<t_{i}\dot{.}$  

It is market convention to replace the random variable $L_{t_{i}}$ with the corresponding forward. rate of time $t_{1}$ . We get  

$$
[F(t_{1},t_{i})-F(t_{0},t_{i})]N\delta
$$  

which, in general, will be nonzero. How do we know that this is the correct way to mark the contract to market? We simply take the time $t_{1}$ expectation of:  

$$
\left[L_{t_{i}}-F(t_{0},t_{i})\right]N\delta
$$  

with respect to the natural forward measure of $t_{i+1}$  

$$
E_{t_{1}}^{\tilde{P}^{t_{i+1}}}\left[L_{t_{i}}-F(t_{0},t_{i})\right]N\delta=[F(t_{1},t_{i})-F(t_{0},t_{i})]N\delta
$$  

Where we use the fact that under the $\tilde{P}^{t_{i+1}}$ , the $F(t_{1},t_{i})$ is an unbiased estimate ofd $L_{t_{i}}$  

# 14.6.2 PRICING CMS  

Pricing CMS is known to involve convexity adjustments. Staying within the context of the simple framework used in this chapter, the industry first obtains the $t_{1}\times t_{2}$ and $t_{2}\times t_{3}$ swaption volatilities. Then, knowing that the swap is a Martingale under the "annuity" measure treated in Chapter 17, various transformations under specific assumptions are performed and then the convexity correction to the forward swap rate is estimated. In other words, the industry calculates the $\in\L_{t}$ in the equation  

$$
\mathrm{cms}_{t}=s_{t}^{f}+\in\mathfrak{}_{t}
$$  

where $c m s_{t}$ is the CMS rate, $s_{t}^{f}$ is the relevant forward swap rate, and $\in_{t}$ is the convexity correction.  

It is straightforward to price CMS using the forward LIBOR dynamics discussed earlier and. then use successive measure changes for the required mean corrections. Because CMS offer a good example for such an application, we show a simple case.  

Consider a two-period forward CMS where a fixed CMS rate $x_{t_{0}}$ is paid at times $t_{2}$ and $t_{3}$ against the floating two-period cash swap rate at these times. The present value of the cash flows under the $\tilde{P}^{t_{3}}$ forward probability is given by  

$$
\begin{array}{c}{{0=E_{t_{0}}^{\tilde{P}^{t_{3}}}\Bigg[\big(x_{t_{0}}-s_{t_{1}}\big)\frac{1}{\big(1+L_{t_{0}}\delta\big)\big(1+L_{t_{1}}\delta\big)}+\big(x_{t_{0}}-s_{t_{2}}\big)}}\ {{{}}}\ {{\frac{1}{\big(1+L_{t_{0}}\delta\big)\big(1+L_{t_{1}}\delta\big)\big(1+L_{t_{2}}\delta\big)}\Bigg]N}}\end{array}
$$  

where the settlement interval is assumed to be one and $N$ is the notional swap amount. The. $s_{t_{1}}$ and $s_{t_{2}}$ are the two 2-period swap rates unknown at time. $t_{0}$ . They are given by the usual spot swap for-. mula shown in Eq. (14.49)..  

Setting $\delta=1$ , and rearranging this equation, we obtain  

$$
x_{t_{0}}=\frac{E_{t_{0}}^{\tilde{p}^{3}}\left[s_{t_{1}}\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\right)+s_{t_{2}}\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right)\right]}{E_{t_{0}}^{\tilde{p}^{3}}\left[\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\right)+\left(1/\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right)\right]}
$$  

Hence, to find the value of the CMS rate. $x_{t_{0}}$ , all we need to do is write down the dynamics of the forward LIBOR processes, $F\left(t_{0},t_{1}\right)$ and $F\left(t_{0},t_{2}\right)$ , under the same forward measure $\tilde{P}^{t_{3}}$ as done earlier, and then select Monte Carlo paths.  

It is clear that proceeding in this way and obtaining Monte Carlo paths from the arbitrage-free forward LIBOR dynamics requires calibrating the respective volatilities $\sigma^{i}$ . But once this is done, and once the correction factors are included in the proper equations, the Monte Carlo paths can be selected in a straightforward manner. The CMS rate can then be calculated from  

$$
x_{t_{0}}=\frac{\sum_{j=1}^{M}\left[s_{t_{1}}^{j}\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\right)+s_{t_{2}}^{j}\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\left(1+L_{t_{2}}^{j}\right)\right)\right]}{\sum_{j=1}^{M}\left[\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\right)+\left(1/\left(1+L_{t_{0}}^{j}\right)\left(1+L_{t_{1}}^{j}\right)\left(1+L_{t_{2}}^{j}\right)\right)\right]}
$$  

where the swap rates $s_{t_{i}}^{j}$ themselves depend on the same forward rate trajectories and, hence, can be calculated from the selected paths.  

The same exercise can be repeated by starting from perturbed values of volatilities and initia forward rates to obtain the relevant Greeks for risk-management purposes as well..  
