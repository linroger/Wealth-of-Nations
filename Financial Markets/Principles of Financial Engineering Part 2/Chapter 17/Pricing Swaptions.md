---
tags:
  - annuity
  - european_swaptions
  - libor_rate
  - swap_measure
  - swaptions
aliases:
  - European Swaptions
  - Pricing Swaptions
  - Swap Measure
key_concepts:
  - annuity definition
  - default-free discount bonds
  - forward swap rate
  - pricing swaptions
  - swap measure
---

# 17.4 PRICING SWAPTIONS  

The pricing and risk management of swaptions can be approached from many angles using various working measures. For example, we have already seen in Chapters 4 and 14 that the time $t_{0}$ forward swap rate $f\left(t_{0},t_{1},T\right)$ for a forward swap that begins at time $t_{1}$ and ends at time $T$ will be a weighted average of the forward rates $F\left(t_{0},t_{i},t_{i+1}\right)$ . If we adopt this representation, a possible working measure would be the time $T$ forward measure. The Martingale dynamics of all forward rates under this measure could be obtained, and swaptions and various other swap derivatives could be priced with it..  

However, we adopt an alternative approach. For some pricing and risk-management problems,. using the swap measure as the working probability may be more convenient. This gives us an. opportunity to discuss this interesting class of working measures in a very simple context. Therefore, we will obtain the pricing functions for European swaptions using the swap measure..  

# 17.4.1 SWAP MEASURE  

The measures considered thus far were obtained using normalization by the price of a single asset.. Under some conditions, we may want to use normalization by the value of a stream of payments. instead of a single asset. One well-known case is the swap measure. We will discuss the swap measure in a simple, two-period model with finite states. The model has the same time and cash flow structure discussed earlier in this chapter. We start with the definition of an annuity..  

Consider a contract that pays. $\delta$ dollars at every. $\delta$ units of time. The payment dates are denoted by $t_{i},$  

$$
t_{i}-t_{i-1}=\delta
$$  

![](a368602be4b860578e64bfff5c53a7f9beb63e1c129a6cd459040d3140997721.jpg)  

# FIGURE 17.4  

Present value of annuity.  

For example, $\delta$ can be 1/2 and the payments would be made every 6 months. The payments continue for $N$ years. This would be an annuity and we could use its time $t$ value to normalize time. $t$ asset prices. This procedure leads us to the swap measure..  

Suppose at time $t_{2}$ there is a finite number of states of the world indexed by. $i=1$ , 2, ..., n. In this context suppose an annuity starts at time $t_{2}$ and makes two payments of 1 dollar at times $t_{3}$ and $t_{4}$ , respectively. Hence, in this case, $\delta=1$ . This situation is shown in Figure 17.4. Obviously, for. simplicity, we eliminated any associated credit risks. The annuity is assumed to be default-free. In reality, such contracts do have significant credit risk as was seen during the GFC..  

The present value of the payments at time $t_{2}$ is a random variable when considered from time $t_{0}$ and is given by the expression:18  

$$
P V_{t_{2}}^{i}=\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}
$$  

Here, $L_{t_{2}}^{i}$ is the time $t_{2}$ LIBOR rate in state $i$ and $F(t_{2},t_{3})^{i}$ is the forward rate at time $t_{2}$ , in state $i$ on a loan that starts at time $t_{3}$ . The loan is paid back at time $t_{4}$ . We are using these rates in order to calculate the time $t_{2}$ present value of the payments that will be received in times $t_{3}$ and $t_{4}$ . These values are state dependent and $P V_{t_{2}}^{i}$ is therefore indexed by $i$  

Using the default-free discount bonds $B(t,t_{3})$ and $B(t,t_{4})$ that mature at times $t_{3}$ and $t_{4}$ , we can write the $P V_{t_{2}}^{i}$ as  

$$
P V_{t_{2}}^{i}=(\delta)B(t_{2},t_{3})^{i}+(\delta)B(t_{2},t_{4})^{i}
$$  

