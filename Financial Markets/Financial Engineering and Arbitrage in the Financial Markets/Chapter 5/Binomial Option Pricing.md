---
tags:
  - american_option
  - binomial_option_pricing
  - european_option
  - option_payoff
  - option_pricing
aliases:
  - Binomial Model
  - Option Premium
  - Payoff Manufacturing
key_concepts:
  - Binomial tree examples
  - Dealer's cost of manufacturing
  - Hedge ratio calculation
  - Payoff manufacturing mechanics
  - Risk-neutral probability
---

# 5.6  BINOMIAL OPTION PRICING  

The option premium charged by a dealer reflects his cost of manufacturing the payoff. The dealer sells (or buys) the option, and then borrows or lends money and takes a partial position. in the underlying asset. By the expiry time his hedge is worth exactly the same as the payoff on the option he owes or receives. We will illustrate the mechanics of payoff manufacturing. with increasingly more revealing examples of binomial trees.? All examples use stocks, but. are equally applicable to other traded assets.  

# 5.6.1 One-Step Examples  

We use the following assumptions for Examples 1-3. The underlying stock sells currently for.   
$S=\$50$ a share. The expiry of the option is 1 year from today (or one period with no trading.   
in the underlying between now and expiry). The dealer sells the option, collects the premium,.   
and follows a set of instructions. For Examples 1, 2(a) and 3(a), we also assume that the dealer can borrow or lend money at no interest. On the expiry date, one period from today, the stock.  

can take on two values $S_{u p}=\$70$ or $S_{d n}=\$20$ . The dealer believes that the up probability is $^1/_{4}$ and the down probability is $^3/_{4}$ . He takes the following steps:  

1) Given the potential stock outcomes. $S_{u p}=\mathbb{S}70$ or $S_{d n}=\mathbb{S}20$ for the up and down states. tomorrow, and given today's stock price of $S=\$50$ , the dealer computes a number,.  

$$
q=\frac{S-S_{d n}}{S_{u p}-S_{d n}}
$$  

We will refer to $q$ as the risk-neutral probability of the up state and to. $1-q$ as the riskneutral probability of the down state. These are the only probability-like numbers that the dealer uses in his weighted average calculations, not his subjective beliefs. $^1/_{4}$ and $^3/_{4}$ (he could easily be wrong). The risk-neutral probability,. $q$ , has no meaning outside the context. of this six-step procedure, i.e. it is not a real probability of anything. In our examples, we. compute $q$ to be:  

$$
q=\frac{50-20}{70-20}=\frac{3}{5}=0.60
$$  

2) Given the strike level $K$ and the potential stock outcomes $S_{u p}=\mathbb{S}70$ or $S_{d n}=\$20$ for the up and down states, he assigns the call payoffs $C_{u p}$ and $C_{d n}$ , or put payoffs $P_{u p}$ or $P_{d n}$ , for the corresponding states of nature in the expiry period.  

3) He computes the premium on the option by taking the average of the future option outcomes weighted by the risk-neutral probabilities of the states, i.e..  

$$
C=q C_{u p}+(1-q)C_{d n}\mathrm{or}P=q P_{u p}+(1-q)P_{d n} 
$$  

4) He computes a hedge number  

$$
\Delta=\frac{C_{u p}-C_{d n}}{S_{u p}-S_{d n}}\mathrm{or}\Delta=\frac{P_{u p}-P_{d n}}{S_{u p}-S_{d n}}
$$  

that tells him how many shares of stock he needs to hold (buy or sell) today.  

5) He buys/sells the prescribed number of shares by paying/receiving $\Delta\times S$ . He uses the collected premium in the purchase or sale. If necessary, he borrows/lends $\Delta\times S$ minus the option premium, so that his cash position today is zero.   
6) He liquidates his hedge one period from today when the state of nature is revealed, i.e. the stock either goes up or down. He uses the proceeds to settle his borrowing/lending and to pay the agreed-upon payoff to the option buyer.  

We will show that if he faithfully follows Steps 1-5, then in Step 6 he will always have. on hand the exact amount of money demanded by the option holder, no matter what happens to the stock price. He will not have used his subjective beliefs to gamble on the direction of the stock.  

