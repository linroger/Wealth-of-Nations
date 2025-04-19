---
tags:
  - '#black_scholes_merton_model'
  - '#euler_rule'
  - '#european_option'
  - '#exercise_price'
  - '#forward_contract_on_option'
  - '#forward_start_option'
  - '#linear_homogeneity'
  - '#option_pricing'
  - '#option_replication'
  - '#option_timeline'
---
# 17.7 FORWARD START OPTIONS

Another useful application of Euler's rule is that of a forward start option, which is an option that is purchased today but does not begin until a later date. When the premium is paid today, the purchaser specifies that they wish to acquire an option at a designated later date that has a particular degree of moneyness..

Figure 17.1 illustrates the timeline. Let time $t$ be the day the forward start option is initiated and time $T_{1}$ be the date on which the underlying option is received and $T_{2}$ be the date when the underlying option expires. That is, at time $T_{1}$ $\left\langle t<T_{1}<T_{2}\right\rangle$ when the asset price is $S_{1}$ the option will be granted with an exercise price of. $\alpha S_{1}$ . For example, an at-the-money option has. $\alpha=1$ . An option with exercise price. $5\%$ higher than the asset price has $\alpha=1.05$ . Because we do not know today what the asset price will be at $T_{1}$ , we cannot prespecify the exercise price. This would appear to make it difficult to price the option, but in fact it is easy to price the option because we can use the principle of linear homogeneity. The original reference on this is Rubinstein (1991a)..

![](85311eaa8f6b1f1d9eed441f80580707a9592a41c7080fbd839cd56c3a2b97d6.jpg)
FIGURE 17.1  Forward Start Option Timeline

First let us define. $c(S_{t},\alpha,T_{1},T_{2})$ as the value of a forward start option at time $t$ in which the exercise price is determined at time $T_{1}$ and equals $\alpha$ times the value of the underlying at time $T_{1}$ , and the option expires at time. $T_{2}$ . Although the option is created and paid for at time $t.$ , at time $T_{1}$ , the option formally comes into existence, that is, its exercise price is now declared. At this point, it has the property of a standard European option, which has a time to expiration of. $\tau_{12}$ . Consequently, we know that it is linearly homogeneous with respect to the asset price and exercise price. Writing its value as $c(S_{1},\alpha S_{1},\tau_{12})$ where subscript 1 denotes $t=1$ , we can state that this option's value is equal to

$$
\begin{array}{r}{c\big(S_{1},\alpha S_{1},\tau_{12}\big)=S_{1}c(1,\alpha,\tau_{12}).}\end{array}
$$

The value $c\big(1,\alpha,\tau_{12}\big)$ is known at all times. It is simply the value of an option where the underlying is the value of one unit of the currency, the exercise price is. $\alpha$ , and the time to. expiration is $\tau_{12}$ . One could easily plug these values into the Black-Scholes-Merton model and obtain the value. Even at time. $t$ we know this value. Equation (17.51), however, says. that the forward start option value at time. $T_{1}$ is the product of. $S_{1}$ and this option. At time $t.$ , we do not know what. $S_{1}$ will be, but we can still price the option at time. $t$

To do so, we need to find a combination of instruments that replicates the option, or, in other words, produces a value at. $T_{1}$ equal to that of the option. It should be obvious that holding $c\left(1,\alpha,\tau_{12}\right)$ units of the asset will produce a value of. $c\left(1,\alpha,\tau_{12}\right)S.$ at time $T_{1}$ Consequently, the value of the forward start option today is.

$$
c\left(S_{t},\alpha,\tau_{1},\tau_{2}\right)=S_{t}c\left(1,\alpha,\tau_{12}\right).
$$

In other words, holding $c\big(1,\alpha,\tau_{12}\big)$ units of the asset valued at. $S_{1}$ will reproduce the option. value at time $t$ Do not, however, confuse this statement with any suggestion of full replication. Buying $c\big(1,\alpha,\tau_{12}\big)$ units of the asset at time valued at $S_{t}$ will not replicate the final payoff of the option. The replication strategy is dynamic. We hold a static amount, $c\left(1,\alpha,\tau_{12}\right)$ , of the underlying until time. $T_{1}$ . At that point, we have an option with a fixed exercise price of $S_{1}\alpha$ on an underlying whose value is fluctuating. This option is now an ordinary European call and is replicated using the appropriate number of units of the asset as given by the dynamic delta..

If instead today we specified a fixed exercise price of $X$ , then at $T_{1}$ we are awarded an option with an exercise price of $X$ and a time to expiration of $\tau_{12}$ . Such an option is trivially equal to purchasing an option today with a time to expiration of $\tau_{2}$ and an exercise price of X. If the premium is paid today and the option is received later, it is equivalent to just receiving the option today.

It is important, however, to contrast these types of options with forward contracts on. options. A forward contract on an option is an agreement to purchase an option at a later date. The option will have an exercise price of $X$ and a time to expiration of. $\tau_{12}$ when granted. Being a forward contract, no money is paid today but a price that will be paid at $T_{1}$ is agreed on by the two parties. It is also a simple process to determine this option's price. If today we purchase the option with time to expiration. $\tau_{2}$ and exercise price $X_{:}$ that is, the option described in the previous paragraph, but borrow the premium, then at time $T_{1}$ , we shall have replicated the payoff of the forward contract on the option..

In other words, let $c(S_{t},X,\tau_{2})$ be the price of a call option today struck at. $X$ with time to expiration $\tau_{2}$ . Let $F\bigl[c\bigl(S_{t}X\tau_{2}\bigr),T_{1}\bigr]$ be the forward price agreed on today to purchase the option with current price. $c(S_{t},X,\tau_{2})$ at time $T_{1}$ . The payoff at time. $T_{1}$ will be

$$
c\left(S_{1},X,\tau_{12}\right)-F\left[c\left(S_{t}X\tau_{12}\right),T_{1}\right].
$$

This payoff can be replicated today by purchasing the call option at. $c(S_{t},X,\tau_{2})$ and borrowing $F\left[c\left(S_{t}X\tau_{2}\right),T_{1}\right]e^{-r_{c}\tau_{1}}$ . At time $T_{1}$ , we are holding the option worth. $c\big(S_{t},X,\tau_{12}\big)$ and owe $F\left[c\left(S_{t}X\tau_{2}\right),T_{1}\right]$ , which combine to replicate the payoff of the forward contract.. Because the transaction is a forward contract, it requires no outlay today. Consequently, the value of the position today, $c(S_{t},X,\tau_{2})-F\big[c\big(S_{t}X\tau_{2}\big),T_{1}\big]e^{-r_{c}\tau_{1}}$ , must equal zero, meaning that

$$
F\bigl[c\bigl(S_{t}X\tau_{2}\bigr),T_{1}\bigr]=c\bigl(S_{1},X,\tau_{2}\bigr)e^{r_{c}\tau_{1}}.
$$

Here we see the general rule that the price of a forward contract is the price of the underlying compounded to the expiration of the forward contract. This result will be derived formally in Chapter 22, when we address the pricing of forwards and futures.

If the option is written such that the exercise price is specified as. $\alpha S_{1}$ , then instead of holding the call worth $c(S_{t},X,\tau_{2})$ today, we hold $c(1,\alpha,\tau_{12})$ units of the asset, as determined previously in our derivation of the price of a forward start option. This instrument combines elements of a forward contract on an option and a forward start option.