In this representation, the right-hand side default-free bond prices are state dependent, since they are measured at time $t_{2}$  

Suppose two-period interest rate swaps trade actively. A spot swap that will be initiated at time $t_{2}$ is shown in Figure 17.5. The spot swap rate. $s_{t_{2}}^{i}$ for this instrument is unknown at time. $t_{0}$ and this is implied by the $i$ superscript. As of time $t_{0}$ , markets are assumed to trade a forward swap, with a. rate denoted by $f_{t_{0}}$ that corresponds to $s_{t_{2}}^{i}$  

![](d89d4dc7c613f8fb6ba6aebe11bae285311e90409882894e00bddd2d23d707df.jpg)  

# FIGURE 17.5  

Spot swap initiated at date $t_{2}$  

Now consider the time $t_{0}$ market value of a two-period forward swap contract that starts at time $t_{2}$ . In the context of the fundamental theorem of Chapter 12, we can write a matrix equation containing the annuity, the forward swap contract, and the European fixed payer swaption. $S w_{t}$ that delivers the same two-period swap, if $s_{t_{2}}<f_{t_{0}}$ . Putting these assets together in the simplified matrix equation of Chapter 12, we obtain:  

$$
\left[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta\right]=\left[\begin{array}{c c c}{\cdots}&{\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}}&{\cdots}\ {\cdots}&{\frac{1}{\left(f_{t_{0}}-S_{t_{2}}^{i}\right)\delta}}&{\cdots}\ {\cdots}&{\frac{1}{S w_{t_{2}}^{i}}}&{\cdots}\end{array}\right]\left[\begin{array}{c}{\cdots}\ {\cdots}\ {\cdots}\ {\cdots}\end{array}\right]
$$  

Here $\{Q^{i},i=1,...,n\}$ are the $n$ state prices for the period $t_{2}$ . Under the no-arbitrage condition, these exist, and they are positive  

$$
Q^{i}>0
$$  

for all states $i.^{19}$ The last row of the matrix equation shows the swaption's current value as a function of $Q^{i}$ and the state-dependent expiration values of the swaption. In the states of the world where $f_{t_{0}}>s_{t_{2}}^{i}$ , the swaption will expire out-of-the-money and the corresponding $S w_{t_{2}}^{i}$ will be zero. Without loss of generality, let these be the first $m<n$ values:  

$$
S w_{t_{2}}^{i}=0\quad i=1,...,m
$$  

For the remaining. $n-m$ states, the expiration value of the swaption is  

$$
S w_{t_{2}}^{i}=\frac{\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\quad s_{t_{2}}^{i}<f_{t_{0}}
$$  

The first row of the matrix equation shows the value of the annuity. We obtain this row from the arbitrage-free prices of the corresponding default-free discount bonds with par value $\$1$  

$$
B(t_{2},t_{3})^{i}=\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}
$$  

and  

$$
B(t_{2},t_{4})^{i}=\frac{1}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}
$$  

The quantity $B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta$ is, therefore, the present value of the annuity payment. The. same quantity was previously called PV01. In fact, the present discussion illustrates how PV01 comes to center stage as we deal with streams of fixed-income cash flows..  

The first row of the matrix equation gives:  

$$
B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta=\sum_{i=1}^{n}\left[\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]\varrho^{i}
$$  

Now we switch measures and obtain a new type of working probability known as the swap measure. Dividing the first row by the left-hand side we have:.  

$$
1=\sum_{i=1}^{n}\frac{1}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\left[\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3}){}^{i}\delta)}\right]Q^{i}
$$  

We define the measure $\tilde{p}_{i}^{s}$ using this expression:  