In our illustrations, we will place all the computed numbers on nodes, as shown in Figure 5.8. Next to today's stock price of $S=50$ , we will show all the numbers from Steps 1-5, i.e.. $q,\Delta$ the option premium $C$ or $P$ , the cost of shares $\Delta\times S$ , and the amount of borrowing/lending $\Delta\times S-C$ or $\Delta\times S-P$ . Next to the potential future stock prices $S_{u p}$ and $S_{d n}$ , we will show. the corresponding value of the option $C_{u p}$ (or $P_{u p}$ ) and $C_{d n}$ (or $P_{d n}$ ), the value of the stock position held from the previous step $\Delta\times S_{u p}$ and $\Delta\times S_{d n}$ , and the cash position carried over from the previous step.  

![](d3d61719d9b52fceacade55433ae79171f73b32ee942d2752056599de9c8c11b.jpg)  
Figure 5.8  

Example 1 Binary lottery, zero interest rate. John Dealer sells a binary "call' option on the stock that pays $\$10$ if the stock ends up at or above. $\$60$ or nothing if it ends up below. $\$60$ one period from today. John's calculations are as follows..  

![](e8f1c3da78b2f84d2389af04b51ec2ab4f80f480bce3bb59ed098388dcee34e1.jpg)  
Figure 5.9 Example 1  

The risk-neutral probability $q=0.60$ . The call payoffs one year from today are 10 if the stock is at 70, or 0 if the stock is at 20. So he sells the call for:  

$$
C=0.60(\mathbb{S}10)+0.40(\mathbb{S}0)=\mathbb{\mathbb{S}}6
$$  

Given his hedge ratio  

$$
\Delta=\frac{10-0}{70-20}=\frac{1}{5}=0.20
$$  

he buys 0.20 shares for $0.20\times50$ or $\$10$ . Since he collected only $\$6$ for the option, he borrows $10-6=\$4$  

One period later, if the stock is at. $\$70$ , his stock position is worth. $0.20\times70=\mathbb{\mathbb{S}}14$ He liquidates it, pays. $\$10$ on the option and repays the borrowing of $\$4$ . If the stock is at. $\$20$ , his stock position is. $0.20\times20=\S4$ .He liquidates it, pays nothing on the option, and repays his borrowing of. $\$4$ . Collecting the premium of $\$6$ on day one has allowed John. to manufacture the payoff he is obligated to make irrespective of whether the stock goes up or down..  

Example 2a Call struck at 55, zero interest rate. John Dealer sells a standard call option on the stock struck at $\$55$ . At expiry, the call pays the value of the stock (i.e. $S_{u p}$ or $S_{d n}$ ) minus the strike ( $K=55$ ) if the stock ends up at or above $\$55$ , or nothing if it ends up below $\$55$ one period from today. John's calculations are shown in Figure 5.10.  

![](9d9ad6ac04694ae3b29f800526f6b879d044475600cc9d8a0632a045c815e3af.jpg)  
Figure 5.10 Example 2a  

The call payoffs are 15 if the stock is at 70, or 0 if the stock is at 20. So he sells the call for:  

$$
C=0.60(\mathbb{S}15)+0.40(\mathbb{S}0)=\mathbb{S}9
$$  

Given his hedge ratio  

$$
\Delta=\frac{15-0}{70-20}=\frac{3}{10}=0.30
$$  

he buys 0.30 shares for $0.30\times50$ or $\$15$ . Since he collected only $\$9$ for the option, he borrows $15-9=\$6$  

One period later, if the stock is at $\$70$ , his stock position is worth $0.30\times70=\mathbb{\mathbb{S}}21$ He liquidates it, pays $\$15$ on the option and repays the borrowing of $\$6.$ If the stock is at $\$20$ , his stock position is $0.30\times20=\mathbb{\mathbb{S}}6.$ He liquidates it, pays nothing on the option, and repays his borrowing of $\$6$  

Example 3a Put struck at 55, zero interest rate. John Dealer sells a standard put option on the stock struck at $\$55$ . At expiry, the put pays the strike ( $K=55$ ) minus the stock value $S_{u p}$ or $S_{d n}$ ) if the stock ends up at or below $\$55$ , or nothing if it ends up above $\$55$ one period from today. John's calculations are as shown in Figure 5.11.  

![](af49fe1aab351056eb67b8b439830719f2f63c29db9274fcb3da59c959c636b5.jpg)  
Figure 5.11 Example 3a  

The put payoffs are 0 if the stock is at 70, or 35 if the stock is at 20. So he sells the put for:  

$$
P=0.60(\S0)+0.40(\S35)=\S14
$$  

