---
tags:
  - '#attachment_points'
  - '#cdo_tranche_valuation'
  - '#default_correlation'
  - '#default_distribution'
  - '#equity_tranche'
  - '#itrazz_indices'
  - '#loss_distribution'
  - '#mezzanine_tranche'
  - '#senior_tranche'
  - '#tranche_values'
---
# 21.7 TRANCHE MODELING AND PRICING  

Markets trade the indices and the index tranches actively. As a result, the spreads associated with these instruments should be considered to be arbitrage-free. Still, we would like to understand the price formation, and this requires a modeling effort. The market has over the past few years developed a market standard for this purpose. The specifics of this market standard model are discussed in the next chapter. Here we discuss the heuristics of CDO tranche valuation.  

What determines the tranche values is of course the receipts due to spreads and the potential payoffs due to defaults. The general idea is the same as in any swap. The expected value of the properly discounted cash inflows should equal the expected value of the properly discounted cash outflows. The arbitrage-free spread is that number which makes the expected value of the two streams equal. Clearly, in order to accomplish this we need to find a proper probability distribution to work with. We discuss. this issue using tranche pricing. Tranche values depend on the probabilities that are associated with the payoffs the tranche protection seller will have to make. These probabilities are the ones associated with the number of defaulting companies during a particular time period and their correlation..  

We limit ourselves to one period tranche contracts on an index with $n=3$ names.  

# 21.7.1 A MECHANICAL VIEW OF THE TRANCHES  

Consider a reference portfolio of $n=3$ names. Call them $A,B,C.$ respectively. Limit the time frame to 1-year maturities. Let $D$ represent, as usual, the total number of defaults in a year. The first step in discussing tranche valuation is to obtain the distribution of $D$ . How many possible values can $D$ have? It is clear that with $n=3$ , there are only four scenarios as shown in Figure 21.9.  

At this moment ignore how such probabilities can be obtained and take them as given. Assume that the probability of default is the same for each name and that the recovery is $R$ . Thus,  

$$
p^{A}=p^{B}=p^{C}=p
$$  

We now show how tranche values depend on this probability and on the correlation between the defaults of the three names. We now assume $p$ to be $5\%$ . According to the figure the probability is quite high that there will be no defaults at all, i.e., $D=0$ . The probability associated with more defaults $D$ then gets smaller.  

Now, consider the equity tranche. We have three names, and the equity tranche is bearing the risk of any first name to default. Mezzanine is the protection for the second name, and senior tranche sells protection on the third name. Hence for a protection seller on the senior tranche to pay, all three names need to default. Suppose a market maker now sells protection on the equity tranche. In other words, the market maker will compensate the counterparty as soon as any one of $A,B,$ 0r $C$ defaults. What is the probability of this event? Let. $D$ denote the random variable representing the number of. defaults. Then the probability that there will be at least one default is given by  

$$
P(D=1)+P(D=2)+P(D=3)=1-P(D=0)
$$  

Going back to Figure 21.9, we see that this probability is $1-0.857375=14.2625\%$ in that particular case. This is much higher than the assumed $5\%$ probability that any name defaults individually. Thus writing insurance on a first-to-default contract is much riskier than writing insurance on a particular name in the reference portfolio.18 This is the risk associated with the equity tranche-- the tranche that will get hit first in case of a default.  

An investor may not be willing to take such a risk. He or she may want to write insurance only on the second default. This is the investment in the mezzanine tranche. The tranche has subordination, in the sense that there is a cushion between the defaults and the protection seller's loss. The first default will hit the equity tranche.  

We can calculate the probability that the mezzanine tranche will lose money as,  

![](images/d45d8759ecfc6f9af0dc985cc67182215479266af5d9de7f1d791038ff58b59e.jpg)  

# FIGURE 21.9  

Default probability with three names.  

$$
P(D=2)+P(D=3)=0.007125+0.000125=0.725\%
$$  

One can also write protection for the third default. Here there is even more subordination. Before the insurer suffers any losses, three names must default. In this case, the investment will represent a senior tranche. The probability of making a payoff is simply  

$$
P(D=3)=p\times p\times p=0.05^{3}=0.000125=0.0125\%
$$  

This simple case can be generalized easily to iTraxx indices.  

# 21.7.2 TRANCHE VALUES AND THE DEFAULT DISTRIBUTION  

We use Figure 21.10 to discuss the important relation between the area under the loss density function and the tranche values. First, note that the iTraxx attachment points slice the distribution of. $D$ into five separate pieces. Each tranche is associated with a different area under the density..  

Consider the $3-6\%$ mezzanine tranche as an example. The tranche has two attachment points, the lower attachment point is $3\%$ and the upper attachment point is $6\%$ . In heuristic terms, the lower attachment point represents the subordination, i.e., the cushion the investor has. Defaults up  