$$
\tilde{p}_{i}^{s}=\frac{1}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\left[\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{1\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]Q^{i}
$$  

Note that as long as $Q^{i}>0$ is satisfied, we will have:  

$$
\tilde{p}_{i}^{s}{>}0\quad i{=}1,...,n
$$  

and  

$$
1=\sum_{i=1}^{n}\tilde{p}_{i}^{s}
$$  

Thus, $\tilde{p}_{i}^{s}$ have the properties of a well-defined discrete probability distribution. We call this the. swap measure. We will show two interesting applications of this measure. First, we will see that under. this measure, the corresponding forward swap rate behaves as a Martingale and has very simple dynamics. Second, we will see that by using this measure, we can price European swaptions easily..  

# 17.4.2 THE FORWARD SWAP RATE AS A MARTINGALE  

In order to see why forward swap rates behave as a Martingale under the appropriate swap mea-. sure, consider the second row of the matrix equation in Eq. (17.12). Since the forward swap has a value of zero at the time of initiation, we can write:.  

$$
0=\sum_{i=1}^{n}\left(f_{t_{0}}-s_{t_{2}}^{i}\right)\delta\left[\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}\right]Q^{i}
$$  

We can express this as:  

$$
0=\sum_{i=1}^{n}\left(f_{t_{0}}-s_{t_{2}}^{i}\right)\delta\left[\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}\right]\left[\frac{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}{B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta}\right]Q^{i}
$$  

Now, we use the definition of the swap measure given in Eq. (17.20) and relabel, to get:  

$$
0=\sum_{i=1}^{n}\big(f_{t_{0}}-s_{t_{2}}^{i}\big)[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]\tilde{p}_{i}^{s}
$$  

After taking the constant term outside the summation and eliminating, this becomes:  

$$
0=\sum_{i=1}^{n}{{{\left({{f}_{t_{0}}}-{{s}_{t_{2}}}^{i}\right)}}\tilde{p}_{i}^{s}}
$$  

or again:  

$$
f_{t_{0}}=\sum_{i=1}^{n}s_{t_{2}}^{i}\tilde{p}_{i}^{s}
$$  

which means:  

$$
f_{t_{0}}=E_{t_{0}}^{\tilde{P}^{s}}[s_{t_{2}}]
$$  

Hence, under the swap measure, the forward swap rate behaves as a Martingale. The dynamics of the forward swap rate under this measure can then be written using the SDE:.  

$$
\mathrm{d}f_{t}=\sigma f_{t}\mathrm{d}W_{t}\quad t\in[t_{0},T]
$$  

where we assumed a particular diffusion structure and where $T$ is the general swap maturity. Given. the forward swap rate volatility. $\sigma$ , it would be straightforward to generate Monte Carlo trajectories from these dynamics.  

# 17.4.3 SWAPTION VALUE  

In order to obtain a pricing function for the European swaption, we consider the third row of the matrix equation given in Eq. (17.12). We have:  

$$
S w_{t_{0}}=\sum_{i=1}^{n}S w_{t_{2}}^{i}Q^{i}
$$  

We use the definition of the swap measure $\tilde{P}^{s}$  

$$
\tilde{p}_{i}^{s}=\frac{1}{[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]}\left[\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)}+\frac{1\delta}{\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)}\right]\mathcal{Q}^{i}
$$  

and rewrite the equality in Eq. (17.30):  

$$
S w_{t_{0}}=\sum_{i=m+1}^{n}S w_{t_{2}}^{i}\left[\frac{[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]}{\left(1\delta/\left(1+L_{t_{2}}^{i}\delta\right)\right)+\left(1\delta/\left(1+L_{t_{2}}^{i}\delta\right)(1+F(t_{2},t_{3})^{i}\delta)\right)}\right]\tilde{p}_{i}^{s}
$$  

Note that we succeeded in introducing the swap measure on the right-hand side. Now, we know from Eq. (17.15) that the non-zero expiration values of the swaption are given by.  

Substituting these values in Eq. (17.32) gives,  