Given his hedge ratio  

$$
\Delta=\frac{0-35}{70-20}=-\frac{7}{10}=-0.70
$$  

he shorts 0.70 shares to collect $0.70\times50$ or $\$35$ . Since he collected. $\$14$ for the option, he.   
places the combined proceeds. $35+14=\mathbb{\mathbb{S}}49$ in a deposit (i.e. lends)..  

One period later, if the stock is at $\$70$ , his stock position is worth $-0.70\times70=-\$49$ He liquidates it. He uses the $\$49$ from the deposit to buy the stock back and return it to the lender. He pays nothing on the option. If the stock is at $\$20$ , his stock position is $-0.70\times20=$ $-\$14$ . He uses the. $\$49$ from the deposit to liquidate the stock position $(\$14)$ and pay $\$35$ on the option..  

Let us make a few observations. Once the payoff on the option is defined, the rest is. a mechanical adherence to a recipe. The recipe covers all potential payoff structures - binary, standard, any other exotic - as well as both puts and calls and both bought and sold options. The actions for the dealer who buys the option, instead of selling, would be analogous. They are completely determined by his hedge ratio $\Delta$ . A positive delta means long stock, a negative one means short stock. The borrowing and lending simply balances the cash position resulting from the price of the $\Delta$ amount of stock and the premium on the option.  

Let us now demonstrate that the recipe works with only slight modifications when we do not make the unrealistic assumption that the financing interest rate is zero. Here are the amendments.  

1) The formula for $q$ is changed by replacing today's $S$ with its future value equivalent, i.e. the forward. Recall that the forward is equal to the value of $S$ multiplied by a future value factor, equal to 1 plus the interest rate $r$ for 1 year. For fractions of a year, or special compounding and day-count conventions, it needs to be amended appropriately. For an annual period it is:  

$$
q=\frac{S(1+r)-S_{d n}}{S_{u p}-S_{d n}}
$$  

In our example, we assume that $r=10\%$ and compute $q$ to be:  

$$
q=\frac{50(1.1)-20}{70-20}=\frac{7}{10}=0.70
$$  

2) No change.  

3) We compute the premium on the option by taking the average of the future option outcomes weighted by the risk-neutral probabilities of the states, present-valued to today, i.e.  

$$
C=\frac{1}{1+r}\left[q C_{u p}+(1-q)C_{d n}\right]\mathrm{or}P=\frac{1}{1+r}\left[q P_{u p}+(1-q)P_{d n}\right]
$$  

4) through 6) No change, but we have to remember about interest paid or earned on borrowing or lending when carrying over the cash position from the previous step.  

5) Let us repeat the standard call and put example with a financing cost of $10\%$  

Example 2b Call struck at 55, $10\%$ interest rate. John Dealer sells a standard call option on the stock struck at $\$55$ At expiry, the call pays the value of the stock (i.e. $S_{u p}$ or $S_{d n}$ ) minus the strike ( ${\cal K}=55\$ ) if the stock ends up at or above. $\$55$ , or nothing if it ends up below. $\$55$ one period from today. John's calculations are shown in Figure 5.12.  

![](41971b2f6df407d72711e7d105b1f305ebe1fc9371d0a6ccbffd0aa261f2153a.jpg)  
Figure 5.12 Example 2b  

The call payoffs are still 15 if the stock is at 70, or 0 if the stock is at 20. But he sells the call for:  

$$
C={\frac{1}{1.1}}\left[0.70(\S15)+0.30(\S0)\right]=\S9{\frac{6}{11}}=\S9.54545
$$  

Given his hedge ratio  

$$
\Delta=\frac{15-0}{70-20}=\frac{3}{10}=0.30
$$  

he buys 0.30 shares for $0.30\times50$ or $\$15$ . Since he collected only $\$9–6/11$ for the option, he borrows $15-9{\cdot}6/11=\mathbb{5}5{\cdot}5/11$  

One period later, if the stock is at $\$70$ , his stock position is worth $0.30\times70=\mathbb{\mathbb{S}}21$ He liquidates it, pays $\$15$ on the option and repays the borrowing which has by now accrued to $\$6$ (5-5/11 times 1.1) at the $10\%$ interest rate. If the stock is at $\$20$ , his stock position is $0.30\times20=\mathbb{\mathbb{S}}6.$ He liquidates it, pays nothing on the option, and repays his borrowing and interest of $\$6$  

