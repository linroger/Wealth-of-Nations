# 27.4 FILLING IN THE REMAINDER OF THE HJM BINOMIAL TREE

Recall that we started with the rates

$$
\begin{array}{l}{{f(0,0)=0.068}}\ {{}}\ {{f(0,1)=0.072}}\ {{}}\ {{f(0,2)=0.08}}\ {{}}\ {{f(0,3)=0.082.}}\end{array}
$$

From the volatilities and the no-arbitrage condition, we obtained the following rates:

$$
\begin{array}{l}{{f(1,1)^{+}=f(0,1)+\alpha(0,1)+\sigma(0,1)=0.072+0.0002+0.02=0.0922}}\ {{f(1,2)^{+}=f(0,2)+\alpha(0,2)+\sigma(0,2)=0.08+0.0004125+0.015=0.093}}\end{array}
$$

$$
\begin{array}{r l}&{f(1,3)^{+}=f(0,3)+\alpha(0,3)+\sigma(0,1)=0.082+0.0004+0.01=0.0924}\ &{f(1,1)^{-}=f(0,1)+\alpha(0,1)-\sigma(0,1)=0.072+0.0002-0.02=0.0522}\ &{f(1,2)^{-}=f(0,2)+\alpha(0,2)-\sigma(0,2)=0.08+0.0004125-0.015=0.0654125}\ &{f(1,3)^{+}=f(0,3)+\alpha(0,3)-\sigma(0,3)=0.082+0.0004-0.01=0.0724.}\end{array}
$$

We will extend the tree and add the following rates:

$$
\begin{array}{r l}&{f(2,2)^{*}=\left(f(1,2)^{*}+\alpha(1,2)+\alpha(1,3)\right)}\ &{f(2,3)^{*}=\left(\left(f(1,3)^{*}+\alpha(1,3)+\alpha(1,3)\right)}\ &{f(2,3)^{*}=\left(\left(f(1,2)^{*}+\alpha(1,3)-\alpha(1,3)\right)\right.}\ &{\left.\left(f(2,3)^{*}+\alpha(1,3)+\alpha(1,2)-\alpha(1,3)\right.\right.}\ &{\left.\left.\left(f(2,3)^{*}+\alpha(1,2)+\alpha(1,2)+\alpha(1,2)\right.\right.\right.}\ &{\left.\left.\left.\left(f(1,3)^{*}+\alpha(1,3)+\alpha(1,3)+\alpha(1,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(f(2,3)^{*}-\alpha(1,3)+\alpha(1,3)-\alpha(1,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(f(1,3)^{*}+\alpha(1,3)+\alpha(1,2)-\alpha(1,3)\right.\right.\right.}\ &{\left.\left.\left.(f(3,3)^{*}+\alpha(1,3)+\alpha(1,3)+\alpha(1,3)\right.\right.\right.}\ &{\left.\left.\left.(f(3,3)^{*}+\alpha(1,3)+\alpha(1,3)+\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(f(3,3)^{*}+\alpha(2,3)^{*}+\alpha(2,3)-\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(0,3)^{*}+\alpha(2,3)^{*}+\alpha(2,3)+\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(0,3)^{*}+\alpha(2,3)^{*}+\alpha(2,3)-\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(0,3)^{*}+\alpha(2,3)^{*}+\alpha(2,3)-\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(0,3)^{*}+\alpha(2,3)^{*}+\alpha(2,3)-\alpha(2,3)\right.\right.\right.}\ &{\left.\left.\left.\left.(0,3)
$$

In order to obtain the drifts at times 1 and 2, we will need to know the volatilities $\sigma(1,2)$ $\sigma(1,3)$ , and $\sigma(2,3)$ . Making the assumption that the volatilities do not change, then.

$$
\begin{array}{l}{{\sigma(0,2)=\sigma(1,2)}}\ {{}}\ {{\sigma(0,3)=\sigma(1,3)=\sigma(2,3).}}\end{array}
$$

The covariance matrix at time 1 is as follows:

$$
\begin{array}{c c c}{{}}&{{2}}&{{3}}\ {{}}&{{}}&{{\sigma^{2}(1,2)~\sigma(1,2)\sigma(1,3)}}\ {{}}&{{3}}&{{\sigma(1,3)\sigma(1,2)~\sigma^{2}(1,3).}}\end{array}
$$

The term $\sigma^{2}(1,2)$ is the variance of the one-period-ahead forward rate at time 1, and $\sigma^{2}(1,3)$ is the variance of the two-period-ahead forward rate at time 1. The off-diagonal

term $\sigma(1,2)\sigma(1,3)$ , which equals the other off-diagonal term $\sigma(1,3)\sigma(1,2)$ , is the covariance of the one- and two-period-ahead forward rates at time 1. Filling in the numbers we have

$$
\begin{array}{c c}{{2}}&{{3}}\ {{}}&{{}}\ {{\sigma^{2}(1,2)=0.00025}}&{{\sigma(1,2)\sigma(1,3)=(0.015)(0.01)=0.0001S}}\ {{}}&{{}}\ {{\sigma(1,3)\sigma(1,2)=(0.01)(0.015)=0.00015}}&{{\sigma^{2}(1,3)=0.0001.}}\end{array}
$$

Recall that we explained that the drift can be obtained by taking half of the sum of the terms in the appropriate row and column. That is, if we want the drift $\alpha(i,j)$ , we take half the sum of the elements in the $i^{t b}$ row and $j^{t h}$ column, counting element $i j$ only once. Thus, the drifts are obtained as

$$
\begin{array}{l}{\displaystyle\alpha(1,2)=\frac{0.000225}{2}=0.0001125}\ {\displaystyle\alpha(1,3)=\left(\frac{1}{2}\right)(0.00015+0.0001+0.00015)=0.0002.}\end{array}
$$

Then the rates at time 2 will be

$$
2,2)^{++}=f(1,2)^{+}+\alpha(1,2)+\sigma(1,2)=0.0954125+0.0001125+0.015=0.110525975.
$$

$$
\begin{array}{l}{f(2,3)^{++}=f(1,3)^{+}+\alpha(1,3)+\sigma(1,3)=0.0924+0.0002+0.1=01=0.1026}\ {f(2,2)^{+-}=f(1,2)^{+}+\alpha(1,2)-\sigma(1,2)=0.0954125+0.0001125-0.015=.015=.0826}\ {f(2,3)^{+-}=f(1,3)^{+}+\alpha(1,3)-\sigma(1,3)=0.0924+0.0002-0.1=0.826}\ {f(2,2)^{-+}=f(1,2)^{-}+\alpha(1,2)+\sigma(1,2)=0.0654125+0.0001125+0.015=1.015=}\ {f(2,3)^{-+}=f(1,3)^{-}+\alpha(1,3)+\sigma(1,3)=0.0724+0.0002+0.01=0.0826}\ {...}\end{array}
$$

$$
f(2,2)^{--}=f(1,2)^{-}+\alpha(1,2)-\sigma(1,2)=0.0654125+0.0001125-0.015=0.0505.
$$

$$
f(2,3)^{--}=f(1,3)^{-}+\alpha(1,3)-\sigma(1,3)=0.0724+0.0002-0.01=0.0626.
$$

Note that because of the constant volatility assumption, some of these rates are duplicates. This is a reflection of the fact that the tree recombines. For example, we have $f(2,2)^{+--}=$ $f(2,2)^{\mathrm{--+}}$ and $f(2,3)^{+--}=f(2,3)^{--+}$

Moving on to extend our tree to time 3, the covariance matrix of rates at time 2 is simple. We have only the rate $\sigma^{2}(2,3)$ , which is 0.0001. Then the drift,. $\alpha(2,3)=0.0001/2=$ 0.00005. The rates we need will be.

$$
\begin{array}{l}{f(3,3)^{+++}=f(2,3)^{++}+\alpha(2,3)+\sigma(2,3)=0.1026+0.0005+0.11=0.11265}\ {f(3,3)^{+-}=f(2,3)^{++}+\alpha(2,3)-\sigma(2,3)=0.1026+0.0005-0.11=0.09265}\ {f(3,3)^{+-+}=f(2,3)^{+-}+\alpha(2,3)+\sigma(2,3)=0.0826+0.0005+0.01=0.09265}\ {f(2,3)^{+--}=f(2,3)^{+-}\perp.\omega(2,3)-\alpha(7,3)=0.0826.\ A.0005-0.011=0.0725}\end{array}
$$$$
f(3,3)^{+--}=f(2,3)^{+-}+\alpha(2,3)-\sigma(2,3)=0.0826+0.0005-0.01=0.07265
$$

$$
{\begin{array}{l}{f(3,3)^{-++}=f(2,3)^{-+}+\alpha(2,3)+\sigma(2,3)=0.0826+0.0005+0.1=0.09265}\ {f(3,3)^{---}=f(2,3)^{-+}+\alpha(2,3)-\sigma(2,3)=0.0826+0.0005-0.1=0.01265}\ {f(3,3)^{--+}=f(2,3)^{--}+\alpha(2,3)+\sigma(2,3)=0.0626+0.0005+0.1=0.07265}\ {f(3,3)^{----}=f(2,3)^{--}+\alpha(2,3)-\sigma(2,3)=0.0626+0.0005-0.1=0.05625.}\end{array}}
$$

Again, note that the recombining tree means that $f(3,3)^{++--}=f(3,3)^{+--+}=f(3,3)^{--++}$ and $f(3,3)^{+----}=f(3,3)^{--+--}=f(3,3)^{---+}$

We now have the tree filled in through time 3, and it is illustrated in Figure 27.4.

Now we have fit the entire term structure through three periods. If we have done this correctly, which is guaranteed by using the proper drifts, the tree will be arbitrage free. If that is the case, then we should be able to derive a tree for the price of any instrument, such that each price is the discounted value of the expected price the next period, where expectations are taken using the martingale probability of $^1/_{2}$ . We shall illustrate this point. for a four-period zero-coupon bond. First, let us establish its price at time 0. The initial information given is the set of forward rates $f(0,0),f(0,1),f(0,2)$ and $f(0,3)$ . They imply that the price of the bond at time zero should be.

$$
B(0,4)=e^{-(0.068+0.072+0.08+0.082)}=0.7393.
$$

This is the price of a four-year bond at time 0, and we can verify that by going back to the initial set of bond prices. Now, we should also be able to find this price by applying the equivalent approach of rolling through the tree from maturity back to time 0. We start by pricing this bond at time 3, then working backwards. When we arrive at time zero, we should get this price, subject to perhaps a small round-off error.

![](images/c2dca5836f979315e2104b77331d96271655d7e4e51ebb6cf57e08ecb65ff95d.jpg)
FIGURE 27.4 Binomial Tree over Four Periods

The price at time 3 is obtained by discounting the 1.0 face value at the spot rate at time 3, $f(3,3)$ . There are, of course, four states at time 3. Thus, the prices in the four states are

$$
\begin{array}{l}{{B(3,4)^{+++}=e^{-f(3,3)^{+++}}=e^{-0.11265}=0.8935}}\ {{{}}}\ {{B(3,4)^{++-}=e^{-f(3,3)^{++-}}=e^{-0.09265}=0.9115}}\ {{{}}}\ {{B(3,4)^{--+}=e^{-f(3,3)^{--+}}=e^{-0.07265}=0.9299}}\ {{{}}}\ {{B(3,4)^{--}=e^{-f(3,3)^{--}}=e^{-0.05265}=0.9487.}}\end{array}
$$

The prices of this bond at time 2 are found by weighting each of the next two possible outcomes by 0.5 and discounting by the one-period spot rate at time $2,f(2,2)^{++},f(2,2)^{+-}$ and $f(2,2)^{--}$ , depending on which state we are in:

$$
\begin{array}{l c l}{{B(2,4)^{++}=[0.5(0.8935)+0.5(0.9115)]e^{-0.110525}=0.8081}}\ {{B(2,4)^{+-}=[0.5(0.9115)+0.5(0.9300)]e^{-0.080525}=0.8495}}\ {{B(2,4)^{--}=[0.5(0.9300)+0.5(0.9487)]e^{-0.050525}=0.8931.}}\end{array}
$$

Stepping back to time 1, we weight each of the next two values by 0.5 and discount by the one-period spot rate at time $1,f(1,1)^{+}$ and $f(1,1)^{-}$ , depending on the state:

$$
\begin{array}{r l}&{B(1,4)^{+}=[0.5(0.8081)+0.5(0.8495)]e^{-0.0922}=0.7558}\ &{B(1,4)^{-}=[0.5(0.8495)+0.5(0.8931)]e^{-0.0522}=0.8270.}\end{array}
$$

The price at time 0 is found by weighting each of the next two values by 0.5 and discounting by the one-period spot rate at time. $0,f(0,0)$

$$
B(0,4)=[0.5(0.7558)+0.5(0.8270)]e^{-0.068}=0.7393.
$$

This value differs from the value we originally computed by only a round-off error. Hence, the model is arbitrage free.