$$
S w_{t_{2}}^{i}=\frac{\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\quad s_{t_{2}}^{i}<f_{t_{0}}
$$  

$$
S w_{t_{0}}=\sum_{i=m+1}^{n}\left[\frac{(f_{t_{0}}-s_{t_{2}}^{i})\delta}{\big(1+L_{t_{2}}^{i}\delta\big)}+\frac{\big(f_{t_{0}}-s_{t_{2}}^{i}\big)\delta}{\big(1+L_{t_{2}}^{i}\delta\big)(1+F(t_{2},t_{3})^{i}\delta)}\right]
$$  

$$
\left[\frac{[B(t_{0},t_{3})+B(t_{0},t_{4})]\delta}{\left(\delta/\left(1+L_{t_{2}}^{i}\delta\right)\right)+\left(\delta/\left(1+L_{t_{2}}^{i}\delta\right)\left(1+F(t_{2},t_{3})^{i}\delta\right)\right)}\tilde{p}_{i}^{s}\right]
$$  

We see the important role played by the swap measure here. On the right-hand side of this expression, the state-dependent values of the annuity will cancel out for each $i$ and we obtain the expression:  

$$
S w_{t_{0}}=[B(t_{0},t_{3})+B(t_{0},t_{4})]\sum_{i=m+1}^{n}\left[\left(f_{t_{0}}-s_{t_{2}}^{i}\right)\delta\tilde{p}_{i}^{s}\right]
$$  

This is equivalent to  

$$
S w_{t_{0}}=[B(t_{0},t_{3})+B(t_{0},t_{4})]E_{t_{0}}^{\tilde{p}^{s}}\left[\operatorname*{max}\left[\left(f_{t_{0}}-s_{t_{2}}\right)\delta,0\right]\right]
$$  

Using this pricing equation and remembering that the forward swap rate behaves as a Martingale under the proper swap measure, we can easily obtain a closed-form pricing formula for. European swaptions.  

There are many ways of formulating market practice. One way to proceed is as follows. The market assumes that:  

1. The forward swap rate. $f_{t}$ follows a geometric (log-normal) process  

$$
\mathrm{d}f_{t}=\mu(f_{t},t)\mathrm{d}t+\sigma f_{t}\mathrm{d}W_{t}
$$  

which can be converted into a Martingale by using the swap measure $\tilde{P}^{s}$  

$$
\mathrm{d}f_{t}=\sigma f_{t}\mathrm{d}{\tilde{W}}_{t}
$$  

2. Black's formula can be applied to obtain the value  

$$
f_{t_{0}}N(d_{1})-\kappa N(d_{2})
$$  

with  

$$
d_{1}=\frac{\log(f_{t}/\kappa)+(1/2)\sigma^{2}(t_{2}-t_{0})}{\sigma\sqrt{t_{2}-t_{0}}}
$$  

$$
d_{2}=d_{1}-\sigma{\sqrt{t_{2}-t_{0}}}
$$  

where $t_{2}$ is the expiration of the swaption contract discussed in this section.  

3. Finally, the value of the European swaption $S w_{t}$ is obtained by discounting this value using the present value of the annuity. For time $t_{0}$ , this will give:  

$$
S w_{t_{0}}=[B(t_{0},t_{3})\delta+B(t_{0},t_{4})\delta]\left[f_{t_{0}}N(d_{1})-\kappa N(d_{2})\right]
$$  

In other words, swaptions are priced by convention using Black's formula and then discounting by the value of a proper annuity.  

# 17.4.4 REAL-WORLD COMPLICATIONS  

There may be several complications in the real world. First of all, the market quotes the swaption.   
volatilities $\sigma$ directly, and the preceding formula is used to put a dollar value on a European swap-.   
tion. However, most real-world applications of swaptions are of Bermudan nature and this introduces Americanness to the underlying option. There are no closed formulas for Bermudan.   
Swaptions.  

Second, just as in the case of caps and floors, the existence of the volatility smile introduces significant complications to the pricing of swaptions, especially when they are of the Bermudan type.2o If the swap curve is not flat, then relative to a single strike level, different forward swap rates have different moneyness characteristics. Pricing Bermudan swaptions would then become more complicated.  