Example 3b Put struck at 55, $10\%$ interest rate. John Dealer sells a standard put option. on the stock struck at $\$55$ . At expiry, the put pays the strike (. $K=55$ ) minus the stock value. $S_{u p}$ or $S_{d n}$ ) if the stock ends up at or below. $\$55$ , or nothing if it ends up above. $\$55$ one period from today. John's calculations are as shown in Figure 5.13.  

![](a52f6ea786ca4f7219f1b70536dff020c90e566bbd31bc1c0cec996ac140cf1c.jpg)  
Figure 5.13Example 3b  

The put payoffs are unchanged, 0 if the stock is at 70, or 35 if the stock is at 20. He sells the put for:  

$$
P={\frac{1}{1.1}}\left[0.70(\S0)+0.30(\S35)\right]=\S9{\frac{6}{11}}=\S9.54545
$$  

Given his hedge ratio  

$$
\Delta=\frac{0-35}{70-20}=-\frac{7}{10}=-0.70
$$  

he shorts 0.70 shares to collect $0.70\times50$ or $\$35$ . Since he collected. $\$9–6/11$ for the option,.   
he places the combined proceeds $35+9–6/11=\mathbb{\mathbb{S}}44–6/11$ in a deposit (i.e. lends)..  

One period later, if the stock is at $\$70$ , his stock position is worth $-0.70\times70=-\$49$ He liquidates it. He uses the $\$49$ (44-6/11 times 1.1) from the deposit, which has accrued interest in the meantime, to buy the stock back and return it to the lender. He pays nothing on the option. If the stock is at $\$20$ , his stock position is $-0.70\times20=-\$14$ He uses the. $\$49$ from the deposit and interest to liquidate the stock position $(\$14)$ and to pay $\$35$ on the option..  

Let us make a few more observations. First, the hedge ratios are the same as in the zero interest case, but the borrowing/lending grows period to period and makes a difference in the final apportioning of the proceeds at expiry.  

Second, a positive interest rate raised the price of the call and lowered the price of the put. (Examples 2b and 3b relative to 2a and 3a). This is because a call seller borrows money to buy. stock incurring a cost, while a put seller lends money after shorting a stock accruing interest. So the cost of manufacturing the final payoff increases for the short call hedger and decreases. for the short put hedger.  

Thirdly, the price of the call and the put in our example was the same (Examples 2b and 3b). This was not a coincidence. The strike price on both options was equal to. $\$55$ . This is the forward price of the stock for delivery on the expiry date, equal to the spot price of the stock, $\$50$ , times a future value factor reflecting the cost-of-carry, i.e.. $50\times(1+0.10)=\$55$  

This confirms our prior assertion, before we knew anything about option pricing, that a call and a put struck at a forward will have the same cost, so that one can manufacture the forward by buying a call and selling a put struck at the forward price.  

Let us further show that the last property will hold no matter how volatile the stock is between now and expiry. Suppose that instead of potential outcomes of $\$70$ or $\$20$ , the stock is perceived to have potential outcomes of $S_{u p}=\S80$ or $S_{d n}=\$15$ The stock is more volatile and is thus riskier. We follow our recipe using the interest rate of $10\%$ . The forward value of the stock is still the same $\$55$  

Example 2c Call struck at 55, $10\%$ interest rate. John Dealer's calculations are shown in Figure 5.14.  

![](4cacdc38ce5c8bf969a4739d57c07c6b108e3cf59c1dd99c28b70a0ad253669c.jpg)  
Figure 5.14 Example 2c  

He sells the option for. $\$13.986$ a lot more than before (Example 2c relative to 2b), to reflect the increased expected value of the payoff.  

Example 3c Put struck at 55, $10\%$ interest rate. John's calculations are shown in Figure 5.15.  

![](a23f235584d943185452970924c2cc019017c795697da1cdb8b4e3c9a70aee83.jpg)  
Figure 5.15Example 3c  

Again, he sells the option for $\$13.986$ , a lot more than before (Example 3c relative to 3b), to reflect the increased expected value of the payoff.  

In both cases, he sells the call for the same price as the put (Examples 2c and 3c). It will always be true that if the perceived riskiness of the underlying asset increases, both calls and puts will increase in value, but the price of a call struck at a forward will always be equal to the price of a put struck at a forward. This is because the forward does not have anything to do with the volatility of the stock, it simply reflects the cost-of-carry, and a long-call/short-put position, equivalent to the forward, must carry a net zero premium (an on-market forward costs nothing to enter into).  

