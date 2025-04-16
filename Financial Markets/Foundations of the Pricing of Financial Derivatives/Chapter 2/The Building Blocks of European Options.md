---
tags:
  - '#asset_or_nothing_option'
  - '#binary_options'
  - '#cash_or_nothing_option'
  - '#digital_options'
  - '#european_options'
  - '#option_building_blocks'
  - '#option_decomposition'
  - '#option_payoffs'
---
# 2.12 THE BUILDING BLOCKS OF EUROPEAN OPTIONS

There are two types of options that can be seen as the building blocks of standard European. options, and it is useful to introduce them in this chapter. One type is called a binary option or digital option, owing to the fact that there are only two possible payoffs, O or 1..

To create the building blocks of a standard European option, we first introduce an. option that is quite different from a standard European option and has multiple possible. payoffs. This instrument is called an asset-or-nothing option. If the underlying asset value at expiration exceeds the exercise price, an asset-or-nothing call option pays the asset. Otherwise, it pays nothing. If the underlying asset value at expiration is below the exercise. price, an asset-or-nothing put pays the asset and nothing otherwise. This type of option is obviously not binary or digital, but it is covered with binary or digital options, because it complements them to form a standard European option..

The second type of option is called a cash-or-nothing option. If the underlying asset value at expiration exceeds the exercise price, a cash-or-nothing call option pays a fixed amount of money and zero otherwise. If the underlying asset value at expiration is less than the exercise price, a cash-or-nothing put option pays a fixed amount of money and zero otherwise. The standard type of cash-or-nothing option pays $\$1$ , or one other currency unit, or it pays nothing. Hence, it is often called a binary option or a digital option.

The standard European call option can be viewed as a long position in an asset-ornothing call and a short position in $X$ cash-or-nothing calls where the exercise prices of the asset-or-nothing option and the cash-or-nothing option are both $X$

$$
S_{T}>X
$$

Long asset-or-nothing call pays $S_{T.}$

Short $X$ cash-or-nothing calls pay $-X$

Total of $S_{T}-X$

$$
S_{T}\leq X
$$

Long asset-or-nothing call pays 0.

Short $X$ cash-or-nothing calls pay $^{-0}$

Total of 0

As you can see, this creates a payoff identical to the European call option with strike of $X$ . Similarly, a standard European put can be decomposed into a long position in. $X$ cash-or-nothing puts and a short position in an asset-or-nothing put, both options struck at $X$

$$
S_{T}>X
$$

Short asset-or-nothing call pays 0.

Long $X$ cash-or-nothing calls pay 0.

Total of 0

$$
S_{T}\leq X
$$

Short asset-or-nothing call pays $-S_{T}$

Long $X$ cash-or-nothing calls pay $X$

Total of $X-S_{T}$

Asset-or-nothing and cash-or-nothing options can be thought of as the building blocks of a standard option. As such, these instruments are like atoms that make up many things. with which we are most familiar. By analogy, as hydrogen and oxygen can be combined to make water, so various binary options can be combined to make other financial instru-. ments. As you can probably imagine by now, if these fundamental options trade separately, their combined prices must equal that of a European call in the manner shown in this. chapter.