![](images/b5e196fad6ed8f3468e91e8dfd5a55892fc80efeacbf7a91f41e5849b2f806ff.jpg)  

# FIGURE 21.10  

Loss distribution.  

to this point do not result in payments of default insurance.1 The upper attachment point represents a threshold of defaults after which the mezzanine protection seller has exhausted all the notional amount invested. Any defaults beyond this point do not hurt the mezzanine investor, simply because the investment does not exist anymore. Thus the area to the right of the upper attachment point is the probability of losing all the investment for that particular tranche..  

Once this point about attachment points is understood, we can now show the relationship between default correlation and tranche values.  

Consider Figure 21.11, giving the distribution of. $D$ , the total number of defaults. Note the difference between Figure 21.11 and Figure 21.10. Figure 21.11 shows the default density function while Figure 21.10 shows a loss distribution for a portfolio. Both distributions depend on the average probability of default. $p$ and on the default correlation. $\rho$ . Suppose in Figure 21.11 the correla-. tion originally was low at. $\rho=0.1$ . This leads to the default distribution 1. Then, keep the. $p$ the same and move the correlation up to, say, $\rho=90\%$ . This leads to loss distribution 2. The distribu-. tion will shift from 1 to 2 as shown in Figure 21.11. Consider the implications..  

The first implication is that as correlation goes up, the distribution is being pressed downward from the middle. However, the area needs to equal one. So, as the middle is compressed, the weight goes to the two endpoints. Note that the figure does not plot parts of the distribution in the middle and somewhat exaggerates the right tail for illustration.  

Second, in terms of defaults this means that as correlation increases the probability of no defaults increases compared to the low correlation case. This is because the probability of credits  

![](images/18c7332a329ead72f4aead4d04be98dc8de71e09ff38728b582a612254cbcdeb.jpg)  

# FIGURE 21.11  

Default distribution.  

surviving together increases. Second, the probability of a very large number of defaults also. increases compared to the low correlation case. At the extreme as. $\rho\to1$ the distribution that is approximately bell-shaped starts looking more like a binomial distribution. As correlation goes to. one, the default probabilities of the different assets start to behave more and more similarly and at the end, they become the same random variable. Hence the value assumed by the random variable $D$ will be either $n$ or 0, i.e., either every name will default or no name will default..  

How do we translate the implications from Figure 21.11 to portfolio losses and tranche values? First consider another distribution, the default loss distribution. Consider a portfolio of defaultable assets issued by. $n$ different debtors. For simplicity, assume that the recovery rates are the same and are known at $R$ . Also, the exposure to each name is. $\$1$ , meaning that the total invest-. ment in the portfolio is. $\$1$ . Then, if one name defaults, the investor loses. $(1-R)$ dollars. The total default loss during a horizon of length. $T$ will depend on how many names default during this time. interval. In other words, default loss depends on the distribution of the random variable $D$ defined earlier. Figure 21.11 showed the distribution of defaults $D$  

We won't discuss here how, but let's assume it is possible to choose a corresponding distribution for portfolio losses and plot the probability of losses as in Figure 21.10. Let's assume that the loss distribution 1 in Figure 21.10 corresponds to a default correlation $\rho=40$ , while the loss distri-. bution 2 in Figure 21.10 corresponds to a default correlation $\rho=90\%$ . Thus we have again a low-. and high-correlation scenario as in Figure 21.11 but with slightly different values which reflect the approximate shapes of the distributions. It turns out that the effect of an increase of default correlation has important insights for tranche valuation. First, note that the probability of the area near $0-3\%$ goes up. The same is true for the probability associated with the other tail. The area near the $12-22\%$ tranche also goes up.  

But this has a second implication. The area on the right of the equity upper attachment point. gets smaller. Implying the probability that the equity investor will lose all his investment has gone down. The equity tranche investor will benefit from this change in the distribution function. The equity tranche spread will go down and the investor who sold protection earlier at the higher rate will have mark-to-market gains. Hence the equity tranche protection seller is long default correlation. In other words, the equity tranche investor will benefit if the correlation increases..  

Third, the probability associated with the cushion of the super senior tranche is also getting. smaller. This implies that the probability is higher and the super senior protection writer will suffer. some losses. The spread on the super senior tranche will go up and the investor who sold protection at a lower spread will have mark-to-market losses. Hence the super senior protection seller is short the default correlation. In other words, the super senior tranche investor will lose if default correla-. tion decreases.  

Finally, note that the effect of these movements is mixed on the mezzanine tranche. The area on the right of the upper attachment point has not changed that much. Hence the probabilities associ-. ated with mezzanine tranche losses are approximately the same and the mezzanine investor is more. or less neutral toward the correlation changes. In the next chapter, we will discuss the sensitivity of tranche values to default correlation in further detail and explain how default correlation can be. traded.  