What we have also shown is that while the subjective probabilities of the stock outcomes are irrelevant, the volatility, or the potential dispersion of the outcomes, is not. The more volatile the stock, the higher the premiums on standard calls and puts (Examples 2c and 3c relative to 2b and 3b). This reflects the asymmetric nature of their payoffs. A more volatile stock means that when the option is in-the-money the payoff is likely to be larger, while when the option is out-of-the-money, the payoff is still the same constant zero. Thus the expected value of the payoff is higher if the volatility is higher.  

# Multistep Example  

Let us now demonstrate the full dynamic process of hedging an option, i.e. manufacturing its payoff. We consider a put struck at $K=54$ , the interest rate $r=2.6\%$ per period (i.e. already decompounded), the stock price currently at 50 and following the dynamics as in Figure 5.16.  

For example, an option with 3 months to expiry might be divided into monthly steps. Over the first month, the stock can go up to 60 or down to 35 (the actual probability of each step is irrelevant). If the stock went down to 35 during the first month, then it can go up to 45 or. down to 20 over the second month, etc. For space and clarity, we will drop the arrows in the. rest of the exposition. We follow the same logic as in one-step examples for each sub-tree. We first compute the risk-neutral probability  

$$
q=\frac{S(1+r)-S_{d n}}{S_{u p}-S_{d n}}
$$  

![](00a8acec272bbce16b0702399da332f2e9066d0abb5eb813c1b979ab7d047027.jpg)  
Figure 5.16 A multistep price tree  

for all sub-trees. For example, for the sub-tree emanating from the 45 point, we have:  

$$
q={\frac{45(1+0.026)-30}{55-30}}=0.6468
$$  

We also determine the payoff of the option at expiry. For example, when the stock price is 45, the payoff would be $54-45=\$9$ . We place the $q\mathrm{s}$ and the final payoffs in the diagram. (Figure 5.17).  

![](51472d0e85d570700fabc137026867768b5df3bfdac7f7feebc52655a68e9bb7.jpg)  
Figure 5.17 A multistep price tree with probabilities and final payoffs  

As in one-step examples, we sweep through the tree backwards to determine the premium on the option today. We use the same equation as before for each node:  

$$
C=\frac{1}{1+r}\left[q C_{u p}+(1-q)C_{d n}\right]\mathrm{or}P=\frac{1}{1+r}\left[q P_{u p}+(1-q)P_{d n}\right]
$$  

![](60cbd64f77d051b39d60e63358f1fe8c8932f8f064ce87810de236a7c552a8ab.jpg)  
Figure 5.18A multistep tree with option prices  

We start with the second-to-last date and consider the sub-trees emanating from all three points We compute put values for all three states: 70, 45, and 20. For the $\$45$ state we compute:  

$$
P={\frac{1}{1+0.026}}\left[0.6468\cdot0+(1-0.6468)\cdot24\right]=8.2620
$$  

For the $\$20$ state we compute:  

$$
P={\frac{1}{1+0.026}}\left[0.6208\cdot24+(1-0.6208)\cdot49\right]=32.6316
$$  

We place the values on the tree diagram (Figure 5.18). We go to one date before the one just computed, and calculate the put values for each node (60 and 35) on this date, using the same equation linking a node on a given date to two future nodes. For example, for the $\$35$ State we get:  

$$
P={\frac{1}{1+0.026}}\left[0.6364\cdot8.2620+(1-0.6364)\cdot32.6316\right]=16.6889
$$  

We proceed recursively like this until we obtain today's value of the put, $P=\$7.3881$  

Next, we demonstrate that no matter which route the stock price takes between today and 3 months from today, the hedge will work perfectly.  

For each node, we compute the hedge number  

$$
\Delta=\frac{C_{u p}-C_{d n}}{S_{u p}-S_{d n}}\mathrm{or}\Delta=\frac{P_{u p}-P_{d n}}{S_{u p}-S_{d n}}
$$  

which tells us how many shares we should hold at that node. In our put example, all deltas will be negative or zero to reflect the fact that we will short shares. For example, for the $\$35$ state 1 month from today the delta is:  

$$
\Delta={\frac{8.2620-32.6316}{45-20}}=-0.9748
$$  

Again we place all the deltas on the diagram (Figure 5.19).  

![](6a36f78628757efb1d7c15052fa51dbc3acac09c5d1697035cc72568bf8c2fe9.jpg)  
Figure 5.19 A multistep tree with deltas  

Depending on the route the stock takes, all trades are now determined by the differences between deltas at subsequent nodes. The lending amounts are also determined by the cash position at each node. Let us go through the tree forward following one hypothetical path.  

Suppose the stock price from today's level of. $\$50$ goes down to $\$351$ month from today, then to $\$452$ months from today, and ends up at. $\$30$ months from today. In order to hedge. our position, we are required to short O.5588 share today. This will result in proceeds of $0.5588\times50=\$27.9406$ We deposit that and the premium received from selling the put, i.e.. a total of $27.9406+7.3881=\$35.3287$ , in an account earning $2.6\%$ per month (Figure 5.20).  

![](5a025a9f777eca2fe6adb7c4a6260192d816bd0e304ee7057ee7406f3004aa54.jpg)  
Figure 5.20  

Next month the price goes down to $\$35$ . Based on our new delta of $-0.9748$ , we need to short additional $0.9748-0.5588=0.4159$ shares. This results in proceeds of $0.4159\times35=$ $\$14.5590$ . Meanwhile, our prior lending accrued to. $35.3287\times(1+0.026)=\$36.2473.$ We re-lend the sum of the two, i.e. $14.5590+36.2473=\$0.8063$ , for another month at $2.6\%$ (Note that the borrowing/lending amount can also be found by subtracting the put value at a node, 16.6889, from the value of the share holding,. $-0.9748\times35=-\$34.1174$ ,i.e. -34.1174 $-16.6889=-\$50.8063$ as in Figure 5.21.)  

![](f7241dded89b596dad403f91356a5295cb6025bd6afc158468b207edd5fc493e.jpg)  
Figure 5.21  

The following month, the stock price increases to. $\$45$ . Based on our new delta of -0.9600, we need to buy back. $0.9748-0.9600=0.0148$ shares. This costs us. $0.0148\times45=\$0.6653$ We take that amount from the maturing deposit which has accrued to $50.8063\times(1+0.026)=$ $\$52.1273$ . We re-lend the remainder $52.1273-0.6653=\$1.4620$ for another month at. $2.6\%$ (Again the borrowing/lending amount can be found by subtracting the put value at a node, 8.2620, from the value of the share holding,. $-~0.9600\times45=-\$43.2000$ , i.e. $-43.2000\textrm{--}$ $8.2620=-\$5$ s in Figure 5.22.)  

![](62e7d069d6b593dd3e202e7c20d6c5a11561433fb8e503520455af48d797ea8a.jpg)  
Figure 5.22  

We proceed to the final step in Figure 5.23. The stock goes down to $\$30$ . We collect the deposit with accrued interest, i.e.. $51.4620\times(1+0.026)=\mathbb{5}52.8000.$ We buy back the shorted. shares for $0.9600\times30=\mathbb{5}28.8000$ and pay $\$24$ to the put holder. We are left with no stock position, no borrowing or lending position, and our put obligation is satisfied.  

One can trace any other path through the tree to see that the result would be identical. We would end up with no stock, no cash, and we would have made a payout on the put, if any was required. The summary of all calculation is portrayed in the completed diagram (Figure 5.24).  

![](a37a2e5ace0f1157313166c5d5f0d2a9cb8b9658ec0d31d754dfb642ac267264.jpg)  
Figure 5.23  

![](02b1facaa7223fba455621130bdb4134aa8a291471f500ce2af754dd1456ec03.jpg)  
Figure 5.24  

The procedure of computing the qs sweeping backwards to get the option value up front and sweeping forward to compute the required hedges and borrowing/lending positions works for all standard calls and puts, digital options, barrier options, American exercise style, and many other options. In all of these cases, the only thing that changes is the recursive computations of the option value during the backward sweep. For example, for American options that can be exercised early, one has to amend the option value for any given node to see if the immediate exercise value is not greater than the unexercised value, i.e..  

$$
\begin{array}{l}{{C=M a x\left\{\displaystyle\frac{1}{1+r}\left[q C_{u p}+(1-q)C_{d n}\right],S-K\right\}\mathrm{or}}}\ {{P=M a x\left\{\displaystyle\frac{1}{1+r}\left[q P_{u p}+(1-q)P_{d n}\right],K-S\right\}}}\end{array}
$$  

This is very easy to implement in any computer code or spreadsheet.  
